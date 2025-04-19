---
tags:
  - goldman_sachs
  - hedging_strategies
  - option_replication
  - options_pricing
  - quantitative_finance
aliases:
  - Derman, Ergener, Kani
  - Option Replication
  - Static Replication
key_concepts:
  - Fixed portfolio weights
  - Option hedging method
  - Option pricing models
  - Replicating option portfolio
  - Standard option portfolio
---

# Quantitative Strategies Research Notes  

# Static Options Replication  

# Emanuel Derman Deniz Ergener. Iraj Kani.  

Copyright 1994 Goldman, Sachs & Co. All rights reserved.  

This material is for your private information, and we are not soliciting any action based upon it. This report is not to be construed as an offer to sell or the solicitation of an offer to buy any security in any jurisdiction where such an offer or solicitation would be illegal. Certain transactions, including those involving futures, options and high yield securities, give rise to substantial risk and are not suitable for all investors. Opinions expressed are our present opinions only. The material is based upon information that we consider reliable, but we do not represent that it is. accurate or complete, and it should not be relied upon as such. We, our affiliates, or persons involved in the. preparation or issuance of this material, may from time to time have long or short positions and buy or sell securities, futures or options identical with or related to those mentioned herein..  

This material has been issued by Goldman, Sachs & Co. and/or one of its affiliates and has been approved by. Goldman Sachs International, regulated by The Securities and Futures Authority, in connection with its distribution in the United Kingdom and by Goldman Sachs Canada in connection with its distribution in Canada. This material is. distributed in Hong Kong by Goldman Sachs (Asia) L.L.C., and in Japan by Goldman Sachs (Japan) Ltd. This material is not for distribution to private customers, as defined by the rules of The Securities and Futures Authority in the United Kingdom, and any investments including any convertible bonds or derivatives mentioned in this material will not be made available by us to any such private customer. Neither Goldman, Sachs & Co. nor its representative in Seoul, Korea is licensed to engage in securities business in the Republic of Korea. Goldman Sachs. International or its affiliates may have acted upon or used this research prior to or immediately following its. publication. Foreign currency denominated securities are subject to fluctuations in exchange rates that could have an. adverse effect on the value or price of or income derived from the investment. Further information on any of the securities mentioned in this material may be obtained upon request and for this purpose persons in Italy should contact Goldman Sachs S.I.M. S.p.A. in Milan, or at its London branch office at 133 Fleet Street, and persons in Honge Kong should contact Goldman Sachs Asia L.L.C. at 3 Garden Road. Unless governing law permits otherwise, you must contact a Goldman Sachs entity in your home jurisdiction if you want to use our services in effecting a transaction in the securities mentioned in this material..  

Note: Options are not suitable for all investors. Please ensure that you have read and understood the current options disclosure document before entering into any options transactions..  

Emanuel Derman Deniz Ergener Iraj Kani  

We thank Yoshikazu Kobashi and Daisuke Toki for their interest and encouragement, and Alex Bergier and Barbara Dunn for their comments.  

# QUANTITATIVE STRATEGIES RESEARCH NOTES  

# SUMMARY  

This paper presents a method for replicating or hedging a target stock option with a portfolio of other options. It shows how to construct a replicating portfolio of standard options with varying strikes and maturities and fixed portfolio weights. Once constructed, this portfolio will replicate the value of the target option for a wide range of stock prices and times before expiration, without requiring further weight adjustments. We call this method static replication. It makes no assumptions beyond those of standard options theory.  

You can use the technique to construct static hedges for exotic options, thereby minimizing dynamic hedging risk and costs. You can use it to structure exotic payoffs from standard options. Finally, you can use it as an aid in valuing exotic options, since it lets you approx-. imately decompose the exotic option into a portfolio of standard options whose market prices and bid-ask spreads may be better known.  

Replicating an Exotic Option with a Portfolio of Standard Options.  

![](20ac61b564408a4dec1b6b7810138755b2a18795f1888ca0bf0293f129889316.jpg)  

The figure above, taken from an example in this paper, illustrates. how the technique works. The graph on the left shows the value of a. one-year up-and-out call, struck at 100 with out-barrier at 120, for all times to expiration and for market levels between 90 and 120. The. graph on the right shows the value of a replicating portfolio con-. structed from seven standard options, struck either at 100 or 120,. and expiring every two months over the one-year period. You can see that the replicating portfolio value approximately matches the target. option value over a large range of times and stock prices, and has the same general behavior. The more standard options you include in the replicating portfolio, the better the match..  

# Table of Contents  

Introduction  

First Steps Towards Replication4   
The Method of Static Replication in a Binomial World10 Options Valuation by Backward Induction10 The Principle of Static Replication .. 12 An Explicit Example: Static Replication of an Up-and-Out Call12   
Static Replication Strategy in the Real World17   
A Practical Example.... 22 Replicating an Up-and-Out Call. 22   
Appendix A: Some Exact Static Hedges27   
Appendix B: Mathematics of Static Replication34  

According to the Black-Scholes theory', a stock option at any instant behaves like a weighted portfolio of risky stock and riskless zero-coupon bonds. The Black-Scholes options formula tells you how to calculate the portfolio weights. They depend on the stock price level, the stock dividend yield, the stock volatility, the riskless interest rate and the time to expiration.  

Instead of owning an option, you can in principle own a portfolio of stock and riskless bonds, and achieve exactly the same returns. To do so, you must continuously adjust the weights in your portfolio accord-. ing to the formula as time passes and/or the stock price moves. This portfolio is called the dynamic replicating portfolio. Options traders ordinarily hedge options by shorting the dynamic replicating portfolio against a long position in the option to eliminate all the risk related to stock price movement.  

There are two difficulties with this hedging method. First, continuous. weight adjustment is impossible, and so traders adjust at discrete intervals. This causes small errors that compound over the life of the option, and result in replication whose accuracy increases with the frequency of hedging. Second, there are transaction costs associated. with adjusting the portfolio weights which grow with the frequency ofu. adjustment and can overwhelm the profit margin of the option. Traders have to compromise between the accuracy and cost..  

In this paper we describe a method of options replication that. bypasses some of these difficulties. Given some particular target. option, we show how to construct a portfolio of standard options, with varying strikes and maturities and fixed weights that will not require. any further adjustment and will exactly replicate the value of the target option for a chosen range of future times and market levels. We call this portfolio the static replicating portfolio..  

Our method relies only on the standard assumptions behind the Black-Scholes theory. Therefore, the value and sensitivities of the static replicating portfolio are equal to the usual theoretical value and sensitivities of the target option. You can use this static replicating portfolio to hedge or replicate the target option as time passes and the stock price changes. By increasing the number of options in the static portfolio, you can achieve better replication. The costs2 of.  

replication and transaction are embedded in the market prices of the standard options employed in replication..  

In this paper we apply the method only to options with one underlying stock. A similar extension to options with multiple underlyers is possible, but more involved..  

The static approach to options replication is useful in diverse areas, some of which we list below:.  

# 1. Trading  

You can use static replication to avoid the practical difficulties and. costs involved in dynamically hedging an options position. You can hedge long-term options with portfolios of short-term options, or exotic options with portfolios of standard options. Static replication is especially suited to hedging exotic high-gamma options which require frequent and costly dynamic hedging. A single static hedge can reduce potential risk over long periods of time and large ranges. of stock price.  

The static approach uses options to hedge other options positions over long periods of time. It is therefore naturally suited to managing books that contain large numbers of options, especially in liquid options markets.  

# 2. Structuring  

