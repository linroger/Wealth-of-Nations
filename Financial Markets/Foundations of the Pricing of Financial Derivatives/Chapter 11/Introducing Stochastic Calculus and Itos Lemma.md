---
tags:
  - derivative_pricing
  - ito_lemma
  - ito_process
  - stochastic_calculus
  - wiener_process
aliases:
  - Ito Process
  - Ito's Lemma
  - Stochastic Calc
key_concepts:
  - Derivative pricing example
  - Ito process definition
  - Ito's lemma application
  - Stochastic vs. ordinary calculus
  - Taylor series expansion
---

# 11.2 INTRODUCING STOCHASTIC CALCULUS AND ITO'S LEMMA

In ordinary calculus, the variables are non-stochastic, which simply means that when we. talk about a particular value of. $x$ , that value is known for certain. When. $x$ is stochastic, we leave the world of ordinary calculus and enter the world of stochastic calculus. There we cannot talk about a particular value of $x$ . Instead, we must talk about a set of possible values of $x$ that are generated according to a probability distribution. In stochastic calculus,. results are proven by demonstrating what happens when squared values of a variable are. multiplied by probabilities. A result is said to hold in "mean square limit."1 A more formal. statement of this concept is presented later in this chapter..

# 11.2.1 Generalized It0 Process

Let us now propose that $x$ is stochastic and follows an Ito process, such as $d\mathbb{W}_{t}$ , or a more generalized process such as

$$
d x=\mu(x,t)d t+\sigma(x,t)d\mathrm{W}_{t}.
$$

Recall that $d\mathbb{W}_{t}=\varepsilon_{t}{\sqrt{d t}}$ .With the expressions $\mu(x,t)$ and $\sigma(x,t)$ , we are allowing the expectation and variance of $x$ to be functions of the level of $x$ and time $t.$ Note that $\mu$ and $\sigma$ depend on, at most, the stochastic variable $x$ and time $t$

Now suppose that we go back to the unspecified function $\boldsymbol{F}(\boldsymbol{x},t)$ and examine the Taylor series expansion when. $x$ is stochastic. Again, we emphasize that the function $F$ depends on at most variables. $x$ and $t$ 2 Although $d t^{2}$ is still zero because time is not stochas-. tic, $d x^{2}$ is not zero. Recalling that $d\mathbb{W}_{t}^{2}=d t$ , we square the generalized Ito process defined. in Equation (11.3) and thus we have.

$$
\begin{array}{r l}&{\boldsymbol{d}\boldsymbol{x}^{2}=\left[\mu(\boldsymbol{x},t)\boldsymbol{d}t+\sigma(\boldsymbol{x},t)\boldsymbol{d}W_{t}\right]^{2}}\ &{\qquad=\mu(\boldsymbol{x},t)^{2}\boldsymbol{d}t^{2}+\sigma(\boldsymbol{x},t)^{2}\boldsymbol{d}W_{t}^{2}+2\mu(\boldsymbol{x},t)\sigma(\boldsymbol{x},t)\boldsymbol{d}t\boldsymbol{d}W_{t}.}\end{array}
$$

Note that $d\mathbb{W}_{t}d t$ is zero because

$$
d t d W_{t}=d t\varepsilon_{t}\sqrt{d t}=\varepsilon_{t}d t^{3/2}.
$$

And this expression goes to zero because of the power of $d t$ higher than one. Hence,.

$$
d x^{2}=\sigma^{2}(x,t)d\mathrm{W}_{t}^{2}.
$$

For Taylor series expansion purposes, we also examine dxdt or

$$
d x d t=\left[\mu(x,t)d t+\sigma(x,t)d\mathrm{W}_{t}\right]d t=\mu(x,t)d t^{2}+\sigma(x,t)d\mathrm{W}_{t}d t=0,
$$

because, as just noted, $d\mathbb{W}_{t}d t$ goes to zero in the limit.

So, now our Taylor series expansion when $x$ is stochastic is

$$
d F={\frac{\partial F}{\partial x}}d x+{\frac{\partial F}{\partial t}}d t+{\frac{1}{2}}{\frac{\partial^{2}F}{\partial x^{2}}}d x^{2}.
$$

Note that we do not have to consider higher-order terms, as $d x^{3}$ would go to zero, because $d x^{2}$ is $d t$ .With this setup, we are now ready to express Ito's lemma.

# 11.2.2 Ito Lemma

Assuming $x$ follows a generalized Ito process expressed as

$$
d x=\mu(x,t)d t+\sigma(x,t)d\mathrm{W}_{t},
$$

where $\boldsymbol{F}=\boldsymbol{F}(\boldsymbol{x},t)$ , subject to certain technical constraints,

$$
d F={\frac{\partial F}{\partial x}}\left[\mu(x,t)d t+\sigma(x,t)d W\right]+{\frac{\partial F}{\partial t}}d t+{\frac{1}{2}}{\frac{\partial^{2}F}{\partial x^{2}}}\sigma(x,t)^{2}d t.
$$

This result is known as Ito's lemma, being named for the Japanese mathematician Kiyoshi Ito, whom we mentioned in Chapter 10 and who discovered this result. The equation describes the stochastic process of a function $\boldsymbol{F}(\boldsymbol{x},t)$ that is driven by time $t$ and a stochastic process for $x$ of the form we previously referred to as a Wiener process.

Note that by substituting for $d x$ (Equation (11.3)) and $d x^{2}$ (Equation (11.6)), we can express the stochastic process for $F$ more commonly in finance as

