---
tags:
  - adapted_process
  - information_filtration
  - multi_period_model
  - random_variable
  - stochastic_process
aliases:
  - Stochastic Process Definition
  - Stochastic Process Notation
  - Stochastic Process Terminology
key_concepts:
  - Adapted stochastic process
  - Information filtration
  - Multi-period models
  - Random variable representation
  - Stochastic process definition
---

# 2.4 Stochastic processes: definition, notation, and terminology  

In one-period models all uncertain objects can be represented by a random variable. For example the dividend (at time 1) of a given asset is a random variable. In multi-period models we have to keep track of dividends, asset prices, consumption, portfolios, (labor) income, etc., throughout the time set $\mathcal{T}$ . For example the dividend of a given asset, say asset $i$ , at a particular future date $t\in\mathbb{T}$ can be represented by a random variable. $D_{i t}$ . Recall that, formally, a random variable is a function from the state space $\Omega$ into $\mathbb{R}$ , the set of real numbers. To represent the dividends of an asset throughout all dates, we need a collection of random variables, one for each date. Such a collection is called a stochastic process. (We will often just write "process" instead of "stochastic process.") The dividend of asset $i$ is thus represented by a stochastic process $D_{i}=(D_{i t})_{t\in\ensuremath{\mathbb{T}}}$ , where each $D_{i t}$ is a random variable. We can form multi-dimensional stochastic processes by stacking one-dimensional stochastic processes. For example, we can represent the dividends of $I$ assets by an $I$ -dimensional stochastic process $\pmb{D}=(\pmb{D}_{t})_{t\in\mathcal{T}}$ , where $\boldsymbol{D}_{t}=(D_{1t},\dots,D_{I t})^{\intercal}$  

![](7f009f2c64c1416d0a48f74b70bd85ac136f449620df47a2995d0ffece938a9b.jpg)  
Figure 2.3: The dividends of an asset in the two-period economy.  

![](dbe5340d08b14fab06df60bd4409d2b7472154211292b7eefa269d53d066f04a.jpg)  
Figure 2.4: The multinomial tree version of the dividend process in Figure 2.3.  

In general, for any $t\in\mathbb{T}$ , the dividend at time. $t$ will be known at time. $t$ , but not before. The random variable $D_{i t}$ is then said to be $\mathcal{F}_{t}$ -measurable, where $\mathcal{F}_{t}$ is the sigma-algebra representing. the information at time $t$ .If this information is equivalently represented by a partition. $\mathbf{F}_{t}~=$ $\{F_{t1},F_{t2},\dots\}$ , measurability means that. $D_{i t}$ is constant on each of the elements $F_{t j}$ of the partition. Note that this is indeed the case in our example in Figure 2.3. If. $D_{i t}$ is $\mathcal{F}_{t}$ -measurable for any $t\in\mathcal{T}$ the stochastic process $D_{i}=(D_{i t})_{t\in\ensuremath{\mathbb{T}}}$ is said to be adapted to the information filtration $(\mathcal{F}_{t})_{t\in\mathcal{T}}$ Since the dividends of assets and the income of individuals are assumed to be part of the exogenous. uncertainty, it is natural to assume that dividend processes and income processes are adapted to the information filtration. In fact, most concrete models write down stochastic processes for all the exogenous variables and define the information filtration as the smallest filtration to which these exogenous processes are adapted.  

An individual can choose how much to consume and which portfolio to invest in at any point in time, of course subject to a budget constraint and other feasibility constraints. The consumption and portfolio chosen at a given future date are likely to depend on the income the individual has received up to that point and her information about her future income and the future dividends of assets. The consumption rate at a given future date is therefore a random variable and the consumption rates at all dates constitute a stochastic process, the consumption process. Similarly, the portfolios chosen at different dates form a stochastic process, the portfolio process or so-called trading strategy. Representing consumption and investments by stochastic processes does not mean that we treat them as being exogenously given and purely determined by chance, but simply that the individual will condition her consumption and portfolio decisions on the information received. Since we assume that the underlying model of uncertainty includes all the uncertainty relevant for the decisions of the individuals, it is natural to require that consumption and portfolio processes are adapted to the information filtration.  

