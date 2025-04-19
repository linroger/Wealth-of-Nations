---
title: Currency Swaps
tags:
  - currency_swaps
  - exchange_rate_risk
  - government_bonds
  - hedging
  - swap_contract
aliases:
  - FX swap
  - currency swap
key_concepts:
  - bond value
  - currency swap rates
  - exchange rate risk
  - government bonds
  - swap contract
---

# Currency Swaps

[Swaps-Financial Instruments](Swaps-Financial%20Instruments)
[Lecture Note 3 Swaps- Financial Instruments](Lecture%20Note%203%20Swaps-%20Financial%20Instruments.md)

## 1. DETERMINING CURRENCY SWAP RATES

### 1.1. PREAMBLE

1. Governments often issue bonds in foreign currencies (e.g.,  the Greek government issues Greek bonds denominated in USD rather than in EUR,  the home currency).
1. In issuing bonds in a foreign currency,  a government exposes itself to exchange rate risk. If the foreign currency appreciates relative to the home currency,  then more units of the home currency are required to pay the interest and principal in the foreign currency.
1. Currency swaps serve as a hedge against such exchange rate risk.

### 1.2. CURRENCY SWAP

1. Consider two countries: Home H and Foreign F.
1. At inception$t = 0$,  Home issues government bonds with value$X$in currency F.
1. The bond pays a coupon (interest) semi-annually at the annual interest rate$c$.
1. To hedge against exchange rate risk,  Home enters in a swap contract.
1. Let$M_0$denote the exchange rate for F/H currencies at inception$t = 0$.
1. At inception$t = 0$,  the swap contract requires:
		a. Home pays$N_F = X$in F currency.
		b. Home receives$N_H = X \cdot \frac{1}{M_0}$in H currency.
1. At maturity$t = T$,  the swap contract requires:
		a. Home receives$N_F = X$in F currency.
		b. Home pays$N_H = X \cdot \frac{1}{M_0}$in H currency.

### 1.3. VALUE OF BONDS

1. Time$t = 0$value of the bond denominated in F currency.$$B_0^F = \sum_{t=1}^T \frac{c}{2} \cdot N_F \cdot Z_F(0,  t)\text{ Interest PV} + N_F \cdot Z_F(0,  T)\text{ Principal PV}$$
1. Time$t = 0$value of the bond denominated in H currency.$$B_0^H(K) = \sum_{t=1}^T \frac{K}{2} \cdot N_H \cdot Z_{H(0,  t)}\text{ Interest PV} + N_H \cdot Z_H(0,  T)\text{ Principal PV}$$

		-$K$denotes the "swap rate, " i.e. the annualized coupon rate for semi-annual payments of coupons in the H currency.  
		- The bond value$B_0^H(K)$is a function of the swap rate$K$.

### 1.4. SWAP RATE UNDER SPOT EXCHANGE OF PRINCIPAL

1. Time$t = 0$value of the swap in F currency is equal to the value of the long position in the bond denominated in the F currency minus the value of the short position in the bond denominated in the H currency,  converted into the F currency using the time$t = 0$exchange rate$M_0$.$$V_{0, }^{\text{Swap,  }F}(K)=B_{0}^{F}-M_{0}\cdot B_{0}^{H}(K)+V_{0}^{\text{FX, }F}(\overline{M}_{0})$$
1. Value of exchange of principal.$$V_0^{\mathrm{FX, }F}(\bar{M}_0)=\left(\frac{M_0}{\overline{M}_0}-1\right)\cdot N^F$$