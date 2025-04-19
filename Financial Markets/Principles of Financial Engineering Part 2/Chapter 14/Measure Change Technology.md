---
tags:
  - arbitrage
  - forward_rates
  - libor
  - martingale
  - measure_change
aliases:
  - MCT
  - Measure Change Technology
key_concepts:
  - Gaussian volatility structure
  - LIBOR forward loan
  - Martingale under measure
  - discrete state setting
  - forward rate arbitrage
---

# 14.5 MEASURE CHANGE TECHNOLOGY  

We introduce a relatively general framework and then apply the results to the simple example shown previously. Basically, we need three previously developed relationships. We let $t_{i}$ obey  

$$
t_{0}<t_{1}<\cdots<t_{n}=T
$$  

with  

$$
t_{i}-t_{i-1}=\delta
$$  

denote settlement dates of some basic interest rate swap structure and limit our attention to forward rates for successive forward loans contracted to begin at. $t_{i:}$ and paid at $t_{i+1}$ . An example is shown in Figure 14.4.  

# Result 1  

The forward rate at time $t$ for a LIBOR-based forward loan that starts at time $t_{i}$ and ends at time $t_{i}+\delta$ , denoted by $F(t,t_{i})$ , admits the following arbitrage relationship:  

$$
1+F(t,t_{i})\delta=\frac{B(t,t_{i})}{B(t,t_{i+1})}\quad t<t_{i}
$$  

where, as usual, $B(t,t_{i})$ and $B(t,t_{i+1})$ are the time $t$ prices of default-free zero-coupon bonds that mature at times $t_{\mathrm{i}}$ and $t_{i+1}$ , respectively.  

The left side of this equality is a gross forward return. The right side, on the other hand, is a traded asset price, $B(t,t_{i})$ , normalized by another asset price,. $B(t,t_{i+1})$ . Hence, the ratio will be. a Martingale under a proper measure--here, the forward measure denoted by. $\tilde{P}^{t_{i+1}}$  

Result 2  

In a discrete state setting with $k$ states of the world, assuming that all asset prices are arbitrage free, and that the time $t_{i}$ state prices $Q^{j},j=1,...,k_{\:}$ with $0<Q^{j}$ exist, the time $t_{i}$ values of the forward measure $\tilde{P}^{t_{i}}$ are given by23  

$$
\tilde{p}_{1}^{t_{i}}=\frac{1}{B(t,t_{i})}Q^{1},\tilde{p}_{2}^{t_{i}}=\frac{1}{B(t,t_{i})}Q^{2},\cdots,\tilde{p}_{k}^{t_{i}}=\frac{1}{B(t,t_{i})}Q^{k}
$$  

These probabilities satisfy:  

$$
\tilde{p}_{1}^{t_{i}}+\tilde{p}_{2}^{t_{i}}+\cdots+\tilde{p}_{k}^{t_{i}}=1
$$  

and  

$$
0<\tilde{p}_{j}^{t_{i}}\quad\forall j
$$  

Note that the proportionality factors used to convert $Q^{j}$ into $\tilde{p}_{j}^{t_{i}}$ are equal across $j$  

Result 3  

In the same setting, the time $t_{i}$ probabilities associated with the $t_{i+1}$ forward measure $\tilde{P}^{t_{i+1}}$ are given by  

$$
\tilde{p}_{1}^{t_{i+1}}=\frac{B(t_{i},t_{i+1})^{1}}{B(t,t_{i+1})}Q^{1},\tilde{p}_{2}^{t_{i+1}}=\frac{B(t_{i},t_{i+1})^{2}}{B(t,t_{i+1})}Q^{2},...,\tilde{p}_{k}^{t_{i+1}}=\frac{B(t_{i},t_{i+1})^{k}}{B(t,t_{i+1})}Q^{k}
$$  

where the $B(t_{i},t_{i+1})^{j}$ are the state-dependent values of the $t_{i+1}$ -maturity bond at time $t_{i}$ .Here, the bond that matures at time $t_{i+1}$ is used to normalize the cash flows for time $t_{i}$ . Since the maturity date is $t_{i+1}$ , the $B(t_{i},t_{i+1})^{j}$ are not constant at $t_{i}$ The factors used to convert $\{Q^{j}\}$ into P'rl cease to be constant as well.  

