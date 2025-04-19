---
tags:
  - asian_option
  - average_price
  - corporate_treasury
  - derivative
  - option_pricing
aliases:
  - Asian
  - Asian Option
  - Average Price Option
  - Average Strike Option
key_concepts:
  - Average price call/put
  - Average strike option
  - Black's model application
  - Lognormal assumption
  - Payoff based on average
---

# 26.13 ASIAN OPTIONS  

Asian options are options where the payoff depends on the arithmetic average of the price of the underlying asset during the life of the option. The payoff from an average. price call is $\mathrm{max}(0,S_{\mathrm{ave}}-K)$ and that from an average price put is. $\mathrm{max}(0,K-S_{\mathrm{ave}})$ where $S_{\mathrm{ave}}$ is the average price of the underlying asset. Average price options tend to be less expensive than regular options and are arguably more appropriate than regular. options for meeting some of the needs of corporate treasurers. Suppose that a U.S. corporate treasurer expects to receive a cash flow of 100 million Australian dollars spread evenly over the next year from the company's Australian subsidiary. The. treasurer is likely to be interested in an option that guarantees that the average exchange. rate realized during the year is above some level. An average price put option can. achieve this more effectively than regular put options..  

Average price options can be valued using similar formulas to those used for regular. options if it is assumed that $S_{\mathrm{ave}}$ is lognomal. As it happens, when the usual assumption. is made for the process followed by the asset price, this is a reasonable assumption.10. A popular approach is to fit a lognormal distribution to the first two moments of. $S_{\mathrm{ave}}$ and use Black's model.11 Suppose that $M_{1}$ and $M_{2}$ are the first two moments of $S_{\mathrm{ave}}$ The value of average price calls and puts are given by equations (18.7) and (18.8), with  

$$
F_{0}=M_{1}
$$  

and  

$$
\sigma^{2}=\frac{1}{T}\ln\bigg(\frac{M_{2}}{M_{1}^{2}}\bigg)
$$  

When the average is calculated continuously, and $r,q$ and $\sigma$ are constant (as in DerivaGem):  

$$
M_{1}=\frac{e^{(r-q)T}-1}{(r-q)T}S_{0}
$$  

and  

$$
M_{2}=\frac{2e^{\left[2(r-q)+\sigma^{2}\right]T}S_{0}^{2}}{(r-q+\sigma^{2})(2r-2q+\sigma^{2})T^{2}}+\frac{2S_{0}^{2}}{(r-q)T^{2}}\Bigg(\frac{1}{2(r-q)+\sigma^{2}}-\frac{e^{(r-q)T}}{r-q+\sigma^{2}}\Bigg),
$$  

More generally, when the average is calculated from observations at times $T_{i}\left(1\leq i\leq m\right)$  

$$
M_{1}={\frac{1}{m}}\sum_{i=1}^{m}F_{i}\quad{\mathrm{and}}\quad M_{2}={\frac{1}{m^{2}}}{\bigg(}\sum_{i=1}^{m}F_{i}^{2}e^{\sigma_{i}^{2}T_{i}}+2\sum_{j=1}^{m}\sum_{i=1}^{j-1}F_{i}F_{j}e^{\sigma_{i}^{2}T_{i}}{\bigg)}
$$  

where $F_{i}$ and $\sigma_{i}$ are the forward price and implied volatility for maturity $T_{i}$ See Technical Note 27 on www-2.rotman.utoronto.ca/\~hull/TechnicalNotes for a proof of this.  

# Example 26.3  

Consider a newly issued average price call option on a non-dividend-paying stock where the stock price is 50, the strike price is 50, the stock price volatility is $40\%$ per annum, the risk-free rate is. $10\%$ per annum, and the time to maturity is 1 year. In this case, $S_{0}=50,K=50,r=0.1,q=0,\sigma=0.4$ and $T=1,$ If the average is calculated continuously, $M_{1}=52.59$ and $M_{2}=2\small{,}922.76$ From equations (26.3) and (26.4), $F_{0}=52.59$ and $\sigma=23.54\%$ . Equation (18.7), with. $K=50,T=1$ and $r=0.1$ , gives the value of the option as 5.62. When 12, 52, and 250 observations are used for the average, the price is 6.00, 5.70, and 5.63, respectively.  

We can modify the analysis to accommodate the situation where the option is not newly issued and some prices used to determine the average have already been observed. Suppose that the averaging period is composed of a period of length $t_{1}$ over which prices have already been observed and a future period of length $t_{2}$ (the remaining life of the option). Suppose that the average asset price during the first time period is $\overline{S}$ . The payoff from an average price call is  

$$
\mathrm{max}\biggl({\frac{\overline{{S}}t_{1}+S_{\mathrm{ave}}t_{2}}{t_{1}+t_{2}}}-K,0\biggr)
$$  

where $S_{\mathrm{ave}}$ is the average asset price during the remaining part of the averaging period.   
This is the same as.  

$$
\frac{t_{2}}{t_{1}+t_{2}}\operatorname*{max}(S_{\mathrm{ave}}-K^{*},0)
$$  

where  

$$
K^{*}=\frac{t_{1}+t_{2}}{t_{2}}K-\frac{t_{1}}{t_{2}}\overline{{S}}
$$  

When $\boldsymbol{K}^{*}>0$ , the option can be valued in the same way as a newly issued Asian option provided that we change the strike price from $K$ to $K^{*}$ and multiply the result by. $t_{2}/(t_{1}+t_{2})$ . Whend $\boldsymbol{K}^{*}<\boldsymbol{0}$ the option is certain to be exercised and can be valued as a forward contract. The value is.  

$$
\frac{t_{2}}{t_{1}+t_{2}}\left[M_{1}e^{-r t_{2}}-K^{*}e^{-r t_{2}}\right]
$$  

Another type of Asian option is an average strike option. An average strike call pays off $\mathrm{max}(0,S_{T}-S_{\mathrm{ave}})$ and an average strike put pays off $\mathrm{max}(0,S_{\mathrm{ave}}-S_{T})$ Average strike options can guarantee that the average price paid for an asset in frequent trading over a period of time is not greater than the final price. Alternatively, it can guarantee that the average price received for an asset in frequent trading over a period of time is not less than the final price. It can be valued as an option to exchange one asset for another when $S_{\mathrm{ave}}$ is assumed to be lognormal.  
