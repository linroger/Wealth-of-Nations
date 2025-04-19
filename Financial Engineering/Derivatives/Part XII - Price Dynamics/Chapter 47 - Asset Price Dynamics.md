---
tags:
  - asset_price_dynamics
  - black_scholes
  - continuous_time
  - geometric_brownian_motion
  - ito_lemma
  - sde
  - stochastic_process
  - wiener_process
aliases:
  - Asset Price
  - GBM
  - Price Dynamics
key_concepts:
  - Black-Scholes formula
  - Continuous time mathematics
  - Geometric Brownian motion
  - Ito's lemma
  - Stochastic process
  - Wiener process
---
# PRICE DYNAMICS  

# Asset Price Dynamics  

# Aims  

• To explain a standard Wiener process and how this leads to a stochastic process for the stock price $s$ , known as a geometric Brownian motion (GBM).   
• To show how Ito’s lemma can be used to move from a stochastic process for the stock price $s$ to a stochastic diferential equation (SDE) for any non-linear function $g(S,t)$ .   
• To explain the statistical relationship between a stochastic variable which is lognormal $\ln S_{t}$ and the variable itself, $S_{t}$ . In particular, the relationship between their expected values and variances.  

A great deal of analytic work in pricing derivative securities and in constructing hedge portfolios uses continuous time stochastic processes. Any variable (such as the stock price) which changes over time in a random way is said to be stochastic. In the real world we observe discrete changes in stock prices but if the time interval of observation is small enough, this approximates to a continuous time process. The Black–Scholes option pricing formula was derived using continuous time mathematics. The mathematics used is not much beyond simple calculus and the intuitive elements are stressed at each point in the argument. The aim is for the reader to get a feel for this approach rather than providing detailed proofs.  

In the frst section we examine a Weiner process, an Ito process, and a geometric Brownian motion (GMB) for the stock price S. We then derive a stochastic process for the logarithm of the stock price $\ln S_{t}$ and for the option premium $f(S,t)$ using continuous time mathematics and Ito’s lemma. The resulting equations for $\ln S_{t}$ and $f(S,t)$ are both SDEs with the same source of randomness – the latter is important in deriving a deterministic partial diferential equation PDE for the option premium $f(S,t)$ , as we see in the next chapter. Finally we analyse the behaviour of the stock price when the logarithm of the stock price is assumed to be normally distributed – this relationship is often used in the continuous time literature.  

# 47.1 STOCHASTIC PROCESSES  

In this section we model the behaviour of stock prices in continuous time and show how Ito’s Lemma can be used to derive the stochastic process for the derivatives price, given a Brownian motion for the stock price.  

# 47.1.1 Wiener Process  

This is a basic building block in representing the stochastic behaviour of a ‘cash-market’ or ‘spot’ asset, such as the stock price. If a variable $z$ follows a Wiener process over a short interval of time $\Delta t$ then:  

$$
\Delta z=\varepsilon\sqrt{\Delta t}
$$  

where $\Delta z=z_{t+\Delta t}-z_{t}$ and $\varepsilon\sim n i i d(0,1)$ or $N(0,1)$ for short. It follows that:  

$$
\mathrm{Standard\deviation:}s t d\nu(\Delta z)=\sqrt{\Delta t}
$$  

Consider the change in $z$ over a (long) period of time from 0 to $T_{\mathbf{\delta}}$ . We divide the period $\{0,T\}$ into $n=T/\Delta t$ , small time intervals of length $\Delta t=1/252$ (for example). Then:  

$$
\Delta z_{T}\equiv z_{T}-z_{0}=\sqrt{\Delta t}\quad\sum_{i=1}^{n}\varepsilon_{i}
$$  

The $\varepsilon_{i}$ are niid and therefore:  

Expected value: $E(\Delta z_{T})=0$  

$$
\mathrm{Standard\deviation:}s t d\nu(\Delta z_{T})=\sqrt{T}
$$  

$V a r(\Delta z_{T})$ depends only on the time diference from $t=0$ to $T$ . If we have two non-overlapping time intervals $\{t_{1},t_{2}\}$ and $\{t_{3},t_{4}\}$ then $z_{2}-z_{1}$ and $z_{4}-z_{3}$ are uncorrelated, as the $\varepsilon_{i}$ ’s are independent (over time). A standard Wiener process $d z$ is the limit as $\Delta t\rightarrow0$ :  

