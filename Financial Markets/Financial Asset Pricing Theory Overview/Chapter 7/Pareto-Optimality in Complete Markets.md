---
tags:
  - complete_markets
  - consumption_allocation
  - first_welfare_theorem
  - pareto_optimality
  - risk_sharing
aliases:
  - First Welfare Theorem
  - Pareto optimality
key_concepts:
  - complete market equilibrium
  - consumption allocation
  - efficient risk sharing
  - marginal rate of substitution
  - state price deflator
---

# 7.3 Pareto-optimality in complete markets  

From the analysis in the previous chapter we know that any individual's marginal rate of substitution is a valid state-price deflator. With time-additive expected utility the state-price deflator. induced by individual $\it l$ is the random variable  

$$
\zeta^{l}=e^{-\delta_{l}}\frac{u_{l}^{\prime}(c^{l})}{u_{l}^{\prime}(c_{0}^{l})},
$$  

where $c_{0}^{l}$ is the optimal time $0$ consumption and $c^{l}$ is the optimal state-dependent time. $^{1}$ consumption. In general, these state prices may not be identical for different investors so that multiple state-price vectors and deflators can be constructed in this way. However, if the market is complete, we know that the state-price deflator is unique so we must have $\zeta^{k}=\zeta^{l}$ for any two individuals. $k$ and $\it l$ . This means that $\zeta_{\omega}^{k}=\zeta_{\omega}^{l}$ for all possible states. $\omega\in\Omega=\{1,2,\ldots,S\}$ . Assuming complete markets and time-additive utility we can conclude that  

$$
e^{-\delta_{k}}\frac{u_{k}^{\prime}\left(c_{\omega}^{k}\right)}{u_{k}^{\prime}\left(c_{0}^{k}\right)}=e^{-\delta_{l}}\frac{u_{l}^{\prime}\left(c_{\omega}^{l}\right)}{u_{l}^{\prime}\left(c_{0}^{l}\right)}
$$  

for any $\omega$ , i.e. the marginal rate of substitution is the same for all individuals. From the discussion above, this will imply efficient risk-sharing and that the consumption allocation is Pareto-optimal. This result is often called the First Welfare Theorem:  

Theorem 7.4 If the financial market is complete, then every equilibrium consumption allocation is Pareto-optimal.  

Here is a formal proof:  

Proof: Recall from (6.19) that in a complete market the utility maximization problem of individual $\textit{l}$ can be written as  

$$
\begin{array}{r l}&{\underset{c_{0},c}{\operatorname*{max}}\mathcal{U}_{l}(c_{0},\boldsymbol{\pmb{c}})}\ &{\mathrm{~s.t.~}c_{0}+\boldsymbol{\psi}\cdot\boldsymbol{c}\leq e_{0}^{l}+\boldsymbol{\psi}\cdot\boldsymbol{e}^{l}}\ &{\mathrm{~}c_{0},\boldsymbol{c}\geq0,}\end{array}
$$  

where $\psi$ is the unique state-price vector. Let. $\{(c_{0}^{l},{\pmb c}^{l}),l=1,...,L\}$ be an equilibrium consumption allocation, but suppose we can find another consumption allocation. $\{(\hat{c}_{0}^{l},\hat{\pmb{c}}^{l}),l=1,\dots,L\}$ which gives all individuals at least the same utility and some individuals strictly higher utility than $\{(c_{0}^{l},{\pmb c}^{l}),l=1,...,L\}$ . Since we assume strictly increasing utility and. $(c_{0}^{l},c^{l})$ maximizes individual $l$ 's utility subject to the constraint $c_{0}^{l}+\psi\cdot{\bf{c}}^{l}\leq e_{0}^{l}+\psi\cdot e^{l}$ , the inequality.  

$$
\hat{c}_{0}^{l}+\boldsymbol{\psi}\cdot\hat{\boldsymbol{c}}^{l}\geq e_{0}^{l}+\boldsymbol{\psi}\cdot\boldsymbol{e}^{l}
$$  

must hold for all individuals with strict inequality for at least one individual. Summing up over all individuals we get  

$$
\sum_{l=1}^{L}\left(\hat{c}_{0}^{l}+\psi\cdot\hat{c}^{l}\right)>\sum_{l=1}^{L}\left(e_{0}^{l}+\psi\cdot e^{l}\right)=\bar{e}_{0}+\psi\cdot\bar{e}.
$$  

Hence, the consumption allocation $\{(\hat{c}_{0}^{l},\hat{\pmb{c}}^{l}),l=1,\dots,L\}$ is not feasible..  

A complete market equilibrium provides efficient risk-sharing. From (7.11) it follows that, for any two states $\omega$ and $\omega^{\prime}$ , we have  