We use these results in discussing the mechanics of measure changes. Suppose we need to price. an instrument whose value depends on two forward LIBOR processes,. $F(t,t_{i})$ and $F(t,t_{i+1})$ , simultaneously. We know that each process is a Martingale and obeys an SDE with zero drift under its own forward measure.  

Consider a one-factor setting, where a single Wiener process causes fluctuations in the two forward rates. Suppose that in this setting, starting from time $t$ with $t<t_{i},i=1,...,n,a$ small time interval denoted by $h$ passes with $t+h<t_{i}$ By imposing a Gaussian volatility structure, we can write down the individual discretized arbitrage-free dynamics for two successive forward rates $F\left(t,t_{i}\right)$ and $F(t,t_{i+1})$ as  

$$
\begin{array}{r}{F(t+h,t_{i})-F(t,t_{i})=\sigma^{i}F(t,t_{i})\Delta W_{t+h}^{1}}\end{array}
$$  

and  

$$
F(t+h,t_{i+1})-F(t,t_{i+1})=\sigma^{i+1}F(t,t_{i+1})\Delta W_{t+h}^{2}
$$  

Changes in these forward rates have zero mean under their own forward measure and, hence, are written with zero drift. This means that the unique real-world Wiener process. $W_{t+h}$ is now denoted by $\Delta W_{t+h}^{1}$ and $\Delta W_{t+h}^{2}$ in the two equations. These are normally distributed, with mean zero and. variance $h$ only under their own forward measures, $\tilde{P}^{t_{i+1}}$ and $\tilde{P}^{t_{i+2}}$  

The superscript ine $W_{t+h}^{1}$ and $W_{t+h}^{2}$ expresses the $t_{i+1}$ and $t_{i+2}$ forward probability measures, respectively.24 Finally, note how we simplify the characterization of volatilities and assume that they are constant over time.  

The individual Martingale dynamics are very convenient from a financial engineering point of. view. The respective drift components are zero and, hence, they need not be modeled during pricing. The only major task of the market practitioner is to get the respective volatilities $\sigma^{i}$ and $\bar{\sigma}^{i+1}$  

However, some securities' prices may depend on more than one forward rate in a nonlinear fash-. ion and their value may have to be calculated as an expectation under one single measure. For example, suppose a security's price,. $S_{t}$ , depends on $F(t,t_{i})$ and $F(t,t_{i+1})$ through a pricing relation such as:  

$$
S_{t}=E_{t}^{\tilde{P}}[g(F(t,t_{i}),F(t,t_{i+1}))]
$$  

where $g(.)$ is a known nonlinear function. Then, the expectation has to be calculated under one measure only. This probability can be either the time. $t_{i+1}$ or the time $t_{i+2}$ forward measure. We then have to choose a forward rate equation with Martingale dynamics and carry out a mean correction to get the correct arbitrage-free dynamics for the other. The forward measure of one of the Martingale relationships is set as the working probability distribution, and the other equation(s) is obtained in terms of this unique probability by going through successive measure changes. We discuss this in detail below.  

# 14.5.1 THE MECHANICS OF MEASURE CHANGES  

We have the following expectations concerning $\Delta W_{t+h}^{1}$ and $\Delta W_{t+h}^{2}$ , defined in Eqs. (14.109) and (14.110)  

$$
\begin{array}{r}{E_{t}^{\tilde{P}^{I_{i+1}}}[\Delta W_{t+h}^{1}]=0}\ {E_{t}^{\tilde{P}^{I_{i+2}}}[\Delta W_{t+h}^{2}]=0}\end{array}
$$  

Under their own forward measure, each Wiener increment has zero expectation. If we select $\tilde{P}^{t_{i+2}}$ as our working measure, one of these equalities has to change. We would have25  

$$
\begin{array}{r}{E_{t}^{\tilde{P}^{t_{i+2}}}[\Delta W_{t+h}^{1}]=\lambda_{t}h}\ {E_{t}^{\tilde{P}^{t_{i+2}}}[\Delta W_{t+h}^{2}]=0}\end{array}
$$  

The value of $\lambda_{t}$ gives the correction factor that we need to use in order to obtain the correct arbitrage-free dynamics, if the working measure is $\tilde{P}^{t_{i+2}}$ . Calculating this factor implies that we can change measures in the dynamics of $F(t,t_{i})$  

We start with the original expectation:  

