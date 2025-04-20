---
tags:
  - asset_pricing
  - consumption_dynamics
  - epstein_zin_utility
  - long_run_risks
  - market_portfolio
aliases:
  - Bansal Yaron
  - Consumption Growth
  - Long-Run Risk
key_concepts:
  - Consumption and return data
  - Consumption dynamics model
  - Epstein-Zin utility
  - Long-run risk component
  - Market portfolio dividends
  - Time-varying economic uncertainty
---

# 8.8 Long-run risks and Epstein-Zin utility  

Bansal and Yaron (2004) show that a model with a representative individual having Epstein-Zin utility and with a 'long-run risk component' in aggregate consumption is able to explain some. of the apparently puzzling features of consumption and return data. Both the assumptions on. the preferences and the consumption dynamics are different from the simple consumption-based model, which is a special case. Bansal and Yaron emphasize that it is important to make both these extensions.  

Recall from Section 8.7.5 that the log of the next-period state-price deflator is  

$$
m_{t+1}=-\delta\theta-\frac{\theta}{\psi}g_{t+1}+\left(\theta-1\right)r_{t+1}^{w},
$$  

where $g_{t+1}=\ln(c_{t+1}/c_{t})$ is log consumption growth and $r_{t+1}^{w}$ is the log return on the wealth portfolio.  

# 8.8.1 A model with long-run risks  

We now take the following specific model for consumption dynamics as suggested by Bansal and Yaron (2004):  

$$
\begin{array}{r l}&{g_{t+1}=\mu+x_{t}+\sigma_{t}\eta_{t+1},}\ &{x_{t+1}=\rho x_{t}+\varphi_{e}\sigma_{t}e_{t+1},}\ &{\sigma_{t+1}^{2}=\sigma^{2}+\nu(\sigma_{t}^{2}-\sigma^{2})+\sigma_{v}v_{t+1}.}\end{array}
$$  

The shocks $\eta_{t+1},e_{t+1},v_{t+1}$ are assumed independent and $N(0,1)$ -distributed for all $t$ . The independence assumption simplifies notation and some of the computations in the following, but the shocks might very well be correlated and that may change the asset pricing conclusions of the model.  

The process( $x_{t}$ ) drives variations in conditional expectations of consumption and dividend growth, while the process. $\left(\sigma_{t}^{2}\right)$ captures time-varying economic uncertainty. Note that the dynamics. of these processes can be rewritten as.  

$$
\begin{array}{r l}&{x_{t+1}-x_{t}=(1-\rho)(0-x_{t})+\varphi_{e}\sigma_{t}e_{t+1},}\ &{\sigma_{t+1}^{2}-\sigma_{t}^{2}=(1-\nu)(\sigma^{2}-\sigma_{t}^{2})+\sigma_{v}v_{t+1},}\end{array}
$$  

from which it can be seen that the $x_{t}$ variable is fluctuating around. $0$ and $\sigma_{t}^{2}$ is fluctuating around $\sigma^{2}$ . (Unfortunately, with the proposed dynamics, $\sigma_{t}^{2}$ is not guaranteed to stay positive.) We will assume $\rho<1$ and $\nu<1$ . In the simple consumption-based model, the expected consumption. growth rate is assumed constant so that the $x_{t}$ variable is absent (or constant and equal to $0$ ) and $\sigma_{t}^{2}$ is constant and equal to $\sigma^{2}$ . Bansal and Yaron (2004) report an empirical estimate of $\rho$ equal to 0.979, which means that the. $x_{t}$ variable is varying very slowly over time. Formulated differently, the speed of mean reversion, $1-\rho$ , is very close to zero. Variations in. $x$ only matter for very long periods, hence the name 'long-run risk." Empirical evidence for a long-run risk component in aggregate consumption is also provided by, e.g., Hansen, Heaton, and Li (2008). Bansal and Yaron also present empirical support for variations in the volatility of consumption growth, which is captured by the $\sigma_{t}$ of the above model. They also find a high persistence in that process with. an estimate of $\nu=0.987$  

Turning to the market portfolio, assume that the log-growth rate of its dividends are given by  

$$
g_{d,t+1}=\mu_{d}+\varphi x_{t}+\varphi_{d}\sigma_{t}(\xi\eta_{t+1}+\sqrt{1-\xi^{2}}u_{t+1}),
$$  

