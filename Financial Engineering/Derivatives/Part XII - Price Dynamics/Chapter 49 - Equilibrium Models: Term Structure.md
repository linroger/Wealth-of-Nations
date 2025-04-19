---
tags:
  - equilibrium_models
  - fixed_income_derivatives
  - risk_neutral_valuation
  - short_rate
  - term_structure
aliases:
  - Equilibrium Term Structure
  - Short Rate Models
key_concepts:
  - Black's model
  - Bond prices and options
  - Continuous time stochastic process
  - Path-dependent options
  - Risk-neutral valuation
---
# Equilibrium Models: Term Structure  

# Aims  

• To show how bond prices and option prices can be derived from a model of the short-rate, using risk-neutral valuation.   
• To investigate the properties of diferent time-series models of the short-rate.   
• To demonstrate how continuous time models of the term structure can be used to price bonds and options on bonds.  

Black’s model for pricing fxed income derivatives such as European options on bonds, on bond futures, as well as caps, foors, and swaptions, assumes the underlying variable is lognormal at expiration of the option. Black’s model cannot price derivatives which depend on the evolution of interest rates through time – such as American style options, callable bonds and other path-dependent options.  

The equilibrium yield curve approach assumes a specifc continuous time stochastic process for the one period (short) rate. The parameters of this process are then estimated from historical data. Bond prices and fxed income derivatives prices can then be derived mathematically and these prices depend directly on the estimated parameters of the stochastic process for the short-rate. Hence, in the equilibrium approach the current term structure is an output from the short-rate model. (In contrast, in the no-arbitrage BOPM applied to fxed-income assets the current term structure is used as an input to calibrate the lattice for the short-rate.) The sequence of steps in the equilibrium model approach are:  

• Choose a continuous time formulation for the short-rate and estimate the unknown parameters of this process, from historical data.  

• Mathematically, derive the whole term structure from the chosen short-rate model. • Use continuous-time mathematics to establish a PDE for the price of the fxed income derivative and solve the PDE to give a (closed-form) solution for the derivative’s price (which then depends on the estimated parameters of the short-rate model).  

It is worth noting at the outset that if the estimated time series model of the short-rate does not closely ‘ft’ the current observed behavior of interest rates, then the closed-form solution for the price of the derivative may not be accurate. However, it is not easy to empirically uncover what is the best statistical representation of the short-rate. This is a major practical drawback of this approach. However, we can still take a no-arbitrage approach, based on continuous time models for the short-rate, if we adapt these short-rate equations to ft today’s term structure. This is sometimes possible by making the drift rate in the short-rate equation a function of time (e.g. Ho and Lee 1986 and Hull and White 1990). The mathematics of equilibrium models quickly becomes complex so we only present a heuristic overview of the approach.  

# 49.1 RISK-NEUTRAL VALUATION  

The instantaneous short-rate $r(t)$ is the rate which applies over an infnitesimally short period of time (i.e. $t$ to $t+d t$ as $d t\rightarrow0$ ). Derivatives prices depend on the process for $r(t)$ in a risk-neutral world, so that if a derivative has a payof $V_{T}$ at time $T$ then the current value $V_{t}$ of the derivative is:  

$$
V_{t}=E^{*}[e^{-r_{a v}(T-t)}V_{T}]
$$  

where $E^{*}$ is the expected value in a risk-neutral world, $r_{a v}$ is the average value of the short-rate (between $t$ and $T$ ). We can use Equation 49.1 to price bonds and other fxed income assets (which depend on interest rates). For example, to value a zero-coupon bond which pays $V_{T}=\$1$ at $T$ , we have:  

$$
P(t,T)=E^{*}e^{-r_{a v}(T-t)}
$$  

If $R(t,T)$ is the observed continuously compounded interest rate on this ‘zero’ then it is known at time $t$ , hence:  

$$
P(t,T)=e^{-R(t,T)(T-t)}
$$  

It follows that:  

$$
\begin{array}{l}{{R(t,T)=-\ \displaystyle\frac{1}{(T-t)}\ln P(t,T)}}\\ {{R(t,T)=-\ \displaystyle\frac{1}{(T-t)}\ln[E^{*}e^{-r_{a v}(T-t)}]}}\end{array}
$$  

If we know the stochastic process for the short-rate $r$ in a risk-neutral world, then we can use (49.4b) to determine all the (continuously compounded) zero-coupon rates $R(t,T)$ – that is, the complete term structure. First, we examine alternative plausible models for the instantaneous short-rate rate.  

