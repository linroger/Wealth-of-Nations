---
tags:
  - '#bond_duration'
  - '#bond_portfolio'
  - '#bond_pricing'
  - '#bond_yield'
  - '#dollar_duration'
  - '#dv01'
  - '#modified_duration'
  - '#yield_curve'
---
# 4.10 DURATION  

The duration of a bond, as its name implies, is a measure of how long the holder of the bond has to wait before receiving the present value of the cash payments. A zero-. coupon bond that lasts $n$ years has a duration of $n$ years. However, a coupon-bearing bond lasting $n$ years has a duration of less than $n$ years, because the holder receives. some of the cash payments prior to year. $n$  

Suppose that a bond provides the holder with cash flows $c_{i}$ at time $t_{i}$ $1\leq i\leq n$ ). The bond price $B$ and bond yield. $y$ (continuously compounded) are related by  

$$
B=\sum_{i=1}^{n}c_{i}e^{-y t_{i}}
$$  

The duration of the bond, $D$ , is defined as  

$$
D={\frac{\sum_{i=1}^{n}t_{i}c_{i}e^{-y t_{i}}}{B}}
$$  

This can be written  

$$
D=\sum_{i=1}^{n}t_{i}\biggl[\frac{c_{i}e^{-y t_{i}}}{B}\biggr]
$$  

The term in square brackets is the ratio of the present value of the cash flow at time $t_{i}$ to the bond price. The bond price is the present value of all payments. The duration is therefore a weighted average of the times when payments are made, with the weight applied to time $t_{i}$ being equal to the proportion of the bond's total present value provided by the cash flow at time. $t_{i}$ The sum of the weights is 1.0. Note that, for the purposes of the definition of duration, all discounting is done at the bond yield rate of interest, $y$ (We do not use a different zero rate for each cash flow in the way described in Section 4.6.)  

When a small change. $\Delta y$ in the yield is considered, it is approximately true that  

$$
\Delta B=\frac{d B}{d y}\Delta y
$$  

From equation (4.7), this becomes  

$$
\Delta B=-\Delta y\sum_{i=1}^{n}c_{i}t_{i}e^{-y t_{i}}
$$  

(Note that there is a negative relationship between $B$ and $y$ . When bond yields increase, bond prices decrease. When bond yields decrease, bond prices increase.) From equations (4.8) and (4.10), the key duration relationship is obtained:  

$$
\Delta B=-B D\Delta y
$$  

This can be written  

$$
\frac{\Delta B}{B}=-D\Delta y
$$  

Equation (4.12) is an approximate relationship between percentage changes in a bond. price and changes in its yield. It is easy to use and is the reason why duration, first suggested by Frederick Macaulay in 1938, has become such a popular measure..  

