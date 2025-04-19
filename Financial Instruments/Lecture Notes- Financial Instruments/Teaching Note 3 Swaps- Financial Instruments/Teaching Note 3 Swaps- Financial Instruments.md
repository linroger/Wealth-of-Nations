---
linter-yaml-title-alias: HEDGING WITH CURRENCY SWAPS
title: Teaching Note 3 SwapsFinancial Instruments
tags:
  - financial_instruments
  - forward_rates
  - fx_swap
  - interest_rate_swaps
  - no_arbitrage
aliases:
  - FX Swap
  - Forward Contracts
  - Swap Rate
  - Swaps
  - Teaching Note 3
key_concepts:
  - 'FX swap: currency exchange'
  - 'Forward rates: cash flow'
  - Interest rate swaps
  - No arbitrage condition
  - 'Swap rate: zero value'
---

[Teaching Note 2-Futures Contracts](Teaching%20Note%202-Futures%20Contracts.md)
**[[Teaching Note 1Forward Rates Agreement]]**
 [[Teaching Note 2-Futures Contracts]]
 **[[Teaching Note 3 SwapsFinancial Instruments]]**
 **[[Teaching Note 4-Multiperiod Binomial Trees]]**
 [[Teaching Note 5Black Scholes Formula]]
 [[Teaching Note 6-Implied Volatility]]
 [[Teaching Note 7- [[Exotic Options]]  And Derivative Pricing By Monte Carlo Simulation]]
 [[Teaching Note 8 American Options]]
 [[Teaching Notes 9Corporate Securities And Credit Derivatives]]
 [[Teaching Notes 9ACredit Default Swaps]]
 [[Teaching Notes 10Interest Rate Derivatives]]

[PSET 3 Financial Instruments](PSET%203%20Financial%20Instruments.md)

[Swaps-Financial Instruments](Swaps-Financial%20Instruments.md)
[Overnight Index Swaps (OIS)](Overnight%20Index%20Swaps%20(OIS).md)

%% Begin Waypoint %%
- **[[Teaching Note 3 Swaps- Financial Instruments]]**
	- [[Forward Rates Agreement]]
	- [[Overnight Index Swaps (OIS)]]
	- [[Swaps Types]]
	- [[Teaching Note 3 Swaps- Financial Instruments]]
	- [[The Value of the Swap Contract after Initiation]]

%% End Waypoint %%

# Teaching Note 3 Swaps- Financial Instruments
## OVERVIEW
- Back to the example,  assume the US firm is due to receive the 5 mil euros in 5 equal installments,  every 6 months.
- The US company can enter into five forward (or futures) contracts,  and hedge each single installment as a stand-alone cash flow.$$S_0 = 1.2673,  \ r_{USD} = 5\%,  \ r_{EUR} = 3\%$$

imply the following forward rates

### FORWARD RATES

| Maturity$T$| Forward Rate$F_{0, T}$|
|---|---|
| 0.5 | 1.28 |
| 1 | 1.2929 |
| 1.5 | 1.3059 |
| 2 | 1.3190 |
| 2.5 | 1.3323 |

- For each cash flow,  same arguments as above hold.
Alternatively,  the US firm can also enter into a FX swap:
- A FX swap is a contractual agreement between two counterparties to exchange prespecified amounts of moneys denominated in different currencies.

## FX SWAP CONTRACT DETAILS
- For instance,  the swap contract between the US firm and a bank may be specified as follows:
  1. US firm pays Bank 1 mil euros on every date$T =0.\1,  1,  …,  2.5$;
  2. Bank pays US firm 1 mil$\times K$,  say 1.306 mil,  dollar on the same dates.

### CASH FLOW IN SWAPS
- What is the net cash flow from the swap at any payment date?
  - We need to express cash flows in the same currency.

  - Every$T$,  the firm receives 1 mil$\times K$dollars,  and must pay 1 mil$\times S_T$dollars.$$\text{Net } \$CF \text{ at } T = 1 \ mil \times (K - S_T)$$

Alternatively,  the US firm can also enter into a FX swap:

- A FX swap is a contractual agreement between two counterparties to exchange prespecified amounts of moneys denominated in different currencies.
- For instance,  the swap contract between the US firm and a bank may be specified as follows:
  1. US firm pays Bank 1, 000, 000 euros on every date$T =0.\1,  1,  …,  2.5$;
  1. Bank pays US firm 1, 000, 000 x$K$,  say 1.306 million dollars on the same dates.

What is the net cash flow for the firm from the swap at any payment date?

