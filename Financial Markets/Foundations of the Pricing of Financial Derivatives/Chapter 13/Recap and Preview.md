---
tags:
  - '#arithmetic_brownian_motion'
  - '#black_scholes_merton_model'
  - '#dividend_yield'
  - '#dynamic_hedging'
  - '#european_options'
  - '#option_greeks'
  - '#option_pricing'
  - '#partial_differential_equation'
  - '#put_call_parity'
---
# 13.9 RECAP AND PREVIEW

In this chapter, we showed how the Black-Scholes-Merton model is derived. We illustrated.
the construction of the dynamic hedge that eliminates the effect of movements in the underlying asset. With the risk eliminated, the hedge portfolio should earn the risk-free rate..
There is one and only one call option value that ensures this will be true. If it is not true,.
there is an opportunity for a dynamic arbitrage, which we assume cannot exist under these.
conditions. We also derive the put version of the model..

In addition, we showed how the model can be derived as the discounted expected payoff of the option under the risk-neutral measure. Further, we established the link between the expectations approach and the PDE approach for deriving the Black-Scholes-Merton model. We also showed how the Black-Scholes-Merton model can be decomposed into two models: price asset-or-nothing options and cash-or-nothing options. Hence, a standard European option is--in effect-a combination of a long position in an asset-or-nothing option and short $X$ cash-or-nothing options. The latter are also referred to as binary options or digital options.

We conclude this chapter by exploring some of the Black-Scholes-Merton model limits as well as illustrating a few calculations of option prices..

In Chapter 14, we show how the derivatives of the model are obtained, and we provide the Greeks, which as you should recall from the binomial model, are the sensitivities to the factors that go into the model.

# APPENDIX 13.A

# Deriving the Arithmetic Brownian Motion Option Pricing Model

In this appendix, we derive the call and put prices based on arithmetic Brownian motion (ABM) incorporating a dividend yield. We assume ABMGD or

$$
d S_{t}=\alpha S_{t}d t+\sigma_{\S}d\mathrm{W}_{t}.
$$

As given in this chapter, we construct a hedge portfolio consisting of $b$ units of the asset and one short call option. The value of this portfolio at time. $t$ is

$$
V_{t}=h S_{t}-c_{t}.
$$

Given that we seek to make this portfolio risk free, we use Ito's lemma to express the call price change in terms of the changes in $S_{t}$ and $t.$

$$
d c=\frac{\partial c}{\partial S}d S+\frac{\partial c}{\partial t}d t+\frac{1}{2}\frac{\partial^{2}c}{\partial S^{2}}d S^{2}.
$$

Given the properties of the Wiener process,. $d\mathbb{W}_{t}$ we know that $d S^{2}=\sigma_{\S}^{2}d t$ for ABM. We know that the value of the portfolio is a function of the asset price, the dividend yield, and the option price. Hence, using the total differential rule, we can express the change in the. value of the portfolio as.

$$
d V={\frac{\partial V}{\partial S}}(d S+\delta S d t)+{\frac{\partial V}{\partial c}}d c,
$$

where $\begin{array}{r}{\frac{\partial V}{\partial S}=b}\end{array}$ and $\begin{array}{r}{\frac{\partial V}{\partial c}=-1}\end{array}$ . Note that the dividend yield results in a positive cash flow to the portfolio over time. Thus, the change in the value of the portfolio is

$$
d V=b\left(d S+\delta S d t\right)-d c.
$$

Substituting from Ito's lemma for $d c$ gives

$$
d V_{t}=b\left(d S+\delta S d t\right)-\left(\frac{\partial c}{\partial S}d S+\frac{\partial c}{\partial t}d t+\frac{1}{2}\frac{\partial^{2}c}{\partial S^{2}}\sigma_{\S}^{2}d t\right),
$$

which is a stochastic partial differential equation that defines the change in the value of the portfolio in terms of several expressions. Observe that the stochastic terms are the $d S$ terms but note that they amount to the simple expression $b d S-(\partial c/\partial S)d S.$ As with GBM, we are free to set $b$ to whatever we want as long as its value can be determined before the asset price changes. It should be apparent that by setting $b$ to $\partial c/\partial S$ the two $d S$ terms cancel, leaving the following expression for the change in the value of the portfolio:

