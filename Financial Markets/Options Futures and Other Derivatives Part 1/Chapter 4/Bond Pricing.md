---
tags:
  - '#bond_pricing'
  - '#bond_valuation'
  - '#bond_yield'
  - '#continuous_compounding'
  - '#coupon_payments'
  - '#par_yield'
  - '#present_value'
  - '#zero_rates'
---
# 4.6 BOND PRICING  

Most bonds pay coupons to the holder periodically. The bond's principal (which is also known as its par value or face value) is paid at the end of its life. The theoretical price of a bond can be calculated as the present value of all the cash flows that will be received by the owner of the bond. Sometimes bond traders use the same discount rate for all the cash flows underlying a bond, but a more accurate approach is to use a. different zero rate for each cash flow..  

To illustrate this, consider the situation where zero rates, measured with continuous compounding, are as in Table 4.2. (We explain later how these can be calculated.) Suppose that a 2-year bond with a principal of. $\$100$ provides coupons at the rate of $6\%$ per annum semiannually. To calculate the present value of the first coupon of. $\$3$ , we discount it at $5.0\%$ for 6 months; to calculate the present value of the second coupon. of $\$3$ , we discount it at $5.8\%$ for 1 year; and so on. Therefore, the theoretical price of. the bond is  

$$
3e^{-0.05\times0.5}+3e^{-0.058\times1.0}+3e^{-0.064\times1.5}+103e^{-0.068\times2.0}=98.39
$$  

or $\$98.39$ . (DerivaGem can be used to calculate bond prices.)  

# Bond Yield  

A bond's yield is the single discount rate that, when applied to all cash flows, gives a bond price equal to its market price. Suppose that the theoretical price of the bond we have been considering, $\$98.39$ , is also its market value (i.e., the market's price of the. bond is in exact agreement with the data in Table 4.2). If. $y$ is the yield on the bond,. expressed with continuous compounding, it must be true that.  

$$
3e^{-y\times0.5}+3e^{-y\times1.0}+3e^{-y\times1.5}+103e^{-y\times2.0}=98.39
$$  

This equation can be solved using an iterative ("trial and error") procedure to give y = 6.76%.3  

Table 4.2 Zero rates.   


<html><body><table><tr><td>Maturity (years)</td><td>Zerorate (% continuously compounded)</td></tr><tr><td>0.5</td><td>5.0</td></tr><tr><td>1.0</td><td>5.8</td></tr><tr><td>1.5</td><td>6.4</td></tr><tr><td>2.0</td><td>6.8</td></tr></table></body></html>  

# Par Yield  

The par yield for a certain bond maturity is the coupon rate that causes the bond price to equal its par value. (The par value is the same as the principal value.) Usually the bond is assumed to provide semiannual coupons. Suppose that the coupon on a 2-year bond in our example is $c$ per annum (or $\frac{1}{2}c$ per 6 months). Using the zero rates in Table 4.2, the. value of the bond is equal to its par value of 100 when.  

$$
{\frac{c}{2}}e^{-0.05\times0.5}+{\frac{c}{2}}e^{-0.058\times1.0}+{\frac{c}{2}}e^{-0.064\times1.5}+{\bigg(}100+{\frac{c}{2}}{\bigg)}e^{-0.068\times2.0}=100
$$  

This equation can be solved in a straightforward way to give $c=6.87$ . The 2-year par yield is therefore. $6.87\%$ per annum.  

More generally, if $d$ is the present value of $\$1$ received at the maturity of the bond, $A$ is the value of an annuity that pays one dollar on each coupon payment date, and $m$ is the number of coupon payments per year, then the par yield $c$ must satisfy  

$$
100=A{\frac{c}{m}}+100d
$$  

so that  

$$
c=\frac{(100-100d)m}{A}
$$  

In our example, $m=2$ $d=e^{-0.068\times2}=0.87284$ , and  

$$
A=e^{-0.05\times0.5}+e^{-0.058\times1.0}+e^{-0.064\times1.5}+e^{-0.068\times2.0}=3.70027
$$  

The formula confirms that the par yield is $6.87\%$ per annum. A bond with this coupon and semiannual payments is worth par.  
