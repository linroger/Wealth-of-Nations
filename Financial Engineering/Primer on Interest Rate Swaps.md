---
tags:
  - fixed_interest_rate
  - interest_rate_swaps
  - libor
  - loan_agreement
  - variable_interest_rate
aliases:
  - IRS
  - Interest Rate Swap
  - Swaps
key_concepts:
  - Fixed vs. Variable Rates
  - Interest Rate Definitions
  - LIBOR and Prime Rate
  - Loan Interest Payments
  - Repayment Schedule
---

# EDUCATION AND EXAMINATION COMMITTEE  

OF THE  

SOCIETY OF ACTUARIES  

FINANCIAL MATHEMATICS STUDY NOTE  

# INTEREST RATE SWAPS  

by  

Jeffrey Beckley, FSA, MAAA  

Copyright 2017 by the Society of Actuaries  

The Education and Examination Committee provides study notes to persons preparing for the examinations of the Society of Actuaries. They are intended to acquaint candidates with some of the theoretical and practical considerations involved in the various subjects. While varying opinions are presented where appropriate, limits on the length of the material and other considerations sometimes prevent the inclusion of all possible opinions. These study notes do not, however, represent any official opinion, interpretations or endorsement of the Society of Actuaries or its Education and Examination Committee. The Society is grateful to the authors for their contributions in preparing the study notes.  

# Interest Rate Swaps  

Jeffrey Beckley May, 2017 update  

# Contents  

1 Background. 2   
2 Definitions .. 3   
3 General Formula . 6   
4 Special Formula. 11   
5 Net Payments. 13   
6 Market Value . 15   
7 Conclusion. 17   
8 Exercises . 18   
9 Solutions to Exercises. 23   
10 Glossary . 31  

# 1 Background  

When borrowing money, the borrower pays interest to the lender to compensate for the use of the. money. The interest rate that is charged on the loan may be a fixed interest rate or a variable. interest rate. A fixed interest rate is a rate that is determined at the time of the loan and will not change during the term of the loan even if interest rates in the market change. This means that. the borrower and the lender can agree to a repayment schedule that will not change over the term of the loan. For example, ABC Life Insurance Company borrows 10 million that will be repaid at the end of five years. ABC will pay. $6\%$ interest at the end of each year. In this example, the. interest rate is a fixed interest rate of. $6\%$ and the annual interest payment is 600,000.  

For other loans, the interest rate on the loan will be variable. A variable interest rate is adjusted periodically, upward or downward, to reflect the level of market interest rates at the time of the.   
adjustment. The procedure for adjusting the interest rate will be specified in the loan agreement..   
A variable interest rate is often referred to as a floating interest rate, which is a synonymous.   
term.  

For example, DEF Life Insurance Company borrows 10 million that will be repaid at the end of. five years. DEF will pay interest on the loan at the end of each year. The interest rate on the loan will be adjusted each year. The interest rate to be paid will be the one-year spot interest rate' at. the beginning of the year. Thus, the annual interest payment on the loan could change each year.  

Unlike the loan to ABC where the interest rate is known for all five years at the time that the loan is initiated, the interest rate on the loan to DEF is known for only the first year at the time that the loan is initiated. Therefore, the interest rate that DEF will pay in years two through five may be greater than or less than the interest rate in the first year.  

Most bank loans to corporations or businesses, as well as some home mortgage loans, contain a variable interest rate. Most of the time, the interest rate to be charged is linked to an outside index. The most common indexes used are the London Inter-Bank Offered Rate (LIBOR) and the prime interest rate.  

LIBOR is the interest rate estimated by leading banks in London that the average leading bank would be charged if borrowing from other banks. LIBOR rates are calculated for five currencies and seven borrowing periods ranging from overnight to one year. The prime interest rate is the rate at which banks in the U.S. will lend money to their most favored costumers and is a function of the overnight rate that the Federal Reserve will charge banks. The Wall Street Journal surveys the 10 largest banks in the U.S. and daily publishes the prime interest rate.  

The variable interest rates charged on the loans are typically one of the above indexes plus a spread. For example, the variable interest rate may be LIBOR plus. $2.5\%$ . This is typically expressed in term of basis points or bps. A basis point is 1/100 of $1\%$ . Therefore, the above rate would be LIBOR plus 250 bps. The spread is negotiated between the borrower and the lender. The spread is a function of several factors, such as the credit worthiness of the borrower. The spread will be larger if the credit risk associated with the borrower is greater.  

In the loan to DEF above, the interest rate can change annually. The period of time between. adjustments of the interest rate does not need to be a one-year period. It could be reset more frequently, such as every 90 days.  

A loan with a variable interest rate adds a level of uncertainty (and potentially risk) to the loan.   
that a borrower may want to avoid. An interest rate swap can be used to remove this uncertainty..   
However, a party that has income based on the current level of interest rates, may prefer to have.   
a variable interest rate. This would result in a better matching of income with the expected loan payments, which would reduce the risk for the party. In that case, if the party has a fixed rate.   
loan, they may enter into a swap to change the fixed rate into a variable rate..  

# 2 Definitions  

An interest rate swap is an agreement between two parties in which each party makes periodic interest payments to the other party based on a specified principal amount. One party pays. interest on a variable rate while the other party pays interest on a fixed rate.2.  

The fixed interest rate is known as the swap rate.? We will use the symbol. $R$ to represent the swap rate. The swap rate will be determined at the start of the swap and will remain constant for each payment. In contrast, while the variable interest rate will be defined at the start of the swap (e.g., equal to LIBOR plus 100 bps), the rate will likely change each time a payment is. determined.  

The two parties in the agreement are known as counterparties. The counterparty who agrees to pay the swap rate is called the payer. The counterparty who agrees to pay the variable rate, and thus receive the swap rate, is called the receiver.  

The specified principal amount is called the notional principal amount or just notional amount. The word "notional' means in name only. The notional principal amount under an interest rate swap is never paid by either counterparty. Thereby, it is principal in name only. However, the notional amount is the basis upon which the exchange of payments is determined. One counterparty will owe a payment determined by multiplying the swap rate by the notional amount. The other counterparty will owe a payment determined by multiplying the variable interest rate by the notional amount.  

The specified period of the swap is known as the swap term or swap tenor.  

An interest rate swap will specify dates during the swap term when the exchange of payments is to occur. These dates are known as settlement dates. The time between settlement dates is known as the settlement period. Settlement periods are typically evenly spaced. For example,. settlement periods could be daily, weekly, monthly, quarterly, annually, or any other agreed upon. frequency. The first settlement period normally begins immediately with the first payment at the end of the settlement period. For example, if the settlement period is every three months, then the. first swap payment is made at the end of three months..  

In Section 1, we introduced the concept of variable rate loans. An interest rate swap can be used. to change the variable rate into a fixed rate. In this case the borrower would enter into an interest rate swap with a third party. Entering into a swap does not change the terms of the original loan. A swap is a derivative instrument that is used to exchange variable rate payments for fixed rate payments.  

However, two parties can enter into an interest rate swap without any loan being involved. One.   
reason for doing this is speculation. One counterparty is "betting" that the variable rates are.   
going to increase from current expectations while the other counterparty is betting that the.   
variable rates are going to decrease. Other reasons include managing the duration of a portfolio.   
or to swap a series of cash flows linked to interest rates, but where the cash flows are not from a loan. At the time that each exchange of payments is to occur, the two payments are netted and only.   
one payment is made. For example, Tyler and Graham enter into an interest rate swap. Based on.   
this swap, at the end of one year, Tyler owes Graham 32,000 and Graham owes Tyler 27,000.   
Rather than each counterparty making a payment, the two payments would be netted and Tyler.   
would pay Graham 5,000. This is known as the net swap payment..  

The vast majority of interest rate swaps have a level notional amount over the swap term. However, this is not always the case. For example, a swap could have a notional amount that follows the outstanding balance of an amortization loan. Such a swap is known as an amortizing swap as the notional amount is decreasing over the term of the swap. Similarly, a swap could have a notional amount that increases over time. This is known as an accreting swap.4  

A swap typically has the first settlement period beginning at time zero. However, a swap could be a deferred swap. For deferred swaps, the exchange of payments does not start until a later date. An example is a swap where settlements occur quarterly over a three year period, but the. first settlement period does not start for two years. This means that the first exchange of. payments will be at the end of two years and three months because settlement occurs at the end of the settlement period that starts at time 2 and ends at time 2.25. With a deferred swap, the. swap rate $R$ is determined at the time that the swap is initiated even though the first payment will.  

not occur until after the deferral period. The swap term or swap tenor for a deferred swap includes the deferral period. For the example in this paragraph, the swap term would be five years.  

