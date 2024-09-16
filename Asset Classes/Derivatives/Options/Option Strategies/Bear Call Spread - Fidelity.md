---
created: 2024-01-29T05:45:06 (UTC -06:00)
tags: []
source: https://www.fidelity.com/learning-center/investment-products/options/options-strategy-guide/bear-call-spread
author: The Options Institute at CBOE®
---

# BEAR CALL SPREAD - FIDELITY

> ## Excerpt
> A bear call spread consists of one short call with a lower strike price and one long call with a higher strike price. Learn more.

---
### GOAL

To profit from neutral to bearish price action in the underlying stock.

### EXPLANATION

A bear call spread consists of one short call with a lower strike price and one long call with a higher strike price. Both calls have the same underlying stock and the same expiration date. A bear call spread is established for a net credit (or net amount received) and profits from either a declining stock price or from time erosion or from both. Potential profit is limited to the net premium received less commissions and potential loss is limited if the stock price rises above the strike price of the long call.

## EXAMPLE OF BEAR CALL SPREAD

<table><tbody><tr><td>Sell 1 XYZ 100 call at</td><td>3.30</td></tr><tr><td>Buy 1 XYZ 105 call at</td><td>(1.50)</td></tr><tr><td>Net credit =</td><td>1.80</td></tr></tbody></table>

### MAXIMUM PROFIT

Potential profit is limited to the net premium received less commissions, and this profit is realized if the stock price is at or below the strike price of the short call (lower strike) at expiration and both calls expire worthless.

### MAXIMUM RISK

The maximum risk is equal to the difference between the strike prices minus the net credit received including commissions. In the example above, the difference between the strike prices is 5.00 (105.00 – 100.00 = 5.00), and the net credit is 1.80 (3.30 – 1.50 = 1.80). The maximum risk, therefore, is 3.20 (5.00 – 1.80 = 3.20) per share less commissions. This maximum risk is realized if the stock price is at or above the strike price of the long call at expiration.

Short calls are generally assigned at expiration when the stock price is above the strike price. However, there is a possibility of early assignment. See below.

### BREAKEVEN STOCK PRICE AT EXPIRATION

Strike price of short call (lower strike) plus net premium received.

In this example: 100.00 + 1.80 = 101.80

### PROFIT/LOSS DIAGRAM AND TABLE: BEAR CALL SPREAD

<table><tbody><tr><td>Sell 1 XYZ 100 call at</td><td>3.30</td></tr><tr><td>Buy 1 XYZ 105 call at</td><td>(1.50)</td></tr><tr><td>Net credit =</td><td>1.80</td></tr></tbody></table>

![[bearcallspread600x330.png]]

| Stock Price at Expiration | Short 100 Call Profit/(Loss) at Expiration | Long 105 Call Profit/(Loss) at Expiration | Bear Call Spread Profit/(Loss) at Expiration |
| --- | --- | --- | --- |
| 108 | (4.70) | +1.50 | (3.20) |
| 107 | (3.70) | +0.50 | (3.20) |
| 106 | (2.70) | (0.50) | (3.20) |
| 105 | (1.70) | (1.50) | (3.20) |
| 104 | (0.70) | (1.50) | (2.20) |
| 103 | +0.30 | (1.50) | (1.20) |
| 102 | +1.30 | (1.50) | (0.20) |
| 101 | +2.30 | (1.50) | +0.80 |
| 100 | +3.30 | (1.50) | +1.80 |
| 99 | +3.30 | (1.50) | +1.80 |
| 98 | +3.30 | (1.50) | +1.80 |
| 97 | +3.30 | (1.50) | +1.80 |
| 96 | +3.30 | (1.50) | +1.80 |

### APPROPRIATE MARKET FORECAST

A bear call spread earns the maximum profit when the price of the underlying stock is below the strike price of the short call (lower strike price) at expiration. Therefore, the ideal forecast is “neutral to bearish price action.”

### STRATEGY DISCUSSION

The bear call spreads is a strategy that “collects option premium and limits risk at the same time.” They profit from both time decay and falling stock prices. A bear call spread is the strategy of choice when the forecast is for neutral to falling prices and there is a desire to limit risk.

