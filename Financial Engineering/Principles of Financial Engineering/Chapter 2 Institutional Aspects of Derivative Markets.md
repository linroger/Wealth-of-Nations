# INSTITUTIONAL ASPECTS OF DERIVATIVE MARKETS  

# 2  

# CHAPTER OUTLINE  

2.1 Introduction .. 26   
2.2 Markets.. 26   
2.2.1 Euromarkets. 27   
2.2.1.1 Eurocurrency markets .27   
2.2.1.2 Eurobond markets . .27   
2.2.1.3 Other Euromarkets .. .28   
2.2.2 Onshore Markets .. 28   
2.2.2.1 Futures and options exchanges . .29   
2.2.2.2 Futures compared with forward contracts.. .30   
2.2.3 Changes to the Infrastructure of Derivatives Markets Following the GFC . 34   
2.3 Players.. . 35   
2.4 The Mechanics of Deals ... . 36   
2.4.1 Orders .. . 37   
2.4.2 Confirmation and Settlement.. . 38   
2.4.2.1 Regulatory update following the GFC. .39   
2.5 Market Conventions 39   
2.5.1 What to Quote ... . 40   
2.6 Instruments.. . 41   
2.7 Positions . 41   
2.7.1 Long and Short Positions 41   
2.7.1.1 Payoff diagrams . 42   
2.7.1.2 Real-world complications and short selling . .44   
2.7.2 Payoff Diagrams for Forwards and Futures .. 45   
2.7.3 Types of Positions.. 49   
2.7.3.1 Arbitrage . .49   
2.7.3.2 Comparing performance .. .50   
2.8 The Syndication Process . . 50   
2.8.1 Selling Securities in the Primary Market . 50   
2.8.1.1 Syndication of a bond versus a syndicated loan... .51   
2.9 Conclusions. 51   
Suggested Reading 51   
Exercises . 51  

# 2.1 INTRODUCTION  

This chapter takes a step back and reviews in a nutshell the prerequisite for studying the methods of financial engineering. Readers with a good grasp of the conventions and mechanics of financial markets may skip it, although a quick reading would be preferable.  

Financial engineering is a practice and can be used only when we define the related environment carefully. The organization of markets, and the way deals are concluded, confirmed, and carried out, are important factors in selecting the right solution for a particular financial engineering problem. This chapter examines the organization of financial markets and the way market practitioners interact. Issues related to settlement, to accounting methods, and especially to conventions used by market practitioners are important and need to be discussed carefully.  

In fact, it is often overlooked that financial practices will depend on the conventions adopted by a particular market. This aspect, which is relegated to the background in most books, will be an important parameter of our approach. Conventions are not only important in their own right for proper pricing, but they also often reside behind the correct choice of theoretical models for analyzing pricing and risk management problems. The way information is provided by markets is a factor in determining the model choice. While doing this, the chapter introduces the mechanics of the markets, instruments, and who the players are. A brief discussion of the syndication process is also provided.  

# 2.2 MARKETS  

The first distinction is between local and Euromarkets. Local markets are also called onshore markets. These denote markets that are closely supervised by regulators such as central banks and financial regulatory agencies. There are basically two defining characteristics of onshore markets. The first is reserve requirements that are imposed on onshore deposits. The second is the formal registration process of newly issued securities. Both of these have important cost, liquidity, and taxation implications.  

In money markets, reserve requirements imposed on banks increase the cost of holding onshore deposits and making loans. This is especially true of the large “wholesale” deposits that banks and other corporations may use for short periods of time. If part of these funds is held in a noninterestbearing form in central banks, the cost of local funds will increase.  

The long and detailed registration process imposed on institutions that are issuing stocks, bonds, or other financial securities has two implications for financial engineering. First, issue costs will be higher in cases of registered securities when compared to simpler bearer form securities. Second, an issue that does not have to be registered with a public entity will disclose less information.  

Thus, markets where reserve requirements do not exist, where the registration process is simpler, will have significant cost advantages. Such markets are called Euromarkets.  

# 2.2.1 EUROMARKETS  

We should set something clear at the outset. The term “Euro” as utilized in this section does not refer to Europe, nor does it refer to the Eurozone currency, the Euro. It simply means that, in terms of reserve requirements or registration process we are dealing with markets that are outside the formal control of regulators and central banks. The two most important Euromarkets are the Eurocurrency market and the Eurobond market.1  

# 2.2.1.1 Eurocurrency markets  

Start with an onshore market. In an onshore system, a 3-month retail deposit has the following life. A client will deposit USD100 cash on date $T.$ This will be available the same day. That is to say, “days to deposit” will equal zero. The deposit-receiving bank takes the cash and deposits, say, $10\%$ of this in the central bank. This will be the required reserves portion of the original 100.2 The remaining 90 dollars are then used to make new loans or may be lent to other banks in the interbank overnight market.3 Hence, the bank will be paying interest on the entire 100, but will be receiving interest on only 90 of the original deposit. In such an environment, assuming there is no other cost, the bank has to charge an interest rate around $10\%$ higher for making loans. Such supplementary costs are enough to hinder a liquid wholesale market for money where large sums are moved. Eurocurrency markets eliminate these costs and increase the liquidity. Let’s briefly review the life of a Eurocurrency (offshore) deposit and compare it with an onshore deposit. Suppose a US bank deposits USD100 million in another US bank in the New York Eurodollar (offshore) market. Thus, as is the case for Eurocurrency markets, we are dealing only with banks, since this is an interbank market. Also, in this example, all banks are located in the United States. The Eurodeposit is made in the United States and the “money” never leaves the United States. This deposit becomes usable (settles) in 2 days—that is to say, days to deposit is 2 days. The entire USD100 million can now be lent to another institution as a loan. If this chain of transactions was happening in, say, London, the steps would be similar.  

# 2.2.1.2 Eurobond markets  

A bond sold publicly by going through the formal registration process will be an onshore instrument. If the same instrument is sold without a similar registration process, say, in London, and if it is a bearer security, then it becomes essentially an offshore instrument. It is called a Eurobond. Again the prefix “Euro” does not refer to Europe, although in this case the center of Eurobond activity happens to be in London. But, in principle, a Eurobond can be issued in Asia as well.4  

A Eurobond will be subject to less regulatory scrutiny, will be a bearer security, and will not be (as of now) subject to withholding taxes. The primary market will be in London. The secondary markets may be in Brussels, Luxembourg, or other places, where the Eurobonds will be listed. The settlement of Eurobonds will be done through Euroclear or Clearstream.  

# 2.2.1.3 Other Euromarkets  

Euromarkets are by no means limited to bonds and currencies. Almost any instrument can be marketed offshore. There can be Euro-equity, Euro-commercial paper (ECP), Euro medium-term note (EMTN), and so on. In derivatives, we have onshore forwards and swaps in contrast to offshore nondeliverable forwards and swaps.  

# 2.2.2 ONSHORE MARKETS  

