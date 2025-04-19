---
tags:
  - commodity_markets
  - currency_exchange
  - discounting
  - equity_valuation
  - financial_assets
aliases:
  - Equity, Commodity, Currency
  - Stocks, Commodities, Currencies
key_concepts:
  - Commodity definition
  - Currency trading
  - Discounted cash flows
  - Dividend growth
  - Stock valuation
---

# 2.5 EQUITY, COMMODITY, AND CURRENCY MATH  

Stocks, like bonds, are financial assets offering a promise of future cash flows: dividends and capital gains. These cash flows are, however, much less certain. While coupon interest must be paid at the scheduled dates, cash dividends are only paid if declared by the company. Also, bond price fluctuations are constrained by the magnitude of interest rate changes and their. impact on discounting; capital gains and losses on stocks can be very large, as both the cash flows (the numerator) and the discount rate (the denominator) affect the present value of the future, very uncertain, cash flows. Stock valuation is not an exact science and depends critically on the easy-to-disagree-on assumption of the rate of change (growth) in future cash flows. While we review the details of dividend and free cash flow discounting in a later chapter, we offer the basics here.  

Commodities are physical assets of uniform enough quality to trade in bulk. They are. purchased not for the benefit of future cash flows, but for use in production, or for a promise of price appreciation. The major groups of commodities are agricultural, metals, energy and financials. Each commodity's quality is defined very strictly in physical terms -- size and quality. or chemical composition -- to ensure near perfect substitutability. West Texas Intermediate oil is a commodity; Brent crude is a separate commodity as it is not as light or as sweet as WTI.. The price of a commodity is typically defined in currency per appropriate physical quantity:. oil in dollars per barrel, corn in cents per bushel, equity index in dollars per index point..  

Currencies are special commodities in that their prices are defined in currency per unit of another currency, and therefore can be inverted and are naturally traded in a triangular way, i.e. one currency traded for another, then for another, and then for another or the same.  

# 2.5.1 Equities  

Fundamentally, the price of a stock is equal to the discounted value of all the dividends/cash flows received over the expected holding horizon plus the discounted value of the final price received for the stock at the end of the holding horizon. Since, rationally, the final price that the next buyer will pay must reflect the discounted value of all the future dividends from then on, today's stock price can be viewed as the discounted value of all the dividends/cash flows received during the holding horizon and beyond. Thus, if Jack buys the stock today and. expects to hold it for $n$ years, he would value the stock as the PV of all the dividends and the. PV of the sale price  

$$
P_{0}=\frac{D_{1}}{1+r}+\frac{D_{2}}{(1+r)^{2}}+\cdot\cdot\cdot+\frac{D_{n}+P_{n}}{(1+r)^{n}}
$$  

Realizing that the price $P_{n}$ Jill will pay him for the stock. $n$ years from today is simply the PV of all the dividends over her holding horizon plus the PV of the dividends over all subsequent holding horizon to infinity, Jack would value the stock simply as the PV of the. perpetual sequence of dividends  

$$
P_{0}=\frac{D_{1}}{1+r}+\frac{D_{2}}{(1+r)^{2}}+\cdot\cdot\cdot+\frac{D_{n}}{(1+r)^{n}}+\frac{D_{n+1}}{(1+r)^{n+1}}+\cdot\cdot\cdot
$$  

This sequence of dividends can follow several canonical patterns. If the dividends are expected to grow at a constant percentage rate $g$ per year (which is less than the discount rate), then we can use the formula for the sum of an infinite geometric series to get the price of the stock today  

$$
P_{0}=\frac{D_{1}}{r-g}
$$  

Stocks with a high growth rate $g$ are called growth stocks; stocks with a low growth rate. $g$ are called value stocks (growth can even be negative). We discuss the relationship of growth rates, dividends, and earnings to price/earnings (P/E) ratios in Chapter 11. Here we point out that the assumption about. $g$ is critical in valuing a stock. Suppose both Jack and Jill are trying. to evaluate a stock expected to pay at the end of the year a dividend of. $\$3$ , but Jack expects the dividends to grow at $8\%$ per year while Jill is more optimistic and expects the dividends to grow at $9\%$ per year. Both apply the same discount rate of. $12\%$ . They calculate the following fundamental values for the stock:.  

$$
P_{J a c k}={\frac{3}{0.12-0.08}}={\mathbb{S}}75\quad p_{J i l l}={\frac{3}{0.12-0.09}}={\mathbb{S}}100
$$  

