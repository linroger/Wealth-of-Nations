---
tags:
  - '#black_scholes_merton_model'
  - '#euler_rule'
  - '#european_call_option'
  - '#ito_process'
  - '#linear_homogeneity'
  - '#option_pricing'
  - '#partial_differential_equation'
  - '#risk_neutral_approach'
---
# 17.4 USING LINEAR HOMOGENEITY AND EULER'S RULE TO DERIVE THE BLACK-SCHOLES-MERTON MODEL

In Merton's (1973b) classic article on option pricing theory, he demonstrated that the price of a European call option is linearly homogeneous with respect to the asset price and exercise price. Merton derived this result by defining the problem in terms of the rate of return on the option. In this chapter, we shall take a slightly different but economically equivalent approach.

As we previously covered, the price of an option can be obtained by appealing to the risk-neutral or equivalent martingale approach, which changes the probabilities of the expiration value of the underlying asset such that the current asset price is the expected future asset price discounted at the risk-free rate. As such, the expected expiration value of the option is taken using the adjusted probabilities and discounted at the risk-free rate to obtain the well-known Black-Scholes-Merton formula.

An option is an asset, so by definition the price at time $t$ of an option is the expected future value of that option discounted at a rate appropriate for the time value of money and the risk. Consequently, without changing the probability distribution, we can obtain the option pricing formula by taking the expected value of the option at expiration using the actual probabilities and discounting at a rate suitable for the option's risk. In other words,

$$
c_{t}=e^{-k\tau}E{\left(c_{T}\right)},
$$

where $k$ is the risk-adjusted discount rate appropriate for the option and $\tau=T-t$ is the time to expiration. Again, this statement holds by definition for any asset, whether an option or not.

Of course, the value of a European call option at expiration $T$ is

$$
c_{T}={\mathrm{max}}(0,S_{T}-X),
$$

where $S_{T}$ is the underlying asset price at expiration and $X$ is the exercise price. Now observe that this function is linearly homogeneous with respect to the asset price and exercise price, because

$$
\mathrm{max}(0,\lambda S_{T}-\lambda X)=\lambda\mathrm{max}\bigl(0,S_{T}-X\bigr).
$$

Thus, we know that the expiration value of the option is linearly homogeneous, but we are interested in whether the current value of the option is linearly homogeneous. Here we appeal to the aforementioned result that the current value of any asset is the expected future value discounted back to the current time. Determining an expected value is a linear mathematical operation. That is, taking an expectation is a linear operation and discounting merely involves multiplying an expected payoff by a discount factor. Note that a linear operation performed on a linearly homogeneous function preserves its property of linear homogeneity. Discounting an expected payoff, such as by the factor. $e^{-\tilde{k}\tau}$ involves simply multiplying it by a constant, so we preserve the linear homogeneity of the function. Thus, the current price of the option is linearly homogeneous with respect to the asset price and the exercise price. Hence, we can employ Euler's rule, and it will be quite useful.

Applying Euler's rule to the Black-Scholes-Merton model call price, $c_{t}$ , focused on $S_{t}$ and $X$ , we have

$$
S_{t}\frac{\partial c}{\partial S}+X\frac{\partial c}{\partial X}=c\big(S_{t},X\big).
$$

From Chapter 14, we know

$$
\begin{array}{l}{\displaystyle\Delta_{c}=\frac{\partial c}{\partial S}=N\big(d_{1}\big)~\mathrm{and}}\ {\displaystyle\frac{\partial c}{\partial X}=-e^{-r_{c}\tau}N\big(d_{2}\big).}\end{array}
$$

By substituting these derivatives, we attain a statement of the Black-Scholes-Merton model that is consistent with linear homogeneity. We introduce the current price of a zerocoupon bond with par value of $X$ as $B_{t}\equiv e^{-r_{c}\tau}X$ . Hence,

$$
S_{t}\frac{\partial c}{\partial S}+B_{t}\frac{\partial c}{\partial B_{t}}=c\big(S_{t},X\big),
$$

where

