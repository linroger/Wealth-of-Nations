---
tags:
  - back_testing
  - historical_simulation
  - model_building
  - var_estimation
  - volatility_updating
aliases:
  - Backtest
  - Historical data
  - Risk assessment
  - VaR methods
key_concepts:
  - Back testing VaR model
  - Historical simulation approach
  - Model-building approach
  - Nonlinear derivatives impact
  - VaR estimation methods
---

# 22.7 COMPARISON OF APPROACHES  

We have discussed two methods for estimating VaR: the historical simulation approach. and the model-building approach. The basic model-building approach in Sections 22.3 and 22.4 assumes that changes in the portfolio's value are linearly dependent on the. underlying market variables. This means that it is not accurate when the portfolio. contains nonlinear derivatives. Monte Carlo simulation can be used to avoid the linearity assumption, but the speed advantages of the model-building approach are.  

then lost. The model-building approach is most appropriate for portfolios consisting of long and short positions in assets without any nonlinear derivatives. Results can be produced speedily and it can be used in conjunction with volatility updating procedures such as those we will describe in the next chapter. It has the disadvantage that it assumes a multivariate normal distribution for the asset returns. (Often these returns have heavier tails than the normal distribution, as illustrated in Table 20.1.)  

The historical simulation approach has the advantage that historical data determine. the joint probability distribution of the market variables. It also avoids the need for. cash-flow mapping. The main disadvantages of historical simulation are that it is computationally slow and does not easily allow volatility updating schemes to be. used. 15  

# 22.8 BACK TESTING  

Once a model for calculating VaR has been developed, an important reality check is back testing. This involves testing how well the VaR estimates would have performed in the past. Suppose that we are calculating a 1-day $99\%$ VaR. Back testing would involve looking at how often the loss in a day exceeded the 1-day $99\%$ VaR that would have been calculated for that day. If this happened on about $1\%$ of the days, we can feel reasonably comfortable with the methodology for calculating VaR. If it happened on, say, $7\%$ of days, the methodology is suspect. Unfortunately ES is more difficult to back test than VaR.  
