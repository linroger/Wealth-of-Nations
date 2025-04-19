---
tags:
  - bond_yield
  - dv01
  - forward_contract
  - forward_yield
  - interest_rate_sensitivity
  - repo_rate
aliases:
  - Bond Yield
  - Forward Bond Yield
  - Forward Price
key_concepts:
  - bond's cash flows
  - forward settlement
  - interest rate sensitivity
  - repo rate
  - spot yield
---

# 11.2 FORWARD BOND YIELD  

As covered in Chapter 3, the yield to maturity of a bond is the single rate such that discounting the bond's cash flows at that rate, from spot settlement to maturity, gives the bond's (full) market price. The forward yield of a bond is defined analogously as the single rate such that discounting the bond's cash flows from forward settlement to maturity by that rate gives the bond's (full) forward price.  

Figure 11.4 diagrams the relationship between the spot yield, the repo. rate, and the forward yield, and Table 11.3 reports the spot and forward yields of the 2.875s of 05/15/2028 and the 1.125s of 02/15/2031, which are computed using Equation (A3.5) and the data given in the tables of previous section. As explained in that section, when the coupon rate exceeds the repo rate, market prices align such that investors are indifferent between i) buying a bond at its spot price, and ii) investing in repo to the forward date and buying the bond at its lower, forward price. Figure 11.4 and Table 11.3 make the same point in terms of yield: investors are indifferent between i) investing at the spot yield, and ii) investing in repo to the forward date and then at the higher, forward yield. Put another way, the spot yield is a complex weighted average of the relatively low repo rate and the relatively high forward yield, where the weights reflect the lengths of the relative holding. periods, as indicated in Figure 11.4..  

![](6e34b70f551ec7cacfae9b16b71e4992734c72065c60b6297b973dbac0c43bad.jpg)  

TABLE 11.3  Spot and Forward Yields for the US Treasury 2.875s of 05/15/2028 and 1.125s of 02/15/2031, as of May 14, 2021, for Spot Settlement on May 17, 2021, and for Forward Settlement on September 30, 2021. The Repo Rate is $0.015\%$ . Yields Are in Percent.   


<html><body><table><tr><td>Bond</td><td></td><td>Forward Yield</td></tr><tr><td>2.875sof05/15/2028</td><td>1.260</td><td>1.337</td></tr><tr><td>1.125s of 02/15/2031</td><td>1.625</td><td>1.693</td></tr></table></body></html>  

# 11.3THE INTEREST RATE SENSITIVITY OF A FORWARD CONTRACT  

What is the interest rate sensitivity or Dv01 of a forward contract? With respect to DV01, and with reference to Figure 11.4, should DV01 be computed by shifting the spot yield, the forward yield, the repo rate, or some combination of the three? Table 11.4 shows the Dv01s of the forward contracts in the examples of this chapter with respect to each of these rates. To compute the DV01 with respect to the spot yield, shift the spot yield down one basis point; calculate a new spot price; calculate a new forward price using the new spot price; and take the difference between the new and original forward prices. To compute the Dv01 with respect to the forward yield, shift the forward yield down by one basis point; compute a new forward price using the new forward yield; and take the difference between the new and original forward prices. Finally, to compute the DV01 with respect to the repo rate, shift the repo rate down by one basis point; compute a new forward price using the new repo rate; and take the difference between the new and original forward prices.  

TABLE 11.4 DV01 Metrics for the Forward Prices of. the US Treasury 2.875s of 05/15/2028 and 1.125s of 02/15/2031, as of May 14, 2021, for Spot Settlement on May 17, 2021, and Forward Settlement on. September 30, 2021. The Repo Rate Is $0.015\%$   


<html><body><table><tr><td colspan="2">2.875sof05/15/2028</td></tr><tr><td>Yield or Rate Shifted</td><td>DV01</td></tr><tr><td>Spot Yield Forward Yield</td><td>0.0708</td></tr><tr><td>Repo Rate</td><td>0.0666 -0.0042</td></tr><tr><td>1.125s of 02/15/2031</td><td></td></tr><tr><td>Yield orRateShifted</td><td>DV01</td></tr><tr><td>Spot Yield</td><td>0.0876</td></tr><tr><td>Forward Yield</td><td>0.0841</td></tr><tr><td>Repo Rate</td><td>-0.0036</td></tr></table></body></html>  

The Dv01s of the two bonds with respect to the spot yields are consistent with their respective maturities of 7.0 and 9.75 years. The DV01s with respect to the repo rates are negative and small. They are negative,. because - from the determination of the forward price in Equation (11.1), (11.2) or (11.3) - the forward price increases as the repo rate increases. And they are small, because the term of the underlying repo between the spot. and forward settlement dates is 136 days, or a bit more than 0.37 years. Finally, the Dv01s with respect to the forward yields can be understood as follows. A long forward position is equivalent to a long spot position and a short - borrowing cash - repo position. Therefore, the DV01 with respect to the forward yield is the sum of the (positive) DV01 with respect to the spot rate and the (negative) DV01 with respect to the repo rate..  

Return now to the question of which of these Dv01s should be used, keeping Figure 11.4 in mind. If the spot yield changes while the repo rate is constant, then a shift of the spot yield curve makes sense. If the spot. yield and repo rate change together, by the same amount, then a shift of the forward yield makes sense. Taking this thinking a step further, some. practitioners - recognizing the empirical regularity that longer-term rates. are more volatile than shorter-term repo rates - assume that the repo rate. changes by a fixed percentage of the spot yield change. At a percentage of $30\%$ , for example, the Dv01 of the forward contract is estimated as $30\%$ times the (negative) DV01 with respect to the repo rate plus the (positive) DV01 with respect to the spot yield, which comes to 0.0695 for the forward on the 2.875s of 05/15/2028 and 0.0865 for the forward on the 1.125s of 02/15/2031. Varying this percentage from $0\%$ to $100\%$ , of course, gives estimates ranging from the DV01s given in Table 11.4 with respect to the spot yields to those with respect to the forward yields, respectively. The best approach, however, is to accept that the repo rate and long-term yields can move independently and, therefore, to hedge in a two-factor framework.. Repo rate exposure should be hedged with other short-term, fixed income instruments, and forward yield exposure should be hedged with longer-term instruments.  
