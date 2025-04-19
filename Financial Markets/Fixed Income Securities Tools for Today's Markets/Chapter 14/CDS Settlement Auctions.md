---
tags:
  - bond_liquidity
  - cds_auction
  - cds_settlement
  - corporate_bonds
  - default_event
  - hertz_cds
  - physical_settlement
aliases:
  - CDS Auctions
  - CDS Settlement
  - Hertz CDS Auction
key_concepts:
  - Auction phase one
  - Bond price observation
  - CDS settlement challenges
  - Dealer bids and offers
  - Deliverable obligations list
  - Hertz CDS auction process
  - Inside market midpoint
  - Net CDS positions
  - Physical settlement requests
  - Physical settlement squeeze
---

# 14.11 CDS SETTLEMENT AUCTIONS  

Two challenges typical in the settlement of derivatives trades apply just as well to CDS. First, requiring that all protection buyers physically settle contracts leaves them open to a squeeze. As discussed earlier, protection buyers do not necessarily own the underlying bonds and the supply of bonds eligible for delivery might be subject to manipulation. Second, bond prices may. not be readily observable for the purpose of cash settlement, because corporate bond liquidity - even if satisfactory in normal times - may be quite limited through a default. Industry-run settlement auctions are designed tc cope with both of these fundamental challenges..  

TABLE 14.13 List of Deliverables for Hertz Corporation CDS Auction, June 23, 2020.   


<html><body><table><tr><td>Description</td><td>Maturity</td></tr><tr><td>4.125%Sr.Notes</td><td>10/15/2021</td></tr><tr><td>7.625%Sr.Secured2ndPriorityNotes 6.250%Sr.Notes</td><td>06/01/2022 10/15/2022</td></tr><tr><td>5.500%Sr.Notes</td><td>03/30/2023</td></tr><tr><td>LetterofCreditDisbursements</td><td>12/18/2023</td></tr><tr><td>5.500%Sr.Notes</td><td>10/15/2024</td></tr><tr><td>7.125%Sr.Notes</td><td></td></tr><tr><td>6.000%Sr.Notes</td><td>08/01/2026</td></tr><tr><td></td><td>01/15/2028</td></tr></table></body></html>  

Hertz filed for bankruptcy on May 22, 2020, and, on June 24, 2020, an. auction was held to settle CDS referencing Hertz. Some physical settlement. took place as part of the auction, and the final auction price of 26.375 was. used for cash settlement. This section describes the CDS auction process in the context of this Hertz CDS auction.21.  

A single-name CDS contract specifies reference obligations of the reference entity, together with a set of rules, that determine whether an event of default has occurred and, if so, which bonds are deliverable, or eligible to be delivered, for the purposes of physical settlement. The final list of deliverable obligations into the Hertz CDS auction is given in Table 14.13.  

The auction itself is divided into two phases. In phase one, participating. dealers submit i) bids and offers for purchase and sale of deliverable obligations, with a predefined quotation size and maximum bid-offer spread; and ii) physical settlement requests. Table 14.14 lists the bids and offers of the dealers in the Hertz auction, with the bids sorted in descending order and the offers in ascending order. An inside market midpoint (IMM) is determined from these bids and offers as follows. First, discard all rows with crossing or. touching markets (i.e., where the bid price exceeds or equals the offer price). In Table 14.14, the first four rows constitute crossing or touching markets,. and are discarded. Second, using the top half of the remaining rows (rounded up, if necessary), compute the average of the bids and offers and round to the nearest eighth per 100 face amount. In Table 14.14, the bottom six rows remain. Therefore, using only the top three rows, the average of the bids and offers, which are bolded, is 25.333, which, rounded to the nearest eighth, gives an IMM of 25.375.  

TABLE 14.14 Dealer Initial Markets, Hertz Corporation CDS Auction, June 24, 2020.   


