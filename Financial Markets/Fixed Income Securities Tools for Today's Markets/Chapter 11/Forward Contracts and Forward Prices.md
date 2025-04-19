---
tags:
  - arbitrage
  - bond_contract
  - forward_contracts
  - forward_prices
  - repo_rate
  - treasury_bonds
aliases:
  - Forward agreement
  - Forward bond contract
  - Forward price
key_concepts:
  - Arbitrage arguments
  - Forward bond contract
  - Forward price definition
  - Invoice price
  - Repo rate
---

# 11.1 FORWARD CONTRACTS AND FORWARD PRICES  

In a forward bond contract, the counterparties agree on a price at which to trade a bond at some time in the future. Consider a forward contract, traded on May 14, 2021, to purchase $\$100,000$ face amount of the US Treasury. 2.875s of $05/15/2028$ for 109.72 on September 30, 2021. In this example,. the initiation or trade date is May 14, 2021; the underlying security is the.  

TABLE 11.1 A Forward Contract on the US Treasury 2.875s of 05/15/2028.   


<html><body><table><tr><td>UnderlyingSecurity</td><td>2.875sof05/15/2028</td></tr><tr><td>Principal Amount</td><td>$100,000</td></tr><tr><td>TradeDate</td><td>05/14/2021</td></tr><tr><td>SpotSettlementDate</td><td>05/17/2021</td></tr><tr><td>Spot Price</td><td>110.77344</td></tr><tr><td>Accrued Interest, Spot Settlement (2/184 days)</td><td>0.01562</td></tr><tr><td>Forward Settlement Date</td><td>09/30/2021</td></tr><tr><td>Accrued Interest, Forward Settlement (138/184 days)</td><td>1.07813</td></tr><tr><td>RepoRate toForward SettlementDate</td><td>0.015%</td></tr><tr><td>Days from Spot to Forward Settlement</td><td>136</td></tr><tr><td>ForwardPrice</td><td>109.71721</td></tr></table></body></html>  

2.875s of 05/15/2028; the forward date, expiration date, delivery date, or maturity date is September 30, 2021; and the forward price is 109.72. The counterparty committing to purchase the bond on the forward date is the buyer of the contract and is long the forward, while the counterparty on the other side is the seller of the contract and is short the forward. Table 11.1 summarizes the terms of this forward trade and gives other data that are used presently.  

By definition, the forward price is such that the buyer and seller are. willing to enter into the forward agreement without any exchange of cash. This implies that the initial value of the forward contract is zero. Over time,. however, the value of the forward position may rise or fall. Continuing with the example, say that, just after the agreement was struck, the market forward price increases to 110. The contract to buy the bond at 109.72 now. has positive value to the buyer and negative value to the seller. The buyer could immediately sell the bond through a new forward contract at 110,. which makes the contract worth 110 - 109.72, or 0.28, as of 09/30/2021, or the present value of 0.28 as of today. The seller of the original contract,. however, having locked in a forward price of 109.72, would have to pay the buyer to exit the contract. In any case, note that the "value of a forward contract" denotes the value of an existing contract under current market. conditions, while the "forward price" denotes the price at which the underlying bond is to be traded on the forward date.2.  

![](b8b911dfad7c6e4ba43bbce2e581407474ea88428ea3966cd0bd31131ec372e4.jpg)  
FIGURE 11.2 A Forward Contract on the US Treasury 2.875s of 05/15/2028.  

Forward bond prices can be determined by arbitrage arguments. To demonstrate, consider the following strategy in the context of the example, using the data in Table 11.1 and referring to the timeline in Figure 11.2:  

On May 14, 2021:  

Buy $\$100,000$ face amount of the 2.875s of $05/15/2028$ for 110.77344 plus accrued interest of 0.01562, for settlement on May 17, 2021, for an invoice price of 110.78906 and a dollar invoice of $\$110,789.06$   
Sell the repo to the forward date, that is, borrow $\$110,789.06$ from May 17, 2021, to September 30, 2021, at the repo rate of $0.015\%$ , and post the 2.875s of 05/15/2028 as collateral.   
Note: no cash is generated or required on this date. On September 30, 2021:   
Repay the repo loan, now grown to $110,789.06\times(1+0.015\%\times$ $136/360)=\$110$ 795.34.   
Take back the $\$100,000$ face amount of the 2.875s of 05/15/2028.   
Note: the bonds have effectively been purchased at a full price of 110.79534, which, after subtracting the accrued interest of 1.07813 as of this date, equates to a flat price of 109.71721.  

