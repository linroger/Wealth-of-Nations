---
tags:
  - '#arithmetic_brownian_motion'
  - '#european_spread_call_option'
  - '#european_spread_put_option'
  - '#exercise_price'
  - '#geometric_brownian_motion'
  - '#risk_neutral_valuation'
  - '#spread_option_pricing'
  - '#spread_options'
---
# 17.6 SPREAD OPTIONS3

We now consider spread options where there is a nonzero exercise price. In this case, suppose we have a European spread call option in which at expiration the holder can exchange $\alpha_{2}$ units of asset 2 and receive $\alpha_{1}$ units of asset 1 but also must pay a prespecified. exercise price, X. We assume. $\alpha_{1}$ and $\alpha_{2}$ are both positive. A European spread put option in which at expiration the holder can exchange $\alpha_{1}$ units of asset 1 and receive. $\alpha_{2}$ units of. asset 2 but again has to pay a prespecified exercise price, $X$ Note that. $X$ can be positive. or negative. The payoffs at expiration are

$$
\begin{array}{r l}&{c_{T}=\operatorname*{max}\bigl(0,\alpha_{1}S_{1T}-\alpha_{2}S_{2T}-X\bigr)\mathrm{~and}}\ &{}\ &{\qquad\quad\phi_{T}=\operatorname*{max}\bigl(0,X-\alpha_{1}S_{1T}+\alpha_{2}S_{2T}\bigr).}\end{array}
$$

With spread options, neither asset plays the role of the exercise price. Thus, a spread option is a more complex exchange option with a known exercise price..

Pearson (1995), Carmona and Durrleman (2003, 2006), Li, Deng, and Zhou (2008), and others have offered approximations when solving for the spread option price when each asset follows geometric Brownian motion. Brooks and Cline (2015) provide a closed-form solution that also incorporates dividends. Based on the results in the previous section as well as the more complex terminal boundary condition, the spread option model based on geometric Brownian motion can be expressed as

$$
\begin{array}{l}{{\displaystyle c_{t}=\alpha_{1}S_{1t}e^{-\delta_{1}\tau}\int N\big[d_{1,1}(j)\big]n(j)d j-\alpha_{2}S_{2t}e^{-\delta_{2}\tau}}}\ {{\displaystyle\qquad-\infty\qquad}}\ {{\displaystyle\int N\big[d_{1,2}(j)\big]n(j)d j-X e^{-r_{c}\tau}\int N\big[d_{2}(j)\big]n(j)d j,}}\ {{\displaystyle\qquad-\infty\qquad}}\ {{\displaystyle p_{t}=c_{t}-\alpha_{1}S_{1t}e^{-\delta_{1}\tau}+\alpha_{2}S_{2t}e^{-\delta_{2}\tau}+X e^{-r_{c}\tau},}}\end{array}
$$

where

$$
n(j)=\frac{e^{\frac{-j^{2}}{2}}}{\sqrt{2\pi}},
$$

$$
\begin{array}{r}{N\big[d_{i}(j)\big]=\displaystyle\int_{-\infty}^{d_{i}(j)}\frac{e^{\frac{-k^{2}}{2}}}{\sqrt{2\pi}}d k,}\end{array}
$$

