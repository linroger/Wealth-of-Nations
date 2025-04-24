# CASH FLOW ENGINEERING AND ALTERNATIVE CLASSES (COMMODITIES AND HEDGE FUNDS)  

# 7  

# CHAPTER OUTLINE  

7.1 Introduction . 212   
7.2 Parameters of a Futures Contract .. 212   
7.3 The Term Structure of Commodity Futures Prices . 215   
7.3.1 Backwardation and Contango.. . 215   
7.3.2 Contractual Equation and Synthetic Commodities . 216   
7.3.3 Convenience Yield .. 219   
7.3.4 Cash and Carry Arbitrage... 219   
7.3.5 Another Interpretation of Spot Futures Parity... 221   
4 Swap Engineering for Commodities . 221   
7.4.1 Swap Cash Flow Engineering in Commodity Markets. 222   
7.4.2 Pricing and Valuation of Commodity Swaps.. 222   
7.4.2.1 Calculating swap prices from the futures curve . .224   
7.4.3 Real-World Complications .. 227   
7.4.4 Other Commodity Swaps . 228   
7.5 The Hedge Fund Industry . . 228   
7.5.1 Alternative Investment Funds .. 229   
7.5.2 Hedge Fund Regulation. 229   
7.5.3 Hedge Fund Investment Mandate and Techniques . . 230   
7.5.4 Hedge Funds’ Legal Structure. 230   
7.5.5 Incentives... . 231   
7.5.6 Strategies . 232   
7.5.7 Prime Brokers .. 233   
7.6 Conclusions. 233   
Suggested Reading . 234   
Exercises . 234  

# 7.1 INTRODUCTION  

We have so far applied our cash flow engineering methodology to fixed income and currency instruments. Unlike these asset classes, commodities incur significant storage costs and this realworld complication needs to be taken into account in commodities cash flow engineering. For example, in contrast to currencies which are a homogeneous asset, commodities differ in their quality or grade. We provide more examples of the replication of forwards, futures, and swaps, and examine cash flow engineering in commodities. In contrast to interest rates and equities, commodities are tangible assets. This makes them useful for illustrating some of the abstract derivatives market-related concepts such as the term structure of futures prices as well as open interest and volume. Three practical reasons motivate a careful look at financial engineering applications in commodity markets. As interest in commodities investing and hedging has increased, this has also led to what has been described as the financialization of commodities. Institutional investors are increasingly investing in commodities through commodity futures and swaps. ETFs linked to various commodity indices and commodities have been launched, thus allowing retail investors to invest in commodities as well.  

# 7.2 PARAMETERS OF A FUTURES CONTRACT  

To broaden the examination of futures and forwards, in this section, we concentrate on commodities that are generally traded via futures contracts on organized exchanges. Thus, in contrast to currency markets, exchange traded commodity futures are more liquid than OTC commodity forwards.  

Crude oil is one of the economically most important commodities and crude oil futures are among the most liquidly traded commodity futures. Advanced financial engineering methodologies have been extended to crude oil. These include simple swaps and calendar swaps, discussed in this chapter, as well as options, implied volatility indices, and crude oil volatility index futures, discussed in future chapters. Crude oil is also one of the largest constituents in commodity indices such as the GSCI on which many commodity-related structured products are written. Therefore, we use a crude oil futures contract to introduce key concepts about futures markets. CME and ICE are the exchanges with the most liquid crude oil futures contracts.  

It may come initially as a surprise that crude oil is not a very homogeneous commodity. This creates various trading opportunities but may also be a limitation to arbitrage strategies and require careful consideration in financial engineering applications. There are different grades of crude oil depending on its chemical composition and its sulfur content in particular. The New York Mercantile Exchange (NYMEX) designates crude oil with less than $0.42\%$ sulfur as sweet. Crude oil containing higher levels of sulfur is called sour crude oil and is considered lower quality. Light sweet crude oil is of higher quality since it can be more easily refined into gasoline, kerosene, and high-quality diesel (gas oil) and typically trades at a premium to sour crude oil on futures exchanges. In addition to differences in grade, the geographical location also has to be taken account. West Texas Intermediate (WTI) and the North Sea Brent crude are both light sweet grades and used as benchmarks in oil pricing.  

The following example shows the contract specification of the WTI Crude Oil Futures Contract on CME NYMEX/Globex. The terminologies introduced here apply to all futures contracts, not just commodity futures.  

# EXAMPLE: WTI CRUDE OIL CONTRACT ON CME NYMEX/GLOBEX  

1. Contract size: 1000 barrels (bbl) $\cdot\mathord{\sim}42.000$ US gallons/159,000 l).   
2. Units of trading: Any multiples of $1000{\ b b l}$ .   
3. Minimum fluctuation: $\$0.01$ per bbl.   
4. Price quote: US dollars and cents per bbl.   
5. Contract months: Crude oil futures are some of the most flexible commodity contracts due to the large range of contract months. Crude oil futures are listed 9 years forward using the following listing schedule: consecutive months are listed for the current year and the next 5 years; in addition, the June and December contract months are listed beyond the sixth year. On June 23, 2014, the most distant contract month available was December 2022.   
6. Delivery: Delivery shall be made free-on-board (“FOB”)1 at any pipeline or storage facility in Cushing, Oklahoma, with pipeline access to Enterprise, Cushing storage or Enbridge, Cushing storage.   
7. Delivery grades: Because of quality differences, there must be some standardization so that the buyer knows what she is receiving. Various domestic crudes such as WTI, New Mexican Sweet, Oklahoma Sweet and Foreign Crudes (at a discount of 15 55 cents per bbl) such as UK Brent Blend and Nigeria Bonny Light, for example. For details, see the CME/NYMEX rulebook.2   
8. Last trading day: The business day prior to the 15th calendar day of the contract month.   
9. Last delivery day: Delivery shall take place no earlier than the first calendar day of the delivery month and no later than the last calendar day of the delivery month.   
10. Trading hours: Open outcry, 9:00 a.m. to $2{:}30\ \mathrm{p.m}$ . Chicago time, Monday through Friday. Electronic, $5\ \mathrm{p.m}$ . to $4{:}15\ \mathrm{p.m}$ . Chicago time, Sunday through Friday.   
11. Daily price limit: $\$10.00$ per bbl above or below the previous day’s settlement price for such contract month.  

Table 7.1 provides prices, volumes, and open interest for CME WTI crude oil contracts with maturity up to 1 year as of June 20, 2014. Volume represents the total amount of trading activity or WTI futures contracts that were traded on that day. The August 2014 contract, for example, had a volume of 213,130 which corresponds to approximately 213.1 million bbl with an estimated value of $\$24.5$ billion (at an assumed oil price of $\$123/6b l$ ). Open interest is defined as the total number of outstanding contracts that are held by market participants at the end of each day. Note that for each seller of a futures contract, there is a buyer of that contract. A seller and a buyer combine to create only one contract. Hence, to calculate the total open interest, we need only to know the totals from one side or the other, buyers or sellers, not the sum of both. The total open interest across all contracts on that day is not given in the table, but was 1,709,934 with an estimated market value of almost $\$200$ billion (at a price of $\$123/6b l_{,}$ ).  

<html><body><table><tr><td colspan="4">Table 7.1 WTI Crude Oil Contract Prices, Volume, and Open Interest</td></tr><tr><td>Month</td><td>(Settlement) Price</td><td>Volume</td><td>Open Interest</td></tr><tr><td>July 14</td><td>107.26</td><td>31,672</td><td>24,798</td></tr><tr><td>August 14</td><td>106.83</td><td>213,130</td><td>312,344</td></tr><tr><td>September 14</td><td>105.97</td><td>72,503</td><td>186,919</td></tr><tr><td>October 14</td><td>104.9</td><td>36,431</td><td>126,676</td></tr><tr><td>November14</td><td>103.85</td><td>20,751</td><td>66,259</td></tr><tr><td>December 14</td><td>102.86</td><td>51,854</td><td>229.847</td></tr><tr><td>January 15</td><td>101.88</td><td>6,744</td><td>68,163</td></tr><tr><td>February 15</td><td>100.93</td><td>1,548</td><td>35,424</td></tr><tr><td>March 15</td><td>100.04</td><td>4,301</td><td>64,348</td></tr><tr><td>April 15</td><td>99.15</td><td>630</td><td>24,723</td></tr><tr><td>May 15</td><td>98.31</td><td>890</td><td>23.,460</td></tr><tr><td>June 15</td><td>97.55</td><td>11,556</td><td>100,963</td></tr><tr><td colspan="4">Source:CME GLOBEX onJune20,2014.</td></tr></table></body></html>  

