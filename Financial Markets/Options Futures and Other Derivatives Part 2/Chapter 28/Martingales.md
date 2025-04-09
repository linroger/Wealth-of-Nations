# 28.3 MARTINGALES  

A martingale is a zero-drift stochastic process. A variable $\theta$ follows a martingale if its process has the form.  

$$
d\theta=\sigma d z
$$  

where $d z$ is a Wiener process. The variable. $\sigma$ may itself be stochastic. It can depend on. $\theta$ and other stochastic variables. A martingale has the convenient property that its. expected value at any future time is equal to its value today. This means that  

$$
E(\theta_{T})=\theta_{0}
$$  

where $\theta_{0}$ and $\theta_{T}$ denote the values of. $\theta$ at times zero and. $T$ , respectively. To understand this result, note that over a very small time interval the change in $\theta$ is normally distributed with zero mean. The expected change in $\theta$ over any very small time interval is therefore zero. The change in $\theta$ between time 0 and time. $T$ is the sum of its changes. over many small time intervals. It follows that the expected change in $\theta$ between time 0 and time. $T$ must also be zero.  

# The Equivalent Martingale Measure Result  

Suppose that $f$ and $g$ are the prices of traded securities dependent on a single source of uncertainty. Assume that the securities provide no income during the time period under consideration and define $\phi=f/g$ 4 The variable $\phi$ is the relative price of. $f$ with respect to $g$ It can be thought of as measuring the price of $f$ in units of $g$ rather than dollars.. The security price $g$ is referred to as the numeraire..  

The equivalent martingale measure result shows that, when there are no arbitrage opportunities, $\phi$ is a martingale for some choice of the market price of risk. What is. more, for a given numeraire security. $g$ , the same choice of the market price of risk. makes $\phi$ a martingale for all securities $f.$ This choice of the market price of risk is the. volatility of $g$ In other words, when the market price of risk is set equal to the volatility. of $g$ , the ratio $f/g$ is a martingale for all security prices $f.$ (Note that the market price of risk has the same dimension as volatility. Both are "per square root of time." Setting the market price of risk equal to a volatility is therefore dimensionally valid.).  

To prove this result, suppose that the volatilities of $f$ and $g$ are $\sigma_{f}$ and $\sigma_{g}$ and $r$ is the instantaneous risk-free rate. (These variables can depend on the single source of uncertainty that is being assumed.) From equation (28.10), in a world where the market price of risk is $\sigma_{g}$  

$$
\begin{array}{l}{d f=(r+\sigma_{g}\sigma_{f})f d t+\sigma_{f}f d z}\ {d g=(r+\sigma_{g}^{2})g d t+\sigma_{g}g d z}\end{array}
$$  

Using Ito's lemma gives  

$$
\begin{array}{l}{d\ln f=(r+\sigma_{g}\sigma_{f}-\sigma_{f}^{2}/2)d t+\sigma_{f}d z}\ {d\ln g=(r+\sigma_{g}^{2}/2)d t+\sigma_{g}d z}\end{array}
$$  

so that  

$$
d(\ln f-\ln g)=(\sigma_{g}\sigma_{f}-\sigma_{f}^{2}/2-\sigma_{g}^{2}/2)d t+(\sigma_{f}-\sigma_{g})d z
$$  

or  

$$
d\biggl(\ln{\frac{f}{g}}\biggr)=-{\frac{(\sigma_{f}-\sigma_{g})^{2}}{2}}d t+(\sigma_{f}-\sigma_{g})d z
$$  

Ito's lemma can be used to determine the process for $f/g$ from the process for. $\ln(f/g)$  

$$
d\bigg(\frac{f}{g}\bigg)=(\sigma_{f}-\sigma_{g})\frac{f}{g}d z
$$  

This shows that $f/g$ is a martingale and proves the equivalent martingale measure result.  

From now on, we will use the phrase "world defined by numeraire $g^{,}$ to mean a world where $\sigma_{g}$ , the volatility of $g$ , is the market price of risk. Because $f/g$ is a martingale in this world, it follows from the result at the beginning of this section that  

$$
\frac{f_{0}}{g_{0}}=E_{g}\bigg(\frac{f_{T}}{g_{T}}\bigg)
$$  

or  

$$
f_{0}=g_{0}E_{g}\bigg(\frac{f_{T}}{g_{T}}\bigg)
$$  

where $E_{g}$ denotes the expected value in a world defined by numeraire $g$  
