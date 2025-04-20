---
tags:
  - barrier_options
  - black_scholes
  - exotic_options
  - option_pricing
  - path_dependent
aliases:
  - Barrier Option Pricing
  - Knock-in Options
  - Knock-out Options
key_concepts:
  - Advantages for buyer/writer
  - Analytical pricing solution
  - Barrier option properties
  - Continuous vs discrete monitoring
  - Option valuation techniques
---

# [[7. Black Scholes Model#2 The Volatility Surface|Exotic Options]]

## [[7. Black Scholes Model#2 The Volatility Surface|Exotic Options]]:  Pricing Path-Dependent single Barrier Option contracts

# Abstract

This paper discusses the basic properties of barrier options and an analytical solution  for pricing such contracts. The significance of monitoring is considered, for example  the difference between continuous monitoring and discrete monitoring. Pitfalls  arising from a naïve application of standard option valuation techniques to barrier  options are pointed out. We also discuss the practical issues related to barrier options,  such as the advantages they provide to the buyer as well as to the writer, and consider  practical issues behind valuation.

Key words and phrases: Barrier Options, Knock-out Options, Knock-in Options,  Rebate, Path-dependant Payoff, Black & Scholes, restricted density, Reflection  Principal.
# 1.  Introduction

Barrier options are a class of exotic options which were first priced by Merton  (1973). The most common approaches used to price these type of derivatives are the  expectations methods and the differential equation methods. The expectations  method has been worked out in detail by Rubinstein and Reiner (1991) and also Rich  (1994). The expectations pricing method requires the determination of the riskneutral densities of the underlying price as it breaches the barrier from above and  below. If rebates apply then the first exit time densities through the barrier are also  required. Barrier option prices are then obtained, in the usual way, by integrating the  discounted barrier option pay-off function over the calculated densities. It is  considered difficult to work out these densities when using the expectation approach,  it is however remarkable that closed form solutions for all types of barrier options are  in fact obtained.

A brief discussion of the differential equation method can be found in Wilmott  (1993). The basic idea of this approach is that all barrier options satisfy the BlackScholes partial differential equation but with different domains, expiry conditions  and boundary conditions. In principal, these partial differential equations (PDE's) can  be transformed to the diffusion equation and solved. Once again the analysis is  complex and also requires the evaluation of integrals, but the same closed form  solutions are obtained. The solution from the PDE method is of course related to the  solutions from the expectation approach. Ritchken (1995) has investigated  computational aspects of barrier option pricing using binomial and trinomial lattice.

In this paper, the PDE method will be adopted to show that a direct and simple  analysis leads to the closed form solutions. The method employs symmetry  properties of the Black-Scholes (B&S) PDE and requires little more than the wellknown basic European vanilla option solutions.

# 2. Pricing of simple contingent claims

# 2.1 Asset Price Dynamics and Ito Process

The dynamics of stock price   $S$    are represented by the following Ito process with a  drift rate of   $\mu S$   and variance rate of   $\sigma^{2}S^{2}$  :

$$
d S=\mu S d t+\sigma S d X
$$

divide both sides by  $S,$  ,  to obtain the following stochastic differential equation (SDE):

$$
d S/S=\mu d t+\sigma d X
$$

This process of stock prices, known also as the geometric Brownian motion, can be  written in discrete time setting as

$$
\Delta S/S=\mu\Delta t+\sigma\varepsilon\Delta d t
$$
Where   $\varepsilon$  is a random sample from distribution with zero mean and a unit standard  deviation. If we set   $\sigma=0$  , the term involving   $d X$  in equation (1.2), would drop out  and we are left with ordinary differential equation (ODE)

$$
d S/S=\mu d t\quad{\mathrm{or~}}d S/d t=\mu S
$$

Where   $\mu$   is constant this can be solved exactly to give exponential growth in the  value of the asset, i.e.

$$
S=S_{\scriptscriptstyle0}\exp[\mu(t-t_{\scriptscriptstyle0})]
$$

The random term   $d X$   from equation (1.2) is known as a Weiner process which has  the properties defined below. The model has the stock price growing at a constant  rate   $\mu$  , with random fluctuations superimposed. These fluctuations are proportional  to the standard deviation of the asset price and are dependant on standard normal  random variable. This type of process is known as Weiner process.

Definition 1.1  A stochastic process  $X$    is called Weiner process if the following hold.

1.   $W(\theta)=0$  W(0) = 0

 2.  The process   $W$    has independent increments, i.e. if  $r<s\leq t<u$    then

    $\ W(u)\cdot W(t)$   and   $W(s)\,.W(r)$    are independent stochastic variables.

 3.  For  $s<t$   the stochastic variable   $W(t)\textrm{-}W(s)$   has a Gaussian distribution

    $N(0,{\sqrt{t-s}})$  ).

 4.     W has continuous trajectories

We can write   $d X$    as

$$
d X=\phi\sqrt{d t}
$$

where   $\phi$   is a random variable with   $N\sim(0,\!1)$   and a probability density function  given by

$$
\frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}{\phi}^{2}}\,,\quad\mathrm{for}\quad-\infty<{\phi}<\infty
$$

Define the expectation operator   $\xi$  by

$$
\xi[F(.)]\!=\!\frac{1}{\sqrt{2\pi}}\!\int_{\infty}^{\infty}\!F(\phi)e^{-\frac{1}{2}\phi^{2}}d\phi,
$$

For any function  $F_{z}$  ,  then

$$
\xi[\phi]=0\qquad\mathrm{and}\qquad\xi[\phi^{2}\,]=1
$$
It follows that from equation 1.2, the expectation and variance of   $d S$    can be written as

$$
\begin{array}{l}{{\xi[d S]=\xi[\mu S d t+\sigma S d X]=\mu S d t}}\\ {{V a r[d S]=\xi[d S^{2}\,]-\xi[d S]^{2}=\xi[\sigma^{2}S^{2}d X^{2}\,]=\sigma^{2}S^{2}d t}}\end{array}
$$

# 2.2 Ito's Lemma

Ito's Lemma is an important result about the manipulation of random variables.  While Taylor's theorem allows one to manipulate functions of deterministic  variables, Ito's Lemma can be applied to manipulate functions of random variables. It  relates the small change in a function of random variable to the small change of in  the random variable itself.

2 We will use the following Ito's multiplication table

$$
\begin{array}{c c c}{{(d X)^{2}}}&{{=}}&{{\quad d t,}}\\ {{d t.d X}}&{{=}}&{{\quad O,}}\\ {{(d t)^{2}}}&{{=}}&{{\quad O,}}\end{array}
$$
 dt,

${\mathrm{If}}f(S)$    is a smooth function of  $S$    and we vary   $S$    by small amount   $d S$  , then the function    $f$  will also vary amount small amount   $d\!f.$   Using the Taylor series expansion we can  write the change of the function   $f$   as:

$$
d\!f=\!\frac{d\!f}{d\!S}\,d\!S+\frac{1}{2}\frac{d^{\,2}f}{d\!S^{\,2}}\,d\!S^{\,2}\,+...,
$$

Since   $d S$    is given by equation (1.1), we square it to find that

$$
\begin{array}{r c l}{{}}&{{}}&{{d S^{2}=(\mu S d t+\sigma S d X)^{2}}}\\ {{}}&{{}}&{{=\sigma^{2}S^{2}d X^{2}+2\sigma\mu S^{2}d t d X+\mu^{2}S^{2}d t^{2}}}\end{array}
$$

the first term is the largest for small   $d t$    and dominates the other two terms. We are  then left with

$$
d S^{2}=\sigma^{2}S^{2}d X^{2}+\dots
$$

Since  $d X^{2}\to d t,$  ,

$$
d S^{2}=\sigma^{2}S^{2}d t.
$$
We now substitute this result and equation 1.1 into 1.6, such that we find:

