---
tags:
  - '#accrual_swaps'
  - '#bermudan_swaption'
  - '#cancelable_swaps'
  - '#compounding_swaps'
  - '#embedded_options'
  - '#european_swaption'
  - '#interest_rate_swaps'
  - '#risk_free_rate'
  - '#sofr'
  - '#swap_valuation'
---
# 34.5 SWAPS WITH EMBEDDED OPTIONS  

Some swaps contain embedded options. In this section we consider some commonly encountered examples.  

# Accrual Swaps  

Accrual swaps are swaps where the interest on one side accrues only when the floating reference rate is within a certain range. Sometimes the range remains fixed during the entire life of the swap; sometimes it is reset periodically.  

As a simple example of an accrual swap, consider a deal where a fixed rate. $Q$ is exchanged for compounded SOFR every quarter and the fixed rate accrues only on days when SOFR is below $2\%$ per annum. Suppose that the principal is $L$ . In a normal swap. the fixed-rate payer would pay. $Q L n_{1}/n_{2}$ on each payment date where $n_{1}$ is the number of days in the preceding quarter and. $n_{2}$ is the number of days in the year. (This assumes. that the day count is actual/actual.) In an accrual swap, this is changed to $Q L n_{3}/n_{2}$ where $n_{3}$ is the number of days in the preceding quarter that SOFR was below. $2\%$ . The fixed-rate payer saves $Q L/n_{2}$ on each day when SOFR is above. $2\%$ .4 The fixed-rate. payer's position can therefore be considered equivalent to a regular swap plus a series of. binary options, one for each day of the life of the swap. The binary options pay off. $Q L/n_{2}$ when SOFR is above. $2\%$  

To generalize, suppose that the cutoff rate (. $2\%$ in the case just considered) is $R_{K}$ Consider day $i$ during the life of the swap and suppose that. $t_{i}$ is the time until day $i$ Suppose that the interest accrues when. $R_{i}<R_{K}$ where $R_{i}$ is a floating reference interest. rate for the period between $t_{i}$ and $t_{i}+\tau$ Define $F_{i}$ as the forward value of $R_{i}$ and $\sigma_{i}$ as the volatility of $F_{i}$ Making the usual lognormal assumption, the probability that. $R_{i}$ is greater than $R_{K}$ in a world defined by a numeraire equal to a zero-coupon bond maturing at time $t_{i}+\tau$ is $N(d_{2})$ , where  

$$
d_{2}={\frac{\ln(F_{i}/R_{K})-\sigma_{i}^{2}t_{i}/2}{\sigma_{i}{\sqrt{t_{i}}}}}
$$  

The payoff from the binary option is realized at the swap payment date following day $i$ Suppose that this is at time $s_{i}$ The probability that SOFR is greater than $R_{K}$ in a world defined by a numeraire equal to a zero-coupon bond maturing at time $s_{i}$ is given by $N(d_{2}^{*})$ , where $\boldsymbol{d}_{2}^{*}$ is calculated using the same formula as $d_{2}$ , but with a small timing adjustment to $F_{i}$ reflecting the difference between time $t_{i}+\tau$ and time $s_{i}$  

The value of the binary option corresponding to day $i$ is  

$$
{\frac{Q L}{n_{2}}}P(0,s_{i})N(d_{2}^{*})
$$  

where $P(0,t)$ as usual is the price of a risk-free zero-coupon bond maturing at time $t$ The total value of the binary options is obtained by summing this expression for every day in the life of the swap. The timing adjustment (causing $d_{2}$ to be replaced by $\boldsymbol{d}_{2}^{*}$ ) is so small that, in practice, it is frequently ignored..  

# Cancelable Swap  

A cancelable swap is a plain vanilla interest rate swap where one side has the option to terminate on one or more payment dates. Terminating a swap is the same as entering into the offsetting (opposite) swap. Consider a swap between Microsoft and Goldman Sachs. If Microsoft has the option to cancel, it can regard the swap as a regular swap plus a long position in an option to enter into the offsetting swap. If Goldman Sachs has the cancelation option, Microsoft has a regular swap plus a short position in an option to enter into the swap.  

If there is only one termination date, a cancelable swap is the same as a regular swap. plus a position in a European swaption. Consider, for example, a 10-year swap where Microsoft will receive $6\%$ and pay a floating rate. Suppose that Microsoft has the option to terminate at the end of 6 years. The swap is a regular 10-year swap to receive. $6\%$ and pay floating plus a long position in a 6-year European option to enter into a. 4-year swap where $6\%$ is paid and floating is received. (The latter is referred to as a. $6\times4$ European swaption.) The standard market model for valuing European swap-. tions is described in Chapter 29.  

When the swap can be terminated on a number of different payment dates, it is a regular swap plus a Bermudan-style swaption. Consider, for example, the situation where Microsoft has entered into a 5-year swap with semiannual payments where $6\%$ is received and a floating rate is paid. Suppose that the counterparty has the option to terminate the swap on payment dates between year 2 and year 5. The swap is a regular swap plus a short position in a Bermudan-style swaption, where the Bermudan-style swaption is an option to enter into a swap that matures in 5 years and involves a fixed payment at $6\%$ being received and floating being paid. The swaption can be exercised on any payment date between year 2 and year 5. Methods for valuing Bermudan swaptions are discussed in Chapters 32 and 33.  

# Cancelable Compounding Swaps  

Sometimes compounding swaps can be terminated on specified payment dates. On termination, the floating-rate payer pays the compounded value of the floating amounts up to the time of termination and the fixed-rate payer pays the compounded value of the fixed payments up to the time of termination.  

Some tricks can be used to value cancelable compounding swaps. Suppose first that the floating rate is a risk-free rate (such as compounded SOFR or SONIA) and it is compounded at the risk-free rate. Assume that the principal amount of the swap is paid on both the fixed and floating sides of the swap at the end of its life. This is similar to moving from Table 7.1 to Table 7.2 for a vanilla swap. It does not change the value of the swap and has the effect of ensuring that the value of the floating side always equals the notional principal immediately after a payment date. To make the cancelation decision, we need only look at the fixed side. We construct an interest rate tree as outlined in Chapter 32. We roll back through the tree in the usual way valuing the fixed side. At each node where the swap can be canceled, we test whether it is optimal to keep the swap or cancel it. Canceling the swap in effect sets the fixed side equal to par. If we are paying fixed and receiving floating, our objective is to minimize the value of the fixed side; if we are receiving fixed and paying floating, our objective is to maximize the value of the fixed side.  

When the floating side is the risk-free rate plus a spread compounded at the risk-free rate, the cash flows corresponding to the spread rate of interest can be subtracted from the fixed side instead of adding them to the floating side. The option can then be valued as in the case where there is no spread.  

When the compounding is at the risk-free rate plus a spread, an approximate approach is as follows:5  

1. Calculate the value of the floating side of the swap at each cancelation date assuming forward rates are realized.   
2. Calculate the value of the floating side of the swap at each cancelation date assuming that the floating rate is the risk-free rate and it is compounded at the risk-free rate.   
3. Define the excess of step 1 over step 2 as the "value of spreads" on a cancelation date.   
4. Treat the option in the way described above. In deciding whether to exercise the. cancelation option, subtract the value of the spreads from the values calculated for the fixed side.  
