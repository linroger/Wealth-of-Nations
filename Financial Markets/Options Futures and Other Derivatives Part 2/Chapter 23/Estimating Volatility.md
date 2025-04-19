---
tags:
  - ewma_model
  - garch_model
  - historical_data
  - variance_rate
  - volatility_estimation
aliases:
  - Estimating Volatility
  - Variance Rate
  - Volatility Calculation
key_concepts:
  - Historical data estimation
  - Long-run average variance
  - Market variable volatility
  - Variance rate calculation
  - Weighting schemes
---

# 23.1 ESTIMATING VOLATILITY  

Define $\sigma_{n}$ as the volatility of a market variable on day $n$ , as estimated at the end of day $n-1$ . The square of the volatility, $\sigma_{n}^{2}$ , on day $n$ is the variance rate. We described the standard approach to estimating $\sigma_{n}$ from historical data in Section 15.4. Suppose that the value of the market variable at the end of day $i$ is $S_{i}$ The variable $u_{i}$ is defined as the continuously compounded return during day $i$ (between the end of day $i\textrm{--}1$ and the end of day $i$  

$$
u_{i}=\ln{\frac{S_{i}}{S_{i-1}}}
$$  

An unbiased estimate of the variance rate per day, $\sigma_{n}^{2}$ , using the most recent. $m$ observations on the $u_{i}$ is  

$$
\sigma_{n}^{2}={\frac{1}{m-1}}{\sum_{i=1}^{m}(u_{n-i}-{\overline{{u}}})^{2}}
$$  

where $\overline{{u}}$ is the mean of the $u_{i}^{;}$  

$$
{\overline{{u}}}={\frac{1}{m}}\sum_{i=1}^{m}u_{n-i}
$$  

For the purposes of monitoring daily volatility, the formula in equation (23.1) is usually changed in a number of ways:.  

1. $u_{i}$ is defined as the percentage change in the market variable between the end of day $i-1$ and the end of day. $i$ , so that:  

$$
u_{i}=\frac{S_{i}-S_{i-1}}{S_{i-1}}
$$  

2. $\overline{{u}}$ is assumed to be zero.?   
3. $m\textrm{--}1$ is replaced by $m$ 3.  

These three changes make very little difference to the estimates that are calculated, but they allow us to simplify the formula for the variance rate to  

$$
\sigma_{n}^{2}={\frac{1}{m}}\sum_{i=1}^{m}u_{n-i}^{2}
$$  

where $u_{i}$ is given by equation (23.2).4  

# Weighting Schemes  

Equation (23.3) gives equal weight to $u_{n-1}^{2},u_{n-2}^{2},...,u_{n-m}^{2}.$ Our objective is to estimate the current level of volatility, $\sigma_{n}$ . It therefore makes sense to give more weight to recent data. A model that does this is  

$$
\sigma_{n}^{2}=\sum_{i=1}^{m}\alpha_{i}u_{n-i}^{2}
$$  

The variable $\alpha_{i}$ is the amount of weight given to the observation. $i$ days ago. The $\alpha$ 's are positive. If we choose them so that $\alpha_{i}<\alpha_{j}$ when $i>j$ less weight is given to older observations. The weights must sum to unity, so that  

$$
\sum_{i=1}^{m}\alpha_{i}=1
$$  

An extension of the idea in equation (23.4) is to assume that there is a long-run average  

variance rate and that this should be given some weight. This leads to the model that takes the form  

$$
\sigma_{n}^{2}=\gamma V_{L}+\sum_{i=1}^{m}\alpha_{i}u_{n-i}^{2}
$$  

where $V_{L}$ is the long-run variance rate and. $\gamma$ is the weight assigned to. $V_{L}$ . Since the weights must sum to unity, we have  

$$
\gamma+\sum_{i=1}^{m}\alpha_{i}=1
$$  

This is known as an. $\mathrm{ARCH}(m)$ model. It was first suggested by Engle. The estimate of the variance is based on a long-run average variance and $m$ observations. The older an. observation, the less weight it is given. Defining. $\omega=\gamma V_{L}$ , the model in equation (23.5) can be written  

$$
\sigma_{n}^{2}=\omega+\sum_{i=1}^{m}\alpha_{i}u_{n-i}^{2}
$$  

In the next two sections we discuss two important approaches to monitoring volatility using the ideas in equations (23.4) and (23.5).  
