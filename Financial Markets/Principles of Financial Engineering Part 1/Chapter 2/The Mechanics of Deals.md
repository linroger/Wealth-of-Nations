---
tags:
  - clearinghouse
  - dodd_frank_act
  - limit_order
  - market_order
  - market_practitioner
  - openoutcry_exchanges
  - otc_deals
  - stop_loss_order
  - trading_mechanics
aliases:
  - Deal Mechanics
  - Mechanics of Deals
key_concepts:
  - Back office functions
  - Market and limit orders
  - OTC deal operations
  - Order processing errors
  - Trading and clearing
  - Trading room operations
---

# 2.4 THE MECHANICS OF DEALS  

What are the mechanisms by which the deals are made? How are trades done? It turns out that organized exchanges have their own clearinghouses and their own clearing agents. So it is relatively easy to see how accounts are opened, how payments are made, how contracts are purchased, and positions are maintained. The clearing members and the clearinghouse do most of these. But how are these operations completed in the case of OTC deals? How does one buy a bond and pay for it? How does one buy a foreign currency?  

Turning to another detail, where are these assets to be kept? An organized exchange will keep positions for the members, but who will be the custodian for OTC operations and secondary market deals in bonds and other relevant assets?  

Several alternative mechanisms are in place to settle trades and keep the assets in custody.. A typical mechanism is shown in Figure 2.2. The mechanics of a deal in Figure 2.2 are from the point of view of a market practitioner. The deal is initiated at the trading or dealing room. The trader writes the deal ticket and enters this information in the computer's front office system. The middle office is the part of the institution that initially verifies the deal. It is normally situated on the same floor as the trading room. Next, the deal goes to the back office, which is located either in a different building or on a different floor. Back office activity is as important for the bank as the trading room. The back office does the final verification of the deal, handles settlement instructions, releases payments, and checks the incoming cash flows, among other things. The back office will also handle the messaging activity using the SwIFT system, to be discussed later. Following. the Global Financial Crisis, pre- and posttrade operational processes are increasingly merging to. support new trading and clearing procedures required under financial regulation such as the. Dodd-Frank Act and EMIR. The merging of pre- and posttrade processes is especially crucial to. support the clearing certainty requirement. New requirements to execute certain OTC derivatives. via SEFs, coupled with mandated clearing via a CCP means there is now a two-stage process to the execution of some derivatives. Execution and clearing via a CCP are now two intrinsic components of a derivatives trade, while in the past they were separate..  

![](f06b926f494205b85eda466f635243175b60355cb8f629055d73558bf693813b.jpg)  

# FIGURE 2.2  

How trades are made and confirmed.  

# 2.4.1 ORDERS  

There are two general types of orders investors or traders can place. The first is a market order, where the client gets the price the market is quoting at that instant..  

Alternatively, parties can place a limit order. Here a derived price will be specified along the order, and the trade will go through only if this or a better price is obtained. A limit order is valid only during a certain period, which needs to be specified also. A stop loss order is similar. It specifies a target price at which a position gets liquidated automatically.  

Processing orders is by no means error free. For example, one disadvantage of traditional openoutcry exchanges is that in such an environment, mistakes are easily made. Buyer and seller may record different prices. This is called a "price out." Or there may be a "quantity out," where the buyer has "bought $100'$ while the seller thinks that he has "sold 50. In the case of options exchanges, the recorded expiration dates may not match, which is called a "time out." Out-trades need to be corrected after the market close. There can also be missing trades. These trades need to be negotiated in order to recover positions from counterparties and clients.2' Electronic trading systems are also vulnerable to outages. During one such outage for agricultural contracts in April 2014, the CME temporarily resorted to open-outcry trading.  

# 2.4.2 CONFIRMATION AND SETTLEMENT  

Order confirmation and settlement are two integral parts of financial markets. Order confirmation involves sending messages between counterparties, to confirm trades verbally agreed upon between market practitioners. Settlement is exchanging the cash and the related security, or just exchanging securities.  

The SwIFT system is a communication network that has been created for "paperless" communication between market participants to this end. It stands for the Society for Worldwide Financial. Telecommunications and is owned by a group of international banks. The advantage of SwIFT is. the standardization of messages concerning various transactions such as customer transfers, bank. transfers, foreign exchange (FX), loans, and deposits. Thousands of financial institutions in more than 100 countries use this messaging system.  

Another interesting issue is the relationship between settlement, clearing, and custody. Settlement means receiving the security and making the payment. The institutions can settle, but in order for the deal to be complete, it must be cleared. The orders of the two counterparties need to be matched and the deal terminated. Custody is the safekeeping of securities by depositing them with carefully selected depositories around the world. A custodian is an institution that provides custody services. Clearing and custody are both rather complicated tasks. FedWire, Euroclear, and Clearstream are three international securities clearing firms that also provide some custody services. Some of the most important custodians are banks.  

Countries also have their own clearing systems. The best known bank clearing systems are. CHIPS and CHAPS. CHAPS is the clearing system for the United Kingdom, CHIPS is the clearing system for payments in the United States. Payments in these systems are cleared multilaterally and are netted. This greatly simplifies settling large numbers of individual trades.  

Spot trades settle according to the principle of DVP--that is to say, delivery versus payment-- which means that first the security is delivered (to securities clearing firms) and then the cash is paid.  

Issues related to settlement have another dimension. There are important conventions involving. normal ways of settling deals in various markets. When a settlement is done according to the con-. vention in that particular market, we say that the trade settles in a regular way. Of course, a trade can settle in a special way. But special methods would be costly and impractical..  

# EXAMPLE  

Market practitioners denote the trade date by $T.$ and settlement is expressed relative to this date.  

US Treasury securities settle regularly on the first business day after the trade--that is to say, on $T+1$ . But it is also common for efficient clearing firms to have cash settlementthat is to say, settlement is done on the trade date $T$  

Corporate bonds and international bonds settle on $T+3$  

Commercial paper (CP) settles the same day.  

Spot transactions in stocks settle regularly on $T+3$ in the United States.  

Euromarket deposits are subject to. $T+2$ settlement. In the case of overnight borrowing. and lending, counterparties may choose cash settlement.  

FX markets settle regularly on $T+2$ . This means that a spot sale (purchase) of a foreign. currency will lead to two-way flows 2 days after the trade date, regularly. $T+2$ is usually called the spot date.  

It is important to expect that the number of days to settlement in general refers to business days. This means that in order to be able to interpret $T+2$ correctly, the market professional would need to pin down the corresponding holiday convention.  

Before discussing other market conventions, we can mention two additional terms that are related to the preceding dates. The settlement date is sometimes called the value date in contracts. Cash changes hands at the value date. Finally, in swap-type contracts, there will be the deal date. (i.e., when the contract is signed), but the swap may not begin until the effective date. The latter is. the actual start date for the swap contract and will be at an agreed-upon later date..  

# 2.4.2.1 Regulatory update following the GFC  

On April 23, 2014, The Depository Trust & Clearing Corporation (DTCC) released a white paper outlining the rationale for supporting a move to shorten the settlement cycle (SsC) in the US financial markets for equities, corporate and municipal bonds, and unit investment trust (UIT) trades. The rationale for the reduction from $T+3$ (trade date plus 3 days) to $T+2$ (trade date plus 2 days) is that a shortened settlement cycle will reduce the following: counterparty risk exposure, procycli-. cality, NSCC's liquidity need, and overall operational and industry risk.22  
