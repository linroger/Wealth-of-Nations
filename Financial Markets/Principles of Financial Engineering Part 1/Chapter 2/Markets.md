---
tags:
  - '#central_clearing'
  - '#derivatives_markets'
  - '#euromarkets'
  - '#financial_regulation'
  - '#forward_contracts'
  - '#futures_contracts'
  - '#gfc_impact'
  - '#marking_to_market'
  - '#onshore_markets'
  - '#otc_markets'
---
# 2.2 MARKETS  

The first distinction is between local and Euromarkets. Local markets are also called onshore markets.   
These denote markets that are closely supervised by regulators such as central banks and financial reg-.   
ulatory agencies. There are basically two defining characteristics of onshore markets. The first is.   
reserve requirements that are imposed on onshore deposits. The second is the formal registration pro-.   
cess of newly issued securities. Both of these have important cost, liquidity, and taxation implications..  

In money markets, reserve requirements imposed on banks increase the cost of holding onshore deposits and making loans. This is especially true of the large "wholesale" deposits that banks and. other corporations may use for short periods of time. If part of these funds is held in a noninterest-. bearing form in central banks, the cost of local funds will increase..  

The long and detailed registration process imposed on institutions that are issuing stocks, bonds,. or other financial securities has two implications for financial engineering. First, issue costs will be higher in cases of registered securities when compared to simpler bearer form securities. Second, an issue that does not have to be registered with a public entity will disclose less information..  

Thus, markets where reserve requirements do not exist, where the registration process is. simpler, will have significant cost advantages. Such markets are called Euromarkets.  

# 2.2.1 EUROMARKETS  

We should set something clear at the outset. The term "Euro"' as utilized in this section does not refer to Europe, nor does it refer to the Eurozone currency, the Euro. It simply means that, in terms of reserve requirements or registration process we are dealing with markets that are outside the formal control of regulators and central banks. The two most important Euromarkets are the Eurocurrency market and the Eurobond market.'  

# 2.2.1.1 Eurocurrency markets  

Start with an onshore market. In an onshore system, a 3-month retail deposit has the following life. A client will deposit USD100 cash on date $T.$ This will be available the same day. That is to say, "days to deposit' will equal zero. The deposit-receiving bank takes the cash and deposits, say, $10\%$ of this in the central bank. This will be the required reserves portion of the original 100.? The. remaining 90 dollars are then used to make new loans or may be lent to other banks in the interbank overnight market.3 Hence, the bank will be paying interest on the entire 100, but will be receiving. interest on only 90 of the original deposit. In such an environment, assuming there is no other cost, the bank has to charge an interest rate around $10\%$ higher for making loans. Such supplementary costs are enough to hinder a liquid wholesale market for money where large sums are moved. Eurocurrency markets eliminate these costs and increase the liquidity. Let's briefly review the life of a Eurocurrency (offshore) deposit and compare it with an onshore deposit. Suppose a US bank deposits USD100 million in another US bank in the New York Eurodollar (offshore) market. Thus, as is the case for Eurocurrency markets, we are dealing only with banks, since this is an interbank market. Also, in this example, all banks are located in the United States. The Eurodeposit is made in the United States and the "money" never leaves the United States. This deposit becomes usable (settles) in 2 days-that is to say, days to deposit is 2 days. The entire USD100 million can now be lent to another institution as a loan. If this chain of transactions was happening in, say, London, the steps would be similar..  

# 2.2.1.2 Eurobond markets  

A bond sold publicly by going through the formal registration process will be an onshore instrument. If the same instrument is sold without a similar registration process, say, in London, and if it is a bearer security, then it becomes essentially an offshore instrument. It is called a Eurobond. Again the prefix "Euro' does not refer to Europe, although in this case the center of Eurobond activity happens to be in London. But, in principle, a Eurobond can be issued in Asia as well.4  