where $u_{t+1}$ is another $N(0,1)$ shock independent of the other shocks in (8.64), and where $\varphi$ $\varphi_{d}>0$ and $\xi\in[-1,1]$ are additional constants. Then  

$$
\mathrm{Var}_{t}[g_{d,t+1}]=\varphi_{d}^{2}\sigma_{t}^{2},\qquad\mathrm{Corr}_{t}[g_{t+1},g_{d,t+1}]=\xi.
$$  

In the discussion of the simple consumption-based model earlier in this chapter, we have implicitly. assumed that the market portfolio was a claim to aggregate consumption so that. $g_{d,t+1}=g_{t+1}$ in all periods. In the above model this requires that $\mu_{d}=\mu$ $\varphi=\varphi_{d}=1$ , and $\xi=1$ . In reality the dividends of the stock market portfolio fluctuate much more than aggregate consumption (. $\varphi_{d}>1$ and are not perfectly correlated with aggregate consumption ( $\xi<1$ ). Bansal and Yaron (2004) assume the above dividend growth model with $\xi=0$ , but we will allow for correlation in the following. Following Abel (1999), Bansal and Yaron (2004) use $\varphi=3$ so that expected dividend growth is considerably more sensitive to the persistent factor than expected consumption growth, which can be explained by the leverage of the companies issuing the stocks..  

The state prices and returns in the model will be driven by $x_{t}$ and $\sigma_{t}^{2}$ . As we have seen earlier, for example in Section 8.7.5, we can obtain closed-form expressions for the risk-free rate and expected excess returns when the log state-price deflator and the log returns are jointly normally distributed. The driving processes $(x_{t}),(\sigma_{t}^{2})$ are Gaussian processes so if the log state-price deflator and the log returns were linearly related to these variables, they would also be Gaussian. Such a linear relationship is not exact, however, but we will establish and use an approximate linear relationship, which will then allow us to obtain closed-form expressions for the risk-free return, the expected excess return on the market portfolio, etc. The approximation is described in the following subsection.  

# 8.8.2 The Campbell-Shiller linearization  

Campbell and Shiller (1988) introduce a linear, approximative relation between log returns, log dividends, and log prices. Write the gross return on an asset as.  

$$
\lambda_{t+1}=\frac{P_{t+1}+D_{t+1}}{P_{t}}=\frac{\frac{P_{t+1}}{D_{t}}+\frac{D_{t+1}}{D_{t}}}{\frac{P_{t}}{D_{t}}}=\frac{\frac{P_{t+1}}{D_{t+1}}\frac{D_{t+1}}{D_{t}}+\frac{D_{t+1}}{D_{t}}}{\frac{P_{t}}{D_{t}}}=\frac{e^{z_{t+1}+\Delta d_{t+1}}+e^{\Delta d_{t+1}}}{e^{z_{t}}}=\frac{e^{\Delta d_{t+1}}(e^{z_{t+1}}+\Delta d_{t+1})}{e^{z_{t}}}
$$  

where $d_{t}=\ln D_{t}$ $p_{t}=\ln P_{t}$ $\begin{array}{r}{z_{t}=p_{t}-d_{t}=\ln{\frac{P_{t}}{D_{t}}}}\end{array}$ and $\begin{array}{r}{\Delta d_{t+1}=d_{t+1}-d_{t}=\ln{\frac{D_{t+1}}{D_{t}}}}\end{array}$ . Then  

$$
\ln R_{t+1}=\ln\left[e^{\Delta d_{t+1}}(1+e^{z_{t+1}})\right]-z_{t}=-z_{t}+\Delta d_{t+1}+\ln(1+e^{z_{t+1}})
$$  

and a first-order Taylor approximation of $\ln(1+e^{z_{t+1}})$ around $z_{t+1}=z$ gives  

$$
r_{t+1}=\ln R_{t+1}\approx-z_{t}+\Delta d_{t+1}+\ln(1+e^{z})-\frac{e^{z}}{1+e^{z}}(z_{t+1}-z).
$$  

Letting $\begin{array}{r}{\kappa_{1}=\frac{e^{z}}{1+e^{z}}}\end{array}$ 1+e and Ko = ln(1 + e) - k1z, we obtain  

$$
r_{t+1}\approx\kappa_{0}+\kappa_{1}z_{t+1}-z_{t}+\Delta d_{t+1}.
$$  

For $z$ , it is natural to use the average value of the log price-dividend ratio of the asset.  

For an asset paying a dividend identical to the consumption stream, we can replace $\Delta d_{t+1}$ by the log-growth rate of consumption, $g_{t+1}=\ln(C_{t+1}/C_{t})$ . In this case $z_{t}$ is to be interpreted as the log price-consumption ratio, and we have  

$$
r_{t+1}^{w}\approx\kappa_{0}+\kappa_{1}z_{t+1}-z_{t}+g_{t+1}.
$$  

Substituting this approximation into (8.59), we obtain  

$$
\begin{array}{r}{\mathrm{E}_{t}\left[e^{-\delta\theta+\theta\left(1-\frac{1}{\psi}\right)g_{t+1}+\theta\kappa_{0}+\theta\kappa_{1}z_{t+1}-\theta z_{t}}\right]=1.}\end{array}
$$  

For the market portfolio paying aggregate dividends, the analogous approximation of the log return is  

$$
r_{t+1}^{m}\approx\kappa_{0}^{m}+\kappa_{1}^{m}z_{t+1}^{m}-z_{t}^{m}+g_{d,t+1},
$$  

where $z_{t}^{m}$ is the log price-dividend ratio and $g_{d,t+1}$ is the log-growth rate of aggregate dividends. Substituting (8.67) and (8.69) into (8.62), we obtain  

$$
\begin{array}{r}{\mathrm{E}_{t}\left[e^{-\delta\theta+\left[\theta\left(1-\frac{1}{\psi}\right)-1\right]g_{t+1}+(\theta-1)(\kappa_{0}+\kappa_{1}z_{t+1}-z_{t})+\kappa_{0}^{m}+\kappa_{1}^{m}z_{t+1}^{m}-z_{t}^{m}+g_{d,t+1}}\right]=1,}\end{array}
$$  

which we shall apply below.  

# 8.8.3 The state-price deflator  

Substituting the specific model equations into (8.68), we get  

$$
\begin{array}{r}{\mathrm{E}_{t}\left[e^{-\delta\theta+\theta\left(1-\frac{1}{\psi}\right)\left(\mu+x_{t}+\sigma_{t}\eta_{t+1}\right)+\theta\kappa_{0}+\theta\kappa_{1}z_{t+1}-\theta z_{t}}\right]=1,}\end{array}
$$  

which has to be satisfied (approximately, at least) for all possible values of. $x_{t}$ and $\sigma_{t}$ at any point in time $t$ . Conjecture a solution for the log price-consumption ratio of the form  

$$
z_{t}=A_{0}+A_{1}x_{t}+A_{2}\sigma_{t}^{2}
$$  

for all $t$ . Substituting that and the equations for $x_{t+1}$ and $\sigma_{t+1}^{2}$ from (8.64) into the previous equation and then collecting terms yield  

$$
\begin{array}{l}{\displaystyle=\exp\left\{\theta q+\theta\left(1-\frac{1}{\psi}-A_{1}\left[1-\rho\kappa_{1}\right]\right)x_{t}+\theta A_{2}\left(\kappa_{1}\nu-1\right)\sigma_{t}^{2}\right\}\mathrm{E}_{t}\left[e^{\theta\left(1-\frac{1}{\psi}\right)\sigma_{t}\eta_{t+1}+\theta\kappa_{1}\left[A_{1}\varphi_{e}\sigma_{t}\epsilon_{t+1}+A_{2}\left(1-\rho\kappa_{1}\right)\right]}\right]}\ {\displaystyle=\exp\left\{\theta q+\theta\left(1-\frac{1}{\psi}-A_{1}\left[1-\rho\kappa_{1}\right]\right)x_{t}-\theta A_{2}\left(1-\kappa_{1}\nu\right)\sigma_{t}^{2}\right\}\exp\left\{\frac{1}{2}\theta^{2}\left(\left[\left(1-\frac{1}{\psi}\right)^{2}+\kappa_{1}^{2}A_{1}^{2}\varphi_{e}^{2}\right]\sigma_{e}^{2}\right)\right.}\ {\displaystyle=\exp\left\{\theta q+\frac{1}{2}\theta^{2}\kappa_{1}^{2}A_{2}^{2}\sigma_{v}^{2}+\theta\left(1-\frac{1}{\psi}-A_{1}\left[1-\rho\kappa_{1}\right]\right)x_{t}+\theta\left(\frac{1}{2}\theta\left[\left(1-\frac{1}{\psi}\right)^{2}+K_{1}^{2}A_{1}^{2}\varphi_{e}^{2}\right]-A_{2}\left(1-\rho\kappa_{1}\right)\right)\right\}}\end{array}
$$  

where $\begin{array}{r}{q=-\delta+(1-\frac{1}{\psi})\mu+\kappa_{0}+A_{0}(\kappa_{1}-1)+\kappa_{1}A_{2}\sigma^{2}(1-\nu)}\end{array}$ . Since this is to be satisfied for all values of $x_{t}$ and $\sigma_{t}^{2}$ , we need the coefficients of $x_{t}$ and $\sigma_{t}^{2}$ to be zero, i.e.  

$$
\begin{array}{c}{A_{1}=\displaystyle\frac{1-\frac{1}{\psi}}{1-\rho\kappa_{1}},}\ {A_{2}=\displaystyle\frac{\theta}{2(1-\kappa_{1}\nu)}\left[\left(1-\frac{1}{\psi}\right)^{2}+\kappa_{1}^{2}A_{1}^{2}\varphi_{e}^{2}\right]=\displaystyle\frac{\theta\left(1-\frac{1}{\psi}\right)^{2}}{2(1-\kappa_{1}\nu)}\left[1+\left(\frac{\kappa_{1}\varphi_{e}}{1-\rho\kappa_{1}}\right)^{2}\right].}\end{array}
$$  

The constant $A_{0}$ is included in $q$ is then determined from the condition $\begin{array}{r}{1=\exp\left\{q+\frac{1}{2}\theta^{2}\kappa_{1}^{2}A_{2}^{2}\sigma_{v}^{2}\right\}}\end{array}$ i.e. $q+{\textstyle\frac{1}{2}}\theta^{2}\kappa_{1}^{2}A_{2}^{2}\sigma_{v}^{2}=0$  

Combining (8.58) and (8.67), the log of the state-price deflator can be written as  

$$
\begin{array}{l}{{m_{t+1}=(\theta-1)q-\delta-\displaystyle\frac{\mu}{\psi}-\frac{x_{t}}{\psi}+(\theta-1)A_{2}(\kappa_{1}\nu-1)\sigma_{t}^{2}}}\ {{\displaystyle~+\left(\theta-1-\frac{\theta}{\psi}\right)\sigma_{t}\eta_{t+1}+(\theta-1)\kappa_{1}A_{1}\varphi_{e}\sigma_{t}e_{t+1}+(\theta-1)\kappa_{1}A_{2}\sigma_{v}v_{t+1}.}}\end{array}
$$  

Note that $\begin{array}{r}{\theta-1-\frac{\theta}{\psi}=\theta(1-\frac{1}{\psi})-1=1-\gamma-1=-\gamma}\end{array}$ . Define  

$$
\l=\gamma,\quad\lambda_{e}=(1-\theta)\kappa_{1}A_{1}\varphi_{e},\quad\lambda_{v}=(1-\theta)\kappa_{1}A_{2}.
$$  

Then, from the distributional assumptions on the shocks, we conclude that we can rewrite $r n_{t+1}$ as  

$$
\begin{array}{r}{m_{t+1}=\mathrm{E}_{t}[m_{t+1}]-\lambda_{\eta}\sigma_{t}\eta_{t+1}-\lambda_{e}\sigma_{t}e_{t+1}-\lambda_{v}\sigma_{v}v_{t+1},}\end{array}
$$  

and that $n_{t+1}$ is conditional lognormally distributed with  

$$
\mathrm{E}_{t}[m_{t+1}]=(\theta-1)q-\delta-\frac{\mu}{\psi}-\frac{x_{t}}{\psi}+(\theta-1)A_{2}(\kappa_{1}\nu-1)\sigma_{t}^{2},
$$  

$$
\mathrm{Var}_{t}[m_{t+1}]=\sigma_{t}^{2}\left(\lambda_{\eta}^{2}+\lambda_{e}^{2}\right)+\lambda_{v}^{2}\sigma_{v}^{2}.
$$  

# 8.8.4 The risk-free rate  

The risk-free log interest rate becomes  

$$
\begin{array}{l}{{r_{t}^{f}=-\ln\operatorname{E}_{t}\left[e^{m_{t+1}}\right]=-\operatorname{E}_{t}[m_{t+1}]-\frac{1}{2}\operatorname{Var}_{t}[m_{t+1}]}}\ {{\mathrm{}=\delta+(1-\theta)q+\frac{\mu+x_{t}}{\psi}-\frac{1}{2}\lambda_{v}^{2}\sigma_{v}^{2}-\left((1-\theta)A_{2}(1-\kappa_{1}\nu)+\frac{1}{2}\gamma^{2}+\frac{1}{2}\lambda_{e}^{2}\right)\sigma_{t}^{2}.}}\end{array}
$$  

Let us first look at some special cases. For the standard dynamics of consumption growth, we have $x_{t}~\equiv~0$ $\sigma_{t}^{2}\equiv\sigma^{2}$ and $\sigma_{v}^{2}=0$ so that $q=0$ .Moreover, $\varphi_{e}~=~0$ and thus $\lambda_{e}~=~0$ , and $\begin{array}{r}{A_{2}(1-\kappa_{1}\nu)=\theta(1-\frac{1}{\psi})^{2}/2}\end{array}$ . Hence, we get the constant risk-free rate  

$$
r_{t}^{f}=\delta+\frac{\mu}{\psi}-\frac{1}{2}\sigma^{2}\left(\theta(1-\frac{1}{\psi})^{2}+\gamma^{2}\right)=\delta+\frac{\mu}{\psi}-\frac{1}{2}\left(1-\theta+\frac{\theta}{\psi^{2}}\right)\sigma^{2}.
$$  

This is consistent with (8.61) because in this version of the model $z_{t}$ in (8.72) is constant and,. hence, $r_{t+1}^{w}$ equals a constant plus log consumption growth. Consequently, the variance of the wealth portfolio equals the variance of consumption growth, $\sigma_{w}^{2}=\sigma^{2}$ , and if you apply that. in (8.61), you get the above expression for the risk-free rate..  

If we use the long-run risk model for consumption dynamics but specialize to power utility, the risk-free rate will be $r_{t}^{f}=\delta+\gamma(\mu+x_{t})-{\textstyle\frac{1}{2}}\gamma^{2}\sigma_{t}^{2}$ . The level of the risk-free rate will be similar to the case with the simple model for consumption dynamics, but the fluctuations in expected consumption growth and consumption volatility generate fluctuations in the risk-free rate.  

For the general expression for the risk-free rate (8.80), the level is still decreasing in the elasticity. of intertemporal substitution. According to Bansal and Yaron (2004), the unconditional variance of the risk-free rate is  

$$
\mathrm{Var}[r_{t}^{f}]\approx\left(\frac{1}{\psi}\right)^{2}\mathrm{Var}[x_{t}],
$$  

which is again decreasing in the elasticity of intertemporal substitution. In the long-run risk model with power utility briefly discussed above, we would similarly have $\mathrm{Var}[r_{t}^{f}]\approx\gamma^{2}\mathrm{Var}[x_{t}]$ .With power utility, a high risk aversion is needed to match the equity premium, but that may easily lead to an unrealistic high variance of the risk-free rate. With Epstein-Zin utility and a fairly high elasticity of intertemporal substitution, we can keep a relatively low and relatively stable risk-free rate.  

# 8.8.5 The premium on risky assets  

From Section 4.2.2, we have that for any normally distributed log-return $r_{i,t+1}$  

$$
\begin{array}{l}{{\displaystyle\mathrm{E}_{t}[r_{i,t+1}]-r_{t}^{f}=-\mathrm{Cov}_{t}\left[m_{t+1},r_{i,t+1}\right]-\frac{1}{2}\mathrm{Var}_{t}[r_{i,t+1}]}}\ {{\displaystyle\qquad=\lambda_{\eta}\sigma_{t}\mathrm{Cov}_{t}[\eta_{t+1},r_{i,t+1}]+\lambda_{e}\sigma_{t}\mathrm{Cov}_{t}[e_{t+1},r_{i,t+1}]}}\ {{\displaystyle\qquad+\lambda_{v}\sigma_{v}\mathrm{Cov}_{t}[v_{t+1},r_{i,t+1}]-\frac{1}{2}\mathrm{Var}_{t}[r_{i,t+1}]}.}\end{array}
$$  

If we substitute the modeling assumptions (8.64) and (8.65) together with (8.72) into (8.70), we  

find that  

$$
\begin{array}{r l}&{=\mathrm{E}_{t}\Bigg[\exp\Bigg\{\widetilde{q}+(\varphi-\displaystyle\frac{1}{\psi})x_{t}+(\theta-1)A_{2}(\kappa_{1}\nu-1)\sigma_{t}^{2}+\kappa_{1}^{m}z_{t+1}^{m}-z_{t}^{m}\Bigg\}}\ &{\qquad\times\exp\Big\{(\varphi a\xi-\gamma)\sigma_{t}\eta_{t+1}+(\theta-1)\kappa_{1}A_{2}\sigma_{v}v_{t+1}+\varphi_{d}\sqrt{1-\xi^{2}}\sigma_{t}u_{t+1}+(\theta-1)\kappa_{1}A_{1}\varphi_{e}\sigma_{t}e_{t+1}\Big\}}\end{array}.
$$  

where $\tilde{q}=-\delta+(\theta-1)q-\mu/\psi+\kappa_{0}^{m}+\mu_{d}$ . Now conjecture that the log price-dividend ratio is of the form  

$$
z_{t}^{m}=B_{0}+B_{1}x_{t}+B_{2}\sigma_{t}^{2},
$$  

which implies that  

$$
\begin{array}{r l}&{\kappa_{1}^{m}z_{t+1}^{m}-z_{t}^{m}=(\kappa_{1}^{m}-1)B_{0}+\kappa_{1}^{m}B_{2}\sigma^{2}(1-\nu)+B_{1}(\rho\kappa_{1}^{m}-1)x_{t}}\ &{\qquad+B_{2}(\nu\kappa_{1}^{m}-1)\sigma_{t}^{2}+\kappa_{1}^{m}B_{1}\varphi_{e}\sigma_{t}e_{t+1}+\kappa_{1}^{m}B_{2}\sigma_{v}v_{t+1}.}\end{array}
$$  

If we substitute that into (8.83), we obtain  

$$
\begin{array}{r l r}&{}&{=\mathrm{E}_{t}\Bigg[\exp\Bigg\{\widetilde{q}+(\kappa_{1}^{m}-1)B_{0}+\kappa_{1}^{m}B_{2}\sigma^{2}(1-\nu)+\displaystyle\frac{1}{2}[(\theta-1)\kappa_{1}A_{2}+\kappa_{1}^{m}B_{2}]^{2}\sigma_{\nu}^{2}+\left(\varphi-\displaystyle\frac{1}{\psi}+B_{1}(\rho\kappa_{1}^{m}}\ &{}&\ &{}&{\times\exp\left\{\left(A_{2}(\theta-1)(\kappa_{1}\nu-1)+B_{2}(\nu\kappa_{1}^{m}-1)+\displaystyle\frac{1}{2}\gamma^{2}-\gamma\varphi_{d}\xi+\displaystyle\frac{1}{2}\varphi_{d}^{2}+\displaystyle\frac{1}{2}(\beta_{e}^{m}-\lambda_{e})^{2}\right)\sigma_{t}^{2}\right\}\Bigg],}\end{array}
$$  

where $\beta_{e}^{m}=\kappa_{1}^{m}B_{1}\varphi_{e}$ and $\lambda_{e}=(1-\theta)\kappa_{1}A_{1}\varphi_{e}$ . Since this must be satisfied for any values of $x_{t}$ and $\sigma_{t}^{2}$ , we need the coefficients of those terms to be zero and, consequently, the constant part of the exponent to be zero as well, i.e.  

$$
B_{1}=\frac{\varphi-\frac{1}{\gamma}}{1-\rho\kappa_{1,m}},\quad B_{2}=\frac{(1-\theta)A_{2}(1-\kappa_{1}\nu)+\frac{1}{2}\gamma^{2}-\gamma\varphi_{d}\xi+\frac{1}{2}\varphi_{d}^{2}+\frac{1}{2}(\beta_{e}^{m}-\lambda_{e})^{2}}{1-\nu\kappa_{1,m}},
$$  

and $B_{0}$ is such that $\tilde{q}+(\kappa_{1}^{m}-1)B_{0}+\kappa_{1}^{m}B_{2}\sigma^{2}(1-\nu)+{\textstyle\frac{1}{2}}[(\theta-1)\kappa_{1}A_{2}+\kappa_{1}^{m}B_{2}]^{2}\sigma_{v}^{2}=0$ ). This confirms the conjectured form of $z_{t}^{m}$  

If we use (8.84) in the Campbell-Shiller approximation (8.69) and focus on the shock terms, we obtain  

$$
r_{t+1}^{m}=\mathrm{E}_{t}[r_{t+1}^{m}]+\beta_{e}^{m}\sigma_{t}e_{t+1}+\beta_{v}^{m}\sigma_{v}v_{t+1}+\beta_{\eta}^{m}\sigma_{t}\eta_{t+1}+\varphi_{d}\sqrt{1-\xi^{2}}\sigma_{t}u_{t+1},
$$  

where $\beta_{v}^{m}=\kappa_{1}^{m}B_{2}$ and $\beta_{\eta}^{m}=\varphi_{d}\xi$ . Substituting this into (8.82) we find  

$$
\mathrm{E}_{t}[r_{t+1}^{m}]-r_{t}^{f}=\beta_{\eta}^{m}\lambda_{\eta}\sigma_{t}^{2}+\beta_{e}^{m}\lambda_{e}\sigma_{t}^{2}+\beta_{v}^{m}\lambda_{v}\sigma_{v}^{2}-\frac{1}{2}\mathrm{Var}_{t}[r_{t+1}^{m}],
$$  

and  

$$
\begin{array}{r}{\mathrm{Var}_{t}[r_{t+1}^{m}]=\left((\beta_{e}^{m})^{2}+\varphi_{d}^{2}\right)\sigma_{t}^{2}+(\beta_{v}^{m})^{2}\sigma_{v}^{2}.}\end{array}
$$  

Let us look at some special cases. If we keep the Epstein-Zin preferences but specialize to the consumption dynamics of the simple model ( $\sigma_{t}^{2}\equiv\sigma^{2}$ $x_{t}\equiv0$ ), we get  

$$
\operatorname{E}_{t}[r_{t+1}^{m}]-r_{t}^{f}=\varphi_{d}\xi\gamma\sigma^{2}-{\frac{1}{2}}\operatorname{Var}_{t}[r_{t+1}^{m}],\quad\operatorname{Var}_{t}[r_{t+1}^{m}]=\varphi_{d}^{2}\sigma^{2}
$$  

and $\varphi_{d}=\xi=1$ if we assume the dividends are identical to aggregate consumption. This is consistent with (8.63) because in this special version of the model $r_{t+1}^{w}$ equals a constant plus $g_{t+1}=\mu+\sigma\eta_{t+1}$ and $r_{t+1}^{m}=\mathrm{E}_{t}[r_{t+1}^{m}]+\varphi_{d}\xi\sigma\eta_{t+1}+\varphi_{d}\sqrt{1-\xi^{2}}\sigma u_{t+1}$ so that  

$$
\begin{array}{r}{\mathrm{Cov}_{t}[r_{t+1}^{m},g_{t+1}]=\mathrm{Cov}_{t}[r_{t+1}^{m},r_{t+1}^{w}]=\varphi_{d}\xi\sigma^{2}.}\end{array}
$$  

Since $\begin{array}{r}{\frac{\theta}{\psi}+1-\theta=\gamma}\end{array}$ , it is now clear that (8.63) and (8.89) agree.  

Conversely, if we specialize to power utility ( $\gamma=1/\psi$ $\theta=1$ ) but keep the long-run risk model for the dynamics of consumption and dividends, we get $\lambda_{e}=\lambda_{v}=0$ and thus  

$$
\mathrm{E}_{t}[r_{t+1}^{m}]-r_{t}^{f}=\varphi_{d}\xi\gamma\sigma_{t}^{2}-\frac{1}{2}\mathrm{Var}_{t}[r_{t+1}^{m}].
$$  

Therefore, under a power utility assumption, introducing a long-run risk element in consumption dynamics does not change the level of excess expected returns on the market portfolio. We need the combination of Epstein-Zin utility and long-run risks in order to affect excess expected returns.  

In the general expression (8.87) for the market risk premium the first term--the standard termis a premium for short-run risk, the second term is a premium for long-run risk, while the third term is a premium for consumption volatility risk. What can we say about the sign of the the two latter premia? First consider $\lambda_{e}=(1-\theta)\kappa_{1}A_{1}\varphi_{e}$ . We have $0<\kappa_{1}<1$ and $\varphi_{e}>0$ . If we assume that $1>1/\psi$ , we will have $A_{1}>0$ . With $\gamma>1/\psi$ , we have $\theta<1$ , and thus all in all we get. $\lambda_{e}>0$ Next consider $\beta_{e}^{m}=\kappa_{1}^{m}B_{1}\varphi_{e}$ . Again $\kappa_{1}^{r n}$ and $\varphi_{e}$ must be positive. If the persistence parameter. $\rho$ is greater than $1/\gamma$ $B_{1}$ will be positive, and hence. $\beta_{e}^{m}$ is positive. Under such parameter values, the. long-run risk premium. $\beta_{e}^{m}\lambda_{e}\sigma_{t}^{2}$ is going to be positive. Also note that. $\beta_{e}^{m}$ and thus the long-run. risk premium are increasing in $\rho$ and $\varphi$ , i.e. the risk premium increases with the persistence of the long-run growth component and the sensitivity of dividends to that long-run component. What about the volatility risk premium? Again, if. $\gamma>1/\psi$ so that $\theta<1$ , we will have $B_{2}>0$ and hence $\beta_{v}^{m}=\kappa_{1}^{m}B_{2}>0$ . Also note that $A_{2}>0$ so, for $\gamma>1/\psi$ , we have $\lambda_{v}=(1-\theta)\kappa_{1}A_{2}>0$ . Under these parameter conditions, the volatility risk premium. $\beta_{v}^{m}\lambda_{v}\sigma_{v}^{2}$ will be positive.  

From the preceding discussion it is clear that the long-run risk and volatility risk features of the model will add to the market risk premium if. $\gamma>1>1/\psi$ . In particular, the elasticity of intertemporal substitution $\psi$ has to exceed 1. As discussed in Section 5.7.3, there is some debate. about empirical realistic values of. $\psi$ , where some authors find $\psi$ greater than one and others find $\psi$ smaller than one.  

The variations in consumption volatility induce variations in the excess expected return, the return volatility, and the Sharpe ratio of the market portfolio.  

# 8.8.6 Evaluation of the model  

Bansal and Yaron (2004) calibrate their model to return and consumption data from the United States over the period 1929-1998. Table 8.2 contains statistics for the return data and for the calibrated model using an elasticity of intertemporal substitution equal to 1.5. With a modest level of risk aversion the model comes very close at matching the data.  

As acknowledged by Bansal and Yaron, it is econometrically very difficult to detect a small but highly persistent component in a time series, but at least their study shows that if consumption growth has such a component, it may have significant effects on asset returns. Combined with the plausible Epstein-Zin preferences, long-run risks in consumption may explain (a substantial part of) the equity premium puzzle.  

Table 8.2: Asset pricing in the Bansal and Yaron model. The information is taken from Table IV in Bansal and Yaron (2004). All returns are in percentage terms. The elasticity of intertemporal. substitution is $\psi=1.5$   


<html><body><table><tr><td></td><td colspan="2">U.S. data 1929-1998</td><td colspan="2">Calibrated model</td></tr><tr><td>Variable</td><td>Estimate</td><td>Std. error</td><td>=7.5</td><td>=10</td></tr><tr><td>E[rm -rf]</td><td>6.33</td><td>2.15</td><td>4.01</td><td>6.84</td></tr><tr><td>E[r]</td><td>0.86</td><td>0.42</td><td>1.44</td><td>0.93</td></tr><tr><td>o[rm]</td><td>19.42</td><td>3.07</td><td>17.81</td><td>18.65</td></tr><tr><td>o[rf]</td><td>0.97</td><td>0.28</td><td>0.44</td><td>0.57</td></tr></table></body></html>  

Bansal (2007) gives a useful survey of the rapidly growing literature on long-run risks and asset pricing with a lot of additional references for the interested reader. Various extensions of the longrun risk model and the applications of it are mentioned in that survey. For example, including a long-run risk component in consumption appears to be important for explaining the cross-section of returns. Bansal, Dittmar, and Lundblad (2005) show that the exposure of an assets dividends to long-run consumption risks is an important explanatory variable in accounting for differences in mean returns across portfolios.  