<html><body><table><tr><td>Dealer</td><td>Bid</td><td>Offer</td><td>Dealer</td></tr><tr><td>Citigroup</td><td>26.0</td><td>22.5</td><td>Morgan Stanley</td></tr><tr><td>Credit Suisse</td><td>26.0</td><td>24.0</td><td>Barclays</td></tr><tr><td>Deutsche Bank</td><td>26.0</td><td>24.5</td><td>Goldman Sachs</td></tr><tr><td>RBC Capital Markets</td><td>25.5</td><td>25.5</td><td>Bank of America</td></tr><tr><td>BNP Paribas</td><td>24.5</td><td>26.0</td><td>J.P. Morgan Securities</td></tr><tr><td>J.P. Morgan Securities</td><td>24.0</td><td>26.5</td><td>BNP Paribas</td></tr><tr><td>Bank of America</td><td>23.5</td><td>27.5</td><td>RBC Capital Markets</td></tr><tr><td>Goldman Sachs</td><td>22.5</td><td>28.0</td><td>Citigroup</td></tr><tr><td>Barclays</td><td>22.0</td><td>28.0</td><td>Credit Suisse</td></tr><tr><td>Morgan Stanley</td><td>20.5</td><td>28.0</td><td>Deutsche Bank</td></tr><tr><td>Inside Market Midpoint</td><td colspan="3">25.375</td></tr></table></body></html>  

Turning to the second part of phase one of the auction, Table 14.15. shows the physical settlement requests of the participating dealers. These requests must match the direction and size of their respective net CDS positions. Goldman Sachs and its clients, for example, by offering to deliver 140.0 million face amount of deliverable obligations, must, on net, have. bought protection on at least 140.0 million CDS notional amount. Put another way, Goldman and its clients are requesting to collect on their having bought a net of 140.0 million notional amount of CDS by delivering 140.0 million face amount of deliverable obligations and receiving $\$140$ million. J.P. Morgan Securities and its clients, on the other side, by. bidding to take 20.0 million of deliverable obligations, must, on net, have sold protection on at least 20.0 million CDS notional amount. They are requesting to settle their CDS obligations by taking delivery of 20.0 million of deliverable obligations and paying. $\$20$ million. Taking the physical. settlement requests all together, there are total requests to sell or deliver $\$143.525$ million face amount and total requests to buy or take delivery on. $\$42$ million, leaving a net open interest (NOI) to sell of. $\$111.525$ million.  

Before proceeding to phase two of the auction, a note is made of adjust-. ment amounts. To provide an incentive for dealers to submit competitive. bids and offers, dealers are penalized for submitting off-market bids and. offers, where "off-market" is judged relative to the IMM and NOI. More specifically, in the case of the Hertz auction, there was a NOI to sell and the IMM was 25.375. It follows from Table 14.14 that the bids and offers of Citigroup, Credit Suisse, and Deutsche Bank at 26.0-28.0, and those of. RBC Capital Markets at 25.5-27.5, were too high in a market where there were more sellers than buyers. Therefore, these dealers had to pay adjustment amounts equal to the difference between their above-market bids and the IMM times the quotation amount: $\$2$ or $\$12,500$ for Citigroup, Credit Suisse, and Deutsche Bank, and $\$2$ million $\times(25.5-25.375)/100$ , or $\$2,500$ for RBC Capital Markets. In phase one auctions with NOI to buy, adjustment amounts are levied on dealers with bids and offers below the IMM.  

TABLE 14.15 Physical Settlement Requests, Hertz Corporation CDS Auction, June 24, 2020. Amounts Are in. $\$1$ Millions.   


<html><body><table><tr><td colspan="2">Dealer Size</td></tr><tr><td>Offers</td><td></td></tr><tr><td>Bank of America</td><td>0.0</td></tr><tr><td>BNP Paribas</td><td>3.525</td></tr><tr><td>Citigroup</td><td>10.0</td></tr><tr><td>Deutsche Bank</td><td>0.0</td></tr><tr><td>Goldman Sachs</td><td>140.0</td></tr><tr><td>Morgan Stanley</td><td>0.0</td></tr><tr><td>RBC Capital Markets</td><td>0.0</td></tr><tr><td>Total Sell Requests</td><td>143.525</td></tr><tr><td>Bids</td><td></td></tr><tr><td>Barclays</td><td>7.0</td></tr><tr><td>Credit Suisse</td><td>15.0</td></tr><tr><td>J.P. Morgan Securities</td><td>20.0</td></tr><tr><td>Total Buy Requests</td><td>42.0</td></tr><tr><td>Net Open Interest (Sell)</td><td>111.525</td></tr></table></body></html>  