$$
d z=\varepsilon{\sqrt{d t}}
$$  

where $d z$ and $d t$ represent the usual notation in diferential calculus. A Wiener process is sometimes referred to as a ‘Brownian motion’ and has the following properties:  

# Properties of a Wiener process  

• for any $s<t,z(t)-z(s)\sim N(0,t-s)$   
• for $0<t_{1}<t_{2}<t_{3}<t_{4}$ $z_{4}-z_{3}$ and $z_{2}-z_{1}$ are uncorrelated • $z_{0}=1$ with probability 1.  

# 47.1.2 Generalised Wiener Process  

The problem in using a standard Wiener process to represent stock prices is that the mean change $E(d z)$ is zero but we know that stock prices tend to increase over long periods of time. A slightly better model for stock prices is the ‘generalised Wiener process’:  

$$
d x=a d t+b d z
$$  

where $\cdot_{a}\cdot\cdot$ and $\mathbf{\nabla}^{\cdot}b_{\mathbf{\nabla}}^{\cdot}$ are constants. If we ignore the stochastic term $d z$ , then:  

$$
d x/d t=\mathrm{~a~}x_{t}=x_{0}+a t
$$  

and $x_{t}$ grows at a rate $\cdot_{a}\cdot\cdot$ per period. In discrete time the generalised Wiener process is:  

$$
\Delta x=a\ \Delta t+b\ \Delta z
$$  

where $\Delta z=\varepsilon\sqrt{\Delta t}$  

$$
\begin{array}{c}{{E(\Delta x)=a\ \Delta t\ \mathrm{and}}}\\ {{\mathrm{var}(\Delta x)=b^{2}\ \Delta t}}\end{array}
$$  

The drift rate is $\cdot_{a^{\prime}}$ (per period) and the variance rate is $b^{2}$ (per period). Over the period $\{0,T\}$ :  

$$
E(\Delta x_{T})=a T,\qquad\mathrm{var}(\Delta x_{T})=b^{2}T
$$  

# 47.1.3 Ito Process  

A further generalisation of (47.7) is to allow ‘a’ and ‘b’ to depend on both the level of $x$ and time, which gives rise to a stochastic diferential equation SDE known as an Ito process:  

$$
d x=a(x,t)\ d t+b(x,t)\ d z
$$  

Here both the expected drift rate $a(x,t)$ and the variance rate $b(\boldsymbol{x},t)$ may vary over time and with the level of $x$ .  

# 47.2 GEOMETRIC BROWNIAN MOTION (GBM) AND ITO’S LEMMA  

One would have thought that (47.5) would provide a reasonable characterisation of the behaviour of stock prices since it can have an upward drift rate $(a>0)$ plus a random element. In (47.5) the expected absolute change $d x$ is a constant, $a$ . But in fnance we assume it is the expected proportionate change in the stock price $d x/x$ that is constant. That is to say, we expect two identical stocks, one with a price of $\$10$ and one with a price of $\$100$ to both move by say $10\%$ on average – that is, by $\$1$ and $\$10$ , respectively – and not for both to change by $\$1$ . Hence the stochastic behaviour of stock prices can be represented by a ‘geometric Brownian motion (GBM)’ using the proportionate change in the stock price:  

$$
d S/S=\mu d t+\sigma d z\quad{\mathrm{~where~}}d z=\varepsilon{\sqrt{d t}}\ .
$$  

A GBM is a specifc form of Ito process with $a=\mu S,b=\sigma$ S and $d S/S\sim N(\mu\ d t,\sigma^{2}d t)$ .  

# 47.2.1 Ito’s Lemma  

Ito’s lemma is a way of deriving the stochastic process for any function of a stochastic variable. Suppose we have some function $G(z)$ where $z$ is a Wiener process and we require an expression for the diferential of this function, $d G(z)$ . From ordinary calculus, a Taylor series approximation for $d G(z)$ up to second-order terms in $d z$ is:  

$$
d G(z)\approx\frac{\partial G}{\partial z}d z+\frac{1}{2}\frac{\partial^{2}G}{\partial z^{2}}d z^{2}
$$  

