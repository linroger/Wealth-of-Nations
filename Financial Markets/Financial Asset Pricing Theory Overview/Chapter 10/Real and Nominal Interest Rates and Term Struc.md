---
tags:
  - asset_pricing
  - inflation
  - monetary_economies
  - real_nominal_rates
  - term_structure
aliases:
  - Nominal Interest Rates
  - Real vs Nominal Rates
key_concepts:
  - Expected inflation rate
  - Nominal state-price deflator
  - Real short-term interest rate
  - Real vs nominal bonds
  - Real, nominal interest rates
---

# 10.6 Real and nominal interest rates and term structures  

In the following we shall first derive some generally valid relations between real rates, nominal rates, and inflation and investigate the differences between real and nominal bonds. Then we will discuss two different types of models in which we can say more about real and nominal rates. The first setting follows the neoclassical tradition in assuming that monetary holdings do not affect the preferences of the individuals so that the presence of money has no effects on real rates and real asset returns. Hence, the relations derived earlier in this chapter still applies. However, several empirical findings indicate that the existence of money does have real effects. For example, real stock returns are negatively correlated with inflation and positively correlated with money growth. Also, assets that are positively correlated with inflation have a lower expected return.2 In the second setting we consider below, money is allowed to have real effects. Economies with this property are called monetary economies.  

# 10.6.1 Real and nominal asset pricing  

The relations between interest rates or yields and aggregate consumption and production obtained above apply to real interest rates or yields. The real short-term interest rate is the rate of return over the next instant of an asset that is risk-free in real terms, i.e. provides a certain purchasing power. A real yield of maturity $s$ is derived from the real price of a real zero-coupon bond maturing at time $s$ , i.e. a bond paying one consumption unit at time $s$ . In reality most deposit arrangements and traded bonds are nominal in the sense that the dividends they promise are pre-specified units of some currency, not some units of consumption goods. In this section we search for the link between real and nominal interest rates and yields.  

Recall the results we derived on real and nominal pricing in Section 4.5. Let us stick to the continuous-time framework. Let $F_{t}$ denote the price of the good in currency units at time. $t$ (or think of. $F_{t}$ as the value of the Consumer Price Index at time. $t$ ) A nominal dividend of $\tilde{D}_{t}$ corresponds to a real dividend of $D_{t}=\tilde{D}_{t}/F_{t}$ and a nominal price of $\tilde{P}_{t}$ corresponds to a real price of. $P_{t}=\tilde{P}_{t}/F_{t}$ . We have seen that a nominal state-price deflator $\tilde{\zeta}=(\tilde{\zeta}_{t})$ is related to a real state-price deflator $\zeta=\left(\zeta_{t}\right)$ via the equation  

$$
\tilde{\zeta}_{t}=\frac{\zeta_{t}}{F_{t}},~\mathrm{all}~t\in[0,T].
$$  

The nominal state-price deflator links nominal dividends to nominal prices in the same way that a real state-price deflator links real dividends to real prices.  

The real return on a nominally risk-free asset is generally stochastic (and conversely). The dynamics of the real state-price deflator is  

$$
d\zeta_{t}=-\zeta_{t}\left[r_{t}d t+\lambda_{t}^{\top}d z_{t}\right],
$$  

where $\boldsymbol r=(r_{t})$ is the short-term real interest rate and. $\lambda=\left(\lambda_{t}\right)$ is the market price of risk. The. dynamics of the price of the consumption good is written as  

$$
d F_{t}=F_{t}\left[\mu_{\varphi t}d t+\pmb{\sigma}_{\varphi t}^{\top}d z_{t}\right].
$$  

We interpret $\varphi_{t+d t}~=~d F_{t}/F_{t}$ as the realized inflation rate over the next instant, i.e. $\mu_{\varphi t}=$ $\mathrm{E}_{t}[\varphi_{t+d t}]/d t$ is the expected inflation rate, and $\sigma_{\varphi t}$ is the sensitivity vector of the inflation rate. Then we have shown that the nominal and the real short-term interest rates are related as follows  

$$
\tilde{r}_{t}=r_{t}+\mu_{\varphi t}-\|\pmb{\sigma}_{\varphi t}\|^{2}-\pmb{\sigma}_{\varphi t}^{\top}\pmb{\lambda}_{t},
$$  

