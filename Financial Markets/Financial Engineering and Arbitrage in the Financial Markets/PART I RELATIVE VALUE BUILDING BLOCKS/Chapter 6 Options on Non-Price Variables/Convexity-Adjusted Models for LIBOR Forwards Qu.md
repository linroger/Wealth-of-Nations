---
tags:
  - arrears_swap
  - convexity_adjustment
  - eurodollar_futures
  - libor_forwards
  - quanto_futures
  - swap_rates
  - yield_curve_bootstrap
aliases:
  - Black model
  - European structures
  - LIBOR/swap curve
key_concepts:
  - Convexity adjustment for pricing
  - Eurodollar futures
  - Quantoed futures contract
  - Swaps as convex instruments
  - Yield curve construction
---

# 6.2 CONVEXITY-ADJUSTED MODELS FOR LIBOR FORWARDS, QUANTOS, AND CONSTANT MATURITY SWAPS  

The Black model can be extended, but often requires a convexity adjustment, in order to correctly price European structures that, at first, seem to require an arbitrage-free term structure model. It can also be extended to handle structures that, at first, do not seem to require any option model, and yet they do. The first two examples of when we need a convexity adjustment are of the second variety and are the yield curve bootstrap itself and an arrears swap.  

When constructing the yield curve, we want to use the most liquid instruments as their price/rate is the most reliable, and the same most liquid instruments will probably be used to hedge. To build the LIBOR/swap curve that is used to price the majority of interest rate derivatives, we typically use the combination of Eurodollar (Euroyen, Eurosterling, or Euribor) futures up to 5, 7, or 10 years and swap rates afterwards. Swaps, which can be viewed as exchanges of bonds, are convex instruments, i.e. their PV is convex in the yield. Eurodollar futures are not; they pay $\$25$ per basis point. When building the yield curve with longer. expiring Eurodollar futures, we cannot ignore the fact that they are not identical to FRAs. The. forward LIBOR cannot be simply read off the futures quotes; it must be convexity-adjusted to produce the correct value equivalent to the rate that would be quoted on an FRA..  

An arrears swap  wherein the floating leg cash flows are set and paid at the beginning of each interest accrual period instead of being paid at the end -- is another non-option example of requiring a convexity adjustment. The forward discount bond price is convex in LIBOR. The model is risk neutral in the forward LIBOR with respect to the forward discount factor and will price correctly the LIBOR cash flow determined on the set date, paid 3 months later, discounted back to the set date and then back to today, but will not price correctly the LIBOR cash flow paid on the set date and discounted to today.  

The constant maturity swap (CMS), and options on it, are examples of where the same. convexity adjustment that is present, but small, in an arrears swap becomes a big issue. In an. arrears swap, the error comes from a 3-month mismatch; in the CMS options the mismatch between the set date of the swap rate (on the option expiry date) and the multiple payment. dates for the fixed leg over the life of the swap is very large. The unadjusted Black model, risk. neutral with respect to the numeraire annuity factor, will misprice the immediate settlement of a long swap rate.  

The last case we consider below is the quanto case, which is very common in currency. contexts. Quanto refers to assigning dollar values to non-native variables which cannot be bought and sold in dollars, like points of the Nikkei index with a multiplier defined in US dollars per index point. The hedger of a quanto structure is exposed to the cross movement of. the Nikkei index and the yen/dollar exchange rate, and the forward price of the index cannot be computed using a US dollar interest rate. The Black model using dollar financing numeraire. must have the index forward "convexity' adjusted..  

# 6.2.1  Convexity Adjustment for Eurodollar Futures  

Suppose we have bootstrapped discount factors out to the 3-year point and we want to use a Eurodollar futures contract on 3-month LIBOR expiring in 36 months to extend our yield curve to 39 months. Suppose the Eurodollar contract is quoted at 97.20, implying a LIBOR rate of $2.8\%$ for the period from 36 months to 39 months. However, the $2.8\%$ rate is not the same as the forward LIBOR rate, because the futures contract is a non-convex daily-settled arrangement. By the contract expiry date, the total mark-to-market settlement amounts will not be the same as those for settling an FRA that locks the forward $36\times39$ financing perfectly. In a short rate (normal) one-factor model (which assumes perfect correlation between the discount rates for the mark-to-market settlements and the future LIBOR rate), and ignoring the continuous-to-discrete Act/360 conversion, the convexity adjustment formula is:  

