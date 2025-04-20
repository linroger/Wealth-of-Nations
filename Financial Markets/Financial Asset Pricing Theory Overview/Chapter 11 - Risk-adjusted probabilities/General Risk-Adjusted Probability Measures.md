---
tags:
  - derivative_pricing
  - girsanov_theorem
  - martingale
  - numeraire
  - risk_adjusted_probability
aliases:
  - General Risk-Adjusted Probability
  - Risk-Adjusted Measures
key_concepts:
  - Law of Iterated Expectations
  - Pricing condition and martingale
  - Radon-Nikodym derivative
  - Risk-neutral probability measure
  - Zero-coupon bond as numeraire
---

# 11.5 General risk-adjusted probability measures  

Consider an asset with a single dividend payment of $D_{s}$ at time $s$ . Using the risk-neutral probability measure $\mathbb{Q}$ the price at time $t<s$ of this asset is  

$$
P_{t}=\mathrm{E}_{t}^{\mathbb{Q}}\left[\left(R_{t,s}^{f}\right)^{-1}D_{s}\right].
$$  

If we invest $^{1}$ in the bank account at time. $0$ and roll-over at the short-term interest rate, the value at time $t$ will be $P_{t}^{f}=R_{0,t}^{f}$ . We can think of $P^{f}=(P_{t}^{f})$ as the price process of the bank account.. Since $R_{t,s}^{f}=R_{0,s}^{f}/R_{0,t}^{f}=P_{s}^{f}/P_{t}^{f}$ , we can rewrite the above equation as  

$$
{\frac{P_{t}}{P_{t}^{f}}}=\mathrm{E}_{t}^{\mathbb{Q}}\left[{\frac{D_{s}}{P_{s}^{f}}}\right].
$$  

Both the current price and the future dividend of the asset is measured relative to the price of the bank account, i.e. the bank account is used as the numeraire. By the Law of Iterated Expectations (Theorem 2.1),  

$$
\frac{P_{t}}{P_{t}^{f}}=\mathrm{E}_{t}^{\mathbb{Q}}\left[\mathrm{E}_{t^{\prime}}^{\mathbb{Q}}\left[\frac{D_{s}}{P_{s}^{f}}\right]\right]=\mathrm{E}_{t}^{\mathbb{Q}}\left[\frac{P_{t^{\prime}}}{P_{t^{\prime}}^{f}}\right],\quad t<t^{\prime}\leq s,
$$  

so the relative price process $(P_{t}/P_{t}^{f})$ is a $\mathbb{Q}$ -martingale.  

Valuation with the forward measure for maturity $s$ uses the zero-coupon bond maturing at $s$ as the numeraire. The price of the bond $B_{t}^{s}$ converges to its face value of $^{1}$ as $t\rightarrow s$ .If we let $B_{s}^{s}=1$ denote the cum-dividend price of the bond at maturity, the price $P_{t}$ of the asset paying $D_{s}$ at time $s>t$ will satisfy  

$$
{\frac{P_{t}}{B_{t}^{s}}}=\mathrm{E}_{t}^{\mathbb{Q}^{s}}\left[{\frac{D_{s}}{B_{s}^{s}}}\right]
$$  

from which it is clear that the zero-coupon bond is used as a numeraire. The relative price process $(P_{t}/B_{t}^{s})$ is a $\mathbb{Q}^{s}$ martingale.  

In fact we can use any asset or trading strategy having a strictly positive price process as the. numeraire and find an equivalent probability measure under which the relative price processes are martingales. Let $\pmb{\theta}$ be a trading strategy with associated value process $V^{\theta}=(V_{t}^{\theta})_{t\in\mathcal{T}}$ (see Chapter 3 for the precise definition) so that. $V_{t}^{\pmb{\theta}}>0$ with probability 1 for all $t\in\mathcal{T}$ . Then $\mathbb{Q}^{\theta}$ is said to be a risk-adjusted measure for $\pmb{\theta}$ if  

(i) $\mathbb{P}$ and $\mathbb{Q}^{\theta}$ are equivalent;  

(ii) the Radon-Nikodym derivative do has finite variance;.  

(iii) the time. $t$ price of an asset paying a dividend of $D_{s}$ at time $s>t$ is  

$$
P_{t}=V_{t}^{\theta}\operatorname{E}_{t}^{\mathbb{Q}^{\theta}}\left[{\frac{D_{s}}{V_{s}^{\theta}}}\right].
$$  

Clearly, the pricing condition (11.30) can be rewritten as  

$$
\frac{P_{t}}{V_{t}^{\theta}}=\mathrm{E}_{t}^{\mathbb{Q}^{\theta}}\left[\frac{D_{s}}{V_{s}^{\theta}}\right],
$$  

