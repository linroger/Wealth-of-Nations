# 7.3 THE TERM STRUCTURE OF COMMODITY FUTURES PRICES  

Table 7.1 provides the futures prices corresponding to different contract months. This is the term.   
structure of futures prices. If we plot the future prices against all contract months, we obtain a.   
curve. The nearby contracts prices are on the left and the furthest contract months are on the right.  

# 7.3.1 BACKWARDATION AND CONTANGO  

Traders use different terms to describe the shape of the curve. If the resulting curve is downward sloping, we say that it is backwardation. In other words, backwardation describes a situation where the price for forward delivery is below the price for spot delivery. If the curve is upward sloping, we say that it is in contango. Figure 7.1a and b plots examples of curves in backwardation and in contango. In Chapter 2, we introduced the concept of the basis, which was defined as the difference between the spot price of an underlying asset and its futures price. We can apply this terminology to the term structure of futures prices. A commodity whose futures curve term structure is in backwardation will have a positive basis, whereas a commodity whose futures curve term structure is in contango will have a negative basis. Below, we will discuss, in more detail, what economic mechanism can explain the shape of the commodity futures curves. Contango and backwardation also exist in the pricing of traditional financial products, but, as we will see below, the role of the underlying physical markets in commodities is much more important, especially when demand exceeds supply.  

The term structure of futures prices changes over time by commodity and it differs across com-. modities at the same point in time. Some commodities have a tendency to exhibit contango; others exhibit backwardation most of the time. As Figure 7.1 illustrates, the crude oil futures curve often tends to be in backwardation while the gold futures curve tends to be in contango. The term structure of crude oil futures prices in Table 7.1 implies that on June 20, 2014, crude oil futures were in backwardation. To illustrate how much the term structure can change and that it can flip from backwardation to contango, Figure 7.2 shows the WTI crude oil futures price term structure on four different dates. The orange line represents the curve on June 16, 2014, which is the baseline. The green line plots the term structure 1 month earlier, on May 16, 2014, the blue line plots the curve 1 year earlier, on June 14, 2013, whereas the red line shows the term structure of futures prices on June 16, 2009. As we see the curves in 2013-2014 were in backwardation, but in November 2009, the crude oil futures curve was in contango. Below we will discuss the trading opportunities that. this relatively unusual situation gave rise to. First we will turn to potential explanations for the shape of the term structure of futures prices. To do so we will build on the cash flow engineering methodology developed in earlier chapters and the relationship between commodity futures prices and the underlying replication portfolio..  

![](bbea34c53dd8b9b9af6ec0733b3b520dd6c09ae4792411332440fa17b1e78731.jpg)  

# FIGURE 7.1  

Backwardation and contango.  

# 7.3.2 CONTRACTUAL EQUATION AND SYNTHETIC COMMODITIES  

Consider the example of an oil refiner that contacts a bank asking for the price for the purchase of oil in, say, 12 months. The price quoted by the bank is not a forecast of where it thinks the price of oil will trade at the time of delivery. The bank will quote a price which depends on the cost of hedging the bank's own exposure. This is another example of the application of cash flow engineering to derivatives products. The cost of the product will be a function of the cost of the hedge. To avoid the risk of a rise in the price of oil, the bank would enter a series of transactions on the trade date to hedge its risk. Since the bank is agreeing to sell a fixed amount of oil in the future, it must first fund the purchase of oil in the spot market now and store the oil until delivery. Oil is traded in US dollars. The spot oil purchase could be financed by borrowing in US dollars at LIBOR from another bank. The bank buys the agreed amount of oil in the spot market from another institution, say another investment bank or an oil producer. The bank also incurs storage and insurance costs to store the oil until delivery. The above example is framed in the context of a bilateral OTC forward contract, but the same principle also applies to an oil futures contract.  

![](858dd3bee8f173443d4882fe0e88134b4e297d9f0d5bd5b1304893b2377ed945.jpg)  

# FIGURE 7.2  

Historical crude oil term structure of futures prices.  