The contract month with an expiration date closest to the current date is called the front month or prompt month. On June 23, 2014, the front month is July 2014, i.e., the July 2014 contract is the shortest duration crude oil contract that could be purchased in the futures market. The front month contract is also referred to as the nearby or nearest contract.  

Contracts that are a month or more behind the front month contracts are referred to as back month contracts. The liquidity, as approximated by volume, for front month contracts given in the table is higher than for back month contracts. This is generally the case and applies not just to this particular day and this commodity but also to other commodities. Therefore, a trader that seeks the most liquid contract to minimize transaction costs would typically choose a nearby contract. Considerations other than liquidity determine however which contract month is chosen by a particular trader and we discuss this in further detail below. Consider an oil producer that hedges her production using futures. If the hedger liquidates the futures contract and the asset before contract maturity, the hedger bears basis risk, because the futures price and the spot price may not move in lockstep before the delivery date. In energy commodity markets, there are in fact three primary types of basis risk: locational basis risk, product/quality basis risk, and calendar (spread) basis risk. Assume that the hedger in our example produces oil in Saudi Arabia, for example. If the hedge is designed to hedge Saudi oil that will be produced in September of a given year, for example, and a NYMEX WTI futures with December maturity in the same year is used as a hedge, then all three risks are relevant. First, the delivery location specified in the futures contract will be different from that of the physical location in Saudi Arabia where the oil will be produced. Second, the sulfur content will be different since Saudi oil is heavier, thus not qualifying as a delivery grade for the NYMEX WTI contract. Third, there is a difference of 3 months between the delivery date specified in the futures contract and the expected physical delivery of the oil.  

# 7.3 THE TERM STRUCTURE OF COMMODITY FUTURES PRICES  

Table 7.1 provides the futures prices corresponding to different contract months. This is the term structure of futures prices. If we plot the future prices against all contract months, we obtain a curve. The nearby contracts prices are on the left and the furthest contract months are on the right.  

# 7.3.1 BACKWARDATION AND CONTANGO  

Traders use different terms to describe the shape of the curve. If the resulting curve is downward sloping, we say that it is backwardation. In other words, backwardation describes a situation where the price for forward delivery is below the price for spot delivery. If the curve is upward sloping, we say that it is in contango. Figure 7.1a and b plots examples of curves in backwardation and in contango. In Chapter 2, we introduced the concept of the basis, which was defined as the difference between the spot price of an underlying asset and its futures price. We can apply this terminology to the term structure of futures prices. A commodity whose futures curve term structure is in backwardation will have a positive basis, whereas a commodity whose futures curve term structure is in contango will have a negative basis. Below, we will discuss, in more detail, what economic mechanism can explain the shape of the commodity futures curves. Contango and backwardation also exist in the pricing of traditional financial products, but, as we will see below, the role of the underlying physical markets in commodities is much more important, especially when demand exceeds supply.  

The term structure of futures prices changes over time by commodity and it differs across commodities at the same point in time. Some commodities have a tendency to exhibit contango; others exhibit backwardation most of the time. As Figure 7.1 illustrates, the crude oil futures curve often tends to be in backwardation while the gold futures curve tends to be in contango. The term structure of crude oil futures prices in Table 7.1 implies that on June 20, 2014, crude oil futures were in backwardation. To illustrate how much the term structure can change and that it can flip from backwardation to contango, Figure 7.2 shows the WTI crude oil futures price term structure on four different dates. The orange line represents the curve on June 16, 2014, which is the baseline. The green line plots the term structure 1 month earlier, on May 16, 2014, the blue line plots the curve 1 year earlier, on June 14, 2013, whereas the red line shows the term structure of futures prices on June 16, 2009. As we see the curves in 2013 2014 were in backwardation, but in November 2009, the crude oil futures curve was in contango. Below we will discuss the trading opportunities that this relatively unusual situation gave rise to. First we will turn to potential explanations for the shape of the term structure of futures prices. To do so we will build on the cash flow engineering methodology developed in earlier chapters and the relationship between commodity futures prices and the underlying replication portfolio.  

![](0cace25a652a140829aff8d548aa84c5134643a4657128ded408b003299690cf.jpg)  

# FIGURE 7.1  

Backwardation and contango.  

# 7.3.2 CONTRACTUAL EQUATION AND SYNTHETIC COMMODITIES  

Consider the example of an oil refiner that contacts a bank asking for the price for the purchase of oil in, say, 12 months. The price quoted by the bank is not a forecast of where it thinks the price of oil will trade at the time of delivery. The bank will quote a price which depends on the cost of hedging the bank’s own exposure. This is another example of the application of cash flow engineering to derivatives products. The cost of the product will be a function of the cost of the hedge. To avoid the risk of a rise in the price of oil, the bank would enter a series of transactions on the trade date to hedge its risk. Since the bank is agreeing to sell a fixed amount of oil in the future, it must first fund the purchase of oil in the spot market now and store the oil until delivery. Oil is traded in US dollars. The spot oil purchase could be financed by borrowing in US dollars at LIBOR from another bank. The bank buys the agreed amount of oil in the spot market from another institution, say another investment bank or an oil producer. The bank also incurs storage and insurance costs to store the oil until delivery. The above example is framed in the context of a bilateral OTC forward contract, but the same principle also applies to an oil futures contract.  

![](3df84b4e44b7c85052246a3b63b5805d77e6d043bb31fdee58120a86edca817c.jpg)  

# FIGURE 7.2  

Historical crude oil term structure of futures prices.  

We can apply the contractual equation developed earlier to create synthetic commodities. For example, suppose $S_{t}$ represents spot oil, which is the underlying asset for a futures contract with price $F_{t}$ and expiration date $T$ , $t_{0}<T$ . How can we create a synthetic for this contract? The answer is quite similar to the case of currencies. Using the same logic, we can write a contractual equation:  

![](bbf80729a56a8f6be49d94678528bede7eafe69729910e3c350c273977677924.jpg)  

The contractual equation above incorporates one of the distinguishing features of commodities, which is storage costs. Most commodities can be stored at a cost. Note, however, that for some commodities, storage is either not possible (e.g., due to seasons) or prohibitive (e.g., wholesale electricity). Figure 7.3 shows the cash flows associated with a long futures and a synthetic long futures position (ignoring margin payments).  

We can use Eq. (7.1) to obtain two results. First, by rearranging the contracts, we create a synthetic spot:  

![](3c859fcc36767cbcf631ce6402308a85677ee3e5fb2ecac622431087d09a193c.jpg)  

In other words, after changing signs, we need to borrow one unit of oil, make a deposit of $S_{t_{0}}$ dollars, and go long an oil futures contract. This will yield a synthetic spot.  

![](9a6b4b73047910995fc6654ee2b2d4096e4f66562c2f9cc204419d9f7c2b5ae9.jpg)  

# FIGURE 7.3  

Synthetic long crude oil futures position.  

Second, the contractual equation can be used in pricing. In fact, the contractual equation gives the carry cost of a position. To see this, first note that according to Eq. (7.1), the value of the synthetic is the same as the value of the original contract. Then, we must have  

$$
F_{t_{0}}=\big(1+r_{t_{0}}\delta\big)S_{t_{0}}+q_{t_{0}}(T-t_{0})
$$  

where $\delta$ is the factor of days’ adjustment to the interest rate denoted by the symbol $r_{t_{0}}$ and represents storage costs $q_{t_{0}}(T-t_{0})$ . The interest rate $r_{t_{0}}$ could be the LIBOR rate, for example. Storage costs include warehousing and insurance costs. The carry cost is the interest plus storage costs here.  

