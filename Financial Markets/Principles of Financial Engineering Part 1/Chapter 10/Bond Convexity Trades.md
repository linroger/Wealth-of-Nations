# 10.3 BOND CONVEXITY TRADES  

We have already seen convexity trades within the context of vanilla options. Straightforward discount bonds, especially those with long maturities, can be analyzed in a similar fashion and have exposure to interest rate volatility. In fact, a "long"' bond and a vanilla option are both convex instruments and they both coexist with instruments that are either linear or have less convexity.2. Hence, a delta-neutral portfolio can be put together for long maturity bonds to benefit from volatil-. ity shifts. The overall logic will be similar to the options discussed in the previous chapter..  

Consider a long maturity default-free discount bond with price $B(t,T)$ with $t<T.$ This bond's. price at time $t$ can be expressed using the corresponding time $t$ yield, $y_{t}^{T}$  

$$
B(t,T)=\frac{1}{(1+y_{t}^{T})^{T}}
$$  

For $t=0$ and $T=30$ , this function is plotted against various values of the 30-year zero-coupon yield, in Figure 10.2. It is obvious that the price is a convex function of the yield.  

A short bond, on the other hand, can be represented in a similar space with an almost linear curve. For example, Figure 10.3 plots a 1-year bond price. $B(0,1)$ against a 1-year yield $y_{0}^{1}$ .We see that the relationship is essentially linear.3.  

The main point here is that, under some conditions, using these two bonds we can put together a portfolio that will isolate bond convexity gains similar to the convexity gains that the dynamic hedging of options has generated. Thus, suppose movements in the two yields $\boldsymbol y_{t}^{1}$ and $y_{t}^{30}$ are perfectly correlated over time $t.^{4}$ Next, consider a trader who tries to duplicate the strategy of the option market maker discussed in the previous chapter. The trader buys the long bond with borrowed funds and delta hedges the first-order yield exposure by shorting an appropriate amount of the shorter maturity bond.  

This trader will have to borrow. $B(0,30)$ dollars to buy and fund the long bond position. The payoff of the portfolio.  

$$
\{\mathrm{Long~bond},\mathrm{loan~of~}B(0,30)\mathrm{dollars}\}
$$  

is as shown in Figure 10.2b as curve $\mathbf{BB^{\prime}}$ . Now compare this with Figure 10.2c. Here we show the profit/loss position of a market maker who buys an at-the-money \*put option' on the yield $y_{t}^{30}$ . At expiration time $T.$ the option will pay  

$$
P(T)=\operatorname*{max}[y_{0}^{30}-y_{T}^{30},0]
$$  

This option is financed by a money market loan so that the overall position is shown as the downward sloping curve $B B^{\prime}$ 5 We see a great deal of resemblance between the two positions.  

![](a2fa75e56ff757fd8c587f94de06b96b9409ab311ce9c42a2c8f2bf8deb4c4c3.jpg)  

# FIGURE 10.2  

Bond and put option as examples of convex instruments.  

![](2f194c3c852b954356c9d2ae7694ece850970d6166952013d0f9c3d316555f2b.jpg)  

# FIGURE 10.3  

Price--yield relationship for a short bond.  

Given this similarity between bonds and options, we should be able to isolate convexity or gamma trading gains in the case of bonds as well. In fact, once this is done, using an arbitrage argument, we should be able to obtain a partial differential equation (PDE) that default-free discount bond prices will satisfy. This PDE will have close similarities to the Black-Scholes PDE derived in Chapter 8.  

The discussion below proceeds under some simplifying and unrealistic assumptions. We use the. so-called one-factor model. Our purpose is to understand the mechanics of volatility trading in the case of bonds and this assumption simplifies the exposition significantly. Our context is different. than in real life, where fixed-income instruments are affected by more than a single common ran-. dom factor. Thus, we make two initial assumptions:.  

1. There is a short and a long default-free discount bond with maturities. $T^{s}$ and $T.$ respectively. Both bonds are liquid and can be traded without any transaction costs.   
2. The two bond prices depend on the same risk factor denoted by $r_{t}$ This can be interpreted as a. spot interest rate that captures all the randomness at time $t$ and is the single factor mentioned. earlier.  

The second assumption means that the two bond prices are a function of the short rate $r_{t}$ These functions can be written as  

$$
B(t,T^{S})=S(r_{t},t,T^{S})
$$  

and  

$$
B(t,T)=B(r_{t},t,T)
$$  

