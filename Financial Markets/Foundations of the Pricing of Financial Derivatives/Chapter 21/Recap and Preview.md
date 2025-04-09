# 21.4 RECAP AND PREVIEW

In this chapter, we looked at options in which there is more than one underlying asset.. Specifically, we examined options on the greater or lesser valued or greater or lesser per-. forming of two assets. These assets have a second feature not found in standard options in that they enable the user to bet or hedge on which asset will be worth more or less or generate a greater or lesser rate of return.

In Chapter 22, we look at two different types of derivatives: forwards and futures. We do this because they complete our knowledge base in the pricing of derivatives. Yet, they do it in a different manner. As we shall see, they do not require the dynamic hedging we are required to use with options.

# APPENDIX 21A

# Multivariate Feynman-Kac Theorem

Consider the multivariate partial differential equation

$$
\begin{array}{r l r}{\lefteqn{\frac{\partial f(X,t)}{\partial t}+\sum_{k=1}^{N}\frac{\partial f(X,t)}{\partial x_{k}}\mu_{k}(X,t)+\frac{1}{2}\sum_{i=1}^{N}\sum_{k=1}^{N}\frac{\partial^{2}f(X,t)}{\partial x_{i}\partial x_{k}}\sum_{j=1}^{m}\sum_{l=1}^{m}\sigma_{i j}(X,t)\sigma_{k l}(X,t)\rho_{j l}(X,t)}}\ &{}&{-V(X,t)f(X,t)=g(X,t).}\end{array}
$$

Defined for all. $x\in\mathbb{R},t\in(0,T)$ , where $f(X,t):\mathbb{R}^{N}\times(0,T)\rightarrow\mathbb{R}$ is the unknown, subject to the terminal condition,

$$
f(X,t)=b(X).
$$

Note that $\mu,\sigma,b,V,g.$ and $\rho$ , are known functions. Then the Feynman-Kac formula provides the solution as a conditional expectation expressed as

$$
\begin{array}{l}{\displaystyle f(X,t)}\ {=E^{Q}\left[\int\int\cdots\int e^{-\int_{t}^{T}V(X_{\tau},\tau)d\tau}g\big(X_{\tau},\tau\big)d r_{1}\dots d r_{n-1}d r_{n}+e^{-\int_{t}^{T}V(X_{\tau},\tau)d\tau}b(X)\right]X_{t}=x\right]}\end{array}
$$

Under the probability measure. $\mathrm{Q}$ such that $X$ is an Ito process driven by the equation

$$
\begin{array}{r}{d X=\mu(X,t)d t+\sigma(X,t)d W^{Q}.}\end{array}
$$

With $\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf\mathbf{}\mathbf{}\mathbf{}\mathbf{}\mathbf\mathbf{}\mathbf{}\mathbf{}\mathbf\mathbf{}\mathbf{}\mathbf{}\mathbf\mathbf{}\mathbf{}\mathbf\mathbf{}\mathbf{}\mathbf\mathbf{}\mathbf{}\mathbf\mathbf{}\mathbf{}\mathbf\mathbf{}\mathbf\mathbf{}\mathbf{}\mathbf\mathbf{}\mathbf\mathbf{}\mathbf{}\mathbf\mathbf{}\mathbf\mathbf{}\mathbf\mathbf{}\mathbf\mathbf{}\mathbf\mathbf{}\mathbf\mathbf{}\mathbf\mathbf{}\mathbf\mathbf{}\mathbf\mathbf{}\mathbf\mathbf}\mathbf\mathbf{}\mathbf\mathbf{}\mathbf\mathbf{}\mathbf\mathbf\mathbf{}\mathbf\mathbf{}\mathbf\mathbf\mathbf{}\mathbf\mathbf\mathbf{}\mathbf\mathbf\mathbf{}\mathbf\mathbf\mathbf{}\mathbf\mathbf}\mathbf\mathbf{}\mathbf\mathbf\mathbf{}\mathbf\mathbf\mathbf\mathbf{}\mathbf\mathbf\mathbf{}\mathbf\mathbf\mathbf\mathbf{}\mathbf\mathbf\mathbf\mathbf{}\mathbf\mathbf\mathbf\mathbf{}\mathbf\mathbf\mathbf\mathbf}\mathbf\mathbf{}\mathbf\mathbf\mathbf\mathbf\mathbf{}\mathbf\mathbf\mathbf\mathbf\mathbf{}\mathbf\mathbf\mathbf\mathbf\mathbf\mathbf{}\mathbf\mathbf\mathbf\mathbf\mathbf\mathbf{}\mathbf\mathbf\mathbf\mathbf\mathbf\mathbf\mathbf$ a Wiener process under. $\mathcal{Q}$ and the initial condition for $X(t)$ is $X(t)=x$

