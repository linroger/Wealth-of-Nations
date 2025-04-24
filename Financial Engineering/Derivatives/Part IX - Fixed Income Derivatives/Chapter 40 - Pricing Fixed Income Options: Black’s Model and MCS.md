---
tags:
  - black_model
  - european_options
  - fixed_income_options
  - interest_rate_derivatives
  - monte_carlo_simulation
aliases:
  - Black's Model
  - MCS
  - Pricing Fixed Income Options
key_concepts:
  - Black's model
  - Closed-form solutions
  - European options pricing
  - Fixed income derivatives
  - Monte Carlo simulation
---
# Pricing Fixed Income Options: Black’s Model and MCS  

# Aims  

• To show how Black’s model provides closed-form solutions for the price of European options on T-bonds, on T-bond futures, on caps, foors, collars and on European swaptions. • To price fxed income options using Monte Carlo simulation (MCS).  

In previous chapters we discussed hedging/insurance using options on T-bonds and Eurodollar futures and how caps, foors, collars, and swaptions are used to hedge/insure interest sensitive assets and liabilities such as foating rate bank deposits and loans. In this chapter we concentrate on how to price some of these derivatives. To price fxed income derivatives we can use:  

• Black’s model which gives closed form solutions • MCS under risk-neutral valuation (RNV) • BOPM model with an interest rate lattice (tree) • Equilibrium term structure approach.  

Black’s model assumes the price of the underlying asset in the options contract has a lognormal distribution, at maturity of the option. MCS generates a path for the short-rate and prices the derivative under RNV. The BOPM uses a lattice for the ‘short-rate’ of interest. The equilibrium yield curve approach assumes a specifc stochastic process for the interest rate and solves mathematically for the derivatives price – the BOPM and the equilibrium yield curve approach are dealt with in Chapters 41 and 49, respectively.  

# 40.1 BLACK’S MODEL: EUROPEAN OPTIONS  

Black’s (1976) model, which was originally used for pricing options on commodity futures can be adapted to give a closed-form solution for prices of European bond options, futures options, caps, foors, and European swaptions. The cash payout on an interest rate option may occur on the expiration date of the option, T. But note that for some options the payof $V_{T}$ is determined at $T$ , but the actual cash payout is delayed to $T^{*}>T$ . We adopt the following notation:  

$V_{T}=$ cash value (price) of the ‘underlying asset’ at $T$   
$F_{0}=$ forward price at $t=0$ of the underlying asset, for delivery at $T$ $T=$ time to maturity of the option   
$r=$ interest rate continuously compounded for maturity, $T$ $K=$ strike price   
$\sigma=$ volatility of the forward price.  

Black’s model does not assume a GBM for the underlying but requires somewhat weaker assumptions namely, that at expiration $\ln V_{T}$ is normally distributed with standard deviation of $\sigma\sqrt{T}$ and $E(V_{T})=F_{0}$ , the forward price. If the European (fxed-income) option has a payof, which is paid at $T$ , then Black’s formulas for the call and put premia are:  

$$
\begin{array}{l}{{C=e^{-r T}\ [F N(d_{1})-K N(d_{2})]}}\\ {{P=e^{-r T}[K N(-d_{2})-F_{0}N(-d_{1})]}}\\ {{d_{1}=\displaystyle\frac{\ln(F_{0}/K)+\sigma^{2}(T/2)}{\sigma\sqrt{T}},\qquadd_{2}=d_{1}-\sigma\sqrt{T}}}\end{array}
$$  

If the option payof is determined at $T$ , but the actual cash payment is delayed until $T^{*}$ then the above formulas for $d_{1},d_{2}$ still apply (i.e. using $T$ ) but the discount factor is $e^{-r^{*}T^{*}}$ (where $r^{*}$ is the interest rate for maturity $T^{*}$ ) .  

# 40.1.1 European Bond Option  

For a European option on a T-bond, the futures price of the bond is given by $F_{0,T}=[B_{0}-$ $P V(C)]e^{r T}$ where $P V(C)$ is the present value of the coupons on the T-bond, payable over the life of the option and $B_{0}$ is the current cash price of the bond. The volatility $\sigma$ used in Black’s model is for the forward bond price.  

# EXAMPLE 40.1  

