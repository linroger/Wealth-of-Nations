---
tags:
  - arbitrage_principle
  - binomial_model
  - hedge_portfolio
  - put_option
  - risk_free_rate
aliases:
  - Binomial Put Model
  - One-Period Put Pricing
key_concepts:
  - Binomial process
  - Hedge portfolio
  - No-arbitrage model
  - Put option valuation
  - Risk-free return
---

# 7.2 THE ONE-PERIOD BINOMIAL MODEL FOR PUTS

Here we follow a similar pattern with puts as we did with calls in the last section. We specified an asset priced at S that can go up to. $S u$ Or down to $S d$ (the up state and down state, respectively). This basic idea was communicated in Figure 7.1. Now consider a put.

option with exercise price $X$ that expires in one period. The two possible values of the option at expiration are

$$
\begin{array}{r}{\boldsymbol{p}_{u}=\boldsymbol{\mathrm{max}}(0,\boldsymbol{X}-\boldsymbol{S}\boldsymbol{u})}\ {\boldsymbol{p}_{d}=\boldsymbol{\mathrm{max}}(0,\boldsymbol{X}-\boldsymbol{S}\boldsymbol{d}).}\end{array}
$$

Recall our objective is to determine the value of the put option today. As with the call, the basic layout with the corresponding option prices inserted at each node is in Figure 7.4.

Again, appealing to the arbitrage principle, we shall create a portfolio consisting of the put option and the underlying asset. We shall set this portfolio up so that it is hedged, meaning that its future value is known for certain. In the put case, put prices move in the opposite direction to the underlying asset. Thus, if we buy a put, to hedge we will need to buy the underlying asset. A hedged portfolio must, therefore, earn the risk-free rate $(r)$ We can then solve for the price of the option that is consistent with a risk-free return on this portfolio.

Let us buy $b_{p}$ units of the asset and buy one put. The value of this portfolio today is

$$
V=b_{\rho}S+\rho.
$$

The payoffs of this portfolio in the two future states will be

$$
\begin{array}{r}{V_{u}=b_{p}S u+\operatorname*{max}(0,X-S u)=b_{p}S u+p_{u}}\ {V_{d}=b_{p}S d+\operatorname*{max}(0,X-S d)=b_{p}S d+p_{d}.}\end{array}
$$

Figure 7.5 illustrates the setup for puts. Again, the goal is to establish the linkages between the underlying asset, the put option, and this unique hedge portfolio.

Again, to form a hedge portfolio, we need the number of underlying assets to have the. same sign as the number of puts. That is, we need to either buy the underlying and buy the put or short the underlying and sell the put..

![](b0613005d3dc4733b2a56c055368ca812308ae8eb67f48566ca5809d5942b7a4.jpg)
FGURE 7.4 Binomial Process for Underlying Asset and Put Option

![](cbde51600de04f8eb4f83af7b3c6af730645812bee82c47fcc7e6692e08ff5d7.jpg)
FIGURe 7.5 Binomial Process for Underlying Asset, Put Option, and Hedge Portfolio

Recall this portfolio replicates a risk-free bond and thus the two portfolio values at the next time step have to be equal or

$$
V_{u}=V_{d}.
$$

If we set these two values equal to each other, we have one simple equation with one unknown, $b_{\rho}S u+p_{u}=b_{\rho}S d+p_{d}$ . Thus,

$$
b_{p}={\frac{p_{d}-p_{u}}{S u-S d}}.
$$

Because the option is a put,. $\boldsymbol{p}_{d}>p_{u}$ , and Equation (7.14) will be positive. This result. should make sense. You are long the put and puts move opposite to the underlying, so you. should be long the underlying. To avoid arbitrage, the portfolio must be priced to earn the risk-free rate. Again, the following condition must hold:.

$$
V={\frac{V_{u}}{1+r}}
$$

$$
V={\frac{V_{d}}{1+r}}.
$$

We again choose $V_{u}$

$$
\begin{array}{c}{{\displaystyle{\frac{V_{u}}{1+r}}=V}}\ {{\displaystyle{\frac{b_{p}S u+p_{u}}{1+r}}=b_{p}S+p.}}\end{array}
$$

Therefore, the put price can be represented based on the no-arbitrage model as

$$
\begin{array}{c}{{\displaystyle p=B_{p}-b_{p}S}}\ {{\displaystyle B_{p}=\frac{b_{p}S u+p_{u}}{1+r}.}}\end{array}
$$

The remainder of the derivation proceeds exactly as with the derivation of the call. The end result or the risk-neutral model is functionally identical:

$$
\begin{array}{c}{{\displaystyle p=P V\bigl[E(p_{T})\bigr]=\frac{\phi p_{u}+(1-\phi)p_{d}}{1+r}}}\ {{\phi=\frac{1+r-d}{u-d}.}}\end{array}
$$

Again, suppose the current stock price is 99, the exercise price is 100, the annual, discretely compounded, risk-free rate is $2\%$ , the time to expiration is one year, $u=1.25$ and $d=0.8$ . Similar to the call, we can compute the put price in two ways. First, note that $p_{u}=\operatorname*{max}(0,100-123.75)=0$ and $p_{d}=\operatorname*{max}(0,100-79.2)=20.8.$ For the no-arbitrage model, we find the hedge ratio $b_{\phi}=(p_{d}-p_{u})/(u S-d S)=(20.8-0)/(123.75-79.2)=$ 0.4669. Therefore, based on Equation (7.16), we have

$$
{\frac{b_{p}S u+p_{u}}{1+r}}-b_{p}S={\frac{0.4669(99)1.25+0}{1+0.02}}-0.4669(99)=56.6460-46.2231=10.42.
$$

Alternatively, we can use the risk-neutral model. Again, we have. $\phi=(1+0.02-0.8)/$ $(1.25-0.8)=48.8889\%$ Therefore, based on Equation (7.18), we find the same results or

$$
p={\frac{0.4889(0)+(1-0.4889)20.8}{1+0.02}}=10.42.
$$
