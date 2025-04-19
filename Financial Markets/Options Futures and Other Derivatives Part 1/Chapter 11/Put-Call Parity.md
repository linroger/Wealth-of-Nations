---
tags:
  - '#american_options'
  - '#arbitrage_opportunities'
  - '#european_options'
  - '#non_dividend_paying_stock'
  - '#put_call_parity'
  - '#risk_free_interest_rate'
  - '#strike_price'
  - '#time_to_maturity'
  - '#zero_coupon_bond'
---
# 11.4  PUT-CALL PARITY  

We now derive an important relationship between the prices of European put and call. options that have the same strike price and time to maturity. Consider the following two portfolios that were used in the previous section:.  

Portfolio $A$ : one European call option plus a zero-coupon bond that provides a payoff of $K$ at time $T$ Portfolio $C$ : one European put option plus one share of the stock.  

We continue to assume that the stock pays no dividends. The call and put options have the same strike price $K$ and the same time to maturity $T$  

As discussed in the previous section, the zero-coupon bond in portfolio A will be. worth $K$ at time $T$ . If the stock price $S_{T}$ at time $T$ proves to be above $K$ , then the call option in portfolio A will be exercised. This means that portfolio A is worth. $(S_{T}-K)+K=S_{T}$ at time $T$ in these circumstances. If $S_{T}$ proves to be less than $K$ then the call option in portfolio A will expire worthless and the portfolio will be worth $K$ at time $T$  

In portfolio C, the share will be worth. $S_{T}$ at time $T.$ If $S_{T}$ proves to be below $K$ , then the put option in portfolio C will be exercised. This means that portfolio $\mathrm{C}$ is worth $(K-S_{T})+S_{T}=K$ at time $T$ in these circumstances. If $S_{T}$ proves to be greater than $K$ then the put option in portfolio $\mathrm{C}$ will expire worthless and the portfolio will be worth. $S_{T}$ at time $T$  

The situation is summarized in Table 11.2. If $S_{T}>K$ , both portfolios are worth $S_{T}$ at time $T$ if $S_{T}<K$ , both portfolios are worth $K$ at time $T$ . In other words, both are worth.  

$$
\operatorname*{max}(S_{T},K)
$$  

when the options expire at time $T$ . Because they are European, the options cannot be exercised prior to time $T$ . Since the portfolios have identical values at time $T$ , they must have identical values today. If this were not the case, an arbitrageur could buy the less expensive portfolio and sell the more expensive one. Because the portfolios are guaranteed to cancel each other out at time $T$ , this trading strategy would lock in an arbitrage profit equal to the difference in the values of the two portfolios.  

The components of portfolio A are worth $c$ and $K e^{-r T}$ today, and the components of portfolio $\mathrm{\textbf{C}}$ are worth $p$ and $S_{0}$ today. Hence,  

Table 11.2 Portfolios illustrating put-call parity.   


<html><body><table><tr><td colspan="2"></td><td>Sr > K</td><td>ST < K</td></tr><tr><td rowspan="3">PortfolioA</td><td>Call option</td><td>Sr - K</td><td>0</td></tr><tr><td>Zero-coupon bond</td><td>K</td><td>K</td></tr><tr><td>Total</td><td>ST</td><td>K</td></tr><tr><td rowspan="3">Portfolio C</td><td>Put Option</td><td>0</td><td>K - ST</td></tr><tr><td>Share</td><td>ST</td><td>ST</td></tr><tr><td>Total</td><td>ST</td><td>K</td></tr></table></body></html>  

$$
c+K e^{-r T}=p+S_{0}
$$  

This relationship is known as put-call parity. It shows that the value of a European call with a certain exercise price and exercise date can be deduced from the value of a European put with the same exercise price and exercise date, and vice versa.  

To illustrate the arbitrage opportunities when equation (11.6) does not hold, suppose that the stock price is. $\$31$ , the exercise price is. $\$30$ , the risk-free interest rate is $10\%$ per annum, the price of a three-month European call option is. $\$3$ , and the price of a. 3-month European put option is. $\$2.25$ . In this case,.  

$$
{\begin{array}{l}{c+K e^{-r T}=3+30e^{-0.1\times3/12}=\S32.26}\ {p+S_{0}=2.25+31=\S33.25}\end{array}}
$$  

