---
tags:
  - arbitrage
  - forward_price
  - investment_asset
  - non_dividend_stock
  - zero_coupon_bond
aliases:
  - Forward Contract Valuation
key_concepts:
  - Arbitrage opportunities
  - Forward contract
  - Non-dividend-paying stock
  - Spot price
  - Zero-coupon bonds
---

# 5.4 FORWARD PRICE FOR AN INVESTMENT ASSET  

The easiest forward contract to value is one written on an investment asset that provides the holder with no income and for which there are no storage costs. Nondividend-paying stocks and zero-coupon bonds are examples of such investment assets.  

Consider a long forward contract to purchase a non-dividend-paying stock in 3 months.1 Assume the current stock price is $\$40$ and the 3-month risk-free interest rate is $5\%$ per annum.  

Suppose first that the forward price is relatively high at. $\$43$ . An arbitrageur can borrow $\$40$ at the risk-free interest rate of. $5\%$ per annum, buy one share, and short a forward contract to sell one share in 3 months. At the end of the 3 months, the arbitrageur delivers the share and receives $\$43$ . The sum of money required to pay off the loan is  

$$
40e^{0.05\times3/12}=\$40.50
$$  

By following this strategy, the arbitrageur locks in a profit of $\$43.00-40.50=\$2.50$ at the end of the 3-month period..  

Suppose next that the forward price is relatively low at $\$39$ . An arbitrageur can. short one share, invest the proceeds of the short sale at $5\%$ per annum for 3 months,. and take a long position in a 3-month forward contract. The proceeds of the short sale grow to $\bar{40e^{\bar{0}.05\times3/12}}$ or $\$40.50$ in 3 months. At the end of the 3 months, the arbitrageur pays $\$39$ , takes delivery of the share under the terms of the forward contract, and uses it to close out the short position. A net gain of  

$$
\$40.50-
$$  

is therefore made at the end of the 3 months. The two trading strategies we have considered are summarized in Table 5.2.  

Under what circumstances do arbitrage opportunities such as those in Table 5.2 not exist? The first arbitrage works when the forward price is greater than $\$40.50$ .The second arbitrage works when the forward price is less than $\$40.50$ . We deduce that for there to be no arbitrage the forward price must be exactly $\$40.50$  

# A Generalization  

To generalize this example, we consider a forward contract on an investment asset with price $S_{0}$ that provides no income. Using our notation,. $T$ is the time to maturity, $r$ is the risk-free rate, and $F_{0}$ is the forward price. The relationship between. $F_{0}$ and $S_{0}$ is  

$$
F_{0}=S_{0}e^{r T}
$$  

Table 5.2Arbitrage opportunities when forward price is out of line with spot price for asset providing no income. (Asset price. $=\$40$ ; interest rate $=5\%$ maturity of forward contract $=3$ months.)   


<html><body><table><tr><td>ForwardPrice=$43</td><td>ForwardPrice=$39</td></tr><tr><td>Actionnow:</td><td>Actionnow:</td></tr><tr><td>Borrow $40 at 5%for 3 months</td><td>Short 1 unit of asset torealize$40</td></tr><tr><td>Buy one unit of asset</td><td>Invest $40 at 5%for 3 months</td></tr><tr><td>Enter into forward contract to sell</td><td>Enter into a forward contract to buy</td></tr><tr><td>assetin3monthsfor$43</td><td>assetin3monthsfor$39</td></tr><tr><td>Actionin3months:</td><td>Actionin3months:</td></tr><tr><td>Sell asset for $43</td><td>Buy asset for $39</td></tr><tr><td>Use $40.50 to repay loan with interest</td><td>Close short position</td></tr><tr><td></td><td>Receive $40.50 from investment</td></tr><tr><td>Profit realized = $2.50</td><td>Profit realized = $1.50</td></tr></table></body></html>  

$F_{0}>S_{0}e^{r T}$ , arbitrageurs can buy the asset and short forward contracts on the asset. If $F_{0}<S_{0}e^{r T}$ , they can short the asset and enter into long forward contracts on it.? In our example, $S_{0}=40$ $r=0.05$ , and $T=0.25$ , so that equation (5.1) gives  

