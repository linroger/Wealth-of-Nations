---
tags:
  - corporate_bonds
  - hedging
  - interest_rate_swaps
  - pension_liabilities
  - sovereign_debt
aliases:
  - IRS
  - pension fund
  - swap
key_concepts:
  - Exchange of interest payments
  - Floating-rate debt
  - Interest rate risk
  - Leveraged position in bond
  - Sovereign debt crisis
---

# 13.3 USES OF INTEREST RATE SWAPS  

IRS can be conceptualized in two ways: as a leveraged position in a bond (see Chapter 2) and as an exchange of interest payments. The first interpretation best explains the actions of market participants in increasing or decreasing their interest rate exposures. An asset manager deciding to pay. fixed, either as a bet that interest rates will rise or as a hedge against the interest rate risk of a corporate bond portfolio, is more interested in the DV01 of the swap than in the particular cash flows being exchanged. The first. three use cases described in this section - pensions, Greece, and Brunswick Corporation - fall into this category. The second interpretation of swaps. best explains the actions of market participants wanting to alter particular streams of cash flows. In the asset swap transactions described in Chapter 14, the owner of a corporate bond specifically wants to substitute the receipt of. bond coupon with the receipt of a floating rate plus a spread. The last two use cases described here -- bank loans and synthetic floating-rate debt -- fall into this category.  

# Pension Liabilities  

Say that a pension fund has long-term liabilities with a present value of $\$1$ billion and a DV01 of $\$2$ million. At the same time, based on its research. across corporate credits, it has invested $\$1$ billion in a portfolio of corpo-. rate bonds. However, because the universe of corporate bonds lies mostly in the five- to 10-year maturity range, and because the process of choos-. ing credits does not focus on maturity, the selected portfolio has a DV01 of only $\$500,000$ . This configuration exposes the pension fund to the risk. that interest rates fall: for every one-basis-point decline in rates, the value of the liabilities increase by $\$2$ million and the value of the assets increase. by $\$500,000$ , causing a funding gap of $\$1.5$ million. To hedge, the pension fund can receive fixed in a portfolio of long-term IRS with a total DV01 of $\$1.5$ million. The exact distribution of swaps across maturities is likely to be chosen to hedge against changes in different parts of the term structure. of rates, as explained in Chapter 5. In any case, note that receiving fixed in swaps does not require cash from the pension fund, except for posting margin, as described presently. In other words, the pension fund uses its cash to buy the assets it really wants, in this example corporate bonds, and then adjusts the resulting risk profile by trading swaps.  

# Greece Hedges Floating-Rate Debt  

During the sovereign debt crisis in 2010, Greece had borrowed money from other Eurozone countries at Euribor plus a spread.6 Toward the end of 2018, the loan balance was over. $\epsilon{50}$ billion, and 10-year swap rates had fallen to. around $1.60\%$ . Greece chose, therefore, to hedge the risk of future increases in Euribor by paying fixed in 10-year Euribor swaps. The problem, how-. ever, was that Greece had a below investment-grade credit rating and, as a sovereign, did not post collateral. This meant that Greece was not a particu-. larly attractive swap counterparty, particularly to dealers who had positive. NPVs on existing swaps with Greece. More specifically, i) without collat-. eral, the positive NPVs of dealers translated into outright credit exposures to Greece; and ii) these dealers had negative NPV on the hedges of their IRS with Greece, against which they typically had to post collateral and. incur funding costs.7 To overcome the reluctance of these dealers, Greece allowed them to novate their positive NPV swaps to dealers with negative NPV swaps. For example, if Dealer X had a swap with Greece with an NPV of $\epsilon1$ million, and Dealer Y had a swap with Greece with an NPV of $-\mathsf{\in}1$ million, then Dealer Y could pay Dealer X 1 million and take over its swap.. Both dealers would then have no current exposure to Greece; Dealer X could unwind its hedge and its associated funding cost; and, consequently, Dealer. X would no longer be reluctant to trade new swaps with Greece.8  

# Hedging Future Debt Issuance  

This use case starts by describing a forward swap or a forward-starting swap, with Figure 13.3 illustrating a three-year swap, one year forward. Through this forward swap, one counterparty agrees to pay fixed and receive floating for three years starting in one year, while the other agrees to receive fixed and pay floating. Importantly, the fixed rate is agreed on as of the trade date.  

![](6f47394373be38ea78b4ebec7c3d5cfe1fbbaed84f24b0a0c380a4aa60adc845.jpg)  
FIGURE13.3 A Three-Year Swap, One-Year Forward, with Annual Interest Payments.  

Now consider a corporation that plans to sell $\$100$ million of three-year bonds, but in one year's time. Assume that the corporation will be able to sell these bonds at a rate. $1.5\%$ over the then-prevailing three-year swap rate, and that the current three-year swap rate, one year forward is $1.0\%$ The corporation can then lock in a borrowing cost of $1\%+1.5\%=2.5\%$ by paying fixed today on. $\$100$ million of the. $1.0\%$ three-year swap, one year forward. Table 13.2 shows how the hedge works. Say that, one year later, the three-year swap rate has risen to $1.5\%$ . The corporation then issues $\$100$ million of three-year bonds at $3.0\%$ and receives fixed at $1.5\%$ on a $\$100$ million three-year swap. The net interest from the existing $1.0\%$ forward swap, which has become a three-year swap, the debt issue, and the new swap is. $-1.0\%-3.0\%+1.5\%=-2.5\%$ Alternatively, say that, one. year later, the three-year swap rate has fallen to $0.5\%$ . The corporation then. issues at $2.0\%$ and receives in a three-year swap at $0.5\%$ for the same net. of $-1.0\%-2.0\%+0.5\%=-2.5\%$ . Essentially, if rates rise, the corporation pays more on its debt, but wins on having locked in payment of a now low rate on the forward-starting swap. Conversely, if rates fall, the corporation pays less on its debt, but loses on having locked in payment of a now high rate on the forward-starting swap.  

