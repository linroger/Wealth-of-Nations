# 11.3  UPPER AND LOWER BOUNDS FOR OPTION PRICES  

In this section, we derive upper and lower bounds for option prices. These bounds do. not depend on any particular assumptions about the factors mentioned in Section 11.1 (except $r>0$ ). If an option price is above the upper bound or below the lower bound,. then there are profitable opportunities for arbitrageurs..  

# Upper Bounds  

An American or European call option gives the holder the right to buy one share of a stock for a certain price. No matter what happens, the option can never be worth more than the stock. Hence, the stock price is an upper bound to the option price:  

$$
c\leq S_{0}\quad{\mathrm{and}}\quad C\leq S_{0}
$$  

If these relationships were not true, an arbitrageur could easily make a riskless profit by buying the stock and selling the call option.  

An American put option gives the holder the right to sell one share of a stock for $K$ No matter how low the stock price becomes, the option can never be worth more than $K$ . Hence,  

$$
P\leq K
$$  

For European options, we know that at maturity the option cannot be worth more than $K$ . It follows that it cannot be worth more than the present value of $K$ today:  

$$
p\leq K e^{-r T}
$$  

If this were not true, an arbitrageur could make a riskless profit by writing the option and investing the proceeds of the sale at the risk-free interest rate.  

# Lower Bound for Calls on Non-Dividend-Paying Stocks  

A lower bound for the price of a European call option on a non-dividend-paying stock is  

$$
S_{0}\mathrm{~-~}K e^{-r T}
$$  

We first look at a numerical example and then consider a more formal argument.  

Suppose that $S_{0}=\mathbb{\S}20,K=\mathbb{\S}18,r=10\%$ per annum, and $T=1$ year. In this case,  

$$
S_{0}-K e^{-r T}=20-18e^{-0.1}=3.71
$$  

or $\$3.71$ . Consider the situation where the European call price is $\$3.00$ , which is less than the theoretical minimum of. $\$3.71$ . An arbitrageur can short the stock and buy the.  

call to provide a cash inflow of $\$20.00$ If invested for 1 year at $10\%$ per annum, the $\$17.00$ grows to $17e^{0.1\times1}=\S18.79$ At the end of the year, the option expires. If the stock price is greater than $\$18.00$ , the arbitrageur exercises the option paying $\$18.00$ for the stock and uses the stock to close out the short position. This leads to a profit of  

$$
\$18.79-48
$$  

If the stock price is less than $\$18.00$ , the stock is bought in the market and the short position is closed out. The arbitrageur then makes an even greater profit. For example, if the stock price is $\$123$ , the arbitrageur's profit is  

$$
\$18.79-
$$  

For a more formal argument, we consider the following two portfolios:  

Portfolio $A$ : one European call option plus a zero-coupon bond that provides a payoff of $K$ at time $T$   
Portfolio $B$ : one share of the stock.  

In portfolio A, the zero-coupon bond will be worth $K$ at time $T.$ If $S_{T}>K$ , the call option is exercised at maturity and portfolio A is worth $S_{T}.$ If $S_{T}<K$ , the call option expires worthless and the portfolio is worth. $K$ . Hence, at time $T$ portfolio A is worth.  

$$
\operatorname*{max}(S_{T},K)
$$  

Portfolio B is worth. $S_{T}$ at time $T.$ Hence, portfolio A is always worth as much as, and. can be worth more than, portfolio. $\mathrm{B}$ at the option's maturity. It follows that in the absence of arbitrage opportunities this must also be true today. The zero-coupon bond is worth $K e^{-r T}$ today. Hence,  

$$
c+K e^{-r T}\geq S_{0}
$$  

or  

$$
c\ge S_{0}-K e^{-r T}
$$  

Because the worst that can happen to a call option is that it expires worthless, its value cannot be negative. This means that $c\geq0$ , so that  

$$
c\ge\operatorname*{max}(S_{0}-K e^{-r T},0)
$$  

# Example 11.1  

Consider a European call option on a non-dividend-paying stock when the stock price is $\$51$ , the strike price is $\$50$ , the time to maturity is 6 months, and the risk-free interest rate is $12\%$ per annum. In this case, $S_{0}=51$ $K=50$ $T=0.5,\mathrm{and}r=0.12$ From equation (11.4), a lower bound for the option price is $S_{0}\mathrm{~-~}K e^{-r T}$ or  

$$
51-50e^{-0.12\times0.5}=\$3.91
$$  

# Lower Bound for European Puts on Non-Dividend-Paying Stocks  

For a European put option on a non-dividend-paying stock, a lower bound for the price is  

$$
K e^{-r T}-S_{0}
$$  

Again, we first consider a numerical example and then look at a more formal argument.  

Suppose that $S_{0}=\mathbb{S}37,K=\mathbb{\S}40,r=5\%$ per annum, and $T=0.5$ years. In this case,  

$$
K e^{-r T}-S_{0}=40e^{-0.05\times0.5}-37=\S2.01
$$  

Consider the situation where the European put price is $\$1.00$ , which is less than the. theoretical minimum of $\$2.01$ . An arbitrageur can borrow $\$38.00$ for 6 months to buy. both the put and the stock. At the end of the 6 months, the arbitrageur will be required to repay ${\hat{3}}8e^{0.05\times0.5}=\$38.96.$ If the stock price is below. $\$40.00$ , the arbitrageur exercises. the option to sell the stock for $\$40.00$ , repays the loan, and makes a profit of  

$$
\$40.00
$$  

If the stock price is greater than. $\$40.00$ , the arbitrageur discards the option, sells the. stock, and repays the loan for an even greater profit. For example, if the stock price is $\$42.00$ , the arbitrageur's profit is.  

$$
\$42.00-
$$  

For a more formal argument, we consider the following two portfolios:  

Portfolio $C$ : one European put option plus one share Portfolio $D$ : a zero-coupon bond paying off $K$ at time $T$  

If $S_{T}<K$ , then the option in portfolio $\mathrm{C}$ is exercised at option maturity and the portfolio becomes worth $K$ . If $S_{T}>K$ , then the put option expires worthless and the portfolio is worth $S_{T}$ at this time. Hence, portfolio $\mathrm{C}$ is worth  

$$
\operatorname*{max}(S_{T},K)
$$  

at time $T.$ Portfolio $\mathbf{D}$ is worth $K$ at time $T$ . Hence, portfolio $\mathrm{C}$ is always worth as much as, and can sometimes be worth more than, portfolio $\mathrm{\bfD}$ at time $T$ . It follows that in the absence of arbitrage opportunities portfolio $\mathrm{C}$ must be worth at least as much as portfolio $\mathbf{D}$ today. Hence,  

$$
p+S_{0}\geq K e^{-r T}
$$  

or  

$$
p\ge K e^{-r T}-S_{0}
$$  

Because the worst that can happen to a put option is that it expires worthless, its value cannot be negative. This means that  

$$
p\ge\operatorname*{max}(K e^{-r T}-S_{0},0)
$$  

# Example 11.2  

Consider a European put option on a non-dividend-paying stock when the stock price is $\$38$ , the strike price is. $\$40$ , the time to maturity is 3 months, and the. risk-free rate of interest is. $10\%$ per annum. In this case. $S_{\mathrm{0}}=38\$ $K=40$ $T=0.25$ , and $r=0.10$ . From equation (11.5), a lower bound for the option price is $K e^{-r T}-S_{0}$ or $40e^{-0.1\times0.25}-38=\S1.01$  
