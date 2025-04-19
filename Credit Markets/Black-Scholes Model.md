---
cssclasses:
  - academia
title: Black-Scholes Model
tags:
  - black_scholes_model
  - geometric_brownian_motion
  - kospi_200
  - stock_price_process
  - volatility
aliases:
  - BSM
  - Black Scholes
key_concepts:
  - Drift and volatility
  - Geometric Brownian motion
  - KOSPI 200 index data
  - Normal distribution histograms
  - Stock price process
---

[[Financial Engineering/7. Black Scholes Model|Black-Scholes Model]]

# [[Financial Engineering/7. Black Scholes Model|Black-Scholes Model]]

### Black-Scholes Model

### Modeling the Stock Price Process

One of the basic building blocks of the Black-Scholes model is the stock price process. In particular,  in the Black-Scholes world,  the stock price process,  denoted by $S_{t}$ ,  is modeled as a geometric Brownian motion satisfying the following stochastic differential equation:

$$
dS_t=S_t(\mu dt+\sigma dW_t),
$$

where $\mu$ and 0 are constants called the drift and volatility,  respec tively. Also,  0 is always assumed to be a positive constant.

In order to see if such model is “reasonable,  ” let us look at the price data of KOSPI 200 index. In particular Figure 5.1 depicts the KOSPI 200 index from January 2,  2001 till May 18,  2011. If it is reasonable to model it as a geometric Brownian motion,  we must have

$$
\frac{\Delta S_{t}}{S_{t}}\approx\mu\Delta t+\sigma\Delta W_{t}.
$$

In particular if we let $\Delta t=h$ (so that $\Delta S_{t}=S_{t+h}-S_{t}$ and $\Delta W_{t}=$ $W_{t+h}-W_{t})$ ,  the above approximate equality becomes

$$
\frac{S_{t+h}-S_t}{S_t}\approx\mu h+\sigma(W_{t+h}-W_t).
$$

