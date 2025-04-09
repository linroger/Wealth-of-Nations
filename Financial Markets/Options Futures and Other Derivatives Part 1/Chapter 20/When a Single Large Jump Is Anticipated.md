# 20.8 WHEN A SINGLE LARGE JUMP IS ANTICIPATED  

Let us now consider an example of how an unusual volatility smile might arise in equity markets. Suppose that a stock price is currently. $\$50$ and an important news announce-. ment due in a few days is expected either to increase the stock price by $\$8$ or to reduce it by $\$8$ (This announcement could concern the outcome of a takeover attempt or the verdict in an important lawsuit.) The probability distribution of the stock price in, say,. 1 month might then consist of a mixture of two lognormal distributions, the first corresponding to favorable news, the second to unfavorable news. The situation is illustrated in Figure 20.5. The solid line shows the mixture-of-lognormals distribution. for the stock price in 1 month; the dashed line shows a lognormal distribution with the. same mean and standard deviation as this distribution..  

![](images/a691c1da2de1571224a0449250d76922da8ed11feceeaec4fbce92fecd559398.jpg)  
Figure 20.5 Effect of a single large jump. The solid line is the true distribution; the dashed line is the lognormal distribution..  

The true probability distribution is bimodal (certainly not lognormal). One easy way to investigate the general effect of a bimodal stock price distribution is to consider the extreme case where there are only two possible future stock prices. This is what we will now do.  

Suppose that the stock price is currently $\$50$ and it is known that in 1 month it will be either $\$42$ or $\$58$ Suppose further that the risk-free rate is $12\%$ per annum. The situation is illustrated in Figure 20.6. Options can be valued using the binomial model from Chapter 13. In this case, $u=1.16$ $d=0.84$ $a=1.0101$ , and $p=0.5314$ . The results from valuing a range of different options are shown in Table 20.3. The first column shows alternative strike prices; the second shows prices of 1-month European call options; the third shows the prices of one-month European put option prices; and the fourth shows implied volatilities. (As shown in Section 20.1, the implied volatility of a European put. option is the same as that of a European call option when they have the same strike price and maturity.) Figure 20.7 displays the volatility smile from Table 20.3. It is actually a "frown" (the opposite of that observed for currencies) with volatilities declining as we. move out of or into the money. The volatility implied from an option with a strike price of 50 will overprice an option with a strike price of 44 or 56..  

![](images/44a6576924ea6873077d005d99ddb35fd920ea50848c2a49979b3680393dad8d.jpg)  
Figure 20.6 Change in stock price in 1 month.  

Table 20.3 Implied volatilities in situation where it is known that the stock price will move from $\$50$ to either $\$42$ Or $\$58$   


<html><body><table><tr><td>Strikeprice ($)</td><td>Call price ($)</td><td>Put price ($)</td><td>Impliedvolatility (% )</td></tr><tr><td>42</td><td>8.42</td><td>0.00</td><td>0.0</td></tr><tr><td>44</td><td>7.37</td><td>0.93</td><td>58.8</td></tr><tr><td>46</td><td>6.31</td><td>1.86</td><td>66.6</td></tr><tr><td>48</td><td>5.26</td><td>2.78</td><td>69.5</td></tr><tr><td>50</td><td>4.21</td><td>3.71</td><td>69.2</td></tr><tr><td>52</td><td>3.16</td><td>4.64</td><td>66.1</td></tr><tr><td>54</td><td>2.10</td><td>5.57</td><td>60.0</td></tr><tr><td>56</td><td>1.05</td><td>6.50</td><td>49.0</td></tr><tr><td>58</td><td>0.00</td><td>7.42</td><td>0.0</td></tr></table></body></html>  

# SUMMARY  

The Black-Scholes-Merton model and its extensions assume that the probability distribution of the underlying asset at any given future time is lognormal. This assumption is not the one made by traders. They assume the probability distribution of an equity price has a heavier left tail and a less heavy right tail than the lognormal distribution. They also assume that the probability distribution of an exchange rate has a heavier right tail and a heavier left tail than the lognormal distribution.  