Onshore markets can be organized over the counter or as formal exchanges. Over-the-counter (OTC) markets have evolved as a result of spontaneous trading activity. An OTC market often has no formal organization, although it will be closely monitored by regulatory agencies and transactions may be carried out along some precise documentation drawn by professional organizations, such as ISDA and ICMA.5 Some of the biggest markets in the world are OTC. A good example is the interest rate swap (IRS) market, which has the highest notional amount traded among all financial markets with very tight bid-ask spreads. OTC transactions are done over the phone or electronically and the instruments contain a great deal of flexibility, although, again, institutions such as ISDA draw standardized documents that make traded instruments homogeneous.  

In contrast to OTC markets, organized exchanges are formal entities. Most exchanges now use electronic trading, but some open-outcry exchanges with pits remain.6 The distinguishing characteristic of an organized exchange is its formal organization. The traded products and trading practices are homogeneous while, at the same time, the specifications of the traded contracts are less flexible.  

Stock markets are organized exchanges that deal in equities.7 Futures and options markets process derivatives written on various underlying assets. In a spot deal, the trade will be done and confirmed, and within a few days, called the settlement period, money and securities change hands. In futures markets, on the other hand, the trade will consist of taking positions, and settlement will be after a relatively longer period, once the derivatives expire. The trade is, however, followed by depositing a “small” guarantee, called an initial margin (IM).  

# 2.2.2.1 Futures and options exchanges  

CME Group (including CME, CBOT, NYMEX, COMEX), ICE (including ICE futures, Liffe futures, NYSE and Euronext), EUREX, National Stock Exchange of India, and BM/FBovespa are some of the major futures and options exchanges in the world.8 The exchange provides three important services:  

1. A physical location (i.e., the trading floor and the accompanying pits) for such activity, if it is a historical open-outcry system. Otherwise, the exchange will supply an electronic trading platform (such as CME’s Globex). Such platforms use the internet as the underlying network which implies that the location becomes less relevant. Many electronic trading platforms provide Application Programming Interfaces (APIs) that facilitate algorithmic trading.   
2. An exchange clearing house that becomes the real counterparty to each buyer and seller once the trade is done. A clearing house stands between two clearing firms (also known as member firms or clearing participants) and its purpose is to reduce the risk of one (or more) clearing firm failing to honor its trade settlement obligations. Why does central clearing reduce risk compared to bilateral trading? In a bilateral trade, two parties A and B enter into an agreement to exchange financial flows.9 Each of the parties bears counterparty risk or the risk that the other party defaults and is unable to fulfill its obligations. In order to reduce such risks a central counterparty (CCP) approach can be used. The clearing house becomes the CCP by splitting the bilateral trade into two trades involving the CCP and party A and the CCP and party B, respectively. The offsetting positions imply that the CCP does not have any market risk but it faces counterparty risk. A clearing house addresses the counterparty risk by requiring collateral deposits or margin payments from each of the counterparties. It reduces settlement risks by netting offsetting transactions between multiple counterparties. Other functions carried out by the clearning house that reduce risk involve providing independent valuation of trades and collateral, monitoring the credit worthiness of the clearing firms, oftentimes, providing a guarantee fund that can be used to cover losses that exceed a defaulting clearing firm’s collateral on deposit.   
3. The service of creating and designing financial contracts that the trading community needs and, finally, providing a transparent and reliable trading environment.  

The mechanics of trading in futures (options) exchanges is as follows. Two traders trade directly with each other according to their client’s wishes. One sells, say, at 100; the other buys at 100. Then the deal ticket is signed and stamped.10 Until that moment, the two traders are each other’s counterparties. But once the deal ticket is stamped, the clearinghouse takes over as the counterparty. For example, if a client has bought a futures contract for the delivery of 100 bushels of wheat, then the entity eventually responsible (they have agents) for delivering the wheat is not the “other side” who physically sold the contract on the pit, but the exchange clearinghouse. By being the only counterparty to all short and long positions, the clearinghouse will lower the counterparty risk dramatically.11 The counterparty risk is actually reduced further, since the clearinghouse will deal with clearing members, rather than the traders directly.12 The open interest in futures exchanges is the number of outstanding futures contracts. It is obtained by totaling the number of short or long positions that have not yet been closed out by delivery, cash settlement, or offsetting long/short positions.  

# 2.2.2.2 Futures compared with forward contracts  

Forwards are OTC contracts, designed according to the needs of the clients and negotiated between two counterparties. They are easy to price and almost costless to purchase. Futures are different from forward contracts in this respect. Some of the differences are minor; others are more important, leading potentially to significantly different forward and futures prices on the same underlying asset with identical characteristics. Most of these differences come from the design of futures contracts. Futures contracts need to be homogeneous to increase liquidity. The way they expire and the way deliveries are made will be clearly specified, but will still leave some options to the players. Forward contracts are initiated between two specific parties. They can state exactly the delivery and expiration conditions. Futures, on the other hand, will leave some room for last-minute adjustments and these “options” may have market value.  

We consider two contracts in order to review the main parameters involved in the design of a futures and contrast it with forward contracts. The key point is that most aspects of the transaction need to be pinned down to make a homogeneous and liquid contract. This is relatively easy and straightforward to accomplish in the case of a relatively standard commodity such as soybeans. Consider the following soybeans futures contract.13  

# EXAMPLE: CBOT (CME GROUP) SOYBEANS FUTURES  

1. Contract size. 5000 bushels $\mathord{\sim}136$ metric tons).  

2. Deliverable grades. No. 2 yellow at par, No. 1 yellow at 6 cents per bushel over contract price, and No. 3 yellow at 6 cents per bushel under contract price. (Note that in case a trader accepts the delivery, a special type of soybeans will be delivered to him or her. The trader may, in fact, procure the same quantity under better conditions from someone else. Hence, with a large majority of cases, futures contracts do not end with delivery. Instead, the position is unwound with an opposite transaction sometime before expiration.)  

3. Tick size. Quarter-cent/bushel (\$12.50/contract).  

4. Price quote. Cents and quarter-cent/bushel.  

5. Contract months. January, March, May, July, August, September, and November. (Clearly, if the purpose behind a futures transaction is delivery, then forward contracts with more flexible delivery dates will be more convenient.) On June 23, 2014, the most distant contract month available was November 2015.   
6. Last trading day. The business day prior to the 15th calendar day of the contract month.   
7. Last delivery day. Second business day following the last trading day of the delivery month.   
8. Trading hours. Open outcry: 9:30 a.m. to $1{:}15\ \mathrm{p.m}$ . Chicago time, Monday through Friday. Electronic, $8{:}30\ \mathrm{p.m}$ . to $6{:}00\ \mathrm{a.m}$ . Chicago time, Sunday through Friday. Trading in expiring contracts closes at noon on the last trading day.   
9. Daily price limit. 50 cents/bushel ( $\$2500/\mathrm{c}$ ontract) above or below the previous day’s settlement price. No limit in the spot month. (Limits are lifted two business days before the spot month begins.)  

