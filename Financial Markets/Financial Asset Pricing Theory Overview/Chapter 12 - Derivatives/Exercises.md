---
tags:
  - black_scholes_merton
  - coupon_bond
  - dividend_payments
  - european_call_option
  - no_arbitrage
aliases:
  - Exercise 12.1
  - Exercise 12.2
  - Exercise 12.3
  - Exercise 12.4
  - Exercise 12.5
key_concepts:
  - Black-Scholes-Merton equation
  - European call option pricing
  - coupon bond futures price
  - dividend payment impact
  - no-arbitrage option price
---

# 12.7 Exercises  

EXERCISE 12.1 Consider a coupon bond with payment dates $T_{1}<T_{2}<\cdots<T_{n}$ . For each $i=1,2,\dots,n$ , let $Y_{i}$ be the sure payment at time $T_{i}$ . For some $t<T<T_{i}$ , let $\Phi_{t}^{T,T_{i}}$ denote the futures price at time $t$ for delivery at time $T$ of the zero-coupon bond maturing at time. $T_{i}$ with a unit payment. Show that futures price at time. $t$ for delivery at time $T$ of the coupon bond satisfies  

$$
\Phi_{t}^{T,\mathrm{cpn}}=\sum_{T_{i}>T}Y_{i}\Phi_{t}^{T,T_{i}}.
$$  

EXERCISE 12.2 Show by differentiation that the Black-Scholes-Merton call option price satisfies (12.22) and (12.23).  

EXERCISE 12.3  Show that the no-arbitrage price of a European call option on a non-dividend paying stock must satisfy  

$$
\operatorname*{max}\left(0,S_{t}-K B_{t}^{T}\right)\leq C_{t}\leq S_{t}.
$$  

Show that the no-arbitrage price of a European call on a zero-coupon bond will satisfy  

$$
\operatorname*{max}\left(0,B_{t}^{S}-K B_{t}^{T}\right)\le C_{t}^{K,T,S}\le B_{t}^{S}(1-K)
$$  

provided that all interest rates are non-negative.  

EXERCISE 12.4 We will adapt the Black-Scholes-Merton model and option pricing formula to three cases in which the underlying asset provides dividend payments before the expiration of the option at time $T$  

I. Discrete dividends known in absolute terms. Suppose that the underlying asset pays dividends at. $n$ points in time before time $T$ , namely $t_{1}<t_{2}<\cdots<t_{n}$ .All the dividends are known already. Let. $D_{j}$ denote the dividend at time $t_{j}$ . The time $t$ value of all the remaining dividends is then  

$$
D_{t}^{*}=\sum_{t_{j}>t}D_{j}e^{-r(t_{j}-t)},
$$  

where $r$ is the constant interest rate. Define $S_{t}^{*}=S_{t}-D_{t}^{*}$ . Note that $S_{T}^{*}=S_{T}$  

(a) Show that $S_{t}^{*}$ is the necessary investment at time $t$ to end up with one unit of the underlying asset at time $T$  

(b) Assuming that $S_{t}^{*}$ has constant volatility $\sigma$ , so that  

$$
d S_{t}^{*}=S_{t}^{*}\left(\mu(\cdot)d t+\sigma d z_{t}\right)
$$  

for some drift term $\mu(\cdot)$ , derive a Black-Scholes-Merton-type equation for a European call option on this asset. State the option price in terms of. $S_{t}$ (and the remaining dividends). Compare with the standard Black-Scholes-Merton formula--in particular, check whether $\sigma$ is equal to the volatility of $S_{t}$ under the assumptions on $S^{*}$  

II. Discrete dividends known as a percentage of the price of the underlying asset. Again assume that dividends are paid at $t_{1}<t_{2}<\cdots<t_{n}$ , but now assume that the dividend at time $t_{j}$ is known to be. $D_{j}=\delta_{j}S_{t_{j}-}$ , where. $\delta_{j}$ is a known constant and $S_{t_{j}-}$ is the price just before the dividend is paid out. The ex-dividend price is then $S_{t_{j}}=(1-\delta_{j})S_{t_{j}-}$ . Define the process $S^{*}$ by  

$$
S_{t}^{*}=S_{t}\prod_{{t_{j}>t}}(1-\delta_{j}),\quad t<t_{n},
$$  

and $S_{t}^{*}=S_{t}$ for $t\geq t_{n}$ . Answer the questions (a) and (b) above using this definition of $S^{*}$  

III. Continuous dividend payments at a known rate. Now suppose that the underlying asset pays dividends continuously at a constant and known relative rate $\delta$ . This means that over any very short time interval $[t,t+\Delta t]$ , the total dollar dividends is $\int_{t}^{t+\Delta t}\delta S_{u}d u$ or approximately $\partial S_{t+\Delta t}\Delta t$ . Define  

$$
S_{t}^{*}=S_{t}e^{-\delta(T-t)}.
$$  

Again, answer the questions (a) and (b) using this new definition of $S^{*}$ . Hint: For part (a), you may want to divide the interval $[t,T]$ into $N$ equally long subintervals and assume that dividends. are paid only at the end of each subinterval. Use the result $\begin{array}{r}{\operatorname*{lim}_{N\to\infty}(1+\delta\frac{I^{\prime}-t}{N})^{N}=e^{\delta(T-t)}}\end{array}$ to go to the continuous-time limit.  

