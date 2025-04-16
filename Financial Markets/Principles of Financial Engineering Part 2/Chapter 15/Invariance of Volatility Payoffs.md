---
tags:
  - '#black_scholes_model'
  - '#delta_hedging'
  - '#dynamic_hedging'
  - '#imperfect_volatility_positions'
  - '#implied_volatility'
  - '#static_volatility_position'
  - '#straddles'
  - '#variance_vega'
  - '#volatility_engineering'
  - '#volatility_payoffs'
---
# 15.3 INVARIANCE OF VOLATILITY PAYOFFS  

In previous chapters, convexity was used to isolate volatility as a risk. In Chapters 9 and 10, we showed how to convert the volatility of an underlying into "cash," and with that took the first steps toward volatility engineering.  

Using the methods discussed in Chapters 9 and 10, a trader can hedge and risk-manage expo-. sures with respect to volatility movements. Yet, these are positions influenced by variables other than volatility. Consider a speculative position taken by an investor..  

Let $S_{t}$ be a risk factor and suppose an investor buys $S_{t}$ volatility at time $t_{0}$ for a future period denoted by $[t_{1},T]$ $T$ being the expiration of the contract. As in every long position, this means that the investor is anticipating an increase in realized volatility during this period. If realized volatility during $[t_{1},T]$ exceeds the volatility "purchased" at time $t_{0}$ the investor will benefit. Thus far this is not very different from other long positions. For example, a trader buys a stock and benefits if the stock price goes up. He or she can buy a fixed receiver swap and benefit if the swap value goes up (the swap rate goes down). Similarly, in our present case, we receive a "fixed" volatility and benefit if the actual volatility exceeds this level.  

By buying call or put options, straddles, or strangles, and then delta-hedging these positions, the trader will, in general, end up with a long position that benefits if the realized volatility increases, as was shown in Chapters 9 and 10. Yet, there is one major difference between such volatility posi-. tions and positions taken on other instruments such as stocks, swaps, forward rate agreements (FRAs), and so on. Consider Figure 15.1a, that shows a long position on a stock funded by a money. market loan. As the stock price increases, the position benefits by the amount. $S_{t_{1}}-S_{t_{0}}$ . This potential payoff is known and depends only on the level of $S_{t_{1}}$ . In fact, it depends on $S_{t}$ linearly. In Figure 15.1b, we have a short-dated discount bond position. As the yield decreases, the position. gains. Again, we know how much the position will be making or losing, depending on the move-. ments in the yield, $y_{t},$ if convexity gains are negligible.  

A volatility position taken via, say, straddles, is fundamentally different from this as the payoff diagram will move depending on the path followed by variables other than volatility. For example, a change in (i) interest rates, (ii) the underlying asset price, or (iii) the level of implied volatility may lead to different payoffs at the same realized volatility level.  

Variance (volatility) swaps, on the other hand, are pure volatility positions. Potential gains or. losses in positions taken with these instruments depend only on what happens to realized volatility until expiration. This chapter shows how volatility engineering can be used to set up such contracts and to study their pricing and hedging. We begin with imperfect volatility positions..  

# 15.3.1 IMPERFECT VOLATILITY POSITIONS  

In financial markets, a volatility position is often interpreted to be a static position taken by buying. and selling straddles, or a dynamically maintained position that uses straddles or options. As  

![](images/0c1513dc5534d4a84d2b7eafe9d6ee378cbfe1ade63a5693475ef3fd108ca7d6.jpg)  

# FIGURE 15.1  

Long position on a stock (funded by a money market loan) and long discount bond position.  

mentioned previously, these volatility positions are not the right way to price, hedge, or riskmanage volatility exposure. In this section, we go into the reasons for this. We consider a simple position that consists of a dynamically hedged single-call option.  

# 15.3.1.1 A dynamic volatility position  

Consider a volatility exposure taken through a dynamically maintained position using a plain vanilla call. To simplify the exposition, we impose the assumptions of the Black-Scholes world where there are no dividends; the interest rate,. $r_{:}$ and implied volatility, $\sigma$ , are constant; there are no transaction costs; and the underlying asset follows a geometric process. Then the arbitrage-free value of a European call $C(S_{t},t)$ will be given by the Black-Scholes formula3:  

$$
C(S_{t},t)=S_{t}\int_{-\infty}^{d_{1}}{\frac{1}{\sqrt{2\pi}}}e^{-{\frac{1}{2}}x^{2}}\mathrm{d}x-e^{-r(T-t)}K\int_{-\infty}^{d_{2}}{\frac{1}{\sqrt{2\pi}}}e^{-{\frac{1}{2}}x^{2}}\mathrm{d}x
$$  

where $S_{t}$ is the spot price, and $K$ is the strike. The $d_{i},i=1,2$ , are given by  

