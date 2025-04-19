---
tags:
  - ito_calculus
  - ito_lemma
  - ode
  - sde
aliases:
  - Ito's Lemma
  - ODE vs SDE
  - SDE Solutions
key_concepts:
  - Integration of SDE
  - Ito's lemma application
  - Ordinary differential equation
  - SDE solution difference
  - Stochastic differential equation
---

# 12.4 SOLUTIONS TO STOCHASTIC DIFFERENTIAL EQUATIONS ARE NOT ALWAYS THE SAME AS SOLUTIONS TO CORRESPONDING ORDINARY DIFFERENTIAL EQUATIONS

Let us see how solving a stochastic differential equation (SDE) is different from solving an ordinary differential equation (ODE). Consider the ordinary differential equation:

$$
d y_{t}=y_{t}d W_{t},
$$

where $\mathbf{}\mathbf{}{W}_{t}$ is non-stochastic. Remember that this means that we are absolutely certain of the value of $\mathbf{}\mathbf{}{W}_{t}$ . This is a fairly simple ODE. Assuming $y_{t}>0$ , we start by rewriting the equation as

$$
\frac{1}{y_{t}}\frac{d y_{t}}{d W_{t}}d W_{t}=d W_{t}.
$$

We now integrate over 0 to $t$

$$
\intop_{0}^{t}\frac{1}{y_{s}}\frac{d y_{s}}{d W_{s}}d W_{s}=\intop_{0}^{t}d W_{s}.
$$

With $W_{0}=0$ , the solution is $\ln{\boldsymbol{y}_{t}^{}}=\boldsymbol{W}_{t}$ or alternatively, $\boldsymbol{y}_{t}=\boldsymbol{e}^{\boldsymbol{W}_{t}}$ 8.

Now we let $\mathbf{}\mathbf{}{W}_{t}$ be stochastic. We start by proposing a general form for the solution. Specifically, we shall say that $y_{t}=e^{x_{t}}$ . In other words, $x_{t}$ is some function that solves the equation and in which. $x_{t}$ is a function of $\mathbf{}\mathbf{}{W}_{t}$ . In the special case. $x_{t}=0$ , we have $y_{0}=1$ In the ODE case, $x_{t}=W_{t}$ . First, we use Ito's lemma on $x_{t}$ and obtain

$$
d x_{t}=\frac{\partial x_{t}}{\partial y_{t}}d y_{t}+\frac{1}{2}\frac{\partial^{2}x_{t}}{\partial y_{t}^{2}}d{y_{t}}^{2}.
$$

The partial derivatives are $\partial x_{t}/\partial y_{t}=1/y_{t}$ and $\partial^{2}x_{t}/\partial y_{t}^{2}=-(1/y_{t}^{2})$ . We also have $d y_{t}=$ $y_{t}d\mathbb{W}_{t}$ and $d y_{t}^{2}=y_{t}^{2}d t$ , due to the properties of $d\mathbb{W}_{t}$ . Substituting these results, we obtain

$$
d x_{t}=d W_{t}-\frac{1}{2}d t.
$$

Now we perform the integration,

$$
\intop_{0}^{t}d x_{s}=\intop_{0}^{t}d W_{s}-\intop_{0}^{t}\frac{1}{2}d s
$$

$$
x_{t}-x_{0}=W_{t}-t/2.
$$

With $x_{t}=\ln y_{t}$ then

$$
y_{t}=e^{\mathrm{W}_{t}-t/2}.
$$

Notice that now we have an additional term $t/2$ . Thus, at least in this common situation, and quite often otherwise, the solution to an SDE is not the same as a solution to an ODE.