There is no cost to either counterparty to enter into an interest rate swap.5 This is because the swap rate is determined such that the expected future payments for each counterparty has the same present value. This will be our basis for determining the swap rate, $R$ . Since the actual payments are netted as noted above, this results in the present value of the net payments that each counterparty is expected to receive in the future being equal to zero.  

It should be noted that in practice customized swaps may not have a value of zero at inception, in which case a premium would be paid by one counterparty to the other counterparty. However, for the purpose of this study note, we assume the present value of the swap is always zero at inception.  

# Example 1  

Jordan Corporation has borrowed 500,o00 for the next two years at a variable interest rate. Under this loan, Jordan will pay interest at the end of year one and at the end of year two. The interest that Jordan will need to pay at the end of the first year is based on the one-year spot interest rate at the start of year one (time zero). The interest to be paid at the end of the second year will be based on the one-year spot interest rate at the beginning of the second year (time one). As. mentioned above, the one-year spot interest rate that Jordan Corporation will have to pay will likely be related to LIBOR or the prime rate. These negotiated or agreed upon rates would be. used in our calculation. However, for simplicity of language throughout this study note, we will. use the term spot interest rate without worrying about how it would be specifically defined in the swap or loan agreement.  

The current spot interest rates are an annual effective interest rate of $5\%$ for a one-year period and an annual effective interest rate of. $6\%$ for a two-year period. These spot interest rates will be used to calculate present values. From this we know that the interest rate for the first year of the loan is $5\%$ . However, we do not know what the interest rate will be during the second year of the. loan because it will be whatever the one-year spot interest rate is at the beginning of the second. year. Based on the spot interest rates today, we can calculate the implied one-year spot interest rate that will be in effect during the second year. This is also known as the forward interest rate for the period from time one to time two. We will refer to this rate as the one-year forward rate (since it covers a period of one year from time one to time two), deferred one year (since it comes into effect one year in the future). The implied rate for the second year is. $7.01\%$ .6  

However, under this loan, the interest rate for the second year could be higher or lower than $7.01\%$ depending on the interest rates in one year.  

Jordan Corporation is not comfortable with the uncertainty of the second year interest rate so it wants to enter into an interest rate swap that will fix the interest rate for the two years. Using our defined terms from above, the swap term or tenor is two years. The settlement periods are one year with settlement dates at the end of one year and at the end of two years. Jordan Corporation is one of the counterparties. The other counterparty is not specifically known in this example. Under the swap, Jordan will pay a fixed interest rate of $R$ during both years of the loan. To find the swap rate $R$ , we set the present values of the interest to be paid under each loan equal to each other and solve for $R$ . In other words:  

The Present Value of interest on the variable rate loan $=$ The Present Value of interest on the fixed rate loan.  

Under the variable loan interest rate, the interest to be paid in the first year is 500,o00(0.05). Further, based on today's interest rates, the interest to be paid at the end of the second year is expected to be 500,000(0.07010). For the fixed rate loan, the interest to be paid at the end of the first year and at the end of the second year is $500{,}000(R)$ . Setting the present value (using the current spot rates) of each of these interest streams equal to each other, we get:  

$$
\frac{500,000000.05)}{1.05}+\frac{500,00000.07010)}{1.06^{2}}=\frac{500,0000(R)}{1.05}+\frac{500,0000(R)}{1.06^{2}}.
$$  

Solving gives $R=0.05971$ . Therefore, if Jordan Corporation entered into a swap, the fixed interest rate that Jordan would pay is. $5.971\%$ for the tenor of the swap..  

# 3 General Formula  

We will now develop a framework for deriving the swap rate $R$  

Let $r_{t}$ be the spot interest rate for a period of $t$ years. The spot interest rate, $r_{t}$ , is expressed as an annual effective interest rate but $t$ does not need to be an integer. The spot interest rate is the market interest rate today that would be appropriate to determine the present value today of a single payment at time $t$ Using the spot interest rate, a payment of one at time $t$ has a present value of $\left(1+r_{t}\right)^{-t}$ at time zero. As noted above, $t$ is always measured in years.  

Now let $P_{t}$ be the present value of a payment of one at time t. By definition, $P_{t}=(1+r_{t})^{-t}$  

Theoretically, spot interest rates are determined using the price of a zero-coupon bond. Remember that a zero-coupon bond has no coupons and therefore has a single cash flow that is. the maturity value payable at the maturity date. If a zero-coupon bond matures in $t$ years for a maturity value of 1, then the price of the bond is the present value of the maturity value, which is $\left(1+r_{t}\right)^{-t}$ or $P_{t}$ . Therefore, $P_{t}$ is also the price of a zero-coupon bond that matures for 1 at the end of $t$ years. In practice, except for the zero-coupon bonds issued by governments, there may not be.  

zero coupon bonds available in the market to use to determine the appropriate spot interest rates for a loan. In this case the spot interest rates can be implied from other financial instruments in the marketplace.  

To determine the swap interest rate, we also need to know the implied interest rates in the future. These interest rates, known as forward interest rates, are implied by the spot interest rates.' We will let $f_{[t_{1},t_{2}]}$ be the implied interest rate between times $t_{1}$ and $t_{2}$ based on the spot interest rates. As with spot interest rates, forward interest rates are expressed as annual effective interest rates. and times $t_{1}$ and $t_{2}$ are measured in years. For example, $f_{[2,3]}$ is the interest rate from time two to time three, which is the third year. Similarly, $f_{[0.25,0.75]}$ is the annual effective implied interest rate for the six-month period beginning at the end of three months.  

There is a relationship between forward rates and spot rates that can be seen in the following diagram.  

![](9c391e9b989f227fadce865730fc063a55116bdc59a1c939b9d4d0c137eb3009.jpg)  

If these interest rates are to be equivalent, then we can develop the formula:  

$$
\left(1+r_{t_{2}}\right)^{t_{2}}=\left(1+r_{t_{1}}\right)^{t_{1}}\left(1+f_{[t_{1},t_{2}]}\right)^{t_{2}-t_{1}}.
$$  

Rearranging leads us to the following two important relationships:  

$$
\left(1+f_{[t_{1},t_{2}]}\right)^{t_{2}-t_{1}}=\frac{\left(1+r_{t_{2}}\right)^{t_{2}}}{\left(1+r_{t_{1}}\right)^{t_{1}}}
$$  

and  

$$
f_{[t_{1},t_{2}]}=\left[\frac{\left(1+r_{t_{2}}\right)^{t_{2}}}{\left(1+r_{t_{1}}\right)^{t_{1}}}\right]^{\frac{1}{t_{2}-t_{1}}}-1.
$$  

Formula (3.3) expresses the annual forward interest rate for the period. We also need to know the periodic effective forward interest rate for the settlement period, where the length of the. interest rate period is the length of the settlement period. We will use the symbold $\boldsymbol{f}_{[t_{1},t_{2}]}^{*}$ to represent this rate and refer to it as the effective forward interest rate for the settlement period.. Then,  

$$
\left(1+f_{[t_{1},t_{2}]}^{*}\right)=\frac{\left(1+r_{t_{2}}\right)^{t_{2}}}{\left(1+r_{t_{1}}\right)^{t_{1}}}
$$  

and  

$$
f_{[t_{1},t_{2}]}^{*}=\frac{\left(1+r_{t_{2}}\right)^{t_{2}}}{\left(1+r_{t_{1}}\right)^{t_{1}}}-1.
$$  

It should be noted that these relationships and the derivation of forward interest rates is based on the assumption of no arbitrage. The concept of no arbitrage is outside the scope of this study note.  

# Example 2  

Let us work through an example to better understand the relationships between spot interest rates and forward interest rates. Start with the spot interest rates in Table 1.  

Table 1 Spot Interest Rates   


<html><body><table><tr><td>t</td><td>r</td><td></td><td>t</td><td>r</td></tr><tr><td>0.25</td><td>1.00%</td><td></td><td>1.75</td><td>2.05%</td></tr><tr><td>0.50</td><td>1.10%</td><td></td><td>2.00</td><td>2.40%</td></tr><tr><td>0.75</td><td>1.22%</td><td></td><td>2.25</td><td>2.75%</td></tr><tr><td>1.00</td><td>1.35%</td><td></td><td>2.50</td><td>3.05%</td></tr><tr><td>1.25</td><td>1.50%</td><td></td><td>2.75</td><td>3.30%</td></tr><tr><td>1.50</td><td>1.75%</td><td></td><td>3.00</td><td>3.50%</td></tr></table></body></html>  

First, use the above spot rates to determine the one-year forward rate, deferred two years. This would be the implied interest rate for the third year. This will be.  

$$
f_{{[2,3]}}=\left(\frac{\left(1+r_{3}\right)^{3}}{\left(1+r_{2}\right)^{2}}\right)^{\frac{1}{3-2}}-1=\frac{\left(1.035\right)^{3}}{\left(1.024\right)^{2}}-1=0.05736=5.736\%.
$$  