and the relative price process. $(P_{t}/V_{t}^{\pmb{\theta}})$ is a $\mathbb{Q}^{\theta}$ -martingale. If the trading strategy. $\pmb{\theta}$ is self-financing, its gross return between $t$ and $s$ will be. $R_{t,s}^{\theta}=V_{s}^{\theta}/V_{t}^{\theta}$ so that the pricing condition can also be written as.  

$$
P_{t}=\mathrm{E}_{t}^{\mathbb{Q}^{\theta}}\left[\left(R_{t,s}^{\theta}\right)^{-1}D_{s}\right].
$$  

For a full discrete dividend process $D_{i}=(D_{i t})_{t=1,2,...,T}$ , the price will be.  

$$
P_{i t}=V_{t}^{\theta}\operatorname{E}_{t}^{\mathbb{Q}^{\theta}}\left[\sum_{s=t+1}^{T}{\frac{D_{i s}}{V_{s}^{\theta}}}\right].
$$  

Comparing the pricing expressions involving expectations under $\mathbb{P}$ and $\mathbb{Q}^{\theta}$ , we see that the. Radon-Nikodym derivative do is linked to a state-price deflator through the relations.  

$$
\zeta_{t}=\frac{V_{0}^{\theta}}{V_{t}^{\theta}}\operatorname{E}_{t}\left[\frac{d\mathbb{Q}^{\theta}}{d\mathbb{P}}\right],\quad\frac{d\mathbb{Q}^{\theta}}{d\mathbb{P}}=\zeta_{T}\frac{V_{T}^{\theta}}{V_{0}^{\theta}}.
$$  

Now take a continuous-time framework and write the real-world dynamics of the value of the numeraire as  

$$
d V_{t}^{\theta}=V_{t}^{\theta}\left[\left(r_{t}^{f}+\left(\pmb{\sigma}_{t}^{\theta}\right)^{\top}\pmb{\lambda}_{t}\right)d t+\left(\pmb{\sigma}_{t}^{\theta}\right)^{\top}d z_{t}\right],
$$  

which implies that  

$$
\frac{V_{T}^{\theta}}{V_{0}^{\theta}}=\exp\{\int_{0}^{T}\left(r_{t}^{f}+\left(\sigma_{t}^{\theta}\right)^{\top}\lambda_{t}-\frac{1}{2}\|\sigma_{t}^{\theta}\|^{2}\right)d t+\int_{0}^{T}\left(\sigma_{t}^{\theta}\right)^{\top}d z_{t}\}.
$$  

Hence,  

$$
\frac{d\mathbb{Q}^{\theta}}{d\mathbb{P}}=\zeta_{T}\frac{V_{T}^{\theta}}{V_{0}^{\theta}}=\exp\{-\frac{1}{2}\int_{0}^{T}\|\lambda_{t}-\pmb{\sigma}_{t}^{\theta}\|^{2}d t-\int_{0}^{T}\left(\lambda_{t}-\pmb{\sigma}_{t}^{\theta}\right)^{\top}d z_{t}\},
$$  

and it follows from the Girsanov Theorem that the process $z^{\theta}$ defined by  

$$
d z_{t}^{\theta}=d z_{t}+\left(\lambda_{t}-\sigma_{t}^{\theta}\right)d t
$$  

is a standard Brownian motion under the measure $\mathbb{Q}^{\theta}$ . The dynamics of any processe $X=(X_{t})_{t\in[0,T]}$ is transformed via.  

$$
d X_{t}=\mu_{X t}d t+\pmb{\sigma}_{X t}^{\top}d z_{t}=\left(\mu_{X t}-\pmb{\sigma}_{X t}^{\top}\left(\lambda_{t}-\pmb{\sigma}_{t}^{\theta}\right)\right)d t+\pmb{\sigma}_{X t}^{\top}d z_{t}^{\theta}
$$  

and for a price process the analogue is  

$$
d P_{i t}=P_{i t}\left[\mu_{i t}d t+\pmb{\sigma}_{i t}^{\top}d z_{t}\right]=P_{i t}\left[\left(r_{t}^{f}-\delta_{i t}+\pmb{\sigma}_{i t}^{\top}\pmb{\sigma}_{t}^{\theta}\right)d t+\sigma_{i t}^{\top}d z_{t}^{\theta}\right].
$$  

In particular for the numeraire itself,  

$$
d V_{t}^{\theta}=V_{t}^{\theta}\left[\left(r_{t}^{f}+\Vert\sigma_{t}^{\theta}\Vert^{2}\right)d t+\left(\sigma_{t}^{\theta}\right)^{\top}d z_{t}^{\theta}\right].
$$  

Risk-adjusted probability measures are often used in the pricing of derivatives. If the payoff of. the derivative is fully determined by some underlying asset, it is sometimes helpful to express the price of the derivative using the risk-adjusted probability measure with the underlying asset as the numeraire. Some examples will be given in Chapter 12..  
