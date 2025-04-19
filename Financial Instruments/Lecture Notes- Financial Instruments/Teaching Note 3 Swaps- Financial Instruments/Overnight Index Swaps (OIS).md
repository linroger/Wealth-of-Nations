---
cssclasses:
  - academia
title: Overnight Index Swaps (Is)
tags:
  - day_count_convention
  - federal_funds_rate
  - floating_rate
  - overnight_index_swaps
  - sofr
  - swap_rate
  - zero_coupon_curve
aliases:
  - Is
  - OIS
key_concepts:
  - cumulative return overnight rate
  - fixed for floating payments
  - floating rate payment
  - swap rate calculation
  - value of Is
---

**[[Teaching Note 3 SwapsFinancial Instruments]]**
	- [[Forward Rates Agreement]]
	- [[Overnight Index Swaps (OIS)]]
	- [[Swaps Types]]
	- [[Teaching Note 3 SwapsFinancial Instruments]]
	- [[The Value of the Swap Contract after Initiation]]

# Overnight Index Swaps (Is)
## FUNDAMENTALS OF Is
- In an Is,  two counterparties agree to exchange fixed for floating payments,  where the floating payment is tied to the cumulative return from an overnight rate.
	- Federal funds rate,  SOFR in US.
	- Europe: short-term rate (€STR),  (formerly Euro OverNight Index Average (EONIA) rate).
## FLOATING RATE PAYMENT CALCULATION

- Given a notional$N$,  the floating rate payment at time$T_i$is:$$CF(T_i) = N \left[\left(\prod_{j=1}^{n_i} (1 + r_{t_j}\delta) \right) - 1 \right]$$
- Where$\delta$is the daily interval,  $r_t$is the reference (annualized) overnight rate,  and$n_i$is the number of days between reset periods.
- The day count convention is normally Actual/360.
### IN THE CONTINUOUS TIME LIMIT

- In the continuous time limit ($\delta \rightarrow 0$),  we have:$$CF(T_i) = N \left(e^{\int_{0}^{T_i} r_u \,    du} - 1 \right)$$
#### IS CHARACTERISTICS
- Is with maturity less than 1 year have only one payment at the maturity.
- Is with longer maturities have normally quarterly payments.

## VALUE OF IS

- The value of Is is the difference between the floating leg and the fixed leg:$$V^{OIS}_t = V^{Floating}_t - V^{Fixed}_t$$
- ## Floating Leg
- At reset dates,  and assuming the payment of a principal at maturity of the swap,  the value of the floating leg is par.
- Indeed,  investing the notional$N$in the overnight index daily gives at$T_i$:$$N \prod_{j=1}^{n_i} (1 + r_{t_j}\delta) = CF(T_i) + N$$
- We can replicate the floating payments,  plus a residual of notional at maturity$T_n$,  with an investment$N$at time 0.
- It follows:$$V^{Floating}_{0} = N$$

## FIXED LEG

- Given a proper discount function$Z^{OIS}(0,    T_i)$,  we obtain:$$V^{Fixed}_{0} = N c \Delta \sum_{i=1}^{n} Z^{OIS}(0,    T_i) + N Z^{OIS}(0,    T_n)$$

## VALUATION AT INCEPTION
- The value of the contract at inception is zero,  $V^{OIS}_0 = 0$.
- It follows that:$$V^{OIS}_{0} = V^{Floating}_{0} - V^{Fixed}_{0} = 0$$

## SWAP RATE CALCULATION

- This equation implies that the swap rate$c$can be computed from:$$1 = c \Delta \sum_{i=1}^{n} Z^{OIS}(0,    T_i) + Z^{OIS}(0,    T_n)$$- Which gives the coupon rate$c$for a swap with maturity$T_n$:$$c(T_n) = \frac{1 - Z^{OIS}(0,    T_n)}{\Delta \sum_{i=1}^{n} Z^{OIS}(0,    T_i)}$$
- We emphasize that the coupon rate$c$is for a swap with maturity$T_n$.
## IS COUPON RATES AND ZERO-COUPON CURVE

- Given the Is coupon rates$c(T_i)$for every maturity$T_i$,  we can bootstrap the Is zero-coupon curve from the relation:$$Z^{OIS}(0,    T_i) = \frac{1 - c(T_i)}{1 + c(T_i) \Delta \sum_{j=1}^{i-1} Z^{OIS}(0,    T_j)}$$
- Recalling that Is with maturity less than or equal to 1 year generally have only one payment.
