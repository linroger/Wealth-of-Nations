---
tags:
  - '#arithmetic_brownian_motion'
  - '#black_scholes_merton_model'
  - '#brownian_motion'
  - '#geometric_brownian_motion'
  - '#ito_lemma'
  - '#lognormal_distribution'
  - '#normal_distribution'
  - '#stochastic_calculus'
  - '#stochastic_integral'
---
# 11.6 RECAP AND PREVIEW

In this chapter, we presented the concept of Ito's lemma, which is a specification roughly analogous to a Taylor series, but which applies to stochastic processes. Ito's lemma enables us to explain how the change in one variable is related to the changes in other variables. We also showed how Ito's lemma can be expressed in terms of a stochastic integral, and we showed how a stochastic integral differs from the standard integrals with which we are familiar from standard math. The information from this chapter will be needed to derive the Black-Scholes-Merton model.

In Chapter 12, we shall look at some other properties of the normal and lognormal diffusion process that will be necessary in order to complete the foundations of the

Black-Scholes-Merton model. After that point, we shall finally be able to dive into the derivation of the model.

# APPENDIX 11A

# Technical Stochastic Integral Results

# 11A.1 Selected Stochastic Integral Results

Before proceeding, it is important to recall from the definition of a Wiener process, we know

$$
d\mathbb{W}_{t}=\varepsilon_{t}{\sqrt{d t}}.
$$

Recall the definition of an Ito integral found in Equation (11.16) can be represented here as

$$
\int_{0}^{t}d W_{t}=\sum_{k=1}^{n}\bigl(W_{k}-W_{k-1}\bigr):n\to\infty(b\to0),
$$

where $(0,t)$ is partitioned into intervals of equal length $b$ , where $t=n b$ Wiener Integration Theorem

$$
\boldsymbol{f}_{t}=\int_{0}^{t}d\boldsymbol{W}_{j}
$$

then

$$
f_{t}=\int_{0}^{t}d W_{j}{\stackrel{d}{=}}\tilde{\varepsilon}\sqrt{d t}(\mathrm{equalindistribution}),
$$

where e denotes a standard normal random variable and $\underline{d}$ denotes equal in distribution. Proof: Within this proof, we demonstrate that $f_{t}$ is equal in distribution to a standard normal random variable times the square root of time. We know $d\mathbb{W}$ is distributed normal and the sum of independent normals is normal. Thus, we focus on the first two moments of the distribution. Recall

$$
f_{t}=\int_{0}^{t}d W_{j}\equiv\operatorname*{lim}_{n\to\infty}\sum_{i=1}^{n}\big(W_{i}-W_{i-1}\big),
$$

where $n=b t$ and $b$ is equally spaced time steps. Taking the expected value,

$$
E\big(f_{t}\big)=E\left(\operatorname*{lim}_{n\to\infty}\sum_{i=1}^{n}\big(W_{i}-W_{i-1}\big)\right)=\operatorname*{lim}_{n\to\infty}\sum_{i=1}^{n}E\big[\big(W_{i}-W_{i-1}\big)\big]=0.
$$

Thus, the first moment is zero. We now turn to the second moment. The expected value of the square,

$$
\begin{array}{l}{{\displaystyle{\cal E}(f_{t}^{2})={\cal E}\left(\displaystyle\sum_{\tau=0}^{\tau=t}d\mathrm{W}_{\tau}\displaystyle\int_{\tau=0}^{\tau=t}d\mathrm{W}_{\tau}\right)}}\ {{\displaystyle~={\cal E}\left[\left(\displaystyle\operatorname*{lim}_{n\rightarrow\infty}\displaystyle\sum_{i=1}^{n}\left(\mathrm{W}_{i}-\mathrm{W}_{i-1}\right)\right)\left(\displaystyle\operatorname*{lim}_{n\rightarrow\infty}\displaystyle\sum_{j=1}^{n}\left(\mathrm{W}_{j}-\mathrm{W}_{j-1}\right)\right)\right]}}\ {{\displaystyle~=\operatorname*{lim}_{n\rightarrow\infty}\displaystyle\sum_{i=1}^{n}\sum_{j=1}^{n}\cal E}\big[\big(\mathrm{W}_{i}-\mathrm{W}_{i-1}\big)\big]\big(\mathrm{W}_{j}-\mathrm{W}_{j-1}\big).}}\end{array}
$$

Note that the covariance is zero when $i\neq j$

