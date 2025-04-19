---
tags:
  - '#brownian_motion'
  - '#compound_option_pricing'
  - '#correlation'
  - '#covariance'
  - '#probability_density'
  - '#random_walk'
  - '#stochastic_integral'
  - '#stochastic_process'
  - '#variance'
  - '#wiener_process'
---
# 16.2 MOVING FROM A DISCRETE TO A CONTINUOUS WORLD

It is possible to demonstrate quite formally that if we hold $t$ fixed and increase $_n$ , in the limit, the random component, $\pm1$ , will converge to a standard normal random variable, which of course has expected value of 0 and variance of 1.6 In that case, our model is as follows:

$$
\begin{array}{r}{d{\mathbb{W}}_{t}=\varepsilon_{t}\sqrt{d t}\qquad}\ {\quad\boldsymbol{t}\qquad}\ {\mathbb{W}_{t}=\displaystyle\int d\mathbb{W}_{s}.}\end{array}
$$

If we substitute the first equation into the second, the integral looks somewhat strange due to the square root term. This integral is no longer a standard Riemann integral but is instead a stochastic integral. We treated these integrals in Chapter 11, and as it turns out, with constant variance, a stochastic integral of this form is more or less the same as a Riemann integral. Therefore, we can say quite comfortably that with $W_{0}=0$

$$
\mathrm{\mathrm{W}}_{t}=\int_{0}^{t}d\mathrm{W}_{s}=\mathrm{W}_{t}-\mathrm{\mathrm{W}}_{0}=\mathrm{\mathrm{W}}_{t}.
$$

This result would appear to hold by definition, but a formal proof requires the tools of. stochastic integration, which requires defining the integral, not in terms of a limit of an absolute difference but rather the expectation of a mean squared difference. Of course, we covered this in Chapter 11.

The variable $\mathbb{W}_{t}$ is a Brownian motion. Recall the requirements for a Brownian motion are as follows:

The process commences at zero $W_{0}=0$ ) and is continuous..
The random variable is normally distributed with an expectation of zero and variance of $t$ over time $t$
The increments, $W_{t+d t}-W_{t}=\Delta W_{t}$ are independent and normally distributed.

As noted, this process is also sometimes called a Wiener process, hence the W notation. Some experts make slight distinctions between Brownian motion and Wiener processes. Some even refer to $\mathbb{W}_{t}$ as the Brownian motion and $d\mathbb{W}_{t}$ as the Wiener process. Technically, our discrete time model is not a Brownian motion; it is often just referred to as a random walk.

We covered these points in Chapter 10 but let us review them here. Remember that $\varepsilon_{t}\sim N(0,1)$ , SO

$$
E\left(d W_{t}\right)=E\left(\varepsilon_{t}{\sqrt{d t}}\right)={\sqrt{d t}}E\left(\varepsilon_{t}\right)=0
$$

$$
\mathrm{~}\mathrm{{r}\left(\it{d W}_{t}\right)=\mathrm{{var}\left(\it{\varepsilon}_{t}\sqrt{\it{d t}}\right)=\it{d t v a r}\left(\it{\varepsilon}_{t}\right)=\it{d t}}}
$$

$$
E{\left(\mathrm{W}_{t}\right)}=E\left(\intop_{0}^{t}d\mathrm{W}_{j}\right)=\intop_{0}^{t}E\left(d\mathrm{W}_{j}\right)=0
$$

$$
\operatorname{var}\left(W_{t}\right)=\operatorname{var}\left(\intop_{0}^{t}d\mathrm{W}_{j}\right)=\intop_{0}^{t}\operatorname{var}\left(d\mathrm{W}_{j}\right)=\intop_{0}^{t}d j=t.
$$

For the last line, note that because the increments are independent, all covariances between $d\mathbb{W}_{\mathrm{j}}$ and $d\mathbb{W}_{k}$ are zero, $j\neq k$

