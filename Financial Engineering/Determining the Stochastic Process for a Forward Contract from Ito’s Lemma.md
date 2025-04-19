---
tags:
  - arbitrage_free_pricing
  - forward_contract
  - geometric_brownian_motion
  - ito_lemma
  - stochastic_process
aliases:
  - Forward Price Dynamics
  - Ito's Lemma
key_concepts:
  - Arbitrage-free price
  - Drift rate comparison
  - Forward contract price
  - Geometric Brownian Motion (GBM)
  - Ito's Lemma expansion
---

# Determining the Stochastic Process for a Forward Contract from Ito’s Lemma 

Let $F=F(S,t)$ . Note that $F$ is once differentiable in $t$ and twice differentiable in $S$ . Ito's Lemma justifies the use of the following Taylor-series-like expansion for the instantaneous change in $F$ : 

$$ d F=\frac{\partial F}{\partial t}d t+\frac{\partial F}{\partial S}d S+\frac{1}{2}\frac{\partial^{2}F}{\partial S^{2}}d S^{2}. $$ 

Since $d S^{2}=S^{2}\sigma^{2}d t$ , substituting $S^{2}\sigma^{2}d t$ in place of $d S^{2}$ in the Ito's Lemma equation yields equation (2): 

$$ \frac{\partial F}{\partial t}d t+\frac{\partial F}{\partial S}d S+\frac{1}{2}\sigma^{2}S^{2}\frac{\partial^{2}F}{\partial S^{2}}d t $$ 

Since the instantaneous change in $S$ evolves according to the geometric Brownian motion (GBM) equation $d S=\mu S d t+\sigma S d z$ , substituting $\mu S d t+\sigma S d z$ in place of $d S$ in equation (2) yields: 

$$ d F=\left({\frac{\partial F}{\partial t}}+{\frac{\partial F}{\partial S}}\mu S+{\frac{1}{2}}\sigma^{2}S^{2}{\frac{\partial^{2}F}{\partial S^{2}}}\right)d t+{\frac{\partial F}{\partial S}}\sigma S d z $$ 

In equation (3), we refer to $\frac{\partial F}{\partial t}$ as “theta”, $\frac{∂F}{∂S}$ as “delta”, and $\frac{\partial^{2}{\cal F}}{\partial S^{2}}$ as “gamma”. Theta measures the effect that the passage of time has on $F$ , delta measures the sensitivity of $F$ with respect to changes in $S$ , and gamma captures the sensitivity of delta with respect to changes in $S$ . 

Next, consider a forward contract on a non-dividend paying stock; its date $t$ “arbitrage-free” price is $F=S e^{r(T-t)}$ . Since $\mathrm{theta}={\frac{\partial F}{\partial t}}=-r S e^{r(T-t)}$ , ${\mathrm{delta}}={\frac{\partial F}{\partial S}}=e^{r(T-t)}$ , and $\mathrm{{gamma}=}$ $\frac{\partial^{2}F}{\partial S^{2}}=0$ , we are now able to infer the stochastic process for the price of the forward contract by substituting the values for theta, delta and gamma into equation (3): 

$$ d F=[e^{r(T-t)}\mu S-r S e^{r(T-t)}]d t+e^{r(T-t)}\sigma S d z. $$ 

Substituting $F$ in place of $S e^{r(T-t)}$ in equation (4), we obtain 

$$ d F=(\mu-r)F d t+\sigma F d z. $$ 

Note the difference in the drift rate for the forward contract vis-a-vis the drift rate for the underlying asset. Specifically, over infinitesimal units of time, the price of the forward contract grows at the rate of $(\mu-r)d t$ , whereas the underlying asset grows at the rate of µdt. Intuitively this is not a surprising result, particularly in view of the fact that the “arbitrage-free” price $F=S e^{r(T-t)}$ represents the future (date $T$ ) value of the date $t$ value of the underlying asset, compounded forward at the riskless rate of interest.