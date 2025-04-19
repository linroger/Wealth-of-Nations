---
tags:
  - american_option
  - european_option
  - option_pricing
  - option_value
  - volatility
aliases:
  - Option Pricing and Volatility
  - Volatility and Options
key_concepts:
  - European/American options
  - Exercise price and asset price
  - Higher volatility, higher value
  - In-the-money outcome
  - Volatility and option value
---

# 2.11 THE EFFECT OF VOLATILITY ON OPTION PRICES

If it is not already intuitively obvious, it is simple to demonstrate that a call option on an asset with higher volatility will be worth more, all else equal. For example, consider an option with any expiration except immediate. The options can be European or American.

Let the exercise price be $X$ and the underlying asset price be S. Let us specify that the underlying can make only two moves, up or down. It can move up by $\Delta S$ or down by $\Delta S$ Thus, its new price is either $S+\Delta S$ or $S-\Delta S.$ Let us specify that if the up move occurs, the option expires in-the-money, is exercised, and, therefore, pays off $S+\Delta S-X$ If it moves down, the option expires out-of-the-money, and is, therefore, not exercised and worth zero.

It is easy to treat the value of $\Delta S$ as a good measure of the volatility of the underlying.. The greater is $\Delta S$ , the more volatile is the asset. Suppose that we increase the volatility. by making $\Delta S$ be a bit larger. Let us use the factor. $\Delta^{*}S$ to represent a higher volatility.. In that case, the payoff of the option will be. $S+\Delta^{*}S$ in one outcome and zero in the other. We can see that the in-the-money outcome is higher, and the out-of-the-money outcome is. the same as when the volatility was S. We also see that these outcomes occur in the same corresponding conditions as when the volatility was lower. A similar argument applies for puts.

Hence, it should be quite clear that higher volatility leads to a higher option value.. This result will hold regardless of whether there are dividends. In addition, because an. American call need not be exercised early, it can be made to produce the same payoffs as a European call. Hence, the right to exercise early does not impair the positive effect of. volatility.