$$
d_{i}={\frac{\log(S_{t}/K)\pm(1/2)\sigma^{2}(T-t)+r(T-t)}{\sigma{\sqrt{T-t}}}}
$$  

For simplicity, and without loss of generality, we let  

$$
r=0
$$  

This simplifies some expressions and makes the discussion easier to follow.  

Now consider the following simple experiment. A trader uses the Black-Scholes setting to take a dynamically hedged long position on implied volatility. Implied volatility goes up. Suppose the trader tracks the gains and losses of the position using the corresponding variance-vega. What would be this trader's possible gains in the following specific case? Consider the following simple setup.  

1. The parameters of the position are as follows:  

$$
K=S_{t_{0}}=100
$$  

$$
\sigma=20\%
$$  

Initially we let $t_{0}=0$  

2. The trader expects an increase in the implied volatility from. $20\%$ to $30\%$ , and considers taking a long volatility position.   
3. To buy into a volatility position, the trader borrows an amount equal to $100C\left(S_{t},t\right)$ , and buys.   
100 calls at time $t_{0}$ with funding cost $r=0$   
4. Next, the position is delta-hedged by short-selling. $C_{s}$ units of the underlying per call to obtain. the familiar exposure shown in Figure 15.2.  

![](images/57a7b0480024b3f74ab6094f0ef60c887751fc0005efd4994c4009fc659cfea2.jpg)  

# FIGURE 15.2  

Delta-hedged long call position.  

In this example, there are about 1.2 months to the expiration of this option, the option is at-the money, and the initial implied volatility is $20\%$  

It turns out that in this environment, even when the trader's anticipations are borne out, the payoffs from the volatility position may vary significantly, depending on the path followed by $S_{t}$ The implied volatility may move from. $20\%$ to $30\%$ as anticipated, but the position may not pay the. expected amount. The following example displays the related calculations.  

# EXAMPLE  

We can calculate the relevant Greeks and payoff curves using Mathematica or MATLAB.   
First, we obtain the initial price of the call as.  

$$
C(100,t_{0})=2.52
$$  

Multiplying by 100, the total position is worth $\$232$ . Then, we get the implied delta of this position by first calculating the $S_{t}$ -derivative of $C(S_{t},t)$ evaluated at $S_{t_{0}}=100$ , and then. multiplying by 100:.  

$$
100\bigg(\frac{\partial C(S_{t},t)}{\partial S_{t}}\bigg)=51.2
$$  

Hence, the position has $+51$ -delta. To hedge this exposure, the trader needs to short 51 units of the underlying and make the net delta exposure approximately equal to zero.  

Next, we obtain the associated gamma and the (variance) vega of the position at $t_{0}$ Using the given data, we get  

$$
{\mathrm{Gamma}}=100\bigg[\frac{\hat{\sigma}^{2}C(S_{t},t)}{\hat{\sigma}S_{t}^{2}}\bigg]=6.3
$$  

$$
\mathrm{Variancevega}=100\left[{\frac{\partial C(S_{t},t)}{\partial\sigma^{2}}}\right]=3152
$$  

The change in the option value, given a change in the (implied) variance, is given approximately by  

$$
100[\partial C(S_{t},t)]\cong(3152)\partial\sigma^{2}
$$  

This means that, everything else being constant, if the implied volatility rises suddenly from $20\%$ to $30\%$ , the instantaneous change in the option price will depend on the product of. these numbers and is expected to be  

$$
\begin{array}{c}{{100[\partial C(S_{t},t)]\cong3152(0.09-0.04)}}\ {{{}}}\ {{=157.6}}\end{array}
$$  

In other words, the position is expected to gain about $\$158$ , if everything else remained. constant.  

The point is that the trader was long implied volatility, expecting that it would increase, and it did. So if the volatility does go up from. $20\%$ to $30\%$ , is this trader guaranteed to gain the. $\$157.6?$ Not necessarily. Let us see why not..  

Even in this simplified Black-Scholes world, the (variance) vega is a function of $S_{t},t,r,$ as well as $\sigma^{2}$ . Everything else is not constant and the $S_{t}$ may follow any conceivable trajectory. But, and this is the important point, when $S_{t}$ changes, this in turn will make the vega change as well. The following table shows the possible values for variance-vega depending on the value assumed by $S_{t}.$ within this setting..  

<html><body><table><tr><td>'s Vega</td></tr><tr><td>80 0.0558</td></tr><tr><td>90 7.4666</td></tr><tr><td>100 31.5234</td></tr><tr><td>110 10.6215</td></tr><tr><td>120 0.5415</td></tr></table></body></html>  

Thus, if the expectations of the trader are fulfilled, the implied volatility increases to $30\%$ , but, at the same time, if the underlying price moves away from the strike, say to. $S_{t_{1}}=80$ , the same calculation will become approximately:  

$$
\begin{array}{c}{{\mathrm{Vega}(\partial\sigma^{2})\cong5.6(0.09-0.04)}}\ {{\mathrm{}}}\ {{\mathrm{~=~}0.28}}\end{array}
$$  