$$
L_{F}=L_{E D}-\frac{1}{2}\times L_{E D}^{2}\times\sigma^{2}\times T\times(T+t)
$$  

where $L_{F}$ is forward LIBOR (FRA equivalent), $L_{E D}$ is LIBOR implied in the Eurodollar futures quote, $\sigma$ is the log-normal volatility of the forward LIBOR rate, $T$ is the time to the. expiry of the future contract, and $t$ is the tenor of the LIBOR rate..  

In our $36\times39$ example, we set $T=3$ $\begin{array}{r}{t=\frac{1}{4}}\end{array}$ , and $L_{E D}=2.8\%$ . The last input we need is the implied volatility from Eurodollar futures options expiring in 3 years or from 3-year  

caplets/floorlets. Suppose the current implied volatility is $\sigma=30\%$ . Then the $36\times39$ forward 3-month LIBOR is computed as follows:  

$$
\begin{array}{l}{{{\cal L}_{F}=0.028-\frac{1}{2}\times0.028^{2}\times0.3^{2}\times3\times3\frac{1}{4}=0.028-0.000344}}\ {{\quad\quad=2.8\%-0.0344\%=2.7656\%}}\end{array}
$$  

The convexity adjustment for short futures expiries is small. In our 3-year example, it is only 3.5 bp. However, it grows quite rapidly, roughly with the square of the time. If we compute it for a 9-year futures expiry, keeping the rest of the inputs constant, we get 29.4 bp. Tripling the time produces a nine times larger convexity wedge.  

# 6.2.2 Convexity Adjustment for CMS Options  

Constant maturity options are caps or floors with long-term government (Constant Maturity Treasury CMT) or Constant Maturity Swap (CMS) rates as the underlying variables, but the day-count and frequency of payoff like that of a short rate. A 5-year quarterly cap on a 10-year. swap rate struck at $6\%$ pays the greater of zero and the difference between the 10-year rate and. the strike every quarter for the next 5 years. The day-count used for the payoff calculations is that of a given quarter and the payoff is made in arrears (at the end) just as for a simple caplet. The only difference between a straight cap and a CMS cap is that, instead of comparing. LIBOR to the strike, we compare the 10-year swap rate to the strike..  

This small difference is much bigger than it seems. With a standard LIBOR cap, the delta hedge instrument is a 3-month Eurodollar deposit, a forward or futures on it. We have learnt how to correct the yield curve to get the right number of futures in the hedge. That correction is relatively small too. With CMS caps/floors - as we compute the delta per 1 bp move in the forward swap rates, and then translate it through duration into a dollar holding of the underlying bond/swap -- our hedge will always be imperfect because of the mismatch (in each caplet) between the long tenor of the forward swap and the payment settlement of the caplet. only 3 months later. These hedging errors magnify the longer the hedge (on later caplets). On a 5-year maturity option, they can be very large in total. The CMT options have the added difficulty of swap spread exposure.  

CMS caps/floors appear to be more similar to swaptions than to caps. A swaption is a bet on a future long-term rate with the payoff multiplied by the appropriate annuity factor reflecting the final maturity of the underlying swap. A CMS cap can be seen as a series of swaptions with increasing maturities and with payoffs multiplied by an "inappropriate' annuity factor (for 3 months). Swaptions can be hedged easily with forward swaps synthesized from long long-maturity swaps and short short-maturity swaps, because the annuity factor in their payoff matches the forward swaps. CMS caps/floors cannot.  

Fortunately, the convexity correction for CMS caplets/floorlets is an easy generalization of the correction for Eurodollars, with the $(T+t)$ term replaced by the ratio of the second and first derivatives of the underlying forward bond price, i.e. roughly the ratio of the underlying bond's convexity to its duration (more precisely in price-value-of-a-basis-point terms). The ratio can be computed numerically by blipping the yield to maturity of the forward bond or closed-form for simple 30/360 fixed bonds.  

For a CMS caplet/floorlet on the. $t$ -year maturity swap rate $C M S_{t}$ expiring $T$ years from now, the convexity adjustment to the forward swap rate $C M S_{t}$ is:  

$$
-\frac{1}{2}\times C M S_{t}^{2}\times\sigma^{2}\times T\times\frac{P_{T,T+t}^{\prime\prime}}{P_{T,T+t}^{\prime}}
$$  

where $P_{T,T+t}^{\prime\prime}$ and $P_{T,T+t}^{\prime}$ are the second and frst derivatives of the price of the par coupon bond starting on the forward date. $T$ and maturing $t$ years later with respect to the yield to maturity.  

