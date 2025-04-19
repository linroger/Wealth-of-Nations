---
tags:
  - '#american_options'
  - '#arithmetic_brownian_motion'
  - '#black_scholes_merton_model'
  - '#compound_options'
  - '#credit_risk'
  - '#exchange_options'
  - '#ito_lemma'
  - '#linear_homogeneity'
  - '#option_greeks'
  - '#option_pricing'
---
# 17.8 RECAP AND PREVIEW

In this chapter, we examined the concept of linear homogeneity and showed how it can be used in option pricing. Linear homogeneity, which occurs in certain types of functions,. expresses a relationship between their differentials. Conveniently, the payoff of an option. is linearly homogeneous with respect to the asset price and exercise price. As such, we can. use this principle to derive the Black-Scholes-Merton model. In this chapter, we show how it can be used to also derive the value of an exchange option, as well as a forward start. option.

In Chapter 18, we introduce the concept of a compound option, which is an option on an option. It will go a long way toward helping us to price American options.

# APPENDIX 17A

# Linear Homogeneity and the Arithmetic Brownian Motion Model

Following the approach given in this chapter and applying Euler's rule to the ABM model call price, $c_{t}$ , focused on $S_{t},X_{\cdot}$ and $\sigma$ we have

$$
S_{t}\frac{\partial c}{\partial S}+X\frac{\partial c}{\partial X}+\sigma\frac{\partial c}{\partial\sigma}=c\big(S_{t},X\big).
$$

Assuming no dividends or other asset cash flows, we know

$$
\begin{array}{c c c}{\displaystyle\Delta_{c}=\frac{\partial c}{\partial S}=N\big(d_{n}\big)~\mathrm{a}}\ {\displaystyle\frac{\partial c}{\partial X}=-e^{-r_{c}\tau}N\big(d_{n}\big).}\ {\displaystyle\frac{\partial c}{\partial\sigma}=\frac{e^{-r_{c}\tau}\sigma_{n}n\big(d_{n}\big)}{\sigma}.}\end{array}
$$

By substituting these derivatives, we confirm that the ABM model has the property of linear homogeneity.

$$
\begin{array}{r l}&{S_{t}\frac{\partial c}{\partial S}+X\frac{\partial c}{\partial X}+\sigma\frac{\partial c}{\partial\sigma}}\ &{\quad=S_{t}N\big(d_{n}\big)+X\left[-e^{-r_{c}\tau}N\big(d_{n}\big)\right]+\sigma\frac{e^{-r_{c}\tau}\sigma_{n}n\big(d_{n}\big)}{\sigma}=c\big(S_{t},X\big).}\end{array}
$$

Recall

$$
\begin{array}{r l}&{c_{t}=\left(S_{t}-X e^{-r_{c}\tau}\right)N\left(d_{n}\right)+e^{-r_{c}\tau}\sigma_{n}n\left(d_{n}\right),\mathrm{where}}\ &{d_{n}=\frac{S_{t}-X e^{-r_{c}\tau}}{\sigma_{n}}\mathrm{~and~}}\ &{\sigma_{n}=\sigma\sqrt{\frac{e^{-2r_{c}\tau}-1}{2r_{c}}}.}\end{array}
$$

We introduce the current price of one zero-coupon bond with par value of $X$ as $B_{1t}\equiv e^{-r_{c}\tau}X$ and a second zero-coupon bond with par value of. $X$ as $B_{2t}\equiv e^{-r_{c}\tau}\sigma$ Further, recall that a linear operation performed on a linearly homogeneous function preserves its property of linear homogeneity, hence,.

where

$$
S_{t}\frac{\partial c}{\partial S}+B_{1t}\frac{\partial c}{\partial B_{1t}}+B_{2t}\frac{\partial c}{\partial B_{2t}}=c\big(S_{t},X\big),
$$