# 49.2 MODELS OF THE SHORT-RATE  

The risk-neutral process for the instantaneous short-rate $r(t)$ is usually an Ito process:  

$$
d r(t)=\mu(r,t)\ d t+\sigma(r,t)\ d z
$$  

where $d z$ is a Wiener process. We know today’s short-rate, $r(0)$ . Note that (49.5) is a ‘one-factor model’ since there is only one source of uncertainty, $d z=\varepsilon{\sqrt{d t}}$ . The crucial issue is how to choose a simplifed tractable version of (49.5) which adequately represents the actual stochastic behaviour of the short-rate. Whether or not the short-rate exhibits (very slow) mean reversion or is non-stationary is a contested empirical issue (particularly since the advent of the literature on cointegration – see Cuthbertson and Nitzsche 2004). Hence, models of the short-rate both with and without mean reversion are used. Some alternatives are given below.  

# 49.2.1 Rendleman–Bartter (1980)  

Here $\mu$ and $\sigma$ in Equation (49.5) are assumed to be constant, hence $r$ follows a GBM. But a GBM may give rise to negative values for the short-rate – so this model is somewhat unrealistic since observed nominal rates are hardly ever negative.1  

# 49.2.2 Ho–Lee (1986)  

The Ho–Lee model has no mean-reversion but allows the drift rate to depend on $t$ :  

$$
d r=\theta(t)d t+\sigma d z
$$  

The function $\theta(t)$ is chosen so that the resulting forward rate curve fts the empirically observed term structure of forward rates. The function $\theta(t)$ is the drift and represents the average direction in which the short-rate moves over time (and is independent of the level of $r$ so there is no mean-reversion). It can be shown that (approximately) $\theta(t)=F_{t}(0,t)$ where $F_{t}(0,t)=\partial F(0,t)/\partial t$ and $F(0,t)$ is the instantaneous forward rate. Hence the slope of the forward curve determines the direction the short-rate moves at time $t$ .  

With the Ho–Lee model, the price of zero-coupon bonds and European options on zero-coupon bonds can be determined analytically – see below. The Ho–Lee model can result in negative values for $r(t)$ and in this respect the Hull–White model is an improvement.  

# 49.2.3 Hull–White (1990)  

In contrast to the Ho–Lee model, the Hull–White model exhibits mean-reversion:  

$$
d r=[\theta(t)-a\ r]d t+\sigma d z=a[(\theta(t)/a)-r]d t+\sigma d z
$$  

It is the term in square brackets that produces mean-reversion – the short-rate $r$ is pulled towards its equilibrium value $r^{e q m}=\theta(t)/a.$ Thus if there were no stochastic shocks $r$ would move towards its long-run value of $\theta(t)/a$ , either from below if $\theta(t)>a\ r$ or from above if $\theta(t)<a\ r$ . The parameter $\theta(t)$ is determined by the initial term structure and it can be shown that:  

$$
\theta(t)=F_{t}(0,t)+a F(0,t)+(\sigma^{2}/2a)(1-e^{-2a t})
$$  

If we ignore the fnal term (which is small) then substituting $\theta(t)$ in 49.7, the drift of the short-rate at time $t$ is $F_{t}(0,t)+a[F(0,t)-r]$ . Hence, the path of the short-rate is determined by the slope of the initial forward rate curve, plus a mean-reverting component determined by the parameter $a$ .  

# 49.2.4 Black–Derman–Toy (1990)  

This is the same as the Ho–Lee equation but with $d(\ln{r})$ as the dependent variable and there is no mean-reversion:  

$$
d(\ln r)=\theta(t)d t+\sigma d z
$$  

Using Ito’s lemma the equation for $d r$ is:  

$$
d r=[\theta(t)+(1/2)\sigma^{2}]d t+\sigma d z
$$  

# 49.2.5 Black–Karasinski (1991)  

This approach takes the Black–Derman–Toy model and adds mean-reversion. If there are no stochastic shocks, ln $r$ approaches its equilibrium value $\ln r=\theta(t)/a$ .  

$$
d(\ln r)=(\theta(t)-a\ln r)+\sigma d z
$$  

The advantage of this model (unlike Ho–Lee and Hull–White) is that interest rates cannot be negative, but its weakness is the di\$culty in obtaining closed-form solutions for fxed income assets, even for simple cases such as the price of a zero-coupon bond.  

# 49.2.6 Vasicek (1977)  