Now suppose we are interested in the covariance between overlapping Brownian motions, $W_{s}$ and $\mathbb{W}_{t}$ where $t>s$ . Recall due to time series independence, we have.

$$
\begin{array}{r l}{{\mathrm{cov}}\left({{\mathbb{V}}_{t}},{\mathbb{W}_{t}}\right)={\mathrm{cov}}\left({{\mathbb{V}}_{0}}+\displaystyle\int_{0}^{s}{d}{\cal W}_{r},{\mathbb{W}_{0}}+\displaystyle\int_{0}^{t}{d}{\mathbb{W}_{r}}\right)}\ {={\mathrm{cov}}\left({{\mathbb{V}}_{0},{\mathbb{V}_{0}}}\right)+{\mathrm{cov}}\left({{\mathbb{W}_{0}},\displaystyle\int_{0}^{t}{d}{\mathbb{W}_{r}}}\right)+{\mathrm{cov}}\left(\displaystyle\int_{0}^{s}{d}{\mathbb{W}_{r}},{\mathbb{W}_{0}}\right)+{\mathrm{Cov}}\left(\displaystyle\int_{0}^{s}{d}{\mathbb{W}_{r}}\right)}\ {=0+0+0+{\mathrm{cov}}\left(\displaystyle\int_{0}^{s}{d}{\cal W}_{r},\displaystyle\int_{0}^{t}{d}{\mathbb{W}_{r}}\right)={\mathrm{cov}}\left(\displaystyle\int_{0}^{s}{d}{\cal W}_{r},\displaystyle\int_{0}^{s}{d}{\cal W}_{r}+\displaystyle\int_{0}^{t}{d}{\cal W}_{r}\right)}\ {={\mathrm{cov}}\left(\displaystyle\int_{0}^{s}{d}{\cal W}_{r},\displaystyle\int_{0}^{s}{d}{\cal W}_{r}\right)+{\mathrm{cov}}\left(\displaystyle\int_{0}^{s}{d}{\cal W}_{r}\displaystyle\int_{s}^{t}{d}{\cal W}_{r}\right)={\mathrm{cov}}\left(\displaystyle\int_{0}^{s}{d}{\cal W}_{r},\displaystyle\int_{0}^{s}{d}{\cal W}_{r}\right).}\ {=s.}\end{array}
$$

Because the correlation is defined as the covariance divided by the product of the standard deviations, the correlation between $W_{s}$ and $\mathbb{W}_{t}$ would be

$$
\rho\big(\mathrm{W}_{s},\mathrm{W}_{t}\big)=\frac{s}{\sqrt{s}\sqrt{t}}=\sqrt{s/t}.
$$

This seemingly minor result turns out to play a major role in compound option pricing models where it is necessary to determine a correlation for the underlying asset price on two dates, with the asset price driven by the value of $\boldsymbol{W}$ on the two dates. We shall cover compound options in Chapter 18.

Now let us look at the probability density for $\mathbb{W}_{t}$ . We know that in general, a normally distributed random variable $x$ with mean $\mu$ and variance $\sigma^{2}$ has a density of

$$
f(x)={\frac{1}{\sqrt{2\pi\sigma^{2}}}}e^{-{\frac{1}{2}}\left({\frac{x-\mu}{\sigma}}\right)^{2}}.
$$

What we know about. $\mathbb{W}_{t}$ is that it is normally distributed with $\mu=0$ and $\sigma^{2}=t$ Thus, its. density is

$$
f\big(W_{t}\big)=\frac{1}{\sqrt{2\pi t}}e^{-\frac{1}{2}\Big(\frac{W_{t}^{2}}{t}\Big)}.
$$

We also know that. $d\mathbb{W}_{t}$ is normally distributed with $\mu=0$ and $\sigma^{2}=d t$ Thus, its density is.

$$
f\left(d\mathrm{W}_{t}\right)=\frac{1}{\sqrt{2\pi d t}}e^{-\frac{1}{2}\left(\frac{d\mathrm{W}_{t}}{\sqrt{d t}}\right)^{2}}.
$$