If storage costs are expressed as a percentage of the price, at an annual rate, just like the interes rates, this formula becomes  

$$
\boldsymbol{F}_{t_{0}}=\big(1+r_{t_{0}}\delta+q_{t_{0}}\delta\big)\boldsymbol{S}_{t_{0}}
$$  

This replication approach allows us to identify all the cash flows associated with the position and, thus, quote a fair value or theoretical price that will ensure no loss at the point of delivery, independent of the actual future spot price. Equation (7.4) is also sometimes called the spot futures parity relationship.  

# 7.3.3 CONVENIENCE YIELD  

Note that according to Eq. (7.4), the more distant the expiration of the contracts is, the higher its price. This means that future term structures would normally be upward sloping, or in contango, as shown in Figure 7.1b. However, as we discussed above, many commodity markets such as oil and certain base metals tend to exhibit a futures price term structure in backwardation. To be able to explain a backwardated term structure, we can extend Eq. (7.3) and incorporate an additional component called the convenience yield $(c y)$ . This leads to the following equation:  

$$
F_{t_{0}}=\bigl(1+r_{t_{0}}\delta\bigr)S_{t_{0}}+q_{t_{0}}(T-t_{0})-\mathrm{cy}
$$  

We can interpret the convenience yield as the premium that a consumer is willing to pay for being able to consume the commodity now rather than at some point in the future. One advantage of having a secure supply of raw materials is that it reduces the risk of stockouts, for example. However, the convenience yield remains a somewhat abstract concept that is intangible since it is really a mathematical placeholder that is used to reconcile the relationship between futures and spot prices in the above equation. The convenience yield cy changes in practice in response to the physical supply and demand imbalance for the underlying commodity. The convenience yield will be high if there are supply shortages and it will be lower when demand and supply are in balance. The convenience yield may be quite high for crude oil which counts oil refiners as its main consumers. First, it is expensive to store oil. Second, if there were supply shortages, the cost of closing a refinery for several months is high. For these two reasons, oil refiners may be willing to pay a premium for spot delivery. This could rationalize but not really economically (in a fundamental sense) explain a futures price that is below the spot oil price (backwardation).  

# 7.3.4 CASH AND CARRY ARBITRAGE  

We will now present a real-world arbitrage example that helps to develop the intuition for spot and futures markets dynamics as a function of supply and demand as well as storage costs. Note that Eq. (7.5) can also be used to identify potential arbitrage opportunities. If the current forward price $\boldsymbol{F}_{t_{0}}$ was greater than the right-hand side—which is more likely if the curve was in contango—one would sell the forward contract, buy the commodity in the spot market (financed by a loan), pay the cost of storage, benefit from holding the physical commodity over the interval $(t_{0};T)$ , and realize at maturity $T$ a cash and carry arbitrage. The following reading gives an example of real-world storage and shipping costs, applies our contractual equation (7.4) and illustrates the cash and carry arbitrage in the heating oil market:  

# EXAMPLE  

JPMorgan Hires Supertanker for Storage, Brokers Say —JPMorgan Chase & Co., the second-largest US bank by deposits, hired a newly built supertanker   
to store heating oil off Malta, shipbrokers reported, in the company’s first such booking in at least   
5 years. The bank hired the Front Queen for 9 months, according to daily reports from Oslo-based SeaLeague   
A/S and Athens-based Optima Shipbrokers Ltd. David Wells, a spokesman for JPMorgan in London,   
declined to comment. JPMorgan, which has never hired an oil tanker based on data compiled by Bloomberg going back 5 years,   
follows companies including Citigroup Inc.’s Phibro LLC unit and BP Plc in hiring ships to store crude or oil   
products at sea. The firms are seeking to take advantage of higher prices later in the year. “It’s opportunity-driven,” Sverre Bjorn Svenning, an analyst at Fearnley Consultants AS in Oslo, said by   
phone. “I doubt it’s going to be a permanent or new sort of trade.” Heating oil for immediate delivery costs $\$553$ a metric ton in northwest Europe and supplies for August   
are at $\$580$ , according to data compiled by Bloomberg.[. . .] Front Queen can hold about 273,000 tons of heating oil, more than three times the amount held by a more   
conventional Long Range 2 tanker, according to Riverlake Shipping SA, Switzerland’s largest shipbroker. JPMorgan hired the ship at \$35,000 41,000 a day, according to the broker reports. The bank is also   
paying $\$1.6$ million for the ship to sail from Singapore to Europe without a cargo, the brokers said.   
Long Range 2 tankers cost about $\$25,000$ a day for storage, according to Riverlake Shipping. Based on a full cargo, the monthly cost for the Front Queen works out at $\$3,85-4,50$ a ton, excluding   
what JPMorgan paid to get the ship from Asia to Europe. Benchmark supertanker rates plunged $87\%$   
from their peak in July as oil producers curbed supply and ship owners expanded the global fleet.   
The Paris-based International Energy Agency expects the first back-to-back drop in global annual oil   
demand since 1983. Traders were already using smaller tankers to store record volumes of jet fuel and heating oil in Europe   
as onshore tanks filled up, D/S Torm A/S, Europe’s biggest oil products shipping line, said April 3.   
Inventories of heating oil at Amsterdam, Rotterdam, and Antwerp stand at 2.7 million tons, the highest for at   
least 2 years, according to data from PJK International BV.[. . .] Bloomberg (extract from article “JPMorgan Hires Supertanker for Storage, Broker Say” by Alaric Nightingale  June 3, 2009)  

What is the profit that JPMorgan could expect to make on the transaction? If we make a few simplifying assumptions we can calculate the price of the synthetic futures based on the contractual equation in Eq. (7.1) and compare it with the actual futures price available in the market. This way, we can approximate the expected profit. In other words, we assume the bank buys spot heating oil for $\$553$ , pays storage and other costs and sells a futures for $\$580$ in the hope of making a profit. To draw a representative futures curve, we would require futures prices for more contract months, but based on these two price points, the heating oil futures price term structure is in contango. This is the same shape as the June 2009 crude oil term structure shown in Figure 7.2. Let’s assume that JPMorgan bought 273,000 tons heating oil in the spot market in June 2009 and entered an appropriately sized short heating oil future. At an assumed spot price of $\$553$ per metric ton, the physical heating oil purchase in June 2009 has a value of $\$150.969$ million. If we make a conservative assumption and take borrowing costs to be, say, $1\%$ for 2 months, total borrowing costs would be $\$1.50969$ million over the period. Insurance costs for oil tankers can vary from $0.25\%$ to more than $3\%$ of hull value depending on the geopolitical and macroeconomic situation. If we assume an insurance cost of $0.25\%$ of the value of the spot purchase for 2 months, then the total insurance cost is $\$377,423$ . The cost of shipping the tanker from Singapore to Europe is $\$1.6$ million according to the reading. Storage costs are $\$3.85$ per ton amount or 1.051 million for the whole cargo. Table 7.2 provides the breakdown of expected costs and revenues. Total costs are $\$155.507163$ million. If we assume a futures price of $\$580$ , this corresponds to revenue of $\$158.34$ million. The expected profit is then $\$2.833$ million.  

<html><body><table><tr><td colspan="2">Table 7.2 Expected Profit Calculations for Heating Oil Example</td></tr><tr><td>Cost of buying spot heating oil</td><td>$150.969 million</td></tr><tr><td>Cost of borrowing (at 1% for 2 months)</td><td>$1.50969 million</td></tr><tr><td>Insurance costs (at 0.25% of hull value)</td><td>$0.377423 million</td></tr><tr><td>Costs of shipping the tanker from Singapore to Europe</td><td>$1.6 million</td></tr><tr><td>Costs of storage (at $3.85 per ton)</td><td>$1.05105 million</td></tr><tr><td>Total costs</td><td>$155.507163 million</td></tr><tr><td>Total revenue from futures sale</td><td>$158.34 million</td></tr><tr><td>Total profit</td><td>$2.832838 million</td></tr></table></body></html>  

