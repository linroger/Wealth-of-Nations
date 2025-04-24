# TOOLS FOR VOLATILITY ENGINEERING, VOLATILITY SWAPS, AND VOLATILITY TRADING  

# 15  

# CHAPTER OUTLINE  

# 15.1 Introduction . 508  

15.2 Volatility Positions .. 509   
15.2.1 Trading Volatility Term Structure . . 509   
15.2.2 Trading Volatility Across Instruments. 510   
15.3 Invariance of Volatility Payoffs .. . 510   
15.3.1 Imperfect Volatility Positions . 511   
15.3.1.1 A dynamic volatility position .. 512   
15.3.2 Volatility Hedging 516   
15.3.3 A Static Volatility Position ... 516   
15.4 Pure Volatility Positions .. 518   
15.4.1 Practical Issues.. 521   
15.4.1.1 The smile effect.. 521   
15.4.1.2 Liquidity problems .. 522   
.5 Variance Swaps .... 522   
15.5.1 Uses and Users of Variance Swaps 522   
15.5.1.1 Uses of variance swaps 522   
15.5.1.2 Market participants with an implicit volatility exposure to hedge . 523   
15.5.2 A Framework for Variance Swaps.. 523   
15.5.2.1 Real-world example of a variance swap.. 524   
15.5.2.2 Real-world conventions. 527   
15.5.2.3 Floating leg 527   
15.5.2.4 Determining the fixed variance. 528   
15.5.3 A Replicating Portfolio .. 529   
15.5.4 The Hedge . 530   
15.6 Real-World Example of Variance Contract.. 531   
.7 Volatility and Variance Swaps Before and After the GFC—The Role   
of Convexity Adjustments? 531   
15.7.1 The Difficulty of Hedging Variance Swaps in Practice . 531  

# 508 CHAPTER 15 TOOLS FOR VOLATILITY ENGINEERING, VOLATILITY SWAPS  

15.7.2 Convexity and the Difference Between Variance and Volatility Swaps.. 533   
15.7.2.1 Source of the convexity adjustment.. 533   
15.7.2.2 The role of convexity in the volatility trading market   
during the GFC.. 535   
15.7.3 Introduction to Volatility as an Asset Class... 535   
15.7.4 Post-GFC Regulation, Standardization and Exchange Traded   
Volatility Products .. 536   
15.7.4.1 Variance futures . 536   
15.7.4.2 Variance swaps . 538   
15.7.5 The Hedge . 539   
15.8 Which Volatility?. 539   
9 Conclusions. 541   
Suggested Reading . 542   
xercises 542   
MATLAB Exercises.. 543  

# 15.1 INTRODUCTION  

Liquid instruments that involve pure volatility trades are potentially very useful for market participants who have natural exposure to various volatilities in their balance sheet or trading book. The classical option strategies discussed in Chapter 11 have serious drawbacks in this respect. When a trader takes a position or hedges a risk, he or she expects that the random movements of the underlying would have a known effect on the position. The underlying may be random, but the payoff function of a well-defined contract or a position has to be known. Payoff functions of most classical volatility strategies are not invariant to underlying risks, and most volatility instruments turn out to be imperfect tools for isolating this risk. Even when traders’ anticipations come true, the trader may realize that the underlying volatility payoff functions have changed due to movements in other variables. Hence, classical volatility strategies cannot provide satisfactory hedges for volatility exposures. The reason for this and possible solutions are the topics of this chapter.  

Traditional volatility trades used to involve buying and selling portfolios of call and put options, straddles or strangles, and then possibly delta-hedging these positions. But such volatility positions were not pure and this led to a search for volatility tools whose payoff function would depend on the volatility risk only. This chapter examines two of the pure volatility instruments that were developed—variance and volatility swaps. Volatility swaps are forward contracts on future realized (stock) volatility. Variance contracts are similar contracts on variance, the square of future volatility. Variance and volatility swaps are interesting for at least two reasons: First, volatility is an important risk for market practitioners, and ways of hedging and pricing such risks have to be understood. Second, the discussion of volatility swaps constitutes a good example of the basic principles that need to be followed when devising new instruments.  

The chapter uses variance swaps instead of volatility swaps to conduct the discussion. Although markets in general use the term volatility, it is more appropriate to think in terms of variance, the square of volatility. Variance is the second centered moment of a random variable, and it falls more naturally from the formulas used in this chapter. For example, volatility (i.e., standard deviation) instruments require convexity adjustments, whereas variance instruments in general do not. Thus, when we talk about vega, for example, we refer to variance vega. This is the sensitivity of the option’s price with respect to $\sigma^{2}$ , not $\sigma$ . In fact, in the heuristic discussion in this chapter, at times the term volatility and variance are used interchangeably.  

# 15.2 VOLATILITY POSITIONS  

Volatility positions can be taken with the purpose of hedging a volatility exposure or speculating on the future behavior of volatility. These positions require instruments that isolate volatility risk as well as possible. To motivate the upcoming discussion, we introduce two examples that illustrate traditional volatility positions.  

# 15.2.1 TRADING VOLATILITY TERM STRUCTURE  

We have seen several examples for strategies associated with shifts in the interest rate term structure. They were called curve steepening or curve flattening trades. It is clear that similar positions can be taken with respect to volatility term structures as well. Volatilities traded in markets come with different maturities. As with the interest rate term structure, we can buy one “maturity” and sell another “maturity,” as the following example shows.  

# EXAMPLE  

[A] dealer said he was considering selling short-dated 25-delta euro puts/dollar calls and buying a longer-dated straddle. A three-month straddle financed by the sale of two 25-delta one-month puts would have cost $3.9\%$ in premium yesterday.  

These volatility plays are attractive because the short-dated volatility is sold for more than the cost of the longer-maturity options.  

In this particular example, the anticipations of traders concern not the level of an asset price or return, but, instead, the volatility associated with the price. Volatility over one interval is bought using the funds generated by selling the volatility over a different interval.  

Apparently, the traders think that short-dated euro volatility will fall relative to the long-dated euro volatility. The question is to what extent the positions taken will meet the traders’ needs, even when their anticipations are borne out. We will see that the payoff function of this position is not invariant to changes in the underlying euro/dollar exchange rate.  

# 15.2.2 TRADING VOLATILITY ACROSS INSTRUMENTS  

Our second example is from the interest rate sector and involves another “arbitrage” position on volatility. The trader buys the volatility of one risk and sells a related volatility on a different risk. This time, the volatilities in question do not belong to different time periods, but instead are generated by different instruments.  

# EXAMPLE  

Dealers are looking at the spreads between euro cap-floor straddle and swaption straddle volatility to take advantage of a $5\%$ volatility difference in the 7-year area. Proprietary traders are selling a two-year cap-floor straddle starting in six years with vols close to $15\%$ . The trade offers a good pick-up over the five-year swaption straddle with volatility $10\%$ . This compares with a historical spread closer to $2\%$ .  

Cap-floors and swaptions are instruments on interest rates. There are both similarities and differences between them. We will study them in more detail in the next chapter. Selling a cap-floor straddle will basically be short interest rate volatility. In the example, the traders were able to take this position at $15\%$ volatility. On the other hand, buying a swaption amounts to a long position on volatility. This was done at $10\%$ , which gives a volatility spread of about $5\%$ . The example states that the latter number has historically been around $2\%$ . Hence, by selling the spread the traders would benefit from a future narrowing of differences between the volatilities of the two instruments.  

This position’s payoff is not invariant to interest rate trajectories. Even when volatilities behave as anticipated, the path followed by the level of interest rates may result in unexpected volatility.2 The following discussion intends to clarify why such positions on volatility have serious weaknesses and require meticulous risk management. We will consider pure volatility positions later.  

# 15.3 INVARIANCE OF VOLATILITY PAYOFFS  

In previous chapters, convexity was used to isolate volatility as a risk. In Chapters 9 and 10, we showed how to convert the volatility of an underlying into “cash,” and with that took the first steps toward volatility engineering.  

Using the methods discussed in Chapters 9 and 10, a trader can hedge and risk-manage exposures with respect to volatility movements. Yet, these are positions influenced by variables other than volatility. Consider a speculative position taken by an investor.  

Let $S_{t}$ be a risk factor and suppose an investor buys $S_{t}$ volatility at time $t_{0}$ for a future period denoted by $[t_{1},T]$ , $T$ being the expiration of the contract. As in every long position, this means that the investor is anticipating an increase in realized volatility during this period. If realized volatility during $[t_{1},T]$ exceeds the volatility “purchased” at time $t_{0}$ , the investor will benefit. Thus far this is not very different from other long positions. For example, a trader buys a stock and benefits if the stock price goes up. He or she can buy a fixed receiver swap and benefit if the swap value goes up (the swap rate goes down). Similarly, in our present case, we receive a “fixed” volatility and benefit if the actual volatility exceeds this level.  

By buying call or put options, straddles, or strangles, and then delta-hedging these positions, the trader will, in general, end up with a long position that benefits if the realized volatility increases, as was shown in Chapters 9 and 10. Yet, there is one major difference between such volatility positions and positions taken on other instruments such as stocks, swaps, forward rate agreements (FRAs), and so on. Consider Figure 15.1a, that shows a long position on a stock funded by a money market loan. As the stock price increases, the position benefits by the amount $S_{t_{1}}-S_{t_{0}}$ . This potential payoff is known and depends only on the level of $S_{t_{1}}$ . In fact, it depends on $S_{t}$ linearly. In Figure 15.1b, we have a short-dated discount bond position. As the yield decreases, the position gains. Again, we know how much the position will be making or losing, depending on the movements in the yield, $y_{t},$ if convexity gains are negligible.  

A volatility position taken via, say, straddles, is fundamentally different from this as the payoff diagram will move depending on the path followed by variables other than volatility. For example, a change in (i) interest rates, (ii) the underlying asset price, or (iii) the level of implied volatility may lead to different payoffs at the same realized volatility level.  

Variance (volatility) swaps, on the other hand, are pure volatility positions. Potential gains or losses in positions taken with these instruments depend only on what happens to realized volatility until expiration. This chapter shows how volatility engineering can be used to set up such contracts and to study their pricing and hedging. We begin with imperfect volatility positions.  

# 15.3.1 IMPERFECT VOLATILITY POSITIONS  

In financial markets, a volatility position is often interpreted to be a static position taken by buying and selling straddles, or a dynamically maintained position that uses straddles or options. As  

![](6e704bf35253e115191ea65764511918cae0dcf045af8cf407ef2a615b0925e5.jpg)  

