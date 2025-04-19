---
tags:
  - affine_models
  - futures
  - options
  - sofr
  - swaption
aliases:
  - Gaussian models
  - SOFR derivative pricing
  - SOFR derivatives
key_concepts:
  - Affine term structure models
  - Analytic pricing formula
  - European SOFR options
  - Overnight Treasury repo rate
  - SOFR reference rate
---

# SOFR Derivative Pricing Using a Short Rate Model

Mingyang Xu  

Investment Analytics, AIG  

# Abstract  

In 2017 the Alternative Reference Rate Committee (ARRC) recommended the Secured Overnight Financing Rate (SOFR) as the replacement for UsD LIBOR as the reference rate for use in derivatives and financial contracts. Since then SOFR-linked derivatives started to develop and their liquidities have also improved gradually. Compared to LIBOR derivatives, pricing SOFR derivatives poses additional challenges, for example, complexity due to rate averaging and convexity adjustment due to timing mismatch. In this paper we propose Gaussian affine term structure models as a natural choice to address these challenges. Because of the advantages of affine models and Gaussian models we derive analytic pricing formula for forward SOFR term rates as well as future SOFR term rates, which can then be used to price most linear SOFR products. Furthermore, since the short rate is normally distributed, closed-form solutions based on Black-Scholes or Bachelier formula are also derived for European SOFR options, including SOFR swaptions, SOFR cap/floor and options on SOFR futures. Although American options cannot be priced analytically, efficient numerical methods are developed by combining lattice and analytic formula.  

# Key words:  

SOFR, Averaging, Affine, Hull-White, Swaption, Option, Futures, Callable Floater, Convexity Adjustment  

# 1. Introduction  

The Secured Overnight Financing Rate (SOFR) is the cost of borrowing overnight collateralized by Treasury securities, i.e. overnight Treasury repo rate. The SOFR is published by the New York Federal Reserve Bank publishes the SOFR on a daily basis. Unlike Libor, SOFR is an actual transaction rate. It is calculated as the volume-weighted median rate of all eligible transactions. SOFR typically trades close to overnight LIBOR, but with higher volatility due to its methodology and wide dispersion in bilateral repo data.  

As the SOFR is expected to replace Libor as the index of choice sometimes in 2021, the SOFR linked derivative market started to develop in the past few years, and its liquidity greatly improved.  

SOFR derivatives tend to use an averaged overnight rate over a given period, which is often either simple interest (Arithmetic Average) or compound interest (Geometric Average) (ARCc, 2021)  

$$
R_{G}=\left[\prod_{i=1}^{d_{b}}\left(1+\frac{r_{i}\times n_{i}}{N}\right)-1\right]\times\frac{N}{d_{c}}
$$  

$$
R_{A}=\left[\sum_{i=1}^{d_{b}}\frac{r_{i}\times n_{i}}{N}\right]\times\frac{N}{d_{c}}
$$  

where  

${\mathsf{d}}_{\mathsf{b}}=$ the number of business days in the interest rate period $\mathsf{d}_{\mathsf{c}}=$ the number of calendar days in the interest rate period ${\sf r}_{\mathrm{i}}=$ the interest rate on the ith business day ${\mathsf{n}}_{\mathrm{i}}=$ the number of calendar days for which $\mathsf{r}_{\mathrm{i}}$ is applied ${\mathsf N}=$ the number of calendar days in the year  

If the SOFR rate is a daily compounded interest rate, compounding is equivalent to rolling forward a money market account, and thus.  

$$
R_{G}=\left[\prod_{i=1}^{d_{b}}\left(1+\frac{r_{i}\times n_{i}}{N}\right)-1\right]\times\frac{N}{d_{c}}=\left[\frac{1}{D(t,T)}-1\right]\times\frac{1}{T-t}
$$  

with ${\sf D}(\sf t,\top)$ defined as  

$$
D(t,T)=\frac{1}{M(t,T)}=\exp{(-\int_{t}^{T}r(u)d u)}
$$  

which is similar to the calculation of simple Libor rate.  

Similarly, the simple average of SOFR rate is also approximately by its continuous version  

$$
R_{A}=\left[\sum_{i=1}^{d_{b}}{\frac{r_{i}\times n_{i}}{N}}\right]\times{\frac{N}{d_{c}}}\approx\left(\int_{t}^{T}r_{u}d u\right){\frac{1}{T-t}}={\frac{\ln{\frac{1}{D(t,T)}}}{T-t}}
$$  

which is similar to continuous compounded forward rate.  

Although compound interest is the more economically correct convention, simple interest is easier to calculate in practice and most existing system can accommodate it. On the other hand, simple interest. makes pricing much more complicated because of the extra convexity adjustment that requires a. stochastic interest rate model.  

Moreover, the fixing of the floating rate of a SOFR derivative can be either in-advance or in-arrears. An. in-advance structure would reference an average of SOFR observed before the beginning of the current interest period, while an in-arrears structure would reference an average of SOFR over the current  

interest period. An average of SOFR in-arrears will reflect what actually happens over the period, but loan borrowers usually prefer to know their payments ahead of time, i.e. in-advance fixing..  

In the case of average SOFR fixing, extra time is also necessary in order to wait for the daily SOFR to be published and the average SOFR rate to be calculated and posted (c.g. ARcC, 2021). This results in. additional convexity adjustment because of timing lags.  

Thus, all of these, including averaging and timing lags, add to the complexity of pricing SOFR derivatives. In order to deal with them a short rate model seems a natural choice. In the following we will discuss pricing methods for various SOFR derivatives using a short rate model. The rest of the paper is organized. as follows: section 2 defines forward SOFR term rates and describes how to build a SOFR curve usinge. SOFR swaps; section 3 applies a Gaussian mean-reverting model to model the dynamics of continuous. SOFR rate and derives forward and futures SOFR term rates; section 4 derives analytic pricing formulas. for various SOFR derivatives based on the SOFR curve and SOFR short rate model; and section 5 concludes the paper.  

# 2. Forward SOFR Term Rate and SOFR Curve  

2.1 Forward SOFR Term Rate  

While the overnight treasury repo market underlying SOFR is extraordinarily deep, term repo markets are much thinner, and thus it would not be possible to build a robust forward-looking term rate off the term Treasury repo market.  

Suppose a future floating payment at. ${\sf T}_{\mathrm{i}}$ is linked to the compound sOFR rate, i.e.  

