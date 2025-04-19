---
tags:
  - coupon_effect
  - spot_rates
  - term_structure
  - treasury_bonds
  - yield_to_maturity
aliases:
  - Coupon Impact
  - Relative Bond Valuation
key_concepts:
  - Coupon effect explained
  - Spot rates vs. yields
  - US Treasury bond market
  - Upward sloping term structure
  - Yield not relative value
---

# 3.4 YIELD AND RELATIVE VALUE  

This section argues that yield is not a reliable measure of relative value. In. fact, if two bonds have the same maturity but different yields, it is not nec-. essarily true that the bond with a higher yield is a superior investment. To explain this, the discussion turns to the coupon effect, starting with a simple numerical example and finishing with an empirical demonstration from the US Treasury bond market.  

Say that the one-year spot rate is $0\%$ and the two-year spot rate is $10\%$ Using the analytics of Chapter 2 and of this chapter, Table 3.1 gives the prices and yields of three two-year bonds with annual coupons of $0\%$ $5\%$ , and $9.5023\%$  

For example, for the $5\%$ bond,  

$$
\begin{array}{l}{91.7769={\frac{5}{(1+0\%)}}+{\frac{105}{(1+10\%)^{2}}}}\ {={\frac{5}{(1+9.7203\%)}}+{\frac{105}{(1+9.7203\%)^{2}}}}\end{array}
$$  

where Equation (3.11) uses the assumed spot rates to discount cash flows and Equation (3.12) follows from the definition of yield to maturity.  

According to Table 3.1, the yield of the zero coupon bond is. $10\%$ Because this bond makes only one payment at maturity, its market price. can be found by discounting at either the two-year spot rate or at the bond's yield. Hence, those two must be equal at. $10\%$  

TABLE 3.1 Prices and Yields of Two-Year Bonds When the One- and Two-Year Spot Rates are. $0\%$ and $10\%$ Respectively. Coupons and Yields Are in Percent.   


<html><body><table><tr><td>Coupon</td><td>Price</td><td></td></tr><tr><td>0.0000</td><td>82.6446</td><td>10.0000</td></tr><tr><td>5.0000</td><td>91.7769</td><td>9.7203</td></tr><tr><td>9.5023</td><td>100.0000</td><td>9.5023</td></tr></table></body></html>  

The yield of the $5\%$ bond, however, is $9.7203\%$ . Equations (3.11) and (3.12) show that the yield of. $9.7203\%$ has to summarize the term structure of spot rates, or, in other words, that discounting at the yield has to have the same effect as discounting the first cash flow by. $0\%$ and the second by $10\%$ . The result of $9.7203\%$ is between the two spot rates, but a lot closer to. $10\%$ : most of the bond's cash flow comes from the second payment, which includes principal, and that second payment is discounted at $10\%$  

Table 3.1 also reports that the $9.5023\%$ bond, which sells for par, has a yield of $9.5023\%$ . This yield is also between the spot rates of. $0\%$ and $10\%$ and is also a lot closer to $10\%$ but not as close as for the $5\%$ bond. Because the $9.5023\%$ bond pays out relatively more of its value in the first cash flow, its yield is closer to $0\%$ than is the yield of the $5\%$ bond.  

In general, the coupon effect can be summarized as follows: when the term structure of spot rates is upward sloping, bonds with higher coupons, which have more of their value discounted at shorter-term, lower spot rates, have lower yields to maturity. While not part of the discussion here, it is also true that when the term structure of spot rates is downward sloping, bonds with higher coupons have higher yields.  

The coupon effect makes it very clear that spot rates are meant to. describe pricing in a bond market as a whole, while yields are meant to describe the pricing of individual bonds. Furthermore, even though all of the bonds in the table are fairly priced relative to the term structure of spot rates, each bond has a different yield. Put another way, the fact that the $0\%$ bond has the highest yield does not mean that it is the best investment.. The fact that the par bond has the lowest yield does not mean that it is the worst investment.  

Figures 3.2 and 3.3 show the coupon effect at work in the US Treasury. market as of mid-May 2021. Figure 3.2 graphs the yields of all Treasury. coupon bonds against their maturity dates. Some bond yields are clearly off the curve. The four points above the curve with maturities from 2040 to. 2041 are relatively newly issued 20-year bonds. The Treasury stopped issu-. ing new 20-year bonds in 1986 but started to do so again in May 2020. These four bonds, therefore, have coupons that reflect the current, low-rate. environment. The other outstanding bonds with similar maturities were orig-. inally issued about 10 years ago as 30-year bonds, and, therefore, have. relatively high coupons, which reflect the interest rate environment at the. time they were issued.  

Table 3.2 shows the coupons and yields of these four newly issued. 20-year bonds, each paired with the coupons and yields of old 30-year bonds of the same maturity. As expected, because of the coupon effect and the upward-sloping term structure of rates, the high-coupon, old 30-year bonds have lower yields than the low-coupon, newly issued 20-year bonds.. More analysis is needed, of course, to say that any one bond in this table is cheap or rich relative to another. But, because of the coupon effect, the fact that the new 20-year bonds have higher yields does not necessarily imply that they are better investments.  

![](6ee5276a4853295815821e04fe638c7ce3cffe26a78c0fd96f8474b28e9ffca6.jpg)  
FIGURE 3.2 Yields of US Treasury Bonds, as of May 14, 2021.  

TABLE 3.2 Yields of Selected US Treasury Bonds Maturing Between May 15,. 2040, and February 15, 2041, as of May 14, 2021. Coupons and Yields Are in Percent.   


<html><body><table><tr><td></td><td colspan="2">New 20-Year Bonds</td><td colspan="2">Old 30-Year Bonds</td></tr><tr><td>Maturity</td><td>Coupon</td><td></td><td>Coupon</td><td></td></tr><tr><td>05/15/2040</td><td>1.125</td><td>2.237</td><td>4.375</td><td>2.107</td></tr><tr><td>08/15/2040</td><td>1.125</td><td>2.245</td><td>3.875</td><td>2.138</td></tr><tr><td>11/15/2040</td><td>1.375</td><td>2.245</td><td>4.250</td><td>2.140</td></tr><tr><td>02/15/2041</td><td>1.875</td><td>2.236</td><td>4.750</td><td>2.133</td></tr></table></body></html>  

Returning to Figure 3.2, there are several bonds that mature on or before May 2031 that have yields noticeably below the curve. To examine these bonds, Figure 3.3 zooms in on maturities on or before May 2031. The dots represent bonds with coupon rates less than or equal to $5\%$ , while the plus signs represent bonds with coupon rates greater or equal to $5.25\%$ . Once again, as expected because of the coupon effect and the upward-sloping term structure, the bonds with the higher coupons have lower yields.  

![](3b63d8f2f068f1a4c3d3d88e80ee7ceb03bf65b0a24f7d331b8f2975f65e4e21.jpg)  
FIGURE 3.3  Yields of US Treasury Bonds Maturing in Less than 10 Years, as of May 14, 2021.  
