---
tags:
  - discrete_time_model
  - expected_return
  - geometric_brownian_motion
  - stock_price
  - volatility
aliases:
  - stock price process
key_concepts:
  - constant variance rate
  - discrete-time version
  - expected drift rate
  - expected percentage return
  - geometric Brownian motion
  - stochastic process
  - stock price volatility
---

# 14.3 THE PROCESS FOR A STOCK PRICE  

In this section we discuss the stochastic process usually assumed for the price of a nondividend-paying stock.  

It is tempting to suggest that a stock price follows a generalized Wiener process; that is,. that it has a constant expected drift rate and a constant variance rate. However, this model fails to capture a key aspect of stock prices. This is that the expected percentage return required by investors from a stock is independent of the stock's price. If investors require a $14\%$ per annum expected return when the stock price is $\$10$ , then, ceteris paribus, they will also require a $14\%$ per annum expected return when it is $\$50$  

Clearly, the assumption of constant expected drift rate is inappropriate and needs to be replaced by the assumption that the expected return (i.e., expected drift divided by the stock price) is constant. If $S$ is the stock price at time $t$ , then the expected drift rate in $S$ should be assumed to be $\mu S$ for some constant parameter $\mu$ . This means that in a short interval of time, $\Delta t$ , the expected increase in $S$ is $\mu S\Delta t.$ The parameter $\mu$ is the expected rate of return on the stock.  

If the coefficient of. $d z$ is zero, so that there is no uncertainty, then this model implies that  

$$
\Delta S=\mu S\Delta t
$$  

in the limit, as $\Delta t\longrightarrow0$ , so that:  

$$
d S=\mu S d t
$$  

or  

$$
\frac{d S}{S}=\mu d t
$$  

Integrating between time 0 and time $T$ we get  

$$
S_{T}=S_{0}e^{\mu T}
$$  

where $S_{0}$ and $S_{T}$ are the stock price at time 0 and time $T.$ Equation (14.5) shows that, when there is no uncertainty, the stock price grows at a continuously compounded rate of $\mu$ per unit of time.  

In practice, of course, there is uncertainty. A reasonable assumption is that the variability of the return in a short period of time,. $\Delta t$ , is the same regardless of the stock price. In other words, an investor is just as uncertain about the return when the stock price is $\$50$ as when it is $\$10$ . This suggests that the standard deviation of the change in a short period of time $\Delta t$ should be proportional to the stock price and leads. to the model  

$$
d S=\mu S d t+\sigma S d z
$$  

or  

$$
\frac{d S}{S}=\mu d t+\sigma d z
$$  

Equation (14.6) is the most widely used model of stock price behavior. The variable $\mu$ is the stock's expected rate of return. The variable $\sigma$ is the volatility of the stock price. The variable $\sigma^{2}$ is referred to as its variance rate. The model in equation (14.6) represents the stock price process in the real world. In a risk-neutral world, $\mu$ equals the risk-free. rate $r$  

# Discrete-Time Model  

The model of stock price behavior we have developed is known as geometric Brownian motion. The discrete-time version of the model is  

$$
{\frac{\Delta S}{S}}=\mu\Delta t+\sigma\epsilon{\sqrt{\Delta t}}
$$  

or  

$$
\Delta S=\mu S\Delta t+\sigma S\epsilon\sqrt{\Delta t}
$$  

The variable. $\Delta S$ is the change in the stock price $S$ in a small time interval. $\Delta t$ and as before $\epsilon$ has a standard normal distribution (i.e., a normal distribution with a mean of zero and standard deviation of 1.0). The parameter $\mu$ is the expected rate of return per unit of time from the stock. The parameter $\sigma$ is the stock price volatility. In this chapter we will assume these parameters are constant.  

The left-hand side of equation (14.7) is the discrete approximation to the return provided by the stock in a short period of time, $\Delta t.$ The term $\mu$ $\Delta t$ is the expected value of this return, and the term. $\sigma\dot{\epsilon}\sqrt{\Delta t}$ is the stochastic component of the return. The variance of the stochastic component (and, therefore, of the whole return) is $\sigma^{2}\Delta t.$ This is consistent with the definition of the volatility $\sigma$ given in Section 13.7; that is,. $\sigma$ is such that $\sigma\sqrt{\Delta t}$ is the standard deviation of the return in a short time period. $\Delta t$  

Equation (14.7) shows that. $\Delta S/S$ is approximately normally distributed with mean $\mu\Delta t$ and standard deviation $\sigma\mathcal{N}\dot{\Delta}t$ . In other words,.  