In words, this is the implied annual effective interest rate for the period from time two to time three. In this case, $f_{[2,3]}=f_{[2,3]}^{*}$ . Remember that $\boldsymbol{f}_{[t_{1},t_{2}]}^{*}$ is the effective interest rate for the period from time $t_{1}$ to $t_{2}$ . However, because in this case the period we are considering is a one-year. period, the effective interest rate for the one-year period is the annual effective interest rate. Whenever we find the forward interest rate for a one-year period, that is. $t_{2}-t_{1}=1$ , then fi21 = f4.21 We can also se that Formula (3.3) above is equal to Formula (3.5) when $t_{2}-t_{1}=1$  

Now, let us look at the period from time 2 to time 2.25. Using the spot interest rates, the forward rate is  

$$
f_{[2,2,25]}=\left(\frac{\left(1+r_{2,25}\right)^{2.25}}{\left(1+r_{2}\right)^{2}}\right)^{\frac{1}{2.25-2}}-1=\left(\frac{\left(1.0275\right)^{2.25}}{\left(1.024\right)^{2}}\right)^{4}-1=0.05593=5.593\%.
$$  

This is the annual effective interest rate being earned during this three-month period. If we want the effective rate for the 3 months, then the rate is.  

$$
f_{[2,2,25]}^{\ast}=\left(\frac{\left(1+r_{2.25}\right)^{2.25}}{\left(1+r_{2}\right)^{2}}\right)-1=\left(\frac{\left(1.0275\right)^{2.25}}{\left(1.024\right)^{2}}\right)-1=0.01370=1.370\%.
$$  

Note here that $f_{[2,2.25]}$ and $f_{[2,2.25]}^{*}$ are also related as $(1.05593)^{0.25}=1.01370$  

To complete our framework, we will define. $Q_{t}$ to be the notional amount for the settlement. period ending at time $t$ where $t$ is measured in years. While the notional amount is generally level. (meaning $Q_{t}$ is a constant), this does not have to be the case. If we have a three-year interest rate. swap where the floating rate resets annually, then we could have a notional amount of one. million the first year, two million the second year, and three million the last year. In this case, $Q_{\mathrm{1}}=1,000,000$ while $Q_{2}=2,000,000$ and $Q_{3}=3,000,000$  

Using the above defined symbols and the fact that the counterparties both have the same present value of interest to be paid at time 0, we can find the swap rate using the following formula:  

The present value of the interest to be paid on the variable interest rate loan $=$ The present value of the interest to be paid on the fixed interest rate loan.  

That is, which implies  

$$
\sum_{i=1}^{n}{\cal Q}_{t_{i}}f_{[t_{i-1},t_{i}]}^{*}{\cal P}_{t_{i}}=\sum_{i=1}^{n}{\cal Q}_{t_{i}}\cdot R\cdot{\cal P}_{t_{i}}=R\sum_{i=1}^{n}{\cal Q}_{t_{i}}{\cal P}_{t_{i}},
$$  

$$
R=\frac{\displaystyle\sum_{i=1}^{n}{Q_{t_{i}}f_{[t_{i-1},t_{i}]}^{*}P_{t_{i}}}}{\displaystyle\sum_{i=1}^{n}{Q_{t_{i}}P_{t_{i}}}}.
$$  

# Example 3  

We will now find the swap rate for Example 1 using Formula (3.7):  

$$
\begin{array}{r l}&{\displaystyle\sum_{R=\frac{\lambda=1}{\sum_{i=1}^{n}Q_{t_{i}}P_{t_{i-1},t_{i}}^{*}}P_{t_{i}}}^{n}=\frac{Q_{1}f_{[0,1]}^{*}P_{1}+Q_{2}f_{[1,2]}^{*}P_{2}}{Q_{1}P_{1}+Q_{2}P_{2}}}\ &{=\frac{(500,000)(0.05)(1.05)^{-1}+(500,000)(0.0701)(1.06)^{-2}}{(500,000)(1.05)^{-1}+(500,0000)(1.06)^{-2}}=0.05971=5.971\%.}\end{array}
$$  

Note that we get the same answer as we did in Example 1. Also, we see that when the notional amount is level, we can cancel the notional amount out of both the numerator and the. denominator.  

# Example 4  

Now let's work an example where the notational amounts are not level. Above, we discussed a three-year interest rate swap where the floating rate resets annually with a notional amount of one million the first year, two million the second year, and three million the last year. This is an accreting swap with a three-year term and annual settlement periods. We will now find the swap rate using the spot interest rates in Table 1. In this case,. $Q_{\mathrm{1}}=1,000,000$ while $Q_{2}=2,000,000$ and $Q_{3}=3,000,000$ . We will also need to calculate the forward interest rates. First,.  

$$
f_{[0,1]}^{*}=\frac{\left(1+r_{1}\right)^{1}}{\left(1+r_{0}\right)^{0}}-1=\frac{\left(1+0.0135\right)^{1}}{1}-1=0.0135.
$$  

We note here that the forward rate from time O to time 1 is the same as the spot rate for a one-. year period. This should make sense given the definitions since both definitions state that this is the interest rate for the period from time O to time 1. We next have,.  

$$
f_{[1,2]}^{*}=\frac{\left(1+r_{2}\right)^{2}}{\left(1+r_{1}\right)^{1}}-1=\frac{\left(1+0.0240\right)^{2}}{\left(1+0.0135\right)^{1}}-1=0.03461
$$  

and  

$$
f_{\left[2,3\right]}^{^{\ast}}=\frac{\left(1+r_{3}\right)^{3}}{\left(1+r_{2}\right)^{2}}-1=\frac{\left(1.035\right)^{3}}{\left(1.024\right)^{2}}-1=0.05736.
$$  

Then,  

$$
\begin{array}{l}{{\displaystyle{\cal R}=\frac{\displaystyle\sum_{i=1}^{n}{\cal Q}_{t_{i}}f_{[t_{i-1},t_{i}]}^{*}P_{t_{i}}}{\displaystyle\sum_{i=1}^{n}{\cal Q}_{t_{i}}P_{t_{i}}}=\frac{\displaystyle{\cal Q}_{1}f_{[0,1]}^{*}P_{1}+{\cal Q}_{2}f_{[1,2]}^{*}P_{2}+{\cal Q}_{3}f_{[2,3]}^{*}P_{3}}{\displaystyle{\cal Q}_{1}P_{1}+{\cal Q}_{2}P_{2}+{\cal Q}_{3}P_{3}}}}\ {{~}}\ {{\displaystyle=\frac{\displaystyle(1,000,000)(0.01350)(1.0135)^{-1}+(2,000,000)(0.03461)(1.024)^{-2}+(3,000,000)(0.035)^{-1}}{\displaystyle(1,000,000)(1.0135)^{-1}+(2,000,0000)(1.024)^{-2}+(3,000,0000)(1.035)^{-1}}}}\end{array}
$$  

# 4 Special Formula  

Next we will develop a formula that we can use to derive the swap rate, $R$ , for any interest rate swap provided that the notional amount is level for each settlement period. In other words, this formula will work as long as $Q_{\iota}$ is constant. This formula is useful because, as mentioned earlier, the vast majority of interest rate swaps have a constant notional amount.  

First, note that $P_{t}=(1+r_{t})^{-t}=\frac{1}{(1+r_{t})^{t}}\rightarrow(1+r_{t})^{t}=\frac{1}{P_{t}}.$  

Second, note that $f_{[t_{1},t_{2}]}^{*}=\frac{\left(1+r_{t_{2}}\right)^{t_{2}}}{\left(1+r_{t_{1}}\right)^{t_{1}}}-1=\frac{P_{t_{1}}}{P_{t_{2}}}-1.$  

Then,  

$$
R=\frac{\displaystyle\sum_{i=1}^{n}{\cal Q}_{t_{i}}f_{[t_{i-1},t_{i}]}^{*}P_{t_{i}}}{\displaystyle\sum_{i=1}^{n}{\cal Q}_{t_{i}}P_{t_{i}}}{=\frac{\displaystyle\sum_{i=1}^{n}f_{[t_{i-1},t_{i}]}^{*}P_{t_{i}}}{\displaystyle\sum_{i=1}^{n}P_{t_{i}}}},
$$  

and finally,  

$$
\begin{array}{r l}&{R=\frac{\displaystyle\sum_{i=1}^{n}\left\{\left[\frac{P_{i_{i-1}}}{P_{i_{i}}}\right]-1\right\}P_{i_{i}}}{\displaystyle\sum_{i=1}^{n}P_{i_{i}}}=\frac{\displaystyle\sum_{i=1}^{n}\left\{P_{i_{i-1}}-P_{i_{i}}\right\}}{\displaystyle\sum_{i=1}^{n}P_{i_{i}}}}\ &{=\frac{P_{i_{0}}-P_{i_{1}}+P_{i_{1}}-P_{i_{2}}+P_{i_{2}}-P_{i_{3}}+\dots+P_{i_{n-1}}-P_{i_{n}}}{\displaystyle\sum_{i=1}^{n}P_{i_{i}}}}\ &{=\frac{P_{i_{0}}-P_{i_{n}}}{\displaystyle\sum_{i=1}^{n}P_{i_{i}}}.}\end{array}
$$  

