---
cssclasses:
  - academia
title: Teaching Note 7 A Rundown On Continuous Time Models
tags:
  - brownian_motion
  - continuous_time_models
  - interest_rate_modeling
  - ito_formula
  - vasicek_model
aliases:
  - Continuous Time Models
  - Vasicek
  - Wiener Process
key_concepts:
  - AR(1) model
  - Annualized quantities
  - Brownian motion properties
  - Ito's formula derivation
  - Risk neutral pricing
  - Taylor rule approximation
---

[[An Overview of the Vasicek Short Rate Model|Vasicek Model]]

# Teaching Note 7 A Rundown On Continuous Time Models

[[Fixed Income Lecture Notes]]

 [[Introduction to Fixed Income Asset Pricing]]

 [[Lecture Note 2Interest Rate Risk Management And Factors]]

 [[Forward Rates and Term Structure]]

 [[Teaching Note 4 Interest Rate Derivatives]]

 [[Teaching Note 5 Risk Neutral Pricing]]

[Teaching Note 6 Mortgage Backed Securities](Teaching%20Note%206%20Mortgage%20Backed%20Securities.md)

[Teaching Note 7 A Rundown On Continuous Time Models](Teaching%20Note%207%20A%20Rundown%20On%20Continuous%20Time%20Models.md)

## THE VASICEK MODEL OF INTEREST RATES

- We now derive the main tools of continuous time models as a limit from the
discrete time model.
- Consider the AR(1) model for interest rates:
$$r_{t+1}=\alpha+\beta r_{t}+\epsilon_{t+1}$$
We can rewrite
$$r_{t+1}-r_{t}=\alpha-(1-\beta)r_{t}+\epsilon_{t+1}$$
- We had daily data,  so "1" is one day,  and all coefficients $\alpha$,  $\beta$ and $Var(\epsilon_{t+1})$ are daily quantities.
- In financial applications we consider "annualized" quantities. Let ∆t = 1/252 be the daily fraction out of the 252 business days. Then
$$r_{t+\Delta t}-r_{t}=\alpha-\gamma r_{t}\Delta t+\sigma\eta_{t+\Delta t}$$
- where $\gamma=(1-\beta)/\Delta t$ is an "annualized" regression coefficient,  $\sigma$ is the annualized volatility,  and therefore $$\eta_{t+\Delta t}\sim N(0,\Delta t)$$
- We can therefore equivalently write
$$r_{t+\Delta t}-r_{t}=\gamma\left(\frac{\alpha}{\gamma\Delta t}-r_{t}\right)\Delta t+\sigma\eta_{t+\Delta t}$$
- Note that $$\frac\alpha{\gamma\Delta t}=\overline{r}=\text{ central tendency of}$$
- Because $E[\eta_{t+\Delta t}]=0$,  we have $$E_t[r_{t+\Delta t}-r_t]=\gamma\left(\overline{r}-r_t\right)\Delta t$$
- Hence:
	- $\text{If } r_t>\overline{r}\Longrightarrow E_t[r_{t+\Delta t}-r_t]<0\Longrightarrow$ rates are expected to drop
	- $\text{If } r_t<\overline{r}\Longrightarrow E_t[r_{t+\Delta t}-r_t]>0\Longrightarrow$ rates are expected to rise
	- We take the limit until $\Delta t\to dt$,  an infinitesimal,  and we obtain
		- $r_{t+\Delta t}-r_t\to dr_t=$ change in interest rate over $dt$
		- $\eta_{t+\Delta t}\to dW_t\sim N(0,dt)=$ Brownian motion=shock to interest rates

## THE [[An Overview of the Vasicek Short Rate Model|Vasicek Model]] OF INTEREST RATES
- We can then rewrite
$$dr_{t}=\gamma\left(r-r_{t}\right)dt+\sigma dW_{t}$$

- This is the **[[An Overview of the Vasicek Short Rate Model|Vasicek Model]]** of interest rates.
- It is the continuous time version of the standard AR(1) process.
	- The term "$γ (r − r_t)$" is called **drift**;
	- The term "$σ$" is called **diffusion**.
- Next figure shows two simulations of the interest rate process for two different volatility levels σ.
 ![500](2f3e3ae3cda0e87b88194214c6bd507d.png)
## BROWNIAN MOTION (WIENER PROCESS)
- $W_t$ is called Brownian motion or Wiener process.
- The change over time in Brownian motion is denoted as $$dW_t = W_{t+dt} - W_t \sim N(0, dt)$$
- $W_{t}$ has the following properties
	- **Finite**
	- **Continuous**
	- Martingale Property
		- For $\tau > t$,  $E[W_{\tau}|W_t] = W_t$
	- Normality
		- For $\tau > t$,  $W_{\tau} - W_t \sim N(0, \tau)$
	 - Quadratic Variation
		- Consider the partition $[0,t_1,…,t_n]$ with $t_i = it/n$
		- $$\sum_{j=2}^n (W_{t_j} - W_{t_{j-1}})^2 \to t \quad \text{(a.s.)}$$
- Additional Properties
	- The last property essentially says that $dW_t^2 = dt$
	- $dt^2 = 0$
	- $dW_tdt = 0$

## TAYLOR RULE APPROXIMATION FOR SECURITY VALUATION
- Consider a security with value $P(r_t, t)$ at time $t$ where $r_t$ is the interest rate.
- Over a small time interval $\Delta t$,  the second order Taylor rule approximation has: $$P(r_{t+\Delta t}, t + \Delta t) \approx P(r_t, t) + \frac{\partial P}{\partial t} \Delta t + \frac{\partial P}{\partial r}(r_{t+\Delta t} - r_t) + \frac{1}{2} \frac{\partial^2 P}{\partial r^2}(r_{t+\Delta t} - r_t)^2$$
#### SUBSTITUTING CHANGE IN INTEREST RATES

