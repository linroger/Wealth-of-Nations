---
cssclasses: academia
linter-yaml-title-alias: LECTURE NOTE 5 BLACK SCHOLES FORMULA
title: Lecture Note 5Black Scholes Formula
tags:
  - black_scholes_formula
  - delta_hedging
  - dynamic_replication
  - option_premium
  - option_pricing
aliases:
  - Black Scholes Formula
  - Black and Scholes Formula
  - Lecture Note 5Black Scholes Formula
key_concepts:
  - Black Scholes Formula
  - Delta Hedging
  - Dynamic Replication
  - Option Premium
  - Replicating Portfolio
---

---

title: LECTURE NOTE 5 BLACK SCHOLES FORMULA

aliases: [LECTURE NOTE 5 BLACK SCHOLES FORMULA]

linter-yaml-title-alias: LECTURE NOTE 5 BLACK SCHOLES FORMULA

# Lecture Note 5Black Scholes Formula

[Binomial Tree Steps](Binomial%20Tree%20Steps.md)

[Ch1 Introduction to Derivative Markets](Ch1%20Introduction%20to%20Derivative%20Markets.md)

[The Pricing of Options and Corporate Liabilities](Asset%20Classes/Derivatives/Options/The%20Pricing%20of%20Options%20and%20Corporate%20Liabilities.md)

## FINANCIAL INSTRUMENTS TEACHING NOTE 5 BLACK AND SCHOLES FORMULA
1. Black and Scholes Formula
1.1 Dynamic Replication
1.2 Black and Scholes and the Binomial Trees
1.3 Delta,  Gamma,  and other Greeks
1.4 Options' Beta and Expected Returns
1.5 Delta Hedging
1.6 Delta Gamma Hedging
## OPTION PREMIUM
- Black,  Scholes and Merton show that (under certain conditions) there exists a trading strategy
involving only stocks and bonds that *replicate* the payoff at$T$of a call or a put option.
- Assume a stock$S_{t}$has constant expected (log) return$µ$and constant volatility σ.
- That is,  if the log return during a small time interval$h$be${} R_t = log\left(\frac{S_{t+h}}{S_t} \right) {}$,  assume
$$E[R_{t}]=\mu\times h;\;\;E[R_{t}^{2}]=\sigma^{2}\times h$$
- (µ and σ are the annualized expected log return and volatility)
- Consider now a put option with strike price K and maturity T.
- The following trading strategy **replicates** the final payoff $max(K − S_T,            0)$.
## OPTION PREMIUM BY DYNAMIC REPLICATION
1. At time 0:
(a) Short$∆0 = −N(−d_{1,           0})$of stocks
- Here$N(x)$is the standard normal cumulative density function,  and$d_{1,           t}$is$$d_{1,           t}=\frac{\ln\left(S_{t}/K\right)+\left(r+\sigma^{2}/2\right)\left(T-t\right)}{\sigma\sqrt{T-t}}$$
- $r$is the continuously compounded risk free rate;$\sigma$is the volatility of stock returns.
(b) Buy an amount$B_0 = K × e^{−r×T} × N(−d_{2,           0})$of Treasury Zero Coupon bonds.
- Here$d_{2,           0} = d1,           t − σ × \sqrt{T}$.
- The portfolio so constructed has value at time 0
$$P_{0}=B_{0}+\Delta_{0}S_{0}$$
- (it can be shown P0 > 0).
1. From now on,  *rebalance* the portfolio,  to make sure that at every t,  the portfolio has a position in stocks given by$$∆t = −N(−d_{1,           t})$$
- E.g. if$S_{t}$↓ ⇒$∆t$↓⇒ short more stocks and put proceeds into bonds ⇒$B_{t}$↑.
- Or if$S_{t}$↑ ⇒$∆t ↑$⇒ buy back stocks by liquidating some bonds ⇒$B_{t}$↓.
## OPTION PREMIUM BY DYNAMIC REPLICATION
- For instance,  let$S$= K = 100,  T = 1,  r = 5%,  σ = 20%. Then,
d1 =; d2 =; N(−d1) = 0.3632; N(−d2) = 0.4404 =⇒ ∆0 = −N(−d1) = −0.3632
- Initial short position in stocks:$$∆ × 100 = −N(d_1) × 100 = −0.3632 × 100 = −36.32$$.
- Initial bond position:$$B_0 = Ke^{-rT}N(−d_2) =41.89$$.
- Initial value of the portfolio:$$P_0 = B_0 + ∆_0S_0 =41.89 −36.32 =5.57$$
- One day later (h = 1/252 = 1 day) the stock is$S_h = 99$=⇒$∆h = −N(−d1,           h)$= −0.3821
- Need to short more,  and thus sell$|∆_h − ∆_0| = | −0.3821 − (−0.3632)| = 0.0189$shares.
- Obtain cash =$0.0189 × 99 =1.879$,  and put it in bonds:
New Bond Position =$$B_h = B_0 × e_{r×h} +1.879 =41.89 −1.879 =43.777$$New Portfolio Position =$$P_h = B_h + ∆_h × S_h =43.777 − × 99 =5.941$$
## OPTION PREMIUM BY DYNAMIC REPLICATION
- **Fact:** The portfolio Pt = ∆t$S_{t}$+$B_{t}$obtained from the above trading strategy *replicates* the put option payoff.
- That is,  at maturity$$P_{T}=\Delta_{T}S_{T}+B_{T}=\max(K-S_{T})$$
- *Proof by simulation:* Next two figures shows that the strategy works,  even when portfolio rebalancing is at daily interval ($h=1/252$).
- I simulate stock price paths. And then performed the above trading strategy.
## OPTION PREMIUM BY DYNAMIC REPLICATION

 ![500](Obsidian%202024-10-04%2016.37.30.png)

 ![500](Obsidian%202024-10-04%2016.37.53.png)

 ![500](9f437bafc6f0d76f8ad3f0af6ad25e9b6688c490ee3fc154ba46b7b54eb57e4b.png)

 ![500](807e472a44c55673e8cae3f79ee1bf6ecc02b8d50f83f414ffbc94ffc6d0fe35.png)

 ![500](82c5af46b3.png)

