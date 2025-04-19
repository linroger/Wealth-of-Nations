---
tags:
  - arbitrage_free
  - one_period_economy
  - optimal_consumption
  - risk_free_asset
  - state_dependent_utility
aliases:
  - Exercise 6.1
  - Exercise 6.2
  - Exercise 6.3
  - Exercise 6.4
  - Exercise 6.5
key_concepts:
  - arbitrage-free market
  - logarithmic utility
  - mean-variance
  - one-period economy
  - optimal consumption plan
  - risk-free asset
  - risk-free interest rate
  - state price vector
  - state-dependent utility
  - state-price deflator
---

# 6.8 Exercises  

EXERCISE 6.1 Consider a one-period economy and an individual with a time-additive but state-dependent expected utility so that the objective is.  

$$
\operatorname*{max}_{\theta}u(c_{0},X_{0})+e^{-\delta}\operatorname{E}[u(c,X)].
$$  

The decisions of the individual do not affect. $X_{0}$ or $X$ .For example, $X_{0}$ and $X$ could be the aggregate consumption in the economy at time 0 and time. $^{1}$ , respectively, which are not significantly. affected by the consumption of a small individual. What is the link between prices and marginal utility in this case? What if $\begin{array}{r}{u(c,X)=\frac{1}{1-\gamma}(c-X)^{1-\gamma}}\end{array}$ ? What if $\begin{array}{r}{u(c,X)=\frac{1}{1-\gamma}(c/X)^{1-\gamma}?}\end{array}$  

EXERCISE 6.2  Consider a one-period economy where four basic financial assets are traded. without portfolio constraints or transaction costs. There are four possible end-of-period states of the economy. The objective state probabilities and the prices and state-contingent dividends of the assets are given in the following table:.  

<html><body><table><tr><td></td><td>state 1</td><td>state 2</td><td>state3</td><td>state 4</td><td></td></tr><tr><td>probability</td><td>6</td><td>1 4</td><td>1 4</td><td>1一 3</td><td></td></tr><tr><td></td><td colspan="4">state-contingent dividend</td><td>price</td></tr><tr><td>Asset 1</td><td>1</td><td>2</td><td>2</td><td>2</td><td>3 2</td></tr><tr><td>Asset 2</td><td>1</td><td>3</td><td>0</td><td>0</td><td>7 6</td></tr><tr><td>Asset 3</td><td>0</td><td>0</td><td>1</td><td>1</td><td>1</td></tr><tr><td>Asset 4</td><td>3</td><td>2</td><td>1</td><td>1</td><td>3 3 2</td></tr></table></body></html>  

The economy is known to be arbitrage-free.  

(a) Show that asset 4 is redundant and verify that the price of asset 4 is identical to the price of the portfolio of the other assets that replicates asset 4.   
(b) Is the market complete?   
(c) Show that the vector $\begin{array}{r}{\psi^{*}=\left(\frac{1}{6},\frac{1}{3},\frac{1}{6},\frac{1}{6}\right)}\end{array}$ is a valid state price vector and that i is in the set of dividends spanned by the basic assets. Characterize the set of all valid state-price vectors..   
(d) Show that the vector $\begin{array}{r}{\boldsymbol{\zeta}^{*}=\left(1,\frac{4}{3},\frac{4}{7},\frac{4}{7}\right)}\end{array}$ is a valid state-price deflator and that it is in the set of dividends spanned by the basic assets. Show that any state-price deflator must be a vector of the form $\left(1,{\textstyle{\frac{4}{3}}},y,1-{\textstyle{\frac{3}{4}}}y\right)$ , where $y\in\left(0,\frac{4}{3}\right)$   
(e) Show that it is possible to construct a risk-free asset from the four basic assets. What is the risk-free interest rate?  

