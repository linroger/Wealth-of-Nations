---
title: Valuing Treasury Futures Using QuantLib Python
source: http://gouthamanbalaraman.com/blog/value-treasury-futures-quantlib-python.html
description: Provides an introduction to valuation of treasury futures contract in
  QuantLib Python.
tags:
  - cheapest_to_deliver
  - futures_contract
  - quantlib_python
  - treasury_futures
  - yield_curve
aliases:
  - QuantLib Futures
  - Valuing Futures
key_concepts:
  - Build yield curve
  - Cheapest to deliver
  - Futures contract modeling
  - QuantLib Python contract
  - Treasury futures valuation
---

# Valuing Treasury Futures Using QuantLib Python
Provides an introduction to valuation of treasury futures contract in QuantLib Python.

In this post,  we will learn how to value treasury futures contract using QuantLib. The treasury futures contract gives the buyer the right to buy the underlying by the time the contract expires. The underlying is usually delivered from a basket of securities. So in order to properly value the futures contract,  we would need to find the deliverable. Here we start by doing a naive calculation by constructing a fictional security. We will see what is wrong about this approach. As a next step we will perform the cheapest to deliver calculation and subsequently use that deliverable to value the same contract.

```latex
import QuantLib as ql
import math

calc_date = ql.Date(30,  11,  2015)
ql.Settings.instance().evaluationDate = calc_date
day_count = ql.ActualActual()
calendar = ql.UnitedStates()
bussiness_convention = ql.Following
end_of_month = False
settlement_days = 0
face_amount = 100
coupon_frequency = ql.Period(ql.Semiannual)
```

## Build Yield Curve

As a first step,  we build the treasury curve out of the treasury securities such as T-Bills,  T-Notes and Treasury bonds.

Collapse Code

```latex
# build curve
prices = [99.9935,  99.9576,  99.8119,  99.5472,  99.8867,  
100.0664,  99.8711,  100.0547,  100.3047,  100.2266]

coupon_rates = [0.0000,   0.0000,   0.0000,   0.0000,   0.00875,   
               0.0125,   0.01625,   0.02,   0.0225,   0.03]
maturity_dates = [ql.Date(24,  12,  2015),   ql.Date(25,  2,  2016),   
                  ql.Date(26,  5,  2016),   ql.Date(10,  11,  2016),  
                  ql.Date(30,  11,  2017),   ql.Date(15,  11,  2018),   
                  ql.Date(30,  11,  2020),   ql.Date(30,  11,  2022),  
                  ql.Date(15,  11,  2025),   ql.Date(15,  11,  2045)]

issue_dates = [ql.Date(25,  6,  2015),   ql.Date(27,  8,  2015),  
               ql.Date(28,  5,  2015),   ql.Date(12,  11,  2015),  
               ql.Date(30,  11,  2015),   ql.Date(16,  11,  2015),  
               ql.Date(30,  11,  2015),   ql.Date(30,  11,  2015),  
               ql.Date(16,  11,  2015),   ql.Date(16,  11,  2015)]

coupon_frequency = ql.Period(6,   ql.Months)

bond_helpers = []
for coupon,   issue_date,   maturity_date,   price \
    in zip(coupon_rates,   issue_dates,   maturity_dates,   prices):
    schedule = ql.Schedule(calc_date,  
                   maturity_date,  
                   coupon_frequency,  
                   calendar,  
                   bussiness_convention,  
                   bussiness_convention,  
                   ql.DateGeneration.Backward,  
                   False)

    helper = ql.FixedRateBondHelper(ql.QuoteHandle(ql.SimpleQuote(price)),  
                                    settlement_days,  
                                    face_amount,  
                                    schedule,  
                                    [coupon],  
                                    day_count,  
                                    bussiness_convention
                                    )
    bond_helpers.append(helper)

yield_curve = ql.PiecewiseCubicZero(calc_date,   bond_helpers,   day_count)
yield_curve_handle = ql.YieldTermStructureHandle(yield_curve)
for d in maturity_dates:
    print "|%20s  %9.6f|"%(d,   yield_curve.discount(d))
```

```latex
| December 24th,   2015   0.999935|
| February 25th,   2016   0.999576|
|      May 26th,   2016   0.998119|
| November 10th,   2016   0.995472|
| November 30th,   2017   0.981524|
| November 15th,   2018   0.964278|
| November 30th,   2020   0.920306|
| November 30th,   2022   0.868533|
| November 15th,   2025   0.799447|
| November 15th,   2045   0.384829|
```

