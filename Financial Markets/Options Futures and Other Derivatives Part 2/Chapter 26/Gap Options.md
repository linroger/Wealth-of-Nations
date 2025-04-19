---
tags:
  - black_scholes_merton_bsm
  - european_call_option
  - gap_call_option
  - gap_put_option
  - option_pricing
aliases:
  - Black-Scholes-Merton
  - Gap call
  - Gap put
key_concepts:
  - Asset value
  - Black-Scholes formula
  - Gap call option
  - Gap put option
  - Option payoff
---

# 26.4 GAP OPTIONS  

A gap call option is a European call options that pays off. $S_{T}-K_{1}$ when $S_{T}>K_{2}$ . The difference between a gap call option and a regular call option with a strike price of $K_{2}$ is that the payoff when. $S_{T}>K_{2}$ is increased by $K_{2}\mathrm{~-~}K_{1}$ . (This increase is positive or. negative depending on whether $K_{2}>K_{1}$ or $K_{1}>K_{2}$  

A gap call option can be valued by a small modification to the Black-ScholesMerton formula. With our usual notation, the value is.  

$$
S_{0}e^{-q T}N(d_{1})-K_{1}e^{-r T}N(d_{2})
$$  

where  

$$
\begin{array}{l}{\displaystyle{d_{1}=\frac{\ln(S_{0}/K_{2})+(r-q+\sigma^{2}/2)T}{\sigma\sqrt{T}}}}\ {{}}\ {{d_{2}=d_{1}-\sigma\sqrt{T}}}\end{array}
$$  

The price in this formula is greater than the price given by the Black-Scholes-Merton formula for a regular call option with strike price $K_{2}$ by  

$$
(K_{2}-K_{1})e^{-r T}N(d_{2})
$$  

To understand this difference, note that the probability that the option will be exercised is $N(d_{2})$ and, when it is exercised, the payoff to the holder of the gap option is greater than that to the holder of the regular option by $K_{2}\mathrm{~-~}K_{1}$  

For a gap put option, the payoff is $K_{1}-S_{T}$ when $S_{T}<K_{2}$ . The value of the option is  

$$
K_{1}e^{-r T}N(-d_{2})\:-\:S_{0}e^{-q T}N(-d_{1})
$$  

where $d_{1}$ and $d_{2}$ are defined as for equation (26.1).  

# Example 26.1  

An asset is currently worth $\$500,000$ . Over the next year, its price is expected to. have a volatility of. $20\%$ . The risk-free rate is. $5\%$ , and no income is expected. Suppose that an insurance company agrees to buy the asset for $\$400,000$ if its value has fallen below $\$400,000$ at the end of one year. The payout will be. $400,000-S_{T}$ whenever the value of the asset is less than. $\$400,000$ . The insurance company has provided a regular put option where the policyholder has the right to sell the asset to the insurance company for. $\$400,000$ in one year. This can be valued using. equation (15.21), with $S_{0}=500,000,K=400,000,r=0.05,\sigma=0.2$ $T=1$ The value is $\$3,436$  

Suppose next that the cost of transferring the asset is. $\$50,000$ and this cost is borne by the policyholder. The option is then exercised only if the value of the asset is less than $\$350,000$ . In this case, the cost to the insurance company is. $K_{1}-S_{T}$ when $S_{T}<K_{2}$ , where $K_{2}=350\small{,}000$ $K_{1}=400{,}000$ , and $S_{T}$ is the price of the asset in one year. This is a gap put option. The value is given by equa-. tion (26.2), with $S_{0}=500{,}000$ $K_{1}=400{,}000$ $K_{2}=350\small{,}000$ $r=0.05$ $q=0$ $\sigma=0.2$ $T=1,$ It is $\$1,896$ . Recognizing the costs to the policyholder of making. a claim reduces the cost of the policy to the insurance company by about. $45\%$ in this case.  
