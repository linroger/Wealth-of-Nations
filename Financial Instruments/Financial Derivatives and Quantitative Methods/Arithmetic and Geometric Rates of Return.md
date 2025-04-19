---
title: Arithmetic and Geometric Rates of Return
tags:
  - arithmetic_mean
  - continuous_compounding
  - geometric_mean
  - rate_of_return
  - wiener_process
aliases:
  - Arithmetic Mean vs Geometric Mean
  - Continuously Compounded Return
key_concepts:
  - Arithmetic mean return
  - Continuously compounded rate
  - Geometric mean return
  - Variance of return
  - Wiener process properties
---

# Arithmetic and Geometric Rates of Return

We now consider $\mu$ and $U$ again. Suppose we have an asset worth 100 and for two successive periods it increases by $20\%$. Then the value at the end of the first period is 120 and the value at the end of the second period is 144.

Now suppose that instead the asset increases in the first period by $30\%$ and in the second period by $10\%$. The average or arithmetic mean of the return is $20\%$. However,  the value of the asset is 130 at the end of the first period and 143 at the end of the second period. The variability of the return has meant that the asset is worth less after two periods even though the average return is the same. We can calculate the equivalent per period return that would give the same value of 143 after two periods if there were no variance in the returns. That is the value $V$ that satisfies

$$143=100 (1+\nu)^2.$$

This value is known as the geometric mean. It is another measure of the average return over the two periods. Solving this equation gives the geometric

Mean as $\nu=0.195826$ or $19.58\%$ per period² which is less than the arithmetic rate of return per period.

There is a simple relationship between the arithmetic mean return,  the geometric mean return,  and the variance of the return. Let $\mu_{1}=\mu+\sigma$ be the rate of return in the first period and let $\mu_{2}=\mu-\sigma$ be the rate of return in the second period. Here the average rate of return is $\frac{1}{2}(\mu_{1}+\mu_{2})=\mu$ and the variance of the two rates is $\sigma^{2}$. The geometric rate of return $\mu$ satisfies $(1+\nu)^{2}=(1+\mu_{1})(1+\mu_{2})$. Substituting and expanding this gives

$$1+2\nu+\nu^2=(1+\mu+\sigma)(1+\mu-\sigma)=(1+\mu)^2-\sigma^2=1+2\mu+\mu^2-\sigma^2$$

Or

$$\nu=\mu-\frac{1}{2}\sigma^{2}+\frac{1}{2}(\mu^{2}-\nu^{2}).$$

Since rates of return are typically less than one,  the square of the return is even smaller and hence the difference between two squared percentage terms is smaller still. Hence we have the approximation $\nu\approx\mu-\frac{1}{2}\sigma^{2}$ to 1.

$$\mathrm{geometric~mean}\approx\mathrm{arithmetic~mean}-\frac{1}{2}\mathrm{variance}.$$

This approximation will be better the smaller the interest rates and the smaller the variance. In the example,  $\mu=0.2$ and $\sigma=0.1$,  so $\frac{1}{2}\sigma^{2}=0.005$ and $\mu-\frac{1}{2}\sigma^{2}=0.1950$,  which is close to the actual geometric mean of 0.1958. Thus,  the difference between $\mu$ and $V$ is that $V$ is the geometric rate of return,  and $\mu$ is the arithmetic rate of return. It is quite usual to use the arithmetic rate and therefore to write that the expected value of the logarithm of the stock price satisfies

$$\operatorname{E}[\ln S_T]=\ln S_0+\left (\mu-\frac{1}{2}\sigma^2\right) T$$

And

$$\mathrm{Var}[\ln S_T]=\sigma^2 T.$$

### Continuously Compounded Rate of Return

The value $V$ is the continuously compounded rate of return. It is given by

$$\nu=\frac{1}{T}[\ln S_{T}-\ln S_{0}].$$

Hence,  taking expectations,  we can calculate

$$\mathrm{E}[\nu]=\frac{1}{T}\mathrm{E}[\ln S_{T}-\ln S_{0}]==\frac{1}{T}\left (\mathrm{E}[\ln S_{T}]-\ln S_{0}\right)=\mu-\frac{\sigma^{2}}{2}.$$

Similarly,  the variance satisfies.

$$\mathrm{Var}[\nu]=\frac{1}{T^{2}}\mathrm{Var}[\ln S_{T}-\ln S_{0}]=\frac{1}{T^{2}}\mathrm{Var}[\ln S_{T}]=\frac{\sigma^{2}T}{T^{2}}=\frac{\sigma^{2}}{T}.$$

