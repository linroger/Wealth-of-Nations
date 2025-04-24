 
source: 
  https://www.investopedia.com/articles/active-trading/111414/how-value-interest-rate-swaps.asp
description: An interest rate swap is a contractual agreement between two parties
  agreeing to exchange cash flows of an underlying asset for a fixed period of time.
tags:
  - counterparties
  - fixed_interest_rates
  - floating_interest_rates
  - interest_rate_swaps
  - sofr
aliases:
  - IRS
  - Interest Rate Swap
  - Swap Values
key_concepts:
  - benchmark interest rates
  - fixed vs floating rates
  - interest rate swap
  - manage financial risks
  - notional amount
---


FluxFactory / Getty Images

Every day, businesses are trying to protect themselves from unpredictable interest rates that could eat into their profits. A major tool in their arsenals is interest rate swaps.

An interest rate swap is a financial agreement where two parties—typically corporations and banks—trade interest payment obligations with each other. One party agrees to pay a fixed interest rate to the other party in exchange for receiving a floating (variable) rate payment. For those who have had home mortgages, it's like trading a variable-rate mortgage for a fixed-rate one, except on a much larger scale.

These swaps serve a vital purpose: helping companies and financial institutions manage their risk and potentially save money on interest payments. Just like you might want the certainty of a fixed-rate mortgage instead of watching your payments bounce up and down with market rates, businesses use interest rate swaps to gain more predictable costs. Below, we take you through how to assess the value of each side in a swap.

### Key Takeaways