The above example not only illustrates the construction of a synthetic futures position, but also the exploitation of a potential arbitrage opportunity. We can ask what the effect of such transactions involving spot heating oil purchases and futures markets sales is likely to be. The extract from the Bloomberg article above suggests that many market participants engaged in such trades. This can be expected to lead to an increase in spot prices and a decrease in futures prices, thus reducing the contango and potentially moving it to the backwardation shape that energy commodities typically exhibit. The above is just an example, but it illustrates drivers of the term structure that have been found to be important in more comprehensive studies of the term structure of futures prices such as those listed at the end of this chapter.  

# 7.3.5 ANOTHER INTERPRETATION OF SPOT FUTURES PARITY  

There are no upfront payments but buying futures or forward contracts is not costless. Ignoring any guarantees or margins that may be required for taking futures positions, taking forward or futures positions does involve a cost. Suppose we consider a storable commodity with spot price $P_{t_{0}}$ . Let the forward price be denoted by $P_{t_{0}}^{\mathrm{f}}$ . Finally, suppose storage costs and all such effects are zero. Then the futures price is given by  

$$
P_{t_{0}}^{\mathrm{f}}=\big(1+r_{t_{0}}\delta\big)P_{t_{0}}
$$  

where $r_{t_{0}}$ is the appropriate interest rate that applies for the trader and $\delta$ is the time to expiration as a proportion of a year. Now, suppose the spot price remains the same during the life of the contract. This means that the difference  

$$
P_{t_{0}}^{\mathrm{f}}-P_{t_{0}}=r_{t_{0}}\delta P_{t_{0}}
$$  

is the cost of taking this position. Note that this is as if we had borrowed $P_{t_{0}}$ dollars for $a$ “period” $\delta$ in order to carry a long position. Yet there has been no exchange of principals. In the case of a default, no principal will be lost.  

# 7.4 SWAP ENGINEERING FOR COMMODITIES  

The overall structure of commodity swaps is similar to equity swaps, which we mentioned in Chapter 4 and discuss in greater detail in Chapter 18 on cash flow engineering applications in equity markets. As with equity swaps, there are two major types of commodity swaps. Parties to the swap can either (1) exchange fixed for floating payments based on a commodity index or (2) exchange payments when one payment is based on an index and the other on a money market reference rate.  

The vast majority of commodity swaps involve oil. Consider a refinery, for example. Refineries buy crude oil and sell refined products. They may find it useful to lock in a fixed price for crude oil. This way, they can plan future operations better. Hence, using a swap, a refiner may want to receive a floating price of oil and pay a fixed price per bbl.  

Such commodity or oil swaps can be arranged for all sorts of commodities, metals, precious metals, and energy prices.  

# EXAMPLE  

Japanese oil companies and trading houses are naturally short in crude oil and long in oil products. They use the short-term swap market to cover this exposure and to speculate, through the use of floating/fixedpriced swaps. Due to an overcapacity of heavy-oil refineries in the country, the Japanese are long in heavyoil products and short in light-oil products. This has produced a swap market of Singapore light-oil products against Japanese heavy-oil products.  

There is also a “paper balance” market, which is mainly based in Singapore but developing in Tokyo. This is an oil instrument, which is settled in cash rather than through physical delivery of oil.  

Thomson Reuters IFR (Issue 946)  

# 7.4.1 SWAP CASH FLOW ENGINEERING IN COMMODITY MARKETS  

Let’s examine how we can engineer a commodity swap. Here we assume that the counterparties exchange payments where one payment is based on an index and the other on a money market reference rate. Suppose the $S_{t}$ represents a commodity. It could be oil for example. Then, the analysis would be identical to engineering an equity swap.  

One could invest $N=100$ and “buy” $\boldsymbol{Q}$ units of the commodity in question. The price $S_{t}$ would move over time. One can think of the investment paying (receiving) any capital gains (losses) to the investor at regular intervals, $t_{0},t_{1},...,t_{n}$ . At the maturity of the investment, the $N$ is returned to the investor. All this is identical to the case of stocks covered in Chapter 4. This is illustrated in Figure 7.4a.  

One can put together a commodity swap by adding the $n$ -period FRN to this investment, as shown in Figure 7.4b. The initial and final payments of the $N$ would cancel and the swap would consist of paying any capital gains and receiving the capital losses and the $\mathrm{LIBOR}+d_{t},$ , where $d_{t}$ is the swap spread (see Figure 7.4c).  

Note that the swap spread may deviate from zero due to any convenience yield the commodity may offer, or due to supply demand imbalances during short periods of time. The convenience yield here would be the equivalent of the dividends paid by the stock.  

# 7.4.2 PRICING AND VALUATION OF COMMODITY SWAPS  

Consider a commodity swap in which the counterparties exchange fixed for floating payments based on a commodity index instead of the swap type shown in Figure 7.4 in which there was an  

![](b29732bdea4af9a73d934512967a6cf517454306d601da393a19aad1cb4abe14.jpg)  

# FIGURE 7.4  

Commodity swap replication.  

<html><body><table><tr><td colspan="2">Table 7.3 Sample Swap Contract</td></tr><tr><td>Fixed-price payer:</td><td>Swap dealer X</td></tr><tr><td>Floating-price payer:</td><td>Crude oil producer</td></tr><tr><td>Commodity reference price:</td><td>NYMEX WTI futures contract</td></tr><tr><td>Fixed-price payment:</td><td>$95.00 bbl X volume</td></tr><tr><td>Floating-price payment:</td><td>The average over the calendar month of the daily settlement prices for the NYMEX prompt contract times the monthly volume</td></tr><tr><td>Monthly volume:</td><td>100,000 bbl/month</td></tr><tr><td>Term:</td><td>January 2013-December 2013</td></tr><tr><td>Payments:</td><td>14 business days following each settlement period</td></tr><tr><td colspan="2">Source: risk.net/energy-risk, Blanco and Piere (2013).</td></tr></table></body></html>  

exchange of payments when one payment is based on an index and the other on a money market reference rate. The following example involves an oil producer that sells a swap to hedge revenues over a certain period.  

Here we make the assumption that the oil producer is attempting to hedge its revenues against an unexpected decline of crude oil prices in 2013. According to Table 7.3, the oil producer and the swap dealer X would agree to enter into a calendar year 2013 swap with a fixed price of $\$95/6b l$ and a monthly volume of $100,000\ b\mathsf b\mathsf b\mathsf b\$ per month. The net payment of each month is the difference between the fixed-price payment of $\$95/6b l$ and the realized average price, multiplied by the monthly volume. As a result of these terms and conditions, the seller of the swap (the producer) will receive a payment from the swap dealer if the average oil price is lower than $\$95/6b l$ . The opposite will happen if the average oil price is higher than $\$95/6b l$ . Assume, for example, that the floating leg of the swap settles at $\$85/6b l$ at the end of January 2013. In this case, there would be a payment from the swap dealer to the oil producer of $100,000{\ b}{\mathsf{b l}}\times(\S95-\S85)=\S1,000,000.$ . Figures $7.5\mathrm{a}$ and 7.5b illustrate the payments received by the swap seller (i.e. the oil producer) and the swap buyer (i.e., the swap dealer). For the purpose of illustration, we assume in Figure 7.5 that the floating leg of the swap settles at $\$100/b b l$ and $\$105/6b l$ in February 2013 and March 2013. Figure 7.5c shows the net payments to the swap seller, i.e., the oil producer. This example shows that the swap fulfills its purpose of hedging the oil producer against unexpected decreases in oil prices. Table 7.4 explains the key contract terms used in Table 7.3. It is common for energy commodity sales and purchase contracts to have ratable delivery provisions such that the final invoice price is based on the average price during the pricing window. This provides hedgers such as producers or consumers with an incentive to use average price swaps or a strip of futures contracts to match the pricing provisions of the physical deals.  

# 7.4.2.1 Calculating swap prices from the futures curve  

As we saw in the context of interest rate swaps, the swap rate at inception is set so that the present value of future fixed and floating payments is equal. The mark-to-market value of the interest rate swap is calculated by discounting the future cash flows using forward rates, for example. Similarly, in the case of the oil swap, we can calculate the mark-to-market gains and losses by valuing the  

