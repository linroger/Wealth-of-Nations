---
tags:
  - american_options
  - binomial_model
  - lattice_model
  - option_pricing
  - risk_neutral
aliases:
  - CRR model
  - Cox Ross Rubinstein
key_concepts:
  - American-style options
  - Binomial tree model
  - Lattice models
  - Option pricing equation
  - Risk-neutral world
---

# [[Financial Instruments/Lecture Notes- Financial Instruments/Teaching Note 4-Multiperiod Binomial Trees/Binomial Option Pricing|Binomial Tree Model]]
## I. One-Period Binomial Tree
## II. [[Financial Instruments/Lecture Notes- Financial Instruments/Teaching Note 4-Multiperiod Binomial Trees/Binomial Option Pricing#The Cox-Ross-Rubinstein Binomial Tree|CRR Binomial Tree Model]]
## III. Estimation and Calibration of $\boldsymbol{\mu}$ and $\sigma$
## IV. Dividends and Option Pricing
## V. Introduction of Combinatorial Method
### Appendix A. Binomial Tree Model for Jump-Diffusion Processes
This chapter is devoted to introducing the binomial tree model, also known as a kind of lattice model. The lattice models, such as the binomial tree model introduced in this chapter or the finite difference method introduced in the next chapter, are popular numerical methods for pricing options, particularly for American-style options. They are also flexible since only nominal changes of the payoff function are needed for dealing with pricing complex, nonstandard options.
## I. One-Period Binomial Tree
### Figure 4-1
![Figure 4-1](https://cdn-mineru.openxlab.org.cn/extract/44625589-b78c-4302-9b0f-635bc859ed28/1ed8e118749ba589561939441cc1ce64dad49a0e3884831d545deeda9f673685.jpg)
(i) Constructing a portfolio: long $\Delta$ shares and short 1 call.
### Figure 4-2
![Figure 4-2](https://cdn-mineru.openxlab.org.cn/extract/44625589-b78c-4302-9b0f-635bc859ed28/65b09c49b3d09b23f9adf91bbba9e1275f2780cfe9215a61df7a30a0c8ada631.jpg)
(ii) Deciding the value of $\Delta$: if $22\Delta - 1 = 18\Delta \Rightarrow$ portfolio is riskless.
(iii) Hence, at $t = 0.25$, the value of the portfolio is $22 \cdot 0.25 - 1 = 18 \cdot 0.25 = 4.5$.
*$^*$ Note that the risk-free interest rate $r$ emerges due to the use of the no-arbitrage argument.
### Figure 4-3
![Figure 4-3](https://cdn-mineru.openxlab.org.cn/extract/44625589-b78c-4302-9b0f-635bc859ed28/7344b770a6f5327335bd371b3cc49b7ceedc903482172fa2e3f8e2cdd6fa9bb6.jpg)
$$
\begin{array}{rl}
& \Delta = \frac{c_u - c_d}{S_0 u - S_0 d} \\
& \Rightarrow \frac{c_u - c_d}{S_0 u - S_0 d} \cdot S_0 - c = \left( S_0 u \frac{c_u - c_d}{S_0 u - S_0 d} - c_u \right) e^{-r T} \\
& \Rightarrow c = \frac{c_u - c_d}{u - d} - \left( \frac{c_u - c_d}{u - d} u - c_u \right) e^{-r T} \\
& \Rightarrow c = e^{-r T} \left( \frac{c_u - c_d}{u - d} e^{r T} - \frac{(c_u - c_d) u}{u - d} + \frac{(u - d)}{u - d} c_u \right) \\
& \Rightarrow c = e^{-r T} \left( \frac{(c_u - c_d) e^{r T} - c_u u + c_d u + \pi c_u - d c_d + c_d - c_d d}{u - d} \right) \\
& \quad = e^{-r T} \left( \frac{(e^{r T} - d) c_u}{u - d} + \frac{(u - d) c_d}{u - d} - \frac{(e^{r T} - d) c_d}{u - d} \right) \\
& \quad = e^{-r T} \left( \frac{e^{r T} - d}{u - d} c_u + \left( 1 - \frac{e^{r T} - d}{u - d} \right) c_d \right)
\end{array}
$$
*($\frac{e^{r T} - d}{u - d}$ and $1 - \frac{e^{r T} - d}{u - d}$ are like binomial probabilities, so they are denoted as $p$ and $1-p$.)*
$$
= e^{-r T} \left( p c_u + (1-p) c_d \right).
$$
*$^*$ For different options, the above equation remains valid, but different payoffs $c_u$ and $c_d$ should be considered.
It is worth noting that $p$ is not the probability for $c_u$ (or for the upward movement of $S$). However, $p$ can be regarded as the probability for $c_u$ (or for the upward movement of $S$) in the risk-neutral world. This is because in the real world, if the expected stock return is $\mu$,
$$
S_0 e^{\mu T} = S_0 u \cdot q + S_0 d \cdot (1-q) \Rightarrow q = \frac{e^{\mu T} - d}{u - d}.
$$
Similarly, in the risk-neutral world, since the expected returns for all securities are the same and equal to $r$,
$$
S_0 e^{r T} = S_0 u \cdot p + S_0 d \cdot (1-p) \Rightarrow p = \frac{e^{r T} - d}{u - d}.
$$
Therefore, $p$ and $1-p$ are termed as risk-neutral probabilities in the binomial tree framework.
The option pricing equation
$$
c = e^{-r T} \left( p \cdot c_u + (1-p) \cdot c_d \right)
$$
In the binomial tree model is consistent with the RNVR because both the expected growth rate of the underlying asset and the discount rate of the option payoff are the risk-free rate.
One can use the upward and downward probabilities in the real world ($q$ and $1-q$ in the binomial tree model), but it is almost impossible to identify a proper discount rate to discount the expected payoff of options, i.e.,
$$
c = e^{-rT} \left( q \cdot c_u + (1-q) \cdot c_d \right).
$$
In practice, for securities with more risk or uncertainty, it should apply higher discount rates to future expected payoffs. Furthermore, it is well known that options are riskier than their underlying assets due to the high-leverage characteristic for investing in options. So, it is not suited to employ the expected return for the underlying asset, $\mu$, to discount the expected payoff of the option.
If we reconsider the numerical example of the one-period binomial tree in the beginning of this chapter and further assume $\mu = 16\%$, then we can derive the probability $q$ in the real world to be 0.7041. Next, by equalizing
$$
e^{-rT} \left( q \cdot c_u + (1-q) \cdot c_d \right) = 0.633,
$$
Which is the true option value in the numerical example, we can solve the discount rate for the option to be $42.58\%$.
In fact, the proper discount rates for expected payoffs of options depend not only on the expected returns $(\mu)$ and volatilities $(\sigma)$ of underlying assets but also on the different $K$ and $T$ of options. As a consequence, it is very difficult (if it is possible) to derive theoretical option prices directly in the real world.
### Lognormal Property
If $X$ is lognormally distributed, i.e., $\ln X$ follows a normal distribution with mean $E[\ln X]$ and variance $\mathrm{var}(\ln X)$, then
$$
E[X] = e^{E[\ln X] + \frac{1}{2} \cdot \mathrm{var}(\ln X)},
$$
And
$$
\mathrm{var}(X) = e^{2 \cdot E[\ln X] + \mathrm{Var}(\ln X)} - \left( e^{\mathrm{Var}(\ln X)} - 1 \right).
$$
$$
\therefore \ln S_T \sim N\left( \ln S_0 + \left( \mu - \frac{\sigma^2}{2} \right) T,\; \sigma^2 T \right)
$$
$$
\Rightarrow E[S_T] = S_0 e^{\mu T}, \quad \mathrm{var}(S_T) = S_0^2 e^{2\mu T} \left( e^{\sigma^2 T} - 1 \right).
$$
$$
\therefore \ln S_{t+\Delta t} \sim N\left( \ln S_t + \left( \mu - \frac{\sigma^2}{2} \right) \Delta t,\; \sigma^2 \Delta t \right)
$$
$$
\Rightarrow E[S_{t+\Delta t}] = S_t e^{\mu \Delta t}.
$$
$$
\Rightarrow \mathrm{var}(S_{t+\Delta t}) = S_t^2 e^{2\mu \Delta t} \left( e^{\sigma^2 \Delta t} - 1 \right) \approx S_t^2 \sigma^2 \Delta t
$$
(because $e^x \approx 1 + x$ when $x \to 0$), ignoring the terms with $\Delta t^2$.
(In the next paragraph, we will use this property to derive the parameters $u$, $d$, and $p$ in the CRR binomial tree framework.)
### Deriving $u$, $d$, and $p$ in the CRR (Cox, Ross, and Rubinstein (1979)) Binomial Tree Model
![Figure 4-5](https://cdn-mineru.openxlab.org.cn/extract/44625589-b78c-4302-9b0f-635bc859ed28/74b0228c187944828e0362bfb5298957620c40923e945523838d66f08b80866c.jpg)
#### Problems of the CRR Model:
1. $p = \frac{e^{r \Delta t} - d}{u - d} = \frac{e^{\sigma r \sqrt{\Delta t}} - e^{-\sigma r \sqrt{\Delta t}}}{u - d}$ is not necessarily inside $[0,1]$ unless $\Delta t$ is small enough.
2. The approximations used to derive $\mathrm{var}(S_{t+\Delta t})$ as well as $u$ and $d$ are valid only when $\Delta t$ is very small.
#### Another Binomial Tree Model Proposed in Jarrow and Rudd (1983):
By considering the logarithmic stock price space and the constraint of $p=1/2$, then
$$
u = e^{\left(r - \frac{\sigma^2}{2}\right)\Delta t + \sigma \sqrt{\Delta t}}, \quad
d = e^{\left(r - \frac{\sigma^2}{2}\right)\Delta t - \sigma \sqrt{\Delta t}},
$$
Can be solved as follows.
### Figure 4-6
![Figure 4-6](https://cdn-mineru.openxlab.org.cn/extract/44625589-b78c-4302-9b0f-635bc859ed28/710c7cdcf62340e8f73ee216f5d6ec5ac89eec6df0d4aee3ecf16a898d227bc1.jpg)
$$
\ln S_{t+\Delta t} \sim N\left( \ln S_t + \left(r - \frac{\sigma^2}{2}\right)\Delta t,\; \sigma^2 \Delta t \right)
$$
$$
\therefore E[\ln S_{t+\Delta t}] = \ln S_t + \left(r - \frac{\sigma^2}{2}\right)\Delta t,\quad \mathrm{var}(\ln S_{t+\Delta t}) = \sigma^2 \Delta t
$$
Matching mean and variance of $\ln S_{t+\Delta t}$:
$$
\Rightarrow
\left\{
\begin{array}{ll}
p (\ln S_t + \ln u) + (1-p) (\ln S_t + \ln d) = \ln S_t + \left(r - \frac{\sigma^2}{2}\right)\Delta t, \\
p (\ln S_t + \ln u)^2 + (1-p) (\ln S_t + \ln d)^2 - \left( \ln S_t + \left(r - \frac{\sigma^2}{2}\right)\Delta t \right)^2 = \sigma^2 \Delta t
\end{array}
\right.
$$
In this model, $p$ is fixed to be 0.5, and only $u$ and $d$ are left as unknowns. By further derivations, one obtains
$$
\ln u = 2 \left(r - \frac{\sigma^2}{2}\right)\Delta t - \ln d.
$$
$\Rightarrow$ Replacing $\ln u$ with $2\mu - D$ in Eq. (2) yields
$$
\begin{array}{rl}
& 0.5 (\ln S_t + 2\mu - D)^2 + 0.5 (\ln S_t + D)^2 - 2 (\ln S_t + \mu)^2 = 2\sigma^2 \Delta t \\
& \Rightarrow D^2 - 2\mu D + \mu^2 - \sigma^2 \Delta t = 0 \\
& \Rightarrow D = \frac{2\mu \pm \sqrt{4\mu^2 - 4(\mu^2 - \sigma^2 \Delta t)}}{2} = \mu \pm \sigma \sqrt{\Delta t} = \ln d \\
& \Rightarrow \ln u = \mu \pm \sigma \sqrt{\Delta t}.
\end{array}
$$
$$
\begin{aligned}
& \text{Because } u > 1 \Rightarrow u \neq e^{-\sigma \sqrt{\Delta t}}. \\
& \Rightarrow u = e^{+\sigma \sqrt{\Delta t}}.
\end{aligned}
$$
### Figure 4-5
![Figure 4-5](https://cdn-mineru.openxlab.org.cn/extract/44625589-b78c-4302-9b0f-635bc859ed28/74b0228c187944828e0362bfb5298957620c40923e945523838d66f08b80866c.jpg)
• Advantages of this alternative binomial tree model: 1) there is no approximation; 2) $p$ maintains to be a positive number between 0 and 1; 3) the convergence rate is generally better than the CRR model for pricing plain vanilla options.
• Disadvantages of this alternative binomial tree model is due to $S_{0}u d\neq S_{0}$ : 1) Since there is no stock price layer coinciding with the specified barrier price, it is less effecient to price the family of barrier options. 2) Since there is no stock price layer equal to $S_{0}$ , it is impossible to apply a quick method, known as the extended tree model, to estimate some Greek letters, like $\Delta$ , $\Gamma$ , and $\Theta$ .
• One possible trinomial tree structure proposed in Hull (2011):
$$
=e^{\sigma\sqrt{3\Delta t}},\ d=\frac{1}{u},\ p_{u}=\sqrt{\frac{\Delta t}{12\sigma^{2}}}(r-\frac{\sigma^{2}}{2})+\frac{1}{6},\ p_{m}=\frac{2}{3},\ p_{d}=-\sqrt{\frac{\Delta t}{12\sigma^{2}}}(r-\frac{\sigma^{2}}{2})+\frac{1}{6},
$$
through matching (i) mean of $S_{t+\Delta t}$ , (ii) variance of $S_{t+\Delta t}$ , $(\mathrm{iii})\sum p_{i}\ =\ 1$ , $\left(\operatorname{iv}\right)d\;=\;{\frac{1}{u}}$ , $\textstyle\left(\mathrm{v}\right)p_{m}={\frac{2}{3}}$ , where (iv) and (v) are arbitrarily imposed constraints.
(Refer to Boyle (1986), Kamrad and Ritchken (1991), and Tian (1993) for more trinomial tree structures.)
(Kamrad and Ritchken (1991) and Tian (1993) show that faster error convergence rates can be attained if all of the three branching probabilities in the trinomial tree are close or equal to $\frac13$ .)
III. Estimation and Calibration of $\textdollar{\mu}$ and $\sigma$
$\begin{array}{r l}&{E[\ln(S_{T}/S_{0})]=(\mu-\frac{\sigma^{2}}{2})T}\\ &{\qquad\qquad\qquad\uparrow\mathrm{because}}\\ &{\ln S_{T}-\ln S_{0}\sim N D((\mu-\frac{\sigma^{2}}{2})T,\sigma^{2}T)}\end{array}$ ̸= $\begin{array}{c}{{\ln(E[S_{T}/S_{0}])}}\\ {{\parallel\mathrm{assume}}}\\ {{K T}}\end{array}$
Assume $S_{1}=S_{0}e^{\eta}$ ( $T=1$ year) $\begin{array}{l}{{\Rightarrow E[S_{T}/S_{0}]=e^{K T}}}\\ {{\Rightarrow E[S_{T}]=S_{0}\,e^{K T}}}\end{array}$
( $\eta$ : continuonsly compounding return per annum)
( $S_{1}$ is stochastic ⇒η follows a distribution) $(E[S_{T}]$ is a known number $\Rightarrow K$ is constant) $\begin{array}{r}{\Rightarrow\eta=\ln\frac{S_{1}}{S_{0}}\sim N D(\mu-\frac{\sigma^{2}}{2},\sigma^{2})}\end{array}$ $\Rightarrow K=\mu={\mathrm{expected}}$ growth rate according to the lognormal property of $S_{T}$ on page 4-5 $\Rightarrow\mu-\frac{\sigma^{2}}{2}$ is the expected value of the continuously
Compounding return per annum
i. Considering two trading days, $t$ and $t+1$ , i. Considering two trading days, $t$ and $t+1$ , we can derive St+1 = St - eηd and ηd = ln StS+t 1 then $E[S_{t+1}/S_{t}]=e^{K_{d}}$ and $K_{d}=\ln E[S_{t+1}/S_{t}]$ ii. Calculating the average of $\ln{\frac{S_{t+1}}{S_{t}}}$ for $n$ days, ii. Calculating the average of $\frac{S_{t+1}}{S_{t}}$ for $n$ days and the result is the estimation of $\mu_{d}-\frac{\sigma_{d}^{2}}{2}$ . Taking the natural log, we can estimate $K_{d}=\mu_{d}$ $\begin{array}{r l}&{\frac{1}{n}(\ln\frac{S_{1}}{S_{0}}+\ln\frac{S_{2}}{S_{1}}+\cdot\cdot+\ln\frac{S_{n}}{S_{n-1}})}\\ &{=\frac{1}{n}(\ln R_{1}+\ln R_{2}+\cdot\cdot+\ln R_{n})}\\ &{=\frac{1}{n}(\ln(R_{1}\cdot R_{2}\cdot\cdot\cdot R_{n}))}\\ &{=\ln(R_{1}\cdot R_{2}\cdot\cdot\cdot R_{n})^{\frac{1}{n}}}\end{array}$ ${\begin{array}{r l}&{\ln({\frac{1}{n}}({\frac{S_{1}}{S_{0}}}+{\frac{S_{2}}{S_{1}}}+\cdot\cdot\cdot+{\frac{S_{n}}{S_{n-1}}}))}\\ &{=\ln({\frac{1}{n}}(R_{1}+R_{2}+\cdot\cdot\cdot+R_{n}))}\end{array}}$
$\Rightarrow$ The geometric average of daily returns $\Rightarrow{}$ The arithemtic average of daily returns estimate the continuously compounding estimates the daily expected growth rate $\mu_{d}$ return µd − 2 d
$\Rightarrow$ The standard deviation of the series of daily $\Rightarrow{}$ The standard deviation of the series of $\frac{S_{t+1}}{S_{t}}$ $\ln{\frac{S_{1}}{S_{0}}}$ , $\begin{array}{r}{\ln{\frac{S_{2}}{S_{1}}},\dots,\ln{\frac{S_{n}}{S_{n-1}}}}\end{array}$ generates the estimation is NOT the estimation of $\sigma_{d}$
Of σd
$^*$ Note that the estimated results based on the daily data, i.e., $\mu_{d}$ and $\sigma_{d}$ , need to be annualized to derive the commonly-used annual estimates.
• Implied volatility (the calibration (校準) of $\sigma$ )
For any option pricing function $c(S_{0},K,r,\sigma,T)$ , $S_{0}$ is the stock price today, $K$ and $T$ can be found in the option contract, and $r$ is the risk-free rate corresponding to the time to maturity $T$ . As for $\sigma$ , it is usually estimated based on the historical stock prices.
However, the market price of an option reflects the consensus of the forward-looking $\sigma$ of market participants and may not equal the theoretical option value based on the historical $\sigma$ . Through equalizing $c(S_{0},K,r,\sigma,T)$ and the market option price, it is possible to calibrate $\sigma$ from the forward-looking viewpoint.
The value of $\sigma^{*}$ satisfying $f(\sigma^{*})\equiv c(S_{0},K,r,\sigma^{*},T)-$ market option price = 0 is called the implied volatility. Here two root-finding algorithms are introduced to solve for the implied volatility.
Bisection Method
First find $[a_{n},b_{n}]$ such that $f(a_{n})f(b_{n})<0$ . The iterative two steps to find $[a_{n+1},b_{n+1}]$ are as follows.
(i) Calcuate $\begin{array}{r}{x_{n}=a_{n}+\frac{b_{n}-a_{n}}{2}}\end{array}$ (ii) If $\begin{array}{r}{f(a_{n})f(x_{n})<0\Rightarrow a_{n+1}=a_{n},b_{n+1}=x_{n}}\\ {\mathrm{else}\Rightarrow a_{n+1}=x_{n},b_{n+1}=b_{n}}\end{array}$
• Newton’s Method
$$
\begin{array}{r}{x_{n+1}=x_{n}-\frac{f(x_{n})}{f^{\prime}(x_{n})}}\end{array}
$$
$$
{\begin{array}{r}{{\biggl|}\,\Rightarrow-f(x_{n})=f^{\prime}(x_{n})(x-x_{n})\Rightarrow x=x_{n+1}=x_{n}-{\frac{f(x_{n})}{f^{\prime}(x_{n})}}}\end{array}}
$$
Quadratical convergence:
According to the second-order Taylor series, $\begin{array}{r}{f(x)=f(x_{n})+f^{\prime}(x_{n})(x-x_{n})+\frac{f^{\prime\prime}(\xi)}{2}(x-x_{n})^{2},}\end{array}$
where $\xi$ is between $x_{n}$ and $x$ .
$$
\begin{array}{r l}&{\Rightarrow x-x_{n}+\frac{f(x_{n})}{f^{\prime}(x_{n})}=-\frac{f^{\prime\prime}(\xi)}{2f^{\prime}(x_{n})}(x-x_{n})^{2}}\\ &{\Rightarrow x-x_{n+1}=-\frac{f^{\prime\prime}(\xi)}{2f^{\prime}(x_{n})}(x-x_{n})^{2}}\end{array}
$$
## IV. Dividends and Option Pricing
This section introduces how to modify the option pricing models if the dividend yield $q$ or known cash dividends $D$ at the pre-specified time point $t$ are considered.
### Table 4-1 Three Different Models for Dividend Payments
$$
\begin{align}
\begin{array}{|c|c|c|c|}
\hline
\text{Suppose the time point today is 0 Model 1:} & \text{Black-Scholes Model European} & \text{Binomial Tree Model European} & \text{Binomial Tree Model American} \\
\hline
\text{Dividend yield } q & S_0 \leftarrow S_0 e^{-qT} & \text{European } S_0 \leftarrow S_0 e^{-qT} \text{ or} & \text{American } e^{(r - q)\Delta t} - d \\
\hline
\text{Dividend yield } q & S_0 \leftarrow S_0 e^{-qT} & e^{(r - q)\Delta t} - d & p = \frac{e^{(r - q)\Delta t} - d}{u - d} \\
\hline
\text{Model 2: Known cash dividends at t as a percentage of } S_t & \text{not available} & \text{Figure 4-8} & \text{Figure 4-8} \\
\hline
\text{Model 3: Known cash dividends } D \text{ at t} & S_0 \leftarrow S_0 - D e^{-rt} & \text{Figure 4-10} & \text{Figure 4-10} \\
\hline
\end{array}
\end{align}
$$
### Model 1: Dividend Yield $q$
It is known that the distributions of $S_T$ are the same under
$$
\left\{
\begin{array}{l}
S_0 + \text{paying dividend yield } q \\
S_0 e^{-qT} + \text{no dividend yield}
\end{array}
\right.
$$
### Figure 4-8
![Figure 4-8](https://cdn-mineru.openxlab.org.cn/extract/44625589-b78c-4302-9b0f-635bc859ed28/3db18ad7a2a5754b4fe6a6f3dbf04522f1a7471548ce63f0d252e1e3f8825a4c.jpg)
#### Analytical Formula
$\odot$ Analytical formula obtained by replacing $S_0$ with $S_0 e^{-qT}$ in the Black-Scholes formula:
$$
\Rightarrow c = S_0 e^{-qT} N(d_1) - K e^{-rT} N(d_2),\quad p = K e^{-rT} N(-d_2) - S_0 e^{-qT} N(-d_1).
$$
$\odot$ The PDE for ( $S_0$ + paying dividend yield $q$ ):
Given
$$
\frac{dS}{\,S\,} = (\mu - q)\,dt + \sigma\,dZ,
$$
We have
$$
dS = (\mu - q) S\,dt + \sigma S\,dZ.
$$
(Note that $S$ denotes the ex-dividend underlying asset price.)
For any derivative $f$ on $S$, by Itô’s lemma:
$$
df = \left( \frac{\partial f}{\partial t} + \frac{\partial f}{\partial S} (\mu - q) S + \frac{1}{2} \frac{\partial^2 f}{\partial S^2} \sigma^2 S^2 \right) dt + \frac{\partial f}{\partial S} \sigma S dZ.
$$
Construct a portfolio $\pi$:
$$
\pi = -f + \frac{\partial f}{\partial S} S \Rightarrow d\pi = -df + \frac{\partial f}{\partial S} dS + \frac{\partial f}{\partial S} S q dt
$$
$$
= \left( -\frac{\partial f}{\partial t} - \frac{1}{2} \frac{\partial^2 f}{\partial S^2} \sigma^2 S^2 + \frac{\partial f}{\partial S} S q \right) dt.
$$
Due to the no-arbitrage argument,
$$
d\pi = r \pi dt
$$
$$
\Rightarrow \left( -\frac{\partial f}{\partial t} - \frac{1}{2} \frac{\partial^2 f}{\partial S^2} \sigma^2 S^2 + \frac{\partial f}{\partial S} S q \right) dt = r (-f + \frac{\partial f}{\partial S} S) dt
$$
$$
\Rightarrow \frac{\partial f}{\partial t} + (r - q) S \frac{\partial f}{\partial S} + \frac{1}{2} \sigma^2 S^2 \frac{\partial^2 f}{\partial S^2} = r f.
$$
You can check that the formulas shown at the top of this page are the solutions to the above PDE given the boundary conditions being $\max (S_T - K, 0)$ and $\max (K - S_T, 0)$ for the call and put options, respectively.
*$^*$ When the dividend yield $q$ is present, it can be found that $(r - q) S \frac{\partial f}{\partial S}$ replaces $r S \frac{\partial f}{\partial S}$ in the original PDE (without dividend yield) on p.2-2. However, it does not mean to replace $r$ with $r - q$ in the PDE, because the right-hand side of the above PDE remains $r f$. The truth is that for the underlying asset $S$, the expected growth rate changes from $r$ to $r - q$, but the discount rate for the derivative $f$ is still $r$.
$\odot$ For the binomial tree model:
**Method 1**: Replace $S_0$ with $S_0 e^{-qT}$ + no dividend payment.
**Method 2**: Change the risk-neutral probability $p$:
$$
p = \frac{\,e^{(r - q)\Delta t} - d\,}{\,u - d\,} \Rightarrow p = \frac{e^{(r - q)\Delta t} - d}{u - d}.
$$
*$^*$ However, during the backward induction phase, we still use $r$ to discount the expected option value at the next time point, i.e.,
$$
f = e^{-r \Delta t} \left[ p f_u + (1-p) f_d \right].
$$
(For European options, both above methods generate correct results, but for American options, only the second method can generate correct results.)
### Model 2: Known Cash Dividends as a Percentage $\delta$ of the Stock Price at Time Point $t$
(In practice, it is rare for companies to distribute cash dividends in this way.)
$\odot$ For the Black-Scholes formula, it is unavailable to deal with this problem.
$\odot$ For the binomial tree model, it is simple to deal with this problem (see Figure 4-8).
### Figure 4-8
![Figure 4-8](https://cdn-mineru.openxlab.org.cn/extract/44625589-b78c-4302-9b0f-635bc859ed28/43c3dd51e959242736070ae2080540e04b75f617296316c3a8b8676b9d078337.jpg)
### Model 3: Known Cash Dividends $D$ at Time Point $t$
$\odot$ For the Black-Scholes formula, replace $S_0$ with $S_0 - D e^{-rt}$.
$\odot$ For the binomial tree model,
**Method 1**: Replace $S_0$ with $S_0 - D e^{-rt}$. However, this method only works for European options but cannot be applied to pricing American options.
$$
\left\{
\begin{array}{l l}
S_0 + \text{paying } D \\
S_0 - D e^{-rt} + \text{ no dividend payment}
\end{array}
\right.
$$
(This is because the distributions of $S_\tau$ ($\tau \ge t$) are the same under no dividend payment.)
### Figure 4-9
![Figure 4-9](https://cdn-mineru.openxlab.org.cn/extract/44625589-b78c-4302-9b0f-635bc859ed28/90b81bc0f631c2f5f3c1aef6fc8a8572ae5b22ddb2ee2a0c70b94fca7cbafbb0.jpg)
**Method 3**: This method can maintain the recombined feature of the binomial tree.
### Figure 4-10
![Figure 4-10](https://cdn-mineru.openxlab.org.cn/extract/44625589-b78c-4302-9b0f-635bc859ed28/95b0c0e6521439abbf5b5151f5d3e0629ccec482a0e5161689a5b0b3e5edf29a.jpg)
Define $S_0^* = S_0 - D e^{-r (t - t_0)} = S_0 - D e^{-rt}$.
**Step 1**: Build $S^*$-tree following the traditional way, but note that in theory,
$$
\sigma^* = \sigma \cdot \frac{S_0}{\,S_0 - D e^{-r(t - t_0)}\,},
$$
Where $\sigma^*$ is the volatility for the stochastic part of the stock price and $\sigma$ is the total volatility of the stock price.
*(For a different volatility $\sigma^*$, one should derive new $u^*$, $d^*$, and $p^*$ in theory. In practice, however, it is rare to calculate $\sigma^*$. The difference between $\sigma^*$ and $\sigma$ is minor, and since $\sigma$ is an estimated value based on historical data, performing the above adjustment does not necessarily lead to a better forward-looking estimate.)*
**Step 2**: For $t_i < t$, replace $S_{t_i}^*$ with $S_{t_i}^* + D e^{-r (t - t_i)}$.
(Since $S_0^* = S_0 - D e^{-rt}$ in Step 1, $S^*$-tree is the same as the tree in Method 1 after $t$, which formulates the stock price process after the dividend payment appropriately. However, the stock prices before $t$ are not consistent with the stock price process before the dividend payment, i.e., $S_0^* \neq S_0$ and $E[S_{t_i}^*] \neq E[S_{t_i}]$ for $t_i < t$. Therefore, the adjustment in Step 2 should be performed.)
#### Currency Option
$\odot$ Replace the dividend yield $q$ with the foreign risk-free rate $r_f$ (Because the underlying asset $S_t$ is a dollar of the foreign currency in domestic dollars, and holding the foreign currency can earn the foreign risk-free rate, a foreign currency is analogous to a stock paying a known dividend yield.)
$\odot\;$
$$
c = S_0 e^{-r_f T} N(d_1) - K e^{-r T} N(d_2),
$$
Where
$$
d_1 = \frac{\ln (S_0/K) + (r - r_f + \frac{\sigma^2}{2}) T}{\,\sigma \sqrt{T}\,},
\quad
d_2 = d_1 - \sigma \sqrt{T}.
$$
#### Futures Options
$\odot$ Call holders: have the right to enter a long position in futures with the delivery price to be $F_T$ and receive cash $F_T - K$ if $F_T \ge K$, where $F_T$ is the latest settlement futures price before $T$ (usually $F_T$ is the closing price on the date $T$) and $K$ is the strike price in futures options.
$\odot$ Put holders: have the right to enter a short position in futures with the delivery price to be $F_T$ and receive cash $K - F_T$ if $F_T \le K$.
*$^*$ Since a futures contract is worth zero when first created (in the above cases, it is at $T$), it can be concluded that the payoff of a futures option is similar to that of exercising plain vanilla options, and the only difference is to replace $S_T$ with $F_T$. This observation implies that we can develop the pricing formula for futures options by following the same method used to develop the option formula for plain vanilla options.
$\odot$ Black-Scholes formula for futures options: Suppose the futures price follows a geometric Brownian motion:
$$
\frac{dF}{\,F\,} = \mu\,dt + \sigma\,dZ.
$$
Let $c (F, t)$ be the call on futures, and according to Itô’s lemma,
$$
d c = \left( \frac{\partial c}{\partial t} + \frac{\partial c}{\partial F} \mu F + \frac{1}{2} \frac{\partial^2 c}{\partial F^2} \sigma^2 F^2 \right) dt + \frac{\partial c}{\partial F} \sigma F dZ.
$$
Construct portfolio $\pi = -c + \left ( \frac{\partial c}{\partial F} \right) F$ (noting the initial value of futures is 0),
$$
d\pi = -d c + \frac{\partial c}{\partial F} d F = -\left( \frac{\partial c}{\partial t} + \frac{1}{2} \frac{\partial^2 c}{\partial F^2} \sigma^2 F^2 \right) dt = r \pi dt = r (-c) dt
$$
$$
\Rightarrow \frac{\partial c}{\partial t} + \frac{1}{2} \sigma^2 F^2 \frac{\partial^2 c}{\partial F^2} = r c.
$$
(Comparing with the PDE for stock options, there is no such term $\frac{\partial c}{\partial F} (r - q) F$.)
Thus, one can set $q = r$ and $S_0 = F_0$ in the Black-Scholes formula to derive the formula for futures options:
$$
c = e^{-r T} \left[ F_0 N(d_1) - K N(d_2) \right],
$$
Where
$$
d_1 = \frac{\ln(F_0/K) + \frac{\sigma^2}{2} T}{\,\sigma \sqrt{T}\,},
\quad
d_2 = d_1 - \sigma \sqrt{T}.
$$
$\odot$ Binomial Tree:
Because $q = r$,
$$
p = \frac{\,e^{(r - q)\Delta t} - d\,}{\,u - d\,} = \frac{1 - d}{u - d}.
$$
(Remember that we still use $r$ as the discount rate for the payoff of the futures options.)
Another way to derive $p$:
### Figure 4-11
![Figure 4-11](https://cdn-mineru.openxlab.org.cn/extract/44625589-b78c-4302-9b0f-635bc859ed28/ad3e35ca1c4e8c4bfbea9e1b19082017b1928cb52f5be293601c1c1e03569b24.jpg)
$\bullet$ The Black-Scholes model as well as the binomial tree model are versatile models: Treat stock index, currency, and futures like a share of stock paying a dividend yield $q$. For stock index options: $q = \text{average dividend yield on the index over the option life}$. For currency options: $q = r_f$. For futures options: $q = r$.
$\bullet$ Combinatorics (組合數學) is a branch of pure mathematics concerning the study of discrete (and usually finite) objects. Aspects of combinatorics include “counting” the objects satisfying certain criteria, deciding when the criteria can be met, or finding “largest,” “smallest,” or “optimal” objects.
$\bullet$ Combinatorial method for European options: Based on the binomial tree framework, applying the combinatorial method is far faster than the backward induction procedure. In fact, it is not necessary to build the binomial tree in the combinatorial method, which is another advantage because it can save memory space for computer programming.
### Figure 4-12
![Figure 4-12](https://cdn-mineru.openxlab.org.cn/extract/44625589-b78c-4302-9b0f-635bc859ed28/8dd35a79473dbd561f4e096f2ac7805abeca207d887a240fd1914500b1ead8b4.jpg)
$$
\text{European option value} = e^{-r T} \sum_{j=0}^{n} \binom{n}{j} p^{n-j} (1-p)^{j} \max\left(S_0 u^{n-j} d^{j} - K,\, 0\right),
$$
Where $\binom{n}{j}$, also denoted as $C_j^n$, is the combination of $j$ from $n$, $u = e^{\sigma \sqrt{\Delta t}}$, $d = e^{-\sigma \sqrt{\Delta t}}$, and $p = \frac{e^{(r - q) \Delta t} - d}{u - d}$.
*$^*$ For the binomial tree model, its complexity is $O (n^2)$, whereas for the above combinatorial method, the complexity is $O (n)$. The difference in required computational time is substantial for a large number of $n$, e.g., $n > 5000$.
## Appendix A. Binomial Tree Model for Jump-Diffusion Processes
$\bullet$ The content in this appendix belongs to the advanced content.
$\bullet$ Binomial tree model for the jump-diffusion process in Amin (1993):
$\odot$ Consider Merton’s (1976) lognormal jump-diffusion process as follows:
$$
\frac{dS}{\,S\,} = (r - q - \lambda K_Y)\,dt + \sigma\,dZ + (Y - 1)\,dq,
$$
Where $K_Y = E[Y - 1]$ and $\ln Y \sim N\left (\mu_J, \sigma_J^2\right)$. By Itô’s lemma,
$$
d\,\ln S = \left( r - q - \frac{1}{2} \sigma^2 - \lambda K_Y \right) dt + \sigma\,dZ + \ln Y\,dq = \alpha\,dt + \sigma\,dZ + \ln Y\,dq.
$$
$\odot$ A modified lattice model based on Amin (1993):
### Figure 4-13
![Figure 4-13](https://cdn-mineru.openxlab.org.cn/extract/44625589-b78c-4302-9b0f-635bc859ed28/7c4946fc3ee65c3f546d68abb4eca156584b55905a6091a0bfd064417af54f2f.jpg)
$\odot$ Backward induction:
### Figure 4-14
![Figure 4-14](https://cdn-mineru.openxlab.org.cn/extract/44625589-b78c-4302-9b0f-635bc859ed28/23b0e47cb63ecd4c9f5bfe3b3caf752914360884b446d9613c86e7746c024b16.jpg)
*$^*$ Define the branching probabilities as follows.
$$
P(k) =
\left\{
\begin{array}{ll}
\text{prob}(\ln S_{t+\Delta t} - \ln S_t = \alpha \Delta t + \sigma \sqrt{\Delta t})
= (1 - \lambda \Delta t) p_u + \lambda \Delta t \Delta N(k), \\
\text{prob}(\ln S_{t+\Delta t} - \ln S_t = \alpha \Delta t - \sigma \sqrt{\Delta t})
= (1 - \lambda \Delta t) p_d + \lambda \Delta t \Delta N(k), \\
\text{prob}(\ln S_{t+\Delta t} - \ln S_t = \alpha \Delta t + k \sigma \sqrt{\Delta t})
= \lambda \Delta t \Delta N(k), \quad \text{for } -M_J \le k \le M_t.
\end{array}
\right.
$$
$$
\begin{aligned}
\Delta N(k) &= N\left( \frac{\alpha \Delta t + \left(k + \frac{1}{2}\right) \sigma \sqrt{\Delta t} - \mu_J}{\,\sigma_J\,} \right) - N\left( \frac{\alpha \Delta t + \left(k - \frac{1}{2}\right) \sigma \sqrt{\Delta t} - \mu_J}{\,\sigma_J\,} \right), \quad \text{for } k \neq \pm M_J, \\
M_J &\equiv \operatorname{int}\left( \frac{3 \sigma_J}{\,\sigma \sqrt{\Delta t}\,} \right), \\
\Delta N(M_J) &= 1 - N\left( \frac{\alpha \Delta t + \left(M_J - \frac{1}{2}\right) \sigma \sqrt{\Delta t} - \mu_J}{\,\sigma_J\,} \right), \\
\Delta N(-M_J) &= N\left( \frac{\alpha \Delta t - \left(M_J - \frac{1}{2}\right) \sigma \sqrt{\Delta t} - \mu_J}{\,\sigma_J\,} \right).
\end{aligned}
$$
(Note that using $\lambda \Delta t \Delta N (k)$ for $-M_J \le k \le M_J$ in the above captures the effect of the jump component $\ln Y \, dq$ in the $d\,\ln S$ process.)
(Note that the definitions of $p (k)$ here are slightly different from those in Amin (1993).)
*$^*$ For the remaining diffusion process, $d\,\ln S = \alpha \, dt + \sigma \, dZ$, determine $p_u$ and $p_d$ by matching its mean and variance:
$$
\left\{
\begin{array}{ll}
p_u S_t u + p_d S_t d = S_t e^{\alpha \Delta t}, \\
p_u S_t^2 u^2 + p_d S_t^2 d^2 - \left( p_u S_t u + p_d S_t d \right)^2 = S_t^2 \sigma^2 \Delta t, \\
p_u + p_d = 1.
\end{array}
\right.
$$
Where $u = e^{\alpha \Delta t + \sigma \sqrt{\Delta t}}$ and $d = e^{\alpha \Delta t - \sigma \sqrt{\Delta t}}$. Analogous with the CRR binomial tree model, we can infer
$$
p_u = \frac{\,e^{\alpha \Delta t} - d\,}{\,u - d\,}.
$$
*$^*$ However, if we consider the probabilities of $(1 - \lambda \Delta t) p_u$ and $(1 - \lambda \Delta t) p_d$ for the upward and downward branches, respectively, when the jump component is introduced, the mean and variance generated by the probabilities of $(1 - \lambda \Delta t) p_u$ and $(1 - \lambda \Delta t) p_d$ are no longer $S_t e^{\alpha \Delta t}$ and $S_t^2 \sigma^2 \Delta t$:
$$
\left\{
\begin{array}{ll}
(1 - \lambda \Delta t) p_u S_t u + (1 - \lambda \Delta t) p_d S_t d = (1 - \lambda \Delta t) S_t e^{\alpha \Delta t}, \\
(1 - \lambda \Delta t) p_u S_t^2 u^2 + (1 - \lambda \Delta t) p_d S_t^2 d^2 - \left[ (1 - \lambda \Delta t) S_t e^{\alpha \Delta t} \right]^2 \approx (1 - \lambda \Delta t) S_t^2 \sigma^2 \Delta t, \\
(1 - \lambda \Delta t) p_u + (1 - \lambda \Delta t) p_d = (1 - \lambda \Delta t).
\end{array}
\right.
$$
For the variance equation, it can be rewritten as
$$
(1 - \lambda \Delta t) \left[ p_u S_t^2 u^2 + p_d S_t^2 d^2 - \left( p_u S_t u + p_d S_t d \right)^2 \right] \approx (1 - \lambda \Delta t) S_t^2 \sigma^2 \Delta t,
$$
If $\Delta t$ is small such that $(1 - \lambda \Delta t) \approx 1$.
Thus, the standard deviation becomes $\sqrt{1 - \lambda \Delta t} \, S_t \, \sigma \sqrt{\Delta t}$. By comparing with the mean, $(1 - \lambda \Delta t) S_t e^{\alpha \Delta t}$, one can find that the deviation of the mean from its true value is more serious than the deviation of the standard deviation, because $\sqrt{1 - \lambda \Delta t}$ is closer to 1 than $(1 - \lambda \Delta t)$ when $\Delta t$ is small.
*$^*$ To offset the above undesirable effects, we should solve $p_u$ and $p_d$ in the following system of equations.
$$
\left\{
\begin{array}{ll}
p_u S_t u + p_d S_t d = \frac{\,S_t e^{\alpha \Delta t}\,}{\,1 - \lambda \Delta t\,}, \\
p_u S_t^2 u^2 + p_d S_t^2 d^2 - \left( p_u S_t u + p_d S_t d \right)^2 = \frac{S_t^2 \sigma^2 \Delta t}{\,1 - \lambda \Delta t\,}, \\
p_u + p_d = 1.
\end{array}
\right.
$$
*$^*$ In Amin (1993), only the adjustment for the mean is considered, i.e., he solves the probability $p_u$ with
$$
p_u S_t u + p_d S_t d = \frac{\,S_t e^{\alpha \Delta t}\,}{\,1 - \lambda \Delta t\,}
$$
And obtains
$$
p_u = \frac{\,\frac{e^{\alpha \Delta t}}{1 - \lambda \Delta t} - d\,}{\,u - d\,}.
$$
*$^*$ Option value of a node can be expressed as
Option value of $\ln S_t$:
$$
= \sum_{-M_J \le k \le M_J} p(k) \cdot \left( \text{option value for } \ln S_{t+\Delta t} = \ln S_t + \alpha \Delta t + k \sigma \sqrt{\Delta t} \right).
$$
$\odot$ To consider the adjustment for the variance, a simple method of adjusting the grid size of the multinomial tree can achieve this goal. By defining $\sqrt{1 - \sigma \lambda \Delta t}$, $u^* = e^{\alpha \Delta t + \sigma^* \sqrt{\Delta t}}$, $d^* = e^{\alpha \Delta t - \sigma^* \sqrt{\Delta t}}$, one can derive the following tree structure and the corresponding branching probabilities.
### Figure 4-15
![Figure 4-15](https://cdn-mineru.openxlab.org.cn/extract/44625589-b78c-4302-9b0f-635bc859ed28/dd90f71b0aec6664ccae364c4d88f970499d1be23e45f234fb947dfb96fd2a56.jpg)
$$
\begin{align}
P^*(k) =
\begin{cases}
\text{prob}(\ln S_{t+\Delta t} - \ln S_t = \alpha \Delta t + \sigma^* \sqrt{\Delta t})
= (1 - \lambda \Delta t) p_u^* + \lambda \Delta t \Delta N(k), \\
\text{prob}(\ln S_{t+\Delta t} - \ln S_t = \alpha \Delta t - \sigma^* \sqrt{\Delta t})
= (1 - \lambda \Delta t) p_d^* + \lambda \Delta t \Delta N(k), \\
\text{prob}(\ln S_{t+\Delta t} - \ln S_t = \alpha \Delta t + k \sigma^* \sqrt{\Delta t})
= \lambda \Delta t \Delta N(k), \quad \text{for } -M_J \le k \le \Delta t.
\end{cases}
\end{align}
$$
$$
\Delta N(k) =
N\left( \frac{\alpha \Delta t + \left(k + \frac{1}{2}\right) \sigma^* \sqrt{\Delta t} - \mu_J}{\,\sigma_J\,} \right)
-
N\left( \frac{\alpha \Delta t + \left(k - \frac{1}{2}\right) \sigma^* \sqrt{\Delta t} - \mu_J}{\,\sigma_J\,} \right),
\quad \text{if } k \neq \pm M_J.
$$
$$
M_J \equiv \operatorname{int}\left( \frac{3 \sigma_J}{\,\sigma^* \sqrt{\Delta t}\,} \right),
$$
$$
\Delta N(M_J) = 1 - N\left( \frac{\alpha \Delta t + \left(M_J - \frac{1}{2}\right) \sigma^* \sqrt{\Delta t} - \mu_J}{\,\sigma_J\,} \right),
$$
$$
\Delta N(-M_J) = N\left( \frac{\alpha \Delta t - \left(M_J - \frac{1}{2}\right) \sigma^* \sqrt{\Delta t} - \mu_J}{\,\sigma_J\,} \right).
$$
$$
p_u^* = \frac{\,e^{\alpha \Delta t} - \lambda \Delta t d^* - d^*\,}{\,u^* - d^*\,}, \quad
p_d^* = 1 - p_u^*.
$$