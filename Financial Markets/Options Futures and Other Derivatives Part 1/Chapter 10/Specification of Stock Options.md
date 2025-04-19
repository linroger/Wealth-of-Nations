---
tags:
  - american_style_option
  - expiration_date
  - position_limits
  - stock_options
  - strike_price
aliases:
  - LEAPS
  - exercise limits
  - option contract
key_concepts:
  - American-style option contract
  - Expiration date details
  - Position and exercise limits
  - Stock split adjustments
  - Strike price definition
---

# 10.4  SPECIFICATION OF STOCK OPTIONS  

In the rest of this chapter, we will focus on stock options. As already mentioned, a standard exchange-traded stock option in the United States is an American-style option contract to buy or sell 100 shares of the stock. Details of the contract (the expiration date, the strike price, what happens when dividends are declared, how large a position. investors can hold, and so on) are specified by the exchange..  

# Expiration Dates  

One of the items used to describe a stock option is the month in which the expiration date occurs. Thus, a January call trading on IBM is a call option on IBM with an expiration date in January. The precise expiration date is the third Friday of the expiration month and trading takes place every business day (. $\mathrm{\zeta}8{:}30~\mathrm{a.m}$ . to $3{:}00~{\mathrm{p.m.}}$ Chicago time) until the expiration date.  

Stock options in the United States are on a January, February, or March cycle. The January cycle consists of the months of January, April, July, and October. The. February cycle consists of the months of February, May, August, and November.. The March cycle consists of the months of March, June, September, and December. If the expiration date for the current month has not yet been reached, options trade with. expiration dates in the current month, the following month, and the next two months in the cycle. If the expiration date of the current month has passed, options trade with. expiration dates in the next month, the next-but-one month, and the next two months of. the expiration cycle. Consider, for example, an option on a January cycle. At the beginning of January, options are traded with expiration dates in January, February,. April, and July, at the end of January, they are traded with expiration dates in February, March, April, and July, at the beginning of May, they are traded with expiration dates in. May, June, July, and October; and so on. When one option reaches expiration, trading. in another is started. When there is a great deal of interest in a company, options expiring in other months may trade. Also, options expiring on Fridays other than the. third Friday of a month sometimes trade. The latter are known as weekly's.  

Longer-term options, known as LEAPS (long-term equity anticipation securities), also trade on many stocks in the United States. These have expiration dates up to 39 months into the future. The expiration dates for LEAPS on stocks are always the third Friday of a January.  

# Strike Prices  

The exchange normally chooses the strike prices at which options can be written so that they are spaced $\$2.50$ $\$5$ , or $\$10$ apart. Typically the spacing is. $\$2.50$ when the stock price is between $\$5$ and $\$25$ $\$5$ when the stock price is between. $\$25$ and $\$200$ , and  

$\$10$ for stock prices above $\$200$ . As will be explained shortly, stock splits and stock dividends can lead to nonstandard strike prices.  

# Terminology  

For any given asset at any given time, many different option contracts may be trading. Suppose there are four expiration dates and five strike prices for options on a particular stock. If call and put options trade with every expiration date and every strike price, there are a total of 40 different contracts. All options of the same type (calls or puts) on a stock are referred to as an option class. For example, IBM calls are one class, whereas IBM puts are another class. An option series consists of all the options of a given class with the same expiration date and strike price. In other words, it refers to a particular contract that is traded. For example, IBM 160 October 2021 calls would constitute an option series.  

Options are referred to as in the money, at the money, or out of the money. If. $S$ is the stock price and $K$ is the strike price, a call option is in the money when $S>K$ , at the money when $S=K$ , and out of the money when $S<K$ . A put option is in the money when $S<K$ , at the money when $S=K$ , and out of the money when $S>K$ . Clearly, an option will be exercised only when it is in the money. In the absence of transaction costs, an in-the-money option will always be exercised on the expiration date if it has not been exercised previously.1  

The intrinsic value of an option is defined as the value it would have if there were no time to maturity, so that the exercise decision had to be made immediately. For a call option, the intrinsic value is therefore $\operatorname*{max}(S-K,0)$ . For a put option, it is $\operatorname*{max}(K-S,0)$ . An in-the-money American option must be worth at least as much as its intrinsic value because the holder has the right to exercise it immediately. Often it is optimal for the holder of an in-the-money American option to wait rather than exercise. immediately. The excess of an option's value over its intrinsic value is the option's time value. The total value of an option is therefore the sum of its intrinsic value and its time value.  