This strategy buys the bond and sells the repo, which establishes a posi-. tion equivalent to a long forward and, therefore, is called a synthetic forward position: there is no cash flow on the trade date and the bond is effectively purchased on the forward date. By arbitrage, therefore, the forward price, that is, the price at which the bond is bought through the forward contract,. must equal the price at which the bond is bought through this synthetic. forward, that is, 109.71721. More formally, if the forward price,. $F$ were greater than 109.71721, an arbitrageur could sell the forward at $F$ and buy the bond forward through the strategy at 109.71721, thus locking in a riskless profit of $F-109.7172$ as the forward date. Similarly, if $F$ were less than 109.71721, the arbitrageur could buy the forward and sell the bond forward through the strategy to lock in a riskless profit of $109.71721-F$ Hence, the only forward price consistent with no arbitrage opportunities is $=109.71721$  

Algebraically, the full forward price can be written as,  

$$
109.71721+1.07813=(110.77344+0.01562)\left(1+{\frac{0.015\%\times136}{360}}\right)
$$  

In words, the full forward price equals the future value of the full spot price to the forward delivery date at the bond's repo rate..  

The derivation of the arbitrage-free forward price requires an extra step when there is an intermediate coupon payment, that is, a coupon payment between the spot and forward settlement dates. To illustrate, consider a forward contract on the 1.125s of 02/15/2031 over the same dates as the previous example, except, of course, the coupon payment dates differ. Table 11.2 and Figure 11.3 give the data for this example.  

To replicate this long forward contract, implement the following strategy:  

On May 14, 2021:  

Buy $\$100,000$ face amount of the 1.125s of $02/15/2031$ for 95.50781 plus accrued interest of 0.28280, for settlement on May 17, 2021, for an invoice price of 95.79061 and a dollar invoice of $\$95,790.61$ Sell the repo to the forward date, that is, borrow. $\$95,790.61$ from May 17, 2021, to September 30, 2021, at the repo rate of $0.015\%$ , and post the 1.125s of 02/15/2031 as collateral.  

TABLE 11.2  A Forward Contract on the US Treasury 1.125s of 02/15/2031.   


<html><body><table><tr><td>UnderlyingSecurity</td><td>1.125sof02/15/2031</td></tr><tr><td>Principal Amount</td><td>$100,000</td></tr><tr><td>Trade Date</td><td>05/14/2021</td></tr><tr><td>SpotSettlement Date</td><td>05/17/2021</td></tr><tr><td>SpotPrice</td><td>95.50781</td></tr><tr><td>Accrued Interest, Spot Settlement (91/181 days)</td><td>0.28280</td></tr><tr><td>Forward Settlement Date</td><td>09/30/2021</td></tr><tr><td>Accrued Interest, Forward Settlement (46/184 days)</td><td>0.14063</td></tr><tr><td>Repo Rate to Forward Settlement Date</td><td>0.015%</td></tr><tr><td>Days from Spot to Forward Settlement</td><td>136</td></tr><tr><td>ForwardPrice</td><td>95.09290</td></tr></table></body></html>  