Phase two of the auction takes place a few hours after the results of phase one. The purpose of phase two is to determine a final auction price,. defined as the clearing price for the NOI established in phase one. In phase. two, market participants - including, but not limited to the participating dealers in phase one - submit limit orders to buy, if the NOI was to sell, or limit orders to sell, if the NOI was to buy. Furthermore, to ensure the sensible result that the final auction price not be too high relative to the IMM if the NOI is to sell, or not be too low relative to the IMM if the NOI is to buy, limit order prices are constrained by a cap amount, usually set to half the maximum bid-offer spread in phase one. In the Hertz auction, the cap amount was half of two, or one. And, because there was a NOI to sell, the limit orders to buy in phase two were constrained to be less than or equal to the IMM of 25.375 plus the cap amount of one, or 26.375.  

TABLE 14.16  Goldman Sachs Limit Orders, Hertz Corporation CDS Auction, June 24, 2020. Amounts Are. $\$1$ Millions.   


<html><body><table><tr><td>Bid Price</td><td>Size</td></tr><tr><td>26.375</td><td>42</td></tr><tr><td>25.000</td><td>10</td></tr><tr><td>24.000</td><td>10</td></tr><tr><td>23.750</td><td>5</td></tr><tr><td>23.500</td><td>24</td></tr><tr><td>23.250</td><td>10</td></tr><tr><td>23.000</td><td>23</td></tr><tr><td>22.500</td><td>2</td></tr><tr><td>20.000</td><td>14</td></tr></table></body></html>  

Table 14.16 shows the limit orders to buy submitted by Goldman Sachs in phase two of the Hertz auction. On behalf of itself and its customers, Goldman Sachs bid to purchase $\$42$ million face amount at a price of 26.375; an additional $\$10$ million at a price of 25.000; and so forth. Note that bids from the initial market in phase one of the auction carry over into this phase, so that Goldman Sachs' bid at 22.5 for the predefined size of $\$2$ million in Table 14.14 appears as the penultimate row of Table 14.16.22  

All of the limit orders to buy Hertz bonds are collected and ordered by price, from high to low. Then, following the rules of a Dutch auction, the final auction price is set such that the quantity of limit orders to buy at that price or above matches the. $\$111.525$ million NOI to sell. In the Hertz auction, at the highest allowable bid price of 26.375, there were limit orders to purchase. $\$118.50$ million face amount, which is more than. the NOI available for sale. Therefore, the final auction price was set at 26.375 and all bidders at that price were allocated a pro rata amount of. the available $\$111,4525$ million. Goldman Sachs, for example, with its limit. order to buy. $\$42$ million at 26.375, was able to purchase. $\$42$ million $\times$ $\$111.525/\$118.50$ , or $\$39.528$ million face amount through the auction..  

To summarize, the auction had two outcomes. First, $\$143.525$ million face amount of deliverable Hertz bonds were sold by the dealers or their customers in the "Offers" part of Table 14.15 at a price of 26.375 to the dealers or their customers in the "Bids" part of the table -- $\$42$ million - and to the market participants awarded allocations in phase two of the auction - $\$111.525$ million. Second, all Hertz CDS settled at the final auction price of 26.375. CDS counterparties who chose cash settlement used this final price as the recovery amount, that is, protection buyers received from protection sellers the notional amount of their $\mathrm{CDS}\times(100\%$ $-~26.375\%$ , or $73.625\%$ . Counterparties who chose physical settlement worked through their dealers as follows. Protection buyers delivered deliverable obligations of their choice for 26.375 and received a cash settlement of 73.625, for total proceeds of 100. Protection sellers paid 26.375 for any bond delivered to them and paid a cash settlement of 73.625, again, for total proceeds of 100.  

This section concludes by noting that, while CDS auctions have gen-. erally been successful in settling at reasonable final prices, success is not assured. A recent example of failure was the auction to settle Europcar Mobility Group CDS on January 13, 2021. Just before the auction, deliverable bonds were trading at about 70, and phase one of the auction resulted in an IMM of 73 and a NOI to buy 43.3 million. But in phase two, limit orders to sell totaled only $\epsilon35.9$ million. Hence, with no price high enough to. match limit sell orders to the NOI to buy, the final auction price, by rule, was set to 100. Buyers of CDS protection received nothing. Some commentators attributed the lack of limit sell orders to the fact that Europcar restructuring. agreements prevented many bondholders from selling their bonds through the CDS auction. Other commentators, however, claimed that there were more than enough bonds available to cover the NOI, but potential sellers simply did not show up at the auction.23  