$$
d V={\frac{\partial c}{\partial t}}\delta S d t-\left({\frac{\partial c}{\partial t}}d t+{\frac{1}{2}}{\frac{\partial^{2}c}{\partial S^{2}}}\sigma_{\mathbb{S}}^{2}d t\right).
$$

Notice in this case again that there are no stochastic terms, so this portfolio is perfectly hedged. Thus, to avoid arbitrage the portfolio value, $V$ , must increase at the risk-free rate. This specification is made by the requirement that

$$
d V=V r_{c}d t.
$$

We now substitute $b S-c=(\partial c/\partial S)S-c$ for $V$ to obtain

$$
d V=\left({\frac{\partial c}{\partial S}}S-c\right)r_{c}d t.
$$

We then have two expressions for. $d V.$ Equating these two expressions and canceling the dt terms gives

$$
\left(r_{c}-\delta\right)S\frac{\partial c}{\partial S}+\frac{\partial c}{\partial t}+\frac{1}{2}\frac{\partial^{2}c}{\partial S^{2}}\sigma_{\S}^{2}=r_{c}c.
$$

This equation is a partial differential equation of which the solution,. $c_{:}$ , is the call option price. As before, the solution is subject to the boundary conditions, which refers to the value of $c$ at the option expiration. In the case of a European call, the condition is that. $c_{T}=\operatorname*{max}\bigl(0,S_{T}-\bar{X}\bigr)$

The ABM model is known to be represented as13

$$
c=e^{-r_{c}\tau}\left[\left(S e^{(r_{c}-\delta)\tau}-X\right)N(d_{n})+\sigma_{5}\sqrt{\frac{e^{2\left(r_{c}-\delta\right)\tau}-1}{2\left(r_{c}-\delta\right)}}n(d_{n})\right],
$$

where $N(d_{n})$ is the area under the standard cumulative normal distribution up to $d_{n}$ and $n(d_{n})$ is the value for the standard normal probability density function where

$$
d_{n}=\frac{S e^{\left(r_{c}-\delta\right)\tau}-X}{\sigma_{\mathbb{S}}\sqrt{\frac{e^{2(r_{c}-\delta)\tau}-1}{2\left(r_{c}-\delta\right)}}}.
$$

Note that the put formula follows directly from put-call parity or

$$
\begin{array}{l}{{\displaystyle p=X e^{-r_{c}\tau}-S e^{-\delta\tau}+c}}\ {{\mathrm{}~=X e^{-r_{c}\tau}-S e^{-\delta\tau}+e^{-r_{c}\tau}\left[\left(S e^{(r_{c}-\delta)\tau}-X\right)N(d_{n})+\sigma_{5}\sqrt{\frac{e^{2(r_{c}-\delta)\tau}-1}{2\left(r_{c}-\delta\right)}}n(d_{n})\right]}}\ {{\mathrm{}~=e^{-r_{c}\tau}\left[\left(X-S e^{(r_{c}-\delta)\tau}\right)N(-d_{n})+\sigma_{5}\sqrt{\frac{e^{2(r_{c}-\delta)\tau}-1}{2\left(r_{c}-\delta\right)}}n(d_{n})\right].}}\end{array}
$$

We now proceed with illustrating the manual calculations of call and put values based on arithmetic Brownian motion. We again start with a non-dividend-paying example with an at-the-money call option where the stock price is 50, the volatility is 19.967, the interest rate is $2\%$ , and the time to maturity is 0.25. The first step in manual calculations requires the computation of $d_{n}$ . Recall that at-the-money implies $S=X$ , thus we have

$$
d_{n}={\frac{S_{\delta}^{\left(r_{c}-\delta\right)\tau}-X}{\sigma_{\mathbb{S}}{\sqrt{\frac{e^{2\left(r_{c}-\delta\right)\tau}-1}{2\left(r_{c}-\delta\right)}}}}}={\frac{50e^{(0.02-0)0.25}-50}{19.967{\sqrt{\frac{e^{2\left(0.02-0\right)0.25}-1}{2\left(0.02-0\right)}}}}}=0.025.
$$