- We need to express cash flows in the same currency.
- Every$T$,  the firm receives 1, 000, 000 x$K$dollars and must pay 1, 000, 000 x$M_T$dollars.
  - Net$\text{CF}$at$T = 1$million x$(K - M_T)$
## DETERMINING THE SWAP RATE

### HOW IS THE SWAP RATE $K = 1.306$ DETERMINED?
- The **Swap Rate$K$** is chosen at time 0 so that the **Value of the swap is equal to zero**. 
	- $\Rightarrow$no exchange of money at inception but only in the future.
### VALUING A SWAP
- How can we determine the value of a swap?
  - Let’s use the same methodology we used to value forwards,  that is,  let’s find how much would the firm pay to get out of the position.
#### NO ARBITRAGE CONDITION
- No arbitrage condition: Suppose the firm wants to close the swap exposure by using a sequence of forwards.
#### SWAP PAYOFF

- The payoff for every$T = 0.5,  …,  2.5$is$$\text{Payoff at } T \text{ of swap + reverse forward } = 1 \ mil \times (K - S_T) + 1 \ mil \times (S_T - F_{0, T})$$
- The Present Value of these sequence of net payments is$$PV \text{ of swap + reverse forward cash flows } = e^{-r_{USD} \times 0.5} \times 1 \ mil \times (K - F_{0, 0.5}) + e^{r_{USD} \times 1} \times 1 \ mil \times (K - F_{0, 1}) + … + e^{-r_{USD} \times 2.5} \times 1 \ mil \times (K - F_{0, 2.5})$$
- No arbitrage$\Rightarrow$At time 0,  the PV of swap + reverse forwards cash flows = 0
  - Why?$K$and$F_{0, T}$are chosen so that it costs nothing to enter into a swap or forward.
  - If PV of these cash flows$\neq 0$,  infinite profits are available.
#### SOLVING FOR$K$
- We obtain one equation in one unknown$K$$$0 = e^{-r_{USD} \times 0.5} \times 1 \ mil \times (K - F_{0, 0.5}) + e^{r_{USD} \times 1} \times 1 \ mil \times (K - F_{0, 1}) + … + e^{-r_{USD} \times 2.5} \times 1 \ mil \times (K - F_{0, 2.5})$$
- The solution to the equation is a weighted average of forward prices:$$\text{Currency Swap Rate} = K = w_{0.5}F_{0.5} + w_{1}F_{0, 1} + … + w_{2.5}F_{0, 2.5}$$
- The weights$w_T$are given by the relative time value of money across maturities$$w_T = \frac{e^{-r_{USD} \times T}}{e^{-r_{USD} \times 0.5} + e^{-r_{USD} \times 1} + … + e^{-r_{USD} \times 2.5}}$$
- We obtain an alternative (equivalent) formulation by substituting the forward prices$F_{0, T} = S_0(e^{-r_{EUR} \times T})$: $$\text{Currency Swap Rate} = K = \frac{S_0(e^{-r_{EUR} \times 0.5} + e^{-r_{EUR} \times 1} + … + e^{-r_{EUR} \times 2.5})}{e^{-r_{USD} \times 0.5} + e^{-r_{USD} \times 1} + … + e^{-r_{USD} \times 2.5}}$$

  - The FX Swap rate equals the current exchange rate multiplied by the ratio of the relative borrowing costs in the two currencies.

---

# HEDGING WITH SWAPS VERSUS FORWARDS

The payoff profile from the sequence of forwards and one swap is different:

1. The sequence of forwards imply the US firms gets less money early on,  and more later on (from$1.28 mil to$1.3323 mil).
1. The swap implies the firm gets a constant amount$1.306 mil every six months.
	1. ![500](IMG-20240913171226970.png)
1. Both strategies perfectly hedge the exposure,  as the exchange rate risk is eliminated and both payoff profiles are known at 0.

### OTHER TYPES OF SWAPS

The number of swaps that exist in the market is very large. • The most common are:

1. Interest rate swaps
	1. One party pays a fixed coupon and the other party pays a floating rate.
	1. Plain vanilla IR swaps have floating rate given by LIBOR
1. Energy swaps
	1. One party pays a fixed amount and the other party pays a floating amount linked to some energy index,  such as oil prices,  gas prices,  etc.
1. Basis swaps
	1. Both parties make floating payments,  but linked to different indices,  such as [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] versus Treasuries
1. Total return swaps
	1. Both parties make floating payments,  linked to the total return of different securities.
	1. E.g. one party may pay the total return of Apple stock and the other the total return of Microsoft stock.