We can apply the contractual equation developed earlier to create synthetic commodities. For example, suppose $S_{t}$ represents spot oil, which is the underlying asset for a futures contract with. price $F_{t}$ and expiration date $T$ $t_{0}<T$ How can we create a synthetic for this contract? The answer. is quite similar to the case of currencies. Using the same logic, we can write a contractual equation:  

![](1d467915b21571e0659d18cc75d79f0c485a91516670d3aff2577c9534b45793.jpg)  

The contractual equation above incorporates one of the distinguishing features of commodities,. which is storage costs. Most commodities can be stored at a cost. Note, however, that for some commodities, storage is either not possible (e.g., due to seasons) or prohibitive (e.g., wholesale. electricity). Figure 7.3 shows the cash flows associated with a long futures and a synthetic long. futures position (ignoring margin payments).  

We can use Eq. (7.1) to obtain two results. First, by rearranging the contracts, we create a syn. thetic spot:  

![](ebacdc7f78ae875bac12fe9c0be9059ac063db493b0ce3f512acc7a1f0ec39c7.jpg)  

In other words, after changing signs, we need to borrow one unit of oil, make a deposit of $S_{t_{0}}$ dollars, and go long an oil futures contract. This will yield a synthetic spot.  

![](6734ed0b3e8ce58a63af701e945e2a0b0d4617a8e87309cf88f17c8af163605a.jpg)  

# FIGURE 7.3  

Synthetic long crude oil futures position.  

Second, the contractual equation can be used in pricing. In fact, the contractual equation gives the carry cost of a position. To see this, first note that according to Eq. (7.1), the value of the synthetic is the same as the value of the original contract. Then, we must have  

$$
F_{t_{0}}=\big(1+r_{t_{0}}\delta\big)S_{t_{0}}+q_{t_{0}}(T-t_{0})
$$  

where $\delta$ is the factor of days' adjustment to the interest rate denoted by the symbol. $r_{t_{0}}$ and represents storage costs $q_{t_{0}}(T-t_{0})$ . The interest rate $r_{t_{0}}$ could be the LIBOR rate, for example. Storage costs include warehousing and insurance costs. The carry cost is the interest plus storage costs here.  

If storage costs are expressed as a percentage of the price, at an annual rate, just like the interes rates, this formula becomes  

$$
\boldsymbol{F}_{t_{0}}=\big(1+r_{t_{0}}\delta+q_{t_{0}}\delta\big)\boldsymbol{S}_{t_{0}}
$$  

This replication approach allows us to identify all the cash flows associated with the position and, thus, quote a fair value or theoretical price that will ensure no loss at the point of delivery, independent of the actual future spot price. Equation (7.4) is also sometimes called the spot-futures parity relationship.  

# 7.3.3 CONVENIENCE YIELD  

Note that according to Eq. (7.4), the more distant the expiration of the contracts is, the higher its price. This means that future term structures would normally be upward sloping, or in contango, as shown in Figure 7.1b. However, as we discussed above, many commodity markets such as oil and certain base metals tend to exhibit a futures price term structure in backwardation. To be able to explain a backwardated term structure, we can extend Eq. (7.3) and incorporate an additional component called the convenience yield $(c y)$ . This leads to the following equation:  

$$
F_{t_{0}}=\big(1+r_{t_{0}}\delta\big)S_{t_{0}}+q_{t_{0}}(T-t_{0})-c y
$$  

We can interpret the convenience yield as the premium that a consumer is willing to pay for being able to consume the commodity now rather than at some point in the future. One advantage of having a secure supply of raw materials is that it reduces the risk of stockouts, for example. However, the convenience yield remains a somewhat abstract concept that is intangible since it is really a mathematical placeholder that is used to reconcile the relationship between futures and spot prices in the above equation. The convenience yield cy changes in practice in response to the physical supply and demand imbalance for the underlying commodity. The convenience yield will be high if there are supply shortages and it will be lower when demand and supply are in balance. The convenience yield may be quite high for crude oil which counts oil refiners as its main consumers. First, it is expensive to store oil. Second, if there were supply shortages, the cost of closing a refinery for several months is high. For these two reasons, oil refiners may be willing to pay a premium for spot delivery. This could rationalize but not really economically (in a fundamental sense) explain a futures price that is below the spot oil price (backwardation).  

