# 16.5 RECAP AND PREVIEW

In this chapter, we showed how the change of probability measure in the discrete time stochastic process that we use is related to the change of probability measure in the continuous time stochastic process we use. We also show the Kolmogorov equations, which define how movements at one point in time are related to movement at a future or prior point in time.

This chapter completes Part III. In Part IV, we return to a more direct application of the Black-Scholes-Merton model. Specifically, we examine types of options other than the standard European option, and we derive the relevant pricing models under the Black-Scholes-Merton assumptions.

# QUESTIONS AND PROBLEMS

1 Assume we wish to model movements over the next calendar month,. $t=1/12$ , with a two-period model, $n=2$ periods. Propose a Wiener process with an expected value of 0 and standard deviation of $\sqrt{t}=\sqrt{1/12}$
2 Assume we wish to model movements over some generic time period, $t.$ with an $_n$ -period model. Propose a Wiener process with an expected value of 0 and standard. deviation of $\sqrt{t}$
3 Suppose we have two points in time, $s$ and $\boldsymbol{\mathscr{u}}$ . Unfortunately, we do not know which point in time is larger than the other point in time. Derive the covariance and correlation between two overlapping Brownian motions, $W_{s}$ and $\mathrm{W}_{u}$
4 Assume that the actual probability of an up move is. $\phi=60\%$ and the artificial probability of an up move is $q=50\%$ for each time step. Build a two-period binomial model of the Radon-Nikodym derivative and show that this process is a martingale under the actual probability measure but not the artificial probability measure..
5Assuming arithmetic Brownian motion with arithmetic drift with constant coefficients, derive the expected value and standard deviation.

# NOTES

1. A random walk is a stochastic process consisting of a series of independent and identically distributed random variables. A Brownian motion is a random walk, but all random walks are not Brownian motions. Technically, Brownian motions are required to be continuous. We relax this requirement in these introductory sections as we eventually make the limiting argument.
2. Now there would be three outcomes at time step 2: $+2$ with probability ${{1/}_{4}},0$ with probability $^1/_{2}$ , and $^{-2}$ with probability $1/_{4}$ . The expected value is still zero, but the variance is now $(1/4)(2-0)^{2}+(1/2)(0-0)^{2}+(1/4)(-2-0)^{2}=2$
3. To obtain the variance we would end up squaring $\Delta t$ , which would take it to zero when. $\Delta t$ is small.
4. We could also find the variance of $W_{2}$ the traditional way, by probability weighting the three. squares of the outcomes less the expected value squared.
5. Recall we follow standard notation where the subscript is simple $t$ even though it is not observed until $t+\Delta t$ because we eventually focus on the limiting result.
6. The formal proof of this result is a variation of the DeMoivre-LaPlace limit theorem, which proves that a binomial distribution converges to a normal distribution in the limit..
7. The covariance is actually the product of the correlation and the two standard deviations of the es, which are both 1.0.
8. The term velocity refers to the speed of something. Hence, a derivative such as $d\mathbb{W}_{t}/d t$ would refer to the rate at which $\mathbb{W}_{t}$ changes with time, which, of course, is the speed.
9. Consider, however, that blackjack dealers frequently change decks to alter the probabilities.
10. It would be convenient if the probabilities under measure $P$ were $p$ and $1-p$ , or the value of a. put.
11. At time 0, there is only one state, so we do not need to index it by state..
12. It can be proven by using the moment-generating function that in the limit these values produce the desired periodic mean, $\mu$ , and volatility, $\sigma$
13. That this density solves the differential equation can be verified by taking the partial derivatives with respect to $t$ and $_x$ and substituting back into the differential equation.

# Extensions and Generalizations of Derivative Pricing

# Applying Linear Homogeneity to Option Pricing.

n this chapter, we shall illustrate how the mathematical principle of linear homogeneity and its associated Euler rule can be used in pricing options. Our objective is to illustrate the pricing of exchange options and forward start options. We shall, however, illustrate how the Black-Scholes-Merton model can be priced using this procedure. We then show how the exchange option model is a more general model than Black-Scholes-Merton, which is but a special case of an exchange option. The analysis provided here relies on the concepts of homogeneous functions, linear homogeneity, and Euler's rule. But first let us introduce exchange options.