EXERCISE 12.5Let $S_{1}=\left(S_{1t}\right)$ and $S_{2}=\left(S_{2t}\right)$ be the price processes of two assets. Consider the option to exchange (at zero cost) one unit of asset 2 for one unit of asset 1 at some prespecified date $T$ . The payoff is thus $\operatorname*{max}\left(S_{1T}-S_{2T},0\right)$ . The assets have no dividends before time. $T$  

(a) Argue that the time $t$ value of this option can be written as  

$$
V_{t}=S_{2t}\operatorname{E}_{t}^{\mathbb{Q}_{2}}\left[\operatorname*{max}\left(\frac{S_{1T}}{S_{2T}}-1,0\right)\right],
$$  

where $\mathbb{Q}_{2}$ is the risk-adjusted probability measure associated with asset 2.  

Suppose that $S_{1}$ and $S_{2}$ are both geometric Brownian motions so that we may write their joint dynamics as  

$$
\begin{array}{r l}&{{d S_{1t}}=S_{1t}\left[\mu_{1}d t+\sigma_{1}d z_{1t}\right],}\ &{{d S_{2t}}=S_{2t}\left[\mu_{2}d t+\rho\sigma_{2}d z_{1t}+\sqrt{1-\rho^{2}}\sigma_{2}d z_{2t}\right].}\end{array}
$$  

(b) Find the dynamics of. $S_{1t}/S_{2t}$ under the probability measure $\mathbb{Q}_{2}$  

(c) Use the two previous questions and your knowledge of lognormal random variables to show that  

$$
V_{t}=S_{1t}N(d_{1})-S_{2t}N(d_{2}),
$$  

where  

$$
d_{1}=\frac{\ln(S_{1t}/S_{2t})}{v}+\frac{1}{2}v,\quad d_{2}=d_{1}-v,\quad v=\sqrt{(\sigma_{1}^{2}+\sigma_{2}^{2}-2\rho\sigma_{1}\sigma_{2})(T-t)}.
$$  

This formula was first given by Margrabe (1978).  

(d) Give pricing formulas (in terms of $S_{1t}$ and $S_{2t}$ ) for an option with payoff. $\operatorname*{max}(S_{1T},S_{2T})$ and an option with payoff. $\operatorname*{min}(S_{1T},S_{2T})$   
(e) What happens to the pricing formula (12.66) if asset 2 is a zero-coupon bond maturing at time $T$ with a payment of $K$ ? And if, furthermore, interest rates are constant, what then?  

EXERCISE 12.6 Let $F_{t}^{T,S}$ and $\Phi_{t}^{T,S}$ denote the forward price and futures price at time $t$ respectively, for delivery at time $T>t$ of a zero-coupon bond maturing at time $S>T$ . Under the. assumptions of the Vasicek model introduced in Section 10.5.1, show that  

$$
\begin{array}{r l}&{{\cal F}_{t}^{T,S}=\exp\{-[a(S-t)-a(T-t)]-[b(S-t)-b(T-t)]r_{t}\},}\ &{\quad\Phi_{t}^{T,S}=\exp\{-\tilde{a}(T-t,S-T)-[b(S-t)-b(T-t)]r_{t}\},}\end{array}
$$  

where $a(\cdot)$ and $b(\cdot)$ are given by (10.38) and (10.36),  

$$
\tilde{a}(T-t,S-T)=a(S-T)+\kappa\hat{r}b(S-T)b(T-t)-\frac{\sigma_{r}^{2}}{2}b(S-T)^{2}\left(b(T-t)-\frac{\kappa}{2}b(T-t)^{2}\right)
$$  

and $\hat{r}=\bar{r}-\sigma_{r}\lambda/\kappa$  

EXERCISE 12.7 Let $\tilde{l}_{T_{0}}^{\delta}(k)$ be the equilibrium swap rate for a swap with payment dates $T_{1},T_{2},\ldots,T_{k}$ , where $T_{i}=T_{0}+i\delta$ as usual. Suppose that $l_{T_{0}}^{\delta}(1),\ldots,l_{T_{0}}^{\delta}(n)$ are known. Find a recursive procedure for deriving the associated discount factors $B_{T_{0}}^{T_{1}},B_{T_{0}}^{T_{2}},\ldots,B_{T_{0}}^{T_{n}}$  

EXERCISE 12.8 Show the parity (12.64). Show that a payer swaption and a receiver swaption. (with identical terms) will have identical prices, if the exercise rate of the contracts is equal to the forward swap rate L4,To.  

EXERCISE 12.9 Consider a swap with starting date $T_{0}$ and a fixed rate $K$ . For $t\leq T_{0}$ , show that $V_{t}^{\mathrm{fl}}/V_{t}^{\mathrm{fix}}=\tilde{L}_{t}^{\delta,T_{0}}/K$ , where $\tilde{L}_{t}^{\delta,T_{0}}$ is the forward swap rate.  

# Appendix A  

# A review of basic probability concepts  

Any asset pricing model must handle uncertainty. Therefore we need to apply some concepts and results from probability theory. We will be a bit more formal than many textbooks on statistics for business and economics. This section is meant to give a short introduction. We will discuss further issues in later chapters when we need them in our asset pricing models.  

The basic mathematical object for studies of uncertain events is a probability space, which is a triple $(\Omega,{\mathcal{F}},\mathbb{P})$ consisting of a state space. $\Omega$ , a sigma-algebra $\mathcal{F}$ , and a probability measure. $\mathbb{P}$ Any study of uncertain events must explicitly or implicitly specify the probability space. Let us discuss each of the three elements of a probability space in turn.  

