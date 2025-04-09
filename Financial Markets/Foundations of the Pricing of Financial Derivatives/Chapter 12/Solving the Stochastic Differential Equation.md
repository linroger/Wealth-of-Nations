# 12.3 SOLVING THE STOCHASTIC DIFFERENTIAL EQUATION

The equations for the relative return and log return are stochastic processes, as well as stochastic differential equations. A differential equation has a potential solution, which is a function such that the derivatives conform to the differential equation. In this context, a solution would be the asset price at some future time $t.$ , expressed in terms of the asset price at a previous time such as time 0.

To solve the stochastic differential equation, (12.23), we want to obtain a future price $S_{t}$ in terms of a current price, say $S_{0}$ . We take the equation for the log return, Equation (12.13) using $d G_{\mathrm{t}}$ as the LHS, and integrate over the interval O to $t$

$$
\int_{0}^{t}d G_{j}=\int_{0}^{t}\mu d j+\int_{0}^{t}\sigma d W_{j}.
$$

The left-hand side is clearly $G_{t}-G_{0}$ . The first integral on the right-hand side of Equation (12.34) is a standard Riemann integral and equals

$$
\int_{0}^{t}\mu d j=\mu\int_{0}^{t}d j=\mu t.
$$

The second integral on the right-hand side of Equation (12.34) is a stochastic integral and, fortunately, one of the simplest of stochastic integrals. It is obtained as.

$$
\int_{0}^{t}\sigma d W_{j}=\sigma\int_{0}^{t}d W_{j}=\sigma(W_{t}-W_{0}).
$$

In fact, in this case, the stochastic integral is so simple, it is the same as the Riemann integral. The variable $\mathbf{}\mathbf{}{W}_{t}$ is the value of the Brownian motion process at time $t$ . It is quite common that $W_{0}$ is set at zero, so let us do it. So now we have. $\sigma W_{t}$ as the solution to Equation (12.36). Then $G_{t}-G_{0}=\mu t+\sigma W_{t}$ is the solution to Equation (12.34). To get. this solution in terms of $S_{t}$ and $S_{0}$ , we exponentiate this result,

$$
e^{G_{t}-G_{0}}=e^{\mu t+\sigma W_{t}}.
$$

Because $S_{t}=e^{G_{t}}$ , and $S_{0}=e^{G_{0}}$

$$
S_{t}=S_{0}e^{\mu t+\sigma W_{t}}.
$$

Equation (12.38) is presumably the solution to the stochastic differential equation, (12.23). Now, to be absolutely certain that we have the correct solution, we need to check it by applying Ito's lemma to. $S_{t}$ , inserting the derivatives, and determining if we obtain (12.23).. Our stochastic differential equation for. $S_{t}$ obtained from Ito's lemma is.

$$
d S_{t}=\frac{\partial S_{t}}{\partial W_{t}}d W_{t}+\frac{\partial S}{\partial t}d t+\frac{1}{2}\frac{\partial^{2}S_{t}}{\partial W_{t}^{2}}d W_{t}^{2}.
$$

We then insert the partial derivatives that we obtain by differentiating the solution, Equation (12.38). The partial derivatives are

$$
\begin{array}{r}{\frac{\partial S_{t}}{\partial W_{t}}=S_{t}\sigma}\ {\frac{\partial^{2}S_{t}}{\partial W_{t}^{2}}=S_{t}\sigma^{2}}\ {\frac{\partial S_{t}}{\partial{x}}=S_{t}\mu.}\end{array}
$$

Now recall that $d\mathbb{W}_{t}^{2}=d t$ . Substituting these results into Equation (12.39) and rearranging, we obtain:

$$
\frac{d S_{t}}{S_{t}}=\alpha d t+\sigma d W_{t}.
$$

This is the original stochastic process, Equation (12.23). Thus, our solution is correct.
