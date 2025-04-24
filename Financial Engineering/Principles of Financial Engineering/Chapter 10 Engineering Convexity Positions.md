# ENGINEERING CONVEXITY POSITIONS  

# 10  

# CHAPTER OUTLINE  

10.1 Introduction . 320   
10.2 A Puzzle.. 320   
0.3 Bond Convexity Trades . 321   
10.3.1 Delta-Hedged Bond Portfolios.. 325   
10.3.2 Costs... 328   
10.3.3 A Bond PDE. 328   
10.3.4 PDEs and Conditional Expectations. 330   
10.3.5 From Black Scholes to Bond PDE. 330   
10.3.6 Closed-Form Bond Pricing Formulas. 332   
10.3.6.1 Case 1 . 332   
10.3.6.2 Case 2 .. 332   
10.3.6.3 Case 3 .. 333   
10.3.7 A Generalization. 333  

# 0.4 Sources of Convexity.. 334  

10.4.1 Mark to Market.. 334   
10.4.2 Convexity by Design. . 335   
10.4.2.1 Swaps . 335   
10.4.2.2 Convexity of FRAs 338   
10.4.3 Prepayment Options . . 339  

# 10.5 A Special Instrument: Quantos . 340  

10.5.1 A Simple Example . 340   
10.5.1.1 Quantos in equity 342   
10.5.2 Pricing . 342   
10.5.3 The Mechanics of Pricing.. 342   
10.5.4 Where Does Convexity Come in?.. 345   
10.5.5 Practical Considerations... 345  

# 10.6 Conclusions. 345  

# Suggested Reading 346  

# xercises . 346  

MATLAB Exercises.. 347  

# 10.1 INTRODUCTION  

How can anyone trade volatility? Stocks, yes. Bonds, yes. But volatility is not even an asset. Several difficulties are associated with defining precisely what volatility is. For example, from a technical point of view, should we define volatility in terms of the estimate of the conditional standard deviation of an asset price $S_{t}^{\phantom{\dagger}}$ ?  

$$
\sqrt{E_{t}[S_{t}-E_{t}[S_{t}]]^{2}}
$$  

Or should we define it as the average absolute deviation?  

$$
E_{t}[|S_{t}-E_{t}[S_{t}]|]
$$  

There is no clear answer, and these two definitions of statistical volatility will yield different numerical values. Leaving statistical definitions of volatility aside, there are many instances where traders quote, directly, the volatility instead of the dollar value of an instrument. For example, interest rate derivatives markets quote cap-floor and swaption volatilities.1 Equity options provide implied volatility. Implied volatility is calculated by taking the market price of an option and backing out the implied volatility that results in the market price given a particular option pricing model and other input parameters. Traders and market makers trade the quoted volatility. Hence, there must be some way of isolating and pricing what these traders call volatility in their respective markets.  

We started seeing how this can be done in Chapter 9. Options became more valuable when “volatility” increased, everything else being the same. Chapter 9 showed how these strategies can quantify and measure the “volatility” of an asset in monetary terms. This was done by forming delta-neutral portfolios, using assets with different degrees of convexity. In this chapter, we develop this idea further, apply it to instruments other than options, and obtain some generalizations. The plan for this chapter is as follows.  

First, we show how convexity of a long bond relates to yield volatility. The higher the volatility of the associated yield, the higher the benefit from holding the bond. We will discuss the mechanics of valuing this convexity. Then, we compare these mechanics with option-related convexity trades. We see some close similarities and some differences. At the end, we generalize the results to any instrument with different convexity characteristics. The discussion associated with volatility trading itself has to wait until Chapter 15, since it requires an elementary treatment of arbitrage pricing theory.  

# 10.2 A PUZZLE  

Here is a puzzle. Consider the yield curve shown in Figure 10.1. The 10-year zero-coupon bond has a yield to maturity that equals $5.2\%$ . The 30-year zero, however, has a yield to maturity of just $4.94\%$ . In other words, if we buy and hold the latter bond 20 more years, we would receive a lower yield during its lifetime.  

![](4b8541991eae11b6b7841d03e491e53fc55db6a3716c2c9411d0bbbdce8a3d37.jpg)  

# FIGURE 10.1  

Yield curve.  

It seems a bit strange that the longer maturity is compensated with a lower yield. There are several economic or institutional explanations for this phenomenon. For example, expectations for inflation 20 years down the line may be less than the inflationary expectations for the next 10 years only. Or, the relative demands for these maturities may be determined by institutional factors and, because players don’t like to move out of their “preferred” maturity, the yield curve may exhibit such inconsistencies. Insurance companies, for example, need to hedge their positions on long-term retirement contracts and this preference may lower the yield and raise the price of long bonds.  

But these explanations can hardly fully account for the observed anomaly. Institutional reasons such as preferred habitat and treasury debt retirement policies that reduce the supply of 30-year treasuries may account for some of the difference in yield, but it is hard to believe that an additional 20-year duration is compensated so little. Can there be another explanation?  

In fact, the yield to maturity may not show all the gains that can be realized from holding a long bond. This may be hard to believe, as yield to maturity is by definition how much the bond will yield per annum if kept until maturity.  

Yet, there can be additional gains to holding a long bond, due to the convexity properties of the instrument, depending on what else is available to trade “against” it, and depending on the underlying volatility. These could explain the “puzzle” shown in Figure 10.1. The $4.94\%$ paid by the 30-year treasury, plus some additional gains, could exceed the total return from the 10-year bond. This is conceivable since the yield to maturity and the total return of a bond are, in fact, quite different ways of measuring financial returns on fixed-income instruments.  

# 10.3 BOND CONVEXITY TRADES  

We have already seen convexity trades within the context of vanilla options. Straightforward discount bonds, especially those with long maturities, can be analyzed in a similar fashion and have exposure to interest rate volatility. In fact, a “long” bond and a vanilla option are both convex instruments and they both coexist with instruments that are either linear or have less convexity.2 Hence, a delta-neutral portfolio can be put together for long maturity bonds to benefit from volatility shifts. The overall logic will be similar to the options discussed in the previous chapter.  

Consider a long maturity default-free discount bond with price $B(t,~T)$ , with $t<T$ . This bond’s price at time $t$ can be expressed using the corresponding time $t$ yield, $y_{t}^{T}$ :  

$$
B(t,T)=\frac{1}{(1+y_{t}^{T})^{T}}
$$  

For $t=0$ , and $T=30$ , this function is plotted against various values of the 30-year zero-coupon yield, in Figure 10.2. It is obvious that the price is a convex function of the yield.  

A short bond, on the other hand, can be represented in a similar space with an almost linear curve. For example, Figure 10.3 plots a 1-year bond price $B(0,1)$ against a 1-year yield $y_{0}^{1}$ . We see that the relationship is essentially linear.3  

The main point here is that, under some conditions, using these two bonds we can put together a portfolio that will isolate bond convexity gains similar to the convexity gains that the dynamic hedging of options has generated. Thus, suppose movements in the two yields $y_{t}^{1}$ and $y_{t}^{30}$ are perfectly correlated over time $t.^{4}$ Next, consider a trader who tries to duplicate the strategy of the option market maker discussed in the previous chapter. The trader buys the long bond with borrowed funds and delta hedges the first-order yield exposure by shorting an appropriate amount of the shorter maturity bond.  

This trader will have to borrow $B(0,30)$ dollars to buy and fund the long bond position. The payoff of the portfolio  

$$
\{\mathrm{Longbond},\mathrm{loanof}B(0,30)\mathrm{dollars}\}
$$  

is as shown in Figure 10.2b as curve $\mathbf{BB^{\prime}}$ . Now compare this with Figure 10.2c. Here we show the profit/loss position of a market maker who buys an at-the-money “put option” on the yield $y_{t}^{30}$ . At expiration time $T_{\mathbf{\delta}}$ , the option will pay  

$$
P(T)=\mathrm{max}[y_{0}^{30}-y_{T}^{30},0]
$$  

This option is financed by a money market loan so that the overall position is shown as the downward sloping curve $B B^{\prime}$ .5 We see a great deal of resemblance between the two positions.  

![](e40a0a79b960b4b32e55773db0dd11a4f6ab1f8c5bb7fcbaae783d717fdff5c8.jpg)  

# FIGURE 10.2  

Bond and put option as examples of convex instruments.  

![](bacc691cf03ffb13bf14968be42c8708b757ddc8920df3f2403cc9178d372316.jpg)  

# FIGURE 10.3  

Price yield relationship for a short bond.  

Given this similarity between bonds and options, we should be able to isolate convexity or gamma trading gains in the case of bonds as well. In fact, once this is done, using an arbitrage argument, we should be able to obtain a partial differential equation (PDE) that default-free discount bond prices will satisfy. This PDE will have close similarities to the Black Scholes PDE derived in Chapter 8.  

