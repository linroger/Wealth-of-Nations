---
tags:
  - '#binomial_distribution'
  - '#central_limit_theorem'
  - '#chebyshev_inequality'
  - '#law_of_iterated_expectations'
  - '#law_of_large_numbers'
  - '#law_of_total_probability'
  - '#lognormal_distribution'
  - '#normal_distribution'
  - '#poisson_distribution'
  - '#probability_distributions'
  - '#probability_theory'
---
# 4.4 SOME GENERAL RESULTS IN PROBABILITY THEORY

In the following subsections, we look at some of the general results from probability the-. ory that are helpful in option theory. By the term general, we mean that these results are not dependent on any particular probability distribution. When a specific probability dis-. tribution is known, usually a stronger statement can be made..

# 4.4.1 The Central Limit Theorem

The central limit theorem is a powerful statement that tells us that sum or average of. independent samples drawn from any given probability distribution becomes normally. distributed in the limit, that is, as the sample size approaches infinity. Thus, provided the. sample size is large enough, the central limit theorem enables us to use the rules associated with normal probability theory when drawing inferences about sample means. How large. the sample size must be to rely on the central limit theorem is not known, but a common rule of thumb has always been at least 30.

# 4.4.2 Chebyshev's Inequality

Chebyshev's inequality, sometimes called Chebyshev's theorem, enables us to make a some-. times useful statement about the probability of a sample value deviating from the population mean. More precisely, let $x$ be a random variable with mean $\mu$ and variance $\sigma^{2}$ , which can come from any probability distribution. For any real number $z>0$

$$
\operatorname*{Pr}(\left|x-\mu\right|\geq z\sigma)\leq{\frac{1}{z^{2}}},\operatorname{assuming}z\geq1.
$$

Thus, Chebyshev's theorem gives an upper bound on how much the observed value deviates from the mean in terms of an arbitrary value $z$ . For example, let $x$ be the average height in inches of a randomly drawn male university student. Let. $\mu=70$ and $\sigma=2$ . For $z$ equals various values, we have the following results:.

<html><body><table><tr><td></td><td></td><td>Maximum Pr(|x - μl ≥ zo)</td></tr><tr><td>5</td><td>10</td><td>0.04</td></tr><tr><td>4</td><td>8</td><td>0.0625</td></tr><tr><td>3</td><td>6</td><td>0.1111</td></tr></table></body></html>

In other words, the probability that a sample value will deviate from the mean by more than 10 inches is less than O.04. Thus, the probability that a student will be more than 80 inches (70 plus 10 inches) is less than $4\%$ . The probability that a student will be more than 78 inches (70 plus eight) is less than $6.25\%$ . The probability that a student will be more than 76 inches (70 plus six) is less than. $11.11\%$ . These rules hold for any distribution, though knowing the exact distribution usually enables one to make more precise. statements.11

# 4.4.3 The Law of Large Numbers

The law of large numbers provides information about the accuracy with which a sample. mean approximates a population mean. Basically, it says that the probability that the difference between the sample mean and the population mean is greater than an arbitrarily. chosen small value is zero because the sample size goes to infinity. This law holds as long. as the sample consists of independently selected random variables from the same distribution. The law of large numbers more or less says that if we take sufficiently large samples,. our sample mean estimate converges to the population mean..

# 4.4.4 The Law of Iterated Expectations (the Tower Law)

The law of iterated expectations, sometimes called the Tower law, is used to specify the expected value assessed at a given time $t$ in terms of an expected value at another time $t+i.$ which is taken as an expected value at a later time $t+j$ In other words, we are taking the expectation of an expectation. For example, suppose we are at time $t+i$ and are calculating the expected value at time $t+j$ . We might denote this as $E_{t+\mathrm{i}}(x_{t+j})$ , which simply means that using the information at time $t+i_{:}$ , we assess the expected value of $x$ to occur at a later time. $t+j$ . Now step back to time $t$ and try to assess the expected value at time $t+i$ In other words, we want. $E_{t}[E_{t+i}(x_{t+j})]$ . The law of iterated expectations simply says

$$
E_{t}\left[E_{t+i}\left(x_{t+j}\right)\right]=E_{t}\left(x_{t+j}\right).
$$

In other words, the expectation is iterated from the later time to the earlier time.

# 4.4.5 The Law of Total Probability

