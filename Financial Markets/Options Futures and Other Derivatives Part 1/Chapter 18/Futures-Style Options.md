# 18.11 FUTURES-STYLE OPTIONS  

Some exchanges, particularly those in Europe, trade what are termed futures-style options. These are futures contracts on the payoff from an option. Normally a trader who buys (sells) an option, whether on the spot price of an asset or on the futures price of an asset, pays (receives) cash up front. By contrast, traders who buy or sell a futuresstyle option post margin in the same way that they do on a regular futures contract (see Chapter 2). The contract is settled daily as with any other futures contract and the final settlement price is the payoff from the option. Just as a futures contract is a bet on what the future price of an asset will be, a futures-style option is a bet on what the payoff. from an option will be. If interest rates are constant, the futures price in a futures-style. option is the same as the forward price in a forward contract on the option payoff. Our analysis of forward contracts in Chapter 5 shows that this is the current option price. compounded forward at the risk-free rate.  

Black's model in equations (18.7) and (18.8) gives the current European option price. The futures price in a futures-style call option is therefore  

$$
F_{0}N(d_{1})\mathrel{-}K N(d_{2})
$$  

and the futures price in a futures-style put option is  

$$
K N(-d_{2})\:-\:F_{0}N(-d_{1})
$$  

where $d_{1}$ and $d_{2}$ are as defined in equations (18.7) and (18.8). These formulas do not depend on the level of interest rates. They are correct for a futures-style option on a futures contract and a futures-style option on the spot value of an asset. In the first case, $F_{0}$ is the current futures price for the contract underlying the option; in the second case, it is the current futures price for a futures contract on the underlying asset maturing at the same time as the option.  

The put-call parity relationship for a futures-style options is  

$$
p+F_{0}=c+K
$$  

An American futures-style option can be exercised early, in which case there is an immediate final settlement at the option's intrinsic value. But as it turns out, it is never.   
optimal to exercise an American futures-style option early because the futures price of.   
the option is always greater than the intrinsic value. This type of American futures-style.   
option can therefore be treated as though it is European..  

# SUMMARY  

Futures options require delivery of the underlying futures contract on exercise. When a call is exercised, the holder acquires a long futures position plus a cash amount equal to the excess of the futures price over the strike price. Similarly, when a put is exercised the holder acquires a short position plus a cash amount equal to the excess of the strike price over the futures price. The futures contract that is delivered usually expires slightly later than the option..  

A futures price behaves in the same way as a stock that provides a dividend yield equal to the risk-free rate, $r.$ This means that the results produced in Chapter 17 for options on a stock paying a dividend yield apply to futures options if we replace the stock price by the futures price and set the dividend yield equal to the risk-free interest rate. Pricing formulas for European futures options were first produced by Fischer Black in 1976. They assume that the futures price is lognormally distributed at the option's expiration.  

If the expiration dates for the option and futures contracts are the same, a European futures option is worth exactly the same as the corresponding European spot option. This result is often used to value European spot options. The result is not true for American options. If the futures market is normal, an American futures call is worth more than the corresponding American spot call option, while an American futures put is worth less than the corresponding American spot put option. If the futures market is inverted, the reverse is true.  

# FURTHER READING  

Black, F. "The Pricing of Commodity Contracts,' Journal of Financial Economics, 3 (1976): 167-79.  

# Short Concept Questions  

18.1. Explain the difference between a call option on yen and a call option on yen futures.   
18.2. Why are options on bond futures more actively traded than options on bonds?   
18.3. "A futures price is like a stock paying a dividend yield." What is the dividend yield?   
18.4. What is Black's formula for the price of (a) a European call option on futures and (b) a European put option on futures?   
18.5. How does the put-call parity formula for a futures option differ from put-call parity for an option on a non-dividend-paying stock?   
18.6. What is the difference between a futures option and a futures-style option?  

# Practice Questions  

18.7. A futures price is currently 50. At the end of six months it will be either 56 or 46. The riskfree interest rate is $6\%$ per annum. What is the value of a six-month European call option. on the futures with a strike price of 50?.   
18.8. Consider an American futures call option where the futures contract and the option contract expire at the same time. Under what circumstances is the futures option worth more than the corresponding American option on the underlying asset?.  

18.9. Calculate the value of a five-month European futures put option when the futures price is $\$19$ , the strike price is $\$20$ , the risk-free interest rate is $12\%$ per annum, and the volatility of the futures price is $20\%$ per annum.  

