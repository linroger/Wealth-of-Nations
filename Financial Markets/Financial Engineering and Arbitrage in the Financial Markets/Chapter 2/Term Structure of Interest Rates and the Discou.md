---
tags:
  - coupon_bond
  - discount_factor
  - interest_rates
  - term_structure
  - yield_curve
aliases:
  - Discount Factors
  - Term Structure
  - Yield Curve Bootstrap
key_concepts:
  - Coupon bond valuation
  - Discount factor bootstrap
  - Spot zero rates
  - Term structure of rates
  - Yield to maturity
---

# 2.3 TERM STRUCTURE OF INTEREST RATES AND THE DISCOUNT FACTOR BOOTSTRAP  

Interest rates on any given day are different for different maturity instruments. A set of interest.   
rates complete across all maturities is called the term structure of interest rates. This complete set can be defined using observed coupon bond rates, zero-coupon rates, or a mix of the two.   
The term structure implicitly defines a unique set of discount factors with which we are able.   
to price any fixed income security in the market by present valuing its cash flows..  

# 2.3.1Term Structure  

Jack is offered a $4.0\%$ semi-annual $\$1,000$ par value bond maturing in $3^{1}/_{2}$ years. How much should he pay for it? We draw a picture of the bond in Figure 2.12. We observe that the $3\%$ -year bond is a package of seven cash flows starting 6 months from now and ending 42 months from now, and if we knew the seven spot zero-coupon rates $r_{1},r_{2},\ldots,r_{7}$ or equivalently the seven discount factors $d f_{1},d f_{2},\cdot\cdot\cdot,d f_{7}$ we would know how to value the bond.  

Suppose that no zero-coupon bonds are currently traded in the market from which to obtain the zero-coupon rates, but we can observe the set of coupon bond prices and rates in Figure 2.13. All the bonds have semi-annual coupons, the yields-to-maturity are stated in semi-annual.  

![](81a2c0a2a1ab18423dac977c07d0685b6227c4ac72e8e5b5f4313d293302f394.jpg)  
Figure 2.12 A $3\%$ -year coupon bond we want to value  

![](6916017075b20a3e5a56226cde0413c5f78fe573a858d39ae058dafd714d85c3.jpg)  
Figure 2.13 The term structure of coupon interest rates  

rates, and prices are stated per $\$100$ par value. The yields-to-maturity are computed by solving. for the discount rate for which the sum of the present values of the cash flows equals the given bond price. An example yield-to-maturity equation is shown for the 2-year. $3.5\%$ bond. The equation is solved using a trial-and-error method, a financial calculator, or an Excel function RATE. The term structure of coupon rates is a set of terms (maturities) and the corresponding. yields-to-maturity. It is commonly represented as a table or graph. In Figure 2.13 we show both.  

# 2.3.2 Discount Factor Bootstrap  

The yields-to-maturity from Figure 2.13 cannot be used directly to discount the cash flows of Jack's $3^{1}/_{2}$ -year bond (we need spot zero rates). But they contain enough information to allow us to do so. The process of obtaining spot zero rates or spot discount factors from the coupon term structure is called the yield curve bootstrap and is illustrated in Table 2.1. It proceeds step-by-step from the shortest to the longest maturity and relies on the sum-of-the parts argument. Step 1 is easy since what we labeled a 6-month $2\%$ bond is really a 6-month. zero-coupon bond with a face value of $\$101$ . So the 6-month zero rate is the same as the yield-to-maturity of the 6-month coupon bond, i.e. $2\%$ . At Step 2, the 1-year. $2.5\%$ coupon bond is viewed as a package of two zero-coupon bonds: a 6-month $\$1.25$ face value bond and a 12-month $\$101.25$ face value bond. The price of the package is $\$100.10$ . Using the 6-month. zero rate from Step 1, we can compute the present value of $\$1.25$ in 6 months and subtract it. from $\$100.10$ . The remainder is the present value of the 12-month $\$101.25$ cash flow. Knowing that, we compute the 12-month zero rate and the 12-month discount factor. At each subsequent step, the coupon bond for that maturity is viewed as a package of zero-coupon bonds maturing at coupon dates and using the zero rates or discount factors from prior steps we can compute the present value of all the coupon cash flows prior to the last one. Subtracting those present values from the total value of the bond (the current price) we get the present value of the last cash flow consisting of the last coupon and principal. Again, it is easy then to solve for the zero-coupon rate or the discount factor to the date of the last cash flow.  

