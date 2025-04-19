---
title: Advanced Usage of QuantLib analytics library
tags:
  - bond_pricing
  - cds
  - credit_risk
  - curve_calibration
  - hazard_rate
  - interest_rates
  - nelson_siegel
  - quantlib
  - risk_management
  - sofr
aliases:
  - Credit Default Swaps
  - Nelson-Siegel Model
  - QuantLib Advanced
  - Risky Bond Pricing
  - SOFR Swaps
key_concepts:
  - CDS hazard rate
  - Corporate bond pricing
  - Credit curve
  - Credit default risk
  - Discount curve
  - Hazard rate curves
  - Nelson-Siegel model
  - Risky bond pricing
  - SOFR curve calibration
  - SOFR swaps
  - Survival probability
---

# Advanced Usage of QuantLib analytics library
## More details at: https://quantlib-python-docs.readthedocs.io/en/latest/

- 1\. SOFR Is swap rates and SOFR discount curve calibration
  - a. SOFR curve calibration (via Bootstrapping)
  - b. Display the calibrated SOFR discount curve dataframe
  - c. Plot the calibrated SOFR Zero Rates and Discount Factors curves
  - d. Validate SOFR calibration by pricing SOFR swaps
- 2\. Credit Default Swaps (CDS): calibration + pricing
  - a. CDS Hazard Rate calibration
  - b. Plot the calibrated Hazard Rate and Survival Probability curves
  - c. CDS valuation
- 3\. Pricing risky bonds in the CDS-implied Hazard Rate Model (with Credit Default Risk)
  - a. Create Corporate Bond
  - b. Price Corporate Bond on Risk-Free Yield Curve (without Credit Risk)
  - c. Compute Intrinsic Risky Bond Price on IBM CDS Credit Curve (with Credit Risk)
- 4\. Pricing risky bonds in Custom Hazard Rate Model (with Credit Default Risk)
  - a. Create and Display the Custom Credit Curve
  - b. Price Risky Bond on Custom Credit Curve (with Credit Risk)
- 5\. Smooth parametric yield and hazard rate curves: Nelson-Siegel + extensions
  - a. Nelson Siegel basis functions
  - b. Plot Basis Functions for Nelson-Siegel + extensions
  - c. Constructing smooth Nelson-Siegel hazard rate / survival probability curves
  - d. Pricing risky bonds in Nelson-Siegel model (with Credit Risk)

```python

```

# 1. SOFR Is swap rates and SOFR discount curve calibration

## a. SOFR curve calibration (via Bootstrapping)

Overnight Index Swap contract is an interest rate swap contract exchanging and overnight index interest rate (e.g. Fed Funds,  SOFR,  LIBOR) for a fixed interest rate until the contract maturity. The fixed rate is set at a rate agreed upon by both parties. The floating leg portion of the swap is compounded and paid at reset dates.

```python
# Set the static valuation date: 2023-04-14
Calc_date = ql.Date (14,             4,             2023)
Ql.Settings.Instance (). EvaluationDate = calc_date

# Calendar
Calendar = ql.UnitedStates (ql. UnitedStates. GovernmentBond)

# Settle_days
Settle_days = 2

# SOFR [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]] swap tenors: 1 Y,             2 Y,             3 Y,             5 Y 7 Y,             10 Y,             20 Y and 30 Y
SOFR_tenors = [ql.Period (y,             ql. Years) for y in [1,             2,             3,             5,             7,             10,             20,             30]]
               
# SOFR [[A Guide to the Front End and Basis Swap Markets#Overnight Index Swaps Overview|OIS]] swap rates (as of 2023-04-14)
SOFR_rates = [4.81,             4.11,             3.73,             3.38,             3.32,             3.26,             3.20,             3.02]

SOFR_OIS_swap_helpers = []
For (SOFR_tenor,             SOFR_rate) in zip (SOFR_tenors,             SOFR_rates):
    SOFR_OIS_swap_helpers.Append (ql.OISRateHelper (settle_days,             SOFR_tenor,             ql.QuoteHandle (ql.SimpleQuote (SOFR_rate/100)),             ql.Sofr ()))

# Create SOFR yield curve
Sofr_yield_curve = ql.PiecewiseLinearZero (settle_days,             calendar,             SOFR_OIS_swap_helpers,             ql. Actual 360 ())
Sofr_yield_curve.EnableExtrapolation ()
Sofr_yield_curve_handle = ql.YieldTermStructureHandle (sofr_yield_curve)

Print (sofr_yield_curve.ReferenceDate ())

```

    April 18 th,             2023

