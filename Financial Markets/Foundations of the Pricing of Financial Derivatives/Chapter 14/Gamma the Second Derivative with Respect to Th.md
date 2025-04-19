---
tags:
  - delta
  - derivative
  - gamma
  - option_greeks
  - option_pricing
aliases:
  - Gamma
  - Rate of Change
  - Second Derivative
key_concepts:
  - First derivative of delta
  - Instantaneous rate of change
  - Second derivative of price
---

# 14.2 GAMMA: THE SECOND DERIVATIVE WITH RESPECT TO THE UNDERLYING PRICEA

The second derivative with respect to the underlying price is the gamma and is obtained as follows:

$$
\begin{array}{c}{\displaystyle\Gamma_{c}=\frac{\partial\left(\frac{\partial c}{\partial S}\right)}{\partial S}=\frac{\partial^{2}c}{\partial S^{2}}=\frac{\partial N\left(d_{1}\right)}{\partial S}}\ {\displaystyle=\frac{\partial N(d_{1})}{\partial d_{1}}\frac{\partial d_{1}}{\partial S}=\frac{n(d_{1})}{S\sigma\sqrt{\tau}}.}\end{array}
$$

This value is called the gamma. We can indeed think of it as the second derivative with respect to the asset price or we can think of it as the first derivative of the delta. Thus, it. represents the instantaneous rate of change of the delta as the underlying price changes.
