---
tags:
  - '#black_scholes_formula'
  - '#delta'
  - '#gamma'
  - '#gamma_trading'
  - '#greeks'
  - '#implied_volatility'
  - '#option_sensitivity'
  - '#theta'
  - '#vega'
  - '#vega_hedging'
---
# 9.6 THE GREEKS AND THEIR USES  

The Black-Scholes formula gives the value of a vanilla call (put) option under some specific assumptions. Obviously, this is useful for calculating the arbitrage-free value of an option. But a financial engineer needs methods for determining how the option premium, $C(t)$ , changes as the variables or the parameters in the formula change within the market environment. This is important since the assumptions used in deriving the Black-Scholes formula are unrealistic. Traders, market. makers, or risk managers must constantly monitor the sensitivity of their option books with respect to changes in $S_{t},r,t_{:}$ or $\sigma$ . The role of Greeks should be well understood.  

# EXAMPLE  

A change in $\sigma$ is a good example. We motivated option positions essentially (but not fully) as positions taken on volatility. It is clear that volatility is not constant as assumed in the Black-Scholes world. Once an option is bought and delta-hedged, the hedge ratio. $C_{\mathrm{s}}$ and the $C_{\mathrm{ss}}$ both depend on the movements in the volatility parameter $\sigma$  

Hence, the "hedged' option position will still be risky in many ways. For example, depending on the way changes in $\sigma$ and $S_{t}$ affect the $C_{s s}$ , a market maker may be correct in his or her forecast of how much $S_{t}$ will fluctuate, yet may still lose money on a long option position.  

A further difficulty is that option sensitivities may not be uniform across the strike price $K$ or expiration $T.$ For options written on the same underlying, differences in. $K$ and $T$ lead to what are called smile effects and term structure effects, respectively, and should be taken into account carefully.  

Option sensitivity parameters are called the "Greeks' in the options literature. We discuss them next and provide several practical examples.  

# 9.6.1 DELTA  

Consider the Black-Scholes formula $\textit{C}(S_{t},t|r,\sigma,T,K)$ . How much would this theoretical price change if the underlying asset price,. $S_{t},$ moved by an infinitesimal amount?.  

One theoretical answer to this question can be given by using the partial derivative of the function with respect to $S_{t}$ This is by definition the delta at time $t!$  