Note that $E(d z^{2})=d t$ and in the above equation we now replace $d z^{2}$ by $d t$ ,1 which gives us Ito’s equation for the stochastic process $d G(z)$ :  

$$
d G(z)=\frac{\partial G}{\partial z}d z+\frac{1}{2}\frac{\partial^{2}G}{\partial z^{2}}d t
$$  

Above we used a simple heuristic derivation for the stochastic behaviour of $d G$ . (A more detailed exposition is given in Appendix 47.) Note that although (47.12) is an approximation it can be shown that Ito’s equation (47.13) is exact.  

# 47.2.2 SDE for the Derivatives Price  

Assume the stock price follows an Ito process:  

$$
d S=a(S,t)d t+b(S,t)d z
$$  

The SDE for the derivatives price $f(S,t)$ is a function of the stochastic variable $s$ and time, $t$ (which is deterministic). Ito’s lemma gives the diferential equation for $f(S,t)$ as (see Appendix 47):  

$$
d f={\frac{\partial f}{\partial t}}d t+\left[{\frac{\partial f}{\partial S}}d S+{\frac{1}{2}}b^{2}{\frac{\partial^{2}f}{\partial S^{2}}}d t\right]
$$  

Substituting for $d S$ from (47.14):  

$$
d f=\left[{\frac{\partial f}{\partial t}}+a{\frac{\partial f}{\partial S}}+{\frac{1}{2}}b^{2}{\frac{\partial^{2}f}{\partial S^{2}}}\right]d t+\left\{{\frac{\partial f}{\partial S}}b\right\}d z
$$  

The drift rate of the function $f(S,t)$ is given by the expression in the square brackets and its variance rate is the expression in the curly brackets. The key feature to note is that both $d S$ (in Equation 47.14) and $d f$ depend on the same underlying source of uncertainty $d z$ . Hence, it is possible to create a risk-free portfolio by combining the stock and the option. This portfolio must earn the risk-free rate – otherwise arbitrage profts can be made. This is the approach used in the BOPM to price an option and we use it here in a continuous time framework.  

# 47.2.3 SDE for d(lnS)  

We now use Ito’s lemma to derive the stochastic behaviour of $f(S)=\ln S$ , given that $d S/S$ follows a GBM. Note that the ‘continuously compounded return’, $R^{c}\equiv d(\ln S)$ . Since $d(\ln S)$ using ordinary calculus, equals $d S/S$ then it would seem from (47.11) that the expected value of $E[d(\ln S)]$ should equal $\mu d t$ . However, this is not the case, since the transformation from $d S/S$ to $d\ln S$ requires stochastic calculus and Ito’s lemma. The GBM is:  

$$
d S=\mu S d t+\sigma S d z,\quad\mathrm{where}\quad a=\mu S\mathrm{and}b=\sigma S.
$$  

Given $f(S)=\ln S$ then:  

$$
\frac{\partial f}{\partial t}=0,\frac{\partial f}{\partial S}=\frac{1}{S},\frac{\partial^{2}f}{\partial S^{2}}=-\frac{1}{S^{2}}
$$  

Substituting these expressions into Ito’s equation (47.15) gives:  

$$
d(\ln S)=(\mu-\sigma^{2}/2)d t+\sigma d z
$$  

Using Ito’s lemma the drift rate for $d(\ln S)$ is not $\mu d t$ but $(\mu-\sigma^{2}/2)d t$ . However, both $d S/S$ and $d(\ln S)$ have the same variance, $\sigma^{2}d t$ . Hence given the GBM for $d S/S{\sim}N(\mu d t,\sigma^{2}d t)$ the stochastic process for $d(\ln S)$ using Ito’s lemma is:  

$$
\begin{array}{l}{{d(\ln S)\sim N[(\mu-\sigma^{2}/2)d t,\quad\sigma^{2}d t]}}\\ {{\ln S_{T}\sim N[\ln S_{0}+(\mu-\sigma^{2}/2)T,\quad\sigma^{2}T]}}\end{array}
$$  

# 47.2.4 Two Stochastic Variables  

What happens if we have an option whose payof depends on two stochastic variables $S_{1}$ and $S_{2}?$ For example, this could be an option with a payof that depends on the highest of two stock prices at expiration of the option. If $S_{1}$ and $S_{2}$ both follow an Ito process then:  