$$
F_{0}=40e^{0.05\times0.25}=\S40.50
$$  

which is in agreement with our earlier calculations  

A long forward contract and a spot purchase both lead to the asset being owned at. time $T$ The forward price is higher than the spot price because of the cost of. financing the spot purchase of the asset during the life of the forward contract. This point was overlooked by Kidder Peabody in 1994, much to its cost (see Business Snapshot 5.1).  

# Example 5.1  

Consider a 4-month forward contract to buy a zero-coupon bond that will mature. 1 year from today. (This means that the bond will have 8 months to go when the forward contract matures.) The current price of the bond is. $\$930$ . We assume that the 4-month risk-free rate of interest (continuously compounded) is. $6\%$ per annum. Because zero-coupon bonds provide no income, we can use equation (5.1) with $T=4/12,r=0.06$ , and $S_{0}=930\$ The forward price, $F_{0}$ , is given by  

$$
F_{0}=930e^{0.06\times4/12}=\S948.79
$$  

This would be the delivery price in a contract negotiated today.  

# Business Snapshot 5.1 Kidder Peabody's Embarrassing Mistake  

Investment banks have developed a way of creating a zero-coupon bond, called a strip, from a coupon-bearing Treasury bond by selling each of the cash flows underlying the coupon-bearing bond as a separate security. Joseph Jett, a trader working for Kidder Peabody, had a relatively simple trading strategy. He would buy strips and sell them in the forward market. As equation (5.1) shows, the forward price of a security providing no income is always higher than the spot price. Suppose, for example, that the 3-month interest rate is $4\%$ per annum and the spot price of a strip is $\$70$ The 3-month forward price of the strip is $70e^{0.04\times3/12}=\hat{\Phi}7\hat{0}.7\hat{0}$  

Kidder Peabody's computer system reported a profit on each of Jett's trades equal to the excess of the forward price over the spot price ( $\$0.70$ in our example). In fact, this profit was nothing more than the cost of financing the purchase of the strip. But, by rolling his contracts forward, Jett was able to prevent this cost from accruing to him.  

The result was that the system reported a profit of. $\$100$ million on Jett's trading (and Jett received a big bonus) when in fact there was a loss in the region of. $\$350$ million. This shows that even large financial institutions can get relatively simple things wrong!  

# What If Short Sales Are Not Possible?  

Short sales are not possible for all investment assets and sometimes a fee is charged for borrowing assets. As it happens, this does not matter. To derive equation (5.1), we do not need to be able to short the asset. All that we require is that there be market participants who hold the asset purely for investment (and by definition this is always true of an investment asset). If the forward price is too low, they will find it attractive to sell the asset and take a long position in a forward contract.  

We continue to consider the case where the underlying investment asset gives rise to no storage costs or income. If $F_{0}>S_{0}e^{r T}$ an investor can adopt the following strategy:  

1.Borrow $S_{0}$ dollars at an interest rate. $r$ for $T$ years.   
2. Buy 1 unit of the asset..   
3. Enter into a forward contract to sell 1 unit of the asset.  

At time $T$ the asset is sold for. $F_{0}$ An amount $S_{0}e^{r T}$ is required to repay the loan at this. time and the investor makes a profit of $F_{0}-S_{0}e^{r T}$  

Suppose next that $F_{0}<S_{0}e^{\bar{r}T}.$ In this case, an investor who owns the asset can:  

1. Sell the asset for $S_{0}$   
2. Invest the proceeds at interest rate. $r$ for time $T$   
3. Enter into a forward contract to buy 1 unit of the asset.  

At time $T$ the cash invested has grown to $S_{0}e^{r T}.$ The asset is repurchased for $F_{0}$ and thee investor makes a profit of. $S_{0}e^{r T}-F_{0}$ relative to the position the investor would have been in if the asset had been kept.  

As in the non-dividend-paying stock example considered earlier, we can expect the forward price to adjust so that neither of the two arbitrage opportunities we have considered exists. This means that the relationship in equation (5.1) must hold.  