$$
\frac{\partial c}{\partial B_{t}}=\frac{\partial c}{\partial X}\frac{\partial X}{\partial B_{t}}=\frac{\partial c/\partial X}{\partial B_{t}/\partial X}=-\frac{e^{-r_{c}\tau}N(d_{2})}{e^{-r_{c}\tau}}=-N(d_{2}).
$$

Alternatively, let us simply start by assuming the option price is linearly homogeneous. with respect to $S_{t}$ and $B_{t}$ , two assets that can be easily traded. Note that we are not starting with any specified stochastic process. Using Euler's rule, we know that the current option price, which is a function of. $S_{t}$ and $t$ , can be expressed as

$$
c_{t}=\gamma S_{t}+\omega B_{t},
$$

where $\gamma$ is $\partial c_{t}/\partial S_{t}$ and $\omega$ is $\partial c_{t}/\partial B_{t}$ . An interpretation of Equation (17.14) is that one call option can be replicated by holding y units of the asset, each worth $S_{t}.$ and $\omega$ units of a risk-free bond with current value $\boldsymbol{B}_{t}=\boldsymbol{X}\boldsymbol{e}^{-\boldsymbol{r}_{c}\tau}$

The total differential of the option price is

$$
d c_{t}=\gamma d S_{t}+\omega d B_{t}.
$$

The differential $d S_{t}$ can be left in this form. We can, however, obtain the exact differential for the risk-free bond, $d B_{t}$ . We simply take the derivative with respect to $t.$

$$
\frac{d B_{t}}{d t}=r_{c}X e^{-r_{c}\tau}=r_{c}B_{t}.
$$

We then obtain the desired differential as

$$
d B_{t}=r_{c}B_{t}d t.
$$

Consequently, the call price differential is

$$
d c_{t}=\gamma d S_{t}+\omega r_{c}B_{t}d t.
$$

At this point, it is helpful to substitute $c_{t}-\gamma S_{t}$ for $\omega B_{t}$ from Equation (17.: leaving us

$$
d c_{t}=\gamma d S_{t}+\left(c_{t}-\gamma S_{t}\right)r_{c}d t.
$$

Now, we assume only that the call price depends on $S_{t}$ and $t$ and that the underlying follows an Ito process expressed as $d\bar{S_{t}}=\alpha\big(\bar{S_{t}},t\big)d t+\sigma\big(\bar{S_{t}},t\big)d\mathrm{W}_{t}$ Ito's lemma can be used to obtain an equivalent expression for the change in the price of the call,

$$
d c_{t}=\frac{\partial c_{t}}{\partial S_{t}}d S_{t}+\frac{\partial c_{t}}{\partial t}d t+\frac{1}{2}\frac{\partial^{2}c_{t}}{\partial{S_{t}}^{2}}\sigma^{2}\big(S_{t},t\big)d t,
$$

from which we can now set Equation (17.20) equal to Equation (17.19). And by choosing y to equal $\partial c_{t}/\partial S_{t}$ , we eliminate the risky term $d S_{t}$ , leaving the following non-stochastic partial differential equation,

$$
c_{t}r_{c}=\frac{\partial c_{t}}{\partial S_{t}}r_{c}S_{t}+\frac{\partial c_{t}}{\partial t}+\frac{1}{2}\frac{\partial^{2}c_{t}}{\partial S_{t}^{2}}\sigma^{2}\big(S_{t},t\big),
$$

which is a second-order partial differential equation. This partial differential equation solution, subject to the boundary condition $c_{T}=\operatorname*{max}\bigl(0,S_{T}-\bar{X}\bigr)$ , depends on the specification of the volatility term.

Several important insights can be gained from linear homogeneity. First, no assumptions were made regarding risk-free hedging. Second, the only assumption made regarding the underlying asset stochastic process is that it follows an Ito process. Third, the drift term of the Ito process has no influence on the resulting partial differential equation. Fourth, if we assume a generic geometric Brownian motion of the form $d S_{t}=\alpha\big(S_{t},t\big)d t+\sigma S_{t}d\mathrm{W}_{t}$ we obtain the Black-Scholes-Merton model. In Appendix 17A, we explore linear homogeneity applied to the arithmetic Brownian motion model.
