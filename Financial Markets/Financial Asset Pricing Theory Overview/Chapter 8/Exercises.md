---
tags:
  - consumption_based_capm
  - european_call_option
  - present_value
  - state_price_deflator
  - zero_coupon_bond
aliases:
  - carl smart
  - exercise 8.1
  - investment projects
  - risk-ignoring approach
key_concepts:
  - aggregate consumption growth
  - conditional CAPM
  - consumption growth rate
  - expected dividends
  - riskless returns
---

# 8.11 Exercises  

EXERCISE 8.1 Carl Smart is currently (at time $t=0$ ) considering a couple of investment projects that will provide him with a dividend in one year from now (time. $t=1$ ) and a dividend in two years from now (time $t=2$ ). He figures that the size of the dividends will depend on the growth rate of aggregate consumption over these two years. The first project Carl considers provides a dividend of  

$$
D_{t}=60t+5(C_{t}-\mathrm{E}[C_{t}])
$$  

at $t=1$ and at $t=2$ . The second project provides a dividend of  

$$
D_{t}=60t-5(C_{t}-\mathrm{E}[C_{t}])
$$  

at $t=1$ and at. $t=2$ . Here $\operatorname{E}[]$ is the expectation computed at time 0 and $C_{t}$ denotes aggregate consumption at time $t$ . The current level of aggregate consumption is $C_{0}=1000$  

As a valuable input to his investment decision Carl wants to compute the present value of the future dividends of each of the two projects.  

First, Carl computes the present values of the two projects using a "risk-ignoring approach", i.e. by discounting the expected dividends using the riskless returns observed in the bond markets. Carl observes that a one-year zero-coupon bond with a face value of 1000 currently trades at a price of 960 and a two-year zero-coupon bond with a face value of 1000 trades at a price of 929.02.  

(a) What are the expected dividends of project 1 and project 2? (b) What are the present values of project 1 and project 2 using the risk-ignoring approach?  

Suddenly, Carl remembers that he once took a great course on advanced asset pricing and that the present value of an uncertain dividend of $D_{1}$ at time 1 and an uncertain dividend of $D_{2}$ at time 2 should be computed as  

$$
P=\mathrm{E}\left[\frac{\zeta_{1}}{\zeta_{0}}D_{1}+\frac{\zeta_{2}}{\zeta_{0}}D_{2}\right],
$$  

where the $\zeta_{t}$ 's define a state-price deflator. After some reflection and analysis, Carl decides to. value the projects using a conditional Consumption-based CAPM so that the state-price deflator between time $t$ and $t+1$ is of the form  

$$
\frac{\zeta_{t+1}}{\zeta_{t}}=a_{t}+b_{t}\frac{C_{t+1}}{C_{t}},\quad t=0,1,\ldots.
$$  

Carl thinks it's fair to assume that aggregate consumption will grow by either. $1\%$ ('low") or 3% ("high') in each of the next two years. Over the first year he believes the two growth rates are equally likely. If the growth rate of aggregate consumption is high in the first year, he believes that there is a. $30\%$ chance that it will also be high in the second year and, thus, a 70% chance of. low growth in the second year. On the other hand, if the growth rate of aggregate consumption. is low in the first year, he estimates that there will be a $70\%$ chance of high growth and a. $30\%$ chance of low growth in the second year..  

In order to apply the Consumption-based CAPM for valuing his investment projects, Carl has to identify the coefficients. $a_{t}$ and $b_{t}$ for $t=0,1$ . The values of $a_{0}$ and $b_{0}$ can be identified from the. prices of two traded assets that only provide dividends at time 1. In addition to the one-year zero-coupon bond mentioned above, a one-year European call option on aggregate consumption is. traded. The option has a strike price of. $K=1020$ so that the payoff of the option in one year is $\operatorname*{max}(C_{1}-1020,0)$ , where $C_{1}$ is the aggregate consumption level at. $t=1$ . The option trades at a. price of 4.7.  