$$
P a y m e n t=N\cdot\delta\cdot R_{G}(T_{i})
$$  

With unit Its present value at $\mathrm{\Deltat}$ is given by  

$$
V(t)=E[\delta\cdot R_{G}(T_{i})D(t,T_{i})]=E\left[\left(\frac{D(t,T_{i-1})}{D(t,T_{i})}-1\right)D(t,T_{i})\right]=P(t,T_{i-1})-P(t,T_{i})
$$  

where in term of money market account ${\mathsf{M}}({\mathsf{T}})$ or discounting factor. ${\sf D}(t,\top)$ the SOFR term rate at ${\mathsf{T}}_{\mathrm{i}}$  

$$
R_{G}(T_{i})=\frac{1}{\delta}\left(\frac{M(T_{i})}{M(T_{i-1})}-1\right)=\frac{1}{\delta}\left(\frac{D(t,T_{i-1})}{D(t,T_{i})}-1\right)
$$  

Meanwhile, we have under the ${\sf T}_{\mathrm{i}}$ -forward measure  

$$
V(t)=P(t,T_{i})\delta E^{T_{i}}[R_{G}]
$$  

and thus we have forward SOFR rate  

$$
f_{R_{G}}(t)=E^{T_{i}}[R_{G}]=\frac{1}{\delta}\frac{V(t)}{P(t,T_{i})}=\frac{1}{\delta}\Bigg(\frac{P(t,T_{i-1})}{P(t,T_{i})}-1\Bigg)
$$  

which can be calculated from a discount curve $\{\mathsf{P}(\mathtt{t},\top)\}$  

Similarly, we can define the forward-looking SOFR term rate for the arithmetic average of SOFR rate as the expected rate under the ${\sf T}_{\mathrm{i}}$ forward measure  

$$
f_{R_{A}}(t)=E^{T_{i}}[R_{A}]=\frac{1}{T_{i}-T_{i-1}}\int_{T_{i-1}}^{T_{i}}E^{T_{i}}[r_{u}]d u
$$  

which cannot be calculated directly from a discount curve without an interest rate model.  

Thus, in order to calculate forward SOFR term rates at least a SOFR forward curve is required.  

# 2.2 Build Forward SOFR Curve  

Similar to any other yield curves, a SOFR curve can be built by matching the market quotes of SOFR-. linked instruments. However, during the LIBOR era and after the LIBOR era, the choice of instrument is different.  

Before the LIBOR completely retires, the SOFR market is not deep enough and a SOFR curve can be built using SOFR futures and SOFR-LIBOR basis swaps.  

After the LIBOR retires, a SOFR curve can be built using 3M SOFR futures (short-end) up to 20 months and SOFR swaps (long-end) from 2 years on..  

Since a SOFR forward rate is related to the corresponding SOFR futures rate  

$$
\begin{array}{c}{{f_{R}(t)=E^{T}[R]=\displaystyle\frac{1}{\delta}\bigg(\frac{P(t,T_{0})}{P(t,T)}-1\bigg)=E[R]+C o n v e x i t y A d j u s t m e n t}}\ {{=F_{R}(t)+C o n v e x i t y A d j u s t m e n t}}\end{array}
$$  

SOFR discount factors can be calibrated using SOFR futures rates together with convexity adjustment.  

SOFR fixed vs floating swaps are valued in a similar way to LIBOR vanilla swaps and thus can be used to calibrate long term rates. The valuation of SOFR swaps will be discussed in detail later.  

# 3. SOFR Short Rate Model  

Corresponding to SOFR rate, instantaneous short rate models, including both spot rate and forward rate, seem to be a natural choice for modeling interest rate dynamics..  

Assume the short rate follows a mean-reverting Gaussian process, i.e. Hull-White model, (c.g. Brigo and Mercurio, 2001)  

$$
\begin{array}{c}{r(t)=\varphi(t)+x(t)}\ {\quad}\ {d x_{t}=-k x_{t}d t+\sigma(t)d W}\end{array}
$$  

whose model parameters can be first calibrated to swaption volatilities. Moreover, the drift parameter, $\varphi({\sf t}).$ , is tuned to match the SOFR curve term structure before it is used to price SOFR instruments, i.e.  

$$
e x p\left(-\int_{0}^{T}\varphi(t)d t\right)E\left[e x p\left(-\int_{0}^{T}x(t)d t\right)\right]=P(t,T)
$$  

One can show that under the ${\sf T}_{\mathrm{i}}$ -forward measure the dynamics of the state variable $\mathbf{\boldsymbol{\times}}(\mathbf{\boldsymbol{t}})$ follow as SDE  

$$
d x(t)=(-B(t,T_{i})\sigma(t)^{2}-k x(t))d t+\sigma(t)d W_{t}^{r,T_{i}}
$$  

whose strong solution is given by  

$$
x(\tau)=E^{T_{i}}[x(\tau)|\mathcal{F}_{t}]+\exp{(-k\tau)}\int_{t}^{\tau}\exp{(k u)}\sigma(u)d W_{u}^{r,T_{i}}
$$  

with  

$$
\langle{\boldsymbol\tau})|{\mathcal{F}_{t}}\right]=e x p\left(-\int_{t}^{\tau}\kappa(u)d u\right)\boldsymbol{x}(t)-e x p\left(-\int_{t}^{\tau}\kappa(u)d u\right)\int_{t}^{\tau}{e x p\left(\int_{t}^{u}\kappa(v)d v\right)}\boldsymbol{B}(u,T_{i})d u,
$$  

where  

$$
B(t,T)=\exp\left(\int_{0}^{t}k(u)d u\right)\int_{t}^{T}e x p\left(-\int_{0}^{u}k(s)d s\right)d u=\int_{t}^{T}e x p\left(-\int_{t}^{u}k(s)d s\right)d u
$$  

Thus, the SOFR forward term rate for both types of averaging are given by  

$$
\begin{array}{l}{{{\displaystyle{\vphantom{\displaystyle{\frac{r_{i}}{R_{G}}}}}}\^{e}_{R_{G}}(t)={\displaystyle{\cal E}^{T_{i}}[R_{G}]=\frac{1}{\delta}}\bigg(\frac{P(t,T_{i-1})}{P(t,T_{i})}-1\bigg)}~}\ {{\displaystyle~=\frac{e x p\left(\int_{T_{i-1}}^{T_{i}}\varphi(u)d u+A(t,T_{i-1})-A(t,T_{i})-\big(B(t,T_{i-1})-B(t,T_{i})\big)x_{t}\right)+\cal E}_{1}~}{{\displaystyle T_{i}-T_{i-1}}}~.}\end{array}
$$  