![](f59fec9f462989dcf3d03db30ced9f8079cc5e8a3f2da89e5954c09cfff41477.jpg)  

# FIGURE 7.5  

Cash flow example of oil commodity.  

<html><body><table><tr><td colspan="2">Table 7.4 Key Contract Terms of an Over-the-Counter Swap</td></tr><tr><td>Parameter</td><td>Explanation</td></tr><tr><td>Commodity reference price</td><td>The commodity price index that will be used to determine the floating leg price. Common choices for the underlying are the prompt futures contract settlement, spot prices, month-ahead indices, and deferred (second-prompt prices)</td></tr><tr><td>Floating price</td><td>The formula that will be used to determine the floating leg payment. It is often the average of the daily settlements of the commodity reference price during the pricing or fixing window</td></tr><tr><td>Fixed price Fixing or pricing period(s)</td><td>Negotiated price for the fixed leg of the contract</td></tr><tr><td></td><td>A schedule of dates in which the underlying price will be observed to set the value of the floating leg for each settlement period</td></tr><tr><td>Notional or volume</td><td>Notional amount of commodity used to determine the swap cash flows</td></tr><tr><td colspan="2">Source: risk.net/energy-risk, Blanco and Piere (2013).</td></tr></table></body></html>  

swap and constructing swap prices. Commodity swap prices also require a forward curve. The price quotes for the forward curve, which are the equivalent of the forward curve implied LIBOR rates in an interest rate swap, could come from futures, forward, or swap prices or a mixture of the three. Let’s assume that we use the futures curve to calculate the swap curve. This is illustrated in Table 7.5. Here we further assume that the swap curve is based on the expected average of the futures prompt contract during a given month which involves combining two futures contract maturities for each swap price. In constructing the curve day count conventions, contract expiry dates and holidays have to be carefully taken into account. Consider, for example, the swap curve price for January 2013 in Table 7.5. It is based on the following calculation:  

$$
\begin{array}{r l}&{P_{\mathrm{swap,Jan}}=P_{\mathrm{future,Feb}}\times w_{1}+P_{\mathrm{future,March}}\times w_{2}}\\ &{\qquad=\&88.40\times52\%+88.92\times48\%=\&88.65}\end{array}
$$  

Table 7.5 provides the swap curve construction for months January 2013 until December 2013.  

Similar to an interest swap, the information in Table 7.5 can be used to calculate the mark-tomarket value of the swap and its “fair value.” For this, we require information about the discount rate and yield curve. This is left as an exercise at the end of this chapter. The exercise also provides information about the discount rate to use to discount the cash flows.  

<html><body><table><tr><td colspan="8">Table 7.5 Building the Calendar Year 2013 Prompt Month Swap Curve from the Futures Curve</td></tr><tr><td colspan="3">Futures Curve</td><td colspan="6">Swap Curve Construction Days Days Swap</td></tr><tr><td> Month</td><td>Expiration</td><td>Price ($/bbl)</td><td> Date</td><td>Until Roll Date</td><td>After Roll Date</td><td>Weight Contract #1 (%)</td><td>Weight Contract #2 (%)</td><td>Curve (Prompt) ($)</td></tr><tr><td>January 13 February 13</td><td>16/02/2013</td><td>88.40</td><td>January 13 February 13</td><td>12 9</td><td>11 10</td><td>52 47</td><td>48 53</td><td>88.65 89.19</td></tr><tr><td>March 13</td><td></td><td></td><td>March 13</td><td>10</td><td>11</td><td>48</td><td>52</td><td>89.68</td></tr><tr><td>April 13</td><td>13/02/2013</td><td>88.92</td><td>April 13</td><td>11</td><td></td><td>52</td><td></td><td></td></tr><tr><td>May 13</td><td>14/03/2013</td><td>89.43</td><td>May 13</td><td></td><td>10</td><td></td><td>48</td><td>90.07</td></tr><tr><td></td><td>15/04/2013</td><td>89.90</td><td>June 13</td><td>12</td><td>10</td><td>55</td><td>45</td><td>90.35</td></tr><tr><td>June 13</td><td>16/05/2013</td><td>90.25</td><td>July 13</td><td>9</td><td>10</td><td>47</td><td>53</td><td>90.52</td></tr><tr><td>July 13</td><td>13/06/2013</td><td>90.47</td><td>August 13</td><td>12</td><td>10</td><td>55</td><td>45</td><td>90.60</td></tr><tr><td>August 13</td><td>16/07/2013</td><td>90.57</td><td>September 13</td><td>11 10</td><td>10 10</td><td>52</td><td>48</td><td>90.63</td></tr><tr><td>September 13</td><td>15/08/2013</td><td>90.63</td><td>October 13</td><td>12</td><td>11</td><td>50</td><td>50</td><td>90.63</td></tr><tr><td>October 13</td><td>13/09/2013</td><td>90.63</td><td>November 13</td><td>10</td><td>11</td><td>52 48</td><td>48</td><td>90.62</td></tr><tr><td>November 13</td><td>16/10/2013</td><td>90.62</td><td>December 13</td><td>9</td><td></td><td></td><td>52</td><td>90.56</td></tr><tr><td>December 13</td><td>14/11/2013</td><td>90.61</td><td></td><td></td><td>13</td><td>41</td><td>59</td><td>90.46</td></tr><tr><td>January 14</td><td>12/12/2013</td><td>90.52</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>February 14</td><td>11/01/2013</td><td>90.41</td><td>v-risk.Blanco and Piere (20l3)</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td colspan="9">Source: risk.net/ene</td></tr></table></body></html>  

# 7.4.3 REAL-WORLD COMPLICATIONS  

OTC commodity swaps such as the one discussed above can be customized. However, commodity swap contract specifications and liquidity differ even in the exchange traded market. On October 19, 2014, for example, Dalian Commodity Exchange (DCE) launched an iron ore commodity swap. The contract differs from the iron ore contract offered by the Singapore Exchange (SGX) since 2009 because there are currency and settlement differences. The DCE contract is in RMB, whereas the SGX contract is in US dollars. In contrast to the Dalian contract, which is physically settled, the SGX contract is financially settled. In 2013, SGX cleared around $95\%$ of the world’s iron ore swaps—the remainder accounted for by trades on the Chicago Mercantile Exchange and ICE. The following example illustrates potential arbitrage opportunities and limitations in commodity swap markets as well as real-world complications such as seasonality and time-varying liquidity.  

# EXAMPLE  

In line with a number of Chinese commodity contracts, there are only three liquid months on DCE, for contracts that settle in January, May, and September. With liquidity along larger parts of the curve in Singapore, this leaves traders with China operations able to conduct spread trades based on the arbitrage between DCE and SGX [. . .]  

The reason SGX volumes grew after the DCE launch is the significant difference between the two products: currency (RMB versus US\$) and physical settlement in Dalian versus financial settlement on the SGX. This has led to the creation of different, and complementary, dynamics between the exchanges.  

“The Dalian contract and the Singapore swap are fundamentally different contracts,” says Leong Chean Wai, Singapore-based head of commodity derivatives at DBS Bank. “Dalian is a closed market—it isn’t accessible to international players, unlike Singapore. It has, however, introduced the spread trade, which is a new element to the iron ore market, even though it is something that is commonly executed in other base metal markets. This encourages more players to enter the market and means the DCE contract has led to an increase in Singapore liquidity, rather than a fall.” $I...J$  

A lot of iron ore traders in DCE trade coke, coking coal, and steel. They frequently adjust their positions among different contracts for arbitrage. This means it is difficult to predict which contract will be the most active one. [. . .]  

“China’s futures market is still taking baby steps. A well-developed futures market usually has marketmakers who can guarantee that every listed contract has enough liquidity. But there are no market-makers in China’s futures market. That’s part of the reason why some contracts have great liquidity, but some do not.”  

But it’s not so much a lack of market-makers that is holding back liquidity along large parts of the DCE curve; the seasonal nature of demand for commodities is also significant, according to Lin Ling, Shanghaibased analyst at Citic Futures.  

