---
tags:
  - bond_pricing
  - equilibrium
  - interest_rate_models
  - mean_reversion
  - ornstein_uhlenbeck_process
  - vasicek_model
  - yield_curve
aliases:
  - Ornstein-Uhlenbeck
  - Short-term interest rate
  - Vasicek
  - Zero-coupon bond
key_concepts:
  - Bond pricing and yield curve
  - Equilibrium real interest rate
  - Market price of risk
  - Mean reversion in drift
  - Ornstein-Uhlenbeck process
  - Stochastic differential equation (SDE)
  - Vasicek interest rate model
---

# 10.5 Equilibrium interest rate models  

# 10.5.1 The Vasicek model  

A classic but still widely used model of interest rate dynamics and the pricing of bonds and interest. rate derivatives is the model proposed by Vasicek (1977). The basic assumptions of the model is that the continuously compounded short-term interest rate. $r_{t}$ has dynamics  

$$
d r_{t}=\kappa\left(\bar{r}-r_{t}\right)d t+\sigma_{r}d z_{t},
$$  

where $\kappa$ $\bar{r}$ , and $\sigma_{r}$ are positive constants, and that the market price of risk associated with the shock $z$ is a constant $\lambda$  

Before we study the consequences of these assumptions, let us see how they can be supported. by a consumption-based equilibrium model. Following Goldstein and Zapatero (1996) assume that aggregate consumption evolves as  

$$
d c_{t}=c_{t}\left[\mu_{c t}d t+\sigma_{c}d z_{t}\right],
$$  

where $z$ is a one-dimensional standard Brownian motion, $o_{C}$ is a constant, and the expected consumption growth rate $\mu_{c t}$ follows the process  

$$
d\mu_{c t}=\kappa\left(\bar{\mu}_{c}-\mu_{c t}\right)d t+\theta d z_{t}.
$$  

The representative individual is assumed to have a constant relative risk aversion of $\gamma$ . It follows from (10.16) that the equilibrium real short-term interest rate is.  

$$
r_{t}=\delta+\gamma\mu_{c t}-\frac{1}{2}\gamma(1+\gamma)\sigma_{C}^{2}
$$  

with dynamics $d r_{t}=\gamma d\mu_{c t}$ , which gives (10.31) with $\sigma_{r}=\gamma\theta$ and $\bar{r}=\gamma\bar{\mu}_{c}+\delta-{\textstyle\frac{1}{2}}\gamma(1+\gamma)\sigma_{c}^{2}$ . The market price of risk is $\lambda=\gamma\sigma_{c}$ , a constant.  

The process (10.31) is a so-called Ornstein-Uhlenbeck process. An Ornstein-Uhlenbeck process exhibits mean reversion in the sense that the drift is positive when. $r_{t}<r$ and negative when. $x_{t}>r$ . The process is therefore always pulled towards a long-term level of. $r$ .However, the. random shock to the process through the term. $\sigma_{r}d z_{t}$ may cause the process to move further away from $r$ . The parameter $\kappa$ controls the size of the expected adjustment towards the long-term level. and is often referred to as the mean reversion parameter or the speed of adjustment..  

To determine the distribution of the future value of the short-term interest rate define a new process $y_{t}$ as some function of. $r_{t}$ such that $y=(y_{t})_{t\geq0}$ is a generalized Brownian motion. It turns out that this is satisfied for $y_{t}=g(r_{t},t)$ , where $g(r,t)=e^{\kappa t}r$ . From Ito's Lemma we get  

$$
\begin{array}{l}{{\displaystyle{d y_{t}=\left[\frac{\partial g}{\partial t}(r_{t},t)+\frac{\partial g}{\partial r}(r_{t},t)\kappa\left(\bar{r}-r_{t}\right)+\frac{1}{2}\frac{\partial^{2}g}{\partial r^{2}}(r_{t},t)\sigma_{r}^{2}\right]d t+\frac{\partial g}{\partial r}(r_{t},t)\sigma_{r}d z_{t}}}}\ {{\mathrm{~}=\left[\kappa e^{\kappa t}r_{t}+\kappa e^{\kappa t}\left(\bar{r}-r_{t}\right)\right]d t+e^{\kappa t}\sigma_{r}d z_{t}}}\ {{\displaystyle{~=\kappa\bar{r}e^{\kappa t}d t+\sigma_{r}e^{\kappa t}d z_{t}}}.}\end{array}
$$  