The discussion below proceeds under some simplifying and unrealistic assumptions. We use the so-called one-factor model. Our purpose is to understand the mechanics of volatility trading in the case of bonds and this assumption simplifies the exposition significantly. Our context is different than in real life, where fixed-income instruments are affected by more than a single common random factor. Thus, we make two initial assumptions:  

1. There is a short and a long default-free discount bond with maturities $T^{s}$ and $T.$ respectively. Both bonds are liquid and can be traded without any transaction costs.   
2. The two bond prices depend on the same risk factor denoted by $\boldsymbol{r}_{t}$ . This can be interpreted as a spot interest rate that captures all the randomness at time $t$ and is the single factor mentioned earlier.  

The second assumption means that the two bond prices are a function of the short rate $\boldsymbol{r}_{t}$ . These functions can be written as  

$$
B(t,T^{S})=S(r_{t},t,T^{S})
$$  

and  

$$
B(t,T)=B(r_{t},t,T)
$$  

where $B(t,T^{s})$ is the time $t$ price of the short bond and $B(t,\ T)$ is the time $t$ price of the long bond. We postulate that the maturity $T^{s}$ is such that the short bond price $B(t,T^{s})$ is (almost) a linear function of $\boldsymbol{r}_{t}$ , meaning that the second derivative of $B(t,T^{s})$ with respect to $\boldsymbol{r}_{t}$ is negligible.  

Thus, we will proceed as if there was a single underlying risk that causes price fluctuations in a convex and a quasi-linear instrument, respectively. We will discuss the cash gains generated by the dynamically hedged bond portfolio in this environment.  

# 10.3.1 DELTA-HEDGED BOND PORTFOLIOS  

The trader buys the long bond with borrowed funds and then hedges the downside risk implied by the curve $A A^{\prime}$ in Figure 10.4. The hedge for the downside risk will be a position that makes money when $\boldsymbol{r}_{t}$ increases and loses money when $\boldsymbol{r}_{t}$ declines. This can be accomplished by shorting an appropriate number of the short bond.  

![](4177f38481f83a99dfc1617ce30a422f7f7f1c7ef8da5babdfc7bc0c5160c07e.jpg)  

# FIGURE 10.4  

Delta-hedged bond portfolio.  

In fact, the trick to form a delta-neutral portfolio is the same as in Chapter 9. Take the partial derivative of the functions $\textit{S}(r_{t},t,T^{s})$ and $B(r_{t},~t,~T)$ with respect to $r_{t},$ evaluate them at point $r_{t_{0}}$ , and use these to form a hedge ratio, $h_{t}$ :  

$$
\begin{array}{c}{h_{t}=\displaystyle\frac{(\hat{\sigma}B(r_{t},t,T)/\hat{\sigma}r_{t})}{(\hat{\sigma}S(r_{t},t,T^{s})/\hat{\sigma}r_{t})}}\\ {=\displaystyle\frac{B_{r}}{S_{r}}}\end{array}
$$  

$S_{r}$ is assumed to be a constant, given the quasi-linearity of the short bond price with respect to $r_{t}.\ h_{t}$ is a function of $\boldsymbol{r}_{t}$ , since $B_{r}$ is not constant due to the long bond’s convexity. Given the value of $r_{t_{0}},h_{t}$ can be numerically calculated, and $h_{t_{0}}$ units of the short maturity bond would be sold short at $t_{0}$ .  

The change in the value of this portfolio due to a small change in the spot rate $\Delta r_{t}$ only is given by  

$$
\begin{array}{c}{\displaystyle\Delta[B(r_{t},t,T)-h_{t}S(r_{t},t,T^{s})]=B_{r}\Delta r_{t}-\frac{B_{r}}{S_{r}}S_{r}\Delta r_{t}+R}\\ {=R}\end{array}
$$  

since the $S_{r}$ terms cancel out. $R$ is the remainder term of the implied Taylor series approximation, or Ito’s Lemma in this case, which depends essentially on the second derivative, $B_{r r}$ , and on $\boldsymbol{r}_{t}$ volatility. $S_{r}$ is approximately constant. This means that the net position,  

will have the familiar volatility position shown in the bottom part of Figure 10.4. As $\boldsymbol{r}_{t}$ fluctuates, this position is adjusted by buying and (short) selling an appropriate number of the nonconvex asset. The new value of partial derivative, $h_{t},$ is used at each readjustment. Again, just as in Chapter 8, this will make the practitioner “sell high” and “buy low” (or vice versa). As a result of these hedge adjustments, the counterparty who owns the long bond will earn gamma profits. These trading gains will be greater as volatility increases. Hence, we reach the result:  

Everything else being the same, the greater the volatility of $r_{t}.$ the more “valuable” the long bond.  

This means that as volatility increases, ceteris paribus, the yield of the convex instruments should decline, since more market participants will try to put this trade in place and drive its price higher.  

# EXAMPLE  

Suppose that initially the yield curve is flat at $5\%$ . The value of a 30-year default-free discount bond is given by  

$$
\begin{array}{c}{{B(0,30)=\displaystyle\frac{1}{(1+0.05)^{30}}}}\\ {{=0.23}}\end{array}
$$  

The original delta of the bond, $D_{t_{0}}$ at $r_{t_{0}}=0.05$ will be:  

$$
\begin{array}{c}{\displaystyle D_{t_{0}}=-\frac{30}{\big(1+{r_{t_{0}}}\big)^{31}}}\\ {\displaystyle=-6.61}\end{array}
$$  

A 1-year short bond is assumed to have an approximately linear pricing formula  

$$
\begin{array}{c}{B(t_{0},T^{s})=\big(1-r_{t_{0}}\big)}\\ {=0.95}\end{array}
$$  

The market maker will borrow 0.23 dollars, buy one long bond, and then hedge this position by shorting  

$$
\frac{-6.61}{-1.0}
$$  

units of the short bond. (Given linearity approximation the short bond has unit interest sensitivity.)  

A small time, $\Delta$ , passes. All rates change, $\boldsymbol{r}_{t}$ moves to $6\%$ . The portfolio value will move  

$$
\Delta B(t,T)-h_{t}\Delta B(t,T^{s})=\quad\left[\frac{1}{(1+0.06)^{30}}-\frac{1}{(1+0.05)^{30}}\right]
$$  

Note that in calculating this number, we are assuming that $\Delta$ is small. Only the effect of changing $\boldsymbol{r}_{t}$ is taken into account. In a sense, we are using a framework similar to partial derivatives.  

The new delta is calculated as $-4.9$ . The adjusted portfolio should be short 4.9 units of the short bond. Thus,  

$$
(6.6-4.9)=1.7
$$  

units need to be covered at a price of 0.94 each to bring the position to the desired deltaneutral state.  

This leaves a trading profit equal to  

$$
1.7(0.95-0.94)=\S0.017
$$  

Another period passes, with $\boldsymbol{r}_{t}$ going back to $r_{t_{2}}=0.05$ . The cycle repeats itself. The delta will change again, the portfolio will be readjusted, and trading profits will continue to accumulate.  

This example is approximate, since not all costs of the position are taken into account. The example started with the assumption of a flat yield curve, which was later relaxed and the yields became volatile. However, we never mentioned what causes this change. It turns out that volatility leads to additional gains for long bond holders and this increases the demand for them. As a result, ceteris paribus, long bond yields would decline relative to short bond yields. Hence, the introduction of yield volatility changed the structure of the initial yield curve.  

# 10.3.2 COSTS  

What are the costs (and other gains) of putting together such a long volatility position using default-free discount bonds? First, there is the funding cost. To buy the long bond, $B(t,\ T)$ funds were borrowed at $\boldsymbol{r}_{t}$ percent per annum. As long as the position is kept open, interest expense will be incurred. Second, as time passes, the pricing function of the bond becomes less and less convex, and hence the portfolio’s trading gains will respond less to volatility changes. Finally, as time passes, the value of the bonds will increase automatically even if the rates don’t come down.  

# 10.3.3 A BOND PDE  

A PDE consisting of the gains from convexity of long bonds and costs of maintaining the volatility position can be put together. Under some conditions, this PDE has an analytical solution, and an analytical formula can be obtained the way the Black Scholes formula was obtained.  

First we discuss the PDE informally. We start with the trading gains due to convexity. These gains are given by the continuous adjustment of the hedge ratio $h_{t},$ which essentially depends on $B_{r},$ except for a constant of proportionality, since the hedging instrument is quasi-linear in $\boldsymbol{r}_{t}$ . As $\boldsymbol{r}_{t}$ changes, the partial $B_{r}$ changes, and this will be captured by the second derivative. Then, convexity gains during a small time interval $\Delta$ is a function, as in Chapter 9, of  

$$
\frac{1}{2}\frac{\partial^{2}B(t,T)}{\partial r_{t}^{2}}\left(\sigma(r_{t},t)r_{t}\sqrt{\Delta}\right)^{2}
$$  

