---
title: Contango And Backwardation In Arbitrage-Free Futures-Markets
tags:
  - arbitrage_free
  - backwardation
  - carry_trades
  - contango
  - futures_prices
aliases:
  - Forward Prices
  - Futures Markets
  - Spot Prices
key_concepts:
  - Arbitrage opportunities
  - Carry and reverse trades
  - Contango and backwardation
  - Futures price determination
  - Term structure of prices
---

# Contango And Backwardation In Arbitrage-Free Futures-Markets

### Abstract

This paper gives a short recapitulation of the constraints for forward and futures prices under the condition that no risk-free profits can be achieved through arbitrage activities.

Contents
1. Introduction
1. 2. Definition of Contango and Backwardation
1. 3. Determination of Futures Prices
1. - 3.1 Carry Trades
1. - 3.2 Reverse Carry Trades
1. - 3.3 Currency Futures
1. - 3.4 Convenience Yield
1. - 3.5 Investment versus Consumption Goods
1. 4. The Term-Structure of Futures-Prices
1. 5. Conclusion

### 1. Introduction

During the financial crisis,  from July 2008 until the beginning of 2009,  oil prices fell dramatically from around $140 to $40. Futures prices also fell,  but by less. As a result,  in January 2009,  the futures price for delivery in December 2009 was about $20 above the spot price (super-contango1).

Oil bought in the spot market could be sold $20 higher on the futures market. This required oil to be stored for almost a year. In fact,  storage not only occurred on land but also at sea. As of spring 2009,  35 supertankers (about 7% of worldwide capacity) were chartered for this purpose The example demonstrates that the relationship between spot and futures prices could provide profitable arbitrage opportunities. However,  such opportunities will normally be short-lived,  since trading activities will lead to an adjustment of market prices. Because a free lunch does not exist in efficient financial markets,  arbitrage opportunities will vanish over time. In the above example,  the futures price will fall and/or the spot price will rise until the difference exactly corresponds to the sum of the costs for storage and interest payments (the so-called costs of carry). As a result,  the described carry trade would no longer be profitable.

This paper gives a short recapitulation of the constraints for forward and futures 3 prices under the condition that no risk-free profits can be achieved through arbitrage activities. We begin by defining the expressions contango and backwardation. In the main chapter,  it is analyzed how futures prices are determined in arbitrage-free markets. Finally,  we also take a short look at the whole term structure of futures prices.

### 2. Definition Of Contango And Backwardation

In this paper,  contango and backwardation are defined by the relationship of spot and futures prices. Contango describes a situation where the futures price for delivery some months ahead is above the spot price for immediate delivery,  whereas in backwardation the futures price is below the spot

1 Super-contango occurred again in spring 2020 at the beginning of the corona pandemic. 2 Dennin 2019,  p. 195ff. (Chapter 32 "Crude Oil: Contango in Texas"). 3 Unlike forward contracts,  futures contracts are traded at exchanges. In the following,  only the term "futures" will be used. Differences between forwards and futures that arise from the mechanism of daily settlement through margin accounts for exchange-traded futures are thereby neglected but see Hull 2018 p. 29f. (Chapter "The operation of margin accounts"). The title of Hull 2018,  however,  suggests that the term "futures" is sometimes also used as a general term,  comprising both forwards and futures contracts.
price. To decide whether the market is in contango or backwardation,  one therefore only has to compare the current quotations of spot and futures prices.

The theory is problematic for several reasons. First,  unlike arbitrage-free arguments developed in this paper,  the theory of Keynes requires some psychological assumptions about the risk preferences of market participants. Secondly,  contrary to Keynes,  it can be argued that risk-averse buyers such as oil refineries or flour mills,  on the other hand,  are willing to accept a surcharge on the expected market price if they can protect themselves against rising prices (normal contango). 5 Finally,  it is not immediately obvious whether a market is in normal backwardation in the sense of Keynes. To decide this,  the value of the "expected" spot price must somehow be determined. Only in retrospect can the theory be tested by comparing historical prices of already expired futures contracts with historical spot prices at maturity of these contracts The confusion between backwardation and normal backwardation (sometimes the expression normal contango is also used) has prompted some authors to avoid these terms altogether,  the textbook of Hull 2018 is an example. In any case,  it always has to be made sufficiently clear how these terms are used in a specific context. Whereas in academia the definition of Keynes is also sometimes adopted,  practitioners almost always use the terms contango and backwardation as defined in this paper.

