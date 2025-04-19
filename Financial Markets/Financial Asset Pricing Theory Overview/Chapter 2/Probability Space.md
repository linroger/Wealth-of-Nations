---
tags:
  - asset_pricing
  - probability_measure
  - probability_space
  - random_variable
  - state_space
aliases:
  - Probability Model
  - Probability Spaces
key_concepts:
  - Collection of events
  - Possible outcomes
  - Random variable on space
  - Realization of uncertain objects
  - State space for model
---

# 2.2 Probability space  

Any model with uncertainty refers to a probability space $(\Omega,{\mathcal{F}},\mathbb{P})$ , where  

: $\Omega$ is the state space of possible outcomes. An element $\omega\in\Omega$ represents a possible realization. of all uncertain objects of the model. An event is a subset of $\Omega$   
: $\mathcal{F}$ is a $\sigma$ -algebra in $\Omega$ , i.e. a collection of subsets of $\Omega$ with the properties (i) $\Omega\in{\mathcal{F}}$ (ii) for any set $F$ in $\mathcal{F}$ , the complement $F^{c}\equiv\Omega\setminus F$ is also in $\mathcal{F}$ (iii) if $F_{1},F_{2},\cdots\in\mathcal{F}$ , then the union $\cup_{n=1}^{\infty}F_{n}$ is in $\mathcal{F}$ $\mathcal{F}$ is the collection of all events that can be assigned a probability.   
. $\mathbb{P}$ is a probability measure, i.e. a function $\mathbb{P}:\mathcal{F}\to[0,1]$ with $\mathbb{P}(\Omega)=1$ and the property that $\begin{array}{r}{\mathbb{P}(\cup_{m=1}^{\infty}A_{m})=\sum_{m=1}^{\infty}\mathbb{P}(A_{m})}\end{array}$ for any sequence $A_{1},A_{2},\dots$ of disjoint events.  

An uncertain object can be formally modeled as a random variable on the probability space. A random variable $X$ on the probability space $\left(\Omega,\mathcal{F},\mathbb{P}\right)$ is a real-valued function on $\Omega$ which is $\mathcal{F}$ -measurable in the sense that for any interval $I\subseteq\mathbb{R}$ , the set $\{\omega\in\Omega\mid X(\omega)\in I\}$ belongs to $\mathcal{F}$ i.e. we can assign a probability to the event that the random variable takes on a value in $I$  

What is the relevant state space for an asset pricing model? A state. $\omega\in\Omega$ represents a possible realization of all relevant uncertain objects over the entire time span of the model. In one-period models dividends, incomes, etc. are realized at time 1. A state defines realized values of all the dividends and incomes at time 1. In multi-period models a state defines dividends, incomes, etc. at all points in time considered in the model, i.e. all. $t\in\mathcal{T}$ , where either $\mathcal{T}=\{0,1,2,\ldots,T\}$ or $\mathcal{T}=[0,T]$ . The state space must include all the possible combinations of realizations of the uncertain objects that may affect the pricing of the assets. These uncertain objects include all the possible combinations of realizations of (a) all the future dividends of all assets, (b) all the future incomes of all individuals, and (c) any other initially unknown variables that may affect prices,. e.g. variables that contain information about the future development in dividends or income. The state space $\Omega$ therefore has to be "large." If you want to allow for continuous random variables,. for example dividends that are normally distributed, you will need an infinite state space. If you restrict all dividends, incomes, etc. to be discrete random variables, i.e. variables with a finite number of possible realizations, you can do with a finite state space. For some purposes we need to distinguish between an infinite state space and a finite state space..  

![](c3b9f849e011d191529bc0e1d2961cb1d0afbc67a74674473701d7e0b39512b8.jpg)  

We will sometimes assume a finite state space in which case we will take it to be $\Omega=\{1,2,\dots,S\}$ so that there are $S$ possible states of which exactly one will be realized. An event is then simply a subset of $\Omega$ and $\mathcal{F}$ is the collection of all subsets of. $\Omega$ . The probability measure $\mathbb{P}$ is defined by the state probabilities. $p_{\omega}\equiv\mathbb{P}(\omega)$ $\omega=1,2,\ldots,S$ , which we take to be strictly positive with. $p_{1}+...p_{S}=1$ , of course. With a finite state space we can represent random variables with $S$ dimensional vectors and apply results and techniques from linear algebra. In any case we take the state probabilities as given and assume they are known to all individuals.  
