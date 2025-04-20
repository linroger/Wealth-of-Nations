---
tags:
  - black_scholes
  - dividend_stocks
  - european_options
  - foreign_currency
  - futures_options
aliases:
  - European Option Pricing
  - Pricing Options
key_concepts:
  - Black-Scholes formula
  - Dividend paying stocks
  - Foreign currency options
  - Futures options pricing
  - Put-call parity
---
# Pricing European Options  

# Aims  

• To adapt the standard Black–Scholes formula to price European options on stocks that pay dividends. • To price European foreign currency options and futures options. • To demonstrate the links between pricing formulas for European options on dividend paying stocks, foreign currency options and options on futures contracts. • To examine the links between the put–call parity relationship for European options on dividend paying stocks, on foreign currency and on futures contracts.  

The standard Black–Scholes formulas for call and put options on a non-dividend paying stock are:  

$$
\begin{array}{l l l l l}{{C}}&{{=}}&{{S N(d_{1})-K e^{-r T}N(d_{2})\quad}}&{{\mathrm{and}}}&{{}}&{{P=K e^{-r T}N(-d_{2})-S N(-d_{1})}}\\ {{\nonumber}}&{{=}}&{{\frac{\ln(S/K)+(r+\sigma^{2}/2)T}{\sigma\sqrt{T}}}}&{{\mathrm{and}}}&{{}}&{{d_{2}=d_{1}-\sigma\sqrt{T}}}\end{array}
$$  

# 25.1 WHAT DO $N({\mathsf{d}}_{1})$ ) AND $N({\mathsf{d}}_{2})$ REPRESENT?  

Even without detailed proofs, we can get some insight into the interpretation of these two concepts. The term $N(d_{2})$ is the probability that the call option will be exercised (i.e. $S_{T}>K)$ in a risk-neutral world. If the call option is exercised then the holder of the call pays $K_{:}$ , so the expected cash outfow at $T$ is $K N(d_{2})$ , with expected present value $e^{-r T}K N(d_{2})$ . The delta of the call is equal to $N(d_{1})$ . In the delta-hedged portfolio you hold $N(d_{1})$ stocks and their current value (conditional on the call being exercised) is $S N(d_{1})$ . Hence today the expected payof to the call in a risk-neutral world is $C=S N(d_{1})-K e^{-r T}N(d_{2})$ .  

# 25.2 EUROPEAN OPTIONS: DIVIDEND PAYING STOCKS  

We show how to adapt the Black–Scholes equations to price options where the underlying asset generates a cash fow. To incorporate dividends in the Black–Scholes model for European options, two alternative methods are available depending on whether dividends are paid continuously or are discrete payments. Discrete dividend payments are applicable to options on individual stocks as dividends are often paid twice a year, while the assumption of continuous dividends is more applicable to options on stock indices, where the assumption that dividends are paid in a continuous stream (from many diferent stocks) is not too unrealistic.  

# 25.2.1 Discrete Dividends  

Assume there are n known dollar dividend payments $D_{i}$ over the life of the option, which are paid at discrete times $t_{i}$ from today (fraction of a year) on the ex-dividend dates. To price an option on a stock which pays discrete dividends, we merely replace the stock price $s$ in the Black–Scholes equation with $S^{*}$ where:  

$$
S^{*}=S-P V(d i\nu i d e n d s)=S-\sum_{i=1}^{n}D_{i}e^{-r_{i}t_{i}}
$$  

# 25.2.2 Continuous Dividend Payments  

Suppose dividends are paid continuously and the (annual) dividend yield $\delta$ (decimal) is constant. There is a ‘trick’ which enables us to obtain the correct option pricing formula for an option on a stock that pays continuous dividends:  

In the Black–Scholes formula use $S^{*}=S e^{-\delta T}$ in place of S.  

The standard Black–Scholes formulas then become:  

$$
\begin{array}{l}{{C=S e^{-\delta T}N(d_{1})-K e^{-r T}N(d_{2})}}\\ {{P=K e^{-r T}N(-d_{2})-S e^{-\delta T}N(-d_{1})}}\end{array}
$$  

Also $\ln(S e^{-\delta T}/K)=\ln(S/K)-\delta T$  

$$
d_{1}={\frac{\ln(S/K)+(r-\delta+\sigma^{2}/2)T}{\sigma{\sqrt{T}}}}
$$  

