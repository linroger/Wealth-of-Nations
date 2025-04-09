# 5.8 CONCLUSIONS  

The basic concepts underlying repo markets are simple, but due to the fact that repos are dominated by institutions, knowledge about repo markets is not widespread compared to other aspects of financial engineering. Yet, repo markets are crucial for the smooth operation of financial systems. Many financial strategies would be difficult to implement if it weren't for the repo. This chapter has shown that repos can be analyzed with the same techniques discussed in earlier chapters..  

# SUGGESTED READING  

Relatively few sources are available on repos, but the ones that exist are good. One good text is Steiner (2012). Risk, Euromoney, and similar publications have periodic supplements that deal with repo. These supplements contain interesting examples in terms of recent repo market strategies. Many of the examples in this chapter are taken from such past supplements. Repo markets differ between countries. For an introduction to Equity Repos, see Choudhry (2010).  

# EXERCISES  

1. Suppose you are a newly employed investment banker and you find that your bank got stuck in a deal where it has to deliver a bond to close a short future position. The bond has just gone "special' and you do not own it yet. What strategy do you suggest to address this situation and avoid a heavy penalty in case of failure to deliver?   
2. A dealer needs to borrow EUR 30 million. He uses a Bund as collateral. The Bund has the following characteristics: Collateral $4.3\%$ Bund, June 12, 2004 Price: 100.50 Start date: September 10 Term: 7 days Repo rate: $2.7\%$ Haircut: $0\%$ a. How much collateral does the dealer need? b. Two days after the start of the repo, the value of the Bund increases to 101. How much of the securities will be transferred to whom? c.What repo interest will be paid?.  

3. A dealer repos $\$10$ million T-bills. The haircut is $5\%$ . The parameters of the deal are as follows:  

T-bill yield:. $2\%$ Maturity of T-bills: 90 days Repo rate: $2.5\%$ term: 1 week   
a. How much cash does the dealer receive?   
b. How much interest will be paid at the end of the repo deal?  

4. A dealer wants to borrow $\$10$ million using a bond repo but due to certain market restriction he cannot repo out the bond for 2 months. a. Suggest a strategy so that he can borrow the cash for the period without losing the permanent ownership of the bond. b. Calculate the forward price of bond trading at $\$43.59$ if the current repo rate is $4\%$ p.a.  

5. Answer the questions related to the following case study:  

# CASE STUDY: CTD AND REPO ARBITRAGE  

Two readings follow. Please read them carefully and answer the questions that follow. You may have to first review three basic concepts: (i) special repo versus general collateral, (ii) the notion of CTD bonds, and (ii) failure to deliver. You must understand these well, otherwise the following strategies will not make sense.  

# Readings  

DB Bank is believed to have pocketed over EUR100 million (UsD89.4 million) after reportedly squeezing repo traders in a massive interest-rate futures position. The bank was able to take advantage of illiquidity in the cheapest-to-deliver bond that would have been used to settle a long futures position it entered, in a move that drew sharp criticism from some City rivals.  

In the trade, the Bank entered a calendar spread in which it went long the Eurex-listed BOBL March'01. future on German medium-term government bonds and sold the June'01 contract to offset the long position, said traders familiar with the transaction. One trader estimated the Bank had bought 145,000 March'01 contracts. and sold the same number of June'01 futures. At the same time the Bank built up a massive long position via the. repo market in the cheapest-to-deliver bond to settle the March future, in this case a 10-year Bund maturing in October 2005.  

Since the size of the '05 Bund issue is a paltry EUR10.2 billion, players short the March future would have. needed to round up $82\%$ of the outstanding bonds to deliver against their futures obligations. "It is almost. inconceivable that this many of the Bunds can be delivered," said a director-derivatives strategy in London. "Typically traders would be able to rustle up no more than $25\%$ of a cheapest-to-deliver bond issue," he added  

At the same time it was building the futures position, the Bank borrowed the cheapest-to-deliver bonds in size via the repo market. Several traders claim the Bank failed to return the bonds to repo players by the agreed term, forcing players short the March future to deliver more expensive bonds or else buy back the now more. expensive future.  

