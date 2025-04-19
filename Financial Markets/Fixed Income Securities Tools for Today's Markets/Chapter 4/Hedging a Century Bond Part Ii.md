---
tags:
  - century_bond
  - convexity
  - market_maker
  - treasury_bond
aliases:
  - Dv01
  - Hedging a Century Bond
  - P&L implications
key_concepts:
  - Convexity and duration
  - Long convexity position risk
  - Market maker hedging Dv01
  - P&L implications
  - Treasury bond prices
---

# 4.6 HEDGING A CENTURY BOND: PART II  

Section 4.3 explained why and how a market maker hedges the Dv01 from $\$10$ million face amount of the NSC 4.10s of 05/15/2121 by selling $\$12.1$ million face amount of the Treasury 1.625s of 11/15/2050. This section shows that this hedge leaves the market maker with a long convexity position and describes the resulting risk and P&L implications.  

Figure 4.6 shows the $\mathrm{P}\&\mathrm{L}$ of $\$100$ million face amount of the NSC century bond and of $\$121$ million face amount of the 29.5-year Treasury bond. For example, the prices of these bonds in mid-May 2021 were 99.939 and 84.391, respectively, and if rates fell by 100 basis points, their prices would be 130.898 and 107.309, respectively. Hence, the P&L from $\$100$ million of the one and $\$121$ million of the other is $\$100$ million $\times(130.898-99.939)/100.$ or $\$30.96$ million, and $\$121$ million $\times$ $(107.309-84.391)/100$ , or $\$27.7$ million, respectively.  

Section 4.3 showed that, with these face amounts, the two positions have the same Dv01 at current market levels. Figure 4.6 reflects this fact in that the two $\mathrm{P}\&\mathrm{L}$ curves are tangent to each other, that is, they have the same slope, at current rates. Both bonds are positively convex, of course, but, because the NSC bonds are more convex (Table 4.4), their P&L exceeds the P&L on the Treasury bonds whether rates fall or rise. This result is emphasized by the dotted line in the figure, graphed against the right axis, which is the P&L of the NSC bonds minus the. $\mathrm{P}\&\mathrm{L}$ of the Treasury bonds and which,. in turn, is the net P&L of the market maker in this application. This net P&L is zero, of course, at current market levels but is positive for both negative and positive rate changes, and particularly large for large, negative changes.  

![](daf216b9e4be2551e5d6d7169a7b13d27544930154ac086959f996537385f9c1.jpg)  
FIGURE 4.6P&L of a Long Position of $\$100$ Million Face Amount of the NSC. 4.10s of 05/15/2121, a Dv01-Equivalent Long Position in the Treasury 1.625s of 11/15/2050, and a Position Long the NSC Bonds and Short the Treasury Bonds, as. of Mid-May 2021.  

Expanding on the results of the previous paragraph, for unchanged. rates and prices, the P&L of both bond holdings is clearly zero. If rates fall, both bonds increase in price and -- because they are both positively convex -- both their Dv01s increase as well. But because the NSC bonds are more. convex, their DV01 increases by more, which, for falling rates, means higher profits. Instead, if rates rise, both bonds decrease in price and in Dv01. But because the NSC bonds are more convex, their DV01 falls by more, which, for rising rates, means lower losses. Therefore, whether rates fall or rise, the P&L on the NSC bonds exceeds the P&L on a DV01-equivalent amount of Treasury bonds.  

The market maker is said to have a positively convex position and to be long convexity because the convexity of its long position (NsC bonds) is greater than the convexity of its short position (Treasury bonds) and because its P&L seems to be positive whether rates fall or rise. But is it really the case that the market maker profits from the position no matter what? If so, why don't arbitrageurs initiate positions that are long the century NSC bonds and short the 29.5-year Treasury bonds?  

These questions can be answered by noting that Figure 4.6 omits an important variable: time. As mentioned earlier, all of the figures in this chapter assume an instantaneous change in rates, that is, with no passage of time. As it turns out, however, bonds or portfolios that are more convex tend to earn less over time. Therefore, the full story of a positively convex position, or of being long convexity, is that the position profits if rates move down or up by a sufficient amount. If rates change by less than that, or stay the same, the position loses money. In this sense, a long convexity position is also long volatility. In any case, this is a fundamental property of asset pricing, applicable to both stock options and coupon bonds. Section 4.8 explores the topic further in the context of pension asset-liability management, and Chapter 8 shows how convexity fits into a general framework of returns.  

