---
tags:
  - black_model
  - caps_and_floors
  - interest_rate_derivatives
  - option_pricing
  - risk_neutral
aliases:
  - Black-Scholes Approach
  - Caps and Floors Pricing
  - Interest Rate Derivatives
key_concepts:
  - Black-Scholes model
  - Caps and floors
  - Floating rate borrowers
  - Interest rate derivatives
  - Option payoff structure
  - Over-the-counter market
  - Risk neutral representation
---

# Interest Rate Derivatives-An Introduction to the  Pricing of Caps and Floors
# Abstract

This article introduces the basic structure and engineering of interest rate derivative  instruments, which are products whose payoffs depend in some way on the level of  interest rates. These financial instruments include caps, floors, swaptions and options  on coupon-paying bonds. The most common way to price interest rate derivatives  such as caps and floors, is to adopt the Black-Scholes approach and to implement the  Black (1976) pricing model. Following an introduction to the structure of interest rate  derivatives, we also present the underlying risk neutral representation of the Black  model in order to derive the existing closed form solution. In fact, the model is very  intuitive and easy to implement for a single cap/floor. When pricing a portfolio of  caplets/floorlets however, with multiple expiry dates, one may need to use  sophisticated analytics written in higher programming languages for computational  speed and efficiency.

# Interest-rate caps and floors

Interest rate options are widely used to either speculate on the future course of interest  rates or to hedge the interest payments or receipts on an underlying position. The  advantage of these instruments over other types of derivatives such as swaps and  interest rate futures is that interest options allow an investor to benefit from changes  in interest rates while also limiting any downside losses. Hence, like all options they  provide insurance.

The over-the-counter market trades options on a number of interest rates relating to  short-term financial instruments, such as bank deposits, certificates of deposit,  commercial paper, and T-bills. The most liquid options traded of all these are caps,  floors, and collars. Caps are interest rate option structures with a payout if interest  rates rise (this may also depend on the option style or exercise). Consequently, they  are used by floating rate borrowers or issuers to ensure against a rise in interest rates.  Floors, on the hand, have a payoff for the user if interest rates fall and, consequently,  are used by depositors/investors to insure against interest rates falling. A collar is a  combination of the two while a zero cost collar can be constructed by taking opposite  position of the two options types, such that the strike prices are chosen so that the net  premium for the user is zero.

Consider the following example where a corporation has issued a floating-rate note or  a loan, paying interest semi-annually at six-month Libor  $+\ 0.50\%$  , with residual term  to maturity of 5 years and 3 months. You can effectively lock in the maximum level  of your future borrowing rate by buying a cap that consists of 10 half-year caplets,  starting in 3 month's time.

Generic representation of the payoff to a cap is given in Figure 1.1. The long option  position is a call if the underlying is an interest rate or an FRA; it is a put if the  underlying instrument is a future. The long-option position combined with the  unexpected effects of interest rate changes gives a payoff that resembles a long put  position on the interest rate – i.e. if interest rates fall the borrower benefits from the  fall less the option premium, but if rates rise the interest rate payable on is capped.  The effective rate of interest on the capped loan will be the exercise price of the  option plus the option premium and plus (minus) any reset margin above (below)  Libor. It is in fact very intuitive to see the payoff to the cap from the graph. The solid  thin line represents the interest rate exposure to the issuer or a borrower of a floating  rate loan. The thin dotted line represents the long call option for hedging the loan. The  payoff of the combined position is represented by the solid fat line, which shows the  offsetting effect of the positions for various interest rate scenarios.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/44785c5e549601a118e900929a3ce157d1295a924a25ff41e14ad0d5de9c67b5.jpg)
Figure 1.1 Profit and Loss using a Long Call on FRA

# Caps and Floors payoffs

The pay off of the options can simply be described algebraically using the following  notation. Let  $K_{c}$    and  $K_{p}$   be the strike levels for the call and the put respectively while  $T$    is the expiration date of the contract.

