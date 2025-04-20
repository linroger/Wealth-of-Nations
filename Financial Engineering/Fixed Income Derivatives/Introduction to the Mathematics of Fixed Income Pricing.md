---
tags:
  - arbitrage_pricing
  - fixed_income
  - interest_rates
  - mathematical_finance
  - risk_neutral
aliases:
  - Fixed Income Math
  - Fixed Income Pricing
key_concepts:
  - arbitrage pricing theory
  - discount bond maturity
  - fixed income pricing
  - risk neutral valuation
  - stochastic variables calculus
---

# Introduction to the Mathematics of Fixed Income Pricing  
  
# Introduction  

Powerfully built techniques for handling the dynamics and calculus of stochastic variables  such as interest rates have been developed over the last few decades. In this section we  introduce the fundamentals of mathematical finance with respect to fixed income pricing.  An extended and through discussion of the content of this section can be found in  Choudhry (2004).  

To begin we need to state the following sets of assumptions, generally adopted from  1 Merton’s  pricing method:  

   There are no transaction cost or taxes 

    There exists an exchange market for borrowing and lending at the same rate of interest  (no bid-offer spread) 

    The term structure is “flat” and known with certainty 

    There is a rational and competitive market 

    Market participants prefer to increase wealth 

    There are no arbitrage opportunities.  

The main prerequisite of mathematical finance that is imperative in understanding fixed  income are risk neutral valuation and arbitrage pricing theory. In this introduction we will  establish the probabilistic setting in which these concepts are formulated.  

As stated in Musiela and Rutkowski (1998), an economy is a family of filtered space   $\{\!\!\left(\varOmega,I,\mu\right)\!\!:\mu\in P\!\right\}^{2}$  , where the filtration satisfies the usual conditions 3 , and  $\textdollar{P}$    is a collection  4 of mutually equivalent probability measures on the measurable space.   We model the  subjective market uncertainty of each investor by associating to each investor a probability  measure from   $\textdollar{P}$  . Investors with more risky tolerance will be represented by probability  measures that weight unfavourable events relatively lower, whereas conservatives investors  are characterized by probability measures that weight unfavourable relatively higher.  Moreover, it is assumed that investment information is revealed to each investor  simultaneously as events in the filtration.  

Since the measures in  $\textdollar{P}$   are mutually equivalent, the investors agree on the events that have  and have not occurred. We refer the reader to Neftci (2000) for an excellent example of this.  It is convenient to further assume that investors initially have no other information, that is,  the filtration is trivial with respect to each probability measure in   $\textdollar{P}$  . This assumption  asserts that the initial information available to investors is objective.  
The foundation of a working knowledge of fixed income finance rests on an understanding  of the inherent relationship between the various interest rates and bonds. Consider the  economy   $\{\!(\varOmega,I,\mu)\!:\!\mu\in\bar{P}\!\}$   on the interval   $[0,T]$   and a Markov process   5      $X_{t}$      $I\equiv\sigma\big(X_{:0\leq s\leq t}\big)$  6 with . Implicit in this statement is the assumption that the state variable   probability   ${\cal P}\equiv{\cal P}^{X}$   associated with   $\boldsymbol{X}_{t}$    belongs to  $\textdollar{P}$   for some fixed elements  $\mathrm{X}$   of the state  space  $\boldsymbol{X}_{t}$   .  

Setting the scene further, a zero coupon or discount bond of maturity    $T$   is a security that  pays the holder one unit of currency at time   $T.$  . The prices of government and corporate  discount bonds at time   $t\leq T$   are denoted   $B(t,\boldsymbol{T})$   and   $\widetilde{B}(t,T)$   respectively. The local  expectation hypothesis (L-EH) relates the discount bond to the instantaneous interest rate,  or the spot rate for borrowing of the loan over the time interval  $\left[t,t+d t\right]$  .  