i.e. the nominal short rate is equal to the real short rate plus the expected inlation rate minus the variance of the inflation rate minus a risk premium. The presence of the last two terms invalidates the Fisher relation, which says that the nominal interest rate is equal to the sum of the real interest rate and the expected inflation rate.  

An application of Ito's Lemma (Exercise 10.2) shows that the dynamics of the nominal state-price deflator is  

$$
\begin{array}{r}{d\tilde{\zeta}_{t}=-\tilde{\zeta}_{t}\left[\tilde{r}_{t}d t+\tilde{\lambda}_{t}^{\top}d z_{t}\right],}\end{array}
$$  

where $\tilde{\lambda}_{t}=\lambda_{t}+\sigma_{\varphi t}$ is the nominal market price of risk.  

The time $t$ real price of a real zero-coupon bond maturing at time $s$ is  

$$
B_{t}^{s}=\operatorname{E}_{t}\left[{\frac{\zeta_{s}}{\zeta_{t}}}\right]=\operatorname{E}_{t}\left[\exp\left\{-\int_{t}^{s}r_{u}d u-{\frac{1}{2}}\int_{t}^{s}\|\lambda_{u}\|^{2}d u-\int_{t}^{s}\lambda_{u}^{\top}d z_{u}\right\}\right].
$$  

The time $t$ nominal price of a nominal zero-coupon bond maturing at $T$ is  

$$
\tilde{B}_{t}^{T}=\mathrm{E}_{t}\left[\frac{\tilde{\zeta}_{T}}{\tilde{\zeta}_{t}}\right]=\mathrm{E}_{t}\left[\exp\left\{-\int_{t}^{s}\tilde{r}_{u}d u-\frac{1}{2}\int_{t}^{s}\|\tilde{\lambda}_{u}\|^{2}d u-\int_{t}^{s}\tilde{\lambda}_{u}^{\top}d z_{u}\right\}\right].
$$  

Clearly the prices of nominal bonds are related to the nominal short rate and the nominal market price of risk in exactly the same way as the prices of real bonds are related to the real short rate and. the real market price of risk. Models that are based on specific exogenous assumptions about the. short rate dynamics and the market price of risk can be applied both to real term structures and to nominal term structures but not simultaneously for both real and nominal term structures. This is indeed the case for most popular term structure models. However the equilibrium arguments. that some authors offer in support of a particular term structure model, cf. Section 10.5, typically apply to real interest rates and real market prices of risk. The same arguments cannot generally. support similar assumptions on nominal rates and market price of risk. Nevertheless, these models are often applied on nominal bonds and term structures..  

Above we derived an equilibrium relation between real and nominal short-term interest rates. What can we say about the relation between longer-term real and nominal interest rates? Applying. the well-known relation $\operatorname{Cov}[x,y]=\operatorname{E}[x y]-\operatorname{E}[x]\operatorname{E}[y]$ , we can write  

$$
\begin{array}{r l}&{\tilde{B}_{t}^{T}=\mathrm{E}_{t}\left[\frac{\zeta_{T}}{\zeta_{t}}\frac{F_{t}}{F_{T}}\right]}\ &{\quad\quad=\mathrm{E}_{t}\left[\frac{\zeta_{T}}{\zeta_{t}}\right]\mathrm{E}_{t}\left[\frac{F_{t}}{F_{T}}\right]+\mathrm{Cov}_{t}\left[\frac{\zeta_{T}}{\zeta_{t}},\frac{F_{t}}{F_{T}}\right]}\ &{\quad\quad=B_{t}^{T}\mathrm{E}_{t}\left[\frac{F_{t}}{F_{T}}\right]+\mathrm{Cov}_{t}\left[\frac{\zeta_{T}}{\zeta_{t}},\frac{F_{t}}{F_{T}}\right].}\end{array}
$$  

From the dynamics of the state-price deflator and the price index, we get  

$$
\begin{array}{l}{\displaystyle\frac{\zeta_{T}}{\zeta_{t}}=\exp\left\{-\int_{t}^{T}\left(r_{s}+\frac{1}{2}\|\lambda_{s}\|^{2}\right)d s-\int_{t}^{T}\lambda_{s}^{\top}d z_{s}\right\},}\ {\displaystyle\frac{F_{t}}{F_{T}}=\exp\left\{-\int_{t}^{T}\left(\mu_{\varphi s}-\frac{1}{2}\|\sigma_{\varphi s}\|^{2}\right)d s-\int_{t}^{T}\sigma_{\varphi s}^{\top}d z_{s}\right\},}\end{array}
$$  