![](images/9dd0c8c0bb48eecf2781effdd1d1ff3606f6f6bbc2af0d7851c23bc70dc3b437.jpg)  
Figure 20.7 Volatility smile for situation in Table 20.3.  

Traders use volatility smiles to allow for nonlognormality. The volatility smile defines. the relationship between the implied volatility of an option and its strike price. For equity options, the volatility smile tends to be downward sloping. This means that outof-the-money puts and in-the-money calls tend to have high implied volatilities whereas. out-of-the-money calls and in-the-money puts tend to have low implied volatilities. For foreign currency options, the volatility smile is U-shaped. Both out-of-the-money and. in-the-money options have higher implied volatilities than at-the-money options.  

Often traders also use a volatility term structure. The implied volatility of an option. then depends on its life. When volatility smiles and volatility term structures are. combined, they produce a volatility surface. This defines implied volatility as a function of both the strike price and the time to maturity..  

# FURTHER READING  

Bakshi, G., C. Cao, and Z. Chen. "Empirical Performance of Alternative Option Pricing. Models," Journal of Finance, 52, No. 5 (December 1997): 2004-49..   
Bates, D. S. "Post-'87 Crash Fears in the S&P Futures Market," Journal of Econometrics, 94 (January/February 2000): 181-238.   
Daglish, T., J. C. Hull, and W. Suo. "Volatility Surfaces: Theory, Rules of Thumb, and Empirical Evidence," Quantitative Finance, 7, 5 (2007), 507-24.   
Derman, E. "Regimes of Volatility," Risk, April 1999: 55-59.   
Ederington, L. H., and W. Guan. "Why Are Those Options Smiling," Journal of Derivatives, 10, 2 (2002): 9-34.   
Hull, J. C., and A. White. "Optimal Delta Hedging of Options," Journal of Banking and Finance, 82 (September, 2017): 180-190.   
Jackwerth, J. C., and M. Rubinstein. "Recovering Probability Distributions from Option Prices," Journal of Finance, 51 (December 1996): 1611-31.   
Melick, W. R., and C. P. Thomas. "Recovering an Asset's Implied Probability Density Function from Option Prices: An Application to Crude Oil during the Gulf Crisis," Journal of Financial and Quantitative Analysis, 32, 1 (March 1997): 91-115.   
Reiswich, D., and U. Wystup. "FX Volatility Smile Construction," Working Paper, Frankfurt School of Finance and Management, April 2010.   
Rubinstein, M. "Nonparametric Tests of Alternative Option Pricing Models Using All Reported Trades and Quotes on the 30 Most Active CBOE Option Classes from August 23, 1976,. through August 31, 1978, Journal of Finance, 40 (June 1985): 455-80..  

# Short Concept Questions  

20.1. What is a volatility smile?   
20.2.What is a volatility surface?   
20.3. What is the difference between the volatility smiles that are typically observed for equities and currencies?  

20.4. What is a minimum variance delta?   
20.5. How is a volatility surface used in option pricing?  

# Practice Questions  

20.6. What volatility smile is likely to be observed when:  

(a) Both tails of the stock price distribution are less heavy than those of the lognormal distribution?   
(b) The right tail is heavier, and the left tail is less heavy, than that of a lognormal distribution?  

20.7. What volatility smile is likely to be caused by jumps in the underlying asset price? Is the pattern likely to be more pronounced for a 2-year option than for a 3-month option?  

20.8. A European call and put option have the same strike price and time to maturity. The call has an implied volatility of. $30\%$ and the put has an implied volatility of. $25\%$ .What trades would you do?  

20.9. Explain carefully why a distribution with a heavier left tail and less heavy right tail than the lognormal distribution gives rise to a downward sloping volatility smile..  

20.10. The market price of a European call is. $\$3.00$ and its price given by Black-Scholes-Merton model with a volatility of. $30\%$ is $\$3.50$ . The price given by this Black-Scholes-Merton model for a European put option with the same strike price and time to maturity is $\$1.00$ What should the market price of the put option be? Explain the reasons for your answer.  

20.11. Explain what is meant by "crashophobia."  