Since $\sigma(W_{t+h}-W_{t})\sim N(0,      \sigma^{2}h)$，the histogram of $(S_{t+h}-S_{t})/S_{t}$ should resemble a normal distribution with standard deviation $\sigma{\sqrt{h}}$ (It is called the $h$ -day volatility.) To see it is indeed the case we have plotted the histograms for $h=1,      2,      3,      5,      7$ (days) in Figures 5.2 up to

 ![500](https://storage.simpletex.cn/view/fyXTzNfy7qe06lCWR7MXM0MvD1yNUwLa0)

Figure 5.1: KOSPI 200 from 2001. 1. 2 to 2011. 5. 18.

5.7. In there,  we have also computed the normal distributions that are closest to the given histograms. Such normal distributions are overlaid together in Figure 5.8. In there,  we can see the standard deviations ( $h$ -day volatility) for each time interval $h$ increases as shown in Table 5.1.

Let us now see if the $h$ -day volatility increases in proportion to ${\sqrt{h}}$ The last column of Table 5.1 shows the $h$ -day volatilities divided by $v/h$ .There,  we can see that they remain roughly constant. In Figure 5.9 are plotted $h$ -day volatilities and a graph $y=0.016436\sqrt{h}$ that best fits the data. In either case,  we can see that the $h$ -day volatilities scales roughly in proportion to $\sqrt{h}$

<table>
<tbody>
<tr>
<th>$\overline{\mathrm{day}}$</th>
<th>${\mathrm{volatility}}$ $h$- day</th>
<th>$(h$-day volatility$)/\sqrt{}$ dav</th>
</tr>
<tr>
<td>1</td>
<td>0.016858</td>
<td>0.016858</td>
</tr>
<tr>
<td>2</td>
<td>0.023430</td>
<td>0.016568</td>
</tr>
<tr>
<td>3</td>
<td>0.029624</td>
<td>0.017103</td>
</tr>
<tr>
<td>5</td>
<td>0.036611</td>
<td>0.016373</td>
</tr>
<tr>
<td>7</td>
<td>0.040421</td>
<td>0.015278</td>
</tr>
</tbody>
</table>
Table 5.1: Standard Deviations (volatility) for the Normal Distributions.
Next,  if $S_{t}$ were to be modeled s satisfying

$$
\frac{\Delta S_t}{S_t}\approx\mu\Delta t+\sigma W_t,
$$

using the increment Brownian motion $W_{t}$ ,  it is not enough to check that the standard deviation of $\Delta S_{t}/S_{t}$ scales like $\sqrt{h}$ .We alsoneed to check the independence of increment. In order to do that,  let us go back to the stochastic differential equation for $S_{t}$ and rewrite $d\log S_{t}$ using the Ito formula as:

$$
d\log S_t=(\mu-\frac{1}{2}\sigma^2)dt+\sigma dW_t.
$$

Therefore we can write

$$
\Delta\log S_t\approx\left(\mu-\frac{1}{2}\sigma^2\right)\Delta t+\sigma\Delta W_t.
$$

On the other hand

$$
\log S_t=\log S_0+\left(\mu-\frac{1}{2}\sigma^2\right)t+\sigma W_t.
$$

Therefore from (5.1) and (5.2),  $\log S_{t}$ and $\Delta\log S_{t}$ should exhibit "independent" behavior. For that purpose,  the following lemma comes in handy
Lemma 5.1. Let $X$ and $Y$ be both Gaussian random variable. Ther $X$ and $Y$ are independent if and only if $Cor(X,  Y)\:=\:0$，where $Cor(X,  Y)$ is the correlation given bg

$$
Cor(X,  Y)=E\left[\left(\frac{X-m_X}{\sigma_X}\right)\left(\frac{Y-m_Y}{\sigma_Y}\right)\right],
$$

where $m_{X}=E[X]$ and $\sigma_{X}^{2}\:=\:E[(X\:-\:m_{X})^{2}]$ and TIlY and $\sigma Y$ are defined similarly
From the data we can compute $\operatorname{Cor}(\log S_{t},  \Delta\operatorname{log}S_{t})$ ,  which turns out to be -0.023749. This correlation between $\log S_{t}$ and $\Delta\log S_{t}$ is quite small; therefore it is reasonable to presume it to be zero,  which then implies by Lemma 5.1 that $\log S_{t}$ and $\Delta\log S_{t}$ are independent.
The $h$ -day volatility scaling and the independence expounded above indicate that it is “reasonable” to model $S_{t}$ as a geometric Brownian motion.
It should be noted that we can use $\Delta S_{t}/S_{t}$ and $\Delta\log S_{t}$ interchangeably. The reason is as follows. First

$$
\Delta\log S_t=\log S_{t+h}-\log S_t=\log\frac{S_{t+h}}{S_t},
$$

But

$$
\log\frac{S_{t+h}}{S_t}=\log\left(1+\frac{S_{t+h}-S_t}{S_t}\right).
$$

By the Taylor expansion,  $\log(1+x)=x+O(x^{2})$ . Therefore

$$
\log\frac{S_{t+h}}{S_t}\approx\frac{S_{t+h}-S_t}{S_t}.
$$

In other words,  it is reasonable to say that $\Delta\log S_{t}\approx\Delta S_{t}/S_{t}$

A remark on the drift term is in order. The $h$ -day drift terms are listed as Table 5.2

<table>
<tbody>
<tr>
<td>$\overline{\mathrm{day}(h)}$ 1</td>
<td>$h$- day mean</td>
</tr>
<tr>
<td>1</td>
<td>0.0007</td>
</tr>
<tr>
<td>2</td>
<td>0.0014</td>
</tr>
<tr>
<td>3</td>
<td>0.0021</td>
</tr>
<tr>
<td>5</td>
<td>0.0035</td>
</tr>
<tr>
<td>7</td>
<td>0.0046</td>
</tr>
</tbody>
</table>
Table 5.2: $h$ -day mean ( $h$ -day drift terms).
It confirms the expected pattern that $h$ -day mean is supposed to be proportional to $h$ .However,  it is a happy accident of data. In many cases,  $h$ -day mean will change quite a bit so that they generally do not exhibit such pattern. Estimating the drift term is not a statistically robust process. So any estimate of the drift is not a reliable data. However,  as we shall see below,  the drift term plays no role in the Black-Scholes model. So it really does not matter how one sets it
### 5.2 Black-Scholes Market
Black-Scholes model is the simplest yet most widely used continuous model in finance. Even with its many shortcomings,  its importance can not be too emphasized. Anyone who is interested in gaining deeper understanding of mathematical finance must be thoroughly familiar with it. Let us now spell out the details of this model
### ·Time
The interval is $[0,  T]$ ,  where $t=0$ denotes the present.
### Probability space
The underlying probability space is denoted by $(\Omega,  \mathcal{F},  P)$

### Information Structure

The information structure is given by a filtration $(\mathcal{F}_{t})_{t\geq0}$ of sub 0 fields of $F$ such that

(i) $\mathcal{F}_{0}$ is the trivial 0 -field $\{\emptyset,      \Omega\}$

(i) ${\mathcal F}_{t_{1}}\subset{\mathcal F}_{t_{2}}$ if $t_{1}\leq t_{2}$

For any $t\in[0,      T]$，we define $\mathcal{F}_{t-}$ to be the 0 -field generated by all $F_{\mathrm{s}}$，( $s<t$ ) and $\mathcal{F}_{t+}$ the 0 -field that is the intersection of $\mathcal{F}_{\mathrm{s}}$ for all $s>t$ .We then assume that

$$
\mathcal{F}_{t-}=\mathcal{F}_{t}=\mathcal{F}_{t+}.
$$

### Brownian motion

The Brownian motion with respect to the measure $P$ is denoted by $W_{t}$ .It is assumed that

$$
W_t\in\mathcal{F}_t.
$$

### Bank account (riskless bond) process

The bank account (riskless bond) process $B_{t}$ is assumed to satisfy the following ordinary differential equatior

$$
\begin{array}{rcl}dB_t&=&rB_tdt\\B_0&=&1\end{array}
$$

For a fixed positive constant 7 which is usually called the riskless (instantaneous) interest rate. It is trivial to see that

$$
B_t=e^{rt},
$$

Which is the result of the continuous compounding with interest rate 7

### ·Time scale

It is customary to use the time scale in such a way that one year is given duration (time span）1. Since we only count the trading days,  one year is considered to have roughly 250 trading days,  which means that one trading day is given 1/250 (year). By the same token,  the interest rate is always quoted as the annualize interest rate. However,  in reality,  banks do not compound continuously; and if the compounding is to be done daily,  banks do compound even for holidays. So reconciling the differences between the theory (continuous compounding) and the practice (daily,  monthly or quarterly compounding) is a subtle matter.

### Stock price process

We assume there is only one risky asset,  which we call the stock. Its price process is denoted by $S_{t}$ .Following the motivation given in Section 5.1,  it is assumed to satisfy the following stochastic differential equation

$$
dS_t=S_t(\mu dt+\sigma dW_t),
$$

where $\mu$ is a constant while we always assume 0 is a positive constant. Thus $S_{t}$ is the so-called geometric Brownian motion studied in Example 4.25 of Chapter 4. In particular,  we know that

$$
S_t=S_0\exp\left[\left(\mu-\frac{1}{2}\sigma^2\right)t+\sigma W_t\right].
$$

### ·Discounted stock price process

Define the discounted stock price process $S_{t}^{*}$ by

$$
S_t^*=\frac{S_t}{B_t}=e^{-rt}S_t.
$$

Then it is easily seen that

$$
dS_{t}^{*}=S_{t}^{*}\left[(\mu-r)dt+\sigma dW_{t}\right].
$$

The standard procedure of the martingale approach in finance is to find a new measure $Q$ ,  called the martingale measure or risk neutral measure,  with respect to which $S_{t}^{*}$ becomes a martingale. Utilizing the standard procedure in Girsanov theorem,  define the exponential martingale $M_{t}$ by

$$
\begin{array}{rcl}dM_t&=&-\gamma M_tdW_t\\M_0&=&1,      \end{array}
$$

for some constant 7 to be determined later. First,  define the measure $Q_{t}$ on ${\mathcal{F}}_{t}$ by

$$
dQ_t=M_tdP.
$$

Then let $Q=Q_{T}$ .Welearned that

$$
Q_{t}=Q\mid_{\mathcal F_{t}}\:.
$$

The Girsanov theorem says that the new stochastic process $\widetilde{W}_{t}$ de fined by

$$
d\widetilde{W}_t=dW_t+\gamma dt
$$

is a Brownian motion with respect to $Q(=Q_{T})$ . Now

$$
\begin{array}{rcl}dS_t^*&=&S_t^*\left[(\mu-r)dt+\sigma dW_t\right]\\&=&S_t^*\left[(\mu-r-\sigma\gamma)dt+\sigma d\widetilde W_t\right].\end{array}
$$

If we define $\gamma$ by

$$
\gamma=\frac{\mu-r}{\sigma},
$$

$S_{t}^{*}$ now satisfies

$$
dS_{t}^{*}=\sigma S_{t}^{*}d\widetilde{W}_{t}.
$$

Namely,  $S_{t}^{*}$ is a $Q$ -martingale. The constant $\Upsilon$ defined in (5.3) is called the market price of risk." Although a misnomer,  it nonetheless plays a very important role in finance. It is also useful to notice that (5.4) is equivalent to

$$
dS_t=S_t(rdt+\sigma d\widetilde{W}_t).
$$

In finance jargon,  (5.5) is to be interpreted as saying that in the risk neutral (martingale) world,  the mean instantaneous return of any risky asset should be exactly the same as that of riskless asset

### 5.3 [[Financial Instruments/Financial Derivatives and Quantitative Methods/Risk Neutral Pricing of Options|Risk-Neutral Valuation Principle in the Black-Scholes Model]]

In Chapter 2,  we have established the risk-neutral valuation principle for the discrete model. The same risk neutral valuation principle holds for continuous model. In this section,  we establish it for the Black-Scholes model. However any alert reader will notice that this derivation works without any significant modification for any continuous market model with stochastic volatility

Definition 5.2. A European option or a European contingent claim with expiry (time) at $t=T$ is an $\mathcal{F}_{T}$ -random variable.

Let us now suppose $X$ is a European option with expiry $t=T$ The risk-neutral valuation principle we are trying to derive here has the same form as the one given for discrete case.

### 5.3.0.1 Construction of Portfolio

Let $CQ$ be the martingale measure obtained in section 5.2. Define $V_{t}$ by

$$
V_t=B_tE_Q\left[\frac{X}{B_T}\mid\mathcal{F}_t\right]
$$

And

$$
V_{t}^{*}=\frac{V_{t}}{B_{t}}.
$$

Thus $V_{t}^{*}$ is obviously a $CQ$ -martingale. Then by the Martingale Representation theorem,  there exists $\alpha_{t}\in\mathcal{F}_{t}$ such that

$$
dV_t^*=\alpha_td\widetilde{W}_t.
$$

Combining this with (5.4),  and setting

$$
\zeta_t=\frac{\alpha_t}{\sigma S_t^*},
$$

It is easy to see that

$$
dV_t^*=\zeta_tdS_t^*.
$$

It should be noted that the denominator in (5.6) never vanishes as $\sigma>0$ and $S_{t}^{*}>0$ . Define $\xi_{t}$ by

$$
\xi_{t}=V_{t}^{*}-\zeta_{t}S_{t}^{*}.
$$

Thus we have

$$
V_t=\xi_tB_t+\zeta_tS_t.
$$

Namely,  if one construct a portfolio of $\xi_{t}$ units of riskless bond and $\zeta_{t}$ shares of stock at each time $t$ ,  then $V_{t}$ must be the one that represents the value of this portfolio. We will show below that this portfolio is self-financing

### Continuous Trading and Self-Financing

In the Black-Scholes model,  we assume the portfolio is continuously changed,  i.e. traded (rebalanced,  to use finance jargon). This continuous trading assumption is not of course realistic but can be envisioned as a “limit" of frequent trading

Definition 5.3. A portfolio $(\xi_{t},      \zeta_{t})$ that consists of $\xi_{t}$ units of riskless bond and $\zeta_{t}$ shares of stocks is called self-financing,  if

$$
dV_t=\xi_tdB_t+\zeta_tdS_t,
$$

where $V_{t}$ is the values of theportfolioat timetgiven by

$$
V_t=\xi_tB_t+\zeta_tS_t.
$$

This definition comes as a “limit” of the discrete counterpart. (See especially Definition 2.39.)

Theorem 5.4. The portfolio $(\xi_{t},      \zeta_{t})$ is self-financing if and only if

$$
dV_{t}^{*}=\zeta_{t}dS_{t}^{*}.
$$

Proof. First note that

$$
\begin{array}{rcl}dV_t&=&d(B_tV_t^*)\\&=&V_t^*dB_t+B_tdV_t^*,      \end{array}
$$

By Ito's formula. On the other hand,  using (5.9),  we have

$$
\begin{aligned}
\xi_{t}dB_{t}+\zeta_{t}dS_{t}& =\:(V_{t}^{*}-\zeta_{t}S_{t}^{*})dB_{t}+\zeta_{t}dS_{t} \\
&=\:V_{t}^{*}dB_{t}+\zeta_{t}B_{t}\left[-B_{t}^{-2}S_{t}dB_{t}+B_{t}^{-1}dS_{t}\right] \\
&=\:V_{t}^{*}dB_{t}+\zeta_{t}B_{t}d(B_{t}^{-1}S_{t}) \\
&=\:V_{t}^{*}dB_{t}+\zeta_{t}B_{t}dS_{t}^{*}.& \text{(}
\end{aligned}
$$

Note that the self-financing condition is equivalent to the LHS of (5.10) being equal to the LHS of (5.11),       which in turn is equivalent to $dV_{t}^{*}=\zeta_{t}dS_{t}^{*}$ by looking at the right hand sides of (5.10) and L (5.11)
Remark 5.5. Theorem 5.4 is the continuous counter-part of Proposition 2.40. It also proves that the portfolio constructed in “Constructing Portfolio subsection is self-financing

### Replicating Portfolio

Definition 5.6. A portfolio consisting of $\xi_{t}$ units of riskless bond and $\zeta_{t}$ shares of stock is said to replicate aEuropean option $X\in\mathcal{F}_{t}$ 计

$$
\xi_TB_T+\zeta_TS_T=X
$$

As random variables

### Risk-Neutral Valuation Principle

We are now ready to state and prove the risk-neutral valuation princi ple in the Black-Scholes model setting. Suppose $(\xi_{t},      \zeta_{t})$ is a portfolio constructed above using the martingale representation theorem as in "Construction of Portfolio subsection above. Then,       in particular,       the discounted portfolio value $V_{t}^{*}$ satisfies

$$
dV_t^*=\zeta_tdS_t^*,
$$

which then implies that this portfolio is self-financing by Theorem 5.4. Now note that since $X$ and $B_{T}\in\mathcal{F}_{T}$

$$
\begin{array}{rcl}V_T&=&B_TE_Q\left[\frac{X}{B_T}\mid\mathcal{F}_T\right]\\&=&X,      \end{array}
$$

which means that this portfolio replicates $X$ .Therefore the price of $X$ at time $t$ must be

$$
V_t=B_tE_Q\left[\frac{X}{B_T}\mid\mathcal{F}_t\right].
$$

For,       otherwise,       there must exist an arbitrage at time $t$ involving the portfolio $(\xi_{t},      \zeta_{t})$ and the option itself $X$ We summarize our result as follows:
Theorem 5.7. (Risk-Neutral Valuation Principle) The price $V_{t}$ at time t of the European option $X\in\mathcal{F}_{T}$ is

$$
V_t=B_tE_Q\left[\frac{X}{B_T}\mid\mathcal{F}_t\right].
$$

### 5.4 [[Financial Instruments/Financial Derivatives and Quantitative Methods/Black Scholes Formula|The Black-Scholes Formula]]

The above risk-neutral valuation principle gives a method of computing the price of any European option. However,       in practice,       it is not easy to carry out actual closed-form computation. In this section,       we derive the celebrated formula called the Black-Scholes formula for pricing the European call or put options. A European call option is a contract to pay at expiry,       say at time $T$ ,      ， the amount that is the difference between the preset value,       say $K$ ,      called the strike price and the stock price $S_{T}$ as long as $S_{T}$ is greater than $K$ ；and zero. Otherwise. (In this chapter all options are European.) Thus the call option can be succinctly expressed as

$$
X=(S_T-K)^+,
$$

where $a^{+}$ means $\max(a,      0)$
Let us now find the formula for the price of $X$ at time 0 i.e.we are seeking a closed-form formula for $V_{0}$

$$
\begin{aligned}
V_{0}& =\:e^{-rT}E_{Q}\left[(S_{T}-K)^{+}\right] \\
&=\:e^{-rT}E_{Q}\left[(S_{T}-K)\cdot\mathbf{1}_{\{S_{T}>K\}}\right] \\
&=\:e^{-rT}E_{Q}\left[S_{T}\cdot\mathbf{1}_{\{S_{T}>K\}}\right]-Ke^{-rT}E_{Q}\left[\mathbf{1}_{\{S_{T}>K\}}\right] \\
&=\:I_{1}-I_{2},    
\end{aligned}
$$

where $\mathbf{1}_{\{S_{T}>K\}}$ is the indicator (characteristic） function of the set $\{S_{T}>K\}$
Compute $I_{2}$ : First,       note that

$$
S_T=S_0\mathrm{exp}\left[\left(r-\frac{1}{2}\sigma^2\right)T+\sigma\widetilde{W}_T\right]>K
$$

Is equivalent to

$$
\log(S_0/K)+\left(r-\frac{1}{2}\sigma^2\right)T>-\sigma\widetilde{W}_T\stackrel{\mathcal{L}}{=}-\sigma\sqrt{T}\widetilde{W}_1,
$$

where the symbol $L$ above the equal sign denotes the equality in law $S2$ ,       or equivalently in distribution. Then

$$
Prob(S_T>K)=Prob\left(-\widetilde W_1<\frac{\log(S_0/K)+(r-\frac{1}{2}\sigma^2)T}{\sigma\sqrt{T}}\right).
$$

Thus,       since the distribution of $-\widetilde{W}_{1}$ is the standard normal distribu tion $N(0,      1)$ of mean 0 and variance 1,

$$
E_Q\begin{bmatrix}\mathbf{1}_{\{S_T>K\}}\end{bmatrix}=Prob\left(Z<\frac{\log(S_0/K)+(r-\frac{1}{2}\sigma^2)T}{\sigma\sqrt{T}}\right),
$$

where $Z$ is a standard Gaussian random variable with mean 0 and variance 1. Therefore

$$
E_Q\begin{bmatrix}1_{\{S_T>K\}}\end{bmatrix}=N(d_2),
$$

Where

$$
\begin{aligned}N(d)=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{d}e^{-x^2/2}dx\end{aligned}
$$

And

$$
d_2=\frac{\log(S_0/K)+(r-\frac{1}{2}\sigma^2)T}{\sigma\sqrt{T}}.
$$

Thus

$$
I_2=Ke^{-rT}N(d_2).
$$

Compute $I_{1}$

$$
\begin{aligned}I_{1}&=\quad E_{Q}\left[\frac{S_{T}}{B_{T}}\cdot\mathbf{1}_{\{S_{T}>K\}}\right]\\&=\quad E_{Q}\left[S_{T}^{*}\cdot\mathbf{1}_{\{S_{T}>K\}}\right]\\&=\quad\int_{\{S_{T}>K\}}S_{T}^{*}dQ.\end{aligned}
$$

Recall

$$
dS_{t}^{*}=\sigma S_{t}^{*}d\widetilde{W}_{t}.
$$

Thus $S_{t}^{*}$ is an exponential martingale,       and so is $\frac{S_{t}^{*}}{S_{0}}$ .In view of the facts that $\frac{S_{t}^{*}}{S_{0}}$ is an exponential martingale and $\left.\frac{S_{t}^{*}}{S_{0}}\right|_{t=0}=1$ ,       define a new measure $\tilde{\tilde{P}}$ by first defining $\tilde{\tilde{P}}_{t}$ by

$$
d\tilde{\tilde{P}}_{t}=\frac{S_{t}^{*}}{S_{0}}dQ
$$

and then setting $\bar{\tilde{P}}=\bar{\tilde{P}}_{T}$ .Thus by the machinery of Girsanov theo rem,       there exists $\widetilde{W}_{t}$ ,       which is a $\tilde{\tilde{P}}$ -Brownian motion such that

$$
d\widetilde{\widetilde{W}}_t=d\widetilde{W}_t-\sigma dt.
$$

Thus

$$
\widetilde{\widetilde{W}}_{t}=\widetilde{W}_{t}-\sigma t.
$$

Now from the fact that

$$
dS_t=S_t(rdt+\sigma d\widetilde{W}_t),
$$

We have

$$
\begin{aligned}S_{T}&=\quad S_{0}\mathrm{exp}\left[\left(r-\frac{1}{2}\sigma^{2}\right)T+\sigma\widetilde{W}_{t}\right]\\&=\quad S_{0}\mathrm{exp}\left[\left(r+\frac{1}{2}\sigma^{2}\right)T+\sigma\widetilde{\widetilde{W}}_{t}\right]\end{aligned}
$$

by (5.13). Hence $S_{T}>K$ if and only if

$$
d_1=\frac{\log(S_0/K)+\left(r+\frac{1}{2}\sigma^2\right)T}{\sigma\sqrt{T}}>-\frac{\widetilde{\widetilde{W}}_T}{\sqrt{T}}=Z,
$$

where $Z$ is a standard Gaussian random variable of mean 0 and variance 1. Therefore

$$
\begin{aligned}&E_{Q}\left[\frac{S_{T}}{B_{T}}\cdot\mathbf{1}_{\{S_{T>K}\}}\right]\\&=\quad E_{Q}\left[S_{T}^{*}\cdot\mathbf{1}_{\{S_{T>K}\}}\right]\\&=\quad S_{0}E_{Q}\left[\frac{S_{T}^{*}}{S_{0}}\cdot\mathbf{1}_{\{S_{T>K}\}}\right]\\&=\quad S_{0}\int_{\{S_{T>K}\}}\frac{S_{T}^{*}}{S_{0}}\:dQ\\&=\quad S_{0}\int_{\{S_{T>K}\}}d\widetilde{\tilde{P}}\\&=\quad S_{0}\int_{\{Z<d_{1}\}}d\widetilde{\tilde{P}}\\&=\quad S_{0}N(d_{1}).\end{aligned}
$$

Therefore we have

$$
V_0=S_0N(d_1)-Ke^{-rT}N(d_2).
$$

In general,       by shifting time and conditioning everything at time $t$ one can obtain the following:
Theorem 5.8. The price $V_{t}$ at time $t$ of the European call option $X=(S_{T}-K)^{+}$ is given by

$$
V_t=S_tN(d_1)-Ke^{-r(T-t)}N(d_2),
$$

Where

$$
\begin{aligned}N(d)&=\quad\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{d}e^{-x^{2}/2}dx,      \\d_{1}&=\quad\frac{\log(S_{t}/K)+(r+\frac{1}{2}\sigma^{2})(T-t)}{\sigma\sqrt{T-t}},      \\d_{2}&=\quad\frac{\log(S_{t}/K)+(r-\frac{1}{2}\sigma^{2})(T-t)}{\sigma\sqrt{T-t}}.\end{aligned}
$$

Note also that Theorem 5.8 provides a valuable information on the replicating portfolio. Namely,

$$
\begin{array}{rcl}\xi_t&=&-Ke^{-rT}N(d_2),      \\\zeta_t&=&N(d_1).\end{array}
$$

The negative sign of $\xi_{t}$ the short position of the riskless bond; the positive sign of $\zeta_{t}$ indicates the long position of the stock,       etc.

### 5.5 The Black-Scholes Partial Differential Equa-. Tion

The original derivation of the Black-Scholes formula Black and Sc holes gave was via the so-called Black-Scholes partial differential equation. In this section,       we present two derivations of the celebrated Black-Scholes PDE. The first one is via the martingale framework and the second without it.

### 5.5.1 First Derivation of the Black-Scholes PDE

We use the notations and facts from the previous sections. Recall that in the risk-neutral world,      i.e.,       with respect to the martingale measure,       the discounted stock price process satisfies.

$$
dS_t^*=\sigma S_t^*d\widetilde{W}_t,
$$

Which is equivalent to

$$
dS_t=S_t(rdt+\sigma d\widetilde{W}_t).
$$

Let $(\xi_{t},      \zeta_{t})$ be the self-financing portfolio consisting of $\xi_{t}$ units of riskless bond and $\zeta_{t}$ shares of stock that replicates the call option

$$
X=(S_T-K)^+
$$

with the expiry $T$ and the strick price $K$ .The existence of such portfolio was already verified in section 5.3,       and the discounted value $V_{t}^{*}$ of this portfolio is seen to satisfy

$$
\begin{array}{rcl}dV_t^*&=&\zeta_tdS_t^*\\&=&\sigma\zeta_tS_t^*d\widetilde W_t.\end{array}
$$

Let us now assume that $V_{t}$ can be expressed as

$$
V_t=C(t,      S_t)
$$

for some smooth deterministic function $C(t,      S)$ of two variables $t$ and $S$ .At this juncture,       we do not yet know such function exists. But we will later show that such function indeed exists. Define $C^{*}=$ $C^{*}(t,      S_{t})=C(t,      S_{t})/B_{t}=e^{-rt}C$ Then

$$
\begin{aligned}dC^{*}&=\quad d(e^{-rt}C)\\&=\quad e^{-rt}dC-re^{-rt}Cdt\\&=\quad e^{-rt}\left[\frac{\partial C}{\partial t}dt+\frac{\partial C}{\partial S}dS_{t}+\frac{1}{2}\frac{\partial^{2}C}{\partial S^{2}}(dS_{t})^{2}\right]-re^{-rt}Cdt.\end{aligned}
$$

Thelast equality is due toIto'sformula. It is tobe notedthat $\frac{\partial C}{\partial S}(t,      S)$ 全 $\frac{\partial C}{\partial S}=\frac{\partial C}{\partial S}(t,      S_{t})$ M S $C(t,      S)$ C $t$ apples to the $\frac{\partial C}{\partial t}$ and $\frac{\partial^{2}C}{\partial S^{2}}$ . Clleting termns and using (5.14),       we have

$$
\begin{aligned}dC^{*}&=\quad e^{-rt}\left[\frac{\partial C}{\partial t}+rS_{t}\frac{\partial C}{\partial S}+\frac{1}{2}\sigma^{2}S_{t}^{2}\frac{\partial^{2}C}{\partial S^{2}}-rC\right]dt\\&+\sigma e^{-rt}S_{t}\frac{\partial C}{\partial S}d\widetilde{W}_{t}.\end{aligned}
$$

Thus utilizing (5.14) the necessary and sufficient condition for $C(t,      S_{t})$ to be equal to $V_{t}$ is that

$$
\left.\frac{\partial C}{\partial t}+rS\frac{\partial C}{\partial S}+\frac{1}{2}\sigma^2S^2\frac{\partial^2C}{\partial S^2}-rC\right|_{t=t,      S=S_t}=0
$$

And

$$
\sigma e^{-rt}S_{t}\frac{\partial C}{\partial S}=\sigma\zeta_{t}S_{t}^{*}.
$$

Therefore by (5.17),       we must have

$$
\zeta_t=\frac{\partial C}{\partial S}=\frac{\partial C}{\partial S}(t,      S_t)
$$

and (5.16) says that the deterministic function $C(t,      S)$ of two variables $t$ and S must satisfies the following partial differential equation

$$
\begin{aligned}\frac{\partial C}{\partial t}+rS\frac{\partial C}{\partial S}+\frac{1}{2}\sigma^2S^2\frac{\partial^2C}{\partial S^2}-rC=0.\end{aligned}
$$

Thereasonfor the validity of this partialdifferential equation is that $S_{t}$ can take any positive value therefore (5.19) must hold for any $t\geq0$ and $S$ . (In fact it suffces to assume $S>0$ .But it is a moot point here.) Now it is easy to see that the replication condition is

$$
C(T,      S)=(S-K)^{+}.
$$

(5.18) is also very usefulin that it gives a methodor formula to calculate the number of shares of stock the replication portfolio is to have.

The promised proof of the existence of $C(t,      S)$ satisfying (5.15) can now be seen very easily. Namely,       suppose $C(t,      S)$ is a deterministic function of two variables satisfying (5.19) and (5.20). Then by backtracking the arguments presented above,       (5.15) can be easily seen to be satisfied by such $C(t,      S)$ . Thus the proof boils down to the existence of the solution of (5.19) and (5.20),       which will be shown in the subsequent sections

### 5.5.2 Second Derivation of the Black-Scholes PDE

The derivation given above is the most succinct and conceptually cleanest derivation of the Black-Scholes PDE. The reader is advised to get familiar with this type of argument. However,       it presupposes some knowledge of the risk-neutral valuation theory utilizing the martingale methodology. There is a way,       however,       to derive it directly withoutresorting to the martingale measure $Q$ and $Q$ Brownian motion $\widetilde{W}_{t}$ .This also is the way Black and Scholes originally derived it. Let us present it here.
As before,       the stock price process is assumed to satisfy

$$
dS_t=S_t(\mu dt+\sigma dW_t),
$$

where $W_{t}$ is a Brownian motion with respect to some Wiener measure $P$ ,       usually called the underlying (physical) measure.
Let $X=(S_{T}-K)^{+}$ be a European call option,       and let $(\xi_{t},      \zeta_{t})$ be a self-financing portfolio consisting of $\xi_{t}$ units of riskless bond and $\zeta_{t}$ shares of stock thatreplicates $X$ .Of course,       it is far from trivial that such portfolio exists. The existence of such portfolio is part of the derivation process of the Black-Scholes PDE given in this subsection.
Let us for now assume such portfolio exists,       and let

$$
V_t=\xi_tB_t+\zeta_tS_t
$$

be the value at time $t$ of such portfolio. Then the self-financing condition implies that $dV_{t}=\xi_{t}dB_{t}+\zeta_{t}dS_{t}$ . Therefore,

$$
\begin{aligned}
dV_{t}& =\:\xi_{t}dB_{t}+\zeta_{t}dS_{t} \\
&=\:re^{rt}\xi_{t}dt+\zeta_{t}S_{t}\left[\mu dt+\sigma dW_{t}\right] \\
&=\quad\left[re^{rt}\xi_{t}+\mu\zeta_{t}S_{t}\right]dt+\sigma\zeta_{t}S_{t}dW_{t}.
\end{aligned}
$$

As before,       let us assume that $V_{t}$ can be expressed as

$$
V_t=C(t,      S_t)
$$

175
for some smooth function $C(t,      S)$ of two variables $t$ and $S$ .Then by Ito's formula

$$
\begin{aligned}dC&=\quad\frac{\partial C}{\partial t}dt+\frac{\partial C}{\partial S}dS_{t}+\frac{1}{2}\frac{\partial^{2}C}{\partial S^{2}}(dS_{t})^{2}\\&=\quad\left[\frac{\partial C}{\partial t}+\mu S_{t}\frac{\partial C}{\partial S}+\frac{1}{2}\sigma^{2}S_{t}^{2}\frac{\partial^{2}C}{\partial S^{2}}\right]dt\\&+\sigma S_{t}\frac{\partial C}{\partial S}dW_{t}.\end{aligned}
$$

Equating (5.22) and (5.23) and collecting the coefficients of $dW_{t}$ ，we have

$$
\begin{matrix}\zeta_t&=&\frac{\partial C}{\partial S}(t,      S_t)\end{matrix}
$$

And

$$
\begin{matrix}re^{rt}\xi_t+\mu\zeta_tS_t&=&\frac{\partial C}{\partial t}+\mu S_t\frac{\partial C}{\partial S}+\frac{1}{2}\sigma^2S_t^2\frac{\partial^2C}{\partial S^2}.\end{matrix}
$$

Since

$$
V_t=C,      \quad V_t=e^{rt}\xi_t+\zeta_tS_t\quad\mathrm{and}\quad\zeta_t=\frac{\partial C}{\partial S},
$$

Plugging them (5.21),       we have

$$
\xi_t=e^{-rt}\left[C(t,      S_t)-S_t\frac{\partial C}{\partial S}(t,      S_t)\right].
$$

Plugging 5.24) and 5.26) into 5.25) and simplifying,       we have

$$
\left.\frac{\partial C}{\partial t}+rS\frac{\partial C}{\partial S}+\frac{1}{2}\sigma^2S^2\frac{\partial^2C}{\partial S^2}-rC\right|_{t=t,      S=S_t}=0,
$$

Which is exactly what we have derived before. Therefore the Black Scholes PDE (5.19) must also hold.
Note that in the Black-Scholes PDE,       the drift coefficient $\mu$ disappears and in its stead the riskless interest rate $Y$ appears. By the same token,       the physical measure $P$ plays no role but the martingale measure $Q$ is what matters
Let us now give an argument for the promised existence of the self-financing portfolio. Let $C$ be the solution of the Black-Scholes PDE (5.19) satisfying the condition

$$
C(T,      S)=(S-K)^+.
$$

As suggested by (5.24),       define $\zeta_{t}$ by

$$
\zeta_t=\frac{\partial C}{\partial S}(t,      S_t),
$$

and $\xi_{t}$ ,       as in (5.26),       by

$$
\xi_t=e^{-rt}\left[C(t,      S_t)-S_t\frac{\partial C}{\partial S}(t,      S_t)\right].
$$

Construct a portfolio consisting of $\xi_{t}$ units of riskless bond and $\zeta_{t}$ shares of stock. Then it is trivial to see that

$$
\begin{array}{rcl}V_t&=&e^{rt}\xi_t+\zeta_tS_t\\&=&C\\&=&C(t,      S_t).\end{array}
$$

Let us now prove the self-financing property of this portfolio. Rewriting the Black-Scholes PDE by

$$
\frac{\partial C}{\partial t}+\mu S_t\frac{\partial C}{\partial S}+\frac{1}{2}\sigma^2S_t^2\frac{\partial^2C}{\partial S^2}=(\mu-r)S_t\frac{\partial C}{\partial S}+rC
$$

And plugging this into (5.23),       we have

$$
\begin{array}{rcl}dV_t&=&dC(t,      S_t)\\&=&\left[(\mu-r)S_t\frac{\partial C}{\partial S}+rC\right]dt+\sigma S_t\frac{\partial C}{\partial S}dW_t.\end{array}
$$

Using $\zeta_{t}=\frac{\partial C}{\partial S}$ and pluging (531 into the above quation,       we then have

$$
\begin{aligned}
dV_{t}& =\:dC \\
&=\quad\left[(\mu-r)\zeta_{t}S_{t}+r(\xi_{t}e^{rt}+\zeta_{t}S_{t})\right]dt+\sigma\zeta_{t}S_{t}dW_{t} \\
&=\:r\xi_{t}e^{rt}dt+\zeta_{t}S_{t}\left[\mu dt+\sigma dW_{t}\right] \\
&=\:\xi_{t}dB_{t}+\zeta_{t}dS_{t},    
\end{aligned}
$$

Which is the self-financing condition we were after. The replicating condition is trivially satisfied by (5.28)

### 5.6 Solution of the Black-Scholes PDE

Now solve the Black-Scholes PDE (5.19) subject to the condition 5.20). Let $S_{0}$ be the constant that represents the known stock price

at time $t=0$ .Define $z=\log\left(S/S_{0}\right)$ and $\ddot{C}(t,      z)=C(t,      S)$ .Ther

$$
\begin{array}{rcl}\frac{\partial\tilde{C}}{\partial z}&=&S\frac{\partial C}{\partial S},      \\\frac{\partial^2\tilde{C}}{\partial z^2}&=&S^2\frac{\partial^2C}{\partial S^2}+S\frac{\partial C}{\partial S}.\end{array}
$$

Therefore,       Black-Scholes equation becomes

$$
\begin{aligned}\frac{\partial\widetilde{C}}{\partial t}+\left(r-\frac{1}{2}\sigma^2\right)\frac{\partial\widetilde{C}}{\partial z}+\frac{1}{2}\sigma^2\frac{\partial^2\widetilde{C}}{\partial z^2}-r\widetilde{C}=0.\end{aligned}
$$

Now let $x=Az+Bt$ .where $A$ and $B$ are constant tobe determined Let

$$
v(t,      \:x)=\tilde{C}(t,      \:z)=C(t,      \:S).
$$

Then

$$
\begin{aligned}\frac{\partial\tilde{C}}{\partial t}&=\quad\frac{\partial v}{\partial t}+\frac{\partial v}{\partial x}\frac{\partial x}{\partial t}=\frac{\partial v}{\partial t}+B\frac{\partial v}{\partial x},      \\\frac{\partial\tilde{C}}{\partial z}&=\quad\frac{\partial v}{\partial t}\frac{\partial t}{\partial z}+\frac{\partial v}{\partial x}\frac{\partial x}{\partial z}=A\frac{\partial v}{\partial x},      \\\frac{\partial^{2}\tilde{C}}{\partial z^{2}}&=\quad A^{2}\frac{\partial^{2}v}{\partial x^{2}}.\end{aligned}
$$

Therefore 5.32 becomes

$$
\frac{\partial v}{\partial t}+\left(B+\left(r-\frac{1}{2}\sigma^2\right)A\right)\frac{\partial v}{\partial x}+\frac{1}{2}\sigma^2A^2\frac{\partial^2v}{\partial x^2}-rv=0.
$$

Let us choose $A$ and $B$ so that

$$
B+\left(r-\frac{1}{2}\sigma^2\right)A=0\quad\mathrm{and}\quad\sigma A=1,
$$

i.e.,

$$
A=\frac1\sigma\quad\text{and}\quad B=-\frac1\sigma\left(r-\frac12\sigma^2\right).
$$

Then (5.33) becomes

$$
\begin{aligned}\frac{\partial v}{\partial t}+\frac{1}{2}\frac{\partial^2v}{\partial x^2}-rv=0.\end{aligned}
$$

Define

$$
u(t,      \:x)=e^{-rt}v(t,      \:x),
$$

Then 5.35 becomes

$$
\begin{aligned}\frac{\partial u}{\partial t}+\frac{1}{2}\frac{\partial^2u}{\partial x^2}=0.\end{aligned}
$$

If we replace of $A$ and $B$ in $3L$ by 5.34 ther

$$
x=\frac1\sigma z-\frac1\sigma\Big(r-\frac12\sigma^2\Big)t,
$$

And so

$$
z=\left(r-\frac{1}{2}\sigma^{2}\right)t+\sigma x.
$$

Back to the first change of variable,       we have

$$
\begin{array}{rcl}S&=&S_0e^z\\&=&S_0\exp\left(\left(r-\frac{1}{2}\sigma^2\right)t+\sigma x\right).\end{array}
$$

In conclusion,       if $u$ is defined by

$$
u(t,      \:x)=e^{-rt}v(t,      \:x)=e^{-rt}C(t,      \:S),
$$

$U.$ satisfies the following heat equation initial boundary problem

$$
\left\{\begin{array}{l}\frac{\partial u}{\partial t}+\frac{1}{2}\frac{\partial^2u}{\partial x^2}=0\\\\u(T,      \:x)=e^{-rT}C(T,      \:S),      \end{array}\right.
$$

where $3L$ and $S$ are related by

$$
S=S_0\exp\Bigl(\Bigl(r-\frac{1}{2}\sigma^2\Bigr)t+\sigma x\Bigr).
$$

The equation in (5.38) is the so-called heat equation,       but with the time seemingly fowing backward. However,       if we make one more substitution $\tau\:=\:T-t$ for time,       (5.38）becomes an equation for $u(\tau,      x)$ satisfying

$$
\left\{\begin{array}{l}\frac{\partial u}{\partial\tau}=\frac{1}{2}\frac{\partial^2u}{\partial x^2}\\\\u(0,      x)=e^{-rT}C(T,      S).\end{array}\right.
$$

This is the usual form of the initial value problem of the heat equation. In other words,       (5.38) is the correct,       well-posed heat equation

because the initial condition $u(T,      x)=e^{-r^{\prime}I^{\prime}}C(T,      S)$ is posed at a future time while we are interested in the solution at times before that fixed future time. Incidentally,       in finance literature,       (5.38) is called the boundary value problem It is a well known fact from the theory of parabolic (heat) equa
tions the solution $u(t,      x)$ of (5.38) can be written as

$$
u(t,      x)=\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi(T-t)}}e^{-\frac{(x-y)^2}{2(T-t)}}u(T,      y)dy.
$$

Here the function

$$
\frac{1}{\sqrt{2\pi(T-t)}}\:e^{-\frac{(x-y)^2}{2(T-t)}}
$$

is called the heat kernel (for (5.38)） and its probabilistic meaning is that it represents the probability density function for aBrownian particle (motion) to move from $y$ to $3L$ in time $T-t$
Let us now derive the value of theEuropean call option. Since the stockprice attime $t=0$ is $S_{0}$ ,       it must be $C(0,      S_{0})$ . It is easily seen from (5.37) that this case correspond to the case in which $t=0$ and $x=0$ .Namely,       by 5.40 the options value at time $t=0$ is nothing but

$$
u(0,      0)=\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi T}}\:e^{-\frac{x^{2}}{2T}}\:u(T,      \:x)dx.
$$

We now derive the Black-Scholes formula for the call option. Note that

$$
u(T,      x)=e^{-rT}(S_T-K)^+.
$$

By (5.41),

$$
u(0,      0)=\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi T}}e^{-\frac{x^{2}}{2T}}e^{-rT}(S_{T}-K)^{+}dx,
$$