This model has mean-reversion with a fxed value for the equilibrium level of interest rates of $r^{e q m}=b$ . The short-rate is assumed to be normally distributed and hence it is possible for $r$ to be negative:  

$$
d r=a[b-r]d t+\sigma d z
$$  

# 49.2.7 Cox–Ingersoll–Ross (CIR 1985)  

This has a fxed equilibrium value for the short-rate $r^{e q m}=b$ (as in the Vasicek model) and the standard deviation of the short-rate is proportional to $\sqrt{r}$ . Hence as $r\to0$ , the standard deviation approaches zero and short-rates are always non-negative. The risk-neutral process for $r$ is:  

$$
d r=a[b-r]d t+\sigma{\sqrt{r}}d z
$$  

In the ‘equilibrium model approach’, the parameters in the above equations are estimated from time series data. For example, in the CIR model, econometric estimates of $a,b$ and $\sigma$ are required.  

# 49.3 PRICING USING CONTINUOUS TIME MODELS  

The above equations are one-factor models of the short-rate, as there is only one source of uncertainty. It is usually mathematically fairly di\$cult (although not impossible) to obtain a closed-form solution for a derivative security, when the underlying short-rate is governed by one of the above dynamic equations. We therefore consider a few simple cases which have analytic solutions but as the reader should note, these are largely for illustrative purposes only.  

All the solutions take the short-rate equation as given and this leads to a PDE for the derivative’s price. The solution to this PDE then gives the (closed-form) solution for the price of the derivative. The price of the derivative depends on the estimates of the parameters of the short-rate equation and the current value of the underlying asset (e.g. either the current short-rate or the zero coupon bond price), as well as the time to maturity $T-t$ of the derivative security. When closed-form solutions are not possible, the PDE can be solved for the derivatives price using numerical methods (e.g. fnite-diference methods).  

# 49.3.1 Black–Scholes  

Suppose we have a fxed income derivative security with price $f(r,t)$ and the derivative has no payments until the terminal date $T$ (e.g. European style option). It can be shown that if $r(t)$ follows an Ito process (49.5), then the Black–Scholes PDE is (see Chapter 48) is:  

$$
{\frac{\partial f}{\partial t}}+{\frac{\partial f}{\partial r}}\mu+{\frac{1}{2}}{\frac{\partial^{2}f}{\partial r^{2}}}\sigma^{2}-r f=0
$$  

where $\mu$ and $\sigma$ may be functions of $r$ and $t$ . The payof for the derivative at maturity $T$ is assumed known – for example, for a call $f_{T}=\operatorname*{max}(0,V_{T}-K)$ where $V_{T}=$ price of the underlying asset.  

# 49.3.1.1 Solution 1: Zero-coupon Bond, Constant Short-rate  

We price a zero-coupon bond using the Black–Scholes PDE, under the assumption of either constant or stochastic interest rates. A constant short-rate implies ${\partial f}/{\partial r}=0$ and $\sigma^{2}=0$ , so (49.13) becomes:  

$$
{\frac{\partial f}{\partial t}}-r\ f=0\ \mathrm{or}\ d(\ln f)=r\ d t
$$  

This has a solution:  

$$
\ln f(t)=r t+k
$$  

where $k$ is an arbitrary constant. The boundary condition is $f(T)=M$ , the maturity value of the bond, which using (49.15) gives:  

$$
\ln f(T)=r T+k=\ln M
$$  

hence $k=\ln M-r\ T$ . Substituting in Equation (49.15) for $k$ gives:  

$$
\ln f(t,T)=-r\ (T-t)+\ln M
$$  

Therefore the price of a zero coupon bond with face value $M$ and maturity $T-t$ , when the interest rate is constant is:  

$$
f(t,T)=M e^{-r(T-t)}
$$  

49.3.1.2 Solution 2: Zero-coupon Bond, Stochastic Interest Rates  

Suppose the short-rate follows the Ho–Lee model:  

$$
d r=a\ d t+\sigma d z
$$  

where $a$ and $\sigma$ are estimated parameters. First we assume a solution for the price of the zero coupon bond $f(t,T)$ (with maturity value $\$1$ ) of the form:  

$$
f(t,T)=k(t,T)e^{-r(T-t)}
$$  

$$
\begin{array}{r}{\frac{\partial f}{\partial r}=-k(T-t)e^{-r(T-t)},\frac{\partial^{2}f}{\partial r^{2}}=+k(T-t)^{2}e^{-r(T-t)},\frac{\partial f}{\partial t}=k r e^{-r(T-t)}+\frac{\partial k(t,T)}{\partial t}e^{-r(T-t)},}\end{array}
$$  

