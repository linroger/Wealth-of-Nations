---
tags:
  - '#arbitrage_free_model'
  - '#binomial_model'
  - '#forward_rate_model'
  - '#heath_jarrow_morton_model'
  - '#hjm_model_implementation'
  - '#interest_rate_derivatives'
  - '#term_structure_modeling'
  - '#volatility_modeling'
---
# 27.5 RECAP AND PREVIEW

In this chapter, we developed the continuous time version of the multifactor HeathJarrow-Morton model. We then illustrated how the model can be implemented in a binomial world with one factor. We showed that the tree is free of arbitrage.

In Chapter 28, we shall illustrate how this tree can be used to price a wide range of interest rate derivatives.

# QUESTIONS AND PROBLEMS

1 In your own words, interpret the Heath-Jarrow-Morton forward rate model expressed as

$$
f(t,T)-f(0,T)=\intop_{0}^{t}\alpha(\nu,T)d\nu+\sum_{i=1}^{n}\intop_{0}^{t}\sigma_{i}(\nu,T)d\mathrm{W}(\nu).
$$

2 Based on the HJM forward rate stochastic process, prove the spot rate process follows:

$$
r(t)=f(0,t)+\intop_{0}^{t}\alpha(\nu,t)d\nu+\sum_{i=1}^{n}\intop_{0}^{t}\sigma_{i}(\nu,t)d W_{i}(\nu).
$$

3 Explain how the one-factor HJM model can be discretized within a binomial model such that

$$
\begin{array}{r}{f(t+1,T)^{+}=f(t,T)+\alpha(t,T)+\sigma(t,T)}\ {f(t+1,T)^{-}=f(t,T)+\alpha(t,T)-\sigma(t,T).}\end{array}
$$

4 From the HJM forward rate stochastic process, the no-arbitrage result can be expressed as

$$
d f(t,T)=\alpha(t,T)d t+\sum_{i=1}^{n}\sigma_{i}(t,T)d W_{t}(t),
$$

where

$$
\alpha(t,T)=\sum_{i=1}^{n}\sigma_{i}(t,T)\int_{t}^{T}\sigma(t,\nu)d\nu.
$$

5Within the discretized version of the forward rate stochastic process of the HJM model, compute the appropriate forward rates at time 1 based on the following inputs.

$$
\begin{array}{l}{{f(0,0)=0.020}}\ {{}}\ {{f(0,1)=0.021\mathrm{and}\sigma(0,1)=0.04}}\ {{}}\ {{f(0,0)=0.022}}\end{array}
$$

# NOTES

1. That is, given an interest rate change that is normally distributed, the original rate can eventually be driven below zero. By contrast, with proportional rate changes, the rate cannot hit or go below zero.

2. What we mean here can be expressed in simple terms. If we were just going to examine the term structure, we would pick a series of bonds whose maturities range from one to so many years. Let us use $T$ to represent the maturity of the longest maturity bond. That might not necessarily be the. longest maturity bond that exists, but it would be one likely chosen for practical reasons, such as data availability or liquidity. In some cases, we might just need to observe the shortest end of. the term structure, so $T$ would be short. Regardless, when working with the term structure, we. pick a starting point, which is always time 0, and an ending point, which is the maturity of the longest maturity bond. As we shall see here, to fit the HJM model, we shall need to have bond prices and volatilities that go just past the ending point..
3. In this chapter, all forward rates are for transactions of the shortest duration. When working with the HJM model in continuous time, the forward rates are for transactions of instantaneous. maturity, and for the discrete case, all forward rates are for one-period transactions. When we say instantaneous or one period, we, of course, mean the underlying. Thus, a forward rate like $f(0,3)$ is the rate observed at time 0 for a transaction to start at time 3 and end either instantaneously or one period later.
4. In most other cases, numerical methods such as binomial models can be used to obtain the price. Partial derivatives can then be estimated by numerical approximations.
5. Note that the volatility is not necessarily constant across the term structure or across time. In other words, volatility can change, but it cannot change independent of the level of rates. That is, volatility cannot be independently stochastic. What we mean by this is that volatility is stochastic but is unrelated to the level of rates. Some volatility structures have been proposed in which the volatility is functionally related to the level of rates. In that case, the volatility will be stochastic, but all of the uncertainty is coming from the uncertainty of the interest rate. Models with stochastically dependent volatility are permitted and can oftentimes be easily accommodated because the uncertainty is not more than that already present in the model. In the case of non-stochastic volatility, all volatilities are known, but they are allowed to change as long as the change is known. Also, in the version we present here, there is no distinction between states. That is, volatility is the same at a given time regardless of what level rates are at. In the full HJM model, volatility can also differ by states, though it still must be deterministic or dependently stochastic. As we note. shortly, our volatilities will be associated, not with rates, but with factors driving these rates.
6. For some reason, the literature has stressed the point that the drift under the equivalent martingale measure cannot be zero. HJM (1991) and Ritchken (1996) use a simple binomial tree example to show that if a drift of zero is assumed, there is an arbitrage opportunity. It is not clear why. anyone would think that the drift should be zero. From the previous formula, it should be clear that the drift cannot be zero if interest rates are stochastic..
7. As noted, the exponentially decaying volatility structure produces a number of closed-form solutions. See Jarrow and Turnbull (2000, Chapters 16 and 17) for details. In addition, Brenner and Jarrow (1993) obtain some closed-form solutions for a special case of a two-factor model. The option pricing formulas in both of these cases bear a striking resemblance to the. Black-Scholes-Merton model.
8. If we had. $T$ forward rates, this would mean we have $T$ bond prices. Either would imply the other.
9. Technically, we can go one more step to time $T$ but the only bond that would exist over the final. time period is a one-period zero-coupon bond, which was the original. $T$ -period zero-coupon bond at time 0. With one period to go, this bond would have no uncertainty. Thus, for that last period all we would have is the riskless asset. So, all we can really build is a model with $T-1$ maturity up to $T$

# Pricing Fixed-Income. Securities and Derivatives Using an Arbitrage-Free Binomial Tree

n Chapter 27, we demonstrated the Heath-Jarrow-Morton arbitrage-free model for the. evolution of the term structure. Recall that the tree is specified in terms of continuously compounded forward rates. We showed how the technique of Grant and Vora (1999,. 2006) could be used to discretize the model and develop a binomial tree, which we repeat here as Figure 28.1.

First, recall the notation, in which $f(x,y)$ is the continuously compounded forward rate at time $x$ for a one-period transaction to start at time $y.$ Thus, $f(0,0)$ is the current spot rate (0.068), $f(0,1)$ is the forward rate observed at time O for a one-period loan to start at time 1 (0.072), $f(0,2)$ is the forward rate observed at time 0 for a one-period loan to start at time 2 (0.08), and $f(0,3)$ is the forward rate observed at time O for a one-period loan to start at time 3 (0.082). The $^+$ and -- signs in the superscripts indicate the number of up and down moves that have accumulated since time O to the current state. Hence, the top number at each node is the current one-period spot rate, with the forward rates below. As an example, the rate $f(2,3)^{+-}$ rate of 0.0826 means that $8.26\%$ is the continuously compounded forward rate when the spot rate has gone up and then down, so we are at time 2, and the rate applies to a one-period transaction to start at time 3.

In this chapter, we are going to use this model to determine the prices of a very large set. of financial instruments. We will first price the simplest instruments, zero-coupon bonds.. Then we will price the following instruments: coupon bonds, options on zero-coupon. bonds, options on coupon bonds, callable bonds, FRAs, interest rate swaps, interest rate options, interest rate swaptions, and interest rate futures..