where $B(t,T^{s})$ is the time $t$ price of the short bond and $B(t,T)$ is the time $t$ price of the long bond. We postulate that the maturity $T^{s}$ is such that the short bond price $B(t,T^{s})$ is (almost) a linear function of $r_{t}$ , meaning that the second derivative of $B(t,T^{s})$ with respect to $r_{t}$ is negligible.  

Thus, we will proceed as if there was a single underlying risk that causes price fluctuations in a convex and a quasi-linear instrument, respectively. We will discuss the cash gains generated by the dynamically hedged bond portfolio in this environment.  

# 10.3.1 DELTA-HEDGED BOND PORTFOLIOS  

The trader buys the long bond with borrowed funds and then hedges the downside risk implied by the curve $A A^{\prime}$ in Figure 10.4. The hedge for the downside risk will be a position that makes money when $r_{t}$ increases and loses money when. $r_{t}$ declines. This can be accomplished by shorting an. appropriate number of the short bond..  

![](96a253d8c557d73b41c21c4964d993798e670001beae489a010d96f6a3213097.jpg)  

# FIGURE 10.4  

Delta-hedged bond portfolio.  

In fact, the trick to form a delta-neutral portfolio is the same as in Chapter 9. Take the partial derivative of the functions $S~(r_{t},t,T^{s})$ and $B(r_{t},t,T)$ with respect to $r_{t},$ evaluate them at point $r_{t_{0}}$ and use these to form a hedge ratio,. $h_{t}$  

$$
\begin{array}{c}{h_{t}=\displaystyle\frac{(\partial B(r_{t},t,T)/\partial r_{t})}{(\partial S(r_{t},t,T^{s})/\partial r_{t})}}\ {=\displaystyle\frac{B_{r}}{S_{r}}}\end{array}
$$  

$S_{r}$ is assumed to be a constant, given the quasi-linearity of the short bond price with respect to $r_{t}.h_{t}$ is a function of $r_{t}$ since $B_{r}$ is not constant due to the long bond's convexity. Given the value. of $r_{t_{0}},h_{t}$ can be numerically calculated, and $h_{t_{0}}$ units of the short maturity bond would be sold short. at $t_{0}$  

The change in the value of this portfolio due to a small change in the spot rate $\Delta r_{t}$ only is given by  

$$
\begin{array}{c}{\Delta[B(r_{t},t,T)-h_{t}S(r_{t},t,T^{s})]=B_{r}\Delta r_{t}-\frac{B_{r}}{S_{r}}S_{r}\Delta r_{t}+R}\ {=R}\end{array}
$$  

since the $S_{r}$ terms cancel out. $R$ is the remainder term of the implied Taylor series approximation,. or Ito's Lemma in this case, which depends essentially on the second derivative, $B_{r r}$ and on $r_{t}$ volatility. $S_{r}$ is approximately constant. This means that the net position,  

will have the familiar volatility position shown in the bottom part of Figure 10.4. As. $r_{t}$ fluctuates, this position is adjusted by buying and (short) selling an appropriate number of the nonconvex asset. The new value of partial derivative,. $h_{t},$ is used at each readjustment. Again, just as in. Chapter 8, this will make the practitioner "sell high' and "buy low" (or vice versa). As a result of these hedge adjustments, the counterparty who owns the long bond will earn gamma profits. These trading gains will be greater as volatility increases. Hence, we reach the result:.  

Everything else being the same, the greater the volatility of $r_{t},$ the more "valuable"' the long bond.  

This means that as volatility increases, ceteris paribus, the yield of the convex instruments should decline, since more market participants will try to put this trade in place and drive its price higher.  

# EXAMPLE  

Suppose that initially the yield curve is flat at $5\%$ . The value of a 30-year default-free discount bond is given by  

$$
\begin{array}{c}{{B(0,30)=\displaystyle\frac{1}{(1+0.05)^{30}}}}\ {{{}}}\ {{{}=0.23}}\end{array}
$$  

The original delta of the bond, $D_{t_{0}}$ at $r_{t_{0}}=0.05$ will be:.  

$$
\begin{array}{c}{{D_{t_{0}}=-\displaystyle\frac{30}{\big(1+r_{t_{0}}\big)^{31}}}}\ {{{}}}\ {{{}=-6.61}}\end{array}
$$  

A 1-year short bond is assumed to have an approximately linear pricing formula  

