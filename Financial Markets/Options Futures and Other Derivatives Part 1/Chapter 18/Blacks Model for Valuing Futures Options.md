---
tags:
  - '#black_model'
  - '#european_options'
  - '#futures_options'
  - '#futures_price_volatility'
  - '#lognormal_process'
  - '#option_pricing'
  - '#put_option_pricing'
---
# 18.7 BLACK'S MODEL FOR VALUING FUTURES OPTIONS  

European futures options can be valued by extending the results we have produced. Fischer Black was the first to show this in a paper published in 1976. Assuming that. the futures price follows the (lognormal) process in equation (18.5), the European call price $c$ and the European put price $p$ for a futures option are given by equations (17.4) and (17.5) with $S_{0}$ replaced by $F_{0}$ and $q=r$  

$$
\begin{array}{c}{{c=e^{-r T}[F_{0}N(d_{1})-K N(d_{2})]}}\ {{p=e^{-r T}[K N(-d_{2})-F_{0}N(-d_{1})]}}\end{array}
$$  

where  

$$
d_{1}={\frac{\ln(F_{0}/K)+\sigma^{2}T/2}{\sigma{\sqrt{T}}}}
$$  

$$
d_{2}={\frac{\ln(F_{0}/K)-\sigma^{2}T/2}{\sigma{\sqrt{T}}}}=d_{1}-\sigma{\sqrt{T}}
$$  

and $\sigma$ is the volatility of the futures price. When the cost of carry and the convenience yield are functions only of time, it can be shown that the volatility of the futures price is the same as the volatility of the underlying asset.  

# Example 18.6  

Consider a European put futures option on a commodity. The time to the option's maturity is 4 months, the current futures price is. $\$20$ , the exercise price is $\$20$ , the risk-free interest rate is $9\%$ per annum, and the volatility of the futures price is. $25\%$ per annum. In this case, $F_{0}=20,K=20,r=0.09,T=4/12,\sigma=0.25$ and $\ln(F_{0}/K)=0$ , so that  

$$
d_{1}=\frac{\sigma\sqrt{T}}{2}=0.07216
$$  

$$
d_{2}=-\frac{\sigma\sqrt{T}}{2}=-0.07216
$$  

$$
N(-d_{1})=0.4712,N(-d_{2})=0.5288
$$  

and the put price $p$ is given by  

$$
p=e^{-0.09\times4/12}(20\times0.5288-20\times0.4712)=1.12
$$  

or $\$1.12$  
