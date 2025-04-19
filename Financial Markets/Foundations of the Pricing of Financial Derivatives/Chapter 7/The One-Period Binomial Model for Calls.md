---
tags:
  - arbitrage
  - binomial_model
  - call_option
  - hedge_ratio
  - risk_free_rate
aliases:
  - BOPM
  - Binomial Option Pricing
key_concepts:
  - Binomial tree
  - Hedge portfolio
  - No-arbitrage principle
  - One-period binomial model
  - Up and down states
---

# 7.1 THE ONE-PERIOD BINOMIAL MODEL FOR CALLS

Recalling from the previous chapter, we specified an asset priced at. $S$ that can go up to $S u$ or down to Sd. Given the historical decision to assume a lognormal distribution, early authors pursued a multiplicative binomial approach.1 We shall refer to these two states as. the up state and the down state, respectively. The basic idea is communicated in Figure 7.1. At the initial point in time, there is only one node, whereas at the next point in time, there. are only two nodes. Also, at the initial point in time, there are two arcs emanating from the initial node.

This type of figure is sometimes called a binomial tree, although it will look a little more like a tree when we expand it later..

The risk-free rate is $r.$ Consider a call option with exercise price $X$ that expires in one period. The two possible values of the option at expiration are

$$
\begin{array}{l}{{c_{u}=\mathrm{max}(0,S u-X)}}\ {{c_{d}=\mathrm{max}(0,S d-X).}}\end{array}
$$

Of course, our objective is to determine the value of the option today,. $^{c.}$ The basic layout with the corresponding option prices inserted at each node is in Figure 7.2.

Appealing to the arbitrage principle, we shall create a portfolio consisting of the option and the underlying asset. We shall set this portfolio up so that it is hedged, meaning that its future value is known for certain. A hedged portfolio must, therefore, earn the risk-free rate. We can then solve for the price of the option that is consistent with a risk-free return on this portfolio.

Let us buy $b_{c}$ units of the asset and sell one call. The value of this portfolio today is

$$
V=h_{c}S-c.
$$

![](5234a4ee7a189c8be56f729cf614589ccb08fd51b8e3da2245437894ecac9e2a.jpg)
FIGURE 7.1 Binomial Process for Underlying Asset

![](e9f7333a512a646f3c08abd074c88ae68263f7b2b73308be68702a4e1e2b53af.jpg)
FIGURE 7.2 Binomial Process for Underlying Asset and Call Option

The payoffs of this portfolio in the two future states will be

$$
\begin{array}{r}{V_{u}=b_{c}S u-\operatorname*{max}(0,S u-X)=b_{c}S u-c_{u}}\ {V_{d}=b_{c}S d-\operatorname*{max}(0,S d-X)=b_{c}S d-c_{d}.}\end{array}
$$

Figure 7.3 illustrates the setup. The goal is to understand the linkages between the under lying asset, the call option, and this unique hedge portfolio.
If this portfolio replicates a risk-free bond, it must produce a risk-free return, meaning that these two outcomes are the same, as specified by the condition,

$$
V_{u}=V_{d}.
$$

![](2223071c10c90effe8c5e334e5677dfd52772ead7c0aa811fe143703af7c37bc.jpg)
FIGURE 7.3 Binomial Process for Underlying Asset, Call Option, and Hedge Portfolio

If we set these two values equal to each other, we have one simple equation with one unknown, $b_{c}S u-c_{u}=b_{c}S d-c_{d}$ The solution is known as the hedge ratio and is expressed as follows:

$$
b_{c}={\frac{c_{u}-c_{d}}{S u-S d}}.
$$

Note that the sign of $b_{c}$ will be positive as $c_{u}>c_{d}$ and $S u>S d$ The logic of a positive sign for $b_{c}$ is based on the fact that we prespecified that we are short one call option, as indicated by the minus sign in front of $c$ in Equation (7.2). In effect, the call position is $-1$ unit. The. asset position is $b_{c}>0$ units. We are long the asset and short the call option. Because call values are positively related to the values of their underlying assets, it is intuitive that a short call would be offset by long units of the asset.

Thus, if the number of units of the asset that we hold is set to $b_{c}$ , the two future values of the portfolio will be identical. Hence, the portfolio is risk free. To avoid arbitrage, the portfolio must be priced to earn the risk-free rate. Thus, the following condition must hold:

$$
V={\frac{V_{u}}{1+r}}
$$

$$
V={\frac{V_{d}}{1+r}}.
$$

Consequently, we can apply the following condition, using either $V_{u}$ or $V_{d}$ .We will choose $V_{u}$

$$
\begin{array}{c}{{\displaystyle{\frac{V_{u}}{1+r}}=V}}\ {{\displaystyle{\frac{b_{c}S u-c_{u}}{1+r}}=b_{c}S-c.}}\end{array}
$$

Therefore, the call price can be represented based on the no-arbitrage model as

$$
\begin{array}{c}{c=b_{c}S-B_{c}}\ {B_{c}=\cfrac{b_{c}S u-c_{u}}{1+r}.}\end{array}
$$

Thus, a call option can be replicated by purchasing $b$ units of stock partially financed through borrowing of $B_{c}$ . A call is simply a leveraged position in a stock, that is, a call is equivalent to buying stock with borrowed money. As we will see later, the degree of leverage is dynamic.

The next step is to insert the solution for $b$ , Equation (7.8), and solve for. $c$

$$
\begin{array}{c}{{c=P V\bigl[E(c_{T})\bigr]=\displaystyle\frac{\phi c_{u}+(1-\phi)c_{d}}{1+r}}}\ {{\phi=\displaystyle\frac{1+r-d}{u-d}.}}\end{array}
$$

There are quite a few steps and algebraic substitutions that lead from Equation (7.8) to. Equation (7.9). Details are provided in Appendix 7A of this chapter. Thus, a call price. is simply the present value of the expected future call payoffs discounted at the risk-free. rate. The probabilities used in forming the expectations, however, are not the real probabilities. They are the risk-neutral probabilities and this model is known as the risk-neutral model. The risk-neutral model is based on the expectation taken using risk-neutral prob-. abilities and discounting at the risk-free interest rate..

For example, suppose the underlying is a stock and its current price is 99, the exercise price is 100, the annual, discretely compounded, risk-free rate is $2\%$ , the time to expiration is one year, $u=1.25$ , and $d=0.8$ .We can compute the call price in two ways. First, note that $c_{u}=\operatorname*{max}(0,123.75-100)=23.75$ and $c_{u}=\mathrm{max}(0,79.2-100)=0$ . For the no-arbitrage model, we first find the hedge ratio $b_{c}=(c_{u}-c_{d})/(S u-S d)=(23.75-0)/$ $(123.75-79.2)=0.5331$ Therefore, based on Equation (7.8), we have

$$
\begin{array}{l c r}{{c=h_{c}S-\displaystyle\frac{h_{c}S u-c_{u}}{1+r}=0.5331(99)-\displaystyle\frac{0.5331(99)1.25-23.75}{1+0.02}}}\ {{~=52.7769-41.3933=11.38.}}\end{array}
$$

Alternatively, we can apply the risk-neutral model. The binomial probability of an up move is $\phi=(1+0.02-0.8)/(1.25-0.8)=48.8889\%.$ Therefore, based on Equation (7.9), we. find the same results, or

$$
c={\frac{0.4889(23.75)+(1-0.4889)0}{1+0.02}}=11.38.
$$