This implies that  

$$
y_{t^{\prime}}=y_{t}+\kappa\bar{r}\int_{t}^{t^{\prime}}e^{\kappa u}d u+\int_{t}^{t^{\prime}}\sigma_{r}e^{\kappa u}d z_{u}.
$$  

After substitution of the definition of and and a multiplication by. $e^{-\kappa t^{\prime}}$ , we arrive at the. $y_{t}$ $y_{t^{\prime}}$   
expression  

$$
\begin{array}{r l}&{r_{t^{\prime}}=e^{-\kappa(t^{\prime}-t)}r_{t}+\kappa\bar{r}\displaystyle\int_{t}^{t^{\prime}}e^{-\kappa(t^{\prime}-u)}d u+\int_{t}^{t^{\prime}}\sigma_{r}e^{-\kappa(t^{\prime}-u)}d z_{u}}\ &{\quad=e^{-\kappa(t^{\prime}-t)}r_{t}+\bar{r}\left(1-e^{-\kappa(t^{\prime}-t)}\right)+\displaystyle\int_{t}^{t^{\prime}}\sigma_{r}e^{-\kappa(t^{\prime}-u)}d z_{u}.}\end{array}
$$  

This holds for all. $t^{\prime}>t\geq0$ . In particular, we get that the solution to the stochastic differential equation (10.31) can be written as  

$$
r_{t}=e^{-\kappa t}r_{0}+\bar{r}\left(1-e^{-\kappa t}\right)+\int_{0}^{t}\sigma_{r}e^{-\kappa(t-u)}d z_{u}.
$$  

According to Theorem 2.3, the integrald $\begin{array}{r}{\int_{t}^{t^{\prime}}\sigma_{r}e^{-\kappa\left(t^{\prime}-u\right)}d z_{u}}\end{array}$ is normally distributed with meand zero and variance $\begin{array}{r}{\int_{t}^{t^{\prime}}\sigma_{r}^{2}e^{-2\kappa(t^{\prime}-u)}d u=\frac{\sigma_{r}^{2}}{2\kappa}\Big(1-e^{-2\kappa(t^{\prime}-t)}\Big)}\end{array}$ We can thus conclude that $T t^{\prime}$ (given $r_{t}$ ) is normally distributed, with mean and variance given by  

$$
\begin{array}{r l}&{~\mathrm{E}_{t}[r_{t^{\prime}}]=e^{-\kappa(t^{\prime}-t)}r_{t}+\bar{r}\left(1-e^{-\kappa(t^{\prime}-t)}\right),}\ &{~\mathrm{Var}_{t}[r_{t^{\prime}}]=\frac{\sigma_{r}^{2}}{2\kappa}\left(1-e^{-2\kappa(t^{\prime}-t)}\right).}\end{array}
$$  

The value space of an Ornstein-Uhlenbeck process is $\mathbb{R}$ . For $t^{\prime}\to\infty$ , the mean approaches $r$ and the variance approaches. $\sigma_{r}^{2}/(2\kappa)$ . For $\kappa\rightarrow\infty$ , the mean approaches $r$ , and the variance approaches $0$ . For $\kappa\rightarrow0$ , the mean approaches the current value $r_{t}$ , and the variance approaches. $\sigma_{r}^{2}(t^{\prime}-t)$ . The distance between the level of the process and the long-term level is expected to be halved over a period of $t^{\prime}-t=(\ln2)/\kappa$ , since $\begin{array}{r}{\mathrm{E}_{t}[r_{t^{\prime}}]-\bar{r}=\frac{1}{2}(r_{t}-\bar{r})}\end{array}$ implies that $\begin{array}{r}{e^{-\kappa(t^{\prime}-t)}=\frac{1}{2}}\end{array}$ and, hence, $t^{\prime}-t=(\ln2)/\kappa$  

The effect of the different parameters can also be evaluated by looking at the paths of the process, which can be simulated by  

$$
r_{t_{i}}=r_{t_{i-1}}+\kappa[\bar{r}-r_{t_{i-1}}](t_{i}-t_{i-1})+\sigma_{r}\varepsilon_{i}\sqrt{t_{i}-t_{i-1}},
$$  