(c) Using the information on the two traded assets, write up two equations that can be used for determining $a_{0}$ and $b_{0}$ . Verify that the equations are solved for $a_{0}=3$ and $b_{0}=-2$  

The values of $a_{1}$ and $b_{1}$ may depend on the consumption growth rate of the first year, i.e. Carl has to find $a_{1}^{h},b_{1}^{h}$ that defines the second-year state-price deflator if the first-year growth rate was high and $a_{1}^{l},b_{1}^{l}$ that defines the second-year state-price deflator if the first-year growth rate was low. Using the observed market prices of other assets, Carl concludes that.  

$$
a_{1}^{h}=2.5,\quad b_{1}^{h}=-1.5,\quad a_{1}^{l}=3.5198,\quad b_{1}^{l}=-2.5.
$$  

(d) Verify that the economy is path-independent in the sense that the current price of an asset that will pay you $^{1}$ at $t=2$ if the growth rate is high in the first year and low in the second year will be identical (at least to five decimal places) to the current price of an asset that will pay you 1 at $t=2$ if the growth rate is low in the first year and high in the second year.  

(e) Illustrate the possible dividends of the two projects in a two-period binomial tree.  

(f) What are the correctly computed present values of the two projects?  

(g) Carl notes that the expected dividends of the two projects are exactly the same but the present value of project 2 is higher than the present value of project 1. Although Carl is. pretty smart, he cannot really figure out why this is so. Can you explain it to him?.  

EXERCISE 8.2 In the simple consumption-based asset pricing model, the growth rate of aggre-.   
gate consumption is assumed to have a constant expectation and standard deviation (volatility).   
For example, in the continuous-time version aggregate consumption is assumed to follow a geo-.   
metric Brownian motion. Consider the following alternative process for aggregate consumption:.  

$$
d c_{t}=c_{t}[\mu d t+\sigma c_{t}^{\alpha-1}d z_{t}],
$$  

where $\mu$ $\sigma$ , and $\alpha$ are positive constants, and $z=\left(z_{t}\right)$ is a standard Brownian motion. As in the. simple model, assume that a representative individual exists and that this individual has timeadditive expected utility exhibiting constant relative risk aversion given by the parameter. $\gamma>0$ and a constant time preference rate $\delta>0$  

(a) State an equation linking the expected excess return on an arbitrary risky asset to the level of aggregate consumption and the parameters of the aggregate consumption process. How does the expected excess return vary with the consumption level?   
(b) State an equation linking the short-term continuously compounded risk-free interest rate $\boldsymbol{r}_{t}^{f}$ to the level of aggregate consumption and the parameters of the aggregate consumption process. How does the interest rate vary with the consumption level?   
(c) Use Ito's Lemma to find the dynamics of the interest rate, $d r_{t}^{f}$ ? Can you write the drift and the volatility of the interest rate as functions of the interest rate level only?  

EXERCISE 8.3 Give a proof of Theorem 8.2.  

EXERCISE 8.4 Consider the Chan and Kogan model. Show the expressions in (8.49), (8.50), (8.52), (8.53), and (8.54). Show Theorem 8.4.  

EXERCISE 8.5 In the Chan and Kogan model, show how (8.56) follows from (8.42).  

EXERCISE 8.6 Consider a continuous-time economy with complete markets and a representative individual having an "external habit' or "keeping up with the Jones'es' utility function. so that, at any time. $t$ , the individual maximizes $\begin{array}{r}{\mathrm{E}_{t}\left[\int_{t}^{T}e^{-\delta(s-t)}u(c_{s},X_{s})d s\right]}\end{array}$ , where $u(c,X)=$ $\textstyle{\frac{1}{1-\gamma}}(c-X)^{1-\gamma}$ for $c>X\ge0$   
Define $\begin{array}{r}{Y_{t}=-\ln{\left(1-\frac{X_{t}}{c_{t}}\right)}}\end{array}$  

(a) Argue that $Y_{t}$ is positive. Would you call a situation where $Y_{t}$ is high for a "good state" or a "bad state"? Explain!  