$$
\begin{array}{c}{d S_{1}=a_{1}(S_{1},t)\ d t+b_{1}(S_{1},t)\ d z_{1}}\\ {d S_{2}=a_{2}(S_{2},t)\ d t+b_{2}(S_{2},t)\ d z_{2}}\end{array}
$$  

Suppose two Wiener processes $d z_{i}$ have variances and correlation coefcient $-1\leq\mathsf{\rho}_{\mathsf{\rho}}\leq1$ . Ito’s lemma gives the SDE for the derivative security $f(S_{1},S_{2},t)$ which has a payof depending on these two underlying variables:  

$$
i f=\frac{\partial f}{\partial t}d t+\left(\frac{\partial f}{\partial S_{1}}d S_{1}+\frac{\partial f}{\partial S_{2}}d S_{2}\right)+\frac{1}{2}\left(b_{1}^{2}\frac{\partial^{2}f}{\partial S_{1}^{2}}+b_{2}^{2}\frac{\partial^{2}f}{\partial S_{2}^{2}}\right)d t+\rho b_{1}b_{2}\left(\frac{\partial^{2}f}{\partial S_{1}\partial S_{2}}\right)d t.
$$  

The only ‘new’ term is the fnal one which accounts for the correlation between the two stock returns. We could also substitute for $d S_{1}$ and $d S_{2}$ , which gives $d f$ as a direct function of the Wiener processes $d z_{1},d z_{2}$ . To hedge or ‘remove’ these two stochastic terms in the SDE for $d f$ requires delta hedging with two underlying assets $S_{1},S_{2}$ . As we see in the next chapter this gives a PDE (which is deterministic) and can be solved for the derivatives price either analytically or numerically.  

# 47.3 DISTRIBUTION OF LOG STOCK PRICE AND STOCK PRICE  

Below we examine the relationship between the statistical distribution for the ‘logarithm of the stock price’ $(\ln S)$ and the distribution for the ‘level of the stock price’ S – the latter is needed because it is the expected stock price which determines the payof to a (plain vanilla) option. In particular, if we know the mean and standard deviation of the logarithm of a variable $\ln S$ , what is the mean and standard deviation for the level of $S$ , itself. This is the standard statistical analysis of the lognormal distribution which is often used in continuous time fnance.  

Assume the continuously compounded $(\log)$ return $R_{t}^{c}\equiv\ln(S_{t}/S_{t-1})$ over a small interval of time $(t-1,t)$ is $N(\nu,\sigma^{2})$ and obeys the following stochastic process (with $d t=1\AA$ ):  

$$
R_{t}^{c}\equiv\ln(S_{t}/S_{t-1})=\nu+\sigma\varepsilon_{t}
$$  

where $\varepsilon_{t}$ is an identically and independently distributed random variable with a zero-mean and is drawn from a symmetric distribution. Note that $\ensuremath{\varepsilon}_{t}$ need not be normally distributed:),  

$E R_{t}^{c}\equiv E[\ln(S_{t}/S_{t-1})]=\nu$ (per period) and $\nu a r(R_{t}^{c})\equiv\nu a r[\ln(S_{t}/S_{t-1})]=\sigma^{2}$ . From (47.20) the stock price $S_{t}$ follows the stochastic process:  

$$
S_{t}=S_{t-1}e^{v+\sigma\varepsilon_{t}}
$$  

which is a non-linear function of $(\nu,\sigma,\varepsilon_{t})$ . What does (47.21) imply for the shape of the distribution for $S_{t}$ and its expected (average) value? One way of thinking about this is to set $\nu=0$ , $\sigma=0.1$ , hence $S_{t}=S_{t-1}e^{0.10\varepsilon_{t}}$ . To see how the exponential term in\$uences the distribution of $S_{t}$ consider an artifcial scenario where $S_{0}=100$ and successive values of $\ensuremath{\varepsilon}_{t}=+1$ , always.2 The resulting price series is:  

The gap between each successive value of $S_{t}$ becomes larger – starting at 10.52, then 11.62 etc. – making a ‘long’ right tail for the distribution of $S$ . Alternatively, if $\ensuremath{\varepsilon}_{t}=-1$ always, then the price series (starting at 100 and moving to the left) is:  

