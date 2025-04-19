---
tags:
  - daily_settlement
  - forward_agreement
  - futures_contract
  - futures_forward_difference
  - interest_rates
  - market_rates
aliases:
  - Forward Rates vs Futures Rates
  - Futures vs. Forwards
  - Futures-Forward
key_concepts:
  - Daily settlement impact
  - Futures contract P&L
  - Futures rates exceed forward rates
  - One-factor term structure model
  - Volatility and time
---

# 12.6 THE FUTURES-FORWARD DIFFERENCE  

By definition, borrowers and lenders can lock in market forward rates, and earlier sections of this chapter show that, ignoring daily settlement, borrowers and lenders can also lock in market futures rates. This section explains that, because of daily settlement, market futures rates exceed market forward rates. However, the magnitude of the difference turns out to be small except for contracts of the longest terms.  

If a trader receives fixed at $2\%$ through a forward agreement, all of the P&L from the agreement is realized at its expiration. But if the trader buys an otherwise identical futures contract at $2\%$ , that same total P&L is realized over time. More specifically, when rates are falling and the futures contract is making money, daily settlement profits are reinvested at relatively low rates. And when rates are rising and the futures contract is losing money, daily settlement losses have to be financed at relatively high rates. Therefore, averaging across scenarios of both falling and rising rates, receiving daily settlement payments over time is worse than receiving all of the  

P&L at the end. Hence, traders require a higher rate when buying a futures contract than when receiving fixed in a forward agreement. Or, in reverse, other traders willingly accept a higher rate when selling a futures contract than when paying fixed in a forward agreement. In this example, the futures rate exceeds the forward rate of $2\%$ . Furthermore, based on the logic of that result, the difference between the two rates increases with the length of time to expiration of the contracts and with the volatility of interest rates.  

Appendix A12 proves, in general, that the futures rate exceeds the. forward rate.10 For the purposes of understanding orders of magnitude,. however, Table 12.12 presents some results, without proof, from a normal one-factor term structure model with a constant drift and with a constant volatility of 80 basis points per year. This volatility is chosen to be roughly consistent with the levels shown in Chapter 16. In any case, the rows of the table in the first and second panels correspond to the three different kinds of futures contracts described in this chapter: three-month contracts on a term rate (Euribor futures); one-month contracts on an average of overnight rates (fed funds and SOFR futures); and three-month contracts on compounded overnight rates. The first panel gives the formulas for the differences between futures and forward rates in the model just described, where. $\sigma$ denotes the annual normal volatility (e.g.,. $0.8\%$ for 80 basis points); $\beta$ denotes the term of the underlying rate, in years, which, for the contracts.  

IABLE 12.12 The Futures-Forward Rate Difference for Selected Contracts in a One-Factor Model with a Volatility of 80 Basis Points per Year.   


<html><body><table><tr><td>Underlying Rate</td><td>Contract Examples</td><td>Formula</td><td>β</td></tr><tr><td>Term</td><td>3m Euribor</td><td>o²t2 o²tβ + 2 2</td><td>0.25</td></tr><tr><td>Avg. ON</td><td>1mFF/SOFR</td><td>o²tβ o²β2 +</td><td>1</td></tr><tr><td></td><td></td><td>2 6 ot2 o²tβ o²β2</td><td>12</td></tr><tr><td>Comp. ON</td><td>3m SOFR</td><td>+ 2 2 3</td><td>0.25</td></tr><tr><td></td><td>t=1</td><td>Fut-Fwd Difference (bps) t=2</td><td>t=5</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>Term</td><td>3m Euribor</td><td>1.4</td><td>8.4</td></tr><tr><td>Avg. ON</td><td>1m FF/SOFR</td><td>1.3</td><td>8.1</td></tr><tr><td>Comp. ON</td><td>0.3 0.4</td><td>1.5</td><td>32.3 8.4 32.8</td></tr></table></body></html>  

shown, is either 0.25 or 1/12; and $t$ denotes the time to the beginning of the rate reference period. As an illustration of $t$ from the examples in the text, the beginning of the reference period of the three-month June Euribor and three-month June SOFR contracts depicted in Figure 12.5 - June 15 - is 152 days or about $t=0.42$ years from the trade date of January 14.  

The second panel of Table 12.12 gives the differences between the futures and forward rates in the model for each of the contract types and for four values of $t$ , in basis points. The first point to notice is that futures-forward rate differences for a given. $t$ do not vary much across contracts. The reason for this can be seen from the formulas in the first panel. With $\beta$ relatively small, the dominant term in all the formulas is the common term $\sigma^{2}t^{2}/2$ . The second point to notice is that the futures-forward rate difference is relatively small except for the longest times to the beginning of the reference period. This is again explained by the dominant term, $\sigma^{2}t^{\bar{2}}/2$ , which increases with the square of. $t$ . That term alone, in fact, is a. good approximation for all of the terms in the given formulas: for $t=10$ for example, $\sigma^{2}t^{2}/2$ equals 32 basis points, which approximately equals the exact solution for all of the contract types..  

# Interest Rate Swaps  

nterest rate swaps (IRS) are contracts in which two counterparties agree to exchange a sequence of interest payments on some notional amount of currency. In an overnight index swap (OIs), payments based on a fixed rate of interest are exchanged for payments based on a floating, overnight rate, which changes daily with market conditions. The swaps introduced in Chapter 2 are OIS, in which the floating rate is the Secured Overnight Financing Rate (SOFR) defined and discussed in Chapters 10 and 12. A fixed-for-floating swap is similar, but the floating rate is a term rate, rather than an overnight rate. Euribor swaps are fixed-for-floating swaps, in which the floating rate is typically the three-month Euribor rate described. in Chapter 12. Historically, the most common IRS across currencies were fixed-for-floating London Interbank Offered Rate (LIBOR) swaps, in which the floating rate was LIBOR of some term. However, with the transition away from LIBOR, as described in Chapter 12, these swaps are disappearing. OIS and fixed-for-floating swaps are the main focus of this chapter.  

There are several classes of derivatives closely related to IRs, includ-. ing forward-rate agreements (FRAs) (see Chapter 12), caps and floors, and. swaptions (see Chapter 16). While traditionally not called "swaps" by the financial industry, these products are defined as "swaps" in the Dodd-Frank Act, which can cause some terminological confusion. In any case, these products are discussed elsewhere in this book but are included in the market size statistics presented in this chapter..  

The first section of this chapter describes the size of the IRS market and. how various market sectors use swaps. The second section builds on the introduction of IRS in Chapter 2 and of short-term rates in Chapter 12 to. present more detail on cash flows, pricing, and risk metrics. The third section uses several examples and cases to illustrate how IRS are used to manage risk.. The fourth section addresses the risk that a swap counterparty defaults on. contractual obligations, that is, counterparty credit risk, and describes the posting of collateral or margin to mitigate this risk. The fifth section explains swaps clearing, through which the two counterparties to a swap legally face.  

a clearinghouse instead of each other. The sixth section introduces basis swaps and basis swap spreads and explains how swaps that reference nearly risk-free, floating-rate indexes, like SOFR, are priced differently from swaps referencing other floating-rate indexes.  