## b. Display the calibrated SOFR discount curve dataframe

```python
Def get_yield_curve_details_df (yield_curve,             curve_dates=None):
    
    If (curve_dates == None):
        Curve_dates = yield_curve.Dates ()

    dates = [d.to_date () for d in curve_dates]
    Discounts = [round (yield_curve.Discount (d),             3) for d in curve_dates]
    Yearfracs = [round (yield_curve.TimeFromReference (d),             3) for d in curve_dates]
    ZeroRates = [round (yield_curve.ZeroRate (d,             yield_curve.DayCounter (),             ql. Compounded). Rate () * 100,             3) for d in curve_dates]

    Yield_curve_details_df = pd.DataFrame (data={'Date': dates,            
                             'YearFrac': yearfracs,            
                             'DiscountFactor': discounts,            
                             'ZeroRate': zeroRates})                             
    Return yield_curve_details_df
# Display SOFR yield curve
Grid_dates = [sofr_yield_curve.ReferenceDate () + ql.Period (y,             ql. Years) for y in list (range (0,            30,            2))]
Sofr_yield_curve_simple_df = get_yield_curve_details_df (sofr_yield_curve)                  # using calibration grid
Sofr_yield_curve_details_df = get_yield_curve_details_df (sofr_yield_curve,             grid_dates)    # using external grid

Print (sofr_yield_curve_simple_df)
Print (sofr_yield_curve_details_df)

```

             Date  YearFrac  DiscountFactor  ZeroRate
    0  2023-04-18     0.000           1.000     4.808
    1  2024-04-18     1.017           0.953     4.808
    2  2025-04-21     2.039           0.921     4.094
    3  2026-04-20     3.050           0.895     3.706
    4  2028-04-18     5.075           0.846     3.347
    5  2030-04-18     7.103           0.795     3.291
    6  2033-04-18    10.147           0.724     3.232
    7  2043-04-20    20.297           0.530     3.173
    8  2053-04-18    30.439           0.415     2.931
              Date  YearFrac  DiscountFactor  ZeroRate
    0   2023-04-18     0.000           1.000     4.808
    1   2025-04-18     2.031           0.922     4.100
    2   2027-04-18     4.058           0.869     3.527
    3   2029-04-18     6.089           0.820     3.319
    4   2031-04-18     8.117           0.770     3.272
    5   2033-04-18    10.147           0.724     3.232
    6   2035-04-18    12.175           0.680     3.221
    7   2037-04-18    14.206           0.638     3.209
    8   2039-04-18    16.233           0.600     3.197
    9   2041-04-18    18.264           0.564     3.185
    10  2043-04-18    20.292           0.530     3.173
    11  2045-04-18    22.322           0.503     3.125
    12  2047-04-18    24.350           0.478     3.076
    13  2049-04-18    26.381           0.455     3.028
    14  2051-04-18    28.408           0.434     2.979

## c. Plot the calibrated SOFR Zero Rates and Discount Factors curves

```python
Plt = sofr_yield_curve_details_df.Plot (x='Date',             y='ZeroRate',             grid=True,             style='*-',             title='SOFR Curve: Zero Rates',             figsize=(12,            5))
Plt. Set_ylabel ('Zero Rate (%)')
Plt. Set_xlabel ('Date')

Plt = sofr_yield_curve_details_df.Plot (x='Date',             y='DiscountFactor',             grid=True,             style='*-',             title='SOFR Curve: Discount Factors',             figsize=(12,            5))
Plt. Set_ylabel ('Discount Factors')
Plt. Set_xlabel ('Date')
```

    Text (0.5,             0,             'Date')
![png](CreditMarketSolutions_161_1.png)

![png](CreditMarketSolutions_161_2.png)

