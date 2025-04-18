---
tags:
  - american_call_option
  - american_put_option
  - arbitrage
  - asset_price
  - european_call_option
  - european_put_option
aliases:
  - Arbitrage Example
  - Derivative Pricing
  - Setup and Definitions
key_concepts:
  - American call/put
  - Arbitrage definition
  - Asset price
  - European call/put
  - Risk-free rate
---

# 2.1 SETUP, DEFINITIONS, AND ARBITRAGE

We position ourselves at time $t.$ , and let. $S_{t}$ be the asset price today, $T$ be the expiration of the derivative,. $S_{T}$ be the asset price at expiration, $X$ be the exercise price,. $r_{c}$ be the annualized, continuously compounded risk-free rate, $\sigma$ be the annualized volatility, and $\tau=T-t$ be the time to expiration.1 Let $c_{t}$ be the price of a European call at time $t$ and $\mathbf{}p_{t}$ be the price of a European put at time $t.$ Let $C_{t}$ be the price of an American call at time $t$ and $P_{t}$ be the price of an American put at time $t$ Other notation will be introduced as needed. The asset is assumed to make no payments such as dividends that might be paid if the asset were a stock, but we shall relax that assumption at appropriate points.2 The results demonstrated herein are largely intuitive, but formal proofs and discussions are covered in Stoll (1969), Merton (1973a, 1973b), Smith (1976), Cox and Rubinstein (1985), and Chance and Brooks (2016).

Before starting, let us introduce the concept of arbitrage. Let us start with a definition.

Arbitrage is a market condition in which two assets or combinations of assets that produce the same results at a future date sell for different prices prior to or at that future date. When an arbitrage condition exists, it creates an opportunity for a person to buy the lower-priced asset or combination of assets and sell the higher-priced asset or combination of assets, thereby netting a positive cash flow at the initiation of the transaction, with the long and short positions offsetting and eliminating the risk, resulting in no negative potential cash flow at any future date. As a result, an arbitrage generates money at the start and has no obligation to pay any money later. It is, thus, free money..

Virtually the entire corpus of derivative pricing theory assumes that arbitrage opportuni-. ties do not exist. If they did, we assume that such opportunities would be exploited. The. buying of the lower-priced asset or combination of assets and the selling of the higherpriced asset or combination of assets will result in an increase in the cost of the former and a decrease in the cost of the latter until the prices converge..

Let us take a look at a simple example of arbitrage. Suppose someone offers you an. opportunity to bet a certain amount of money on a game in which the outcome is based on movements in the S&P 500. Specifically, if the S&P 500 goes up the next day, you receive 10. If it goes down, you receive 5. Let us assume it costs 6 to play the game. Now, consider a second game that pays 20 if the S&P 500 goes up and 10 if it goes down, but. this game costs 11 to play. It should appear that either the first game is overpriced or the second game is underpriced. If someone else is offering the second game to the public for 11, you too can offer it for 11. But if someone would pay you 11, why not just cut the cost and the payoffs in half, thereby offering the second game for 5.50 with payoffs of 10 for heads and 5 for tails. So, you offer the first game for 6 and buy into the second game. for 5.50. If the market goes up, you collect 20 on the second game and pay out 20 on the. first. If the market goes down, you collect 10 on the second game and pay out 10 on the. first. The end result is completely offset, so you have a hedged position and yet you collect $6.00-5.50=0.50$ at the start. That is your money to keep..

Of course, your instincts say that this could not happen. Someone would notice that. the two games are identical and yet are selling for different prices. But in the financial markets, there are millions of prices quoted at any one time. Almost none of them will present arbitrage opportunities, but on occasion a few will..

When an arbitrage opportunity presents itself, the person taking advantage of it, called an arbitrageur or sometimes just an $a r b$ , will buy the cheaper opportunity and sell the more expensive one, pushing up the price of the former and driving down the price of the latter until the two prices are equal.3

In the financial markets, arbitrage opportunities are rare, but they do exist very briefly.. By assuming that they are quickly exploited, we invoke a very powerful statement about human behavior that requires few, if any, restrictive assumptions. We simply assume that. people will take money that is offered if there is no risk involved. We do not have to know. whether they would take the risk to make more money. Here there is no risk, and yet there is money for the taking. We are not required to make any strong assumptions about human. behavior to know that people would act on such opportunities..

So, throughout this book, we shall assume that market prices equal the prices that are implied by models that assume that all arbitrage opportunities have been exploited.

Before exploring boundaries, limits, and other conditions, we introduce selected terminology. More detailed explanations will be given later. We now present moneyness terminology that is independent of whether you buy or sell the option. Let $S_{t}$ be the price of the underlying at time $t$ and $X$ be the exercise price of the call option, then, when $S_{t}>X$ we say that the call is in-the-money and when $S_{t}<X$ , we say that the call is out-of-the-money. When $S_{t}=X$ , the call is said to be at-the-money. Now suppose $X$ is the exercise price of the put option, then, when $S_{t}<X$ , we say that the put is in-the-money and when $S_{t}>X$ we say that the put is out-of-the-money. When $S_{t}=X$ , the put is said to be at-the-money.