and  

$$
)=E^{T_{i}}[R_{A}]={\frac{1}{T_{i}-T_{i-1}}}\int_{T_{i-1}}^{T_{i}}E^{T_{i}}[r_{u}]d u={\frac{1}{T_{i}-T_{i-1}}}\left(\int_{T_{i-1}}^{T_{i}}\varphi(u)d u+\int_{T_{i-1}}^{T_{i}}E^{T_{i}}[x(u)|{\mathcal{F}}_{t}]d u\right).
$$  

respectively.  

In a special case where $k$ is constant, we have  

$$
\begin{array}{r l r}{\lefteqn{\int_{T_{i-1}}^{T_{i}}E^{T_{i}}[x(\tau)|\mathcal{F}_{t}]d\tau}}\ &{}&{=x(t)\frac{e x p(-k(T_{i-1}-t))-e x p(-k(T_{i}-t))}{k}}\ &{}&{\displaystyle-\int_{T_{i-1}}^{T_{i}}e x p(-k\tau)d\tau\int_{t}^{\tau}\frac{\exp{(k u)}-e x p\left(-k(T_{i}-2u)\right)}{k}\sigma(u)^{2}d u}\end{array}
$$  

where  

$$
B(t,T)=\frac{1-\exp{(-k(T-t)})}{k}
$$  

and  

$$
\mathtt{\Psi}_{}^{\mathtt{Y}_{i}}[x(\tau)|\mathcal{F}_{t}]=e x p(-k(\tau-t))x(t)-e x p(-k\tau)\int_{t}^{\tau}\frac{\exp{(k u)}-e x p\big(-k(T_{i}-2u)\big)}{k}\sigma(u)
$$  

In a more general case where neither $\mathsf{k}$ nor $\upsigma$ is constant, we can calculate the 2-dimensional integratior by first change the order of integration and then numerically integrating by splitting into sub-intervals  

# 4. SOFR Derivative Pricing  

# 4.1 SOFR Futures  

A single Eurodollar futures contract is similar to a forward rate agreement to borrow or lend US\$1,ooo,o00 for three months starting on the contract settlement date. Buying the contract is equivalent to lending money, and selling the contract short is equivalent to borrowing money.  

SOFR futures are similar to Eurodollar futures, and their final settlement price are calculated as  

$$
P r i c e=100-R
$$  

where 1M SOFR futures use simple interest  

$$
R={\frac{\sum_{i}\delta_{i}r_{i}}{\sum_{i}\delta_{i}}}\times100=\left[\sum_{i=1}^{d_{b}}{\frac{r_{i}\times n_{i}}{360}}\right]\times{\frac{360}{d_{c}}}\times100
$$  

while 3M SOFR futures use compounded interest  

$$
R=\left[\prod_{i=1}^{d_{b}}\left(1+\frac{r_{i}\times n_{i}}{360}\right)-1\right]\times\frac{360}{d_{c}}\times100\
$$  

where ${\mathsf{d}}_{\mathsf{b}}$ denotes the number business days during the calculation period, either 1M or 3M, and r, is the SOFR rate published by Fed NY next day.  

The 3M futures are worth $\$2500$ per index point and the 1M futures are worth. $\$4167$ per index point. One can think of the 3M futures as having a. $\$1$ million face value and the 1M futures as having a $\$5$ million face value, since.  

$$
\begin{array}{l c r}{{2500=1000000\times\displaystyle\frac{1}{100}\times\frac{3}{12}}}\ {{}}\ {{4167\approx10000000\times\displaystyle\frac{1}{100}\times\frac{1}{12}}}\end{array}
$$  

Note that SOFR futures uses day counter Act/360 Fixed. Also note that for 3M SOFR futures the month symbol refers to the beginning of the calculation period, not the month for final settlement, while for 1M sOFR futures the month symbol refers to the delivery month for that contract.  

Define a daily rolling money market account  

$$
M(T)=M(T_{0})\prod_{i=1}^{d_{b}}\left(1+\frac{r_{i}\times n_{i}}{360}\right)
$$  

where $d_{b}$ is the number of business days between $\tau_{o}$ and $\tau$ With rolling money market account the compounded interest can be rewritten as  

$$
R_{G}=\left[\frac{M(T)}{M(T_{0})}-1\right]\times\frac{1}{T-T_{0}}\times100\
$$  

where ${\sf T}_{0}$ denotes the beginning of the calculation period and $\intercal$ is the settlement date. For example, for 3M SOFR futures $\mathsf{T}-\mathsf{T}_{0}=3\mathsf{M}$  

Like any other futures contracts there is a convexity adjustment between futures and forward price or rate due to daily settlement, and the convexity adjustment is computed by  

$$
F_{R_{G}}(t)-f_{R_{G}}(t)=E[R_{G}]-E^{T}[R_{G}]
$$  

where by definition the forward rate is martingale under the $\intercal$ -forward measure  

$$
f_{R_{G}}(t)=E^{T}[R_{G}]=\frac{1}{\delta}\biggl(\frac{P(t,T_{0})}{P(t,T)}-1\biggr)
$$  

With daily settlement, the SOFR futures rate (without discounting) must be a martingale under the spot risk-neutral measure, i.e.  

$$
F_{R_{G}}(t)=\frac{1}{T-T_{0}}E\left[\frac{M(T)}{M(T_{0})}-1\right|\mathcal{F}_{t}\right]=\frac{1}{T-T_{0}}\left(\frac{E\left[M(T)|\mathcal{F}_{t}\right]}{M(T_{0})}-1\right)
$$  

which requires an interest rate model in order to compute the convexity adjustment.  

Assuming the SOFR rate is governed by a 1-Factor Hull-White model, we can calculate the futures SOFR rate for $\mathsf{T}_{0}{>}\mathsf{t}$  

$$
\begin{array}{l}{{\displaystyle{\vec{\bf\tau}}_{R_{G}}(t)=\frac{1}{T-T_{0}}\left(\frac{P(t,T_{0})}{P(t,T)}-1\right)}}\ {{\displaystyle~+\frac{1}{T-T_{0}}\frac{P(t,T_{0})}{P(t,T)}\left[\exp\left(A(t,T)-A(t,T_{0})+A(T_{0},T)+\frac{1}{2}B(T_{0},T)^{2}V a r\left(y+y\right)\right)\right]~,}}\end{array}
$$  

