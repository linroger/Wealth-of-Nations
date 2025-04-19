---
tags:
  - asset_returns
  - consumption_growth
  - continuous_time
  - multi_period_model
  - risk_free_rate
aliases:
  - Consumption and Returns
  - Multi-Period Analysis
key_concepts:
  - Consumption-beta equation
  - Excess expected return
  - Relative consumption growth
  - Risk-free gross return
  - State-price deflator
  - Time-additive expected utility
---

# 8.3 General multi-period link between consumption and asset returns  

Now take the analysis to multi-period settings. Assuming time-additive expected utility we can define a state-price deflator from the optimal consumption plan of any individual as  

$$
\zeta_{t}=e^{-\delta t}\frac{u^{\prime}(c_{t})}{u^{\prime}(c_{0})}.
$$  

This is true both in the discrete-time and in the continuous-time setting. If a representative individual exists, the equation holds for aggregate consumption..  

Not surprisingly, the multi-period discrete-time setting leads to equations very similar to those derived in the one-period framework in the previous section. Since.  

$$
\frac{\zeta_{t+1}}{\zeta_{t}}=e^{-\delta}\frac{u^{\prime}(c_{t+1})}{u^{\prime}(c_{t})},
$$  

we get from (4.25) and (4.26) that the risk-free gross return is  

$$
R_{t}^{f}=e^{\delta}\left(\mathrm{E}_{t}\left[\frac{u^{\prime}(c_{t+1})}{u^{\prime}(c_{t})}\right]\right)^{-1}
$$  

and that the excess expected gross return on a risky asset is  

$$
\begin{array}{r l}&{\mathrm{E}_{t}[R_{i,t+1}]-R_{t}^{f}=-\frac{\mathrm{Cov}_{t}[u^{\prime}(c_{t+1})/u^{\prime}(c_{t}),R_{i,t+1}]}{\mathrm{E}_{t}[u^{\prime}(c_{t+1})/u^{\prime}(c_{t})]}}\ &{\qquad=\rho_{t}\left[R_{i,t+1},\frac{u^{\prime}(c_{t+1})}{u^{\prime}(c_{t})}\right]\sigma_{t}[R_{i,t+1}]\left(-\frac{\sigma_{t}[u^{\prime}(c_{t+1})/u^{\prime}(c_{t})]}{\mathrm{E}_{t}[u^{\prime}(c_{t+1})/u^{\prime}(c_{t})]}\right).}\end{array}
$$  

These equations are the multi-period equivalents of the Equations (8.1) and (8.2) for the one-period. model. As in the one-period case, we can obtain an approximate relation between expected returns and relative consumption growth, $g_{t+1}=c_{t+1}/c_{t}-1$ , over the next period,  

$$
\begin{array}{r}{\mathrm{E}_{t}[R_{i,t+1}]-R_{t}^{f}\approx\gamma(c_{t})\mathrm{Cov}_{t}[g_{t+1},R_{i,t+1}],}\end{array}
$$  

and also an approximate consumption-beta equation  

$$
\begin{array}{r}{\mathrm{E}_{t}[R_{i,t+1}]-R_{t}^{f}\approx\beta_{t}[R_{i,t+1},R_{t+1}^{c}]\left(\mathrm{E}_{t}[R_{t+1}^{c}]-R_{t}^{f}\right),}\end{array}
$$  

where $\beta_{t}[R_{i,t+1},R_{t+1}^{c}]=\operatorname{Cov}_{t}[R_{i,t+1},R_{t+1}^{c}]/\operatorname{Var}_{t}[R_{t+1}^{c}]$ and $R_{t+1}^{c}$ is the gross return on a portfolio perfectly correlated with consumption growth over this period.  

Now let us turn to the continuous-time setting. Suppose that the dynamics of consumption can be written as  

$$
d c_{t}=c_{t}\left[\mu_{c t}\:d t+\pmb{\sigma}_{c t}^{\top}\:d z_{t}\right],
$$  

where $\mu_{c t}$ is the expected relative growth rate of consumption and. $\sigma_{c t}$ is the vector of sensitivities. of consumption growth to the exogenous shocks to the economy. In particular, the variance of relative consumption growth is given by $\|\sigma_{c t}\|^{2}$ .Given the dynamics of consumption and the. relation (8.16) we can obtain the dynamics of $\zeta_{t}$ by an application of Ito's Lemma on the function. $g(t,c)=e^{-\partial t}u^{\prime}(c)/u^{\prime}(c_{0})$ . The relevant derivatives are  

$$
\frac{\partial g}{\partial t}(t,c)=-\delta e^{-\delta t}\frac{u^{\prime}(c)}{u^{\prime}(c_{0})},\quad\frac{\partial g}{\partial c}(t,c)=e^{-\delta t}\frac{u^{\prime\prime}(c)}{u^{\prime}(c_{0})},\quad\frac{\partial^{2}g}{\partial c^{2}}(t,c)=e^{-\delta t}\frac{u^{\prime\prime\prime}(c)}{u^{\prime}(c_{0})},
$$  

implying that  