The law of total probability is a simple statement about the conditional probabilities and marginal probabilities. Specifically let $y$ and $x$ be random variables where $x$ is bifurcated into values greater than $b$ and less than or equal to $b$ . Then the law of total probability states that

$$
\operatorname*{Pr}(y)=\operatorname*{Pr}(y|x>b)\operatorname*{Pr}(x>b)+\operatorname*{Pr}(y|x\leq b)\operatorname*{Pr}(x\leq b).
$$

The statement $\Pr(y)$ is simply any specification of $y$ , such as $\operatorname*{Pr}(y>k)$ or $\operatorname*{Pr}(a\leq y\leq k)$ So, the probability of any event associated with $y$ can be broken down into the probability of that event for $y$ , conditional on an event occurring for $x$ , and the probability of that event for $y$ , conditional on that event not occurring for $x$

# 4.5TECHNICAL INTRODUCTION TO COMMON PROBABILITY DISTRIBUTIONS USED IN FINANCE

Numerous financial challenges are addressed with the use of common probability distributions. As noted previously, probability distributions are either discrete or continuous..

Discrete distributions have a countable set of possible outcomes, such as flipping a. coin, where each outcome has a nonnegative chance of occurring and the sum of the probability of all outcomes is equal to one. More formally, for a discrete probability function,. $p_{X}(a)$ , the following properties hold for a specific value,. $x$

