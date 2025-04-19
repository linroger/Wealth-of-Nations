---
tags:
  - information
  - information_filtration
  - multi_period_model
  - state_space
  - uncertainty
aliases:
  - Information flow
  - Partitions
  - Sigma-algebra
key_concepts:
  - Information filtration
  - Information representation
  - Multi-period model
  - Sigma-algebra construction
  - Uncertainty resolution over time
---

# 2.3 Information  

In a one-period model all uncertainty is resolved at time $t=1$ .At time $0$ we only know that the true state is an element in $\Omega$ . At time 1 we know exactly which state has been realized. In a multi-period model the uncertainty is gradually resolved. Investors will gradually know more. and more about the true state. For example, the dividends of assets at a given point in time are typically unknown before that time, but known afterwards. The consumption and investment. decisions taken by individuals at a given point in time will depend on the available information at. that time and therefore asset prices will also depend on the information known. We will therefore have to consider how to formally represent the flow of information through time.  

To illustrate how we can represent the information at different points in time, consider an example. of a two-period, three-date economy with six possible outcomes simply labeled 1 through 6. In Figure 2.1 each outcome is represented by a dashed horizontal line. The probability of each outcome is written next to each line. At time 0 we assume that investors are unable to rule out any of the six outcomes if a state could be ruled out from the start, it should not have been included in the model. This is indicated by the ellipse around the six dots/lines representing the possible. outcomes. At time 1, investors have learned either (i) that the true outcome is 1 or 2, (ii) that the true outcome is 3,4, or 5, or (ii) that the true outcome is 6. At time 2, all uncertainty has been resolved so that investors will know exactly which outcome is realized..  

We can represent the information available at any given point in time $t$ by a partition $\mathbf{F}_{t}$ of $\Omega$ which means that $\mathbf{F}_{t}$ is a collection of subsets. $F_{t1},F_{t2},...$ of $\Omega$ so that  

(i) the union of these subsets equal the entire set $\Omega$ $\cup_{k}F_{t k}=\Omega$ (ii) the subsets are disjoint: $F_{t k}\cap F_{t l}=\emptyset$ for all $k\neq l$  

In our example, the partition. $\mathbf{F}_{0}$ representing time 0 information (or rather lack of information) is the trivial partition consisting only of. $\boldsymbol{F}_{0}=\boldsymbol{\Omega}$ , i.e.  

$$
\begin{array}{r}{\mathbf{F}_{0}=\{\boldsymbol{\Omega}\}.}\end{array}
$$  

The partition $\mathbf{F}_{1}$ representing time 1 information consists of $F_{11}$ $F_{12}$ , and $F_{13}$ , i.e.  

$$
\mathbf{F}_{1}=\left\{\{1,2\},\{3,4,5\},\{6\}\right\}.
$$  

The partition $\mathbf{F}_{2}$ that represents time 2 information (full information) is  

$$
\mathbf{F}_{2}={\big\{}\{1\},\{2\},\{3\},\{4\},\{5\},\{6\}{\big\}}.
$$  

In a general multi-period model with a finite state space $\Omega$ , the information fow can be summarized by a sequence $(\mathbf{F}_{t})_{t\in\mathcal{T}}$ of partitions. Since investors learn more and more, the partitions should be increasingly fine, which more formally means that when $t<t^{\prime}$ , every set $F\in\mathbf{F}_{t^{\prime}}$ is a subset of some set in $\mathbf{F}_{t}$  

An alternative way of representing the information flow is in terms of an information filtration, i.e. a sequence $(\mathcal{F}_{t})_{t\in\mathcal{T}}$ of sigma-algebras on $\Omega$ . Given a partition $\mathbf{F}_{t}$ of $\Omega$ , we can construct a sigmaalgebra $\mathcal{F}_{t}$ as the set of all unions of (countably many) sets in $\mathbf{F}_{t}$ , including the "empty union", i.e. the empty set $\varnothing$ . Where $\mathbf{F}_{t}$ contains only the disjoint "decidable"' events at time $t$ $\mathcal{F}_{t}$ contains all "decidable" events at time $t$ . For our simple two-period example above we get  

$$
\begin{array}{c}{{\mathcal{F}_{0}=\{\emptyset,\Omega\},}}\ {{\mathrm{}}}\ {{\mathcal{F}_{1}=\{\emptyset,\{1,2\},\{3,4,5\},\{6\},\{1,2,3,4,5\},\{1,2,6\},\{3,4,5,6\},\Omega\},}}\end{array}
$$  