Some confusion always arises because Keynes has introduced the expression of "normal backwardation" Keynes was concerned about the relationship of futures prices and the expectations of market participants on what the spot price will be at maturity of the futures contract. He postulated that futures prices will normally be below the "expected" spot prices,  because if riskaverse producers can sell their products in advance at a guaranteed price via the futures market,  they are willing to accept a discount relative to the expectation at which price the goods will trade a few months ahead.

4 Keynes 1930,  p. 144. 5 However,  commercial buyers may be able to pass eventual price increases on to their customers. In this case,  they would indeed be less risk-averse than producers.

6 Empirically,  normal backwardation cannot be supported,  see for example Kolb 1992.

### 3. Determination Of Futures Prices

#### 3.1 Carry Trades7

Consider an asset like a non-dividend-paying stock that provides its owner with no income. Assume a contango situation where in t = 0 the futures price F0 for delivery in say 3 months is above the spot price S0 . If,  for example,  F0 = €43 and S0 = €40,  a carry trade might be profitable where the stock is bought for S0 = €40,  held for 3 months and sold at a higher fixed price F0 = €43. If the purchase of the stock is financed by a loan,  no money is needed to finance this carry trade. Assuming an interest rate of i = 4% per annum (1% per quarter),  the trade consists of the following steps:

Action Now (T = 0)
- borrow €40 for 3 months at 1% per quarter
- - buy stock for S0 = €40
- - enter into a futures contract to sell at F0 = €43 in 3 months

Action In 3 Months (Delivery Date T = T)
- the futures contract comes due and the stock is sold for F0 = €43
- - from the proceeds,  €40.40 (€40 + 1%) is used to repay the loan
- This provides a risk-free profit of F0 *S*0 ⋅ 1, 01 = € 2, 40.
- In general,  the profit of a carry trade is 1, 01 = € 2, 40. I
- n general,  the profit of a carry trade is given as futures price F0 minus spot price S0 minus interest charges.
- If i is the interest rate per period and T denotes the time of duration of the futures contract,  the formula for the profit p of a carry trade is:

(1) p = F0 − S0(1+i)
$$p~=~F_{0}~-~S_{0}(1{+}i)^{T}$$
As already mentioned in the introduction,  trading activities will lead to an adjustment of market prices until such carry trades are no longer profitable. In a so-called arbitrage-free market,  no riskfree profits can be achieved. This corresponds to condition p ≤ 0 and implies the following upper threshold for the futures price F0 :

1. The following is explained in more detail in Hull 2018 p. 107ff. (Chapter 5. "Determination of forward and futures prices"),  Geman 2005,  p. 35ff.
In mathematical models,  it is often assumed that interest payments are not made at certain discrete points in time (e.g. annually,  quarterly or monthly),  but instead there is a continuous uninterrupted flow of payments. This can be compared to a water pool: Either a certain amount of water is regularly taken out at some discrete points in time (e.g.,  once a month or once a quarter),  or the pool might have an outflow from which water is constantly running out. As a consequence of continuous interest payments,  the compounding factor per period,  which in the discrete case is given by 1+i,  has to be replaced by e r.

1. Here,  e = 2.71828 is Euler's number and r stands for the continuously compounded interest rate. In the continuous case,  condition (2) is therefore as follows:

$${\mathrm{(4)}}$$
(4) p = e
$$p\;=\;e^{q T}F_{0}\;-\;S_{0}e^{r T}$$

(3) F0≤ S0
$$F_{0}\ \leq\ S_{0}e^{r T}$$

As an extension,  it can be assumed that some income is provided by the asset. Again,  this income may take either the form of certain payments at some discrete points in time or that of a continuous flow of money. In the first case,  the investor receives payments on his account and can thereafter collect interest on these payments. At maturity,  payments plus accrued interest would add to the profit of the carry trade given by formula (1). This would lead to a lower threshold for the futures price,  depending on the specific characteristics of the income stream.

