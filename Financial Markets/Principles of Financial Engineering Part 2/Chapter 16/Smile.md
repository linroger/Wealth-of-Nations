---
tags:
  - black_scholes
  - implied_volatility
  - option_pricing
  - options
  - volatility
aliases:
  - SMILE
  - Volatility Smile
key_concepts:
  - Dynamic hedging strategy
  - Expected gamma gains
  - Implied volatility smile
  - Options as volatility instruments
  - Out-of-the-money options
---

# 16.3 SMILE  

Options were introduced as volatility instruments in Chapter 9. This is very much in line with the way traders think about options. We showed that when we deal with options as volatility instruments mathematically we arrived at the same formula, in this case the same partial differential equation (PDE) as the Black-Scholes PDE. Mathematically the approach was identical to the standard textbook treatment that considers options as directional instruments.' Yet, although the interpretation in Chapter 9 is more in line with the way traders and option markets think, in that discussion there was still a major missing component.  

It turns out that everything else being the same, an out-of-the-money put or call has a higher implied volatility than an ATM call or put. This effect, alluded to several times up to this point, is called the volatility smile. However, in order to discuss the smile in this chapter we adopt still another interpretation of options as instruments.  

The discussion in Chapter 9 showed that the option price (after some adjustments for interest receipts and payments) is actually related to the expected gamma gains due to volatility in the underlying. The interpretation we use in this chapter will show that these expected gains will depend on the option's strike. One cost to pay for this interesting result is the need for a different mathematical approach. The advantage is that the smile will be the natural outcome. A side advantage is that we will discuss a dynamic hedging strategy other than the well-known delta-hedging. In fact, we start the chapter with a discussion of options from a more "recent' point of view which. uses the so-called dirac delta functions. It is perhaps the best way of bringing the smile explicitly. in option pricing.  