where A and B are piecewise functions  

$$
\begin{array}{l}{{\displaystyle{\cal B}(t,T)=\frac{1}{k_{n}}+\left({\cal B}(T_{n},T)-\frac{1}{k_{n}}\right)\exp\bigl(-k_{n}(T_{n}-t)\bigr)>0}}\ {{\displaystyle{\cal A}(t,T)={\cal A}(T_{n},T)+\sigma_{n}^{2}\left({\cal B}(T_{n},T)-\frac{1}{k_{n}}\right)^{2}\frac{1-\exp\bigl(-2k_{n}(T_{n}-t)\bigr)}{4k_{n}}+\frac{\sigma_{n}^{2}(T_{n}-t)}{2k_{n}^{2}}}}\ {{\displaystyle~+\frac{\sigma_{n}^{2}}{k_{n}}\biggl({\cal B}(T_{n},T)-\frac{1}{k_{n}}\biggr)\frac{1-\exp\bigl(-k_{n}(T_{n}-t)\bigr)}{k_{n}}}}\end{array}
$$  

and $\mathsf{v}(\mathsf{T}_{0})$ is normally distributed  

$$
y_{T_{0}}\sim N\left(y_{t}e x p\left(-\int_{t}^{T_{0}}\kappa(u)d u\right),e x p\left(-\int_{t}^{T_{0}}\kappa(u)d u\right)\int_{t}^{T_{0}}e x p\left(\int_{t}^{u}\kappa(v)d v\right)\sigma(u)^{2}d u\right)
$$  

If $\mathsf{T}_{0}{<}\mathsf{t}$ , we have  

$$
F_{R_{G}}={\frac{1}{T-T_{0}}}\left[e x p\left(\int_{T_{0}}^{t}r_{s}(u)d u\right)e x p\left(2\int_{t}^{T}\varphi(u)d u\right)P(t,T)-1\right]
$$  

where $\boldsymbol{\mathsf{r}}_{s}$ is the realized SOFR from. ${\sf T}_{0}$ through t and. $\mathsf{P}(\mathtt{t},\top)$ can be calculated from the SOFR curve.  

For 1M SOFR futures simple interest formula is used instead, which can be approximated by  

$$
R_{A}(T)=\left[\sum_{i=1}^{d_{b}}{\frac{r_{i}\times n_{i}}{N}}\right]\times{\frac{N}{d_{c}}}\times100\approx{\frac{1}{T-T_{0}}}\int_{T_{0}}^{T}r_{s}(u)d u\times100={\frac{1}{T-T_{0}}}l n{\frac{M(T)}{M(T_{0})}}\times100\times10^{-1}d u.
$$  

Its corresponding forward SOFR term rate  

$$
\L_{\lambda_{A}}(t)=E^{T}[R_{A}]={\frac{1}{P(t,T)}}E\left[{\frac{1}{T-T_{0}}}\left(\int_{T_{0}}^{T}r_{s}(u)d u\right)D(t,T)\right]={\frac{1}{T-T_{0}}}E^{T}\left[\left(\int_{T_{0}}^{T}r_{s}(u)d u\right)\right]
$$  

which can be calculated analytically.  

The 1M sOFR futures rate is martingale under the spot risk-neutral measure, and thus we have  

$$
\frac{1}{\cdot-T_{0}}E\left[\int_{T_{0}}^{T}r_{s}(u)d u\right|\mathcal{F}_{t}\right]=\frac{1}{T-T_{0}}\left(\int_{T_{0}}^{T}\varphi(u)d u+\frac{\exp\left(-k(T_{0}-t)\right)-\exp\left(-k(T-t)\right)}{k}x^{2}+4\frac{\sum_{s=0}^{T}\varphi^{2}(u)d u}{2k}x^{2}\right)+\frac{1}{4}x^{4}+4{\sqrt{3}}(2{\sqrt{3}}(u-t)^{2}+4{\sqrt{3}}(u-t)^{2})+\sum_{s=0}^{T}\varphi^{2}(u)d u.
$$  

where the expected short rate  

$$
E[r_{s}(u)|\mathcal{F}_{t}]=\varphi(t)+x(t)e x p\left(-\int_{t}^{u}k d t\right)
$$  

Unlike an SOFR-linked OlS swap, the floating leg of a fixed vs SOFR swap makes multiple payment as the floating leg of a LIBOR swap.  

In a SOFR fixed-floating swaps, the floating leg pays at time $\mathsf{T}_{\mathrm{j}}$  

$$
\delta_{j}R_{G}\bigl(T_{j}\bigr)=\prod_{i=1}^{d_{b,j}}\biggl(1+{\frac{r_{i}\times n_{i}}{360}}\biggr)-1={\frac{M\bigl(T_{j}\bigr)}{M\bigl(T_{j-1}\bigr)}}-1
$$  

where ${\mathsf{d}}_{\mathsf{b,j}}$ is the number of business days between $[\mathsf{T}_{\mathrm{j}-1},\mathsf{T}_{\mathrm{j}}]$ . It is essentially an SOFR linked OIS swap with multiple floating payments with reset in-arrears.  

Assuming compound average and no payment delay the PV of the floating leg at time t is then given by  

$$
\begin{array}{c}{P V_{F l o a t}(t)=\displaystyle\sum_{j=1}^{n}E\left[\left(\frac{M\big(T_{j}\big)}{M\big(T_{j-1}\big)}-1\right)D\big(t,T_{j}\big)\right]=\displaystyle\sum_{j=1}^{n}E\big[D\big(t,T_{j-1}\big)\big]-E\big[D\big(t,T_{j}\big)\big]}\ {=P(t,T_{0})-P(t,T_{n})}\end{array}
$$  

With payment delay, e.g. 2 business days, the convexity adjustment should be taken into account in theory. However, in practice the convexity adjustment is quite small and thus neglectable  

$$
P V_{F l o a t}(t)=\sum_{j=1}^{n}\delta_{j}f_{R_{G}}{\bigl(}T_{j}{\bigr)}P(t,T_{j,p})
$$  

where the forward SOFR term rate  