$$
E_{t}^{\tilde{P}^{t_{i+1}}}[\Delta W_{t+h}^{1}]=\sum_{j=1}^{k}\Delta W_{t+h}^{1j}\tilde{p}_{j}^{t_{i+1}}=0
$$  

where $\tilde{p}_{j}^{t_{i}+1}$ are the probabilities associated with the individual states $j=1,...,k$ Now, using the identity,  

$$
\frac{B(t,t_{i+2})B(t_{i},t_{i+2})^{j}}{B(t,t_{i+2})B(t_{i},t_{i+2})^{j}}\equiv1
$$  

we rewrite the expectation as  

$$
E_{t}^{\tilde{P}_{t+1}^{t_{i+1}}}\left[\Delta W_{t+h}^{1}\right]=\sum_{j=1}^{k}\Delta W_{t+h}^{1j}\frac{B(t,t_{i+2})B(t_{i},t_{i+2})^{j}}{B(t,t_{i+2})B(t_{i},t_{i+2})^{j}}\equiv\tilde{p}_{j}^{t_{i+1}}
$$  

We regroup and use the definition of the $t_{\mathrm{i}+1}$ and $t_{\mathrm{i}+2}$ forward measures as implied by Result 3  

$$
\tilde{p}_{j}^{t_{i+1}}=\frac{B(t_{i},t_{i+1})^{j}}{B(t,t_{i+1})}Q^{j}
$$  

and  

$$
\tilde{p}_{j}^{t_{i+2}}=\frac{B(t_{i},t_{i+2})^{j}}{B(t,t_{i+2})}Q^{j}
$$  

Rescaling the $Q^{j}$ using appropriate factors, Eq. (14.118) becomes  

$$
\sum_{j=1}^{k}(\Delta W_{t+h}^{1j})\left[\frac{B(t,t_{i+2})B(t_{i},t_{i+1})^{j}}{B(t,t_{i+1})B(t_{i},t_{i+2})^{j}}\right]\tilde{p}_{j}^{t_{i+2}}=0
$$  

Note that the probabilities switch as the factors that were applied to the $Q^{j}$ changed. The superscript in $W_{t+h}^{1}$ does not change.  

The next step in the derivation is to try to \*recognize' the elements in this expectation. Using Result 1, we recognize the equality  

$$
1+\delta F(t_{i},t_{i+1})^{j}=\frac{B(t_{i},t_{i+1})^{j}}{B(t_{i},t_{i+2})^{j}}
$$  

Replacing, eliminating the. $j\mathrm{\cdot}$ -independent terms, and rearranging gives  

$$
\sum_{j=1}^{k}(\Delta W_{t+h}^{1j})(1+\delta F(t_{i},t_{i+1})^{j})\tilde{p}_{j}^{t_{i+2}}=0
$$  

Now, multiplying through, this leads to  

$$
\sum_{j=1}^{k}(\Delta W_{t+h}^{1j})\tilde{p}_{j}^{t_{i+2}}=-\left(\sum_{j=1}^{k}(\Delta W_{t+h}^{1j})F(t_{i},t_{i+1})^{j}\tilde{p}_{j}^{t_{i+2}}\right)\delta
$$  

We can write this using the conditional expectation operator,  

$$
E_{t}^{\tilde{p}^{t_{1+2}}}[\Delta W_{t+h}^{1}]=-E_{t}^{\tilde{p}^{t_{1+2}}}[\Delta W_{t+h}^{1}F(t_{i},t_{i+1})]\delta.
$$  

In the last expression, the left-hand side is the desired expectation of the $\Delta W_{t+h}^{1}$ under the new probability $\tilde{P}^{t_{i+2}}$ . This expectation will not equal zero if the right-hand-side random variables are. correlated. This correlation is nonzero as long as forward rates are correlated. To evaluate the mean of $\Delta W_{t+h}^{1}$ under the new probability $\tilde{P}^{t_{i+2}}$ , we then have to calculate the covariance.  

Let the covariance be given by $-\lambda_{t}h$ . We have,  

$$
\delta E_{t}^{\tilde{p}^{t_{i+2}}}[\Delta W_{t+h}^{1}F(t_{i},t_{i+1})]=-\lambda_{t}h
$$  

Using $\lambda_{t}$ we can switch probabilities in the $F(t,t_{i})$ dynamics. We start with the original Martingale dynamics:  

