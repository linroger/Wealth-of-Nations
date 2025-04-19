---
tags:
  - '#call_option_rho'
  - '#european_options'
  - '#interest_rate_sensitivity'
  - '#option_pricing'
  - '#option_rho'
  - '#put_option_rho'
  - '#risk_free_rate'
---
# 19.9 RHO  

The rho of an option is the rate of change of its price $f$ with respect to the interest. rate $r$  

$$
\frac{\partial f}{\partial r}
$$  

It measures the sensitivity of the value of a portfolio to a change in the interest rate when all else remains the same. In practice (at least for European options) $r$ is usually set equal to the risk-free rate for a maturity equal to the option's maturity (see Section 28.6). This means that a trader has exposure to movements in the whole term structure when the options in the trader's portfolio have different maturities. For a European call option on a non-dividend-paying stock,  

$$
\mathrm{rho~(call)}=K T e^{-r T}N(d_{2})
$$  

where $d_{2}$ is defined as in equation (15.20). For a European put option,  

$$
\mathrm{rho~(put)}=-K T e^{-r T}N(-d_{2})
$$  

# Example 19.7  

As in Example 19.1, consider a call option on a non-dividend-paying stock where the stock price is $\$49$ , the strike price is $\$50$ , the risk-free rate is $5\%$ , the time to maturity is 20 weeks $(=0.3846$ years), and the volatility is. $20\%$ . In this case, $S_{0}=49,K=50,r=0.05,\sigma=0.2$ and $T=0.3846$  

The option's rho is  

$$
K T e^{-r T}N(d_{2})=8.91
$$  

This means that a $1\%$ (0.01) increase in the risk-free rate (from $5\%$ to $6\%$ increases the value of the option by approximately $0.01\times8.91=0.0891$  