# Price of European Bond Option  

Consider a 9-month European call option with strike $K=1{,}000$ , on a 10-year T-bond with maturity value $M=\$1,000$ and semi-annual coupons. The current cash market bond price $B_{0}=980$ and over the next 9 months the present value of the coupons (discounted at the appropriate spot yields) is 20.  

The 9-month spot yield is $r=5\%$ p.a. (continuously compounded) and the volatility of the forward bond price is $8\%$ p.a.  

$$
F_{0,T}=[B_{0}-P V(C)]e^{r T}=[980-20]e^{0.05(9/12)}=996.68
$$  

$$
C=e^{-r T}\ \left[F\ N(d_{1})-K N(d_{2})\right]=0.9632\left[996.68\left(0.4947\right)-1,000\left(0.4671\right)\right]=0.373\ \mathrm{{\Omega}}^{3}
$$  

# 40.1.2 Caps and Floors  

Consider a caplet on 90-day LIBOR on a notional principal $\$2$ with strike rate $K_{c a p}$ . The $t e n o r_{k}=90/360$ and the caplet matures in $t_{k}=2$ years. If the out-turn 90-day LIBOR rate at maturity of the cap is $L_{k}$ the payof at maturity is:  

$$
^{p}a y o f f l o n g c a p l e t\left(a t m a t u r i t y\right)=t e n o r_{k}Q\operatorname*{max}(L_{k}-K_{c a p},0)
$$  

The payof is calculated at $t_{k}$ but is paid at $t_{k+1}=t_{k}+t e n o r_{k}$ . Note that $r^{*}$ is continuously compounded, whereas $K$ and $f_{k}$ refer to simple annual rates. Assume $\ln L_{k}$ is normally distributed with standard deviation $\sigma_{k}\sqrt{t_{k}}$ then:  

# Invoice price of caplet that matures at $\mathfrak{t}_{k}$ :  

$$
V(t_{k})_{c a p l e t}=t e n o r_{k}Q e^{-r^{*}t_{k+1}}[f_{k}N(d_{1})-{K}_{c a p}N(d_{2})]
$$  

$$
d_{1}={\frac{\ln(f_{k}/K)+(\sigma_{k}^{2}/2)t_{k}}{\sigma_{k}{\sqrt{t_{k}}}}}~d_{2}=d_{1}-\sigma_{k}{\sqrt{t_{k}}}
$$  

$f_{k}=$ forward interest rate between $t_{k}$ and $t_{k+1}$ calculated $t=0$ $r^{*}=$ interest rate for maturity $t_{k+1}$ continuously compounded  

# EXAMPLE 40.2  

# Pricing a Caplet  

Suppose $Q=\$100,000$ , maturity $t_{k}=1$ -year, $t e n o r_{k}=90/360,f_{k}=3\%$ (90-day simple rate, 90/360 day-count convention).  

There is a fat term structure. Continuously compounded interest rates $r$ (at all maturities) are given by, $1+0.03(90/360)=e^{r(90/360)}$ , s $)r=(360/90)$ ln $(1+0.03/4)=0.0299$ , $K_{c a p}=3.5\%$ p.a. and $\sigma=20\%$ p.a. We have $d_{1}=-1.4915$ $d_{2}-1.5915$ . Using (40.4) the caplet price is:  

V tk caplet 90 360 10 000 $e^{-0.0299(1.25)}[0.03(0.0679)-0.035~(0.0557)]=2.0773$  

# 40.1.3 Caps  

