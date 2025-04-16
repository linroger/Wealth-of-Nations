---
tags:
  - '#american_style_derivatives'
  - '#asian_options'
  - '#average_price_call_option'
  - '#binomial_tree_methods'
  - '#european_style_derivatives'
  - '#interpolation'
  - '#lookback_options'
  - '#monte_carlo_simulation'
  - '#path_dependent_derivatives'
---
# 27.5 PATH-DEPENDENT DERIVATIVES  

A path-dependent derivative (or history-dependent derivative) is a derivative where the. payoff depends on the path followed by the price of the underlying asset, not just its final value. Asian options and lookback options are examples of path-dependent derivatives. As explained in Chapter 26, the payoff from an Asian option depends on. the average price of the underlying asset; the payoff from a lookback option depends on. its maximum or minimum price. One approach to valuing path-dependent options when analytic results are not available is Monte Carlo simulation, as discussed in Chapter 21. A sample value of the derivative can be calculated by sampling a random. path for the underlying asset in a risk-neutral world, calculating the payoff, and. discounting the payoff at the risk-free interest rate. An estimate of the value of the. derivative is found by obtaining many sample values of the derivative in this way and. calculating their mean.  

The main problem with Monte Carlo simulation is that the computation time necessary to achieve the required level of accuracy can be unacceptably high. Also, American-style path-dependent derivatives (i.e., path-dependent derivatives where one side has exercise opportunities or other decisions to make) cannot easily be handled. In this section, we show how the binomial tree methods presented in Chapter 21 can be extended to cope with some path-dependent derivatives.23 The procedure can handle American-style path-dependent derivatives and is computationally more efficient than Monte Carlo simulation for European-style path-dependent derivatives.  

For the procedure to work, two conditions must be satisfied:  

1. The payoff from the derivative must depend on a single function, $F$ , of the path followed by the underlying asset.   
2. It must be possible to calculate the value of $F$ at time $\tau+\Delta t$ from the value of. $F$ at time $\tau$ and the value of the underlying asset at time $\tau+\Delta t$  

First we construct a tree for the underlying asset's price in the usual way. The next step is to work forward through the tree establishing the maximum and minimum. values of the path function at each node. Because the value of the path function at. time $\tau+\Delta t$ depends only on the value of the path function at time. $\tau$ and the value of the underlying variable at time $\tau+\Delta t$ , the maximum and minimum values of the path. function for the nodes at time $\tau+\Delta t$ can be calculated in a straightforward way from those for the nodes at time $\tau$ The second stage is to choose representative values of the. path function at each node. There are a number of approaches. A simple rule is to choose the representative values as the maximum value, the minimum value, and a. number of other values that are equally spaced between the maximum and the. minimum. As we roll back through the tree, we value the derivative for each of the. representative values of the path function. When the value of the derivative is needed for other values of the path function, it is calculated by interpolation..  

To illustrate the nature of the calculation, consider the problem of valuing the average price call option in Example 26.3 of Section 26.13 when the payoff depends on the arithmetic average stock price. The initial stock price is 50, the strike price is 50, the risk-free interest rate is. $10\%$ , the stock price volatility is. $40\%$ , and the time to maturity is 1 year. For 20 time steps, the binomial tree parameters are. $\Delta t=0.05$ $u=1.0936$ $d=0.9144$ $p=0.5056$ , and $1-p=0.4944$ . The path function is the arithmetic average of the stock price..  

Figure 27.3 shows the calculations that are carried out in one small part of the tree. Node $\boldsymbol{\mathrm X}$ is the central node at time 0.2 year (at the end of the fourth time step). Nodes Y and $Z$ are the two nodes at time 0.25 year that are reachable from node X. The stock. price at node X is 50. Forward induction shows that the maximum average stock price. that is achievable in reaching node $\boldsymbol{\mathrm X}$ is 53.83. The minimum is 46.65. (The initial and final stock prices are included when calculating the average.) From node X, the tree. branches to one of the two nodes Y and Z. At node Y, the stock price is 54.68 and the bounds for the average are 47.99 and 57.39. At node Z, the stock price is 45.72 and the. bounds for the average stock price are 43.88 and 52.48.  

Suppose that the representative values of the average are chosen to be four equally.   
spaced values at each node. This means that, at node X, averages of 46.65, 49.04, 51.44,.   
and 53.83 are considered; at node Y, averages 47.99, 51.12, 54.26, and 57.39 are.   
considered; and at node Z, averages 43.88, 46.75, 49.61, and 52.48 are considered..   
Assume that backward induction has already been used to calculate the value of the option for each of the alternative values of the average at nodes Y and Z. Values are.  

![](images/c5082aacf0341bf6b6a721928682595e09342f53055a27b645841c2602bb41b3.jpg)  
Figure 27.3 Part of tree for valuing option on the arithmetic average.  

shown in Figure 27.3 (e.g., at node Y when the average is 51.12, the value of the option is 8.101).  

Consider the calculations at node $\boldsymbol{\mathrm X}$ for the case where the average is 51.44. If the stock price moves up to node Y, the new average will be  

$$
{\frac{5\times51.44+54.68}{6}}=51.98
$$  

The value of the derivative at node. $\mathrm{Y}$ for this average can be found by interpolating. between the values when the average is 51.12 and when it is 54.26. It is  

$$
\frac{(51.98-51.12)\times8.635+(54.26-51.98)\times8.101}{54.26-51.12}=8.247
$$  

Similarly, if the stock price moves down to node $Z$ , the new average will be.  

$$
{\frac{5\times51.44+45.72}{6}}=50.49
$$  

and by interpolation the value of the derivative is 4.182.  

The value of the derivative at node $\boldsymbol{\mathrm X}$ when the average is 51.44 is, therefore,  

$$
(0.5056\times8.247+0.4944\times4.182)e^{-0.1\times0.05}=6.206
$$  

The other values at node. $\boldsymbol{\mathrm X}$ are calculated similarly. Once the values at all nodes at.   
time 0.2 year have been calculated, the nodes at time 0.15 year can be considered.  

The value given by the full tree for the option at time zero is 7.17. As the number of time steps and the number of averages considered at each node is increased, the value of the option converges to the correct answer. With 60 time steps and 100 averages at each node, the value of the option is 5.58. The analytic approximation for the value of the option, as calculated in Example 26.3, with continuous averaging is 5.62.  

A key advantage of the method described here is that it can handle American. options. The calculations are as we have described them except that we test for early exercise at each node for each of the alternative values of the path function at the node. (In practice, the early exercise decision is liable to depend on both the value of the path function and the value of the underlying asset.) Consider the American version of the average price call considered here. The value calculated using the 20-step. tree and four averages at each node is 7.77; with 60 time steps and 100 averages, the value is 6.17.  

The approach just described can be used in a range of different situations. The two. conditions that must be satisfied were listed at the beginning of this section. Efficiency is improved somewhat if quadratic rather than linear interpolation is used at each node.  