$$
\begin{array}{r}{\begin{array}{r l}&{\frac{\partial c}{\partial B_{1t}}=\frac{\partial c}{\partial X}\frac{\partial X}{\partial B_{1t}}=\frac{\partial c/\partial X}{\partial B_{1t}/\partial X}=-\frac{e^{-r_{c}\tau}N\left(d_{n}\right)}{e^{-r_{c}\tau}}=-N\left(d_{n}\right).}\ &{\frac{\partial c}{\partial B_{2t}}=\frac{\partial c}{\partial\sigma}\frac{\partial\sigma}{\partial B_{2t}}=\frac{\partial c/\partial\sigma}{\partial B_{2t}/\partial\sigma}=\frac{\frac{e^{-r_{c}\tau}\sigma_{n}n\left(d_{n}\right)}{\sigma}}{e^{-r_{c}\tau}}=\frac{\sigma_{n}n\left(d_{n}\right)}{\sigma}.}\end{array}}\end{array}
$$

Alternatively, let us simply start by assuming the option price is linearly homogeneous with respect to $S_{t},B_{1t};$ and $B_{2t}$ . Note that we are not starting with any specified stochastic process. Using Euler's rule, we know that the current option price, which is a function of $S_{t}$ and $t.$ , can be expressed as

$$
c_{t}=\gamma S_{t}+\omega B_{1t}+\upsilon B_{2t},
$$

where $\gamma$ is $\partial c_{t}/\partial S_{t}$ $\omega$ is $\partial c_{t}/\partial B_{1t}$ , and $\upsilon$ is $\partial c_{t}/\partial B_{2t}$ . An interpretation of Equation (17.14) is that one call option can be replicated by holding y units of the asset, each worth $S_{t}$ , and $(\omega+\upsilon)$ units of a risk-free bond with current value. $(X+\sigma)e^{-r_{c}\tau}$

The total differential of the option price is

$$
d c_{t}=\gamma d S_{t}+\omega d B_{1t}+\upsilon d B_{2t}.
$$

The differential $d S_{t}$ can be left in this form. Recall we obtained the differential for the risk-free bonds in Equation (17.17). Thus, we note

$$
\begin{array}{r}{d B_{1t}=r_{c}B_{1t}d t.}\ {{}}\ {d B_{2t}=r_{c}B_{2t}d t.}\end{array}
$$

Consequently, the call price differential is

$$
d c_{t}=\gamma d S_{t}+\omega r_{c}B_{1t}d t+\upsilon r_{c}B_{2t}d t.
$$

At this point, it is helpful to substitute $c_{t}-\gamma S_{t}$ for $\omega B_{1t}+\upsilon B_{2t}$ from Equation (17.14) leaving us

$$
d c_{t}=\gamma d S_{t}+\left(c_{t}-\gamma S_{t}\right)r_{c}d t.
$$

Now, we assume only that the call price depends on $S_{t}$ and $t$ and that the underlying follows. an Ito process expressed formally as. $d S_{t}=\alpha(S_{t},t)~d i+\sigma(S_{t},t)~d\mathrm{W}_{t},$ Allowing volatility to. be nonconstant, Ito's lemma can be used to obtain an equivalent expression for the change in the price of the call,.

$$
d c_{t}=\frac{\partial c_{t}}{\partial S_{t}}d S_{t}+\frac{\partial c_{t}}{\partial t}d t+\frac{1}{2}\frac{\partial^{2}c_{t}}{\partial{S_{t}}^{2}}\sigma^{2}\big(S_{t},t\big)d t,
$$

which we can now set Equation (17.20) equal to Equation (17.19). And by choosing y to equal $\partial c_{t}/\partial S_{t}$ , we eliminate the risky term $d S_{t}$ , leaving the following non-stochastic partial differential equation,

$$
c_{t}r_{c}=\frac{\partial c_{t}}{\partial S_{t}}r_{c}S_{t}+\frac{\partial c_{t}}{\partial t}+\frac{1}{2}\frac{\partial^{2}c_{t}}{\partial S_{t}^{2}}\sigma^{2}\big(S_{t},t\big),
$$

