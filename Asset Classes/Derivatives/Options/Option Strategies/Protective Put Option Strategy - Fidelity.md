---
created: 2024-02-04T03:34:55 (UTC -06:00)
tags: []
source: https://www.fidelity.com/learning-center/investment-products/options/options-strategy-guide/protective-put
author: The Options Institute at CBOE®
---

# PROTECTIVE PUT OPTION STRATEGY - FIDELITY

> ## Excerpt
> A protective put position is created by buying (or owning) stock and buying put options on a share-for-share basis.

---
## PROTECTIVE PUT (LONG STOCK + LONG PUT)

### POTENTIAL GOALS

There are typically two different reasons why an investor might choose the protective put strategy;

1. To limit risk when first acquiring shares of stock. This is also known as a “married put.”
2. To protect a previously-purchased stock when the short-term forecast is bearish but the long-term forecast is bullish.

A protective put position is created by buying (or owning) stock and buying put options on a share-for-share basis. In the example, 100 shares are purchased (or owned) and one put is purchased. If the stock price declines, the purchased put provides protection below the strike price. The protection, however, lasts only until the expiration date. If the stock price rises, the investor participates fully, less the cost of the put.

## EXAMPLE OF PROTECTIVE PUT (LONG STOCK + LONG PUT)

<table><tbody><tr><td>Buy 100 shares XYZ stock at 100.00</td></tr><tr><td>Buy 1 XYZ 100 put at 3.25</td></tr></tbody></table>

Potential profit is unlimited, because the underlying stock price can rise indefinitely. However, the profit is reduced by the cost of the put plus commissions.

Risk is limited to an amount equal to stock price minus strike price plus put price plus commissions. In the example above, the put price is 3.25 per share, and stock price minus strike price equals 0.00 per share (100.00 – 100.00). The maximum risk, therefore, is 3.25 per share plus commissions. This maximum risk is realized if the stock price is at or below the strike price of the put at expiration. If such a stock price decline occurs, then the put can be exercised or sold. See the Strategy Discussion below.

Stock price plus put price

In this example: 100.00 + 3.25 = 103.25

<table><tbody><tr><td>Buy 100 shares XYZ stock at 100.00</td></tr><tr><td>Buy 1 XYZ 100 put at 3.25</td></tr></tbody></table>

![[Protective Put Option Strategy - Fidelity/protectiveput600x340.png]]

|Stock Price at Expiration| Long StockProfit/(Loss) at Expiration | Long 100 Put Profit/(Loss) at Expiration | Protective Put Profit/(Loss) at Expiration |
| --- | --- | --- | --- |
|108| +8.00 | (3.25) | +4.75 |
| 107 | +7.00 | (3.25) | +3.75 |
| 106 | +6.00 | (3.25) | +2.75 |
| 105 | +5.00 | (3.25) | +1.75 |
| 104 | +4.00 | (3.25) | +0.75 |
| 103 | +3.00 | (3.25) | (0.25) |
| 102 | +2.00 | (3.25) | (1.25) |
| 101 | +1.00 | (3.25) | (2.25) |
| 100 | 0 | (3.25) | (3.25) |
| 99 | (1.00) | (2.25) | (3.25) |
| 98 | (2.00) | (1.25) | (3.25) |
| 97 | (3.00) | (0.25) | (3.25) |
| 96 | (4.00) | +0.75 | (3.25) |

The protective put strategy requires a 2-part forecast. First, the forecast must be bullish, which is the reason for buying (or holding) the stock. Second, there must also be a reason for the desire to limit risk. Perhaps there is a pending earnings report that could send the stock price sharply in either direction. In this case, buying a put to protect a stock position allows the investor to benefit if the report is positive, and it limits the risk of a negative report. Alternatively, an investor could believe that a downward trending stock is about to reverse upward. In this case, buying a put when acquiring shares limits risk if the predicted change in trend does not occur.