$$
\begin{array}{l c r}{\displaystyle{d f=\frac{d f}{d{\cal S}}\left(\mu{\cal S}d t+\sigma{\cal S}d X\right)+\frac{1}{2}\frac{d^{2}f}{d{\cal S}^{2}}\,\sigma^{2}{\cal S}^{2}d t}}\\ {\displaystyle{d f=\frac{d f}{d{\cal S}}\,\mu{\cal S}d t+\frac{d f}{d{\cal S}}\,\sigma{\cal S}d X+\frac{1}{2}\frac{d^{2}f}{d{\cal S}^{2}}\,\sigma^{2}{\cal S}^{2}d t}}\\ {\displaystyle{d f=(\frac{d f}{d{\cal S}}\,\mu{\cal S}+\frac{1}{2}\frac{d^{2}f}{d{\cal S}^{2}}\,\sigma^{2}{\cal S}^{2})d t+\sigma{\cal S}\,\frac{d f}{d{\cal S}}\,d X}}\end{array}
$$

This is Ito's Lemma relating the small change in a function of random variable to the  small change in the variable itself.  The first component of the right hand side  equation is deterministic component of the change in the function    $f$   and is  proportional to   $d t.$  .  The second component is a random component and is proportional  to  $d t$  .

The result (1.8) can be extended to a function of two variable which entails the use of  partial derivatives since there are two independent random variables, i.e.  $S$    and  $t.$  .  We  can expand   $f\!(S+d S,\,t+d t)$    in a Taylor series about  $(S,\,t)$   to get

$$
d\!f=\!\frac{\partial f}{\partial\boldsymbol{S}}\,d\boldsymbol{S}+\frac{\partial f}{\partial t}\,d t+\frac{1}{2}\frac{\partial^{2}f}{\partial\boldsymbol{S}^{2}}\,d\boldsymbol{S}^{2}\,+...,
$$

$$
d f=(\frac{\partial f}{\partial S}\,\mu S+\frac{1}{2}\frac{\partial^{2}f}{\partial S^{2}}\,\sigma^{2}S^{2}\,+\frac{\partial f}{\partial t})d t+\sigma S\,\frac{\partial f}{\partial S}\,d X
$$

# 3.1 The Black -Scholes Formulation of Option Pricing

We illustrate how to use the riskless hedging principle to derive the governing partial  differential equation for the price of European call. The derivation follows the  approach used by Black and Scholes in their seminal paper (1973). They made the  following assumption in the financial market:

(i)  trading takes place continuously in time;

 (ii)  the riskless interest  $r$    is known and constant over time;

 (iii)  the asset pays no dividend;

 (iv)  there are no transaction costs in buying or selling the asset or the option,

   and no taxes;

 (v)  there are no riskless arbitrage opportunities;

 (vi)  short selling is permitted and the assets are divisible.

Let   $V(S,\,t)$    be the value of an option whose value depends on both  $S$    and  $t.$  .  Using Ito's  Lemma, equation (1.9), the random walk followed by   $\mathrm{V}$   can be written
$$
d V=({\frac{\partial V}{\partial S}}\,\mu S+{\frac{1}{2}}{\frac{\partial^{2}V}{\partial S^{2}}}\,\sigma^{2}S^{2}\,+{\frac{\partial V}{\partial t}})d t+\sigma S{\frac{\partial V}{\partial S}}\,d X
$$

If we now construct a portfolio of consisting a long position of the option and a short  position of the underlying asset   $(-\Delta)$  , the value of the portfolio is

$$
\Pi=V-\Delta S
$$

The change in the portfolio in one-time step is

Let;

$$
\begin{array}{l}{\displaystyle d\Pi=d V-\Delta d S}\\ {\displaystyle\Delta=\frac{\partial V}{\partial S}}\end{array}
$$

Putting (1.1), (3.1) and (3.2) together, the change in the portfolio can be written as

$$
\begin{array}{l}{\displaystyle{d\Pi=(\frac{\partial V}{\partial S}\,\mu S+\frac{1}{2}\frac{\partial^{2}V}{\partial S^{2}}\sigma^{2}S^{2}+\frac{\partial V}{\partial t})d t+\sigma S\frac{\partial V}{\partial S}\,d X}}\\ {\displaystyle{-\,\Delta(\mu S d t+\sigma S d X)}}\\ {\displaystyle{=(\frac{\partial V}{\partial S}\,\mu S+\frac{1}{2}\frac{\partial^{2}V}{\partial S^{2}}\sigma^{2}S^{2}+\frac{\partial V}{\partial t})d t+\sigma S\frac{\partial V}{\partial S}\,d X-\Delta\mu S d t-\Delta\sigma S d X}}\end{array}
$$

Since

$$
\begin{array}{l}{\displaystyle\Delta=\frac{\partial V}{\partial S}}\\ {\displaystyle d\Pi=(\frac{\partial V}{\partial S}\,\mu S+\frac12\frac{\partial^{2}V}{\partial S^{2}}\,\sigma^{2}S^{2}\,+\frac{\partial V}{\partial t})d t+(\sigma S\frac{\partial V}{\partial S}\,d X-\mu S\frac{\partial V}{\partial S}\,d t-\sigma S\frac{\partial V}{\partial S}\,d X}\end{array}
$$

by simply rearranging the above equation, we have

$$
d\Pi=(\mu S\,\frac{\partial V}{\partial S}-\mu S\,\frac{\partial V}{\partial S})d t+(\sigma S\,\frac{\partial V}{\partial S}\,d X-\sigma S\,\frac{\partial V}{\partial S}\,d X)+(\frac{1}{2}\,\frac{\partial^{2}V}{\partial S^{2}}\,\sigma^{2}\,S^{2}\,+\frac{\partial V}{\partial t})d t
$$

The first two terms from the right hand side of the equation cancels each other and  the random component in the equation is eliminated. This results in a portfolio whose  increments is wholly deterministic:

$$
d\Pi=({\frac{\partial V}{\partial t}}\!+\!{\frac{1}{2}}{\frac{\partial^{2}V}{\partial\!S^{2}}}\sigma^{2}S^{2}\,)d t
$$
Note the uncertainty due to   $d X$    is cancelled out and  $u$  ,  the premium for risk (return on    $S)$  ) ,  is also cancelled out. Not only that the term   $d\Pi$  has no uncertainty, it is also  preference free and not dependant on   $u$  ,  a parameter controlled by investors risk  aversion. If the portfolio value is fully hedged, then no arbitrage implies that it myst  earn only risk free rate of return.   We then have

$$
r\Pi d t=({\frac{\partial V}{\partial t}}\!+\!{\frac{1}{2}}{\frac{\partial^{2}V}{\partial\boldsymbol{S}^{2}}}\sigma^{2}\boldsymbol{S}^{2}\,)d t
$$

using equation (3.2)

$$
r(V-\Delta S)d t=({\frac{\partial V}{\partial t}}+{\frac{1}{2}}{\frac{\partial^{2}V}{\partial S^{2}}}\sigma^{2}S^{2}\,)d t
$$

since

$$
\Delta\,{=}\,\frac{\partial V}{\partial S}
$$

$$
r(V-\frac{\partial V}{\partial S}S)d t=(\frac{\partial V}{\partial t}+\frac{1}{2}\frac{\partial^{2}V}{\partial S^{2}}\sigma^{2}S^{2}\,)d t
$$

$$
(r V-r S)\frac{\partial V}{\partial S})d t=(\frac{\partial V}{\partial t}+\frac{1}{2}\frac{\partial^{2}V}{\partial S^{2}}\sigma^{2}S^{2}\,)d t
$$

dividing both sides by   $d t$    and rearranging the equation, we have

$$
r V={\frac{\partial V}{\partial t}}+{\frac{1}{2}}{\frac{\partial^{2}V}{\partial S^{2}}}\,\sigma^{2}S^{2}+r S{\frac{\partial V}{\partial S}}
$$

finally

$$
\frac{\partial V}{\partial t}+\frac{1}{2}\frac{\partial^{2}V}{\partial S^{2}}\,\sigma^{2}S^{2}+r S\,\frac{\partial V}{\partial S}\!-\!r V=0
$$

This is the Black-Scholes partial derivative equation and any derivative  security  whose price depends only on the current value of   $S$    and on   $t.$  , and which is paid for  up-front must satisfy the Black-Scholes equation.  The most frequent type of partial  differential equation in financial problems is the parabolic equation. Equation (3.5) is  called backward parabolic since the equation is linear and the signs of these  particular derivatives are the same.
The price of particular derivative security is obtained by solving Equation (3.5)  subject to the appropriate auxiliary conditions (terminal payoff) for the  corresponding derivative security. The solution of the Black-Scholes equation with  different auxiliary conditions can then provide valuation formulas for different types  of derivative securities.

