---
tags:
  - dividend_beta
  - one_period_framework
  - risk_adjusted_discount
  - risk_free_return
  - state_price_deflator
aliases:
  - Event-Price Deflator
  - Pricing Kernel
  - Stochastic Discount Factor
key_concepts:
  - Finite variance assumption
  - Gross rates of returns
  - Pricing equation
  - Risk-free portfolio
  - State-price deflator definition
---

# 4.2 Definitions and immediate consequences  

This section gives a formal definition of a state-price deflator. Some authors use the name stochastic discount factor, event-price deflator, or pricing kernel instead of state-price deflator..  

# 4.2.1 The one-period framework  

A state-price deflator is a random variable $\zeta$ with the properties that.  

(i) $\zeta$ has finite variance,  

(ii) $\zeta>0$ , i.e. $\zeta(\omega)>0$ for all states $\omega\in\Omega$  

(iii) the price of the $I$ basic assets are given by  

$$
P_{i}=\mathrm{E}[\zeta D_{i}],\quad i=1,2,\dots,I,
$$  

or, more compactly, $P=\mathrm{E}[\zeta D]$  

The finite variance assumptions on both the state-price deflator and the dividends ensure that the expectation $\operatorname{E}[\zeta D_{i}]$ is finite.  

We get a similar pricing equation for portfolios:  

$$
P^{\theta}=\sum_{i=1}^{I}\theta_{i}P_{i}=\sum_{i=1}^{I}\theta_{i}\operatorname{E}[\zeta D_{i}]=\operatorname{E}\left[\zeta\left(\sum_{i=1}^{I}\theta_{i}D_{i}\right)\right]=\operatorname{E}\left[\zeta D^{\theta}\right].
$$  

In terms of gross rates of returns, $R_{i}=D_{i}/P_{i}$ , a state-price deflator $\zeta$ has the property that  

$$
1=\mathrm{E}[\zeta R_{i}],\quad i=1,2,\ldots,I,
$$  

or, $\mathbf{1}=\operatorname{E}[\zeta R]$ in vector notation.  

For a risk-free portfolio with a dividend of 1, the price $P^{f}$ is  

$$
P^{f}=\operatorname{E}\left[\zeta\right]
$$  

and the risk-free gross rate of return is thus  

$$
R^{f}=\frac{1}{P^{f}}=\frac{1}{\mathrm{E}\left[\zeta\right]}.
$$  

Exploiting the definition of a covariance, the pricing condition (4.1) can be rewritten as  

$$
P_{i}=\operatorname{E}[\zeta]\operatorname{E}[D_{i}]+\operatorname{Cov}[D_{i},\zeta].
$$  

A dividend of a given size is valued more highly in a state for which the state-price deflator is high than in a state where the deflator is low. If a risk-free asset is traded, we can rewrite this as.  

$$
P_{i}=\frac{\mathrm{E}[D_{i}]+R^{f}\mathrm{Cov}[D_{i},\zeta]}{R^{f}},
$$  

i.e. the value of a future dividend is given by the expected dividend adjusted by a covariance term,. discounted at the risk-free rate. If the dividend is positively [negatively] covarying with the state-. price deflator, the expected dividend is adjusted downwards [upwards]. Defining the dividend-beta of asset $i$ with respect to the state-price deflator as.  

$$
\beta[D_{i},\zeta]=\frac{\mathrm{Cov}[D_{i},\zeta]}{\mathrm{Var}[\zeta]}
$$  

and $\eta=-\mathrm{Var}[\zeta]/\mathrm{E}[\zeta]<0$ , we can rewrite the above pricing equation as  

$$
P_{i}=\frac{\mathrm{E}[D_{i}]-\beta[D_{i},\zeta]\eta}{R^{f}}.
$$  

Some basic finance textbooks suggest that a future uncertain dividend can be valued by taking the expected dividend and discount it by a discount rate reflecting the risk of the dividend. For  

asset $i$ , this discount rate $\hat{R}_{i}$ is implicitly defined by $P_{i}=\mathrm{E}[D_{i}]/\hat{R}_{i}$ and combining this with the above equations, we must have  

$$
{\hat{R}}_{i}={\frac{R^{f}\operatorname{E}[D_{i}]}{\operatorname{E}[D_{i}]-\beta[D_{i},\zeta]\eta}}=R^{f}{\frac{1}{1-{\frac{\beta[D_{i},\zeta]\eta}{\operatorname{E}[D_{i}]}}}}.
$$  

The risk-adjusted discount rate does not depend on the scale of the dividend in the sense that the risk-adjusted discount rate for a dividend of $k D_{i}$ for any constant $k$ is the same as for a dividend of. $D_{i}$ . Note that the risk-adjusted discount rate will be smaller than $R^{f}$ if the dividend. is negatively covarying with the stare-price deflator. In fact, if $\mathrm{E}[D_{i}]<\beta[D_{i},\zeta]\eta$ , the risk-adjusted. gross discount rate will be negative! While this possibility is rarely realized in textbooks, it is not really surprising. Some assets or investments will have a negative expected future dividend but still a positive value today. This is the case for most insurance contracts. The lesson here is to be careful if you want to value assets by discounting expected dividends by risk-adjusted discount rates.  

