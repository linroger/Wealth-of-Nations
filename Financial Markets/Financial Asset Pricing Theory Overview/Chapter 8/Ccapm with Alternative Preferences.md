---
tags:
  - ccapm
  - consumption_based_model
  - habit_formation
  - risk_aversion
  - state_dependent_preferences
aliases:
  - Alternative Preferences
  - CCAPM
key_concepts:
  - consumption-based model
  - habit formation
  - relative risk aversion
  - risk-free asset
  - state-price deflator
---

# 8.7 CCAPM with alternative preferences  

An interesting alternative to the simple consumption-based model is to allow the utility of a given. consumption level at a given point in time. $t$ to depend on some benchmark $X_{t}$ , i.e. the preferences are modeled bye $\operatorname{E}[\int_{0}^{T}e^{-\delta t}u(c_{t},X_{t})d t]$ in continuous time ord $\operatorname{E}[\sum_{t=0}^{T}e^{-\delta t}u(c_{t},X_{t})]$ in discrete time. This incorporates the case of (internal) habit formation where $X_{t}$ is determined as a weighted average of the previous consumption rates of the individual, and the case of state-dependent (or. "external habit"') preferences where $X_{t}$ is a variable not affected by the consumption decisions of. the individual. If we assume that a high value of the benchmark means that the individual will be more eager to increase consumption, as is the case with (internal) habit formation, we should. have $u_{c X}(c,X)>0$  

Typically, models apply one of two tractable specifications of the utility function. The first specification is  

$$
u(c_{t},X_{t})=\frac{1}{1-\gamma}\left(c_{t}-X_{t}\right)^{1-\gamma},\quad\gamma>0,
$$  

which is defined for $c_{t}>X_{t}$ . Marginal utility is  

$$
u_{c}(c_{t},X_{t})=\left(c_{t}-X_{t}\right)^{-\gamma},
$$  

and the relative risk aversion is  

$$
-\frac{c_{t}u_{c c}(c_{t},X_{t})}{u_{c}(c_{t},X_{t})}=\gamma\frac{c_{t}}{c_{t}-X_{t}},
$$  

which is no longer constant and is greater than. $\gamma$ . This will allow us to match historical consumption. and stock market data with a lower value of the parameter. $\gamma$ , but it is more reasonable to study. whether we can match the data with a fairly low average value of the relative risk aversion given by (8.35). The second tractable specification is.  

$$
u(c_{t},X_{t})=\frac{1}{1-\gamma}\left(\frac{c_{t}}{X_{t}}\right)^{1-\gamma},\quad\gamma>0,
$$  

which is defined for $c_{t},X_{t}>0$ . Since  

$$
u_{c}(c,X)=c^{-\gamma}X^{\gamma-1},\qquadu_{c X}(c,X)=(\gamma-1)c^{-\gamma}X^{\gamma-2}
$$  

we need $\gamma>1$ to ensure that marginal utility is increasing in. $X$ . Despite the generalization of the. utility function relative to the standard model, the relative risk aversion is still constant:  

$$
-\frac{c u_{c c}(c,X)}{u_{c}(c,X;\gamma)}=\gamma.
$$  

# 8.7.1 Habit formation  

In the case with (internal) habit formation the individual will appreciate a given level of consumption at a given date higher if she is used to low consumption than if she is used to high. consumption. Such a representation of preferences is still consistent with the von Neumann and Morgenstern (1944) axioms of expected utility but violates the time-additivity of utility typically. assumed. A rational individual with an internal habit will take into account the effects of her current decisions on the future habit levels. We saw in Chapter 6 that this will considerably complicate the formulas for optimal consumption and for the associated state-price deflator..  

Individuals with habit formation in preferences will other things equal invest more in the risk-. free asset in order to ensure that future consumption will not come very close to (or even below) the future habit level. This extra demand for the risk-free asset will lower the equilibrium interest rate and, hence, help resolve the risk-free rate puzzle. Moreover, we see from (8.35) that the risk aversion is higher in "bad states" where current consumption is close to the habit level than in. "good states" of high current consumption relative to the benchmark. This will be reflected by. the risk premia of risky assets and has the potential to explain the observed cyclical behavior of. expected returns.  

As we have seen in Chapter 6 the state-price deflators that can be derived from individuals with internal habit formation are considerably more complex than with time-additive preferences or external habit formation. A general and rather abstract continuous-time analysis for the case of an internal habit defined by a weighted average of earlier consumption rates is given by Detemple and Zapatero (1991).  

Only very few concrete asset pricing models with internal habit have been developed with the continuous-time model of Constantinides (1990) as the most frequently cited. The model of Constantinides assumes a representative individual who can invest in a risk-free asset and a single risky asset. A priori, the risk-free rate and the expected rate of return and the volatility of the risky asset are assumed to be constant. The utility of the individual is given by (8.34), where the habit level is a weighted average of consumption at all previous dates. Constantinides solves for the optimal consumption and investment strategies of the individual and shows that the optimal consumption rate varies much less over time in the model with habit formation than with the usual time-additive specification of utility. A calibration of the model to historical data shows that the model is consistent with a large equity premium and a low risk aversion but, on the other hand, the consumption process of the model has an unrealistically high auto-correlation and the variance of long-term consumption growth is quite high. By construction, the model cannot explain variations in interest rates and expected returns on stocks.  

# 8.7.2 State-dependent utility: general results  

With an external habit/benchmark, e.g. given by the aggregate consumption level, the state-price deflator is  

$$
\zeta_{t}=e^{-\delta t}\frac{u_{c}(c_{t},X_{t})}{u_{c}(c_{0},X_{0})},
$$  

where the only difference to the model without habit is that the marginal utilities depend on the habit level. An external habit formalizes the idea that the marginal utility of consumption of one individual is increasing in the consumption level of other individuals (sometimes referred to as the "keeping up with the Jones'es" effect). In this case, there is no effect of the consumption choice of the individual on the future benchmark levels, but of course the individual will include her knowledge of the dynamics of the benchmark when making consumption decisions.  

In a discrete-time setting the one-period deflator is  

$$
\frac{\zeta_{t+1}}{\zeta_{t}}=e^{-\delta}\frac{u_{c}(c_{t+1},X_{t+1})}{u_{c}(c_{t},X_{t})}.
$$  

Using the Taylor approximation  

$$
u_{c}(c_{t+1},X_{t+1})\approx u_{c}(c_{t},X_{t})+u_{c c}(c_{t},X_{t})\Delta c_{t+1}+u_{c X}(c_{t},X_{t})\Delta X_{t+1},
$$  

the approximate relation  

$$
\operatorname{E}_{t}[R_{i,t+1}]-R_{t}^{f}\approx\left(-\frac{c_{t}u_{c c}(c_{t},X_{t})}{u_{c}(c_{t},X_{t})}\right)\operatorname{Cov}_{t}\left[R_{i,t+1},\frac{\Delta c_{t+1}}{c_{t}}\right]-\frac{u_{c x}(c_{t},X_{t})}{u_{c}(c_{t},X_{t})}\operatorname{Cov}_{t}\left[R_{i,t+1},\Delta X_{t+1}\right]
$$  

can be derived. The covariance of return with the benchmark variable adds a term to the excess expected return of a risky asset. Moreover, the relative risk aversion in the first term will now generally vary with the benchmark variable.  

In a continuous-time setting where the dynamics of consumption is again given by (8.21) and the dynamics of the benchmark process $X=\left(X_{t}\right)$ is of the form  

$$
d X_{t}=\mu_{X}{\mathrm{}}_{t}d t+\pmb{\sigma}_{X}^{\top}d z_{t},
$$  

an application of It $\hat{\mathrm{~o~}}$ 's Lemma will give the dynamics of the state-price deflator. As before, the. risk-free rate and the market price of risk can be identified from the drift and the sensitivity,. respectively, of the state-price deflator. The following theorem states the conclusion. Exercise 8.3 asks for the proof.  

Theorem 8.2 In a continuous-time economy where the optimal consumption process of an indi-. vidual with state-dependent expected utility satisfies (8.21) and the dynamics of the benchmark is given by (8.38), the continuously compounded risk-free short-term interest rate satisfies.  

$$
\begin{array}{l}{{\displaystyle r_{t}^{f}=\delta+\frac{-c_{t}u_{c c}(c_{t},X_{t})}{u_{c}(c_{t},X_{t})}\mu_{c t}-\frac{1}{2}\frac{c_{t}^{2}u_{c c c}(c_{t},X_{t})}{u_{c}(c_{t},X_{t})}\|{\pmb\sigma}_{c t}\|^{2}}}\ {{\displaystyle\qquad-\frac{u_{c X}(c_{t},X_{t})}{u_{c}(c_{t},X_{t})}\mu_{X t}-\frac{1}{2}\frac{u_{c X X X}(c_{t},X_{t})}{u_{c}(c_{t},X_{t})}\|{\pmb\sigma}_{X t}\|^{2}-\frac{c_{t}u_{c c X}(c_{t},X_{t})}{u_{c}(c_{t},X_{t})}\pmb{\sigma}_{c t}^{\top}{\pmb\sigma}_{X t}}}\end{array}
$$  

and  

$$
\lambda_{t}=\frac{-c_{t}u_{c c}(c_{t},X_{t})}{u_{c}(c_{t},X_{t})}\pmb{\sigma}_{c t}-\frac{u_{c X}(c_{t},X_{t})}{u_{c}(c_{t},X_{t})}\pmb{\sigma}_{X t}
$$  

defines a market price of risk process. In particular, the excess expected rate of return on asset i is  

$$
\mu_{i t}+\delta_{i t}-r_{t}^{f}=\frac{-c_{t}u_{c c}(c_{t},X_{t})}{u_{c}(c_{t},X_{t})}\pmb{\sigma}_{i t}^{\top}\pmb{\sigma}_{c t}-\frac{u_{c X}(c_{t},X_{t})}{u_{c}(c_{t},X_{t})}\pmb{\sigma}_{i t}^{\top}\pmb{\sigma}_{X t}.
$$  

Assuming $u_{C X}(c,X)>0$ , we see from (8.40) that, if $\sigma_{X t}$ goes in the same direction as $\sigma_{\mathit{c t}}$ state-dependent utility will tend to lower the market price of risk, working against a resolution of the equity premium puzzle. On the other hand there is much more room for time variation in both the risk-free rate and the market price of risk, which can help explain the predictability puzzle.  

Again, the above results hold for aggregate consumption if a representative individual with. preferences of the given form exists. If ${\pmb\sigma}_{X t}={\bf0}$ , we can link asset prices to aggregate consumption without assuming the existence of a representative individual, as in the case of standard preferences. We obtain  

$$
\mu_{i t}+\delta_{i t}-r_{t}^{f}=\frac{C_{t}}{\sum_{l=1}^{L}\left(\frac{1}{A_{l}\left(c_{l t},X_{t}\right)}\right)}\pmb{\sigma}_{i t}^{\top}\pmb{\sigma}_{C t},
$$  

where $C_{t}$ is aggregate consumption and $A_{l}(c_{l t},X_{t})=-u_{c c}^{l}(c_{l t},X_{t})/u_{c}^{l}(c_{l t},X_{t})$ is the (now statedependent) absolute risk aversion of individual $l$  

# 8.7.3 The Campbell and Cochrane model  

Campbell and Cochrane (1999) suggest a discrete-time model of an economy with identical individuals with utility functions like (8.34), where $X_{t}$ is the benchmark or external habit level. The "next-period deflator' is then  

$$
m_{t+1}\equiv\frac{\zeta_{t+1}}{\zeta_{t}}=e^{-\delta}\frac{(c_{t+1}-X_{t+1})^{-\gamma}}{(c_{t}-X_{t})^{-\gamma}}.
$$  

The lognormal distributional assumption for aggregate consumption made in the simple model seems to be empirically reasonable so the Campbell and Cochrane model keeps that assumption. Since it is not obvious what distributional assumption on $X_{t}$ that will make the model computationally tractable, Campbell and Cochrane define the "surplus consumption ratio" $S_{t}=(c_{t}-X_{t})/c_{t}$ in terms of which the "next-period deflator" can be rewritten as  

$$
m_{t+1}=e^{-\delta}\left(\frac{c_{t+1}}{c_{t}}\right)^{-\gamma}\left(\frac{S_{t+1}}{S_{t}}\right)^{-\gamma}=\exp\left\{-\delta-\gamma\ln\left(\frac{c_{t+1}}{c_{t}}\right)-\gamma\ln\left(\frac{S_{t+1}}{S_{t}}\right)\right\}.
$$  

It is assumed that changes in both consumption growth and the surplus consumption ratio are conditionally lognormally distributed with  

$$
\begin{array}{r l}&{\ln\left(\frac{c_{t+1}}{c_{t}}\right)=\bar{g}+\nu_{t+1},}\ &{\ln\left(\frac{S_{t+1}}{S_{t}}\right)=(1-\varphi)\left(\ln\bar{S}-\ln S_{t}\right)+\Lambda(S_{t})\nu_{t+1},}\end{array}
$$  

where $\nu_{t+1}\sim N(0,\sigma^{2})$ and the function $\Lambda$ is specified below with the purpose of obtaining some desired properties. With lognormality of $c_{t+1}$ and $S_{t+1}$ $c_{t+1}-X_{t+1}=c_{t+1}S_{t+1}$ and therefore the next-period deflator will also be lognormal. Note that $\ln S_{t}$ will fluctuate around $\ln S$ , which may think of as representing business cycles with low values of $\ln S_{t}$ corresponding to bad times with relatively low consumption. Also note that the consumption and the surplus consumption ratios are perfectly correlated.  

The distributional assumption on the surplus consumption ratio ensures that it stays positive so that $c_{t}>X_{t}$ , as required by the utility specification. On the other hand, if you want the benchmark $X_{t}$ to stay positive, the surplus consumption ratio must be smaller than 1, which is not ensured by the lognormal distribution. According to Campbell, Lo, and MacKinlay (1997, p. 331), it can be shown that  

$$
\ln X_{t+1}\approx\ln(1-{\bar{S}})+{\frac{g}{1-\varphi}}+(1-\varphi)\sum_{j=0}^{\infty}\varphi^{j}\ln c_{t+j}
$$  

so that the benchmark is related to a weighted average of past consumption levels.  

With the above assumptions, the next-period deflator $r n_{t+1}$ is  

$$
m_{t+1}=\exp\left\{-\delta-\gamma\left[\bar{g}-\left(1-\varphi\right)\ln\frac{S_{t}}{\bar{S}}\right]-\gamma\left(1+\Lambda(S_{t})\right)\nu_{t+1}\right\},
$$  

which is conditionally lognormally distributed with  

$$
\frac{\sigma_{t}[m_{t+1}]}{\operatorname{E}_{t}[m_{t+1}]}=\sqrt{\exp\left\{\gamma^{2}\sigma^{2}(1+\Lambda(S_{t}))^{2}\right\}-1}\approx\gamma\sigma\left(1+\Lambda(S_{t})\right).
$$  

(Again the approximation is not that accurate for the parameter values necessary to match consumption and return data.) It follows from (4.26) that the expected excess gross return on a risky asset is  

$$
\begin{array}{r}{\mathrm{E}_{t}[R_{i,t+1}]-R_{t}^{f}\approx-\gamma\sigma\left(1+\Lambda(S_{t})\right)\rho_{t}\left[m_{t+1},R_{i,t+1}\right]\sigma_{t}[R_{i,t+1}].}\end{array}
$$  

The variation in risk aversion through $S_{t}$ increases the risk premium relative to the standard model, cf. (8.30). In order to obtain the counter-cyclical variation in risk premia observed in data, $\Lambda$ has to be a decreasing function of $S$  

The continuously compounded short-term risk-free rate is  

$$
\ln{\cal R}_{t}^{f}=\ln\left(\frac{1}{\mathrm{E}_{t}[m_{t+1}]}\right)=\delta+\gamma\bar{g}-\frac{1}{2}\gamma^{2}\sigma^{2}-\gamma(1-\varphi)\ln\frac{S_{t}}{\bar{S}}-\frac{1}{2}\gamma^{2}\sigma^{2}\Lambda(S_{t})\left(\Lambda(S_{t})+2\right).
$$  

In comparison with the expression (8.29) for the risk-free rate in the simple model, the last two. terms on the right-hand side are new. Note that. $S_{t}$ has opposite effects on the two new terms. A low value of. $S_{t}$ means that the marginal utility of consumption is high so that individuals will. try to borrow money for current consumption. This added demand for short-term borrowing will drive up the equilibrium interest rate. On the other hand, a low. $S_{t}$ will also increase the risk. aversion and, hence, precautionary savings with a lower equilibrium rate as a result. Campbell. and Cochrane fix $\Lambda(\cdot)$ and $S$ at  

$$
\Lambda(S_{t})=\frac{1}{\bar{S}}\sqrt{1-2\ln(S_{t}/\bar{S})}-1,\qquad\bar{S}=\sigma\sqrt{\gamma/(1-\varphi)}
$$  

so that the equilibrium interest rate is given by the constant  

$$
\ln{R^{f}}=\delta+\gamma\bar{g}-\frac{1}{2}\sigma^{2}\left(\frac{\gamma}{\bar{S}}\right)^{2}.
$$  

Note that $\Lambda(\cdot)$ is decreasing.2  

The authors calibrate the model to historical data for consumption growth, interest rates, and. the average Sharpe ratio, which for example requires that. $\gamma=2$ and $S=0.057$ . The calibrated model is consistent with the observed counter-cyclical variation in expected returns, standard deviations of returns, and the Sharpe ratio. With the given parameter values the model can therefore explain the predictability in those variables. The calibrated model yields empirically reasonable levels of the expected return and standard deviation of stock returns but note that, although the calibrated value of the utility parameter $\gamma$ is small, the relative risk aversion $\gamma/S_{t}$ is still high. With $S_{t}=S=0.057$ , the risk aversion is approximately 35, and the risk aversion. is much higher in bad states where $S_{t}$ is low. The model can therefore not explain the equity premium puzzle. Also observe that the value of $S$ implies an average habit level only 5.7% lower than current consumption, which seems to be an extreme degree of habit formation. Finally, note that the dynamics of the business cycle variable. $S_{t}$ is exogenously chosen to obtain the desired properties of the model. It would be interesting to understand how such a process could arise endogenously.  

# 8.7.4 The Chan and Kogan model  

In many models for individual consumption and portfolio choice the individual is assumed to have constant relative risk aversion both because this seems quite reasonable and because this. simplifies the analysis. If all individuals in an economy have constant relative risk aversion, you might think that a representative individual would also have constant relative risk aversion, but as pointed out by Chan and Kogan (2002) this is only true if they all have the same level of risk. aversion. Individuals with a low (constant) relative risk aversion will other things equal invest a larger fraction of their wealth in risky assets, e.g. stocks, than individuals with high (constant) relative risk aversion. Increasing stock prices will imply that the wealth of the relatively risk tolerant individuals will grow more than the wealth of comparably more risk averse individuals. Consequently, the aggregate risk aversion in the economy (corresponding to the risk aversion of a. representative individual) will fall. Conversely, the aggregate risk aversion will increase when stock markets drop. This simple observation supports the assumption of Campbell and Cochrane (1999) discussed above that the risk aversion of the representative individual varies counter-cyclically, which helps in resolving asset pricing puzzles.  

Let us take a closer look at the model of Chan and Kogan (2002). It is a continuous-time exchange economy in which the aggregate endowment/consumption. $Y=\left(Y_{t}\right)$ follows the a geometric Brownian motion  

$$
d Y_{t}=Y_{t}[\mu d t+\sigma d z_{t}].
$$  

where $\mu>\sigma^{2}/2$ $\sigma>0$ , and $z~=~\left(z_{t}\right)$ is a one-dimensional standard Brownian motion. Two assets are traded: a risky asset which is a unit net supply and pays a continuous dividend equal to the aggregate endowment, and an instantaneously risk-free asset (a bank account) generating a continuously compounded short-term interest rate of. $\boldsymbol{r}_{t}^{f}$ . The economy is populated with infinitely-. lived individuals maximizing time-additive state-dependent utility given by (8.36), i.e.  

$$
\operatorname{E}\left[\int_{0}^{\infty}e^{-\delta t}u(c_{t},X_{t};\gamma)d t\right],\quad u(c,X;\gamma)={\frac{1}{1-\gamma}}\left({\frac{c}{X}}\right)^{1-\gamma}.
$$  

Here $X$ is an external benchmark, e.g. an index of the standard of living in the economy. Let  

$x_{t}=\ln X_{t}$ and $\boldsymbol{y}_{t}=\ln\boldsymbol{Y}_{t}$ . The dynamics of the benchmark is modeled through  

$$
x_{t}=e^{-\kappa t}x_{0}+\kappa\int_{0}^{t}e^{-\kappa(t-s)}y_{s}d s
$$  

so that  

$$
d x_{t}=\kappa\left(y_{t}-x_{t}\right)d t.
$$  

The log-benchmark is a weighted average of past log-consumption. The relative log-consumption variable $\omega_{t}=y_{t}-x_{t}$ will be representative of the state of the economy. A high (low) value of $\omega_{t}$ represents a good (bad) state in terms of aggregate consumption relative to the benchmark. Note that  

$$
d\omega_{t}=d y_{t}-d x_{t}=\kappa\left(\bar{\omega}-\omega_{t}\right)d t+\sigma d z_{t},
$$  

where $\bar{\omega}=(\mu-\sigma^{2}/2)/\kappa$  

Individuals are assumed to differ with respect to their relative risk aversion $\gamma$ but to have identical subjective time preference parameters $\delta$ . Since the market is complete, an equilibrium in the economy will be Pareto-optimal and identical to the solution of the problem of a central planner or representative individual. Let $f(\gamma)$ denote the weight of the individuals with relative risk aversion $\gamma$ in this problem, where we normalize so that $\textstyle\int_{1}^{\infty}f(\gamma)=1$ . The problem of the central planner is to solve  

$$
\begin{array}{r l}&{\displaystyle\operatorname*{sup}_{\{c_{t}(Y_{t},X_{t};\gamma);\gamma>1,t\geq0\}}\operatorname E\left[\int_{0}^{\infty}e^{-\delta t}\left(\int_{1}^{\infty}f(\gamma)\frac{1}{1-\gamma}\left(\frac{c_{t}(Y_{t},X_{t};\gamma)}{X_{t}}\right)^{1-\gamma}d\gamma\right)d t\right]}\ &{\displaystyle\mathrm{s.t.}\int_{1}^{\infty}c_{t}(Y_{t},X_{t};\gamma)d\gamma\leq Y_{t},\quad t\geq0.}\end{array}
$$  

In an exchange economy no intertemporal transfer of resources are possible at the aggregate level so the optimal value of the central planner's objective function will be $\begin{array}{r}{\operatorname{E}[\int_{0}^{\infty}e^{-\delta t}U(Y_{t},X_{t})d t]}\end{array}$ where  

$$
^{r_{J}}(Y_{t},X_{t})=\operatorname*{sup}_{\{c_{t}(Y_{t},X_{t};\gamma);\gamma>1\}}\left\{\int_{1}^{\infty}f(\gamma)\frac{1}{1-\gamma}\left(\frac{c_{t}(Y_{t},X_{t};\gamma)}{X_{t}}\right)^{1-\gamma}d\gamma\Big|\int_{1}^{\infty}c_{t}(Y_{t},X_{t};\gamma)d\gamma\leq Y_{t}\right\}.
$$  

The solution to this problem is characterized in the following theorem, which is the key to the asset pricing results in this model.  

Theorem 8.3 The optimal consumption allocation in the problem (8.44) is  

$$
c_{t}(Y_{t},X_{t};\gamma)=\alpha_{t}(\omega_{t};\gamma)Y_{t},\quad\alpha_{t}(\omega_{t};\gamma)=f(\gamma)^{1/\gamma}e^{-\frac{1}{\gamma}h(\omega_{t})-\omega_{t}},
$$  

where the function h is implicitly defined by the identity  

$$
\int_{1}^{\infty}f(\gamma)^{1/\gamma}e^{-{\frac{1}{\gamma}}h(\omega_{t})-\omega_{t}}d\gamma=1.
$$  

The utility function of the representative individual is  

$$
U(Y_{t},X_{t})=\int_{1}^{\infty}\frac{1}{1-\gamma}f(\gamma)^{1/\gamma}e^{-\frac{1-\gamma}{\gamma}h(\omega_{t})}d\gamma.
$$  

Proof: If we divide the constraint in (8.44) through by $X_{t}$ and introduce the aggregate consump-.   
tion share $\alpha_{t}(Y_{t},X_{t};\gamma)=c_{t}(Y_{t},X_{t};\gamma)/Y_{t}$ , the Lagrangian for the optimization problem is.  

$$
\begin{array}{l}{\displaystyle{\mathcal{L}_{t}=\int_{1}^{\infty}f(\gamma)\frac{1}{1-\gamma}\left(\alpha_{t}(Y_{t},X_{t};\gamma)\frac{Y_{t}}{X_{t}}\right)^{1-\gamma}d\gamma+H_{t}\left(\frac{Y_{t}}{X_{t}}-\int_{1}^{\infty}\alpha_{t}(Y_{t},X_{t};\gamma)\frac{Y_{t}}{X_{t}}d\gamma\right)}}\ {\displaystyle{\quad=\frac{Y_{t}}{X_{t}}\int_{1}^{\infty}\left[f(\gamma)\frac{1}{1-\gamma}\alpha_{t}(Y_{t},X_{t};\gamma)^{1-\gamma}\left(\frac{Y_{t}}{X_{t}}\right)^{-\gamma}-H_{t}\alpha_{t}(Y_{t},X_{t};\gamma)\right]d\gamma+H_{t}\frac{Y_{t}}{X_{t}}},}\end{array}
$$  

where $H_{t}$ is the Lagrange multiplier. The first-order condition for $\alpha_{t}$ implies that  

$$
\alpha_{t}(Y_{t},X_{t};\gamma)=H_{t}^{-1/\gamma}f(\gamma)^{1/\gamma}\left(\frac{Y_{t}}{X_{t}}\right)^{-1}=f(\gamma)^{1/\gamma}e^{-\frac{1}{\gamma}h_{t}-\omega_{t}},
$$  

where $h_{t}=\ln H_{t}$ . The consumption allocated to all individuals must add up to the aggregate. consumption, which implies the condition (8.46). From the condition, it is clear that $h_{t}$ and therefore $\alpha_{t}$ depends on $\omega_{t}$ but not separately on $Y_{t}$ and $X_{t}$  

The maximum of the objective function is  

$$
\begin{array}{l}{\displaystyle{U(Y_{t},X_{t})=\int_{1}^{\infty}f(\gamma)\frac{1}{1-\gamma}\left(\alpha_{t}(Y_{t},X_{t};\gamma)\frac{Y_{t}}{X_{t}}\right)^{1-\gamma}d\gamma}}\ {~=\displaystyle\int_{1}^{\infty}f(\gamma)\frac{1}{1-\gamma}f(\gamma)^{(1-\gamma)/\gamma}e^{-\frac{1-\gamma}{\gamma}h(\omega_{t})-(1-\gamma)\omega_{t}}e^{(1-\gamma)\omega_{t}}d\gamma}\ {~=\displaystyle\int_{1}^{\infty}\frac{1}{1-\gamma}f(\gamma)^{1/\gamma}e^{-\frac{1-\gamma}{\gamma}h(\omega_{t})}d\gamma,}\end{array}
$$  

which ends the proof.  

The optimal allocation of consumption to a given individual is a fraction of aggregate endowment,. a fraction depending on the state of the economy and the relative risk aversion of the individual.  

The next lemma summarizes some properties of the function $h$ which will be useful in the following discussion.  

Lemma 8.1 The function h defined in (8.46) is decreasing and convex with  

$$
h^{\prime}(\omega)=-\left(\int_{1}^{\infty}\frac{1}{\gamma}f(\gamma)^{1/\gamma}e^{-\frac{1}{\gamma}h(\omega)-\omega}d\gamma\right)^{-1}<-1.
$$  

Proof: Differentiating with respect to $\omega_{t}$ in (8.46), we get  

$$
\int_{1}^{\infty}f(\gamma)^{1/\gamma}e^{-\frac{1}{\gamma}h(\omega_{t})-\omega_{t}}\left(-\frac{1}{\gamma}h^{\prime}(\omega_{t})-1\right)d\gamma=0,
$$  

which implies that  

$$
h^{\prime}(\omega_{t})\int_{1}^{\infty}\frac{1}{\gamma}f(\gamma)^{1/\gamma}e^{-\frac{1}{\gamma}h(\omega_{t})-\omega_{t}}d\gamma=-\int_{1}^{\infty}f(\gamma)^{1/\gamma}e^{-\frac{1}{\gamma}h(\omega_{t})-\omega_{t}}d\gamma=-1,
$$  

from which the expression for $h^{\prime}(\omega_{t})$ follows. Since we are integrating over $\gamma\geq1$  

$$
\int_{1}^{\infty}\frac{1}{\gamma}f(\gamma)^{1/\gamma}e^{-\frac{1}{\gamma}h(\omega_{t})-\omega_{t}}d\gamma<\int_{1}^{\infty}f(\gamma)^{1/\gamma}e^{-\frac{1}{\gamma}h(\omega_{t})-\omega_{t}}d\gamma=1,
$$  

which gives the upper bound on $h^{\prime}(\omega_{t})$  

Convexity means $h^{\prime\prime}(\omega_{t})\geq0$ and by differentiating (8.48) we see that this is true if and only if  

$$
-h^{\prime}(\omega)\int_{1}^{\infty}\frac{1}{\gamma^{2}}f(\gamma)^{1/\gamma}e^{-\frac{1}{\gamma}h(\omega)-\omega}d\gamma\geq\int_{1}^{\infty}\frac{1}{\gamma}f(\gamma)^{1/\gamma}e^{-\frac{1}{\gamma}h(\omega)-\omega}d\gamma,
$$  

i.e. if and only if  

$$
\int_{1}^{\infty}{\frac{1}{\gamma^{2}}}f(\gamma)^{1/\gamma}e^{-{\frac{1}{\gamma}}h(\omega)-\omega}d\gamma\geq\left(\int_{1}^{\infty}{\frac{1}{\gamma}}f(\gamma)^{1/\gamma}e^{-{\frac{1}{\gamma}}h(\omega)-\omega}d\gamma\right)^{2}.
$$  

In order to show this we apply the Cauchy-Schwartz inequality for integrals,  

$$
\left(\int_{a}^{b}F(x)G(x)d x\right)^{2}\leq\left(\int_{a}^{b}F(x)^{2}d x\right)\left(\int_{a}^{b}G(x)^{2}d x\right),
$$  

with $x=\gamma$ $a=1$ $b=\infty$ , and  

$$
F(x)=\frac{1}{\gamma}\left(f(\gamma)^{1/\gamma}e^{-\frac{1}{\gamma}h(\omega)-\omega}\right)^{1/2},\quad G(x)=\left(f(\gamma)^{1/\gamma}e^{-\frac{1}{\gamma}h(\omega)-\omega}\right)^{1/2}.
$$  

By the Cauchy-Schwartz inequality and (8.46), we get exactly  

$$
\begin{aligned}
\left(
  \int_{1}^{\infty}
    \frac{1}{\gamma} f(\gamma)^{1/\gamma}
    e^{ -\frac{1}{\gamma} h(\omega) - \omega }
  \, d\gamma
\right)^2
&\leq
\left(
  \int_{1}^{\infty}
    \frac{1}{\gamma^2} f(\gamma)^{1/\gamma}
    e^{ -\frac{1}{\gamma} h(\omega) - \omega }
  \, d\gamma
\right)
\left(
  \int_{1}^{\infty}
    f(\gamma)^{1/\gamma}
    e^{ -\frac{1}{\gamma} h(\omega) - \omega }
  \, d\gamma
\right) \\
&=
\int_{1}^{\infty}
  \frac{1}{\gamma^2} f(\gamma)^{1/\gamma}
  e^{ -\frac{1}{\gamma} h(\omega) - \omega }
\, d\gamma
\end{aligned}
$$  

as was to be shown.  

Using (8.46) and (8.48), straightforward differentiation of the utility function (8.47) gives that  

$$
\begin{array}{r l}&{{\cal U}_{\cal Y}(Y_{t},X_{t})={\cal X}_{t}^{-1}e^{h(\omega_{t})},}\ &{{\cal U}_{\cal Y Y}(Y_{t},X_{t})=h^{\prime}(\omega_{t}){\cal Y}_{t}^{-1}{\cal U}_{\cal Y}(Y_{t},X_{t}).}\end{array}
$$  

The relative risk aversion of the representative individual is therefore  

$$
-\frac{Y_{t}U_{Y Y}\left(Y_{t},X_{t}\right)}{U_{Y}\left(Y_{t},X_{t}\right)}=-h^{\prime}(\omega_{t}).
$$  

It follows from Lemma 8.1 that this relative risk aversion is greater than 1 and decreasing in the state variable $\omega_{t}$ . The intuition is that the individuals with low relative risk aversion will other. things equal invest more in the risky asset--and their wealth will therefore fluctuate more -than individuals with high relative risk aversion. In good states a larger fraction of the aggregate. resources will be held by individuals with low risk aversion than in bad states. The relative risk aversion of the representative individual, which is some sort of wealth-weighted average of the individual risk aversions, will therefore be lower in good states than in bad states. Aggregate. relative risk aversion is counter-cyclical..  

We can obtain the equilibrium risk-free rate and the market price of risk from Theorem 8.2. In the present model the dynamics of $X_{t}=e^{x_{t}}$ will be  

$$
d X_{t}=\kappa X_{t}\left(y_{t}-x_{t}\right)d t=\kappa X_{t}\omega_{t}d t,
$$  

which is locally insensitive to shocks corresponding to ${\pmb\sigma}_{X t}={\bf0}$ . This will simplify the formulas for the risk-free rate and the Sharpe ratio. Moreover,  

$$
\begin{array}{r l r}&{}&{U_{Y X}(Y_{t},X_{t})=-X_{t}^{-1}(1+h^{\prime}(\omega_{t}))U_{Y}(Y_{t},X_{t}),}\ &{}&{Y_{t}^{2}U_{Y Y Y}(Y_{t},X_{t})=\left(h^{\prime\prime}(\omega_{t})+h^{\prime}(\omega_{t})^{2}-h^{\prime}(\omega_{t})\right)U_{Y}(Y_{t},X_{t}).}\end{array}
$$  

We arrive at the following conclusion:  

Theorem 8.4 In the Chan and Kogan model the risk-free short-term interest rate is  

$$
r_{t}^{f}=\delta-h^{\prime}(\omega_{t})\kappa(\bar{\omega}-\omega_{t})+\kappa\omega_{t}-\frac{1}{2}\sigma^{2}\left(h^{\prime\prime}(\omega_{t})+h^{\prime}(\omega_{t})^{2}\right).
$$  

and the Sharpe ratio of a risky asset is  

$$
\frac{\mu_{t}+\delta_{t}-r_{t}^{f}}{\sigma_{t}}=-h^{\prime}(\omega_{t})\sigma,
$$  

which is decreasing in the state variable $\omega_{t}$  

In Exercise 8.4 you are asked to provide the details. In Exercise 8.5 you are asked to show how (8.56) follows from (8.42).  

The Sharpe ratio in the model varies counter-cyclically. In good states of the economy the. average relative risk aversion is relatively low and the risk premium necessary for markets clear is therefore also low. Conversely in bad states where the average relative risk aversion is high..  

# 8.7.5 Epstein-Zin utility  

Recall from Section 6.6 that in a discrete-time model with Epstein-Zin utility the next-period state-price deflator is given by  

$$
M_{t+1}\equiv\frac{\zeta_{t+1}}{\zeta_{t}}=e^{-\delta\theta}\left(\frac{c_{t+1}}{c_{t}}\right)^{-\theta/\psi}\left(R_{t+1}^{\pi_{t}}\right)^{\theta-1},
$$  

where $\delta$ is the subjective time preference rate (so that $b=e^{-\delta}$ is the subjective discount factor), $\psi$ is the elasticity of intertemporal substitution, and $\begin{array}{r}{\theta=(1-\gamma)/(1-\frac{1}{\psi})}\end{array}$ , where $\gamma$ is the relative risk aversion. Again note that if. $\gamma=1/\psi$ and thus $\theta=1$ , we are back to the traditional state-price. deflator for time-additive power utility,. $M_{t+1}=e^{-\delta}(c_{t+1}/c_{t})^{-\gamma}$ . Let $\begin{array}{r}{g_{t+1}=\ln\left(\frac{c_{t+1}}{c_{t}}\right)}\end{array}$ denote the log growth rate of consumption and let $r_{t+1}^{w}=\ln R_{t+1}^{\pi_{t}}$ denote the log return on the wealth of the. individual, which for a representative individual can be interpreted as the log return on a claim to aggregate consumption (in equilibrium: aggregate dividends including labor income. $-$ aggregate consumption). We can then write the log of the state-price deflator, $m_{t+1}=\ln M_{t+1}$ as  

$$
m_{t+1}=-\delta\theta-\frac{\theta}{\psi}g_{t+1}+\left(\theta-1\right)r_{t+1}^{w}.
$$  

Applying the state-price deflator to the "wealth portfolio' implies  

$$
\begin{array}{r}{\mathrm{E}_{t}\left[\frac{\zeta_{t+1}}{\zeta_{t}}e^{r_{t+1}^{w}}\right]=\mathrm{E}_{t}\left[e^{m_{t+1}+r_{t+1}^{w}}\right]=1\quad\Rightarrow\quad\mathrm{E}_{t}\left[e^{-\delta\theta-\frac{\theta}{\psi}g_{t+1}+\theta r_{t+1}^{w}}\right]=1.}\end{array}
$$  

Assume that log consumption growth $g_{t+1}$ and the log return on the wealth portfolio $r_{t+1}^{w}$ are jointly normally distributed with $g_{t+1}\sim N(\mu_{c},\sigma_{c}^{2})$ $r_{t+1}^{a}\sim N(\mu_{w},\sigma_{w}^{2})$ and $\mathrm{Cov}_{t}[g_{t+1},r_{t+1}^{w}]=\sigma_{c w}$ By the use of Theorem B.2 in Appendix B we find that  

$$
1=\mathrm{E}_{t}\left[e^{-\delta\theta-\frac{\theta}{\psi}g_{t+1}+\theta r_{t+1}^{w}}\right]=\exp\left\{-\delta\theta-\frac{\theta}{\psi}\mu_{c}+\theta\mu_{w}+\frac{1}{2}\frac{\theta^{2}}{\psi^{2}}\sigma_{c}^{2}+\frac{1}{2}\theta^{2}\sigma_{w}^{2}-\frac{\theta^{2}}{\psi}\sigma_{c w}\right\}.
$$  

This implies that  

$$
\mu_{w}=\delta+\frac{\mu_{c}}{\psi}-\frac{1}{2}\frac{\theta}{\psi^{2}}\sigma_{c}^{2}-\frac{1}{2}\theta\sigma_{w}^{2}+\frac{\theta}{\psi}\sigma_{c w},
$$  

which we shall make use of below.  

Applying the state-price deflator to the risk-free asset implies that the one-period risk-free log rate of return is  

$$
\begin{array}{l}{{r_{t}^{f}=-\ln\mathrm{E}_{t}\left[e^{m_{t+1}}\right]=-\ln\mathrm{E}_{t}\left[e^{-\delta\theta-\frac{\theta}{\psi}g_{t+1}+(\theta-1)r_{t+1}^{w}}\right]}}\ {{\mathrm{}=\delta\theta+\frac{\theta}{\psi}\mu_{c}+(1-\theta)\mu_{w}-\frac{1}{2}\frac{\theta^{2}}{\psi^{2}}\sigma_{c}^{2}-\frac{1}{2}(1-\theta)^{2}\sigma_{w}^{2}-\frac{\theta}{\psi}(1-\theta)\sigma_{c w}}}\ {{\mathrm{}=\delta+\frac{\mu_{c}}{\psi}-\frac{1}{2}\frac{\theta}{\psi^{2}}\sigma_{c}^{2}-\frac{1}{2}(1-\theta)\sigma_{w}^{2},}}\end{array}
$$  

where the last equality is due to (8.60). For the special case of power utility ( $\gamma=1/\psi$ $\theta=1$ ), we are of course back to $r_{t}^{f}=\delta+\gamma\mu-{\textstyle\frac{1}{2}}\gamma^{2}\sigma^{2}$ as in (8.29).  

Obviously, the extension from power utility to Epstein-Zin utility has some consequences for the risk-free rate. Not surprisingly, it is generally (the inverse of) the elasticity of intertemporal substitution that determines how expected consumption growth $\mu_{c}$ affects the equilibrium risk-free short rate. If investors expect a higher growth rate of consumption, they would want to borrow more in order to increase consumption now instead of in the next period, where the prospective high consumption would lead to low marginal utility. To ensure market clearing, the short rate would have to increase. If investors have a high elasticity of intertemporal substitution, a small increase in the short rate is sufficient. The last two terms in (8.61) can be seen as an adjustment for risk,. which now includes both consumption risk and wealth risk. If we take the stock market volatility as a rough approximation to the volatility of the wealth portfolio, typical estimates suggest that $\sigma_{w}^{2}$ is considerably higher then $\sigma_{c}^{2}$ . Clearly the precise values of the preferences parameters are therefore very important for the magnitude of the risk adjustment. In fact, if. $\theta$ is (much) larger than 1, $\begin{array}{r l}{-\frac{1}{2}\frac{\theta}{\psi^{2}}\sigma_{c}^{2}-\frac{1}{2}(1-\theta)\sigma_{w}^{2}}\end{array}$ can be positive.  

In the power utility model with a high risk aversion, the average risk-free rate typically gets. too high. With Epstein-Zin utility, we can have a high risk aversion without having a very low substitution parameter so Epstein-Zin utility can potentially help in explaining the risk-free rate. puzzle.  

The log return. $r_{t+1}^{i}$ on an arbitrary risky claim must satisfy  

$$
\begin{array}{r}{\mathrm{E}_{t}\left[e^{m_{t+1}+r_{t+1}^{i}}\right]=1\quad\Rightarrow\quad\mathrm{E}_{t}\left[e^{-\delta\theta-\frac{\theta}{\psi}g_{t+1}+(\theta-1)r_{t+1}^{w}+r_{t+1}^{i}}\right]=1.}\end{array}
$$  

Assuming that $g_{t+1}$ $r_{t+1}^{w}$ , and $r_{t+1}^{i}$ are jointly normally distributed, we get  

$$
\begin{array}{l}{{\tt\vert\tilde{\tau}\vert}_{t+1}^{i}]+\frac{1}{2}\mathrm{Var}_{t}[r_{t+1}^{i}]=\delta\theta+\frac{\theta}{\psi}\mu_{c}+(1-\theta)\mu_{w}-\frac{1}{2}\frac{\theta^{2}}{\psi^{2}}\sigma_{c}^{2}-\frac{1}{2}(1-\theta)^{2}\sigma_{w}^{2}}}\ {{\mathrm{~}-\frac{\theta}{\psi}(1-\theta)\sigma_{c w}+\frac{\theta}{\psi}\mathrm{Cov}_{t}[r_{t+1}^{i},g_{t+1}]+(1-\theta)\mathrm{Cov}_{t}[r_{t+1}^{i},r_{t+1}^{w}]}}\ {{\mathrm{~}=\delta+\frac{\mu_{c}}{\psi}-\frac{1}{2}\frac{\theta}{\psi^{2}}\sigma_{c}^{2}-\frac{1}{2}(1-\theta)\sigma_{w}^{2}+\frac{\theta}{\psi}\mathrm{Cov}_{t}[r_{t+1}^{i},g_{t+1}]+(1-\theta)\mathrm{Cov}_{t}[r_{t+1}^{i},r_{t+1}^{i}]}.}}\end{array}
$$  

