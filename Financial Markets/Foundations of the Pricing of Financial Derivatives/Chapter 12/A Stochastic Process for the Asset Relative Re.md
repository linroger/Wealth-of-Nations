---
tags:
  - '#asset_relative_return'
  - '#central_limit_theorem'
  - '#geometric_brownian_motion'
  - '#ito_lemma'
  - '#log_return'
  - '#lognormally_distributed'
  - '#stochastic_differential_equations'
  - '#stochastic_process'
---
# 12.1 A STOCHASTIC PROCESS FOR THE ASSET RELATIVE RETURN

The relative return on the asset from a starting point of time O to a point of time dt is3

$$
\frac{S_{d t}}{S_{0}}.
$$

The relative return from time $d t$ to time $2d t$ is

$$
\frac{S_{2d t}}{S_{d t}}.
$$

This pattern continues so that at a given future time $T.$ , the relative return is

$$
{\frac{S_{T}}{S_{T-d t}}}.
$$

Backing up to time 0, the relative return on the asset to time $T$ is

$$
\frac{S_{T}}{S_{0}}.
$$

This return can be expressed by linking the successive relative returns,

$$
\frac{S_{T}}{S_{0}}=\left(\frac{S_{d t}}{S_{0}}\right)\left(\frac{S_{2d t}}{S_{d t}}\right)\cdot\cdot\cdot\left(\frac{S_{T-d t}}{S_{T-2d t}}\right)\left(\frac{S_{T}}{S_{T-d t}}\right).
$$

Now let us convert Equation (12.9) into the log or continuously compounded return,

$$
\ln\left(\frac{S_{T}}{S_{0}}\right)=\ln\left(\frac{S_{d t}}{S_{0}}\right)+\ln\left(\frac{S_{2d t}}{S_{d t}}\right)+\cdot\cdot\cdot+\ln\left(\frac{S_{T-d t}}{S_{T-2d t}}\right)+\ln\left(\frac{S_{T}}{S_{T-d t}}\right).
$$

We see that the log return for the period of time 0 to time $T$ is the sum of the log returns. of the subperiods from time O to time. $T.$ Now recall that the central limit theorem says that a random variable that is defined as the sum of a series of other random variables from any distribution that is constant approaches a normal distribution. Thus, we know that the return from time O to time. $T$ is normally distributed, provided the distribution of the intermediate returns is constant. We can also propose that each subperiod is infinitesimally small such that it, too, is made up of a series of component returns over infinitesimally small subperiods. Hence, it is reasonable to propose that the return over any arbitrary "short" period from $t$ to $t+d t$ is normally distributed with $d t$ period expectation of $\mu_{p}$ and variance of $\sigma_{p}^{2}$ , which is formally written as.

$$
\ln\left(\frac{S_{t+d t}}{S_{t}}\right)\sim N\left(\mu_{p},\sigma_{p}^{2}\right).
$$

It is important to emphasize that when the price is lognormally distributed, the log of the relative return is normally distributed. Thus, the asset price is lognormally distributed. By definition, the log return is defined in the following manner:

$$
\ln\left(\frac{S_{t+d t}}{S_{t}}\right)=\ln S_{t+d t}-\ln S_{t}=d\ln S_{t}.
$$

In other words, the log return is the change in the log values of the asset price at the beginning and ending of the holding period. We then propose that the log return follows the GBM stochastic process

$$
d\ln S_{t}=\mu d t+\sigma d\mathrm{W}.
$$

where the expectation and variance are, therefore,

$$
\begin{array}{r}{E(d\ln S_{t})=\mu d t}\ {\mathrm{var}(d\ln S_{t})=\sigma^{2}d t.}\end{array}
$$

Now, however, we want the return $d S_{t}/S_{t}$ . Let us use the following transformation:

$$
G_{t}=\ln S_{t},
$$

so that

$$
S_{t}=\operatorname{e}^{G}.
$$

We wish to find the stochastic process for $S_{t}$ , so we can use Ito's lemma. Temporarily dropping the time subscript, we obtain.

$$
d S=\frac{\partial S}{\partial G}d G+\frac{1}{2}\frac{\partial^{2}S}{\partial G^{2}}d G^{2}.
$$

The partial derivatives are easily obtained as

$$
\begin{array}{c}{{{\displaystyle\frac{\partial S}{\partial G}}=\mathrm{e}^{G}=S}}\ {{{}}}\ {{{\displaystyle\frac{\partial^{2}S}{\partial G^{2}}}=\mathrm{e}^{G}=S.}}\end{array}
$$

Substituting these results, we get

$$
d S=S d G+{\frac{1}{2}}S d G^{2}.
$$

Because $d G=d\ln S.$ the differentials, $d G$ and $d G^{2}$ , are

$$
\begin{array}{c}{{d G=\mu d t+\sigma d W}}\ {{}}\ {{d G^{2}=\sigma^{2}d t.}}\end{array}
$$

Substituting these results, we obtain

$$
d S=S(\mu d t+\sigma d W_{t})+\frac{1}{2}S\sigma^{2}d t.
$$

Dividing both sides by $S_{t}$ and adding the time subscript, we now have the stochastic process for $d S_{t}/S_{t}$

$$
\frac{d S_{t}}{S_{t}}=(\mu+\sigma^{2}/2)d t+\sigma d\mathrm{W}_{t}.
$$

Defining $\alpha=\mu+\sigma^{2}/2$ , we have

$$
\frac{d S_{t}}{S_{t}}=\alpha d t+\sigma d W_{t}.
$$

And this is the equation we proposed heuristically in Chapter 10. We have now provided a formal derivation of its existence. The expectation and variance are

$$
\begin{array}{c}{E\displaystyle\left(\frac{d S_{t}}{S_{t}}\right)=\alpha d t}\ {\displaystyle\operatorname{var}\left(\frac{d S_{t}}{S_{t}}\right)=\sigma^{2}d t.}\end{array}
$$

Thus, we now have the stochastic differential equations for the return (Equation (12.23)) and the log return (Equation (12.13). The return over the longer horizon is $d S_{T}/S_{0}$ , and the log return over the long horizon is normally distributed, which means that $d S_{T}/S_{0}$ is lognormally distributed.4 Both the infinitesimal return, $d S_{t}/S_{t}$ , and the infinitesimal log return, $d\ln S_{t}$ , are normally distributed.

For those students who remember their calculus, they might more easily make the link that because $d\ln S(t)=S^{\prime}(t)/S^{\prime}(t)$ then $d\ln S(t)=d S(t)/S(t)=\alpha d t+\sigma d W_{t}$
