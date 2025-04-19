---
tags:
  - '#cross_currency_interest_rate_swap'
  - '#currency_swaps'
  - '#diff_swap'
  - '#differential_swap'
  - '#fixed_for_fixed_currency_swap'
  - '#floating_for_floating_currency_swap'
  - '#forward_rates'
  - '#quanto_adjustment'
  - '#usd_gbp'
---
# 34.3 CURRENCY AND NONSTANDARD SWAPS  

Currency swaps were introduced in Chapter 7. They enable an interest rate exposure in. one currency to be swapped for an interest rate exposure in another currency. Usually two principals are specified, one in each currency. The principals are exchanged at both the beginning and the end of the life of the swap as described in Section 7.7..  

Suppose that the currencies involved in a currency swap are U.S. dollars (UsD) and British pounds (GBP). In a fixed-for-fixed currency swap, a fixed rate of interest is specified in each currency. The payments on one side are determined by applying the fixed rate of interest in USD to the USD principal; the payments on the other side are determined by applying the fixed rate of interest in GBP to the GBP principal.  

In a floating-for-floating currency swap, the payments on one side are determined by applying a USD floating rate (possibly with a spread added) to the USD principal; similarly the payments on the other side are determined by applying a GBP floating rate (possibly with a spread added) to the GBP principal. In a cross-currency interest rate swap, a floating rate in one currency is exchanged for a fixed rate in another currency.  

Floating-for-floating and cross-currency interest rate swaps can be valued using the. "assume forward rates are realized" rule. Future rates in each currency are assumed to. equal today's forward rates. This enables the cash flows in the currencies to be. determined. The USD cash flows are discounted at the USD zero rate. The GBP cash flows are discounted at the GBP zero rate. The current exchange rate is then used to. translate the two present values to a common currency..  

It is important to ensure that valuation procedures are such that transactions that could be negotiated today (at the midpoint of bid and ask) have zero value. The discount rates that are used are often adjusted to ensure that this is the case.2.  

The results in Chapter 30 indicate that the "assume forward rates will be realized" approach to valuation does not always work. It must be replaced by "assume adjusted forward rates will be realized." If payments on a swap depend on a bond yield or a swap rate, equation (30.1) can be used to determine adjusted forward rates. If timing differences are involved in the determination of payments, equation (30.3) can be used to determine adjusted forward rates. A swap where an interest rate in one currency is applied to a principal in another currency is known as a differential swap or diff swap. In this case the quanto adjustment in equation (30.5) is necessary to determine adjusted forward rates.  
