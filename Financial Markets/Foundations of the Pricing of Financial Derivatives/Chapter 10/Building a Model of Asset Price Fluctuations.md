---
tags:
  - '#arithmetic_brownian_motion'
  - '#asset_price_fluctuations'
  - '#asset_return_model'
  - '#drift_term'
  - '#geometric_brownian_motion'
  - '#ito_process'
  - '#lognormal_distribution'
  - '#noise_term'
  - '#wiener_process'
---
# 10.4 BUILDING A MODEL OF ASSET PRICE FLUCTUATIONS

The characteristics of the return on an asset can be described by the expected return and. variance of return.' Let $E(R)$ be the expected return on the asset and $\sigma^{2}$ be the variance of the return, with both measures standardized to a common period of time, typically a. year.4 Thus, these are the annual expected return and variance. Then $\sigma$ is the standard deviation, which is the square root of the variance. If we have an effective model, a sample of historical data will produce an average return and standard deviation equal to these. values.

Let $R_{t}h$ be the return on the asset, between $t$ and $t+b$ , which is its price change divided. by its base price minus one, over the holding period. $b$ . For example, $R_{t}$ is stated as an annual rate and $b$ , the holding period, is a fraction of a year. Thus, $R_{t}h$ is the return over the holding period. Now let us set $R_{t}h$ equal to $E(R)b+g_{t}$ where $g_{t}$ represents the random component of the return, again generated between $t$ and $t+b$ . In other words,. the return consists of the expected return plus a random component. We do not yet know what the random component,. $g_{t}$ , is, but we assume it is related to the variance. Now, let. us force the expected value of our model to. $E(R)b$ . This requirement is easily fulfilled by. letting $E\left(g_{t}\right)=0$ . Thus, we must keep this constraint in mind when we look for a suitable. functional form for $g_{t}$

Now let us make the model have the correct variance. If the variance over a year is $\sigma^{2}$ then the variance over the holding period. $b$ is $h\sigma^{2}$ . Thus, the variance of our model should. be such that it equals. $h\sigma^{2}$ . So far, our model has two terms, $E(R)b+g_{t}$ The term $E(R)b$ is a constant, so it has no variance. Thus, we need to make sure that var. $\left(g_{t}\right)=h\sigma^{2}$

One model that has the appropriate variance is $g_{t}=\sigma\varepsilon_{t}{\sqrt{d t}}$ which is simply $\sigma d\boldsymbol{W}_{t}$ This model is just a modified Wiener process with the transformation coming from multiplication by the volatility of the asset. Remember that we also have to have the expected value of $g_{t}$ equal to zero, but that requirement is upheld because we already know that $g_{t}=\sigma d\mathbb{W}_{t}$ and $E\left(d W_{t}\right)=0$

Now our model looks like this:

$$
R_{t}=E\left(R\right)d t+\sigma\varepsilon_{t}\sqrt{d t}.
$$

Let us check and see if this model has the other necessary properties. If $S_{t}$ is the current asset price, then the asset price after the period $d t$ is $\boldsymbol{S_{t+d t}}=\boldsymbol{S_{t}}\left[\boldsymbol{1}+\boldsymbol{E}\left(\boldsymbol{R}\right)\dot{d t}+\sigma\varepsilon_{t}\sqrt{d t}\right]$ What is the variance of this future asset price? Over the next increment, the variance is

$$
\left[S_{t}+S_{t}E\left(R\right)d t+S_{t}\sigma\varepsilon_{t}\sqrt{d t}\right]=\mathrm{var}\left(S_{t}\right)+\mathrm{var}\left[S_{t}E\left(R\right)d t\right]+\mathrm{var}\left(S_{t}\sigma\varepsilon_{t}\sqrt{d t}\right)=S_{t}^{2}\sigma^{2}d t.
$$

Note that this result makes use of the fact that the constants, $S_{t},E(R)$ and $d t$ , have zero variance.

Now consider increments to a later period $T.$ The variance is

$$
\mathrm{var}\left(S_{T}\right)=\int_{t}^{T}S_{t}^{2}\sigma^{2}d j=S_{t}^{2}\sigma^{2}\int_{t}^{T}d j=S_{t}^{2}\sigma^{2}\left(T-t\right).
$$

So, clearly the further out we look, that is, the larger $T$ is, the higher the variance is.

Finally, the model must not permit the asset price to ever go to or below zero. Let us write the model in the following form:.

$$
\frac{d S_{t}}{S_{t}}=E\left(R\right)d t+\sigma\varepsilon_{t}\sqrt{d t}.
$$

Multiplying through by. $S_{t}$ makes everything on the right-hand side (RHs) be multiplied by $S_{t}$ . That is, the model can be written as.

