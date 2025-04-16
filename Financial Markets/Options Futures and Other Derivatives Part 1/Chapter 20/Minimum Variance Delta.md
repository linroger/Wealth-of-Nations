---
tags:
  - '#black_scholes_merton'
  - '#delta_calculation'
  - '#equity_prices_volatility'
  - '#implied_volatility'
  - '#minimum_variance_delta'
  - '#option_pricing'
  - '#vega'
---
# 20.6 MINIMUM VARIANCE DELTA  

The formulas for delta and other Greek letters in Chapter 19 assume that the implied volatility remains the same when the asset price changes. This is not what is usually expected to happen. Consider, for example, a stock or stock index option.  

As explained in Section 20.3, there is a negative correlation between equity prices and volatility. The delta that takes this relationship between implied volatilities and equity. prices into account is referred to as the minimum variance delta. It is:.  

$$
\Delta_{\mathrm{MV}}=\frac{\partial f_{\mathrm{BSM}}}{\partial S}+\frac{\partial f_{\mathrm{BSM}}}{\partial\sigma_{\mathrm{imp}}}\frac{\partial E(\sigma_{\mathrm{imp}})}{\partial S}
$$  

where $f_{\mathrm{BSM}}$ is the Black-Scholes-Merton price of the option, $\sigma_{\mathrm{imp}}$ is the option's implied volatility, $E(\sigma_{\mathrm{imp}})$ denotes the expectation of $\sigma_{\mathrm{imp}}$ as a function of the equity price, $S.$ This gives  

$$
\Delta_{\mathrm{MV}}=\Delta_{\mathrm{BSM}}+\mathcal{V}_{\mathrm{BSM}}\frac{\partial E(\sigma_{\mathrm{imp}})}{\partial S}
$$  

where $\Delta_{\mathrm{BSM}}$ and $\mathcal{V}_{\mathrm{BSM}}$ are the delta and vega calculated from the Black-Scholes-Merton (constant volatility) model. Because. $\mathcal{V}_{\mathrm{BSM}}$ is positive and, as we have just explained $\partial E(\sigma_{\mathrm{imp}})/\partial S$ is negative, the minimum variance delta is less than the Black-ScholesMerton delta.  
