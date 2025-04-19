---
tags:
  - arbitrage
  - call_option
  - derivative_pricing
  - option_valuation
  - risk_free_asset
aliases:
  - Call Option Example
  - Option Pricing
  - Valuing Options
key_concepts:
  - Arbitrage opportunity
  - Asset price movement
  - Call option definition
  - Option price determination
  - Risk-free asset investment
---

# 6.5 A FIRST LOOK AT VALUING OPTIONS

Let us now create a different kind of derivative, a call option. We use the same example where the asset is priced at 70 and can go up to 100 with. $60\%$ probability or down to 50 with $40\%$ probability. Suppose someone tells you that if you will give them some money. today, you will acquire the right to buy the asset at 75 one period later but are not obliged to do so. Let us determine how much money you would need to pay to acquire that right.

If the asset goes up to 100 in one period, you would pay your 75 and acquire the 100. asset, netting a gain of 25. If the asset goes down to 60, it would not be worth paying 75. to acquire the asset. You would simply choose not to acquire the asset, thereby ending up. with zero. This asset, which is a call option, is therefore an instrument that pays either 25 or zero one period later. We wish to know how much you would have to pay for this asset. Clearly it is somewhere between 25 and zero..

Suppose we buy two of these options and invest 47.62 in the risk-free asset, which will pay $5\%$ interest, so that one year later, it will be worth $47.62(1.05)=50.$ This 50 is the lower of the two outcomes for the asset. Now, consider the outcomes:

If the good economy occurs: You exercise the option, paying 75 and acquiring an asset.
worth 100 for a gain of 25. Because two options have been purchased, you have 50.
You collect your 50 from the risk-free asset for a total payoff of 100..

If the bad economy occurs: The option will not be worth exercising. You will, however, collect the 50 on the risk-free asset, so your total payoff will be 50.

So, in a good economy, your total wealth is 100 and in a bad economy, your total wealth is 50. These outcomes are the same as if you had bought the asset. Therefore, the amount you should have to pay to achieve this outcome should be the same as the cost of the asset,. which is 70. Because you would pay 47.62 for the risk-free asset and you bought two options, the price of each option should be.

$$
{\frac{70-47.62}{2}}=11.19.
$$

If the price of the option were lower than 11.19, one could buy the options and the. risk-free asset and produce a payoff equal to that of the underlying asset. That means one. could sell short the asset and receive net of 11.19 at the start, but one would pay less than 11.19. One period later, the options and the risk-free asset would exactly offset, thereby.

eliminating any uncertainty. One would then pocket the difference between 11.19 and what the option costs. If the option costs more than 11.19, the reverse arbitrage would be. done: Sell the option and issue the risk-free bond, while buying the asset. In both cases, one earns an arbitrage profit. This arbitrage activity would continue until the price of the. option adjusts to eliminate the opportunity. Of course, that occurs with the option price. at 11.19.