18.10. Suppose you buy a put option contract on October gold futures with a strike price of $\$1,400$ per ounce. Each contract is for the delivery of 100 ounces. What happens if you. exercise when the October futures price is $\$1,380?$   
18.11. Suppose you sell a call option contract on April live cattle futures with a strike price of 130 cents per pound. Each contract is for the delivery of 40,000 pounds. What happens if the contract is exercised when the futures price is 135 cents?   
18.12. Consider a two-month futures call option with a strike price of 40 when the risk-free interest rate is $10\%$ per annum. The current futures price is 47. What is a lower bound. for the value of the futures option if it is (a) European and (b) American?   
18.13. Consider a four-month futures put option with a strike price of 50 when the risk-free. interest rate is $10\%$ per annum. The current futures price is 47. What is a lower bound for the value of the futures option if it is (a) European and (b) American?   
18.14. A futures price is currently 60 and its volatility is $30\%$ . The risk-free interest rate is $8\%$ per annum. Use a two-step binomial tree to calculate the value of a six-month European call option on the futures with a strike price of 60. If the call were American, would it ever be worth exercising it early?   
18.15. In Problem 18.14, what does the binomial tree give for the value of a six-month European put option on futures with a strike price of 60? If the put were American, would it ever be worth exercising it early? Verify that the call prices calculated in Problem 18.14 and the put prices calculated here satisfy put-call parity relationships.   
18.16. A futures price is currently 25, its volatility is. $30\%$ per annum, and the risk-free interest. rate is $10\%$ per annum. What is the value of a nine-month European call on the futures with a strike price of 26?   
18.17. A futures price is currently 70, its volatility is $20\%$ per annum, and the risk-free interest rate is $6\%$ per annum. What is the value of a five-month European put on the futures with a strike price of 65?   
18.18. Suppose that a one-year futures price is currently 35. A one-year European call option and a one-year European put option on the futures with a strike price of 34 are both priced at 2 in the market. The risk-free interest rate is $10\%$ per annum. Identify an arbitrage opportunity.   
18.19. "The price of an at-the-money European futures call option always equals the price of a similar at-the-money European futures put option.' Explain why this statement is true.   
18.20. Suppose that a futures price is currently 30. The risk-free interest rate is $5\%$ per annum. A three-month American futures call option with a strike price of 28 is worth 4. Calculate bounds for the price of a three-month American futures put option with a strike price of 28.   
18.21. Show that, if $C$ is the price of an American call option on a futures contract when the strike price is $K$ and the maturity is $T$ , and $P$ is the price of an American put on the same. futures contract with the same strike price and exercise date, then $F_{0}e^{-r T}-K<C-{\cal P}<F_{0}-K e^{-r T}$  

where $F_{0}$ is the futures price and $r$ is the risk-free rate. Assume that $r>0$ and that there is no difference between forward and futures contracts. (Hint: Use an analogous approach to that indicated for Problem 17.16.)  

18.22. Calculate the price of a three-month European call option on the spot value of silver. The three-month futures price is $\$12$ , the strike price is $\$13$ , the risk-free rate is $4\%$ and the volatility of the price of silver is $25\%$  

18.23. A corporation knows that in three months it will have. $\$5$ million to invest for 90 days at LIBOR minus 50 basis points and wishes to ensure that the rate obtained will be at least $6.5\%$ . What position in exchange-traded options should it take to hedge?.  

18.24. A futures price is currently 40. It is known that at the end of three months the price will be either 35 or 45. What is the value of a three-month European call option on the futures with a strike price of 42 if the risk-free interest rate is $7\%$ per annum?  

18.25. The futures price of an asset is currently 78 and the risk-free rate is $3\%$ . A six-month put on the futures with a strike price of 80 is currently worth 6.5. What is the value of a sixmonth call on the futures with a strike price of 80 if both the put and call are European? What is the range of possible values of the six-month call with a strike price of 80 if both put and call are American?  

18.26. Use a three-step tree to value an American futures put option when the futures price is 50, the life of the option is 9 months, the strike price is 50, the risk-free rate is $3\%$ , and the volatility is $25\%$  

18.27. It is February 4. July call options on corn futures with strike prices of 260, 270, 280, 290, and 300 cost 26.75, 21.25, 17.25, 14.00, and 11.375, respectively. July put options with these strike prices cost 8.50, 13.50, 19.00, 25.625, and 32.625, respectively. The options. mature on June 19, the current July corn futures price is 278.25, and the risk-free interest rate is $1.1\%$ . Calculate implied volatilities for the options using DerivaGem. Comment. on the results you get.  

18.28. Calculate the implied volatility of soybean futures prices from the following information concerning a European put on soybean futures:  

<html><body><table><tr><td>Current futures price</td><td>525</td></tr><tr><td>Exercise price</td><td>525</td></tr><tr><td>Risk-freerate</td><td>6% per annum</td></tr><tr><td>Time to maturity</td><td>5months</td></tr><tr><td>Putprice</td><td>20</td></tr></table></body></html>  

18.29. Calculate the price of a six-month European put option on the spot value of an index. The six-month forward price of the index is 1,400, the strike price is 1,450, the risk-free rate is $5\%$ , and the volatility of the index is $15\%$  

![](images/81c73da156d1a7324f2f08378668822f2c7393f5f672fcf87294425f3d48aa48.jpg)  

# The Greek Letters  

A financial institution that sells an option to a client in the over-the-counter markets is. faced with the problem of managing its risk. If the option happens to be the same as one. that is traded actively on an exchange or in the OTC market, the financial institution can neutralize its exposure by buying the same option as it has sold. But when the option has been tailored to the needs of a client and does not correspond to the products traded. by exchanges, hedging the exposure is far more difficult..  

In this chapter we discuss some of the alternative approaches to this problem. We cover what are commonly referred to as the "Greek letters", or simply the "Greeks". Each Greek letter measures a different dimension to the risk in an option position and the aim of a trader is to manage the Greeks so that all risks are acceptable. The analysis presented in this chapter is applicable to market makers in options on an exchange as well as to traders working in the over-the-counter market for financial institutions.  

Toward the end of the chapter, we will consider the creation of options synthetically. This turns out to be very closely related to the hedging of options. Creating an option position synthetically is essentially the same task as hedging the opposite option position. For example, creating a long call option synthetically is the same as hedging a short position in the call option.  
