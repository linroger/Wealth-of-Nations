---
tags:
  - black_scholes
  - exchange_option
  - ito_lemma
  - lognormal_diffusion
  - option_pricing
aliases:
  - Exchange Call Option
  - Exchange Option
  - Option Pricing
key_concepts:
  - Black-Scholes model
  - Euler's theorem
  - Ito's lemma
  - linear homogeneity
  - relative performance
---

# 17.5 EXCHANGE OPTION PRICING

Now let us use the concept of linear homogeneity to price exchange options. We assume each asset follows the lognormal diffusion process,.

$$
{\frac{d S_{i}}{S_{i}}}=\alpha_{i}d t+\sigma_{i}d W_{i}
$$

$$
i=1,2,
$$

and we specify that the correlation between the two Wiener processes driving the asset. prices is $\rho_{12}$ .1 Let $c(S_{1},S_{2})$ be the value today of the exchange call option, which gives the. right to tender asset 2 for asset 1 at expiration,. $T.$ As noted, the payoff of this option is. $\bar{c_{T}}(S_{1},S_{2})=\operatorname*{max}\bigl(0,S_{1}-S_{2}\bigr)$ . It is easy to see that this terminal payoff is linearly homogeneous with respect to the two asset values. Because the value of the option today is a. simple discounted expectation of the payoff at expiration, the current value of the option must also be linearly homogeneous..

Using Euler's theorem, we can express the value of the option as

$$
c(S_{1},S_{2})-{\frac{\partial c(S_{1},S_{2})}{\partial S_{1}}}S_{1}-{\frac{\partial c(S_{1},S_{2})}{\partial S_{2}}}S_{2}=0.
$$

Although this statement, viewed from the context of Euler's theorem, is purely mathematical, it also has a natural interpretation in finance. It says that a portfolio consisting of the purchase of one unit of the exchange call option and short positions in $\partial c/\partial S_{1}$ units of asset 1 and $\partial c/\partial S_{2}$ units of asset 2 would require no initial investment. Therefore, to avoid profitable arbitrage, such a portfolio must generate an instantaneous return of zero.

The differential of Equation (17.23) is

$$
d c(S_{1},S_{2})-\frac{\partial c(S_{1},S_{2})}{\partial S_{1}}d S_{1}-\frac{\partial c(S_{1},S_{2})}{\partial S_{2}}d S_{2}=0.
$$

Now we apply the multivariate version of Ito's lemma to the value of the call:2

$$
\begin{array}{l}{{S_{1},S_{2}\nonumber=\displaystyle\frac{\partial c\big(S_{1},S_{2}\big)}{\partial S_{1}}d S_{1}+\displaystyle\frac{\partial c\big(S_{1},S_{2}\big)}{\partial S_{2}}d S_{2}+\displaystyle\frac{\partial c\big(S_{1},S_{2}\big)}{\partial t}d t}}\ {{\qquad+\displaystyle\frac{1}{2}\left[\displaystyle\frac{\partial^{2}c\big(S_{1},S_{2}\big)}{\partial S_{1}^{2}}{\sigma_{1}}^{2}{S_{1}}^{2}+2\displaystyle\frac{\partial^{2}c\big(S_{1},S_{2}\big)}{\partial S_{1}\partial S_{2}}{\sigma_{1}}{\sigma_{2}}{\rho_{12}}S_{1}S_{2}+\displaystyle\frac{\partial^{2}c\big(S_{1},S_{2}\big)}{\partial S_{2}^{2}}{\sigma_{2}}^{2}S_{2}^{2}\right]d t}}\end{array}
$$

Equating Equation (17.25) with (17.24), and after canceling, we obtain

$$
\frac{\partial c(S_{1},S_{2})}{\partial t}+\frac{1}{2}\left[\frac{\partial^{2}c(S_{1},S_{2})}{\partial{S_{1}}^{2}}{\sigma_{1}}^{2}{S_{1}}^{2}+2\frac{\partial^{2}c(S_{1},S_{2})}{\partial S_{1}\partial S_{2}}{\sigma_{1}}{\sigma_{2}}{\rho_{12}}S_{1}S_{2}+\frac{\partial^{2}c(S_{1},S_{2})}{\partial{S_{2}}^{2}}{\sigma_{2}}^{2}S_{2}^{2}\right]=0
$$

The solution is the exchange option price,

$$
c(S_{1},S_{2})=S_{1}N(d_{1})-S_{2}N(d_{2}),
$$

