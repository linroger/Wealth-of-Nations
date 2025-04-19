---
tags:
  - binomial_tree_model
  - black_scholes_model
  - greek_letters
  - implied_volatility
  - option_pricing
aliases:
  - Greek Letter Analysis
  - Option Risk Measures
key_concepts:
  - Binomial tree model
  - Black-Scholes-Merton model
  - Greek letters
  - Implied volatility
  - Option risk
---

# 19.3 GREEK LETTER CALCULATION  

Most traders use more sophisticated hedging procedures than those mentioned so far. These hedging procedures involve calculating measures such as delta, gamma, and vega. The measures are collectively referred to as Greek letters. They quantify different aspects of the risk in an option position. This chapter considers the properties of some of most important Greek letters.  

In order to calculate a Greek letter, it is necessary to assume an option pricing. model. Traders usually assume the Black-Scholes-Merton model (or its extensions in Chapters 17 and 18) for European options and the binomial tree model (introduced in. Chapter 13) for American options. (As has been pointed out, the latter makes the same. assumptions as Black-Scholes-Merton model.) When calculating Greek letters, traders. normally set the volatility equal to the current implied volatility. This approach, which. is sometimes referred to as using the "practitioner Black-Scholes model," is appealing.. When volatility is set equal to the implied volatility, the model gives the option price at a particular time as an exact function of the price of the underlying asset, the implied. volatility, interest rates, and (possibly) dividends. The only way the option price can change in a short time period is if one of these variables changes. A trader naturally feels confident if the risks of changes in all these variables have been adequately hedged.  

In this chapter, we first consider the calculation of Greek letters for a European option on a non-dividend-paying stock. We then present results for other European options. Chapter 21 will show how Greek letters can be calculated for American-style options..  
