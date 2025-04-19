---
cssclasses:
  - academia
title: Securitized Banking and the Run On Repo
tags:
  - bank_solvency
  - credit_spreads
  - financial_crisis
  - repo_market
  - securitized_banking
aliases:
  - Repurchase Agreements
  - Run on Repo
  - Securitized Banking
key_concepts:
  - Bank solvency concerns
  - Credit spread correlation
  - Run on repo market
  - Securitization and finance
  - Systemic bank run
---

# Securitized Banking and the Run On Repo

## 1. Introduction

Abstract

The panic of 2007–2008 was a run on the sale and repurchase market (the [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] market),  which is a very large,  short-term market that provides financing for a wide range of securitization activities and financial institutions. [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|Repo]] transactions are collateralized,  frequently with securitized bonds. We refer to the combination of securitization plus [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] finance as ''securitized banking'' and argue that these activities were at the nexus of the crisis. We use a novel data set that includes credit spreads for hundreds of securitized bonds to trace the path of the crisis from subprime-housing related assets into markets that had no connection to housing. We find that changes in the LIB-OIS spread,  a proxy for counterparty risk,  were strongly correlated with changes in credit spreads and [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] rates for securitized bonds. These changes implied higher uncertainty about bank solvency and lower values for [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] collateral. Concerns about the [[Financial Markets and Institutions/III. Liquidity of Assets/Class 5- Private Information,    Liquidity,    and Securitization/Class 5- Private Information,    Liquidity,    and Securitization.md|liquidity]] of markets for the bonds used as collateral led to increases in [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] haircuts,  that is the amount of collateral required for any given transaction. With declining asset values and increasing haircuts,  the US banking system was effectively insolvent for the first time since the Great Depression.

The 2007–2008 financial crisis was a system wide bank run. What makes this bank run special is that it did not occur in the traditional-banking system,  but instead took place in the ''securitized-banking'' system. A traditional-banking run is driven by the withdrawal of deposits,  a securitized-banking run is driven by the withdrawal of repurchase ([[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]]) agreements. Hence,  we describe the crisis as a run on [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]]. The purpose of this paper is to propose a mechanism for this new kind of bank run and to provide supporting evidence for this mechanism through analysis of two novel data sets.

Traditional banking is the business of making and holding loans,  with insured demand deposits as the main source of funds. Securitized banking is the business of packaging and reselling loans,  with [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] agreements as the main source of funds. Securitized-banking activities were central to the operations of firms formerly known as investment banks (e.g. Bear Stearns,  Lehman Brothers,  Morgan Stanley,  and Merrill Lynch),  but they also play a role at commercial banks,  as a supplement to traditional-banking activities of firms such as Citigroup,  J.P. Morgan,  and Bank of America. 1

We argue that the financial crisis that began in August 2007 was a systemic event,  to meaning that the banking sector became insolvent,  in the sense that it could not pay off its debt. What happened is analogous to the banking panics of the 19 th century in which depositors en masse went to their banks seeking to withdraw cash in exchange for demand and savings deposits. The banking system could not honor these demands because the cash had been lent out and the loans were illiquid so they suspended convertibility and relied on clearinghouses to issue certificates as makeshift currency. 2 Evidence of the insolvency of the banking system (i.e.,  that the system cannot pay off the demand deposits,  as demanded by depositors) in these earlier episodes is the discount on these certificates. We argue that the current crisis is similar in that contagion led to withdrawals in the form of unprecedented high [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] haircuts and even the cessation of [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] lending on many forms of collateral. Evidence of insolvency in 2008 is the [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] or forced rescue of several large firms,  with other (even larger) firms requiring government support to stay in business.

To perform our analysis,  we use two novel data sets,  one with information on 392 securitized bonds and related assets,  including many classes of asset-backed securities

(ABSs),  collateralized debt obligations (CDOs),  and credit default swaps (CDSs) and the other [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] rates and [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] haircuts. 3 Using these data,  we are able to provide a new perspective on the contagion in this crisis. In our exposition,  we use this term ''contagion'' specifically to mean the spread of the crisis from subprime housing assets to nonsubprime assets that have no direct connection to the housing market. In fact,  we argue that to explain the crisis requires explaining why the spreads on non-subprime related asset classes rose dramatically.

To provide background for our analysis,  we illustrate the differences between traditional banking and securitized banking in Figs. 1 and 2. Fig. 1 provides the classic picture of the financial intermediation of mortgages by the traditional-banking system. In Step A,  depositors transfer money to the bank,  in return for a checking or savings account from which withdrawals can be made at any time. In Step B,  the bank loans these funds to a borrower,  who promises to repay through a mortgage on the property. The bank then holds this mortgage on its balance sheet,  along with other non-mortgage loans made to retail and commercial borrowers.

1. The clearinghouse private money was a claim on the coalition of banks,  not a liability of any individual bank. By broadening the backing for the claim,  the clearinghouse made the claim safer,  a kind of insurance. Gorton (1985) and Gorton and Mullineaux (1987) discuss the clearinghouse response to panics. Also,  see Gorton and Huang (2006).
1. This paper uses many terms and abbreviations that are atypical or new to the academic literature. Beginning in Section 2,  the first appearance of these terms is given in bold type,  and definitions of bolded terms are given in Appendix A.

Fig. 1. Traditional banking.

Balance sheet,  along with other non-mortgage loans made to retail and commercial borrowers.

