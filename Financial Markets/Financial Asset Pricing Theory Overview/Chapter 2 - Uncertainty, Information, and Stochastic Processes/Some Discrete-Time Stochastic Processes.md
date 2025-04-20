---
tags:
  - asset_pricing
  - discrete_time
  - markov_process
  - random_walk
  - stochastic_processes
aliases:
  - Discrete-time stochastic process
  - Stochastic process
key_concepts:
  - Autoregressive process
  - Exogenous shocks
  - Filtered probability space
  - Markov process
  - Random walk
---

# 2.5 Some discrete-time stochastic processes  

In most discrete-time financial models the basic uncertainty is described by a sequence $\varepsilon_{1},\varepsilon_{2},\dots,\varepsilon_{T}$ of random variables, one for each point in time. Think of $\varepsilon_{t}$ as an exogenous shock to the financial. market at time $t$ . We assume that the shocks at different points in time are mutually independent,. that each shock has a mean of zero and a variance of one. The shock at any given point in time $t$ can be multi-variate, in which case we will write it as a vector,. $\varepsilon_{t}$ . In that case the elements of. the vector are assumed to be mutually independent. We assume that the shocks at all points in time have the same dimension. The distribution of the exogenous shocks has to be specified in the model. Typically, the shocks are assumed to be normally distributed (infinite state space) but models with a binomial or multinominal structure (finite state space) also exist..  

The filtered probability space $(\Omega,\mathcal{F},\mathbb{P},(\mathcal{F}_{t})_{t\in\mathcal{T}})$ is defined implicitly from the assumptions on the exogenous shocks. For example, assume that the exogenous shocks $\varepsilon_{1},\ldots,\varepsilon_{T}$ are $N(0,1)$ distributed. The state space is then the set of all possible realizations of all the $T$ shocks, which is equivalent to $\mathbb{R}^{T}$ . The $\sigma$ -algebra $\mathcal{F}$ is the set of events that can be assigned a probability, which is the set of (Borel-)subsets of $\mathbb{R}^{T}$ . The probability measure $\mathbb{P}$ is defined via the normality assumption as  

$$
\mathbb{P}(\varepsilon_{t}<h)=N(h)\equiv\int_{-\infty}^{h}{\frac{1}{\sqrt{2\pi}}}e^{-a^{2}/2}d a,\quad t=1,\dots,T,
$$  

where $N(\cdot)$ is the cumulative distribution function for an $N(0,1)$ variable. Probabilities of other events will follow from the above. The information at time $t$ is represented by the smallest $\sigma$ -algebra with respect to which the random variables $\varepsilon_{1},\ldots,\varepsilon_{t}$ are measurable.  

Stochastic processes for dividends etc. can be defined relative to the assumed exogenous shocks. It is easy to obtain non-zero means, non-unit variances, and dependencies across time. A discrete-. time stochastic process $X=(X_{t})_{t\in\mathcal{T}}$ is typically specified by the initial value $X_{0}$ (a constant in $\mathbb{R}$ ) and the increments over each period, i.e.. $\Delta X_{t+1}\equiv X_{t+1}-X_{t}$ for each $t=0,1,\ldots,T-1$ . The increments $\Delta X_{t+1}$ are defined in terms of the exogenous shocks $\varepsilon_{1},\ldots,\varepsilon_{t+1}$ which implies that the. process $X$ is adapted.  

Let us look at some discrete-time stochastic processes frequently used in asset pricing models. In all the examples we assume that the exogenous shocks. $\varepsilon_{1},\ldots,\varepsilon_{T}$ are independent, one-dimensional $N(0,1)$ distributed random variables.  

Random walk: $\Delta X_{t+1}=\sigma\varepsilon_{t+1}$ or, equivalently, $X_{t+1}=X_{0}+\sigma(\varepsilon_{1}+\varepsilon_{2}+\cdot\cdot\cdot+\varepsilon_{t+1})$ . Here $\sigma$ is a positive constant. A random walk is a Markov process since only the current value $X_{t}$ and not the previous values. $X_{t-1},X_{t-2},...$ affect $X_{t+1}$ . Since the expected change over any single period is zero, the expected change over any time interval will be zero, so a random walk is a martingale. Conditionally on. $X_{t}$ $X_{t+1}$ is normally distributed with mean. $X_{t}$ and variance $\sigma^{2}$ $X_{t+1}$ is unconditionally (i.e. seen from time. $0$ ) normally distributed with mean. $X_{0}$ and variance $(t+1)\sigma^{2}$  

Random walk with drift: $\Delta X_{t+1}=\mu+\sigma\varepsilon_{t+1}$ , where $\mu$ is a constant (the drift rate) and $\sigma$ is a positive constant. Also a random walk with drift is a Markov process. The expected change over any single period is $\mu$ so unless $\mu=0$ and we are back to the random walk (without drift), the process $X=(X_{t})_{t\in\mathcal{T}}$ is not a martingale. Conditionally on $X_{t}$ $X_{t+1}$ is normally distributed with mean $\mu+X_{t}$ and variance $\sigma^{2}$ $X_{t+1}$ is unconditionally normally distributed with mean $X_{0}+(t+1)\mu$ and variance $(t+1)\sigma^{2}$  

Autoregressive processes: A process $X=(X_{t})_{t\in\mathcal{T}}$ with  

$$
\Delta X_{t+1}=(1-\rho)(\mu-X_{t})+\sigma\varepsilon_{t+1},
$$  