$$
d_{2}={\frac{\ln(S/K)+(r-\delta-\sigma^{2}/2)T}{\sigma{\sqrt{T}}}}=d_{1}-\sigma{\sqrt{T}}
$$  

where  

$C=$ call premium $P=$ put premium   
$S=$ stock price $\delta=$ dividend yield (continuously compounded) $\sigma=$ standard deviation $r=$ risk-free rate (continuously compounded) $T=$ time to maturity  

The intuition behind the above ‘trick’ is as follows. Payment of dividends causes a fall in the stock price by the amount of the dividend payment. Hence the growth rate for a stock which pays continuous dividends is reduced by $\delta$ .  

# 25.3 FOREIGN CURRENCY AND FUTURES OPTIONS  

The above formulas for pricing European calls and puts on dividend paying stocks can be easily adapted to price European options on foreign currencies and European options on futures contracts. Before we get into the detailed formulas note that the changes required are:  

# Option on foreign currency:  

Replace $\delta$ with the foreign interest rate $r_{f}$ .   
$s$ is now the spot exchange rate.   
$\sigma$ is the volatility of the $\left(\log\right)$ return on the spot-FX rate.  

# Options on futures:  

Replace $\delta$ by $r$ (this implies $r$ ‘disappears’ from the defnition of $d_{1}$ and $d_{2}$ ).   
Replace $s$ by $F$ (the futures price).   
$\sigma$ is the volatility of the $\left(\log\right)$ return of the futures price.  

When the cost of carry and the convenience yield are functions only of time it can be shown that the volatility of the futures price equals the volatility of the underlying asset, and $\sigma$ is usually taken to be the volatility of the futures price. Also, note that the option pricing formula for futures options (known as Black’s model) does not require that the futures option and the (underlying) futures contract have the same maturity date.  

# 25.3.1 European Option on Foreign Currencies  

Holding a foreign currency is analogous to holding a stock paying a known dividend yield (Garman-Kohlhagen 1983). The foreign currency pays a ‘dividend’ equal to the foreign  

risk-free rate $r_{f}$ . Since we assume the same stochastic process for the exchange rate $s$ as for a stock (paying dividends), our earlier formulas for pricing apply with:  

$\delta$ (dividend yield) is replaced by $r_{f.}$ , the foreign interest rate  

$$
{\begin{array}{r l}&{C=S e^{-r_{f}T}N(d_{1})-K e^{-r T}N(d_{2})}\\ &{P=K e^{-r T}N(-d_{2})-S e^{-r_{f}T}N(-d_{1})}\\ &{d_{1}={\frac{\ln(S/K)+(r-r_{f}+\sigma^{2}/2)T}{\sigma{\sqrt{T}}}}}\\ &{d_{2}={\frac{\ln(S/K)+(r-r_{f}-\sigma^{2}/2)T}{\sigma{\sqrt{T}}}}=d_{1}-\sigma{\sqrt{T}}}\end{array}}
$$  

The spot rate $S$ is measured as domestic per unit of foreign currency. For example, for a US resident if $s$ is measured as dollars per euro, then $r=$ the domestic (US) interest rate and $r_{f}~=$ interest rate in the Euro area. $\sigma$ is the volatility of $\ln(S_{t}/S_{t-1})$ – the change in the $\left(\log\right)$ exchange rate. Also, $r$ and $r_{f}$ are $T$ -period interest rates (continuously compounded).  

The above equations can be expressed in terms of the forward FX-rate (for the same maturity date as the option) since:  

$$
F=S e^{(r-r_{f})T}
$$  

which makes the FX-option price formula the same as Black’s generic formula for pricing options on any type of futures contract (see Chapters 38 and 39). Substituting $S=F e^{-(\hat{r}-r_{f})T}$ in the above Equations (25.6)–(25.8), gives the ‘forward price’ versions of European call and put premia on a foreign currency:  

$$
\begin{array}{l}{C=e^{-r T}[F N(d_{1})-K N(d_{2})]}\\ {P=e^{-r T}[K N(-d_{2})-F N(-d_{1})]}\\ {d_{1}=\displaystyle\frac{\ln(F/K)+(\sigma^{2}/2)T}{\sigma\sqrt{T}}}\\ {d_{2}=\displaystyle\frac{\ln(F/K)-(\sigma^{2}/2)T}{\sigma\sqrt{T}}=d_{1}-\sigma\sqrt{T}}\end{array}
$$  