In the continuous case,  on the other hand,  one assumes that income q is given as a percentage of the market value of the asset. If this income is continuously reinvested into the asset,  the number of assets in the investor's portfolio would grow with rate q. A portfolio with e.g.,  100 items at t = 0 would,  by continuously reinvesting the proceeds of the asset,  consist of 100 e qT items at the maturity date *t = T*. Anticipating how many assets he will have at the maturity date,  the investor sells a correspondingly higher number of futures contracts at *t = 0*. Taking the higher revenue from these additional futures contracts into account,  the profit of the carry trade per item bought in t = 0 now is:

The arbitrage-free condition p ≤ 0 then implies:

### 3.2 Reverse Carry Trades

In the previous chapter,  we have derived an upper bound for the futures price F0. The question now is whether futures prices always equal this upper bound - in which case it is said that the market is in "full carry" - or whether futures prices could also lie below that bound. A special case in which the market is not in full carry is backwardation because the futures price F0 is then even below the spot price S0.

9 The same argument as developed above for an income providing asset can then be applied to incorporate storage costs,  only that because of e
-uT < 1,  the investor now sells not a higher,  but a lower number of futures contracts. By replacing q = -u in formula (5),  one gets:

$${\mathrm{(6)}}$$
(6) F0≤ S0
$$F_{0}\ \leq\ S_{0}e^{(r+u)T}$$

Here,  the sum r+u of interest and storage costs is usually referred to as the costs of carry.

Finally,  storage costs can also be incorporated into the model. These can be treated completely analogously,  but with a reversed sign,  as "negative" income. In the discrete case,  payments for storage costs push the investor's account further into the red and reduce,  plus interest incurred,  the final profit at the maturity date.

In the continuous case,  on the other hand,  storage costs are defined as a percentage of the value of the assets. It is assumed that a certain percentage of goods must continuously be spent for storage. Storage costs are so to say paid in kind. This assumption obviously is only an approximation to reality and is primarily made to facilitate mathematical modeling. But consider,  for example,  fruits and vegetables,  where a certain percentage has spoiled during storage. For every kilogram,  e.g.,  only 950 grams might be left. Formally,  with continuous storage costs u,  this corresponds to e
-uT =
0.95.

$$\mathbf{(5)}$$
(5) F0≤ S0
$$F_{0}\ \leq\ S_{0}e^{(r-q)\, T}$$

9 Note however that,  because of formula (5),  if *r-q* < 0,  i.e. if income q exceeds interest rate r,  backwardation necessarily applies.
Let us assume backwardation with the futures price F0 of a non-dividend paying stock being below the spot price S0. For an investment fund or a life insurance firm with a sufficiently long investment horizon,  it would then be profitable to conduct a so-called "reverse" carry trade: The fund or the life insurer could sell stocks at the relatively high spot price S0,  invest the proceeds at interest rate r,  and enter into a futures contract to buy back the shares at a later point in time at the comparatively low futures price F0 *< S*0. Alternatively,  shares could instead be lent to a hedge fund for a fixed period. The hedge fund then conducts the described reverse carry trade: The shares are sold short 10,  simultaneously bought back via a futures contract and finally returned to the lender. In this case,  a lending fee for borrowing the shares is usually charged to the hedge fund,  but for the sake of simplicity,  this is neglected here.

Whereas in a usual carry trade the investor holds or "carries" the assets until the futures contract is due,  in a reverse carry trade the investor disposes himself of the assets during the term of the contract. By instead buying a futures contract,  the investor agrees to buy back the assets at maturity for a price that is fixed in advance. Crucially,  a reverse carry trade requires that enough surplus stock is available for selling and that some investors are willing to temporarily part with these assets. As we will see,  for some commodities this is not necessarily the case. However,  in this chapter,  it is assumed that it is always possible to execute reverse carry trades. These trades lead to a correction of spot and/or futures prices should the market not be in full carry.

Profit ~p from a reverse carry for an asset with no income is given by spot price S0 plus accrued interests minus the futures price:

$$\quad(7)\quad\quad\quad\widetilde{p}\ =\ S_{0}\, e^{r T}\ -\ F_{0}$$

This is exactly the negative of the profit p = −~p of a conventional carry trade. In an arbitragefree market,  neither a carry trade nor a reverse carry trade is profitable. Conditions p ≤ 0 and ~p ≤ 0 imply ~p = p = 0,  therefore:

