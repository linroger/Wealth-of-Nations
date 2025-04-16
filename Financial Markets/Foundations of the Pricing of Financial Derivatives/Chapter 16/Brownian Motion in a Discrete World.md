---
tags:
  - '#binomial_process'
  - '#brownian_motion'
  - '#covariance'
  - '#expectation'
  - '#increment'
  - '#random_variable'
  - '#time_periods'
  - '#time_step'
  - '#variance'
  - '#wiener_process'
---
# 16.1 BROWNIAN MOTION IN A DISCRETE WORLD

An extremely simple form of Brownian motion is a binomial process in which a random variable W, starting off at a value of $W_{0}=0$ , can take on a value of $W_{1}^{+}=+1$ or $W_{1}^{-}=-1$ in the next time period or sometimes termed time step. We denote the change from the point in time O to the point in time 1 as $\Delta\mathbb{W}_{0}$ . Thus, the change notation refers to the initial point in time (0 here) and not the final point in time (1 here). Figure 16.1 illustrates this process.

Although some versions of this type of model permit unequal probabilities, many desirable properties are associated with the case where the probabilities of the up and down. moves are $^1/_{2}$ . If, however, one is attempting to model a process with a given expectation and volatility, then there are formulas that specify the probabilities, which will not generally be $^1/_{2}$ . In the limiting case, that is, when the number of time steps over which a fixed period of time is large, however, it is well known that the formulas converge to. $^1/_{2}$

Now let us examine some of the properties of the model. First consider the increment, $\Delta\mathrm{W_{0}}$ . The expected value and variance of the increment are.

$$
E\left(\Delta W_{0}\right)=\left({\frac{1}{2}}\right)\left(+1\right)+\left({\frac{1}{2}}\right)\left(-1\right)=0
$$

$$
\mathrm{var}\left(\Delta{\cal W}_{0}\right)=\left(\frac{1}{2}\right)(+1-0)^{2}+\left(\frac{1}{2}\right)(-1-0)^{2}=1.
$$

![](04c5dc09cec1db7728af4b2815ac37b28866d75bc2974125a768a2cbd383b460.jpg)

FIGURE 16.1 One-Period Binomial Wiener Process

Thus, because $W_{1}=W_{0}+\Delta W_{0}$ , its expectation is

$$
\begin{array}{c}{{E\left(W_{1}\right)=E\left(W_{0}+\Delta W_{0}\right)=E\left(W_{0}\right)+E\left(\Delta W_{0}\right)}}\ {{{}}}\ {{{}=0+0=0.}}\end{array}
$$

The variance of $W_{1}$ is, by definition,

$$
\operatorname{var}\left(W_{1}\right)=E\left(W_{1}^{2}\right)-\left[E\left(W_{1}\right)\right]^{2}.
$$

Focusing first on the expected value of the square of $W_{1}$

$$
E\left(W_{1}^{2}\right)=\left({\frac{1}{2}}\right)(+1)^{2}+\left({\frac{1}{2}}\right)(-1)^{2}=1.
$$

Because $E\big(\mathbb{W}_{1}\big)=0$ , we have

$$
\operatorname{var}\left(\mathrm{W}_{1}\right)=1-0^{2}=1.
$$

Another way to obtain this result is to recall that we want $\operatorname{var}\bigl(\mathrm{W}_{1}\bigr)$ , which is var $\left(\mathrm{W}_{0}+\Delta\mathrm{W}_{0}\right)$ . The variance of a sum is the sum of the variances and twice all pairwise covariances, but $W_{0}$ is a constant so its variance is zero and, therefore, there is no. covariance with $\Delta\mathrm{W_{0}}$ . Thus, $\operatorname{var}\left(\mathrm{W}_{1}\right)=\operatorname{var}\left(\Delta\mathrm{W}_{0}\right)$ , which we already found as 1.

In this form, however, the model is too simple and has limited use. We can extend it somewhat by adding time periods. Note, however, that if we just let the process move from $+1$ to $+2$ or 0 or from $-1$ to 0 or $^{-2}$ , the variance would obviously increase.2 With a large number of time periods, we might find ourselves with an unreasonable variance. One way to scale the variance is to establish that we are trying to model a random process over a fixed period of time. We might say, for example, that we wish to model movements over a period $t=1$ , which might be one year, and we could capture these movements with a model of $n=2$ periods. We are, therefore, establishing that the time step is $\Delta t=1/2$ . We might be inclined, therefore, to adjust the model so that $\Delta\mathbb{W}=\pm1\Delta t$ , but this adjustment will. cause a problem. Intuitively, we might expect that we can better capture reality if we shrink the time interval such that. $t$ is fixed but $_n$ is large. In that case,. $\Delta t\to0$ .What does this leave us with? No motion at all, as it is easy to see that the variance will approach zero.3