For the gross rate of return, $R_{i}=D_{i}/P_{i}$ , we get  

$$
\boldsymbol{1}=\mathrm{E}[\boldsymbol{\zeta}]\mathrm{E}[R_{i}]+\mathrm{Cov}[R_{i},\boldsymbol{\zeta}]
$$  

implying that  

$$
\operatorname{E}[R_{i}]={\frac{1}{\operatorname{E}[\zeta]}}-{\frac{\operatorname{Cov}[R_{i},\zeta]}{\operatorname{E}[\zeta]}}.
$$  

If a risk-free asset is available, the above equation specializes to  

$$
\operatorname{E}[R_{i}]-R^{f}=-{\frac{\operatorname{Cov}[R_{i},\zeta]}{\operatorname{E}[\zeta]}},
$$  

which again can be rewritten as  

$$
\operatorname{E}[R_{i}]-R^{f}={\frac{\operatorname{Cov}[R_{i},\zeta]}{\operatorname{Var}[\zeta]}}\left(-{\frac{\operatorname{Var}[\zeta]}{\operatorname{E}[\zeta]}}\right)=\beta[R_{i},\zeta]\eta,
$$  

where the return-beta $\beta[R_{i},\zeta]$ is defined as $\mathrm{Cov}[R_{i},\zeta]/\mathrm{Var}[\zeta]$ corresponding to the definition of the market-beta of an asset in the traditional CAPM. An asset with a positive [negative] returnbeta with respect to the state-price deflator will have an expected return smaller [larger] than the risk-free return. Of course, we can also write the covariance as the product of the correlation and the standard deviations so that  

$$
\mathrm{E}[R_{i}]-R^{f}=-\rho[R_{i},\zeta]\sigma[R_{i}]\frac{\sigma[\zeta]}{\mathrm{E}[\zeta]},
$$  

and the Sharpe ratio of asset $i$ is  

$$
{\frac{\operatorname{E}[R_{i}]-R^{f}}{\sigma[R_{i}]}}=-\rho[R_{i},\zeta]{\frac{\sigma[\zeta]}{\operatorname{E}[\zeta]}}.
$$  

In particular, we can see that the maximal Sharpe ratio is the ratio $\sigma[\zeta]/\operatorname{E}[\zeta]$  

The expressions involving expected returns and return-betas above are not directly useful if. you want to value a future dividend. For that purpose the equations with expected dividends. and dividend-betas are superior. On the other hand the return-expressions are better for empirical studies, where you have a historical record of observations of returns and, for example, of a potential. state-price deflator.  

Example 4.1 Let $\zeta$ be a state-price deflator and consider a dividend given by  

$$
D_{i}=a+b\zeta+\varepsilon,
$$  

where $a,b$ are constants, and where $\varepsilon$ is a random variable with mean zero and $\mathrm{Cov}[\varepsilon,\zeta]=0$ .What is the price of this dividend? We can use the original pricing condition to get  

$$
\begin{array}{r}{\mathrm{\Sigma}_{i}=\operatorname{E}[D_{i}\zeta]=\operatorname{E}\left[\left(a+b\zeta+\varepsilon\right)\zeta\right]=a\operatorname{E}[\zeta]+b\operatorname{E}[\zeta^{2}],}\end{array}
$$  

using $\operatorname{E}[\varepsilon\zeta]=\operatorname{Cov}[\varepsilon,\zeta]+\operatorname{E}[\varepsilon]\operatorname{E}[\zeta]=0+0=0$ . Alternatively, we can compute  

$$
\begin{array}{r}{\operatorname{E}[D_{i}]=a+b\operatorname{E}[\zeta],\qquad\operatorname{Cov}[D_{i},\zeta]=b\operatorname{Var}[\zeta],}\end{array}
$$  

and use (4.5) to get  

$$
\begin{array}{c}{P_{i}=\operatorname{E}[\zeta]\left(a+b\operatorname{E}[\zeta]\right)+b\operatorname{Var}[\zeta]}\ {=a\operatorname{E}[\zeta]+b\operatorname{E}[\zeta^{2}]}\end{array}
$$  

using the identity $\mathrm{Var}[\zeta]=\mathrm{E}[\zeta^{2}]-(\mathrm{E}[\zeta])^{2}$  

# Lognormal state-price deflator and return  

In many specific models the state-price deflator is assumed to have a lognormal distribution. It follows from Appendix B that.  

$$
\begin{array}{r}{\operatorname{E}[\zeta]=\operatorname{E}\left[e^{\ln\zeta}\right]=e^{\operatorname{E}[\ln\zeta]+\frac{1}{2}\operatorname{Var}[\ln\zeta]}.}\end{array}
$$  

In particular, if a risk-free asset exists, the continuously compounded risk-free rate of return is  

