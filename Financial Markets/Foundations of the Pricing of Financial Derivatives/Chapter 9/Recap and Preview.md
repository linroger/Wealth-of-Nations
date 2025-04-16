---
tags:
  - '#binomial_model'
  - '#black_scholes_merton_model'
  - '#continuous_time_derivatives'
  - '#lognormal_distribution'
  - '#option_pricing'
  - '#probability_theory'
  - '#stochastic_process'
  - '#wiener_processes'
---
# 9.5 RECAP AND PREVIEW

We have shown in this chapter that the binomial model converges to the Black-ScholesMerton model.' We made no assumptions regarding what the probabilities were, and we.

did not have to specify a particular formula for $\boldsymbol{\mathscr{u}}$ and $d$ . Hsia's proof requires only the condition of the DeMoivre-LaPlace limit theorem, which is that. $n p\rightarrow\infty$ as $n\to\infty$ . This condition will not be met only if the probability per period approaches zero. This is clearly not the case. If the probability of an up move approaches zero, then the probability of a down move would approach one. The model would then be meaningless as there would be no uncertainty. In fact, it is well known that the probability value converges to. $1/_{2}$ 10

This completes Part II. In Part III, we move into the continuous time world of Black, Scholes, and Merton. Chapter 10 introduces the statistical process that we shall use to describe movements in the underlying asset.

# QUESTIONS AND PROBLEMS

1 When selecting the lowest integer within the binomial sum where the call option is in-the-money, we have the following relationships,

$$
{a}^{*}={\frac{\ln(X/S)-n\ln d}{\ln(u/d)}}{\mathrm{~and}}
$$

If we assume that $d=1/u$ , explain the behavior of $\phi$ as $_n$ increases. Further, illustrate your results for $S=100$ $X=100$ $u=1.25$ , and $n=1,2,3,4,5,100$ , and 101.

2Suppose $S=90$ $X=100$ $u=1.25$ $d=0.80$ $n=5$ , and $r=5.0\%$ . Compute $B_{1}(j)$ and $B_{2}(j)$ for all six outcomes. With these results as well as the data provided here, calculate the call and put prices.

<html><body><table><tr><td>Counter</td><td>n choosej</td><td>S</td></tr><tr><td>0</td><td>1</td><td>29.49</td></tr><tr><td>1</td><td>5</td><td>46.08</td></tr><tr><td>2</td><td>10</td><td>72.00</td></tr><tr><td>3</td><td>10</td><td>112.50</td></tr><tr><td>4</td><td>5</td><td>175.78</td></tr><tr><td>5</td><td>1</td><td>274.66</td></tr><tr><td>Sum</td><td>1,024</td><td>114.87*</td></tr></table></body></html>

\*Sum of the product of. ${\mathrm{B}}_{2}{\mathrm{S}}$ or the expected terminal stock price.

3 Prove: $\begin{array}{r}{{V a r}\left[\ln\left(\frac{S_{T}}{S}\right)\right]=n\phi(1-\phi)\Big[\ln\left(\frac{u}{d}\right)\Big]^{2}.}\end{array}$

4 Prove $B_{1}$ is always greater than or equal to $B_{2}$

5 Within the vast literature related to the multiplicative binomial model, there has. emerged what are known as coherent conditions. Coherent conditions address the conditions necessary to ensure that regardless of the number of time steps, the binomial model is consistent (coherent) with the parameters of the lognormal distribution. To be coherent, the following two conditions must hold at any point in time. $t.$ and any node $j!$

$$
e^{r\Delta t}=\phi u+(1-\phi)d{\mathrm{~and}}
$$

$$
\sigma^{2}\Delta t=\phi(1-\phi)\left[\ln\left(\frac{u}{d}\right)\right].
$$

Based on these two conditions, identify the relationships among $\phi,u_{}.$ and $d$

# NOTES

1. An alternative approach is provided by Jarrow and Rudd (1983), whose up and down factors are different from those of Cox, Ross, and Rubinstein, and these values hold for any number of time steps, not just in the limit. They then provide a general sketch of how the binomial model converges to the Black-Scholes-Merton model..
2. Chance (2008) provides a review of binomial option pricing models and the various formulas that have been used to convert volatility to the up and down factors. He shows that they all converge to a risk neutral probability of $1/_{2}$
3. For ease of exposition, we suppress the time subscript $t$
4. Note the symbol $\in$ is read as "is an element of." Thus,. $(a\in n)$ is read $^{\circ}a$ is an element of $_{n}$
5. Although it is not particularly important, note that. $r$ is the harmonic mean return on the asset when the probability is $\phi^{*}$
6. Note that this expression is the inverse of the return. That is, it is the earlier price over the later price.
7. Let $_x$ be distributed lognormally meaning that $\ln x$ is distributed normally. Let. $y=1/x$ Is lny distributed normally? $\ln y=\ln1-\ln x=-\ln x$ Given that $\ln x$ is distributed normally, changing. its sign will not change its status as a normally distributed variable. It simply changes all positive outcomes to negative and vice versa. It does not change the normal distribution into some other type of distribution.
8. This result is obtained by evaluating the integral of the normally distributed random variable $x$ using the normal density function..
9. Another convergence result is provided in the Rendleman and Bartter (1979) version of the. model. Their proof seems somewhat more complex than the Cox-Ross-Rubinstein proof and requires the condition that the probabilities converge to. $1/_{2}$ . Although this condition is met, nonetheless, it is not necessary to impose it to obtain the proof..
10. For the Jarrow and Rudd proof, they simply set the probability to $1/_{2}$ and then do not alter it as time steps are added (p. 188). In other applications of the binomial model, such as elsewhere in the Jarrow-Rudd book, the probability is not arbitrarily set to ${}^{1}h_{2\cdot}$ but simulations would show that it converges to. $^1/_{2}$ given their formulas for. $\boldsymbol{\mu}$ and $d$ , as the number of time steps increases.. Of course, as noted, Chance (2008) demonstrated that in all of the well-known formulas the. probability converges to $\%$

# Continuous Time Derivatives Pricing Theory

# The Basics of Brownian Motion and Wiener Processes

The prices of assets evolve in a random manner, meaning that stock prices, interest rates, exchange rates, and commodity prices are largely unpredictable. Thus, the financial landscape will be everchanging. Unpredictable, however, does not mean bizarre or meaningless. Indeed, it is important that we understand the probability process driving prices, because this helps us to develop good valuation models. Estimates of expected returns and volatilities and their effects on asset and derivative prices are essential elements in the financial decision-making process. Although there are many excellent references on the subject of this chapter, three we highly recommend are Baxter and Rennie (1996), Neftci (2000), and Malliaris and Brock (1982).

A stochastic process is a sequence of observations from a probability distribution. Rolling a pair of dice multiple times is a stochastic process. In this case, the distribution is stable because the possible outcomes do not change from one roll to the next. Rolling a 6-5 three times in a row, while highly unlikely, in no way changes the probability of rolling another 6-5. A changing distribution, however, would be the case if we drew a card from a deck and then drew another card without replacing the previously drawn card.. Real-world asset prices probably come from changing distributions, though it is difficult to determine when a distribution has changed. Empirical analysis of past data can be useful. in that context-not to predict the future, but to know when the numbers are coming out according to different bounds of probability. At this point, however, we shall focus on stochastic processes that are stable, which are sometimes called homogeneous or identically. distributed.
