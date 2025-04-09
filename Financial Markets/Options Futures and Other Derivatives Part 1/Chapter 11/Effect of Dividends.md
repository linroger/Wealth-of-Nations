# 11.7 EFFECT OF DIVIDENDS  

The results produced so far in this chapter have assumed that we are dealing with options on a non-dividend-paying stock. In this section, we examine the impact of dividends. We assume that the dividends that will be paid during the life of the option  

![](images/bf79158770a7fe393def25179d0b0d6ca3843092912ee19213ffd6b8579d5d58.jpg)  
Figure 11.7 Variation of price of a European put option with the stock price.  

are known. In many situations, this assumption is often not too unreasonable. We will use $D$ to denote the present value of the dividends during the life of the option. In the calculation of $D$ , a dividend is assumed to occur at the time of its ex-dividend date.  

# Lower Bound for Calls and Puts  

We can redefine portfolios A and B as follows:  

Portfolio $A$ : one European call option plus an amount of cash equal to $D+K e^{-r T}$ Portfolio $B$ : one share  

A similar argument to the one used to derive equation (11.4) shows that  

$$
c\ge\operatorname*{max}(S_{0}-D-K e^{-r T},0)
$$  

We can also redefine portfolios $\mathrm{C}$ and $\mathbf{D}$ as follows:  

Portfolio $C$ : one European put option plus one share Portfolio $D$ : an amount of cash equal to $D+K e^{-r T}$  

A similar argument to the one used to derive equation (11.5) shows that  

$$
p\geq\operatorname*{max}(D+K e^{-r T}-S_{0},0)
$$  

# Early Exercise  

When dividends are expected, we can no longer assert that an American call option will not be exercised early. Sometimes it is optimal to exercise an American call immediately prior to an ex-dividend date. It is never optimal to exercise a call at other times. This point is discussed further in Section 15.12.  

# Put-Call Parity  

Comparing the value at option maturity of the redefined portfolios A and $\mathrm{C}$ shows that, with dividends, the put-call parity result in equation (11.6) becomes  

$$
c+D+K e^{-r T}=p+S_{0}
$$  

Dividends cause equation (11.7) to be modified (see Problem 11.24) to  

$$
S_{0}-D-K\le C-P\le S_{0}-K e^{-r T}
$$  

# SUMMARY  

There are six factors affecting the value of a stock option: the current stock price, the strike price, the time to expiration, the stock price volatility, the risk-free interest rate, and the dividends expected during the life of the option. The value of a call usually increases as the current stock price, the time to expiration, the volatility, and the riskfree interest rate increase. The value of a call decreases as the strike price and expected. dividends increase. The value of a put usually increases as the strike price, the time to. expiration, the volatility, and the expected dividends increase. The value of a put decreases as the current stock price and the risk-free interest rate increase..  

It is possible to reach some conclusions about the value of stock options without making any assumptions about the volatility of stock prices. For example, the price of a call option on a stock must always be worth less than the price of the stock itself. Similarly, the price of a put option on a stock must always be worth less than the. option's strike price.  

A European call option on a non-dividend-paying stock must be worth more than  

$$
\operatorname*{max}(S_{0}-K e^{-r T},0)
$$  

where $S_{0}$ is the stock price,. $K$ is the strike price,. $r$ is the risk-free interest rate, and $T$ is the time to expiration. A European put option on a non-dividend-paying stock must be worth more than.  

$$
\operatorname*{max}(K e^{-r T}-S_{0},0)
$$  

When dividends with present value $D$ will be paid, the lower bound for a European call option becomes  

$$
\operatorname*{max}(S_{0}-D-K e^{-r T},0)
$$  

and the lower bound for a European put option becomes  

$$
\operatorname*{max}(K e^{-r T}+D-S_{0},0)
$$  

Put-call parity is a relationship between the price, $c$ , of a European call option on a. stock and the price, $p$ , of a European put option on a stock. For a non-dividend-paying stock, it is  

$$
c+K e^{-r T}=p+S_{0}
$$  

For a dividend-paying stock, the put-call parity relationship is  

$$
c+D+K e^{-r T}=p+S_{0}
$$  

Put-call parity does not hold for American options. However, it is possible to use arbitrage arguments to obtain upper and lower bounds for the difference between the price of an American call and the price of an American put.  

In Chapter 15, we will carry the analyses in this chapter further by making specific assumptions about the probabilistic behavior of stock prices. The analysis will enable us to derive exact pricing formulas for European stock options. In Chapters 13 and 21, we will see how numerical procedures can be used to price American options.  

