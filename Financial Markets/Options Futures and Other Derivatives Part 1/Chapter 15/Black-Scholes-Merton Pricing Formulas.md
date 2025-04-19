---
tags:
  - american_options
  - black_scholes_merton
  - european_options
  - option_pricing
  - risk_neutral_valuation
aliases:
  - BSM formulas
  - Black-Scholes
  - European call
  - European put
key_concepts:
  - American call option
  - Black-Scholes-Merton formulas
  - European call/put options
  - Risk-neutral valuation
  - Standard normal distribution
---

# 15.8 BLACK-SCHOLES-MERTON PRICING FORMULAS  

The most famous solutions to the differential equation (15.16) are the Black-ScholesMerton formulas for the prices of European call and put options. These formulas are:.  

$$
c=S_{0}N(d_{1})-K e^{-r T}N(d_{2})
$$  

and  

$$
p=K e^{-r T}N(-d_{2})-S_{0}N(-d_{1})
$$  

![](9a6dae0a1252ccffd1553a224346cf1ac983df8148cb84e7a530b7141d8fde69.jpg)  
Figure 15.3 Shaded area represents $N(x)$  

where  

$$
\begin{array}{r l}&{d_{1}=\cfrac{\ln{(S_{0}/K)}+(r+\sigma^{2}/2)T}{\sigma\sqrt{T}}}\ &{d_{2}=\cfrac{\ln{(S_{0}/K)}+(r-\sigma^{2}/2)T}{\sigma\sqrt{T}}=d_{1}-\sigma\sqrt{T}}\end{array}
$$  

The function. $N(x)$ is the cumulative probability distribution function for a variable with. a standard normal distribution. In other words, it is the probability that a variable with a standard normal distribution will be less than. $x$ . It is illustrated in Figure 15.3. The remaining variables should be familiar. The variables. $c$ and $p$ are the European call and European put price, $S_{0}$ is the stock price at time zero, $K$ is the strike price, $r$ is the continuously compounded risk-free rate, $\sigma$ is the stock price volatility, and $T$ is the time. to maturity of the option.  

One way of deriving the Black-Scholes-Merton formulas is by solving the differential equation (15.16) subject to the boundary condition mentioned in Section 15.6.8 (See Problem 15.25 to prove that the call price in equation (15.20) satisfies the. differential equation.) Another approach is to use risk-neutral valuation. Consider a. European call option. The expected value of the option at maturity in a risk-neutral. world is  

$$
\hat{E}[\operatorname*{max}(S_{T}-K,0)]
$$  

where, as before, $\hat{E}$ denotes the expected value in a risk-neutral world. From the riskneutral valuation argument, the European call option price. $c$ is this expected value discounted at the risk-free rate of interest, that is,.  

$$
c=e^{-r T}\hat{E}[\operatorname*{max}(S_{T}-K,0)]
$$  

The appendix at the end of this chapter shows that this equation leads to the result in equation (15.20).  

Since it is never optimal to exercise early an American call option on a non-dividend-.   
paying stock (see Section 11.5), equation (15.20) is the value of an American call option.   
on a non-dividend-paying stock. Unfortunately, no exact analytic formula for the value   
of an American put option on a non-dividend-paying stock has been produced..   
Numerical procedures for calculating American put values are discussed in Chapter 21..  

When the Black-Scholes-Merton formula is used in practice the interest rate. $r$ is set equal to the zero-coupon risk-free interest rate for a maturity. $T.$ As we show in later chapters, this is theoretically correct when $r$ is a known function of time. It is also theoretically correct when the interest rate is stochastic provided that the stock price at time $T$ is lognormal and the volatility parameter is chosen appropriately. As mentioned. earlier, time is normally measured as the number of trading days left in the life of the. option divided by the number of trading days in 1 year.  

# Understanding $\cal{N}(d_{1})$ and $N(d_{2})$  

The term $N(d_{2})$ in equation (15.20) has a fairly simple interpretation. It is the prob-. ability that a call option will be exercised in a risk-neutral world. The $N(d_{1})$ term is not. quite so easy to interpret. The expression. $S_{0}N(d_{1})e^{r T}$ is the expected stock price at time $T$ in a risk-neutral world when stock prices less than the strike price are counted as zero. The strike price is only paid if the stock price is greater than. $K$ and as just mentioned this has a probability of. $N(d_{2})$ . The expected payoff in a risk-neutral world is. therefore  

$$
S_{0}N(d_{1})e^{r T}-K N(d_{2})
$$  

Present-valuing this from time $T$ to time zero gives the Black-Scholes-Merton equation for a European call option:  

$$
c=S_{0}N(d_{1})-K e^{-r T}N(d_{2})
$$  

For another way of looking at the Black-Scholes-Merton equation for the value of a European call option, note that it can be written as.  

$$
c=e^{-r T}N(d_{2})[S_{0}e^{r T}N(d_{1})/N(d_{2})-K]
$$  

The terms here have the following interpretation:  

$e^{-r T}$ :Present value factor $N(d_{2})$ : Probability of exercise $S_{0}e^{r T}N(d_{1})/N(d_{2})$ :Expected stock price in a risk-neutral world if option is exercised $K$ :Strike price paid if option is exercised.  

# Properties of the Black-Scholes-Merton Formulas  

We now show that the Black-Scholes-Merton formulas have the right general proper-.   
ties by considering what happens when some of the parameters take extreme values.  

When the stock price, $S_{0}$ , becomes very large, a call option is almost certain to be. exercised. It then becomes very similar to a forward contract with delivery price $K$  

From equation (5.5), we expect the call price to be  

$$
S_{0}\mathrm{~-~}K e^{-r T}
$$  

This is, in fact, the call price given by equation (15.20) because, when $S_{0}$ becomes very large, both $d_{1}$ and $d_{2}$ become very large, and. $N(d_{1})$ and $N(d_{2})$ become close to 1.0. When the stock price becomes very large, the price of a European put option, $p$ approaches zero. This is consistent with equation (15.21) because $N(-d_{1})$ and $N(-d_{2})$ are both close to zero in this case..  

Consider next what happens when the volatility $\sigma$ approaches zero. Because the stock is virtually riskless, its price will grow at rate $r$ to $S_{0}e^{r T}$ at time $T$ and the payoff from a call option is  

$$
\operatorname*{max}(S_{0}e^{r T}-K,0)
$$  

Discounting at rate. $r$ , the value of the call today is  

$$
e^{-r T}\operatorname*{max}(S_{0}e^{r T}-K,0)=\operatorname*{max}(S_{0}-K e^{-r T},0)
$$  

To show that this is consistent with equation (15.20), consider first the case where $S_{0}>K e^{-r T}$ This implies that In $(S_{0}/K)+r T>0.$ As $\sigma$ tends to zero, $d_{1}$ and $d_{2}$ tend to $+\infty$ , so that $N(d_{1})$ and $N(d_{2})$ tend to 1.0 and equation (15.20) becomes  

$$
c=S_{0}-K e^{-r T}
$$  

When $S_{0}<K e^{-r T}$ it follows that $\ln(S_{0}/K)+r T<0$ As $\sigma$ tends to zero, $d_{1}$ and $d_{2}$ tend to $-\infty$ , so that $N(d_{1})$ and $N(d_{2})$ tend to zero and equation (15.20) gives a call price of zero. The call price is therefore always $\operatorname*{max}(S_{0}-\bar{K}e^{-r T},0)$ as $\sigma$ tends to zero. Similarly, it can be shown that the put price is always $\operatorname*{max}(K e^{-r T}-S_{0},0)$ as $\sigma$ tends to zero.  
