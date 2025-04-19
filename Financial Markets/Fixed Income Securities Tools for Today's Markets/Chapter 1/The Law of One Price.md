---
tags:
  - bond_pricing
  - discount_factors
  - law_of_one_price
  - market_price
  - us_treasury_bonds
aliases:
  - LOOP
  - Law of One Price
key_concepts:
  - Bonds trading rich or cheap
  - Deviations from the law
  - Identical cash flows, same price
  - Market price vs present value
  - Present value calculation
---

# 1.3 THE LAW OF ONE PRICE  

The US Treasury 1.75s of 05/15/2022 mature in mid-May, approximately one year from the settlement date of the examples of this chapter but are not included among the bonds in Table 1.2. How should the 1.75s of 05/15/2022 be priced? A natural answer is to apply the discount factors of Table 1.3 even though the 1.75s of 05/15/2022 are not used to construct those discount factors. After all, because all of these bonds are obligations of the US Treasury, it seems reasonable to assume as a first approximation that the present value of receiving $\$1$ from the Treasury on some future date does not depend on which particular bond pays that $\$1$ . This reasoning is known as the law of one price: absent confounding factors (e.g., liquidity, financing, taxes, credit risk), identical cash flows should sell for the same price.  

According to the law of one price, then, the price of the 1.75s of 05/15/2022 should be,  

$$
{\frac{1.75}{2}}\times0.999923+\left(100+{\frac{1.75}{2}}\right)\times0.999419=101.691
$$  

where the bond's present value is calculated as the sum of each cash flow multiplied by its corresponding discount factor from Table 1.3. As it turns out, the market price of this bond is 101.693, which is nearly equal to the prediction of the law of one price in Equation (1.4).  

Table 1.4 compares market prices with present values for all US Treasury bonds that mature on November 15 or May 15 out to November 15, 2024.  

IABLE 1.4 Treasury Bond Prices Versus Present Values Using the Discount Factors of Table 1.3. Bonds in Bold Are Used to Derive those Discount Factors. Coupons Are in Percent.   


<html><body><table><tr><td></td><td></td><td>Maturity</td><td>Market Price</td><td>Present Value</td><td>Rich(+)/ Cheap(-)</td><td>Issue Date</td></tr><tr><td>Term</td><td>Coupon</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>0.5 0.5</td><td>2.875 2.000</td><td>11/15/2021 11/15/2021</td><td>101.4297 100.9952</td><td>101.4297 100.9922</td><td>0.0000 0.0030</td><td>11/15/2018 11/15/2011</td></tr><tr><td>0.5</td><td>8.000</td><td>11/15/2021</td><td>104.0904</td><td>103.9920</td><td>0.0984</td><td>11/15/1991</td></tr><tr><td>1.0</td><td>2.125</td><td>05/15/2022</td><td>102.0662</td><td>102.0662</td><td>0.0000</td><td>05/15/2019</td></tr><tr><td>1.0</td><td>1.750</td><td>05/15/2022</td><td>101.6931</td><td>101.6914</td><td>0.0017</td><td>05/15/2012</td></tr><tr><td>1.5</td><td>1.625</td><td>11/15/2022</td><td>102.2862</td><td>102.2862</td><td>0.0000</td><td>11/15/2012</td></tr><tr><td>1.5</td><td>7.625</td><td>11/15/2022</td><td>111.3969</td><td>111.2797</td><td>0.1172</td><td>11/16/1992</td></tr><tr><td>2.0</td><td>0.125</td><td>05/15/2023</td><td>99.9538</td><td>99.9538</td><td>0.0000</td><td>05/15/2020</td></tr><tr><td>2.0</td><td>1.750</td><td>5/15/2023</td><td>103.1970</td><td>103.1997</td><td>-0.0026</td><td>05/15/2013</td></tr><tr><td>2.5</td><td>0.250</td><td>11/15/2023</td><td>100.0795</td><td>100.0795</td><td>0.0000</td><td>11/16/2020</td></tr><tr><td>2.5</td><td>2.750</td><td>11/15/2023</td><td>106.3040</td><td>106.3163</td><td>-0.0123</td><td>11/15/2013</td></tr><tr><td>3.0</td><td>0.250</td><td>05/15/2024</td><td>99.7670</td><td>99.7670</td><td>0.0000</td><td>05/17/2021</td></tr><tr><td>3.0</td><td>2.500</td><td>05/15/2024</td><td>106.5448</td><td>106.4941</td><td>0.0508</td><td>05/15/2014</td></tr><tr><td>3.5</td><td>2.250</td><td>11/15/2024</td><td>106.3091</td><td>106.3091</td><td>0.0000</td><td>11/17/2014</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>3.5</td><td>7.500</td><td>11/15/2024</td><td>124.8220</td><td>124.5906</td><td>0.2314</td><td>08/15/1994</td></tr></table></body></html>  

The "Present Value" column is computed along the lines of Equation (1.4), giving the prices of the bonds as predicted by the law of one price. The column "Rich $\left(+\right)/$ Cheap $(-)^{\mathfrak{s}}$ is the difference between the market price and the present value. Bonds with prices greater than that predicted by a model, like the law of one price, are said to be trading rich, while bonds with prices less than predicted by the model are said to be trading cheap.  

The bonds in bold in Table 1.4 are those listed in Table 1.2 and used to compute the discount factors in Table 1.3. Therefore, these bonds are fair, that is, neither rich nor cheap, relative to those discount factors. The prices of the other bonds in Table 1.4, however, can be either rich or cheap relative to those discount factors or, equivalently, relative to the prices of the bonds in bold.  

The table, as a whole, more or less supports the law of one price. Most. of the deviations of present values from market prices are very small, and. even the largest deviation, the 23-cent richness of the 7.5s of 11/15/2024, is less than $0.2\%$ of the bond's market price..  

Across the bonds in Table 1.4, those with the largest deviations are the older, high-coupon bonds, for example, the 8s of 11/15/2021, issued in 1991; and the 7.625s of 11/15/2022, issued in 1992. Furthermore, these bonds all trade rich relative to the bonds in bold. This is somewhat surprising because, historically, older bonds, which tend to be relatively illiquid, have tended to trade cheap relative to other bonds. Perhaps in the current, low-rate environment, some investors have a strong preference for income and are willing to pay more than fair value for bonds paying high coupons..  

While the law of one price is generally supported by Table 1.4, it is. natural to ask whether a trader or investor could profit by buying cheap. bonds and simultaneously selling fairly priced bonds; by selling rich bonds. and simultaneously buying fairly prices bonds; or - so as to profit on both sides of the trade - by buying cheap bonds and simultaneously selling rich. bonds. The next section addresses this question..  
