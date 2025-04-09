# 17.6  AMERICAN OPTIONS  

As described in Chapter 13, binomial trees can be used to value American options on indices and currencies. As in the case of American options on a non-dividend-paying stock, the parameter determining the size of up movements,. $u$ , is set equal to $e^{\sigma{\sqrt{\Delta t}}}$ where $\sigma$ is the volatility and $\Delta t$ is the length of time steps. The parameter determining. the size of down movements,. $d$ , is set equal to $1/u$ , or $e^{-\sigma{\sqrt{\Delta t}}}$ . For a non-dividendpaying stock, the probability of an up movement is.  

$$
p={\frac{a-d}{u-d}}
$$  

where $a=e^{r\Delta t}$ For options on indices and currencies, the formula for $p$ is the same, but $a$ is defined differently. In the case of options on an index,  

$$
a=e^{(r-q)\Delta t}
$$  

where $q$ is the dividend yield on the index. In the case of options on a currency,  

$$
a=e^{(r-r_{f})\Delta t}
$$  

where $r_{f}$ is the foreign risk-free rate. Example 13.1 in Section 13.11 shows how a two-step tree can be constructed to value an option on an index. Example 13.2 shows how a threestep tree can be constructed to value an option on a currency. Further examples of the use of binomial trees to value options on indices and currencies are given in Chapter 21.  

In some circumstances, it is optimal to exercise American currency and index options. prior to maturity. Thus,American currency and index options are worth more than their European counterparts. In general, call options on high-interest currencies and put. options on low-interest currencies are the most likely to be exercised early. The reason is that a high-interest currency is expected to depreciate and a low-interest currency is. expected to appreciate. Similarly, call options on indices with high-dividend yields and put options on indices with low-dividend yields are most likely to be exercised early..  

# SUMMARY  

The index options trading on exchanges are settled in cash. On exercise of an index call option contract, the holder typically receives 100 times the amount by which the index. exceeds the strike price. Similarly, on exercise of an index put option contract, the holder receives 100 times the amount by which the strike price exceeds the index. Index. options can be used for portfolio insurance. If the value of the portfolio mirrors the index, it is appropriate to buy one put option contract for each $100S_{0}$ dollars in the portfolio, where $S_{0}$ is the value of the index. If the portfolio does not mirror the index,. $\beta$ put option contracts should be purchased for each. $100S_{0}$ dollars in the portfolio,. where $\beta$ is the beta of the portfolio from the capital asset pricing model. The strike price. of the put options purchased should reflect the level of insurance required..  

Most currency options are traded in the over-the-counter market. They can be used. by corporate treasurers to hedge a foreign exchange exposure. For example, a U.S. corporate treasurer who knows that the company will be receiving sterling at a certain time in the future can hedge by buying put options that mature at that time. Similarly, a U.S. corporate treasurer who knows that the company will be paying sterling at a. certain time in the future can hedge by buying call options that mature at that time. Currency options can also be used to create a range forward contract. This is a zero-cost contract that can be used to provide downside protection while giving up some of the upside for a company with a known foreign exchange exposure..  

The Black-Scholes-Merton formula for valuing European options on a non-dividendpaying stock can be extended to cover European options on a stock paying a known dividend yield. The extension can be used to value European options on stock indices and currencies because:  

1. A stock index is analogous to a stock paying a dividend yield. The dividend yield. is the dividend yield on the stocks that make up the index..   
2. A foreign currency is analogous to a stock paying a dividend yield. The foreign risk-free interest rate plays the role of the dividend yield..  

Binomial trees can be used to value American options on stock indices and currencies.  

# FURTHER READING  

Biger, N., and J. C. Hull. "The Valuation of Currency Options, Financial Management, 12 (Spring 1983): 24-28.   
Bodie, Z. "On the Risk of Stocks in the Long Run, Financial Analysts Journal, 51, 3 (1995): 18-22.   
Garman, M. B., and S. W. Kohlhagen. "Foreign Currency Option Values,' Journal of International Money and Finance, 2 (December 1983): 231-37.   
Giddy, I. H., and G. Dufey. "Uses and Abuses of Currency Options,' Journal of Applied Corporate Finance, 8, 3 (1995): 49-57.   
Grabbe, J. O. "The Pricing of Call and Put Options on Foreign Exchange,' Journal of International Money and Finance,2 (December 1983): 239-53.   
Merton, R. C. "Theory of Rational Option Pricing,' Bell Journal of Economics and Management Science, 4 (Spring 1973): 141-83.  

