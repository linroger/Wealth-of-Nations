---
tags:
  - '#black_scholes_merton_model'
  - '#call_options'
  - '#delta'
  - '#dividend_adjusted_greeks'
  - '#dividend_adjustment'
  - '#put_options'
  - '#sensitivity_analysis'
---
# 14.7 INCORPORATING DIVIDENDS

In the case of continuous dividends, recall the Black-Scholes-Merton model is adjusted where $S^{\prime}=e^{-\delta\tau}S$ and can be expressed as

$$
\begin{array}{l}{{c=S^{\prime}N(d_{1})-X e^{-r_{c}\tau}N(d_{2})}}\ {{\displaystyle p=X e^{-r_{c}\tau}N(-d_{2})-S^{\prime}N(-d_{1})}}\ {{d_{1}=\frac{\ln\left(S^{\prime}/X\right)+\left(r_{c}+\sigma^{2}/2\right)\tau}{\sigma\sqrt\tau}}}\ {{d_{2}=d_{1}-\sigma\sqrt\tau.}}\end{array}
$$

IABLE 14.1 Dividend-Adjusted Greeks


<html><body><table><tr><td>Greek</td><td>Calls</td><td>Puts</td></tr><tr><td>Delta</td><td>e- N(d)</td><td>-e-N(-d)</td></tr><tr><td>Gamma</td><td>e-tn(d) SoVt</td><td>Same as call</td></tr><tr><td>Theta</td><td>oS'n(d) - rXe-r N(d2) 2√t +8S'N(d)</td><td>oS'n(d) + rXe-rN(-d2) 7 -8S'N(-d)</td></tr><tr><td>Vega</td><td>S√tn(d)</td><td>Same as call</td></tr><tr><td>Rho</td><td>tXe-r N(d2)</td><td>-tXe-rN(-d2)</td></tr></table></body></html>

For example, the dividend-adjusted deltas are simply

$$
\Delta_{c}={\frac{\partial c}{\partial S}}={\frac{\partial c}{\partial S^{\prime}}}{\frac{\partial S^{\prime}}{\partial S}}=N(d_{1})e^{-\delta\tau}{\mathrm{~and~}}
$$

$$
\Delta_{\mathstrut p}={\frac{\partial\slash p}{\partial\cal S}}={\frac{\partial\slash p}{\partial\cal S^{\prime}}}{\frac{\partial\cal S^{\prime}}{\partial\cal S}}=-{\cal N}(-d_{1})e^{-\delta\tau}.
$$

Table 14.1 presents the five dividend-adjusted Greeks for calls and puts.

The values of these Greeks are sensitive to changes in other parameters. We explore some of these sensitivities in Section 14.8..
