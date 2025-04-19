---
tags:
  - binomial_model
  - black_scholes_merton
  - dividends
  - index_options
  - option_pricing
aliases:
  - BSM
  - Black-Scholes
  - Option Pricing with Dividends
key_concepts:
  - Black-Scholes-Merton formula
  - Continuously compounded dividend yield
  - Holding or carrying costs
  - Index options dividend approximation
  - Present value of dividends
---

# 13.6 BLACK-SCHOLES-MERTON OPTION PRICING WHEN THERE ARE DIVIDENDS

Recall in Chapter 2 that we examined the boundary conditions for option pricing with. and without dividends. In almost every situation, we subtracted the present value of the dividends, $D_{t}$ , from the asset price. We also discussed how this consideration comes into. play in the binomial model, as covered in Chapter 7. Whenever we subtract the present. value of the dividends over the life of the option, we are assuming that the dividends over. the life of the option are known. Hence, when we are interested in pricing an option in a continuous time world, the stochastic process followed by the asset price, Equation (13.1), can apply only to the value of the asset price minus the present value of the dividends. Without going through the derivation again, we will just say that the Black-Scholes-Merton formula for calls and puts requires a small adjustment, which is that the asset price, $S_{t}$ , must represent the asset price minus the present value of the dividends.

There is one other common adjustment for dividends, which is to assume that dividends are paid continuously and that the aggregate annual rate is expressed as $\delta$ , which is interpreted as the continuously compounded annual dividend yield. This adjustment is, more or less, an approximation, because no stock pays dividends continuously, but index options in which the underlying index contains mostly dividend-paying stocks could be reasonably approximated with this method. This is because some stocks in the index pay dividends on one day and some on other days. On a given day if a single stock pays dividends, then the index is paying a dividend. Though there does tend to be some dividend clustering in months and days of the week, there is still a modest degree of dispersion of dividends, and the method is widely used for index options. In that case, the Black-Scholes-Merton model and all of the dividend-adjusted boundary conditions that we covered in Chapter 2 will have $S_{t}e^{-\delta\tau}$ used instead of $S_{t}$

Finally, we should add that some options are on physical assets that incur storage costs, which are sometimes called holding or carrying costs. For example, oil is very expensive to store. Thus, while oil is being held, there is not only the loss of revenue from interest tied up in the oil, which is captured by the risk-free rate, but there is also an additional cost that represents out-of-pocket expense of storing the oil. In this case, there should be a further adjustment downward of the asset price by the present value of these costs.

We now turn to exploring selected limiting results for the Black-Scholes-Merton model.
