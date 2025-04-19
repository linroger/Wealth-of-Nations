---
tags:
  - binomial_model
  - black_scholes_model
  - delta_hedging
  - option_pricing
  - put_call_parity
aliases:
  - Binomial Model
  - PCP
  - Standard Approach
key_concepts:
  - Call and put options
  - Continuous time world
  - Delta of options
  - Discrete risk-free rate
  - Discrete time approximation
  - Option sensitivities
  - Partial derivatives
  - Put-call parity
  - Static arbitrage transactions
  - Underlying asset price
---

# 8.1 STANDARD APPROACH

Let $S$ be the current price of the underlying asset and. $\boldsymbol{\mathscr{u}}$ and $d$ be the up and down fac-.
tors. The discrete risk-free rate per period is $r_{:}$ and $X$ is the exercise price of the option..
We illustrate both calls and puts in the binomial model for two periods in Figure 8.1.

We are interested in the sensitivities of the option value to the underlying, to time to. expiration, to the volatility, and to the risk-free interest rate. These four parameters are subject to change over time; hence, risk managers need to understand how their option values change along with other assets for which they are responsible..

Recall that put-call parity (PCP) can be expressed generically as

$$
c=S-P V(X)+p,
$$

where $P V(X)$ denotes the present value of $X$ In this and future chapters the interest rate. quotation convention, such as different ways of discrete compounding and even continuous compounding, can vary. Hence, for convenience, we will simply rely on a generic present value function. PCP is based on static arbitrage transactions. Therefore, put-call parity should hold with any model for option pricing. Thus, we will rely on the linkage between puts and calls whenever convenient..

![](92509b192310996d9418a900f411d32f2b5bddc4448bcca7b867ec338be16164.jpg)
FIGURE 8.1 The Binomial Model (Two Periods)

# 8.1.1 Delta

The sensitivity of call and put options to the value of the underlying is called the delta. Of course, it is intuitive that a put moves opposite to the underlying as it benefits from decreases in the price of the underlying. Thus, its delta must be negative. Here, we take the negative of the traditional measure of the put delta to represent it as a positive number, simplifying various binomial model interpretations.2 The call and put deltas are formally defined as

$$
\Delta_{c}=\frac{\partial c}{\partial S}\mathrm{and}\Delta_{\phi}=-\frac{\partial\phi}{\partial S}.
$$

We have specified the deltas in terms of partial derivatives. At this point, we do not have a continuous and differentiable model of the option value, which will come later with the Black-Scholes-Merton model. We can observe the following relationship between call and put deltas based on put-call parity, Equation (8.1), and the fact that the partial derivative of anything with itself is one. Thus, we know (recall our put delta is signed)

$$
\Delta_{c}=1-\Delta_{p}.
$$

In discrete time, we approximate the deltas with the following:

$$
\Delta_{c}\simeq\frac{\Delta c}{\Delta S}\mathrm{and}\Delta_{{p}}\simeq-\frac{\Delta{p}}{\Delta S},
$$

where the delta symbols in the numerator and denominator reflect the change in the prices. of the options and asset from their current prices. The problem in measuring delta in a. binomial tree is that technically we must assume that the asset price changes without an increment of time. Time is a variable and if we advance further into the tree, we have not held time constant. With delta, we are attempting to measure the sensitivity of the. option to a single effect, the change in the value of the underlying. From the binomial tree diagram, we see that the asset price can change only with an increment of time, not at a given instant in time. One way to deal with this problem is to have enough binomial periods so that the length of each time step is very short. There is also another way to fit the tree to deal with the problem, which we explore in the second half of this chapter. For now, let us measure delta the best we can, given the form of the tree we have used to now.

As we shall see later when covering the Black-Scholes-Merton model, in a continuous. time world, the option price is nonlinear with respect to the asset price, meaning that the option price change is not the same upward as it is downward for a given change in the underlying. This result is due to the convexity of the relationship between the option price and the asset price. That convexity is evident in the binomial model as well. Although it is not apparent in Figure 8.1, the option price change is not the same upward as it is downward. In continuous time, we deal with this problem by using the first derivative, which is the limit of the rate of change in the option price for an infinitesimal change in. the asset price. The first derivative linearizes the change in the option price in relation to the change in the asset price. In the binomial model, the usual approach to measuring delta. is to take the average of the two possible call price changes and divide by the average of the two possible asset price changes:3