# FURTHER READING  

Broadie, M., and J. Detemple. "American Option Valuation: New Bounds, Approximations, and a Comparison of Existing Methods," Review of Financial Studies, 9, 4 (1996): 1211-50.   
Merton, R. C. "On the Pricing of Corporate Debt: The Risk Structure of Interest Rates," Journal of Finance, 29, 2 (1974): 449-70.   
Merton, R. C. "The Relationship between Put and Call Prices: Comment," Journal of Finance, 28 (March 1973): 183-84.   
Stoll, H. R. "The Relationship between Put and Call Option Prices," Journal of Finance, 24 (December 1969): 801-24.  

# Short Concept Questions  

11.1. List six factors that affect stock option prices.   
11.2. What is the lower bound for a European call option on a stock paying no dividends?   
11.3. What is the lower bound for a European put option on a stock paying no dividends?   
11.4. What is the put-call parity equation for a stock paying no dividends?   
11.5. Under what circumstances should an American call option on a stock paying no dividends be exercised early?   
11.6. Under what circumstances should an American put option on a stock paying no dividends be exercised early?  

# Practice Questions  

11.7. What is a lower bound for the price of a 4-month call option on a non-dividend-paying stock when the stock price is. $\$28$ , the strike price is $\$25$ , and the risk-free interest rate is $8\%$ per annum?   
11.8. What is a lower bound for the price of a 1-month European put option on a nondividend-paying stock when the stock price is. $\$12$ , the strike price is $\$15$ , and the riskfree interest rate is $6\%$ per annum?   
11.9. Give two reasons why the early exercise of an American call option on a non-dividendpaying stock is not optimal. The first reason should involve the time value of money. The second should apply even if interest rates are zero.   
11.10. "The early exercise of an American put is a trade-off between the time value of money and the insurance value of a put." Explain this statement.   
11.11. Why is an American call option on a dividend-paying stock always worth at least as much. as its intrinsic value. Is the same true of a European call option? Explain your answer..   
11.12. The price of a non-dividend-paying stock is $\$19$ and the price of a 3-month European. call option on the stock with a strike price of. $\$20$ is $\$1$ . The risk-free rate is. $4\%$ per annum. What is the price of a 3-month European put option with a strike price of. $\$20?$   
11.13. Explain why the arguments leading to put-call parity for European options cannot be used to give a similar result for American options..   
11.14. What is a lower bound for the price of a 6-month call option on a non-dividend-paying stock when the stock price is. $\$80$ , the strike price is. $\$75$ , and the risk-free interest rate is. $10\%$ per annum?   
11.15. What is a lower bound for the price of a 2-month European put option on a nondividend-paying stock when the stock price is. $\$58$ , the strike price is $\$65$ , and the riskfree interest rate is $5\%$ per annum?   
11.16. A 4-month European call option on a dividend-paying stock is currently selling for $\$5$ The stock price is $\$64$ , the strike price is $\$60$ , and a dividend of $\$0.80$ is expected in 1 month. The risk-free interest rate is $12\%$ per annum for all maturities. What opportun-. ities are there for an arbitrageur?   
11.17. A 1-month European put option on a non-dividend-paying stock is currently selling for $\$2.50$ . The stock price is $\$47$ , the strike price is $\$50$ , and the risk-free interest rate is $6\%$ per annum. What opportunities are there for an arbitrageur?   
11.18. Give an intuitive explanation of why the early exercise of an American put becomes more attractive as the risk-free rate increases and volatility decreases.   
11.19. The price of a European call that expires in 6 months and has a strike price of $\$30$ is $\$2$ The underlying stock price is $\$29$ , and a dividend of $\$0.50$ is expected in 2 months and again in 5 months. Risk-free interest rates (all maturities) are $10\%$ . What is the price of a European put option that expires in 6 months and has a strike price of $\$30?$   
11.20. Explain the arbitrage opportunities in Problem 11.19 if the European put price is. $\$3$   
11.21. The price of an American call on a non-dividend-paying stock is. $\$4$ . The stock price is $\$31$ , the strike price is. $\$30$ , and the expiration date is in 3 months. The risk-free interest rate is $8\%$ . Derive upper and lower bounds for the price of an American put on the same stock with the same strike price and expiration date.   
11.22. Explain carefully the arbitrage opportunities in Problem 11.21 if the American put price is greater than the calculated upper bound.   
11.23. Prove the result in equation (11.7). (Hint: For the first part of the relationship, consider (a) a portfolio consisting of a European call plus an amount of cash equal to $K$ , and (b) a portfolio consisting of an American put option plus one share.)   
11.24. Prove the result in equation (11.11). (Hint: For the first part of the relationship, consider (a) a portfolio consisting of a European call plus an amount of cash equal to $D+K$ , and (b) a portfolio consisting of an American put option plus one share.)   
11.25. Consider a 5-year call option on a non-dividend-paying stock granted to employees. The option can be exercised at any time after the end of the first year. Unlike a regular exchange-traded call option, the employee stock option cannot be sold. What is the likely impact of this restriction on the early-exercise decision?  

