# 11.1 INTRODUCTION  

This chapter discusses traditional option strategies from the financial engineering perspective and provides market-based examples. It then moves on to discuss exotic options. We are concerned with portfolios and positions that are taken with a precise gain-loss profile in mind. The players. consciously take risks in the hope of benefiting or protecting themselves from an expected movement in a certain risk factor. Most investor behavior is of this kind. Investors buy a stock with a. higher (systematic) risk, in anticipation of higher returns. A high-yield bond carries a higher default probability, which the bond holder is willing to bear. For all the different instruments, there are one or more risk factors that influence the gains and losses of the position taken. The investor weighs the risks due to potentially adverse movements in these factors against the gains that will result, if these factors behave in the way the investor expected. Some of the hedging activity can be inter-. preted in a similar way. This chapter deals with techniques and strategies that use options in doing. this. We consider classical (vanilla) as well as exotic options tools.  

According to an important theorem in modern finance, if options of all strikes exist, carefully selected option portfolios can replicate any desired gain-loss profile that an investor or a hedger. desires. We can synthetically create any asset using a (static) portfolio of carefully selected options,' since financial positions are taken with a payoff in mind. Hence, we start our discussion. by looking at payoff diagrams.  

# 11.1.1 PAYOFF DIAGRAMS  

Let $x_{t}$ be a random variable representing the time- $t$ value of a risk factor, and let. $f(x_{T})$ be a function that indicates the payoff of an arbitrary instrument at "maturity" date $T.$ given the value of $x_{T}$ at time $T>t.$ We call $f(x_{T})$ a payoff function. The functional form of. $f\left(.\right)$ is known if the contract is well. defined.? It is customary in textbooks to represent the pair $\{f(x_{T}),x_{T}\}$ as in Figure 11.1 or 11.2. Note. that, here, we have a nonlinear upward sloping payoff function that depends on the values assumed by $x_{T}$ only. The payoff diagram in Figure 11.1 is drawn in a completely arbitrary fashion, yet, it illustrates some of the general principles of financial exposures. Let us review these.  

![](images/4465ca0304792d1a5bd9cc026d24300fa6dbc4a2e9ea5e89162e33cc8be13029.jpg)  

# FIGURE 11.1  

Payoff of nonlinear exposure.  

![](images/9fef3ed7e02188eba222b5d83c833b754abb34f48be1c96e72156ffc53e207d9.jpg)  

# FIGURE 11.2  

Payoff of a linear exposure.  

First of all, for fairly priced exposures that have zero value of initiation, net exposures to a risk factor, $x_{T}$ must be negative for some values of the underlying risk. Otherwise, we would be making positive gains, and there would be no risk of losing money. This would be an arbitrage opportunity. Swap-type instruments fall into this category. If, on the other hand, the final payoffs of the contract are non-negative for all values of. $x_{T}$ the exposure has a positive value at initiation, and to take the. position an upfront payment will have to be made. Option positions have this characteristic.3  

Second, exposures can be convex, concave, or linear with respect to $x_{T}$ and this has relevance for an investor or market professional. The implication of linearity is obvious: the sensitivity of the position to movements in $x_{T}$ is constant. The relevance of convexity was discussed in Chapters 9 and 10. With convexity, movements in volatility need to be priced in, and again options are an important category here.  

Finally, it is preferable that the payoff functions. $f(x_{T})$ depend only on the underlying risk,. $x_{T},$ and do not move due to extraneous risks. We saw in Chapters 9 and 10 that volatility positions. taken with options may not satisfy this requirement. The issue will be discussed in Chapter 15.  

# 11.1.1.1 Examples of $\pmb{\chi}_{\mathfrak{t}}$  

The discussion thus far dealt with an abstract underlying, $x_{t}$ This underlying can be almost any risk the human mind can think of. The following lists some well-known examples of $x_{t}$  

Various interest rates: The best examples are LIBOR rates and swap rates. But the commercial paper (CP) rate, the federal funds rate, the index of overnight interest rates (an example of which is EONIA, Euro Over Night Index Average), and many others are also used as reference rates. Exchange rates, especially major exchange rates such as dollar--euro, dollar--yen, dollar-sterling ("cable'), and dollar-Swiss franc. Equity indices: Here also the examples are numerous. Besides the well-known US indices such as the Dow, NASDAQ, and the S&P500, there are European indices such as CAC40, DAX, and FTSE100, as well as various Asian indices such as the Nikkei 225 and emerging market indices. Commodities are also quite amenable to such positions. Futures on coffee, soybeans, and energy are other examples for $x_{T}.$ Bond price indices: One example is the EMBI $^+$ prepared by JPMorgan to track emerging. market bonds.  

Besides these well-known risks, there are more complicated underlyings that, nevertheless, are central elements in financial market activity:  

1. The underlying to the option positions discussed in this chapter can represent volatility or variance. If we let the percentage volatility of a price, at time $t.$ be denoted by $\sigma_{t},$ then the time $T$ value of the underlying $x_{T}$ may be defined as  

$$
x_{T}=\displaystyle\int_{t}^{T}\sigma_{u}^{2}S_{u}^{2}\mathrm{d}u
$$  

where $S_{u}$ may be any risk factor. In this case, $x_{T}$ represents the total variance of $S_{u}$ during the interval $[t,T]$ Volatility is the square root of. $x_{T}$  

.. The correlation between two risk factors can be traded in a similar way.  

3. The underlying, $x_{t}$ can also represent the default probability associated with a counterparty or instrument. This arises in the case of credit instruments.  

4. The underlying can represent the probability of an extraordinary event happening. This would. create a "Cat' instrument that can be used to buy insurance against various catastrophic events.   
5. The underlying, $x_{t}$ can also be a nonstorable item such as electricity, weather, or bandwidth..  

Readers who are interested in the details of such contracts or markets should consult Hull (2014). In this chapter, we limit our attention to the engineering aspects of option contracts.  