$$P(r_{t+\Delta t}, t + \Delta t) - P(r_t, t) \approx \frac{\partial P}{\partial t} \Delta t + \frac{\partial P}{\partial r}[\gamma(r - r_t)\Delta t + \sigma \eta_{t+\Delta t}] + \frac{1}{2} \frac{\partial^2 P}{\partial r^2}[\gamma(r - r_t)\Delta t + \sigma \eta_{t+\Delta t}]^2$$

#### TAKING LIMITS
- As $\Delta t \to dt$,  consider the quadratic term: $$[\gamma(r - r_t)dt + \sigma^2 \eta_{t+dt}]^2 = \gamma^2(r - r_t)^2 dt^2 + \sigma^2 dt + 2\gamma(r - r_t)dt \sigma dW_t$$$$\gamma^2(r - r_t)^2 dt^2 + \sigma^2 dW_t^2 + 2\gamma(r - r_t)dt \sigma dW_t = \sigma^2 dt$$
## ITO'S FORMULA
- - The capital gain over the period $dt$ is $$dP_t=P\left(r_{t+dt},t+dt\right)-P\left(r_t,t\right).$$
- We obtain in the limit Ito's Formula $$dP_t=\left\{\frac{\partial P}{\partial t}+\frac{\partial P}{\partial r}\gamma(\overline{r}-r_t)+\frac{1}{2}\frac{\partial^2P}{\partial r^2}\sigma^2\right\}dt+\frac{\partial P}{\partial r}\sigma dW_t$$
### CAPITAL GAIN CALCULATION
- The expected capital gain over an infinitesimal period $dt$ is $$E[dP_t]=\left\{\frac{\partial P}{\partial t}+\frac{\partial P}{\partial r}\gamma(\overline{r}-r_t)+\frac12\frac{\partial^2P}{\partial r^2}\sigma^2\right\}dt$$
- There are three terms determining a bond expected return:
	1. The passage of time
	2. The expectation of future rate times the sensitivity of bond to rate changes
	3. A convexity effect due to a non-linear relation between the security and the interest rate.
- The volatility of bond return depends on the interest rate volatility $σ$ times the sensivity of bonds to interest rates.

## RISK NEUTRAL PRICING IN CONTINUOUS TIME
- Consider a generic model of interest rates
$$d r_{t}=m(r_{t},t)d t+s(r_{t},t)d W_{t}\qquad\qquad\tag{1}$$
- where $m(r, t)$ and $s(r, t)$ are functions of the interest rate r and time t. The choice of $m(r, t)$ and $s(r, t)$ give rise to different models [^1]
- Consider two fixed income securities that depend on the interest rate.
	1. $V (r, t)$ = e.g. option
	2. $Z(r, t)$ = zero-coupon bond.
- What is a no-arbitrage relation between $V (r, t)$ and $Z(r, t)$?
- As a matter of notation,  I often write $V$ instead of $V (r, t),$ and partial derivatives are often indicated as follows:
$$V_{t}=\frac{\partial V}{\partial t};\quad V_{r}=\frac{\partial V}{\partial r};\quad V_{r r}=\frac{\partial^{2}V}{\partial r^{2}}\tag{2}$$
## RISK NEUTRAL PRICING IN CONTINUOUS TIME
1. **Portfolio**: Set up a portfolio that is long one unit of the security $V (r, t)$ and $N$ units of the zero coupon bond $Z(r, t)$ with maturity $T$:
$$\Pi(r,t)=V(r,t)+N Z(r,t)\tag{3}$$
2. **Hedging**: Choose N to eliminate sensitivity to interest rates:
$$\frac{\partial\Pi(r,t)}{\partial r}=0\tag{4}$$
	- This condition translates into the equation $$\frac{\partial {V(r,t)}}{\partial r} +\ N{\partial Z(r,t)\over\partial r}=0\tag{5}$$
	- Solve for optimal hedge ratio $N$: $$\large\frac{\partial V(r,t)}{\partial r}+N\frac{\partial Z(r,t)}{\partial r}=0 \tag{5}$$ $$ N=-\frac{\partial V(r,t)/\partial r}{\partial Z(r,t)/\partial r}=-\frac{\text{Sensitivity of V to interest rates}}{\text{Sensitivity of $Z$ to interest rates}}\tag{6}$$
3. **No Arbitrage**: Apply Ito's formula to the portfolio $Π(r, t)$: $$d\Pi=\left\{\Pi_{t}+\Pi_{r}m(r,t)+\frac{1} {2}\Pi_{rr}s(r,t)^{2}\right\}dt+\Pi_{r}s(r,t)dW_{t}\tag{7}$$
	- We know from hedging that $\Pi_{r}=\partial\Pi/\partial r=0$,  which implies $$d\Pi=\left\{\Pi_{t}+\frac{1}{2}\Pi_{rr}s(r,t)^{2}\right\}dt\tag{8}$$
	- Interest rate risk $dW_{t}$ does not affect the portfolio $\Longrightarrow$ portfolio is riskless.