Substitution in the Black–Scholes PDE, Equation (49.13), with $\mu=a$ gives:  

$$
\begin{array}{r}{\frac{\partial k(t,T)}{\partial t}=(T-t)\textit{k}a-\frac{1}{2}(T-t)^{2}\ \sigma^{2}k}\\ {\frac{d\ln k}{d t}=\Big[(T-t)\textit{a}-\frac{1}{2}(T-t)^{2}\sigma^{2}\Big]}\end{array}
$$  

We now integrate (49.20b) over $(t,T)$ and incorporate the boundary condition, $k(T,T)=\$1$ to give:  

$$
\ln k(t,T)=-(1/2)\ (T-t)^{2}a+(1/6)(T-t)^{3}\sigma^{2}
$$  

When (49.21) is substituted in (49.19) we have an explicit expression for the price $f(r,t)$ of a zero-coupon bond which depends on the time to maturity $T-t$ and the parameters of the short-rate process. The price of the zero-coupon bond will be consistent with no arbitrage along the yield curve (given the assumed Ho–Lee process for the short-rate rate). Substituting for $f(r,t)$ from (49.19) in (49.4b):  

$$
R(t,T)={\frac{1}{(T-t)}}\ln f(t,T)={\frac{-1}{(T-t)}}\ln k(t,T)+r(t)
$$  

Hence, in the Ho–Lee model an instantaneous change in the short-rate rate leads to an equal change in all long rates, that is, a parallel shift in the yield curve. This is a rather restrictive term structure model which could be made more fexible (and realistic) by using an alternative stochastic process for the short-rate rate, as illustrated below.  

# 49.4 BOND PRICES AND DERIVATIVE PRICES  

The Vasicek model incorporates mean reversion and it can be shown that the price of a zero-coupon bond is:  

$$
P(t,T)=k(t,T)e^{-B(t,T)r(t)}
$$  

where $k$ and $B$ depend on the parameters of the short-rate equation:  

$$
\begin{array}{l}{{k(t,T)=\displaystyle\exp\left[\frac{[B(t,T)-T+t](a^{2}b-\sigma^{2}/2)}{a^{2}}-\frac{\sigma^{2}B(t,T)^{2}}{4a}\right]}}\\ {{B(t,T)=\displaystyle\frac{1-e^{-a(T-t)}}{a}}}\end{array}
$$  

These expressions for $k$ and $B$ are more complex than those for the Ho–Lee model and they allow the yield curve (at time $t$ ) to be either (smoothly) upward or downward sloping or to exhibit a ‘humped shape’. The expression for long-rates is:  

$$
R(t,T)=-\ \frac{1}{(T-t)}\ln P(t,T)=\frac{1}{(T-t)}\ln k(t,T)+\frac{1}{(T-t)}B(t,T).r(t)
$$  

It is clear from the coe\$cient on $r(t)$ in the above equation that when $r(t)$ changes by $1\%$ , long-rates do not all move by the same amount as the short-rate, so shifts in the yield curve are not constrained to be parallel.  

# 49.4.1 Call Option on a Zero-coupon Bond  

It requires some complex continuous time mathematics to derive the closed-form solution for an interest rate derivative security based on the Vasicek, Ho–Lee, and Hull–White models. But Jamshidian (1989) has shown how a European call or put on a zero-coupon bond (or a coupon paying bond) can be priced. For example, for a call option on a zero-coupon bond that matures at time $s$ , the call premium has a closed-form solution of the form :  

$$
C a l l(0,T)=Q\ P(0,s)\ N(h)-K\ P(0,T)\ N(h-\phi)
$$  

where $Q=$ (principal) value of the bond, $K=$ strike price of the bond, $P(0,s)$ is the price of a deliverable bond with maturity value of $\$1$ at any time $s$ (including $s=T.$ ), $N(.)$ is the cumulative normal distribution and $T$ is the maturity of the option. The terms $h$ and $\phi$ are complex expressions which depend on $(K,T,t,Q)$ and the price of bonds of maturity $s$ and $T$ that is, $P(0,s)$ and $P(0,T)$ – as well as the parameters of the short-rate equation. The price of a put option is:  

$$
P u t(0,T)=K\ P(0,T)\ N(-h+\phi)-Q\ P(0,s)\ N(-h)
$$  

# 49.4.2 Option on Coupon Paying Bond  