where at $T$ ， $S_{T}$ and $JL$ are related by

$$
S_T=S_0\exp\left(\left(r-\frac{1}{2}\sigma^2\right)T+\sigma x\right).
$$

One can compute $u(0,      0)$ as follows:

$$
\begin{aligned}
u(0,      0)& \begin{array}{rcl}{=}&{{e^{-rT}\int_{D}{\frac{1}{\sqrt{2\pi T}}}e^{-{\frac{x^{2}}{2T}}}\left(S_{0}\exp\left(\left(r-{\frac{1}{2}}\sigma^{2}\right)T+\sigma x\right)-K\right)dx}}\end{array} \\
&=\:e^{-rT}\int_{D}\frac{1}{\sqrt{2\pi T}}e^{-\frac{x^{2}}{2T}}S_{0}\exp\biggl(\biggl(r-\frac{1}{2}\sigma^{2}\biggr)T+\sigma x\biggr)dx \\
&-Ke^{-rT}\int_{D}\frac{1}{\sqrt{2\pi T}}e^{-\frac{x^{2}}{2T}}dx \\
&=\quad\mathrm{I}_{1}-Ke^{-rT}\mathrm{I}_{2},    
\end{aligned}
$$

 Where

$$
\begin{aligned}
&\text{D} =\Big\{x:S_{0}\exp\Big(\Big(r-\frac{1}{2}\sigma^{2}\Big)T+\sigma x\Big)>K\Big\},       \\
&\text{I} _{\lfloor}=e^{-rT}\int_{D}{\frac{1}{\sqrt{2\pi T}}}e^{-{\frac{x^{2}}{2T}}}S_{0}\exp\Bigl(\Bigl(r-{\frac{1}{2}}\sigma^{2}\Bigr)T+\sigma x\Bigr)dx,       \\
&\text{I} :=\int_{D}{\frac{1}{\sqrt{2\pi T}}}e^{-{\frac{x^{2}}{2T}}}dx.
\end{aligned}
$$

