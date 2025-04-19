---
tags:
  - asset_pricing
  - expected_asset_price
  - expected_return
  - gbm_abm
aliases:
  - Asset Price Expectation
  - Expected Price
  - Future Asset Price
key_concepts:
  - Arithmetic Brownian motion
  - Expected asset price
  - Expected rate of return
  - Geometric Brownian motion
  - Stochastic differential equation
---

# 12.5 FINDING THE EXPECTED FUTURE ASSET PRICE

Given the solution,

$$
S_{t}=S_{0}e^{\mu t+\sigma W_{t}},
$$

to the stochastic differential equation, we shall now use it to obtain the expected asset price at t. Such a concept is commonly seen in real markets, such as when someone asks an analyst, "Where do you think the Dow will be in a year?" Using Equation (12.49), we. express the problem as follows:

$$
E(S_{t})=S_{0}E\left(e^{\mu t+\sigma{\mathcal{W}}_{t}}\right)=S_{0}e^{\mu t}E\left(e^{\sigma{\mathcal{W}}_{t}}\right).
$$

This expectation is evaluated by recognizing that $\mathbf{}\mathbf{}{W}_{t}$ is normally distributed. We are reminded that the probability density for a normally distributed random variable $\mathbf{}\mathbf{}{W}_{t}$ which has mean zero and variance $t$ , is

$$
f\big(\boldsymbol{W}_{t}\big)=\frac{1}{\sqrt{2\pi t}}e^{-\boldsymbol{W}_{t}^{2}/2t}.
$$

Thus, we can find the expected value of $S_{t}$ by evaluating the following expression:

$$
E\big(e^{\sigma W_{t}}\big)=\int_{-\infty}^{\infty}e^{\sigma W_{t}}\frac{1}{\sqrt{2\pi t}}e^{-W_{t}^{2}/2t}d W_{t}.
$$

We express the right-hand side as

$$
\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi t}}e^{\sigma W_{t}}e^{-W_{t}^{2}/2t}d W_{t}.
$$

Working on the exponent, we obtain

$$
\begin{array}{r l}&{\sigma{\bf{\boldsymbol{W}}}_{t}-{\boldsymbol{W}}_{t}^{2}/2t=\frac{2\sigma{\boldsymbol{\boldsymbol{W}}}_{t}t-{\boldsymbol{W}}_{t}^{2}}{2t}}\ &{\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad}\ &{\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad}\ &{\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad}\ &{\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad}\ &{\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad
$$

So now we have

$$
e^{\sigma^{2}t/2}\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi t}}e^{-\frac{1}{2}\left(\frac{\mathbb{W}_{t}-\sigma t}{\sqrt{t}}\right)^{2}}d\mathbb{W}_{t}.
$$

The integrand is the probability density function for a normally distributed random variable with mean $\sigma t$ and variance $t$ and, by definition, integrates to a value of 1.0. Thus,.

$$
E\big(e^{\sigma W_{t}}\big)=e^{\sigma^{2}t/2}.
$$

So our expectation is,

$$
E\left(S_{t}\right)=S_{0}e^{\mu t+\sigma^{2}t/2}=S_{0}e^{(\mu+\sigma^{2}/2)t}.
$$

Note that this result is also equal to $E(S_{t})=S_{0}e^{\alpha t}$ because $\alpha=\mu+\sigma^{2}/2$ . This is an intuitively simple result. It says that the expected future asset price is the current asset price compounded at the expected rate of return.

We now explore the choice of modeling financial problems with either GBM or ABM.
