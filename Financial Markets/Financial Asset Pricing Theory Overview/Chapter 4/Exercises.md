---
tags:
  - arbitrage
  - asset_pricing
  - continuous_time
  - dividend
  - expected_return
  - one_period_economy
  - portfolio
  - redundant_assets
  - risk_free_asset
  - sharpe_ratio
  - state_price_deflator
  - state_price_vector
aliases:
  - Exercise 4.1
  - Exercise 4.2
  - Exercise 4.3
  - Exercise 4.4
  - Exercise 4.5
  - Exercise 4.6
  - Exercise 4.7
  - Exercise 4.8
key_concepts:
  - Absence of arbitrage
  - Continuous-time framework
  - Dividend payments
  - Expected return calculation
  - Maximal Sharpe ratio
  - One-period economy
  - Portfolio construction
  - Redundant assets
  - Risk-free asset pricing
  - State-price deflator
---

# 4.8 Exercises  

EXERCISE 4.1 Imagine a one-period economy where the state-price deflator. $\zeta$ is lognormally distributed with $\operatorname{E}[\ln\zeta]=\mu_{\zeta}$ and $\mathrm{Var}[\ln\zeta]=\sigma_{\zeta}^{2}$ . What is the maximal Sharpe ratio of a risky. asset? (Look at Equation (4.14).) What determines the sign of an asset's Sharpe ratio?  

EXERCISE 4.2 Consider a one-period, three-state economy with two assets traded. Asset 1 has a price of 0.9 and pays a dividend of 1 no matter what state is realized. Asset 2 has a price of 2 and pays 1, 2, and 4 in state 1, 2, and 3, respectively. The real-world probabilities of the states are 0.2, 0.6, and 0.2, respectively. Assume absence of arbitrage..  

(a) Find the state-price vector. $\psi^{*}$ and the associated state-price deflator. What portfolio gen-. erates a dividend of. $\psi^{*}$   
(b) Find the state-price deflator $\zeta^{*}$ and the associated state-price vector. What portfolio gener-. ates a dividend of. $\zeta^{\ast}$ 2.   
(c) Find a portfolio with dividends 4, 3, and 1 in states 1, 2, and 3, respectively. What is the price of the portfolio?.  

EXERCISE 4.3 Give a proof of Theorem 4.3 both for the one-period framework and the continuous-time framework.  

EXERCISE 4.4 Show Lemma 4.1.  

EXERCISE 4.5 Assume a one-period framework with no redundant assets. Show that $\zeta^{*}$ can be rewritten as in (4.60).  

EXERCISE 4.6 Consider a one-period economy where the assets are correctly priced by a state price deflator. $M$ . A nutty professor believes that the assets are priced according to a model in which $Y$ is a state-price deflator, where $Y$ is a random variable with $E[Y]=E[M]$ . Refer to this. model as the. $Y$ model.  

(a) Show that the $Y$ -model prices a risk-free asset correctly.  

(b) Argue that the expected return on an arbitrary asset $i$ according to the $Y$ -model is given by  

$$
\mathrm{E}_{Y}\left[R_{i}\right]\equiv{\frac{1}{\mathrm{E}[M]}}-{\frac{1}{\mathrm{E}[M]}}\mathrm{Cov}[Y,R_{i}].
$$  

(c) Show that  

$$
\frac{|\operatorname{E}\left[R_{i}\right]-\operatorname{E}_{Y}\left[R_{i}\right]|}{\sigma[R_{i}]}\leq\frac{\sigma[Y-M]}{\operatorname{E}[M]}
$$  

so that the mispricing of the. $Y$ -model (in terms of expected returns) is limited.  

(d) What can you say about the returns for which the left-hand side in the above inequality will be largest?  

(e) Under which condition on $Y$ will the. $Y$ -model price all assets correctly?  

EXERCISE 4.7 Consider a one-period economy where two basic financial assets are traded. without portfolio constraints or transaction costs. There are three equally likely end-of-period. states of the economy and the prices and state-contingent dividends of the two assets are given in the following table:  

<html><body><table><tr><td></td><td colspan="2">state-contingent dividend</td><td>price</td><td></td></tr><tr><td>Asset 1</td><td>state1 1</td><td>state2 1</td><td>state3 0</td><td>0.5</td></tr><tr><td>Asset2</td><td>2</td><td>2</td><td>2</td><td>1.8</td></tr></table></body></html>  

The economy is known to be arbitrage-free.  

(a) Characterize the set of state-contingent dividends that can be attained by combining the two assets.   
(b) Characterize the set of state-price vectors ${\pmb{\psi}}=(\psi_{1},\psi_{2},\psi_{3})$ consistent with the prices and. dividends of the two basic assets.   
(c) Find the state-price vector. $\psi^{*}$ that belongs to the set of attainable dividend vectors.   
(d) Characterize the set of state-price deflators ${\boldsymbol{\zeta}}=(\zeta_{1},\zeta_{2},\zeta_{3})$ consistent with the prices and dividends of the two basic assets.   
(e) What is the risk-free (gross) return $R^{f}$ over the period?   
(f) What prices of the state-contingent dividend vector (1,1,5) are consistent with absence of arbitrage?   
(g) What prices of the state-contingent dividend vector (1,2,5) are consistent with absence of arbitrage?   
(h) Show that the state-price deflator $\zeta^{*}$ that belongs to the set of attainable dividend vectors is given by the vector (0.75, 0.75, 1.2), i.e. it has the value 0.75 in states 1 and 2 and the value 1.2 in state 3.  