Consider a 3-year $10\%$ coupon bond with a face value of $\$100.5$ uppose that the yield on the bond is $12\%$ per annum with continuous compounding. This means that $y=0.12$ . Coupon payments of $\$5$ are made every 6 months. Table 4.6 shows the calculations necessary to determine the bond's duration. The present values of the bond's cash flows, using the yield as the discount rate, are shown in column 3 (e.g., the present value of the first cash flow is $5e^{-0.12\times0.5}=4.709;$ . The sum of the numbers in column 3 gives the bond's price as 94.213. The weights are calculated by dividing the numbers in column 3 by 94.213. The sum of the numbers in column 5 gives the duration as 2.653 years.  

DV01 is the price change from a 1-basis-point increase in all rates. Gamma is the change in DV01 from a 1-basis-point increase in all rates. The following example investigates the accuracy of the duration relationship in equation (4.11).  

Table 4.6 Calculation of duration.   


<html><body><table><tr><td>Time (years)</td><td>Cash flow ($)</td><td>Present value</td><td>Weight</td><td>Time X weight</td></tr><tr><td>0.5</td><td>5</td><td>4.709</td><td>0.050</td><td>0.025</td></tr><tr><td>1.0</td><td>5</td><td>4.435</td><td>0.047</td><td>0.047</td></tr><tr><td>1.5</td><td>5</td><td>4.176</td><td>0.044</td><td>0.066</td></tr><tr><td>2.0</td><td>5</td><td>3.933</td><td>0.042</td><td>0.083</td></tr><tr><td>2.5</td><td>5</td><td>3.704</td><td>0.039</td><td>0.098</td></tr><tr><td>3.0</td><td>105</td><td>73.256</td><td>0.778</td><td>2.333</td></tr><tr><td></td><td>130</td><td>94.213</td><td>1.000</td><td>2.653</td></tr></table></body></html>  

# Example 4.4  

For the bond in Table 4.6, the bond price, $B$ , is 94.213 and the duration,. $D$ , is 2.653, so that equation (4.11) gives  

$$
\Delta B=-94.213\times2.653\times\Delta y
$$  

or  

$$
\Delta B=-249.95\times\Delta y
$$  

When the yield on the bond increases by 10 basis points. $(=0.1\%$ ), $\Delta y=+0.001$ The duration relationship predicts that. $\Delta B=-249.95\times0.001=-0.250$ , so that. the bond price goes down to $94.213-0.250=93.963$ . How accurate is this?. Valuing the bond in terms of its yield in the usual way, we find that, when the bond yield increases by 10 basis points to. $12.1\%$ , the bond price is.  

$$
\begin{array}{c}{{5e^{-0.121\times0.5}+5e^{-0.121\times1.0}+5e^{-0.121\times1.5}+5e^{-0.121\times2.0}}}\ {{+5e^{-0.121\times2.5}+105e^{-0.121\times3.0}=93.963}}\end{array}
$$  

which is (to three decimal places) the same as that predicted by the duration relationship.  

# Modified Duration  

The preceding analysis is based on the assumption that $y$ is expressed with continuous compounding. If $y$ is expressed with annual compounding, it can be shown that the approximate relationship in equation (4.11) becomes  

$$
\Delta B=-\frac{B D\Delta y}{1+y}
$$  

More generally, if $y$ is expressed with a compounding frequency of $m$ times per year, then  

$$
\Delta B=-\frac{B D\Delta y}{1+y/m}
$$  

A variable $D^{*}$ , defined by  

$$
\boldsymbol{D}^{*}=\frac{\boldsymbol{D}}{1+\boldsymbol{y}/m}
$$  

is sometimes referred to as the bond's modified duration. It allows the duration relationship to be simplified to.  

$$
\Delta B=-B D^{*}\Delta y
$$  

when $y$ is expressed with a compounding frequency of. $m$ times per year. The following.   
example investigates the accuracy of the modified duration relationship.  

# Example 4.5  

The bond in Table 4.6 has a price of 94.213 and a duration of 2.653. The yield, expressed with semiannual compounding is. $12.3673\%$ . The modified duration,. $D^{*}$ is given by  

$$
D^{*}=\frac{2.653}{1+0.123673/2}=2.499
$$  

From equation (4.13),  

$$
\Delta B=-94.213\times2.499\times\Delta y
$$  

or  

$$
\Delta B=-235.39\times\Delta y
$$  

When the yield (semiannually compounded) increases by 10 basis points $(=0.1\%$ we have $\Delta y=+0.001$ . The duration relationship predicts that we expect $\Delta B$ to be $-235.39\times0.001=-0.235$ , so that the bond price goes down to $94.213-0.235=$ 93.978. How accurate is this? An exact calculation similar to that in the previous example shows that, when the bond yield (semiannually compounded) increases by 10 basis points to $12.4673\%$ , the bond price becomes 93.978. This shows that the modified duration calculation gives good accuracy for small yield changes.  

Another term that is sometimes used is dollar duration. This is the product of modified duration and bond price, so that. $\Delta B=-D_{\S}\Delta y$ where $D_{\mathbb{S}}$ is dollar duration.  

# Bond Portfolios  

The duration, $D$ , of a bond portfolio can be defined as a weighted average of the durations of the individual bonds in the portfolio, with the weights being proportional to the bond prices. Equations (4.11) to (4.13) then apply, with $B$ being defined as the value of the bond portfolio. They estimate the change in the value of the bond portfolio for a small change $\Delta y$ in the yields of all the bonds.  

It is important to realize that, when duration is used for bond portfolios, there is an. implicit assumption that the yields of all bonds will change by approximately the same. amount. When the bonds have widely differing maturities, this happens only when there is a parallel shift in the zero-coupon yield curve. We should therefore interpret equations (4.11) to (4.13) as providing estimates of the impact on the price of a bond portfolio of a small parallel shift, $\Delta y$ , in the zero curve.  

By choosing a portfolio so that the duration of assets equals the duration of liabilities (i.e., the net duration is zero), a financial institution eliminates its exposure to small parallel shifts in the yield curve. But it is still exposed to shifts that are either large or nonparallel.  