Denote the riskless spot rate by   $\boldsymbol{r}_{t}=\boldsymbol{r}(\boldsymbol{X}_{t})$   and assume that it is a non-negative, adapted  process with almost all sample paths integrable on the   $\left[0,T\right]$   with respect to the Lebesgue  measure.  

The L-EH asserts that  

$$
B(t,T)=E_{P}(\exp(-\int_{t}^{T}r(X_{s})d s|I_{t})
$$  

As defined in Musiela and Rutkowski (1998), the economic interpretation of this  hypothesis is that “… the current bond price equals the expected value … of the bond price  in the next (infinitesimal) period, discounted at the current short-term rate”.  

This statement is better understood in a discrete time setting. In fact using a left sum  approximation to the integral with partition   $\left\{\boldsymbol{t}_{i}\right\}_{t=0}^{n}$   of   $[0,T]$   yields  

$$
\begin{array}{r l}&{B(0,T)=E_{P}(\exp(-\underset{i=L}{\overset{n}{\sum}}r(X_{t_{i-l}})\varDelta t_{i}))}\\ &{=E_{P}(\exp(-r(X_{t_{o}})\varDelta t_{L})\exp(-\underset{i=2}{\overset{n}{\sum}}r(X_{t_{i-l}})\varDelta t_{i}))}\\ &{=(\exp(-r(X)t_{L})E_{P}(E_{P}(\exp(-\underset{i=2}{\overset{n}{\sum}}r(X_{t_{i-l}})\varDelta t_{i}\big|_{t_{i}}))}\\ &{=(\exp(-r(X_{t_{o}})t_{L})E_{P}^{X}(B(t,T))}\end{array}
$$  
Under the assumption of no arbitrage, it can be shown that above equation holds under the  8 risk neutral measure.   Naturally as similar relationship holds between the risky bond and  the risky spot rate.  

# [[1. DeterministicCashFlows#2 Fixed Income Securities|Bond pricing]]  

9  ${'}B_{t}$  The process   $B_{t}$   is referred to as an accumulation factor or savings account.  represents  the price of a riskless security that continuously compounds at the spot rate. More precisely  it is the amount of cash at time  $t$   that accumulates by investing   $\S1$   initially, and continually  rolling over a bond with an infinitesimal time to maturity. See Musiela and Rutkowski  (1998) page 268 for more detail on this.  

Therefore an adapted process   $B_{t}$   of finite variation with continuous sample path is given by  

$$
B_{t}=\exp(\intop_{0}^{t}r(X_{s})d s
$$  

When security   $S_{t}$  is divided by the saving account the resultant process is the price process  10 of the security discounted at the riskless rate.  

We consider next a coupon-bearing bond, with fixed coupon payments   $c_{l},...,c_{n}$   at  predetermined times   $T_{\mathit{l}},...,T_{\mathit{n}}$   with  $T_{n}=T$  .  

The price of the coupon bond is simply the present value of the sum of these cash flows.  Denoting the price of a riskless coupon bond at time by  $c B(t,T)$  , we have  

$$
B_{c}(t,T)=\sum_{i=I}^{n}c_{i}B(t,T)
$$  

A similar relationship holds for the risky coupon bond.  

However  the  coupons  are  typically  structured  by  setting  $c_{i}=c$    for   $\mathbf{i}=l,...,n-l$    and  $\mathtt{c_{n}}=N+c$  , where  $N$  is the principal or face value, and   $c$   is  a fixed amount that is generally quoted as a percentage of   $N$  called the coupon rate. A  problem that arises in comparing coupon bonds is that uncertainty about the rate at which  the coupons will be reinvested causes uncertainty in the total return of the coupon bond.  Hence, coupon bonds of different coupon rates and payment dates are not directly  comparable. The standard way to overcome this problem is to extend the notion of a yield  to maturity to coupon bearing bonds.  
# [[1. DeterministicCashFlows#2.2 Yield-To-Maturity|Yield to Maturity (YTM)]]  

In Musiela and Rutkowski (1998) the continuously compounded riskless yield to maturity   $Y_{c}(t)=Y_{c}(t;c_{_I},...,c_{_n}.T_{_I},...,T_{_n})$   is derived as the unique exposition to the equation  

$$
B_{c}(t)=\sum_{T_{i}>t}c_{i}e^{-Y_{c}(t)(T_{i}-t)}
$$  

and stands for the total return on the coupon bond under the assumption that each of the  coupon payments occurring after  $t$   is reinvested at the rate  $Y_{c}(t)$  . The risky yield to maturity  is defined in a similar fashion.  

# [[1. DeterministicCashFlows#3.2 Term Structure Explanations|Expectation Hypothesis]]  

There are number of excellent textbooks that the reader is encouraged to read which  provides the necessary background, in particular Ingersoll (1987) and Choudhry (2004).  

The yield to maturity expectation hypothesis (YTM-EH) relates the riskless YTM and the  riskless spot rate. Musiela and Rutkowski (1998) state that this hypothesis as the assertion  that  

“… the [continuously compounded] yield from holding any [discount] bond is equal  to the [continuously compounded yield expected from rolling over a series of single  period [discount] bonds”.  

To gain a better understanding of this statement, we first observe that the YTM of a discrete  time setting with the partition  $\left\{\boldsymbol{t}_{i}\right\}_{i=0}^{n}$    of   [t, T] , we have that the yield of a discount bond   $B(t_{i-l},t_{i})$    is given by  

$$
Y(t_{i-l},t_{i})=r(X_{t_{i-l}})
$$  

from which we deduce that the bond price is given by  

$$
B(t_{i-l},t_{i})=\exp(-r(X_{t_{i-l}})\varDelta t_{i}\,.
$$
 .  

Since the YTM-EH asserts that the yield of   $B(t,\boldsymbol{T})$   is equal to the yield expected from  rolling over a series of discount bonds  $B(t_{i-l},t_{i})$  , it follows that  

$$
\begin{array}{l}{{\displaystyle Y(t,T)\!=\!\frac{I}{T-t}\mathrm{ln}(B(t,T))\!=\!-\!\frac{I}{T-t}E_{P}\!\left[\mathrm{ln}\!\left(\prod_{i=L}^{n}B(t_{i-L},t_{i})\right)\!\!\left|I_{t}\right.\right]}}\\ {{\displaystyle=\!\frac{I}{T-t}E_{P}\!\left[\sum_{i=L}^{n}\!r(X_{t_{i-L}})\varDelta t_{t}\big|I_{t}\right]\!.}}\end{array}
$$  
Taking the limit, as the mesh of the partition tends to zero; we obtain the continuously time  discount bond price and YTM under the YTM-EH:  

$$
\begin{array}{l}{{\displaystyle B(t,T)=\exp\Biggl\lbrack-E_{P}\biggl(\int_{t}^{T}r(X_{s})d s\biggr)\bigl\rbrack I_{t}\Biggr\rbrack}}\\ {{\displaystyle Y(t,T)=\frac{I}{T-t}\Biggl[E_{P}\biggl(\int_{t}^{T}r(X_{s})d s\biggr)\bigl\rbrack I_{t}\Biggr]}}\end{array}
$$  

The last interest rate that we will consider is the instantaneous forward interest rate, or  forward rate for borrowing or lending over the time interval   $\left[s,s+d s\right]$   as seen from  \~ time  $\left[t\!\le\!s\right]$  . This will be denoted by   $f(t,s)$   in the riskless case and   $\widetilde{f}(t,s)$   in the risky case.  

If the dynamics of the process   $\left\{f(t,s)\right\}_{t\leq s\leq T}$   are specified, then the price of the discount  bond is defined by  

$$
B(t,T)=\exp(-\!\!\!\int_{t}^{T}f(s,t)d s
$$  

Alternatively, if the dynamics of the discount bond are known, then we have  

$$
f(t,T)=-\frac{\partial}{\partial T}\ln B(t,T),
$$  

provided that this derivation exists!  

Therefore the YTM-EH asserts that the forward rate is an unbiased estimate of the spot rate  under the state variable probability measure   $\textdollar{P}$  . See Choudhry (2004) chapter 2, equation  (2.18). For the relationship between the spot and forward rate we refer the reader to read  further in chapter 3 of Choudhry (2004).  

# 11 Review of Arbitrage Pricing Theory  

12 The methodology presented in this review can be found in Musiela and Rutkowski (1998) .  Consider the economy   $\left\{\!\left(\varOmega,I,\mu\right)\!:\mu\in P\right\}$   on the interval  $[0,T]$  . A trading strategy or  portfolio   $\phi_{t}$   is a vector of locally bounded adapted processes of tradable asset holdings.  13 Moreover, it is assumed that every sample path is right continuous with left limits . A  trading strategy   $\phi_{t}$   is called self-financing if the wealth process   $W_{t}(\phi)$    of the trading  strategy neither receives nor pays out cash flows external to the assets that comprise the  strategy.  
More precisely, let  φ   denote the holding of asset  $S^{i}$  . Then, a self-financing trading strategy   $\phi\!=\!(\phi^{L},\!\ldots,\!\phi^{n})$   is defined by asserting that   $W_{t}(\boldsymbol{\phi})=\sum_{t=L}^{n}\boldsymbol{\phi}_{t}^{L}\,\boldsymbol{S}_{t}^{i}$   satisfies  

$$
d W_{t}(\phi)\!=\!\phi_{t}^{^{L}}d S_{t}^{^{L}+...+}\phi_{t}^{^{L}}d S_{t}^{^{n}}
$$  

A strategy   $\phi\!\in\!\Phi_{_T}$   is called an arbitrage opportunity if the wealth process   $W(\phi)$   satisfies for  some (consequently for all)  $P\in P$  , all the following conditions  

$$
\begin{array}{r l r}&{W_{o}\left(\phi\right)=0}&{(\mathrm{zero\,inseatm e n t})}\\ &{\mathbb{P}\big\{\mathrm{W}_{\mathrm{T}}\left(\phi\right)\geq0\big\}=I}&{(\mathrm{Zerror\,disk})}\\ &{\mathbb{P}\big\{\mathrm{W}_{\mathrm{T}}\left(\phi\right)>0\big\}>0}&{(\mathrm{PSble\,gain}).}\end{array}
$$  

Thus, taking an advantage the arbitrage opportunity it is possible to create limitless wealth  without risk. Under the assumption that arbitrage portfolios do not exist, it has been shown  that there exists a risk-neutral or martingale measure Q in our economy under which the  discounted asset process   $Z\equiv B_{t}^{-I}S_{t}$   follows a martingale. This result is known as the  Fundamental Theorem of Asset Pricing. Musiela and Rutkowski (1998) define this theorem  as “a result, which establishes the equivalence the absence of an arbitrage opportunity in  the stochastic model of financial market, and the existence of a martingale measure”.  

# References  

Bjork, T.,  Arbitrage Theory in Continuous Time . Oxford 1997  

Choudhry, M.,  Analysing & Interpreting the Yield Curve , John Wiley 2004  Ingersoll, J.,  Theory of Financial Decision Making,  Rosman and Littlefield 1987  Karatzas, I and Shreve, S.,  Brownian Motion and Stochastic Calculus , Spinger 1991  Korn, R., and Korn, E.,  Option Pricing and Portfolio Optimization , AMS 2000  Musiela, M., and Rutkowski, M.,  Martingale Methods in Financial Modelling , Spinger  1997  

Neftci, S.,  An Introduction to the Mathematics of Financial Derivatives , Academic Press  2000  

Pliska, S.,  Introduction to Mathematical Finance: Discrete Time Models , Blackwell 1997  Rosenthal, J.,  A First Look at Rigorous Probability Theory , World Scientific 2000  
