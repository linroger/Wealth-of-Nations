---
tags:
  - asset_price
  - binary_options
  - cash_or_nothing
  - digital_options
  - european_option
aliases:
  - Asset-or-nothing call
  - Binary or digital options
  - Cash-or-nothing call
  - European call option
key_concepts:
  - Asset-or-nothing put
  - Discontinuous options payoffs
  - Risk-neutral world
  - Strike price
  - Thinly traded assets
---

# 26.10 BINARY OPTIONS  

Binary or digital options are options with discontinuous payoffs. A simple example of a binary option is a cash-or-nothing call. This pays off nothing if the asset price ends up.  

below the strike price at time $T$ and pays a fixed amount, $Q$ , if it ends up above the strike price. In a risk-neutral world, the probability of the asset price being above the strike price at the maturity of an option is, with our usual notation,. $N(d_{2})$ . The value of a cash-or-nothing call is therefore. $Q e^{-r T}N(d_{2})$ . A cash-or-nothing put is defined. analogously to a cash-or-nothing call. It pays off. $Q$ if the asset price is below the. strike price and nothing if it is above the strike price. The value of a cash-or-nothing put is $\bar{Q}e^{-r T}N(-d_{2})$  

Another type of binary option is an asset-or-nothing call. This pays off nothing if the underlying asset price ends up below the strike price and pays the asset price if it ends up above the strike price. With our usual notation, the value of an asset-or-nothing call is $S_{0}e^{-q T}N(d_{1})$ . An asset-or-nothing put pays off nothing if the underlying asset price ends up above the strike price and the asset price if it ends up below the strike price. The value of an asset-or-nothing put is $S_{0}e^{-q T}N\bar{(}-d_{1})$  

Binary options have discontinuous payoffs. This can create problems if the underlying asset is thinly traded so that relatively small buy or sell trades move the price. Consider a cash-or-nothing call with a strike price of $\$20$ and a payoff of. $\$1$ million. If. the final asset price is. $\$19.99$ , there is no payoff; if it is $\$20$ or more, the payoff is. $\$1$ million. If there is one day left in the life of the option and the price a little below $\$20$ , it would be tempting for the holder of the cash-or-nothing call to place buy orders for the underlying asset to tip the price over $\$20$ A similar issue can arise with barrier options on thinly traded assets. If the price of the underlying asset is close to the barrier, one side is likely to be tempted to place buy or sell orders to ensure that the barrier is reached..  

A regular European call option is equivalent to a long position in an asset-or-nothing. call and a short position in a cash-or-nothing call where the cash payoff in the cash-or-. nothing call equals the strike price. Similarly, a regular European put option is. equivalent to a long position in a cash-or-nothing put and a short position in an. asset-or-nothing put where the cash payoff on the cash-or-nothing put equals the strike price.  