May and September are peak seasons for consuming iron ore. The consumption in January is quite low, but it’s immediately before Chinese New Year and steel mills need to have some winter storage for the next year. This rule is applicable to both coke and coking coal as well. $I\cdot\cdot\cdot J$ The real test comes when the May contract— the first liquid month on DCE—becomes due. “It’s not possible to predict how that will turn out until the actual day. A lot will depend on where the physical is trading compared with the exchange. China has a large active physical market and traders will wait—if the physical is cheaper, they will buy that, and sell out their futures positions and if the price is lower on the DCE than the physical delivery, they will do that.”  

There is, essentially, a three-way arbitrage on the China iron ore swaps market: the DCE futures price versus the physical onshore versus the international swap market. While the former is a straightforward arbitrage of the futures price versus physical, the onshore/offshore arbitrage is a function of the different curves in SGX and DCE.  

Backward look  

Chinese commodities markets are typically characterized by contango—where the forward price is higher than the spot—due to factors such as tax, storage costs, and the limited access to onshore markets from international players, and iron ore was initially no exception. However, it has now moved into backwardation (where the futures price is below the expected future spot price for a particular commodity). East says: “What we saw when the DCE launched its iron ore futures contract was that it was in contango, whereas the SGX market was in backwardation. What happened was that all the traders came in and bought SGX backwardation and sold DCE contango.” Arbitrage is inherently risky and East points to the dangers posed by a steepening of either the backwardation or contango, which can lead to mark-tomarket losses—and of course, having access to the China physical market is critical to arbitraging the DCE and SGX markets. [. . .] These markets move—there is an arbitrage between the two, but also it causes problems with regard to margining. “If the price goes up, the trader will be making a profit in one and a loss in the other, but because these positions are in different exchanges he can’t offset the margin,” he says.  

Risknet/Asia Risk (April 2, 2014)  

The reading above provides example of an application of the contractual equation in Eq. (7.1) to the iron ore market. Traders can use the spot futures parity relationship to identify arbitrage opportunity between the onshore physical and the futures market. Since iron ore contracts are traded at the DCE and SGX but exhibited different term structures, traders bet on a convergence of the curves and essentially bought low and sold high. They sold the DCE contango (where initially nearby contract prices were below back month contracts price) and bought SGX backwardation (nearby contract prices above back month ones).  

This example not only illustrates the use of commodity swaps for spread arbitrage trades, but also the continuing spread of financial engineering applications around the world. Currently the US dollar is still the currency in which most derivatives contracts are denominated, but it is very likely that over the next decades, currencies such as the RMB and other Asian currencies will see growth in derivatives and financial engineering applications.  

# 7.4.4 OTHER COMMODITY SWAPS  

A commodity-linked interest rate swap is a hybrid swap in which LIBOR is exchanged for a fixed rate, linked to a commodity price. A buyer of crude oil may wish to tie costs to the cost of debt. The buyer could elect to receive LIBOR and pay a crude-oil-linked rate such that, as the price of crude oil rises, the fixed rate the buyer pays declines.  

A crack spread swap is a swap used by oil refiners. They pay the floating price of the refined product and receive the floating price of crude oil plus a fixed margin, the crack spread. This way, refiners can hedge a narrowing of the spread between crude oil prices and the price of their refined products.  

# 7.5 THE HEDGE FUND INDUSTRY  

Throughout the book we refer to the application of financial engineering techniques to trading opportunities and arbitrage as well as derivatives product design. One of the most prominent types of arbitrageur in financial markets is hedge funds. Their strategies are very diverse, but many funds  

use financial engineering techniques to design their strategies and they trade derivatives. Similar to commodities, hedge funds are often referred to as an alternative asset class. Therefore, in this section, we review the hedge fund industry and its role in financial markets.  

# 7.5.1 ALTERNATIVE INVESTMENT FUNDS  

Hedge funds are alternative investment funds (AIFs) that use a diverse set of techniques to improve performance and reduce volatility. The hedge fund industry has significantly changed over recent years and grown from what in retrospective appears to have been a loosely regulated multibillion dollar cottage industry dominated by high net worth individuals as its main investors in the 1990s to a tightly regulated and institutionalized sector of the asset management industry that absorbed many activities previously predominantly found in banks.  

Hedge funds differ from traditional investment funds such as mutual funds in three main ways: regulation, investment mandate, and legal structure.  

# 7.5.2 HEDGE FUND REGULATION  

First, to understand the effect of hedge fund regulation, it is important to distinguish the alternative investment fund manager (AIFM) from the hedge funds that it manages.3 The object of recent regulation such as the 2010 Dodd-Frank Walter Street Reform and Consumer Protection Act (Dodd-Frank), the JOBS Act and AIFMD/EMIR is the AIFM. AIFMs such as Bridgewater Associates and the Man Group, for example, are headquartered in Connecticut and London, respectively, but their products include onshore and offshore funds. Most hedge funds are located in lightly regulated, low-tax, offshore centers like the Cayman Islands or Bermuda. The Cayman Islands are the single most popular location for hedge funds, with almost one in two registered there. However, even before the global financial crisis (GFC), there have been many onshore hedge funds in the United States or Europe where they were registered with regulators.  

Dodd-Frank changed the regulation of hedge funds in the United States by requiring that all hedge funds with d100 million or more in assets be registered with the Securities and Exchange Commission (SEC). It also instructed the SEC to collect information, on a confidential basis, from private fund advisers regarding the risk-profiles of their funds. The 2012 JOBS (Jumpstart Our Business Startups) act directed the SEC to remove the decades-old ban on general solicitation that applied to companies or funds that make private securities offerings. As a result, hedge fund managers in the United States are now free to communicate freely with and advertise to the public.  

The European Union (EU) Directive on AIFMs passed in 2010 requires hedge funds to register with national regulators and increased disclosure requirements for AIFMs operating in the EU. The directive also increases capital requirements for hedge funds and places further restrictions on leverage utilized by hedge funds. Non-EU AIFMs marketing funds in the EU are subject to reporting requirements under an enhanced national private placement regime until they are eligible to or required to market under an EU passport in the future.4  

The GFC and the Maddof scandal affected both the supply of and demand for investor capital for hedge funds. The scandal negatively affected the perception of hedge funds by high net worth individuals who often invested in hedge funds via funds of funds.5 Arbitrages in the real world are not riskless and they require a stable sources of funding. Therefore, sudden redemptions by funds of funds and high net worth individuals during the GFC led many hedge funds to set out and seek more sticky sources of capital such as institutional investors. As a result, the investor base of hedge funds has changed. Since 2010, institutional investors such as pension funds, SWFs, endowments, and foundations account for the majority of hedge fund investor assets, while HNWI and family offices are in the minority.  

# 7.5.3 HEDGE FUND INVESTMENT MANDATE AND TECHNIQUES  

The second distinguishing feature of hedge funds has to do with their investment mandate and techniques. Historically, most registered mutual funds had essentially two choices: They could either go long in the stated asset class or stay in cash. Often there is a limit on the latter. Thus, mutual funds have no room for maneuver during bear markets. Hedge funds on the other hand were less restricted and could short the markets. This was perceived at that time to be the “hedge” for a down-market, hence the term “hedge fund” emerged. In addition to shorting, hedge funds could also use derivatives to speculate or hedge and reduce risk. In recent years, a convergence of the alternative investment industry and the traditional investment industry has been witnessed as $40A c t$ funds in the United States and absolute return UCITS funds in the EU increasingly employ hedge fund techniques while being marketed to retail investors.6  

Regulation explains why hedge funds are allowed to use shorting and derivative, but less wellknown differences in investment mandate explain why they choose to. While traditional mutual funds normally only offer relative returns, hedge funds aim to offer absolute returns on an investment. For example, traditional funds set for themselves stock or bond market benchmarks and then measure their performance relative to these benchmarks. The fund may be down, but if the benchmark is down even more, the fund is said to outperform.7 This is because a typical mutual fund has to be long the underlying securities. When the price of the security goes down, they have few means to make positive returns. Hedge funds, on the other hand, can realize profits in downmarkets as well. Unlike most traditional fund managers, hedge funds can (1) sell short, (2) use derivatives, and (3) leverage to make bigger investments.  