49.66 54.88 60.65 67.03 74.08 81.87 90.48 100  

Here, the gap between successive price changes gets smaller – starting at $-9.52$ , then $-8.61$ etc. – which ‘squashes’ the distribution in the left tail (and $s$ cannot fall below zero). Even though the distribution of $\ensuremath{\varepsilon}_{t}$ is symmetric, the distribution of the price level $s$ is truncated to the left and extended to the right and is clearly not symmetric. This tends to increase the expected value (mean) of the distribution for $s$ , so that it exceeds the expected value of the distribution of $\ln S$ (i.e. $E\ln S=\nu=0.$ ). The distribution of $R_{t}^{c}\equiv\ln(S_{t}/S_{t-1})$ is symmetric by assumption (see Equation 47.20) but the distribution of $1+R\equiv S_{t}/S_{t-1}$ is not symmetric, as argued above. We further illustrate the relationship between the mean of the distribution $\operatorname{E}(\ln S)$ and $E S$ , in Example 47.1.  

# EXAMPLE 47.1  

# Expected Value of lnS and S  

Assume $R_{t}^{c}\equiv\ln(S_{t}/S_{t-1})=\nu+\sigma\varepsilon_{t}$ . For $S_{0}=100$ , $\sigma=0.10$ and $\nu=0$ , then $E\ln(S_{t}/S_{t-1})=$ $\nu=0$ . The mean (expected) value for the (level of the) stock price one period ahead is: $E S_{1}=(S_{0}e^{\nu})E(e^{\sigma\varepsilon_{1}})=100E(e^{0.10\varepsilon_{1}})$ .3 Suppose we draw $\varepsilon_{t}$ from a distribution where it takes  

(continued)  

(continued)  

the value $+2$ or $^{-2}$ , with equal probability and therefore $E\varepsilon_{t}=0$ . The two equally likely outcomes for the stock price (in period-1) are:  

$$
S^{+}=100e^{0.10(+2)}=122.14\mathrm{and}S^{-}=100e^{0.10(-2)}=81.87
$$  

The expected stock price is: $E S=(122.14+81.87)/2=102.0$  

Hence, if the initial stock price is 100 and the continuously compounded return has a mean (expected value) $\nu=0$ , then it is not the case that the expected (average) value of the stock price (in the next period) is equal to 100.  

The average level of the stock price will be greater than 100 (in our case 102.0). This arises because of the exponential term $e^{\sigma\mathfrak{s}_{t}}$ . As the distribution of $\varepsilon_{t}$ is symmetric then positive values for $\varepsilon_{t}$ (e.g. $+2)$ in a large sample of data will be accompanied by an approximate equal number of negative values (of $-2$ ). But the positive value of $\varepsilon_{t}$ increases $s$ by more than the negative value of $\ensuremath{\varepsilon}_{t}$ decreases $s$ , hence the average value of $S$ is greater than 100.  

We now assume $\varepsilon_{t}$ is normally distributed and $\ln(S_{t}/S_{t-1})\sim N(\upsilon,\ \sigma^{2})$ . It can be shown that the distribution of $S_{t}$ has a mean:  

$$
E S_{t}=S_{t-1}e^{\nu}E(e^{\sigma\varepsilon_{i}})=S_{t-1}e^{\nu}\int_{-\infty}^{+\infty}\phi(\varepsilon)e^{\sigma\varepsilon}d\varepsilon=S_{t-1}e^{\nu+\sigma^{2}/2}
$$  

where the mathematical formula for an $N(0,1)$ distribution is denoted $\phi(\varepsilon)$ . For example, if $E[\ln(S_{t}/S_{t-1})]=\nu=0.12$ p.a. and $\sigma=0.15$ p.a., then $E(S_{t})/S_{t-1}=e^{\nu}e^{\sigma^{2}/2}=1.1275$ 1.0113 1.1403. The mean of $(S_{t}/S_{t-1})$ is larger than $\nu=12\%$ p.a. because $S_{t}$ is a non-linear function of the stochastic variable, $\ensuremath{\varepsilon}_{t}$ (Equation 47.21). $E S_{1}$ can also be calculated using a numerical technique. Set $S_{0}=100(\mathrm{say)}$ and draw $m=1{,}000$ values of $\boldsymbol{\varepsilon}_{t}$ from the $N(0,1)$ distribution and calculate the mean using:  

