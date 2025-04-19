---
tags:
  - '#continuously_compounded'
  - '#forward_rate_agreement'
  - '#forward_rates'
  - '#instantaneous_forward_rate'
  - '#interest_rates'
  - '#maturity'
  - '#zero_coupon_bond'
  - '#zero_rates'
---
# 4.8 FORWARD RATES  

Forward interest rates are the rates of interest implied by current zero rates for periods of time in the future. To illustrate how they are calculated, we suppose that zero rates. are as shown in the second column of Table 4.5. The rates are assumed to be continuously compounded. Thus, the. $3\%$ per annum rate for 1 year means that, in. return for an investment of $\$100$ today, an amount. $100e^{0.03\times1}=\S\dot{1}03.05$ is received in. 1 year; the. $4\%$ per annum rate for 2 years means that, in return for an investment of. $\$100$ today, an amount. $100e^{0.04\times2}=\dot{\mathbb{\S}}108.33$ is received in 2 years; and so on.  

The forward interest rate in Table 4.5 for year 2 is $5\%$ per annum. This is the rate of interest that is implied by the zero rates for the period of time between the end of the first year and the end of the second year. It can be calculated from the 1-year zero interest rate of $3\%$ per annum and the 2-year zero interest rate of. $4\%$ per annum. It is the rate of interest for year 2 that, when combined with $3\%$ per annum for year 1, gives $4\%$ overall for the 2 years. To show that the correct answer is $5\%$ per annum, suppose that $\$100$ is invested. A rate of $3\%$ for the first year and $5\%$ for the second year gives  

$$
100e^{0.03\times1}e^{0.05\times1}=\$108.33
$$  

at the end of the second year. A rate of $4\%$ per annum for 2 years gives.  

$$
100e^{0.04\times2}
$$  

which is also. $\$108.33$ This example illustrates the general result that when interest rates are continuously compounded and rates in successive time periods are combined, the overall equivalent rate is simply the average rate during the whole period. In our example, $3\%$ for the first year and. $5\%$ for the second year average to $4\%$ over the 2 years. The result is only approximately true when the rates are not continuously compounded.  

The forward rate for year 3 is the rate of interest that is implied by a $4\%$ per annum 2-year zero rate and a. $4.6\%$ per annum 3-year zero rate. It is. $5.8\%$ per annum. The. reason is that an investment for 2 years at. $4\%$ per annum combined with an investment. for one year at. $5.8\%$ per annum gives an overall average return for the three years of $4.6\%$ per annum. The other forward rates can be calculated similarly and are shown in the third column of the table. In general, if. $R_{1}$ and $R_{2}$ are the zero rates for maturities  

Table 4.5 Calculation of forward rates.   


<html><body><table><tr><td>Year (n)</td><td>Zerorateforan n-yearinvestment (% per annum)</td><td>Forwardrate fornthyear (% per annum)</td></tr><tr><td>1</td><td>3.0</td><td></td></tr><tr><td>2</td><td>4.0</td><td>5.0</td></tr><tr><td>3</td><td>4.6</td><td>5.8</td></tr><tr><td>4</td><td>5.0</td><td>6.2</td></tr><tr><td>5</td><td>5.3</td><td>6.5</td></tr></table></body></html>  

$T_{1}$ and $T_{2}$ , respectively, and $R_{F}$ is the forward interest rate for the period of time between $T_{1}$ and $T_{2}$ , then  

$$
R_{F}=\frac{R_{2}T_{2}-R_{1}T_{1}}{T_{2}-T_{1}}
$$  

To illustrate this formula, consider the calculation of the year-4 forward rate from the data in Table 4.5: $T_{1}=3$ $T_{2}=4$ $R_{1}=0.046$ , and $R_{2}=0.05$ , and the formula gives $R_{F}=0.062$  

Equation (4.5) can be written as  

$$
R_{F}=R_{2}+(R_{2}-R_{1})\frac{T_{1}}{T_{2}-T_{1}}
$$  

This shows that,if the zero curve is upward sloping between $T_{1}$ and $T_{2}$ so that $R_{2}>R_{1}$ then $R_{F}>R_{2}$ (i.e., the forward rate for a period of time ending at $T_{2}$ is greater than the $T_{2}$ zero rate). Similarly, if the zero curve is downward sloping with $R_{2}<R_{1}$ , then $R_{F}<R_{2}$ (i.e., the forward rate is less than the $T_{2}$ zero rate). Taking limits as $T_{2}$ approaches $T_{1}$ in equation (4.6) and letting the common value of the two be $T$ , we obtain  

$$
R_{F}=R+T\frac{\partial R}{\partial T}
$$  

where $R$ is the zero rate for a maturity of. $T.$ The value of. $R_{F}$ obtained in this way is known as the instantaneous forward rate for a maturity of. $T.$ This is the forward rate. that is applicable to a very short future time period that begins at time T. Define $P(0,T)$ as the price of a zero-coupon bond maturing at time $T$ Because $P(0,T)=e^{-R T}$ , the equation for the instantaneous forward rate can also be written as.  

$$
R_{F}=-\frac{\partial}{\partial T}\ln P(0,T)
$$  

If a large financial institution can borrow or lend at the rates in Table 4.5, it can lock in the forward rates. For example, it can borrow $\$100$ at $3\%$ for 1 year and invest the money at $4\%$ for 2 years, the result is a cash outflow of $100e^{0.03\times1}=\S103.05$ at the end of year 1 and an inflow of $100e^{0.04\times2}=\$108.33$ at the end of year 2. Since $108.33=103.05e^{0.05}$ , a return equal to the forward rate $(5\%)$ is earned on $\$103.05$ during the second year. Alternatively, it can borrow $\$100$ for 4 years at $5\%$ and invest it for 3 years at $4.6\%$ . The result is a cash inflow of $100e^{0.046\times3}=\S114.80$ at the end of the third year and a cash outflowof $100e^{0.05\times4}=\$122.14$ at the end of the fourth year.Since $122.14=114.80e^{0.062}$ money is being borrowed for the fourth year at the forward rate of $6.2\%$  

If a large investor thinks that rates in the future will be different from today's forward rates, there are many trading strategies that the investor will find attractive (see Business Snapshot 4.1). One of these involves entering into a contract known as a forward rate agreement. We will now discuss how this contract works and how it is valued.  