The term  $d X$  disappear from the PDE, which means there is no uncertainty. While the  stock price evolves in an uncertain manner, when we value derivatives with respect  to stock price, this uncertainty no longer exist in the pricing formula for this  derivative.

The term  u  which is the expected rate of return on the stock also disappear from the  PDE. The expected return is affected by risk preference. The more risk averse the  investor, the smaller the expected return. Given that the expected return does not  appear in the pricing formula for derivatives, valuation of derivatives in this  framework is preference free. The solution to the differential equation is therefore the  same in a risk-free world as it is in the real world.  Hence, this type of valuation  method are often called, risk neutral valuation relationship (RNVR).

Application of RNV sets the expected growth rate of stock equal to risk free interest  rate, then discount expected payoff of option at risk free rate.

There are many solutions to (3.5) that correspond to different derivatives,   $f$  , with  underlying asset  $S$    . In other words, without further constraints, the PDE in (3.5) does  not have a unique solution.

The particular security being valued is determined by its boundary conditions of the  differential equation. In the case of a European call, the value at expiry   $c(S,T)\!=\!(S-E,\!0)$    serves as the final condition for the Black-Scholes PDE.

# 3.2  Lognormal property and stock price process

Black-Scholes (1973) assume that there are two fundamental assets: a bond with a  price   $B(.)$    and a stock with a price   $S(.)$  . The price of the bond and the stock are  assumed to grow as follows for any   $0\leq t\leq T$  :

$$
\begin{array}{l}{{\displaystyle{\cal B}(t)=\exp(r t),\qquad\mathrm{and}}}\\ {{\displaystyle{\cal S}(t)={\cal S}(0)\exp\Biggl\{\!\!\left(\mu-\frac{1}{2}\sigma^{2}\right)\!t+\sigma w(t)\Biggr\},}}\end{array}
$$

3 where  $r,\,u$  ,  and   $\sigma$    are constants, and   $w(t)$    is a standard Brownian motion .   The ratio of   $S(T)$    to  $S(t)$    can be written:
$$
{\begin{array}{l}{S(T)=S(0)\exp\!\left\{\!\!\left(\mu-{\frac{1}{2}}\sigma^{2}\right)\!{\bar{T}}+\sigma w(T)\right\}}\\ {S(t)=S(0)\exp\!\left\{\!\!\left(\mu-{\frac{1}{2}}\sigma^{2}\right)\!{\bar{t}}+\sigma w(t)\right\}}\end{array}}
$$

$$
=\exp\Biggl\{\!\left(\mu-{\frac{1}{2}}\sigma^{2}\right)\!(T-t)+\sigma\bigl(w(T)-w(t)\bigr)\Biggr\}
$$

Taking log of both sides of the above equation, we get

$$
\ln\!\left({\frac{S(T)}{S(t)}}\right)\!=\!\left(\mu-{\frac{1}{2}}\sigma^{2}\right)\!(T-t)+\sigma{\big(}w(T)-w(t){\big)}
$$

the increment   $w(T)\textrm{-}w(t)$    is distributed normal  $N(\theta,\,T{-}t)$  ,  so it follow that

$$
\!\ln\!\left({\frac{S(T)}{S(t)}}\right)\!\sim N\!\left(\!\left(\mu\!-\!{\frac{1}{2}}\sigma^{2}\right)\!(T-t),\sigma(T-t)\right)
$$

From equation (3.6) it can also be seen that

$$
\ln\!\left(S(T)\right)\!=\ln\!\left(S(t)\right)\!+\!\Biggl(\mu-\frac{1}{2}\sigma^{^2}\Biggr)\!(T-t)+\sigma\!\left(w(T)-w(t)\right)
$$

and, therefore, that

$$
\ln\!\left(S(T)\right)\sim N\!\left(\!\left(\mu-{\frac{1}{2}}\sigma^{2}\right)\!(T-t),\sigma(T-t)\right)
$$

from equation (3.6), the terminal stock price  $S(T)$   may be written as follows:

$$
S(T)=\exp\Biggl\{\!\!\left(\mu-{\frac{1}{2}}\sigma^{2}\right)\!(T-t)+\sigma\bigl(w(T)-w(t)\bigr)\Biggr\}
$$

$$
=\!\exp\!\left\{\!\!\left(\mu-{\frac{1}{2}}\sigma^{2}\right)\!\!(T-t)+\sigma W\!\right\}
$$

where   $W\equiv\big(w(T)-w(t)\big)$    is distributed as normal   $N(0,T-t)$    under the usual  probability measure.
As mentioned above the price of European option at time   $t$    can be found by  discounting the expected payoff of the call option (Where   $\mathrm{E}^{*}$    denotes expectation  taken under the risk-neutral probability measure). The expectation is taken  conditional on information at time  $t$    [that is, conditional on  $S(t)]$  :

$$
c(t)=e^{-r(T-t)}E^{*}\big[\mathrm{max}\big(S(T)-K_{*}\!0\big)\big|S(t)\big)\big]
$$

Now, substituting equation (3.8) into (3.9):

$$
c(t)=e^{-r(T-t)}\int_{w=-\infty}^{+\infty}\left(S(t)e^{\left(\mu-\frac{1}{2}\sigma^{2}\right)(T-t)+\sigma W}-K\right)^{+}f_{w}(w)d w.
$$

$f_{\scriptscriptstyle W}(w)$  is the probability density function (pdf) of   $w$  .  With    $W\sim N(0,T-t)$  ,   it  follows that the probability density function of   $W$    is given by

$$
f_{_W}(w)\!=\!\frac{1}{\sqrt{2\pi}\sqrt{T-t}}e^{-\frac{1}{2}\left(\frac{w}{\sqrt{T-t}}\right)^{2}}
$$

Substitute this for   $f_{\scriptscriptstyle W}(w)$  in equation (3.9a) to get the call option value:

$$
\begin{array}{c}{c(t)=e^{-r(T-t)}\displaystyle\int_{w=-\infty}^{+\infty}\!\!\left(S(t)e^{\left(\mu-\frac{1}{2}\sigma^{2}\right)(T-t)+\sigma W}-K\right)^{+}}\\ {\mathrm{x}\frac{1}{\sqrt{2\pi}\sqrt{T-t}}e^{-\frac{1}{2}\left(\frac{w}{\sqrt{T-t}}\right)^{2}}d w.}\end{array}
$$

To simplify, let   $w\!=\!\varepsilon\sqrt{T-t}$    so that   $d\varepsilon\!=\!\frac{d w}{\sqrt{T-t}}$    and the call option value becomes

$$
c(t)=e^{-r(T-t)}\int_{\varepsilon=-\infty}^{+\infty}\left(S(t)e^{\left(\mu-\frac{1}{2}\sigma^{2}\right)(T-t)+\sigma\varepsilon\sqrt{T-t}}-K\right)^{+}\frac{1}{\sqrt{2\pi}}e^{-\frac{1^{2}}{2}}d\varepsilon
$$

let  ε    be such that   $\left(S(t)e^{(r-\frac{1}{2}\sigma^{2})(T-t)+\sigma\varepsilon\sqrt{T-t}}-K\right)\!=\!0\,,\,\mathrm{then}$

$$
{\mathcal{E}}_{\scriptscriptstyle0}=\!\frac{1}{\sigma\sqrt{T-t}}\!\left\{\ln\!\left(\frac{K}{S(t)}\right)\!-\!\left(r-\!\frac{1}{2}\sigma^{2}\right)\!(T-t)\right\}
$$
4 The formula for   $c(t)$    simplifies slightly because the integrand  is identically zero  when   $\varepsilon<\varepsilon_{\!\scriptscriptstyle0}$

$$
c(t)=e^{-r(T-t)}\int_{\varepsilon=\varepsilon_{0}}^{+\infty}\left(S(t)e^{\left(\mu-\frac{1}{2}\sigma^{2}\right)(T-t)+\sigma\varepsilon\sqrt{T-t}}-K\right)\,\frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}\,\varepsilon^{2}}d\varepsilon
$$

We may split the integrand (and hence the integral ) into two components:

$$
c(t)=e^{-r(T-t)}\intop_{\varepsilon=\varepsilon_{0}}^{+\infty}\!\!\!\!\int S(t)e^{(r-\frac{1}{2}\sigma^{2})(T-t)+\sigma\varepsilon\sqrt{T-t}}\;\;\frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}\varepsilon^{2}}\;d\varepsilon
$$

$$
-\,K e^{-r(T-t)}\int_{\varepsilon=\varepsilon_{0}}^{+\infty}\frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}\ \varepsilon^{2}}d\varepsilon
$$

Collect terms and simplify:

$$
c(t)=S(t)\intop_{\varepsilon=\varepsilon_{0}}^{+\infty}\frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}\varepsilon^{2}(T-t)+\sigma\varepsilon\sqrt{T-t}\;\;-\frac{1}{2}\varepsilon^{2}}\;d\varepsilon
$$

$$
-\,K e^{-r(T-t)}\int_{\varepsilon=\varepsilon_{0}}^{+\infty}\frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}\,\varepsilon^{2}}d\varepsilon
$$

The exponent in the integrand of the first term is scaled perfect square satisfying

$$
-{\frac{1}{2}}\sigma^{2}(T-t)+\sigma\varepsilon\sqrt{T-t}-{\frac{1}{2}}\varepsilon^{2}=-{\frac{1}{2}}{\bigl(}\varepsilon-\sigma\sqrt{T-t}{\bigr)}^{2}=-{\frac{1}{2}}\varepsilon^{2},
$$

where   $\varepsilon^{'}\equiv\varepsilon-\sigma\sqrt{T-t}$    .  Now substitute this into the first integral to simply the  expression for  $c(t)$  :

$$
c(t)\!=\!S(t)\!\int\!\!\!\!\int\!\!\frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}\varepsilon^{2}}d\varepsilon^{'}\!-\!k e^{-r(T-t)}\!\int\displaylimits_{\varepsilon=\varepsilon_{0}}^{+\infty}\!\!\frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}\varepsilon^{2}}d\varepsilon
$$
The integrands are normal standard pdf's. Therefore, the integrals involve normal  standard normal cdf's. The option value   $c(t)$    may now be written in terms of the  cumulative standard normal function  $\Nu(.)$   as follows:

$$
c(t)=S(t)\big[1-N(\varepsilon_{\scriptscriptstyle0}-\sigma\sqrt{T-t})\big]-K e^{-r(T-t)}\big[1-N(\varepsilon_{\scriptscriptstyle0})\big].
$$

From  the  property  of  the  cumulative  standard  Normal  function:   $[1-N(z)]\!=\!N(-z)$    This may be used to simplify   $c(t)$  :

$$
c(t)\,{=}\,S(t)N(-\varepsilon_{_0}+\sigma\sqrt{T-t}\,)-K e^{-r(T-t)}N(-\varepsilon_{_0})
$$

By algebraic manipulations, one can show that if

$$
{\mathcal{E}}_{0}={\frac{1}{\sigma{\sqrt{T-t}}}}\left\{\ln\!\left({\frac{K}{S(t)}}\right)\!-\!\left(r-{\frac{1}{2}}\sigma^{2}\right)\!(T-t)\right\}\!,
$$

then

$$
-\,\mathcal{E}_{_0}=\frac{\ln\!\left(\frac{S(t)}{K}\right)\!+\!\left(r-\frac{1}{2}\sigma^{2}\right)\!(T-t)}{\sigma\sqrt{T-t}},
$$

and

$$
-\,\varepsilon_{0}+\sigma\sqrt{T-t}=\frac{\ln\!\left(\frac{S(t)}{K}\right)\!+\!\left(r+\frac{1}{2}\sigma^{2}\right)\!(T-t)}{\sigma\sqrt{T-t}},
$$

If we label the latter two terms and   ${\sf d}_{2}$    and   ${\bf d}_{1}$    respectively, you get the Black-Scholes  formula for the price of a standard European call on a non dividend-paying stock:

$$
=S(t)N(d_{1})-e^{-r(T-t)}K N(d_{2}),
$$

where

$$
d_{_1}\!=\!\frac{\ln\!\left(\cfrac{S(t)}{K}\right)\!+\!\left(r+\cfrac{1}{2}\sigma^{2}\right)\!(T-t)}{\sigma\sqrt{T-t}},
$$
The above call price formula can be interpreted using the language of probability.  First,   $N(d_{2})$   is seen as the probability of the call being in-the-money at expiry and  so   $K N(d_{2})$   can be interpreted as the risk neutral expectation of the payment made  by the holder of the call option at expiry on exercising the option. Second,   $S(t)e^{r(T-t)}N(d_{1})$  is the risk neutral expectation of the asset price at expiry  conditional on the call being in-the-money. Hence, the expectation of the call value  at expiry is

$$
=S(t)N(d_{1})-e^{-r(T-t)}K N(d_{2}),
$$

which is then discounted by the factor   $=e^{-r(T-t)}$   in the risk neutral world to give the  present value of the call.

# 4.1 Barrier Options

Options with the barrier feature, commonly called barrier options, are considered to  be one of the simplest types of path-dependent options. The unique feature is that the  payoff depends not only on the final price of the underlying asset but also on whether  or not the underlying asset price has reached (one-touch) some barrier level during  the life of the option. An  out-barrier  option (knock-out option) is one where the  option is nullified prior to expiration if the underlying asset price touches the barrier.  The option holder may be compensated by a rebate payment for the cancellation of  the option. An  in-barrier  option (knock-in) option is barrier option type which comes  into play if the asses price hits or crosses the predefined barrier level. When the  barrier is approached from below, the barrier option is called an  up-option;  otherwise  it is called  down-option . One can identify eight type of European barrier options,  such as down-in calls, up-in calls, down-out calls, up-out calls. And similar four  types of options for the European barrier put options.

All these options are called standard or vanilla barrier options. The attractiveness of  barrier options is that they are cheaper than their corresponding vanilla options, as  the sum of the premiums of a knock-in and its corresponding knock-out is always the  same as the premium of their corresponding vanilla option if there are no rebates.

# 4.2 Vanilla barrier options

Another name for barrier type options is also a trigger option. This is because the  payoff depends critically on whether a pre-specified barrier or a trigger is touched  during the life of the option. If the barrier is breached during this time, the holder is  entitled to receive a European option. Otherwise, the holder gets a rebate at the  maturity of the option. This kind of barrier is known as knock-in barrier option, or  simply knock-in. Given the underlying asset price, the barrier level can be placed  above of below it. If the barrier is below the underlying price, the knock-in option is  called a down knock-in option (DI - for down and in option). The payoff of a down  knock-in option (PDI) can be formally given as
$$
\begin{array}{r l}&{P D I=\operatorname*{max}\big\{\!\left[\omega S(t^{*})-\omega K,0\right]\!\mid S(t)>H}\\ &{\mathrm{and}\ S(T)\!\mid\!S(H,\mathrm{for\;some}\quad t<T\leq t^{*}\big\},}\end{array}
$$

or

$$
P D I=R m(\tau)\ \mathrm{if}\;S(t)>H\,\mathrm{and}\;S(T)>H,\,\mathrm{for\all}\;t<T\leq t^{*}\,,
$$

Where   $t,a n d,t^{*}$    are the current and expiration time of the option respectively;  $H$    is  the knock-in boundary of the option or the constant barrier level.  $K$   is the strike price  of the option;    $\omega$  is a binary operator (1 for a call and   $^{-1}$   for a put).    $R m(\tau)$    is the  rebate of the barrier option paid at maturity if the barrier is not touched.

Below we also so define the payoff for remaining vanilla barrier types such as up-anin (PUI), down-and-out (PDO). For up-and-out (PUO) payoff see Zhang (1998).

The payoff of an up-and-in barrier option (PUI) is given formally as;

$$
\begin{array}{r l}&{P U I=\operatorname*{max}\big\{\!\big[\omega S(t^{*})-\omega K,\!0\big]\!\big|\,S(t)<H}\\ &{}\\ &{\mathrm{and}\ S(T)\geq H,\,\mathrm{for\,some}\quad t<T\leq t^{*}\big\},}\end{array}
$$

or

The Payoff of a down and knock out barrier option or simply down-and-out is given;

$$
\begin{array}{r l}&{P D O=\operatorname*{max}\big\{\!\left[\omega S(t^{*})-\omega K,0\right]\!\mid S(t)>H}\\ &{}\\ &{\mathrm{and}\ S(T)>H,\mathrm{\,for\,some\,}\quad t<T\leq t^{*}\big\},}\end{array}
$$

or

${\tt R}({\tt T})$   is in this case also the rebate function which is time dependant. R(T) is most  often an increasing function of time starting from zero, or   $R^{\prime}\!(T)\!>\theta$    and  $R(\!O\!){=}0$  .  The  rebate defined in (4.2c) is called non-deferred rebate, implying that the rebate is paid  as soon as the barrier is reached. The rebate can also be deferred, that is, the rebate  payment can be postponed until maturity.
# 4.2.1 Path Independence and Path Dependence

A security is path-independent if its value at a given point in time depends on the socalled state-of-the-world at the time, and now on how the world evolved to that state.  For example, the premium of European option depends on the price and the return  volatility of the underlying at a given point in time, but is independent of the actual  price history that transpired prior to that time. Barrier options are dependant on price  history for determining if a barrier has been hit or not. For an out-option, this type of  dependency is theoretically no different than the path-dependency inherent in the  early exercise of an American option. A non-linear barrier option exist for an  American option, defined at time  $t$    by the critical price  $S_{t}$  at which the investor should    exercise. In practise this barrier is subjective, to the extent that the investor needs to  specify volatility before the American barrier can be identified. Also, the rational  investor would exercise, but is not required to do so, whereas the breaching of the  barrier triggers a contractual provision in a knock-out or knock-in option.

Financial engineers are concerned with yet another type of path dependence -  whether and how backward recursion can be used for pricing. Backward recursion  refers to the methods such as Cox-Ross-Rubinstein. This is of interest because  backward recursion is flexible and efficient when compared to Monte Carlo  simulations. In order to use backward recursion one requires the security (contingent  claim) being priced be path-independent (in a weak sense). Fortunately, barrier  options are bath-independent in this sense

# 4.3 Reflecting barrier

A Brownian motion with reflecting barrier is also called Brownian motion reflected  about some particular point. A Brownian motion  $X(t)$    reflected about the line  $x=b$    is  given as follows.

$$
\begin{array}{l}{{\tilde{X}(t)=X(t)\mathrm{~for~}t<T_{b}}}\\ {{=2b-X(t)\mathrm{~for~}t>T_{b}}}\end{array}
$$

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/d584fb2d9a995e0f2b94aa7f74fa74d66cebeec668eac7baf3adfb78b7098aab.jpg)
Simulated asset  price

Figure 1.1   Simulated asset prices with a fixed barrier level of 115.
The well-known result abut the reflecting barrier is the reflection principle which  states that for every sample path with   $X(T)>b$    there are two sample paths   $X(T)$

and   $\tilde{X}(T)$    with the same probability of occurrence. Because of the symmetry with  respect to  $b$    of a Brownian motion   $X(t)$    starting at   $b$  ,  the "probability" of doing this  is the same as the "probability" of travelling from   $b$    to the point  $2b-X(t)$  .  The reason  for this is that, for every bath which crosses level   $b$    and is found at time   $t$    at a point

below   $b$  ,  there is a shadow path   $\stackrel{\sim}{X}(t)$    obtained from the reflection about the level  $b$    which exceeds this level at time t, and these two paths have the same probability. The  actual probability for the occurrence of any particular path is zero. With the  argument stated above, we can write the equation of the reflection principle as  follows:

$$
P\big[T_{b}<t,X(t)<b\big]\!=\!P\big[T_{b}<t,X(t)\!>\!b\big]\!=\!P\big[X(t)\!>\!b\big],
$$

Where   $T_{b}$    stands for the time when the reflecting barrier  $\mathfrak{b}$   is first touched and   $P$    is  the probability.  The reflection principle can be used to find the first passage time.  The solution of the density functions for the Brownian motion with a reflecting  5 barrier can be found in several text books in financial mathematics .

# 4.4.1 Unrestricted distribution and absorbing barrier

Let   $g$  stand for the annual continues dividend yield on the underlying asset. The  stochastic process which governs the underlying asset price movement given in (1.1)  becomes

$$
d S=(\mu-g)S d t+\sigma S d z(t),
$$

where all the parameters are the same as equation (1.1) except for incorporating the  continues dividend payout. The solution to the above SDE is given below

$$
S(\tau)\!=\!S\exp\!\big[\nu\tau+\sigma w(\tau)\big],
$$

where   $\tau\!=\!t^{*}-t,\ \left[t,t^{*}\right]$  stand for current time and expiration time of the option,  respectively,    $\nu\,{=}\,r-g-\sigma^{2}\,/\,2$  ,   and   $w(\tau)$  is standard Gauss-Weiner process ( note  here that we have changed the notation slightly).

We know that   $\boldsymbol{X}_{\u{\tau}}=\ln\bigl[S(\tau)/S)\bigr]$    is the log-return of the underlying asset, then the  density function of   $X_{\tau}$   is normally distributed with mean   $\nu\tau$  v and variance   $\sigma^{2}\tau$  .   its  pdf is then given by:
$$
f(x)\!=\!\frac{1}{\sigma\sqrt{2\pi\tau}}\mathrm{exp}\Bigg[\!-\frac{(x-\nu\tau)^{2}}{2\sigma^{2}\tau}\Bigg]\!.
$$