$$
r^{f}=\ln R^{f}=-\ln\operatorname{E}[\zeta]=-\operatorname{E}[\ln\zeta]-{\frac{1}{2}}\operatorname{Var}[\ln\zeta].
$$  

For a risky asset with a gross return $R_{i}$ so that the state-price deflator $\zeta$ and the gross return $R_{i}$ are jointly lognormally distributed, the product $\zeta R_{i}$ will also be lognormally distributed. Hence, we find  

$$
1=\operatorname{E}\left[\zeta R_{i}\right]=\operatorname{E}\left[e^{\ln\zeta+\ln R_{i}}\right]=\exp\left\{\operatorname{E}[\ln\zeta+\ln R_{i}]+{\frac{1}{2}}\operatorname{Var}\left[\ln\zeta+\ln R_{i}\right]\right\},
$$  

and thus  

$$
=\operatorname{E}[\ln\zeta+\ln R_{i}]+{\frac{1}{2}}\operatorname{Var}\left[\ln\zeta+\ln R_{i}\right]=\operatorname{E}[\ln\zeta]+{\frac{1}{2}}\operatorname{Var}\left[\ln\zeta\right]+\operatorname{E}[\ln R_{i}]+{\frac{1}{2}}\operatorname{Var}\left[\ln R_{i}\right]+\operatorname{Cov}\left[\ln\zeta,\ln R_{i}\right]
$$  

If we let $r_{i}=\ln R_{i}$ denote the continuously compounded rate of return on asset $i$ and apply (4.15), we obtain  

$$
\operatorname{E}[r_{i}]-r^{f}=-\operatorname{Cov}[\ln\zeta,r_{i}]-{\frac{1}{2}}\operatorname{Var}[r_{i}].
$$  

# Excess returns  

Some empirical tests of asset pricing models focus on excess returns, where returns on all assets are measured relative to the return on a fixed benchmark asset or portfolio. Let. $R$ be the return  

on the benchmark. The excess return on asset $i$ is then $R_{i}^{e}\equiv R_{i}-R$ . Since the above equations.   
hold for both asset. $i$ and the benchmark, we get that.  

$$
\mathrm{E}[\zeta R_{i}^{e}]=0
$$  

and  

$$
\mathrm{E}[R_{i}^{e}]=-\frac{\mathrm{Cov}[R_{i}^{e},\zeta]}{\mathrm{E}[\zeta]}=\beta[R_{i}^{e},\zeta]\eta,
$$  

where $\beta[R_{i}^{e},\zeta]=\beta[R_{i},\zeta]-\beta[R,\zeta]$  

# State-price vectors with a finite state space  

If the state space is finite, $\Omega=\{1,2,\dots,S\}$ , we can alternatively represent a general pricing rule by a state-price vector, which is an $S$ -dimensional vector $\psi=(\psi_{1},\ldots,\psi_{S})^{\intercal}$ with the properties  

(i) $\psi>0$ , i.e. $\psi_{\omega}>0$ for all $\omega=1,2,\ldots,S$  

(ii) the price of the $I$ assets are given by  

$$
P_{i}=\psi\cdot D_{i}=\sum_{\omega=1}^{S}\psi_{\omega}D_{i\omega},\quad i=1,2,\ldots,I,
$$  

or, more compactly,. $P=\underline{{\underline{{D}}}}\psi$ , where $\underline{{\underline{{\boldsymbol{D}}}}}$ is the dividend matrix of all the basic assets.  

Suppose we can construct an Arrow-Debreu asset for state $\omega$ , i.e. a portfolio paying $^{1}$ in state $\omega$ and nothing in all other states. The price of this portfolio will be equal to $\psi_{\omega}$ , the "state price for state $\omega$ The price of a risk-free dividend of $^{1}$ .9 $\begin{array}{r}{P^{f}\equiv\psi\cdot{\bf1}=\sum_{\omega=1}^{S}\psi_{\omega}}\end{array}$ So that the gross risk-free rate of return is  

$$
R^{f}={\frac{1}{\sum_{\omega=1}^{S}\psi_{\omega}}}={\frac{1}{\psi\cdot{\bf1}}}.
$$  

There is a one-to-one correspondence between state-price vectors and state-price deflators. With a finite state space a state-price deflator is equivalent to a vector. $\boldsymbol{\zeta}=(\zeta_{1},\zeta_{2},\ldots,\zeta_{S})^{\intercal}$ and we can rewrite (4.1) as  

$$
P_{i}=\sum_{\omega=1}^{S}p_{\omega}\zeta_{\omega}D_{i\omega},\quad i=1,2,\ldots,I.
$$  

We can then define a state-price vector $\psi$ by  

$$
\psi_{\omega}=\zeta_{\omega}p_{\omega}.
$$  

Conversely, given a state-price vector this equation defines a state-price deflator. With infinitely many states we cannot meaningfully define state-price vectors but we can still define state-price deflators in terms of random variables.  

Example 4.2 Consider the same market as in Example 3.1. Suppose there is a state-price vector $\psi=(0.3,0.2,0.3)^{\top}$ . Then we can compute the prices of the four assets as. $P=\underline{{\underline{{D}}}}\underline{{\psi}}$ , i.e.  

