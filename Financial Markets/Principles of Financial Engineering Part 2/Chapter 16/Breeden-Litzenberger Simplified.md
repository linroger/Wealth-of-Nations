---
tags:
  - '#arbitrage_free_pricing'
  - '#breeden_litzenberger_theorem'
  - '#butterfly_spreads'
  - '#dirac_delta_function'
  - '#european_options'
  - '#option_pricing'
  - '#option_strategies'
  - '#risk_adjusted_probabilities'
  - '#vanilla_options'
---
# 16.6 BREEDEN-LITZENBERGER SIMPLIFIED  

The so-called Breeden-Litzenberger Theorem is an important result that shows how one can back out risk-adjusted probabilities from liquid arbitrage-free option prices. In this section, we discuss a trader's approach to Breeden--Litzenberger. This approach will show the theoretical relevance of some popular option strategies used in practice. Below, we use a simplified framework which could be generalized in a straightforward way. However, we will not generalize these results, but instead in the following section use the dirac delta approach to prove the Breeden-Litzenberger theorem.  

Consider a simple setting where we observe prices of four liquid European call options, denoted by $\{C_{t}^{1},...,C_{t}^{4}\}$ . The options all expire at time $T$ with $t<T.$ The options have strike prices denoted by $\{\dot{K^{1}}<...\dot{<}K^{4}\}$ with  

$$
\boldsymbol{K}^{i}-\boldsymbol{K}^{i-1}=\Delta\boldsymbol{K}
$$  

Hence, the strike prices are equally spaced. Apart from the assumption that these options are written on the same underlying. $S_{t}$ which does not pay dividends, we make no distributional assumption about $S_{t}$ In fact the volatility of. $S_{t}$ can be stochastic and the distribution is not necessarily log. normal.  

Finally we use the LIBOR rate $L_{t}$ to discount cash flows to be received at time $T.$ The discoun1 factor will then be given by  

$$
\frac{1}{(1+L_{t}\delta)}
$$  

Next we define a simple probability space. We assume that the strike prices define the four states of the world where $S_{T}$ can end up. Hence the state space is discrete and is assumed to be made of only four states $\{\omega^{1},...,\omega^{4}\}$  

$$
\omega^{i}=K^{i}
$$  

We then have four risk-adjusted probabilities associated with these states defined as follows  

$$
\begin{array}{l c r}{{p^{1}=P(S_{T}=K^{1})}}\ {{}}\ {{p^{2}=P(S_{T}=K^{2})}}\ {{}}\ {{p^{3}=P(S_{T}=K^{3})}}\ {{}}\ {{p^{4}=P(S_{T}=K^{4})}}\end{array}
$$  

The arbitrage-free pricing of Chapter 11 can be applied to these vanilla options:  

$$
C_{t}^{i}=\frac{1}{(1+L_{t}\delta)}E_{t}^{\tilde{P}}\big[(S_{T}-K,0)^{+}\big]
$$  

The straightforward application of this formula using the probabilities $p^{i}$ gives the following pricing equations, where possible payoffs are weighed by the corresponding probabilities (Figure 16.8).  

![](c1622e45733dae0d0bfcbded242bd8fc6de3be2cbfdb742e5a2fddb038f7129a.jpg)  

# FIGURE 16.8  

Payoff diagrams for puts and calls with different moneyness.  

$$
C_{t}^{1}=\frac{1}{(1+L_{t}\delta)}\left[p^{2}\Delta K+p^{3}(2\Delta K)+p^{4}(3\Delta K)\right]
$$  

$$
C_{t}^{2}=\frac{1}{(1+L_{t}\delta)}\left[p^{3}(\Delta K)+p^{4}(2\Delta K)\right]
$$  

$$
C_{t}^{3}=\frac{1}{(1+L_{t}\delta)}\left[p^{4}(\Delta K)\right]
$$  

Next we calculate the first differences of these option prices.  

$$
C_{t}^{1}-C_{t}^{2}=\frac1{(1+L_{t}\delta)}\left[p^{2}\Delta K+p^{3}(\Delta K)+p^{4}(\Delta K)\right]
$$  

$$
C_{t}^{2}-C_{t}^{3}=\frac1{(1+L_{t}\delta)}\left[p^{3}(\Delta K)+p^{4}(\Delta K)\right]
$$  

Finally, we calculate the second difference and obtain the following interesting result:  

$$
(C_{t}^{1}-C_{t}^{2})-(C_{t}^{2}-C_{t}^{3})=\frac1{(1+L_{t}\delta)}p^{2}\Delta K
$$  

Divide by $\Delta K$ twice to obtain  