The second step is to look up the values of $N(d_{n})$ from Table 5.1. As before, the value for $N(d_{n})$ is found by locating the row starting with 0.0. From that row locate the column with heading of 0.025. Thus, $N(d_{n})=0.509973$ The final step is to substitute these values into the call equation or

$$
\begin{array}{r l}&{=e^{-r_{c}\tau}\left[\left(S e^{(r_{c}-\delta)\tau}-X\right)N(d_{n})+\sigma_{5}\sqrt{\frac{e^{2(r_{c}-\delta)\tau}-1}{2\left(r_{c}-\delta\right)}}n(d_{n})\right]}\ &{=e^{-0.02(0.25)}\left[\left(S0e^{(0.02-0)0.25}-50\right)0.025+19.967\sqrt{\frac{e^{2(0.02-0)\tau}-1}{2(0.02-0)}}\frac{e^{-0.025^{2}/2}}{\sqrt{2\pi}}\right]=4.09}\end{array}
$$

Put-call parity is the most efficient way to compute the put value when the call value is known. Thus,

$$
p=X e^{-r_{c}\tau}-S e^{-\delta\tau}+c=50e^{-0.02(0.25)}-50e^{-0(0.25)}+4.0988=\S3.8495.
$$

But for a slight rounding error, these option values are identical to those found in the. chapter. The only input difference was a price change volatility of. $19.967\$ rather than a. relative volatility of $40\%$ . Notice that. $40\%$ of 50 stock is 20. Thus, relative volatility of. $40\%$ or a $\$50$ stock implies a one standard deviation move would be. $\$20$ . Thise $\$20$ is closely aligned with our assumed $\$19.967$ . Though not precise, we see that with a slight. reduction to 19.967 we have the same option values. This slight difference is driven by the different distributional assumptions made where the Black-Scholes-Merton model is based on the lognormal distribution of terminal asset prices, whereas the arithmetic Brownian motion model is based on the normal distribution of terminal asset prices.

As in the chapter, let us consider the influence of a $2\%$ dividend yield $\delta=0.02^{\prime}$ on our calculations given in the previous example. In this case, $d_{n}$ or14

$$
d_{n}={\frac{S e^{(r_{c}-\delta)\tau}-X}{\sigma_{\mathbb{S}}{\sqrt{\frac{e^{2(r_{c}-\delta)\tau}-1}{2(r_{c}-\delta)}}}}}={\frac{50e^{(0.02-0.02)0.25}-50}{19.967{\sqrt{\frac{e^{2(0.02-0.02)0.25}-1}{2(0.02-0.02)}}}}}=0.0.
$$

The value for $N(d_{n})$ is 0.5 and thus we have

$$
\begin{array}{l}{c={e^{-r_{c}\tau}}\left[{\left({S e^{(r_{c}-\delta)\tau}}-X\right)N\left(d_{n}\right)+\sigma_{5}\sqrt{\frac{{e^{2\left(r_{c}-\delta\right)\tau}}-1}{2\left(r_{c}-\delta\right)}}n\left(d_{n}\right)}\right]}\ {={e^{-0.02\left(0.25\right)}}{\left[{\left({50{e^{\left(0.02-0.02\right)0.25}}-50}\right)0.025+19.967\sqrt{\frac{{e^{2\left(0.02-0.02\right)\tau}}-1}{2\left(0.02-0.02\right)}}\frac{{e^{-0.0^{2}/2}}}{\sqrt{2\pi}}}\right]}}\end{array}
$$

Applying put-call parity, we have

$$
\begin{array}{l}{{\displaystyle p=X e^{-r_{c}\tau}-S e^{-\delta\tau}+c}}\ {{\displaystyle~=50e^{-0.02(0.25)}-50e^{-0.02(0.25)}+3.9630=3.9630.}}\end{array}
$$

Again, both call and put values are identical because the underlying growth rate under the equivalent martingale measure is zero. Also, we see that the call value declined and the put value increased when the dividend yield was changed from $0\%$ to $2\%$ . Therefore, the Black-Scholes-Merton model and arithmetic Brownian motion model have similar properties.

# QUESTIONS AND PROBLEMS

1 Assuming a stock price is modeled with arithmetic Brownian motion with geometric drift, $d S_{t}=\alpha S_{t}d t+\sigma_{\mathbb{S}}d\mathbb{W}_{t}$ derive the partial differential equation based on the hedging. approach for call options given in this chapter..