This is quite similar to the case of vanilla options, except that here the $\sigma(\boldsymbol{r}_{t},\ t)$ is the percentage short rate volatility. Short bond interest sensitivity will cancel out.  

If we model the risk-neutral dynamics of the short rate $\boldsymbol{r}_{t}$ as  

$$
\mathrm{d}r_{t}=\mu(r_{t},t)\mathrm{d}t+\sigma/r_{t}\mathrm{d}W_{t}\quad t\in[0,T]
$$  

where percentage volatility $\sigma$ is constant, these gamma gains simplify to  

$$
\frac{1}{2}B_{r r}\sigma^{2}r_{t}^{2}\Delta
$$  

during a small period $\Delta$ .6  

$$
\frac{\partial^{2}B(t,T)}{\partial r_{t}^{2}}=B_{r r}
$$  

To these, we need to add (subtract) other costs and gains that the position holder is subject to. The interest paid during the period $\Delta$ on borrowed funds will be  

$$
r_{t}B(t,T)\Delta
$$  

The other gain (loss) is the direct effect of passing time  

$$
\frac{\hat{\sigma}B(t,T)}{\hat{\sigma}t}\Delta=B_{t}\Delta
$$  

As time passes, bonds earn accrued interest, and convexity declines due to “roll-down” on the yield curve. The interest earned due to shorting the linear instrument will cancel out the cost of this short position.  

The final component of the gains and losses that the position is subject to during $\Delta$ is more complex than the case of a vanilla call or put. In the case of the option, the underlying stock, $S_{t}$ , provided a very good delta hedging tool. The market maker sold $(\partial/\partial S_{t})C(S_{t},t)$ units of the underlying $S_{t}$ in order to hedge a long call position. In the present case, the underlying risk is not the stock price $S_{t}$ or some futures contract. The underlying risk is the spot rate $r_{t}.$ , and this is not an asset. That is to say, the “hedge” is not $\boldsymbol{r}_{t}$ itself, but instead it is an asset indirectly influenced by $r_{t}$ . Also, randomness of interest rates requires projecting future interest gains and costs. All these complicate the cash flow analysis.  

These complications can be handled by positing that the drift term $\mu(r_{t},t)$ in the dynamics,7  

$$
\mathrm{d}r_{t}=\mu(r_{t},t)\mathrm{d}t+\sigma r_{t}\mathrm{d}W_{t},\quad t\in[0,T]
$$  

represents the risk-free expected change in the spot rate over an infinitesimal interval $\mathrm{d}t$ .8 Using this drift, we can write the last piece of gains and losses over a small interval $\Delta$ as (Vasicek, 1977):  

$$
\mu(r_{t},t)B_{r}\Delta
$$  

Adding all gains and losses during the interval $\Delta$ , we obtain the net gains from the convexity position:  

$$
\frac{1}{2}B_{r r}\sigma^{2}r_{t}^{2}\Delta+\mu(r_{t},t)B_{r}\Delta-r_{t}B\Delta+B_{t}\Delta
$$  

In order to preclude arbitrage opportunities, this sum must equal zero. Canceling the common $\Delta$ terms, we get the PDE for the bond:  

$$
\frac{1}{2}B_{r r}\sigma^{2}r_{t}^{2}+\mu(r_{t},t)B_{r}-r_{t}B+B_{t}=0
$$  

The boundary condition is simpler than in the case of vanilla options and is given by  

$$
B(T,T)=1
$$  

the par value of the default-free bond at maturity date $T.$ .  

# 10.3.4 PDEs AND CONDITIONAL EXPECTATIONS  

In this PDE, the unknown is again a function $B(t,\ T)$ . This function will depend on the random process $r_{t},t$ , as well as other parameters of the model. The most important of these is the short rate volatility, $\sigma$ . If $\boldsymbol{r}_{t}$ is the continuously compounded short rate, the solution is given by the conditional expectation  

$$
B(t,T)=E_{t}^{\tilde{P}}\left[e^{-\int_{t}^{T}r_{u}\mathrm{d}u}\right]
$$  

where $\tilde{P}$ is an appropriate probability. In other words, taking appropriate partial derivatives of the right-hand side of this expression, and then plugging these in the PDE would make the sum on the left-hand side of Eq. (10.32) equal to zero.9  

It is interesting to look at the parallel with options. The pricing function for $B(t,T)$ was based on a particular conditional expectation and solved the bond PDE. In the case of vanilla options written on a stock $S_{t}.$ , and satisfying all Black Scholes assumptions, the call price $C(S_{t},t)$ is given by a similar conditional expectation,  

$$
C(S_{t},t)=E_{t}^{\tilde{P}}[e^{-r(T-t)}C(S_{T},T)]
$$  

where $T$ is the expiration date and $\tilde{P}$ is the appropriate probability. If this expectation is differentiated with respect to $S_{t}$ and $t$ , the resulting partial derivatives will satisfy the Black Scholes PDE with the corresponding boundary condition. The main difference is that the BlackScholes assumptions take the short rate $\boldsymbol{r}_{t}$ to be constant, whereas in the case of bonds, it is a stochastic process.  

These comments reconcile the two views of options that were mentioned in Chapter 9. If we interpret options as directional instruments, then Eq. (10.35) will give the expected gains of the optional at expiration, under an appropriate probability. The argument above shows that this expectation solves the associated PDE which was approached as an arbitrage relationship tying gamma gains to other costs incurred during periodic rebalancing. In fact, we see that the two interpretations of options are equivalent.  

# 10.3.5 FROM BLACK SCHOLES TO BOND PDE  

Comparing the results of trading bond convexity with those obtained in trading vanilla options provides good insights into the general characteristics of PDE methods that are commonly used in finance.  

In Chapter 9, we derived a PDE for a plain vanilla call, $C\left(t\right)$ using the argument of convexity trading. In this chapter, we discussed a PDE that is satisfied by a default-free pure discount bond $B$ $(t,T)$ . The results were as follows.  

1. The price of a plain vanilla call, written on a nondividend-paying stock $S_{t},$ strike $K.$ , expiration $T_{\mathrm{{+}}}$ , was shown to satisfy the following “arbitrage” equality:  

$$
\frac{1}{2}C_{S S}(\sigma(S_{t},t)S_{t})^{2}\Delta=(r C-r C_{s}S_{t})\Delta-C_{t}\Delta
$$  

where $\sigma(S_{t},\ t)$ is the percentage volatility of $S_{t}$ during 1 year. The way it is written here, this percentage volatility could very well depend on time $t$ and $S_{t}$ .  

According to this equation, in order to preclude any arbitrage opportunities, trading gains obtained from dynamic hedging during a period of length $\Delta$ should equal the net funding cost, plus loss of time value. Canceling common terms and introducing the boundary condition yielded the Black Scholes PDE for a vanilla call:  

$$
\begin{array}{c}{{\frac{1}{2}C_{S S}(\sigma(S_{t},t)S_{t})^{2}+r C_{S}S_{t}-r C+C_{t}=0}}\\ {{C(T)=\mathrm{max}[S_{T}-K,0]}}\end{array}
$$  

Under the additional assumption that $\sigma(S_{t},t)S_{t}$ is proportional to $S_{t}$ with a constant factor of proportionality $\sigma$ ,  

$$
\sigma(S_{t},t)S_{t}=\sigma S_{t}
$$  

this PDE could be solved analytically, and a closed-form formula could be obtained for the $C$ $\mathbf{\rho}(t)$ . This formula is the Black Scholes equation:  

$$
C(t)=S_{t}N(d_{1})-K e^{-r(T-t)}N(d_{2})
$$  

$$
d_{1,2}=\frac{\log(S_{t}/K)+r(T-t)\pm(1/2)\sigma^{2}(T-t)}{\sigma\sqrt{T-t}}
$$  

The partial derivatives of this $C(t)$ would satisfy the preceding PDE.  

2. The procedure for a default-free pure discount bond $B(t,\ T)$ followed similar steps, with some noteworthy differences. Assuming that the continuously compounded spot interest rate, $\boldsymbol{r}_{t},$ is the only factor in determining bond prices, the convexity gains due to oscillations in $\boldsymbol{r}_{t}$ and to dynamic hedging can be isolated, and a similar “arbitrage relation” can be obtained:  

$$
\frac{1}{2}B_{r r}(\sigma(r_{t},t)r)^{2}\Delta=(r_{t}B-\mu(r_{t},t)B_{r})\Delta-B_{t}\Delta
$$  

Here, $\sigma(r_{t},t)$ is the percentage volatility of the short rate $\boldsymbol{r}_{t}$ during 1 year.  

Canceling common terms, and adding the boundary condition, we obtain the bond PDE:  

$$
\begin{array}{c}{{\frac{1}{2}B_{r r}\sigma^{2}r_{t}^{2}+\mu(r_{t},t)B_{r}-r_{t}B+B_{t}=0}}\\ {{{}}}\\ {{B(T,T)=1}}\end{array}
$$  