$$
\begin{array}{c}{{B(t_{0},T^{s})=\left(1-r_{t_{0}}\right)}}\ {{{}}}\ {{{}=0.95}}\end{array}
$$  

The market maker will borrow O.23 dollars, buy one long bond, and then hedge this position by shorting  

$$
\frac{-6.61}{-1.0}
$$  

nits of the short bond. (Given linearity approximation the short bond has unit interest sensitivity.)  

A small time, $\Delta$ , passes. All rates change, $r_{t}$ moves to $6\%$ . The portfolio value will move  

$$
\begin{array}{r l}{\Delta B(t,T)-h_{t}\Delta B(t,T^{s})=}&{{}\left[\frac{1}{\left(1+0.06\right)^{30}}-\frac{1}{\left(1+0.05\right)^{30}}\right]}\ {}&{{}-6.61[\left(1-0.6\right)-\left(1-0.0\bar{5}\right)]}\end{array}
$$  

Note that in calculating this number, we are assuming that $\Delta$ is small. Only the effect of changing $r_{t}$ is taken into account. In a sense, we are using a framework similar to partial derivatives.  

The new delta is calculated as. $-4.9$ . The adjusted portfolio should be short 4.9 units of the short bond. Thus,.  

$$
(6.6-4.9)=1.7
$$  

units need to be covered at a price of 0.94 each to bring the position to the desired deltaneutral state.  

This leaves a trading profit equal to  

$$
1.7(0.95-0.94)=\$0.017
$$  

Another period passes, with $r_{t}$ going back to $r_{t_{2}}=0.05$ . The cycle repeats itself. The delta will change again, the portfolio will be readjusted, and trading profits will continue to accumulate.  

This example is approximate, since not all costs of the position are taken into account. The. example started with the assumption of a flat yield curve, which was later relaxed and the yields became volatile. However, we never mentioned what causes this change. It turns out that volatility leads to additional gains for long bond holders and this increases the demand for them. As a result, ceteris paribus, long bond yields would decline relative to short bond yields. Hence, the introduction of yield volatility changed the structure of the initial yield curve..  

# 10.3.2 COSTS  

What are the costs (and other gains) of putting together such a long volatility position using default-free discount bonds? First, there is the funding cost. To buy the long bond, $B(t,T)$ funds were borrowed at $r_{t}$ percent per annum. As long as the position is kept open, interest expense will be incurred. Second, as time passes, the pricing function of the bond becomes less and less convex, and hence the portfolio's trading gains will respond less to volatility changes. Finally, as time passes, the value of the bonds will increase automatically even if the rates don't come down.  

# 10.3.3 A BOND PDE  

A PDE consisting of the gains from convexity of long bonds and costs of maintaining the volatility. position can be put together. Under some conditions, this PDE has an analytical solution, and an analytical formula can be obtained the way the Black-Scholes formula was obtained..  

First we discuss the PDE informally. We start with the trading gains due to convexity. These gains are given by the continuous adjustment of the hedge ratio $h_{t},$ which essentially depends on $B_{r},$ except for a constant of proportionality, since the hedging instrument is quasi-linear in $r_{t}.$ As $r_{t}$ changes, the partial $B_{r}$ changes, and this will be captured by the second derivative. Then, convexity gains during a small time interval $\Delta$ is a function, as in Chapter 9, of  

$$
\frac{1}{2}\frac{\partial^{2}B(t,T)}{\partial r_{t}^{2}}\left(\sigma(r_{t},t)r_{t}\sqrt{\Delta}\right)^{2}
$$  

This is quite similar to the case of vanilla options, except that here the $\sigma(r_{t},t)$ is the percentage short rate volatility. Short bond interest sensitivity will cancel out.  

If we model the risk-neutral dynamics of the short rate $r_{t}$ as  

$$
\mathrm{d}r_{t}=\mu(r_{t},t)\mathrm{d}t+\sigma/r_{t}\mathrm{d}W_{t}\quad t\in[0,T]
$$  

where percentage volatility $\sigma$ is constant, these gamma gains simplify to  

$$
\frac{1}{2}B_{r r}\sigma^{2}r_{t}^{2}\Delta
$$  

during a small period $\Delta$ o.  

$$
\frac{\partial^{2}B(t,T)}{\partial r_{t}^{2}}=B_{r r}
$$  

To these, we need to add (subtract) other costs and gains that the position holder is subject to. The interest paid during the period $\Delta$ on borrowed funds will be  