If the interest rate swap starts immediately (is not a deferred swap), then $P_{t_{0}}=P_{0}=1$ because the present value of 1 payable today is 1. Under that circumstance, then Formula (4.1) simplifies to:  

$$
R=\frac{1-P_{t_{n}}}{\displaystyle\sum_{i=1}^{n}P_{t_{i}}}.
$$  

# Example 5  

We will now calculate the swap rate of Example 1 using Formula (4.2):  

$$
R={\frac{1-P_{t_{n}}}{\sum_{i=1}^{n}P_{t_{i}}}}={\frac{1-P_{2}}{P_{1}+P_{2}}}={\frac{1-\left(1.06\right)^{-2}}{\left(1.05\right)^{-1}+\left(1.06\right)^{-2}}}=0.05971=5.971\%.
$$  

This formula can save considerable time if we are given spot interest rates as we do not need to actually calculate forward interest rates.  

As discussed in Section 3, spot interest rates may be determined using the price of zero-coupon bonds. Further, as we also demonstrated, $P_{t}$ can also be viewed as the price of a zero-coupon bond maturing for an amount of 1 at time $t$ Formula (4.2) is especially useful if we want to calculate the swap rate using the price of zero-coupon bonds. In that case, we do not need to determine the spot interest rates or the forward interest rates, we can just directly calculate the swap rate $R$  

# Example 6  

In this example, Jenna has borrowed 250,o00 to be repaid at the end of three years. Under the loan, Jenna will pay a floating interest rate based on the one-year spot interest rate at the start of each of the next three years. Jenna wants to swap the floating rate for a fixed rate.  

Further, we have the following prices for zero-coupon bonds with a maturity value of 1:  

Table 2 Prices of Zero-Coupon Bonds   


<html><body><table><tr><td>Maturity Date</td><td>Price</td></tr><tr><td>1 Year</td><td>0.96</td></tr><tr><td>2 Years</td><td>0.91</td></tr><tr><td>3 Years</td><td>0.85</td></tr><tr><td>4 Years</td><td>0.79</td></tr><tr><td>5 Years</td><td>0.72</td></tr></table></body></html>  

Using this information, we can quickly calculate the swap rate as  

$$
R={\frac{1-P_{t_{n}}}{\underset{i=1}{\overset{n}{\sum}}P_{t_{i}}}}={\frac{1-P_{3}}{P_{1}+P_{2}+P_{3}}}={\frac{1-0.85}{0.96+0.91+0.85}}=0.05515=5.515\%.
$$  

If zero-coupon bond prices are readily available in the financial markets, using this information in combination with Formula (4.2) makes calculations quick and easy.  

# Example 7  

We mentioned above that while not common, it is possible to have a deferred swap. Provided that the notional amount of the swap is level, we can use Formula (4.1). The CHI Corporation. has entered into a five-year loan agreement that permits it to borrow two million for the next five years. Under the loan agreement, CHI will pay an annual effective interest rate of. $5\%$ for the first two years of the loan. For the last three years of the loan, the interest rate is a floating rate that will change annually and be equal to the one-year spot rate at the beginning of years three, four and five. CHI wants to swap the floating interest rate during the last three years of this loan for a fixed interest rate. CHI will achieve this objective by using a deferred interest rate swap. Assuming the zero-coupon bond prices in Table 2, we want to calculate the fixed interest rate that CHI will pay under the swap agreement. Using Formula (4.1),.  

$$
R={\frac{P_{t_{0}}-P_{t_{n}}}{\displaystyle\sum_{i=1}^{n}P_{t_{i}}}}={\frac{P_{2}-P_{5}}{P_{3}+P_{4}+P_{5}}}={\frac{0.91-0.72}{0.85+0.79+0.72}}=0.08051=8.051\%.
$$  

# 5 Net Payments  

An interest rate swap is an exchange of payments where one counterparty pays interest based on a variable interest rate while the other counterparty pays interest based on a fixed interest rate.. However, as noted previously, rather than both counterparties making payments, the payments under the swap are "netted' meaning that only the difference between the payments (the net. swap payment) is made by one counterparty to the other counterparty.  

# Example 8  

Chloe and Madison enter into a two year interest rate swap. Under the swap, Chloe will pay a fixed rate on a notional amount of 500,o00 while receiving payments based on a floating interest rate. The swap rate is $3.5\%$ with annual settlement periods. The floating rate is LIBOR plus 25 basis points. The LIBOR rate for the first year is $3.1\%$ and for the second year it turns out to be $3.7\%$ . Determine the net swap payment that will occur between Chloe and Madison at the end of the first year and at the end of the second year.  

At the end of the first year, Chloe will pay the fixed rate while Madison will pay the floating rate. Therefore, Chloe would pay. $(500,000)(0.035)=17,500$ Since Madison is paying the. floating rate, she will pay. $(500,000)(0.031+0.0025)=16,750$ . These two payments would be. netted so the net swap payment would be $17,500-16,750=750$ from Chloe to Madison.  

At the end of the second year, Chloe would again pay. $(500,000)(0.035)=17,500$ as the fixed rate has not changed. Since Madison is paying the floating rate, she will pay $(500,000)(0.037+$ $0.0025)=19,750.$ These two payments would be netted so the net swap payment would be. $19,750-17,500=2,250$ . This time the net swap payment would be paid by Madison to Chloe..  

If one of the counterparties to the swap has a loan, then the net swap payment combined with the. interest that the counterparty must make on the loan results in a net interest payment on the loan. The net interest payment is the interest paid on the loan plus any net swap payment made. by the loan holder less any net swap payment received by the loan holder..  

# Example 9  

We extend Example 8, so that in addition to the swap, Chloe also has a 500,000 loan from Anderson Bank, which charges a floating interest rate of LIBOR plus 25 basis points. Calculate the net interest payment required by Chloe at the end of each of the two years..  

At the end of the first year, Chloe must pay Anderson Bank the interest based on the floating. rate. Therefore, Chloe must pay Anderson Bank. $(500,000)(0.031+0.0025)=16,750$ .We also know from Example 8 that Chloe must pay 750 to Madison at the end of the first year. Therefore, Chloe's net interest payment is $16,750+750=17,500$  

At the end of the second year, Chloe must again pay Anderson Bank the interest based on the floating rate, which would be. $(500,000)(0.037+0.0025)=19,750$ We also know from Example 8 that Chloe will receive a payment of 2,250 from Madison at the end of the second year. Therefore, Chloe's net interest payment is. $19,750-2,250=17,500$  

We note that in both years, Chloe's net interest payment is 17,500. Since Chloe has swapped the. floating interest rate on the loan with Anderson Bank for a fixed interest rate, we should expect the interest paid to be the same in both years. Also, note that the net interest payment is equal to $(500,000)(0.035)=17,500$ That is, the net interest payment is just the amount of the loan. multiplied by the fixed interest rate. This will be true as long as the notional amount of the swap is equal to the amount of the loan and the floating rate on the loan is the same as the floating rate being swapped.  

# 6 Market Value  

A position in an interest rate swap can be sold or closed by one of the counterparties at any time during its swap term for its market value. The market value, ignoring transaction costs, is the present value of the expected future cash flows under the swap. The present value is calculated using the spot interest rates at the time of determining the market value. The spot interest rates are likely to be different than the spot interest rates at the time that the swap rate was determined.  

First, note that the market value of the swap for either counterparty is zero at the time that the. swap rate is determined. By definition, the present value of the expected future cash flows is zero at that time.  

Secondly, note that the market value at any time after the swap commences can be positive or negative. If the present value of the future cash flows is negative, then the market value will be negative. A negative market value means that to sell the swap, the seller would need to pay the buyer to step into the seller's position.  

Finally, since a swap is a merely an exchange of payments between two counterparties, the market value of the swap for one counterparty will be the negative of the market value of the swap for the other counterparty.  

# Example 10  

We will begin by looking at Example 1. Remember that for this example, the one-year spot interest rate was $5\%$ and the two-year spot interest rate was $6\%$ . Further, we found the swap rate to be $5.971\%$ on a notional amount of 500,000.  

Let's assume for this example, that one year has passed. There is one year left in the swap and. we want to determine the market value of the swap. The market value will be the present value of future expected cash flows. Both present value and the expected future cash flows are a. function of the current spot interest rates--that is the interest rates today-one year after the swap was initiated.  