again using (8.60). From (8.61) it is now clear that  

$$
\begin{array}{r l}&{\mathrm{E}_{t}[r_{t+1}^{i}]-r_{t}^{f}+\frac{1}{2}\mathrm{Var}_{t}[r_{t+1}^{i}]=\frac{\theta}{\psi}\mathrm{Cov}_{t}[r_{t+1}^{i},g_{t+1}]+(1-\theta)\mathrm{Cov}_{t}[r_{t+1}^{i},r_{t+1}^{w}]}\ &{\phantom{\mathrm{E}_{t}[r_{t+1}^{i}]-r_{t}^{f}+\frac{1}{2}\mathrm{Var}_{t}[r_{t+1}^{i}]}=\sigma_{t}[r_{t+1}^{i}]\left(\frac{\theta}{\psi}\sigma_{c}\rho_{i c}+(1-\theta)\sigma_{w}\rho_{i w}\right)}\ &{\phantom{\mathrm{E}_{t}[r_{t+1}^{i}]}=\sigma_{t}[r_{t+1}^{i}]\left(\frac{\gamma-1}{1-\psi}\sigma_{c}\rho_{i c}+\frac{1-\psi\gamma}{1-\psi}\sigma_{w}\rho_{i w}\right).}\end{array}
$$  

For the special case of power utility ( $\gamma=1/\psi$ $\theta=1$ ), the right-hand side reduces to $\gamma\operatorname{Cov}_{t}[r_{t+1}^{i},g_{t+1}]$ in agreement with (8.31). For $\theta=0$ (which requires a risk aversion of $^{1}$ , i.e. log utility), the risk premium equals $\operatorname{Cov}_{t}[r_{t+1}^{i},r_{t+1}^{w}]$ as in the classic CAPM. In general, the risk premium is a combination of the asset's covariances with consumption and with wealth. As mentioned above, $\sigma_{w}$ may be considerably higher than $\sigma_{c}$ . Let us assume that $\gamma>1$ . Then if. $\psi>1$ , we have. $\theta<0$ and thus a high weight on $\sigma_{w}$ . The right-hand side of (8.63) can therefore potentially be higher with Epstein-Zin utility than with power utility. As an example, suppose in line with the numbers used in the beginning of Section 8.5 that $\sigma_{t}[r_{t+1}^{i}]=0.2$ $\sigma_{c}~=~0.02$ $\rho_{i c}~=~0.2$ , and fix. $\gamma=10$ $\sigma_{w}=0.2$ , and $\rho_{i w}=0.2$ . Then the risk premium according to the power utility model is $5\times0.2\times0.02\times0.2=0.004=0.4\%$ . With an elasticity of intertemporal substitution of $\psi=1.5$ so that $\theta=-12$ , the risk premium becomes  

$$
0.2\times\left(\frac{-12}{1.5}\times0.02\times0.2+13\times0.2\times0.2\right)=0.0976=9.76\%
$$  

which is not far from historical estimates. (However, with these parameters and $\delta=\mu_{c}=0.02$ the risk-free rate becomes $-22.56\%$ so not all problems are solved.) The risk premium is highly sensitive to the value of $\psi$ . If we instead use $\psi=0.5$ , we get $\theta=4$ and a risk premium of $-1.76\%$ which is not what we are looking for.  

# 8.7.6 Durable goods  