$$
{\left(\begin{array}{l}{P_{1}}\ {P_{2}}\ {P_{3}}\ {P_{4}}\end{array}\right)}={\left(\begin{array}{l l l}{1}&{1}&{1}\ {0}&{1}&{2}\ {4}&{0}&{1}\ {9}&{0}&{1}\end{array}\right)}{\left(\begin{array}{l}{0.3}\ {0.2}\ {0.3}\end{array}\right)}={\left(\begin{array}{l}{0.8}\ {0.8}\ {1.5}\ {3}\end{array}\right)}.
$$  

In particular, the gross risk-free rate of return is $1/(0.3+0.2+0.3)=1.25$ corresponding to a $25\%$ risk-free net rate of return.  

If the state probabilities are 0.5, 0.25, and 0.25, respectively, the state-price deflator corresponding to the state-price vector is given by.  

$$
\zeta_{1}=\frac{0.3}{0.5}=0.6,\quad\zeta_{2}=\frac{0.2}{0.25}=0.8,\quad\zeta_{3}=\frac{0.3}{0.25}=1.2.
$$  

# 4.2.2 The discrete-time framework  

In the discrete-time multi-period framework with time set $\mathcal{T}=\{0,1,2,...,T\}$ a state-price deflator is an adapted stochastic process $\zeta=(\zeta_{t})_{t\in\mathcal{T}}$ such that  

(i) $\zeta_{0}=1$   
(ii) $\zeta_{t}>0$ for all $t=1,2,\ldots,T$   
(iii) for any. $t\in\mathcal{T}$ $\zeta_{t}$ has finite variance,   
(iv) for any basic asset $i=1,\dots,I$ and any $t\in\mathcal{T}$ , the price satisfies.  

$$
P_{i t}=\mathrm{E}_{t}\left[\sum_{s=t+1}^{T}D_{i s}\frac{\zeta_{s}}{\zeta_{t}}\right].
$$  

The condition (i) is just a normalization. The condition (ii) is purely technical and will ensure that some relevant expectations exist. Condition (iv) gives the price at time. $t$ in terms of all the future dividends and the state-price deflator. This condition will also hold for all trading strategies..  

The pricing condition implies a link between the price of an asset at two different points in time, say $t<t^{\prime}$ . From (4.20) we have  

$$
P_{i t^{\prime}}=\mathrm{E}_{t^{\prime}}\left[\sum_{s=t^{\prime}+1}^{T}D_{i s}\frac{\zeta_{s}}{\zeta_{t^{\prime}}}\right].
$$  

We can now rewrite the price $P_{i t}$ as follows:  

$$
\begin{array}{r l}&{P_{t i}=\mathbb{E}_{t}\left[\displaystyle\sum_{s=t+1}^{T}D_{s i}\frac{S_{e}}{\zeta_{d}}\right]}\ &{\quad=\mathbb{E}_{t}\left[\displaystyle\sum_{s=t+1}^{r}D_{s i}\frac{S_{e}}{\zeta_{d}}+\displaystyle\sum_{s=t+1}^{T}D_{s i}\frac{S_{e}}{\zeta_{d}}\right]}\ &{\quad=\mathbb{E}_{t}\left[\displaystyle\sum_{s=t+1}^{r}D_{s i}\frac{S_{e}}{\zeta_{d}}+\displaystyle\frac{\zeta_{v}}{\zeta_{d}}\displaystyle\sum_{s=t+1}^{T}D_{i}\frac{S_{e}}{\zeta_{d}}\right]}\ &{\quad=\mathbb{E}_{t}\left[\displaystyle\sum_{s=t+1}^{r}D_{s i}\frac{S_{e}}{\zeta_{d}}+\displaystyle\frac{\zeta_{v}}{\zeta_{d}}\mathbb{E}_{t}\left[\displaystyle\sum_{s=t+1}^{T}D_{i}\frac{S_{e}}{\zeta_{d}}\right]\right]}\ &{\quad=\mathbb{E}_{t}\left[\displaystyle\sum_{s=t+1}^{r}D_{s i}\frac{S_{e}}{\zeta_{d}}+\displaystyle\frac{\zeta_{v}}{\zeta_{d}}\mathbb{E}_{t}\left[\displaystyle\sum_{s=t+1}^{T}D_{i}\frac{S_{e}}{\zeta_{d}}\right]\right]}\ &{\quad=\mathbb{E}_{t}\left[\displaystyle\sum_{s=t+1}^{r}D_{s i}\frac{S_{e}}{\zeta_{d}}+P_{w}\frac{\zeta_{v}}{\zeta_{d}}\right].}\end{array}
$$  

Here the fourth equality follows from the Law of Iterated Expectations, Theorem 2.1. Conversely, Equation (4.21) implies Equation (4.20).  

A particularly simple version of (4.21) occurs for $t^{\prime}=t+1$  

$$
P_{i t}=\mathrm{E}_{t}\left[\frac{\zeta_{t+1}}{\zeta_{t}}\left(P_{i,t+1}+D_{i,t+1}\right)\right],
$$  

