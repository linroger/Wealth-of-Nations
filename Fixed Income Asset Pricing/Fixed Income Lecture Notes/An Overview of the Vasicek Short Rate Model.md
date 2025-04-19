---
title: An Overview of the Vasicek Short Rate Model
cssclasses:
  - academia
tags:
  - interest_rates
  - mean_reversion
  - short_rate_model
  - term_structure
  - vasicek_model
aliases:
  - Interest Rate Model
  - Short Rate
  - Vasicek
key_concepts:
  - Hull-White extension
  - Mean reversion
  - Short rate dynamics
  - Stochastic interest rate model
  - Zero-coupon bond pricing
---

# An Overview of the Vasicek Short Rate Model
# Abstract

The Vasicek model (1977) is one of the earliest stochastic models of the term structure of interest rates. This model,  though it has it’s shortcomings,  has many advantages,  such as analytical tract ability and mean reversion features,  and may be viewed as a short rate model template.

Several short rate models have their foundations rooted in the Vasicek model. The classical Hull-White model (1990a),  for example,  is an extension of the Vasicek model with time dependent parameters 1 .

In the work that follows we derive the short rate implied by the Vasicek model using the integrating factor method and provide an overview of this method and it’s shorthand. Secondly we consider the model dynamics and ﬁnally we apply the model to zero-coupon bond pricing 2 and provide a detailed derivation.

Finally in reviewing the Vasicek model we outline it’s disadvantages,  consider other short rate models and look at the Hull-White extension to this model. The aim of the paper is to provide an overview of the Vasicek model and an introduction into short rate modelling.

# 1. Short Rates

The short rate $r_{t}$ is taken to be the continually compounded annualised interest rate at which one can borrow or lend money for an in nite sim ally short period at a future time t.

Short rate models attempt to model the term structure of instantaneous forward interest rates 3 . Such models come in two ﬂavours,  namely endogenous equilibrium models,  where the short rate term structure is a model output and exogenous arbitrage-free models,  where it is an explicit input. The later is preferred and better explains the interest rate dynamics observed in the market.

In the models that follow the short rate is stochastic and corresponds to the instantaneous forward rate. By modelling the evolution of the short rate we can determine at any future time t the price zero-coupon bond $Z(t,     T)$ maturing at time $\mathrm{T}$ as

$$
Z(t,     T)=\mathbb{E}\left[e x p\left(-\int_{s=t}^{T}r_{s}\;d s\right)|\mathcal{F}_{s}\right]
$$  

which means that instantaneous forward rates can be speciﬁed as follows

$$
f(t,     T)=-\frac{\partial}{\partial T}l n(Z(t,     T))
$$  
# 2. Vasicek Short Rate Model

The Vasicek model describes short interest rates as having the following dynamics

$$
d r_{t}=(\theta-a r_{t})d t+\sigma d B_{t}
$$  

which can also be represented as

$$
d r_{t}=a(b-r_{t})d t+\sigma d B_{t}
$$  

where

- a=Speed of Mean Reversion,  $0\leq a\leq1$
- b = Mean Reversion Level
- $r_{t}=$ Short Rate at time,  t
- $\sigma=$ Short Rate Volatility
- $B_{t}=$ Brownian Motion Process at time,  t
- and $\theta={\mathrm{ab}}$

The Vasicek Model’s drift term exhibits mean reversion,  meaning that over time interest rates will converge to the mean reversion level $b$ with speed $a$ . The $b$ parameter can be thought of as the long term interest rate level. When the short rate wanders above the long term rate it is pulled down and likewise when it drifts below the long term rate it is pushed up.

Figure 1 demonstrates mean reversion manifesting itself as strong resistance and support from which the short rate will bounce to return and converge to the long term interest rate level.

The mean reversion for the Vasicek model is captured within the drift term $d r_{t}\,     =\,     a(b\,     -\,     r_{t})$ ,  where a and b are positive constants. Mathematically we demonstrate this below in table 1 . When the short rate $r_{t}$ drifts above (below) the long term rate $b$ then the change in the Vasicek process is negative (positive) forcing convergence to the long term interest rate level.

# 3. Vasicek Solution for the Short Rate

