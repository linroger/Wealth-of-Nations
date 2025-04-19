---
tags:
  - asset_pricing
  - black_scholes_merton
  - geometric_brownian_motion
  - stochastic_processes
  - volatility
aliases:
  - ABM
  - Black-Scholes
  - GBM
  - Preview
  - Recap
key_concepts:
  - Arithmetic Brownian motion
  - Asset return behavior
  - Black-Scholes-Merton model
  - Geometric Brownian motion
  - Stochastic process and asset
---

# 12.7 RECAP AND PREVIEW

In this chapter, we took what we have already learned about stochastic processes and adapted it to the case of an asset. We showed how certain properties of the asset's return behavior are derived out of the model. We showed how to obtain the formula for the future

asset price in terms of a base price and information on what happened in the intervening period. We also examined and compared both arithmetic Brownian motion and GBM.

In the following chapter, we shall do what we have been alluding to many times: derive the Black-Scholes-Merton model..

# QUESTIONS AND PROBLEMS

1 Geometric Brownian motion with geometric drift is often represented in one of two ways:

$$
d S_{t}=(\mu+\sigma^{2}/2)S_{t}d t+\sigma S_{t}d W_{t}.
$$

In the finance context, explain the economic relationship between $\alpha$ and $\mu$

2 Mathematically, there are significant differences between GBM with geometric drift and ABM with geometric drift. In early empirical work on stock prices, Osborne (1959) asserted, "Percentage changes of less than 15 per cent, expressed as fractions from unity, are very nearly natural logarithms of the same ratio" (p. 146). Identify five important issues related to the choice of GBM or ABM.

3Volatility is often reported as a standard deviation,. $\sigma$ . If we assume the standard deviation itself follows GBM with geometric drift, what is the stochastic process of the variance as well as its mean and variance?.

4Assuming $S_{t}$ follows geometric Brownian motion, explain the relationship between $E\big[\mathrm{ln}\big(S_{T}/S_{0}\big)\big]$ and $\ln\bigl[E\bigl(S_{T}\bigr)/S_{0}\bigr]$

5 Based on a historical analysis of a tech company, the annualized average arithmetic return was $29.4\%$ and the annualized average geometric return was $25.95\%$ . The annualized standard deviation of arithmetic returns was $26.2\%$ . Based on the analysis contained in this chapter, how can you explain the relationship between these two annualized returns?

# NOTES

1. Profits are simply revenues minus expenses. An example of a calendar spread is the difference between the wholesale price of a good purchased in June and the retail price of the same good sold in December. An example of a product spread is the cost of crude oil purchased by a refinery and the subsequent price of refined products sold.
2. A linear transformation of a normally distributed variable $x$ to a variable $y$ by multiplying $x$ by a constant and adding a constant preserves the normality.
3. Technically, we may consider using $\varDelta t$ in this explanation rather than $d t$ Given the context here of diffusion processes, we simply use dt.
4. In a lognormal distribution, the log return is normally distributed.
5. Here we use $d S$ to mean changes over short time periods and S to mean long time period.
6. Recall we use $\$1$ symbol to emphasize the different unit of measure with ABM.
7. The proof of this result is covered in Chapter 11. See Section 11.5.1
8. The reason we know this is the solution is that the derivative of the natural log function is. $(1/y_{t})$ times the derivative of $y_{t}$ with respect to $\mathbb{W}_{t}$
9. See, for example, Antoin E. Murphy, "Corporate Ownership in France: The Importance of History," NBER, Working Paper 10716, 2004, http:/www.nber.org/papers/w10716.
10. A cross-sectional distribution is taken at a point in time but examines different instruments, such as stock prices. Time series distribution is taken across time for selected instruments, again such as stock prices.
11. Without limited liability, a call option can be higher than the corresponding stock price because the call enjoys limited liability, whereas the underlying stock does not..
12. Homogeneity is covered in detail in Chapter 17 but mentioned here just to have an exhaustive list of the issues related to GBM and ABM.

# Deriving the Black-Scholes-Merton Model

rom the basic principles associated with the standard geometric Brownian motion. stochastic process used in modeling asset prices and with an understanding of Ito's lemma, we can now derive the Black-Scholes-Merton (Black and Scholes 1973; Merton 1973b) model for pricing European options. Let the asset price follow the standard. lognormal diffusion process given by the stochastic differential equation known as. geometric Brownian motion,

$$
\frac{d S_{t}}{S_{t}}=\alpha d t+\sigma d\mathrm{{W}}_{t},
$$

where $d S_{t}$ is the change in the asset price per unit of time. $d t,S_{t}$ is the asset price at time. $t,\alpha$ is the drift or expected rate of return on the asset,. $\sigma$ is the volatility of the return on. the asset, and $d\mathbb{W}_{t}$ is the Wiener process that represents the uncertainty. Equation (13.1). describes the rate of return on the asset. Recall that $d\mathbb{W}_{t}=\varepsilon_{t}{\sqrt{d t}}$ where $\varepsilon_{t}$ is a standard normal random variable (mean 0, variance 1) and that the key properties of $d\mathbb{W}_{t}$ are that $E\big(d\mathbb{W}_{t}\big)=0$ $\operatorname{var}\left(d\mathrm{W}_{t}\right)=d t$ and that $\boldsymbol{d}\boldsymbol{\mathrm{W}}_{t}^{2}=\boldsymbol{d t}$
