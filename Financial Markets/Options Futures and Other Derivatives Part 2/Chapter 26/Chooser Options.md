---
tags:
  - call_option
  - chooser_options
  - european_options
  - option_valuation
  - put_call_parity
aliases:
  - As You Like It Option
  - Chooser
  - Chooser Option
key_concepts:
  - Call or put selection
  - Chooser option definition
  - Complex chooser options
  - Put-call parity application
  - Valuation formula derivation
---

# 26.8 CHOOSER OPTIONS  

A chooser option (sometimes referred to as an as you like it option) has the feature that, after a specified period of time, the holder can choose whether the option is a call or a put. Suppose that the time when the choice is made is $T_{1}$ . The value of the chooser option at this time is  

$$
\mathrm{max}(c,p)
$$  

where $c$ is the value of the call underlying the option and $p$ is the value of the put underlying the option.  

If the options underlying the chooser option are both European and have the same strike price, put-call parity can be used to provide a valuation formula. Suppose that $S_{1}$  

is the asset price at time $T_{1},K$ is the strike price, $T_{2}$ is the maturity of the options, and $r$ is the risk-free interest rate. Put-call parity implies that  

$$
\begin{array}{r l}&{\operatorname*{max}(c,p)=\operatorname*{max}(c,c+K e^{-r(T_{2}-T_{1})}-S_{1}e^{-q(T_{2}-T_{1})})}\ &{\qquad=c+e^{-q(T_{2}-T_{1})}\operatorname*{max}(0,K e^{-(r-q)(T_{2}-T_{1})}-S_{1})}\end{array}
$$  

This shows that the chooser option is a package consisting of:  

1. A call option with strike price $K$ and maturity $T_{2}$   
2. $e^{-q(T_{2}-T_{1})}$ put options with strike price $K e^{-(r-q)(T_{2}-T_{1})}$ and maturity $T_{1}$  

As such, it can readily be valued.  

More complex chooser options can be defined where the call and the put do not have the same strike price and time to maturity. They are then not packages and have features that are somewhat similar to compound options.  