Alternatively, let us try the model

$$
\Delta\mathrm{W}=\pm\sqrt{\Delta t}.
$$

Now let us observe what we have in Figure 16.2.

![](cedbb52839366b8d117b51e55ce29e14497eef40f7b3e24e2c46c92391d93175.jpg)
FIGURE 16.2 Two-Period Binomial Wiener Process

Now let us find the expectation and variance of $\Delta\mathbb{W}_{0}$ and $\Delta\mathbb{W}_{1}$ . For the first increment,.

$$
\begin{array}{l}{{\displaystyle{\cal E}\left(\Delta W_{0}\right)=\left(\frac12\right)\left(+1\sqrt{1/2}\right)+\left(\frac12\right)(-1\sqrt{1/2})=0}}\ {{\mathrm{var}\left(\Delta W_{0}\right)=\left(\frac12\right)\left(+1\sqrt{1/2}-0\right)^{2}+\left(\frac12\right)\left(-1\sqrt{1/2}-0\right)^{2}=1/2.}}\end{array}
$$

For $W_{1}$ , note again that the variance is the sum of the variance of $W_{0}$ and $\Delta W_{1}.W_{0}$ is known so it has no variance nor a covariance with $\Delta W_{1}$ , and we can ignore any covariance between $W_{0}$ and $\Delta\mathbb{W}_{1}$ . Therefore,

$$
\begin{array}{r}{E\big(W_{1}\big)=E\big(W_{0}\big)+E\big(\Delta W_{0}\big)=0+0=0\qquad}\ {\mathrm{var}\big(W_{1}\big)=\mathrm{var}\big(W_{0}\big)+\mathrm{var}\big(\Delta W_{0}\big)=0+1/2=1/2.}\end{array}
$$

Now we need the expectation and variance of $W_{2}$ 4.

$$
\begin{array}{c}{E\big(W_{2}\big)=W_{0}+E\big(\Delta W_{0}\big)+E\big(\Delta W_{1}\big)=0+0+0=0}\ {\operatorname{var}\big(W_{2}\big)=\operatorname{var}\big(W_{0}\big)+\operatorname{var}\big(\Delta W_{0}\big)+\operatorname{var}\big(\Delta W_{1}\big)=0+1/2+1/2=1.}\end{array}
$$

Thus, we observe again a zero mean but a variance that is growing linearly in time. Recall $\Delta t=1/2$ , so after two time steps, we have a variance of one as well as $t=1$

Now let us consider the general case of a process $\mathbf{}W_{t}$ where $t$ can be any future point in time:5

$$
\begin{array}{c}{{E\left(\Delta W_{t}\right)=\left(\displaystyle\frac{1}{2}\right)\left(+1\sqrt{\Delta t}\right)+\left(\displaystyle\frac{1}{2}\right)\left(-1\sqrt{\Delta t}\right)=0}}\ {{\mathrm{var}\left(\Delta W_{t}\right)=\displaystyle\left(\frac{1}{2}\right)\left(+1\sqrt{\Delta t}-0\right)^{2}+\left(\displaystyle\frac{1}{2}\right)\left(-1\sqrt{\Delta t}-0\right)^{2}=\Delta t.}}\end{array}
$$

Now consider the expectation and variance of $\mathbb{W}_{t}$ . First let us set the following. relationship,

$$
\mathrm{W}_{t}=\mathrm{W}_{0}+\sum_{i=0}^{n-1}\Delta\mathrm{W}_{i}.
$$

Then we can find the expected value and variance as

$$
\begin{array}{l}{{\displaystyle{\cal E}\big({\cal W}_{t}\big)={\cal W}_{0}+{\cal E}\left(\sum_{i=1}^{n-1}\Delta{\cal W}_{i}\right)=0+0+...0=0}}\ {{\mathrm{var}\big({\cal W}_{t}\big)=\mathrm{var}\big({\cal W}_{0}\big)+\mathrm{var}\left(\sum_{i=1}^{n-1}\Delta{\cal W}_{i}\right)}}\ {{\displaystyle~=0+\Delta t+\Delta t+...\Delta t=t.}}\end{array}
$$

The latter result comes from the fact that summing from O to $n-1$ is $_n$ items. So $_n$ times $\Delta t$ is $t$ because $\Delta t=t/n$
