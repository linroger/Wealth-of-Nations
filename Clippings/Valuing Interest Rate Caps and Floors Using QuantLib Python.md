---
title: "Valuing Interest Rate Caps and Floors Using QuantLib Python"
source: "http://gouthamanbalaraman.com/blog/interest-rate-cap-floor-valuation-quantlib-python.html"
description: "A tutorial on valuing caps and floors using QuantLib Python."
tags:
  - "clippings"
---
# Valuing Interest Rate Caps and Floors Using QuantLib Python

A tutorial on valuing caps and floors using QuantLib Python.

In this post, I will walk you through a simple example of valuing caps. I want to talk about two specific cases:

1.  Value caps given a constant volatility
2.  Value caps given a cap volatility surface

Caps, as you might know, can be valued as a sum of caplets. The value of each caplet is determined by the Black formula. In practice, each caplet would have a different volatility. Meaning, a caplet that is in the near term can have a different volotility profile compared to the caplet that is far away in tenor. Similarly caplet volatilities differ with the strike as well.

Let us start by constructing different componets required in valuing the caps. The components that we would need are:

1.  interest rate term structure for discounting
2.  interest rate term structure for the floating leg
3.  construction of the cap
4.  the pricing engine to value caps using the Black formula

For simplicity, we will construct only one interest rate term structure here, and assume that the discounting and the floating leg is referenced by the same. Below the term structure of interest rates is constructed from a set of zero rates.
```
dates = [ql.Date(14,6,2016), ql.Date(14,9,2016), 
         ql.Date(14,12,2016), ql.Date(14,6,2017),
         ql.Date(14,6,2019), ql.Date(14,6,2021),
         ql.Date(15,6,2026), ql.Date(16,6,2031),
         ql.Date(16,6,2036), ql.Date(14,6,2046)
         ]
yields = [0.000000, 0.006616, 0.007049, 0.007795,
          0.009599, 0.011203, 0.015068, 0.017583,
          0.018998, 0.020080]
day_count = ql.ActualActual()
calendar = ql.UnitedStates()
interpolation = ql.Linear()
compounding = ql.Compounded
compounding_frequency = ql.Annual

term_structure = ql.ZeroCurve(dates, yields, day_count, calendar, 
                       interpolation, compounding, compounding_frequency)
ts_handle = ql.YieldTermStructureHandle(term_structure)
```