Suppose we have a cap on a notional principal of $\$2$ with $n$ -reset dates, $t_{1},t_{2}\ldots t_{n}$ with the fnal payment at $T=t_{n+1}$ . The tenor is the time between the reset dates (measured in years), $t e n o r_{k}=t_{k+1}-t_{k}$ $(=90/360$ for example .  

To price a cap, each caplet must be valued separately (see Equation 40.4) but this requires diferent forward volatilities $\sigma_{k}^{2}$ for each caplet. However, in practice cap premia are often quoted using fat volatilities – that is, $\sigma_{k}^{2}$ is assumed to be constant for all horizons $k$ . The invoice price of a cap is the sum of the caplet premia that comprise the cap.  

$$
V_{c a p}=\sum_{k=1}^{n}V(t_{k})_{c a p l e t}
$$  

# 40.1.4 Floorlet and Floors  

The invoice price of a foorlet that matures at $t_{k}$ is:  

$$
V(t_{k})_{F L}=t e n o r_{k}Q~e^{-r^{*}t_{k+1}}~[~K_{F L}N(-d_{2})-f_{k}N(-d_{1})~]~
$$  

and the invoice price of a foor is the sum of the foorlet premia that make up the foor.  

# 40.2 PRICING A CAPLET USING MCS  

MCS can often provide a quick and conceptually easy method of valuing some fxed-income derivatives. For example, under RNV the price of a caplet is:  

$$
V_{t}=E^{*}[e^{-r_{a v}(T-t)}V_{T}]
$$  

For example, consider pricing a caplet (on 90-day LIBOR) with a strike price $K_{c a p}=10\%$ and $T=1$ year. To use MCS we need to generate a data series for the short-term LIBOR rate. Suppose we choose a discrete approximation to Vasicek’s mean reverting model:  

$$
r_{t}-r_{t-1}=a(b-r_{t-1})d t+\sigma\sqrt{d t}\varepsilon_{t}
$$  

where – niid(0,1). The (mean) long-run interest rate might be $b=3\%$ p.a. (0.03) and the rate of convergence, $a=0.20$ . We take $d t=T/n=0.01$ , so we divide 1 year into $n=100$ time units. Assume that the current short rate is $r_{0}=4\%$ p.a. (0.04) and the notional principal in the caplet is Q. MCS involves the following steps:  

• Generate $n=100$ observations on $\boldsymbol{r}_{t}$ and calculate its average value, $r_{a v}=\sum_{t=1}^{n}r_{t}/n$ • Calculate the payof of the caplet at expiration $\mathrm{\Omega}=\operatorname*{max}\{r_{100}-K_{c a p},0)$ • The price of caplet for the frst Monte Carlo run is $V^{(1)}=e^{-r_{a v}(T+90/360)}~\mathrm{max}\{r_{100}-K,0\}~$ • Repeat the above steps for $m=10{,}000$ runs of the MCS then:  

$$
I n\nu o i c e p r i c e o f c a p l e t=Q(1/m)\sum_{i=1}^{m}V^{(i)}
$$  

It is easy to see how this method can be applied to other interest rate derivatives discussed above. For example, the value of a cap using MCS is simply the sum of the MCS prices of the individual caplets (with diferent maturity dates and strikes).  

Option premia calculated using MCS are dependent on the specifc stochastic model chosen for the short rate. Hence estimation issues arise. But the option can be priced using MCSs with alternative stochastic processes for the interest rate – and the sensitivity of alternative MCS option premia to alternative stochastic processes can be assessed.  

# 40.3 EUROPEAN SWAPTION: BLACK’S MODEL  

A ‘pay-fxed, receive-foating’ swap is equivalent to being short a fxed rate bond and long a foating rate bond. A payer swaption is an option to enter into an interest rate swap at maturity of the option contract $T$ , to pay-fxed, receive-foating at an agreed swap rate $K_{s p}$ , on a notional principal $Q$ over the life of the swap. The underlying swap in the swaption contract begins at $T$ and matures at $T_{s p}=T+n$ years. (A receiver swaption is an option to enter into a swap contract to receive-fxed, pay-foating at an agreed swap rate $K_{s p}$ .) We use the following notation (Figure 40.1) and assume the swap rate at $T$ is lognormal:  

Ksp swap rate in the option contract simple rate, p.a. $T=$ expiration of swaption i.e. commencement of the swap  

![](7e932469d5df5527559f78ed367b87b9a5af6fbdcd20b6302e2d3d73d136a304.jpg)  

If $s p_{T}>K_{s p}$ at expiry, the payer swaption has positive cash flows every $m$ -periods of $(Q/m)\{s p_{T}-K_{s p}\}$ , until time $T+n$ .  

FIGURE 40.1 Payer swaption  

$n=$ maturity of underlying swap in the swaption contract $m=$ number of payments per year in the swap $(=1/t e n o r)$ $s p_{T}=$ cash market swap rate for an $n$ -year swap at $T$ simple rate, p.a. $Q=$ notional principal for the underlying swap in the swaption contract  

A payer swaption gives rise to $a$ series of cash fows at expiration:  

$$
Q(t e n o r)\operatorname*{max}(s p_{\mathit{T}}-K,0)
$$  

which accrue at $t_{1},t_{2},\ldots\ldots t_{n}$ years from today (where $t_{i}=T+i/m)$ – see Figure 40.1. The value today $t_{0}$ , of any one of these cash fows received at time $t_{i}$ is given by Black’s formula:  

$$
V\ (\mathrm{single\cash\flow})=Q(t e n o r)e^{-r_{i}t_{i}}[s p^{f}\ N(d_{1})-K N(d_{2})]
$$  

$$
d_{1}={\frac{\ln(s p^{f}/K)+\sigma^{2}(T/2)}{\sigma{\sqrt{T}}}}\ d_{2}=d_{1}-\sigma{\sqrt{T}}
$$  

$\boldsymbol{s p}^{f}=$ forward swap rate to begin $T$ for maturity $T_{s p}$ simple rate  

ri continuously compounded interest rate for maturity $t_{i}$  

At $t_{0}$ we know the forward swap rate, $s p^{f}$ . A payer swaption comprises a series of cash fows, hence its value (invoice price) today, at $t_{0}$ is:  

$$
\begin{array}{l l}{{}}&{{\displaystyle\S V_{s w p o}^{p a y e r}(t_{0})=Q(t e n o r)A N[s p^{f}~N(d_{1})-K_{s p}N(d_{2})]}}\\ {{}}&{{A N=\displaystyle\left[\sum_{i=1}^{m.n}e^{-r_{i}t_{i}}\right]}}\end{array}
$$  

$A N$ is the present value of an annuity of $\$1$ paid at $t_{i}$ over $(m.n)$ periods.  

# EXAMPLE 40.3  

# Pricing a European Payer Swaption  

Suppose $Q=\$100,000$ , swaption maturity $T=5$ years, with $s p^{f}=4.04\%$ p.a. (fat term structure, simple rate), $r^{*}=4\%$ (continuously compounded), $^1K_{s p}=4.2\%$ p.a. and $\sigma=20\%$ p.a. The underlying swap has maturity $n=3$ years and tenor $=180/360$ $m=2,$ .  

$$
\begin{array}{l}{{d_{1}=\displaystyle\frac{\ln(4.04/4.2)+(0.2)^{2}(5/2)}{0.2\sqrt{5}}=0.1369,\quad d_{2}=0.1369-0.2\sqrt{5}=-0.3103}}\\ {{4N=\displaystyle\left[\sum_{i=1}^{6}e^{-0.04t_{i}}\right]=4.5829\quad\mathrm{where~}t_{i}=5+i/2.}}\end{array}
$$  

$$
\begin{array}{l}{{\S V_{s w p o}^{p a y e r}(t_{0})=Q(t e n o r)A N[s p^{f}\ N(d_{1})-K_{s p}N(d_{2})]\qquad}}\\ {{\qquad=100,000(180/360)4.5829\left[0.0404(0.5544)-0.0402(0.3782)\right]=}}\end{array}
$$  

If we have a receiver swaption (i.e. receive-fxed, pay-foating) then the payof is $Q(t e n o r)\operatorname*{max}(K_{F L}-s p_{_T},0)$ and the invoice price of the put is:  

$$
\Phi V_{s w p o}^{r e c e i v e r}=Q(t e n o r)~A N~[~K_{s p}~N(-d_{2})-s p^{f}N(-d_{1})~]
$$  

# 40.3.1 Limitations of Black’s Formula  

Black’s model is widely used in practice because it provides a closed-form solution for European option premia on T-bonds (and T-bond futures), Eurocurrency futures and on swaps (i.e. swaptions). However, Black’s model has its limitations. First, it is inconsistent to assume that at expiration of the option, the bond price, the bond futures price, the short rate, and the swap rate are all lognormally distributed.  

Second, in reality a bond price or interest rates do not have a constant volatility over the life of the option but Black’s formula assumes a constant volatility. For example, the volatility of the price of a bond approaches zero as the bond nears its maturity date. However, if the T-bond or T-bond futures option has a maturity $T$ which is small relative to the ‘life’ of the underlying bond being delivered, then the constant volatility assumption may provide a reasonable approximation.  

Note that Black’s model only deals with European and not American or other ‘more exotic’ fxed income options. Some of the weaknesses of Black’s model can be dealt with by using MCS – for example, we can incorporate stochastic volatility – but as we shall see in Chapter 41, the BOPM is also useful in pricing fxed income securities.  

An Excel fle on the website prices a caplet using MCS. MATLAB programs to implement Black’s model for bond options, caps and foor and swaptions are also provided.  

# 40.4 SUMMARY  

• Black’s (1976) model can be adapted to give a closed-form solution for pricing certain fxed-income options as long as we assume that at expiration, either interest rates or bond prices or futures prices are distributed lognormally. The latter cannot be true for all three ‘prices’ but this is often ignored in practice because of the tractability of Black’s formula.   
• Black’s formula is used to price European options on T-bonds (and T-bond futures) as well as caps, foors, and swaptions.   
• Monte Carlo simulation provides a fexible approach to pricing many types of fxed income options, including (some) path-dependent options. Of course, the resulting option prices will only be accurate if the stochastic process assumed for interest rates is a reasonable representation of their future behaviour. The robustness of the calculated MCS option premia can be assessed using alternative stochastic processes for interest rates.  

# EXERCISES  

# Question 1  

Black’s model can be applied to European options on T-bonds, T-bond futures, caps, foors, and swaptions. What key assumptions are required to apply Black’s model?  

# Question 2  

When pricing a caplet using MCS why do we not assume that the interest rate follows a geometric Brownian motion (GBM)?  

# Question 3  

What are the key factors which determine the payof at maturity from a 3-year payer swaption with notional principal $Q$ , tenor of 90 days and a swap life of 2 years?  

# Question 4  

Use Black’s model to value a 6-month European put option on a 10-year bond with strike price $K=\$100$ . The current price of the 10-year bond is $P_{B}=\$103$ .  

Present value of coupons on the bond (paid during the life of the option), $P V(C)=\S4$ . The 1-year interest rate $r=3\%$ p.a. (continuously compounded). The bond’s (forward price) volatility is $5\%$ p.a.  

Show your calculations for $d_{1},d_{2},N(.)$ , etc.  

# Question 5  

Today, using Black’s model, on a $T=2$ -year option, the implied price volatility for an underlying bond which matures 10 years from today is $\sigma_{i m p}$ . Suppose this implied volatility $\sigma_{i m p}$ is used today to price a $T=9$ -year option (on the same 10-year bond). Would the option price for the $T=9$ -year option be too high or too low?  

# Question 6  

Use Black’s model to calculate the price of a 9-month cap, on 90-day LIBOR, with strike $K_{c}=$ $5\%$ (actual/360, day count) and principal $Q=\$100,000$ . The (interest-rate) volatility is $\sigma=10\%$ p.a. and the 90-day forward rate (beginning in 9 months) is $f_{k}=0.05$ (simple rate, actual/360).  

The yield curve is fat at $r_{s}=5\%$ p.a. (over 90 days, simple rate) so $(1+r_{s}/4)=e^{r(1/4)}$ hence $\ln(1+r_{s}/4)=r/4$ , which gives $r=4.969\%$ p.a. (continuously compounded). Show your calculations for $d_{1},d_{2},N(.)$ , etc.  

# Question 7  

The underlying asset in a ( $T=3$ -year) payer swaption with a strike of $K_{s p}=7.5\%$ p.a. is an $N=4$ -year swap, with annual payments (tenor $=1$ year) and principal $Q=\$100,000$ . The volatility of the 4-year (forward) swap rate, $\sigma=20\%$ p.a.  

The yield curve is currently fat at $r=8\%$ p.a. (continuous compounding). Forward rates at all maturities are $8\%$ p.a. (continuous compounding) which gives a forward swap rate (simple rate) of $s p^{f}=8.33\%$ p.a. $(=\exp(0.08)-1)$ . The volatility of the (4-year) forward swap rate, $\sigma=20\%$ p.a.  

Show your calculations for $d_{1},d_{2},N(.)$ , etc.  