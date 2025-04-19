---
tags:
  - closed_form_valuation
  - continuous_time
  - discrete_time
  - multi_period_valuation
  - state_price_deflator
aliases:
  - Multi-Period Models
  - Multi-Period Valuation
key_concepts:
  - Closed-form dividend valuation
  - Continuous-time valuation
  - Discrete-time framework
  - Price-dividend ratio
  - Risk-adjusted discount factor
---

# 4.4 Multi-period valuation models  

This section gives some examples of concrete assumptions on the state-price deflator and the dividends that will lead to a closed-form expression for the present value of the dividends.  

Here is a simple example of closed-form valuation of a single terminal dividend of $D_{T}$ . Suppose that $D_{T}=\mathrm{E}_{t}[D_{T}]e^{X}$ for a lognormally distributed random variable. $X$ . To ensure $\operatorname{E}_{t}[e^{X}]=1$ , we need $X\sim N(-\textstyle{\frac{1}{2}}\sigma_{X}^{2},\sigma_{X}^{2})$ , cf. Theorem B.2 in Appendix B. Also assume that $\zeta_{T}=\zeta_{t}e^{Y}$ , where $X$ and $Y$ are jointly normally distributed with correlation. $\rho$ and $Y\sim N(\mu_{Y},\sigma_{Y}^{2})$ . Then the present. value of the dividend is.  

$$
P_{t}=\operatorname{E}_{t}\left[D_{T}{\frac{\zeta_{T}}{\zeta_{t}}}\right]=\operatorname{E}_{t}\left[\operatorname{E}_{t}[D_{T}]e^{X}e^{Y}\right]=\operatorname{E}_{t}[D_{T}]\operatorname{E}_{t}\left[e^{X+Y}\right].
$$  

Since $\begin{array}{r}{X+Y\sim N(-\frac{1}{2}\sigma_{X}^{2}+\mu_{Y},\sigma_{X}^{2}+\sigma_{Y}^{2}+2\rho\sigma_{X}\sigma_{Y})}\end{array}$ , we get  

$$
\begin{array}{c}{{\displaystyle\mathrm{E}_{t}\left[e^{X+Y}\right]=\exp\left\{-\frac{1}{2}\sigma_{X}^{2}+\mu_{Y}+\frac{1}{2}\left(\sigma_{X}^{2}+\sigma_{Y}^{2}+2\rho\sigma_{X}\sigma_{Y}\right)\right\}}}\ {{\mathrm{}=\exp\left\{\mu_{Y}+\frac{1}{2}\sigma_{Y}^{2}+\rho\sigma_{X}\sigma_{Y}\right\}}}\end{array}
$$  

and thus  

$$
P_{t}=\mathrm{E}_{t}[D_{T}]\exp\left\{\mu_{Y}+\frac{1}{2}\sigma_{Y}^{2}+\rho\sigma_{X}\sigma_{Y}\right\}.
$$  

The exponential term on the right-hand side of that equation is the appropriately risk-adjusted discount factor for the given dividend.  

In a continuous-time setting the distributional assumption on $Y=\ln(\zeta_{T}/\zeta_{t})$ is satisfied if the. market price of risk vector is a constant. $\lambda$ and the short-term risk-free rate is a constant. $r^{f}$ since then  

$$
Y=-\left(r^{f}+\frac{1}{2}\|\lambda\|^{2}\right)(T-t)-\int_{t}^{T}\lambda^{\top}d z_{u}\sim N\left(-\left(r^{f}+\frac{1}{2}\|\lambda\|^{2}\right)(T-t),\|\lambda\|^{2}(T-t)\right),
$$  

in which case we can rewrite the present value as  

$$
P_{t}=\mathrm{E}_{t}[D_{T}]\exp\left\{-r^{f}(T-t)+\rho\sigma_{X}\sigma_{Y}\right\}.
$$  

If we substitute in $O Y$ and write $\sigma_{X}^{2}\:=\:\sigma_{d}^{2}(T-t)$ , where $\sigma_{d}^{2}$ is the annualized variance of the dividend, we get a present value of  

$$
P_{t}=\operatorname{E}_{t}[D_{T}]\exp\left\{-r^{f}(T-t)+\rho\sigma_{d}\|\lambda\|(T-t)\right\}=\operatorname{E}_{t}[D_{T}]\exp\left\{-(r^{f}-\rho\sigma_{d}\|\lambda\|)(T-t)\right\}.
$$  

The expected dividend is discounted with a risk-adjusted percentage interest rate, which equals the risk-free rate minus $\rho\sigma_{d}\|\boldsymbol{\lambda}\|$  

# 4.4.1 Discrete-time valuation  

