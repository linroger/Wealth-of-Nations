# 8.5 RECAP AND PREVIEW

In option valuation, the Greeks are the changes in the value of an option for changes. in the inputs that determine the value of an option. They are sensitivity measures and are important in the valuation and trading of options. We examined the various Greeks known as the delta, gamma, theta, vega, and rho, and we showed how they can be calculated in the binomial model. We also presented numerical examples.

In Chapter 9, we show how the binomial model can be extended to a continuous-time. world in which the time step is extremely small and how the value ultimately converges to the Black-Scholes-Merton option value.

# QUESTIONS AND PROBLEMS

Suppose you are given the following information:. $S=48.08$ $X=50$ $r_{a}=4.0\%$ (discrete, annual compounding), one year to expiration, two time steps, $u=1.2808$ , and $d=0.7808$ . Complete the following binomial tree.

![](images/bf0f6fc76479f4222f8029a6c78318911aac2c7d9b3e138d97fb3902069a91ff.jpg)

2 Based on the results from the previous problem, compute the delta, gamma, and theta based on the standard method.
3 Based on the data from the previous two problems and the following binomial tree, compute the delta, gamma, and theta using the extended method..
4 Based on put-call parity, derive the relationship between call and put deltas, gammas, and thetas. Assume interest rates are quoted on a continuous compounding basis.
5 Verify that your results in problem 3 are consistent with the put-call parity results in problem 4.

![](images/fe23e3db6a6c1a1f916f542fffca688a0f0d8cb86001aefc16d0d6a66b4981b2.jpg)

# NOTES

1. A dealer stands ready to buy or sell options at the behest of a client. The dealer takes the opposite position of the client and lays off the risk by hedging. In essence, dealers are wholesalers or intermediaries of risk.
2. In Chapter 14, we revert to the traditional put delta with the negative sign. Thus, in this introductory material, we report put deltas as positive numbers.
3. Note that the price changes are expressed as $\boldsymbol{c}_{u}-\boldsymbol{c}$ and $c-c_{d}$ . We are taking the average absolute price changes. Thus, we need to have $c-c_{d}$ rather than $c_{d}-c$ because the latter is negative. We take the same approach for S. Further, we take the negative of the traditional put delta so it. is represented as a positive number.
4. These points will become clearer when we cover the Greeks in a continuous time world.
5. Here we note that if the down factor is not the inverse of the up factor, meaning a nonrecombining tree, then $S u d\ne S$ , and this method will not be as precise. Nonetheless, with enough time steps, Sud will often be close enough to. $S$ to ignore any such problems.
6. Vega is referred to as an option Greek as the Greek letter nu,. $\nu.$ looks similar to the letter v for volatility. Vega is not a Greek letter, as say delta, gamma, theta, and so on. Nonetheless, in the. history of options someone decided that vega sounded like a good term for the effect of volatility on an option price.
7. We should also make sure that the change in volatility and interest rate is very small, given that we are attempting to approximate a derivative.
8. Also, with this type of tree, if we need to measure gamma one period prior to expiration, we can do so. Otherwise, we could not.
9. We do not illustrate the calculations for how the option prices are obtained because this is covered in Chapter 7.
|0. Note that this price is the same current price we used in the standard method..
|1. We have not covered the Black-Scholes-Merton model yet but showing the computed values from that model gives us a preview of how the binomial model will converge to it..

# Convergence of the Binomial Model to the Black-Scholes-Merton Model

t is well known that the binomial model converges to the Black-Scholes-Merton model when the number of time periods increases to infinity and the length of each time period is infinitesimally short. This proof was provided in Cox, Ross, and Rubinstein (1979). Their proof, however, is unnecessarily long and relies on a specific case of the central limit theorem. This complication is evident on pp. 250 and 252 of their article, which refers to the fact that skewness becomes zero in the limit. Also, their results are derived only for the special case where the up and down factors are given by specific formulas they obtain that allow the distribution of the asset return to have the same parameters as the desired lognormal distribution in the limit. Effectively, their distribution converges to the lognormal in the limit. They go on to show that the binomial model then converges to the Black-Scholes-Merton model under their assumptions.1

The Cox-Ross-Rubinstein proof is elegant but far too specific. A more general proof of the convergence of the binomial to the Black-Scholes-Merton model is provided by Hsia (1983). His paper, published in The Journal of Financial Research, received virtually no attention, but it is clearly the most general overall proof. It imposes no restrictions on the choice of up and down parameters. Moreover, the proof is much shorter, easier to follow, and requires fewer cases of taking limits.2