## d. Validate SOFR calibration by pricing SOFR swaps

```python
# Validate SOFR swaps
Sofr_index = ql.Sofr (sofr_yield_curve_handle)
# Swap_engine = ql.DiscountingSwapEngine (sofr_yield_curve_handle)

Print ('SOFR Swap valuation: PVs should be close to zero!')

For (SOFR_tenor,             SOFR_rate) in zip (SOFR_tenors,             SOFR_rates):    
    Start_date = calendar.Advance (calc_date,             settle_days,             ql. Days)
    Schedule = ql.MakeSchedule (start_date,             calendar.Advance (start_date,             SOFR_tenor),             ql.Period ('1 Y'),             calendar=calendar)        
    OisSwap = ql.MakeOIS (SOFR_tenor,             sofr_index,             SOFR_rate/100,             nominal=100)
    
    # oisSwap.SetPricingEngine (swap_engine)
    Print ('Swap PV for',             SOFR_tenor,             'tenor /',             SOFR_rate,             'coupon : ',             oisSwap.NPV ()) 
    
```

    SOFR Swap valuation: PVs should be close to zero!
    Swap PV for 1 Y tenor / 4.81 coupon : 0.0
    Swap PV for 2 Y tenor / 4.11 coupon : 2.842170943040401 e-14
    Swap PV for 3 Y tenor / 3.73 coupon : -4.263256414560601 e-14
    Swap PV for 5 Y tenor / 3.38 coupon : -4.033573475226149 e-11
    Swap PV for 7 Y tenor / 3.32 coupon : -2.842170943040401 e-14
    Swap PV for 10 Y tenor / 3.26 coupon : 7.105427357601002 e-15
    Swap PV for 20 Y tenor / 3.2 coupon : -2.1316282072803006 e-14
    Swap PV for 30 Y tenor / 3.02 coupon : -6.394884621840902 e-14

# 2. Credit Default Swaps (CDS): calibration + pricing
## a. CDS Hazard Rate calibration

```python
CDS_recovery_rate = 0.4

CDS_day_count = ql. Actual 360 ()

# CDS standard tenors: 1 Y,             2 Y,             3 Y,             5 Y 7 Y and 10 Y
CDS_tenors = [ql.Period (y,             ql. Years) for y in [1,             2,             3,             5,             7,             10]]
              
# CDS spreads for IBM as of calc_date = 2023-04-14
CDS_spreads = [17.25,             24.09,             35.58,             55.58,             70.51,             79.92]

CDS_helpers = [ql.SpreadCdsHelper ((CDS_spread / 10000.0),             CDS_tenor,             settle_days,             ql.TARGET (),            
                                  Ql. Quarterly,             ql. Following,             ql. DateGeneration. TwentiethIMM,             CDS_day_count,             CDS_recovery_rate,             sofr_yield_curve_handle)
               
For (CDS_spread,             CDS_tenor) in zip (CDS_spreads,             CDS_tenors)]

# Bootstrap hazard_rate_curve
Hazard_rate_curve = ql.PiecewiseFlatHazardRate (calc_date,             CDS_helpers,             CDS_day_count)
Hazard_rate_curve.EnableExtrapolation ()

# Display calibrated hazard rates and survival probabilities
Hazard_list = [(hr[0]. To_date (),             
                CDS_day_count.YearFraction (calc_date,             hr[0]),            
                Hr[1] * 100,            
                Np.Exp (-hr[1]*CDS_day_count.YearFraction (calc_date,             hr[0])),            
                Hazard_rate_curve.SurvivalProbability (hr[0])) for hr in hazard_rate_curve.Nodes ()]

Grid_dates,             year_frac,             hazard_rates,             sp_manual,             surv_probs = zip (*hazard_list)

Hazard_rates_df = pd.DataFrame (data={'Date': grid_dates,             
                                     'YearFrac': year_frac,            
                                     'HazardRate': hazard_rates,            
                                     'SPManual': sp_manual,            
                                     'SurvivalProb': surv_probs})
Print (hazard_rates_df)

```

             Date   YearFrac  HazardRate  SPManual  SurvivalProb
    0  2023-04-14   0.000000    0.285237  1.000000      1.000000
    1  2024-06-20   1.202778    0.285237  0.996575      0.996575
    2  2025-06-20   2.216667    0.540041  0.988100      0.991133
    3  2026-06-22   3.236111    1.033609  0.967104      0.980745
    4  2028-06-20   5.261111    1.511140  0.923575      0.951188
    5  2030-06-20   7.288889    1.925096  0.869082      0.914772
    6  2033-06-20  10.333333    1.803340  0.829987      0.865903

