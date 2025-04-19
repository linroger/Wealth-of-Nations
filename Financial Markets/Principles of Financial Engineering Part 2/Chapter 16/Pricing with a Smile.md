---
tags:
  - exotic_options
  - hedging_portfolios
  - interest_rate_derivatives
  - pricing_with_a_smile
  - volatility_smile
aliases:
  - Caps and Floors
  - Exotic Options
  - Pricing with Smile
  - Volatility Smile
key_concepts:
  - Caps and Floors
  - Exotic Option Pricing
  - Pricing and Hedging
  - Replicating Portfolio
  - Volatility Smile Parameter
---

# 16.16 PRICING WITH A SMILE  

Pricing and hedging are fairly closely related activities, at least in abstract settings. Once an asset is. replicated with liquid securities, the price of the asset is the cost of the replicating portfolio plus. some profit margin. At several points in the previous chapters, we saw that assets can be replicated using a series of options with different strike prices. This was the method applied for finding a hedge for a volatility swap in Chapter 15, for example. The replicating portfolio was made of a weighted sum of relevant options with the same characteristics except for their strikes. In. Chapter 12, we saw that option portfolios could replicate statically almost any future payoff func-. tion. Again, these options were similar except for their strike prices..  

The potential use of options with different strikes makes the volatility smile a crucial parameter in forming hedging portfolios and in pricing complex instruments. In fact, if implied volatilities. depend on the moneyness of the option, then the volatility parameters used in formulas for replicat-. ing portfolios would automatically change as the markets move and the moneyness of the replicat-. ing options changes. The critical point is that this will be true even if the underlying realized. volatility remains the same. This section presents two examples of this phenomenon..  

The first involves the class of interest rate derivatives known as caps and floors. These are among the most widely traded instruments. Their hedging and pricing are influenced in a crucial way if there is a volatility smile. The second involves the pricing and hedging of exotic options. Here also, the methodology and market practices crucially depend on the existence of the volatility smile.  
