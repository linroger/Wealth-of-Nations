---
tags:
  - '#arbitrage_free'
  - '#binomial_tree'
  - '#discrete_time'
  - '#drift_adjustment_term'
  - '#drift_restriction'
  - '#forward_rates'
  - '#hjm_model'
  - '#local_expectations_hypothesis'
  - '#wiener_process'
---
# 27.2 DISCRETIZING THE HJM MODEL

With the exception of a few restrictive volatility structures, the HJM model does not pro-. duce closed-form solutions for the prices and risk measures of various instruments.7 Hence, numerical methods are normally required. Here we will look at discretizing the HJM model for use in a binomial tree. In doing so, we shall gain a deeper understanding of the model. and especially the drift restriction that prevents arbitrage. At this level, we shall focus exclusively on the one-factor version. Hence, we are given the stochastic process for the forward rate, Equation (27.9). Because we shall use only a one-factor model, Equation (27.4) becomes

$$
d f(t,T)=\alpha(t,T)d t+\sigma(t,T)d W(t),
$$

where the arbitrage-free drift restriction, Equation (27.8), becomes

$$
\alpha(t,T)=\sigma(t,T)\int_{t}^{T}\sigma(t,\nu)d\nu.
$$

To generate a binomial version of the model, we must first consider the information with which we have to work. We shall need the prices of a set of bonds maturing at discrete time points,. $1,2,3,...,T-1,T.$ If $T$ is the longest maturity available, that would mean we have. $T$ forward rates available, $f(0,0),f(0,1),\ldots,f(0,T-1)$ 8 We would then need volatilities for maturities of $1,2,...,T-1$ . This set of information will be sufficient to build a binomial tree of $T-1$ time steps.' First, let us write the stochastic process for the forward rates in discrete form as

$$
\Delta f(t,T)=\alpha(t,T)\Delta t+\sigma(t,T)\Delta W(t).
$$

To convert a Wiener process to a binomial, we simply express the random variable as a binary variable with a value of. $+1$ or $-1$ at each time step and assume martingale probabilities of $^1/_{2}$ , as we did in Chapter 16. We assume each time step has a defined length of one unit. Hence, the stochastic process becomes.

$$
\Delta f(t,T)=\alpha(t,T)\pm\sigma(t,T).
$$

Thus, at a given time, for a given forward rate $f(t,T)$ , we move one step ahead to the next.
time in the following manner:.

$$
\begin{array}{r}{f(t+1,T)^{+}=f(t,T)+\alpha(t,T)+\sigma(t,T)}\ {f(t+1,T)^{-}=f(t,T)+\alpha(t,T)-\sigma(t,T).}\end{array}
$$

That is, we add the drift and add or subtract the volatility. Recall that to prevent arbitrage. in a term structure, the local expectations hypothesis (LEH) must hold. The LEH says that the expected return on any financial instrument over the shortest time period must be the riskless rate, where expectations are taken using a special martingale probability measure. that appeals to the local expectations hypothesis. That is,.

$$
B(t,T)=B(t,t+b)E^{Q}[B(t+b,T)],
$$

where the superscript $\mathcal{Q}$ means that expectations are taken using the martingale proba-. bilities. The first term, $B(t,t+b)$ , is the price of the bond with the shortest maturity. In. multiplying by it, we are discounting at the riskless rate. The second term, $E^{Q}[{B}(t+b,T)],$ is the expectation of the bond price at time $t+b$ . By discounting this expectation at the riskless rate, we obtain the current bond price.

Writing Equation (27.19) as

$$
\frac{B(t,T)}{B(t,t+b)}=E^{Q}[B(t+b,T)],
$$

and using Equation (27.1), which states that the bond price can be found by discounting at the sequence of forward rates, we substitute and obtain.

$$
\frac{B(t,T)}{B(t,t+b)}=e^{-\intop f(t,\nu)d\nu}e^{\intop f(t,\nu)d\nu}=e^{-\intop f(t,\nu)d\nu}.
$$

This result must equal the expectation in Equation (27.20), which can be found by evaluating the following expression based on Equation (27.18):

$$
e^{-\int_{t+b}^{T}f(t,\nu)d\nu}=\left(\frac{1}{2}\right)e^{-\int_{t+b}^{T}[f(t,\nu)+\alpha(t,\nu)+\sigma(t,\nu)]d\nu}+\left(\frac{1}{2}\right)e^{-\int_{t+b}^{T}[f(t,\nu)+\alpha(t,\nu)-\sigma(t,\nu)]d\nu}.
$$

This expectation reflects the binomial probabilities of $^1/_{2}$ and the integrals represent the discounting of the sequence of forward rates. In other words, the two terms that are multiplied by $1/_{2}$ are the next two possible bond prices, which themselves are obtained by discounting at the sequence of forward rates over the remaining lives of the bonds. After some additional math, we obtain

$$
\alpha(t,T)=\sigma(t,T)\int_{t}^{T}\sigma(t,\nu)d\nu,
$$

which is the result we obtained as Equation (27.15).

To actually work with the HJM model in discrete time, however, requires that we obtain a discretized version of the drift restriction. HJM (1991) provide a version of this result, which they obtain in a clever way. Using a binomial model, they get a result that they extend to continuous time by letting the time step approach zero. They then use it to show the correct drift in a simple binomial example. Ritchken (1996: 579-580) notes this result but this is not correct for the binomial case. Starting with a binomial model, obtaining a result and taking the continuous time limit to that result is certainly correct. But the discrete time version of this continuous time limit is not correct, as shown by Grant and Vora (1999, 2006), who go on to derive the correct discrete time formula. They start with a variation of the expression we used:

$$
B(t,T)=E^{Q}[B(t+b,T)]B(t,t+b).
$$

They then make use of the fact that a Wiener process is a normal distribution, so the interaction of the volatilities has convenient properties, and the correlation between all. forward rates in a one-factor model is 1.0. After considerable algebra, they find a simple expression for the drift,.

$$
\alpha(t,T)=\left(\frac{1}{2}\right)\Bigg[\sigma^{2}(t,T)+2\sigma(t,T)\sum_{j=t+1}^{T-1}\sigma(t,j)\Bigg].
$$

This value can be computed very easily from the covariance matrix of forward rate volatilities, which we shall demonstrate in a numerical example below. Grant and Vora refer to this term as the drift adjustment term though there is really no reason to call it anything other than the drift. Another good treatment of how this procedure unfolds is in Jarrow and Chatterjea (2013).