# 4.7YIELD-BASED DVO1, DURATION,AND CONVEXITY  

Previous sections described Dv01, duration, and convexity in a general, one-factor framework: specify the way changes in a rate or factor change the entire term structure, re-price bonds after the change, and compute risk metrics. This section is about yield-based metrics, for which a change. in rates means a fixed change in bond yields. These metrics have two significant weaknesses. One, they are defined only for bonds with fixed cash flows, but not, for example, for a callable bond or a mortgage. Two, their use implicitly assumes parallel shifts in bond yields, which is not an empirically sound assumption. Nevertheless, there are several reasons to study and understand yield-based metrics. First, they are simple to compute and easy to understand, and, in many situations, are perfectly reasonable to use. Second, these metrics are widely used across the financial industry. Third, much of the intuition gained from understanding these metrics carries over to more general frameworks..  

The reason that yield-based metrics are easy to compute is that price can be written as a function of yield, in the forms of Equations (3.7) and (3.8). Recalling that $c$ is the annual coupon payment and $T$ is the number of years to maturity, these equations are repeated here for convenience,  

$$
\begin{array}{l}{{P=\displaystyle\frac{c}{2}\sum_{t=1}^{2T}\displaystyle\frac{1}{\left(1+\displaystyle\frac{y}{2}\right)^{t}}+\displaystyle\frac{100}{\left(1+\displaystyle\frac{y}{2}\right)^{2T}}}}\ {{P=\displaystyle\frac{c}{y}\left(1-\displaystyle\frac{1}{\left(1+\displaystyle\frac{y}{2}\right)^{2T}}\right)+\displaystyle\frac{100}{\left(1+\displaystyle\frac{y}{2}\right)^{2T}}}}\end{array}
$$  

With these expressions, Dv01 and duration, as defined in Equations (4.5). and (4.11), can be solved explicitly. Calculate the derivative of the previous  

price-yield relationships and then divide by. $-10{,}000$ to find DV01 or by $-{\cal P}$ to find duration. The resulting formulas for yield-based Dv01 are,  

$$
\begin{array}{l}{{\displaystyle{\cal D}V01=\frac{1}{10,000}\frac{1}{1+\frac{y}{2}}\left[{\frac{c}{2}}\sum_{t=1}^{2T}\frac{t}{2}\frac{1}{\left(1+\frac{y}{2}\right)^{t}}+T\frac{100}{\left(1+\frac{y}{2}\right)^{2T}}\right]}~(4.2)}}\ {{\displaystyle{\cal D}V01=\frac{1}{10,000}\left[{\frac{c}{y^{2}}}\left(1-\frac{1}{\left(1+\frac{y}{2}\right)^{2T}}\right)+T\left(1-\frac{c}{100y}\right)\frac{100}{\left(1+\frac{y}{2}\right)^{2T+1}}\right]}~}\end{array}
$$  

and for yield-based duration are,  

$$
\begin{array}{c}{{\displaystyle{\cal D}=\frac{1}{P}\frac{1}{1+\frac{3}{2}}\left[\frac{c}{2}\sum_{t=1}^{2T}\frac{t}{2}\frac{1}{\left(1+\frac{y}{2}\right)^{t}}+T\frac{100}{\left(1+\frac{y}{2}\right)^{2T}}\right]}}\ {{\displaystyle{\cal D}=\frac{1}{P}\left[\frac{c}{y^{2}}\left(1-\frac{1}{\left(1+\frac{y}{2}\right)^{2T}}\right)+T\left(1-\frac{c}{100y}\right)\frac{100}{\left(1+\frac{y}{2}\right)^{2T+1}}\right]}}\end{array}.
$$  

This formulation of yield-based duration is also known in the industry as modified and adjusted duration.1  

The terms inside the square brackets of Equations (4.22) and (4.24) have. an intuitive interpretation that sheds light on these risk metrics. The terms $t/2$ and $T$ represent the times to receipt of each cash flow, that is, 0.5 years,. 1 year, 1.5 years, and so forth, out to $T$ years, the years to maturity. And each of these terms is multiplied by the present value of the cash flow to be received at that time, that is, $(c/2)/(1+y/2)^{t}$ for the coupon payments and $100/(1+y/2)^{2T}$ for the principal payment. Putting this all together, the sum of the terms in brackets can be described as the weighted sum of the times at. which cash flows are received, with each weight equal to the present value. of the cash flow received at that time. Furthermore, in the case of duration, where the bond price can be moved inside the brackets, each weight can be described as the present value of the cash flow received at that time divided by the bond price, which is the sum of all the present values. Therefore, this weight is simply the proportion of the bond's value contributed by that cash flow.  