2 Assuming a stock price is modeled with geometric Brownian motion with geometric drift, $d S_{t}=\alpha S_{t}d t+\sigma S_{t}d W_{t}$ , derive the partial differential equation based on the hedging approach for put options given in this chapter. Do not rely on put-call parity..

3Prove Equation (13.20) is true:

$$
1+\alpha d t+\sigma d W=1+\Big[\big(\alpha-\sigma^{2}/2\big)d t+\sigma d W+\left(\big(\alpha-\sigma^{2}/2\big)d t+\sigma d W\right)^{2}/2\Big].
$$

4 Suppose a particular asset price follows geometric Brownian motion or $d S_{t}=\mu S_{t}d t+$ $\sigma S_{t}d\mathbb{W}_{t}$ . Prove the probability that $S_{t}$ is greater than $X$ $\operatorname*{Pr}\left(S_{t}>X\right)$ , is $N(d_{2})$ as defined in the Black-Scholes-Merton model except that the risk-free interest rate, $r_{c:}$ is replaced with the investor's expected rate of return, $\mu$

5 Suppose we have a stock trading at 100 per share. If the stock price follows $d S_{t}=$ $\mu S_{t}d t+\sigma S_{t}d\mathbb{W}_{t}$ , compute the probability of the stock exceeding its current value with a particular risk-averse investor's view with $\mu=8.0\%$ and $\sigma=31.6\%$ . Compare your answer to the case of a risk-neutral investor's view with the risk-free interest rate of $r_{c}=5.0\%$ and $\sigma=40\%$ . Explain your results.

6 Suppose we have a stock trading at 100 per share. Further suppose that the stock's volatility is $30\%$ and the risk-free rate is $5\%$ . Using Table 5.1, compute the Black-Scholes-Merton option value of an at-the-money call and put option with one year to expiration. (Assume the dividend yield is zero.)

7 Suppose we have a stock trading at 100 per share, the stock's volatility is $30\%$ and the risk-free rate is $5\%$ . In this case, assume the dividend yield is. $5\%$ . Using Table 5.1, compute the Black-Scholes-Merton option value of at-the-money call and put options with one year time to expiration.

8  Given the arithmetic Brownian motion with geometric drift model,. $d S=\mu S d t+\sigma d\mathrm{W}_{\cdot}$ derive the corresponding partial differential equation. Further, given the partial derivatives below, verify that the call model given here is valid:.

$$
\begin{array}{c}{{c=\left(S-X e^{-r\tau}\right)N\left(d_{n}\right)+\sigma_{5}\sqrt{\frac{1-e^{-2r\tau}}{2r}}n\left(d_{n}\right),d_{n}=\frac{S e^{r\tau}-X}{\sigma_{5}\sqrt{\frac{e^{2r\tau}-1}{2r}}}=\frac{S_{0}-X e^{-r\tau}}{\sigma_{5}\sqrt{\frac{1-e^{-2r\tau}}{2r}}},}}\ {{n\left(d_{n}\right)=\frac{e^{-d_{n}^{2}/2}}{\sqrt{2\pi}},N\left(d_{n}\right)=\displaystyle\int_{-\infty}^{d_{n}}\frac{e^{-x^{2}/2}}{\sqrt{2\pi}}d x,\frac{\partial c}{\partial S}=N(d_{n}),\frac{\partial^{2}c}{\partial S^{2}}=\frac{n\left(d_{n}\right)}{\sigma_{5}\sqrt{\frac{1-e^{-2r\tau}}{2r}}},\mathrm{and}}}\ {{\frac{\partial c}{\partial t}=-r X e^{-r\tau}N\left(d_{n}\right)-\frac{\sigma e^{-2r\tau}}{2\sqrt{\frac{1-e^{-2r\tau}}{2r}}}n\left(d_{n}\right).}}\end{array}
$$

# NOTES

