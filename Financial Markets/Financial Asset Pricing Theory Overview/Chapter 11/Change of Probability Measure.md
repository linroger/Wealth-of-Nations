---
tags:
  - bayes_formula
  - brownian_motion
  - probability_measure
  - radon_nikodym
  - stochastic_process
aliases:
  - Change of Measure
  - Probability Measure Change
key_concepts:
  - Change-of-measure process
  - Equivalent probability measures
  - Probability space
  - Radon-Nikodym derivative
  - Real-world probabilities
---

# 11.2 Change of probability measure  

Any financial model with uncertainty formally builds on a probability space. $\left(\Omega,\mathcal{F},\mathbb{P}\right)$ , where $\Omega$ is the state space (the set of possible realizations of all relevant uncertain objects),. $\mathcal{F}$ is the set of. events that can be assigned a probability, and. $\mathbb{P}$ is a probability measure assigning probabilities to events. It is implicitly understood that $\mathbb{P}$ gives the true or real-world probabilities of events. The. consumption and investment decisions of individuals will depend on the probabilities they associate with different events and, hence, the equilibrium asset prices will reflect those probabilities. However, as we will see in the following sections, for some purposes it will be interesting to consider other probability measures on the same set of events. We will use the term real-world probability.  

measure for $\mathbb{P}$ but in the literature $\mathbb{P}$ is also referred to as the true, the physical, or the empirical probability measure.  

A word on notation. Whenever the expectation operator is written without a superscript, it means the expectation using the probability measure $\mathbb{P}$ . The expectation under a different probability measure $\mathbb{Q}$ will be denoted by $\mathrm{E}^{\mathbb{Q}}$ . Similarly for variances and covariances and for conditional moments.  

The alternative probability measures we will consider will be equivalent to $\mathbb{P}$ . Two probability measures $\mathbb{P}$ and $\mathbb{Q}$ on the same set of events $\mathcal{F}$ are said to be equivalent probability measures if they assign probability zero to exactly the same events, i.e.  

$$
\mathbb{P}(F)=0\quad\Leftrightarrow\quad\mathbb{Q}(F)=0.
$$  

The link between two equivalent probability measures $\mathbb{P}$ and $\mathbb{Q}$ can be represented by a random variable, which is typically denoted by $\textstyle{\frac{d\mathbb{Q}}{d\mathbb{P}}}$ and referred to as the Radon-Nikodym derivative of $\mathbb{Q}$ with respect to $\mathbb{P}$ . For any state $\omega\in\Omega$ , the value of $\textstyle{\frac{d\mathbb{Q}}{d\mathbb{P}}}$ shows what the $\mathbb{P}$ probability of $\omega$ should be multiplied by in order to get the $\mathbb{Q}$ -probability of $\omega$ . In the special case of a finite state space $\Omega=\{1,2,\dots,S\}$ , the probability measures $\mathbb{P}$ and $\mathbb{Q}$ are defined by the probabilities $p_{\omega}$ and $q_{\omega}$ , respectively, of the individual states $\omega=1,2,\ldots,S$ . The Radon-Nikodym derivative of $\mathbb{Q}$ with respect to $\mathbb{P}$ is then captured by the. $S$ possible realizations  

$$
\frac{d\mathbb Q}{d\mathbb P}(\omega)=\frac{q_{\omega}}{p_{\omega}},\quad\omega=1,\ldots,S.
$$  

The Radon-Nikodym derivative $\textstyle{\frac{d\mathbb{Q}}{d\mathbb{P}}}$ must be strictly positive on all events having a non-zero $\mathbb{P}$ probability. Furthermore, to ensure that the. $\mathbb{Q}$ probabilities sum up to one, we must have. $\begin{array}{r}{\mathrm{E}\left[\frac{d\mathbb{Q}}{d\mathbb{P}}\right]=}\end{array}$ 1. For example, with a finite state space  