The CIR and Hull–White short-rate models can also be used to price European call and put options on zero-coupon bonds and can be adapted to price options on coupon paying bonds (Jamshidian 1989). For all one-factor models of the short-rate, zero-coupon bond prices of all maturities move up and down in unison as the short-rate changes. This allows European options on coupon-bonds to be expressed as the sum of the prices of options on zero-coupon bonds. A European swaption can be viewed as an option on a coupon paying bond and hence can be valued using one-factor models of the short-rate.  

A further development is to assume the short-rate is infuenced by two stochastic factors, for example by assuming that $\sigma$ is also stochastic. Closed-form solutions for bond prices and interest rate derivatives can often be derived based on two-factor models (Longstaf-Schwartz 1992, Hull and White 1994).  

# 49.4.3 Hedging Using One-factor Models  

Although one-factor models are usually accurate enough for pricing bonds and some European options, we cannot rely on accurate hedging of interest rate options, since one-factor models usually assume restrictive shifts in the yield curve, which are not realistic. The price of fxed-income derivatives can change substantially due to non-parallel shifts in the yield curve and due to changes in the term structure of volatility.2  

As noted in an earlier chapter, there is not just one number for the delta, gamma, and vega of a fxed income derivative – because of diferent changes in spot rates and volatilities, along the yield curve. To put in place a hedge you frst have to decide what type of shift in the yield curve you want to hedge against (e.g. a parallel shift or a twist in the yield curve). You then calculate the appropriate delta and gamma by changing each of the spot rates by the required amount and recalculating the derivatives (option) price under this new scenario – this is the ‘perturbation approach’ to obtaining the Greeks.  

For example, the ‘5-year delta’ is the change in the value of your derivatives position for a small (1 bp) change in the 5-year spot yield. You can repeat this for spot rates at other maturities (e.g. 1 bp change in the 1-year spot rate) to give the derivatives portfolio deltas, for changes in several spot rates, along the yield curve. These changes in spot yields also imply changes in the forward curve and if the derivatives price depends on forward rates (e.g. caps and foors) these can also be incorporated in the calculation of delta.  

Having obtained the deltas of your derivatives portfolio with respect to changes in several spot rates, you can then choose hedging instruments to ofset these efects (e.g. using interest rate futures and other fxed-income options). The same procedure can be used to calculate the derivatives portfolio vega by changing volatilities along the yield curve, each by a small amount and calculating the change in the value of the derivative.  

# 49.5 SUMMARY  

• In the equilibrium model approach, the parameters of the chosen short-rate model are estimated. Continuous time mathematics is then used to derive a closed-form solution for bond prices and prices of fxed income derivatives (e.g. options on bonds, caps and foors etc.), which depend on the estimated parameters of the chosen short-rate equation. • The main problem with the equilibrium approach is that small errors in estimating the short-rate parameters can lead to large errors in the price of the derivative security.  

• Diferent models for the short-rate give diferent outcomes for the response of long-rates to changes in the short-rate – this is the ‘equilibrium’ term structure equation. Some short-rate models are restrictive, allowing only parallel shifts in the yield curve.   
• When hedging, if we assume non-parallel shifts in the yield curve then we need to calculate the portfolio delta (or gamma or vega) of the fxed-income derivative with respect to specifc changes in spot rates (or volatilities) along the yield curve – usually using a ‘perturbation approach’.   
• The gamma and vega risk on a portfolio of fxed income options (on the same underlying) can be hedged using other fxed income options (e.g. caps, foors, options on T-bonds and on T-bond futures) with diferent maturities and strike prices. Finally, interest rate futures can be used to hedge any residual delta-risk with respect to changes in interest rates.  

# EXERCISES  

# Question 1  

In the ‘equilibrium yield curve’ approach, explain why the estimated equation for the (one-period) short-rate is so important.  

# Question 2  

In the equilibrium yield curve approach, derivatives are priced assuming a risk-neutral world. What is the key equation connecting a fxed income derivative’s value today and the payof to the derivative at maturity, $T$ .  

# Question 3  

Explain why you might not want to use a geometric Brownian motion, $d r(t)=\mu(r,t)d t+$ $\sigma(r,t)d z$ , as a realistic model of the short-rate.  

# Question 4  

Write down the Vasicek equation for the short-rate and explain how mean reversion is incorporated in the equation.  

# Question 5  

What advantages does the Cox–Ingersoll–Ross (CIR) model for the short-rate have over the Vasicek model?  