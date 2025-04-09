# 9.8 CONCLUSION: WHAT IS AN OPTION?  

This chapter has shown that an option is essentially a volatility instrument. The critical parameter is how much the underlying risk oscillates within a given interval. We also saw that there are many other risks to manage. The implied volatility parameter, $\sigma$ , may change, interest rates may fluctuate, and option sensitivities may behave unexpectedly. These risks are not "costs" of maintaining the position perhaps, but they affect pricing and play an important role in option trading.  

# SUGGESTED READING  

Most textbooks approach options as directional instruments. There are, however, some nontechnical. sources that treat options as volatility instruments directly. The first to come to mind is Natenberg. (1994). A reader who prefers a technical approach has to consider more abstract treatments such as. Musiela and Rutkowski (1998). Several texts discuss Black-Scholes theory. The one that we recommend is Duffie (2001). Readers should look at Wilmott (2006) for the technical details. For the useful combination of options analysis with Mathematica, the reader can consult Stojanovic. (2003). Risk publications have several books that collect articles that have the same approach used. in this chapter. There, the reader will find a comprehensive discussion of the Black-Scholes formula. Examples on Greeks were based on the terminology used in Derivatives Week (now part of GlobalCapital).  

# APPENDIX 9.1  

In this appendix, we derive formulas for delta and gamma. The relatively lengthy derivation is for delta.  

# DERIVATION OF DELTA  

The Black--Scholes formula for a plain vanilla European call expiration $T.$ strike, $K$ , is given by  

$$
C(S_{t},t)=S_{t}\int_{-\infty}^{\log(\frac{S_{t}/K}{\sigma\sqrt{T-t}}+(1/2)\sigma^{2})(T-t)}\frac{1}{\sqrt{2}\pi}e^{-(1/2)u^{2}}\mathrm{d}u-e^{-r(T-t)}K\int_{-\infty}^{\log(\frac{S_{t}/K}{\sigma\sqrt{T-t}}+(r-1/2)\sigma^{2})(T-t)}\frac{1}{\sqrt{2}\pi}e^{-(1/2)u^{2}}\mathrm{d}u
$$  

Rearrange and let $x_{t}=(S_{t}/K e^{-r(T-t)})$ to get  

$$
C(x_{t},t)=K e^{-r(T-t)}\left[x_{t}\int_{-\infty}^{\infty}\frac{x_{t}+(1/2)\sigma^{2}(T-t)}{\sqrt{2}\pi}\frac{1}{\sqrt{2}\pi}e^{-(1/2)u^{2}}\mathrm{d}u-\int_{-\infty}^{\frac{\log x_{t}-(1/2)\sigma^{2}(T-t)}{\sigma\sqrt{T-1}}}\right]
$$  

$$
\frac{1}{\sqrt{2}\pi}e^{-(1/2)u^{2}}\mathrm{d}u
$$  

Now differentiate with respect to $x_{t}$  

$$
\frac{\mathrm{d}C(x_{t},t)}{\mathrm{d}x_{t}}=K e^{-r(T-t)}\left[\int_{-\infty}^{\frac{\log x_{t}+(1/2)\sigma^{2}(T-t)}{\sigma\sqrt{T-t}}}\frac{1}{\sqrt{2}\pi}e^{-(1/2)u^{2}}\mathrm{d}u\right]+\frac{1}{\sigma\sqrt{T-t}}
$$  

$$
\left[{\frac{1}{\sqrt{2}\pi}}e^{-{\frac{1}{2}}\left({\frac{\log x_{I}+(1/2)\sigma^{2}(T-t)}{\sigma{\sqrt{T-t}}}}\right)^{2}}\right]
$$  

$$
-\left[{\frac{1}{x_{t}\sigma{\sqrt{T-t}}}}{\frac{1}{\sqrt{2\pi}}}e^{-{\frac{1}{2}}\left({\frac{\log x_{t}-(1/2)\sigma^{2}(T-t)}{\sigma{\sqrt{T-t}}}}\right)^{2}}\right]
$$  

Now we show that the last two terms in this expression sum to zero and that  

$$
{\frac{1}{\sigma{\sqrt{T-t}}}}\left[{\frac{1}{\sqrt{2}\pi}}e^{-{\frac{1}{2}}\left({\frac{\log x_{t}+(1/2)\sigma^{2}(T-t)}{\sigma{\sqrt{T-t}}}}\right)^{2}}\right]={\frac{1}{x_{t}\sigma{\sqrt{T-t}}}}{\frac{1}{\sqrt{2\pi}}}e^{-{\frac{1}{2}}\left({\frac{\log x_{t}-(1/2)\sigma^{2}(T-t)}{\sigma{\sqrt{T-t}}}}\right)^{2}}
$$  