$$
\operatorname{E}\left[{\frac{d\mathbb{Q}}{d\mathbb{P}}}\right]=\sum_{\omega=1}^{S}p_{\omega}{\frac{d\mathbb{Q}}{d\mathbb{P}}}(\omega)=\sum_{\omega=1}^{S}p_{\omega}{\frac{q_{\omega}}{p_{\omega}}}=\sum_{\omega=1}^{S}q_{\omega}=1.
$$  

The expected value under the measure $\mathbb{Q}$ of a random variable. $X$ is given by.  

$$
\operatorname{E}^{\mathbb{Q}}[X]=\operatorname{E}\left[{\frac{d\mathbb{Q}}{d\mathbb{P}}}X\right].
$$  

Again, this is easily demonstrated with a finite state space:  

$$
\operatorname{E}^{\mathbb{Q}}[X]=\sum_{\omega=1}^{S}q_{\omega}X(\omega)=\sum_{\omega=1}^{S}p_{\omega}{\frac{q_{\omega}}{p_{\omega}}}X(\omega)=\sum_{\omega=1}^{S}p_{\omega}{\frac{d\mathbb{Q}}{d\mathbb{P}}}(\omega)X(\omega)=\operatorname{E}\left[{\frac{d\mathbb{Q}}{d\mathbb{P}}}X\right].
$$  

In a multi-period model where all the uncertainty is resolved at time $T$ , the Radon-Nikodym. derivative $\textstyle{\frac{d\mathbb{Q}}{d\mathbb{P}}}$ will be realized at time $T$ but usually not known before time $T$ . Define the stochastic process $\xi=(\xi_{t})_{t\in\mathcal{T}}$ by  

$$
\xi_{t}=\mathrm{E}_{t}\left[\frac{d\mathbb{Q}}{d\mathbb{P}}\right].
$$  

In particular, $\textstyle\xi_{T}={\frac{d\mathbb{Q}}{d\mathbb{P}}}$ . The process $\xi$ is called the change-of-measure process or the likelihood ratio process. Note that the process $\xi$ is a $\mathbb{P}$ -martingale since, for any $t<t^{\prime}\leq T$ , we have  

$$
\operatorname{E}_{t}\left[\xi_{t^{\prime}}\right]=\operatorname{E}_{t}\left[\operatorname{E}_{t^{\prime}}\left[\xi_{T}\right]\right]=\operatorname{E}_{t}\left[\xi_{T}\right]=\xi_{t}.
$$  

Here the first and the third equalities follow from the definition of $\xi$ . The second equality follows.   
from the Law of Iterated Expectations, Theorem 2.1..  

In multi-period models we often work with conditional probabilities and the following result turns out to be very useful. Let. $X=(X_{t})_{t\in\mathcal{T}}$ be any stochastic process. Then we have.  

$$
\operatorname{E}_{t}^{\mathbb{Q}}\left[X_{t^{\prime}}\right]={\frac{\operatorname{E}_{t}\left[\xi_{t^{\prime}}X_{t^{\prime}}\right]}{\operatorname{E}_{t}\left[\xi_{t^{\prime}}\right]}}=\operatorname{E}_{t}\left[{\frac{\xi_{t^{\prime}}}{\xi_{t}}}X_{t^{\prime}}\right].
$$  

This is called Bayes' Formula. For a proof, see Bjork (2004, Prop. B.41).  

A change of the probability measure can be handled very elegantly in continuous-time models where the underlying uncertainty is represented by a standard Brownian motion $z=(z_{t})_{t\in[0,T]}$ (under the real-world probability measure $\mathbb{P}$ ), which is the case in all the continuous-time models considered in this book. Let $\lambda=(\lambda_{t})_{t\in[0,T]}$ be any adapted and sufficiently well-behaved stochastic process.' Here, $z$ and $\lambda$ must have the same dimension. For notational simplicity, we assume in the following that they are one-dimensional, but the results generalize naturally to the multidimensional case. We can generate an equivalent probability measure $\mathbb{Q}^{\lambda}$ in the following way. Define the process $\xi^{\lambda}=(\xi_{t}^{\lambda})_{t\in[0,T]}$ by  