$$
f_{R_{G}}(T_{j})=\frac{1}{\delta_{j}}\left(\frac{P\left(t,T_{j-1}\right)}{P\left(t,T_{j}\right)}-1\right)
$$  

The fixed leg pays at time $\mathsf{T}_{\mathrm{j}}$ for unit notional.  

$$
(T_{i}-T_{i-1})S
$$  

and its PV of the ith fixed coupon  

$$
P V_{F i x e d}(t)=\sum_{i=1}^{m}E[(T_{i}-T_{i-1})S\cdot D(t,T_{i})]=\sum_{i=1}^{m}(T_{i}-T_{i-1})S\cdot P(t,T_{i})
$$  

Thus, the breakeven SOFR swap rate  

$$
S(t)=\frac{\sum_{j=1}^{n}\delta_{j}f_{R_{G}}\big(T_{j}\big)P(t,T_{j,p})}{\sum_{i=1}^{m}\delta_{i}P(t,T_{j})}
$$  

In certain circumstances we ignore the payment delay and the faire swap rate becomes  

$$
S(t)=\frac{P(t,T_{0})-P(t,T_{n})}{\sum_{i=1}^{m}\delta_{i}P(t,T_{j})}
$$  

Note that assuming the swap cash flows use compound interest and are discounted at SOFR itself, the valuation of sOFR fixed-floating swaps with compounded interest are exactly the same as a vanilla IR swap based on Libor.  

For simple interest, we have to assume an interest rate model and use the forward simple SOFR term rate $f_{R_{A}}(T_{j})$ in place of $f_{R_{G}}(T_{j})$  

# 4.3 SOFR Swaptions  

The underlying of a SOFR swaption is an SOFR fixed vs floating swap, which is similar to a LIBOR vanilla swap except for the index and resetting.  

Similar to a LIBOR swap, the values of a floating leg and a fixed leg are  

$$
P V_{F l o a t}(t)=\sum_{j=1}^{n}E\left[\left(\frac{M\left(T_{j}\right)}{M\left(T_{j-1}\right)}-1\right)D(t,T_{j})\right]=P(t,T_{0})-P(t,T_{n})
$$  

and  

$$
P V_{F i x e d}(t)=\sum_{k=1}^{m}E[(T_{i}-T_{i-1})S\cdot D(t,T_{i})]=S\sum_{i=1}^{m}(T_{i}-T_{i-1})\cdot P(t,T_{i})
$$  

Thus, ignoring the payment delay the SOFR swap rate is the same a LIBOR swap with a single curve  

$$
S(t)=\frac{P(t,T_{0})-P(t,T_{n})}{\sum_{i=1}^{m}\delta_{j}P(t,T_{i})}
$$  

which is martingale under the annuity measure, $\begin{array}{r}{A(t,T_{0},T_{m})=\sum_{i=1}^{m}\delta_{j}P(t,T_{i})}\end{array}$  

Thus, the PV of a SOFR swaption  

$$
V_{s w a p t i o n}(t)=E\left[(S-K)^{+}\sum_{i=1}^{m}\delta_{j}D(t,T_{i})\right]=A(t,T_{0},T_{m})E^{A}[(S(T_{0})-K)^{+}]
$$  

with $E^{A}[S(T_{0})]=S(t)$  

A Bermudan swaption has to be valued numerically on a lattice, e.g. trinomial tree. The fixed leg can be calculated easily by backward deduction. The floating leg can be calculated similar to a callable SOFR floater.  

With geometric averaging, the PV of a floating payment at the beginning of a payment period  

$$
P V_{F l o a t}\big(T_{i-1};x_{j}\big)=N\cdot(f_{R}+s)\cdot\delta_{i}\cdot P\big(T_{i-1},T_{i};x_{j}\big)
$$  

with  

$$
f_{R_{G}}=E^{T}[R_{G}]=\frac{1}{\delta_{i}}\left(\frac{1}{P\left(T_{i-1},T_{i};x_{j}\right)}-1\right)
$$  

which is the same as a LIBOR vanilla swap.  

With arithmetic averaging, the PV of a floating payment given a state variable x(T-1)  

$$
P V_{F l o a t}\big(T_{i-1};x_{j}\big)=N\cdot(f_{R}+s)\cdot\delta_{i}\cdot P\big(T_{i-1},T_{i};x_{j}\big)
$$  

with  

$$
=E^{T}[R_{A}]=\int_{T_{i-1}}^{T_{i}}\varphi(u)d u-\sigma^{2}\frac{2k\delta_{i}-3+4\exp(-k\delta_{i})-\exp(-2k\delta_{i})}{2k^{3}}+\frac{1-\exp(-k\delta_{i})}{k}
$$  

where $\mathsf{x}(\mathsf{T}_{\mathrm{i-1}})$ is given at each node.  

# 4.4 SOFR Caps/Floors  

SOFR cap/floor is similar to LIBOR cap/floor except that index rates are reset in arrears using either simple average rate or compounded average rate. Thus, different from LIBOR cap/floor the first floating payment is unknown at inception.  

The value of each caplet/floorlet is given by  

$$
V_{C a p l e t}(t)=E[(R.(T_{i})-K)^{+}\delta_{i}D(t,T_{i})]
$$  

where the average SOFR rate R at ${\mathsf{T}}_{\mathrm{i}}$ is given by.  

$$
R_{G}(T_{i})=\left[\frac{M(T_{i})}{M(T_{i-1})}-1\right]\times\frac{1}{T_{i}-T_{i-1}}
$$  

or  

$$
R_{A}(T_{i})\approx\frac{1}{T_{i}-T_{i-1}}l n\frac{M(T_{i})}{M(T_{i-1})}
$$  

with the relationship  

$$
\delta_{i}\cdot R_{G}(T_{i})=\left[\exp\left(\delta_{i}\cdot R_{A}(T_{i})\right)-1\right]
$$  

Assuming the short rate follows a mean-reverting process, ${\sf R}_{\sf A}({\sf T}_{\mathrm{i}})$ as the integral of a normal process is.   
normally distributed, and thus. ${\sf R}_{\sf G}({\sf T}_{\mathrm{i}})$ is lognormally distributed..  

In order to value SOFR cap/floor, we compute the mean and variance of both ${\sf R_{A}(T_{i})}$ and ${\sf R}_{\sf G}({\sf T}_{\mathrm{i}})$  

