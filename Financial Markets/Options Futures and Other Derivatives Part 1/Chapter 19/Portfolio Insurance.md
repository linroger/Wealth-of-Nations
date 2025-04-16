---
tags:
  - '#delta_hedging'
  - '#index_futures'
  - '#market_volatility'
  - '#option_pricing'
  - '#portfolio_insurance'
  - '#portfolio_management'
  - '#risk_management'
  - '#synthetic_options'
---
# 19.13 PORTFOLIO INSURANCE  

A portfolio manager is often interested in acquiring a put option on his or her portfolio. This provides protection against market declines while preserving the potential for a gain if the market does well. One approach (discussed in Section 17.1) is to buy put options on a market index such as the S&P 500. An alternative is to create the options synthetically.  

Creating an option synthetically involves maintaining a position in the underlying asset (or futures on the underlying asset) so that the delta of the position is equal to the delta of the required option. The position necessary to create an option synthetically is the reverse of that necessary to hedge it. This is because the procedure for hedging an option involves the creation of an equal and opposite option synthetically.  

There are two reasons why it may be more attractive for the portfolio manager to. create the required put option synthetically than to buy it in the market. First, option markets do not always have the liquidity to absorb the trades required by managers of large funds. Second, fund managers often require strike prices and exercise dates that are different from those available in exchange-traded options markets..  

The synthetic option can be created from trading the portfolio or from trading in index futures contracts. We first examine the creation of a put option by trading the portfolio. From Table 19.6, the delta of a European put on the portfolio is  

$$
\Delta=e^{-q T}[N(d_{1})-1]
$$  

where, with our usual notation,  

$$
d_{1}=\frac{\ln(S_{0}/K)+(r-q+\sigma^{2}/2)T}{\sigma\sqrt{T}}
$$  

The other variables are defined as usual: $S_{0}$ is the value of the portfolio, $K$ is the strike. price, $r$ is the risk-free rate,. $q$ is the dividend yield on the portfolio,. $\sigma$ is the volatility of. the portfolio, and. $T$ is the life of the option. The volatility of the portfolio can usually be assumed to be its beta times the volatility of a well-diversified market index.  

To create the put option synthetically, the fund manager should ensure that at any given time a proportion  

$$
e^{-q T}[1-N(d_{1})]
$$  

of the stocks in the original portfolio has been sold and the proceeds invested in riskless assets. As the value of the original portfolio declines, the delta of the put given by equation (19.8) becomes more negative and the proportion of the original portfolio sold must be increased. As the value of the original portfolio increases, the delta of the put becomes less negative and the proportion of the original portfolio sold must be decreased (i.e., some of the original portfolio must be repurchased).  

Using this strategy to create portfolio insurance means that at any given time funds are divided between the stock portfolio on which insurance is required and riskless assets. As the value of the stock portfolio increases, riskless assets are sold and the position in the stock portfolio is increased. As the value of the stock portfolio declines, the position in the stock portfolio is decreased and riskless assets are purchased. The cost of the insurance arises from the fact that the portfolio manager is always selling after a decline in the market and buying after a rise in the market.  

# Example 19.9  

A portfolio is worth. $\$90$ million. To protect against market downturns the managers of the portfolio require a 6-month European put option on the portfolio with a strike price of. $\$87$ million. The risk-free rate is. $9\%$ per annum, the dividend yield is $3\%$ per annum, and the volatility of the portfolio is estimated as. $25\%$ per annum.A stock index stands at 900. The portfolio is considered to mimic the index fairly closely. One alternative, discussed in Section 17.1, is to buy 1,000 put option contracts on the index with a strike price of 870. Another alternative is to create the required option synthetically. In this case, $S_{0}=90$ million, $K=87$ million, $r=0.09,q=0.03,\upsigma=0.25$ , and $T=0.5$ , so that  

$$
d_{1}={\frac{\ln(90/87)+(0.09-0.03+0.25^{2}/2)0.5}{0.25{\sqrt{0.5}}}}=0.4499
$$  