$$
\xi_{t}^{\lambda}=\exp\left\{-\int_{0}^{t}\lambda_{s}\:d z_{s}-\frac{1}{2}\int_{0}^{t}\lambda_{s}^{2}\:d s\right\}.
$$  

Then $\xi_{0}^{\lambda}=1$ $\xi^{\lambda}$ is strictly positive, and an application of Ito's Lemma shows that $d\xi_{t}^{\lambda}=-\xi_{t}^{\lambda}\lambda_{t}d z_{t}$ so that $\xi^{\lambda}$ is a $\mathbb{P}$ -martingale (see Exercise 2.4) and $\mathrm{E}[\xi_{T}^{\lambda}]=\xi_{0}^{\lambda}=1$ . Consequently, an equivalent probability measure $\mathbb{Q}^{\lambda}$ can be defined by the Radon-Nikodym derivative  

$$
\frac{d\mathbb{Q}^{\lambda}}{d\mathbb{P}}=\xi_{T}^{\lambda}=\exp\left\{-\int_{0}^{T}\lambda_{s}d z_{s}-\frac{1}{2}\int_{0}^{T}\lambda_{s}^{2}d s\right\}.
$$  

From (11.2), we get that  

$$
\operatorname{E}_{t}^{\mathbb{Q}^{\lambda}}\left[X_{t^{\prime}}\right]=\operatorname{E}_{t}\left[\frac{\xi_{t^{\prime}}^{\lambda}}{\xi_{t}^{\lambda}}X_{t^{\prime}}\right]=\operatorname{E}_{t}\left[X_{t^{\prime}}\exp\left\{-\int_{t}^{t^{\prime}}\lambda_{s}d z_{s}-\frac{1}{2}\int_{t}^{t^{\prime}}\lambda_{s}^{2}d s\right\}\right]
$$  

for any stochastic process. $X=(X_{t})_{t\in[0,T]}$ . A central result is Girsanov's Theorem:  

Theorem 11.1 (Girsanov) The process $z^{\lambda}=(z_{t}^{\lambda})_{t\in[0,T]}$ defined by.  

$$
z_{t}^{\lambda}=z_{t}+\int_{0}^{t}\lambda_{s}d s,\quad0\leq t\leq T,
$$  

is a standard Brownian motion under the probability measure $\mathbb{Q}^{\lambda}$ . In differential notation,.  

$$
d z_{t}^{\lambda}=d z_{t}+\lambda_{t}d t.
$$  

This theorem has the attractive consequence that the effects on a stochastic process of changing the probability measure from $\mathbb{P}$ to some $\mathbb{Q}^{\lambda}$ are captured by a simple adjustment of the drift. If. $X=\left(X_{t}\right)$ is an Ito-process with dynamics.  

$$
d X_{t}=\mu_{t}d t+\sigma_{t}d z_{t},
$$  

then  

$$
d X_{t}=\mu_{t}d t+\sigma_{t}\left(d z_{t}^{\lambda}-\lambda_{t}d t\right)=\left(\mu_{t}-\sigma_{t}\lambda_{t}\right)d t+\sigma_{t}d z_{t}^{\lambda}.
$$  

Hence, $\mu-\sigma\lambda$ is the drift under the probability measure. $\mathbb{Q}^{\lambda}$ , which is different from the drift under. the original measure $\mathbb{P}$ unless $\sigma$ or $\lambda$ are identically equal to zero. In contrast, the volatility remains. the same as under the original measure. We will say that the equation (11.6) is the $\mathbb{Q}^{\lambda}$ -dynamics of the process $X$  

In many financial models, the relevant change of measure is such that the distribution under. $\mathbb{Q}^{\lambda}$ of the future value of the central processes is of the same class as under the original. $\mathbb{P}$ measure, but with different moments. However, in general, a shift of probability measure may change not only some or all moments of future values, but also the distributional class..  