The above formulas for $c$ and $P$ are easy to use and an example is given in Example 25.1.  

# EXAMPLE 25.1  

# Pricing a Call Option on Sterling (GBP)  

Inputs:  

$$
\begin{array}{r c l}{S}&{=}&{142\left(\mathrm{cents}/\mathrm{GBP}\right)}\\ {r}&{=}&{0.05\left(\mathrm{US~interest~rate}\right)}\\ {\sigma}&{=}&{0.15\left(\sigma^{2}=0.0225\right)}\end{array}
$$  

$$
\begin{array}{l}{K}\\ {\qquadr_{f}}\\ {\qquadr_{f}}\end{array}=\mathrm{0.09(UK\interest\rate)}
$$  

$$
d_{1}={\frac{\ln(142/145)+(0.05-0.09+0.0225/2)0.1370}{0.15{\sqrt{0.1370}}}}=-0.4475
$$  

$$
d_{2}=d_{1}-\sigma\sqrt{T}=-0.4475-0.0555=-0.5030
$$  

$$
N(d_{1})=0.3264,\qquadN(d_{2})=0.3074
$$  

$$
\begin{array}{c}{{C=142\ e^{-0.09(0.1370)}(0.3264)-145\ e^{-0.05(0.1370)}(0.3074)}}\\ {{=45.7808-44.2687=1.5121\ \mathrm{(cents/GBP)}}}\end{array}
$$  

# 25.3.2 European Option on a Futures Contract  

At maturity, a futures option delivers a futures contract. The payof at maturity for a call futures option is $\operatorname*{max}(0,{{F}_{T}}-K)$ and for a put futures option is $\operatorname*{max}(0,K-F_{T})$ . It can be shown that the futures price can be treated like a security paying a continuous dividend at a rate $\delta=r$ . Hence, we adapt the Black–Scholes formula (for dividend paying stocks) by:  

(dividend yield) is replaced by r and $s$ is replaced by $F$ .  

This gives Black’s (1976) formula for pricing options on futures contracts:  

$$
\begin{array}{l}{C=e^{-r T}[F N(d_{1})-K N(d_{2})]}\\ {P=e^{-r T}[K N(-d_{2})-F N(-d_{1})]}\\ {d_{1}=\displaystyle\frac{\ln(F/K)+(\sigma^{2}/2)T}{\sigma\sqrt{T}}}\\ {d_{2}=\displaystyle\frac{\ln(F/K)-(\sigma^{2}/2)T}{\sigma\sqrt{T}}=d_{1}-\sigma\sqrt{T}}\end{array}
$$  

Not surprisingly the above formulas are the same as those for the ‘forward price’ version of an option on a foreign currency (Equations 25.11–25.14).  

The assumptions, when using Black’s (1976) formula, are that the interest rate is constant and the underlying futures price has a lognormal distribution at maturity of the option. The latter is not unreasonable in the case of options on stock index futures and currency futures. However, for options on an interest rate dependent security (e.g. options on T-bonds, on T-bond futures, and options on interest rates), the assumption of a constant interest rate as used in Black’s model is less tenable – but even here Black’s model is often used to price European options on these fxed income securities (see Chapters 38 and 39).  

# 25.4 PUT–CALL PARITY  

# 25.4.1 European Options on Dividend Paying Stocks  

Similar to the above analysis, the put–call parity condition for an option on a stock that pays continuous dividends is obtained by replacing $s$ by $S^{*}=S e^{-\delta T}$ in the put–call parity condition for a non-dividend paying stock:  

To show that Equation (25.20) holds, consider the following two portfolios:  

Portfolio-A: One European put option plus $N=e^{-\delta T}$ stocks, with dividends being reinvested in additional stocks at the rate $\delta$ .   
Portfolio-B: One European call plus cash of $K e^{-r T}$ .  

Both options have the same strike and time to maturity. For $S_{T}>K$ , portfolio-A consists of one-stock worth $S_{T}$ , since the put is not exercised. For $S_{T}>K$ , portfolio-B has a payof from the call of $S_{T}-K$ plus cash of $K$ , making a total payof of $S_{T}$ – the same payof as portfolio-A.  