Below we provide the result from Cox and Miller (1965) for the density function of a  Brownian process with an absorbing barrier. An absorbing barrier is a barrier which  upon touching, all the particles vanish.

$$
\begin{array}{l}{{\displaystyle{f(x)\!=\!\frac{1}{\sigma\sqrt{2\pi\tau}}\exp\!\left[-\frac{\left(x-\nu\tau\right)^{2}}{2\sigma^{2}\tau}\right]}.}}\\ {{\displaystyle{\qquad-\,e^{2a\nu/\sigma^{2}}\exp\!\left[-\frac{\left(x-2a-\nu\tau\right)^{2}}{2\sigma^{2}\tau}\right]\,\,\,\mathrm{for}\,x<a,}}}\end{array}
$$
 x < a,

# 4.4.2 Restricted Distributions

From the specification of the payoff of a brier option, we know that in order to price  it, we certainly need another density function conditioned on whether the barrier is  reached during the life of the option. Define:

$$
{M_{t}^{t^{*}}=\operatorname*{max}\left\{\left.S(s)\,\right|\,s\in\left[t,t^{*}\right]\right\}},
$$

and

$$
m_{t}^{t^{*}}=\operatorname*{min}\big\{S(s)\,|\,s\in\big[t,t^{*}\big]\big\},
$$

where   $x\in X$    stands for that  $x$    belongs to  $X,$  ;   $\left[t,t^{*}\right]$    stands for the set of real numbers  starting from   $t$    and ending at    $t^{*}$    .  max and min represent the functions giving the  maximum and the minimum of a set of numbers, respectively.

The two variables given in (4.3a) and (4.3b) are the maximum and minimum of all  underlying asset prices  within the life of the option. We can express these in terms  of log-returns:

$$
\begin{array}{r}{\boldsymbol{Y}_{\u{\tau}}=\ln({\boldsymbol{M}_{t}^{\mathrm{\scriptsize~t}^{*}}}\,/\,{\boldsymbol{S}})\quad\mathrm{~and~}\quad\ \boldsymbol{y}_{\u{\tau}}=\ln({\boldsymbol{M}_{t}^{\mathrm{\scriptsize~t}^{*}}}\,/\,{\boldsymbol{S}})}\end{array}
$$

let   $T_{a}$    stand for the time the underlying asset price first reaches an up barrier U. The  following always hold:
$$
P_{r}(T_{a}>\tau)\!=\!P_{r}(M_{t}^{t^{*}}<U)\!=\!P_{r}(Y_{\tau}<a),
$$

and

$$
P_{r}\left(T_{a}\leq\tau\right)=P_{r}\left(M_{\phantom{t}_{t}}^{t^{*}}\geq U\right)=P_{r}\left(Y_{\tau}\geq a\right)\!,
$$