where $\varepsilon_{i}\sim N(0,1)$ . Figure 10.1 shows a single path for different combinations of. $r_{0}$ $\kappa$ $r$ , and $\sigma_{r}$ In each sub-figure one of the parameters is varied and the others fixed. The base values of the parameters are $r_{0}=0.08$ $\bar{r}=0.08$ $\kappa=\ln2\approx0.69$ , and $\sigma_{r}=0.03$ . All paths are computed using. the same sequence of random numbers $\varepsilon_{1},\ldots,\varepsilon_{n}$ and are therefore directly comparable. None of. the paths shown involve negative values of the process, but other paths will, see e.g. Figure 10.2.. As a matter of fact, it can be shown that an Ornstein-Uhlenbeck process with probability one will. sooner or later become negative..  

What are the implications of the Vasicek assumptions for bond prices and the yield curve? The time $t$ price of a zero-coupon bond maturing at time. $s$ is given by  

$$
B_{t}^{s}=\mathrm{E}_{t}\left[\frac{\zeta_{s}}{\zeta_{t}}\right]=\mathrm{E}_{t}\left[\exp\left\{-\int_{t}^{s}r_{u}d u-\frac{1}{2}\int_{t}^{s}\lambda^{2}d u-\int_{t}^{s}\lambda d z_{u}\right\}\right].
$$  

![](aa91ef79b8c9771b5427ae66d58f461f07dd747c5525df962126c215a3dd4ab1.jpg)  
Figure 10.1: Simulated paths for an Ornstein-Uhlenbeck process. The basic parameter values are $r_{0}=\bar{r}=0.08$ $\kappa=\ln2\approx0.69$ , and $\sigma_{r}=0.03$  

In order to compute this expectation, first use (10.32) to find that  

$$
\int_{t}^{s}r_{u}d u=\int_{t}^{s}e^{-\kappa(u-t)}r_{t}d u+\int_{t}^{s}{\bar{r}}\left(1-e^{-\kappa(u-t)}\right)d u+\int_{t}^{s}\int_{t}^{u}\sigma_{r}e^{-\kappa(u-v)}d z_{v}d u.
$$  

Interchange the order of integration in the double integral (this follows from the so-called Fubini Theorem of stochastic calculus)  

$$
\int_{t}^{s}\left[\int_{t}^{u}\sigma_{r}e^{-\kappa(u-v)}d z_{v}\right]d u=\int_{t}^{s}\left[\int_{v}^{s}\sigma_{r}e^{-\kappa(u-v)}d u\right]d z_{v}.
$$  

Further note that. $\begin{array}{r}{\int_{t}^{s}e^{-\kappa(u-t)}d u=b(s-t)}\end{array}$ , where we have introduced the function  

$$
b(\tau)={\frac{1}{\kappa}}\left(1-e^{-\kappa\tau}\right),
$$  

Also note that  

$$
\int_{t}^{s}b(s-u)d u={\frac{1}{\kappa}}(s-t-b(s-t)),\qquad\int_{t}^{s}b(s-u)^{2}d u={\frac{1}{\kappa^{2}}}(s-t-b(s-t))-{\frac{1}{2\kappa}}b(s-t)^{2}.
$$  

It now follows that  

$$
\int_{t}^{s}r_{u}d u=r_{t}b(s-t)+\bar{r}\left(s-t-b(s-t)\right)+\int_{t}^{s}\sigma_{r}b(s-u)d z_{u},
$$  

and using Theorem 2.3 and results in Appendix B we obtain  

$$
\begin{array}{r l}&{B_{t}^{s}=e^{-r_{t}b(s-t)-\bar{r}(s-t-b(s-t))-\frac{1}{2}\lambda^{2}(s-t)}\operatorname{E}_{t}\bigg[e^{-\int_{t}^{s}(\lambda+\sigma_{r}b(s-u))d z_{u}}\bigg]}\ &{\quad=e^{-r_{t}b(s-t)-\bar{r}(s-t-b(s-t))-\frac{1}{2}\lambda^{2}(s-t)}e^{\frac{1}{2}\int_{t}^{s}(\lambda+\sigma_{r}b(s-u))^{2}d u}}\ &{\quad=e^{-r_{t}b(s-t)-\bar{r}(s-t-b(s-t))-\frac{1}{2}\lambda^{2}(s-t)}e^{\frac{1}{2}\lambda^{2}(s-t)+\lambda\sigma_{r}\int_{t}^{s}b(s-u)d u+\frac{1}{2}\sigma_{r}^{2}\int_{t}^{s}b(s-u)^{2}d u}}\ &{\quad=e^{-a(s-t)-b(s-t)r_{t}},}\end{array}
$$  

