---
tags:
  - '#bear_spreads'
  - '#bull_spreads'
  - '#butterfly_spreads'
  - '#calendar_spreads'
  - '#european_options'
  - '#packages'
  - '#range_forward_contract'
  - '#straddles'
  - '#strangles'
  - '#zero_cost_product'
---
# 26.1 PACKAGES  

A package is a portfolio consisting of standard European calls, standard European. puts, forward contracts, cash, and the underlying asset itself. We discussed a number of different types of packages in Chapter 12: bull spreads, bear spreads, butterfly spreads,. calendar spreads, straddles, strangles, and so on..  

Often a package is structured by traders so that it has zero cost initially. An example is a range forward contract.1 This was discussed in Section 17.2. It consists of a long call and a short put or a short call and a long put. The call strike price is greater than the put strike price and the strike prices are chosen so that the value of the call equals the value of the put.  

It is worth noting that any derivative can be converted into a zero-cost product by deferring payment until maturity. Consider a European call option. If $c$ is the cost of the option when payment is made at time zero, then $\bar{A}=c e^{r T}$ is the cost when payment is made at time $T.$ the maturity of the option. The payoff is then $\operatorname*{max}(S_{T}-K,0)-A$ or $\operatorname*{max}(S_{T}-K-A,-A)$ . When the strike price, $K$ , equals the forward price, other names for a deferred payment option are break forward, Boston option, forward with optional exit, and cancelable forward.  
