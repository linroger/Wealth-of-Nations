---
tags:
  - asset_price
  - black_scholes_merton
  - call_option
  - option_pricing
  - volatility
aliases:
  - BSM Model Limits
  - Black-Scholes Limits
key_concepts:
  - Asset price to zero
  - Call option value
  - Exercise price to zero
  - Time to expiration
  - Volatility to infinity
---

# 13.7 SELECTED BLACK-SCHOLES-MERTON MODEL LIMITING RESULTS

In this section, we explore the Black-Scholes-Merton model for calls when the asset price tends to zero or positive infinity, time tends to zero, volatility tends to zero or to positive infinity, and the exercise price tends to zero. We assume the dividend yield is zero.

From the Black-Scholes-Merton model, we note that $d_{1}$ can be written as

$$
d_{1}=\frac{\ln(S)}{\sigma\sqrt{\tau}}-\frac{\ln(X)-\left(r_{c}+\sigma^{2}/2\right)\tau}{\sigma\sqrt{\tau}}.
$$

Only the first term on the right-hand side is affected by changes in $S$ Thus, as $S$ tends to $+\infty$ , then that implies. $(\Rightarrow)\ln(S)$ tends to $+\infty$ (denoted $\ln(S)\to+\infty$ , which implies $d_{1},d_{2}\rightarrow+\infty$ . Based on the properties of. $N(d)$ , we have the following result,.

$$
S\rightarrow+\infty\Rightarrow\ln(S)\rightarrow+\infty\Rightarrow d_{1},d_{2}\rightarrow+\infty\Rightarrow N\bigl(d_{1}\bigr),N\bigl(d_{2}\bigr)\rightarrow1.0\Rightarrow c=S-X e^{-r_{c}\tau}.
$$

Thus, as the underlying asset price increases, then the option value tends to infinity.

As $S$ tends to zero, $\ln(S)$ tends to $-\infty$ , then $d_{1},d_{2}\rightarrow-\infty$ . Based on properties of the $N(d)$ , we have the following result,

$$
S\to0\Rightarrow\ln(S)\to-\infty\Rightarrow d_{1},d_{2}\to-\infty\Rightarrow N\bigl(d_{1}\bigr),N\bigl(d_{2}\bigr)\to0.0\Rightarrow c=0.
$$

In this case, as the underlying asset price decreases, then the option value tends toward zero.. We now turn to the case where time to expiration tends to positive infinity. We note that $d_{1}$ can be written as

$$
d_{1}=\frac{\ln(S/X)}{\sigma\sqrt{\tau}}+\frac{\left(r_{c}+\sigma^{2}/2\right)\sqrt{\tau}}{\sigma}.
$$

The first term on the right-hand side tends toward zero as. $\tau$ tends to $+\infty$ and the second term on the right-hand side tends toward $+\infty$ as $\tau$ tends to $+\infty$ . Thus, assuming positivee interest rates, $N(d_{1})\to1.0$ Note that the second term of the Black-Scholes-Merton model goes to zero due to the present value factor. $\left(e^{-r_{c}\tau}\right)$ . That is, the present value of the exercise. price is zero. Thus,

$$
\tau\to+\infty\Rightarrow d_{1}\to+\infty,X e^{-r_{c}\tau}N\left(d_{2}\right)\to0\Rightarrow N\left(d_{1}\right)\to1.0\Rightarrow c=S.
$$

We now turn to the case where time to maturity tends to zero. In other words, we are approaching very closely to maturity. Recall, for the model to be coherent, then it must converge to $\operatorname*{max}\bigl(0,S_{T}-X\bigr)$ at expiration. We must address three cases: (1) $S_{T}>X$ (2) $S_{T}<X$ , and (3) $S_{T}=X$ . When $S_{T}>X$ , we note that $d_{1}$ can be written as

$$
d_{1}=\frac{\ln(S/X)}{\sigma\sqrt{\tau}}+\frac{\left(r_{c}+\sigma^{2}/2\right)\sqrt{\tau}}{\sigma}.
$$

We sketch the results as time to expiration approaches zero for these three cases:

1. In-the-money $(S_{T}>X)$ ..

$$
\tau\to0\&\ln(S/X)>0\Rightarrow d_{1},d_{2}\to+\infty\Rightarrow N\bigl(d_{1}\bigr),N\bigl(d_{2}\bigr)\to1.0\Rightarrow c=S_{T}-X.
$$

2. Out-of-the-money $(S_{T}<X)$

$$
\tau\to0\&\ln(S/X)<0\Rightarrow d_{1},d_{2}\to-\infty\Rightarrow N\bigl(d_{1}\bigr),N\bigl(d_{2}\bigr)\to0.0\Rightarrow c=0.
$$

3. At-the-money $(S_{T}=X)$ ..

$$
\tau\rightarrow0\&\ln(S/X)=0\Rightarrow d_{1},d_{2}\rightarrow0\Rightarrow N\bigl(d_{1}\bigr),N\bigl(d_{2}\bigr)\rightarrow0.5\Rightarrow c=0.
$$

Thus, as time to expiration approaches zero, we have the call price converging to $\operatorname*{max}\bigl(0,S_{T}-X\bigr)$

We now turn to the case where volatility tends to positive infinity. In this case, we note that $d_{1}$ and $d_{2}$ can be written as

$$
\begin{array}{r l}&{d_{1}=\cfrac{\ln\left(S e^{r_{c}\tau}/X\right)}{\sigma\sqrt{\tau}}+\cfrac{\sigma\sqrt{\tau}}{2}~\mathrm{and}}\ &{d_{2}=\cfrac{\ln\left(S e^{r_{c}\tau}/X\right)}{\sigma\sqrt{\tau}}-\cfrac{\sigma\sqrt{\tau}}{2}.}\end{array}
$$

Thus, as volatility tends to positive infinity, then the first term on the right-hand side tends to zero and we have the following results:.

$$
\sigma\rightarrow+\infty,d_{1}\rightarrow+\infty,d_{2}\rightarrow-\infty\Rightarrow N(d_{1})\rightarrow1.0,N(d_{2})\rightarrow0.0\Rightarrow c=S.
$$

We now turn to the case where volatility tends to zero. In this case, we note that $d_{1}$ can be written as

$$
d_{1}=\frac{\ln\left(S e^{r_{c}\tau}/X\right)}{\sigma\sqrt\tau}+\frac{\sigma\sqrt\tau}{2}.
$$

For volatility, we must address three cases, (1) $S e^{r_{c}\tau}>X$ (2) $S e^{r_{c}\tau}<X$ and (3) $S e^{r_{c}\tau}=X$ We sketch the results as volatility tends to zero for these three cases. Note that the expected terminal asset value under the risk neutral probability measure has the asset growing at the risk-free rate or $S e^{r_{c}\tau}$

1. Expected terminal value in-the-money $(S e^{r_{c}\tau}>X)$

$$
\sigma\rightarrow0\&\ln\bigl(S e^{r_{c}\tau}/X\bigr)>0\Rightarrow d_{1},d_{2}\rightarrow+\infty\Rightarrow N\bigl(d_{1}\bigr),N\bigl(d_{2}\bigr)\rightarrow1.0\Rightarrow c=S-X e^{-r_{c}\tau}.
$$

2. Expected terminal value out-of-the-money $\begin{array}{r}{(S e^{r_{c}\tau}<X)}\end{array}$

$$
\sigma\to0\&\ln\left(S e^{r_{c}\tau}/X\right)<0\Rightarrow d_{1},d_{2}\to-\infty\Rightarrow N(d_{1}),N(d_{2})\to0.0\Rightarrow c=0.
$$

3. Expected terminal value at-the-money $(S e^{r_{c}\tau}=X)$

$$
\begin{array}{c}{{\sigma\rightarrow0\&\ln\bigl(S e^{r_{c}\tau}/X\bigr)=0\Rightarrow d_{1},d_{2}\rightarrow0\Rightarrow N\bigl(d_{1}\bigr),N\bigl(d_{2}\bigr)\rightarrow0.5}}\ {{\Rightarrow c=S(0.5)-X e^{-r_{c}\tau}(0.5)=0.5e^{-r_{c}\tau}(S e^{r_{c}\tau}-X)=0.}}\end{array}
$$

Again, as volatility tends to zero, we have the call price converges to the lower boundary.

We now turn to the case where the exercise price tends to zero. In this case, we note that $d_{1}$ can be written as

$$
d_{1}=-\frac{\ln(X)}{\sigma\sqrt{\tau}}+\frac{\ln(S)+\left(r_{c}+\frac{\sigma^{2}}{2}\right)\tau}{\sigma\sqrt{\tau}}.
$$

For the exercise price, we simply note

$$
X\rightarrow0\Rightarrow\ln(X)\rightarrow-\infty\Rightarrow d_{1},d_{2}\rightarrow+\infty\Rightarrow N{\left(d_{1}\right)},N{\left(d_{2}\right)}\rightarrow1.0\Rightarrow c=S.
$$

Thus, as the exercise price approaches zero, then the call price approaches the dividend yield adjusted asset price.

Note that using a similar approach, we can find the limits for puts. Alternatively,. we can apply the limiting results with put-call parity and arrive at the same put limits.. For completeness, we conclude this chapter by manually computing Black-Scholes-Merton option pricing model values.
