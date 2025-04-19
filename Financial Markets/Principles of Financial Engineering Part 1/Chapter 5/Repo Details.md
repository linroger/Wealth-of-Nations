---
tags:
  - collateral
  - financial_engineering
  - repo_dealer
  - repo_market
  - repurchase_agreement
aliases:
  - repo operation
  - repurchase
  - reverse repo
key_concepts:
  - cheap funding
  - repo definition
  - repo terminology
  - repo transaction sequence
  - shorting securities
---

# 5.2 REPO DETAILS  

We begin with the standard definition. As Figure 5.1 showed, a repo is a repurchase agreement. where a repo dealer sells a security to a counterparty and simultaneously agrees to buy it back at a predetermined price and at a predetermined date. Thus, it is a sale and a repurchase written on the same ticket. In other words, a repo is legally recognized as a single transaction and not as a disposal and a repurchase for tax purposes.2  

# 5.2.1 REP0 TERMINOLOGY  

To avoid any confusion, it is important to learn the naming conventions used in repo markets. In repo markets, most of the terminology is set from the point of view of the repo dealer. Also, words such as "borrowing"' and "lending' are used as if the item that changes hands is not cash, but a. security such as a bond or equity. In particular, the terms "lender' or "borrower' are determined by. the lending and borrowing of a security and not of "cash'-although in the actual exchange, cash. is changing hands. How can we apply these concepts to Figure 5.1? In Figure 5.1, the collateral seller was the lender and the collateral buyer was the borrower (of the security).  

Accordingly, in a repo transaction where the security is first delivered to a client and cash is received, the repo dealer is the "lender'-he or she lends the security and gets cash. This way, the. repo dealer has raised cash. If, on the other hand, the same operation was initiated by a client and. the counterparty was a repo dealer, the deal becomes a reverse repo, or is simply referred to as. reverse. The dealer is borrowing the security, the reverse of what happens in a repo operation..  

At first glance, the repo operation looks like a fairly simple transaction that would not contribute to the methodology of financial engineering. This is not true. In fact, in terms of practical applications of financial engineering repo may be as common as swaps.  

Consider the following example. Suppose an investor wants to buy a security using short-term funding. If he borrows these funds from a bank and then goes to another dealer to buy the bond, the original loan will be nonsecured. This implies higher interest costs. Now, if the investor uses repo by buying first, and then repoing the security, he can get the needed funds cheaper because there will be collateral behind the "loan." As a result, both the transaction costs and the interest rate will be lower. In addition, transactions are grouped and written on a single ticket. Given the lower risks, higher flexibility, and other conveniences, repo transactions are very liquid and practical.  

With a repo, the sequence of transactions changes. In a typical outright purchase a market professional would  

Secure funds $\rightarrow$ Pay for the security $\rightarrow$ Receive the security  

When repo markets are used for buying a security, the sequence of transactions becomes:  

In this case, the repo market is used for finding cheap funding for the purchases the practitioner. needs to make. The bond is used as collateral. If this is a default-free security, borrowed funds will come with a relatively low repo rate.  

Similarly, shorting securities also become possible. The market participant will use the repc market and go through the following steps:  

Deliver the cash and borrow the bond. $\rightarrow$ Return the bond and receive cash plus interest  

The market practitioner will earn the repo rate while borrowing the bond. This is equivalent to the market practitioner holding a short-term bond position. The bond is not purchased, but it is. "leased."  

# 5.2.2 SPECIAL VERSUS GENERAL COLLATERAL  

Repo transactions can be classified into two categories. Sometimes, specific securities receive special attention from markets. For example, some bonds become cheapest-to-deliver (CTD). The "shorts" who promised delivery in the bond futures markets are interested in a particular bond and not in others that are similar. This particular bond becomes very much in demand and goes special in the repo markets. A repo transaction that specifies the particular security in detail is called a special repo. The security remains special as long as the relative scarcity persists in the market.  

Otherwise, in a repo deal, the party that lends the securities can lend any security of a similar. risk class. This type of security is called general collateral. One party lends US government bonds against cash, and the counterparty does not care about the particular bonds this basket contains. Then the collateral could be any Treasury bond..  

The special security will have a higher price than its peers, as long as it remains special. This means that to borrow this security, the client gives up his or her cash at a lower interest rate. After all, the client really needs this particular bond and will therefore have to pay a "price"--agreeing. to a lower repo rate.  

The interest rate for general collateral is called the repo rate. Specials command a repo rate that. is significantly lower. In this case, the cash can be relent at a higher rate via a general repo and the original owner of the "special"' benefits.  

# EXAMPLE  

Suppose repo rate quotes are $4.5{-}4.6\%$ . You own a bond worth UsD100, which by chance. goes special the next day. You can lend your bond for, say, UsDio0, and get cash for 1 week and pay only. $2.5\%$ . This is good, since you can immediately repo this sum against general collateral and earn an annual rate of $4.5\%$ on the 100. You have earned an enhanced. return on your bond because you just happened to hold something special..  

When using bond market data in research, it is important to take into account the existence of specials in repo transactions. If "repo specials" are mixed with transactions dealing with general collateral, the data may exhibit strange variations and may be quite misleading. This point is quite relevant since about $20\%$ of repo transactions involve specials.  

# 5.2.2.1 Why do bonds go special?  

There are at least two reasons why some securities go special systematically. For one, some bonds are. cheapest-to-deliver (CTD) in bond futures trading (see the case study at the end of this chapter). The. second reason is that on-the-run issues are more liquid and are therefore more in demand by traders in order to support hedging and position-taking activities. Such "benchmark' bonds often go special. This is somewhat paradoxical, as the more liquid bonds become the more expensive they are to obtain rela-. tive to others.3  

As an example, consider the so-called butterfly trades in the fixed-income sector. Nonparallel. shifts that involve the belly of the yield curve are sometimes called butterfly shifts. These shifts may. have severe implications for balance sheets and fixed-income portfolios. Traders use 2-510-year on-the-run bonds to put together hedging trades, to guard, or speculate against such yield curve. movements. These trades are called butterfly trades. The on-the-run bonds used in such strategies may become "benchmarks" and may go special.  

# 5.2.3 SUMMARY  

We can now summarize the discussion. What are the advantages of repo transactions?  

1. A repo provides double security when lending cash. These are the (high) credit rating of a repc dealer and the collateral.   
2. A "special"' repo is a unique and convenient way to enhance returns.   
3. By using repo markets, traders can short the market and raise funding efficiently. This improves general market efficiency and trading.   
4. Financial strategies and product structuring will benefit due to lower transaction costs, more efficient use of time, and lower funding costs.  

We now consider various types of repo or repo-type transactions.  
