---
title: Valuing European Option Using the Heston Model in QuantLib Python
source: "https://gouthamanbalaraman.com/blog/valuing-european-option-heston-model-quantLib.html"
description: "Introduces an example on how to value European options using Heston model in Quantlib Python"
tags: ["clippings"]
---
# Valuing European Option Using the Heston Model in QuantLib Python

Introduces an example on how to value European options using Heston model in Quantlib Python

*Visit here for other [QuantLib Python examples](http://gouthamanbalaraman.com/blog/quantlib-python-tutorials-with-examples.html). If you found these posts useful,  please take a minute by providing some [feedback.](https://docs.google.com/forms/d/e/1FAIpQLSdFdJ768HKmIyJmaVRHBUJNY5NyQl6vr0GZvSkx-bUfIloNZA/viewform)*

Heston model can be used to value options by modeling the underlying asset such as the stock of a company. The one major feature of the Heston model is that it inocrporates a stochastic volatility term.

$$\begin{eqnarray} dS\_t &=& \mu S\_tdt + \sqrt{V\_t} S\_t dW\_t^1 \\ dV\_t &=& \kappa(\theta-V\_t) + \sigma \sqrt{V\_t} dW\_t^2 \end{eqnarray}$$

Here :

- $S\_t$ is the asset's value at time $t$
- $\mu$ is the expected growth rate of the log normal stock value
- $V\_t$ is the variance of the asset $S\_t$
- $W\_t^1$ is the stochastic process governing the $S\_t$ process
- $\theta$ is the value of mean reversion for the variance $V\_t$
- $\kappa$ is the strength of mean reversion
- $\sigma$ is the volatility of volatility
- $W\_t^2$ is the stochastic process governing the $V\_t$ process
- The correlation between $W\_t^1$ and $W\_t^2$ is $\rho$

In contrast,  the Black-Scholes-Merton process assumes that the volatility is constant.

Let us consider a European call option for AAPL with a strike price of \$130 maturing on 15th Jan,  2016. Let the spot price be \$127.62. The volatility of the underlying stock is know to be 20%,  and has a dividend yield of 1.63%. We assume a short term risk free rate of 0.1%. Lets value this option as of 8th May,  2015.

Using the above inputs,  we construct the European option as shown below.

In \[3\]:

```latex
# Valuing European Option Using the Heston Model in QuantLib Python
payoff = ql.PlainVanillaPayoff(option_type,  strike_price)
exercise = ql.EuropeanExercise(maturity_date)
european_option = ql.VanillaOption(payoff,  exercise)
```

In order to price the option using the Heston model,  we first create the Heston process. In order to create the Heston process,  we use the parameter values: mean reversion strength `kappa = 0.1`,  the spot variance `v0 = volatility*volatility = 0.04`,  the mean reversion variance `theta=v0`,  volatility of volatility `sigma = 0.1` and the correlation between the asset price and its variance is `rho = -0.75`.

On valuing the option using the Heston model,  we get the net present value as:

In \[5\]:

```latex
engine = ql.AnalyticHestonEngine(ql.HestonModel(heston_process), 0.01,  1000)
european_option.setPricingEngine(engine)
h_price = european_option.NPV()
print "The Heston model price is", h_price
```

```latex
The Heston model price is 6.5308651372
```

Performing the same calculation using the Black-Scholes-Merton process,  we get:

```latex
The Black-Scholes-Merton model price is  6.74927181246
```

The difference in the price between the two models is: `bs_price - h_price = 0.21840667525992163`. This difference is due to the stochastic modeling of the volatility as a CIR-process.

## Conclusion

This post provided a minimal example of valuing European options using the Heston model. Comparison with the Black-Scholes-Merton model is shown for instructional purpose.

   [quantlib](http://gouthamanbalaraman.com/tag/quantlib.html)   [python](http://gouthamanbalaraman.com/tag/python.html)   [finance](http://gouthamanbalaraman.com/tag/finance.html)

---

**Related Post**

- [QuantLib Python Tutorials With Examples](http://gouthamanbalaraman.com/blog/quantlib-python-tutorials-with-examples.html)
- [On the Convergence of Hull White Monte Carlo Simulations](http://gouthamanbalaraman.com/blog/hull-white-simulation-monte-carlo-convergence.html)
- [Valuing Options on Commodity Futures Using QuantLib Python](http://gouthamanbalaraman.com/blog/value-options-commodity-futures-black-formula-quantlib-python.html)
- [Short Interest Rate Model Calibration in QuantLib Python](http://gouthamanbalaraman.com/blog/short-interest-rate-model-calibration-quantlib.html)
- [QuantLib Python Cookbook Announcement](http://gouthamanbalaraman.com/blog/quantlib-python-cookbook-announcement.html)