An important concept that needs to be reviewed concerning futures markets is the process of marking to market. When one “buys” a futures contract, a margin is put aside, but no cash payment is made. This leverage greatly increases the liquidity in futures markets, but it is also risky. To make sure that counterparties realize their gains and losses daily, the exchange will reevaluate positions every day using the settlement price observed at the end of the trading day.  

# EXAMPLE  

A soybeans futures contract has a price of $\$1470.2$ on day $T.$ . At the end of day $T+1$ , the settlement price is announced as $\$1469.4$ . The price fell by 80 cents, and this is a loss to the long position holder. The position will be marked to market, and the clearinghouse—or more correctly the clearing firm—will lower the client’s balance by the corresponding amount.  

The above example illustrates one of the differences between futures and forwards. Futures contracts are always marked to market, whereas this requirement does not apply to all forwards, as we explain below.  

We consider the cash flows generated by a futures contract and compare them with the cash flows on a forward contract on the same underlying. It turns out that, unlike forwards, the effective maturity of a futures position is, in fact, 1 day. This is due to the existence of marking to market in futures trading. The position will be marked to market in the sense that every night the exchange will, in effect, close the position and then reopen it at the new settlement price. It is best to look at this with a precise example. Suppose a futures contract is written on one unit of a commodity with spot price $S_{t}$ . Let $F_{t}$ be the futures price quoted in the exchange. Suppose $t$ is a  

![](367444b181bda586fb9b4c8e0f54b1296bf9c9ab967e117f20338a7a3ca83593.jpg)  

# FIGURE 2.1  

Marking to market.  

Tuesday (March 11, 2014, for example), and that the expiration of the contract is within 3 trading days, that is on Friday, March 14, 2014:  

$$
T=t+3
$$  

where $T=$ March 11, 2014 and $t=\mathbf{M}$ arch 14, 2014. Suppose further that during these days, the settlement prices follow the trajectory  

$$
F_{t}(=\S1470.2)>F_{t+1}(=\S1469.4)>F_{t+2}(=\S1468.4)=F_{t+3}(=\S1468.4)
$$  

where $t=\mathbf{M}$ arch 11, 2014, $t+1=\mathbf{M}$ arch 12, 2014, $t+2=\mathbf{M}$ arch 13, 2014, and $t+3=\mathbf{March}\ 14$ , 2014. What cash flows will be generated by a long position in one futures contract if at expiration date $T$ the position is closed by taking the offsetting position?15  

The answer is shown in Figure 2.1. Marking to market is equivalent to forcing the long (short) position holder to close his position at that day’s settlement price and reopen it again at the same price. Thus, at the end of the first trading day after the trade, the futures contract that was “purchased” at $f_{t}$ will be “sold” at the $f_{t+1}$ shown in Eq. (2.2) for a loss:  

$$
F_{t+1}-F_{t}=1469.4-1470.2=-0.8<0
$$  

Similarly, at the end of the second trading day, marking to market will lead to another loss:  

$$
F_{t+2}-F_{t+1}=1468.4-1469.4=-1.0<0
$$  

This is the case since, according to trajectory in Eq. (2.2), prices have declined again. The expiration date will see no further losses, since, by chance, the final settlement price is the same as the previous day’s settlement.  

In contrast, the last portion of Figure 2.1 shows the cash flows generated by the forward prices $F_{t}$ . Since there is no marking to market (in this case), the only capital loss occurs at the expiration of the contract. Clearly, this is a very different cash flow pattern.16 Marking to market may significantly alter the implied cash flows and result in some moderate convexities.  

Interest rate futures are some of the most liquid futures. The following example illustrates the typical quoting convention for interest futures. The futures price is quoted as 100 minus the interest rate. This implies that a falling interest rate futures price indicates a rise in the underlying interest rate.  

# EXAMPLE: LIFFE 3-MONTH EURIBOR INTEREST RATE FUTURES  

1. Unit of trading. h1,000,000.   
2. Delivery months. January, February, March, April, May, June, July, August, September, October, November, and December. December 2019 is the last contract month available for trading, as of April 24, 2014.   
3. Price quotes. 100 minus rate of interest. (Based on the European Bankers Federations’ Euribor Offered Rate (EBF Euribor) for 3-month Euro deposits at 11.00 Brussels time (10:00 London time) on the Last Trading Day. The settlement price will be 100.00 minus the EBF Euribor Offered Rate rounded to three decimal places.)   
4. Minimum price movement. (Tick size and value) 0.005 (h12.50).   
5. Last trading day. 10.00—Two business days prior to the third Wednesday of the delivery month.   
6. Delivery day. First business day after the last trading day.   
7. Trading hours. 01:00 06:45, 07:00 21:00.   
8. Clearing. ICE Clear Europe Limited.  

Eurocurrency futures contracts will be discussed in the next chapter and will be revisited several times later. In particular, one aspect of the contract that has not been listed among the parameters noted here has interesting financial engineering implications. Eurocurrency futures have a quotation convention that implies a linear relationship between the forward interest rate and the price of the futures contract. This is another example of the fact that conventions are indeed important in finding the right solution to a financial engineering problem.  

Although, for simplicity, we assume in some of the financial engineering applications in this book that forward contracts are costless to enter, this is not the case in reality since forward contracts and other OTC derivatives require the posting of collateral. However, there are some subtle differences in collateral requirements between forward and futures contracts. First, according to the latest BCBS-IOSCO guidelines, financial and nonfinancial counterparties will be required to exchange variation margin (VM) for all new contracts entered into after December 1, 2015, and two-way IM in several phases starting in December 2015.17 This requirement also applies to derivatives that are not centrally cleared, including certain forward contracts. There are exemptions for physically settled FX OTC derivatives which require VM, but not IM.  

Second, there are differences in interest payments on the collateral in OTC and exchange-traded markets. Exchange-traded futures are settled daily and requirement daily margin that does not earn interest. If OTC forwards are cleared through a CCP or bilaterally, interest is paid on the VM if it is held in the form of cash.  

# 2.2.3 CHANGES TO THE INFRASTRUCTURE OF DERIVATIVES MARKETS FOLLOWING THE GFC  

Prior to the financial crisis, many derivatives contracts such as IRSs were mostly traded OTC and were often not centrally cleared. Oftentimes, OTC derivative contracts were not standardized and trade repositories did not exist for contracts such as credit default swaps, for example. In the years following, the GFC regulation has been implemented that saw a move towards central clearing, exchange trading, standardization and trade repositories for an increasing number of derivative contracts.  

In September 2009, the G20 set an objective of introducing mandatory clearing for standardized derivatives, including OTC IRSs. The United States (through Dodd Frank), the European Union (through EMIR), and other jurisdictions in the G20 developed and implemented regulations to achieve this objective. US regulations are driving reporting, clearing and settlement functions to much more tightly regulated Swap Execution Facilities (SEFs).18 LCH.Clearnet cleared $\$282.6$ trillion in notional amount of IRSs and $\$446.1$ billion in cleared nondeliverable FX forwards volume in 2013. ICE Clear Credit’s annual cleared CDS volume rose to $\$7.7$ trilllion in 2013.19  