11.26. Use the software DerivaGem to verify that Figures 11.1 and 11.2 are correct.  

11.27. What is the impact (if any) of negative interest rates on:  

(a) The put-call parity result for European options   
(b) The result that American call options on non-dividend-paying stocks should never be exercised early   
(c) The result that American put options on non-dividend-paying stocks should sometimes be exercised early.  

Assume that holding cash earning zero interest is not possible  

11.28. Calls were traded on exchanges before puts. During the period of time when calls were traded but puts were not traded, how would you create a European put option on a non-. dividend-paying stock synthetically.  

11.29. The prices of European call and put options on a non-dividend-paying stock with an expiration date in 12 months and a strike price of $\$120$ are $\$20$ and $\$5$ , respectively. The current stock price is $\$130$ . What is the implied risk-free rate?.  

11.30. A European call option and put option on a stock both have a strike price of $\$20$ and an expiration date in 3 months. Both sell for $\$3$ . The risk-free interest rate is. $10\%$ per annum, the current stock price is. $\$19$ , and a $\$1$ dividend is expected in 1 month. Identify the arbitrage opportunity open to a trader.  

11.31. Suppose that $c_{1},c_{2}$ , and $c_{3}$ are the prices of European call options with strike prices $K_{1}$ $K_{2}$ ,and $K_{3}$ , respectively, where $K_{3}>K_{2}>K_{1}$ and $K_{3}-K_{2}=K_{2}-K_{1} $ All options have the same maturity. Show that  

$$
c_{2}\leq0.5(c_{1}+c_{3})
$$  

(Hint: Consider a portfolio that is long one option with strike price $K_{1}$ , long one option with strike price $K_{3}$ , and short two options with strike price. $K_{2}$  

11.32. What is the result corresponding to that in Problem 11.31 for European put options?  

![](images/187d2433b0566e3755883555ec6e4f545bf77b357d5a9d3a121a3c13325bcaa8.jpg)  

# Trading Strategies Involving Options  

We discussed the profit pattern from an investment in a single option in Chapter 10. In.   
this chapter we look at what can be achieved when an option is traded in conjunction.   
with other assets. In particular, we examine the properties of portfolios consisting of.   
(a) an option and a zero-coupon bond, (b) an option and the asset underlying the option, and (c) two or more options on the same asset..  

A natural question is why a trader would want the profit patterns discussed here. The answer is that the choices a trader makes depend on the trader's judgment about how prices will move and the trader's willingness to take risks. Principal-protected notes, discussed in Section 12.1 appeal to individuals who are risk-averse. They do not want to risk losing their principal, but have an opinion about whether a particular asset will increase or decrease in value and are prepared to let the return they earn on this principal depend on whether they are right. If a trader is willing to take rather more risk than this, he or she could choose a bull or bear spread, discussed in Section 12.3. Yet more risk would be taken with a straightforward long position in a call or put option.  

Suppose that a trader feels there will be a big move in price of an asset, but does not. know whether this will be up or down. There are a number of alternative trading strategies. A risk-averse trader might choose a reverse butterfly spread, discussed in Section 12.3, where there will be a small gain if the trader's hunch is correct and a small loss if it is not. A more aggressive investor might choose a straddle or strangle,. discussed in Section 12.4, where potential gains and losses are larger..  

Further trading strategies involving options are considered in later chapters. For. example, Chapter 17 shows how options on stock indices can be used to manage the risks in a stock portfolio and explains how range forward contracts can be used to. hedge a foreign exchange exposure; Chapter 19 covers the way in which Greek letters are used to manage the risks when derivatives are traded; Chapter 26 covers exotic options and what is known as static options replication..  