<html><body><table><tr><td colspan="2">181days(02/15to08/15)</td><td colspan="2">184days (08/15/21to02/15/22) CouponDate</td><td rowspan="2">CouponDate 02/15/22</td></tr><tr><td colspan="2">CouponDate 02/15/21</td><td colspan="2">08/15/21</td></tr><tr><td></td><td>136days(5/17tb9/30)</td><td></td><td></td><td></td></tr><tr><td rowspan="3">91days</td><td>90days (02/15 to05/17） (05/17to08/15)(08/15to</td><td>46days</td><td></td><td rowspan="3"></td></tr><tr><td></td><td>09/30)</td><td></td></tr><tr><td>TradeSpot</td><td></td><td>Forward</td></tr><tr><td>Date</td><td>SettlementDate</td><td></td><td>Date</td></tr><tr><td>05/14/21</td><td>05/17/21</td><td></td><td>09/30/21</td></tr></table></body></html>  

Note: no cash is generated or required on this date.  

On August 15, 2021:  

Use the bond's coupon payment of. $\$100,000$ to reduce the repo borrowing. More specifically, over the 90 days from May 17, 2021, to August 15, 2021, the repo loan balance grows to $\$95,790.61(1+0.015\%\times90/360)=\$995$ 794.20.Reducing this balance by the coupon payment leaves a balance of $\$95,231.70$  

Note: no cash is generated or required on this date.  

On September 30, 2021:  

Repay the repo loan, which, over the period August 15, 2021, to September 30, 2021, grows to $95,231.70\times(1+0.015\%\times46/360)=$ $\$95,233,453$  

Take back the $\$100,000$ face amount of the 1.125s of 02/15/2031.  

Note: the bonds have effectively been purchased at a full price of 95.23353, which, subtracting the accrued interest of 0.14063 as of this date, equates to a flat price of 95.09290.  

Algebraically, then, the full forward price of the 1.125s of 02/15/2031, 95.23353 can be written as,  

$$
\begin{array}{c}{95.23353=\left[\left(95.50781+0.28280\right)\left(1+\frac{0.015\%\times90}{360}\right)-\frac{1.125}{2}\right]}\ {\times\left(1+\frac{0.015\%\times46}{360}\right)\qquad(17.25\%)}\end{array}
$$  

Rearranging terms, and noting that the product of two interest rates is typically very small, gives the following approximation,  

$$
{\begin{array}{r l}&{95.23353\approx{\left[(95.50781+0.28280)-{\frac{1.125/2}{\left(1+{\frac{0.015\%\times90}{360}}\right)}}\right]}}\ &{\qquad\times\left(1+{\frac{0.015\%\times136}{360}}\right)}\end{array}}
$$  

In words, in the case of an intermediate coupon, the full forward price approximately equals the future value to the forward date of the full spot price less the present value of the coupon payment. More generally, were there more than one intermediate coupon payment, the full forward price would approximately equal the future value of the full spot price minus the present values of all those intermediate coupons.  

In both of these examples, forward bond prices are less than spot prices: for the 2.875s of 05/15/2028, the forward price of 109.72 is less than the spot price of 110.77, and for the 1.125s of 02/15/2031, the forward price of 95.09 is less than the spot price of 95.51. This relationship is typical and is commonly known as the forward drop.  

To understand the intuition behind the forward drop, imagine that a trader has funds equal to the spot price and wants to own the bond as of the forward date. There are two possible strategies, which, by arbitrage, have to be equally appealing: i) use the funds to buy the bond spot and earn coupon interest to the forward date; and ii) buy the bond forward and invest the funds at the repo rate. If the coupon interest from strategy i) exceeds the repo interest from strategy ii), then the two strategies can be equally appealing only if the forward price is less than the spot price. But coupon interest on bonds typically does exceed the repo rate, because the term structure of interest rates is typically upward sloping. Hence, the forward price is usually less than the spot price, and there is usually a forward drop. Of course, if the repo rate exceeds the coupon rate, the argument reverses, and the forward price exceeds the spot price..  

Consistent with this intuitive discussion, Appendix A11.1 shows that the forward drop of a bond approximately equals the difference between the interest earned on the bond and the cost of financing its purchase from the settlement date to the forward date. Following the terminology of Chapter 3, then, in which this difference is called cash carry, it follows that the forward drop approximately equals cash carry, or, in the jargon of forward and futures markets, simply "carry." This point is illustrated here for these two examples. For the 2.875s of 05/15/2028, the difference between the spot and forward prices is. $110.77344-109.71721$ , or about 1.06. At the same time, because the bond earns an actual/actual. $2.875\%$ semiannual coupon and finances at an actual/360 repo rate of $0.015\%$ , the difference between. the interest earned and the financing cost is about the same: $(2.875/2)\times$ $136/184-0.015\times136/360=1.06$ . For the 1.125s of 02/15/2031, the forward drop is. $95.50781-95.09290$ , or 0.41. The difference between the. coupon interest and financing cost is about the same:. $(1.125/2)\times136/184-$ $0.015\times136/360=0.41$  