$$
d F=\left[{\frac{\partial F}{\partial t}}+{\frac{\partial F}{\partial x}}\mu(x,t)+{\frac{1}{2}}{\frac{\partial^{2}F}{\partial x^{2}}}\sigma(x,t)^{2}\right]d t+{\frac{\partial F}{\partial x}}\sigma(x,t)d\mathrm{W}_{t}.
$$

In this manner, we see that the term within the square brackets is the expected change in $F$ per unit of time and the variance is given as. $(\partial\bar{F}/\partial x)^{2}\sigma(x,t)^{2}$ per unit of time.3 That is,.

$$
\begin{array}{l}{\displaystyle{E(d F)=E\left\{\left[\frac{\partial F}{\partial t}+\frac{\partial F}{\partial x}\mu(x,t)+\frac{1}{2}\frac{\partial^{2}F}{\partial x^{2}}\sigma(x,t)^{2}\right]d t+\frac{\partial F}{\partial x}\sigma_{x,t}d W\right\}}}\ {~=E\left[\frac{\partial F}{\partial t}+\frac{\partial F}{\partial x}\mu(x,t)+\frac{1}{2}\frac{\partial^{2}F}{\partial x^{2}}\sigma(x,t)^{2}\right]d t~\mathrm{and}}\ {{\mathrm{var}(d F)=\mathrm{var}\left\{\left[\frac{\partial F}{\partial t}+\frac{\partial F}{\partial x}\mu(x,t)+\frac{1}{2}\frac{\partial^{2}F}{\partial x^{2}}\sigma(x,t)^{2}\right]d t+\frac{\partial F}{\partial x}\sigma(x,t)d W_{t}\right\}}}\ {~=\left(\frac{\partial F}{\partial x}\right)^{2}\sigma(x,t)^{2}d t.}\end{array}
$$

Note that the covariance terms in the variance formula are all zero and that all the uncertainty in $F$ comes from the uncertainty in $\mathbb{W}_{t}$

Ito's lemma is widely used in pricing derivatives. The price of a derivative is said to be "derived" from the price of the underlying asset and time. Thus, $\boldsymbol{F}(\boldsymbol{x},t)$ is a convenient specification of a derivative price, because its value is derived from $x$ and $t$ with $x$ known to. be stochastic and $t$ representing time. Suppose $F$ is the price of an option or other derivative contract on an asset whose value is $x$ . If we let that asset price evolve according to the Ito process, then we can characterize the change in the option price by Ito's lemma, as stated in the previous equation.

For example, consider an instrument that is presently valued as the future value of the spot price, where the rate applied,. $k$ , is known. The constant. $k$ denotes the carrying cost that generally includes financing charges and any other costs or benefits from holding the. asset. That is,

$$
F_{t}=S_{t}e^{k\tau},
$$

where the time to expiration of this instrument is expressed as. $\tau=T-t.^{4}$ If we assume that the underlying instrument follows geometric Brownian motion or. $d S_{t}=\alpha S_{t}d t+$ $\sigma S_{t}d\mathbb{W}_{t}$ , then based on Ito's Lemma as represented by Equation (11.10), we have

$$
d F_{t}=\left(\frac{\partial F}{\partial t}+\frac{\partial F}{\partial S}\alpha S_{t}+\frac{1}{2}\frac{\partial^{2}F}{\partial S^{2}}\sigma^{2}S_{t}^{2}\right)d t+\frac{\partial F}{\partial S}\sigma S_{t}d W_{t}.
$$

With $F_{t}=S_{t}e^{k(T-t)}$ , the three required derivatives are as follows:

$$
\begin{array}{c}{{\displaystyle\frac{\partial F}{\partial t}=-k S_{t}e^{k\tau},}}\ {{}}\ {{\displaystyle\frac{\partial F}{\partial S}=e^{k\tau},\mathrm{and}}}\ {{}}\ {{\displaystyle\frac{\partial^{2}F}{\partial S^{2}}=0.}}\end{array}
$$

Substituting these results, we have

$$
\begin{array}{l}{{d F_{t}=\left[-k S_{t}e^{k\tau}+e^{k\tau}\alpha S_{t}+\frac{1}{2}(0)\sigma^{2}S_{t}^{2}\right]d t+e^{k\tau}\sigma S_{t}d W_{t}}}\ {{~=(\alpha-k)F_{t}d t+\sigma F_{t}d W_{t}.}}\end{array}
$$

Therefore, if the underlying instrument price can be modeled with geometric Brownian motion, then this instrument is also geometric Brownian motion with an adjusted drift term and identical relative volatility.

Interestingly, if we modeled the underlying instrument as arithmetic Brownian motion with geometric drift or $d S_{t}=\alpha S_{t}d t+\sigma d\mathrm{W}_{t}$ then we have5

$$
\begin{array}{l}{{d F_{t}=\left[-k S_{t}e^{k\tau}+e^{k\tau}\alpha S_{t}+\displaystyle\frac{1}{2}(0)\sigma^{2}\right]d t+e^{k\tau}\sigma d W_{t}}}\ {{~}}\ {{~=(\alpha-k)F_{t}d t+e^{k\tau}\sigma d W_{t}.}}\end{array}
$$

Note that the volatility term here is an absolute measure, such as currency units, rather than a relative measure such as percentage. In this case, the instrument price is also arithmetic Brownian motion with an adjusted drift term. The absolute volatility is growing when $k>0$ . We will return to explore arithmetic Brownian motion in more detail in Chapters 12 and 13.