$$
\begin{array}{l}{\displaystyle\Delta_{c}=\frac{(1/2)(c_{u}-c)+(1/2)(c-c_{d})}{(1/2)(S u-S)+(1/2)(S-S d)}=\frac{c_{u}-c_{d}}{S u-S d}}\ {\displaystyle\Delta_{p}=1-\Delta_{c}=-\frac{(1/2)(p_{u}-p)+(1/2)(p-p_{d})}{(1/2)(S u-S)+(1/2)(S-S d)}=\frac{p_{d}-p_{u}}{S u-S d}.}\end{array}
$$

Recall that in Chapter 7, our derivation of the binomial model revealed that this is the correct measure of delta because it is the number of shares that should be held to hedge in relation to a short position in one call option. This idea is the same notion of delta in the. continuous time world of the Black-Scholes-Merton model. Because the delta is. $\Delta c/\Delta S$ if we hold $\Delta c/\Delta S$ units of the asset and the asset changes by. $\Delta S$ , the position in the asset changes by $(\Delta c/\Delta S)\Delta S=\Delta c$ If we hold one short call, then it changes by. $-\Delta c$ and the net. result is an offset..

# 8.1.2 Gamma

A short option position hedged with delta units of a long asset position will be a perfect hedge provided that the effect of the asset price change is accurately captured by the delta. In the real, non-binomial world, this result will occur only if the asset price change is infinitesimal. Hence, delta-hedged positions are at least partially vulnerable to virtually any change in the asset price, however large that change may be. In other words, there are essentially no changes that are truly infinitesimal in the real world. In addition, the delta will change with any change in time. If the delta changes, the hedged position must be revised to reflect a new number of shares that will balance the asset price risk. If the delta is not revised quickly enough, the hedged position will lose its effectiveness. The. gamma reflects the change in the delta given a change in the asset price and captures this. effect. Technically gamma is somewhat meaningless in a binomial world unless we impose some limitations on our ability to trade to adjust the hedge position whenever the asset price changes. We often use the binomial model to approximate a continuous time world, however, so we need to know how to estimate the gamma in the binomial model.4.

The gamma is formally defined as

$$
\Gamma={\frac{\partial\left({\frac{\partial c}{\partial S}}\right)}{\partial S}}={\frac{\partial^{2}c}{\partial S^{2}}}.
$$

Taking the second derivative of Equation (8.1), we note that the gamma of the call and put are equal or

$$
\Gamma_{c}=\Gamma_{p}.
$$

In the binomial model, we measure the call gamma by first noting that the call delta can change from the above measure,. $\Delta_{\mathrm{c}}$ , either to the new delta if the asset goes up, which we. call $\Delta_{c u}$ , or to the new delta if the asset goes down, which we call. $\Delta_{c d}$ . Using the formula for the call delta, these deltas at time 1 are defined as follows:

$$
\begin{array}{r l}&{\Delta_{c u}=\cfrac{c_{u^{2}}-c_{u d}}{S u^{2}-S u d}}\ &{\Delta_{c d}=\cfrac{c_{u d}-c_{d^{2}}}{S u d-S d^{2}}.}\end{array}
$$

In the binomial model, the gamma is estimated by averaging the change in the delta, $(1/2)(\Delta_{u}-\Delta)+(1/2)(\Delta-\Delta_{d})=(1/2)(\Delta_{u}-\Delta_{d})$ , and dividing by the average change in. the asset price. For the numerator,

$$
(1/2)(\Delta_{u}-\Delta_{d})=(1/2)\left(\frac{c_{u^{2}}-c_{u d}}{S u^{2}-S u d}\right)-(1/2)\left(\frac{c_{u d}-c_{d^{2}}}{S u d-S d^{2}}\right).
$$

For the denominator,

