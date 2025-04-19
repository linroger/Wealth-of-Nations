---
tags:
  - binomial_tree
  - price_trees
  - rate_trees
  - term_structure
  - zero_coupon_bonds
aliases:
  - Binomial Tree
  - Price Tree
  - Rate Tree
key_concepts:
  - Binomial tree
  - Expected value
  - Spot rates
  - Underlying securities
  - Zero coupon bonds
---

# 7.1 RATE AND PRICE TREES  

Assume that the six-month and one-year spot rates are $2\%$ and $2.15\%$ respectively. Taking these market rates as given is equivalent to taking the prices of a six-month bond and a one-year-bond as given. Securities with assumed prices are called underlying securities to distinguish them from the contingent claims priced by arbitrage arguments.  

Next, assume that six months from now the six-month rate is either $2.50\%$ or $1.50\%$ with equal probability. This very strong assumption is. depicted at the top of Figure 7.1 by means of a binomial tree, where "binomial"' means that only two future values are possible. The columns in the. tree represent dates. The six-month rate is. $2\%$ today, which is called date 0. Six months from now, on date 1, there are two possible outcomes or states. of the world. The $2.50\%$ state is called the upstate while the $1.50\%$ state is called the downstate.  

Given the current term structure of spot rates (i.e., the current six-month and one-year rates), trees can be computed for the prices of six-month and. one-year zero coupon bonds. The price tree for. $\$1,000$ face value of the six-month zero, depicted at the bottom left of Figure 7.1, shows that the date-0 price is $\$1,000$ . (For readability, currency symbols are not included in price trees.) Note that, in a tree for the value of a particular security, the maturity of the security falls over time. On date 0 of the tree just discussed, the security is a six-month zero, while on date 1 the security is a maturing zero.  

The price tree for. $\$1,000$ face value of a one-year zero is depicted at the bottom right of Figure 7.1. The three prices on date 2 are all $\$1,000$ , which. is the face value of the one-year zero. The two prices on date 1 are found by discounting this certain. $\$1,000$ at the then-prevailing six-month rate. Hence, the date 1 upstate price is $\$1,000/(1+0.025/2)$ , or $\$987.654$ , and the date 1 downstate price is. $\$1,000/(1+0.015/2)$ , or $\$992.556$ . Finally, the date 0 price is computed using the given, date 0, one-year rate of $2.15\%$ $\$1,000$ , 0r 978.842.  

![](c2cbc43407e0d8e1569c228b30daac60b2516755c16e9fb1ba59ef04fd3f410d.jpg)  
FIGURE 7.1  Pricing Six-Month and One-Year Zero Coupon Bonds with a Binomial Rate Tree.  

The probabilities of moving up or down the tree may be used to compute average or expected values. As of date 0, the expected value of the one-year zero price on date 1 is,  

$$
0.5\times\$9987.654+0.5\times\$9992.556=\$9990.105
$$  

Discounting this expected value to date 0, at the date 0, six-month rate gives an expected discounted value of,.  

$$
{\frac{0.5\times{\bar{\mathrm{5987.654+0.5\times\bar{\mathrm{5992.556}}}}}}{1+{\frac{.02}{2}}}}=\bar{\mathrm{5980.302}}
$$  

Note that the one-year zero's expected discounted value of. $\$980.302$ is not equal to its market price of $\$978.842$ . These two numbers need not be equal, because investors do not price securities by expected discounted. value. Over the next six months, the one-year zero is a risky security, worth $\$987.654$ half of the time and $\$992.556$ the other half of the time, for an average or expected value of $\$990.105$ . If investors do not like this price uncertainty, they would prefer a security worth $\$990.105$ on date 1 with certainty. More specifically, a security worth $\$990.105$ with certainty after six months would sell for $\$990.105/(1+.02/2)$ , or $\$980.302$ , as of date 0. By contrast, investors penalize the risky one-year zero coupon bond with an average price of $\$990.105$ in six months by pricing it today at $\$978.842$ Chapters 8 and 9 elaborate further on investor risk aversion.  