# 7.5.4 HEDGE FUNDS’ LEGAL STRUCTURE  

The use of leverage is explained by the third main feature of hedge funds, which is its legal structure. Hedge funds’ legal structure grants them contractual flexibility, such as lockups for investors, whose legal rights are those of a limited partner. These characteristics facilitate leverage and allow the prime broker to grant special funding conditions to hedge funds. Leverage arises not just as a result of (a) borrowing, but also (b) the use of financial instruments with intrinsic leverage such as futures or (c) construction leverage resulting from short positions that fund long positions.8 Nevertheless, hedge funds have had on average lower leverage than banks, which had leverage ratios of 20 30, in the run up to the GFC.9 In February 2014, average hedge fund leverage was 2.04, but it varied from 1.02 for Distressed Securities to 3.44 for Global Macro funds according to Citi Prime Finance.10 Because some hedge funds leverage their capital significantly and some funds trade frequently, hedge funds are much more influential than their equity capital indicates.  

Assets under management in hedge funds were around $\$2.7$ trillion in 2014 compared to less than $\$200$ billion in 1994.11 However, most of the hedge fund $\mathbf{AuM}$ are concentrated in the largest funds. Although only $9\%$ of funds in 2012 have AuM above $\$1$ billion, these funds manage more than $70\%$ of the industry AuM. The majority of hedge fund assets is therefore managed by large institutionalized AIFMs.12  

Hedge funds are important market participants. According to Reuters, hedge fund trading activity accounted for up to half the daily turnover on the New York Stock Exchange and the London Stock Exchange in 2005. More importantly, hedge funds make up almost $60\%$ of US credit derivatives trading, and about half of emerging market bond trading. According to the same sources, about one-third of equity market activity is due to hedge funds. It is estimated that they are responsible for more than $50\%$ of trading in commodities.  

# 7.5.5 INCENTIVES  

Historically, hedge fund managers often started as prop desk traders at major banks. They then left the bank to set up their own businesses. The Volcker Rule, part of the 2010 Dodd-Frank financial overhaul, came into effect on April 1, 2014, and restricts the ability of banking institutions and certain nonbank financial companies to engage in proprietary trading. In anticipation of the implementation of the rule, many investment banks closed proprietary trading desks with many traders moving to less regulated areas of financial markets such as hedge funds or privately held proprietary trading firms. Client-flow trading desks, of course, remain in investment banks and provide a training ground for young traders and a source of talent for hedge funds.  

Successful traders in banks are attracted by the hedge funds’ potentially generous remuneration. Annual fees at traditional mutual funds are normally between 30 and 50 bp. Hedge funds charge an annual $1-2\%$ management fee. However, they also receive up to $20\%$ of any outperformed amount. Funds of hedge funds charge an additional annual $1-1.5\%$ management fee and an average $10\%$ performance fee.  

Many hedge funds have high water marks. If the value of the portfolio they are managing falls below, say, last year’s value, the fund does not receive performance fees until this level is exceeded again. This means that after a sharp fall in the portfolio, such funds will be dissolved and reestablished under a different entity.  

# 7.5.6 STRATEGIES  

Hedge funds are classified according to the strategies they employ. The market a hedge fund uses is normally the basis for its strategy classification.  

Global macro funds bet on trends in financial markets based on macroeconomic factors. Positions are in general levered using derivatives. As we saw in our discussion of futures and margin requirements, such derivatives cost a fraction of the outright purchase.  

Managed futures/Commodity Trading Advisors (CTAs). These strategies speculate on market trends using futures markets. Systematic CTAs differ from discretionary CTAs in that they use computer programs that use technical analysis tools like relative strength and momentum indicators to make investment decisions.  

Long/short strategists buy stocks they think are cheap and short those they think are expensive. The overall position can be net long or net short. This means that they are not necessarily market neutral. Within this category, the class of short bias funds can take long equity positions, but their overall position must be short.  

Emerging market funds use equities or fixed income. Managers using this strategy tend to buy securities and sell only those they own. Note that this is in contrast to short-selling which is a technique that requires borrowing a security before selling it. Many emerging market countries do not allow short selling and derivatives markets in these countries are normally not developed.  

Event driven. There are two groups here. Merger or risk arbitrage trades the shares of firms in takeover battles, normally with a view that the bid will have to be raised to win over shareholders in the target company and will cost the bidder a lot more money. A higher buyout price will usually weigh on the bidding company’s share price as it could deplete cash reserves or force it to issue bonds to pay the extra money.  

Distressed debt funds trade the bonds of a company in financial distress, where prices have collapsed, but where the chances of repayment are seen as high or there is a possibility that debt could be converted into equity. Distressed debt normally trades at a deep discount to its nominal value and could be bought against the company’s investment grade bonds, which, because of collateral agreements, may not have crashed to the same extent.  

Relative value. These strategies generally buy stocks or bonds managers think are cheap and sell those they think are expensive.  

Equity neutral or hedged strategies should be cash neutral, which means the dollar value of stocks bought should equal the dollar value of stocks they have shorted. They can also be market neutral, which means the correlation between a portfolio and the overall market should be zero.  

Fixed income strategies look at interest rates, sovereign bonds, corporate bonds, and mortgage and asset-backed securities. Managers can trade corporate against government debt, cash versus futures, or a yield curve—short maturity bonds against long maturity bonds. Bonds of different governments are often traded against each other where interest rate cycles are seen to be out of sync.  

Convertible arbitrage funds trade convertible bonds. These are the implicit equity, bond, credit, and derivatives such as options.  

Credit derivatives are a key tool for hedge funds. Within this class, capital structure arbitrage, put simply, involves a hedge fund manager trading corporate bonds against the company’s stock on the basis that one is cheap and the other expensive.13  

# 7.5.7 PRIME BROKERS  

Prime brokers offer settlement, custody, and securities lending services to hedge funds. Prime brokers earn their money from commissions and by charging a premium over money market lending rates for loans.  

Prime brokers also provide trade execution, stock lending, leveraged finance, and other essential services to hedge funds. In fact, without prime brokerages, hedge fund activity would be very different than where it is at the moment.  

One factor is the level of leverage prime brokers are offering. Such leverage can multiply a hedge fund’s activities by a factor of 3 or more, but increased capital requirements for banks mean that leverage levels are low in hedge funds, especially compared to banks where they are typically 10 times higher than for hedge funds. The second major help provided by prime brokers is in execution of trades. For example, short selling an asset requires borrowing it. How would the hedge fund find a place to borrow such an asset? Prime brokers’ securities lending divisions have better information on this.  

An important prime brokerage function is risk management and position keeping. Prime brokers keep the positions of the hedge funds14 and have developed elaborate risk management systems that a small hedge fund may find too costly to own.  

Global prime brokerage revenues have fallen from $\$15$ billion in 2008 to $\$12$ billion in 2012.15 This trend is due to pressure on profit margins and the multiprime trend in the prime brokerage industry. The collapse of several prime brokerage firms during the GFC, which accounted for a large share of the prime brokerage business, highlighted the need for hedge funds to diversify their prime broker exposure in order to reduce their counterparty risk. Counterparty risk has become a much more important consideration in financial engineering since the GFC and we will discuss it in a later chapter in detail.  

# 7.6 CONCLUSIONS  

In this chapter, we extended the application of cash flow engineering techniques to commodity markets. As we saw storage costs and quality and grade differences in commodities make the financial engineering for commodities more complex than for homogeneous assets such as currencies, for example. We used the contractual equation for a commodity futures to derive a synthetic commodity futures position and applied it to a real-world cash and carry arbitrage example in the heating oil market. Commodity swap engineering is similar to that for other assets such as equities and we provided examples of different types of commodity swaps. Just as the commodity market has undergone a financialization with the inflow of investor capital and new investment products such as commodity ETNs and ETFs, the hedge fund industry has significantly changed in recent years and undergone an institutionalization. We discussed how recent regulation and the GFC have significantly transformed the hedge fund industry.  

# SUGGESTED READING  

