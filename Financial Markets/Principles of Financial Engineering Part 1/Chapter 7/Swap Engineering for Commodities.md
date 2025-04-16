---
tags:
  - '#arbitrage'
  - '#commodity_swaps'
  - '#crack_spread_swap'
  - '#dalian_commodity_exchange'
  - '#financial_engineering'
  - '#futures_curve'
  - '#hedging'
  - '#iron_ore_swaps'
  - '#oil_swaps'
  - '#singapore_exchange'
---
# 7.4 SWAP ENGINEERING FOR COMMODITIES  

The overall structure of commodity swaps is similar to equity swaps, which we mentioned in Chapter 4 and discuss in greater detail in Chapter 18 on cash flow engineering applications in.  

equity markets. As with equity swaps, there are two major types of commodity swaps. Parties to the swap can either (1) exchange fixed for floating payments based on a commodity index or (2) exchange payments when one payment is based on an index and the other on a money market reference rate.  

The vast majority of commodity swaps involve oil. Consider a refinery, for example. Refineries buy crude oil and sell refined products. They may find it useful to lock in a fixed price for crude oil. This way, they can plan future operations better. Hence, using a swap, a refiner may want to receive a floating price of oil and pay a fixed price per bbl..  

Such commodity or oil swaps can be arranged for all sorts of commodities, metals, precious metals, and energy prices.  

# EXAMPLE  

Japanese oil companies and trading houses are naturally short in crude oil and long in oil products. They use the short-term swap market to cover this exposure and to speculate, through the use of floating/fixedpriced swaps. Due to an overcapacity of heavy-oil refineries in the country, the Japanese are long in heavyoil products and short in light-oil products. This has produced a swap market of Singapore light-oil products against Japanese heavy-oil products.  

There is also a "paper balance" market, which is mainly based in Singapore but developing in Tokyo. This is an oil instrument, which is settled in cash rather than through physical delivery of oil.  

Thomson Reuters IFR (Issue 946)  

# 7.4.1 SWAP CASH FLOW ENGINEERING IN COMMODITY MARKETS  

Let's examine how we can engineer a commodity swap. Here we assume that the counterparties exchange payments where one payment is based on an index and the other on a money market ref-. erence rate. Suppose the $S_{t}$ represents a commodity. It could be oil for example. Then, the analysis. would be identical to engineering an equity swap..  

One could invest $N=100$ and "buy" $Q$ units of the commodity in question. The price $S_{t}$ would move over time. One can think of the investment paying (receiving) any capital gains (losses) to the investor at regular intervals, $t_{0},t_{1},...,t_{n}$ At the maturity of the investment, the $N$ is returned to the investor. All this is identical to the case of stocks covered in Chapter 4. This is illustrated in Figure 7.4a.  

One can put together a commodity swap by adding the $n$ -period FRN to this investment, as. shown in Figure 7.4b. The initial and final payments of the $N$ would cancel and the swap would. consist of paying any capital gains and receiving the capital losses and the $\mathrm{LIBOR}+d_{t}$ where $d_{t}$ is the swap spread (see Figure 7.4c).  

Note that the swap spread may deviate from zero due to any convenience yield the commodity. may offer, or due to supply-demand imbalances during short periods of time. The convenience yield here would be the equivalent of the dividends paid by the stock..  

# 7.4.2 PRICING AND VALUATION OF COMMODITY SWAPS  

Consider a commodity swap in which the counterparties exchange fixed for floating payments based on a commodity index instead of the swap type shown in Figure 7.4 in which there was an.  

![](images/e0da8a37c8c4721124a611da1ebb06e9bf70ea8efb5d2a837021bceb541af798.jpg)  

# FIGURE 7.4  

Commodity swap replication.  

<html><body><table><tr><td colspan="2">Table 7.3SampleSwap Contract</td></tr><tr><td>Fixed-price payer:</td><td>Swap dealer X</td></tr><tr><td>Floating-price payer:</td><td>Crude oil producer</td></tr><tr><td>Commodityreferenceprice:</td><td>NYMEXWTIfuturescontract</td></tr><tr><td>Fixed-price payment:</td><td>$95.00bbl×volume</td></tr><tr><td>Floating-price payment:</td><td>Theaverageoverthecalendarmonthofthedailysettlementprices for the NYMEX prompt contract times the monthly volume</td></tr><tr><td>Monthlyvolume:</td><td>100,000bbl/month</td></tr><tr><td>Term:</td><td>January2013-December2013</td></tr><tr><td>Payments:</td><td>14 business days following each settlement period</td></tr><tr><td colspan="2">Source:risk.net/energy-risk,BlancoandPiere(2013).</td></tr></table></body></html>  