To see this, on the right-hand side, use the substitution:  

$$
\frac{1}{x_{t}}=e^{-\log x_{t}}
$$  

and then rearrange the exponent in the exponential function.  

Thus, we are left with  

$$
\frac{\partial C(x_{t},t)}{\partial x_{t}}=K e^{-r(T-t)}\left[\int_{-\infty}^{\frac{\log x_{t}+(1/2)\sigma^{2}(T-t)}{\sigma\sqrt{T-t}}}\frac{1}{\sqrt{2}\pi}e^{-(1/2)u^{2}}\mathrm{d}u\right]
$$  

Now use the chain rule and obtain  

$$
\frac{\partial C(S_{t},t)}{\partial S_{t}}=\left[\int_{-\infty}^{\log{x_{t}+(1/2)\sigma^{2}(T-t)}}\frac{1}{\sqrt{2}\pi}e^{-(1/2)u^{2}}\mathrm{d}u\right]
$$  

$$
=N(d_{1})
$$  

# DERIVATION OF GAMMA  

Once delta of a European call is obtained, the gamma will be the derivative of the delta. This gives  

$$
\frac{\partial^{2}C(S_{t},t)}{\partial S_{t}^{2}}=\frac{1}{S_{t}\sigma\sqrt{T-t}}\frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}\left(\frac{\log{x_{t}+(1/2)\sigma^{2}(T-t)}}{\sigma\sqrt{T-t}}\right)^{2}}
$$  

with $x_{t}=(S_{t}/K e^{-r(T-t)})$  

# APPENDIX 9.2  

In this appendix, we review some basic concepts from stochastic calculus. This brief review can be used as a reference point for some of the concepts utilized in later chapters. Oksendal (2010) is a good source that provides an introductory discussion on stochastic calculus. Heuristics can be found in Hirsa and Neftci (2013).  

# STOCHASTIC DIFFERENTIAL EQUATIONS  

An SDE, driven by a Wiener process $W_{t},$ is written as  

$$
\mathrm{d}S_{t}=a(S_{t},t)\mathrm{d}t+b(S_{t},t)\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

This equation describes the dynamics of. $S_{t}$ over time. The Wiener process $W_{t}$ has increments $\Delta W_{t}$ that are normally distributed with mean zero and variance. $\Delta$ where the $\Delta$ is a small time. interval. These increments are uncorrelated over time. As a result, the future increments of a Wiener process are unpredictable given the information at time. $t.$ the $I_{t}$  

The $a(S_{t},t)$ and the $b(S_{t},t)$ are known as the drift and the diffusion parameters. The drift parameter models expected changes in $S_{t}$ The diffusion component models the corresponding volatility. When unpredictable movements occur as jumps, this will be referred as a jump component.  

A jump component would require adding terms such as $\lambda(S_{t},t)\mathrm{d}J_{t}$ to the right-hand side of the. SDE shown above. Otherwise $S_{t}$ will be known as a diffusion process. With a jump component it becomes a jump-diffusion process.  

# Examples  

The simplest SDE is the one where the drift and diffusion coefficients are independent of the information received over time:  

$$
\mathrm{d}S_{t}=\mu\mathrm{d}t+\sigma\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

Here, $W_{t}$ is a standard Wiener process with variance $t.$ In this SDE, the coefficients $\mu$ and $\sigma$ do not have time subscripts. $t$ as time passes, they do not change.  

The standard SDE used to model underlying asset prices is the geometric process. It is the model assumed in the Black and Scholes world:  

$$
\mathrm{d}S_{t}=\mu S_{t}\mathrm{d}t+\sigma S_{t}\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

This model implies that drift and the diffusion parameters change proportionally with $S_{t}$  

An SDE that has been found useful in modeling interest rates is the mean reverting model:  

$$
\mathrm{d}S_{t}=\lambda(\mu-S_{t})\mathrm{d}t+\sigma S_{t}\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

According to this, as $S_{t}$ falls below a "long-run mean" $\mu$ , the term $(\mu-S_{t})$ will become positive, which makes $\mathrm{d}S_{t}$ more likely to be positive, hence, $S_{t}$ will revert back to the mean $\mu$  