In Europe, the derivatives market infrastructure is defined and supervised by the European Securities and Markets Authority (ESMA) under the European Markets Infrastructure Regulation (EMIR) regulation. Following the DoddFrank Act, the US Commodity Futures Trading Commission (CFTC) has developed the regulation, under which Swap Data Repositories are regulated.  

The hope is that recent regulation and moving most privately negotiated, bilateral contracts in the OTC market to central clearing and requiring real-time trade reporting will allow regulators to see the volume of contracts trading in the market, to assess the trading activity in different asset classes, to monitor derivatives trading data and thus, to oversee risk exposures and reduce systemic risk in the derivatives market. From a financial engineering perspective, the effect of regulatory changes is of great importance. Regulation affects margin and funding costs of different derivatives instruments and strategies. It affects the profitability and permissibility of certain structured products and trades. In later chapters, we will discuss the effect of recent regulation on financial engineering practice in different asset classes.  

# 2.3 PLAYERS  

Market makers make markets by providing days to delivery, notice of delivery, warehouses, etc. Market makers provide liquidity and must, as an obligation, buy and sell at their quoted prices. Thus for every security at which they are making the market, the market maker must quote a bid and an ask price. A market maker does not warehouse a large number of products, nor does the market maker hold them for a long period of time. Different exchanges have different structures and use different approaches in liquidity provision or market making. For example, at the New York Stock Exchange (NYSE), market making is based on the Designated Market Maker (DMM) system.20 DMMs have the primary responsibility of guaranteeing a fair and orderly market. Sometimes, this may involve taking the other side of trades when there are short-term buy-and-sellside imbalances in customer orders. In return, the DMM is granted various informational and trade execution advantages.  

Traders buy and sell securities. They do not, in the pure sense of the word, “make” the markets. A trader’s role is to execute clients’ orders and trade for the company given his or her position limits. Position limits can be imposed on the total capital the trader is allowed to trade or on the risks that he or she wishes to take.  

A trader or market maker may run a portfolio, called a book. There are “FX books,” “options books,” “swap books,” and “derivatives books,” among others. Books run by traders are called “trading books”; they are different from “investment portfolios,” which are held for the purpose of investment. Trading books exist because during the process of buying and selling for clients, the trader may have to warehouse these products for a short period of time. These books are hedged periodically. Hedge funds are an important type of arbitrageur in financial markets and we discuss hedge funds in detail in Chapter 7.  

Brokers do not hold inventories. Instead, they provide a platform where the buyers and sellers can get together. Buying and selling through brokers is often more discreet than going to bids and asks of traders. In the latter case, the trader would naturally learn the identity of the client. In open-outcry options markets, a floor-broker is a trader who takes care of a client’s order but does not trade for himself or herself. (On the other hand, a market maker does.)  

Dealers quote two-way prices and hold large inventories of a particular instrument, maybe for a longer period of time than a market maker. They are institutions that act in some sense as market makers.  

Risk managers are relatively new players. Trades, and positions taken by traders, should be “approved” by risk managers. The risk manager assesses the trade and gives approvals if the trade remains within the preselected boundaries of various risk managers.  

Regulators are important players in financial markets. Practitioners often take positions of “tax arbitrage” and “regulatory arbitrage.” A large portion of financial engineering practices is directed toward meeting the needs of the practitioners in terms of regulation and taxation.  

Researchers and analysts are players who do not trade or make the market. They are information providers for the institutions and are helpful in sell-side activity. Analysts in general deal with stocks and analyze one or more companies. They can issue buy/sell/hold signals and provide forecasts. Researchers provide macrolevel forecasting and advice.  

# 2.4 THE MECHANICS OF DEALS  

What are the mechanisms by which the deals are made? How are trades done? It turns out that organized exchanges have their own clearinghouses and their own clearing agents. So it is relatively easy to see how accounts are opened, how payments are made, how contracts are purchased, and positions are maintained. The clearing members and the clearinghouse do most of these. But how are these operations completed in the case of OTC deals? How does one buy a bond and pay for it? How does one buy a foreign currency?  

Turning to another detail, where are these assets to be kept? An organized exchange will keep positions for the members, but who will be the custodian for OTC operations and secondary market deals in bonds and other relevant assets?  

Several alternative mechanisms are in place to settle trades and keep the assets in custody. A typical mechanism is shown in Figure 2.2. The mechanics of a deal in Figure 2.2 are from the point of view of a market practitioner. The deal is initiated at the trading or dealing room. The trader writes the deal ticket and enters this information in the computer’s front office system. The middle office is the part of the institution that initially verifies the deal. It is normally situated on the same floor as the trading room. Next, the deal goes to the back office, which is located either in a different building or on a different floor. Back office activity is as important for the bank as the trading room. The back office does the final verification of the deal, handles settlement instructions, releases payments, and checks the incoming cash flows, among other things. The back office will also handle the messaging activity using the SWIFT system, to be discussed later. Following the Global Financial Crisis, pre- and posttrade operational processes are increasingly merging to support new trading and clearing procedures required under financial regulation such as the Dodd Frank Act and EMIR. The merging of pre- and posttrade processes is especially crucial to support the clearing certainty requirement. New requirements to execute certain OTC derivatives via SEFs, coupled with mandated clearing via a CCP means there is now a two-stage process to the execution of some derivatives. Execution and clearing via a CCP are now two intrinsic components of a derivatives trade, while in the past they were separate.  

![](1f45ff68fae7a2663f7b0187005d1c3dca0d86d5a2a5e2df1f22429f0087b0ee.jpg)  

# FIGURE 2.2  

How trades are made and confirmed.  

# 2.4.1 ORDERS  

There are two general types of orders investors or traders can place. The first is a market order, where the client gets the price the market is quoting at that instant.  

Alternatively, parties can place a limit order. Here a derived price will be specified along the order, and the trade will go through only if this or a better price is obtained. A limit order is valid only during a certain period, which needs to be specified also. A stop loss order is similar. It specifies a target price at which a position gets liquidated automatically.  

Processing orders is by no means error free. For example, one disadvantage of traditional openoutcry exchanges is that in such an environment, mistakes are easily made. Buyer and seller may record different prices. This is called a “price out.” Or there may be a “quantity out,” where the buyer has “bought $100^{\circ}$ while the seller thinks that he has “sold 50.” In the case of options exchanges, the recorded expiration dates may not match, which is called a “time out.” Out-trades need to be corrected after the market close. There can also be missing trades. These trades need to be negotiated in order to recover positions from counterparties and clients.21 Electronic trading systems are also vulnerable to outages. During one such outage for agricultural contracts in April 2014, the CME temporarily resorted to open-outcry trading.  

# 2.4.2 CONFIRMATION AND SETTLEMENT  

Order confirmation and settlement are two integral parts of financial markets. Order confirmation involves sending messages between counterparties, to confirm trades verbally agreed upon between market practitioners. Settlement is exchanging the cash and the related security, or just exchanging securities.  

