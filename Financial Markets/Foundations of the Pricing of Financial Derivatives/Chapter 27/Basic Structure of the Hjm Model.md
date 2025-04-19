---
tags:
  - '#drift_term'
  - '#forward_rates'
  - '#hjm_model'
  - '#no_arbitrage'
  - '#spot_rate'
  - '#stochastic_volatility'
  - '#volatility_structure'
  - '#wiener_process'
  - '#zero_coupon_bond'
---
# 27.1 BASIC STRUCTURE OF THE HJM MODEL

In contrast to most other term structure models, which are based on movements in spot interest rates, the HJM model is driven by movements in forward interest rates. We start by specifying that the model applies over a period of time $t\in[0,T]$ 2 Let $B(t,T)$ be the price of a zero-coupon bond at time $t$ that pays 1.0 at time $T.$ Define $f(t,T)$ as the continuously compounded forward rate observed at time $t$ for an instantaneous transaction to begin at time $T$ That is, based on the term structure in existence at time $t$ , we observe a forward rate for a transaction to start at $T$ and end an instant later.

In a typical situation, we find the present value of a future amount by discounting at the spot rate. We start with a simple example using annual discrete compounding. For example, suppose we want to know the present value of 1.0 two years from today. We then would discount 1.0 by the operation $1/[1+r(0,2)]^{2}$ where $r(0,2)$ is the two-year spot rate. We can, however, discount by the one-year spot rate and the one-year ahead forward rate. That is, let $f(0,1)$ be the forward rate observed at time 0 for a one-period transaction to start at time 1 and obviously end at time 2.3 Thus, we can find the present value of 1.0 paid at time 2, denoted $B(0,2)$ by the calculation,

$$
B(0,2)=\frac{1}{[1+r(0,1)][1+f(0,1)]}.
$$

The substitution of the one-period spot rate and the one-period ahead forward rate is valid because

$$
f(0,1)=\frac{[1+r(0,2)]^{2}}{1+r(0,1)}-1.
$$

So, in a continuous time world, the price at time $t$ of a 1.0 face value zero-coupon. bond maturing at $T$ is given as

$$
B(t,T)=\exp\left(-\int_{t}^{T}f(t,s)d s\right).
$$

That is, we can obtain the price of a zero-coupon bond by successively discounting at the forward rates. Note that we can extract a given forward rate by differentiating the previous equation with respect to $T$

$$
f(t,T)=-\frac{\partial\log B(t,T)}{\partial T}.
$$

Although Equation (27.2) is a nice mathematical specification of a forward rate, it is not of much practical use without a formula that relates the spot price to its maturity. Such a formula can be obtained only for limited cases.4 This formula reminds us, however,. that forward rates, specifically instantaneous forward rates, are derivatives of bond prices. with respect to maturity. The shortest forward rate, the one defined as. $f(t,t)$ , is of special significance. It is a spot rate that is sometimes called the short rate,.

$$
r(t)=f(t,t).
$$

In the HJM model, this is the only spot rate that commands our attention.

Starting from an initial state at time $0,\mathrm{HM}$ proposes that the forward rate observed at time 0 for period I $;f(0,T)$ , changes in the following manner during the time from 0 to $T$

$$
f(t,T)-f(0,T)=\intop_{0}^{t}\alpha(\nu,T)d\nu+\sum_{i=1}^{n}\intop_{0}^{t}\sigma_{i}(\nu,T)d\mathbb{W}_{i}(\nu).
$$

We must now carefully examine this important equation. The term $\alpha(\nu,T)$ is the instantaneous drift term observed at time. $\nu$ for the forward rate at. $T.$ The second expression on the right-hand side begins with a summation of. $_n$ terms, which means it is an. $_n$ -factor model. These factors are captured by the terms,. $\sigma_{i}(\nu,T)$ and $d\mathbb{W}_{i}(\nu)$ . The term $\sigma_{i}(\nu,T)$ is the volatility of factor. $i$ observed at time $\nu$ for the forward rate at. $T.^{5}$ The term $d\mathbb{W}_{i}(\nu)$ is a Wiener process representing the source of uncertainty for factor $i$ at time $\nu$ There are some formal mathematical restrictions required to uphold these assumptions, but we need not concern ourselves with them here. The expression in simple terms says that the forward rate started off at a value of. $f(0,T)$ and evolved over time to a value of $f(t,T)$ These changes in the forward rate reflected the accumulation, as indicated by the integrals, of the infinitesimal changes that consist of drift and volatility that have occurred over the period 0 to $T$

HJM go on to show that even though we do not really need to know it, the spot rate process can be derived and is quite similar to that of the forward rate:.

$$
r(t)=f(0,t)+\intop_{0}^{t}\alpha(\nu,t)d\nu+\sum_{i=1}^{n}\intop_{0}^{t}\sigma_{i}(\nu,t)d W_{i}(\nu).
$$

In addition, the process for the bond price is given as