where  

$$
a(\tau)=y_{\infty}(\tau-b(\tau))+\frac{\sigma_{r}^{2}}{4\kappa}b(\tau)^{2}
$$  

and  

$$
y_{\infty}=\bar{r}-\frac{\lambda\sigma_{r}}{\kappa}-\frac{\sigma_{r}^{2}}{2\kappa^{2}}.
$$  

The continuously compounded yield of the zero-coupon bond maturing at time $s$ is  

$$
y_{t}^{s}=-\frac{\ln B_{t}^{s}}{s-t}=\frac{a(s-t)}{s-t}+\frac{b(s-t)}{s-t}r_{t},
$$  

which is affine in the current short rate $r_{t}$ . A model with this property is called an affine term. structure model. It can be shown that $y_{t}^{s}\to y_{\infty}$ for $s\to\infty$ , which explains the notation. The. asymptotic long yield is a constant in the Vasicek model. Concerning the shape of the yield curve $s\to y_{t}^{s}$ it can be shown that.  

(i) if $\begin{array}{r}{r_{t}<y_{\infty}-\frac{\sigma_{r}^{2}}{4\kappa^{2}}}\end{array}$ , the yield curve is increasing;   
(ii) if $\begin{array}{r}{r_{t}>y_{\infty}+\frac{\sigma_{r}^{2}}{2\kappa^{2}}}\end{array}$ , the yield curve is decreasing:   
(iii) for intermediate values of. $r_{t}$ , the yield curve is humped, i.e. increasing in $s$ up to some maturity $s^{*}$ and then decreasing for longer maturities.  

Within the Vasicek model it is possible to find closed-form expressions for the prices of many. other interesting assets, such as forwards and futures on bonds, Eurodollar futures, and European options on bonds; see Chapter 12..  

There are many other affine term structure models and they can basically all be supported by. a consumption-based asset pricing model in the same way as the Vasicek model. Assume that the expected growth rate and the variance rate of aggregate consumption are affine in some state. variables, i.e.  

$$
\mu_{c t}=a_{0}+\sum_{i=1}^{n}a_{i}x_{i t},\qquad\|\pmb{\sigma}_{c t}\|^{2}=b_{0}+\sum_{i=1}^{n}b_{i}x_{i t},
$$  

then the equilibrium short rate will be  

$$
r_{t}=\left(\delta+\gamma a_{0}-\frac{1}{2}\gamma(1+\gamma)b_{0}\right)+\gamma\sum_{i=1}^{n}\left(a_{i}-\frac{1}{2}(1+\gamma)b_{i}\right)x_{i t}.
$$  

Of course, we should have. $\begin{array}{r}{b_{0}+\sum_{i=1}^{n}b_{i}x_{i t}\ge0}\end{array}$ for all values of the state variables. The market. price of risk is. $\lambda_{t}=\gamma\sigma_{c t}$ . If the state variables. $x_{i}$ follow processes of the affine type, we have an affine term structure model..  

For other term structure models developed with the consumption-based approach, see e.g. Bakshi and Chen (1997).  

# 10.5.2 The Cox-Ingersoll-Ross model  

Another widely used model of interest rate dynamics was suggested by Cox, Ingersoll, and Ross (1985b). They assume that the short-term interest rate. $r_{t}$ follows a so-called square root process  

$$
d r_{t}=\kappa\left(\bar{r}-r_{t}\right)d t+\sigma_{r}\sqrt{r_{t}}d\bar{z}_{t},
$$  

where $\kappa$ $r$ , and $\sigma_{r}$ are positive constants. Further they assume that the associated market price of risk is. $\lambda_{t}=\lambda\sqrt{r_{t}}/\sigma_{r}$ , where the. $\lambda$ on the right-hand side is a constant.  

They derive their model as a special case of their general equilibrium model with production which we have reviewed in Section 10.4. The representative individual is assumed to have a logarithmic utility so that the relative risk aversion of the direct utility function is $^{1}$ . In addition, the individual is assumed to have an infinite time horizon, which implies that the indirect utility function will be independent of time. It can be shown that under these assumptions the indirect utility function of the individual is of the form. $J(W,x)=A\ln W+B(x)$ . In particular, $J_{W x}=0$ and the relative risk aversion of the indirect utility function is also $^{1}$ . It follows from (10.28) that the equilibrium real short-term interest rate is equal to  