Once we have computed all the zero rates and spot discount factors, we are also able to compute forward one-period discount factors and forward one-period zero rates. We added. them in the last two columns of the last panel of Table 2.1. In valuing bonds, we use the sum-of-the parts argument similar to that in Figure 2.4 and discount cash flows directly to today (spot) using the spot zero rates or spot discount factors (instead of one yield-to-maturity). Alternatively, we can use the backward step-by-step discounting sweep argument similar to that. in Figure 2.3 and discount and cumulate cash flows going back step-by-step using the forward. zero rates or forward discount factors. We will return to this second method in Chapter 3 when we define the notion of forward rates. The two methods always produce identical answers.  

# 2.3.3 Valuation of an Arbitrary Bond  

Having performed the discount curve bootstrap, Jack is now ready to present-value his $4.0\%$ semi-annual $\$1,000$ par value bond maturing in. $3^{1}/_{2}$ years. All he needs to do is to multiply his expected coupon cash flows of $\$2.00$ and $\$1,000$ principal by the corresponding discount factors and sum up the present values to find the total present value of the bond. Figure 2.14 presents the procedure graphically and as a simple table. This valuation method applies to any bond with fixed cash flows..  

Table 2.1 The Bootstrap   


<html><body><table><tr><td colspan="9"></td></tr><tr><td></td><td>n 1</td><td>Term 6m</td><td>Coupon 2.00</td><td>Price 100.00</td><td>YTM 2.0000%</td><td>Zt ？</td><td>？</td><td></td></tr><tr><td>Step1- 6m:100.00=</td><td></td><td></td><td>101.00</td><td></td><td></td><td></td><td></td><td>=0.990099</td></tr><tr><td></td><td rowspan="2"></td><td></td><td rowspan="2">(1 + Z6m/2) Coupon</td><td rowspan="2">Price</td><td rowspan="2">YTM</td><td rowspan="2"></td><td rowspan="2">(1 + 0.02/2)</td><td rowspan="2">J</td></tr><tr><td>n 6m</td><td>Term</td></tr><tr><td colspan="8">1 2</td><td></td></tr><tr><td></td><td>1y</td><td>2.50 1.25</td><td></td><td>100.10 101.25</td><td>2.3982%</td><td>？</td><td>？</td><td></td></tr><tr><td colspan="7">ep2-12m:100.10=</td><td></td><td>= 0.976419</td></tr><tr><td></td><td></td><td></td><td></td><td>(1 +z1y/2)2</td><td></td><td></td><td></td><td></td></tr><tr><td>n 1</td><td>6m</td><td>Term</td><td>Coupon 2.00</td><td>Price 100.00</td><td>YTM 2.0000%</td><td>Zt 2.0000%</td><td>df 0.990099</td><td></td></tr><tr><td>2 3</td><td>1y</td><td></td><td>2.50</td><td>100.10</td><td>2.3982%</td><td>2.4007%</td><td>0.976419</td><td></td></tr><tr><td></td><td></td><td>18m</td><td>3.00</td><td>100.25</td><td>2.8286%</td><td>？</td><td>？</td><td></td></tr><tr><td></td><td>1.50</td><td></td><td>1.50</td><td>101.50</td><td></td><td></td><td></td><td></td></tr><tr><td colspan="7">:100.25 = (1+ 0.02/2) +</td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>(1+ 0.024007/2)2</td><td>(1 + Z18m/ 2)3</td><td></td><td></td><td></td><td></td></tr><tr><td>n</td><td></td><td>Term</td><td>Coupon</td><td>Price</td><td>YTM</td><td>Zt</td><td>df</td><td></td></tr><tr><td>1 2</td><td></td><td>6m</td><td>2.00</td><td>100.00</td><td>2.0000%</td><td>2.0000%</td><td>0.990099</td><td></td></tr><tr><td>3</td><td></td><td>1y 18m</td><td>2.50 3.00</td><td>100.10 100.25</td><td>2.3982% 2.8286%</td><td>2.4007% 2.8371%</td><td>0.976419 0.958623</td><td></td></tr><tr><td>4</td><td></td><td>2y</td><td>3.50</td><td>100.32</td><td>3.3333%</td><td>？</td><td>？</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td colspan="7">1.75 tep4-24m:100.32= +</td><td>101.75</td><td>→Z2y,df2</td></tr><tr><td></td><td></td><td></td><td>(1+ 0.02/2)</td><td>(1+ 0.024007/2)2</td><td></td><td>(1+ 0.028371/2)3</td><td>(1 + Z2y/ 2)4</td><td></td></tr><tr><td>n</td><td></td><td>Term</td><td>Coupon</td><td>Price</td><td>YTM</td><td>Zt</td><td>df</td><td></td></tr><tr><td>1</td><td>6m 2 1y</td><td></td><td>2.00</td><td>100.00</td><td>2.0000%</td><td>2.0000%</td><td>0.990099</td><td></td></tr><tr><td></td><td></td><td></td><td>2.50</td><td>100.10</td><td>2.3982%</td><td>2.4007%</td><td>0.976419</td><td></td></tr><tr><td></td><td></td><td>18m</td><td>3.00</td><td>100.25</td><td>2.8286%</td><td>2.8371%</td><td>0.958623</td><td></td></tr><tr><td>4</td><td></td><td></td><td>3.50</td><td>100.32</td><td>3.3333%</td><td>3.3542%</td><td>0.935636</td><td></td></tr><tr><td></td><td></td><td>30m</td><td>3.25</td><td>99.84</td><td>3.3172%</td><td>？</td><td>？</td><td></td></tr><tr><td>99.84 = +</td><td>1.625</td><td></td><td>1.625</td><td></td><td>1.625</td><td>1.625</td><td></td><td>101.625</td></tr><tr><td colspan="7">s(z/0z +1) + ±(Z/2≤200 +1) + s(Z/1≤8200 +1) (1+ 0.02/2)</td><td></td><td></td></tr><tr><td>n Term</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>1 2</td><td></td><td>6m</td><td>Coupon 2.00</td><td>Price 100.00</td><td>YTM 2.0000%</td><td>Zt 2.0000%</td><td>df 0.990099</td><td></td></tr><tr><td>3</td><td></td><td>1y</td><td>2.50</td><td>100.10</td><td>2.3982%</td><td>2.4007%</td><td>0.976419</td><td></td></tr><tr><td>4</td><td></td><td>18m</td><td>3.00</td><td>100.25</td><td>2.8286%</td><td>2.8371%</td><td>0.958623</td><td></td></tr><tr><td>5</td><td></td><td>2y</td><td>3.50</td><td>100.32</td><td>3.3333%</td><td>3.3542%</td><td>0.935636</td><td></td></tr><tr><td>6</td><td></td><td>30m</td><td>3.25</td><td>99.84</td><td>3.3172%</td><td>3.3323%</td><td>0.920701</td><td></td></tr><tr><td></td><td></td><td>3y</td><td>3.00</td><td>99.78</td><td>3.0773%</td><td>？</td><td>？</td><td></td></tr><tr><td>99.78 =</td><td></td><td></td><td>1.50</td><td></td><td></td><td></td><td>1.50</td><td>101.50</td></tr><tr><td colspan="7">1.50</td><td>(1 + z3/ 2)6</td><td></td></tr><tr><td></td><td></td><td></td><td>(1+ 0.02/2)+(1+ 0.024007/2)2</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>n</td><td>Term</td><td>Coupon</td><td>Price</td><td>YTM</td><td>Zt</td><td>J</td><td></td></tr><tr><td></td><td>1</td><td>6m</td><td>2.00</td><td>100.00</td><td>2.0000%</td><td>2.0000%</td><td>0.990099</td><td></td></tr><tr><td>2 3</td><td></td><td>1y</td><td>2.50</td><td>100.10</td><td>2.3982%</td><td>2.4007%</td><td>0.976419</td><td></td></tr><tr><td>4</td><td></td><td>18m</td><td>3.00</td><td>100.25</td><td>2.8286%</td><td>2.8371%</td><td>0.958623</td><td></td></tr><tr><td>5</td><td></td><td>2y</td><td>3.50</td><td>100.32</td><td>3.3333%</td><td>3.3542%</td><td>0.935636</td><td></td></tr><tr><td>6</td><td></td><td>30m 3y</td><td>3.25 3.00</td><td>99.84 99.78</td><td>3.3172% 3.0773%</td><td>3.3323% 3.0797%</td><td>0.920701 0.912392</td><td></td></tr><tr><td></td></table></body></html>  

