---
tags:
  - ccapm
  - consumption_based_model
  - crra_utility
  - risk_free_rate
  - sharpe_ratio
aliases:
  - Multi-Period CCAPM
  - Simple CCAPM
key_concepts:
  - CRRA utility
  - Constant Sharpe ratio
  - Lognormal consumption
  - Representative individual
  - Risk-free return
---

# 8.4 The simple multi-period CCAPM  

A large part of the asset pricing literature makes (not always explicitly stated, unfortunately) the following additional assumptions:  

1. the economy has a representative individual with CRRA time-additive utility, i.e. $u(C)=$ $\frac{1}{1-\gamma}C^{1-\gamma}$  

2. future aggregate consumption is lognormally distributed.  

In the discrete-time version of the model, we can proceed as in version 2 of the one-period model. The first assumption leads to a marginal rate of substitution given by  

$$
{\frac{u^{\prime}(C_{t+1})}{u^{\prime}(C_{t})}}=\left({\frac{C_{t+1}}{C_{t}}}\right)^{-\gamma}=\exp\left\{-\gamma\ln\left({\frac{C_{t+1}}{C_{t}}}\right)\right\}.
$$  

By the second assumption, $\ln\left(C_{t+1}/C_{t}\right)\sim N(\bar{g},\sigma_{C}^{2})$ , and hence  

$$
\operatorname{E}_{t}\left[{\frac{u^{\prime}(C_{t+1})}{u^{\prime}(C_{t})}}\right]=\operatorname{E}_{t}\left[\exp\left\{-\gamma\ln\left({\frac{C_{t+1}}{C_{t}}}\right)\right\}\right]=\exp\left\{-\gamma{\bar{g}}+{\frac{1}{2}}\gamma^{2}\sigma_{C}^{2}\right\}
$$  

and  

$$
{\frac{\sigma_{t}\left(u^{\prime}(C_{t+1})/u^{\prime}(C_{t})\right)}{\operatorname{E}_{t}\left[u^{\prime}(C_{t+1})/u^{\prime}(C_{t})\right]}}={\sqrt{e^{\gamma^{2}\sigma_{C}^{2}}-1}}\approx\gamma\sigma_{C}.
$$  

According to (8.17), the gross risk-free return over the period from $t$ to $t+1$ is then given by  

$$
R_{t}^{f}=e^{\delta}\left(\mathrm{E}_{t}\left[\left(C_{t+1}/C_{t}\right)^{-\gamma}\right]\right)^{-1}=\exp\left\{\delta+\gamma\bar{g}-{\frac{1}{2}}\gamma^{2}\sigma_{C}^{2}\right\}
$$  

so that the continuously compounded risk-free rate of return becomes  

$$
r_{t}^{f}\equiv\ln R_{t}^{f}=\delta+\gamma\bar{g}-\frac{1}{2}\gamma^{2}\sigma_{C}^{2}.
$$  

From (8.19) we conclude that in the simple model the excess expected gross return on a risky asset is  

$$
\begin{array}{c}{{\displaystyle\mathrm{E}_{t}\left[R_{i,t+1}\right]-R_{t}^{f}\approx-\gamma\sigma_{C}\rho_{t}\left[R_{i,t+1},\left(\frac{C_{t+1}}{C_{t}}\right)^{-\gamma}\right]\sigma_{t}\left[R_{i,t+1}\right]}}\ {{\approx\gamma\sigma_{C}\rho_{t}\left[R_{i,t+1},\displaystyle\frac{C_{t+1}}{C_{t}}\right]\sigma_{t}\left[R_{i,t+1}\right],}}\end{array}
$$  

where the last expression follows from a first-order Taylor approximation as in Section 8.2.2. If. we further assume that the future asset price and the future consumption level are simultaneously lognormally distributed, we are back in version 3 of the one-period model so that we get.  

$$
\mathrm{E}_{t}[\ln R_{i,t+1}]-\ln R_{t}^{f}+{\frac{1}{2}}\mathrm{Var}_{t}[\ln R_{i,t+1}]=\gamma\sigma_{C}\rho_{t}\left[\ln R_{i,t+1},\ln\left({\frac{C_{t+1}}{C_{t}}}\right)\right]\sigma_{t}\left[\ln R_{i,t+1}\right]
$$  

or, equivalently,  

$$
\ln\left(\mathrm{E}_{t}[R_{i,t+1}]\right)-\ln R_{t}^{f}=\gamma\sigma_{C}\rho_{t}\left[\ln R_{i,t+1},\ln\left(\frac{C_{t+1}}{C_{t}}\right)\right]\sigma_{t}\left[\ln R_{i,t+1}\right].
$$  

In the formulas above the mean $g$ and variance $\sigma^{2}$ of consumption growth can vary over time, but in the stationary case where both are constant we see that the risk-free interest rate must also be constant. Furthermore, a risky asset with a constant correlation with consumption growth will have a constant Sharpe ratio $\left(\mathrm{E}_{t}\left[R_{i,t+1}\right]-R_{t}^{f}\right)/\sigma_{t}[R_{i,t+1}]$ . If the standard deviation of the return is constant, the expected excess rate of return will also be constant.  

In the continuous-time version of the stationary simple consumption-based model, the second assumption means that $\mu_{C t}$ and $\sigma_{C t}$ in the consumption process (8.21) are constant, i.e. consumption follows a geometric Brownian motion. It follows from (8.23) and (8.25) that the model with these assumptions generate a constant continuously compounded short-term risk-free interest rate Of  

$$
r^{f}=\delta+\gamma\mu_{C}-\frac{1}{2}\gamma(1+\gamma)\|\pmb{\sigma}_{C}\|^{2}
$$  

and a constant Sharpe ratio for asset $i$ given by  

$$
\frac{\mu_{i t}+\delta_{i t}-r^{f}}{\|\pmb{\sigma}_{i t}\|}=\gamma\rho_{i C}\|\pmb{\sigma}_{C}\|
$$  

if the asset has a constant correlation with consumption.  