A Eurobond will be subject to less regulatory scrutiny, will be a bearer security, and will not be (as of now) subject to withholding taxes. The primary market will be in London. The secondary markets may be in Brussels, Luxembourg, or other places, where the Eurobonds will be listed. The settlement of Eurobonds will be done through Euroclear or Clearstream.  

# 2.2.1.3 Other Euromarkets  

Euromarkets are by no means limited to bonds and currencies. Almost any instrument can be marketed offshore. There can be Euro-equity, Euro-commercial paper (ECP), Euro medium-term note (EMTN), and so on. In derivatives, we have onshore forwards and swaps in contrast to offshore nondeliverable forwards and swaps.  

# 2.2.2 ONSHORE MARKETS  

Onshore markets can be organized over the counter or as formal exchanges. Over-the-counter. (OTC) markets have evolved as a result of spontaneous trading activity. An OTC market often has no formal organization, although it will be closely monitored by regulatory agencies and transactions may be carried out along some precise documentation drawn by professional organizations, such as ISDA and ICMA.5 Some of the biggest markets in the world are OTC. A good example is the interest rate swap (IRS) market, which has the highest notional amount traded among all financial markets with very tight bid-ask spreads. OTC transactions are done over the phone or electronically and the instruments contain a great deal of flexibility, although, again, institutions such as ISDA draw standardized documents that make traded instruments homogeneous.  

In contrast to OTC markets, organized exchanges are formal entities. Most exchanges now use. electronic trading, but some open-outcry exchanges with pits remain. The distinguishing character-. istic of an organized exchange is its formal organization. The traded products and trading practices. are homogeneous while, at the same time, the specifications of the traded contracts are less flexible.  

Stock markets are organized exchanges that deal in equities.' Futures and options markets. process derivatives written on various underlying assets. In a spot deal, the trade will be done and confirmed, and within a few days, called the settlement period, money and securities change hands.. In futures markets, on the other hand, the trade will consist of taking positions, and settlement will be after a relatively longer period, once the derivatives expire. The trade is, however, followed by depositing a "small' guarantee, called an initial margin (IM)..  

# 2.2.2.1 Futures and options exchanges  

CME Group (including CME, CBOT, NYMEX, COMEX), ICE (including ICE futures, Liffe futures, NYSE and Euronext), EUREX, National Stock Exchange of India, and BM/FBovespa are some of the major futures and options exchanges in the world.8 The exchange provides three important services:  