### Compute $1_{2}$

Put $y=\frac{x}{\sqrt{T}}$ then

$$
\begin{aligned}D&=\quad\left\{x:S_{0}\exp\Bigl(\Bigl(r-\frac{1}{2}\sigma^{2}\Bigr)T+\sigma x\Bigr)>K\right\}\\&=\quad\Big\{y:y>-\frac{\log(S_{0}/K)+(r-\frac{1}{2}\sigma^{2})T}{\sigma\sqrt{T}}\Big\},      \end{aligned}
$$

And

$$
\begin{aligned}
\mathrm{I}_{2}& =\:\int_{D}\frac{1}{\sqrt{2\pi}}e^{-\frac{y^{2}}{2}}dy \\
&=\:\int_{-\frac{\log(S_{0}/K)+(r-\frac{1}{2}\sigma^{2})T}{\sigma\sqrt{T}}}^{\infty}\frac{1}{\sqrt{2\pi}}e^{-\frac{y^{2}}{2}}dy \\
&=\:\int_{-\infty}^{\frac{\log(S_{0}/K)+(r-\frac{1}{2}\sigma^{2})T}{\sigma\sqrt{T}}}\frac{1}{\sqrt{2\pi}}e^{-\frac{y^{2}}{2}}dy \\
&=\quad N\Big(\frac{\log(S_{0}/K)+(r-\frac{1}{2}\sigma^{2})T}{\sigma\sqrt{T}}\Big).
\end{aligned}
$$