-----------------------------------------------------------------------------------

# THE VALUE OF THE SWAP CONTRACT AFTER INITIATION
## DETERMINING THE VALUE POST-INITIATION
- What is the value of a swap contract *after* initiation?
  - Let today be$t$, $K$be the swap rate of the existing swap,  and$T_1,  T_2,  …,  T_n$be the remaining payment periods.
  - Use the same logic as for forward and ask: What would the firm have to pay to get out of the position?
  - As before,  using a sequence of forwards to get out of the position gives

$$V^{swap}_t = PV \text{ of swap + reverse forward cash flows } = e^{-r_s(T_{1}-t)} \times (K - F_{1, T_1}) + e^{-r_s(T_{2}-t)} \times (K - F_{1, T_2}) + … + e^{-r_s(T_{n}-t)} \times (K - F_{1, T_n})$$

### OBTAINING THE SWAP VALUE FORMULA

- The swap value formula can be expressed as:$$V^{swap}_t = \sum_{i=1}^n e^{-r_s(T_{i}-t)} \times (K - F_{1, T_i})$$
  - By substituting the value of$F_{1, T_i}$with$S_t$times the discounted cash flow,  we get the equivalent formula:$$V^{swap}_t = K \times \left(\sum_{i=1}^n e^{-r_s(T_{i}-t)} \right) - S_t \times \left(\sum_{i=1}^n e^{-r_e(T_{i}-t)} \right)$$

---

# PLAIN VANILLA FX SWAPS
## UNDERSTANDING PLAIN VANILLA FX SWAPS
- In the example above I assumed the counterparties swap equal payments in the two currencies.
  - The US Firm pays Eur 1 Mil to the Bank every six months and at the same time the Bank pays$1.306 mil to the US Firm.
- The **plain vanilla FX (or currency) swap** is slightly different,  as the two counterparties not only exchange a series of equal cash flows over time (coupons),  but also a (larger) notional amount at both the initiation and maturity of the contract.
  - The primary use of **plain vanilla FX swaps** is to allow firms to borrow in any foreign currency and hedge the [Foreign Exchange](Foreign%20Exchange%20Quoting%20Conventions.md) risk.
  - Because of this,  it is important for the firm to also hedge the principal amount of the loan,  which must be paid at maturity of the bond.

### EXAMPLE
- A US firm issues 100 million Euro-denominated 5 year note with coupon$c = 4\%$.
  - The firm exchanges the proceeds into$126.73 million at the current exchange rate$S_0 = 1.2673$/Eur.
  - If the firm’s revenues are mainly in US dollars,  then the firm is subject to exchange rate risk.
  - Every six month,  the firm must pay Eur 2 mil = 100 mil$$\times 2\%$$

. In addition,  at$T = 5$,  the firm must pay back the Eur 100 mil principal.

- A plain vanilla FX swap that hedges this exchange rate risk is as follows:
  - US Firm receives from Bank 2 mil euros every six months,  plus 100 mil euros at$T$;
  - US Firm pays to bank$K \times 2$mil dollars every six months,  plus$K \times 100$mil dollars at$T$.

### SWAP RATE DETERMINATION
- What is Swap Rate$K$?
  - It is that value of the exchange rate that makes the value of the swap null at inception.

### SWAP VALUE TO THE US FIRM
- What is the value of the swap to the US firm?
  - In the swap contract,  the firm is **long** a Euro-denominated 4% coupon bond with 100 mil Euro principal,  and **short**$K$dollar-denominated bond 4% with principal$100 mil.
  - Let$B^{EUR}(t,  T)$and$B^{USD}(t,  T)$be the value of the two bond (in their respective currencies).
	 - E.g. If the (c.c.) rates are constant across maturities at$r_e = 4\%$and$r_s = 6\%$,  then$$B^{EUR}(0,  T) = 100 \text{ mil } (2\% \times e^{-r_e \times 0.5} + e^{-r_e \times 1} + … + e^{-r_e \times 5}) = EUR 99,  819,  335$$

$$B^{USD}(0,  T) = 100 \text{ mil } (2\% \times e^{-r_s \times 0.5} + e^{-r_s \times 1} + … + e^{-r_s \times 5}) = USD 91,  102,  721$$

  - The value of the swap at$t$is then$$V^{swap}_t = S_t \times B^{EUR}(t,  T) - K \times B^{USD}(t,  T)$$