The state space $\Omega$ is the set of possible states or outcomes of the uncertain object. Only one. of these states will be realized. For example, if one studies the outcome of a throw of a die (the number of "eyes" on the upside), the state space is. $\Omega=\{1,2,3,4,5,6\}$ . An event is a set of possible. outcomes, i.e. a subset of the state space. In the example with the die, some events are. $\{1,2,3\}$ $\{4,5\}$ $\{1,3,5\}$ $\{6\}$ , and $\{1,2,3,4,5,6\}$ . This is an example where a finite state space is natural.. For other uncertain objects it is natural to take an infinite state space. If we only want to study. the dividend of a given stock at a given point in time, an appropriate state space is $\mathbb{R}_{+}\equiv\left\lbrack0,\infty\right\rbrack$ since the dividend may in principle be any non-negative real number. In our asset pricing models. we want to study the entire economy over a certain time span so the state space has to list all the possible realizations of dividends of all assets and incomes of all individuals. Of course, this requires a large state space. Note that some authors use the term sample space instead of state space.  

The second component of a probability space, $\mathcal{F}$ , is the set of events to which a probability can be assigned, i.e. the set of "probabilizable"' or "measurable" events. Hence, $\mathcal{F}$ is a set of subsets of the state space! It is required that  

(i) the entire state space can be assigned a probability, i.e. $\Omega\in{\mathcal{F}}$   
(ii) if some event $F\subseteq\Omega$ can be assigned a probability, so can its complement $F^{c}\equiv\Omega\setminus F$ , i.e. $F\in\mathcal{F}\Rightarrow F^{c}\in\mathcal{F}$ ; and  

(iii) given a sequence of probabilizable events, the union is also probabilizable, i.e. $F_{1},F_{2},\cdots\in$ $\mathcal{F}\Rightarrow\cup_{i=1}^{\infty}F_{i}\in\mathcal{F}$  

A set $\mathcal{F}$ with these properties is called a sigma-algebra, a sigma-field, or a tribe. We will stick to the term sigma-algebra.  

An alternative way to represent the probabilizable events is by a partition $\mathbf{F}$ of $\Omega$ . By a partition $\mathbf{F}$ of $\Omega$ we mean a collection $A_{1},\ldots,A_{k}$ of disjoint subsets of $\Omega$ , i.e. $A_{i}\cap A_{j}=\varnothing$ for $i\neq j$ , so that the union of these subsets equals the entire set. $\Omega$ , i.e. $\Omega=A_{1}\cup\ldots\cup A_{k}$ . With a finite state space $\Omega=\{\omega_{1},\omega_{2},\dots,\omega_{S}\}$ the natural partition is  

$$
\mathbf F=\Big\{\{\omega_{1}\},\{\omega_{2}\},\cdot\cdot\cdot,\{\omega_{S}\}\Big\},
$$  

which intuitively means that we will learn exactly which state is realized. Given a partition $\mathbf{F}$ we can define an associated sigma-algebra $\mathcal{F}$ as the set of all unions of (countably many) sets in $\mathbf{F}$ including the "empty union', i.e. the empty set $\varnothing$ .Again, if. $\Omega=\{\omega_{1},\omega_{2},...,\omega_{S}\}$ and $\mathbf{F}=\left\{\{\omega_{1}\},\{\omega_{2}\},\ldots,\{\omega_{S}\}\right\}$ , the corresponding sigma-algebra is the set of all subsets of $\Omega$ . On the other hand we can also go from a sigma-algebra $\mathcal{F}$ to a partition $\mathbf{F}$ . Just remove all sets in $\mathcal{F}$ that are unions of the sets in $\mathcal{F}$ . Again this includes the empty set $\varnothing$ since that is is an "empty union' of the other sets in $\mathcal{F}$ . If the state space is infinite, the equivalence between a partition and. a sigma-algebra may break down, and the sigma-algebra formulation is the preferred one; see for example the discussion in Bjork (2004, App. B).  

We can think of the sigma-algebra $\mathcal{F}$ or the associated partition $\mathbf{F}$ as representing full information about the realization of the state. In some cases it can be relevant also to model some limited information about the realized state. Many models in financial economics are designed to capture uncertainty about many different variables or objects, for example the dividends on a large number of stocks. It may be relevant to formalize what can be learned about the true state by just observing the dividends of one particular stock. In other models some individuals are assumed to know more about some uncertain objects than other individuals. Less-than-full information can be represented formally by a sigma-algebra $\mathcal{G}$ on $\Omega$ , which is coarser than $\mathcal{F}$ in the sense that any set in $\mathcal{G}$ is also in $\mathcal{F}$ . In terms of partitions, a partition $\mathbf{G}$ of $\Omega$ represent less information than $\mathbf{F}$ if any set in $\mathbf{G}$ is the union of sets in $\mathbf{F}$ . In the example with the throw of a die, full information is represented by the partition  

$$
\mathbf{F}=\left\{\{1\},\{2\},\{3\},\{4\},\{5\},\{6\}\right\}
$$  

or the associated sigma-algebra. An example of less-than-perfect information is represented by the partition  

$$
\mathbf{G}=\left\{\{1,3,5\},\{2,4,6\}\right\}
$$  

or the associated sigma-algebra  

$$
\mathcal{G}=\Big\{\emptyset,\{1,3,5\},\{2,4,6\},\Omega\Big\}.
$$  

With $\mathbf{G}$ , you will only know whether the die will show an odd or an even number of eyes on the upside. As mentioned above the link between partitions and sigma-algebras is more delicate in infinite state spaces and so is the notion of information. Dubra and Echenique (2004) gives an example in an economic setting where one partition represents more information than another partition but the sigma-algebra associated with the second partition seems to represent more information than the sigma-algebra associated with the first!.  

