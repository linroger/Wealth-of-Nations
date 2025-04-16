---
tags:
  - '#adaptive_mesh_model'
  - '#alternative_tree_building_procedure'
  - '#american_call_option'
  - '#binomial_tree'
  - '#foreign_currency_option'
  - '#option_valuation'
  - '#risk_neutral_world'
  - '#trinomial_trees'
---
# 21.4 ALTERNATIVE PROCEDURES FOR CONSTRUCTING TREES  

The Cox, Ross, and Rubinstein approach described so far is not the only way of building a binomial tree. The change in ln $S$ in time $\Delta t$ in a risk-neutral world has mean $(r-q-\sigma^{2}/2)\Delta t$ and standard deviation $\sigma\sqrt{\Delta t}$ These can be matched by setting $p=0.5$ and  

$$
u=e^{(r-q-\sigma^{2}/2)\Delta t+\sigma\sqrt{\Delta t}},\qquadd=e^{(r-q-\sigma^{2}/2)\Delta t-\sigma\sqrt{\Delta t}}
$$  

This alternative tree-building procedure has the advantage over the Cox, Ross, and  

Rubinstein approach that the probabilities are always 0.5 regardless of the value of. $\upsigma$ or the number of time steps. Its disadvantage is that it is not quite as straightforward to. calculate delta, gamma, and theta from the tree because the tree is no longer centered at the initial stock price.  

# Example 21.6  

Consider a 9-month American call option on a foreign currency. The foreign currency is worth 0.7900 when measured in the domestic currency, the strike price is 0.7950, the domestic risk-free interest rate is $6\%$ per annum, the foreign risk-free interest rate is $10\%$ per annum, and the volatility of the exchange rate is $4\%$ per annum. In this case, $S_{0}=0.79,K=0.795,r=0.06,r_{f}=0.10,\sigma=0.04,$ and  

Figure 21.11 Binomial tree for American call option on a foreign currency. At each node, upper number is spot exchange rate and lower number is option price. All probabilities are 0.5.  

At each node: Upper value $=$ Underlying Asset Price Lower value $=$ Option Price Shading indicates where option is exercised  

Strike price $=0.795$ Discount factor per step $=0.9851$ Time step, $\mathsf{d t}=0.2500$ years, 91.25 days  

![](images/9b613e56b67c5fb924e1f1130d5f9c83951617665361e0259d501a34dcfb33a1.jpg)  

$T=0.75$ Using the alternative tree-building procedure, we set $\Delta t=0.25$ (3 steps) and the probabilities on each branch to 0.5, so that  

$$
\begin{array}{l l}{{u=e^{(0.06-0.10-0.0016/2)0.25+0.04{\sqrt{0.25}}}=1.0098}}\ {{}}\ {{d=e^{(0.06-0.10-0.0016/2)0.25-0.04{\sqrt{0.25}}}=0.9703}}\end{array}
$$  

The tree for the exchange rate is shown in Figure 21.11. The tree gives the value of the option as $\$0.0026$  

# Trinomial Trees  

Trinomial trees can be used as an alternative to binomial trees. The general form of the tree is as shown in Figure 21.12. Suppose that. $p_{u},p_{m}$ and $p_{d}$ are the probabilities of. up, middle, and down movements at each node and. $\Delta t$ is the length of the time step.. For an asset paying dividends at a rate $q$ , parameter values that match the mean and standard deviation of changes in ln $S$ are  

$$
u=e^{\sigma{\sqrt{3\Delta t}}},~d=1/u
$$  

$$
p_{d}=-\sqrt{\frac{\Delta t}{12\sigma^{2}}}\bigg(r-q-\frac{\sigma^{2}}{2}\bigg)+\frac{1}{6},p_{m}=\frac{2}{3},p_{u}=\sqrt{\frac{\Delta t}{12\sigma^{2}}}\bigg(r-q-\frac{\sigma^{2}}{2}\bigg)+\frac{1}{6}
$$  

Calculations for a trinomial tree are analogous to those for a binomial tree. We work from the end of the tree to the beginning. At each node we calculate the value of.  

![](images/b79aff022801bf7e7cbf35a0bcfff5850f2e8f6f3078479d1b5b61725edf1b76.jpg)  
Figure 21.12 Trinomial stock price tree.  

exercising and the value of continuing. The value of continuing is  

$$
e^{-r\Delta t}(p_{u}f_{u}+p_{m}f_{m}+p_{d}f_{d})
$$  

where $f_{u},f_{m}$ and $f_{d}$ are the values of the option at the subsequent up, middle, and down nodes, respectively. The trinomial tree approach proves to be equivalent to the explicit finite difference method, which will be described in Section 21.8.  

Figlewski and Gao have proposed an enhancement of the trinomial tree method, which they call the adaptive mesh model. In this, a high-resolution (small-. $\Delta t$ ) tree is grafted onto a low-resolution (large-. $\Delta t$ ) tree.' When valuing a regular American. option, high resolution is most useful for the parts of the tree close to the strike price at the end of the life of the option..  