Caplet (pay off at maturity)    $\begin{array}{l}{{\displaystyle Q\{\mathrm{max},(0,L i b o r_{T}-K_{c})\frac{d a y s}{360}\}}}\\ {{\displaystyle Q\{\mathrm{max},(0,K_{P}-l i b o r_{T})\frac{d a y s}{360}\}}}\end{array}$  Floorlet (pay off at maturity)

The implication from the above algebrical representation of the payoffs at settlement  requires knowledge of the future course of the underlying rates, i.e. LIBOR. Since we  cannot realistically forecast the future course of an interest rate, it is natural to model  1 it as a random variable. Now, following the Black-Scholes  framework, the basic  assumption underlying option pricing theory is the nonexistent of arbitrage, were the  word "arbitrage" essentially addresses the opportunity to make a risk-free profit. In  other words, the common saying that "there is no free lunch" is the fundamental  principal underlying the theory of finance. To make the ideas presented above more  concrete, we now begin a formal treatment of the stochastic process of interest rate.

Let us suppose that the interest rate   $r$    follows Brownian Motion described by a  stochastic differential equation of the form
$$
d r_{t}=u(t,r_{t})d t+\sigma(t,r_{t})d W_{t}
$$

where   $u(t,r_{t})$  and   $\sigma(t,r_{t})$    the expected value and the standard deviation of the  instantaneous interest rate variation, respectively. The price at date  $t$    of a zero-coupon  bond maturing at date   $T>t$    is a function of the short term interest rate

$$
B(t,T)=B(t,T,r)\,.
$$
  .

Finally, the prices of zero-coupon bonds are derived by using an approach based on a  parabolic partial differential equation (PDE). From the PDE approach and applying  2 Ito's lemma  to equation (2) and using

$$
d r_{t}=u(t,r_{t})d t+\sigma(t,r_{t})d W_{t}
$$

one gets

$$
d B=[\frac{\delta B}{\delta t}+\frac{\delta B}{\delta r}u+{\scriptstyle\frac{1}{2}}\sigma^{2}\,\frac{\delta^{2}B}{{\delta r}^{2}}]d t+\frac{\delta B}{\delta r}\sigma d W_{t}
$$

$$
=u_{_B}B d t+\sigma B d W_{_t}\,.
$$

We now set up a riskless portfolio:   $P=B_{1}+\Phi B_{2}$    involving two zero-coupon bonds,  described as

$$
\begin{array}{l}{B_{1}=B(t,T_{1},r)}\\ {B_{2}=B(t,T_{2},r)\,.}\end{array}
$$
 .

Selecting the position   $\Phi$     in the second bond which renders the portfolio to be riskless,  we find the following condition:

$$
\frac{\delta B_{1}}{\delta r}+\Phi\,\frac{\delta B_{2}}{\delta r}=0\,.
$$

The net effect of the change of the portfolio is equal to zero. We can determine the  appropriate value of the position in the second bond by simply rearranging the  equation (7), from which we get

$$
\Phi=-\frac{\delta B_{1}}{\delta r}\nearrow\frac{\delta B_{2}}{\delta r}\,.
$$
 .

3 This can also be interpreted as the ratio of the sensitivities to the risk variable . We  can now express the change of the portfolio in a time  dt  as
$$
d\Pi=[{\frac{\delta B_{1}}{\delta t}}+{\frac{\delta B_{1}}{\delta r}}u+{\frac{\i}{2}}\sigma^{2}\,{\frac{\delta^{2}B_{1}}{\delta r^{2}}}]d t+\Phi[{\frac{\delta B_{2}}{\delta t}}+{\frac{\delta B_{2}}{\delta r}}u+{\frac{\i}{2}}\sigma^{2}\,{\frac{\delta^{2}B_{2}}{\delta r^{2}}}]d t
$$

Now, since the portfolio is riskless, it should have a return equal to the risk-free rate.