Under some special assumptions on the dynamic behavior of $\boldsymbol{r}_{t}$ , this bond PDE can be solved analytically, and a closed-form formula can be obtained.  

We now summarize some important differences between these parallel procedures. First, note that the PDE for the vanilla option is obtained in an environment where the only risk comes from the asset price $S_{t}$ , whereas for bonds the only risk is the interest rate $r_{t}.$ , which is not an asset per se. Second, the previously mentioned difference accounts for the emergence of the term $\mu(r_{t},\ t)$ in the bond PDE, while no such nontransparent term existed in the call option PDE. The $\mu(r_{t},\ t)$ represents the expected change in the spot rate during $\mathrm{d}t$ once the effect of interest rate risk is taken out. Third, the $\mu(r_{t},t)$ may itself depend on other parameters that affect interest rate dynamics. It is obvious that under these conditions, the closed-form solution for $B(t,\ T)$ would depend on the same parameters. Note that in the case of the vanilla option, there was no such issue and the only relevant parameter was σ. This point is important since it could make the bond price formula depend on all the parameters of the underlying random process, whereas in the case of vanilla options, the Black Scholes formula depended on the characteristics of the volatility parameter only.  

Before we close this section, a final parallel between the vanilla option and bond prices should be discussed. The PDE for a call option led to the closed-form Black Scholes formula under some assumptions concerning the volatility of $S_{t}$ . Are there similar closed-form solutions to the bond PDE? The answer is yes.  

# 10.3.6 CLOSED-FORM BOND PRICING FORMULAS  

Under different assumptions concerning short rate dynamics, we can indeed solve the bond PDE and obtain closed-form formulas. We consider three cases of increasing complexity. The cases are differentiated by the assumed short rate dynamics.  

# 10.3.6.1 Case 1  

The first case is simple. Suppose $\boldsymbol{r}_{t}$ is constant at $r$ . This gives the trivial dynamics,  

$$
\mathrm{d}r_{t}=0
$$  

where $\sigma$ and $\mu(r_{t},t)$ are both zero. The bond PDE in Eq. (10.43) then reduces to  

$$
\begin{array}{c}{{-r B+B_{t}=0}}\\ {{B(T,T)=1}}\end{array}
$$  

This is a simple, ordinary differential equation. The solution $B(t,\ T)$ is given by  

$$
B(t,T)=e^{-r(T-t)}
$$  

# 10.3.6.2 Case 2  

The second case is known as the Vasicek model.10 Suppose the risk-adjusted dynamics of the spot rate follows the mean-reverting process given by11  

$$
\mathrm{d}r_{t}=\alpha(\kappa-r_{t})\mathrm{d}t+\sigma\mathrm{d}W_{t}\quad t\in[0,T]
$$  

where $W_{t}$ is a Wiener process defined for a risk-adjusted probability.12  

Note that the volatility structure is restricted to constant absolute volatility denoted by $\sigma$ . Suppose, further, that the parameters $\alpha,\ \kappa,\ \sigma$ , are known exactly. The fundamental PDE for a typical $B(t,~T)$ will then reduce to  

$$
B_{r}\alpha(\kappa-r_{t})+B_{t}+\frac{1}{2}B_{r r}\sigma^{2}-r_{t}B=0
$$  

Using the boundary condition $B(T,\ T)=1$ , this PDE can be solved analytically, to provide a closed-form formula for $B(t,~T)$ . The closed-form solution is given by the expression  

$$
B(t,T)=A(t,T)e^{-C}(t,T)r_{t}
$$  

where  

$$
C(t,T)=\frac{(1-e^{-\alpha(T-t)})}{\alpha}
$$  

$$
A(t,T)=e\frac{(C(t,T)-(T-t))(\alpha^{2}\kappa-(1/2)\sigma^{2})}{\alpha^{2}}-\frac{\sigma^{2}C(t,T)^{2}}{4\alpha}
$$  

Here, $\boldsymbol{r}_{t}$ is the “current” observation of the spot rate.  

# 10.3.6.3 Case 3  

The third well-known case, where the bond PDE in Eq. (10.43) can be solved for a closed form, is the Cox Ingersoll Ross (CIR) model. In the CIR model, the spot rate $\boldsymbol{r}_{t}$ is assumed to obey the slightly different mean-reverting stochastic differential equation  

$$
\mathrm{d}\boldsymbol{r}_{t}=\alpha(\kappa-\boldsymbol{r}_{t})\mathrm{d}t+\sigma\sqrt{\boldsymbol{r}_{t}}\mathrm{d}W_{t}\quad t\in[0,T]
$$  

which is known as the square-root specification of interest rate volatility. Here $W_{t}$ is a Wiener process under the risk-neutral probability.  

The closed-form bond pricing equation here is somewhat more complex than in the Vasicek model. It is given by  

$$
B(t,T)=A(t,T)e^{-C(t,T)r_{t}}
$$  

where the functions $A(t,T)$ and $C(t,T)$ are given by  

$$
A(t,T)=\left(2\frac{\gamma e^{1/2(\alpha+\gamma)(T-t)}}{(\alpha+\gamma)(e^{\gamma(T-t)}-1)+2\gamma}\right)^{2\frac{\alpha\kappa}{\sigma^{2}}}
$$  

$$
C(t,T)=2\frac{e^{\gamma(T-t)}-1}{(\alpha+\gamma)(e^{\gamma(T-t)}-1)+2\gamma}
$$  

and where $\gamma$ is defined as  

$$
\gamma=\sqrt{\left(\alpha\right)^{2}+2\sigma^{2}}
$$  

The bond volatility $\sigma$ determines the risk premia in expected discount bond returns.  

# 10.3.7 A GENERALIZATION  

The previous sections showed that whenever two instruments depending on the same risk factor display different degrees of convexity, we can, in principle, put together a delta hedging strategy similar to the delta hedging of options discussed in Chapter 9. Whether this is worthwhile depends, of course, on the level of volatility relative to transaction costs and bid ask spreads.  

When a market practitioner buys a convex instrument and short sells an appropriate number of a linear (or less convex) instrument, he or she will benefit from higher volatility. We then say that the position is long volatility or long gamma. This trader has purchased gamma. If, in contrast, the convex instrument is shorted and the linear instrument is purchased at proper ratios, the position will benefit when the volatility of the underlying decreases.  

As the case of long bonds shows, the idea that volatility can be isolated (to some degree), and then traded is very general, and can be implemented when instruments of different convexities are available on the same risk. Of course, volatility can be such that transaction costs and bid ask spreads make trading it unfeasible, but that is a different point. More important, if the yield curve slope changes due to the existence of a second factor, the approach presented in the previous sections will not guarantee convexity gains.  

# 10.4 SOURCES OF CONVEXITY  

There is more than one reason for the convexity of pricing functions. We discuss some simple cases briefly, using a broad definition of convexity.  

# 10.4.1 MARK TO MARKET  

We start with a minor case due to daily marking-to-market requirements. Let $f_{t}$ denote the daily futures settlement price written on an underlying asset $S_{t},$ let $F_{t}$ be the corresponding forward price, and let $\boldsymbol{r}_{t}$ be the overnight interest rate.  

Marking to market means that the futures position makes or loses money every day depending on how much the futures settlement price has changed,  

$$
\Delta f_{t}=f_{t}-f_{t-1}
$$  

where the time index $t$ is measured in days and hence is discrete.  

Suppose the overnight interest rate $\boldsymbol{r}_{t}$ is stochastic. Then if the trader receives (pays) mark-tomarket gains daily, these can be deposited or borrowed at higher or lower overnight interest rates. If $\Delta f_{t}$ were uncorrelated with interest rate changes,  

$$
\Delta r_{t}=r_{t}-r_{t-1}
$$  

marking to market would not make a difference.  

But, when $S_{t}$ is itself an interest rate product or an asset price related to interest rates, the random variables $\Delta f_{t}$ and $\Delta r_{t}$ will, in general, be correlated. For illustration, suppose the correlation between $\Delta f_{t}$ and $\Delta r_{t}$ is positive. Then, when $f_{t}$ increases, $\boldsymbol{r}_{t}$ is likely to increase also, which means that the mark-to-market gains can now be invested at a higher overnight interest rate. If the correlation between $\Delta f_{t}$ and $\Delta r_{t}$ is negative, the reverse will be true. Forward contracts do not, normally, require such daily marking-to-market. The contract settles only at the expiration date. This means that daily paper gains or losses on forward contracts cannot be reinvested or borrowed at higher or lower rates.  

Thus, a futures contract written on an asset $S_{t}$ whose price is negatively correlated with $\boldsymbol{r}_{t}$ will be cheaper than the corresponding forward contract. If the correlation between $S_{t}$ and $\boldsymbol{r}_{t}$ is positive, then the futures contract will be more expensive. If $S_{t}$ and $\boldsymbol{r}_{t}$ are uncorrelated, then futures and forward contracts will have the same price, everything else being the same.  