Let's calculate the market value under two interest scenarios. First, let's calculate the market. value assuming that the one-year spot interest rate is. $7.010\%$ . We note that based on the spot interest rate curve from one year ago, this was the implied one-year spot interest rate for time one to time two.  

Let's calculate the market value for Jordan Corporation. Under the swap, Jordan Corporation has to pay $5.971\%$ interest on 500,o00 at the end of the year. In return, it will receive a payment of. interest based on the one-year spot rate which is $7.010\%$ . Therefore, the net payment to Jordan. Corporation at the end of one year will be. $(500,000)(0.07010-0.05971)=5195$ . Then to determine the market value, the present value will be calculated using $7.010\%$ interest since this payment will be made at the end of one year, resulting in a market value of $5195/1.07010=4854.69$  

Now, if the spot interest rates today are the same as they were one year ago, let's calculate the market value for Jordan Corporation. The one year spot rate will be an annual effective rate of $5\%$ . Consistent with the previous calculation, the market value would be  

$$
\frac{(500,000)(0.05-0.05971)}{1.05}=-4623.81.
$$  

# Example 11  

In Example 4, we determined the swap rate for a swap with a non-level notional amount. Let's use this example and determine the market value at the end of one year given that the spot interest rates at the end of one year are as follows:  

Table 3 Spot Interest Rates After One Year   


<html><body><table><tr><td>t</td><td>r</td><td></td><td></td><td>r</td></tr><tr><td>0.25</td><td>1.50%</td><td></td><td>1.75</td><td>2.40%</td></tr><tr><td>0.50</td><td>1.65%</td><td></td><td>2.00</td><td>2.48%</td></tr><tr><td>0.75</td><td>1.79%</td><td></td><td>2.25</td><td>2.80%</td></tr><tr><td>1.00</td><td>1.92%</td><td></td><td>2.50</td><td>3.10%</td></tr><tr><td>1.25</td><td>2.10%</td><td></td><td>2.75</td><td>3.35%</td></tr><tr><td>1.50</td><td>2.25%</td><td></td><td>3.00</td><td>3.50%</td></tr></table></body></html>  

At the end of one year, there are two years left on the swap. The notional amount of the swap at. the end of one year is two million and at the end of two years is three million and the swap rate is $4.188\%$ . (Note that the amounts of two and three million were originally at the end of years two. and three but since one year has passed, these are the notional amounts for the next two years.)  

We will determine the market value of this swap from the standpoint of the payer. This. counterparty will pay $4.188\%$ interest on two million at the end of one year and $4.188\%$ interest on three million at the end of two years. In return, the payer will receive the one-year spot rate for the next year at the end of one year on two million and the one-year spot rate during the. second year on three million. The one-year spot rate for the next year is known and is $1.92\%$ The one-year spot rate for the second year is not known, but can be implied by Table 3. The oneyear forward rate, deferred one year is equal to  

$$
f_{[1,2]}=\left[\frac{\left(1+r_{2}\right)^{2}}{\left(1+r_{1}\right)^{1}}\right]^{\frac{1}{2-1}}-1=\left[\frac{\left(1.0248\right)^{2}}{\left(1.0192\right)^{1}}\right]^{\frac{1}{2-1}}-1=0.03043.
$$  

Then the market value is the present value of the expected future cash flows:  

$$
\frac{(2,000,000)(0.0192-0.04188)}{(1.0192)^{1}}+\frac{(3,000,00)(0.03043-0.04188)}{(1.0248)^{2}}=-77,213.08.
$$  

Therefore, the payer will have a negative market value while the receiver will have a positive market value of 77,213.08.  

# 7 Conclusion  

Interest swaps are valuable financial instruments. They can be used to manage the risk of future cash flows, manage the duration of a portfolio, or create liquidity. As future actuaries, you should now be able to not only do the calculations (swap rate, market value, cash payments under a swap, ...) but should also understand the mechanics of the swap.  

# 8 Exercises  

You are given the following spot interest rates for Exercises 1 through 4:  

<html><body><table><tr><td>Time</td><td>Spot Rate</td></tr><tr><td>1</td><td>4.00%</td></tr><tr><td>2</td><td>5.00%</td></tr><tr><td>3</td><td>5.75%</td></tr><tr><td>4</td><td>6.25%</td></tr><tr><td>5</td><td>6.50%</td></tr></table></body></html>  

1. Jacque has a variable-rate loan of 5000 for the next two years where the interest rate is reset annually to the one-year spot interest rate. Jacque enters into an interest rate swap with a two year term and annual settlement periods. Under the swap, Jacque will pay the. fixed rate and receive the variable rate.  

a. Calculate the one-year forward interest rate, deferred one year which is the implied rate for the year from time 1 to time 2.   
b. Determine the fixed interest rate.   
c. Determine the net swap payment that will occur at the end of the first year and state whether Jacque will receive the payment or make the payment.   
d.  If the interest rate on the variable loan is $5.9\%$ during the second year of the loan, determine the net swap payment that will occur at the end of the second year and stat whether Jacque will receive the payment or make the payment.  

2. Miles Manufacturing Corporation enters into a five-year swap term. The notional amount. of the swap is 300,o00 each year. The swap has a settlement period of one year. The. variable interest rate changes each year and is the one year spot interest rate at the beginning of the year.  

Determine the swap rate under this interest rate swap.  

3. James and Associates has a line of credit that will permit it to borrow 400,o00 in year. one; an additional 200,000 in year two for a total of 600,000; and an additional 400,000 in year three for a total of one million. Under the loan, the interest rate resets at the. beginning of each year and is equal to the one-year spot interest rate at the time of reset.. James enters into a three year interest rate swap where the notional amount matches the amount available under the line of credit and variable rate matches the rate for the line of credit.  

Determine the swap rate.  

4. Shyu & Salisbury Actuarial Consultants purchased a deferred interest rate swap with a level notional amount of 125,000. Under the swap, Shyu & Salisbury will swap a variable interest rate for a fixed interest rate during the last three years of a five-year swap. No swapping of interest rates will occur during the first two years. The variable interest rate during each one-year settlement period will be the one-year spot interest rate at the start of the year.  

Determine the swap rate.  

For problems 5 through 7, you are given the following prices for zero-coupon bonds with each having a maturity value of one:.  

<html><body><table><tr><td>Time to Maturity</td><td>1 Year</td><td>2 Years</td><td>3 Years</td><td>4 Years</td><td>5 Years</td></tr><tr><td>Price</td><td>0.97</td><td>0.93</td><td>0.88</td><td>0.82</td><td>0.75</td></tr></table></body></html>  

5. A three-year interest rate swap has a level notional amount of 300,o00. Each settlement period is one year and the variable rate is the one-year spot interest rate at the beginning. of the settlement period.  

a. Calculate the swap rate for this interest rate swap.   
b. Calculate the net swap payment at the end of the first year for the payer..   
C. One year has elapsed and the one-year spot interest rate at the start of year 2 is $4.45\%$ . Calculate the net swap payment at the end of the second year for the. payer.   
d. Two years have elapsed and the one-year spot interest rate at the start of year three is $5.25\%$ . Calculate the market value of the swap.  

6. Chupp Limited enters into a deferred interest rate swap with a level notional amount of 100,000. Under the swap, Chupp will swap a variable interest rate for a fixed interest rate. during the last two years of a five-year swap. No swapping of interest rates will occur. during the first three years. The variable interest rate during each one-year settlement. period will be the one-year spot interest rate at the start of the settlement period.  

Determine the swap rate for the last two years of the swap.  

7. Chen Casualty Company has a three-year loan. The amount of the loan is 2,700,000 during the first year. At the end of the first year, Chen must pay the interest on the loan for the first year plus one-third of the principal. Additionally, at the end of the second year, Chen must pay the interest on the loan for the second year plus one-half the remaining principal. At the end of the third year, Chen must pay the interest for the third year plus all unpaid principal.  

The interest rate on the loan is a variable rate and will be reset annually to the one-year spot interest rate at the beginning of the year.  

Lingxiao, Chen's president, wants to enter into an interest rate swap so Chen will pay a fixed interest rate instead of a variable interest rate. Chen enters into an amortizing interest rate swap with terms to match the loan that accomplishes Lingxiao's objective..  

Calculate the swap rate on Chen's swap.  

8. Pitman Corporation expects to borrow money from Basham Bank over the next three years. Under this arrangement, Pitman will borrow $\$1,000,000$ today, to be repaid in one year. At time one, Pitman will borrow 2,o0o,o00 to be repaid at time two. Finally, Pitman will borrow 3,000,000 at time two to be repaid at time three.  

Pitman has agreed to pay Basham the one-year spot interest rate each year. Pitman wants. to hedge the risk of changing interest rates and lock in a fixed interest rate for the next three years. To do this, Pitman enters into an accreting interest rate swap.  

