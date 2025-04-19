---
tags:
  - bond_futures
  - delivery_options
  - quality_option
  - timing_option
  - treasury_futures
aliases:
  - TYU1
  - Treasury Note Futures
  - US Treasury Futures
key_concepts:
  - Conversion factors
  - Daily settlement
  - Deliverable basket
  - Futures contract mechanics
  - Quality and timing options
---

# 11.4 MECHANICS OF US TREASURY NOTE AND BOND FUTURES  

As mentioned at the start of the chapter, futures and forwards are essentially similar, in that they require the purchase or sale of bonds in the future, but futures embed various delivery options and require daily settlement.  

TABLE 11.5 The Deliverable Basket into TYU1.   


<html><body><table><tr><td colspan="2"></td><td>Conversion</td></tr><tr><td>Coupon</td><td>Maturity</td><td>Factor</td></tr><tr><td>2.875</td><td>05/15/28</td><td>0.8338</td></tr><tr><td>2.875</td><td>08/15/28</td><td>0.8286</td></tr><tr><td>1.250</td><td>04/30/28</td><td>0.7474</td></tr><tr><td>1.250</td><td>03/31/28</td><td>0.7474</td></tr><tr><td>3.125</td><td>11/15/28</td><td>0.8376</td></tr><tr><td>2.625</td><td>02/15/29</td><td>0.8039</td></tr><tr><td>2.375</td><td>05/15/29</td><td>0.7836</td></tr><tr><td>1.625</td><td>08/15/29</td><td>0.7320</td></tr><tr><td>1.750</td><td>11/15/29</td><td>0.7331</td></tr><tr><td>1.500</td><td>02/15/30</td><td>0.7105</td></tr><tr><td>0.625</td><td>05/15/30</td><td>0.6462</td></tr><tr><td>0.625</td><td>08/15/30</td><td>0.6382</td></tr><tr><td>0.875</td><td>11/15/30</td><td>0.6476</td></tr><tr><td>1.125</td><td>02/15/31</td><td>0.6577</td></tr></table></body></html>  

To present this material, the text focuses on the 10-year US Treasury note futures contract maturing in September 2021, with the symbol "TYU1." The ${}^{\mathsf{c e}}\mathsf{T Y}^{\mathsf{s}}$ is the code for the 10-year contract; "U" is the code for September;. and $^{\circ\circ}1^{\circ\circ}$ denotes the last digit of the maturity year, here, 2021. The seller,. or short, of one contract commits to sell or deliver $\$100,000$ face amount of one of the deliverable Treasury notes listed in Table 11.5 at some time in the delivery month, in this case, September 2021. The buyer, or long, commits to buy or take delivery of $\$100,000$ face amount of the Treasury note chosen by the seller at the time chosen by the seller. It is the seller, therefore, that has these two delivery options: the quality option, which is the option to choose which note to sell, or deliver, and the timing option, which is the option to choose when in the delivery month to sell. There are, in fact, two other delivery options, which are discussed later in the chapter: the end-of-month option, which arises because the last trading day of the futures contract (September 21, 2021, for TYU1) is seven business days before the last delivery date (September 30, 2021, for TYU1); and the wild-card option, which arises because the futures settlement price on a given day is set hours before an intention to deliver has to be declared.  

Once a seller has chosen which bond to deliver and when to deliver it, the price at which the bond is sold is the futures price at the time of delivery times the bond's conversion factor, as listed in Table 11.5. These conversion factors are fixed over the life of the futures contract. The reason for and computation of conversion factors is discussed next. For now, to focus on the mechanics, say that the futures price at expiration is 133.86. If the seller delivers the 2.875s of 05/15/2028, with a conversion factor of 0.8338, the price received is $133.86\times{0.8338}=111.61$ per 100 face amount. If the seller delivers the 1.125s of 02/15/2031, with a conversion factor of 0.6577, the price received is $133.86\times0.6577=88.04$ . Also, as with any bond sale, the seller through a futures contract receives accrued interest as of delivery.  

IABLE 11.6 Settlement Prices of TYU1, from May 10, 2021, to May 28, 2021, and the Daily Settlement to a Long Position of One Contract.. Changes Are in Ticks (32nds) and Daily Settlement Payments Are in Dollars.   


