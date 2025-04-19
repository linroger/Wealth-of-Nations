---
tags:
  - continuous_random_variables
  - covariance
  - expectation
  - probability_distribution
  - variance
aliases:
  - CRV
  - Expected Value
  - Probability Density
  - Variance Calculation
key_concepts:
  - Continuous random variables
  - Covariance of variables
  - Density function integration
  - Expectation calculation
  - Variance of variables
---

# 4.3 CONTINUOUS RANDOM VARIABLES

For continuous random variables, the operations are somewhat different, but the results are conceptually identical to the discrete case. Consider a random variable $x$ with lower. limit $x_{L}$ and upper limit $x_{H}$ Its density function is $f(x)$ . Over the entire range of outcomes, the density integrates to 1:

$$
\int_{x_{L}}^{x_{H}}f(x)d x=1.
$$

Remember that the value of the density function at a point is not particularly useful. That is, for a given value of $x$ , say $x_{i}$ , the value $f(x_{i})$ is merely the height of the curve specified. by the density, $f(x)$ . The integration of the density over a range gives us the probability of. the event over that range. For example, if we wish to know if. $x$ is less than or equal to $^{a}$ the integration of the density is.

$$
\operatorname*{Pr}(x\leq a)=\int_{x_{L}}^{a}f(x)d x.
$$

This value is the cumulative probability that $x$ will be lower than $a$ . It is often called the distribution function and sometimes written as $F(a)$ . For a range of $a$ to $b$ , the probability that the $x$ falls in that range is found as follows:.

$$
\operatorname*{Pr}(a\leq x\leq b)=\int_{a}^{b}f(x)d x.
$$

Note that this result can also be found as

$$
\operatorname*{Pr}(a\leq x\leq b)=\int_{x_{L}}^{b}f(x)d x-\int_{x_{L}}^{a}f(x)d x.
$$

Here we integrate from the lower limit up to $b$ and from the lower limit to. $^{a}$ .We then subtract the latter from the former..

In the following material, we will set the lower limit to $-\infty$ and the upper limit to. $+\infty$

# 4.3.1 The Expectation of a Continuous Random Variable

To obtain the expectation, we simply multiply each of the infinite values of the random variable by its density function and integrate,

$$
E(x)=\int_{-\infty}^{\infty}x f(x)d x.
$$

If $x$ is actually a constant $a$ , then we have the following result,

$$
E(a)=\intop_{-\infty}^{\infty}a f(x)d x=a\intop_{-\infty}^{\infty}f(x)d x=a.
$$

Thus, the expected value of a constant is simply the constant. Now, suppose we multiply the constant times the random variable,.

$$
E(a x)=\intop_{-\infty}^{\infty}a x f(x)d x=a\intop_{-\infty}^{\infty}x f(x)d x=a E(x).
$$

And we simply pulled the constant out of the integration.

# 4.3.2 The Variance of a Continuous Random Variable

The variance of a continuous random variable $X$ is given as

$$
\operatorname{var}(x)=\int_{-\infty}^{\infty}[x-E(x)]^{2}f(x)d x.
$$

The key results for the variance are given as follows. First note that the variance itself can be restated as

$$
{\begin{array}{r l}&{\operatorname{var}(x)=\displaystyle\int_{-\infty}^{\infty}(x-E(x))^{2}f(x)d x=\displaystyle\int_{-\infty}^{\infty}\left\{x^{2}-2x E(x)-[E(x)]^{2}\right\}f(x)d x}\ &{\qquad\infty}\ &{\qquad=\displaystyle\int_{-\infty}^{\infty}x^{2}f(x)d x-2E(x)\displaystyle\int_{-\infty}^{\infty}x f(x)d x+[E(x)]^{2}\displaystyle\int_{-\infty}^{\infty}f(x)d x}\ &{\qquad-\infty}\ &{\qquad=E{\bigl(}x^{2}{\bigr)}-2[E(x)]^{2}+[E(x)]^{2}=E{\bigl(}x^{2}{\bigr)}-[E(x)]^{2}.}\end{array}}
$$

If $x$ is a constant, we have the following:

$$
\operatorname{var}(a)=\int_{-\infty}^{\infty}[a-E(a)]^{2}f(x)d x=\int_{-\infty}^{\infty}(a-a)^{2}f(x)d x=0.
$$

Obviously, the variance of a constant is zero. Now suppose we multiply a constant times the random variable.