$$
\begin{array}{r l}&{(1/4)(S u^{2}-S u)+(1/4)(S u-S u d)+(1/4)(S u d-S d)+(1/4)(S d-S d^{2})}\ &{\quad=(1/4)(S u^{2}-S d^{2}).}\end{array}
$$

So now we have the following estimate of the call gamma:

$$
\Gamma_{c}=\frac{\left(\frac{c_{u^{2}}-c_{u d}}{S u^{2}-S u d}\right)-\left(\frac{c_{u d}-c_{d^{2}}}{S u d-S d^{2}}\right)}{(1/2)(S u^{2}-S d^{2})}.
$$

Following this logic, the put gamma can be estimated in a similar fashion:

$$
\Gamma_{p}=\frac{\left(\frac{\displaystyle p_{d^{2}}-p_{u d}}{\displaystyle S u d-S d^{2}}\right)-\left(\frac{\displaystyle p_{u d}-p_{u^{2}}}{\displaystyle S u^{2}-S u d}\right)}{(1/2)(S u^{2}-S d^{2})}.
$$

Note that in order to calculate the call or put gamma, you need the asset and option prices two time periods ahead. Thus, one important limitation of this approach is that it is impossible to calculate the gamma one time step before expiration. This point in time, which would often be very close to expiration, would tend to have a high gamma unless the option is deep in- or out-of-the-money. Therefore, there can be a critical need to estimate the gamma at that very point at which it cannot be estimated. One solution is to use a large number of time steps of very short length.

# 8.1.3 Theta

The theta is the effect of the change in time on the option price. It captures the time value decay, meaning that it reflects the rate at which the option price changes when nothing else changes. We know that option prices move toward their exercise values, and at expiration, they equal their exercise value. The formal specification of theta for a continuous time world is

$$
\Theta_{c}=\frac{\partial c}{\partial t}\mathrm{and}\Theta_{p}=\frac{\partial{\boldsymbol{p}}}{\partial t},
$$

where $t$ is the current point in time. If the remaining time is, say, $\tau=T-t$ then $\partial t=$ $T-\partial\tau$ . Sometimes theta is evaluated in terms of $\partial\tau$ , but we need not do so here as the transformation is simple.

Observing the binomial tree diagram, it should be apparent that an estimate of theta is obtained as

$$
\begin{array}{l}{\Theta_{c}=\displaystyle\frac{c_{u d}-c}{2\Delta t}\mathrm{~and~}}\ {\Theta_{p}=\displaystyle\frac{\boldsymbol{p}_{u d}-\boldsymbol{p}}{2\Delta t},}\end{array}
$$

where $\Delta t$ is the length of each time step. Note that we are measuring the change in option price without the effect of an asset price change. Two time steps are required for the asset to return to where it started.5 In other words, to measure the time sensitivity at time 0, we take. the difference in the price two periods later at the same asset price, $c_{u d}.$ and subtract the current option price, dividing that difference by $2\varDelta t$ , because two time steps have elapsed.

# 8.1.4Vega and Rho

Vega and rho are the effects of the volatility and interest rate, respectively, on the option price.6 Unfortunately, vega and rho cannot be measured as easily as delta, gamma, and theta. To understand why, it is necessary to understand the role of volatility and the interest rate in a typical option pricing model.

The volatility and interest rate are assumed constant over the life of the option. When. working in a continuous time world, we can certainly take the derivative of the BlackScholes-Merton model with respect to the volatility or interest rate, but their interpreta-. tions are simply that the option price will be different if we use a different volatility or interest rate. This point should be very clear in the binomial model. The binomial tree changes only as a result of time and the asset price change. The volatility and interest rate affect the up and down factors and the risk-neutral probability, but these parameters are constant throughout the tree. It is possible, however, to allow the up and down factors and the risk-free rate to change, but this is the subject of more advanced models..

If we want to measure the sensitivity of the binomial option price to a different volatil-. ity or interest rate, we would simply recalculate the binomial option value with a different volatility or interest rate, keeping in mind that the sensitivity is different depending on whether we use a higher or lower volatility or interest rate. We would try both an increase and a decrease in the volatility and interest rate. We would then average the option price difference and divide by the average difference of the volatility or interest rate to get a reasonable estimate of the vega or rho.7