$$\mathrm{\Large~(8)~}\qquad F_{0}\ =\ S_{0}e^{r T}$$

10 A naked short sale,  where shares are not borrowed in advance,  is not an alternative,  as physical delivery of the shares within two trading days is required by the exchanges.
Analogously to chapter 3.1,  it can be shown that this generalizes for an asset that provides income to:

$\eqref{eq:walpha}$.
(9) F0 = S0
$$F_{0}\ =\ S_{0}e^{(r-q)\, T}$$
We conclude that the inequality sign in formulas (3) and (5) can be replaced by an equals sign if there are no limits on reverse carry trades. The market will then always be in full carry.

### 3.3 Currency Futures

Next,  we consider futures on currencies. A foreign currency can be considered as an asset that provides an income q = rf,  where rf denotes the interest rate of the foreign currency. For currency futures,  there is symmetry between carry trades and reverse carry trades: Consider an investor from the U.S. who conducts a reverse carry trade in Japanese yen. She or he will borrow yen,  sell the yen at the spot market for U.S. dollars,  and will enter into a futures contract to rebuy the yen so that the yen loan can be repaid once it comes due. In the meantime,  interest could be earned on the U.S. dollar account and must be paid for the yen loan. The trade would lead to a profit if the difference between spot and futures price is greater than the interest on the yen loan minus interest earned on U.S. dollars during the term of the futures contract.

Now assume that the very same trade is instead executed by a Japanese investor. The trade would then amount to a normal carry trade: The Japanese investor would buy an asset - in this case U.S. dollar - and hold (or "carry") it until the future matures. Obviously,  whether the trade amounts to a carry trade or a reverse carry trade,  only depends on which country the investor is a resident of. In currency futures markets,  carry trades and reverse carry trades are mirror images of each other.

As a result,  if markets are sufficiently liquid,  it is always possible to execute not only carry trades but also reverse carry trades. It can be concluded from this that currency futures should always be full carry. The futures price is therefore given as:11

$$\mathrm{(10)}\qquad\qquad F_{0}\ =\ S_{0}e^{(r-r_{f})T}$$

11 It is important to be aware of how foreign currencies are quoted in practice. If for example,  the Japanese yen trades at 112 for the dollar,  this would translate into a spot price S0 = $0.0089 for the yen in the U.S. (since $1/¥112 =
0.0089). For a Japanese investor,  the spot price for the U.S. dollar would be S0 = ¥112.
It follows from this formula that a foreign currency is in contango (backwardation) if the domestic interest rate r is higher (lower) than the foreign interest rate rf. From the viewpoint of the foreign country,  the reverse applies.

### 3.4 Convenience Yield

Futures markets for commodities such as oil can be in backwardation for an extended period and hence are not always in full carry It follows that from an empirical viewpoint,  the inequality sign in formula (6) cannot be replaced by an equals sign. To understand why this is the case,  consider as an example a shortage in the wheat market. As a result,  the spot price for wheat will be relatively high. At the same time,  the next harvest is only weeks away and is expected to be a very profitable one. The shortage is therefore only temporary. Anticipating this,  today's futures prices for contracts that mature only after the next harvest has taken place will quote below the current spot price. In other words,  the futures market will be in backwardation. Because all remaining wheat supplies will be fully depleted by the time the next harvest begins,  there will be no surplus stocks left available to be sold in any reverse carry trades Backwardation would not be corrected through arbitrage activities.

As another example,  think of an oil refinery that has stored a certain amount of oil for use in the refinery process. The refinery might be tempted,  in case of backwardation,  to sell the inventory on the spot market and to invest instead in futures contracts In the time that follows,  the amount of oil needed for the refinery process would be bought daily on the spot market. The strategy might be profitable because,  if markets are in backwardation,  futures prices are relatively low compared to the spot price. The futures contracts held by the refinery are thereby intended to act as a hedge against rising oil prices. In case of a rising spot price,  some futures can be sold with a profit,  thereby offsetting the higher price to be paid on the spot market.

Obviously,  such a strategy crucially depends on spot and futures prices always moving in parallel. This will,  however,  not be the case for temporary,  short-lived market disruptions. For example,  oil production might be disrupted by technical failures or a terrorist attack15. Or think of the blockade of the Suez Canal in March 2021 by a stranded large container ship. If market participants believe

