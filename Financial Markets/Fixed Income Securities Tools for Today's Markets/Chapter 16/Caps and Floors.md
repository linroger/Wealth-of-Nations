---
tags:
  - caplets
  - caps_floors
  - interest_rate_derivatives
  - libor
  - option_pricing
  - volatility
aliases:
  - Caps
  - Floors
key_concepts:
  - ATM cap pricing example
  - 'Cap: portfolio of caplets'
  - Caplet valuation formula
  - 'Caplets: LIBOR and strike'
  - Implied cap volatility
---

# 16.4 CAPS AND FLOORS  

The easiest way to describe caps is to start with caplets, even though caps are the more traded derivative. At the end of a given accrual period, a caplet pays the greater of zero and of LIBOR minus a strike, where LIBOR is set at the beginning of the accrual period. Consider, for example, a caplet with a three-month LIBOR reset date of February 14, 2022, a payment date of May 14, 2022, and a strike of $181\%$ . Note that there are 89 days over this. accrual period. If LIBOR on February 14, 2022, turns out to be $L$ , then a unit notional of the caplet will pay, on May 14, 2022,.  

$$
\frac{89}{360}[L-.181\%]^{+}
$$  

where, as mentioned already, $[L-.181\%]^{+}$ is another way of writing max $[L-0.181\%,0]$ . Note that the payoff of a caplet looks like that of an option, but the maximum is a feature of the contract rather than a result of optimal exercise behavior.  

Caplets are typically valued by practitioners under the assumption that forward LIBOR rates are normally distributed. Under this assumption,  

Appendix A16.3 shows that the value of a caplet with a reset at time $T$ and payment at time $T+\tau$ is given by,  

$$
\tau d_{0}(T+\tau)\xi^{N}(S_{0},T,K,\sigma)
$$  

where $\tau$ is the term of the reference rate; $d_{0}(T+\tau)$ is the discount factor to the payment date; $S_{0}$ is today's forward rate from $T$ to $T+\tau;K$ is the. strike; $\sigma$ the basis-point volatility of the forward rate; and $\xi^{N}$ the BSM-style formula defined in Appendix A16.4. Table 16.5 applies Equation (16.9) to 100 notional of the caplet introduced previously, as of May 14, 2021. Note that there are 276 days from the pricing date, May 14, 2021, to the reset date, February 14, 2022.3 The appropriate discount factor to the payment date, derived from the swap curve, is .998191. Finally, a volatility of 12.09 basis points, which comes from the discussion, is used to derive the price of .0129 cents per 100 notional amount.  

A cap is a portfolio of caplets, with the value of the cap being the sum. of the value of its component caplets. The implied volatility of a cap is the. volatility that, when used to value every component caplet, results in the. market price of the cap. This leads to some complexities, as will be discussed presently, because the term structure of caplet volatility is not flat. In other words, every caplet is properly valued at its own volatility even though, when quoting the price of a cap, all of its component caplets are valued at a single, cap volatility.  

IABLE 16.5Pricing a Caplet with a LIBOR Reset on February 14, 2022, and a Payment Date on May 14, 2022, as of May 14, 2021.   


<html><body><table><tr><td>Quantity</td><td>Value</td></tr><tr><td>So</td><td>.200%</td></tr><tr><td>T</td><td>276 =.7562 365</td></tr><tr><td>T</td><td>89 =.2472</td></tr><tr><td>K</td><td>360 .181%</td></tr><tr><td></td><td>.1209%</td></tr><tr><td>d(T + t)</td><td>.998191</td></tr><tr><td>gN(So, T, K,o)</td><td>.00052</td></tr><tr><td>VCaplet = 100 xtd(T +t)gN 0</td><td>.0129</td></tr></table></body></html>  

