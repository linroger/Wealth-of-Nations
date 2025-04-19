---
tags:
  - convexity
  - coupon_bonds
  - futures_contracts
  - interest_rates
  - mark_to_market
aliases:
  - Bond Convexity
  - Convexity in Pricing
  - Futures vs. Forwards
  - Sources of Convexity
key_concepts:
  - Bond convexity
  - Convexity by design
  - Convexity in pricing functions
  - Correlation and pricing
  - Coupon bond pricing
  - Daily marking-to-market
  - Eurocurrency future example
  - Futures settlement price
  - Option convexity
  - Overnight interest rate
  - Plain vanilla swaps
---

# 10.4 SOURCES OF CONVEXITY  

There is more than one reason for the convexity of pricing functions. We discuss some simple cases briefly, using a broad definition of convexity.  

# 10.4.1 MARK TO MARKET  

We start with a minor case due to daily marking-to-market requirements. Let $f_{t}$ denote the daily futures settlement price written on an underlying asset $S_{t},$ let $F_{t}$ be the corresponding forward price, and let $r_{t}$ be the overnight interest rate.  

Marking to market means that the futures position makes or loses money every day depending on how much the futures settlement price has changed,.  

$$
\Delta f_{t}=f_{t}-f_{t-1}
$$  

where the time index $t$ is measured in days and hence is discrete.  

Suppose the overnight interest rate $r_{t}$ is stochastic. Then if the trader receives (pays) mark-tomarket gains daily, these can be deposited or borrowed at higher or lower overnight interest rates. If $\Delta f_{t}$ were uncorrelated with interest rate changes,  

$$
\Delta r_{t}=r_{t}-r_{t-1}
$$  

marking to market would not make a difference.  

But, when $S_{t}$ is itself an interest rate product or an asset price related to interest rates, the random variables $\Delta f_{t}$ and $\Delta r_{t}$ will, in general, be correlated. For illustration, suppose the correlation between $\Delta f_{t}$ and $\Delta r_{t}$ is positive. Then, when. $f_{t}$ increases, $r_{t}$ is likely to increase also, which. means that the mark-to-market gains can now be invested at a higher overnight interest rate. If the correlation between $\Delta f_{t}$ and $\Delta r_{t}$ is negative, the reverse will be true. Forward contracts do not, normally, require such daily marking-to-market. The contract settles only at the expiration date. This means that daily paper gains or losses on forward contracts cannot be reinvested or borrowed at higher or lower rates..  

Thus, a futures contract written on an asset $S_{t}$ whose price is negatively correlated with $r_{t}$ will be cheaper than the corresponding forward contract. If the correlation between $S_{t}$ and $r_{t}$ is positive,e then the futures contract will be more expensive. If $S_{t}$ and $r_{t}$ are uncorrelated, then futures and forward contracts will have the same price, everything else being the same.  

# EXAMPLE  

Consider any Eurocurrency future. We saw in Chapter 3 that the price of a 1-year Eurodollar future, settling at time $t+1$ , is given by the linear function  

$$
V_{t}=100(1-f_{t})
$$  

Normally, we expect overnight interest rate $r_{t}$ to be positively correlated with the futures rate $f_{t}$ . Hence, the price $V_{t}$ , which is not a convex function, would be negatively correlated with $r_{t}$ . This means that the Eurodollar futures will be somewhat cheaper than corresponding forward contracts, which in turn means that futures interest rates are somewhat higher than the forward rates.  

Mark-to-market is one reason why futures and forward rates may be different.  

# 10.4.2 CONVEXITY BY DESIGN  

Some products have convexity by design. The contract specifies payoffs and underlying risks, and this specification may make the contract price a nonlinear function of the underlying risks. Among the most important classes of instruments that permit such convexity gains are, of course, options.  

We also discussed convexity gains from bonds. Long maturity default-free discount bond prices. when expressed as a function of yield to maturity $y_{t},$ are simple nonlinear functions, such as  

$$
B(t,T)=\frac{100}{\left(1+y_{t}\right)^{T}}
$$  

Coupon bond prices can be expressed using similar discrete time yield to maturity. The price of a coupon bond with coupon rate $c$ , and maturity $T,$ can be written as  

$$
P(t,T)=\left(\sum_{i=1}^{T}\frac{100c}{\left(1+y_{t}\right)^{i}}\right)+\frac{100}{\left(1+y_{t}\right)^{T}}
$$  

It can be shown that default-free pure discount bonds, or strips, have more convexity than coupon bonds with the same maturity.  

# 10.4.2.1 Swaps  

Consider a plain vanilla, fixed payer interest rate swap with immediate start date at $t=t_{0}$ and end date, $t_{n}=T.$ Following market convention, the floating rate set at time. $t_{i}$ is paid at time $t_{i+1}$ . For simplicity, suppose the floating rate is 12-month USD LIBOR. This means that $\delta=1$ . Let the time $t=t_{0}$ swap rate be denoted by $s$ and the notional amount,. $N$ , be 1.  

