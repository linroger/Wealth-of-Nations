---
cssclasses:
  - academia
linter-yaml-title-alias: PRICING AN INFLATION SWAP
title: Inflation Swaps
tags:
  - breakeven_rate
  - cpi
  - fixed_side
  - inflation_swap
  - nominal_rates
aliases:
  - Inflation Swaps
  - Pricing Inflation Swap
key_concepts:
  - Consumer Price Index (CPI)
  - Fixed side payment
  - Floating side payout
  - Inflation swap contract
  - Nominal rate sensitivity
---

---

title: PRICING AN INFLATION SWAP

aliases: [PRICING AN INFLATION SWAP,  Inflation Swaps]

linter-yaml-title-alias: PRICING AN INFLATION SWAP

# Inflation Swaps
## SUMMARY

An inflation swap is a contract between two counterparties where at maturity sides exchange a pre-specified payment determined by the inflation rate at inception for a payment determined by the simple rate of return of the Consumer Price Index (CPI) from inception to maturity.

## MATHEMATICAL FORMULATION

At inception,  counterparties of an inflation swap agree to exchange payments at maturity. The fixed side pays the contract notional amount:

$$
P_{\text{fixed}}(t_0,      T; r_{\text{CPI}}(t_0,      T)) = N \left[ \left(1 + r_{\text{CPI}}(t_0)\right)^{T-t_0} - 1 \right],      \tag{1.1}
$$

where:

- $t_0$ - effective date,
- $T$ - swap maturity (in years),
- $r_{\text{CPI}}(t_0)$ - contract inflation rate from $t_0$ to $T$ specified at inception,
- $P_{\text{fixed}}(t_0,      T; r_{\text{CPI}}(t_0,      T))$ - fixed payout at $T$,
- $N$ - contract notional.
The floating side pays the actual realized simple inflation rate adjustment based on the realized CPI at maturity:
$$
P_{\text{floating}}(t_0,      T) = N \left[ \frac{I(T)}{I(t_0)} - 1 \right],      \tag{1.2}
$$

where:

- $I(t_0)$ - CPI index at inception,
- $I(T)$ - CPI index at maturity,
- $P_{\text{floating}}(t_0,      T)$ - floating side payout at $T$.
At inception,  the IS should value at par,  i.e.,  the net value of both sides is zero. At time $t > t_0$,  however,  the value of the IS changes as the new expected inflation rate diverges from the contract rate and as the maturity of the swap approaches. If we were to enter (at par) a new IS at time $t$ with the same maturity $T$ as the original IS,  the fixed side payout would be
$$
P_{\text{fixed}}(t,      T; r_{\text{CPI}}(t,      T)) = N \left[ \left(1 + r_{\text{CPI}}(t)\right)^{T-t} - 1 \right],      \tag{1.3}
$$

using the same notation as in (1.1). Since the contract at $t_0$ is worth zero,  the expectation at $t$ of the floating side payout at $T$ equals that of the fixed payout. From (1.2),  we get

$$
I(T) = I(t) \left[ P_{\text{fixed}}(t,      T; r_{\text{CPI}}(t,      T)) + 1 \right]. \tag{1.4}
$$

This,  in turn,  allows us to compute the expected floating payout from (1.2) and (1.3) and substituting $t$ for $t_0$:

$$
P_{\text{floating}}(t,      T) = N \left[ \frac{I(t)}{I(t_0)} \left(1 + r_{\text{CPI}}(t)\right)^{T-t} - 1 \right]. \tag{1.5}
$$

Total value of the IS at $t$ is the difference between the floating and fixed sides present valued from $T$ back to $t$:

$$
V(t,      T) = \left[ P_{\text{floating}}(t,      T) - P_{\text{fixed}}(t_0,      T; r_{\text{CPI}}(t_0,      T)) \right] \times \text{df}(t,      T)\delta_{\text{pay-fixed}},     
\tag{1.6}
$$

where:

- $V(t,      T)$ - value of IS at $t$,
- $\text{df}(t,      T)$ - discount factor associated with $T$ as seen at $t$,
- $\delta_{\text{pay-fixed}}$ =
		- 1,  IS is pay-fixed,
		- -1,  otherwise.
If the counterparty to the IS is considered risk free,  discount factor $\text{df}(t,      T)$ above is calculated using the usual swap discount curve. In the opposite case,  an adjustment to the discount curve can be made by shocking the discount curve by its spread to a bond issued by this counterparty and maturing at (approximately) the same time as the IS.
1. **Sensitivity to Changes in Nominal Rates**:
   To determine the sensitivity of the inflation swap value to changes in nominal rates,  we calculate the duration of the swap. The duration measures the sensitivity of the present value of the cash flows to changes in the interest rate.
   $$
   D_{\text{swap}} = -\frac{1}{V(t,      T)} \cdot \frac{\partial V(t,      T)}{\partial r}
  $$
   Given the discount factor $\text{df}(t,      T) = e^{-r(T-t)}$,      its derivative with respect to $r$ is:
   $$

   \frac{\partial \text{df}(t,  T)}{\partial r} = -(T-t) \cdot e^{-r(T-t)} = -(T-t) \cdot \text{df}(t,  T)

  $$
   $$

   \frac{\partial V(t,  T)}{\partial r} = \left[P_{\text{floating}}(t,  T) - P_{\text{fixed}}(t_0,  T; r_{\text{CPI}}(t_0,  T)) \right] \times \frac{\partial \text{df}(t,  T)}{\partial r}

  $$
   $$

   \frac{\partial V(t,  T)}{\partial r} = \left[P_{\text{floating}}(t,  T) - P_{\text{fixed}}(t_0,  T; r_{\text{CPI}}(t_0,  T)) \right] \times -(T-t) \cdot \text{df}(t,  T)

  $$
   $$

   D_{\text{swap}} = \frac{\left[P_{\text{floating}}(t,  T) - P_{\text{fixed}}(t_0,  T; r_{\text{CPI}}(t_0,  T)) \right] \times (T-t) \cdot \text{df}(t,  T)}{V(t,  T)}

  $$
   $$

   D_{\text{swap}} = T - t

  $$
2. **Sensitivity to Changes in Breakeven Rates**:
   To determine the sensitivity of the inflation swap value to changes in breakeven rates,      we compute the partial derivative of $V(t,      T)$ with respect to $r_{\text{CPI}}(t)$.
   $$

   \frac{\partial P_{\text{floating}}(t,  T)}{\partial r_{\text{CPI}}(t)} = N \cdot \frac{I(t)}{I(t_0)} \cdot (T-t) \cdot \left(1 + r_{\text{CPI}}(t)\right)^{T-t-1}

  $$
   The partial derivative of $P_{\text{fixed}}(t_0,      T; r_{\text{CPI}}(t_0,      T))$ with respect to $r_{\text{CPI}}(t_0,      T)$ is zero since it is fixed at inception.
   Therefore,      the sensitivity of the inflation swap value to changes in breakeven rates is:
   $$

   \frac{\partial V(t,  T)}{\partial r_{\text{CPI}}(t)} = N \cdot \frac{I(t)}{I(t_0)} \cdot (T-t) \cdot \left(1 + r_{\text{CPI}}(t)\right)^{T-t-1} \cdot \text{df}(t,  T)

  $$
   $$

   \frac{\partial V(t,  T)}{\partial r_{\text{CPI}}(t)} = N \cdot \frac{I(t)}{I(t_0)} \cdot (T-t) \cdot \left(1 + r_{\text{CPI}}(t)\right)^{T-t-1} \cdot e^{-r(T-t)}

  $$
  $$
$$
