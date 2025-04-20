---
tags:
  - continuous_time
  - discrete_time_economy
  - linear_factor_model
  - mean_variance
  - state_price_deflator
aliases:
  - Exercise 9.1
  - Exercise 9.2
  - Exercise 9.3
  - Exercise 9.4
key_concepts:
  - continuous-time framework
  - discrete-time economy
  - linear factor model
  - market price of risk
  - mean-variance frontier
  - state-price deflator
---

# 9.8 Exercises  

EXERCISE 9.1 Consider a discrete-time economy with a one-dimensional conditional pricing factor $x=\left(x_{t}\right)$ so that, for some adapted processes $\alpha=\left(\alpha_{t}\right)$ and some $\eta=\left(\eta_{t}\right)$  

$$
\mathrm{E}_{t}[R_{i,t+1}]=\alpha_{t}+\beta_{t}[R_{i,t+1},\boldsymbol{x}_{t+1}]\eta_{t},
$$  

for all assets $i$ and all $t=0,1,\ldots,T-1$  

(a) Show that  

$$
\frac{\zeta_{t+1}}{\zeta_{t}}=\frac{1}{\alpha_{t}}\left(1-\frac{x_{t+1}-\mathrm{E}_{t}[x_{t+1}]}{\mathrm{Var}_{t}[x_{t+1}]}\eta_{t}\right)
$$  

satisfies the pricing condition for a state-price deflator, i.e.  

$$
\mathrm{E}_{t}\left[\frac{\zeta_{t+1}}{\zeta_{t}}R_{i,t+1}\right]=1
$$  

for all assets $i$  

(b) Show that $\zeta_{t+1}/\zeta_{t}$ is only a true one-period state-price deflator for the period between time $t$ and time $t+1$ if you to impose some condition on parameters and/or distributions and provide that condition. If this condition is not satisfied, what can you conclude about the asset prices in this economy?   
(c) Now suppose that the factor is the return on some particular portfolio, i.e. $x_{t+1}=\tilde{R}_{t+1}$ Answer question (b) again..   
(d) Consider the good (?) old (!) CAPM where $x_{t+1}=R_{M,t+1}$ , the return on the market portfolio. Suppose that $\mathrm{E}_{t}[R_{M,t+1}]=1.05$ $\sigma_{t}[R_{M,t+1}]=0.2\$ , and $R_{t}^{f}=1.02$ . What do you need to assume about the distribution of the market return to ensure that the model is free of arbitrage? Is an assumption like this satisfied in typical derivations of the CAPM?.  

EXERCISE 9.2 Using the orthogonal characterization of the mean-variance frontier, show that for any mean-variance efficient return $R^{\pi}$ different from the minimum-variance portfolio there is a unique mean-variance efficient return $R^{z(\pmb{\pi})}$ with $\mathrm{Cov}[R^{\pi},R^{z(\pmb{\pi})}]=0$ . Show that  

$$
\operatorname{E}[R^{z(\pi)}]=\operatorname{E}[R^{*}]-\operatorname{E}[R^{e*}]{\frac{\operatorname{E}[(R^{*})^{2}]-\operatorname{E}[R^{\pi}]\operatorname{E}[R^{*}]}{\operatorname{E}[R^{\pi}]-\operatorname{E}[R^{*}]-\operatorname{E}[R^{\pi}]\operatorname{E}[R^{e*}]}}.
$$  

EXERCISE 9.3 Consider a discrete-time economy in which asset prices are described by an unconditional linear factor model  

$$
\frac{\zeta_{t+1}}{\zeta_{t}}=a+b\cdot x_{t+1},\quad t=0,1,\ldots,T-1,
$$  

where the conditional mean and second moments of the factor are constant, i.e. $\operatorname{E}_{t}[\pmb{x}_{t+1}]=\pmb{\mu}$ and $\mathrm{E}_{t}[\mathbf{\underline{{x}}}_{t+1}\mathbf{\underline{{x}}}_{t+1}^{\top}]=\underline{{\underline{{\Sigma}}}}$ for all $t$  

You want to value an uncertain stream of dividends $D=\left(D_{t}\right)$ . You are told that dividends evolve. as  

$$
\frac{D_{t+1}}{D_{t}}=m+\psi\cdot\pmb{x}_{t+1}+\varepsilon_{t+1},\quad t=0,1,\dots,T-1,
$$  

where $\mathrm{E}_{t}[\varepsilon_{t+1}]=0$ and $\mathrm{E}_{t}[\boldsymbol{\varepsilon}_{t+1}\boldsymbol{x}_{t+1}]=\mathbf{0}$ for all $t$  

The first three questions will lead you through the valuation based directly on the pricing condition of the state-price deflator.  

(a) Show that, for any $t=0,1,\ldots,T-1$  

$$
\operatorname{E}_{t}\left[{\frac{D_{t+1}}{D_{t}}}{\frac{\zeta_{t+1}}{\zeta_{t}}}\right]=m a+\left(m{b}+a\psi\right)\cdot\mu+\psi^{\top}{\underline{{\Sigma}}}{b}\equiv A
$$  

(b) Show that  

$$
\operatorname{E}_{t}\left[{\frac{D_{t+s}}{D_{t}}}{\frac{\zeta_{t+s}}{\zeta_{t}}}\right]=A^{s}.
$$  

(c) Show that the value at time $t$ of the future dividends is  