$$
\begin{array}{r l}&{E\Big(f_{t}^{2}\Big)=\underset{n\rightarrow\infty}{\overset{\lceil n\rceil}{\operatorname*{lim}}}\left\{{\overset{n}{\underset{i=1}{\overset{n}{\sum}}}E\Big[\big({\mathbb{W}}_{i}-{\mathbb{W}}_{i-1}\big)^{2}\Big]}\right.}\ &{\qquad\left.=\underset{n\rightarrow\infty}{\overset{\operatorname*{lim}}{\operatorname*{lim}}}\left\{{\overset{n}{\underset{i=1}{\overset{n}{\sum}}}E\Big[\big({\mathbb{W}}_{i}-{\mathbb{W}}_{i-1}\big)\big({\mathbb{W}}_{j}-{\mathbb{W}}_{j-1}\big)\Big]}\right\}\right.}\ &{\qquad\left.=\underset{n\rightarrow\infty}{\overset{\operatorname*{lim}}{\operatorname*{lim}}}\left\{{\overset{n}{\underset{i=1}{\overset{n}{\sum}}}E\Big[\big({\mathbb{W}}_{i}-{\mathbb{W}}_{i-1}\big)^{2}\Big]}\right\}\right\}}\ &{\qquad=\underset{n\rightarrow\infty}{\overset{\operatorname*{lim}}{\operatorname*{lim}}}\left\{{\overset{n}{\underset{i=1}{\overset{n}{\sum}}}E\big[\big(t_{i}-t_{i-1}\big)\big]}\right\}=\int_{0}^{t}d j=t.}\end{array}
$$

Therefore,

$$
f_{t}=\int_{0}^{t}d W_{j}\stackrel{d}{=}\tilde{\varepsilon}\sqrt{\int_{0}^{t}d j}=\tilde{\varepsilon}\sqrt{t},
$$

where $\tilde{\varepsilon}$ denotes a standard normal random variable and $\underline{d}$ denotes equal in distribution..

We will apply this observation several times in the next few subsections. Throughout. this material, we assume any required derivative of generic functions exists and is finite.. Often, a financial application will require time-varying parameters. For example, an. investor may believe that volatility will generally increase for a particular stock over the next year. The results presented next allow for time-varying parameters but not. state-varying parameters. That is, the parameters are independent of the asset price..

# 11A.1.1 Time Functions of a Normally Distributed Process Lemma

If $g(t)$ is a function solely of calendar time and we have a function defined as

$$
f_{t}\equiv\int_{0}^{t}g(\boldsymbol{j})d W_{j},
$$

then

$$
f_{t}=\sqrt{\frac{\int g^{2}(j)d j}{t}}\intop_{0}^{t}d W_{j}=\tilde{\varepsilon}\sqrt{\intop_{0}^{t}g^{2}(j)d j}.
$$

Proof: From the definition of stochastic integration, we have

$$
f_{t}=\int_{0}^{t}g(j)d W_{j}\equiv\operatorname*{lim}_{n\to\infty}\sum_{i=1}^{n}g\big(t_{i-1}\big)\big(W_{i}-W_{i-1}\big),
$$

where $n=b t$ and $b$ represents spaced time steps. Taking the expected value, we have

$$
E\big(f_{t}\big)=E\left(\operatorname*{lim}_{n\rightarrow\infty}\sum_{i=1}^{n}g\big(t_{i-1}\big)\big(W_{i}-W_{i-1}\big)\right)=\operatorname*{lim}_{n\rightarrow\infty}\sum_{i=1}^{n}g\left(t_{i-1}\right)E\big[\big(W_{i}-W_{i-1}\big)\big]=0.
$$

The expected value of the square,

$$
\begin{array}{r l}&{E\Big(f_{t}^{2}\Big)=E\left(\displaystyle\int_{0}^{t}g(j)d\mathbb{W}_{j}\displaystyle\int_{0}^{t}g(j)d\mathbb{W}_{j}\right)}\ &{\qquad=E\left[\left(\displaystyle\operatorname*{lim}_{n\to\infty}\displaystyle\sum_{i=1}^{n}g\big(t_{i-1}\big)\big(\mathbb{W}_{i}-\mathbb{W}_{i-1}\big)\right)\left(\displaystyle\operatorname*{lim}_{n\to\infty}\displaystyle\sum_{j=1}^{n}g\big(t_{i-1}\big)\big(\mathbb{W}_{j}-\mathbb{W}_{j-1}\big)\right)\right]}\ &{\qquad=\displaystyle\operatorname*{lim}_{n\to\infty}\displaystyle\sum_{i=1}^{n}\sum_{j=1}^{n}E\big[g\big(t_{i-1}\big)\big(\mathbb{W}_{i}-\mathbb{W}_{i-1}\big)g\big(t_{j-1}\big)\big(\mathbb{W}_{j}-\mathbb{W}_{j-1}\big)\big].\qquad(1-\mathbb{W}_{i-1})}\end{array}
$$

Note that the covariance is zero when $i\neq j$

