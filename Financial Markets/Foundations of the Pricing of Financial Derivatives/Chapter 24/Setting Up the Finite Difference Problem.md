---
tags:
  - '#boundary_conditions'
  - '#call_price_valuation'
  - '#explicit_finite_difference_method'
  - '#finite_difference_grid'
  - '#finite_difference_problem'
  - '#ito_lemma'
  - '#lognormal_distribution'
  - '#option_delta'
---
# 24.1 SETTING UP THE FINITE DIFFERENCE PROBLEM

Recall that the call price depends on the underlying price and time or $c_{t}=c(S,t)$ . Following Brennan and Schwartz, we begin by defining a new variable $y=\ln S$ Let $\boldsymbol{\mathscr{w}}$ be defined such that $w(y,t)=c(S,t)$ The goal is to transform a multiplicative distribution (i.e., the. lognormal distribution) to an additive distribution (i.e., the normal distribution). Recall that if $S$ is lognormally distributed, then. $\ln(S)$ is normally distributed. The variable. $w(y,t)$ is the price of the call at time. $t$ in terms of the transformed asset price and time. In other. words, we price the call in terms of the log of the asset price and time. $t.$ . Based on Ito's lemma, we shall need the following:.

$$
\frac{\partial c}{\partial S}=\frac{\partial w}{\partial y}\frac{\partial y}{\partial S}=\frac{\partial w}{\partial y}\frac{1}{S}=\frac{\partial w}{\partial y}e^{-y},
$$

$$
\begin{array}{c c c}{\displaystyle\frac{\partial^{2}c}{\partial S^{2}}=\frac{\partial}{\partial S}\left(\frac{\partial w}{\partial y}e^{-y}\right)=e^{-y}\frac{\partial w/\partial y}{\partial S}+\frac{\partial w}{\partial y}\frac{\partial e^{-y}}{\partial S}}\ {\displaystyle}&{\displaystyle=e^{-y}\frac{\partial^{2}w}{\partial y^{2}}\frac{\partial y}{\partial S}-\frac{\partial w}{\partial y}e^{-2y}=\left(\frac{\partial^{2}w}{\partial y^{2}}-\frac{\partial w}{\partial y}\right)e^{-2y}}\end{array}
$$

$$
{\frac{\partial c}{\partial t}}={\frac{\partial w}{\partial t}}.
$$

Substituting these results into the partial differential equation, we obtain

$$
\frac{\sigma^{2}}{2}\frac{\partial^{2}w}{\partial y^{2}}+\left(r_{c}-\frac{\sigma^{2}}{2}\right)\frac{\partial w}{\partial y}+\frac{\partial w}{\partial t}-r_{c}w=0.
$$

To get a practical solution for $\boldsymbol{\mathscr{w}}$ in this equation, we express it as the difference equation,

$$
\frac{\sigma^{2}}{2}\frac{\Delta^{2}w}{\Delta y^{2}}+\left(r_{c}-\frac{\sigma^{2}}{2}\right)\frac{\Delta w}{\Delta y}+\frac{\Delta w}{\Delta t}-r_{c}w=0.
$$

We then partition a reasonable range of the log of the asset price into finite intervals. For example, the minimum asset price is zero and the maximum is infinity. Suppose we consider only the following prices as feasible:. $0,\Delta y,2\Delta y,\ldots,y-2\Delta y,y-\Delta y,y,y+\Delta y,y+$ $2\Delta y,\ldots,\infty$ . When we implement the technique, we shall need to make. $\Delta y$ as small as possible and we must choose a finite maximum asset price to represent infinity, so let us call it $S_{m a x}$ . In addition $\ln0$ is undefined so we let the minimum $S$ be very close to but not equal to zero. Here we specify $\operatorname*{min}(\ln S)$ as a very small value, $\eta$ 2.

Letting $\tau$ be the time to expiration, we partition the time remaining in the option's life into discrete intervals equaling $\tau,\tau-\Delta t,\tau-2\Delta t,...,2\Delta t,\Delta t,0$ These gradations of time and asset price can be arranged on a grid, as in Table 24.1..

Each dot corresponds to an option price associated with the log of the asset price in the given row and the time to expiration in the given column.

Some of the information in the grid would already be known. For example, we know the following boundary conditions,

$$
c=0\mathrm{if}S=0\mathrm{forall}t.
$$

And because we know that $\ln S=\eta$ when $S$ is very close to zero, we specify this condition as