### Compute $I_{1}$

Put $y=\frac{x-\sigma T}{\sqrt{T}}$ then

$$
\begin{aligned}D&=\quad\Big\{x:S_{0}\exp\Big(\Big(r-\frac{1}{2}\sigma^{2}\Big)T+\sigma x\Big)>K\Big\}\\&=\quad\Big\{y:y>-\frac{\log(S_{0}/K)+(r+\frac{1}{2}\sigma^{2})T}{\sigma\sqrt{T}}\Big\},      \end{aligned}
$$

And

$$
\begin{gathered}
\text{I1} \begin{array}{rcl}{=}&{{S_{0}\int_{D}{\frac{1}{\sqrt{2\pi T}}}\mathrm{exp}\Big(-{\frac{1}{2}}\Big({\frac{x-\sigma T}{\sqrt{T}}}\Big)^{2}\Big)dx}}\end{array} \\
=\:S_{0}\int_{-\frac{\log(S_{0}/K)+(r+\frac{1}{2}\sigma^{2})T}{\sigma\sqrt{T}}}^{\infty}\frac{1}{\sqrt{2\pi}}e^{-\frac{y^{2}}{2}}dy \\
=\quad S_{0}\int_{-\infty}^{\frac{\log(S_{0}/K)+(r+\frac{1}{2}\sigma^{2})T}{\sigma\sqrt{T}}}\frac{1}{\sqrt{2\pi}}e^{-\frac{y^{2}}{2}}dy \\
=\quad S_{0}N\left(\frac{\log(S_{0}/K)+(r+\frac{1}{2}\sigma^{2})T}{\sigma\sqrt{T}}\right).
\end{gathered}
$$

