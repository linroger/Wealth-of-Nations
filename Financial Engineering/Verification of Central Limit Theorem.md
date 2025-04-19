---
tags:
  - central_limit_theorem
  - distribution_function
  - moment_generating_function
  - random_variables
  - standard_normal_distribution
aliases:
  - CLT Verification
  - Central Limit Theorem Proof
key_concepts:
  - Distribution function
  - Independent random variables
  - Moment generating function
  - Random variable mean
  - Random variable variance
  - Standard normal distribution
  - Taylor series expansion
---

# Chapter 2 Additional Readings  

# A Verification of the Central Limit Theorem  

Central Limit Theorem: If. $\{X_{I},X_{2},\ldots\}$ is a set of independent and identically distributed random variables with mean. $\mu$ and standard deviation $\sigma,$ then the distribution function for the random. variable  

$$
Z_{n}={\frac{{\bar{X}}-\mu}{\sigma/{\sqrt{n}}}}
$$  

approaches the distribution function for the standard normal distribution as $n\to\infty$ where the sample mean random variable is defined as X = Ei-1 Xi.  

Proof: We start by proving that the moment generating function (defined shortly) of the random. variable $Z_{n}$ approaches the moment generating function of the standard normal random variable $Z$ as $n$ approaches infinity. The point is that the moment generating function of a random. variable uniquely determines the distribution function of the random variable, although we will not prove this fact. Some details in this prove will not be completely rigorous, since a rigorous proof is beyond the level of this text..  

The moment generating function $M_{X}(t)$ of a random variable. $X$ is defined to be the. expectation of the random variable $e^{X t}\colon M_{X}(t)=E[e^{X t}]$ where $t$ can be any real number. Since.  

$$
{\frac{1}{\sqrt{2\pi}}}e^{-z^{2}/2}
$$  

is the density function for the standard normal random variable $Z.$ then moment generating function of $Z$ is:  

$$
\begin{array}{r}{M_{Z}(t)=E[e^{Z t}]=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty}e^{-z^{2}/2}e^{z t}d z.}\end{array}
$$  

Completing the square, we have  

$$
\begin{array}{r}{-\frac{1}{2}z^{2}+z t=-\frac{1}{2}(z-t)^{2}+\frac{1}{2}t^{2}.}\end{array}
$$  

Substituting the right side of equation (2) into the right side of equation (1) yields  

$$
M_{Z}(t)=\frac{1}{\sqrt{2\pi}}e^{t^{2}/2}\int_{-\infty}^{\infty}e^{-(z-t)^{2}/2}d z.
$$  

Making the change of variables $u=z-t$ results in  

$$
\begin{array}{r}{M_{Z}(t)=\frac{1}{\sqrt{2\pi}}e^{t^{2}/2}\int_{-\infty}^{\infty}e^{-u^{2}/2}d u=e^{t^{2}/2}.}\end{array}
$$  

# Chapter 2 Additional Readings  

To obtain the final expression on the right side of equation (3), we used the fact that  

$$
{\frac{1}{\sqrt{2\pi}}}\int_{-\infty}^{\infty}e^{-u^{2}/2}d u=1
$$  

since $e^{-u^{2}/2}/{\sqrt{2\pi}}$ is the density function for the standard normal random variable. We have left to show that $M_{Z_{n}}(t)\to e^{t^{2}/2}$ as $n\to\infty$ . We can express  

$$
Z_{n}={\frac{{\bar{X}}-\mu}{\sigma/{\sqrt{n}}}}={\frac{\sum_{i=1}^{n}(X_{i}-\mu)}{\sigma{\sqrt{n}}}}.
$$  

Thus, the moment generating function for $Z_{n}$ is:  

$$
M_{Z_{n}}(t)=E\left[e^{\frac{t\sum_{i=1}^{n}\left(X_{i}-\mu\right)}{\sigma{\sqrt{n}}}}\right].
$$  

Since the $X_{i}^{\prime}s$ are independent random variables, then $Z_{n}$ has the density function $p(x_{1})p(x_{2})\cdots p(x_{n})$ where $p(x_{i})$ is the density function for the random variable $X_{i}$ . Referring to equation (4), we can express the moment generating function in the form  

