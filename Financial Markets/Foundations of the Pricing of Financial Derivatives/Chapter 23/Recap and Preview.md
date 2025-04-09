# 23.4 RECAP AND PREVIEW

In this chapter, we examined the method of Monte Carlo simulation, which can be used to price options by generating a large sample of outcomes for the underlying, calculating

the corresponding option payoff, averaging that payoff, and discounting by the risk-free rate. We illustrated it for the standard Black-Scholes-Merton case, but the benefit of Monte Carlo lies in its ability to handle more complex cases.

In Chapter 24, we look at one more numerical procedure, the finite difference method, which solves the partial differential equation in a numerical manner.

# QUESTIONS AND PROBLEMS

1Let $x_{1}$ and $x_{2}$ denote two independent standard normal random variables with mean
0 and variance 1. Explain how to generate two dependent standard normal random variables. Prove your approach works.
2 Explain how one transforms correlated standard normal random variables to correlated normal random variable with nonzero means and variance not equal to one.
3 Identify and discuss two ways to reduce the standard error of the estimate when pricing options with Monte Carlo simulation.
4 The following two figures were generated with Monte Carlo simulation. One figure. is based on geometric Brownian motion (GBM) and one figure is based on arithmetic Brownian motion (ABM). Identify each figure and defend your answer.

![](01f3f1f1a00a48d92bd75298ae981c59e9c6bc1b4b9690c00f3598d7b876c566.jpg)

![](fdc118fc66699ed9a6d5aa78fbe0b8b871c3d13541e806262f6e0d1cb3e3ddd9.jpg)

5 The option price obtained from a Monte Carlo simulation is a sample average. Distinguish between the standard deviation of a sample and the standard deviation of the sample mean estimate and explain the implication of this point for Monte Carlo simulation.

6[Contributed by Jeremy Vasseur] Suppose you wish to use the antithetic variate method to increase the number of observations in a Monte Carlo simulation. You are not, however, using a normal distribution but rather an asymmetric distribution to generate the. random values. Explain whether you can use the antithetic variate method to conduct this simulation.

# NOTES

1. The seminal work on the use of Monte Carlo simulation in option pricing is Boyle (1977).

2. See, for example, Chapter 12, Section 4. Also, a dividend yield could easily be incorporated

3. This approximation is based on the fact that the distribution of the sum of 12 uniformly dis-. tributed random numbers between 0 and 1 will have a mean of 6.0 and a standard deviation of 1. By subtracting 6.0, we shift the mean to zero without changing the standard deviation. What. we obtain is technically not normally distributed, but it is symmetric, with mean zero and standard deviation of 1.0, which are three properties associated with the normal distribution. The. procedure is widely accepted as a quick and reasonable approximation but might not pass the most demanding tests for normality. However, many other random number generators would also not pass the most demanding tests either. The Excel nested function normsinv(rand()) will also generate a standard normal directly from the uniform random number..

4. Although this is a point from the most elementary principles of statistics, it is important to distinguish between the standard deviation of a sample and the standard deviation of the sample mean estimate. The latter is the former divided by the square root of the sample size. Hence, the. sample mean is much less volatile than the sample values themselves..

5. Although we covered this point in Chapter 4, it is worth repeating that two variables that are independent will have zero correlation, but two variables that have zero correlation can be highly dependent. As an example, the relationship $y=\sin(x)$ expresses the familiar sine function, a repeating wave in which. $y$ goes up and then down alternatively as $x$ increases. The variable. $y$ is completely dependent on $_x$ , but the relationship is nonlinear. A graph shows a very obvious curve, not a straight line. Calculation of the correlation between $y$ and $_x$ would result in a value. of approximately zero, even though $y$ and $_x$ are highly related, of course, in a nonlinear manner.

# Finite Difference Methods

s we have learned to this point, under the appropriate assumptions, the price of a call $c.$

$$
\frac{\partial c}{\partial S_{t}}r_{c}S_{t}+\frac{\partial c}{\partial t}+\frac{1}{2}\frac{\partial^{2}c}{\partial S_{t}^{2}}S_{t}^{2}\sigma^{2}=r_{c}c_{t}.
$$

For standard European options and certain other options, a closed form solution is possible. In the case of European options, the boundary condition is $c_{T}=\operatorname*{max}(0,S_{T}-X)$ where $S_{T}$ is the asset price at expiration and $X$ is the exercise price in the well-known Black-Scholes-Merton model. In some cases, however, no closed-form solution can be derived. Although the binomial model can often be used, the finite difference method is another alternative. It essentially amounts to a trinomial and in some respects is more. efficient, because it allows for more possible outcomes. The approach taken here is the. log transform method as suggested by Brennan and Schwartz (1978), which is known to provide a stable solution.1