(b) Argue that the unique state-price deflator is given by  

$$
\zeta_{t}=e^{-\delta t}\frac{c_{t}^{-\gamma}e^{\gamma Y_{t}}}{c_{0}^{-\gamma}e^{\gamma Y_{0}}}.
$$  

First, write the dynamics of consumption and the variable $Y_{t}$ in the general way:.  

$$
\begin{array}{r l}&{{d c}_{t}=c_{t}\big[\mu_{c t}{d t}+\sigma_{c t}^{\top}{d z}_{t}\big],}\ &{{d Y}_{t}=\mu_{Y t}{d t}+\sigma_{Y t}^{\top}{d z}_{t},}\end{array}
$$  

where $z=(z_{t})$ is a multi-dimensional standard Brownian motion.  

(c) Find the dynamics of the state-price deflator and identify the continuously compounded short-term risk-fre interest rate $\boldsymbol{r}_{t}^{f}$ and the market price of risk $\lambda_{t}$  

An asset $i$ pays an uncertain terminal dividend but no intermediate dividends. The price dynamics is of the form  

$$
d P_{i t}=P_{i t}\left[\mu_{i t}d t+\sigma_{i t}^{\top}d z_{t}\right].
$$  

(d) Explain why  

$$
\mu_{i t}-r_{t}^{f}=\beta_{i c t}\eta_{c t}+\beta_{i Y t}\eta_{Y t},
$$  

where $\beta_{i c t}=(\pmb{\sigma}_{i t}^{\top}\pmb{\sigma}_{c t})/\lVert\pmb{\sigma}_{c t}\rVert^{2}$ and $\beta_{i Y t}=(\pmb{\sigma}_{i t}^{\top}\pmb{\sigma}_{Y t})/\lVert\pmb{\sigma}_{Y t}\rVert^{2}$ . Express $\eta_{c t}$ and $\eta_{Y t}$ in terms of previously introduced parameters and variables.  

Next, consider the specific model:  

$$
\begin{array}{r l}&{d c_{t}=c_{t}[\mu_{c}d t+\sigma_{c}d z_{1t}],}\ &{d Y_{t}=\kappa[\bar{Y}-Y_{t}]d t+\sigma_{Y}\sqrt{Y_{t}}\left(\rho d z_{1t}+\sqrt{1-\rho^{2}}d z_{2t}\right),}\end{array}
$$  

where $(z_{1},z_{2})^{\top}$ is a two-dimensional standard Brownian motion, $\mu_{c}$ $\sigma_{c}$ $\kappa$ $Y$ , and $O Y$ are positive constants, and $\rho\in(-1,1)$  

(e) What is the short-term risk-free interest rate and the market price of risk in the specific model?  

Assume that the price dynamics of asset $i$ is  

$$
d P_{i t}=P_{i t}\left[\mu_{i t}d t+\sigma_{i t}\left(\psi d z_{1t}+\sqrt{1-\psi^{2}}d z_{2t}\right)\right],
$$  

where $\sigma_{i t}>0$ and $\psi\in(-1,1)$  

(f) What is the Sharpe ratio of asset. $i$ in the specific model? Can the specific model gener-. ate counter-cyclical variation in Sharpe ratios (if necessary, provide parameter conditions ensuring this)?  

EXERCISE 8.7 Consider the set-up of Exercise 6.10 with $\textstyle u(c,h)={\frac{1}{1-\gamma}}(c-h)^{1-\gamma}$  

(a) Can optimal consumption follow a geometric Brownian motion under these assumptions?   
(b) Assume that the excess consumption rate. $\hat{c}_{t}=c_{t}-h_{t}$ follows a geometric Brownian motion. Show that the state-price deflator will be of the form $\zeta_{t}=f(t)e^{-\delta t}\hat{c}_{t}^{-\gamma}$ for some deterministic function $f(t)$ (and find that function). Find an expression for the equilibrium interest rate and the market price of risk. Compare with the "simple model' with no habit, CRRA utility,. and consumption following a geometric Brownian motion.  