which can be substituted into the above relation between prices on real and nominal bonds. How  
ever, the covariance-term on the right-hand side can only be explicitly computed under very special   
assumptions about the variations over time in $\lambda$ , and $r$ $\mu_{\varphi}$ $\sigma_{\varphi}$  

# 10.6.2 No real effects of inflation  

In this subsection we will take as given some process for the consumer price index and assume that monetary holdings do not affect the utility of the individuals directly. As before the aggregate consumption level is assumed to follow the process  

$$
d c_{t}=c_{t}\left[\mu_{c t}d t+\sigma_{c t}^{\top}d z_{t}\right]
$$  

so that the dynamics of the real state-price density is  

$$
d\zeta_{t}=-\zeta_{t}\left[r_{t}d t+\lambda_{t}^{\top}d z_{t}\right].
$$  

The short-term real rate is given by  

$$
r_{t}=\delta+{\frac{-c_{t}u^{\prime\prime}(c_{t})}{u^{\prime}(c_{t})}}\mu_{c t}-{\frac{1}{2}}c_{t}^{2}{\frac{u^{\prime\prime\prime}(c_{t})}{u^{\prime}(c_{t})}}\|{\pmb\sigma}_{c t}\|^{2}
$$  

and the market price of risk vector is given by  

$$
\lambda_{t}=\left(-\frac{c_{t}u^{\prime\prime}(c_{t})}{u^{\prime}(c_{t})}\right)\pmb{\sigma}_{c t}.
$$  

By substituting the expression (10.54) for $\lambda_{t}$ into (4.70), we can write the short-term nominal rate as  

$$
\tilde{r}_{t}=r_{t}+\mu_{\varphi t}-\|\sigma_{\varphi t}\|^{2}-\left(-\frac{c_{t}u^{\prime\prime}(c_{t})}{u^{\prime}(c_{t})}\right)\sigma_{\varphi t}^{\top}\sigma_{c t}.
$$  

In the special case where the representative individual has constant relative risk aversion, i.e. $u(c)=c^{1-\gamma}/(1-\gamma)$ , and both the aggregate consumption and the price index follow geometric Brownian motions, we get constant rates  

$$
\begin{array}{l}{r=\displaystyle\delta+\gamma\mu_{c}-\frac{1}{2}\gamma(1+\gamma)\|\pmb{\sigma}_{c}\|^{2},}\ {\tilde{r}=r+\mu_{\varphi}-\|\pmb{\sigma}_{\varphi}\|^{2}-\gamma\pmb{\sigma}_{\varphi}^{\top}\pmb{\sigma}_{c}.}\end{array}
$$  

Breeden (1986) considers the relations between interest rates, inflation, and aggregate consumption and production in an economy with multiple consumption goods. In general the presence of several consumption goods complicates the analysis considerably. Breeden shows that the equilibrium nominal short rate will depend on both an inflation rate computed using the average weights. of the different consumption goods and an inflation rate computed using the marginal weights of the different goods, which are determined by the optimal allocation to the different goods of an extra dollar of total consumption expenditure. The average and the marginal consumption weights will generally be different since the representative individual may shift to other consumption goods as. his wealth increases. However, in the special (probably unrealistic) case of Cobb-Douglas type utility function, the relative expenditure weights of the different consumption goods will be constant. For that case Breeden obtains results similar to our one-good conclusions..  

# 10.6.3 A model with real effects of money  

In the next model we consider, cash holdings enter the direct utility function of the individual(s). This may be rationalized by the fact that cash holdings facilitate frequent consumption transactions. In such a model the price of the consumption good is determined as a part of the equilibrium of the economy, in contrast to the models studied above where we took an exogenous process for the consumer price index. We follow the set-up of Bakshi and Chen (1996) closely..  

# The general model  