The final component of a probability space is a probability measure $\mathbb{P}$ , which formally is a. function from the sigma-algebra $\mathcal{F}$ into the interval [0, 1]. To each event $F\in{\mathcal{F}}$ , the probability. measure assigns a number. $\mathbb{P}(F)$ in the interval [0, 1]. This number is called the. $\mathbb{P}$ -probability (or) simply the probability) of. $F$ . A probability measure must satisfy the following conditions:.  

(i) $\mathbb{P}(\Omega)=1$ and $\mathbb{P}(\varnothing)=0$   
(ii) the probability of the state being in the union of disjoint sets is equal to the sum of the probabilities for each of the sets, i.e. given $F_{1},F_{2},\cdots\in\mathcal{F}$ with $F_{i}\cap F_{j}=\emptyset$ for all $i\neq j$ , we have $\begin{array}{r}{\mathbb{P}(\cup_{i=1}^{\infty}F_{i})=\sum_{i=1}^{\infty}\mathbb{P}(F_{i})}\end{array}$  

If the state space $\Omega$ is finite, say $\Omega=\{\omega_{1},\omega_{2},\dots,\omega_{S}\}$ , and each $\left\{\omega_{i}\right\}$ is probabilizable, a probability measure $\mathbb{P}$ is fully specified by the individual state probabilities $\mathbb{P}(\omega_{i})$ $i=1,2,\dots,S$  

Many different probability measures can be defined on the same sigma-algebra, $\mathcal{F}$ , of events. In the example of the die, a probability measure $\mathbb{P}$ corresponding to the idea that the die is "fair' is defined by  

$$
\mathbb{P}(\{1\})=\mathbb{P}(\{2\})=\cdots=\mathbb{P}(\{6\})=1/6.
$$  

Another probability measure, $\mathbb{Q}$ , can be defined by  

$$
\mathbb{Q}(\{1\})=1/12,\quad\mathbb{Q}(\{2\})=\cdots=\mathbb{Q}(\{5\})=1/6,\quad\mathbb{Q}(\{6\})=3/12,
$$  

which may be appropriate if the die is believed to be "unfair."  

Two probability measures. $\mathbb{P}$ and $\mathbb{Q}$ defined on the same state space and sigma-algebra. $(\Omega,{\mathcal{F}})$ are called equivalent if the two measures assign probability zero to exactly the same events, i.e. if $\mathbb{P}(A)=0\Leftrightarrow\mathbb{Q}(A)=0$ . The two probability measures in the die example are equivalent. In the stochastic models of financial markets switching between equivalent probability measures turns out to be useful.  

A random variable is a function. $X$ from the state space $\Omega$ into the real numbers $\mathbb{R}$ . To each possible outcome $\omega\in\Omega$ the function assigns a real number. $X(\omega)$ . A random variable is thus the formal way to represent a state-dependent quantity. To be meaningful, the function. $X$ must be $\mathcal{F}$ -measurable. This means that for any interval. $I\in\mathbb R$ , the set $\{\omega\in\Omega|X(\omega)\in I\}$ belongs to $\mathcal{F}$ , i.e. we can assign a probability to the event that the random variable takes on a value in the interval $I$ A random variable is thus defined relative to a probability space. $\left(\Omega,\mathcal{F},\mathbb{P}\right)$  

Any random variable is associated with a probability distribution. We can represent the distribution by the cumulative distribution function $F_{X}:\mathbb{R}\to\mathbb{R}$ defined for any $x\in\mathbb R$ by  

$$
F_{X}(x)=\mathbb{P}\left(X\leq x\right)\equiv\mathbb{P}\left(\left\{\omega\in\Omega|X(\omega)\leq x\right\}\right).
$$  

If the random variable can only take on finitely many different values $x_{1},x_{2},\dots,x_{m}\in\mathbb{R}$ , it is said to be a discrete-valued or simply a discrete random variable, and we can represent the probability distribution by the numbers $\begin{array}{r}{f_{X}(x_{i})\equiv\mathbb{P}(X=x_{i})\equiv\mathbb{P}\left(\left\{\omega\in\Omega|X(\omega)=x_{i}\right\}\right.}\end{array}$ ).Note that this is surely the case if the state space $\Omega$ itself is finite. A random variable $X$ is said to be a continuous-valued or simply continuous random variable if it can take on a continuum of.  

possible values and a function $f_{X}:\mathbb{R}\to\mathbb{R}$ exists such that  

$$
F_{X}(x)=\int_{-\infty}^{x}f_{X}(y)d y.
$$  

The function. $f_{X}$ is then called the probability density function of. $X$ .It is also possible to construct random variables that are neither discrete or continuous but they will not be important for our purposes. In any case we can represent the probability distribution more abstractly by a. distribution measure $\mu_{X}$ , which is a probability measure on the real numbers. $\mathbb{R}$ equipped with the so-called Borel-algebra $\mathcal{B}$ . The Borel-algebra can be defined as the smallest sigma-algebra that. includes all intervals. The Borel-algebra includes all subsets of $\mathbb{R}$ "you can think of" but there are. in fact some very obscure subsets of. $\mathbb{R}$ which are not in the Borel-algebra. Fortunately, this will. be unimportant for our purposes. The distribution measure is defined for any. $B\in{\mathcal{B}}$ by  

$$
\begin{array}{r}{\mu_{X}(B)=\mathbb{P}\left(X\in B\right)\equiv\mathbb{P}\left(\left\{\omega\in\Omega|X(\omega)\in B\right\}\right).}\end{array}
$$  