# FLEX Options  

The Chicago Board Options Exchange offers FLEX (short for flexible) options on. equities and equity indices. These are options where the traders agree to nonstandard terms. These nonstandard terms can involve a strike price or an expiration date that is different from what is usually offered by the exchange. They can also involve the option being European when it is normally American or vice versa. FLEX options are an attempt by option exchanges to regain business from the over-the-counter markets. The exchange specifies a minimum size (e.g., 100 contracts) for FLEX option trades..  

# Dividends and Stock Splits  

The early over-the-counter options were dividend protected. If a company declared a cash dividend, the strike price for options on the company's stock was reduced on the ex-dividend day by the amount of the dividend. Exchange-traded options are not usually adjusted for cash dividends. In other words, when a cash dividend occurs, there are no adjustments to the terms of the option contract. An exception is sometimes made for large cash dividends. When a dividend greater than $10\%$ of the stock price is declared, a committee of the Options Clearing Corporation at the CBOE can decide to adjust the terms of call and put options on the stock. Typically the effect of the adjustment is to reduce the strike price by the amount of the dividend.  

Exchange-traded options are adjusted for stock splits. A stock split occurs when the existing shares are "split"' into more shares. For example, in a 3-for-1 stock split, three new shares are issued to replace each existing share. Because a stock split does not change the assets or the earning ability of a company, we should not expect it to have any effect. on the wealth of the company's shareholders. All else being equal, the 3-for-1 stock split should cause the stock price to go down to one-third of its previous value. In general, an. $n$ -for-m stock split should cause the stock price to go down to. $m/n$ of its previous value. The terms of option contracts are adjusted to reflect expected changes in a stock price arising from a stock split. After an. $n$ -for-m stock split, the strike price is reduced to. $m/n$ of its previous value, and the number of shares covered by one contract is increased to. $n/m$ of its previous value. If the stock price declines in the way expected, the positions of both the writer and the purchaser of a contract remain unchanged..  

# Example 10.1  

Consider a call option to buy 100 shares of a company for $\$30$ per share. Suppose the company makes a 2-for-1 stock split. The terms of the option contract are then changed so that it gives the holder the right to purchase 200 shares for $\$15$ per share.  

Stock options are adjusted for stock dividends. A stock dividend involves a company. issuing more shares to its existing shareholders. For example, a $20\%$ stock dividend means that investors receive one new share for each five already owned. A stock dividend, like a stock split, has no effect on either the assets or the earning power of a company. The stock price can be expected to go down as a result of a stock dividend. The $20\%$ stock dividend referred to is essentially the same as a 6-for-5 stock split. All else being equal, it should cause the stock price to decline to. $5/6$ of its previous value.. The terms of an option are adjusted to reflect the expected price decline arising from a stock dividend in the same way as they are for that arising from a stock split.  

# Example 10.2  

Consider a put option to sell 100 shares of a company for $\$15$ per share. Suppose the company declares a $25\%$ stock dividend. This is equivalent to a 5-for-4 stock split. The terms of the option contract are changed so that it gives the holder the right to sell 125 shares for $\$12$  

Adjustments are also made for rights issues. The basic procedure is to calculate the theoretical price of the rights and then to reduce the strike price by this amount.  

# Position Limits and Exercise Limits  

The Chicago Board Options Exchange often specifies a position limit for option contracts. This defines the maximum number of option contracts that an investor can hold on one side of the market. For this purpose, long calls and short puts are considered to be on the same side of the market. Also considered to be on the same side are short calls and long puts. The exercise limit usually equals the position limit. It defines the maximum number of contracts that can be exercised by any individual (or group of individuals acting together) in any period of five consecutive business days. Options on the largest and most frequently traded stocks have positions limits of 250,000 contracts. Smaller capitalization stocks have position limits of 200,000, 75,000, 50,000, or 25,000 contracts.  

Position limits and exercise limits are designed to prevent the market from being. unduly influenced by the activities of an individual investor or group of investors. However, whether the limits are really necessary is a controversial issue.  
