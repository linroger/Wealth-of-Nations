---
tags:
  - '#black_scholes_merton'
  - '#call_delta'
  - '#greeks'
  - '#leverage_factor'
  - '#omega'
  - '#option_elasticities'
  - '#option_pricing_model'
  - '#vega'
  - '#volatility'
---
# 14.9 ELASTICITIES

The Greeks presented here are simply partial derivatives. Thus, a call delta answers the question of how much a call price will increase for a small dollar change in the underlying asset. There is no adjustment for the absolute price level. In response to this problem, some have argued that various elasticities would be more informative.

For example, rather than report the call delta, it may be more informative to report the percentage change in the call price with respect to the percentage change in the underlying asset. Thus, the elasticity of the call price to the asset price, known as omega, is.

$$
\Omega_{c}=\frac{\partial c/c}{\partial S/S}=\frac{\partial c}{\partial S}\frac{S}{c}=\Delta_{c}\frac{S}{c}.
$$

Note that elasticity is simply the first derivative, or delta, adjusted by what we call a leverage factor, $S/c$

Similar calculations could be performed on all the reported Greeks . For example, the elasticity of a call price with respect to volatility is

$$
\frac{\partial c/c}{\partial\sigma/\sigma}=\frac{\partial c}{\partial\sigma}\frac{\sigma}{c}=\Theta_{c}\frac{\sigma}{c}.
$$

We see that the reported elasticities could be significantly different from reported Greeks. Clearly, with the Greek formulas, we can easily compute the corresponding elasticities.

One well-known weakness of the Greeks and related elasticities is the lack of information regarding the different likelihoods of various parameter changes. For example, beyond the asset price, option prices are generally very sensitive to changes in volatilities. The Greeks do not address the likelihood of volatility increasing from $30\%$ $33\%$ Or a $10\%$ increase. Moreover, as partial derivatives, the Greeks are technically accurate only for infinitesimal changes. One way to address this issue is through simulation, a topic we take up in Chapter 23.

# 14.10 EXTENDED GREEKS OF THE BLACK-SCHOLES-MERTON OPTION PRICING MODEL

There are many more Greeks, corresponding to the many different partial and cross-partial derivatives. For example, one can differentiate the vega with respect to time, so as to determine how vega changes as the option approaches expiration. There are numerous possible combinations. Table 14.2 provides selected Greek names where known or otherwise brief syntax is given.
