---
tags:
  - cumulative_distribution
  - european_option
  - normsdist_function
  - risk_free_rate
  - stock_price
aliases:
  - cumulative normal distribution
  - normsdist
key_concepts:
  - cumulative normal function
  - european call option
  - european put option
  - risk free interest
  - stock price calculation
---

# 15.9 CUMULATIVE NORMAL DISTRIBUTION FUNCTION  

When implementing equations (15.20) and (15.21), it is necessary to evaluate the cumulative normal distribution function $N(x)$ . Tables for $N(x)$ are provided at the end of this book. The NORMSDIST function in Excel also provides a convenient way of calculating $N(x)$  

# Example 15.6  

The stock price 6 months from the expiration of an option is $\$42$ , the exercise price. of the option is. $\$40$ , the risk-free interest rate is $10\%$ per annum, and the volatility is $20\%$ per annum. This means that $S_{0}=42,K=40,r=0.1,\sigma=0.2,T=0.5$  

$$
{\begin{array}{l}{d_{1}={\cfrac{\ln(42/40)+(0.1+0.2^{2}/2)\times0.5}{0.2{\sqrt{0.5}}}}=0.7693}\ {d_{2}={\cfrac{\ln(42/40)+(0.1-0.2^{2}/2)\times0.5}{0.2{\sqrt{0.5}}}}=0.6278}\end{array}}
$$  

and  

$$
K e^{-r T}=40e^{-0.05}=38.049
$$  

Hence, if the option is a European call, its value $c$ is given by  

$$
c=42N(0.7693)-38.049N(0.6278)
$$  

If the option is a European put, its value $p$ is given by  

$$
p=38.049N(-0.6278)-42N(-0.7693)
$$  

Using the NORMSDIST function in Excel gives  

$$
\begin{array}{l l}{{N(0.7693)=0.7791,}}&{{N(-0.7693)=0.2209}}\ {{N(0.6278)=0.7349,}}&{{N(-0.6278)=0.2651}}\end{array}
$$  

so that  

$$
c=4.76,\qquadp=0.81
$$  

Ignoring the time value of money, the stock price has to rise by. $\$2.76$ for the purchaser of the call to break even. Similarly, the stock price has to fall by $\$2.81$ for the purchaser of the put to break even..  
