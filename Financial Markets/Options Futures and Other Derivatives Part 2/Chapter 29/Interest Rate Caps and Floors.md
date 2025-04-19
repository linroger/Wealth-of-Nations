---
tags:
  - caplet_pricing
  - floating_rate_note
  - interest_rate_caps
  - interest_rate_floors
  - shifted_lognormal_model
aliases:
  - Caps and Floors
  - Interest Rate Cap
  - Interest Rate Floor
key_concepts:
  - Bachelier normal model
  - Call options on interest rates
  - Effective reference interest rate
  - Floating-rate note
  - Series of put options
  - Strike price per annum
  - Three-month reference interest rate
---

# 29.2 INTEREST RATE CAPS AND FLOORS  

An interest rate cap is a series of call options on interest rates. It can be understood by considering a floating-rate note where the interest rate is reset every three months.1 The interest rate for each three-month period is based on a three-month reference interest rate, applicable to the period, that is observed in the market. (For example, the interest rate on the floating-rate note could be the reference interest rate plus 25 basis points.) If a company borrows $\$10$ million for five years using the floating-rate note and enters into a cap with a notional principal of $\$10$ million and a strike price of $3\%$ per annum, the company has ensured that the effective reference interest rate determining its loan interest payments will never be more than $3\%$ per annum. If the reference interest rate for a particular quarter is less than $3\%$ , there is no payoff for the quarter, but when this interest rate is greater than $3\%$ there is a payoff designed to bring the effective reference interest rate down to $3\%$ per annum. For example, if the reference interest rate for a period is $4\%$ , the cap will provide a payoff of  

$$
0.25\times\S10,000,000\times(0.04-0.03)=\S25,000
$$  

to reduce the effective reference rate for the quarter to $3\%$ per annum.  

Similarly an interest rate floor is a series of put options on interest rates. A company that owns a. $\$10$ million floating-rate bond with quarterly resets might buy a floor with a strike price of. $2\%$ per annum. This would ensure that the reference interest rate each. quarter determining the interest payments received is at least $2\%$ per annum. If the. reference interest rate in the market for a particular quarter is greater than $2\%$ , there is no payoff for the quarter, but if this interest rate is less than $2\%$ , there is a payoff. designed to bring the effective reference interest rate up to $2\%$ per annum. For example, if the reference interest rate is $1.5\%$ per annum, the floor will provide a payoff of  

$$
0.25\times\S10,000,000\times(0.02-0.015)=\S12,500
$$  

LIBOR has traditionally been the most common reference rate in interest rate caps and floors. As LIBOR is phased out, it is likely that caps and floors based on reference rates calculated from overnight rates will become more popular (see Section 4.2). Here we present results for caps and floors where the reference rate is (like LIBOR) set in advance of a period. We then discuss possible adjustments to the models for reference rates based on overnight rates.  

# The Cap as a Portfolio of Interest Rate Options  

Consider a cap with a total life of $T$ , a principal of. $L$ , and a cap rate of $R_{K}$ . Suppose that. the reset dates are. $t_{1},t_{2},\ldots,t_{n}$ and define $t_{n+1}=T$ Define $R_{k}$ as the floating interest rate for the period between time. $t_{k}$ and $t_{k+1}$ observed at time $t_{k}$ $1\leq k\leq n$ ). The cap leads to a payoff at time. $t_{k+1}\left(k=1,2,\dots,n\right)$ of  

$$
L\delta_{k}\operatorname*{max}(R_{k}-R_{K},0)
$$  

where $\delta_{k}=t_{k+1}-t_{k}$ 2 Both $R_{k}$ and $R_{K}$ are expressed with a compounding frequency equal to the frequency of resets.  

Expression (29.5) is the payoff from a call option on the floating rate observed at time $t_{k}$ with the payoff occurring at time $t_{k+1}$ . The cap is a portfolio of $n$ such options. Rates are observed at times $t_{1},t_{2},t_{3},\ldots..,t_{n}$ and the corresponding payoffs occur at times $t_{2},t_{3},t_{4},\ldots,t_{n+1}$ The $n$ call options underlying the cap are known as caplets.  

