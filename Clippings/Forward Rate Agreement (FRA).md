$$
\begin{array}{|l|l|l|}
\hline
\multicolumn{3}{|c|}{\text{FRAs vs. Interest Rate Futures}} \\
\hline
\textbf{Feature} & \textbf{Forward Rate Agreement (FRA)} & \textbf{Interest Rate Futures} \\
\hline
\text{Trading Venue} & \text{OTC market. They are privately negotiated between two parties (usually banks or financial institutions).} & \text{They are traded on organized exchanges (e.g., the Chicago Mercantile Exchange).} \\
\text{Standardization} & \text{Highly customizable.} & \text{Standardized contracts.} \\
\text{Settlement} & \text{Cash settlement at maturity. The difference between the agreed-upon rate and the prevailing market rate at settlement is exchanged.} & \text{Daily mark-to-market settlement. Gains and losses are settled daily based on the change in the futures price.} \\
\text{Liquidity} & \text{Generally less liquid than futures. Finding a counterparty for a specific FRA can be more challenging.} & \text{Highly liquid on the exchanges.} \\
\text{Purpose} & \text{They are primarily used for hedging interest rate risk.} & \text{They are used for both hedging and speculation, where traders look to profit from anticipated changes in interest rates.} \\
\text{Risks} & \text{Counterparty risk exists since it's an OTC contract.} & \text{Lower risk due to the exchange's clearinghouse acting as a counterparty for all trades.} \\
\hline
\end{array}
$$
title: Forward Rate Agreement (FRA)
source: https://www.investopedia.com/terms/f/fra.asp
description: Forward rate agreements are over-the-counter contracts between parties
  that determine the rate of interest to be paid on an agreed-upon date in the future.
tags:
  - derivative_contract
  - forward_rate_agreement
  - fra
  - interest_rate_risk
  - otc_contract
aliases:
  - FRA
  - Forward
  - Interest Rate Agreement
key_concepts:
  - Fixed vs. floating rates
  - Interest rate derivative
  - Locking future interest rates
  - Market interest rate expectations
  - OTC interest rate contract
---


Definition

A forward rate agreement is an over-the-counter contract between parties that determines the rate of interest to be paid on an agreed-upon date in the future.

## What Is a Forward Rate Agreement (FRA)?

A forward rate agreement (FRA) is an over-the-counter (OTC) contract between parties in which the underlying is an interest rate. In an FRA, one side of the contract, called the long side, is obligated to pay a fixed-rate interest on a given amount in the future. The other party, called the short side, must pay according to a floating interest rate index on the same future date for the same amount. The duration of an FRA is typically one interest rate period, e.g., 90 days, but it can be whatever length of time the parties agree on.

FRAs provide a glimpse into the market's expectations for future interest rates. Unlike implied forward rates, which are derived from rates trading right now, FRAs are traded directly in the market, offering a more direct view of where market participants believe interest rates are headed.

At their core, FRAs are derivative contracts with a value that is based on an underlying interest rate index. When an FRA is initiated, its value is zero, and neither party pays a premium. The fixed rate in an FRA contract is the market's consensus view of where the underlying interest rate will be at the contract's maturity date. This makes FRAs valuable for gauging market sentiment and managing interest rate risk. By locking in a future interest rate, businesses and investors can protect themselves from potential rate changes.  

### Key Takeaways

- Forward rate agreements (FRAs) are over-the-counter (OTC) contracts between parties that determine the rate of interest to be paid on an agreed-upon date in the future.
- Forwards are OTC agreements that aren't standardized and sold via exchanges like the Chicago Mercantile Exchange. The underlying of FRAs is the interest rate.
- The notional amount is not exchanged but is cash based on the rate difference and the contract's notional value.
- FRAs are used when borrowers want to lock in their borrowing costs for the future.

## How Forward Rate Agreements Work