$\operatorname*{Pr}(x=a)=p_{X}(a)$ [Read: The probability that $X$ is a specific value, $x=a$ , is $p_{X}(a)$ 1 $\begin{array}{r}{\displaystyle p_{X}(\boldsymbol{x})\geq0\forall\boldsymbol{x}}\end{array}$ [Read: The probability is nonnegative for all possible outcomes $x$ 1 $N$ $\sum_{j=1}{p_{X}(x_{j})}=1$ . [Read: The sum of the probabilities over all possible values of $x$ is 1.]

Discrete probability distributions covered here include the binomial and Poisson distributions.

Continuous distributions have an infinitesimal probability of achieving any particular. outcome, whereas the likelihood of achieving a value within a defined range of outcomes. is measurable. Finally, the integral over the range of all outcomes is equal to one. More formally, for a continuous probability function, $\boldsymbol{p}_{c}(\boldsymbol{x})$ , the following properties hold:

$_{x=b}$ $\begin{array}{r}{\operatorname*{Pr}(a\leq x\leq b)=\int_{x=a}p_{c}(x)d x}\end{array}$ . [Read: The probability that $x$ takes a value in a range of a through b.].

$\operatorname*{Pr}(a\leq x\leq b)\geq0\forall a\leq b$ [Read: The probability is nonnegative for all possible ranges of $a$ through $b$ 1

$x{=}+\infty$ $\begin{array}{r}{\operatorname*{Pr}(-\infty\leq x\leq+\infty)=\int\fint_{x=-\infty}{p_{c}(x)d x}=1.}\end{array}$ [Read: The integral over all possible values of $x$ is 1.]

Continuous probability distributions covered here include the normal and lognormal distributions.

# 4.5.1 Binomial Distribution

The binomial distribution is used to model situations involving two random outcomes, such as a coin toss. Thus, this discrete probability distribution is binary, derived from the Latin root bi meaning "two." The -nomial extension is derived from Latin, meaning "name." Thus, the binomial distribution is based on two names, such as true and false, heads or tails, 1 or 0, up or down, and so forth. We often select one of the names to be success and the other name to be failure. The binomial distribution is a two-parameter distribution, with parameters $_n$ and $\boldsymbol{p}$ . The parameter $_n$ denotes the number of independent events. In finance, $_n$ is often the number of time steps, such as 252 for number of trading. days in one particular year. The parameter. $\boldsymbol{p}$ denotes the probability of observing a success,. such as true, heads, 1, up, and so on. In finance,. $p$ is often the probability that a financial instrument will go up over the next time step..

The possible outcomes from a binomial distribution range from O to $_n$ , such as the number of observed up events over $_n$ days, where each event has probability $p$ of success. The binomial distribution is therefore denoted. $B(n,p)$ . If $x$ is said to have a binomial distribution, then the probability mass function can be expressed as12.

$$
b(i,n,\boldsymbol{\phi})=\mathrm{Pr}(i;n,\boldsymbol{\phi})=\mathrm{Pr}(x=i)=\binom{n}{i}p^{i}(1-p)^{n-i},
$$

for all $i=0,1,2,\ldots,n.$ where the combination of $_n$ events with. $i$ successes is defined as.

$$
{\binom{n}{i}}={\frac{n!}{i!(n-i)!}},
$$

and $_n$ denotes factorial or $n(n-1)(n-2)\dots(2)1$ . The combination of $_n$ events with $i$ successes identifies the number of different ways of observing $i$ successes over $_n$ events.

The cumulative distribution function (CDF) can be expressed as

$$
B(j;n,\boldsymbol{\phi})=\operatorname*{Pr}(x\leq j)=\sum_{i=0}^{j}{\binom{n}{i}}p^{i}(1-p)^{n-i}.
$$

The mean is $n(p)$ and the variance is $n(\boldsymbol{p})(1-\boldsymbol{p})$ . We will explore this distribution in greater detail in Chapter 7.

# 4.5.2 Poisson Distribution

The Poisson distribution is used to model countable outcomes, such as the number of companies registered in a particular year. This distribution is named after Simeon Denis Poisson (1781-1840), although Abraham de Moivre (1711) appears to be the first to develop it. The Poisson is also a discrete probability distribution. In finance, the Poisson distribution is used when one is interested in the number of times a particular event happens during a specified time span. This distribution assumes that the occurrence of one event does not affect the likelihood of observing another event as well as assumes the average number of events is constant.

The possible outcomes from a Poisson distribution are the integers from O to $\infty$ , such as the number of bankruptcies observed in a given year. The Poisson distribution requires only one parameter, the average number of observed outcomes during an interval of time, denoted $\lambda$ . Thus, the Poisson distribution is denoted $P D(\lambda)$ . If $\mathbf{x}$ is said to have a Poisson distribution, then the probability mass function can be expressed as

$$
p m(i,\lambda)=\operatorname*{Pr}(i;\lambda)=\operatorname*{Pr}(x=i)=\frac{\lambda^{i}e^{-\lambda}}{i!},
$$

for all $i=0,1,2,\ldots,\infty$

The cumulative distribution function (CDF) can be expressed as

$$
P M(j;\lambda)=\operatorname*{Pr}(x\leq j)=e^{-\lambda}\sum_{i=0}^{j}{\frac{\lambda^{i}}{i!}}.
$$

The mean and variance are both $\lambda$

# 4.5.3 Normal Distribution

The normal distribution is one of the most well-known of all distributions and is widely used in finance; hence, we devote the entire Chapter 5 to it. We provide a brief technical introduction here. The range of a variable, $x.$ , that follows a normal distribution is $-\infty<$ $x<+\infty$ . It is a symmetric two-parameter distribution typically identified with the mean, $\mu$ , and standard deviation,. $\sigma$ . The range for the mean is therefore. $-\infty<\mu<+\infty$ and the range for the standard deviation is $\sigma>0$ . If $x$ is said to have a normal distribution, then the probability density function (PDF) can be expressed as

$$
n(x)={\frac{1}{\sigma{\sqrt{2\pi}}}}e^{-{\frac{(x-\mu)^{2}}{2\sigma^{2}}}}.
$$

The PDF is the derivative of the cumulative distribution function. The CDF, assuming $-\infty<a<+\infty$ , can be expressed as

$$
N(a)=\int_{x=-\infty}^{a}n(x)d x=\int_{x=-\infty}^{a}{\frac{1}{\sigma{\sqrt{2\pi}}}}e^{-{\frac{(x-\mu)^{2}}{2\sigma^{2}}}}d x.
$$

The CDF range is $0\leq N(a)\leq1$ and provides the probability that an outcome is less than or equal to $a$ . The PDF is simply the first derivative of the CDF.

We briefly identify several location statistics related to the normal distribution. The median is defined as the $\widehat{x}$ such that $\stackrel{\widehat{x}}{\underset{-\infty}{\int}}f(x)d x=\stackrel{+\infty}{\underset{\widehat{x}}{\int}}f(x)d x=\frac{1}{2}$ for any PDF $f(x)$ . For the normal distribution, the median is equal to. $\mu$ (a constant). The mode is defined as the. $\widehat{x}$ Such that $\begin{array}{r}{\frac{d f(x)}{d x}=0}\end{array}$ and $\begin{array}{r}{\frac{d^{2}f(x)}{d x^{2}}<0}\end{array}$ for any PDF For the normal distributin, the mode is also equal to $\mu$

With statistical distributions, the $n^{t b}$ noncentral moment is defined as ${\mu_{n}}^{\prime}(x)=E(x^{n})$ and the $n^{t b}$ central moment is defined as $\mu_{n}(x)=E[(x-\mu)^{n}]$ . The first noncentral moment is the mean or

$$
M e a n={\mu_{1}}^{\prime}(x)=\mu.
$$

The mean is a constant and the first central moment is zero or $\mu_{1}(x)=0$ . The second central moment is the variance or

$$
V a r i a n c e=\operatorname{var}(x)=\mu_{2}(x)=\sigma^{2}.
$$

The variance is a constant and the second noncentral or raw moment is $\mu_{2}{}^{\prime}(x)=\mu^{2}+\sigma^{2}$ The third central moment is the skewness or

$$
S k e w n e s s=\mu_{3}(x)=0.
$$

Skewness of zero implies a symmetric distribution. The third noncentral moment is $\mu_{3}{}^{\prime}(x)=\mu^{3}+3\mu\sigma^{2}$ . The fourth central moment is the kurtosis or.

$$
K u r t o s i s=\mu_{4}(x)=3\sigma^{4}.
$$

Note that the fourth moment is positive and a function of variance. The fourth noncentral Or raw moment is $\mu_{4}{}^{\prime}(x)=\mu^{4}+6\mu^{2}\sigma^{2}+3\sigma^{4}$ Kurtosis is often normalized by the variance squared. Thus, the kurtosis of the normal distribution is 3 and is known as mesokurtic..

Figures $4.1\mathrm{a}{-}\mathrm{h}$ illustrate both the probability density function as well as the cumulative distribution function of the normal distribution applied to some financial instrument price. The following series of figures illustrates the effect of increases in the standard deviation because different financial instruments have different levels of standard deviation. One common challenge is misinterpreting high standard deviation instruments, particularly when applying the lognormal distribution, which we cover next.

We see from these graphs that with the normal distribution, there is a nonzero probability that the underlying instrument value can fall below zero. Financial derivative instru-. ments can often themselves take on negative values. Negative value is very common for symmetric derivatives such as forwards, futures, and swaps as well as short positions in asymmetric derivatives such as options, swaptions, caps, and floors. For example, the short position for any option cannot be positive as it can only result in a future liability. A call option price may be 14, but to the writer it is a liability of 14 and hence has a negative. value. Because common stock has limited liability, we expect the stock price to remain nonnegative. Limited liability can be viewed as a company obtaining a long put option. contract with a zero strike price. Clearly, company assets can obtain a negative value, such. as is the case with environmental damage or company products found to be carcinogenic.. Again, more extensive details on the normal distribution are given in Chapter 5. To address some of these challenges, many financial models are built on the lognormal distribution.

![](images/5fccc7da129f093142cf7f5193a8273d4f4625d630605828c2d6194015950094.jpg)
FIGURE 4.1a Normal Probability Density Function $\mu=0\%$ $\sigma=30\%$

![](images/e99b4bae5da485fce7df5c46ff76b67f43d12d2fed3dd522f87c9f4c439aafb3.jpg)
FIGURE 4.1b Normal Cumulative Distribution Function $\mu=0\%$ $\sigma=30\%$

![](images/467bbfb2900fc6e68e8ee855bb1c76a2f08b4abf14435d2e3c8194d454be1cac.jpg)
FIGURE 4.1c Normal Probability Density Function $\mu=0\%$ $\sigma=80\%$

![](images/5d37aeef3ba1b4fe9587cc0d251416b3c6f880ece7cbd2c3d464dbfbf89e7b4c.jpg)
FIGURE 4.1d Normal Cumulative Distribution Function $\mu=0\%$ $\sigma=80\%$

![](images/4a219b9a629aadff37ac3510cd4836c09a65bcaee7921795ae9bb0aa31573ae9.jpg)
FIGURE 4.1e Normal Probability Density Function $\mu=0\%$ $\sigma=130\%$

![](images/4f0ff57d2a978769a280105aef7dfaf3a2db9e632529dcf66af3488c414b5163.jpg)
FIGURE 4.1f Normal Cumulative Distribution Function $\mu=0\%$ $\sigma=130\%$

![](images/87989e441942957ddd6338f5c04846d78c59cb9e80473c35b9cfd67e2f956637.jpg)
FIGURE 4.1g Normal Probability Density Function $\mu=0\%$ $\sigma=800\%$

![](images/3ccd2ce2ee0ab1d04a6ba7243b5272dfad485c65ea14cb8ccf80db1c08d882d4.jpg)
FIGURE 4.1h Normal Cumulative Distribution Function $\mu=0\%$ $\sigma=800\%$

# 4.5.4 Lognormal Distribution

The lognormal distribution is related to the normal distribution in the following way: If $y=\ln(x)$ is normally distributed, $x$ is said to be lognormally distributed. It is an asymmetric two-parameter distribution again identified with the implied normal distribution's mean, $\mu$ , and standard deviation, $\sigma$ . The range for the mean is $-\infty<\mu<+\infty$ and the range for the standard deviation is $\sigma>0$ . The range of a variable, $x$ , that follows a lognormal distribution is $0<x<+\infty$ . Note that zero is not included. If $x$ is said to have a lognormal distribution, then the PDF can be expressed as (where the Greek lambda, $\lambda$ , here is not to be confused with the Poisson distribution parameter introduced previously):

$$
\lambda(x)={\frac{1}{x\sigma{\sqrt{2\pi}}}}e^{-{\frac{[\ln(x)-\mu]^{2}}{2\sigma^{2}}}}.
$$

The CDF, assuming $0<a<+\infty$ can be expressed as

$$
\Lambda(a)=\int_{x=-\infty}^{a}\lambda(x)d x=\int_{x=-\infty}^{a}\frac{1}{x\sigma\sqrt{2\pi}}e^{-\frac{[\ln(x)-\mu]^{2}}{2\sigma^{2}}}d x.
$$

Similar to the normal distribution, the CDF range is $0\leq\Lambda(a)\leq1$ and provides the probability that an outcome is less than or equal to $a$

We briefly identify several location statistics related to the lognormal distribution. The median for the lognormal distribution is.

$$
M e d i a n=e^{\mu}.
$$

The mode is

$$
M o d e=e^{\mu-\sigma^{2}}.
$$

Recall the first noncentral moment is the mean and can be expressed as

$$
M e a n=E(x)={\mu_{1}}^{\prime}(x)=e^{\mu+\frac{\sigma^{2}}{2}}\sqrt{b^{2}-4a c}.
$$

The mean is a constant and the first central moment is zero or $\mu_{1}(x)=0.$ The second central moment is the variance or.

$$
\operatorname{var}(x)=\mu_{2}(x)=e^{2\mu+\sigma^{2}}(e^{\sigma^{2}}-1).
$$

The variance is a constant and the second noncentral moment is $\mu_{2}{'}(x)=\mathrm{e}^{2(\mu+\sigma^{2})}$ The third central moment is the skewness or

$$
S k e w(x)=\mu_{3}(x)=e^{3\mu+\frac{3\sigma^{2}}{2}}(e^{\sigma^{2}}-1)^{2}(e^{\sigma^{2}}+2).
$$

The skewness of the lognormal distribution is positive, which implies an asymmetric distribution, specifically positive or right skewed. The third noncentral moment is. ${\mu_{3}}^{\prime}(x)=$ $e^{3\left(\mu+{\frac{3}{2}}\sigma^{2}\right)}$ ). Similar to variance and covariance, skewness is difficult to interpret. Thus, skewness is often normalized in the following manner:.

$$
\Lambda\mathrm{S}k e w\equiv\frac{\mu_{3}^{\prime}}{{\cal V}a r^{2/3}}=(e^{\sigma^{2}}-1)^{2}(e^{\sigma^{2}}+2).
$$

The normalized skewness is an exponentially increasing function of the normal distribution variance. Symmetrical distributions, similar to the normal distribution, will have $N S k e w=0$ . If $N S k e w>0$ as is the case for the lognormal distribution, then the mean is greater than the median and the median is greater than the mode. If $N S k e w<0$ as is common with empirical finance distributions, then we have mean $<$ median $<$ mode. There are, however, some rare exceptions to this pattern; see Stuart and Ord (1987: 107).

The fourth central moment is the kurtosis or

$$
K u r t o s i s(x)=\mu_{4}(x)=e^{3\mu+\frac{3\sigma^{2}}{2}}(e^{\sigma^{2}}-1)^{2}(e^{4\sigma^{2}}+2e^{3\sigma^{2}}+3e^{2\sigma^{2}}-3).
$$

Note that the fourth moment is positive and a function of the variance. The fourth noncentral moment is ${\mu_{4}}^{\prime}(x)=e^{4(\mu+2\bar{\sigma}^{2})}$ . Kurtosis is often normalized by the variance squared. Thus, the normalized kurtosis of the lognormal distribution is

$$
N K u r t=\frac{\mu_{4}}{V a r^{2}}=(e^{\sigma^{2}}-1)(e^{3\sigma^{2}}+3e^{2\sigma^{2}}+6e^{\sigma^{2}}+6).
$$

The kurtosis is an exponentially increasing function of the normal distribution variance. Recall that the normal distribution is mesokurtic, that is, $N K u r t=3$ . Because variance is always positive, for the lognormal distribution, $N K u r t>3$ and is known as leptokurtic. As an aside, $N K u r t<3$ is called platykurtic.

Before illustrating graphically the lognormal distribution, we establish the link between the normal distribution parameters, $\mu$ and $\sigma$ , and the expected value and stan-. dard deviation of the lognormally distributed variable. We make this link by illustrating with asset prices. Recall if variable $x$ is distributed normal, denoted $x\sim N(\mu,\sigma)$ , then variable $y$ defined as $y=\exp(x)$ is distributed lognormal, denoted $x\sim\Lambda(\mu,\sigma)$ . In the context of rates of return, suppose $S_{T}=S_{t}e^{R(T-t)}$ . If $R\sim N(\mu,\sigma)$ , then we know.

$$
S_{T}\sim\Lambda\left[\ln(S_{t})+\mu(T-t),\sigma\sqrt{T-t}\right].
$$

Thus, $\begin{array}{r}{E(S_{T})=S_{0}e^{\left(\mu+\frac{\sigma^{2}}{2}\right)(T-t)},\qquad\mathrm{var}(S_{T})=S_{0}^{2}\left[e^{2(\mu+\sigma^{2})(T-t)}-e^{(2\mu+\sigma^{2})(T-t)}\right],}\end{array}$ and $S D(S_{T})=\sqrt{S_{0}^{2}\left[e^{2(\mu+\sigma^{2})(T-t)}-e^{(2\mu+\sigma^{2})(T-t)}\right]}$ . It is important to note that in finance. the normal distribution parameters are typically expressed in percentage ( $\mu$ and $\sigma$ here), whereas the lognormal mean and standard deviation. $(\operatorname{E}(S_{T})$ and $\mathrm{var}(S_{T})$ here) are typically expressed in currency units. Remember both distributions are two-parameter distributions. Often with both the lognormal and normal distributions, these two parameters are assumed to be the normal distribution's mean $(\mu)$ and standard deviation $(\sigma)$ . One could just as easily represent the lognormal distribution parameters with the lognormal distribution's mean, $E(S_{T})$ , and standard deviation, $S D(S_{T})$ . For example, suppose the normal distribution's mean is. $\mu=9.5\%$ and the standard deviation is. $\sigma=38\%$ . If an asset price is trading at 100 and suppose we have a one-year horizon, we can compute $E(S_{T})=118.20$ and $S D(S_{T})=46.59$ based on the previous equations. Thus, the mean and standard deviation of the lognormally distributed asset price is expressed in dollars or other currency units.

Alternatively, the normal distribution parameters can be expressed as a function of the lognormal distribution parameters or

$$
\begin{array}{l}{\displaystyle\mu=\frac{\ln\Big[\frac{E(S_{T})}{S_{0}}\Big]}{T-t}-\frac{\ln\Big[1+\frac{V a r(S_{T})}{E(\widetilde{S}_{T})^{2}}\Big]}{2(T-t)}\mathrm{~and~}}\ {\displaystyle\sigma^{2}=\frac{\ln\Big[1+\frac{V a r(S_{T})}{E(S_{T})^{2}}\Big]}{T-t}.}\end{array}
$$

Figures $4.2\mathrm{a-h}$ illustrate both the probability density function as well as the cumulative. distribution function of the lognormal distribution applied to some financial instrument. price. The following series of figures illustrates the effect of increases in the standard deviation because different financial instruments have different levels of standard deviation. With the lognormal distribution, the input parameters in finance are typically the mean and. standard deviation of the continuously compounded rates of return. Thus, the parameters are expressed in percentage and not currency units..

We see from these graphs that with the lognormal distribution, there is no possibility. that the underlying instrument value will fall to zero or below. Because common stock has. limited liability, we expect the stock price to remain nonnegative, but we also expect that some stock prices will go to zero--an outcome not possible with the lognormal distribu-. tion. Based on the lognormal distribution, limited liability has no value. Thus, both the. normal and lognormal distribution have strengths and weaknesses..

![](images/331ca4d1b6b1505fb5d790ebadcbcf7efcfaeda17b1b763cf967e49c62e604df.jpg)
FIGURE 4.2a Lognormal Probability Density Function $\mu=0\%$ $\sigma=30\%$

![](images/2316dd46c6f9e30a5f07a234bf67c687b1be7d7f14ebb6a2f267a3563fa1e6ac.jpg)
FIGURE 4.2b Lognormal Cumulative Distribution Function $\mu=0\%$ $\sigma=30\%$

![](images/dc8303c2d62c42530094f61e0c240fea335909688591e39db47bc9f2fdc7d60c.jpg)
FIGURE 4.2c Lognormal Probability Density Function $\mu=0\%$ $\sigma=80\%$

![](images/c2de335d9496222ed0fb0aa9ab78f18e8368cfc5f974d2e3163994eb25832508.jpg)
FIGURE 4.2d Lognormal Cumulative Distribution Function $\mu=0\%$ $\sigma=80\%$

![](images/93cdf9b0c5d8bae9a560bbc2946a545c777a6b722a77c255f6a06225cdd09f5a.jpg)
FIGURE 4.2e Lognormal Probability Density Function $\mu=0\%$ $\sigma=130\%$

![](images/5666d46b8b589eb9f7c92c23d8ddd5176429baed6fee8f386fecaacd8e3040ac.jpg)
FIGURE 4.2f Lognormal Cumulative Distribution Function $\mu=0\%$ $\sigma=130\%$

![](images/b8ed8077145424b4d73c19f108ef9151497c92c8cf2d821f5af9da6187556c4e.jpg)
FIGURE 4.2g Lognormal Probability Density Function $\mu=0\%$ $\sigma=800\%$

![](images/10f68f96c19952b95193690f001c319d2ff8982d6c2cd29209cd3a2d77ae42e9.jpg)

![](images/6c12244bdf3f19bad6c4b526846d909d9f17c88e249b22a728e2399ce82764c8.jpg)

# Financial Applications of Probability Distributions

n Chapter 4, we took a look at the fundamentals of probability theory and introduced some distributions. Option theory and indeed much of finance theory is based on the normal distribution as well as the related lognormal distribution; hence, we devote a full chapter to these distributions. In the limit, discrete distributions such as the binomial can be structured to converge to either the normal or lognormal distributions. The reasons for this extensive use of the normal and lognormal distributions are twofold. First, these distributions have only two parameters, because they are completely characterized by the expected value and variance. Second, financial utility is often based on two characteristics: non-satiation and risk aversion. Non-satiation is the notion that people always prefer more money to less. As such, they prefer a higher expected return, so they have a preference for the first moment of the distribution. Risk aversion is the notion that people do not like risk. Hence, they dislike the second moment of the distribution. If people care about only the first two moments, then the normal distribution is appropriate.

Of course, people may indeed care about higher-order moments. For example, positive. skewness is generally a desirable feature of investments. Some financial models are based. on skewness preference and skewed distributions. In the first part of the chapter, we will introduce the normal and lognormal distributions. The second part of the chapter refers to a related distribution called the bivariate normal and lognormal. As such, it might be more appropriate to call the single variable versions the univariate normal and lognormal. distribution, but this is typically not done. Usually when one uses the phrase normal distribution, one means the univariate normal. This case is the one involving only a single. variable. In the second case, the bivariate normal or lognormal, there are two normally distributed variables and they may be correlated..