1. A physical location (i.e., the trading floor and the accompanying pits) for such activity, if it is a historical open-outcry system. Otherwise, the exchange will supply an electronic trading platform (such as CME's Globex). Such platforms use the internet as the underlying network. which implies that the location becomes less relevant. Many electronic trading platforms provide Application Programming Interfaces (APIs) that facilitate algorithmic trading.   
2. An exchange clearing house that becomes the real counterparty to each buyer and seller once the trade is done. A clearing house stands between two clearing firms (also known as member firms or clearing participants) and its purpose is to reduce the risk of one (or more) clearing. firm failing to honor its trade settlement obligations. Why does central clearing reduce risk compared to bilateral trading? In a bilateral trade, two parties A and B enter into an agreement. to exchange financial flows.? Each of the parties bears counterparty risk or the risk that the other party defaults and is unable to fulfill its obligations. In order to reduce such risks a central counterparty (CCP) approach can be used. The clearing house becomes the CCP by splitting the bilateral trade into two trades involving the CCP and party A and the CCP and party B, respectively. The offsetting positions imply that the CCP does not have any market risk but it. faces counterparty risk. A clearing house addresses the counterparty risk by requiring collateral deposits or margin payments from each of the counterparties. It reduces settlement risks by netting offsetting transactions between multiple counterparties. Other functions carried out by the clearning house that reduce risk involve providing independent valuation of trades and. collateral, monitoring the credit worthiness of the clearing firms, oftentimes, providing a guarantee fund that can be used to cover losses that exceed a defaulting clearing firm's. collateral on deposit.   
3. The service of creating and designing financial contracts that the trading community needs and, finally, providing a transparent and reliable trading environment. The mechanics of trading in futures (options) exchanges is as follows. Two traders trade.   
directly with each other according to their client's wishes. One sells, say, at 100; the other buys at.   
100. Then the deal ticket is signed and stamped.1o Until that moment, the two traders are each.   
other's counterparties. But once the deal ticket is stamped, the clearinghouse takes over as the.   
counterparty. For example, if a client has bought a futures contract for the delivery of 100 bushels  

of wheat, then the entity eventually responsible (they have agents) for delivering the wheat is not the "other side' who physically sold the contract on the pit, but the exchange clearinghouse. By being the only counterparty to all short and long positions, the clearinghouse will lower the counterparty risk dramatically.11 The counterparty risk is actually reduced further, since the clearinghouse will deal with clearing members, rather than the traders directly.'2 The open interest in futures exchanges is the number of outstanding futures contracts. It is obtained by totaling the number of short or long positions that have not yet been closed out by delivery, cash settlement, or offsetting long/short positions.  

# 2.2.2.2 Futures compared with forward contracts  

Forwards are OTC contracts, designed according to the needs of the clients and negotiated between two counterparties. They are easy to price and almost costless to purchase. Futures are different from forward contracts in this respect. Some of the differences are minor; others are more important, leading potentially to significantly different forward and futures prices on the same underlying. asset with identical characteristics. Most of these differences come from the design of futures contracts. Futures contracts need to be homogeneous to increase liquidity. The way they expire and the. way deliveries are made will be clearly specified, but will still leave some options to the players.. Forward contracts are initiated between two specific parties. They can state exactly the delivery and expiration conditions. Futures, on the other hand, will leave some room for last-minute adjustments and these "options"' may have market value..  

We consider two contracts in order to review the main parameters involved in the design of a. futures and contrast it with forward contracts. The key point is that most aspects of the transaction need to be pinned down to make a homogeneous and liquid contract. This is relatively easy and straightforward to accomplish in the case of a relatively standard commodity such as soybeans.. Consider the following soybeans futures contract.13  

# EXAMPLE: CBOT (CME GROUP) SOYBEANS FUTURES  

1. Contract size. 5000 bushels $\mathord{\sim}136$ metric tons).  

2. Deliverable grades. No. 2 yellow at par, No. 1 yellow at 6 cents per bushel over contract price, and No. 3 yellow at 6 cents per bushel under contract price. (Note that in case a trader accepts the delivery, a special type of soybeans will be delivered to him or her. The trader may, in fact, procure the same quantity under better conditions from someone else. Hence, with a large majority of cases, futures contracts do not end with delivery. Instead, the position is unwound with an opposite transaction sometime before expiration.)  

3. Tick size. Quarter-cent/bushel (\$12.50/contract).  

4. Price quote. Cents and quarter-cent/bushel.  

5. Contract months. January, March, May, July, August, September, and November.. (Clearly, if the purpose behind a futures transaction is delivery, then forward contracts. with more flexible delivery dates will be more convenient.) On June 23, 2014, the most distant contract month available was November 2015.   
6. Last trading day. The business day prior to the 15th calendar day of the contract month..   
7. Last delivery day. Second business day following the last trading day of the delivery month.   
8. Trading hours. Open outcry: 9:30 a.m. to. $1{:}15\mathrm{p.m}$ . Chicago time, Monday throughe Friday. Electronic,. $8{:}30~\mathrm{p.m}$ . to $6{:}00~\mathrm{a.m}$ . Chicago time, Sunday through Friday. Trading. in expiring contracts closes at noon on the last trading day..   
9. Daily price limit. 50 cents/bushel $\$2300/0$ ontract) above or below the previous day's. settlement price. No limit in the spot month. (Limits are lifted two business days before the spot month begins.)  

An important concept that needs to be reviewed concerning futures markets is the process of marking to market. When one "buys"' a futures contract, a margin is put aside, but no cash payment is made. This leverage greatly increases the liquidity in futures markets, but it is also risky. To make sure that counterparties realize their gains and losses daily, the exchange will reevaluate positions every day using the settlement price observed at the end of the trading day.  

