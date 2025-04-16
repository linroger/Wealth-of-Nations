---
tags:
  - '#black_scholes_merton'
  - '#exchange_rate_movements'
  - '#foreign_currency_options'
  - '#heavy_tails'
  - '#implied_volatility'
  - '#jumps_in_exchange_rates'
  - '#lognormal_distribution'
  - '#non_constant_volatility'
  - '#option_maturity'
  - '#volatility_smile'
---
# 20.2 VOLATILITY SMILE FOR FOREIGN CURRENCY OPTIONS  

The volatility smile used by traders to price foreign currency options tends to have the general form shown in Figure 20.1. The implied volatility is relatively low for at-themoney options. It becomes progressively higher as an option moves either into the. money or out of the money.  

In the appendix at the end of this chapter, we show how to determine the risk-neutral probability distribution for an asset price at a future time from the volatility smile given by options maturing at that time. We refer to this as the implied distribution. The volatility smile in Figure 20.1 corresponds to the implied distribution shown by the solid line in Figure 20.2. A lognormal distribution with the same mean and standard deviation as the implied distribution is shown by the dashed line in Figure 20.2. It can be seen that the implied distribution has heavier tails than the lognormal distribution.'  

To see that Figures 20.1 and 20.2 are consistent with each other, consider first a deepout-of-the-money call option with a high strike price of. $K_{2}$ $(K_{2}/S_{0}$ well above 1.0). This option pays off only if the exchange rate proves to be above. $K_{2}$ . Figure 20.2 shows that the probability of this is higher for the implied probability distribution than for the lognormal distribution. We therefore expect the implied distribution to give a relatively high price for the option. A relatively high price leads to a relatively high implied volatility--and this is exactly what we observe in Figure 20.1 for the option. The two figures are therefore consistent with each other for high strike prices. Consider next a deep-out-of-the-money put option with a low strike price of. $K_{1}$ $K_{1}/S_{0}$ well below 1.0).. This option pays off only if the exchange rate proves to be below. $K_{1}$ . Figure 20.2 shows. that the probability of this is also higher for the implied probability distribution than for the lognormal distribution. We therefore expect the implied distribution to give a relatively high price, and a relatively high implied volatility, for this option as well. Again, this is exactly what we observe in Figure 20.1..  

![](images/6bf969a47e7b3126a8b4e0d1fb7608b36948164dba879e27ccb1dfbcf54e8b8c.jpg)  
Figure 20.1Volatility smile for foreign currency options ( $K=$ strike price, $S_{0}=$ current exchange rate).  

![](images/2e1bb21dd425493b97180f4e9c3411f2938d30336a598ecd1fdaffd6ae115e23.jpg)  
Figure 20.2  Implied and lognormal distribution for foreign currency options.  

# Empirical Results  

We have just shown that the volatility smile used by traders for foreign currency options implies that they consider that the lognormal distribution understates the probability of extreme movements in exchange rates. To test whether they are right, Table 20.1 examines the daily movements in 10 different exchange rates over a 10-year period between 2005 and 2015. The exchange rates are those between the U.S. dollar and the following currencies: Australian dollar, British pound, Canadian dollar, Danish krone, euro, Japanese yen, Mexican peso, New Zealand dollar, Swedish krona, and Swiss franc. The first step in the production of the table is to calculate the standard deviation of daily percentage change in each exchange rate. The next stage is to note how often the actual percentage change exceeded 1 standard deviation, 2 standard deviations, and so on. The final stage is to calculate how often this would have happened if the percentage changes had been normally distributed. (The lognormal model implies that percentage changes are almost exactly normally distributed over a one-day time period.)  

Table 20.1  Percentage of days when daily exchange rate moves are greater than $1,2,\ldots,6$ standard deviations $\mathrm{SD}=$ standard deviation of daily change).   


<html><body><table><tr><td colspan="2">Realworld</td><td>Lognormal model</td></tr><tr><td>>1 SD</td><td>23.32</td><td>31.73</td></tr><tr><td>>2 SD</td><td>4.67</td><td>4.55</td></tr><tr><td>>3 SD</td><td>1.30</td><td>0.27</td></tr><tr><td>>4 SD</td><td>0.49</td><td>0.01</td></tr><tr><td>>5 SD</td><td>0.24</td><td>0.00</td></tr><tr><td>>6 SD</td><td>0.13</td><td>0.00</td></tr></table></body></html>  

Business Snapshot 20.1 Making Money from Foreign Currency Options  

Black, Scholes, and Merton in their option pricing model assume that the underlying asset price has a lognormal distribution at future times. This is equivalent to the assumption that asset price changes over a short period of time, such as one day, are normally distributed. Suppose that most market participants are comfortable with the Black-Scholes-Merton assumptions for exchange rates. You have just done the analysis in Table 20.1 and know that the lognormal assumption is not a good one for exchange rates. What should you do?  

The answer is that you should buy deep-out-of-the-money call and put options on. a variety of different currencies and wait. These options will be relatively inexpensive and more of them will close in the money than the lognormal model predicts. The present value of your payoffs will on average be much greater than the cost of the options.  

In the mid-1980s, a few traders knew about the heavy tails of foreign exchange. probability distributions. Everyone else thought that the lognormal assumption of Black-Scholes-Merton was reasonable. The few traders who were well informed. followed the strategy we have described-- and made lots of money. By the late 1980s everyone realized that foreign currency options should be priced with a volatility smile and the trading opportunity disappeared.  

Daily changes exceed 3 standard deviations on $1.30\%$ of days. The lognormal model predicts that this should happen on only $0.27\%$ of days. Daily changes exceed 4, 5, and 6 standard deviations on $0.49\%$ $0.24\%$ , and $0.13\%$ of days, respectively. The lognormal model predicts that we should hardly ever observe this happening. The table therefore provides evidence to support the existence of heavy tails (Figure 20.2) and the volatility smile used by traders (Figure 20.1). Business Snapshot 20.1 shows how you could have made money if you had done the analysis in Table 20.1 ahead of the rest of the market.  

# Reasons for the Smile in Foreign Currency Options  

Why are exchange rates not lognormally distributed? Two of the conditions for an asset price to have a lognormal distribution are:  

1. The volatility of the asset is constant..   
2. The price of the asset changes smoothly with no jumps.  

In practice, neither of these conditions is satisfied for an exchange rate. The volatility of an exchange rate is far from constant, and exchange rates frequently exhibit jumps,. sometimes in response to the actions of central banks. It turns out that both a nonconstant volatility and jumps will have the effect of making extreme outcomes more likely.  

The impact of jumps and nonconstant volatility depends on the option maturity. As the maturity of the option is increased, the percentage impact of a nonconstant volatility on prices becomes more pronounced, but its percentage impact on implied volatility usually becomes less pronounced. The percentage impact of jumps on both prices and the implied volatility becomes less pronounced as the maturity of the option is increased.2 The result of all this is that the volatility smile becomes less pronounced as option maturity increases.  
