---
tags:
  - cme_nymex
  - commodity_futures
  - contract_specifications
  - crude_oil
  - futures_contract
  - wti_crude_oil
aliases:
  - Futures Contract Parameters
  - WTI Crude Oil Contract
key_concepts:
  - CME NYMEX
  - Contract size
  - Crude oil futures
  - Futures contract parameters
  - Minimum fluctuation
---

# 7.2 PARAMETERS OF A FUTURES CONTRACT  

To broaden the examination of futures and forwards, in this section, we concentrate on commodities that are generally traded via futures contracts on organized exchanges. Thus, in contrast to. currency markets, exchange traded commodity futures are more liquid than OTC commodity. forwards.  

Crude oil is one of the economically most important commodities and crude oil futures are among the most liquidly traded commodity futures. Advanced financial engineering methodologies have been extended to crude oil. These include simple swaps and calendar swaps, discussed in this chapter, as well as options, implied volatility indices, and crude oil volatility index futures, discussed in future chapters. Crude oil is also one of the largest constituents in commodity indices such as the GSCI on which many commodity-related structured products are written. Therefore, we use a crude oil futures contract to introduce key concepts about futures markets. CME and ICE are the exchanges with the most liquid crude oil futures contracts.  

It may come initially as a surprise that crude oil is not a very homogeneous commodity. This creates various trading opportunities but may also be a limitation to arbitrage strategies and require careful consideration in financial engineering applications. There are different grades of crude oil. depending on its chemical composition and its sulfur content in particular. The New York Mercantile Exchange (NYMEX) designates crude oil with less than $0.42\%$ sulfur as sweet. Crude oil containing higher levels of sulfur is called sour crude oil and is considered lower quality. Light sweet crude oil is of higher quality since it can be more easily refined into gasoline, kerosene, and high-quality diesel (gas oil) and typically trades at a premium to sour crude oil on futures. exchanges. In addition to differences in grade, the geographical location also has to be taken account. West Texas Intermediate (WTI) and the North Sea Brent crude are both light sweet grades and used as benchmarks in oil pricing.  

The following example shows the contract specification of the WTI Crude Oil Futures Contract on CME NYMEX/Globex. The terminologies introduced here apply to all futures contracts, not just commodity futures.  

# EXAMPLE: WTI CRUDE OIL CONTRACT ON CME NYMEX/GLOBEX  

1. Contract size: 1000 barrels (bbl) ( ${\sim}42{,}000$ US gallons/159,000 1).   
2. Units of trading: Any multiples of $1000~\mathrm{bbl}$ -   
3. Minimum fluctuation: $\$0.01$ per bbl.   
4. Price quote: US dollars and cents per bbl.   
5. Contract months: Crude oil futures are some of the most flexible commodity contracts due to the large range of contract months. Crude oil futures are listed 9 years forward using the following listing schedule: consecutive months are listed for the current year and the next 5 years; in addition, the June and December contract months are listed. beyond the sixth year. On June 23, 2014, the most distant contract month available was December 2022.   
6. Delivery: Delivery shall be made free-on-board (FOB?)' at any pipeline or storage. facility in Cushing, Oklahoma, with pipeline access to Enterprise, Cushing storage or Enbridge, Cushing storage.   
7. Delivery grades: Because of quality differences, there must be some standardization so. that the buyer knows what she is receiving. Various domestic crudes such as WTI, New Mexican Sweet, Oklahoma Sweet and Foreign Crudes (at a discount of 15-55 cents per bbl) such as UK Brent Blend and Nigeria Bonny Light, for example. For details, see the. CME/NYMEX rulebook.2   
8. Last trading day: The business day prior to the 15th calendar day of the contract month.   
9. Last delivery day: Delivery shall take place no earlier than the first calendar day of the delivery month and no later than the last calendar day of the delivery month.   
10. Trading hours: Open outcry, 9:00 a.m. to $2{:}30~\mathrm{p.m}$ . Chicago time, Monday through Friday. Electronic, $5\mathrm{p.m}$ . to $4{:}15\mathrm{p.m}$ . Chicago time, Sunday through Friday..   
11. Daily price limit: $\$10.00$ per bbl above or below the previous day's settlement price for such contract month.  