# ITO'S LEMMA  

Suppose $f(S_{t})$ is a function of a random process $S_{t}$ having the dynamics:  

$$
\mathrm{d}S_{t}=a(S_{t},t)\mathrm{d}t+b(S_{t},t)\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

We want to expand $f\left(S_{t}\right)$ around a known value of $S_{t},$ say $S_{0}$ using Taylor series expansions. The expansion will yield:  

$$
f(S_{t})=f(S_{0})+f_{s}(S_{0})[S_{t}-S_{0}]+\frac{1}{2}f_{s s}(S_{0})[S_{t}-S_{0}]^{2}+R(S_{t},S_{0})
$$  

where $R(S_{t},S_{0})$ represents all the remaining terms of the Taylor series expansion.  

First note that $f(S_{t})$ can be rewritten as, $f\left({{S}_{0}}+\Delta{{S}_{t}}\right)$ , if we define $\Delta S_{t}$ as:  

$$
\Delta S_{t}=S_{t}-S_{0}
$$  

Then, the Taylor series approximation will have the form:  

$$
f(S_{0}+\Delta S_{t})-f(S_{0})\cong f_{s}\Delta S_{t}+\frac{1}{2}f_{s s}\Delta S_{t}^{2}
$$  

The $\Delta S_{t}$ is a "small' change in the random variable $S_{t}$ In approximating the right-hand side, we keep the term $f_{s}\Delta S_{t}$  

Consider the second term $(1/2)f_{s s}(\Delta S_{t})^{2}$ . If $S_{t}$ is deterministic, one can say that the term $(\Delta S_{t})^{2}$ is small. This could be justified by keeping the size of $\Delta S_{t}$ non-negligible, yet small enough that its square $\left(\Delta S_{t}\right)^{2}$ is negligible. However, here, changes in $S_{t}$ will be random. Suppose these changes have zero mean. Then the variance is  

$$
0<E[\Delta S_{t}]^{2}\cong b(S_{t},t)^{2}\Delta
$$  

This equality means that as long as $S_{t}$ is random, the right-hand side of Eq. (9.121) must keep the second-order term in any type of Taylor series approximation.  

Moving to infinitesimal time $\mathrm{d}t$ , this gives Ito's Lemma, which is the stochastic version of the Chain rule,  

$$
\mathrm{d}f(S_{t})=f_{s}\mathrm{d}S_{t}+\frac{1}{2}f_{s s}b(S_{t},t)^{2}\mathrm{d}t
$$  

This equation can be regarded as the dynamics of the process $f(S_{t})$ , which is driven by $S_{t}$ The $\mathrm{d}S_{t}$ term in the above equation can be substituted out using the $S_{t}$ dynamics.  

# GIRSANOV THEOREM  

Girsanov Theorem provides the general framework for transforming one probability measure into another "equivalent" measure. It is an abstract result that plays a very important role in pricing.  

In heuristic terms, this theorem says the following. If we are given a Wiener process $W_{t}$ , then, we can multiply the probability distribution of this process by a special function $\xi_{t}$ that depends on time. $t_{:}$ and on the information available at time. $t$ the $I_{t}$ This way we can obtain a new Wiener process $\tilde{W}_{t}$ with probability distribution. $\tilde{P}$ . The two processes will relate to each other through the relation:  

$$
\mathrm{d}\tilde{W}_{t}=\mathrm{d}W_{t}-X_{t}\mathrm{d}t
$$  

That is to say, $\tilde{W}_{t}$ is obtained by subtracting an $I_{t}$ dependent term $X_{t},$ from $W_{t}$  

Girsanov Theorem is often used in the following way: (i) we have an expectation to calculate, (ii) we transform the original probability measure, such that expectation becomes easier to calculate, and (ii) we calculate the expectation under the new probability..  

# EXERCISES  

1. Consider the following comment dealing with options written on the euro-dollar exchange rate:  

Some traders, thinking that implied volatility was too high entered new trades. One. example was to sell one-year in-the-money euro Puts with strikes around UsD1.10 and buy. one-year at-the-money euro Puts. If the euro is above UsD1.10 at maturity, the trader makes the difference in the premiums. The trades were put on across the curve. (Based on an article in Derivatives Week (now part of GlobalCapital))..  

a. Draw the profit/loss diagrams of this position at expiration for each option separately.   
b. What would be the gross payoff at expiry?   
c.What would be the net payoff at expiry?   
d. Why would the traders buy "volatility' given that they buy and sell options? Don't these two cancel each other in terms of volatility exposure?  