Table 4.5 illustrates this interpretation by calculating the yield-based. DV01 and duration of the Treasury 1.625s of 05/15/2026 as of mid-May 2021. The first column gives the term of each cash flow; the second column gives the cash flows; and the third column gives the present value of each cash flow discounted at $0.82277\%$ , the bond's yield at the time. For example, the. present value of the coupon payable in 2.5 years is,.  

$$
{\frac{0.8125}{\left(1+{\frac{0.82277\%}{2}}\right)^{5}}}=0.7960
$$  

The sum of the present values of the cash flows is just the market price, in this case, 103.9219. The fourth column gives the present value of each cash flow as a percentage of the market price. Not surprisingly, for a bond maturing in five years and trading at a small premium, the principal accounts for a large. share of the bond's value, in this case, over. $93\%$  

TABLE 4.5  Calculating the Yield-Based DV01 and Duration of the Treasury 1.625s of 05/15/2026 at a Yield of $0.82277\%$ , as of Mid-May 2021.   


<html><body><table><tr><td>(1)</td><td>(2) Cash Flow</td><td>(3) Present Value</td><td>(4) PV/Price (%)</td><td>(5) Term x PV/Price</td><td>(6) Term-Wtd PV</td></tr><tr><td>0.5</td><td>0.8125</td><td>0.8092</td><td>0.779</td><td>0.0039</td><td>0.4046</td></tr><tr><td>1.0</td><td>0.8125</td><td>0.8059</td><td>0.775</td><td>0.0078</td><td>0.8059</td></tr><tr><td>1.5</td><td>0.8125</td><td>0.8026</td><td>0.772</td><td>0.0116</td><td>1.2038</td></tr><tr><td>2.0</td><td>0.8125</td><td>0.7993</td><td>0.769</td><td>0.0154</td><td>1.5985</td></tr><tr><td>2.5</td><td>0.8125</td><td>0.7960</td><td>0.766</td><td>0.0191</td><td>1.9900</td></tr><tr><td>3.0</td><td>0.8125</td><td>0.7927</td><td>0.763</td><td>0.0229</td><td>2.3782</td></tr><tr><td>3.5</td><td>0.8125</td><td>0.7895</td><td>0.760</td><td>0.0266</td><td>2.7632</td></tr><tr><td>4.0</td><td>0.8125</td><td>0.7862</td><td>0.757</td><td>0.0303</td><td>3.1450</td></tr><tr><td>4.5</td><td>0.8125</td><td>0.7830</td><td>0.753</td><td>0.0339</td><td>3.5236</td></tr><tr><td>5.0</td><td>100.8125</td><td>96.7575</td><td>93.106</td><td>4.6553</td><td>483.7877</td></tr><tr><td>Sum</td><td></td><td>103.9219</td><td>100.000</td><td>4.8267</td><td>501.6005</td></tr><tr><td>Duration: DV01:</td><td></td><td></td><td></td><td>4.8069</td><td></td></tr></table></body></html>  

The fifth column of the table multiplies each present value proportion by. its term: 0.5 weighted by $0.779\%$ , 1.0 weighted by $0.775\%$ , and so forth, and 5.0 weighted by $93.106\%$ . In this way, the sum of the column is the. weighted average of the payment times, with weights equal to the value proportion of each payment. In terms of Equation (4.24), this weighted average, 4.8267, is the sum of the terms in brackets divided by price. Duration, therefore, is $4.8267/(1+0.82277\%/2)$ , or 4.8069. This interpretation. explains why many market participants say that this bond has a duration of 4.83 years: the value of the bond is paid, on average, in 4.83 years.2 This. interpretation also explains why the duration of a coupon bond is somewhat less than its maturity: while most of a bond's value is paid at maturity, some. portion is paid earlier.  

Lastly, the sixth column of the table gives term times present value. The sum of this column is the sum of the terms in brackets in Equation (4.22), which means that DV01 is $(1/10,000)\times501.6005/(1+0.82277\%/2)=$ 0.0500.  

