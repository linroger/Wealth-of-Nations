---
aliases:
- Alias_221_Short Diagonal Spread with Calls - Fidelity.md
- Alias_222_Short Diagonal Spread with Calls - Fidelity.md
author: "The Options Institute at CBOE\xAE"
created: 2024-01-29T05:54:12 (UTC -06:00)
source: https://www.fidelity.com/learning-center/investment-products/options/options-strategy-guide/short-diagonal-spread-calls
tags:
- tag_example
---



# SHORT DIAGONAL SPREAD WITH CALLS - FIDELITY

> ## Excerpt
> A short diagonal spread with calls is created by selling one

---
### POTENTIAL GOALS

To profit from bearish stock price action with limited risk if the stock price rises.

### EXPLANATION

A short diagonal spread with calls is created by selling one “longer-term” call with a lower strike price and buying one “shorter-term” call with a higher strike price. In the example a two-month (56 days to expiration) 95 Call is sold and a one-month (28 days to expiration) 100 Call is purchased. This strategy is established for a net credit, and both the profit potential and risk are limited. The maximum profit is realized if the stock price falls sharply below the strike price of the short call, and the maximum risk is realized if the stock price is at the strike price of the long call on the expiration date of the long call.

## EXAMPLE OF SHORT DIAGONAL SPREAD WITH CALLS

<table><tbody><tr><td>Buy 1 28-day XYZ 100 call</td><td>(3.35)</td></tr><tr><td>Sell 1 56-day XYZ 95 call</td><td>7.60</td></tr><tr><td>Net credit =</td><td>4.25</td></tr></tbody></table>

### MAXIMUM PROFIT

The maximum profit potential of a short diagonal spread with calls is equal to the net credit received less commissions. If the stock price falls sharply below the strike price of the short call, then the value of the spread approaches zero; and the full credit received is kept as income.

### MAXIMUM RISK

The maximum risk is realized if the stock price is equal to the strike price of the long call on the expiration date of the long call. With the stock price at the strike price of the long call at expiration of the long call, the loss equals the price of the short call minus the net credit received when the position was established less commissions. This is the point of maximum loss because the short call has its maximum difference in price with the expiring long call. It is impossible to know for sure what the maximum loss potential is, because it depends of the price of short call, and that price is subject to the level of volatility which can change.

**Important!** **If the short option is held beyond the long option expiration the new short only position will be considered uncovered and will have unlimited risk.**

### BREAKEVEN STOCK PRICE AT EXPIRATION OF THE LONG CALL

There is one breakeven point, which is below the strike price of the short call. Conceptually, the breakeven point at expiration of the long call is the stock price at which the price of the short call equals the net credit received for the spread. It is impossible to know for sure what the breakeven stock price will be, however, because it depends of the price of the short call which depends on the level of volatility.

### PROFIT/LOSS DIAGRAM AND TABLE: SHORT DIAGONAL SPREAD WITH CALLS

<table><tbody><tr><td>Buy 1 28-day XYZ 100 call</td><td>(3.35)</td></tr><tr><td>Sell 1 56-day XYZ 95 call</td><td>7.60</td></tr><tr><td>Net credit =</td><td>4.25</td></tr></tbody></table>

![[ShortDiagnolSpreadCalls600x330.png]]

| Stock Price at Expiration of the 28-day Call | Long 1 28-day 100 Call Profit/(Loss) at Expiration | Short 1 56-day 95 Call Profit/(Loss) at Expiration of the 28-day Call\* | Net Profit/(Loss) at Expiration of the 28-day Call |
| --- | --- | --- | --- |
| 115 | +11.65 | (12.60) | (0.95) |
| 110 | +6.65 | (7.70) | (1.05) |
| 105 | +1.65 | (3.20) | (1.55) |
| 100 | (3.35) | +0.65 | (2.70) |
| 95 | (3.35) | +4.00 | +0.65 |
| 90 | (3.35) | +6.10 | +2.75 |
| 85 | (3.35) | +7.10 | +3.75 |

\*Profit or loss of the short call is based on its estimated value on the expiration date of the long call. This value was calculated using a standard Black-Scholes options pricing formula with the following assumptions: 28 days to expiration, volatility of 30%, interest rate of 1% and no dividend.

### APPROPRIATE MARKET FORECAST

A short diagonal spread with calls realizes its maximum profit if the stock price is sharply below the strike price of the short call on the expiration date of the long call. The forecast, therefore, must be “bearish.”

### STRATEGY DISCUSSION

A short diagonal spread with calls is a logical strategy choice when the stock price is above the strike price of the short call and the forecast is for bearish stock price action.

Short diagonal spreads with calls are frequently compared to simple bear spreads with calls in which both calls have the same expiration date. The differences between the two strategies are the profit potential, the risk, and the alternative courses of action at expiration of the long call. Short diagonal spreads are established for a greater net credit than comparable bear call spreads, because the price of the longer-dated short call is higher than the price of the same-strike, shorter-dated call in a comparable bear call spread. Also, the maximum risk is less if the stock price rises sharply.

The tradeoff is that a short diagonal spread incurs a loss if the stock price is at the strike price of the short call on the expiration date of the long call, while a bear call spread would realize a profit. In this scenario, the longer-dated short call in a short diagonal spread experiences less time decay than the shorter-dated, same-strike call in a comparable bear call spread.