$$\text{No Arbitrage}\quad\Longrightarrow\quad d\Pi=r\Pi dt\tag{9}$$
4. **Reshuffle**: Substitute in (9) the expression for dΠ from (8): $$\Pi_{t}+\frac{1}{2}\Pi_{rr}s(r,t)^{2}=r\Pi$$
		+ Substitute: $\Pi=V+NZ$,  $\Pi_{t}=V_{t}+NZ_{t}$,  $\Pi_{rr}=V_{rr}+NZ_{rr}$,  to obtain $$V_{t}+\frac{1}{2}V_{rr}s(r,t)^{2}-rV=N\left[Z_{t}+\frac{1}{2}Z_{rr}s(r,t)^{2}-rZ\right]$$ * Substitute also $N$ from (6) to get $$ \frac{V_{t}+\frac{1}{2}V_{rr}s(r,t)^{2}-rV}{V_{r}}=\frac{Z_{t}+\frac{1}{2}Z_{rr}s(r,t)^{2}-rZ}{Z_{r}}\tag{10}$$
	- Note that the left-hand-side is identical to the right-hand side.
		- =⇒ All pairs of fixed income securities must satisfy (10)
	- Denote by "$−m^∗(r, t)$" the common ratio,  which we will estimate from data: $$V_{t}+\frac{1}{2}V_{rr}s(r,t)^{2}-rV=-m^{*}(r,t)\tag{11}$$
	- **Reorganize to obtain the Fundamental Pricing Equation:** $$V_{t}+V_{r}m^{*}(r,t)+\frac{1}{2}V_{rr}s(r,t)^{2}=rV\tag{12}$$
	- *All* fixed income security must satisfy this Partial Differential Equation (PDE) subject to the boundary condition
$$V(r,T)=g(r,T)= \text{Payoff of security at }T \tag{13}$$

5. **RISK-NEUTRAL PRICING**: HOW CAN WE SOLVE EQUATION (12)?
	- The *Feynman Kac formula* shows the solution of (12) is:
$$V(r,T)=E_{t}^{*}\left[e^{-\int_{t}^{T}r_{u}d u}g(r_{T},T)\right]\tag{14}$$
	- The notation E∗[.] means we compute the expectation using the Risk Neutral Process for interest rates:
$$d r=m^{*}(r,t)d t+s(r,t)d W_{t}^{*}\tag{15}$$
	 - where $dW^∗_t$ is another Brownian motion $dW^∗_t ∼ N(0, dt).$
	- and not the original process (1):
$$d r=m(r,t)d t+s(r,t)d W_{t}\tag{16}$$

## INTEREST RATE MODELS
- Choice of $m(r, t)$ and $s(r, t)$ =⇒ interest rate model.
- **Affine Models**: In the following four cases,  the value of a zero coupon bond. at t with maturity T is: $$Z(r,t;T)=e^{A(t,T)-B(t,T)r};\tag{17}$$
6. **Vasicek:**
	1. $m^{*}(r,t)=\eta^{*}-\gamma^{*}r$ **and** $s(r,t)=\sigma$**,  and $$B(t,T)=\frac{1}{\gamma^{*}}(1-e^{-\gamma^{*}(T-t)})\tag{18}$$$$A(t,T)=\frac{1}{(\gamma^{*})^{2}}\left(B(t,T)-(T-t)\right)\left(\eta^{*}\gamma^{*}-\frac{1}{2}\sigma^{2}\right)-\frac{\sigma^{2}B(t;T)^{2}}{4\gamma^{*}}\tag{19}$$
	- We often denote the risk-neutral central tendency as $$r^{*}=\frac{\eta^{*}}{\gamma^{*}}$$
$2. \textbf{ Cox,  Ingersol,  and Ross }(\mathbf{CIR}) {: }m^* (r, t) = \eta ^* - \gamma ^* r$ and $s(r,t)=\sqrt\alpha r;$
$$\begin{align*}
m^*(r, t) &= \eta^* - \gamma^* r \quad \text{and} \quad s(r, t) = \sqrt{\alpha r}; \\
B(t; T) &= \frac{2\left(e^{\psi_1 (T-t)} - 1\right)}{(\gamma^* + \psi_1) \left(e^{\psi_1 (T-t)} - 1\right) + 2\psi_1}; \tag{20} \\
A(t; T) &= 2\eta^* \log \left(\frac{2\psi_1 e^{(\psi_1+\gamma^*)\frac{T-t}{2}}}{\alpha \left((\gamma^* + \psi_1)(e^{\psi_1 (T-t)} - 1) + 2\psi_1\right)}\right); \tag{21}
\end{align*}$$
where
$$

\psi_1 = \sqrt{(\gamma^*)^2 + 2\alpha}.

$$
- The risk-neutral central tendency is often denoted by
$$

r^* = \frac{\eta^*}{\gamma^*}.

$$
 **3 . Ho and Lee: $m^*(r,t)=\eta^*(t)$ and $s(r,t)=\sigma;$**
$$\begin{aligned}&B(t,T)\:=\:T\:\boldsymbol{-}t\\&A(t,T)\:=\:-\int_t^T\eta^*(\tau)\:(T-\tau)\:d\tau+\frac16\sigma^2\left(T-t\right)^3\end{aligned}$$

**4. Hull and White: $m^{*}(r,t)=\eta^{*}(t)-\gamma^{*}r$ and $s(r,t)=\sigma$;**$$
\begin{aligned}
B(t,T)& =\frac1{\gamma^*}\left(1-e^{-\gamma^*(T-t)}\right)  \\
A(t,T)& =-\int_t^TB(\tau;T)\eta^*(\tau)d\tau   \\
&+\frac{\sigma^2}{2(\gamma^*)^2}\left(T-t+\frac{1-e^{-2\gamma^*(T-t)}}{2\gamma}-2B(t;T)\right)
\end{aligned}$$
## FITTING THE [[An Overview of the Vasicek Short Rate Model|Vasicek Model]] TO DATA
- Where do the *risk neutral parameters* of an interest rate model come from?
	- They are estimated by non-linear OLS in the same fashion as Nelson and Siegel.