exchange of payments when one payment is based on an index and the other on a money market. reference rate. The following example involves an oil producer that sells a swap to hedge revenues over a certain period.  

Here we make the assumption that the oil producer is attempting to hedge its revenues against an unexpected decline of crude oil prices in 2013. According to Table 7.3, the oil producer and the swap dealer X would agree to enter into a calendar year 2013 swap with a fixed price of. $\$95/\mathrm{b b l$ and a monthly volume of. $100{,}000{\mathrm{bbl}}$ per month. The net payment of each month is the difference between the fixed-price payment of. $\$95/\mathrm{b b l$ and the realized average. price, multiplied by the monthly volume. As a result of these terms and conditions, the seller of. the swap (the producer) will receive a payment from the swap dealer if the average oil price is lower than. $\$95/\mathrm{b b l$ . The opposite will happen if the average oil price is higher than. $\$95/\mathrm{b b l$ Assume, for example, that the floating leg of the swap settles at. $\$85/\mathrm{bbl}$ at the end of January 2013. In this case, there would be a payment from the swap dealer to the oil producer of $100,000{\mathrm{~bbl}}\times(\S95-\S85)=\S1,000,000.$ Figures $7.5\mathrm{a}$ and 7.5b illustrate the payments received by the swap seller (i.e. the oil producer) and the swap buyer (i.e., the swap dealer). For the purpose of illustration, we assume in Figure 7.5 that the floating leg of the swap settles at $\$100/\mathrm{bbl}$ and $\$105/\mathrm{bbl}$ in February 2013 and March 2013. Figure 7.5c shows the net payments to the. swap seller, i.e., the oil producer. This example shows that the swap fulfills its purpose of hedging the oil producer against unexpected decreases in oil prices. Table 7.4 explains the key contract terms used in Table 7.3. It is common for energy commodity sales and purchase contracts to have ratable delivery provisions such that the final invoice price is based on the average price. during the pricing window. This provides hedgers such as producers or consumers with an incentive to use average price swaps or a strip of futures contracts to match the pricing provisions of the physical deals..  

# 7.4.2.1 Calculating swap prices from the futures curve  

As we saw in the context of interest rate swaps, the swap rate at inception is set so that the present value of future fixed and floating payments is equal. The mark-to-market value of the interest rate swap is calculated by discounting the future cash flows using forward rates, for example. Similarly, in the case of the oil swap, we can calculate the mark-to-market gains and losses by valuing the  

![](images/f144e3ba5f50df6195e39b82c6a3807d6a6daae6897c2d263d8a035ab9a0fa7a.jpg)  

# FIGURE 7.5  

Cash flow example of oil commodity.  

<html><body><table><tr><td colspan="2">Table 7.4 Key Contract Terms of an Over-the-Counter Swap</td></tr><tr><td>Parameter</td><td>Explanation</td></tr><tr><td>Commodityreferenceprice</td><td>The commodity price index that will be used to determine the floating leg price. Common choices for the underlying are the prompt futures contract settlement, spot prices, month-ahead indices, and deferred (second-prompt prices)</td></tr><tr><td>Floating price</td><td>The formula that will be used to determine the floating leg payment. It is often the average of the daily settlements of the commodity reference price during the pricing or fixing window</td></tr><tr><td>Fixed price Fixing orpricingperiod(s)</td><td>Negotiatedpricefor thefixedlegof thecontract</td></tr><tr><td></td><td>A schedule of dates in which the underlying price will be observed to set the value of thefloatinglegforeachsettlementperiod</td></tr><tr><td>Notionalorvolume</td><td>Notional amountofcommodityusedto determine theswapcashflows</td></tr><tr><td colspan="2">Source:risk.net/energy-risk,BlancoandPiere(2013).</td></tr></table></body></html>  

swap and constructing swap prices. Commodity swap prices also require a forward curve. The price quotes for the forward curve, which are the equivalent of the forward curve implied LIBOR rates in an interest rate swap, could come from futures, forward, or swap prices or a mixture of the three. Let's assume that we use the futures curve to calculate the swap curve. This is illustrated in Table 7.5. Here we further assume that the swap curve is based on the expected average of the. futures prompt contract during a given month which involves combining two futures contract maturities for each swap price. In constructing the curve day count conventions, contract expiry dates. and holidays have to be carefully taken into account. Consider, for example, the swap curve price. for January 2013 in Table 7.5. It is based on the following calculation:.  

$$
\begin{array}{r l}{P_{\mathrm{swap,Jan}}=P_{\mathrm{future,Feb}}\times w_{1}+P_{\mathrm{future,March}}\times w_{2}}&{{}}\ {\qquad=\S88.40\times52\%+88.92\times48\%=\S88.65}&{{}}\end{array}
$$  

Table 7.5 provides the swap curve construction for months January 2013 until December 2013.  

Similar to an interest swap, the information in Table 7.5 can be used to calculate the mark-to-. market value of the swap and its "fair value." For this, we require information about the discount rate and yield curve. This is left as an exercise at the end of this chapter. The exercise also provides information about the discount rate to use to discount the cash flows..  

<html><body><table><tr><td colspan="8">Table 7.5 Building the Calendar Year 2013 Prompt Month Swap Curve from the Futures Curve</td></tr><tr><td colspan="3">Futures Curve</td><td colspan="6">SwapCurve Construction Days Swap</td></tr><tr><td>Month</td><td>Expiration</td><td>Price ($/bbl)</td><td>Date</td><td>Days Until Roll Date</td><td>After Roll Date</td><td>Weight Contract #1 (%)</td><td>Weight Contract #2 (%)</td><td>Curve (Prompt) ($)</td></tr><tr><td>January 13 February 13</td><td>16/02/2013</td><td>88.40</td><td>January 13 February 13</td><td>12 9</td><td>11 10</td><td>52 47</td><td>48 53</td><td>88.65 89.19</td></tr><tr><td>March 13</td><td></td><td></td><td>March 13</td><td>10</td><td></td><td>48</td><td>52</td><td>89.68</td></tr><tr><td>April 13</td><td>13/02/2013</td><td>88.92</td><td>April 13</td><td></td><td>11</td><td></td><td></td><td></td></tr><tr><td></td><td>14/03/2013</td><td>89.43</td><td></td><td>11</td><td>10</td><td>52</td><td>48</td><td>90.07</td></tr><tr><td>May 13</td><td>15/04/2013</td><td>89.90</td><td>May 13</td><td>12</td><td>10</td><td>55</td><td>45</td><td>90.35</td></tr><tr><td>June 13</td><td>16/05/2013</td><td>90.25</td><td>June 13</td><td>9</td><td>10</td><td>47</td><td>53</td><td>90.52</td></tr><tr><td>July 13</td><td>13/06/2013</td><td>90.47</td><td>July 13 August 13</td><td>12</td><td>10</td><td>55</td><td>45</td><td>90.60</td></tr><tr><td>August 13</td><td>16/07/2013</td><td>90.57</td><td>September 13</td><td>11 10</td><td>10 10</td><td>52 50</td><td>48</td><td>90.63</td></tr><tr><td>September 13</td><td>15/08/2013</td><td>90.63</td><td>October 13</td><td>12</td><td>11</td><td>52</td><td>50</td><td>90.63</td></tr><tr><td>October 13</td><td>13/09/2013</td><td>90.63</td><td>November 13</td><td>10</td><td>11</td><td>48</td><td>48</td><td>90.62</td></tr><tr><td>November 13</td><td>16/10/2013</td><td>90.62</td><td>December 13</td><td>9</td><td></td><td></td><td>52</td><td>90.56</td></tr><tr><td>December 13</td><td>14/11/2013</td><td>90.61</td><td></td><td></td><td>13</td><td>41</td><td>59</td><td>90.46</td></tr><tr><td>January 14</td><td>12/12/2013</td><td>90.52</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>February 14</td><td>11/01/2013</td><td>90.41</td><td>2013)</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td colspan="9"></td></tr></table></body></html>

Source: risk.net/energy-risk, Blanco and Piere (2013).  

# 7.4.3 REAL-WORLD COMPLICATIONS  

OTC commodity swaps such as the one discussed above can be customized. However, commodity. swap contract specifications and liquidity differ even in the exchange traded market. On October 19, 2014, for example, Dalian Commodity Exchange (DCE) launched an iron ore commodity swap.. The contract differs from the iron ore contract offered by the Singapore Exchange (SGX) since 2009 because there are currency and settlement differences. The DCE contract is in RMB, whereas the SGX contract is in US dollars. In contrast to the Dalian contract, which is physically settled, the SGX contract is financially settled. In 2013, SGX cleared around. $95\%$ of the world's iron ore. swaps- the remainder accounted for by trades on the Chicago Mercantile Exchange and ICE. The following example illustrates potential arbitrage opportunities and limitations in commodity. swap markets as well as real-world complications such as seasonality and time-varying liquidity.  

# EXAMPLE  

In line with a number of Chinese commodity contracts, there are only three liquid months on DCE, for contracts that settle in January, May, and September. With liquidity along larger parts of the curve in Singapore, this leaves traders with China operations able to conduct spread trades based on the arbitrage between DCE and SGX [...]  

The reason SGX volumes grew after the DCE launch is the significant difference between the two products: currency (RMB versus US\$) and physical settlement in Dalian versus financial settlement on the SGX. This has led to the creation of different, and complementary, dynamics between the exchanges.  

"The Dalian contract and the Singapore swap are fundamentally different contracts," says Leong Chean Wai, Singapore-based head of commodity derivatives at DBs Bank. "Dalian is a closed market-it isn't accessible to international players, unlike Singapore. It has, however, introduced the spread trade, which is a new element to the iron ore market, even though it is something that is commonly executed in other base metal markets. This encourages more players to enter the market and means the DCE contract has led to an increase in Singapore liquidity, rather than a fall." $I...J$  

A lot of iron ore traders in DCE trade coke, coking coal, and steel. They frequently adjust their positions among different contracts for arbitrage. This means it is difficult to predict which contract will be the most active one. [...]  

"China's futures market is still taking baby steps. A well-developed futures market usually has marketmakers who can guarantee that every listed contract has enough liquidity. But there are no market-makers in China's futures market. That's part of the reason why some contracts have great liquidity, but some do not."  

But it's not so much a lack of market-makers that is holding back liquidity along large parts of the DCE. curve; the seasonal nature of demand for commodities is also significant, according to Lin Ling, Shanghaibased analyst at Citic Futures.  

May and September are peak seasons for consuming iron ore. The consumption in January is quite low, but it's immediately before Chinese New Year and steel mills need to have some winter storage for the next year.. This rule is applicable to both coke and coking coal as well.. $I\cdot\cdot J$ The real test comes when the May contract. the first liquid month on DCE-becomes due. "It's not possible to predict how that will turn out until the actual. day. A lot will depend on where the physical is trading compared with the exchange. China has a large active physical market and traders will wait-if the physical is cheaper, they will buy that, and sell out their futures positions and if the price is lower on the DCE than the physical delivery, they will do that.".  

There is, essentially, a three-way arbitrage on the China iron ore swaps market: the DCE futures price versus the physical onshore versus the international swap market. While the former is a straightforward arbitrage of the futures price versus physical, the onshore/offshore arbitrage is a function of the different curves in SGX and DCE.  

Backward look  

Chinese commodities markets are typically characterized by contango-where the forward price is higher than the spot-due to factors such as tax, storage costs, and the limited access to onshore markets from international players, and iron ore was initially no exception. However, it has now moved into backwardation (where the futures price is below the expected future spot price for a particular commodity). East says: "What we saw when the DCE launched its iron ore futures contract was that it was in contango, whereas the SGX market was in backwardation. What happened was that all the traders came in and bought SGX backwardation and sold DCE contango." Arbitrage is inherently risky and East points to the dangers posed by a steepening of either the backwardation or contango, which can lead to mark-tomarket losses--and of course, having access to the China physical market is critical to arbitraging the DCE. and SGX markets. [...] These markets move--there is an arbitrage between the two, but also it causes. problems with regard to margining. "If the price goes up, the trader will be making a profit in one and a. loss in the other, but because these positions are in different exchanges he can't offset the margin," he says..  

Risknet/Asia Risk (April 2, 2014)  

The reading above provides example of an application of the contractual equation in Eq. (7.1) to the iron ore market. Traders can use the spot-futures parity relationship to identify arbitrage opportunity between the onshore physical and the futures market. Since iron ore contracts are traded at the DCE and SGX but exhibited different term structures, traders bet on a convergence of the curves and essentially bought low and sold high. They sold the DCE contango (where initially nearby contract prices were below back month contracts price) and bought SGX backwardation (nearby contract prices above back month ones).  

This example not only illustrates the use of commodity swaps for spread arbitrage trades, but. also the continuing spread of financial engineering applications around the world. Currently the US dollar is still the currency in which most derivatives contracts are denominated, but it is very likely that over the next decades, currencies such as the RMB and other Asian currencies will see growth in derivatives and financial engineering applications.  

# 7.4.4 OTHER COMMODITY SWAPS  

A commodity-linked interest rate swap is a hybrid swap in which LIBOR is exchanged for a fixed rate, linked to a commodity price. A buyer of crude oil may wish to tie costs to the cost of debt. The buyer could elect to receive LIBOR and pay a crude-oil-linked rate such that, as the price of crude oil rises, the fixed rate the buyer pays declines.  

A crack spread swap is a swap used by oil refiners. They pay the floating price of the refined product and receive the floating price of crude oil plus a fixed margin, the crack spread. This way, refiners can hedge a narrowing of the spread between crude oil prices and the price of their refined products.  
