---
title: Credit Markets Homework 3
tags:
  - bond_pricing
  - bootstrapping
  - credit_market_homework
  - duration_convexity
  - fixed_rate_bond
  - perpetual_bond
  - scenario_analysis
  - sofr_swap
  - yield_curve
aliases:
  - Credit Markets
  - Homework 3
  - Perpetual Bond
  - SOFR Curve
key_concepts:
  - Bond price, DV01, duration
  - Fixed rate corporate bond
  - Perpetual bond pricing
  - SOFR yield curve calibration
  - Scenario bond prices
  - US SOFR swap curve
---

# Credit Markets Homework 3

This homework relies on:

- The SOFR Is symbology file `sofr_swap_symbology`,
- The SOFR swaps market data file `sofr_swaps_market_data_eod` and
- The CDS spreads market data file `cds_market_data_eod`.

-----------------------------------------------------------
# Problem 1: Risk & Scenario analysis for a fixed rate corporate bond (yield model)
## Use the QuantLib Basic notebook (or previous homeworks) as templates

```python
Import QuantLib as ql
Import numpy as np
Import pandas as pd
Import datetime as dt

Def get_ql_date (date) -> ql. Date:
    """
    Convert dt. Date to ql. Date
    """
    If isinstance (date,           dt. Date):
        Return ql.Date (date. Day,           date. Month,           date. Year)
    Elif isinstance (date,           str):
        Date = dt.Datetime.Strptime (date,           "%Y-%m-%d"). Date ()
        Return ql.Date (date. Day,           date. Month,           date. Year)
    Else:
        Raise ValueError (f"to_qldate,           {type (date)},           {date}")
    
Def create_schedule_from_symbology (details: dict):
    '''Create a QuantLib cashflow schedule from symbology details dictionary (usually one row of the symbology dataframe)
    '''
    
    # Create maturity from details['maturity']
    Maturity = get_ql_date (details['maturity'])
    
    # Create acc_first from details['acc_first']
    Acc_first =  get_ql_date (details['acc_first'])
    
    # Create calendar for Corp and Govt asset classes
    Calendar = ql.UnitedStates (ql. UnitedStates. GovernmentBond)
    
    # define period from details['cpn_freq'] … Can be hard-coded to 2 = semi-annual frequency
    Period = ql.Period (2)
    
    # business_day_convention
    Business_day_convention = ql. Unadjusted
    
    # termination_date_convention
    Termination_date_convention = ql. Unadjusted
    
    # date_generation
    Date_generation=ql. DateGeneration. Backward
    
    # Create schedule using ql. MakeSchedule interface (with keyword arguments)
    Schedule = ql.MakeSchedule (effectiveDate=acc_first,            # this may not be the same as the bond's start date
                            TerminationDate=maturity,          
                            Tenor=period,          
                            Calendar=calendar,          
                            Convention=business_day_convention,          
                            TerminalDateConvention=termination_date_convention,          
                            Rule=date_generation,          
                            EndOfMonth=True,          
                            FirstDate=ql.Date (),          
                            NextToLastDate=ql.Date ())
    Return schedule

Def create_bond_from_symbology (details: dict):
    '''Create a US fixed rate bond object from symbology details dictionary (usually one row of the symbology dataframe)
    '''
    
     # Create day_count from details['dcc']
     # For US Treasuries use ql.ActualActual (ql. ActualActual. ISMA)
     # For US [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]] use ql. Thirty 360 (ql. Thirty 360. USA)
    
    If details['class'] == 'Corp':
        Day_count = ql. Thirty 360 (ql. Thirty 360. USA)
    Elif details['class'] == 'Govt':
        Day_count = ql.ActualActual (ql. ActualActual. ISMA)
    Else:
        Raise ValueError (f"unsupported asset class,           {type (details['class'])},           {details['class']}")
    # Create issue_date from details['start_date']
    Issue_date = get_ql_date (details['start_date'])
    
    # Create days_settle from details['days_settle']
    Days_settle = int (float (details['days_settle']))

    # Create coupon from details['coupon']
    Coupon = float (details['coupon'])/100.
    # Create cashflow schedule
    Schedule = create_schedule_from_symbology (details)
    
    Face_value = 100
    Redemption = 100
    
    Payment_convention = ql. Unadjusted
        
    # Create fixed rate bond object
    Fixed_rate_bond = ql.FixedRateBond (
        Days_settle,          
        Face_value,          
        Schedule,          
        [coupon],          
        Day_count,          
        Payment_convention,          
        Redemption,          
        Issue_date)        

    Return fixed_rate_bond

Def get_bond_cashflows (bond: ql. FixedRateBond,           calc_date=ql. Date) -> pd. DataFrame:
    '''Returns all future cashflows as of calc_date,           i.e. with payment dates > calc_date.
    '''    
    Day_counter = bond.DayCounter ()    
    
    X = [(cf.Date (),           day_counter.YearFraction (calc_date,           cf.Date ()),           cf.Amount ()) for cf in bond.Cashflows ()]
    Cf_date,           cf_yearFrac,           cf_amount = zip (*x)
    Cashflows_df = pd.DataFrame (data={'CashFlowDate': cf_date,           'CashFlowYearFrac': cf_yearFrac,           'CashFlowAmount': cf_amount})

    # filter for payment dates > calc_date
    Cashflows_df = cashflows_df[cashflows_df. CashFlowYearFrac > 0]
    Return cashflows_df
Def calibrate_yield_curve_from_frame (
        Calc_date: ql. Date,          
        Treasury_details: pd. DataFrame,          
        Price_quote_column: str):
    '''Create a calibrated yield curve from a details dataframe which includes bid/ask/mid price quotes.
    '''
    Ql.Settings.Instance (). EvaluationDate = calc_date

    # Sort dataframe by maturity
    Sorted_details_frame = treasury_details. Sort_values (by='maturity')    
    
    # For US Treasuries use ql.ActualActual (ql. ActualActual. ISMA)
    Day_count = ql.ActualActual (ql. ActualActual. ISMA)

    Bond_helpers = []
    
    For index,           row in sorted_details_frame.Iterrows ():
        Bond_object = create_bond_from_symbology (row)
        
        Tsy_clean_price_quote = row[price_quote_column]
        Tsy_clean_price_handle = ql.QuoteHandle (ql.SimpleQuote (tsy_clean_price_quote))
        
        Bond_helper = ql.BondHelper (tsy_clean_price_handle,           bond_object)
        Bond_helpers.Append (bond_helper)
        
    Yield_curve = ql.PiecewiseLogCubicDiscount (calc_date,           bond_helpers,           day_count)
    # yield_curve = ql.PiecewiseFlatForward (calc_date,           bond_helpers,           day_count)
    
    Yield_curve.EnableExtrapolation ()
    Return yield_curve
Def get_yield_curve_details_df (yield_curve,           curve_dates=None):
    
    If (curve_dates == None):
        Curve_dates = yield_curve.Dates ()

    dates = [d.to_date () for d in curve_dates]
    Discounts = [round (yield_curve.Discount (d),           3) for d in curve_dates]
    Yearfracs = [round (yield_curve.TimeFromReference (d),           3) for d in curve_dates]
    ZeroRates = [round (yield_curve.ZeroRate (d,           yield_curve.DayCounter (),           ql. Compounded). Rate () * 100,           3) for d in curve_dates]

    Yield_curve_details_df = pd.DataFrame (data={'Date': dates,          
                             'YearFrac': yearfracs,          
                             'DiscountFactor': discounts,          
                             'ZeroRate': zeroRates})                             
    Return yield_curve_details_df
Def calc_clean_price_with_zspread (fixed_rate_bond,           yield_curve_handle,           zspread):
    Zspread_quote = ql.SimpleQuote (zspread)
    Zspread_quote_handle = ql.QuoteHandle (zspread_quote)
    Yield_curve_bumped = ql.ZeroSpreadedTermStructure (yield_curve_handle,           zspread_quote_handle,           ql. Compounded,           ql. Semiannual)
    Yield_curve_bumped_handle = ql.YieldTermStructureHandle (yield_curve_bumped)
    
    # Set Valuation engine
    Bond_engine = ql.DiscountingBondEngine (yield_curve_bumped_handle)
    Fixed_rate_bond.SetPricingEngine (bond_engine)
    Bond_clean_price = fixed_rate_bond.CleanPrice ()
    Return bond_clean_price
Def calibrate_sofr_curve_from_frame (
        Calc_date: ql. Date,          
        Sofr_details: pd. DataFrame,          
        Rate_quote_column: str):
    '''Create a calibrated yield curve from a SOFR details dataframe which includes rate quotes.
    '''
    Ql.Settings.Instance (). EvaluationDate = calc_date

    # Sort dataframe by maturity
    Sorted_details_frame = sofr_details. Sort_values (by='tenor')    
    
    # settle_days
    Settle_days = 2
    
    # For US SOFR [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]] Swaps 
    Day_count = ql. Actual 360 ()

    # For US SOFR Swaps     
    Calendar = ql.UnitedStates (ql. UnitedStates. GovernmentBond)
    
    Sofr_helpers = []
    
    For index,           row in sorted_details_frame.Iterrows ():
        Sofr_quote = row[rate_quote_column]
        Tenor_in_years = row['tenor']
        Sofr_tenor = ql.Period (tenor_in_years,           ql. Years)
        
        # create sofr_rate_helper
        Sofr_helper = ql.OISRateHelper (settle_days,           sofr_tenor,           ql.QuoteHandle (ql.SimpleQuote (sofr_quote/100)),           ql.Sofr ())
                        
        Sofr_helpers.Append (sofr_helper)
        
    Sofr_yield_curve = ql.PiecewiseLinearZero (settle_days,           calendar,           sofr_helpers,           day_count)
    Sofr_yield_curve.EnableExtrapolation ()
    
    Return sofr_yield_curve
Def calibrate_cds_hazard_rate_curve (calc_date,           sofr_yield_curve_handle,           cds_par_spreads_bps,           cds_recovery_rate = 0.4):
    '''Calibrate hazard rate curve from CDS Par Spreads'''
    CDS_settle_days = 2

    CDS_day_count = ql. Actual 360 ()

    # CDS standard tenors: 1 Y,           2 Y,           3 Y,           5 Y 7 Y and 10 Y
    CDS_tenors = [ql.Period (y,           ql. Years) for y in [1,           2,           3,           5,           7,           10]]
    CDS_helpers = [ql.SpreadCdsHelper ((cds_par_spread / 10000.0),           CDS_tenor,           CDS_settle_days,           ql.TARGET (),          
                                  Ql. Quarterly,           ql. Following,           ql. DateGeneration. TwentiethIMM,           CDS_day_count,           cds_recovery_rate,           sofr_yield_curve_handle)
               
    For (cds_par_spread,           CDS_tenor) in zip (cds_par_spreads_bps,           CDS_tenors)]

    # bootstrap hazard_rate_curve
    Hazard_rate_curve = ql.PiecewiseFlatHazardRate (calc_date,           CDS_helpers,           CDS_day_count)
    Hazard_rate_curve.EnableExtrapolation ()

    Return (hazard_rate_curve)
Def get_hazard_rates_df (hazard_rate_curve):
    '''Return dataframe with calibrated hazard rates and survival probabilities'''
    
    CDS_day_count = ql. Actual 360 ()
    
    Hazard_list = [(hr[0]. To_date (),           
                CDS_day_count.YearFraction (calc_date,           hr[0]),          
                Hr[1] * 1 e 4,          
                Hazard_rate_curve.SurvivalProbability (hr[0])) for hr in hazard_rate_curve.Nodes ()]

    Grid_dates,           year_frac,           hazard_rates,           surv_probs = zip (*hazard_list)

    Hazard_rates_df = pd.DataFrame (data={'Date': grid_dates,           
                                     'YearFrac': year_frac,          
                                     'HazardRateBps': hazard_rates,                                               
                                     'SurvivalProb': surv_probs})
    Return (hazard_rates_df)
```