20.12. A stock price is currently $\$20$ . Tomorrow, news is expected to be announced that will. either increase the price by. $\$5$ or decrease the price by $\$5$ . What are the problems in. using Black-Scholes-Merton to value 1-month options on the stock?  

20.13. What volatility smile is likely to be observed for 6-month options when the volatility is uncertain and positively correlated with the stock price?  

20.14. Explain the problems in testing a stock option pricing model empirically.  

20.15. Suppose that a central bank's policy is to allow an exchange rate to fluctuate between. 0.97 and 1.03. What pattern of implied volatilities for options on the exchange rate would you expect to see?  

20.16. Option traders sometimes refer to deep-out-of-the-money options as being options on volatility. Why do you think they do this?.  

20.17. A European call option on a certain stock has a strike price of. $\$30$ , a time to maturity of. 1 year, and an implied volatility of. $30\%$ . A European put option on the same stock has a strike price of. $\$30$ , a time to maturity of 1 year, and an implied volatility of. $33\%$ . What is the arbitrage opportunity open to a trader? Does the arbitrage work only when the lognormal assumption underlying Black-Scholes-Merton holds? Explain carefully the reasons for your answer..  

20.18. Suppose that the result of a major lawsuit affecting a company is due to be announced tomorrow. The company's stock price is currently $\$60$ If the ruling is favorable to the. company, the stock price is expected to jump to. $\$75$ . If it is unfavorable, the stock is. expected to jump to $\$50$ . What is the risk-neutral probability of a favorable ruling?  

Assume that the volatility of the company's stock will be. $25\%$ for 6 months after the ruling if the ruling is favorable and. $40\%$ if it is unfavorable. Use DerivaGem to calculate. the relationship between implied volatility and strike price for 6-month European options on the company today. The company does not pay dividends. Assume that the 6-month risk-free rate is $6\%$ . Consider call options with strike prices of. $\$30$ $\$40$ $\$50$ $\$60,\$70$ , and $\$80$  

20.19. An exchange rate is currently 0.8000. The volatility of the exchange rate is quoted as $12\%$ and interest rates in the two countries are the same. Using the lognormal assumption, estimate the probability that the exchange rate in 3 months will be (a) less than 0.7000, (b) between 0.7000 and 0.7500, (c) between 0.7500 and 0.8000, (d) between 0.8000 and 0.8500, (e) between 0.8500 and 0.9000, and (f) greater than 0.9000. Based on the volatility smile usually observed in the market for exchange rates, which of these estimates would you expect to be too low and which would you expect to be too high?  

20.20. A stock price is $\$40$ A 6-month European call option on the stock with a strike price of. $\$30$ has an implied volatility of $35\%$ . A 6-month European call option on the stock with a strike price of $\$50$ has an implied volatility of $28\%$ . The 6-month risk-free rate is $5\%$ and no dividends are expected. Explain why the two implied volatilities are different. Use DerivaGem to calculate the prices of the two options. Use put-call parity to calculate. the prices of 6-month European put options with strike prices of $\$30$ and $\$50$ . Use DerivaGem to calculate the implied volatilities of these two put options.   
20.21. "The Black-Scholes-Merton model is used by traders as an interpolation tool." Discuss this view.   
20.22. Using Table 20.2, calculate the implied volatility a trader would use for an 8-month option with $K/S_{0}=1.04$   
20.23. A company's stock is selling for. $\$4$ The company has no outstanding debt. Analysts consider the liquidation value of the company to be at least. $\$300,000$ and there are 100,000 shares outstanding. What volatility smile would you expect to see?   
20.24. Data for a number of foreign currencies are provided on the author's website: http://www-2.rotman.utoronto.ca/\~hull/data Choose a currency and use the data to produce a table similar to Table 20.1.   
20.25. Data for a number of stock indices are provided on the author's website: http://www-2.rotman.utoronto.ca/\~hull/data Choose an index and test whether a three-standard-deviation down movement happens more often than a three-standard-deviation up movement.   
20.26. Consider a European call and a European put with the same strike price and time to maturity. Show that they change in value by the same amount when the volatility. increases from a level $\sigma_{1}$ to a new level $\sigma_{2}$ within a short period of time. (Hint: Use put-call parity.)   
20.27. An exchange rate is currently 1.0 and the implied volatilities of 6-month European options with strike prices 0.7, 0.8, 0.9, 1.0, 1.1, 1.2, 1.3 are $13\%$ $12\%$ $11\%$ $10\%$ $11\%$ $12\%$ $13\%$ . The domestic and foreign risk-free rates are both. $2.5\%$ . Calculate the implied probability distribution using an approach similar to that used for Example 20A.1 in the appendix to this chapter. Compare it with the implied distribution where all the implied volatilities are $11.5\%$  