$$
\frac{\Delta^{2}C}{\Delta K^{2}}=\frac{1}{(1+L_{t}\delta)\Delta K}p^{2}
$$  

where  

$$
\Delta^{2}C=(C_{t}^{1}-C_{t}^{2})-(C_{t}^{2}-C_{t}^{3})
$$  

This is the well-known Breeden-Litzenberger result in this very simple environment. It has interesting implications for the options trader.  

Note that  

$$
(C_{t}^{1}-C_{t}^{2})-(C_{t}^{2}-C_{t}^{3})=(C_{t}^{1}-C_{t}^{3})-2C_{t}^{2}
$$  

In other words, this is an option position that is long two wings and short the center twice. In fact this is a butterfly centered at $K_{2}$ . It turns out that the arbitrage-free market value of this butterfly multiplied by the $(1+L_{t}\delta)\Delta K$ gives the risk-adjusted probability that the underlying $S_{t}$ will end up at state $K_{2}$ . Letting $\Delta K\to0$ we get  

$$
\frac{{\hat{\sigma}}^{2}C}{\partial K^{2}}=\frac{1}{(1+L_{t}\delta)}\phi(S_{T}=K)
$$  

where $\phi(S_{T}=K)$ is the (conditional) risk-adjusted density of the underlying at time $T$ 6  

This discussion illustrates one reason why butterflies are traded as vanilla instruments in option markets. They yield the probability associated with their center. Below we prove the Breeden-Litzenberger result using the dirac delta function..  

# 16.6.1 THE PROOF  

The idea behind the Breeden-Litzenberger result has been discussed before. It rests on the fact that by using liquid and arbitrage-free options prices we can back out the risk-adjusted probabilities associated with various states of the world in the future. The probabilities will relate to the future values of the underlying price, $S_{T}.$  

The theorem asserts that (i) if a continuum of European vanilla option prices exists for all $0\leq K$ and (ii) if the function giving $C(S_{t},K)$ is twice differentiable with respect to $K$ , then we have  

$$
\frac{{\hat{\sigma}}^{2}C}{{\hat{\sigma}}K^{2}}=\frac{1}{(1+L_{t}\delta)}\phi(S_{T}=K)
$$  

where $\phi\big(S_{T}=K|S_{t_{0}}\big)$ is the conditional risk-adjusted density of. $S_{T}.$ In other words, if we had a con-. tinuum of vanilla option prices, we could obtain the risk-adjusted density with a straightforward differentiation. We now prove this using the dirac delta function. $\delta_{K}(S_{T})$  

Apply the twice differential operator to the definition of both sides of the arbitrage-free price $C(S_{t},K)$ . By definition, this means  

$$
\frac{\ensuremath{\hat{\sigma}}^{2}}{\ensuremath{\hat{\sigma}}K^{2}}C(S_{t},K)=\frac{1}{(1+L_{t}\delta)}\frac{\ensuremath{\hat{\sigma}}^{2}}{\ensuremath{\hat{\sigma}}K^{2}}\int\left(S_{T}-K\right)^{+}\phi(S_{T})\mathrm{d}S_{T}
$$  

Assuming that we can interchange the operators and realizing that $\phi(S_{T})$ does not depend on $K$ we obtain  

$$
\frac{\ensuremath{\hat{\sigma}}^{2}}{\ensuremath{\hat{\sigma}}K^{2}}C(S_{t},K)=\frac{1}{(1+L_{t}\delta)}\int\frac{\ensuremath{\hat{\sigma}}^{2}}{\ensuremath{\hat{\sigma}}K^{2}}(S_{T}-K)^{+}\phi(S_{T})\mathrm{d}S_{T}
$$  

But  

$$
\frac{\partial^{2}}{\partial K^{2}}(S_{T}-K)^{+}=\delta_{K}(S_{T})
$$  

is a dirac delta, which means that  

$$
\frac{\partial^{2}}{\partial K^{2}}C(S_{t},K)=\frac{1}{(1+L_{t}\delta)}\intop_{0}^{\infty}\delta_{K}(S_{T})\phi(S_{T})\mathrm{d}S_{T}
$$  

The previous discussion and Eq. (16.4) tells us that in this integral $\phi(S_{T})$ is being multiplied by. zero everywhere except for $S_{T}=K$ Thus,  

$$
{\frac{\partial^{2}}{\partial K^{2}}}C(S_{t},K)={\frac{1}{(1+L_{t}\delta)}}\phi(S_{T}=K)
$$  

To recover the risk-adjusted density just take the second partial of the European vanilla option prices with respect to $K$ .This is the Breeden-Litzenberger result.  
