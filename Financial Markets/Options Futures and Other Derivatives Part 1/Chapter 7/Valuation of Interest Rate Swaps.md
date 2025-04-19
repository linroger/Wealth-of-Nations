---
tags:
  - forward_rate
  - interest_rate_swap
  - libor_swap
  - ois_rates
  - risk_free_rate
  - valuation
aliases:
  - IRS Valuation
  - Swap Valuation
key_concepts:
  - Eurodollar futures
  - Forward rate agreement (FRA)
  - LIBOR swap
  - Risk-free zero curve
  - Swap valuation
---

# 7.6 VALUATION OF INTEREST RATE SWAPS  

We now move on to discuss the valuation of interest rate swaps. An interest rate swap is worth close to zero when it is first initiated. After it has been in existence for some time, its value may be positive or negative.  

Each exchange of payment in a swap can be regarded as a forward rate agreement (FRA). As shown at the end of Section 4.9, an FRA can be valued by assuming that forward rates are realized. Because it is nothing more than a portfolio of FRAs, an interest rate swap can also be valued by assuming that forward rates are realized. The procedure is:  

1. Calculate forward rates for each of the unknown floating rates that will determine swap cash flows.   
2. Calculate the swap cash flows on the assumption that unknown floating rates will. equal forward rates.   
3. Discount the swap cash flows at the risk-free rate..  

The value of a swap therefore requires a calculation of forward rates corresponding to. all floating payments and risk-free rates to discount the net cash flows from payments. dates to the present. We explained how to calculate a risk-free zero curve from OIS rates earlier in the chapter. This provides the necessary risk-free rates. Furthermore, if the swap is an OIS, the relevant forward rates can be calculated from this risk-free zero curve using the formulas in Section 4.8. Note that the first rate required is not really a. forward rate. It is a blend of one-day rates already observed and the zero rate that. corresponds to the remaining one-day rates in the period..  

In the case of a LIBOR swap, the necessary forward rates are estimated from Eurodollar futures and swap rates (assuming these are available). Eurodollar futures provide a direct estimate of forward rates (although a convexity adjustment might be necessary as discussed in Chapter 6). In the case of swap rates, we use that fact that. swap rates such as those in Table 7.4 define swaps that are worth zero. This provides. equations that must be satisfied by forward rates. With appropriate interpolation a complete forward curve consistent with the swaps rates can be obtained. Note that the first LIBOR payment has generally already been determined and does not require a forward rate calculation.  

# Example 7.1  

Suppose that some time ago a financial institution entered into a swap where it. agreed to make semiannual payments at a rate of. $3\%$ per annum and receive the SOFR six-month reference rate on a notional principal of $\$100$ million. The swap now has a remaining life of 1.2 years. Payments will therefore be exchanged at 0.2,. 0.7, and 1.2 years. Assume the risk-free rates with continuous compounding. (calculated from SOFR) for 0.2, 0.7, and 1.2 years are. $2.8\%$ $3.2\%$ , and $3.4\%$ respectively. Assume also that the continuously compounded risk-free rate observed for the last 0.3 years (which contain. $60\%$ of the days that will determine the exchange at 0.2 years) is $2.3\%$ . The floating rate for the exchange at 0.2 years is. assumed to be $0.6\times2.3\%+0.4\times2.8\%$ ,or $2.50\%$ . The floating rate for exchange at 0.7 years is the forward rate for the period between 0.2 and 0.7 years. This is $3.36\%$ with continuous compounding. Similarly, the floating rate for the exchange at 1.2 years is the forward rate for the period between 0.7 years and 1.2 years. This is $3.68\%$ with continuous compounding.  

The swap is therefore valued assuming that the three floating rates are $2.50\%$ $3.36\%$ , and $3.68\%$ with continuous compounding. With semiannual compounding, these rates become $2.516\%,3.388\%$ , and $3.714\%$ . The calculations for valuing  

the swap are therefore as indicated in the following table (all cash flows are in millions of dollars):.   


<html><body><table><tr><td>Time (years)</td><td>Fixed cash flow</td><td>Floating cashflow</td><td>Net cashflow</td><td>Discount factor</td><td>Presentvalue ofnetcashflow</td></tr><tr><td>0.2</td><td>-1.500</td><td>+1.258</td><td>-0.242</td><td>0.9944</td><td>-0.241</td></tr><tr><td>0.7</td><td>-1.500</td><td>+1.694</td><td>+0.194</td><td>0.9778</td><td>+0.190</td></tr><tr><td>1.2</td><td>-1.500</td><td>+1.857</td><td>+0.357</td><td>0.9600</td><td>+0.343</td></tr><tr><td>Total</td><td></td><td></td><td></td><td></td><td>+0.292</td></tr></table></body></html>  

Consider,for example,the 0.7 yearrow. The fixedcash flowis $-0.5\times0.03\times100$ or $-\$1.500$ million. The floating cash flow, assuming forward rates are realized, is $0.5\times0.03388\times100$ or $\$1.694$ million. The net cash flow is therefore $\$0.194$ million. The discount factor is $e^{-0.032\times0.7}=0.9778$ , so that the present value is $\$0.194\times0.9778=\$0.190$  

The value of the swap is obtained by summing the present values. It is $\$0.292$ million. (Note that these calculations are approximate because they do not take account of holiday calendars and day count conventions.)  