12 6-month oil futures were in backwardation from 1999 to 2004,  from second half of 2007 to first half of 2008,  from 2011 to first half 2014,  from 2018 to 2019,  and most recently in 2021.

13 For a simple model of this,  see Milonas/Thomadakis 1997. 14 This strategy corresponds to a reverse carry trade. 15 E.g. the Abqaiq–Khurais attack in September 2019 on oil facilities in Saudi Arabia.
that such disruptions are only temporary,  only the spot price will move,  whereas such events will not affect futures contracts with a maturity date on which such disruptions are,  according to market expectations,  probably over. In this case,  the hedging strategy of the oil refinery would not work,  since a rising spot price would not be accompanied by a higher futures price.

The assumption that disruptions are only temporary is crucial here because,  in case of longer lasting disruptions,  futures prices would also rise more or less in parallel with the spot price. In that case,  it would make no difference economically whether one holds the physical asset or a futures contract. Futures contracts could then indeed serve as a hedge against a rising spot price.

In addition,  also note that for spot and futures prices to behave differently,  a supply disruption need not have occurred. A certain probability for temporary disruptions to take place during the lifetime of a futures contract is sufficient to justify a lower price for a futures contract compared to the spot price. Again,  the key assumption is that such potential disruptions are only temporary and will be over before the futures contract matures.

In conclusion,  if there is a positive probability for a temporary supply disruption during the lifetime of a futures contract,  accompanied by a temporarily higher spot price,  holding the physical asset is advantageous compared to buying a long-term futures contract. Some physical storage will therefore take place even if the market is in backwardation. The owner of a physical asset has the "real option" to make use of the asset at any time,  whereas for the owner of a futures contract the asset will only be available at the delivery date. The value of this real option has been called
"convenience yield" In accordance with option price theory,  the value of the convenience yield increases with greater price volatility.

By introducing a convenience yield y,  inequality (6) can be replaced by the following equation:
The convenience yield should be interpreted as a residual value or an implicit cost item and will not show up in any profit and loss account. In this,  it differs from the explicit costs of carry such as interest costs and storage costs. Backwardation can be explained by a convenience yield y that is greater than the costs of carry r+u since it then follows from (11) that F0 < S0.

$$\mathrm{(11)}\qquad\qquad F_{0}\;=\;S_{0}e^{(r+u-y)T}$$

16 The term "convenience yield" can be traced back to Kaldor 1939 p. 6f.

### 3.5 Investment Versus Consumption Goods

The distinction between investment goods and consumption goods facilitates the understanding of why backwardation occurs in futures markets for some assets and not for others Investment goods,  on the one hand,  are goods that are only held for investment purposes and not used in industrial processes. Stocks and other securities,  currencies,  or gold are examples of investment goods. Gold,  for example,  is extracted from beneath the earth and then permanently stored below the Federal Reserve Building in New York or in the vaults of private investors Even the tiny percentage of gold that is used for industrial purposes is not permanently lost since it can eventually be recycled.

In the case of investment goods,  market transactions will only change which investor holds which assets,  but will not lead to a decrease in the number of stocks available in the market. As a consequence,  there will always be enough inventory available that can be sold through arbitrage activities should the market be in backwardation. Risk-free profits could then be achieved through reverse carry trades,  which would consequently lead to an adjustment of spot and futures prices. Futures markets for investment goods will therefore always be in full carry and backwardation in particular will not persist over an extended period.

Consumption goods,  on the contrary,  are goods that are used up in manufacturing processes After that,  they are no longer there. For example,  oil is processed in a refinery,  or wheat is ground in a mill. In this case,  the level of storage depends on both production and consumption. This can be compared to a water tank that has both an inflow and an outflow. New water must flow into the tank (i.e.,  production) to compensate for the outflow (i.e.,  consumption). If production decreases and/or consumption increases,  a shortage may result.

Such a shortage would give oil companies an incentive to produce more oil and farmers to plant more wheat. In the longer run,  production and consumption will probably balance each other out.

However,  since negative storage is not possible20,  goods that are not available until sometime in the future cannot alleviate a shortage that exists today. As a consequence,  the spot price for immediate

