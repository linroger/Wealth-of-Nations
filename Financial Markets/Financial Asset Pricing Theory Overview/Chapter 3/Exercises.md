---
tags:
  - arbitrage
  - call_option
  - no_arbitrage
  - one_period_model
  - risk_free_asset
aliases:
  - Exercise 3.1
  - Exercise 3.2
  - Exercise 3.3
  - Exercise 3.4
key_concepts:
  - Law of One Price
  - arbitrage-free market
  - market complete
  - no-arbitrage price
  - one-period model
  - risk-free asset
  - risk-free dividend
---

# 3.8 Exercises  

EXERCISE 3.1 Consider a one-period model with only two possible end-of-period states. Three assets are traded in an arbitrage-free market. Asset 1 is a risk-free asset with a price of 1 and an end-of-period dividend of $R^{f}$ , the risk-free gross rate of return. Asset 2 has a price of $S$ and offers. a dividend of. $u S$ in state. $^{1}$ and $d S$ in state 2..  

(a) Show that if the inequality. $d<R^{f}<u$ does not hold, there will be an arbitrage.  

Asset 3 is a call-option on asset 2 with an exercise price of $K$ . The dividend of asset 3 is therefore $C_{u}\equiv\operatorname*{max}(u S-K,0)$ in state 1 and $C_{d}\equiv\operatorname*{max}(d S-K,0)$ in state 2.  

(b) Show that a portfolio consisting of $\theta_{1}$ units of asset $1$ and $\theta_{2}$ units of asset 2, where  

$$
\theta_{1}=(R^{f})^{-1}\frac{u C_{d}-d C_{u}}{u-d},\quad\theta_{2}=\frac{C_{u}-C_{d}}{(u-d)S}
$$  

will generate the same dividend as the option.  

(c) Show that the no-arbitrage price of the option is given by  

$$
C=(R^{f})^{-1}\left(q C\boldsymbol{u}+(1-q)C_{d}\right),
$$  

where $q=(R^{f}-d)/(u-d)$  

EXERCISE 3.2 Imagine a one-period economy with two possible end-of-period states that are. equally likely. Two assets are traded. Asset 1 has an initial price of 1 and pays off 1 in state 1 and 2 in state 2. Asset 2 has an initial price of 3 and gives a payoff of 2 in state 1 and a payoff $k$ in state 2, where $k$ is some constant.  

(a) Argue that if $k=4$ , the Law of One Price does not hold. Is the Law of One Price violated for other values of $k$   
(b) For what values of $k$ is the market complete?   
(c) For what values of $k$ is the market free of arbitrage?   
(d) Assume $k=8$ . Is it possible to obtain a risk-free dividend? If so, what is the risk-free rate?  

EXERCISE 3.3 Verify Equation (3.4).  

EXERCISE 3.4 In a one-period two-state economy the risk-free interest rate over the period is $25\%$ . An asset that pays out 100 in state 1 and 200 in state 2 trades at a price of 110.  

(a) What is the no-arbitrage price of a second risky asset that pays out 200 in state 1 and 100 in state 2?   
(b) If this second risky asset trades at a higher price than what you computed in (a), how can you obtain a risk-free profit?  