Now consider prices. In a multi-period model we need to keep track of prices at all points in time. The price of a given asset at a given point in time depends on the supply and demand for that asset of all individuals, which again depends on the information individuals have at that time. Hence, we can also represent prices by adapted stochastic processes. To sum up, all the stochastic process relevant for our purposes will be adapted to the information filtration representing the resolution of all the relevant uncertainty.  

Next, we introduce some further terminology often used in connection with stochastic processes. A stochastic process $X=(X_{t})_{t\in\mathcal{T}}$ is said to be a martingale (relative to the probability measure $\mathbb{P}$ and the information filtration $(\mathcal{F}_{t})_{t\in\mathcal{T}}$ ), if for all $t,t^{\prime}\in\mathcal{T}$ with $t<t^{\prime}$  

$$
\operatorname{E}_{t}[X_{t^{\prime}}]=X_{t},
$$  

i.e. no change in the value is expected.  

A sample path of a stochastic process $X$ is the collection of realized values. $(X_{t}(\omega))_{t\in\mathcal{T}}$ for a given outcome $\omega\in\Omega$ . The value space of a stochastic process is the smallest set S with the. property that $\mathbb{P}(\{X_{t}\in\mathcal{S}\})=1$ for all $t\in\mathcal{T}$ . If the value space has countably many elements,. the stochastic process is called a discrete-value process. Otherwise, it is called a continuous-value process. Of course, if the state space. $\Omega$ is finite, all processes will be discrete-value processes. If. you want to model continuous-value processes, you need an infinite state space..  

For the modeling of most time-varying economic objects it seems reasonable to use continuousvalue processes. Admittedly, stock prices are quoted on exchanges as multiples of some smallest possible unit (0.01 currency units in many countries) and interest rates are rounded off to some number of decimals, but the set of possible values of such objects is approximated very well by an interval in $\mathbb{R}$ (maybe $\mathbb{R}_{+}$ or $\mathbb{R}$ itself). Also, the mathematics involved in the analysis of continuous-value processes is simpler and more elegant than the mathematics for discrete-value processes. However there are economic objects that can only take on a very limited set of values. For these objects discrete-value processes should be used. An example is the credit ratings assigned by Moody's and similar agencies to debt issues of corporations.  

As time goes by, we can observe the evolution in the object which the stochastic process describes. At any given time $t^{\prime}$ , the previous values $(X_{t})_{t\in[0,t^{\prime})}$ , where $X_{t}\in\mathrm{{S}}$ , will be known (at least in the models we consider). These values constitute the history of the process up to time. $t^{\prime}$ . The future values are still stochastic.  

As time passes we will typically revise our expectations of the future values of the process or,. more precisely, revise the probability distribution we attribute to the value of the process at any. future point in time, cf. the discussion in the previous section. Suppose we stand at time $t$ and consider the value of a process $X$ at a future time $t^{\prime}>t$ . The distribution of the value of $X_{t^{\prime}}$ is characterized by probabilities. $\mathbb{P}(X_{t^{\prime}}\in A)$ for subsets $A$ of the value space S. If for all. $t,t^{\prime}\in\mathcal{T}$ with $t<t^{\prime}$ and all $A\subseteq{\mathcal{S}}$ , we have that  

$$
\mathbb{P}\left(X_{t^{\prime}}\in A\mid(X_{s})_{s\leq t}\right)=\mathbb{P}\left(X_{t^{\prime}}\in A\mid X_{t}\right),
$$  

then $X$ is called a Markov process. Broadly speaking, this condition says that, given the presence, the future is independent of the past. The history contains no information about the future value that cannot be extracted from the current value.  
