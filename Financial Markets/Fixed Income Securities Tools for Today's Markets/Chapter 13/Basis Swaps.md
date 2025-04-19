---
tags:
  - basis_swaps
  - cross_currency_swaps
  - euribor
  - sofr
  - str
aliases:
  - Basis Swap
  - STR vs Euribor
key_concepts:
  - Basis risk definition
  - Credit risk perspective
  - Floating rate on one leg
  - Hedging basis risk
  - STR vs Euribor swap
---

# 13.6 BASIS SWAPS  

Both OIS and fixed-for-floating swaps pay interest at a fixed rate on one leg and at a floating rate on the other leg. A basis swap, by contrast pays interest at one floating rate on one leg and interest on a different floating rate on another leg. Before the transition away from LIBOR, basis swap volumes were particularly large in exchanging LIBOR of one term against LIBOR of another term, and swaps of effective fed funds (see Chapter 12) against LIBOR of various terms were common as well. In US dollar markets, swaps of SOFR against LIBOR are trading actively in the transition period but will fade with the disappearance of LIBOR. Cross-currency basis swaps have been and continue to be extremely popular. These swaps exchange interest at a short-term rate in one currency for interest at a short-term rate in another currency, for example, SOFR versus STR. This section focuses on basis swaps of STR versus three-month Euribor to explain concepts, both because Euribor is still an active rate and because foreign exchange rates are outside the scope of this edition of the book..  

Consider a bank that funds itself at STR flat (i.e., without a spread) and lends money to customers at three-month Euribor plus $1\%$ . This bank has the basis risk that STR, compounded over a relevant time period, rises relative to three-month Euribor, compounded over that same period. In general, by the way, the term "basis risk" refers to the risk that two rates or prices, which usually change together in some fixed or predictable relationship, diverge in an unusual and unfavorable way. In any case, Figure 13.8 shows how the bank can hedge its basis risk with an STR versus three-month Euribor basis swap. As of February 2022, the two-year STR versus three-month Euribor basis swap spread was 13.8 basis points, which means that the bank, as shown in the figure, can receive STR plus 13.8 basis points and pay three-month Euribor on some notional amount for two years. More specifically, at the end of every quarter during those two years, the bank receives interest at daily compounded STR plus 13.8 basis points over that quarter (along the lines of Figure 13.1), and the bank pays interest at three-month Euribor set at the start of the quarter (along the lines of Figure 13.2). Overall then, with its basis swap hedge, the bank in Figure 13.8 locks in a fixed rate of $1.138\%$ , so long as its customers do not default. Put another way, the customers pay a credit and liquidity spread of $1.138\%$ over the near-riskless  

![](b0d412560b6aeadd8f4fdbdf905006979c90cbe984ed2376fdcdfb126b19ce55.jpg)  
FIGURE 13.8 Hedging Basis Risk with an STR versus Three-Month Euribor Basis Swap.  

ESTR: $1\%$ as a spread over three-month Euribor and 13.8 basis points as a spread of three-month Euribor over STR.  

From the swap dealer's perspective, there is virtually no credit risk: the. bank itself is probably a good credit and the basis swap is collateralized.. Because Euribor is a riskier rate than STR, however, compounded STR. over a quarter will normally be less than three-month Euribor. It makes sense, therefore, that paying a spread over STR is fair against receiving. three-month Euribor, although the market determination of the exact spread can certainly be the subject of further analysis..  

The existence of basis swap spreads shows that not all swaps can be valued using the methodology for pricing swaps that is given in Chapter 2 and earlier in this chapter. That methodology argued that the floating leg (including the fictional notional amount) is worth par when the floating rate is considered to be the risk-free rate, that is, the rate at which funds can be moved without risk across time. And it is reasonable to classify both overnight SOFR and overnight STR as risk-free rates.19 The same is not true, however, for three-month Euribor. Or, to put it another way, it cannot be simultaneously true that i) a floating leg paying STR is worth. par; ii) STR plus 13.8 basis point is fair against three-month Euribor for. two years; and iii) a floating leg paying three-month Euribor for two years is worth par.  