$$
M_{Z_{n}}(t)=\int\displaylimits_{-\infty}^{\infty}\int\displaylimits_{-\infty}^{\infty}\cdots\int\displaylimits_{-\infty}^{\infty}e^{\frac{t\sum_{i=1}^{n}(x_{i}-\mu)}{\sigma\sqrt{n}}}p(x_{1})p(x_{2})\cdots p(x_{n})d x_{1}d x_{2}\cdots d x_{n}
$$  

$$
\begin{array}{r l}&{=\left[\int_{--\infty}^{\infty}e^{\frac{(x_{1}-\mu)t}{\sigma\sqrt{n}}}p(x_{1})d x_{1}\right]\left[\int_{--\infty}^{\infty}e^{\frac{(x_{2}-\mu)t}{\sigma\sqrt{n}}}p(x_{2})d x_{2}\right]\cdots\left[\int_{--\infty}^{\infty}e^{\frac{(x_{n}-\mu)t}{\sigma\sqrt{n}}}p(x_{n})d x_{n}\right].}\end{array}
$$  

From Taylor series, we know that $\begin{array}{r}{e^{x}=1+x+\frac{1}{2}x^{2}+\frac{1}{3!}x^{2}+\frac{1}{4!}x^{2}+\cdots.}\end{array}$ Hence, for each $i=1,2,\dots,n$ we have:  

$$
\begin{array}{r l}&{\int_{-\infty}^{\infty}e^{\frac{\left(x_{i}-\mu\right)t}{\sigma\sqrt{n}}}p(x_{i})d x_{i}=\int_{--\infty}^{\infty}[1+\frac{(x_{i}-\mu)t}{\sigma\sqrt{n}}+\frac{(x_{i}-\mu)^{2}t^{2}}{2\sigma^{2}n}+\frac{(x_{i}-\mu)^{3}t^{3}}{6\sigma^{3}n^{3/2}}\cdots]p(x_{i})d x_{i}}\end{array}
$$  

Since $p(x_{i})$ is the density function for a random variable with mean $\upmu$ and variance $\upsigma^{2}$ , then we know  

$$
\begin{array}{r}{\int_{-\infty}^{\infty}p(x_{i})d x_{i}=1,\int_{-\infty}^{\infty}x_{i}p(x_{i})d x_{i}=\mu,a n d\int_{-\infty}^{\infty}(x_{i}-\mu)^{2}p(x_{i})d x_{i}=\sigma^{2}.}\end{array}
$$  

Although we don't know the precise values of the following integrals, we can say that  

$$
\begin{array}{r}{\int_{-\infty}^{\infty}(x_{i}-\mu)^{k}p(x_{i})d x_{i}=C(k)}\end{array}
$$  

for some constants $C(k)$ that are independent of. $n$ for $k=3$ , 4, ... Based on equations (7) and (8), we rewrite equation (6) in the form:  

# Chapter 2 Additional Readings  

$$
\begin{array}{r}{\int_{-\infty}^{\infty}e^{\frac{(x_{i}-\mu)t}{\sigma\sqrt{n}}}p(x_{i})d x_{i}=1+\frac{t^{2}}{2n}+\frac{C(3)t^{3}}{6\sigma^{3}n^{3/2}}+\frac{C(4)t^{4}}{24\sigma^{4}n^{2}}+\cdots.}\end{array}
$$  

Notice that the right side of equation (9) is the same for every $i$ Substituting the right side of equation (9) into equation (5) yields  

$$
M_{Z_{n}}(t)=(1+\frac{t^{2}}{2n}+\frac{C(3)t^{3}}{6\sigma^{3}n^{3/2}}+\frac{C(4)t^{4}}{24\sigma^{4}n^{2}}+\cdots)^{n}.
$$  

Since  

$$
{\frac{C(3)t^{3}}{6\sigma^{3}n^{3/2}}}+{\frac{C(4)t^{4}}{24\sigma^{4}n^{2}}}+\cdots
$$  

is much smaller than $\frac{t^{2}}{2n}$ as $n\to\infty$ , then  

$$
M_{Z_{n}}(t)\to(1+\frac{t^{2}}{2n})^{n}
$$  

as $n\to\infty$ .We know from calculus that  

$$
\left(1+{\frac{a}{n}}\right)^{n}\to e^{a}
$$  

as $n\to\infty$ . Choosing $a{=}t^{2}/2$ this shows that  

$$
M_{Z_{n}}(t)\rightarrow e^{\frac{t^{2}}{2}}
$$  

as $n\to\infty$ as we set out to verify.  