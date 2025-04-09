# 9.3 PUT OPTIONS

Based on put-call parity, we have

$$
\begin{array}{r}{p=S B_{1}-X e^{-r_{c}\tau}B_{2}-S+X e^{-r_{c}\tau}=X e^{-r_{c}\tau}(1-B_{2})-S(1-B_{1}).}\end{array}
$$

This binomial result will converge to the Black-Scholes-Merton put model in the limit as $n\to\infty$ Or

$$
\begin{array}{r}{p_{t}=c_{t}-S_{t}+X e^{-r_{c}\tau}=X e^{-r_{c}\tau}N(-d_{2})-S_{t}N(-d_{1}).}\end{array}
$$

The convergence properties are the same as the call results as illustrated in Figure 9.2.
This identical pattern is driven by put-call parity. Put-call parity can be expressed. $\mathsf{a s c}_{t}=$ $\scriptstyle{p_{t}=S_{t}-X^{-r_{c}\tau}}$ Thus, the binomial convergence of the put is simply shifted by the difference between the asset price and the present value of the strike price.
We now explore the important role of dividends, which can occur if the underlying asset is a stock or index.

![](535e39cbf9ef7a141d3e97ac0926979c8fcd5ca83209fc7a49e6358b4e6ed3fa.jpg)
FIGURe 9.2  Convergence of the Binomial Model for Puts to the Black-Scholes-Merton
