---
tags:
  - '#autocallables'
  - '#cppi_techniques'
  - '#dppi'
  - '#gap_risk'
  - '#liquidity_risk'
  - '#monte_carlo_simulations'
  - '#obpi'
  - '#out_of_the_money_puts'
  - '#portfolio_insurance'
  - '#principal_protection_techniques'
---
# 23.9 REAL-WORLD COMPLICATIONS  

The idea behind CPPI techniques is simple. Actually, even the modeling is fairly straightforward.   
Yet, in practice, several difficulties arise. We will look at only some of them..  

# 23.9.1 THE GAP RISK  

If a structurer does not want exposure to gap risk then it could be sold to other investors through other structured products. For example, with structured products such as autocallables, a high coupon is paid to the investor, but the structure is called automatically if the underlying price hits a preselected level. Note that with autocallables the investor receives a high coupon but also assumes the risk of large downward movements in a basket. The extra coupon received by the investor can be visualized as the cost of insuring the gap risk.1o  

Another possibility frequently used in practice is to manage the gap risk using deep out-of-themoney puts. This is possible if the underlying is liquid. However, in the case of CPPI strategies, the underlying is often illiquid and this makes delta-hedging of the option positions difficult. Still, one can claim that during stress periods, correlations go toward one and liquid indices can become correlated with the illiquid underlying. Hence, carefully chosen deep out-of-the-money options on liquid indices can also hedge the gap risk. Banks generally charge a small "protection' or "gap fee to cover gap risk, usually as a function of the notional leveraged exposure.  

# 23.9.2 THE ISSUE OF LIQUIDITY  

The issue of liquidity of the underlying is important to CPPI-type strategies for several reasons.. First is the need to close the risky asset position when the cushion goes toward zero. If the underly-. ing market is not liquid this may be very difficult to do, especially when markets are falling at a steep rate.11  

Second, if the underlying is illiquid, then options on the underlying may not trade and hedging the gap risk through out-of-the-money options may be impossible..  

The third issue is more technical. As mentioned in the previous section, gap risk can be. modeled using the jump process augmented stochastic differential equations for. $S_{t}.$ In this setting, jump risk is the probability that $C u_{t}$ is negative. This determines the numerical value selected for the. $\lambda$ parameter. However, note that if the underlying is not liquid,. then options on this underlying will not be liquid either. Yet, liquid option prices are needed to calibrate the parameters of the jump process. With illiquid option markets this may be impossible. Essentially, the selection of. $\lambda$ would depend on arbitrarily made assumptions and/or. historical data.  

# 23.9.3 WHICH PRINCIPAL PROTECTION TECHNIQUE IS BEST IN PRACTICE?  

In the introduction to this chapter, we noted that different principal protection techniques exist including OBPI, CPPI, DPPI, and others. Which principal protection technique works best in practice? It turns out that this is an empirical question and no theoretical ranking of the techniques can be provided. Options can at certain times be very expensive, making OBPI unattractive. At first glance, CPPI may appear similar to standard option replication strategies. However, there are fundamental differences since standard CPPI does not make assumptions about future portfolio volatility, the distribution of portfolio returns, or the investor's time horizon. Because of the way that the cushion adjusts in CPPI, this approach will work well in a trending bull market with no reversals, since the hedger will keep increasing her exposure. There are some market environments when CPPI is less likely to do well. In a market without trends and oscillating prices, CPPI can be expected to perform poorly, since the hedge will buy on up-moves in prices only to see the market weaken subsequently and sell on down-moves in prices only to see the market rebound. Monte Carlo simulations and historical backtests that are specific to the underlying asset of interest and that incorporate assumptions about future market environments are required to decide which PPI technique generates the best risk-adjust performance for the hedger or investor. For the S&P500, for example, Lu (2010) provides a comparison of the performance of different portfolio insurance approaches including OBPI, CPPI, and DPPI.  