For $S_{T}<K$ , portfolio-A has a put payof of $K-S_{T}$ plus one stock worth $S_{T}$ , giving a total payof of $K$ . For $S_{T}<K$ , portfolio-B has a payof of $K$ in cash and the call is out-of-the-money. Hence portfolios A and B have the same payofs at $T$ and therefore must be worth the same today, otherwise risk-free arbitrage profts are possible. This gives rise to the put–call parity relationship in Equation (25.20).  

# 25.4.2 European Options on Currencies  

For European options on currencies we replace $\delta$ with $r_{f}$ so put–call parity is:  

$$
S e^{-r_{f}T}+P=C+K e^{-r T}
$$  

Put–call parity for foreign currency options can be established in a similar fashion to that for an option on a dividend paying stock. We take the US dollar as the domestic currency and the (pound) sterling (GBP) as the foreign currency. The spot exchange rate is $S\left(\mathbb{S}/\mathbb{£}\right)$ . Consider the following two portfolios:  

Portfolio-A: One put with price $\$9$ (strike $K$ and maturity T) plus cash of $\mathrm{USD}=S e^{-r_{f}T}$ invested in foreign risk-free asset   
Portfolio-B: One long call at $\$0$ (strike $K$ and maturity T) plus cash of $\mathrm{USD}=K e^{-r T}$ invested in domestic risk-free asset  

The risk-free asset could be T-bills or a bank deposit. We show in Table 25.1 that the payofs at maturity are the same for both portfolios and hence they must be worth the same today, which gives the put–call parity condition of Equation (25.21).  

For portfolio-A, if cash of USD, $S e^{-r_{f}T}$ is switched into sterling (at the current exchange rate $S\S/£$ ), you receive GBP of $e^{-r_{f}T}$ today. If this sterling amount is invested in a sterling bank deposit paying $r_{f}$ it will accrue to £1 at $T$ which can then be switched back into $S_{T}$ dollars (Table 25.1, top row).  

First consider the outcome for the two portfolios when $S_{T}>K$ . Portfolio-A pays $S_{T}$ dollars, since the put is out-of-the money. At $T$ , portfolio-B pays out $S_{T}-K$ dollars from the call and $\$1$ on the domestic (US) asset, giving a total payof $S_{T}$ – the same as portfolio-A.  

Consider the outcomes for $S_{T}<K$ . The put in portfolio-A pays out $K-S_{T}$ dollars and the sterling asset pays £1, equivalent to $S_{T}$ dollars at $T$ – that is, a net payof of $K$ dollars. For $S_{T}<K$ the call in portfolio-B is not exercised and the US bank deposit pays out $\$8$ at $T$ – which is the same payof as portfolio-A.  

TABLE 25.1 Put–call parity, currency options   


<html><body><table><tr><td colspan="2"> Today</td><td>S> K</td><td>S<K</td></tr><tr><td>Portfolio-A:</td><td>Cash of USD SeT invested in foreign risk free asset</td><td>S</td><td>ST</td></tr><tr><td></td><td>plus Long put</td><td>0</td><td>K-ST</td></tr><tr><td></td><td>Outcome Portfolio A</td><td>S</td><td></td></tr><tr><td>Portfolio-B:</td><td>Long call</td><td>S-K</td><td>0</td></tr><tr><td></td><td>plus Cash of USD Ke-rT invested in US risk</td><td></td><td>K</td></tr><tr><td></td><td>free asset</td><td></td><td></td></tr><tr><td></td><td>Outcome Portfolio B</td><td>S</td><td>K</td></tr></table></body></html>  

# 25.4.3 European Futures Options  

For European options on futures we take the put–call parity condition for a dividend paying stock, Equation (25.20) and  

replace $\delta$ by r and replace S by $F$  

which gives put–call parity for futures options:  

$$
P=C+(K-F)e^{-r T}.
$$  

An alternative derivation is to note that $F=S e^{(r-\delta)T}$ , hence $S=F e^{-(r-\delta)T}$ and if this is substituted in (25.20) we again obtain (25.22). To demonstrate put–call parity, we construct two portfolios which have the same payof at expiration and hence must have the same value today (Table 25.2). The two portfolios are:  

