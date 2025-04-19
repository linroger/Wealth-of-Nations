---
linter-yaml-title-alias: 1. BLACK-SCHOLES MODEL OF OPTION PRICING
title: 1. BLACK-SCHOLES MODEL OF OPTION PRICING
tags:
  - black_scholes_model
  - call_option
  - delta_hedging
  - implied_volatility
  - option_pricing
aliases:
  - BSM
  - Black-Scholes
  - Option Pricing Model
key_concepts:
  - Delta hedging
  - Implied volatility calculation
  - Interest rate, maturity
  - Stock price, strike price
  - Stock volatility parameter
---

# 1. BLACK-SCHOLES MODEL OF OPTION PRICING
## 1.1. PARAMETERS
1. Stock price: 𝑆
2. Strike price: 𝐾
3. Interest rate on risk-free asset (continuously compounded): 𝑟
4. Maturity: 𝑇
5. Stock volatility: 𝜎
## 1.2. OPTIMAL PRICING FORMULA

1. Delta hedging.$$\begin{array}{c}{{d_{1}(S,K,T,r,\sigma)=\begin{array}{c}{{\ln\left[\frac{S}{K}\right]+\left(r+\frac{\sigma^{2}}{2}\right)\cdot T}}\\ {{\sigma\cdot\sqrt{T}}}\end{array}}}\\ {{d_{2}(S,K,T,r,\sigma)=d_{1}-\sigma\cdot\sqrt{T}}}\end{array}$$
2. Standard normal cumulative distribution function.$$\Phi(x):={\frac{1}{\sigma\cdot{\sqrt{2\pi}}}}\cdot\int_{-\infty}^{x}\exp\left(-{\frac{1}{2}}\cdot u^{2}\right)d u$$
3. Call option price.$$c=S\cdot\Phi\big(d_{1}(S,K,T,r,\sigma)\big)-K\cdot\exp(-r\cdot T)\cdot\Phi\big(d_{2}(S,K,T,r,\sigma)\big)$$
4. Put option price.$$p=-S\cdot\Phi\bigl(-d_{1}(S,K,T,r,\sigma)\bigr)+K\cdot\exp(-r\cdot T)\cdot\Phi\bigl(-d_{2}(S,K,T,r,\sigma)\bigr)$$

## 1.2.1. IMPLIED VOLATILITY

1. Suppose we observe option prices$(𝑐, 𝑝)$.
2. **Question**: What is the volatility parameter$𝜎$*implied* by the Black-Scholes model?
3. **Answer**: It is the volatility parameter that solves a non-linear equation.$$\begin{aligned}c&=S*\Phi\big(d_1(S,K,T,r,\sigma_c^*)\big)-K*e^{−𝑟 * 𝑇}*\Phi\big(d_2(S,K,T,r,\sigma_c^*)\big)\\\\p&=-S*\Phi\big(-d_1(S,K,T,r,\sigma_p^*)\big)+K*e^{−𝑟 * 𝑇} *\Phi\big(-d_2(S,K,T,r,\sigma_p^*)\big)\end{aligned}$$
5. Use non-linear equation solve function to solve for implied volatility values ($𝜎_{𝑐}^∗, 𝜎_{𝑝}^∗$).