which is a second order partial differential equation. This partial differential equation solution, subject to the boundary condition $c_{T}=\operatorname*{max}\bigl(0,S_{T}-\bar{X}\bigr)$ , depends on the specification of the volatility term. The PDE in Equation (17.73) is not the Black-Scholes-Merton PDE unless we assume volatility is constant.

If we assume a generic arithmetic Brownian motion of the form $d S_{t}=\alpha\big(S_{t},t\big)d t+$ $\sigma d\mathbb{W}_{t}$ , we obtain the ABM model which is the solution to

$$
c_{t}r_{c}=\frac{\partial c_{t}}{\partial S_{t}}r_{c}S_{t}+\frac{\partial c_{t}}{\partial t}+\frac{1}{2}\frac{\partial^{2}c_{t}}{\partial S_{t}^{2}}\sigma^{2},
$$

subject to the value at expiration of

$$
c_{T}={\mathrm{max}}\big(0,S_{T}-X\big).
$$

# APPENDIX 17B

# Multivariate Ito's Lemma

Consider $_n$ Ito processes at time $t.$ , expressed as

$$
d X_{t}=\mu(X,t)d t+\Sigma(X,t)d W_{t},
$$

where

$$
d X_{t}\equiv\left[\begin{array}{c}{{d x_{1}}}\ {{d x_{2}}}\ {{\vdots}}\ {{d x_{n}}}\end{array}\right],
$$

$$
\mu(X,t)\equiv{\left[\begin{array}{l}{\mu_{1}(X,t)}\ {\mu_{2}(X,t)}\ {\qquad\vdots}\ {\mu_{n}(X,t)}\end{array}\right]},
$$

$$
\Sigma(X,t)\equiv\left[\begin{array}{c c c c}{\sigma_{1,1}(X,t)~\sigma_{1,2}(X,t)}&{\cdot\cdot\cdot}&{\sigma_{1,m}(X,t)}\ {\sigma_{2,1}(X,t)~\sigma_{2,2}(X,t)}&{\cdot\cdot\cdot}&{\sigma_{2,m}(X,t)}\ {\vdots}&{\vdots}&{\cdot}&{\vdots}\ {\sigma_{n,1}(X,t)~\sigma_{n,2}(X,t)}&{\cdot\cdot\cdot}&{\sigma_{n,m}(X,t)}\end{array}\right],\mathrm{and}
$$

$$
d\mathrm{W}_{t}\equiv\left[\begin{array}{c}{{d\mathrm{W}_{1,t}}}\ {{d\mathrm{W}_{2,t}}}\ {{\vdots}}\ {{d\mathrm{W}_{n,t}}}\end{array}\right].
$$

Note that each Ito process can depend on up to $^m$ Wiener processes or

$$
d x_{k,t}=\mu_{k}(X,t)d t+\sum_{j=1}^{m}\sigma_{k,j}(X,t)d W_{j,t}.
$$

Suppose

$$
y_{t}=f(X,t).
$$

Then

$$
\begin{array}{l}{{d y_{t}=\left\{\displaystyle\frac{\partial f(X,t)}{\partial t}+\sum_{k=1}^{n}\displaystyle\frac{\partial f(X,t)}{\partial x_{k}}\mu_{k}(X,t)\right.}}\ {{\displaystyle\left.\qquad+\displaystyle\frac{1}{2}\sum_{i=1}^{n}\sum_{k=1}^{n}\displaystyle\frac{\partial^{2}f(X,t)}{\partial x_{i}\partial x_{k}}\sum_{j=1}^{m}\sum_{l=1}^{m}\sigma_{i j}(X,t)\sigma_{k l}(X,t)\rho_{j l}(X,t)\right\}d t}}\ {{\displaystyle\left.\qquad+\sum_{k=1}^{n}\displaystyle\frac{\partial f(X,t)}{\partial x_{k}}\sum_{j=1}^{m}\sigma_{k,j}(X,t)d W_{j,t}.\right.}}\end{array}
$$