It is often useful to summarize the probability distribution of a random variable in a few informative numbers. The most frequently used are the expected value (or mean) and the variance. For a discrete random variable $X$ that can take on the values. $x_{1},\ldots,x_{m}\in\mathbb{R}$ the expected value $\operatorname{E}[X]$ is defined by  

$$
\operatorname{E}[X]=\sum{\sum_{i=1}^{m}}x_{i}\mathbb{P}\left(X=x_{i}\right).
$$  

For a continuous random variable $X$ with probability density function $f_{X}$ , the expected value is. defined as  

$$
\operatorname{E}[X]=\int_{-\infty}^{\infty}x f_{X}(x)d x
$$  

if this integral is finite; otherwise the random variable does not have an expected value. Similarly we can define the expected value of a function $g(X)$ as $\begin{array}{r}{\operatorname{E}[g(X)]=\sum_{i=1}^{n}g(x_{i})\mathbb{P}\left(X=x_{i}\right)}\end{array}$ or $\operatorname{E}[g(X)]=$ $\textstyle\int_{-\infty}^{\infty}g(x)f_{X}(x)d x$ , respectively.  

For a general random variable. $X$ we can define the expected value of $g(X)$ as  

$$
\operatorname{E}[g(X)]=\int_{\Omega}g\left(X(\omega)\right)d\mathbb{P}(\omega)
$$  

which is an integral with respect to the probability measure $\mathbb{P}$ . For functions that are just modestly nice (so-called Borel functions) one can rewrite the expected value as  

$$
\operatorname{E}[g(X)]=\int_{-\infty}^{\infty}g(x)d\mu_{X}(x)
$$  

which is an integral with respect to the distribution measure. $\mu_{X}$ of the random variable. We do not want to go into the theory of integration with respect to various measures so let us just note that for discrete and continuous random variables the general definition simplifies to the definitions. given in the paragraph above.  

The variance of a random variable $X$ is generally defined as  

$$
\operatorname{Var}[X]=\operatorname{E}\left[\left(X-\operatorname{E}[X]\right)^{2}\right]=\operatorname{E}\left[X^{2}\right]-\left(\operatorname{E}[X]\right)^{2}.
$$  

The standard deviation of $X$ is $\sigma[X]={\sqrt{\operatorname{Var}[X]}}$ . The $n$ 'th moment of the random variable $X$ is $\operatorname{E}[X^{n}]$ , while the. $n$ 'th central moment is $\operatorname{E}left[(X-\operatorname{E}[X])^{n}\right]$ . In particular, the variance is the second central moment.  

It can be shown that, for any constants $a$ and $b$  

$$
\operatorname{E}[a X+b]=a\operatorname{E}[X]+b,\quad\operatorname{Var}[a X+b]=a^{2}\operatorname{Var}[X].
$$  

In the example with the throw of a die, the random variable $X$ defined by $X(\omega)=\omega$ for all $\omega\in\Omega$ simply represents the uncertain number of eyes on the upside of the die after the throw. Other random variables may be relevant also. Suppose that you bet 10 dollars with a friend that the number of eyes on the upside will be even or odd. If even, you will win 10 dollars, if odd, you will loose 10 dollars. A random variable $Y$ capturing your uncertain gain on the bet can be defined as follows:  

$$
Y(\omega)=\left\{{10,}\atop{-10,}\atop{\mathrm{if}\omega\in\{1,3,5\}}.}\right.
$$  

If the die is believed to be fair, corresponding to the probability measure $\mathbb{P}$ , the distribution associated with the random variable $Y$ is given by  

$$
{\mathbb{P}}\left(Y=-10\right)={\mathbb{P}}\left(\omega\in\{1,3,5\}\right)=\frac{1}{2},\quad{\mathbb{P}}\left(Y=10\right)={\mathbb{P}}\left(\omega\in\{2,4,6\}\right)=\frac{1}{2}
$$  

or by the cumulative distribution function  