Traditional-banking runs,  for the most part,  were ended in United States after the Great Depression,  owing to a combination of influences,  including enhanced dis count window lending by the Federal Reserve and the introduction of deposit insurance. Deposit insurance removes any incentive for insured depositors to withdraw their funds,  but larger insured banks cannot offer insured depositors to non retail depositors (including sovereign wealth funds,  mutual funds,  and cash-rich companies) One solution to this problem is the securitized-banking system illustrated in Fig. 2,  which takes large deposits from investors (Step 1) and then intermediates these deposits to mortgage borrowers (Steps 2 and 3) and other debtors,  Step 1 in Fig. 2 is an analogue to Step A from Fig. 1,  with one important difference. In the traditional-banking sys-. Tem shown in Fig. 1,  the deposits are insured by the government. To achieve similar protection in Step 1 of Fig. 2,  the investor receives collateral from the bank. In practice,  this deposit-collateral transaction takes the form of a [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] agreement: the investor buys some asset (i.e.,  the collateral) from the bank for $sx$ and the bank agrees to repurchase the same asset some time later (perhaps the next day) for $\$Y.$ The percentage $(Y-X)/X$ is the repo rate and is analogous to the interest rate on a bank deposit

 ![500](https://storage.simpletex.cn/view/fmSeg2dnFdVakc1f1gTNM8hrCknrw38z6)

Fig. 2. Securitized banking

Typically. The total amount of the deposit will be some amount less than the value of the underlying asset,  with the difference called a haircut. For example,  if an asset has a market value of $\$100$ and a bank sells it for S 80 with an agreement to repurchase it for S 88,          then we would say that the repo rate is $10\%\left[=(88-80)/80\right]$ and the haircut is $20\%$ 20% $20\%(100-80/100)$ .If the bank defaults on the promise to repurchase the collateral,  then the investor has the right to terminate the agreement and keep or sell the collateral. Turning next to the lower right corner of Fig. 2,  we show how the second part of the intermediation differs from traditional banking. In Fig. 1,  the bank did the work of underwriting the loan itself. In Fig. 2,  the bank outsources this function to a direct lender. Such lenders grew to prominence in the most recent housing boom,  with a specialization of underwriting loans to be held for only a short time before being sold to banks. Much has been written about potential conflicts in this separation of the loan decision from the source of finance,  but that is not our topic here. In principle,  there is no reason that this separation must necessarily lead to poor underwriting and in any event such problems do not imply anything about contagion or systemic events.

Another key component of securitized banking is in the securitization itself: the intermediation activities that transfer most of the mortgage loans to outside investors in Step 4. We discuss this step in detail in Section 2. For our purposes here,  the key idea is that the outputs of this securitization are often used as collateral in Step 1,  so that securitized banking is a cycle that requires all steps to keep running. In this paper,  we show how this cycle broke down in the crisis. Fig. 3 summarizes the relations between the main elements of traditional and securitized banking. The familiar elements of traditional banking are reserves,  deposit insurance,  interest rates on deposits,  and the holding of loans on balance sheet. Bank solvency is promoted by requiring a fraction of deposits to be held in reserve,  and in emergencies these reserves can be replenished by borrowing from the central bank. The analogue in securitized banking is the repo haircut,  which forces banks to keep some fraction of their assets in reserve when they borrow money through repo markets. Deposit insurance is a promise made by the government to pay depositors in the event of default. The analogue in securitized banking is collateral. A bank in need of cash can raise deposit rates to the paper came due; see Kacperczyk and Schnabl (2010). Also important was the run on [[A Primer on Money Market Mutual Funds|money market funds]] following the failure of Lehman Brothers,  as explained by The Investment Company Institute (2009）. In sum mary,  all short-term debt markets were vulnerable during the crisis. In this paper,  we focus on the repo market because of its large size. Also,  repo is secured by collateral that can be “"rehypothecated,  " which means that a deposi tor of cash in the bank takes physical possession of bond collateral and then can reuse that collateral. So,  the collateral has a money multiplier. When haircuts rise,  the money multiplier works in reverse,  causing a massive deleveraging process. This does not happen for unsecurec short-term debt. This paper and those mentioned above are part of a rapidly growing literature that tries to empirically show what happened during the crisis. Aside from runs the financial crisis is complicated in many other dimensions Studies have been made of the breakdown of various arbitrage relations,  perhaps due to counterparty risk and attendant funding problems,  e.g.,  Coffey,  Hrung,  and Sarkar (2009). Gorton (2010),  Baba and Packer (2009).,  Stanton and Wallace (2009),  Fontana (2009),  and Fender and Scheicher (2009). Other research looks at counterparty risk and liquidity,  e.g,  Arora,  Gandhi,  and Longstaff (2009),  Schwarz (2009) and Singh and Aitken (2009). Other papers discuss the international dimensions of the crisis. And compare the crisis to previous crises,  e.g,  Eichengreen,  Mody,  Nedeljkovic,  and Sarno (2009) and Reinhart and Rogoff (2008) Ivashina and Scharfstein (2008) look at bank lending during the crisis. The real effects of the crisis are also important to consider,  as do e.g.,  Almeida,  Campello,  and Laranjeira (2009) and Campello Giabona,  Graham,  and Harvey (2009). Many other papers look at subprime mortgages,  rating agencies,  auction rate securities,  short selling prohibitions,  and so on,  so the above list is far from being complete. S The remainder of the paper is organized as follows.

In Section 2,  we provide institutional background for our analysis,  with a discussion of the growth of securitized banking,  using subprime mortgages as the case study We use this case study to provide more detail for Step 4 in Fig. 2 and to explain the mechanics of securitization and the repo market In Section 3,  we introduce and explain the two main

banking system to insolvency. Take as a benchmark a repo market size of,  for example,  $\$10$ trillion. With zero haircuts,          this is the amount of financing that banks can achieve in the repo markets. When the weighted-average haircut reaches,          say. $20\%$ then banks have a shortage of 52 trillion. In the crisis,  some of this amount was raised early on by issuing new securities. But,  this fell far short of what was needed. Furthermore,  selling the underlying collateral drives asset prices down,  which then reinforces the cycle: lower prices,  less collateral,  more concerns about solvency,  and ever increasing haircuts In addition to repo,  other short-term debt experienced

State variables used in the paper: the ABX index—which proxies for fundamentals in the subprime mortgage market and the LIB Is,  which is the spread between the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] (London Inter Bank Offered Rate,  for unsecured interbank borrowing) and the rate on an overnight interest swap (OlS) a proxy for the risk-free rate. In our analysis the LIB-OIS spread acts primarily as a proxy for counterparty risk in the banking system. We then plot runs. There were runs,  in particular,  on asset-backed [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]] programs and structured investment vehicles. Papers that consider the runs on asset-backed [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]] programs during the crisis include Covitz,  Liang,  and Suarez (2009) and Carey,  Correa,  and Kotter (2009). Aside from asset-backed [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]],  . The [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]] of financial firms,  the predominant issuers of corporate short-term [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]] also saw withdrawals when investors refused to reinvest as these state variables for 2007 and 2008 and review the timeline for the crisis.

 ![500](https://storage.simpletex.cn/view/fCnORz7FEwpnX8SXKGODK6Xyw5cCGZpE4)

Fig. 4. The repo-haircut index. The repo-haircut index is the equally weighted average haircut for all nine asset classes included in Table 2,  Panel D.

The ABX data show that the deterioration of the subprime market began in early 2007. As is now well known,  this deterioration had a direct impact on banks,  which had many of these secur itized assets and pre-securitized mortgages on their balance sheets. This real deterioration in bank balance sheets became apparent in the interbank markets in mid2007,  as evidenced by an upward spike in the LIB-OIS in August. This state variable remained in a historically high but narrow range until September 2008,  when the events at Fannie Mae (Federal National Mortgage Association) Freddie Mac (Federal Home Loan Mortgage Corporation) Lehman,  and AIG (American International Group Inc.) led to a rapid deterioration in interbank markets and increase in the LIB-OIS spread that persisted until the end of 2008. We posit that the increased risk at banks had several securitized assets and related derivatives. These increased spreads are equivalent to a price decrease,  which represents a fall in the value of collateral used in repo transactions. Then,  as lenders began to fear for the stability of the banks and the possibility that they might need to seize and sel collateral,  the borrowers were forced to raise repo rates and haircuts. Both of these increases occurred in the crisis. In Sections 5.3 and 5.4,  we find that these increases were correlated with changes in the LIB-OIS (for repo rates) and changes in the (expected future) volatility of the underlying collateral (for repo haircuts),  consistent with the model of Dang. Gorton,  and Holmstrom (2011). It is the rise in haircuts that constitutes the run on repo. An increase in a haircut is tantamount to a withdrawal from the bank forcing deleveraging on a large scale. Section 5.5 uses data from Schwarz (2009) to confirm that the LIB-OIS relations found for credit spreads and repo rates are primarily driven by counterparty risk Section 6 reviews our arguments and concludes the paper. Appendix A defines some of the paper's terminol ogy that could be unfamiliar for some readers and also includes descriptions for each of the asset classes of securitized bonds that are used in our empirical analysis. Appendix B gives more detail on the data construction.

Interrelated effects,  all of which centered on the securitized assets used as collateral in the repo market. We provide evidence for these effects,  using a data set with information on securitized bonds,  credit default swaps,  and other assets used in repo transactions. These data were created by large financial institutions and are used for trading and portfolio valuation by a wide range of market participants. Section 3 provides summary statistics on these data and illustrates how some of these assets co-moved with the ABX and the LIB-OIS Section 5 gives the main empirical results of the paper.

### 2. Institutional background

This section discusses the main institutional features that intersected in the crisis: the subprime mortgage market (Section 2.1),  securitization (Section 2.2). And repo finance (Section 2.3).

Without a structural model of repo markets,  we are only able to talk about co-movement of spreads on various assets,  and thus we use the language of correlation instead of causation in our empirical analysis. Section 5.1 explains our methodology and presents results for a few representative asset classes. Section 5.2 uses the full set of asset classes to demonstrate that it was the interbank markets (LIB-OIS) and not the subprime housing market (ABX) that was correlated with increases in the spreads on non-subprime

### 2.1. The subprime mortgage market

The opportunity for home ownership for all Americans has been a long-standing national goal. This goal was behind the origins of modern housing finance during the Great Depression with the New Deal's National Housing Act of 1934 (see,  e.g.,  Fishback,  Horrace and Kantor 2001). For example,  as President George W. Bush put it in 2004: "Not enough minorities own their own homes. One thing I've done is I've called on private sector mortgage banks and banks to be more aggressive about lending to firsttime home buyers."6 The private sector responded The subprime mortgage market is a financial innovation,  aimed at providing housing finance to (disproportionately poor and minority) people with some combination of spotty credit histories,  a lack of income documentation or no money for a down payment. Historically,  this group was perceived by banks as too risky to qualify for the usual mortgage products,  for example,  a 30-year fixed rate mortgage. As explained by Gorton (2010),  the innovation was to structure the mortgage to effectively make the maturity two or three years. This was accomplished with a fixed initial-period interest rate,  but then at the reset date having the rate rise significantly. Essentially requiring the borrower to refinance the mortgage. With rising home prices,  borrowers would build equity in their homes and would be able to refinance The innovation was a success,  if measured in terms of

 ![500](https://storage.simpletex.cn/view/fkWp0GxCRAouGtWgGNSUgixHWMg5xEkgq)

Fig. 5. Issuance in US capital markets (billions of dollars). Data are from US Department of Treasury,  federal agencies,  Thomson Financial,  Inside MBS & ABS,  and Bloomberg

![5_image_0.png](5_image_0.png)

US Department of Treasury,  federal agencies,  Thomson Financial,  Inside MBS & ABS,  and Bloomberg.

Non-mortgage instruments,  the asset-backed securitization market is very large,  exceeding the issuance of all corporate debt in the US in 2004,  2005,  and 2006. Overall,  the figure shows that securitization is a very large,  significant,  part of US capital markets.

Securitization spawned a large number of new financial instruments and new usages for old instruments.

Among these are the asset-backed security (ABS),  credit default swap collateralized debt obligation (CDO),  and collateralized loan obligation (CLO). 9 Credit default swaps are derivative contracts under which one party insures another party against a loss due to default with reference to a specific corporate entity,  asset-backed security,  or index. For our purposes,  the CDS spread,  which is the fixed coupon paid by the party buying the protection,  is an indication of the risk premium with regard to the specified corporate entity. CDOs are securitizations of [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]] or asset-backed or mortgage-backed securities. Close are securitizations of loans to corporations. CDOs are relevant here for two reasons.

First,  the underlying CDO portfolios contained tranches of subprime securitizations,  making their value sensitive to subprime risk. And second,  like asset-backed securities generally,  they too depend on the repo market,  at least to some extent.

Fig. 6 shows how the pieces of the securitization process fit together. This figure is an expansion of Step 4 from the securitized-banking diagram shown in Fig. 2,  and also includes Step 1 from Fig. 2,  while omitting Steps 2 and 3. The starting point is a bank with a set of loans in its inventory. The bank does not have the resources to keep all of these loans on its balance sheet. In securitized banking the profit comes from the intermediation,  not from holding the loans. In Step 4,  these loans are transferred to the SPV and placed in one big pool. This pool is the assets of the SPV,  which builds a capital structure on those assets using different layers,  each called a tranche. The idea here is that the first losses on the pool are allocated to the equity layer at the bottom,  with additional losses moving up the capital structure,  by seniority,  until they reach the AAA tranche at the top. These layers and rating are represented by the asset-backed securities issued by the SPV. Because the assets backing these securities are mortgages,  the ABS goes by the specialized name of residential mortgage-backed securities in this case.

The ABS could be sold directly to investors (Step 5) or could instead be securitized in a CDO (Step 6). A CDO has a tranche structure similar to an ABS. The tranches of the CDO may be sold directly to investors (Step 7),  or resecuritized into further levels of CDOs (not shown in figure).

In some cases,  the ABS or CDO tranches could return to the balance sheets of the banks,  where they could be used as collateral in the repo transaction of Step 1.

With each level of securitization,  the SPV often combines many lower rated (BBB,  BBB-) tranches into a new vehicle that has mostly AAA and AA-rated tranches,  a process that relies on well-behaved default models. This slicing and recombining is driven by a strong demand for highly rated securities for use as investments and collateral: essentially,  there is not enough AAA debt in the world to satisfy demand,  so the banking system set out to manufacture the supply. As emphasized by Gorton (2010),  it can be difficult to pierce the veil of a CDO and learn exactly what lies behind each tranche. This opacity was a fundamental part of precrisis securitization and was not limited to subprime-based assets. 10

## 2.3. The Repo Market

A repurchase agreement (or repo) is a financial contract used by market participants as a financing method to meet short-term liquidity needs. 11 A repurchase agreement is a two-part transaction. The first part is the transfer of specified securities by one party,  the bank or borrower,  to another party,  the depositor or lender,  in exchange for cash the depositor holds the bond,  and the bank holds the cash. 12 The second part of the transaction consists of a contemporaneous agreement by the bank to repurchase the securities at the original price,  plus an agreed upon additional amount on a specified future date. It is important to note that repurchase agreements,  like derivatives,  do not end up in [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] court if one party defaults. The nondefaulting party has the option to simply walk away from the transaction,  keeping either the cash or the bonds. 13 In the last 30 years,  the demand for repo has grown enormously. The main reason is the rapid growth of money under management by institutional investors,  pension funds,  and mutual funds. In addition,  demand for repo has come from states,  municipalities,  and nonfinancial firms. These entities hold cash for various reasons but would like to have a safe investment,  which earns interest,  while retaining flexibility to use the cash,  in short,  a demand deposit-like product. Insured checking accounts were imperfect substitutes for repo finance because of limitations on deposit insurance,  differences in regulatory regimes applied to depository and repo finance (e.g.,  capital requirements),  and other factors. In the last three decades these entities have grown in size and become an important feature of the financial landscape.

For example,  according to the Bank for International Settlements (2007,  p. 1,  footnote 1): ''In 2003,  total world assets of commercial banks amounted to USD 49 trillion,  compared to USD 47 trillion of assets under management by institutional investors.''

Mutual funds,  including in particular Money Market Mutual funds (MMMFs),  are important users of repo. MMMFs held $552 billion in [[Class Note 12 Part 2 Repos|repurchase agreements]] in December 2008 (Report of the Money Market Working Group,  2009). These data are for MMMFs only; there are no data covering all other types of mutual funds. The importance of [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] for mutual funds motivated eight of the larger fund companies to send a letter (see Letter June 11,  2010) to House Financial Senior Committee Chairman Barney Frank and Senate Banking,  Housing and Urban Affairs Committee Chairman Christopher Dodd expressing concern that part of the proposed financial reform legislation ''would result in significant unintended consequences for the capital markets. The provision would likely curtail the desire of market participants to invest in [[Class Note 12 Part 2 Repos|repurchase agreements]] (''repos'').''

Corporate treasurers and state and local governments started to expand their use of [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] in the 1960 s and 1970 s,  even though [[Class Note 12 Part 2 Repos|repurchase agreements]] were not standardized until the late 1980 s. Stigum and Crescenzi

(2007,  p. 536) note that corporate treasurers started to use [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] in the 1960 s: ''By the mid-1970 s,  most corporations,  including many that a few years earlier did not know what [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] was,  had amended their bylaws to permit them to invest in [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]].'' Corporations use [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] to manage their cash. The Association for Financial Professionals (AFT) in its (2006) annual [[Financial Markets and Institutions/III. Liquidity of Assets/Class 5- Private Information,    Liquidity,    and Securitization/Class 5- Private Information,    Liquidity,    and Securitization.md|liquidity]] survey reports that 60% of its 342 respondents allow [[Class Note 12 Part 2 Repos|repurchase agreements]] for their cash management. Of those,  57% are allowed to use 50% or more of their cash in [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]],  although in practice the allocation to [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] is much less (Association for Financial Professionalism,  2006).

These nonfinancial firms also have been increasing the amounts of cash that their treasury departments hold (in part,  perhaps,  because of the increasing availability of [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]]). Bates,  Kahle,  and Stulz (2008,  p. 1) point out a secular trend that ''the average cash-to-assets ratio for US industrial firms more than doubles between 1980 and 2006.'' This ratio more than doubled from 10.5% in 1980 to 23.2% in 2006. In particular,  the average firm can pay back all its debt obligations with its cash holdings. Foley,  Hartzell,  Titman and Twite (2006,  p. 1) also study this rise in cash holding by US firms: ''At the end of fiscal 2004,  cash represented 10.5% of the aggregate assets of all Compustat firms. While this is a large percentage,  for many firms,  the dollar value of cash holdings was also large. For example,  at the end of 2004 cash holdings of Microsoft,  General Motors,  Ford,  General Electric,  Exxon Mobil,  and Pfizer were,  respectively,  $60.6 billion,          $36.0 billion,  $33.4 billion,          $23.2 billion,  $23.1 billion,          and $19.9 billion.'' Also,  see Pinkowitz,  Stulz,  and Williamson (2006).

![8_image_0.png](8_image_0.png)

[[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|Repo]] amounts done by the 19 primary-dealer banks. According to Fed data,  primary dealers reported financing $4.5 trillion in fixed income securities with repo as of March 4,          2008. But,          this covers only a fraction of the repo market in the US. 15 The US Bond Market Association (now known as the Securities Industry and Financial Markets Association) conducted a survey of repo and securities lending in 2005,          estimating that the total exceeded $5.21 trillion.

One way to estimate the total size of the US [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] market is to base it on triparty [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] data. Triparty [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] peaked at $2.8 trillion (see Task Force on Tri-Party Repo Infrastructure,          2009). Market participants anecdotally provide a range of views as to what fraction triparty repo is of the overall market. This leads to an estimate that the US repo market is likely to be roughly the same size (or larger) than the total assets in the US banking system of $10 trillion. Using a different method,  Singh and Aitken (2010) also find a [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] market precrisis peak of about $10 trillion. Finally,          using still a third method,          Bank for International Settlements economists Peter Hordahl and ¨ Michael King (2008 p. 37) report that repo markets have doubled in size since 2002,          ''with gross amounts outstanding at year-end 2007 of roughly $10 trillion in each of the US and Euro markets,  and another $1 trillion in the UK repo market.'' Finally,  the European repo market,  widely viewed as being much smaller than the US market was 4.87 trillion Euros in June 2009,  having peaked at 6.78 trillion Euros in June 2007,  according to the International Capital Markets Association (ICMA)

European Repo Market Survey (2010). According to the figures published in the ICMA European Repo Market Survey of June 2009,  the repo market globally grew at an average rate of 19% per annum between 2001 and 2007. While the available evidence is very suggestive that the repo market is very large,  it is impossible to say exactly how large.

Another way to get a sense of the growth in the securitized-banking system is to compare the total assets in the commercial-banking system to the total assets in the dealer (investment) banks,  because the latter rely more heavily on repo finance than the former. For this purpose,  Federal Flow of Funds data are available,  shown in Fig. 7. The figure shows that the ratio of broker–dealer total assets to commercial banks' total assets has grown from less than 5% in 1990 to a peak near 25% in 2007.

Some evidence on the use of repo in dealer banks comes from King (2008) and Hordahl and King (2008) ¨ ; the latter paper states that ''the (former) top US investment banks funded roughly half of their assets using repo markets,  with additional exposure due to off-balancesheet financing of their customers'' (p. 39). Some details on dealer use of repo are shown in Table 1 and are consistent this quotation and with Lehman Brothers [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] report (Report of Anton R. Valukas,  2010,  p. 43) that: ''Lehman funded itself through the short-term repo markets and had to borrow tens or hundreds of