## a. Create generic fixed-rate corporate bond

Fix the calculation date as of April 15 2024 and use a coupon of 5% and a maturity of 10 years (April 15 2034).

Display the fixed rate bond cashflows.

```python
# Import tools from previous homeworks
# Use static calculation/valuation date of 2024-04-15,           matching data available in the market prices EOD file
Calc_date = ql.Date (15,           4,           2024)
Ql.Settings.Instance (). EvaluationDate = calc_date
```

    ---------------------------------------------------------------------------

    ModuleNotFoundError                       Traceback (most recent call last)

    Cell In[99],           line 2
          1 # import tools from previous homeworks
    ----> 2 from credit_market_tools import *
          4 # Use static calculation/valuation date of 2024-04-15,           matching data available in the market prices EOD file
          5 calc_date = ql.Date (15,           4,           2024)
    ModuleNotFoundError: No module named 'credit_market_tools'

```python
# Bond_details
Test_bond_details = {'class': 'Corp',          
                'start_date': '2024-04-15',           
                'acc_first': '2024-04-15',           
                'maturity': '2034-04-15',           
                'coupon': 5,          
                'dcc' : '30/360',          
                'days_settle' : 2}

# Use create_bond_from_symbology () to create the bond
Test_fixed_rate_bond = create_bond_from_symbology (test_bond_details)

Test_fixed_rate_bond_cashflows_df = get_bond_cashflows (test_fixed_rate_bond,           calc_date)
Print (test_fixed_rate_bond_cashflows_df)
```

              CashFlowDate  CashFlowYearFrac  CashFlowAmount
    0   October 15 th,           2024          0.508333             2.5
    1     April 15 th,           2025          1.008333             2.5
    2   October 15 th,           2025          1.508333             2.5
    3     April 15 th,           2026          2.008333             2.5
    4   October 15 th,           2026          2.508333             2.5
    5     April 15 th,           2027          3.008333             2.5
    6   October 15 th,           2027          3.508333             2.5
    7     April 15 th,           2028          4.008333             2.5
    8   October 15 th,           2028          4.508333             2.5
    9     April 15 th,           2029          5.008333             2.5
    10  October 15 th,           2029          5.508333             2.5
    11    April 15 th,           2030          6.008333             2.5
    12  October 15 th,           2030          6.508333             2.5
    13    April 15 th,           2031          7.008333             2.5
    14  October 15 th,           2031          7.508333             2.5
    15    April 15 th,           2032          8.008333             2.5
    16  October 15 th,           2032          8.508333             2.5
    17    April 15 th,           2033          9.008333             2.5
    18  October 15 th,           2033          9.508333             2.5
    19    April 15 th,           2034         10.008333             2.5
    20    April 15 th,           2034         10.008333           100.0