OPTION PREMIUM BY DYNAMIC REPLICATION

 ![500](b8d85f2f265d55393d652.png)

### BLACK AND SCHOLES FORMULA
- Since portfolio Pt replicates the payoff of the put option,  the value of the portfolio at any time must equal the value of the put option.
- Why? - Arbitrage: "Buy Cheap / Sell Dear".
- For instance,  if Pt < Put Option Premium =⇒
1. Sell option and set up the replicating portfolio (which costs$P_t$)
1. Today make$(\text{Put Option Premium} −P_t) > 0$.
1. At maturity T the replicating portfolio provides the payoff,  exactly.
- In particular,  at time 0,  the value of the option mu$S_{t}$be
Put Premium at 0,  $p_{0}\ =\ P_{0}=B_{0}+\Delta_{0}\times S_{0}$
$$=\ K\times e^{-rT}\times N(-d_{2,           0})-S_{0}\times N(-d_{1,           0})$$
- This is the celebrated "Black and Scholes" formula for option pricing.
- Similarly,  a call option formula is given by
$$\mathrm{Call~Premium~at~0,           ~}c_{0}=S_{0}\times N(d_{1,           0})-K\times e^{-r T}\times N(d_{2,           0})$$
## DELTA HEDGING AND DYNAMIC REPLICATION
- Why does the dynamic replication strategy work?
- Suppose you sold a put option and decide to hedge using the replicating portfolio P.
- Let Π be the portfolio short the put (−p) and long the replicating portfolio
$$\begin{array}{r c l}{{\Pi}}&{{=}}&{{-p+P}}\\ {{}}&{{=}}&{{-p+\Delta S+B}}\end{array}$$
- What is the sensitivity of Π to *small* variations in stocks?
$$\frac{d\;\Pi}{d\;S}=-\frac{d\;p}{d\;S}+\Delta\times1+0$$
- The portfolio Π is delta hedged$(d Π^*/d S* = 0)$if
$$\Delta={\frac{d\ p}{d\ S}}$$
- It can be shown that indeed$∆ = −N(−d_1)$is exactly$d p/d S$
- This implies that for every *small* variation in stock S,  the portfolio and the option move exactly by the same amount.
- =⇒ the dynamic replication works.
## DELTA HEDGING AND DYNAMIC REPLICATION
- The next figure shows the dynamic replication at work in a graph:
 ![500](Obsidian%202024-10-04%2016.38.00.png)
 ![500](de3c911d9416ed48b3ffc.png)
