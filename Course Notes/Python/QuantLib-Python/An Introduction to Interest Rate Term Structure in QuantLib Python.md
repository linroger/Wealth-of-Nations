---
title: An Introduction to Interest Rate Term Structure in QuantLib Python
source: 
  https://gouthamanbalaraman.com/blog/quantlib-term-structure-bootstrap-yield-curve.html
description: This post will walk through the basics of bootstrapping yield curve in
  QuantLib Python.
tags:
  - bond_pricing
  - bootstrapping
  - interest_rate_term_structure
  - quantlib_python
  - yield_curve
aliases:
  - Interest Rate Term Structure
  - QuantLib Python
  - Yield Curve Bootstrapping
key_concepts:
  - Bootstrapping yield curve
  - Coupon bonds
  - Pricing securities
  - QuantLib Python basics
  - Spot rates
---

# An Introduction to Interest Rate Term Structure in QuantLib Python

This post will walk through the basics of bootstrapping yield curve in QuantLib Python.

*Visit here for other [QuantLib Python examples](http://gouthamanbalaraman.com/blog/quantlib-python-tutorials-with-examples.html). If you found these posts useful,  please take a minute by providing some [feedback.](https://docs.google.com/forms/d/e/1FAIpQLSdFdJ768HKmIyJmaVRHBUJNY5NyQl6vr0GZvSkx-bUfIloNZA/viewform)*

Term structure is pivotal to pricing securities. One would need a YieldTermStructure object created in QuantLib to use with pricing engines. In an earlier post on [modeling bonds using QuantLib](https://gouthamanbalaraman.com/blog/quantlib-bond-modeling.html) we discussed how to use spot rates directly with bond pricing engine. Here in this post we will show how to bootstrap yield curve using QuantLib.

As usual lets import QuantLib and do some initialization.

```python
import QuantLib as ql

def print_curve(xlist,      ylist,      precision=3):
    """
    Method to print curve in a nice format
    """
    print "----------------------"
    print "Maturities\tCurve"
    print "----------------------"
    for x,     y in zip(xlist,      ylist):
        print x,     "\t\t",      round(y,      precision)
    print "----------------------"
```

The deposit rates and fixed rate bond rates are provided below. This example is based on Exhibit 5-5 given in Frank Fabozzi's Bond Markets,  Analysis and Strategies,  Sixth Edition.

```python
# An Introduction to Interest Rate Term Structure in QuantLib Python
depo_maturities = [ql.Period(6,     ql.Months),      ql.Period(12,      ql.Months)]
depo_rates = [5.25,      5.5]

# Bond rates
bond_maturities = [ql.Period(6*i,      ql.Months) for i in range(3,     21)]
bond_rates = [5.75,      6.0,      6.25,      6.5,      6.75,      6.80,      7.00,      7.1,      7.15,     
              7.2,      7.3,      7.35,      7.4,      7.5,      7.6,      7.6,      7.7,      7.8]

print_curve(depo_maturities+bond_maturities,      depo_rates+bond_rates)
```

Lets define some of the constants required for the rest of the objects needed below.

```python
# some constants and conventions
# here we just assume for the sake of example
# that some of the constants are the same for
# depo rates and bond rates

calc_date = ql.Date(15,      1,      2015)
ql.Settings.instance().evaluationDate = calc_date

calendar = ql.UnitedStates()
bussiness_convention = ql.Unadjusted
day_count = ql.Thirty360()
end_of_month = True
settlement_days = 0
face_amount = 100
coupon_frequency = ql.Period(ql.Semiannual)
settlement_days = 0
```

The basic idea of bootstrapping using QuantLib is to use the deposit rates and bond rates to create individual helpers. Then use the combination of the two helpers to construct the yield curve.

```python
# create deposit rate helpers from depo_rates
depo_helpers = [ql.DepositRateHelper(ql.QuoteHandle(ql.SimpleQuote(r/100.0)),     
                                     m,     
                                     settlement_days,     
                                     calendar,     
                                     bussiness_convention,     
                                     end_of_month,     
                                     day_count )
                for r,      m in zip(depo_rates,      depo_maturities)]
```

The rest of the points are coupon bonds. We assume that the YTM given for the bonds are all par rates. So we have bonds with coupon rate same as the YTM.

```python
# create fixed rate bond helpers from fixed rate bonds
bond_helpers = []
for r,      m in zip(bond_rates,      bond_maturities):
    termination_date = calc_date + m
    schedule = ql.Schedule(calc_date,     
                   termination_date,     
                   coupon_frequency,     
                   calendar,     
                   bussiness_convention,     
                   bussiness_convention,     
                   ql.DateGeneration.Backward,     
                   end_of_month)

    helper = ql.FixedRateBondHelper(ql.QuoteHandle(ql.SimpleQuote(face_amount)),     
                                        settlement_days,     
                                        face_amount,     
                                        schedule,     
                                        [r/100.0],     
                                        day_count,     
                                        bussiness_convention,     
                                        )
    bond_helpers.append(helper)
```

The yield curve is constructed by putting the two helpers together.

```python
rate_helpers = depo_helpers + bond_helpers
yieldcurve = ql.PiecewiseLogCubicDiscount(calc_date,     
                             rate_helpers,     
                             day_count)
```

The spot rates is obtined from yieldcurve object using the zeroRate method.

```python
# get spot rates
spots = []
tenors = []
for d in yieldcurve.dates():
    yrs = day_count.yearFraction(calc_date,      d)
    compounding = ql.Compounded
    freq = ql.Semiannual
    zero_rate = yieldcurve.zeroRate(yrs,      compounding,      freq)
    tenors.append(yrs)
    eq_rate = zero_rate.equivalentRate(day_count,     
                                       compounding,     
                                       freq,     
                                       calc_date,     
                                       d).rate()
    spots.append(100*eq_rate)
```

The bootstrap curve looks as shown below:

| Maturity | Spots |
| --- | --- |
| 0.0 | 0.0 |
| 0.5 | 5.25 |
| 1.0 | 5.426 |
| 1.5 | 5.761 |
| 2.0 | 6.02 |
| 2.5 | 6.283 |
| 3.0 | 6.55 |
| 3.5 | 6.822 |
| 4.0 | 6.87 |
| 4.5 | 7.095 |
| 5.0 | 7.205 |
| 5.5 | 7.257 |
| 6.0 | 7.31 |
| 6.5 | 7.429 |
| 7.0 | 7.485 |
| 7.5 | 7.543 |
| 8.0 | 7.671 |
| 8.5 | 7.802 |
| 9.0 | 7.791 |
| 9.5 | 7.929 |
| 10.0 | 8.072 |

Once we have the spots,  the zero coupon curve can be directly constructed the next time as show in the [bond pricing example](https://gouthamanbalaraman.com/quantlib-bond-modeling.html). The yieldcurve.dates() and yieldcuve.zeroRate(…) methods would provide for the necessary rates as shown above.

   [python](http://gouthamanbalaraman.com/tag/python.html)   [finance](http://gouthamanbalaraman.com/tag/finance.html)   [quantlib](http://gouthamanbalaraman.com/tag/quantlib.html)

---

**Related Post**

- [QuantLib Python Tutorials With Examples](http://gouthamanbalaraman.com/blog/quantlib-python-tutorials-with-examples.html)
- [Modeling Vanilla Interest Rate Swaps Using QuantLib Python](http://gouthamanbalaraman.com/blog/interest-rate-swap-quantlib-python.html)
- [Valuing Options on Commodity Futures Using QuantLib Python](http://gouthamanbalaraman.com/blog/value-options-commodity-futures-black-formula-quantlib-python.html)
- [Short Interest Rate Model Calibration in QuantLib Python](http://gouthamanbalaraman.com/blog/short-interest-rate-model-calibration-quantlib.html)
- [Announcing qtk for QuantLib Python](http://gouthamanbalaraman.com/blog/announcing-qtk-quantlib-python.html)

---