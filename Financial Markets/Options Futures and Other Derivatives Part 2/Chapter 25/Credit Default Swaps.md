---
tags:
  - cds
  - credit_default_swaps
  - credit_derivatives
  - credit_event
  - default
  - reference_entity
aliases:
  - CDS
  - Credit Default Swap
key_concepts:
  - Credit default swap (CDS)
  - Credit event
  - Insurance against default risk
  - Notional principal
  - Reference entity
---

# 25.1 CREDIT DEFAULT SWAPS  

The most popular credit derivative is a credit default swap (CDS). This was introduced in Section 7.11. It is a contract that provides insurance against the risk of a default by particular company. The company is known as the reference entity and a default by the company is known as a credit event. The buyer of the insurance obtains the right to sell bonds issued by the company for their face value when a credit event occurs and the seller of the insurance agrees to buy the bonds for their face value when a credit event occurs.1 The total face value of the bonds that can be sold is known as the credit default swap's notional principal.  

The buyer of the CDS makes periodic payments to the seller until the end of the life of. the CDS or until a credit event occurs. In a standard contract, payments are made in. arrears every quarter, but deals where payments are made every month, 6 months, or 12 months or where payments are made in advance occasionally also occur. The settle-. ment in the event of a default usually involves a cash payment..  

An example will help to illustrate how a typical deal is structured. Suppose that two parties enter into a 5-year credit default swap on March 20, 2020. Assume that the notional principal is $\$100$ million and the buyer agrees to pay 90 basis points per annum for protection against default by the reference entity, with payments being made quarterly in arrears.  

The CDS is shown in Figure 25.1. If the reference entity does not default (i.e., there is no credit event), the buyer receives no payoff and pays 22.5 basis points (a quarter of 90 basis points) on $\$100$ million on June 20, 2020, and every quarter thereafter until. March 20, 2025. The amount paid each quarter is. $0.00225\times100,000,000$ , or $\$225,000$ 2 If there is a credit event, a substantial payoff is likely. Suppose that the buyer notifies the seller of a credit event on May 20, 2023 (2 months into the fourth year). If the contract specifies physical settlement, the buyer has the right to sell bonds issued by the reference. entity with a face value of $\$100$ million for $\$100$ million. If, as is now usual, there is cash. settlement, an ISDA-organized auction process is used to determine the mid-market value of the cheapest deliverable bond several days after the credit event. Suppose the auction indicates that the bond is worth. $\$35$ per $\$100$ of face value. The cash payoff would be $\$65$ million.  

Figure 25.1 Credit default swap.  

![](849016e2d4bd4a824e0c1705e5220731398e581432fd75b257195772e16b08b1.jpg)  