- Given today's rate $r = r_0$, we can fit the discount function implied by e.g. the Vasicek model, $Z (0, r_0, T) = e^{A(0;T)−B(0;T)}×r_0$ in (17) to the current bond prices.
- To recap, remember that from quoted data, we have available n prices $P_i (0, T_i)$ for coupon bonds with maturities $T_{1}^*, …, T^*_n$, as well as their respective coupons $c_i, i = 1, …, n$
- We look for a discount function that generates prices that are "close" to these bonds as follows:
	1. For given set of parameters $(γ^∗, r^∗, σ)$ we can compute the functions $A (0; T)$ and $B (0; T)$ in (18) and (19) for any maturity T, and hence the discount function (17).
	2. Given the function (17) and the coupon $c_i$, we can compute n *theoretical* bond prices $\hat{P_i} (0, r_0; T_i)$ for the same maturities (notice that the bond prices depend on the current interest rate $r_0$ as well).
	3. We can finally find the parameters that minimize the distance between the actual prices and the theoretical ones as
$$\operatorname*{min}_{\gamma^{*},\bar{r}^{*},\sigma}J=\sum\limits_{i=1}^{n}\left(P^{i}\left(0,T_{i}\right)-\widehat{P}^{i}\left(0,r_{0};T_{i}\right)\right)^{2}\tag{22}$$
- I find $γ^∗ = 0.0702$, $r^∗ = 0.2322$, $σ = 0.0463$
- The next figures compare the results using the Vasicek model and the Nelson - Siegel model.
## BOND PRICES AND FITTED PRICES 09-JAN-2002
 ![500](1d033a2ec80ee977981970e290a5b1e5.png)
## ZERO-COUPON YIELD CURVES: 08-JAN-2002
 ![500](dfca352bd74a360e361a14c0d23e8d22.png)

- Next Figure reports the risk neutral stationary distribution that is implied by the above estimates.
## THE RISK NEUTRAL STATIONARY DISTRIBUTION OF INTEREST RATES
 ![500](4a981d284ce97c48d29ad3b39b318943.png)
- As can be seen, the risk neutral distribution results in a large area with negative
interest rates.

## THE MARKET PRICE OF RISK
- Consider the expected return from an investment in the security V .
- According to Ito's formula:
$$\frac{d V}{V}=\mu_{V}d t+\sigma_{V}d W$$
- where the diffusion σV is
$$\sigma_{V}=\frac{V_{r}}{V}s(r,t)\tag{23}$$
- and the expected return $\mu_{V}$ is
$$E\left[\frac{dV}{V}\right]=\mu_{V}dt=\frac{1}{V}\left\{V_{t}+V_{r}m(r,t)+\frac{1}{2}V_{rr}s^{2}(r,t)\right\}dt$$
- The two terms $(V_{t}+\frac{1}{2}V_{rr}s^{2}(r,t))$, also appear in the pricing PDE (12): $$V_{t}+\frac{1}{2}V_{rr}s^{2}(r,t)=rV-V_{r}m^{*}(r,t)$$ * Substitute, to obtain the expected return as $$E\left[\frac{dV}{V}\right]=\left\{r+\frac{V_{r}}{V}(m(r,t)-m^{*}(r,t))\right\}dt$$
* Using expression (23), we can rewrite this as $$E\frac{[\frac{dV}{V}]-r\,dt}{\sigma_{V}}=\frac{1}{s(r,t)}(m(r,t)-m^{*}(r,t))dt\tag{24}$$
* On the left is the **market price of interest rate risk**, or **Sharpe ratio** $$E\frac{[\frac{dV}{V}]-r\,dt}{\sigma_{V}}=\frac{\text{Risk Premium}}{\text{Volatility}}$$The right-hand-side of (24) shows that such ratio does not depend on V .
	- All fixed income securities have the same market price of risk
- We thus define the market price of risk as $$\lambda(r,t)=\frac{1}{s(r,t)}(m(r,t)-m^{*}(r,t))\tag{25}$$ * _Every_  fixed-income security $V$ we must have a risk premium given by $$E\left[\frac{dV}{V}\right]-rdt=\sigma_{V}\,\lambda(r,t)dt \tag{26}$$
* The risk premium of a fixed income security depends on 
	* Amount of risk $\sigma_{V}$
	* Market price of risk $\lambda(r,t)$
* Given an estimate of $\lambda(r,t)$, the risk-neutral drift $m^{*}(r,t)$ is $$m^{*}(r,t)=m(r,t)-\lambda(r,t)s(r,t)\tag{27}$$
- that is, it is equal to the original drift adjusted for the market price of risk. The risk-neutral process is a "risk-adjusted" process.

## ESTIMATING THE MARKET PRICE OF RISK
- In Vasicek model, the Market Price of Interest Rate Risk is
$$\lambda(r)=\frac{1}{\sigma}\ \left(\gamma\ \left(r-r\right)-\gamma^{*}\ \left(r^{*}-r\right)\right)\tag{28}$$
- Generically, we can write the market price of risk as:
$$\lambda(r)=\lambda_{0}+\lambda_{1}\times r$$
- where
$$\lambda_{0}\ =\ \frac{1}{\sigma}\times(\gamma^{\rm r}-\gamma^{*}\gamma^{*})\ ;\qquad\mbox{and}\quad\lambda_{1}=-\frac{1}{\sigma}\times(\gamma-\gamma^{*})\tag{29}$$
* Given estimates of true parameters and risk neutral parameters, we can estimate the market price of risk 

## UNDERSTANDING "RISK NEUTRAL" PARAMETERS
- We have the following two sets of parameters
	- From fitting bond prices
$$\gamma^{*}=0.0702;~~\bar{r}^{*}=0.2322;~~\sigma=0.0463$$
	- From running a regression of r_t+∆t onto $r_t$,
$$\gamma=0.3261;\;\;\;\bar{r}=0.0509;\;\;\;\;\sigma=0.0221.$$
- These results shows two main "problems":
	1. The risk-neutral long-term interest rate is very high; 
	2. The risk-neutral volatility of the interest rate is also high.
