# 19.6 GAMMA  

The gamma $(\Gamma)$ of a portfolio of options on an underlying asset is the rate of change of the portfolio's delta with respect to the price of the underlying asset. It is the second partial derivative of the portfolio with respect to asset price:  

$$
\Gamma=\frac{\partial^{2}\Pi}{\partial S^{2}}
$$  

If gamma is small, delta changes slowly, and adjustments to keep a portfolio delta. neutral need to be made only relatively infrequently. However, if gamma is highly. negative or highly positive, delta is very sensitive to the price of the underlying asset. It is then quite risky to leave a delta-neutral portfolio unchanged for any length of time. Figure 19.7 illustrates this point. When the stock price moves from $S$ to $S^{\prime}$ , delta hedging assumes that the option price moves from $C$ to $C^{\prime}$ , when in fact it moves from $C$ to $C^{\prime\prime}$ . The difference between $C^{\prime}$ and $C^{\prime\prime}$ leads to a hedging error. The size of the error depends on the curvature of the relationship between the option price and the. stock price. Gamma measures this curvature.  

![](044304f1752b6d4dd9e57ff86c4344e37e4aec07739f848f173513a98c31f707.jpg)  
Figure 19.7 Hedging error introduced by nonlinearity.  

Suppose that $\Delta S$ is the price change of an underlying asset during a small interval of time, $\Delta t$ and $\Delta\Pi$ is the corresponding price change in the portfolio. The appendix at the end of this chapter shows that, if terms of order higher than $\Delta t$ are ignored,  

$$
\Delta\Pi=\Theta\Delta t+{\textstyle{\frac{1}{2}}}\Gamma\Delta S^{2}
$$  

for a delta-neutral portfolio, where $\Theta$ is the theta of the portfolio. Figure 19.8 shows the nature of the relationship between $\Delta\Pi$ and $\Delta S$ When gamma is positive, theta tends to be negative. The portfolio declines in value if there is no change in. $S$ , but increases in value if there is a large positive or negative change in $S$ When gamma is negative, theta tends to be positive and the reverse is true: the portfolio increases in value if there is no change in $S$ but decreases in value if there is a large positive or negative change in. $S$ As the absolute value of gamma increases, the sensitivity of the value of the portfolio to. $S$ increases.  

# Example 19.3  

Suppose that the gamma of a delta-neutral portfolio of options on an asset is 10,000. Equation (19.3) shows that, if a change of $+2$ or $^{-2}$ in the price of the asset occurs over a short period of time, there is an unexpected decrease in the value of the portfolio of approximately $0.5\times10,000\times2^{2^{-}}=\S20,000$  

# Making a Portfolio Gamma Neutral  

A position in the underlying asset has zero gamma and cannot be used to change the gamma of a portfolio. What is required is a position in an instrument such as an option that is not linearly dependent on the underlying asset.  

Suppose that a delta-neutral portfolio has a gamma equal to $\Gamma$ , and a traded option has a gamma equal to $\Gamma_{T}.$ If the number of traded options added to the portfolio is. $w_{T}$ the gamma of the portfolio is.  

$$
w_{T}\Gamma_{T}+\Gamma
$$  

Hence, the position in the traded option necessary to make the portfolio gamma neutral is $-\Gamma/\Gamma_{T}.$ Including the traded option is likely to change the delta of the portfolio, so the position in the underlying asset then has to be changed to maintain delta neutrality.  

![](545018350e3a9b110feb5f9a94294751ee3cdf0853d3e9d6943341dd24ec7945.jpg)  
Figure 19.8Relationship between $\Delta\Pi$ and $\Delta S$ in time $\Delta t$ for a delta-neutral portfolio with (a) slightly positive gamma, (b) large positive gamma, (c) slightly negative gamma, and (d) large negative gamma.  

Note that the portfolio is gamma neutral only for a short period of time. As time passes, gamma neutrality can be maintained only if the position in the traded option is adjusted so that it is always equal to $-\Gamma/\Gamma_{T}$  

Making a portfolio gamma neutral as well as delta-neutral can be regarded as a. correction for the hedging error illustrated in Figure 19.7. Delta neutrality provides protection against relatively small stock price moves between rebalancing. Gamma neutrality provides protection against larger movements in this stock price between hedge rebalancing. Suppose that a portfolio is delta neutral and has a gamma of $-3{,}000$ . The delta and gamma of a particular traded call option are 0.62 and 1.50,. respectively. The portfolio can be made gamma neutral by including in the portfolio a. long position of  

$$
\frac{3,000}{1.5}=2,000
$$  

in the call option. However, the delta of the portfolio will then change from zero to $2,000\times0.62=1,240$ Therefore 1,240 units of the underlying asset must be sold from. the portfolio to keep it delta neutral..  

# Calculation of Gamma  

For a European call or put option on a non-dividend-paying stock, the gamma given by the Black-Scholes-Merton model is.  

$$
\Gamma={\frac{N^{\prime}(d_{1})}{S_{0}\sigma{\sqrt{T}}}}
$$  

where $d_{1}$ is defined as in equation (15.20) and $N^{\prime}(x)$ is as given by equation (19.2). The gamma of a long position is always positive and varies with $S_{0}$ in the way indicated in Figure 19.9. The variation of gamma with time to maturity for out-of-the-money,. at-the-money, and in-the-money options is shown in Figure 19.10. For an at-the-money option, gamma increases as the time to maturity decreases. Short-life at-the-money. options have very high gammas, which means that the value of the option holder's position is highly sensitive to jumps in the stock price.  

# Example 19.4  

As in Example 19.1, consider a call option on a non-dividend-paying stock where the stock price is $\$49$ , the strike price is $\$50$ , the risk-free rate is $5\%$ , the time to maturity is 20 weeks $:=0.3846$ years), and the volatility is. $20\%$ . In this case, $S_{0}=49,K=50,r=0.05,\sigma=0.2,$ and $T=0.3846$  

The option's gamma is  

$$
\frac{N^{\prime}(d_{1})}{S_{0}\sigma\sqrt{T}}=0.066
$$  

When the stock price changes by $\Delta S$ , the delta of the option changes by 0.066S.  

![](0ef151b447fa5f37675228b28a939e4204fd5c760282194a2536b377ed681a58.jpg)  
Figure 19.9  Variation of gamma with stock price for an option $(K=50,r=0$ $\sigma=25\%$ $T=2$  

![](182bee1a44e810252327d178c00c4d9db52000e1e5c37a0fe1ee9f47724810fd.jpg)  
Figure 19.10 Variation of gamma with time to maturity for a stock option $(S_{0}=50$ $r=0,\sigma=25\%$  