Consider a discrete-time multi-period framework and assume that the state-price deflator $\zeta=\left(\zeta_{t}\right)$ satisfies  

$$
\begin{array}{r}{\mathrm{E}_{t}\left[\frac{\zeta_{t+1}}{\zeta_{t}}\right]=\mu_{\zeta},\quad\mathrm{Var}_{t}\left[\frac{\zeta_{t+1}}{\zeta_{t}}\right]=\sigma_{\zeta}^{2}}\end{array}
$$  

for each $t=0,1,2,\ldots,T-1$ . In particular, $\operatorname{E}_{t}\left[(\zeta_{t+1}/\zeta_{t})^{2}\right]=\sigma_{\zeta}^{2}+\mu_{\zeta}^{2}$ . Consider an uncertain stream of dividends $D=\left(D_{t}\right)$ , where the dividend growth rate is given by  

$$
\frac{D_{t+1}}{D_{t}}=a+b\frac{\zeta_{t+1}}{\zeta_{t}}+\varepsilon_{t+1},\quad t=0,1,\ldots,T-1,
$$  

where $\varepsilon_{1},\ldots,\varepsilon_{T}$ are independent with $\mathrm{E}_{t}[\varepsilon_{t+1}]=0$ and $\mathrm{E}_{t}[\varepsilon_{t+1}\zeta_{t+1}]=0$ for all $t$  

First note that  

$$
\begin{array}{c}{\displaystyle\mathrm{E}_{t}\left[\frac{D_{t+1}}{D_{t}}\frac{\zeta_{t+1}}{\zeta_{t}}\right]=\mathrm{E}_{t}\left[\left(a+b\frac{\zeta_{t+1}}{\zeta_{t}}+\varepsilon_{t+1}\right)\frac{\zeta_{t+1}}{\zeta_{t}}\right]=a\mathrm{E}_{t}\left[\frac{\zeta_{t+1}}{\zeta_{t}}\right]+b\mathrm{E}_{t}\left[\left(\frac{\zeta_{t+1}}{\zeta_{t}}\right)^{2}\right]}\ {=a\mu_{\zeta}+b\left(\sigma_{\zeta}^{2}+\mu_{\zeta}^{2}\right)\equiv A}\end{array}
$$  

for every $t=0,1,\ldots,T-1$ . Together with the Law of Iterated Expectations this implies that for each $s>t$  

$$
\begin{array}{r l}&{\mathrm{E}_{t}\left[\frac{D_{s}}{D_{t}}\frac{\zeta_{s}}{\zeta_{t}}\right]=\mathrm{E}_{t}\left[\frac{D_{s-1}}{D_{t}}\frac{\zeta_{s-1}}{\zeta_{t}}\frac{D_{s}}{D_{s-1}}\frac{\zeta_{s}}{\zeta_{s-1}}\right]}\ &{\qquad=\mathrm{E}_{t}\left[\frac{D_{s-1}}{D_{t}}\frac{\zeta_{s-1}}{\zeta_{t}}\mathrm{E}_{s-1}\left[\frac{D_{s}}{D_{s-1}}\frac{\zeta_{s}}{\zeta_{s-1}}\right]\right]}\ &{\qquad=A\mathrm{E}_{t}\left[\frac{D_{s-1}}{D_{t}}\frac{\zeta_{s-1}}{\zeta_{t}}\right]}\ &{\qquad=\dots}\ &{\qquad=A^{s-t}.}\end{array}
$$  

The price-dividend ratio of the asset is therefore  

$$
\begin{array}{l}{{\displaystyle{\frac{P_{t}}{D_{t}}}=\mathrm{E}_{t}\left[\sum_{s=t+1}^{T}\frac{D_{s}}{D_{t}}\frac{\zeta_{s}}{\zeta_{t}}\right]=\sum_{s=t+1}^{T}\mathrm{E}_{t}\left[\frac{D_{s}}{D_{t}}\frac{\zeta_{s}}{\zeta_{t}}\right]}}\ {{\displaystyle~=\sum_{s=t+1}^{T}A^{s-t}=A+A^{2}+\cdot\cdot\cdot+A^{T-t}}}\ {{\displaystyle~=\frac{A}{1-A}\left(1-A^{T-t}\right).}}\end{array}
$$  

The price is thus  

$$
P_{t}=D_{t}\frac{A}{1-A}\left(1-A^{T-t}\right).
$$  

If $|A|<1$ and you let $T\to\infty$ , i.e. assume dividends continue in all future, you get  

$$
P_{t}=D_{t}\frac{A}{1-A}.
$$  

In particular, the price-dividend ratio is a constant.1  

# 4.4.2 Continuous-time valuation: The PDE approach  

4.4.3 Continuous-time valuation: Affine models  