To solve the SDE described in ( 1 ) for $r_{t}$ we use the the Integrating Factor Method,  outlined in detail in section 4 below,  whereby ( 1 ) is rearranged into the form

$$
d X_{t}+P_{t}X_{t}d t=d B_{t}
$$  

The Integrating Factor $I_{t}$ is set to be $I_{t}\;=\;e^{\int P_{t}d t}$ R . Multiplying both sides of ( 3 ) by $I_{t}$ and integrating leads to an expression for $r_{t}$ .

Applying the Integrating Factor method to the Vasicek process we obtain

$$
d r_{t}+a r_{t}d t=\theta d t+\sigma d B_{t}
$$  

Setting $I_{t}=e^{\int a d t}=e^{a t}$ R ,  since a is a constant and multiplying both sides by $I_{t}$ gives

$$
\underbrace{I_{t}d r_{t}+I_{t}a r_{t}d t}_{d\left(I_{t}r_{t}\right)}=I_{t}\theta d t+I_{t}\sigma d B_{t}
$$  

The Integrating Factor Method says that $d(I_{t}X)+I_{t}P_{t}X d t$ can be reduced to $d(I_{t}X_{t})$ ,  which can be conﬁrmed by applying Itˆo’s Lemma. Applied to ( 5 ) the left-hand side becomes

$$
d(I_{t}r_{t})=I_{t}\theta d t+I_{t}\sigma d B_{t}
$$
$$
d(e^{a t}r_{t})=e^{a t}\theta d t+e^{a t}\sigma d B_{t}
$$  

Integrating over ( s,  t ),  where $0\leq s\leq t$ yields

$$
e^{a t}r_{t}-e^{a s}r_{s}=\int_{u=s}^{t}e^{a u}\:d u+\sigma\int_{u=s}^{t}e^{a u}\:d B_{u}
$$
$$
e^{a t}r_{t}-e^{a s}r_{s}={\frac{\theta}{a}}(e^{a t}-e^{a s})+\sigma\int_{u=s}^{t}e^{a u}\,     d B_{u}
$$  

Collecting $r_{t}$ terms we obtain

$$
r_{t}=\underbrace{e^{-a(t-s)}r_{s}+{\frac{\theta}{a}}(1-e^{-a(t-s)})}_{D r i f t}+\underbrace{\sigma\int_{u=s}^{t}e^{-a(t-u)}\;d B_{u}}_{D i f f u s i o n}
$$  

This is exactly what is required,  namely an expression for the short rate at a future time t.

# 4. Solving SDEs using the Integrating Factor Method

First Order SDEs,  much like First Order ODEs,  can be solved using the Integrating Factor Method outlined below.

# 4.1 Integrating Factor Method
1. Collect terms for $d X_{t}$ and $d t$ and rearrange the SDE into the form
$$
d X_{t}+P_{t}X_{t}d t=d B_{t}
$$  
1. Set the Integrating Factor
$$
I_{t}=e^{\int P_{t}~d t}
$$  
1. Multiply both sides by $I_{t}$ giving
$$
I_{t}d X_{t}+I_{t}P_{t}X_{t}d t=I_{t}d B_{t}
$$  
1. From Ito’s Lemma the left-hand side becomes
$$
I_{t}d X_{t}+I_{t}P_{t}X_{t}d t=d(I_{t}X_{t})
$$ 
1. This leads to
$$
d(I_{t}X_{t})=I_{t}d B_{t}
$$
1. Simple integration can now be used to obtain a result for $X_{t}$
# 4.2 Integrating Factor Shorthand

It is common practice within academic literature to jump straight to step 5 above when solving ﬁrst order SDEs,  which for the Vasicek Model would be as follows

$$
d r_{t}=(\theta-a r_{t})d t+\sigma d B_{t}
$$  

Using Integrating Factor,  $I_{t}=e^{a t}$ we arrive at

$$
d(e^{a t}r_{t})=\theta e^{a t}d t+\sigma e^{a t}d B_{t}
$$  

Integrating over ( s,  t ),  where $0\leq s\leq t$

$$
e^{a t}r_{t}-e^{a s}r_{s}={\frac{\theta}{a}}\left(e^{a t}-e^{a s}\right)+\sigma\int_{u=s}^{t}e^{a u}\,     d B_{u}
$$  