# Short Concept Questions  

17.1. How does the number of options necessary to hedge a well-diversified portfolio change as the beta of the portfolio changes?   
17.2. What is a range forward contract?   
17.3. How can the dividend yield expected by the market on a stock index be estimated from futures contracts on a stock index?   
17.4. How is the Black-Scholes-Merton formula for valuing a European option on a nondividend-paying stock adjusted to value a European option on an asset providing a known dividend yield?   
17.5. "Once we know how to value options on a stock paying a dividend yield, we know how to value options on stock indices and currencies"' Explain this statement.   
17.6. A portfolio is currently worth $\$10$ million and has a beta of 1.0. An index is currently standing at 800. Explain how a put option on the index with a strike price of 700 can be used to provide portfolio insurance.  

# Practice Questions  

17.7. A stock index is currently 300, the dividend yield on the index is $3\%$ per annum, and the risk-free interest rate is $8\%$ per annum. What is a lower bound for the price of a sixmonth European call option on the index when the strike price is 290?   
17.8. A currency is currently worth $\$0.80$ and has a volatility of. $12\%$ . The domestic and foreign risk-free interest rates are $6\%$ and $8\%$ , respectively. Use a two-step binomial tree to value (a) a European four-month call option with a strike price of 0.79 and (b) an American four-month call option with the same strike price.   
17.9. Explain how corporations can use range forward contracts to hedge their foreign exchange risk when they are due to receive a certain amount of a foreign currency in the future.  

17.10. Calculate the value of a three-month at-the-money European call option on a stock index when the index is at 250, the risk-free interest rate is $10\%$ per annum, the volatility of the index is. $18\%$ per annum, and the dividend yield on the index is. $3\%$ per annum.  

17.11. Calculate the value of an eight-month European put option on a currency with a strike price of 0.50. The current exchange rate is 0.52, the volatility of the exchange rate is $12\%$ , the domestic risk-free interest rate is $4\%$ per annum, and the foreign risk-free interest rate is $8\%$ per annum.  

17.12. Show that the formula in equation (17.12) for a put option to sell one unit of currency A for currency B at strike price $K$ gives the same value as equation (17.11) for a call option to buy $K$ units of currency B for currency A at strike price. $1/K$  

17.13. A foreign currency is currently worth $\$1.50.$ The domestic and foreign risk-free interest rates are $5\%$ and $9\%$ , respectively. Calculate a lower bound for the value of a six-month. call option on the currency with a strike price of $\$1.40$ if it is (a) European and. (b) American.  

17.14. Consider a stock index currently standing at 250. The dividend yield on the index is $4\%$ per annum, and the risk-free rate is $6\%$ per annum. A three-month European call option on the index with a strike price of 245 is currently worth $\$10$ What is the value of a three-month put option on the index with a strike price of 245?  

17.15. An index currently stands at 696 and has a volatility of $30\%$ per annum. The risk-free rate of interest is $7\%$ per annum and the index provides a dividend yield of $4\%$ per annum. Calculate the value of a three-month European put with an exercise price of 700.  

17.16. Show that,if. $C$ is the price of an American call with exercise price $K$ and maturity $T$ on a stock paying a dividend yield of. $q$ , and $P$ is the price of an American put on the same. stock with the same strike price and exercise date, then  

$$
S_{0}e^{-q T}-K<C-{\cal P}<S_{0}-K e^{-r T},
$$  

where $S_{0}$ is the stock price, $r$ is the risk-free rate, and $r>0$ . (Hint: To obtain the first half of the inequality, consider possible values of:  

Portfolio $A$ : a European call option plus an amount $K$ invested at the risk-free rate Portfolio $B$ : an American put option plus $e^{-q T}$ Of stock with dividends being reinvested in the stock.  

To obtain the second half of the inequality, consider possible values of:  

Portfolio $C$ : an American call option plus an amount $K e^{-r T}$ invested at the riskfree rate   
Portfolio $D$ : a European put option plus one stock with dividends being reinvested in the stock.)  

17.17. Show that a European call option on a currency has the same price as the corresponding European put option on the currency when the forward price equals the strike price.  

17.18. Would you expect the volatility of a stock index to be greater or less than the volatility of a typical stock? Explain your answer.  

17.19. Does the cost of portfolio insurance increase or decrease as the beta of a portfolio increases? Explain your answer.  

