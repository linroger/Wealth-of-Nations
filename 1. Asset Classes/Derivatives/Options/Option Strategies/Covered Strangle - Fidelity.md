---
created: 2024-01-29T05:52:09 (UTC -06:00)
tags: []
source: https://www.fidelity.com/learning-center/investment-products/options/options-strategy-guide/covered-strangle
author: The Options Institute at CBOE®
---

# COVERED STRANGLE - FIDELITY

> ## Excerpt
> A covered strangle position is created by buying (or owning) stock and selling both an out-of-the-money call and an out-of-the-money put. Learn more.

---
## COVERED STRANGLE: (LONG STOCK + SHORT OOM CALL + SHORT OOM PUT)

### GOAL

To earn leveraged income from modestly bullish price action in the underlying stock.

### EXPLANATION

A covered strangle position is created by buying (or owning) stock and selling both an out-of-the-money call and an out-of-the-money put. The call and put have the same expiration date. The maximum profit is realized if the stock price is at or above the strike price of the short call at expiration. Profit potential is limited and loss potential is substantial and leveraged if the stock price falls. Below the strike price of the put, losses are$2.00 per share for each$1.00 decline in stock price, because both the long stock and the short put lose as the stock price declines.

Note that the short put is not “covered” as the strategy name implies, because cash is not held in reserve to buy additional shares. See Strategy Discussion below.

## EXAMPLE OF COVERED STRANGLE: (LONG STOCK + SHORT OOM CALL + SHORT OOM PUT)

<table><tbody><tr><td>Buy 100 shares XYZ stock at 100.00</td></tr><tr><td>Sell 1 XYZ 105 call at 1.40</td></tr><tr><td>Sell 1 XYZ 95 put at 1.20</td></tr></tbody></table>

### MAXIMUM PROFIT

Profit potential is limited to the total premiums received plus upper strike price minus stock price. In the example above, the maximum profit is 7.60, because the total premiums received are 2.60 (1.40 + 1.20) and the upper strike price minus stock price equals 5.00 (105.00 – 100.00).

### MAXIMUM RISK

Potential loss is substantial and leveraged if the stock price falls. Below the lower strike price at expiration, losses are$2.00 per share for each$1.00 decline in stock price, because both the long stock and the short put lose as the stock price declines.

### BREAKEVEN STOCK PRICE AT EXPIRATION

If stock price – lower strike price > total premiums: Breakeven = stock price minus total premiums received In this example: 100 - (1.40 + 1.20) = 97.40 If stock price – lower strike price < total premiums: Breakeven = Lower Strike price – 0.50 ͯ \[Total premiums minus (stock price minus lower strike price)\] If total premiums had equaled 7.00: 95.00 – 0.50 ͯ \[7.00 – (100.00 – 95.00)\] = 94.00

### PROFIT/LOSS DIAGRAM AND TABLE: COVERED STRANGLE

<table><tbody><tr><td>Buy 100 shares XYZ stock at 100.00</td></tr><tr><td>Sell 1 XYZ 105 call at 1.40</td></tr><tr><td>Sell 1 XYZ 95 put at 1.20</td></tr></tbody></table>

![[coveredstrangle600x340.png]]

| Stock Price at Expiration | Long Stock Profit/(Loss) at Expiration | Short 105 Call Profit/(Loss) at Expiration | Short 95 Put Profit/(Loss) at Expiration | Covered Strangle Profit/(Loss) at Expiration |
| --- | --- | --- | --- | --- |
| 108 | +8.00 | (1.60) | +1.20 | +7.60 |
| 107 | +7.00 | (0.60) | +1.20 | +7.60 |
| 106 | +6.00 | +0.40 | +1.20 | +7.60 |
| 105 | +5.00 | +1.40 | +1.20 | +7.60 |
| 104 | +4.00 | +1.40 | +1.20 | +6.60 |
| 103 | +3.00 | +1.40 | +1.20 | +5.60 |
| 102 | +2.00 | +1.40 | +1.20 | +4.60 |
| 101 | +1.00 | +1.40 | +1.20 | +3.60 |
| 100 | 0 | +1.40 | +1.20 | +2.60 |
| 99 | (1.00) | +1.40 | +1.20 | +1.60 |
| 98 | (2.00) | +1.40 | +1.20 | +0.60 |
| 97 | (3.00) | +1.40 | +1.20 | (0.40) |
| 96 | (4.00) | +1.40 | +1.20 | (1.40) |
| 95 | (5.00) | +1.40 | +1.20 | (2.40) |
| 94 | (6.00) | +1.40 | +0.20 | (4.40) |
| 93 | (7.00) | +1.40 | (0.80) | (6.40) |
| 92 | (8.00) | +1.40 | (1.80) | (8.40) |

### APPROPRIATE MARKET FORECAST

The covered strangle strategy requires a modestly bullish forecast, because the maximum profit is realized if the stock price is at or above the strike price of the short call at expiration.

### STRATEGY DISCUSSION

A covered strangle is the combination of an out-of-the-money covered call (long stock plus short out-of-the-money call) and an out-of-the-money short put. The short put is not “covered” as the strategy name implies, however, because cash is not held in reserve to buy shares if the put is assigned. Rather, the long stock position, or account equity, is used as collateral to meet the margin requirement for the short put. Below the lower strike price both the long stock and short put incur losses, and, as a result, percentage losses are twice what they would be for a covered call position alone.

