---
tags:
  - '#american_options'
  - '#european_options'
  - '#futures_options'
  - '#in_the_money_options'
  - '#option_pricing_bounds'
  - '#out_of_the_money_options'
  - '#put_call_parity'
---
# 18.5 BOUNDS FOR FUTURES OPTIONS  

The put-call parity relationship in equation (18.1) provides bounds for European call and put options. Because the price of a put, $p$ , cannot be negative, it follows from equation (18.1) that  

$$
c+K e^{-r T}\geq F_{0}e^{-r T}
$$  

so that  

$$
c\geq\operatorname*{max}((F_{0}-K)e^{-r T},0)
$$  

Similarly, because the price of a call option cannot be negative, it follows from equation (18.1) that  

$$
K e^{-r T}\leq F_{0}e^{-r T}+p
$$  

so that  

$$
p\ge\operatorname*{max}((K-F_{0})e^{-r T},0)
$$  

These bounds are analogous to the ones derived for European stock options in Chapter 11. The prices of European call and put options are very close to their lower bounds when the options are deep in the money. To see why this is so, we return to the put-call parity relationship in equation (18.1). When a call option is deep in the money, a put option with the same strike price is deep out of the money. This means that. $p$ is very close to zero. The difference between. $c$ and its lower bound equals. $p$ , so that the price of the call option must be very close to its lower bound. A similar argument. applies to put options.  

Because American futures options can be exercised at any time, we must have  

and  

$$
\begin{array}{l}{C\geq\operatorname*{max}(F_{0}-K,0)}\ {{}}\ {P\geq\operatorname*{max}(K-F_{0},0)}\end{array}
$$  

Thus, assuming interest rates are positive, the lower bound for an American option  

price is always higher than the lower bound for the corresponding European option price. There is always some chance that an American futures option will be exercised early.  
