---
tags:
  - black_scholes_merton_model
  - capital_asset_pricing_model
  - implied_volatility
  - option_pricing
  - sharpe_ratio
aliases:
  - Black-Scholes
  - CAPM
  - Preview
  - Recap
key_concepts:
  - European call elasticity
  - Sharpe ratio of stock
  - certainty equivalent version
  - implied volatility
  - option pricing consistency
---

# 30.7 RECAP AND PREVIEW

We learned in this chapter that option pricing is consistent with capital asset pricing. That is, the price obtained from the Black-Scholes-Merton model is consistent with the expected return from the CAPM. But even if the CAPM does not hold, the expected return on the option can be related to the expected return on the asset through the risk-free rate, the risk premium on the asset, and the risk of the option relative to the asset. Unless the option is incorrectly priced relative to the asset, the performance of the option as measured by its Sharpe ratio is no different from the performance of the asset. In short, option pricing is completely consistent with asset pricing.

In Chapter 31, we look at the concept of implied volatility, which is the volatility of the. underlying that is implied by the price of an option. Implied volatility plays an extremely. important role, not only in helping us to understand option pricing but also in helping us to see what opinions investors have about the level of risk..

# QUESTIONS AND PROBLEMS

1 Explain why the following expression is known as the certainty equivalent version of the CAPM:

$$
S=\frac{E\big(S^{\prime}\big)-\lambda\mathrm{cov}\big(S^{\prime},R_{m}\big)}{1+r},
$$

where

$$
\lambda=\frac{E\left(R_{m}\right)-r}{{\sigma_{m}}^{2}}.
$$

2 "The elasticity of a standard European call,. $(\partial c/\partial S)(S/c)$ , is at least equal to 1.". Evaluate and explain whether this statement is true or false.

3 Prove that within the Black-Scholes-Merton framework, the expected return on the call can be expressed as

$$
E\big(R_{c}\big)=r+\big(E\big(R_{s}\big)-r\big)\Omega_{c},
$$

where 2, = as/s'

4 Prove the expected return on the put can be expressed as

$$
E\big(R_{p}\big)=r+\big[E\big(R_{s}\big)-r\big]\Omega_{p},
$$

$$
{\mathrm{where~}}\varOmega_{\rho}\equiv\frac{\partial p/p}{\partial S/S}.
$$

5 The Sharpe ratio of the stock will equal the Sharpe ratio of a call option on the stock." Evaluate and explain whether this statement is true or false.

6 [Contributed by Brecklyn Groce] Suppose an investment manager calculates the Sharpe ratio of an investment in a stock index as O.35. The Sharpe ratio of a call option on the index is 0.44. In this chapter it is asserted that the Sharpe ratio of an. asset and its derivative should be the same. Why are they different in this case?.

# NOTES

1. Other well-known models are the arbitrage pricing model and the cost of carry forward/futures pricing model, which is known as interest rate parity in the foreign currency world. The CAPM is briefly mentioned in Chapters 1 and 6.
2. We are assuming no dividends, interest, cash flows, or holding costs. These would not cause any problems, but our approach would vary depending on whether the dividends are known or random.
3. To restate what we have previously learned, the notion of a certainty equivalent is that of a value that one would accept for certain in lieu of facing a risky situation. The expected value minus the risk premium that appears in the numerator is a risk-adjusted future value, which can then be discounted at the risk-free rate.
4. It is easy to use the Black-Scholes-Merton model to see that the elasticity is not less than 1. Elasticity is defined as. $(\partial c/\partial S)(S/c)$ . You should recognize this as $N\big(d_{1}\big)S/c$ from the Black-ScholesMerton model. Replacing $c$ with the Black-Scholes-Merton formula reveals that elasticity is no less than 1 if. $X e^{-r_{c}\tau}N(d_{2})$ is always true.
5. Using the Sharpe ratios for options is problematic, however, because option return distributions are highly nonnormal, and the Sharpe ratio characterizes performance exclusively with the expected return and volatility, ignoring higher-order moments associated with non-normal distributions. For an empirical analysis of some of the problems of evaluating the performance of covered call writing strategies, see Brooks, Chance, and Hemler (2019).
6. In other words, the Black-Scholes-Merton model is obtained without any reference to the option's expected return or volatility, nor does it directly provide the option's expected return and volatility.
7. Alternatively, we could use the continuous time version of the CAPM and adjust that equation so that it would contain a dt term and reflect expected returns over the interval $d t$
8. In taking expectations of this equation, recall that the expectation of $d\mathbb{W}$ is zero.
9. Remember that the variance of a constant (in this case, $(\partial c/\partial S)(S/c))$ , is the constant squared times the variance of the random variable. The variance of $d\mathbb{W}$ is $d t$

# Implied Volatility and the Volatillity Smile

Volatility of the underlying asset return is unquestionably the most critical parameter in option valuation. For one, it is the only parameter that is completely unobservable. Technically the risk-free rate and either the upcoming dividends or the upcoming dividend yield are unobservable, but these factors are not difficult to predict and they impart a relatively minor effect on option valuation. Volatility, however, is not easy to predict.. Moreover, many option pricing models, such as the Black-Scholes-Merton and binomial. models, assume that volatility is deterministic. Forcing a model with constant volatility to behave like a model with nonconstant volatility is incorrect, but it is what most researchers and practitioners do. On top of this problem, option value is highly sensitive to volatility. Thus, it is important that we take a close look at volatility..

As we previously learned, both the BSM and binomial models require five inputs: the. underlying asset price, the exercise price, the risk-free rate, the volatility, and the time to. expiration. If the underlying asset pays dividends or interest, or has any other cash flows,. these too must be incorporated as a sixth input. But in any case, volatility is such a primary. driver of option value that standard practice is to oftentimes insert the price of the option into the model and derive the volatility that makes the model price equal the market price. This volatility is called the implied volatility because it is implied from the market price. If there were no uncertainty about the pricing model used by investors, the implied volatility would be the volatility used by the market to price the option..

Inasmuch as the implied volatility should be the volatility of the underlying asset. return, any option on the underlying asset should produce the same implied volatility. But that is not what happens. What this means is either that there is no single-option valuation model that everyone accepts and uses or that people have different opinions about volatility. Different opinions are certainly acceptable, but when the same investor uses a different volatility for two options on the same asset, there is clearly something other than a difference of opinion going on.

So, let us first contrast volatility with implied volatility illustrating with several examples. Based on this analysis, we introduce the popular volatility index (VIX) associated with the $\mathrm{S\&RP}~500$ index options. Next, we further explore what implied volatility is, and then we shall look at the unusual behavior it exhibits in suggesting that the underlying can have more than one volatility at the same time.
