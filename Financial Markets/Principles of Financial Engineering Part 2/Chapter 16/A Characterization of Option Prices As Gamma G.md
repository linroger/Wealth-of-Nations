---
tags:
  - black_scholes_pde
  - breeden_litzenberger
  - gamma_hedging
  - option_pricing
  - tanaka_formula
aliases:
  - Gamma Gains
  - Option Characterization
key_concepts:
  - Black-Scholes PDE
  - Tanaka's formula
  - gamma hedging gains
  - option pricing
  - risk-adjusted density
---

# 16.7 A CHARACTERIZATION OF OPTION PRICES AS GAMMA GAINS  

The question then is, how does a trader "characterize" an option using these hedging gains? First of all, in liquid option markets the order flow determines the price and the trader does not have to go through a pricing exercise. But still, can we use these trading gains to represent the frame of mind of an options trader?  

The discussion in the previous section provides a hint about this issue. The trader buys or sells an option with strike price $K$ The cash needed for this transaction is either borrowed or lent. Then the trader delta hedges the option. Finally, this hedge is adjusted as the underlying price fluctuates around the initial $S_{t_{0}}$  

According to this, the trader could add the (discounted) future gains (payouts) from these hedge adjustments and this would be the true time-value of the option, besides interest or other expenses. The critical point is that these future gains need to be calculated at the initial gamma, evaluated at the initial $s_{t_{0}}$ , and adjusted for passing time.  

We can explain this statement. First, for simplicity assume interest rates are equal to zero. We then let the price of the vanilla call be denoted by $C(S_{t},t)$ . Then by definition we have  

$$
C\left(S_{t_{0}},T\right)=\mathbf{M}\mathrm{ax}[S_{t_{0}}-K,0]
$$  

This will be the future value of the option if the underlying ended up at $S_{t_{0}}$ at time $T.$ Now, this value is equal to the initial price plus how much the time value has changed between $t_{0}$ and $T.$  

$$
C{\left({{S}_{t_{0}}},T\right)}=C{\left({{S}_{t_{0}}},t_{0}\right)}+\displaystyle\int_{t_{0}}^{T}{\frac{\partial C}{\partial t}\left|{{s}_{t}}={{S}_{t_{0}}}\mathrm{{d}}t\right.}
$$  

Now, we know from the Black-Scholes PDE that  

$$
\frac{\partial C}{\partial t}=\frac{1}{2}\frac{\partial^{2}C}{\partial S_{t}^{2}}\sigma_{t}^{2}(S_{t},t)
$$  

Substituting and reorganizing Eq. (16.42) above becomes  

$$
C{{\left({{S}_{t_{0}}},t_{0}\right)}}={\bf{M a x}}\left[{{S}_{t_{0}}}-K,0\right]+\displaystyle\int_{0}^{T}{\frac{1}{1}\frac{{{\partial}^{2}}C{{\left({{S}_{t_{0}}},t\right)}}}{\partial{{S}_{t}^{2}}}{{\sigma}_{t}^{2}}\left({{S}_{t_{0}}},t\right)}{\mathrm{d}t}
$$  

Note that on the right-hand side, the integral is evaluated at the constant $S_{t_{0}}$ so we don't need to. take expectations.  

According to this, the trader is valuing the option at time. $t_{0}$ by adding the intrinsic value and the gamma gains evaluated with a gamma at $S_{t_{0}}$ and a volatility centered at $S_{t_{0}}$ . Still, the time $t$ changes and this will change the gamma over time. Thus, it is important to realize that the trader is not valuing the option by looking at the expected value of the future gamma gains evaluated at random future $S_{t}$ The gamma is evaluated at the initial $S_{t_{0}}$  

# 16.7.1 RELATIONSHIP TO TANAKA'S FORMULA  

The discussion above is also consistent with the option interpretation obtained using Tanaka's formula. Consider the value of the option as shown above, again.  

$$
C\left(S_{t_{0}},t_{0}\right)={\mathrm{Max}}\left[S_{t_{0}}-K,0\right]+\displaystyle\int_{t_{0}}^{T}{\frac{\partial^{2}C\left(S_{t_{0}},t\right)}{\partial S_{t}^{2}}\sigma_{t}^{2}\left(S_{t_{0}},t\right)}{\mathrm{d}t}
$$  

Now we know from Breeden-Litzenberger that  

$$
\frac{\partial^{2}C\big(S_{t_{0}},t\big)}{\partial S_{t}^{2}}\sigma_{t}^{2}\left(S_{t_{0}},t\right)=\varPhi\left(S_{t_{0}},t|S_{t_{0}}\right)
$$  

where $\mathcal{P}\big(S_{t_{0}},t|S_{t_{0}}\big)$ is the risk-adjusted density of $S_{t}$ at time $t.$ Substituting this in the option value  

$$
C(S_{t_{0}},t_{0})=\mathbf{M}\mathrm{ax}\left[S_{t_{0}}-K,0\right]+\int_{t_{0}}^{T}\frac{1}{2}\sigma_{t}^{2}\big(S_{t_{0}},t\big)\boldsymbol{\varPhi}\big(S_{t_{0}},t|S_{t_{0}}\big)\mathrm{d}t
$$  

This is the same equation we obtained by using dirac delta functions along with the Tanaka for-. mula. The second term on the right-hand side was called local time. In this case, the local time is evaluated for the ATM option with strike $K=S_{t_{0}}$  