$$
\begin{array}{r l}&{E(f_{t}^{2})=\displaystyle\operatorname*{lim}_{n\to\infty}\left[+\sum_{i=1}^{n}\sum_{j=1}^{n}E\big[g^{2}\big(t_{i-1}\big)\big(W_{i}-W_{i-1}\big)^{2}\Big]\right.}\ &{\qquad\left.=\sum_{n\to\infty}^{n}\left[+\sum_{i=1}^{n}\sum_{j=1}^{n}E\big[g\big(t_{i-1}\big)\big(W_{i}-W_{i-1}\big)g\big(t_{j-1}\big)\big(W_{j}-W_{j-1}\big)\big]\right]}\ &{\qquad\quad=\displaystyle\operatorname*{lim}_{n\to\infty}\left[\sum_{i=1}^{n}E\Big[g^{2}\big(t_{i-1}\big)\big(W_{i}-W_{i-1}\big)^{2}\Big]\right]}\ &{\qquad=\displaystyle\operatorname*{lim}_{n\to\infty}\left[\sum_{i=1}^{n}g^{2}\big(t_{i-1}\big)\big(t_{i}-t_{i-1}\big)\right]=\int_{0}^{t}g^{2}(j)d j.}\end{array}
$$

Therefore,

$$
f_{t}=\intop_{0}^{t}g(j)d\mathrm{W}_{j}=\sqrt{\frac{\intop g^{2}(j)d j}{t}}\intop_{0}^{t}d\mathrm{W}_{j}=\tilde{\varepsilon}\sqrt{\intop_{0}^{t}g^{2}(j)d j}.
$$

Based on this result, we note the mean and variance of this function are simply

$$
\begin{array}{r}{E\big(f_{t}\big)=E(\tilde{\varepsilon})\sigma\sqrt{\displaystyle\int_{0}^{t}g^{2}(j)d j}=0\mathrm{~and~}\quad}\ {\operatorname{var}\big(f_{t}\big)=E(\tilde{\varepsilon}^{2})\displaystyle\int_{0}^{t}g^{2}(j)d j=\displaystyle\int_{0}^{t}g^{2}(j)d j.}\end{array}
$$

We illustrate one application of this lemma. Suppose we wish to model the underlying instrument based on arithmetic Brownian motion with geometric drift. Specifically, suppose the underlying instrument is modeled as

$$
d S_{t}=\alpha_{t}S_{t}d t+\sigma_{t}d W_{t}.
$$

In this case, we may have time varying geometric drift as well as time varying absolute volatility. Recall in a prior example where $F_{t}=S_{t}e^{k\tau}$ , we found

$$
d F_{t}=(\alpha-k)F_{t}d t+e^{k\tau}\sigma d W_{t}.
$$

Based on the previous lemma, let us focus solely on the noise term. Thus, $g(j)=\sigma e^{k(T-j)}$ The stochastic integral,

$$
f_{T}=\int_{0}^{T}g(j)d W_{j}=\int_{0}^{T}\sigma e^{k(T-j)}d W_{j},
$$

can be represented as

$$
\begin{array}{r}{f_{T}=\sigma\sqrt{\frac{\int e^{2k(T-j)}d j}{T}}\int d W_{j}=\tilde{\varepsilon}\sigma\sqrt{\int_{0}^{T}e^{2k(T-j)}d j}.}\end{array}
$$

The solution to the standard integral is

$$
\begin{array}{c}{{{\displaystyle\int_{0}^{T}e^{2k(T-j)}d j=e^{2k(T)}\int e^{-2k(j)}d j=e^{2k(T)}\left[\left.\frac{e^{-2k(j)}}{-2k}\right|_{j=0}^{j=T}\right]}}}\ {{{\displaystyle=e^{2k(T)}\left(\frac{e^{-2k(T)}-1}{-2k}\right)=\frac{e^{2k(T)}-1}{2k}}.}}\end{array}
$$

Thus, in this case, absolute volatility has an adjustment factor addressing the assumed underlying growth rate. Based on this result, we note the mean and variance of this function are

$$
\begin{array}{l}{{\displaystyle E\big(f_{T}\big)=E(\tilde{\varepsilon})\sigma\sqrt{\int_{0}^{T}e^{2k(T-\tilde{\jmath})}d\tilde{\jmath}}=0~\mathrm{and}}}\ {{\displaystyle T}}\ {{\displaystyle\operatorname{var}\big(f_{T}\big)=E(\tilde{\varepsilon}^{2})\sigma^{2}\int e^{2k(T-\tilde{\jmath})}d\tilde{\jmath}=\sigma^{2}\left(\frac{e^{2k(T)}-1}{2k}\right).}}\end{array}
$$

# 11A.1.2Time Functions of a Lognormally Distributed Process Lemma

Again, if $g(t)$ is a function solely of calendar time and we have a function defined as

$$
\ b_{t}\equiv e^{\int g(\mathbf{\boldsymbol{\mathbf{\mathit{\sigma}}}})d W_{j}},
$$

then

$$
\begin{array}{r}{b_{t}=e^{f_{t}}=e^{\sqrt{\frac{f}{\int g^{2}(j)d j}}t}=e^{\sqrt{\frac{t}{\int g^{2}(j)d j}}}.}\end{array}
$$

Proof: Based directly on the previous lemma.

In this case, the mean and variance are based on properties of the lognormal distribution. Thus,

$$
E\left(b_{t}\right)=e^{\frac{\int g^{2}(\mathbf{\omega}_{j})d j}{2}}\mathrm{and}
$$

$$
\operatorname{var}\bigl(b_{t}\bigr)=E\bigl(b_{t}^{2}\bigr)-E\bigl(b_{t}\bigr)^{2}={\mathrm{e}}^{2\int_{0}^{t}g^{2}(j)d j}-e^{\int g^{2}(j)d j}=e^{\int g^{2}(j)d j}\left(e^{\int g^{2}(j)d j}-1\right).
$$

# 11A.2 A General Linear Theorem

Mikosch (1998) provides an elegant introduction to stochastic calculus with a finance focus. On page 150 and following, he provides an extremely useful as well as powerful result. We review this result expressed here as a theorem. We follow the theorem with several useful finance applications that also rely on the stochastic integration results of the previous section.

# 11A.2.1Mikosch's General Linear Theorem

Consider a generic linear stochastic integral of the form7

$$
x_{t}=x_{0}+\int_{0}^{t}{\left[{\mu_{1}(j)x_{j}+\mu_{2}(j)}\right]d j}+\int_{0}^{t}{[\sigma_{1}(j)x_{j}+\sigma_{2}(j)]d W_{j}}
$$

or expressed in stochastic differential form as

$$
d x_{t}=\left[\mu_{1}(t)x_{t}+\mu_{2}(t)\right]d t+[\sigma_{1}(t)x_{t}+\sigma_{2}(t)]d\mathrm{W}_{t},
$$

where $\mu_{1},\mu_{2},\sigma_{1},\sigma_{2}$ are deterministic continuous coefficient functions, $t\in[0,T]$ (bounded). Let

$$
y_{t}\equiv\mathrm{e}^{\int_{0}^{t}\left[\mu_{1}(j)-\frac{\sigma_{1}^{2}(j)}{2}\right]d j+\int_{0}^{t}\sigma_{1}(j)d W_{j}},
$$

then

$$
x_{t}=y_{t}\left(x_{0}+\int_{0}^{t}\frac{\d y_{t}^{t}}{\d y_{j}}d y_{j}+\int_{0}^{t}\frac{\d y_{j}}{\d y_{j}}d W_{j}\right).
$$

Proof: See Mikosch (1998).

In most finance cases, either $\sigma_{1}(j)=0$ or $\sigma_{2}(j)=0$ ,but not both. When $\sigma_{1}(j)>0$ and $\sigma_{2}(j)=0$ , the process is termed linear multiplicative noise. Recall that the binomial process was modeled through a multiplicative process $(S_{0}u^{j}d^{n-j})$ .When $\sigma_{1}(j)=0$ and $\sigma_{2}(j)>0$ , the process is termed linear additive noise. In this case, the binomial process would be modeled through an additive process $[S_{0}+j u+(n-j)d.]$

Although we would be interested in the $E\big(\boldsymbol{x}_{t}\big)$ and $\mathrm{var}\bigl(x_{t}\bigr)$ , the solution for these parameters is a bit tedious for Mikosch's general linear theorem. Thus, we introduce two lemmas that are more straightforward. With the combination of the previous stochastic integration results as well as this theorem, we illustrate several important finance applications.

# 11A.2.2 Linear Additive Noise Lemma

Consider an underlying instrument that is linear with an additive noise term implying a terminal normal distribution. That is, the generic stochastic integral representation is.

$$
S_{t}=S_{0}+\int_{0}^{t}[\mu_{1}(j)S_{j}+\mu_{2}(j)]d j+\int_{0}^{t}\sigma_{2}(j)d W_{j},
$$

or the generic stochastic differential representation is

$$
d S_{t}=\left[\mu_{1}(t)S_{t}+\mu_{2}(t)\right]d t+\sigma_{2}(t)d W_{t}.
$$

From the general linear theorem, we have

$$
\begin{array}{r}{t}\ {\qquad\int_{t}\mu_{1}(\mathbf{\nabla}j)d j}\ {y_{t}\equiv e^{0}}\end{array}
$$

and

$$
S_{t}=y_{t}\left[S_{0}+\int_{0}^{t}{\frac{\mu_{2}(j)}{y_{j}}d j}+\int_{0}^{t}{\frac{\sigma_{2}(j)}{y_{j}}d W_{j}}\right].
$$

The mean and variance can be expressed as

$$
\begin{array}{l}{{\displaystyle{E\big(S_{t}\big)=S_{0}e^{\int_{0}^{t}(\boldsymbol{\scriptstyle{\scriptstyle{\scriptstyle{\scriptstyle{\scriptstyle1}}}})d_{j}}}+\int_{0}^{t}\mu_{2}(j)\exp\left\{\int_{j}^{t}\mu_{1}(k)d k\right\}d j\mathrm{and}}}}\ {{\displaystyle{\mathrm{var}\big(S_{t}\big)=\int_{0}^{t}\sigma_{2}^{2}(j)\exp\left\{2\int_{j}^{t}\mu_{1}(k)d k\right\}d j.}}}\end{array}
$$

For example, consider arithmetic Brownian motion with additive drift. Thus, $\mu_{1}({\boldsymbol{j}})=0$ $\mu_{2}(j)=\mu_{2},\sigma_{1}(j)=0$ , and $\sigma_{2}(j)=\sigma_{2}$ . Thus, $d S_{t}=\mu_{2}d t+\sigma_{2}d\mathrm{W}_{t}$ Based on the linear additive noise lemma, we have

$$
\begin{array}{r}{y_{t}=e^{0}{}^{t}{}^{\left.\mu_{1}\right(j)d j}=e^{0}=1}\end{array}
$$

and

$$
S_{t}=y_{t}\left[S_{0}+\int_{0}^{t}\frac{\mu_{2}(j)}{y_{j}}d j+\int_{0}^{t}\frac{\sigma_{2}(j)}{y_{j}}d W_{j}\right]=S_{0}+\mu_{2}t+\sigma_{2}\int_{0}^{t}d W_{j}.
$$

Thus, the expected value and variance for underlying instruments that follow arithmetic Brownian motion with additive drift is

$$
\begin{array}{r l}&{\displaystyle E\big(S_{t}\big)=S_{0}+\mu_{2}t+\sigma_{2}E\left(\int_{0}^{t}d\mathrm{W}_{j}\right)=S_{0}+\mu_{2}t\mathrm{and}}\ &{\mathrm{var}\big(S_{t}\big)=\sigma_{2}^{2}t.}\end{array}
$$

Now consider arithmetic Brownian motion with geometric drift. Thus, $\mu_{1}(j)=\mu_{1}$ $\mu_{2}(j)=0,\sigma_{1}(j)=0$ and $\sigma_{2}(j)=\sigma_{2}$ . Thus, $d S_{t}=\mu_{1}S_{t}d t+\sigma_{2}d W_{t}$ Based on the linear additive noise lemma, we have

$$
\left.y_{t}\equiv e^{\stackrel{t}{\int}\mu_{1}d j}=e^{\mu_{1}t}\right.
$$

and

$$
S_{t}=y_{t}\left(S_{0}+\int_{0}^{t}\frac{\sigma_{2}}{y_{j}}d\mathbb{W}_{j}\right)=e^{\mu_{1}t}\left(S_{0}+\sigma_{2}\int_{0}^{t}e^{-\mu_{1}j}d\mathbb{W}_{j}\right)=S_{0}e^{\mu_{1}t}+\sigma_{2}\int_{0}^{t}e^{\mu_{1}(t-j)}d\mathbb{W}_{j}.
$$

From the time functions of a normally distributed process lemma, we have the expected value and variance for underlying instruments that follow arithmetic Brownian motion with geometric drift is

$$
\begin{array}{l}{{{\cal E}\big(S_{t}\big)=S_{0}e^{\mu_{1}t}+\sigma_{2}E\left[\displaystyle\int_{0}^{t}e^{\mu_{1}(t-j)}d W_{j}\right]=S_{0}e^{\mu_{1}t}{\mathrm{and}}}}\ {{{\mathrm{var}}\big(S_{t}\big)=\sigma_{2}^{2}\displaystyle\int_{0}^{t}e^{2\mu_{1}(t-j)}d j=\sigma_{2}^{2}\displaystyle\frac{e^{2\mu_{1}t}-1}{2\mu_{1}}.}}\end{array}
$$

We turn now to the multiplicative case.

# 11A.2.3 Linear Multiplicative Noise Lemma

Consider an underlying instrument that is linear with a multiplicative noise term implying the terminal distribution is lognormal. That is, the generic stochastic integral representation is

$$
S_{t}=S_{0}+\int_{0}^{t}[\mu_{1}(j)S_{j}+\mu_{2}(j)]d j+\int_{0}^{t}\sigma_{1}(j)S_{j}d W_{j},
$$

or the generic stochastic differential representation is

$$
d S_{t}=\left[\mu_{1}(t)S_{t}+\mu_{2}(t)\right]d t+\sigma_{1}(t)S_{t}d W_{t}.
$$

Then

$$
y_{t}=e^{\int_{0}^{t}\left[\mu_{1}(j)-\frac{\sigma_{1}^{2}(j)}{2}\right]d j+\int_{0}^{t}\sigma_{1}(j)d W_{j}}
$$

and

$$
S_{t}=y_{t}\left[S_{0}+\int_{0}^{t}\frac{\mu_{2}(j)}{y_{j}}d j\right].
$$

The mean and variance are bit more involved for the multiplicative case. Let

$$
A(a,b)\equiv e^{\int_{a}^{b}\left[\mu_{1}(j)-\frac{\sigma_{1}^{2}(j)}{2}\right]d j}.
$$

Therefore, we have

$$
\begin{array}{l}{{\displaystyle E(S_{t})=S_{0}A(0,t)e^{\frac{j}{\theta_{0}^{'}}t_{0,0}\lambda t}+\int_{0}^{t}(j)A(j,t)e^{\frac{j}{\theta_{0}^{'}}t_{0,0}^{'}\lambda t}d s\mathrm{~mod~}}}\ {{\displaystyle E(S_{t}^{2})=S_{0}^{2}A^{2}(0,t)e^{\frac{j}{\theta_{0}^{'}}t_{0}\lambda t}+2S_{0}A(0,t)\int_{0}^{t}\mu_{2}(j)A(j,t)e^{\frac{j}{\theta_{0}^{'}}t_{0}^{'}\lambda t_{0}\lambda t}d s\mathrm{~mod~}}}\ {{\displaystyle~+\int_{0}^{t}\int_{0}^{t}\mu_{2}(j)A(j,t)\mu_{2}(k)A(k,t)e^{\frac{j}{\theta_{0}^{'}}t_{0}^{'}(m)d m+t\frac{j}{\lambda}}{2}d k d j}}\ {{\displaystyle~+\int_{0}^{t}\int_{t}^{t}\mu_{2}(j)A(j,t)\mu_{2}(k)A(k,t)e^{\frac{j}{\theta_{0}^{'}}t_{0}^{'}(m)d m+t\frac{j}{\lambda}/(0)d m}~d k d j~.}}\end{array}
$$

Thus, the variance is simply based on the definition of variance or

$$
\mathrm{var}\big(S_{t}\big)\equiv E\big(S_{t}^{2}\big)-\big[E\big(S_{t}\big)\big]^{2},
$$

where these two moments are based on Equations (11.78) and (11.79).

Now consider arithmetic Brownian motion with geometric drift. Thus, $\mu_{1}(j)=\mu_{1}$ $\mu_{2}(j)=0$ $\sigma_{1}(j)=\sigma_{1}$ , and $\sigma_{2}(j)=0$ . Thus, $d S_{t}=\mu_{1}S_{t}d t+\sigma_{1}S_{t}d W_{t}$ . Based on the linear additive noise lemma, we have

and

$$
y_{t}\equiv e^{\int\left(\mu_{1}-\frac{\sigma_{1}^{2}}{2}\right)d j+\int_{0}^{t}\sigma_{1}d W_{j}}=e^{\left(\mu_{1}-\frac{\sigma_{1}^{2}}{2}\right)t+\sigma_{1}\int_{0}^{t}d W_{j}}
$$

$$
S_{t}=y_{t}{\big(}S_{0}{\big)}=S_{0}e^{\left(\mu_{1}-{\frac{\sigma_{1}^{2}}{2}}\right)t+\sigma_{1}\intop d W_{j}}.
$$

From the time functions of a lognormally distributed process lemma, we have

$$
S_{t}=S_{0}e^{\left(\mu_{1}-\frac{\sigma_{1}^{2}}{2}\right)t+\sigma_{1}\sqrt{t}\widehat{\varepsilon}}
$$

Thus, the expected value and variance for underlying instruments that follow geometric Brownian motion with geometric drift, based on properties of a lognormal distribution, is

$$
E\big(S_{t}\big)=S_{0}E\left[e^{\bigg(\mu_{1}-\frac{\sigma_{1}^{2}}{2}\bigg)t+\sigma_{1}\sqrt{t}\hat{\varepsilon}}\right]=S_{0}e^{\bigg(\mu_{1}-\frac{\sigma_{1}^{2}}{2}\bigg)t}E\Big(e^{\sigma_{1}\sqrt{t}\hat{\varepsilon}}\Big)=S_{0}e^{\bigg(\mu_{1}-\frac{\sigma_{1}^{2}}{2}\bigg)t}\bigg(e^{\frac{\sigma_{1}^{2}t}{2}}\bigg)=S_{0}e^{\mu_{1}+\frac{\sigma_{1}^{2}}{2}\bigg(\frac{\sigma_{1}^{2}}{2}\bigg)t},
$$

$$
\begin{array}{r l}&{E(S_{t}^{2})=S_{0}^{2}E\left[e^{2\left(\mu_{1}-\frac{\sigma_{1}^{2}}{2}\right)t+2\sigma_{1}\sqrt{t}\hat{\varepsilon}}\right]=S_{0}^{2}e^{2\left(\mu_{1}-\frac{\sigma_{1}^{2}}{2}\right)t}E\Big(e^{2\sigma_{1}\sqrt{t}\hat{\varepsilon}}\Big)}\ &{\qquad=S_{0}^{2}e^{2\left(\mu_{1}-\frac{\sigma_{1}^{2}}{2}\right)t}\left(e^{4\sigma_{1}^{2}t}\right)=S_{0}^{2}e^{\left(2\mu_{1}+\sigma_{1}^{2}\right)t},}\end{array}
$$

and

$$
\operatorname{var}\left(S_{t}\right)=E\left(S_{t}^{2}\right)-E\left(S_{t}\right)^{2}=S_{0}^{2}e^{\left(2\mu_{1}+\sigma_{1}^{2}\right)t}-\left(S_{0}e^{\mu_{1}t}\right)^{2}=S_{0}^{2}e^{2\mu_{1}t}\left(e^{\sigma_{1}^{2}t}-1\right).
$$

# QUESTIONS AND PROBLEMS

One model for the S&P 500 index futures price is represented as

$$
F_{t}=S_{t}e^{(r-\delta)\tau},
$$

where $S_{t}$ denotes the $\mathrm{S\&P~}500$ index value, $r$ denotes the risk free rate, $\delta$ denotes the dividend yield, and $\tau$ denotes the time to maturity, expressed in years. If $S_{t}$ is assumed to follow geometric Brownian motion, $d S_{t}=\alpha S_{t}d t+\sigma S_{t}d W_{t}$ , where $\alpha$ denotes the expected return on the index and $\sigma$ denotes the standard deviation (both annualized, continuously compounded). What is the expected return and standard deviation of the continuously compounded percentage change in the future price?

2  One model for the S&P 500 index futures price is represented as

$$
F_{t}=S_{t}e^{(r-\delta)\tau},
$$

where $S_{t}$ denotes the $\mathrm{S\&RP}500$ index value, $r$ denotes the risk-free rate, $\delta$ denotes the dividend yield, and $\tau$ denotes the time to expiration, expressed in years. Now if. $S_{t}$ is assumed to follow arithmetic Brownian motion with geometric drift, $d S_{t}=\alpha S_{t}d t+$ $\sigma d\mathbb{W}_{t}$ , where $\alpha$ denotes the expected return on the index (annualized, continuously compounded) and $\sigma$ denotes the absolute standard deviation (annualized unit changes).. What is the expected change and standard deviation of the change in the future price?

3Prove the time functions of a normally distributed process lemma stated as: If $g(t)$ is a function solely of calendar time and we have a function defined as.

$$
f_{t}\equiv\int_{0}^{t}g(\boldsymbol{j})d W_{j},
$$

then

$$
f_{t}=\sqrt{\frac{\int g^{2}(j)d j}{t}}\intop_{0}^{t}d W_{j}=\tilde{\varepsilon}\sqrt{\intop_{0}^{t}g^{2}(j)d j}.
$$

4Suppose a stochastic integral can be expressed as

$$
f_{t}\equiv\int_{0}^{t}e^{c(\mathbf{\Phi})j}d\mathrm{W}_{j}.
$$

Derive the mean and variance of $f_{t}$

5Suppose the US dollar (USD) to Narnian lokum (NNL) is $S_{t}=1.25$ USD for each NNL. Based on an analysis of the two countries, the exchange rate is assumed to follow geometric Brownian motion. Specifically,. $d S_{t}=\alpha S_{t}d t+\sigma S_{t}d W_{t}$ where $\alpha=5.0\%$ and $\sigma=35\%$ . Compare the expected change in the exchange rate and standard deviation of the expected change from the US perspective as well as the Narnian perspective assuming a five-year horizon. (Note: If the spot exchange rate is. $S_{t}=\mathbb{S}1.25/N_{\cdot}$ then the reciprocal exchange rate is $R_{t}=N0.8/\S\mid=N({1}/{1.25})/\S]$

# NOTES

1. The term mean square limit can be thought of somewhat like the concept of variance, which is the mean squared deviation around the expected value. It is approximately correct to say that a result in stochastic calculus holds when the variance converges to a finite value.
2. The variable $F$ can depend on other parameters, but they must be constant across $_x$ and $t$
3. Remember that the expected value of $d\mathbb{W}_{t}$ is zero. Hence, the expected value of $d F$ comes from the first term on the right-hand side; the term in parentheses is the expected value, which is a constant. Multiplying by dt scales it by the length of the time interval. The variance in the stochastic process comes from the second term on the right-hand side. The variance is the square of whatever term. is multiplied by $d\mathbb{W}_{t}$ times the variance of $d\mathbb{W}_{t}$ , which is $d t$
4. This instrument closely resembles a forward contract under the carry arbitrage model covered in Chapter 22, but the details of that instrument are not relevant for this application of Ito's lemma. Also, note that $\tau$ is in years and $T-t$ is typically just an index, that is, a type of counter that can be used to identify points in time; there is no harm done in letting. $T-t$ represent days/365 to make it completely consistent with the definition of $\tau$
5. In arithmetic Brownian motion with arithmetic drift, the asset follows the stochastic process, $d S_{t}=\alpha d t+\sigma d\mathrm{W}_{t}$ , meaning that the price change and not the return is modeled as a function of. its drift and volatility. In such a case, the asset value can go below zero..
6. There is no term related to $d t$ because $z$ is not directly determined by $t$
7. Generic refers to $\mu_{1},\mu_{2},\sigma_{1}$ , and $\sigma_{2}$ being a function of, at most, calendar time. Many different functional forms are possible.

# Properties of the Lognormal and Normal Diffusion Processes for Modeling Assets

n this chapter, we will take what we have already learned about stochastic processes and. adapt it to the case of an asset. We will show how certain properties of the asset's return behavior are derived. Finally, we will show how to obtain the formula for the future asset price in terms of a base price and information on what happened in the intervening period. In examining the diffusion processes of assets, let us start by noting that there are many excellent treatments of the subject of this chapter and those in this entire unit. For further study, we recommend several that are particularly well written such as Shimko (1992),. Neftci (2006), Ross (1999), and Malliaris and Brock (1982). In this chapter, we use the term asset to represent any of a variety of potential exposures, such as stocks, exchange rates, or combinations of assets, one of which we will introduce later in this chapter..

Recall that in Chapter 10, we obtained the stochastic process for the asset price in a. heuristic manner. We started with four desirable properties for such a process summarized succinctly here:

1. The asset price may have a nonzero drift..
2. Changes in the asset price are random..
3. Over time, the asset price becomes more unpredictable.
4. Over time, the asset price is nonnegative..

Based on these properties, we proposed geometric Brownian motion (GBM) with geometric drift. The GBM process has all four properties and can be expressed in two ways,

$$
\begin{array}{l}{{d S_{t}=\alpha S_{t}d t+\sigma S_{t}d W_{t}\mathrm{and}}}\ {{\underline{{{d S_{t}}}}=\alpha d t+\sigma d W_{t}.}}\end{array}
$$

One clear undesirable property evident in Equation (12.1) is the assumption that the underlying instrument is greater than zero or $S_{t}>0$ . That is, property (4) holds, but there is no chance for the underlying to be zero in the future. For numerous finance applications, this is simply inappropriate. For example, there is always a chance that a particular stock's price goes permanently to zero. Interest rates can and do go to zero as well as negative. Many financial risks involve differences in prices, such as profits, calendar-related spreads, or product-related spreads.1 Thus, we also explore properties of the normal diffusion process for modeling various financial applications because it admits zero and negative values.

Recall the random variable $d\mathbb{W}_{t}$ is the transformed Brownian motion, which we called a Wiener process. Recall that $d\mathbb{W}_{t}$ is normally distributed with $E(d\mathbb{W}_{t})=0$ , var $\cdot(d W_{t})=$ dt. Also, we noted that $\boldsymbol{d}\boldsymbol{\mathbb{W}}_{t}^{2}$ is non-stochastic and equal to $d t.$ . Using these results, the expectation and variance of Equation (12.1) are

$$
\begin{array}{c}{\displaystyle E\left(\frac{d\ensuremath{S}_{t}}{\ensuremath{S}_{t}}\right)=\alpha d t\mathrm{and}}\ {\displaystyle\mathrm{var}\left(\frac{d\ensuremath{S}_{t}}{\ensuremath{S}_{t}}\right)=\sigma^{2}d t.}\end{array}
$$

Given the fact that $d S_{t}/S_{t}$ is just a linear transformation of a normally distributed random. variable $d\mathbb{W}_{t}$ , then it is also normally distributed.2 In this chapter, we formally derive this stochastic process and some important results related to it..

Alternatively, we can model some underlying exposure with arithmetic Brownian motion (ABM). There are two forms of ABM, either with geometric drift or arithmetic drift. Recall from Chapter 10, we introduced the $\$1$ symbol to emphasize the unit of measure is the same as the asset price and not percentage. Thus, arithmetic Brownian motion with geometric drift (ABMGD) can be expressed as

$$
d S_{t}=\alpha S_{t}d t+\sigma_{\mathbb{S}}d W_{t},
$$

or, depending on context, arithmetic Brownian motion with arithmetic drift (ABMAD) can be expressed as

$$
d S_{t}=\alpha_{\mathbb{S}}d t+\sigma_{\mathbb{S}}d\mathrm{W}_{t}.
$$

These ABM processes resolve the undesirable property evident in Equation (12.1) because the underlying exposure can be positive, zero, or negative. Also, at times we may wish to have the underlying instrument growing geometrically (e.g., stocks) and at other times. arithmetically (e.g., spreads such as refined petroleum and crude oil). Note that in this case. relative return may be undefined if $S_{t}=0$ or lacking financial interpretation if $S_{t}<0$ . For the ABM stochastic process, we are interested in $d S_{t}$ and not $d S_{t}/S_{t}$ . Again, volatility, and perhaps mean, is measured in currency units and not percentage..
