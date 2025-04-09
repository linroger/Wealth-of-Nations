# 15.5 CHANGING THE DRIFT IN A CONTINUOUS TIME STOCHASTIC PROCESS

For applications of Girsanov's theorem in finance, the random variable we deal with is often a stochastic process, and in many cases, the random variable will be a Brownian motion, $\mathbf{}\mathbf{}{W}_{t}$ , such that

$$
\mathrm{W}_{t}=\int_{0}^{t}d\mathrm{W}_{j},
$$

where we set $W_{0}=0$ and the increments are distributed with expected value zero and variance $d t$ 4 The density of. $\mathbf{}\mathbf{}{W}_{t}$ is5

$$
f(\mathrm{W}_{t})=\frac{1}{\sqrt{2\pi t}}e^{-\frac{1}{2}\frac{\mathrm{W}_{t}^{2}}{t}}.
$$

We wish to change this Brownian motion into another process that has a new probability measure $\mathcal{Q}$ . We shall shift the distribution by the amount $\gamma_{t}$ . In later applications, we shall see that $\gamma_{t}$ will become an extremely simple function of $t.$ , but for now let us leave it unspecified.

So what we want is a new Brownian motion that has expected value of $\gamma_{t}$ .What will accomplish this trick is to designate.

$$
\phi_{t}=e^{\stackrel{t}{\int}\gamma_{u}d W_{u}-\frac{1}{2}\stackrel{t}{\int}\gamma_{u}^{2}d u}.
$$

For this transformation to be possible, we must impose a constraint on the behavior of $\gamma_{u}$ Specifically, we require that.

$$
E\left(\overset{t}{\underset{e^{0}}{\int}}\gamma_{u}^{2}d u\right)<\infty.
$$

This statement is called the Novikov condition. In simple terms it means that the variation in $\gamma_{u}$ must be finite. For all our applications, the Novikov condition will be met.6.

If these requirements are met, then $\gamma_{t}$ can be shown to be a martingale. Let us first apply Ito's lemma on $\phi_{t}$

$$
d\phi_{t}=\frac{\partial\phi_{t}}{\partial W_{t}}d W_{t}+\frac{1}{2}\frac{\partial^{2}\phi_{t}}{\partial W_{t}^{2}}d W_{t}^{2}.
$$

First, we find the partials?

$$
\begin{array}{r l}&{\displaystyle\frac{\partial\phi_{t}}{\partial W_{t}}=\frac{\partial\left({e_{e}^{\prime}}{{{f_{y}}_{u}}}d{{\mathbf{v}}_{v}}-\frac{1}{2}\int{{{\gamma}_{u}}^{2}}d{{u}}\right)}{\partial W_{t}}}\ &{\displaystyle=\phi_{t}\frac{\partial\left(\displaystyle\int{{{\gamma}_{u}}}d{{\mathbf{w}}_{v}}-\frac{1}{2}\int{{{\gamma}_{u}}^{2}}d u\right)}{\partial W_{t}}}\ &{\displaystyle=\phi_{t}{{\gamma}_{t}}.}\end{array}
$$

And, because $\gamma_{t}$ is not determined by $\mathbb{W}_{t}$ , the second derivative is

$$
\frac{\partial^{2}\phi_{t}}{\partial W_{t}^{2}}=0.
$$

So

$$
d\phi_{t}=\phi_{t}\gamma_{t}d W_{t}=e^{\int\gamma_{u}d W_{u}-\frac{1}{2}\int_{0}^{t}\gamma_{u}^{2}d u}\gamma_{t}d W_{t}.
$$

Now let us consider the value at $t=0$

Now we have

$$
\phi_{0}=e^{0}\stackrel{\textstyle()}{\displaystyle\int}\gamma_{u}d\mathbb{W}_{u}-\frac{1}{2}\stackrel{\textstyle()}{\displaystyle\int}\gamma_{u}^{2}d u}{\gamma_{0}d\mathbb{W}_{0}}=e^{0}=1.
$$

$$
\begin{array}{r l}&{\displaystyle\int d\phi_{u}=\int_{0}^{t}\phi_{u}\gamma_{u}d W_{u}=\phi_{t}-\phi_{0},\mathrm{so}}\ &{~0}\ &{\displaystyle~t}\ &{\phi_{t}-1=\int\phi_{\mu}\gamma_{u}d W_{u},}\ &{~0}\ &{\mathrm{and}~\phi_{t}=1+\displaystyle\int\phi_{u}\gamma_{u}d W_{u}.}\end{array}
$$

Because $d\mathbb{W}_{u}$ on the right-hand side is known to be a martingale, its expectation is zero and, therefore, $E(\phi_{t})=1=\phi_{0}$ . Consequently, $\phi_{t}$ is a martingale.

Thus, we can now be certain that Girsanov's theorem applies. Our Brownian motion can be transformed as follows:

$$
\mathbb{W}_{t}^{\mathcal{Q}}=\mathbb{W}_{t}-\int_{0}^{t}\gamma_{u}d u,
$$

where $\mathbb{W}_{t}^{Q}$ is a Wiener process under the new probability measure $\mathrm{Pr}^{\mathrm{Q}}$ such that

$$
\frac{d\operatorname{Pr}\mathcal{Q}}{d\operatorname{Pr}}=\phi_{\mathcal{Q}}.
$$

Remember that $\phi$ is the Radon-Nikodym derivative.

We shall ultimately need the Wiener differential, $d\mathbb{W}_{t}^{Q}$ , which is obtained as follows:

$$
\begin{array}{r l}&{\displaystyle{\mathbb{W}_{t}^{\mathcal{Q}}=\boldsymbol{W}_{t}-\int_{0}^{t}\gamma_{u}d u},}\ &{\displaystyle~0_{\quad t}}\ &{\displaystyle{\mathbb{W}_{t}^{\mathcal{Q}}-\boldsymbol{W}_{t}=-\int_{0}^{\tau_{u}}d u\quad\mathrm{implies}}}\ &{\displaystyle d\boldsymbol{W}_{t}^{\mathcal{Q}}-d\boldsymbol{W}_{t}=-\gamma_{t}d t,\quad\mathrm{so}}\ &{\displaystyle d\boldsymbol{W}_{t}^{\mathcal{Q}}=d\boldsymbol{W}_{t}-\gamma_{t}d t.}\end{array}
$$

Now let us step back and think about how this result is important for our purposes. We shall want to convert our asset price process to a martingale. This will remove the drift and permit us to price the option by evaluating its expected future value under the new probability measure. When we remove the drift, what we are doing is removing the risk. premium and the risk-free rate. If we know the value of the risk premium, it would be no. problem: We would simply subtract it out. But we do not know what the risk premium is. We do not know how much of the asset's expected return to remove. We do know, however, that if we remove just enough that the asset return is a martingale, then we require no discounting whatsoever. So the trick is to change the probability distribution so that the asset return is a martingale. Here is where the finance ends and the math takes over. Girsanov's theorem tells us how to change a probability distribution to leave it the same type of distribution with the same variance but with a different drift. What we have just seen is that the Brownian motion process, $\mathbf{}\mathbf{}{W}_{t}$ , can be changed such that it is still a martingale. Because the asset price process is a simple transformation of the Brownian motion process, it should be easy to transform it as well into a martingale.

We have seen that we are subtracting a function $\gamma_{t}$ . This means that y can potentially change with $t$ We are somewhat lucky here, because for our purposes $\gamma_{t}$ is a very simple function of $t\colon\gamma_{t}=\gamma t$ 8 Now notice what we obtain for our Radon-Nikodym derivative:

$$
\phi_{t}=e^{\int\gamma d W_{u}-\frac{1}{2}\int}\displaylimits_{0}^{t}\gamma^{2}d u=e^{\gamma\int d W_{u}-\frac{1}{2}\gamma^{2}\int d u}.
$$

In other words, if we multiply the density function of $\mathbf{}\mathbf{}{W}_{t}$ by $\phi_{t}$ as specified, we should obtain the density function for a new Brownian motion, which we shall call $\mathbb{W}_{t}^{Q}$ , and in which the expected value has been shifted by $\gamma t$ Let us see. Given,

$$
\begin{array}{l l}{f(W_{t})=\displaystyle\frac{1}{\sqrt{2\pi t}}e^{-(W_{t}^{2})/2t},}&{\mathrm{and}}\ {\frac{d\mathrm{Pr}^{Q}}{d\mathrm{Pr}}=e^{(\gamma W_{t}-\gamma^{2}t)/2},}\end{array}
$$

we obtain by multiplication

$$
\begin{array}{l}{{f(W_{t})=\displaystyle\frac{d\mathrm{Pr}^{Q}}{d\mathrm{Pr}}=\frac{1}{\sqrt{2\pi t}}e^{-(W_{t}^{2}/2t+\gamma W_{t}-\gamma^{2}t/2)}}}\ {{~=\displaystyle\frac{1}{\sqrt{2\pi t}}e^{-(1/2)\left(\frac{W_{t}-\gamma_{t}}{t}\right)^{2}}~.}}\end{array}
$$

Equation (15.28) is the density for a Brownian motion with its zero expected value shifted by $-\gamma t$ . So

$$
\mathbb{W}_{t}^{Q}=\mathbb{W}_{t}-\gamma t.
$$

To recap, we have that. $\mathbf{}\mathbf{}{W}_{t}$ is a Brownian motion under the probability measure Pr, such that

$$
\begin{array}{c}{{E^{P}(W_{t})=W_{0}=0}}\ {{E^{P}(W_{t}^{Q})=E^{P}(W_{t}-\gamma t)=E^{P}(W_{t})-\gamma t}}\ {{=0-\gamma t.}}\end{array}
$$

The first statement defines that. $\mathbf{}\mathbf{}{W}_{t}$ is a Brownian motion under. $\mathrm{Pr}.$ The second statement says that under $\mathrm{Pr},\mathrm{W}_{t}^{Q}$ is not a Brownian motion. Its expectation, $-\gamma t$ , is not zero, except at $t=0$ , and varies with $t$ . But $\mathbb{W}_{t}^{Q}$ is a Brownian motion under. $\mathcal{Q}$

$$
E^{\mathcal{Q}}(W_{t}^{\mathcal{Q}})=W_{0}^{\mathcal{Q}}=0.
$$

This statement follows because. $\mathbf{}\mathbf{}{W}_{t}$ and $\mathbb{W}_{t}^{\operatorname{Q}}$ both start at a value of zero. Under. $Q,W_{t}$ is not a Brownian motion because

$$
E^{\mathcal{Q}}(W_{t})=E^{\mathcal{Q}}(W_{t}^{\mathcal{Q}}+\gamma t)=E^{\mathcal{Q}}(W_{t}^{\mathcal{Q}})+\gamma t=\gamma t.
$$

When we say that some random process, such as $\mathbf{}\mathbf{}{W}_{t}$ Or $\mathbb{W}_{t}^{\operatorname{Q}}$ , is a Brownian motion under a given measure, we are saying that the probabilities of its possible paths are assigned such that its central property, a constant expectation of zero, is preserved. When the probabilities are changed such that the process no longer has a zero expected value, it is no longer the same thing. But another process can and in this case does have the property of a Brownian motion under the new probability measure.