$$
r(x_{t})=g(x_{t})-\xi(x_{t})^{2}.
$$  

The authors further assume that the expected rate of return and the variance rate of the return on the productive investment are both proportional to the state, i.e.  

$$
g(x)=k_{1}x,\qquad\xi(x)^{2}=k_{2}x,
$$  

where $k_{1}>k_{2}$ . Then the equilibrium short-rate becomes $r(x)=(k_{1}-k_{2})x\equiv k x$ .Assume now that the state variable follows a square root process  

$$
\begin{array}{l}{d x_{t}=\kappa\left(\bar{x}-x_{t}\right)d t+\rho\sigma_{x}\sqrt{x_{t}}d z_{1t}+\sqrt{1-\rho^{2}}\sigma_{x}\sqrt{x_{t}}d z_{2t}}\ {~=\kappa\left(\bar{x}-x_{t}\right)d t+\sigma_{x}\sqrt{x_{t}}d{\bar{z}_{t}},}\end{array}
$$  

where $\bar{z}$ is a standard Brownian motion with correlation $\rho$ with the standard Brownian motion $z_{1}$ and correlation $\sqrt{1-\rho^{2}}$ with $z_{2}$ . Then the dynamics of the real short rate is $d r_{t}=k d x_{t}$ , which yields  

$$
d r_{t}=\kappa\left(\bar{r}-r_{t}\right)d t+\sigma_{r}\sqrt{r_{t}}d\bar{z}_{t},
$$  

where ${\bar{r}}=k{\bar{x}}$ and $\sigma_{r}=\sqrt{k}\sigma_{x}$ . The market prices of risk given in (10.29) and (10.30) simplify to  

$$
\lambda_{1}=\xi(x)=\sqrt{k_{2}x}=\sqrt{k_{2}/k}\sqrt{r},\qquad\lambda_{2}=0.
$$  

The market price of risk associated with the combined shock. $z$ is $\rho\lambda_{1}+\sqrt{1-\rho^{2}}\lambda_{2}$ , which is proportional to $\sqrt{r}$ . These conclusions support (10.40) and the associated form of the market price of risk.  

Before we discuss the implications for bond prices and the yield curve, let us look at the properties of the square root process. The only difference to the Ornstein-Uhlenbeck process is the square root term in the volatility. The variance rate is now $\sigma_{r}^{2}r_{t}$ which is proportional to the level of the process. A square root process also exhibits mean reversion. A square root process can only take on non-negative values. To see this, note that if the value should become zero, then the  

![](65ce9a40fa08e2f820571e190c9b1606d4f949a2add631b935d92ad2ab9f4548.jpg)  
Figure 10.2: A comparison of simulated paths for an Ornstein-Uhlenbeck process and a square root process. For both processes, the parameters $\bar{r}=0.08$ and $\kappa=\ln2\approx0.69$ are used, while. $\sigma_{r}$ is set to 0.03 for the Ornstein-Uhlenbeck process and to $0.03/\sqrt{0.08}\approx0.1061$ for the square root process..  

![](7976161ada784d107961ebe3e70514aeb6bdf97ff52ddd658fdca3deb8374271.jpg)  
(b) Initial value. $r_{0}=0.06$ , different random numbers  

(a) Initial value $r_{0}=0.08$ , same random numbers as in Figure 10.1  

drift is positive and the volatility zero, and therefore the value of the process will with certainty become positive immediately after (zero is a so-called reflecting barrier). It can be shown that if $2\kappa\bar{r}\geq\sigma_{r}^{2}$ , the positive drift at low values of the process is so big relative to the volatility that the. process cannot even reach zero, but stays strictly positive.1 Hence, the value space for a square root process is either $\S=[0,\infty)$ 0r $\S=(0,\infty)$  

Paths for the square root process can be simulated by successively calculating  

$$
r_{t_{i}}=r_{t_{i-1}}+\kappa[\bar{r}-r_{t_{i-1}}](t_{i}-t_{i-1})+\sigma_{r}\sqrt{r_{t_{i-1}}}\varepsilon_{i}\sqrt{t_{i}-t_{i-1}}.
$$  