You are given the following spot interest rates:  

<html><body><table><tr><td>Period of Time</td><td>Spot Interest Rate</td></tr><tr><td>1 Year</td><td>0.050</td></tr><tr><td>2 Years</td><td>X</td></tr><tr><td>3 Years</td><td>0.065</td></tr><tr><td>4 Years</td><td>0.075</td></tr></table></body></html>  

Pitman's fixed interest rate under the interest rate swap is $6.963\%$  

Determine $X$  

9.  

Penney Airlines entered into a five-year interest rate swap two years ago. Under the fiveyear swap, Penney agreed to be the payer of a swap rate of $6.5\%$ on a level annual notional amount of 100,o00 each year for five years. Now there are three years left on the swap agreement.  

Today, the spot interest rates are:  

<html><body><table><tr><td>Period of Time</td><td>Spot Interest Rate</td></tr><tr><td>1 Year</td><td>0.050</td></tr><tr><td>2 Years</td><td>0.057</td></tr><tr><td>3 Years</td><td>0.065</td></tr><tr><td>4 Years</td><td>0.075</td></tr><tr><td>5 Years</td><td>0.080</td></tr></table></body></html>  

Calculate the market value of the swap from Penney's perspective if Penney decided to sell it today.  

10. Ningzhu Industries enters into a three-year interest rate swap with a level notional amount of 400,o00. The settlement periods are one year. The variable interest rate is the one-year spot rate at the beginning of each settlement period. Ningzhu will swap this variable interest rate for a fixed annual interest rate that is level over the three year period.  

You are given the following forward interest rates:  