* A high "risk-neutral" $r^{*}$ is not necessarily a problem, as it may just imply a market price of risk: $$\lambda(r)=\lambda_{0}+\lambda_{1}r$$
- where $λ_0$ and $λ_1$ are in (29).
- Indeed, we find λ0 = 0.006437365 and λ1 = −5.52699784.
- Given the current interest rate r = 1.68%, the current market price of risk is
$$\lambda(r)=-0.086416199$$
	- It is small, but not unreasonable. (Note: What does $λ(r) < 0$ imply for the bond risk premium?)
- One important issue that the volatility σ *should* be the same under risk neutral and true parameters.
	- This can be seen by comparing (15) and (16): The two processes have different means but the same volatility.

## RESTRICTED VASICEK MODEL
- This suggests we should restrict the Vasicek model to have the volatility estimated from interest rates.
- By redoing the non-linear least square estimate on γ∗and r∗ while restricting σ =0.0221  yields
$$\gamma^{*}=0.4476,\bar{r}^{*}=0.0654,\sigma=0.0221\ \mathrm{(restricted)}$$
- Next figures show the implications for fitting:

## FITTED PRICES FOR VARIOUS MODELS
 ![500](0ed84c4821991abf0b18e9afe58582bb.png)

## ZERO -COUPON YIELD CURVES
 ![500](b2b4c238d3c3be7281a014181113e2a3.png)
## APPLICATION. RELATIVE VALUE TRADES ON THE YIELD CURVE
- Let today be February 17, 2004
-  We use the Vasicek model to implement the relative value trade.
- The first step to set up a relative value trade is to obtain the parameters $r^∗, γ^∗$ and $σ$ of the Vasicek model that best fit the term structure of interest rates.
- Because realistically the long/short strategy of the trade will involve repurchase agreements, the rate of interest to be used as the short-term rate should be the overnight repo rate. 

## THE OVERNIGHT REPO RATE: MAY 21, 1991 - FEBRUARY 17, 2004
 ![500](f8e9f66c31752e0a4d84d1211094c79c.png)
Data Source: Bloomberg

- The parameter $σ$ is given by the volatility of the short-term interest rate.
- The volatility of the overnight repo rate is substantial: σ = 3.17%.
- Instead, r∗ and γ∗ are estimated by using a nonlinear least square technique.
- In particular, let $c_i$ be the coupon rate of bond i, ni the number of coupon dates remaining, and $T^{i,j}, j = 1, …, n_{i}$  the coupon dates for bond i.
- The value of the bond according to the Vasicek model is then
$$P_{i}^{Vasicek}=\frac{c_{i}\times100}{2}\times\sum\limits_{j=1}^{n_{i}}Z(0,T_{i,j})+100\times Z(0,T_{i,n_{i}})\tag{30}$$
- We then minimize
$$J(\gamma^{*},\bar{r}^{*})=\sum\limits_{i=1}^{n}\left(P_{i}^{Data}-P_{i}^{Vasicek}\right)^{2}.\tag{31}$$
- The minimization procedure yields $r^∗ = 18.99$% and $γ^∗ = 0.0583$

## THE FIT OF THE VASICEK MODEL TO BOND PRICES
 ![500](26d24d68a74eb0ed0dc497285ae0a8a3.png)
## APPLICATION (CNTD.) DESIGN OF THE RELATIVE VALUE TRADE
- Panel C reports the pricing errors, that is, the difference between the prices in the data andthe model:
	- $$\text{Pricing Error of Treasury Security} i = P^{Data}_i− P^{Vasicek}_i$$
- Most securities are not priced correctly, and some of them display large differences.
	- For instance, the 10-year T-note appears grossly overpriced by the market, as its traded price is almost $1 higher than the Vasicek model's prediction.
- Indeed, Panel D shows the pricing errors in percentage of the traded prices $P^{Data}_i$, and the price of the 10-year note is almost 1% higher than the model's prediction.

## APPLICATION (CNTD.) DESIGN OF THE RELATIVE VALUE TRADE
- For simplicity, we focus on short term bonds. Panels C and D show that short-term bonds are also mispriced.
- For our exercise, we focus on the T-note maturing on T = 1.5, which is overpriced by about 57 basis points compared to the model.
- Our relative value trade then calls for the following strategy:
	- Sell high / Buy low =⇒ Sell 1.5-yr T-note / Buy Vasicek 1.5-yr note
- That is, we want to sell the overpriced 1.5-year note, and purchase the 1.5-year note implied by the Vasicek model.

- While performing the first part of the trade is simple, how do we purchase the 1.5-year note that is "implied by the Vasicek model"?
- This fair value is a mathematical formula, so we cannot purchase it per se.
- The key to the trade is to recall that we can purchase, however, the replicating portfolio that according to the Vasicek model exactly replicates the 1.5-year note.
- So, the proper strategy is
	- Sell 1.5-yr T-note / Buy portfolio that *replicates* the Vasicek 1.5-yr note (33)
- The key insight of no arbitrage and relative value trading is that such a (replicating) portfolio costs exactly the Vasicek value of the 1.5-year note.

