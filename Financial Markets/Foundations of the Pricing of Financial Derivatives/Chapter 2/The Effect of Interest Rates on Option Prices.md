---
tags:
  - american_options
  - call_options
  - interest_rates
  - option_pricing
  - put_options
aliases:
  - Interest Rate Impact
  - Option Price Sensitivity
key_concepts:
  - American options explained
  - Call options benefit from rates
  - Early exercise neutral effect
  - Interest rates affect options
  - Put options are negatively affected
---

# 2.10 THE EFFECT OF INTEREST RATES ON OPTION PRICES

Interest rates impart a small but positive effect on call option prices and a small but negative effect on put option prices. Consider that the holder of a European call faces a payoff at. expiration of either zero or $S_{T}-X$ If interest rates increase, the value of the possible zero payoff is unaffected, but the present value of the $X$ dollars paid out if the option ends up in-the-money is less. Hence, a higher risk-free rate makes a European call option more valuable as the $S_{T}-P V(X)$ increases.

If the options are American, the results are unaffected but do require an explanation. For American calls, there might be immediate early exercise. In that case, the extra interest from the higher rate and waiting to exercise is forgone, but this effect does not disadvantage the call. If there is early exercise at any point beyond immediacy, there is additional interest saved on the payment of the exercise price. Hence, American calls are positively related to interest rates.

For the holder of a European put option, the payoff at expiration is either zero or $X-S_{T}$ . If interest rates increase, the value of the possible zero payoff is unaffected but the present value of the receipt of. $X$ dollars is lower. Consequently, rising interest rates. decrease the value of the European put.

For an American put, exercise at any time after the present but before expiration. reduces the effect of higher interest rates but does not eliminate it. Hence, American puts are negatively related to interest rates.

Note that for both American calls and puts, the effect of exercising immediately is neutral with respect to interest rates. We can easily see this by simply remembering that. an option that is immediately exercised is worth $S_{T}-X$ for a call and $X-S_{T}$ for a put. There is no interest rate effect at all. In fact, an immediately exercisable option is really not an option in that it instantly turns into either the asset, if a call, or a short position in the asset, if a put, or the cash equivalent if the contract provides for settlement in cash.

There are several other explanations for the effect of interest rates on option prices.. Most rely on the idea that the call is a leveraged transaction that substitutes for a stock margin trade and that the put is like an insurance policy. They lead to the same conclusion.
