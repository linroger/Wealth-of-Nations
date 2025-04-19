---
tags:
  - binomial_model
  - black_scholes_merton_model
  - dividend_yield
  - dividends
  - european_options
aliases:
  - Dividend Impact
  - Dividend Payments
key_concepts:
  - Binomial model challenges
  - Continuous dividend yield
  - Dividend adjusted BSM model
  - Dividends lower growth rate
  - Escrow method
---

# 9.4 DIVIDENDS

The payment of dividends has the effect of lowering the expected growth rate of the stock based on the risk-neutral probability measure. Hence, solely increasing dividends will lower the call price and raise the put price. Thus, we need an efficient way to incorporate dividends into the Black-Scholes-Merton model for European options.

As discussed in Chapter 7, dividends pose a significant problem within the binomial. model. Based on the escrow method, we work backward through the tree checking whether the binomial model value is below the exercise value. Recall it may be optimal for the call buyer to exercise immediately before the ex-dividend date whereas the put buyer would. exercise immediately after the ex-dividend date so as to enable the stock to drop, which benefits the put buyer. The escrow method works well with short dated options on individual stocks or other instruments with relatively few dividend payments over the life of. the option.

Alternatively, we may assume a known continuous dividend yield. The dividend yield approach is useful for index options that contain a large number of relatively small dividends. As with discrete dividends, the continuous dividend yield will have the effect of lowering the expected growth rate of the stock. Thus, the risk-neutral probability of an up move occurring can be expressed as

$$
\phi=\frac{e^{(r_{c}-\delta_{c})\Delta t}-d}{u-d},
$$

where $\delta_{c}$ denotes the annualized, continuously compounded dividend yield. In this case, the dividend adjusted binomial model converges to the dividend adjusted Black-ScholesMerton model or

$$
c_{t}=S_{t}e^{-\delta_{c}\tau}N(d_{1})-X e^{-r_{c}\tau}N(d_{2}),
$$

where

$$
d_{1}=\frac{\ln(S_{t}/X)+(r_{c}-\delta_{c}+\sigma^{2}/2)\tau}{\sigma\sqrt{\tau}},\mathrm{and}
$$

$$
d_{2}=\frac{\ln(S_{t}/X)+(r_{c}-\delta_{c}-\sigma^{2}/2)\tau}{\sigma\sqrt{\tau}}.
$$