$$
E^{T_{i}}[\exp{(\delta_{i}\cdot R_{A}(T_{i}))}]=\frac{P(t,T_{i-1})}{P(t,T_{i})}
$$  

$$
E^{T_{i}}[\delta_{i}\cdot R_{A}(T_{i})]=\int_{T_{i-1}}^{T_{i}}\varphi(u)d u-\sigma^{2}{\frac{2k\delta_{i}-3+4\exp(-k\delta_{i})-\exp(-2k\delta_{i})}{2k^{3}}}+{\frac{1-\exp(-k\delta_{i})}{k}}E^{T_{i}}\left({\frac{\delta_{i}}{\delta_{i}}}\right)+{\frac{1}{\exp(-k\delta_{i})}}(2k\delta_{i}-3k\delta_{i})
$$  

$$
V a r^{T_{i}}[R_{A}(T_{i})\cdot\delta_{i}]=2l n(E^{T_{i}}[\exp{(\delta_{i}\cdot R_{A}(T_{i}))}])-2\delta_{i}\cdot E^{T_{i}}[R_{A}(T_{i})]
$$  

$$
{}^{T_{i}}[\exp{(R_{A}(T_{i})\cdot\delta_{i})}]=\exp{(2\delta_{i}\cdot E^{T_{i}}[R_{A}(T_{i})]+\delta_{i}^{2}V a r^{T_{i}}[R_{A}(T_{i})])}(\exp\bigl(\delta_{i}^{~2}V a r^{T_{i}}[R_{A}(T_{i})]\bigr)),
$$  

Then, Black-Scholes (Blank and Scholes, 1973) or Bachelier formula can be applied to value the caplet accordingly  

$$
V_{C a p l e t}(t)=E[(R_{G}(T_{i})-K)^{+}\delta_{i}D(t,T_{i})]=P(t,T_{i})E^{T_{i}}\left[\left(\exp\bigl(\delta_{i}\cdot R_{A}(T_{i})\bigr)-(1+\delta_{i}K)\right)+(1-\delta_{i})^{+}\delta_{i}T_{i}\right]
$$  

or  

$$
V_{C a p l e t}(t)=E[(R_{A}(T_{i})-K)^{+}\delta_{i}D(t,T_{i})]=\delta_{i}P(t,T_{i})E^{T_{i}}[(R_{A}(T_{i})-K)^{+}]
$$  

# 4.5 Options on SOFR Futures  

Options on SOFR futures are very similar to options on Eurodollar futures. There are American options on both 3M SOFR futures and 1M SOFR futures. Each option is exercisable into one specified underlying. instrument, i.e. CME SOFR futures contract.  

The SOFR futures price is a function of the corresponding SOFR futures rate  

$$
P r i c e=100-F_{R}
$$  

where at settlement the settlement SOFR rate  

$$
R_{G}(T)=\left[\prod_{i=1}^{d_{b}}\left(1+{\frac{r_{i}\times n_{i}}{360}}\right)-1\right]\times{\frac{360}{d_{c}}}\times100=\left[{\frac{M(T)}{M(T_{0})}}-1\right]\times{\frac{1}{T-T_{0}}}\times100
$$  

and  

$$
R_{A}(T)=\left[\sum_{i=1}^{d_{b}}{\frac{r_{i}\times n_{i}}{N}}\right]\times{\frac{N}{d_{c}}}\times100\approx{\frac{1}{T-T_{0}}}\int_{T_{0}}^{T}r_{s}(u)d u\times100={\frac{1}{T-T_{0}}}l n{\frac{M(T)}{M(T_{0})}}\times100\times10^{-1}d u.
$$  

for 3-month and 1-month, respectively.  

As derived earlier, a forward SOFR term rate is a martingale under the T-forward measure, while a futures SOFR term rate is martingale under the spot risk-neutral measure.  

Suppose the expiration time of a European SOFR call option is T. Its value is  

$$
V_{C a l l}(t)=E[(F_{R}(T)-K)^{+}D(t,T)]
$$  

where the SOFR futures rate R is martingale under the spot risk-neutral measure  

$$
F_{R}(\tau)=\frac{1}{T-T_{0}}E\left[e x p\left(\int_{T_{0}}^{T}r_{s}(u)d u\right)-1\right|\mathcal{F}_{\tau}\right]
$$  

for geometric averaging, or  

$$
F_{R}(\tau)=\frac{1}{T-T_{0}}E\left[\int_{T_{0}}^{T}r_{s}(u)d u\Biggr|\mathcal{F}_{\tau}\right]
$$  

for arithmetic averaging.  

Using a one-factor affine model, e.g. Hull-White model, we have for geometric averaging  

$$
F_{R}(\tau)=\frac{1}{T-T_{0}}E\left[e x p\left(\int_{T_{0}}^{T}r_{s}(u)d u\right)-1\right|\mathcal{F}_{\tau}\right]=\frac{1}{T-T_{0}}
$$  

$$
\begin{array}{r l}{\displaystyle}&{=\frac{1}{T-T_{0}}\bigg(e x p\left(\displaystyle\int_{T_{0}}^{T}\varphi(u)d u\right)E\big[\exp\bigl(A(T_{0},T)-B(T_{0},T)y_{T_{0}}\bigr)\big|\mathcal{F}_{t}\big]-1\bigg)}\ {\displaystyle}&{=\frac{P(t,T_{0})}{P(t,T)}\exp\left(A(t,T)-A(t,T_{0})+A(T_{0},T)-B(T_{0},T)E\big[y_{T_{0}}\big]+\frac{1}{2}B(T_{0},T)^{2}V a r(y_{T_{0}})\right)-}\ {\displaystyle}&{\qquadT-T_{0}}\end{array}
$$  

where the state variable $\mathsf{v}(\ t)=-\mathsf{x}(\ t)$ that is governed by.  

$$
d y_{t}=-\kappa y_{t}d t-\sigma(t)d W
$$  

and  

$$
E\big[y_{T_{0}}|\mathcal{F}_{\tau}\big]=y(\tau)\mathrm{exp}\left(-\int_{\tau}^{T_{0}}\kappa d u\right)
$$  

Because $\mathsf{v}(\tau)$ is normally distributed and $\mathsf{V a r}(\mathsf{V}\tau_{0})$ is deterministic, ${\sf F}_{\sf R}(\tau)$ will be a shifted lognormal process, and eventually the Black-Scholes formula can be applied to value a European option.  

