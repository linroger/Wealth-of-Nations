---
tags:
  - arbitrage
  - bond_pricing
  - cheapest_to_deliver
  - cost_of_delivery
  - futures_contract
aliases:
  - CTD
  - Final Settlement Price
  - TYU1
key_concepts:
  - Arbitrage opportunities
  - Cheapest-to-deliver bond
  - Cost of delivery
  - Deliverable basket bonds
  - Futures price at expiration
---

# 11.6 COST OF DELIVERY AND THE FINAL SETTLEMENT PRICE  

The cost of delivery measures how much it costs a short to fulfill the commitment to deliver a bond through a futures contract. Having decided to deliver bond $i.$ the short first has to buy the bond at its market price plus accrued interest and then deliver it through the futures contract for the futures price times the conversion factor plus accrued interest. Denoting the time- $t$ flat price of bond $i$ at time $t$ by $\boldsymbol{p}_{t}^{i}$ ; its accrued interest by $A I_{t}^{i}$ ; its conversion factor by $c f^{i}$ ; and the futures price by. $F_{t}$ , the cost of delivery is,.  

$$
p_{t}^{i}+A I_{t}^{i}-(c f^{i}\times F_{t}+A I_{t}^{i})=p_{t}^{i}-c f^{i}\times F_{t}
$$  

IABLE 11.7 Prices of TYU1 and Notes in Its Deliverable Basket as of the Last Trading Date, September 21, 2021.   


<html><body><table><tr><td>TYU1 Price: 133.85938</td><td></td><td colspan="4"></td></tr><tr><td>Coupon</td><td>Maturity</td><td>Conversion Factor</td><td>Price</td><td>Cost of Delivery</td><td>Price / Conv. Fac.</td></tr><tr><td>2.875</td><td>05/15/2028</td><td>0.8338</td><td>111.61719</td><td>0.00524</td><td>133.86566</td></tr><tr><td>2.875</td><td>08/15/2028</td><td>0.8286</td><td>111.82813</td><td>0.91225</td><td>134.96032</td></tr><tr><td>1.250</td><td>04/30/2028</td><td>0.7474</td><td>101.14063</td><td>1.09413</td><td>135.32329</td></tr><tr><td>1.250</td><td>03/31/2028</td><td>0.7474</td><td>101.17969</td><td>1.13319</td><td>135.37555</td></tr><tr><td>3.125</td><td>11/15/2028</td><td>0.8376</td><td>113.76563</td><td>1.64501</td><td>135.82333</td></tr><tr><td>2.625</td><td>02/15/2029</td><td>0.8039</td><td>110.50000</td><td>2.89045</td><td>137.45491</td></tr><tr><td>2.375</td><td>05/15/2029</td><td>0.7836</td><td>108.82813</td><td>3.93592</td><td>138.88224</td></tr><tr><td>1.625</td><td>08/15/2029</td><td>0.7320</td><td>103.34375</td><td>5.35869</td><td>141.17999</td></tr><tr><td>1.750</td><td>11/15/2029</td><td>0.7331</td><td>104.33594</td><td>6.20363</td><td>142.32156</td></tr><tr><td>1.500</td><td>02/15/2030</td><td>0.7105</td><td>102.20313</td><td>7.09604</td><td>143.84676</td></tr><tr><td>0.625</td><td>05/15/2030</td><td>0.6462</td><td>94.89063</td><td>8.39070</td><td>146.84405</td></tr><tr><td>0.625</td><td>08/15/2030</td><td>0.6382</td><td>94.64844</td><td>9.21938</td><td>148.30529</td></tr><tr><td>0.875</td><td>11/15/2030</td><td>0.6476</td><td>96.57031</td><td>9.88298</td><td>149.12031</td></tr><tr><td>1.125</td><td>02/15/2031</td><td>0.6577</td><td>98.58594</td><td>10.54663</td><td>149.89499</td></tr></table></body></html>  

The short will choose which bond to deliver to minimize the cost of delivery.. The bond that minimizes the cost of delivery is called the cheapest-to-deliver,. or the CTD. Table 11.7 shows the price of TYU1, the prices of the bonds in. its deliverable basket, and the costs of delivery for each of those bonds, as of the last trading date, September 21, 2021. For example, the cost of delivery. of the 2.875s of 05/15/2028 is,  