## Treasury Futures

Here we want to understand how to model treasury futures contract. Let us look at the TYZ5,  the treasury futures on the 10 year note for delivery in December 2015. The notional deliverable is a 10-year 6% coupon note. In reality,  the seller of the futures contract can deliver from a basket of securities. 

For now,  lets assume that the deliverable is actually a 6% coupon 10-year note issued as of the calculation date. Let us construct a 10 year treasury note and value this security. The futures price for the TYZ5 is $127.0625.

```latex
def create_tsy_security(bond_issue_date,   
                        bond_maturity_date,  
                        coupon_rate,  
                        coupon_frequency=ql.Period(6,   ql.Months),  
                        day_count=ql.ActualActual(),  
                        calendar=ql.UnitedStates()
                        ):
    face_value = 100.
    settlement_days = 0
    
    schedule = ql.Schedule(bond_issue_date,  
                           bond_maturity_date,  
                           coupon_frequency,  
                           calendar,  
                           ql.ModifiedFollowing,  
                           ql.ModifiedFollowing,  
                           ql.DateGeneration.Forward,  
                           False)

    security = ql.FixedRateBond(settlement_days,  
                                   face_value,  
                                   schedule,  
                                   [coupon_rate],  
                                   day_count
                                   )
    return security

bond_issue_date = calc_date 
delivery_date = ql.Date(1,  12,  2015)

bond_maturity_date = bond_issue_date + ql.Period(10,   ql.Years)
day_count = ql.ActualActual()
coupon_frequency = ql.Period(6,   ql.Months)
coupon_rate = 6/100.

deliverable = create_tsy_security(bond_issue_date,  
                                  bond_maturity_date,  
                                  coupon_rate,  
                                  coupon_frequency,  
                                  day_count,  
                                  calendar
                                  )
bond_engine = ql.DiscountingBondEngine(yield_curve_handle)
deliverable.setPricingEngine(bond_engine)
```

Lets calculate the Z-Spread for this deliverable. The Z-Spread is the static spread added to the yield curve to match the price of the security. This spread is a measure of the risk associated with the security. For a treasury security,  you would expect this to be zero. 

```latex
futures_price = 127.0625
clean_price = futures_price*yield_curve.discount(delivery_date)

zspread = ql.BondFunctions.zSpread(deliverable,   clean_price,  
                                   yield_curve,   day_count,   
                                   ql.Compounded,   ql.Semiannual,   
                                   calc_date)*10000
print "Z-Spread =%3.0fbp" % (zspread)
```

```latex
Z-Spread = 71bp
```

Here we get a spread of 71 basis points. This is unusually high for a treasury futures contract. 

### Cheapest To Deliver

Above we used a fictional 6% coupon bond as the deliverable. In reality,  the deliverable is picked from a basket of securities based on what is the cheapest to deliver. Cheapest to deliver is not the cheapest in price. The seller of the futures contract,  has to buy the delivery security from the market and sell it at an adjusted futures price. The adjusted futures price is given as:

_Adjusted Futures Price = Futures Price x Conversion Factor_

The gain or loss to the seller is given by the basis,

_Basis = Cash Price - Adjusted Futures Price_

So the cheapest to deliver is expected to be the security with the lowest basis. The conversion factor for a security is the price of the security with a 6% yield. Let us look at a basket of securities that is underlying this futures contract to understand this aspect.

Collapse Code

