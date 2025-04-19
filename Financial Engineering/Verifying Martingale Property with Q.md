---
tags:
  - bond_numeraire
  - discounted_stock
  - martingale_property
  - risk_neutral_probability
  - stock_price
aliases:
  - Martingale Verification
  - Risk-Neutral Measure
  - Stock Price Martingale
key_concepts:
  - Bond as numeraire
  - Discounted stock price
  - Martingale property verification
  - Risk-neutral probabilities
  - Stock price dynamics
---

# Chapter 5 Additional Readings  

# Verifying the Martingale Property for Subsequent Periods  

In Section 5.2.2.2, we verified that the stock price relative to the bond (the bond as the numeraire) satisfies the martingale property from time O to 1. Here, we will do the same for the stock price from time 1 to 2 and then in subsequent periods. We will also demonstrate that the required measure that makes the discounted stock price into a martingale is the risk-neutral probability $\mathbb{Q}$ . This appendix is essentially a continuation of Section 5.2.2.2.  

Suppose, we are given the stock price ${\cal S}_{\boldsymbol{O},\boldsymbol{I};\boldsymbol{u}}$ at time 1 after an upjump at time 1. Denote $S_{O,2:u,u}$ and $S_{O,2:u,d}$ as the stock prices at time 2 given the outcomes $\omega_{\mathrm{u,u}}$ (consecutive upjumps at time 1 and 2) and $\omega_{\mathrm{u,d}}.$ respectively. Denote $q_{I,2;u,u}$ and $q_{I,2;u,d}$ as the risk-neutral probabilities that at time 1, the stock will have an upjump or downjump at time 2 given that it had an upjump at time 1. Let $B_{I.2}$ (discount function) be the time 1 value of a bond that pays 1 at time 2. Analogous to equation (5.15), the forward prices from time 1 to 2 given the stock price. ${\cal S}_{\boldsymbol{O},\boldsymbol{I};u}$ at time 1, must satisfy the system of equations:  

$$
\begin{array}{r}{{\small\left[\begin{array}{c c}{S_{0,2;u,u}}&{S_{0,2;u,d}}\ {1}&{1}\end{array}\right]\left[\begin{array}{c}{\psi_{1,2;u,u}}\ {\psi_{1,2;u,d}}\end{array}\right]=\left[\begin{array}{c}{S_{0,1;u}}\ {B_{1,2}}\end{array}\right]}.}\end{array}
$$  

If we divide the matrix equation by $B_{I,2}$ , and define the risk-neutral probabilities $q_{I,2;u,u}{=}\psi_{I,2;u,u}\left/B_{I,2}\right.$ and $q_{l,2;u,d}{=}\psi_{I,2;u,d}/B_{I,2}$ as required by equation (5.12) we get:  

$$
\Big[\begin{array}{c c}{S_{0,2;u,u}}&{S_{0,2;u,d}}\ {1}&{1}\end{array}\Big]\Big[{q}_{1,2;u,d}\Big]=\Big[{S}_{0,1;u}/B_{1,2}\Big].
$$  

The first row of matrix equation (2) is the equation:  

$$
\begin{array}{r}{S_{0,2;u,u}q_{1,2;u,u}+S_{0,2;u,d}q_{1,2;u,d}=\frac{S_{0,1;u}}{B_{1,2}}.}\end{array}
$$  

Equation (3) can be expressed in the form:  