$$
P_{t}=D_{t}\frac{A}{1-A}\left(1-A^{T-t}\right).
$$  

Next, consider an alternative valuation technique. From (4.31) we know that the dividends can be valued by the formula  

$$
P_{t}=\sum_{s=1}^{T-t}\frac{\operatorname{E}_{t}[D_{t+s}]-\beta_{t}\left[D_{t+s},\frac{\zeta_{t+s}}{\zeta_{t}}\right]\eta_{t,t+s}}{(1+\hat{y}_{t}^{t+s})^{s}},
$$  

where  

$$
\beta_{t}\left[D_{t+s},\frac{\zeta_{t+s}}{\zeta_{t}}\right]=\mathrm{Cov}_{t}\left[D_{t+s},\frac{\zeta_{t+s}}{\zeta_{t}}\right]/\mathrm{Var}_{t}\left[\frac{\zeta_{t+s}}{\zeta_{t}}\right],\quad\eta_{t,t+s}=-\mathrm{Var}_{t}\left[\frac{\zeta_{t+s}}{\zeta_{t}}\right]/\mathrm{E}_{t}\left[\frac{\zeta_{t+s}}{\zeta_{t}}\right].
$$  

In the next questions you have to compute the ingredients to this valuation formula.  

(d) What is the one-period risk-free rate of return $\boldsymbol{r}_{t}^{f}$ ? What is the time $t$ annualized yield $\hat{y}_{t}^{t+s}$ on a zero-coupon bond maturing at time. $t+s$ ? (If $B_{t}^{t+s}$ denotes the price of the bond, tl. annualized gross yield is defined by the equation $B_{t}^{t+s}=(1+\hat{y}_{t}^{t+s})^{-s}$   
(e) Show that $\mathrm{E}_{t}[D_{t+s}]=D_{t}\left(m+\psi\cdot\pmb{\mu}\right)^{s}$   
(f) Compute $\operatorname{Cov}_{t}\left[D_{t+s},\frac{\zeta_{t+s}}{\zeta_{t}}\right]$   
(g) Compute $\beta_{t}\left[D_{t+s},\frac{\zeta_{t+s}}{\zeta_{t}}\right]$   
(h) Compute $\eta_{t,t+s}$   
(i) Verify that the time $t$ value of the future dividends satisfies. $(^{*})$  

EXERCISE 9.4 In a continuous-time framework an individual with time-additive expected power utility induces the state-price deflator.  

$$
\zeta_{t}=e^{-\delta t}\left(\frac{c_{t}}{c_{0}}\right)^{-\gamma},
$$  

where $\gamma$ is the constant relative risk aversion,. $\delta$ is the subjective time preference rate, and. $c=$ $(c_{t})_{t\in[0,T]}$ is the optimal consumption process of the individual. If the dynamics of the optimal consumption process is of the form.  

$$
d c_{t}=c_{t}\left[\mu_{c t}d t+\sigma_{c t}^{\top}d z_{t}\right]
$$  

then the dynamics of the state-price deflator is  

$$
d\zeta_{t}=-\zeta_{t}\left[\left(\delta+\gamma\mu_{c t}-\frac{1}{2}\gamma(1+\gamma)\|\sigma_{c t}\|^{2}\right)d t+\gamma\sigma_{c t}^{\top}d z_{t}\right].
$$  

(a) State the market price of risk $\lambda_{t}$ in terms of the preference parameters and the expected growth rate and sensitivity of the consumption process.  

In many concrete models of the individual consumption and portfolio decisions, the optimal consumption process will be of the form.  

$$
\begin{array}{r}{c_{t}=W_{t}e^{f(X_{t},t)},}\end{array}
$$  

where $W_{t}$ is the wealth of the individual at time $t$ $X_{t}$ is the time $t$ value of some state variable, and $f$ is some smooth function. Here $X$ can potentially be multi-dimensional..  

(b) Give some examples of variables other than wealth that may affect the optimal consumption of an individual and which may therefore play the role of. $X_{t}$  

Suppose the state variable $X$ is one-dimensional and write the dynamics of the wealth of the individual and the state variable as  

$$
\begin{array}{r l}&{d W_{t}=W_{t}\left[\left(\mu_{W t}-e^{f(X_{t},t)}\right)d t+\pmb{\sigma}_{W t}^{\top}d z_{t}\right],}\ &{d X_{t}=\mu_{X t}d t+\pmb{\sigma}_{X t}^{\top}d z_{t}}\end{array}
$$  

(c) Characterize the market price of risk in terms of the preference parameters and the drift and sensitivity terms of $W_{t}$ and $X_{t}$  

Hint: Apply Ito's Lemma to $c_{t}=W_{t}e^{f(X_{t},t)}$ to express the required parts of the consumption process in terms of $W$ and $X$  

(d) Show that the instantaneous excess expected rate of return on risky asset $i$ can be written as  

$$
\mu_{i t}+\delta_{i t}-r_{t}^{f}=\beta_{i W,t}\eta_{W t}+\beta_{i X,t}\eta_{X t},
$$  

where $\beta_{i W,t}$ and $\beta i X,t$ are the instantaneous beta's of the asset with respect to wealth and the state variable, respectively. Relate. $\eta_{W t}$ and $\eta_{X t}$ to preference parameters and the drift. and sensitivity terms of $W$ and $X$  