$$
\frac{u_{k}^{\prime}\left(c_{\omega}^{k}\right)}{u_{k}^{\prime}\left(c_{\omega^{\prime}}^{k}\right)}=\frac{u_{l}^{\prime}\left(c_{\omega}^{l}\right)}{u_{l}^{\prime}\left(c_{\omega^{\prime}}^{l}\right)}.
$$  

Suppose that (7.12) did not hold. Suppose we could find two individuals $k$ and $\it l$ and two states $\omega$ and $\omega^{\prime}$ such that  

$$
\frac{u_{k}^{\prime}(c_{\omega}^{k})}{u_{k}^{\prime}(c_{\omega^{\prime}}^{k})}>\frac{u_{l}^{\prime}(c_{\omega}^{l})}{u_{l}^{\prime}(c_{\omega^{\prime}}^{l})}.
$$  

Then the two agents could engage in a trade that makes both better off. What trade? Since the. market is complete, Arrow-Debreu assets for all states are traded, in particular for states $\omega$ and $\omega^{\prime}$ Consider the following trade: Individual $k$ buys $\varepsilon_{\omega}$ Arrow-Debreu assets for state $\omega$ from individual $\textit{l}$ at a unit price of $\varphi_{\omega}$ . And individual $\textit{l}$ buys $\varepsilon_{\omega^{\prime}}$ Arrow-Debreu assets for state $\omega^{\prime}$ from individual $k$ at a unit price of $\varphi_{\omega^{\prime}}$ . The deal is arranged so that the net price is zero, i.e..  

$$
\varepsilon_{\omega}\varphi_{\omega}-\varepsilon_{\omega^{\prime}}\varphi_{\omega^{\prime}}=0\quad\Leftrightarrow\varepsilon_{\omega^{\prime}}=\varepsilon_{\omega}\frac{\varphi_{\omega^{\prime}}}{\varphi_{\omega}}.
$$  

The deal will change the consumption of the two individuals in states $\omega$ and $\omega^{\prime}$ but not in other states, nor at time $0$ . The total change in the expected utility of individual $k$ will be  

$$
p_{\omega}\left(u_{k}(c_{\omega}^{k}+\varepsilon_{\omega})-u_{k}(c_{\omega}^{k})\right)+p_{\omega^{\prime}}\left(u_{k}(c_{\omega^{\prime}}^{k}-\varepsilon_{\omega}\frac{\varphi_{\omega^{\prime}}}{\varphi_{\omega}})-u_{k}(c_{\omega^{\prime}}^{k})\right).
$$  

Dividing by $\varepsilon_{\omega}$ and letting $\varepsilon_{\omega}\rightarrow0$ , the additional expected utility approaches  

$$
p_{\omega}u_{k}^{\prime}(c_{\omega}^{k})-\frac{\varphi_{\omega^{\prime}}}{\varphi_{\omega}}u_{k}^{\prime}(c_{\omega^{\prime}}^{k}),
$$  

which is strictly positive whenever  

$$
\frac{u_{k}^{\prime}(c_{\omega}^{k})}{u_{k}^{\prime}(c_{\omega^{\prime}}^{k})}>\frac{p_{\omega^{\prime}}\varphi_{\omega^{\prime}}}{p_{\omega}\varphi_{\omega}}.
$$  

On the other hand, the total change in the expected utility of individual $\textit{l}$ will be  

$$
p_{\omega}\left(u_{l}(c_{\omega}^{l}-\varepsilon_{\omega})-u_{l}(c_{\omega}^{l})\right)+p_{\omega^{\prime}}\left(u_{l}(c_{\omega^{\prime}}^{l}+\varepsilon_{\omega}\frac{\varphi_{\omega^{\prime}}}{\varphi_{\omega}})-u_{l}(c_{\omega^{\prime}}^{l})\right).
$$  

Dividing by $\varepsilon_{\omega}$ and letting $\varepsilon_{\omega}\rightarrow0$ , we get  

$$
-p_{\omega}u_{l}^{\prime}(c_{\omega}^{l})+p_{\omega^{\prime}}\frac{\varphi_{\omega^{\prime}}}{\varphi_{\omega}}u_{l}^{\prime}(c_{\omega^{\prime}}^{l}),
$$  

which is strictly positive whenever  

$$
\frac{u_{l}^{\prime}(c_{\omega}^{l})}{u_{l}^{\prime}(c_{\omega^{\prime}}^{l})}<\frac{p_{\omega^{\prime}}\varphi_{\omega^{\prime}}}{p_{\omega}\varphi_{\omega}}.
$$  

If the inequality (7.13) holds, the two individuals can surely find prices $\varphi_{\omega}$ and $\varphi_{\omega^{\prime}}$ so that both (7.14) and (7.15) are satisfied, i.e. both increase their expected utility.  

If the market is incomplete, the individuals might not be able to implement this trade. In other words, we cannot be sure that (7.12) holds for states for which Arrow-Debreu assets are not traded, i.e. "uninsurable" states.  

