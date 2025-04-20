---
tags:
  - dividend_pricing
  - forward_measure
  - risk_neutral_valuation
  - state_price_deflator
  - zero_coupon_bonds
aliases:
  - Forward martingale measure
  - Forward neutral measure
  - Forward risk-adjusted measure
key_concepts:
  - Forward risk-adjusted measure
  - Radon-Nikodym derivative
  - Risk-neutral valuation approach
  - Time price of dividend
  - Zero-coupon bond price
---

# 11.4 Forward risk-adjusted probability measures  

When valuing an asset with the risk-neutral valuation approach, we have to know the risk-neutral covariance between the risk-free discount factor $(R_{t,s}^{f})^{-1}$ and the asset dividend $D_{i s}$ . Except for simple cases, such covariances are hard to compute analytically. In this section we introduce an alternative probability measure where we do not need to deal with such covariances. The downside is that we have to use a separate probability measure for each payment date.  

# 11.4.1 Definition  

Let $s\in\mathcal T$ be a trading date and assume that zero-coupon bonds with a face value of 1 maturing at time $s$ are traded. As before, the price at time $t\leq s$ of such a bond is denoted by $B_{t}^{s}$ . A probability measure $\mathbb{Q}^{s}$ on $(\Omega,\mathcal{F}_{s})$ is then called a forward risk-adjusted probability measure (or just a forward measure) for maturity $s$ if the following conditions are satisfied:  

(i) $\mathbb{P}$ and $\mathbb{Q}^{s}$ are equivalent;   
(ii) the Radon-Nikodym derivative $\frac{d\mathbb{Q}^{s}}{d\mathbb{P}}$ has finite variance,e   
(iii) the time $t$ price of a dividend paid at time $s\geq t$ equals the product of the zero-coupon bond price $B_{t}^{s}$ and the $\mathbb{Q}^{s}$ -expectation of the dividend.  

The time $t$ price of a discrete-time dividend process $D_{i}=(D_{i s})$ is then  

$$
P_{i t}=\sum_{s=t+1}^{T}B_{t}^{s}\operatorname{E}_{t}^{\mathbb{Q}^{s}}[D_{i s}].
$$  

No covariance or joint distribution is necessary, but a separate probability measure must be used for each payment date. If you trust the market valuation of bonds, you can observe. $B_{t}^{s}$ in the bond market and you only have to find the expected dividend under the appropriate forward measure. If zero-coupon bonds are not traded, implicit zero-coupon bond prices can be derived or estimated from market prices of traded coupon bonds, see e.g. Munk (2005, Ch. 2).  

Apparently, forward measures were introduced by Jamshidian (1987) and Geman (1989). Some authors use the names forward neutral measure or forward martingale measure instead.  

The word forward can be explained as follows. A forward (contract) on a given asset, say asset $i$ is a binding agreement between two parties stipulating that one party has to sell a unit of the asset to the other party at a given future point in time, say time $s$ , for a price already set today. The (unique) delivery price that ensures that the present value of this contract equals zero is called the forward price of asset $i$ with delivery at time. $s$ . If asset $i$ is assumed to pay no dividends before time $s$ , the forward price for delivery at time $s$ can be shown to be $P_{i t}/B_{t}^{s}$ , i.e. the current price of. the asset "discounted forward in time" using the zero-coupon bond price maturing at the delivery date. The $\mathbb{Q}^{s}$ -measure is defined such that the. $\mathbb{Q}^{s}$ -expectation of the dividend equals the forward price of the asset with delivery at time $s$ (in case of no intermediary dividends).  

# 11.4.2 Relation to state-price deflators and risk-neutral measures  

The time 0 price of a dividend payment of $D_{s}$ at time $s$ is given by both. $\mathrm{E}[\zeta_{s}D_{s}]$ and  

$$
B_{0}^{s}\mathrm{E}^{\mathbb{Q}^{s}}[D_{s}]=B_{0}^{s}\mathrm{E}\left[{\frac{d\mathbb{Q}^{s}}{d\mathbb{P}}}D_{s}\right].
$$  

Therefore, a forward measure for maturity $s$ is related to a state-price deflator through  

