---
tags:
  - consumption_process
  - discrete_time_framework
  - habit_formation
  - state_price_deflator
  - time_additive_utility
aliases:
  - Discrete Time Framework
  - Habit Formation Utility
  - Time Additive Utility
key_concepts:
  - Consumption process choice
  - Habit level at time
  - Non-additive preference specification
  - State-price deflator definition
  - Time-additive expected utility
---

# 6.3 The discrete-time framework  

In the discrete-time framework each individual has to choose a consumption process $c=(c_{t})_{t\in\mathcal{T}}$ where $\mathcal{T}=\{0,1,\ldots,T\}$ and $c_{t}$ denotes the random, i.e. state-dependent, consumption at time $t$ The individual also has to choose a trading strategy. $\pmb{\theta}=(\pmb{\theta}_{t})_{t=0,1,...,T-1}$ with $\pmb{\theta}_{t}$ representing the portfolio held from time $t$ until time $t+1$ . Again, $\pmb{\theta}_{t}$ may depend on the information available to the individual at time $t$ so $\pmb{\theta}$ is an adapted stochastic process. The individual has an endowment or income process $\boldsymbol{e}=(\boldsymbol{e}_{t})_{t\in\mathcal{T}}$ , where $e_{0}$ is the initial endowment (wealth) and $e_{t}$ is the possibly state-dependent income received at time $t$  

# 6.3.1 Time-additive expected utility  

Let us first focus on individuals with time-additive expected utility. Standing at time 0 the problem of an individual investor can therefore be written as  

$$
\operatorname*{max}_{\theta}u(c_{0})+\sum_{t=1}^{T}e^{-\delta t}\operatorname{E}[u(c_{t})]
$$  

$$
\begin{array}{l}{{c_{t}\leq e_{t}+D_{t}^{\theta},\quad t=1,\dots,T,}}\ {{{}}}\ {{c_{0},c_{1},...,c_{T}\geq0.}}\end{array}
$$  

Applying (3.8), we can also write the constraint on time $t$ consumption as  

$$
c_{t}\leq e_{t}+\pmb\theta_{t-1}\cdot(\pmb P_{t}+\pmb D_{t})-\pmb\theta_{t}\cdot\pmb P_{t}.
$$  

As in the one-period case we will assume that the non-negativity constraint on consumption is automatically satisfied and that the budget constraints hold as equalities. Therefore the problem can be reformulated as  

$$
\operatorname*{max}_{\theta}u\left(e_{0}-\theta_{0}\cdot P_{0}\right)+\sum_{t=1}^{T}e^{-\delta t}\operatorname{E}\left[u\left(e_{t}+\theta_{t-1}\cdot\left(P_{t}+D_{t}\right)-\theta_{t}\cdot P_{t}\right)\right].
$$  

The only terms involving the initially chosen portfolio $\pmb{\theta}_{0}=(\theta_{10},\theta_{20},\dots,\theta_{I0})^{\top}$ will be  

$$
u\left(e_{0}-\pmb{\theta}_{0}\cdot\pmb{P}_{0}\right)+e^{-\delta}\operatorname{E}\left[u\left(e_{1}+\pmb{\theta}_{0}\cdot\left(\pmb{P}_{1}+\pmb{D}_{1}\right)-\pmb{\theta}_{1}\cdot\pmb{P}_{1}\right)\right].
$$  

The first-order condition with respect to $\theta_{i0}$ implies that  

$$
P_{i0}=\mathrm{E}\left[e^{-\delta}\frac{u^{\prime}(c_{1})}{u^{\prime}(c_{0})}(P_{i1}+D_{i1})\right].
$$  

This can also be verified by a variational argument as in the one-period analysis. More generally, the first-order condition with respect to. $\theta_{i t}$ implies that  

$$
P_{i t}=\mathrm{E}_{t}\left[\frac{e^{-\delta}u^{\prime}(c_{t+1})}{u^{\prime}(c_{t})}(P_{i,t+1}+D_{i,t+1})\right].
$$  