The SWIFT system is a communication network that has been created for “paperless” communication between market participants to this end. It stands for the Society for Worldwide Financial Telecommunications and is owned by a group of international banks. The advantage of SWIFT is the standardization of messages concerning various transactions such as customer transfers, bank transfers, foreign exchange (FX), loans, and deposits. Thousands of financial institutions in more than 100 countries use this messaging system.  

Another interesting issue is the relationship between settlement, clearing, and custody. Settlement means receiving the security and making the payment. The institutions can settle, but in order for the deal to be complete, it must be cleared. The orders of the two counterparties need to be matched and the deal terminated. Custody is the safekeeping of securities by depositing them with carefully selected depositories around the world. A custodian is an institution that provides custody services. Clearing and custody are both rather complicated tasks. FedWire, Euroclear, and Clearstream are three international securities clearing firms that also provide some custody services. Some of the most important custodians are banks.  

Countries also have their own clearing systems. The best known bank clearing systems are CHIPS and CHAPS. CHAPS is the clearing system for the United Kingdom, CHIPS is the clearing system for payments in the United States. Payments in these systems are cleared multilaterally and are netted. This greatly simplifies settling large numbers of individual trades.  

Spot trades settle according to the principle of DVP—that is to say, delivery versus payment— which means that first the security is delivered (to securities clearing firms) and then the cash is paid.  

Issues related to settlement have another dimension. There are important conventions involving normal ways of settling deals in various markets. When a settlement is done according to the convention in that particular market, we say that the trade settles in a regular way. Of course, a trade can settle in a special way. But special methods would be costly and impractical.  

# EXAMPLE  

Market practitioners denote the trade date by $T.$ , and settlement is expressed relative to this date.  

US Treasury securities settle regularly on the first business day after the trade—that is to say, on $T+1$ . But it is also common for efficient clearing firms to have cash settlement— that is to say, settlement is done on the trade date $T$ .  

Corporate bonds and international bonds settle on $T+3$ .  

Commercial paper (CP) settles the same day.  

Spot transactions in stocks settle regularly on $T+3$ in the United States.  

Euromarket deposits are subject to $T+2$ settlement. In the case of overnight borrowing and lending, counterparties may choose cash settlement.  

FX markets settle regularly on $T+2$ . This means that a spot sale (purchase) of a foreign currency will lead to two-way flows 2 days after the trade date, regularly. $T+2$ is usually called the spot date.  

It is important to expect that the number of days to settlement in general refers to business days. This means that in order to be able to interpret $T+2$ correctly, the market professional would need to pin down the corresponding holiday convention.  

Before discussing other market conventions, we can mention two additional terms that are related to the preceding dates. The settlement date is sometimes called the value date in contracts. Cash changes hands at the value date. Finally, in swap-type contracts, there will be the deal date (i.e., when the contract is signed), but the swap may not begin until the effective date. The latter is the actual start date for the swap contract and will be at an agreed-upon later date.  

# 2.4.2.1 Regulatory update following the GFC  

On April 23, 2014, The Depository Trust & Clearing Corporation (DTCC) released a white paper outlining the rationale for supporting a move to shorten the settlement cycle (SSC) in the US financial markets for equities, corporate and municipal bonds, and unit investment trust (UIT) trades. The rationale for the reduction from $T+3$ (trade date plus 3 days) to $T+2$ (trade date plus 2 days) is that a shortened settlement cycle will reduce the following: counterparty risk exposure, procyclicality, NSCC’s liquidity need, and overall operational and industry risk.22  

# 2.5 MARKET CONVENTIONS  

Market conventions often cause confusion in the study of financial engineering. Yet, it is very important to be aware of the conventions underlying the trades and the instruments. In this section, we briefly review some of these conventions.  

Conventions vary according to the location and the type of instrument one is concerned with. Two instruments that are quite similar may be quoted in very different ways. What is quoted and the way it is quoted are important.  

As mentioned, in Chapter 1 in financial markets there are always two prices. There is the price at which a market maker is willing to buy the underlying asset and the price at which he or she is willing to sell it. The price at which the market maker is willing to buy is called the bid price. The ask price is the price at which the market maker is willing to sell. In London financial markets, the ask price is called an offer. Thus, the bid-ask spread becomes the bid-offer spread.  

As an example consider the case of deposits in London money and FX markets, where the convention is to quote the asking interest rate first. For example, a typical quote on interest rates would be as follows:  

<html><body><table><tr><td>Ask (Offer)</td><td>Bid</td></tr><tr><td>5</td><td>5</td></tr></table></body></html>  

In other money centers, interest rates are quoted the other way around. The first rate is the bid, the second is the ask rate. Hence, the same rates will look as such:  

<html><body><table><tr><td> Bid</td><td>Ask (Offer)</td></tr><tr><td>5 5</td><td></td></tr></table></body></html>  

A second characteristic of the quotes is decimalization. The Eurodollar interest rates in London are quoted to the nearest $\frac{1}{16}$ or sometimes $\frac{1}{32}$ . But many money centers quote interest rates to two decimal points. Decimalization is not a completely straightforward issue from the point of view of brokers/dealers. Note that with decimalization, the bid-ask spreads may narrow all the way down to zero, and there will be no minimum bid-ask spread. This may mean lower trading profits, everything else being the same.  

# 2.5.1 WHAT TO QUOTE  

Another set of conventions concerns what to quote. For example, when a trader receives a call, he or she might say, “I sell a bond at a price of 95,” or instead, he or she might say, “I sell a bond at yield $5\%$ .” Markets prefer to work with conventions to avoid potential misunderstandings and to economize time. Equity markets quote individual stock prices. On most stock exchanges including the NYSE, the quotes are to decimal points.  

Most bond markets quote prices rather than yields, with the exception of short-term T-bills. For example, the price of a bond may be quoted as follows:  

<html><body><table><tr><td>Bid Price</td><td>Ask (Offer) Price</td></tr><tr><td>90.45</td><td>90.57</td></tr></table></body></html>  

The first quote is the price a market maker is willing to pay for a bond. The second is the price at which the market maker dealer is willing to sell the same bond. Note that according to this, bond prices are quoted to two decimal points, out of a par value of 100, regardless of the true denomination of the bond.  

It is also possible that a market quotes neither a price nor a yield. For example, caps, floors, and swaptions often quote “volatility” directly. Swap markets prefer to quote the “spread” (in the case of USD swaps) or the swap rate itself (Euro-denominated swaps). The choice of what to quote is not a trivial matter. It affects pricing as well as risk management.  

# 2.6 INSTRUMENTS  

This section provides a list of the major instrument classes from the perspective of financial engineering. A course on markets and instruments along the lines of Hull (2014) is needed for a reasonable understanding.  

The convention in financial markets is to divide these instruments according to the following sectors:  

1. Fixed income instruments. These are interbank certificates of deposit (CDs), or deposits (depos), CP, banker’s acceptances, and Treasury bill (T-bills). These are considered to be money market instruments. Bonds, notes, and floating rate notes (FRNs) are bond market instruments   
2. Equities. These are various types of stock issued by public companies   
3. Currencies   
4. Commodities   
5. Derivatives, the major classes of which are interest rate, equity, currency, and commodity derivatives   
6. Credit instruments, which are mainly high-yield bonds, corporate bonds, credit derivatives, CDSs, and various guarantees that are early versions of the former   
7. Structured products MBS, CDO, ABS.  

