# 19.5 THETA  

The theta (O) of a portfolio of options is the rate of change of the value of the portfolio with respect to the passage of time with all else remaining the same. Theta is sometimes referred to as the time decay of the portfolio. For a European call option on a nondividend-paying stock, it can be shown from the Black-Scholes-Merton formula (see Problem 15.25) that  

$$
\Theta(\mathrm{call})=-{\frac{S_{0}N^{\prime}(d_{1})\sigma}{2\sqrt T}}-r K e^{-r T}N(d_{2})
$$  

where $d_{1}$ and $d_{2}$ are defined as in equation (15.20) and  

$$
N^{\prime}(x)={\frac{1}{\sqrt{2\pi}}}e^{-x^{2}/2}
$$  

is the probability density function for a standard normal distribution.  

For a European put option on the stock,  

$$
\Theta(\mathrm{put})=-\frac{S_{0}N^{\prime}(d_{1})\sigma}{2\sqrt{T}}+r K e^{-r T}N(-d_{2})
$$  

Because $N(-d_{2})=1-N(d_{2})$ , the theta of a put exceeds the theta of the corresponding call by $r K e^{-r T}$  

In these formulas, time is measured in years. Usually, when theta is quoted, time is measured in days, so that theta is the change in the portfolio value when 1 day passes with all else remaining the same. We can measure theta either "per calendar day" or. "per trading day." To obtain the theta per calendar day, the formula for theta must be divided by 365; to obtain theta per trading day, it must be divided by 252. (DerivaGem. measures theta per calendar day.)  

# Example 19.2  

As in Example 19.1, consider a call option on a non-dividend-paying stock where the stock price is $\$49$ , the strike price is $\$50$ , the risk-free rate is $5\%$ , the time to maturity is 20 weeks $(=0.3846$ years), and the volatility is. $20\%$ . In this case, $S_{0}=49,K=50,r=0.05,\sigma=0.2,$ and $T=0.3846$  

The option's theta is  

$$
-\frac{S_{0}N^{\prime}(d_{1})\sigma}{2\sqrt{T}}-r K e^{-r T}N(d_{2})=-4.31
$$  

The theta is $-4.31/365=-0.0118$ per calendar day, or $-4.31/252=-0.0171$ per trading day.  

Theta is usually negative for an option.' This is because, as time passes with all else. remaining the same, the option tends to become less valuable. The variation of O with stock price for a call option on a stock is shown in Figure 19.5. When the stock price is very low, theta is close to zero. For an at-the-money call option, theta is large and negative. As the stock price becomes larger, theta tends to. $-\boldsymbol{r}K\boldsymbol{e}^{-{r T}}$ (In our example, $r=0.$ ) Figure 19.6 shows typical patterns for the variation of O with the time to. maturity for in-the-money, at-the-money, and out-of-the-money call options..  

![](c358cd5f6ddabb09428a2ebdd72bfbfbfdd7611188987c2c3bb069466b374b3d.jpg)  
Figure 19.5 Variation of theta of a European call option with stock price $(K=50$ $r=0$ $\sigma=0.25$ $T=2$  

![](4d871b64e63a20c762953799336320b6ec747f42aea8b5cc8e287ee74f1aad61.jpg)  
Figure 19.6 Typical patterns for variation of theta of a European call option with time to maturity $(S_{0}=50,K=50,r=0,\sigma=25\%)$  

Theta is not the same type of hedge parameter as delta. There is uncertainty about the future stock price, but there is no uncertainty about the passage of time. It makes sense to hedge against changes in the price of the underlying asset, but it does not make any sense to hedge against the passage of time. In spite of this, many traders regard theta as a useful descriptive statistic for a portfolio. This is because, as we shall see later, in a delta-neutral portfolio theta is a proxy for gamma.  