Portfolio-A Long futures cost of zero $+$ Long option futures Portfolio-B Long call option futures $^+$ Cash of $(K-F)e^{-r T}$ .  

The futures and the option both expire at $T$ . The cost of the long futures at $t=0$ is zero, since no money is required to initiate a futures position (we ignore margin payments). Note that if $K>F$ then today we hold cash of $(K-F)e^{-r T}$ and if $K<F$ we borrow an amount today of $|(K-F)e^{-r T}|$ . The amount $(K-F)e^{-r T}$ will accrue to $(K-F)$ at time $T$ .1 The long futures position at $T$ has a cash payout of $F_{T}-F$ , while the put payof is $\operatorname*{max}(K-F_{T},0)$ .  

TABLE 25.2 Put–call parity, futures options   


<html><body><table><tr><td>Portfolio</td><td>Current value</td><td>S> </td><td>S<K</td></tr><tr><td>Long futures</td><td></td><td>F-F</td><td>F-F</td></tr><tr><td>Long put</td><td>P</td><td>K-F</td><td>0</td></tr><tr><td colspan="2">Portfolio A: Long futures + Long put</td><td>K-F</td><td>F-F</td></tr><tr><td>Long call</td><td>C</td><td>0</td><td>F-K</td></tr><tr><td>Cash</td><td>(K-F)e-rT</td><td>K-F</td><td>K-F</td></tr><tr><td>Portfolio B: Long call + Bonds/cash</td><td></td><td>K-F</td><td>F-F</td></tr></table></body></html>  

First consider $F_{T}<K$ . For portfolio-A the long futures payof is $F_{T}-F$ and the put payof is $K-F_{T}$ , giving a net payof of $K-F$ . For portfolio-B when $F_{T}<K$ , the long call has a payof of zero and cash of $(K-F)e^{-r T}$ accrues to $K-F$ , so portfolio-B has the same payof as portfolio-A.  

Next consider $F_{T}>K$ . Portfolio-A has the long futures payof $F_{T}-F$ and the put payof is zero. For portfolio-B when $F_{T}>K$ , the call has a payof $F_{T}-K$ and the cash accrues to $K-F$ giving a net payof of $F_{T}-F$ – the same as for portfolio-A.  

Portfolios A and B have the same payof at $T$ and therefore must be worth the same today – otherwise risk-free arbitrage profts can be made. This gives rise to the put–call parity condition of Equation (20.22).  

# 25.5 SUMMARY  

• The standard Black–Scholes formula (on a non-dividend paying stock) can be adapted to price European options on stocks which pay discrete dividends by replacing $s$ in the Black–Scholes formula with:  

$$
S^{*}=S-P V(d i\nu i d e n t s)=S-\sum_{i=1}^{n}D_{i}e^{-r_{i}t_{i}}
$$  

• To price European calls and puts on stock indices which pay continuous dividends at the rate $\delta$ , we take the standard Black–Scholes formula (without dividends) and replace $s$ with $S^{*}=S e^{-\delta T}$ , hence:  

$$
\begin{array}{l}{C=S e^{-\delta T}N(d_{1})-K e^{-r T}N(d_{2})}\\ {P=K e^{-r T}N(-d_{2})-S e^{-\delta T}N(-d_{1})}\\ {d_{1}=\displaystyle\frac{\ln(S/K)+(r-\delta+\sigma^{2}/2)T}{\sigma\sqrt{T}}}\\ {d_{2}=\displaystyle\frac{\ln(S/K)+(r-\delta-\sigma^{2}/2)T}{\sigma\sqrt{T}}=d_{1}-\sigma\sqrt{T}}\end{array}
$$  

• European options on foreign currencies can be priced using Equations (25.23)–(25.26) by substituting the foreign interest rate $r_{f}$ in place of $\delta$ , with $r=$ domestic interest rate, $S={\tt s p o t}$ exchange rate (domestic per unit of foreign currency) and $\sigma$ is the volatility of the (log) return of the spot-FX rate.   
• European options on futures contracts can be priced using Equations (25.23)–(25.26) by ‘replacing’ $\delta$ with $r$ and replacing $s$ by $F$ . This gives Black’s (1976) formula for pricing options on futures contracts.  