Then, the time. $t_{0}$ value of the swap is given by  

$$
V_{t_{0}}=E_{t_{0}}^{\tilde{P}}\left[\frac{L_{t_{0}}-s}{\left(1+L_{t_{0}}\right)}+\frac{L_{t_{1}}-s}{\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)}+\cdots+\frac{L_{t_{n-1}}-s}{\prod_{i=0}^{n-1}\left(1+L_{t_{i}}\right)}\right]
$$  

where $\{L_{t_{0}},...,L_{t_{n-1}}\}$ are random LIBOR rates to be observed at times $t_{0},...,t_{n-1}$ , respectively, and $\tilde{P}$ is an appropriate probability measure. With a proper choice of measure, we can act as if we  

can substitute a forward LIBOR rate, $\boldsymbol{F}(t_{0},t_{i})$ , for the future spot LIBOR $L_{t_{i}}$ for all ${t_{i}}^{13}$ If liquid markets exist where such forward LIBOR rates can be observed, then after this substitution we can write the previous pricing formula as.  

$$
\begin{array}{r l}{V_{t_{0}}=}&{\cfrac{L_{t_{0}}-s}{\big(1+L_{t_{0}}\big)}+\cfrac{F(t_{0},t_{1})-s}{\big(1+L_{t_{0}}\big)(1+F(t_{0},t_{1}))}}\ &{+\cfrac{F(t_{0},t_{2})-s}{\big(1+L_{t_{0}}\big)(1+F(t_{0},t_{1}))(1+F(t_{0},t_{2}))}+\dots+\cfrac{F(t_{0},t_{n-1})-s}{\prod_{i=0}^{n-1}(1+F(t_{0},t_{i}))}}\end{array}
$$  

where $F(t_{0},t_{0})=L_{t_{0}}$ , by definition. Clearly, this formula is nonlinear in each $\boldsymbol{F}(t_{0},t_{i})$ . As the forward rates change, $V_{t_{0}}$ changes in a nonlinear way..  

This can be seen better if we assume that the yield curve is flat and that all yield curve shifts are parallel. Under such unrealistic conditions, we have.  

$$
L_{t_{0}}=F(t_{0},t_{0})=F(t_{0},t_{1})=\cdots=F(t_{0},t_{n-1})=F_{t_{0}}
$$  

The swap formula then becomes  

$$
V_{t_{0}}=\frac{F_{t_{0}}-s}{(1~+~F_{t_{0}})}+\frac{F_{t_{0}}-s}{(1~+~F_{t_{0}})^{2}}+\cdots~+~\frac{F_{t_{0}}-s}{(1~+~F_{t_{0}})^{T}}
$$  

which simplifies to14  

$$
V_{t_{0}}=\left(F_{t_{0}}-s\right)\frac{\left(\left(1+F_{t_{0}}\right)^{T}-1\right)}{F_{t_{0}}\left(1+F_{t_{0}}\right)^{T}}
$$  

The second derivative of this expression with respect to $F_{t_{0}}$ will be negative, for all $F_{t_{0}}>0$  

As this special case indicates, the fixed payer swap is a nonlinear instrument in the underlying forward rates. Its second derivative is negative, and the function is concave with respect to a "typical' forward rate. This is not surprising since a fixed payer swap has risks similar to the issuing of a 30-year bond. This means that a fixed-receiver swap will have a convex pricing formula and will have a similar profile as a long position in a 30-year coupon bond.  

# EXAMPLE  

Figure 10.5 plots the value of a fixed payer swap under the restrictive assumption that the yield curve is flat and that it shifts only parallel to itself. The parameters are as follows:.  

$$
t=0
$$  

$$
s=7\%
$$  

$$
\begin{array}{c}{T=30}\ {}\ {F_{t_{0}}=6\%}\end{array}
$$  

We see that the function is nonlinear and concave.  

![](84952aef7f555a0f36bb2edcf5dc0c032a8a4a9f3f5894caca976fd867d60e7d.jpg)  

# FIGURE 10.5  

Value of a fixed payer swap.  

In Chapter 20, we will consider a different type of swap called constant maturity swap. The. convexity of constant maturity swaps is due to their structure. This convexity will, in general, be more pronounced and at the same time more difficult to correctly account for..  

Taking convexity characteristics of financial instruments into account is important. This is best. illustrated by the Chicago Board of Trade's (CBOT) attempt to launch a new contract with proper convexity characteristics.  

# EXAMPLE  

The Chicago Board of Trade's board of directors last week approved a plan to launch 5- and 10-year US dollar denominated interest rate swap futures and options contracts. Compared with the over-the-counter market, trading of swaps futures will reduce administrative cost and eliminate counterparty risk, the. exchange said. The CBOT's move marks the second attempt by the exchange to launch a successful swap futures contract. Treasuries were the undisputed benchmark a decade ago. They are not treated as a benchmark for valuation anymore. People price off the swap curve instead, said a senior economist at the CBOT.  