Hence,  the standard deviation of $V$ is simply $\sigma/{\sqrt{T}}$

### A WienerProcess

We will now consider the stochastic process in more detail and see how to take limits as the length of the time interval goes to zero. This will produce a continuous-time stochastic process.

Consider a variable $iL$ which takes on values at discrete points in time $t=0,    1,    \ldots,    T$ and suppose that $Z$ evolves according to the following rule:

$$z_{t+1}=z_{t}+\epsilon;\quad W_{0}\quad\mathrm{fixed}$$

Where $t$ is a random drawing from a standardized normal distribution,  that is,  with mean of zero and variance of one. The draws are assumed to be independently distributed. This represents a random walk where on average $iL$ remains unchanged each period but where the standard deviation of the realized value is one each period. At date $t=0$ ,  we have $E[z_{T}]=z_{0}$ and the variance $Var[z_{T}]=T$ as the draws are independent.

Now divide the periods into $TL$ subperiods,  each of length $\Delta t$. To keep the process equivalent,  the variance in the shock must also be reduced so that the standard deviation is $\sqrt{\Delta t}$. The resulting process is known as aWiener process. The Wiener process has two important properties:

Property 1: The change in $iL$ over a small interval of time satisfies:

$$z_{t+h}=z_{t}+\epsilon\sqrt{\Delta t}.$$

Then,  as of time $t=0$,  it is still the case that $E[ z_{T}]$ = $z_{0}$ and the variance $Var[z_{T}]=T$ . This relation may be written

$$\Delta z (t+\Delta t)=\epsilon\sqrt{\Delta t}$$

Where $\Delta z (t+\Delta t)=z_{t+\Delta t}-z_{t}$ . This has an expected value of zero and standard deviation of $\sqrt{\Delta t}$

Property 2: The values of $\Delta z$ for any two different short intervals of time are independent.

It follows from this that

$$z (T) - z (0)=\sum_i^N\epsilon_i\sqrt{\Delta t}$$

Where $N=T/\Delta t$ is the number of time intervals between 0 and $T$. Hence,  we have

$$\mathrm{E}[Z (T)]=z (0)$$

And

$$\mathrm{Var}[z (T)]=N\Delta t=T$$

 Or the standard deviation of $z (T)$ is $\sqrt{T}$.

Now consider what happens in the limit as $\Delta t\to 0$ ,  that is,  as the length of the interval becomes an infinitesimal $dt$. We replace $\Delta z (t+\Delta t)$ by $dz (t)$.

Which has a mean of zero and standard deviation of $dt$. This continuous time stochastic process is also known as Brownian Motion after its use in physics to describe the motion of particles subject to a large number of small molecular shocks.

This process is easily generalized to allow for a non-zero mean and arbitrary standard deviation. A generalized Wiener process for a variable $3L$ is defined in terms of $dz (t)$ as follows

$$dx= adt+ bdz$$

where $U$ and $b$ are constants. This formula for the change in the value of ${:}L$ consists of two components,  a deterministic component $b$ $dz ( t)$ .The deterministic component is $dx= a$ $dt$ or $\frac {dx}{dt}$ = $a$ which shows that $x$ = $x_{0}+ at$ so that $d.$ is simply the trend term for $JL$. Thus the increase in the value of ${:}\boldsymbol{L}$ over one time period is $d$. The stochastic component $b$ $dz ( t)$ adds noise or variability to the path for $2 L$. The amount of variability added is $b$ times the Wiener process. Since the Wiener process has a standard deviation of one,  the generalized process has a standard deviation of $b$.

### The Asset Price Process

### Remember that we have

$$\ln S_{t+1}-\ln S_t=\omega_t$$

Where $\omega t$ are independent random variables with mean $U$ and standard deviation of 0. The continuous time version of this equation is therefore

$$d\:\ln S (t)=\nu\:dt+\sigma\:dz$$

Where Z is a standard Wiener process. The right-hand-side of the equation is just a random variable that is evolving through time. The term $V$ is called the

Drift parameter and the standard deviation of the continuously compounded rate of return is $\sqrt{Var[r (t)]}=\sigma\sqrt{\Delta t}$ and the term $U$ is referred to as the volatility of the asset return.

### Ito Calculus