# A Cap as a Portfolio of Bond Options  

An interest rate cap can also be characterized as a portfolio of put options on zerocoupon bonds with payoffs on the puts occurring at the time they are calculated. The payoff in expression (29.5) at time $t_{k+1}$ is equivalent to  

$$
\frac{L\delta_{k}}{1+R_{k}\delta_{k}}\operatorname*{max}(R_{k}-R_{K},0)
$$  

at time $t_{k}$ . A few lines of algebra show that this reduces to  

$$
\operatorname*{max}\biggl[L-\frac{L(1+R_{K}\delta_{k})}{1+R_{k}\delta_{k}},0\biggr]
$$  

The expression  

$$
\frac{L(1+R_{K}\delta_{k})}{1+R_{k}\delta_{k}}
$$  

is the value at time $t_{k}$ of a zero-coupon bond that pays off $L(1+R_{K}\delta_{k})$ at time $t_{k+1}$ . The expression in (29.6) is therefore the payoff from a put option with maturity $t_{k}$ on a zero-. coupon bond with maturity $t_{k+1}$ when the face value of the bond is $L(1+R_{K}\delta_{k})$ and the strike price is.. $L$ . It follows that an interest rate cap can be regarded as a portfolio of European put options on zero-coupon bonds.  

# Floors and Collars  

An interest rate floor is a portfolio of put options on interest rates or a portfolio of call options on zero-coupon bonds. Each of the individual options comprising a floor is known as a floorlet. A collar is an instrument designed to guarantee that the interest rate on an underlying floating-rate note always lies between two levels. A collar is a combination of a long position in a cap and a short position in a floor. It is usually constructed so that the price of the cap is initially equal to the price of the floor. The cost of entering into the collar is then zero.  

Business Snapshot 29.1 gives the put-call parity relationship between caps and floors.  

# Valuation of Caps and Floors  

As shown in equation (29.5), the caplet corresponding to the rate observed at time $t_{k}$ provides a payoff at time $t_{k+1}$ of  

$$
L\delta_{k}\operatorname*{max}(R_{k}-R_{K},0)
$$  

Under the standard market model, the value of the caplet is  

$$
L\delta_{k}P(0,t_{k+1})[F_{k}N(d_{1})-R_{K}N(d_{2})]
$$  

# Business Snapshot 29.1 Put-Call Parity for Caps and Floors  

There is a put-call parity relationship between the prices of caps and floors. This is  

Value of cap $=$ Value of floor $^+$ Value of swap  

In this relationship, the cap and floor have the same strike price, $R_{K}$ . The swap is an agreement to receive a floating rate, $R$ , and pay a fixed rate of $R_{K}$ with no exchange of payments on the first reset date.All three instruments have the same life and the same frequency of payments.  

To see that the result is true, consider a long position in the cap combined with a short position in the floor. The cap provides a cash flow of $R\mathrm{~-~}R_{K}$ for periods when $R$ is greater than. $R_{K}$ . The short floor provides a cash flow of $-(R_{K}-R)=R-R_{K}$ for periods when. $R$ is less than. $R_{K}$ . There is therefore a cash flow of $R\mathrm{~-~}R_{K}$ in all. circumstances. This is the cash flow on the swap. It follows that the value of the cap minus the value of the floor must equal the value of the swap.  

Note that LIBOR-for-fixed swaps are usually structured so that LIBOR at time. zero determines a payment on the first reset date. LIBOR-based caps and floors are. usually structured so that there is no payoff on the first reset date. The formula therefore needs adjustment when $R$ is a LIBOR rate.  

where  