or in terms of the gross rate of return $R_{i,t+1}=(P_{i,t+1}+D_{i,t+1})/P_{i t}$  

$$
1=\mathrm{E}_{t}\left[\frac{\zeta_{t+1}}{\zeta_{t}}R_{i,t+1}\right].
$$  

These equations show that the ratio $\zeta_{t+1}/\zeta_{t}$ acts as a one-period state-price deflator between time $t$ and $t+1$ in the sense of the definition in the one-period framework, except that the price at the end of the period (zero in the one-period case) is added to the dividend. Of course, given the stateprice deflator process $\zeta=\left(\zeta_{t}\right)$ we know the state-price deflators $\zeta_{t+1}/\zeta_{t}$ for each of the subperiods. (Note that these will depend on the realized value $\zeta_{t}$ which is part of the information available at time $t$ .) Conversely, a sequence of "one-period state-price deflators" $\zeta_{t+1}/\zeta_{t}$ and the normalization $\zeta_{0}=1$ define the entire state-price deflator process.  

If an asset provides a risk-free gross rate of return $R_{t}^{f}$ over the period between $t$ and $t+1$ that return will be known at time $t$ and we get that  

$$
1=\operatorname{E}_{t}\left[{\frac{\zeta_{t+1}}{\zeta_{t}}}R_{t}^{f}\right]=R_{t}^{f}\operatorname{E}_{t}\left[{\frac{\zeta_{t+1}}{\zeta_{t}}}\right]
$$  

and hence  

$$
R_{t}^{f}=\left(\mathrm{E}_{t}\left[\frac{\zeta_{t+1}}{\zeta_{t}}\right]\right)^{-1}.
$$  

Similar to the one-period case, the above equations lead to an expression for the expected excess return of an asset over a single period:.  

where  

$$
\mathrm{E}_{t}[R_{i,t+1}]-R_{t}^{f}=-\frac{\mathrm{Cov}_{t}\left[R_{i,t+1},\frac{\zeta_{t+1}}{\zeta_{t}}\right]}{\mathrm{E}_{t}\left[\frac{\zeta_{t+1}}{\zeta_{t}}\right]}=\beta_{t}\left[R_{i,t+1},\frac{\zeta_{t+1}}{\zeta_{t}}\right]\eta_{t},
$$  

$$
\beta_{t}\left[R_{i,t+1},\frac{\zeta_{t+1}}{\zeta_{t}}\right]=\frac{\mathrm{Cov}_{t}\left[R_{i,t+1},\frac{\zeta_{t+1}}{\zeta_{t}}\right]}{\mathrm{Var}_{t}\left[\frac{\zeta_{t+1}}{\zeta_{t}}\right]},\quad\eta_{t}=-\frac{\mathrm{Var}_{t}\left[\frac{\zeta_{t+1}}{\zeta_{t}}\right]}{\mathrm{E}_{t}\left[\frac{\zeta_{t+1}}{\zeta_{t}}\right]}.
$$  

