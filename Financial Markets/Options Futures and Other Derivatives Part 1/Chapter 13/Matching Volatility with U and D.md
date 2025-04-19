---
tags:
  - binomial_tree
  - cox_ross_rubinstein
  - girsanov_theorem
  - risk_neutral
  - volatility
aliases:
  - Binomial Tree Parameters
  - Matching Volatility
key_concepts:
  - Binomial tree construction
  - Girsanov's theorem
  - Real world volatility
  - Risk-neutral world
  - Volatility matching
---

# 13.7 MATCHING VOLATILITY WITH u AND d  

The three parameters necessary to construct a binomial tree with time step $\Delta t$ are $u,d$ and $p$ . Once $u$ and $d$ have been specified, $p$ must be chosen so that the expected return is the risk-free rate $r$ We have already shown that  

$$
p=\frac{e^{r\Delta t}-d}{u-d}
$$  

The parameters $u$ and $d$ should be chosen to match volatility. The volatility of a stock. (or any other asset), $\sigma$ , is defined so that the standard deviation of its return in a short period of time $\Delta t$ .15 $\overline{{\sigma\sqrt{\Delta t}}}$ (see Chapter 15 for a further discussion of this). Equivalently the variance of the return in time $\Delta t$ is $\sigma^{2}\Delta t.$ The variance of a variable $X$ is defined as $E(X^{2})\:-\:[E(X)]^{2}$ , where $E$ denotes expected value. During a time step of length $\Delta t$ there is a probability $p$ that the stock will provide a return of $u\mathrm{~-~}1$ and a probability $1-p$ that it will provide a return of $d-1$ . It follows that volatility is matched if  

$$
p(u-1)^{2}+(1-p)(d-1)^{2}-[p(u-1)+(1-p)(d-1)]^{2}=\sigma^{2}\Delta t
$$  

Substituting for $p$ from equation (13.11), this simplifies to  

$$
e^{r\Delta t}(u+d)-u d-e^{2r\Delta t}=\sigma^{2}\Delta t
$$  

![](66262210d002192e3d453c2b7f5e0670a25d7fb3f6289ebb055a672f26af8c54.jpg)  
Figure 13.9 Change in stock price in time $\Delta t$ in (a) the real world and (b) the risk.. neutral world..  

When terms in $\Delta t^{2}$ and higher powers of. $\Delta t$ are ignored, a solution to equation (13.13) is2  

$$
u=e^{\sigma{\sqrt{\Delta t}}}\quad{\mathrm{and}}\quad d=e^{-\sigma{\sqrt{\Delta t}}}
$$  

These are the values of. $u$ and $d$ used by Cox, Ross, and Rubinstein (1979).  

In the analysis just given we chose $u$ and $d$ to match volatility in the risk-neutral world. What happens if instead we match volatility in the real world? As we will now show, the formulas for $u$ and $d$ are the same.  

Suppose that $p^{*}$ is the probability of an up-movement in the real world while. $p$ is as before the probability of an up-movement in a risk-neutral world. This is illustrated in Figure 13.9. Define $\mu$ as the expected return in the real world. We must have.  

$$
p^{*}u+(1-p^{*})d=e^{\mu\Delta t}
$$  

or  

$$
p^{*}={\frac{e^{\mu\Delta t}-d}{u-d}}
$$  

Suppose that $\sigma$ is the volatility in the real world. The equation matching the variance is the same as equation (13.12) except that $p$ is replaced by $p^{*}$ . When this equation is. combined with equation (13.14), we obtain.  

$$
e^{\mu\Delta t}(u+d)-u d-e^{2\mu\Delta t}=\sigma^{2}\Delta t
$$  

This is the same as equation (13.13) except the $r$ is replaced by $\mu$ . When terms in $\Delta t^{2}$ and higher powers of $\Delta t$ are ignored, it has the same solution as equation (13.13):  

$$
u=e^{\sigma{\sqrt{\Delta t}}}\quad{\mathrm{and}}\quad d=e^{-\sigma{\sqrt{\Delta t}}}
$$  

# Girsanov's Theorem  

The results we have just produced are closely related to an important result known as. Girsanov's theorem. When we move from the risk-neutral world to the real world, the expected return from the stock price changes, but its volatility remains the same. More.  

$$
e^{x}=1+x+{\frac{x^{2}}{2!}}+{\frac{x^{3}}{3!}}+\cdot\cdot\cdot
$$  

generally, when we move from a world with one set of risk preferences to a world with. another set of risk preferences, the expected growth rates in variables change, but their. volatilities remain the same. We will examine the impact of risk preferences on the. behavior of market variables in more detail in Chapter 28. Moving from one set of risk preferences to another is sometimes referred to as changing the measure. The real-world measure is sometimes referred to as the $P$ -measure, while the risk-neutral world measure. is referred to as the $Q$ measure.3  
