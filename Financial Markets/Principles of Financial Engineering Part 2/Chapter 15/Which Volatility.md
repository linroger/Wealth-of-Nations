# 15.8 WHICH VOLATILITY?  

This chapter dealt with four notions of volatility. These must be summarized and distinguished clearly before we move on to discussion of the volatility smile in the next chapter.  

When market professionals use the term "volatility," chances are they refer to Black--Schole's. implied volatility. Otherwise, they will use terms such as realized or historical volatility. Local volatility and variance swap volatility are also part of the jargon. Finally, cap-floor volatility and. swaption volatility are standard terms in financial markets..  

As explained in Chapter 9, implied volatility is simply the value of. $\sigma$ that one would plug into. the Black-Scholes formula to obtain the fair market value of a plain vanilla option as observed. in the markets. For this reason, it is more correct to call it Black-Scholes implied vol or Black volatility in the case of interest rate derivatives. It is quite conceivable for a professional to use a. different formula to price options, and the volatility implied by this formula would naturally be different. The term implied volatility is, thus, a formula-dependent variable..  

We can attach the following definitions to the term "volatility."  

First, there is the class of realized volatilities. This is closest to what is contained in statistics courses. In this case, there is an observed or to-be-observed data set, a "sample," $\{x_{1},...x_{n}\}$ which can be regarded as a realization of a possibly vector-stochastic process,. $x_{t},$ defined under some real-world probability. $P$ . The process $x_{t}$ has a second moment  

$$
\sigma_{t}=\sqrt{E_{t}^{P}[(x_{t}-E_{t}^{P}[x_{t}])^{2}]}
$$  

We can devise an estimator to estimate this $\sigma_{t}$ For example, we can let.  

$$
\hat{\sigma}_{t}=\sqrt{\frac{\sum_{i=0}^{m}{(x_{t-i}-\overline{{x}}_{t}^{m})}^{2}}{m}}
$$  

where $\overline{{x}}_{t}^{m}$ is the $m$ -period sample mean:  

$$
\overline{{x}}_{t}^{m}=\frac{\sum_{i=0}^{m}x_{t-i}}{m}
$$  

Such volatilities measure the actual real-world fluctuations in asset prices or risk factors. One example of the use of this volatility concept was shown in this chapter. The. $\sigma_{t}^{2}$ defined earlier represented the floating leg of the variance swap discussed here..  

The next class is implied volatility.14 There is an observed market price. The market practitione1 has a pricing formula (e.g., Black--Scholes) or procedure (e.g., implied trees) for this price.. Then, implied volatility is that "volatility" number, or series of numbers, which must be plugged into the formula in order to recover the fair market price. Thus, let $F(S_{t},t,r,\sigma_{t},T)$ be the Black-Scholes price for a European option written on the underlying $S_{t},$ with interest rates $r$ and expiration $T.$ At time $t$ $\sigma_{t}$ represents the implied volatility if we solve the following equation (nonlinearly) for $\sigma_{t}$  

$$
F(S_{t},t,r,\sigma_{t},T)=\mathrm{observedprice}
$$  

This implied volatility may differ from the realized volatility significantly, since it incorporates any adjustments that the trader feels he or she should make to expected realized volatility. Implied volatility may be systematically different than realized volatility if volatility is stochastic and if a risk premium needs to be added to volatility quotes. Violations of Black-Scholes assumptions may also cause such a divergence.  

Local volatility is used to represent the function $\sigma(.)$ in a stochastic differential equation:.  

$$
\mathrm{d}S(t)=\mu(S,t)\mathrm{d}t+\sigma(S,t)S_{t}\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

However, local volatility has a more specific meaning. Suppose options on. $S_{t}$ trade in all strikes, $K$ and expirations $T$ and that the associated arbitrage-free prices,. $\{C(S_{t},t,K,T)\}$ , are observed for all $K,T.$ Then the function $\boldsymbol{\sigma}(\boldsymbol{S}_{t},t)$ is the local volatility, if the corresponding. SDE successfully replicates all these observed prices either through a Monte Carlo or PDE pricing method.  

In other words, local volatility is a concept associated with calibration exercises. It can be. regarded as a generalization of Black-Scholes implied volatility. The implied volatility replicates a single observed price through the Black-Scholes formula. The local volatility, on the other hand, replicates an entire surface of options indexed by. $K$ and $T$ , through a pricing method. As a result, we get a volatility surface indexed by $K$ and $T$ instead of a single number as in the case of BlackScholes implied volatility. Finally, in this chapter we encountered the variance swap volatility. This referred to the expectation of the average future squared deviations. But, because the expectation used the risk-neutral measure, it is different from real-world volatility.  

Discussions of the volatility smile relate to these volatility notions. The implied volatility is obviously of interest to most traders but it cannot exist independently of realized volatility. It is natural to expect a close relationship between the two concepts.15 Also, as volatility trading develops, more and more instruments are written that use the realized volatility as some kind of underlying risk factor for creating new products. The variance swap was only one example.  