We discuss these major classes of instruments from many angles in the chapters that follow.  

# 2.7 POSITIONS  

By buying or short-selling assets, one takes positions, and once a position is taken, one has exposure to various risks.  

# 2.7.1 LONG AND SHORT POSITIONS  

A long position is easier to understand because it conforms to the instincts of a newcomer to financial engineering. In our daily lives, we often “buy” things, we rarely “short” them. Hence, when we buy an item for cash and hold it in inventory, or when we sign a contract that obliges us to buy something at a future date, we will have a long position. We are long the “underlying instrument,” and this means that we benefit when the value of the underlying asset increases.  

A short position, on the other hand, is one where the market practitioner has sold an item without really owning it. For example, a client calls a bank and buys a particular bond. The bank may not have this particular bond on its books, but can still sell it. In the meantime, however, the bank has a short position.  

# 2.7.1.1 Payoff diagrams  

One can represent short and long positions using payoff diagrams. Figure 2.3 illustrates the long position from the point of view of an investor. The investor has savings of 100. The upwardsloping vertical line $O A$ represents the value of the investor’s position given the price of the security. Since its slope is $+1$ , the price of the security $P_{0}$ will also be the value of the initial position. Starting from $P_{0}$ the price increases by $\Delta P$ ; the gain will be equal to this change as well.  

In particular, if the investor “buys” the asset when the price is 100 using his or her own savings, the net worth at that instant is represented by the vertical distance $O B$ , which equals 100. A market professional, on the other hand, has no “money.” So he or she has to borrow the OB (or the $P_{0,}$ ) first and then buy the asset. This is called funding the long position.  

This situation is shown in Figure 2.4. Note that the market professional’s total net position amounts to zero at the time of the purchase, when $P_{0}=100$ . In a sense, by first borrowing and then buying the asset, one “owns” not the asset but some exposure. If the asset price goes up, the position becomes profitable. If, on the other hand, the price declines, the position will show a loss.  

Figure 2.5 shows a short position from a market practitioner’s point of view. Here the situation is simpler. The asset in the short position is borrowed anyway at $P_{0}=100$ . Hence, when the price  

![](893e15d97ce99284562b1301282adbb41403ca5b0c56ec697b7f0528e3078632.jpg)  

# FIGURE 2.3  

Long position of a market professional.  

![](334465eb4c1b49a369f9c74e827ac314fc9470c2b09eb0b23ab3b3f08e34bd56.jpg)  

# FIGURE 2.4  

Funding a long position.  

![](83f1f613e227e66ccfcd23cf4df3a97ccf86d73e121781a142c64227cc244750.jpg)  

# FIGURE 2.5  

Short position of a market professional.  

is 100 at the time of the sale, the net worth is automatically zero. What was sold was an asset that was worth 100. The cash generated by the sale just equals the value of the asset that was borrowed. Therefore, at the price $P_{0}=100$ , the position has zero value. The position will gain when the price falls and will lose when the price goes up. This is the case since what is borrowed is a security and not “money.” The asset is sold at 100; and, when $P$ increases, one would have to return to the original owner a security that is worth more than 100.  

Similarly, when $P$ falls, one covers the short position by buying a new security at a price lower than 100 and then returning this (less valuable) asset to the original owner. Overall, the short position is described by a downward sloping straight line with slope $^{-1}$ .  

# 2.7.1.2 Real-world complications and short selling  

When we discuss synthetics and replicating portfolios for derivatives in this book, for simplicity, we assume that borrowing costs associated with shorting the underlying assets are negligible. This may be a reasonable assumption for liquid forward and futures markets, but it is not the case for other assets such as cash equities and bonds. Here, we briefly discuss real-world complications and the mechanics and costs of shorting stocks. Consider a hedge fund that would like to short a share such as Coca-Cola (KO), for example, in the hope of buying it back later at a lower price. The fund could contact a broker dealer such as Citibank, for example, who would normally locate the shares by borrowing them from a major custody bank or fund management company such as State Street, for example. The incentive for State Street to lend the shares lies in the fact that it could charge a fee for lending the shares. If the hedge fund was to borrow a share of KO and sell it for, say $\$41$ , it could however not keep the $\$41$ . The reason is that the security lender—State Street in this example—needs to protect itself against the potential inability of the hedge fund to return the share. This is achieved by asking for cash collateral. In an institutional US stock loan, the borrower is required to put up cash collateral, typically $102\%$ of the value of the stock or $\$41.82$ in the case of KO. The $\$0.82$ represents the margin requirement. Hence, in contrast to stylized academic accounts, short selling in practice does not free up capital, but instead it uses capital. If the price of KO was to increase, to say $\$50$ , then the hedge fund would receive a margin call and would have to put up additional margin, of say $\$51$ . The opposite would happen if the stock price decreased.  

Once the hedge fund returns the KO share, State Street returns the cash collateral plus interest. If Street can invest the cash collateral and a market interest rate that is higher than the rebate rate, that is interest rate paid to the hedge fund, this represents an additional return source for State Street. The difference between the rebate rate and market interest rates is the loan fee that the hedge fund has to pay. Securities lending fees for most stocks are small, that is around $1\%$ per year in the United States, for most stocks, but sometimes they can be as high as $50\%$ per year or even higher for individual stocks.23 The market for securities lending is after all subject to the same laws of supply and demand as other markets and hard to borrow securities can only be borrowed at substantial cost. Most securities lending transactions are open loans. An open loan has an overnight tenor, but continues until one of the counterparties decides to cancel it. The short seller faces recall risk if the lender decides to recall or cancel the loan.  

In the above example, before the hedge fund closes the short position in KO it must buy back the share. Sometimes a lot of shortsellers try to do so at the same time and this can drive up the price and lead to a short squeeze, as the following recent example illustrates.  

# EXAMPLE  

Great cornering and eye-popping acceleration make Porsche’s cars popular among thrill-seeking bankers   
and hedge fund managers. Now its clients are discovering that the carmaker itself has an unexpected talent   
for cornering markets. $I...J$ [. . .] on October 26th it executed a handbrake turn, saying that it owned nearly $43\%$ of VW’s shares   
outright and had derivative contracts on nearly $32\%$ more $I...J$ Hedge funds quickly did the maths,   
concluding that they could be caught in an “infinite squeeze” Their frenzied buying sent VW’s share price soaring $I...J.$ After languishing below h200 last year, it   
jumped to more than h1,005 at one point on October 28th [. . .]  

The Economist, October 30, 2008  

