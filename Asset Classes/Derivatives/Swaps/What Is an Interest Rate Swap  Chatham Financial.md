---
Owner: RRoger Lin
tags:
  - Swaps
---
# WHAT IS AN INTEREST RATE SWAP CHATHAM FINANCIAL

[https://www.chathamfinancial.com/insights/what-is-an-interest-rate-swap](https://www.chathamfinancial.com/insights/what-is-an-interest-rate-swap)
[[Swaps]]
[[Swaps Part 2]]
[[Swaps Lecture Notes]]

![[what-is-an-interest-rate-swap.jpg]]

### INTEREST RATE SWAP CASH FLOW

A common swap structure in CRE finance is a pay-fixed swap, in which the borrower pays a periodic fixed-rate (often monthly in the U.S. and quarterly in Europe) and receives SOFR in return. This structure complements the underlying payment structure of many CRE floating-rate loans and, in conjunction with a floater, gives a borrower a fixed-rate profile. The SOFR cashflows that the borrower receives on the swap net out the SOFR component of the loan interest and the borrower is left with a net fixed rate.

![[interest-rate-swap-diagram.png]]

### INTEREST RATE SWAP PRICING

The rate for a pay-fixed swap consists of two distinct components:

+ **Mid-market rate**: This is the market rate for a given swap structure and term. While it will differ based on the swap structure (a 5-year swap and a 10-year swap will likely have different mid-market rates) and may change over time (the rate for a 5-year swap is likely different today than what it was yesterday), in normal market conditions this rate should be an objective number. Different banks quoting the same structure at the same time should quote very similar mid-market rates (i.e. within a few tenths of a basis point of one another). This mid-market rate reflects what the market is pricing SOFR to average over a given term. A 5-year swap rate, for instance, is roughly the average of the [forward curve](https://www.chathamfinancial.com/insights/what-is-a-forward-curve) for SOFR for the next 5 years.

![[Untitled 20.png|Untitled 20.png]]

+ **Credit charge**: For any given executed swap, the swap provider will add a transaction-specific mark-up which is designed to compensate the swap provider bank for the credit risk they take in providing the swap, and to provide the bank’s trading desk (which is often a different P&L than the bank’s lending group) with a return. This mark-up will differ from deal-to-deal, and by the sponsor and the collateral securing the swap. For shorter dated swaps on low leverage mortgage debt, this charge may only be a few basis points. For longer dated swaps, the charge may be in the high single digits or teens, or even higher.

With this is mind, for a floating-rate loan that is swapped to fixed, the fixed-rate coupon is the sum of the mid-market swap rate, the credit charge on the swap, and the spread on the underlying loan.

![[Untitled 1 13.png|Untitled 1 13.png]]

### SWAP CONSIDERATIONS

Interest rate swaps, whether executed as a requirement in conjunction with a new financing or to manage risk on an existing loan, carry risks. Chatham encourages real estate investors to consider the following factors when contemplating a swap or a financing with a swap:

+ **Availability**: Swaps involve an exchange of payments between the borrower and the swap provider over time. These future obligations create credit risk for both parties. In practice, CRE investors will find that their ability to enter into a swap is contingent upon identifying a bank willing to underwrite their credit. In some cases, a borrower entity may have multiple banks that are willing to underwrite the borrower’s credit for a swap on an unsecured basis. This is most common with entities that have multiple unsecured lenders, like real estate investment trusts (REITs) or open-end fund vehicles. In other cases, the borrower entity may be required to provide some form of collateral to secure the swap. This is most common when the borrower is a single purpose entity (SPE) created to hold an asset and mortgage debt. In these cases, the borrower will likely need to secure the swap with the underlying asset, pari pasu to the loan. In practice, this will limit the borrower to swapping with the lender.
+ **Pricing**: As described above a swap rate is comprised of two components—the objective, structure-specific mid-market rate and the transaction-specific credit charge (or mark-up) added to it. Borrowers entering into a financing with a swap should understand that the mid-market rate can move significantly between the signing of a term sheet and the closing of a loan. Borrowers should also negotiate the credit charge before signing a term sheet—we’ve seen many borrowers award a loan based on small differences in spread without realizing that the credit charge on the swap more than offset any loan spread benefit.
+ **Documentation**: A swap will be documented with an ISDA Master and Schedule, industry standard documentation for [Interest Rate Derivatives](Teaching%20Notes%2010-%20Interest%20Rate%20Derivatives.md) like swaps. While these documents may be presented to a borrower by a swap provider as boilerplate (or rarely negotiated), they are typically heavily negotiated. Key provisions include language around termination events that can create cash events prior to loan maturity—language which can allow defaults on unrelated financings to trigger defaults on the swap, and language which can tie non-recourse carve-out guarantors to swap obligations.
+ **Mark-to-market**: Swaps may fluctuate between being an asset or a liability to a borrower over their life, based on the contracted swap rate relative to the market replacement rate at any given time for the remaining swap term. Depending on accounting approaches, quarter-over-quarter changes in mark-to-market value may flow through earnings if the swap does not receive appropriate accounting treatment. Investment platforms that use historical cost accounting may find that changes in swap mark-to-market impact fund returns.
+ **Prepayment**: Swaps may require a breakage payment if terminated early in conjunction with an asset sale or loan refinance, though this penalty will be less than the prepayment penalty on a similarly couponed fixed-rate loan. Swaps may also be structured with open prepay windows to limit potential prepayment costs.