EXERCISE 8.8 (This problem is based on the working paper Menzly, Santos, and Veronesi (2002).) Consider an economy with a representative agent with life-time utility given by  

$$
U(C)=\operatorname{E}\left[\int_{0}^{\infty}e^{-\varphi t}\ln(C_{t}-X_{t})d t\right],
$$  

where $X_{t}$ is an external habit level and $\varphi$ is a subjective discount rate. As in Campbell and Cochrane (1999) define the surplus ratio as $S_{t}=(C_{t}-X_{t})/C_{t}$ . Define $Y_{t}=1/S_{t}$ . Aggregate consumption $C_{t}$ is assumed to follow a geometric Brownian motion  

$$
d C_{t}=C_{t}\left[\mu_{C}d t+\sigma_{C}d z_{t}\right],
$$  

where $\mu_{C}$ and $\sigma_{C}$ are constants and. $z$ is a one-dimensional standard Brownian motion. The dynamics of the habit level is modeled through.  

$$
d Y_{t}=k[\bar{Y}-Y_{t}]d t-\alpha(Y_{t}-\kappa)\sigma_{C}d z_{t},
$$  

where $k,Y,\alpha$ , and $\kappa$ are constants.  

(a) Show that $\mathrm{E}_{t}[Y_{\tau}]=\bar{Y}+(Y_{t}-\bar{Y})e^{-k(\tau-t)}$  

(b) For any given dividend process. $D=\left(D_{t}\right)$ in this economy, argue that the price is given by  

$$
P_{t}^{D}=\left(C_{t}-X_{t}\right)\mathrm{E}_{t}\left[\int_{t}^{\infty}e^{-\varphi(\tau-t)}\frac{D_{\tau}}{C_{\tau}-X_{\tau}}d\tau\right].
$$  

Let $s_{\tau}^{D}=D_{\tau}/C_{\tau}$ denote the dividend's share of aggregate consumption. Show that the price $P_{t}^{D}$ satisfies  

$$
\frac{P_{t}^{D}}{C_{t}}=\frac{1}{Y_{t}}\operatorname{E}_{t}\left[\int_{t}^{\infty}e^{-\varphi(\tau-t)}s_{\tau}^{D}Y_{\tau}d\tau\right].
$$  

(c) Show that the price $P_{t}^{C}$ of a claim to the aggregate consumption stream $D_{\tau}=C_{\tau}$ is given by  

$$
\frac{P_{t}^{C}}{C_{t}}=\frac{1}{\varphi+k}\left(1+\frac{k\bar{Y}}{\varphi}S_{t}\right).
$$  

(d) Find the dynamics of the state-price deflator. Find and interpret expressions for the risk-free interest rate and the market price of risk in this economy.  

EXERCISE 8.9 (This problem is based on the paper Longstaff and Piazzesi (2004).) Consider a continuous-time model of an economy with a representative agent and a single non-durable good. The objective of the agent at any time $t$ is to maximize the expected time-additive CRRA utility,  

$$
\mathrm{E}_{t}\left[\int_{t}^{\infty}e^{-\delta(s-t)}\frac{C_{s}^{1-\gamma}}{1-\gamma}d s\right],
$$  

where $\gamma>0$ and $C_{s}$ denotes the consumption rate at time. $s$ . The agent can invest in a bank account, i.e. borrow and lend at a short-term interest rate of. $r_{t}$ . The bank account is in zero net supply. A single stock with a net supply of one share is available for trade. The agent is initially endowed with this share. The stock pays a continuous dividend at the rate. $D_{t}$ . The agent receives. an exogenously given labor income at the rate. $I_{t}$  

(a) Explain why the equilibrium consumption rate must equal the sum of the dividend rate and the labor income rate, i.e. $C_{t}=I_{t}+D_{t}$  