In the case of arithmetic averaging, similarly we have  

$$
\begin{array}{l}{{F_{R}(\tau)=\displaystyle\frac{1}{T-T_{0}}E\left[\int_{T_{0}}^{T}r_{s}(u)d u\bigg|\mathcal{F}_{\tau}\right]=\displaystyle\frac{1}{T-T_{0}}\int_{T_{0}}^{T}E[r_{s}(u)|\mathcal{F}_{\tau}]d u}}\ {{\displaystyle=\frac{1}{T-T_{0}}\left(\int_{T_{0}}^{T}\varphi(u)d u+\frac{\exp\left(-k(T_{0}-\tau)\right)-\exp\left(-k(T-\tau)\right)}{k}x(\tau)\right)}}\end{array}
$$  

Because ${\mathbf{\boldsymbol{\times}}}(\tau)$ is normally distributed,. ${\sf F}_{\sf R}(\tau)$ will be a normal process and thus the Bachelier formula can be applied to value a European option on SOFR 1M futures.  

Usually, options on SOFR futures have American style, i.e. they can be exercised any time before settlement date, and therefore a trinomial tree can be built for the state variable x(t) and then early exercise can be modeled on the lattice.  

# 4.6 SOFR Callable Floaters  

A SOFR floating rate note (FRN) pays floating coupons linked to either geometric or arithmetic average of SOFR rate. In general, the present value of a one floating coupon is given by.  

$$
V_{i}(t)=N\cdot\delta_{i}E[(R.(T_{i})+s)D(t,T_{i})]=N\cdot\delta_{i}\cdot(f_{R.}(T_{i})+s)\cdot P(t,T_{i})
$$  

where ${\sf f}_{\sf R.}({\sf T}_{\mathrm{i}})$ is the average SOFR rate for the ith period and the spread can be treated as a fixed rate coupon.  

If a SOFR-linked structured note has an embedded option, the lattice method can be applied to evaluate the option similar to any other callable bonds. To that end, we build a trinomial tree according to the short rate model for SOFR term structure.  

On a lattice the discount factor and transition probability for the kth path at $t$ can be written as  

$$
D_{i,k}(t,T)=\prod_{l}D_{i,k}(T_{l-1},T_{l})
$$  

and  

$$
p_{i,k}=\prod_{l}p_{i,k,l}
$$  

which provides us a way to calculate the Arrow-Debru price recursively.  

For each node on the lattice, the present value of a fixed rate cash flow can be easily calculated as  

$$
P V_{F i x}=\delta_{i}c\cdot E\left[E\big[D(t,T)\big|x(T)=x_{j}\big]\right]=\delta_{i}c\cdot E\left[\sum_{k}D_{i,k}(t,T)p_{i,k}\right]
$$  

where $\mathsf{D}_{\mathrm{i,k}}(\mathsf{t},\mathsf{T})$ and $\uprho_{\mathrm{i,k}}$ represent the discount factor and transition probability, respectively, of the kth path that ends at the node $\mathsf{x}_{\mathrm{j}},$ and their product is actually the Arrow-Debru price.  

The calculation of a floating rate coupon is more complicated. Since the floating cash flows are pathdependent, and thus non-combining, its PV cannot be calculated by backward deduction. Instead, floating cash flows' PVs should be calculated at the beginning of each cash flow period either analytically. or numerically.  

As mentioned earlier, there are two types of interest rate based on SOFR rate, namely compound interest and simple interest. For compound interest, the coupon payment can actually be efficiently computed at the beginning of the coupon period Ti-1  

$$
\begin{array}{c}{{P V_{F l o a t}\big(T_{i-1};x_{j}\big)=E\left[\left(\displaystyle\frac{1}{D(T_{i-1},T_{i})}-1\right)D(T_{i-1},T_{i})+s\delta_{i}D(T_{i-1},T_{i})\right\vert x(T_{i-1})=x_{j}\right]}}\ {{=1+(s\delta_{i}-1)E\big[D(T_{i-1},T_{i})\big\vert x(T_{i-1})=x_{j}\big]}}\end{array}
$$  

where s denotes the spread over SOFR.  

Similarly, the PV of the floating payment based on simple average of SOFR at the beginning of the period is given by  

$$
P V_{F l o a t}\big(T_{i-1};x_{j}\big)=E\big[-l n D(T_{i-1},T_{i})\cdot D(T_{i-1},T_{i})\big|x(T_{i-1})=x_{j}\big]
$$  

If the Hull-White model is used to model the dynamics of the interest rate, i.e.  

$$
d x=-\kappa x d x+\sigma d W
$$  

and  

$$
r=\varphi(t)+x(t)
$$  

we have the present value of the payment at the beginning of the accrual period calculated analytically  

$$
\mathsf{O}(T_{i-1},T_{i})]=P(T_{i-1},T_{i})E^{T}[-l n D(T_{i-1},T_{i})]=P(T_{i-1},T_{i})\left(\int_{T_{i-1}}^{T_{i}}(\varphi(u)+E^{T}[x(u)])d u\right)
$$  

$$
=P(T_{i-1},T_{i})\left(\int_{T_{i-1}}^{T_{i}}\varphi(u)d u-\sigma^{2}{\frac{2k\delta-3+4\exp(-k\delta)-\exp(-2k\delta)}{2k^{3}}}+{\frac{1-\exp(-k\delta)}{k}}\right)\left(\int_{T_{i-1}}^{T_{i}}\varphi(u)d u-\sigma^{2}{\frac{2k\delta-3+4\exp(-k\delta)-\exp(-2k\delta)}{2k^{3}}}\right)\left(\int_{T_{i-1}}^{T_{i}}\varphi(u)d u\right).
$$  

and thus the expected average rate  

$$
^{T}[R_{A}]\cdot\delta=\int_{T_{i-1}}^{T_{i}}\varphi(u)d u-\sigma^{2}\frac{2k\delta-3+4\exp(-k\delta)-\exp(-2k\delta)}{2k^{3}}+\frac{1-\exp(-k\delta)}{k}x(T_{i-1})d u.
$$  

where $\mathsf{x}(\mathsf{T}_{\mathrm{i-1}})$ is given.  

If there is no analytic solution for each floating payment, approximations can be applied to simplify the calculation. Let $\begin{array}{r}{D(T_{i-1},T_{i})=e x p\left(\int_{T_{i-1}}^{T_{i}}-r(u)d u\right):=y}\end{array}$ Then, we have  