## BLACK AND SCHOLES FORMULA
- Example: Consider an at-the-money option.
- The stock price is$S$= 100,  the strike price is K = 100,  the (continuously compounded)
interest rate is r = 5%,  maturity is T = 1,  and the return volatility σ = 30%.
- We then have
$$d_{1}=\frac{\log\left(\frac{S}{K}\right)+(r-\delta+\sigma^{2}/2)T}{\sigma\sqrt{T}}=\frac{\log\left(\frac{100}{100}\right)+(+(0.30)^{2}/2)\times1}{0.30\sqrt{1}}=0.3167;$$
$$d_{2}=d_{1}-\sigma\sqrt{T}=0.3167-\sqrt{1}=0.0167$$
- Therefore$N(d_{1})=0.62425$and$N(d_{2})=0.50665$.
- The value of the call option is
$$c_{0}=SN(d_{1})-Ke^{-rT}N(d_{2})=100\times0.62425-100\times e^{\times1}\times0.50665=14.2312$$
- The value of a put option can be computed from these data by recalling that
$$N(-d_{1})=1-N(d_{1})=0.37575;\quad N(-d_{2})=1-N(d_{2})=0.49335$$
- so that
$$p_0 = −SN(−d1) + Ke^{-rT}N(−d2) = −100 × 0.37575 + 100 × e^{1 × 0.49335} = 9.3542$$
- To interpret the Black and Scholes formula it is convenient to go back to binomial trees discussed in TN 4.
- Black and Scholes model assumes continuous trading
- That is,  traders can trade at any instant$t$
- Moreover,  stock prices can take on any value,  and not only the values on a tree.
- Both conditions are approximately met as we let the time interval$h = T/n$in the binomial tree go to zero.
- Indeed,  as we have seen,  recall that we have the following:
	- **Fact:** As n goes to infinity,  the Binomial Tree price converges to Black and Scholes price
	- To see the similarity of Black and Scholes formula with the one stemming from a binomial tree,  consider the following example.
 ![500]d9eae26af9a0ff47259210.png)
