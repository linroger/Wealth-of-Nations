---
tags:
  - binomial_tree
  - continuous_time_process
  - financial_engineering
  - martingale_probabilities
  - pricing_tools
aliases:
  - Case 2
  - Chapter 12
  - Martingale
  - Pricing
key_concepts:
  - Binomial tree
  - Continuous time process
  - Martingale probabilities
  - Mean and variance
  - Recombining tree
---

# 418 CHAPTER 12 PRICING TOOLS IN FINANCIAL ENGINEERING  

Thed $\{\underline{{u}}_{i},\:d_{i}\}$ are assumed to be constant at $u,d.$  

We now show how to determine the Martingale probabilities. One approach is to find probabilities such that under $p$ $(1-p)$  

$$
S_{i}=e^{-r\Delta}E_{i}^{\tilde{p}}[S_{i+\Delta}]
$$  

or  

$$
S_{i}=e^{-r\Delta}[p S_{i+\Delta}^{u}+(1-p)S_{i+\Delta}^{d}]
$$  

Using the definition of. $S_{i+\Delta}^{u},S_{i+\Delta}^{d}$ , in Eqs. (12.88) and (12.89), we can write  

$$
S_{i}=e^{-r\Delta}[p S_{i}u+(1-p)S_{i}d]
$$  

The mean and the variance of. $S_{i}$ under this probability should also be as given by the postulated. dynamics of the continuous time process in the limit.22 In other words, $p$ should also satisfy  

$$
E_{i}^{\tilde{P}}[S_{i+\Delta}]=[p u+(1-p)d]S_{i}
$$  

and  

$$
E_{i}^{\tilde{P}}[S_{i+\Delta}^{2}-E_{i}^{\tilde{P}}[S_{i+\Delta}]^{2}]=[p u^{2}+(1-p)d^{2}]S_{i}^{2}-E_{i}^{\tilde{P}}[S_{i+\Delta}]^{2}
$$  

Use  

$$
E_{i}^{\Tilde{P}}[S_{i+\Delta}]=S_{i}e^{r\Delta}
$$  

$$
E_{i}^{\tilde{P}}[S_{i+\Delta}^{2}-E_{i}^{\tilde{P}}[S_{i+\Delta}]^{2}]=S_{i}^{2}e^{2r\Delta}(e^{\sigma^{2}\Delta}-1)
$$  

and get the equations  

$$
\begin{array}{c}{{e^{r\Delta}=p u+(1-p)d}}\ {{{}}}\ {{e^{2r\Delta+\sigma^{2}\Delta}=p u^{2}+(1-p)d^{2}}}\end{array}
$$  

The $p,u,d$ that satisfy these two equations will (i) satisfy the Martingale equality for all $\Delta$ (ii) get arbitrarily close to the mean and the variance of the continuous time process $S_{t}$ as $\Delta$ goes to zero, and (iii) make the asymptotic distribution of $S_{i}$ normal. However, there is one problem. Note that here we have two equations and three unknowns: $u,d,$ and $p$ One more equation is needed. Choose  

$$
u={\frac{1}{d}}
$$  

This makes the tree recombine and completes the system of equations. Under these conditions, the following values solve the equations  

$$
\begin{array}{c}{{p=\displaystyle\frac{e^{r\Delta}-d}{u-d}}}\ {{u=e^{\sigma\sqrt{\Delta}}}}\ {{d=e^{-\sigma\sqrt{\Delta}}}}\end{array}
$$  

Any approximation here is in the sense that all terms containing higher orders of $\Delta$ are ignored.23  

# 12.6.2.2 Case 2  

The previous selection of $p,u,d$ satisfies  

$$
S_{i}=e^{-r\Delta}\left[p S_{i}e^{\sigma\sqrt{\Delta}}+(1-p)S_{i}e^{-\sigma\sqrt{\Delta}}\right]
$$  

It turns out that $p,u,d$ can be selected in other ways as well. In particular, note that during an interval $\Delta,S_{t}$ moves to  

$$
S_{t+\Delta}=S_{t}e^{r\Delta-\frac{1}{2}\sigma^{2}\Delta+\sigma\left[W_{t+\Delta}-W_{t}\right]}
$$  

Using the approximation  

$$
W_{t+\Delta}-W_{t}=\left\{{+}\sqrt{\Delta}\begin{array}{c}{{\mathrm{withprobability0.5}}}\ {{-\sqrt{\Delta}}}\end{array}\right.
$$  

we get new values for $p,u$ and $d$  

$$
\begin{array}{c}{u=e^{r\Delta-\frac{1}{2}\sigma^{2}\Delta+\sigma\sqrt{(\Delta)}}}\ {d=e^{r\Delta-\frac{1}{2}\sigma^{2}\Delta-\sigma\sqrt{(\Delta)}}}\ {p=0.5}\end{array}
$$  

These values will again satisfy the Martingale equality, the equality for the mean, and the variance of $S_{i}$ , in the same approximate sense.  