# EXAMPLE  

A soybeans futures contract has a price of $\$1470.2$ on day $T.$ At the end of day $T+1$ , the settlement price is announced as $\$1469.4$ . The price fell by 80 cents, and this is a loss to the long position holder. The position will be marked to market, and the clearinghouse- or more correctly the clearing firm-will lower the client's balance by the corresponding amount.  

The above example illustrates one of the differences between futures and forwards. Futures contracts are always marked to market, whereas this requirement does not apply to all forwards, as we explain below.  

We consider the cash flows generated by a futures contract and compare them with the cash flows on a forward contract on the same underlying. It turns out that, unlike forwards, the effective maturity of a futures position is, in fact, 1 day. This is due to the existence of marking to market. in futures trading. The position will be marked to market in the sense that every night the. exchange will, in effect, close the position and then reopen it at the new settlement price. It is best to look at this with a precise example. Suppose a futures contract is written on one unit of a commodity with spot price $S_{t}$ Let $F_{t}$ be the futures price quoted in the exchange. Suppose. $t$ is a  

![](c236d86ff76f52629fe2ef75b011dcffd73babfa6b6fef918cac6aed5725f2f4.jpg)  

# FIGURE 2.1  

Marking to market.  

Tuesday (March 11, 2014, for example), and that the expiration of the contract is within 3 trading days, that is on Friday, March 14, 2014:  

$$
T=t+3
$$  

where $T=$ March 11, 2014 and $t=\mathbf{M}$ arch 14, 2014. Suppose further that during these days, the settlement prices follow the trajectory.  

$$
F_{t}(=\S1470.2)>F_{t+1}(=\S1469.4)>F_{t+2}(=\S1468.4)=F_{t+3}(=\S1468.4)
$$  

where $t=\mathbf{M}$ arch 11, 2014, $t+1=\mathbf{M}$ arch 12, 2014, $t+2=\mathbf{M}$ arch 13, 2014, and $t+3=\mathrm{March14}$ 2014. What cash flows will be generated by a long position in one futures contract if at expiration date $T$ the position is closed by taking the offsetting position?15  

The answer is shown in Figure 2.1. Marking to market is equivalent to forcing the long (short). position holder to close his position at that day's settlement price and reopen it again at the same. price. Thus, at the end of the first trading day after the trade, the futures contract that was "purchased" at $f_{t}$ will be "sold' at the $f_{t+1}$ shown in Eq. (2.2) for a loss:  

$$
F_{t+1}-F_{t}=1469.4-1470.2=-0.8<0
$$  

Similarly, at the end of the second trading day, marking to market will lead to another loss:  

$$
F_{t+2}-F_{t+1}=1468.4-1469.4=-1.0{<}0
$$  

This is the case since, according to trajectory in Eq. (2.2), prices have declined again. The expiration date will see no further losses, since, by chance, the final settlement price is the same as the previous day's settlement.  

In contrast, the last portion of Figure 2.1 shows the cash flows generated by the forward prices $F_{t}$ . Since there is no marking to market (in this case), the only capital loss occurs at the expiration. of the contract. Clearly, this is a very different cash flow pattern. Marking to market may signifi-. cantly alter the implied cash flows and result in some moderate convexities.  

Interest rate futures are some of the most liquid futures. The following example illustrates the typical quoting convention for interest futures. The futures price is quoted as 100 minus the interest rate. This implies that a falling interest rate futures price indicates a rise in the underlying interest rate.  

# EXAMPLE: LIFFE 3-MONTH EURIBOR INTEREST RATE FUTURES  