$$
\frac{d\Pi}{\Pi}=r d t
$$

4 or equivalently

$$
d\Pi=[{\frac{\delta B_{1}}{\delta t}}+{\frac{\delta B_{1}}{\delta r}}u+{\frac{_{1}}{2}}\sigma^{2}\,{\frac{\delta^{2}B_{1}}{\delta r^{2}}}]d t+\Phi[{\frac{\delta B_{2}}{\delta t}}+{\frac{\delta B_{2}}{\delta r}}u+{\frac{_{1}}{2}}\sigma^{2}\,{\frac{\delta^{2}B_{2}}{\delta r^{2}}}]d t=r(B_{1}+\Phi B_{2})
$$

The randomness in  d Π   will vanish since it makes the coefficient of   $d r$    zero. If we  assume the non existence of arbitrage, the portfolio must have a rate of return equal to  the short rate of interest. Finally, using equation (8) and rearranging the above  equation, we have

$$
\frac{\displaystyle\frac{\partial B_{1}}{\partial t}+\frac{\partial B_{1}}{\partial r}u+\frac{1}{2}\sigma^{2}\,\frac{\delta^{2}B_{1}}{\delta r^{2}}-r B_{1}}{\displaystyle\frac{\partial B_{1}}{\partial r}}=\frac{\displaystyle\frac{\partial B_{2}}{\partial t}+\frac{\partial B_{2}}{\partial r}u+\frac{1}{2}\sigma^{2}\,\frac{\delta^{2}B_{2}}{\delta r^{2}}-r B_{2}}{\displaystyle\frac{\delta B_{2}}{\delta r}}
$$

Hence the quantity (the same as the above equation except that we have divided by   $\sigma$  )

$$
\lambda=\lambda(t,r_{t})=\frac{\displaystyle{\frac{\delta B}{\delta t}+\frac{\delta B}{\delta r}u+{\scriptstyle{\frac{1}{2}}}\sigma^{2}\,\frac{\delta^{2}B}{\delta r^{2}}-r B}}{\displaystyle{\frac{\delta B}{\delta r}\sigma}}
$$

is a constant across all obligations at a given date. That is to say, the price of risk is  constant. Dividing the numerator and denominator by  $B$    in equation (11), we get

$$
\lambda=\frac{u_{\scriptscriptstyle B}-r}{\displaystyle\frac{1}{B}\frac{\delta B}{\delta r}\sigma}
$$

or equivalently

$$
u_{B}-r=\lambda\sigma_{B}
$$

Equation (12) can be interpreted as the access return (the return on a bond above the  risk-free rate) is equal to   $\lambda$    times a factor measuring the risk (volatility) of the bond.  Hence,   $\lambda$    can be interpreted naturally as the market price (interest rate) of risk.
It follows that the values of any securities that are sensitive to the change of the  interest rate  $r$    satisfies the partial-differential equation:

$$
\frac{\delta B}{\delta t}+\frac{\delta B}{\delta r}\,u+{\scriptstyle\frac{1}{2}}\sigma^{2}\,\frac{\delta^{2}B}{\delta r^{2}}-r B=\frac{\delta B}{\delta r}\sigma\lambda
$$

or

$$
\frac{\delta B}{\delta t}+\frac{\delta B}{\delta r}(u-\lambda\sigma)+{\scriptstyle{\frac{1}{2}}}\sigma^{2}\,\frac{\delta^{2}B}{\delta r^{2}}-r B=0
$$

The stochastic model for the spot rate presented above allows us to value contingent  claims such as bond options. In our analysis we can price caps and floor by solving  equation (14) with the boundary condition   $B(T,T,r)=1$  .