# 7.3.4 CASH AND CARRY ARBITRAGE  

We will now present a real-world arbitrage example that helps to develop the intuition for spot and futures markets dynamics as a function of supply and demand as well as storage costs. Note that Eq. (7.5) can also be used to identify potential arbitrage opportunities. If the current forward price $F_{t_{0}}$ was greater than the right-hand side-which is more likely if the curve was in contango-one would sell the forward contract, buy the commodity in the spot market (financed by a loan), pay the cost of storage, benefit from holding the physical commodity over the interval. $(t_{0};T)$ , and realize at maturity $T$ a cash and carry arbitrage. The following reading gives an example of real-world. storage and shipping costs, applies our contractual equation (7.4) and illustrates the cash and carry arbitrage in the heating oil market:.  

# EXAMPLE  

JPMorgan Hires Supertanker for Storage, Brokers Say -JPMorgan Chase & Co., the second-largest US bank by deposits, hired a newly built supertanker   
to store heating oil off Malta, shipbrokers reported, in the company's first such booking in at least   
5 years. The bank hired the Front Queen for 9 months, according to daily reports from Oslo-based SeaLeague.   
A/S and Athens-based Optima Shipbrokers Ltd. David Wells, a spokesman for JPMorgan in London,.   
declined to comment. JPMorgan, which has never hired an oil tanker based on data compiled by Bloomberg going back 5 years,   
follows companies including Citigroup Inc.'s Phibro LLC unit and BP Plc in hiring ships to store crude or oil   
products at sea. The firms are seeking to take advantage of higher prices later in the year. "It's opportunity-driven," Sverre Bjorn Svenning, an analyst at Fearnley Consultants AS in Oslo, said by   
phone. "I doubt it's going to be a permanent or new sort of trade." Heating oil for immediate delivery costs. $\$553$ a metric ton in northwest Europe and supplies for August.   
are at $\$580$ according to data compiled by Bloomberg.[...] Front Queen can hold about 273,000 tons of heating oil, more than three times the amount held by a more.   
conventional Long Range 2 tanker, according to Riverlake Shipping SA, Switzerland's largest shipbroker. JPMorgan hired the ship at \$35,000-41,000 a day, according to the broker reports. The bank is also   
paying $\$1.6$ million for the ship to sail from Singapore to Europe without a cargo, the brokers said.   
Long Range 2 tankers cost about $\$25,000$ a day for storage, according to Riverlake Shipping.. Based on a full cargo, the monthly cost for the Front Queen works out at $\$3.85-4.50$ a ton, excluding   
what JPMorgan paid to get the ship from Asia to Europe. Benchmark supertanker rates plunged $87\%$   
from their peak in July as oil producers curbed supply and ship owners expanded the global fleet.   
The Paris-based International Energy Agency expects the first back-to-back drop in global annual oil   
demand since 1983. Traders were already using smaller tankers to store record volumes of jet fuel and heating oil in Europe   
as onshore tanks filled up, D/S Torm A/S, Europe's biggest oil products shipping line, said April 3.   
Inventories of heating oil at Amsterdam, Rotterdam, and Antwerp stand at 2.7 million tons, the highest for at   
least 2 years, according to data from PJK International BV.[...] Bloomberg (extract from article "JPMorgan Hires Supertanker for Storage, Broker Say" by Alaric Nightingale - June 3, 2009)  