## b. Plot the calibrated Hazard Rate and Survival Probability curves

```python
Plt = hazard_rates_df.Plot (x='Date',             y='HazardRate',             grid=True,             style='*-',             title='IBM Hazard Rates Curve',             figsize=(12,            5))
Plt. Set_ylabel ('Hazard Rate (%)')
Plt. Set_xlabel ('Date')

Plt = hazard_rates_df.Plot (x='Date',             y='SurvivalProb',             grid=True,             style='*-',             title='IBM Survival Probability Curve',             figsize=(12,            5))
Plt. Set_ylabel ('Survival Probability')
Plt. Set_xlabel ('Date')

```

    Text (0.5,             0,             'Date')
![png](CreditMarketSolutions_167_1.png)

![png](CreditMarketSolutions_167_2.png)

## c. CDS valuation

```python
# CDS specs
Side = ql. Protection. Seller

Face_notional = 100

Contractual_spread = 100 / 10000

Cds_start_date = ql.Date (14,             4,             2023)
Cds_maturity_date = ql.Date (20,             6,             2028)

# Create CDS schedule
Cds_schedule = ql.MakeSchedule (cds_start_date,             cds_maturity_date,             ql.Period ('3 M'),            
                            Ql. Quarterly,             ql.TARGET (),             ql. Following,             ql. Unadjusted,             ql. DateGeneration. TwentiethIMM)

# Create CDS object
Cds_obj = ql.CreditDefaultSwap (side,             face_notional,             contractual_spread,             cds_schedule,             ql. Following,             ql. Actual 360 ())

# Create CDS Implied Credit Curve and pricing engine
Cds_surv_prob_curve_handle = ql.DefaultProbabilityTermStructureHandle (hazard_rate_curve)

Cds_pricing_engine = ql.MidPointCdsEngine (cds_surv_prob_curve_handle,             CDS_recovery_rate,             sofr_yield_curve_handle)
Cds_obj.SetPricingEngine (cds_pricing_engine)
# Print CDS valuation results
Print ('CDS protection start date: ',             cds_obj.ProtectionStartDate ())
Print ('CDS fair/par spread: ',             round (cds_obj.FairSpread ()*10000,             3))
Print ('CDS PV: ',             round (cds_obj.NPV (),             4))    
Print ('CDS Premium Leg PV: ',             round (cds_obj.CouponLegNPV (),             4))
Print ('CDS Default Leg PV',             round (cds_obj.DefaultLegNPV (),             4))
Print ('Survival Prob. To Maturity: ',             round (hazard_rate_curve.SurvivalProbability (cds_maturity_date),             4))

```

    CDS protection start date: April 14 th,             2023
    CDS fair/par spread: 55.502
    CDS PV: 2.0855
    CDS Premium Leg PV: 4.6868
    CDS Default Leg PV -2.6013
    Survival Prob. To Maturity: 0.9512

# 3. Pricing risky bonds in the CDS-implied Hazard Rate Model (with Credit Default Risk)
## a. Create Corporate Bond