We assume the existence of a representative individual who chooses a consumption process. $c=\left(c_{t}\right)$ and a cash process $\tilde{M}=(\tilde{M}_{t})$ , where. $\tilde{M_{t}}$ is the dollar amount held at time. $t$ . As before, let. $F_{t}$ be the unit dollar price of the consumption good. Assume that the representative individual has an infinite time horizon, no endowment stream, and an additively time-separable utility of consumption and the real value of the monetary holdings, i.e.. $M_{t}=\tilde{M}_{t}/F_{t}$ .At time $t$ the individual has the opportunity to invest in a nominally risk-free bank account with a nominal rate of return of $\tilde{r}_{t}$ When the individual chooses to hold $\tilde{M_{t}}$ dollars in cash over the period. $[t,t+d t]$ , she therefore gives up a dollar return of. $\tilde{M}_{t}\tilde{r}_{t}d t$ , which is equivalent to a consumption of $\tilde{M}_{t}\tilde{r}_{t}d t/F_{t}$ units of the good. Given a (real) state-price deflator $\zeta=\left(\zeta_{t}\right)$ , the total cost of choosing. $c$ and $M$ is thus $\begin{array}{r}{\mathrm{E}\left[\int_{0}^{\infty}\zeta_{t}\big(c_{t}+\tilde{M}_{t}\tilde{r}_{t}/F_{t}\big)d t\right]}\end{array}$ . In sum, the optimization problem of the individual can be written as follows:  

$$
\begin{array}{r l}&{\quad\displaystyle\operatorname*{sup}_{(c_{t},\tilde{M}_{t})}\mathrm{E}\left[\int_{0}^{\infty}e^{-\delta t}u\left(c_{t},\tilde{M}_{t}/F_{t}\right)d t\right]}\ &{\displaystyle\mathrm{s.t.~}\mathrm{E}\left[\int_{0}^{\infty}\zeta_{t}\left(c_{t}+\frac{\tilde{M}_{t}}{F_{t}}\tilde{r}_{t}\right)d t\right]\leq W_{0},}\end{array}
$$  

where $W_{0}$ is the initial (real) wealth of the individual.  

The Lagrangian associated with the optimization problem is  

$$
\begin{array}{l}{\displaystyle\mathcal{L}=\mathrm{E}\left[\int_{0}^{\infty}e^{-\delta t}u\left(c_{t},\tilde{M}_{t}/F_{t}\right)d t\right]+\psi\left(W_{0}-\mathrm{E}\left[\int_{0}^{\infty}\zeta_{t}\left(c_{t}+\frac{\tilde{M}_{t}}{F_{t}}\tilde{r}_{t}\right)d t\right]\right)}\ {\displaystyle\quad=\psi W_{0}+\mathrm{E}\left[\int_{0}^{\infty}\left(e^{-\delta t}u\left(c_{t},\tilde{M}_{t}/F_{t}\right)-\psi\zeta_{t}\left(c_{t}+\frac{\tilde{M}_{t}}{F_{t}}\tilde{r}_{t}\right)\right)d t\right].}\end{array}
$$  

If we maximize the integrand "state-by-state', we will also maximize the expectation. The first order conditions are  

$$
\begin{array}{r l}&{e^{-\delta t}u_{c}(c_{t},\tilde{M}_{t}/F_{t})=\psi\zeta_{t},}\ &{e^{-\delta t}u_{M}(c_{t},\tilde{M}_{t}/F_{t})=\psi\zeta_{t}\tilde{r}_{t},}\end{array}
$$  

where $u_{c}$ and $u_{M}$ are the first-order derivatives of $u$ with respect to the first and second argument, respectively. The Lagrange multiplier $\psi$ is set so that the budget condition holds as an equality. Again, we see that the state-price deflator is given in terms of the marginal utility with respect to consumption. Imposing the initial value $\zeta_{0}=1$ and recalling the definition of $M_{t}$ , we have  

$$
\zeta_{t}=e^{-\delta t}\frac{u_{c}(c_{t},M_{t})}{u_{c}(c_{0},M_{0})}.
$$  

We can apply the state-price deflator to value all payment streams. For example, an investment of one dollar at time $t$ in the nominal bank account generates a continuous payment stream at the rate of $\ddot{r}_{s}$ dollars to the end of all time. The corresponding real investment at time $t$ is $1/F_{t}$ and the real dividend at time $s$ is $\tilde{r}_{s}/F_{s}$ . Hence, we have the relation  

$$
\frac{1}{F_{t}}=\mathrm{E}_{t}\left[\int_{t}^{\infty}\frac{\zeta_{s}}{\zeta_{t}}\frac{\tilde{r}_{s}}{F_{s}}d s\right],
$$  

or, equivalently,  