2. (Delta Hedge Portfolio)  

Write a VBA program to show the delta-hedged portfolio adjustments and cash flows for a long call from the dealers' perspective with the following data:.  

Total number of long calls $N=100$ Number of adjustments $M=15$ $S(0)=100\$ $K=100$ $T=1$ $r=8\%$ $\sigma=30\%$ ; and realized volatility $=50\%$  

3. Consider the following quote:  

Implied U.S. dollar/New Zealand dollar volatility fell to. $I0.I\%/I I.I\%$ on Tuesday. Traders   
bought at-the-money options at the beginning of the week, ahead of the Federal Reserve.   
interest-rate cut. They anticipated a rate cut which would increase short-term volatility. They.   
wanted to be long gamma. Trades were typically for one-week maturities, in average notionals   
of UsD10-20 million. (Based on an article in Derivatives Week (now part of GlobalCapital)).   
a. Explain why traders wanted to be long gamma when the volatility was expected to increase.   
b. Show your argument using numerical values for Greeks and the data given in the reading.  

c. How much money would the trader lose under these circumstances? Calculate approximately, using the data supplied in the reading. Assume that the position was originally for USD30 million..  

4. Consider the following episode:  

EUR/USD one-month implied volatility sank by $2.7\%$ to $10\%$ Wednesday as traders hedged this euro exposure against the greenback, as the euro plunged to historic lows on the spot market. After the European Central Bank raised interest rates by 25 basis points, the euro fell against leading to a strong demand for euro Puts. The euro touched a low of USD0.931 Wednesday. (Based on an article in Derivatives Week.)  

a. In the euro/dollar market, traders rushed to stock up on gamma by buying short-dated eurc puts struck below USD0.88 to hedge against the possibility that the interest rates rise. Under normal circumstances, what would happen to the currency?   
b. When the euro failed to respond and fell against major currencies, why would the traders then rush to buy euro puts? Explain using payoff diagrams.   
c. Would a trader "stock up' gamma if euro-triggered barrier options?  

5. You are given the following table concerning the price of a put option satisfying all Black-Scholes assumptions. The strike is 20 and the volatility is $30\%$ . The risk-free rate is $2.5\%$  

<html><body><table><tr><td>OptionPrice</td><td>Underlying Asset Price</td></tr><tr><td>10</td><td>10</td></tr><tr><td>5</td><td>15</td></tr><tr><td>1.3</td><td>20</td></tr><tr><td>0.25</td><td>25</td></tr><tr><td>0.14</td><td>30</td></tr></table></body></html>  

The option expires in 100 days. Assume (for convenience), that, for every month the option loses approximately one-third of its value.  

a. How can you approximate the option delta? Calculate three approximations for the delta in the previous case.   
b. Suppose you bought the option when the underlying was at 20 using borrowed funds. You have hedged this position in a standard fashion. How much do you gain or lose in four equal time periods if you observe the following price sequence in that order:.  

c. Suppose now that the underlying price follows the new trajectory given by  

How much do you gain or lose until expiration? d. Explain the difference between gains and losses.  

6. Search the Internet for the following questions. a. Which sensitivities do the Greeks, volga and Vanna represent? b. Why are they relevant for vega hedging?  

"Exploiting the franc peg' [...].  

The Swiss currency is no longer rallying the way it did during market distress on Eurozone debt concerns. It all changed when the Swiss National Bank (SNB) announcement pegging its currency against the euro at the EUR/CHF rate of 1.20, aimed at preventing excessive franc acceleration against the debt-ridden euro. As credit rating agencies rushed to downgrade the sovereign debt of Southern Europe in late 2o09, investors rushed their savings out of the single currency and into safe-haven francs. The exodus took the form of cash flight, property sales and bank transfers as "default" became a recurring theme in Greece, Spain, Portugal, Ireland and Italy.  

Consequently, the franc soared $35\%$ and $40\%$ against the euro and the USD respectively from 2009 to September 2011. The SNB began massive interventions in March 2009 to sell its currency for euros to stem the tide of the soaring franc. But the surge of franc-bound capital caused the SNB to lose more than CHF 20 billion from early 2009 to end of 2010. When the central bank's losses became a matter of national urgency, it ultimately went with the "nuclear option.". On Sept. 6, 2011 the SNB announced it "will no longer tolerate a EUR/CHF exchange rate below the minimum rate of CHF 1.20. The SNB will enforce this minimum rate with the utmost determination and is prepared to buy foreign. currency in unlimited quantities."  