<html><body><table><tr><td></td><td></td><td></td><td>Daily</td></tr><tr><td>Date</td><td>Price</td><td>Change</td><td>Settlement</td></tr><tr><td>05/10/2021</td><td>131-24</td><td></td><td></td></tr><tr><td>05/11/2021</td><td>131-19</td><td>-5</td><td>-156.25</td></tr><tr><td>05/12/2021</td><td>131-01</td><td>-18</td><td>-562.50</td></tr><tr><td>05/13/2021</td><td>131-10</td><td>9</td><td>281.25</td></tr><tr><td>05/14/2021</td><td>131-17+</td><td>7.5</td><td>234.38</td></tr><tr><td>05/17/2021</td><td>131-15+</td><td>-2</td><td>-62.50</td></tr><tr><td>05/18/2021</td><td>131-16+</td><td>1</td><td>31.25</td></tr><tr><td>05/19/2021</td><td>131-04</td><td>-12.5</td><td>-390.63</td></tr><tr><td>05/20/2021</td><td>131-19</td><td>15</td><td>468.75</td></tr><tr><td>05/21/2021</td><td>131-17+</td><td>-1.5</td><td>-46.88</td></tr><tr><td>05/24/2021</td><td>131-23+</td><td>6</td><td>187.50</td></tr><tr><td>05/25/2021</td><td>132-02+</td><td>11</td><td>343.75</td></tr><tr><td>05/26/2021</td><td>132-01</td><td>-1.5</td><td>-46.88</td></tr><tr><td>05/27/2021</td><td>131-25</td><td>-8</td><td>-250.00</td></tr><tr><td>05/28/2021</td><td>131-30</td><td>5</td><td>156.25</td></tr></table></body></html>  

Futures contracts are subject to daily settlement. Throughout a trading day, market forces determine futures prices, and, at the end of each day, the exchange on which the futures trade determines a settlement price. For liquid contracts, like Treasury futures, the settlement price is usually the last traded price of the day. For some contracts, however, in exceptional circumstances, the exchange may substitute its judgment so that the daily settlement price reflects the end-of-day market level. In any case, Table 11.6 reports daily settlement prices for TYU1 from May 10, 2021, to May 28, 2021, per 100 face amount of the underlying bonds. Note that prices are reported in terms of "ticks" or 32nds, so that 131-24 denotes a price of $131+24/32$ or 131.75. Note too, that $^{\circ\circ}+{}^{\circ\circ}$ means one half, so that $131{-}17+$ denotes a price of $131+17.5/32$ , or 131.546875. The third column in the table shows the change in the daily settlement price, also measured in ticks, so that the settlement price fell by five ticks from May 10, 2021, to May 11, 2021.  

The daily settlement feature of futures contracts requires that changes in the price of the contract be settled daily. These daily payments, for a long position of one contract in TYU1, are given in the last column of Table 11.6.  

From May 10, 2021, to May 11, 2021, for example, because the price of TYU1 falls by five ticks (per 100 face amount), the buyer loses value and must pay $(5/32)\%\times\S100,000=\S156.25$ , which the exchange passes on to the seller. From May 12, 2021, to May 13, 2021, on the other hand, the settlement price increases by nine ticks, which means that the seller loses value and must pay $(9/32)\%\times\S100,000=\S281.25$ , which the exchange passes on to the buyer. All futures market participants must post maintenance margin, usually in the form of a fixed number of dollars per contract, to protect the exchange against their defaulting on daily settlement payments.  

With these mechanics explained, the differences between forward and futures contracts can be summarized as follows. First, forward contracts require the purchase and sale of a particular underlying security on a particular date, while futures contracts give the seller the right to choose the security (from a basket of deliverables) and to choose the date (in the delivery month). Second, the profit or loss from a forward contract is realized at the expiration of the contract, while the profit or loss from a futures contract is realized over time. Consider the futures prices in Table 11.6, which, over the period, increase a total of six ticks, from 131-24 to 131-30. Were this a forward contract, the buyer's profit would have increased by six ticks as of the expiration date, in this case, September 30, 2021. But because this is a futures contract with daily settlement, the buyer receives these six ticks as the price changes - some days receiving cash, some days paying cash, but cumulatively, from May 10, 2021, to May 28, 2021, receiving a total of six ticks. A related implication of this reasoning is that, as of May 28, 2021, the forward contract has value - it is a claim on six ticks at expiration - while the futures contract is worth zero - its value has already been fully paid. Put another way, after the settlement payment on May 28, 2021, the buyer of the futures contract on May 10, 2021, at 131-24 has a zero-value position, as does a new buyer of the contract on May 28, 2021, at 131-30.3  