The result from equation (14) is a modified version of the original Black-Scholes  solution for pricing derivatives via risk neutral technique. This solution is the most  elegant result for pricing derivatives as it provides neat and incredible mathematical  solution to a complicated issue that incorporates investor risk. In fact one of the  crucial aspect of the model is based on its assumption on complete markets. This  implies that that all derivatives can be priced via replication strategy and it further  assumes that the appropriate securities to create the replicate position always exist.  Under this scenario, the return from the hedged or the replicated position should yield  the risk free rate and the risk premium required by investors is solved via the above  partial-differential equation. In fact, you can see this by rearranging the equation and  taking the   $-r B$   to the right hand side and equate this to the change of the portfolio.

Having derived the general bond pricing and risk-neutral framework, one can solve  equation (14) while using the boundary conditions to arrive the Black-76 closed-from  5 solution to price interest options such caps/floor, and bond option . For caps and  floors, we will use the implied forward rate   $F,$  ,  at each caplet maturity as the  underlying asset. We assume also that underlying forward rates follow lognormal  process. The price of the cap is simply the sum of the price of the caplets that make up  the cap. Similarly, the value of a floor is the sum of the sequence of individual put  options, these are often called floorlets.

$$
C a p=\sum_{i=1}^{n}C a p l e t_{i}\qquad\qquad\qquad\qquad F l o o r=\sum_{i=1}^{n}F l o o r l e t_{i}
$$

where

$$
C a p l e t=\frac{N o t i o n a l\cfrac{d}{B a s i s}}{(1+F\cfrac{d}{B a s i s})}e^{-r(T-t)}[F N(d_{1})-X N(d_{2})]
$$
$$
F l o o r l e t=\frac{N o t i o n a l\displaystyle\frac{d}{B a s i s}}{(1+F\displaystyle\frac{d}{B a s i s})}e^{-r(T-t)}[X N(-d_{2})-F N(-d_{1})]
$$

and

$$
d_{1}={\frac{\ln(F/X)+(\sigma^{2}/2(T-t)}{\sigma{\sqrt{T-t}}}}\qquad\quad d_{2}=d_{1}-\sigma{\sqrt{T-t}}
$$

The term   $d$    is the number of days in the forward period .  Basis  is the number of days  in the year used in the market, and the term  $N(.)$   is the cumulative normal distribution.  Note that the risk-free interest rate does not enter the equation for   $d_{\scriptscriptstyle1}$   and   $d_{2}$    because  the influence of the risk-free rate on the future values of the underlying asset in a riskneutral world is already accounted for in the forward price. Now, you can easily  implement this model by simply plugging in the input parameters such as, a value for  the underlying asset, strike level, number of days in the forward period and year. Most  importantly, you will need to assume a value for the volatility parameter. Once these  values are entered, the value of a cap or floor can easily be determined.

To implement the model described above and generate a numerical values, we will  use the Bloomberg Professional Analytics as our pricing tool of choice. The  Bloomberg cap/floor/collar pricing capabilities has become market standard among  various market players such as derivative traders, sales, and risk managers. Use of  these analytics creates transparency and helps market practitioners assess risk and  execute trades very easily. To continue our discussion, we analyse 5 year cap on a 3  month LIBOR. Figure 1.2. displays the value of the caplets expressed as a percentage  of face amount as well as the market value in nominal terms.

We illustrate the form for pricing the caplet on the Bloomberg system. This is done by  selecting the function BCCF   $<\!\mathrm{go}^{>}$   and then entering the following parameters:  settlement date, start date and expiration date and the face amount of the contract.  Volatility and strike(s) are crucial parameters to the model and will have tremendous  effect on the cost of the option depending on whether you wish to price the option on  a flat or varying strike and volatility levels. Enter a single volatility and strike for all  maturities or simply page forward to the second page and enter unique strike and  volatility levels for each caplet components. Once you have entered the strike(s), you  will immediately see the intrinsic value of the option visually from the graph on the  first page. The red horizontal line and the white steep curve display the strike level  6 and the implied forward  rate respectively.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/29a9d228cf43837cf0fa03358db9dcbb6856374f2a1c2c6048818dc440b2de9f.jpg)

