---
tags:
  - bond_option
  - callable_bond
  - interest_rates
  - pricing_problems
  - time_step
aliases:
  - Reducing Time Step
  - Time Step Reduction
key_concepts:
  - Computational concerns and step size
  - Pricing contingent claims accuracy
  - Realistic interest rate distributions
  - Smaller time step benefits
  - Time step and cash flows
---

# 7.8 REDUCING THE TIME STEP  

This chapter has so far assumed that the time elapsed between dates of the tree is six months. The methodology outlined, however, adapts easily to any time step of $\Delta t$ years. For monthly time steps, for example, $\Delta t=1/12$ or .0833, and one-month rather than six-month interest rates appear on the tree. Furthermore, discounting is done over the appropriate time interval. If the rate of term $\Delta t$ is $r$ , then discounting means dividing by $1+r\Delta t$ . In the case of monthly time steps, discounting with a one-month rate of $2\%$ means dividing by $1+0.02/12$  

In practice there are two reasons to choose time steps smaller than six. months. First, a security or portfolio of securities rarely makes all of its pay-. ments in even six-month intervals from the starting date. Reducing the time. step to a month, a week, or even a day can ensure that all cash flows are sufficiently close in time to some date in the tree. Second, assuming that the. six-month rate can take on only two values in six months, three values in one year, and so on, produces a tree that is too coarse for many practical. pricing problems. Reducing the step size can fill the tree with enough rates to price contingent claims with sufficient accuracy.  

While smaller time steps generate more realistic interest rate distributions, they require that more attention be paid to numerical issues, and they may make computations too slow for their intended uses. The choice of step size ultimately depends, therefore, on the problem at hand. When pricing a 30-year callable bond, for example, a model with weekly or even monthly time steps may provide a realistic enough interest rate distribution to generate reliable prices. By contrast, pricing a one-month bond option with any precision would require a much smaller time step. While the trees in this chapter assume that the step size is the same throughout the tree, this need not be the case. Sophisticated implementations of trees allow step size to vary across dates in order to achieve a balance between realism and computational concerns.  