# EXAMPLE  

Consider any Eurocurrency future. We saw in Chapter 3 that the price of a 1-year Eurodollar future, settling at time $t+1$ , is given by the linear function  

$$
V_{t}=100(1-f_{t})
$$  

Normally, we expect overnight interest rate $\boldsymbol{r}_{t}$ to be positively correlated with the futures rate $f_{t}$ . Hence, the price $V_{t}$ , which is not a convex function, would be negatively correlated with $\boldsymbol{r}_{t}$ . This means that the Eurodollar futures will be somewhat cheaper than corresponding forward contracts, which in turn means that futures interest rates are somewhat higher than the forward rates.  

Mark-to-market is one reason why futures and forward rates may be different.  

# 10.4.2 CONVEXITY BY DESIGN  

Some products have convexity by design. The contract specifies payoffs and underlying risks, and this specification may make the contract price a nonlinear function of the underlying risks. Among the most important classes of instruments that permit such convexity gains are, of course, options.  

We also discussed convexity gains from bonds. Long maturity default-free discount bond prices, when expressed as a function of yield to maturity $y_{t},$ , are simple nonlinear functions, such as  

$$
B(t,T)=\frac{100}{\left(1+y_{t}\right)^{T}}
$$  

Coupon bond prices can be expressed using similar discrete time yield to maturity. The price of a coupon bond with coupon rate $c$ , and maturity $T,$ , can be written as  

$$
P(t,T)=\left(\sum_{i=1}^{T}\frac{100c}{\left(1+y_{t}\right)^{i}}\right)+\frac{100}{\left(1+y_{t}\right)^{T}}
$$  

It can be shown that default-free pure discount bonds, or strips, have more convexity than coupon bonds with the same maturity.  

# 10.4.2.1 Swaps  

Consider a plain vanilla, fixed payer interest rate swap with immediate start date at $t=t_{0}$ and end date, $t_{n}=T.$ Following market convention, the floating rate set at time $t_{i}$ is paid at time $t_{i+1}$ . For simplicity, suppose the floating rate is 12-month USD LIBOR. This means that $\delta=1$ . Let the time $t=t_{0}$ swap rate be denoted by $s$ and the notional amount, $N$ , be 1.  

Then, the time $t_{0}$ value of the swap is given by  

$$
V_{t_{0}}=E_{t_{0}}^{\tilde{P}}\left[{\frac{L_{t_{0}}-s}{\left(1+L_{t_{0}}\right)}}+{\frac{L_{t_{1}}-s}{\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)}}+\cdots+{\frac{L_{t_{n-1}}-s}{\prod_{i=0}^{n-1}\left(1+L_{t_{i}}\right)}}\right]
$$  

where $\{L_{t_{0}},...,L_{t_{n-1}}\}$ are random LIBOR rates to be observed at times $t_{0},\ ...,t_{n-1}$ , respectively, and $\tilde{P}$ is an appropriate probability measure. With a proper choice of measure, we can act as if we  

can substitute a forward LIBOR rate, $F(t_{0},\ t_{i})$ , for the future spot LIBOR $L_{t_{i}}$ for all ${t_{i}}.^{13}$ If liquid markets exist where such forward LIBOR rates can be observed, then after this substitution we can write the previous pricing formula as  

$$
\begin{array}{r l}{V_{t_{0}}=}&{\frac{L_{t_{0}}-s}{\big(1+L_{t_{0}}\big)}+\frac{F(t_{0},t_{1})-s}{\big(1+L_{t_{0}}\big)(1+F(t_{0},t_{1}))}}\\ &{\ +\frac{F(t_{0},t_{2})-s}{\big(1+L_{t_{0}}\big)(1+F(t_{0},t_{1}))(1+F(t_{0},t_{2}))}+\cdots+\frac{F(t_{0},t_{n-1})-s}{\prod_{i=0}^{n-1}(1+F(t_{0},t_{i}))}}\end{array}
$$  

where $F(t_{0},t_{0})=L_{t_{0}}$ , by definition. Clearly, this formula is nonlinear in each $F(t_{0},\ t_{i})$ . As the forward rates change, $V_{t_{0}}$ changes in a nonlinear way.  

This can be seen better if we assume that the yield curve is flat and that all yield curve shifts are parallel. Under such unrealistic conditions, we have  

$$
L_{t_{0}}=F(t_{0},t_{0})=F(t_{0},t_{1})=\dots=F(t_{0},t_{n-1})=F_{t_{0}}
$$  

The swap formula then becomes  

$$
V_{t_{0}}=\frac{F_{t_{0}}-s}{\left(1\ +\ F_{t_{0}}\right)}+\frac{F_{t_{0}}-s}{\left(1\ +\ F_{t_{0}}\right)^{2}}+\ \ldots+\frac{F_{t_{0}}-s}{\left(1\ +\ F_{t_{0}}\right)^{T}}
$$  

which simplifies to14  

$$
V_{t_{0}}=\left(F_{t_{0}}-s\right)\frac{\left(\left(1+F_{t_{0}}\right)^{T}-1\right)}{F_{t_{0}}\left(1+F_{t_{0}}\right)^{T}}
$$  

The second derivative of this expression with respect to $F_{t_{0}}$ will be negative, for all $F_{t_{0}}>0$ .  

As this special case indicates, the fixed payer swap is a nonlinear instrument in the underlying forward rates. Its second derivative is negative, and the function is concave with respect to a “typical” forward rate. This is not surprising since a fixed payer swap has risks similar to the issuing of a 30-year bond. This means that a fixed-receiver swap will have a convex pricing formula and will have a similar profile as a long position in a 30-year coupon bond.  

# EXAMPLE  

Figure 10.5 plots the value of a fixed payer swap under the restrictive assumption that the yield curve is flat and that it shifts only parallel to itself. The parameters are as follows:  

$$
t=0
$$  

$$
s=7\%
$$  

$$
\begin{array}{c}{{T=30}}\\ {{}}\\ {{F_{t_{0}}=6\%}}\end{array}
$$  

We see that the function is nonlinear and concave.  

![](c42b9a79035513a976d1ecafcdc43b88c4ec0481481cb9a127d22a6b7b280e93.jpg)  

# FIGURE 10.5  

Value of a fixed payer swap.  

In Chapter 20, we will consider a different type of swap called constant maturity swap. The convexity of constant maturity swaps is due to their structure. This convexity will, in general, be more pronounced and at the same time more difficult to correctly account for.  

Taking convexity characteristics of financial instruments into account is important. This is best illustrated by the Chicago Board of Trade’s (CBOT) attempt to launch a new contract with proper convexity characteristics.  

# EXAMPLE  

The Chicago Board of Trade’s board of directors last week approved a plan to launch 5- and 10-year US dollar denominated interest rate swap futures and options contracts. Compared with the over-the-counter market, trading of swaps futures will reduce administrative cost and eliminate counterparty risk, the exchange said. The CBOT’s move marks the second attempt by the exchange to launch a successful swap futures contract. Treasuries were the undisputed benchmark a decade ago. They are not treated as a benchmark for valuation anymore. People price off the swap curve instead, said a senior economist at the CBOT.  

The main difference between the new contract and the contract that the CBOT de-listed in the mid-1990s is that the new one is convex in form rather than linear. It’s one less thing for end users to worry about, the economist said, noting that swap positions are marked to market on a convex basis. Another critical flaw in the old contract was that it launched in the 3- and 5-year, rather than the 5- and 10-year maturities, which is where most business takes place.  

The new swaps contracts will offer institutional investors such as bank treasurers, mortgage passthrough traders, originators, service managers, portfolio managers, and other OTC market participants a vehicle for hedging credit and interest rate exposure, the exchange said.  

(Thomson Reuters IFR Issue 1393, July 21, 2001)  

This is an excellent example that shows the importance of convexity in contract design. Futures contracts are used for hedging by traders. If the convexity of the hedging instrument is different than the convexity of the risks to be hedged, then the hedge may deteriorate as volatility changes. In fact, as volatility increases, the more convex instrument may yield higher gamma gains and this will influence its price.  

# 10.4.2.2 Convexity of FRAs  

Now consider the case of forward rate agreements (FRAs). As discussed in Chapter 3, FRAs are instruments that can be used to fix, at time $t_{0}$ , the risk associated with a LIBOR rate $L_{t_{i}}$ , that will be observed at time $t_{i\cdot}$ , and that has a tenor of $\delta$ expressed in days per year.15 The question is when would this FRA be settled. This can be done in different ways, leading to slightly different instruments. We can envisage three types of FRAs.  

One way is to set $L_{t_{i}}$ at time $t_{i},$ but then, settle at time $t_{i}+\delta$ . This would correspond to the “natural” way interest is paid in financial markets. Hence, at time $t=t_{0}$ , the value of the FRA will be zero and at time $t_{i}+\delta$ the FRA buyer will receive or pay  