# APPENDIX 17C

# Greeks of the Exchange Option Model

We obtain the first and second derivatives in symbolic form. The deltas with respect to the two asset prices were obtained previously but not carried out in detail. They are.

$$
\begin{array}{r l r}{\lefteqn{\frac{\partial c\left(S_{1},S_{2}\right)}{\partial S_{1}}=\frac{\partial S_{2}c(S,1)}{\partial S_{1}}=S_{2}\frac{\partial c(S,1)}{\partial S_{1}}=S_{2}\frac{\partial c(S,1)}{\partial S}\frac{\partial S}{\partial S_{1}}=S_{2}N\big(d_{1}\big)\frac{1}{S_{2}}=N\big(d_{1}\big)}}\ &{}&{\frac{\partial c\left(S_{1},S_{2}\right)}{\partial S_{2}}=\frac{\partial S_{2}c(S,1)}{\partial S_{2}}=S_{2}\frac{\partial c(S,1)}{\partial S}\frac{\partial S}{\partial S_{2}}+c(S,1)=S_{2}\frac{\partial c(S,1)}{\partial S}\left(-\frac{S}{S_{2}}\right)+c(S,1)}\ &{}&{=c(S,1)-S\frac{\partial c(S,1)}{\partial S}=c(S,1)-S N\big(d_{1}\big)}\ &{}&{=S N\big(d_{1}\big)-N\big(d_{2}\big)-S N\big(d_{1}\big)=-N\big(d_{2}\big).}&{\quad(1)^{\frac{1}{\beta}},}\end{array}
$$

Therefore, applying what we know from Black-Scholes-Merton, the gammas are obtained as

$$
\begin{array}{l}{{\displaystyle\frac{\partial^{2}c\left(S_{1},S_{2}\right)}{\partial S_{1}^{2}}=\frac{\partial^{2}c(S,1)}{\partial S^{2}}\left(\frac1{S_{2}}\right)=\frac{n\left(d_{1}\right)}{S\sigma\sqrt\tau}\left(\frac{1}{S_{2}}\right)=\frac{n\left(d_{1}\right)}{S_{1}\sigma\sqrt\tau}}}\ {{\displaystyle\frac{\partial^{2}c\left(S_{1},S_{2}\right)}{\partial S_{2}^{2}}=\frac{\partial^{2}c(S,1)}{\partial S^{2}}\left(\frac{S^{2}}{S_{2}}\right)=\frac{n\left(d_{2}\right)}{S_{2}\sigma\sqrt\tau}}.}\end{array}
$$

Hence, the theta is

$$
\frac{\partial c\big(S_{1},S_{2}\big)}{\partial t}=-\frac{S_{1}\sigma e^{-d_{1}^{2}/2}}{2\sqrt{2\pi T}}.
$$

Recall for us to arrive at theta, we first need the derivative with respect to time to expiration or

$$
\begin{array}{c}{\displaystyle\frac{\partial c(S_{1},S_{2})}{\partial\tau}=S_{2}\frac{\partial c(S,1)}{\partial\tau}=S_{2}\left[S\frac{\partial N(d_{1})}{\partial d_{1}}\frac{\partial d_{1}}{\partial\tau}-\frac{\partial N(d_{2})}{\partial d_{2}}\frac{\partial d_{2}}{\partial\tau}\right]}\ {\displaystyle~=S_{2}\left[S n(d_{1})\frac{\partial d_{1}}{\partial\tau}-n(d_{2})\frac{\big(\partial d_{1}-\sigma\sqrt{\tau}\big)}{\partial\tau}\right]}\ {\displaystyle~=S_{1}n(d_{1})\frac{\partial d_{1}}{\partial\tau}-n(d_{2})\frac{\partial d_{1}}{\partial\tau}+n(d_{2})\frac\sigma{2\sqrt{\tau}}.}\end{array}
$$