# FIGURE 15.1  

Long position on a stock (funded by a money market loan) and long discount bond position.  

mentioned previously, these volatility positions are not the right way to price, hedge, or riskmanage volatility exposure. In this section, we go into the reasons for this. We consider a simple position that consists of a dynamically hedged single-call option.  

# 15.3.1.1 A dynamic volatility position  

Consider a volatility exposure taken through a dynamically maintained position using a plain vanilla call. To simplify the exposition, we impose the assumptions of the Black Scholes world where there are no dividends; the interest rate, $r_{\mathrm{:}}$ , and implied volatility, $\sigma$ , are constant; there are no transaction costs; and the underlying asset follows a geometric process. Then the arbitrage-free value of a European call $C(S_{t},t)$ will be given by the Black Scholes formula3:  

$$
C(S_{t},t)=S_{t}\int_{-\infty}^{d_{1}}\frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}x^{2}}\mathrm{d}x-e^{-r(T-t)}K\int_{-\infty}^{d_{2}}\frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}x^{2}}\mathrm{d}x
$$  

where $S_{t}$ is the spot price, and $K$ is the strike. The $d_{i},i=1,2$ , are given by  

$$
d_{i}=\frac{\log(S_{t}/K)\pm(1/2)\sigma^{2}(T-t)+r(T-t)}{\sigma\sqrt{T-t}}
$$  

For simplicity, and without loss of generality, we let  

$$
r=0
$$  

This simplifies some expressions and makes the discussion easier to follow.4  

Now consider the following simple experiment. A trader uses the Black Scholes setting to take a dynamically hedged long position on implied volatility. Implied volatility goes up. Suppose the trader tracks the gains and losses of the position using the corresponding variance-vega. What would be this trader’s possible gains in the following specific case? Consider the following simple setup.  

1. The parameters of the position are as follows:  

$$
K=S_{t_{0}}=100
$$  

$$
\sigma=20\%
$$  

Initially we let $t_{0}=0$ .  

2. The trader expects an increase in the implied volatility from $20\%$ to $30\%$ , and considers taking a long volatility position.   
3. To buy into a volatility position, the trader borrows an amount equal to $100\:C\left(S_{t},\:t\right)$ , and buys 100 calls at time $t_{0}$ with funding cost $r=0$ .5   
4. Next, the position is delta-hedged by short-selling $C_{s}$ units of the underlying per call to obtain the familiar exposure shown in Figure 15.2.  

![](5fe6321b33d1344060be0fc1052756d095f266ead36f6719e87fba8d629f59c7.jpg)  

# FIGURE 15.2  

Delta-hedged long call position.  

In this example, there are about 1.2 months to the expiration of this option, the option is at-themoney, and the initial implied volatility is $20\%$ .  

It turns out that in this environment, even when the trader’s anticipations are borne out, the payoffs from the volatility position may vary significantly, depending on the path followed by $S_{t}$ . The implied volatility may move from $20\%$ to $30\%$ as anticipated, but the position may not pay the expected amount. The following example displays the related calculations.  

# EXAMPLE  

We can calculate the relevant Greeks and payoff curves using Mathematica or MATLAB. First, we obtain the initial price of the call as  

$$
C(100,t_{0})=2.52
$$  

Multiplying by 100, the total position is worth $\$252$ . Then, we get the implied delta of this position by first calculating the $S_{t}$ -derivative of $C(S_{t},t)$ evaluated at $S_{t_{0}}=100$ , and then multiplying by 100:  

$$
100\bigg(\frac{\partial C(S_{t},t)}{\partial S_{t}}\bigg)=51.2
$$  

Hence, the position has $+51$ -delta. To hedge this exposure, the trader needs to short 51 units of the underlying and make the net delta exposure approximately equal to zero.  

Next, we obtain the associated gamma and the (variance) vega of the position at $t_{0}$ . Using the given data, we get  

$$
\mathrm{Gamma}=100\bigg[\frac{\hat{\sigma}^{2}C(S_{t},t)}{\hat{\sigma}S_{t}^{2}}\bigg]=6.3
$$  

$$
{\mathrm{Variance~vega}}=100\left[{\frac{\hat{\sigma}C(S_{t},t)}{\hat{\sigma}\sigma^{2}}}\right]=3152
$$  

The change in the option value, given a change in the (implied) variance, is given approximately by  

$$
100[\partial C(S_{t},t)]\cong(3152)\widehat{\sigma}\sigma^{2}
$$  

This means that, everything else being constant, if the implied volatility rises suddenly from $20\%$ to $30\%$ , the instantaneous change in the option price will depend on the product of these numbers and is expected to be  

$$
\begin{array}{c}{{100[\partial C(S_{t},t)]\cong3152(0.09-0.04)}}\\ {{{}}}\\ {{=157.6}}\end{array}
$$  

In other words, the position is expected to gain about $\$158$ , if everything else remained constant.  

The point is that the trader was long implied volatility, expecting that it would increase, and it did. So if the volatility does go up from $20\%$ to $30\%$ , is this trader guaranteed to gain the $\$157.6?$ Not necessarily. Let us see why not.  

Even in this simplified Black Scholes world, the (variance) vega is a function of $S_{t},\ t,\ r,$ as well as $\sigma^{2}$ . Everything else is not constant and the $S_{t}$ may follow any conceivable trajectory. But, and this is the important point, when $S_{t}$ changes, this in turn will make the vega change as well. The following table shows the possible values for variance-vega depending on the value assumed by $S_{t},$ , within this setting.6  

<html><body><table><tr><td>St Vega</td></tr><tr><td>80 0.0558</td></tr><tr><td>90 7.4666</td></tr><tr><td>100 31.5234</td></tr><tr><td>110 10.6215</td></tr><tr><td>120 0.5415</td></tr></table></body></html>  

Thus, if the expectations of the trader are fulfilled, the implied volatility increases to $30\%$ , but, at the same time, if the underlying price moves away from the strike, say to $S_{t_{1}}=80$ , the same calculation will become approximately:  

$$
\begin{array}{l}{{\mathrm{Vega}(\hat{o}\sigma^{2}){\cong}5.6(0.09-0.04)}}\\ {{=}0.28}\end{array}
$$  

Hence, instead of an anticipated gain of $\$157.6$ , the trader could realize almost no gain at all. In fact, if there are costs to maintaining the volatility position, the trader may end up losing money. The reason is simple: as $S_{t}$ changes, the option’s sensitivity to implied volatility, namely the vega, changes as well. It is a function of $S_{t}$ . As a result, the outcome is very different from what the trader was originally expecting.  

For a more detailed view on how the position’s sensitivity moves when $S_{t}$ changes, consider Figure 15.3 where we plot the partial derivative:  

$$
100{\frac{\partial{\mathrm{~variance~vega}}}{\partial S_{t}}}
$$  

Under the present conditions, we see that as long as $S_{t}$ remains in the vicinity of the strike $K$ , the trader has some exposure to volatility changes. But as soon as $S_{t}$ leaves the neighborhood of $K$ , this exposure drops sharply. The trader may think he or she has a (variance) volatility position, but, in fact, the position costs money, and may not have any significant variance exposure as the underlying changes right after the trade is put in place. Thus, such classical volatility positions are imperfect ways of putting on volatility trades or hedging volatility exposures.  

![](4486c037cb124f120b718a3d6346c4a8a80ad2dbbccc928021deb05f3223277f.jpg)  

# FIGURE 15.3  

Vega as a function of the price of the underlying.  

# 15.3.2 VOLATILITY HEDGING  

The outcome of such volatility positions may also be unsatisfactory if these positions are maintained as a hedge against a constant volatility exposure in another instrument. According to what was discussed, movements in $S_{t}$ can make the hedge disappear almost completely and the trader may hold a naked volatility position in the end. An institution that has volatility exposure may use a hedge only to realize that the hedge may be slipping over time due to movements unrelated to volatility fluctuations.  

Such slippage may occur for more reasons than just a change in $S_{t}$ . In reality, there are also (i) smile effects, (ii) interest rate effects, and (iii) shifts in correlation parameters in some instruments. Changes in these can also cause the classical volatility payoffs to move away from initially perceived levels.  

# 15.3.3 A STATIC VOLATILITY POSITION  

If a dynamic delta-neutral option position loses its exposure to movements in $\sigma^{2}$ and, hence, ceases to be useful as a hedge against volatility risk, do static positions fare better?  

A classic position that has volatility exposure is buying (selling) ATM straddles. Using the same numbers as above, Figure 15.4 shows the joint payoff of an ATM call and an ATM put struck at $K=100$ . This position is made of two plain vanilla options and may suffer from a similar defect. The following example discusses this in more detail.  

![](2c282b99cf434d83d4d56f7553d884472fa6f951569cef12d74ebe2f26a33d0f.jpg)  

# FIGURE 15.4  

Joint payoff of an ATM call and ATM put.  

# EXAMPLE  

As in the previous example, we choose the following numerical values:  

$$
S_{t_{0}}=100,~r=0,~T-t_{0}=0.1
$$  

The initial volatility is $20\%$ , which means that  

$$
\sigma^{2}=0.04
$$  

We again look at the sensitivity of the position with respect to movements in some variables of interest. We calculate the variance vega of the portfolio:  

$$
V(S_{t},t)=100\{\mathrm{ATMPut+ATMCall}\}
$$  

by taking the partial:  

$$
{\mathrm{Straddle~vega}}=100{\frac{\partial V(S_{t},t)}{\partial\sigma^{2}}}
$$  

Then, we substitute the appropriate values of $S_{t},t,\sigma^{2}$ in the formula. Doing this for some values of interest for $S_{t}$ , we obtain the following sensitivity factors:  

<html><body><table><tr><td>St</td><td>Vega</td></tr><tr><td>80</td><td>11</td></tr><tr><td>90</td><td>1493</td></tr><tr><td>100</td><td>6304</td></tr><tr><td>110</td><td>2124</td></tr><tr><td>120</td><td>108</td></tr></table></body></html>  

According to these numbers, if $S_{t}$ stays at 100 and the volatility moves from $20\%$ to $30\%$ , the static position’s value increases approximately by  

$$
{\begin{array}{c}{{\hat{\sigma}}\operatorname{Straddle}\cong6304(0.09-0.04)}\\ {\qquad}\\ {=315.2}\end{array}}
$$  