You can create a static replicating portfolio with the same payoff as an exotic option, perhaps at a reduced premium. You can even replicate target options of your own design that are not offered in the market.  

# 3. Valuation  

Static replication decomposes a target option into a portfolio of standard options. The market value of the portfolio provides a practical estimate for the fair value of a target option. This value. may reflect the true cost of the option more realistically than the usual theoretical value, especially in the presence of transaction. costs, volatility smiles, and other market conditions that violate the assumptions behind Black-Scholes.  

You can use the same method to specify a static hedge for a portfolio. of target stock (index) options, as well as for options on interest rates or currencies, though we will not consider those applications in this paper.  

# QUA NTITATIVE STRATEGIES RESEARCH NOTES  

The static replicating portfolio is not unique. You can use a variety of. static portfolios available to find one that achieves other aims as well - minimizing volatility exposure, for example. In some cases, it is possible to find a portfolio consisting of only a small number of options that provides a static hedge (see Appendix A). In general, a. perfect static hedge requires an infinite number of standard options. Even so, a static hedge portfolio with only several options can provide. adequate replication over a wide variety of future market conditions.  

Our approach differs from other attempts to statically hedge options..   
Some earlier methods have used an optimization strategy to mini-.   
mize the discrepancy between the target and replicating portfolio val-.   
ues over a range of market conditions. Others have focused on finding.   
static hedge portfolios in special cases where a small number of options can exactly replicate an exotic target option3.  

Our approach differs in principle: we can systematically specify, stepby-step, how to find a perfect portfolio that replicates a path-independent exotic option at all future stock price levels and times. In general this requires an infinite number of options. We can then use the same method with only a limited number of options to replicate the target option precisely at a limited number of stock prices and times. By increasing the number of options in the replicating portfolio we can increase the accuracy of replication. Often, a fairly small portfolio works adequately, and limits the transaction costs.  

This paper proceeds as follows. In the next section we investigate an intuitive approach towards replication. We then show how you can generalize this method to develop a comprehensive theory of replication. We then illustrate in detail how the method works in a binomial lattice world where only discrete stock price moves are allowed. Finally, we give some practical examples of static replicating portfolios for barrier options. In Appendix A, we present several static hedge portfolios consisting of only small numbers of options that nevertheless exactly replicate an exotic target option under special circumstances. Appendix B reviews the mathematics of static replication.  

# FIRST STEPS TOWARDS REPLICATION  

Barrier options' have high gamma when the underlying stock price is in the neighborhood of the barrier. In that region, dynamic hedging is both expensive and inaccurate, and static hedging is an attractive alternative. In this section we introduce our approach to static replication by trying to use standard (non-barrier) options to replicate an up-and-out European-style call option, described in Table 1.  

TABLE 1. An up-and-out call option.   


<html><body><table><tr><td colspan="2"></td></tr><tr><td>Stock price:</td><td>100</td></tr><tr><td>Strike:</td><td>100</td></tr><tr><td>Barrier:</td><td>120</td></tr><tr><td>Rebate:</td><td>0</td></tr><tr><td>Time to expiration:</td><td>1 year</td></tr><tr><td>Dividend yield:</td><td>5.0% (annually compounded)</td></tr><tr><td>Volatility:</td><td>25% per year</td></tr><tr><td>Risk-free rate:</td><td>10.0% (annually compounded)</td></tr><tr><td>Up-and-Out Call Value:</td><td>0.656</td></tr><tr><td>Ordinary Call Value:</td><td>11.434</td></tr></table></body></html>  

There are two different classes of stock price scenarios that determine the option's payoff:.  

1. The stock price does not hit the barrier before expiration. In this case, the up-and-out call has the same value as an ordinary call. with strike equal to 100.   
2. The stock price hits the barrier before expiration. Then the up-. and-out call is extinguished and has zero value.  

These are displayed in Figure 1 below.  

![](7d92e7f85fae7bd89bbad0c2891c5e702c813718c52c9d0ffa67ee0c407f90d2.jpg)  
FIGUre 1. Stock price scenarios for an up-and-out European call option with strike ${\bf K}={\bf100}$ and barrier $\mathbf{\bar{B}}=\mathbf{1}2\mathbf{0}$  

From a trader's point of view, a long position in this up-and-out call is. equivalent to owning an ordinary call if the stock never hits the barrier, and owning nothing otherwise. Let's try to construct a portfolio. of ordinary options that behaves like this..  

First we replicate the up-and-out call for scenarios in which the stock price never reaches the barrier of 120 before expiration. In this case,.   
the up-and-out call has the same payoff as an ordinary one-year.   
European-style call with strike equal to 100. We name this call Port-.   
folio 1, as shown in Table 2. It replicates the target up-and-out call.   
for all scenarios which never hit the barrier prior to expiration..  

<html><body><table><tr><td colspan="6">IABLE 2. Portfolio 1. Its payoff matches that of an up-and-out call if thebarrierisnevercrossedbeforeexpiration.</td></tr><tr><td>Quantity</td><td>Type</td><td>Strike</td><td>Expiration</td><td>Value1yearbeforeexpiration</td><td></td></tr><tr><td rowspan="2">1</td><td>call</td><td>100</td><td></td><td>Stock at 100</td><td>Stockat120</td></tr><tr><td></td><td></td><td>1 year</td><td>11.434</td><td>25.610</td></tr></table></body></html>  

The value of Portfolio 1 at a stock level of 120 is 25.610, much too large when compared with the zero value of the up-and-out call on. the barrier. Consequently, its value at a stock level of 100 is 11.434,. also much greater than the value (0.657) of the up-and-out call..  

Portfolio 1 replicates the target option for scenarios of type 1. By adding a suitable short position in just one extra option to Portfolio 1, we can attain the correct zero value for the replicating portfolio at one definite future time on the barrier at a stock price of 120. Let's choose to do this one year from expiration by cancelling the previous portfo-. lio value of 25.610 at a stock price of 120 with one year to expiration. Table 3 shows Portfolio 2, consisting of a single one-year 100 strike standard call (that is, Portfolio 1) plus a short position in 1.866 oneyear calls struck at 120. The 120 strike call has no payoff at expira-. tion below the barrier, and therefore doesn't alter the replication for scenarios of type 1 already achieved by Portfolio 1. Any strike greater than 120 would achieve the same goal..  

Here's the reason we choose to go short 1.866 120 calls. The theoretical value of the 100 call at a stock price of 120 with one year to expiration in Table 2 is 25.610. The theoretical value of the 120 call is 13.721. By going short $25.610/13.721=1.866$ call options struck at 120, we can cancel the theoretical value of the 100 call on the 120 barrier with one year to expiration, and so ensure that Portfolio 2 will. have zero value on the 120 barrier.  

Portfolio 2 replicates the value of the up-and-out call (1) at expiration below the barrier, and (2) exactly on the 120 barrier at one year prior. to expiration. Table 3 shows that its value when the stock is at 100 is 2.832, which is larger than the up-and-out call value of 0.657 at the. same market level. This excess value reflects the fact that the value of Portfolio 2 is zero on the barrier only at one year before expiration, whereas the up-and-out call's value is zero on the barrier at all times.. Figure 2 shows the value of Portfolio 2 on the 120 barrier at all times prior to expiration. You can see that its value deviates more dramatically from the zero value of an up-and-out call on the barrier as expi-. ration approaches.  

TABLE 3. Portfolio 2. Its payoff matches that of an up-and-out call if the barrier is never crossed, or if it is crossed exactly 1 year before expiration.   