# Figure 1.2.  Bloomberg Cap/Floor/Collar Valuation Screen: BCCF <go>

The selected flat option strike level of 3.501 is in fact higher then the implied forward  rate until approximately 12/27/04 but it is lower after this date until the expiry of the  last option. So, from the point of view of intrinsic value, the option is out-of-the  money until December 2004 and in-the-money from March 2005 until the last  expiration date.  We use the models default cap/floor implied vol at ili ties and get an  option premium of:

$$
C a p=\sum_{i=1}^{n}C a p l e t_{i}=5.0781\%
$$

and corresponding market value of

$$
(\frac{5.0781}{100})x1,\!000,\!000=50781.00
$$

To see the impact of the cost of the option by simply changing a single parameter  input such as the strike level, increase the strike by for example one percentage point  and you will price the option cheaper. To demonstrate the computational speed of the  model, change the calculator option to solve for the implied volatility by entering  specific premium level. Through iterative process the model will work out the correct  immediately implied volatility given an option premium.
Page three of the Bloomberg Cap/Floor/Collar pricing screen BCCF provides detailed  information such as each expiry dates of the option components, vol at ili ties, implied  forward rates, deltas, and the option component values. This is shown at figure 1.3.

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/3ea86aea34e696ff176d11274d3604c4c8d28412cf3e5ce53e5cfaaa2fac0109.jpg)

# Figure 1.3.  Bloomberg Cap/Floor/Collar Valuation Screen: BCCF <go>

Now, once the premium is computed, it must also be discounted back to time zero  using the forward rate consistent to the expiry of the contract. Bloomberg's  cap/floor/collar analytics is a powerful tool to price these contracts and requires  minimum model required inputs as it will also compute the implied forward rates  applicable for different expiry dates for the option.

# Estimating volatility

The estimation of volatility is of course central to the pricing options.  Specifically,  the volatility of returns from today until the maturity of the option is required. The  black model assumes constant volatility over this period, unlike the stochastic  volatility and some of the numerical models. The most common approaches in  estimating vol at ili ties is to adopt either of the following techniques:

  To assume volatility is stationary, and to calculate historical volatility
  To model volatility based upon historic information to provide a forecast using  7 models such as ARCH (Auto regressive Conditional Heteros ke d asti city)

   To imply volatility from other options already trading in the market place

The latter approach suggests a circular argument, namely deriving the volatility from  existing options. It can however act as an extremely useful check on where other  participants see volatility, but must be interpreted carefully.

This is precisely what is referred to in most academic literatures as the market  expectation of future rate changes. Many option markets that are highly liquid, for  example at-the-money USD and GBP cap markets, will quote vol at ili ties rather than  option prices. This is because all the pricing parameters required for the black model  are available elsewhere such as in the swap market. Therefore volatility is the only  unknown parameter.

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/135dfa776ce8d474df7fb081484b0dcc4a76239a8e1dcc79faf2c165417f305a.jpg)

# Figure 1.4.  Bloomberg Cap/Floor Implied volatility surface

An excellent knowledge of implied volatility in terms of future expectations for future  price or rate variability allows one a better way to assess his/her exposure to market  risk. Knowing how changing volatility affect hedging and pricing will be crucial for  the development of a cost-effective hedges and weigh up the timing risks coupled  with a particular strategy.

It is also a common practise to use volatility surfaces, i.e. a matrix of (strike vs.  forward start date), when pricing and valuing caps and floors. This allows the smile  effect to be incorporated. The data used in figure 1.4 can be accessed or easily  downloaded from the Bloomberg in order to generate three dimensional volatility  surfaces and smiles to help one identify miss-priced options.
# Appendix: Itô’s Lemma

In finance, when using continues-time models, it is common to assume that the price  of an asset is an Ito's process. Therefore, to derive the price of a financial derivative,  one needs to use Ito's calculus. In this section, we briefly review Ito's lemma by  treating it as a natural extension of the differentiation in calculus. Ito's lemma is the  basis of stochastic calculus.