$$
{\frac{\Delta S}{S}}\sim\phi(\mu\Delta t,\sigma^{2}\Delta t)
$$  

# Example 14.3  

Consider a stock that pays no dividends, has a volatility of $30\%$ per annum, and provides an expected return of $15\%$ per annum with continuous compounding. In this case, $\mu=0.15$ and $\sigma=0.30$ . The process for the stock price is  

$$
\frac{d S}{S}=0.15d t+0.30d z
$$  

If $S$ is the stock price at a particular time and. $\Delta S$ is the increase in the stock price in the next small interval of time, the discrete approximation to the process is  

$$
\frac{\Delta S}{S}=0.15\Delta t+0.30\epsilon\sqrt{\Delta t}
$$  

where $\epsilon$ has a standard normal distribution. Consider a time interval of 1 week, or 0.0192 year, so that $\Delta t=0.0192$ . Then the approximation gives  

$$
{\frac{\Delta S}{S}}=0.15\times0.0192+0.30\times{\sqrt{0.0192}}\epsilon
$$  

or  

$$
\Delta S=0.00288S+0.0416S\epsilon
$$  

# Monte Carlo Simulation  

A Monte Carlo simulation of a stochastic process is a procedure for sampling random. outcomes for the process. We will use it as a way of developing some understanding of the nature of the stock price process in equation (14.6).  

Consider the situation in Example 14.3 where the expected return from a stock is $15\%$ per annum and the volatility is. $30\%$ per annum. The stock price change over 1 week was shown to be approximately  

$$
\Delta S=0.00288S+0.0416S\epsilon
$$  

A path for the stock price over 10 weeks can be simulated by sampling repeatedly for. $\epsilon$ from $\phi(0,1)$ and substituting into equation (14.10). The expression $=$ RAND() in Excel produces a random sample between 0 and 1. The inverse cumulative normal distribution is NORMSINV. The instruction to produce a random sample from a standard normal. distribution in Excel is therefore $=$ NORMSINV(RANDQ). Table 14.1 shows one path for a stock price that was sampled in this way. The initial stock price is assumed to be $\$100$ For the first period, $\epsilon$ is sampled as 0.52. From equation (14.10), the change during. the first time period is  

$$
\Delta S=0.00288\times100+0.0416\times100\times0.52=2.45
$$  

Therefore, at the beginning of the second time period, the stock price is $\$102.45$ . The  

Table 14.1 Simulation of stock price when $\mu=0.15$ and $\sigma=0.30$ during 1-week periods..   


<html><body><table><tr><td>Stockprice</td><td>Randomsample</td><td>Changein stock price duringperiod</td></tr><tr><td>atstartofperiod</td><td>for E</td><td></td></tr><tr><td>100.00</td><td>0.52</td><td>2.45</td></tr><tr><td>102.45</td><td>1.44</td><td>6.43</td></tr><tr><td>108.88</td><td>-0.86</td><td>-3.58</td></tr><tr><td>105.30</td><td>1.46</td><td>6.70</td></tr><tr><td>112.00</td><td>-0.69</td><td>-2.89</td></tr><tr><td>109.11</td><td>-0.74</td><td>-3.04</td></tr><tr><td>106.06</td><td>0.21</td><td>1.23</td></tr><tr><td>107.30</td><td>-1.10</td><td>-4.60</td></tr><tr><td>102.69</td><td>0.73</td><td>3.41</td></tr><tr><td>106.11</td><td>1.16</td><td>5.43</td></tr><tr><td>111.54</td><td>2.56</td><td>12.20</td></tr></table></body></html>  

value of $\epsilon$ sampled for the next period is 1.44. From equation (14.10), the change during the second time period is  

$$
\Delta S=0.00288\times102.45+0.0416\times102.45\times1.44=6.43
$$  

So, at the beginning of the next period, the stock price is $\$108.88$ , and so on.4 Note that, because the process we are simulating is Markov, the samples for $\epsilon$ should be independent of each other.  

Table 14.1 assumes that stock prices are measured to the nearest cent. It is important to realize that the table shows only one possible pattern of stock price movements. Different random samples would lead to different price movements. Any small time interval $\Delta t$ can be used in the simulation. In the limit as $\Delta t\longrightarrow0$ , a perfect description of the stochastic process is obtained. The final stock price of 111.54 in Table 14.1 can be regarded as a random sample from the distribution of stock prices at the end of 10 weeks. By repeatedly simulating movements in the stock price, a complete prob-. ability distribution of the stock price at the end of this time is obtained. Monte Carlo simulation is discussed in more detail in Chapter 21.  