$$
\begin{array}{r}{\boldsymbol{w}=0\mathrm{if}\boldsymbol{S}^{\mathrm{eq}}\mathrm{close}^{,0}(\mathrm{ln}\boldsymbol{S}=\eta)\mathrm{for~all}\boldsymbol{t}.}\end{array}
$$

This statement permits us to fill in zeroes along the bottom row.

TABLE 24.1 Finite Difference Grid


<html><body><table><tr><td></td><td colspan="7">Time to Expiration</td></tr><tr><td>In S</td><td>T</td><td>T-△t</td><td>T-2△t</td><td>?</td><td>2△t</td><td>△t</td><td></td></tr><tr><td>8</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>y+2△y</td><td>·</td><td>·</td><td></td><td></td><td></td><td>·</td><td></td></tr><tr><td>y+△y</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>y</td><td></td><td></td><td></td><td>·</td><td></td><td></td><td></td></tr><tr><td>y-△y</td><td>·</td><td></td><td>·</td><td>·</td><td></td><td>·</td><td></td></tr><tr><td>y-2△y</td><td></td><td></td><td>·</td><td>·</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>·</td><td>·</td><td></td><td>·</td><td></td></tr><tr><td>2△y</td><td></td><td></td><td>·</td><td>·</td><td></td><td>·</td><td></td></tr><tr><td>△y</td><td></td><td>·</td><td>·</td><td>·</td><td></td><td>·</td><td></td></tr><tr><td>n</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

IABLE 24.2 Partially Filled-in Finite Difference Grid


<html><body><table><tr><td></td><td colspan="8">TimetoExpiration</td></tr><tr><td>In S</td><td>T</td><td>T-△t</td><td>T-2△t</td><td></td><td>2△t</td><td>△t</td><td>0</td></tr><tr><td>S max</td><td>“十</td><td></td><td></td><td></td><td></td><td></td><td>max(O,S -X) max</td></tr><tr><td></td><td></td><td>•(t)+△ye·(t-△t)+△yey·(t-2△t）+△yey·()+△yey·(2△t)+△yey·(△t)+△yey</td><td></td><td></td><td></td><td></td><td>max(0,e°-X)</td></tr><tr><td>y+2△y</td><td></td><td></td><td></td><td></td><td></td><td></td><td>max(0, ey+2△y - X)</td></tr><tr><td>y+△y</td><td></td><td></td><td></td><td></td><td></td><td></td><td>max(0,ey+△y - X)</td></tr><tr><td>y</td><td></td><td></td><td></td><td></td><td></td><td></td><td>max(0,ey -X)</td></tr><tr><td>y-△y</td><td></td><td></td><td></td><td></td><td></td><td></td><td>max(0, ey-2y - X)</td></tr><tr><td>y-2△y</td><td></td><td></td><td></td><td></td><td></td><td></td><td>max(0,ey-2△y - X)</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>max(0,e*-X)</td></tr><tr><td>2△y</td><td></td><td></td><td></td><td></td><td></td><td></td><td>max(0,e2△y - X)</td></tr><tr><td>△y</td><td></td><td></td><td></td><td></td><td></td><td></td><td>max(0,ey - X)</td></tr><tr><td>n</td><td>Q</td><td></td><td></td><td>（</td><td></td><td></td><td>0</td></tr></table></body></html>

When $S\to\infty$ , the first derivative of the call price with respect to the asset price is 1:

$$
\operatorname*{lim}_{S\to\infty}{\frac{\partial c}{\partial S}}=1{\mathrm{~if~}}S\to\infty{\mathrm{~for~all~}}t.
$$

Because

$$
\frac{\partial c}{\partial S}=\left(\frac{\partial w}{\partial y}\right)e^{-y},
$$

we have

$$
{\frac{\partial w}{\partial y}}=e^{y}=S{\mathrm{~for~all~}}t{\mathrm{~when~ln~}}S\to\infty.
$$

This means that once we know the second highest call value, we can obtain the highest value by adding ye' to it. This is equivalent to imposing the standard condition that the option delta is 1 at a very high stock price.

We also know the value of the option at expiration,

$$
c={\mathrm{max}}(0,S_{T}-X){\mathrm{~for~all~}}S{\mathrm{~when~}}t=0.
$$

In terms of $y$ , this is simply

$$
w=\operatorname*{max}(0,e^{y}-X){\mathrm{~for~all~}}y.
$$

Thus, we can fill in the entire right column. So, the grid is now partially filled in, as shown in Table 24.2.

So, let us now take a look at the explicit finite difference method.