# APPENDIX 21B

# An Alternative Derivation of the Min-Max Option Model

Let us form a hedge portfolio currently valued at $V$ by placing $x\%$ of our wealth in asset 1, $y\%$ of our wealth in asset 2, and $100\%-x\%-y\%$ of our wealth in the risk-free asset. For example, let $x$ and $y$ be expressed as percentages (e.g., $x=0.3$ or $30\%$ $y=0.6$ or $60\%$ $1-x-y=0.1$ or $10\%$ ). To express the current value of this portfolio consider that we invest $x V$ dollars in asset 1, which will buy $x V/S_{1}$ shares. We invest $y V$ dollars in asset 2, which will buy $y V/S_{2}$ shares. We then invest $V-x V-y V$ dollars in the risk-free asset. The current value of our portfolio can, therefore, be expressed as

$$
V=\left({\frac{x V}{S_{1}}}\right)S_{1}+\left({\frac{y V}{S_{2}}}\right)S_{2}+(1-x-y)V.
$$

The change in the value of this portfolio can be expressed as

$$
d V=\left({\frac{x V}{S_{1}}}\right)d S_{1}+\left({\frac{y V}{S_{2}}}\right)d S_{2}+(1-x-y)V r d t+\delta_{1}\left({\frac{x V}{S_{1}}}\right)S_{1}d t+\delta_{2}\left({\frac{y V}{S_{2}}}\right)S_{2}d t,
$$

which can be written as

$$
d V=x\left({\frac{d S_{1}}{S_{1}}}\right)V+y\left({\frac{d S_{2}}{S_{2}}}\right)V+(1-x-y)V r d t+\delta_{1}x V d t+\delta_{2}y V d t.
$$

Because $d V$ is driven by two stochastic processes, each of which follows a separate lognormal diffusion, we know that the change in. $V$ can also be expressed using the multivariate version of Ito's lemma. In other words,.

$$
\begin{array}{l}{{d V=\displaystyle\frac{\partial V}{\partial S_{1}}d S_{1}+\frac{\partial V}{\partial S_{2}}d S_{2}+\frac{\partial V}{\partial t}d t}}\ {{\qquad+\displaystyle\frac{1}{2}\left(\frac{\partial^{2}V}{\partial S_{1}^{2}}{S_{1}}^{2}{\sigma_{1}}^{2}+\frac{\partial^{2}V}{\partial S_{2}^{2}}{S_{2}}^{2}{\sigma_{2}}^{2}+2\frac{\partial^{2}V}{\partial S_{1}\partial S_{2}}S_{1}S_{2}\sigma_{1}\sigma_{2}\rho_{12}\right)d t.}}\end{array}
$$

Suppose we select the value of $x$ to be $(\partial V/\partial S_{1})S_{1}/V$ and the value of $y$ to be $(\partial V/\partial S_{2})S_{2}/V$ We choose the values $x$ and $y$ based on current conditions, and, therefore, we can certainly set them where they should be, because we know the current values of $\partial V/\partial S_{1}$ $S_{1}$ $\partial V/\partial S_{2},S_{2}$ , and $V$ 5 Making these substitutions and setting Equations (21.39) and (21.40) equal to each other eliminates the stochastic terms, justifying use of the risk-free rate for discounting, leaving the following non-stochastic partial differential equation:

$$
\begin{array}{l}{{\displaystyle{V r=\frac{\partial V}{\partial S_{1}}S_{1}\left(r-\delta_{1}\right)+\frac{\partial V}{\partial S_{2}}S_{2}\left(r-\delta_{2}\right)+\frac{\partial V}{\partial t}}}}\ {{\displaystyle~+\frac{1}{2}\left(\frac{\partial^{2}V}{\partial S_{1}^{2}}{S_{1}}^{2}{\sigma_{1}}^{2}+\frac{\partial^{2}V}{\partial S_{2}^{2}}{S_{2}}^{2}{\sigma_{2}}^{2}+2\frac{\partial^{2}V}{\partial S_{1}\partial S_{2}}S_{1}S_{2}\sigma_{1}\sigma_{2}\rho_{12}\right).}}\end{array}
$$

This equation will apply to any min-max options. The differences in the various minmax options will come from the boundary conditions, which are Equations (21.4) and (21.5). We shall use Equation (21.41) to price a call on the minimum. Therefore its price, the solution to the above PDE, is subject to the boundary condition of Equation (21.2), which we repeat here,

$$
c_{\mathrm{min},T}=\operatorname*{max}\bigl[0,\operatorname*{min}\bigl(S_{1T}S_{2T}\bigr)-X\bigr].
$$

Stulz obtains the solution reported in the chapter by discounting the expected payoff under risk neutrality.

# QUESTIONS AND PROBLEMS

1 One of the challenging aspects of creating min-max options is the need to have similarly priced underlying instruments. Explain how you can transform any two underlying instrument prices to resolve the similarly priced feature.

2  A portfolio of two call options on different stocks with the same maturity and exercise price can be replicated with options on the maximum and/or minimum. Identify the replicating min and/or max option combination and prove that this portfolio is the proper replicating portfolio.

3 Explain how a dividend yield will influence the boundary condition given in the previous problem.

Based on arbitrage arguments, show that Pmax + Pmin = P1 + P2.

5 Based on the previous problems as well as standard put-call parity, we have the following relationships:

$$
\begin{array}{r l}&{p_{\mathrm{max}}+p_{\mathrm{min}}=p_{1}+p_{2},}\ &{\qquadp_{\mathrm{max}}=X e^{-r_{c}\tau}-c_{\mathrm{max},X=0}+c_{\mathrm{max}},}\ &{\qquadp_{\mathrm{min}}=X e^{-r_{c}\tau}-c_{\mathrm{min},X=0}+c_{\mathrm{min}},}\ &{\qquadp_{1}=c_{1}-S_{1}+X e^{-r_{c}\tau},\mathrm{and}}\ &{\qquadp_{2}=c_{2}-S_{2}+X e^{-r_{c}\tau}.}\end{array}
$$

Demonstrate, by substitution, that $c_{\mathrm{max},X=0}+c_{\mathrm{min},X=0}=S_{1}+S_{2}$ Prove with an arbitrage table that this equality holds.

# NOTES

1. We leave the proof of this claim to an end-of-chapter problem.
.. An alternative derivation is provided in Appendix 21.B.
3. Haug (2007) presents a version of this solution; see pp. 211-212.
4. The properties of the lognormal diffusion hold even if the asset is normalized to a value of 1, because the diffusion describes the proportional change in the asset's value.
5. The values of the partial derivatives of $V$ with respect to $S_{1}$ and $S_{2}$ are not known at the present. With the pricing model that solves this PDE, we can then derive these partial derivatives.

# Pricing Forwards, Futures, and Options on Forwards and Futures.

o this point, we have focused exclusively on options and have paid almost no attention to other forms of derivatives. The reason for that approach is that options are somewhat more difficult to price than other derivatives. This is because option values are affected by volatility, and to model the effect of volatility, we have to incorporate characteristics of the distribution of the underlying, and we have to dynamically hedge the option. For other derivatives, the pricing process is much easier and the mathematics much simpler. In this chapter, we shall take a look at these other derivatives-forwards and futures--as well as options on forwards and futures.