$$
\begin{array}{r}{F(t+h,t_{i})=F(t,t_{i})+\sigma^{i}F(t,t_{i})\Delta W_{t+h}^{1}}\end{array}
$$  

Switch by adding and subtracting $\sigma^{i}F(t,t_{i})\lambda_{t}h$ to the right-hand side and regroup:  

$$
F(t+h,t_{i})=F(t,t_{i})-\sigma^{i}F(t,t_{i})\lambda_{t}h+\sigma^{i}F(t,t_{i})[\lambda_{t}h+\Delta W_{t+h}^{1}]
$$  

Let  

$$
\Delta W_{t+h}^{2}=[\lambda_{t}h+\Delta W_{t+h}^{1}]
$$  

We have just shown that the expectation of the right-hand side of this expression equals zero under $\tilde{P}^{t_{i+2}}$ . So, under the $\tilde{P}^{t_{i+2}}$ we can write the new dynamics of the $F(t,t_{i})$ as  

$$
F(t+h,t_{i})=F(t,t_{i})-\sigma^{i}F(t,t_{i})\lambda_{t}h+\sigma^{i}F(t,t_{i})\Delta W_{t+h}^{2}
$$  

As can be seen from this expression, the new dynamics have a non-zero drift and $F(t,t_{i})$ is not a Martingale under the new measure. Yet, this process is arbitrage free and easy to exploit in Monte Carlo type approaches. Since both dynamics are expressed under the same measure, the set of equations that describe the dynamics of the two forward rates can be used in pricing instruments that depend on these forward rates. The same pseudo-random numbers can be used in the two SDEs. Finally, the reader should remember that the discussion in this section depends on the discrete approximation of the SDEs.  

# 14.5.2 GENERALIZATION  

A generalization of the previous heuristic discussion leads to the Forward LIBOR Model. Suppose the setting involves $n$ forward rates, $F(t_{0},t_{i}),i=0,...,n-1$ , that apply to loans which begin at time $t_{i:}$ and end at $t_{i+1}=t_{i}+\delta$ . The $\boldsymbol{F}(t_{0},t_{0})$ is the trivial forward rate and is the spot LIBOR with tenor $\delta$ . The terminal date is $t_{n}$  

Similar to the discussion in the previous section, assume that there is a single factor.26 Using the $t_{i+1}$ forward measure we obtain arbitrage-free Martingale dynamics for each forward rate $F(t,t_{i})$  

$$
\mathrm{d}F(t,t_{i})=\sigma^{i}F(t,t_{i})W_{t}^{i+1}\quad t\in[0,\infty)
$$  

The superscript in $W_{t}^{i+1}$ implies that27  

$$
E_{t}^{\tilde{P}^{t_{i+1}}}[d W_{t}^{i+1}]=0
$$  

These arbitrage-free dynamics are very useful since they do not involve any interest rate modeling. and are dependent only on the correct specification of the respective volatilities. However, when  

more than one forward rate determines a security's payoff in a nonlinear fashion, the process may have to be written under a unique working measure..  

Suppose we chose $\tilde{P}^{t_{n}}$ as the working measure.28 The heuristic approach discussed in the previous section can be generalized to obtain the following arbitrage-free system of SDEs that involve recursive drift corrections in a one-factor case:  

$$
\mathrm{d}F(t,t_{i})=-\left[\sigma^{i}F(t,t_{i})\sum_{j=i}^{n-1}\frac{\delta\sigma^{j}F(t,t_{j})}{1+F(t,t_{j})\delta}\right]\mathrm{d}t+\sigma^{i}F\big[(t,t_{i})\mathrm{d}W_{t}^{t_{n}}\quad t\in[0,\infty)\mathrm{~}
$$  

where superscript in. $\mathrm{d}W_{t}^{t_{n}}$ indicates that the working measure is. $\tilde{P}^{t_{n}}$ . The equations in this system. are expressed under this forward measure for $i=1$ ... $n$ .Yet, only the last equation has Martingale dynamics  

$$
\mathrm{d}F(t,t_{n-1})=\sigma^{n-1}F(t,t_{n-1})\mathrm{d}W_{t}^{t_{n}}\quad t\in[0,\infty)
$$  

All other SDEs involve successive correction factors given by the first term on the right side. It is important to realize that all terms in these factors can be observed at time $t.$ The dynamics do not need a modeling of actual drifts..  