<html><body><table><tr><td>Quantity</td><td>Type</td><td>Strike</td><td>Expiration</td><td colspan="2">Value 1 year before expiration</td></tr><tr><td></td><td></td><td></td><td></td><td>Stock at100</td><td>Stock at 120</td></tr><tr><td>1.000</td><td>call</td><td>100</td><td>1 year</td><td>11.434</td><td>25.610</td></tr><tr><td>-1.866</td><td>call</td><td>120</td><td>1 year</td><td>-8.602</td><td>-25.610</td></tr><tr><td>Net</td><td></td><td></td><td></td><td>2.832</td><td>0.000</td></tr></table></body></html>  

![](1938d56e6b9756353a3a4ef060ed059b5ee327b6b8b83763b8f741a0d6a7ff3f.jpg)  
FIGuRe 2. Value of Portfolio 2 on the barrier at 120.  

Portfolio 3 in Table 4 illustrates an alternative replicating portfolio. It adds to Portfolio 1 a short position in one extra option so as to attain the correct zero value for the replicating portfolio at a stock price of 120 with 6 months to expiration, as well as for all stock prices below the barrier at expiration. Figure 3 shows the value of Portfolio 3 for stock prices of 120, at all times prior to expiration. You can see that the replication on the barrier is good only at six months. At all other times, it again fails to match the up-and-out call's zero payoff.  

TABLE 4. Portfolio 3. Its payoff matches that of an up-and-out call if the barrier is never crossed, or if it is crossed exactly at 6 months to expiration.   


<html><body><table><tr><td>Quantity</td><td>Type</td><td>Strike</td><td>Expiration</td><td colspan="2">Value 6 months before expiration</td></tr><tr><td></td><td></td><td></td><td></td><td>Stockat100</td><td>Stockat120</td></tr><tr><td>1.000</td><td>call</td><td>100</td><td>1 year</td><td>7.915</td><td>22.767</td></tr><tr><td>-2.387</td><td>call</td><td>120</td><td>1 year</td><td>-4.446</td><td>-22.767</td></tr><tr><td>Net</td><td></td><td></td><td></td><td>3.469</td><td>0.000</td></tr></table></body></html>  

![](db6100fc5bacb0bdd48edd81f524e6665cf3b2a36faf9df63f5609cb92d8ecc6.jpg)  
FIGuRe 3. Value of Portfolio 3 on the barrier at 120.  

By adding one more call to Portfolio 3, we can construct a portfolio to. match the zero payoff of the up-and-out call at a stock price of 120 at both six months and one year. This portfolio, Portfolio 4, is shown in. Table 5.  

IABLE 5. Portfolio 4. Its payoff matches that of an up-and-out call if barrier is never crossed, or if it is crossed exactly at 6 months or 1 year to expiration.   


<html><body><table><tr><td>Quantity</td><td>Type</td><td>Strike</td><td>Expiration</td><td colspan="2">Value for stock price = 120</td></tr><tr><td></td><td></td><td></td><td></td><td>6months</td><td>1 year</td></tr><tr><td>1.000</td><td>call</td><td>100</td><td>1 year</td><td>22.767</td><td>25.610</td></tr><tr><td>-2.387 0.752</td><td>call call</td><td>120 120</td><td>1 year 6months</td><td>-22.767 0.000</td><td>-32.753 7.142</td></tr><tr><td>Net</td><td></td><td></td><td></td><td>0.000</td><td>0.000</td></tr></table></body></html>  

The value of Portfolio 4 on the barrier at 120 for all times prior to expiration is shown in Figure 4. You can see that this portfolio does a much better job of matching the zero value of an up-and-out call on the barrier. For times between zero and six months the boundary value at a stock price of 120 remains fairly close to zero.  

![](71418afcdc77bc805afa4e60e0beefe584ebe9f505e2c0b6a56c43bd9d141a23.jpg)  
FIGuRe 4. Value of Portfolio 4 on the barrier at 120.  

By adding more options to the replicating portfolio, we can match the value of the target option at more points on the barrier. Figure 5 shows the value of a portfolio of seven standard options at a stock level of 120 that matches the zero value of the target up-and-out call on the barrier every two months. You can see that the match between the target option and the replicating portfolio on the barrier is much improved. In the next section we show that improving the match on the boundary improves the match between the target option and the portfolio for all times and stock prices.  

![](f6def69db2878ae586b134b2410655d3d8a6fd80bc3dfbe234be41f04b361569.jpg)  
FlGure 5. Value on the barrier at 120 of a portfolio of standard options that is constrained to have zero value every two months.  

# THE METHOD OFSTATIC REPLICATIONIN A BINO MIAL WORLD  

We will now show how you can statically replicate a target option.   
with a portfolio of other options for all times and all market levels.   
Our method relies on the theory of options valuation..  

Because its results are easy to visualize, we will employ the binomial method of options valuation to illustrate our replication strategy. In. the binomial method, time passes in quantized steps. At each step. the stock price is allowed to move up or down a fixed amount. In the limit where the time steps and the stock moves become smaller and. smaller, the imaginary world of the binomial method approaches a. model in which stock prices change continuously and are distributed lognormally, and its options pricing formula becomes equivalent to. the Black-Scholes solution'.  

The binomial method is not a different model from the Black-Scholes model. It is an alternative way of solving the same options model that at the same time provides a clear visual picture. We now proceed in this framework.  

Imagine you have a binomial tree of stock prices with a finite number of time periods between today and expiration. We will show how to replicate an arbitrary target option with a portfolio of other options so that, at every time and stock price allowed in the binomial model, the replication is exact.  

# Options Valuation by Backward Induction  

In the binomial method, we value derivative securities with uncertain future payoffs by backward induction in a risk-neutral world. The method is illustrated in Figure 6 for options on stock..  

There are three components to the method:  

1. The risk-neutral binomial tree. This is a tree of stock prices constructed so that the mean stock price grows with time like the forward stock price. This constraint follows from the assumption that options can be hedged with stock.  

# QUA NTITATIVE STRATEGIES RESEARCH NOTES  