EXERCISE 4.8 Consider a two-period economy where the resolution of uncertainty can be represented by the tree in Figure 2.2 in Chapter 2. Assume that three assets are traded. Their dividend processes are illustrated in Figure 4.1, where a triple $(D_{1},D_{2},D_{3})$ near a node means that asset $i={1,2,3}$ pays a dividend of $D_{i}$ if/when that node is reached. For example, if the economy at time 2 is in the scenario. $F_{22}$ , assets 1 and 2 will pay a dividend of 1 and asset 3 will pay a dividend of 2. In Figure 4.1, the numbers near the lines connecting nodes denote values of the next-period state-price deflator, i.e. $\zeta_{1}/\zeta_{0}=\zeta_{1}$ over the first period and. $\zeta_{2}/\zeta_{1}$ over the second period. For. example, the value of $\zeta_{2}/\zeta_{1}$ given that the economy is in scenario $F_{11}$ at time $^{1}$ is $^{1}$ if the economy moves to scenario $F_{21}$ and $2/3$ if the economy moves to scenario $F_{22}$ . This characterizes completely the state-price deflator to be used in the computations below.  

![](9ecf41d112b9045cdd64941fa06bf9669f56618f613c5d14cc382d51b161b720.jpg)  
Figure 4.1: Dividends and state prices.  

(a) Find the price processes of the three assets. (You should find that the time 0 price of asset 1 is 1.802.)   
(b) Find the short-term (one-period) interest rate process. What are the one-period and the two-period zero-coupon yields at time 0?   
(c) Is the market complete?  

EXERCISE 4.9 Consider a discrete-time economy where a state-price deflator $\zeta=\left(\zeta_{t}\right)$ satisfies  

$$
\ln\left(\frac{\zeta_{t+1}}{\zeta_{t}}\right)\sim N(\mu_{\zeta},\sigma_{\zeta}^{2})
$$  

for each $t=0,1,\ldots,T-1$ . An asset pays a dividend process $D=\left(D_{t}\right)$ satisfying  

$$
\frac{D_{t+1}}{D_{t}}=a\left(\frac{\zeta_{t+1}}{\zeta_{t}}\right)^{b}+\varepsilon_{t+1},\quad t=0,1,\ldots,T-1,
$$  

where $a$ and $b$ are constants, and $\varepsilon_{1},\ldots,\varepsilon_{T}$ are independent with $\mathrm{E}_{t}[\varepsilon_{t+1}]=0$ and $\mathrm{E}_{t}[\varepsilon_{t+1}\zeta_{t+1}]=0$ for all $t$ . What is the price of the asset at any time $t$ (in terms of $a,b,\mu_{\zeta},\sigma_{\zeta}^{2})$  

EXERCISE 4.10 Consider a continuous-time economy in which the state-price deflator follows a geometric Brownian motion:.  

$$
\begin{array}{r}{d\zeta_{t}=-\zeta_{t}\left[r^{f}d t+\lambda^{\top}d z_{t}\right],}\end{array}
$$  

where $r^{f}$ and $\lambda$ are constant.  

(a) What is the price $B_{t}^{s}$ of a zero-coupon bond maturing at time $s$ with a face value of 1? Define the continuously compounded yield $y_{t}^{s}$ for maturity $s$ via the equation $B_{t}^{s}=e^{-y_{t}^{s}(s-t)}$ (b) Compute $\boldsymbol y_{t}^{s}$ . What can you say about the yield curve $s\mapsto y_{t}^{s}$  

EXERCISE 4.11 Show that. $\zeta_{t}^{*}=V_{0}^{*}/V_{t}^{*}$ , where $V^{*}$ and $\zeta^{*}$ are given by (4.51) and (4.50).  

EXERCISE 4.12 In a one-period framework show that if $x$ is a pricing factor and. $k_{1},k_{2}$ are constants with $k_{2}\neq0$ , then $y=k_{1}+k_{2}x$ is also a pricing factor..  

EXERCISE 4.13 Consider a two-period arbitrage-free economy where the resolution of uncertainty is illustrated in the following binomial tree.  

![](21962c625e82cc0c10adca08392d14d9efd2cc8649ef86fb744d2d27c92c18dc.jpg)  

Each branch in the tree has a conditional probability of $\frac{\mathrm{~1~}}{2}$ . Assets in the economy are priced by a. state-price deflator $\zeta=\left(\zeta_{t}\right)_{t\in\{0,1,2\}}$ . The numbers along the branches show the possible values of. the state-price deflator over that period, i.e. $\zeta_{1}/\zeta_{0}$ over the first period and. $\zeta_{2}/\zeta_{1}$ over the second period. The pair of numbers written at each node shows the dividend payments of asset 1 and asset 2, respectively, if that node is reached. For example, if the up-branch is realized in both periods, then asset 1 will pay a dividend of 10 and asset 2 a dividend of 6 at time 2..  

(a) For each of the two assets compute the following quantities in both the up-node and the. down-node at time 1: (i) the conditional expectation of the dividend received at time 2, (ii) the ex-dividend price, and (ii) the expected net rate of return over the second period.   
(b) For each of the two assets compute the following quantities at time 0: (i) the expectation of. the dividend received at time 1, (ii) the price, and (ii) the expected net rate of return over. the first period.   
(c) Compare the prices of the two assets. Compare the expected returns of the two assets.. Explain the differences.   
(d) Is it always possible in this economy to construct a portfolio with a risk-free dividend over. the next period? If so, find the one-period risk-free return at time O and in each of the two. nodes at time 1.   
(e) Is the market complete? Explain!.  