where

$$
\begin{array}{l}{d_{1}=\displaystyle\frac{\ln\left(S_{1}/S_{2}\right)+(\sigma^{2}/2)\tau}{\sigma\sqrt{\tau}}}\ {d_{2}=d_{1}-\sigma\sqrt{\tau}}\ {~\sigma=\sqrt{{\sigma_{1}}^{2}+{\sigma_{2}}^{2}-2\rho_{12}\sigma_{1}\sigma_{2}}.}\end{array}
$$

Note that $\sigma$ is the volatility of a new variable, defined as the proportional change in the log of the ratio $S_{1}/S_{2}$ . It is obtained as follows:.

$$
\begin{array}{r l}&{\mathrm{var}\left[\mathrm{ln}\left(\frac{S_{1}}{S_{2}}\right)\right]=\mathrm{var}\big(\mathrm{ln}S_{1}-\mathrm{ln}S_{2}\big)}\ &{\qquad=\mathrm{var}\left(\mathrm{ln}S_{1}\right)+\mathrm{var}\left(\mathrm{ln}S_{2}\right)-2\mathrm{cov}\big(\mathrm{lnS}_{1},\mathrm{ln}S_{2}\big)}\ &{\qquad={\sigma_{1}}^{2}+{\sigma_{2}}^{2}-2\rho_{12}\sigma_{1}\sigma_{2}.}\end{array}
$$

We can check the solution by taking the partial derivatives of Equation (17.27) and inserting them into Equation (17.26).

Because we know that. $c$ is linearly homogeneous with respect to the prices of assets. 1 and 2, we can say that $a c(S_{1},S_{2})=\dot{c}(a S_{1},a\bar{S_{2}})$ , where $^{a}$ is a constant. Define $^{a}$ as $1/S_{2}$ which gives us $\left(1/S_{2}\right)c\left(S_{1},S_{2}\right)=c(S,1)$ or $c\left(S_{1},S_{2}\right)=S_{2}c(S,1)$ where $S=S_{1}/S_{2}$ . In effect we have created a new artificial asset, the ratio of the value of asset 1 to the value of asset 2. Because it is not possible to deliver such an asset, this instrument can perhaps. be more easily expressed as a cash-settled call option that enables one to exchange one. unit of currency and receive the value $S=S_{1}/S_{2}$ in cash. Thus, the exchange call is an. ordinary European call on. $S$ with an exercise price of 1. We can, therefore, differentiate.

the exchange option price by differentiating its equivalent value, $S_{2}c(S,1)$ .We will also. need second partial derivatives with respect to. $S_{1},S_{2}$ , the cross partial of. $S_{1}$ and $S_{2}$ , and the first derivative with respect to $t$

Thus, the model can be expressed as

$$
\begin{array}{l}{{c\left(S_{1},S_{2}\right)=S_{2}c(S,1)}}\ {{\qquad=S_{2}\bigl[S N\bigl(d_{1}\bigr)-N\bigl(d_{2}\bigr)\bigr],}}\end{array}
$$

where

$$
S=S_{1}/S_{2}.
$$

Equation (17.29) is an ordinary Black-Scholes-Merton option on the artificial asset $S$ with exercise price of 1. The. $d_{1}$ and $d_{2}$ variables in this variation are the same as shown in. Equation (17.27).

By converting $S_{1}$ and $S_{2}$ to $S$ and the strike to 1, we have normalized these assets. In. asset management and asset allocation in particular, we are often interested in the relative performance of asset 1 in terms of asset 2. In other words, we want to know which asset. class outperforms the other and by how much. In practice, the actual prices of asset 1. and 2 are often significantly different and hence some form of normalization is necessary.. Investors decide the dollar amount to invest in each asset class independent of the quoted. price of each asset. We see here clearly that an exchange option can capture in option value in terms of the relative behavior of the two assets..

Now, for completeness, we need to verify the solution to the PDE in the tradi-. tional manner. That is, we must show that Equation (17.27) solves Equation (17.26). Our approach is to transform the PDE into one that is isomorphic to the Black-Scholes-Merton and infer the solution via the Black-Scholes-Merton model..

Let us initially examine the first derivatives with respect to. $S_{1}$ and $S_{2}$ , commonly referred to as the option delta. We will make use of the artificial asset $S$ to simplify the math, thereby enabling us to use many of the results we already know from the BlackScholes-Merton model. We shall need certain partial derivatives. The first partial deriva-. tives with respect to the underlying prices are.