$$
F_{Y}(x)\equiv\mathbb{P}\left(Y(\omega)\leq x\right)=\left\{\begin{array}{l l}{0,}&{\mathrm{for~}x<-10,}\ {\frac{1}{2},}&{\mathrm{for~}-10\leq x<10,}\ {1,}&{\mathrm{for~}x\geq10.}\end{array}\right.
$$  

Observing the realization of a random variable can give you some information about which state $\omega$ was realized. If the random variable $X$ takes on different values in all states, i.e. you cannot. find $\omega_{1},\omega_{2}\in\Omega$ with $\omega_{1}\neq\omega_{2}$ and $X(\omega_{1})\neq X(\omega_{2})$ , observing the realized value. $X(\omega)$ will tell you exactly which state was realized. On the other extreme, if. $X$ takes on the same value in all states, you cannot infer anything from observing. $X(\omega)$ . Other random variables will tell you something. but not all. In the example above, observing the realization of the random variable $Y$ will tell you either that the realized state is in. $\{1,3,5\}$ or in $\{2,4,6\}$ . We can represent this by the partition  

$$
\mathbf{F}_{Y}=\left\{\{1,3,5\},\{2,4,6\}\right\}
$$  

or the associated sigma-algebra  

$$
\mathcal{F}_{Y}=\Big\{\emptyset,\{1,3,5\},\{2,4,6\},\Omega\Big\}.
$$  

More generally, we can define the sigma-algebra associated with a random variable $X:\Omega\to\mathbb{R}$ to be the smallest sigma-algebra on $\Omega$ with respect to which. $X$ is a measurable function. This sigma-algebra will be denoted. $\mathcal{F}_{X}$ . Just think of this as the information generated by. $X$  

We have defined a random variable to be a function from $\Omega$ to $\mathbb{R}$ . Given two random variables $X_{1}$ and $X_{2}$ on the same probability space, we can form the vector $\left({X}_{1},{X}_{2}\right)^{\top}$ , which is then a (measurable) function from $\Omega$ to $\mathbb{R}^{2}$ said to be a two-dimensional random variable. For example, $X_{1}$ could represent the uncertain dividend of one asset and $X_{2}$ the uncertain dividend of another asset. Similarly we can define random variables of any other (integer) dimension. This will often be notationally convenient.  

For a two-dimensional random variable. $\left(X_{1},X_{2}\right)^{\top}$ the joint or simultaneous cumulative distribution function is the function $F_{(X_{1},X_{2})}:\mathbb{R}^{2}\rightarrow\mathbb{R}$ defined by  

$$
F_{(X_{1},X_{2})}\left(x_{1},x_{2}\right)=\mathbb{P}\left(X_{1}\leq x_{1},X_{2}\leq x_{2}\right)\equiv\mathbb{P}\left(\left\{\omega\in\Omega\vert X_{1}(\omega)\leq x_{1}{\mathrm{~and~}}X_{2}(\omega)\leq x_{2}\right\}\right).
$$  

If both $X_{1}$ and $X_{2}$ are discrete random variables, the vector random variable. $(X_{1},X_{2})^{\top}$ is also discrete, and the joint probability distribution is characterized by probabilities $\mathbb{P}\left(X_{1}=x_{1},X_{2}=x_{2}\right)$ The two-dimensional random variable $(X_{1},X_{2})$ is said to be continuous if a function. $f_{(X_{1},X_{2})}:$ $\mathbb{R}^{2}\to\mathbb{R}$ exists such that  

$$
F_{(X_{1},X_{2})}(x_{1},x_{2})=\int_{-\infty}^{x_{1}}\int_{-\infty}^{x_{2}}f_{(X_{1},X_{2})}(y_{1},y_{2})d y_{1}d y_{2}
$$  

and $f_{(X_{1},X_{2})}$ is then called the joint or simultaneous probability density function of $(X_{1},X_{2})$  

Given the joint distribution of. $(X_{1},X_{2})^{\top}$ , we can find the distributions of. $X_{1}$ and $X_{2}$ , the socalled marginal distributions. For example, if $(X_{1},X_{2})^{\top}$ is continuous with joint probability density function $f_{(X_{1},X_{2})}$ , we can find the marginal probability density function of $X_{1}$ by integrating over all possible values of $X_{2}$ , i.e.  

$$
f_{X_{1}}(x_{1})=\int_{-\infty}^{+\infty}f_{(X_{1},X_{2})}(x_{1},x_{2})d x_{2}.
$$  

Two random variables $X_{1}$ and $X_{2}$ are said to be independent if  

$$
\mathbb{P}\left(X_{1}\in B_{1},X_{2}\in B_{2}\right)=\mathbb{P}\left(X_{1}\in B_{1}\right)\mathbb{P}\left(X_{2}\in B_{2}\right)
$$  

for all Borel sets $B_{1},B_{2}\subseteq\mathbb{R}$ or, equivalently, if  

$$
F_{(X_{1},X_{2})}(x_{1},x_{2})=F_{X_{1}}(x_{1})F_{X_{2}}(x_{2})
$$  

for all $\left(x_{1},x_{2}\right)\in\mathbb{R}^{2}$  

We can easily extend the definition of expected value to functions of multi-dimensional random variables.If $(X_{1},X_{2})^{\top}$ is a two-dimensional continuous random variable and. $g:\mathbb{R}^{2}\rightarrow\mathbb{R}$ , the expected value of $g(X_{1},X_{2})$ is defined as  

$$
\operatorname{E}[g(X_{1},X_{2})]=\int_{-\infty}^{+\infty}\int_{-\infty}^{+\infty}g(x_{1},x_{2})f_{(X_{1},X_{2})}(x_{1},x_{2})d x_{1}d x_{2}.
$$  

We define the covariance between $X_{1}$ and $X_{2}$ by  

$$
\operatorname{Cov}[X_{1},X_{2}]=\operatorname{E}\left[\left(X_{1}-\operatorname{E}[X_{1}]\right)\left(X_{2}-\operatorname{E}[X_{2}]\right)\right]=\operatorname{E}[X_{1}X_{2}]-\operatorname{E}[X_{1}]\operatorname{E}[X_{2}].
$$  

In particular, $\operatorname{Cov}[X_{1},X_{1}]=\operatorname{Var}[X_{1}]$ . The correlation between $X_{1}$ and $X_{2}$ is  

$$
\rho[X_{1},X_{2}]={\frac{\mathrm{Cov}[X_{1},X_{2}]}{\sigma[X_{1}]\sigma[X_{2}]}},
$$  

which is a number in the interval $[-1,1]$ . Some useful properties of covariances are  

$$
\mathrm{\small~\left.\begin{array}{r}{\mathrm{\small~\left/{ov}[}X_{2},X_{1}\right],\quad\mathrm{\small~\mathrm{Cov}[}a X_{1}+b X_{2},X_{3}\mathrm{\small~\left/{X_{3}}]~}=a\mathrm{\small~\mathrm{Cov}[}X_{1},X
$$  

where $X_{1},X_{2},X_{3}$ are three random variables and $a,b\in\mathbb{R}$ . An often used result is  

$$
\mathrm{Var}[X_{1}+X_{2}]=\mathrm{Var}[X_{1}]+\mathrm{Var}[X_{2}]+2\mathrm{Cov}[X_{1},X_{2}].
$$  

If $X_{1}$ and $X_{2}$ are independent, one can show that $\mathrm{Cov}[X_{1},X_{2}]=0$ and, consequently, $\rho[X_{1},X_{2}]=$ $0$  

If $\pmb{X}=(X_{1},\ldots,X_{K})^{\top}$ is a $K$ -dimensional random variable, its variance-covariance matrix is the $K\times K$ matrix $\mathrm{Var}[X]$ with $(i,j)$ 'th entry given by. $\operatorname{Cov}[X_{i},X_{j}]$ . If $\boldsymbol{X}$ is a $K$ -dimensional random variable and $\underline{{\underline{{A}}}}$ is an $M\times K$ matrix, then  

$$
\operatorname{Var}[{\underline{{\underline{{A}}}}}X]={\underline{{\underline{{A}}}}}\operatorname{Var}[X]{\underline{{\underline{{A}}}}}^{\top}.
$$  

If $\smash{\ensuremath{\boldsymbol{X}}=(X_{1},\ldots,X_{K})^{\intercal}}$ is a $K$ -dimensional random variable and $Y~=~(Y_{1},\dots,Y_{L})^{\top}$ is an $L$ dimensional random variable, their covariance matrix $\operatorname{Cov}[X,Y]$ is the $K\times L$ matrix whose. $(k,l)$ 'th entry is $\mathrm{Cov}[X_{k},Y_{l}]$ . If $\boldsymbol{X}$ is a $K$ -dimensional random variable, $\mathbf{Y}$ is an $L$ -dimensional random variable, $\underline{{\underline{{A}}}}$ is an $M\times K$ matrix, and $\pmb{a}$ is an $M$ -dimensional vector, then.  

$$
\mathrm{Cov}[{\pmb a}+\underline{{\underline{{A}}}}{\pmb X},{\pmb Y}]=\underline{{\underline{{A}}}}\mathrm{Cov}[{\pmb X},{\pmb Y}].
$$  

Conditional expectations...  

# Appendix B  

# Results on the lognormal distribution  

A random variable $Y$ is said to be lognormally distributed if the random variable $X=\ln Y$ is normally distributed. In the following we let $m$ be the mean of $X$ and $s^{2}$ be the variance of $X$ , so that  

$$
X=\ln Y\sim N(m,s^{2}).
$$  

The probability density function for $X$ is given by  

$$
f_{X}(x)={\frac{1}{\sqrt{2\pi s^{2}}}}\exp\left\{-{\frac{(x-m)^{2}}{2s^{2}}}\right\},\qquadx\in\mathbb{R}.
$$  

Theorem B.1 The probability density function for $Y$ is given by.  

$$
f_{Y}(y)=\frac{1}{\sqrt{2\pi s^{2}}y}\exp\left\{-\frac{(\ln y-m)^{2}}{2s^{2}}\right\},\qquady>0,
$$  

and $f_{Y}(y)=0$ for $y\leq0$  

This result follows from the general result on the distribution of a random variable which is given as a function of another random variable; see any introductory text book on probability theory and distributions.  

Theorem B.2 For $X\sim N(m,s^{2})$ and $\gamma\in\mathbb{R}$ we have  

Proof: Per definition we have  

$$
\operatorname{E}\left[e^{-\gamma X}\right]=\exp\left\{-\gamma m+{\frac{1}{2}}\gamma^{2}s^{2}\right\}.
$$  

$$
\operatorname{E}\left[e^{-\gamma X}\right]=\int_{-\infty}^{+\infty}e^{-\gamma x}{\frac{1}{\sqrt{2\pi s^{2}}}}e^{-{\frac{(x-m)^{2}}{2s^{2}}}}d x.
$$  

Manipulating the exponent we get  

$$
\begin{array}{l}{{\displaystyle\mathrm{E}\left[e^{-\gamma X}\right]=e^{-\gamma m+\frac{1}{2}\gamma^{2}s^{2}}\int_{-\infty}^{+\infty}\frac1{\sqrt{2\pi s^{2}}}e^{-\frac{1}{2s^{2}}\left[(x-m)^{2}+2\gamma(x-m)s^{2}+\gamma^{2}s^{4}\right]}d x}}\ {{\displaystyle\quad\quad=e^{-\gamma m+\frac{1}{2}\gamma^{2}s^{2}}\int_{-\infty}^{+\infty}\frac1{\sqrt{2\pi s^{2}}}e^{-\frac{(x-[m-\gamma s^{2}])^{2}}{2s^{2}}}d x}}\ {{\displaystyle\quad\quad=e^{-\gamma m+\frac{1}{2}\gamma^{2}s^{2}},}}\end{array}
$$  

where the last equality is due to the fact that the function  

$$
x\mapsto{\frac{1}{\sqrt{2\pi s^{2}}}}e^{-{\frac{(x-[m-\gamma s^{2}])^{2}}{2s^{2}}}}
$$  

is a probability density function, namely the density function for an $N(m-\gamma s^{2},s^{2})$ distributed random variable.  

Using this theorem, we can easily compute the mean and the variance of the lognormally distributed random variable $Y=e^{X}$ . The mean is (let $\gamma=-1$  

$$
\operatorname{E}[Y]=\operatorname{E}\left[e^{X}\right]=\exp\left\{m+{\frac{1}{2}}s^{2}\right\}.
$$  

With $\gamma=-2$ we get  

$$
\begin{array}{r}{\mathrm{E}\left[Y^{2}\right]=\mathrm{E}\left[e^{2X}\right]=e^{2(m+s^{2})},}\end{array}
$$  

so that the variance of $Y$ is  

$$
{\begin{array}{r}{\operatorname{Var}[Y]=\operatorname{E}\left[Y^{2}\right]-(\operatorname{E}[Y])^{2}}\ {=e^{2(m+s^{2})}-e^{2m+s^{2}}}\ {=e^{2m+s^{2}}\left(e^{s^{2}}-1\right).}\end{array}}
$$  

The next theorem provides an expression of the truncated mean of a lognormally distributed random variable, i.e. the mean of the part of the distribution that lies above some level. We define the indicator variable ${\mathbf{1}}_{\left\{Y>K\right\}}$ to be equal to 1 if the outcome of the random variable $Y$ is greater than the constant. $K$ and equal to $0$ otherwise.  

Theorem B.3 If $X=\ln Y\sim N(m,s^{2})$ and $K>0$ , then we have  

$$
\begin{array}{r}{\mathrm{E}\left[Y\mathbf{1}_{\{Y>K\}}\right]=e^{m+\frac{1}{2}s^{2}}N\left(\frac{m-\ln K}{s}+s\right)}\ {=\mathrm{E}\left[Y\right]N\left(\frac{m-\ln K}{s}+s\right).}\end{array}
$$  

Proof: Because $Y>K\Leftrightarrow X>\ln K$ , it follows from the definition of the expectation of a random variable that  

$$
\begin{array}{l}{\displaystyle\mathrm{E}\left[Y\mathbf{1}_{\{Y>K\}}\right]=\mathrm{E}\left[e^{X}\mathbf{1}_{\{X>\ln K\}}\right]}\ {~=\displaystyle\int_{\ln K}^{+\infty}e^{x}\frac{1}{\sqrt{2\pi s^{2}}}e^{-\frac{(x-m)^{2}}{2s^{2}}}d x}\ {~=\displaystyle\int_{\ln K}^{+\infty}\frac{1}{\sqrt{2\pi s^{2}}}e^{-\frac{(x-[m+s^{2}])^{2}}{2s^{2}}}e^{\frac{2m s^{2}+s^{4}}{2s^{2}}}d x}\ {~=e^{m+\frac{1}{2}s^{2}}\displaystyle\int_{\ln K}^{+\infty}f_{\bar{X}}(x)d x,}\end{array}
$$  

where  

$$
f_{\bar{X}}(x)=\frac{1}{\sqrt{2\pi s^{2}}}e^{-\frac{(x-[m+s^{2}])^{2}}{2s^{2}}}
$$  

is the probability density function for an $N(m+s^{2},s^{2})$ distributed random variable. The calculations  

$$
\begin{array}{r l}{\displaystyle\int_{\ln K}^{+\infty}f_{\tilde{X}}(x)d x=\operatorname*{Prob}(\bar{X}>\ln K)}\ &{\quad\quad=\operatorname*{Prob}\bigg(\frac{\bar{X}-[m+s^{2}]}{s}>\frac{\ln K-[m+s^{2}]}{s}\bigg)}\ &{\quad\quad=\operatorname*{Prob}\bigg(\frac{\bar{X}-[m+s^{2}]}{s}<-\frac{\ln K-[m+s^{2}]}{s}\bigg)}\ &{\quad\quad=N\bigg(-\frac{\ln K-[m+s^{2}]}{s}\bigg)}\ &{\quad\quad=N\bigg(\frac{m-\ln K}{s}+s\bigg)}\end{array}
$$  

complete the proof.  

Theorem B.4 If $X=\ln Y\sim N(m,s^{2})$ and $K>0$ , we have.  

$$
{\begin{array}{r}{\operatorname{E}\left[\operatorname*{max}\left(0,Y-K\right)\right]=e^{m+{\frac{1}{2}}s^{2}}N\left({\frac{m-\ln K}{s}}+s\right)-K N\left({\frac{m-\ln K}{s}}\right)}\ {=\operatorname{E}\left[Y\right]N\left({\frac{m-\ln K}{s}}+s\right)-K N\left({\frac{m-\ln K}{s}}\right).}\end{array}}
$$  

Proof: Note that  

$$
\begin{array}{r l}&{\mathrm{E}\left[\operatorname*{max}\left(0,Y-K\right)\right]=\mathrm{E}\left[(Y-K)\mathbf{1}_{\{Y>K\}}\right]}\ &{\qquad=\mathrm{E}\left[Y\mathbf{1}_{\{Y>K\}}\right]-K\mathrm{Prob}\left(Y>K\right).}\end{array}
$$  

The first term is known from Theorem B.3. The second term can be rewritten as  

$$
{\begin{array}{r l}&{\operatorname{Prob}\left(Y>K\right)=\operatorname{Prob}\left(X>\ln K\right)}\ &{\qquad=\operatorname{Prob}\left({\frac{X-m}{s}}>{\frac{\ln K-m}{s}}\right)}\ &{\qquad=\operatorname{Prob}\left({\frac{X-m}{s}}<-{\frac{\ln K-m}{s}}\right)}\ &{\qquad=N\left(-{\frac{\ln K-m}{s}}\right)}\ &{\qquad=N\left({\frac{m-\ln K}{s}}\right).}\end{array}}
$$  

The claim now follows immediately.  