```python
Issue_date = ql.Date (14,             4,             2023)
Maturity_date = ql.Date (14,             4,             2027)
Coupon_freq = ql. Semiannual
Coupon_term = ql.Period (coupon_freq)
Calendar = ql.UnitedStates (ql. UnitedStates. GovernmentBond)
Day_count_conv = ql. Unadjusted
Date_generation = ql. DateGeneration. Backward
Month_end = True
Schedule = ql.Schedule (issue_date,            
                       Maturity_date,            
                       Coupon_term,            
                       Calendar,            
                       Day_count_conv,            
                       Day_count_conv,            
                       Date_generation,            
                       Month_end)

# Corp Bonds specs
Day_count = ql. Thirty 360 (ql. Thirty 360. USA)
Settlement_days = 2
Coupon_rate = 0.04
Coupons = [coupon_rate]
Payment_convention = ql. Unadjusted

# Construct the FixedRateBond
Face_value = 100
Fixed_rate_bond = ql.FixedRateBond (
    Settlement_days,            
    Face_value,            
    Schedule,            
    Coupons,            
    Day_count,            
    Payment_convention)

X = [(cf.Date (),             cf.Amount ()) for cf in fixed_rate_bond.Cashflows ()]
Cf_date,             cf_amount = zip (*x)
Cf_frame = pd.DataFrame (data={'CashFlowDate': cf_date,             'CashFlowAmount': cf_amount})
Print (cf_frame)

```

             CashFlowDate  CashFlowAmount
    0  October 14 th,             2023             2.0
    1    April 14 th,             2024             2.0
    2  October 14 th,             2024             2.0
    3    April 14 th,             2025             2.0
    4  October 14 th,             2025             2.0
    5    April 14 th,             2026             2.0
    6  October 14 th,             2026             2.0
    7    April 14 th,             2027             2.0
    8    April 14 th,             2027           100.0

## b. Price Corporate Bond on Risk-Free Yield Curve (without Credit Risk)

```python
Compounding = ql. Compounded
# Compounding = ql. Continuous

Day_counter = fixed_rate_bond.DayCounter ()

Risk_free_bond_engine = ql.DiscountingBondEngine (sofr_yield_curve_handle)

Fixed_rate_bond.SetPricingEngine (risk_free_bond_engine)
Risk_free_bond_price = fixed_rate_bond.CleanPrice ()
Risk_free_bond_yield = fixed_rate_bond.BondYield (risk_free_bond_price,             day_counter,             ql. Compounded,             ql. Semiannual) * 100

Print ('risk_free_bond_price: ',             risk_free_bond_price)
Print ('risk_free_bond_yield: ',             risk_free_bond_yield)

```

    Risk_free_bond_price: 101.54536292727957
    Risk_free_bond_yield: 3.5807016439305466

## c. Compute Intrinsic Risky Bond Price on IBM CDS Credit Curve (with Credit Risk)

```python
# Bond_recovery_rate
Bond_recovery_rate = 0.4

# Cds_curve_risky_bond_engine: using calibrated IBM CDS curve
Cds_curve_risky_bond_engine = ql.RiskyBondEngine (cds_surv_prob_curve_handle,             bond_recovery_rate,             sofr_yield_curve_handle)
Fixed_rate_bond.SetPricingEngine (cds_curve_risky_bond_engine)

# 3. Calculate intrinsic risky bond on custom survival probability curve
Risky_bond_price = fixed_rate_bond.CleanPrice ()
Risky_bond_yield = fixed_rate_bond.BondYield (risky_bond_price,             ql. Thirty 360 (ql. Thirty 360. USA),             ql. Compounded,             ql. Semiannual) * 100

Print ('risky_bond_price: ',             risky_bond_price)
Print ('risky_bond_yield: ',             risky_bond_yield)

# Compute the credit I-Spread,             relative to risk-free bond (SOFR curve)
Risky_bond_credit_ispread_bps = (risky_bond_yield - risk_free_bond_yield) * 100
Print ('risky_bond_ispread_bps: ',             risky_bond_credit_ispread_bps)

# Calc z-spread
Risky_bond_zspread_bps = ql.BondFunctions.ZSpread (fixed_rate_bond,             risky_bond_price,             sofr_yield_curve,             ql. Thirty 360 (ql. Thirty 360. USA),             ql. Compounded,             ql. Semiannual) * 1 e 4
Print ('risky_bond_zspread_bps: ',             risky_bond_zspread_bps)
```

    Risky_bond_price: 99.77353776497536
    Risky_bond_yield: 4.061950922012331
    Risky_bond_ispread_bps: 48.12492780817843
    Risky_bond_zspread_bps: 47.384353360489136

# 4. Pricing risky bonds in Custom Hazard Rate Model (with Credit Default Risk)
## a. Create and Display the Custom Credit Curve