Equation (4.4a) shows that the barrier is never hit within the life of the option since  the first time barrier is breached is after the expiration time of the option. This is  equivalent to the fact that the maximum value of the underlying asset price within the  life of the option is always below the barrier in a probabilistic sense. Equation (4.4b)  is the complement of (4.4a), and implies that the barrier is touched within the life of  the option since the first time the barrier is hit is during the life of the option.

The joint-cumulative distribution between the log-return of the underlying asset and  the transferred maximum given in (4.3c) is given as follows [see Harrison (1985)] for   $x:y\ y\geq0$  :

$$
F(X_{\tau}\leq x,Y_{\tau}\leq y)=N\!\left({\frac{x-\nu t}{\sigma{\sqrt{\tau}}}}\right)-e^{2y\nu/\sigma^{2}}N\!\left({\frac{x-2y-\nu t}{\sigma{\sqrt{\tau}}}}\right)\!,
$$

where   $\Nu(.)$   is the cumulative function of a standard normal distribution. The jointcumulative function in (4.5) is equivalent to the following

$$
F(X_{\tau}\leq x,Y_{\tau}<y)=N\!\left(\frac{x-\nu t}{\sigma\sqrt{\tau}}\right)-e^{2y\nu/\sigma^{2}}N\!\left(\frac{x-2y-\nu t}{\sigma\sqrt{\tau}}\right)\!,
$$

Equation (4.4a) and (4.5a) together imply that (4.5a) is the cumulative function of the  log-return of the underlying asset conditional on the fact that the barrier is never  touched within the life of the option. Differentiating (4.5a) with respect to  $x$    yield the  density function of the log-return of the underlying asset conditional on the fact that  the barrier U is never touched within the life of the option.:

$$
\phi(x\,|\,Y_{\tau}<a)=f(x)-e^{2a\nu\tau/\sigma^{2}}f(x-2a),
$$

or

$$
\phi(x\,|\,Y_{\tau}<a)=f(x)-\left(\frac{U}{S}\right)^{2\nu/\sigma^{2}}f(x-2a)\,\,\mathrm{for}\,\,x<a,
$$

and

$$
\phi(x\,|\,Y_{\tau}<a)=0\,\,\mathrm{for}\,\,x{\ge}\,a,
$$

where  $f(x)$    is the unrestricted density function of the log-return of the underlying  asset given in (4.2.1). The restricted density function given in (4.5b) or (4.5c) is  exactly the same as the solution to the Brownian motion with an absorbing barrier  $a$     $>\theta$    given in (4.2.1a).
The complement of being always below the barrier is not always being above or at  the barrier, because it is possible that the barrier is reached and the price ends up  below. The density function that the barrier is touched can be obtained from the  following identity.

$$
\phi(x\,|\,Y_{\tau}\geq a)+\phi(x\,|\,Y_{\tau}<a)=f(x)
$$

This equation can be interpreted as the summation of the probability when the  barrier is touched and the probability when the barrier is never touched within the  live of the option, and this is the same as the unrestricted density given in (4.2.1a).

# 4.5.1 Distribution of the first passage time

The first passage time to a particular point on the path of the underlying asset price is  the first time that this particular point is first reached. The joint probability that             $x=y=a>0$     for an up-barrier cab be obtained using (4.4a) and (4.5)

$$
\begin{array}{l}{{P\left(X_{_t}\leq a,Y_{_t}\leq a\right)=P\left(X_{_t}\leq a,T_{_a}>\tau\right)}}\\ {{\mathrm{~}}}\\ {{{\mathrm{~}}}=N\mathrm{\left(}\displaystyle\frac{a-\nu t}{\sigma\sqrt{\tau}}\right)\!-e^{2a\nu/\sigma^{2}}N\mathrm{\left(}\displaystyle\frac{-a-\nu t}{\sigma\sqrt{\tau}}\right)\!,}}\end{array}
$$

if the drift term   $\nu\,{=}\,r-g-\sigma^{2}\,/\,2\,{\geq}\,0$  , the density function of the first passage time  from zero to the transferred barrier point   $a=\ln(U/S)>0$    can be obtained by  differentiating (4.6) with respect to the time to maturity.

$$
\begin{array}{r l r}&{}&{h(T\,|\,a>0)\!=\!\!\left[-\displaystyle\frac{\partial}{\partial\tau}F(X_{\tau}\!\leq\!a,Y_{\tau}\!\leq\!a)\right]_{\tau=T}}\\ &{}&\\ &{}&{\qquad\displaystyle=\!\frac{a}{\sigma\sqrt{2\pi T^{3}}}\mathrm{exp}\!\left[-\displaystyle\frac{\left(a-\nu T\right)^{2}}{2\sigma^{2}T}\right]}\end{array}
$$

equation (4.6a) is the distribution of the first passage time.

# 5.1 Pricing standard barrier options

One of the oldest barrier option types such as down-and-out call options were first  made available in the U.S. market from 1967. The corresponding valuation formula  for these options was driven by Merton (1973). A decade later Bergman (1983)  developed a framework for pricing path-dependant claims such as barrier options,  and Cox and Rubinstein (1985) used their down-and-out formula to price fixed  income securities with embedded characters. Rubinstein and Reiner (1991) also  contributed detailed results for all barrier option types with the assumption that the  underlying asset price follows lognormal process.
The expected payoffs of in and out barrier options can be calculated in the same way  as in vanilla options with the only exception that the restricted density function  shown above is used. Using a risk-neutral evaluation relationship, one can obtain  barrier option prices by discounting the expected payoffs at the risk-free rate of  return. The barrier option is however also affected by the relative magnitude of the  strike price and the barrier level. For a down-and-in call with a strike price  $K$    greater  than the barrier level  $H$    and without any rebate, the value of the call can be found by  integrating the payoff of a vanilla call option with the restricted density function for  all possible underlying asset price starting from the strike price  $K$    to infinity.

If however the strike price is below or lower the barrier, the payoff of the down-andin call barrier option includes two parts: the integration of the payoff function of a  vanilla call option with the restricted density functions given in (5.1a) for all possible  underlying asset prices starting from the barrier  $H=L$    to infinity, and the integration  of the same payoff function with the density function given in (5.1b) for all  $S$    starting  from the strike price  $K$    to the barrier  $H=L$  .

$$
\phi(x\,|\,Y_{\tau}\leq b)=e^{b\nu/\sigma^{2}}f(x-2b)=\!\left({\frac{L}{S}}\right)^{2\nu/\sigma^{2}}f(x-2a)\quad{\mathrm{for}}\;x>b
$$

and

$$
\phi(x\,|\,Y_{\tau}\geq b)=f(x){\mathrm{~for~}}x\leq b,
$$

where     $b\,=\,l n(L/S)$    and   $L$    stands for a down-barrier   $L\,<\,S.$  .  (5.1a) is the restricted  density function of the underlying asset log-return under the condition that the downbarrier is touched within the options lifetime.

# 5.2 Down-and-in barrier call option

The payoff of a down-an-in barrier call option can be divided in two parts; one part  including the payoff of the corresponding vanilla option if the barrier is reached any  time within the life of the option, and the rebate if the barrier is never reached.  Within the life of the option. Lets first consider the case where the strike is greater  than the barrier level (   $K>H$  ). The value of down-and-in call option (VDIC)  without any rebate if the barrier is reached is readily obtained by discounting it is  expected payoff given in equation (4.2a) at the risk-free rate of return:

$$
V D I C=\left(\frac{H}{S}\right)^{2\nu/\sigma^{2}}\left\{\left(\frac{H^{2}}{S}\right)\;e^{-g\tau}N\left[d_{\mathrm{\sigma}b s}\left(\frac{H^{2}}{S},K\right)\right]-K e^{-r\tau}N\left[d_{b s}\left(\frac{H^{2}}{S},K\right)\right]\right\},
$$

where
$$
d_{_{b s}}(S,K)\!=\!\frac{\ln\!(S\,/\,K)+(r-g-\sigma^{2}\,/\,2)\tau}{\sigma\sqrt{\tau}}\!=\!\frac{\ln\!(S\,/\,K)+\nu\tau}{\sigma\sqrt{\tau}},
$$

$$
d_{\scriptscriptstyle1b s}\left(S,K\right)=d_{\scriptscriptstyle b s}\left(S,K\right)+\sigma\sqrt\tau
$$