$$
E S_{1}=(100)e^{0.12}\left(\frac{1}{1,000}\right)\sum_{i=1}^{1,000}e^{0.15\varepsilon_{i}}
$$  

then $E S_{1}$ will be greater than $S_{0}e^{\nu}$ . More formally we can summarise the above lognormal distribution theory as follows. Assume $\ln(S_{t}/S_{t-1})\sim N(\upsilon d t,\ \sigma^{2}d t)$ :  

$$
\ln(S_{t}/S_{t-1})=\nu d t+\sigma\sqrt{d t}\varepsilon_{t}\qquad\varepsilon_{t}\sim n i i d(0,1)
$$  

$$
S_{t}=S_{t-1}e^{\nu\ d t+\sigma{\sqrt{d t}}\ \varepsilon_{t}}
$$  

Then, the expected value and variance of $\ln(S_{t}/S_{t-1})$ and $\ln(S_{T}/S_{0})$ are:  

$$
E[\ln(S_{t}/S_{t-1})]=\nu d t\mathrm{and}E[\ln(S_{T}/S_{0})]=\nu T
$$  

$$
\nu a r[\ln(S_{t}/S_{t-1})]=\sigma^{2}d t\mathrm{and}\nu a r[\ln(S_{T}/S_{0})]=\sigma^{2}T
$$  

Using standard statistical distribution theory it can be shown that for the stock price:  

$$
E(S_{t}/S_{t-1})=e^{(\nu+\sigma^{2}/2)d t}\quad\mathrm{and}\quad E(S_{T}/S_{0})=e^{(\nu+\sigma^{2}/2)T}
$$  

For completeness, also note that statistical distribution theory shows that the variance of the stock price at $T$ is:  

$$
\mathrm{var}(S_{T})=S_{0}^{2}~e^{2\mu T}(e^{\sigma^{2}T}-1)
$$  

Hence, starting from the assumption that $\ln(S_{t}/S_{t-1})\sim N(\nu d t,\sigma^{2}d t)$ is niid, we have obtained the mean and variance for the level of the stock price, $S_{T}$ .  

# 47.4 SUMMARY  

• An Ito process is one where the (absolute) change in a stochastic variable $x$ over a short interval of time, is normally distributed. The drift rate and variance may be functions of $x$ and time.   
• The stochastic behaviour for the proportionate change in stock prices (over a small interval of time) can be represented by a continuous time process with positive drift, known as geometric Brownian motion (GBM), which is a specifc form of Ito process.   
• Ito’s lemma can be used to determine the stochastic process for any non-linear function $f(S,t)$ , given the stochastic process for $S$ .   
• If the continuously compounded return is normally distributed $\ln(S_{t}/S_{t-1})\sim$ $N(\nu d t,\sigma^{2}d t)$ then statistical distribution theory implies that the distribution of $(S_{t}/S_{t-1})$ is not symmetric and has a long right tail and a truncated left tail. The distribution of $(S_{t}/S_{t-1})$ is lognormal, with mean $E(S_{t}/S_{t-1})=e^{(\nu+\sigma^{2}/2)d t}$ .  

# APPENDIX 47: ITO’S LEMMA  

In moving from a GBM for $d S/S$ with drift $\mu$ to a SDE for $d(\ln S)$ requires the use of Ito’s lemma and the drift term for $d(\ln S)$ is $\mu-\sigma^{2}/2$ . Below we give a heuristic proof of Ito’s lemma. An Ito process (for $d t\rightarrow0$ ) is:  

$$
d x=a(x,t)\ d t+b(x,t)\ d z,\mathrm{where}d z=\varepsilon\sqrt{d t},\varepsilon\sim n i i d(0,1)
$$  

Below we show that any function $f(x,t)$ satisfes Ito’s equation:  

$$
d f=\left({\frac{\partial f}{\partial t}}+{\frac{\partial f}{\partial x}}a+{\frac{1}{2}}{\frac{\partial^{2}f}{\partial x^{2}}}b^{2}\right)d t+{\frac{\partial f}{\partial x}}b\ d z
$$  