## b. Compute the bond price,  DV 01,  duration and convexity (analytic method)

Assume that the market yield of the bond is 6%. Compute the bond price,  DV 01,  duration and convexity,  using the analytic method.

```python
# Test_bond_yield of 6%
Test_bond_yield = 6

# Test_bond_clean_price
Test_bond_clean_price = test_fixed_rate_bond.CleanPrice (test_bond_yield/100,           test_fixed_rate_bond.DayCounter (),           ql. Compounded,           ql. Semiannual)
Test_bond_dirty_price = test_fixed_rate_bond.DirtyPrice (test_bond_yield/100,           test_fixed_rate_bond.DayCounter (),           ql. Compounded,           ql. Semiannual)

# Compute analytical dv 01,           duration and convexity
Test_bond_yield_rate = ql.InterestRate (test_bond_yield/100,           test_fixed_rate_bond.DayCounter (),           ql. Compounded,           ql. Semiannual)
Test_bond_duration = ql.BondFunctions.Duration (test_fixed_rate_bond,           test_bond_yield_rate)
Test_bond_convexity = ql.BondFunctions.Convexity (test_fixed_rate_bond,           test_bond_yield_rate)
Test_bond_dv 01 = test_bond_duration * test_bond_dirty_price / 100

Print ('test_bond_clean_price: ',           round (test_bond_clean_price,           2))
Print ('test_bond_dirty_price: ',           round (test_bond_dirty_price,           2))
Print ('test_bond_dv 01: ',           round (test_bond_dv 01,           2))
Print ('test_bond_duration: ',           round (test_bond_duration,           2))
Print ('test_bond_convexity: ',           round (test_bond_convexity,           2))
```

    Test_bond_clean_price: 92.56
    Test_bond_dirty_price: 92.58
    Test_bond_dv 01: 7.09
    Test_bond_duration: 7.66
    Test_bond_convexity: 71.74

## c. Scenario bond prices: "re-pricing" vs "second-order approximations"

Compute the scenario bond prices on the following scenario yield grid: [from 1% to 11% in steps of 0.5%]

Compute the second-order scenario price approximations using duration and convexity sensitivities (formula 13 from Lecture 1).

Plot the scenario prices (Y-axis) vs yieds (X-axis),  for both the "re-pricing" and "second-order approximations" method.

Here we are using formula [13] from Lecture 1,  which gives us the second-order price approximation via duration/convexity (second order Taylor expansion in yield parameter).

$$\begin{align}
\Delta B (y) = B\left (y+\Delta y\right)-B\left (y\right)\approx B\cdot\left[D\cdot\Delta y+\frac{1}{2}\cdot\Gamma\cdot\left (\Delta y\right)^{2}\right]
\end{align}$$

We implement formula [13] into the `calc_second_order_price_change (…)` function,           taking into account that $B (y)$ is the dirty bond price.
```python
Def calc_second_order_price_change (dirty_price,           yield_diff,           duration,           convexity):
    Return dirty_price * (yield_diff * duration + 0.5 * yield_diff*yield_diff*convexity)

# Bond_yield_grid : yield grid [from 1% to 11% in steps of 0.5%]    
Bond_yield_grid = [y for y in np.Arange (1,           11.5,           0.5)]

# Scenario_prices
Scenario_prices = [round (test_fixed_rate_bond.CleanPrice (y/100,           test_fixed_rate_bond.DayCounter (),           ql. Compounded,           ql. Semiannual),           3) for y in bond_yield_grid]

# Second_order_approx_prices
Second_order_approx_prices = [round (test_bond_clean_price + calc_second_order_price_change (test_bond_dirty_price,           (y - test_bond_yield) / 100,           test_bond_duration,           test_bond_convexity),           2) 
                                   For y in bond_yield_grid]

# Plot bond_scennarios_df
Bond_scenarios_df = pd.DataFrame (data={'ScenYields': bond_yield_grid,           'ScenPrices': scenario_prices,           'ApproxPrices': second_order_approx_prices})
Print (bond_scenarios_df.Round (1))

# Plot Scenario Prices for "analytic re-pricing" vs "second-order approximations
Plt = bond_scenarios_df.Plot (x='ScenYields',           y=['ScenPrices',           'ApproxPrices'],           grid=True,           style='-*',           title='Scenario Prices for "analytic re-pricing" vs "second-order approximations"',           figsize=(12,          4))
Plt.Axhline (test_bond_clean_price,           color='red',           linestyle='--',           alpha=0.7)
Plt. Set_ylabel ('Scenario Price')
Plt. Set_xlabel ('Yield')

```

        ScenYields  ScenPrices  ApproxPrices
    0          1.0       138.0         136.3
    1          1.5       132.4         131.2
    2          2.0       127.1         126.2
    3          2.5       122.0         121.5
    4          3.0       117.2         116.8
    5          3.5       112.6         112.4
    6          4.0       108.2         108.1
    7          4.5       104.0         104.0
    8          5.0       100.0         100.0
    9          5.5        96.2          96.2
    10         6.0        92.6          92.6
    11         6.5        89.1          89.1
    12         7.0        85.8          85.8
    13         7.5        82.6          82.7
    14         8.0        79.6          79.7
    15         8.5        76.7          76.9
    16         9.0        74.0          74.3
    17         9.5        71.4          71.8
    18        10.0        68.8          69.5
    19        10.5        66.4          67.4
    20        11.0        64.2          65.4
    Text (0.5,           0,           'Yield')
![png](CreditMarketSolutions_200_2.png)
## d. Extreme events scenarios

Compute and show the scenario bond price for a bond yield of 15% (extreme event scenario).

Compute and show the second-order scenario price approximation in the extreme event scenario.

How accurate is the second-order scenario price approximations (using duration and convexity sensitivities)?

Compute and show the analytic DV 01,           duration and convexity in the extreme event scenario.
```python
Extreme_event_bond_yield = 15
Extreme_event_bond_clean_price = round (test_fixed_rate_bond.CleanPrice (extreme_event_bond_yield/100,           test_fixed_rate_bond.DayCounter (),           ql. Compounded,           ql. Semiannual),           3)
Extreme_event_second_order_approx_price = round (test_bond_clean_price + calc_second_order_price_change (test_bond_dirty_price,           (extreme_event_bond_yield - test_bond_yield) / 100,           test_bond_duration,           test_bond_convexity),           2) 
                             
Print ('extreme_event_scenario_price: ',           extreme_event_bond_clean_price)
Print ('extreme_event_approx_price: ',           extreme_event_second_order_approx_price)
Print ('extreme_event_approx_error: ',           round (extreme_event_second_order_approx_price - extreme_event_bond_clean_price,           2))                             
```

    Extreme_event_scenario_price: 49.033
    Extreme_event_approx_price: 55.62
    Extreme_event_approx_error: 6.59
-----------------------------------------------------------
# Problem 2: Perpetual bonds
## a. Price a fixed rate perpetual bond
We are interested in a fixed rate perpetual bond (infinite maturity) on a face notional of $100 and semi-annual coupon c.

Assuming that the bond has a (continuously componded) yield of y,           what is the fair value price of the bond?

For simplicity,           you can assume T+0 settlement and zero accrued. 