- Therefore,  at time$t = 0$,  the value of$K$that makes the value of the swap equal to zero is$$V^{swap}_0 = 0 \Leftrightarrow S_0 \times B^{EUR}(0,  T) = K \times B^{USD}(0,  T) \Leftrightarrow K = \frac{S_0 \times B^{EUR}(0,  T)}{B^{USD}(0,  T)}$$
  - This is the same expression we obtained earlier when the last (notional) payment is zero.
  - In this case we obtain$K = 1.2673 \times 1.0957 = 1.389$.
  - US firm pays$2\times K = 2.778$mil every 6 months,  plus$138.9 mil at maturity.

# OTHER SWAPS

The number of swaps that exist in the market is very large. The most common are:

1. **Interest rate swaps**
	- One party pays a fixed coupon and the other party pays a floating rate.
	- Plain vanilla IR swaps have floating rate given by LIBOR.
1. **Energy swaps**
	- One party pays a fixed amount and the other party pays a floating amount linked to some energy index,  such as oil prices,  gas prices,  etc.
1. **Basis swaps**
	- Both parties make floating payments,  but linked to different indices,  such as [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] versus Treasuries.
1. **Total return swaps**
	- Both parties make floating payments,  linked to the total return of different securities.
	- E.g.,  one party may pay the total return of Apple stock and the other the total return of Microsoft stock.

# OVERNIGHT INDEX SWAPS (IS)
- In an Is,  the two counterparties agree to exchange fixed for floating payments,  where the floating payment is tied to the cumulative return from an overnight rate.
- Federal funds rate,  SOFR in US. Europe: short-term rate (€STR),  (formerly Euro OverNight Index Average (EONIA) rate).
- Given a notional$N$,  the floating rate payment at time$T_i$is:$$CF(T_i) = N \left[\left(\prod_{i=1}^{n_i} (1 + r_i\delta) \right) - 1 \right]$$
- where$\delta$is the daily interval, $r_i$is the reference (annualized) overnight rate,  and$n_i$is the number of days between reset periods.
  - The day count convention is normally Actual/360.
  - In the continuous time limit ($\delta \rightarrow 0$),  we have that:$$CF(T_i) = N \left(e^{\int_{T_{i-1}}^{T_i} r(u)du} - 1 \right)$$
	 - Is with maturity less than 1 year have only one payment at the maturity.
	 - Is with longer maturities have normally quarterly payments.

## WHAT IS THE VALUE OF IS?
- The value of Is is the difference between the floating leg and the fixed leg at the time of valuation.
#### FLOATING LEG
- At reset dates,  and assuming the payment of a principal at maturity of the swap,  the value of the floating leg is par.
- Investing the notional$N$in the overnight index daily gives at$T_i$:$$N \prod_{i=1}^{n_i} (1 + r_i\delta) = CF(T_i) + N$$
- We can replicate the floating payments,  plus a residual of notional at maturity$T_i$,  with an investment$N$at time 0.
  - It follows$V_0^{floating} = N$
#### FIXED LEG

- Given a proper discount function$Z^{OIS}(0, T_i)$,  we obtain:$$V_0^{fixed} = N \sum_{i=1}^{n} Z^{OIS}(0, T_i) + N Z^{OIS}(0, T_n)\tag{6}$$
- The value of the contract at inception is zero, $$V_0^{OIS} = 0$$
- It follows from (6) then that$$V_0^{OIS} = V_0^{floating} - V_0^{fixed} = 0$$
- This equation implies that the swap rate$c$can be computed from:$$1 = c \sum_{i=1}^{n} Z^{OIS}(0, T_i) + Z^{OIS}(0, T_n)$$
	- which gives$$c(T_n) = \frac{1 - Z^{OIS}(0, T_n)}{\sum_{i=1}^{n} Z^{OIS}(0, T_i)}$$
	  - where we now emphasize that the coupon rate$c$is for a swap with maturity$T_n$,  and thus write$c(T_n)$
## IS DISCOUNT CURVE

- Given the Is coupon rates$c(T_i)$for every maturity$T_i$,  we can bootstrap the Is zero-coupon curve from (8).
	- We obtain the relation:$$Z^{OIS}(0, T_i) = 1 - c(T_i) \sum_{j=1}^{i-1} Z^{OIS}(0, T_j)$$
		- recalling,  however,  that Is with maturity less than or equal to 1 year generally have only one payment.
- Next: Figure shows an example of bootstrapping from Is quotes,  on January 2,  2009. Panel A reports the original Is quotes from Bloomberg. Panel B uses the quotes from Panel A along with bootstrap methodology (11) and defines the Is discount function$Z^{OIS}(0, T)$.