As expected, this return is about twice as big as in the previous example. The straddle has more sensitivity to volatility changes. But, the option’s responsiveness to volatility movements is again not constant, and depends on factors that are external to what happens to volatility. The table shows that if $S_{t}$ moves to 80, then even when the trader’s expectation is justified and volatility moves from $20\%$ to $30\%$ , the position’s mark-to-market gains will go down to about 0.56.  

![](06a4210dae3540cdf13e91d669da40e910561f33efc14f751bfb47a7e866f4d5.jpg)  

# FIGURE 15.5  

Straddle’s sensitivity with respect to implied volatility for different values of $S_{t}.$  

Figure 15.5 shows the behavior of the straddle’s sensitivity with respect to implied volatility for different values of $S_{t}$ . We see that the volatility position is again not invariant to changes in external variables. However, there is one major difference from the case of a dynamically maintained portfolio. Static non-delta-hedged positions using straddles will benefit from actual (realized) movements in $S_{t}$ . For example, if $S_{t}$ stays at 80 until expiration date $T,$ the put leg of the straddle would pay 20 and the static volatility position would gain. This is regardless of how the vega of the position changed due to movements in $S_{t}$ over the interval $[t_{0},T]$ .  

# 15.4 PURE VOLATILITY POSITIONS  

The key to finding the right way to hedge volatility risk or to take positions in it is to isolate the “volatility” completely, using existing liquid instruments. In other words, we have to construct a synthetic such that the value of the synthetic changes only when “volatility” changes. This position should not be sensitive to variations in variables other than the underlying volatility. The exposure should be invariant. Then, we can use the synthetic to take volatility exposures or to hedge volatility risk. Such volatility instruments can be quite useful.  

First, we know from Chapters 12 and 13 that by using options with different strikes we can essentially create any payoff that we like—if options with a broad range of strikes exist and if markets are complete. Thus, we should, in principle, be able to create pure volatility instruments by using judiciously selected option portfolios.  

![](258f0208ab847210e70a9c43d77e9a555d2af05c72f8f0e2450efc0bced1d89a.jpg)  

# FIGURE 15.6  

Vega of three plain vanilla European call options.  

Second, if an option position’s vega drops suddenly once $S_{t}$ moves away from the strike, then, by combining options of different strikes appropriately, we may be able to obtain a portfolio of options whose vega is more or less insensitive to movements in $S_{t}$ . Heuristically speaking, we can put together small portions of smooth curves to get a desired horizontal line.  

When we follow these steps, we can create pure volatility instruments. Consider the plot of the vega of three plain vanilla European call options, two of which are out-of-the-money. The options are identical in all respects, except for their strike. Figure 15.6 shows an example. Three $\sigma^{2}$ sensitivity factors for the strikes $K_{0}=100$ , $K_{1}=110$ , $K_{2}=120$ are plotted. Note that each variance vega is very sensitive to movements in $S_{t}$ , as discussed earlier. Now, what happens when we consider the portfolio made of the sum of all three calls? The sensitivity of the portfolio,  

$$
V(S_{t},t)=\{C(S_{t},t,K_{0})+C(S_{t},t,K_{1})+C(S_{t},t,K_{2})\}
$$  

again varies as $S_{t}$ changes, but less. So, the direction taken is correct except that the previous portfolio did not optimally combine the three options. In fact, according to Figure 15.6, we should have combined the options by using different weights that depend on their respective strike price. The more out-of-the-money the option is, the higher should be its weight, and the more it should be present in the portfolio.  

Hence, consider the new portfolio where the weights are inversely proportional to the square of the strike $K$ ,  

$$
V(S_{t},t)=\frac{1}{K_{0}^{2}}C(S_{t},t,K_{0})+\frac{1}{K_{1}^{2}}C(S_{t},t,K_{1})+\frac{1}{K_{2}^{2}}C(S_{t},t,K_{2})
$$  

![](38e8af45601ed18b356e8bac47cee3124d384ba03fbc275bb686609f1595651e.jpg)  
Variance vega of a portfolio of options with weights inversely proportional to the square of the strike price.  

# FIGURE 15.7  

The variance vega of this portfolio that uses the parameter values given earlier, is plotted in Figure 15.7. Here, we consider a suitable $0<\in$ , and the range  

$$
K_{0}-\in<S_{t}<K_{2}+\in
$$  

Figure 15.7 shows that the vega of the portfolio is approximately constant over this range when $S_{t}$ changes. This suggests that more options with different strikes can be added to the portfolio, weighting them by the corresponding strike prices. In the example below we show these calculations.  

# EXAMPLE  

Consider the portfolio  

$$
V(S_{t},t)=\left[\frac{1}{80^{2}}C(S_{t},t,80)+\frac{1}{90^{2}}C(S_{t},t,90)+\frac{1}{100^{2}}C(S_{t},t,100)\right.
$$  

$$
+\frac{1}{110^{2}}C(S_{t},t,110)+\frac{1}{120^{2}}C(S_{t},t,120)\bigg]
$$  

This portfolio has an approximately constant vega for the range  

$$
80-\in<S_{t}<120+\in
$$  

By including additional options with different strikes in a similar fashion, we can lengthen this section further.  

We have, in fact, found a way to create synthetics for volatility positions using a portfolio of liquid options with varying strikes, where the portfolio options are weighted by their respective strikes.  

# 15.4.1 PRACTICAL ISSUES  

In our attempt to obtain a pure volatility instrument, we have essentially followed the same strategy that we have been using all along. We constructed a synthetic. But this time, instead of matching the cash flows of an instrument, the synthetic had the purpose of matching a particular sensitivity factor. It was put together so as to have a constant (variance) vega.  

Once a constant vega portfolio is found, the payoff of this portfolio can be expressed as an approximately linear function of $\sigma^{2}$  

$$
V(\sigma^{2})=a_{0}+a_{1}\sigma^{2}+\mathrm{small}
$$  

with  

$$
a_{1}=\frac{\hat{\sigma}V(\sigma^{2},t)}{\hat{\sigma}\sigma^{2}}
$$  

as long as $S_{t}$ stays within the range  

$$
S^{\mathrm{min}}=K_{0}<S_{t}<K_{n}=S^{\mathrm{max}}
$$  

Under these conditions, the volatility position will look like any other long (or short) position, with a positive slope $a_{1}$ .  

The portfolio with a constant (variance) vega can be constructed using vanilla European calls and puts. The rules concerning synthetics discussed earlier apply here also. It is important that elements of the synthetic be liquid; therefore, liquid calls and puts have to be selected. The previous discussion referred only to calls. Practical applications of the procedure involve puts as well. This brings us to two somewhat complicated issues. The first has to do with the smile effect. The second concerns liquidity.  

# 15.4.1.1 The smile effect  

Suppose we form a portfolio at time $t_{0}$ that has a constant vega as long as $S_{t}$ stays in a reasonable range  

$$
S^{\mathrm{min}}<S_{t}<S^{\mathrm{max}}
$$  

Under these conditions, the portfolio consists of options with different “moneyness” properties, and the volatility parameter in the option pricing formulas may depend on $K$ if there is a volatility  

smile. In general, as $K$ decreases, the implied $\sigma(K)$ would increase for constant $S_{t}$ . Under these conditions, the trader needs to accurately determine the smile and the way to model it before the portfolio is formed.  

# 15.4.1.2 Liquidity problems  

From the preceding it follows that we need to select out-of-the-money options for the synthetic since they are more liquid. But as time passes, the moneyness of these options changes and this affects their liquidity. Those options that become in-the-money are now less liquid. Other options that were not originally included in the synthetic become more liquid. Even though the replicating portfolio was static, the illiquidity of the constituent options may become a drawback in case the position needs to be unwound.  

# 15.5 VARIANCE SWAPS  

One instrument that has invariant exposure to fluctuations in (realized) variance is the variance swap. In this section, we introduce this concept and in the next, we provide a simple framework for studying it.  

A variance swap is, in many ways, just like any other swap. The parties exchange floating risk against a risk fixed at the contract origination. In this case, what is being swapped is not an interest rate or a return on an equity instrument, but the variances that correspond to various risk factors.  

# 15.5.1 USES AND USERS OF VARIANCE SWAPS  

Before we study the hedging and pricing of variance swaps it is instructive to think about what the potential uses of variance swaps are.  

# 15.5.1.1 Uses of variance swaps  

We can distinguish several uses and users of variance swaps. First, some users may be interested in variance swaps as a way of directionally trading variance levels. This could be for hedging or speculative purposes. Market participants who would like to speculate on the future levels of stock or index variance or volatility can go long or short realized variance with a variance swap. The advantage of such a position over trading and hedging options is that the variance swap is not contaminated by other risk exposures. If an investor expects a sharp decline in political and financial uncertainty after a forthcoming election, for example, a short position in a variance swap may be a good way to express this view and profit from it.  

Second, some investors may use the variance swap to trade the spread between realized and implied variance levels. As we will see below, the fair strike price $\boldsymbol{F}_{t_{0}}$ in a variance swap is related to the level of current-implied volatilities for options with the same expiration as the swap. Therefore, by unwinding the swap before expiration, a market participant can trade the spread between realized and implied volatility.  

# 15.5.1.2 Market participants with an implicit volatility exposure to hedge  

We can think of at least three groups of market participants with an implicit volatility exposure to hedge. Some event-driven hedge funds engage in merger arbitrage and take positions that assume that the spread between an acquirer and takeover target will narrow. The risk is, however, that if overall market volatility increases the merger may be less likely and the spread may widen leading to loses for merger arbitrage hedge funds.  

Some institutional investors that follow active benchmarking strategies regularly rebalance their portfolios. In volatile periods such rebalancing may need to be more frequent, thus leading to higher portfolio turnover and transaction costs. Independent from transaction costs, higher volatility may also lead to increased tracking error for portfolio managers who are judged against a benchmark. As asset prices move quickly, they may not be able to track the benchmark as effectively as when volatility is low.  

Standard equity funds could be argued to be short volatility since there is a negative empirical correlation between equity market levels and volatility as we will see below. Thus, as global equity correlations rise, diversification across securities and countries becomes less effective. The GFC represents a recent example of many such turbulent periods during which most assets fall, but variances tends to rise, thus leading to a potential hedge.  

The three market participants listed above could all benefit potentially from long positions in variance swaps to hedge their exposures and reduce portfolio risk.  

In the following section, we move to a more technical discussion of variance swaps. However, we emphasize again that the discussion will proceed using the variance rather than the volatility as the underlying.  

# 15.5.2 A FRAMEWORK FOR VARIANCE SWAPS  

