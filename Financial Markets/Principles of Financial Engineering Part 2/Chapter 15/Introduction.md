---
tags:
  - option_strategies
  - payoff_functions
  - variance_swaps
  - volatility_swaps
  - volatility_trades
aliases:
  - Introduction to Volatility
  - Pure Volatility Instruments
key_concepts:
  - Classical option strategy drawbacks
  - Variance and volatility swaps
  - Variance vs. volatility
  - Volatility risk for practitioners
  - Volatility trades, instruments
---

# 15.1 INTRODUCTION  

Liquid instruments that involve pure volatility trades are potentially very useful for market participants who have natural exposure to various volatilities in their balance sheet or trading book. The classical option strategies discussed in Chapter 11 have serious drawbacks in this respect. When a trader takes a position or hedges a risk, he or she expects that the random movements of the underlying would have a known effect on the position. The underlying may be random, but the payoff function of a well-defined contract or a position has to be known. Payoff functions of most classical volatility strategies are not invariant to underlying risks, and most volatility instruments turn out to be imperfect tools for isolating this risk. Even when traders' anticipations come true, the trader may realize that the underlying volatility payoff functions have changed due to movements in other variables. Hence, classical volatility strategies cannot provide satisfactory hedges for volatility exposures. The reason for this and possible solutions are the topics of this chapter..  

Traditional volatility trades used to involve buying and selling portfolios of call and put options, straddles or strangles, and then possibly delta-hedging these positions. But such volatility positions were not pure and this led to a search for volatility tools whose payoff function would depend on the volatility risk only. This chapter examines two of the pure volatility instruments that were developed-variance and volatility swaps. Volatility swaps are forward contracts on future realized (stock) volatility. Variance contracts are similar contracts on variance, the square of future volatility. Variance and volatility swaps are interesting for at least two reasons: First, volatility is an important risk for market practitioners, and ways of hedging and pricing such risks have to be understood. Second, the discussion of volatility swaps constitutes a good example of the basic principles that need to be followed when devising new instruments.  

The chapter uses variance swaps instead of volatility swaps to conduct the discussion. Although markets in general use the term volatility, it is more appropriate to think in terms of variance, the. square of volatility. Variance is the second centered moment of a random variable, and it falls more naturally from the formulas used in this chapter. For example, volatility (i.e., standard deviation) instruments require convexity adjustments, whereas variance instruments in general do not. Thus, when we talk about vega, for example, we refer to variance vega. This is the sensitivity of the option's price with respect to $\sigma^{2}$ not $\sigma$ . In fact, in the heuristic discussion in this chapter, at times the term volatility and variance are used interchangeably.  
