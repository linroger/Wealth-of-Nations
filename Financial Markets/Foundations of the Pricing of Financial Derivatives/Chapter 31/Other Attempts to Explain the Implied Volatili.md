---
tags:
  - black_scholes_merton
  - implied_volatility
  - option_pricing
  - stochastic_volatility
  - volatility_smile
aliases:
  - IV smile
  - Volatility Skew
key_concepts:
  - Algorithmic choices
  - Asset price jumps
  - Deep OTM put options
  - Liquidity explanation
  - Stochastic volatility
---

# 31.5 OTHER ATTEMPTS TO EXPLAIN THE IMPLIED VOLATILITY SMILE

When the volatility smile was first observed, some researchers believed that the explanation was liquidity. The true "smile" appearance meant that deep out-of-the-money put options. and deep in-the-money call options had the highest implied volatilities. These options have low liquidity; hence, it was argued that the prices observed for these options of low liquidity reflected the thinness of their markets. But this explanation would suggest that highly liquid options--typically those trading nearly at-the-money--would have the same implied volatilities. In fact, they do not and never did. Moreover, when the smile turned into a skew, the moneyness argument fell by the wayside. In addition, liquidity would not explain. the implied volatilities of deep in-the-money put options and deep out-of-the-money call. options, which also have low liquidity, and yet have high implied volatilities..

Other researchers believe that the smile reflects stochastic volatility.11 Volatility is. surely not constant as assumed in the Black-Scholes-Merton model. If volatility is stochas-. tic, researchers argue that the smile reflects the failure of the Black-Scholes-Merton model to capture the random nature of volatility. Others argue that the Black-Scholes-Merton. model, which assumes that asset prices fluctuate in a smooth and continuous manner, fails. to capture the true nature of asset price movements, which are observed to have discrete jumps.12

These arguments about stochastic volatility and jumps have a great deal of appeal because they in some sense preserve many of the essential features of the Black-Scholes-Merton model. These arguments do not require that the model motivate the holding of options and the preference for some investors for certain options over others. And if these models were used, the smile would presumably go away, which it does not. Unfortunately, once these looser assumptions are introduced, the mathematical tractability of the model is lost, and the process of pricing an option becomes one of making other strong assumptions or imposing severe computational demands.13 It is fair to say that mathematicians have devoted many hours of human and machine time to researching the smile with little if any regard to the reasons why the smile exists.14

Finally, it should be noted that there is a portion of the volatility smile that is com-. pletely artificial and is driven by the algorithmic and computational choices made by. researchers and practitioners. That is, choosing the algorithm for convergence and the criterion that define whether convergence has occurred can lead to a smile-like effect.15.