Variations in the different parameters will have similar effects as for the Ornstein-Uhlenbeck process, which is illustrated in Figure 10.1. Instead, let us compare the paths for a square root process and an Ornstein-Uhlenbeck process using the same drift parameters. $\kappa$ and $\bar{r}$ , but where the. $\sigma_{r}$ parameter for the Ornstein-Uhlenbeck process is set equal to the. $\sigma_{r}$ -parameter for the square root process multiplied by the square root of. $\bar{r}$ , which ensures that the processes will have the same variance rate at the long-term level. Figure 10.2 compares two pairs of paths of the processes. In part (a), the initial value is set equal to the long-term level, and the two paths continue to be very close to each other. In part (b), the initial value is lower than the long-term level, so that the variance rates of the two processes differ from the beginning. For the given sequence of random numbers, the Ornstein-Uhlenbeck process becomes negative, while the square root process of course stays positive. In this case there is a clear difference between the paths of the two processes.  

Since a square root process cannot become negative, the future values of the process cannot be normally distributed. In order to find the actual distribution, let us try the same trick as for the  

Ornstein-Uhlenbeck process, that is we look at $y_{t}=e^{\kappa t}r_{t}$ . By Ito's Lemma,  

$$
\begin{array}{r l}&{d y_{t}=\kappa e^{\kappa t}r_{t}d t+\kappa e^{\kappa t}(\bar{r}-\kappa r_{t})d t+e^{\kappa t}\sigma_{r}\sqrt{r_{t}}d z_{t}}\ &{\qquad=\kappa\bar{r}e^{\kappa t}d t+\sigma_{r}e^{\kappa t}\sqrt{r_{t}}d z_{t},}\end{array}
$$  

so that  

$$
y_{t^{\prime}}=y_{t}+\kappa\bar{r}\int_{t}^{t^{\prime}}e^{\kappa u}d u+\int_{t}^{t^{\prime}}\sigma_{r}e^{\kappa u}\sqrt{r_{u}}d z_{u}.
$$  

Computing the ordinary integral and substituting the definition of $y$ , we get  

$$
r_{t^{\prime}}=r_{t}e^{-\kappa(t^{\prime}-t)}+\bar{r}\left(1-e^{-\kappa(t^{\prime}-t)}\right)+\sigma_{r}\int_{t}^{t^{\prime}}e^{-\kappa(t^{\prime}-u)}\sqrt{r_{u}}d z_{u}.
$$  

Since $r$ enters the stochastic integral we cannot immediately determine the distribution of $r_{t^{\prime}}$ given $r_{t}$ from this equation. We can, however, use it to obtain the mean and variance of $r_{t^{\prime}}$ . Due to the fact that the stochastic integral has mean zero, cf. Theorem 2.2, we easily get  

$$
\mathrm{E}_{t}[r_{t^{\prime}}]=e^{-\kappa(t^{\prime}-t)}r_{t}+\bar{r}\left(1-e^{-\kappa(t^{\prime}-t)}\right)=\bar{r}+\left(r_{t}-\bar{r}\right)e^{-\kappa(t^{\prime}-t)}.
$$  

To compute the variance the second equation of Theorem 2.2 can be applied, which will eventually lead to  

$$
\mathrm{Var}_{t}\big[r_{t^{\prime}}\big]=\frac{\sigma_{r}^{2}r_{t}}{\kappa}\left(e^{-\kappa(t^{\prime}-t)}-e^{-2\kappa(t^{\prime}-t)}\right)+\frac{\sigma_{r}^{2}\bar{r}}{2\kappa}\left(1-e^{-\kappa(t^{\prime}-t)}\right)^{2}.
$$  

Note that the mean is identical to the mean for an Ornstein-Uhlenbeck process, whereas the variance is more complicated for the square root process.  

It can be shown that, given the value $r_{t}$ , the value $r_{t^{\prime}}$ with $t^{\prime}>t$ is non-centrally $\chi^{2}$ -distributed More precisely, the probability density function for $T t^{\prime}$ is  

$$
f_{r_{t^{\prime}}|r_{t}}(x)=f_{\chi_{a,b}^{2}}(2c x),
$$  

where  

$$
c=\frac{2\kappa}{\sigma_{r}^{2}\left(1-e^{-\kappa(t^{\prime}-t)}\right)},\qquadb=c r_{t}e^{-\kappa(t^{\prime}-t)},\qquada=\frac{4\kappa\bar{r}}{\sigma_{r}^{2}},
$$  