SNB had pegged its currency once before against the Deutsche mark in 1978 after francs soared close to. $100\%$ near doubling in the prior six years as a result of U.S. stagflation following the oil crisis. The franc/mark peg lasted two years and dragged down the franc's effective trade index by about. $I4\%$  

The question then becomes whether the SNB remains successful in stemming further CHF strength. Will it make sense to sell the franc into 2012? As of this writing, the Swiss franc lost nearly one third of its value against the euro and U.S. dollar since the euro peg began in September..  

Our favorite pick against the Swiss franc would be the Canadian dollar because of ongoing volatility in oil prices stemming from Mideast uncertainty. Aside from the energy argument sustaining the loonie, any surprise bounce in U.S. growth is likely to help loonie sentiment. CAD/CHF is seen extending gains towards 0.96 from the current 0.90, with support cropping up at 0.88. An alternative but similar trade would be to combine longs in UsD/CHF with shorts in USD/CAD." (source: www.futuresmag.com, Exploiting the franc peg, by Ashraf Laidi, January 1, 2012)  

7. Answer the questions related to the case study Swiss Central Bank, 2012: a. What is the rationale for the proposed futures strategy b. What options strategy could you consider that would also benefit from the peg?  

8. (MATLAB exercise on European Option)  

Write a MATLAB program to determine the initial price of European Call and European Put option using the BSM formula with the following data:  

Now plot the initial price of both call and put options by varying the following parameters t a time while keeping the other parameters fixed.  

a. $S(0)$   
b. $K$   
c. $r$   
d. $\sigma$  

Also plot the initial call and put price juxtaposed by varying two parameters at a time and keeping other parameters fixed.  

e. $S(0)$ & $K$ f. $K$ & $\sigma$ g. $S(0)$ & $\sigma$  

9. (MATLAB exercise on Chooser Option)  

Write a MATLAB program to determine the initial price of chooser option using the BSM formula with the following data:  

$S(0)=100\$ $K=105$ $T_{0}=0.5$ $T=1$ $r=8\%$ $\sigma=30\%$  

Now plot the initial price of option by varying the following parameters at a time while eeping the other parameters fixed.  

a. s(O)   
b. $K$   
c. $T_{0}$ Also plot the variation of option price with $T_{0}$ & $T$ together and keeping other parameters   
fixed.  

10. (MATLAB exercise on Barrier Option)  

Write a MATLAB program to determine the initial price of Barrier Down and In Call option and Barrier Down and Out Call option using the BSM formula with the following data: $S(0)=100\$ $K=105$ $T=1$ $r=8\%$ $\sigma=30\%$ $H=95$  

Now plot the initial price of both call and put options by varying the following parameters at a time while keeping the other parameters fixed.  

a. $S(0)$   
b. $K$   
C. $H$  

11. MATLAB exercise on a Delta-Hedged Portfolio  

Write a MATLAB program to delta hedge the portfolio consisting only of the stock and the risk-free asset to cover the long call option. Observe the number of shorted shares and the cash flow during the adjustment of the portfolio to make it delta neutral at each time point. Report the final cash position at the expiration after settling all the open positions.  

Gradually increase the frequency of adjustment and observe the net cash position and also plot the performance vs frequency of this delta hedging that how correctly it covers the long call position.  

Use the following data:   
$S(0)=100\$ $K=105$ $T=1$ $r=8\%$ $\sigma=30\%$ and realized volatility $=50\%$   
Frequency: [6, 12, 50, 100, 300]  

# ENGINEERING CONVEXITY POSITIONS  

# 10  

# SHAPTER OUTLINE  

10.1 Introduction. 32(   
10.2 A Puzzle. 320   
0.3 Bond Convexity Trades . 321   
10.3.1 Delta-Hedged Bond Portfolios.. 325   
10.3.2 Costs.. 328   
10.3.3 A Bond PDE. 328   
10.3.4 PDEs and Conditional Expectations. 330   
10.3.5 From Black-Scholes to Bond PDE. 330   
10.3.6 Closed-Form Bond Pricing Formulas. 332   
10.3.6.1 Case 1. 332   
10.3.6.2 Case 2. 332   
10.3.6.3 Case 3. 333   
10.3.7 A Generalization. 333  
