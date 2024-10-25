---
category: "[[Clippings]]"
author: 
title: "Valuing Convertible Bonds Using QuantLib Python"
source: http://gouthamanbalaraman.com/blog/value-convertible-bond-quantlib-python.html
clipped: 2024-10-25
published: 
topics: 
tags: [clippings]
---
# Valuing Convertible Bonds Using QuantLib Python

Provides an introduction to valuation of convertible bonds using QuantLib Python with a minimal example.
```python
import QuantLib as ql
```
In this blog I will work through an example of valuing convertible bonds in QuantLib. Lets start by doing the usual setup of creating a `calculation_date` and setting it as the `evaluationDate`.

One little quirk in the QuantLib convertible bond implementation is that there are places where the redemption amount is hard coded to `100`. So if you have conversion ratio evaluated as

Conversion Ratio\=Redemption AmountConversion Price

you will need to scale to an appropriate value with a redemption amount of `100`. For instance, vendors report conversion ratio with a redemption amount of 1000. The conversion ratio obtained this way should be divided by a factor of `10` to get the equivalent conversion ratio for use in the QuantLib calculations. This is a limitation right now (as of version 1.7), which can be fixed in the future.

Following is the details of the convertible bond of interest.

The call and put schedule for this bond is created as shown below. Here for each call date, we create a `CallabilityPrice`, then use that to form the `Callability` object. This is appended to the `CallabilitySchedule` object to form a list of call and put schedules.

Any dividend information for the underlying stock is used to form the `DividendSchedule`.

Now we bulid the fixed coupon convertible bond object

Build the Black-Scholes-Merton process to model the equity part

Build the convertible bond pricing engine