while ${\mathcal{F}}_{2}$ becomes the collection of all possible subsets of $\Omega$ . In a general multi-period model we write $(\mathcal{F}_{t})_{t\in\mathcal{T}}$ for the information filtration. We will always assume that the time $0$ information is trivial, corresponding to $\mathcal{F}_{0}=\{\emptyset,\Omega\}$ and that all uncertainty is resolved at or before the final date so that $\mathcal{F}_{T}$ is the set of all possible subsets of $\Omega$ . The fact that we learn more and more about the true state as time goes by implies that we must have $\mathcal{F}_{t}\subset\mathcal{F}_{t^{\prime}}$ whenever $t<t^{\prime}$ , i.e. every set in $\mathcal{F}_{t}$ is also in $\mathcal{F}_{t^{\prime}}$  

Above we constructed an information filtration from a sequence of partitions. We can also go from a filtration to a sequence of partitions. In each. $\mathcal{F}_{t}$ , simply remove all sets that are unions of. other sets in $\mathcal{F}_{t}$ . Therefore there is a one-to-one relationship between information filtration and a. sequence of partitions.  

In models with an infinite state space, the information filtration representation is preferable. In any case we will therefore generally write the formal model of uncertainty and information as a filtered probability space $(\Omega,\mathcal{F},\mathbb{P},(\mathcal{F}_{t})_{t\in\mathcal{T}})$ , where $\left(\Omega,\mathcal{F},\mathbb{P}\right)$ is a probability space and $(\mathcal{F}_{t})_{t\in\mathcal{T}}$ is an information filtration.  

Whenever the state space is finite we can alternatively represent the uncertainty and information fow by a multinomial tree. For example we can depict the uncertainty and information flow in Figure 2.1 by the multinomial tree in Figure 2.2. Each node at a given point in time corresponds to an element in the partition representing the information. For example the node labeled $F_{11}$ at time 1 represents the element $\{1,2\}$ of the partition $\mathbf{F}_{1}$ .We can think of $F_{11}$ $F_{12}$ , and $F_{13}$ as the three possible "scenarios' at time 1. At time $0$ , there is only one possible scenario. At. time 2, where all uncertainty is resolved, there are as many scenarios as states. The arrival of new information in a given period can be thought of as the transition from one scenario at the beginning of the period to a scenario at the end of the period. In our example, there are three possible transitions in the first period. If the economy is in scenario $F_{11}$ at time 1 (i.e. the true state is 1 or 2), there are two possible transitions over the next period, either to $F_{21}$ (state 1) or to $F_{22}$ (state 2). If the economy is in scenario. $F_{12}$ at time 1 (the true state is known to be 3, 4, or 5), there are three possible transitions over the next period, to $F_{23}$ (state 3), to $F_{24}$ (state 4), or to $F_{25}$ (state 5). If the economy is in scenario. $F_{13}$ at time 1, the true state is already known to be state 6, and there is only one possible transition over the next period, corresponding to no new information arriving. Each state corresponds to a path through the tree.  

The transitions are illustrated by the arrows in Figure 2.2. The numbers along the lines are conditional probabilities of the transitions happening. Over the first period there is really no. information to condition on. The transition from. $F_{0}$ to $F_{11}$ will happen with a probability of 0.3,. which is simply the sum of the probabilities of the two outcomes in $F_{11}$ , namely the probability of 0.24 for state 1 and the probability of 0.06 for state 2. Similarly for the other transitions over the first period. The probabilities assigned to the transitions over the second period are true. conditional probabilities. Conditional on the economy being in scenario $F_{11}$ at time 1, it will move to $F_{21}$ with a probability of $0.24/(0.24+0.06)=0.8$ since that is the probability of state 1 given. that the state is either 1 or 2 as represented by scenario $F_{11}$ . Similarly for the other transitions. over the second period. Of course, given the conditional probabilities in the multinomial tree, we can also recover the state probabilities. For example, the state $\omega=5$ corresponds to a transition from $F_{0}$ to $F_{12}$ over the first period, followed by a transition from $F_{12}$ to $F_{25}$ over the second period. The probability of this sequence of transitions is given by the product of the probabilities of each of the transitions, i.e. $0.4\cdot0.5=0.2$ , which equals the probability of state. $\omega=5$  