In the three years preceding October 2008 Porsche had secretly used derivatives to accumulate a stake in VW and repeatedly denied that it was doing so. In the process Porsche had accumulated most of the freely available shares of VW. The remainder of the shares was owned by the state government and passive funds which implied that hedge funds were short VW risked not being able to close their short positions in time. The above illustrates that shorting is not simply the opposite of going long. Not only are there borrowing fees, but the risk profile of shorting stocks is also different from that of going long. Significant borrowing costs also have implications for financial engineering and derivatives pricing. It can affect put-call parity and the early exercise of American options, which we will discuss in later chapters. The price discontinuities introduced by short squeezes make continuous hedging impossible and violate assumptions about the smooth stochastic processes that some financial engineering models rely on. Financial engineers and traders need to be aware of such model limitations in turbulent times and anticipate them in the pricing of products and execution of arbitrage strategies.  

# 2.7.2 PAYOFF DIAGRAMS FOR FORWARDS AND FUTURES  

Forwards and futures contracts are the most basic type of derivatives and involve some of the simplest cash flow exchanges. We discussed institutional differences between forwards and futures markets in Section 2.2. Next we extend our discussion of positions and payoff diagrams to forwards. A forward is a contract written at time $t_{0}$ , with a commitment to accept delivery of (deliver) $N$ units of the underlying asset at a future date $t_{1}$ , $t_{0}<t_{1}$ , at the forward price $\boldsymbol{F}_{t_{0}}$ . At time $t_{0}$ , nothing changes hands; all exchanges will take place at time $t_{1}$ . The current price of the underlying asset $S_{t_{0}}$ is called the spot price and is not written anywhere in the contract, instead, $\boldsymbol{F}_{t_{0}}$ is used during the settlement. Note that $\boldsymbol{F}_{t_{0}}$ has a $t_{0}$ subscript and is fixed at time $t_{0}$ . An example of such a contract is shown in Figure 2.6.  

![](bef25036ce875435f4419553109aabb6f0437dbab4bbad431dcfc535f766e27e.jpg)  

# FIGURE 2.6  

Long and short forward position.  

Forward contracts are written between two parties, depending on the needs of the client. They are flexible instruments. The size of contract $N$ , the expiration date $t_{1}$ , and other conditions written in the contract can be adjusted in ways the two parties agree on.  

To recap our earlier discussion: if the same forward purchase or sale is made through a homogenized contract, in which the size, expiration date, and other contract specifications are preset, if the trading is done in a formal exchange, if the counterparty risk is transferred to a clearinghouse, and if there is formal mark-to-market, then the instrument is called futures.  

Positions on forward contracts are either long or short. A long position is a commitment to accept delivery of the contracted amount at a future date, $t_{1}$ , at price $\boldsymbol{F}_{t_{0}}$ . This is displayed in Figure 2.6a. Here $\boldsymbol{F}_{t_{0}}$ is the contracted forward price. As time passes, the corresponding price on newly written contracts will change and at expiration the forward price becomes $\boldsymbol{F}_{t_{1}}$ . The difference, $F_{t_{1}}-F_{t_{0}}$ , is the profit or loss for the position taker. Note two points. Because we assume, for simplicity, that the forward contract does not require any cash payment at initiation, the time $t_{0}$ value is on the $x$ -axis. This implies that, at initiation, the market value of the contract is zero. Second, at time $t_{1}$ the spot price $S_{t_{1}}$ and the forward price $\boldsymbol{F}_{t_{1}}$ will be the same (or very close).  

A short position is a commitment to deliver the contracted amount at a future date, $t_{1}$ , at the agreed price $\boldsymbol{F}_{t_{0}}$ . The short forward position is displayed in Figure 2.6b. The difference $F_{t_{0}}-F_{t_{1}}$ is the profit or loss for the party with the short position.  

# EXAMPLES  

Elementary forwards and futures contracts exist on a broad array of underlyings. Some of the best known are the following:  

1. Forwards on interest rates. These are called forward rate agreements (FRA). An FRA is an OTC contract designed to fix the interest rate that will apply to either borrowing or lending a certain amount during a specific time period in the future.   
2. Forwards on currencies. These are called FX forwards and consist of buying (selling) one currency against another at a future date $t_{1}$ .   
3. Futures on loans and deposits. Here, a currency is exchanged against itself, but at a later date. We call these forward loans or deposits. Another term for these is forward forward. Futures provide a more convenient way to trade interest rate commitments; hence, forward loans are not liquid. Futures on forward loans are among the most liquid.   
4. Futures on commodities, e.g., be oil, corn, pork bellies, and gold. There is even a thriving market in futures trading on weather conditions.   
5. Futures and forwards on individual stocks and stock indices. Given that one cannot settle a futures contract on an index by delivering the whole basket of stocks, these types of contracts are cash settled. The losers compensate the gainers in cash, instead of exchanging the underlying products.   
6. Futures contracts on (interest rate) swaps. These are relatively recent and they consist of future swap rate commitments. They are also settled in cash. Compared to futures trading, the OTC swap and OTC forward market are more dominant here.24   
7. Futures contracts on volatility indices.   
8. Futures contracts on swaps.  

It is interesting to note some technical aspects of the graphs in Figures 2.3 2.7. First, the payoff diagrams that indicate the value of the positions taken are linear in the price of the asset. As the price $P$ changes, the payoff changes by a constant amount. The sensitivity of the position to price changes is called delta. In fact, given that the change in price will determine the gains or losses on a one-to-one basis, the delta of a long position will be 1. In the case of a short position, the delta will equal $^{-1}$ .  

![](6b8796f3218fb5321dc0cdf628380ad215fcfce3466f8ae5f1f33155027fc97a.jpg)  

# FIGURE 2.7  

A hedge.  

One can define many other sensitivity factors by taking other partial derivatives. Such sensitivities are called Greeks and are extensively used in option markets.25 Financial derivatives with a delta of 1 have no optionality and are called Delta One products and the trading desks that pursue strategies related to them are called Delta One desks.26  

Forwards and futures contracts are ideal for creating synthetic instruments for many reasons. Forwards and futures are, in general, linear permitting static replication. They are often very liquid and, in case of currency forwards, have homogeneous underlying. Many technical complications are automatically eliminated by the homogeneity of a currency. Forwards and futures on interest rates present more difficulties and we will discuss them in the next chapter.  

# 2.7.3 TYPES OF POSITIONS  

Positions can be taken for the purposes of hedging, arbitrage, and speculation. We briefly review these activities.  

Let us begin with hedging. Hedging is the act of eliminating the exposures of existing positions without unwinding the position itself. Suppose we are short a bond (i.e., we borrowed somebody’s bond and sold it in the market for cash). We have cash at hand, but at the same time, we owe somebody a bond. This means that if the bond price goes up, our position will have a mark-to-market loss.  

In order to eliminate the risk we can buy a “similar” bond. Our final position is shown in Figure 2.7. The long and short positions “cancel” each other except for some remaining basis risk.27 At the end, we will have little exposure to movements in the underlying price $P$ . To hedge the same risk we can also take the long position not in the cash or spot bond markets, but in a futures or forward market. That is to say, instead of buying another bond, we may write a contract at time $t$ promising that we will buy the bond at a prespecified price $P^{f}$ after $\delta$ days. This will not require any cash disbursement until the settlement time $t+\delta$ arrives, while yielding a gain or loss given the way the market prices move until that time. Here, the forward price $P^{f}$ and the spot price $P$ will not be identical. The underlying asset being the same, we can still anticipate quite similar profits and losses from the two positions. This illustrates one of the basic premises of financial engineering. Namely that as much as possible, one should operate by taking positions that do not require new funding.  

