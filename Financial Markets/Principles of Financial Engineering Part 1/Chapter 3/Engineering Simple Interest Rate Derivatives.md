---
tags:
  - '#convergence_trade'
  - '#eurocurrency_futures'
  - '#forward_contracts'
  - '#fra_contracts'
  - '#futures_contracts'
  - '#hedging'
  - '#interest_rate_derivatives'
  - '#money_market'
  - '#risk_management'
  - '#yield_curve'
---
# 3.3 ENGINEERING SIMPLE INTEREST RATE DERIVATIVES  

Forwards, futures contracts, and the underlying interbank money markets involve some of the simplest cash flow exchanges. They are ideal for creating synthetic instruments for many reasons. The money market refers to a segment of the financial market which is used by participants as a means for borrowing and lending in the short term. Money markets are very liquid and maturities range from several days to just under a year. We can contrast the money market with the capital market for longer-term funding, which is supplied by bonds and equity.  

A forward or a futures contract can fix the future selling or buying price of an underlying item. This can be useful for hedging, arbitraging, and pricing purposes. They are essential in creating. synthetics. Consider the following interpretation.  

Foreign currency and commodity forwards (futures) are the simplest types of derivative instruments. Forwards and futures are, in general, linear permitting static replication. They are often. very liquid and, in case of currency forwards, have homogeneous underlying. Many technical complications are automatically eliminated by the homogeneity of a currency.' Forwards and futures on interest rates present more difficulties, and we discuss them in this chapter. The chapter discusses financial engineering methods that use forward loans, Eurocurrency futures, and FRAs. The discussion prepares the ground for the next chapter on swap-based financial engineering. In fact, the FRA contracts considered here are precursors to plain vanilla swaps.  

Interest rate strategies, hedging, and risk management present more difficulties than FX, equity, or commodity-related instruments for at least two reasons. First of all, the payoff of an interest rate . derivative depends, by definition, on some interest rate(s). In order to price the instrument, one needs to apply discount factors to the future payoffs and calculate the relevant present values. But the discount factor itself is an interest rate-dependent concept. If interest rates are stochastic, the present value of an interest rate-dependent cash flow will be a nonlinear random variable; the resulting expectations may not be as easy to calculate. There will be two sources of any future fluctuations-those due to future cash flows themselves and those due to changes in the discount factor applied to these cash flows. When dealing with equity or commodity derivatives, such non-. linearities are either not present or have a relatively minor impact on pricing. Second, every interest rate is associated with a maturity or tenor. This means that, in the case of interest rate derivatives we are not dealing with a single random variable, but with vector-valued stochastic processes. The existence of such a vector-valued random variable requires new methods of pricing, risk management, and strategic position taking. We start our discussion with interest rates and simple interest rate derivatives since interest rates are the foundation for pricing derivatives in other asset classes.  

# 3.3.1 A CONVERGENCE TRADE  

Before we start discussing replication of elementary interest rate derivatives we consider a real-life example.  

For a number of years before the European currency (euro) was born, there was significant uncertainty as to which countries would be permitted to form the group of euro users. During this period, market practitioners put in place the so-called convergence plays. The reading that follows is one example.  

# EXAMPLE  

Last week traders took positions on convergence at the periphery of Europe. Traders sold the spread between the Italian and Spanish curves. JP Morgan urged its customers to buy a   
$I2\times24$ Spanish FRA and sell a $I2\times24$ Italian FRA. According to the bank, the spread, which traded at   
133 bp would move down to below 50 bp (basis points). The logic of these trades was that if Spain entered the single currency, then Italy would also do so..   
Recently, the Spanish curve has traded below the Italian curve. According to this logic, the Italian yield   
curve would converge on the Spanish yield curve, and traders would gain..  

(Episode based on Thomson Reuters IFR issue number 1887).  

Traders buy and sell spreads in order to benefit from a likely occurrence of an event. In this episode, these spreads are sold using the FRAs, which we discuss in this chapter. If the two currencies converge, the difference between Italian and Spanish interest rates will decline.' The FRA positions will benefit. Note that market professionals call this selling the spread. As the spread goes down, they will profit-hence, in a sense they are short the spread. The example makes references to the yield curve.  

# 3.3.2 YIELD CURVE  

The yield curve is a curve that plots several interest rates or yields across different maturities for a given borrower in a given currency. The maturity can range from several days to 50 years..   
The contract length of the debt is typically referred to as the maturity or the term. Therefore, the.   
yield curve is also sometimes referred to as the term structure of interest rates. Figure 3.7 provides.   
a real-world example. It plots the US dollar yield curve on July 13, 2014. For comparison the.   
figure also shows the yield curve on June 15, 2007, that is, before the GFC. Short-term and.  

![](75972445610700049c0e864c92b6c6ed4fe8c1aaaaba8bfaa5d99e413ceb48cc.jpg)  
Note: X-axis (Maturity) is not to scale  

# FIGURE 3.7  

US Treasury yield curve.  

long-term yields exhibit significant variation over time and represent important risk factors for fixed income instruments.  

There are several ways of calculating the yield curve.' One approach to the calculation of the yield curve is based on zero-coupon bonds. We discuss alternative approaches in the Appendix to this chapter. We can calculate a yield curve using zero-coupon bonds with par value 100 based on the following definition of the yield to maturity:  

$$
B(t,T)=\frac{100}{(1+y_{t}^{T})^{T-t}}
$$  

where $B(t,T)$ is time $t$ price of default-free zero-coupon bond that pays 100 at time $T.$ The $y_{t}^{T}$ will correspond to the. $(T-t)$ -maturity zero-coupon yield.  

Broadly speaking, the yield curve can be calculated from prices available in the bond market or the money market and different methods lead to different results. Of course, there is no single yield curve describing the cost of money for every market participant since borrowing costs depend on the currency in which the securities are denominated as well as the creditworthiness of the borrower. Yield curves corresponding to the bonds issued by governments in their own currency are called government bond yield curves. Figure 3.8 shows Treasury yield curve for the United States, United Kingdom, Japan, and Germany on June 16, 2014. On that day, the spreads between yield  

![](ba90635e14501940286f88e35181065bda4d8a9450118a637c9d7a0ea83c5861.jpg)  

# FIGURE 3.8  

Treasury yield curves for US, Japan, and Germany on 16 June 2014.  

curves were as large as $200\mathrm{bps}$ in the case of the 10-year US and JPY treasuries. Yield curves based on money market prices may combine information on short-term LIBOR rates, futures prices, and interest rate swaps to plot the curve.  