- Consider i = 0 and i = 1 with$S_{1,           u} = S_0 × u$and$S_{1,           d} = S_0 × d$.
- Assume the price of the option has S1,  u *> K > S*1,  d,  so that the payoffs from the tree above result.
- Let$q^∗$be the risk neutral probability of going up in the tree.
- The price of the option at time 0 according to risk neutral pricing is the
$$c_{0}=e^{-r\times T}E^{*}\left[\max(S_{1}-K)\right]$$$$=e^{-r\times T}\times\left[q^{*}\times\max(S_{1,           u}-K)+(1-q^{*})\times\max(S_{1,           d}-K)\right]$$$$=e^{-r\times T}\times q^{*}\times(S_{1,           u}-K)$$$$=S_{0}\times e^{-r\times T}\times q^{*}\times u-e^{-r\times T}\times K\times q^{*}$$$$=S_{0}\times N_{1}-e^{-r\times T}\times K\times N_{2}$$
- where,  defining by$u_{vc}$the annualized c.c. return from an up movement$S_{1,  u}/S_{0}=e^{u_{vc}\times T}=u$$$N_{1}=e^{-r\times T}\times q^{*}\times u=e^{(u_{vc}-r)\times T}\times q^{*}\quad\text{and}\quad N_{2}=q^{*}$$
- The similarity with Black and Scholes formula is not coincidential
$$\mathrm{Call}=S\times N(d_{1})-K\times e^{-r T}\times N(d_{2})$$
- Interpretation:
- $N_2 = N(d_2)$risk neutral probability to be in the money at maturity;
- $N_1 = N(d_1)$risk neutral expected excess return *conditional* on exercise at T.
- Indeed,  recall we obtained the following formula in TN 4 for a large number of steps n:
$$c_0\:=\:e^{-rT}E^*\left[\max(S_T-K)\right]$$
$$=\left.e^{-r\times T}\sum_{j=0}^n\left(\frac{n!}{j!(n-j)!}\right)\max(S_{T,           j}-K)\right.$$
· where $S_{T,           j}=S_0\times u^{(n-j)}\times d^j.$ · Let $a$ be the smallest integer for which $S_{T,           j}>K$ for $j\geq a,           $ and $S_{T,            j}< K$for$j<a$
 · Putting all together:
$$\begin{aligned}c_0&=&e^{-r\times T}\sum_{j=a}^n\left(\frac{n!}{j!(n-j)!}\right)(S_{T,           j}-K)\\&=&S_0\times N_1-K\times e^{-r\times T}\times N_2\end{aligned}$$
$$\begin{aligned}\text{h}\quad N_1~=~\left(e^{-r\times T}\sum_{j=a}^n\left(\frac{n!}{j!(n-j)!}\right)\times u^{(n-j)}\times d^j\right)\quad\text{and}\quad N_2=\sum_{j=a}^n\left(\frac{n!}{j!(n-j)!}\right)\end{aligned}$$
- It can be shown that$N_1\to N(d_1)$and$N_2\to N(d_2)$as$n\to\infty$·The interpretation,  though,  is the same as in the simple 2-period model.
## DOES THE DYNAMIC REPLICATION STRATEGY WORK IN REALITY?
- Black and Scholes formula relies on dynamic replication. Does it actually work in reality?
- Sometimes yes: e.g. Jan - Dec 2000
	- Replication of S&P500 option with T = 1 year. σ = standard deviation of returns in 1999.
 ![500](a0a066b36c5ace6a32d6593d8b113d31.png)
## DOES THE DYNAMIC REPLICATION STRATEGY WORK IN REALITY?
- Sometimes no: e.g. Jan - Dec 1987
-  ![500](310cd3852c2b02cfa09c96b2ce307c53.png)
- We will return on the empirical performance of Black and Scholes model in the next TNs.
## BLACK AND SCHOLES PRICING FORMULA
- Like futures,  simple modifications to the option specification can still be treated within the Black and Scholes framework.
 1. OPTIONS WITH *KNOWN* DIVIDEND
- Define$S^∗ =S− PV (D)$where$PV (D)$= Present Value of Dividends before expiration.
- Use Black and Scholes formula with$S^∗$instead of$S$.
 1. OPTIONS WITH *KNOWN* DIVIDEND YIELD Q
- Define S∗ =$S$× e−q×T and use Black and Scholes formula as usual.
$$\begin{array}{l l}{{c\ =\$S$e^{-q T}N(d_{1})-K e^{-r T}N(d_{2});}}&{{\ p=K e^{-r T}N(-d_{2})-S e^{-q T}N(-d_{1});}}\\ {{}}\\ {{d_{1}\ =\ \frac{\ln(S/K)+(r-q+\sigma^{2}/2)T}{\sigma\sqrt{T}};}}&{{d_{2}=d_{1}-\sigma\sqrt{T}}}\end{array}$$
 1. OPTIONS ON CURRENCIES
