---
tags:
  - bond_convexity
  - bond_pricing
  - duration
  - dv01
  - interest_rate_risk
aliases:
  - convexity measure
  - positive convexity
  - price-rate curve
key_concepts:
  - DV01 falling as rates
  - bond price sensitivity
  - convex shape of curve
  - first-order approximation
  - second derivative of price
---

# 4.5 CONVEXITY  

As can be seen from the tangent lines in Figure 4.3, the interest rate sensitivity. of a bond falls as rates increase. Making this point more directly, Figure 4.4. graphs the DV01 of the Treasury 1.625s of 11/15/2050, a 29.5-year bond,. and of the Treasury 1.625s of 05/15/2026, a five-year bond. DV01 falls as rates increase, but the rate of decline is much faster for the 29.5-year bond than for the five-year bond..  

A curve is said to have a convex shape if a line connecting two points on that curve lies above the curve. The price-rate curves of coupon bonds are convex, and Figure 4.3 makes it clear that the convex shape of the price-rate curve is tantamount to DV01 falling as rates increase. For this reason, the relationship between Dv01 and the level of rates is called convexity. The property of Dv01 falling as rates increase is called positive convexity, while the property of DV01 rising as rates increase is called negative convexity.  

![](b815bd57cf7b57014f394961d8115e25471971368fe4b371cf3f19656cc4ebd5.jpg)  
FIGURE 4.4 DV01s of the Treasury 1.625s of 11/15/2050 and of the Treasury 1.625s of 05/15/2026, as of Mid-May 2021.  

Mathematically, convexity, $C$ , is defined as,.  

$$
C={\frac{1}{P}}{\frac{d^{2}P}{d y^{2}}}
$$  

the second derivative of the price-rate function divided by price. To summarize, all of these statements are equivalent: the price-rate curve is convex; its second derivative is positive; its first derivative becomes less negative as rates increase; and its DV01 falls as rates increase.  

Table 4.4 calculates the convexity of the NSC bond and of the two Treasury bonds as of mid-May 2021. For each bond, three prices are given: the current market price, the price after the 30-year par rate falls by one basis point, and the price after the 30-year par rate rises by one basis point. Then, two first derivatives, or slopes, are computed for each bond. These slopes are computed just as in Equation (4.1), but the slopes here are centered around the 30-year par rate plus and minus 0.5 basis points.  

The final step in Table 4.4 is to estimate the convexity as defined in Equation (4.14). The second derivative centered at the current rate (i.e., a "change" of 0.0) is estimated as the change in the first derivatives from $+0.5$ to $-0.5$ basis points divided by the change in rates of. $+0.5-(-0.5)$ , or 1 basis point. Dividing the result by price gives the estimate of convexity centered at current market levels. For the NSC bond,.  

$$
C={\frac{1}{99.939}}{\frac{-2,399.67-(-2,410.67)}{0.01\%}}=1,101
$$  

TABLE 4.4 Calculating Convexity for Bonds in Table 4.1, as of Mid-May 2021. Rate Changes Are in Basis Points..   


<html><body><table><tr><td>Rate Change</td><td>Price 1st Derivative</td><td>Convexity</td></tr><tr><td></td><td>NSC 4.10s of 05/15/2121</td><td></td></tr><tr><td>-1.0</td><td>100.180067</td><td rowspan="3">1,101</td></tr><tr><td>-0.5</td><td>-2,410.67</td></tr><tr><td>0.0</td><td>99.939000</td></tr><tr><td>0.5</td><td>-2,399.67</td><td></td></tr><tr><td>1.0</td><td>99.699033</td><td></td></tr><tr><td></td><td>Treasury 1.625s of 11/15/2050</td><td></td></tr><tr><td>-1.0 -0.5</td><td>84.589932 -1,993.08</td><td rowspan="3">648</td></tr><tr><td></td><td>84.390624</td></tr><tr><td>0.0</td><td></td></tr><tr><td>0.5 1.0</td><td>-1,987.61</td><td></td></tr><tr><td></td><td>84.191863</td><td></td></tr><tr><td></td><td>Treasury 1.625s of 05/15/2026</td><td></td></tr><tr><td>-1.0</td><td>103.962050 -401.75</td><td rowspan="3">12</td></tr><tr><td>-0.5</td><td></td></tr><tr><td>0.0</td><td>103.921875</td></tr><tr><td>0.5 1.0</td><td>-401.63 103.881712</td><td></td></tr></table></body></html>  