$$
\begin{array}{r}{d_{1,1}(j)=\frac{\ln\left[\frac{\pi\left(\kappa-\kappa_{1}\wedge\frac{\kappa_{2}}{\kappa}\right)\ln\frac{\kappa_{1}\kappa_{2}}{\kappa}\left(-\kappa+\frac{\kappa_{2}^{2}}{2}\right)+\mu\nu_{1}\sqrt{\kappa_{2}}}{\pi\left(\kappa-\kappa_{2}^{2}+\mu\nu_{1}\right)\frac{\kappa_{2}}{\kappa}\left(\kappa+2\sqrt{\kappa_{1}}\right)}\right]}{\sigma_{1}\sqrt{\kappa_{1}\left(1-\rho^{2}\right)}},}\ {d_{1,2}(j)=\frac{\ln\left[\frac{\pi\kappa_{1}\kappa_{1}}{\kappa+\kappa_{2}\kappa_{2}}\left(-\kappa^{2}+\mu\nu_{2}\right)\frac{\kappa_{2}\kappa_{1}}{\kappa}\right]}{\sigma_{1}\sqrt{\kappa_{2}\kappa_{2}}\left(\kappa-\kappa_{2}^{2}+\frac{\kappa_{2}^{2}}{2}\right)+\mu\nu_{1}\sqrt{\kappa_{1}}}\right],\mathrm{and}}\ {\prod_{s^{\prime}}\left[\frac{\pi\left(\kappa-\kappa_{1}\wedge\frac{\kappa_{2}}{\kappa}\right)}{\kappa}+\frac{\kappa_{2}\kappa_{1}}{2}\right],}\end{array}
$$

$$
\begin{array}{r}{d_{2}(j)=\frac{\ln\left[\frac{\alpha_{1}S_{1t}e^{\left(r_{c}-\delta_{1}-\frac{\sigma_{1}^{2}}{2}\right)\tau+\rho\sigma_{1}\sqrt{\tau}j}}{\sigma_{1}\sqrt{\tau(1-\delta_{2}-\frac{\sigma_{2}^{2}}{2})\tau+\sigma_{2}\sqrt{\tau}j}}\right]}{\sigma_{1}\sqrt{\tau(1-\rho^{2})}}.}\end{array}
$$

This solution is not an approximation like Pearson (1995), Carmona and Durrleman (2003, 2006), Li, Deng, and Zhou (2008) and others; rather, it is an exact result. It is still technically a double integral as the standard $N(d)$ function is itself an integral. In practice,. however, it is a single integral because of the existence of very accurate numerical approximations available to compute the standard $N(d)$ function. Fast solutions to single integral problems are widely available, particularly with fast and efficient computer languages such as R or $\mathrm{C}{+}{+}$

The solution in the case of arithmetic Brownian motion with geometric drift is much more straightforward. Note that the spread is normally distributed and is denoted as

$$
S P_{T}=\alpha_{1}S_{1T}-\alpha_{2}S_{2T}.
$$

Under risk-neutral valuation, we have

$$
E\big(S P_{T}\big)=\alpha_{1}S_{1t}e^{(r_{c}-\delta_{1})\tau}-\alpha_{2}S_{2t}e^{(r_{c}-\delta_{2})\tau}=S P_{t}e^{r_{c}\tau},
$$

where one measure of the current spread at $t$ is

$$
S P_{t}\equiv\alpha_{1}S_{1t}e^{-\delta_{1}\tau}-\alpha_{2}S_{2t}e^{-\delta_{2}\tau}.
$$

Let $\sigma_{S P}$ denote the standard deviation of changes in the spread. Thus, based on the Brownian motion (ABM) model, the spread option prices are.

$$
\begin{array}{r l}&{c_{t}=\left(S P_{t}-X e^{-r\tau}\right)N\left(d_{n}\right)+\sigma_{S P}\sqrt{\cfrac{{e^{r_{c}\tau}}-1}{2r_{c}}}n\left(d_{n}\right),}\ &{p_{t}=c_{t}-\alpha_{1}S_{1t}e^{-\delta_{1}\tau}+\alpha_{2}S_{2t}e^{-\delta_{2}\tau}+X e^{-r\tau},}\end{array}
$$

where

$$
\begin{array}{l}{{n\big(d_{n}\big)={\displaystyle\frac{e^{\displaystyle\frac{-d_{n}^{2}}{2}}}{\sqrt{2\pi}}},}}\ {{\qquadd_{n}}}\ {{N\big(d_{n}\big)=\displaystyle\int_{-\infty}^{}n(x)d x,\mathrm{and}}}\ {{\qquadd_{n}={\displaystyle\frac{S P_{t}e^{r_{c}r}-X}{\sigma_{S P}\sqrt{\frac{e^{r_{c}r}-1}{2r_{c}}}}}.}}\end{array}
$$
