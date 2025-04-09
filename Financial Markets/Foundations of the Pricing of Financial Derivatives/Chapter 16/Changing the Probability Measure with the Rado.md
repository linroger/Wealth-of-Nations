# 16.3 CHANGING THE PROBABILITY MEASURE WITH THE RADON-NIKODYM DERIVATIVE IN DISCRETE TIME

We examined the Radon-Nikodym derivative for a continuous time process in Chapter 15.. In the current chapter, we started with a discrete time Brownian motion model. We then extended it to the continuous time case. Before leaving, we need to return to the discrete time case and examine how to change the probability measure. This procedure is extremely. important but is much more difficult in the continuous time case. This material draws heavily on the excellent treatment in Baxter and Rennie (1996)..

So let us again go back to the simple world with two outcomes. We can generalize it a little bit without any problems by having our variable. $W_{0}$ move to $\mathbb{W}_{1}^{+}$ or $W_{1}^{-}$ with probabilities $\phi$ and $1-\phi$ , respectively. Now let us suppose that we are interested in changing. the probabilities to $q$ and $1-q$ . Without further study, one may wonder why we would. want to do this or even whether we could do this without creating a problem. Probabilities. are, after all, usually given by external phenomena, and we cannot often change them.9 But assigned probabilities can actually sometimes be changed. We have already seen that we can create artificial probabilities that lead to correct prices of derivatives but do not require knowledge of the true probabilities, the expected returns of assets, or the utility preferences of investors. This procedure in continuous time, however, is quite complex, as. we previously showed. We now illustrate it in the discrete time setting..

So what we have is illustrated in Figure 16.3.
What we want is illustrated in Figure 16.4.

![](images/8aee52d8f8c9913b3bd8029000c4089edcbd3e03e394b7f85dc106785fd77838.jpg)
FIGURE 16.3 One-Period Wiener Process with Actual Probability

![](images/fd8598320774447bc150c9a97699cbf4fbc112b75b28f8e0896a979196e6ae31.jpg)
FIGURE 16.4 One-Period Wiener Process with Artificial Probability $q$

Let us define the ratios of probabilities, $q/\phi$ and $(1-q)/(1-\phi)$ , as $\gamma^{s}$ where $s$ indicates the $^+$ or -- state. That is,

$$
\begin{array}{l}{\gamma^{+}=q/\phi}\ {\gamma^{-}=(1-q)/(1-\phi).}\end{array}
$$

The probabilities $q$ and $\phi$ represent different probability measures. The probabilities $\phi$ and $1-\phi$ are said to be measure $P$ and $q$ and $1-q$ are measure Q.10 We can take the expected value of $W_{1}$ under either measure $P$ or measure $\mathcal{Q}$ . Under measure $\mathcal{Q}$ , we have, by definition,

$$
E^{Q}\big(W_{1}\big)=q W_{1}^{+}+(1-q)W_{1}^{-}.
$$

This statement can be rewritten as follows:

$$
E^{\mathcal{Q}}\big(W_{1}\big)=\phi(q/\phi)W_{1}^{+}+(1-\phi)\left[(1-q)/(1-\phi)\right]W_{1}^{-}.
$$

We can write this expectation compactly as

$$
E^{Q}\big(W_{1}\big)=E^{P}\big(\gamma^{s}W_{1}\big).
$$

In other words, we can take the expectation under the. $\mathcal{Q}$ measure by taking the expectation under the $P$ measure, provided we adjust the random process by a new specific stochastic process involving a ratio of probabilities. So $\gamma^{s}$ , which is a ratio of probabilities in state. $s$ is a stochastic process itself. We can easily see this in Equation (16.32). It takes on a value of $q/\phi$ or $(1-q)/(1-\phi)$ in the two states respectively..

Let us extend this result one more period. Figure 16.5 illustrates the process we now have.

Now we must index our ratio of probabilities by time, that is, $\gamma_{t}^{s}$ . First note that the process Starts at $\gamma_{0}=1.0$ 11 The stochastic process of $\gamma_{t}^{s}$ can be derived as follows. First consider.

![](images/dc3078e47410e0644b2d85e1beaac384fe0eea02c09500eb772fc34550fc5b15.jpg)
FIGURE 16.5Two-Period Wiener Process with Probability $q$

$\gamma_{t}^{+}$ , which as we know is $q/\phi$ . The value $q/\phi$ can be expressed as a weighted average of the next two values of the process as shown here:

$$
\begin{array}{r l}&{{\gamma_{1}}^{+}=(\phi){\gamma_{2}}^{++}+(1-\phi){\gamma_{2}}^{+-}}\ &{\quad\quad=(\phi)\left(\frac{q^{2}}{\phi^{2}}\right)+(1-\phi)\left(\frac{q(1-q)}{\phi(1-\phi)}\right)}\ &{\quad\quad=q^{2}/\phi+q(1-q)/\phi}\ &{\quad\quad=\left(q^{2}+q-q^{2}\right)/\phi=q/\phi.}\end{array}
$$

Thus, in the time. $1+$ state, we weight the ratio of the probabilities of the next two values of the process,e $q^{2}/\phi^{2}$ and $q(1-q)/\phi(1-\phi)$ by $\phi$ and $1-\phi$ , respectively. Similarly in the time 1- state, we have for y,

$$
\begin{array}{l}{{{\gamma_{1}}^{-}=(\phi){\gamma_{2}}^{+-}+(1-\phi){\gamma_{2}}^{--}}}\ {{\quad=(\phi)\left[\frac{(1-q)q}{(1-\phi)\phi}\right]+(1-\phi)\frac{(1-q)^{2}}{(1-\phi)^{2}}}}\ {{\quad=(1-q)q/(1-\phi)+(1-q)^{2}/(1-\phi)}}\ {{\quad=(1-q)/(1-\phi).}}\end{array}
$$

And we see that $\gamma_{1}^{-}$ is a probability-weighted average of the next two values of the process. This exercise shows how. $\gamma_{t}$ is a stochastic process. Ordinarily, one would not think that a probability is a stochastic process itself, but in this case, the ratio of probabilities is stochastic. At the time. $1+$ state, there are two upcoming outcomes: y will equal either $q^{2}/\phi^{2}$ with probability $\phi$ or $q(1-q)/\phi(1-\phi)$ with probability $(1-\phi)$ . A similar statement applies in the time. $1-$ state. So we see that $\gamma_{1}^{s}$ is a stochastic process itself with values. as shown in Figure 16.6..

And as we saw, each value is the expectation of what it will be in the next period. So, in general

$$
\begin{array}{r}{\gamma_{t}=E^{P}\big(\gamma_{t+1}^{s}\big).}\end{array}
$$

![](images/d242627da150f7df73c24610199f073f576ae00b801ff199e61e4c8457bc4fc9.jpg)
FIGURE 16.6 Stochastic Process of y

This process $\gamma_{t+1}^{s}$ is the discrete time analog to the Radon-Nikodym derivative and represents a relationship between two equivalent probability measures. Equivalent probability measures are two probability measures that meet certain requirements, the main. one being that any event that is possible under one measure must be possible under the. other and vice versa. In other words, the impossible cannot be created from the possible and the impossible cannot be destroyed from the possible. In continuous time, this. concept is much more difficult, except that it is more easily seen for what it is: a derivative of one probability distribution with respect to another. In discrete time, it is merely a ratio of probabilities, but calculus derivatives are technically not defined in discrete time.. We covered the continuous case in Chapter 15..