$d_{\it b s},d_{\it1b s}$      are an extended version Black-Scholes parameters we have already seen  above. We can also extend the Black-Scholes solution for the call price and use this  formula to give an alternative compact formula for the down-and-in barrier call  option;

$$
C_{_{b s}}(S,K)=\omega S e^{-g\tau}N[\omega d_{_{1b s}}(S,K)]-\omega K e^{-r\tau}N[\omega d_{_{b s}}(S,K)],
$$

The value of down-and-in call barrier option can then also be written in form

$$
V D I C=\Biggr(\frac{H}{S}\Biggr)^{2\nu/\sigma^{2}}C_{b s}\Biggl(\frac{H^{2}}{S},K\Biggr),
$$

The formula (5.2) gives the value of a down-and-in call option without any rebate  when the strike price is greater than the barrier. In the case when the strike is lower  than the barrier, the whole integration ranges must then be divided into sub-ranges.  For example, the integration range   $(K\;,\;\infty\;)$    into   $(K,\;H)$    and   $(H,\ \infty\ )$   because the  corresponding density functions are different into these sub-ranges.  For the range      $(\mathrm{H},\infty)$    we can obtain the value of the option in this up portion (VDNUP)

$$
\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\
$$

$$
\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\
$$

Where   $C_{b s}$   is again the extended Black-Scholes formula given above. Since the range  (K, H) is equivalent to the difference of the two ranges   $(-\infty,\mathrm{H})$   and   $(-\infty,\mathrm{K})$  , we can  obtain the value of the down-and-in call for the range (K, H)

$$
V D N I C=P_{_{b s}}(S,K)-P_{_{B S}}(S,H)+(H-K)e^{-r\tau}N\bigl[-\,d_{_{b s}}(S,H)\bigr],
$$

where
$P_{b s}(S,\!K)$    is the Black-Scholes formula for vanilla European put option. The value  of the down-and-in option without any rebate is therefore the sum of the values of the  options given in (5.3) and (5.4). From the above analysis, the pricing formula of a  down-and-in option depends on whether  $\mathrm{K}>\mathrm{H}$   or  $\mathrm{K}<\mathrm{H}$  . In order to obtain a general  formula to cover both situations, one can use an indicator   $B_{H>K}$   which equals one  when   $\mathrm{H}>\mathrm{K}$  , and zero if otherwise. Given the above indicator, we can express the  price of down-and-in call option (DINC) without rebate:

$$
D I N C=\Biggr(\frac{H}{S}\Biggr)^{2\nu\,/\,\sigma^{2}}\Biggl(C_{b s}\Biggl[\frac{H^{2}}{S},\operatorname*{max}(H,K)\Biggr]
$$

$$
\begin{array}{l}{{\displaystyle+\left[\operatorname*{max}(H,K)-K\right]e^{-r\tau}N\Bigg\{d_{_{b s}}\Bigg[\frac{H^{2}}{S},\operatorname*{max}(H,K)\Bigg]\Bigg\}\Bigg)}}\\ {{\displaystyle+\left\{P_{_{b s}}(S,K)-P_{_{b s}}(S,H)+(H-S)e^{-r\tau}N\big[-d_{_{b s}}(S,H)\big]\right\}\!\!B_{_{H>K}},}}\end{array}
$$

Where max (H, K) is the function which gives the larger of the two numbers  $\mathrm{H}$   and   $\mathrm{K}$  , and other parameters are the same as in (5.3) and (5.4). When  $\mathrm{K}>\mathrm{H}$  , the pricing  formula given is (3.6) becomes the same as (5.2) because max   $(\mathrm{H},\;\mathrm{K})=\mathrm{K}$  , and       $B_{H>K}\,=0$  . We can also check when   $\mathrm{K}<\mathrm{H}$  , max   $(\mathrm{H},\,\mathrm{K})=\mathrm{H}$  ,   $B_{H>K}\!=1$  , the pricing  formula (3.6) is the sun of the two pricing formulas given in (5.3) and (5.4) and the  sum represents the value of the down-and-in call option when there is no rebate.

We now continue to price down-and-call option by using numerical example and  with the assumption that the down barrier is touched. This implies that the rebate is  zero.

To find the find the price of down-and-in barrier call option, consider the following  parameter;  strike price   $\mathrm{K}=£98$  , spot price  $=£100$  , barrier level of  $\mathrm{H}=£95$  , interest  rate   $r=8\%$  , the yield of the underlying asset  $g=3\%$   and volatility of the underlying  asset  $=20\%$

Substituting   $\mathrm{S}=£100$  ,   $\mathrm{K}=£98$  ,  $\mathrm{H}=£95$  ,   $w=0.20$  ,   $r=0.08$  ,  $g=0.03$  ,  and  $t=0.5$    into (5.6) yields

$$
\begin{array}{r l}&{\nu=r-g-\sigma^{2}\⁄2=0.8-0.03-(0.20^{2}⁄2)=0.03,}\\ &{(H^{2}⁄S)=(95^{2}⁄100)=90.25,}\\ &{\operatorname*{max}(H,K)=\operatorname*{max}(95,\!98)=98,}\end{array}
$$
$$
d_{_{b s}}\!\left(\frac{H^{2}}{S},\!K\right)\!=\!\frac{\ln\!\left[\left(\!H^{2}\mid2\right)\!/\,K\right]\!+\nu\tau}{\sigma\sqrt{\tau}}\!=\!-0.4765,
$$

$$
d_{_{1b s}}\Biggl(\frac{H^{2}}{S},K\Biggr)=d_{_{b s}}\Biggl(\frac{H^{2}}{S},K\Biggr)+\sigma\sqrt{\tau}=-0.3351
$$

Since   $\mathrm{K}=£98>£95=\mathrm{H}$  , the call option price  $B_{H>K}{=}0$  .  We can then find the downand-in call price from (5.6) as follows:

$$
D I N C(K=98)\!=\!\!\left(\frac{H}{S}\right)^{2\nu\tau/\sigma^{2}}C_{b s}\!\left(\frac{H^{2}}{S},K\right)
$$

$$
\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\
$$

$$
0.95^{2\,x0.03\,/\,0.20^{2}}\bigl[90.25e^{-0.03x0.5}N(-0.3351)-98e^{-0.08x0.5}N(-0.4765)\bigr]\!=\!£2.731
$$

when the strike price   $\mathrm{K}=£92$  , max (H, K) - max   $(95,\,92)=£\,95$  ,   $B_{H>K}{=}I$  ,  and all  the terms in (5.6) and nonzero.

Substituting  $\mathrm{S}=£100,\,\mathrm{K}=£92,\,B_{H>K}=\,I,\,\mathrm{sigma}=0.20,\,r=0.08,\,g=0.03$   and   $t=$   $\it0.50$    into (5.6) yields:

$$
d_{_{b s}}\biggl[\frac{H^{2}}{S}\mathrm{max}(H,K)\biggr]\!=\!\frac{\ln\bigl[\bigl(H^{2}\mid S\bigr)/\,H\bigr]\!+\nu\tau}{\sigma\sqrt{\tau}}\!=\!-0.2566,
$$

$$
d_{_{1b s}}\Biggl[{\frac{H^{2}}{S}}\mathrm{max}(H,K)\Biggr]\!=\!d_{_{b s}}\Biggl({\frac{H^{2}}{S}},\!K\Biggr)\!+\sigma\sqrt{\tau}=\!-0.1152,
$$

$$
\begin{array}{r l}&{P_{_{b s}}(S,K)\!=\!-S\!\left[e^{-g\tau}N\!\left[-\,d_{_{1b s}}(S,K)\right]\!+\!k e^{-\tau}N\!\left[-\,d_{_{b s}}(S,K)\right]\!\right]\!\!=\!1.5801,}\\ &{P_{_{b s}}(S,H)\!=\!-S e^{-g\tau}N\!\left[-\,d_{_{1b s}}(S,H)\right]\!+\!H e^{-\tau}N\!\left[-\,d_{_{b s}}(S,H)\right]\!\!=\!2.4896}\end{array}
$$
$$
C_{b s}\!\left(\frac{H^{2}}{S},\operatorname*{max}(H,K)\right)\!=\!\!\left(\frac{95^{2}}{100}\right)\!e^{o.03x0.5}N\!\!\left[d_{1b s}\!\left(\frac{95^{2}}{100},\!95\right)\right]
$$