Therefore,       we can obtain the following

$$
C(0,      S_0)=S_0N(d_1)-e^{-rT}KN(d_2),
$$

Where

$$
\begin{gathered}
d_{1} =\frac{\log(S_{0}/K)+(r+\frac{1}{2}\sigma^{2})T}{\sigma\sqrt{T}},       \\
d_{2} =\frac{\log(S_{0}/K)+(r-\frac{1}{2}\sigma^{2})T}{\sigma\sqrt{T}}.
\end{gathered}
$$

In general,       if we know the value $S_{t}$ at time $t$ ，then we can apply the same formula to get

$$
C(t,      S_t)=S_tN(d_1)-e^{-r(T-t)}KN(d_2),
$$

where $T-t$ is the time to expiry from time $t$ and

$$
d_{1}=\quad\frac{\log(S_{t}/K)+(r+\frac{1}{2}\sigma^{2})(T-t)}{\sigma\sqrt{T-t}},      \\d_{2}=\quad\frac{\log(S_{t}/K)+(r-\frac{1}{2}\sigma^{2})(T-t)}{\sigma\sqrt{T-t}}.
$$

Note also that (5.43) provides a valuable information on the repli cating portfolio. Namely,

$$
\left\{\begin{array}{ll}\xi_t=-Ke^{-rT}N(d_2),      \\\\\zeta_t=N(d_1).\end{array}\right.
$$

The negative sign of $\xi_{t}$ the short position of the riskless bond; the positive sign of $\zeta_{t}$ indicates the long position of the stock.

### 5.7 Put-Call Parity

Let $X$ be the European call option with the expiry $T$ and the strike price $K$ ,      i.e

$$
X=(S_T-K)^+
$$

as $\mathcal{F}_{T}$ measurable random variables. Let $C_{t}$ be its value at time $t$ Then the risk-neutral valuation principle,       Theorem 5.7,       says that

$$
C_t=B_tE_Q\left[\frac{X}{B_T}\mid\mathcal{F}_t\right],
$$

where $CQ$ is the martingale measure. Let $Y$ be the European put option with the same expiry $T$ and the same strike price $K$ . Namely,       $Y\:=\:(K\:-\:S_{T})^{+}$ .Then these call and put options are intricately linked via a principle called the“put-call parity." Let $P_{t}$ be the value of $Y$ at time $t$ ，then Theorem 5.7 says that

$$
P_{t}=B_{t}E_{Q}\left[\frac{Y}{B_{T}}\mid\mathcal{F}_{t}\right].
$$

Note now that

$$
C_T-P_T=X-Y=S_T-K.
$$

Therefore,       upon applying the risk-neutral valuation principle,       The
 ![500](https://storage.simpletex.cn/view/fGBEgFH5E0epsDaAgPHDchYPBMEQ6GPbP)
Figure 5.10: Payoff of $CT$
Orem 5.7,       to the above,       wehave

$$
\begin{aligned}
C_{t}-P_{t}& =\quad B_{t}E_{Q}\left[\frac{X-Y}{B_{T}}\mid\mathcal{F}_{t}\right] \\
&=\:B_{t}E_{Q}\left[\frac{S_{T}}{B_{T}}\mid\mathcal{F}_{t}\right]-B_{t}E_{Q}\left[\frac{K}{B_{T}}\mid\mathcal{F}_{t}\right] \\
&=\:S_{t}-Ke^{-r(T-t)}.
\end{aligned}
$$

 ![500](https://storage.simpletex.cn/view/frhZxzszm5UKG8cuIFVGYT1Tf2hQFANyC)
Figure 5.11: Payoff of $P_{T}$
 ![500](https://storage.simpletex.cn/view/f9gdkFwh2kmMpgtyWGmmx35dwyeM4wLFl)
Figure 5.12: Payoff of $C_{T}-P_{T}$
The last equality is the consequence of the fact that $S_{t}^{*}=S_{t}/B_{t}$ is a $Q$ -martingale and that $B_{t}=e^{rt}$ .(5.45) combined with the BlackScholes formula (5.43) gives the Black-Scholes formula for put option. From (5.45),       we have

$$
\begin{aligned}P_{t}&=\quad C_{t}-S_{t}+Ke^{-r(T-t)}\\&=\quad-S_t\left(1-N(d_1)\right)+Ke^{-r(T-t)}\left(1-N(d_2)\right)\\&=\quad-S_{t}N(-d_{1})+Ke^{-r(T-t)}N(-d_{2})\end{aligned}
$$

Where

$$
d_{1}=\quad\frac{\log(S_{t}/K)+(r+\frac{1}{2}\sigma^{2})(T-t)}{\sigma\sqrt{T-t}},      \\d_{2}=\quad\frac{\log(S_{t}/K)+(r-\frac{1}{2}\sigma^{2})(T-t)}{\sigma\sqrt{T-t}}.
$$

Here we used the fact that

$$
1-N(d)=N(-d)
$$

for the cumulative normal distribution $N(d)$
This Black-Scholes formula also gives the replicating portfolio $(\xi_{t},      \zeta_{t})$ for the put option that consists of $\xi_{t}$ units of riskless bond and $\zeta_{t}$ shares of stock by

$$
\left\{\begin{array}{ll}\xi_t=Ke^{-rT}N(-d_2),      \\\\\zeta_t=-N(-d_1).\end{array}\right.
$$

### Appendix

 ![500](https://storage.simpletex.cn/view/fxa3qvEsXPO7Qs8VPL9RCWV58aT5hoSgE)
Figure 5.2: 1-day percentage changes of KOSPI 200.
 ![500](https://storage.simpletex.cn/view/finYmeh5KrRk00hXNNinUnSWnAR6QrNS2)
Figure 5.3: 1-day percentage changes of KOSPI 200 with Normal Distribution Approximation.

 ![500](https://storage.simpletex.cn/view/fYYVVnMOGDLqd7DnxwTWDGNnqSoNvdfoZ)
Figure 5.4: 2-day percentage changes of KOSPI 200 with Normal Distribution Approximation
 ![500](https://storage.simpletex.cn/view/fZ5QHYCkMIiQuSXoZGAky6lgqkXArY0x1)
Figure 5.5: 3-day percentage changes of KOSPI 200 with Normal Distribution Approximation

 ![500](https://storage.simpletex.cn/view/fnd0crhyxU1d7XtfIEiPf362chZcAN3ig)
Figure 5.6: 5-day percentage changes of KOSPI 200 with Normal Distribution Approximation
 ![500](https://storage.simpletex.cn/view/fnl2xNcDvTK1NKmWA17ISKSPgUGSCM5l3)
Figure 5.7:7-day percentage changes of KOSPI 200 with Normal Distribution Approximation.

 ![500](https://storage.simpletex.cn/view/fPkeABOgRryFG7wRNgu2g3v2LFmGdPRDk)
Figure 5.8: Overlaid normal distributions.
 ![500](https://storage.simpletex.cn/view/fL4PBqggGIezYei4q2E6hEKAHuHFiSzXG)
Figure 5.9: Change of the $h$ -day Volatilities
