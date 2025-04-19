---
tags:
  - american_options
  - arbitrage_rules
  - european_options
  - intrinsic_value
  - option_expiry
  - option_pricing
aliases:
  - Option Pricing
  - Option Value
key_concepts:
  - American option exercise
  - Arbitrage rules options
  - European option value
  - Higher strike call value
  - Longer maturity option value
  - Option value prior expiry
---

# 5.3  OPTION VALUES PRIOR TO EXPIRY  

In all the above diagrams we showed the payoff of the options on the expiry date. Prior to expiry the option value will have to be higher than the present value of the payoff and, in most cases, even higher than the intrinsic value (equal to the payoff computed with today's stock price). For American options, which can be exercised immediately, this should be obvious. One can always exercise the option for its intrinsic value, so the premium cannot be lower than that. There is then the possibility of an even greater payoff. For European options, the. argument is a little more subtle. For options on assets with no intermediate payouts (dividends, coupons), it can be shown that European calls should not be exercised early, and are thus equally as valuable as American calls.' It may be optimal to exercise American puts early and so the European options price can be lower than its American version..  

In general, the value of the option prior to expiry can be represented as a line above the intrinsic value bound (Figure 5.7).  

Option prices observe the following arbitrage rules.  

A higher strike call will be always worth less than a lower strike call with the same expiry. If ABC's stock is at 60, then a 70 call will be worth more than an 80 call because the 70 call will always pay more than an 80 call. If the stock ends up at 75, the 70 call will pay 5 while the 80 call will pay nothing. The two will pay the same only if they both pay nothing. A lower strike put will be always worth less than a higher strike put with the same maturity. The reasoning is analogous to the call case.  

An option with a longer maturity will always be worth at least as much as an otherwise. identical option with a shorter maturity. If the options have the same strikes, then their intrinsic values will be the same, but the longer option will allow more time for the underlying asset to move to generate a higher payoff. The analogy is to the insurance policy comparison between short- and long-term coverage. Since long-term coverage allows for a greater possibility of a. payoff, it will cost more. Insurance has asymmetric payoff. It pays nothing if the desired event. does not take place, no matter how "close" to it we get; on the other side, the payoff depends on how deep into-the-money we get. With options, the longer time also offers the possibility of getting deeper into the money. It is that one side of the probability distribution that determines the value of the policy.  

We will discover more arbitrage rules later.  
