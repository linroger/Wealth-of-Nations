---
tags:
  - american_options
  - binomial_tree
  - correlated_assets
  - option_pricing
  - risk_neutral
aliases:
  - Options on Correlated Assets
  - Two Asset Options
key_concepts:
  - American option valuation
  - Binomial tree construction
  - Correlated asset pricing
  - Nonrectangular tree method
  - Transforming variables
---

# 27.7 OPTIONS ON TWO CORRELATED ASSETS  

Another tricky numerical problem is that of valuing American options dependent on two assets whose prices are correlated. A number of alternative approaches have been suggested. This section will explain three of these.  

# Transforming Variables  

It is relatively easy to construct a tree in three dimensions to represent the movements of two uncorrelated variables. The procedure is as follows. First, construct a two-. dimensional tree for each variable, and then combine these trees into a single three-. dimensional tree. The probabilities on the branches of the three-dimensional tree are. the product of the corresponding probabilities on the two-dimensional trees. Suppose,. for example, that the variables are stock prices, $S_{1}$ and $S_{2}$ . Each can be represented in two dimensions by a Cox, Ross, and Rubinstein binomial tree. Assume that. $S_{1}$ has a probability $p_{1}$ of moving up by a proportional amount $u_{1}$ and a probability $1-p_{1}$ of moving down by a proportional amount $d_{1}$ . Suppose further that $S_{2}$ has a probability $p_{2}$ of moving up by a proportional amount $u_{2}$ and a probability $1-p_{2}$ of moving down by a proportional amount $d_{2}$ In the three-dimensional tree there are four branches emanating from each node. The probabilities are:  

$p_{1}p_{2}$ .. $S_{1}$ increases; $S_{2}$ increases $p_{1}(1-p_{2})$ .. $S_{1}$ increases; $S_{2}$ decreases $(1-p_{1})p_{2}$ .. $S_{1}$ decreases; $S_{2}$ increases $(1-p_{1})(1-p_{2})$ .. $S_{1}$ decreases; $S_{2}$ decreases  

Consider next the situation where. $S_{1}$ and $S_{2}$ are correlated. Suppose that the riskneutral processes are:  

$$
\begin{array}{r}{d S_{1}=(r-q_{1})S_{1}d t+\sigma_{1}S_{1}d z_{1}}\ {d S_{2}=(r-q_{2})S_{2}d t+\sigma_{2}S_{2}d z_{2}}\end{array}
$$  

and the instantaneous correlation between the Wiener processes, $d z_{1}$ and $d z_{2}$ , is $\rho$ . This means that  

$$
\begin{array}{r}{d\ln S_{1}=(r-q_{1}-\sigma_{1}^{2}/2)d t+\sigma_{1}d z_{1}}\ {d\ln S_{2}=(r-q_{2}-\sigma_{2}^{2}/2)d t+\sigma_{2}d z_{2}}\end{array}
$$  

Two new uncorrelated variables can be defined:26  

$$
\begin{array}{r}{x_{1}=\sigma_{2}\ln S_{1}+\sigma_{1}\ln S_{2}}\ {x_{2}=\sigma_{2}\ln S_{1}-\sigma_{1}\ln S_{2}}\end{array}
$$  

These variables follow the processes  

$$
\begin{array}{r l}&{d x_{1}=[\sigma_{2}(r-q_{1}-\sigma_{1}^{2}/2)+\sigma_{1}(r-q_{2}-\sigma_{2}^{2}/2)]d t+\sigma_{1}\sigma_{2}\sqrt{2(1+\rho)}d z_{A}}\ &{d x_{2}=[\sigma_{2}(r-q_{1}-\sigma_{1}^{2}/2)-\sigma_{1}(r-q_{2}-\sigma_{2}^{2}/2)]d t+\sigma_{1}\sigma_{2}\sqrt{2(1-\rho)}d z_{B}}\end{array}
$$  

where $d\boldsymbol{z}_{A}$ and $d\boldsymbol{z}_{B}$ are uncorrelated Wiener processes.  

The variables $x_{1}$ and $x_{2}$ can be modeled using two separate binomial trees. In time $\Delta t$ $x_{i}$ has a probability $p_{i}$ of increasing by $h_{i}$ and a probability $1-p_{i}$ of decreasing by $h_{i}$ The variables $h_{i}$ and $p_{i}$ are chosen so that the tree gives correct values for the first two moments of the distribution of $x_{1}$ and $x_{2}$ . Because they are uncorrelated, the two trees can be combined into a single three-dimensional tree, as already described. At each node of the tree,. $S_{1}$ and $S_{2}$ can be calculated from $x_{1}$ and $x_{2}$ using the inverse. relationships  

$$
S_{1}=\mathrm{exp}\bigg[\frac{x_{1}+x_{2}}{2\sigma_{2}}\bigg]\quad\mathrm{and}\quad S_{2}=\mathrm{exp}\bigg[\frac{x_{1}-x_{2}}{2\sigma_{1}}\bigg]
$$  

The procedure for rolling back through a three-dimensional tree to value a derivative is analogous to that for a two-dimensional tree.  

# Using a Nonrectangular Tree  

Rubinstein has suggested a way of building a three-dimensional tree for two correlated stock prices by using a nonrectangular arrangement of the nodes.27 From a node $(S_{1},S_{2})$ , where the first stock price is $S_{1}$ and the second stock price is $S_{2}$ , there is a 0.25 chance of moving to each of the following:  

$$
(S_{1}u_{1},S_{2}A),\quad(S_{1}u_{1},S_{2}B),\quad(S_{1}d_{1},S_{2}C),\quad(S_{1}d_{1},S_{2}D)
$$  

where  

$$
\begin{array}{r}{u_{1}=\exp[(r-q_{1}-\sigma_{1}^{2}/2)\Delta t+\sigma_{1}\sqrt{\Delta t}]}\ {d_{1}=\exp[(r-q_{1}-\sigma_{1}^{2}/2)\Delta t-\sigma_{1}\sqrt{\Delta t}]}\end{array}
$$  

and  

$$
\begin{array}{l}{A=\exp[(r-q_{2}-\sigma_{2}^{2}/2)\Delta t+\sigma_{2}\sqrt{\Delta t}(\rho+\sqrt{1-\rho^{2}})]}\ {B=\exp[(r-q_{2}-\sigma_{2}^{2}/2)\Delta t+\sigma_{2}\sqrt{\Delta t}(\rho-\sqrt{1-\rho^{2}})]}\ {C=\exp[(r-q_{2}-\sigma_{2}^{2}/2)\Delta t-\sigma_{2}\sqrt{\Delta t}(\rho-\sqrt{1-\rho^{2}})]}\ {D=\exp[(r-q_{2}-\sigma_{2}^{2}/2)\Delta t-\sigma_{2}\sqrt{\Delta t}(\rho+\sqrt{1-\rho^{2}})]}\end{array}
$$  

When the correlation is zero, this method is equivalent to constructing separate trees for $S_{1}$ and $S_{2}$ using the alternative binomial tree construction method in Section 21.4.  

# Adjusting the Probabilities  

A third approach to building a three-dimensional tree for $S_{1}$ and $S_{2}$ involves first assuming no correlation and then adjusting the probabilities at each node to reflect the correlation.8 The alternative binomial tree construction method for each of $S_{1}$ and $S_{2}$ in Section 21.4 is used. This method has the property that all probabilities are 0.5. When the two binomial trees are combined on the assumption that there is no correlation, the probabilities are as shown in Table 27.2. When the probabilities are adjusted to reflect the correlation, they become those shown in Table 27.3.  