$$
\begin{array}{l}{\operatorname{var}(a x)=\displaystyle\int_{-\infty}^{\infty}[a x-E(a x)][a x-E(a x)]f(x)d x}\ {\qquad\to\infty}\ {\displaystyle=\int_{-\infty}^{\infty}a[x-E(x)]a[x-E(x)]f(x)d x=a^{2}\displaystyle\int_{-\infty}^{\infty}[x-E(x)]^{2}f(x)d x=a^{2}\operatorname{var}(x).}\end{array}
$$

So, the constant comes out of the variance as a square. Suppose we add a constant to the random variable.

$$
\begin{array}{l}{\operatorname{var}(a+x)=\displaystyle\int_{-\infty}^{\infty}\left[a+x-E(a+x)\right]^{2}f(x)d x}\ {\qquad\infty}\ {{\displaystyle{\quad=\int_{-\infty}^{\infty}\left[a-E(a)+x-E(x)\right]^{2}f(x)d x}=\int_{-\infty}^{\infty}\left[a-a+x-E(x)\right]^{2}f(x)d x}}\ {\qquad\infty}\ {{\displaystyle{\quad=\int_{-\infty}^{\infty}\left[x-E(x)\right]^{2}f(x)d x}=\operatorname{var}(x)}.}\end{array}
$$

Adding a constant clearly has no effect on the variance.

# 4.3.3 The Covariance of Continuous Random Variables

The covariance of $x$ and $y$ is

$$
\operatorname{cov}(x,y)=\int_{-\infty}^{\infty}[x-E(x)][y-E(y)]f(x y)d x y.
$$

In the previous equation, $f(x y)$ is the joint density of. $x$ and $y$ , which gives the probability of outcomes of both. $x$ and $y$ occurring. The single integral in the covariance equation means to integrate over all joint outcomes. At this point it will be useful to introduce a substitution for the integral and the density function.

$$
\int_{-\infty}^{\infty}f(x y)d x y=\int_{-\infty-\infty}^{\infty}{\int_{+}^{\infty}f(y|x)f(x)d x d y}=\int_{-\infty-\infty}^{\infty}{f(x|y)f(y)d y}d x.
$$

Here we substitute the product of the conditional and marginal densities for the joint density. When we do so, we must have an integral and a differential for each density. Also note that any time we see any of these expressions with no other terms, it equals 1.0. In other words,

$$
\begin{array}{l}{\displaystyle{\int_{-\infty}^{\infty}f(y|x)d y=\int_{-\infty}^{\infty}f(x|y)d x=1.}}\end{array}
$$

Now our covariance can be written as

$$
\begin{array}{r l}&{\quad_{\infty}^{\infty}}\ &{=\int_{0}^{t}\left(1\gamma-{\cal K}(\gamma)-{\cal K}(\lambda)+{\cal K}(\lambda){\cal K}(\gamma)\right)\int(x)d x\gamma d x}\ &{\quad-\omega^{*}}\ &{=\int_{0}^{t}\mathcal{K}(f(x))d x-{\cal K}(\gamma)\overline{{\int_{x}^{\infty}\left(x(y)\right)d x\gamma d x}}-{\cal K}(x)\overline{{\int_{x}^{\infty}\eta(x)d y}}}\ &{\quad-\omega^{*}}\ &{\quad+{\cal E}(x)\mathbb{E}(y)\overline{{\int_{x}^{\infty}\left(f(x)\right)d x\gamma d x}}}\ &{={\cal E}(x)-\mathcal{K}(y)\overline{{\int_{x}^{\infty}\left(x(y)\right)d x d x\gamma-{\cal E}(x)\int_{x}^{\infty}\int_{y}^{t}\eta(x)\left(y\right)d x d y}}+{\cal E}(x){\cal E}(y)}\ &{=\cfrac{\omega^{*}}{\omega^{*}}}\ &{=\cfrac{\rho}{\omega^{*}}}\ &{=\cfrac{\rho}{\omega(x)}-\mathbb{E}(y)\overline{{\int_{x}^{\infty}\int_{x}^{x}\left(y\right)d x d y}}-\cfrac{\rho}{\omega^{*}}}\ &{=\cfrac{\rho}{\omega(x)}-\mathbb{E}(x)\overline{{\int_{x}^{\infty}\int_{x}^{x}\left(y\right)d x\int_{x}^{\infty}\left(y\right)d x\int_{x}^{\infty}\left(y\right)d y d x}}+{\cal E}(x)\mathbb{E}(y)}\ &{=\cfrac{\rho}{\omega(x)}-\mathbb{E}(x)\overline{{\int_{x}^{x}\left(y\right)d x d y}}.}\end{array}
$$

So we have