and the delta of the required option is  

$$
e^{-q T}\left[N(d_{1})-1\right]=-0.3215
$$  

This shows that. $32.15\%$ of the portfolio should be sold initially and invested in risk-free assets to match the delta of the required option. The amount of the portfolio sold must be monitored frequently. For example, if the value of the original portfolio reduces to. $\$88$ million after 1 day, the delta of the required option changes to 0.3679 and a further $4.64\%$ of the original portfolio should be. sold and invested in risk-free assets. If the value of the portfolio increases to $\$92$ million, the delta of the required option changes to $-0.2787$ and $4.28\%$ of the original portfolio should be repurchased.  

# Use of Index Futures  

Using index futures to create options synthetically can be preferable to using the.   
underlying stocks because the transaction costs associated with trades in index futures are generally lower than those associated with the corresponding trades in the under-.   
lying stocks. The dollar amount of the futures contracts shorted as a proportion of the.   
value of the portfolio should from equations (19.6) and (19.8) be.  

$$
e^{-q T}e^{-(r-q)T^{*}}\left[1-N(d_{1})\right]=e^{q(T^{*}-T)}e^{-r T^{*}}\left[1-N(d_{1})\right]
$$  

where $T^{*}$ is the maturity of the futures contract. If the portfolio is worth $A_{1}$ times the index and each index futures contract is on. $A_{2}$ times the index, the number of futures. contracts shorted at any given time should be.  

$$
e^{q(T^{*}-T)}e^{-r T^{*}}\left[1-N(d_{1})\right]A_{1}/A_{2}
$$  

# Example 19.10  

Suppose in Example 19.9 futures contracts on the index maturing in 9 months are used to create the option synthetically. In this case initially. $T=0.5$ $T^{*}=0.75$ $A_{1}=100{,}000$ , and $d_{1}=0.4499$ . Each index futures contract is on 250 times the index, so that $A_{2}=250.$ The number of futures contracts shorted should be  

$$
e^{q(T^{*}-T)}e^{-r T^{*}}\left[1-N(d_{1})\right]A_{1}/A_{2}=122.96
$$  

or 123, rounding to the nearest whole number. As time passes and the index changes, the position in futures contracts must be adjusted.  

This analysis assumes that the portfolio mirrors the index. When this is not the case, it is necessary to (a) calculate the portfolio's beta, (b) find the position in options on the index that gives the required protection, and (c) choose a position in index futures to create the options synthetically. As discussed in Section 17.1, the strike price for the options should be the expected level of the market index when the portfolio reaches its insured value. The number of options required is beta times the number that would be required if the portfolio had a beta of 1.0.  

# Impact on Volatility  

We discussed in Chapter 15 the issue of whether volatility is caused solely by the arrival of new information or whether trading itself generates volatility. Portfolio insurance. strategies such as those just described have the potential to increase volatility. When the. market declines, they cause portfolio managers either to sell stock or to sell index futures contracts. Either action may accentuate the decline (see Business Snapshot 19.2). The sale of stock is liable to drive down the market index further in a direct way. The. sale of index futures contracts is liable to drive down futures prices. This creates selling pressure on stocks via the mechanism of index arbitrage (see Chapter 5), so that the market index is liable to be driven down in this case as well. Similarly, when the market rises, the portfolio insurance strategies cause portfolio managers either to buy stock or. to buy futures contracts. This may accentuate the rise.  

In addition to formal portfolio trading strategies, we can speculate that many investors. consciously or subconsciously follow portfolio insurance rules of their own. For example, an investor may choose to sell when the market is falling to limit the downside risk...  

Whether portfolio insurance trading strategies (formal or informal) affect volatility. depends on how easily the market can absorb the trades that are generated by portfolio. insurance. If portfolio insurance trades are a very small fraction of all trades, there is likely to be no effect. But if portfolio insurance becomes very popular, it is liable to. have a destabilizing effect on the market, as it did in 1987..  