$$
r_{t}B(t,T)\Delta
$$  

The other gain (loss) is the direct effect of passing time  

$$
\frac{\partial B(t,T)}{\partial t}\Delta=B_{t}\Delta
$$  

As time passes, bonds earn accrued interest, and convexity declines due to "roll-down' on the. yield curve. The interest earned due to shorting the linear instrument will cancel out the cost of this short position.  

The final component of the gains and losses that the position is subject to during $\Delta$ is more complex than the case of a vanilla call or put. In the case of the option, the underlying stock, $S_{t}$ provided a very good delta hedging tool. The market maker sold $(\partial/\partial S_{t})C(S_{t},t)$ units of the underlying $S_{t}$ in order to hedge a long call position. In the present case, the underlying risk is not the stock price $S_{t}$ or some futures contract. The underlying risk is the spot rate $r_{t},$ and this is not an. asset. That is to say, the "hedge" is not. $r_{t}$ itself, but instead it is an asset indirectly influenced by. $r_{t}$ Also, randomness of interest rates requires projecting future interest gains and costs. All these complicate the cash flow analysis..  

These complications can be handled by positing that the drift term $\mu(r_{t},t)$ in the dynamics,  

$$
\mathrm{d}r_{t}=\mu(r_{t},t)\mathrm{d}t+\sigma r_{t}\mathrm{d}W_{t},\quad t\in[0,T]
$$  

represents the risk-free expected change in the spot rate over an infinitesimal interval ${\mathrm{d}}t$ Using this drift, we can write the last piece of gains and losses over a small interval $\Delta$ as (Vasicek, 1977):  

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

the par value of the default-free bond at maturity date $T.$  

# 10.3.4 PDEs AND CONDITIONAL EXPECTATIONS  

In this PDE, the unknown is again a function. $B(t,T)$ . This function will depend on the random process $r_{t},t,$ , as well as other parameters of the model. The most important of these is the short rate volatility, $\sigma$ If $r_{t}$ is the continuously compounded short rate, the solution is given by the conditional expectation  

$$
B(t,T)=E_{t}^{\tilde{P}}\left[e^{-\int_{t}^{T}r_{u}\mathrm{d}u}\right]
$$  

where $\tilde{P}$ is an appropriate probability. In other words, taking appropriate partial derivatives of the right-hand side of this expression, and then plugging these in the PDE would make the sum on the left-hand side of Eq. (10.32) equal to zero.  

It is interesting to look at the parallel with options. The pricing function for $B(t,T)$ was based on a particular conditional expectation and solved the bond PDE. In the case of vanilla options written on a stock $S_{t}.$ and satisfying all Black-Scholes assumptions, the call price $C(S_{t},t)$ is given by a similar conditional expectation,  

$$
C(S_{t},t)=E_{t}^{\tilde{P}}[e^{-r(T-t)}C(S_{T},T)]
$$  

where $T$ is the expiration date and $\tilde{P}$ is the appropriate probability. If this expectation is differentiated with respect to $S_{t}$ and $t.$ , the resulting partial derivatives will satisfy the Black-Scholes PDE. with the corresponding boundary condition. The main difference is that the Black-Scholes assumptions take the short rate $r_{t}$ to be constant, whereas in the case of bonds, it is a stochastic process.  

These comments reconcile the two views of options that were mentioned in Chapter 9. If we interpret options as directional instruments, then Eq. (10.35) will give the expected gains of the optional at expiration, under an appropriate probability. The argument above shows that this expectation solves the associated PDE which was approached as an arbitrage relationship tying gamma gains to other costs incurred during periodic rebalancing. In fact, we see that the two interpretations of options are equivalent.  

# 10.3.5 FROM BLACKSCHOLES TO BOND PDE  

Comparing the results of trading bond convexity with those obtained in trading vanilla options provides good insights into the general characteristics of PDE methods that are commonly used in finance.  

In Chapter 9, we derived a PDE for a plain vanilla call, $C\left(t\right)$ using the argument of convexity trading. In this chapter, we discussed a PDE that is satisfied by a default-free pure discount bond $B$ $(t,T)$ . The results were as follows.  

1. The price of a plain vanilla call, written on a nondividend-paying stock $S_{t},$ strike $K.$ expiration $T_{:}$ was shown to satisfy the following "arbitrage"' equality:  

$$
\frac{1}{2}C_{S S}(\sigma(S_{t},t)S_{t})^{2}\Delta=(r C-r C_{s}S_{t})\Delta-C_{t}\Delta
$$  