Table 7.1 provides prices, volumes, and open interest for CME WTI crude oil contracts with maturity up to 1 year as of June 20, 2014. Volume represents the total amount of trading activity or WTI futures contracts that were traded on that day. The August 2014 contract, for example, had a volume of 213,130 which corresponds to approximately 213.1 million bbl with an estimated value of $\$24.5$ billion (at an assumed oil price of $\$115/\mathrm{bbl}$ . Open interest is defined as the total number of outstanding contracts that are held by market participants at the end of each day. Note that for each seller of a futures contract, there is a buyer of that contract. A seller and a buyer combine to create only one contract. Hence, to calculate the total open interest, we need only to know the totals from one side or the other, buyers or sellers, not the sum of both. The total open interest across all contracts on that day is not given in the table, but was 1,709,934 with an estimated market value of almost $\$200$ billion (at a price of $\$115/601$  

<html><body><table><tr><td colspan="4">Table 7.1 WTI Crude Oil Contract Prices, Volume, and Open Interest</td></tr><tr><td>Month</td><td>(Settlement)Price</td><td>Volume</td><td>Open Interest</td></tr><tr><td>July 14</td><td>107.26</td><td>31,672</td><td>24,798</td></tr><tr><td>August 14</td><td>106.83</td><td>213,130</td><td>312,344</td></tr><tr><td>September14</td><td>105.97</td><td>72,503</td><td>186,919</td></tr><tr><td>October 14</td><td>104.9</td><td>36,431</td><td>126,676</td></tr><tr><td>November14</td><td>103.85</td><td>20,751</td><td>66,259</td></tr><tr><td>December14</td><td>102.86</td><td>51,854</td><td>229,847</td></tr><tr><td>January 15</td><td>101.88</td><td>6,744</td><td>68,163</td></tr><tr><td>February 15</td><td>100.93</td><td>1,548</td><td>35,424</td></tr><tr><td>March 15</td><td>100.04</td><td>4,301</td><td>64,348</td></tr><tr><td>April 15</td><td>99.15</td><td>630</td><td>24,723</td></tr><tr><td>May 15</td><td>98.31</td><td>890</td><td>23,460</td></tr><tr><td>June 15</td><td>97.55</td><td>11,556</td><td>100,963</td></tr><tr><td colspan="4">Source:CMEGLOBEXonJune20,2014.</td></tr></table></body></html>  

The contract month with an expiration date closest to the current date is called the front month. or prompt month. On June 23, 2014, the front month is July 2014, i.e., the July 2014 contract is the shortest duration crude oil contract that could be purchased in the futures market. The front month contract is also referred to as the nearby or nearest contract..  

Contracts that are a month or more behind the front month contracts are referred to as back month contracts. The liquidity, as approximated by volume, for front month contracts given in the table is higher than for back month contracts. This is generally the case and applies not just to this particular day and this commodity but also to other commodities. Therefore, a trader that seeks the most liquid contract to minimize transaction costs would typically choose a nearby contract. Considerations other than liquidity determine however which contract month is chosen by a particular trader and we discuss this in further detail below. Consider an oil producer that hedges her production using futures. If the hedger liquidates the futures contract and the asset before contract maturity, the hedger bears basis risk, because the futures price and the spot price may not move in lockstep before the delivery date. In energy commodity markets, there are in fact three primary types of basis risk: locational basis risk, product/quality basis risk, and calendar (spread) basis risk. Assume that the hedger in our example produces oil in Saudi Arabia, for example. If the hedge is designed to hedge Saudi oil that will be produced in September of a given year, for example, and a NYMEX wTI futures with December maturity in the same year is used as a hedge, then all three risks are relevant. First, the delivery location specified in the futures contract will be different from that of the physical location in Saudi Arabia where the oil will be produced. Second, the sulfur content will be different since Saudi oil is heavier, thus not qualifying as a delivery grade for the NYMEX WTI contract. Third, there is a difference of 3 months between the delivery date specified in the futures contract and the expected physical delivery of the oil.  
