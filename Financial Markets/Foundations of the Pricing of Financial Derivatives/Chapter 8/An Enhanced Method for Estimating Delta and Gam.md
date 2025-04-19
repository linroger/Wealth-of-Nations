---
tags:
  - binomial_tree
  - delta_estimation
  - gamma_estimation
  - greeks
  - option_pricing
aliases:
  - Enhanced Greeks Method
key_concepts:
  - Binomial tree modification
  - Delta calculation
  - Gamma calculation
  - Theta calculation
  - Vega and Rho
---

# 8.2 AN ENHANCED METHOD FOR ESTIMATING DELTA AND GAMMA

Because delta and gamma should technically be measured without a change in time, a modified method of fiting the binomial tree can be used to achieve this property. Suppose we wish to fit a binomial tree with. $N$ time steps. With this modification we fit the tree. with $N+2$ time steps and position the current asset price in the middle of the second time step, in the following manner. In our example in the previous section, we assess the Greeks assuming we are at point in time 2 with one up move. Figure 8.2 illustrates the binomial tree for a call where the shade indicates actual potential paths for the current stock price $(S u d)$

Now let us position ourselves right in the center where the current asset price is Sud,. with the corresponding option price being. $c_{u d}$ . We shall see that this binomial tree offers. several advantages over the standard approach. As we shall learn in the next sections, it will enable us to calculate both delta and gamma without imposing a time change.8.

# 8.2.1 Delta

Positioned at the current asset price of $S_{u d}$ , we can now measure the effect of a different asset price on the option price without moving forward in time. Notice that at this time point, there are two other asset prices, $S u^{2}$ and $S d^{2}$ . We can observe the effect of the asset

![](d1315db585645b0925f6becad3e06316bae1cd3bd2d44020b091c0ef0c8ae0af.jpg)
FGURE 8.2Two-Period Expanded Binomial Model

price being $S u^{2}$ or $S d^{2}$ at the same time point and measure delta as the average option price change divided by the average asset price change.

$$
\begin{array}{l l}{{\Delta_{c}=\displaystyle\frac{\left(1/2\right)\left(c_{u^{2}}-c_{u d}\right)+\left(1/2\right)\left(c_{u d}-c_{d^{2}}\right)}{\left(1/2\right)\left(S u^{2}-S u d\right)+\left(1/2\right)\left(S u d-S d^{2}\right)}=\displaystyle\frac{c_{u^{2}}-c_{d^{2}}}{S u^{2}-S d^{2}}~\mathrm{and}}}\ {{\Delta_{\phi}=\displaystyle\frac{\left(1/2\right)\left(p_{u d}-p_{u^{2}}\right)+\left(1/2\right)\left(p_{d^{2}}-p_{u d}\right)}{\left(1/2\right)\left(S u^{2}-S u d\right)+\left(1/2\right)\left(S u d-S d^{2}\right)}=\displaystyle\frac{p_{d^{2}}-p_{u^{2}}}{S u^{2}-S d^{2}}.}}\end{array}
$$

So, now our estimate of delta does not permit any passage of time.

# 8.2.2 Gamma

Remember that gamma measures the change in delta, given a change in the asset price. From the point at which the asset is at Sud, we can think of the gamma as being the difference in the change in option price over the change in asset price for the asset price in. the node above and for the asset price in the node below. That is,.

$$
\begin{array}{r l}&{\Gamma_{c}=\frac{\big(\frac{c_{u^{2}}-c_{u d}}{S u^{2}-S u d}\big)-\big(\frac{c_{u d}-c_{d2}}{S u d-S d^{2}}\big)}{(1/2)\big(S u^{2}-S d^{2}\big)}\mathrm{~and~}}\ &{\Gamma_{p}=\frac{\big(\frac{p_{d2}-p_{u d}}{S u d-S d^{2}}\big)-\big(\frac{p_{u d}-p_{u^{2}}}{S u^{2}-S u d}\big)}{(1/2)\big(S u^{2}-S d^{2}\big)}.}\end{array}
$$

The numerator measures the average difference in the delta and the denominator measures the average asset price change. Note that we can now measure gamma at any time step,. including the one before expiration..

# 8.2.3 Theta

As in the standard case, theta will require two time steps ahead of the current price. The theta would then be measured the same as in the standard case:

$$
\begin{array}{r l}&{\Theta_{c}=\frac{c_{u^{2}d^{2}}-c_{u d}}{2\Delta t}\mathrm{~and~}}\ &{\Theta_{p}=\frac{\dot{p}_{u^{2}d^{2}}-\dot{p}_{u d}}{2\Delta t}.}\end{array}
$$

# 8.2.4 Vega and Rho

The same issues concerning the estimation of vega and rho that were discussed previously would apply here. The tree does not technically permit the volatility or the interest rate to change. The tree could be recomputed with small changes in volatilities and interest rates to obtain estimates of the vega and rho, but these measures would technically mean the sensitivity if vega and rho were different but fixed, as opposed to variable.
