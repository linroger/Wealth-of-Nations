# 18.8 USING BLACK'S MODEL INSTEAD OFBLACK-SCHOLES-MERTON  

The results in Section 18.3 show that European futures options and European spot options are equivalent when the option contract matures at the same time as the futures contract. Specifically, equations (18.7) and (18.8) provide the price of a European option on the spot price of a asset where $F_{0}$ is the futures price of the asset for a contract maturing at the same time as the option.  

# Example 18.7  

Consider a six-month European call option on the spot price of gold, that is, an. option to buy one ounce of gold in the spot market in six months. The strike price is $\$1,200$ , the six-month futures price of gold is $\$1,240$ , the risk-free rate of interest is $5\%$ per annum, and the volatility of the futures price is. $20\%$ . The option is the same as a six-month European option on the six-month futures price. The value of the option is therefore given by equation (18.7) as  

$$
e^{-0.05\times0.5}[1,240N(d_{1})-1,200N(d_{2})]
$$  

where  

$$
d_{1}=\frac{\ln(1,240/1,200)+0.2^{2}\times0.5/2}{0.2\times\sqrt{0.5}}=0.3026
$$  

$$
d_{2}=\frac{\ln(1,240/1,200)-0.2^{2}\times0.5/2}{0.2\times\sqrt{0.5}}=0.1611
$$  

It is $\$88.37$  

Traders like to use Black's model rather than Black-Scholes-Merton to value European spot options. It has a fairly general applicability. The underlying asset can be a. consumption or investment asset and it can provide income to the holder. Often. $F_{0}$ is set equal to the forward price rather than the futures price. When interest rates are. assumed to be deterministic, forward and futures prices are equal and so this is valid.. As we will see later in the book, when interest rates are stochastic it is valid to set $F_{0}$ equal to the forward price provided that $r$ is the risk-free rate for maturity $T$  

The big advantage of Black's model is that it avoids the need to estimate the income (or convenience yield) on the underlying asset. The futures or forward price that is used in the model incorporate the market's estimate of this income.  

Equations (17.13) and (17.14) show Black's model being used to value European options on the spot value of a currency. In this case, Black's model avoids the need to estimate the foreign risk-free rate explicity because all information needed about this rate is captured by $F_{0}$ Equations (17.8) and (17.9) show Black's model being used to. value European options on the spot value of an index. In this case, dividends on the underlying portfolio of stocks do not have to be estimated explicitly because all information needed about dividends is captured by $F_{0}$  

When considering stock indices in Section 17.4, we explained that put-call parity is used to imply the forward prices for maturities for which there are actively traded options. Interpolation is then used to estimate forward prices for other maturities. The same approach can be used for a wide range of other underlying assets.  
