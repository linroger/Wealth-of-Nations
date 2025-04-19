---
tags:
  - convexity
  - delta_neutral
  - interest_rate_derivatives
  - option_pricing
  - volatility
aliases:
  - Introduction to Volatility
  - Trading Volatility
key_concepts:
  - Arbitrage pricing theory
  - Convexity and yield volatility
  - Delta-neutral portfolios
  - Implied volatility calculation
  - Trading volatility
---

# 10.1 INTRODUCTION  

How can anyone trade volatility? Stocks, yes. Bonds, yes. But volatility is not even an asset. Several difficulties are associated with defining precisely what volatility is. For example, from a technical point of view, should we define volatility in terms of the estimate of the conditional standard deviation of an asset price $S_{t}^{\mathbf{\alpha}}$  

$$
\sqrt{E_{t}[S_{t}-E_{t}[S_{t}]]^{2}}
$$  

Or should we define it as the average absolute deviation?  

$$
E_{t}[|S_{t}-E_{t}[S_{t}]|]
$$  

There is no clear answer, and these two definitions of statistical volatility will yield different numerical values. Leaving statistical definitions of volatility aside, there are many instances where traders quote, directly, the volatility instead of the dollar value of an instrument. For example, interest rate derivatives markets quote cap-floor and swaption volatilities.' Equity options provide implied volatility. Implied volatility is calculated by taking the market price of an option and backing out the implied volatility that results in the market price given a particular option pricing model and other input parameters. Traders and market makers trade the quoted volatility. Hence, there must be some way of isolating and pricing what these traders call volatility in their respective markets.  

We started seeing how this can be done in Chapter 9. Options became more valuable when. "volatility" increased, everything else being the same. Chapter 9 showed how these strategies can quantify and measure the "volatility" of an asset in monetary terms. This was done by forming delta-neutral portfolios, using assets with different degrees of convexity. In this chapter, we develop. this idea further, apply it to instruments other than options, and obtain some generalizations. The plan for this chapter is as follows.  

First, we show how convexity of a long bond relates to yield volatility. The higher the volatility of the associated yield, the higher the benefit from holding the bond. We will discuss the mechanics of valuing this convexity. Then, we compare these mechanics with option-related convexity trades. We see some close similarities and some differences. At the end, we generalize the results to any instrument with different convexity characteristics. The discussion associated with volatility trading itself has to wait until Chapter 15, since it requires an elementary treatment of arbitrage pricing theory.  
