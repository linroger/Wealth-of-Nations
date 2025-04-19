---
tags:
  - black_scholes_merton_model
  - girsanov_theorem
  - greeks
  - option_pricing
  - volatility
aliases:
  - Chapter 14
  - Girsanov
  - Preview
  - Recap
key_concepts:
  - Calculus derivatives
  - Extended Greeks
  - Girsanov's theorem
  - Option value sensitivities
  - Risk-neutral measure
---

# 14.11 RECAP AND PREVIEW

In this chapter, we derived the calculus derivatives of the Black-Scholes-Merton model to obtain the Greeks, which are the sensitivities of the option value to the factors that go into the models. We further illustrate selected sensitivities of Greeks to changes in the asset price, volatility, and time to expiration. Finally, we introduce elasticities as well as selected extended Greeks.

In Chapter 15, we examine a mathematical result known as Girsanov's theorem and. show how it establishes our ability to derive the model under the risk-neutral or martingale measure.

TABLE 14.2 Extended Greek Names or Definitions


<html><body><table><tr><td>Parameter</td><td>S</td><td>t</td><td></td><td>r</td><td>X</td><td>8</td></tr><tr><td colspan="7">First-Order Derivatives</td></tr><tr><td>Value (O)</td><td>dOos Delta (4)</td><td>4e0e Theta (0)</td><td>dO0o Vega (v)</td><td>dOdr Rho (p)</td><td>dOdx</td><td>0008</td></tr><tr><td>Elasticity</td><td>O%S% Omega (Ω2)</td><td>%%0</td><td>0%%</td><td>O%r%</td><td>0%X%</td><td>0%8%</td></tr><tr><td></td><td></td><td>Selected Second-Order Derivatives</td><td></td><td></td><td></td><td></td></tr><tr><td>Delta (4)</td><td>Gamma (F)</td><td>Charm</td><td>04000 Vanna</td><td>040r</td><td></td><td></td></tr><tr><td>Theta (0)</td><td></td><td>1e00</td><td>000o Veta</td><td>000r</td><td>000X</td><td>0000</td></tr><tr><td>Vega (v)</td><td></td><td></td><td>dvdo Vomma</td><td>dvdr Ver</td><td>dvdX</td><td>dv08</td></tr><tr><td>Rho (p) dOdx</td><td></td><td></td><td></td><td>0pdr</td><td>dpdX</td><td>0p08</td></tr><tr><td>000o0</td><td></td><td></td><td></td><td></td><td>(0OdX)ax</td><td>(0O0x)08 (0008)08</td></tr><tr><td></td><td>Selected Third-Order Derivatives</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Gamma(F） dIoS</td><td>ordt</td><td></td><td>ordo</td><td>ordr</td><td>drax</td><td>0r08</td></tr><tr><td></td><td>Speed</td><td>Color 40 (4000)</td><td>Zomma</td><td></td><td></td><td></td></tr><tr><td>4e00 Vomma</td><td></td><td></td><td>(00ot)do dVommado</td><td>(00ot)dr dVomma0r</td><td>(00dt)ax dVommadX</td><td>(00dt)08</td></tr><tr><td></td><td></td><td></td><td>Ultima</td><td></td><td></td><td>dVomma08</td></tr><tr><td>0pdr</td><td></td><td></td><td></td><td>(0pdr)0r</td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>(0pdr)0X</td><td>(0pdr)08</td></tr></table></body></html>

# QUESTIONS AND PROBLEMS

1 Derive the call and put theta for a stock that pays a continuous dividend yield, $\delta$
2  Prove the following relationships for stocks with a dividend yield,. $\delta$

$$
\begin{array}{l}{{n(d_{1})=\displaystyle\frac{X e^{-r T}n(d_{2})}{S e^{-\delta T}}\mathrm{or}}}\ {{{}}}\ {{n(d_{2})=\displaystyle\frac{S e^{-\delta T}n(d_{1})}{X e^{-r T}}.}}\end{array}
$$

3 Derive the partial derivative of the call price with respect to the dividend yield, $\delta$

4  One of the most important cross-partial derivatives is vanna, the partial derivative of delta with respect to the volatility, because delta is key to risk management and volatility is not constant in practice. Derive the vanna for both calls and puts on a dividend paying stock with yield, $\delta$

$$
V a n n a_{c}=\frac{\partial\Delta_{c}}{\partial\sigma}=\frac{\partial}{\partial\sigma}e^{-\delta\tau}N\big(d_{1}\big)
$$

5 Derive $\partial c/\partial X$ for a stock paying a dividend yield, $\delta$

# NOTES

1. Vega is not a Greek word and the symbol typically used is the Greek nu because it looks similar to $\nu$ for volatility. Thus, it has come to be used as one of the option Greeks.

2. It is also possible to differentiate with respect to the exercise price. One would obtain $\partial c/\partial X=$ $-e^{-r_{c}\tau}N(d_{2})$ , which is negative. Because the exercise price does not change, however, this value has no name and is rarely needed. One case in which it has been used is in extracting the risk-neutral density implied by the option price. It is fairly easy to see how this is done. Note that the cumulative density is in the formula for the partial with respect to X. This implies that the density itself can be extracted. By using a sample of the prices of options that vary only by slightly different exercise prices, one can infer the density that implies the option price.

# Girsanov's Theorem in Option Pricing

t this point we have already derived the Black-Scholes-Merton model. Therefore, it are some additional results that are useful to understand to gain a better perspective on this model as well as give you the tools to create your own models. In this chapter, we cover one of those results, which is called Girsanov's theorem. Good references on this material are Karatzas and Shreve (1991) and Neftci (2000).

Girsanov's theorem appears to be a somewhat complex rule that at best provides limited marginal value if one already understands derivative pricing. Indeed, it is quite possible to obtain a solid understanding of derivative pricing without encountering Girsanov's. theorem. Nowhere did it appear in the literature on derivatives for many years, despite many exceptionally powerful advances developed by financial economists. Yet Girsanov's theorem provides the foundation for the mathematical rigor that underlies derivative pricing. Unfortunately, Girsanov's theorem in its raw form provides virtually no intuition and is rarely, if ever, presented with any economic insights. In short, mathematicians often approach the derivative pricing problem in their own ways, one being the application of Girsanov's theorem, and financial economists approach it in other ways. That these two. groups arrive at the same answer is not surprising, but they speak different languages and travel different routes. Here we cause them to converge. The material is admittedly more mathematical than financial, but that is because the readership of this book is likely to be more financial than mathematical and is more in need of seeing the mathematics and being reminded of when the mathematicians are saying something that a financial economist recognizes.