As mentioned earlier, the intuition derived from yield-based measures is often useful for understanding more general risk metrics. A lot of this intuition arises from the relatively simple expressions for yield-based DV01 and duration in Equations (4.23) and (4.25), and from the extremely simple expressions in the case of zero coupon bonds and par bonds. To derive these latter expressions, simply substitute $c=0$ and then $c=100y$ into the price equation, (4.21), and into the Dv01 and duration equations just referenced, to obtain the following. For a zero coupon bond,.  

$$
D V01_{c=0}={\frac{T}{100\Big(1+{\frac{y}{2}}\Big)^{2T+1}}}
$$  

$$
D_{c=0}=\frac{T}{\left(1+\frac{y}{2}\right)}
$$  

And for a par bond,  

$$
\begin{array}{c}{{\displaystyle{D V01_{c=100y}=\frac{1}{100y}\left(1-\frac{1}{\left(1+\frac{y}{2}\right)^{2T}}\right)}}}\ {{\displaystyle{}}}\ {{\displaystyle{D_{c=100y}=\frac{1}{y}\left(1-\frac{1}{\left(1+\frac{y}{2}\right)^{2T}}\right)}}}\end{array}
$$  

![](676cd9a0ebe1e5afa059cd652b3485d0a5e387e5b53da6937a91b488c0ecbfbd.jpg)  
FIGUre 4.7 Yield-Based Duration for Bonds with Coupons of $0\%$ $2\%$ , and $5\%$ Yield Equals $2\%$  

The discussion now turns to using these simple expressions to understand how yield-based duration and Dv01 depend on a bond's maturity, coupon, and yield. Figure 4.7, fixing yield for all bonds at. $2\%$ , graphs the duration of bonds of terms out to 40 years with coupons of $0\%$ $2\%$ , and $5\%$ . Several lessons can be taken from this figure..  

First, the duration of a zero coupon bond is approximately equal to its term, which can also be seen from Equation (4.28). Second, the duration of a par bond, in this case, of all bonds with a coupon of $2\%$ , increases with term, which can also be deduced from Equation (4.30).3 In addition,. however, the figure illustrates how the duration of par bonds increases less than linearly with term. Out to terms of five years, duration approximately equals term, but, for longer terms, duration falls more and more below term. The duration of a 10-year par bond is about 9.0; of a 20-year bond, 16.4; of. a 30-year bond, 22.5; and of a 40-year bond, 27.4. Third, the duration of a premium bond, with a coupon of $5\%$ , is less than the duration of a par bond. More generally, looking at the figure as a whole, bonds with higher coupons have lower durations. The intuition here is that higher-coupon bonds pay a greater fraction of their value earlier, which, in turn, means that the lower terms are more heavily weighted in the calculation of duration. Put another way, higher-coupon bonds are effectively shorter-term bonds and, therefore, have lower durations.  

Figure (4.8) graphs the DV01s of the same set of bonds, continuing to hold the yields of all bonds equal to $2\%$ . The DV01s of par bonds increase with maturity, which follows directly from inspection of Equation (4.29).. As with duration, however, the increase is less than linear. The DV01s of par. bonds with terms of five years or less are about equal to term divided by. 100. The DV01 of a five-year bond at a yield of $2\%$ , for example, is 0.047, which is slightly less than 0.05, or 5 cents per 100 face amount. But, for. longer terms, the difference is larger: the Dv01 of the 10-year par bond in. the figure is 9 cents; of the 20-year bond, 16 cents; of the 30-year bond, 22 cents; and of the 40-year bond, 27 cents.  

Unlike duration, however, Figure (4.8) shows that DV01 increases with coupon. To understand this, combine the definitions of DV01 and duration in Equations (4.5) and (4.11) to see that,  

$$
D V01=\frac{P\times D}{10\small,000}
$$  

In thinking about how Dv01 changes with term, therefore, there is a. price effect in addition to a duration effect. The duration effect almost always causes DV01 to increase with term, along the lines of the previous discussion. The price effect, however, can reinforce or counter this duration effect. For par bonds, whose prices are always 100, there is no price effect. For premium bonds, whose prices increase with term (recall Figure 3.1), the price effect reinforces the duration effect and, therefore, as shown in Figure (4.8), the. DV01s of $5\%$ bonds increase much more rapidly with term than do the DV01s of par bonds. For discount bonds, by contrast, whose prices decrease. with term, the price effect works against the duration effect and, therefore, as shown in the figure, the DV01s of zero coupon bonds increase more slowly. with term than those of par bonds. In fact, inspection of Equation (4.27). reveals that, at large enough terms, the Dv01s of zero coupon bonds fall. as term increases further, that is, the price effect,. $(1+y/2)^{2{\bar{T}}+1}$ , eventually dominates the duration effect,. $T$  

