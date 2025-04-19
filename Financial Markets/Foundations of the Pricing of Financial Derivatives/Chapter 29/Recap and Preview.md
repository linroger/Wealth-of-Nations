---
tags:
  - asset_pricing
  - expected_returns
  - option_pricing
  - pure_assets
  - state_preference
aliases:
  - Chapter 30
  - Preview
  - Recap
key_concepts:
  - call option price
  - complex assets
  - expected returns options
  - option pricing theory
  - pure asset prices
  - state preference theory
---

# 29.6 RECAP AND PREVIEW

With the development of option pricing theory, state preference theory has stepped to the. back in the family of valuation models. Although, as we have seen here, state preference. theory is clearly consistent with option pricing theory, the implications of the latter are much easier to observe in the real world, and, hence, it has become more widely used in practice as well as in scholarly work. Keep in mind, however, that just as a biologist cannot. simply observe a specimen with the naked eye and expect to learn much about it, so must a serious student of finance observe the internal structure of the financial pricing process.. State preference theory provides the framework to accomplish that task..

In Chapter 30, we examine what option pricing theory implies for the expected returns on options and how this relates to the expected returns on the underlying assets.

# QUESTIONS AND PROBLEMS

1 Compare and contrast pure assets with complex assets.

2 Suppose we have four states and four complex assets with the payoffs in the HH matrix. Further, assume we observe the prices of the complex assets have all been normalized to 100 (the $s$ matrix). Compute the prices of the pure assets in this setting:

$$
\mathbf{H}={\left|\begin{array}{l l l l}{105}&{65}&{20}&{40}\ {105}&{95}&{150}&{130}\ {105}&{130}&{110}&{200}\ {105}&{150}&{180}&{110}\end{array}\right|}\mathbf{S}={\left|\begin{array}{l}{100.00}\ {100.00}\ {100.00}\ {100.00}\end{array}\right|}.
$$

3 With pure assets one must be careful with rounding. Based on the pure asset values given next, compute the implied discrete compounded interest rate when the pure asset values are rounded at the first decimal place. Repeat this exercise for rounding at the second through sixth decimal place. Discuss your findings for the six cases (rounding at first, second, third, fourth, fifth, and sixth decimal place), explaining the role of rounding in computing pure asset values:

$$
\Psi=\left|\begin{array}{c}{{0.366548}}\ {{0.187780}}\ {{0.143015}}\ {{0.273531}}\end{array}\right|.
$$

4 Suppose you have an asset priced at 50 that can go either up to 60 or down to 40 in the next year. The risk-free rate is $5\%$ (discrete compounding). Consider a call option. with exercise price of 50. First, compute the correct call option price. Identify three approaches to solving for the state prices and demonstrate that each approach results. in the same state prices.

5Using just call option prices, explain how to construct pure asset prices when given five different exercise prices for one-month options.

# NOTES

1. Instead of the word asset, some articles and books use the term security, but a security is a claim issued by a company. We shall not use that term here, preferring the more general term asset..

2. To obtain the inverse of. $\mathbf{H}$ we require the condition that no row or column of. $\mathbf{H}$ is a linear function of any other row or column. This condition will always hold if no complex asset is a linear function of any other combination of complex assets. Otherwise, that asset would be. redundant.
3. To solve for $r_{\mathrm{f}}$ in matrix notation we would introduce an $n\times1$ row vector, i, which contains 1. as each element. Then. $r_{f}=(1/\mathfrak{u}\Psi)-1$
4. The matrix operations of transposing, multiplying, and taking the inverse can be easily done using Excel's array formulas $=$ transpose() $\mathsf{\Gamma}_{\mathsf{=m m u l t}()}$ , and $\equiv$ minverse().
5. The derivative of the call formula with respect to the exercise price has a minus sign, which would have to be ignored if one were using the derivative as the price of a digital option..

# Option Prices and Expected Returns

n the study of finance in general, we devote considerable time to deriving and using pricing models. Probably the two best known pricing models are the capital asset pricing model and the Black-Scholes-Merton option pricing model.1 The former, commonly referred to as the CAPM, provides the required rate of return on the asset. If the asset is correctly priced, which the model assumes must happen in equilibrium, the return expected by investors, known as the expected rate of return, equals the required rate of return. But asset pricing models are not usually expressed in terms of the price of the asset, whereas option pricing models are almost always expressed in terms of the price of the option. In this chapter, we shall connect the expected return and price for both the asset and the option. In addition, we shall tie together the expected returns and volatilities of the option to that of the asset. Much of this work draws from Rubinstein (1984).