Let $F_{t}$ denote the dividend-consumption ratio, i.e. $F_{t}=D_{t}/C_{t}$ .Assume that $F_{t}=\exp\{-X_{t}\}$ where $X=\left(X_{t}\right)$ is the diffusion process.  

$$
d X_{t}=\left(\mu-\kappa X_{t}\right)d t-\eta{\sqrt{X_{t}}}d z_{1t}.
$$  

Here $\mu$ $\kappa$ , and $\eta$ are positive constants and. $z_{1}=\left(z_{1t}\right)$ is a standard Brownian motion.  

(b) Explain why $F_{t}$ is always between zero and one.  

Assume that the aggregate consumption process is given by the dynamics  

$$
d C_{t}=C_{t}\left[\alpha d t+\sigma\sqrt{X_{t}}\rho d z_{1t}+\sigma\sqrt{X_{t}}\sqrt{1-\rho^{2}}d z_{2t}\right],
$$  

where $\alpha$ $\sigma$ , and $\rho$ are constants and $z_{2}=\left(z_{2t}\right)$ is another standard Brownian motion, independent Of %1.  

(c) What is the equilibrium short-term interest rate in this economy?  

(d) Use Ito's Lemma to derive the dynamics of $F_{t}$ and of $D_{t}$   
(e) Show that the volatility of the dividend rate is greater than the volatility of the consumption rate if $\eta\rho>0$  

Let $P_{t}$ denote the price of the stock, i.e. the present value of all the future dividends.  

(f) Show that the stock price can be written as  

$$
P_{t}=C_{t}^{\gamma}\operatorname{E}_{t}\left[\int_{t}^{\infty}e^{-\delta(s-t)}C_{s}^{1-\gamma}F_{s}d s\right].
$$  

It can be shown that. $P_{t}$ can be written as a function of $t$ $C_{t}$ , and $F_{t}$  

$$
P_{t}=C_{t}\int_{t}^{\infty}e^{-\delta(s-t)}A(t,s)F_{t}^{-B(t,s)}d s.
$$  

Here $A(t,s)$ and $B(t,s)$ are some deterministic functions of time that we will leave unspecified.  

(g) Use Ito's Lemma to show that  

$$
d P_{t}=P_{t}\left[\ldots d t+\left(\rho\sigma+\eta H_{t}\right)\sqrt{X_{t}}d z_{1t}+\sigma\sqrt{1-\rho^{2}}\sqrt{X_{t}}d z_{2t}\right],
$$  

where the drift term is left out (you do not have to compute the drift term!) and where  

$$
H_{t}=\frac{-\int_{t}^{\infty}e^{-\delta(s-t)}A(t,s)B(t,s)F_{t}^{-B(t,s)}d s}{\int_{t}^{\infty}e^{-\delta(s-t)}A(t,s)F_{t}^{-B(t,s)}d s}.
$$  

(h) Show that the expected excess rate of return on the stock at time $t$ can be written as  

$$
\psi_{t}=\gamma X_{t}\left(\sigma^{2}+\sigma\rho\eta H_{t}\right)
$$  

and as  

$$
\psi_{t}=\gamma\sigma_{C t}^{2}+\gamma\rho H_{t}\sigma_{C t}\sigma_{F t},
$$  

where $\sigma_{C t}$ and $\sigma_{F t}$ denote the percentage volatility of $C_{t}$ and $F_{t}$ , respectively.  

(i) What would the expected excess rate of return on the stock be if the dividend-consumption ratio was deterministic? Explain why the model with stochastic dividend-consumption ratio has the potential to resolve (at least partially) the equity premium puzzle.  

EXERCISE 8.10 Consider a discrete-time representative individual economy with preferences $\operatorname{E}[\sum_{t=0}^{\infty}\beta^{t}u(C_{t},D_{t}^{*})]$ , where $C_{t}$ is the consumption of perishable goods and $D_{t}^{*}$ is the consumption of services from durable goods. Assume a Cobb-Douglas type utility function,  

$$
u(C,D^{*})={\frac{1}{1-\gamma}}\left(C^{\alpha}(D^{*})^{1-\alpha}\right)^{1-\gamma}
$$  