FRAs typically involve two parties exchanging a fixed interest rate for a variable one. The party paying the [fixed rate](https://www.investopedia.com/terms/f/fixedinterestrate.asp) is the borrower or long side, while the party paying the variable rate is the lender or short side.

People enter into an FRA wanting to lock in an interest rate if they believe rates are likely to rise. As such, they want to fix their borrowing costs today through the agreement. Suppose the U.S. Federal Reserve is likely to hike U.S. interest rates in a monetary tightening cycle. Companies would then want to fix their borrowing costs before rates rise too dramatically.

FRAs are very flexible, and settlement dates can be tailored to the needs of those involved in the transaction. The cash difference between the FRA and the reference rate or floating rate is settled on the [value date](https://www.investopedia.com/terms/v/valuedate.asp) or [settlement date](https://www.investopedia.com/terms/s/settlementdate.asp).  

## Formula and Calculation for a Forward Rate Agreement (FRA)

$\begin{aligned} &\text{FRAP} = \left ( \frac{ ( R - \text{FRA} ) \times NP \times P }{ Y } \right ) \times \left ( \frac{ 1 }{ 1 + R \times \left (\frac{ P }{ Y } \right ) } \right ) \\ &\textbf{where:} \\ &\text{FRAP} = \text{FRA payment} \\ &\text{FRA} = \text{Forward rate agreement rate, or fixed interest} \\ &\text{rate that will be paid} \\ &R = \text{Reference, or floating interest rate used in} \\ &\text{the contract} \\ &NP = \text{Notional principal, or amount of the loan that} \\ &\text{interest is applied to} \\ &P = \text{Period, or number of days in the contract period} \\ &Y = \text{Number of days in the year based on the correct} \\ &\text{day-count convention for the contract} \\ \end{aligned}$

1. Calculate the difference between the forward and floating rates or reference rates.
2. Multiply the rate difference by the notional amount of the contract and by the number of days in the contract. Divide the result by 360 (days).
3. In the second part of the formula, divide the number of days in the contract by 360 and multiply by the reference rate. Add this result to 1 and then divide 1 by that value.
4. Multiply the result from the right side of the formula by the left side of the formula.

### Example of a Forward Rate Agreement

Suppose Company A enters into an FRA with Company B in which Company A will receive a fixed (reference) rate of 4% on a principal amount of $5 million in half a year, and the FRA rate will be set at 50 [basis points](https://www.investopedia.com/terms/b/basispoint.asp) less than that rate. In return, Company B will receive the one-year term secured overnight financing rate (SOFR), determined in three years, on the principal amount.

The SOFR is an influential interest rate banks use to price U.S. dollar-denominated derivatives and loans. The daily SOFR is taken from the [Treasury](https://www.investopedia.com/articles/investing/073113/introduction-treasury-securities.asp) repurchase market, where investors offer banks overnight loans backed by their bond assets. Term SOFR is a forward-looking rate, providing a term structure for SOFR to be used in floating-rate loans and notes.

The agreement will be settled in cash at the beginning of the forward period, discounted by an amount calculated using the contract rate and period.

The formula for the FRA payment takes into account these five variables:

- FRA = the FRA rate
- R = the reference rate
- NP = the [notional principal](https://www.investopedia.com/terms/n/notionalprincipalamount.asp)
- P = the period, which is the number of days in the contract period
- Y = the number of days in the year based on the correct [day-count convention](https://www.investopedia.com/terms/d/daycount.asp) for the contract

Assume the following data and plug these numbers into the formula above:

- FRA = 3.5%
- R = 4%
- NP = $5 million
- P = 181 days
- Y = 360 days

The FRA payment (FRAP) is thus calculated as:

$\begin{aligned} \text{FRAP} &= \left (\frac{ (0.04 - 0.035) \times \$5\ \text{Million} \times 181 }{ 360 } \right ) \\ &\quad \times \left ( \frac{ 1 }{ 1 + 0.04 \times \left ( \frac{ 181 }{ 360 } \right ) } \right ) \\ &= \$12,569.44 \times 0.980285 \\ &= \$12,321.64 \\ \end{aligned}$

If the payment amount is positive, then the FRA seller pays this amount to the buyer. Otherwise, the buyer pays the seller. Remember, the day-count convention is typically 360 days in a year. Note also that the notional amount of $5 million is not exchanged. Instead, the two companies involved in this transaction use that figure to calculate the interest rate differential.  

## Forward Rate Agreement (FRA) vs. Interest Rate Futures

FRAs are different from interest rate futures, though both are derivatives based on the expectation of future interest rates.

### Customization

The main difference between FRAs and [interest rate futures](https://www.investopedia.com/terms/i/interestratefuture.asp) lies in their level of customization. As OTC contracts, FRAs can be made to the parties' specifications. The terms of the agreement, such as the notional amount, fixed interest rate, and settlement date, can be tailored to meet the specific needs of the counterparties.

By contrast, interest rate futures are standardized contracts traded on exchanges. They have fixed contract sizes, expiration dates, and other terms, which makes them less adaptable to unique hedging requirements. However, this standardization also makes interest rate futures more liquid and easier to trade.

### Counterparty Risk

Since FRAs are private agreements between two parties, each party is exposed to the risk that the other may default on their obligations. This means that the creditworthiness of the counterparty is a crucial consideration in FRA transactions.

Interest rate futures, meanwhile, are traded through exchanges, which act as the intermediary between buyers and sellers. The exchange clearing house guarantees the contracts, significantly reducing [counterparty risk](https://www.investopedia.com/terms/c/counterpartyrisk.asp) for traders.

### Settlement and Regulation

The settlement processes for FRAs and interest rate futures also differ. FRAs are typically settled in cash at the end of the contract term, with the payment based on the difference between the agreed-upon fixed rate and the prevailing market rate. Interest rate futures are marked to market daily, meaning that gains and losses are realized on a daily basis.

Moreover, because interest rate futures are exchange-traded, they are subject to greater regulatory oversight than FRAs. This increased regulation provides more transparency and reduces the risk of default.

<table><thead><tr><th colspan="3">FRAs vs. Interest Rate Futures</th></tr><tr><th><b>Feature</b></th><th><b>Forward Rate Agreement (FRA)</b></th><th><b>Interest Rate Futures</b></th></tr></thead><tbody><tr><td><b>Trading Venue</b></td><td><br>OTC market. They are privately negotiated between two parties (usually banks or financial institutions).</td><td>They are traded on organized exchanges (e.g., the Chicago Mercantile Exchange).</td></tr><tr><td><b>Standardization</b></td><td>Highly customizable.</td><td>Standardized contracts.</td></tr><tr><td><b>Settlement</b></td><td>Cash settlement at maturity. The difference between the agreed-upon rate and the prevailing market rate at settlement is exchanged.</td><td>Daily mark-to-market settlement. Gains and losses are settled daily based on the change in the futures price.</td></tr><tr><td><b>Liquidity</b></td><td>Generally less liquid than futures. Finding a counterparty for a specific FRA can be more challenging.</td><td>Highly liquid on the exchanges.</td></tr><tr><td><b>Purpose</b></td><td>They are primarily used for hedging interest rate risk.</td><td>They are used for both hedging and speculation, where traders look to profit from anticipated changes in interest rates.</td></tr><tr><td><b>Risks</b></td><td>Counterparty risk exists since it's an OTC contract.</td><td>Lower risk due to the exchange's clearinghouse acting as a counterparty for all trades.</td></tr></tbody></table>

## Limitations of Forward Rate Agreements

The downside of FRAs is the risk borrowers face if the market rate has moved adversely, causing the borrower to take a loss on the cash settlement. The FRA also has lower levels of regulation and oversight related to the transaction compared with [futures contracts](https://www.investopedia.com/terms/f/futurescontract.asp).

It can sometimes be difficult for a party to close an FRA before the maturity date, and the agreements are also subject to counterparty risk, as there is a potential that a contract participant could default.

## What Happens If You Sell a Forward Rate Agreement (FRA)?

The seller of a forward rate agreement (FRA), or the lender in the transaction, agrees to accept a fixed interest rate at a predetermined future date. If there has been a decrease in the floating market interest rate, then the FRA seller benefits from having locked in the higher rate.  

## Why Would You Buy a Forward Rate Agreement?

The main reason to buy a forward rate agreement (FRA) is to [hedge](https://www.investopedia.com/terms/h/hedge.asp) against future increases in interest rates. By locking in an interest rate to be paid at a specific date in the future, FRA purchasers provide themselves with a measure of protection should market rates rise.

## What Was LIBOR and Why Was It Abandoned?

The London Interbank Offered Rate or [LIBOR](https://www.investopedia.com/terms/l/libor.asp) was a benchmark interest rate at which major global banks lent to one another in the international interbank market for short-term loans.

The decision to abandon LIBOR was primarily driven by two key factors: manipulation scandals and the evolving nature of financial markets. In the early 2010s, investigations revealed that several banks had manipulated LIBOR submissions to benefit their trading positions, undermining trust in the rate's integrity. In addition, the 2007 to 2008 financial crisis exposed the fragility and potential unreliability of the interbank lending market. With fewer banks participating in daily rate submissions, LIBOR was no longer a good or reliable benchmark.  

## The Bottom Line

An FRA is an OTC contract that establishes an interest rate to be paid at a predetermined future date. The parties in the FRA do not exchange the notional amount. Instead, they settle the contract in cash based on the rate difference and the contract’s notional value.

Parties can enter into an FRA to hedge against or benefit from future interest rate movements. Borrowers can use an FRA to fix their borrowing costs, while lenders can lock in a predetermined rate should market rates fall.

Article Sources

1. Pooya Farahvash. "[Asset-Liability and Liquidity Management](https://www.wiley.com/en-in/Asset+Liability+and+Liquidity+Management-p-9781119701880)," Pages 55-59, 71-72. John Wiley & Sons, 2022.
2. YieldCurve.com. “[Learning Curve: Forward Rate Agreements](http://www.yieldcurve.com/Mktresearch/LearningCurve/FRAs.pdf).” Page 5.
3. John C. Hull. "[Options, Futures, and Other Derivatives](https://www.pearson.com/en-us/subject-catalog/p/options-futures-and-other-derivatives/P200000005938/9780136939917),” Pages 88–90, 162–163, 815. Pearson, 2022.
4. Securities Institute of America. “[Forward Rate Agreement Meaning & Definition](https://securitiesce.com/definitions/6270-forward-rate-agreement-fra).”

Partner Links