$$
{\frac{1}{F_{t}}}=\operatorname{E}_{t}\left[\int_{t}^{\infty}e^{-\delta(s-t)}{\frac{u_{c}(c_{s},M_{s})}{u_{c}(c_{t},M_{t})}}{\frac{\tilde{r}_{s}}{F_{s}}}d s\right].
$$  

Substituting the first optimality condition (10.57) into the second (10.58), we see that the nominal short rate is given by.  

$$
\tilde{r}_{t}={\frac{u_{M}\big(c_{t},\tilde{M}_{t}/F_{t}\big)}{u_{c}\big(c_{t},\tilde{M}_{t}/F_{t}\big)}}.
$$  

The intuition behind this relation can be explained in the following way. If you have an extra dollar now you can either keep it in cash or invest it in the nominally risk-free bank account. If you keep it in cash your utility grows by. $u_{M}(c_{t},\tilde{M}_{t}/F_{t})/F_{t}$ . If you invest it in the bank account you will. earn a dollar interest of. $\tilde{r}_{t}$ that can be used for consuming $\tilde{r}_{t}/F_{t}$ extra units of consumption, which will increase your utility by. $u_{c}(c_{t},\tilde{M}_{t}/F_{t})\tilde{r}_{t}/F_{t}$ . At the optimum, these utility increments must be. identical. Combining (10.60) and (10.61), we get that the price index must satisfy the recursive. relation  

$$
\frac{1}{F_{t}}=\mathrm{E}_{t}\left[\int_{t}^{\infty}e^{-\delta(s-t)}\frac{u_{M}\left(c_{s},M_{s}\right)}{u_{c}\left(c_{t},M_{t}\right)}\frac{1}{F_{s}}d s\right].
$$  

Let us find expressions for the equilibrium real short rate and the market price of risk in this setting. As always, the real short rate equals minus the percentage drift of the state-price deflator, while the market price of risk equals minus the percentage sensitivity vector of the state-price. deflator. In an equilibrium, the representative individual must consume the aggregate consumption. and hold the total money supply in the economy. Suppose that the aggregate consumption and. the money supply follow exogenous processes of the form.  

$$
\begin{array}{r l}&{{d c}_{t}=c_{t}\left[\mu_{c t}{d t}+\sigma_{c t}^{\top}{d z}_{t}\right],}\ &{{d}\tilde{M}_{t}=\tilde{M}_{t}\left[\tilde{\mu}_{M t}{d t}+\tilde{\sigma}_{M t}^{\top}{d z}_{t}\right].}\end{array}
$$  

Assuming that the endogenously determined price index will follow a similar process,  

$$
d F_{t}=F_{t}\left[\mu_{\varphi t}d t+\pmb{\sigma}_{\varphi t}^{\top}d z_{t}\right],
$$  

the dynamics of $M_{t}=\tilde{M}_{t}/F_{t}$ will be  

$$
d M_{t}=M_{t}\left[\mu_{M t}d t+\sigma_{M t}^{\top}d z_{t}\right],
$$  

where  

$$
\iota_{M t}=\tilde{\mu}_{M t}-\mu_{\varphi t}+\|\pmb{\sigma}_{\varphi t}\|^{2}-\tilde{\sigma}_{M t}^{\top}\pmb{\sigma}_{\varphi t},\qquad\pmb{\sigma}_{M t}=
$$  

Given these equations and the relation (10.59), we can find the drift and the sensitivity vector of the state-price deflator by an application of Ito's Lemma (Exercise 10.5). We find that the equilibrium real short-term interest rate can be written as  

$$
\begin{array}{r l}&{\boldsymbol{r}_{t}=\delta+\left(\frac{-c_{t}u_{c c}(c_{t},M_{t})}{u_{c}(c_{t},M_{t})}\right)\boldsymbol{\mu}_{c t}+\left(\frac{-M_{t}u_{c M}(c_{t},M_{t})}{u_{c}(c_{t},M_{t})}\right)\boldsymbol{\mu}_{M t}}\ &{\qquad-\frac{1}{2}\frac{c_{t}^{2}u_{c c c}(c_{t},M_{t})}{u_{c}(c_{t},M_{t})}\lVert\boldsymbol{\sigma}_{c t}\rVert^{2}-\frac{1}{2}\frac{M_{t}^{2}u_{c M M}(c_{t},M_{t})}{u_{c}(c_{t},M_{t})}\lVert\boldsymbol{\sigma}_{M t}\rVert^{2}-\frac{c_{t}M_{t}u_{c c M}(c_{t},M_{t})}{u_{c}(c_{t},M_{t})}\boldsymbol{\sigma}_{c t}^{\top}\boldsymbol{\sigma}_{M t},}\end{array}
$$  

