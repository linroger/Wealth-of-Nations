---
tags:
  - bond_pricing
  - ctd_bond
  - duration
  - futures_contract
  - yield_curve
aliases:
  - Cheapest to Deliver
  - Quality Option
  - TYU1
key_concepts:
  - CTD bond determination
  - Conversion factor
  - Deliverable bond price ratio
  - Quality option expiration
  - Term structure of yields
---

# 11.8 THE QUALITY OPTION AT EXPIRATION  

To illustrate how the quality option works at expiration of the futures contract, assume for the moment that the 2.875s of 05/15/2028 and the 1.125s of 02/15/2013 are the only deliverable bonds into TYU1. Figure 11.5 graphs. the ratio of price to conversion factor against yield for these two bonds as of the last trading date, September 21, 2021. The figure assumes that the term structure of yields is flat, that is, that the two bonds have the same yield at the indicated level. At a yield of. $6\%$ , the price-conversion factor ratio of each. of the bonds is about 100: as explained in the previous section, the conversion factor is approximately equal to the price of the bond (per dollar face amount) at a yield of the notional coupon rate - here. $6\%-a s$ of the last delivery date (which is only a few days different from the last trading date).. Hence, the ratio of each bond's price (per 100 face amount) to its conversion factor is about 100. Furthermore, the futures price is 100, the costs of delivering either bond is zero, and the two bonds are jointly CTD.  

As rates move away from $6\%$ , however, the costs of delivering the two bonds diverge. Conversion factors are fixed to equate the price-conversion. factor ratio of the two bonds at a yield of $6\%$ . But as yields fall below $6\%$ , the price and price-conversion factor ratio of the shorter-maturity. and shorter-duration 2.875s of 05/15/2028 increase more slowly than the price and price-conversion factor ratio of the longer-maturity and longer-duration 1.125s of 02/15/2031. Therefore, for yields below. $6\%$ , the 2.875s of 05/15/2028 are CTD. On the other hand, as yields rise above $6\%$ , the price-conversion factor ratio of the longer-duration 1.125s of 02/15/2031 falls more quickly, and that bond is CTD.  

The futures price equals the lowest price-conversion factor ratio across deliverable bonds. Graphically, in the present example, the price of TYU1 is the minimum or lower envelope of the two price-conversion factor curves, depicted in Figure 11.5 by a semi-transparent, gray band. At expiration, the futures price tracks the price of the low-duration bond when rates are low and the price of the high-duration bond when rates are high.  

![](0955e3004faf5b9315b4f05c07de13f4ecd9ed33e2418edbcd2fa616c517ca58.jpg)  
FIGURE 11.5 Quality Option for TYU1 with a Flat Term Structure of Yields, as of the Last Trading Date.  

Figure 11.5 is stylized in two ways. First, because there are many deliverable bonds, several distinct ranges of yield at expiration might each determine a different CTD. Along the lines of the discussion here, however, the deliverable bond with the shortest duration is typically CTD at the lowest range of yields; deliverable bonds with intermediate durations might be CTD at intermediate ranges of yield; and the deliverable bond with the longest duration is typically CTD at the highest range of yields.  

The second way Figure 11.5 is stylized is in assuming that the yields of. the two bonds are equal and move up or down in parallel. In reality, the term structure of interest rates and individual bond yields can move in many. ways that affect the determination of the CTD. Most generally, a bond is more likely to be CTD after any change that cheapens it relative to other bonds in the deliverable basket. If the term structure flattens, shorter-term bonds are more likely to be CTD. If the term structure steepens, longer-term. bonds are more likely to be CTD. And if the yield of any bond increases idiosyncratically relative to yields of other deliverable bonds, that bond is more likely to be CTD.  
