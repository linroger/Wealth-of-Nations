---
tags:
  - bond_pricing
  - discount_factors
  - present_value
  - term_structure
  - treasury_bonds
aliases:
  - Discount Factor
  - Present Value
  - d(t)
key_concepts:
  - Bonds and discount factors
  - Discount factor definition
  - Present value of currency
  - US Treasury bonds
  - Value decreases with term
---

# 1.2 DISCOUNT FACTORS  

The discount factor for a particular term gives the value today, or the present. value, of one unit of currency to be received at the end of that term. Denote the discount factor for $t$ years by $d(t)$ . Then, for example, if. $d(3.0)=0.99$ the present value of. $\$1$ to be received in three years is 99 cents.  

Because Treasury bonds promise future cash flows, discount factors can be extracted from Treasury bond prices. In fact, the rows of Table 1.2 can be. used to write equations that relate bond prices to discount factors. Starting. with the first row of the table, that is, with the bond maturing in six months,  

$$
101.4297=\left(100+{\frac{2.875}{2}}\right)d(0.5)
$$  

In words, the price of the 2.875s of 11/15/2021 equals the present value of its future cash flows, or, more precisely, the sum of its principal and  

coupon cash flows multiplied by the discount factor for funds to be received in six months. Solving,. $d(.5)=0.999923.$ 2  

By the same reasoning, the equations relating prices to discount factors can be written for the other bonds in Table 1.2. For the next two bonds, which mature in one year and in 1.5 years, respectively,  

$$
\begin{array}{l}{{102.0662=\frac{2.125}{2}d(0.5)+\left(100+\frac{2.125}{2}\right)d(1.0)}}\ {{{}}}\ {{102.2862=\frac{1.625}{2}d(0.5)+\frac{1.625}{2}d(1.0)+\left(100+\frac{1.625}{2}\right)d(1.0)+{}}}\end{array}
$$  

Given the solution for $d(0.5)$ , from Equation (1.1), Equation (1.2) can be solved for $d(1)$ . Then, given the solutions for both $d(0.5)$ and $d(1.0)$ Equation (1.3) can be solved for $d(1.5)$ . Continuing in this way through the rows of Table 1.2 solves for the discount factors, in six-month intervals, out to three and one-half years. Table 1.3 reports these results. That these discount factors fall as term increases reflects the time value of money: the longer a payment of $\$1$ is delayed, the less it is worth today.3  

Figure 1.1 shows discount factors, in six-month intervals, from the. bonds listed in Table 1.2 and other bonds, not shown here, which have maturity dates on November 15 and May 15 out to 10 years. Discount factors can again be seen to decrease with term, with the value of. $\$1$ to be received in 10 years worth less than 85 cents as of the pricing date..  

TABLE 1.3Discount Factors Derived from Bonds Listed in Table 1.2.   


<html><body><table><tr><td>Term</td><td>DiscountFactor</td></tr><tr><td>0.5</td><td>0.999923</td></tr><tr><td>1.0</td><td>0.999419</td></tr><tr><td>1.5</td><td>0.998504</td></tr><tr><td>2.0</td><td>0.997041</td></tr><tr><td>2.5</td><td>0.994558</td></tr><tr><td>3.0</td><td>0.990195</td></tr><tr><td>3.5</td><td>0.984742</td></tr></table></body></html>  

![](208ab44a0a07ebbb9e3253325f91e588400001d592c50ae19aa14609b7e21ae2.jpg)  
FIGure 1.1 Discount Factors Derived from Selected US Treasury Bonds, as of May 14, 2021.  