# Review of Differentiation

Let   $G(x)$    be differentiable function of  $x$  .  Using Taylor expansion, we have

$$
\Delta G\equiv G(x+\Delta x)-G(x)=\frac{\delta G}{\delta x}\Delta x+\frac{1}{2}\frac{\delta^{2}G}{\delta x^{2}}(\Delta x)^{2}+\frac{1}{6}\frac{\delta^{3}G}{\delta x^{3}}(\Delta x)^{3}+.......\,.
$$

Taking the limit as   $\Delta x\rightarrow0$   and ignoring the higher order terms of ,  we have

$$
d G={\frac{\delta G}{\delta x}}d x.
$$

When  $G$    is a function of  $x$    and  $y.$  ,  we have

$$
\Delta G=\frac{\delta G}{\delta x}\Delta x+\frac{\delta G}{\delta y}\Delta y+\frac{1}{2}\frac{\delta^{2}G}{\delta x^{2}}(\Delta x)^{2}+\frac{\delta^{2}G}{\delta x\delta y}\Delta x\Delta y+\frac{1}{2}\frac{\delta^{2}G}{\delta y^{2}}(\Delta y)^{2}+.......
$$

Taking the limit as   $\Delta x\rightarrow0$    and as   $\Delta y\to0$  ,  we have

$$
d G=\frac{\delta G}{\delta x}d x+\frac{\delta G}{\delta y}d y.
$$

To turn in the case in which  $\mathrm{G}$   is a differentiable function of   $x_{t}$  and  $t,$  ,  and   $x_{t}$  is an Ito's  process. The Taylor expansion becomes

$$
\Delta G=\frac{\delta G}{\delta x}\Delta x+\frac{\delta G}{\delta t}\Delta t+\frac{1}{2}\frac{\delta^{2}G}{\delta x^{2}}(\Delta x)^{2}+\frac{\delta^{2}G}{\delta x\delta t}\Delta x\Delta t+\frac{1}{2}\frac{\delta^{2}G}{\delta t^{2}}(\Delta t)^{2}+.......
$$

# Selected Bibliography and References

Abken, Peter A. "Interest Rate Caps, Collars and Floors."  Economic Review ,  Federal Reserve Bank of Atlanta 74 (November-December, 1989), pp.2-25  Black, F & Scholes, M 1973 “The pricing of options and corporate liabilities”  Journal of Political Economy

#  www.YieldCurve.com 2003
Yaksick, Rudy. "Swaps, Caps and Floors: Some Parity and Price Identities."  The Journal of Financial Engineering  1 (June, 1992), pp.105-115.  Bjork, Tomas,  Arbitrage Theory in Continuous Time . Oxford: Oxford  University Press 1998  Clewlow, Les and Chris Strickland.  Implementing Derivatives Models ,  Chichester, U.K.: John Wiley 1998  Haug, Espen Gaarder.  The Complete Guide to Option Pricing Formulas . New  York: McGraw-Hill 1997  Hull, John C.  Options, Futures and other Derivatives , 4th. ed. Inglewood  Cliffs, New Jersey: Prentice-Hall 2000   Jarrow, Robert A.  Modelling Fixed Income Securities and Interest Rate  Options . New York: McGraw-Hill 1996  Pliska, Stanley R.  Introduction to Mathematical Finance: Discrete Time  Models.  Malden, Mass.: Blackwell 1997  Prisman, Eliezer Z.   Pricing Derivative Securities .  San Diego: Academic  Press 2000  Wilmott, Paul.  Derivatives: The Theory and Practice of Financial  Engineering . New York: Wiley 1999  Wilmott, Paul, Sam Howison and Jeff DeWynne.  The Mathematics of  Financial Derivatives: A Student Introduction . Cambridge: Cambridge  University Press 1995  Tsay, Ruey S.   Analysis of Financial Time Series . Wiley, 2002