$$
\begin{array}{r l}{\displaystyle\frac{\partial c\big(S_{1},S_{2}\big)}{\partial S_{1}}=\frac{\partial\big[S_{2}c(S,1)\big]}{\partial S_{1}}}&{}\ {\displaystyle=S_{2}\frac{\partial c(S,1)}{\partial S_{1}}=S_{2}\frac{\partial c(S,1)}{\partial S}\frac{\partial S}{\partial S_{1}}}&{}\ {\displaystyle=\frac{\partial c(S,1)}{\partial S}}&{}\end{array}
$$

$$
\begin{array}{l}{\displaystyle\frac{\partial\big[S_{2}c(S,1)\big]}{\partial S_{2}}=S_{2}\frac{\partial c(S,1)}{\partial S}\frac{\partial S}{\partial S_{2}}+c(S,1)}\ {\displaystyle=S_{2}\frac{\partial c(S,1)}{\partial S}\left(-\frac{S}{S_{2}}\right)+c(S,1)}\ {\displaystyle=c(S,1)-S\frac{\partial c(S,1)}{\partial S}.}\end{array}
$$

The second partial derivatives with respect to the asset prices are

$$
{\frac{\partial^{2}c(S_{1},S_{2})}{\partial{S_{1}}^{2}}}={\frac{\partial}{\partial S_{1}}}~\left[{\frac{\partial c(S_{1},S_{2})}{\partial S_{1}}}\right]={\frac{\partial}{\partial S_{1}}}~\left[{\frac{\partial c(S,1)}{\partial S}}\right]={\frac{\partial}{\partial S}}~\left[{\frac{\partial c(S,1)}{\partial S}}\right]={\frac{\partial}{\partial S}}~\left[{\frac{\partial c(S,1)}{\partial S}}{\frac{\partial S}{\partial S_{1}}}\right]={\frac{\partial^{2}c(S,1)}{\partial S^{2}}}~\left({\frac{S_{1}}{S_{2}S_{1}}}\right)={\frac{\partial^{2}c^{2}}{S_{1}}}
$$

$$
\begin{array}{r l}{\frac{\partial^{2}c\left(S_{1},S_{2}\right)}{\partial S_{2}}=}&{\frac{\partial}{\partial\lambda_{2}}\left[\frac{\partial c\left(S_{1},S_{2}\right)}{\partial S_{2}}\right]=\frac{\partial}{\partial S_{2}}\left[\alpha(S,1)-S\frac{\partial c\left(S,1\right)}{\partial S}\right]=\frac{\partial\lambda_{2}(S,1)}{\partial S_{2}}-S\frac{\partial S\left(S,1\right)}{\partial S}}\ &{=\frac{\partial c\left(S,1\right)}{\partial S_{2}}-\frac{\partial c\left(S,1\right)}{\partial S}\frac{\partial S}{\partial S_{2}}-S\frac{\partial S}{\partial S_{2}}\left[\frac{\partial c(S,1)}{\partial S}\right]-S\frac{\partial S}{\partial S_{2}}\left[\frac{\partial c(S,1)}{\partial S}\right]}\ &{=\frac{\partial c\left(S,1\right)}{\partial S}\frac{\partial S}{\partial S_{2}}-\frac{\partial c(S,1)}{\partial S}\frac{\partial S}{\partial S_{2}}-S\frac{\partial S^{2}c(S,1)}{\partial S^{2}}\frac{\partial S}{\partial S_{2}}}\ &{=-\frac{\partial S^{2}c(S,1)}{\partial S}\left(-\frac{S}{S}\right)=\frac{\partial^{2}c(S,1)}{\partial S^{2}}\left(\frac{S^{2}}{S_{2}}\right)}\ {\frac{\partial^{2}c(S,1)_{S}}{\partial S_{2}\partial S_{2}}=}&{\frac{\partial^{2}c\left(S_{1},S_{2}\right)}{\partial S_{2}}\left[\frac{\partial c(S,1)_{S}}{\partial S_{2}}\right]}\ &{=\frac{\partial}{\partial S_{2}}\left[\frac{\partial c(S,1)}{\partial S}\right]=\frac{\partial^{2}(S,1)}{\partial S^{2}}\frac{\partial S}{\partial S_{2}}}\ &{=\frac{\partial^{2}c(S,1)}{\partial S_{2}}\left(-\frac{S}{S}\right).}\end{array}
$$

