---
tags:
  - '#correlation'
  - '#currency_risk'
  - '#financial_engineering'
  - '#foreign_equity'
  - '#forward_contracts'
  - '#interest_rate_risk'
  - '#pricing_quantos'
  - '#quanto_instruments'
  - '#quanto_swaps'
---
# 10.5 A SPECIAL INSTRUMENT: QUANTOS  

Quanto-type financial products form a major class of instruments where price depends on correla-. tions. At the end of this chapter, we will look at these in detail and study the financial engineering. of quantos by discussing their characteristics and other issues. This can be regarded as another example to the methods introduced in Chapter 9. We will consider pricing of quantos in Chapter 13.  

# 10.5.1 A SIMPLE EXAMPLE  

Consider the standard currency swap in Figure 10.7. There are two cash flows, in two currencies, USD and EUR. The principal amounts are exchanged at the start date and reexchanged at the end date. During the life of the swap, floating payments based on USD LIBOR are exchanged for floating payments based on EUR LIBOR. There will be a small known spread involved in these exchanges as well.  

The standard currency swap of Figure 10.7 will now be modified in an interesting way. We keep the two floating LIBOR rates the same, but force all payments to be made in one currency only, say USD. In other words, the calculated EUR LIBOR indexed cash flows will be paid (received) in USD. This instrument is called a quanto swap or differential swap. In such a swap, the principal amounts would be in the same currency, and there would be no need to exchange them. Only net interest rate cash flows will be exchanged.  

![](images/3e028155df94934be7fb76428510db9048998eaf30b331e50156c1f1685cc1b9.jpg)  

# FIGURE 10.7  

# EXAMPLE  

Suppose the notional principal is USD30 million. Quotes on LIBOR are as follows:  

<html><body><table><tr><td>0.055 1.71</td><td></td></tr><tr><td>3-month</td><td></td></tr><tr><td>6-month 0.185</td><td>1.64</td></tr><tr><td>12-month 0.065</td><td>1.73</td></tr></table></body></html>  

In a quanto swap, one party would like to receive 6-month USD LIBOR and pay 6-month JPY LIBOR for 1 year. However, all payments are made in USD. For example, if the first settlement is according to the quotes given in the table, in 6 months this party will receive:  

$$
30,000,000(0.0164)\left({\frac{1}{2}}\right)-30,000,000(0.00185)\left({\frac{1}{2}}\right)-30,000,000\left({\frac{1}{2}}\right)c
$$  

where $c$ is a constant spread that needs to be determined in the pricing of this quanto swap.   
Note that the JPY interest rate is applied to a USD denominated principal..  

In this type of swap, the two parties are exposed to the risk of interest rate differentials. However, at least one of them is not exposed to currency risk..  

Why would anyone be interested in quanto swaps? Note that even after the spread $c$ is included the interest cost paid in dollars,  

$$
\mathrm{JPY}\mathrm{LIBOR}+c
$$  

may be significantly less than USD LIBOR rates. This way, the party that receives USD LIBOR and pays JPY LIBOR (in USD) may be lowering funding costs substantially. Accordingly, the mar-. ket would see interest in such quanto swaps when the short ends of the yield curves in two major. currencies are significantly different. Banks could then propose these instruments to their clients as a way of "reducing" funding costs. Of course, from the clients' point of view, quanto swaps still involve an interest rate risk and, possibly, an exchange rate risk. If the underlying yield curves shift. in unexpected ways, losses may be incurred..  

The following example illustrates these from the point of view of British pound and Swiss franc interest rates.  

# EXAMPLE  

With European economies at a very different point in the trade cycle, corporates are looking to switch their debts into markets offering the cheapest funding. But whereas most would previously have been dissuaded by foreign exchange risk, the emergence of quanto products has allowed them to get the best of both worlds.  

With quanto swaps, interest is paid in a different currency to that of the reference index, the exchange rate being fixed at the outset of the swap. As a result, the product can provide exposure to a nondomestic yield curve without the accompanying exchange rate risks.  

In recent weeks, this type of product has proved increasingly appealing to UK corporates that have entered into a swap in which the paying side is referenced to Swiss LIBOR but the returns are paid in sterling. Swiss franc LIBOR is still low relative to sterling LIBOR and although the corporate ends up paying Swiss LIBOR plus a spread, funding costs are often still considerably cheaper than normal sterling funding. Deals have also been referenced to German or Japanese LIBOR.. However, derivatives officials were also keen to point out that quanto products are far from being riskfree. "Given that the holder of the swap ends up paying Swiss LIBOR plus a spread, the curves do not have. to converge much to render the trade uneconomic," said one..  

(Thomson Reuters IFR Issue 1190, July 5 1997)  

# 10.5.1.1 Quantos in equity  

The notion of a quanto instrument can be applied in other financial markets. For example, a foreign investor may want to have exposure to Japanese equity markets without having to incur currency. risk. Then, a quanto contract can be designed such that the gains and losses of an index in Japanese equities are paid annually in the foreign investors' domestic currency instead of in yen..  