A potential benefit of a short diagonal spread with calls is that, after the long call expires, the short call remains open and can be “managed” in a number of ways. First, the short call can be left open in the hopes that it will expire worthless. Although this strategy has unlimited risk and is not suitable for many investors, it offers the possibility of earning the maximum profit potential of the strategy. Second, the short call can be converted to a bear call spread by buying a call with a higher strike price and the same expiration date as the open short call. This limits risk and leaves intact the potential for additional profits. Third, the short call can be converted to a bull call spread by buying a call with a lower strike price and the same expiration date as the open short call. While this managing alternative increases risk if the stock price declines, it offers potential profits if the stock price forecast has changed to bullish.

### IMPACT OF STOCK PRICE CHANGE

“Delta” estimates how much a position will change in price as the stock price changes. Long calls have positive deltas, and short calls have negative deltas. When the position is first established, the net delta of a short diagonal spread with calls is negative. With changes in stock price and passing time, however, the net delta varies from slightly positive to approximately −0.90, depending on the relationship of the stock price to the strike prices of the calls and on the time to expiration of the long call.

If the stock price equals the strike price of the long call at expiration of the long call, the position delta approaches −0.90. In this case, the delta of the in-the-money short call approaches −0.90 (depending on volatility and on the time to expiration), and the delta of the expiring long call goes to zero.

When the stock price is above the strike price of the long call at expiration of the long call, the position delta is slightly positive, because the delta of the short call approaches −0.90 and the delta of the in-the-money expiring long call approaches +1.00.

The position delta approaches zero if the stock price falls sharply below the strike price of the short call, because the deltas of both calls approach zero.

### IMPACT OF CHANGE IN VOLATILITY

Volatility is a measure of how much a stock price fluctuates in percentage terms, and volatility is a factor in option prices. As volatility rises, option prices tend to rise if other factors such as stock price and time to expiration remain constant. Long options, therefore, rise in price and make money when volatility rises, and short options rise in price and lose money when volatility rises. When volatility falls, the opposite happens; long options lose money and short options make money. “Vega” is a measure of how much changing volatility affects the net price of a position.

Since vegas decrease as expiration approaches, a short diagonal spread with calls generally has a net negative vega when the position is first established. Consequently, rising volatility generally hurts the position and falling volatility generally helps. The vega is most negative when the stock price is equal to the strike price of the short call, and it is least negative when the stock price is equal to the strike price of the long call.

The net vega approaches zero if the stock price falls sharply below the strike price of the short call or rises sharply above the strike price of the long call. In both cases, with the options both far out of the money or both deep in the money, both vegas approach zero.

### IMPACT OF TIME

The time value portion of an option’s total price decreases as expiration approaches. This is known as time erosion. “Theta” is a measure of how much time erosion affects the net price of a position. Long option positions have negative theta, which means they lose money from time erosion, if other factors remain constant; and short options have positive theta, which means they make money from time erosion.

Short diagonal spreads with calls generally have a net positive theta when first established, because the positive theta of the short call more than offsets the negative theta of the long call. However, the theta can vary from positive to negative depending on the relationship of the stock price to the strike prices of the calls and on the time to expiration of the shorter-dated long call.

The theta is most positive when the stock price is close to the strike price of the short call, and it is the least positive or possibly negative when the stock price is close to the strike price of the long call.

### RISK OF EARLY ASSIGNMENT

Stock options in the United States can be exercised on any business day, and holders of short stock option positions have no control over when they will be required to fulfill the obligation. Therefore, the risk of early assignment is a real risk that must be considered when entering into positions involving short options.

While the long call in a short diagonal spread with calls has no risk of early assignment, the short call does have such risk, even though there is considerable time to its expiration. While one might think that a short option with 28 days or more to expiration has a near-zero chance of being assigned, this thinking is incorrect. Early assignment of stock options is generally related to dividends, and short calls that are assigned early are generally assigned on the day before the ex-dividend date. In-the-money short calls whose time value is less than the dividend have a high likelihood of being assigned. Even long-term options are assigned early when the conditions are right.

If the short call is assigned prior to the expiration of the long call, then 100 shares of stock are sold short and the long call remains open. If a short stock position is not wanted, it can be closed in one of two ways. First, 100 shares can be purchased in the marketplace. Second, the short 100-share position can be closed by exercising the long call. Although exercising a long call will forfeit the time value of that call, in the case of a short diagonal spread with calls, this is rarely a concern for the following reason. If the longer-term short call in a short diagonal spread is assigned, then there is probably no time value in the long call as it is much closer to its expiration. Therefore, in a short diagonal spread with calls, it is generally preferable to exercise the long call to close the short stock position. Buying shares to cover the short stock position and then selling the long call is only advantageous if the commissions are less than the time value of the long call, which, as noted above, is unlikely if the time value of the longer-dated short call is less than the dividend.

Note, however, that whichever method is used, buying stock or exercising the long call, the date of the stock purchase will be one day later than the date of the short sale. This difference will result in additional fees, including interest charges and commissions. Assignment of a short call might also trigger a margin call if there is not sufficient account equity to support the short stock position.

### POTENTIAL POSITION CREATED AT EXPIRATION OF THE LONG CALL

The position at expiration of the long call depends on the relationship of the stock price to the strike price of the long call. If the stock price is at or below the strike price of the long call, then the long call expires worthless and the short call remains open.

If the stock price is above the strike price of the long call, then the long call is exercised. The result is a two-part position consisting of a short call and long 100 shares of stock. If the stock price is above the strike price of the long call immediately prior to its expiration, and if a position of long 100 shares is not wanted, then the long call must be closed (sold).

### OTHER CONSIDERATIONS

The term “diagonal” in the strategy name originated when options prices were listed in newspapers in a tabular format. Strike prices were listed vertically in rows, and expirations were listed horizontally in columns. Therefore a “diagonal spread” involved options in different rows and different columns of the table; i.e., they had different strike prices and different expiration dates.
