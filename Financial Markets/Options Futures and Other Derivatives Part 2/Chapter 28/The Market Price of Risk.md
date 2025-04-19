---
tags:
  - derivatives
  - market_price_of_risk
  - no_arbitrage
  - risk_return
  - wiener_process
aliases:
  - MPR
  - Market Price of Risk
  - Sharpe Ratio
key_concepts:
  - Derivatives and Wiener process
  - Market price of risk
  - No arbitrage condition
  - Risk and return trade-offs
  - Risk-free rate compensation
---

# 28.1 THE MARKET PRICE OF RISK  

We start by considering the properties of derivatives dependent on the value of a single variable $\theta$ Assume that the process followed by. $\theta$ is  

$$
\frac{d\theta}{\theta}=m d t+s d z
$$  

where $d z$ is a Wiener process. The parameters $m$ and $s$ are the expected growth rate in $\theta$ and the volatility of $\theta$ , respectively. We assume that they depend only on. $\theta$ and time $t$ The variable. $\theta$ need not be the price of an investment asset. It could be something as far. removed from financial markets as the temperature in the center of New Orleans.  

Suppose that $f_{1}$ and $f_{2}$ are the prices of two derivatives dependent only on. $\theta$ and $t$ These can be options or other instruments that provide a payoff in the future equal to some function of $\theta$ Assume that during the time period under consideration. $f_{1}$ and $f_{2}$ provide no income.1  

Suppose that the processes followed by $f_{1}$ and $f_{2}$ are  

and  

$$
\begin{array}{l}{\displaystyle\frac{d f_{1}}{f_{1}}=\mu_{1}d t+\sigma_{1}d z}\ {\displaystyle}\ {\displaystyle\frac{d f_{2}}{f_{2}}=\mu_{2}d t+\sigma_{2}d z}\end{array}
$$  

where $\mu_{1},\mu_{2},\sigma_{1}$ and $\sigma_{2}$ are functions of $\theta$ and $t.$ The $\cdot\angle z^{\flat}$ in these processes must be the same $d z$ as in equation (28.1) because it is the only source of the uncertainty in the prices of $f_{1}$ and $f_{2}$  

The prices $f_{1}$ and $f_{2}$ can be related using an analysis similar to the Black-Scholes. analysis described in Section 15.6. The discrete versions of the processes for $f_{1}$ and $f_{2}$ are  

$$
\begin{array}{r}{\Delta f_{1}=\mu_{1}f_{1}\Delta t+\sigma_{1}f_{1}\Delta z}\ {{}}\ {\Delta f_{2}=\mu_{2}f_{2}\Delta t+\sigma_{2}f_{2}\Delta z}\end{array}
$$  

We can eliminate the $\Delta z$ by forming an instantaneously riskless portfolio consisting of $\sigma_{2}f_{2}$ of the first derivative and $-\sigma_{1}f_{1}$ of the second derivative. If $\Pi$ is the value of the portfolio, then  

$$
\Pi=(\sigma_{2}f_{2})f_{1}-(\sigma_{1}f_{1})f_{2}
$$  

and  

$$
\Delta\Pi=\sigma_{2}f_{2}\Delta f_{1}-\sigma_{1}f_{1}\Delta f_{2}
$$  

Substituting from equations (28.2) and (28.3), this becomes  

$$
\Delta\Pi=(\mu_{1}\sigma_{2}f_{1}f_{2}-\mu_{2}\sigma_{1}f_{1}f_{2})\Delta t
$$  

Because the portfolio is instantaneously riskless, it must earn the risk-free rate. Hence,  

$$
\Delta\Pi=r\Pi\Delta t
$$  

Substituting into this equation from equations (28.4) and (28.5) gives  

$$
\mu_{1}\sigma_{2}-\mu_{2}\sigma_{1}=r\sigma_{2}-r\sigma_{1}
$$  

or  

$$
{\frac{\mu_{1}-r}{\sigma_{1}}}={\frac{\mu_{2}-r}{\sigma_{2}}}
$$  

Note that the left-hand side of equation (28.6) depends only on the parameters of the process followed by $f_{1}$ and the right-hand side depends only on the parameters of the. process followed by $f_{2}$ . Define $\lambda$ as the value of each side in equation (28.6), so that.  

$$
{\frac{\mu_{1}-r}{\sigma_{1}}}={\frac{\mu_{2}-r}{\sigma_{2}}}=\lambda
$$  

Dropping subscripts, equation (28.6) shows thatif $f$ is the price of a derivative dependent. only on $\theta$ and $t$ with  

$$
\frac{d f}{f}=\mu d t+\sigma d z
$$  

then  