20.28. Using Table 20.2, calculate the implied volatility a trader would use for an 11-month option with $K/S_{0}=0.98$  

# APPENDIX  

# DETERMINING IMPLIED RISK-NEUTRAL DISTRIBUTIONS FROM VOLATILITY SMILES  

The price of a European call option on an asset with strike price $K$ and maturity $T$ is given by  

$$
c=e^{-r T}\int_{S_{T}=K}^{\infty}(S_{T}-K)g(S_{T})d S_{T}
$$  

where $r$ is the interest rate (assumed constant), $S_{T}$ is the asset price at time $T$ , and $g$ is the risk-neutral probability density function of $S_{T}$ . Differentiating once with respect to $K$ gives  

$$
\frac{\partial c}{\partial K}=-e^{-r T}\int_{S_{T}=K}^{\infty}g(S_{T})d S_{T}
$$  

Differentiating again with respect to $K$ gives  

$$
\frac{\partial^{2}c}{\partial K^{2}}=e^{-r T}g(K)
$$  

This shows that the probability density function $g$ is given by  

$$
g(K)=e^{r T}\frac{\partial^{2}c}{\partial K^{2}}
$$  

This result, which is from Breeden and Litzenberger (1978), allows risk-neutral probability distributions to be estimated from volatility smiles.6 Suppose that $c_{1},c_{2}$ , and $c_{3}$ are the prices of $T$ -year European call options with strike prices of. $K\mathrm{~-~}\delta,K$ , and $K+\delta$ respectively. Assuming $\delta$ is small, an estimate of $g(K)$ , obtained by approximating the partial derivative in equation (20A.1), is.  

$$
e^{r T}\frac{c_{1}+c_{3}-2c_{2}}{\delta^{2}}
$$  

For another way of understanding this formula, suppose you set up a butterfly spread with strike prices $K-\delta,K$ , and $K+\delta$ , and maturity $T.$ This means that you buy a call. with strike price $K-\delta$ , buy a call with strike price. $K+\delta$ , and sell two calls with strike. price $K$ The value of your position is. $c_{1}+c_{3}-2c_{2}$ The value of the position can also be calculated by integrating the payoff over the risk-neutral probability distribution, $g(S_{T})$ and discounting at the risk-free rate. The payoff is shown in Figure 20A.1. Since $\delta$ is small, we can assume that $g(S_{T})=g(K)$ inthe whole ofthe range $K-\delta<S_{T}<K+\delta$ where the payoff is nonzero. The area under the "spike" in Figure 20A.1 is $0.5\times2\delta\times\delta=\delta^{2}$ The value of the payoff (when & is small) is therefore $e^{-r T}g(K)\delta^{2}$ . It follows that  

$$
e^{-r T}g(K)\delta^{2}=c_{1}+c_{3}-2c_{2}
$$  

![](images/252226359d23e235f9bd369932843fc4236600911e474770c7e769d01d4fb5c4.jpg)  
Figure 20A.1 Payoff from butterfly spread.  

which leads directly to  

$$
g(K)=e^{r T}\frac{c_{1}+c_{3}-2c_{2}}{\delta^{2}}
$$  

# Example 20A.1  

