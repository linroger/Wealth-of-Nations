---
tags:
  - '#asset_price'
  - '#binomial_model'
  - '#discrete_time_derivatives'
  - '#general_equilibrium_theory'
  - '#option_pricing'
  - '#risk_aversion'
  - '#risk_neutral_pricing'
---
# 6.7 PRICING OPTIONS UNDER RISK AVERSION

If risk-averse investors insisted on pricing options by incorporating their risk aversion, they. should still arrive at the correct price. They would use the true probabilities,. $q$ and $1-q_{:}$ to discount the expected option payoff. Let $k_{o}$ be the discount rate of the option. For our example in which the arbitrage-free price of the option is 11.19, the option payoffs are 25 and zero, and the true probabilities are. $60\%$ and $40\%$ , the option discount rate would be found as the solution to the following:

$$
\begin{array}{r l r}{\mathbb{S}25(0.6)+\mathbb{S}0(0.4)}&{{}=\mathbb{S}11.19}&{}\ {1+k_{o}}&{{}}&{}\ {k_{o}=0.3405.}&{{}}&{}\end{array}
$$

In other words, the discount rate on the option would be $34.05\%$

The beauty of risk-neutral pricing is that we do not have to come up with the $34.05\%$ rate, nor do we have to come up with the true probabilities. All we have to know is the asset price, $S_{:}$ the values of $\boldsymbol{\mathscr{u}}$ and $d$ that describe the asset's volatility, and the risk-free rate, $r$ These requirements are far less onerous..

It is important to note that risk-neutral pricing never asks how the asset price was. obtained. It takes that price as being given in a market in which the buyer of the asset. trades with the seller of the asset. A trade produces an asset price. Using that asset price, the price of the option can be obtained. What we do not know from option pricing is how that asset price was obtained. That is the subject of general equilibrium theory, which is a branch of economics and financial economics that studies how prices are determined in markets with buyers and sellers whose risk aversion influences how they price assets. In finance, models such as the CAPM are general equilibrium models. Models such as the arbitrage pricing theory and virtually all option pricing models are not general equilibrium. models because they take market equilibrium as given without any regard to how that. equi they expl in C man

![](images/c299057348044fc7ec3389910504d6c8792a9c3d6f3bf92e02d27a0c7460e9d0.jpg)

# Discrete Time Derivatives Pricing Theory

# The Binomial Model

to one level or down to another. We called this model the two-state or binomial model. In this chapter, we derive the model more formally. This work is attributed to Cox, Ross, and Rubinstein (1979) and Rendleman and Bartter (1979). An excellent book on binomial models in finance is by van der Hoek and Elliott (2006).