<html><body><table><tr><td>Period</td><td>Forward Interest Rate</td></tr><tr><td>f(0.1</td><td>0.035</td></tr><tr><td>f1,21</td><td>0.045</td></tr><tr><td>f(2.3]1</td><td>0.060</td></tr><tr><td>f(3.4]</td><td>0.070</td></tr></table></body></html>  

Calculate the swap rate.  

11. ABC Life Insurance Company enters into a one-year interest rate swap with a notional. value of 10 million. Under this swap, ABC will pay a variable interest rate each quarter. and in return will receive a fixed interest rate each quarter. The variable interest rate will adjust each quarter to be the three-month spot interest rate at the start of each quarter..  

The spot interest rates at the time of the purchase of the swap are those in Table 1 but are repeated here for your convenience:  

<html><body><table><tr><td>t</td><td>r</td><td></td><td>f</td><td>r</td></tr><tr><td>0.25</td><td>1.00%</td><td></td><td>1.75</td><td>2.05%</td></tr><tr><td>0.50</td><td>1.10%</td><td></td><td>2.00</td><td>2.40%</td></tr><tr><td>0.75</td><td>1.22%</td><td></td><td>2.25</td><td>2.75%</td></tr><tr><td>1.00</td><td>1.35%</td><td></td><td>2.50</td><td>3.05%</td></tr><tr><td>1.25</td><td>1.50%</td><td></td><td>2.75</td><td>3.30%</td></tr><tr><td>1.50</td><td>1.75%</td><td></td><td>3.00</td><td>3.50%</td></tr></table></body></html>  

a.Determine the swap interest rate per quarter.   
b. Determine the net swap payment that will be made at the end of the first quarter.   
c.State whether ABC will receive the payment in b. or be required to make the payment in b.  

12. Deepa entered into a three year interest rate swap two years ago. The notional amount of the swap was 250,000 with one year settlement periods. Under the agreement, Deepa agreed to pay a variable rate equal to the one-year LIBOR rate plus a spread of 120 basis points and receive payments based on a constant annual interest rate of $6.21\%$  

At the end of the third year, Deepa receives a net swap payment of 307.50.  

Determine the one-year LIBOR rate during the third year.  

13. AJK Farms has a 1,00o,o00 loan from Anderson Bank. Under the terms of the loan, AJK will pay interest annually to Anderson Bank based on LIBOR plus 150 basis points.. Additionally, AJK will pay the principal of 1,00o,o00 at the end of five years..  

AJK would prefer to know the annual interest cost that will be incurred. To fix the interest rate on the loan, AJK enters into a five-year interest rate swap with a notional amount of 1,000,000 and annual settlement dates. The terms of the swap are that AJK will swap a variable rate of LIBOR plus 20 basis points for a fixed rate of $6.30\%$  

During the third year of the loan, LIBOR is $5.9\%$  

a. Determine the net swap payment at the end of the third year and state whether AJK receives or makes this payment.   
b. Determine the net interest payment made by AJK at the end of the third year.   
c.Determine the net interest payment made by AJK at the end of each of the other years.  

# 9 Solutions to Exercises  

1.  

a. The forward interest rate for time 1 to time 2 is $f_{[1,2]}$ . Using equivalence, which is Formula (3.1),  

$$
\left(1+r_{2}\right)^{2}=\left(1+r_{1}\right)^{1}\left(1+f_{[1,2]}\right)^{1}\to\left(1.05\right)^{2}=(1.04)(1+f_{[1,2]})\to f_{[1,2]}={\frac{(1.05)^{2}}{(1.04)}}-1=0.0602.
$$  

Note that $f_{{[1,2]}}$ could be determined with a direct application of Formula (3.3):  

$$
f_{[1,2]}=\left[\frac{\left(1+r_{2}\right)^{2}}{\left(1+r_{1}\right)^{1}}\right]^{1}-1=\left[\frac{\left(1.05\right)^{2}}{\left(1.04\right)^{1}}\right]^{1}-1=0.06010
$$  

Using Formula (3.1) is intuitive under the equivalence principal while using Formula (3.3) requires memorization of a formula.  

b. The fixed interest rate is the swap rate $R$  

$$
\begin{array}{r l}&{\quad\underset{{\bf\phi}}{\sum_{i=1}^{n}}{Q_{t_{i}}}f_{[t_{i-1},t_{i}]}^{*}P_{t_{i}}}\ &{\quad\quad\quad\quad\underset{{\bf\phi}}{\sum_{i=1}^{n}}{Q_{t_{i}}}P_{t_{i}}}\ &{\quad\quad\quad\quad\frac{\left(5000\right)\left(0.04\right)\left(1.04\right)^{-1}+\left(5000\right)\left(0.06010\right)\left(1.05\right)^{-2}}{\left(5000\right)\left(1.04\right)^{-1}+\left(5000\right)\left(1.05\right)^{-2}}=0.049757}\end{array}
$$  

or  

$$
R=\frac{1-P_{t_{n}}}{\displaystyle\sum_{i=1}^{n}P_{t_{i}}}=\frac{1-P_{2}}{P_{1}+P_{2}}=\frac{1-\left(1.05\right)^{-2}}{\left(1.04\right)^{-1}+\left(1.05\right)^{-2}}=0.049755.
$$  

The slight difference in the answers is because of rounding. The second approach. does not involve any rounding whereas in the first approach the forward rate was rounded to five decimal places  

c. At the end of one year, Jacque would pay the fixed rate and would receive the variable rate. Therefore, Jacque would pay $(5000)(0.049755)=248.77$ and would receive $(5000)(0.04)=200.$ Since the payments are netted, Jacque would make a net swap payment of 48.77 to the counterparty.  

d. At the end of the second year, Jacque would pay the fixed rate and would receive the variable rate. Therefore, Jacque would pay $(5000)(0.049755)=248.77$ and would receive $(5000)(0.059)=295.00$ Since the payments are netted, Jacque would receive a net swap payment of 46.23 from the counterparty.  

2.  

$$
\begin{array}{l}{{\displaystyle R=\frac{1-P_{t_{n}}}{\L_{n}}=\frac{1-P_{5}}{\L_{P_{i}}+P_{2}+P_{3}+P_{4}+P_{5}}}}\ {~}\ {{\displaystyle~=\frac{1-\left(1.065\right)^{-5}}{\left(1.04\right)^{-1}+\left(1.05\right)^{-2}+\left(1.0575\right)^{-3}+\left(1.0625\right)^{-4}+\left(1.065\right)^{-5}}=0.063878.}}\end{array}
$$  

3. Since the notional amount is not level, we must use Formula (3.7).  

$$
R=\frac{\displaystyle{\sum_{i=1}^{n}{{{Q_{t_{i}}}{f_{[t_{i-1},t_{i}]}^{*}}P_{t_{i}}}}}}{\displaystyle{\sum_{i=1}^{n}{{Q_{t_{i}}}P_{t_{i}}}}}{\displaystyle{=\frac{{{Q_{1}}{f_{[0,1]}^{*}}P_{1}+{Q_{2}}{f_{[1,2]}^{*}}P_{2}+{Q_{3}}{f_{[2,3]}^{*}}P_{3}}}{\displaystyle{Q_{1}}{P_{1}}+{Q_{2}}{P_{2}}+{Q_{3}}{P_{3}}}}}=
$$  

$$
(400,000)(1.04)^{-1}+(600,000)(1.05)^{-2}+(1,000,000)(1.0575)^{-3}
$$  

4. The swap rate could be found using formula (3.7) or formula (4.1). This solution will solve for $R$ both ways.  

$$
R=\frac{Q_{3}f_{[2,3]}^{*}P_{3}+Q_{4}f_{[3,4]}^{*}P_{4}+Q_{5}f_{[4,5]}^{*}P_{5}}{Q_{3}P_{3}+Q_{4}P_{4}+Q_{5}P_{5}}=
$$  

$$
f_{[2,3]}^{*}=\frac{(1.0575)^{3}}{\left(1.05\right)^{2}}-1=0.07266;\boldsymbol{f}_{[3,4]}^{*}=\frac{\left(1.0625\right)^{4}}{\left(1.0575\right)^{3}}-1=0.07764;\boldsymbol{f}_{[4,5]}^{*}=\frac{\left(1.065\right)^{5}}{\left(10625\right)^{4}}-1=0.0775;
$$  

or  

$$
R=\frac{P_{t_{0}}-P_{t_{n}}}{\displaystyle\sum_{i=1}^{n}P_{t_{i}}}=\frac{P_{2}-P_{5}}{P_{3}+P_{4}+P_{5}}=\frac{\left(1.05\right)^{-2}-\left(1.065\right)^{-5}}{\left(1.0575\right)^{-3}+\left(1.0625\right)^{-4}+\left(1.065\right)^{-5}}=0.07506.
$$  

5.  

$$
R={\frac{1-P_{t_{n}}}{\displaystyle\sum_{i=1}^{n}P_{t_{i}}}}={\frac{1-P_{3}}{P_{1}+P_{2}+P_{3}}}={\frac{1-0.88}{0.97+0.93+0.88}}=0.04317.
$$  

b. The payer pays the fixed interest rate and receives the variable interest rate. The fixed interest rate is the swap rate which is $4.317\%$ . The variable rate is the oneyear spot rate for the first year of the loan. This is  

$$
r_{1}={\frac{1}{P_{1}}}-1={\frac{1}{0.97}}-1=0.03093.
$$  

The net swap payment will be. $(300,000)(0.04317)-(300,000)(0.03093)=3672$   
which will be paid by the payer to the receiver.  

c. The payer pays the fixed interest rate and receives the variable interest rate. The fixed interest rate is the swap rate which is $4.317\%$ . The variable rate is the one-. year spot rate for the second year of the loan is $4.45\%$ . The net swap payment will. be $(300,000)(0.04317)-(300,000)(0.04450)=-399$ . Therefore, the 399 which. will be paid by the receiver to the payer.  

Note that you would get an answer of -400.36 if you carry all the decimal places in the calculation of $R$  

d. The market value is the present value of expected future cash flows. Under this swap, the variable rate has been swapped for the constant swap rate. There is one year left under the swap. The expectation is that the swap owner will pay (300,000)(0.04317) and receive (300,000)(0.0525). These payments would be made at the end of one year. Therefore, the market value will be:  

$$
\frac{(300,000)(0.0525)-(300,000)(0.04317)}{1.0525}=2659.38\
$$  

Note that you would get an answer of 2660.67 if you carry all the decimal places in the calculation of $R$  

6.  

$$
R={\frac{P_{t_{0}}-P_{t_{n}}}{\displaystyle\sum_{i=1}^{n}P_{t_{i}}}}={\frac{P_{3}-P_{5}}{P_{4}+P_{5}}}={\frac{0.88-0.75}{0.82+0.75}}=0.08280.
$$  

7. Under this loan, Chen will have a loan of 2.7 million for the first year. At the end of one year, Chen repays one third of the principal so Chen pays 0.9 million resulting in a loan of 1.8 million for the second year. At end of the second year, Chen repays one half of the principal resulting in a loan of 0.9 million for the third year.  

Since the swap notional amount follows the loan, the notional amount for the swap is not level. Therefore, we must use formula (3.7).  

<html><body><table><tr><td colspan="2">ZQlufti-,)P; R=i=1 ZQ,P, n</td><td colspan="2">Qfo,1P + Q2f,2)P2 + Q3f(2,3]P3 QP + Q2P2 + Q3P3</td><td rowspan="5">[(0.88)</td><td rowspan="5"></td></tr><tr><td colspan="2">i=1 From Section 4, we note fh,21</td><td></td><td>P</td></tr><tr><td colspan="2">一 (2.7) 1 (0.97) + (1.8)</td><td>0.97 1</td><td>0.93 (0.93) + (0.9)</td></tr><tr><td colspan="3">0.97 0.93 (2.7)(0.97) + (1.8)(0.93) + (0.9)(0.88)</td><td></td><td>0.88</td></tr><tr><td colspan="6">(2.7)[1- 0.97]+ (1.8)[0.97 - 0.93]+ (0.9)[0.93 - 0.88] (2.7)(0.97) + (1.8)(0.93) + (0.9)(0.88) (2.7)[0.03]+(1.8)[0.04] + (0.9)[0.05]</td></tr></table></body></html>  

8.  

$$
R=0.06963=\frac{\displaystyle\sum_{i=1}^{n}{Q_{t_{i}}f_{[t_{i-1},t_{i}]}^{*}P_{t_{i}}}}{\displaystyle\sum_{i=1}^{n}{Q_{t_{i}}P_{t_{i}}}}=\frac{Q_{1}f_{[0,1]}^{*}P_{1}+Q_{2}f_{[1,2]}^{*}P_{2}+Q_{3}f_{[2,3]}^{*}P_{3}}{Q_{1}P_{1}+Q_{2}P_{2}+Q_{3}P_{3}}
$$  

$$
f_{[0,1]}^{*}=r_{1}=0.05;f_{[1,2]}^{*}=\frac{\left(1+X\right)^{2}}{1.05}-1;f_{[2,3]}^{*}=\frac{\left(1.065\right)^{3}}{\left(1+X\right)^{2}}-1
$$  

$$
=\cfrac{(1)(0.05)(1.05)^{-1}+(2)\left[\cfrac{\left(1+X\right)^{2}}{1.05}-1\right]\left(1+X\right)^{-2}+(3)\left[\cfrac{\left(1.065\right)^{3}}{\left(1+X\right)^{2}}-1\right]\left(1.065\right)^{-3}}{(1)(1.05)^{-1}+(2)(1+X)^{-2}+(3)(1.065)^{-3}}=0.0696
$$  

Solving for $X$  

$$
{\frac{0.05}{1.05}}+(2){\left[\frac{1}{1.05}-\frac{1}{\left(1+X\right)^{2}}\right]}+(3){\left[\frac{1}{\left(1+X\right)^{2}}-\frac{1}{\left(1.065\right)^{3}}\right]}=0.06963{\left[\frac{1}{1.05}+\frac{2}{\left(1+X\right)^{2}}+\frac{1}{\left(1+X\right)^{3}}\right]}.
$$  

$$
\begin{array}{r l}&{\begin{array}{l l l l}{^{1.0.9}}&{\quad\lfloor\mathbf{L}^{1.0.9}}&{\textnormal{t n f}\rfloor}&{\textnormal{L}^{1.0.9}}\end{array}\quad\textnormal{t}^{1.7.0}}\ &{\begin{array}{l}{\displaystyle\frac{3-2-(2)(0.06963)}{(1+X)^{2}}=0.06963\Bigg[\frac{1}{1.05}+\frac{3}{(1.065)^{3}}\Bigg]-\frac{0.05}{1.05}-\frac{2}{1.05}+\frac{3}{(1.065)^{3}}=0.77041}\end{array}}\ &{X=\sqrt{\frac{3-2-(2)(0.06963)}{0.77041}}-1=0.057.}\end{array}
$$  

9. There are three years left under the swap. Penney Airlines will pay a fixed rate of $6.5\%$ on a notional amount of 100,000 at the end of each of the next three years. The payments that Penney Airlines will pay will be $(100,000)(0.065)=6500$ per year.  

In return, Penney Airlines will receive an interest payment based on the one year spot rate. on a notional amount of 100,o00. We use the current spot interest rates to calculate the expected payments as follows:  

End of Year 1 $:(100,000)(r_{1})=(100,000)(0.05)=5000$   
$f_{{[1,2]}}=\frac{\left(1.057\right)^{2}}{1.05}-1=0.0640467$   
End of Year 2: $(100,000)(f_{[1,2]})=(100,000)(0.0640467)=6404.67$   
$f_{{[2,3]}}=\frac{\left(1.065\right)^{3}}{\left(1.057\right)^{2}}-1=0.0811821$   
End of Year $3\colon(100,000)(f_{[2,3]})=(100,000)(0.0811821)=8118.21$   
Now we calculate the present value of the expected cash flows for Penney Airline:   
Market ${\mathrm{Value}}={\frac{(5000-6500)}{1.05}}+{\frac{(6404.67-6500)}{(1.057)^{2}}}+{\frac{(8118.21-6500)}{(1.065)^{3}}}=-174.26.$  

10. Present values can be quickly found using forward interest rates. Our present values are:  

$$
P_{1}={\frac{1}{1+f_{[0,1]}}}={\frac{1}{1.035}}=0.96618
$$  

$$
P_{2}=\frac{1}{(1+f_{[0,1]})(1+f_{[1,2]})}=\frac{1}{(1.035)(1.045)}=0.92458
$$  

$$
P_{3}={\frac{1}{(1+f_{[0,1]})(1+f_{[1,2]})(1+f_{[2,3]})}}={\frac{1}{(1.035)(1.045)(1.060)}}=0.87224
$$  

11. This exercise is different from the others for two reasons. First, the interest rate swap. occurs quarterly. Second, ABC Life will pay a variable rate and receive a fixed rate.  

a. First, calculate the swap rate:  

$$
R=\frac{\displaystyle\sum_{i=1}^{n}{{Q}_{t_{i}}{f}_{[t_{i-1},t_{i}]}^{*}{P}_{t_{i}}}}{\displaystyle\sum_{i=1}^{n}{{Q}_{t_{i}}{P}_{t_{i}}}}=\frac{{Q}_{0,25}{{f}_{[0,0,25]}^{*}{P}_{0,25}}+{Q}_{0,5}{{f}_{[0,25,0,50]}^{*}{P}_{0,5}}+{Q}_{0,75}{{f}_{[0,50,0,75]}^{*}{P}_{0,75}}+{Q}_{1}{{f}_{[0,75,0,8,1]}^{*}}}{{Q}_{0,25}{P}_{0,25}+{Q}_{0,5}{P}_{0,5}+{Q}_{0,75}{P}_{0,75}+{Q}_{1}{P}_{1}},
$$  

$$
f_{{[0,0.25]}}^{*}=\left(1.01\right)^{0.25}-1=0.0024907;f_{{[0.25,0.50]}}^{*}=\frac{\left(1.011\right)^{0.5}}{\left(1.01\right)^{0.25}}-1=0.0029868
$$  

$$
f_{[0.50,0.75]}^{*}=\frac{\left(1.0122\right)^{0.75}}{\left(1.011\right)^{0.5}}-1=0.0036312;\:f_{[0.75,1]}^{*}=\frac{\left(1.0135\right)^{1}}{\left(1.0122\right)^{0.75}}-1=0.0043244\left|
$$  

$$
(10)(0.0024907)(1.01)^{-0.25}+(10)(0.0029868)(1.011)^{-0.5}+
$$  

or  

$$
R={\frac{1-P_{1}}{P_{0.25}+P_{0.5}+P_{0.75}+P_{1}}}={\frac{1-\left(1.0135\right)^{-1}}{\left(1.01\right)^{-0.25}+\left(1.011\right)^{-0.5}+\left(1.0122\right)^{-0.75}+\left(1.0135\right)^{-1}}}=0.00.
$$  

Note that this is a quarterly effective interest rate.  

b. ABC Life will pay the variable rate and receive the fixed rate. Therefore, ABC Life will pay $(10,000,000)(0.0024907)=24,907$ and will receive $(10,000,000)(0.0033555)=33,555$ . The net swap payment will be 33,555 - $24,907=8648$   
c. The payment will be received by ABC Life from the counterparty.  

12. Under this agreement, Deepa will pay the variable rate and will receive the fixed rate. In the third year, Deepa will receive a net payment of.  

$(250,000)(0.0621)-(250,000)(L I B O R+0.012)=307.50$ and so  

$$
L I B O R=\frac{(250,000)(0.0621)-307.50}{250,000}-0.012=0.04887.
$$  

13.  

a. Under the swap, AJK will pay the fixed rate which is $6.3\%$ and will receive the. variable rate. The variable rate under the swap will be I $\operatorname{LIBOR}+0.2\%$ which is equal to $5.9\%+0.2\%=6.1\%$ . Therefore, AJK pays $(1,000,000)(0.063)=63,000$ and receives $(1,000,000)(0.061)=61,000$ . The net swap payment will be 2000 and will be paid by AJK.   
b. The net interest payment is interest paid on the loan plus any net swap payment made by the loan holder less any net swap payment received by the loan holder. The interest rate paid on the loan is $\mathrm{LIBOR}+1.5\%=5.9\%+1.5\%=7.4\%.$ The interest paid on the loan is $(1,000,000)(0.074)=74,000.$ The net interest payment is $74,000+2,000-0=76,000$   
c. The net interest payment to be made in every year will be the same for AJK. The swap assures that the interest to be paid will be the fixed rate on the loan plus any spread between the variable rate charged by Anderson Bank and the variable rate specified by the swap. This is $6.3\%+(1.5\%-0.2\%)=7.6\%.$ Therefore, the net. interest payment each year will be $(1,000,000)(0.076)=76,000$  

# 10 Glossary  

Accreting swap - A swap that has a notional amount that increases over time.  

Amortizing Swap -- A swap where the notional amount is decreasing over the term of the swap.. For example, a swap could have a notional amount that follows the outstanding balance of a loan.  

Counterparties - The two parties in the interest rate swap.  

Deferred swap - A swap where the exchange of payments does not start until a later date.  

Fixed interest rate - An interest rate that is determined at the time of the loan and will not change during the term of the loan even if interest rates in the market change.  

Forward interest rates -- These are future interest rates implied by the present spot interest. rates. For this note, $f_{[t_{1},t_{2}]}$ is the implied interest rate between time $t_{1}$ and $t_{2}$ based on the spot interest rates. The forward interest rates are expressed as annual effective interest rates and times $t_{1}$ and $t_{2}$ are measured in years.  

Interest rate swap - An agreement between two counterparties to exchange payments during a specified period in the future based on interest rates applied to a specified principal amount.  

London Inter-Bank Offered Rate (LIBOR) - The average interest rate estimated by leading. banks in London that the average leading bank would be charged if borrowing from other banks. LIBOR rates are calculated for 5 currencies and 7 borrowing periods ranging from overnight to one year.  

Market value - The price at which an interest rate swap can be sold by one of the counterparties. The market value, ignoring transaction costs, is the present value of the expected future cash flows under the swap. The present value is calculated using the spot interest rates at the time of determining the market value. The market value may be positive or negative.  

Net Interest Payment -- The total net payment that is made by the counterparty with a loan. The net interest payment is the interest paid on the loan plus any net swap payment made by the loan holder less any net swap payment received by the loan holder.  

Net Swap Payment - The amount of money that is paid by one counterparty in the swap to the other counterparty on each settlement date.  

Notional principal amount or notional amount - The specified principal amount in the interes rate swap.  

Payer - The payer under the swap is the counterparty that agrees to pay the fixed interest rate. and receive the variable interest rate. The other counterparty is known as the receiver and agrees to pay the variable interest rate while receiving the fixed rate..  

Prime interest rate - The rate at which banks in the United States will lend money to their most favored costumers. It is a function of the overnight rate that the Federal Reserve will charge banks. The Wall Street Journal surveys the 10 largest banks in the U.S. and daily publishes the prime interest rate.  

Receiver - The receiver is the counterparty that agrees to pay the variable interest rate while receiving the fixed rate.  

Settlement dates - The dates specified in an interest rate swap when the exchange of payments is to occur.  

Settlement period - The time between settlement dates.  

Spot interest rate - The spot interest rate is the market interest rate today that would be appropriate to determine the present value today of a single payment at time $t$ In this note,. $r_{t}$ is the spot interest rate for a period of $t$ years. Using the spot interest rate, a payment of 1 at time $t$ has a present value of $\left(1+r_{t}\right)^{-t}$ at time 0. Spot rates, $r_{t}$ , is expressed as an annual effective interest rate. The spot interest rates used in a swap will likely be related to LIBOR or the prime rate as agreed upon by the counterparties. For simplicity of language throughout this study note, the term spot interest rate is used without worrying about how it would be specifically defined in the swap or loan agreement..  

Swap rate - The fixed interest rate in an interest rate swap. In this note, $R$ is the swap rate.  

Swap term or swap tenor - The specified period of time covered by an interest rate swap.  

Variable interest rate -- An interest rate that is adjusted periodically, upward or downward, to reflect the level of market interest rates at the time of the adjustment. The procedure for determining the new interest rate will be specified in the loan agreement..  

Zero-coupon bond -- A zero coupon bond is a bond with no coupons and has a single cash flow that is the maturity value payable at the maturity date. The price of a zero-coupon bond are used to determine spot interest rates.  