where $\gamma>0$ and $\alpha\in[0,1]$  

(a) Write up the one-period state-price defator discount facor M+1 = S1 - c(Ct1,Di) in this economy.  

Assume that the services from the the durable goods are given by. $D_{t}^{*}=\theta(K_{t-1}+D_{t})$ , where. $K_{t-1}$   
is the stock of the durable entering period. $t$ and $D_{t}$ is the additional purchases of the durable good.   
in period $t$ . We can interpret $\theta$ as a depreciation rate or as the intensity of usage of the durable.   
We must have. $K_{t}=(1-\theta)(K_{t-1}+D_{t})$   
(b) Argue that if one additional unit of the durable is purchased in period $t$ , then the additional services from the durable in period $t+j$ will be $\theta(1-\theta)^{j}$   
(c) What is the marginal (life-time expected) utility, $\mathrm{MU}_{t}^{D}$ , from purchasing an extra unit of the durable in period $t$ \~.   
(d) If pt is the unit price of the durable good, argue that MUP = p:Cg(1-)-1(D+)(1-a)1-) in equilibrium.  

Now we allow for a stochastic intensity of usage, i.e. $\theta\:=\:\left(\theta_{t}\right)$ is a stochastic process. Define $X_{t}=(K_{t-1}+D_{t})/K_{t-1}$ $x_{t}=\ln X_{t}$ $c_{t}=\ln C_{t}$ , and $m_{t}=\ln M_{t}$  

(e) Show that. $m_{t+1}=\ln\beta+(\alpha(1-\gamma)-1)\Delta c_{t+1}+(1-\alpha)(1-\gamma)$ [(ln0t+1) + xt+1 + ln(1 - 0t)].  

Assume now that  

$$
\begin{array}{r l r}{\quad}&{\Delta c_{t+1}=g+\varepsilon_{t+1},\quad}&{\varepsilon_{t+1}\sim N(0,\sigma_{\varepsilon}^{2}),}\ {\quad}&{\ln\theta_{t+1}=h+\varphi\ln\theta_{t}+\nu_{t+1},\quad}&{\nu_{t+1}\sim N(0,\sigma_{\nu}^{2}),}\ {\quad}&{x_{t+1}=(1-w-\varphi)\ln\theta_{t}-\ln(1-\theta_{t})-h+a\nu_{t+1},}\end{array}
$$  

and that the two exogenous shocks $\varepsilon_{t+1}$ and $\nu_{t+1}$ have correlation $\rho$  

(f) Derive the continuously compounded equilibrium short interest rate $r_{t}^{f}=\ln R_{t}^{f}$ . You should find that the interest rate is constant if $w=0$  

EXERCISE 8.11 Consider a continuous-time economy with a representative agent with timeadditive subsistence HARA utility, i.e. the objective of the agent is to maximize.  

$$
\operatorname{E}\left[\int_{0}^{T}e^{-\delta t}{\frac{1}{1-\gamma}}\left(c_{t}-{\bar{c}}\right)^{1-\gamma}d t\right],
$$  

where $\bar{c}\geq0$ is the subsistence consumption level. Assume that aggregate consumption $c=\left(c_{t}\right)$ evolves as  

$$
d c_{t}=\mu c_{t}d t+\sigma{\sqrt{c_{t}(c_{t}-{\bar{c}})}}d z_{t},
$$  

where $z=\left(z_{t}\right)$ is a (one-dimensional) standard Brownian motion. Find the equilibrium shortterm interest rate $\boldsymbol{r}_{t}^{f}$ and the market price of risk $\lambda_{t}$ , expressed in terms of $c_{t}$ and the parameters introduced above. How do $\boldsymbol{r}_{t}^{f}$ and $\lambda_{t}$ depend on the consumption level? Are $\boldsymbol{r}_{t}^{f}$ and $\lambda_{t}$ higher or lower or unchanged relative to the standard case in which $\bar{c}=0$ 2.  