1. Naturally the option price is also a function of the exercise price, $X$ , the continuously compounded risk-free rate, $r_{c}$ , and the volatility, $\sigma$ , but these values are static and, thus, they are parameters rather than variables. They can, of course, vary from option to option, but they are not allowed to vary internally, that is, within the dynamics of the evolution of the underlying asset and the price of the specific option over the life of the option.
2. To reduce notational clutter, where feasible, we eliminate the $t$ subscripts on $c_{t},V_{t}$ and $S_{t}$
3. Differential equations are also sometimes associated with initial conditions, such as when the value of the variable at the start is known. In the case of an option, the initial condition is that the price is nonnegative and bounded from above by the asset price.
4. Bachelier assumes arithmetic Brownian motion with arithmetic drift where the asset follows the stochastic process, $d S=\alpha_{\S}d t+\sigma_{\S}d\mathrm{W}.$ The asset value can go below zero.
;. See for example, Sprenkle (1961), Boness (1964), and Samuelson and Merton (1965).
6. Rubinstein (1976) has shown that the Black-Scholes-Merton model can be derived an alternative way, which requires no assumptions about the ability to continuously adjust a hedge.
7. Full details of this interesting side story are not clear, but it seems to be the case that Merton developed the mathematical insights, but in deference to Black and Scholes, he withheld the publication of his paper until the Black and Scholes paper appeared in print. Interestingly, Black and Scholes were working on two papers at the time, with the second paper being an empirical test of the model using over-the-counter option price data. That paper was presented at the annual meeting of the American Finance Association in 1971 and appeared in print in The Journal of Finance in 1972 (Black and Scholes 1972). Meanwhile, the original Black and Scholes paper, which derived the model, was rejected by the University of Chicago's renowned Journal of Political Economy (JPE). Black and Scholes then submitted the paper to Harvard's Review of Economics and Statistics, which also rejected it. Then the University of Chicago's Merton Miller suggested that the Journal of Political Economy reconsider the paper, because Miller believed it was a major breakthrough. The $J P E$ then agreed to publish the paper and it appeared in print in 1973, about the same time as the Merton paper but after the model's empirical tests had already appeared in the Journal of Finance. Other interesting stories about the development and use of the model are in Black (1989a, 1989b) and Mehrling (2005), and an excellent treatment of its impact on Wall Street is Bernstein (1996).

8. We illustrate the derivation of the arithmetic Brownian motion alternative in Appendix 13A. Although the ultimate formula is different, the approach to finding it is very similar..

9. For notational simplicity, we have dropped the time subscript on $\mathbb{W}_{t}$ and $\varepsilon_{t}$

10. See Chapter 10, Section 10.3, if you need a review of the properties of the Wiener proce!

11. The terms $\boldsymbol{\mathscr{u}}$ and $q$ certainly look remarkably like terms in the Black-Scholes-Merton model, leading one to wonder how the equation would be solved if one did not already know the solution. As noted, earlier models had provided some guidance here. Moreover, solving partial differential equations often proceeds based on guesses of general forms of solutions.

12. A cash-or-nothing call can be structured to pay a different amount than $X$ In that case, $X$ would be replaced by the amount to be paid, but $d_{2}$ would be calculated using. $X$ or whatever is the. strike.

13. Note if the dividend yield equals the interest rate, then the square root term equals the square root of time to maturity. This solution is proven in Chapter 14..

14. Recall when the interest rate equals the dividend yield then the denominator is simply the volatility times the square root of time to maturity..

# The Greeks in the. Black-Scholes-Merton Mode!

Recall the Greeks refer to the partial derivatives of a pricing model ith respect to to the Black-Scholes-Merton model. We focus first on the call option results and then turn to put options, relying on put-call parity for a smooth transition. After incorporating. dividends, we will examine selected sensitivities of the Greeks as well as some extensions.

In Chapter 13, we derived the Black-Scholes-Merton model, as given here:

$$
\begin{array}{r l r}&{}&{c=S N(d_{1})-X e^{-r_{c}\tau}N(d_{2})}\ &{}&{d_{1}=\cfrac{\ln(S/X)+\left(r_{c}+\sigma^{2}/2\right)\tau}{\sigma\sqrt{\tau}}}\ &{}&{d_{2}=d_{1}-\sigma\sqrt{\tau}}\ &{}&{d_{i}}\ &{}&{N(d_{i})=\displaystyle\int\cfrac{1}{-\infty}\cfrac{e^{-x^{2}/2}d x,i=1,2.}{12\pi}}\end{array}
$$