- When you buy foreign currency,  you would invest in foreign Treasuries. Thus,  $r_{foreign}$is a dividend yield. Apply previous formula with$q = r_{foreign}$.
1. FUTURES OPTIONS
- Entering into a futures position does not co$S_{t}$anything. Thus,  compared to the dynamic replication with stocks,  a trader would *save* the riskless rate.
- The option pricing formula is then Black and Scholes formula in which the futures price$F$is used instead of$S$,  but the "dividend yield" equals the risk free rate$q = r$.
- Substituting this in the previous formula:
$$c~=~e^{-r T}[F N(d_{1})-K N(d_{2})];~~~~p=e^{-r T}[K N(-d_{2})-F N(-d_{1})]$$
$$d_{1}~=~\frac{\ln(F/K)+(\sigma^{2}/2)T}{\sigma\sqrt{T}};~~~~d_{2}=d_{1}-\sigma\sqrt{T}$$
## RISKS IN OPTIONS AND THE GREEKS
- Risk managers and traders need to control the sensitivity of options to changes in the underlying. - Terminology:
1. **Delta**: Sensitivity of option to changes in underlying
$$\Delta=\frac{d\;\mathrm{Option\;Price}}{d\;S}=\left\{\begin{array}{l l}{{N(d_{1})}}&{{\mathrm{~for\;Calls}}}\\ {{-N(-d_{1})}}&{{\mathrm{~for\;Puts}}}\end{array}\right.$$
1. **Gamma**: Sensitivity of Delta ∆ to changes in the underlying. For both calls and puts:
$$\Gamma=\frac{d\ \Delta}{d\ S}=\frac{N^{\prime}(d_{1})}{S\sigma\sqrt{T}}\quad\mathrm{~with~}\ N^{\prime}(x)=\frac{e^{-x^{2}}2}{\sqrt{2\pi}}$$
- =⇒$\Gamma$= curvature of option price with respect to stock S;
## RISKS IN OPTIONS AND THE GREEKS RISKS IN OPTIONS AND THE GREEKS RISKS IN OPTIONS AND THE GREEKS
## RISKS IN OPTIONS AND THE GREEKS

 ![500](0b083e8311dca709f00de5289d7e9936.png)

RISKS IN OPTIONS AND THE GREEKS

 ![500](92ffd2566d50d6c0218ae50e0bd182ba.png)

1. **THETA**: SENSITIVITY OF OPTION TO PASSAGE OF TIME T RISKS IN OPTIONS AND THE GREEKS$$\Theta=\frac{d\text{ Option Price}}{ d \mathrm{~}t}=\text{Long ugly formula}$$
 ![500](23e937f63b7eaacf68f8e4fd36e33850.png)
- Why for a put option Θ > 0 for low$S$and Θ < 0 for high S?
- For$S$high,  payoff is zero,  but put price is positive.
	- =⇒ As time passes (but keeping$S$fixed),  the put price mu$S_{t}$decline.
- For$S$low,  why is Θ > 0?
	- Simple example: the firm goes bankrupt =⇒$S$= 0.
		- =⇒ Put payoff at T = K.
	- Value at time *t < T* is$p = e^{−r(T−t)}K$,  which increases with t.
- What about call options?
	- For non-dividend paying stock,  Θ < 0 for call options.
		- If$S$is very very high,  option holder will receive$S−$K at maturity (with high probability)
		- This is the payoff of a long forward,  so present value at$t < T$is$c =S−Ke^{-rT} >S−K$
			- Intuition: for calls,  we will pay K,  whose present value today is smaller than K,  pushing up the price of the call.
- If the stock pays (a lot of) dividends,  then Θ > 0 for high S,  as the option holder misses the dividend payouts during the life of the option (compared to a stock holder).
 ![500](44e2c18c4c0158811c7968e5b0c8b6bc.png)
- In Black and Scholes model,  the volatility σ and the interest rate r are constant.
- However,  it is interesting how does a change in σ and r change the value of the option.
1. **Rho**: Change in option price due to a change in interest rate r
$$\mathrm{Rho}={\frac{d~\mathrm{Option~Price}}{d~r}}=\left\{\begin{array}{l l}{{K T e^{-r T}N(d_{2})>0}}&{{\mathrm{~for~Calls}}}\\ {{-K T e^{-r T}N(-d_{2})<0}}&{{\mathrm{~for~Puts}}}\end{array}\right.$$
- Intuition: it all depends on whether the option holder will pay K (call) or receive K (put).
The PV of K declines as r increases,  yielding the result.
1. **VEGA**: CHANGE IN OPTION PRICE DUE TO A CHANGE IN VOLATILITY Σ EXAMPLE OF RISK MANAGEMENT PROBLEM$$\text{Vega}=\frac{d\text{ Option Price}}{ d \mathrm{~}\sigma}=S\sqrt{T}N^{\prime}(d_1)>0$$
 ![500](49bb935ac04b3456b51a6767b5f39c3b.png)
- Assume today is Feb 22,  2008 and you sold the following Capital Protected Note:1
- Maturity: February 20,  2015
- Issue Price:$10 - Principal:$10
- Interest: 0
- Principal Protection: 100% - Payoff at maturity: Principal plus Supplemental Redemption Amount (SRA),  if positive.
- Index: S&P 500,  renormalized to have Initial Index Value =$10.
- If you sell this security,  then you mu$S_{t}$protect your position again$S_{t}$increases in the stock price.
- =⇒ Delta-hedge =⇒ need to set up the replicating portfolio.
## THE CAPITAL PROTECTED NOTE'S PAYOFF

 ![500](bbbbf486ab7cc6cdfc53831bfd3fd43b.png)

- The Capital Protected Note's payoff can be decomposed into
1. A zero coupon bond with principal$10 and maturity T = 7.
1. 1.16 at-the-money call options on the (normalized) S&P 500 with maturity T = 7.
- The reference index is normalized so that$S_0$= β × S&P500 =$10.
- On Feb 28,  2008,  we had S&P 500 = 1353.1. =⇒ β = 10/1353.1.
- Other data on Feb 28,  2008,  are as follows
- The 7-year (c.c.) interest rate was r = 3.23%.
- The dividend yield of SP500 is δ = 2%.
- Let the volatility foreca$S_{t}$over 7-year be σ = 15% - The value of the security is
$$\begin{array}{l l}{{V a l u e\ =\ e^{-r T}\$10+1.16\times C a l l(10,           10,           r,           \delta,           \sigma,           T)}}\\ {{\ \ \ \ \ \ \ \ =\ \$7.9764+1.16\times\$1.7}}\\ {{\ \ \ \ \ \ \ \ =\ \$9.9483}}\end{array}$$
- Close to$10 - Note that an investor in CPN trades off coupons for 1.16 call options.
## DELTA HEDGING AT TIME 0
- How can we hedge the short CPN? - Theoretically,  we ju$S_{t}$need a position in the replicating portfolio:
1. Buy a zero coupon bond today for$7.9764 (to hedge the "bond" component)
1. Purchase 1.16 units of the replicating portfolio for the (embedded) call option.
- The replicating portfolio *for each call* is as follows:
- Given the call ∆ = e−δTN(d1) = 0.5747,  we have:
Position in (normalized) S&P500 = 0.5747;
$$\begin{array}{lll}\text{Bond Position}&=&Call(10,           10,           r,           \delta,           \sigma,           T)-\Delta\times S_0\\ &=&1.7-\Delta\times10=-4.047\end{array}$$
- That is,  for each call option,  invest\$0.5747 × \$10 = 5.747 in stock and borrow$4.047.
VALUE OF REPLICATING PORTFOLIO =$0.5747 \times10-4.047=1.7$
.
- Multiply the positions above by 1.16 and we obtain the replicating portfolio for a CPN.
## DYNAMIC DELTA HEDGING
- Theoretically,  if we rebalance frequently the position in stocks,  the portfolio will replicate exactly
the payoff the structured derivative.
- If$S_{t}$increases,  ∆ increases and we mu$S_{t}$borrow more to inve$S_{t}$more in stocks (how much?);
- If$S_{t}$decreases,  ∆ decreases and we sell some stocks and use the proceeds to repay some of
the loan.
## DELTA-GAMMA HEDGING
- There are some issues with delta-hedging
1. For any small variation in stock price we need to rebalance the portfolio
- =⇒ with transaction costs this is expensive.
1. Large variations in the stock price imply the hedge does not work too well.
- We can alleviate somewhat these problems by "Delta-Gamma" hedging:
- In addition to stocks,  we need a position in a security with positive Gamma,  such as a
short-term traded option.
- Consider a portfolio$\Pi$which is short the$T-$dated call$Call(S,           T)$(as the one implicit in the CPN),  long$N$stock and long also$N^{c}$of$T_{1}-$date calls$Call(S,  T_{1})$$$\Pi=-Call(S,  T)+N\times S+N^{c}\times Call(S,  T_{1})$$
- We want to hedge both the sensitivity of Π to changes in the stock (dΠ
dS = 0) and the change in
such sensitivity to changes in the stock,  that is,  the convexity
$$d\,           \frac{\left(\frac{d\Pi}{d S}\right)}{d S}=\frac{d\Pi^{2}}{d S^{2}}=0$$
 ![500](76ace2442a76b1b506b98c54cdafddfc.png)
## DELTA-GAMMA HEDGING
- The Delta-Gamma hedge then requires:
$$\frac{d\Pi}{dS}=0\Longrightarrow-\frac{dCall(S,           T)}{dS}+N+N^{c}\times\frac{dCall(S,           T_{1})}{dS}=0\qquad\mbox{(Delta Hedging)}$$$$\frac{d^{2}\Pi}{dS^{2}}=0\Longrightarrow-\frac{d^{2}Call(S,           T)}{dS^{2}}+N^{c}\times\frac{d^{2}Call(S,           T_{1})}{dS^{2}}=0\qquad\mbox{(Gamma Hedging)}$$
- Using the notation ∆(*S,  T*) and Γ(*S,  T*) to indicate the Delta and Gamma of the option with
maturity T,  solving the two equations in two unknowns we obtain:
$$N^{c}=\frac{\Gamma(S,           T)}{\Gamma(S,           T_{1})};\quad N=\Delta(S,           T)-N^{c}\times\Delta(S,           T_{1})$$
- Note that the position in stocks is smaller (if N c > 0) than in the case of only Delta-hedging,
as we now have to also hedge the position in the short-term call option,  which is used to hedge again$S_{t}$Gamma.
## DELTA-GAMMA HEDGING: THE CAPITAL PROTECTED NOTE
- For instance,  using a 1−year option to hedge the CPN,  we have
$$\begin{array}{r l r l}{{C a l l(S,           T)=1.7;}}&{{\Gamma(S,           T)=0.08016;}}&{{\Delta(S,           T)=0.5747}}\\ {{C a l l(S,           T_{1})=0.6443;}}&{{\Gamma(S,           T_{1})=0.2575;}}&{{\Delta(S,           T_{1})=0.5512}}\end{array}$$
- we obtain
Position in short-term call = N c = 0.3113;
Position in stock = N = 0.4031;
Position in bonds = 1.7 − N ×$S$− N_c × Call(*S,  T*1) = −2.5315
- Next figure plots the CPN for various stock prices,  along with the Delta hedge portfolio and the
Delta-Gamma hedge portfolio.
 ![500](8b5b1043a76ea7cdeed7def54d1512e3.png)
## DELTA-GAMMA HEDGING: THE CAPITAL PROTECTED NOTE
- The Delta-Gamma hedging strategy allows for larger swings in the stock price before calling for
a rebalancing.
- For instance,  under Delta hedging,  we need rebalance to when *S <* 9 or *S >* 11,  as the
dashed line starts diverging from solid line.
- Instead,  Delta-Gamma requires rebalancing only when *S <* 8 or *S >* 13,  as the dotted line
is very close to the solid line for a much wider range of prices.
- Less frequent rebalancing implies lower transaction costs.
- Of course,  now we have more transaction costs because we have to rebalance also the
T1−option positions.
- We need to use very liquid,  exchange traded securities to minimize transaction costs on
options.
- Note that the additional benefit of the strategy is that large sudden changes in the stock price
(plus/minus 20%) are hedged.
- A curiosity: From the figure,  the CPN is valued at \$8 for$S$low. In what sense this is a "capital
protected note"? If the investor sells the security when$S$is low,  he/she would not recover$10.
- We know that ∆ = N(d1) is the sensitivity of a call option price to changes in the stock price
- What is the *percentage* sensitivity of the call price to *percentage* change in the stock price?
- =⇒ In percentage,  call options move more than the underlying stock
- What is the risk premium on an option? - Recall that a call option is given by a portfolio of stocks and bonds
$$\mathrm{Call}=\Delta\times S+B$$
- As for any portfolio,
Return on a portfolio = weighted average of the returns of the individual assets
- where the weights are given by relative positions in the assets.
- That is,  let RC be the return on the call,  RS the return on stock,  and RB the return on bonds
over a small interval of time
$$R_{C}=w\times R_{S}+(1-w)\times R_{B}$$
- where the weight on stock is
$$w={\frac{\mathrm{Position~in~Stock}}{\mathrm{Value~of~Portfolio}}}={\frac{\Delta\times S}{\mathrm{Call}}}={\frac{\%{\mathrm{age~Change~in~Call}}}{\%{\mathrm{age~Change~in~Stock}}}}$$
- If$S$is the aggregate market (e.g. S&P500),  then we can think of w as the Call Option's Beta.
- Developing the return equation and using also the notation w = β,  we obtain
$$
(R_C-R_B)=\beta\times(R_S-R_B)
$$

 ![500](fce45ee4408b6c513f8ca493d2af75cc.png)

- Given such large β,  the excess return on a call option is much larger than the one on the stock.
- A call option is effectively a Leveraged Investment
- We borrow (B) to purchase (∆) stock with minimum equity investment (*Call*)
	- =⇒ Expected Excess Return is very high:$E [R_C − R_B] = β × E [R_S − R_B]$
- Note that β depends on S,  so it is not constant.
- Clearly,  the risk is also very high. What is the variance of call option returns?
- It is$β^2 \times$variance of stock returns:$σ_{c}^2=β^2 × σ_{s}^2$
 ![500](a0a60ba734ac5dd7a94901bf9c0c2f88.png)
 ![500](991e9c50231370c4a65f763a5f035534.png)
 ![500](3cddb2484285391085c6963ee376570f.png)
- The volatility of the call option,  computed as the 22-day standard deviation of returns,  is much higher than the one of the SP500 index.
## THE RISK / RETURN CHARACTERISTICS OF OPTIONS

,  The Risk / Return characteristics of an investment is often measured by the Sharpe Ratio

$$\text{Sharpe Ratio}=\frac{\text{Expected Excess Return}}{\text{Volatility}}$$

· The Sharpe Ratio of a Call option is therefore

$$\text{Sharpe Ratio of Call}=\frac{\text{Expected Excess Return Call}}{\text{Volatility Call}}$$

$$=\frac{E[R_C-R_B]}{\sigma_C}$$

$$=\frac{\beta E[R_S-R_B]}{\beta\sigma_S}$$

$$=\text{Sharpe Ratio of Stock}$$

·The Sharpe Ratio is the same as the one of stocks (theoretically,  at least)