What is the profit that JPMorgan could expect to make on the transaction? If we make a few. simplifying assumptions we can calculate the price of the synthetic futures based on the contractual equation in Eq. (7.1) and compare it with the actual futures price available in the market. This way, we can approximate the expected profit. In other words, we assume the bank buys spot heating oil for $\$553$ , pays storage and other costs and sells a futures for. $\$580$ in the hope of making a profit.. To draw a representative futures curve, we would require futures prices for more contract months, but based on these two price points, the heating oil futures price term structure is in contango.. This is the same shape as the June 2009 crude oil term structure shown in Figure 7.2. Let's assume that JPMorgan bought 273,000 tons heating oil in the spot market in June 2009 and entered an appropriately sized short heating oil future. At an assumed spot price of. $\$553$ per metric ton, the. physical heating oil purchase in June 2009 has a value of. $\$150.969$ million. If we make a conserva-. tive assumption and take borrowing costs to be, say,. $1\%$ for 2 months, total borrowing costs would be $\$1.50969$ million over the period. Insurance costs for oil tankers can vary from. $0.25\%$ to more than $3\%$ of hull value depending on the geopolitical and macroeconomic situation. If we assume an. insurance cost of. $0.25\%$ of the value of the spot purchase for 2 months, then the total insurance cost is $\$377,423$ . The cost of shipping the tanker from Singapore to Europe is. $\$1.6$ million according to the reading. Storage costs are. $\$3.85$ per ton amount or 1.051 million for the whole cargo.. Table 7.2 provides the breakdown of expected costs and revenues. Total costs are $\$155.507163$ million. If we assume a futures price of. $\$580$ , this corresponds to revenue of. $\$158.34$ million. The expected profit is then $\$2.833$ million.  

<html><body><table><tr><td colspan="2">Table 7.2 Expected Profit Calculations for Heating Oil Example</td></tr><tr><td>Cost of buying spot heating oil</td><td>$150.969 million</td></tr><tr><td>Cost of borrowing (at 1%for 2 months)</td><td>$1.50969 million</td></tr><tr><td>Insurance costs (at 0.25%ofhullvalue)</td><td>$0.377423million</td></tr><tr><td>Costs of shipping the tanker from Singapore to Europe</td><td>$1.6million</td></tr><tr><td>Costs of storage (at $3.85 per ton)</td><td>$1.05105million</td></tr><tr><td>Total costs</td><td>$155.507163million</td></tr><tr><td>Totalrevenuefromfuturessale</td><td>$158.34million</td></tr><tr><td>Totalprofit</td><td>$2.832838million</td></tr></table></body></html>  

The above example not only illustrates the construction of a synthetic futures position, but also the exploitation of a potential arbitrage opportunity. We can ask what the effect of such transactions involving spot heating oil purchases and futures markets sales is likely to be. The extract from the Bloomberg article above suggests that many market participants engaged in such trades. This can be expected to lead to an increase in spot prices and a decrease in futures prices, thus reducing the contango and potentially moving it to the backwardation shape that energy commodities typically exhibit. The above is just an example, but it illustrates drivers of the term structure that have been found to be important in more comprehensive studies of the term structure of futures prices such as those listed at the end of this chapter.  

# 7.3.5 ANOTHER INTERPRETATION OF SPOT-FUTURES PARITY  

There are no upfront payments but buying futures or forward contracts is not costless. Ignoring any guarantees or margins that may be required for taking futures positions, taking forward or futures positions does involve a cost. Suppose we consider a storable commodity with spot price $P_{t_{0}}$ . Let the forward price be denoted by $P_{t_{0}}^{\mathrm{f}}$ . Finally, suppose storage costs and all such effects are zero. Then the futures price is given by  

$$
P_{t_{0}}^{\mathrm{f}}=\left(1+r_{t_{0}}\delta\right)P_{t_{0}}
$$  

where $r_{t_{0}}$ is the appropriate interest rate that applies for the trader and $\delta$ is the time to expiration as a proportion of a year. Now, suppose the spot price remains the same during the life of the contract. This means that the difference  

$$
P_{t_{0}}^{\mathrm{f}}-P_{t_{0}}=r_{t_{0}}\delta P_{t_{0}}
$$  

is the cost of taking this position. Note that this is as if we had borrowed $P_{t_{0}}$ dollars for $a$ "period" $\delta$ in order to carry a long position. Yet there has been no exchange of principals. In the case of a default, no principal will be lost.  