$$
\frac{\mu\mathrm{~-~}r}{\sigma}=\lambda
$$  

The parameter $\lambda$ is known as the market price of risk of $\theta$ . (In the context of portfolio performance measurement, it is known as the Sharpe ratio.) It can be dependent on both $\theta$ and $t$ , but it is not dependent on the nature of the derivative $f.$ Our analysis shows that, for no arbitrage, $(\mu-r)/\sigma$ must at any given time be the same for all derivatives that are dependent only on $\theta$ and $t$  

The market price of risk of $\theta$ measures the trade-offs between risk and return that are made for securities dependent on $\theta$ . Equation (28.8) can be written  

$$
\mu\mathrm{~-~}r=\lambda\sigma
$$  

The variable $\sigma$ can be loosely interpreted as the quantity of $\theta$ -risk present in $f.$ On the right-hand side of the equation, the quantity of. $\theta$ -risk is multiplied by the price of $\theta$ -risk. The left-hand side is the expected return, in excess of the risk-free interest rate,. that is required to compensate for this risk. Equation (28.9) is analogous to the capital. asset pricing model, which relates the expected excess return on a stock to its risk. This chapter will not be concerned with the measurement of the market price of risk. This. will be discussed in Chapter 36 when the evaluation of real options is considered..  

It is natural to assume that $\sigma$ , the coefficient of $d z$ , in equation (28.7) is the volatility of $f.$ In fact, $\sigma$ can be negative. This will be the case when $f$ is negatively related to $\theta$ (so that $\partial f/\partial\theta$ is negative). It is the absolute value $|\sigma|$ of $\sigma$ that is the volatility of $f.$ One way of understanding this is to note that the process for $f$ has the same statistical properties when we replace $d z$ by $-d z$  

Chapter 5 distinguished between investment assets and consumption assets. An investment asset is an asset that is bought or sold purely for investment purposes by some investors. Consumption assets are held primarily for consumption. Equation (28.8)  

is true for all investment assets that provide no income and depend only on $\theta$ . If the variable $\theta$ itself happens to be such an asset, then  

$$
\frac{m-r}{s}=\lambda
$$  

But, in other circumstances, this relationship is not necessarily true.  

# Example 28.1  

Consider a derivative whose price is positively related to the price of oil and depends on no other stochastic variables. Suppose that it provides an expected. return of $12\%$ per annum and has a volatility of. $20\%$ per annum. Assume that the. risk-free interest rate is $8\%$ per annum. It follows that the market price of risk of oil is  

$$
\frac{0.12-0.08}{0.2}=0.2
$$  

Note that oil is a consumption asset rather than an investment asset, so its market price of risk cannot be calculated from equation (28.8) by setting. $\mu$ equal to the expected return from an investment in oil and. $\sigma$ equal to the volatility of oil prices.  

# Example 28.2  

Consider two securities, both of which are positively dependent on the 90-day interest rate. Suppose that the first one has an expected return of. $3\%$ per annum and a volatility of $20\%$ per annum, and the second one has a volatility of $30\%$ per annum. Assume that the instantaneous risk-free rate of interest is. $6\%$ per annum. The market price of interest rate risk is, using the expected return and volatility. for the first security,  

$$
\frac{0.03-0.06}{0.2}=-0.15
$$  

From a rearrangement of equation (28.9), the expected return from the second security is, therefore,.  

$$
0.06-0.15\times0.3=0.015
$$  

or $1.5\%$ per annum.  

# Alternative Worlds  

The process followed by derivative price $f$ .5  

$$
d f=\mu f d t+\sigma f d z
$$  

The value of. $\mu$ depends on the risk preferences of investors. In a world where the market price of risk is zero,. $\lambda$ equals zero. From equation (28.9) $\mu=r$ , so that the. process followed by. $f$ is  

$$
d f=r f d t+\sigma f d z
$$  

We will refer to this as the traditional risk-neutral world.  

Other assumptions about the market price of risk, $\lambda$ , enable other worlds that are internally consistent to be defined. From equation (28.9),  

$$
\mu=r+\lambda\sigma
$$  

so that  

$$
d f=\left(r+\lambda\sigma\right)f d t+\sigma f d z
$$  

The market price of risk of a variable determines the growth rates of all securities.   
dependent on the variable. As we move from one market price of risk to another, the expected growth rates of security prices change, but their volatilities remain the same.   
This is Girsanov's theorem, which we illustrated for the binomial model in Section 13.7.   
Choosing a particular market price of risk is also referred to as defining the probability.   
measure. Some value of the market price of risk corresponds to the "real world"' and.   
the growth rates of security prices that are observed in practice..  