Suppose that the price of a non-dividend-paying stock is $\$10$ , the risk-free interest rate is $3\%$ , and the implied volatilities of 3-month European options with strike prices of. $\$6$ $\$7$ $\$8$ $\$9$ $\$10$ $\$11$ $\$12$ $\$13$ $\$14$ are $30\%$ $29\%$ $28\%$ $27\%$ $26\%$ $25\%$ $24\%$ $23\%$ $22\%$ , respectively. One way of applying the above results is as follows. Assume that $g(S_{T})$ is constant between $S_{T}=6$ and $S_{T}=7$ , constant between $S_{T}=7$ and $S_{T}=8$ , and so on. Define:  

$$
\begin{array}{r l}{g(S_{T})=g_{1}\quad\mathrm{for}\quad6\le S_{T}<7}\ {g(S_{T})=g_{2}\quad\mathrm{for}\quad7\le S_{T}<8}\ {g(S_{T})=g_{3}\quad\mathrm{for}\quad8\le S_{T}<9}\ {g(S_{T})=g_{4}\quad\mathrm{for}\quad9\le S_{T}<10}\ {g(S_{T})=g_{5}\quad\mathrm{for}\quad10\le S_{T}<11}\ {g(S_{T})=g_{6}\quad\mathrm{for}\quad11\le S_{T}<12}\ {g(S_{T})=g_{7}\quad\mathrm{for}\quad12\le S_{T}<13}\ {g(S_{T})=g_{8}\quad\mathrm{for}\quad13\le S_{T}<14}\end{array}
$$  

The value of $g_{1}$ can be calculated by interpolating to get the implied volatility for a 3-month option with a strike price of $\$6.5$ as $29.5\%$ . This means that options with strike prices of $\$6,\$6.5$ , and $\$7$ have implied volatilities of $30\%$ $29.5\%$ , and $29\%$ , respectively. From DerivaGem their prices are $\$4.045$ $\$3.549$ , and $\$3.055$ respectively. Using equation (20A.2), with $K=6.5$ and $\delta=0.5$ , gives  

$$
g_{1}={\frac{e^{0.03\times0.25}(4.045+3.055-2\times3.549)}{0.5^{2}}}=0.0057
$$  

Similar calculations show that  

$$
\begin{array}{c}{{g_{2}=0.0444,~g_{3}=0.1545,~g_{4}=0.2781}}\ {{g_{5}=0.2813,~g_{6}=0.1659,~g_{7}=0.0573,~g_{8}=0.0113}}\end{array}
$$  

![](images/869ce22a773525f3ff8e920324083294fae161206d030c352fd90e748e798138.jpg)  
Figure 20A.2 Implied probability distribution for Example 20A.1.   
Figure 20A.2 displays the implied distribution. (Note that the area under the. probability distribution is 0.9985. The probability that. $S_{T}<6$ or $S_{T}>14$ is therefore 0.0015.) Although not obvious from Figure 20A.2, the implied distribution does have a heavier left tail and less heavy right tail than a lognormal distribution. For the lognormal distribution based on a single volatility of $26\%$ , the probability of a stock price between $\$6$ and $\$7$ is 0.0031 (compared with 0.0057 in Figure 20A.2) and the probability of a stock price between. $\$13$ and $\$14$ is 0.0167 (compared with 0.0113 in Figure 20A.2).  

![](images/636e6774de04a99365ad1f32897bce5ed12dfecd318761abc18acb32b21117cc.jpg)  

# Basic Numerical Procedures  

This chapter discusses three numerical procedures for valuing derivatives when analytic results such as the Black-Scholes-Merton formulas do not exist. The first represents the. asset price movements in the form of a tree and was introduced in Chapter 13. The second is Monte Carlo simulation, which we encountered briefly in Chapter 14 when stochastic processes were explained. The third involves finite difference methods.  

Monte Carlo simulation is usually used for derivatives where the payoff is dependent. on the history of the underlying variable or where there are several underlying variables.. Trees and finite difference methods are usually used for American options and other derivatives where the holder has decisions to make prior to maturity. In addition to. valuing a derivative, all the procedures can be used to calculate Greek letters such as. delta, gamma, and vega.  

The basic procedures discussed in this chapter can be used to handle most of the derivatives valuation problems encountered in practice. However, sometimes they have to be adapted to cope with particular situations, as will be explained in Chapter 27.  
