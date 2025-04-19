---
tags:
  - ito_integral
  - ito_lemma
  - riemann_integration
  - stochastic_function
  - stochastic_integration
aliases:
  - Ito Integral
  - Ito's Integral
key_concepts:
  - Ito integral definition
  - Ito's lemma
  - Riemann integration
  - Stochastic function derivative
  - Stochastic integration
---

# 11.3 ITO'S INTEGRAL

In addition, Ito's lemma can be expressed in integral form. Let us restate the problem. We are given a random variable $x_{t}$ that follows the stochastic process:

$$
d x_{t}=\mu(x,t)d t+\sigma(x,t)d W_{t},
$$

where we have subscripted $t$ on $x$ to reinforce the point that $x$ can take on different values at different times $t.$ depending on the evolution of $\mathbb{W}_{t}$ through time. Applying Ito's lemma to the function, $\boldsymbol{F}(\boldsymbol{x},t)$ , we obtain

$$
d F\bigl(x_{t},t\bigr)=\frac{\partial F}{\partial t}d t+\frac{\partial F}{\partial x_{t}}d x_{t}+\frac{1}{2}\frac{\partial^{2}F}{\partial x_{t}^{2}}d x_{t}^{2}.
$$

Now suppose we integrate over the period from time 0 to time. $t_{\cdot}$ an operation called stochastic integration, which is not the same as standard or non-stochastic integration. The. latter is done by dividing the area under a curve into rectangles. The area under the curve is approximately the sum of the areas of each of the rectangles. As the number of rectangles. goes to infinity, the sum of the areas of the rectangles approaches the area under the curve.. Alternatively, standard integration can be viewed as adding up all of the infinitesimally. small values $d X/d t$ across values of $t$ Consequently, the derivative must be defined for all values of t. This type of standard integration is called a Riemann integration.

In a stochastic function, however, a derivative such as. $d x_{t}/d t$ is not defined. To put it. somewhat roughly, the zig-zaggedness of $x_{t}$ renders it impossible for the slope of a tangent. line at any point to have a finite limit, which is a requirement for a derivative to exist. It is possible, however, to integrate a stochastic function by defining integration somewhat differently. Instead of being the limit of the area under each rectangle under the curve, a stochastic integral is defined as the mean square limit, meaning somewhat loosely that the integral is the expected value of the sum of the squared product of the volatility times the change in the stochastic variable. Such a limit will exist for the processes we typically encounter in finance. In this sense, a stochastic integral is much more like a volatility measure. More formally, the stochastic integral known as the Ito integral can be expressed as

$$
\int_{0}^{t}\sigma(x_{j},t)d x_{j},
$$

and in limit form is the following,

$$
\operatorname*{lim}_{n\to\infty}E\left[\sum_{k=1}^{n}\sigma\big(x_{k-1},k\big)\big(x_{k}-x_{k-1}\big)\right].
$$

The mean squared difference is then zero,

$$
\operatorname*{lim}_{n\to\infty}E{\left[\sum_{k=1}^{n}\sigma\left(x_{k-1},k\right)\left(x_{k}-x_{k-1}\right)-\int_{0}^{t}\sigma\left(x_{j},j\right)d x_{j}\right]}^{2}=0.
$$

Remember that in the ordinary integral, the analogous expression is that the limit of the area of the rectangles equals the integral. For a stochastic integral, we must define this notion a little differently, in terms of expectations of squared differences.

Conveniently, some of the properties of ordinary integration are consistent with stochastic integration. For example, by definition,

$$
\int_{0}^{t}d x_{j}=x_{t}-x_{0}.
$$

In other words, whether $x$ is stochastic or not, the sum of the changes in $x$ from $x_{0}$ to $x_{t}$ is, by definition, $\boldsymbol{x}_{t}-\boldsymbol{x}_{0}$ . In the special case where the volatility is constant, that is, $\sigma_{x,t}=\sigma$ for all $t$ , we can pull the constant out and obtain

$$
\int_{0}^{t}\sigma d x_{j}=\sigma\left(x_{t}-x_{0}\right).
$$
