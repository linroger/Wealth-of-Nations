---
tags:
  - amortization
  - fixed_rate_mortgage
  - interest_rate
  - monthly_payments
  - mortgage_loans
aliases:
  - 30-year mortgage
  - Fixed-Rate Mortgage
  - Mortgage Amortization
key_concepts:
  - Amortization table example
  - Fixed-rate mortgage loans
  - Monthly payment calculation
  - Mortgage amortization graphically
  - Principal and interest components
---

# 15.2 FIXED-RATE MORTGAGE LOANS  

Though terms of 10, 15, and 20 years are also available, the most common mortgage is a 30-year, fixed-rate, level payment mortgage. For example, a. homeowner might borrow $\$100,000$ from a bank at $4.5\%$ and agree to make payments of $\$506.6853$ every month for 30 years. (The extra decimal places are given to help the reader reproduce the calculations to follow.) The loan rate and the monthly payment are related by,.  

$$
\begin{array}{c}{{\displaystyle\S S06.6853\sum_{n=1}^{360}\frac{1}{\left(1+\frac{4.50\%}{12}\right)^{n}}=\S100,000}}\ {{\displaystyle\left.\left\{3506.6853\frac{12}{4.50\%}\right[1-\frac{1}{\left(1+\frac{4.50\%}{12}\right)^{360}}\right]=\S100,000}}\end{array}
$$  

where Equation (15.2) follows by applying Equation (A2.16).  

These equations say that, at a rate of $4.5\%$ , the present value of the monthly payments on the mortgage over its 30-year or 360-month life equals the initial loan amount of $\$100,000$ . This relationship is simply a market convention to define a monthly payment from a mortgage rate, just as price is quoted given yield to maturity or vice versa. Truly pricing a mortgage loan is much more complicated, of course, with the need to account for a term structure of risk-free rates, the value of the prepayment option, and a spread or term structure of spreads to reflect credit risk.  

The market convention of a single rate to describe a mortgage loan is also used to divide its monthly payments into interest and principal components. Table 15.4 gives selected rows of the amortization table for the mortgage just described, with the monthly payment rounded to $\$506.69$ . The starting balance is $\$100,000$ . The interest component of the first payment is the interest on that starting balance at a rate of $4.50\%$ , that is, $\$100,000$ . The principal component of the first payment is simply the total monthly payment, fixed at $\$506.69$ , minus the interest component of $\$375.00$ , or $\$131.69$ . Given this breakdown, the ending balance of the loan at the end of the first month is the starting balance minus the first principal payment, that is, $\$100,000$ minus $\$131.69$ or $\$99,868.31$ . For the second payment, interest on the outstanding balance at the end of the first month is $\$99,868.31\times4.50\%/12=\$374.51$ ; the principal payment is $\$506.69-4374.51=$ ; and the ending balance is $\$99$ $,868.31-\$132.18=\$99$ , 736.14. Subsequent payments are handled analogously.  

Appendix A15.1 shows that, using this method of amortizing principal,. the ending balance at any time equals the present value of all remaining payments discounted at the original interest rate. Applied to the example, the balances at the end of five years, or 60 months (300 months remaining), and at the end of 10 years, or 120 months (240 months remaining), are shown in the table and can be computed, respectively, by the following equations,  

TABLE 15.4 Selected Rows of a Mortgage Amortization Table for a 30-Year $\$100,000$ Mortgage at $4.5\%$ . The Total Monthly Payment Is $\$506.69$ . Entries Are in Dollars..   


<html><body><table><tr><td>Payment Month</td><td>Interest Payment</td><td>Principal Payment</td><td>Ending Balance</td></tr><tr><td></td><td></td><td></td><td>100,000.00</td></tr><tr><td>1</td><td>375.00</td><td>131.69</td><td>99,868.31</td></tr><tr><td>2</td><td>374.51</td><td>132.18</td><td>99,736.14</td></tr><tr><td>3</td><td>374.01</td><td>132.67</td><td>99,603.46</td></tr><tr><td>4</td><td>373.51</td><td>133.17</td><td>99,470.29</td></tr><tr><td>5</td><td>373.01</td><td>133.67</td><td>99,336.62</td></tr><tr><td>60</td><td>342.46</td><td>164.23</td><td>91,157.92</td></tr><tr><td>120</td><td>301.11</td><td>205.58</td><td>80,089.43</td></tr><tr><td>358</td><td>5.66</td><td>501.03</td><td>1,007.70</td></tr><tr><td>359</td><td>3.78</td><td>502.91</td><td>504.79</td></tr><tr><td>360</td><td>1.89</td><td>504.79</td><td>0.00</td></tr></table></body></html>  

$$
\Im506.6853\frac{12}{4.50\%}\left[1-\frac{1}{\left(1+\frac{4.50\%}{12}\right)^{300}}\right]=\S91,157.92
$$  

$$
\Im506.6853\frac{12}{4.50\%}\left[1-\frac{1}{\left(1+\frac{4.50\%}{12}\right)^{240}}\right]=\S80,089.43
$$  

Figure 15.1 depicts the amortization of this mortgage graphically. For each month, against the left axis, the height of the dark-shaded area represents the principal component of that month's payment; the height of the light-shaded area represents the interest component; and the total height, or sum, equals the fixed total payment of $\$506.69$ . The black curve, against the right axis, gives the ending balance or principal outstanding at the end of each month. The figure clearly illustrates the banker's adage that "interest lives off principal," that is, as principal is paid off, interest payments decline. Interest constitutes $\$375.00/\$506.69$ or $74.0\%$ of the first monthly payment; $\$342.46/\$506.69$ or $67.6\%$ of the 60th payment; $\$301.11/\$506.69$ or $59.4\%$ of the 120th payment; etc.; and $\$1.89/\$506.69$ or $0.4\%$ of the final payment. While not shown in the figure, the higher the loan rate, the greater the monthly payment, and the greater the proportion of each payment that is dedicated to interest.  

![](a1e21b018fdbdb86fe98a6a38d092043864f482ce79594d92f842795388e008f.jpg)  
FIGURE 15.1 Amortization of a 30-Year $\$100,000$ Mortgage at $4.5\%$  