while the market price of risk vector is  

$$
\begin{array}{r l}&{\lambda_{t}=\left(-\frac{c_{t}u_{c c}\left(c_{t},M_{t}\right)}{u_{c}\left(c_{t},M_{t}\right)}\right)\pmb{\sigma}_{c t}+\left(\frac{-M_{t}u_{c M}\left(c_{t},M_{t}\right)}{u_{c}\left(c_{t},M_{t}\right)}\right)\pmb{\sigma}_{M t}}\ &{\quad=\left(-\frac{c_{t}u_{c c}\left(c_{t},M_{t}\right)}{u_{c}\left(c_{t},M_{t}\right)}\right)\pmb{\sigma}_{c t}+\left(\frac{-M_{t}u_{c M}\left(c_{t},M_{t}\right)}{u_{c}\left(c_{t},M_{t}\right)}\right)\left(\tilde{\pmb{\sigma}}_{M t}-\pmb{\sigma}_{\varphi t}\right).}\end{array}
$$  

With $u_{c M}<0$ , we see that assets that are positively correlated with the inflation rate will have. a lower expected real return, other things equal. Intuitively such assets are useful for hedging inflation risk so that they do not have to offer as high an expected return..  

The relation (4.70) is also valid in the present setting. Substituting the expression (10.64) for the market price of risk into (4.70), we obtain  

$$
\tilde{r}_{t}-r_{t}-\mu_{\varphi t}+\|\sigma_{\varphi t}\|^{2}=-\left(-\frac{c_{t}u^{\prime\prime}(c_{t})}{u^{\prime}(c_{t})}\right)\sigma_{\varphi t}^{\top}\sigma_{c t}-\left(\frac{-M_{t}u_{c M}(c_{t},M_{t})}{u_{c}(c_{t},M_{t})}\right)\sigma_{\varphi t}^{\top}\sigma_{M t}.
$$  

# An example  

To obtain more concrete results, we must specify the utility function and the exogenous processes $c$ and $\tilde{M}$ . Assume a utility function of the Cobb-Douglas type,.  

$$
u(c,M)=\frac{\left(c^{\varphi}M^{1-\varphi}\right)^{1-\gamma}}{1-\gamma},
$$  

where $\varphi$ is a constant between zero and one, and $\gamma$ is a positive constant. The limiting case for $\gamma=1$ is log utility,  

$$
u(c,M)=\varphi\ln c+(1-\varphi)\ln M.
$$  

By inserting the relevant derivatives into (10.63), we see that the real short rate becomes  

$$
\begin{array}{l}{\displaystyle r_{t}=\delta+[1-\varphi(1-\gamma)]\mu_{c t}-(1-\varphi)(1-\gamma)\mu_{M t}-\frac{1}{2}[1-\varphi(1-\gamma)][2-\varphi(1-\gamma)]\|\sigma_{c t}\|^{2}}\ {\displaystyle\qquad+\frac{1}{2}(1-\varphi)(1-\gamma)[1-(1-\varphi)(1-\gamma)]\|\sigma_{M t}\|^{2}+(1-\varphi)(1-\gamma)[1-\varphi(1-\gamma)]\sigma_{c t}^{\top}\sigma_{M t},}\end{array}
$$  

which for $\gamma=1$ simplifies to  

$$
r_{t}=\delta+\mu_{c t}-\|\pmb{\sigma}_{c t}\|^{2}.
$$  

We see that with log utility, the real short rate will be constant if aggregate consumption $c=\left(c_{t}\right)$ follows a geometric Brownian motion. From (10.61), the nominal short rate is  

$$
\tilde{r}_{t}=\frac{1-\varphi}{\varphi}\frac{c_{t}}{M_{t}}.
$$  

The ratio $c_{t}/M_{t}$ is called the velocity of money. If the velocity of money is constant, the nominal short rate will be constant. Since. $M_{t}=\tilde{M}_{t}/F_{t}$ and $F_{t}$ is endogenously determined, the velocity of money will also be endogenously determined.  