$$
\begin{array}{l}{\displaystyle\frac{\partial g}{\partial t}(t,c_{t})=-\delta e^{-\delta t}\frac{u^{\prime}(c_{t})}{u^{\prime}(c_{0})}=-\delta\zeta_{t},}\ {\displaystyle\frac{\partial g}{\partial c}(t,c_{t})=e^{-\delta t}\frac{u^{\prime\prime}(c_{t})}{u^{\prime}(c_{0})}=\frac{u^{\prime\prime}(c_{t})}{u^{\prime}(c_{t})}\zeta_{t}=-\gamma(c_{t})c_{t}^{-1}\zeta_{t},}\ {\displaystyle\frac{\partial^{2}g}{\partial c^{2}}(t,c_{t})=e^{-\delta t}\frac{u^{\prime\prime\prime}(c_{t})}{u^{\prime}(c_{0})}=\frac{u^{\prime\prime\prime}(c_{t})}{u^{\prime}(c_{t})}\zeta_{t}=\eta(c_{t})c_{t}^{-2}\zeta_{t},}\end{array}
$$  

where $\gamma(c_{t})\equiv-c_{t}u^{\prime\prime}(c_{t})/u^{\prime}(c_{t})$ is the relative risk aversion of the individual, and where $\eta(c_{t})\equiv$ $c_{t}^{2}u^{\prime\prime\prime}(c_{t})/u^{\prime}(c_{t})$ is positive under the very plausible assumption that the absolute risk aversion of the individual is decreasing in the level of consumption. Consequently, the dynamics of the state-price deflator can be expressed as  

$$
d\zeta_{t}=-\zeta_{t}\left[\Big(\delta+\gamma(c_{t})\mu_{c t}-\frac{1}{2}\eta(c_{t})\|\sigma_{c t}\|^{2}\Big)d t+\gamma(c_{t})\sigma_{c t}^{\top}d z_{t}\right],
$$  

Comparing the above equation with (4.41), we can draw the conclusions summarized in the following theorem:  

Theorem 8.1 In a continuous-time economy where the optimal consumption process of an in-. dividual with time-additive expected utility satisfies (8.21), the continuously compounded risk-free short-term interest rate satisfies  

$$
r_{t}^{f}=\delta+\gamma(c_{t})\mu_{c t}-\frac{1}{2}\eta(c_{t})\|\pmb{\sigma}_{c t}\|^{2}
$$  

and  

$$
\lambda_{t}=\gamma(c_{t})\sigma_{c t}
$$  

defines a market price of risk process. Here $\gamma(c_{t})=-c_{t}u^{\prime\prime}(c_{t})/u^{\prime}(c_{t})$ and $\eta(c_{t})=c_{t}^{2}u^{\prime\prime\prime}(c_{t})/u^{\prime}(c_{t})$  

Equation (8.23) gives the interest rate at which the market for short-term borrowing and lending. will clear. The equation relates the equilibrium short-term interest rate to the time preference rate and the expected growth rate $\mu_{c t}$ and the variance rate $\|\sigma_{c t}\|^{2}$ of aggregate consumption growth over the next instant. We can observe the following relations:.  

: There is a positive relation between the time preference rate and the equilibrium interest rate. The intuition behind this is that when the individuals of the economy are impatient and has a high demand for current consumption, the equilibrium interest rate must be high in order to encourage the individuals to save now and postpone consumption..   
. The multiplier of $\mu_{c t}$ in (8.23) is the relative risk aversion of the representative individual, which is positive. Hence, there is a positive relation between the expected growth in aggregate consumption and the equilibrium interest rate. This can be explained as follows: We expect. higher future consumption and hence lower future marginal utility, so postponed payments due to saving have lower value. Consequently, a higher return on saving is needed to maintain market clearing.   
If $u^{\prime\prime\prime}$ is positive, there will be a negative relation between the variance of aggregate con-. sumption and the equilibrium interest rate. If the representative individual has decreasing absolute risk aversion, which is certainly a reasonable assumption,. $u^{\prime\prime\prime}$ has to be positive. The intuition is that the greater the uncertainty about future consumption, the more will the individuals appreciate the sure payments from the risk-free asset and hence the lower a return is necessary to clear the market for borrowing and lending.  

If we substitute (8.24) into (4.39) we see that the excess expected rate of return on asset $i$ OVer the instant following time $t$ can be written as  

$$
\mu_{i t}+\delta_{i t}-r_{t}^{f}=\gamma(c_{t})\pmb{\sigma}_{i t}^{\top}\pmb{\sigma}_{c t}=\gamma(c_{t})\rho_{i c t}\left\|\pmb{\sigma}_{i t}\right\|\left\|\pmb{\sigma}_{c t}\right\|.
$$  

Here $\sigma_{i t}^{\top}\sigma_{c t}$ and $\rho_{i c t}$ are the covariance and correlation between the rate of return on asset $i$ and the consumption growth rate, respectively, and. $\lVert\pmb{\sigma}_{i t}\rVert$ and $\|\sigma_{c t}\|$ are standard deviations (volatilities) of the rate of return on asset. $i$ and the consumption growth rate, respectively. Equation (8.25) is the continuous-time version of (8.19). Note that the continuous-time relation is exact. Again, if we can find a trading strategy "mimicking" the consumption process (same volatility, perfect correlation) we get the "consumption-beta" relation  