We noted that this formula is the solution to the following partial differential equation,

$$
r_{c}S{\frac{\partial c}{\partial S}}+{\frac{\partial c}{\partial t}}+{\frac{1}{2}}{\frac{\partial^{2}c}{\partial S^{2}}}\sigma^{2}S^{2}=r_{c}c.
$$

The only way to be absolutely certain that the solution of a differential equation is correct is to take the derivatives of the solution and insert them into the differential equation. If the. solution is correct, the differential equation will turn into the solution equation. So, let us do that here. As is indicated in Equation (14.2), we shall need to take the first and second derivatives with respect to the asset price, which are called the delta and gamma, respectively, and the first derivative with respect to time, which is called the theta. We approximated these sensitivity measures in the binomial model. Now, we shall more formally derive them in the continuous time world..

Before starting, however, there are some interim results that will prove useful in this. process. Recall that $N(d)$ is the value of the cumulative density function, also called the. distribution function, of a standard normal random variable, d. Thus, the integrand is simply the probability density function denoted $n(d)$ . We first take the partial derivatives of $N(d_{1})$ and $N(d_{2})$ with respect to $d_{1}$ and $d_{2}$ , respectively,

$$
\frac{\partial N(d_{1})}{\partial d_{1}}=\frac{1}{\sqrt{2\pi}}e^{-d_{1}^{2}/2}=n(d_{1})
$$

and

$$
\frac{\partial N(d_{2})}{\partial d_{2}}=\frac{1}{\sqrt{2\pi}}e^{-d_{2}^{2}/2}=\frac{1}{\sqrt{2\pi}}e^{-(d_{1}-\sigma\sqrt{\tau})^{2}/2}=n(d_{2}).
$$

Further, we can establish the relationship between $n(d_{1})$ and $n(d_{2})$ . Focusing first $\mathrm{on}\Big(d_{1}-\sigma\sqrt{\tau}\Big)^{2}$ , we note

$$
\begin{array}{l}{{\left(d_{1}-\sigma\sqrt{\tau}\right)^{2}=d_{1}^{2}-2\sigma\sqrt{\tau}d_{1}+\sigma^{2}\tau}}\ {{~=d_{1}^{2}-2\sigma\sqrt{\tau}\left[\displaystyle\frac{\ln(S/X)+\left(r_{c}+\sigma^{2}/2\right)\tau}{\sigma\sqrt{\tau}}\right]+\sigma^{2}\tau}}\ {{~=d_{1}^{2}-2\ln\left(S/X e^{-r_{c}\tau}\right).}}\end{array}
$$

Substituting this result into Equation (14.4), we have either

$$
\begin{array}{l}{{n(d_{1})=\displaystyle\frac{X e^{-r\tau}n\left(d_{2}\right)}{S}~\mathrm{or}}}\ {{}}\ {{n(d_{2})=\displaystyle\frac{S n\left(d_{1}\right)}{X e^{-r\tau}}.}}\end{array}
$$

With these results, we note

$$
{\frac{S}{X e^{-r\tau}}}={\frac{n(d_{2})}{n(d_{1})}}={\frac{\frac{e^{-d_{2}^{2}/2}}{\sqrt{2\pi}}}{\frac{e^{-d_{1}^{2}/2}}{\sqrt{2\pi}}}}=e^{\left(d_{1}^{2}-d_{2}^{2}\right)/2}.
$$

Focusing on the exponent,

$$
\begin{array}{c}{{\displaystyle\frac{d_{1}^{2}-d_{2}^{2}}{2}=\frac{1}{2}\left[d_{1}^{2}-\left(d_{1}-\sigma\sqrt{\tau}\right)^{2}\right]=\frac{1}{2}\left(d_{1}^{2}-d_{1}^{2}+2d_{1}\sigma\sqrt{\tau}-\sigma^{2}\tau\right)=d_{1}\sigma\sqrt{\tau}-\frac{\sigma^{2}\tau}{2}}}\ {{\displaystyle=\left[\frac{\ln\left(\frac{S}{X}\right)+\left(r+\frac{\sigma^{2}}{2}\right)\tau}{\sigma\sqrt{T}}\right]\sigma\sqrt{\tau}-\frac{\sigma^{2}\tau}{2}=\ln\left(\frac{S}{X}\right)+r\tau.}}\end{array}
$$