- To set up the replicating portfolio we need to find a security that is fairly priced according to the model, and we therefore use the 7.5-year T-note, which has a pricing error of only 3 basis points.
- When we derived the no arbitrage condition, we considered the following portfolio, now specializedfor the securities at hand:
$$\Pi(r_{t},t)=-P_{1.5-y r}^{Vasicek}(r_{t},t)+N_{t}\times P_{7.5-y r}^{Vasicek}(r_{t},t)\text{34}$$
- where $P^{Vasicek}_{1.5−yr} (r_t, t$) and $P^{Vasicek}_{7.5−y}r (r_t, t)$ denote the 1.5-year and the 7.5-year coupon notes, at t, respectively.
- The hedging strategy calls for selecting Nt in order to make the portfolio insensitive to changes in the interest rate. That is
$$\frac{\partial\Pi}{\partial r}=0\Longrightarrow N_{t}=\frac{\partial P_{1.5-y r}^{Vasicek}(r,t)/\partial r}{\partial P_{7.5-y r}^{Vasicek}(r,t)/\partial r}\tag{35}$$
- According to the model, no arbitrage then implies that $$d\Pi=r\Pi dt \tag{36}$$
- that is, $Π$ behaves as the return from a safe investment.
* To figure out the replicating portfolio, we must invert (34), and rewrite $$P_{1.5-yr}^{Vasicek}(r_{t},t)=N_{t}\times P_{7.5-yr}^{Vasicek}(r_{t},t)-\Pi(r_{t},t) \tag{37}$$
- According to the model, we can replicate the Vasicek 1.5-year note by using a position in the 7.5-year note, and by borrowing Πt at the risk free rate $r_t$.
- Since Πt is a borrowed cash position, let us denote it by $C_t$ and let us substitute it into the right-hand side of (37).
- With no arbitrage, the replicating portfolio is then given by
$$P_{1,5-yr}^{Vasicek}(r_{t},t)=N_{t}\times P_{7,5-yr}^{Vasicek}(r_{t},t)-C_{t}\tag{38}$$
- Recall that $C_t$ is the amount borrowed for the replication strategy.
	- If $C_t$ < 0, then we are net lenders in our position.
- Once we know $C_t$ and $Nt$, we follow a rebalancing strategy in which we keep our position $Nt$ in the 7.5-year T-note, and borrow or lend cash $C_t$ at the rate $r_t$, so that indeed $dC = rCdt$
* The initial amount borrowed $C_{0}$ must be given by the theoretical portfolio value at time $0$: $$C_{0}=-P_{1,5-up}^{V\,o\,sick}(r_{0})+N_{0}\times P_{7,5-up}^{V\,o\,sick}(r_{0}) \tag{39}$$
* Vasicek model tells us the position in each bond to take, as $$\frac{\partial P_{c}(r)}{\partial r}=\frac{c\times100}{2}\sum\limits_{i=1}^{n}\frac{\partial Z(r;T_{i})}{\partial r}+100\times\frac{\partial Z(r;T_{n})}{\partial r}$$$$=-\frac{c\times100}{2}\sum\limits_{i=1}^{n}B(0;T_{i})Z(r;T_{i})-100\times B(0;T_{n})Z(r;T_{n})$$
- where recall $$B(0, T_i) =\left(1\,-\,e^{-\gamma^{*}\times T_{i}}\right)\,/\gamma^{*}. $$
- We then get
$$N_{0}=\frac{\partial P_{1.5-yr}(r)/\partial r}{\partial P_{7.5-yr}(r)/\partial r}=\frac{1.4912}{5.6854}=0.2623\tag{40}$$
	- =⇒ for each 1.5-year note sold, we must purchase 0.2623 of the 7.5-year note.
- Given $N_0$, we can compute the value of $C_{0}$
$$C_{0}=-106.9791+0.2623\times108.7344=-78.4581$$
- To conclude, the replicating portfolio is then
$$P_{0}\;=\;N_{0}\times P_{7.5-y r}(0)-C_{0}=0.2623\times108.7344+78.4581=\;106.9791=P_{1.5-y r}^{Vasicek}(r_{0})$$
- By selling $P^{data}_{1.5−y}r = 107.5469$ and buying the replicating portfolio, which costs
106.9791, the initial lock in profit is
$$\mathrm{Initial~profit}=\$107.5469-\$106.9791=\$0.5678$$

## APPLICATION (CNTD.) THE DYNAMIC TRADE
- The dynamic trade recall implies the following steps
7. For each new $r_t$, recompute the optimal hedge ratio Nt using Equation 35.
8. Compute the new cash requirement =$(N_t − N{t−dt}) × P^{data}_{7.5−yr(t).}$
9. Adjust the amount of cash borrowed
$$C_{t}=C_{t-d t}+C_{t-d t}\times r_{t-dt}\times d t+\text{Cash~needed}$$
10. At every coupon period $T_i$, borrow more to pay the coupons due in the short position, and use the coupons received to decrease the amount borrowed.
$$C_{T_{i}}\ =\ C_{T_{i}-dt}+C_{T_{i}-dt}\times r_{T_{i}-dt}\times dt+\ \text{Cash needed}\ +\left(100\times\frac{c^{1.5-yr}}{2}\right)-N_{T_{i}-dt}\left(\frac{100\times c^{7.5-yr}}{2}\right)$$

## APPLICATION (CNTD.). THE REPLICATING PORTFOLIO: SIMULATIONS  
 ![500](82a954736729d52bfa0818cafee290c6.png)

## THE REPLICATING PORTFOLIO: DATA
 ![500](5ba49b84d8188b9078a460a0ea4aeef7.png)

- Panel B shows the observed 1.5-year note and its Vasicek value. Note:
	1. The twovalues are close to each other, and they both converge to their final payout of 100+ 6.50/2=103.25.
	2. The volatility of the Vasicek price is not nearly as large as the one of the actual tradedprice, especially during the initial period.
- This low volatility is indeed one of the shortcomings of the Vasicek model.
- Panel C shows the observed 7.5-year note and its Vasicek value. Note:
	- The true price and the model price move much less in sync, if at all.
- Panel D shows that, surprisingly, on this occasion the replicating strategy actually worked relatively well, especially when compared with the performance of the Vasicek model in Panel C.
	- In fact, the dotted line in Panel D represents the traded 1.5-year bond, while the solid line represents the value of the replicating portfolio, which only uses traded assets and the true repo rate for its implementation.

## APPLICATION (CNTD.). THE REPLICATING PORTFOLIO: DATA
- We finally obtain $$\text{Final replication error }= P_T − P^{data}_{1.5−yr} = \$103.4695 − \$103.25 = \$0.2195$$ - The total profit for this trade is then the sum of the profit at time 0, $0.5678, plus the interest accrued on this profit over 1.5 years, plus the replication error: $$\text{Total Profit }= \$0.5678/Z(0, 1.5) + \$0.2195 = \$0.5790 + \$0.2195 = \$0.7985$$
- where $Z(0, 1.5) = 0.9792$is the 1.5-year discount factor on February 17, 2004, obtained from a bootstrap procedure