$$
\mu_{i t}+\delta_{i t}-r_{t}^{f}=\beta_{i t}^{c}\left(\mu_{t}^{*}+\delta_{t}^{*}-r_{t}^{f}\right),
$$  

where $\beta_{i t}^{c}=\pmb{\sigma}_{i t}^{\top}\pmb{\sigma}_{c t}/\lVert\pmb{\sigma}_{c t}\rVert^{2}$  

If the market is effectively complete, the above equations are valid for aggregate consumption. if we apply the utility function and time preference rate of the representative individual. The representative individual version of Equation (8.25) says that risky assets are priced so that the expected excess return on an asset is given by the product of the relative risk aversion of the representative individual and the covariance between the asset return and the growth rate of aggregate consumption. This is the key result in the Consumption-based CAPM (or just CCAPM) developed by Breeden (1979).  

As already indicated in the one-period framework, we can obtain a relation between expected returns and aggregate consumption also if the market is incomplete and no representative individual exists. Let us stick to the continuous-time setting. Let $c_{l}=\left(c_{l t}\right)$ denote the optimal consumption process of individual number $\textit{l}$ in the economy and assume that  

$$
d c_{l t}=c_{l t}\left[\mu_{c l t}d t+\sigma_{c l t}^{\top}d z_{t}\right].
$$  

If there are $L$ individuals in the economy, aggregate consumption is $\begin{array}{r}{C_{t}=\sum_{l=1}^{L}c_{l t}}\end{array}$ and we have that  

$$
\begin{array}{l}{\displaystyle{d C_{t}=\sum_{l=1}^{L}d c_{l t}=\left(\sum_{l=1}^{L}c_{l t}\mu_{c l t}\right)d t+\left(\sum_{l=1}^{L}c_{l t}\sigma_{c l t}\right)^{\top}d z_{t}}}\ {\displaystyle{~\equiv C_{t}\left[\mu_{C t}d t+\pmb{\sigma}_{C t}^{\top}d z_{t}\right],}}\end{array}
$$  

where $\begin{array}{r}{\mu_{C t}\equiv\left(\sum_{l=1}^{L}c_{l t}\mu_{c l t}\right)/C_{t}}\end{array}$ and $\begin{array}{r}{\pmb{\sigma}_{C t}=\left(\sum_{l=1}^{L}c_{l t}\pmb{\sigma}_{c l t}\right)/C_{t}}\end{array}$ . We know from (8.25) that  

$$
\mu_{i t}+\delta_{i t}-r_{t}^{f}=A_{l}(c_{l t})c_{l t}\pmb{\sigma}_{i t}^{\top}\pmb{\sigma}_{c l t},\quad l=1,\ldots,L,
$$  

where $A_{l}(c_{l t})\equiv-u_{l}^{\prime\prime}(c_{l t})/u_{l}^{\prime}(c_{l t})$ is the absolute risk aversion of individual $\textit{l}$ . Consequently,  

$$
\left(\mu_{i t}+\delta_{i t}-r_{t}^{f}\right)\frac{1}{A_{l}(c_{l t})}=c_{l t}\pmb{\sigma}_{i t}^{\top}\pmb{\sigma}_{c l t},\quad l=1,\ldots,L,
$$  

and summing up over $l$ , we get  

$$
\left(\mu_{i t}+\delta_{i t}-r_{t}^{f}\right)\sum_{l=1}^{L}\left(\frac{1}{A_{l}(c_{l t})}\right)=\sigma_{i t}^{\top}\left(\sum_{l=1}^{L}c_{l t}\sigma_{c l t}\right)=\sigma_{i t}^{\top}\left(C_{t}\sigma_{C t}\right).
$$  

Therefore, we have the following relation between excess expected returns and aggregate consumption:  

$$
\mu_{i t}+\delta_{i t}-r_{t}^{f}=\frac{C_{t}}{\sum_{l=1}^{L}\left(\frac{1}{A_{l}\left(c_{l t}\right)}\right)}\pmb{\sigma}_{i t}^{\top}\pmb{\sigma}_{C t}.
$$  

Relative to the complete markets version (8.25), the only difference is that the relative risk aversion of the representative individual is replaced by some complicated average of the risk aversions of the individuals. Note that if all individuals have CRRA utility with identical relative risk aversions, then $A_{l}(c_{l t})=\gamma/c_{l t}$ and the multilier $\begin{array}{r}{C_{t}/\sum_{l=1}^{L}\left(\frac{1}{A_{l}\left(c_{l t}\right)}\right)}\end{array}$ in the above equation reduces to $\gamma$  

The Consumption-based CAPM is a very general asset pricing result. Basically any asset pricing. model can be seen as a special case of the Consumption-based CAPM. On the other hand, the general Consumption-based CAPM is not very useful for applications without further assumptions. Therefore we turn now to more specific consumption-based models..  
