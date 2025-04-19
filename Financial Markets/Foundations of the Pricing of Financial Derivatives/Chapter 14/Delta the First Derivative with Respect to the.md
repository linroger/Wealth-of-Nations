---
tags:
  - black_scholes_merton
  - delta
  - derivative
  - hedge_ratio
  - option_pricing
aliases:
  - Delta
  - Option Delta
key_concepts:
  - Black-Scholes-Merton model
  - Change in option price
  - 'Delta: price derivative'
  - Hedge ratio
  - Underlying price change
---

# 14.1 DELTA: THE FIRST DERIVATIVE WITH RESPECT TO THE UNDERLYING PRICE

This measure is called the delta. We take the derivative of the call price with respect to the underlying price,

$$
\begin{array}{r l r}{\lefteqn{\frac{\partial c}{\partial S}=S\frac{\partial N\left(d_{1}\right)}{\partial S}+N(d_{1})-X e^{-r_{c}\tau}\frac{\partial N\left(d_{2}\right)}{\partial S}}}\ &{}&{=S\frac{\partial N\left(d_{1}\right)}{\partial d_{1}}\frac{\partial d_{1}}{\partial S}+N(d_{1})-X e^{-r_{c}\tau}\frac{\partial N\left(d_{2}\right)}{\partial d_{2}}\frac{\partial d_{2}}{\partial S}.}\end{array}
$$

Substituting from Equations (14.3), (14.4), and (14.10), we obtain

$$
\frac{\partial c}{\partial S}=N(d_{1})+S n\left(d_{1}\right)\frac{1}{S\sigma\sqrt{\tau}}-X e^{-r_{c}\tau}n(d_{2})\frac{1}{S\sigma\sqrt{\tau}}.
$$

Finally, based on Equation (14.6) we note that the last two terms cancel, thus the call option delta is

$$
\Delta_{c}=\frac{\partial c}{\partial S}=N\big(d_{1}\big).
$$

The delta expresses the instantaneous change in the option price for a change in the under-.
lying price. Because $N(d_{1})$ is a probability, its value is between O and 1. In the derivation.
of the Black-Scholes-Merton model, delta is also the hedge ratio, representing the number of units of the asset required to offset one unit of the option when the underlying price.
changes in continuous time.