## PRICING BY MONTE CARLO SIMULATIONS
- We now exploit Feynman Kac formula to evaluate fixed income securities using Monte Carlo simulations.
* Recall the value of any fixed income security can be computed as $$V(r,T)=E_{t}^{*}\left[e^{-\bar{l}^{T}r_{u}du}g(r_{T},T)\right]\tag{41}$$
* under the risk neutral process $$dr=m^{*}(r,t)dt+s(r,t)dW_{t}^{*}\tag{42}$$
* The idea is to approximate $V(r,T)$ by its simulated value $$\bar{V}(r,T)=\frac{1}{J}\sum_{s=1}^{J}e^{-\bar{l}^{T}r_{u}^{s}du}g(r_{T}^{s},T)\to E_{t}^{*}\left[e^{-\bar{l}^{T}r_{u}du}g(r_{T},T)\right]\tag{43}$$
## SIMULATION PROCEDURE
- Discretize first the time interval \[0, T] in $N = T/∆t$ intervals of size $∆t$.
- Let the initial condition be the current interest rate $r_0$. We approximate : 
- $$\begin{aligned}dr&\approx r_{t+\Delta t}-r_t\\dt&\approx\Delta t\\dW^*&\approx\varepsilon_{t+\Delta t}\thicksim\mathcal{N}\left(0,\Delta t\right)\end{aligned}$$
	* to obtain the recursion (Euler discretization) $$r_{t+\Delta t}=r_{t}+m^{*}\left(r_{t},t\right)\Delta t+s\left(r_{t},t\right)\ \varepsilon_{t+\Delta t}$$
* **Important:** Note that $\varepsilon_{t+\Delta t}$ has variance $\Delta t$, and not variance $1$. It can be obtained from a Standard Normal $x_{t+\Delta t}\sim\mathcal{N}(0,1)$ from $$\varepsilon_{t+\Delta t}=\sqrt{\Delta t}\times x_{t+\Delta t}\sim\mathcal{N}\left(0,\Delta t\right)$$

## SIMULATING CIR MODEL
- Consider the CIR model with $m^∗ (r, t) = γ^∗(r^∗ − r)$ and $s (r, t) = √αr$
* Starting from $r_{0}$, we have $$\begin{aligned}r_1&=r_0+\gamma^*\left(\overline{r}^*-r_0\right)\Delta t+\sqrt{\alpha r_0}\times\varepsilon_1\\r_2&=r_1+\gamma^*\left(\overline{r}^*-r_1\right)\Delta t+\sqrt{\alpha r_1}\times\varepsilon_2\\r_i&=r_{i-1}+\gamma^*\left(\overline{r}^*-r_{i-1}\right)\Delta t+\sqrt{\alpha r_{i-1}}\times\varepsilon_i\\&\vdots\vdots\\r_N&=r_{N-1}+\gamma^*\left(\overline{r}-r_{N-1}\right)\Delta t+\sqrt{\alpha r_{N-1}}\times\varepsilon_N\end{aligned}$$
- We then obtain a run of simulated interest rates.
- Next figure plots one simulated path for interest rates, under the CIR model and the parameter values of CIR.
 ![500](f70dcdb54e9b08c35806f6d312acd09f.png)
## CIR ZERO COUPON BONDS BY SIMULATIONS
- Example: suppose we want to simulate the price of a zero coupon bond.
- Since $g\left(r_{T}\right)=1$, the pricing formula (41) tells us:

$$V\left(r,t\right)\ =\ E^{*}\left[e^{-\int_{t}^{T}r(u)du}\times1\right]=E^{*}\left[e^{-\sum_{i=0}^{N-1}r_{i}\Delta t}\right]$$
- The Monte Carlo simulation approach is:
- (a) Repeat the simulation of interest rates J times, say J = 1, 000;
- (b) Obtain J paths of interest rates $r^{j}_0, r^{j}_1, …, r^{j}_{N−1}$ and hence J values of the bond (one for each interest rate path)
$$Z^{\mathrm{Run}\ j}=e^{-\sum_{i=0}^{N-1}r_{i}^{j}\times\Delta}\times\$1$$
- (c) Compute the value of the zero-coupon bond as the sample average
$$\widetilde{Z}\left(r,t\right)\;\approx\;E^{*}\left[e^{-\;\Sigma_{i=0}^{N-1}\,r_{i}\Delta}\right]=\frac{1}{J}\sum\limits_{j=1}^{J}\;Z^{\mathsf{Run}\;j}$$
- Given the discount function $\hat{Z} (T)$ for every T, we can compute the value of coupon-bonds.
- Next figure plots the theoretical CIR prices along with the simulated ones for differentJ.
* The risk neutral parameters computed from non-linear least squares are $$\gamma^{*}=0.3807;\quad\tau^{*}=0.072;\quad\alpha=0.0548.$$

 ![500](97f4594d274677368a71f8b83778b306.png)
- Clearly, the good fit of simulated prices with exact prices is due to the high value of γ (mean reversion) and low value of α (volatility) used in the CIR model.

- As it can be seen, under Vasicekmodel, which has a high volatility σ, long-term bonds results difficult to approximate well by Monte Carlo simulations, even with 10000 runs.
 ![500](0b9ac213c668b778688cc51697078594.png)
