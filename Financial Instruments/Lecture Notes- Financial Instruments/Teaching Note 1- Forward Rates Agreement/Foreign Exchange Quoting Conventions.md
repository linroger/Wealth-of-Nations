---
title: Foreign Exchange Quoting Conventions
tags:
  - currency_pair
  - foreign_exchange
  - fx_forward_rate
  - fx_spot_rate
  - interest_rate_parity
  - outright_forward
aliases:
  - FX
  - FX Quoting
  - Forex
key_concepts:
  - Base and quote currency
  - Exchange rate definition
  - FX forward rate
  - FX spot rate
  - Forward contract value
  - Interest rate parity
---

- [[Ch1 Introduction to Derivative Markets]]
- [[Chapter 6 (Hull) Hedging Strategies with Forwards]]
- [[Deriving Forward Exchange Rate Numerical Example]]
- [[Primary vs. Secondary Commodities]]
- [[Foreign Exchange Quoting Conventions]]
- [[Forward Contracts on Exchange Rates]]
- [[Forwards and Futures Notes]]
- [[Hedging Strategies with Forwards]]
- [[Financial Instruments/Lecture Notes/Teaching Note 1- Forward Rates Agreement/Interest Rates,  Carry Trades,  and Exchange Rate Movements]]
- [[Teaching Note 1Forward Rates Agreement]]
# Foreign Exchange Quoting Conventions
- The base currency is the first currency shown in a foreign exchange quotation. The second currency in the quotation is called the quote currency,  or counter currency.
- Foreign exchange quotations are always presented as a currency pair in the following format: XXX/YYY e.g. EUR/USD. This is because,  when you exchange currency,  you’re selling one currency and buying another.
- The exchange rate represents how much quote currency you need to sell in order to buy one unit of the base currency.
[Currency Forward](Currency%20Forward.md)
### FX SPOT RATE$S_0$
- The FX spot rate, $S_0 = FOR-DOM$,  represents the number of units of domestic currency needed to buy one unit of foreign currency at time 0.
- A notional of$N$units of foreign currency is equal to$N*S_t$units of domestic currency
- The domestic currency is also referred to as the numeraire currency and the foreign one as the base currency
### FX OUTRIGHT FORWARD RATE$F(0, T)$
1. The forward exchange rate contract trades at time$t=0$at zero cost and leads to an exchange of notionals at time$T$at the pre-specified outright forward rate$F(0, T)$.
1. At time$t$,  the foreign notional amount$N$is exchanged against an amount of$N*F(0, T)$domestic currency units. 
	1. - For example,  1, 000, 000 EUR may be exchanged against 1, 390, 000 USD assuming an outright forward rate of 1.3900 EUR-USD. 
1. The outright forward is related to the FX spot rate via the spot–interest rate parity, $$F(0, T) = S \cdot e^{(r_{DOM}-r_{FOR})\tau}$$

where

- $r_{FOR}$is the foreign interest rate (continuously compounded)
- $r_{DOM}$is the domestic interest rate (continuously compounded)
- $\tau$is the time to maturity,  equal to$T - t$
## FX FORWARD VALUE

- At inception,  an outright forward contract has a value of zero. 
- Thereafter,  when foreign exchange rates and/or interest rates change,  the value of the forward contract is no longer zero,  but is worth$$v_f(t, T) = e^{-r_{DOM}\tau}(F(t, T) - K) = S_t e^{-r_{FOR}\tau} - Ke^{-r_{DOM}\tau}$$

for a pre-specified exchange rate$K$. 

- This is the forward contract value in domestic currency units,  marked to the market at time$t$. 
- As stated previously,  setting$K = F(0,  T)$yields a zero-cost contract.

---