$$
B_{0}^{s}\frac{d\mathbb{Q}^{s}}{d\mathbb{P}}=\zeta_{s}\quad\Leftrightarrow\quad\frac{d\mathbb{Q}^{s}}{d\mathbb{P}}=\frac{\zeta_{s}}{B_{0}^{s}}=\frac{\zeta_{s}}{\operatorname{E}\left[\zeta_{s}\right]}.
$$  

The zero-coupon bond price and therefore the Radon-Nikodym derivative $\frac{d\mathbb{Q}^{s}}{d\mathbb{P}}$ only "makes sense' up to time $s$ . Results on the existence and uniqueness of $\mathbb{Q}^{s}$ follow from the corresponding conclusions about state-price deflators.  

In terms of a risk-neutral probability measure $\mathbb{Q}$ , the time 0 value of the dividend. $D_{s}$ is $\mathrm{E}^{\mathbb{Q}}[(R_{0,s}^{f})^{-1}D_{s}]$ and therefore a forward measure for maturity. $s$ is related to a risk-neutral proba-d bility measure through the equation.  

$$
B_{0}^{s}\frac{d\mathbb{Q}^{s}}{d\mathbb{Q}}=\left(R_{0,s}^{f}\right)^{-1}\quad\Leftrightarrow\quad\frac{d\mathbb{Q}^{s}}{d\mathbb{Q}}=(B_{0}^{s})^{-1}\left(R_{0,s}^{f}\right)^{-1}=\frac{\left(R_{0,s}^{f}\right)^{-1}}{\mathrm{E}^{\mathbb{Q}}\left[\left(R_{0,s}^{f}\right)^{-1}\right]}.
$$  

In a continuous-time framework, the last equality can be rewritten as  

$$
\frac{d\mathbb{Q}^{s}}{d\mathbb{Q}}=\frac{e^{-\int_{0}^{s}r_{u}^{f}d u}}{\mathrm{E}^{\mathbb{Q}}\left[e^{-\int_{0}^{s}r_{u}^{f}d u}\right]}.
$$  

If the future risk-free rates are non-random, we see that the forward measure for maturity. $s$ and the risk-neutral probability measure will assign identical probabilities to all events that are decidable at time $s$ , i.e. $\mathbb{Q}^{s}=\mathbb{Q}$ on ${\mathcal{F}}_{s}$ . In a one-period economy, $\mathbb{Q}$ and $\mathbb{Q}^{1}$ are always identical.  

Assume a continuous-time setting and write the dynamics of the zero-coupon bond price maturing at time $s$ as  

$$
d B_{t}^{s}=B_{t}^{s}\left[\left(r_{t}^{f}+(\pmb{\sigma}_{t}^{s})^{\top}\pmb{\lambda}_{t}\right)d t+(\pmb{\sigma}_{t}^{s})^{\top}d z_{t}\right].
$$  

Table 11.2: The $\mathbb{Q}^{2}$ -probabilities in Example 11.3.   


<html><body><table><tr><td>W</td><td>p</td><td>S2</td><td>dQ2 dIP</td><td>q2</td></tr><tr><td>1</td><td>0.24</td><td>1.2</td><td>1.3921</td><td>0.3341</td></tr><tr><td>2</td><td>0.06</td><td>0.8</td><td>0.9281</td><td>0.0557</td></tr><tr><td>3</td><td>0.04</td><td>1</td><td>1.1601</td><td>0.0464</td></tr><tr><td>4</td><td>0.16</td><td>0.9</td><td>1.0441</td><td>0.1671</td></tr><tr><td>5</td><td>0.2</td><td>0.9</td><td>1.0441</td><td>0.2088</td></tr><tr><td>6</td><td>0.3</td><td>0.54</td><td>0.6265</td><td>0.1879</td></tr></table></body></html>  

This implies that  

$$
1=B_{s}^{s}=B_{0}^{s}\exp\left\{\int_{0}^{s}\left(r_{t}^{f}+(\sigma_{t}^{s})^{\top}\lambda_{t}+\frac{1}{2}\|\sigma_{t}^{s}\|^{2}\right)d t-\int_{0}^{s}\left(\sigma_{t}^{s}\right)^{\top}d z_{t}\right\}.
$$  