$$
\frac{d B(t,T)}{B(t,T)}=[r(t)+b(t,T)]d t+\sum_{i=1}^{n}a_{i}(t,T)d W_{i}(t),
$$

where

$$
\begin{array}{l}{\displaystyle{a_{i}(t,T)\equiv-\int_{t}^{T}\sigma_{i}(t,\nu)d\nu}}\ {\displaystyle{\qquadT}}\ {\displaystyle{b(t,T)\equiv-\int_{t}^{T}\alpha(t,\nu)d\nu+\frac{1}{2}\sum_{i=1}^{n}a_{i}(t,T)^{2}.}}\end{array}
$$

This expression should look somewhat familiar because it resembles the stochastic process ordinarily used for an asset. Note that the drift, however, consists of the risk-free rate and another term, and that there are multiple volatilities representing the various factors.

HJM go on to derive their most important result, which is that the condition of no. arbitrage implies that a martingale probability measure exists and implies a restriction on the drift coefficients of the forward rates. Specifically, for the. $_n$ -factor model, we have

$$
\alpha(t,T)=\sum_{i=1}^{n}\sigma_{i}(t,T)\int_{t}^{T}\sigma(t,\nu)d\nu.
$$

This statement means that the drift is not independent of the volatility and is in fact a specific function of the volatility.6 At a given time point $t_{:}$ , the drift for the forward rate to start at $T$ is obtained by integrating, meaning to essentially add, all of the volatilities over the time periods from $t$ to $T$ and multiplying by the sum of the volatilities across all of the factors observed at $t$ for the rate to start at $T$ Again, this restriction ensures that no arbitrage opportunities are possible. We do not explore the details of how this result is obtained in continuous time, but we will look at it more carefully in a discrete time framework later in this chapter and also in Chapter 28.

In general, the continuous time HJM model is written as

$$
d f(t,T)=\alpha(t,T)d t+\sum_{i=1}^{n}\sigma_{i}(t,T)d W_{t}(t),
$$

with the drift restricted as given above in Equation (27.8).

In the HJM model, the volatility structure is an input. What we mean by a volatility structure is a concept with three dimensions. Consider one volatility, $\sigma_{i}(a,b)$ . It has three parameters. The subscript $i$ refers to the factor that we call. $i.$ There can be many factors,. each of which should be thought of as a source of risk, meaning some effect that drives volatility. Examples of factors might be Federal Reserve policy, government fiscal policy, exchange rates, the stock market, and so on. The HJM model accommodates an unlimited number of factors. Jumping to the third parameter, $b$ identifies the maturity or expiration. of the forward contract to which the rate applies. If $b$ is, say, five, it means that we are. referring to the volatility of a forward contract on the one-period rate that matures in five periods. The other parameter,. $a$ , is a time series factor and reflects how a particular volatility varies over time. For example, for factor $i,$ maturity five, we have $\sigma_{i}(0,5)$ $\sigma_{i}(1,5)$ $\sigma_{i}(2,5),\ldots$ , and so on. These volatilities capture how the risk of that rate varies over time. There is clearly a lot of information in the volatility structure, and although this gives the model a great deal of flexibility, it also places heavy demands on the user. When we illustrate it, we shall use just one factor, a limited number of maturities, and just a few time periods.

There need not be any formal mathematical structure to these volatilities. In other words, they need not be related to each other mathematically. There are some special cases of HJM involving specific mathematical structures to the volatility, such as

$$
\sigma(t,T)=\sigma e^{-\lambda(T-t)},
$$

which is called exponentially dampened volatility. In this case a single volatility,. $\sigma$ , is given and all successive volatilities are related to it. The specification results in volatilities. declining at an exponential rate. This particular structure is especially convenient because. it permits many closed-form solutions for options and other derivatives. For details see Jarrow and Turnbull (2000, Chapters 16 and 17)..

Other volatility functions include the simple case of constant volatility

$$
\sigma(t,T)=\sigma,
$$

which makes this model equivalent to HL. Another case sometimes seen is the nearly proportional volatility,

$$
\sigma(t,T)=\eta(t,T){\operatorname*{min}}[f(t,T),M],
$$

where $\eta(t,T)$ is a deterministic function and $M$ is a large positive constant. This specifica-. tion sets the volatility proportional to the current forward rate and caps it on the upper end so that it will not become unreasonably high. Two other structures seen are

$$
\begin{array}{l}{{\sigma(t,T)=\sigma f(t,T)^{\gamma}}}\ {{}}\ {{\sigma(t,T)=\sigma r(t)^{\gamma}e^{-\lambda(T-t)}.}}\end{array}
$$

Note that these examples and the nearly proportional volatility case are examples of which the volatility is stochastic but completely dependent on the level of rates. Thus, although these are stochastic volatility models, they are not independent stochastic volatility models. Hence, they do not pose any additional problems not already present in the model. For more on volatility structures of the HJM model, see Jarrow (2002), Ritchken (1996), and Ritchken and Sankarasubramanian (1995).
