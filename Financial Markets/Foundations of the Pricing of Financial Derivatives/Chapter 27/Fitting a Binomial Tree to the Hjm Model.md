---
tags:
  - binomial_tree
  - drift_calculation
  - forward_rates
  - hjm_model
  - volatility
aliases:
  - Binomial tree example
  - Grant-Vora formula
  - HJM model fitting
key_concepts:
  - Binomial tree
  - Drift calculation
  - Forward rates
  - HJM model
  - Volatility structure
---

# 27.3 FITTING A BINOMIAL TREE TO THE HJM MODEL

Let us now work a numerical example. We start with the following information for the term structure of forward rates:

$$
\begin{array}{l}{{f(0,0)=0.068}}\ {{}}\ {{f(0,1)=0.072}}\ {{}}\ {{f(0,2)=0.08}}\ {{}}\ {{f(0,3)=0.082.}}\end{array}
$$

Of course, the shortest forward rate, $f(0,0)$ , is the spot rate. These rates imply the following bond prices:

$$
\begin{array}{l}{{B(0,1)=e^{-0.068}=0.9343}}\ {{B(0,2)=e^{-(0.068+0.072)}=0.8694}}\ {{B(0,3)=e^{-(0.068+0.072+0.08)}=0.8025}}\ {{B(0,4)=e^{-(0.068+0.072+0.08+0.082)}=0.7393.}}\end{array}
$$

![](93ac4fa8b27c21a5ba9d7231a829dc82c1ea1c74f0352ff05e1566c47eb5083c.jpg)
FIGURe 27.1  Structural Layout of One-Period Binomial Tree of Forward Rates

The volatilities at time 0 are given as

$$
\begin{array}{l l}{{\sigma(0,1)=0.02}}\ {{}}\ {{\sigma(0,2)=0.015}}\ {{}}\ {{\sigma(0,3)=0.01.}}\end{array}
$$

Figure 27.1 shows the structure of the problem. The volatilities are known, as just given, and could be filled in, but we use symbols here so the reader can see the distinction between the original forward rates, the drifts, and the volatilities.

We need to find the drifts,. $\alpha(0,1)$ $\alpha(0,2)$ , and $\alpha(0,3)$ to determine the rates at time 1 that will guarantee no arbitrage. When we have that done, we can move ahead to time 2.

The Grant-Vora formula was given as Equation (27.25). Unfortunately, this formula will be a little confusing when $t=0$ and $T=1$ , because then we would be summing from $j=1$ to 0. What happens is that this whole term drops out. To avoid this confusion, there is an alternative equivalent formula:

$$
\alpha(t,T)=\sigma(t,T)\sum_{j=t+1}^{T}\sigma(t,j)-\left(\frac{\sigma^{2}(t,T)}{2}\right).
$$

Because we are used to working with variances and covariances, these formulas may look familiar. Consider any two forward rates $f(t,T)$ and $f(t,T-1)$ . The covariance at $t$ between these rates is. $\sigma(t,T)\sigma(t,T-1)\rho(t,T-1)$ , where. $\rho(t,T-1)$ is the correlation between the two forward rates. The use of a linear one-factor model, however, means that these rates are perfectly correlated. Hence, the covariance is simply the product of the volatilities, that is, $\sigma(t,T)\sigma(t,T-1)$ . Thus, the covariance matrix will be of the form,

$$
\begin{array}{c c c c}{{}}&{{}}&{{1}}&{{2}}&{{3}}\ {{1}}&{{\sigma^{2}(0,1)}}&{{\sigma(0,1)\sigma(0,2)}}&{{\sigma(0,1)\sigma(0,3)}}\ {{2}}&{{\sigma(0,2)\sigma(0,1)}}&{{\sigma^{2}(0,2)}}&{{\sigma(0,2)\sigma(0,3)}}\ {{3}}&{{\sigma(0,3)\sigma(0,1)}}&{{\sigma(0,3)\sigma(0,2)}}&{{\sigma^{2}(0,3).}}\end{array}
$$

In other words, by knowing the volatility structure we know the variances and covariances of all of the forward rates for all time points up to the final one. Grant and Vora show that the drift for any maturity $T$ will be one-half the sum of the elements in the $i^{t b}$ row and $j^{t h}$ column. For our example, the values in the covariance matrix are

$$
\begin{array}{c c c c}{{}}&{{}}&{{1}}&{{2}}&{{3}}\ {{1}}&{{0.0004}}&{{0.0003}}&{{0.0002}}\ {{2}}&{{0.0003}}&{{0.000225}}&{{0.00015}}\ {{3}}&{{0.0002}}&{{0.00015}}&{{0.0001.}}\end{array}
$$

Let us begin to derive the term structure with maturity $T=1$ . We can use the formula

$$
\begin{array}{c}{\alpha(0,1)=\sigma(0,1)\displaystyle\sum_{j=1}^{1}\sigma(0,1)-\frac{\sigma^{2}(0,1)}{2}}\ {=\sigma(0,1)\sigma(0,1)-\frac{\sigma^{2}(0,1)}{2}=\frac{\sigma^{2}(0,1)}{2}}\ {=\frac{0.0004}{2}=0.0002,}\end{array}
$$