Therefore,

$$
e^{\left(d_{1}^{2}-d_{2}^{2}\right)/2}=e^{\ln\left(\frac{S}{X}\right)+r\tau}=\frac{S}{X e^{-r\tau}}.
$$

We shall also need the derivatives of $d_{1}$ and $d_{2}$ with respect to. $S$

$$
\begin{array}{l}{\displaystyle\frac{\partial d_{1}}{\partial S}=\frac{\partial}{\partial S}\left(\frac{\left[\ln(S/X)+\left(r_{c}+\left(\sigma^{2}/2\right)\right)\tau\right.}{\sigma\sqrt{\tau}}\right)=\frac{1}{S\sigma\sqrt{\tau}}}\ {\displaystyle\frac{\partial d_{2}}{\partial S}=\frac{\partial\left(d_{1}-\sigma\sqrt{\tau}\right)}{\partial S}=\frac{\partial d_{1}}{\partial S}=\frac{1}{S\sigma\sqrt{\tau}}.}\end{array}
$$

We also need the derivatives of $d_{1}$ and $d_{2}$ with respect to time to expiration, $\tau$ . Recall the quotient rule from Chapter 3:

$$
{\frac{d y}{d x}}={\frac{\nu{\frac{d b}{d x}}-b{\frac{d\nu}{d x}}}{\nu^{2}}}{\mathrm{~(the~quotient~rule)}}.
$$

Note for $d_{1}$ $b=\ln(S/X)+(r_{c}+\sigma^{2}/2)\tau$ and $\nu=\sigma\sqrt{\tau}$ .Thus, $\partial b/\partial\tau=(r_{c}+\sigma^{2}/2)$ and $\partial\nu/\partial\tau=\sigma/(2\sqrt{\tau})$ . Further, we assume $\sigma>0$ . Thus, applying the quotient rule, we have

$$
\begin{array}{r l}&{\frac{\partial d_{1}}{\partial\tau}=\frac{\nu\frac{\partial\hat{\nu}}{\partial x}-b\frac{\partial\hat{\nu}}{\partial x}}{\nu^{2}}=\frac{\sigma\sqrt{\tau}\left(r_{c}+\frac{\sigma^{2}}{2}\right)-\left[\ln(S/X)+\left(r_{c}+\sigma^{2}/2\right)\tau\right]\left[\sigma/(2\sqrt{\tau})\right.}{\left.\sigma^{2}\tau}}\ &{\qquad=\frac{\left(r_{c}+\frac{\sigma^{2}}{2}\right)-\left[\ln(S/X)+\left(r_{c}+\sigma^{2}/2\right)\tau\right]\left[1/(2\tau)\right]}{\sigma\sqrt{\tau}}=\frac{\left(r_{c}+\frac{\sigma^{2}}{2}\right)}{\sigma\sqrt{\tau}}-\frac{d_{1}}{2\tau}.}\ &{\qquad\frac{\partial d_{2}}{\partial\tau}=\frac{\partial d_{1}}{\partial\tau}-\sigma\frac{\partial\sqrt{\tau}}{\partial\tau}=\frac{\left(r_{c}+\frac{\sigma^{2}}{2}\right)}{\sigma\sqrt{\tau}}-\frac{d_{1}}{2\tau}-\frac{\sigma}{2\sqrt{\tau}}}\ &{\qquad=\frac{\left(r_{c}+\frac{\sigma^{2}}{2}\right)}{\sigma\sqrt{\tau}}-\frac{d_{1}-\sigma\sqrt{\tau}}{2\tau}=\frac{\left(r_{c}+\frac{\sigma^{2}}{2}\right)}{\sigma\sqrt{\tau}}-\frac{d_{2}}{2\tau}.}\end{array}
$$

From the formula for. $d_{1}$ , we will also use the following:

$$
\begin{array}{l}{S=X e^{{d_{1}\sigma\sqrt{\tau}-\left(r+\sigma^{2}/2\right)\tau}}\mathrm{and}}\ {~}\ {X=S e^{{-d_{1}\sigma\sqrt{\tau}+\left(r+\sigma^{2}/2\right)\tau}}.}\end{array}
$$