$$
{\begin{array}{r l r l}{C~=e^{-r T}[F N(d_{1})-K N(d_{2})]}&{\quad}&{P=e^{-e T}[K N(-d_{2})-F N(-d_{1})]}\\ {d_{1}={\frac{\ln(F/K)+(\sigma^{2}/2)T}{\sigma{\sqrt{T}}}}}&{\quad}&{d_{2}={\frac{\ln(F/K)-(\sigma^{2}/2)T}{\sigma{\sqrt{T}}}}=d_{1}-\sigma^{*}}\end{array}}
$$  

• Put–call parity condition for European options on a stock that pays continuous dividends is obtained by replacing $s$ with $S^{*}\stackrel{\cdot}{=}S e^{-\delta T}$ in the put–call parity condition for a non-dividend paying stock:  

Non-dividend paying stock: $\begin{array}{r}{S+P=C+K e^{-r T}}\\ {S e^{-\delta T}+P=C+K e^{-r T}}\end{array}$ Stock paying continuous dividends:  

• Put–call parity for European options on a foreign currency can be obtained using Equation (25.27) by replacing $\delta$ with the foreign interest rate $r_{f}$ . • Put–call parity for European options on futures contracts can be obtained from Equation (25.27) by replacing $\delta$ with the (domestic) interest rate $r$ and replacing $s$ by $F$ :  

$$
P=C+(K-F)e^{-r T}
$$  

• The put–call parity relationships for European options all assume that risk-free arbitrage opportunities have been eliminated.  

# EXERCISES  

# Question 1  

The stock index is $S=1{,}100$ with volatility $\sigma=20\%$ and the risk-free rate of interest is $r=5\%$ (continuously compounded). European calls and puts are available with a strike of $K=1{,}000$ and time to maturity $T=6/12$ years. Over the life of the option, the stocks in the index pay a dividend at a (continuously compounded) rate of $\delta=0.03$ .  

Use the Black–Scholes equation to calculate $d_{1}$ and $d_{2}$ and the price of the call and put.   
Check your calculations using put–call parity.  

# Question 2  

Swiss franc (SFr) January-60 European call and put options have 6 months to maturity. The current spot-FX rate is 64, the current US risk-free rate is $6\%$ p.a. and the Swiss interest rate is $3\%$ p.a. (continuously compounded). The volatility $\sigma$ of the USD-SFr exchange rate is $20\%$ p.a. (All currency quotes are in US cents per Swiss franc.)  

(a) Calculate the call and put premia (for these European options) using the Black–Scholes (Garman–Kohlhagen) formulas.   
(b) Check your calculations for call and put premia using put–call parity.   
(c) What is the intrinsic and time value of the call and put?  

# Question 3  

What is the link between the original Black–Scholes (European) option pricing formula on an underlying asset with price, $s$ paying a continuous ‘dividend yield’ $\delta$ , and Black’s formula for the price of a (European) futures option?  

# Question 4  

The price of a European call on a foreign currency is given by  

$$
\begin{array}{l c r}{C=S e^{-r_{f}T}N(d_{1})-K e^{-r T}N(d_{2})}\\ {{}}\\ {d_{1}=\displaystyle\frac{\ln(S/K)+(r-r_{f}+\sigma^{2}/2)T}{\sigma\sqrt{T}}}\\ {{}}\\ {d_{2}=d_{1}-\sigma\sqrt{T}}\end{array}
$$  

Using the equation for the forward rate for foreign currency show that this can be expressed as:  

$$
\begin{array}{l}{C=e^{-r T}[F N(d_{1})-K N(d_{2})]}\\ {d_{1}=\displaystyle\frac{\ln(F/K)+(\sigma^{2}/2)T}{\sigma\sqrt{T}}}\\ {d_{2}=d_{1}-\sigma\sqrt{T}}\end{array}
$$  

# Question 5  

A European futures call option on oil with 6 months to expiration has a strike price $K=\$100$ , the current 6-month futures price $F=\$100$ , the risk free rate $r=4\%$ (continuously compounded) and the volatility of the $(\log)$ change in the oil price is $\sigma=20\%$ . The call premium using Black’s formula is $C=5.5256$ . A European put option (with the same underlying, strike and time to maturity as the call) has a quoted price of $P_{q}=5.0$ .  

Using put–call parity, show how an arbitrage proft can be made.  