The main difference between the new contract and the contract that the CBOT de-listed in the mid-1990s is that the new one is convex in form rather than linear. It's one less thing for end users to worry about, the economist said, noting that swap positions are marked to market on a convex basis. Another critical flaw in. the old contract was that it launched in the 3- and 5-year, rather than the 5- and 10-year maturities, which. is where most business takes place..  

The new swaps contracts will offer institutional investors such as bank treasurers, mortgage passthrough. traders, originators, service managers, portfolio managers, and other OTC market participants a vehicle for hedging credit and interest rate exposure, the exchange said.  

(Thomson Reuters IFR Issue 1393, July 21, 2001)  

This is an excellent example that shows the importance of convexity in contract design. Futures contracts are used for hedging by traders. If the convexity of the hedging instrument is different than the convexity of the risks to be hedged, then the hedge may deteriorate as volatility changes. In fact, as volatility increases, the more convex instrument may yield higher gamma gains and this will influence its price.  

# 10.4.2.2 Convexity of FRAs  

Now consider the case of forward rate agreements (FRAs). As discussed in Chapter 3, FRAs are instruments that can be used to fix, at time. $t_{0}$ the risk associated with a LIBOR rate. $L_{t_{i}}$ , that will be observed at time $t_{i:}$ and that has a tenor of. $\delta$ expressed in days per year.15 The question is when would this FRA be settled. This can be done in different ways, leading to slightly different instruments. We can envisage three types of FRAs.  

One way is to set. $L_{t_{i}}$ at time $t_{i},$ but then, settle at time. $t_{i}+\delta$ . This would correspond to the "natural" way interest is paid in financial markets. Hence, at time $t=t_{0}$ , the value of the FRA will be zero and at time. $t_{i}+\delta$ the FRA buyer will receive or pay  

$$
\left[L_{t_{i}}-F_{t_{0}}\right]N\delta
$$  

depending on the sign of the difference. The FRA seller will have the opposite cash flow.  

The second type of FRA trades much more frequently in financial markets. The description of these is the same, except that the FRA is settled at time. $t_{i:}$ instead of at $t_{i}+\delta$ At time $t_{i}.$ when thee LIBOR rate $L_{t_{i}}$ is observed, the buyer of the FRA will make (receive) the payment  

$$
\frac{\left[L_{t_{i}}-F_{t_{0}}\right]\delta}{1+L_{t_{i}}\delta}N
$$  

This is the previous settlement amount discounted from time $t_{i}+\delta$ to time $t_{i},$ using the time $t_{i}$ LIBOR rate. Figure 10.6 shows an example to the payoff of a 12-month FRA.  

Of even more interest for our purpose is a third type of FRA contract, a LIBOR-in-arrears FRA where the LIBOR observed at time $t_{i}$ is used to settle the contract at time $t_{i:}$ according to  

$$
\left[L_{t_{i}}-f_{t_{0}}\right]\delta N
$$  

![](0c52dfff15003128c045173addfc20ce75708b454ceed03cedb1f9c44455d4ab.jpg)  

# FIGURE 10.6  

Payoff of a 12-month FRA.  

Here, $f_{t_{0}}$ is the FRA rate that applies to this particular type of FRA.16 Note that we are using a. symbol different than $F_{t_{0}}$ , because the two FRA rates are, in general, different from each other due to convexity differences in the two contracts..  

The question to ask here is under what conditions would the rates $F_{t_{0}}$ and $f_{t_{0}}$ differ from each other? The answer depends indeed on the convexity characteristics of the underlying contracts. In fact, market practitioners approximate these differences using convexity adjustment factors.  

# 10.4.3 PREPAYMENT OPTIONS  

A major class of instruments that have convexity by design is the broad array of securities associ-. ated with mortgages. A mortgage is a loan secured by the purchaser of a residential or commercial property. Most fixed-rate mortgages have a critical property. They contain the right to prepay the loan. The mortgage receiver has the right to pay the remaining balance of the loan at any time, and incur only a small transaction cost. This is called a prepayment option and introduces negative convexity in mortgage-related securities. In fact, the prepayment option is equivalent to. an American-style put option written on the mortgage rate $R_{t}$ . If the mortgage rate $R_{t}$ falls below a limit $R^{K}$ the mortgage receiver will pay back the original amount denoted by $N.$ by refinancing at the new rate $R_{t}$ Instead of making a stream of fixed annual interest payments $R_{t_{0}}N$ , the mortgage receiver has the option (but not the obligation) to pay the annual interest $R_{t_{i}}N$ at some time $t_{i}$ The mortgage receiver may exercise this option if. $R_{t_{i}}<R_{t_{0}}$ . The situation is reversed for the. mortgage issuer.  

The existence of such prepayment options creates negative convexity for mortgage-backed securities (MBSs) and other related asset classes. Since the prepayment option involves an exchange of one fixed stream of payments against another fixed stream, it is clear that interest rate swaps play a critical role in hedging and risk-managing these options dynamically. We will deal with this important topic in Chapter 17.  