TABLE 13.2 Debt Is Sold at $1.5\%$ over the Swap Rate. Hedge Future Debt Issuance by Paying Fixed at. $1\%$ on a Three-Year Swap, One Year Forward. The Three-Year Swap Rate in One Year Is Either $1.5\%$ or $0.5\%$   


<html><body><table><tr><td>3-Year Swap Rate</td><td>1.5%</td><td>0.5%</td></tr><tr><td>Trade</td><td>CashFlow</td><td>CashFlow</td></tr><tr><td>IssueDebt</td><td>-3.0%</td><td>-2.0%</td></tr><tr><td>ReceiveFixed</td><td>1.5%</td><td>0.5%</td></tr><tr><td>Pay Fixed on Fwd Starting Swap</td><td>-1.0%</td><td>-1.0%</td></tr><tr><td>Total</td><td>-2.5%</td><td>-2.5%</td></tr></table></body></html>  

In practice, instead of receiving fixed on a new swap at the time of issue, the corporation can unwind the forward-starting swap and apply its realized NPV to the debt issue. A positive NPV would reduce the higher cost of debt, perhaps by using that positive NPV as proceeds and selling less debt, while a negative NPV would increase the lower cost of debt, perhaps by selling more debt to pay off that negative NPV.  

Debt issuers sometimes find that forward swaps are expensive to trans-. act relative to spot-starting swaps. In that case, an issuer might pay fixed in a spot-starting swap on a notional amount set so the DV01 of the hedging swap matches the Dv01 of the forward sale of corporate bonds. Hedges with spot-starting swaps do entail some curve risk, however. For example, in the scenario of the previous paragraph, paying fixed on a spot-starting three-year swap leaves the debt, but not the hedge, exposed to changes in the one-year rate, three years forward. And paying fixed on a spot-starting four-year swap leaves the hedge, but not the debt, exposed to changes in. the one-year rate. In any case, note that swap hedges protect only against. changes in the swap rate. Any increases in corporate borrowing rates relative to the swap rate, which was assumed away in the example of the previous paragraphs, are clearly not hedged by swap positions.  

The Brunswick Corporation, which manufactures boats and other products, planned to issue $\$300$ million of fixed-rate debt in mid-2023. In January 2021, it entered into $\$150$ million of forward-starting swaps to hedge half of that issuance. Furthermore, it seems to have structured its hedges with various starting dates and maturities to account for uncertainty about the actual issuance dates. The treasurer indicated that the volume of hedges might increase over time as, presumably, the dates of issuance become firmer. In short, figuring out what needs to be hedged can be much more difficult than figuring out how to hedge.9  

# Bank Loans  

Banks prefer to make floating-rate loans to customers. First, from the perspective of asset-liability management, floating-rate assets naturally hedge deposits, which are floating-rate liabilities (and which constitute the overwhelming majority of bank funding). Second, as discussed in Chapter 14, floating-rate loans are much easier to sell in the secondary market than are fixed-rate loans. Many borrowers, however, want to lock in a fixed interest rate over some term of their borrowings. The reconciliation of bank and borrower objectives is achieved with IRS, as illustrated in Figure 13.4. The bank makes a floating-rate loan to the borrower, on which the borrower pays a floating rate. At the same time, the bank receives fixed from the borrower and, in a back-to-back swap, pays fixed to a dealer. The net result. for the customer is a fixed-rate loan: paying floating on the loan is offset by receiving floating on the swap, leaving only the fixed payments on the swap. The net result to the bank is the original floating-rate loan: the cash flows from the two swaps, by design, exactly offset each other. While many banks do facilitate their customer loan business as illustrated in the figure, with. back-to-back swaps, some hedge the aggregate risk of their customer swap portfolio with relatively few larger swaps..  

![](7bc703d561c7dedd762fb94dcc311c47c3b5ab6c5f84067e96f69cb8878cde90.jpg)  
FIGURE 13.4 Facilitating a Bank Loan with an Interest Rate Swap.  

# Synthetic Floating-Rate Debt  

As just discussed, banks borrow at floating rates through deposits and make floating-rate loans. Banks usually do want some amount of long-term funding, however, because an overreliance on short-term funding creates a vulnerability to withdrawals of that funding, either because of generally stressed financial conditions or because of concerns with that particular bank.. A bank might, therefore, choose to issue some long-term, floating-rate. debt, thus obtaining some cushion of floating-rate funding that is much less subject to withdrawals. As it turns out, however, the market for such debt is extremely limited. A practical solution, therefore, is to create synthetic. long-term, floating-rate debt, as illustrated in Figure 13.5. The bank sells. long-term debt in the more traditional, fixed-rate market, and then receives. fixed and pays floating in an IRS. The net result is long-term floating-rate debt, as desired.  

![](bb1e9e0f7f4c3d4f743b8bbf1f5e958c8d78643fa6ee8cd0406ef3e5cce2b105.jpg)  
FIGURE 13.5 Synthetic Issue of Floating-Rate Debt.  
