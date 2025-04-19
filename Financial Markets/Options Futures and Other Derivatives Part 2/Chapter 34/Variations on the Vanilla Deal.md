---
tags:
  - amortizing_swaps
  - floating_rates
  - interest_rate_swaps
  - libor
  - step_up_swaps
aliases:
  - Vanilla Swap Variations
key_concepts:
  - Basis swaps
  - Floating reference rates
  - Notional principal changes
  - OIS transactions
  - Step-up and amortizing swaps
---

# 34.1 VARIATIONS ON THE VANILLA DEAL  

Many interest rate swaps involve relatively minor variations to the plain vanilla structure discussed in Chapter 7. In some swaps the notional principal changes with time in a predetermined way. Swaps where the notional principal is an increasing. function of time are known as step-up swaps. Swaps where the notional principal is a. decreasing function of time are known as amortizing swaps. Step-up swaps could be useful for a construction company that intends to borrow increasing amounts of money at floating rates to finance a particular project and wants to swap to fixed-rate funding. An amortizing swap could be used by a company that has fixed-rate borrowings with a certain prepayment schedule and wants to swap to borrowings at. a floating rate.  

<html><body><table><tr><td colspan="2">Business Snapshot 34.1 Hypothetical Confirmation for Nonstandard Swap</td></tr><tr><td>Trade date: Effective date: Business day convention (all dates): Holiday calendar: Termination date:</td><td>4-January, 2021 11-January, 2021 Following business day U.S. 11-January, 2026</td></tr><tr><td>Fixed amounts Fixed-rate payer: Fixed-rate notional principal:</td><td>Microsoft USD 100 million</td></tr><tr><td>Fixed rate: Fixed-rate day count convention: Fixed-rate payment dates</td><td>2% per annum Actual/365 Each 11-July and 11-January</td></tr><tr><td>Floating amounts</td><td>commencing 11-July 2021 up to and including 11-January 2026</td></tr><tr><td></td><td>Goldman Sachs USD 120 million</td></tr><tr><td>Floating-rate payer Floating-rate notional principal Floating rate Floating-rate day count convention Floating-rate payment dates</td><td>USD 3-month compounded SOFR Actual/360</td></tr></table></body></html>  

The principal can be different on the two sides of a swap. Also the frequency of payments can be different. Business Snapshot 34.1 illustrates this by showing a hypothetical swap between Microsoft and Goldman Sachs where the notional principal is $\$120$ million on the floating side and. $\$100$ million on fixed side. Payments are made. every three months on the floating side and every 6 months on the fixed side. These type of variations to the basic plain vanilla structure do not affect the valuation methodology. The "assume forward rates are realized" approach can still be used..  

Traditionally LIBOR has been the most common floating reference rate in swaps. As LIBOR is phased out, it is likely that swaps based on overnight rates will become more common. (As explained in Chapter 7, a typical OIS transaction involves compounded daily overnight rates being exchanged for a fixed rate at the end of each three-month period.) Banks have indicated that they would like to be able to use a non-risk-free. floating reference rate in transactions, and in time it is likely that an acceptable nonrisk-free floating reference rate will be developed. Banks will then be able to trade swaps where the floating rate reflects credit spreads (which vary through time) as well as those where the floating rate is risk-free.  

Whatever the floating reference rate, the "assume forward rates are realized approach" can be used in standard floating-for-fixed swaps. Cash flows are calculated based on. forward rates calculated from the yield curve for the floating reference rate and these are discounted at the risk-free (OIS) rate.  

<html><body><table><tr><td colspan="2">Business Snapshot 34.2 Hypothetical Confirmation for Compounding Swap</td></tr><tr><td>Trade date:</td><td>4-January, 2021</td></tr><tr><td>Effective date: Holiday calendar:</td><td>11-January, 2021 U.S.</td></tr><tr><td>Business day convention (all dates): Termination date:</td><td>Following business day</td></tr><tr><td>Fixed amounts Fixed-rate payer:</td><td>11-January, 2026 Microsoft</td></tr><tr><td>Fixed-rate notional principal: Fixed rate:</td><td>USD 100 million 2% per annum</td></tr><tr><td>Fixed-rate day count convention: Fixed-rate payment date:</td><td>Actual/365 11-January, 2026</td></tr><tr><td>Fixed-rate compounding:</td><td>Applicable at 2.3% per annum</td></tr><tr><td>Fixed-rate compounding dates</td><td>Each 11-April, 11-July, 11-October, and 11-January commencing</td></tr><tr><td></td><td>11-April 2021 up to and including</td></tr><tr><td>Floating amounts</td><td>11-January 2026</td></tr><tr><td>Floating-rate payer:</td><td></td></tr><tr><td>Floating-rate notional principal:</td><td>Goldman Sachs</td></tr><tr><td>Floating rate:</td><td>USD 100 million USD 3-month compounded SOFR</td></tr><tr><td>Floating-rate day count convention:</td><td>plus 20 basis points Actual/360</td></tr><tr><td></td><td></td></tr><tr><td>Floating-rate payment date:</td><td></td></tr><tr><td></td><td>11-January, 2026 Applicable at SOFR</td></tr><tr><td>Floating-rate compounding: Floating-rate compounding dates:</td><td>Each 11-April, 11-July, 11-October, and 11-January commencing</td></tr></table></body></html>  

Basis swaps where interest at one floating reference rate is exchanged for interest at. another floating reference rate are a potentially useful tool to companies whose assets and liabilities are dependent on different floating rates.  
