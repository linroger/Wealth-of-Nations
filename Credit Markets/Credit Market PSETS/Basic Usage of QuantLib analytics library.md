---
title: Basic Usage of QuantLib analytics library
tags:
  - analytics
  - bond_pricing
  - cashflow_schedule
  - quantlib
  - yield_curve
aliases:
  - QuantLib example
  - QuantLib tutorial
  - QuantLib usage
key_concepts:
  - Bond pricing
  - Cashflow schedule
  - QuantLib library
  - Quote object
  - Yield curve
---

# Basic Usage of QuantLib analytics library
## More details at: https://quantlib-python-docs.readthedocs.io/en/latest/

- 1\. Objects and Handles
  - a. Define a quote object and inspect the value
  - b. Define quoteHandle as a handle/smart pointer to the quote object
  - c. Calendars and day-count conventions
- 2\. Cashflow Schedules
  - a. Construct semi-annual cashflow schedule object,  for fixed-rate bonds
  - b. Inspect the semi-annual cashflow schedule
  - c. Construct quarterly cashflow schedule object,  for floating-rate bonds
  - d. Inspect the quarterly cashflow schedule
- 3\. Discount Curve / Yield Curve Term Structure
  - a. Constructing a Flat Yield Curve
  - b. Inspect the discount curve
- 4\. Fixed and Floating Rate Bonds
  - a. Constructing a fixed rate bond object
  - b. Investigate the fixed-rate bond cash-flows
  - c. Constructing a floating rate bond object: linked to SOFR index
- 5\. Bond Present Value Calculation (no credit risk)
  - a. Direct function call using risk-free bond pricing engine
  - b. Manual Calculation to validate PV (for fixed and floating-rate bonds)
  - c. Bond Clean vs Dirty Prices (adjusted to settle date)
- 6\. Market Data Scenarios
  - a. Apply +/-1 bp parallel shift scenarios in interest rates curve and compute scenario prices
  - b. Compute scenario DV 01,  duration and convexity
  - c. Yield to Price conversions
  - d. Price to Yield conversions
- 7\. Analytical Duration,  Convexity and Z-Spread (flat yield model)
  - a. Compute bond duration,  convexity and Z-Spread
  - b. Validate Z-Spread
- 8\. Treasury Yield Curve Calibration (via Bootstrapping)
  - a. Calibrate treasury flat yield curve (simple case of one calibration instrument)
  - b. Display the calibrated Treasury discount curve dataframe
  - c. Plot the calibrated Treasury Zero Rates and Discount Factors curves
  - d. Reprice the bond on the yield curve to validate the calibration

```python
Import QuantLib as ql
Import numpy as np
Import pandas as pd
```

# 1. Objects and Handles
## a. Define a quote object and inspect the value

```python
Quote = ql.SimpleQuote (. 01)
Print (quote.Value ())

Quote.SetValue (. 02)
Print (quote.Value ())
```

    0.01
    0.02

## b. Define quoteHandle as a handle/smart pointer to the quote object

```python
QuoteHandle = ql.QuoteHandle (quote)
QuoteHandle.Value ()
```

    0.02

### When the quote object is changed,  the quoteHandle changes value as well

```python
Quote.SetValue (. 03)
QuoteHandle.Value ()
```

    0.03

## c. Calendars and day-count conventions

```python
# Dates
Todays_date = ql.Date.TodaysDate ()
Test_date = todays_date + 90
Print ('todays_date =',         todays_date)
Print ('test_date =',         test_date)
# Calendars
Calendar = ql.UnitedStates (ql. UnitedStates. GovernmentBond)
Holiday_list = list (calendar.HolidayList (todays_date,         test_date))
Print ('holiday_list =',         holiday_list)
# Day count conventions
Day_count = ql. Actual 360 ()
Print ('day_count =',         day_count)

# Year fractions
Test_year_fraction = day_count.YearFraction (todays_date,         test_date)
Print ('Year Fraction  from',         todays_date,         'to',         test_date,        '] =',         test_year_fraction)
```

    Todays_date = May 4 th,         2024
    Test_date = August 2 nd,         2024
    Holiday_list = [Date (27,        5,        2024),         Date (19,        6,        2024),         Date (4,        7,        2024)]
    Day_count = Actual/360 day counter
    Year Fraction  from May 4 th,         2024 to August 2 nd,         2024 ] = 0.25