![](56b4fd0756c4bf00dd1605f394b80d6e0ffcbef561439e09b669ef4f534f14c2.jpg)  
FIGURE 4.8 Yield-Based DV01 for Bonds with Coupons of $0\%,2\%$ and $5\%$ . Yield Equals $2\%$  

Having described how Dv01 and duration vary with term and coupon. rate, the discussion turns to the effect of yield. It is clear from Equation (4.22) that Dvo1 falls as yield increases. This fact was introduced earlier, as an implication of the convex shape of the price-rate curve. As it turns out, increasing yield also lowers duration. Intuitively, increasing yield lowers the present value of all payments, but lowers the present value of the longer payments the most. This, in turn, lowers the proportions of bond value in the longer payments, lowers their weights in the duration calculation, and, therefore, lowers the duration of the bond..  

Figure 4.9 illustrates how duration changes with yield, graphing the duration of par bonds of various terms at yields of $0.5\%$ $2\%$ , and $5\%$ As just discussed, duration is lower at higher yields, significantly so for longer terms. Furthermore, the difference between duration and term, discussed earlier, is greater at higher yields. At a yield of $0.5\%$ , the durations of. 10- and 30-year par bonds are 9.7 and 27.8, respectively, while, at a yield of $5\%$ , those durations are 7.8 and 15.5, respectively.  

![](171d75abf4833da419c80fad3b046adc4222b9b8460222d5dc4f67756baa5cfd.jpg)  
FIGURE 4.9  Duration of Par Bonds, with Yields Equal to $0.5\%$ $2\%$ , and $5\%$  

The section turns now to yield-based convexity. Given the general definition of convexity in Equation (4.14), an expression for yield-based convexity can be found by taking the second derivative of Equation (4.20) and dividing by price. The resulting formula is,.  

$$
C=\frac{1}{P\left(1+\frac{y}{2}\right)^{2}}\left[\frac{c}{2}\sum_{t=1}^{2T}\frac{(t/2)((t+0.5)/2)}{\left(1+\frac{y}{2}\right)^{t}}+\frac{100T(T+0.5)}{\left(1+\frac{y}{2}\right)^{2T}}\right]
$$  

As in the formula for yield-based duration, Equation (4.24), the terms inside the brackets of (4.32) multiply the present value of payments by some function of the term of those payments. The big difference between the two,. however, is that, in the duration formula, that function of term is linear (i.e.,. $t$ and $T$ ), while in the convexity formula, the function is quadratic, $(t/2)((t+$ $0.5)/2)$ and $T(T+0.5)$ . The implication is that convexity increases much. faster with term than duration. This can be seen in the more general case from Tables 4.3 and 4.4. The durations of the 5- and 29.5-year Treasuries, and the 100-year NSC bonds are 3.9, 23.6, and 24.1, respectively, while their convexities are 12, 648, and 1,101, respectively..  

For completeness, the convexity formulas for zero coupon and par bonds are included here. For zero coupon bonds,  

$$
C_{c=0}=\frac{T(T+0.5)}{\left(1+\displaystyle\frac{y}{2}\right)^{2}}
$$  

and for par bonds,  

$$
C_{c=y}=\frac{2}{y^{2}}\left[1-\frac{1}{\left(1+\frac{y}{2}\right)^{2T}}\right]-\frac{2T}{y\left(1+\frac{y}{2}\right)^{2T+1}}
$$  

The section concludes with a note about the assumptions underlying the. use of yield-based metrics. The yield-based Dv01, duration, and convexity. for each bond are determined by shifting the yield of that bond. Therefore, any risk management strategy across bonds implicitly assumes that yields of all included bonds move up and down together, in parallel. For example,. if one bond has a yield-based Dv01 of 0.05 and a second of 0.10, then hedging 100 face amount of the second by selling 200 face amount of the first is perfectly successful only if the yields of both bonds move by the same amount. If a trader hedges a 9.5-year bond with a 10-year bond over a short period of time, the assumption of parallel shifts in yield might be reasonable enough. Hedging a two-year bond with a 10-year bond, however, assuming that those yields move in parallel, is not likely to produce the desired, hedged Outcome.  