or using the covariance matrix

$$
\alpha(0,1)={\frac{0.0004}{2}}=0.0002.
$$

For maturity $T=2$ , we obtain the drift by the formula

$$
\begin{array}{l}{{\displaystyle\alpha(0,2)=\sigma(0,2)\sum_{j=1}^{2}\sigma(0,j)-\frac{\sigma^{2}(0,2)}{2}}}\ {{\mathrm{}~}}\ {{\displaystyle\qquad=\sigma(0,2)[\sigma(0,1)+\sigma(0,2)]-\frac{\sigma^{2}(0,2)}{2}}}\ {{\mathrm{}~}}\ {{\displaystyle\qquad=0.015(0.02+0.015)-\frac{0.000225}{2}=0.0004125,}}\end{array}
$$

or using the covariance matrix,

$$
\alpha(0,2)=\frac{0.0003+0.000225+0.0003}{2}=0.0004125.
$$

For maturity $T=3$ , we have the formula

$$
\begin{array}{l}{\displaystyle\alpha(0,3)=\sigma(0,3)\sum_{j=1}^{3}\sigma(0,j)-\frac{\sigma^{2}(0,3)}{2}}\ {\displaystyle=\sigma(0,3)[\sigma(0,1)+\sigma(0,2)+\sigma(0,3)]-\frac{\sigma^{2}(0,3)}{2}}\ {\displaystyle=0.01(0.02+0.015+0.01)-\frac{0.0001}{2}=0.0004,}\end{array}
$$

![](0198538cef55ca6617e51300b9ce6283f37f5602345873d979dc90a26ba1d4ff.jpg)
FIGURe 27.2 Numerical Illustration of One-Period Binomial Tree of Forward Rates

or from the covariance matrix,

$$
\alpha(0,3)={\frac{0.0002+0.00015+0.0001+0.0002+0.00015}{2}}=0.0004.
$$

So now we can fill in the first time step of the tree, which is Figure 27.2.

Now suppose we wanted to move forward another time step. If we position ourselves at the top step at time 1, where the rates are $f(1,1)^{+},f(1,2)^{+}$ , and $f(1,3)^{+}$ , we can then imagine moving forward to time step 2 in the manner shown in Figure 27.3.

Note that we now require not only new drift terms but also we see volatility terms not previously seen. That is, we started with a term structure of volatility of. $\sigma(0,1)$ $\sigma(0,2)$ and $\sigma(0,3)$ . These were the volatilities from time point 0. Now, having moved forward to. time point 1, we have a new set of volatilities:. $\sigma(1,2)$ and $\sigma(1,3)$ . Recall that $\sigma(0,2)$ was our value at time 0 of the volatility of the forward rate for time 2. Now, at time 1, $\sigma(1,2)$ is our value of that volatility. Should it be different? In HJM it can indeed be different. In this model, volatility can change over time, but it cannot change stochastically. That is, although $\sigma(1,2)$ can be different from $\sigma(0,2)$ , we had to have known both values at time O. In other words, volatility can change, but we have to know to what value it will change.

![](e8056746f79b46b8e38d3576a510780f7748305c61367f415702ba722491066c.jpg)
FIGURE 27.3 Binomial Tree of Forward Rates from Time $1~\mathrm{Up}$ State

If we do not impose any time series changes on volatility then we simply use the value. $\sigma(0,2)$ for $\sigma(1,2)$ and use $\sigma(0,3)$ for $\sigma(1,3)$ . Then we would be able to calculate the drift. and fit the tree. We would then step down to the lower state at time 1 and determine the rates in the next two states at time 2. As long as we make the assumption that $\sigma(0,2)=$ $\sigma(1,2)$ and $\sigma(0,3)=\sigma(1,3)$ , the tree will recombine. In other words, we require constant. time series volatility. We do not, however, require equivalent cross-sectional volatility. That is, all rates do not have to have the same volatility for the tree to recombine, but a given rate must have the same volatility across time for the tree to recombine. Also, note that as we move to time step 3, we would require. $\sigma(2,3)$ , which might also be assumed equal to $\sigma(0,3)$ or could be treated as a different but known value..

Once we have the entire tree filled in, we have all of the information we need to price any bond or derivative. The remainder of the problem is illustrated in the next section. Recall that we never really worked with spot rates. They are related to the forward rates, but all instruments can be priced off of the forward rates as easily as off of the spot rates. In other words, there is no more information in the spot rates that we do not already have with the forward rates.

We should also note that because of the assumption of a normal distribution of interest rates, it is possible to obtain negative interest rates. This problem, as well as the problem of the tree not recombining, can be addressed in certain versions of the model. Further, negative interest rates have sometimes occurred in practice so the normal distribution may be adequate.

Here we have worked only with one-factor models. In the language of term struc-. ture movements, single-factor models seem to capture only changes in the general level of interest rates but do not reflect changes in the slope or curvature of the term structure. To capture these effects, multifactor models are required. Multifactor models are much more complex. For example, a tree version of a two-factor HJM model requires a trinomial, and the number of paths for. $T$ time steps is $3T$ Clearly some trade-offs are required before deciding to go to models of more than one factor..

So, now let us complete the tree based on all of the information we have
