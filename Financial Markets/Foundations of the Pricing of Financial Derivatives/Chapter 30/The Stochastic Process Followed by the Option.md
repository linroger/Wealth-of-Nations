# 30.6 THE STOCHASTIC PROCESS FOLLOWED BY THE OPTION

When deriving the option pricing model, we assume that the asset follows a stochastic process of the form

$$
d S=\alpha_{s}S d t+S\sigma_{s}d\mathrm{W},
$$

where $d\mathbb{W}$ is a standard Brownian motion. To obtain the option pricing model, we require the stochastic process for the asset. We do not, however, specifically require a full analysis of the option's stochastic properties to obtain its price.6 Studies of the performance of option strategies and of option pricing models, however, invariably make use of probability models and statistical rules. Hence, it may be important for some purposes to know what the stochastic process of the option would look like. In general, we would expect it to be of the form

$$
\begin{array}{r}{d c=\alpha_{c}(S,t)d t+\sigma_{c}(S,t)d\mathrm{W},}\end{array}
$$

where we note that the option's expected return and volatility are functions of $S$ and $t.$

Recall that in deriving the option pricing formula, we use Ito's lemma, which expresses the change in the option price as a function of first- and second-order changes in the asset price and time,

$$
d c=\frac{\partial c}{\partial S}d S+\frac{\partial c}{\partial t}d t+\frac{1}{2}\frac{\partial^{2}c}{\partial S^{2}}d S^{2}.
$$

Substituting the stochastic process of the asset for $d S$ and noting that $d S^{2}$ is the wellknown result $S^{2}\sigma_{S}^{2}d t$ we obtain

$$
d c=\left(\frac{\partial c}{\partial S}S\alpha_{s}+\frac{1}{2}\frac{\partial^{2}c}{\partial S^{2}}S^{2}{\sigma_{s}}^{2}+\frac{\partial c}{\partial t}\right)d t+\left(\frac{\partial c}{\partial S}S\sigma_{s}\right)d W.
$$

Dividing by $c$ , we now have a statement for the return on the call,

$$
\frac{d c}{c}=\left(\frac{\frac{\partial c}{\partial S}S\alpha_{s}+\frac{1}{2}\frac{\partial^{2}c}{\partial S^{2}}S^{2}\sigma_{s}^{2}+\frac{\partial c}{\partial t}}{c}\right)d t+\left(\frac{\partial c}{\partial S}\frac{S}{c}\sigma_{s}\right)d W.
$$

We can write this more compactly as

$$
\frac{d c}{c}=\alpha_{c}d t+\sigma_{c}d\mathrm{W},
$$

where

$$
\begin{array}{l}{\displaystyle\alpha_{c}=\left(\frac{1}{c}\right)\left(\frac{\partial c}{\partial S}S\alpha_{s}+\frac{1}{2}\frac{\partial^{2}c}{\partial S^{2}}S^{2}\sigma_{s}^{2}+\frac{\partial c}{\partial t}\right)\mathrm{~and}}\ {\displaystyle\sigma_{c}=\frac{\partial c}{\partial S}\frac{S}{c}\sigma_{s}.}\end{array}
$$

Now, suppose we wish to obtain the expected return, $\mu_{c}$ , and volatility, $\sigma_{c}$ , of the option. We must first recognize the dimension of the parameters of the model. In the option pricing model, the return on the option, $d c/c_{!}$ , is a measure over an infinitesimal time interval. We can take the expected return, but it will be multiplied by dt and will reflect the expectation over this very short time interval. The CAPM deals with returns over a finite interval.7

Taking expectations of Equation (30.29), we obtain\*