Hence, instead of an anticipated gain of. $\$157.6$ , the trader could realize almost no gain at all. In. fact, if there are costs to maintaining the volatility position, the trader may end up losing money. The reason is simple: as. $S_{t}$ changes, the option's sensitivity to implied volatility, namely the vega, changes as well. It is a function of. $S_{t}$ As a result, the outcome is very different from what the trader was originally expecting.  

For a more detailed view on how the position's sensitivity moves when $S_{t}$ changes, consider Figure 15.3 where we plot the partial derivative:.  

$$
100\frac{\partial\mathrm{variancevega}}{\partial S_{t}}
$$  

Under the present conditions, we see that as long as $S_{t}$ remains in the vicinity of the strike $K$ the trader has some exposure to volatility changes. But as soon as $S_{t}$ leaves the neighborhood of $K$ this exposure drops sharply. The trader may think he or she has a (variance) volatility position, but, in fact, the position costs money, and may not have any significant variance exposure as the underlying changes right after the trade is put in place. Thus, such classical volatility positions are imperfect ways of putting on volatility trades or hedging volatility exposures.  

![](images/6785e0aa035a11c760c69be7b774d0c279d64fda0459314e42da788e0c45a119.jpg)  

# FIGURE 15.3  

Vega as a function of the price of the underlying.  

# 15.3.2 VOLATILITY HEDGING  

The outcome of such volatility positions may also be unsatisfactory if these positions are maintained as a hedge against a constant volatility exposure in another instrument. According to what was discussed, movements in $S_{t}$ can make the hedge disappear almost completely and the trader may hold a naked volatility position in the end. An institution that has volatility exposure may use a hedge only to realize that the hedge may be slipping over time due to movements unrelated to volatility fluctuations.  

Such slippage may occur for more reasons than just a change in. $S_{t}$ In reality, there are also (i) smile effects, (ii) interest rate effects, and (iii) shifts in correlation parameters in some instru-. ments. Changes in these can also cause the classical volatility payoffs to move away from initially perceived levels.  

# 15.3.3 A STATIC VOLATILITY POSITION  

If a dynamic delta-neutral option position loses its exposure to movements in. $\sigma^{2}$ and, hence, ceases to be useful as a hedge against volatility risk, do static positions fare better?  

A classic position that has volatility exposure is buying (selling) ATM straddles. Using the same numbers as above, Figure 15.4 shows the joint payoff of an ATM call and an ATM put struck at $K=100$ . This position is made of two plain vanilla options and may suffer from a similar defect. The following example discusses this in more detail.  

![](images/31e2c8ff351038603298dad221642bcea7fb64a471228d083a23e18e6a87e2fc.jpg)  

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

Then, we substitute the appropriate values of $S_{t},\:t,\:\sigma^{2}$ in the formula. Doing this for some. values of interest for. $S_{t}$ , we obtain the following sensitivity factors:  

<html><body><table><tr><td>'s</td><td>Vega</td></tr><tr><td>80</td><td>11</td></tr><tr><td>90</td><td>1493</td></tr><tr><td>100</td><td>6304</td></tr><tr><td>110</td><td>2124</td></tr><tr><td>120</td><td>108</td></tr></table></body></html>  

According to these numbers, if. $S_{t}$ stays at 100 and the volatility moves from. $20\%$ to $30\%$ the static position's value increases approximately by  

$$
\begin{array}{c}{{\partial\operatorname{Straddle}\cong6304(0.09-0.04)}}\ {{}}\ {{=315.2}}\end{array}
$$  

As expected, this return is about twice as big as in the previous example. The straddle has more sensitivity to volatility changes. But, the option's responsiveness to volatility movements is again not constant, and depends on factors that are external to what happens to volatility. The table shows that if $S_{t}$ moves to 80, then even when the trader's expectation is justified and volatility moves from $20\%$ to $30\%$ , the position's mark-to-market gains will go down to about 0.56.  

![](images/06b7f34621dda0d5b9d89e7a23d334acf3f7d7b43a53cf66c2802a323c90436d.jpg)  

# FIGURE 15.5  

Straddle's sensitivity with respect to implied volatility for different values of $S_{t}.$  

Figure 15.5 shows the behavior of the straddle's sensitivity with respect to implied volatility for different values of. $S_{t}$ . We see that the volatility position is again not invariant to changes in external variables. However, there is one major difference from the case of a dynamically maintained portfolio. Static non-delta-hedged positions using straddles will benefit from actual (realized) movements in. $S_{t}$ . For example, if. $S_{t}$ stays at 80 until expiration date $T,$ the put leg of the straddle would pay 20 and the static volatility position would gain. This is regardless of how the vega of the position changed due to movements in $S_{t}$ over the interval. $[t_{0},T]$  