Rearranging for $r_{t}$

$$
r_{t}=e^{-a(t-s)}r_{s}+\frac\theta a\left(1-e^{-a(t-s)}\right)+\sigma\int_{u=s}^{t}e^{-a(t-u)}\;d B_{u}
$$  

# 5 Vasicek Model Dynamics

Inspecting ( 7 ) we observe that the expression for $r_{t}$ is made up of two deterministic terms representing the drift and a stochastic integral representing the diffusion of our process,  from which we can deduce the ﬁrst and second conditional moments.

From the drift terms

$$
\mathbb{E}[r_{t}|\mathcal{F}_{s}]=e^{-a(t-s)}r_{s}+\frac{\theta}{a}(1-e^{-a(t-s)})
$$  

and from diffusion term

$$
\begin{array}{l}{{V a r(r_{t}|\mathcal{F}_{s})=V a r\left(\sigma\int_{u=s}^{t}e^{-a(t-u)}\;d B_{u}\right)}}\\ {{\qquad\qquad=\mathbb{E}\left[\left(\sigma\int_{u=s}^{t}e^{-a(t-u)}\;d B_{u}|\mathcal{F}_{s}\right)^{2}\right]-\underbrace{\mathbb{E}\left[\sigma\int_{u=s}^{t}e^{-a(t-u)}\;d B_{u}|\mathcal{F}_{s}\right]^{2}}_{=0}}}\end{array}
$$

 | {z }

The second term is zero,  since the expectation of a stochastic integral is zero by deﬁnition

$$
\begin{array}{l}{{V a r(r_{t}|F_{s})=\mathbb{E}\left[\left(\sigma\int_{u=s}^{t}e^{-a(t-u)}\;d B_{u}\right)^{2}\vert F_{s}\right]}}\\ {{\ }}\\ {{\ =\sigma^{2}\int_{u=s}^{t}e^{-2a(t-u)}\;d u}}\\ {{\ }}\\ {{\ =\sigma^{2}\left[\frac{e^{-2a(t-u)}}{2a}\right]_{u=s}^{t}}}\\ {{\ }}\\ {{\ =\frac{\sigma^{2}}{2a}\left(1-e^{-2a(t-s)}\right)}}\end{array}
$$  

Note we dropped the expectation operator $\mathbb{E}[.]$ whilst applying Itˆo Isometry,  where $d B_{u}^{2}=d u$ ,  since there is no longer any source of randomness.

Now since $r_{t}$ is a Brownian Motion we know it is normally distributed as follows