The Radon-Nikodym derivative of the forward measure with respect to the real-world probability measure can now be written as  

$$
\frac{d\mathbb Q^{s}}{d\mathbb P}=\frac{\zeta_{s}}{B_{0}^{s}}=\exp\left\{-\frac{1}{2}\int_{0}^{s}\|\lambda_{t}-\sigma_{t}^{s}\|^{2}-\int_{0}^{s}\left(\lambda_{t}-\sigma_{t}^{s}\right)^{\top}d z_{t}\right\}.
$$  

According to the Girsanov Theorem 11.1 the process $z^{s}=(z^{s})_{t\in[0,T]}$ defined by $z_{0}^{s}=\mathbf{0}$ and  

$$
d z_{t}^{s}=d z_{t}+\left(\lambda_{t}-\pmb{\sigma}_{t}^{s}\right)d t
$$  

is a standard Brownian motion under the forward measure for maturity $s$ . The dynamics of any process $X=(X_{t})_{t\in[0,T]}$ is transformed via  

$$
d X_{t}=\mu_{X t}d t+\pmb{\sigma}_{X t}^{\top}d z_{t}=\left(\mu_{X t}-\pmb{\sigma}_{X t}^{\top}\left(\pmb{\lambda}_{t}-\pmb{\sigma}_{t}^{s}\right)\right)d t+\pmb{\sigma}_{X t}^{\top}d z_{t}^{s}
$$  

and for a price process the analogue is  

$$
d P_{i t}=P_{i t}\left[\mu_{i t}d t+\sigma_{i t}^{\top}d z_{t}\right]=P_{i t}\left[\left(r_{t}^{f}-\delta_{i t}+\sigma_{i t}^{\top}\sigma_{t}^{s}\right)d t+\sigma_{i t}^{\top}d z_{t}^{s}\right].
$$  

# 11.4.3 Valuation with forward measures  

Example 11.3 Consider the same two-period economy as in Example 11.2. Let us find the forward measure for maturity at time 2, i.e.. $\mathbb{Q}^{2}$ . First, we must find the price of the zero-coupon. bond maturing at time 2:  

$$
B_{0}^{2}=\mathrm{E}[\zeta_{2}]=0.862.
$$  

Now the forward probabilities of the states can be computed as $q_{\omega}^{2}=\zeta_{2}(\omega)p_{\omega}/B_{0}^{2}$ yielding the numbers in Table 11.2. Note that the forward probabilities are different from the risk-neutral probabilities computed in Table 11.1.  

Given the forward probabilities for maturity 2, it is easy to value a dividend received at time 2. The time $0$ value of the time 2 dividend illustrated in Figure 11.3 is.  

$$
B_{0}^{2}\mathrm{E}^{\mathbb{Q}^{2}}[D_{2}]=0.862\cdot\left(1\cdot q_{2}^{2}+2\cdot[q_{1}^{2}+q_{3}^{2}+q_{4}^{2}]+3\cdot[q_{5}^{2}+q_{6}^{2}]\right)=2.018.
$$  

The dividend received at time 1 is not valued using the forward measure for maturity 2 but with the forward measure for time 1, i.e. $\mathbb{Q}^{1}$ . The forward measure at time 1 only assigns probabilities to the decidable events at time 1, i.e. the events $\{1,2\}$ $\{3,4,5\}$ $\{6\}$ and unions of these events. Since the one-period bond is the risk-free asset over the first period, the. $\mathbb{Q}^{1}$ -probabilities are identical to the risk-neutral probabilities of these events, which are depicted in Figure 11.2. Note that these are different from the. $\mathbb{Q}^{2}$ -probabilities of the same events, e.g. $q_{1}^{2}+q_{2}^{2}=0.3898$ while $q_{1}+q_{2}=0.3830$ The time 0 value of the time 1 dividend illustrated in Figure 11.3 is  

$$
B_{0}^{1}\operatorname{E}^{\mathbb{Q}^{1}}[D_{1}]=(R_{0}^{f})^{-1}\operatorname{E}^{\mathbb{Q}}[D_{1}]=2.64
$$  

so that the total time 0 value of the asset is. $2.64+2.018=4.658$ as found in Example 11.2..   
Exercise 11.3 has more on the forward measures in this example.  