Because we know that $d\mathbb{W}_{t}=\varepsilon_{t}{\sqrt{d t}}$ we can substitute into Equation (16.20) and obtain

$$
f\left(d\mathrm{W}_{t}\right)=\frac{1}{\sqrt{2\pi d t}}e^{-\frac{1}{2}{\varepsilon_{t}}^{2}}.
$$

Now consider two distinct Brownian motions, $\mathrm{W}_{x}$ and $W_{y}$ . Let us examine a new process that is a product of these two processes, specifically, $d\dot{\mathbb{W}}_{x}d\mathbb{W}_{y}$ . We know that the two increments are defined as

$$
\begin{array}{r}{d{\mathrm{W}}_{x}={\varepsilon}_{x}\sqrt{d t}}\ {d{\mathrm{W}}_{y}={\varepsilon}_{y}\sqrt{d t}.}\end{array}
$$

Now let us find the variance of their product. By definition var. $\left(d\mathbb{W}_{x}d\mathbb{W}_{y}\right)=$ $E\left[(d W_{x}d W_{y})^{2}\right]-\left[E\left(d W_{x}d W_{y}\right)\right]^{2}$ .Then $E\left(d W_{x}d W_{y}\right)=E\left(\varepsilon_{x}\sqrt{d t}\varepsilon_{y}\sqrt{d t}\right)=d t E\left(\varepsilon_{x}\varepsilon_{y}\right).$ Now use the definition of covariance, $\begin{array}{r}{\mathrm{cov}\left(\varepsilon_{x},\varepsilon_{x}\right)=E\left(\varepsilon_{x}\varepsilon_{x}\right)-E\left(\varepsilon_{x}\right)E\left(\varepsilon_{y}\right).}\end{array}$ which here reduces to. $E\left(\varepsilon_{x}\varepsilon_{x}\right)$ because the expectation of each $\varepsilon$ is zero. Now consider the correlation between the processes $\varepsilon_{x}$ and $\varepsilon_{y}$ , which shall be denoted as $\rho_{x y}$ . Because correlation is the covariance divided by the product of the standard deviations, then $\operatorname{cov}(\varepsilon_{x},\varepsilon_{x})=\rho_{x y}$ because the two standard deviations are each 1.0. So, $E\left(\varepsilon_{x}\varepsilon_{x}\right)=\rho_{x y}.$ So $E\left(d W_{x}d W_{y}\right)=\rho_{x y}d t$ But we want the square of this value. Obviously, this square is. zero because we have ${\rho_{x y}}^{2}d t^{2}$ and $d t^{2}$ goes to zero in the limit. It follows that the second. term in the variance definition, $\left[E\left(d W_{x}d\mathrm{W}_{y}\right)\right]^{2}$ goes to zero because it is $(\rho_{x y}d t)^{2}$ . Thus,

$$
\mathrm{var}\left(d\mathrm{W}_{x}d\mathrm{W}_{y}\right)=0.
$$

If the variance is zero, then

$$
E\left(d W_{x}d W_{y}\right)=d W_{x}d W_{y}=\rho_{x y}d t.
$$

So we see that the product of two Brownian motions is non-stochastic.

Mathematicians often refer to the derivative with respect to time, in this case $d\mathbb{W}_{t}/d t$ as the velocity. For Brownian motion, however, the velocity does not exist, as shown here:

$$
{\frac{d W_{t}}{d t}}=\operatorname*{lim}_{\Delta t\to0}{\frac{\Delta W_{t}}{\Delta t}}=\operatorname*{lim}_{\Delta t\to0}{\frac{\varepsilon_{t}\sqrt{\Delta t}}{\Delta t}}=\operatorname*{lim}_{\Delta t\to0}{\frac{\varepsilon_{t}}{\sqrt{\Delta t}}}\to\pm\infty.
$$