# 10.5.2 PRICING  

The pricing of quanto contracts raises interesting financial engineering issues.17 we discuss a sim-. ple case to illustrate quantos. First, fix the underlying. Assume that we are dealing with a particular foreign currency denominated stock $S_{t}^{*}$ . Without loss of generality, suppose the domestic currency. is UsD, the foreign currency is euro, and the stock is European..  

A dollar-based investor would like to buy the stock, and benefit from potential upside in European markets, but dislikes currency exposure to euro. The investor desires exposure to underlying equity risk only. To accommodate his wish, the bank proposes purchasing the stock via a quanto forward. An expiration date $T$ is chosen, and the current exchange rate EUR/USD, $e_{t}$ is used to calculate the time $T$ settlement. The forward contract has USD price $F_{t}$ and settles according to  

$$
V_{T}=(e_{t}S_{T}^{*}-F_{t})
$$  

Here, the $V_{T}$ is the time $T$ value of the contract. It is measured in the domestic currency and will be positive if the stock appreciates sufficiently; otherwise, it will be negative. $F_{t}$ is the forward price of the quanto contract on $S_{T}^{*}$ and has to be determined by a proper pricing strategy.  

# 10.5.3 THE MECHANICS OF PRICING  

Suppose the current time is. $t$ and a forward quanto contract on $S_{T}^{*}$ is written with settlement date $T=t+\Delta$ . Suppose also that at time. $T$ there are only three possible states of the world. $\{\omega^{1},\omega^{2},\omega^{3}\}$ The following table gives the possible values of four instruments, the foreign stock, a foreign deposit, a domestic deposit, and a forward FX contract on the exchange rate $e_{t}$  

<html><body><table><tr><td>Time t Price</td><td>Value in w</td><td>Value in w2</td><td>Value inw3</td></tr><tr><td>S*</td><td>S+</td><td>S+△</td><td>S+</td></tr><tr><td>1USD</td><td>(1 + r△)</td><td>(1 + r△)</td><td>(1 + r△)</td></tr><tr><td>1et</td><td>el+△(1+r*△)</td><td>e²+△(1 +r*)</td><td>e3+△(1 +r*△)</td></tr><tr><td>0</td><td>V+a</td><td>f-e²+△</td><td>f-e3+</td></tr></table></body></html>  

In this table, the first row gives the value of the foreign stock in the three future states of the world. These are measured in the foreign currency. The second row represents what happens to 1 dollar invested in a domestic savings account. The third row shows what happens when 1 unit of foreign currency is purchased at $e_{t}$ dollars and invested at the foreign rate $r^{*}$  

The forward exchange rate $f_{t}$ is priced as  

$$
f_{t}=e_{t}\frac{1+r\Delta}{1+r^{*}\Delta}
$$  

where $e_{t}$ is the current exchange rate. In this example, we are assuming that the domestic and foreign interest rates are constant at $r$ and $r^{*}$ , respectively. Now consider the quanto forward contract with current price $F_{t}$ mentioned earlier. $F_{t}$ will be determined at time $t.$ and the contract will settle at time $T=t+\Delta$ . Depending on which state occurs, the settlement amount will be one of the following:  

$$
\{(S_{t+\Delta}^{*}e_{t}-F_{t}),(S_{t+\Delta}^{*2}e_{t}-F_{t}),(S_{t+\Delta}^{*3}e_{t}-F_{t})\}
$$  

These amounts are all in USD. What is the arbitrage-free value of $\boldsymbol{F}_{t}$  

We can use three of the four instruments listed to form a portfolio with weights $\lambda_{i},\boldsymbol{i}=1$ , 2, 3 that replicate the possible values of $e_{t}S_{t+\Delta}^{*}$ at each state exactly. This will be similar to the cases discussed in Chapter 8. For example, using the first three instruments, for each state we can write  

$$
\begin{array}{r l}{\mathrm{State}\omega^{1}}&{\lambda_{1}S_{t+\Delta}^{*1}e_{t+\Delta}^{1}+\lambda_{2}(1+r\Delta)+\lambda_{3}e_{t+\Delta}^{1}(1+r^{*}\Delta)=S_{1+\Delta}^{*1}e_{t}^{1}}\ {\mathrm{State}\omega^{2}}&{\lambda_{1}S_{t+\Delta}^{*2}e_{t+\Delta}^{2}+\lambda_{2}(1+r\Delta)+\lambda_{3}e_{t+\Delta}^{1}(1+r^{*}\Delta)=S_{1+\Delta}^{*2}e_{t}}\ {\mathrm{State}\omega^{3}}&{\lambda_{1}S_{t+\Delta}^{*3}e_{t+\Delta}^{3}+\lambda_{2}(1+r\Delta)+\lambda_{3}e_{t+\Delta}^{1}(1+r^{*}\Delta)=S_{1+\Delta}^{*3}e_{t}}\end{array}
$$  