Let us go through a simplified example. We are pricing a 4-year caplet on the 10-year annual swap rate. The yield curve is flat at $6\%$ . The implied volatility on a European 4-into-10 swaption is $\sigma=20\%$ . The yield on the forward 10-year swap is the par rate on the forward 10-year fixed coupon bond and is equal to $6\%$ . We price the forward $6\%$ coupon bond to get its current price:  

$$
P=100
$$  

We approximate the first and second derivative numerically by blipping the yield by 1 bp. and using center difference approximations similar to the duration and convexity formulae of Chapter 2. The blips produce:  

$$
P_{+1b p}=99.926434,P_{-1b p}=100.073636
$$  

The derivatives are:  

$$
{\begin{array}{r l}&{P^{\prime}={\frac{P_{+1b p}-P_{-1b p}}{2b p}}={\frac{99.9264-100.0736}{0.02}}=-7.36}\ &{P^{\prime\prime}={\frac{100(P_{+1b p}-2P+P_{-1b p})}{(1b p)^{2}}}={\frac{100(99.9264-200+100.0736)}{0.0001}}=70}\end{array}}
$$  

The convexity adjustment to the CMS forward is:  

$$
{\frac{1}{2}}\times0.06^{2}\times0.20^{2}\times4\times{\frac{70}{7.36}}=0.002739=0.2739\%
$$  

We would use the rate of $6.274\%$ as an input into the convexity-adjusted Black model to price the 4-year caplet on the 10-year CMS rate.  

# 6.2.3 Quanto Adjustments  

Quantos are options whose payoffs are defined in non-native currencies. A seemingly standard put option on FTSE 100, whose payoff is in US dollars per point of the index, is quite a bit more complicated than that whose payoff is defined in British pounds. In the simpler pound. case, the hedge is obvious. The seller of the put shorts the stocks in the index. The total change in their value in pounds dynamically produces the pound payoff at expiry. The quanto version of the option forces the dealer into an additional currency hedge as the pound payoff needs to be guaranteed in dollars, and the two hedges are interrelated. As the potential payoff. in dollars rises because of the FTSE change, the underlying stock hedge pound value may over- or under-compensate for a possible FX rate change when the hedge is liquidated and the payoff made.  

The quanto feature can be added to almost any option. A popular equity option that pays the best of several national indexes, say S&P 500, Nikkei 225, and FTSE 100, is often quantoed into one desired currency, say the euro. Futures are sometimes quantoed too, and require an adjustment when pricing relative to the non-quantoed cousins.  

The quanto adjustment follows from the change of numeraire argument in the risk-neutral. world and in continuous time it is equal to: $I_{Q}=I\times e^{\rho\sigma_{I}\sigma_{F X}T}$ where $I$ is the spot value of the index (Nikkei), $\rho$ is the correlation of the Nikkei returns and forward yen/dollar FX rate percentage changes, $\sigma_{I}$ is the log-normal volatility of the Nikkei (implied from standard Nikkei. options), $\sigma_{F X}$ is the log-normal volatility of the forward yen/dollar FX rate, and. $T$ is the time to the quanto option expiry date in years. The result is the quanto-adjusted value of the index. $I_{Q}$ to be input into the Black-Scholes model. To compute the fair value of a quantoed-into-dollars Nikkei futures contract, we would further subject it to the cash-and-carry spot-forward link. using the yen interest rate and Nikkei dividend yield..  

Suppose the Nikkei is at 11,050, 6-month options on the Nikkei imply a volatility of $\sigma_{I}=20\%$ , 6-month FX options on the yen/dollar rate imply $Q_{F X}=10\%$ , and the correlation between the Nikkei and the FX rate is $\rho=0.15$ . To price 6-month quanto options on the Nikkei, we first adjust the spot index input:  

$$
I_{Q}=11,050\times e^{0.15\times0.2\times0.1\times0.5}=11,066.59
$$  

We can compute the forward quanto-adjusted value of the index using the standard parity relationship. If the semi-annual 6-month yen LIBOR is. $1.2\%$ and the dividends are zero, then,. ignoring the Act/360 convention, the forward Nikkei is equal to:.  

$$
I_{Q}^{F}=I_{Q}(1+{^{L}}/{_{2}})=11,066.59\times1.006=11,132.99
$$  

This forward Nikkei is the fair value of a quantoed futures contract and it is also the input we would use in a Black model with the dollar LIBOR rate as the risk-free rate.  