In the following consider an individual maximizing $u(c_{0})+\beta\operatorname{E}[u(c)]$ , where. $c_{0}$ denotes consumption at the beginning of the period and $c$ denotes the state-dependent consumption at the end of the period. Assume $u(c)=c^{1-\gamma}/(1-\gamma)$ .For $\omega\in\{1,2,3,4\}$ , let $c_{\omega}$ denote the end-of-period consumption if state $\omega$ is realized.  

(f) Show that the optimal consumption plan must satisfy  

$$
c_{2}=c_{1}\left(\frac{4}{3}\right)^{-1/\gamma},\qquadc_{4}=c_{0}\left(\frac{1}{\beta}-\frac{3}{4}\left(\frac{c_{3}}{c_{0}}\right)^{-\gamma}\right)^{-1/\gamma}.
$$  

For the remainder of the problem it is assumed that the individual has identical income/endowment in states 3 and 4.  

(g) Explain why $c_{3}$ and $c_{4}$ must be identical, and hence that the optimal consumption plan must have  

$$
c_{3}=c_{4}=c_{0}\left(\frac{4}{7\beta}\right)^{-1/\gamma}.
$$  

(h) Assuming $\gamma=2$ $\beta={\frac{6}{7}}$ , and $c_{0}=1$ , find the optimal state-dependent end-of-period consumption, i.e. $c_{1},c_{2},c_{3},c_{4}$   
(i) What is the present value of the optimal consumption plan?  

(j) Assuming that the individual receives no end-of-period income in any state, find an optimal portfolio for this individual..  

EXERCISE 6.3 Consider a one-period economy with four possible, equally likely, states at the end of the period. The agents in the economy consume at the beginning of the period (time 0) and at the end of the period (time 1). The agents can choose between three different consumption plans as shown in the following table:  

<html><body><table><tr><td rowspan="2"></td><td rowspan="2">consumption at time 0</td><td colspan="4">state-contingent time 1 consumption</td></tr><tr><td>state1</td><td>state 2</td><td>state3</td><td>state4</td></tr><tr><td>Consumption plan 1</td><td>8</td><td>6</td><td>16</td><td>6</td><td>4</td></tr><tr><td>Consumption plan 2</td><td>8</td><td>6</td><td>6</td><td>9</td><td>9</td></tr><tr><td>Consumption plan 3</td><td>8</td><td>4</td><td>16</td><td>25</td><td>4</td></tr></table></body></html>  

Denote the time 0 consumption by. $c_{0}$ , the uncertain consumption at time 1 by $c$ , and the con-. sumption at time 1 in case state. $\omega$ is realized by $c_{\omega}$  

(a) Consider an agent with logarithmic utility,  

$$
U(c_{0},c_{1},c_{2},c_{3},c_{4})=\ln c_{0}+\mathrm{E}[\ln c]=\ln c_{0}+\sum_{\omega=1}^{4}p_{\omega}\ln c_{\omega},
$$  

where $p_{\omega}$ is the probability that state. $\omega$ is realized. Compute the utility for each of the. three possible consumption plans and determine the optimal consumption plan. Find the associated state-price vector. Using this state-price vector, what is the price at the beginning of the period of an asset that gives a payoff of 2 in states 1 and 4 and a payoff of 1 in states 2 and 3?  

(b) Answer the same questions with the alternative time-additive square root utility,  

$$
U(c_{0},c_{1},c_{2},c_{3},c_{4})=\sqrt{c_{0}}+{\mathrm E}[\sqrt{c}]=\sqrt{c_{0}}+\sum_{\omega=1}^{4}p_{\omega}\sqrt{c_{\omega}}.
$$  

(c) Answer the same questions with the alternative habit-style square root utility,  

$$
U(c_{0},c_{1},c_{2},c_{3},c_{4})=\sqrt{c_{0}}+\mathrm{E}\left[\sqrt{c-0.5c_{0}}\right]=\sqrt{c_{0}}+\sum_{\omega=1}^{4}p_{\omega}\sqrt{c_{\omega}-0.5c_{0}}.
$$  