$$
\big[L_{t_{i}}-F_{t_{0}}\big]N\delta
$$  

depending on the sign of the difference. The FRA seller will have the opposite cash flow.  

The second type of FRA trades much more frequently in financial markets. The description of these is the same, except that the FRA is settled at time $t_{i}.$ , instead of at $t_{i}+\delta$ . At time $t_{i\cdot}$ , when the LIBOR rate $L_{t_{i}}$ is observed, the buyer of the FRA will make (receive) the payment  

$$
\frac{\big[L_{t_{i}}-F_{t_{0}}\big]\delta}{1+L_{t_{i}}\delta}N
$$  

This is the previous settlement amount discounted from time $t_{i}+\delta$ to time $t_{i},$ using the time $t_{i}$ LIBOR rate. Figure 10.6 shows an example to the payoff of a 12-month FRA.  

Of even more interest for our purpose is a third type of FRA contract, a LIBOR-in-arrears FRA, where the LIBOR observed at time $t_{i}$ is used to settle the contract at time $t_{i}.$ , according to  

$$
\left[L_{t_{i}}-f_{t_{0}}\right]\delta N
$$  

![](1c0bfb47c6338db3f48f1fa0fc8a3b1e5e982739205a0989fd0cd5004cee36e6.jpg)  

# FIGURE 10.6  

Payoff of a 12-month FRA.  

Here, $f_{t_{0}}$ is the FRA rate that applies to this particular type of FRA.16 Note that we are using a symbol different than $F_{t_{0}}$ , because the two FRA rates are, in general, different from each other due to convexity differences in the two contracts.  

The question to ask here is under what conditions would the rates $F_{t_{0}}$ and $f_{t_{0}}$ differ from each other? The answer depends indeed on the convexity characteristics of the underlying contracts. In fact, market practitioners approximate these differences using convexity adjustment factors.  

# 10.4.3 PREPAYMENT OPTIONS  

A major class of instruments that have convexity by design is the broad array of securities associated with mortgages. A mortgage is a loan secured by the purchaser of a residential or commercial property. Most fixed-rate mortgages have a critical property. They contain the right to prepay the loan. The mortgage receiver has the right to pay the remaining balance of the loan at any time, and incur only a small transaction cost. This is called a prepayment option and introduces negative convexity in mortgage-related securities. In fact, the prepayment option is equivalent to an American-style put option written on the mortgage rate $R_{t}$ . If the mortgage rate $R_{t}$ falls below a limit $\boldsymbol{R}^{K}$ , the mortgage receiver will pay back the original amount denoted by $N.$ , by refinancing at the new rate $R_{t}$ . Instead of making a stream of fixed annual interest payments $R_{t_{0}}N$ , the mortgage receiver has the option (but not the obligation) to pay the annual interest $R_{t_{i}}N$ at some time $t_{i}$ . The mortgage receiver may exercise this option if $R_{t_{i}}<R_{t_{0}}$ . The situation is reversed for the mortgage issuer.  

The existence of such prepayment options creates negative convexity for mortgage-backed securities (MBSs) and other related asset classes. Since the prepayment option involves an exchange of one fixed stream of payments against another fixed stream, it is clear that interest rate swaps play a critical role in hedging and risk-managing these options dynamically. We will deal with this important topic in Chapter 17.  

# 10.5 A SPECIAL INSTRUMENT: QUANTOS  

Quanto-type financial products form a major class of instruments where price depends on correlations. At the end of this chapter, we will look at these in detail and study the financial engineering of quantos by discussing their characteristics and other issues. This can be regarded as another example to the methods introduced in Chapter 9. We will consider pricing of quantos in Chapter 13.  

# 10.5.1 A SIMPLE EXAMPLE  

Consider the standard currency swap in Figure 10.7. There are two cash flows, in two currencies, USD and EUR. The principal amounts are exchanged at the start date and reexchanged at the end date. During the life of the swap, floating payments based on USD LIBOR are exchanged for floating payments based on EUR LIBOR. There will be a small known spread involved in these exchanges as well.  

The standard currency swap of Figure 10.7 will now be modified in an interesting way. We keep the two floating LIBOR rates the same, but force all payments to be made in one currency only, say USD. In other words, the calculated EUR LIBOR indexed cash flows will be paid (received) in USD. This instrument is called a quanto swap or differential swap. In such a swap, the principal amounts would be in the same currency, and there would be no need to exchange them. Only net interest rate cash flows will be exchanged.  

![](d62bce53d7f011f1cf9c0436ffeaf57bd282c310ae0b22401e108c43d2905d37.jpg)  

# FIGURE 10.7  

# EXAMPLE  

Suppose the notional principal is USD30 million. Quotes on LIBOR are as follows:  

<html><body><table><tr><td>0.055 1.71</td><td></td></tr><tr><td>3-month</td><td></td></tr><tr><td>6-month 0.185</td><td>1.64</td></tr><tr><td>12-month 0.065</td><td>1.73</td></tr></table></body></html>  

In a quanto swap, one party would like to receive 6-month USD LIBOR and pay 6-month JPY LIBOR for 1 year. However, all payments are made in USD. For example, if the first settlement is according to the quotes given in the table, in 6 months this party will receive:  

$$
30,000,000(0.0164)\left({\frac{1}{2}}\right)-30,000,000(0.00185)\left({\frac{1}{2}}\right)-30,000,000\left({\frac{1}{2}}\right)c
$$  

where $c$ is a constant spread that needs to be determined in the pricing of this quanto swap.   
Note that the JPY interest rate is applied to a USD denominated principal.  

In this type of swap, the two parties are exposed to the risk of interest rate differentials. However, at least one of them is not exposed to currency risk.  

Why would anyone be interested in quanto swaps? Note that even after the spread $c$ is included, the interest cost paid in dollars,  

$$
\mathbf{JPY\LIBOR}+c
$$  

may be significantly less than USD LIBOR rates. This way, the party that receives USD LIBOR and pays JPY LIBOR (in USD) may be lowering funding costs substantially. Accordingly, the market would see interest in such quanto swaps when the short ends of the yield curves in two major currencies are significantly different. Banks could then propose these instruments to their clients as a way of “reducing” funding costs. Of course, from the clients’ point of view, quanto swaps still involve an interest rate risk and, possibly, an exchange rate risk. If the underlying yield curves shift in unexpected ways, losses may be incurred.  

The following example illustrates these from the point of view of British pound and Swiss franc interest rates.  

# EXAMPLE  

With European economies at a very different point in the trade cycle, corporates are looking to switch their debts into markets offering the cheapest funding. But whereas most would previously have been dissuaded by foreign exchange risk, the emergence of quanto products has allowed them to get the best of both worlds.  

With quanto swaps, interest is paid in a different currency to that of the reference index, the exchange rate being fixed at the outset of the swap. As a result, the product can provide exposure to a nondomestic yield curve without the accompanying exchange rate risks.  

In recent weeks, this type of product has proved increasingly appealing to UK corporates that have entered into a swap in which the paying side is referenced to Swiss LIBOR but the returns are paid in sterling. Swiss franc LIBOR is still low relative to sterling LIBOR and although the corporate ends up paying Swiss LIBOR plus a spread, funding costs are often still considerably cheaper than normal sterling funding. Deals have also been referenced to German or Japanese LIBOR. However, derivatives officials were also keen to point out that quanto products are far from being riskfree. “Given that the holder of the swap ends up paying Swiss LIBOR plus a spread, the curves do not have to converge much to render the trade uneconomic,” said one.  

(Thomson Reuters IFR Issue 1190, July 5 1997)  

# 10.5.1.1 Quantos in equity  

The notion of a quanto instrument can be applied in other financial markets. For example, a foreign investor may want to have exposure to Japanese equity markets without having to incur currency risk. Then, a quanto contract can be designed such that the gains and losses of an index in Japanese equities are paid annually in the foreign investors’ domestic currency instead of in yen.  

# 10.5.2 PRICING  

The pricing of quanto contracts raises interesting financial engineering issues.17 We discuss a simple case to illustrate quantos. First, fix the underlying. Assume that we are dealing with a particular foreign currency denominated stock $S_{t}^{*}$ . Without loss of generality, suppose the domestic currency is USD, the foreign currency is euro, and the stock is European.  

A dollar-based investor would like to buy the stock, and benefit from potential upside in European markets, but dislikes currency exposure to euro. The investor desires exposure to underlying equity risk only. To accommodate his wish, the bank proposes purchasing the stock via a quanto forward. An expiration date $T$ is chosen, and the current exchange rate EUR/USD, $\boldsymbol{e}_{t}$ is used to calculate the time $T$ settlement. The forward contract has USD price $F_{t}$ and settles according to  

$$
V_{T}=(e_{t}S_{T}^{*}-F_{t})
$$  