Fig. 7. Ratio of broker–dealers' total assets to banks' total assets. Data are from Federal Flow of Funds.

Billions of dollars in those markets each day from counterparties to be able to open for business. Confidence was critical. The moment that repo counterparties were to lose confidence in Lehman and decline to roll over its daily funding,  Lehman would be unable to fund itself and continue to operate.''

Notably,  commercial banks did not rely heavily on repo. The amount of securities sold under repo as a percentage of total assets from April 1,  2008 to February 29,  2009 was 63 basis points (mean) and the median was 2.7% (Afonso,  Kovner,  and Schoar 2010). The crisis was centered on the dealer banks. In fact,  commercial banks' balance sheets grew during the crisis (He,  Khang,  and Krishnamurthy 2010).

For every repo,  the other side of the transaction is a reverse repo. This raises the issue of double counting of both repo and reverse repo. The issue concerns whether the relevant number is gross repo or net repo for financial firms. For example,  a dealer bank that lent money via repo to a hedge fund (which provides the dealer bank with a bond as collateral) and then borrowed against that bond from another dealer bank would have a net of zero (ignoring the haircuts). But,  in a run the depositors want their cash bank and the dealer bank cannot instantaneously get the cash back from the hedge fund. (This would be possible in a clearinghouse arrangement.) So,  it would seem that gross repo borrowing is the relevant number. It is not known how much of the demand for repo comes from outside the banking system,  i.e.,  are most of the depositor/lender end users nonbanks? The extent of this issue is unclear as there are no data on the extent of involvement in repo from nonfinancial firms and only financial firms have been counted,  estimated,  or surveyed. At least anecdotally,  many nonfinancial firms' treasury departments (e.g.,  Westinghouse,  IBM,  Microsoft) invest in repo as do institutional investors.

## 3. State Variables: The Abx Indices And The Lib-Ois Spread

This section introduces the key state variables of the paper. Section 3.1 discusses the ABX indices,  which are proxies for fundamentals of the subprime market.

Table 1 Broker–dealer repo financing (billions of dollars).

Merrill Lynch (ML) did not list Financial instruments owned. Instead,  ML listed Trading assets,  Investment securities,  and Securities received as collateral.

In the column ML,  all three asset categories were used. In the column marked ML**,  only trading assets and investment securities are included. In the case of ML**,  only Trading assets are used. Data are from Company 10-Qs. See King (2008) and Singh and Aitken (2009).

Section 3.2 discusses the LIB-OIS spread,  which is a proxy for fears about bank solvency. In Section 3.3,  we plot these two state variables against the time line of the crisis.

## 3.1. Subprime Fundamentals And The Abx Indices

With respect to the housing market,  the fundamentals essentially are housing prices and changes in housing prices. Subprime mortgages are very sensitive to housing prices,  as shown by Gorton (2010). How was information about the fundamentals in the subprime mortgage market revealed to market participants? No secondary markets for the securities are related to subprime (mortgagebacked securities,  collateralized debt obligations). But,  in the beginning of 2006,  the growth in the subprime securitization market led to the creation of several subprime-related indices. Specifically,  dealer banks launched the ABX. HE (ABX) index in January 2006. The ABX index is a credit derivative that references 20 equally weighted subprime RMBS tranches. Subindices are linked to a basket of subprime bonds with specific ratings: AAA,  AA,

A,  BBB and BBB-. Each subindex references the 20 subprime RMBS bonds with the rating level of the subindex.

Every six months the indices are reconstituted based on a preidentified set of rules,  and a new vintage of the index and subindices are issued. 16 Gorton (2009) argues that the introduction of the ABX

Indices is important because it opened a (relatively) liquid,  publicly observable market that priced subprime risk. The other subprime-related instruments,  RMBSs and CDOs,  did not trade in publicly observable markets. In fact,  securitized products generally have no secondary trading that is publicly visible. Thus,  for our purposes the ABX indices are important because of the information revelation about the value of subprime mortgages,  which in turn depends on house prices. Keep in mind that house

16 The index is overseen by Markit Partners. The dealers provide Markit Partners with daily and monthly marks. See http://www.markit.

Com/information/products/abx. Html.

Price indices,  such as the Standard and Poor's (S&P) CaseShiller Indices,  are calculated with a two-month lag. 17 Furthermore,  house price indices are not directly relevant because of the complicated structure of subprime securitizations.

In this paper,  we focus on the BBB ABX tranche of the first vintage of the ABX in 2006,  which is representative of the riskier levels of subprime securitization. We refer to this tranche of the 2006-1 issue simply as ABX. In the next subsection,  we show how the ABX evolved during the crisis and compare this evolution with deterioration in the interbank markets.

## 3.2. The Interbank Market And The Lib-Ois Spread