We have written the process in terms of $\ln S (t)$ rather than $S (t)$ itself. This is convenient and shows the connection to the binomial model. However,  it is usual to think in terms of $S (t)$ itself too. In ordinary calculus,  we know that

$$d\ln S (t)=\frac{dS (t)}{S (t)}.$$

Thus,  we might think that $dS ( t) / S ( t)$ = $\nu$ $dt$ + $\sigma$ $dz$. But this would be WRONG. The correct version is

$$\frac{dS (t)}{S (t)}=\left (\nu+\frac{1}{2}\sigma^2\right)\:dt+\sigma\: dz.$$

This is a special case of Ito's lemma. Ito's lemma shows that for any process of the form

$$dx=a (x,    t) dt+b (x,    t) dz$$

Then the function $G (x,    t)$ follows the process

$$dG=\left (\frac{\partial G}{\partial x}a (x,    t)+\frac{\partial G}{\partial t}+\frac{1}{2}\frac{\partial^2 G}{\partial x^2}b^2 (x,    t)\right) dt+\frac{\partial G}{\partial x}b (x,    t) dz.$$

We'll see how to use Ito's lemma. We have

$$d\:\ln S (t)=\nu\:dt+\sigma\: dz.$$

Then let $\ln S (t)=x (t)$ s 0 $s (T)=G (x,    t)=e^{x}$ . Then upon differentiating

$$\frac{\partial G}{\partial x}=e^x=S,    \quad\frac{\partial^2 G}{\partial S^2}=e^x=S,    \quad\frac{\partial G}{\partial t}=0.$$

Hence,  using Ito's lemma

$$dS (t)=(\nu S (t)+0+\frac{1}{2}\sigma^{2}S (t)) dt+\sigma S (t)\:dz$$

Or

$$d\: S (t)=(\nu+\frac 12\sigma^2) S (t)\:dt+\sigma S (t)\:dz$$

Since $\mu=\nu+\frac{1}{2}\sigma^{2}$ we can write this as

$$d\: S (t)=\mu S (t)\:dt+\sigma S (t)\: dz.$$

This process is known as geometric Brownian motion as it is the rate of change which is Brownian motion. Thus sometimes the above equation is written as

$$\begin{aligned}\frac{d\: S (t)}{S (t)}=\mu\:dt+\sigma\: dz.\end{aligned}$$

We can also do the same calculation the other way around. Suppose that we start from the process

$$ds (t)=\mu S (t)\:dt+\sigma S (t)\: dz.$$

Now consider the function $G (S)=\ln S$ . Differentiating we have

$$\frac{\partial G}{\partial S}=1,    \quad\frac{\partial^2 G}{\partial S^2}=-\frac{1}{S^2},    \quad\frac{\partial G}{\partial t}=0.$$

Hence substituting into Ito's lemma we get.

$$dG=d\ln S (t)=\left (\mu-\frac{1}{2}\sigma^2\right)\:dt+\sigma\: dz.$$

### The forward price

As we have seen before the forward price just depends on the current price of the underlying,  the interest rate,  and the time to expiration. With continuous compounding we can write the forward price equation as

$$F (S (t),    t)=S (t) e^{r (T-t)}.$$

This shows the forward price is a stochastic process which depends on the price of the underlying asset which itself is a stochastic process. Since we have

That the forward price is a function of a stochastic process we can use Ito's lemma. Upon differentiation we have

$$\frac{\partial F}{\partial S}=e^{r (T-t)};\quad\frac{\partial F}{\partial t}=-rS (t) e^{r (T-t)};\quad\frac{\partial^2 F}{\partial S^2}=0.$$

Hence substituting into Ito's lemma

$$\begin{aligned}dF&=\left (e^{r (T-t)}\mu S (t)-rS (t) e^{r (T-t)}\right) dt+\sigma S (t) e^{r (T-t)}dz\\&=(\mu-r) S (t) e^{r (T-t)}\sigma S (t) e^{r (T-t)}dz\\&=(\mu-r) F (t) dt+\sigma F (t) dz.\end{aligned}$$

This shows that the forward price also follows a geometric Brownian motion process with expected return given by the risk premium on the underlying $\mu-r$ and volatility 0 (the same as the underlying asset).

## Summary

We have shown how returns are continuously compounded and introduced the geometric Brownian motion process for stock prices. We have shown how Ito's lemma can be used. The next thing to do will be to show how to use the assumption of geometric Brownian motion to price an option or derivative using Ito's lemma.