```python
# 2. Create custom survival probability curve
Custom_surv_prob_dates = [calc_date + ql.Period (T ,             ql. Years) for T in range (11)]
Custom_average_hazard_rates = [0.0030,             0.0060,             0.0090,             0.0110,             0.0125,             0.0140,             0.0150,             0.0160,             0.0170,             0.0180,             0.0190]
Custom_surv_prob_levels = [np.Exp (-T * custom_average_hazard_rates[T]) for T in range (11)]
# Custom_surv_prob_levels = [1.0,             0.9950,             0.9860,             0.9733,             0.9569,             0.9370,             0.9166,             0.8940,             0.8728,             0.8504,             0.8269]

# Custom_surv_prob_curve
Custom_surv_prob_curve = ql.SurvivalProbabilityCurve (custom_surv_prob_dates,             custom_surv_prob_levels,             ql. Actual 360 (),             ql.TARGET ())
Custom_surv_prob_curve.EnableExtrapolation ()
Custom_surv_prob_curve_handle = ql.DefaultProbabilityTermStructureHandle (custom_surv_prob_curve)

# 3. Display custom credit curve
Custom_surv_prob_df = pd.DataFrame (data={'Date': custom_surv_prob_dates,            
                                          'Average Hazard Rates': custom_average_hazard_rates,            
                                          'Survival Probs': custom_surv_prob_levels})

Plt = custom_surv_prob_df.Plot (x='Date',             y='Average Hazard Rates',             grid=True,             style='*-',             title='Custom Hazard Rate Curve',             figsize=(12,            5))
Plt. Set_ylabel ('Hazard Rate (%)')
Plt. Set_xlabel ('Date')

Plt = custom_surv_prob_df.Plot (x='Date',             y='Survival Probs',             grid=True,             style='*-',             title='Custom Survival Probability Curve',             figsize=(12,            5))
Plt. Set_ylabel ('Survival Probability')
Plt. Set_xlabel ('Date')
```

    Text (0.5,             0,             'Date')
![png](CreditMarketSolutions_177_1.png)

![png](CreditMarketSolutions_177_2.png)

## b. Price Risky Bond on Custom Credit Curve (with Credit Risk)

```python
# Bond_recovery_rate
Bond_recovery_rate = 0.4

# Custom_curve_risky_bond_engine
Custom_curve_risky_bond_engine = ql.RiskyBondEngine (custom_surv_prob_curve_handle,             bond_recovery_rate,             sofr_yield_curve_handle)
Fixed_rate_bond.SetPricingEngine (custom_curve_risky_bond_engine)

# 3. Price risky bond on custom survival probability curve
Risky_bond_price = fixed_rate_bond.CleanPrice ()
Risky_bond_yield = fixed_rate_bond.BondYield (risky_bond_price,             ql. Thirty 360 (ql. Thirty 360. USA),             ql. Compounded,             ql. Semiannual) * 100

Print ('risky_bond_price: ',             risky_bond_price)
Print ('risky_bond_yield: ',             risky_bond_yield)

# Compute the credit I-Spread,             relative to risk-free bond (SOFR curve)
Risky_bond_credit_ispread_bps = (risky_bond_yield - risk_free_bond_yield) * 100
Print ('risky_bond_ispread_bps: ',             risky_bond_credit_ispread_bps)

# Calc z-spread
Risky_bond_zspread_bps = ql.BondFunctions.ZSpread (fixed_rate_bond,             risky_bond_price,             sofr_yield_curve,             ql. Thirty 360 (ql. Thirty 360. USA),             ql. Compounded,             ql. Semiannual) * 1 e 4
Print ('risky_bond_zspread_bps: ',             risky_bond_zspread_bps)
```

    Risky_bond_price: 98.75601148481837
    Risky_bond_yield: 4.342892980575562
    Risky_bond_ispread_bps: 76.21913366450156
    Risky_bond_zspread_bps: 75.04528626811441

# 5. Smooth parametric yield and hazard rate curves: Nelson-Siegel + extensions
## a. Nelson Siegel basis functions

