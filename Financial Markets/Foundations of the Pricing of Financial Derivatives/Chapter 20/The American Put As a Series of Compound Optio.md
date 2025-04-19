---
tags:
  - american_put_option
  - compound_options
  - correlation
  - multivariate_normal
  - option_pricing
aliases:
  - American Put
  - Compound Option
  - Geske Model
key_concepts:
  - American put valuation
  - Compound option series
  - Correlation of Wiener processes
  - Early exercise condition
  - Multivariate normal probability
---

# 20.2 THE AMERICAN PUT AS A SERIES OF COMPOUND OPTIONS

To solve the problem, we need to know the correlation between successive cumulative Wiener processes at different times, say $t_{1}$ and $t_{2}$ , where $t_{1}<t_{2}$ . For example, starting from time 0, we have

$$
\begin{array}{l}{{W_{t_{1}}=\displaystyle\int_{0}^{t_{1}}d W_{j}}}\ {{\quad\displaystyle\quad\Gamma_{t_{2}}=\displaystyle\int_{0}^{t_{2}}d W_{j}=\displaystyle\int_{0}^{t_{1}}d W_{j}+\displaystyle\int_{t_{1}}^{t_{2}}d W_{j}.}}\end{array}
$$

Ultimately, we shall need the correlation between $\mathbb{W}_{t_{1}}$ and $\mathbb{W}_{t_{2}}$ , which, based on Chapter 10, can be expressed as follows:1

$$
\rho_{12}={\frac{\operatorname{cov}\left(w_{1},w_{2}\right)}{{\sqrt{\operatorname{var}\left(w_{1}\right)}}{\sqrt{\operatorname{var}\left(w_{2}\right)}}}}={\frac{\tau_{1}}{{\sqrt{\tau_{1}}}{\sqrt{\tau_{2}}}}}={\sqrt{\frac{\tau_{1}}{\tau_{2}}}},
$$

where $\tau_{1}$ is the time elapsed over one increment and $\tau_{2}$ is the time elapsed over two increments.2 This correlation is important, because it is a component of a multivariate normal probability calculation, which captures the likelihood of multiple events occurring, such as exercising at one point in time, having not exercised earlier. Now we can proceed to explain how to value the option.

At any instant we exercise the option if two conditions are met:

<html><body><table><tr><td>(C1) (C2)</td><td>It has not already been exercised and if the payoff from n exercising g is greater than t the value of the put if it is not exercised.</td></tr></table></body></html>

The critical asset price that triggers early exercise is defined as $S_{t}^{*}$ in the equation

$$
X-S_{t}^{*}=P_{t}.
$$

This condition means that at $t$ , there is an asset price, $S_{t}^{*}$ , that produces a put price, $P_{t}$ When that put price is equal to the exercise value, any asset price below $S_{t}^{*}$ will trigger early exercise. The time point. $t$ is clearly any time point up to the expiration,. $T$

At the first instant, there is no probability of prior exercise. So we integrate the exercise payoff, which is the exercise price minus the asset price, over all possible asset prices less than the critical asset price. Then we discount this value back one instant. This produces two terms, one of which is the discounted exercise price multiplied by the probability that the asset price will be below the critical asset price. At the next instant we must also discount the expected payoff, but we must consider the joint probability of exercise at that instant conditional on not having exercised at the previous instant. We follow this procedure for the remaining instants over the life of the option.

Ultimately the price of the option then becomes a discounted weighted average of all of the possible payoffs. It can be written as follows:

$$
\begin{array}{r l}&{e^{-r_{c}d t}\Big(X-S_{d t}^{*}\Big)\mathrm{Prob}\Big(S_{d t}\leq S_{d t}^{*}\Big)}\ &{\quad+e^{-r_{c}2d t}\Big(X-S_{2d t}^{*}\Big)\mathrm{Prob}\Big(S_{2d t}\leq S_{2d t}^{*}~\mathrm{and}~S_{d t}>S_{d t}^{*}\Big)}\ &{\quad+e^{-r_{c}3d t}\Big(X-S_{3d t}^{*}\Big)\mathrm{Prob}\Big(S_{3d t}\leq S_{3d t}^{*},~S_{2d t}>S_{2d t}^{*}~\mathrm{and}~S_{d t}>S_{d t}^{*}\Big)}\ &{\quad+\cdot\cdot\cdot}\end{array}
$$

The overall solution can be written more compactly as

$$
P=X w_{2}-S w_{1},
$$