We know the first two terms cancel and we obtain

$$
\frac{\partial c}{\partial\tau}=\frac{\sigma}{2\sqrt{\tau}}n\big(d_{2}\big).
$$

Recall we define theta as the derivative with respect to the point in time, that is, $\partial c/\partial t$ and we defined the time to expiration as $\tau=T-t$ Hence,

$$
\Theta_{c}=\frac{\partial c}{\partial t}=-\frac{\sigma S}{2\sqrt{\tau}}n\left(d_{1}\right).
$$

The vegas are

$$
\begin{array}{l}{\displaystyle\frac{\partial c\big(S_{1},S_{2}\big)}{\partial\sigma_{1}}=S_{1}n\big(d_{1}\big)\sqrt{\tau}\Big(\frac{\sigma_{1}-\rho\sigma_{2}}{\sigma}\Big)}\ {\displaystyle\frac{\partial c\big(S_{1},S_{2}\big)}{\partial\sigma_{2}}=S_{1}n\big(d_{1}\big)\sqrt{\tau}\Big(\frac{\sigma_{2}-\rho\sigma_{1}}{\sigma}\Big).}\end{array}
$$

And the partial derivative with respect to the correlation is

$$
\frac{\partial c(S_{1},S_{2})}{\partial\rho}=-S_{1}n(d_{1})\sqrt{\tau}\left(\frac{\sigma_{2}\sigma_{1}}{\sigma}\right).
$$

Note that the risk-free rate does not appear in the price equation. Hence, there is no rho.

# QUESTIONS AND PROBLEMS

1 Given the following standard ABM model, demonstrate that it does not have the property of linear homogeneity in. $S_{t}$ and $X$ alone.

$$
\begin{array}{r l}&{c_{t}=\left(S_{t}-X e^{-r_{c}\tau}\right)N\left(d_{n}\right)+e^{-r_{c}\tau}\sigma_{n}n\big(d_{n}\big),\mathrm{wh}}\ &{d_{n}=\frac{S_{t}-X e^{-r_{c}\tau}}{\sigma_{n}}\mathrm{~and~}}\ &{\sigma_{n}=\sigma\sqrt{\frac{e^{-2r_{c}\tau}-1}{2r}}.}\end{array}
$$

You are given the following partial derivatives:

$$
\begin{array}{l}{\displaystyle\frac{\partial c}{\partial S}=N\big(d_{n}\big)\mathrm{~and~}}\ {\displaystyle\frac{\partial c}{\partial X}=-e^{-r_{c}\tau}N\big(d_{n}\big).}\end{array}
$$

2Assume a stock has a $\$1$ price and a corresponding one year call option is at-themoney. Further, assume no dividends and the risk-free rate is zero. For this case, compare the results of the Black-Scholes-Merton model and ABM model.

3Demonstrate that American exchange options on non-dividend-paying assets will not. be exercised early. Thus, American exchange options will be worth the same as European exchange options.

4 A hedge fund recently hired a new and highly talented manager. In negotiations, they will receive $20\%$ of any superior performance above the SPY (an exchange-traded fund that seeks to mimic an investment in the S&P 500 index) over the next year. If they underperform the SPy, then their compensation is zero. Based on this information, identify the valuation model that would provide the fair market value of this compensation scheme. Further, explain the manager's incentive based on this compensation scheme.

5 For two constants, $\alpha_{1}>0$ and $\alpha_{2}>0$ prove the following put-call parity representation:

$$
c\big(\alpha_{1}S_{1},\alpha_{2}S_{2}\big)-p\big(\alpha_{1}S_{1},\alpha_{2}S_{2}\big)=\alpha_{1}S_{1}-\alpha_{2}S_{2}.
$$