We have to determine the price level in the economy, which is given only recursively in (10.62). This is possible under the assumption that both $C$ and $\tilde{M}$ follow geometric Brownian motions. We conjecture that $F_{t}=k\tilde{M}_{t}/c_{t}$ for some constant $k$ . From (10.62), we get  

$$
\frac{1}{k}=\frac{1-\varphi}{\varphi}\int_{t}^{\infty}e^{-\delta(s-t)}\operatorname{E}_{t}\left[\left(\frac{c_{s}}{c_{t}}\right)^{1-\gamma}\left(\frac{\tilde{M}_{s}}{\tilde{M}_{t}}\right)^{-1}\right]d s.
$$  

Inserting the relations  

$$
\begin{array}{l}{\displaystyle\frac{c_{s}}{c_{t}}=\exp\left\{\left(\mu_{c}-\frac{1}{2}\|\pmb{\sigma}_{c}\|^{2}\right)(s-t)+\pmb{\sigma}_{c}^{\top}(z_{s}-z_{t})\right\},}\ {\displaystyle\frac{\tilde{M}_{s}}{\tilde{M}_{t}}=\exp\left\{\left(\tilde{\mu}_{M}-\frac{1}{2}\|\tilde{\sigma}_{M}\|^{2}\right)(s-t)+\tilde{\sigma}_{M}^{\top}(z_{s}-z_{t})\right\},}\end{array}
$$  

and applying a standard rule for expectations of lognormal variables, we get  

$$
\begin{array}{l}{\displaystyle\frac{1}{k}=\frac{1-\varphi}{\varphi}\int_{t}^{\infty}\exp\Big\{\Big(-\delta+(1-\gamma)(\mu_{c}-\frac{1}{2}\|\pmb{\sigma}_{c}\|^{2})-\tilde{\mu}_{M}+\|\tilde{\pmb{\sigma}}_{M}\|^{2}}\ {\displaystyle\qquad+\frac{1}{2}(1-\gamma)^{2}\|\tilde{\pmb{\sigma}}_{c}\|^{2}-(1-\gamma)\pmb{\sigma}_{c}^{\top}\tilde{\pmb{\sigma}}_{M}\Big)(s-t)\Big\}d s,}\end{array}
$$  

which implies that the conjecture is true with  

$$
k=\frac{\varphi}{1-\varphi}\left(\delta-(1-\gamma)(\mu_{c}-\frac{1}{2}\|\sigma_{c}\|^{2})+\tilde{\mu}_{M}-\|\tilde{\sigma}_{M}\|^{2}-\frac{1}{2}(1-\gamma)^{2}\|\sigma_{c}\|^{2}+(1-\gamma)\sigma_{c}^{\top}\tilde{\sigma}_{M}\right).
$$  

From an application of Ito's Lemma, it follows that the price index also follows a geometric Brownian motion  

$$
d F_{t}=F_{t}\left[\mu_{\varphi}d t+\pmb{\sigma}_{\varphi}^{\top}d z_{t}\right],
$$  

where  

$$
\mu_{\varphi}=\tilde{\mu}_{M}-\mu_{c}+\|\pmb{\sigma}_{c}\|^{2}-\tilde{\pmb{\sigma}}_{M}^{\top}\pmb{\sigma}_{c},\qquad\pmb{\sigma}_{\varphi}=\tilde{\pmb{\sigma}}_{M}-\pmb{\sigma}_{c}.
$$  

With $F_{t}=k\tilde{M}_{t}/c_{t}$ , we have $M_{t}=c_{t}/k$ , so that the velocity of money $c_{t}/M_{t}=k$ is constant, and the nominal short rate becomes  

$$
\tilde{r}_{t}=\frac{1-\varphi}{\varphi}k=\delta-(1-\gamma)(\mu_{c}-\frac{1}{2}\|\pmb{\sigma}_{c}\|^{2})+\tilde{\mu}_{M}-\|\tilde{\pmb{\sigma}}_{M}\|^{2}-\frac{1}{2}(1-\gamma)^{2}\|\pmb{\sigma}_{c}\|^{2}+(1-\gamma)\pmb{\sigma}_{c}^{\top}\tilde{\pmb{\sigma}}_{M},
$$  