The same relation holds for net rates of return. Just substitute $R_{i,t+1}=1+r_{i,t+1}$ and $R_{t}^{f}=$ $1+r_{t}^{f}$ on the left-hand side and observe that the ones cancel. On the right-hand side use that $\mathrm{ov}_{t}[R_{i,t+1},\boldsymbol{x}]=\mathrm{Cov}_{t}[1+r_{i,t+1},\boldsymbol{x}]=\mathrm{Cov}_{t}[r_{i,t+1},\boldsymbol{x}$ for any random variable $x$ . Therefore we can work with gross or net returns as we like in such expressions. The conditional Sharpe ratio of asset $i$ becomes  

$$
\frac{\mathrm{E}_{t}[R_{i,t+1}]-R_{t}^{f}}{\sigma_{t}[R_{i,t+1}]}=-\rho_{t}\left[R_{i,t+1},\frac{\zeta_{t+1}}{\zeta_{t}}\right]\frac{\sigma_{t}\left[\frac{\zeta_{t+1}}{\zeta_{t}}\right]}{\mathrm{E}_{t}\left[\frac{\zeta_{t+1}}{\zeta_{t}}\right]}.
$$  

The maximal conditional Sharpe ratio is $\begin{array}{r}{\sigma_{t}\left[\frac{\zeta_{t+1}}{\zeta_{t}}\right]/\operatorname{E}_{t}\left[\frac{\zeta_{t+1}}{\zeta_{t}}\right]}\end{array}$ . These expressions are useful for empirical purposes.  

In a situation where the next-period state-price deflator $\zeta_{t+1}/\zeta_{t}$ and the next-period gross return $R_{i,t+1}=e^{r_{i,t+1}}$ on a risky asset are jointly lognormally distributed conditional on time $t$ information, it follows from our one-period analysis that the expected excess continuously compounded rate of return is  

$$
\mathrm{E}_{t}[r_{i,t+1}]-r_{t}^{f}=-\operatorname{Cov}_{t}\left[\ln\left(\frac{\zeta_{t+1}}{\zeta_{t}}\right),r_{i,t+1}\right]-\frac{1}{2}\mathrm{Var}_{t}[r_{i,t+1}],
$$  

where  

$$
r_{t}^{f}=\ln R_{t}^{f}=-\ln\operatorname{E}_{t}\left[\left({\frac{\zeta_{t+1}}{\zeta_{t}}}\right)\right]=-\operatorname{E}_{t}\left[\ln\left({\frac{\zeta_{t+1}}{\zeta_{t}}}\right)\right]-{\frac{1}{2}}\operatorname{Var}_{t}\left[\ln\left({\frac{\zeta_{t+1}}{\zeta_{t}}}\right)\right]
$$  

is the continuously compounded risk-free rate of return over the next period.  

For the valuation of a future dividend stream we have to apply (4.20). Applying the covariance definition once again, we can rewrite the price as  

$$
P_{i t}=\sum_{s=t+1}^{T}\left(\operatorname{E}_{t}[D_{i s}]\operatorname{E}_{t}\left[\frac{\zeta_{s}}{\zeta_{t}}\right]+\operatorname{Cov}_{t}\left[D_{i s},\frac{\zeta_{s}}{\zeta_{t}}\right]\right).
$$  

By definition of a state-price deflator, a zero-coupon bond maturing at time $s$ with a face value of 1 will have a time. $t$ price of  

$$
B_{t}^{s}=\mathrm{E}_{t}\left[\frac{\zeta_{s}}{\zeta_{t}}\right].
$$  

Define the corresponding (annualized) yield $\hat{y}_{t}^{s}$ by  

$$
B_{t}^{s}=\frac{1}{(1+\hat{y}_{t}^{s})^{s-t}}\quad\Leftrightarrow\quad\hat{y}_{t}^{s}=(B_{t}^{s})^{-1/(s-t)}-1.
$$  

Note that this is a risk-free rate of return between time $t$ and time $s$ . Now we can rewrite the.   
above price expression as.  

$$
\begin{array}{l}{{P_{i t}=\displaystyle\sum_{s=t+1}^{T}B_{t}^{s}\left(\mathrm{E}_{t}[D_{i s}]+\frac{\mathrm{Cov}_{t}\left[D_{i s},\frac{\zeta_{s}}{\zeta_{t}}\right]}{B_{t}^{s}}\right)}}\ {{=\displaystyle\sum_{s=t+1}^{T}\frac{\mathrm{E}_{t}[D_{i s}]+\frac{\mathrm{Cov}_{t}\left[D_{i s},\frac{\zeta_{s}}{\zeta_{t}}\right]}{\mathrm{E}_{t}\left[\frac{\zeta_{s}}{\zeta_{t}}\right]}}{\left(1+\frac{\hat{y}_{t}^{s}}{{{\cal J}}_{t}^{s}}\right)^{s-t}}.}}\end{array}
$$  

Each dividend is valued by discounting an appropriately risk-adjusted expected dividend by the risk-free return over the period. This generalizes the result in the one-period framework.  

Some authors formulate the important pricing condition (iv) as follows: for all basic assets $i=1,\dots,I$ the state-price deflated gains process $G_{i}^{\zeta}=(G_{i t}^{\zeta})_{t\in\mathcal{T}}$ defined by  

$$
G_{i t}^{\zeta}=\sum_{s=1}^{t}D_{i s}\zeta_{s}+P_{i t}\zeta_{t}
$$  

is a martingale. This means that for $t<t^{\prime}$ $G_{i t}^{\zeta}=\mathrm{E}[G_{i t^{\prime}}^{\zeta}]$ , i.e.  

$$
\sum_{s=1}^{t}D_{i s}\zeta_{s}+P_{i t}\zeta_{t}=\mathrm{E}_{t}\left[\sum_{s=1}^{t^{\prime}}D_{i s}\zeta_{s}+P_{i t^{\prime}}\zeta_{t^{\prime}}\right].
$$  

Subtracting the sum on the left-hand side and dividing by $\zeta_{t}$ yield (4.21).  

# 4.2.3 The continuous-time framework  

Similar to the discrete-time framework we define a state-price deflator in the continuous-time framework as an adapted stochastic process $\zeta=\left(\zeta_{t}\right)$ with  

(i) $\zeta_{0}=1$   
(ii) $\zeta_{t}>0$ for all $t\in[0,T]$   
(iii) for each $t$ $\zeta_{t}$ has finite variance,   
(iv) for any basic asset $i=1,\dots,I$ and any $t\in[0,T)$ , the price satisfies  

$$
P_{i t}=\mathrm{E}_{t}\left[\int_{t}^{T}\delta_{i s}P_{i s}\frac{\zeta_{s}}{\zeta_{t}}d s+D_{i T}\frac{\zeta_{T}}{\zeta_{t}}\right].
$$  

Under technical conditions, Equation (4.33) will also hold for all trading strategies. As in the discrete-time case the pricing equation (4.33) implies that for any $t<t^{\prime}<T$  

$$
P_{i t}=\mathrm{E}_{t}\left[\int_{t}^{t^{\prime}}\delta_{i s}P_{i s}\frac{\zeta_{s}}{\zeta_{t}}d s+P_{i t^{\prime}}\frac{\zeta_{t^{\prime}}}{\zeta_{t}}\right].
$$  

Again, the condition (iv) can be reformulated as follows: for all basic assets $i=1,\ldots,I$ the state-price deflated gains process $G_{i}^{\zeta}=(G_{i t}^{\zeta})_{t\in\mathbb{T}}$ defined by  

$$
G_{i t}^{\zeta}=\left\{\begin{array}{l l}{\int_{0}^{t}\delta_{i s}P_{i s}\zeta_{s}d s+P_{i t}\zeta_{t}}&{\mathrm{~for~}t<T,}\ {\int_{0}^{T}\delta_{i s}P_{i s}\zeta_{s}d s+D_{i T}\zeta_{T}}&{\mathrm{~for~}t=T}\end{array}\right.
$$  

is a martingale.  

If we invest in one unit of asset. $i$ at time $t$ and keep reinvesting the continuously paid dividends in the asset, we will end up at time. $T$ with $\exp\{\int_{t}^{T}\delta_{i u}d u\}$ units of the asset, cf. the argument in. Section 3.2.3. Therefore, we have the following relation:  

$$
P_{i t}=\mathrm{E}_{t}\left[e^{\int_{t}^{T}\delta_{i u}d u}D_{i T}\frac{\zeta_{T}}{\zeta_{t}}\right].
$$  

As in the discrete-time case we can derive information about the short-term risk-free rate of return and the expected returns on the risky assets from the state-price deflator. First we do this informally by considering a discrete-time approximation with period length. $\Delta t$ and let $\Delta t\rightarrow0$ at some point. In such an approximate model the risk-free one-period gross rate of return satisfies  

$$
\frac{1}{R_{t}^{f}}=\mathrm{E}_{t}\left[\frac{\zeta_{t+\Delta t}}{\zeta_{t}}\right],
$$  

according to (4.25). In terms of the annualized continuously compounded one-period risk-free rate $\boldsymbol{r}_{t}^{f}$ , the left-hand side is given by $\exp\{-r_{t}^{f}\Delta t\}\approx1-r_{t}^{f}\Delta t$ . Subtracting one on both sides of the equation and changing signs, we get  

$$
r_{t}^{f}\Delta t=-\mathrm{E}_{t}\left[\frac{\zeta_{t+\Delta t}-\zeta_{t}}{\zeta_{t}}\right].
$$  

Dividing by $\Delta t$ and letting $\Delta t\rightarrow0$ we get  

$$
r_{t}^{f}=-\operatorname*{lim}_{\Delta t\rightarrow0}\frac{1}{\Delta t}\operatorname{E}_{t}\left[\frac{\zeta_{t+\Delta t}-\zeta_{t}}{\zeta_{t}}\right]=-\frac{1}{d t}\operatorname{E}_{t}\left[\frac{d\zeta_{t}}{\zeta_{t}}\right].
$$  

The left-hand side is the continuously compounded short-term risk-free interest rate. The righthand side is minus the relative drift of the state-price deflator.  

To obtain an expression for the current expected return on a risky asset start with the equivalent of (4.23) in the approximating discrete-time model, i.e.  

$$
\mathrm{E}_{t}\left[\frac{\zeta_{t+\Delta}}{\zeta_{t}}R_{i,t+\Delta{t}}\right]=1,
$$  

which implies that  

$$
\mathrm{E}_{t}\left[R_{i,t+\Delta t}\right]\mathrm{E}_{t}\left[\frac{\zeta_{t+\Delta}}{\zeta_{t}}\right]-1=-\mathrm{Cov}_{t}\left[R_{i,t+\Delta t},\frac{\zeta_{t+\Delta}}{\zeta_{t}}\right].
$$  

For small $\Delta t$ , we have  

$$
\begin{array}{r}{\begin{array}{c}{\mathrm{E}_{t}\left[R_{i,t+\Delta t}\right]\approx e^{(\delta_{i t}+\mu_{i t})\Delta t},}\ {\mathrm{E}_{t}\left[\frac{\zeta_{t+\Delta t}}{\zeta_{t}}\right]\approx e^{-r_{t}^{f}\Delta t},}\ {\mathrm{Cov}_{t}\left[R_{i,t+\Delta t},\frac{\zeta_{t+\Delta}}{\zeta_{t}}\right]\approx\mathrm{Cov}_{t}\left[\frac{P_{i,t+\Delta t}}{P_{i t}},\frac{\zeta_{t+\Delta t}}{\zeta_{t}}\right]=\mathrm{Cov}_{t}\left[\frac{P_{i,t+\Delta t}-P_{i t}}{P_{i t}},\frac{\zeta_{t+\Delta t}-\zeta_{t}}{\zeta_{t}}\right].}\end{array}}\end{array}
$$  

If we substitute these expressions into the previous equation, use $e^{x}\approx1+x$ on the left-hand side,. divide by $\Delta t$ , and let $\Delta t\rightarrow0$ we arrive at  

$$
\mu_{i t}+\delta_{i t}-r_{t}^{f}=-\operatorname*{lim}_{\Delta t\rightarrow0}\frac{1}{\Delta t}\operatorname{Cov}_{t}\left[\frac{P_{i,t+\Delta t}-P_{i t}}{P_{i t}},\frac{\zeta_{t+\Delta t}-\zeta_{t}}{\zeta_{t}}\right]=-\frac{1}{d t}\operatorname{Cov}_{t}\left[\frac{d P_{i t}}{P_{i t}},\frac{d\zeta_{t}}{\zeta_{t}}\right].
$$  

The left-hand side is the expected excess rate of return over the next instant. The right-hand side is the current rate of covariance between the return on the asset and the relative change of the state-price deflator.  

Now let us give a more rigorous treatment. Write the dynamics of a state-price deflator as  

$$
d\zeta_{t}=-\zeta_{t}\left[m_{t}d t+\lambda_{t}^{\top}d z_{t}\right]
$$  

for some relative drift $m$ and some "sensitivity" vector $\lambda$ .First focus on the risk-free asset. By the pricing condition in the definition of a state-price defator, the process $G_{f}^{\zeta}$ defined by $\begin{array}{r}{G_{f t}^{\zeta}=\zeta_{t}\exp\{\int_{0}^{t}r_{u}^{f}d u\}}\end{array}$ has to be a martingale, i.e. have a zero drift. By Ito's Lemma,  

$$
d G_{f t}^{\zeta}=G_{f t}^{\zeta}\left[\left(-m_{t}+r_{t}^{f}\right)d t-\lambda_{t}^{\top}d z_{t}\right]
$$  

so we conclude that $m_{t}=r_{t}^{f}$ , i.e. the relative drift of a state-price deflator is equal to the negative of the continuously compounded short-term risk-free interest rate.  

Next, for any risky asset. $i$ the process $G_{i}^{\zeta}$ defined by (4.35) must be a martingale. From Ito's Lemma and the dynamics of. $P_{i}$ and $\zeta$ given in (3.3) and (4.38), we get  

$$
\begin{array}{r l}&{d G_{i t}^{\zeta}=\delta_{i t}P_{i t}\zeta_{t}d t+\zeta_{t}d P_{i t}+P_{i t}d\zeta_{t}+(d\zeta_{t})(d P_{i t})}\ &{\qquad=P_{i t}\zeta_{t}\left[\left(\mu_{i t}+\delta_{i t}-m_{t}-\sigma_{i t}^{\top}\lambda_{t}\right)d t+\left(\lambda_{t}+\sigma_{i t}\right)^{\top}d z_{t}\right].}\end{array}
$$  

With a risk-free asset, we know that $m_{t}=r_{t}^{f}$ , so setting the drift equal to zero, we conclude that the equation  

$$
\mu_{i t}+\delta_{i t}-r_{t}^{f}=\sigma_{i t}^{\top}\lambda_{t}
$$  

must hold for any asset $i$ . This is equivalent to (4.37). In compact form, the condition on $\lambda$ can be written  

$$
\mu_{t}+\delta_{t}-r_{t}^{f}{\bf1}=\underline{{\underline{{\sigma}}}}_{t}\lambda_{t}.
$$  

A (nice) process $\lambda=\left(\lambda_{t}\right)$ satisfying this equation is called a market price of risk. If the price of the $i$ 'th asset is only sensitive to the $j$ 'th exogenous shock, Equation (4.39) reduces to  

$$
\mu_{i t}+\delta_{i t}-r_{t}^{f}=\sigma_{i j t}\lambda_{j t},
$$  

implying that  

$$
\lambda_{j t}=\frac{\mu_{i t}+\delta_{i t}-r_{t}^{f}}{\sigma_{i j t}}.
$$  

Therefore, $\lambda_{j t}$ is the compensation in terms of excess expected return per unit of risk stemming. from the $j^{;}$ th exogenous shock. This explains the name market price of risk. Summing up, the dynamics of a state-price deflator is of the form.  

$$
\begin{array}{r}{d\zeta_{t}=-\zeta_{t}\left[r_{t}^{f}d t+\lambda_{t}^{\top}d z_{t}\right],}\end{array}
$$  

where $\lambda$ is a market price of risk. This implies that  

$$
\zeta_{s}=\zeta_{t}\exp\left\{-\int_{t}^{s}r_{u}^{f}d u-\frac{1}{2}\int_{t}^{s}\|\lambda_{u}\|^{2}d u-\int_{t}^{s}\lambda_{u}^{\top}d z_{u}\right\}
$$  

for any $s>t$  

If we know or specify the dynamics of the state-price deflator and the dividend stream from an asset, we can in principle price the asset using (4.33). However, only in special cases is it possible to compute the price in closed form. See examples in Section 4.4. In other cases one can use Monte Carlo simulation to approximate the relevant expectation.  