Here, the $V_{T}$ is the time $T$ value of the contract. It is measured in the domestic currency and will be positive if the stock appreciates sufficiently; otherwise, it will be negative. $F_{t}$ is the forward price of the quanto contract on $S_{T}^{*}$ and has to be determined by a proper pricing strategy.  

# 10.5.3 THE MECHANICS OF PRICING  

Suppose the current time is $t$ and a forward quanto contract on $S_{T}^{*}$ is written with settlement date $T=t+\Delta$ . Suppose also that at time $T$ there are only three possible states of the world $\{\omega^{1},\omega^{2},\omega^{3}\}$ . The following table gives the possible values of four instruments, the foreign stock, a foreign deposit, a domestic deposit, and a forward FX contract on the exchange rate $\boldsymbol{e}_{t}$ .  

<html><body><table><tr><td>Time t Price</td><td>Value in w1</td><td>Value in w²</td><td>Value in w3</td></tr><tr><td>S*</td><td></td><td>#</td><td>#</td></tr><tr><td>1 USD</td><td>(1+r△)</td><td>(1+r△)</td><td>(1+r△)</td></tr><tr><td></td><td>1+)</td><td>1+A)</td><td>+</td></tr><tr><td>1 e</td><td></td><td></td><td></td></tr></table></body></html>  

In this table, the first row gives the value of the foreign stock in the three future states of the world. These are measured in the foreign currency. The second row represents what happens to 1 dollar invested in a domestic savings account. The third row shows what happens when 1 unit of foreign currency is purchased at $\boldsymbol{e}_{t}$ dollars and invested at the foreign rate $r^{*}$ .  

The forward exchange rate $f_{t}$ is priced as  

$$
f_{t}=e_{t}\frac{1+r\Delta}{1+r^{*}\Delta}
$$  

where $\boldsymbol{e}_{t}$ is the current exchange rate. In this example, we are assuming that the domestic and foreign interest rates are constant at $r$ and $r^{*}$ , respectively. Now consider the quanto forward contract with current price $F_{t}$ mentioned earlier. $F_{t}$ will be determined at time $t.$ , and the contract will settle at time $T=t+\Delta$ . Depending on which state occurs, the settlement amount will be one of the following:  

$$
\{(S_{t+\Delta}^{*}e_{t}-F_{t}),(S_{t+\Delta}^{*2}e_{t}-F_{t}),(S_{t+\Delta}^{*3}e_{t}-F_{t})\}
$$  

These amounts are all in USD. What is the arbitrage-free value of $F_{t}^{\prime}$ ?  

We can use three of the four instruments listed to form a portfolio with weights $\lambda_{i},i=1$ , 2, 3 that replicate the possible values of $e_{t}S_{t+\Delta}^{*}$ at each state exactly. This will be similar to the cases discussed in Chapter 8. For example, using the first three instruments, for each state we can write  

$$
\begin{array}{r l}{\mathrm{State}\omega^{1}}&{\lambda_{1}S_{t+\Delta}^{*1}e_{t+\Delta}^{1}+\lambda_{2}(1+r\Delta)+\lambda_{3}e_{t+\Delta}^{1}(1+r^{*}\Delta)=S_{1+\Delta}^{*1}e t}\\ {\mathrm{State}\omega^{2}}&{\lambda_{1}S_{t+\Delta}^{*2}e_{t+\Delta}^{2}+\lambda_{2}(1+r\Delta)+\lambda_{3}e_{t+\Delta}^{1}(1+r^{*}\Delta)=S_{1+\Delta}^{*2}e t}\\ {\mathrm{State}\omega^{3}}&{\lambda_{1}S_{t+\Delta}^{*3}e_{t+\Delta}^{3}+\lambda_{2}(1+r\Delta)+\lambda_{3}e_{t+\Delta}^{1}(1+r^{*}\Delta)=S_{1+\Delta}^{*3}e t}\end{array}
$$  

In these equations, the right-hand side is the future value of the foreign stock measured at the current exchange rate. The left-hand side is the value of the replicating portfolio in that state.  

These form three equations in three unknowns, and, in general, can be solved for the unknown $\lambda_{i}$ . Once these portfolio weights are known, the current cost of putting the portfolio together leads to the price of the quanto:  

$$
\lambda_{1}S_{t}^{*}e_{t}+\lambda_{2}+\lambda_{3}e_{t}
$$  

This USD amount needs to be carried to time $T$ , since the contract settles at $T.$ . This gives  

$$
F_{t}=[\lambda_{1}S_{t}^{*}e_{t}+\lambda_{2}+\lambda_{3}e_{t}](1+r\Delta)
$$  

# EXAMPLE  

Suppose we have the following data on the first three rows of the previous table:  

<html><body><table><tr><td>Time t Price</td><td>Value in w1</td><td>Value in w²</td><td>Value in w3</td></tr><tr><td>100</td><td>115</td><td>100</td><td>90</td></tr><tr><td>1 USD</td><td>(1 + 0.05△)</td><td>(1 +0.05△)</td><td>(1 +0.05△)</td></tr><tr><td>1 EUR X 0.98</td><td>(1 + 0.03△)1.05</td><td>(1 +0.03△)0.98</td><td>(1 + 0.03)0.90</td></tr></table></body></html>  

What is the price of the quanto forward? We set up the three equations  

$$
\lambda_{1}(1.05)115+\lambda_{2}(1+0.05\Delta)+\lambda_{3}1.05(1+0.03\Delta)=0.98(115)
$$  

$$
\begin{array}{r l}{}&{\kappa_{1}(1.9s)100+\lambda_{2}(1+0.05\Delta)+\lambda_{3}0.98(1+0.03\Delta)=0.98(100)}\\ {}&{\lambda_{1}(0.98)100+\lambda_{2}(1+0.05\Delta)+\lambda_{3}0.98(1+0.03\Delta)=0.98(100)}\\ {}&{}\\ {}&{\lambda_{1}(0.90)90+\lambda_{2}(1+0.05\Delta)+\lambda_{3}0.90(1+0.03\Delta)=0.98(90)}\end{array}
$$  

We select the expiration $\Delta=1$ , for simplicity, and obtain  

$$
\lambda_{1}=0.78
$$  

$$
\lambda_{2}=60.67
$$  

$$
\lambda_{3}=-41.53
$$  

Borrowing 42 units of foreign currency, lending 61 units of domestic currency, and buying 0.78 units of the foreign stock would replicate the value of the quanto contract at time $t+1$ . The price of this portfolio at $t$ will be  

$$
100\lambda_{1}0.98+\lambda_{2}+0.98\lambda_{3}=96.41
$$  

If this is to be paid at time $t+\Delta$ , then it will be equal to the arbitrage-free value of $F_{t}$ :  

$$
F_{t}=(1.05)96.41=101.23
$$  

This example shows that the value of the quanto feature is related to the correlation between the movements of the exchange rate and the foreign stock. If this correlation is zero, then the quanto will have the same value as a standard forward. If the correlation is positive (negative), then the quanto forward will be less (more) valuable than the standard forward. In the example above, the exchange rates and foreign stock were positively correlated and the quantoed instrument cost less than the original value of the foreign stock.  

# 10.5.4 WHERE DOES CONVEXITY COME IN?  

The discussion of the previous section has shown that, in a simple one period setting with three possible states of the world, we can form a replicating portfolio for the quantoed asset payoffs at a future date. As the number of states increases and time becomes continuous, this type of replicating portfolio needs readjustment. The portfolio adjustments would, in turn, lead to negative or positive trading gains depending on the sign of the correlation, similar to the case of options. This is where volatilities become relevant. In the case of quanto assets there are, at least, two risks involved, namely, exchange rate and foreign equity or interest rates. The covariance between these affects pricing as well.  

The quanto feature will have a positive or negative value at time $t_{0}$ due to the trading gains realized during rebalancing. Thus, quantos form another class of assets where the nonnegligibility of second-order sensitivities leads to dependence of the asset price on variances and covariances.  

# 10.5.5 PRACTICAL CONSIDERATIONS  

At first glance, quanto assets may appear very attractive to investors and portfolio managers. After all, a contract on foreign assets is purchased and all currency risk is eliminated. Does this mean we should always quanto?  

Here again, some real-life complications are associated with the instrument. First of all, the purchase of a quanto may involve an upfront payment and the quanto characteristics depend on risk premia, bid ask spreads, and on transaction costs associated with the underlying asset and the underlying foreign currency. These may be high and an approximate hedge using foreign currency forwards may be cheaper in the end.  

Second, quanto assets have expiration dates. If, for some unforeseen reason, the contract is unwound before expiration, further costs may be involved. More important, if the foreign asset is held beyond the expiration date, the quanto feature would no longer be in effect.  

Finally, the quanto contract depends on the correlation between two risk factors, and this correlation may be unstable. Under these conditions, the parties that are long or short the quanto have exposure to changes in this correlation parameter. This may significantly affect the mark-to-market value of the quanto contracts.  