2. The boundary conditions. These are the values of the option on some boundary in the future where its value is determined (for. example, by the option's terms) at each stock price node on the. boundary. The values of the option everywhere inside the bound-. ary are uniquely determined by these boundary values..  

3. The backward equation. This is the formula for computing all ear-. lier option values from the boundary option values by moving. backwards down the tree. In mathematical form, the equation rep-. resents the statement that a hedged position must earn the same instantaneous return as a riskless money-market account. In the limit of infinitesimally small time steps and stock moves, the back-. ward equation becomes the Black-Scholes equation..  

![](5ed9847fb351b62c2a6ef98875d4c6c0e70ed6b15586a4cb43fadfe61490ef62.jpg)  
FIGURe 6. The method of backward induction.  

The risk-neutral binomial tree depends only on interest rates, the current stock price, the stock volatility and the stock dividend yield. The backward equation is the same for all securities whose values. are contingent on the stock price. Only the boundary condition differs from security to security. If two different portfolios have the same values everywhere on the boundary, and produce the same cashflows inside this boundary, the backward equation dictates that they will.. have the same values everywhere inside the boundary. This leads to the principle of static replication.  

# The Principle of Static Replic ation  

You can replicate a target security for all future stock prices and. times within some boundary by constructing a portfolio of securities. with the same net cashflows within this boundary and the same net values on the boundary.  

# An Explicit Example: Static Replication of an Up-and-Out Call  

Let's illustrate how this works. In order to concentrate on the essence of the method, we'll make certain simplifying assumptions. Dropping these assumptions does not invalidate our method; it just makes the explanation less transparent. So, we assume that interest rates and stock dividend yields are zero, and that the stock is worth 100 today. We also assume that the stock price can move up or down 10 with equal probability (of 1/2) only at the end of each year. Figure 7 shows the binomial tree of stock prices for this stock in the risk-neutral world over the next five years.  

![](241901b4d24334fc451223cd8b5fc9224bbcacdbd4f11b37ea8e5bfa084b947d.jpg)  
FIGURE 7. A binomial tree of stock prices in dollars. Up and down moves have equal probability.  

Let's choose a five-year up-and-out European-style call with a strike.   
of 70 and a knockout barrier of 120 as the target barrier option we'll.   
try to replicate. This option has a natural boundary at expiration in five years, where it expires, and on the knockout barrier at 120.   
These boundaries are shown in Figure 8..  

![](59817dcfcb0f5fb31d6dff9ef9a9544e8046f74479a6b45766fee9d9268e1e78.jpg)  
FIGurE 8. A binomial tree of call prices for a five-year European-style up-and-out call with strike at 70 and barrier at 120. The corresponding stock prices at each node are shown in Figure 7.  

For those scenarios in which the stock price reaches expiration in year 5 without having touched the knockout boundary, the call has the payoff of an ordinary call. Its boundary value on each node in the heavily shaded expiration boundary in Figure 8 is  

$$
{\mathrm{call~value}}=m a x\left(S-70,0\right)
$$  

At all nodes on the knockout boundary at a stock level of 120, the call is worth zero.  

# QUANTITATIVE STRATEGIES RESEARCH NOTES  

At earlier times the value of the call is given by the formula  

$$
C=\frac{C_{u}+C_{d}}{2}
$$  

Equation 2 is the backward equation familiar to users of binomial. models. $C_{u,d}$ denotes the call value at the up and down nodes one. year in the future.. $(C_{u}+C_{d})/2$ is the expected value of the call, and. since we have chosen interest rates to be zero for pedagogical simplicity, there is no need to discount the expected value. You can check to see that the value of the call at each earlier node in the tree, below the knockout boundary and before expiration, is obtained by using. this equation to work backwards in time through the tree. If we constructed stock and option trees with smaller and smaller time periods between successive levels, Equation 2 would become equivalent to the Black-Scholes equation. The up-and-out call is worth $\$11.88$ today in this simplified binomial world with one-year steps.s.  

How can you replicate this up-and-out call with ordinary options? You need to create a portfolio of ordinary options that have the same payoff on the boundaries. The four trees in Figure 9 illustrates the procedure we use. The boundary on which we want to match the value of the up-and-out option is shown as a heavy grey line. Tree 1 is the tree of binomial stock prices. Tree 2 is the tree for a replicating portfolio that matches the target option's payoff on the expiration boundary. Tree 3 is the tree for a portfolio that also matches the payoff at one point on the knockout boundary. Finally, Tree 4 shows the perfect replicating portfolio that matches the target option's payoff on all boundaries, and therefore at every node inside the boundary as well.  

Tree 1 shows the stock prices at each node. Tree 2 shows the value of an ordinary 5-year call struck at 70. It has the same values as the upand-out call of Figure 8 at expiration in year 5 at all nodes below the. barrier of 120. Therefore, this ordinary call replicates the up-and-out call perfectly if the barrier is never struck. However, the ordinary call has a value of 50 at those stock nodes labeled A and B that correspond to stock prices of 120 in year 2 and year 4. In contrast, the upand-out call has zero value at those nodes.  

![](d4b54324a1c26f33a2bdb91dbbc38c49acc91c6814625b149d8436a180da55dd.jpg)  
FIGUre 9. Replicating an up-and-out call with a portfolio of ordinary calls.  

By adding a short position in 10 5-year calls with a strike of 120 to the portfolio in Tree 2, the portfolio value can be made zero at node A. This portfolio is shown in Tree 3. Because the strike of the new calls is not below 120, it expires out-of-the-money if the barrier is never struck. Therefore, it does not spoil the replication already achieved on the expiration boundary in year 5. However, this portfolio now has a value of -25 at stock node B, in contrast to the zero value of the upand-out call option at the same node.  

To alter the value of -25 at node B to zero, we need to achieve a portfolio value of -15 at node C in Tree 3. Since node C has a portfolio value of $^{-65}$ , we must add 50 to the portfolio value there. We can achieve this by adding a long position in 5 three-year calls struck at 120 to the portfolio. Because the strike of these new calls is not below 120, they do not spoil the replication already achieved below the knockout barrier. This new portfolio is shown in Tree 4.  

You can see that the portfolio we have constructed in Tree 4 has values on the nodes of the knockout boundary which exactly match those of the up-and-out call in Figure 8. Consequently, the values obtained from the backward equation at all earlier nodes inside the boundary also have the same values as those of the up-and-out call.  

Let's summarize what we've done. Our target option was an up-andout call. We defined the boundary to be the collection of nodes on the out barrier and at expiration. We noticed that an ordinary call with the same strike would produce the same values as the up-and-out call at expiration, but different values on the out barrier. We were then systematically able to correct the values on the out barrier by. adding positions in calls struck at the barrier with earlier expirations. In this way, we reproduced the value of the up-and-out call at all nodes on the boundary. The result was perfect replication in this binomial world. There was nothing unique about the portfolio we. chose; we could have used calls with a strike greater than 120 to achieve the cancellation on the out barrier..  

We can use this technique to match the boundary node values of any target option, using a replicating portfolio of as many ordinary options as are necessary. On boundaries above the current stock price we need to use calls with strikes on or above that boundary. This ensures that the calls in the replicating portfolio will have no payoff below the boundary, and so will not ruin the replication already achieved within the boundary. Similarly, on boundaries below the current stock price, we must use puts with strikes on or below the boundary.  

In the next section we show how to apply this method when we are no longer working in the binomial framework..  

# STATIC REPLICATION STRATEGY IN THE REAL WORLD  

In the previous section we showed how to replicate exactly an option in the binomial world. Because there are only a limited number of nodes on the binomial boundaries, you can replicate the target option exactly with a limited number of ordinary options. In the real world,. stocks trade more or less continuously, and so achieving exact replication in general will require a portfolio with an infinite number of ordinary options. Nevertheless, by constructing a portfolio that matches the target option's payoff at a well-chosen but limited set of boundary points, you can still achieve good replication everywhere. In this section we describe how to do this..  

Stock options contracts specify the payoff of the option under all possible future scenarios. Most contracts define the payoff on a time boundary at expiration and on a finite set of stock price boundaries which together surround the current value of the underlyer. These payoffs can be specified in terms of cash, stocks or options themselves.  

The diagrams in Figure 10 illustrate some payoff boundaries. Each. diagram shows a boundary that completely surrounds the current stock price, in the sense that all stock price paths moving out into the. future from the current time and current stock price must terminate on that boundary. (In some cases there is a boundary at infinity that we don't show.)  

Figure 1O(a) shows the boundary for a call option. The terminal value of the call at expiration is given by max (stock price - strike, O). For a. European-style call, all stock paths ultimately hit this boundary. For an American-style call there is an early exercise boundary before expiration. Figure 10(b) shows the boundary for a down-and-in call. The payoff at expiration is zero if the barrier has never been hit. The. payoff on the in barrier is specified in terms of the value of the ordinary call that the down-and-in call converts to on that barrier.. Finally, Figure 10(c) shows a general payoff boundary. The values at. each point on it can be specified in terms of cash, stock or options. value.  

If you can replicate the value of a target option at each point on this.   
general boundary using a portfolio of ordinary call and put options,.   
without introducing additional payoffs or cashflows within the.   
boundary, then the value of the portfolio must be the same as the value of the target option..  

![](ef125c29d63644943d36af43271bc11eab4a582d6138b46f34512f0764c326b8.jpg)  
FIGURE 10. Options boundaries: (a) ordinary call (b) European-style down-and-in call (c) general option..  

Figure 11 shows the options you can use to match the boundary val-. ues of the target option without introducing these extra cashflows. At each point on the boundary, use an ordinary option that expires at that time, and whose strike is determined in the following way. On. boundaries above the current stock value, use calls with strikes on or above the boundary. This prevents the call from having a payoff. within the boundary, and so altering the value of the option that has already been computed via the backward equation from future boundary values. Similarly, on boundaries below the current stock value, use puts with strikes on or below the boundary. Finally, on expiration-style boundaries that have a fixed-time, you can use calls or puts of any convenient strike..  

![](9fa92fd69af4c578647f66a23db18f19acb2d8fafb21a9c668b23bd8d8159727.jpg)  
FIGURE 11. Allowed strikes for options replication.  

In Figure 12 we illustrate how to construct a replicating portfolio that matches the target option's value on the boundary for a series of discrete times $t_{1},t_{2}.$ . out to expiration $t_{e x p}.$ We first look at the expiration boundary and match the payoff of the target option there with a portfolio consisting of a combination of European-style calls and/or puts with different strikes that expire at that time. This is our initial replicating portfolio that takes care of replication at expiration.  

Moving back one time step before expiration ( $t_{4}$ in Figure 12), we can compute the theoretical value of the initial replicating portfolio at time $t_{4}$ at the boundary stock price $\mathrm{{U_{4}}}$ . In general, this theoretical value will not match the boundary value of the target option when. the stock price is $\mathrm{{U_{4}}}$ . You can now add a position in ordinary calls. with expiration at $t_{e x p}$ and strike at or above. $\mathrm{U_{exp}}$ to the initial replicating portfolio. You must choose these calls such that their theoreti-. cal value, when added to the theoretical value of the initial portfolio at stock price $\mathrm{{U_{4}}}$ and time $t_{4},$ yields the value of the target option at stock price $\mathrm{{U_{4}}}$ . The corrected replicating portfolio then consists of the. initial replicating portfolio plus the position in these new calls. These new calls expire out of the money below stock levels of $\mathrm{U_{exp}}.$ and therefore do not alter the cash position at time $t_{e x p}$ in the portfolio of calls and puts that already replicate the target option at expiration..  

![](d8c3792fd5baee9820dd28e64e55081eeba89479a60e8727be7ab8cbbf618260.jpg)  
FIGUre 12. Replicating the payoff of an option at discrete times.  

Similarly, by adding an appropriate position in puts with strike at or below $\mathbf{L}_{\mathrm{exp}}.$ you can make the replicating portfolio have the appropriate boundary at a stock price of. $\mathrm{L}_{4}$ at time $t_{4}$ The addition of these. puts to the replicating portfolio will not affect the replication already achieved on the boundary at expiration, because they expire out of the money at this stock price level..  

You can now move back to time $t_{3},$ and in the same way add more calls and puts with expiration $t_{4}$ to the replicating portfolio to ensure that it matches the target option's boundary values at time. $t_{3}$ . Again, you must be careful to choose calls with strikes above the upper boundary and puts with strikes below the lower boundary..  

By repeating this procedure at times $t_{2}$ and $t_{I}$ you can create a static replicating portfolio that has the same value as the target option at all of these chosen times on the boundaries, and at expiration.  

In principle, you can match the target option payoffs at as many points on the boundary as you like. The more points you match, the better the replication. If you were to use an infinite number of options in the target portfolio, you could match the payoff everywhere on the boundaries. The target portfolio would have exactly the same value as the static portfolio at all times and all stock prices, as long as interest rates, volatilities and other parameters that appear in the model did not change. In the next section we demonstrate some practical results that show how well you can do with a small number of options in the replicating portfolio.  

There are several features of the static replicating portfolio that are worth noting:  

You can find a static replicating portfolio for options with rather. complicated boundaries, as long as all boundary payoffs are known.   
The boundaries on which the payoffs are known need not be the actual boundaries of the target option. For example, you don't have to choose the lower boundary to be the knock-in barrier when replicating a knock-in call; you can instead choose to match its value at some higher stock price at which the value of the knock-in call is known.   
If you are using a static portfolio to replicate some target option,. you must unwind the portfolio when the stock price hits any boundary, trading out of it and into the security (cash, stock or option) that produces the target option's value on that boundary. Theoretically, this unwinding and replacement is costless.  

# A PRACTICAL EXAMPLE  

In this section we give some examples of static replicating portfolios for some exotic equity options.  

# Replicating an Up-andOut Call  

Consider the up-and-out European-style call option defined in Table 6. Its theoretical value with one year to expiration is 1.913. We can use. our method to construct a static replicating portfolio. Table 7 shows one particular example. It consists of a standard European-style call option with strike 100 that expires one year from today, plus six additinal options each struck at 120. The 100-strike call replicates the payoff at expiration if the barrier is never struck. The remaining six options. expire every two months between today and the expiration in one year. The position in each of them is chosen so that the total portfolio value is exactly zero at two month intervals on the barrier at 120.  

TABLE 6. An up-and-out call option.   


<html><body><table><tr><td colspan="2"></td></tr><tr><td>Stock price:</td><td>100</td></tr><tr><td>Strike:</td><td>100</td></tr><tr><td>Barrier:</td><td>120</td></tr><tr><td>Rebate:</td><td>0</td></tr><tr><td>Time to expiration:</td><td>1 year</td></tr><tr><td>Dividend yield:</td><td>3.0% (annually compounded)</td></tr><tr><td>Volatility:</td><td>15% per year</td></tr><tr><td>Risk-free rate:</td><td>5.0% (annually compounded)</td></tr><tr><td>Up-and-Out Call Value:</td><td>1.913</td></tr></table></body></html>  

The theoretical value of the replicating portfolio in Table 7 at a stock price of 100, one year from expiration, is 2.284, about 0.37 or $19\%$ off from the theoretical value of the target option. Figure 13 shows the mismatch in value, in both dollar terms and in percentage of the value of the target option, between the theoretical value of the replicating portfolio and the target portfolio, over a range of stock prices as time passes. You can see that the replication in percentage terms is good to within $30\%$ over a large range of stock price and time. Near the barrier itself, the percentage mismatch becomes large, but it is a large percentage of a vanishing option value, so the actual dollar mismatch is small. The only region of large dollar mismatch is near the barrier, close to expiration.  

TABLE 7. The replicating portfolio.   


<html><body><table><tr><td>Quantity</td><td>Option Type</td><td>Strike</td><td>Expiration (months)</td><td>Value (Stock = 100)</td></tr><tr><td>0.16253</td><td>Call</td><td>120</td><td>2</td><td>0.000</td></tr><tr><td>0.25477</td><td>Call</td><td>120</td><td>4</td><td>0.018</td></tr><tr><td>0.44057</td><td>Call</td><td>120</td><td>6</td><td>0.106</td></tr><tr><td>0.93082</td><td>Call</td><td>120</td><td>8</td><td>0.455</td></tr><tr><td>2.79028</td><td>Call</td><td>120</td><td>10</td><td>2.175</td></tr><tr><td>-6.51351</td><td>Call</td><td>120</td><td>12</td><td>-7.140</td></tr><tr><td>1.00000</td><td>Call</td><td>100</td><td>12</td><td>6.670</td></tr><tr><td>Total</td><td></td><td></td><td></td><td>2.284</td></tr></table></body></html>  

Instead of using six options, struck at 120, to match the zero boundary value on the barrier every two months for one year, we can use 24 options to match the boundary value at half-month intervals. In that case, the theoretical value of the replicating portfolio becomes 2.01,. only O.10 away from the theoretical value of the target option. The behavior of the replicating portfolio over a range of stock prices and. times to expiration is shown in Figure 14. You can see that the portfolio value varies like that of an up-and-out option with barrier at 120. The replication mismatch is shown in Figure 15, and is clearly. smaller than in the case of replication with six options..  

![](bfe5b3c22ef2d0060c58ecc099b1cf41ef45e9d6bc5b6f8d42493011aaddfeb5.jpg)  

FIGUrE 13. The replication mismatch between the target option of Table 6 and the replicating portfolio of Table 7.  

# Call Value vs Stock Price and Time to Expiration  

![](18fff833f45d74bebd312d52c4d6d19b1c2289a64caf16bedb34f04369749ce0.jpg)  
FIGURE 14. Theoretical value of a 24-option replicating portfolio for the target option of Table 6.  

![](e2153744eafb92b7e5dc3fb82f97dc6fd801e7ad1e029fd2d8484753081b86f2.jpg)  
Re plic ation Error (\$)   
FIGURE 15. Replication mismatch between a 24-option replicating portfolio and the target option of Table 6..  

# APPENDIX A: SO ME EXACT STATIC HEDGES  

# A Down-and-Out Call with Barrier at the Strike and Forward Close to Sp ot  

Under certain circumstances, you can statically replicate a barrier option with a position in stocks and bonds alone, avoiding the need for options. We present and analyze several examples below.  

Consider a European down-and-out call option' with time $t$ to expiration on a stock with price. $S$ and dividend yield $^{d.}$ We denote the strike level by. $K$ and the level of the out-barrier by. $B.$ We assume in this particular example that $B$ and $K$ are equal. and that there is no. cash rebate when the barrier is hit. There are two classes of scenarios for the stock price paths: scenario 1 in which the barrier is avoided. and the option finishes in-the-money; and scenario 2 in which the barrier is hit before expiration and the option expires worthless.. These are shown in Figure 16..  

![](ce168b7b8d998b130d674d402465bd7f789db80d73afc8d17493f2ff1c921f98.jpg)  
FIGUrE 16. A down-and-out European call option with $B=K$  

In scenario 1 the call pays out $S^{\prime}{-}K$ , where $S$ 'is the unknown value of the stock price at expiration. This is the same as the payoff of a forward contract with delivery price $K.$ This forward has a theoretical value $F=S e^{-d t}-K e^{-r t}$ , where $^{d}$ is the continuously paid dividend yield of the stock. You can replicate the down-and-out call under all stock price paths in scenario 1 with a long position in the forward.  

For paths in scenario 2, where the stock price hits the barrier at any time $\iota^{\prime}$ before expiration, the call immediately expires with zero value. In that case, the above forward $F$ that replicates the barrier-. avoiding scenarios of type 1 is worth. $K{\bf e}^{-d t^{\prime}}-K{\bf e}^{-r t^{\prime}}$ . This matches the. option value for all barrier-striking times. $\iota^{\prime}$ only if $\boldsymbol{r}=d$ .So, if the.  

# QUANTITATIVE STRATE GIES RESEARCH NOTES  

riskless interest rate equals the dividend yield (that is, the stock forward is close to spot), a forward with delivery price $K$ will exactly replicate a down-and-out call with barrier and strike at the same level $K$ , no matter whether the barrier is struck or avoided.  

# Barrier Calls on a Stock with Large Volatility  

Let's look at a down-and-in call similar to the call above, but where the strike $K$ is above the barrier B. For very large volatility, the stock. price is almost certain to hit the barrier, as shown in Figure 17..  

![](4ba139853c5bdd2632102f883fa1f0e70621b90b6986beb3cbae20968346645b.jpg)  
FIGUre 17. A down-and-in European call with large volatility.  

When the stock price hits the barrier, $S$ equals $B$ and the down-andin call becomes an ordinary call with large volatility. It's value is then $B{\mathrm{e}}^{-{\mathrm{d}}t}$ , because owning a call on a stock with very large volatility is equivalent in value to a long stock position less the dividends paid during the option's lifetime. So, the down-and-in call's value is $B{\stackrel{}{\ e^{-}}}{}^{d t}$ You can replicate it before the stock price hits the boundary by owning $B\mathrm{e}^{-\mathrm{d}t}$ dollars. When the stock price hits the barrier, the static replicating portfolio will have a theoretical value large enough to fund the purchase of an ordinary call with strike $K.$  

Now look at a down-and-out call. It is equivalent to a long position in. an ordinary call with the same strike and a short position in a downand-in call with the same strike and barrier'. When volatility is. large, the ordinary call is worth. $S e^{-d t}$ and the down-and-in call is worth $B e^{-d t}$ . So, the down-and-out call has a value $S e^{-d t}-B e^{-d t}$ . You can statically replicate it by buying. ${\bf e}^{-d t}$ shares of stock and shorting $B{\stackrel{}{e}}^{-d t}$ dollars.  

# Barrier Puts on a Stock with Large Volatility  

Similarly, you can statically replicate barrier puts with stock when volatility is very large. The argument is a little more subtle than the one for calls, and is illustrated in Figure 18..  

![](5dccae3c47e2364c458920ccbe4cec190e008bc683c5de5e4a7a257fe91649df.jpg)  
FIGURE 18. A European barrier put with large volatility.  

Let's first look at an up-and-out put with strike $K,$ and with barrier. $B$ above the strike. At very high volatilities, there are only two possibil-. ities for the stock price, as shown in Figure 18: it will either rapidly. move up and hit the out-barrier or move down and stop at zero stock. price, which is effectively also a barrier. The value of the up-and-out put at stock price $S$ is the average of its values at zero stock price and the barrier $B$  

If $B$ is an out-barrier, the put will be worth zero there. At zero stock price a high-volatility Black-Scholes put is worth exactly $K e^{-r t}$ , the present value of the strike.  

To calculate the average value you need the probabilities of reaching either barrier. At very high volatilities the lognormal distribution of stock prices assumed in the Black-Scholes model becomes flat, and so the probability of not reaching one barrier is proportional to how close the stock is to the other barrier. The probability $p_{B}$ of hitting $B$ is therefore proportional to the "distance" between the current stock price and zero stock price, that is $S.$ Similarly, the probability $p_{O}$ of hitting zero stock price is proportional to the "distance" between $S$ and $B$ that is $(B\mathrm{~-~}S)$ . Because the probabilities must add to one, $p_{B}=S/B$ and ${p_{0}}=(B-S)/B$ , as shown in Figure 18.  

The value of the up-and-out put is given by the average  

$$
p_{B}\times0+p_{0}\times K=K e^{-r t}\big(1-S/B\big)
$$  

This shows that you can replicate the up-and-out put when volatility is very high by a long position in a zero-coupon bond with a face of $K$ dollars and a short position in $K e^{-r t}/B$ shares of stock.  

Now let's look at an up-and-in put. An up-and-in put is equivalent to. a long position in an ordinary put combined with a short position in. the up-and-out put. At high volatility the ordinary put has value $K e^{-r t}$ . So, the value of the up-and-in put is given by the value of Equa-. tion 3 less $K e^{-r t}$ , that is $K\mathbf{e}^{-r t}(S/B)$ . This shows that you can replicate the up-and-in put with high volatility via a long position in. $K e^{-r t}$ shares of stock.  

# Barrier Calls on a Stock with Finite Volatility.  

We are indebted to Peter Carr of Cornell University for the example below3.  

Let's look at a European-style down-and-in call option with strike $K$ and barrier $B$ where the barrier is below the strike. In Figure 19 we illustrate the stock price $S,$ the strike $K,$ the barrier $B$ and another strike $K^{\prime}$ somewhere below the barrier.  

![](2c2a4b75b3da05bf367570d0f977a8434080eb20fce12c89c6883a1ca6488eb6.jpg)  
FIGUrE 19. Behavior of a down-and-in European call with $\mathbf{B}<\mathbf{K}$  

Again, there are again two classes of scenarios that determine the value $C_{K I}$ of the knock-in call:  

1. The stock price never hits the barrier B before expiration. In that case, whether the stock price finishes above or below the strike, the knock-in call expires worthless and $C_{K I}=O.$   
2. The stock price hits the barrier B when the remaining time to expiration is $t.$ The down-and-in call knocks in to become an ordinary call with strike $K$ and value $C(B,K,r{d},\ensuremath{\mathrm{{\sigma}}},{\ t})$ where $C(S,K,r{d,\mathrm{{\sigma}}},t)$ is the value of a Black-Scholes call with stock price $S_{\it:\/\/}$ strike $K$ riskless rate $\pmb{r}$ dividend yield $d_{\mathrm{:}}$ volatility $\upsigma$ , and time to expiration $t.$  

These values of the knock-in call for each of these scenarios are shown in Figure 19.  

Is there some other security you can buy in advance that will have the same value under each scenario?.  

First look at scenario 1 in which the stock price has never hit the barrier. At expiration, $S$ is greater than. $B$ and the value of the call is. zero. Any put with strike $K$ below the barrier. $B$ will expire out of thes. money in this region, and also have zero value. Let. $P(S,K^{\prime},d,\mathrm{{\sigma}},t)$ be the value of this put with strike. $K^{\prime}$ and time to expiration t. You can. use this put to replicate the down-and-in call for stock paths that never hit the barrier..  

Now, suppose you try to use some number. $_n$ of these puts to replicate the down-and-in call for scenario 2 as well. In scenario 2 the stock price hits the barrier at some time. $t$ before expiration. Then the puts are worth $\pmb{n}\times\pmb{P}(\pmb{B},\pmb{K}^{\prime},\pmb{r},\pmb{\upsigma},t)$ In contrast, the down-and-in call has. knocked in and has a theoretical value. $C(B,K,r,\mathrm{{\sigma}},t).$ Suppose you can choose the strike $K^{\prime}$ such that the puts have the same value as the. call. Then this put portfolio will statically replicate the knock-in call for all scenarios.  

Under certain conditions there is an appropriate value of $K$ .You need a value of $K^{\prime}$ such that the put portfolio and the call have the same value on the knock-in boundary, that is  

$$
C(B,K,r,d,\mathbf{\upsigma},t)=\mathbf{\upsigma}_{n}\times P(B,K^{\prime},r,d,\mathbf{\upsigma},t)
$$  

There are two symmetries of the Black-Scholes formula for calls and puts that we can use to find a $K$ and an $_n$ that solve Equation 4. First, a call on stock is the right to exchange a zero-coupon bond for stock. This exchange option can alternatively be written as a put on the bond, and so,  

$$
C(B,K,r,d,\mathrm{{o}},t)=P(K,B,d,r,\mathrm{{o}},t)
$$  

Second, when stock prices evolve lognormally, the same proportional. increase in stock price and strike produces a similar increase in option price:  

$$
P(K,B,d,r,\mathbf{\sigma},t)=\mathbf{\delta}m\times P\Big(\frac{K}{m},\frac{B}{m},d,r,\mathbf{\sigma},t\Big)
$$  

# QUA NTITATIVE STRATEGIES RESEARCH NOTES  

Then,  

$$
\begin{array}{l}{{C(B,K,r,d,\mathbf{\upsigma},t)=P(K,B,d,r,\mathbf{\upsigma},t)}}\ {{\mathrm{~}=\displaystyle\frac{K}{B}\times P\Big(B,\frac{B^{2}}{K},d,r,\mathbf{\upsigma},t\Big)}}\end{array}
$$  

where the first step follows from Equation 5 and the second step follows from Equation 6 with. $m=K/B$  

If you compare Equation 7 with Equation 4, you can see that they are identical except for a switch in the roles of $\pmb{r}$ and $^{d.}$ If $\scriptstyle r=d$ , then thet switch makes no difference, and Equation 4 can be satisfied with. $\mathbf{n}~=~K/B$ and $K^{\prime}=B^{2}/K$  

This means that if. $\scriptstyle r=d$ , that is if forward is equal to spot for the stock, then you can statically replicate a down-and-in European call by means of $\mathbf{\delta}_{n}~=~K/B$ ordinary puts struck at $B^{2}/K$ . The put replicates the knock-in call in the following sense. Before knock-in, it has exactly the same value for all stock prices. If no knock-in occurs before expiration, it has the same terminal value. Finally, at knockin, it has exactly the same value as the call into which the knock-in is transformed. Therefore, assuming negligible transaction costs and no change in interest rates or volatility since the initial options position, you can trade out of the put and into the knocked-in call with zero cost.  

In Figure 19 we assume that the barrier $B$ is below the strike $K.$ Only in that case does the put with strike $K^{\prime}$ replicate the down-and-in call value on the barrier (scenario 1) and also have zero value at expira-. tion if the barrier is never struck (scenario 2). Had the barrier been above the strike, the put would have replicated the down-and-in call under scenario 1, but not under scenario 2.  

Similarly, when $\scriptstyle r=d$ , you can replicate an up-and-in put with bar-. rier $B$ above the strike $K$ by means of. $\textbf{\em n}=\textbf{\em K}/B$ calls struck at $B^{2}/K$ A single call can match the value of the knock-in put on the barrier and at expiration only when the barrier is below the strike..  

# APPENDIX B: MATHEMATICS OF STATIC REPLICATION  

In this section we will present some mathematical concepts regard-. ing the static replication of options. We assume that there is a single source of uncertainty driving the stock price process represented by. the Wiener process $Z(t)$ in terms of which the stock evolution is. given by  

$$
\frac{d S}{S}=r d t+\upsigma d Z
$$  

Let $\Gamma(S,T-t)$ denote the value at time $t$ of a claim contingent on stock price $s$ , defined in terms of its payoff on the boundary of a proper region in $(S,t)$ -plane containing today's stock price and time. We will assume' that the stock prices at the boundary $S_{\partial\Omega}$ can be (locally) parametrized by means of some sufficiently regular function of physical time $B(t)$ for all time t except possibly at expiration $T$ Working in the continuous theory, our objective is to find a representation of the value of the contingent claim's value $\Gamma(S,T-t)$ at any instant of time $t$ and stock price $S$ as the weighted average of values of a set of standard options as follows:  

$$
\Gamma(S,T-t)=\int_{t}^{T}\mathrm{\alpha}(t,u)C(S,K(u),u-t)d u
$$  

where $C(S,K,\uptau)$ denotes the value of a standard (call or put) option with strike price $K$ and maturity $\pmb{\uptau}$ . The form of the weighting function $\mathrm{\bf\Phi}\mathrm{\bf\Phi}\mathrm{\bf\Phi}\mathrm{\bf\Phi}\mathrm{\bf\Phi}\mathrm{\bf\Phi}\mathrm{\bf\Phi}\mathrm{\bf\Phi}$ and the strike price function $K(\uptau)$ is so far unspecified but can be restricted. Since we are interested in the static replication the weights. $\alpha(\ t,\tau)$ must be independent of the initial time $t$  

$$
{\frac{\partial}{\partial t}}\alpha(t,\uptau)=0\qquad{\mathrm{for~}}\uptau>t
$$  

Hence we can drop the parameter $t$ and use the simpler notation $\upalpha(\uptau)$ for the static weight function. We will also assume that the strike prices $K(\uptau)$ coincide with the boundary levels $B(\uptau)$  

# QUA NTITATIVE STRATE GIES RESEARCH NOTES  

$$
K(\uptau)=B(\uptau)\qquad{\mathrm{for~}}\uptau>t
$$  

As described in the text, this assumption is sufficient, but not necessary to guarantee that there are no redundant cashflows generated by the hedging vehicles within the boundary $\partial\Omega$ . Altogether we have the following relation:  

$$
\Gamma(S,T-t)=\int_{t}^{T}\alpha(u)C(S,B(u),u-t)d u
$$  

In many cases of interest the payoff at expiration of the given claim. $\Gamma(S,0)$ is a discontinuous function. This means that the weighte $\upalpha(T)$ corresponding to the expiration is infinite and has the form of a Dirac delta function. In these cases we can separate the terminal. weights and express Equation 12 in the generalized form:.  

$$
\Gamma(S,T-t)=\int_{t}^{T}\mathrm{\L}\mathrm{d}\tau\L(S,B(u),u-t)d u+\mathrm{\L}\alpha_{T}C_{T}(S,B(T),T-t)
$$  

in which $C_{T}(S,B(T),T-t)$ formally represents the totality of all hedging standard options necessary to hedge the terminal payoff of the claim and ${\bf{{a}}}_{T}$ represents collectively the respective weights.  

Let $\xi(t)$ be the known value (payoff) of the contingent claim on the boundary point at time $t$  

$$
\S(t)=\Gamma(B(t),T-t)
$$  

Evaluating Equation 13 on the boundary points would then lead to the identity:  

$$
\boldsymbol{\upxi}(t)=\int_{t}^{T}\mathrm{d}(\boldsymbol{u})C(\boldsymbol{B}(t),\boldsymbol{B}(\boldsymbol{u}),\boldsymbol{u}-t)d\boldsymbol{u}+\alpha_{T}C_{T}(\boldsymbol{B}(t),\boldsymbol{B}(T),T-t)
$$  

We can solve Equation 15 recursively for the weights. This is done by first determining the terminal weights. ${\bf{{a}}}_{T}$ by matching the contingent claim's terminal payoff with an appropirate collection of standard options with expiration $T$ . It is a simple matter to show that the. terminal weights can always be determined in this manner. Then  

Equation 15 is used recursively to find the weights for hedges with smaller expirations.  

A discrete time solution of Equation 15 would begin with dividing the time interval $(t,T)$ into a set of equally spaced time points $t=t_{0},t_{1},t_{2},\dots t_{N}=T$ We will denote the weights at these time points respectively as $\mathbf{a}_{0},\mathbf{a}_{1},...\mathbf{a}_{N}$ . We will use the similar index notation for other quantities of interest to us as well. Note that $\upalpha_{N}$ denotes collectively the set of terminal weights which, as mentioned earlier, can be determined easily from matching the terminal payoff of the contingent claim with a portfolio of standard options with expiration $T$ Evaluating Equation 15 at time $t_{N-2}$ would then give:.  

$$
\begin{array}{r}{\sharp_{N-2}=\alpha_{N-1}C(B_{N-2},B_{N-1},t_{N-1}-t_{N-2})+\alpha_{N}C_{N}(B_{N-2},B_{N},t_{N}-t_{N-2})}\end{array}
$$  

which can be solved for the weight an-1 :  

$$
\mathbf{\alpha}_{\alpha_{N-1}}=\frac{\mathbf{\xi}_{N-2}-\mathbf{\alpha}_{N}C_{N}(B_{N-2},B_{N},t_{N}-t_{N-2})}{C(B_{N-2},B_{N-1},t_{N-1}-t_{N-2})}
$$  

By continuing in this manner we will find the relation  

$$
\mathbf{\upalpha}_{{\mathbf{{q}}_{i}}}=\frac{{\upxi_{i-1}}-{\upalpha_{i+1}}C(B_{i},B_{i+1},t_{i+1}-t_{i})-\hdots-{\upalpha_{N}}C_{N}(B_{i-1},B_{N},t_{N}-t_{i-1})}{C(B_{i-1},B_{i},t_{i}-t_{i-1})}
$$  

This relation is then used to recursively determine all weights from the previous ones.  

<html><body><table><tr><td colspan="2">QUANTITATIVESTRATEGIESRESEARCHNOTES</td></tr><tr><td colspan="2">Quantitative Strategies Publications</td></tr><tr><td>June 1990</td><td>UnderstandingGuaranteedExchange-Rate ContractsInForeignStockInvestments Emanuel Derman, Piotr Karasinski</td></tr><tr><td>July 1991</td><td>and Jeffrey S. Wecker Valuing Index Options When Markets Can Jump Emanuel Derman, Alex Bergier and Iraj Kani</td></tr><tr><td>January 1992</td><td>Valuing and Hedging Outperformance Options</td></tr><tr><td>March 1992</td><td>Emanuel Derman Pay-On-Exercise Options</td></tr><tr><td>December 1992</td><td>Emanuel Derman and Iraj Kani TheNikkeilodeonReferenceManual</td></tr><tr><td>December 1992</td><td>Valuing Options onPeriodically-Settled Stocks</td></tr><tr><td></td><td>Emanuel Derman, Iraj Kani and Alex Bergier</td></tr><tr><td>April 1993</td><td>TheOvidUserManual</td></tr><tr><td>April 1993</td><td>OptionPricingWhenVolatilityandInterestRates Are Random --A Finite Difference Approach Indrajit Bardhan</td></tr><tr><td>June 1993</td><td>TheIns and Outs ofBarrier Options</td></tr><tr><td></td><td>Emanuel Derman and Iraj Kani</td></tr><tr><td>July 1993 July 1993</td><td>The CompleatCalculator Catalog</td></tr><tr><td></td><td>Valuing Convertible Bonds as Derivatives Indrajit Bardhan, Alex Bergier, Emanuel Derman,</td></tr><tr><td>September 1993</td><td>Cemal Dosembet, Iraj Kani and Piotr Karasinski</td></tr><tr><td></td><td>TheHYDRAReferenceManual</td></tr><tr><td>October 1993</td><td>TheSMILEReferenceManual</td></tr><tr><td>January 1994</td><td>TheVolatilitySmile andItsImplied Tree</td></tr><tr><td></td><td>Emanuel Derman and Iraj Kani</td></tr><tr><td></td><td></td></tr><tr><td>March 1994</td><td>Options Pricing and Transactions Costs</td></tr><tr><td></td><td>QS Focus</td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td>May 1994</td><td></td></tr><tr><td></td><td>QuestforVALUEReferenceManual</td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td>May 1994</td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td>EstimatingtheImpactof Dilution ontheValue</td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td>of Corporate Securities</td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr></table></body></html>  