You can use following sympy code (implementing Formula 5 from Session 1) as a starting point.
```python
# Import libraries
Import sympy as sp

# Define fixed rate bond specs as symbolic variables
T = sp.Symbols ('T')
C = sp.Symbols ('c')
Y = sp.Symbols ('y')

# Define symbolic equation for generic fixed rate bond pv
Bond_pv_eq =  1 + (c/2  / (sp.Exp (y/2) - 1) - 1 )* (1 - sp.Exp (-T*y))
Print ('Analytic formula for bond_pv: ',           bond_pv_eq)
Display (bond_pv_eq)
```

    Analytic formula for bond_pv: (1 - exp (-T*y))*(c/(2*(exp (y/2) - 1)) - 1) + 1
$\displaystyle \left (1 - e^{T y}\right) \left (\frac{c}{2 \left (e^{\frac{y}{2}} - 1\right)} - 1\right) + 1$
We start with the formula for pricing a risky fixed rate bond on a face of 100%,           derived in Lecture 1,           formulas [4] and [5].

$$\begin{align}
B_{0}^{T}=B (0,           c,           T,           y)=\sum_{k=1}^{2 T}\frac{c}{2}\cdot e^{-k\cdot\frac{y}{2}}+e^{-T\cdot y}
\end{align}$$

$$\begin{align}
=1+\frac{\frac{c}{2}-\left (e^{\frac{y}{2}}-1\right)}{e^{\frac{y}{2}}-1}\cdot\left (1-e^{-T\cdot y}\right)
\end{align}$$

$$\begin{align}
=1+\frac{c-y_{sa}}{y_{sa}}\cdot\left[1-\left (1+\frac{y_{sa}}{2}\right)^{-2 T}\right]
\end{align}$$

Remember that the the semi-annual yield is given by:  $y_{sa} = 2 \cdot \left (e^{\frac{y}{2}}-1 \right)$.

In the case of the fixed rate perpetual bond,           the bond maturity and cashflows extend to "infinity",           so the pricing formula simplifies in terms of $y_{sa}$ to

$$\begin{align}
B_{0}^{\infty}=B (0,           c,          \infty,           y)=\sum_{k=1}^{\infty}\frac{c}{2}\cdot e^{-k\cdot\frac{y}{2}} =  \frac{c}{2 \cdot \left (e^{\frac{y}{2}}-1 \right)}=\frac{c}{y_{sa}},          
\end{align}$$
To obtain the fair price on a face of $100,           one has to multiply the formula above by 100:
$$\begin{align}
B_{0}^{\infty}(100) =  \frac{100 \cdot c}{2 \cdot \left (e^{\frac{y}{2}}-1 \right)} = 100 \cdot \frac{c}{y_{sa}},          
\end{align}$$
## b. Perpetual bonds priced "at par"
For which yield y does the bond trade "at par",           i.e. fair value price = $100?

$$\begin{align}
B_{0}^{\infty}(100)=100 \iff y=2\cdot \ln \left ( 1 + \frac{c}{2} \right) \iff y_{sa} = c.
\end{align}$$
Hence,           the perpetual bond trades "at par" if the smi-annual yield $y_{sa}$ matches the semi-annual coupon c (same result as for "regular" fixed rate bonds).

## c. Duration and DV 01 for a fixed rate perpetual bond
Compute Duration and DV 01 of the perpetual bond.
```python
# Define symbolic equations
Perpetual_bond_price = c / (sp.Exp (y/2) - 1) / 2
Print ('1. Perpetual bond price (with coupon c): ')
Display (perpetual_bond_price)

# Find first and second order derivatives
First_order_derivative = perpetual_bond_price.Diff (y)
Print ('2. Perpetual bond DV 01: ')
Display (-first_order_derivative)

Perpetual_bond_duration =  sp.Simplify (first_order_derivative / perpetual_bond_price)
Print ('3. Perpetual bond duration: ')
Display (perpetual_bond_duration)
```

    1. Perpetual bond price (with coupon c):
$\displaystyle \frac{c}{2 \left (e^{\frac{y}{2}} - 1\right)}$
    2. Perpetual bond DV 01:
$\displaystyle \frac{c e^{\frac{y}{2}}}{4 \left (e^{\frac{y}{2}} - 1\right)^{2}}$
    3. Perpetual bond duration:
$\displaystyle \frac{e^{\frac{y}{2}}}{2 e^{\frac{y}{2}} - 2}$
Hence,           PV 01 and duration of a fixed rate perpetual bond are given by

$$\begin{align}
PV 01 = -\frac{\partial B}{\partial y} = -\frac{\partial}{\partial y}\left[\frac{c}{2 \cdot \left ( e^{\frac{y}{2}}-1 \right) }\right]=\frac{c \cdot e^{\frac{y}{2}}}{4 \cdot \left ( e^{\frac{y}{2}} - 1 \right)^2} = \frac{c \cdot \left ( 1 + \frac{y_{sa}}{2} \right) }{y_{sa}^2}
\end{align}$$
$$\begin{align}
D = -\frac{1}{B} \cdot \frac{\partial B}{\partial y} = \frac{e^{\frac{y}{2}}}{2 \cdot \left ( e^{\frac{y}{2}} - 1 \right)} = \frac{1 + \frac{y_{sa}}{2} }{y_{sa}}.
\end{align}$$
## d. Convexity of a fixed rate perpetual bond
Compute the convexity of the perpetual bond.
```python
Second_order_derivative = sp.Simplify (first_order_derivative.Diff (y))
Print ('Second order derivative: ')
Display (second_order_derivative)

Perpetual_bond_convexity =  sp.Simplify (second_order_derivative / perpetual_bond_price)
Print ('Perpetual bond convexity: ')
Display (perpetual_bond_convexity)

```

    Second order derivative:
$\displaystyle - \frac{c \left (\left (e^{\frac{y}{2}} - 1\right) e^{\frac{y}{2}} - 2 e^{y}\right)}{8 \left (e^{\frac{y}{2}} - 1\right)^{3}}$
    Perpetual bond convexity:
$\displaystyle \frac{\left (1 + e^{- \frac{y}{2}}\right) e^{y}}{4 \left (2 e^{\frac{y}{2}} + e^{y} + 1\right)}$
Hence,           second order derivative and convexity $\Gamma$ of the fixed rate perpetual bond are given by

$$\begin{align}
\frac{\partial^{2} B}{\partial y^{2}} = \frac{\partial^{2}}{\partial y^{2}}\left[\frac{\frac{c}{2}}{e^{\frac{y}{2}}-1}\right] = \frac{\partial}{\partial y}\left[\frac{c \cdot e^{\frac{y}{2}}}{4 \cdot \left ( e^{\frac{y}{2}} - 1 \right)^2} \right] = \frac{c \cdot e^{\frac{y}{2}} \cdot \left (e^{\frac{y}{2}} + 1 \right)}{8 \cdot \left ( e^{\frac{y}{2}} - 1 \right)^3}  = \frac{c \cdot \left ( 1 + \frac{y_{sa}}{2} \right) \cdot \left ( 2 + \frac{y_{sa}}{2} \right)}{y_{sa}^3}
\end{align}$$