The regular payments from the buyer of protection to the seller of protection cease when there is a credit event. However, because these payments are made in arrears, a final accrual payment by the buyer is usually required. In our example, where there is a default on May 20, 2023, the buyer would be required to pay to the seller the amount of the annual payment accrued between March 20, 2023, and May 20, 2023 (approximately $\$150,000$ , but no further payments would be required.  

The total amount paid per year, as a percent of the notional principal, to buy protection (90 basis points in our example) is known as the CDS spread. Several large banks are market makers in the credit default swap market. When quoting on a new 5-year credit default swap on a company, a market maker might bid 250 basis points. and ask 260 basis points. This means that the market maker is prepared to buy. protection by paying 250 basis points per year (i.e., $2.5\%$ of the principal per year) and to sell protection for 260 basis points per year (i.e., $2.6\%$ of the principal per year).  

Many different companies and countries are reference entities for the CDS contracts that trade. As mentioned, payments are usually made quarterly in arrears. Contracts with maturities of 5 years are most popular, but other maturities such as 1, 2, 3, 7, and 10 years are also sometimes used. Usually contracts mature on one of the following standard dates: March 20, June 20, September 20, and December 20. The effect of this is that the actual time to maturity of a contract when it is initiated is close to, but not necessarily the same as, the number of years to maturity that is specified. Suppose you call a dealer on November 18, 2021, to buy 5-year protection on a company. The contract would probably last until December 20, 2026. Your first payment would be due on December 20, 2021, and would equal an amount covering the November 18, 2021, to December 20, 2021, period.' A key aspect of a CDS contract is the definition of a credit event (i.e., a default). Usually a credit event is defined as a failure to make a payment as it becomes due, a restructuring of debt, or a bankruptcy. Restructuring is sometimes excluded in North American contracts, particularly in situations where the yield on the reference entity's debt is high. More information on the CDS market is given in Business Snapshot 25.2.  

# Business Snapshot 25.2 The CDS Market  

In 1998 and 1999, the International Swaps and Derivatives Association (ISDA) developed a standard contract for trading credit default swaps in the over-the-. counter market. Since then the market has grown in popularity. A CDS contract is. like an insurance contract in many ways, but there is one key difference.An insurance contract provides protection against losses on an asset that is owned by the protection buyer. In the case of a CDS, the underlying asset does not have to be owned.  

During the credit turmoil of 2007 and 2008, regulators became very concerned about systemic risk (see Business Snapshot 1.2). They felt that credit default swapse were a source of vulnerability for financial markets. The danger is that a default by one financial institution might lead to big losses by its counterparties in CDS transactions. and further defaults by other financial institutions. Regulatory concerns were fueled. by troubles at insurance giant AIG. This was a big seller of protection on the AAArated tranches created from mortgages (see Business Snapshot 24.1). The protection proved very costly to AIG and the company was bailed out by the U.S. government..  

During 2007 and 2008, trading ceased in many types of credit derivatives, but CDSs continued to trade actively (although the cost of protection increased dramatically).. The advantage of CDSs over some other credit derivatives is that the way they work is. straightforward. Other credit derivatives, such as those created from the securitization of household mortgages (see Chapter 8), lack this transparency..  

It is not uncommon for the volume of CDSs on a company to be greater than its debt. Cash settlement of contracts is then clearly necessary. When Lehman defaulted in September 2008, there was about $\$400$ billion of CDS contracts and $\$155$ billion of Lehman debt outstanding.The cash payout to the buyers of protection (determined by an ISDA auction process) was $91.375\%$ of principal.  

There is one important difference between credit default swaps and the other overthe-counter derivatives that we have considered in this book. The other over-thecounter derivatives depend on interest rates, exchange rates, equity indices, commodity prices, and so on. There is no reason to assume that any one market participant has better information than any other market participant about these variables.  

Credit default swaps spreads depend on the probability that a particular company. will default during a particular period of time.Arguably some market participants have more information to estimate this probability than others.A financial institution that works closely with a particular company by providing advice, making loans, and handling new issues of securities is likely to have more information about. the creditworthiness of the company than another financial institution that has no dealings with the company. Economists refer to this as an asymmetric information problem. Financial institutions emphasize that the decision to buy protection against. the risk of default by a company is normally made by a risk manager and is not. based on any special information that may exist elsewhere in the financial institution. about the company.  

# Credit Default Swaps and Bond Yields  

A CDS can be used to hedge a position in a corporate bond. Suppose that an investor buys a 5-year corporate bond yielding. $7\%$ per year for its face value and at the same.  

time enters into a 5-year CDS to buy protection against the issuer of the bond defaulting. Suppose that the CDS spread is 200 basis points, or. $2\%$ , per annum. The. effect of the CDS is to convert the corporate bond to a risk-free bond (at least approximately). If the bond issuer does not default, the investor earns $5\%$ per year when the CDS spread is netted against the corporate bond yield. If the bond does default, the investor earns. $5\%$ up to the time of the default. Under the terms of the. CDS, the investor is then able to exchange the bond for its face value. This face value can be invested at the risk-free rate for the remainder of the 5 years.  

This shows that the spread of the yield on an. $n$ -year bond issued by a company over the risk-free rate should approximately equal the company's. $n$ -year CDS spread. If it is markedly more than this, an investor can earn more than the risk-free rate by buying the corporate bond and buying protection. If it is markedly less than this, an investor can borrow at less than the risk-free rate by shorting the bond and selling CDS protection.  

The CDS-bond basis is defined as  

The bond yield spread has traditionally been calculated as the excess of the bond yield over the relevant LIBOR/swap rate.  

The arbitrage argument given above suggests that the CDS-bond basis should be close to zero. In fact it tends to be positive during some periods (e.g., pre-2007) and negative during other periods (e.g., the 2007-2009 financial crisis). The sign of the CDS-bond basis since the financial crisis has depended on the reference entity and has been sometimes positive and sometimes negative.  

# The Cheapest-to-Deliver Bond  

As explained in Section 24.3, the recovery rate on a bond is defined as the value of the bond immediately after default as a percent of face value. This means that the payoff from a CDS is $L(1-R)$ , where $L$ is the notional principal and $R$ is the recovery rate.  

Usually a CDS specifies that a number of different bonds can be delivered in the event of a default. The bonds typically have the same seniority, but they may not sell for the same percentage of face value immediately after a default.4 This gives the holder of a CDS a cheapest-to-deliver bond option. As already mentioned, an auction process, organized by ISDA, is usually used to determine the value of the cheapest-to-deliver bond and, therefore, the payoff to the buyer of protection.  