# 2. Cashflow Schedules
## a. Construct semi-annual cashflow schedule object,  for fixed-rate bonds

```python
Issue_date = ql.Date (2,         4,         2024)        # 2024-04-02
Maturity_date = ql.Date (2,         4,         2028)     # 2028-04-02
Coupon_freq = ql. Semiannual
Coupon_term = ql.Period (coupon_freq)
Calendar = ql.UnitedStates (ql. UnitedStates. GovernmentBond)
Day_count_conv = ql. Unadjusted
Date_generation = ql. DateGeneration. Backward
Month_end = True

# Fixed_rate_schedule
Fixed_rate_schedule = ql.Schedule (issue_date,        
                       Maturity_date,        
                       Coupon_term,        
                       Calendar,        
                       Day_count_conv,        
                       Day_count_conv,        
                       Date_generation,        
                       Month_end)
```

## b. Inspect the semi-annual cashflow schedule
- Use list () to get a list of all the dates in Schedule,  and len () to get number of dates
- Use ] for random access
- Use startDate (),  endDate ()

```python
Print ("All dates: ",         list (fixed_rate_schedule))
Print ("Length: ",         len (fixed_rate_schedule))
Print ("The 3 rd coupon date: ",         [fixed_rate_schedule])  # random access
Print ("Start Date: ",         fixed_rate_schedule.StartDate ())
Print ("End Date: ",         fixed_rate_schedule.EndDate ())
```

    All dates:  [Date (2,        4,        2024),         Date (2,        10,        2024),         Date (2,        4,        2025),         Date (2,        10,        2025),         Date (2,        4,        2026),         Date (2,        10,        2026),         Date (2,        4,        2027),         Date (2,        10,        2027),         Date (2,        4,        2028)]
    Length:  9
    The 3 rd coupon date:  [<QuantLib.QuantLib.Schedule; proxy of <Swig Object of type 'Schedule *' at 0x17891c9c0> >]
    Start Date:  April 2 nd,         2024
    End Date:  April 2 nd,         2028

## c. Construct quarterly cashflow schedule object,  for floating-rate bonds

```python
# Floating_rate_bond_schedule
Floating_rate_schedule = ql.Schedule (
    Issue_date,        
    Maturity_date,        
    Ql.Period (ql. Quarterly),        
    Calendar,        
    Day_count_conv,        
    Day_count_conv,        
    Date_generation,        
    Month_end,        
)
```

## d. Inspect the quarterly cashflow schedule

```python
Print ("All dates: ",         list (floating_rate_schedule))
Print ("Length: ",         len (floating_rate_schedule))
Print ("Start Date: ",         fixed_rate_schedule.StartDate ())
Print ("End Date: ",         fixed_rate_schedule.EndDate ())
```

	All dates:  [Date (2,        4,        2024),        
			     Date (2,        7,        2024),        
			      Date (2,        10,        2024),         
			      Date (2,        1,        2025),         
			      Date (2,        4,        2025),        
			       Date (2,        7,        2025),         
			       Date (2,        10,        2025),         
			       Date (2,        1,        2026),         
			       Date (2,        4,        2026),         
			       Date (2,        7,        2026),         
			       Date (2,        10,        2026),         
			       Date (2,        1,        2027),         
			       Date (2,        4,        2027),         
			       Date (2,        7,        2027),         
			       Date (2,        10,        2027),         
			       Date (2,        1,        2028),         
			       Date (2,        4,        2028)]
    Length:  17
    Start Date:  April 2 nd,         2024
    End Date:  April 2 nd,         2028

# 3. Discount Curve / Yield Curve Term Structure
## a. Constructing a Flat Yield Curve

```python
# Set the static valuation date: 2024-04-02
Calc_date = ql.Date (2,         4,         2024)
Ql.Settings.Instance (). EvaluationDate = calc_date

# Using 5% flat interest rate for testing
Flat_rate = ql.SimpleQuote (0.05)
Rate_handle = ql.QuoteHandle (flat_rate)
Day_count = ql. Actual 360 ()
Calendar = ql.UnitedStates (ql. UnitedStates. GovernmentBond)
Continuous_comp = ql. Continuous # continously compounded rate of 5%
Flat_yield_curve = ql.FlatForward (calc_date,         rate_handle,         day_count,         continuous_comp)
Flat_yield_curve_handle = ql.YieldTermStructureHandle (flat_yield_curve)
```