Choosing the covered strangle strategy based on a modestly bullish forecast requires both a high tolerance for risk and trading discipline. High tolerance for risk is required, because risk is leveraged on the downside. Trading discipline is required because the ability to “cut losses short” is an attribute of trading discipline. Many traders who use the covered strangle strategy have strict guidelines – which they adhere to – about closing positions when the market goes against the forecast.

### IMPACT OF STOCK PRICE CHANGE

“Delta” estimates how much a position will change in price as the stock price changes. Long stock and short puts have positive deltas, and short calls have negative deltas. Although the net delta of a covered strangle position is always positive, it varies between 0.00 and +2.00 depending on the relationship of the stock price to the strike prices of the options.

If the stock price is between the strike prices, then the position delta is approximately +1.00, because the delta of the long stock is +1.00 and the negative delta of the short call almost exactly offsets the positive delta of the short put.

The position delta approaches zero as the stock price rises above the strike price of the short call, because the delta of the covered call (long stock plus short call) approaches zero, and the delta of the short put also approaches zero.

The position delta approaches +2.00 as the stock price falls below the strike price of the short put, because the deltas of the long stock and short put both approach +1.00, while the delta of the short call approaches zero.

### IMPACT OF CHANGE IN VOLATILITY

Volatility is a measure of how much a stock price fluctuates in percentage terms, and volatility is a factor in option prices. As volatility rises, option prices tend to rise if other factors such as stock price and time to expiration remain constant. Short option positions, therefore, rise in price and lose money when volatility rises. When volatility falls, short option positions make money. Since a covered strangle has two short options, the position loses doubly when volatility rises and profits doubly when volatility falls. However, because the options are out-of-the-money in a covered strangle, the impact of changing volatility is generally less for a covered strangle than for a covered straddle.

### IMPACT OF TIME

The time value portion of an option’s total price decreases as expiration approaches. This is known as time erosion, and short option positions profit from time erosion if other factors remain constant. Since a covered strangle position has two short options, the positions profits doubly from the passing of time to expiration. However, because the options are out-of-the-money in a covered strangle, the impact of time erosion is generally more linear for a covered strangle than for a covered straddle, which experiences less time erosion initially and more time erosion as expiration approaches.

### RISK OF EARLY ASSIGNMENT

Stock options in the United States can be exercised on any business day, and the holder of a short stock option position has no control over when they will be required to fulfill the obligation. Therefore, the risk of early assignment is a real risk that must be considered when entering into positions involving short options.

Both the short call and the short put in a covered strangle have early assignment risk. Early assignment of stock options is generally related to dividends.

Short calls that are assigned early are generally assigned on the day before the ex-dividend date. In-the-money calls whose time value is less than the dividend have a high likelihood of being assigned. Therefore, if the stock price is above the strike price of the short call, an assessment must be made if early assignment is likely. In the case of a covered strangle, it assumed that being assigned on the short call is a good event, because assignment of the call converts the stock position to cash and a profit is realized (not including the short put which remains open – with risk – until expiration). However, if selling the stock is not wanted, then buying the short call to eliminate the possibility of assignment is necessary.

Short puts that are assigned early are generally assigned on the ex-dividend date. In-the-money puts whose time value is less than the dividend have a high likelihood of being assigned. Therefore, if the stock price is below the strike price of the short put, an assessment must be made if early assignment is likely. In the case of a covered strangle, it is assumed that being assigned on the short put is not wanted, because the purchase of additional shares requires additional capital and/or a possible margin call. Therefore, if early assignment of the short put is deemed likely, the short put must be purchased to eliminate the possibility of assignment. However, if additional shares are wanted, then no action needs to be taken.

If early assignment of the short put does occur, and if the stock position is not wanted, the stock can be closed in the marketplace by selling. Note, however, that the date of the closing stock sale will be one day later than the date of the opening stock purchase (from assignment of the put). This one-day difference will result in additional fees, including interest charges and commissions. Assignment of a short put might also trigger a margin call if there is not sufficient account equity to support the stock position.

### POTENTIAL POSITION CREATED AT EXPIRATION

If the short call in a covered strangle is assigned, then the stock is sold at the strike price of the call and replaced with cash. Assuming the put expires, there is no stock position, only cash.

If the short put in a covered strangle is assigned, then stock is purchased at the strike price of the put. Assuming the call expires, the result is that the initial stock position is doubled.

### OTHER CONSIDERATIONS

Although the short call in a covered strangle position is covered by the long (or owned) stock, the short put, as noted above, is not “covered,” because no cash is held in reserve as it is in the case of a cash-secured short put. In the case of a covered strangle, the account equity including the long stock is used as collateral for the margin requirement for the short put. Therefore, if account equity declines sufficiently, a margin call will be triggered. The covered strangle is suitable only for aggressive investors who are suited to taking this risk.

If it is the intention to <u>not sell the stock</u>, then there are two possible tax considerations for the short (covered) call, (1) the strike price of the call, and (2) the time to expiration of the call. Each of these can affect the holding period of the stock for tax purposes. As a result, the tax rate on the profit or loss from the stock might be affected. Investors should seek professional tax advice when calculating taxes on options transactions. The following topics are summarized from the brochure, “_Taxes and Investing_” published by The [Options](Options.md) Industry Council and available free of charge from [www.cboe.com.](http://www.cboe.com/ "www.cboe.com.")

A “qualified covered call” does not affect the holding period of the stock. Generally, a “qualified covered call” has more than 30 days to expiration and is “not deep in the money.” A non-qualified covered call suspends the holding period of the stock for tax purposes during its life. For specific examples of qualified and non-qualified covered calls refer to “_Taxes and Investing_.”