The difference between the spot price of a given cash market asset and the price of its related futures contract, $P-P_{\mathrm{.}}^{f}$ , is called the basis.28 The purchase of a particular financial instrument or commodity and the sale of its related derivative (e.g., the purchase of a particular bond and the sale of a related futures contract) may sometimes not be motivated by a hedging motive, but by speculation, in which case it is also called basis trading.  

# 2.7.3.1 Arbitrage  

The notion of arbitrage is central to financial engineering. It means two different things, depending on whether we look at it from the point of view of market practice or from the theory of financial engineering.  

We begin with the definition used in the theory of financial engineering. In that context, we say that given a set of financial instruments and their prices, $\{P_{1},P_{2},...,P_{k}\}$ , there is no arbitrage opportunity if a portfolio that costs nothing to assemble now, with a nonnegative return in the future is ruled out. A portfolio with negative price and zero future return should not exist either.  

If prices $P_{i}$ have this characteristic, we say that they are arbitrage free. In a sense, arbitragefree prices represent the fair market value of the underlying instruments. One should not realize gains without taking some risk and without some initial investment. Many arguments in later chapters will be based on the no arbitrage principle.  

In market practice, the term “arbitrage,” or “arb,” has a different meaning. In fact, “arb” represents a position that has risks, a position that may lose money but is still highly likely to yield a “high” profit.  

# 2.7.3.2 Comparing performance  

There are two terms that need to be defined carefully in order to understand the appendix to Chapter 12 and several examples. An asset $A$ is set to outperform another asset $B$ , if a long position in $A$ and a simultaneous short position in $B$ makes money. Otherwise $A$ is said to underperform $B$ . According to this, outperform indicates relative performance and is an important notion for spread trading.  

# 2.8 THE SYNDICATION PROCESS  

A discussion of the syndication process will be useful. Several contract design and pricing issues faced by a financial engineer may relate to the dynamics of the syndication process. Stocks, bonds, and other instruments are not sold to investors in the primary market the way, say, cars or food are sold. The selling process may take a few days or weeks and has its own wrinkles. The following gives an indicative time table for a syndication process.  

# 2.8.1 SELLING SECURITIES IN THE PRIMARY MARKET  

Time tables show variations from one instrument to another. Even in the same sector, the timing may be very different from one issuer to another, depending on the market psychology at that time. The process described gives an example. The example deals with a Eurobond issue. For syndicated loans, for facilities, and especially for IPOs, the process may be significantly different, although the basic ideas will be similar.  

1. The week of D-14: Manager is chosen, mandate is given. Issue strategy is determined. Documentation begins.   
2. The week of D-7: Documentation completed. Comanagers are determined.   
3. D-Day: “Launch” date. Contacting underwriter and selling group members. Issue is published in the press.   
4. $\mathsf{D}+8$ : Preliminary allotment done by lead manager.   
5. $\mathbf{D}+9$ : Pricing day.   
6. $\mathrm{{D+10}}$ : Offering day. Allotment messages are sent to group members.   
7. $\mathrm{D}+24$ : Payment day. Syndicate members make payments.  

In other markets, important deviations in terms of both timing and procedure may occur during actual syndication processes. But overall, the important steps of the process are as shown in this simple example.  

# 2.8.1.1 Syndication of a bond versus a syndicated loan  

We can compare a bond issue with processing a syndicated loan. There are some differences. Syndicated loans are instruments that are in banking books or credit departments of banks. The follow-up and risk management is done by the banking credit departments with methodologies similar to standard loans. For example, information in the offering circular is not as important.  

Bonds, on the other hand, are handled by investment or in trading books, and the analysis and information in the circular are taken seriously. Documentation differences are major.  

The syndicated loan tries to maintain a relationship between the bank and its client through the agent. But in the bond issue, the relationship between the lender and the borrower is much more distant. Hence, this type of borrowing is available only to good names with good credit standing. Banks have to continuously follow lesser names to stay aware of any deterioration of credit conditions. The maturities can also be very different.  

# 2.9 CONCLUSIONS  

This chapter reviewed some basic information the reader is assumed to have been exposed to. The discussion provided here is sketchy and cannot be a substitute for a thorough course on conventions, markets, and players. Also, market conventions, market structure, and the instrument characteristics may change over time.  

# SUGGESTED READING  

It is important for a financial engineering student to know the underlying instruments, markets, and conventions well. This chapter provided only a very brief review of these issues. Fortunately, several excellent texts cover these further. Hull (2014) and Wilmott (2006) are first to come to mind. Market-oriented approaches to instruments, pricing, and some elementary financial market strategies can be found in Steiner (2012) and Roth (1996). These two sources are recommended as background material.  

# EXERCISES  

1. What is the difference between initial and variation margin?   
2. How do collateral requirements differ between futures and OTC derivative markets.   
3. What are the differences between centrally and bilaterally cleared derivatives?   
4. What does open interest refer to?   
5. Suppose the following stock prices for GE and Honeywell were observed before any talk o merger between the two institutions: Honeywell (HON) 27.80 General Electric (GE) 53.98  

Also, suppose you “know” somehow that GE will offer 1.055 GE shares for each Honeywell share during any merger talks.  

a. What type of “arbitrage” position would you take to benefit from this news? b. Do you need to deposit any of your funds to take this position? c. Do you need to and can you borrow funds for this position? d. Is this a true arbitrage in the academic sense of the word? e. What (if any) risks are you taking?  

6. Read the market example below and answer the following questions that relate to it.  

Proprietary dealers are betting that Euribor, the proposed continental European-based euro money market rate, will fix above the Euro BBA LIBOR alternative. . . The arbitrage itself is relatively straightforward. The proprietary dealer buys the Liffe September 1999 Euromark contract and sells the Matif September 1999 Pibor contract at roughly net zero cost. As the Liffe contract will be referenced to Euro BBA LIBOR and the Matif contract will be indexed to Euribor, the trader in effect receives Euribor and pays Euro BBA LIBOR.  

The strategy is based on the view that Euribor will generally set higher than Euro BBA LIBOR. Proprietary dealers last week argued that Euribor would be based on quotes from 57 different banks, some of which, they claimed, would have lower credit ratings than the eight LIBOR banks. In contrast, Euro BBA LIBOR will be calculated from quotes from just 16 institutions. (From Thomson Reuters IFR, December 18, 1998)  

a. Show the positions of the proprietary dealers using position diagrams.   
b. In particular, what is on the horizontal axis of these diagrams? What is on the vertical axis?   
c. How would the profits of the “prop” dealers be affected at expiration, if in the meantime there was a dramatic lowering of all European interest rates due, say, to a sudden recession?  