where $\boldsymbol{\sigma}(\boldsymbol{S}_{t},t)$ is the percentage volatility of. $S_{t}$ during 1 year. The way it is written here, this. percentage volatility could very well depend on time $t$ and $S_{t}$  

According to this equation, in order to preclude any arbitrage opportunities, trading gains obtained from dynamic hedging during a period of length $\Delta$ should equal the net funding cost, plus loss of time value. Canceling common terms and introducing the boundary condition yielded the Black-Scholes PDE for a vanilla call:  

$$
\begin{array}{r}{\frac{1}{2}C_{S S}(\sigma(S_{t},t)S_{t})^{2}+r C_{S}S_{t}-r C+C_{t}=0}\ {C(T)=\operatorname*{max}[S_{T}-K,0]\qquad}\end{array}
$$  

Under the additional assumption that $\sigma(S_{t},t)S_{t}$ is proportional to $S_{t}$ with a constant factor of proportionality $\sigma$  

$$
\sigma(S_{t},t)S_{t}=\sigma S_{t}
$$  

this PDE could be solved analytically, and a closed-form formula could be obtained for the $C$ $(t)$ . This formula is the Black-Scholes equation:.  

$$
C(t)=S_{t}N(d_{1})-K e^{-r(T-t)}N(d_{2})
$$  

$$
d_{1,2}={\frac{\log(S_{t}/K)+r(T-t)\pm(1/2)\sigma^{2}(T-t)}{\sigma{\sqrt{T-t}}}}
$$  

The partial derivatives of this $C(t)$ would satisfy the preceding PDE  

2. The procedure for a default-free pure discount bond $B(t,T)$ followed similar steps, with some noteworthy differences. Assuming that the continuously compounded spot interest rate, $r_{t},$ is the only factor in determining bond prices, the convexity gains due to oscillations in $r_{t}$ and to dynamic hedging can be isolated, and a similar "arbitrage relation"' can be obtained:  

$$
\frac{1}{2}B_{r r}(\sigma(r_{t},t)r)^{2}\Delta=(r_{t}B-\mu(r_{t},t)B_{r})\Delta-B_{t}\Delta
$$  

Here, $\sigma(r_{t},t)$ is the percentage volatility of the short rate $r_{t}$ during 1 year..  

Canceling common terms, and adding the boundary condition, we obtain the bond PDE:  

$$
\begin{array}{c}{{\frac{1}{2}B_{r r}\sigma^{2}r_{t}^{2}+\mu(r_{t},t)B_{r}-r_{t}B+B_{t}=0}}\ {{}}\ {{B(T,T)=1}}\end{array}
$$  

Under some special assumptions on the dynamic behavior of. $r_{t}$ , this bond PDE can be solved analytically, and a closed-form formula can be obtained.  

We now summarize some important differences between these parallel procedures. First, note. that the PDE for the vanilla option is obtained in an environment where the only risk comes from the asset price. $S_{t}$ , whereas for bonds the only risk is the interest rate. $r_{t}.$ which is not an asset. per se. Second, the previously mentioned difference accounts for the emergence of the term $\mu(r_{t},t)$ in the bond PDE, while no such nontransparent term existed in the call option PDE. The. $\mu(r_{t},t)$ represents the expected change in the spot rate during ${\mathrm{d}}t$ once the effect of interest rate. risk is taken out. Third, the. $\mu(r_{t},t)$ may itself depend on other parameters that affect interest rate. dynamics. It is obvious that under these conditions, the closed-form solution for $B(t,T)$ would depend on the same parameters. Note that in the case of the vanilla option, there was no such issue and the only relevant parameter was o. This point is important since it could make the bond price formula depend on all the parameters of the underlying random process, whereas in the. case of vanilla options, the Black-Scholes formula depended on the characteristics of the volatility parameter only.  

Before we close this section, a final parallel between the vanilla option and bond prices should be discussed. The PDE for a call option led to the closed-form Black-Scholes formula under some assumptions concerning the volatility of $S_{t}$ Are there similar closed-form solutions to the bond PDE? The answer is yes.  

# 10.3.6 CLOSED-FORM BOND PRICING FORMULAS  

Under different assumptions concerning short rate dynamics, we can indeed solve the bond PDE and obtain closed-form formulas. We consider three cases of increasing complexity. The cases are differentiated by the assumed short rate dynamics.  

