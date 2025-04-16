---
tags:
  - '#25_delta_usd_risk_reversals'
  - '#black_scholes_formula'
  - '#dollar_strength'
  - '#market_makers'
  - '#option_markets'
  - '#quoting_conventions'
  - '#risk_reversals'
  - '#volatility_smile'
  - '#volatility_spreads'
---
# 11.5 QUOTING CONVENTIONS  

Quoting conventions in option markets may be very complicated. Given that market makers look at options as instruments of volatility, they often prefer quoting volatility directly, rather than a cash value for the option. These quotes can be very confusing at times. The best way to study them is to consider the case of risk reversals. Risk reversal quotes illustrate the role played by volatility, and show explicitly the existence of a skewness in the volatility smile, an important empirical observation that will be dealt with separately in Chapter 16.  

One of the examples concerning risk reversals presented earlier contained the following statement:  

The 1-month risk reversal jumped to 0.81 in favor of euro calls Wednesday from 0.2 2 weeks ago.  

It is not straightforward to interpret such statements. We conduct the discussion using the euro/dollar exchange rate as the underlying risk. Consider the dollar calls represented in  

![](e933a8f06646ad865897419dad86ef85c6e1c5a88315f53877a79e6140b0ab3d.jpg)  

# FIGURE 11.23  

Payoffs of ATM and 25-delta calls and puts.  

Figure 11.23a, where it is assumed that the spot is trading at 0.95, and that the option is ATM. In the same figure, we also show a 25-delta call. Similarly, Figure 11.23b shows an ATM dollar put and a 25-delta put, which will be out-of-the-money. All these options are supposed to be plain vanilla and European style.  

Now consider the following quotes for two different 25-delta USD risk reversals:  

The interpretation of such bid-ask spreads is not straightforward. The numbers in the quotes do. not relate to dollar figures, but to volatilities. In simple terms, the number to the right of the slash is the volatility spread the market maker is willing to receive for selling the risk reversal position and the number to the left is the volatility spread he is willing to pay for the position..  

The numbers to the right are related to the sale by the market maker of the 25-delta UsD call and simultaneously the purchase of a 25-delta USD put, which, from a client's point of view is the risk reversal shown in Figure 11.24a. Note that, for the client, this situation is associated with "dollar strength." If the market maker sells this risk reversal, he will be short this position.  

![](611f1cdba48ea62ecae15c9bdf4e2aabec1c67db79da33dd6472af811aa5e729.jpg)  

# FIGURE 11.24  

Payoffs of two different 25-delta USD risk reversals.  

The numbers to the left of the slash correspond to the purchase of a 25-delta USD call and the sale of a 25-delta USD put, which is shown in Figure 11.24b. This outcome, when in demand, is associated with "dollar weakness."  

# 11.5.1 EXAMPLE 1  

Now consider the interpretation of the numerical values in the first example:  

Example 1:"flat/0.3 USD call bid"  

The left side in this quote is "flat."' This means that the purchase of the 25-delta USD call, and a simultaneous sale of the 25-delta USD put, would be done at the same volatilities. A client who sells this to the market maker pays or receives nothing extra and the deal has "zero cost." In other words, the two sides would agree on a single volatility and then plug this same number into the Black-Scholes formula to obtain the cost of the put and the cost of the call. The right-hand number in the quote shows a bias. It means that the market maker is willing to sell the 25-delta UsD call, and buy the 25-delta USD put, only if he can earn O.3 volatility points net. This implies that the volatility number used in the sale of USD call will be O.3 points higher than the volatility used for the 25-delta USD put. The market maker thinks that there is a "bias' in the market in favor of dollar strength; hence, the client who purchases this risk reversal will incur a net cost.  

# 11.5.2 EXAMPLE 2  

The second quote given by  

Example $2\colon0.3/0.6$ USD call bid"  

is more complicated to handle, although the interpretation of the O.6 is similar to the first example. With this number, the market maker is announcing that he or she needs to receive O.6 volatility points net if a client wants to bet on the dollar strength.  

However, the left-hand element of the quote is not "flat' anymore but is a positive O.3. This implies that the bias in the market, in favor of dollar strength is so large, and so many clients demand this long position that, now the market maker is willing to pay net O.3 volatility points when buying the 25-delta call and selling the 25-delta put.  

Thus, in risk reversal quotes, the left-hand number is a volatility spread that the market maker is willing to pay, and the second number is a volatility spread the market maker would like to earn. In each case, to see how much the underlying options would cost, market participants have to agree on some base volatility and then, using it as a benchmark, bring in the volatility spreads..  