The Bank was able to do this because penalties for failure to deliver in the repo market are less onerous than those governing failure to deliver on a future for physical delivery. Under Eurex rules, traders that fail to deliver on a future must pay 40 basis points of the face value of the bond per day. After a week the exchange is entitled to buy any eligible bond on behalf of the party with the long futures position and send the bill to the player with the short futures position, according to traders. Conversely, the equivalent penalty for failure to deliver in the repo market is 1.33 bp per day.  

(Thomson Reuters IFR, March 2001).  

Eurex Reforms Bobl Future Eurex is introducing position limits for its September contracts in its two-, five-, and 10-year German government bond futures. "If we want, we will do it in December as well," said a spokesman for the exchange. The move is aimed at supporting the early transfer of open positions to the next trading cycle and is a reaction to the successful squeeze of its Bundesobligation (Bobl) or five-year German government bond futures contract in March.  

"The new trading rules limit the long positions held by market participants, covering proprietary and customer trading positions," said Eurex's spokesman. Position limits will be set in relation to the issue size of the cheapest-to-deliver bond and will be published six exchange trading days before the rollover period begins.  

(Thomson Reuters IFR, June 9, 2001).  

# Part A. First Reading  

What is a calendar spread? Show DB's position using cash flow diagram   
2. Put this together with DB's position in the repo market..   
3.What is DB's position aiming for?   
4. What is the importance of the size of. $\mathrm{'05}$ Bund issue? How do traders "rustle up" such bonds to be delivered?.   
5. Why are penalties for failure to deliver relevant?   
6. Would an asset swap (e.g., swapping LIBOR against the relevant bond mentioned in the paper) have helped the shorts? Explain.   
7. Could taking a carefully chosen position in the relevant maturity FRA, offset the losses that shorts have suffered? Explain carefully.   
8. Explain how CTD bonds are determined. For needed information go to Web sites of futures exchanges.  

# Part B. Second Reading  

1. Eurex has made some changes in the Bund futures trading rules. What are these?   
2. Suppose these rules had been in effect during March, would they have prevented DB's arbitrage position?   
3. Would there be ways DB can still take such a position? What are they?  

This page intentionally left blank  

# CASH FLOW ENGINEERING IN FOREIGN EXCHANGE MARKETS  

# 6  

# HAPTER OUTLINE  

5.1 Introduction. 176   
5.2 Currency Forwards . 178   
6.2.1 Engineering the Currency Forward. 180   
6.2.2 Which Synthetic? .. 180   
6.2.2.1 A money market synthetic . .180   
6.2.2.2 A synthetic with T-bills 182   
6.2.2.3 Which synthetic should one use?. .182   
6.2.2.4 Credit risk . .183   
5.3 Synthetics and Pricing .183   
5.4 A Contractual Equation. 184   
5.5 Applications ... .185   
6.5.1 Application 1: A Withholding Tax Problem . 185   
6.5.2 Application 2: Creating Synthetic Loans . 187   
6.5.3 Application 3: Capital Controls . 189   
6.5.4 Application 4: "Cross" Currencies. 189   
5.6 Conventions for FX Forward and Futures. 191   
6.6.1 Quoting Conventions for FX Forward.. 191   
6.6.2 FX Forward Versus FX Futures. 194   
6.7 Swap Engineering in FX Markets.. .194   
6.7.1 FX Swaps. 194   
6.7.1.1 Advantages. .195   
6.7.1.2 Uses of FX swaps. .196   
6.7.1.3 Quotation conventions. .197   
6.8 Currency Swaps Versus FX Swaps.. 198   
6.8.1 Currency Swaps... 198   
6.8.2 Differences Between Currency Swaps and FX Swaps... . 200   
6.8.3 Another Difference . 202   
6.8.4 Uses of Currency Swaps.. . 202   
6.8.5 Relative Size and Liquidity of FX Swap and Currency Swap Markets. 202   
6.8.6 The Effect of the GFC on the FX Market, Margins, and Clearing. . 203   
6.9 Mechanics of Swapping New Issues. 204   
6.9.1 Interest Rate and Currency Swap Example. 204   
6.10 Conclusions... .206   
Suggested Reading .. .207   
Exercises .. . 207  