Note that $c_{t}$ and $c_{t+1}$ in these expressions are the optimal consumption rates of the individual. Not surprisingly, this condition is equivalent to the conclusion in the one-period framework. In particular, we can define a state-price deflator $\zeta=(\zeta_{t})_{t\in\mathcal{T}}$ from the individual's optimal consumption process by $\zeta_{0}=1$ and  

$$
\frac{\zeta_{t+1}}{\zeta_{t}}=\frac{e^{-\delta}u^{\prime}(c_{t+1})}{u^{\prime}(c_{t})},
$$  

which means that  

$$
\begin{array}{l}{{\zeta_{t}=\displaystyle\frac{\zeta_{t}}{\zeta_{t-1}}\displaystyle\frac{\zeta_{t-1}}{\zeta_{t-2}}\ldots\ldots\displaystyle\frac{\zeta_{1}}{\zeta_{0}}}}\ {{\mathrm{}=e^{-\delta}\displaystyle\frac{u^{\prime}(c_{t})}{u^{\prime}(c_{t-1})}e^{-\delta}\displaystyle\frac{u^{\prime}(c_{t-1})}{u^{\prime}(c_{t-2})}\ldots e^{-\delta}\displaystyle\frac{u^{\prime}(c_{1})}{u^{\prime}(c_{0})}}}\ {{\mathrm{}=e^{-\delta t}\displaystyle\frac{u^{\prime}(c_{t})}{u^{\prime}(c_{0})}.}}\end{array}
$$  

This is the individual's marginal rate of substitution between time $0$ consumption and time $t$ consumption.  

# 6.3.2 Habit formation utility  

Next let us consider a non-additive specification of preferences and for concreteness we study a specification with habit formation. The objective of the individual is  

$$
\operatorname*{max}_{\theta=(\theta_{t})_{t=0,1,..,T-1}}\operatorname{E}\left[\sum_{{t=0}}^{T}e^{-\delta t}u(c_{t},h_{t})\right],
$$  

where $h_{t}$ is the habit level at time. $t$ . First assume that the habit level at time $t$ is some fraction of the consumption level at time. $t-1$  

$$
h_{t}=\beta c_{t-1},
$$  

and let $h_{0}=0$ . Apply the variational argument given earlier. Let. $c_{0},c_{1},\ldots,c_{T}$ denote the optimal consumption process and let $h_{0},h_{1},\ldots,h_{T}$ denote the resulting process for the habit level. What happens if the individual purchases. $\varepsilon>0$ units extra of asset $i$ at time $t$ and sells those $\varepsilon$ units again at time $t+1$ ? Consumption at time $t$ and $t+1$ will change to $c_{t}-\varepsilon P_{i t}$ and $c_{t+1}+\varepsilon(D_{i,t+1}+P_{i,t+1})$ respectively. The perturbation will also affect the habit level. With the assumed habit formation, only the habit level at time. $t+1$ and time $t+2$ will be changed. The new habit levels will be. ${h_{t+1}}-\beta\varepsilon{P_{i t}}$ at time $t+1$ and $h_{t+2}+\beta\varepsilon(D_{i,t+1}+P_{i,t+1})$ . Therefore the change in total utility. from time $t$ and onwards will be  

$$
\begin{array}{r l}&{u\left(c_{t}-\varepsilon P_{i t},h_{t}\right)-u(c_{t},h_{t})+e^{-\delta}\mathrm{E}_{t}\left[u\left(c_{t+1}+\varepsilon(D_{i,t+1}+P_{i,t+1}),h_{t+1}-\beta\varepsilon P_{i t}\right)-u\left(c_{t+1},h_{t+1}\right)\right]}\ &{+e^{-2\delta}\mathrm{E}_{t}\left[u\left(c_{t+2},h_{t+2}+\beta\varepsilon(D_{i,t+1}+P_{i,t+1})\right)-u(c_{t+2},h_{t+2})\right]\leq0}\end{array}
$$  

