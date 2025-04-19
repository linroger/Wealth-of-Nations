---
tags:
  - monte_carlo_simulation
  - partial_simulation
  - portfolio_valuation
  - probability_distribution
  - var_calculation
aliases:
  - Monte Carlo
  - Partial Simulation
  - VaR
key_concepts:
  - Build probability distribution
  - Calculate 1-day VaR
  - Monte Carlo simulation
  - Multivariate normal distribution
  - Revalue the portfolio
---

# 22.6 MONTE CARLO SIMULATION  

As an alternative to the procedure described so far, the model-building approach can be implemented using Monte Carlo simulation to generate the probability distribution for $\Delta P$ . Suppose we wish to calculate a 1-day VaR for a portfolio. The procedure is as follows:  

1. Value the portfolio today in the usual way using the current values of market variables.   
2. Sample once from the multivariate normal probability distribution of the $\Delta x_{i}$ 11   
3. Use the values of the $\Delta x_{i}$ that are sampled to determine the value of each market variable at the end of one day.   
4. Revalue the portfolio at the end of the day in the usual way.   
5. Subtract the value calculated in Step 1 from the value in Step 4 to determine a sample $\Delta P$   
6. Repeat Steps 2 to 5 many times to build up a probability distribution for $\Delta P$  

The $\mathrm{VaR}$ is calculated as the appropriate percentile of the probability distribution of $\Delta P$ Suppose, for example, that we calculate 5,000 different sample values of. $\Delta P$ in the way just described. The 1-day $99\%$ VaR is the value of $\Delta P$ for the $50\mathrm{th}$ worst outcome; the 1-day VaR $95\%$ is the value of $\Delta P$ for the $250\mathrm{th}$ worst outcome; and so on.12 The $N\cdot$ day $\mathrm{VaR}$ is usually assumed to be the 1-day VaR multiplied by. $\sqrt{N}$ 13  

The drawback of Monte Carlo simulation is that it tends to be slow because a. company's complete portfolio (which might consist of hundreds of thousands of. different instruments) has to be revalued many times.14 One way of speeding things up is to assume that equation (22.8) describes the relationship between $\Delta P$ and the $\Delta x_{i}$ We can then jump straight from Step 2 to Step 5 in the Monte Carlo simulation and avoid the need for a complete revaluation of the portfolio. This is sometimes referred to as the partial simulation approach. A similar approach is sometimes used when implementing historical simulation.  
