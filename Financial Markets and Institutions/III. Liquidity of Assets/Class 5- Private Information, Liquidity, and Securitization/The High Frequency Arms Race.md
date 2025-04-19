---
linter-yaml-title-alias: 'The HFT Arms Race: Example'
title: The High Frequency Arms Race
tags:
  - cme_nyse
  - high_frequency_trading
  - limit_order_book
  - market_correlation
  - market_design
aliases:
  - Frequent Batch Auctions
  - HFT Arms Race
key_concepts:
  - CME and NYSE data
  - ES vs SPY
  - High-frequency trading
  - Limit order book
  - Market correlations breakdown
---

A few slides taken from: The High-Frequency Trading Arms Race: Frequent Batch Auctions as a Market Design Response Eric Budish,  Peter Cramton and John Shim Forthcoming,  Quarterly Journal of Economics Seminar Slides,  Sept 2015

# The High Frequency Arms Race

![1_Image_0.Png](1_Image_0.Png)

- In 2010,  Spread Networks invests $300mm to dig a high-speed ber optic cable from NYC to Chicago.
- Shaves round-trip data transmission time … from 16ms to 13ms.
- Industry observers: 3ms is an eternity. Anybody pinging both markets has to be on this line,  or they're dead.
- Joke at the time: next innovation will be to dig a tunnel,  avoiding the planet's pesky curvature.
- Joke isn't that funny … Spread's cable is already obsolete!
- Not tunnels,  but microwaves (rst 10ms,  then 9ms,  now 8ms).
- Analogous races occurring throughout the financial system,  sometimes measured as minutely as microseconds or nanoseconds

# Brief Description Of The Continuous Limit Order Book

- Basic building block: limit order
- Species a price,  quantity,  and buy/sell (bid/ask)
- Buy 100 shares of XYZ at $100.00
- Traders may submit limit orders to the market at any time during the trading day
- Also may cancel or modify outstanding limit orders at any time
- Orders and cancellations are processed by the exchange one-at-a-time in order of receipt (serial process)
- Set of outstanding orders is known as the limit order book
- Trade occurs whenever a new limit order is submitted that is either (i) bid ≥ lowest ask; (ii) ask ≤ highest bid
- New limit order is interpreted as accepting (fully or partially) one or more outstanding orders
- Direct feed data from Chicago Mercantile Exchange (CME) and New York Stock Exchange (NYSE)
- Gives play by play of limit order book
- Millisecond resolution time stamps
- These are the data HFT rms subscribe to and parse in real time
- Focus primarily on a pair of instruments that track the S&$P$ 500 index
- ES: E-MinS&P 500 Future,  traded on CME
- SPY: SPDR S&P 500 Exchange Traded Fund,  traded on NYSE (and other equities exchanges)
- Time period: 2005-2011 Market Correlations Break Down at High Frequency ES vs. SPY: 1 Day

![4_image_0.png](4_image_0.png)

Market Correlations Break Down at High Frequency ES vs. SPY: 1 hour

![5_image_0.png](5_image_0.png)

Market Correlations Break Down at High Frequency ES vs. SPY: 1 minute

![6_image_0.png](6_image_0.png)

Market Correlations Break Down at High Frequency ES vs. SPY: 250 milliseconds

![7_image_0.png](7_image_0.png)

# Arb Durations Over Time: 2005-2011

Median over time Distribution by year

![8_image_0.png](8_image_0.png)