## b. Inspect the discount curve

```python
Ref_date = flat_yield_curve.ReferenceDate ()
Test_date = ql.Date (30,         6,         2025)

# Calc year fraction between ref_date and test_date
YearFrac = flat_yield_curve.DayCounter (). YearFraction (ref_date,         test_date)

Print ("Reference Date =",         ref_date)
Print ("Test Date =",         test_date)
Print ("Year Fraction between Reference Date and Test Date : ",         yearFrac)
Print ("Discount Factor for Test Date",         test_date,         ": ",         flat_yield_curve.Discount (test_date))
Print ("custom DF calculation for Test Date",         test_date,         ": ",         np.Exp (-flat_rate.Value () * yearFrac))
Print ("Difference in Discount Factor: ",         flat_yield_curve.Discount (test_date) - np.Exp (-flat_rate.Value () * yearFrac))
```

    Reference Date = April 2 nd,         2024
    Test Date = June 30 th,         2025
    Year Fraction between Reference Date and Test Date :  1.261111111111111
    Discount Factor for Test Date June 30 th,         2025 :  0.9388913116117773
    Custom DF calculation for Test Date June 30 th,         2025 :  0.9388913116117772
    Difference in Discount Factor: 1.1102230246251565 e-16

# 4. Fixed and Floating Rate Bonds
## a. Constructing a fixed rate bond object

```python
# Day_count: ACT/ACT for Govt bonds
Day_count_govt = ql.ActualActual (ql. ActualActual. ISMA)

# Day_count: 30/360 for fixed-rate Corp bonds
Day_count_corp_fixed = ql. Thirty 360 (ql. Thirty 360. USA)

# Day_count: ACT/360 for floating-rate bonds
Day_count_floater = ql. Actual 360 ()
# Settlement_days: 1 for Govt bonds
Settlement_days_govt = 1

# Settlement_days: 2 for Corp Bonds
Settlement_days_corp = 2

# Govt Bonds specs
Day_count = day_count_govt
Settlement_days = settlement_days_govt

# Coupons
Coupon_rate = 0.04
Coupons = [coupon_rate]

# Payment_convention
Payment_convention = ql. Unadjusted

# Face_value
Face_value = 100
# Construct the fixed_rate_bond
Face_value = 100
Fixed_rate_bond = ql.FixedRateBond (
    Settlement_days,        
    Face_value,        
    Fixed_rate_schedule,        
    Coupons,        
    Day_count,        
    Payment_convention)
```

## b. Investigate the fixed-rate bond cash-flows

```python
X = [(cf.Date (),         cf.Amount ()) for cf in fixed_rate_bond.Cashflows ()]
Cf_date_fixed,         cf_amount = zip (*x)
Cf_frame_fixed = pd.DataFrame (data={'CashFlowDate': cf_date_fixed,         'CashFlowAmount': cf_amount})
Display (cf_frame_fixed)
```

            CashFlowDate  CashFlowAmount
    0  October 2 nd,         2024             2.0
    1    April 2 nd,         2025             2.0
    2  October 2 nd,         2025             2.0
    3    April 2 nd,         2026             2.0
    4  October 2 nd,         2026             2.0
    5    April 2 nd,         2027             2.0
    6  October 2 nd,         2027             2.0
    7    April 2 nd,         2028             2.0
    8    April 2 nd,         2028           100.0

## c. Constructing a floating rate bond object: linked to SOFR index

```python
# Sofr_term_structure_handle: using 5% flat interest rate for testing
Rate_handle = ql.QuoteHandle (ql.SimpleQuote (5/100))
Sofr_term_structure = ql.FlatForward (calc_date,         rate_handle,         day_count_floater,         ql. Continuous)
Sofr_term_structure_handle = ql.YieldTermStructureHandle (sofr_term_structure)

# Set SOFR index history
Im = ql.IndexManager.Instance ()
Sofr_index = ql.Sofr (sofr_term_structure_handle)

# Set SOFR fixings
Im.ClearHistory (sofr_index.Name ())
Sofr_index.AddFixing (ql.Date (28,         ql. March,         2024),         5/100)
Sofr_index.AddFixing (ql.Date (1,         ql. April,         2024),         5/100)
# Floating_rate_bond
Floating_rate_bond = ql.FloatingRateBond (settlement_days,        
                                Face_value,        
                                Floating_rate_schedule,        
                                Sofr_index,        
                                Day_count_floater,        
                                Payment_convention,        
                                Spreads=[25/10000],         # 25 bps floating rate
                                IssueDate=issue_date)

```