In stock valuation, even a minute news release changing the forecast of the growth rate of. earnings, or cash flow can lead to significant price revisions. Chapter 11 contains a thorough review of the fundamental equity valuation using discounted free cash flow.  

# 2.5.2Currencies  

Currencies are commodities. They trade in bulk and are of uniform quality: a 20-euro note can be replaced by 20 1-euro coins without loss of value. Normally, the price of a commodity is quoted in currency per physical unit of commodity like a bushel, a barrel or a metric tonne. Currencies, also called foreign exchange (FX), are special since the priced physical unit of the commodity is also a currency. One pound sterling (the priced commodity) may cost 1.5 US dollars (pricing currency), or 1 US dollar (priced commodity) may cost O.6667 pounds sterling (pricing currency). The price in pounds per dollar is equivalent to the reciprocal of the price in dollars per pound. Exchanging dollars for pounds can be described either as selling dollars or buying pounds.  

The other feature distinguishing currencies from other commodities is that we often want to know and transact at the cross ratio. We rarely exchange 300 barrels of oil for bushels of wheat. However, when returning to London from Mexico, we may want to exchange the leftover 600 pesos for pounds without first selling pesos for dollars and then dollars for pounds..  

Let us review quote conventions and some potential issues. In what follows, we use the easily recognizable three-letter currency codes as adopted by the transaction messaging system SWIFT. Most currencies around the world are quoted with respect to a vehicle currency which is one of the major hard currencies, e.g. USD, GBP, or EUR. A currency can be quoted in European terms, i.e. in currency per dollar, or American terms in dollars per currency. Most British Commonwealth currencies (AUD, NZD, etc.) and the euro (EUR) follow the American convention (US dollars per euro or pound). Most others (e.g. CHF, PLZ, JPY) follow the European convention (Swiss francs or Danish krone per US dollar). Remembering all this is important when observing quotes or percentage appreciation rates that are not labeled. This text follows the standard in which a spot exchange rate is denoted by. $X$ with the terms in square brackets or as a superscript. For example 1.5 dollars per pound sterling is:.  

$$
X^{U S D/G B P}=X\left[\frac{U S D}{G B P}\right]=1.50
$$  

For any two currencies, the FX rate in currency 1 per unit of currency 2 uniquely determines the FX rate in currency 2 per unit of currency 1, i.e. $X[C u r r1/C u r r2]=1/X[C u r r2/C u r r1]$ In our example:  

$$
X\left[{\frac{G B P}{U S D}}\right]={\frac{1}{X\left[{\frac{U S D}{G B P}}\right]}}=0.6667
$$  

Most FX rates are quoted to 4 decimal places, except when the whole number is large they are quoted to 2 decimal places; for example, a JPY/UsD quote may be 119.23. Often, the quotation units are assumed to follow the common (European or American) convention and are dropped. This may lead to misinterpretation of appreciation statistics. Consider Table 2.4, which you may see in the press.  

Do the negative $\%$ Change numbers mean that all the listed currencies depreciated against the dollar? On the contrary, the CHF, quoted as CHF/USD, has actually appreciated as it takes 0.0030 fewer Swiss francs to buy $\$1$ than it did yesterday, while the other two currencies,. AUD and EUR, have in fact depreciated.  

Table 2.4 Currency changes against the USD as of .... ./2009   


<html><body><table><tr><td></td><td>Last</td><td>Change</td><td>%Change</td></tr><tr><td>AUD</td><td>0.5457</td><td>-0.0014</td><td>-0.3</td></tr><tr><td>EUR</td><td>1.0205</td><td>-0.0020</td><td>-0.2</td></tr><tr><td>CHF</td><td>1.6844</td><td>-0.0030</td><td>-0.2</td></tr></table></body></html>  

Confusion may also come in the percentage change statistics. If the AUD costs USD 0.5457 today and it cost 0.5471 yesterday, then we compute the percentage change as:  

$$
\%\Delta X^{U S D/A U D}=-0.0014/0.5471=-0.002559=-0.2559\%
$$  

as shown in Table 2.4. Does this mean that the USD has appreciated by $0.2559\%?$ Absolutely not. Today the USD costs:  

$$
X^{A U D/U S D}=1/X^{A U D/U S D}=1/0.5457=1.832509
$$  

Yesterday it cost:  