# 10.3.6.1 Case 1  

The first case is simple. Suppose $r_{t}$ is constant at $r$ This gives the trivial dynamics,  

$$
\mathrm{d}r_{t}=0
$$  

where $\sigma$ and $\mu(r_{t},t)$ are both zero. The bond PDE in Eq. (10.43) then reduces to  

$$
\begin{array}{c}{{-r B+B_{t}=0}}\ {{}}\ {{B(T,T)=1}}\end{array}
$$  

This is a simple, ordinary differential equation. The solution $B(t,T)$ is given by  

$$
B(t,T)=e^{-r(T-t)}
$$  

# 10.3.6.2 Case 2  

The second case is known as the Vasicek model.1o Suppose the risk-adjusted dynamics of the spot :ate follows the mean-reverting process given by11  

$$
\mathrm{d}r_{t}=\alpha(\kappa-r_{t})\mathrm{d}t+\sigma\mathrm{d}W_{t}\quad t\in[0,T]
$$  

where $W_{t}$ is a Wiener process defined for a risk-adjusted probability.12  

Note that the volatility structure is restricted to constant absolute volatility denoted by. $\sigma$ Suppose, further, that the parameters. $\alpha,~\kappa,~\sigma$ , are known exactly. The fundamental PDE for a typi-. cal $B(t,T)$ will then reduce to.  

$$
B_{r}\alpha(\kappa-r_{t})+B_{t}+\frac12B_{r r}\sigma^{2}-r_{t}B=0
$$  

Using the boundary condition. $B(T,T)=1$ , this PDE can be solved analytically, to provide a closed-form formula for $B(t,T)$ . The closed-form solution is given by the expression  

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

Here, $r_{t}$ is the "current' observation of the spot rate.  

# 10.3.6.3 Case 3  

The third well-known case, where the bond PDE in Eq. (10.43) can be solved for a closed form, is the Cox-Ingersoll-Ross (CIR) model. In the CIR model, the spot rate. $r_{t}$ is assumed to obey the slightly different mean-reverting stochastic differential equation  

$$
\mathrm{d}r_{t}=\alpha(\kappa-r_{t})\mathrm{d}t+\sigma\sqrt{r_{t}}\mathrm{d}W_{t}\quad t\in[0,T]
$$  

which is known as the square-root specification of interest rate volatility. Here $W_{t}$ is a Wiener process under the risk-neutral probability.  

The closed-form bond pricing equation here is somewhat more complex than in the Vasicek model. It is given by  

$$
B(t,T)=A(t,T)e^{-C(t,T)r_{t}}
$$  

where the functions $A(t,T)$ and $C(t,T)$ are given by.  

$$
A(t,T)=\left(2\frac{\gamma e^{1/2(\alpha+\gamma)(T-t)}}{(\alpha+\gamma)(e^{\gamma(T-t)}-1)+2\gamma}\right)^{2\frac{\alpha\kappa}{\sigma^{2}}}
$$  

$$
C(t,T)=2\frac{e^{\gamma(T-t)}-1}{(\alpha+\gamma)(e^{\gamma(T-t)}-1)+2\gamma}
$$  

and where $\gamma$ is defined as  

$$
\gamma=\sqrt{(\alpha)^{2}+2\sigma^{2}}
$$  

The bond volatility $\sigma$ determines the risk premia in expected discount bond returns.  

# 10.3.7 A GENERALIZATION  

The previous sections showed that whenever two instruments depending on the same risk factor display different degrees of convexity, we can, in principle, put together a delta hedging strategy similar to the delta hedging of options discussed in Chapter 9. Whether this is worthwhile depends, of course, on the level of volatility relative to transaction costs and bid--ask spreads.  

When a market practitioner buys a convex instrument and short sells an appropriate number of a linear (or less convex) instrument, he or she will benefit from higher volatility. We then say that the position is long volatility or long gamma. This trader has purchased gamma. If, in contrast, the convex instrument is shorted and the linear instrument is purchased at proper ratios, the position will benefit when the volatility of the underlying decreases.  

As the case of long bonds shows, the idea that volatility can be isolated (to some degree), and then traded is very general, and can be implemented when instruments of different convexities are. available on the same risk. Of course, volatility can be such that transaction costs and bid-ask spreads make trading it unfeasible, but that is a different point. More important, if the yield curve slope changes due to the existence of a second factor, the approach presented in the previous sections will not guarantee convexity gains..  