```python
X = [(cf.Date (),         cf.Amount ()) for cf in floating_rate_bond.Cashflows ()]
Cf_date_float,         cf_amount = zip (*x)
Cf_frame_float = pd.DataFrame (data={'CashFlowDate': cf_date_float,         'CashFlowAmount': cf_amount})
Print (cf_frame_float)
```

             CashFlowDate  CashFlowAmount
    0      July 2 nd,         2024        1.335104
    1   October 2 nd,         2024        1.349865
    2   January 2 nd,         2025        1.349865
    3     April 2 nd,         2025        1.320345
    4      July 2 nd,         2025        1.335104
    5   October 2 nd,         2025        1.349865
    6   January 2 nd,         2026        1.349865
    7     April 2 nd,         2026        1.320345
    8      July 2 nd,         2026        1.335104
    9   October 2 nd,         2026        1.349865
    10  January 2 nd,         2027        1.350044
    11    April 2 nd,         2027        1.320520
    12     July 2 nd,         2027        1.335104
    13  October 2 nd,         2027        1.350044
    14  January 2 nd,         2028        1.350044
    15    April 2 nd,         2028        1.335370
    16    April 2 nd,         2028      100.000000

# 5. Bond Present Value Calculation (no credit risk)
## a. Direct function call using risk-free bond pricing engine

```python
# Fixed_rate_bond PV
Bond_engine = ql.DiscountingBondEngine (flat_yield_curve_handle)
Fixed_rate_bond.SetPricingEngine (bond_engine)
Fixed_rate_bond_pv = fixed_rate_bond.NPV ()
Print ('fixed_rate_bond_pv =',         fixed_rate_bond_pv)

# Floating_rate_bond PV
Floating_rate_bond.SetPricingEngine (bond_engine)
Floating_rate_bond_pv = floating_rate_bond.NPV ()
Print ('floating_rate_bond_pv =',         floating_rate_bond_pv)
```

    Fixed_rate_bond_pv = 95.93321956659715
    Floating_rate_bond_pv = 100.91327849916414

## b. Manual Calculation to validate PV (for fixed and floating-rate bonds)

```python
# Validate fixed-rate bond PV
Used_cf_frame = cf_frame_fixed
Used_bond_pv = fixed_rate_bond_pv

# Validate floating-rate bond PV
Discount_yearfrac = np.Zeros ((len (used_cf_frame,        )))
Discount_factor = np.Zeros ((len (used_cf_frame,        )))

I = 0
For cf_date in used_cf_frame['CashFlowDate']:
    Discount_yearfrac[i] = flat_yield_curve.DayCounter (). YearFraction (flat_yield_curve.ReferenceDate (),         cf_date)
    Discount_factor[i] = flat_yield_curve.Discount (cf_date)
    I += 1

Used_cf_frame['YearFrac'] = discount_yearfrac
Used_cf_frame['DiscountFactor'] = discount_factor
Used_cf_frame['NPV'] = used_cf_frame['CashFlowAmount'] * used_cf_frame['DiscountFactor']

Used_cf_frame
```