$$
\begin{array}{l}{{d_{1}=\displaystyle\frac{\ln(F_{k}/R_{K})+\sigma_{k}^{2}t_{k}/2}{\sigma_{k}\sqrt{t_{k}}}}}\ {{d_{2}=\displaystyle\frac{\ln(F_{k}/R_{K})-\sigma_{k}^{2}t_{k}/2}{\sigma_{k}\sqrt{t_{k}}}=d_{1}-\sigma_{k}\sqrt{t_{k}}}}\end{array}
$$  

Here, $F_{k}$ is the forward interest rate at time O for the period between time $t_{k}$ and $t_{k+1}$ , and $\sigma_{k}$ is the volatility of this forward interest rate. This is a natural extension of Black's model. The volatility $\sigma_{k}$ is multiplied by $\sqrt{t_{k}}$ because the interest rate $R_{k}$ is observed at time $t_{k}$ , but the risk-free discount factor $P(0,t_{k+1})$ reflects the fact that the payoff is at time $t_{k+1}$ , not time $t_{k}$ . The value of the corresponding floorlet is  

$$
L\delta_{k}P(0,t_{k+1})[R_{K}N(-d_{2})-F_{k}N(-d_{1})]
$$  

# Example 29.3  

Consider a contract that caps an interest rate on. $\$10$ million at $8\%$ per annum (with quarterly compounding) for 3 months starting in 1 year. The interest rate is. observed at time 1 year and paid at time 1.25 years. This is a caplet and could be one element of a cap. Suppose that the forward interest rate for the period covered. by the caplet is $7\%$ per annum with quarterly compounding and the volatility of. this forward rate is. $20\%$ per annum. The continuously compounded risk-free zero rate for all maturities is. $6.5\%$ . In equation (29.7), $F_{k}=0.07$ $\delta_{k}=0.25$ $L=10$ $R_{K}=0.08$ $t_{k}=1.0$ $t_{k+1}=1.25$ $P(0,t_{k+1})=e^{-0.065\times1.25}=0.9220$ and $\sigma_{k}=0.20.$ Also,  

$$
{\begin{array}{l}{{d_{1}={\frac{\ln(0.07/0.08)+0.2^{2}\times1/2}{0.20\times1}}=-0.5677}}\ {{d_{2}=d_{1}-0.20=-0.7677}}\end{array}}
$$  

so that the caplet price (in $\$1$ millions) is.  

$$
0.25\times10\times0.9220[0.07N(-0.5677)-0.08N(-0.7677)]=0.00519
$$  

This result can also be obtained using the DerivaGem software accompanying this book.  

Each caplet of a cap must be valued separately using equation (29.7). Similarly, each. floorlet of a floor must be valued separately using equation (29.8). One approach is to use. a different volatility for each caplet (or floorlet). The volatilities are then referred to as spot volatilities. An alternative approach is to use the same volatility for all the caplets (floorlets) comprising any particular cap (floor) but to vary this volatility according to the life of the cap (floor). The volatilities used are then referred to as flat volatilities.' Flat volatilities are akin to cumulative averages of spot volatilities and are therefore less variable as a function of maturity. The volatilities quoted in the market are usually flat volatilities. However, many traders like to estimate spot volatilities because this allows them to identify underpriced and overpriced caplets (floorlets)..  

There is a smile or skew in the implied volatilities calculated from caplet/floorlet prices.. Some analysts choose to model this with the SABR model which was introduced in Section 27.2. This can be useful in managing the risks associated with smile movements..  

# Theoretical Justification for the Model  

The extension of Black's model used to value a caplet can be shown to be internally consistent by considering a world defined by a numeraire equal to a risk-free zero-coupon bond maturing at time $t_{k+1}$ . Section 28.4 shows that:  

