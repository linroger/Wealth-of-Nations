# 19.8 VEGA  

As mentioned in Section 19.3, when Greek letters are calculated the volatility of the asset is in practice usually set equal to its implied volatility. The Black-Scholes-Merton model assumes that the volatility of the asset underlying an option is constant. This means that the implied volatilities of all options on the asset are constant and equal to this assumed volatility.  

But in practice the volatility of an asset changes over time. As a result, the value of an option is liable to change because of movements in volatility as well as because of changes in the asset price and the passage of time. The vega of an option, $\nu$ , is the rate of change in its value with respect to the volatility of the underlying asset:8  

$$
{\boldsymbol{\nu}}={\frac{\partial{\boldsymbol{f}}}{\partial{\boldsymbol{\sigma}}}}
$$  

where $f$ is the option price and the volatility measure,. $\sigma$ , is usually the option's implied. volatility. When vega is highly positive or highly negative, there is a high sensitivity to changes in volatility. If the vega of an option position is close to zero, volatility changes have very little effect on the value of the position..  

A position in the underlying asset has zero vega. Vega cannot therefore be changed by taking a position in the underlying asset. In this respect, vega is like gamma.. A complication is that different options in a portfolio are liable to have different implied volatilities. If all implied volatilities are assumed to change by the same amount during any short period of time, vega can be treated like gamma and the vega risk in a. portfolio of options can be hedged by taking a position in a single option. If $\nu$ is the vega of a portfolio and $\nu_{T}$ is the vega of a traded option, a position of $-\mathcal{V}/\mathcal{V}_{T}$ in the traded option makes the portfolio instantaneously vega neutral. Unfortunately, a. portfolio that is gamma neutral will not in general be vega neutral, and vice versa. If a hedger requires a portfolio to be both gamma and vega neutral, at least two traded options dependent on the underlying asset must be used.  

# Example 19.5  

Consider a portfolio that is delta neutral, with a gamma of $-5{,}000$ and a vega (measuring sensitivity to implied volatility) of $-8{,}000$ . The options shown in the. following table can be traded. The portfolio can be made vega neutral by including a long position in 4,000 of Option 1. This would increase delta to 2,400 and require that 2,400 units of the asset be sold to maintain delta neutrality. The gamma of the portfolio would change from. $-5{,}000$ to $-3{,}000$  

<html><body><table><tr><td></td><td>Delta</td><td>Gamma</td><td>Vega</td></tr><tr><td>Portfolio</td><td>0</td><td>-5000</td><td>-8000</td></tr><tr><td>Option 1</td><td>0.6</td><td>0.5</td><td>2.0</td></tr><tr><td>Option 2</td><td>0.5</td><td>0.8</td><td>1.2</td></tr></table></body></html>  

To make the portfolio gamma and vega neutral, both Option 1 and Option 2 can be used. If $w_{1}$ and $w_{2}$ are the quantities of Option 1 and Option 2 that are.  

added to the portfolio, we require that  

$$
-5,000+0.5w_{1}+0.8w_{2}=0
$$  

and  

$$
-8,000+2.0w_{1}+1.2w_{2}=0
$$  

The solution to these equations is. $w_{1}=400$ $w_{2}=6\mathrm{,000}$ The portfolio can there-. fore be made gamma and vega neutral by including 400 of Option 1 and 6,000 of Option 2. The delta of the portfolio, after the addition of the positions in the two traded options, is $400\times0.6+6,000\times0.5=3,240.$ Hence, 3,240 units of the asset would have to be sold to maintain delta neutrality.  

Hedging in the way indicated in Example 19.5 assumes that the implied volatilities of all. options in a portfolio will change by the same amount during a short period of time. In practice, this is not necessarily true and a trader's hedging problem is more complex. As we will see in the next chapter, for any given underlying asset a trader monitors a. "volatility surface" that describes the implied volatilities of options with different strike. prices and times to maturity. The trader's total vega risk for a portfolio is related to the different ways in which the volatility surface can change.  

For a European call or put option on a non-dividend-paying stock, vega given by the Black-Scholes-Merton model is  

$$
\mathcal{V}=S_{0}\sqrt{T}N^{\prime}(d_{1})
$$  

where $d_{1}$ is defined as in equation (15.20). The formula for $N^{\prime}(x)$ is given in equation (19.2). The vega of a long position in a European or American option is always positive. The general way in which vega varies with $S_{0}$ is shown in Figure 19.11.  

![](6af8380c68ecfc00a855b4e3b0a7824a4f38a48c0434329f07ca2b6bfc95a0e2.jpg)  
Figure 19.11 Variation of vega with stock price for an option $(K=50,r=0$ $\sigma=25\%$ $T=2$  

# Example 19.6  

As in Example 19.1, consider a call option on a non-dividend-paying stock where the stock price is $\$49$ , the strike price is. $\$50$ , the risk-free rate is $5\%$ , the time to maturity is 20 weeks $(=0.3846$ years), and the implied volatility is. $20\%$ . In this case, $S_{0}=49,K=50,r=0.05,\sigma=0.2$ and $T=0.3846$  

The option's vega is  

$$
S_{0}\sqrt{T}N^{\prime}(d_{1})=12.1
$$  

Thus a $1\%$ (0.01) increase in the implied volatility from $20\%$ to $21\%$ ) increases the value of the option by approximately $0.01\times12.1=0.121$  

Calculating vega from the Black-Scholes-Merton model and its extensions may seem. strange because one of the assumptions underlying the model is that volatility is constant. It would be theoretically more correct to calculate vega from a model in which volatility is assumed to be stochastic.? However, traders prefer the simpler approach of. measuring vega in terms of potential movements in the Black-Scholes-Merton implied volatility.  

Gamma neutrality protects against large changes in the price of the underlying asset between hedge rebalancing. Vega neutrality protects against changes in volatility. As. might be expected, whether it is best to use an available traded option for vega or gamma hedging depends on the time between hedge rebalancing and the volatility of. the volatility.10  

When volatilities change, the implied volatilities of short-dated options tend to change. by more than the implied volatilities of long-dated options. The vega of a portfolio is therefore often calculated by changing the volatilities of long-dated options by less than. that of short-dated options. One way of doing this is discussed in Section 23.6..  