$$
-\,95e^{-0.08x0.5}N\Biggl[d_{_{b s}}\Biggl({\frac{95^{2}}{100}},95\Biggr)\Biggr]\,=3.9816
$$

Thus the value of the down-and-in call option is

$$
\begin{array}{c}{{D I N C=\left(\displaystyle\frac{95}{100}\right)^{2x0.03/0.2^{2}}\left[3.9816+(95-92)e^{-0.08x0.5}N(-0.2566)\right]}}\\ {{+\left[1.5801-2.4896+(95-92)e^{-0.08x0.05}N(-0.4689)\right]=£4.863}}\end{array}
$$

the price of the down-and-in barrier call option can also be incorporated in the case  when the barrier is never touched and the option pays some rebate.  (the present  value of this rebate is given above). For compact solutions for all remaining types of  barrier options can be found under Haug (1998).

The value of the rebate at the option maturity can be obtained by integrating the  restricted density function below from which the down barrier  $H=L$    to infinity.

$$
\phi(x\,|\,Y_{\tau}>b)=f(x)-\left(\frac{L}{S}\right)^{2\nu/\sigma^{2}}f(x-2b)\qquad\mathrm{for}\;x>b,
$$

$$
=R m(\tau)\Biggl\{N\bigl[d_{_{b s}}(S,H)\bigr]-\left(\frac{H}{S}\right)^{2\nu\tau/\sigma^{2}}N\bigl[d_{_{b s}}(H,S)\bigr]\Biggr\},
$$

The present value of the rebate is obtained by discounting (5.7) at the risk free rate  $r$  :

$$
R B D I=e^{-r\tau}R m(\tau)\Biggl\{N\bigl[d_{_{b s}}(S,H)\bigr]-\left(\frac{H}{S}\right)^{2\nu\tau/\sigma^{2}}N\bigl[d_{_{b s}}(H,S)\bigr]\Biggr\},
$$

RBDI is the present value of the rebate for down-and-in call option.
The price of down-and-in call option (PDIC) can now be expressed using (5.6) and  (5.8):

#  $P D I C=D I N C\quad+\quad R B D I$

Where RBDI and DINC are given in equations (5.6) and (5.8) respectively.

To find the present value of the rebate when the rebate is paid £1.5 at maturity if the  barrier is not touched within the live of the call option from the numerical example  above, substituting

$\mathrm{Rm}(0.5)=1.5$  ,   $\mathrm{S}=£100$  ,  $\mathrm{H}=£95$  , sigma  $=0.20$  ,   $\mathrm{r}=0.08$  ,  $\mathbf{g}=0.03$  , and  $\mathbf{t}=0.50$    Into equation (5.8) yields

$$
d_{_{b s}}\left(H,S\right)\!=\!\frac{\ln(S\,/\,H)+\nu\tau}{\sigma\sqrt{\tau}}\!=\!\frac{\ln(100\,/\,95)+0.03x0.5}{0.20\sqrt{0.50}}\!=\!0.4688,
$$

$$
d_{_{b s}}(H,S)\!=\!\frac{\ln(H\,/\,S)+\nu\tau}{\sigma\sqrt{\tau}}\!=\!\frac{\ln(95\,/\,100)+0.03x0.5}{0.20\sqrt{0.50}}\!=\!-0.2566,
$$

$$
R B D I=1.5e^{-0.08x0.05}\left\{N\big[0.4688\big]-\left(\frac{95}{100}\right)^{2x0.03/0.2^{2}}N\big[-0.2566\big]\right\}=£0.449
$$

we can now find the price of the down-and-in call option when the rebate is paid £1.5  at maturity if the barrier is not touched within the live of the option

The down-and-in call option price with strike price  $\mathrm{K}{=}\ 92$

$$
=\mathrm{DINC}(\mathrm{K}=92)+\mathrm{RBDI}\ =\ 4.862\ \ +\ 0.449\ \ =£5.312
$$

An important issue of pricing barrier options is whether the barrier crossing is  monitored in continues time. Most models assume continues monitoring of the  barrier. In other words, in the models a knock-in or knock-out occurs if the barrier is  reached at any instance before the maturity of the contract, mainly because this leads  to analytical solutions;  see for example Merton (1973), Heynen & Kat  (1994a,1994b) and kunitomo & Ikeda (1992) for various formulae for continuously  monitored barrier options under the classical Brownian motion framework; see Kou  & Wang (2001) for continuously monitored barrier options under a jump diffusion  framework.

However in practice most, if not all, barrier options traded in markets are discretely  monitored. In other words, they specify fixed times for monitoring of the barrier  (typically daily closings).
Besides practical implementation issues, there are some legal and financial reasons  why discretely monitored barrier options are preferred to continuously monitored  barrier options.  For example, some discussions in trader's literature ("Derivatives  Week", may   $29^{\mathrm{th}}$  , 1995) voice concern that, when the monitoring is continuous,  extraneous barrier breach may occur in less liquid markets while the major western  markets are closed, and may lead to certain arbitrage opportunities.

Although discretely monitored barrier options are popular and important, pricing  them is not as easy as that of their continuous counterparts for three reasons. (1)  There are essentially no closed solutions, except using   $m$  - dimensional normal  distribution function   $\mathit{\check{m}}$    is the number of monitoring points), which can hardly be  computed easily if, for example   $m>5$  ; see Reiner (2000). (2) Direct Monte Carlo  simulation or standard binomial trees may be difficult, and can take hours or even  days to produce accurate results; see Broadie, Glasserman and Kou (1999). (3)  Although the Central Limit Theorem asserts that, as  $m\to\infty$  , the difference between  continuously and discretely monitored barrier options should be small, it is well  known in the traders literature that numerically the difference can be surprisingly  large, even for large  m .

To give a feel for the accuracy of these models, see Table 1.1. This is reproduced  with permission from Brodie, Glasserman and Kou (1997). The numerical results  shown in Table 1.1 suggest that, even for daily monitored discrete barrier options,  there can still be big differences between the discrete prices and the continuous  prices.

# Table 1.1

Up-and-out Call option price results, with   $m=50$   (daily monitoring) and following  parameters:

$\begin{array}{l}{\mathrm{S}(0)=110}\\ {\mathrm{K}=100}\end{array}$  S(0) = 110

  $\upsigma=0.30$   per year

  $\mathbf{r}=0.1$  , and

  $\mathrm{T}=0.2$   year, which represents roughly 50 trading days.

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/992b65514f92c573f6597136b196daf1386a6162fc0bbb87373e6079d4d1fc32.jpg)
# References

Broadie, M., Glasserman, P. and Kou, S G. (1997), “A continuous correction for  discrete barrier options”,  Math. Finance   7 , pp. 325-349

Broadie, M., Glasserman, P. and Kou, S G. (1999), “Connecting discrete and  continuous path-dependant options”,  Finan. Stochastic s  3, pp. 55-82.   Espen G. Haug., (1997),  The complete guide to Option pricing , McGraw-Hill

Heynen, R. C. and Kat, H. M. (1994b), “Partial barrier options”,  Journal of Financial  Engineering

James, P.,  (2003),  Option Theory , John Wiley & Sons Ltd

M. S. Joshi,. (2003),  The concepts and practice of mathematical finance , Cambridge  University Press

Kunitomo, N. and Ikeda, M. (1992), “Pricing options with curved boundaries”,   Math. Finance

Merton, R. C. (1973), “Theory of rational option pricing”,  Bell J. Economic  Management and Science  4, pp. 41-183.

Merton, R. C., (1974) “On the pricing of corporate debt: the risk structure of interest  rates”,  Journal of Finance , 29 pp. 449-470

Reiner, E. (2000).  Convolution Methods for Path-Dependant Options , Preprint, UBS  Warburg Dillon Read

Ritchken, P., (1995), “On pricing barrier options”,  Journal of Derivatives  3, pp. 9-28

Rubinstien, M., Reiner, E., (1991), “Breaking down the barrier”,  Risk  4, pp. 28-35

Wilmott, P., Howison, Dewynne, (1993),  The Mathematics of Financial Derivatives ,  Cambridge University Press