<div>
<style scoped>
	. Dataframe tbody tr th: only-of-type {
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
	  <th>CashFlowDate</th>
	  <th>CashFlowAmount</th>
	  <th>YearFrac</th>
	  <th>DiscountFactor</th>
	  <th>NPV</th>
	</tr>
  </thead>
  <tbody>
	<tr>
	  <th>0</th>
	  <td>October 2 nd,  2024</td>
	  <td>2.0</td>
	  <td>0.508333</td>
	  <td>0.974904</td>
	  <td>1.949807</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>April 2 nd,  2025</td>
	  <td>2.0</td>
	  <td>1.013889</td>
	  <td>0.950569</td>
	  <td>1.901138</td>
	</tr>
	<tr>
	  <th>2</th>
	  <td>October 2 nd,  2025</td>
	  <td>2.0</td>
	  <td>1.522222</td>
	  <td>0.926713</td>
	  <td>1.853426</td>
	</tr>
	<tr>
	  <th>3</th>
	  <td>April 2 nd,  2026</td>
	  <td>2.0</td>
	  <td>2.027778</td>
	  <td>0.903582</td>
	  <td>1.807163</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>October 2 nd,  2026</td>
	  <td>2.0</td>
	  <td>2.536111</td>
	  <td>0.880905</td>
	  <td>1.761810</td>
	</tr>
	<tr>
	  <th>5</th>
	  <td>April 2 nd,  2027</td>
	  <td>2.0</td>
	  <td>3.041667</td>
	  <td>0.858917</td>
	  <td>1.717833</td>
	</tr>
	<tr>
	  <th>6</th>
	  <td>October 2 nd,  2027</td>
	  <td>2.0</td>
	  <td>3.550000</td>
	  <td>0.837361</td>
	  <td>1.674722</td>
	</tr>
	<tr>
	  <th>7</th>
	  <td>April 2 nd,  2028</td>
	  <td>2.0</td>
	  <td>4.058333</td>
	  <td>0.816346</td>
	  <td>1.632693</td>
	</tr>
	<tr>
	  <th>8</th>
	  <td>April 2 nd,  2028</td>
	  <td>100.0</td>
	  <td>4.058333</td>
	  <td>0.816346</td>
	  <td>81.634627</td>
	</tr>
  </tbody>
</table>
</div>

```python
Pv_manual = used_cf_frame['NPV']. Sum ()
Print ('NPV engine = ',         used_bond_pv)
Print ('NPV manual = ',         pv_manual)
Print ('NPV diff = ',         pv_manual - used_bond_pv)
```

    NPV engine =  95.93321956659715
    NPV manual =  95.93321956659715
    NPV diff =  0.0

## c. Bond Clean vs Dirty Prices (adjusted to settle date)

```python
Print ('Bond Notional = ',         fixed_rate_bond.Notional ())
Print ('Settle Date = ',         fixed_rate_bond.SettlementDate ())
Print ('Discount Factor to Settle Date = ',         round (flat_yield_curve_handle.Discount (fixed_rate_bond.SettlementDate ()),         4))
Print ('Bond NPV (Calc Date) = ',         round (fixed_rate_bond.NPV (),         4))
Print ('Bond NPV Adjusted to Settle Date = ',         round (fixed_rate_bond.NPV () / flat_yield_curve_handle.Discount (fixed_rate_bond.SettlementDate ()),         4))
Print ('Bond Dirty Price = ',         round (fixed_rate_bond.DirtyPrice (),         4))
Print ('Bond Clean Price = ',         round (fixed_rate_bond.CleanPrice (),         4))
Print ('Bond Accrued = ',         round (fixed_rate_bond.AccruedAmount (),         4))

```

    Bond Notional =  100.0
    Settle Date =  April 3 rd,         2024
    Discount Factor to Settle Date =  0.9999
    Bond NPV (Calc Date) =  95.9332
    Bond NPV Adjusted to Settle Date =  95.9465
    Bond Dirty Price =  95.9465
    Bond Clean Price =  95.9356
    Bond Accrued =  0.0109

# 6. Market Data Scenarios
## a. Apply +/-1 bp parallel shift scenarios in interest rates curve and compute scenario prices

```python
# Start with interest_rate_bump = 0
Interest_rate_bump = ql.SimpleQuote (0.0)
Flat_yield_curve_bumped = ql.ZeroSpreadedTermStructure (flat_yield_curve_handle,         ql.QuoteHandle (interest_rate_bump))

Bond_engine = ql.DiscountingBondEngine (ql.YieldTermStructureHandle (flat_yield_curve_bumped))
Fixed_rate_bond.SetPricingEngine (bond_engine)

Price_base = fixed_rate_bond.CleanPrice ()

# Original price (zero interest rate bump)
Print ("Price (base case): ",         round (price_base,         4))

# Bump interest rate by +1 bps (parallel shift)
Interest_rate_bump.SetValue (0.0001)
Price_up_1 bp = fixed_rate_bond.CleanPrice ()
Print ("Price in +1 bps scenario: ",         round (price_up_1 bp,         4))
Print ("Price diff in +1 bps scenario: ",         round (price_up_1 bp - price_base,         6))

# Bump interest rate by -1 bps (parallel shift)
Interest_rate_bump.SetValue (-0.0001)
Price_down_1 bp = fixed_rate_bond.CleanPrice ()
Print ("Price for -1 bps scenario: ",         round (price_down_1 bp,         4))
Print ("Price diff in -1 bps scenario: ",         round (price_down_1 bp - price_base,         6))

 # Remove interest rate bump
Interest_rate_bump.SetValue (0)
```

    Price (base case):  95.9356
    Price in +1 bps scenario:  95.8993
    Price diff in +1 bps scenario:  -0.036268
    Price for -1 bps scenario: 95.9719
    Price diff in -1 bps scenario:  0.036283

## b. Compute scenario DV 01,  duration and convexity

```python
# Compute scenario delta/gamma sensitivities
Dv 01 = round ((price_down_1 bp - price_base) * 1 e 4 / 100,         4)
Duration = round (dv 01 / fixed_rate_bond.DirtyPrice () * 100,         4)
Gamma_1 bp = (price_down_1 bp - 2*price_base + price_up_1 bp) * 1 e 8 / 100
Convexity = round (gamma_1 bp / fixed_rate_bond.DirtyPrice () * 100,         4)

Print ("DV 01: ",         dv 01)
Print ("Duration: ",         duration)
Print ("Convexity: ",         convexity)
```

    DV 01:  3.6283
    Duration:  3.7816
    Convexity:  14.9262

## c. Yield to Price conversions

```python
# Use original interest rate yield of 5%
# Flat_rate.SetValue (0.05)
Print ('Bond PV for',         flat_rate.Value ()*100,         'pct yield: ',         round (fixed_rate_bond.NPV (),         4))
# Change interest rate yield to 6% and recompute bond PV
Flat_rate.SetValue (0.06)
Print ('Bond PV for',         flat_rate.Value ()*100,         'pct yield: ',         round (fixed_rate_bond.NPV (),         4))

# Set interest rate yield back to 5%
Flat_rate.SetValue (0.05)
```

    Bond PV for 5.0 pct yield: 95.9332
    Bond PV for 6.0 pct yield: 92.3743

## d. Price to Yield conversions

```python
# Bond_market_price = fixed_rate_bond.CleanPrice ()
Bond_market_price = 95.00   # Clean market price

Compounding = ql. Compounded
# Compounding = ql. Continuous

Settle_date = fixed_rate_bond.SettlementDate (calc_date)
Day_counter = fixed_rate_bond.DayCounter ()

Print ('day_counter =',         day_counter)
Print ('coupon_freq =',         coupon_freq)
Print ('calc_date =',         calc_date)
Print ('settle_date =',         settle_date)
Implied_yield = fixed_rate_bond.BondYield (bond_market_price,         day_counter,         compounding,         coupon_freq,         settle_date) * 100
Print ('implied_yield =',         round (implied_yield,         4))
```

    Day_counter = Actual/Actual (ISMA) day counter
    Coupon_freq = 2
    Calc_date = April 2 nd,         2024
    Settle_date = April 3 rd,         2024
    Implied_yield = 5.4076

# 7. Analytical Duration,  Convexity and Z-Spread (flat yield model)
## a. Compute bond duration,  convexity and Z-Spread

```python
# Flat_bond_yield (used as an input to compute duration and convexity)
Flat_bond_yield = 5.5 # in pct
Flat_bond_yield_rate = ql.InterestRate (flat_bond_yield/100,         day_count,         compounding,         coupon_freq)

# Calc Duration and Convexity
Bond_duration = ql.BondFunctions.Duration (fixed_rate_bond,         flat_bond_yield_rate)
Bond_convexity = ql.BondFunctions.Convexity (fixed_rate_bond,         flat_bond_yield_rate)

# Calc z-spread for a given market price
Bond_market_price = 95.3194     # Clean market price,         implies zero Z-Spread!
Bond_market_price = 95          # Test market price,         implies Z-Spread > 0
Bond_zspread = ql.BondFunctions.ZSpread (fixed_rate_bond,         bond_market_price,         flat_yield_curve,         day_count,         compounding,         coupon_freq,         settle_date)

# Print results
Print ('Bond Duration =',         round (bond_duration,         4))
Print ('Bond Convexity =',         round (bond_convexity,         4))
Print ('Bond Z-Spread bps =',         round (bond_zspread * 10000,         4))

```

    Bond Duration = 3.6247
    Bond Convexity = 15.4882
    Bond Z-Spread bps = 26.5978

## b. Validate Z-Spread

```python
Def calc_clean_price_with_zspread (fixed_rate_bond,         yield_curve_handle,         zspread):
    Zspread_quote = ql.SimpleQuote (zspread)
    Zspread_quote_handle = ql.QuoteHandle (zspread_quote)
    Yield_curve_bumped = ql.ZeroSpreadedTermStructure (yield_curve_handle,         zspread_quote_handle,         ql. Compounded,         ql. Semiannual)
    Yield_curve_bumped_handle = ql.YieldTermStructureHandle (yield_curve_bumped)
    
    # Set Valuation engine
    Bond_engine = ql.DiscountingBondEngine (yield_curve_bumped_handle)
    Fixed_rate_bond.SetPricingEngine (bond_engine)
    Bond_clean_price = fixed_rate_bond.CleanPrice ()
    Return bond_clean_price

```

```python
# Compare the original and the z-spread computed clean prices
Bond_zspread_price = calc_clean_price_with_zspread (fixed_rate_bond,         flat_yield_curve_handle,         bond_zspread)

Print ('Bond Z-Spread bps =',         round (bond_zspread * 10000,         2))
Print ('bond_market_price =',         bond_market_price)
Print ('bond_zspread_price =',         bond_zspread_price)
Print ('bond price diff =',         bond_zspread_price - bond_market_price)
```

    Bond Z-Spread bps = 26.6
    Bond_market_price = 95
    Bond_zspread_price = 94.99999999999486
    Bond price diff = -5.144329406903125 e-12

# 8. Treasury Yield Curve Calibration (via Bootstrapping)
## a. Calibrate treasury flat yield curve (simple case of one calibration instrument)

```python
# Fixed_rate_bond: 4% coupon and 2028-04-02 maturity

# Clean price quote
Tsy_clean_price_quote = 96.0
Tsy_clean_price_handle = ql.QuoteHandle (ql.SimpleQuote (tsy_clean_price_quote))
# Create BondHelper object
Bond_helper = ql.BondHelper (
    Tsy_clean_price_handle,        
    Fixed_rate_bond)

Bond_helper_list = [bond_helper]
        
Tsy_flat_yield_curve = ql.PiecewiseLogCubicDiscount (calc_date,         bond_helper_list,         day_count)
Tsy_flat_yield_curve.EnableExtrapolation ()

Tsy_yield_curve_handle = ql.YieldTermStructureHandle (tsy_flat_yield_curve)

```

## b. Display the calibrated Treasury discount curve dataframe

```python
Def get_yield_curve_details_df (yield_curve,         curve_dates=None):
    
    If (curve_dates == None):
        Curve_dates = yield_curve.Dates ()

    dates = [d.to_date () for d in curve_dates]
    Discounts = [round (yield_curve.Discount (d),         3) for d in curve_dates]
    Yearfracs = [round (yield_curve.TimeFromReference (d),         3) for d in curve_dates]
    ZeroRates = [round (yield_curve.ZeroRate (d,         yield_curve.DayCounter (),         ql. Compounded). Rate () * 100,         3) for d in curve_dates]

    Yield_curve_details_df = pd.DataFrame (data={'Date': dates,        
                             'YearFrac': yearfracs,        
                             'DiscountFactor': discounts,        
                             'ZeroRate': zeroRates})                             
    Return yield_curve_details_df
```

```python
# Display Treasury yield curve details
Tsy_flat_yield_curve_simple_df = get_yield_curve_details_df (tsy_flat_yield_curve)                  # using calibration grid
Display (tsy_flat_yield_curve_simple_df)

Grid_dates = [tsy_flat_yield_curve.ReferenceDate () + ql.Period (y,         ql. Years) for y in list (range (0,        30,        2))]
Tsy_flat_yield_curve_details_df = get_yield_curve_details_df (tsy_flat_yield_curve,         grid_dates)    # using external grid
Display (tsy_flat_yield_curve_details_df)

```

<div>
<style scoped>
	. Dataframe tbody tr th: only-of-type {
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
	  <td>2023-04-14</td>
	  <td>0.000</td>
	  <td>1.000</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>2030-04-01</td>
	  <td>6.964</td>
	  <td>0.135</td>
	  <td>33.285</td>
	</tr>
  </tbody>
</table>
</div>

<div>
<style scoped>
	. Dataframe tbody tr th: only-of-type {
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
	  <td>2023-04-14</td>
	  <td>0.0</td>
	  <td>1.000</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>1</th>
	  <td>2025-04-14</td>
	  <td>2.0</td>
	  <td>0.563</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>2</th>
	  <td>2027-04-14</td>
	  <td>4.0</td>
	  <td>0.317</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>3</th>
	  <td>2029-04-14</td>
	  <td>6.0</td>
	  <td>0.178</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>4</th>
	  <td>2031-04-14</td>
	  <td>8.0</td>
	  <td>0.100</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>5</th>
	  <td>2033-04-14</td>
	  <td>10.0</td>
	  <td>0.057</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>6</th>
	  <td>2035-04-14</td>
	  <td>12.0</td>
	  <td>0.032</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>7</th>
	  <td>2037-04-14</td>
	  <td>14.0</td>
	  <td>0.018</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>8</th>
	  <td>2039-04-14</td>
	  <td>16.0</td>
	  <td>0.010</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>9</th>
	  <td>2041-04-14</td>
	  <td>18.0</td>
	  <td>0.006</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>10</th>
	  <td>2043-04-14</td>
	  <td>20.0</td>
	  <td>0.003</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>11</th>
	  <td>2045-04-14</td>
	  <td>22.0</td>
	  <td>0.002</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>12</th>
	  <td>2047-04-14</td>
	  <td>24.0</td>
	  <td>0.001</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>13</th>
	  <td>2049-04-14</td>
	  <td>26.0</td>
	  <td>0.001</td>
	  <td>33.285</td>
	</tr>
	<tr>
	  <th>14</th>
	  <td>2051-04-14</td>
	  <td>28.0</td>
	  <td>0.000</td>
	  <td>33.285</td>
	</tr>
  </tbody>
</table>
</div>

## c. Plot the calibrated Treasury Zero Rates and Discount Factors curves

```python
Plt = tsy_flat_yield_curve_details_df.Plot (x='Date',         y='ZeroRate',         grid=True,         style='*-',         title='Treasury Flat Curve: Zero Rates',         figsize=(12,        4))
Plt. Set_ylabel ('Zero Rate (%)')
Plt. Set_xlabel ('Date')

Plt = tsy_flat_yield_curve_details_df.Plot (x='Date',         y='DiscountFactor',         grid=True,         style='*-',         title='Treasury Flat Curve: Discount Factors',         figsize=(12,        4))
Plt. Set_ylabel ('Discount Factors')
Plt. Set_xlabel ('Date')
```

    Text (0.5,         0,         'Date')
![png](CreditMarketSolutions_101_1.png)

![png](CreditMarketSolutions_101_2.png)

## d. Reprice the bond on the yield curve to validate the calibration

```python
# 1. Price risk-free bond
Risk_free_bond_engine = ql.DiscountingBondEngine (tsy_yield_curve_handle)

Fixed_rate_bond.SetPricingEngine (risk_free_bond_engine)
Risk_free_bond_price = fixed_rate_bond.CleanPrice ()
Risk_free_bond_yield = fixed_rate_bond.BondYield (risk_free_bond_price,         day_counter,         compounding,         coupon_freq,         settle_date) * 100

Print ('tsy_clean_price_quote: ',         tsy_clean_price_quote)
Print ('risk_free_bond_price: ',         risk_free_bond_price)
Print ('price_calibration_error: ',         risk_free_bond_price-tsy_clean_price_quote)
Print ('risk_free_bond_yield: ',         risk_free_bond_yield)

```

    Tsy_clean_price_quote: 96.0
    Risk_free_bond_price: 96.0
    Price_calibration_error: 0.0
    Risk_free_bond_yield: 5.119227409362794