6 Prove the lower bound of a call spread option is $c_{t}\ge\operatorname*{max}\bigl(0,\alpha_{1}S_{1t}-\alpha_{2}S_{2t}-X e^{-r_{c}\tau}\bigr),$

# NOTES

1. Alternatively, we could assume each asset follows arithmetic Brownian motion with geometric drift. In this case, the subtraction of two normally distributed variables is also normally distributed, hence, arriving at the pricing model is straightforward.
2. See Appendix 17B for a formal statement of the multivariate Ito's lemma.
3. For extensive discussion of spread options, see Brooks and Cline (2015).

# Compound Option Pricing

n this chapter we study compound options, which are options in which the underlying. is an option. Thus, a compound option is an option on an option. Compound options are rarely seen directly in practice, but that is not an excuse to ignore them. For example, they are extremely valuable tools for understanding credit risk. Compound option models have also been deployed when addressing contingency hedging (e.g., hedging an extended. bid on a project), various aspects of drug development, and captions (i.e., an option on a. cap where a cap is a series of interest rate options that can be used to hedge, say, a loan portfolio for a bank). As we will show here, an option on the stock of a company that has debt is a compound option. In addition, compound option theory provides a means for. pricing American options.

After introducing specific notation for compound options, we show how an option perspective on a common stock can aid in understanding the credit risk related to a firm. With this foundation, we proceed to explore options on stock as compound options. Next, we turn to a formal treatment of compound options complete with boundary conditions and parity relationships. We then turn to a careful examination of Geske's call on call model as he applied it to stock options. Next, we identify a generalized compound option model that addresses four different versions of compound options as well as incorporates cash flow yields on both the underlying instrument as well as the underlying option. We conclude this chapter with a brief look at installment options, which are variations of compound options.

The original development of the compound option model was Geske (1979b). The. context in which this model was developed was that of a call option on a stock, which is itself a call option on the assets of the firm, an idea set forth by Black and Scholes and part of the foundation for the understanding of credit risk, as mentioned. Although the Black-Scholes-Merton model would appear to properly price such a call option, if all the basic assumptions are met, Geske's compound option model shows that the volatility of the stock is dynamic because it is determined by the leverage of the firm, meaning how much debt it uses. Leverage, of course, changes with changes in the value of the stock. Recall that the Black-Scholes-Merton model assumes constant volatility. And although most people use the Black-Scholes-Merton model to price options on stocks, technically the compound model is more appropriate.

The compound option model requires significantly more variables, so we briefly intro-. duce some of the terms. Figure 18.1 illustrates three important dates with compound options: the trade date $(t)$ , the compound option expiration date $(T_{1})$ , and the underlying option expiration $(T_{2})$ . There are three important periods of time corresponding to the. compound option: the period of time until the compound option expires $(\tau_{1})$ , the period of time until the underlying option expires $(\tau_{2})$ , and the period of time between the compound option expiration and the underlying option expiration $(\tau_{12})$

![](c6c049a2d2c03a7c66f521dfbf7f22108b78374666b9874b9f320f5b4a3c4f5b.jpg)
FIGURE 18.1 Compound Option Timeline

Further, the compound option model requires the compound option exercise price $(X_{\mathrm{C}})$ and the underlying option exercise price $(X_{U})$ . The remaining underlying parameters are as defined before with $S_{t}$ denoting the underlying instrument price, $r_{c}$ denoting the annualized continuously compounded risk-free rate, and $\sigma$ denoting the annualized standard deviation of the continuously compounded rates of return of the underlying instrument.

Finally, we introduce an underlying option yield, $\widehat{q}$ Compound options are often used in modeling complex financial valuation problems that are often not related to traditional stock options. A yield on the underlying option may be useful for many applications of compound options, including the default option embedded in bonds, drug development. applications with ongoing expenses (negative option yield), and some forms of contingency hedging. Although standard stock options do not pay any dividends, there may be times when we will wish to model options that do involve cash flows. We explore one case later. in this chapter.

We motivate compound options first with options on common stock.