Step7 - 42m  

Table 2.1(Continued)   


<html><body><table><tr><td>n</td><td>Term</td><td>Coupon</td><td>Price</td><td>YTM</td><td>Zt</td><td>P</td></tr><tr><td>1</td><td>6m</td><td>2.00</td><td>100.00</td><td>2.0000%</td><td>2.0000%</td><td>0.990099</td></tr><tr><td>2</td><td>1y</td><td>2.50</td><td>100.10</td><td>2.3982%</td><td>2.4007%</td><td>0.976419</td></tr><tr><td>3</td><td>18m</td><td>3.00</td><td>100.25</td><td>2.8286%</td><td>2.8371%</td><td>0.958623</td></tr><tr><td>4</td><td>2y</td><td>3.50</td><td>100.32</td><td>3.3333%</td><td>3.3542%</td><td>0.935636</td></tr><tr><td>5</td><td>30m</td><td>3.25</td><td>99.84</td><td>3.3172%</td><td>3.3323%</td><td>0.920701</td></tr><tr><td>6</td><td>3y</td><td>3.00</td><td>99.78</td><td>3.0773%</td><td>3.0797%</td><td>0.912392</td></tr><tr><td>7</td><td>42m</td><td>3.25</td><td>99.89</td><td>3.2835%</td><td>3.2961%</td><td>0.891882</td></tr><tr><td>8</td><td>4y</td><td>3.50</td><td>100.15</td><td>3.4595%</td><td>？</td><td>？</td></tr></table></body></html>  