17.20. Suppose that a portfolio is worth $\$60$ million and a stock index stands at 1,200. If the value of the portfolio mirrors the value of the index, what options should be purchased to provide protection against the value of the portfolio falling below $\$54$ million in one year's time?.   
17.21. Consider again the situation in Problem 17.20. Suppose that the portfolio has a beta of 2.0, the risk-free interest rate is. $5\%$ per annum, and the dividend yield on both the portfolio and the index is. $3\%$ per annum. What options should be purchased to provide. protection against the value of the portfolio falling below $\$54$ million in one year's time?   
17.22. An index currently stands at 1,500. European call and put options with a strike price of 1,400 and time to maturity of six months have market prices of 154.00 and 34.25, respectively. The six-month risk-free rate is. $5\%$ . What is the implied dividend yield?   
17.23. A total return index tracks the return, including dividends, on a certain portfolio. Explain how you would value (a) forward contracts and (b) European options on the index.   
17.24. What is the put-call parity relationship for European currency options?   
17.25. Prove the results in equations (17.1), (17.2), and (17.3) using the portfolios indicated.   
17.26. Can an option on the yen/euro exchange rate be created from two options, one on the. dollar/euro exchange rate, and the other on the dollar/yen exchange rate? Explain your answer.   
17.27. Suppose the Dow Jones Industrial Average is 27,o00 and the price of a two-month (European) call option on the index with a strike price of 270 is $\$5.35$ . Use the DerivaGem software to calculate the implied volatility of this option. Assume the risk-free rate is $0.25\%$ and the dividend yield is. $2\%$ . Estimate the price of a two-month put option with a 270 strike price. What is the volatility implied by the price you estimate for this option? (Note that options are on the Dow Jones index divided by 100.)   
17.28. A stock index currently stands at 300 and has a volatility of $20\%$ . The risk-free interest rate is $8\%$ and the dividend yield on the index is $3\%$ . Use a three-step binomial tree to. value a six-month put option on the index with a strike price of 300 if it is (a) European and (b) American?   
17.29. Suppose that the spot price of the Canadian dollar is U.S. $\$0.75$ and that the Canadian. dollar/U.S. dollar exchange rate has a volatility of $8\%$ per annum. The risk-free rates of interest in Canada and the United States are $4\%$ and $5\%$ per annum, respectively.. Calculate the value of a European call option to buy one Canadian dollar for U.S. $\$0.75$ in nine months. Use put-call parity to calculate the price of a European put option to sell one Canadian dollar for U.S.. $\$0.75$ in nine months. What is the price of a call option to buy U.S. $\$0.75$ with one Canadian dollar in nine months?.   
17.30. The spot price of an index is 1,000 and the risk-free rate is $4\%$ . The prices of 3-month European call and put options when the strike price is 950 are 78 and 26. Estimate (a) the dividend yield and (b) the implied volatility..   
17.31. Assume that the price of currency A expressed in terms of the price of currency B follows the process $d S=(r_{\mathrm{B}}-r_{\mathrm{A}})S d t+\sigma S d z$ , where $r_{\mathrm{A}}$ is the risk-free interest rate in currency A and $r_{\mathrm{B}}$ is the risk-free interest rate in currency B. What is the process followed by the price of currency B expressed in terms of currency A?  

17.32. In Business Snapshot 17.1, what is the cost of a guarantee that the return on the fund will not be negative over the next 10 years?.  

![](a4ed021366b8c3e9c9f5e1a9f8da747a27194e8c47c764941a71fcdd22315c56.jpg)  

# Futuresd Options and Black's Model  

The options we have considered so far provide the holder with the right to buy or sell a certain asset by a certain date for a certain price. They are sometimes termed options on spot or spot options because, when the options are exercised, the sale or purchase of the asset at the agreed-on price takes place immediately. In this chapter we move on to consider options on futures, also known as futures options. In these contracts, exercise of the option gives the holder a position in a futures contract.  

The Commodity Futures Trading Commission in the U.S. authorized the trading of options on futures on an experimental basis in 1982. Permanent trading was approved in 1987, and since then the popularity of the contract has grown very fast.  

In this chapter we consider how futures options work and the differences between. these options and spot options. We examine how futures options can be priced, explore the relative pricing of futures options and spot options, and discuss what are known as. futures-style options.  

In 1976, Fischer Black proposed a model, now known as Black's model, for valuing European options on futures.' As this chapter will show, the model has proved to be an important alternative to the Black-Scholes-Merton model for valuing a wide range of European spot options.  