Let $S_{t}$ be the underlying price. The time- $T_{2}$ payoff $V(T_{1},T_{2})$ of a variance swap with a notional amount, $N.$ , is given by the following:  

$$
V(T_{1},T_{2})=\Big[\sigma_{T_{1},T_{2}}^{2}-F_{t_{0}}^{2}\Big](T_{2}-T_{1}){\cal N}
$$  

where $\sigma_{T_{1},T_{2}}$ is the realized volatility rate of $S_{t b}$ during the interval $t\in[T_{1},T_{2}]$ , with $t<T_{1}<T_{2}$ . It is similar to a “floating” rate, and will be observed only when time $T_{2}$ arrives. The $\boldsymbol{F}_{t_{0}}$ is the “fixed” $S_{t}$ volatility rate that is quoted at time $t_{0}$ by markets. This has to be multiplied by $(T_{2}-T_{1})$ to get the appropriate volatility for the contract period. $N$ is the notional amount that needs to be determined at contract initiation. At time $t_{0}$ , the $V(T_{1},T_{2})$ is unknown. The swap is set so that the time- $\cdot t_{0}$ “expected value” of the payoff, denoted by $V(t_{0},T_{1},T_{2})$ is zero. At initiation, no cash changes hands:  

$$
V(t_{0},T_{1},T_{2})=0
$$  

Thus, variance swaps are similar to a vanilla (interest rate) swap in that a “floating” $\sigma_{T_{1},T_{2}}^{2}(T_{2}-T_{1})N$ is received against a “fixed” $(T_{2}-T_{1})F_{t_{0}}^{2}N$ .  

The cash flows implied by a variance swap are shown in Figure 15.8. The contract is initiated at time $t_{0}.$ , and the start date is $T_{1}$ . It matures at $T_{2}$ . The “floating” volatility (variance) is the total volatility (variance) of $S_{t}$ during the entire period $[T_{1},T_{2}].F_{t_{0}}$ has the subscript $t_{0}$ , and, hence, has to be determined at time $t_{0}$ .  

![](f7a03597c078168ac799053db1322be256472d72532a0f8f3034c6d418387f53.jpg)  

# FIGURE 15.8  

Variance swap cash flows.  

# 15.5.2.1 Real-world example of a variance swap  

Below we provide a real-world example of a variance swap.  

# EXAMPLE: VARIANCE SWAP ON S&P500—SPX INDICATIVE TERMS AND CONDITIONS  

<html><body><table><tr><td>Instrument:</td><td>Swap</td></tr><tr><td>Variance buyer:</td><td>TBD (e.g., JPMorganChase)</td></tr><tr><td>Variance seller:</td><td>TBD (e.g., Investor)</td></tr><tr><td>Denominated currency:</td><td>USD</td></tr><tr><td>Vega amount:</td><td>100,000</td></tr><tr><td>Variance amount:</td><td>3125 (determined as vega amount/(strike X 2))</td></tr><tr><td>Underlying:</td><td>S&P500 (Bloomberg ticker: SPX index)</td></tr><tr><td>Strike price Kvol:</td><td>16</td></tr><tr><td>Equity amount:</td><td>T+ 3 after the observation end date, the Equity Amount will be calculated and paid in accordance with the following formula:</td></tr></table></body></html>  

Final Equity payment $\b=$ variance amount $\times$ final realized volatility2 2 strike price2  

If the Equity Amount is positive the Variance Seller will pay the Variance Buyer the Equity Amount. If the Equity Amount is negative the Variance Buyer will pay the Variance Seller an amount equal to the absolute value of the Equity Amount, where  

$$
{\mathrm{Final~realized~volatility}}={\sqrt{\frac{252\times\sum_{t=1}^{t=N}\left(\ln(P_{t}/P_{t-1})\right)^{2}}{\mathrm{Expected}_{-}N}}}\times100\
$$  

and  

Expected $N=$ [number of days], being the number of days which, as of Trade Date, are expected to be Scheduled Trading Days in the Observation Period $P_{0}=$ The Official Closing of the underlying at the Observation Start Date $P_{t}=$ Either the Official Closing of the underlying in any observation date tor, at Observation End Date, the Official Settlement Price of the Exchange-Traded Contract.  

(Bossu et al. (2005))  

The terms and conditions of the variance swap contract show that if realized variance is higher than the strike price $K_{\mathrm{vol}}$ , the variance buyer will receive a payment from the variance seller. Similar to other derivative contracts, variance swaps can be used for hedging or speculation. Let’s consider an example in which the contract is used for hedging purposes. The variance buyer buys the variance swap as insurance, that is, for the purpose of hedging against unexpected increases in variance. Why would the variance buyer want to hedge against variance increases? The variance buyer (i.e., JPMorganChase, here) might have, for example, issued structured equity products with a capital guarantee to retail investors and now wants to hedge the structured product by means of a variance swap. The capital guarantee protects the retail investor against losses. The structured product could consist of an equity market exposure and a capped downside. JPMorganChase could use a long position in a put option on the index, or if it is cheaper, a long position in a variance swap to generate the cash flow to pay for the capital guarantee. When stock markets plunge variances and correlations tend to increase. The variance contract term sheets show a strike price $K_{\mathrm{vol}}$ of 16, that is a volatility of 16. A stock market plunge might occur in a scenario when the realized volatility is (substantial) above 16. The variance buyer (JPMorganChase) could buy, that is go long, the variance swap. Who would be the counterparty? The “Investor” could be a hedge fund for example. We could economically interpret the transaction as JPMorganChase buying insurance from the hedge fund against unexpected increases in variance.  

In line with market practice the variance notional is defined in volatility terms:  

$$
\mathrm{Variance~notional}={\frac{\mathrm{vega~notional}}{2\times K_{\mathrm{vol}}}}
$$  