$$
P V_{F l o a t}\big(T_{i-1};x_{j}\big)=E\big[-l n y\cdot y\big|x(T_{i-1})=x_{j}\big]
$$  

which can be approximated by Taylor expansion around E[y]  

$$
E[R_{A}(T)\delta_{i}\cdot D(T_{i-1},T_{i})]\approx E\big[-\ln(E[y])\cdot E[y]\big]+(1-\ln(E[y]))(E[y^{2}]-E[y]^{2})
$$  

where both expectation  

$$
E[y]=E\left[e x p\left(\int_{T_{i-1}}^{T_{i}}-r(u)d u\right)\right]=P(T_{i-1},T_{i})
$$  

and  

$$
E[y^{2}]=E\left[e x p\left(-\int_{T_{i-1}}^{T_{i}}2r(u)d u\right)\right]
$$  

can also be computed on a recombining tree by backward deduction.  

# 4.7 SOFR CMS with cap/floor  

With a single curve the breakeven SOFR swap rate  

$$
S(t)=\frac{\sum_{j=1}^{n}\delta_{j}f_{R_{G}}\big(T_{j}\big)P(t,T_{j,p})}{\sum_{i=1}^{m}\delta_{i}P(t,T_{i})}
$$  

where the average SOFR rate  

$$
f_{R_{G}}(T_{j})=\frac{1}{\delta_{j}}\bigg(\frac{P\big(t,T_{j-1}\big)}{P(t,T_{i})}-1\bigg)
$$  

Ignoring the payment delay the faire swap rate becomes  

$$
S(t)=\frac{P(t,T_{0})-P(t,T_{n})}{\sum_{i=1}^{m}\delta_{i}P(t,T_{i})}
$$  

which is the same as the LIBOR swap rate.  

If the discount curve is different from the forecast curve, similarly we have the breakeven swap rate  

$$
S(t)=\frac{\sum_{j=1}^{n}\delta_{j}f_{R_{G}}\big(T_{j}\big)P_{d}\big(t,T_{j}\big)}{\sum_{i=1}^{m}\delta_{i}P_{d}(t,T_{i})}=\frac{\sum_{j=1}^{n}\delta_{j}(P_{f}\big(t,T_{j-1}\big)-P_{f}\big(t,T_{j}\big))\frac{P_{d}\big(t,T_{j,p}\big)}{P_{f}\big(t,T_{j}\big)}}{\sum_{i=1}^{m}\delta_{i}P_{d}(t,T_{i})}
$$  

where ZCB bond ratios are lognormally distributed under the ${\sf T}_{\sf p j}$ -forward measure.  

Both dual-curve and payment lag can be handled with the dual curve method, in which the sOFR swap rate conditional on the state variable Z  

$$
S(t;Z)=\frac{\sum_{k}\left(\frac{P_{f}\left(t,T_{k-1}\right)}{P_{f}\left(t,T_{p j}\right)}e^{-\frac{1}{2}\beta_{k-1}\left(T_{j}\right)^{2}-\beta_{k-1}\left(T_{j}\right)Z}-\frac{P_{f}\left(T_{j},T_{k}\right)}{P_{f}\left(t,T_{p j}\right)}e^{-\frac{1}{2}\beta_{k}\left(T_{j}\right)^{2}-\beta_{k}\left(T_{j}\right)Z}\right)\frac{P_{d}\left(t,T_{j}\right)}{P_{f}\left(t,T_{j}\right)}}{\sum_{i}\delta_{i}\frac{P_{f}\left(T_{j},T_{i}\right)}{P_{f}\left(t,T_{p j}\right)}e^{-\frac{1}{2}\beta_{i}\left(T_{j}\right)^{2}-\beta_{i}\left(T_{j}\right)Z}\frac{P_{d}\left(t,T_{i}\right)}{P_{f}\left(t,T_{i}\right)}}
$$  

where the state variable Z is normally distributed under the ${\sf T}_{\sf p j}$ -forward measure with volatility.  

$$
\beta(T)=\sqrt{\int_{0}^{T}\sigma_{F B}(t)^{2}d t}=\sqrt{\int_{0}^{T}(B\big(t,T_{j}\big)-B(t,T))^{2}\sigma(t)^{2}d t}
$$  

Given the distribution of the SOFR swap rate, the CMS rate and a CMS optionlet can be valued numerically  

$$
C M S(t)=E^{T_{p j}}[S(t;Z)]
$$  

and  

$$
P V_{o p t i o n l e t}(t)=P_{d}\big(t,T_{p}\big)E^{T_{p j}}[m a x(\omega(S(t;Z)-K),0)]
$$  

where the option type indicator $\omega=\pm1$  

# 5. Summary  

In 2017 the Secured Overnight Financing Rate (SOFR) was recommended as the replacement for USD LIBOR, and the transition from USD LIBOR to SOFR is set to complete by the end of 2021, after which the SOFR rate will become the primary benchmark floating rate used by most financial products. Since the. announcement SOFR-linked derivatives started to develop and their liquidities have also improved. Because of daily sOFR rate averaging, arithmetic average in particular, and timing mismatch pricing. SOFR derivatives is more complicated than pricing LIBOR derivatives, even if a vanilla IR swap. In order to address these challenges, we apply a mean-reverting Gaussian model, e.g. 1-factor Hull-White model,. to model the dynamics of the instantaneous SOFR rate and derive analytic formula for forward SOFR term rates as well as future SOFR term rates, which can then be used to price most linear SOFR products. Moreover, based on an affine interest rate model for the SOFR rate closed-form solutions are also derived for European SOFR options, including SOFR swaptions, SOFR cap/floor and options on SOFR futures. American options cannot be priced analytically, but efficient numerical methods are developed by combining lattice and analytic formula. Although a 1-facotor Hull-White model is used in this paper, it. is almost straightforward to extend it to multi-factor affine models..  

# References  

ARRC (2021) A User's Guide to SOFR.  

Black, Fischer and Myron Scholes (1973). The Pricing of Options and Corporate Liabilities. Journal of Political Economy. 81 (3): 637-654.  

Damiano Brigo and Fabio Mercurio (2001) Interest Rate Models - Theory and Practice with Smile, Inflation and Credit (2nd ed. 2006 ed.). Springer Verlag. ISBN 978-3-540-22149-4.  