1. The current value of any security is its expected value at time $t_{k+1}$ in this world multiplied by the price of a zero-coupon bond maturing at time $t_{k+1}$ (see equation (28.20).   
2. The expected value of a risk-free interest rate lasting between times $t_{k}$ and $t_{k+1}$ equals the forward interest rate in this world (see equation (28.22)).  

The first of these results shows that, with the notation introduced earlier, the price of a caplet that provides a payoff at time $t_{k+1}$ is  

$$
L\delta_{k}P(0,t_{k+1})E_{k+1}[\operatorname*{max}(R_{k}-R_{K},0)]
$$  

where $E_{k+1}$ denotes expected value in a world defined by a numeraire equal to a zerocoupon bond maturing at time $t_{k+1}$ When the forward interest rate underlying the cap (initially $F_{k}$ ) is assumed to have a constant volatility $\sigma_{k},R_{k}$ is lognormal in the world we are considering, with the standard deviation of $\ln(R_{k})$ equal to $\sigma_{k}\sqrt{t_{k}}$ . From equation (15A.1), the caplet price in equation (29.9) becomes  

where  

$$
\begin{array}{l}{{{\cal L}\delta_{k}P(0,t_{k+1})[E_{k+1}(R_{k})N(d_{1})-R_{K}N(d_{2})]}}\ {{\mathrm{}}}\ {{d_{1}=\displaystyle\frac{\ln{[E_{k+1}(R_{k})/R_{K}]}+\sigma_{k}^{2}t_{k}/2}{\sigma_{k}\sqrt{t_{k}}}}}\ {{d_{2}=\displaystyle\frac{\ln{[E_{k+1}(R_{k})/R_{K}]}-\sigma_{k}^{2}t_{k}/2}{\sigma_{k}\sqrt{t_{k}}}=d_{1}-\sigma_{k}\sqrt{t_{k}}}}\end{array}
$$  

The second result implies that  

$$
E_{k+1}(R_{k})=F_{k}
$$  

which leads to the result in equation (29.7). Note that the results we have used from Section 28.4 are correct when any yield curve is used to define $R_{k}$ and $F_{k}$ . (It does not have to be the risk-free yield curve underlying $P(0,t_{k+1})$  

# Use of DerivaGem  

The software DerivaGem accompanying this book can be used to price interest rate caps and floors using Black's model. In the Cap_and_Swap_Options worksheet select. Cap/Floor as the Underlying Type and Black-European as the Pricing Model. Forward rates for the underlying floating reference rate are input with a compounding frequency corresponding to the tenor. These are used to determine the. $F_{k}$ .Continuously compounded OIS rates are input to determine the discount factor $P(0,t_{k+1})$ . The inputs include the start and end date of the period covered by the cap, the flat volatility, and the cap settlement frequency (i.e., the tenor). The software calculates the payment dates by working back from the end of period covered by the cap to the beginning. The initial caplet/floorlet is assumed to cover a period of length between 0.5 and 1.5 times a regular period. Suppose, for example, that the period covered by the cap is 1.22 years to 2.80 years and the settlement frequency is quarterly. There are six caplets covering the periods. 2.55 to 2.80 years, 2.30 to 2.55 years, 2.05 to 2.30 years, 1.80 to 2.05 years, 1.55 to 1.80 years, and 1.22 to 1.55 years.  

# The Impact of Day Count Conventions  

The formulas we have presented so far in this section do not reflect day count conventions (see Section 6.1 for an explanation of day count conventions). Suppose that the cap rate $R_{K}$ is expressed with an actual/360 day count (as would be normal in. the United States). This means that the time interval. $\delta_{k}$ in the formulas should be replaced by $a_{k}$ , the accrual fraction for the time period between $t_{k}$ and $t_{k+1}$ . Suppose, for example, that $t_{k}$ is May 1 and $t_{k+1}$ is August 1. Under actual/360 there are 92 days between these payment dates so that $a_{k}=92/360=0.2556.$ The forward rate $F_{k}$ must be expressed with an actual/360 day count. This means that we must set it by solving.  

$$
1+a_{k}F_{k}={\frac{P(0,t_{k})}{P(0,t_{k+1})}}
$$  

The impact of all this is much the same as calculating $\delta_{k}$ on an actual/actual basis converting $R_{K}$ from actual/360 to actual/actual, and calculating $F_{k}$ on an actual/actual basis by solving  

$$
1+\delta_{k}F_{k}={\frac{P(0,t_{k})}{P(0,t_{k+1})}}
$$  

# Negative Rates  

Negative interest rates became a feature of financial markets in 2014. By the end of the first half of 2016, interest rates were negative for the Swedish krona, Danish krone, Japanese yen, euro, and Swiss franc. It was then estimated that more than. $\$10$ trillion of government bonds worldwide had negative yields..  

From an economics perspective, negative rates make no sense. (Why pay an entity to have use of your funds?) They also present a challenge to modelers. The standard. market model for valuing caps and floors assumes that the relevant future interest rate is lognormal so that it cannot become negative. One quick fix is to use what is known as the shifted lognormal model. In this, a future interest rate plus a spread, $\alpha$ , is assumed to be lognormal. Caps and floors can then be valued using equations (29.7) and (29.8) with $F_{k}$ replaced by $F_{k}+\alpha$ and $R_{K}$ replaced by $R_{K}+\alpha$ The shift $\alpha$ , when used with flat volatilities, sometimes depends on the cap/floor maturity. The SABR model can be. adjusted in a similar way to become a shifted SABR model.  

An alternative is to use the Bachelier normal model. In a world defined by the numeraire $P(0,t_{k+1})$ , the process for the forward rate underlying a caplet on the. $\left(t_{k},t_{k+1}\right)$ rate in the standard market model is assumed to be.  

$$
d F_{k}=\sigma_{k}F_{k}d z
$$  

where $d z$ is a Wiener process. In the Bachelier normal model, it is  

$$
d F_{k}=\sigma_{k}^{*}d z
$$  

Consistent with the equivalent martingale measure results in Chapter 28, both processes are martingales. The Bachelier model leads to a normal rather than. lognormal distribution for the underlying rate and so allows rates to become negative. Equation (29.7) for a caplet becomes  

$$
L\delta_{k}P(0,t_{k+1})[(F_{k}-R_{K})N(d)+\sigma_{k}^{*}\sqrt{t_{k}}N^{\prime}(d)]
$$  

and equation (29.8) for a floorlet becomes  

$$
L\delta_{k}P(0,t_{k+1})[(R_{K}-F_{k})N(-d)+\sigma_{k}^{*}\sqrt{t_{k}}N^{\prime}(d)]
$$  

where  

$$
d={\frac{F_{k}-R_{K}}{\sigma_{k}^{*}{\sqrt{t_{k}}}}}
$$  

and $N^{\prime}(x)$ is the normal distribution's density function (see equation (19.2)). Note that the volatility parameters, $\sigma_{k}$ and $\boldsymbol{\sigma}_{k}^{*}$ , in the two models are quite different. For. example, when the forward interest rate is $3\%$ $\sigma_{k}$ might be $33\%$ while $\boldsymbol{\sigma}_{k}^{*}$ is about $1\%$ Both the Bachelier normal and shifted lognormal models are implemented for caps, floors, and swaptions in DerivaGem 4.00.  

# Backward-Looking Reference Rates  

The analysis so far has assumed that the reference rate underlying a cap or floor is observed at the beginning of a period and paid at the end of the period. This is not the.   
case for reference rates based on overnight rates (see Section 4.2). A "quick and dirty".   
way of adjusting the models we have presented in (29.7) and (29.8) to value caps and.   
floors for these reference rates is to:.   
. Define $F_{k}$ as the forward rate calculated from the OiS zero curve for the period between t and tk+1:   
. Replace $t_{k}$ by $0.5(t_{k}+t_{k+1})$ in the definitions of $d_{1}$ and $d_{2}$  

This reflects the fact that the underlying one-day rates are, on average, observed halfway through the accrual period..  

When there is less than one accrual period until the reset date, some overnight rates that will comprise the next settlement rate have already been observed. These should be reflected in $F_{k}$ and $t_{k}$ should be replaced by the average of the times until the remaining one-day rates will be observed.  