$$
\begin{array}{l}{r_{t}\sim N\left(\mathbb{E}[r_{t}|\mathcal{F}_{s}],     V a r\left(r_{t}|\mathcal{F}_{s}\right)\right)}\\ {r_{t}\sim N\left(e^{-a\left(t-s\right)}r_{s}+\cfrac{\theta}{a}(1-e^{-a\left(t-s\right)},     \cfrac{\sigma^{2}}{2a}\left(1-e^{-2a\left(t-s\right)}\right)\right)}\end{array}
$$  

In the limit as $t\to\infty$ we observe

$$
\operatorname*{lim}_{t\to\infty}\mathbb{E}[r_{t}|\mathcal{F}_{s}]=\frac{\theta}{a}
$$  

and

$$
\operatorname*{lim}_{t\rightarrow\infty}V a r(r_{t}|\mathcal{F}_{s})=\frac{\sigma^{2}}{2a}
$$  

Hence in the limiting case the Vasicek model has the following dynamics

$$
r_{t}\sim N\left(\frac{\theta}{a,     },     \frac{\sigma^{2}}{2a}\right)
$$  

It can be seen that the expected value tends to $\left({\frac{\theta}{a}}\right)$ ,  which equals $b$ ,  namely the long term rate or mean reversion level and the variance tends to $\left({\frac{\sigma^{2}}{2a}}\right)$ ,  which is the model variance scaled by the speed of mean reversion.

# 6 Zero Coupon Bond Pricing

In what follows we describe how to price a zero-coupon bond as at a future time t,  which enables us to price a variety of linear and non-linear products. We also draw the reader’s attention to the fact that coupon bearing bonds,  and for that matter any cashﬂow,  can be decomposed into a series of zero-coupon bonds,  see Jamshidian (1989).

To evaluate the price at a future time t of a zero-coupon bond $Z({\mathfrak{t}},     {\mathrm{T}})$ maturing at time T,  where $0\leq t\leq T$ ,  we consider the expected value of the short rate over time

$$
Z(t,     T)=\mathbb{E}[e^{-\int_{u=t}^{T}r_{u}\ d u}|{\mathcal F}_{t}]
$$

We know from the model dynamics that the process is normally distributed and recall from the deﬁnition of the normal moment generating function

$$
\mathbb{E}(e^{X})=e^{\mathbb{E}[X]+\frac{1}{2}V a r(X)}
$$  

Applying the normal moment generating Function to ( 13 )

$$
Z(t,     T)=e^{\mathbb{E}\left[-\int_{u=t}^{T}r_{u}\ d u|\mathcal{F}_{t}\right]+\frac{1}{2}V a r\left(-\int_{u=t}^{T}r_{u}\ d u|\mathcal{F}_{t}\right)}
$$  

Evaluating the $\mathbb{E}[.]$ and $V a r(.)$ terms will lead to an expression for the bond price of the form

$$
Z(t,     T)=A(t,     T)e^{-r_{t}B(t,     T)}
$$  

To derive a closed form solution to equation ( 15 ) we decompose the problem. Firstly we evaluate the integral,  secondly the expectation term and ﬁnally the variance term.

# 6.1 Zero Coupon Bond,  Integral Term

Evaluating the integral term of ( 15 ) using the short rate $r_{t}$ derived in ( 7 ) and paying attention to the relabelling of integration bounds within ( 7 ) from ( s,  t ) to ( t,  T )

$$
\begin{array}{l}{{\displaystyle\int_{u=t}^{T}r_{u}\,     d u=\int_{u=t}^{T}r_{t}e^{-a\left(u-t\right)}\,     d u+\frac{\theta}{a}\int_{u=t}^{T}\left(1-e^{-a\left(u-t\right)}\right)\,     d u+\sigma\int_{u=t}^{T}\int_{s=t}^{u}e^{-a\left(u-s\right)}\,     d B_{s}\,     d u}}\\ {{\displaystyle\qquad\qquad=\left[-\frac{r_{t}e^{-a\left(u-t\right)}}{a}\right]_{u=t}^{T}+\frac{\theta}{a}\left[u+\frac{e^{-a\left(u-t\right)}}{a}\right]_{u=t}^{T}+\sigma\int_{u=t}^{T}\int_{s=t}^{u}e^{-a\left(u-s\right)}\,     d B_{s}\,     d u}}\\ {{\displaystyle\qquad\qquad=r_{t}\left(\frac{1-e^{-a\left(T-t\right)}}{a}\right)+\frac{\theta}{a}\left(\left(T-t\right)-\left(\frac{1-e^{-a\left(T-t\right)}}{a}\right)\right)+\sigma\int_{u=t}^{T}\int_{s=t}^{u}e^{-a\left(u-s\right)}\,     d B_{s}\,     d u}}\end{array}
$$  

# 6.2 Zero Coupon Bond,  Expectation Term

The derivation of the conditional expectation term within ( 15 ) follows from ( 17 ). The expectation of the stochastic integral is zero and therefore after observing the negative sign within the expectation

$$
\mathbb{E}\left[-\int_{u=t}^{T}r_{u}\:d u|\mathcal{F}_{t}\right]=-r_{t}\left(\frac{1-e^{-a(T-t)}}{a}\right)-\frac{\theta}{a}\left((T-t)-\left(\frac{1-e^{-a(T-t)}}{a}\right)\right)
$$  

# 6.3 Zero Coupon Bond,  Variance Term

Likewise the conditional variance term required within ( 15 ) follows from ( 17 ),  where the variance is determined from the diffusion term,  namely the stochastic integral,  since the two determini stic drift terms make no contribution to the variance. This gives

$$
V a r\left(-\int_{u=t}^{T}r_{u}\;d u|\mathcal{F}_{t}\right)=V a r\left(-\sigma\int_{u=t}^{T}\int_{s=t}^{u}e^{-a\left(u-s\right)}\;d B_{s}\;d u\right)
$$  

Knowing $V a r(X)=\mathbb{E}[X^{2}]-\mathbb{E}[X]^{2}$ and that $V a r(-X)=V a r(X)$

$$
\begin{array}{r l r}{\lefteqn{\cdot\left(-\int_{u=t}^{T}r_{u}\,     d u|\mathcal{F}_{t}\right)=V a r\left(\int_{u=t}^{T}r_{u}\,     d u\right)}}\\{=\mathbb{E}\left[\left(\sigma\int_{u=t}^{T}\int_{s=t}^{u}e^{-a\left(u-s\right)}\,     d B_{s}\,     d u\right)^{2}\right]-\underbrace{\mathbb{E}\left[\sigma\int_{u=t}^{T}\int_{s=t}^{u}e^{-a\left(u-s\right)}\,     d B_{s}\,     d u\right]}_{=0}\ .}\end{array}
$$

 | {z

Observe that the expected value of the second stochastic integral is zero by deﬁnition and therefore

$$
V a r\left(-\int_{u=t}^{T}r_{u}\;d u|\mathcal{F}_{t}\right)=\mathbb{E}\left[\left(\sigma\int_{u=t}^{T}\int_{s=t}^{u}e^{-a(u-s)}\;d B_{s}\;d u\right)^{2}\right]
$$  

Using Fubini’s Theorem to switch the integration order allows us reduce the remaining stochastic integrand to a deterministic term,  since via Itˆo’s Isometry $d B_{s}^{2}=d s$ . Careful attention is paid to the upper bound $s=u$ within the inner integral which requires a bounds transformation 4 and this gives

$$
V a r\left(-\int_{u=t}^{T}r_{u}\;d u|\mathcal{F}_{t}\right)=\mathbb{E}\left[\left(\sigma\underbrace{\int_{s=t}^{T}\int_{u=s}^{T}}_{B o u n d s C h a n g e}e^{-a(u-s)}\;d u\;d B_{s}\right)^{2}\right]
$$  

The square term eliminates the source of randomness,  since $d B_{s}^{2}$ becomes $d s$ ,  and hence the expectation operator is no longer required

$$
\begin{array}{l}{{V a r\left(-\displaystyle\int_{u=t}^{T}r_{u}\;d u|\mathcal{F}_{t}\right)=\mathbb{E}\left[\sigma^{2}\displaystyle\int_{s=t}^{T}\left(\displaystyle\int_{u=s}^{T}e^{-a(u-s)}\;d u\right)^{2}\;d s\right]}}\\ {{\quad\quad\quad\quad\quad\quad\quad\quad\quad=\sigma^{2}\displaystyle\int_{s=t}^{T}\left(\displaystyle\int_{u=s}^{T}e^{-a(u-s)}\;d u\right)^{2}\;d s}}\end{array}
$$  

Continuing with simple integration leads to

$$
\begin{array}{c}{{V a r\left(-\displaystyle\int_{u=t}^{T}r_{u}\:d u|\mathcal F_{t}\right)=\sigma^{2}\displaystyle\int_{s=t}^{T}\left(\displaystyle\frac{1-e^{-a(T-s)}}{a}\right)^{2}\:d s}}\\ {{=\sigma^{2}\displaystyle\int_{s=t}^{T}\left(\displaystyle\frac{1-2e^{-a(T-s)}+e^{-2a(T-s)}}{a^{2}}\right)\:d s}}\\ {{=\displaystyle\frac{\sigma^{2}}{a^{2}}\left[s-\displaystyle\frac{2e^{-a(T-s)}}{a}+\displaystyle\frac{e^{-2a(T-s)}}{2a}\right]_{s=t}^{T}}}\end{array}
$$  

giving

$$
V a r\left(-\int_{u=t}^{T}r_{u}\;d u|\mathcal{F}_{t}\right)=\frac{\sigma^{2}}{a^{2}}\left[(T-t)-2\left(\frac{1-e^{-a(T-t)}}{a}\right)+\left(\frac{1-e^{-2a(T-t)}}{2a}\right)\right]
$$  

4 Fubini’s Theorem allows the change of integration order for double and multiple stochastic integrals,  however when the integration bounds are a function of one-another a bounds transformation is required.

# 6.4 Fubini’s Theorem and Change of Integration Bounds

Fubini’s Theorem provides the mechanism to alternate the order of integration of double and higher order stochastic integrals. This provides ﬂexibility to decide which stochastic integral to process ﬁrst,  which was helpful in determining the zero-coupon bond variance term in ( 19 ). It allowed us to ﬁrst apply Itˆo’s Isometry to square the stochastic term $d B_{s}$ making it deterministic $d s$ and thus simplifying the calculation.

Applying Fubini’s Theorem is straightforward when we are dealing with constant integration limits,  however some thought is required if integration bounds are a function of one-another. In such cases we follow the below steps.

# Bounds Transformations,  Step by Step

Consider the following double integral where we wish to apply Fubini’s Theorem to reverse the integration order.

$$
\int_{x=a}^{x=b}\int_{y=c}^{y=f(x)}[.]\;d y\;d x
$$  

1. Plot the area represented by the original integration bounds,  ignoring the function being integrated.
1. First start with the inner integral and chart the area bounded by the limits of the inner integral. Always plot functional bounds on the y-axis. In this case we plot $y\,     =\,     f(x)$ on the y-axis.
1. Next chart the area bounded by the outer integral’s limits on the same chart,  giving the net area captured by the limits of the inner and outer integrals.
1. Replot the same area,  reﬂected in the $y=x$ axis,  this is equivalent switching the integration order. Again we do this in stages,  ﬁrst for the new inner and then the new outer integral,  inverting any functional limits.
1. Swap the axis of the original chart and visualise the region captured by the original integration limits reﬂected in the $y=x$ axis.
1. Next plot the new y limits that capture the same area as the original chart,  but reﬂected in $y=x$ axis. Remember to invert any functional limits,  in this case $x=f^{-1}(y)$ .
1. Repeat the process for the new x limits,  again inverting any functional limits.
1. Finally read the new integration bounds from the resulting bounds chart,  in the correct order,  starting with the inner then outer integral.
# Bounds Transformations,  Example

Next we outline the above step by step process providing a graphical representation of the bounds in equation ( 19 ),  namely

$$
\int_{u=t}^{T}\int_{s=t}^{u}[.]\;d s\;d u
$$  

Following the steps outlined above,  we plot the area captured by the original integral. First by charting the inner integral limits in $s$ on the y-axis,  to allow us to plot $s\,     =\,     u$ ,  then the outer integral limits in $u$ on the x-axis. It can be seen that the bounds capture the shaded area in ﬁgure 4 below.

Next we follow the steps outlined above for the reﬂection in $y=x$ . We reﬂect the image from ﬁgure 4 in the $y=x$ axis,  here the $s=u$ axis. We swap the $\mathbf{X}$ and y-axis ( here $s$ and $u$ ) and invert all functional limits,  so in this case $s=u$ becomes $u=s$ .

We infer the limits that create the area required ﬁrst starting with the new inner integral and then the outer one. This allows us to observe the bounds transformation and read off the corresponding values,  see ﬁgure 6 below. Note we have deduced the $s=T$ via reﬂection in $s=u$ .

This leads to the bounds transformation as shown in equation ( 19 )

$$
\int_{u=t}^{T}\int_{s=t}^{u}[.]\;d s\;d u\longrightarrow\int_{s=t}^{T}\int_{u=s}^{T}[.]\;d u\;d s
$$  

# 6.5 Zero Coupon Bond Pricing

Returning to the Zero Coupon Bond Pricing formula ( 13 ) having derived all the terms required

$$
Z(t,     T)=e^{\mathbb{E}\left[-\int_{u=t}^{T}r_{u}\ d u|\mathcal{F}_{t}\right]+\frac{1}{2}V a r\left(-\int_{u=t}^{T}r_{u}\ d u|\mathcal{F}_{t}\right)}
$$ 

Substituting the conditional expectation ( 18 ) and variance ( 21 )

$$
\begin{array}{r}{Z(t,     T)=e^{\left(-r t\left(\frac{1-e^{-a(T-t)}}{a}\right)-\frac{\theta}{a}\left((T-t)-\left(\frac{1-e^{-a(T-t)}}{a}\right)\right)+\frac{\sigma^{2}}{2a^{2}}\left[(T-t)-2\left(\frac{1-e^{-a(T-t)}}{a}\right)+\left(\frac{1-e^{-2a(T-t)}}{2a}\right)\right]\right)}}\end{array}
$$

Factorize the common factor in ( 22 ) by setting

$$
B(t,     T)=\left({\frac{1-e^{-a(T-t)}}{a}}\right)
$$ 

Substituting ( 23 ) into ( 22 )

$$
\begin{array}{r}{Z(t,     T)=e^{\left(-r_{t}B(t,     T)-\frac{\theta}{a}((T-t)-B(t,     T))+\frac{\sigma^{2}}{2a^{2}}\left[(T-t)-2B(t,     T)+\left(\frac{1-e^{-2a(T-t)}}{2a}\right)\right]\right)}}\end{array}
$$  

Evaluating $\scriptstyle\left({\frac{1-e^{-2a(T-t)}}{2a}}\right)$  in terms of $B(t,     T)$

$$
\begin{array}{c}{B(t,     T)=\displaystyle\left(\frac{1-e^{-a(T-t)}}{a}\right)}\\ {\Rightarrow B(t,     T)^{2}=\displaystyle\frac{1-2e^{-a(T-t)}+e^{-2a(T-t)}}{a^{2}}}\\ {\Leftrightarrow e^{-2a(T-t)}=a^{2}B(t,     T)^{2}-1+2e^{-a(T-t)}}\end{array}
$$ 

Therefore

$$
\begin{array}{r l r}&{}&{\left(\frac{1-e^{-2a(T-t)}}{2a}\right)=\left(\frac{1-a^{2}B(t,     T)^{2}+1-2e^{-a(T-t)}}{2a}\right)}\\ &{}&{=\left(\frac{2-2e^{-a(T-t)}}{2a}\right)-\left(\frac{a^{2}B(t,     T)^{2}}{2a}\right)}\\ &{}&{=\left(\frac{1-e^{-a(T-t)}}{a}\right)-\left(\frac{a^{2}B(t,     T)^{2}}{2a}\right)}\\ &{}&{=B(t,     T)-\left(\frac{a B(t,     T)^{2}}{2}\right)}\end{array}
$$ 

Substituting ( 25 ) into ( 24 )

$$
\begin{array}{r l}&{Z(t,     T)=e^{\left(-r_{t}B(t,     T)-\frac{\theta}{a}((T-t)-B(t,     T))+\frac{\sigma^{2}}{2a^{2}}\left[(T-t)-2B(t,     T)+B(t,     T)-\left(\frac{a B(t,     T)^{2}}{2}\right)\right]\right)}}\\ &{\quad\quad\quad=e^{\left(-r_{t}B(t,     T)-\frac{\theta}{a}((T-t)-B(t,     T))+\frac{\sigma^{2}}{2a^{2}}\left[(T-t)-B(t,     T)-\left(\frac{a B(t,     T)^{2}}{2}\right)\right]\right)}}\end{array}
$$ 

Collecting $(T-t)$ and $B(t,     T)$ terms

$$
\begin{array}{r l r}&{}&{Z(t,     T)=e^{\left(-r_{t}B(t,     T)-\left((T-t)-B(t,     T)\right)\left(\frac{\theta}{a}+\frac{\sigma^{2}}{2a^{2}}\right)-\left(\frac{\sigma^{2}a B(t,     T)^{2}}{4a^{2}}\right)\right)}}\\ &{}&{=e^{\left(-r_{t}B(t,     T)+\left(B(t,     T)-(T-t)\right)\left(\frac{\theta}{a}-\frac{\sigma^{2}}{2a^{2}}\right)-\left(\frac{\sigma^{2}B(t,     T)^{2}}{4a}\right)\right)}}\\ &{}&{=e^{-r_{t}B(t,     T)}e^{\left((B(t,     T)-(T-t))\left(\frac{\theta}{a}-\frac{\sigma^{2}}{2a^{2}}\right)-\left(\frac{\sigma^{2}B(t,     T)^{2}}{4a}\right)\right)}}\end{array}
$$  

Hence we have a solution for $Z(t,     T)$ of the desired functional form,  namely

$$
Z(t,     T)=A(t,     T)e^{-r_{t}B(t,     T)}
$$  

where

$$
\begin{array}{r}{A(t,     T)=e^{\Big((B(t,     T)-(T-t))\Big(\frac{\theta}{a}-\frac{\sigma^{2}}{2a^{2}}\Big)-\Big(\frac{\sigma^{2}B(t,     T)^{2}}{4a}\Big)\Big)}}\end{array}
$$
$$
B(t,     T)=\left({\frac{1-e^{-a(T-t)}}{a}}\right)
$$ 
# 7. Disadvantages of the Vasicek Model

The Vasicek Model has several disadvantages which we list below.

1. It is endogenous with time homogeneous parameters that do not vary over time. As such short rate term structure is an output not an input.
1. Vasicek short rates can be negative for certain combinations of model parameters. Although negative interest rates have indeed been observed in Non-Deliverable Forwards,  in Switzerland & Japan. This is neither typical nor as frequent an observation as implied by this model. 3. There is no term structure of volatility. Volatility is assumed constant 5 . 4. Some observed short rate term structures are difﬁcult and sometimes impossible to ﬁt with this model. 5. It is a one factor model. It assumes that short rates are $100\%$ correlated and can only cater for parallel shifts in the yield curve.

# 8. Other Short Rate Models

Other short rate models were developed,  both endogenous and exogenous to address the shortcomings of the Vasicek and other preceding short rate models. Consequently there are several short rate models which have similar but different functional forms,  some of which are listed in table 2 .

The Vasicek model provided a foundation for these models. For example scaling the Vasicek diffusion term by $\sqrt{r_{t}}$ gives the Cox,  Ingersoll and Ross model,  setting the Vasicek $a$ parameter and making θ time dependent to zero leads to the Ho-Lee Model. Likewise making the all the Vasicek parameters time dependent leads to the Hull-White (1990a) model.

# 9. The Extended Vasicek / Hull-White Model

The Hull-White (1990a) Model below,  is also known as the Extended Vasicek Model. It is in essence the very same model,  but with time dependent parameters.

$$
d r_{t}=(\theta_{t}-a_{t}r_{t})d t+\sigma_{t}d B_{t}
$$  

The Hull-White Model appears in it’s most generic case with the $\theta_{t},     a_{t}$ and $\sigma_{t}$ parameters being deterministic and time dependent,  however it is not unusual to see the Hull White Model with any combination of these parameters ﬁxed. The Hull-White model can be implemented as a series of discrete Vasicek models. The extended Vasicicek model attempts to deal with the disadvantages highlighted in section 7 .

Hull & White developed this model further into a two factor model. This was due to one factor models only catering for short rates that are $100\%$ correlated. This in turn only allows for parallel moves resulting yield curves. The two factor Hull-White model has a stochastic mean reversion term,  giving the model richer explanatory power. The 2 factor model process is outlined below.

$$
\begin{array}{r l}&{d r(t)=(\theta(t)+u(t)-a r(t))d t+\sigma_{1}d B_{1}(t)}\\ &{d u(t)=-b u(t)+\sigma_{2}d B_{2}(t)}\end{array}
$$

with

$$
d B_{1}(t)d B_{2}(t)=\rho d t
$$  
# Conclusion

In summary the short rate is the instantaneous forward rate at which one can borrow or lend money for an in nite sim ally short period at a future time t. Short rate models can be endogenous or exogenous and the term structure of rates can be a model output or input respectively. The later is preferred and a better ﬁt of market rates.

The Vasicek model and it’s mean reversion feature were examined,  as well as the possible functional forms of the resulting yield curve. The short rate was derived from the Vasicek SDE using the integrating factor method and model dynamics were considered with particular interest in the limiting case.

The closed form solution for zero-coupon bond prices was derived and the procedure for the change of integration bounds when applying Fubini’s theorem outlined. Finally the model shortcomings were discussed and other short rate models considered,  including the Hull-White extension to the Vasicek model,  which were aimed at addressing these shortcomings.