```latex
# basket describes the coupon rate,   maturity date,   price
day_count = ql.ActualActual()
basket = [(1.625,   ql.Date(15,  8,  2022),   97.921875),   
          (1.625,   ql.Date(15,  11,  2022),   97.671875),  
          (1.75,   ql.Date(30,  9,  2022),   98.546875),  
          (1.75,   ql.Date(15,  5,  2023),   97.984375),  
          (1.875,   ql.Date(31,  8,  2022),   99.375),  
          (1.875,   ql.Date(31,  10,  2022)0.\1),  
          (2.0,   ql.Date(31,  7,  2022),   100.265625),   
          (2.0,   ql.Date(15,  2,  2023),   100.0625),  
          (2.0,   ql.Date(15,  2,  2025),   98.296875),  
          (2.0,   ql.Date(15,  8,  2025),   98.09375),  
          (2.125,   ql.Date(30,  6,  2022),   101.06250),  
          (2.125,   ql.Date(15,  5,  2025)0.\1),  
          (2.25,   ql.Date(15,  11,  2024)0.\1),  
          (2.25,   ql.Date(15,  11,  2025)0.\1),  
          (2.375,   ql.Date(15,  8,  2024)0.\1),  
          (2.5,   ql.Date(15,  8,  2023)0.\1),  
          (2.5,  ql.Date(15,  5,  2024)0.\1),  
          (2.75,   ql.Date(15,  11,  2023)0.\1),  
          (2.75,  ql.Date(15,  2,  2024)0.\1)
          ]
securities = []
min_basis = 100; min_basis_index = -1
for i,   b in enumerate(basket):
    coupon,   maturity,   price = b
    issue = maturity - ql.Period(10,  ql.Years)
    s = create_tsy_security(issue,  maturity,   coupon/100.)
    bond_engine = ql.DiscountingBondEngine(yield_curve_handle)
    s.setPricingEngine(bond_engine)
    cf = ql.BondFunctions.cleanPrice(s0.\1,  
                                     day_count,   ql.Compounded,  
                                     ql.Semiannual,   calc_date)/100.
    adjusted_futures_price = futures_price * cf
    basis = price-adjusted_futures_price
    if basis< min_basis:
        min_basis = basis 
        min_basis_index = i
    securities.append((s,  cf))
    
ctd_info = basket[min_basis_index]
ctd_bond,  ctd_cf = securities[min_basis_index]
ctd_price = ctd_info[2]
print "%-30s = %lf" % ("Minimum Basis",   min_basis)
print "%-30s = %lf" % ("Conversion Factor",   ctd_cf)
print "%-30s = %lf" % ("Coupon",   ctd_info[0])
print "%-30s = %s" % ("Maturity",   ctd_info[1])
print "%-30s = %lf" % ("Price",   ctd_info[2])
```

```latex
Minimum Basis                  = 0.450601
Conversion Factor              = 0.791830
Coupon                         = 2.125000
Maturity                       = June 30th,   2022
Price                          = 101.062500
```

The basis is the loss for a notional of $100 that the seller accrues to close this contract. For a single futures contract (which has a $100000 notional),  there is a loss of $450.60.

NOTE: You will need my [pull request](https://github.com/lballabio/quantlib/pull/370) to execute the `FixedRateBondForward` class since it is not exposed in SWIG at the moment.

```latex
futures_maturity_date = ql.Date(21,  12,  2015)
futures = ql.FixedRateBondForward(calc_date,   futures_maturity_date,   
                                  ql.Position.Long,   0.0,   settlement_days,  
                                  day_count,   calendar,   bussiness_convention,  
                                  ctd_bond,   yield_curve_handle,   yield_curve_handle)
```

The valuation of the futures contract and the underlying is shown below:

Collapse Code

```latex
model_futures_price = futures.cleanForwardPrice()/ctd_cf
implied_yield = futures.impliedYield(ctd_price/ctd_cf,   futures_price,   
                                     calc_date,   ql.Compounded,   day_count).rate()
z_spread = ql.BondFunctions.zSpread(ctd_bond,   ctd_price,   yield_curve,   
                                    day_count,   ql.Compounded,   ql.Semiannual,   
                                    calc_date)
ytm = ql.BondFunctions._yield(ctd_bond,   ctd_price,   day_count,  
                              ql.Compounded,   ql.Semiannual,   calc_date)

print "%-30s = %lf" % ("Model Futures Price",   model_futures_price)
print "%-30s = %lf" % ("Market Futures Price",   futures_price)
print "%-30s = %lf" % ("Model Adjustment",   model_futures_price-futures_price)
print "%-30s = %2.3f%%" % ("Implied Yield",   implied_yield*100)
print "%-30s = %2.1fbps" % ("Forward Z-Spread",   z_spread*10000)
print "%-30s = %2.3f%%" % ("Forward YTM ",   ytm*100)
```

```latex
Model Futures Price            = 127.610365
Market Futures Price           = 127.062500
Model Adjustment               = 0.547865
Implied Yield                  = -7.473%
Forward Z-Spread               = 1.6bps
Forward YTM                    = 1.952%
```

## References

\[1\] [Understanding Treasury Futures](https://www.cmegroup.com/education/files/understanding-treasury-futures.pdf),  CME Group PDF

## Conclusion

In this notebook,  we looked into understanding and valuing treasury futures contracts. We used the QuantLib `FixedRateBondForward` class in order to model the futures contract. But,  we also made a cheapest to deliver calculation to figure out the deliverable.