17 Hull 2018 p. 107. 18 Speck 2013 argues that central banks manipulate the gold market in order to protect the value of paper money relative to gold. Arbitrage mechanisms might then not work.

19 Consumption,  in this context,  obviously does not refer to consumption by private households. 20 Because only positive storage is possible,  futures prices could be below but not above full carry. Also note that in the case of e.g. electricity,  even positive storage is more or less impossible.
delivery will be higher than the price of a long term futures contract. If there are no surplus inventories and if investors are not willing to temporarily part with their assets,  this backwardation will not be corrected through reverse carry trade arbitrage.

### 4. The Term-Structure Of Futures-Prices

Until now,  we were only concerned about the relationship between the spot price and the price of a futures contract with a specific maturity date. In this chapter,  we will briefly discuss the whole term structure of future-prices for different maturities. In this context,  Samuelson 1965 already postulated that spot prices and near-end futures contracts are more volatile than contracts with a maturity date that lies further ahead in the future.

An implication of this is that the market will often be in backwardation if prices rise and in contango if prices fall. This is the case because,  if short-term prices increase (decrease) by a higher amount,  they will,  as a result,  often end up above (below) long-term futures prices. Traders often conclude from this that backwardation is a signal for rising prices and contango a signal for falling prices. However,  this rests on the assumption that the trend that has led to backwardation or contango today will also continue in the future.

As has been shown in chapter 3.4,  backwardation may arise if short-term,  only temporary market disruptions lead to a higher spot price but have no or only little effect on longer-term futures contracts. This is in accordance with the above-mentioned Samuelson hypothesis that postulates an inverse relationship between price volatility and time-to-maturity of a futures contract. In addition,  the considerations in chapter 3.4 can be used analogously to motivate the Samuelson hypothesis also in a scenario with falling spot prices.

Imagine for example that oil prices are falling because OPEC has decided to increase the supply of oil or because growth forecasts have been revised downward,  implying lower demand for oil in the coming months. If market participants believe that the longer-term outlook does not fundamentally change because of these events,  the resulting fall of oil prices would be more pronounced for the spot price and short term futures than for longer-dated futures contracts. A contango situation could then arise. However,  as demonstrated in the introductory example,  in the case of super-contango,  if long term futures quote even above full carry,  a (partial) price adjustment to full carry will take place through arbitrage activities.

### 5. Conclusion

The arbitrage-free condition implies certain constraints on the relationship between spot and futures prices. Futures prices lie below the spot price plus cost of carry because otherwise,  so-called carry trades would be profitable. Generally,  this threshold is only an upper bound for the futures price. In the case of consumption goods (i.e.,  commodities that are used in industrial processes),  supply shortages are possible. Physical ownership is then advantageous compared to holding a futures contract. Backwardation,  a situation where the futures price lies below the spot price,  may occur as a result.

### References

Dennin,  T. 2019: From Tulips to Bitcoins: A History of Fortunes Made and Lost in Commodity Markets. (Original German title: Von Tulpen zu Bitcoins. Eine Geschichte der größten Finanzblasen und wie man sie erkennt)
Geman,  H. 2005: Commodities and Commodity Derivatives. Modeling and Pricing for Agriculturals,  Metals and Energy.

Hull,  J. C. 2018: Options,  Futures,  and Other Derivatives,  10th Edition.

Kaldor,  N. 1939: Speculation and Economic Stability,  in: Review of Economic Studies,  7 (1),  p. 1-27.

Keynes,  J. M. 1930: A Treatise of Money,  Volume 2.

Kolb,  R. W. 1992: Is Normal Backwardation Normal?,  in: The Journal of Futures Markets. 12,  p. 75–91.

Milonas,  N. T.; Thomadakis,  S. B. 1997: Convenience Yield and the Option to Liquidate for Commodities with a Crop Cycle,  in: European Review of Agricultural Economics 24 (2),  267283.

Samuelson,  P. A. 1965: Proof that Properly Anticipated Prices Fluctuate Randomly. Industrial Management Review,  6,  p. 41-49.

Speck,  D. 2013: The Gold Cartel: Government Intervention on Gold,  the Mega Bubble in Paper,  and What This Means for Your Future. (Original German title: Geheime Goldpolitik. Warum die Zentralbanken den Goldpreis steuern)