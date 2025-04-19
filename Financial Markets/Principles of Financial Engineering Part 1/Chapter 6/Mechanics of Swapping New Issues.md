---
tags:
  - bond_issuance
  - currency_swap
  - euromarkets
  - fixed_rate
  - interest_rate_swap
aliases:
  - GBP/USD Swaps
  - New Issue Swaps
  - Swap Mechanics
key_concepts:
  - All-in-cost calculation
  - Currency market considerations
  - Effective cost of funds
  - Floating rate Eurobond
  - Interest rate swap engineering
  - Internal rate of return
---

# 6.9 MECHANICS OF SWAPPING NEW ISSUES  

# 6.9.1 INTEREST RATE AND CURRENCY SWAP EXAMPLE  

In the context of interest rate swap engineering, we noted that the basic cash flow engineering for swaps ignores several minor technical points that need to be considered in practice. We provided a real-life example of interest rate swap usage and highlighted quoting conventions and costs. Similarly, in this chapter, our discussion of swap engineering in currency markets has abstracted away from important real-world considerations. Therefore, here we provide another real-world application to new bond issues.  

Suppose there is an A-rated British entity that would like to borrow 100 million sterling (GBP) for a period of 3 years. The entity has no preference toward either floating or fixed-rate funding, and intends to issue in Euromarkets. Market research indicates that if the entity went ahead with its plans, it could obtain fixed-rate funds at $6.5\%$ annually.16 But the bank recommends the following approach.  

It appears that there are nice opportunities in USD-GBP currency swaps, and it makes more sense to issue a floating rate Eurobond in the UsD sector with fixed coupons. The swap market quotes funding at $\operatorname{LIBOR}+95$ bp in GBP against USD rates for this entity. Then the proceeds can. be swapped into sterling for a lower all-in-cost. How would this operation work? And what are the risks?  

We begin with the data concerning the new issue. The parameters of the newly issued bond are provided in Table 6.1.17 Now, the issuer would like to swap these proceeds to floating rate GBP funds. In doing this, the issuer faces the market conditions as provided in Table 6.2. We first work out the original and the swapped cash flows and then calculate the all-in-cost, which is the real cost of funds to the issuer after the proceeds are swapped into GBP.  

<html><body><table><tr><td colspan="2">Table 6.1The New Issue</td></tr><tr><td>Amount</td><td>USD100million</td></tr><tr><td>Maturity</td><td>2 years</td></tr><tr><td>Coupon</td><td>6% p.a.</td></tr><tr><td>Issue price</td><td>2001</td></tr><tr><td>Options</td><td>None</td></tr><tr><td>Listing</td><td>Luxembourg</td></tr><tr><td>Commissions</td><td>14</td></tr><tr><td>Expenses</td><td>USD75000</td></tr><tr><td>Governing law</td><td>English</td></tr><tr><td>Negative pledge</td><td>Yes</td></tr><tr><td>Pari passu</td><td>Yes</td></tr><tr><td>Cross default</td><td>Yes</td></tr></table></body></html>  

<html><body><table><tr><td>Table 6.2 Swap Market Quotes</td><td></td></tr><tr><td>Spot exchange rate GBP-USD</td><td>1.6701/1.6708</td></tr><tr><td>GBP 2-yearinterestrateswap</td><td>5.46/51</td></tr><tr><td>USD-GBPcurrencyswap</td><td>+4/-1</td></tr></table></body></html>  

The first step is to obtain the amount of cash the issuer will receive at time $t_{0}$ and then determine how much will be paid out at $t_{1},t_{2}$ . To do this, we again need to calculate the proceeds from the issue.  

The issue price is 100.75 and the commissions are $1.25\%$ . This means that the amount received by the issuer before expenses is  

$$
\frac{(100.75-1.25)}{100}100,000,000=99,500,000
$$  

We see that the issue is sold at a premium which increases the proceeds, but once commissions are deducted, the amount received falls below 100 million. Thus, expenses must be deducted  

$$
\mathrm{Proceeds}=99,500,000-75,000=99,425,000
$$  

Given the proceeds, we can calculate the effective cost of fixed-rate UsD funds for this issuer. The issuer makes two coupon payments of $6\%$ (out of the 100 million) and then pays back $100~\mathrm{mil}.$ lion at maturity. At. $t_{0}$ , the issuer receives only 99,425,000. This cash flow is shown in Figure 6.11. Note that unlike the theoretical examples, the principal paid is not the same as the principal received. This is mainly due to commissions and expenses..  

From this cash flow, we can calculate the internal rate of return $y_{t_{0}}$ by solving the equation  

$$
99,425,000={\frac{60,000}{\left(1+y_{t_{0}}\right)}}+{\frac{60,000}{\left(1+y_{t_{0}}\right)^{2}}}+{\frac{100,000,000}{\left(1+y_{t_{0}}\right)^{2}}}
$$  

The solution is  

$$
y_{t_{0}}=6.3150\%
$$  

Hence, the true fixed cost of USD funds is greater than $6\%$  

The issuer will first convert this into floating rate USD funds. For this purpose, the issuer will sell a swap. That is to say, the issuer will receive fixed. $5.46\%$ and pay floating LIBOR flat. This is equivalent to paying approximately USD. $\operatorname{LIBOR}+54$ bp. Finally, the issuer will convert. these USD floating rate funds into GBP floating rate funds by paying floating GBP and receiving floating USD.  

![](95477193aa96ffcfe91d6df4978b62bf07427626640c02a567a5b53b4181af37.jpg)  

# FIGURE 6.11  

New bond issue and currency swap.  