As expected from the curvatures of the price-rate curves in Figure 4.2, the convexity measure is largest for the NsC century bond, smaller for the. 29.5-year Treasury bond, and yet smaller for the five-year Treasury bond.  

Convexity values are not as easily interpreted as Dv01 and duration values, but consider the following. Equation (4.12) showed that the percentage change in a bond's price approximately equals the negative of its duration times the change in rate. However, Appendix A4.2 shows that a better approximation uses both the bond's duration and convexity,  

$$
\frac{\Delta P}{P}\approx-D\Delta y+\frac{1}{2}C\Delta y^{2}
$$  

Because duration appears in the first term of (4.16) and convexity in the sec. ond, using duration alone is called a first-order approximation, while using both duration and convexity is called a second-order approximation.  

Illustrating with the NsC bonds, which have a duration of 24.1 (Table 4.3) and a convexity of 1,101 (Table 4.4), estimates of the percentage  

change in price after rates fall by 100 basis points, or $1\%$ are,  

$$
-24.1\times(-1\%)=24.1\%
$$  

using duration alone, and,  

$$
-24.1\times(-1\%)+0.5\times1,101\times(-1\%)^{2}=29.6\%
$$  

using both duration and convexity. The actual price of the bond after rates decline by 100 basis points is 130.898, which translates into a true percentage price change of (130.898 - 99.939)/99.939, or $30.978\%$ . Therefore, adding the convexity term in Equations (4.16) and (4.18) does result in a more accurate approximation.  

Figure 4.5 makes the same point graphically. The actual price of the NSC bonds is given by the solid curve. The approximation to prices after various changes in rates using just duration or Dv01 is given by the dashed line, which is the same dashed tangent shown in Figure 4.3. And the approximation using both duration and convexity is given by the dotted line. Because both duration and convexity are local estimates, using derivatives at current market levels to estimate prices, both the dashed and dotted lines are less and less accurate as rates move further from current levels. It is clear to the eye, however, that the approximation using both duration and convexity is relatively close to the true price for larger changes in rates than is the approximation using duration alone..  

![](6764869f764af0d056b600e5a13b6125150ca11e3b39241a75bc84b517336845.jpg)  
FIGURE 4.5  Price-Rate Curve of the NSC 4.10s of O5/15/2121, as of Mid-May 2021, with Price Approximations Using Duration and Using both Duration and Convexity.  

Returning now to interpreting convexity numbers, the difference between approximating percentage price change with both duration and convexity [Equation (4.18)] and with duration alone [Equation (4.17)] is the term,  

$$
0.5\times1,101\times(1\%)^{2}=5.5\%
$$  

Therefore, noting that $(1\%)^{2}$ equals one basis point, the correction of. $5.5\%$ in (4.19) is half the convexity divided by 10,000. In other words, for a. $1\%$ change in rates, the second-order correction to the duration approximation of price change is half the convexity divided by 10,000 (i.e., 0.055), or equivalently, the percentage correction is half the convexity divided by 100 (i.e., 5.5).  

The section concludes by noting that the convexity of a portfolio equals the weighted sum of the convexities of its component holdings, where the weights are percentages of portfolio value. The convexity of a portfolio with $25\%$ of its value in the NSC bonds - with a convexity of 1,101 - and $75\%$ of its value in the Treasury 1.625s of $05/15/2026~-$ - with a convexity of 12 - is $25\%\times1,101+75\%\times12=284.25$ Portfolio convexity is a weighted sum, as is portfolio duration, because both metrics divide by price: duration divides the change in price by price, and convexity divides the second derivative divided by price. A formal proof is given in Appendix A4.1.  