From (47.A.1), $(d x)^{2}$ is of order $d t$ . Expanding $f(x,t)$ as a Taylor series (ignoring terms of higher order than $d t$ ):  

$$
d f={\frac{\partial f}{\partial t}}d t+{\frac{\partial f}{\partial x}}d x+{\frac{1}{2}}{\frac{\partial^{2}f}{\partial x^{2}}}(d x)^{2}
$$  

Substituting for $d x$ and $d x^{2}$ from (47.A.1):  

$$
d f={\frac{\partial f}{\partial t}}d t+{\frac{\partial f}{\partial x}}(a\ d t+b\ d z)+{\frac{1}{2}}{\frac{\partial^{2}f}{\partial x^{2}}}[a\ d t+b\ d z]^{2}
$$  

The term in square brackets is:  

$$
i t+b\ d z]^{2}=(a\ d t)^{2}+2a b\ (d t\ d z)+(b\ d z)^{2}=O_{p}d t^{2}+O_{p}d t^{3/2}+b^{2}\varepsilon^{2}d t\quad.
$$  

where $O_{p}(.)$ represents the ‘order in probability’. The frst two terms are of higher order than $O_{p}(d t)$ , while the fnal term is of order $d t$ and must be retained. Also, $\varepsilon\sim N(0,1)$ , so that $\dot{V a r(\varepsilon)}=E\varepsilon^{2}-(E\varepsilon)^{2}=1$ . But $E\varepsilon=0$ , so $E\varepsilon^{2}=1$ and therefore $E(\varepsilon^{2}d t)=d t$ . It can also be shown that $V a r(\varepsilon^{2}\ d t)$ is of order $d t^{2}$ and as a result, $\cdot_{\varepsilon^{2}}d t^{\prime}$ itself, becomes non-stochastic with expected value, $d t$ . Thus as $d t\rightarrow0$ :  

$$
\begin{array}{r}{(b~d z)^{2}\rightarrow b^{2}~d t}\\ {[a~d t+b~d z]^{2}\rightarrow b^{2}~d t}\end{array}
$$  

This is the basis of our ‘simplifcation’ of the proof, so we simply ‘replace’ the stochastic term $(b d z)^{2}$ by $b^{2}d t$ . Substituting from Equation (47.A.7) in (47.A.4) and letting $d t\rightarrow0$ gives Ito’s equation (47.A.2).  

# EXERCISES  

# Question 1  

Do you think that the number of centimetres of rainfall per month at a certain place are (statistically) independent over time? Explain.  

# Question 2  

Explain the basic properties of a standard Wiener process.  

# Question 3  

Explain a geometric Brownian motion (GBM) for stock prices.  

# Question 4  

If the change in the stock price follows a GBM, $d S=\mu\ S\ d t+\sigma S\ d z$ , use Ito’s lemma to show that $d\ln(S)=(\mu-\sigma^{2}/2)d t+\sigma d z$ .  

# Question 5  

The continuously compounded stock return follows the stochastic process:  

$$
R_{i}^{c}\equiv\ln(S_{t}/S_{t-1})=\nu+\sigma\varepsilon_{t}
$$  

$\varepsilon_{t}$ is an identically and independently distributed random variable from a binomial distribution, where it takes the value $+1$ or $^{-1}$ , with equal probability and therefore $E\varepsilon_{t}=0$ . The mean of the continuously compounded return equals $\nu$ (per period) and its variance is $\sigma^{2}$ . Assume $S_{0}=100$ , $\nu=0$ and $\sigma=0.1$ , so that from (1) $S_{t}=S_{t-1}e^{0.10\varepsilon_{t}}$ and the stock price after 2 periods is determined by:  

$$
S_{2}=S_{0}e^{0.10(\varepsilon_{1}+\varepsilon_{2})}
$$  

Calculate the four possible out-turn values for the combination $(\varepsilon_{1}+\varepsilon_{2})$ , the resulting four possible outcomes for $S_{2}$ and the expected value $E S_{2}$ . Brie\$y comment on the distribution of $R_{2}^{c}\equiv\mathrm{ln}(S_{2}/S_{0})$ and the resulting distribution of $(S_{2}/S_{0})$ .  