Our proxy for the state of the interbank market and,  in particular,  the repo market is the spread between threemonth [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and the overnight index swap rate,  which we call the LIB-OIS spread. [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] is the rate paid on unsecured interbank loans,  cash loans in which the borrower receives an agreed amount of money either at call or for a given period of time,  at an agreed interest rate. These loans are not traded. Basically,  a cash-rich bank deposits money with a cash-poor bank for a period of time. The rate on such a deposit is LIBOR,  which is the interest rate at which banks are willing to lend cash to other financial institutions in size. The British Bankers' Association (BBA) London interbank offered rate fixings are calculated by taking the average of a survey of financial institutions operating in the London interbank market. 18 The BBA publishes daily fixings for LIBOR

Deposits of maturities up to a year.

From the three-month [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] rate we subtract a measure of interest rate expectations over the same term.

This rate is the overnight index swap (Is) rate. The

![10_image_0.png](10_image_0.png)

Fig. 8. Asset-backed security index versus LIB-OIS (spread between the London Interbank Offered Rate and the rate on an overnight index swap). ABX is the 2006-1 BBB tranche.

Overnight index swap is a fixed-to-floating interest rate swap that ties the floating leg of the contract to a daily overnight reference rate (here,  the [[A Guide to the Front End and Basis Swap Markets#Federal Funds Market|Fed Funds Rate]] ). 19 The floating rate of the swap is equal to the geometric average of the overnight index over every day of the payment period. When an Is matures,  the counterparties exchange the difference between the fixed rate and the average effective fed-funds rate over the time period covered by the swap,  settling the trade on a net basis. The fixed quote on an Is should represent the expected average of the overnight target rate over the term of the agreement. As with swaps generally,  there is no exchange of principal and only the net difference in interest rates (times the notional amount) is paid at maturity,  so Is

Contracts have little credit-risk exposure. 20 If there is no credit risk and no transactions costs,  then the interest rate on an interbank loan should equal the overnight index swap (the expected [[A Guide to the Front End and Basis Swap Markets#Federal Funds Market|Fed Funds]] cost of the loan). To see this,  consider an example: Bank 1 loans Bank 2 $10 million for three months. Bank 1 funds the loan by borrowing $10 million each day in the overnight [[A Guide to the Front End and Basis Swap Markets#Federal Funds Market]]. Further,  Bank 1 hedges the interest rate risk by entering into an overnight index swap under which Bank 1 agrees to pay a counterparty the difference between the contracted fixed rate and the overnight [[A Guide to the Front End and Basis Swap Markets#Federal Funds Market|Fed Funds Rate]] over the next three months. In the past arbitrage has kept this difference below 10 bps.

If the spread between [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and the Is widens,  an apparent arbitrage opportunity arises. But,  at some times,  banks are not taking advantage of it. Why? The answer is

19 There are equivalent swaps in other currencies,  which reference other rates. 20 In addition,  credit risk in swaps is managed by requiring that collateral be posted to the party for which the swap becomes a liability.

That there is counterparty risk,  that is,  Bank 1 worries that Bank 2 will default and so there is a premium between the expected interest rates over the period,  the Is rate,  and the rate on the loan,  LIBOR. We refer to the spread between the three-month [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and the three-month Is as LIB-OIS.

Ideally,  we would like to use the LIB-OIS as a pure measure of counterparty risk in the banking system. Schwarz (2009) shows that this interpretation is too narrow and that the LIB-OIS reflects both counterparty risk and market-liquidity risk. In Section 5.5,  we use the Schwarz data to divide the LIB-OIS into counterparty and liquidity risk,  and we find that the counterparty component drives the vast majority of our results,  and the liquidity component has no explanatory power. Thus,  in discussing the empirical results,  we refer to LIB-OIS as a proxy for counterparty risk,  with the evidence for this interpretation given in Section 5.5.

## 3.3. A Time Number Line For The Crisis

In Fig. 8,  we show the ABX and LIB-OIS spreads. For the ABX,  we use the 2006-1 BBB tranche in all cases. The time period is from January 1,  2007 through December 25,  2008. During the full period,  the ABX makes a steady rise,  whereas the LIB-OIS shows two jumps,  in August 2007 and September 2008. These months are not particularly special for the ABX. Furthermore,  the LIB-OIS recovers some ground at the end of 2008,  while the ABX spread continues to grow. It is difficult to explain why the LIB-OIS spikes occur at these times,  and we are not attempting an explanation here. Instead,  these figures are intended only to illustrate that the spikes are not concurrent with major changes in the ABX.

The first six months of 2007 were ordinary for the vast majority of fixed-income assets. It is only when we look at subprime-specific markets that we begin to see the seeds of the crisis. The ABX begins the year at 153 basis points

(bps),  which is close to its historical average since the series began in January 2006,  after a first year with almost no volatility. The first signs of trouble appear at the end of January,  and by March 1 the spread was 552 bps. The next sustained rise came in June,  reaching 669 bps by the end of that month. In contrast,  the LIB-OIS hardly moved during the period,  steady at around 8 bps.

Of particular interest is the summer of 2007,  when the LIB-OIS first signals danger in the interbank market. From its steady starting value of 8 bps,  LIB-OIS grows to 13 bps on July 26,  before exploding past its historical record to 40 bps on August 9 and to new milestones in the weeks ahead before peaking at 96 bps on September 10. This period also marked the initial shock for a wide swath of the securitization markets,  particularly in high-grade tranches commonly used as collateral in the repo market. The ABX is also rising during this period,  but its most significant move begins earlier and visually appears to lead the LIB-OIS. From its starting value of 669 bps at the end of June,  the spread rises to 1,  738 bps by the end of July,  before any significant move in the LIB-OIS.

The ABX spread continued its steady rise in the first half of 2008,  going from 3,  812 to 6,  721 bps over the sixmonth period from January 1 to June 30. Once again,  the LIB-OIS is behaving differently from the ABX,  with trading in a band between 30 and 90 bps. The reduction in the LIB-OIS in January is followed by increases through February and March,  coincident—or perhaps causal—of the trouble at Bear Stearns,  which reached its climax with its announced sale to JP Morgan on March 16.

In the second half of 2008,  the full force of the panic hit asset markets,  financial institutions,  and the real economy. The ABX spread continued its steady rise,  with prices of pennies on the dollar and spreads near 9,  000 bps by the end of the period. The LIB-OIS,  after a period of stability in the early summer,  began to rise in early September,  and then passed the 100 bps threshold for the first time on the September 15 [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] filing of Lehman Brothers. The subsequent weeks heralded near collapse of the interbank market,  with the LIB-OIS peaking at 364 bps on October 10,  before falling back to 128 bps by the end of 2008.

## 4. Data

Our data come from dealer banks,  which observe market prices and convert these prices into spreads. The conversion of prices into spreads involves models of default timing and recovery amounts,  and we are not privy to these models. However,  one indication of the quality of the data is they were the source for marking-to-market the books of some major financial institutions. The data set contains 392 series of spreads on structured products,  credit derivative indices,  and a smaller set of single-company credit derivatives. In each case,  the banks capture the on-the-run bond or tranche,  which would be the spreads of interest to market participants. Fixed-rate bond spreads are spreads to Treasuries and floating-rate spreads are to LIBOR. Appendix B

Contains a brief discussion of spread calculation.

Some examples of the asset classes covered include spreads on credit card securitization tranches,  auto loan securitization tranches,  and all other major securitization classes. For each asset class,  e.g.,  securitized credit card receivables,  there are spreads for each maturity,  each rating category,  and often for both fixed and floating rate bonds. For example,  for fixed rate credit card receivables there are spreads for AAA bonds for maturities from two years to ten years. Also included are spreads on CDO and CLO tranches.

Some series date back as far as January 2001,  and others begin as late as 2006. Spreads are based on transactions prices,  and if there are no such prices,  then the series ends.

Table 2 provides summary statistics on various categories of asset classes. Panel A shows the spreads in basis points. Our state variable,  LIB-OIS spreads,  is shown first,  followed by representative asset classes that were exposed to subprime: home equity loans (HEL),  mezzanine collateralized debt obligations and home equity lines of credit (HELOC). Also shown are the CDS spreads for Countrywide and Washington Mutual (Wamu),  two of the largest subprime mortgage originators. Finally,  CDS spreads for three monoline insurers are shown. These firms were alleged to have been heavily exposed to subprime risks via credit guarantees made on subprime-related bonds.

Five periods are covered in Table 2: the whole period

(January 2007–January 2009),  the first half of 2007,  the second half of 2007,  all of 2007,  and all of 2008 (which also includes January 2009). In general,  the first half of 2007 looks normal in the sense that it is prior to the panic. Looking at LIB-OIS,  for example,  the average is about 8 basis points for the first half of 2007,  consistent with no arbitrage and no counterparty risk. Also,  AAA HELOC

Bonds traded at just over 15 basis points in the first half of 2007. The mortgage originators and monolines were also trading in normal spread ranges.

From Panel A,  it is clear that the subprime-related structured products and companies get hit in the second half of 2007. HEL,  mezzanine CDOs and HELOCs reach their peaks in the second half of 2007. In the cases of HEL BBB and HELOC AAA there are no data in 2008,  these markets simply disappear. 21 This is also true of Countrywide,  perhaps the largest originator of subprime mortgages. But,  for WAMU and the monoline insurers the peak is in 2008.

The standard deviations are also worth noting. For the subprime-related structured asset classes,  the peak of their spreads occurs in the second half of 2007,  but the standard deviations are mostly highest in 2008. Thinking of standard deviations as a rough guide to uncertainty,  this temporal sequence of rising uncertainty is important later when we look at the repo market in detail.

Panel B shows asset classes that are non-subprime-related structured products based on US portfolios: automobile loans,  credit-card receivables,  student loans,  commercial mortgage-backed securities,  high-grade structured-finance CDO HG SF CDO,  and mezzanine structured-finance CDOs (Mezzanine SF CDO). In each case,  we show the AAA tranches. In the first half of 2007,  the normal state of affairs is that AAA asset-backed securities traded below LIBOR,  true of auto loans,  credit card receivables,  and student loans. For the six categories shown,  there are increases in the spreads in the second half of 2007,  but the large increases are in 2008.

21 The dealer banks use only on-the-run prices to calculate spreads.

If there are no on-the-run prices,  no spreads are calculated.

Summary statistics.

This table reports the summary statistics for the state variable,  credit spreads,  repo spreads and control variables used in this paper. For each series we show summary statistics for the whole period and four subperiods. Panel A shows statistics for the state variable LIB-OIS and the credit spreads of three categories of subprime related assets. Panels B and Panel C shows statistics for the credit spreads of US and non-US non-subprime asset classes,  respectively. Panel D reports the statistics for the spreads between three-month repo rates and Is. Panel E shows statistics for the five control variables used in the regression analysis. All variables given in this table are defined in Appendix A. All spreads are measured in basis points,  with spread computations explained in Appendix B.

Fig. 9. LIB-OIS (spread between the London interbank offered rate and the rate on an overnight index swap) and non-subprime-related asset classes. LIB-OIS is shown with the spreads on AAA-rated asset-backed securities: student loans,  credit cards,  and auto loans. The scale is in basis points.

Fig. 9 is an illustration of the time series patterns for a few of these non-subprime asset classes: automobile loans,  credit card receivables,  and student loans. In each case,  the spreads appear to move closely with the LIB-OIS.

![15_image_0.png](15_image_0.png)

These co-movements represent an important aspect of the crisis: the apparent relation of the interbank market (LIB-OIS) with spreads on securities far removed from subprime housing. In Section 5,  we perform formal tests of these relations.

The crisis was global. Panel C shows non-US nonsubprime-related asset classes,  including mortgagebacked securities with portfolios of Australian,  UK,  and Dutch mortgages. Also shown are UK credit-card receivables,  European consumer loans,  and European automobile loans. These categories are all trading normally in the first half of 2007,  and show increases in their spreads during the second half of 2007. But,  the spreads significantly widen in 2008,  as do the standard deviations of their spreads.

Panel D summarizes our second data set,  which is on the interbank repo market. 22 Shown are different categories of collateral,  in each row. The categories themselves show how far the repo market has evolved from simply being a market related to US Treasuries. For each category the annualized repo rate spread to the Is is shown. These spreads are for overnight repo. 23 Also shown is the average haircut on the collateral during the time period. For example,  looking at the first category,  BBBþ/A corporates,  the average repo rate spread to Is in the first half of 2007 was 2 bps,  and the haircut was zero. Repo spreads for AA-AAA corporate bond collateral were negative for the first half of 2007. Overall,  the patterns in repo are similar to those for the non-subprimerelated asset classes; that is,  the spreads rise in the second half of 2007 but become dramatically higher in 2008. The haircuts also become dramatically higher in 2008. The market disappeared for unpriced CDOs and Close,  unpriced ABS and MBS,  all subprime; and AA-AAA CDO.

The last row in Panel E gives summary data for the repo-rate index and the repo-haircut index. (The latter index is plotted in Fig. 4 and discussed in Section 1.)

During the time that all asset classes have active repo markets in 2007 and early 2008,  the repo-rate index is the equal-weighted average for all the asset classes. 24 As haircuts rise to 100% for any given asset class (¼no trade) on date t,  we drop that class from the index and compute the index change for period t using only the classes that traded in both period t-1 and period t. The repo-haircut

## 5. Empirical Tests

In this section we examine the data more formally to determine which state variables drive the spreads on the various asset classes,  and on repo. In addition,  we empirically examine the determinants of repo haircuts. The goal is to provide some understanding of the mechanism that could result in a small amount of subprime risk having very large impacts on the spreads of completely unrelated asset classes. This is what must be explained to understand the crisis.

## 5.1. Methodology And Basic Tests

We want to test whether the spreads on US non subprime-related asset classes (AAA tranches) move with our state variables for the subprime market (ABX) and for interbank counterparty risk (LIB-OIS). For each asset,  we want to estimate

Panel A shows the results for the six asset classes of US non subprime-related assets (AAA tranches) shown in Table 2. Panel B. At the bottom of the table are F-tests corresponding to the hypothesis that the coefficients on the ABX variables are jointly zero and that the coefficients on the LIB-OIS variables are jointly zero. For the four securitization categories,  credit cards,  auto loans,  student loans,  and commercial mortgage-backed securities,  the LIB-OIS variables are jointly significant. F-tests also show that the ABX coefficients are not jointly significant in any of the regressions For the two categories of CDO,  high grade (HG) and mezzanine,  neither the LIB-OIS nor the ABX is significant Panel B of Table 3 addresses the global aspects of the crisis.

$$S_{i,         t}=a_{0}+a_{1}t+b_{1}\mathbf{ABX}_{t}+b_{2}\mathbf{LIB}-\mathbf{OIS}_{t}+b_{3}\mathbf{X}_{t}+e_{i,         t},         $$

Panel B covers non-US non-subprime related asset classes,  the same ones displayed in Panel C of Table 2. All of these asset classes are significantly affected by LIB-OIS but not by the ABX where $t$ is time,  a weekly time index; $S_{i,         t}$ is the spread on asset i at time t; $a_0$ is a constant; $a_1$ is a time trend; $ABX_r$ is a vector of the last four observations of the ABX spread including the current period; LIB- $\cdot0IS_t$ is a vector of the last four observations of the LIB-OIS spread including the current period; and $x_t$ is a vector of control variables. Because the $S_{i,         t}$ spreads are more similar to unit root prices than to independently identically distributed (i.i.d. returns,  and because these levels vary significantly over our time period,  we take first differences of Eq. (1) and normalize all changes by their level in the previous period:

$$\Delta S_{i,         t}=a_{1}+b_{1}\Delta\mathbf{ABX}_{t}+b_{2}\Delta\mathbf{LIB}-\mathbf{OIS}_{t}+b_{3}\Delta\mathbf{X}_{t}+e_{i,         t}$$

## 5.2. Credit Spreads For All Categories And Tranches

Table 3 focuses on a subset of the available asset categories,  a subset that we think is of particular interest but nevertheless is a subset. Table 4 summarizes the F-tests for the joint significance of the changes in LIB-OIS,  for the full set of asset categories,  broken down into the following categories: subprime-related,  US; non-subprimerelated; non-US non-subprime-related; financial firms (CDS

Spreads); and industrial firms (CDS spreads). The table has three panels,  corresponding to the whole period from January 4,  2007 to January 29,  2009,  and sub-periods. We also performed similar F-tests for the ABX and lags on all asset categories. These results are not tabulated,  because there is nothing of interest to show overall,  changes in the ABX are no better than noise at predicting changes in spreads.

Some highlights from Table 4 are as follows. Subprimerelated asset categories and the broad array of financial firms are not typically correlated to the LIB-OIS. But,  for the overall period,  Panel A,  66% of the US non-subprime asset classes are significantly positively correlated at the 10% confidence level. Similarly,  76% of the non-US nonsubprime categories are positively correlated at the 10%

Level or lower. Note that most of this occurs in 2007 for the non-US structured products,  but for the US nonsubprime structured products it is split across 2007 and 2008. Also,  note that for 2008,  Panel C shows that 75% of 25 Because most of our series are not related to specific companies,  we omit the company-specific control variables used by Collin-Dufresne,  Goldstein,  and Martin (2001).

Credit spreads regression results.

For each bond i,  we estimate Eq. (2) using weekly data from January 4,  2007 to January 29,  2009,  DLIB-OIS is the percentage change of the spread between the 3-month [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and the Overnight Index Swap (Is). DABX is the parentage change of the index at period t. DOIS is the Overnight Index Swap. Dr-10 is the change in yield on the 10-year Treasury,  with its square given by (Dr-10) 2. DSlope is the change in 10-year minus 2-year Treasury yields. DVIX is the change in implied volatility of Standard and Poor 500,  and DS&P is the return on S&P 500. T-statistics are given in parentheses below the coefficient estimates. The last two rows report F-statistics and p-values for the key state variables. The null hypothesis of the LIB-OIS F-test is that the sum of all coefficients of DLIB-OIS and its lags is zero. The null hypothesis of the ABX F-test is the sum of all coefficients of DABX and its lags is zero.

Panel A shows the results of six US non-subprime assets and Panel B shows the results of six non-US non-subprime assets.

| Panel A: US non-subprime asset classes     | Credit spreads   |            |          |                   |               |       |
|--------------------------------------------|------------------|------------|----------|-------------------|---------------|-------|
| Cards                                      | Auto             | Student    | CMBS     | HG SF CDO         | Mezz SF CDO   |       |
| Intercept                                  | 0.003            | 0.016      | 0.010          | 0.036             | 0.042         | 0.052 |
| (0.1)                                      | (0.33)           | (0.33)            | (2.41)   | (2.86)            | (3.96)        |       |
| DLIB-OIS                                   | 0.341            | 0.079      | 0.461    | 0.025             | 0.051               | 0.037       |
| (3.24)                                     | (0.54)           | (5.23)     | (0.26)   | (1.16)                   | (0.94)               |       |
| DLIB-OIS,          t 1                                            | 0.264            | 0.486      | 0.131    | 0.078             | 0.042               | 0.055 |
| (2.64)                                     | (3.55)           | (1.59)     | (0.84)   | (1.00)                   | (1.45)        |       |
| DLIB-OIS,          t 2                                            | 0.132            | 0.012      | 0.138    | 0.082                   | 0.038         | 0.081       |
| (1.32)                                     | (0.08)           | (1.67)     | (0.92)          | (0.91)            | (2.15)               |       |
| DLIB-OIS,          t 3                                            | 0.027            | 0.170      | 0.013          | 0.030                   | 0.030               | 0.004       |
| (0.27)                                     | (1.25)           | (0.16)            | (0.33)          | (0.72)                   | (0.1)               |       |
| DABX                                       | 0.141                  | 0.331            | 0.455    | 0.012             | 0.001         | 0.070 |
| (0.66)                                            | (1.13)                  | (2.32)     | (0.27)   | (0.00)            | (0.86)        |       |
| DABX,          t 1                                            | 0.079            | 0.025            | 0.119    | 0.013                   | 0.016         | 0.061 |
| (0.36)                                     | (0.09)                  | (0.6)      | (0.32)          | (0.18)            | (0.74)        |       |
| DABX,          t 2                                            | 0.315            | 0.250      | 0.202          | 0.072                   | 0.020               | 0.040       |
| (1.48)                                     | (0.86)           | (1.06)            | (1.71)          | (0.23)                   | (0.5)               |       |
| DABX,          t 3                                            | 0.277                  | 0.351            | 0.150          | 0.052                   | 0.049         | 0.011       |
| (1.3)                                            | (1.2)                  | (0.69)            | (1.24)          | (0.54)            | (0.14)               |       |
| DOIS                                       | 0.253                  | 0.147            | 0.358          | 0.096                   | 0.156         | 0.106 |
| (0.78)                                            | (0.33)                  | (1.34)            | (0.69)          | (1.14)            | (0.85)        |       |
| Dr 10                                            | 0.111            | 0.092            | 0.059    | 0.214                   | 0.227               | 0.132       |
| (0.58)                                     | (0.36)                  | (0.36)     | (2.65)          | (2.87)                   | (1.85)               |       |
| (Dr 10) 2                                            | 0.174            | 0.076      | 0.037    | 0.042                   | 0.094               | 0.144       |
| (0.57)                                     | (0.18)           | (0.14)     | (0.33)          | (0.75)                   | (1.26)               |       |
| DS&P                                       | 0.443                  | 1.518      | 0.757          | 1.622                   | 0.580               | 0.592 |
| (0.29)                                            | (0.7)            | (0.57)            | (2.42)          | (0.89)                   | (0.99)        |       |
| DVIX                                       | 0.006                  | 0.004      | 0.003          | 0.003             | 0.002         | 0.006 |
| (0.5)                                            | (0.23)           | (0.29)            | (0.56)   | (0.41)            | (1.26)        |       |
| DSlope                                     | 0.155                  | 0.189      | 0.039          | 0.298             | 0.269         | 0.075 |
| (0.74)                                            | (0.64)           | (0.23)            | (3.29)   | (3.02)            | (0.92)        |       |
| LIB-OIS F-test                             | 20.16            | 10.26      | 26.13    | 2.99              | 1.38          | 1.08  |
| (o 0.01)                                    | (o 0.01)          | (o 0.01)    | (0.08)   | (0.24)            | (0.30)        |       |
| ABX F-test                                 | 0.00             | 0.73       | 0.42     | 0.00              | 0.08          | 0.39  |
| (0.95)                                     | (0.40)           | (0.52)     | (0.95)   | (0.78)            | (0.59)        |       |
| Panel B: Non-US non-subprime asset classes | Credit spreads   |            |          |                   |               |       |
| Australia RMBS                             | UK RMBS          | Dutch RMBS | UK cards | European consumer | European auto |       |
|                                            | receivable       |            |          |                   |               |       |
| Intercept                                  | 0.014            | 0.017      | 0.014    | 0.031             | 0.032         | 0.037 |
| (0.52)                                     | (0.93)           | (1.14)     | (2.4)    | (3.21)            | (2.35)        |       |
| DLIB-OIS                                   | 0.126            | 0.240      | 0.100    | 0.109             | 0.049         | 0.081 |
| (1.57)                                     | (4.38)           | (2.71)     | (2.86)   | (1.76)            | (1.8)         |       |
| DLIB-OIS,          t 1                                            | 0.575            | 0.237      | 0.071    | 0.136             | 0.021         | 0.019 |
| (7.56)                                     | (4.57)           | (2.11)     | (3.72)   | (0.8)             | (0.45)        |       |
| DLIB-OIS,          t 2                                            | 0.181                  | 0.051            | 0.115    | 0.019             | 0.033         | 0.104 |
| (2.44)                                            | (1.01)                  | (3.42)     | (0.52)   | (1.26)            | (2.51)        |       |
| DLIB-OIS,          t 3                                            | 0.138            | 0.067      | 0.015          | 0.019                   | 0.020         | 0.022 |
| (1.86)                                     | (1.32)           | (0.47)            | (0.55)          | (0.77)            | (0.53)        |       |
| DABX                                       | 0.025            | 0.029      | 0.095    | 0.094             | 0.116         | 0.095 |
| (0.15)                                     | (0.26)           | (1.37)     | (1.03)   | (1.65)            | (0.84)        |       |
| DABX,          t 1                                            | 0.002                  | 0.022      | 0.002    | 0.028             | 0.001         | 0.010       |
| (0.02)                                            | (0.19)           | (0.03)     | (0.34)   | (0.01)            | (0.09)               |       |
| DABX,          t 2                                            | 0.171                  | 0.018            | 0.037          | 0.011             | 0.037         | 0.044 |
| (1.09)                                            | (0.17)                  | (0.54)            | (0.13)   | (0.54)            | (0.4)         |       |
| DABX,          t 3                                            | 0.173            | 0.072      | 0.109          | 0.084                   | 0.060               | 0.265       |
| (1.09)                                     | (0.66)           | (1.6)            | (1.05)          | (0.9)                   | (2.47)               |       |
| DOIS                                       | 0.034            | 0.031            | 0.237          | 0.051                   | 0.054               | 0.164       |

| Table 3 (continued ) Panel B: Non-US non-subprime asset classes   |         |         | Credit spreads   |            |                   |               |
|-------------------------------------------------------------------|---------|---------|------------------|------------|-------------------|---------------|
| Australia RMBS                                                    |         | UK RMBS | Dutch RMBS       | UK cards   | European consumer | European auto |
|                                                                   |         |         |                  | receivable |                   |               |
| (0.1)                                                             |         | (0.15)         | (0.63)                  | (0.33)            | (0.48)                   | (0.91)               |
| Dr 10                                                                   | 0.207         | 0.140         | 0.067                  | 0.134            | 0.106                   | 0.146               |
| (1.36)                                                                   |         | (1.34)         | (0.81)                  | (1.84)            | (1.97)                   | (1.71)               |
| (Dr 10) 2                                                                   | 0.194   | 0.022         | 0.058                  | 0.036            | 0.096                   | 0.018               |
| (0.85)                                                            |         | (0.15)         | (0.5)                  | (0.34)            | (1.23)                   | (0.15)               |
| DS&P                                                              | 0.915         | 0.272         | 0.709                  | 0.164      | 0.194             | 0.695         |
| (0.76)                                                                   |         | (0.33)         | (0.86)                  | (0.28)     | (0.45)            | (1.01)        |
| DVIX                                                              | 0.006         | 0.001         | 0.002                  | 0.000      | 0.001             | 0.003         |
| (0.64)                                                                   |         | (0.11)         | (0.31)                  | (0.07)     | (0.39)            | (0.6)         |
| DSlope                                                            | 0.179   | 0.077   | 0.051            | 0.133      | 0.091             | 0.190         |
| (1.05)                                                            |         | (0.66)  | (0.51)           | (1.64)     | (1.53)            | (2)           |
| LIB-OIS                                                           | 25.57   | 30.71   | 20.89            | 14.40      | 6.56              | 8.62          |
| F-test                                                            | (o 0.01) | (o 0.01) | (o 0.01)          | (o 0.01)    | (0.01)            | (o 0.01)       |
| ABX                                                               | 0.01    | 0.28    | 0.14             | 0.09       | 0.51              | 0.41          |
| F-test                                                            | (0.93)  | (0.60)  | (0.71)           | (0.77)     | (0.48)            | (0.52)        |

| sum of coefficients for DLIB-OIS and its lags. Categories Total number   | Negative   | Positive   |     |    |    |    |     |
|--------------------------------------------------------------------------|------------|------------|-----|----|----|----|-----|
| 10%                                                                      | 5%         | 1%         | 10% | 5% | 1% |    |     |
| Panel A: Whole period: January 4,          2007 to January 29,          2009 Subprime 63   | 1          | 1          | 0   | 2  | 1  | 2  |     |
| Nonsubprime_US                                                           | 176        | 3          | 0   | 0  | 4  | 7  | 106 |
| Nonsubprime_Europe                                                       | 59         | 0          | 0   | 0  | 0  | 6  | 39  |
| Financial                                                                | 46         | 0          | 0   | 0  | 3  | 2  | 6   |
| Industrial                                                               | 48         | 0          | 0   | 0  | 5  | 14 | 9   |
| Total                                                                    | 392        | 4          | 1   | 0  | 14 | 30 | 162 |
| Panel B: Subperiod I: January 4,          2007 to December 27,          2007 Subprime 63   | 2          | 4          | 2   | 0  | 2  | 1  |     |
| Nonsubprime_US                                                           | 176        | 4          | 0   | 1  | 8  | 21 | 75  |
| Nonsubprime_Europe                                                       | 59         | 0          | 0   | 0  | 5  | 10 | 24  |
| Financial                                                                | 46         | 3          | 1   | 0  | 1  | 2  | 1   |
| Industrial                                                               | 48         | 0          | 0   | 0  | 0  | 1  | 4   |
| Total                                                                    | 392        | 9          | 5   | 3  | 14 | 36 | 105 |
| Panel C: Subperiod II: January 3,          2008 to January 29,          2009 Subprime 63   | 1          | 0          | 0   | 0  | 0  | 0  |     |
| Nonsubprime_US                                                           | 176        | 8          | 0   | 0  | 23 | 26 | 41  |
| Nonsubprime_Europe                                                       | 59         | 0          | 0   | 0  | 0  | 1  | 0   |
| Financial                                                                | 46         | 0          | 0   | 0  | 6  | 10 | 6   |
| Industrial                                                               | 48         | 0          | 0   | 0  | 6  | 9  | 21  |
| Total                                                                    | 392        | 9          | 0   | 0  | 35 | 46 | 68  |

Summary of F-test results for different asset categories.

For each bond i,  we estimate Eq. (2) using weekly data from January 4,  2007 to January 29,  2009,  DLIB-OIS is the percentage change of the spread between the 3-month [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and the Overnight Index Swap (Is). This table summarizes the F-test results for the LIB-OIS state variable and its lags. The null hypothesis of F-test is the sum of all coefficients of DLIB-OIS and its lags is zero. The numbers in the table indicate how many F-tests of bonds in each category are significant at various confidence levels. Asset categories are listed in Panel A of Table 1. ''Negative'' and ''Positive'' indicate the sign of the sum of coefficients for DLIB-OIS and its lags.

The industrials are significantly,  positively correlated to changes in LIB-OIS,  indicating the real affects hitting the economy. In 2007,  Panel B,  there are no such real effects.

Table 5 presents the F-test results divided by rating category. Assets in all rating categories were eligible for repo,  but AAA collateral was likely to be the most widely used. The table is suggestive in this regard,  but not definitive. Looking at the whole period (Panel A),  62% of the AAA

Products were positively and significantly correlated with changes in LIB-OIS. This is about equally divided between the two subperiods. For AA,  A,  and BBB-rated bonds,  the percentages that are significantly positive for the whole period are 28%,  55%,  and 53%,  respectively. For A and BBB,  this is about equally divided between the two subperiods.

## 5.3. Repo Spreads

In a world with known and certain values for collateral and no transactions costs for selling collateral,  repo rates should be equal to the risk-free rate,  and spreads would be zero. A lender/depositor would have no fear of default,  because the collateral could be freely seized and sold.

Table 5 Summary of F-test results for different rating classes.

For each bond i,  we estimate Eq. (2) using weekly data from January 4,  2007 to January 29,  2009,  DLIB-OIS is the percentage change of the spread between the three-month [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and the overnight index swap (Is). This table summarizes the F-test results for the LIB-OIS state variable and its lags. The null hypothesis of F-test is the sum of all coefficients of DLIB-OIS and its lags is zero. The numbers in the table indicate how many F-tests of bonds in each rating class are significant at various confidence levels. Negative and positive indicate the sign of the sum of the coefficients for DLIB-OIS

And its lags.

| and its lags. Rating                                                 | Total number   | Negative   | Positive   |     |    |    |     |
|----------------------------------------------------------------------|----------------|------------|------------|-----|----|----|-----|
|                                                                      | 10%            | 5%         | 1%         | 10% | 5% | 1% |     |
| Panel A: Whole Period: January 4,          2007 to January 29,          2009 AAA 157 4 | 0              | 0          | 4          | 10  | 83 |    |     |
| AA                                                                   | 47             | 0          | 1          | 0   | 1  | 3  | 9   |
| A                                                                    | 74             | 0          | 0          | 0   | 3  | 5  | 33  |
| BBB                                                                  | 83             | 0          | 0          | 0   | 2  | 6  | 36  |
| Other                                                                | 31             | 0          | 0          | 0   | 4  | 6  | 1   |
| Total                                                                | 392            | 4          | 1          | 0   | 14 | 30 | 162 |
| Panel B: Subperiod I: January 4,          2007 to December 27,          2007 AAA 157 5 | 1              | 1          | 9          | 25  | 47 |    |     |
| AA                                                                   | 47             | 0          | 0          | 1   | 0  | 1  | 7   |
| A                                                                    | 74             | 0          | 2          | 0   | 3  | 4  | 27  |
| BBB                                                                  | 83             | 1          | 1          | 0   | 1  | 5  | 23  |
| Other                                                                | 31             | 3          | 1          | 1   | 1  | 1  | 1   |
| Total                                                                | 392            | 9          | 5          | 3   | 14 | 36 | 105 |
| Panel C: Subperiod II: January 3,          2008 to January 29,          2009 AAA 157 0 | 0              | 0          | 4          | 13  | 44 |    |     |
| AA                                                                   | 47             | 1          | 0          | 0   | 3  | 12 | 4   |
| A                                                                    | 74             | 4          | 0          | 0   | 14 | 9  | 5   |
| BBB                                                                  | 83             | 4          | 0          | 0   | 9  | 11 | 5   |
| Other                                                                | 31             | 0          | 0          | 0   | 5  | 1  | 10  |
| Total                                                                | 392            | 9          | 0          | 0   | 35 | 46 | 68  |

In reality,  collateral pricing can be uncertain,  and illiquidity and volatility in the secondary markets for this collateral can induce large transactions costs following a default. In this case,  measures of bank-counterparty risk (LIB-OIS) could be relevant to lenders,  and in the case of default they would be sensitive to uncertainty about collateral values. Lenders could then demand higher rates or higher haircuts or both. Higher rates would occur because the loans are no longer riskfree.

Higher haircuts could occur to adjust for the uncertain value of the collateral,  because each dollar of collateral could be worth much less by the time it can be sold.

Where $S_{j,          t}$ is the average spread to Is for all assets in class j

$$S_{j,          t}=\overline{S}_{i,          t},          i\in j.$$

$\Delta VOL_{j,          t}$ is defined as the difference between expectec volatility today and realized volatility over the previous four weeks (not including the current week)

In reality,  collateral pricing can be uncertain,  and illiquidity and volatility in the secondarymarkets for this collateral can induce large transactions costs following a default. In this case,  measures of bank-counterparty risk (LIB-OIS) could be relevant to lenders,  and in the case of default they would be sensitive to uncertainty about collateral values. Lenders could then demand higher rates or higher haircuts or both. Higher rates would occur because the loans are no longer riskfree Higher haircuts could occur to adjust for the uncertain value of the collateral,  because each dollar of collateral could be worth much less by the time it can be sold. To test for the quantitative importance of these relations,  we first estimate a version of Eq. (2) for repo spreads:

$$\Delta\mathrm{VOL}_{j,          t}=\mathrm{VOL}_{j,          t}-\mathrm{VOL}_{j,          t-5}.$$

Volatility uses absolute differences,  and not percentage differences,  because percentage differences are harder to interpret across multiple weeks. Because we use future information for our expected-volatility proxy the resulting estimates could not be part of an imple mentable investment strategy. This restriction does not matter for our analysis,  because we are not seeking to build investment portfolios from these results. In any case,  we do not have a choice because volatility expecta tions cannot be extracted from historical spread data. We estimate Eq. (3) for all five classes of collateral that

$$\Delta R_{j,          t}=a_{1}+b_{1}\Delta\mathbf{ABX}_{t}+b_{2}\Delta\mathbf{LIB}-\mathbf{OIS}_{t}+b_{3}\Delta\mathbf{X}_{t}+b_{4}\Delta\mathbf{VOL}_{j,          t}+e_{i,          t}$$

where $R_{j,          t}$ is the average spread of repo rates to the Is for some class j of collateral (as in Table 2,  Panel D),  $v 0 L_{j.r}$ is a vector of the last four expected volatilities (defined below) for that class of collateral,  and all other variables are defined as in Eq. (2).

$VOL_{j,          t}$ is a forward-looking measure,  defined here as the average absolute (weekly) change in spreads over the next four weeks 26

Have data available to construct the VOL measure. 27 The regression results for these five classes are shown in Table 6. The final rows show the results of the F-tests for the joint significance of LIB-OIS (Test 1),  the ABX (Test 2) and VOL changes (Test 3). These tests show that the changes in repo spreads are significantly related to the change in LIB-OIS for all five categories,  with almost all of the effect coming in the contemporaneous period.

$$\mathrm{VOL}_{j,          t}=\sum_{s=1}^{4}\left (\frac{|\Delta S_{j,          t+s}|}{4}\right).$$

Changes in repo spreads are not significantly related to changes in the ABX or VOL or to any of the other control variables. Thus,  just as we found for credit spreads in our earlier analysis,  the state variable for bank-counterparty risk is the only significant correlate with repo spreads.

### 5.4. Repo Haircuts

It seems natural that banks would have to raise repo spreads to attract funds. But,  higher rates do not by themselves cause a systemic event. For a run on repo,  we need to see that the depositors withdraw from the bank,  that is,  market participants demand higher repo haircuts. Fig. 4 shows that this did occur. In this subsection we turn to examining repo haircuts.

First,  regarding the data,  the size of repo haircuts depends on the identities of the counterparties and on the type of collateral. Our data set is from a high-quality dealer bank transacting with other high-quality dealer banks. Other repo data that we have involve different types of counterparties,  e.g.,  a dealer bank providing collateralized funds to a hedge fund,  via reverse repo. The haircuts that a hedge fund faces when borrowing from a dealer bank are larger than what the dealer faces in the interbank market,  for the same bond (on the same date).

All the haircut data sets show the same pattern as displayed in Fig. 4,  but they do not all start at zero haircuts prior to the crisis. The data set we analyze here is the most extensive.

Haircuts are a puzzle. If depositors in the repo market,  receiving collateral to protect their deposits,  were concerned that the bank might fail,  causing them to need to sell the collateral,  then the risks of what price they would realize would enter their calculation. If the market for the collateral is volatile,  then standard finance theory suggests that they should ask for a higher repo rate initially. Dang,  Gorton,  and Holmstrom (2011) ¨ argue that debt and in particular,  repo are optimally designed securities which are used to intertemporally transport value. Their design is such as to minimize the variance of their value in the face of public shocks. A haircut is sometimes needed to protect against such volatility and provide an incentive for a counterparty to repurchase the security. We next explore the factors related to these increases using the same regression framework as we did for repo spreads:

Where Hj,  t is the average haircut for all assets in class j and all other variables are defined as in Eq. (3). 28 Because haircuts are already defined as a percentage of the total value of the underlying collateral,  the change in haircuts on the left-hand side of Eq. (7) is already given in percentages. Table 7 summarizes the results. As we have found in earlier tests,  the ABX and the control variables are not significant. In contrast to previous regressions,  the change in the LIB-OIS is also not significant. The only variable with any explanatory power is the proxy for expected volatility,  which is significant for three of the five classes of collateral.

The key finding here is that both repo spreads and repo haircuts rose during the crisis,  with these increases correlated either to concerns about counterparty risk (for spreads),  or to uncertainty about collateral values (for haircuts). While these results are somewhat different for spreads and haircuts,  we suspect that this system is jointly determined and that a disruption in the interbank market and increases in uncertainty about collateral are both necessary conditions for a run on repo. In an environment with no counterparty risk,  no reason exists to expect haircuts to be affected by uncertainty about collateral; similarly,  high counterparty risk by itself would be unlikely to affect repo spreads if all collateral had fixed values and liquid markets. It seems unlikely that nature provides an example with rising VOL but no change in LIB-OIS. Instead,  all of these things happened at the same time,  and it is not possible to disentangle the exact causes.

### 5.5. LIB-OIS: counterparty risk or market-liquidity risk?

Overall,  these results support the interpretation of LIB-OIS as a proxy for counterparty risk in our results.

Our results show a strong correlation between the LIB-OIS and both credit spreads and repo rates,  and we have interpreted the LIB-OIS as a proxy for counterparty risk. However,  Schwarz (2009) demonstrates that,  during the early stages of the crisis,  the LIB-OIS was driven at least as much by market-liquidity risk as by counterparty risk We can use the Schwarz data and methods to decompose the LIB-OIS relations for part of our sample period. For these tests,  we use the Schwarz credit-tiering measure,  which represents the average spread in overnight borrowing rates between high-risk and low-risk banks. 29 As shown in Schwarz (2009),  this measure can be thought of as a proxy for counterparty risk,  and it explains some (but not most) of the variation in LIB-OIS from January 1,  2007 through April 30,  2008,  the last date that her series is available In our first set of tests,  we replace the △LIB-OIS

Receiving collateral to protect their deposits,  were concerned that the bank might fail,  causing them to need to sell the collateral,  then the risks of what price they would realize would enter their calculation. If the market for the collateral is volatile,  then standard finance theory suggests that they should ask for a higher repo rate initially. Dang,  Gorton,  and Holmstrom (2011) argue that debt and in particular,  repo are optimally designed securities which are used to intertemporally transport value. Their design is such as to minimize the variance of their value in the face of public shocks. A haircut is sometimes needed to protect against such volatility and provide an incentive for a counterparty to repurchase the security. We next explore the factors related to these increases using the same regression framework as we did for repo spreads:

$$\Delta H_{j,          t}=a_{1}+b_{1}\Delta\mathbf{ABX}_{t}+b_{2}\Delta\mathbf{LIB}-\mathbf{OIS}_{t}+b_{3}\Delta\mathbf{X}_{t}+b_{4}\Delta\mathbf{VOL}_{j,          t}+e_{i,          t}$$

Variables in Eqs. (2)(4) with analogous changes in the credit-tiering measure. The results,  for the time period through April 30. 2008,  are almost as strong as for the LIB-OIS variable over the same time period. For 176 nonsubprime related US bond spreads,  the credit-predicted component is significant 60 times at the one-percentlevel and an additional 28 times at the $5\%$ level. These results suggest that the Schwarz (2009) credit-tiering measure could be the ideal proxy for counterparty risk—even better than LIB-OIS. Which is contaminated by other factors—if it were available for the entire sample period. For the haircut regressions in Eq. (4),  the credit-tiering measure,  like LIB-OIS,  is insignificant in all cases. 30 In our second set of tests,  we employ a two-step

Where $H_{j,          t}$ is the average haircut for all assets in class j and all other variables are defined as in Eq. (3). 28 Because haircuts are already defined as a percentage of the total value of the underlying collateral,  the change in haircuts on the left-hand side of Eq. (7) is already given in percentages. Table 7 summarizes the results. As we have found in earlier tests,  the ABX and the control variables are not significant. In contrast to previous regressions,  the change in the LIB-OIS is also not significant. The only variable with any explanatory power is the proxy for expected volatility,  which is significant for three of the five classes of collateral. The key finding here is that both repo spreads and repo

Procedure. We first regress LIB-OIS on the credit-tiering measure and use the point estimate of the coefficient from this regression to decompose LIB-OIS into a creditpredicted variable and a residual,  and into weekly changes for both of those components. The residual here would include market liquidity and any other unex plained portions of LIB-OIS. We then replace △LIB-OIS with these two components—predicted and residual,  in Eqs. (2)(4). We find that the credit-predicted component performs much better than the residual for predicting credit spreads and repo rates. For example,  for the 176 non-subprime related US bond spreads,  the creditpredicted component is significant 35 times at the 1% level and an additional 31 times at the $5\%$ level. In contrast,  the residual is never significant for these bonds at the $1\%$ level,  and only four times at the $5\%$ level less than would be expected by chance. Thus,  for the early part of the crisis,  it seems that the counterparty-risk component of LIB-OIS is much more important for our results than is the market-liquidity component haircuts rose during the crisis,  with these increases correlated either to concerns about counterparty risk (for spreads),  or to uncertainty about collateral values (for haircuts). While these results are somewhat different for spreads and haircuts,  we suspect that this system is jointly determined and that a disruption in the interbank market and increases in uncertainty about collateral are both necessary conditions for a run on repo. In an environment with no counterparty risk,  no reason exists to expect haircuts to be affected by uncertainty about collateral; similarly,  high counterparty risk by itself would be unlikely to affect repo spreads if all collateral had fixed values and liquid markets. It seems unlikely that nature provides an example with rising VOL but no change in particular non-subprime related collateral. Public shocks causing expected future spread volatility led to increases in the repo haircuts,  which is tantamount to massive withdrawals from the banking system. The banking system has changed,  with securitized banking playing an increasing role alongside traditional banking. One large area of securitized banking,  the securitization of subprime home mortgages,  began to weaken in early 2007 and continued to decline throughout 2007 and 2008. But,  the weakening of subprime per se was not the shock that caused systemic problems. The first systemic event occurs in August 2007,  with a shock to the repo market that we demonstrate using the LIB-OIS,  the spread between the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and the Is,  as a proxy. The reason that this shock occurred in August 2007,  as opposed to any other month of 2007,  is perhaps unknowable. We hypothesize that the market slowly became aware of the risks associated with the subprime market,  which then led to doubts about repo collateral and bank solvency. At some point (August 2007 in this telling) a critical mass of such fears led to the first run on repo,  with lenders no longer willing to provide shortterm finance at historical spreads and haircuts.

## 6. Conclusion

How did problems in the subprime mortgages cause a systemic event? Our answer is that there was a run in the repo market. The location and size of subprime risks held by counterparties in the repo market were not known and led to fear that liquidity would dry up for collateral,  in particular non-subprime related collateral. Public shocks causing expected future spread volatility led to increases in the repo haircuts,  which is tantamount to massive withdrawals from the banking system.

The banking system has changed,  with securitized banking playing an increasing role alongside traditional banking. One large area of securitized banking,  the securitization of subprime home mortgages,  began to weaken in early 2007 and continued to decline throughout 2007 and 2008. But,  the weakening of subprime per se was not the shock that caused systemic problems. The first systemic event occurs in August 2007,  with a shock to the repo market that we demonstrate using the LIB-OIS,  the spread between the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and the Is,  as a proxy. The reason that this shock occurred in August 2007,  as opposed to any other month of 2007,  is perhaps unknowable. We hypothesize that the market slowly became aware of the risks associated with the subprime market,  which then led to doubts about repo collateral and bank solvency. At some point (August 2007 in this telling) a critical mass of such fears led to the first run on repo,  with lenders no longer willing to provide shortterm finance at historical spreads and haircuts.

After August 2007,  the securitized-banking model was under pressure,  with small equity bases stretched by increasing haircuts on high-grade collateral. We see evidence of this pressure in the co-movement of spreads on a wide variety of AAA and AA credits. This pressure contributed to the forced rescue of Bear Stearns in March 2008 and the failure of Lehman Brothers in September 2008. The second systemic event and run on repo occurred with the failure of Lehman. In this second event,  we see parallels to 19 th century banking crises,  with a famine of liquidity leading to significant premia on even the safest of assets.

## Appendix A. Glossary Of Key Terms And Asset Classes

This glossary provides definitions for all terms given in bold in the body of the paper and all asset classes listed in Table 2. For the latter group,  we include the panel location of that variable in parenthesis following the definition

(e.g.,  Panel A).

AA-AAA ABS RMBS or CMBS. This residential mortgage-backed security or commercial mortgage-backed security has ratings between AA and AAA,  inclusive

(Table 1—Panel D).

OAA ABS RMBS or CMBS. This residential mortgagebacked security or commercial mortgage-backed security has ratings between AA and AAA,  inclusive (Table 1— Panel D).

AA-AAA CDO. This collateralized debt obligation has ratings between AA and AAA,  inclusive (Table 2—Panel D).

AA-AAA CLO. This collateralized loan obligation ratings between AA and AAA,  inclusive (Table 2—Panel D).

A-AAA ABS Auto CC or S.L. This asset-backed security is made up of auto loans,  credit card receivables,  or student loans,  with ratings between A and AAA,  inclusive

(Table 2—Panel D).

ABX,  ABX index,  ABX index spread. The ABX index is a credit derivative that references 20 equally-weighted subprime RMBS tranches. There are also subindices are linked to a basket of subprime bonds with specific ratings:

AAA,  AA,  A BBB and BBB-. Each sub-index references the 20 subprime RMBS bonds with the rating level of the subindex. Every six months the indices are reconstituted based on a pre-identified set of rules,  and a new vintage of the index and sub-indices is issued. In this paper,  we focus on the BBB ABX tranche of the first vintage of the ABX in 2006,  which is representative of the riskier levels of subprime securitization. We refer to this tranche of the 2006-1 issue simply as ABX.

Asset-backed securities (ABS). An asset-backed security is a bond that is backed by the cash flows from a pool of specified assets in a special purpose vehicle not the general credit of a corporation. The asset pools could be residential mortgages (residential mortgage-backed securities) commercial mortgages (commercial mortgage-backed securities),  automobile loans,  credit card receivables,  student loans,  aircraft leases,  royalty payments,  or many other asset classes.

Australia RMBS AAA. This AAA-rated RMBS is backed by Australian mortgages (Table 2—Panel C).

Auto AAA. This AAA-rated ABS is backed by auto loans

(Table 2—Panel B).

BBBþ/A corporate. These [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]] are rated between BBBþ and A,  inclusive (Table 2—Panel D).

Cards AAA. This AAA-rated ABS is backed by credit card receivables (Table 2—Panel B).

CMBS AAA. This is an AAA-rated commercial mortgage backed securities (Table 2—Panel B).

Credit default swaps (CDS). A credit default swap is a derivative contract in which one party agrees to pay the other a fixed periodic coupon for the specified life of the agreement. The other party makes no payments unless a specified credit event occurs. Credit events are typically defined to include a material default,  bankruptcy or [[Class Slide 4-Restructuring Debt Outside Bankruptcy|Debt Restructuring ]] for a specified reference asset. If such a credit event occurs,  the party makes a payment to the first party,  and the swap then terminates. The size of the payment is usually linked to the decline in the reference asset's market value following the credit event.

Collateralized debt obligation (CDO). A collateralized debt obligation is a special purpose vehicle,  which buys a portfolio of fixed income assets and finances the purchase of the portfolio via issuing different tranches of risk in the capital markets. These tranches are senior tranches (rated Aaa/AAA),  mezzanine tranches (rated Aa/AA to Ba/BB),  and equity tranches (unrated). Of particular interest are ABS CDOs,  which have underlying portfolios consisting of asset-backed securities,  including residential mortgage-backed securities and commercial mortgagebacked securities.

Collateralized loan obligation. A collateralized loan obligation is a securitization of commercial bank loans.

Commercial mortgage-backed security (CMBS). See asset-backed security.

Dutch RMBS AAA. This AAA-rated RMBS is backed by Dutch mortgages (Table 2—Panel C).

European auto AAA. This AAA-rated ABS is backed by European auto loans (Table 2—Panel C).

European consumer receivables AAA. This AAA-rated ABS backed by European consumer receivable (Table 2— Panel C).

Haircut. The collateral pledged by borrowers toward the repo may have a haircut or initial margin applied,  which means that the collateral is valued at less than market value. This haircut reflects the perceived underlying risk of the collateral and protects the lender against a change in its value. Haircuts are different for different asset classes and ratings.

HEL BBB. This BBB-rated ABS backed by home equity loans with BBB ratings (Table 2—Panel A).

HELOC AAA. This AAA-rated ABS is backed by Homeequity lines-of-credit (Table 2—Panel A).

HG SF CDO. High-grade structured-finance CDOs buy collateral consisting of the AAA and AA-rated tranches of securitized bonds (Table 2—Panel B).

Home equity loans (HEL). A home equity loan is a line of credit under which a home owner can borrower using the home equity as collateral.

Home equity lines of credit (HELOC). A home equity line of credit differs from a home equity loan in that the borrower does not borrower the full amount of the loan at the outset but can draw down the line of credit over a specified period of time with a maximum amount.

LIB-OIS. This is the spread between the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and the Is.

LIBOR. The London Interbank Offered Rate (LIBOR) is a series of interest rates,  of different maturities and currencies,  at which banks offer to lend fund to each other. These rates are calculated by the British Bankers' Association as the averages of quotes contributed by a panel of banks and announced at 11:00 a.m. in England. This is called the rate fixing. Quotes are ranked,  and the top and bottom quartiles are discarded. [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] is fixed for 15 different maturities,  from overnight to one year,  and in ten international currencies. Similar fixing arrangements exist in many markets around the world. See Gyntelberg and Wooldridge (2008).

Mezzanine SF CDO. A mezzanine structured finance CDO refers to a collateralized debt obligation in which the underlying portfolio consists of tranches of different asset-backed securities that are rated between BBB and A,  inclusive (Table 2—Panel B).

Monoline insurers or monoline insurance companies.

These are insurance companies that are restricted by regulation to one line of the business,  the business of issuing financial guarantees on bonds,  that is insurance against the loss due to default of specified bonds. The first such company was AMBAC Financial Group Inc.,  formed in 1971,  followed by MBIA,  formed in 1983. In 1989 a law in New York limited the sale of financial insurance products by those companies solely to bond insurance,  making them ''monolines.''

Mortgage originators. These financial firms underwrite and fund residential and possibly,  commercial mortgages.

Overnight index swap (Is). An overnight indexed swap is a fixed/floating interest rate swap in which the floating leg of the swap is tied to a published index of a daily overnight rate reference. The term ranges from one week to two years (sometimes more). At maturity,  the two parties agree to exchange the difference between the interest accrued at the agreed fixed rate and interest accrued through geometric averaging of the floating index rate on the agreed notional amount. This means that the floating rate calculation replicates the accrual on an amount (principal plus interest) rolled at the index rate every business day over the term of the swap. If cash can be borrowed by the swap receiver on the same maturity as the swap and at the same rate and lent back every day in the market at the index rate,  the cash payoff at maturity exactly matches the swap payout the Is acts as a perfect hedge for a cash instrument. Because indices are generally constructed on the basis of the average of actual transactions,  the index is generally achievable by borrowers and lenders. Economically,  receiving the fixed rate in an Is is like lending cash. Paying the fixed rate in an Is is like borrowing cash. Settlement occurs net on the earliest practical date. There is no exchange of principal. The index rate used is typically the weighted average rate for overnight transactions as published by the central bank (e.g.,  the effective [[A Guide to the Front End and Basis Swap Markets#Federal Funds Market|Fed Funds Rate]] ).

Repo-haircut index. This is equal-weighted average haircut for all nine of the asset classes in Panel D of Table 2. Haircuts of 100% (¼no trade) are included in this average (Table 2—Panel D).

Repo-rate index: During the time that all asset classes have active repo markets in 2007 and early 2008,  this index is identical to the equal-weighted average repo rate for all nine the asset classes in Panel D of Table 2. As haircuts rise to 100% for any given asset class (¼no trade) on date t,  we drop that class from the index and compute the index change for period t using only the classes that traded in both period t-1 and period t (Table 2—Panel D).

Repurchase agreements,  reverse repurchase agreement. A sale and repurchase agreement,  known as a repo,  is a sale of a security combined with an agreement to repurchase the same security at a specified price at the end of the contract. One side of the transaction lends or deposits money; the other side is borrowing. Economically,  a repo is a secured or collateralized loan,  that is,  a loan of cash against a security as collateral. From the point of view of the borrower of the cash (who is putting up the security as collateral),  it is a reverse repurchase agreement,  or ''reverse repo.''

Residential mortgage-backed security (RMBS). See asset-backed security.

Securitization. This process of financing by segregates specified cash flows from loans originated by a firm (the sponsor) and sells claims specifically linked to these specified cash flows. This is accomplished by setting up another company,  called a special purpose vehicle or special purpose entity,  and then selling the specified cash flows to this company,  which purchases the rights to the cash flows by issuing (rated) securities into the capital market. The sponsor services the cash flows,  that is,  makes sure that the cash flows are arriving,  etc. The SPV

Is not an operating company in the usual sense. It is more of a robot company in that it is a set of rules. It has no employees or physical location.

Securitized banking. This term refers to the nexus of securitization and repurchase markets in which depositors are able to engage in (reverse) repo by depositing money in exchange for securitized bonds as collateral.

Securitized bond. This general term refers to any traded and rated tranche of an ABS,  RMBS,  CMBS,  CDO,  or CLO.

Special purpose vehicle (SPV). An SPV or special purpose entity (SPE) is a legal entity that has been set up for a specific,  limited,  purpose by another entity,  the sponsoring firm. An SPV can take the form of a corporation,  trust,  partnership,  or a limited liability company. The SPV can be a subsidiary of the sponsoring firm,  or it can be an orphan SPV,  one that is not consolidated with the sponsoring firm for tax,  accounting,  or legal purposes

(or it could be consolidated for some purposes but not others). An SPV can carry out only some specific purpose,  or circumscribed activity,  or a series of such transactions. An essential feature of an SPV is that it be [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] remote,  that is,  the SPV never can become legally bankrupt. The most straightforward way to achieve this would be for the SPV to waive its right to file a voluntary [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] petition,  but this is legally unenforceable. The only way to completely eliminate the risk of either voluntary or involuntary [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] is to create the SPV

In a legal form that is ineligible to be a debtor under the US Bankruptcy Code.

Structured finance. This broad term is used to describe securitized bonds,  but also more generally any bond with an embedded derivative.

Student AAA. AAA-rated ABS is backed by student loans (Table 2—Panel B).

Tranche. A tranche (French for ''cut'') refers to a slice of a portfolio ordered by seniority,  For example,  a senior tranche or AAA tranche is more senior than a junior tranche or BBB tranche.

Triparty repo. This sale and repurchase agreement is intermediated by a custodian bank or international clearing organization. The intermediary manages the transaction including marking-to-market of the collateral. Parties to the transaction agree to an eligible collateral profile,  which determines what bonds can be used as collateral.

The intermediary bears intraday risk see Task Force on Tri-Party Repo Infrastructure (2010).

UK cards AAA. This AAA-rated ABS is backed by UK

Credit-card receivables (Table 2—Panel C).

UK RMBS AAA. This AAA-rated RMBS is backed by UK

Mortgages (Table 2—Panel C).

Unpriced ABS or MBS,  all subprime. These are all tranches of ABSs or MBS and all subprime securitized bonds which do not have public pricing posted on Bloomberg or Reuters (two news services used by traders)

(Table 2—Panel D).

Unpriced CDO or CLO. All tranches of CDO and CLO

Securitized bonds that do not have public pricing posted on Bloomberg or Reuters (two news services used by traders) (Table 2—Panel D).

VIX. The VIX index is a measure of the volatility of the S&P index,  produced by and traded on the Chicago Board of Trade. The new version of the index,  introduced in 2003,  is based on the options prices of the broader S&P

500 index. Its square approximates the conditional riskneutral expectation of the annualized return variance over the next 30 calendar days and thus the corresponding variance swap rate. See Carr and Wu (2006) (Table 2— Panel E).

## Appendix B. The Spread Data

Spreads are not a common variable of analysis for financial economists,  who prefer to focus on returns. As a practical matter,  however,  interest rate risk is frequently hedged,  leaving credit risk as the focus. Credit spreads isolate the risk of default and the recovery rate. Thus,  when assessing fixed income securities,  investors focus on spreads as a common measure for determining how much they are being paid to bear the credit risk embedded in a security.

For fixed rate instruments,  the spread is the yield spread,  i.e.,  the difference between the yield-to-maturity of the credit risky instrument and the benchmark instrument (LIBOR) with the same maturity. Floating rate instrument prices are converted to spreads by determining the discount margin,  which is the fixed amount to be added to the current [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] that is required to reprice the bond to par. The discount margin measures the yield relative to the current [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and so does not take into account the term structure of interest rates.

The discount margin,  dm,  satisfies the following relation:

$$P=100+\sum_{i=1}^{n}{\frac{100 (q m-d m)/m}{(1+y_{i}+d m)^{i}}}$$

Where P is the price of the floating rate note (FRN) per $100 face value; qm is the quoted margin on FRN; dm is the discount margin; yi is the assumed value of the reference rate (LIBOR) in period i; n is the number of period until maturity; and m is the number of period per year.

The formula shows that if the quoted margin is equal to the discount margin,  then the second term is zero and the FRN is valued at par. If the current price of the floater differs from par,  then the discount margin is nonzero. The discount margin assumes that the cash flows over the remaining life of the bond are determined by the current reference rate value. The margin is selected so that the present value of the cash flows is equal to the security's price. The discount margin is a measure that is similar to yield-to-maturity for fixed rate instruments. It expresses the price of an FRN relative to the current [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] level.

See Fabozzi and Mann (2000).

## References

Acharya,  V.,  Gale,  D.,  Yorulmazer,  T.,  2009. Rollover Risk and Market Freezes. Unpublished Working Paper,  New York University,  New York.

Adrian,  T.,  Shin,  H.,  2008. [[Financial Markets and Institutions/III. Liquidity of Assets/Class 5- Private Information,    Liquidity,    and Securitization/Class 5- Private Information,    Liquidity,    and Securitization.md|Liquidity]],  [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]],  and financial cycles.

Current Issues in Economics and Finance 40,  1.

Afonso,  G.,  Kovner,  A.,  Schoar,  A.,  2010. Stressed,  Not Frozen: The Federal Funds Market in the Financial Crisis. Staff Report 437,  New York Federal Reserve Bank.

Almeida,  H.,  Campello,  M.,  Laranjeira,  B.,  2009. Corporate Debt Maturity and the Real Effects of the 2007 Credit Crisis,  Unpublished Working Paper,  University of Illinois.

Arora,  N.,  Gandhi,  P.,  Longstaff,  F.,  2009. Counterparty Credit Risk and the Credit Default Swap Market. Unpublished Working Paper,  University of California,  Los Angeles,  CA.

Association for Financial Professionals,  2006. AFP [[Financial Markets and Institutions/III. Liquidity of Assets/Class 5- Private Information,    Liquidity,    and Securitization/Class 5- Private Information,    Liquidity,    and Securitization.md|Liquidity]] Survey.

/ http://www.afponline.org/pub/pdf/2006LiquiditySurvey_1.pdfS.

Baba,  N.,  Packer,  F.,  2009. From Turmoil to Crisis: Dislocations in the Fx Swap Market before and after the Failure of Lehman Brothers. Working Paper 285,  Bank for International Settlements,  Basel,  Switzerland.

Bank for International Settlements,  1999. Implications of [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|Repo]] Markets for Central Banks,  Report of a Working Group Established by the Committee on the Global Financial System of the Central Banks of the Group of Ten Countries. March 9.

Bank for International Settlements,  2007. Institutional Investors,  Global Savings and [[Lecture 2- Asset Allocation with Multiple Risky Assets|asset allocation]]. Report Submitted by a Working Group Established by the Committee on the Global Financial System. February.

Bates,  T.,  Kahle,  K.,  Stulz,  R.,  2008. Why do US Firms Hold so Much More Cash than they Used to? Unpublished Working Paper,  Ohio State University.

Bond Market Association.,  2005. [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|Repo]] and Securities Lending Survey of US Markets Volume and Loss Experience. Research (January).

Brunnermeier,  M.,  Pedersen,  L.H.,  2009. Market [[Financial Markets and Institutions/III. Liquidity of Assets/Class 5- Private Information,    Liquidity,    and Securitization/Class 5- Private Information,    Liquidity,    and Securitization.md|liquidity]] and funding [[Financial Markets and Institutions/III. Liquidity of Assets/Class 5- Private Information,    Liquidity,    and Securitization/Class 5- Private Information,    Liquidity,    and Securitization.md|liquidity]]. Review of Financial Studies 22 (6),  2201–2238.

Calomiris,  C.W.,  1994. Is the discount window necessary? A Penn Central Perspective. Federal Reserve Bank of St. Louis Review 76 (May/June),

31–56.

Calomiris,  C.W.,  Himmelberg,  C.P.,  Wachtel,  P.,  1995. [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]] and corporate finance: a microeconomic perspective. CarnegieRochester Conference Series on Public Policy,  pp. 203–250.

Campello,  M.,  Giabona,  E.,  Graham,  J.,  Harvey,  C.,  2009. [[Financial Markets and Institutions/III. Liquidity of Assets/Class 5- Private Information,    Liquidity,    and Securitization/Class 5- Private Information,    Liquidity,    and Securitization.md|Liquidity]] Management and Corporate Investment during a Financial Crisis. Unpublished Working Paper,  Duke University,  Durham,  NC.

Carey,  M.,  Correa,  R.,  Kotter,  J.,  2009. Revenge of the Steamroller: ABCP as a Window on Risk Choices. Unpublished Working Paper,  Board of Governors of the Federal Reserve System,  Washington,  DC.

Carr,  P.,  Wu,  L.,  2006. A tale of two indices. The Journal of Derivatives Spring,  13–29.

Coffey,  N.,  Hrung,  W.,  Sarkar,  A.,  2009. Capital Constraints,  Counterparty Risk and Deviations from Covered Interest Rate Parity. Unpublished Working Paper,  New York Federal Reserve Bank,  New York.

Collin-Dufresne,  P.,  Goldstein,  R.,  Martin,  S.,  2001. The determinants of credit spread changes. Journal of Finance 56 (6),  2177–2207.

Corrigan,  D.,  de Tera´n,  N.,  2007. Collateral: Securities Lending,  [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|Repo]],  OTC

Derivatives and the Future of Finance. Global Custodian,  London.

Covitz,  D.,  Liang,  N. Suarez,  G.,  2009. The Evolution of a Financial Crisis:

Runs in the Asset-Backed [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]] Market. Unpublished Working Paper 2009-36,  Board of Governors of the Federal Reserve System,  Washington,  DC.

Dang,  T.V.,  Gorton,  G.B. Holmstrom,  B.,  2011. Ignorance and the Optim- ¨

Ality of Debt for [[Financial Markets and Institutions/III. Liquidity of Assets/Class 5- Private Information,    Liquidity,    and Securitization/Class 5- Private Information,    Liquidity,    and Securitization.md|Liquidity]] Provision. Unpublished Working Paper,  Yale University.

Eichengreen,  B.. Mody,  A. Nedeljkovic,  M. Sarno,  L.,  2009. How the Subprime Crisis went Global: Evidence from Bank Credit Default Swap Spreads. Working Paper 14904,  National Bureau of Economic Research.

Fabozzi,  F.,  Mann,  S.,  2000. Floating-Rate Securities. Wiley. Fegatelli,  P.,  2010. The Role of Collateral Requirements in the Crisis: One Tool for Two Objectives? Unpublished Working Paper,  Banque centrale du Luxembourg.

Fender,  I.,  Scheicher,  M.,  2009. The Pricing of Subprime Mortgage Risk in Good Times and Bad: Evidence from the ABX. HE Indices. Working Paper 279,  Bank of International Settlements,  Basel,  Switzerland.

Fishback,  P.,  Horrace,  W.,  Kantor,  S.,  2001. The Origins of Modern Housing Finance: The Impact of Federal Housing Programs during the Great Depression. Unpublished Working Paper,  University of Arizona,  Tucson,  AZ.

Foley,  C.F.,  Hartzell,  J.,  Titman,  S.,  Twite,  G.,  2006. Why do Firms Hold so Much Cash? A Tax-based Explanation. Working Paper 12649,  National Bureau of Economic Research,  Cambridge,  MA.

Fontana,  A.,  2009. The Persistent Negative CDS-bond Basis during the 2007/2008 Financial Crisis. Unpublished Working Paper. University Ca' Foscari,  Itlay,  Venice.

Geanakoplos,  J.,  2010. The leverage cycle. In: Acemoglu,  D.,  Rogoff,  K.,

Woodford,  M. (Eds.),  NBER Macroeconomics Annual 2009,  vol. 24. University of Chicago Press,  Chicago,  pp. 1–65.

Gorton,  G.,  2009. Information,  [[Financial Markets and Institutions/III. Liquidity of Assets/Class 5- Private Information,    Liquidity,    and Securitization/Class 5- Private Information,    Liquidity,    and Securitization.md|liquidity]],  and the (ongoing) panic of 2007. A.

American Economic Review Papers and Proceedings 99 (2),  567–572.

Gorton,  G.,  1985. Clearinghouses and the origin of central banking in the US. Journal of Economic History 45 (2),  277–283.

Gorton,  G.,  2010. Slapped by the Invisible Hand: The Panic of 2007.

Oxford University Press.

Gorton,  G.,  Huang,  L.,  2006. Banking panics and endogenous coalition formation. Journal of Monetary Economics 53 (7),  1613–1629.

Gorton,  G.,  Metrick,  A.,  2010. Regulating the shadow banking system.

Brookings Papers on Economic Activity (Fall),  261–297.

Gorton,  G.,  Mullineaux,  D.,  1987. The joint production of confidence:

Endogenous regulation and nineteenth century commercial bank clearinghouses. Journal of Money,  Credit and Banking 19 (4),

458–468.

Gorton,  G.,  Souleles,  N.,  2006. Special purpose vehicles [[Financial Markets and Institutions/III. Liquidity of Assets/Class 5- Private Information,    Liquidity,    and Securitization/Class 5- Private Information,    Liquidity,    and Securitization.md|and securitization]]. In: Stulz,  R.,  Carey,  M. (Eds.),  The Risks of Financial Institutions.

University of Chicago Press,  Chicago,  IL.

Gorton,  G.,  Pennacchi,  G.,  1995. Banks and loan sales: marketing nonmarketable assets. Journal of Monetary Economics 35 (3),  389–411.

Gorton,  G.,  Pennacchi,  G.,  1990. Financial intermediaries and [[Financial Markets and Institutions/III. Liquidity of Assets/Class 5- Private Information,    Liquidity,    and Securitization/Class 5- Private Information,    Liquidity,    and Securitization.md|liquidity]] creation. Journal of Finance 45 (1),  49–72.

Government Finance Officers Association (GFOA),  2001. Considerations for Governments in Developing a Master Repurchase Agreement,  third ed.

Gyntelberg,  J.,  Wooldridge,  P.,  2008. Interbank rate fixings during the recent turmoil. Bank for International Settlements Quarterly Review March,  59–72.

He,  Z.,  Xiong,  W.,  2009. Dynamic Debt Runs. Unpublished Working Paper,  Princeton University,  Princeton,  NJ.

He,  Z. Khang,  G. Krishnamurthy,  A.,  2010. Balance Sheet Adjustments during the 2008 Crisis. Unpublished Working Paper,  Northwestern University,  Kellogg Graduate School of Management.

Hordahl,  P.,  King,  M.,  2008. Developments in [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] markets during the ¨

Financial turmoil. Bank for International Settlements Quarterly Review (December),  37–53.

International Capital Market Association,  2010. European [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|repo]] market survey number 18-conducted December 2009.

Investment Company Institute,  2009. Report of the Money Market Working Group. March 17.

Iskandar-Datta,  M.,  Jia,  Y.,  2010. Why do Firms Hold so much Cash? The International Evidence. Unpublished Working Paper,  Wayne State University.

Ivashina,  V.,  Scharfstein,  D.,  2008. Bank Lending during the Financial Crisis of 2008. Unpublished Working Paper,  Harvard Business School,  Boston,  MA.

Johnson,  C.,  1997. Derivatives and rehypothecation failure: it's 3:00 p.m.,

Do you know where your collateral is? Arizona Law Review 30.

Kacperczyk,  M.,  Schnabl,  P.,  2010. When safe proved risky: [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]] during the financial crisis of 2007–2009. Journal of Economic Perspectives 24 (1),  29–50.

King,  M.,  2008. Are the brokers broken? New York. Citibank Global Markets Group.

Martin,  A.,  Skeie,  D.,  von Thadden,  E.L.,  2010. [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|Repo]] runs. Staff Report 444.

Federal Reserve Bank of New York,  New York.

Pagano,  M.,  Volpin,  P.,  2009. Securitization,  Transparency,  and [[Financial Markets and Institutions/III. Liquidity of Assets/Class 5- Private Information,    Liquidity,    and Securitization/Class 5- Private Information,    Liquidity,    and Securitization.md|Liquidity]].

Unpublished Working Paper.

Pinkowitz,  L.,  Stulz,  R.,  Williamson,  R.,  2006. Does the contribution of corporate cash holdings and dividends to firm value depend on governance? A cross-country analysis. Journal of Finance 61,  2725–2751.

Reinhart,  C.,  Rogoff,  K.,  2008. Is the 2007 US subprime financial crisis so different? An international historical comparison. American Economic Review 98,  339–344.

Report of Anton R. Valukas,  2010. In Re Lehman Brothers Holdings Inc.,

Et al. Debtors,  Chapter 11 Case No. 08-13555,  United States Bankruptcy Court,  Southern District of New York,  March 10.

Report of the Money Market Working Group,  2009. Submitted to the Board of Governors of the Investment Company Institute. March 17.

Schroeder,  J.,  2006. [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|Repo]] madness: the characterization of [[Class Note 12 Part 2 Repos|repurchase agreements]] under the [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] code and the U.C.C. Syracuse Law Review 46,  999–1050.

Schwarz,  K.,  2009. Mind the Gap: Disentangling Credit and [[Financial Markets and Institutions/III. Liquidity of Assets/Class 5- Private Information,    Liquidity,    and Securitization/Class 5- Private Information,    Liquidity,    and Securitization.md|Liquidity]] in Risk Spreads. Unpublished Working Paper,  University of Pennsylvania,  Wharton School,  Philadelphia,  PA.

Schweitzer,  L.,  Grosshandler,  S.,  Gao,  W.,  2008. Bankruptcy court rules that [[Class Note 12 Part 2 Repos|repurchase agreements]] involving mortgage loans are safe harbored under the [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] code,  but that servicing rights are not. Journal of Bankruptcy Law (May/June),  357–360.

Shleifer,  A.,  Vishny,  R.,  2009. Unstable Banking. Working Paper 14943,  National Bureau of Econmic Research,  Cambridge,  MA.

Singh,  M. Aitken,  J.,  2009. Counterparty Risk,  Impact on Collateral flows,  and Role for Central Counterparties. Working Paper 09/173,  International Monetary Funds,  Washington,  DC.

Singh,  M.,  Aitken,  J.,  2010. The (sizeable) Role of Rehypothecation in the Shadow Banking System,  Working Paper 10/172,  International Monetary Funds,  Washington,  DC.

Stanton,  R.,  Wallace,  N.,  2009. The Bear's Lair: Indexed Credit Default Swaps and the Subprime Mortgage Crisis. Unpublished Working Paper,  University of California,  Berkeley,  CA.

Stigum,  M.,  Crescenzi,  A.,  2007. Stigum's Money Market,         fourth ed.

McGraw Hill.

Task Force on Tri-Party [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|Repo]] Infrastructure,  2009. Payments Risk Committee,  Progress Report. December 22.

Task Force on Tri-Party [[Financial Markets and Institutions/III. Liquidity of Assets/Class 7- CP,    Repo,    and the Crisis/Class 7- CP,    Repo,    and the Crisis.md|Repo]] Infrastructure. 2010. Report. May 17.