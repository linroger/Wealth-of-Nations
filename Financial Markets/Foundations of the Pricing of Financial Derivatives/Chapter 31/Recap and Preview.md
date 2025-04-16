---
tags:
  - '#black_scholes_merton_model'
  - '#currency_options'
  - '#exercise_price'
  - '#foreign_currency_options'
  - '#implied_volatility'
  - '#isomorphism'
  - '#option_pricing'
  - '#volatility_smile'
---
# 31.7 RECAP AND PREVIEW

The entire notion of implied volatility and the existence of the volatility smile are results. of using a model that does not capture every factor that affects the prices of options. Practitioners and academics largely accept the limitations of the model and consider the smile a means of forcing the model to reveal information it is not designed to reveal. As flawed as the model may be, the advantages of the Black-Scholes-Merton model and its attendant defects may outweigh the disadvantages of other more complex models.

In the final chapter, we look at foreign currency options. There are, of course, options. on a wide range of underlyings, of which foreign currency is just one. Foreign currency,. however, is a very different type of underlying in that it can be viewed from the perspective of either one currency or the other. Thus, there are two mirror-image underlyings..

# QUESTIONS AND PROBLEMS

1 As the financial crisis unfolded, the implied volatilities rose as illustrated in the. following two figures. Note that on June 30, 2008, the put implied volatilities were. always above the call implied volatilities. On September 30, 2008, the put implied volatilities were always below the call implied volatilities. Based solely on these patterns, what does this imply regarding the exercise price such that the call and put. prices are the same?

![](images/f9e37424b211837aca967473dffefb56e6894ff1eae7b91ad673cb787e307685.jpg)

![](images/cd41edd381ed406c928a087b4c2ed4b7ed1942e0a84f2410dfcb05c15e4a3740.jpg)
Call and Put Option Implied Volatility

2 "Within the Black-Scholes-Merton framework, any option on the same underlying should be a perfect substitute for any other option." Demonstrate this result by designing a perfect substitute for one call option with another call option. Identify and explain four reasons that have been offered for the observed implied volatility smile. Explain how practitioners use the implied volatility smile. "One measure of the internal consistency of an option pricing model is deviations from the average implied volatility for options with the same maturity." Evaluate and. explain whether this statement is true or false.

# NOTES

1. There are several technical issues in the VIX calculations that do not materially change VIX's interpretation.
2. A great source for various algorithms, such as solving for embedded parameters, can be found at www.numerical.recipes.
3. The choice of 0.001 is arbitrary..
4. The classic papers on the smile are Derman and Kani (1994), Dupire (1994), and Rubinstein (1994).
5. In some cases, the smile is illustrated in a three-dimensional graph in which the third dimension is the time to expiration. The volatilities could also differ by time to expiration, giving rise to the notion of a term structure of volatilities. When the implied volatilities are illustrated with exercise price along one axis and time to expiration along the other, the relationship is known as the volatility surface.
6. In Chapter 10, we documented the important role of dividends for SPY holding period returns.
7. The software used to generate these graphs linearly interpolates between observations. Thus the exercise value does not break exactly at 100 as it should..
8. Given an exercise price of $X$ , time to expiration of $\tau$ , and volatility of $\sigma$ , the formulas for $d_{1}$ and dj = In(S/X+c;+o2/2) $d_{2}$ are \* $d_{2}=d_{1}-\sigma\sqrt{\tau}$
9. If the two options had either the same time to expiration or the same exercise price, the formula. for the holdings would simplify a little..
10. As, for example, the binomial analog and the Black-Scholes-Merton model expressed as a dis counted expected future value under risk neutrality.
11. See, for example, Renault and Touzi (1996).
12. See, for example, Andersen and Andreasen (2000).
13. For example, one strong assumption is that the risk arising from stochastic volatility is non-priced risk. That is, the risk associated with uncertain volatility is a risk that does not concern investors. They are either neutral toward that risk or the risk is uncorrelated with their. other holdings, meaning that the risk is diversifiable. Once these assumptions are invoked, the financial economics is lost and what remains is simply an exercise in computational finance.
14. Perhaps if these reasons were found, the mathematicians would be out of work.
15. See Chance, Hanson, Li, and Muthuswamy (2017). They estimate that a minimum of $16\%$ of the smile can be explained by these purely artificial effects..
16. Other parameters required include the risk-free rate of 9 basis points and dividend yield of $3.12\%$

# Pricing Foreign Currency Options

ne of the most popular option underlyings is foreign currency. The right to buy or sell investors, and speculators. Yet, options on foreign currencies can be a bit more difficult to understand than options on stocks, bonds, and commodities. The reason primarily lies in the fact that every currency contract involves not one but two currencies. Options on stocks, bonds, and commodities, by contrast, do not involve more than one currency. They do, however, implicitly involve more than one asset. For example, an option to buy a stock is an option to exchange a currency for the stock. From the opposite perspective, however,. it is clearly an option to exchange stock for the currency. We may speak of a share of stock as costing 50 but we could just as easily say that the cost of 1.0 is 0.02 shares of stock. That is, one could theoretically exchange 0.02 shares of stock and receive 1.0. Although the notion of exchanging stock for money is a valid economic concept and explains precisely the same idea as if we described the transaction as exchanging money for stock, it is not. the form we typically use in commerce. But in the currency world, things are just a bit. different.

Hence, exchanging dollars for euros is the mirror image of exchanging euros for dollars. Likewise, exchanging dollars for stock is the mirror image of exchanging stock for dollars. Because we never describe the stock transaction as the latter, we may have trouble understanding the currency transaction from that point of view.

In the world of currency trading, however, it is necessary to understand the transaction from either point of view. In particular, foreign currency option transactions have an important characteristic that sheds light on some interesting issues in option valuation. That characteristic is that a foreign currency call can be viewed as a foreign currency put. from the mirror image perspective. We describe this idea as the concept of isomorphism,. the notion that two things have essentially the same form. This point would also hold for calls on stocks because they can be viewed as puts on cash, but because we virtually never view a stock sale as the purchase of money paid for by tendering stock, we almost never use this concept elsewhere in financial markets..

In foreign currency transactions, we shall refer to the two currencies as the base currency and the quoted currency. The base currency is just the underlying currency. For example, a call option quoted in dollars in which the underlying is euros has the dollar as the quoted currency and the euro as the base currency.1 In addition, the instruments we examine are sometimes called foreign currency options, currency options, and foreign exchange options, so be prepared for alternative nomenclature.