$$
\mathrm{delta}=\frac{\partial C(S_{t},t\mid r,\sigma,T,K}{\partial S_{t}}
$$  

This partial derivative was denoted by. $C_{s}$ earlier. Note that delta is the local sensitivity of the option price to an infinitesimal change in. $S_{t}$ only, which incidentally is the reason behind using partial derivative notation..  

To get some intuition on this, remember that the price curve for a long call has an upward slope in the standard. $C(t)$ $S_{t}$ space. Being the slope of the tangent to this curve, the delta of a long call. (put) is always positive (negative). The situation is represented in Figure 9.9. Here, we consider. three outcomes for the underlying asset price represented by. $S_{A},S_{B}$ and $S_{C}$ and hence obtain three points, $A,B$ and $C$ , on the option pricing curve. At each point, we can draw a tangent. The slope. of this tangent corresponds to the delta at the respective price..  

At point $C$ , the slope, and hence, the delta is close to 0, since the curve is approaching the horizontal axis as $S_{t}$ falls. At point $B$ , the delta is close to 1, since the curve is approaching a line with slope. $+1$ At point $A$ , the delta is in the "middle," and the slope of the tangent is between O and 1..  

![](images/4133932cbc663f4ece954559fa4c2682294e12b12a8dece3791886868ecc2bc8.jpg)  

# FIGURE 9.9  

Payoff of a long call position and slope.  

Thus, we always have $0<d e l t a<1$ in case of a long call position. As mentioned earlier, when the option is ATM, the delta is close to 0.5.  

# 9.6.1.1 Convention  

Market professionals do not like to use decimal points. The convention in option markets is to think about trading, not one, but 100 options, so that the delta of option positions can be referred to in whole numbers, between O and 100. According to this convention, the delta of an ATM option is around 50. A 25-delta option would be out-of-the-money and a 75-delta option in-the-money. Especially in FX markets, traders use this terminology to trade options.  

Under these conditions, an options trader may evaluate his or her exposure using delta points.. A trader may be long delta, which means that the position gains if the underlying increases, and loses if the underlying decreases. A short delta position implies the opposite..  

# 9.6.1.2 The exact expression  

The partial derivative in Eq. (9.79) can be taken in case the call option is European and the price is given by the Black--Scholes formula. Doing so, we obtain the delta of this important special case:.  

$$
\frac{\partial C(S_{t},t\mid r,\sigma,T,K)}{\partial S_{t}}=\int_{-\infty}^{\frac{(T-t)(r+(1/2)\sigma^{2})+\log(S_{t}/K)}{\sqrt{(T-t)\sigma}}}\frac{1}{\sqrt{2\pi}}e^{-(1/2)x^{2}}\mathrm{d}x
$$  

This derivation is summarized in Appendix 9.1. It is shown that the delta is itself a function. that depends on the "variables" $S_{t},K,r,\sigma$ , and on the remaining life of the option, $T-t.$ This function is in the form of a probability. The delta is between O and 1, and the function will have the familiar $S$ -shape of a continuous cumulative distribution function (CDF). This, incidentally, means. that the derivative of the delta with respect to $S_{t}$ which is called gamma, will have the shape of a. probability density function (PDF).20 A typical delta will thus look like the S-shaped curve shown. in Figure 9.10.  

We can also see from this formula how various movements in market variables will affect this particular option sensitivity. The formula shows that whatever increases the ratio  

$$
\frac{\log(S_{t}/K)+(r+(1/2)\sigma^{2})(T-t)}{\sigma{\sqrt{T-t}}}
$$  

will increase the delta; whatever decreases this ratio, will decrease the delta.  

For example, it is clear that as $r$ increases, the delta will increase. On the other hand, a decrease in the moneyness of the call option, defined as the ratio  

$$
\frac{S_{t}}{K}
$$  

decreases the delta. The effect of volatility changes is more ambiguous and depends on the moneyness of the option.  

![](images/4f4d55a3a9747cd5b0d52758605add51faec62de738626a1b5839e73943f3bb8.jpg)  

# FIGURE 9.10  

Delta of a long call position based on Black-Scholes formula.  

# EXAMPLE  

We calculate the delta for some specific options. We first assume the Black--Scholes world, even though the relevant market we are operating in may violate many of the Black-Scholes assumptions. This assumes, for example, that the dividend yield of the underlying is zero and this assumption may not be satisfied in real-life cases. Second, we differentiate the function $C(t)$  

$$
C(t)=S_{t}N(d_{1})-K e^{-r(T-t)}N(d_{2})
$$  

where $d_{1}$ and $d_{2}$ are as given in Eqs. (9.53) and (9.54), with respect to $S_{t}$ . Then, we substitute values observed for $S_{t},K,r,\sigma,(T-t)$  

Suppose the Microsoft December calls and puts shown in the table from our first example in this chapter satisfy these assumptions. The deltas can be calculated based on the following parameter values:  

$$
S_{t}=61.15,r=0.025,\sigma=30.7\%,T-t=58/365
$$  

Here, $\sigma$ is the implied volatility obtained by solving the equation for $K=60$  

$$
C(61.115,60,0.025,58/365,\sigma)=\mathrm{Observedprice}
$$  

Plugging the observed data into the formula for delta yields the following values:  

<html><body><table><tr><td>Calls</td><td>Delta</td></tr><tr><td>Dec 55.00 0.82</td><td></td></tr><tr><td>Dec 60.00 0.59</td><td></td></tr><tr><td>Dec 65.00 0.34</td><td></td></tr><tr><td>Dec 70.00 0.16</td><td></td></tr></table></body></html>  

<html><body><table><tr><td>Puts Delta</td><td></td></tr><tr><td>Dec 55.00 -0.17</td><td></td></tr><tr><td>Dec 60.00 -0.40</td><td></td></tr><tr><td>Dec 65.00 -0.65</td><td></td></tr><tr><td>Dec 70.00 -0.84</td><td></td></tr></table></body></html>  

We can make some interesting observations:  

1. The ATM calls and puts have the same price.   
2. Their deltas, however, are different.   
3. The calls and puts that are equally far from the ATM have slightly different deltas in. absolute value. According to the last point, if we consider 25-delta calls and puts, they will not be exactly   
the same.21  

We now point out to some questionable assumptions used in our example. First, in calculating. the deltas for various strikes, we always used the same volatility parameter. $\sigma$ . This is not a trivial. point. Options that are identical in every other aspect, except for their strike $K_{i}$ may have different implied volatilities. There may be a volatility smile. Using the ATM implied volatility in calculating the delta of all options may not be the correct procedure. Second, we assumed a zero dividend yield, which is not realistic either. Normally, stocks have positive expected dividend yields and some correction for this should be made when option prices and the relevant Greeks are calculated. A rough way of doing it is to calculate an annual expected percentage dividend yield and subtract. it from the risk-free rate. $r.$ Third, should we use. $S_{t}$ or a futures market equivalent, in case this latter. exists, the delta evaluated in the futures or forward price may be more desirable..  

# 9.6.2 GAMMA  

Gamma represents the rate of change of the delta as the underlying risk $S_{t}$ changes. Changes in delta were seen to play a fundamental role in determining the price of a vanilla option. Hence,  

![](images/c8afb33e58cd9d14c313452a0ebe03fbec3e8bbd78f71f79107a9a6a6dc7aaa7.jpg)  

# FIGURE 9.11  

Gamma of a long call position based on Black-Scholes formula.  

gamma is another important Greek. It is given by the second partial derivative of $C(S_{t},~t)$ with respect to $S_{t}$  

$$
\mathrm{gamma}=\frac{\partial^{2}C(S_{t},t\mid r,\sigma,T,K}{\partial S_{t}^{2}}
$$  

We can easily obtain the exact expression for gamma in the case of a European call. The derivation in Appendix 9.1 gives.  

$$
\frac{\partial^{2}C(S_{t},t\mid r,\sigma,T,K}{\partial S_{t}^{2}}=\frac{1}{S_{t}\sigma\sqrt{T-t}}\left[\frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}\left(\frac{\log(S/k)+r(T-t)}{\sigma\sqrt{T-t}}\frac{1}{2}\sigma^{2}(T-t)}\right)^{2}\mathrm{d}u\right]
$$  

Gamma shows how much the delta hedge should be adjusted as. $S_{t}$ changes. Figure 9.11 illustrates the gamma for the Black-Scholes formula. We see the already-mentioned property. Gamma is highest if the option is ATM, and approaches zero as the option becomes deep in-the-money or out-of-the-money.  

We can gain some intuition on the shape of the gamma curve. First, remember that gamma is,. in fact, the derivative of delta with respect to. $S_{t}$ . Second, remember that delta itself had the shape. of a cumulative normal distribution. This means that the shape of gamma will be similar to that of a continuous, bell-shaped PDF, as expression (9.87) indicates.  

Consider now a numerical example dealing with gamma calculations. We use the same data uti lized earlier in the chapter.  

# EXAMPLE  

To calculate the gamma, we use the same table as in the first example in the chapter. We take the partial derivative of the delta with respect to $S_{t}$ . This gives a new function. $S_{t},K,r,$ $\sigma$ $(T-1)$ , which measures the sensitivity of delta to the underlying $S_{t}$ We then substitute the observed values for $S_{t},K,r,\sigma,(T-t)$ to obtain gamma at that particular point..  

For the Microsoft December calls and puts shown in the table, gammas are calculated based on the parameter values  

$$
S_{t}=60.0,r=0.025,\sigma=31\%,T-t=58/365,k=60
$$  

where $\sigma$ is the implicit volatility.  

Again we are using the implicit volatility that corresponds to the ATM option in calculating the delta of all options, in-the-money or out..  

Plugging the observed data into the formula for gamma yields the following values:  

<html><body><table><tr><td>Calls</td><td>Gamma</td></tr><tr><td>Dec 55.00</td><td>0.034</td></tr><tr><td>Dec 60.00</td><td>0.053</td></tr><tr><td>Dec 65.00</td><td>0.050</td></tr><tr><td>Dec 70.00</td><td>0.032</td></tr></table></body></html>  

<html><body><table><tr><td>Puts</td><td>Gamma</td></tr><tr><td>Dec 55.00</td><td>0.034</td></tr><tr><td>Dec 60.00</td><td>0.053</td></tr><tr><td>Dec 65.00</td><td>0.050</td></tr><tr><td>Dec 70.00</td><td>0.032</td></tr></table></body></html>  

The following observations can be made:  

1. The puts and calls with different distance to the ATM strike have gammas that are alike but not exactly symmetric.  

2. Gamma is positive if the market maker is long the option; otherwise it is negative.  

It is also clear from this table that gamma is highest when we are dealing with an ATM option.  

Finally, we should mention that as time passes, the second-order curvature of ATM options will increase as the gamma function becomes more peaked and its tails go toward zero.  

# 9.6.2.1 Market use  

We must comment on the role played by gamma in option trading. We have seen that long delta. exposures can be hedged by going short using the underlying asset. But, how are gamma exposures  

hedged? Traders sometimes find this quite difficult. Especially in very short-dated, deep out-of-themoney options, gamma can suddenly go from zero to very high values and may cause significant losses (or gains).  

# EXAMPLE  

The forex option market was caught short gamma in GBP/EUR last week. The spot rate surged from GBP0.6742 to GBP0.6973 late the previous week, 1-month volatilities went up from about $9.6\%$ to roughly $13.3\%$ This move forced players to cover their gamma.  

(A typical market quote)  

This example shows one way delta and gamma are used by market professionals. Especially in the foreign exchange markets, options of varying moneyness characteristics are labeled according to their delta. For example, consider 25-delta Sterling puts. Given that an ATM put has a delta of. around 50, these puts are out-of-the-money. Market makers had sold such options and, after hedging. their delta exposure, were holding short gamma positions. This meant that as the Sterling-Euro exchange rate fluctuated, hedge adjustments led to higher than expected cash outflows..  

# 9.6.3 VEGA  

A critical Greek is the vega. How much will the value of an option change if the volatility parame-. ter, $\sigma$ , moves by an infinitesimal amount? This question relates to an option's sensitivity with. respect to implied volatility movements. Vega is obtained by taking the partial derivative of the function with respect to $\sigma$  

$$
\mathrm{vega}=\frac{\partial C(S_{t},t\mid r,\sigma,T,K}{\partial\sigma}
$$  

An example of vega is shown in Figure 9.12 for a call option. Note the resemblance to the gamma displayed earlier in Figure 9.11. According to this figure, the vega is greatest when the. option is ATM. This implies that if we use the ATM option as a vehicle to benefit from oscillations in $S_{t},$ we will also have maximum exposure to movements in the implied volatility. We consider. some examples of vega calculations using actual data..  

# EXAMPLE  

Vega is the sensitivity with respect to the percentage volatility parameter, $\sigma$ , of the option. According to the convention, this is calculated using the Black-Scholes formula. We differ entiate the formula with respect to the volatility parameter $\sigma$  

Doing this and then substituting  

$$
C(61.15,0.025,60,58/365,\sigma)=\mathrm{Observedprice}
$$  

we get a measure of how this option's prices will react to small changes in $\sigma$  

For the table above, we get the following results:  

<html><body><table><tr><td>Calls</td><td>Vega($)</td></tr><tr><td>Dec 55.00</td><td>6.02</td></tr><tr><td>Dec 60.00</td><td>9.4</td></tr><tr><td>Dec 65.00</td><td>8.9</td></tr><tr><td>Dec 70.00</td><td>5.6</td></tr></table></body></html>  

<html><body><table><tr><td>Puts</td><td>Vega($)</td></tr><tr><td>Dec55.00</td><td>6.02</td></tr><tr><td>Dec 60.00</td><td>9.4</td></tr><tr><td>Dec 65.00</td><td>8.9</td></tr><tr><td>Dec 70.00</td><td>5.6</td></tr></table></body></html>  

We can make the following comments:  

1. ATM options have the largest values of vega.   
2. As implied volatility increases, the ATM vega changes marginally, whereas the out-of-. the-money and in-the-money option vegas do change, and in the same direction.  

![](images/c73286bf086b6df5b54b01087cff652a89ebcd253871d907212d8db45e0e6172.jpg)  

# FIGURE 9.12  

Vega of a long call position based on Black-Scholes formula.  

Option traders can use the vega in calculating the "new" option price in case implied volatilities change by some projected amount. For example, in the preceding example, if the implied volatility increases by 2 percentage points, then the value of the Dec 60-put will increase approximately by 0.19, everything else being the same.  

# 9.6.3.1 Market use  

Vega is an important Greek because it permits market professionals to keep track of their exposure to changes in implied volatility. This is important, since the Black-Scholes formula is derived in a framework where volatility is assumed to be constant, yet used in an environment where the volatilityparameter, $\sigma$ , changes. Market makers often quote the $\sigma$ directly, instead of quoting the Black-Scholes value of the option. Under these conditions, vega can be used to track exposure of option books to changes in $\sigma$ . This can be followed by vega hedging.  

The following reading is one example of the use of vega by the traders.  

# EXAMPLE  

Players dumped USD/JPY vol last week in a quiet spot market, causing volatilities to go down further. One player was selling UsD1 billion in six-month dollar/yen options in the market. These trades were entered to hedge vega exposure. The drop in the vols forced market makers to hedge exotic trades they had previously sold.  

According to this reading, some practitioners were long volatility. They had bought options when the dollar-yen exchange rate volatility was higher. They faced vega risk. If implied volatility. declined, their position would lose value at a rate depending on the position's vega. To cover these. risky positions, they sold volatility and caused further declines in this latter. The size of vega is. useful in determining such risks faced by such long or short volatility positions..  

# 9.6.3.2 Vega hedging  

Vega is the response of the option value to a change in implied volatility. In a liquid market, option traders quote implied volatility and this latter continuously fluctuates. This means that the value of an existing option position also changes as implied volatility changes. Traders who would like to. eliminate this exposure use vega hedging in making their portfolio vega-neutral. Vega hedging in practice involves buying and selling options, since only these instruments have convexity and. hence, have vega.  

# 9.6.4 THETA  

Next, we ask how much the theoretical price of an option would change if a small amount of time, dt, passes. We use the partial derivative of the function with respect to time parameter $t$ which is called theta:  

$$
\mathrm{theta}=\frac{\partial C(S_{t},t\mid r,\sigma,T,K}{\partial t}
$$  

![](images/4ca65dc9f58ed6531298170c1d117a747e833e45e39142c6b1c6fbf16dfe95e2.jpg)  

# FIGURE 9.13  

Theta of a long call position based on Black-Scholes formula.  

According to this, theta measures the decay in the time value of the option. The intuition behind theta is simple. As time passes, one has less time to gain from future $S_{t}$ oscillations. Option's time value decreases. Thus, we must have theta $<0$  

If the Black-Scholes assumptions are correct, we can calculate this derivative analytically and plot it. The derivative is represented in Figure 9.13. We see that, all else being the same, a plain vanilla option's time value will decrease at a faster rate as expiration approaches.  

# 9.6.5 OMEGA  

This Greek relates to American options only and is an approximate measure developed by market professionals to measure the expected life of an American-style option..  

# 9.6.6 HIGHER-ORDER DERIVATIVES  

The Greeks seen thus far are not the only sensitivities of interest. One can imagine many other sensitivities that are important to market professionals and investors. In fact, we can calculate the sensitivity of the previously mentioned Greeks themselves with respect to. $S_{t},\sigma,t,$ and $r$ These are higher-order cross partial derivatives and under some circumstances will be quite relevant to the trader.  

Two examples are as follows. Consider the gamma of an option. This Greek determines how much cash can be earned as the underlying $S_{t}$ oscillates. But the value of the gamma depends on the $S_{t}$ and $\sigma$ as well. Thus, a gamma trader may be quite interested in the following sensitivities:  

$$
\frac{\partial{\mathrm{gamma}}}{\partial S_{t}}\quad\frac{\partial{\mathrm{gamma}}}{\partial\sigma}
$$  

These two Greeks are sometimes referred to as the speed and zomma, respectively.22 It is obvious that the magnitude of these partials will be useful in determining the risks and gains of gamma positions. Exotic option deltas and gammas may have discontinuities, and such high-order moments may be very relevant.  

Another interesting Greek is the derivative of vega with respect to $S_{t}$  

$$
\begin{array}{l}{{\displaystyle\frac{\partial\mathrm{vega}}{\partial S_{t}}}}\ {{\displaystyle\frac{\partial\mathrm{vega}}{\partial\sigma}=\mathrm{volga}}}\end{array}
$$  

This derivative is of interest to a vega trader. In a sense, this is volatility gamma, hence the name. Similarly, the partial derivative of all important Greeks with respect to a small change in time parameter may provide information about the way the Greeks move over time.  

# 9.6.7 GREEKS AND PDEs  

The fundamental Black-Scholes PDE that we derived in this chapter can be reinterpreted using the Greeks just defined. In fact, we can plug the Greeks into the Black-Scholes PDE.  

$$
\frac{1}{2}C_{s s}\sigma^{2}S_{t}^{2}+r C_{s}S_{t}-r C+C_{t}=0
$$  

and recast it as  

$$
{\frac{1}{2}}\mathrm{gamma}\sigma^{2}S_{t}^{2}+r\mathrm{delta}S_{t}-r C+\mathrm{theta}=0
$$  

In this interpretation, being long in options means, "earning" gamma and "paying" theta.  

It is also worth noting that the higher-order Greeks mentioned in Eqs. (9.92) and (9.93) are not present in Eq. (9.95). This is because they are second-order Greeks. The first-order Greeks are related to changes in the underlying risk. $\Delta S_{t},\Delta\sigma$ or time $\Delta$ .whereas the higher-order Greeks would relate to changes that will have sizes given by the products. $(\Delta S_{t}\Delta\sigma)$ or $(\Delta\sigma\Delta)$ . In fact, when $\Delta S_{t},\Delta\sigma,\Delta$ are "small' but non-negligible, products of two small numbers such as. $(\Delta S_{t}\Delta\sigma)$ are even smaller and negligible, depending on the sizes of incremental changes in $S_{t}.$ or volatility.23  

In some real-life applications, when volatility "spikes," higher-order Greeks may become relevant. Yet, in theoretical models with standard assumptions, where. $\Delta\to0$ , they fall from the overall. picture, and do not contribute to the PDE in Eq. (9.94)..  

# 9.6.7.1 Gamma trading  

The Black-Scholes PDE can be used to explain what a gamma trader intends to accomplish. Assume that the real-life gamma is correctly calculated by choosing a formula for. $C(S_{t},\:t\mid r,K,\sigma,$ $T_{,}$ and then taking the derivative:  

$$
\mathrm{{gamma}}=\frac{{\partial^{2}}C(S_{t},t\mid r,K,\sigma,T}{\partial S_{t}^{2}}
$$  

Following the logic that led to the Black-Scholes PDE in Eq. (9.94), a gamma trader would,. first, form a subjective view on the size of expected changes in the underlying using some subjective probability $P^{*}$ , as of time $t_{0}<t$ The gains can be written as,  

$$
E_{t_{0}}^{P*}\left[\frac{1}{2}\mathrm{gamma}(\Delta S_{t})^{2}\right]
$$  

This term would be greater, the greater the oscillations in. $S_{t}$ . Then these gains will be compared. with interest expenses and the loss of time value. If the expected gamma gains are greater than these costs, then the gamma trader will go long gamma. If, in contrast, the costs are greater, the. gamma trader will prefer to be short gamma..  

There are at least two important comments that need to be made about trading gammas.  

# 9.6.7.2 Gamma trading versus Vega  

First of all, the gamma of an option position depends on the implied volatility parameter. $\sigma$ . This parameter represents implied volatility. It need not have the same value as the (percentage) oscilla-. tions anticipated by a gamma trader. In fact, a gamma trader's subjective (expected) gains, due to $S_{t}$ oscillations, are given by  

$$
E_{t_{0}}^{p*}\left[{\frac{1}{2}}\operatorname{gamma}(\Delta S_{t})^{2}\right]
$$  

There is no guarantee that the implied volatility parameter will satisfy the equality  

$$
\sigma^{2}S_{t}^{2}\Delta E_{t_{0}}[\mathrm{gamma}]=E_{t_{0}}^{P*}[\mathrm{gamma}(\Delta S_{t})^{2}]
$$  

This is even if the trader is correct in his or her anticipation. The right-hand side of this expression represents the anticipated (percentage) oscillations in the underlying asset that depend on a) subjective probability distribution, whereas the left-hand side is the volatility value that is plugged into the Black-Scholes formula to get the option's fair price.  

Thus, a gamma trader's gains and losses also depend on the implied volatility movements, and. the option's vega will be a factor here. For example, a gamma trader may be right about increased real-world oscillations, but, may still lose money if implied volatility,. $\sigma$ , falls simultaneously. This. will lower the value of the position if.  

$$
\frac{\partial C_{s s}}{\partial\sigma}<0
$$  

The following reading illustrates the approaches a trader or risk manager may adopt with respect to vega and gamma risks.  

# EXAMPLE  

The VOLX contracts, (one) the new futures based on the price volatility of three reference markets measured   
by the closing levels of the benchmark cash index. The three are the German (DAX), UK (FT-SE), and.   
Swedish (OMX) markets. The designers argue that VOLX products, by creating a term structure of volatility that is arbitrageable,   
offer numerous hedging and trading possibilities. This covers both vega and gamma exposures and also   
takes in the long-dated options positions that are traditionally very difficult to hedge with short options. Simply put, option managers who have net short positions and therefore are exposed to increases in.   
volatility, can hedge those positions by being long the VOLX contract. The reverse is equally true. As a pure.   
form of vega, the contracts offer particular benefits for vega hedging. Their vega profile is constant for any   
level of spot ahead of the rate setting period, and then diminishes linearly once the RsP has begun.. The gamma of VOLX futures, in contrast, is very different from those of traditional options. Although a   
risk manager would traditionally hedge an option position by using a product with a similar gamma profile,   
hedging the gamma of a complex book with diversified strikes can become unwieldy. VOLX gamma,   
regardless of time and the level of the underlying spot, is evenly distributed. vOLX will be particularly   
useful for the traditionally hard to hedge out-of-the-money wings of an option portfolio.  

(Thomson Reuters IFR, November 23, 1996)  

# 9.6.7.3 Which expectation?  

We characterized trading gains expected from $S_{t}$ oscillations using the expression:  

$$
E_{t_{0}}^{P*}\left[\frac{1}{2}\mathrm{gamma}(\Delta S_{t})^{2}\right]
$$  

Here the expectation $E_{t_{0}}^{P*}[(\Delta S_{t})^{2}]$ is taken with respect to subjective probability distribution $P^{*}$ The behavior of gamma traders depends on their subjective probability, but the market-determined arbitrage-free price will be objective and the corresponding expectation has to be arbitrage-free. The corresponding pricing formulas will depend on objective risk-adjusted probabilities.  
