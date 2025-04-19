---
tags:
  - bond_pricing
  - bond_valuation
  - bond_yield
  - coupon_rate
  - yield_to_maturity
aliases:
  - Bond Yield
  - YTM
  - Yield
key_concepts:
  - Bond price and yield
  - Bond valuation with rates
  - Coupon rate and yield
  - Price-yield relationship
  - Yield to maturity definition
---

# 3.2 YIELD TO MATURITY  

Chapter 2 made the point that rates are often more intuitive than prices in describing bond valuation. But, along the lines of that chapter, to describe the pricing of a 10-year bond in terms of semiannually compounded spot rates or forward rates requires 20 of those spot or forward rates. It is hardly surprising, therefore, that market participants prefer to quote the price of a bond and to think about its valuation with a single rate, namely, its yield to maturity.  

The yield to maturity of a bond is the single rate such that discounting. the bond's cash flows by that rate gives the bond's market price. Table 1.4 reported the price of the US Treasury 7.625s of 11/15/2022 for settlement in. mid-May 2021 as 111.3969. Recalling that US Treasury bonds pay coupons semiannually so that this bond had three remaining payment dates, and not-. ing the Treasury bonds are quoted with semiannually compounded yields, the yield to maturity of this bond,. $y$ , is defined as,2  

$$
111.3969={\frac{3.8125}{\left(1+{\frac{y}{2}}\right)}}+{\frac{3.8125}{\left(1+{\frac{y}{2}}\right)^{2}}}+{\frac{103.8125}{\left(1+{\frac{y}{2}}\right)^{3}}}
$$  

Equation (3.5) can be solved for. $y$ by some numerical method or with a financial calculator, giving a result of $0.0252\%$ . Hence, trades of this bond. could be quoted and consummated either at a price of 111.3969 or at a yield of $0.0252\%$  

More generally, let. $y$ denote the yield of a bond; let. $c$ denote its annual,. dollar coupon payment; let. $T$ denote its maturity in years, which means there are $2T$ semiannual payments remaining; and let $P$ denote its price, per 100 face amount, for settlement on a coupon payment date. To illustrate notation, note that for the 7.625s of 11/15/2022 settling in mid-May 2021, $c=7.625$ $T=1.5$ $P=111.3969$ , and $y=0.0252\%$ . Returning to the general case, then, $P$ is given by,  

$$
\begin{array}{l}{P=\displaystyle\frac{\frac{1}{2}c}{\left(1+\displaystyle\frac{y}{2}\right)^{+}}+\frac{\frac{1}{2}c}{\left(1+\displaystyle\frac{y}{2}\right)^{2}}+\cdots+\frac{100+\frac{1}{2}c}{\left(1+\displaystyle\frac{y}{2}\right)^{2T}}}\ {P=\displaystyle\frac{c}{2}\sum_{t=1}^{2T}\frac{1}{\left(1+\displaystyle\frac{y}{2}\right)^{t}}+\frac{100}{\left(1+\displaystyle\frac{y}{2}\right)^{2T}}}\ {P=\displaystyle\frac{c}{y}\left(1-\frac{1}{\left(1+\displaystyle\frac{y}{2}\right)^{2T}}\right)+\frac{100}{\left(1+\displaystyle\frac{y}{2}\right)^{2T}}}\end{array}
$$  

where Equation (3.7) just re-expresses (3.6) with summation notation, and Equation (3.8) follows from (3.7) and Equation (A2.16) of Appendix A2.2..  

Equation (3.8) reveals three immediate implications about the. price-yield relationship. First, when. $c=100y$ $P=100$ : when the coupon payment is the face amount times the yield, or, more simply, when the coupon rate equals the yield, the bonds sells for its face amount, or par.. Second, when $c>100y$ $P>100$ : when the coupon rate exceeds the yield,. the bond sells at a premium to par. Third, when. $c<100y$ $P<100$ : when the yield exceeds the coupon rate, the bond sells at a discount to par.  

Figure 3.1 illustrates the relationship between price and yield as described by Equations (3.6) to (3.8). Every point along the curves in the figure represents a bond with a particular coupon and maturity, and all bonds in the figure are priced at a yield of. $1.5\%$ . The thick black line, then,. shows that bonds with a coupon rate of. $1.5\%$ , of any maturity, have a price. of 100. Investors are willing to pay 100 for a bond that pays the going market coupon rate over time and then returns par at maturity.  

Bonds with a coupon rate greater than the fixed yield of $1.5\%$ , represented by the. $3\%$ and $6\%$ gray, dashed lines in the figure, sell at a premium to par. With 30 years to maturity, the price a $6\%$ bond yielding. $1.5\%$ is about 208, while the price of a. $3\%$ bond at that yield is about 136.. Investors are willing to pay much more than par for these bonds because they pay above-market coupon rates for many years. Bonds with the same coupon rates but shorter maturities still command premiums, but smaller ones. For example, the prices of the 15-year bonds in the figure with $6\%$ and $3\%$ coupon rates are about 160 and 120, respectively. And, as maturities get very short, prices approach 100: while the $6\%$ and $3\%$ bonds do pay above-market coupon rates, they do so for such a short time that their prices are not much above 100.  

![](654f886059209293a460b0d354f3288d3eb16e41d95b8940efd4d2568732649a.jpg)  
FIGure 3.1 Prices of Bonds with Different Coupons and Maturities. All Yields Equal $1.5\%$  

Following similar reasoning, the lines in Figure 3.1 representing bonds with coupon rates of. $0\%$ and $0.75\%$ show prices all below par. The dis-. count is greatest for the longest maturity bonds, for which investors receive below-market coupon rates for the longest times, with the prices of 30-year $0\%$ and $0.75\%$ bonds being about 64 and 82, respectively. Price is less discounted for shorter maturity bonds, to about 80 and 90 at 15 years, respectively, until bonds very near maturity sell for just under par. The trend of premium and discount bond prices to approach par as they mature is known as the pull to par. This behavior, of course, is only the trend, at a fixed yield of. $1.5\%$ . The actual price paths of these bonds as they mature are determined by their realized market yields.  