where $\rho\in(-1,1)$ , is said to be an autoregressive process of order 1 or simply an $\mathrm{AR}(1)$ process. It is a Markov process since only the current value $X_{t}$ affects the distribution of the future value. The expected change over the period is positive if $X_{t}<\mu$ and negative if $X_{t}>\mu$ . In any case, the value $X_{t+1}$ is expected to be closer to $\mu$ than $X_{t}$ is. The process is pulled towards $\mu$ and therefore the process is said to be mean-reverting. This is useful for modeling the dynamics of variables that tend to vary with the business cycle around some long-term average. Note, however, extreme shocks may cause the process to be pushed further away from $\mu$  

The covariance between the subsequent values $X_{t}$ and $X_{t+1}=X_{t}+(1-\rho)(\mu-X_{t})+\sigma\varepsilon_{t+1}=$ $\rho X_{t}+(1-\rho)\mu+\sigma\varepsilon_{t+1}$ is  

$$
\operatorname{Cov}[X_{t},X_{t+1}]=\rho\operatorname{Cov}[X_{t},X_{t}]=\rho\operatorname{Var}[X_{t}]
$$  

so that $\rho=\mathrm{Cov}[X_{t},X_{t+1}]/\operatorname{Var}[X_{t}]$ is the so-called auto-correlation parameter. Solving backwards, we find  

$$
\begin{array}{r l}&{X_{t+1}=\rho X_{t}+(1-\rho)\mu+\sigma\varepsilon_{t+1}}\ &{\qquad=\rho(\rho X_{t-1}+(1-\rho)\mu+\sigma\varepsilon_{t})+(1-\rho)\mu+\sigma\varepsilon_{t+1}}\ &{\qquad=\rho^{2}X_{t-1}+(1+\rho)(1-\rho)\mu+\sigma\varepsilon_{t+1}+\rho\sigma\varepsilon_{t}}\ &{\qquad=\ldots}\ &{\qquad=\rho^{k+1}X_{t-k}+(1+\rho+\cdots+\rho^{k})(1-\rho)\mu+\sigma\varepsilon_{t+1}+\rho\sigma\varepsilon_{t}+\cdots+\rho^{k}\sigma\varepsilon_{t-k+1}}\ &{\qquad=\rho^{k+1}X_{t-k}+(1-\rho^{k+1})\mu+\sigma\displaystyle\sum_{j=0}^{k}\rho^{j}\varepsilon_{t+1-j}.}\end{array}
$$  

More generally, a process $X=(X_{t})_{t\in\mathcal{T}}$ with  

$$
X_{t+1}=\mu+\rho_{1}(X_{t}-\mu)+\rho_{2}(X_{t-1}-\mu)+\cdot\cdot\cdot+\rho_{l}(X_{t-l+1}-\mu)+\sigma\varepsilon_{t+1}
$$  

is said to be an autoregressive process of order $l$ or simply an. $\mathrm{AR}(l)$ process. If the order is higher.   
than 1, the process is not a Markov process.  

(G)ARCH processes: ARCH is short for Autoregressive Conditional Heteroskedasticity. An $\mathrm{ARCH}(l)$ process $X=(X_{t})_{t\in\mathcal{T}}$ is defined by  

$$
X_{t+1}=\mu+\sigma_{t+1}\varepsilon_{t+1},
$$  

where  

$$
\sigma_{t+1}^{2}=\delta+\sum_{i=1}^{l}\alpha_{i}\varepsilon_{t+1-i}^{2}.
$$  

The conditional variance depends on squares of the previous l shock terms.  

GARCH is short for Generalized Autoregressive Conditional Heteroskedasticity. A GARCH $(l,m)$ process $X=(X_{t})_{t\in\mathcal{T}}$ is defined by  

$$
X_{t+1}=\mu+\sigma_{t+1}\varepsilon_{t+1},
$$  

where  

$$
\sigma_{t+1}^{2}=\delta+\sum_{i=1}^{l}\alpha_{i}\varepsilon_{t+1-i}^{2}+\sum_{j=1}^{m}\beta_{j}\sigma_{t+1-j}^{2}.
$$  

ARCH and GARCH processes are often used for detailed modeling of stock market volatility  

More generally we can define an adapted process $X=(X_{t})_{t\in\mathcal{T}}$ by the initial value $X_{0}$ and the equation  

$$
\Delta X_{t+1}=\mu(X_{t},\ldots,X_{0})+\sigma(X_{t},\ldots,X_{0})\varepsilon_{t+1},\quad t=0,1,\ldots,T-1,
$$  

where $\mu$ and $\sigma$ are real-valued functions. If $\varepsilon_{t+1}\sim N(0,1)$ , the conditional distribution of $X_{t+1}$ given $X_{t}$ is a normal distribution with mean $X_{t}+\mu(X_{t},\ldots,X_{0})$ and variance $\sigma(X_{t},\dots,X_{0})^{2}$  

We can write the stochastic processes introduced above in a different way that will ease the transition to continuous-time processes. Let $z=(z_{t})_{t\in\mathcal{T}}$ denote a unit random walk starting at. zero, i.e. a process with the properties.  

(i) $z_{0}=0$ (ii) $\Delta z_{t+1}\equiv z_{t+1}-z_{t}\sim N(0,1)$ for all $t=0,1,\ldots,T-1$ (iii) $\Delta z_{1},\Delta z_{2},...\Delta z_{T}$ are independent.  

Then we can define a random walk with drift as a process $X$ with  

$$
\Delta X_{t+1}=\mu+\sigma\Delta z_{t+1},
$$  

an $\mathrm{AR}(1)$ process is defined by  

$$
\Delta X_{t+1}=(1-\rho)(\mu-X_{t})+\sigma\Delta z_{t+1},
$$  

and a general adapted process is defined by  

$$
\Delta X_{t+1}=\mu(X_{t},\ldots,X_{0})+\sigma(X_{t},\ldots,X_{0})\Delta z_{t+1}.
$$  

We will see very similar equations in continuous time.  