We also need the first partial derivative with respect to time:

$$
{\frac{\partial c\left(S_{1},S_{2}\right)}{\partial t}}={\frac{\partial S_{2}c(S,1)}{\partial t}}=S_{2}{\frac{\partial c(S,1)}{\partial t}}.
$$

Expressing Equation (17.26) based on the derivatives above in terms of $S$ and $\sigma$ we find

$$
\begin{array}{l}{{\displaystyle\nabla_{2}\frac{\partial c(S,1)}{\partial t}+\frac{1}{2}\frac{\partial^{2}c(S,1)}{\partial S^{2}}\left(\frac1{S_{2}}\right){\sigma_{1}}^{2}\big(S S_{2}\big)^{2}+\frac{\partial^{2}c(S,1)}{\partial S^{2}}\left(-\frac S{S_{2}}\right)\sigma_{1}\sigma_{2}\rho_{12}\big(S S_{2}\big)S_{2}}}\ {~}\ {{\displaystyle~+\frac12\frac{\partial^{2}c(S,1)}{\partial S^{2}}\left(\frac{S^{2}}{S_{2}}\right){\sigma_{2}}^{2}{S_{2}}^{2}}=0}\ {{\displaystyle\nabla_{2}\left[\frac{\partial c(S,1)}{\partial t}+\frac12\frac{\partial^{2}c(S,1)}{\partial S^{2}}{\sigma_{1}}{\sigma_{1}}^{2}S^{2}-\frac{\partial^{2}c(S,1)}{\partial S^{2}}\sigma_{1}\sigma_{2}\rho_{12}S^{2}+\frac12\frac{\partial^{2}c(S,1)}{\partial S^{2}}\left(\frac{S^{2}}{S_{2}}\right){\sigma_{2}}^{2}S^{2}\right]=0}}\end{array}
$$

$$
\frac{\partial c(S,1)}{\partial t}+\frac{1}{2}~\frac{\partial^{2}c(S,1)}{\partial S^{2}}\sigma^{2}S^{2}=0.
$$

And this is the PDE that was presented as Equation (17.26).

We can also see that the first two lines in the equation show that this partial differential equation is the same as the Black-Scholes-Merton partial differential equation when the interest rate, $r_{c}$ , is set to zero, the underlying asset price is $S.$ , and the volatility is $\sigma$ . Recall the Black-Scholes-Merton PDE as given in Equation (13.11):

$$
r_{c}S{\frac{\partial c}{\partial S}}+{\frac{\partial c}{\partial t}}+{\frac{1}{2}}{\frac{\partial^{2}c}{\partial S^{2}}}\sigma^{2}S^{2}=r_{c}c.
$$

Substituting $r_{c}=0$ , then we have Equation (17.33).

Consequently, we can say that the exchange option is equivalent to. $S_{2}$ units of an ordinary European call when the underlying asset is $S$ , the strike is one, the interest rate is. zero, and the volatility is $\sigma^{2}=\sigma_{1}^{2}+\sigma_{2}^{2}-\overset{\cdot}{2}\rho_{12}\sigma_{1}\sigma_{2}.$ The last two lines above verify that this PDE is the same as the one we previously obtained. Thus, we note that Equation (17.27) solves Equation (17.26).

This result is useful in better understanding not only the exchange option but also the ordinary European option. The latter can be viewed as an exchange option where the asset exchanged is cash. The exchange option implies a zero interest rate because it can be replicated by holding asset 1 and shorting asset 2. The shorting of asset 2 would not have an expected return of $r_{c}$ as it would if it were risk free. Rather the holder of asset 2 would demand its expected return, $\alpha_{2}$ , as compensation. Consequently, the short seller of asset 2, who is trying to replicate the exchange option, would not have an expected return of $-r_{c}$ but rather of $-\alpha_{2}$ . In any ordinary European call, the second term in the pricing equation is the present value of the exercise price. In the exchange option, the second term is also the present value of the exercise price. The current price of asset 2 is its present value.

Interestingly, in the same issue of The Journal of Finance directly preceding the Margrabe article, there is an article by Fischer (1978), in which he modeled bonds indexed to inflation. He showed that to price such a bond one needs the formula for an option where the exercise price is stochastic. Such an option is equivalent to an exchange option, and naturally Fisher derives the same formula as Margrabe.

The traditional exchange option Greeks are provided in Appendix 17C. We now turn to explore spread options.
