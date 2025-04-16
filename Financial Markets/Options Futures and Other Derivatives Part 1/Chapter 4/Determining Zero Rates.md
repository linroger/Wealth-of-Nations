---
tags:
  - '#bond_pricing'
  - '#bootstrap_method'
  - '#continuous_compounding'
  - '#coupon_bonds'
  - '#interpolation'
  - '#spline_function'
  - '#zero_curve'
  - '#zero_rates'
---
# 4.7 DETERMINING ZERO RATES  

In this section we describe a procedure known as the bootstrap method which can be used to determine zero rates.  

Consider the data in Table 4.3 on the prices of five bonds. Because the first three. bonds pay no coupons, the zero rates corresponding to the maturities of these bonds  

Table 4.3 Data for bootstrap method.   


<html><body><table><tr><td>Bondprincipal ($)</td><td>Timetomaturity (years)</td><td>Annual coupon* ($)</td><td>Bondprice ($)</td><td>Bond yield** (%)</td></tr><tr><td>100</td><td>0.25</td><td>0</td><td>99.6</td><td>1.6064 (Q)</td></tr><tr><td>100</td><td>0.50</td><td>0</td><td>99.0</td><td>2.0202 (SA)</td></tr><tr><td>100</td><td>1.00</td><td>0</td><td>97.8</td><td>2.2495 (A)</td></tr><tr><td>100</td><td>1.50</td><td>4</td><td>102.5</td><td>2.2949 (SA)</td></tr><tr><td>100</td><td>2.00</td><td>5</td><td>105.0</td><td>2.4238 (SA)</td></tr></table></body></html>

\*Half the stated coupon is assumed to be paid every 6 months. \*\*Compounding frequency corresponds to payment frequency: ${\mathrm{Q}}=$ quarterly, $\mathbf{SA}=$ semiannual, $\mathbf{A}=$ annual.  

can easily be calculated. The 3-month bond has the effect of turning an investment of 99.6 into 100 in 3 months. The continuously compounded 3-month rate $R$ is therefore given by solving  

$$
100=99.6e^{R\times0.25}
$$  

It is $1.603\%$ per annum. The 6-month continuously compounded rate is similarly given by solving  

$$
100=99.0e^{R\times0.5}
$$  

It is $2.010\%$ per annum. Similarly, the 1-year rate with continuous compounding is given by solving  

$$
100=97.8e^{R\times1.0}
$$  

It is $2.225\%$ per annum.  

The fourth bond lasts 1.5 years. Because coupons are paid semiannually, the cash flows it provides are as follows:.  

6 months: $\$2$   
1 year: $\$2$   
1.5 years: $\$102$  

From our earlier calculations, we know that the discount rate for the payment at the end of 6 months is $2.010\%$ and that the discount rate for the payment at the end of 1 year is $2.225\%$ . We also know that the bond's price,. $\$102.5$ , must equal the present value of all. the payments received by the bondholder. Suppose the 1.5-year zero rate is denoted by $R$ It follows that.  

$$
2e^{-0.02010\times0.5}+2e^{-0.02225\times1.0}+102e^{-R\times1.5}=102.5
$$  

This reduces to  

$$
e^{-1.5R}=0.96631
$$  

or  

$$
R=-{\frac{\ln(0.96631)}{1.5}}=0.02284
$$  

The 1.5-year zero rate is therefore. $2.284\%$ . This is the only zero rate that is consistent.   
with the 6-month rate, 1-year rate, and the data in Table 4.3.  

The 2-year zero rate can be calculated similarly from the 6-month, 1-year, and 1.5-year zero rates, and the information on the last bond in Table 4.3. If $R$ is the 2-year zero rate, then  

$$
2.5e^{-0.02010\times0.5}+2.5e^{-0.02225\times1.0}+2.5e^{-0.02284\times1.5}+102.5e^{-R\times2.0}=105
$$  

This gives $R=0.02416$ , or $2.416\%$  

The rates we have calculated are summarized in Table 4.4. A chart showing the zero. rate as a function of maturity is known as the zero curve.A common assumption is that. the zero curve is linear between the points determined using the bootstrap method. (This means that the 1.25-year zero rate is $0.5\times2.225+0.5\times2.284=2.255\%$ in our example.) It is also usually assumed that the zero curve is horizontal prior to the first point and horizontal beyond the last point. Figure 4.1 shows the zero curve for our data using these assumptions. By using longer maturity bonds, the zero curve would be more accurately determined beyond 2 years.  

Table 4.4 Continuously compounded zero rates determined from data in Table 4.3.   


<html><body><table><tr><td>Maturity (years)</td><td>Zerorate (% continuously compounded)</td></tr><tr><td>0.25</td><td>1.603</td></tr><tr><td>0.50</td><td>2.010</td></tr><tr><td>1.00</td><td>2.225</td></tr><tr><td>1.50</td><td>2.284</td></tr><tr><td>2.00</td><td>2.416</td></tr></table></body></html>  

In practice, we do not usually have bonds with maturities equal to exactly 1.5 years, 2 years, 2.5 years, and so on. One approach is to interpolate between the bond price data. before it is used to calculate the zero curve. For example, if it is known that a 2.3-year. bond with a coupon of $6\%$ sells for 108 and a 2.7-year bond with a coupon of $6.5\%$ sells for 109, it might be assumed that a 2.5-year bond with a coupon of $6.25\%$ would sell for 108.5.Another more general procedure is as follows. Define $t_{1}$ $\ldots,t_{2},\ldots\ldots,t_{n}$ as the maturities of the instruments whose prices are to be matched. Assume a piecewise linear curve with. corners at these times. Use an iterative "trial and error" procedure to determine the rate at time $t_{1}$ that matches the price of the first instrument, then use a similar procedure to. determine the rate at time $t_{2}$ that matches the price of the second instrument, and so on. For any trial rate, the rates used for coupons are determined by linear interpolation.  

A more sophisticated approach is to use polynomial or exponential functions, rather than linear functions, for the zero curve between times $t_{i}$ and $t_{i+1}$ for all i. The functions. are chosen so that they price the bonds correctly and so that the gradient of the zero curve does not change at any of the. $t_{i}.$ This is referred to as using a spline function for the zero curve..  

![](images/311c6934218c617b2c09737f73581d9380f06ddfddc88d57ea7b576823003f51.jpg)  
Figure 4.1 Zero rates given by the bootstrap method.  