```python
# Nelson_siegel curve shape: Nelson-Siegel
Def nelson_siegel (params,             maturity):
    ''' params = (theta 1,             theta 2,             theta 3,             lambda)'''    
    
    If (maturity > 0):
        Slope_1 = (1 - np.Exp (-maturity/params[3]))/(maturity/params[3])
    Else:            
        Slope_1 = 1

    Curvature_1 = slope_1 - np.Exp (-maturity/params[3])

    Total_value = params[0] + params[1] * slope_1 + params[2] * curvature_1
    
    Return total_value

# Nelson_siegel_extended curve shape: Nelson-Siegel-Svensson
Def nelson_siegel_extended (params,             maturity):

    If (maturity > 0):
        Slope_1 = (1 - np.Exp (-maturity/params[3]))/(maturity/params[3])
    Else:            
        Slope_1 = 1

    Curvature_1 = slope_1 - np.Exp (-maturity/params[3])

    Total_value = params[0] + params[1] * slope_1 + params[2] * curvature_1    
    
    If (params[5] != 0):
        If (maturity > 0):
            Slope_2 = (1 - np.Exp (-maturity/params[5]))/(maturity/params[5])
        Else:
            Slope_2 = 1

        Curvature_2 = slope_2 - np.Exp (-maturity/params[5])

        Total_value = total_value + params[4] * curvature_2
    Return total_value

```

## b. Plot Basis Functions for Nelson-Siegel + extensions

```python

Curve_shapes_df = pd.DataFrame ([T,             nelson_siegel ([1,             0,             0,             2],             T),             
                                 Nelson_siegel ([0,             1,             0,             2],             T),             
                                 Nelson_siegel ([0,             0,             2,             2],             T)] for T in range (0,            30,            1))
Curve_shapes_df. Columns = ['TTM',             'Level',             'Slope',             'Curvature']

Curve_shapes_df 2 = pd.DataFrame ([T,             nelson_siegel_extended ([1,             0,             0,             2,             0,             0],             T),             
                                 Nelson_siegel_extended ([0,             1,             0,             2,             0,             0],             T),             
                                 Nelson_siegel_extended ([0,             0,             2,             2,             0,             0],             T),             
                                 Nelson_siegel_extended ([0,             0,             0,             2,             1,             10],             T)] for T in range (0,            30,            1))
Curve_shapes_df 2. Columns = ['TTM',             'Level',             'Slope',             'Curvature_1',             'Curvature_2']

Print (curve_shapes_df 2. Head ())

Plt = curve_shapes_df.Plot (x='TTM',             y=['Level',             'Slope',             'Curvature'],             grid=True,             style='-',             title='Nelson-Siegel basis functions',             figsize=(12,            5))
Plt. Set_ylabel ('Curve Level')
Plt. Set_xlabel ('Time to maturity (years)')

Plt = curve_shapes_df 2. Plot (x='TTM',             y=['Level',             'Slope',             'Curvature_1',             'Curvature_2'],             grid=True,             style='-',             title='Nelson-Siegel-Svensson basis functions',             figsize=(12,            5))
Plt. Set_ylabel ('Curve Level')
Plt. Set_xlabel ('Time to maturity (years)')

```

       TTM  Level     Slope  Curvature_1  Curvature_2
    0    0    1.0  1.000000     0.000000     0.000000
    1    1    1.0  0.786939     0.360816     0.046788
    2    2    1.0  0.632121     0.528482     0.087615
    3    3    1.0  0.517913     0.589566     0.123121
    4    4    1.0  0.432332     0.593994     0.153880
    Text (0.5,             0,             'Time to maturity (years)')
![png](CreditMarketSolutions_183_2.png)

![png](CreditMarketSolutions_183_3.png)

## c. Constructing smooth Nelson-Siegel hazard rate / survival probability curves

