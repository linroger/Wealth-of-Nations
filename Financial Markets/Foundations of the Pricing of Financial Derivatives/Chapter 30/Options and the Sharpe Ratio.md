---
tags:
  - call_option
  - option_pricing
  - risk_premium
  - sharpe_ratio
  - volatility
aliases:
  - Options Performance
  - Sharpe Ratio
key_concepts:
  - Asset risk premium
  - Option Sharpe ratio
  - Option mispricing
  - Risk-free rate
  - Sharpe ratio definition
---

# 30.5 OPTIONS AND THE SHARPE RATIO

A widely used measure of investment performance is the Sharpe ratio. For a portfolio with return $R_{p}$ and volatility $\sigma_{p}$ , the Sharpe ratio is

$$
\mathrm{Sharpe}_{\phi}=\frac{R_{\phi}-r}{\sigma_{p}}.
$$

The Sharpe ratio measures the return in excess of the risk-free rate, which is the numerator,. relative to the total risk, which is the denominator. Using our measures of return and. volatility for an option, Equations (30.9) and (30.19), the Sharpe ratio for a call option is

$$
{\begin{array}{r l}&{{\mathrm{Sharpe}}_{c}={\cfrac{R_{c}-r}{\sigma_{c}}}}\ &{\qquad={\cfrac{r+\left({\frac{\Delta S}{S}}-r\right)b\left({\frac{S}{c}}\right)-r}{b\left({\frac{S}{c}}\right)\sigma_{s}}}}\ &{\qquad={\cfrac{\left({\frac{\Delta S}{S}}-r\right)}{\sigma_{s}}}.}\end{array}}
$$

In other words, the Sharpe ratio for an option is simply the Sharpe ratio for the asset. This result is likely to surprise some, but an explanation is simple. The Sharpe ratio measures whether an investment provided a risk premium in excess of the appropriate risk premium for its level of risk. If the option is correctly priced relative to its underlying asset, it cannot provide a risk premium beyond that already provided by the asset. The option merely leverages the risk premium of the asset. And the leverage used by the option, although an advantage in augmenting the return, is an offsetting disadvantage in augmenting the risk. That is, the Sharpe ratio is a proportional measure of performance. If the numerator and denominator change by the same proportion, the Sharpe ratio cannot change.

Of course, if the option is mispriced, then the arbitrage linkage between option and asset that enabled us to obtain the above results is broken. An option would then provide a form of excess return, and the Sharpe ratio of the option would exceed that of the asset.5