The appropriate methodology for valuing a fixed-for-floating swap when the floating index is not a risk-free rate, like Euribor, is the following. First, discount the fixed cash flows (including the fictional notional amount) at the discount factors implied by swaps against the risk-free rate index,. like STR. These calculations are described in Chapter 2. Second, the value. of the floating leg is equal to par plus the present value of payments of the basis swap spread, where discounting is again done using the risk-free rates. For example, the basis swap in Figure 13.8 shows that the value of receiving three-month Euribor equals the value of receiving STR plus 13.8 basis points. But the value of receiving STR (including the fictional notional amount) is par. Therefore, the value of receiving three-month Euribor quarterly for two years is par plus the present value of receiving. 13.8 basis points, paid quarterly, for two years.  

Appendix A13.1 illustrates the calculations outlined in the previous paragraph with representative market rates toward the end of February 2022, when the fixed rate on a two-year, fixed versus three-month Euribor swap was $0.078\%$ and, as already mentioned, the two-year STR versus. three-month Euribor basis swap spread was 13.8 basis points. The values of both the fixed and floating sides are calculated to be 100.281. To summarize, when the floating index is a risk-free rate, both sides of a fixed-for-floating swap at initiation are worth par. When the floating index is not a risk-free rate, but trades with a positive basis swap spread against the risk-free rate, both sides of the swap at initiation are equal in value, of course, but each side is worth more than par. Note that traders may just accept that rates on newly initiated swaps are fair and, therefore, may not care about the value of each side separately. Nevertheless, a methodology is required to compute the NPVs of existing swaps in a trading book, which are not observable in the market..  

The pricing methodology just described can take rates on STR swaps and spreads on STR versus three-month Euribor basis swaps as given to price fixed versus three-month Euribor swaps. Alternatively, the methodol-. ogy can take rates on STR swaps and on fixed versus three-month Euribor. swaps as given to imply fair basis swap spreads. The latter approach, called two-curve pricing, is often preferred when basis swaps of all terms are insufficiently liquid. In fact, two-curve pricing typically does not explicitly calculate basis swap spreads at all. A brief description of this methodology is given in Appendix A13.2.  

# Corporate Debt and Credit Default Swaps  

existing debt, stock repurchases). The loans and bonds used to raise these funds are subject to credit risk, because corporations may not make good on their promises to pay interest and repay principal. Lenders, in turn, require compensation for bearing credit risk in the form of higher returns. The cash flows of credit default swaps (CDS) also depend on the payment or nonpayment of debt obligations but are not themselves obligations of corporate issuers. In other words, through CDS contracts, market participants trade corporate credit risks with each other. While this chapter focuses mostly on corporate debt, much of the discussion applies to sovereign and municipal debt as well, because the debt obligations of many governments have at times been perceived as subject to nontrivial probabilities of default.  

Many market participants rely to some extent on rating agencies to measure the credit risk of borrowers and their loans and bonds. The long-term debt ratings classifications of the three major rating agencies in the United States are given in Table 14.1. More granular breakdowns of each of these broad ratings classifications are also available, and short-term debt has its own, separate scales.'  

TABLE 14.1  Long-Term Debt Ratings Classifications. The Ratings in Each Entry Are Listed in Decreasing Order of Creditworthiness..   


<html><body><table><tr><td>Agency</td><td>Investment tGrade</td><td>SpeculativeGrade/ High Yield</td><td>Default</td></tr><tr><td>Moody's</td><td>Aaa, Aa, A, Baa</td><td>Ba, B, Caa, Ca</td><td>C</td></tr><tr><td>S&P, Fitch</td><td>AAA, AA, A, BBB</td><td>BB, B, CCC, CC, C</td><td>D</td></tr></table></body></html>  