In these equations, the right-hand side is the future value of the foreign stock measured at the current exchange rate. The left-hand side is the value of the replicating portfolio in that state.  

These form three equations in three unknowns, and, in general, can be solved for the unknown $\lambda_{i}$ Once these portfolio weights are known, the current cost of putting the portfolio together leads to the price of the quanto:.  

$$
\lambda_{1}S_{t}^{*}e_{t}+\lambda_{2}+\lambda_{3}e_{t}
$$  

This USD amount needs to be carried to time $T$ since the contract settles at $T.$ This gives  

$$
F_{t}=[\lambda_{1}S_{t}^{*}e_{t}+\lambda_{2}+\lambda_{3}e_{t}](1+r\Delta)
$$  

# EXAMPLE  

Suppose we have the following data on the first three rows of the previous table:  

<html><body><table><tr><td>Time t Price</td><td>Value in w1</td><td>Value in w2</td><td>Value inw3</td></tr><tr><td>100</td><td>115</td><td>100</td><td>90</td></tr><tr><td>1 USD</td><td>(1 + 0.05△)</td><td>(1 + 0.05△)</td><td>(1 + 0.05)</td></tr><tr><td>1EURX0.98</td><td>(1 + 0.03△)1.05</td><td>(1 + 0.03△)0.98</td><td>(1 + 0.03△)0.90</td></tr></table></body></html>  

What is the price of the quanto forward? We set up the three equations.  

$$
\lambda_{1}(1.05)115+\lambda_{2}(1+0.05\Delta)+\lambda_{3}1.05(1+0.03\Delta)=0.98(115)
$$  

$$
\begin{array}{r l}{\lambda_{1}(0.98)100+\lambda_{2}(1+0.05\Delta)+\lambda_{3}0.98(1+0.03\Delta)=0.98(100)}\ {\lambda_{1}(0.90)90+\lambda_{2}(1+0.05\Delta)+\lambda_{3}0.90(1+0.03\Delta)=0.98(90)}\end{array}
$$  

We select the expiration $\Delta=1$ , for simplicity, and obtain  

$$
\lambda_{1}=0.78
$$  

$$
\lambda_{2}=60.67
$$  

$$
\lambda_{3}=-41.53
$$  

Borrowing 42 units of foreign currency, lending 61 units of domestic currency, and buying O.78 units of the foreign stock would replicate the value of the quanto contract at time $t+1$ . The price of this portfolio at $t$ will be  

$$
100\lambda_{1}0.98+\lambda_{2}+0.98\lambda_{3}=96.41
$$  

If this is to be paid at time. $t+\Delta$ , then it will be equal to the arbitrage-free value of $F_{t}$  

$$
F_{t}=(1.05)96.41=101.23
$$  

This example shows that the value of the quanto feature is related to the correlation between the. movements of the exchange rate and the foreign stock. If this correlation is zero, then the quanto will have the same value as a standard forward. If the correlation is positive (negative), then the. quanto forward will be less (more) valuable than the standard forward. In the example above,. the exchange rates and foreign stock were positively correlated and the quantoed instrument cost less than the original value of the foreign stock..  

# 10.5.4 WHERE DOES CONVEXITY COME IN?  

The discussion of the previous section has shown that, in a simple one period setting with three possible states of the world, we can form a replicating portfolio for the quantoed asset payoffs at a future date. As the number of states increases and time becomes continuous, this type of replicating portfolio needs readjustment. The portfolio adjustments would, in turn, lead to negative or positive trading gains depending on the sign of the correlation, similar to the case of options. This is where volatilities become relevant. In the case of quanto assets there are, at least, two risks involved, namely, exchange rate and foreign equity or interest rates. The covariance between these affects pricing as well.  

The quanto feature will have a positive or negative value at time $t_{0}$ due to the trading gains realized during rebalancing. Thus, quantos form another class of assets where the nonnegligibility of second-order sensitivities leads to dependence of the asset price on variances and covariances.  

# 10.5.5 PRACTICAL CONSIDERATIONS  

At first glance, quanto assets may appear very attractive to investors and portfolio managers. After all, a contract on foreign assets is purchased and all currency risk is eliminated. Does this mean we should always quanto?  

Here again, some real-life complications are associated with the instrument. First of all, the pur-. chase of a quanto may involve an upfront payment and the quanto characteristics depend on risk premia, bid-ask spreads, and on transaction costs associated with the underlying asset and the. underlying foreign currency. These may be high and an approximate hedge using foreign currency forwards may be cheaper in the end.  

Second, quanto assets have expiration dates. If, for some unforeseen reason, the contract is unwound before expiration, further costs may be involved. More important, if the foreign asset is held beyond the expiration date, the quanto feature would no longer be in effect..  

Finally, the quanto contract depends on the correlation between two risk factors, and this corre-. lation may be unstable. Under these conditions, the parties that are long or short the quanto have exposure to changes in this correlation parameter. This may significantly affect the mark-to-market value of the quanto contracts.  