$$
\operatorname{cov}(x,y)=E(x y)-E(x)E(y).
$$

Covariances with constants are zero as indicated by the following:

$$
\operatorname{cov}(a,x)=\int_{-\infty}^{\infty}[a-E(a)][x-E(x)]f(x y)d x y=\int_{-\infty}^{\infty}(a-a)[x-E(x)]f(x y)d x y=0.
$$

Next we show the important result that the variance of a weighted combination of random variables is a weighted combination of their variances and all possible pairwise covariances.

$$
{\begin{array}{r l}{\operatorname{var}(\alpha+b)}&{=\displaystyle\int_{0}^{\infty}|(\alpha+b\gamma-E(\alpha+b\gamma))|^{2}(c\gamma)d x\gamma}\ &{=\displaystyle\int_{0}^{\infty}|(\alpha-E(\alpha)+b\gamma-E(b\gamma))|^{2}(c\gamma)d x\gamma}\ &{=\displaystyle\int_{0}^{\infty}|(\alpha-E(\alpha))+b\gamma-E(b\gamma)|^{2}(c\gamma)d x\gamma}\ &{=\displaystyle\int_{0}^{\infty}|(\alpha|-E(\alpha))+b|\gamma-E(\gamma)|)|^{2}(c\gamma)d x\gamma}\ &{=\displaystyle\int_{0}^{\infty}|(\alpha-E(x))+b|\gamma-E(y)|^{2}(c\gamma)d x\gamma}\ &{=\displaystyle\int_{0}^{\infty}|(\alpha^{2}(1-E(x))^{2}+b^{2}\left|\gamma-E(y)\right|^{2}+2d u b(x-E(x))|\gamma-E(y)|)\int(x\gamma)d x}\ &{=\displaystyle\int_{0}^{\infty}|(\alpha-E(x))^{2}(\nu)d x\gamma}\ &{=\displaystyle\int_{-\infty}^{\infty}|(\nu-E(x))^{2}(\nu)d x\gamma+2u b^{2}\left|\int_{(1-E(x))}^{\infty}E(y,x)d\gamma\right|d x\gamma.}\end{array}}
$$

Recall that previously we substituted the product of the conditional and marginal densities for the joint density and split the single integral into the product of two integrals. Using these tricks, we obtain $a^{2}\operatorname{var}(x)$ for the first term, $b^{2}\mathrm{var}(y)$ for the second and $2a b\mathrm{cov}(x,y)$ Thus,

$$
\operatorname{var}(a x+b y)=a^{2}\operatorname{var}(x)+b^{2}\operatorname{var}(y)+2a b\operatorname{cov}(x,y).
$$

The covariance between two weighted random variables is simply their covariance times the product of their weights:

$$
\operatorname{cov}(a x,b y)=\int_{-\infty}^{\infty}[a x-E(a x)][b y-E(b y)]f(x y)d x y
$$

$$
\begin{array}{l}{\displaystyle=\int_{-\infty}^{\infty}\{a[x-E(x)]b[y-E(y)]\}f(x y)d x y}\ {\displaystyle\qquad\infty}\ {=a b\displaystyle\int_{-\infty}^{\infty}[x-E(x)][y-E(y)]f(x y)d x y=a b\mathrm{cov}(x,y).}\end{array}
$$

This result is widely used in portfolio analysis, a point we made in the discrete case.

The covariance between the sum of a constant and random variables times another. sum of a constant and a random variable is simply the covariance of the random variables:

$$
\begin{array}{r l}&{\mathrm{cov}(a+x,b+y)=\displaystyle\int_{-\infty}^{\infty}[\left|a+x-E(a+x)\right|]b+y-E(b+y)]f(x y)d x y}\ &{\mathrm{~cov~}}\ &{\mathrm{~=~}\displaystyle\int_{-\infty}^{\infty}[[a-E(a)+x-E(x)][b-E(b)+y-E(y)]f(x y)d x y}\ &{\mathrm{~~,~}}\ &{\mathrm{~~}\mathrm{~=~}\displaystyle\int_{-\infty}^{\infty}[[a-a+x-E(x)][b-b+y-E(y)]f(x y)d x y}\ &{\mathrm{~~,~}}\ &{\mathrm{~=~}\displaystyle\int_{-\infty}^{\infty}[[x-E(x)][y-E(y)]f(x y)d x y=\mathrm{cov}(x,y).}\end{array}
$$

One of the more complex results is the covariance between the sum of two random variables and a third random variable:

$$
\begin{array}{l}{\operatorname{cov}(x+y,z)=\displaystyle\int_{-\infty}^{\infty}[x+y-E(x+y)][z-E(z)]f(x y z)d x y z}\ {\qquad-\infty}\ {\qquad\infty}\ {=\displaystyle\int_{-\infty}^{\infty}[x-E(x)+y-E(y)][z-E(z)]f(x y z)d x y z}\ {\qquad-\infty}\ {\qquad\infty}\ {=\displaystyle\int_{-\infty}^{\infty}[x z-x E(z)-E(x)z+E(x)E(z)+y z-y E(z)-E(y)z+E(y)E(z)]}\end{array}
$$

$$
\begin{array}{l}{{\displaystyle+\int_{-\infty}^{\infty}y z f(x y z)d x y z-E(z)\int_{-\infty}^{\infty}\int y f(x y z)d x y z}}\ {{\displaystyle-E(y)\int_{-\infty}^{\infty}}}\end{array}\nonumber
$$

As we did previously when working with only two random variables, we need to convert the joint density into the product of the marginal and conditional densities. Now, however, we have three variables. We use the following relationships:

$$
\begin{array}{c}{f(x y z)=f(y|x z)f(x z)=f(x|y z)f(y z)=f(z|x y)f(x y)}\ {=f(y z|x)f(x)=f(x z|y)f(y)=f(x y|z)f(z).}\end{array}
$$

As we have previously noted, the integral of any density function over its entire domain is 1.0. Thus,

$$
\int_{-\infty}^{\infty}f(y z|x)d y z=\int_{-\infty}^{\infty}f(x z|y)d x z=\int_{-\infty}^{\infty}f(x y|z)d x y=1.0.
$$

Of the eight expressions for the covariance, the first is, therefore,

$$
\begin{array}{l}{{\displaystyle\int_{-\infty}^{\infty}x z f(x y z)d x y z=\int_{-\infty}^{\infty}\int_{}^{\infty}x z f(y|x z)f(x z)d y d x z}}\ {{\mathrm{~}_{\infty}}}\ {{\displaystyle=\int_{-\infty}^{\infty}f(y|x z)d y\int_{-\infty}^{\infty}x z f(x z)d x z=E(x z)}.}\end{array}
$$

The second is

$$
\begin{array}{c}{{\displaystyle-E(z)\int_{-\infty}^{\infty}x f(x y z)d x y z=-E(z)\int_{-\infty}^{\infty}f(y z|x)d y z\int_{-\infty}^{\infty}x f(x)d x}}\ {{=-E(z)E(x).}}\end{array}
$$

The third is

$$
\begin{array}{c}{{\displaystyle-E(x)\int_{-\infty}^{\infty}z f(x y z)d x y z=-E(x)\int_{-\infty}^{\infty}f(x y|z)d x y\int_{-\infty}^{\infty}z f(z)d z}}\ {{=-E(x)E(z).}}\end{array}
$$

The fourth expression is clearly $E(x)E(z)$ . The fifth expression is

$$
\begin{array}{l}{+\displaystyle\int_{-\infty}^{\infty}y z f(x y z)d x y z=\displaystyle\int_{-\infty-\infty}^{\infty}\int_{-\infty}^{\infty}y z f(z|y z)f(x y z)d x d y z}\ {=\displaystyle\int_{-\infty}^{\infty}f(x|y z)d x\displaystyle\int_{-\infty}^{\infty}y z f(y z)d y z=E(y z).}\end{array}
$$

The sixth expression is

$$
\begin{array}{c}{{\displaystyle-E(z)\int_{-\infty}^{\infty}y f(x y z)d x y z=-E(z)\int_{-\infty}^{\infty}f(x z|y)d x z\int_{-\infty}^{\infty}y f(y)d y}}\ {{=-E(z)E(y).}}\end{array}
$$

The seventh expression is

$$
\begin{array}{c}{{\displaystyle-E(y)\int_{-\infty}^{\infty}z f(x y z)d x y z=-E(y)\int_{-\infty}^{\infty}f(x y|z)d x y\int_{-\infty}^{\infty}z f(z)d z}}\ {{=-E(y)E(z).}}\end{array}
$$

The eighth expression is clearly $E(y)E(z)$ . Thus, overall our covariance is

$$
\begin{array}{r l}&{E(x z)-E(z)E(x)-E(x)E(z)+E(x)E(z)+E(y z)-E(z)E(y)-E(y)E(z)+E(y)E(z)}\ &{\quad=E(x z)-E(x)E(y)+E(y z)-E(y)E(z)=\mathrm{Cov}(x,z)+\mathrm{Cov}(y,z).}\end{array}
$$