EXERCISE 6.4 Show Equation (6.24).  

EXERCISE 6.5 Using the Lagrangian characterization of the mean-variance frontier, show that for any mean-variance efficient return $R^{\pi}$ different from the minimum-variance portfolio there is a unique mean-variance efficient return $R^{z(\pmb{\pi})}$ with $\mathrm{Cov}[R^{\pi},R^{z(\pmb{\pi})}]=0$ .Show that $\mathrm{E}[R^{z(\pi)}]=$ $(A-B\operatorname{E}[R^{\pi}])/(B-C\operatorname{E}[R^{\pi}])$  

EXERCISE 6.6 Let $R_{\mathrm{min}}$ denote the return on the minimum-variance portfolio. Let $R$ be any Other return, efficient or not. Show that. $\operatorname{Cov}[R,R_{\mathrm{min}}]=\operatorname{Var}[R_{\mathrm{min}}]$  

EXERCISE 6.7Let $R_{1}$ denote the return on a mean-variance efficient portfolio and let $R_{2}$ denote the return on another not necessarily efficient portfolio with $\operatorname{E}[R_{2}]=\operatorname{E}[R_{1}]$ . Show that $\mathrm{Cov}[R_{1},R_{2}]=\mathrm{Var}[R_{1}]$ and conclude that $R_{1}$ and $R_{2}$ are positively correlated.  

EXERCISE 6.8 Think of the mean-variance framework in a one-period economy. Show that if there is a risk-free asset, then any two mean-variance efficient returns (different from the risk-free return) are either perfectly positively correlated or perfectly negatively correlated. Is that also true if there is no risk-free asset?  

EXERCISE 6.9 In a one-period model where the returns of all the risky assets are normally distributed, any greedy and risk-averse investor will place herself on the upward-sloping part of the mean-variance frontier. But where? Consider an agent that maximizes expected utility of endof-period wealth with a negative exponential utility function. $u(W)=-e^{-a W}$ for some const ant $a$ Suppose that $M$ risky assets (with normally distributed returns) and one risk-free asset are traded. What is the optimal portfolio of the agent? Where is the optimal portfolio located on the meanvariance frontier?  

EXERCISE6.10 Look at an individual with habit formation living in a continuous-time complete market economy. The individual wants to maximize his expected utility  

$$
\mathrm{E}\left[\int_{0}^{T}e^{-\delta t}u(c_{t},h_{t})d t\right],
$$  

where the habit level $h_{t}$ is given by.  

$$
h_{t}=h_{0}e^{-\alpha t}+\beta\int_{0}^{t}e^{-\alpha(t-u)}c_{u}d u.
$$  

We can write the budget constraint as  

$$
\mathrm{E}\left[\int_{0}^{T}\zeta_{t}c_{t}d t\right]\leq W_{0},
$$  

where $\zeta=\left(\zeta_{t}\right)$ is the state-price deflator and $W_{0}$ is the initial wealth of the agent (including the present value of any future non-financial income).  

(a) Show that $d h_{t}=(\beta c_{t}-\alpha h_{t})~($ lt. What condition on $\alpha$ and $\beta$ will ensure that the habit level declines, when current consumption equals the habit level?  

(b) Show that the state-price deflator is linked to optimal consumption by the relation  

$$
\zeta_{t}=k e^{-\delta t}\left\{u_{c}(c_{t},h_{t})+\beta\operatorname{E}_{t}\left[\int_{t}^{T}e^{-(\delta+\alpha)(s-t)}u_{h}(c_{s},h_{s})d s\right]\right\}
$$  

for some appropriate constant $k$ . Hint: First consider what effect consumption at time $t$ has on future habit levels..  

(c) How does ( $^*$ ) look when $\begin{array}{r}{u(c,h)=\frac{1}{1-\gamma}(c-h)^{1-\gamma};}\end{array}$  