Combining theorems stated above, we have the following conclusion:  

Theorem 7.5 If the financial market is complete, the economy has a representative individual.  

If we want to study asset pricing in a complete market, we might as well assume that the economy has a single individual. But what is the appropriate weighting vector $\pmb{\eta}$ for the complete market? We must ensure that the first-order conditions of the central planner are satisfied when we plug in the optimal consumption plans of the individuals. Recall that in a complete market the utility maximization problem of individual $\textit{l}$ can be formulated as in (6.19). The Lagrangian for this problem is  

$$
\mathcal{L}_{l}=\mathcal{U}_{l}(c_{0}^{l},\pmb{c}^{l})+\kappa_{l}\left(\sum_{\omega=1}^{S}\psi_{\omega}\left(e_{\omega}^{l}-c_{\omega}^{l}\right)+e_{0}^{l}-c_{0}^{l}\right).
$$  

The first-order conditions, again necessary and sufficient, are  

$$
\begin{array}{r l}{\displaystyle\frac{\partial\mathcal{L}_{l}}{\partial c_{0}^{l}}=0\quad\Leftrightarrow\quad\frac{\partial\mathcal{U}_{l}}{\partial c_{0}^{l}}=\kappa_{l},}&{}\ {\displaystyle\frac{\partial\mathcal{L}_{l}}{\partial c_{\omega}^{l}}=0\quad\Leftrightarrow\quad\frac{\partial\mathcal{U}_{l}}{\partial c_{\omega}^{l}}=\kappa_{l}\psi_{\omega},\quad\omega=1,\hdots,S,}&{}\ {\displaystyle\frac{\partial\mathcal{L}_{l}}{\partial\kappa_{l}}=0\quad\Leftrightarrow\quad c_{0}^{l}+\sum_{\omega=1}^{S}\psi_{\omega}c_{\omega}^{l}=e_{0}^{l}+\sum_{\omega=1}^{S}\psi_{\omega}e_{\omega}^{l}.}\end{array}
$$  

If we set $\varphi_{0}=1$ and $\eta_{l}=1/\kappa_{l}$ for each $l=1,\ldots,L$ , the Equations (7.1)-(7.4) will indeed be satisfied.  

Note that the weight $\eta_{l}$ associated with individual $\textit{l}$ is the inverse of his "shadow price"' of his. budget constraint and $\eta_{l}$ will therefore depend on the initial endowment of individual. $\textit{l}$ .Redistributing the aggregate initial endowment across individuals will thus change the relative values of the weights $\eta_{l}$ and, hence, the utility function of the representative individual and equilibrium. asset prices.  

Let us briefly consider the special case where all individuals have time-additive expected utilities. Then the representative individual will also have time-additive expected utility, i.e.  

$$
\mathcal{U}_{\eta}(c_{0},c)=u_{\eta,0}(c_{0})+\mathrm{E}\left[u_{\eta,1}(c)\right]=u_{\eta,0}(c_{0})+\sum_{\omega=1}^{S}p_{\omega}u_{\eta,1}(c_{\omega}),
$$  

where  

$$
\begin{array}{l}{{\displaystyle u_{\eta,0}(c_{0})=\operatorname*{sup}\left\{\sum_{l=1}^{L}\eta_{l}u_{l}(c_{0}^{l})\left|c_{0}^{1},\ldots,c_{0}^{L}>0\mathrm{with}c_{0}^{1}+\cdot\cdot\cdot+c_{0}^{L}\leq c_{0}\right.\right\},}}\ {{\displaystyle u_{\eta,1}(c)=\operatorname*{sup}\left\{\sum_{l=1}^{L}e^{-\delta_{l}}\eta_{l}u_{l}(c^{l})\left|c^{1},\ldots,c^{L}>0\mathrm{with}c^{1}+\cdot\cdot\cdot+c^{L}\leq c\right.\right\}.}}\end{array}
$$  

Often a functional form for $u_{\eta,0}$ and $u_{\eta,1}$ is assumed directly with the property that $u_{\eta,1}(c)=$ $e^{-\delta}u_{\pmb{\eta},0}(c)~=~e^{-\delta}u(c)$ , where $\delta$ can be interpreted as the average time preference rate in the economy. Then the unique state-price deflator follows by evaluating the derivative of $u_{\eta}$ at the aggregate endowment,  

$$
\zeta_{\omega}=\frac{u_{\eta,1}^{\prime}(\bar{e}_{\omega})}{u_{\eta,0}^{\prime}(\bar{e}_{0})}=e^{-\delta}\frac{u^{\prime}(\bar{e}_{\omega})}{u^{\prime}(\bar{e}_{0})}.
$$  

This will be very useful in order to link asset prices and interest rates to aggregate consumption.  