Table 16.6 illustrates the structure of a cap and cap pricing with a one-year US dollar ATM cap as of May 14, 2021. This cap is ATM because its strike of. $0.181\%$ equals the rate of the corresponding swap, which, in this case, is the one-year swap. The cap strike of $0.181\%$ means that every component caplet has a strike of $0.181\%$ . The cap volatility of 12.09 basis points means that the price of the cap is the sum of the component caplet values when each caplet is valued at a volatility of 12.09 basis points. The forward rates are derived from the swap curve, and the caplet premiums are calculated from the normal BSM formula, with: each respective forward rate; a strike of. $0.181\%$ ; a volatility of 12.09 basis points; and appropriate date parameters and discount factors along the lines of Table 16.5. In fact, the caplet in Table 16.6 that pays on May 14, 2022, is the same caplet that is valued in Table 16.5..  

Note that what might have been the first caplet in Table 16.6, with a LIBOR reset at the start of the cap initiation and a payment on August 14, 2021, is omitted from the table. The payment from such a caplet is known as of the start of the cap and, as such, has no option-like premium: it is simply worth its present value. In fact, in this example, where the initial LIBOR setting is below the strike, at . $155\%$ , the payment from this caplet is zero. In any case, along these lines, the first caplet payment is usually omitted from a cap.  

The one-year cap in the example is a spot starting cap; that is, putting aside the skipping of the first payment, the schedule of payments starts immediately. There is also an active market, however, in forward starting caps. In $5\times5$ cap, the first reset is in five years, the first payment in five years plus the length of the accrual period (e.g., five years and three months), and the last payment in 10 years.  

As mentioned before, if caplets traded individually, they would be priced at individual volatilities, not at a single, cap volatility. In other words, there is a term structure of caplet volatilities. This term structure is interesting for use as another perspective on the market price of volatility and for comparison with -- and perhaps trading opportunities against - other volatility instruments. In theory, the term structure of caplet volatility could be recovered from caps of sequential terms. The problem is complicated, however, by the fact that the most traded and useful volatilities are ATM volatilities, which, in the case of caplets, correspond to caplets with strikes equal to their underlying forward rates. But the strikes of caplets that are part of caps all have a single strike that cannot, in general, equal the underlying forward rate. for every component cap. Furthermore, as discussed presently, the volatilities. of options that are and are not ATM can be significantly different from each other. Hence, the extraction of caplet volatilities from caps is often combined with some adjustment for the caplet strikes not being ATM.  

IABLE 16.6 The Structure and Pricing of a One-Year Cap as of May 14, 2021. Rates Are in Percent.   


<html><body><table><tr><td colspan="4">Cap Strike .181%</td></tr><tr><td colspan="4">CapVolatility .1209%</td></tr><tr><td colspan="2">Dates</td><td></td><td></td></tr><tr><td>Reset</td><td>Payment</td><td>Forward Rate</td><td>Caplet Premium</td></tr><tr><td>05/14/2021</td><td>08/14/2021</td><td>.155</td><td></td></tr><tr><td>08/14/2021</td><td>11/14/2021</td><td>.160</td><td>.0039</td></tr><tr><td>11/14/2021</td><td>02/14/2022</td><td>.200</td><td>.0114</td></tr><tr><td>02/14/2022</td><td>05/14/2022</td><td>.200</td><td>.0129 .0281</td></tr><tr><td colspan="4">Sum</td></tr></table></body></html>  

Floorlets and floors are analogous to caplets and caps. The payment of a floorlet at time $T+\tau$ , determined by the LIBOR rate set at time $T$ , is,  

$$
\tau[K-L]^{+}
$$  

Assuming normal forward rates, the value of a floorlet is given by,  

$$
\tau d_{0}(T+\tau)\pi^{N}(S_{0},T,K,\sigma)
$$  

where the function $\pi^{N}$ is given in Appendix A16.4. The value of a floor is.   
the sum of the values of its component floorlets.  

Applying put-call parity, the prices of an ATM caplet and an ATM floorlet with the same expiration are equal, as are the prices of matched-date ATM caps and floors. Say, for example, that the five-year swap rate, five years forward, is $5\%$ . Then paying fixed on this forward starting swap and buying a $5\times5$ floor with a strike of. $5\%$ has exactly the same cash flows as a. $5\times5$ cap with a strike of. $5\%$ . But, by definition, the value of the forward swap is zero. Hence, the values of the cap and the floor must be the same.  
