# 5.3 BIVARIATE NORMAL PROBABILITY DISTRIBUTION

Suppose now that we have two normally distributed random variables, $x$ and $y$ .The expected values are $\mu_{x}$ and $\mu_{y}$ and the standard deviations are $\sigma_{x}$ and $\sigma_{y}$ . For bivariate normally distributed random variables, the conditional expected values of $y$ and $x$ are linearly related, as indicated by the following:

$$
E(y|x_{a})=\mu_{y}+\rho\left(\frac{\sigma_{y}}{\sigma_{x}}\right)(x_{a}-\mu_{x}),
$$

where $\rho$ is the correlation between $y$ and $x$ . This statement says that if the value of. $x$ is known, the expected value of $y$ is given by the right-hand-side expression. This expectation of $y$ is called the conditional expected value of $y$ given $x_{a}$ . The terms $\mu_{y}$ and $\mu_{x}$ are the unconditional expected values. They are our best estimates of the expected values of $y$ or $x$ given that we know nothing about the value of the other. If $x$ and $y$ are linearly related, then the correlation between $x$ and $y$ can be used to make a better prediction of. $y_{\mathrm{{;}}}$ given that we know the current value of. $x$ , which is $x_{a}$ . If $y$ and $x$ are related in this manner, then the joint distribution of $y$ and $x$ is bivariate normal. The conditional variance of $y$ is related to its unconditional variance by the formula

$$
\sigma_{y|x}^{2}=\sigma_{y}^{2}(1-\rho^{2}).
$$

The probability density function for the bivariate normal is

$$
\begin{array}{r l}&{f(x,y,\rho)=\frac{1}{2\pi\sigma_{x}\sigma_{y}\sqrt{1-\rho^{2}}}}\ &{\exp\left[-\frac{1}{2}\left(\frac{\left(\left(x-\mu_{x}\right)/\sigma_{x}\right)^{2}-2\rho\left(\left(x-\mu_{x}\right)/\sigma_{x}\right)\left(\left(y-\mu_{y}\right)/\sigma_{y}\right)+\left(\left(y-\mu_{y}\right)/\sigma_{y}\right)^{2}}{1-\rho^{2}}\right)\right].}\end{array}
$$

The distribution function or cumulative bivariate normal probability is

$$
\begin{array}{r l r}{\lefteqn{\operatorname*{Pr}(x\leq x_{a},y\leq y_{b}\vert\rho)=\frac{1}{\sigma_{x}\sigma_{y}}\int_{-\infty}^{\frac{x_{a}-\mu_{x}}{\sigma_{x}}}\int_{-\infty}^{y_{b}-\mu_{y}}}\frac{1}{2\pi\sqrt{1-\rho^{2}}}}\ &{}&{\exp\left[-\frac{1}{2}\left(\frac{k^{2}-2\rho k j+j^{2}}{1-\rho^{2}}\right)\right]d k d j.}\end{array}
$$

Because each variable $x$ and $y$ is individually normally distributed, each can be transformed or normalized into a standard normal random variable, which we shall call $z_{1}$ and $z_{2}$ , by the relationships,

$$
z_{1}=\frac{x-\mu_{x}}{\sigma_{x}},\quad z_{2}=\frac{y-\mu_{y}}{\sigma_{y}}.
$$

The standard normal bivariate density is then

$$
f(z_{1},z_{2},\rho)=\frac{1}{2\pi\sqrt{1-\rho^{2}}}\exp\left[-\frac{1}{2}\left(\frac{z_{1}^{2}-2\rho z_{1}z_{2}+z_{2}^{2}}{1-\rho^{2}}\right)\right].
$$

Figure 5.5 illustrates the standard normal bivariate density in three-dimensional space.

The following relationships are useful when dealing with the bivariate normal probability distribution. Let $N(x)$ be the (univariate) normal probability for a variable. $x$ and $N_{2}(x,y;\rho)$ be the bivariate normal probability for the variables. $x$ and $y_{:}$ , which can be normalized or not, with correlation $\rho$ . Then, the following are a handful of useful rules.

$$
\begin{array}{c}{{N_{2}(x,y;\rho)=N_{2}(y,x;\rho)}}\ {{{}}}\ {{N_{2}(-x,y;\rho)+N_{2}(x,y;-\rho)=N(y)}}\ {{{}}}\ {{N_{2}(x,y;\rho)-N_{2}(-x,-y;\rho)=N(x)+N(y)-1.0.}}\end{array}
$$

Computation of the bivariate normal probability is quite challenging, but an analytic approximation developed by Drezner (1978) is often used and gives a high degree of accuracy.6 Using that approximation, let us work a problem involving bivariate standard normal random variables. An Excel routine based on this technique is in Appendix 5A. Let $x=0.74$ $y=-1.13$ and $\rho=0.32$ . We wish to know $\operatorname*{Pr}(x\leq0.74$ $y\le-1.13|0.32)$ . The univariate probabilities as obtained from Excel's ${}={}.$ normsdist() function are $N(0.74)=0.7704$ and $N(-1.13)=0.1292$ . The bivariate normal probability is $N_{2}(0.74,-1.13;0.32)=0.1171$ Let us check out the above relationships:

![](images/a1c4d5abdf494d8a68ba9c89b7a72dfbdc2441322e573001184dfb5c9c8b738d.jpg)
FIGURE 5.5 Bivariate Normal Density

$$
N_{2}(0.74,-1.13,0.32)=0.1171=N(-1.13,0.74,0.32)=0.1171
$$

$$
N_{2}(-0.74,-1.13,0.32)=0.0529,N_{2}(0.74,-1.13,-0.32)=0.0763
$$

$$
0.0529+0.0763=0.1292=N(-1.13)
$$

$$
N_{2}(0.74,-1.13,0.32)=0.1171,N_{2}(-0.74,1.13,0.32)=0.2175
$$

$$
0.1171-0.2175=-0.1004
$$

$$
N(0.74)=0.7704,N(-1.13)=0.1292
$$

Some special cases are worth noting. If either of the values $x$ or $y$ is infinite, then. the bivariate probability reverts to the univariate probability. For example, $\operatorname*{Pr}(x\leq a,y\leq$ $\infty|\rho)=\operatorname*{Pr}(x\leq a)$ . This is because of the condition that. $y\leq\infty$ has no effect because its. probability is 1.0. This fact, of course, also holds if the variables are reversed. If $\rho=0$ , then the bivariate probability is the product of the two univariate probabilities of $x$ and $y$ , that is, $\operatorname*{Pr}(x\leq a,y\leq b|\rho=0)=N(a)N(b)$ . This result reflects the fact that the joint probability of two independent random variables is the product of the marginal probabilities. A few other special relationships hold when. $\rho=1$ , but these conditions are rarely observed. You can look these up in Abramowitz and Stegun (1972).

The bivariate normal probability generalizes into a multivariate normal probability. In finance, one occasionally sees the trivariate normal probability and there are techniques for estimating it, which involve simplification of the relationships among univariate, bivariate, and trivariate densities. For the most part, however, computation of these high-order integrals is extremely time-consuming. Monte Carlo simulation is a good way of getting these results.