Our discussion of commodities in this chapter was focused on highlighting cash flow engineering applications in commodities. For reasons of space, we could not provide a comprehensive overview of commodity markets and derivatives. Schofield (2007) is an excellent practical overview of different commodity markets, their economics and dynamics as well as derivatives pricing. For a recent commodity futures guide, see Kleinman (2013). Energy commodity markets are some of the economically most important markets and Edwards (2010) provides a good introduction to them. The commodity swap valuation example in this chapter is taken from Blanco and Pierce (2013). Cheng and Xiong (2013) discuss the effects of the financialization of commodity markets. Gorton et al. (2012) show how commodity term structure dynamics are related to inventories. Finally, the CME Commodity Trading Manual provides more detail on one of the most important commodity futures markets in the world. Lhabitant (2009) and Stefanini (2010) are comprehensive guides on hedge funds and their strategies.  

# EXERCISES  

1. In this question we consider a gold miner’s hedging activities.  

a. What is the natural position of a gold miner? Describe using payoff diagrams.   
b. How would a gold miner hedge her position if gold prices are expected to drop steadily over the years? Show using payoff diagrams.   
c. Would this hedge ever lead to losses?  

2. Consider the JPMorgan heating oil example in the text of this chapter. We calculated the expected profit from the spot oil purchases and forward sale after making assumptions about borrowing and storage costs. Now assume that storage costs are toward the upper end of the range provided in the Bloomberg article, i.e., $\$4.5$ instead of $\$3.85$ per ton and that insurance costs are $1.5\%$ and not $0.25\%$ of hull value. What is the expected profit in this case?  

3. Consider the oil calendar swap example provided in the text. Table 7.5 provided the swap curve derived from the futures curve. To calculate the mark-to-market value of the swap and its “fair price,” we just require information about the discount factor or yield curve. Assume the following discount factor below, taken from Blanco and Pierce (2013) and calculate the floating payments, fixed payments, net payments, NPV of the net payment and swap mark-to-market and fair price for the swap. Assume a valuation date of December 18, 2012.  

<html><body><table><tr><td>Settlements</td><td>Floating Payment ($)</td><td>Fixed Payment ($)</td><td>Net Payment ($)</td><td>Discount Factor</td><td>NPV Net Payment ($)</td></tr><tr><td>31/01/2013</td><td></td><td></td><td></td><td>0.99973</td><td></td></tr><tr><td>28/02/2013</td><td></td><td></td><td></td><td>0.99947</td><td></td></tr><tr><td>31/03/2013</td><td></td><td></td><td></td><td>0.99915</td><td></td></tr><tr><td>30/04/2013</td><td></td><td></td><td></td><td>0.99886</td><td></td></tr><tr><td>28/06/2013</td><td></td><td></td><td></td><td>0.99859</td><td></td></tr><tr><td>31/07/2013</td><td></td><td></td><td></td><td>0.99834</td><td></td></tr><tr><td>30/08/2013</td><td></td><td></td><td></td><td>0.99804</td><td></td></tr><tr><td>30/09/2013</td><td></td><td></td><td></td><td>0.99776</td><td></td></tr><tr><td>31/10/2013</td><td></td><td></td><td></td><td>0.99747</td><td></td></tr><tr><td>27/11/2013</td><td></td><td></td><td></td><td>0.99717</td><td></td></tr><tr><td>31/12/2013</td><td></td><td></td><td></td><td>0.99656</td><td></td></tr><tr><td>Swap mark-to-market</td><td></td><td></td><td></td><td></td><td>？ ？</td></tr></table></body></html>  

4. Answer the questions related to the following case study.  

# SE STUDY: HKMA AND THE HEDGE FUNDS, 1998  

The Hong Kong Monetary Authority (HKMA) has been in the news because of you and your friends, hedge fund managers. In 1998, you are convinced of the following:  

1. The $\mathrm{HKS}$ is overvalued by about $20\%$ against the $\mathrm{US}\mathbb{S}$ .   
2. Hong Kong’s economy is based on the real estate industry.   
3. High interest rates cannot be tolerated by property developers (who incidentally are among Hong Kong’s biggest   
businesses) and by the financial institutions.   
4. Hong Kong’s economy has entered a recession.  

You decide to speculate on Hong Kong’s economy with a “double play” that is made possible by the mechanics of the currency board system. You will face the HKMA as an adversary during this “play.”  

You are provided some background readings. You can also have the descriptions of various futures contracts that you may need for your activities as a hedge fund manager. Any additional data that you need should be searched for in the Internet. Answer the following questions:  

1. What is the rationale of your double-play strategy?   
2. In particular, how are HIBOR, HSI, and HSI futures related to each other?   
3. Display your position explicitly using precise futures contract data.   
4. How much will your position cost during 1 year?   
5. How do you plan to roll your position over?   
6. Looking back, did Hong Kong drop the peg?  

# Hedge Funds Still Bet the Currency’s Peg Goes  

HONG KONG—The stock market continued to rally last week in the belief the government is buying stocks to drive   
currency speculators out of the financial markets, though shares ended lower on Friday on profit-taking. Despite the earlier rally, Hong Kong’s economy still is worsening; the stock market hit a 5-year low 2 weeks ago,   
and betting against the Hong Kong dollar is a cheap and easy wager for speculators. The government maintains that big hedge funds that wager huge sums in global markets had been scooping up big   
profits by attacking both the Hong Kong dollar and the stock market.  

Under this city’s pegged-currency system, when speculators attack the Hong Kong dollar by selling it, that automatically boosts interest rates. Higher rates lure more investors to park their money in Hong Kong, boosting the currency. But they also slam the stock market because rising rates hurt companies’ abilities to borrow and expand. Speculators make money in a falling stock market by short-selling shares—selling borrowed shares in expectation that their price will fall and that the shares can be replaced more cheaply. The difference is the short-seller’s profit. “A lot of hedge funds which operate independently happen to believe that the Hong Kong dollar is overvalued” relative to the weak economy and to other Asian currencies, said Bill Kaye, managing director of hedge fund outfit Pacific Group Ltd. Mr. Kaye points to Singapore where, because of the Singapore dollar’s depreciation in the past year, office rents are now $30\%$ cheaper than they are in Hong Kong, increasing the pressure on Hong Kong to let its currency fall so it can remain competitive. Hedge funds, meanwhile, “are willing to take the risk they could lose money for some period,” he said, while they bet Hong Kong will drop its 15-year-old policy of pegging the local currency at 7.80 Hong Kong dollars to the US dollar. These funds believe they can wager hundreds of millions of US dollars with relatively little risk. Here’s why: If a hedge fund bets the Hong Kong dollar will be toppled from its peg, it’s a one-way bet, according to managers of such funds. That’s because if the local dollar is dislodged from its peg, it is likely only to fall. And the only risk to hedge funds is that the peg remains, in which case they would lose only their initial cost of entering the trade to sell Hong Kong dollars in the future through forward contracts. That cost can be low, permitting a hedge fund to eat a loss and make the same bet all over again. When a hedge fund enters a contract to sell Hong Kong dollars in, say, a year’s time, it is committed to buying Hong Kong dollars to exchange for US dollars in 12 months. If the currency peg holds, the cost of replacing the Hong Kong dollars it has sold is essentially the difference in 12-month interest rates between the United States and Hong Kong. On Thursday, that difference in interbank interest rates was about 6.3 percentage points. So a fund manager making a US\$1 million bet Thursday against the Hong Kong dollar would have paid $6.3\%$ , or US\$63,000. Whether a fund manager wanted to make that trade depends on the odds he assigned to the likelihood of the Hong Kong dollar being knocked off its peg and how much he expected it then to depreciate. If he believed the peg would depreciate about $30\%$ , as a number of hedge fund managers do, then it would have made sense to enter the trade if he thought there was a one-in-four chance of the peg going in a year. That’s because the cost of making the trade—US\$63,000—is less than one-fourth of the potential profit of a $30\%$ depreciation, or US\$300,000. For those who believe the peg might go, “it’s a pretty good trade,” said Mr. Kaye, the hedge fund manager. He said that in recent months, he hasn’t shorted Hong Kong stocks or the currency (Wall Street Journal, August 24, 1998).  