Portfolio $\mathrm{C}$ is overpriced relative to portfolio A. An arbitrageur can buy the securities. in portfolio A and short the securities in portfolio C. The strategy involves buying the call and shorting both the put and the stock, generating a positive cash flow of.  

$$
-3+2.25+31=\$30.25
$$  

up front. When invested at the risk-free interest rate, this amount grows to  

$$
30.25e^{0.1\times0.25}=\$31.02
$$  

in three months. If the stock price at expiration of the option is greater than $\$30$ , the call will be exercised. If it is less than $\$30$ , the put will be exercised. In either case, the arbitrageur ends up buying one share for $\$30$ . This share can be used to close out the short position. The net profit is therefore  

$$
\$31.02\mathrm{~-~}\S30.00=\$1.02
$$  

For an alternative situation, suppose that the call price is $\$3$ and the put price is $\$1$ In this case,  

$$
\begin{array}{l}{c+K e^{-r T}=3+30e^{-0.1\times3/12}=\S32.26}\ {p+S_{0}=1+31=\S32.00}\end{array}
$$  

Portfolio A is overpriced relative to portfolio C. An arbitrageur can short the securities in. portfolio A and buy the securities in portfolio C to lock in a profit. The strategy involves shorting the call and buying both the put and the stock with an initial investment of.  

$$
\$31+\$1-\$3
$$  

When the investment is financed at the risk-free interest rate, a repayment of 29e0.1x0.25 - \$29.73 is required at the end of the three months. As in the previous case, either the call or the put will be exercised. The short call and long put option position therefore leads to the stock being sold for $\$30.00$ . The net profit is therefore  

$$
\$30.00-4
$$  

These examples are illustrated in Table 11.3. Business Snapshot 11.1 shows how options and put-call parity can help us understand the positions of the debt holders and equity holders in a company.  

Table 11.3 Arbitrage opportunities when put-call parity does not hold. Stock price $=\$31$ ; interest rate $=10\%$ ; call price. $ \mathit{\Omega}=\$3$ . Both put and call. have strike price of. $\$30$ and three months to maturity.  

<html><body><table><tr><td>Three-monthputprice=$2.25</td><td>Three-monthput price=$1</td></tr><tr><td>Actionnow:</td><td>Actionnow:</td></tr><tr><td>Buy call for $3</td><td>Borrow$29for3months</td></tr><tr><td>Short put to realize $2.25</td><td>Shortcalltorealize$3</td></tr><tr><td>Short the stocktorealize$31</td><td>Buy put for $1</td></tr><tr><td>Invest$30.25for3months</td><td>Buy the stock for $31</td></tr><tr><td>Actionin3monthsifS>30:</td><td>Actionin3months ifS>30:</td></tr><tr><td>Receive$31.02frominvestment</td><td>Call exercised:sell stockfor $30</td></tr><tr><td>Exercise call to buy stock for $30</td><td>Use $29.73 to repay loan</td></tr><tr><td>Net profit = $1.02</td><td>Net profit = $0.27</td></tr><tr><td>Actionin3monthsifS<30:</td><td>Actionin3monthsifS<30:</td></tr><tr><td>Receive $31.02from investment</td><td>Exercise put to sell stock for $30</td></tr><tr><td>Put exercised: buy stock for $30</td><td>Use $29.73 to repay loan</td></tr><tr><td>Net profit = $1.02</td><td>Net profit = $0.27</td></tr></table></body></html>  

# American Options  

Put-call parity holds only for European options. However, it is possible to derive some results for American option prices. It can be shown (see Problem 11.23) that, when there are no dividends,  

$$
S_{0}-K\le C-P\le S_{0}-K e^{-r T}
$$  

# Example 11.3  

An American call option on a non-dividend-paying stock with strike price $\$20.00$ and maturity in 5 months is worth $\$1.50$ . Suppose that the current stock price is $\$19.00$ and the risk-free interest rate is $10\%$ per annum. From equation (11.7), we have  

$$
19-20\le C-P\le19-20e^{-0.1\times5/12}
$$  

or  

$$
1\ge P-C\ge0.18
$$  

showing that $P-C$ lies between $\$0.18$ and $\$1.00$ . With $C$ at $\$1.50$ $P$ must lie between $\$1.68$ and $\$2.50$ . In other words, upper and lower bounds for the price of an American put with the same strike price and expiration date as the American call are $\$2.50$ and $\$1.68$  