1. Unit of trading. 1,000,000..   
2. Delivery months. January, February, March, April, May, June, July, August, September,. October, November, and December. December 2019 is the last contract month available for trading, as of April 24, 2014..   
3. Price quotes. 100 minus rate of interest. (Based on the European Bankers Federations'. Euribor Offered Rate (EBF Euribor) for 3-month Euro deposits at 11.00 Brussels time (10:00 London time) on the Last Trading Day. The settlement price will be 100.00 minus the EBF Euribor Offered Rate rounded to three decimal places.)   
4. Minimum price movement. (Tick size and value) 0.005 (12.50)..   
5. Last trading day. 10.o0-Two business days prior to the third Wednesday of the. delivery month.   
6. Delivery day. First business day after the last trading day.   
7. Trading hours. 01:00-06:45, 07:0021:00.   
8. Clearing. ICE Clear Europe Limited..  

Eurocurrency futures contracts will be discussed in the next chapter and will be revisited several times later. In particular, one aspect of the contract that has not been listed among the parameters noted here has interesting financial engineering implications. Eurocurrency futures have a quotation convention that implies a linear relationship between the forward interest rate and the price of the futures contract. This is another example of the fact that conventions are indeed important in finding the right solution to a financial engineering problem.  

Although, for simplicity, we assume in some of the financial engineering applications in this book that forward contracts are costless to enter, this is not the case in reality since forward contracts and other OTC derivatives require the posting of collateral. However, there are some subtle differences in collateral requirements between forward and futures contracts. First, according to the latest BCBS-IOsCO guidelines, financial and nonfinancial counterparties will be required to exchange variation margin (VM) for all new contracts entered into after December 1, 2015, and two-way IM in several phases starting in December 2015.17 This requirement also applies to derivatives that are not centrally cleared, including certain forward contracts. There are exemptions for physically settled FX OTC derivatives which require VM, but not IM..  

Second, there are differences in interest payments on the collateral in OTC and exchange-traded markets. Exchange-traded futures are settled daily and requirement daily margin that does not earn interest. If OTC forwards are cleared through a CCP or bilaterally, interest is paid on the VM if it is held in the form of cash.  

# 2.2.3 CHANGES TO THE INFRASTRUCTURE OF DERIVATIVES MARKETS FOLLOWING THE GFC  

Prior to the financial crisis, many derivatives contracts such as IRSs were mostly traded OTC and were often not centrally cleared. Oftentimes, OTC derivative contracts were not standardized and trade repositories did not exist for contracts such as credit default swaps, for example. In the years following, the GFC regulation has been implemented that saw a move towards central clearing, exchange trading, standardization and trade repositories for an increasing number of derivative contracts.  

In September 2009, the G20 set an objective of introducing mandatory clearing for standardized derivatives, including OTC IRSs. The United States (through Dodd-Frank), the European Union (through EMIR), and other jurisdictions in the G20 developed and implemented regulations to achieve this objective. US regulations are driving reporting, clearing and settlement functions to much more tightly regulated Swap Execution Facilities (SEFs).18 LCH.Clearnet cleared $\$282.6$ trillion in notional amount of IRSs and $\$446.1$ billion in cleared nondeliverable FX forwards volume in 2013. ICE Clear Credit's annual cleared CDS volume rose to $\$7.7$ trilllion in 2013.19  

In Europe, the derivatives market infrastructure is defined and supervised by the European Securities and Markets Authority (ESMA) under the European Markets Infrastructure Regulation (EMIR) regulation. Following the Dodd-Frank Act, the US Commodity Futures Trading Commission (CFTC) has developed the regulation, under which Swap Data Repositories are regulated.  

The hope is that recent regulation and moving most privately negotiated, bilateral contracts in. the OTC market to central clearing and requiring real-time trade reporting will allow regulators to. see the volume of contracts trading in the market, to assess the trading activity in different asset classes, to monitor derivatives trading data and thus, to oversee risk exposures and reduce systemic risk in the derivatives market. From a financial engineering perspective, the effect of regulatory changes is of great importance. Regulation affects margin and funding costs of different derivatives instruments and strategies. It affects the profitability and permissibility of certain structured products and trades. In later chapters, we will discuss the effect of recent regulation on financial engineering practice in different asset classes.  