$$
\begin{array}{r l}&{E\left(\frac{d c}{c}\right)=E\left[\left(\frac{\partial c}{\partial S}{\mathcal{S}}{\mathcal{R}}_{s}+\frac{1}{2}\frac{\partial^{2}c}{\partial S^{2}}{\mathcal{S}}^{2}{\mathcal{S}}_{s}^{2}+\frac{\partial c}{\partial t}\right)d t+\left(\frac{\partial c}{\partial S}\frac{S}{c}{\mathcal{S}}_{s}\right)d W\right]}\ &{\qquad=E\Bigg[\Bigg(\frac{\partial c}{\partial S}{\mathcal{S}}{\mathcal{S}}_{s}+\frac{1}{2}\frac{\partial^{2}c}{\partial S^{2}}{\mathcal{S}}_{s}^{2}{\mathcal{S}}_{s}^{2}+\frac{\partial c}{\partial t}\Bigg)d t\Bigg]}\ &{\qquad=\left(\frac{\partial c}{\partial S}{\mathcal{S}}{\mathcal{S}}_{s}+\frac{1}{2}\frac{\partial^{2}c}{\partial S^{2}}{\mathcal{S}}^{2}{\mathcal{S}}_{s}^{2}{\mathcal{S}}_{s}^{2}+\frac{\partial c}{\partial t}\right)d t}\ &{\qquad=\alpha_{*}d t.}\end{array}
$$

Although this formula for the expected return does not look like the expected return for the option, it can be shown to be the same, provided we assume that BlackScholes-Merton holds. All we are required to do is substitute the partial derivatives $\partial c/\partial S$ $\partial^{2}c/\partial S^{2}$ , and $\partial c/\partial t$ from the Black-Scholes-Merton model. We repeat these formulas from Chapter 14:

$$
\begin{array}{l}{{\displaystyle\frac{\partial c}{\partial S}=N(d_{1})\:.}}\ {{\displaystyle\frac{\partial^{2}c}{\partial S^{2}}=\frac{e^{-d_{1}^{2}/2}}{S\sigma_{S}\sqrt{2\pi\tau}}.}}\ {{\displaystyle\frac{\partial c}{\partial t}=-\frac{S\sigma_{S}e^{-{d_{1}^{2}/2}}}{2\sqrt{2\pi\tau}}-r_{c}X e^{-r_{c}\tau}N(d_{2})\:.}}\end{array}
$$

Substituting, we then obtain the expected return on the option,

$$
\alpha_{c}=N\left(d_{1}\right)\alpha_{s}\left(\frac{S}{c}\right)-r_{c}\left(\frac{X e^{-r_{c}\tau}}{c}\right)N\left(d_{2}\right).
$$

From the Black-Scholes-Merton formula, we use the substitution, $S N\big(d_{1}\big)-c=$ $X e^{-r_{c}\tau}N(d_{2})$

$$
\alpha_{c}=r_{c}+\left(\alpha_{s}-r_{c}\right)N\left(d_{1}\right)\left(\frac{S}{c}\right).
$$

Because $N(d_{1})$ is $\partial c/\partial S$ and $\mu_{S}=E\big(R_{S}\big)$ , this is the same formula for the option's expected return we obtained previously, Equation (30.16).

Taking the volatility of the return on the option, we obtain'

$$
\begin{array}{c}{{{\sigma_{c}}^{2}d t=\mathrm{var}\displaystyle\left(\frac{d c}{c}\right)=\left(\frac{\partial c}{\partial S}\frac{S}{c}\sigma_{s}\right)^{2}d t}}\ {{{\sigma_{c}}=\displaystyle\left(\frac{\partial c}{\partial S}\right)\left(\frac{S}{c}\right)\sigma_{s}.}}\end{array}
$$

In this case, we have the same formula we previously obtained for the option's volatility, Equation (30.19).

Finally, we should also recognize that the risk-free rate in the finite interval CAPM and the infinitesimal interval option pricing model need to be expressed on an equivalent basis. In this book, we use $r_{c}$ for continuously compounded returns and $r$ for discrete returns. The CAPM typically uses discrete interest, and the option pricing model uses continuous interest. We would need to be sure that interest is measured in the same manner in both models to make the results equivalent.