Dividing by $\varepsilon$ and letting $\varepsilon\rightarrow0$ , we obtain  

$$
\begin{array}{r l}&{-P_{i t}u_{c}(c_{t},h_{t})+e^{-\delta}\operatorname{E}_{t}\left[u_{c}(c_{t+1},h_{t+1})\left(D_{i,t+1}+P_{i,t+1}\right)-\beta P_{i t}u_{h}(c_{t+1},h_{t+1})\right]}\ &{+e^{-2\delta}\operatorname{E}_{t}\left[u_{h}(c_{t+2},h_{t+2})\beta\left(D_{i,t+1}+P_{i,t+1}\right)\right]\leq0.}\end{array}
$$  

Here a subscript on $u$ indicate the partial derivative of. $u$ with respect to that variable. Again the. opposite inequality can be reached by a similar argument. Replacing the inequality sign with an equality sign and rearranging, we arrive at.  

$$
\begin{array}{r l}&{P_{i t}\left(u_{c}(c_{t},h_{t})+\beta e^{-\delta}\operatorname{E}_{t}\left[u_{h}(c_{t+1},h_{t+1})\right]\right)}\ &{\qquad=e^{-\delta}\operatorname{E}_{t}\left[\left(u_{c}(c_{t+1},h_{t+1})+\beta e^{-\delta}u_{h}(c_{t+2},h_{t+2})\right)(D_{i,t+1}+P_{i,t+1})\right]}\ &{\qquad=e^{-\delta}\operatorname{E}_{t}\left[\left(u_{c}(c_{t+1},h_{t+1})+\beta e^{-\delta}\operatorname{E}_{t+1}[u_{h}(c_{t+2},h_{t+2})]\right)(D_{i,t+1}+P_{i,t+1})\right],}\end{array}
$$  

where the last equality is due to the Law of Iterated Expectations. Consequently,  

$$
P_{i t}=\mathrm{E}_{t}\left[e^{-\delta}\frac{u_{c}(c_{t+1},h_{t+1})+\beta e^{-\delta}\mathrm{E}_{t+1}[u_{h}(c_{t+2},h_{t+2})]}{u_{c}(c_{t},h_{t})+\beta e^{-\delta}\mathrm{E}_{t}\left[u_{h}(c_{t+1},h_{t+1})\right]}\left(D_{i,t+1}+P_{i,t+1}\right)\right],
$$  

and a state-price deflator can be defined by  

$$
\zeta_{t}=e^{-\delta t}\frac{u_{c}(c_{t},h_{t})+\beta e^{-\delta}\operatorname{E}_{t}[u_{h}(c_{t+1},h_{t+1})]}{u_{c}(c_{0},h_{0})+\beta e^{-\delta}\operatorname{E}\left[u_{h}(c_{1},h_{1})\right]}.
$$  

Note that if $\beta=0$ we are back to the case of time-additive utility.  

It is probably more realistic that the habit level at time $t$ depends on all the previous consumption rates but such that the consumption in recent periods are more important for the habit level than consumption in the far past. This can be captured by a specification like  

$$
h_{t}=\sum_{s=0}^{t-1}\beta^{t-s}c_{s},
$$  

where $\beta$ is a constant between 0 and 1. A change in the consumption at time. $t$ will now affect the habit levels at all future dates. $t+1,t+2,\ldots,T$ . Following the same line of argumentation as. above, it can be shown that this problem will generate the state-price deflator  

$$
\zeta_{t}=e^{-\delta t}\frac{u_{c}(c_{t},h_{t})+\sum_{s=1}^{T-t}\beta^{s}e^{-\delta s}\operatorname{E}_{t}[u_{h}(c_{t+s},h_{t+s})]}{u_{c}(c_{0},h_{0})+\sum_{s=1}^{T}\beta^{s}e^{-\delta s}\operatorname{E}\left[u_{h}(c_{s},h_{s})\right]},
$$  

which is difficult to work with.  