The intuition is that Brownian motion is characterized by infinitesimally small zig-zags.. We cannot take limits while permitting the time increment to shrink. For a derivative to exist, we must be able to take a limit, meaning that the line drawn tangent to the point. where we are taking the derivative must converge to a stable value, and this simply does not occur here. This result is, however, not a problem. We shall never need the derivative $d\mathbb{W}_{t}/d t$

Perhaps the most important characteristic of the process $\mathbb{W}_{t}$ is the property that its squared increment is no longer stochastic. We covered this point previously but let us review it here. Consider the squared variable $d\mathbb{W}_{t}^{2}$ . Let us take its expectation,

$$
E\left(d{\cal W}_{t}^{2}\right)=E\left[(\varepsilon_{t}\sqrt{d t})^{2}\right]=d t E(\varepsilon_{t}^{2})=d t,
$$

which results from the fact that var $\left(\varepsilon_{t}\right)=E\left(\varepsilon_{t}^{2}\right)-[E\left(\varepsilon_{t}\right)]^{2}=1$ . But $E\left(\varepsilon_{t}\right)$ is zero, so $E\left(\varepsilon_{t}^{2}\right)=\mathrm{var}\left(\varepsilon_{t}\right)=1$

Now let us take the variance of $\boldsymbol{d}\boldsymbol{\mathbb{W}}_{t}^{2}$

$$
\begin{array}{r l}&{\mathrm{var}\left(d\boldsymbol{W}_{t}^{2}\right)=E\left[(d\boldsymbol{W}_{t}^{2})^{2}\right]-\left[E\left(d\boldsymbol{W}_{t}^{2}\right)\right]^{2}}\ &{\quad\quad\quad=E\left[(\varepsilon_{t}^{2}d t)^{2}\right]-\left[E\left(\varepsilon_{t}^{2}d t\right)\right]^{2}}\ &{\quad\quad\quad=d t^{2}E\left(\varepsilon_{t}^{4}\right)-d t^{2}}\ &{\quad\quad\quad=0.}\end{array}
$$

A key element of this result is remembering that in the limit $d t^{k}\to0$ for all $k>1$

We shall eventually be interested in generalizing our Brownian motion so that it has a nonzero mean and a variance other than $t$ Technically, this would no longer be a Brownian motion, but it is often still referred to in this manner. Suppose we wish to create a stochastic process, $x_{t}$ , in which the increment,. $d\boldsymbol{x}_{t}$ , has mean $\mu$ and variance $\sigma$ . Then we simply do. the following: Let the process be defined as

$$
d x_{t}=\mu d t+\sigma d W_{t}.
$$

The properties of this process are

$$
E\left(d x_{t}\right)=\mu d t\mathrm{and}\mathrm{var}\left(d x_{t}\right)=\sigma^{2}d t.
$$

The latter result arises because the variance of $\sigma d\boldsymbol{W}_{t}$ is the constant $\sigma^{2}$ times the variance of $d\mathbb{W}_{t}$ , which is. $d t$ . The process, $x_{t}$ , defined by the stochastic integral

$$
{x}_{t}={x}_{0}+\intop_{0}^{t}d{x}_{j},
$$

would have the properties

$$
E\left(x_{t}\right)=x_{0}+E\left(\intop_{0}^{t}d x_{j}\right)=x_{0}+\intop_{0}^{t}E\left(d x_{j}\right)=x_{0}+\intop_{0}^{t}\mu d j=x_{0}+\mu t
$$

$$
\operatorname{var}\left(x_{t}\right)=\operatorname{var}\left(\intop_{0}^{t}d x_{j}\right)=\intop_{0}^{t}\operatorname{var}\left(d x_{t}\right)=\operatorname{var}\left(\intop_{0}^{t}\sigma^{2}d j\right)=\sigma^{2}t.
$$

Note that there are no covariance terms for $d\boldsymbol{x}_{t}$ in the variance expression in the last line because the $d\boldsymbol{x}_{t}$ values are independent.

These results give $x_{t}$ more general characteristics and enable us to use it to model more realistic phenomena, such as stock prices, exchange rates, and so on.