# STANDARD ERRORS
To assess how big the simulation error is, we can compute the standard errors. Given the $J$ prices $P_j$, where $j = 1, \ldots, J$, their standard deviations and the average simulated price are defined below.
## STANDARD DEVIATION OF PRICES
The standard deviation of the prices is given by:
$$\sigma_P = \sqrt{\frac{1}{J-1} \sum_{j=1}^J (P_j - \overline{P})^2}$$
where $\overline{P}$ is the actual average simulated price:
$$\overline{P} = \frac{1}{J} \sum_{j=1}^J P_j$$
## STANDARD ERROR
Then, the standard error is calculated as:
$$\text{Standard Error} = se_p= \frac{\sigma_P}{\sqrt{J}}$$
- That is, we can say that with 95% confidence, the true price lies in the confidence interval
- For example, in the Vasicek model, we had
 ![500](ad38beac8251344130e5f8f9a75e7b45.png)

- The price is closer to the true one as (1) we increase the number of simulations; (2) we decrease the horizon.
- The standard errors decrease with the number of simulations.

## APPLICATION: PRICING CONVERTIBLE BONDS
- Convertible securities, or "converts," are instruments that allow an investor to convert a fixed rate income investment into pre-specified amounts of the issuing firm's common stock.
- Typical structures are rather complex, but here we consider a simple case to appreciate how the MC simulation method can be effectively used in this case as well.
	- *Caveat:* Convertibles have a number of "American" options embedded in them.
	- Typically, MC simulations are not suited to deal well with American options, and trees are preferable.
	- However, recently, new methodologies have been discovered to price American options with MC simulations.
- Consider the following structured product
	- **Issuer's rating**: AAA rated (for simplicity, forget about default risk here)
	- **Maturity**: 5 years; 
	-  **Coupon:** 0 (a zero coupon bond);
	- *Notional:** 100;
	- **Conversion Option:** Call option to convert the bond into stock.
		- **Type**: European
		- **Maturity**: 3 year
		- **Conversion ratio**: 1 (one bond for one share)
- How do we go about pricing something like this?
	- The convertible bond is a straight (zero coupon) bond + option (to convert):
$$P_{C o n v e r t}=Z\left(0,r_{0};5\right)+\mathrm{Option}$$
	- We need to compute the option, and we are done.
- Let $S_t$ be the price of common stock at time $t$. Assume $S_0 = 70$.
- Payoff of the conversion option at time $T = 3$
$$\operatorname*{max}\left(S_{T}-Z\left(T,r_{T};T+2\right)\right)$$
- What is the difference from standard option?
	- The strike price depend on the interest rate!
		- =⇒ We cannot apply e.g. Black and Scholes formula.
- Assume stock:
	- Pays no dividends; 
	- Expected return is constant = µ =15%
	- Volatility is constant = σS = 30%
	- It is uncorrelated with interest rates. 
	- Process for stock is the Black Scholes lognormal process $$d S_{t}=\mu S_{t}d t+\sigma_{S}S_{t}d X_{2,t}$$ * The risk-neutral pricing formula is $$P_{\mathit{Option}}=E^{*}\left[e^{-\int_{0}^{T}rdt}\max\left(S_{T}-Z\left(T,r_{T};T+2\right)\right)\right]$$ - where $E^{*}\left[.\right]$ denotes the expectation under the risk neutral dynamics.

- What is the risk neutral process for stocks?
$$dS_{t}=r_{t}S_{t}dt+\sigma_{S}S_{t}dX_{2,t}$$
- The risk neutral process for the risk-free rate is
$$dr_{t}=\gamma^{*}\left(\overline{r}^{*}-r_{t}\right)dt+\sigma dX_{1,t}$$

- So, we simulate simultaneously: $$r_{t+\Delta}=r_{t}+\gamma^{*}\left(\overline{r}^{*}-r_{t}\right)\Delta+\sigma\sqrt{\Delta}x_{1,t+\Delta}$$$$S_{t+\Delta}=S_{t}+r_{t}S_{t}\Delta+S_{t}\sigma_{S}\sqrt{\Delta}x_{2,t+\Delta}$$
- where $x_{1,t+∆} ∼ N (0, 1)$ and $x_{2,t+∆ ∼ N (0, 1)}$
- Notice that the interest rate enters the drift rate of the stock price!
- For each simulation run j:
	- The cash flows are zero up to time T.
	- At time T, given $r^{j}_T$, we can use the Vasicek formula to find
$$Z\left(r_{T}^{j},T;T+2\right)=e^{A(T;T+2)-B(T;T+2)\times r_{T}^{j}}$$
- where
$$B\left(t;T\right)\;=\;\frac{1}{\gamma^{*}}\left(1-e^{-\gamma^{*}\left(T-t\right)}\right)$$
- and
$$A(t;T)\;=\;(B(t;T)-(T-t))\left(\overline{{{r}}}^{*}-\frac{1}{2(\gamma^{*})^{2}}\sigma^{2}\right)-\frac{\sigma^{2}B(t;T)^{2}}{4\gamma^{*}}$$
- Thus, the Cash Flow at time T from the option is
$$C F_{T}^{j}=\operatorname*{max}\left(S_{T}^{j}-Z\left(T,r_{T}^{j};T+2\right)\right)$$
- Discount it to today, using the interest rates of this simulation
$$P_{O p t i o n}^{j}=e^{-\,\Sigma_{i=0}^{N-1}\,r_{i}^{j}\times\Delta t}C F_{T}^{j}$$
- The value of the option is
$$P_{O p t i o n}=\frac{1}{J}\sum\limits_{j=1}^{J}P_{O p t i o n}^{j}$$
- In this case, we obtain
	-  $Z (0, r_0; 5) = 79.8713$ (from Vasicek Formula)
	- $P_{Option} = 10.0721$ (from Simulations)
	- $P_{Convert}= 89.9434$

[^1]: Some restrictions on m(r_t, t) and s(rt, t) are usually imposed to ensure that the process in Equation (1) is well defined. See e.g. Duffie (2001) for discussion and details.