---
tags:
  - bond_pricing
  - bond_yields
  - hqm_curve
  - interest_rate_risk
  - price_rate_curves
  - treasury_bonds
aliases:
  - Bond Sensitivity
  - HQM Curve
  - Price-Rate Curve
key_concepts:
  - 30-year par rate
  - Bond price sensitivity
  - Bond yield spreads
  - HQM par rate curve
  - Interest rate risk metrics
---

# 4.1 PRICE-RATE CURVES  

The three bonds in Table 4.1 are used in this and subsequent sections to illustrate concepts. First, the Norfolk Southern Company (NsC) issued $\$600$ million of the 4.10s of 05/15/2121 in May 2021 with a maturity of 100 years. Sales of century bonds are rare, but, with rates at historically low levels, bonds with very long maturities are being issued more often. The second and third bonds are the US Treasury $1.625s$ of 05/15/2026, issued in May 2016 with a bit less than $\$70$ billion outstanding, and the 1.625s of 11/15/2050, issued in May 2020 with about $\$86$ billion outstanding. The yields of these three bonds as of mid-May 2021 are given in the table, along with their spreads to the High-Quality Market-Weighted (HQM) corporate bond yield curve. The HQM curve, published by the US Treasury, is designed to be representative of corporate bonds rated A or above and is intended for use by pension funds in computing the present value of their liabilities.  

As discussed in the introduction, a "change" in rates has to be defined. in order to compute interest rate risk metrics. For current purposes, the fol-. lowing assumptions are made. First, the base curve is the HQM par rate curve. Second, the spreads of the NSC and US Treasury bonds relative to the HQM curve, as listed in Table 4.1, do not change as the HQM curve changes. Third, the change in the HQM par rate of any term is a fixed proportion of. the change in the 30-year par rate. For example, if the 30-year par rate moves up by one basis point, the 10-year rate moves up by 0.99 basis points; the five-year rate by 0.80 basis points; the two-year rate by 0.37 basis points.. These proportions are meant to capture the broad empirical fact, discussed further in Chapter 6, that short-term rates are less volatile than long-term rates. Figure 4.1 graphs the assumed shifts to the HQM par curve, which,. for visibility, are scaled to a change of plus or minus 50-basis points in the 30-year par rate. It can easily be seen that, as intended, short-term rates move. by less than long-term rates, and that the shift is close to a parallel shift for. terms greater than 10 years.  

TABLE 4.1  Selected Bonds with Indicative Levels as of Mid-May 2021. Spreads. Are Versus Par Rates from the High-Quality Market-Weighted Corporate Bond Curve, as of May 2021. Coupons and Yields Are in Percent. Spreads Are in Basis Points.   


<html><body><table><tr><td>Issuer</td><td>Coupon</td><td>Maturity</td><td></td><td>Spread</td></tr><tr><td>Norfolk Southern Company</td><td>4.10</td><td>05/15/2121</td><td>4.103</td><td>66</td></tr><tr><td>US Treasury</td><td>1.625</td><td>05/15/2026</td><td>0.823</td><td>-41</td></tr><tr><td>US Treasury</td><td>1.625</td><td>11/15/2050</td><td>2.363</td><td>-97</td></tr></table></body></html>  

Equipped with these assumptions, the prices of the bonds in Table 4.1 can be computed after the 30-year HQM par rate changes by, say, one basis point. More specifically: i) given the one-basis-point change in the 30-year par rate, calculate the change in par rates of all other terms along the lines of the previous paragraph; ii) for each bond, add its spread to the shifted par rates; ii) for each bond, convert the shifted par plus spread curve into discount factors; and iv) reprice each bond..  

Figure 4.2 shows the results of these calculations. The horizontal axis gives changes in the 30-year HQM par rate, and the vertical axis gives corresponding bond prices. Note that each rate change is assumed to be instantaneous; that is, no time passes as the rate changes from its current to its new level. In any case, as expected, prices increase as rates fall and decrease as rates rise. But the figure also shows that the three bonds do not have the same sensitivity to changes in rates. The price of the Treasury 1.625s of 05/15/2026, which has five years remaining to maturity, declines relatively mildly as rates increase; that is, its price is least sensitive to changes in rates. By the same token, the price of the Treasury 1.625s of 11/15/2050, which matures in 29.5 years, is more sensitive to rates, and the NSC century. bond is the most sensitive of all. These differences in price sensitivities are quantified in the next sections as differences in Dv01 or duration. Finally, the figure shows that the five-year Treasury price-rate curve is not far from a line, whereas the price-rate curve of the 29.5-year Treasury, and even more so of the NsC century bond, have noticeable curvature. These differences are quantified in subsequent sections as differences in convexity.  

![](7b3aa6c3a5824df27fdf1d6112b1fb39c6836b63ce7a477b570c1f37d8306a9b.jpg)  
FIGURE 4.1 Sample Shifts to HQM Par Rates.  

![](223c7f5d68cda32e73b71ba8bc0793649feee9fa87c4c91701a221baa10d2ad6.jpg)  
FIGURE 4.2 Price-Rate Curves for the Bonds in Table 4.1, as of Mid-May 2021.  
