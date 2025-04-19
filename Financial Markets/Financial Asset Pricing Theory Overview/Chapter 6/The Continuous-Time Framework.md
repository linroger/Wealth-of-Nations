---
tags:
  - asset_pricing
  - consumption
  - continuous_time
  - expected_utility
  - market_completeness
  - state_price
aliases:
  - Continuous Time Framework
  - Continuous-time Model
key_concepts:
  - Continuous-time setting
  - Market completeness
  - Optimal consumption process
  - State-price deflator
  - Time-additive utility
---

# 6.4 The continuous-time framework  

In a continuous-time setting an individual consumes according to a non-negative continuous-time process $c=\left(c_{t}\right)$ . Suppose that her preferences are described by time-additive expected utility so that the objective is to maximize $\begin{array}{r}{\operatorname{E}[\int_{0}^{T}e^{-\delta t}u(c_{t})d t]}\end{array}$  

We will again go through a variational argument giving a link between the optimal consumption process and asset prices. For simplicity assume that assets pay no intermediate dividends. Suppose $c=\left(c_{t}\right)$ is the optimal consumption process for some agent and consider the following deviation from this strategy: at time 0 increase the investment in asset $i$ by $\varepsilon$ units. The extra costs of $\varepsilon P_{i0}$ implies a reduced consumption now. Let us suppose that the individual finances this extra investment by cutting down the consumption rate in the time interval $[0,\Delta t]$ for some small positive $\Delta t$ by $\varepsilon P_{i0}/\Delta t$ . The extra $\varepsilon$ units of asset $i$ is resold at time $t<T$ , yielding a revenue of $\varepsilon P_{i t}$ . This finances an increase in the consumption rate over $[t,t+\Delta t]$ by $\varepsilon P_{i t}/\Delta t$ . The consumption rates outside the intervals $[0,\Delta t]$ and $[t,t+\Delta t]$ will be unaffected. Given the optimality of $c=\left(c_{t}\right)$ , we must have that  

$$
\operatorname{E}\left[\int_{0}^{\Delta t}e^{-\delta s}\left(u\left(c_{s}-{\frac{\varepsilon P_{i0}}{\Delta t}}\right)-u(c_{s})\right)d s+\int_{t}^{t+\Delta t}e^{-\delta s}\left(u\left(c_{s}+{\frac{\varepsilon P_{i t}}{\Delta t}}\right)-u(c_{s})\right)d s\right]\leq0.
$$  

Dividing by $\varepsilon$ and letting $\varepsilon\rightarrow0$ , we obtain  

$$
\operatorname{E}\left[-\frac{P_{i0}}{\Delta t}\int_{0}^{\Delta t}e^{-\delta s}u^{\prime}(c_{s})d s+\frac{P_{i t}}{\Delta t}\int_{t}^{t+\Delta t}e^{-\delta s}u^{\prime}(c_{s})d s\right]\leq0.
$$  

Letting $\Delta t\to0$ , we arrive at  

$$
\mathrm{E}\left[-P_{i0}u^{\prime}(c_{0})+P_{i t}e^{-\delta t}u^{\prime}(c_{t})\right]\leq0,
$$  

or, equivalently,  

$$
P_{i0}u^{\prime}(c_{0})\geq\mathrm{E}\left[e^{-\delta t}P_{i t}u^{\prime}(c_{t})\right].
$$  

The reverse inequality can be shown similarly so that we have that $P_{i0}u^{\prime}(c_{0})=\mathrm{E}[e^{-\partial t}P_{t}u^{\prime}(c_{t})]$ or more generally  

$$
P_{i t}=\mathrm{E}_{t}\left[e^{-\delta(t^{\prime}-t)}\frac{u^{\prime}(c_{t^{\prime}})}{u^{\prime}(c_{t})}P_{i t^{\prime}}\right],\quad t\leq t^{\prime}\leq T.
$$  

With intermediate dividends this relation is slightly more complicated:  

$$
P_{i t}=\mathrm{E}_{t}\left[\int_{t}^{t^{\prime}}\delta_{i s}P_{i s}e^{-\delta(s-t)}\frac{u^{\prime}(c_{s})}{u^{\prime}(c_{t})}d s+e^{-\delta(t^{\prime}-t)}\frac{u^{\prime}(c_{t^{\prime}})}{u^{\prime}(c_{t})}P_{i t^{\prime}}\right].
$$  

We see that  

$$
\zeta_{t}=e^{-\delta t}\frac{u^{\prime}(c_{t})}{u^{\prime}(c_{0})}
$$  

defines a state-price deflator, exactly as in the discrete-time case.  

If the market is complete, we can easily reach (6.44) solving step one of the two-step procedure suggested in Section 6.2.4. The problem is  

$$
\operatorname*{max}_{c=(c_{t})}\operatorname{E}\left[\int_{0}^{T}e^{-\delta t}u(c_{t})d t\right]\qquad\mathrm{s.t.}\mathrm{E}\left[\int_{0}^{T}\zeta_{t}c_{t}d t\right]\leq e_{0}+\mathrm{E}\left[\int_{0}^{T}\zeta_{t}e_{t}d t\right],
$$  

where $\zeta=\left(\zeta_{t}\right)$ is the unique state-price deflator. The left-hand side of the constraint is the present value of the consumption process, the right-hand side is the sum of the initial wealth $e_{0}$ and the present value of the income process. The Lagrangian for this problem is  

$$
\begin{array}{r l}&{\mathcal{L}=\mathrm{E}\left[\displaystyle\int_{0}^{T}e^{-\delta t}u(c_{t})d t\right]+\alpha\left(e_{0}+\mathrm{E}\left[\displaystyle\int_{0}^{T}\zeta_{t}e_{t}d t\right]-\mathrm{E}\left[\displaystyle\int_{0}^{T}\zeta_{t}c_{t}\right]\right)}\ &{\quad=\alpha\left(e_{0}+\mathrm{E}\left[\displaystyle\int_{0}^{T}\zeta_{t}e_{t}d t\right]\right)+\mathrm{E}\left[\displaystyle\int_{0}^{T}\left(e^{-\delta t}u(c_{t})-\alpha\zeta_{t}c_{t}\right)d t\right].}\end{array}
$$  

If we for each $t$ and each state maximize the integrand in the last integral above, we will surely maximize the Lagrangian. The first-order condition is $e^{-\delta t}u^{\prime}(c_{t})=\alpha\zeta_{t}$ and since $\zeta_{0}=1$ , we must have (6.44).  

Exercise 6.10 considers an individual with habit formation in a continuous-time setting.  