which is also a constant. With log utility, the nominal rate simplifies to $\delta+\tilde{\mu}_{M}-\|\tilde{\pmb{\sigma}}_{M}\|^{2}$ . In order to obtain the real short rate in the non-log case, we have to determine $\mu_{M t}$ and $\sigma_{M t}$ and plug into (10.66). We get $\mu_{M}=\mu_{c}+{\textstyle\frac{1}{2}}\|\pmb{\sigma}_{c}\|^{2}+\tilde{\pmb{\sigma}}_{M}^{\top}\pmb{\sigma}_{c}$ and $\pmb{\sigma}_{M t}=\pmb{\sigma}_{c}$ and hence  

$$
r_{t}=\delta+\gamma\mu_{c}-\gamma\|\pmb{\sigma}_{c}\|^{2}\left[\frac{1}{2}(1+\gamma)+\varphi(1-\gamma)\right],
$$  

which is also a constant. In comparison with (10.55) for the case where money has no real effects, the last term in the equation above is new.  

# Another example  

Bakshi and Chen (1996) also study another model specification in which both nominal and real short rates are time-varying, but evolve independently of each other. To obtain stochastic interest. rates we have to specify more general processes for aggregate consumption and money supply than. the geometric Brownian motions used above. They assume log-utility (. $\gamma=1$ ) in which case we have already seen that  

$$
r_{t}=\delta+\mu_{c t}-\|\pmb{\sigma}_{c t}\|^{2},\qquad\tilde{r}_{t}=\frac{1-\varphi}{\varphi}\frac{c_{t}}{M_{t}}=\frac{1-\varphi}{\varphi}\frac{c_{t}F_{t}}{\tilde{M}_{t}}.
$$  

The dynamics of aggregate consumption is assumed to be  

$$
d c_{t}=c_{t}\left[\left(\alpha_{c}+\kappa_{c}X_{t}\right)d t+\sigma_{c}\sqrt{X_{t}}d z_{1t}\right],
$$  

where $X$ can be interpreted as a technology variable and is assumed to follow the process  

$$
d X_{t}=\kappa_{x}{\left(\theta_{x}-X_{t}\right)}d t+\sigma_{x}{\sqrt{X_{t}}}d z_{1t}.
$$  

The money supply is assumed to be $\tilde{M}_{t}=\tilde{M}_{0}e^{\mu_{M}^{*}t}g_{t}/g_{0}$ , where  

$$
d g_{t}=g_{t}\left[\kappa_{g}(\theta_{g}-g_{t})d t+\sigma_{g}\sqrt{g_{t}}\left(\rho_{C M}d z_{1t}+\sqrt{1-\rho_{C M}^{2}}d z_{2t}\right)\right],
$$  

and where $z_{1}$ and $z_{2}$ are independent one-dimensional Brownian motions. Following the same basic. procedure as in the previous model specification, the authors show that the real short rate is  

$$
\boldsymbol{r}_{t}=\boldsymbol{\delta}+\boldsymbol{\alpha}_{c}+(\kappa_{c}-\sigma_{c}^{2})\boldsymbol{X}_{t},
$$  

while the nominal short rate is  

$$
\tilde{r}_{t}=\frac{(\delta+\mu_{M}^{*})(\delta+\mu_{M}^{*}+\kappa_{g}\theta_{g})}{\delta+\mu_{M}^{*}+(\kappa_{g}+\sigma_{g}^{2})g_{t}}.
$$  

Both rates are time-varying. The real rate is driven by the technology variable $X$ ,while the nominal rate is driven by the monetary shock process. $g$ . In this set-up, shocks to the real economy. have opposite effects of the same magnitude on real rates and inflation so that nominal rates are unaffected.  

The real price of a real zero-coupon bond maturing at time $T$ is of the form  

$$
B_{t}^{T}=e^{-a(T-t)-b(T-t)x},
$$  

while the nominal price of a nominal zero-coupon bond maturing at $T$ is  

$$
\tilde{B}_{t}^{T}=\frac{\tilde{a}(T-t)+\tilde{b}(T-t)g_{t}}{\delta+\mu_{M}^{*}+(\kappa_{g}+\sigma_{g}^{2})g_{t}},
$$  

where $a$ $b$ $\tilde{a}$ , and $\ddot{b}$ are deterministic functions of time for which Bakshi and Chen provide closedform expressions.  

In the very special case where these processes are uncorrelated, i.e.. $\rho_{C M}~=~0$ , the real and nominal term structures of interest rates are independent of each other! Although this is an extreme result, it does point out that real and nominal term structures in general may have quite different properties.  