$$\begin{align}
\Gamma = \frac{1}{B} \cdot \frac{\partial^{2} B}{\partial y^{2}} = \frac{e^{\frac{y}{2}} \cdot \left (e^{\frac{y}{2}} + 1 \right)}{4 \cdot \left ( e^{\frac{y}{2}} - 1 \right)^2} =  \frac{\left ( 1 + \frac{y_{sa}}{2} \right) \cdot \left ( 2 + \frac{y_{sa}}{2} \right)}{y_{sa}^2}. 
\end{align}$$
-----------------------------------------------------------
# Problem 3: US SOFR swap curve calibration as of 2024-04-15
### Follow Section "1. SOFR [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]] swap rates and SOFR discount curve calibration + validation" in the QuantLib Advanced notebook !

## a. Load and explore US SOFR swaps symbology and market data

Load the `sofr_swap_symbology` Excel file into a dataframe. Print all swap tenors available.

Load the `sofr_swaps_market_data_eod` Excel file into a dataframe. Print all dates available.

Plot the historial time series of SOFR rates for the available [1 Y,           2 Y,           3 Y,           5 Y,           7 Y,           10 Y,           20 Y,           30 Y] tenors.
```python
# Sofr_symbology
Sofr_symbology = pd. Read_excel ('./data/sofr_swaps_symbology. Xlsx')
Sofr_symbology. Set_index ('figi',           inplace=True)
Display (sofr_symbology)

# Sofr_market_quotes
Sofr_market_quotes = pd. Read_excel ('./data/sofr_swaps_market_data_eod. Xlsx')
# Print (sofr_market_quotes.Head ())

# Pivot to get SOFR rates time series
Sofr_quotes_ts = sofr_market_quotes.Pivot (index="date",           columns="figi",           values="midRate")
Sofr_quotes_ts. Columns = sofr_symbology. Tenor[sofr_quotes_ts. Columns]
# Print (sofr_quotes_ts.Head ())

Plt = sofr_quotes_ts.Plot (grid=True,           style='-',           title='SOFR Swaps: historical time series',           figsize=(12,          8))
Plt. Set_ylabel ('SOFR Rate')
Plt. Set_xlabel ('Date')
```
<div>
<style scoped>
    .dataframe tbody tr th: only-of-type {
        Vertical-align: middle;
    }

    .dataframe tbody tr th {
        Vertical-align: top;
    }

    .dataframe thead th {
        Text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ticker</th>
      <th>class</th>
      <th>bbg</th>
      <th>name</th>
      <th>tenor</th>
      <th>type</th>
      <th>dcc</th>
      <th>exchange</th>
      <th>country</th>
      <th>currency</th>
      <th>status</th>
    </tr>
    <tr>
      <th>figi</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>BBG 00 KFWPJJ 9</th>
      <td>USOSFR 1</td>
      <td>Curncy</td>
      <td>USOSFR 1 Curncy</td>
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 1 Y</td>
      <td>1</td>
      <td>SWAP</td>
      <td>ACT/360</td>
      <td>NONE</td>
      <td>US</td>
      <td>USD</td>
      <td>ACTV</td>
    </tr>
    <tr>
      <th>BBG 00 KFWPJX 3</th>
      <td>USOSFR 2</td>
      <td>Curncy</td>
      <td>USOSFR 2 Curncy</td>
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 2 Y</td>
      <td>2</td>
      <td>SWAP</td>
      <td>ACT/360</td>
      <td>NONE</td>
      <td>US</td>
      <td>USD</td>
      <td>ACTV</td>
    </tr>
    <tr>
      <th>BBG 00 KFWPK 15</th>
      <td>USOSFR 3</td>
      <td>Curncy</td>
      <td>USOSFR 3 Curncy</td>
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 3 Y</td>
      <td>3</td>
      <td>SWAP</td>
      <td>ACT/360</td>
      <td>NONE</td>
      <td>US</td>
      <td>USD</td>
      <td>ACTV</td>
    </tr>
    <tr>
      <th>BBG 00 KFWPK 51</th>
      <td>USOSFR 5</td>
      <td>Curncy</td>
      <td>USOSFR 5 Curncy</td>
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 5 Y</td>
      <td>5</td>
      <td>SWAP</td>
      <td>ACT/360</td>
      <td>NONE</td>
      <td>US</td>
      <td>USD</td>
      <td>ACTV</td>
    </tr>
    <tr>
      <th>BBG 00 KFWPK 79</th>
      <td>USOSFR 7</td>
      <td>Curncy</td>
      <td>USOSFR 7 Curncy</td>
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 7 Y</td>
      <td>7</td>
      <td>SWAP</td>
      <td>ACT/360</td>
      <td>NONE</td>
      <td>US</td>
      <td>USD</td>
      <td>ACTV</td>
    </tr>
    <tr>
      <th>BBG 00 KFWPKB 4</th>
      <td>USOSFR 10</td>
      <td>Curncy</td>
      <td>USOSFR 10 Curncy</td>
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 10 Y</td>
      <td>10</td>
      <td>SWAP</td>
      <td>ACT/360</td>
      <td>NONE</td>
      <td>US</td>
      <td>USD</td>
      <td>ACTV</td>
    </tr>
    <tr>
      <th>BBG 00 KFWPKF 0</th>
      <td>USOSFR 20</td>
      <td>Curncy</td>
      <td>USOSFR 20 Curncy</td>
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 20 Y</td>
      <td>20</td>
      <td>SWAP</td>
      <td>ACT/360</td>
      <td>NONE</td>
      <td>US</td>
      <td>USD</td>
      <td>ACTV</td>
    </tr>
    <tr>
      <th>BBG 00 KFWPKH 8</th>
      <td>USOSFR 30</td>
      <td>Curncy</td>
      <td>USOSFR 30 Curncy</td>
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 30 Y</td>
      <td>30</td>
      <td>SWAP</td>
      <td>ACT/360</td>
      <td>NONE</td>
      <td>US</td>
      <td>USD</td>
      <td>ACTV</td>
    </tr>
  </tbody>
</table>
</div>
    Text (0.5,           0,           'Date')
![png](CreditMarketSolutions_216_2.png)
## b. Calibrate the US SOFR yield curve (via bootstrapping)
The function below shows how to calibrate a smooth yield/discount factor curve from SOFR swaps. 

Prepare a joint symbology & market dataframe quotes as of 2024-04-15. 

Calibrate the SOFR discount factor curve as of 2024-04-15.

Follow section 1 b in the QuantLib Advanced notebook.
```python
Def calibrate_sofr_curve_from_frame (
        Calc_date: ql. Date,          
        Sofr_details: pd. DataFrame,          
        Rate_quote_column: str):
    '''Create a calibrated yield curve from a SOFR details dataframe which includes rate quotes.
    '''
    Ql.Settings.Instance (). EvaluationDate = calc_date

    # Sort dataframe by maturity
    Sorted_details_frame = sofr_details. Sort_values (by='tenor')    
    
    # settle_days
    Settle_days = 2
    
    # For US SOFR [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]] Swaps 
    Day_count = ql. Actual 360 ()

    # For US SOFR Swaps     
    Calendar = ql.UnitedStates (ql. UnitedStates. GovernmentBond)
    
    Sofr_helpers = []
    
    For index,           row in sorted_details_frame.Iterrows ():
        Sofr_quote = row[rate_quote_column]
        Tenor_in_years = row['tenor']
        Sofr_tenor = ql.Period (tenor_in_years,           ql. Years)
        
        # create sofr_rate_helper
        Sofr_helper = ql.OISRateHelper (settle_days,           sofr_tenor,           ql.QuoteHandle (ql.SimpleQuote (sofr_quote/100)),           ql.Sofr ())
                        
        Sofr_helpers.Append (sofr_helper)
        
    Sofr_yield_curve = ql.PiecewiseLinearZero (settle_days,           calendar,           sofr_helpers,           day_count)
    Sofr_yield_curve.EnableExtrapolation ()
    
    Return sofr_yield_curve
```
```python
# Sofr_combined
Sofr_combined = sofr_symbology.Merge (sofr_market_quotes[sofr_market_quotes['date'] == '2024-04-15'],           how='left',           on=['figi'])
Display (sofr_combined.Head ())

# Calibrate SOFR discount curve
Sofr_yield_curve = calibrate_sofr_curve_from_frame (calc_date,           sofr_combined,           'midRate')
Sofr_yield_curve_handle = ql.YieldTermStructureHandle (sofr_yield_curve)

```
<div>
<style scoped>
    .dataframe tbody tr th: only-of-type {
        Vertical-align: middle;
    }

    .dataframe tbody tr th {
        Vertical-align: top;
    }

    .dataframe thead th {
        Text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>figi</th>
      <th>ticker</th>
      <th>class</th>
      <th>bbg</th>
      <th>name</th>
      <th>tenor</th>
      <th>type</th>
      <th>dcc</th>
      <th>exchange</th>
      <th>country</th>
      <th>currency</th>
      <th>status</th>
      <th>date</th>
      <th>bidRate</th>
      <th>askRate</th>
      <th>midRate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>BBG 00 KFWPJJ 9</td>
      <td>USOSFR 1</td>
      <td>Curncy</td>
      <td>USOSFR 1 Curncy</td>
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 1 Y</td>
      <td>1</td>
      <td>SWAP</td>
      <td>ACT/360</td>
      <td>NONE</td>
      <td>US</td>
      <td>USD</td>
      <td>ACTV</td>
      <td>2024-04-12</td>
      <td>5.1753</td>
      <td>5.1831</td>
      <td>5.1792</td>
    </tr>
    <tr>
      <th>1</th>
      <td>BBG 00 KFWPJX 3</td>
      <td>USOSFR 2</td>
      <td>Curncy</td>
      <td>USOSFR 2 Curncy</td>
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 2 Y</td>
      <td>2</td>
      <td>SWAP</td>
      <td>ACT/360</td>
      <td>NONE</td>
      <td>US</td>
      <td>USD</td>
      <td>ACTV</td>
      <td>2024-04-12</td>
      <td>4.8155</td>
      <td>4.8225</td>
      <td>4.8190</td>
    </tr>
    <tr>
      <th>2</th>
      <td>BBG 00 KFWPK 15</td>
      <td>USOSFR 3</td>
      <td>Curncy</td>
      <td>USOSFR 3 Curncy</td>
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 3 Y</td>
      <td>3</td>
      <td>SWAP</td>
      <td>ACT/360</td>
      <td>NONE</td>
      <td>US</td>
      <td>USD</td>
      <td>ACTV</td>
      <td>2024-04-12</td>
      <td>4.5742</td>
      <td>4.5818</td>
      <td>4.5780</td>
    </tr>
    <tr>
      <th>3</th>
      <td>BBG 00 KFWPK 51</td>
      <td>USOSFR 5</td>
      <td>Curncy</td>
      <td>USOSFR 5 Curncy</td>
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 5 Y</td>
      <td>5</td>
      <td>SWAP</td>
      <td>ACT/360</td>
      <td>NONE</td>
      <td>US</td>
      <td>USD</td>
      <td>ACTV</td>
      <td>2024-04-12</td>
      <td>4.3085</td>
      <td>4.3143</td>
      <td>4.3114</td>
    </tr>
    <tr>
      <th>4</th>
      <td>BBG 00 KFWPK 79</td>
      <td>USOSFR 7</td>
      <td>Curncy</td>
      <td>USOSFR 7 Curncy</td>
      <td>USD [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]]  ANN VS SOFR 7 Y</td>
      <td>7</td>
      <td>SWAP</td>
      <td>ACT/360</td>
      <td>NONE</td>
      <td>US</td>
      <td>USD</td>
      <td>ACTV</td>
      <td>2024-04-12</td>
      <td>4.2025</td>
      <td>4.2085</td>
      <td>4.2055</td>
    </tr>
  </tbody>
</table>
</div>
## c. Display the calibrated SOFR discount curve dataframe

Follow section 1 d (in the QuantLib Advanced notebook) to display the calibration details dataframe.
```python
# Display and plot SOFR yield curve
Grid_dates = [sofr_yield_curve.ReferenceDate () + ql.Period (y,           ql. Years) for y in list (range (0,          30,          1))]
Sofr_yield_curve_simple_df = get_yield_curve_details_df (sofr_yield_curve)                  # using calibration grid
Sofr_yield_curve_details_df = get_yield_curve_details_df (sofr_yield_curve,           grid_dates)    # using external grid

Display (sofr_yield_curve_simple_df)
Display (sofr_yield_curve_details_df)
```
<div>
<style scoped>
    .dataframe tbody tr th: only-of-type {
        Vertical-align: middle;
    }

    .dataframe tbody tr th {
        Vertical-align: top;
    }

    .dataframe thead th {
        Text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>YearFrac</th>
      <th>DiscountFactor</th>
      <th>ZeroRate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2024-04-16</td>
      <td>0.000</td>
      <td>1.000</td>
      <td>5.177</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2025-04-16</td>
      <td>1.014</td>
      <td>0.950</td>
      <td>5.177</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2026-04-16</td>
      <td>2.028</td>
      <td>0.909</td>
      <td>4.809</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2027-04-16</td>
      <td>3.042</td>
      <td>0.873</td>
      <td>4.560</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2029-04-16</td>
      <td>5.072</td>
      <td>0.808</td>
      <td>4.281</td>
    </tr>
    <tr>
      <th>5</th>
      <td>2031-04-16</td>
      <td>7.100</td>
      <td>0.748</td>
      <td>4.172</td>
    </tr>
    <tr>
      <th>6</th>
      <td>2034-04-17</td>
      <td>10.147</td>
      <td>0.665</td>
      <td>4.108</td>
    </tr>
    <tr>
      <th>7</th>
      <td>2044-04-18</td>
      <td>20.297</td>
      <td>0.447</td>
      <td>4.044</td>
    </tr>
    <tr>
      <th>8</th>
      <td>2054-04-16</td>
      <td>30.436</td>
      <td>0.327</td>
      <td>3.743</td>
    </tr>
  </tbody>
</table>
</div>
<div>
<style scoped>
    .dataframe tbody tr th: only-of-type {
        Vertical-align: middle;
    }

    .dataframe tbody tr th {
        Vertical-align: top;
    }

    .dataframe thead th {
        Text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>YearFrac</th>
      <th>DiscountFactor</th>
      <th>ZeroRate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2024-04-16</td>
      <td>0.000</td>
      <td>1.000</td>
      <td>5.177</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2025-04-16</td>
      <td>1.014</td>
      <td>0.950</td>
      <td>5.177</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2026-04-16</td>
      <td>2.028</td>
      <td>0.909</td>
      <td>4.809</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2027-04-16</td>
      <td>3.042</td>
      <td>0.873</td>
      <td>4.560</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2028-04-16</td>
      <td>4.058</td>
      <td>0.839</td>
      <td>4.420</td>
    </tr>
    <tr>
      <th>5</th>
      <td>2029-04-16</td>
      <td>5.072</td>
      <td>0.808</td>
      <td>4.281</td>
    </tr>
    <tr>
      <th>6</th>
      <td>2030-04-16</td>
      <td>6.086</td>
      <td>0.777</td>
      <td>4.227</td>
    </tr>
    <tr>
      <th>7</th>
      <td>2031-04-16</td>
      <td>7.100</td>
      <td>0.748</td>
      <td>4.172</td>
    </tr>
    <tr>
      <th>8</th>
      <td>2032-04-16</td>
      <td>8.117</td>
      <td>0.719</td>
      <td>4.151</td>
    </tr>
    <tr>
      <th>9</th>
      <td>2033-04-16</td>
      <td>9.131</td>
      <td>0.691</td>
      <td>4.129</td>
    </tr>
    <tr>
      <th>10</th>
      <td>2034-04-16</td>
      <td>10.144</td>
      <td>0.665</td>
      <td>4.108</td>
    </tr>
    <tr>
      <th>11</th>
      <td>2035-04-16</td>
      <td>11.158</td>
      <td>0.639</td>
      <td>4.101</td>
    </tr>
    <tr>
      <th>12</th>
      <td>2036-04-16</td>
      <td>12.175</td>
      <td>0.613</td>
      <td>4.095</td>
    </tr>
    <tr>
      <th>13</th>
      <td>2037-04-16</td>
      <td>13.189</td>
      <td>0.589</td>
      <td>4.088</td>
    </tr>
    <tr>
      <th>14</th>
      <td>2038-04-16</td>
      <td>14.203</td>
      <td>0.567</td>
      <td>4.082</td>
    </tr>
    <tr>
      <th>15</th>
      <td>2039-04-16</td>
      <td>15.217</td>
      <td>0.544</td>
      <td>4.076</td>
    </tr>
    <tr>
      <th>16</th>
      <td>2040-04-16</td>
      <td>16.233</td>
      <td>0.523</td>
      <td>4.069</td>
    </tr>
    <tr>
      <th>17</th>
      <td>2041-04-16</td>
      <td>17.247</td>
      <td>0.503</td>
      <td>4.063</td>
    </tr>
    <tr>
      <th>18</th>
      <td>2042-04-16</td>
      <td>18.261</td>
      <td>0.484</td>
      <td>4.057</td>
    </tr>
    <tr>
      <th>19</th>
      <td>2043-04-16</td>
      <td>19.275</td>
      <td>0.465</td>
      <td>4.050</td>
    </tr>
    <tr>
      <th>20</th>
      <td>2044-04-16</td>
      <td>20.292</td>
      <td>0.447</td>
      <td>4.044</td>
    </tr>
    <tr>
      <th>21</th>
      <td>2045-04-16</td>
      <td>21.306</td>
      <td>0.432</td>
      <td>4.014</td>
    </tr>
    <tr>
      <th>22</th>
      <td>2046-04-16</td>
      <td>22.319</td>
      <td>0.418</td>
      <td>3.984</td>
    </tr>
    <tr>
      <th>23</th>
      <td>2047-04-16</td>
      <td>23.333</td>
      <td>0.405</td>
      <td>3.954</td>
    </tr>
    <tr>
      <th>24</th>
      <td>2048-04-16</td>
      <td>24.350</td>
      <td>0.392</td>
      <td>3.923</td>
    </tr>
    <tr>
      <th>25</th>
      <td>2049-04-16</td>
      <td>25.364</td>
      <td>0.380</td>
      <td>3.893</td>
    </tr>
    <tr>
      <th>26</th>
      <td>2050-04-16</td>
      <td>26.378</td>
      <td>0.368</td>
      <td>3.863</td>
    </tr>
    <tr>
      <th>27</th>
      <td>2051-04-16</td>
      <td>27.392</td>
      <td>0.357</td>
      <td>3.833</td>
    </tr>
    <tr>
      <th>28</th>
      <td>2052-04-16</td>
      <td>28.408</td>
      <td>0.346</td>
      <td>3.803</td>
    </tr>
    <tr>
      <th>29</th>
      <td>2053-04-16</td>
      <td>29.422</td>
      <td>0.336</td>
      <td>3.773</td>
    </tr>
  </tbody>
</table>
</div>
## d. Plot the calibrated US SOFR Zero Interest Rates and Discount Factor curves

Plot the SOFR zero rates and discount factor curves by maturity. Follow section 1 c in the QuantLib Advanced notebook.
```python
# Plot the SOFR yield curve
Plt = sofr_yield_curve_details_df.Plot (x='Date',           y='ZeroRate',           grid=True,           style='*-',           title=f'SOFR Curve: Zero Rates as of {calc_date. To_date ()}',           figsize=(12,          4))
Plt. Set_ylabel ('Zero Rate (%)')
Plt. Set_xlabel ('Date')

Plt = sofr_yield_curve_details_df.Plot (x='Date',           y='DiscountFactor',           grid=True,           style='*-',           title=f'SOFR Curve: Discount Factors as of {calc_date. To_date ()}',           figsize=(12,          4))
Plt. Set_ylabel ('Discount Factors')
Plt. Set_xlabel ('Date')
```
    Text (0.5,           0,           'Date')
![png](CreditMarketSolutions_223_1.png)
![png](CreditMarketSolutions_223_2.png)
-----------------------------------------------------------
# Problem 4: CDS Hazard Rate calibration and valuation
## Follow Section "2. CDS Hazard Rate calibration + Pricing" in the QuantLib Advanced notebook !!!

## a. Load and explore the CDS market data (IBM credit issuer)

Load the `cds_market_data_eod` Excel file into a dataframe. 

Plot the historical time series of CDS Par Spreads for the available tenors.
```python
# Cds_market_quotes
Cds_market_quotes = pd. Read_excel ('./data/cds_market_data_eod. Xlsx')
Print (cds_market_quotes.Head ())

# Create par spreads (bps) dataframe
Par_spread_col_names = [f'par_spread_{n}y' for n in [1,          2,          3,          5,          7,          10]]
Cds_par_spreads_df = cds_market_quotes. Set_index ('date')[par_spread_col_names]

Plt = cds_par_spreads_df.Plot (grid=True,           style='-',           title='IBM CDS Par Spreads ',           figsize=(12,          8))
Plt. Set_ylabel ('IBM CDS Par Spreads')
Plt. Set_xlabel ('Date')

```

            Date ticker                short_name    tier      sector  region   
    0 2024-01-02    IBM  Intl Business Machs Corp  SNRFOR  Technology  N.Amer  \
    1 2024-01-03    IBM  Intl Business Machs Corp  SNRFOR  Technology  N.Amer   
    2 2024-01-04    IBM  Intl Business Machs Corp  SNRFOR  Technology  N.Amer   
    3 2024-01-05    IBM  Intl Business Machs Corp  SNRFOR  Technology  N.Amer   
    4 2024-01-08    IBM  Intl Business Machs Corp  SNRFOR  Technology  N.Amer   
    
      Currency doc_clause  running_coupon  cds_assumed_recovery  par_spread_1 y   
    0      USD       XR 14            0.01                   0.4        13.6831  \
    1      USD       XR 14            0.01                   0.4        14.2256   
    2      USD       XR 14            0.01                   0.4        13.8318   
    3      USD       XR 14            0.01                   0.4        13.6181   
    4      USD       XR 14            0.01                   0.4        13.4433   
    
       Par_spread_2 y  par_spread_3 y  par_spread_5 y  par_spread_7 y  par_spread_10 y  
    0        18.8194        28.3917        44.7053        62.1494         69.1972  
    1        19.6610        29.4493        46.4866        63.6475         71.4311  
    2        19.1828        28.8454        45.4735        62.6543         70.9180  
    3        18.7703        28.3417        44.7575        61.9778         70.2746  
    4        18.3692        27.7599        43.8548        60.8378         68.8914  
    Text (0.5,           0,           'Date')
![png](png)
## b. Calibrate the IBM hazard rate curve as of 2024-04-15

Follow section 2 a in the QuantLib Advanced notebook. Use the calibrated SOFR discount curve from Problem 3 b.
```python
Def calibrate_cds_hazard_rate_curve (calc_date,           sofr_yield_curve_handle,           cds_par_spreads_bps,           cds_recovery_rate = 0.4):
    '''Calibrate hazard rate curve from CDS Par Spreads'''
    CDS_settle_days = 2

    CDS_day_count = ql. Actual 360 ()

    # CDS standard tenors: 1 Y,           2 Y,           3 Y,           5 Y 7 Y and 10 Y
    CDS_tenors = [ql.Period (y,           ql. Years) for y in [1,           2,           3,           5,           7,           10]]
    CDS_helpers = [ql.SpreadCdsHelper ((cds_par_spread / 10000.0),           CDS_tenor,           CDS_settle_days,           ql.TARGET (),          
                                  Ql. Quarterly,           ql. Following,           ql. DateGeneration. TwentiethIMM,           CDS_day_count,           cds_recovery_rate,           sofr_yield_curve_handle)
               
    For (cds_par_spread,           CDS_tenor) in zip (cds_par_spreads_bps,           CDS_tenors)]

    # bootstrap hazard_rate_curve
    Hazard_rate_curve = ql.PiecewiseFlatHazardRate (calc_date,           CDS_helpers,           CDS_day_count)
    Hazard_rate_curve.EnableExtrapolation ()

    Return (hazard_rate_curve)
Def get_hazard_rates_df (hazard_rate_curve):
    '''Return dataframe with calibrated hazard rates and survival probabilities'''
    
    CDS_day_count = ql. Actual 360 ()
    
    Hazard_list = [(hr[0]. To_date (),           
                CDS_day_count.YearFraction (calc_date,           hr[0]),          
                Hr[1] * 1 e 4,          
                Hazard_rate_curve.SurvivalProbability (hr[0])) for hr in hazard_rate_curve.Nodes ()]

    Grid_dates,           year_frac,           hazard_rates,           surv_probs = zip (*hazard_list)

    Hazard_rates_df = pd.DataFrame (data={'Date': grid_dates,           
                                     'YearFrac': year_frac,          
                                     'HazardRateBps': hazard_rates,                                               
                                     'SurvivalProb': surv_probs})
    Return (hazard_rates_df)

```
```python
# CDS spreads for IBM as of calc_date = 2024-04-15
Cds_par_spreads = list (cds_par_spreads_df. Loc['2024-04-15'])
Print (cds_par_spreads)

# Cds_recovery_rate
Cds_recovery_rate = 0.4

# Hazard_rate_curve
Hazard_rate_curve = calibrate_cds_hazard_rate_curve (calc_date,           sofr_yield_curve_handle,           cds_par_spreads,           cds_recovery_rate)

# Hazard_rates_df
Hazard_rates_df = get_hazard_rates_df (hazard_rate_curve)

Print (hazard_rates_df)

```

    [11.7219,           16.1196,           23.6826,           37.2246,           52.551,           63.7804]
             Date   YearFrac  HazardRateBps  SurvivalProb
    0  2024-04-12   0.000000      19.372676      1.000000
    1  2025-06-20   1.205556      19.372676      0.997667
    2  2026-06-22   2.225000      35.805389      0.994032
    3  2027-06-21   3.236111      68.966639      0.987125
    4  2029-06-20   5.263889     102.209360      0.966876
    5  2031-06-20   7.291667     166.229764      0.934828
    6  2034-06-20  10.336111     164.376354      0.889198
## c. Plot the calibrated Hazard Rates and Survival Probability curves
Follow section 2 b in the QuantLib Advanced notebook. Use the calibrated SOFR discount curve from Problem 3 b.
```python
Plt = hazard_rates_df.Plot (x='Date',           y='HazardRateBps',           grid=True,           style='*-',           title=f'IBM Hazard Rates Curve as of {calc_date. To_date ()}',           figsize=(12,          4))
Plt. Set_ylabel ('Hazard Rate (bps)')
Plt. Set_xlabel ('Date')

Plt = hazard_rates_df.Plot (x='Date',           y='SurvivalProb',           grid=True,           style='*-',           title=f'IBM Survival Probability Curve as of {calc_date. To_date ()}',           figsize=(12,          4))
Plt. Set_ylabel ('Survival Probability')
Plt. Set_xlabel ('Date')

```
    Text (0.5,           0,           'Date')
![png](air/par spread and PV of a CDS 

Follow section 2 c in the QuantLib Advanced notebook. Construct a CDS object with 100 bps coupon and 2029-06-20 maturity. Compute the fair/par spread and PV.
```python
# CDS specs
Side = ql. Protection. Seller

Face_notional = 100

Contractual_spread = 100 / 10000

Cds_start_date = calc_date
Cds_maturity_date = ql.Date (20,           6,           2029)

# Create CDS schedule
Cds_schedule = ql.MakeSchedule (cds_start_date,           cds_maturity_date,           ql.Period ('3 M'),          
                            Ql. Quarterly,           ql.TARGET (),           ql. Following,           ql. Unadjusted,           ql. DateGeneration. TwentiethIMM)

# Create CDS object
Cds_obj = ql.CreditDefaultSwap (side,           face_notional,           contractual_spread,           cds_schedule,           ql. Following,           ql. Actual 360 ())

# Create CDS pricing engine
Default_prob_curve_handle = ql.DefaultProbabilityTermStructureHandle (hazard_rate_curve)
Cds_engine = ql.MidPointCdsEngine (default_prob_curve_handle,           cds_recovery_rate,           sofr_yield_curve_handle)
Cds_obj.SetPricingEngine (cds_engine)
# Print CDS valuation results
Print ('CDS protection start date: ',           cds_obj.ProtectionStartDate ())
Print ('CDS fair/par spread: ',           round (cds_obj.FairSpread ()*10000,           3))
Print ('CDS PV: ',           round (cds_obj.NPV (),           4))    
Print ('CDS Premium Leg PV: ',           round (cds_obj.CouponLegNPV (),           4))
Print ('CDS Default Leg PV',           round (cds_obj.DefaultLegNPV (),           4))
Print ('Survival Prob. To Maturity: ',           round (hazard_rate_curve.SurvivalProbability (cds_maturity_date),           4))

```

    CDS protection start date: April 12 th,           2024
    CDS fair/par spread: 37.172
    CDS PV: 2.9014
    CDS Premium Leg PV: 4.6179
    CDS Default Leg PV -1.7166
    Survival Prob. To Maturity: 0.9669# Untitled