The vega amount is $\$100,000$ (which implies a variance amount of $\$3125(=\$100,000$ $(2\times16)\$ . The implication of the above adjustment is that when the realized volatility is 1 “vega” or 1 volatility point above the strike at maturity, the payoff is approximately equal to the Vega Notional.  

In the variance swap term sheet, it is interesting to observe that returns are calculated on a logarithmic basis and that the mean return is assumed to be zero for simplicity which means that the payoff is perfectly additive: 6-month $+6$ -month variance $=1$ -month variance.  

If the index realizes a $20\%$ volatility over the next year, for example, the Variance Buyer—the long position—will receive $\begin{array}{r}{\xi d50,O O O\overset{\cdot}{=}3I25\times(R e a l i\overset{\cdot}{z}e d\nu o l a t i l i t y^{2}\overset{\cdot}{-}K_{\nu o l}{}^{2})=3I25\times(20\overset{\cdot}{-}I6^{2}).}\end{array}$ . This could be interpreted as a realized insurance payout from the hedge fund to JPMorganChase. Why would the hedge fund enter into such a transaction as a counterparty? As we will see below, historically, the implied variance (the fixed leg) has been above the realized variance (floating leg)  

on average. For example, if the index only realizes $12\%$ , the long will pay $\$350,000$ (Realized volatility $^2-\bar{K}_{\nu o l}^{\quad2})=3I25\times(I2^{2}-I6^{2})$ to the seller. Here JPMorganChase would pay the investor or hedge fund $\$350,000$ .7 This could be interpreted as an insurance premium. In the past over certain time periods it was possible for a hedge fund to earn a substantial risk or insurance premium by selling variance swaps or being short variance swaps. This is by no means a riskless trade, however, since in crises times, the realized volatility tends to exceed and rise above the implied volatility.  

Figure 15.9 shows the floating and fixed leg for a S&P500 variance swap contract from 1996 to 2014. The contract is for 30-day variance. The floating leg is based on the realized variance and  

![](3ff6ceeea1911c31afedea49c6acdd72ad2cdfa4510c23a65812e112a0092be5.jpg)  

# FIGURE 15.9  

Floating and fixed leg for a S&P500 variance swap contract.  

the fixed leg is based on the implied variance.8 As we can see the implied variance was above the realized variance for most of the pre-GFC and post-GFC period. This highlights the insurance premium that a variance seller could have pocketed for selling variance swaps.  

However, the variance seller would have made large losses during the GFC. As the figure illustrates, on September 29, 2008, the realized variance reached a level of 0.70 while implied variance was 0.13. Many trading desks and hedge funds that were short variance in 2008 suffered substantial losses and some were forced to close. Note that variance swaps were traded as OTC contracts and no historical data from exchange traded variance contracts are currently available. Therefore, the plot is based on synthetic variance swap contracts based on S&P500 index options and Optionmetrics volatility surface data.  

Figure 15.9 also illustrates an important feature of volatility, which is its tendency to revert to the mean. If we were to compare the volatility plot to the realized return of the S&P500 we would also see that equity volatility is negatively correlated with the equity index and tends to rise in times of elevated uncertainly or risk.  

# 15.5.2.2 Real-world conventions  

As the term sheet illustrates it is important for counterparties to agree the procedure for calculating the realized volatility, in particular, the sources and the frequency of the price of the underlying as well as the annualization factor used in moving from daily to annual volatilities. It also matters whether the standard deviation is calculated by subtracting the sample mean from each return, or by assuming a zero return. The zero mean method has theoretical advantages since it corresponds most closely to the contract that can be replicated by means of option portfolios.  

# 15.5.2.3 Floating leg  

Variance (volatility) positions need to be taken with respect to a well-defined time interval. After all, the volatility rate is like an interest rate: It is defined for a specific time interval. Thus, we subdivide the period $[T_{1},T_{2}]$ into equal subintervals, say, days:  

$$
T_{1}=t_{1}<t_{2}\dots<t_{n}=T_{2}
$$  

with  

$$
t_{i}-t_{i-1}=\delta
$$  

and then define the realized variance for period $\delta$ as  

$$
\sigma_{t_{i}}^{2}\delta=\left[\frac{S_{t_{i}}-S_{t_{i-1}}}{S_{t_{i-1}}}-\mu\delta\right]^{2}
$$  

where $i=1,...,n$ .9 Here, $\mu$ is the expected rate of change of $S_{t}$ during a year. This parameter can be set equal to zero or any other estimated mean. Regardless of the value chosen, $\mu$ needs to be carefully defined in the contract. If $\mu$ is zero, then the right-hand side is simply the squared returns during intervals of length $\delta$ .  

Adding the marginal variances for successive intervals, $\sigma_{T_{1},T_{2}}^{2}$ is equal to  

$$
\bigg(\sigma_{T_{1},T_{2}}^{2}\bigg)(T_{2}-T_{1})=\sum_{i=1}^{n}\bigg[\frac{S_{t_{i}}-S_{t_{i-1}}}{S_{t_{i}}}-\mu\delta\bigg]^{2}
$$  

Thus, $\sigma_{T_{1},T_{2}}^{2}$ represents the realized percentage variance of the $S_{t}$ during the interval $[T_{1},T_{2}]$ If the intervals become smaller and smaller, $\delta\to0$ , the last expression can be written as  

$$
\begin{array}{r l r}&{}&{\Big(\sigma_{T_{1},T_{2}}^{2}\Big)(T_{2}-T_{1})=\displaystyle\int_{T_{1}}^{T_{2}}\left[\frac{1}{S_{t}}\mathrm{d}S_{t}-\mu\mathrm{d}t\right]^{2}}\\ &{}&{=\displaystyle\int_{T_{1}}^{T_{2}}\sigma_{t}^{2}\mathrm{d}t\quad\quad}\end{array}
$$  

This formula defines the realized variance. It is a random variable at time $t_{0}$ , and can be viewed as the floating leg of the swap. Obviously, such floating variances can be defined for any interval in the future and can then be exchanged against a “fixed” leg.  

# 15.5.2.4 Determining the fixed variance  

Determining the fixed volatility, $\boldsymbol{F}_{t_{0}}$ , will give the fair value of the variance swap at time $t_{0}$ . How do we obtain the numerical value of $F_{t_{0}}$ ? We start by noting that the variance swap is designed so that its fair value at time $t_{0}$ is equal to zero. Accordingly, the $F_{t_{0}}^{2}$ is that number (variance), which makes the fair value of the swap equal zero. This is a basic principle used throughout the text and it applies here as well.  

We use the fundamental theorem of asset pricing and try to find a proper arbitrage-free measure $\tilde{P}$ such that  

$$
E_{t_{0}}^{\tilde{P}}\Big[\sigma_{T_{1},T_{2}}^{2}-F_{t_{0}}^{2}\Big](T_{2}-T_{1})N=0
$$  

What could this measure $\tilde{P}$ be? Suppose markets are complete.  

We assume that the continuously compounded risk-free spot rate $r$ is constant. The random process $\sigma_{T_{1},T_{2}}^{2}$ is, then, a nonlinear function of $S_{u}$ , $T_{1}\leq u\leq T_{2}$ , only:  

$$
\sigma_{T_{1},T_{2}}^{2}(T_{2}-T_{1})=\int_{T_{1}}^{T_{2}}\left[\frac{1}{S_{t}}\mathrm{d}S_{t}-\mu\mathrm{d}t\right]^{2}
$$  

Under some conditions, we can use the normalization by the money market account and let $\tilde{P}$ be the risk-neutral measure.10 Then, from Eq. (15.41), taking the expectation inside the brackets and arranging, we get  

$$
F_{t_{0}}^{2}=E_{t_{0}}^{\tilde{P}}\bigg[\sigma_{T_{1},T_{2}}^{2}\bigg]
$$  

This leads to the pricing formula  

$$
F_{t_{0}}^{2}=\frac{1}{T_{2}-T_{1}}E_{t_{0}}^{\tilde{P}}\left[\int_{T_{1}}^{T_{2}}\left[\frac{1}{S_{t}}\mathrm{d}S_{t}-\mu\mathrm{d}t\right]^{2}\right]
$$  

Therefore, to determine $F_{t_{0}}^{2}$ we need to evaluate the expectation under the measure $\tilde{P}$ of the integral of $\sigma_{t}^{2}$ . The discrete time equivalent of this is given by  

$$
F_{t_{0}}^{2}=\frac{1}{T_{2}-T_{1}}E_{t_{0}}^{\tilde{P}}\left[\sum_{i=1}^{n}\left[\frac{S_{t_{i}}-S_{t_{i-1}}}{S_{t_{i-1}}}-\mu\delta\right]^{2}\right]
$$  

Given a proper arbitrage-free measure, it is not difficult to evaluate this expression. One can use Monte Carlo or tree methods to do this once the arbitrage-free dynamics are specified.  

# 15.5.3 A REPLICATING PORTFOLIO  

The representation using the risk-neutral measure can be used for pricing. But how would we hedge a variance swap? To create the right hedge, we need to find a replicating portfolio. We discuss this issue using an alternative setup. This alternative has the side advantage of the financial engineering interpretation of some mathematical tools being clearly displayed. The following model starts with Black Scholes assumptions.  

The trick in hedging the variance swap lies in isolating $\sigma_{T_{1},T_{2}}^{2}$ in terms of observable (traded) quantities. This can be done by obtaining a proper synthetic. Assume a diffusion process for $S_{t}$ :  

$$
\mathrm{d}S_{t}=\mu(S_{t},t)S_{t}\mathrm{d}t+\sigma(S_{t},t)S_{t}\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

where $W_{t}$ is a Wiener process defined under the probability $\tilde{P}$ . The diffusion parameter $\sigma(S_{t},t)$ is called local volatility. Now consider the nonlinear transformation:  

$$
Z_{t}=f(S_{t})=\log(S_{t})
$$  

We apply Ito’s Lemma to set up the dynamics (i.e., the SDE) for this new process $Z_{t}$ :  

$$
\mathrm{d}Z_{t}=\frac{\hat{\sigma}f(S_{t})}{\hat{\sigma}S_{t}}\mathrm{d}S_{t}+\frac{1}{2}\frac{\hat{\sigma}^{2}f(S_{t})}{\hat{\sigma}S_{t}^{2}}\sigma(S_{t},t)^{2}S_{t}^{2}\mathrm{d}t\quad t\in[0,\infty)
$$  

which gives  

$$
\mathrm{~d~}\log(S_{t})=\frac{1}{S_{t}}\mu(S_{t},t)S_{t}\mathrm{d}t-\frac{1}{2S_{t}^{2}}\sigma(S_{t},t)^{2}S_{t}^{2}\mathrm{d}t+\sigma(S_{t},t)\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

where the $S_{t}^{2}$ term cancels out on the right-hand side. Collecting terms, we obtain  

$$
\mathrm{d}\log(S_{t})=\left[\mu(S_{t},t)-\frac{1}{2}\sigma(S_{t},t)^{2}\right]\mathrm{d}t+\sigma(S_{t},t)\mathrm{d}W_{t}
$$  

Notice an interesting result. The dynamics for $\mathrm{d}S_{t}/S_{t}$ and $\mathrm{~d~}\log(S_{t})$ are almost the same except for the factor involving $\sigma(S_{t},\ t)^{2}\mathrm{d}t$ . This means that we can subtract the two equations from each other and obtain  

$$
\frac{\mathrm{d}S_{t}}{S_{t}}-\mathrm{d}\log(S_{t})=\frac{1}{2}\sigma(S_{t},t)^{2}\mathrm{d}t\quad t\in[0,\infty)
$$  

This operation has isolated the instantaneous percentage local volatility on the right-hand side. But, what we need for the variance swap is the integral of this term. Integrating both sides we get  

$$
\int_{T_{1}}^{T_{2}}\left[\frac{1}{S_{t}}\mathrm{d}S_{t}-\mathrm{d}\log(S_{t})\right]=\frac{1}{2}\int_{T_{1}}^{T_{2}}\sigma(S_{t},t)^{2}\mathrm{d}t
$$  

We now take the integral on the left-hand side,  

$$
\int_{T_{1}}^{T_{2}}\mathrm{d}\log(S_{t})=\log\left(S_{T_{2}}\right)-\log\left(S_{T_{1}}\right)
$$  

We use this and rearrange to obtain the result:  

$$
2\left[\int_{T_{1}}^{T_{2}}\frac{1}{S_{t}}\mathrm{d}S_{t}\right]-2\log\left(\frac{S_{T_{2}}}{S_{T_{1}}}\right)=\int_{T_{1}}^{T_{2}}\sigma(S_{t},t)^{2}\mathrm{d}t
$$  

We have succeeded in isolating the percentage total variance for the period $[T_{1},T_{2}]$ on the right-hand side. Given that $S_{t}$ is an asset that trades, the expression on the left-hand side replicates this variance.  

# 15.5.4 THE HEDGE  

The interpretation of the left-hand side in Eq. (15.54) is quite interesting. It will ultimately provide a hedge for the variance swap. In fact, the integral in the expression is a good example of what Ito integrals often mean in modern finance. Consider  

$$
\int_{T_{1}}^{T_{2}}\frac{1}{S_{t}}\mathrm{d}S_{t}
$$  

How do we interpret this expression?  

Suppose we would like to maintain a long position that is made of $1/S_{t}$ units of $S_{t}$ held during each infinitesimally short interval of size $\mathrm{d}t$ , and for all $t.$ . In other words, we purchase $1/S_{t}$ units of the underlying at time $t$ and hold them during an infinitesimal interval dt. Given that at time $t$ , $S_{t}$ is observed, this position can easily be taken. For example, if $S_{t}=100$ , we can buy 0.01 units of $S_{t}$ at a total cost of 1 dollar. Then, as time passes, $S_{t}$ will change by $\mathrm{d}S_{t}$ and the position will gain or lose $\mathrm{d}S_{t}$ dollars for every unit purchased. We readjust the portfolio, since the $S_{t+\mathrm{d}t}$ will presumably be different, and the portfolio needs to be $1/S_{t+\mathrm{d}t}$ units long.  

The resulting gains or losses of such portfolios during an infinitesimally small interval $\mathrm{d}t$ are given by the expression11  

$$
\frac{1}{S_{t}}\left(S_{t+\mathrm{d}t}-S_{t}\right)=\frac{1}{S_{t}}\mathrm{d}S_{t}
$$  

Proceeding in a similar fashion for all subsequent intervals $\mathrm{d}t$ , over the entire period $[T_{1},T_{2}]$ , the gains and losses of such a dynamically maintained portfolio add up to  

$$
\int_{T_{1}}^{T_{2}}\frac{1}{S_{t}}\mathrm{d}S_{t}
$$  

The integral, therefore, represents the trading gains or losses of a dynamically maintained portfolio.12  

The second integral on the left-hand side of Eq. (15.52)  

$$
\int_{T_{2}}^{T_{2}}\mathrm{d}\log(S_{t})=\log\left(S_{T_{2}}\right)-\log\left(S_{T_{1}}\right)
$$  

is taken with respect to time $t$ , and is a standard integral. It can be interpreted as a static position. In this case, the integral is the payoff of a contract written at time $T_{1}$ , which pays, at time $T_{2}$ , the difference between the unknown log $\left(S_{T_{2}}\right)$ and the known $\log\left(S_{T_{1}}\right)$ . This is known as a log contract. The long and short positions in this contract are logarithmic functions of $S_{t}$ .  

In a sense, the left-hand side of Eq. (15.54) provides a hedge of the variance contract. If the trader is short the variance swap, he or she would also maintain a dynamically adjusted long position on $S_{t}$ and be short a static log contract. This assumes complete markets.  

# 15.6 REAL-WORLD EXAMPLE OF VARIANCE CONTRACT  

Variance (volatility) swaps are clearly useful for taking positions with variance (volatility) exposure and hedging. But, each time a new market is born, there are usually further developments beyond the immediate uses. We briefly mention some further applications of the notions developed in this chapter.  

First of all, the $F_{t}^{2}$ , which is the fixed leg of the variance swap, can be used as a benchmark in creating new products. It is important to realize, however, that this price was obtained using the risk-neutral measure and that it is not necessarily an unbiased forecast of future variance for the period $[T_{1},\ T_{2}]$ . Just like the FRA market prices, the $F_{t}$ will include a risk premium. Still, it is the proper price on which to write volatility options.  

The pricing of the variance swap does not necessarily give a volatility that will equal the implied volatility for the same period. Implied volatility comes with a smile and this may introduce another wedge between $F_{t}$ and the ATM volatility.  

Finally, $F_{t}^{2}$ should be a good indicator for risk-managing volatility exposures and also options books.  

Volatility trading, volatility hedging, and arbitraging are still a relatively new area. Below, we will see some recent difficulties that volatility products encountered during the GFC and new positions associated with them.  

# 15.7 VOLATILITY AND VARIANCE SWAPS BEFORE AND AFTER THE GFC—THE ROLE OF CONVEXITY ADJUSTMENTS?  

As we have seen in Section 15.4, in theory, a market maker could sell a variance swap and hedge it by means of a static hedge with a portfolio of put and call options across a range of strike prices, weighted inversely proportional to the squared strike price.  

# 15.7.1 THE DIFFICULTY OF HEDGING VARIANCE SWAPS IN PRACTICE  

In practice, options across the whole range of required strike prices and maturities are either not available or not very liquid. Index options tend to be more liquid than individual stock options. As a result, dealers and market makers before the GFC concentrated on a limited number of strike prices near the spot level. Since the 1990s the over-the-counter market for variance swaps on indices and individual equities developed. However, what many dealers painfully learned during the GFC when markets dropped and volatility spiked is that liquidity is not constant and it tends to disappear in crisis times. In September 2008, as markets plunged, market makers, who tried to rebalance their hedges in accordance with their models, found that liquidity dried up in listed option markets and it was difficult and expensive to hedge exposures. The drop in liquidity was more severe for single name options than for index options. Dealers who were short single-stock variance swaps suffered the most accordingly.  

# EXAMPLE  

When volatility rises by the amount it did in late 2008 and you square it to calculate the payout of a   
variance swap, it’s a nasty product to be short of—and a lot of dealers were short single-stock variance.   
The hedges they had put on just didn’t perform in any way approaching how they would have wanted. hough those positions are theoretically hedgeable with listed options, it assumes that wherever the stock   
price is, you can buy strikes down to zero, but that is never the case. (a quote of Dean Curnutt, president of Macro Risk Advisors, a New York-based derivatives asset management firm, and previously head of institutional equity derivatives sales at Bank of America, Structured Products, April 1, 2010, www.risk.net/1595196)  

One of the features of variance swaps is that they exhibit a constant vega irrespective of the level of the spot price. Since this vega increases linearly with the level of volatility, the dealer needs to buy more options to hedge the swap as volatility increases. This is possible in normal liquid markets, but in crises times when markets fall and risk aversion increases it is difficult to find liquidity options.  

The above example not only illustrates practical difficulties in hedging variance swaps but also the different risk profiles of volatility and variance swaps. The payoff of a variance swap is, as we saw earlier, equal to the difference between the realized variance (that is the square of the volatility) and a preagreed strike level, multiplied by the vega notional. Thus, the payoff of a variance swap is convex in volatility. What does this imply for an investor that is long a variance swap? It means that the investor will benefit from increased gains and reduced losses compared with an alternative exposure to volatility by means of a volatility swap. Similarly, for an investor that is short a variance swap it implies that losses are magnified compared to a volatility swap. Why would someone want to short a variance swap, then? The answer is that, the fair strike of a variance swap is higher than that of a volatility swap. This makes the selling of variance swaps more attractive compared to volatility swaps since the seller can sell at a higher price. Some investors that are long volatility prefer variance swaps to volatility swaps due to the additional convexity and the resulting higher profit potential when volatility suddenly increases. This investor clientele often chooses single-stock variance trades over index variance trades since volatility moves in single stocks tend to be more pronounced than in indices.  

The following reading illustrates one of the lessons learned from the GFC in equity derivatives.  

# EXAMPLE  

“The convexity in variance swaps was an appealing proposition for clients that tended to be long volatility. For the sell side, it involved a big bet on liquidity in vanilla options being continuously available to provide some degree of hedge. In retrospect, variance is not a product that works for the sell side in very volatile markets, [. . .].  

(Structured Products, April 1, 2010, www.risk.net/1595196)  

As the example illustrates, theoretical models assume that continuous hedging is possible in practice. This assumption does not hold in reality and especially in volatile markets hedging becomes difficult and expensive. Some market participants have therefore argued that the variance swap market grew too fast and did not pay attention to the underlying complexities associated with liquidity and hedging costs.  

# 15.7.2 CONVEXITY AND THE DIFFERENCE BETWEEN VARIANCE AND VOLATILITY SWAPS  

# 15.7.2.1 Source of the convexity adjustment  

As we have seen in Section 15.5.4, variance emerges naturally from hedged options trading. However, there is no simple replication strategy for synthesizing a volatility swap despite the preference for volatility quotes over variance quotes by many market participants. To move from variance swaps to volatility swaps prices a convexity adjustment is required. In other words, from a contingent claims or derivatives perspective, variance is the primary underlying and all other volatility payoffs, such as volatility swaps, should be viewed as derivative securities on the variance as underlying. Intuitively, volatility is the square root of variance and therefore a nonlinear function of variance. As a result volatility is theoretically and practically more difficult to hedge and value.  

To explain the difference between volatility and variances swap pricing, let’s look at a naı¨ve strategy that approximates a volatility swap by statically holding a suitably chosen variance contract. In order to make the variance and volatility payoffs agree in value and volatility sensitivity (the first derivative with respect to $\sigma$ ), we can choose the following approximation:  

$$
\sigma-K_{\mathrm{vol}}\approx\frac{1}{2K_{\mathrm{vol}}}(\sigma^{2}-K_{\mathrm{vol}}^{2})
$$  

The above states that $(1/2K_{\mathrm{vol}})$ variance contracts with a strike $K_{\mathrm{vol}}$ can be used to approximate a volatility swap with a notional of $(\$1/\mathrm{vol}$ point for realized volatilities near $K_{\mathrm{vol}}$ . This naı¨ve approximation would also mean that the fair price of future volatility (the stroke for which the volatility swap has zero value) is simply the square root of the fair variance, that is, $K_{\mathrm{vol}}=\sqrt{K_{\mathrm{var}}}$ . Figure 15.10 plots the left-hand side and the right-hand side of Eq. (15.59) for different values of realized volatility and a strike price $K_{\mathrm{vol}}=16\%$ . The payoff of the volatility swap is represented by the dashed line and the payoff of the variance swap is represented by the solid parabola. The figure shows that the actual volatility swap and the corresponding approximation based on a variance swap different considerably when future realized volatility is far away from the strike price. We see that the naı¨ve approximation  

![](1f60565c5645a21f26c003ee62a3b7815a0d9e16804a8bad0d95f68214976639.jpg)  

# FIGURE 15.10  

Payoff of variance and volatility swaps.  

represented by Eq. (15.59) does not work well since it leads to variance swap payoffs that are always greater than the volatility swap payoff. The difference between the two payoffs is called the convexity bias:  

$$
{\mathrm{Convexity~bias}}\approx{\frac{1}{2K_{\mathrm{vol}}}}(\sigma^{2}-K_{\mathrm{vol}}^{2})
$$  

The implication of this is that due to the square term, which is always positive, the fair delivery price for volatility $K_{\mathrm{vol}}$ would lead to higher payoffs from a long variance swap than a long volatility swap position. One approach to correct for this is to lower the fair strike $K_{\mathrm{vol}}$ for a volatility contract so that it is lower than the square root of the fair stroke for a variance contract $K_{\mathrm{var}}$ : $K_{\mathrm{vol}}<\sqrt{K_{\mathrm{var}}}$ . This could be graphically represented by a shift in the dashed line in Figure 15.10 to the left, so that it does not always lie below the parabola.  

So far we have discussed the static replication of variance swap by means of a volatility swap. In theory, the mismatch and convexity bias mentioned above could be addressed by dynamically trading variance swap contracts during the life of the volatility swap. The intuition for this is similar to the replication of a nonlinear stock option payoff by means of delta-hedging using the linear underlying stock price. In practice, unfortunately, there is no liquid market for variance swaps that would allow such dynamic trading of the underlying. If a liquid variance swap market was to develop in the future, then our financial engineering principles provide us with guidance on how such a dynamic replication could be implemented. When we discussed the replication of call and put options we saw that the optimal hedge ratio depends on the assumed future volatility of the underlying (stock). Here the dynamic replication of a volatility swap also requires a model for the volatility of volatility. In other works, the replication strategy would require holding continuous variance-delta equivalent of variance contracts to hedge the volatility derivative. Such a practical implementation would require an arbitrage-free model for the stochastic evaluation of the volatility surface. The next chapter will describe the volatility surface in more detail.  

# 15.7.2.2 The role of convexity in the volatility trading market during the GFC  

In response to the large losses on variance swaps, some banks, in 2009, decided to offer simpler volatility products to clients. In response to hedge fund client demand in Asia in the second quarter of 2009, BNP Paribas brought back volatility swaps which first traded in the late 1990s. Since the volatility swap has a payoff that depends on the volatility and not the variance, it does not have the same convexity as the variance swap. The downside is that it gives less of a profit to investors that long the volatility swap when volatility rises significantly.  

Another downside of volatility swaps is that they do not have the same theoretical replication as variance swaps.  

One of the few banks that continued to offer variance swap was Societe Generale. The bank was able to do this since it reduced risk in early 2008, earlier and by more than many of its competitors. Thus it was better placed to continue to offer variance swaps when the crisis worsened. As we discussed earlier long only clients find variance swaps attractive due to the convexity and additional profit and loss potential that goes with it. From the dealer or market maker perspective variance swaps are theoretically easier to hedge than volatility swaps since they can be replicated with vanilla options, although dealers use different hedging models and practices.  

Innovation in the variance trading has continued and in March 2009, SG CIB started offering an American variance swap. This product embeds an option that allows investors to close their swap position before maturity at its realized value only. The benefit to SG CIB is that the product gives it the right to exist in the trade, which means that it can sell volatility to the client at a lower price.  

In 2009, market participants were very risk averse and often too scared to trade volatility as an asset class. For those willing to take volatility risk, the American variance swap offered an alternative in a very uncertain environment.  

The above reading illustrates that the market for volatility works like any other market in the sense that it responds to supply and demand. Since 2009, market conditions have improved and volatility has dropped to precrisis levels. While the Vix reached a level of 80 on November 20, 2008, it then fell to around 40 by the end of March 2009 and traded around 11 by June 2014. If volatility was to remain at these pre-GFC levels, then variance swaps may be viewed again more favorably than volatility swaps again, since the breakeven points on the upside, beyond which variance are more profitable than volatility swaps, will fall. The return on the variance swaps for a market maker will depend on the level of volatility and the liquidity of stock options required to hedge variance positions.  

# 15.7.3 INTRODUCTION TO VOLATILITY AS AN ASSET CLASS  

Acceptance of implied volatility and implied correlation as an asset class is growing. The main players are (i) institutional investors, (ii) hedge funds, and (iii) banks. This increased liquidity facilitates the engineering of structured products with embedded volatility.  

# EXAMPLE  

It appears that institutional investors are migrating to four types of strategies for going long exposure to implied volatility. Among the largest institutional investors, variance swap-based strategies are the most popular.  

Variance swaps offer the easiest and most liquid way to get exposure to volatility. Institutional investors and hedge funds are the target audience for the new services offered in this field. These services enable customers to trade variance swaps through Bloomberg terminals. Volumes in the inter-dealer market and with clients prompted the move. Variance swaps are used to go long or short volatility on an index or equity with a selected maturity.  

Pure volatility instruments, such as volatility swaps and variance swaps, make sense for institutional investors, because volatility is both a diversifier on the downside and a global hedge on an equity portfolio. Institutional investors such as pension funds and insurance companies clearly need to diversify. While they are moving to other asset classes, such as hedge funds, they also do not want to reduce their exposure to equity markets, particularly if there is a good chance of equity markets performing well. With this in mind, they are increasingly turning to long-term volatility strangles.  

The main external driver of the current ongoing rise in volatility is M & A activity.  

Requests for forward volatility strategies to hedge structured products are also on the rise, particularly among private banks. These strategies fit their needs, as dealers sold a lot of forward volatility certificates and warrants to them last year.  

(Thomson Reuters IFR, 2004)  

# 15.7.4 POST-GFC REGULATION, STANDARDIZATION AND EXCHANGE TRADED VOLATILITY PRODUCTS  

In addition to supply and demand the market for volatility is also influenced by regulation. OTC derivatives regulation in Europe and the United States is pushing markets toward standardization and exchange trading.  

# 15.7.4.1 Variance futures  

The properties of the CBOE Volatility Index, or VIX, are now relatively well understood.13 The Vix has a negative correlation with the S&P500 and this correlation tends to increase in crisis times. Thus the VIX can be used as a hedge or a “tail risk” hedge against extreme negative events. Unfortunately, the VIX is just a mathematical formula and not an investable index. It is not tradable and cannot be purchased. Fortunately there are several ways to benefit from a rise in the VIX by using exchange traded instruments: VIX futures, variance futures, VIX options, S&P options and volatility-related exchange traded funds (ETFs) and exchange traded notes (ETNs). There is also a myriad of over-the-counter products linked to the VIX.  

On December 10, 2012, the CBOE listed the S&P 500 Variance futures.  

The contract is not a variance swap since it depends on the realized variance of the S&P500, but it does allow investors to speculate on the realized S&P500 volatility. Figure 15.11 shows the open interest and volume of the S&P500 variance futures from 2012 until 2013.  

Below is a term sheet for the S&P500 Variance Futures  

<html><body><table><tr><td>Description:</td><td>S&P 5Oo Variance futures are exchange-traded futures contracts based on the realized variance of the S&P 500 Composite Stock Price Index (S&P 5O0). The final settlement value for the contract will be determined based on a standardized formula for calculating the realized variance of the S&P 5O0 measured from the time of initial listing until</td></tr><tr><td>Contract size:</td><td>expiration of the contract. The standard formula inputs for discount factor and daily interest rate are determined by the Exchange. The contract multiplier for the S&P 50o Variance futures contract is $1 per variance unit. One contract equals one variance unit.</td></tr><tr><td>Trading hours:</td><td>8:30 a.m.-3:15 p.m. (Chicago time). All Orders, quotes, cancellations and Order modifications for S&P 5o Variance futures </td></tr><tr><td></td><td>during trading hours must be received by the Exchange by no later than 3:14:59 p.m. Chicago time and will be automatically rejected if received by the Exchange during trading hours after 3:14:59 p.m. Chicago time.</td></tr><tr><td>Contract months:</td><td>The Exchange may list contract months on S&P 50o Variance futures that correspond to the listed contract months for S&P 500 Index options listed on Chicago Board Options Exchange, Incorporated (CBOE).</td></tr></table></body></html>  

![](aba7185781c2033b2c254edad751987b472021183fc07ef82a66cbeb03ce5a97.jpg)  
S&P500 VARIANCE FUTURES   
Source: CBOE  

# FIGURE 15.11  

Open interest and volume of the S&P500 variance futures.  

In addition to the S&P500 VIX and Variance futures, the CBOE offers futures on several other US equity indices such as  

VSW CBOE Short-Term Volatility Index Futures (VSW) VX CBOE S&P 500 Volatility Index (VIX) Futures  

# 538 CHAPTER 15 TOOLS FOR VOLATILITY ENGINEERING, VOLATILITY SWAPS  

VU CBOE Russell 2000 Volatility Index (RVX) Futures   
VN CBOE Nasdaq-100 Volatility Index (VXN) Futures emerging markets indices,   
VXEM CBOE Emerging Markets ETF Volatility Index (VXEEM) Security Futures VXEW CBOE Brazil ETF Volatility Index (VXEWZ) Security Futures and commodities   
CBOE Gold ETF Volatility Index (GVZ) Security Futures   
CBOE Crude Oil ETF Volatility Index (OVX) Security Futures.  

This shows the widespread acceptance of volatility as an asset class. It also highlights the fact that market participants are become more discerning regarding different types of volatility exposure depending on country and asset class.  

# 15.7.4.2 Variance swaps  

Variance swaps have been traded over-the-counter for almost 20 years, but recently, there have been plans to list variance swaps on exchanges. The following example discusses plans by Eurex to move over-the-counter variance swaps on to exchanges.  

# EXAMPLE  

“Plans to move over-the-counter variance swaps on to exchanges are in full swing in Europe as the Eurex derivatives exchange prepares to list futures-style contracts tracking EuroStoxx 50 variance in mid-2014.  

The exchange is not the first to attempt a listed alternative that produces the same pay-off as the widely traded OTC product. The CBOE launched S&P 500 variance futures a year ago (see “Replicating variance”), but the contract has struggled to gain traction. Since the launch last October, open interest has built up to about 32,000 contracts and volume remains lumpy with relatively few days of active trading.  

Despite the inauspicious start for the US version, some traders remain optimistic there could be support for a listed version in Europe, where many asset managers looking to trade volatility do not have OTC approval, while the VStoxx futures have just a fraction of the liquidity seen in VIX contracts.  

“The demand is there,” said Rory Hill, EMEA co-head of equity derivatives at Citigroup. “After the crisis, closing down and novating OTC risk became an issue. Now, anything that’s OTC, institutions and funds want to try to get listed. Client flows are now pushing volumes on to exchanges and even banks themselves don’t want OTC exposure any more.”  

Sluggish demand for the CBOE product has been attributed to a variety of factors—not least the ample liquidity available in the US OTC variance swaps, where 10-year contracts can trade tighter than six-month maturities in Europe.  

“The S&P variance OTC market is very healthy and very liquid, so there hasn’t been a natural need. Most   
of the clients trading the product are already set up to trade OTC with the top 10 dealers, so their needs are   
already fulfilled,” said Mark Chen, head of equity derivatives index trading at Citigroup in New York. [. . .]  

A number of dealers and hedge funds have already expressed interest in supporting the new product, subject to the right fee structure and incentives. But the real driver is likely to come from regulatory pressure as swaps are pushed into central clearing on a product-by-product basis.  

“What could change things is when the regulatory requirement to clear the OTC products through CCPs goes live. Then we might see some clients move to the listed platform,” said Bornhauser.  

Variance swap activity stalled to a near standstill in the wake of the crisis—Citi’s Hill estimates that volume plummeted to around $20\%$ of its 2006 07 peak, but has since returned to as much as $50\%$ , though that is concentrated in index trades. “There’s still some single-stock vol swap exposure but single-stock variance swaps died a death. Most of the variance swap flow is concentrated”  

(Thomson Reuters IFR 2011, November 23, 2013)  

Regulation restricts the ability of certain investors to buy OTC products. The costs of hedging and funding complex products has also increased in banks, thus explaining the increased attraction of exchange traded assets.  

# 15.7.5 THE HEDGE  

In Section 15.5, we discussed the potential uses and users of variance swaps. But who were the counterparties in variance swaps in the run up to the GFC? It turns out that variance swaps were not just attractive to investors but also for dealers in investment banks with large structured products businesses.  

# EXAMPLE  

Variance swaps became a very critical part of the risk recycling process for dealers that were running structured products books and had a short correlation exposure to offset. That was a big driver of the growth of the market in the early part of the last decade.  

(Structured Products, April 1, 2010, www.risk.net/1595196)  

The above example refers to dealers in large investment banks who had sold structured products to their clients. Equity structured products, for example, often involved a downside protection to the client. The product would thus pay when markets fell. When markets fall, correlations tend to rise sharply. This would leave the seller of such products short correlation. Thus one way of hedging such structured product exposure was to go long correlation by means of variance swaps. This is akin to buying protection on unexpected increases in correlations. Who would sell such protection? Before the financial crisis many hedge funds went short correlation. Thus, a hedge fund would go short a variance swap on an index and go long a variance swap on the constituent stock. This created a short position for the hedge fund and a long position for the dealer. We discuss correlation trading and correlation swaps in more detail in the next chapter.  

# 15.8 WHICH VOLATILITY?  

This chapter dealt with four notions of volatility. These must be summarized and distinguished clearly before we move on to discussion of the volatility smile in the next chapter.  

When market professionals use the term “volatility,” chances are they refer to Black Schole’s implied volatility. Otherwise, they will use terms such as realized or historical volatility. Local volatility and variance swap volatility are also part of the jargon. Finally, cap-floor volatility and swaption volatility are standard terms in financial markets.  

As explained in Chapter 9, implied volatility is simply the value of $\sigma$ that one would plug into the Black Scholes formula to obtain the fair market value of a plain vanilla option as observed in the markets. For this reason, it is more correct to call it Black Scholes implied vol or Black volatility in the case of interest rate derivatives. It is quite conceivable for a professional to use a different formula to price options, and the volatility implied by this formula would naturally be different. The term implied volatility is, thus, a formula-dependent variable.  

We can attach the following definitions to the term “volatility.”  

First, there is the class of realized volatilities. This is closest to what is contained in statistics courses. In this case, there is an observed or to-be-observed data set, a “sample,” $\{x_{1},...x_{n}\}$ , which can be regarded as a realization of a possibly vector-stochastic process, $x_{t},$ defined under some real-world probability $P$ . The process $x_{t}$ has a second moment  

$$
\sigma_{t}=\sqrt{E_{t}^{P}[(x_{t}-E_{t}^{P}[x_{t}])^{2}]}
$$  

We can devise an estimator to estimate this $\sigma_{t}$ . For example, we can let  

$$
\hat{\sigma}_{t}=\sqrt{\frac{\sum_{i=0}^{m}{(x_{t-i}-\overline{{x}}_{t}^{m})}^{2}}{m}}
$$  

where $\overline{{x}}_{t}^{m}$ is the $m$ -period sample mean:  

$$
\ {\overline{{x}}}_{t}^{m}={\frac{\sum_{i=0}^{m}x_{t-i}}{m}}
$$  

Such volatilities measure the actual real-world fluctuations in asset prices or risk factors. One example of the use of this volatility concept was shown in this chapter. The $\sigma_{t}^{2}$ defined earlier represented the floating leg of the variance swap discussed here.  

The next class is implied volatility.14 There is an observed market price. The market practitioner has a pricing formula (e.g., Black Scholes) or procedure (e.g., implied trees) for this price. Then, implied volatility is that “volatility” number, or series of numbers, which must be plugged into the formula in order to recover the fair market price. Thus, let $F(S_{t},t,r,\sigma_{t},T)$ be the Black Scholes price for a European option written on the underlying $S_{t},$ with interest rates $r$ and expiration $T.$ . At time $t$ , $\sigma_{t}$ represents the implied volatility if we solve the following equation (nonlinearly) for $\sigma_{t}$ :  

$$
F(S_{t},t,r,\sigma_{t},T)=\mathrm{observedprice}
$$  

This implied volatility may differ from the realized volatility significantly, since it incorporates any adjustments that the trader feels he or she should make to expected realized volatility. Implied volatility may be systematically different than realized volatility if volatility is stochastic and if a risk premium needs to be added to volatility quotes. Violations of Black Scholes assumptions may also cause such a divergence.  

Local volatility is used to represent the function $\sigma(.)$ in a stochastic differential equation:  

$$
\mathrm{d}S(t)=\mu(S,t)\mathrm{d}t+\sigma(S,t)S_{t}\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

However, local volatility has a more specific meaning. Suppose options on $S_{t}$ trade in all strikes, $K$ , and expirations $T_{\mathbf{\delta}}$ , and that the associated arbitrage-free prices, $\{C(S_{t},t,K,T)\}$ , are observed for all $K,T.$ . Then the function $\sigma(S_{t},t)$ is the local volatility, if the corresponding SDE successfully replicates all these observed prices either through a Monte Carlo or PDE pricing method.  

In other words, local volatility is a concept associated with calibration exercises. It can be regarded as a generalization of Black Scholes implied volatility. The implied volatility replicates a single observed price through the Black Scholes formula. The local volatility, on the other hand, replicates an entire surface of options indexed by $K$ and $T$ , through a pricing method. As a result, we get a volatility surface indexed by $K$ and $T$ , instead of a single number as in the case of Black Scholes implied volatility. Finally, in this chapter we encountered the variance swap volatility. This referred to the expectation of the average future squared deviations. But, because the expectation used the risk-neutral measure, it is different from real-world volatility.  

Discussions of the volatility smile relate to these volatility notions. The implied volatility is obviously of interest to most traders but it cannot exist independently of realized volatility. It is natural to expect a close relationship between the two concepts.15 Also, as volatility trading develops, more and more instruments are written that use the realized volatility as some kind of underlying risk factor for creating new products. The variance swap was only one example.  

# 15.9 CONCLUSIONS  

This chapter provided a brief introduction to a sector that may, in the future, play an even more significant role in financial market strategies. Our purpose was to show how we can isolate the volatility of a risk factor from other related risks, and then construct instruments that can be used to trade it. An important point should be emphasized here. The introductory discussion contained in this chapter deals with the case where the volatility parameter is a function of time and the underlying price only. These methods have to be modified for more complex volatility specifications.  

# SUGGESTED READING  

Rebonato (2000) and (2002) are good places to start getting acquainted with the various notions of volatility. Bossu et al. (2005) provide a good introduction to variance swaps. Some of the material in this chapter comes directly from Demeterfi et al. (1999), where the reader will find proper references to the literature as well. The important paper by Dupire (1992) and the literature it generated can be consulted for local volatility.  

# EXERCISES  

1. Read the quote carefully and describe how you would take this position using volatility swaps. Be precise about the parameters of these swaps.  

a. How would you price this position? What does pricing mean in this context anyway Which price are we trying to determine and write in the contract?   
b. In particular, do you need the correlations between the two markets?   
c. Do you need to know the smile before you sell the position?   
d. Discuss the risks involved in this volatility position.  

# Volatility Swaps  

A bank is recommending a trade in which investors can take advantage of the wide differential between Nasdaq 100 and S&P500 longer-dated implied volatilities.  

Two-year implied volatility on the Nasdaq 100 was last week near all-time highs, at around $45.7\%$ , but the tumult in tech stocks over the last several years is largely played out, said [a] global head of equity derivatives strategy in New York. The tech stock boom appears to be over, as does the most eye-popping part of the downturn, he added. While there will be selling pressure on tech companies over the next several quarters, a dramatic sell-off similar to what the market has seen over the last six months is unlikely.  

The bank recommends entering a volatility swap on the differential between the Nasdaq and the S&P, where the investor receives a payout if the realized volatility in two years is less than about $21\%$ , the approximate differential last week between the at-the-money forward two-year implied volatilities on the indices. The investor profits here if, in two years, the realized two-year volatility for the Nasdaq has fallen relative to the equivalent volatility on the S&P.  

It might make sense just to sell Nasdaq vol, said [the trader], but it’s better to put on a relative value trade with the Nasdaq and S&P to help reduce the volatility beta in the Nasdaq position. In other words, if there is a total market meltdown, tech stocks and the market as a whole will see higher implied vols. But volatility on the S&P500, which represents stocks in a broader array of sectors, is likely to increase substantially, while volatility on the Nasdaq is already close to all-time highs. A relative value trade where the investor takes a view on the differential between the realized volatility in two years time on the two indices allows the investor to profit from a fall in Nasdaq volatility relative to the S&P.  

The two-year sector is a good place to look at this differential, said [the trader]. Two years is enough time for the current market turmoil, particularly in the technology sector, to play itself out, and the differential between two-year implied vols, at about $22\%$ last week, is near all-time high levels. Since 1990, the realized volatility differential has tended to be closer to $10.7\%$ over long periods of time.  

[The trader] noted that there are other means of putting on this trade, such as selling two-year at-the-money forward straddles on Nasdaq volatility and buying two-year at-themoney forward straddles on S&P vol. (Derivatives Week (now part of GlobalCapital), October 30, 2000)  

2. The following reading deals with another example of how spread positions on volatility can be taken. Yet, of interest here are further aspects of volatility positions. In fact, the episode is an example of the use of knock-in and knock-out options in volatility positions.  

a. Suppose the investor sells short-dated (1-month) volatility and buys 6-month volatility. In what sense is this a naked volatility position? What are the risks? Explain using volatility swaps as an underlying instrument.   
b. Explain how a 1-month break-out clause can hedge this situation.   
c. How would the straddles gain value when the additional premium is triggered?   
d. What are the risks, if any, of the position with break-out clauses?  

e. Is this a pure volatility position?  

Sterling volatility is peaking ahead of the introduction of the euro next year. A bank suggests the following strategy to take advantage of the highly inverted volatility curve. Sterling will not join the euro in January and the market expects reduced sterling positions. This view has pushed up one-month sterling/Deutsche mark vols to levels of $12.6\%$ early last week. In contrast, six-month vols are languishing at under $9.2\%$ . This suggests selling shortdated vol and buying six-month vols. Customers can buy a six-month straddle with a onemonth break-out clause added to replicate a short volatility position in the one-month maturity. This way they don’t have a naked volatility position. (Based on an article in Derivatives Week (now part of GlobalCapital).)  

# MATLAB EXERCISES  

3. (Variance swap price). Write a MATLAB program to illustrate the variation of the price of an (equity) variance swap with respect to the change in the mean return of the underlying stock and also show this on a graph. Use the following parameters for the specification of the stochastic process followed by the underlying. • $S(0)=100\$ ; $T=1$ ; $r=8\%$ ; $\sigma=30\%$ ; $\mu=10\%$  

4. (Volatility swap price). Write a MATLAB program to show the invariance of the volatility payoff of a delta hedged long call for the various frequency of delta adjustment until the time of expiry of the call. Use the following data: $S(0)=100$ ; $K=105$ ; $T=1$ ; $r=8\%$ ; $\sigma=30\%$ and realized volatility $=50\%$ Plot the graph for the volatility payoff for 20 simulations for the adjustment frequencies 10, 20, 50, 100, and 500.  

This page intentionally left blank  