---
tags:
  - '#crashophobia'
  - '#equity_options'
  - '#implied_volatility'
  - '#lognormal_distribution'
  - '#negative_correlation_equity_prices_volatility'
  - '#stock_market_crash_1987'
  - '#volatility_skew'
  - '#volatility_smile'
---
# 20.3 VOLATILITY SMILE FOR EQUITY OPTIONS  

Prior to the crash of 1987, there was no marked volatility smile for equity options. Since 1987, the volatility smile used by traders to price equity options (both on individual stocks and on stock indices) has tended to look like that in Figure 20.3. This is sometimes referred to as a volatility skew. The volatility decreases as the strike price increases. The volatility used to price a low-strike-price option (i.e., a deep-out-of-the-money put or a deep-in-the-money call) is significantly higher than that used to price a high-strike-price option (i.e., a deep-in-the-money put or a deep-out-of-the-money call).  

The volatility smile for equity options corresponds to the implied probability distribution given by the solid line in Figure 20.4. A lognormal distribution with the same mean and standard deviation as the implied distribution is shown by the dotted line. It can be seen that the implied distribution has a heavier left tail and a less heavy right tail than the lognormal distribution.  

To see that Figures 20.3 and 20.4 are consistent with each other, we proceed as for Figures 20.1 and 20.2 and consider options that are deep out of the money. From Figure 20.4, a deep-out-of-the-money call with a strike price of $K_{2}$ $(K_{2}/S_{0}$ well above 1.0) has a lower price when the implied distribution is used than when the lognormal distribution is used. This is because the option pays off only if the stock price proves to be above $K_{2}$ , and the probability of this is lower for the implied probability. distribution than for the lognormal distribution. Therefore, we expect the implied. distribution to give a relatively low price for the option. A relatively low price leads to a relatively low implied volatility--and this is exactly what we observe in Figure 20.3 for the option. Consider next a deep-out-of-the-money put option with a strike price. of $K_{1}$ . This option pays off only if the stock price proves to be below $K_{1}$ $K_{1}/S_{0}$ well below 1.0). Figure 20.4 shows that the probability of this is higher for the implied probability distribution than for the lognormal distribution. We therefore expect the implied distribution to give a relatively high price, and a relatively high implied volatility, for this option. Again, this is exactly what we observe in Figure 20.3..  

![](207d941ffd659e7778381c06b71ec20f2410cd2975c5aacf3e5857319b625e36.jpg)  
Figure 20.3 Volatility smile for equities ( $K=$ strike price,. $S_{0}=$ current equity price)..  

![](bcf4ceba1967d814e5c773efe047fc796a22f2ce4c5968268f2b98d4c7317b77.jpg)  
Figure 20.4  Implied distribution and lognormal distribution for equity options.  

# The Reason for the Smile in Equity Options  

There is a negative correlation between equity prices and volatility.3 As prices move down (up), volatilities tend to move up (down). There are several possible reasons for this. One concerns leverage. As equity prices move down (up), leverage increases (decreases) and as a result volatility increases (decreases). Another is referred to as the volatility feedback effect. As volatility increases (decreases) because of external factors, investors require a higher (lower) return and as a result the stock price declines (increases). A further explanation is crashophobia (see Business Snapshot 20.2).  

Whatever the reason for the negative correlation, it means that stock price declines are accompanied by increases in volatility, making even greater declines possible. Stock price increases are accompanied by decreases in volatility, making further stock price increases less likely. This explains the heavy left tail and thin right tail of the implied distribution in Figure 20.4.  

# Business Snapshot 20.2 Crashophobia  

It is interesting that the pattern in Figure 20.3 for equities has existed only since the stock market crash of October 1987. Prior to October 1987, implied volatilities were much less dependent on strike price. This has led Mark Rubinstein to suggest that one reason for the equity volatility smile may be "crashophobia." Traders are concerned about the possibility of another crash similar to October 1987, and they price options accordingly.  

There is some empirical support for this explanation. Declines in the S&P 500 tend to be accompanied by a steepening of the volatility skew. When the S&P increases, the skew tends to become less steep.  