$$
\begin{array}{r}{E_{\mathbb{Q}}\left[S_{2}\left|\frac{S_{0,1;u}}{B_{1,2}}\right|=\frac{S_{0,1;u}}{B_{1,2}}.}\end{array}
$$  

We can repeat the calculation given the stock price $S_{O,I;d}.$ Analogous to equations (3) and (4), we would obtain:  

$$
\begin{array}{r}{S_{0,2;d,u}q_{1,2;d,u}+S_{0,2;d,d}q_{1,2;d,d}=\frac{S_{0,1;d}}{B_{1,2}}}\end{array}
$$  

and  

$$
\begin{array}{r}{E_{\mathbb{Q}}\left[S_{2}\left|\frac{S_{0,1;d}}{B_{1,2}}\right|=\frac{S_{0,1;d}}{B_{1,2}}.}\end{array}
$$  

Equations (4) and (6) together verify the martingale property going from time 1 to 2 that the. expected value of the stock at time 2 given its value at time 1 (in bond numeraire) is equal to the value of the stock at time 1 (in bond numeraire)..  

Next, we study the stock model going from time 0 to 2. Let, $q_{O,2;u,d},q_{O,2;d,u},$ and $q_{O,2;d,d}$ denote the risk-neutral probabilities at time O that the stock price will experience the outcomes $\omega_{\mathrm{u,u}},\omega_{\mathrm{u,d}},\omega_{\mathrm{d,u}},$ and $\omega_{\mathrm{d,d}}$ , respectively, in going from time O to time 2. Let. $B_{O.2}$ be the time 0 value of a bond that pays 1 at time 2. Note that this bond value must satisfy the equation $B_{O,2}{=}B_{O,I}B_{I,2}$ Recall that $\Psi_{0,2;\mathrm{u,u}}$ is the price of the pure security at time O that pays 1 at time 2 after the upjump in the price of the stock from time 0 to time 1 and also from time 1 to time 2. The prices $\Psi_{\mathrm{0},2;\mathrm{u},\mathrm{d}}$ $\Psi_{\mathrm{0},2;\mathrm{d},\mathrm{u}}.$ and $\Psi0{,}2{;}\mathrm{d,d}$ are defined analogously. Similar to previous analysis, we have:  

$$
\begin{array}{r}{{\small\left[\begin{array}{c c c c}{S_{0,2;u,u}}&{S_{0,2;u,d}}&{S_{0,2;d,u}}&{S_{0,2;d,d}}\ {1}&{1}&{1}&{1}\end{array}\right]}\left[\begin{array}{c}{\psi_{0,2;u,u}}\ {\psi_{0,2;u,d}}\ {\psi_{0,2;d,u}}\ {\psi_{0,2;d,u}}\ {\psi_{0,2;d,d}}\end{array}\right]={\small\left[\begin{array}{c}{S_{0}}\ {B_{0,2}}\end{array}\right]}.}\end{array}
$$  

If we divide both sides of equation (7) by $B_{O,2}$ and use equation (5.12) to define the risk-neutral probabilities, we obtain:  

$$
\begin{array}{r}{{\left[\begin{array}{c c c c}{S_{0,2;u,u}}&{S_{0,2;u,d}}&{S_{0,2;d,u}}&{S_{0,2;d,d}}\ {1}&{1}&{1}&{1}\end{array}\right]}{\left[\begin{array}{l}{q_{0,2;u,u}}\ {q_{0,2;u,d}}\ {q_{0,2;d,u}}\ {q_{0,2;d,d}}\end{array}\right]}={\left[\begin{array}{l}{S_{0}/B_{0,2}}\ {1}\end{array}\right]}.}\end{array}
$$  

Notice that the first row of the matrix equation (8) is the equation:  

$$
S_{0,2;u,u}q_{0,2;u,u}+S_{0,2;u,d}q_{0,2;u,d}+S_{0,2;d,u}q_{0,2;d,u}+S_{0,2;d,d}q_{0,2;d,d}=\frac{S_{0}}{B_{0,2}}.
$$  

The left side of equation (9) is the expected value with respect to the probability measure. $\mathbb{Q}$ of the stock price at time 2 given its value at time O in bond numeraire, Thus equation (9) states that this expected value equals the value of the stock at time O in bond numeraire:.  

$$
\begin{array}{r}{E_{\mathbb{Q}}\big[S_{2}|S_{0}/B_{0,2}\big]=\frac{S_{0}}{B_{0,2}}.}\end{array}
$$  

This is the required martingale property for the stock going from time O to 2. Now, we. need to check that this result is consistent with the results going from time O to 1 followed by going from time 1 to 2. Since. $q_{O,2;u,u}$ is the probability that the stock had upjumps at times 1 and. 2, $q_{I,2;u,u}$ is the conditional probability that the stock had an upjump at time 2 given that it had an upjump at time 1, and $q_{O,I;u}$ is the probability that the stock had an upjump at time 1, then by the. definition of conditional probability, we require $q_{l,2;u,u}{=}q_{0,2;u,u}/q_{0,l;u}$ or equivalently: $q_{0,2;u,u}=$ $q_{\mathscr{O},I;u}q_{I,2;u,u}.$ The relationships for the other risk-neutral probabilities are computed in a similar way giving us:.  

# Chapter 5 Additional Readings  

$$
q_{0,2;u,u}=q_{0,1;u}q_{1,2;u,u},q_{0,2;u,d}=q_{0,1;u}q_{1,2;u,d},q_{0,2;d,u}=q_{0,1;d}q_{1,2;d,u},
$$  

$$
q_{0,2;d,d}=q_{0,1;d}q_{1,2;d,d}
$$  

Note that equations (11) define the risk-neutral probabilities from time 0 to time 2, and we need to check that they are consistent with equation (9). Since the left side of equation (9) is $E_{\mathbb{Q}}\big[S_{2}|S_{0}/B_{0,2}\big]$ and substituting the results of equations (11) into the left side of equation (9) gives:  

$$
\begin{array}{c}{{E_{\mathbb{Q}}\bigl[S_{2}\bigl|S_{0}/B_{0,2}\bigr]=S_{0,2;u,u}q_{0,1;u}q_{1,2;u,u}+S_{0,2;u,d}q_{0,1;u}q_{1,2;u,d}}}\ {{{}}}\ {{+S_{0,2;d,u}q_{0,1;d}q_{1,2;d,u}+S_{0,2;d,d}q_{0,1;d}q_{1,2;d,d}}}\ {{{}}}\ {{=(S_{0,2;u,u}q_{1,2;u,u}+S_{0,2;u,d}q_{1,2;u,d})q_{0,1;u}+(S_{0,2;d,u}q_{1,2;d,u}+S_{0,2;d,d}q_{1,2;d,d})q_{0,1;d},}}\end{array}
$$  

Referring to equations (3) and (5), we see that:  

$$
E_{\mathbb{Q}}\big[S_{2}|S_{0}/B_{0,2}\big]=\frac{S_{0,1;u}q_{0,1;u}+S_{0,1;d}q_{0,1;d}}{B_{1,2}}.
$$  

Referring to equation (5.17) and using the fact that $B_{O,2}{=}B_{O,I}B_{I,2}$ , we get:  

$$
\begin{array}{r}{E_{\mathbb{Q}}\big[S_{2}|S_{0}/B_{0,2}\big]=\frac{S_{0}}{B_{0,2}}.}\end{array}
$$  

Equation (10) is identical to equation (12), so the results are consistent. Equation (12) states that the expected value with respect to the probability measure $\mathbb{Q}$ of the stock price at time 2 given its price at time O (in bond numeraire) is equal to the stock price at time O (in bond numeraire). Thus, we have verified all of the martingale properties up to time 2. The proof to show the martingale properties for all subsequent times essentially duplicates the work we have done using an induction argument. We omit the details. The induction argument would give the result:  

$$
E_{\mathbb{Q}}\left[S_{n}\middle|\frac{S_{0}}{B_{0,n}},\frac{S_{1}}{B_{1,n}},\ldots,\frac{S_{k}}{B_{k,n}}\right]=\frac{S_{k}}{B_{k,n}}
$$  

for all $k{=}0,I,2,...,n{-}I$  

Since $E_{\mathbb{Q}}[S_{\mathrm{n}}|S_{O},S_{1},...,S_{k}]=S_{\mathrm{k}}\forall k<n$ if the stock prices are expressed in the units of the. bond as the numeraire, it is clear that. $S_{\mathrm{t}}$ is a martingale, despite its having been a submartingale when priced relative to currency..  

# Chapter 5 Additional Readings  

# Brownian Motion as a Limit of a Discrete Random Walk  

Think of the discrete random walk and Brownian motion taking place on the $\mathbf{Z}$ -axis, where we start at the origin $(z{=}O)$ at time 0. We will then study these two processes as a function of time. We can also graph each of these two processes if we wish with position z as the vertical axis versus time $t$ as the horizontal axis, analogous to the graph of a stock price $(S)$ versus time $(t)$ . The graph of the discrete random walk versus time for a specific history will consist of a 1arge number of discrete points in the. $t{-}z$ plane, while the graph of Brownian motion versus time for a specific history will consist a continuous zig-zag graph in the $t{-}z$ plane. To create Brownian motion from the discrete random walk with. $p=1/2$ , first divide each unit of time on the. continuous time axis into $n$ equal subintervals, so that the width of each subinterval is $\Delta t=1/n$ This results in the discrete times $0,1/n,2/n,...,k/n,...$ on the continuous time axis. Define the. following discrete random walk as a function of time $k$ (the $k^{\mathrm{th}}$ discrete time on the continuous time axis at time $k/n$ ) by:  

$$
\begin{array}{r}{X_{k}^{\left(n\right)}=\sum_{i=1}^{k}{\frac{Z_{i}}{\sqrt{n}}}.}\end{array}
$$  

Assume that each $Z_{i}$ is a random variable that equals 1 with probability $\%$ and equals -1 with probability $\%$ at time $i,$ and that the $Z_{i}^{\phantom{}}s$ are pairwise independent of one another. This discrete random walk, startig at , takes independent smal steps of length $\pm{\frac{1}{\sqrt{n}}}$ at each moment of time rom $(i{-}1)/n$ $i/n$ $i$ goes from I to $k$ $X_{k}^{(n)}$ at time $k/n$ Since the random walk $X_{k}^{(n)}$ takes ever-smaller seps aproaching length 0 as $n\to\infty$ it is approaching a continuous path as $n\to\infty$ for each specific history. This justification for the existence and continuity of the path isn't rigorous. A rigorous argument is beyond the level of this text.  

We next claim that as. $n\to\infty$ , the random walk will converge to a process that has a normal distribution (which is one the requirements to be Brownian motion).To prove this, pick a particular time $t$ on the continuous non-negative real line. Pick the integer $k,$ $k\leq n t$ so that it best approximates $k/n\approx t.$ Note that $\left|k/n-t\right|<l/n$ so that the approximation improves as. $n$ approaches $\infty$ . Also note that. $k\approx n t$ , so that $k\to\infty$ as $n\to\infty$ Define the sample mean random variable  

$$
\bar{Z}=\frac{\sum_{i=1}^{k}Z_{i}}{k}.
$$  

Clearly, $\begin{array}{r}{X_{k}^{(n)}=\frac{k}{\sqrt{n}}\bar{Z}}\end{array}$ Since the random variables $Z_{i}$ are independent and identiclly distributed random variables with mean $\mu=0$ and variance $\sigma^{2}=1$ , by the Central Limit Theorem. from section 2.7, we conclude that $\textstyle{\sqrt{k}}{\bar{Z}}={\frac{\bar{Z}}{1/{\sqrt{k}}}}$ 1/ approaches the standard normal random distribution $Z\sim N(0,1)$ as $k\to\infty$ . This implies that.  

# Chapter 5 Additional Readings  

$$
X_{k}^{(n)}=\sqrt{k}\bar{Z}\sqrt{\frac{k}{n}}\rightarrow Z\sqrt{t}
$$  

$k\to\infty$ Since $Z\sqrt{t}{\sim}N(0,t)$ , this shows thate $X_{k}^{(n)}$ approaches a normal distribution, say $X_{t}$ with mean O and variance $t.$ We have completed the main step to show that our random walk. converges to a process that has a normal distribution with mean O and variance $t.$  

The rest of the properties are easier to justify. If we choose the integer $j$ so that it $j/n$ best approximates a value $s$ with $s<t,$ on the time axis, then by a proof similar to that we just Ccompleted w have tm  x m a approaching a normal distribution $X_{t}-X_{s}$ with mean O and variance $t-s.$ Consider the values $s<t<u<\nu$ on the time axis. Choose the integers $j<k<l<$ m so that they best approximate $j/n\approx s,k/n\approx t,l/n\approx u,$ and $m/n\approx\nu.$ Since  

$$
\begin{array}{r}{X_{k}^{(n)}-X_{j}^{(n)}=\sum_{i=j+1}^{k}\frac{Z_{i}}{\sqrt{n}},X_{m}^{(n)}-X_{l}^{(n)}=\sum_{i=l+1}^{m}\frac{Z_{i}}{\sqrt{n}},}\end{array}
$$  

and $j+l\le k\le l+l\le m$ then the random variables $X_{k}^{(n)}-X_{j}^{(n)}$ and $X_{m}^{(n)}-X_{l}^{(n)}$ are independent. This is easily seen by observing that the $Z_{i}^{\phantom{}}s$ in the first sum are independent of the $Z_{i}$ 's inthe scond sm i thi case. tut $X_{k}^{(n)}-X_{j}^{(n)}$ approaches $X_{t}-X_{s}$ $X_{l}^{(n)}-X_{m}^{(n)}$ approaches $X_{u}-X_{\nu}$ as $n{\longrightarrow}\infty$ . Thus, $X_{t}-X_{s}$ and $X_{u}-X_{\nu}$ should be independent of one another. Each of the requirements in order that. $X_{k}^{(n)}$ will converge to the standard Brownian motion. process as $n\to\infty$ have been addressed, and we conclude that the convergent process $X_{t}$ is in fact standard Brownian motion.  

# Geometric Brownian Motion as a Limit of a Discrete Stochastic Process  

In the same way that we derived Brownian motion as a limit of a discrete stochastic process, we divide each unit of time into $n$ equal subintervals, so that the width of each subinterval is $\Delta t=$ $l/n$ This results in the discrete times $0,I/n,2/n,...,k/n,...$ on the continuous time axis. Define the price of a sock s(m) as as a discrete stochastic process as a function of time $k$ (the $k^{t h}$ discrete time on the continuous time axis at time $k/n$ ) so that:  

$$
\frac{S_{k}^{(n)}-S_{k-1}^{(n)}}{S_{k-1}^{(n)}}=\frac{\mu}{n}+\frac{\sigma Z_{k}}{\sqrt{n}}.
$$  

Assume that each $Z_{k}$ is a random variable that equals 1 with probability $\%$ and equals -1 with probability $\%$ at time $i,$ and that the $Z_{i}^{\prime}s$ are pairwise independent of one another. Observe that $\mu$ is the return per unit time per unit value of the stock and $\sigma$ is the degree of volatility of the. Stock. Solving for $S_{k}^{(n)}$ gives:  

# Chapter 5 Additional Readings  

$$
S_{k}^{(n)}=\left(1+\frac{\mu}{n}+\frac{\sigma Z_{k}}{\sqrt{n}}\right)S_{k-1}^{(n)}.
$$  

Substituting $k$ with $k-l$ in thi quation and elcin he result for $S_{k-1}^{(n)}$ in terms of $S_{k-2}^{(n)}$ on the right side of the equation above, and continuing this process all the way back to time O results in:  

$$
S_{k}^{(n)}=S_{0}\left(1+{\frac{\mu}{n}}+{\frac{\sigma Z_{1}}{\sqrt{n}}}\right)\left(1+{\frac{\mu}{n}}+{\frac{\sigma Z_{2}}{\sqrt{n}}}\right)\cdots\left(1+{\frac{\mu}{n}}+{\frac{\sigma Z_{k}}{\sqrt{n}}}\right).
$$  

Taking logarithms, we have:  

$$
l n S_{k}^{(n)}=l n S_{0}+\sum_{i=1}^{k}l n\Big(1+\frac{\mu}{n}+\frac{\sigma Z_{i}}{\sqrt{n}}\Big).
$$  

From calculus, we know that the Taylor series for $l n(I+x)$ centered at zero is  

$$
\ln(1+x)=x-{\frac{1}{2}}x^{2}+{\frac{1}{3}}x^{3}-\cdots
$$  

For a particular history o of the stock, each $Z_{i}(\omega)$ will take on the definite value of either. $I$ or $-I$ Applying the Taylor series above to.  

$$
x={\frac{\mu}{n}}+{\frac{\sigma Z_{i}(\omega)}{\sqrt{n}}}
$$  

for each $i$ results in:  

$$
\begin{array}{c l c r}{{l n S_{k}^{(n)}(\omega)=l n S_{0}+\displaystyle\sum_{i=1}^{k}\left[\displaystyle\frac{\mu}{n}+\displaystyle\frac{\sigma Z_{i}(\omega)}{\sqrt{n}}-\displaystyle\frac{1}{2}\bigg(\displaystyle\frac{\mu}{n}+\displaystyle\frac{\sigma Z_{i}(\omega)}{\sqrt{n}}\bigg)^{2}+\displaystyle\frac{1}{3}\bigg(\displaystyle\frac{\mu}{n}+\displaystyle\frac{\sigma Z_{i}(\omega)}{\sqrt{n}}\bigg)^{3}-\cdot\right.}}\ {{\displaystyle~}}\ {{\displaystyle~=l n S_{0}+\mu\displaystyle\frac{k}{n}+\sigma\displaystyle\sum_{i=1}^{k}\displaystyle\frac{Z_{i}(\omega)}{\sqrt{n}}-\displaystyle\frac{\sigma^{2}}{2n}\displaystyle\sum_{i=1}^{k}\big(Z_{i}(\omega)\big)^{2}+e r r o r t e r m s.}}\end{array}
$$  

Since $Z_{i}(\omega)$ is always 1 or $^-1$ , then $\left(Z_{i}(\omega)\right)^{2}=1$ . So, we have:  

$$
l n S_{k}^{(n)}(\omega)=l n S_{0}+(\mu-\frac{\sigma^{2}}{2})\frac{k}{n}+\sigma\sum_{i=1}^{k}\frac{Z_{i}(\omega)}{\sqrt{n}}+e r r o r t e r m s.
$$  

Similar to the derivation of Brownian motion from the discrete model, pick a particular time $t$ on the continuous time axis. Choose the integer $k$ so that $k/n\leq t$ and $k/n$ best approximates t. As before, $\left|k/n-t\right|\leq1/n$ and so $k/n\to t$ as $n\to\infty$ . It is also not hard to show that the error. terms are bounded by $C(t,\mu,\sigma)/\sqrt{n}$ where $C(t,\mu,\sigma)$ is a value independent of $n$ . Thus, the error  

terms approach O as $n\to\infty$ . We showed in the derivation of Brownian motion from the discrete model that D- converges to $Z_{t}\left(\upomega\right)$ where $Z_{t}$ is standard Brownian motion. These observations show $l n S_{k}^{(n)}(\omega)$ converges toe  

$$
l n S_{0}+\left(\mu-\frac{\sigma^{2}}{2}\right)t+\sigma Z_{t}(\omega)
$$  

as $n\to\infty$ . Exponentiating, we have $S_{k}^{(n)}(\omega)$ converges to  

$$
S_{0}e^{\left(\mu-\frac{\sigma^{2}}{2}\right)t+\sigma Z_{t}(\omega)}.
$$  

Let's label this resulting continuous stochastic process as $S_{t}(\upomega)$ . Since this result holds for all. possible histories $\mathbf{\rho}_{\omega}$ in the sample space, then  

$$
S_{t}=S_{0}e^{\left(\mu-\frac{\sigma^{2}}{2}\right)t+\sigma Z_{t}}.
$$  

# Verification of the Tower Property  

First, we state the Tower Property: Suppose $X_{t}$ is a stochastic process with an adapted filtration $\{\mathcal{F}_{t}\}.I f s{\le}t,$ then for any $T\geq t,$ we have  

$$
E[E[X_{T}|\mathcal{F}_{t}]|\mathcal{F}_{s}]=E[X_{T}|\mathcal{F}_{s}].
$$  

To verify this property for the case that the filtrations are finite, consider the following more general theorem. Suppose $\mathcal{G}$ and $\mathcal{F}$ are $\upsigma$ -algebras with $\mathcal{G}\subseteq\mathcal{F}$ , and $X$ is a random variable with respect to the o - algebra with. $\mathcal{F}$ . Then, the following expectation result holds:.  

$$
E[X|{\mathcal{G}}]=E[E[X|{\mathcal{F}}]|{\mathcal{G}}].
$$  

Observe that the tower property follows from this result by choosing $\mathcal{G}=\mathcal{F}_{s}$ and $\mathcal{F}=\mathcal{F}_{t}$ We are going to prove this more general statement for the case that the $\upsigma$ -algebras are finite.  

To interpret the expectation equation immediately above, notice that the o - algebra $\mathcal{F}$ is a "finer"'  -- algebra than. $\mathcal{G}$ , since it contains all of the measurable sets that are in $\mathcal{G}$ . Although a. proof is provided below, this result is understandable intuitively. Roughly speaking, the equation states that if one averages a random variable conditioned on the finer subdivision $\mathcal{F}$ and then averages these averages conditioned on the coarser subdivision $\mathcal{G}$ , one gets the same average as conditioning on the coarser subdivision $\mathcal{G}$ alone.  

Verification of the theorem: Since we are assuming the $\upsigma$ -algebra $\mathcal{G}$ is finite, then $\mathcal{G}$ consists of a finite number of disjoint sets $G_{1},G_{2},...,G_{\mathrm{n}}$ and all of the possible unions of these  

# Chapter 5 Additional Readings  

sets. Since $\mathcal{G}\subseteq\mathcal{F}$ and $\mathcal{F}$ is finite, then we can further decompose each set $G_{\mathrm{i}}$ into disjoint sets $F_{\mathrm{ij}}$ for $j=1,...,n_{\mathrm{i}}$ so that  

$$
G_{i}=\bigcup_{j=1}^{n_{i}}F_{i j}
$$  

and $\mathcal{F}$ consists of the sets $F_{\mathrm{ij}}$ and all of the possible unions of these sets. To find $E[X|{\mathcal{G}}]$ means to calculate $E[X|G_{\mathrm{i}}]$ for each $i.$ Suppose $p(x)$ denotes the probability that the random variable $X=x$ Then, by definition,  

$$
E[X|G_{i}]={\frac{\sum_{x\in G_{i}}x p(x)}{\sum_{x\in G_{i}}p(x)}}.
$$  

To find $E[X|{\mathcal{F}}]$ means to calculate $E[X|F_{\mathrm{ij}}]$ for each $i$ and $j.$ By definition,  

$$
E\big[X\big|F_{i j}\big]=\frac{\sum_{x\in F_{i j}}x p(x)}{\sum_{x\in F_{i j}}p(x)}.
$$  

To find $E[E[X|\mathcal{F}]|\mathcal{G}]$ means to calculate $E[E[X|\mathcal{F}]|G_{i}]$ for each i $.E[X|{\mathcal{F}}]$ is a random variable that takes on the values $E[X|F_{\mathrm{ij}}]$ with probability $\textstyle\sum_{x\in F_{i j}}p(x)$ . Thus:  

$$
E[E[X|\mathcal{F}]|G_{i}]=\frac{\sum_{j=1}^{n_{i}}E\big[X\big|F_{i j}\big](\sum_{x\in F_{i j}}p(x))}{\sum_{x\in G_{i}}p(x)}
$$  

$$
=\frac{\sum_{j=1}^{n_{i}}\left[\cfrac{\sum_{\boldsymbol{x}\in F_{i j}}x p(\boldsymbol{x})}{\sum_{\boldsymbol{x}\in F_{i j}}p(\boldsymbol{x})}\right](\sum_{\boldsymbol{x}\in F_{i j}}p(\boldsymbol{x}))}{\sum_{\boldsymbol{x}\in G_{i}}p(\boldsymbol{x})}=\frac{\sum_{j=1}^{n_{i}}\sum_{\boldsymbol{x}\in F_{i j}}x p(\boldsymbol{x})}{\sum_{\boldsymbol{x}\in G_{i}}p(\boldsymbol{x})}
$$  

Since the sets $F_{\mathrm{ij}}$ are disjoint from one another and $\begin{array}{r}{\cup_{j=1}^{n_{i}}F_{i j}=G_{i}}\end{array}$ then  

$$
\sum_{j=1}^{n_{i}}\sum_{x\in F_{i j}}x p(x)=\sum_{x\in G_{i}}x p(x).
$$  

We conclude that  

$$
E[E[X|{\mathcal{F}}]|{\mathcal{G}}]={\frac{\sum_{x\in G_{i}}x p(x)}{\sum_{x\in G_{i}}p(x)}}=E[X|G_{i}]
$$  

as we wished to prove.  