# 10.6 CONCLUSIONS  

Pricing equations depends on one or more risk factors. When the pricing functions are nonlinear, replicating portfolios that use linear assets with periodically adjusted weights will lead to positive or negative cash flows during the hedging process. If the underlying volatilities and correlations are significant, trading gains from these may exceed the transaction costs implied by periodic rebalancing, and the underlying nonlinearity can be traded.  

In this chapter, we saw two basic examples of this: one from the fixed-income sector which made convexity of bonds valuable, and the second from quanto instruments, which also brought in the covariance between risks. The example on quantos is a good illustration of what happens when term structure models depend on more than one factor. In such an environment, the covariances as well as the volatilities between the underlying risks may become important.  

# SUGGESTED READING  

Two introductory sources discuss the convexity gains one can extract from fixed-income instruments. They are Serrat and Tuckman (2011) and Jegadeesh and Tuckman (2000). The convexity differences between futures and forwards are clearly handled in Hull (2014). The discussion of the quanto feature used here is from Piros (1998), which is in DeRosa (1998). Wilmott (2006) has a nice discussion of quantoed assets as well.  

# EXERCISES  

1. You are given the following default-free long bond: Face value: 100 Issuing price: 100 Currency: USD Maturity: 30 years Coupon: $6\%$ No implicit calls or puts. Further, in this market there are no bid ask spreads and no trading commissions. Finally, the yield curve is flat and moves only parallel to itself.  

There is, however, a futures contract on the 1-year LIBOR rate. The price of the contract is determined as  

$$
V_{t}=100(1-f_{t})
$$  

where $f_{t}$ is the “forward rate” on 1-year LIBOR.  

a. Show that if the yield of the 30-year bond is $y_{t},$ then at all times we have  

$$
y_{t}=f_{t}
$$  

b. Plot the pricing functions for $V_{t}$ and the bond.  

c. Suppose the current yield $y_{0}$ is at $7\%$ . Put together a zero-cost portfolio that is delta-neutral toward movements of the yield curve.  

d. Consider the following yield movements over 1-year periods:  

$$
9\%,7\%,9\%,7\%,9\%,7\%
$$  

What are the convexity gains during this period?  

e. What other costs are there?  

2. You are given a 30-year bond with yield $y$ . The yield curve is flat and will have only parallel shifts. You have a liquid 3-month Eurodollar contract at your disposition. You can also borrow and lend at a rate of $5\%$ initially.  

a. Using the long bond and the Eurodollar contract, construct a delta-hedged portfolio that is immune to interest rate changes. b. Now suppose you observe the following interest rate movements over a period of 1 year:  

These observations are each 2 months apart. What are your convexity gains from a long volatility position?  

3. Consider the data given in the previous question.  

a. Suppose an anticipated movement as in the previous question. Market participants suddenly move to an anticipated trajectory such as  

Assuming that this was the only exogenous change in the market, what do you think will happen to the yield on the 30-year bond?  

4. Assuming that the yield curve is flat and has only parallel shifts, determine the spread between the paid-in-arrear FRAs and market-traded linear FRAs if the FRA rates are expected to oscillate as follows around an initial rate:  

$$
\{+0.02,-0.02,+0.02,-0.02,+0.02,-0.02\}
$$  

5. Answer the following questions related to the case study “Convexity of long bonds, convexity and arbitrage.”  

a. First the preliminaries. Explain what is meant by convexity of long-dated bonds.   
b. What is meant by the convexity of long-dated interest rate swaps?   
c. Explain the notion of convexity using a graph.   
d. If bonds are convex, which fixed-income instrument is not convex?   
e. Describe the cash flows of FRAs. When are FRAs settled in the market?   
f. What is the convexity adjustment for FRAs?   
g. What is a cap? What volatility do you buy or sell using caps?   
h. Now the real issue. Explain the position taken by “knowledgeable” professionals. i. In particular, is this a position on the direction of rates or something else? In fact, can you explain why the professionals had to hedge their position using caps or floors?   
j. Do they have to hedge using caps only? Can floors do as well? Explain your answer graphically.  

k. Is this a true arbitrage? Are there any risks?  

# MATLAB EXERCISES  

6. Consider the Vasicek model  

$$
\mathrm{d}\boldsymbol{r}=\alpha(\mu-\boldsymbol{r})\mathrm{d}t+\sigma\mathrm{d}\boldsymbol{W}_{-}t
$$  

Plot the term structure (i.e., plot yield versus time) for the following parameter sets $\left[\mathrm{\alpha},\upmu,\upsigma,\mathrm{r}(0)\right]$ :  

Now for the first parameter set plot the term structure by varying only one parameter at a time and report your observation.  

7. Consider the “CIR (Cox-Ingersoll-Ross)” model  

$$
\mathrm{d}\boldsymbol{r}=\alpha(\mu-\boldsymbol{r})\mathrm{d}t+\sigma\sqrt{\boldsymbol{r}\mathrm{d}W_{-}t}
$$  

Plot the term structure (i.e., plot yield versus time) for the following parameter sets $\left[\mathrm{\alpha},\upmu,\upsigma,\mathrm{r}(0)\right]$ :  

Now for the third parameter set, plot the term structure by varying only one parameter at a time and report your observation.  

# CASE STUDY: CONVEXITY OF LONG BONDS, SWAPS, AND ARBITRAGE  

The yield of a long bond tells you how much you can earn from this bond. Correct? Wrong. You can earn more.  

The reason is that long bonds and swaps have convexity. If there are two instruments, one linear and the other nonlinear, and if these are a function of the same risk factors, we can form a portfolio that is delta-neutral and that guarantees some positive return.  

This is a complex and confusing notion and the purpose of this case study is to clarify this notion a bit.  

At first, the case seems simple. Take a look at the following single reading provided on an arbitrage position taken by market professionals and answer the questions that follow.  

The more sophisticated traders in the swaps market—or at least those who have been willing to work alongside their in-house quants—have until recently been playing a game of one-upmanship to the detriment of their more naive interbank counterparties. By taking into account the convexity effect on long-dated swaps, they have been able to profit from the ignorance of their counterparties who saw no reason to change their own valuation methods.  

More specifically, several months ago several leading Wall Street US dollar swaps houses—reportedly JP Morgan and Goldman Sachs among them—realized that there was more value than met the eye when pricing LIBOR-in-arrears swaps. According to London traders, they began to arbitrage the difference between their own valuation models and those of “swap traders who still relied on naive, traditional methods” and transacting deals where they would receive LIBOR in arrears and pay LIBOR at the start of the period, typically for notional amounts of US\$100m and over.  

Depending on the length of the swap and the LIBOR reset intervals, they realized that they could extract up to an additional 8 10 bp from the transaction, irrespective of the shape of the yield curve. The counterparty, on the other hand, would see money “seep away over the life of the swap, even if it thought it was fully hedged,” said a trader.  

The added value is only significant on long-dated swaps—typically between five and 10 years—and in particular those based on 12-month LIBOR rather than the more traditional six-month LIBOR basis. This value is due to the convexity effect more commonly associated with the relationship between yields and the price of fixed income instruments.  

It therefore pays to be long convexity, and when applied to LIBOR-in-arrears structures proved to be profitable earlier this year. The first deals were transacted in New York and were restricted to the US dollar market, but in early May several other players were alerted to what was going on in the market and decided to apply the same concept in London. One trader expressed surprise at the lack of communication between dealers at different banks, a fact which allowed the arbitrage to continue both between banks directly and through swaps brokers.  

Also, “none of the US banks active in the market was involved in trying to exploit the same opportunities in other currencies,” he said, adding “you could play the same game in sterling—convexity applies to all currencies.”  

In fact, there was one day in May when the sterling market was flooded with these transactions, and it “lasted for several days” according to a sterling swaps dealer, “until everyone moved their prices out,” effectively putting a damper on further opportunities as well as making it difficult to unwind positions.  

Further, successful structures depend on cap volatility as the extra value is captured by selling caps against the LIBOR-in-arrears being received, in addition to delta hedging the swap. In this way value can be extracted from yield curves irrespective of the slope. “In some cap markets such as the yen, volatility isn’t high enough to make the deal work,” said one dealer. Most of the recent interbank activity has taken place in US dollars, sterling, and Australian dollars. As banks have become aware of the arbitrage, opportunities have become rarer, at least in the interbank market. But as one dealer remarked, “the reason this [structure] works is because swap traders think they know how to value LIBOR-in-arrears swaps in the old way, and they stick to those methods.” “Paying LIBOR in arrears without taking the convexity effect into account,” he added, “is like selling an option for free, but opportunities will still exist where traders stick to the old pricing method.” Many large swap players last week declined to comment, suggesting that the market is still alive, although BZW in London, which has been active in the market, did say that it saw such opportunities as a chance to pass on added value to its own customers. (Thomson Reuters IFR issue 1092, July 29, 1995)  

This page intentionally left blank  