---
tags:
  - '#black_scholes_merton_model'
  - '#option_value_derivatives'
  - '#partial_derivatives'
  - '#rho'
  - '#risk_free_rate_sensitivity'
  - '#vega'
  - '#volatility_sensitivity'
---
# 14.5 SELECTED OTHER PARTIAL DERIVATIVES OF THE BLACK-SCHOLES-MERTON MODEL

In addition, we may be interested in how the option value varies with the volatility and risk-free rate. Note that the Black-Scholes-Merton model assumes that the volatility and the risk-free rate are constant. Thus, there is an element of incoherence to these calculations. Remember, however, that this is a financial model and as such will only ever be an approximation to the behavior of the underlying asset. We also know from empirical observation that both the volatility and risk-free rate often vary significantly over time.. Thus, we wish to take their derivatives. As previously noted, the volatility and risk-free rate are assumed to not vary, but their partial derivatives show the sensitivity of the option price to different values of the volatility and interest rate. This is not the same as allowing. them to vary within the model, but it is better than making no such adjustment. Models in which these input values vary do exist, but they are far more complex and face the difficult challenge of finding a way to hedge away their risk so that the final solution meets the risk-neutrality condition.

# 14.5.1 Vega: The Partial Derivative with Respect to the Volatility

If we differentiate the call price with respect to the volatility, $\sigma$ , we get

$$
\frac{\partial c}{\partial\sigma}=S\frac{\partial N(d_{1})}{\partial d_{1}}\frac{\partial d_{1}}{\partial\sigma}-X e^{-r_{c}\tau}\frac{\partial N(d_{2})}{\partial d_{2}}\frac{\partial d_{2}}{\partial\sigma}.
$$

Note that $\partial d_{2}/\partial\sigma=\partial d_{1}/\partial\sigma-\sqrt{\tau}$ and substituting from Equations (14.3) and (14.4), we have

$$
\frac{\partial c}{\partial\sigma}=S n\left(d_{1}\right)\frac{\partial d_{1}}{\partial\sigma}-X e^{-r_{c}\tau}n(d_{2})\left(\frac{\partial d_{1}}{\partial\sigma}-\sqrt{\tau}\right).
$$

Substituting from Equation (14.6) for $n(d_{2})$ and cancelling terms, we obtain.

$$
\nu_{c}=\frac{\partial c}{\partial\sigma}=S\sqrt{\tau}n(d_{1}).
$$

This value is clearly positive and is known as the vega.1 Interestingly, the traditional inter-. pretation of vega in the BSM model is that it helps one on the upside and does not hurt on. the downside, but Chance (1994) shows that the effect is technically from the downside only and is strongly affected by the static and somewhat questionable assumption that the underlying is unaffected by the volatility change..

# 14.5.2 Rho: The Partial Derivative with Respect to the Risk-Free Rate

If we differentiate the call price with respect to the risk-free rate, we obtain

$$
\frac{\partial c}{\partial r}=S\frac{\partial N(d_{1})}{\partial d_{1}}\frac{\partial d_{1}}{\partial r}-\left[X e^{-r_{c}\tau}\frac{\partial N(d_{2})}{\partial d_{2}}\frac{\partial d_{2}}{\partial r}-\tau N\left(d_{2}\right)X e^{-r_{c}\tau}\right].
$$

Making various substitutions as in the previous examples, we simplify this equation to

$$
\rho_{c}={\frac{\partial c}{\partial r}}=X e^{-r_{c}\tau}\tau N\left(d_{2}\right).
$$

This expression, called rho, is clearly positive.2