$$
111.61719-0.8338\times133.85938=0.00524
$$  

Because this is the lowest cost of delivery in the table, these bonds are CTD into TYU1.  

To focus on the quality option, assume for the moment that date. $T$ is both the last trading date and the last delivery date. Arbitrage arguments can then be used to show that,.  

$$
\boldsymbol{p}_{T}^{C T D}-\boldsymbol{c}\boldsymbol{f}^{C T D}\times\boldsymbol{F}_{T}=\boldsymbol{0}
$$  

and,  

$$
F_{T}={\frac{{p_{T}^{\mathrm C T D}}}{c f^{\mathrm C T D}}}\leq{\frac{{p_{T}^{i}}}{c f^{i}}}
$$  

Equation (11.7) says that the cost of delivery of the CTD at expiration is zero. Equation (11.8) says that the futures price at expiration, that is, the last settlement price, equals the ratio of the price of the CTD bond to its conversion factor and that this ratio is less than or equal to the ratios of all. other bond prices to their conversion factors. These theoretical predictions are extremely good approximations for TYU1 as of its last trading date, as can be seen from Table 11.7. The cost of delivery of the CTD is very close to zero; the ratio of its price to its conversion factor very nearly equals the. futures price; and the ratio of all other bond prices to their CTDs are larger.. This section concludes with the arbitrage proofs of Equations (11.7) and (11.8).  

Say that (11.7) is not true, and that, instead, $F_{T}>p^{C T D}/c f^{C T D}$ . In that case, an arbitrageur could buy the CTD, sell the futures, and deliver the CTD, earning a profit of,  

$$
c f^{C T D}\times F_{T}-p_{T}^{C T D}
$$  

which is positive by the starting assumption that $F_{T}>p^{C T D}/c f^{C T D}$ . Hence, ruling out market prices that admit riskless arbitrage opportunities rules out this assumed pricing relationship. Next, assume that $\bar{F_{T}}<p^{C T D}/c f^{C T D}$ . In this case, an arbitrageur could sell the CTD, buy the futures, and take delivery of the bond delivered by the short. If the short delivers the CTD, then the arbitrageur's profit is,  

$$
\boldsymbol{p}_{T}^{C T D}-\boldsymbol{c}\boldsymbol{f}^{C T D}\times\boldsymbol{F}_{T}
$$  

which is positive by the starting assumption that $F_{T}<p^{C T D}/c f^{C T D}$ . If the short delivers some other bond. $i$ , the trader buys back the CTD just sold and sells bond $i$ instead, for a total profit of,.  

$$
p_{T}^{i}-c f^{i}\times F_{T}\ge p_{T}^{C T D}-c f^{C T D}\times F_{T}>0
$$  

where the first inequality follows from the definition of the CTD - the cost of delivering any bond other than the CTD is at least as great as the cost of delivering the CTD - and the second inequality follows from the starting assumption that $F_{T}<p^{C T D}/c f^{C T D}$ . Hence, the arbitrageur's profit is even greater if the short (suboptimally) delivers a bond other than the CTD. But if the arbitrageur's profit is positive for whatever bond the short delivers, then the assumption $F_{T}<\hat{p^{C T D}}/c f^{C T D}$ is ruled out as admitting riskless arbitrage opportunities. Finally, ruling out both $F_{T}>p^{C T D}/c f^{C T D}$ and $F_{T}<$ $\boldsymbol{p}^{C T D}/\bar{c}\boldsymbol{f}^{C T\bar{D}}$ proves the equality in (11.8) and (11.7). The inequality of (11.8) follows from combining (11.7) with the condition that the CTD has the  

lowest cost of delivery,  

$$
\begin{array}{c}{{\displaystyle p_{T}^{i}-c f^{i}\times F_{T}\geq{p_{T}^{C T D}}-c f^{C T D}\times F_{T}=0}}\ {{\displaystyle p_{T}^{i}-c f^{i}\times F_{T}\geq0}}\ {{F_{T}\leq\displaystyle\frac{p_{T}^{i}}{c f^{i}}}}\end{array}
$$  