$$
d S_{t}=E\left(R\right)S_{t}d t+\sigma S_{t}\varepsilon_{t}\sqrt{d t}.
$$

The first term on the RHS is the drift term and the second is the noise term, both expressed in currency units. Note that as the asset price declines, both the drift term and the noise term are diminished. Thus, the smaller $S_{t}$ is, the more the price changes are diminished. It is technically possible for a sufficiently negative shock to drive the price to zero, though this requires an incredibly large negative shock, which is an improbable event. But, from Equation (10.10), it is easily seen that if the price hits zero, any further price changes are all zero. Zero is said to be an absorbing barrier. Hence, our requirement that the price cannot be negative is met. That said, we cannot completely rule out a zero price. In Chapter 12, we shall see that the process we have described here is actually an approximation of a lognormal process. Given that it is not possible to take the log of zero, a zero price is ruled out. But for now, avoiding negative prices is our goal and that goal is achieved with this model.

One final adjustment is necessary. Most of the time the annualized expected return is written as either $\alpha$ Or $\mu$ . We shall choose the former and will reserve $\mu$ for another term. Thus, the model is written as

$$
\frac{d S_{t}}{S_{t}}=\alpha d t+\sigma d W_{t},
$$

where it is understood that $d\mathbb{W}_{t}=\varepsilon_{t}\sqrt{d t}$ We see clearly here that $S_{t}$ cannot obtain zero, otherwise the left-hand side (LHs) of this equation is undefined. A stochastic process of this type is called an Ito process. It is more generally stated in the form,. $d S_{t}=\alpha\left(S,t\right)d t+$ $\sigma\left(S,t\right)d\mathbb{W}_{t}$ , where the expected value and variance are allowed to change with $S$ and $t$

Equation (10.11) appears to imply that the LHS is normally distributed because. $d\mathbb{W}_{t}$ is normally distributed. Recall multiplying a normally distributed variable by a constant. and adding another constant does not change the distribution type, just its parameters. As. we will see in Chapter 12, the LHS is in fact lognormally distributed. At this point, we. simply note that this result is similar to discrete and continuous compounding covered in Chapter 3, Section 3.3.

To recap, the model allows us to replicate the behavior of the asset over a short holding period. We have taken the basic Brownian motion process and converted it into a form that models asset price movements. This model has many convenient and reasonable properties. We refer to the process as geometric Brownian motion. It is "geometric" in the sense that proportional changes, meaning percentage changes, in the asset price follow this stochastic process. Geometric Brownian motion can be formally stated as

$$
d S_{t}=\alpha\left(S,t\right)S_{t}d t+\sigma S_{t}d W_{t}.
$$

It is important to emphasize that the driver of the geometric aspect is the presence of the underlying asset price in the noise term. Thus, as the asset price falls, the impact of the noise term also falls. Given the continuous nature of this process, the asset price never reaches zero. We can divide both sides by $\mathrm{S_{t}}$ and express in the traditional finance form or

$$
\frac{d S_{t}}{S_{t}}=\alpha\left(S,t\right)d t+\sigma d W_{t}.
$$

We thus implicitly assume that the asset prices follow a lognormal distribution. This is not the normal or bell-shaped curve. A lognormal distribution is skewed toward positive returns in contrast to the normal distribution, which is symmetric. A lognormal distribution does imply, however, that the logarithm of the returns comes from the normal or bell-shaped distribution.' These properties are often desirable and fairly reasonable from an empirical standpoint.

An alternative process is known as arithmetic Brownian motion, where the asset prices follow a normal distribution.6 It is "arithmetic" in the sense that absolute changes, meaning dollar changes, in the asset price follow this stochastic process and thus can easily be added together. Arithmetic Brownian motion can be formally stated as

$$
d S_{t}=\alpha\left(S,t\right)d t+\sigma_{\S}d W_{t}.
$$

It is important to emphasize that the driver of the arithmetic aspect is the absence of the underlying asset price in the noise term. Also, we introduce the subscript, $\$1$ (dollars), to highlight the unit of measure is whatever the unit of measure of the asset price (assumed $\$1$ here) and no longer expressed as a percentage. As discussed in later chapters, the drift term can be expressed in dollars or percentage depending on context. Thus, as the asset price falls, the noise term is not affected. Given the continuous nature of this process, the asset price can easily reach zero as well as go negative. One benefit of arithmetic Brownian motion is zero asset values are now possible-an unfortunate reality for many financial instruments.

Of course, no model will reproduce perfectly the process in which asset returns are. generated. The real world can rarely be reduced to a set of mathematical equations. But. as is nearly always the case, if a set of mathematical equations can reproduce the basic manner in which a real-world phenomenon occurs, it can have many uses. One of these uses is in pricing options on assets that follow the process described by the mathematical model covered here.

This model will be developed much further in Chapter 13.