$$
X^{A U D/U S D}=1/X^{A U D/U S D}=1/0.5471=1.827819
$$  

or AUD 0.004689 more. The percentage change in the value of the USD expressed in AUD is then  

$$
\%\Delta X^{A U D/U S D}=0.004689/1.827819=0.002566=0.2566\%
$$  

The simple explanation is that the percentage change is not equal to the negative of the percentage change in the reciprocals. Over longer periods of time the differences can be great. More complications arise when interpreting analysts' mean forecasts of currency rates. Suppose that currently  

$$
X^{\frac{U S D}{A U D}}=0.75,\mathrm{orequivalently},X^{\frac{A U D}{U S D}}=1{\frac{1}{3}}
$$  

Half of the analysts polled predict the rate to go to $X^{\frac{U S D}{A U D}}=0.50$ $\begin{array}{r}{\left(X\frac{A U D}{U S D}=2\right)}\end{array}$ and the other half to $X^{\frac{U S D}{A U D}}=1.\dot{0}0$ $\begin{array}{r}{X^{\frac{A U\bar{D}}{U S D}}=1,}\end{array}$ . On average, in USD/AUD terms, they predict the rate to be $0.75~(=\textstyle{\frac{1}{2}}.0.5+\textstyle{\frac{1}{2}}.1.0)$ , i.e. no appreciation. At the same time, on average, the same analysts implicitly predict the rate in AUD/USD terms to be $\textstyle{1.5(={\frac{1}{2}}.2+{\frac{1}{2}}.1)}$ , i.e. a USD appreciation from 1-1/3. One can find examples where, on average, both currencies may be expected to appreciate at the same time! The main lesson from these examples is that one always needs to be aware of the quotation terms being assumed when interpreting statements about appreciation or depreciation.  

The main law governing spot currency trading is that of no triangular arbitrage. In the inter-dealer market, all spot FX rates have to be 'in line' with each other in such a way that buying one currency through a vehicle is neither cheaper nor more expensive than buying it directly. The rule, of course, does not apply to retail markets. Let us illustrate.  

![](3e6fc1944f0da999299ac6bf2525b33cbed6a5d358bf1e0d06e8a9da7f65a083.jpg)  
Figure 2.18 Triangular arbitrage  

Suppose you observe in New York: $X^{\frac{J P Y}{U S D}}=118.50$ and $X^{\frac{H K D}{U S D}}=7.80$ At the same moment, a dealer in Tokyo quotes $X^{\frac{J P Y}{H K D}}=15.02$ Can you profit?  

Figure 2.18 illustrates the method, assuming that you start with JPY 1 million in your pocket.  

With JPY 1 million in your pocket, you purchase HKD $66,577.8961=[J P Y]1,000,000/$ [JPY/HKD] 15.02 in Tokyo. At the same time, in New York, you sell HKD 66,577.8961 for $[H K D]~66,577.8961/[H K D/U S D]~7.80,$ or USD 8,535.6277, and, with that, buy $[U S D]~8,535.6277\cdot[J P Y/U S D]~118.50.$ or JPY 1,O11,471.88. You are able to make an instant profit of JPY 11,471.88 simply because HKD is cheap in the direct (cross) market in Tokyo relative to New York. In New York, it takes [JPY $/U S D]118.50/[H K D/U S D]7.80=$ JPY 15.19 to buy HKD 1.00, whereas, in Tokyo, HKD 1 costs only JPY 15.02.  

You would not be alone in pursuing this triangle arbitrage opportunity. Dealers in New York. would sell dollars for yen, convert the yen into HK dollars in Tokyo and, with HK dollars, buy. back US dollars in New York (it does not matter where you start on the triangle). Every dealer. around the globe would be going in the same direction. The USD-into-JPY trade would drive up the yen, the JPY-into-HKD trade would drive up HKD relative to JPY, and the HKD-intoUSD trade would drive the USD up against the HKD. Likely, all three quotes would change. until the yen price of HK dollars was the same in New York and Tokyo..  

In the above, we ignore the transaction costs in the form of a bid-ask spread. In reality, we need to modify the computed amounts by considering that we would sell at the bid and buy at the ask. Instead of simply one FX cross rate, we need to compute its bid and ask. The principle remains the same.  

The triangular arbitrage principle binds hundreds of possible currency combinations. As soon as one FX quote changes in the market, many others must follow..  