where

$$
\begin{array}{r l}&{w_{1}=N_{1}\left[-d_{1}\left(S_{t}^{*},d t\right)\right]+N_{2}\left[d_{1}\left(S_{d t}^{*}d t\right),-d_{1}\left(S_{2d t}^{*}2d t\right);-\rho_{12}\right]}\ &{\phantom{\rho_{1}=}+N_{3}\left[d_{1}\left(S_{d t}^{*}d t\right),d_{1}\left(S_{2d t}^{*}2d t\right),-d_{1}\left(S_{3d t}^{*}3d t\right);\rho_{12},-\rho_{13},-\rho_{23}\right]}\ &{\phantom{\rho_{1}=}+\ldots}\end{array}
$$

$$
\begin{array}{r l}&{w_{2}=e^{-r_{c}d t}N_{1}\left[-d_{2}\left(S_{d t}^{*},d t\right)\right]+e^{-r_{c}2d t}N_{2}\left[d_{2}\left(S_{d t}^{*}d t\right),-d_{2}\left(S_{2d t}^{*}2d t\right);-\rho_{12}\right]}\ &{\hphantom{-}+e^{-r_{c}3d t}N_{3}\left[d_{2}\left(S_{d t}^{*}d t\right),d_{2}\left(S_{2d t}^{*}2d t\right),-d_{2}\left(S_{3d t}^{*}3d t\right);\rho_{12},-\rho_{13},-\rho_{23}\right]}\ &{\hphantom{-}+\dots}\end{array}
$$

and

$$
\begin{array}{l}{\displaystyle{d_{1}(q,\tau)=\frac{\ln(S/q)+\left[r_{c}+\left(\sigma^{2}/2\right)\right]\tau}{\sigma\sqrt{\tau}}}}\ {{}}\ {\displaystyle{d_{2}(q,\tau)=d_{1}(q,\tau)-\sigma\sqrt{\tau}}}\end{array}
$$

for any $q$ and $\tau$ . The correlation coefficients follow the pattern,

$$
\begin{array}{c}{\rho_{12}=\displaystyle\sqrt{\frac{d t}{2d t}}=\displaystyle\sqrt{\frac{1}{2}}=\frac{1}{\sqrt{2}}}\ {\rho_{13}=\displaystyle\sqrt{\frac{d t}{3d t}}=\sqrt{\frac{1}{3}}=\frac{1}{\sqrt{3}}}\ {\rho_{23}=\displaystyle\sqrt{\frac{2d t}{3d t}}=\sqrt{\frac{2}{3}}=\sqrt{\frac{2}{3}}.}\end{array}
$$

Geske and Johnson provide the partial derivatives with respect to each of the terms in the formula. Blomeyer and Johnson (1988) provide an extension that takes into account dividend payments, and they also conduct empirical tests of the model.

Because exercise is possible at any time instant, this formula consists of an infinite number of terms, which would seem to make the formula analytically intractable. Geske and Johnson emphasize that the formula is an exact solution, even if it does contain an infinite number of terms. They provide an analytical approximation based on a method called the Richardson extrapolation, which basically assumes that the put can be exercised only at three points spread over its life. This approach greatly reduces the complexity of the problem. They obtain the price of a put that can be exercised only at expiration,. which is the standard Black-Scholes-Merton model price, and the price of another put that can be exercised only halfway to expiration or at expiration, which requires a bivariate. normal probability computation, as well as the price of another put that can be exercised only one-third of the way through its life or two-thirds of the way through its life or at expiration, which requires a trivariate normal probability computation. The American put value is then approximated as a weighted average of the prices of these three puts. They. argue that an approximation of an exact formula is better than an approximation where the solution is not known, which, other than using numerical methods, is all one can do to price an American put. Bunch and Johnson (1992) provide an improvement on this. technique.

Research on American put pricing has gone well beyond the Geske-Johnson model, but it is safe to say that there is no closed-form solution with a finite number of terms and never can be. The early exercise decision itself is an infinite number of decisions. Hence, it would. never be possible to reduce the complexity of the problem without making some simplify-. ing assumptions that ultimately result in the formula being an approximation. Fortunately, advances in computing power have made the binomial model the best method of pricing American puts. Nonetheless, it is important to understand that American options are compound options. They are options in which choices are permitted that allow the option to terminate early by claiming the exercise value or to remain alive with the possibility of. exercise at a later date. The Geske-Johnson model makes that clear.