- Most swaps are customized agreements between two parties and traded over-the-counter rather than on exchanges.
- Interest rate swaps let companies trade floating interest rates for fixed ones (or vice versa), helping them better manage their financial risks and costs.
- The two parties in a swap are called counterparties - one pays a fixed rate while the other pays a floating rate based on benchmark rates like the [Secured Overnight Financing Rate](https://www.investopedia.com/secured-overnight-financing-rate-sofr-4683954) (SOFR).
- Unlike loans, the principal amount (called the notional amount) in a swap is never exchanged; only the interest payments are traded between parties.
- Swaps start with zero value but can become costly as market interest rates change.

Two parties swap interest rates for many, including the desire to change the nature of the assets or liabilities to protect against anticipated adverse interest rate movements. Like all derivatives, swaps are zero-sum instruments, so any value increase for one party is a loss to the other.

The counterparty making payments on a floating rate typically uses benchmark interest rates, such as the SOFR. Those making payments on the fixed-interest rate are benchmarked to [U.S. Treasury bonds](https://www.investopedia.com/terms/t/treasurybond.asp).

## Understanding Interest Rate Swaps

Suppose there are two companies: Company A has a $10 million loan with a floating rate that changes every three months, while Company B has a fixed-rate loan for the same amount. If Company A worries rates will rise while Company B thinks they'll fall, they might enter into a swap agreement. Through the swap, Company A effectively converts its floating rate to a fixed one, while Company B gets the floating rate it wants.

[Interest rate swaps](https://www.investopedia.com/terms/i/interestrateswap.asp) involve several key components:

- **Notional amount**: This is the base amount used to calculate interest payments (like the $10 million in our example). Unlike a loan, this amount is never exchanged – it's just used for calculations.
- **Term**: The length of the swap agreement, typically ranging from two to 10 years.
- **Payment frequency**: How often the parties exchange payments, usually quarterly or semiannually.
- **Benchmark rate**: For the floating portion, payments are typically based on SOFR, which replaced LIBOR as the standard benchmark.

### Important

In 2023, LIBOR, formely used for variable rates, was phased out and replaced by [SOFR](https://www.investopedia.com/secured-overnight-financing-rate-sofr-4683954).

The popularity of interest rate swaps has exploded because they're incredibly flexible. Companies can customize the terms to match their exact needs, and they can usually find a bank willing to take the other side of the trade. However, this flexibility comes with risks—if interest rates move significantly, one party would face large losses.  

## How Is the Fixed Rate Determined?

When two parties enter into an interest rate swap, the key question is: What should the fixed rate be? The golden rule is that at the start, neither party should have an advantage—the swap should begin with zero value for both sides.

Let's say Apple Inc. ([AAPL](https://www.investopedia.com/markets/quote?tvwidgetsymbol=AAPL)) enters into a one-year swap agreement with Goldman Sachs ([GS](https://www.investopedia.com/markets/quote?tvwidgetsymbol=GS)) for $2.5 billion (called the [notional](https://www.investopedia.com/terms/n/notionalvalue.asp) amount). Apple agrees to receive fixed quarterly payments from Goldman Sachs in exchange for making floating-rate payments back to them. The floating payments will be based on market rates (SOFR), but what should the fixed rate be?

The value of the fixed leg and floating leg of the swap will be *V <sub>fix</sub>* and *V <sub>fl,</sub>* respectively. Thus, at the beginning they should be the same:

$V_{fix} = V_{fl}$

Notional amounts are not exchanged in interest rate swaps because these amounts are equal; it doesn't make sense to exchange them. Now, let's assume the SOFR rates (in dollars) are as follows:

| USD SOFR Rates | Percentage |
| --- | --- |
| 3 month | 5.33% |
| 6 month | 5.28% |
| 9 month | 5.20% |
| 12 month | 5.15% |

To determine a fair fixed rate, banks use a complex formula that considers the following:

- Current market interest rates for different periods
- The payment schedule (quarterly in this case)
- The swap's duration
- The notional amount

While the math behind this calculation is somewhat complex (and we'll show it for those interested), the principle is straightforward: The fixed rate is set so neither party starts off with an advantage.

**Step 1: Calculate the Discount Factors**

Let's now walk through the mathematics. The formula for determining the fixed rate involves calculating what's called "discount factors"—essentially a way to determine the present value of future payments. These factors are derived from current market interest rates.  

The discount factor (DF) formula is:

$DF = 1/(1 + r × t/360)$  

Where:  
r = SOFR rate for the period  
t = number of days in the period

This gives us the following table:

| Period | Days | SOFR Rate | Calculation | Discount Factor |
| --- | --- | --- | --- | --- |
| 3 Months | 90 | 5.33% | 1/(1 +.0533 × 90/360) | 0.98685 |
| 6 Months | 180 | 5.28% | 1/(1 +.0528 × 180/360) | 0.97415 |
| 9 Months | 270 | 5.20% | 1/(1 +.0520 × 270/360) | 0.96198 |
| 12 Months | 360 | 515% | 1/(1 +.0515 × 360/360) | 0.95026 |

**Step 2: Fixed-Rate Calculation**

The formula for the fixed rate (c) is as follows:

Where:  
q = payment frequency per year (four for quarterly)  
DF₁₂<sub>ₘ</sub> = final period discount factor  

Plugging in our numbers, we get the following:  

$c = 4 × (1 - 0.95026) ÷ (0.98685 + 0.97415 + 0.96198 + 0.95026)$  
$c = 4 × 0.04974 ÷ 3.87324$

$c=0.0514$

That is, *c =* 5.14%

**Step 3: Calculate Payment Streams**

For the $2.5 billion notional amount:

Quarterly Fixed Payment = (5.14% ÷ 4) × $2.5 billion = $32.125 million  

| Date | Fixed Payment | Floating Payment\* |
| --- | --- | --- |
| Q1 2024 | $32.125M | $33.31M (based on 5.33%) |
| Q2 2024 | $32.125M | Set at the end of Q1 |
| Q3 2024 | $32.125M | Set at the end of Q2 |
| Q4 2024 | $32.125M | Set at the end of Q3 |

\*First floating payment = (5.33% ÷ 4) × $2.5 billion = $33.31M

Subsequent floating payments will be determined by the prevailing three-month SOFR rate at the start of each period. For now, at least, there's a slight advantage for Goldman Sachs, which is making the fixed payment. But that might change in the coming quarters.

**Future Calculations**

The swap starts with zero value but will fluctuate as interest rates change. At each payment date, you have to net the fixed and floating payments to determine which party owes the other.

### Tip

Numerous online calculators will take care of the mathematics to calculate interest rate swaps.

To find the value at any point:

1. Calculate the present value of the remaining fixed payments
2. Calculate the present value of the remaining floating payments
3. Subtract floating from fixed (from the receiver's perspective)

### Risk Mitigation For Institutions Paying Floating Rates During an Interest Rate Surge

If interest rates surge unexpectedly—like during a financial crisis—a company paying floating rates in a swap could face a severe financial cost. For example, during the 1980s savings and loan crisis, some companies saw their floating rates jump from 10% to over 20%. More recently, in 2022, companies with floating-rate obligations were caught off guard when rates rose faster than at any time in modern history.

To protect against such scenarios, companies often build in several safeguards:

- "Breakage clauses" that allow early termination (though usually with significant costs)
- Interest rate caps that set a maximum on floating rate payments
- "Knockout" provisions that terminate the swap if rates exceed certain levels
- Partial rather than full hedging to maintain some flexibility

However, these protections typically come at a price through higher fixed rates or upfront premium payments. The 2008 financial crisis taught many companies a harsh lesson about the importance of stress-testing their swap exposures against extreme scenarios.  

## What Exactly Is SOFR?

The Secured Overnight Financing Rate (SOFR) is based on actual transactions in the U.S. Treasury repurchase ([repo](https://www.investopedia.com/terms/r/repurchaseagreement.asp)) market, where financial institutions borrow cash overnight using U.S. Treasury securities as collateral. Unlike its predecessor LIBOR, which relied on bank estimates, SOFR is based on nearly $1 trillion in daily real transactions.

This makes it much harder to manipulate and more reflective of actual borrowing costs in the U.S. financial system. For everyday investors, SOFR's movements affect everything from adjustable-rate mortgages to corporate loans.

## Why Did LIBOR Have To Be Replaced?

[LIBOR's downfall](https://www.investopedia.com/terms/l/libor-scandal.asp) came after a major scandal in 2012 when several large banks were caught manipulating the rate for profit. Because LIBOR was based on daily estimates from banks rather than actual transactions, traders could influence the rate by submitting false data. The manipulation affected trillions of dollars worth of financial products worldwide, leading to billions in fines and several criminal convictions.

This scandal, combined with a decline in the lending activity LIBOR was meant to reflect, led regulators to phase it out for more transparent alternatives like SOFR.

## What Happens if One Party in A Swap Agreement Defaults?

Modern swap agreements typically include [credit support annexes](https://www.investopedia.com/terms/c/creditsupportannex.asp) that require parties to post collateral if their credit quality deteriorates or if the swap moves significantly in value. If a default occurs despite these protections, the party that's not defaulting can usually end the swap and receive compensation for any losses.

## Do Companies Need a Certain Credit Rating To Engage in Interest Rate Swaps?

While there's no official minimum credit rating requirement, most dealers require counterparties to have at least an [investment-grade rating](https://www.investopedia.com/terms/i/investmentgrade.asp) (BBB- or higher) to enter into swap agreements without posting collateral. Companies with lower ratings aren't completely excluded but may need to post significant collateral or pay higher rates. Some smaller or lower-rated companies might use "swap dealers"—typically larger banks that act as intermediaries – rather than dealing directly with other institutions.

## The Bottom Line

Valuing interest rate swaps comes down to a fundamental principle: at the beginning, both legs of the swap must have equal value. This is achieved through a careful calculation of discount factors based on current market rates, which helps determine the right fixed rate that makes the trade fair for both parties.

While the mathematics can be complex, the core concept is straightforward—the present value of expected fixed-rate payments must equal the present value of projected [floating-rate](https://www.investopedia.com/terms/f/floatinginterestrate.asp) payments. As market rates change over time, this initial equilibrium shifts, causing the swap's value to fluctuate. Understanding this valuation process is crucial because it forms the foundation for one of the most widely used [risk management](https://www.investopedia.com/terms/r/riskmanagement.asp) tools in modern finance.

Article Sources

1. John C. Hull. "[Options, Futures, and Other Derivatives](https://www.pearson.com/en-us/subject-catalog/p/options-futures-and-other-derivatives/P200000005938/9780136939917),” Pages 150–174. Pearson, 2022.
2. U.S. Securities and Exchange Commission. "[What You Need To Know About the End of LIBOR – Investor Bulletin](https://www.sec.gov/oiea/investor-alerts-and-bulletins/what-you-need-know-about-end-libor-investor-bulletin)."
3. PIMCO. "[Interest Rate Swaps](https://www.pimco.com/gbl/en/resources/education/understanding-interest-rate-swaps)."
4. R. S. Johnson. "[Derivatives Markets and Analysis](https://www.wiley.com/en-us/Derivatives+Markets+and+Analysis-p-9781118202692)," Pages 627-672. John Wiley & Sons, 2017.
5. International Swaps and Derivatives Association. "[The Impact of COVID-19 on Swaps Market Liquidity](https://www.isda.org/a/YfbTE/The-Impact-of-COVID-19-on-Swaps-Market-Liquidity.pdf)."
6. Federal Reserve Bank of New York. "[SOFR Averages and Index Data](https://www.newyorkfed.org/markets/reference-rates/sofr-averages-and-index)."
7. Council on Foreign Relations. "[Understanding the Libor Scandal](https://www.cfr.org/backgrounder/understanding-libor-scandal)."

Partner Links