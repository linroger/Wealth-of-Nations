---
tags:
  - arbitrage
  - cds_bond_basis
  - cds_market
  - corporate_debt
  - credit_risk
  - repo_market
aliases:
  - Basis Trade
  - CDS-Bond Basis
  - Negative Basis Trade
  - Positive Basis Trade
key_concepts:
  - Arbitrage opportunity
  - Bond spread
  - CDS and bond pricing
  - CDS spread
  - Relative value trading
  - Repo market financing
---

# 14.8 CDS-BOND BASIS  

Credit risk today is traded in both the corporate debt market and in the CDS market. It is natural to ask, therefore, whether a particular credit trades at the same price in both markets or is cheaper in one market than the other. If the latter, then there might be relative value trading opportunities to buy. in one market and sell in the other..  

Table 14.12 sets the stage with a simplified relationship between selling CDS protection on a particular credit and buying a bond of that same credit, financed in the repo market.19 The table is a simplification by assuming that i) the CDS contract has an upfront payment of zero, that is, the CDS coupon equals the CDS spread; ii) the corporate bond is priced at par;. and iii) the CDS and the underlying bond mature on the same date. Under these assumptions, the table shows that selling CDS protection is equivalent to buying a bond and financing its purchase with term repo to the bond's maturity. More specifically, the cash flows from selling 100 notional of CDS are: zero today; the spread s on 100 until the earlier of default or maturity;. $-\:100(1-R)$ if and when the bond defaults; and zero if the bond matures. without a default. The cash flows from buying 100 face amount of the bond at a price of par are - 100 today; the coupon rate $c$ on the face amount to the earlier of default or maturity; $100R$ if and when the bond defaults; and  

TABLE 14.12 A Simplified Arbitrage Relationship Between Selling Protection on a Credit and Buying a Bond on That Same Credit, Financed by Repo.   


<html><body><table><tr><td></td><td>Today</td><td>Interim (%)</td><td>Default</td><td>Maturity/No Default</td></tr><tr><td>Sell CDS Protection</td><td>0</td><td>S</td><td>-100(1 - R)</td><td>0</td></tr><tr><td>BuyPar Bond</td><td>-100</td><td>C</td><td>100R</td><td>100</td></tr><tr><td>Sell Repo</td><td>100</td><td>-r</td><td>-100</td><td>-100</td></tr><tr><td>Total</td><td></td><td>C-r</td><td>-100(1 - R)</td><td></td></tr></table></body></html>  

100 if the bond matures without a default. Finally, the cash flows from borrowing the bond's purchase price through repo are 100 today; $-r$ on 100 until the earlier of default or maturity; and $-100$ at the earlier of default or maturity. (To clarify these repo cash flows, note that, if a bond defaults, the borrower has to unwind the repo position by paying off the 100 loan amount, which then ends interest payments on the loan.) Finally, adding the cash flows from purchasing the bond and selling the repo gives the "Total" row, which exactly matches the cash flows of selling CDS protection so long as $s=c-r$  

The CDS-bond basis refers to the difference between the CDS spread and some measure of the bond's spread over riskless rates. In the simplified setting of Table 14.12, where the bond spread is the difference between the par coupon and the matching-term repo rate, the CDS-bond basis is $s-(c-r)$ . If the basis is positive, then $s>c-r$ , which means that the bond is rich, or that it has a low spread relative to the CDS spread. Put another way, selling CDS protection earns more than buying the bond. If the basis is negative, then $s<c-r$ , which means that the bond is cheap relative to the. CDS spread, and that buying the bond earns more than selling CDS protection. In either case, when the basis is not zero, an arbitrage opportunity is available. If positive, execute a. $p$ ositive basis trade, that is, sell protection,. short the bond, and buy the repo, to lock in. $s-(c-r)>0$ per period until the earlier of default or maturity. And if the basis is negative, execute a neg-. ative basis trade, that is, buy protection, buy the bond, and sell the repo, to lock in $(c-r)-s>0$ per period.  

Crucial to these arbitrage arguments is that the term of the repo equal the maturity of the bond and the CDs. In a negative basis trade, for example, selling overnight - rather than term - repo exposes a trader to financing risk: the overnight repo rate might increase dramatically or repo funding might be withdrawn completely, either because the bond's creditworthiness has deteriorated, because general financing supply has tightened, or because the trader's own credit has come under stress. In any of these scenarios, the trader might very well be forced to unwind the position at a loss, that is, when the bond has become even cheaper relative to CDS. Similarly, in executing a positive basis trade with overnight repo, the financing risk is not being able to continue to borrow the bonds in order to maintain the short position.  

In practice, because there is no market for very long-term corporate repo, it is nearly impossible to execute a basis trade without bearing financing risk. Therefore, despite arbitrage arguments like Table 14.12, there is a fundamental difference between CDS and levered bond positions: CDS positions have implicit financing to maturity, while levered bond positions are inherently subject to financing risk.  

Outside the simplified setting of Table 14.12, market participants compute the CDS-bond basis using different measures of a bond's spread, like yield spread, bond spread, asset swap spread, and CDS-equivalent bond spread. The advantages and disadvantages of each of these is discussed previously, but all of these measures can be misleading in the context of the CDS-bond basis. Without a term-repo rate, any measure of the basis ignores. the financing risk in a CDS versus levered bond arbitrage trade..  

A lot of money was lost in negative basis trades through the financial crisis of 2007-2009. As funding conditions became more difficult, CDS-bond bases moved negative, reflecting the difficulty of going long credit risk with levered bond positions relative to selling CDS protections. Some traders, however, saw these negative bases as trading opportunities, which turned into nightmares as funding conditions deteriorated even further. Over the crisis, in fact, the investment-grade index CDS-bond basis fell from about. zero to negative 250 basis points.  

Figure 14.6 shows the CDS-bond basis for French and Italian government bonds from January 2006 to October 2021. The basis is defined here as the difference between the five-year CDS spread and the five-year government bond yield spread over Germany. By way of economic backdrop, the European sovereign debt crisis ran from the end of 2009 to 2012, during. which time the finances of both banks and governments in the so-called "peripheral" countries (e.g., Greece, Italy, Portugal, and Spain) came under pressure. Later, in the fall 2018, European Union and Italian government officials squabbled over Italy's proposed budget, which did not comply with existing fiscal rules. The figure shows that the sovereign Italian CDS-bond basis became significantly negative during both of these stressful periods.  

![](4cfbcd8d5e84cf7bf5d08c4db9a76902495d9a832e7bd51b2581e98f3d23c646.jpg)  
FIGURE 14.6 CDS-Bond Basis for French and Italian Sovereign Debt, January 2006 to October 2021.  

As in the financial crisis of 2007-2009, repo lenders became reluctant. to fund Italian government bonds, pushing up their spreads and pushing their CDS-bond basis into negative territory. In fact - though not shown in the figure - spreads of Italian to German government bonds rose to over 600 basis points during the sovereign debt crisis, and to nearly 300 basis points during the budget standoff. By contrast, French government credit exhibited a positive CDS-bond basis during the sovereign debt crisis. French over German spreads did rise to a peak of about 100 basis points at that time, but the bigger story was the difficulty of borrowing and shorting. French government bonds, at least in part because the European Central Bank was aggressively buying European sovereign debt. In any case, the. resulting upward pressure on French government bond prices resulted in a significantly positive CDS-bond basis.20 Finally, more recently, funding. stresses during the COvID pandemic and economic shutdowns drove both Italian and French government CDS-bond bases somewhat negative..  
