---
tags:
  - '#annual_compounding'
  - '#compounding_frequency'
  - '#continuous_compounding'
  - '#equivalent_interest_rates'
  - '#exponential_function'
  - '#interest_rate_conversion'
  - '#interest_rate_measurement'
  - '#natural_logarithm'
  - '#semiannual_compounding'
---
# 4.4 MEASURING INTEREST RATES  

A statement by a bank that the interest rate on one-year deposits is. $10\%$ per annum sounds straightforward and unambiguous. In fact, its precise meaning depends on the way the interest rate is measured..  

Table 4.1 Effect of the compounding frequency on the value of $\$100$ at the end of 1 year when the interest rate is $10\%$ per annum.   


<html><body><table><tr><td>Compoundingfrequency</td><td>Valueof$100 atend ofyear($)</td></tr><tr><td>Annually (m = 1)</td><td>110.00</td></tr><tr><td>Semiannually (m = 2)</td><td>110.25</td></tr><tr><td>Quarterly (m = 4)</td><td>110.38</td></tr><tr><td>Monthly (m = 12)</td><td>110.47</td></tr><tr><td>Weekly (m = 52)</td><td>110.51</td></tr><tr><td>Daily (m = 365)</td><td>110.52</td></tr></table></body></html>  

If the interest rate is measured with annual compounding, the bank's statement that the interest rate is $10\%$ means that $\$100$ grows to  

$$
\$100\times1.1=\$110
$$  

at the end of 1 year. When the interest rate is measured with semiannual compounding, it means that $5\%$ is earned every 6 months, with the interest being reinvested. In this case, $\$100$ grows to  

$$
\$100\times1.05\times1.05=\$110.25
$$  

at the end of 1 year. When the interest rate is measured with quarterly compounding the bank's statement means that $2.5\%$ is earned every 3 months, with the interest being reinvested. The $\$100$ then grows to  

$$
\$100\times1.025^{4}=\$110.38
$$  

at the end of 1 year. Table 4.1 shows the effect of increasing the compounding frequency further.  

The compounding frequency defines the units in which an interest rate is measured.A. rate expressed with one compounding frequency can be converted into an equivalent rate with a different compounding frequency. For example, from Table 4.1 we see that. $10.25\%$ with annual compounding is equivalent to. $10\%$ with semiannual compounding. We can think of the difference between one compounding frequency and another to be analogous to the difference between kilometers and miles. They are two different units of measurement.  

To generalize our results, suppose that an amount $A$ is invested for $n$ years at an interest rate of $R$ per annum. If the rate is compounded once per annum, the terminal value of the investment is  

$$
A(1+R)^{n}
$$  

If the rate is compounded $m$ times per annum, the terminal value of the investment is  

$$
A{\biggl(}1+{\frac{R}{m}}{\biggr)}^{m n}
$$  

When $m=1$ , the rate is sometimes referred to as the equivalent annual interest rate.  

Suppose $R_{1}$ is an interest rate when compounding is $m_{1}$ times per year and $R_{2}$ is the equivalent rate when compounding is $m_{2}$ times per year. From equation (4.1), the values of an investment of $A$ after $n$ years is the same if:  

This means that  

$$
A\biggl(1+\frac{R_{1}}{m_{1}}\biggr)^{m_{1}n}=A\biggl(1+\frac{R_{2}}{m_{2}}\biggr)^{m_{2}n} 
$$  

$$
R_{2}=m_{2}\bigg[\bigg(1+{\frac{R_{1}}{m_{1}}}\bigg)^{m_{1}/m_{2}}-1\bigg]
$$  

As an example of the application of this formula, suppose that an interest rate is $6\%$ with semiannual compounding. The equivalent rate with quarterly compounding can be calculated by setting $m_{1}=2$ $R_{1}=0.06$ , and $m_{2}=4$ . It is:  

$$
R_{2}=4\bigg[\bigg(1+\frac{0.06}{2}\bigg)^{2/4}-1\bigg]=0.0596
$$  

or $5.96\%$  

# Continuous Compounding  

The limit as the compounding frequency, $m$ , tends to infinity is known as continuous compounding.? With continuous compounding, it can be shown that an amount $A$ invested for $n$ years at rate $R$ grows to  

$$
A e^{R n}
$$  

where $e$ is approximately 2.71828. The exponential function, $e^{x}$ , is built into most. calculators, so the computation of the expression in equation (4.2) presents no problems. In the example in Table. $4.1,A=100,n=1$ , and $R=0.1$ , so that the value to which. $A$ grows with continuous compounding is  

$$
100e^{0.1}=\$110.52
$$  

This is (to two decimal places) the same as the value with daily compounding. For most practical purposes, continuous compounding can be thought of as being equivalent to daily compounding. Compounding a sum of money at a continuously compounded rate $R$ for $n$ years involves multiplying it by $e^{R n}$ . Discounting it at a continuously compounded rate $R$ for $n$ years involves multiplying by $e^{-R n}$  

In this book, interest rates will be measured with continuous compounding except where stated otherwise. Readers used to working with interest rates that are measured with annual, semiannual, or some other compounding frequency may find this a little strange at first. However, continuously compounded interest rates are used to such a great extent in pricing derivatives that it makes sense to get used to working with them now.  

Suppose that $R_{c}$ is a rate of interest with continuous compounding and $R_{m}$ is the equivalent rate with compounding $m$ times per annum. From the results in equations (4.1) and (4.2), we have  

$$
A e^{R_{c}n}=A{\left(1+{\frac{R_{m}}{m}}\right)}^{m n}
$$  

or  

$$
e^{R_{c}}=\left(1+\frac{R_{m}}{m}\right)^{m}
$$  

This means that  

$$
R_{c}=m\ln\left(1+{\frac{R_{m}}{m}}\right)
$$  

and  

$$
R_{m}=m(e^{R_{c}/m}-1)
$$  

These equations can be used to convert a rate with a compounding frequency of $m$ times per annum to a continuously compounded rate and vice versa. The natural logarithm function ln $x$ , which is built into most calculators, is the inverse of the exponential function, so that, if $y=\ln x $ then $x=e^{y}$  

# Example 4.1  

Consider an interest rate that is quoted as $10\%$ per annum with semiannual compounding. From equation (4.3) with $m=2$ and $R_{m}=0.1$ , the equivalent rate with continuous compounding is  

$$
2\ln\left(1+{\frac{0.1}{2}}\right)=0.09758
$$  

or $9.758\%$ per annum.  

# Example 4.2  

Suppose that a lender quotes the interest rate on loans as $8\%$ per annum with continuous compounding, and that interest is actually paid quarterly. From equation (4.4) with $m=4$ and $R_{c}=0.08$ , the equivalent rate with quarterly. compounding is  

$$
4\times(e^{0.08/4}-1)=0.0808
$$  

or $8.08\%$ per annum. This means that on a $\$1,000$ loan, interest payments of $\$20.20$ would be required each quarter.  