### IMPACT OF STOCK PRICE CHANGE

A bear call spread benefits when the underlying price falls and is hurt when it rises. This means that the position has a “net negative delta.” _Delta_ estimates how much an option price will change as the stock price changes, and the change in option price is generally less than dollar-for-dollar with the change in stock price. Also, because a bear call spread consists of one short call and one long call, the net delta changes very little as the stock price changes and time to expiration is unchanged. In the language of options, this is a “near-zero gamma.” _Gamma_ estimates how much the delta of a position changes as the stock price changes.

### IMPACT OF CHANGE IN VOLATILITY

Volatility is a measure of how much a stock price fluctuates in percentage terms, and volatility is a factor in option prices. As volatility rises, option prices tend to rise if other factors such as stock price and time to expiration remain constant. Since a bear call spread consists of one short call and one long call, the price of a bear call spread changes very little when volatility changes and other factors remain constant. In the language of options, this is a “near-zero vega.” _Vega_ estimates how much an option price changes as the level of volatility changes and other factors are unchanged.

### IMPACT OF TIME

The time value portion of an option’s total price decreases as expiration approaches. This is known as time erosion. Since a bear call spread consists of one short call and one long call, the sensitivity to time erosion depends on the relationship of the stock price to the strike prices of the spread. If the stock price is “close to” or below the strike price of the short call (lower strike price), then the price of the bear call spread decreases (and makes money) with passing of time. This happens because the short call is closest to the money and erodes faster than the long call. However, if the stock price is “close to” or above the strike price of the long call (higher strike price), then the price of the bear call spread increases (and loses money) with passing time. This happens because the long call is now closer to the money and erodes faster than the short call. If the stock price is half-way between the strike prices, then time erosion has little effect on the price of a bear call spread, because both the short call and the long call erode at approximately the same rate.

### RISK OF EARLY ASSIGNMENT

Stock options in the United States can be exercised on any business day, and holders of a short stock option position have no control over when they will be required to fulfill the obligation. Therefore, the risk of early assignment is a real risk that must be considered when entering into positions involving short options.

While the long call (higher strike) in a bear call spread has no risk of early assignment, the short call (lower strike) does have such risk. Early assignment of stock options is generally related to dividends, and short calls that are assigned early are generally assigned on the day before the ex-dividend date. In-the-money calls whose time value is less than the dividend have a high likelihood of being assigned. Therefore, if the stock price is above the strike price of the short call in a bear call spread (the lower strike price), an assessment must be made if early assignment is likely. If assignment is deemed likely and if a short stock position is not wanted, then appropriate action must be taken. Before assignment occurs, the risk of assignment can be eliminated in two ways. The entire spread can be closed, which involves buying the short call to close and selling the long call to close. Alternatively, the short call can be purchased to close and the long call open can be kept open.

If early assignment of a short call does occur, the obligation to deliver stock can be met either by buying stock in the marketplace or by exercising the long call. Note, however, that whichever method is chosen, the date of stock acquisition will be one day later than the date of the stock sale. This difference will result in additional fees, including interest charges and commissions. Assignment of a short call might also trigger a margin call if there is not sufficient account equity to support the stock position created by the option assignment.

### POTENTIAL POSITION CREATED AT EXPIRATION

There are three possible outcomes at expiration. The stock price can be at or below the lower strike price, above the lower strike price but not above the higher strike price or above the higher strike price. If the stock price is at or below the lower strike price, then both calls in a bear call spread expire worthless and no stock position is created. If the stock price is above the lower strike price but not above the higher strike price, then the short call is assigned and a short stock position is created. If the stock price is above the higher strike price, then the short call is assigned and the long call is exercised. The result is that stock is sold at the lower strike price and purchased at the higher strike price and the result is no stock position.

### OTHER CONSIDERATIONS

The “bear call spread” strategy has other names. It is also known as a “short call spread” and as a “credit call spread.” The term “bear” refers to the fact that the strategy profits with bearish, or falling, stock prices. The term “short” refers to the fact that this strategy is “short the market,” which is another way of saying that it profits from falling prices. Finally, the term “credit” refers to the fact that the strategy is created for a net credit, or net amount received.