Buying a put to limit the risk of stock ownership has two advantages and one disadvantage. The first advantage is that risk is limited during the life of the put. Second, buying a put to limit risk is different than using a stop-loss order on the stock. Whereas a stop-loss order is price sensitive and can be triggered by a sharp fluctuation in the stock price, a long put is limited by time, not stock price. The disadvantage of buying a put is that the total cost of the stock is increased by the cost of the put.

If the stock price is below the strike price at expiration, then a decision has to be made whether to (a) sell the put and keep the stock position unprotected, (b) sell the put and buy another put, thus extending the protection, or (c) exercise the put and sell the stock and invest the funds elsewhere. There is no “right” or “wrong” choice; every investor must make a personal decision based on the forecast and the desire to hold the stock.

The total value of a protective put position (stock price plus put price) rises when the price of the underlying stock rises and falls when the stock price falls. Although value of the two parts, the long stock and the long put, change in different directions, in the language of options, a protective put position has a “positive delta.”

The value of a long put changes opposite to changes in the stock price. When the stock price rises, the long put decreases in price and incurs a loss. And, when the stock price declines, the long put increases in price and earns a profit. Put prices generally do not change dollar-for-dollar with changes in the price of the underlying stock. Rather, puts change in price based on their “delta.” The delta of a long at-the-money put is typically about -50%, so a$1 stock price decline causes an at-the-money long put to make about 50 cents per share. Similarly, a$1 stock price rise causes an at-the-money long put to lose about 50 cents per share. In-the-money long puts tend to have deltas between -50% and -100%. Out-of-the-money long puts tend to have deltas between zero and -50%.

In a protective put position, the negative delta of the long put reduces the sensitivity of the total position to changes in stock price, but the net delta is always positive.

Volatility is a measure of how much a stock price fluctuates in percentage terms, and volatility is a factor in option prices. As volatility rises, option prices tend to rise if other factors such as stock price and time to expiration remain constant. A long put, therefore, benefits from rising volatility and is hurt by decreasing volatility. As a result, the total value of a protective put position will increase when volatility rises and decrease when volatility falls.

The time value portion of an option’s total price decreases as expiration approaches. This is known as time erosion. Since long puts decrease in value and incur losses when time passes and other factors remain constant, the total value of a protective put position decreases as time passes and other factors remain constant.

Stock options in the United States can be exercised on any business day, and the holder (long position) of a stock option position controls when the option will be exercised. Since a protective put position involves a long, or owned, put, there is no risk of early assignment.

If a put is exercised, then stock is sold at the strike price of the put. In the case of a protective put, exercise means that the owned stock is sold and replaced with cash. Puts are automatically exercised at expiration if they are one cent ($0.01) in the money. Therefore, if an investor with a protective put position does not want to sell the stock when the put is in the money, the long put must be sold prior to expiration.

There are important tax considerations in a protective put strategy, because the timing of protective put can affect the holding period of the stock. As a result, the tax rate on the profit or loss from the stock can be affected. Investors should seek professional tax advice when calculating taxes on options transactions. The following topics are summarized from the brochure, “_Taxes and Investing_” published by The [Options](Options.md) Industry Council and available free of charge from [www.cboe.com](http://www.cboe.com/ "www.cboe.com").

“Protective puts” and “married puts” involve the same combination of long stock and long puts on a share-for-share basis, but the names imply a difference in timing of when the puts are purchased. A “married put” implies that stock and puts are purchased at the same time, and married puts do not affect the holding period of the stock. If a stock is held for more than one year before it is sold, then long-term rates apply, regardless of whether the put was sold at a profit or loss or expired worthless.

A “protective put” implies that stock was purchased previously and that puts are being purchased against an existing stock position, and protective puts can affect the holding period of the stock for tax purposes. If a stock is owned for less than one year when a protective put is purchased, then the holding period of the stock starts over for tax purposes. However, if a stock is owned for more than one year when a protective put is purchased, then the gain or loss on the stock is considered long-term regardless of whether the put is exercised, sold at a profit or loss or expires worthless.
