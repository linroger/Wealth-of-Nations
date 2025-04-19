---
tags:
  - bond_futures
  - conversion_factors
  - ctd_bond
  - deliverable_basket
  - squeeze_risk
aliases:
  - Conversion Factors
  - Delivery Basket
key_concepts:
  - Avoid single security risk
  - Bond futures liquidity
  - Conversion factor function
  - Deliverable basket benefits
  - Squeeze risk mitigation
---

# 11.7 MOTIVATIONS FOR A DELIVERY BASKET AND CONVERSION FACTORS  

Historically, the design of bond futures contracts purposely avoided a single underlying security. One reason is to ensure that the liquidity of the futures contract does not depend on the liquidity of a single, underlying bond, which might lose its liquidity for idiosyncratic reasons, for example, through being accumulated by a few large, buy-and-hold investors. A second reason is to avoid losing liquidity to the threat of a squeeze. A trader squeezes a contract by simultaneously buying many contracts and a large fraction of the. deliverable bond, hoping to sell the position at a profit when traders who had sold contracts - but cannot find bonds to deliver - have to pay up to. buy the deliverable bond or to buy back the contracts from the perpetrator of the squeeze. The threat of a squeeze, which makes shorts hesitant to take. positions, can prevent a contract from attracting volume and liquidity..  

A deliverable basket avoids the problems of a single deliverable so long as some bonds can be delivered at a cost not too much greater than the cost of delivering the CTD. In Table 11.7, delivering the 2.875s of 08/15/2028 is about 91 cents per 100 face amount more costly than delivering the CTD, and the 1.250s of 04/30/2028 are about 18 cents more costly than that. The relatively inexpensive substitutability of these near CTD bonds limits the profit potential of a squeeze. After going to all the trouble, expense, and risk of buying many contracts and a large fraction of the outstanding CTD bonds, shorts would refuse to pay a premium of more than about 100 cents per 100 face amount of the CTD, because the two bonds just mentioned can be delivered instead.  

Limiting the costs of delivery of at least some bonds other than the CTD. is accomplished by conversion factors. In Table 11.7, the costs of delivering. the five bonds with the lowest costs of delivery range from about zero to. 1.65. This range would be a lot wider, however, if there were no conversion factors, or, more precisely, if all conversion factors were implicitly equal to 1.0. In that case, sellers would receive the futures price for delivering any. bond; would choose to deliver the bond with the lowest price; and, there-. fore, the market futures price would equal that lowest price. Referring back to Table 11.7, the CTD bond would be the 0.625s of $08/15/2030$ ,which has the lowest price of about 94.65, and the futures price would be 94.65. Furthermore, the five lowest bond prices, which range from that 94.65 to the 101.14 price of the 1.25s of 04/30/2028, would imply costs of delivery that range from zero to. $101.14-94.65\$ or 6.49, which is a lot wider than. the range with the conversion factors of TYU1..  

Conversion factors reduce the difference in delivery costs by adjusting delivery prices for the differences across bond coupon rates. Given the limited maturity range of bonds deliverable into TYU1, a major determinant of the price differences across bonds is coupon rate. The most expensive bond in Table 11.7 is the bond with the highest coupon, the 3.125s of 11/15/2028, with a price of 113.77. The least expensive deliverable bond is one of the bonds with the lowest coupon, the 0.625s of 8/15/2030, with a price of 94.65. Conversion factors essentially recognize that sellers are delivering expensive, high-coupon bonds rather than inexpensive, low-coupon bonds. For example, the conversion factor of the 3.125s of 11/15/2028 is 0.8376, while the conversion factor of the 0.625s of 08/15/2030 is 0.6382. A glance at the table reveals that bonds with higher coupons tend to have higher conversion factors.  

Conversion factors are computed by the exchange and are easily available. The basic idea can be explained most simply, however, with the fol-. lowing approximation: the conversion factor of a bond equals its price, per. dollar face amount, at a yield equal to the notional coupon rate, for set-. tlement on the last delivery date. At present, the notional coupon for US. Treasury futures is $6\%$ . Therefore, to take one example, the conversion factor of the 1.25s of $03/13/2028$ deliverable into TYU1 is approximated using the price-yield Equation (3.8) for a face amount of one dollar, at a yield of $6\%$ , and for settlement on 09/30/2021, which leaves 13 remaining coupon payments,6  

$$
\frac{1.25\%}{6\%}\left(1-\frac{1}{\left(1+\frac{6\%}{2}\right)^{13}}\right)+\frac{1}{\left(1+\frac{6\%}{2}\right)^{13}}=0.7474
$$  

This calculation rule clearly assigns higher conversion factors to higher coupon bonds. But the justification for the rule is stronger than that. Assume. that the term structure of yields is actually flat at. $6\%$ . In that case, the conversion factor of each bond equals the market price of one dollar face amount of the bond, and the ratio of the market price (per 100 face amount) to the.  

conversion factor equals 100 for every bond. Furthermore, by the arguments. of the previous section, the futures price is 100; the cost of delivery of each. bond is zero; and all bonds are jointly CTD. In short, if market yields are flat at the notional coupon, conversion factors make every bond as attractive to deliver as any other, thus lessening the dependence of the contract's liquidity. on the liquidity of any one bond and also reducing, if not eliminating, the potential profits of a squeeze.  

Because the yield curve is not flat at the notional coupon rate, however, conversion factors limit but do not eliminate differences in the costs of delivery across bonds, as evident from Table 11.7. The resulting emergence of a unique CTD is the subject of the next section.  