In our asset pricing models we will often deal with expectations of random variables, e.g. the. expectation of the dividend of an asset at a future point in time. In the computation of such an expectation we should take the information currently available into account. Hence we need to consider conditional expectations. Recall that the information at a given point in time. $t$ is represented by a $\sigma$ -algebra $\mathcal{F}_{t}$ (or, equivalently, a partition $\mathbf{F}_{t}$ ).  One can generally write the expectation of a random variable $X$ given the $\sigma$ -algebra $\mathcal{F}_{t}$ as $\operatorname{E}[X|{\mathcal{F}}_{t}]$ .For our purposes the $\sigma$ -algebra $\mathcal{F}_{t}$ will always represent the information at time $t$ and we will write $\operatorname{E}_{t}[X]$ instead of $\operatorname{E}[X|{\mathcal{F}}_{t}]$ . Since we assume that the information at time $0$ is trivial, conditioning on time $0$ information is the same as not conditioning on any information, hence $\operatorname{E}_{0}[X]=\operatorname{E}[X]$ . Since we assume that all uncertainty is resolved at time $T$ , we have $\operatorname{E}_{T}[X]=X$ . We will sometimes use the following result:  

Theorem 2.1 (The Law of Iterated Expectations) If $\mathcal{F}$ and $\mathcal{G}$ are two $\sigma$ -algebras with $\mathcal{F}\subseteq$ 9 and $X$ is a random variable, then. $\operatorname{E}\left[\operatorname{E}[X|\mathcal{G}]\mid\mathcal{F}\right]=\operatorname{E}[X|\mathcal{F}]$ .In particular, if. $(\mathcal{F}_{t})_{t\in\mathcal{T}}$ is an information filtration and. $t^{\prime}>t$ , we have  

$$
\operatorname{E}_{t}{\left[\operatorname{E}_{t^{\prime}}[X]\right]}=\operatorname{E}_{t}[X].
$$  

![](0dca89f9efdcb18897a0b8361b731f6d97f8f9fd468df7e3865c68f11ddc95c6.jpg)  
Figure 2.1: An example of a two-period economy.  

![](227e1cded9eecd2538f31d24690fa61bb466641d26841f976f43da2166c01e84.jpg)  
Figure 2.2: The multinomial tree version of the two-period economy in Figure 2.1.  

Loosely speaking, the theorem says that what you expect today of some variable that will be realized in two days is equal to what you expect today that you will expect tomorrow about the same variable.  

We can define conditional variances, covariances, and correlations from the conditional expectation exactly as one defines (unconditional) variances, covariances, and correlations from (unconditional) expectations:  

$$
{\begin{array}{r l}&{\operatorname{Var}_{t}[X]=\operatorname{E}_{t}\left[\left(X-\operatorname{E}_{t}[X]\right)^{2}\right]=\operatorname{E}_{t}[X^{2}]-\left(\operatorname{E}_{t}[X]\right)^{2},}\ &{\operatorname{Cov}_{t}[X,Y]=\operatorname{E}_{t}\left[(X-\operatorname{E}_{t}[X])(Y-\operatorname{E}_{t}[Y])\right]=\operatorname{E}_{t}[X Y]-\operatorname{E}_{t}[X]\operatorname{E}_{t}[Y],}\ &{\qquad\operatorname{Corr}_{t}[X,Y]={\frac{\operatorname{Cov}_{t}[X,Y]}{{\sqrt{\operatorname{Var}_{t}[X]\operatorname{Var}_{t}[Y]}}}}.}\end{array}}
$$  

Again the conditioning on time $t$ information is indicated by a $t$ subscript.  

In the two-period model of Figures 2.1 and 2.2 suppose we have an asset paying state-dependent. dividends at time 1 and 2 as depicted in Figures 2.3 and 2.4. Then the expected time 2 dividend computed at time $0$ is  

$$
\operatorname{E}[D_{2}]=\operatorname{E}_{0}[D_{2}]=0.24\cdot0+0.06\cdot20+0.04\cdot10+0.16\cdot5+0.2\cdot20+0.3\cdot20=12.4.
$$  

What is the expected time 2 dividend computed at time 1? It will depend on the information available at time 1. If the information corresponds to the event. $F_{11}=\{1,2\}$ , the expected dividend is  

$$
\operatorname{E}_{1}[D_{2}]=0.8\cdot0+0.2\cdot20=4.
$$  

If the information corresponds to the event $F_{12}=\{3,4,5\}$ , the expected dividend is.  

$$
\operatorname{E}_{1}[D_{2}]=0.1\cdot10+0.4\cdot5+0.5\cdot20=13.
$$  

If the information corresponds to the event $F_{13}=\{6\}$ , the expected dividend is  

$$
\mathrm{E}_{1}[D_{2}]=1.0\cdot20=20.
$$  

The time 1 expectation of the time 2 dividend is therefore a random variable which is measurable with respect to the information at time 1. Note that the time 0 expectation of that random variable is  

$$
\mathrm{E}\left[\mathrm{E}_{1}[D_{2}]\right]=0.3\cdot4+0.4\cdot13+0.3\cdot20=12.4=\mathrm{E}[D_{2}]
$$  

consistent with the Law of Iterated Expectations.  