and where $f_{\boldsymbol{\chi}_{a,b}^{2}}(\cdot)$ denotes the probability density function for a non-centrally $\chi^{2}$ -distributed random variable with $a$ degrees of freedom and non-centrality parameter $b$  

It can be shown that the price of a zero-coupon bond maturing at time $s$ is given by  

$$
B_{t}^{s}=e^{-a(s-t)-b(s-t)r_{t}},
$$  

where  

$$
\begin{array}{l}{{\displaystyle b(\tau)=\frac{2\bigl(e^{\nu\tau}-1\bigr)}{\bigl(\nu+\hat{\kappa}\bigr)\bigl(e^{\nu\tau}-1\bigr)+2\nu},}}\ {{\displaystyle a(\tau)=-\frac{2\kappa\bar{r}}{\sigma_{r}^{2}}\left(\ln(2\nu)+\frac{1}{2}(\hat{\kappa}+\nu)\tau-\ln\left[\bigl(\nu+\hat{\kappa}\bigr)(e^{\nu\tau}-1)+2\nu\right]\right),}}\end{array}
$$  

and $\hat{\kappa}=\kappa+\lambda$ and $\nu=\sqrt{\hat{\kappa}^{2}+2\sigma_{r}^{2}}$ . As in the Vasicek model, the yields are affine in the current short rate,  

$$
y_{t}^{s}={\frac{a(s-t)}{s-t}}+{\frac{b(s-t)}{s-t}}r_{t}.
$$  

It can be shown that the asymptotic long yield is  

$$
y_{\infty}\equiv\operatorname*{lim}_{s\to\infty}y_{t}^{s}=\frac{2\kappa\bar{r}}{\hat{\kappa}+\nu},\nonumber
$$  

and [see Kan (1992)] that the yield curve can have the following shapes:  

(i) if $\kappa+\lambda>0$ , the yield curve is decreasing for. $r_{t}\ge\kappa\bar{r}/(\kappa+\lambda)$ and increasing for $0\leq r_{t}\leq\kappa\bar{r}/\nu$ For $\kappa\bar{r}/\nu<r_{t}<\kappa\bar{r}/(\kappa+\lambda)$ , the yield curve is humped, i.e. first increasing, then decreasing.  

(ii) if $\kappa+\lambda\leq0$ , the yield curve is increasing for $0\leq r_{t}\leq\kappa\bar{r}/\nu$ and humped for. $r_{t}>\kappa\bar{r}/\nu$  

Also in this model closed-form expressions can be derived for many popular interest rate related assets; see Chapter 12.  

Longstaff and Schwartz (1992) study a two-factor version of the model. They assume that the production returns are given by  

$$
\frac{d\eta_{t}}{\eta_{t}}=g(x_{1t},x_{2t})d t+\xi(x_{2t})d z_{1t},
$$  

where  

$$
g(x_{1},x_{2})=k_{1}x_{1}+k_{2}x_{2},\qquad\xi(x_{2})^{2}=k_{3}x_{2},
$$  

so that the state variable. $x_{2}$ affects both expected returns and uncertainty of production, while. the state variable $x_{1}$ only affects the expected return. With log utility the short rate is again equal to the expected return minus the variance,.  

$$
r(x_{1},x_{2})=g(x_{1},x_{2})-\xi(x_{2})^{2}=k_{1}x_{1}+(k_{2}-k_{3})x_{2}.
$$  

The state variables are assumed to follow independent square root processes,  

$$
\begin{array}{r}{d x_{1t}=\left(\varphi_{1}-\kappa_{1}x_{1t}\right)d t+\beta_{1}\sqrt{x_{1t}}d z_{2t},}\ {d x_{2t}=\left(\varphi_{2}-\kappa_{2}x_{2t}\right)d t+\beta_{2}\sqrt{x_{2t}}d z_{3t},}\end{array}
$$  

where $z_{2}$ are independent of. $z_{1}$ and $z_{3}$ , but $z_{1}$ and $z_{3}$ may be correlated. The market prices of risk associated with the Brownian motions are  

$$
\lambda_{1}(x_{2})=\xi(x_{2})=\sqrt{k_{2}}\sqrt{x_{2}},\quad\lambda_{2}=\lambda_{3}=0.
$$  