$$
{\mathrm{step8-48m:100.15=\frac{1.75}{(1+0.02/2)}}+\frac{1.75}{(1+0.024007/2)^{2}}+\cdots+\frac{1.75}{(1+0.030797/2)^{6}}+\frac{1.75}{(1+0.032961/2)^{7}}+\frac{101.75}{(1+z_{49}/2)^{8}}\rightarrow z_{4}}
$$  

<html><body><table><tr><td>n</td><td>Term</td><td>Coupon</td><td>Price</td><td>YTM</td><td>Zt</td><td></td><td>r'1-Jp</td><td>ft-1,t</td></tr><tr><td>1</td><td>6m</td><td>2.00</td><td>100.00</td><td>2.0000%</td><td>2.0000%</td><td>6600660</td><td>0.990099</td><td>2.0000%</td></tr><tr><td>2</td><td>1y</td><td>2.50</td><td>100.10</td><td>2.3982%</td><td>2.4007%</td><td>0.976419</td><td>0.986183</td><td>2.8022%</td></tr><tr><td>3</td><td>18m</td><td>3.00</td><td>100.25</td><td>2.8286%</td><td>2.8371%</td><td>0.958623</td><td>0.981775</td><td>3.7128%</td></tr><tr><td>4</td><td>2y</td><td>3.50</td><td>100.32</td><td>3.3333%</td><td>3.3542%</td><td>0.935636</td><td>0.976021</td><td>4.9136%</td></tr><tr><td>5</td><td>30m</td><td>3.25</td><td>99.84</td><td>3.3172%</td><td>3.3323%</td><td>0.920701</td><td>0.984037</td><td>3.2444%</td></tr><tr><td>6</td><td>3y</td><td>3.00</td><td>99.78</td><td>3.0773%</td><td>3.0797%</td><td>0.912392</td><td>0.990975</td><td>1.8214%</td></tr><tr><td>7</td><td>42m</td><td>3.25</td><td>99.89</td><td>3.2835%</td><td>3.2961%</td><td>0.891882</td><td>0.977520</td><td>4.5994%</td></tr><tr><td>8</td><td>4y</td><td>3.50</td><td>100.15</td><td>3.4595%</td><td>3.4826%</td><td>0.871007</td><td>0.976595</td><td>4.7933%</td></tr></table></body></html>

where one period forward discount factors are df-1,t = - $\mathbf{\Sigma}_{\cdot1,\mathbf{t}}={\frac{\mathrm{df}_{\mathrm{t}}}{\mathrm{df}_{\mathrm{t-1}}}}$ and forward zero rates are $\mathrm{f_{t-l,t}}=2(\mathrm{df_{t-l,t}}^{-2}-1)$  

![](27f773ba4b912238eb310fb703fabddd94628bcfaef83569444efe512696c8f5.jpg)  
Figure 2.14Valuation of the $31/2$ year $4\%$ semiann. coupon bond using the bootstrapped discount factors  