```python
# Nelson_siegel_params = [theta 1,             theta 2,             theta 3,             lambda] = [long term level,             short - long slope,             curvature,             lambda]
Nelson_siegel_params = [0.0300,             -0.0100,             -0.0010,             2]

Nelson_siegel_surv_prob_dates = [calc_date + ql.Period (T ,             ql. Years) for T in range (31)]
Nelson_siegel_average_hazard_rates = [nelson_siegel (nelson_siegel_params,             T) for T in range (31)]
Nelson_siegel_surv_prob_levels = [np.Exp (-T * nelson_siegel_average_hazard_rates[T]) for T in range (31)]

# Nelson_siegel_surv_prob_curve
Nelson_siegel_credit_curve = ql.SurvivalProbabilityCurve (nelson_siegel_surv_prob_dates,             nelson_siegel_surv_prob_levels,             ql. Actual 360 (),             ql.TARGET ())
Nelson_siegel_credit_curve.EnableExtrapolation ()
Nelson_siegel_credit_curve_handle = ql.DefaultProbabilityTermStructureHandle (nelson_siegel_credit_curve)

Nelson_siegel_surv_prob_df = pd.DataFrame (data={'Dates': nelson_siegel_surv_prob_dates,            
                                          'Average Hazard Rates': nelson_siegel_average_hazard_rates,            
                                          'Survival Probs': nelson_siegel_surv_prob_levels})
# Print (nelson_siegel_surv_prob_df)

Plt = nelson_siegel_surv_prob_df.Plot (x='Dates',             y=['Average Hazard Rates'],             grid=True,             style='-',             title='Nelson-Siegel smooth hazard rate curve',             figsize=(12,            5))
Plt. Set_ylabel ('Average hazard rate')
Plt. Set_xlabel ('Maturity')

Plt = nelson_siegel_surv_prob_df.Plot (x='Dates',             y=['Survival Probs'],             grid=True,             style='-',             title='Nelson-Siegel smooth survival probability curve',             figsize=(12,            5))
Plt. Set_ylabel ('Survival Prob')
Plt. Set_xlabel ('Maturity')
```

    Text (0.5,             0,             'Maturity')
![png](CreditMarketSolutions_185_1.png)

![png](CreditMarketSolutions_185_2.png)

## d. Pricing risky bonds in Nelson-Siegel model (with Credit Risk)

```python
# Bond_recovery_rate
Bond_recovery_rate = 0.4

# Nelson_siegel_risky_bond_engine
Nelson_siegel_risky_bond_engine = ql.RiskyBondEngine (nelson_siegel_credit_curve_handle,             bond_recovery_rate,             sofr_yield_curve_handle)
Fixed_rate_bond.SetPricingEngine (nelson_siegel_risky_bond_engine)

# Price risky bond using Nelson-Siegel survival probability curve
Nelson_siegel_risky_bond_price = fixed_rate_bond.CleanPrice ()
Nelson_siegel_risky_bond_yield = fixed_rate_bond.BondYield (nelson_siegel_risky_bond_price,             ql. Thirty 360 (ql. Thirty 360. USA),             ql. Compounded,             ql. Semiannual) * 100

Print ('nelson_siegel_surv_prob_risky_bond_price: ',             nelson_siegel_risky_bond_price)
Print ('nelson_siegel_surv_prob_risky_bond_yield: ',             nelson_siegel_risky_bond_yield)

# Compute the credit I-Spread (relative to risk-free SOFR bond)
Nelson_siegel_risky_bond_credit_ispread = (nelson_siegel_risky_bond_yield - risk_free_bond_yield) * 1 e 2
Print ('nelson_siegel_risky_bond_ispread: ',             nelson_siegel_risky_bond_credit_ispread)

# Compute z-spread
Nelson_siegel_risky_bond_zspread = ql.BondFunctions.ZSpread (fixed_rate_bond,             nelson_siegel_risky_bond_price,             sofr_yield_curve,             ql. Thirty 360 (ql. Thirty 360. USA),             ql. Compounded,             ql. Semiannual) * 1 e 4
Print ('nelson_siegel_risky_bond_zspread: ',             nelson_siegel_risky_bond_zspread)
```

    Nelson_siegel_surv_prob_risky_bond_price: 95.95463373300109
    Nelson_siegel_surv_prob_risky_bond_yield: 5.134316444396973
    Nelson_siegel_risky_bond_ispread: 155.3614800466426
    Nelson_siegel_risky_bond_zspread: 152.96353195435728
