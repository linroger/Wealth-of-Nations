---
tags:
  - financial_modeling
  - girsanov_theorem
  - probability_distribution
  - radon_nikodym
  - random_variable
aliases:
  - Changing Drift
  - Radon-Nikodym derivative
key_concepts:
  - Girsanov's theorem
  - expected value shift
  - normal distribution
  - probability density function
  - probability measure change
---

# 15.2 INTRODUCING THE RADON-NIKODYM DERIVATIVE BY CHANGINGTHE DRIFT FOR A SINGLE RANDOM VARIABLE

Let us begin by examining the process of changing a probability distribution for a general random variable. We start with a random variable $x$ , which is simply a single unknown outcome and not a stochastic process. We shall take $x$ as distributed normally with expected value $\mu$ and variance $\sigma^{2}$ . The probability density of $x$ is

$$
f(x)={\frac{1}{\sigma{\sqrt{2\pi}}}}e^{-{\frac{\left({\frac{x-\mu}{\sigma}}\right)^{2}}{2}}}={\frac{d\operatorname*{Pr}(x)}{d x}},
$$

where the probability distribution function or cumulative probability is $\mathrm{Pr}(x)$ . Now suppose that we wanted to change the location of this probability distribution. Specifically,

we wish to shift the expected value by an amount y, such that the expected value is $\mu+\gamma$ Then the density we want is.

$$
f(x)=\frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{\left(\frac{x-\mu-\gamma}{\sigma}\right)^{2}}{2}}.
$$

Note that the numerator of the exponent takes $x$ and subtracts our shifted expected value. $\mu+\gamma$

We have changed the expected value but not the variance, meaning that we have. changed the location but not the shape of the distribution. We need not specify if. $\gamma$ is positive or negative, because we could shift the expected value upward or downward. Let us call this new density $f^{\mathcal{Q}}(x)$ and the new distribution function $\mathrm{{Pr}}^{Q}(\mathbf{x})$ , so $f^{Q}(x)=d\mathrm{Pr}^{Q}(x)/d x$ Let us see how we can make this distribution change so that. $\Pr(x)$ is replaced by $\scriptstyle\operatorname*{Pr}^{Q}(x)$

Look at the expression in the previous exponent, $-[(x-\mu-\gamma)/\sigma]^{2}/2$ , and note that it equals $-(1/2\sigma^{2})(x^{2}-2x\mu-2\gamma x+2\mu\gamma+\mu^{2}-\gamma^{2})$ . If we compare this expression to what we started with, $-[(x-\mu)/\sigma]^{2}/2=-(1/2\sigma^{2})(x^{2}-2x\mu+\mu^{2})$ , we see that we can get the new expression by multiplying the original expression by a certain factor. That is,

$$
{\frac{1}{\sigma{\sqrt{2\pi}}}}e^{-{\frac{\left({\frac{x-\mu-\gamma}{\sigma}}\right)^{2}}{2}}}=\left({\frac{1}{\sigma{\sqrt{2\pi}}}}e^{-{\frac{\left({\frac{x-\mu}{\sigma}}\right)^{2}}{2}}}\right)\left(e^{-{\frac{(2\gamma x-2\gamma\mu-\gamma^{2})}{2\sigma^{2}}}}\right).
$$

Let us now designate this new multiplier as

$$
\phi(x)=e^{-\frac{(2\gamma x-2\gamma\mu-\gamma^{2})}{2\sigma^{2}}}.
$$

Because $f(x)=d\operatorname*{Pr}(x)/d x$ then. $f(x)d x=d\operatorname*{Pr}(x)$ What we want is $f^{Q}(x)d x=d\mathrm{Pr}^{Q}(x),$ where we have a new probability measure $\mathrm{Pr}^{Q}(x)$ .Because $f(x)\phi(x)=f^{Q}(x),$ then. $f(x)d x\phi(x)=f^{Q}(x)d x$ Then

$$
{\frac{f^{Q}(x)}{f(x)}}=\phi(x).
$$

It follows that

$$
{\frac{d\mathrm{Pr}^{Q}(x)}{d\mathrm{Pr}(x)}}={\frac{f^{Q}(x)d x}{f(x)d x}}=\phi(x).
$$

Our multiplier $\phi(x)$ can be thought of as an adjustment that converts one probability measure, $\Pr(x)$ , into another, $\mathrm{Pr}^{Q}(x)$ . We must be careful, however, in that one cannot just arbitrarily multiply one measure by some other factor because the resulting measure should be of the same type of distribution as the one we started with. In this case, we started with the normal distribution, and we end with the normal distribution but with a different expected value. In some cases, our random variable will be standard normal, meaning that $\mu=0$ and $\sigma=1$ . In that case,

$$
\phi(x)=e^{\frac{x\gamma-\gamma^{2}}{2}}.
$$

This special function. $\phi(\mathbf{x})$ , which we noted can be expressed as. $d\mathrm{Pr}^{Q}(x)/d\mathrm{Pr}(x)$ is a derivative itself and is called the Radon-Nikodym derivative. For this derivative to exist,. it is necessary that the function $\scriptstyle\operatorname*{Pr}^{Q}(x)$ and the function. $\Pr(x)$ be considered equivalent probability measures. What this means is that if an event is possible under one measure,. then it is possible under the other measure. In other words, events that cannot occur in the first place cannot be made possible by simply changing the probability measure. Likewise. events that can occur in the first place cannot be made impossible by changing the probability measure. The probability of a possible event, however, can and will be changed by this change of measure..

Before providing a formal statement of Girsanov's theorem, we introduce a complete. probability space with a particular interest in how it is applicable to financial modeling.
