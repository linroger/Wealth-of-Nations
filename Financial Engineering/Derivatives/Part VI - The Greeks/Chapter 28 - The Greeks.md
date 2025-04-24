---
tags:
  - at_the_money
  - black_scholes
  - bopm_model
  - delta_hedging
  - gamma_hedging
  - option_greeks
  - option_pricing
  - portfolio_management
  - underlying_asset
  - volatility
aliases:
  - Delta-Gamma Hedging
  - Greeks
  - Option Sensitivities
  - Portfolio Delta
key_concepts:
  - 'BOPM: Greek calculation'
  - Black-Scholes formula
  - 'Delta hedging: small price changes'
  - Delta-gamma-vega hedging
  - 'Gamma hedging: large price changes'
  - 'Greeks: delta, gamma, rho, vega'
  - 'Greeks: option price approximation'
---
# The Greeks  

# Aims  

• To show how ‘the Greeks’ (e.g. delta, gamma, rho, vega, and theta) provide useful ‘summary statistics’ for options, which can be used to provide an approximation to the change in the option price.   
• To show how the Greeks are used to protect the value of an options portfolio from small changes (delta hedging) and large changes (delta-gamma hedging) in the price of the underlying asset.   
• To demonstrate how the Greeks are used to protect the value of an options portfolio from large and small changes in the underlying asset’s price, when the latter is also accompanied by (small) changes in volatility – this is ‘gamma-vega-delta’ hedging.   
• To demonstrate how to calculate ‘the Greeks’ for the BOPM.  

# 28.1 DIFFERENT GREEKS  

The Black–Scholes formula (on a non-dividend paying stock) shows that the option premium varies with $S,r,\sigma,T$ , all of which may change minute by minute. In this chapter we show how the change in price of the option can be represented in terms of a number of ‘summary statistics’ which are generally referred to as ‘the Greeks’. Knowing the numerical values for the various ‘Greeks’ also allows an options trader to set up efective hedge positions for her portfolio of options. As we shall see, the more sources of uncertainty the options trader wants to hedge (stocks, interest rates, volatility) and the smaller the desired hedging error, the more complex the trader’s hedging strategy needs to be.  

# 28.1.1 Portfolio Delta  

Suppose you have a portfolio of n options consisting of $N_{i}$ calls and puts (with diferent strikes and time to maturity) but on the same underlying stock (e.g. Microsoft). The portfolio delta of the options is defned as:  

$$
\Delta_{p o r t}=\sum_{i=1}^{n}N_{i}\Delta_{i}
$$  

We take $N_{i}>0$ if you are long ( $\mathbf{\bar{\rho}}=\mathbf{\bar{\rho}}$ buy) a call or put and $N_{i}<0$ if you are short $\scriptstyle(=\mathbf{sell})$ a call or put.  

# EXAMPLE 28.1  

# Delta of Portfolio  

Ms Smart is long (i.e. holds) 1,000 puts (on AT&T) with strike of $K=100$ and time to maturity of 3 months. Each (long) put has a delta of –0.4. Ms Smart has also written (sold) 2,000 calls (on AT&T) with a strike of $K=90$ and time to maturity of 6 months. Each (long) call has a delta of $+0.3$ .  

$$
\Delta_{p o r t}=\left(1,000\right)\left(-0.4\right)+\left(-2,000\right)\left(+0.3\right)=-400-600=-1.000
$$  

If the stock price of AT&T goes up by $\$1$ , then the value of Ms Smart’s portfolio of options will fall by $\$1,000$ (approximately). The 1,000 long puts will fall in value by $\$400$ . Also, 2,000 long calls will rise in value by $\$600$ and therefore Ms Smart’s 2,000 written calls will fall by $\$600$ . Ms Smart is efectively ‘short options’ $(\Delta_{p o r t}=-1,000)$ – if the stock price rises the value of her options portfolio will fall.  

To delta hedge her portfolio of AT&T options Ms Smart will go long (i.e. buy) 1,000 stocks, today. If the stock price goes up by $\$1$ over the next day then her stocks increase in value by $\$1,0000$ , which (approximately) ofsets the loss of around $\$1,000$ on her portfolio of options. She is delta hedged.  

# 28.1.2 Gamma  

In the following sections we denote the derivatives price as $f$ so our remarks will apply to either call or put options. The gamma of an option is defned as:  

$$
\Gamma\equiv\partial^{2}f/\partial S^{2}=\partial\Delta/\partial S
$$  

![](af83619ebab817b79aeee3a86846bfad84c0391e6a064dd91636c5d974944c1e.jpg)  
FIGURE 28.1 Delta and gamma – long call  

Gamma is the second derivative of the option price with respect to the stock price.1 Gamma is also the change in the option’s delta as $s$ changes by a small amount $\Gamma\equiv\partial\Delta/\partial S$ , hence:  

Gamma (like delta) takes on diferent values for diferent values of $S,r,\sigma,T,K$ . The relationship between gamma and the stock price (other variables held constant) is roughly ‘bell shaped’ and the maximum value for gamma occurs when the current stock price is close to the strike price – that is, for a ‘near-ATM’ option (Figure 28.1).  

# EXAMPLE 28.2  

# Delta and Gamma  

Suppose today an option has a $\Delta=0.5$ and $\Gamma=0.05$ . Then if $d S=+\$2$ over the next day, the (approximate) change in delta will be $0.1(=0.05\times\$\Phi2)$ and the new delta will be 0.6. Hence, if you are delta hedging, you will have to increase your holdings of stocks by approximately $+0.1$ to maintain a delta-hedged position.  

If $S=K=50$ and the stock price changes by a small amount (e.g. $\$1$ ), the slope of the Black–Scholes curve (i.e. the option’s delta) will not change by very much, say from 0.5 to 0.53, giving a gamma of 0.03. (However, note that the value of gamma for an ATM option which is also ‘close to maturity’ can be much larger than this – see below.)  

Clearly Figure 28.1 shows that when a call is either very $(S\gg K)$ or very OTM $(S\ll K)$ then $\Gamma$ is small and fairly constant (if the stock price changes by a small amount). This implies that for OTM and ITM options, a delta hedge will work quite well even if you do not rebalance very frequently (e.g. every 5 days), since a small gamma means that delta does not change very much as $s$ changes, from day to day.  

In contrast, for an option that is currently ATM (i.e. $S\approx K,$ ) then gamma can be relatively large and vary a great deal as $s$ changes (Figure 28.1). A large gamma alerts an options trader who is delta hedging her position, that to remain delta hedged she will probably have to rebalance her portfolio frequently (e.g. twice per day). Alternatively she can ‘eliminate’ the current large value of gamma by ‘gamma hedging’ – see below.  

The value for gamma is obtained from the Black–Scholes equation for European options (on a stock paying continuous dividends):  

$$
\Gamma\left(c a l l o r p u t\right)=\frac{N^{\prime}(d_{1})^{e-\delta T}}{S\sigma\sqrt{\mathrm{T}}}\geq0\quad\mathrm{where}\quad N^{\prime}(x)=\frac{e^{-x^{2}/2}}{\sqrt{2\pi}}\geq0
$$  

Gamma is positive for either a long call or a long put. Also the gamma for a call is equal to the gamma for a put option (with the same underlying asset, strike price, and time to maturity). To obtain a ‘negative gamma’ you must sell (write) calls or puts.  

Gamma is useful when calculating the change in the option price for a large change in the stock price – using gamma is sometimes referred to as a ‘curvature adjustment’. A delta-hedged position does not give protection against large changes in the stock price. This can be seen by noting that the change in the option premium can be approximated by a second-order Taylor series expansion of the option price (with respect to $S$ ):  

$$
d f\approx\left({\frac{\partial f}{\partial S}}\right)d S+{\frac{1}{2}}\left({\frac{\partial^{2}f}{\partial S^{2}}}\right)(d S)^{2}\approx\Delta d S+{\frac{1}{2}}\Gamma(d S)^{2}
$$  

The change in the option price depends on both delta and gamma – as can be seen in Example 28.3.  

# EXAMPLE 28.3  

# Delta-Gamma Approximation  

If a call option has $\Delta=0.5$ , $\Gamma=0.05$ and $d S=+\$3$ then the change in the call premium calculated using only the delta is $+\$1.5$ . But to obtain a more accurate value for df, we use both delta and gamma:  

$$
d f\approx0.5\left(3\right)+\left(1/2\right)\left(0.05\right)\left(+3\right)^{2}=1.5+0.225=\S1.725.
$$  

The change in the call premium df (for one call) using the delta-gamma approximation is $\$1.725$ and using only the delta approximation is $\$1.5$ – a diference of $\$0.225$ $(=15\%$ of the delta change of $\$1.5$ ). For 10,000 long calls this diference amounts to $\$2,250$ . The fgure of $\$1.725$ is a more accurate measure of the ‘true’ change in the option price than using only delta. (But remember that the ‘true’ or ‘correct’ change in the option price is given by the Black–Scholes formula.)  

For small changes in $s$ (e.g. $\$0.1$ , the change in call premium using just delta is $\$0.05$ and using the gamma term $\Gamma(d S)^{2}/2=0.00025$ makes little diference. An option’s ‘gamma risk’ only becomes quantitatively important when the change in the stock price is relatively large (or the gamma for a portfolio of options is large – see below).  

# 28.1.3 Portfolio Gamma  

The gamma for a portfolio of options (with diferent strikes and time to maturity but on the same underlying stock) is defned as:  

$$
\Gamma_{p o r t}=\sum_{i=1}^{n}{N_{i}\Gamma_{i}}
$$  

# EXAMPLE 28.4  

# Portfolio Gamma  

Ms Smart has sold (written) 10,000 puts (on a stock) which each have a gamma of 0.10 and she holds 1,000 calls each with a gamma of 0.05. The portfolio gamma is:  

$$
\Gamma_{p o r t}=\left(-10,000\right)\left(0.10\right)+1,000\left(0.05\right)=-1,000+50=-950.
$$  

Suppose Ms Smart has taken a position in stocks such that the delta of her options $+$ stocks portfolio is now zero. Then if the stock price moves up or down by $\$3$ , the value of her portfolio will fall by about $\S4,275\left(=(1/2)\left(-950\right)3^{2}\right)$ . Hence, even if Ms Smart is delta hedged, but her portfolio has a large negative gamma, she loses money if the stock price moves either up or down by a substantial amount. Traders who have delta hedged their options portfolio should ‘beware’ of any large ‘gamma exposure’.  

If Ms Smart’s options portfolio is delta hedged (i.e. $\Delta_{p o r t}=0\dot{}$ ) but the gamma of the portfolio of options is large, then the portfolio will not be hedged against ‘large’ changes in the stock price. But if Ms Smart can form a ‘new portfolio’ of stocks and options which makes both the portfolio delta and the portfolio gamma equal to zero, then she is protected from both small and large changes in the stock price – this is ‘delta-gamma’ hedging and is discussed below.  

Note that the ‘gamma of a stock’ is zero – this is because the value of a stock is linear in the stock price. If $V_{s}=N_{s}S$ then $\partial V_{s}/\partial S=N_{s}$ and $\partial^{2}V_{s}/\partial S^{2}=0$ .  

# 28.1.4 Theta  

The change in the option premium due to the passage of time is non-stochastic and is measured by the option’s theta (see Appendix 28):  

$$
\theta=\partial f/\partial t\quad{\mathrm{hence}}\quad d f=\theta d t
$$  

In the Black–Scholes formula ‘time’ is measured in years or fractions of a year and when discussing theta we can take $d t=\mathrm{\cdot}1$ trading day’, so $d t=1/252=0.004$ (years) or we can measure theta per calendar day $(d t=1/365)$ . The option’s theta depends on the current stock price, time to maturity, stock volatility, and interest rate.  

Theta is usually negative for most long positions in options – both long calls and long puts lose value as they get closer to maturity (all other variables held constant). Theta is most negative for options that are nearly ATM, so ATM options lose time value rather quickly, day by day. Alternatively, if the current stock price is very low then theta is close to zero (for calls and puts). When the time to maturity is short (e.g. few weeks to maturity) the value of theta for ITM, OTM and especially for ATM options can become relatively large – so these options all lose time value relatively quickly (all other variables held constant).  

# EXAMPLE 28.5  

# Theta  

Suppose a long call option has $\theta=-8$ which implies that each day it loses ‘time value’. The approximate fall in the price of the call (all other variables held constant) over 1 trading day (i.e. $d t=1/252=0.004)$ is $d C=\theta d t=-8$ 0.004 0.032 (3.2 cents per trading day) or 2.19 cents per calendar day. As the option gets closer to maturity, the time decay (per day) for the call becomes more severe.  

For example, for the same option with 1 week to maturity (and all other variables held constant) we might have $\theta=-20$ , so that the call premium would fall by 0.08 (8 cents) per trading day (ceteris paribus). If we wish to measure the change in the option premium per calendar day, then we repeat the above with $d t=1/365$ .  

Note that as ‘time’ is deterministic, the theta of the option is not used in any kind of hedging as there is no uncertainty. Theta is useful as an estimate of the change in value of the option over time. There is another more esoteric use for theta. It can be shown (using the Black–Scholes partial diferential equation [PDE], see Chapter 48) that for $\$V$ in a portfolio of options on a single underlying asset with current price $s$ the following holds, $\theta+r S\Delta+(1/2)\sigma^{2}S^{2}\Gamma=r V$ . For a delta-neutral portfolio we have:  

$$
\theta+(1/2)\sigma^{2}S^{2}\Gamma=r V
$$  

This shows that for a delta-neutral portfolio, when theta is large and positive the gamma tends to be large and negative – so here theta is also an indication of the gamma-risk in the options portfolio.  

# 28.1.5 Rho  

The change in the option price due to a change in $r$ is known as ‘rho’, $\rho=\partial f/\partial r$ . For call and put options (for both a dividend paying and non-dividend paying stock):  

$$
\begin{array}{r l}&{\mathrm{Call}\colon\rho_{c}=T K e^{-r T}N(d_{2})>0}\\ &{\mathrm{Put}\colon\rho_{p}=-T K e^{-r T}N(-d_{2})>0}\end{array}
$$  

In the Black–Scholes pricing formula, $r$ is entered as a decimal. Hence, a change in interest rates of $1\%$ is entered as $d r=0.01$ in the formula $d f=\rho d r$ .  

# EXAMPLE 28.6  

Rho  

A long call has $\rho_{c}=27$ . If interest rates increase over 1 day from $3\%$ to $3.5\%$ , that is, by $^1/_{2}\%\left(+0.005\right)$ , then the call premium increases by $d C=\rho_{c}d r=27\left(0.005\right)=$ $\$0.135$ 13.5 cents .  

Theta and rho are the ‘lesser Greek Gods’ since usually the option premium is not particularly sensitive to either changes in $r$ or changes in the time to maturity.  

# 28.1.6 Vega  

The change in the option’s premium for a small change in volatility $\sigma$ , is measured by the option’s vega $\Lambda$ :  

$$
\Lambda=\frac{\partial f}{\partial\sigma}
$$  

‘Vega’ is not a Greek letter and ‘vega’ is also referred to as lamda, kappa, or sigma, which are Greek letters. The numerical value of vega is the same for a long call or long put (with same strike, time to maturity, and underlying stock) and has a bell shape with respect to the stock price (Figure 28.2). To obtain a ‘negative vega’ you must sell (write) calls or puts.  

![](f0eb11f446cc8a0a28290cad9b747460a81164fd7adc64b38940c1695d6d0463.jpg)  
FIGURE 28.2 Vega (long call or put)  

If the vega of an option is large this implies the option price is highly sensitive to small changes in volatility $\sigma$ . For a European option on a stock, the vega is large when the option is close to being at-the-money (i.e. $S\approx K,$ ) and is zero for options that are well OTM or well ITM (Figure 28.2). The analytic expression for the vega of a European (call or put) option on a stock (or stock index) paying a continuous dividend yield $\delta$ is:  

$$
\mathrm{Call\(Put)}\ V e g a,\Lambda=S\sqrt{T}\ N^{\prime}(d_{1})e^{-\delta T}\geq0\qquad\mathrm{where\}N^{\prime}(x)=\frac{e^{-x^{2}}}{\sqrt{2\pi}}\geq0
$$  

Strictly speaking, using the Black–Scholes vega to hedge against changes in volatility $\sigma$ of the underlying asset is inconsistent – as the Black–Scholes model assumes volatility is constant – but this approach seems to work reasonably well in practice (i.e. even when volatility is stochastic). It should be obvious that the vega of a stock is zero – this is because the value of a stock portfolio does not depend on the stock’s volatility (if $V_{s}=N_{s}S$ then $\partial V_{s}/\partial\sigma=0,$ ).  

# EXAMPLE 28.7  

# Vega  

The vega of a long call is $+20$ and you have just sold a call for $\$3$ . The market’s view of volatility increases over the next day by $1\%$ , from $\sigma=25\%$ p.a. to $\sigma=26\%$ p.a. The change in the value of the written call over one-day is:  

$$
d C=(-1)\Lambda d\sigma=-20(+0.01)=-0.2(20\mathrm{cents}).
$$  

The (approximate) price of the call, the next day is $\$2.8$ (assuming $S,r$ are constant).  

Explicit expressions for ‘the Greeks’ can be obtained if we have a closed-form solution for the option premium. These are given in Appendix 28 for European calls and puts (on a stock that pays a continuous dividend yield), based on the Black–Scholes equation. Using the Greeks enables an options trader to hedge her existing portfolio of options either from small or large changes in the price of the underlying asset, or from changes in volatility and changes in interest rates.  

# 28.1.7 Approximating Option Price Changes  

The Greeks also provide a convenient way of fnding the approximate change in the option premium $d f,$ as all the variables $S,r,t,\sigma$ change. A Taylor series expansion f the equation for the (Black–Scholes) option price $f=f(S,r,t,\sigma)$ is:  

$$
{\begin{array}{r l}&{d f\approx\left({\frac{\partial f}{\partial S}}\right)d S+{\frac{1}{2}}\left({\frac{\partial^{2}f}{\partial S^{2}}}\right)(d S)^{2}+{\frac{\partial f}{\partial\sigma}}d\sigma+{\frac{\partial f}{\partial r}}d r+{\frac{\partial f}{\partial t}}d t+h i g h e r o r d e r t e r m}\\ &{\qquad\simeq\Delta d S+{\frac{1}{2}}\Gamma(d S)^{2}+\Lambda.d\sigma+\rho.d r+{\theta.d t}}\end{array}}
$$  

where $d S=$ change in the stock price, etc. This is also a useful expression for calculating the approximate change in the option price $d f,$ once we have any reasonable way of obtaining estimates of the Greeks (e.g. from an approximate closed-form option pricing equation, from MCS or from the BOPM).  

Note also, that the values for all the Greeks change over time as the values of $S,\sigma,r$ and time to maturity $t$ , change. For example, a portfolio of options which currently has $\Gamma=0$ will not represent a gamma-neutral position some time later because as $S,\sigma,t$ and $r$ change over time, so does the option’s gamma, .  

# 28.2 HEDGING WITH THE GREEKS  

# 28.2.1 Portfolio of Options  

Suppose you have a portfolio of $n$ options consisting of $N_{i}$ calls and puts (with diferent strikes and time to maturity) but on the same underlying stock (e.g. Microsoft). The delta, gamma, and vega of the portfolio of options are:  

$$
\Delta_{p o r t}=\sum_{i=1}^{n}N_{i}\Delta_{i}\qquad\Gamma_{p o r t}=\sum_{i=1}^{n}N_{i}\Gamma_{i}\qquad\Lambda_{p o r t}=\sum_{i=1}^{n}N_{i}\Lambda_{i}
$$  

• $N_{i}>0$ if long (buy) a call or put • $N_{i}<0$ if short (sell) a call or put  

• $\Delta_{i}>0$ for long call (from Black–Scholes) • $\Delta_{i}<0$ for long put (from Black–Scholes)  

Also, each long stock has a delta of $+1$ $\left({\partial S/\partial S}=+1\right)$ and a gamma and vega of zero. If you hold (buy) stocks then $N_{s}>0$ and if you short-sell stocks $N_{s}<0$ .  

# 28.2.2 Gamma Neutral  

The gamma for Microsoft stock (or futures on the stock) are both zero. So, the only way you can change the gamma of an existing options portfolio on several Microsoft calls and puts is to take new positions in some other options on Microsoft. Suppose you already have a portfolio-A, of several calls and puts on Microsoft which have a portfolio delta of $\Delta_{A}$ and gamma of $\Gamma_{A}$ . If you now add a further $N_{Z}$ traded options on Microsoft (with diferent strike prices and maturity dates) into your existing options portfolio-A, then the gamma of this new portfolio is:  

$$
\Gamma_{n e w}=N_{Z}\Gamma_{Z}+\Gamma_{A}
$$  

Your new portfolio is gamma-neutral $\Gamma_{n e w}=0$ when:  

$$
N_{Z}=-\Gamma_{A}/\Gamma_{Z}
$$  

But including $N_{Z}$ additional options will also alter the overall portfolio’s delta. Hence we then buy or sell a number of Microsoft stocks (or futures contracts on Microsoft stock) to make the overall options portfolio delta neutral. An example is given in Example 28.8.  

# EXAMPLE 28.8  

# Delta-Gamma-Neutral Portfolio  

Portfolio-A: Call and put options on Microsoft stock, with diferent strikes and maturity dates:  

Portfolio-delta, $\Delta_{A}=500$ . Portfolio-gamma $\Gamma_{A}=-300$  

Other call options $(Z)$ on Microsoft are available, which for simplicity we assume all have the same strike prices $K_{M i c r o}$ and time to maturity, $T_{M i c r o}$ . Each of these Microsoft options-Z has:  

$$
\Delta_{Z}=0.6\quad\mathrm{~and~}\quad\Gamma_{Z}=0.03.
$$  

To make our existing portfolio-A, gamma neutral:  

$$
\begin{array}{l}{{N_{Z}\Gamma_{Z}+\Gamma_{A}=0}}\\ {{N_{Z}=-\Gamma_{A}/\Gamma_{Z}=-(-300)/0.03=+10.000}}\end{array}
$$  

We buy 10,000 of options-Z on Microsoft (each with $K_{M i c r o}$ and $T_{M i c r o,}\mathrm{~,~}$ ).  

The delta of our ‘new’ portfolio (i.e. options-A and options-Z, all on Microsoft stock) is now:  

$$
\Delta_{n e w}=\Delta_{A}+N_{Z}\Delta_{Z}=500+10,000(0.6)=6,500
$$  

Hence to establish delta neutrality we short-sell 6,500 Microsoft stocks.  

Note that as time passes $S,\sigma,r$ and $T$ change, hence so do gamma and delta – therefore periodic rebalancing is required to maintain delta-gamma neutrality.  

Kurpiel and Roncalli (1998) fnd that (in a Black–Scholes constant volatility world) when you just delta hedge a call option with rebalancing over either {5, 1, 1/2} days, the percentage hedging error is $\%H E=\{0.25,0.15,0.1\}^{2}$ whereas with a delta-gamma hedge these fgures improve to $\%H E=\{0.08,0.03,0.02\}$ , which are ‘reasonable’ even when rebalancing takes place only every 5 days.  

# 28.2.3 Vega Neutral  

The vega of an existing options portfolio on Microsoft can only be altered by adding another traded option on Microsoft to the existing portfolio. Suppose we initially hold a portfolio of Microsoft stocks with a portfolio vega of $\Lambda_{A}$ and another option-X on Microsoft is available with a vega $\Lambda_{X}$ . To obtain a vega-neutral position we require $N_{X}$ options which satisfy:  

$$
\Lambda_{n e w}=N_{X}\Lambda_{X}+\Lambda_{A}=0
$$  

hence  

$$
N_{X}=-\Lambda_{_A}/\Lambda_{_X}
$$  

Our new portfolio will not be delta neutral but we know that if we now take a position in Microsoft stocks, we can also achieve delta neutrality. For daily rebalancing in a stochastic volatility world, Kurpiel and Roncalli (2009) report an improvement in hedge performance as we move from purely delta hedging with $\%H E=0.20-0.25\%$ , to delta-vega hedging where $\%H E=0.135\%$ . However, we still have a potential problem because our delta-vega neutral portfolio may have a non-zero gamma and therefore may not be protected against large changes in the stock price.  

# 28.2.4 Gamma-Vega-Delta Neutral  

A gamma-vega-delta neutral position implies that the value of the portfolio is (nearly fully) protected against small or large changes in the stock price and against small changes in the stock’s volatility.  

Suppose we have a portfolio-A of options on Microsoft which is already vega neutral but has a gamma of $\Gamma_{p}\neq0$ . How can we simultaneously achieve gamma and vega neutrality? At frst sight it may seem as if we just include $N_{X}=-\Gamma_{p}/\Gamma_{X}$ new options-X (on Microsoft) to achieve gamma neutrality. However, this is incorrect, as adding the new options-X destroys our initial vega neutrality, because the new $N_{X}$ options themselves have non-zero vegas. To achieve a delta-gamma-vega neutral portfolio we proceed in two steps:  

• First, we include ‘new’ options on Microsoft (with diferent strike prices and maturity dates and hence diferent gammas and vegas) to our original portfolio-A (of Microsoft options), so that we simultaneously achieve gamma-vega neutrality. • Second, we go long or short Microsoft stocks to make our ‘new’ options portfolio delta neutral – this will not alter our ‘new’ gamma-vega neutrality because stocks have a gamma and a vega of zero.  

An example of setting up a ‘delta-gamma-vega’ neutral position is given in Example 28.9.  

# EXAMPLE 28.9  

# Delta-Gamma-Vega Neutral  

You currently hold a Portfolio-A of options on Microsoft:  

Portfolio-A $\Delta_{a}=-500~\Gamma_{a}=-5,000~\Lambda_{a}=-4,000$ Also:  

Option- Microsoft is available with ${\Delta_{y}}=0.6,{\Gamma_{y}}=0.05,{\Lambda_{y}}=15$ Option- Microsoft is available with $\Delta_{z}=0.5,\ \Gamma_{z}=0.10,\ \Lambda_{z}=10$  

First, use options Y and $Z$ (on Microsoft) to give a portfolio which is simultaneously ‘gamma-vega’ neutral.  

# Gamma-vega neutrality  

$$
\begin{array}{r l}&{\Gamma_{a}+N_{y}\Gamma_{y}+N_{z}\Gamma_{z}=0\qquad-5,000+N_{y}\left(0.05\right)+N_{z}(0.10)=0}\\ &{\Lambda_{a}+N_{y}\Lambda_{y}+N_{z}\Lambda_{z}=0\qquad-4,000+N_{y}(15)+N_{z}(10)=0}\end{array}
$$  

Hence: $N_{z}=+74{,}800$ (i.e. buy options-Z) and $N_{y}=-49{,}600$ (i.e. sell options-Y)  

# New portfolio delta:  

$$
\Delta_{a}-49,600~\Delta_{y}+74,800~\Delta_{z}=-500-49,600(0.6)+74,800(0.5)=+7,140
$$  

Second, use Microsoft stocks to achieve delta neutrality. This requires short-selling 7,140 Microsoft stocks.  

The value of your ‘fnal options and stocks’ position consists of your initial portfolio-A of several options on Microsoft (with diferent strikes and time to maturity) plus our new positions in options-Y and options-Z (on Microsoft) which give gamma-vega neutrality, and fnally short-selling Microsoft stocks to achieve delta neutrality. Your new positions in options and stocks means that your ‘fnal portfolio’ is now hedged against small (delta) and large (gamma) changes in S and also against (small) changes in volatility (vega).  

# 28.2.5 Frequency of Rebalancing  

A long call or a long put on a stock (with the same strike price and maturity) have the same positive values for either gamma or vega. Short calls and puts have negative gamma and vega. Although options traders might frequently rebalance their portfolios to maintain delta neutrality, they generally do not rebalance often to maintain gamma and vega neutrality, since it may be difcult to fnd appropriate ‘ofsetting options’ at competitive prices. They therefore adjust their options position to give gamma and vega neutrality only after these ‘Greeks’ become unacceptably large. However, their portfolio of options positions will usually be monitored daily and their potential vulnerability to possible changes in either stock prices or volatility (of stock returns) will be calculated – this is the subject of Chapter 46 on risk measurement.  

The options trading desks of many banks mainly write calls and puts for their clients and hence build up negative gamma and negative vega positions, in the normal course of trading. They therefore often step in as buyers of options when these are available at competitive prices, in order to reduce their gamma-vega exposures. Because an option’s vega and gamma are large when the options are close to ATM, an options dealer may gamma-vega (and delta) hedge a portfolio of ATM options under these circumstances, even when the options have a considerable time to maturity.  

It is also the case that the gamma and vega for ATM options which are close to expiration are exceptionally large and hence the options trader may consider a gamma-vega (and delta) hedge, if she holds options that are both ATM and close to expiration. A trader who initially sells ATM calls and puts and delta hedges her position hopes that the options will become well OTM or ITM, since then the vega and gamma become very small (Figure 28.2) and there may be no need to undertake costly gamma-vega hedging.  

A portfolio of futures options (e.g. options on AT&T futures contracts) can be used together with futures contracts (on AT&T stocks) in implementing dynamic delta hedging. An existing portfolio of futures options-A (e.g. on AT&T futures contracts) can be combined with other futures options-B (on AT&T futures contracts, but with diferent strikes and time to maturity) to simultaneously produce a gamma-neutral and vega-neutral portfolio. Finally, one can use futures contracts (on AT&T) to achieve a portfolio which is gamma-vega-delta neutral.  

As we have seen, if you hold a portfolio of options on AT&T stocks then you can gamma-vega-delta hedge using other options (written on AT&T stock) together with the AT&T stocks themselves. However, because the stock price and the futures price move closely together you can also gamma-vega-delta hedge a portfolio of options (on AT&T stocks), using options on futures contracts of AT&T – together with futures contracts on AT&T stocks (to ensure delta neutrality).  

# 28.3 GREEKS AND THE BOPM  

Suppose we do not have a closed-form solution like Black-Scholes for option premia but we wish to calculate ‘the Greeks’ for a specifc option. We have already seen this in the context of MCS. Now we examine the calculation of the Greeks in the BOPM.  

Suppose we construct a lattice for the stock price and a $T=1$ year option, with $n=52$ steps, so that each time period corresponds to 1 week $(d t=T/n=1/52$ years) and $U=e^{\sigma{\sqrt{d t}}}$ and $D=e^{-\sigma{\sqrt{d t}}}$ . How can we determine the Greeks so that if we currently hold an option, we can hedge against delta, gamma and vega risk?  

There are two ways of doing this. The frst is to apply the perturbation approach used in the MCS in Chapter 26. Suppose the current stock price is $S_{0}$ $(=100)$ and we calculate the call premium $C_{0}$ (under RNV) using backward recursion in the binomial tree. To fnd the option’s delta we perturb the initial stock price by a small amount $h=1$ , say, so that $S_{0}^{+}=S_{0}+h$ is the new initial stock price. We keep everything else unchanged and produce a new tree using $S_{u}^{+}=S_{0}^{+}U$ etc., and calculate the new price for the option $C_{0}^{+}$ . The delta of the option is then calculated as $\Delta^{+}=(C_{0}^{+}-C_{0})/(S_{0}^{+}-S_{0})=(C_{0}^{+}-C_{0})/h.$ . The option’s vega and rho can be calculated in a similar way.  

If we want to fnd the option’s gamma (which is the change in the delta as $s$ changes by a small amount) we repeat our calculation for delta but this time using a lattice which starts of with $S_{0}^{-}=S_{0}-h$ . Suppose for this lattice we obtain a call premium equal to $C_{0}^{-}$ so that our new $\Delta^{-}=(C_{0}^{-}-C_{0})/(S_{0}^{-}-S_{0})=(C_{0}^{-}-C_{0})/(-h).$ . Then gamma is given by the change in delta:  

$$
\Gamma=(\Delta^{+}-\Delta^{-})/h=(C^{+}-2C+C^{-})/h^{2}
$$  

The second way of proceeding is to directly calculate (some of) the Greeks using only the initial tree for $S$ and the tree for the option premium $f$ . Defne the stock price at each node of the tree as $S_{t,i}$ . We designate $i$ as the number of ‘up’ moves in the lattice (e.g. for $U U,i=2{\dot{z}}$ . A ‘down’ move is denoted $\cdot\mathrm{{0^{\cdot}}}$ (which geometrically is represented as a horizontal move – Figure 28.3). Thus at $t=2,S_{u d}$ becomes $S_{21}$ where the ‘1’ represents the number of ‘up’ moves. We also have a similar lattice for the values of the option price $f_{t,i}$ obtained via backward recursion (under RNV). Use of this notation allows the lattice to be represented in computer programs.  

![](8b83800905a486a24c3775aaa3f2d32d8c8da19989c762e8b7459ff619318c01.jpg)  
FIGURE 28.3 BOPM lattice  

At $t=0$ we calculate the option’s delta at node $(0,0)$ using:  

$$
\Delta_{00}=\frac{f_{11}-f_{10}}{S_{11}-S_{10}}
$$  

To estimate gamma, note that we have two estimates of $\Delta$ at $t=1$ :  

$$
\Delta_{11}=\frac{f_{22}-f_{21}}{S_{22}-S_{21}}~\mathrm{and}~\Delta_{10}=\frac{f_{21}-f_{20}}{S_{21}-S_{20}}
$$  

The values of $s$ that correspond to these values of $\Delta$ are calculated as follows. The average value of $S$ in the upper and lower parts of the lattice (at $t=2$ ) are $S^{*}=(S_{22}+S_{21})/2$ and $S^{**}=$ $(S_{21}+S_{20})/2$ . Hence their diference is:  

$$
\lambda=[(S_{22}+S_{21})-(S_{21}+S_{20})]/2=(S_{22}-S_{20})/2
$$  

We can now calculate gamma at $t=0$ , as the change in delta divided by the ‘distance’ between our two measures of delta:  

$$
\Gamma_{0,0}=\frac{\Delta_{11}-\Delta_{10}}{\lambda}
$$  

Even though our estimates of $\Delta$ and $\Gamma$ require the use of nodes at $t=1$ and $t=2$ , it is assumed that these represent $\Delta$ and $\Gamma$ at $t=0$ , because the time interval $d t$ in the lattice is  

small. We can make $d t$ as small as we like so we can also obtain estimates of $\Delta$ at $t=0$ by approximating the derivatives at other nodes (time periods). For example, using values at $t=2$ an estimate of $\Delta$ is:  

$$
\Delta=\frac{f_{22}-f_{20}}{S_{22}-S_{20}}
$$  

An estimate of the option’s theta $\theta=\partial f/\partial t$ (i.e. $t=1$ held constant) is easily obtained by interpolating between the frst two nodes at $t=1$ . The average value of the option at $t=1$ is $(f_{11}+f_{10})/2$ and hence an estimate of $\theta$ is3:  

$$
\theta=\frac{(f_{11}+f_{10})/2-f_{00}}{d t}
$$  

An estimate of vega requires two trees as in any single tree, $\sigma$ is constant and $U=e^{\sigma{\sqrt{d t}}}$ and $D=1/\mathrm{U}$ are constant. Hence we must use the perturbation approach. We choose a new value for sigma $\sigma^{*}=\sigma+h$ (where $h$ is small) and calculate new values for $U$ and $D$ and hence a ‘new tree’ for the stock price. We keep $d t=T/n,r,K,S_{0}$ and $T$ unchanged and calculate the ‘new’ option price using backward recursion on the new tree. If the new option price is $f^{*}$ , the option’s vega is:  

$$
\Lambda=\frac{f^{*}-f}{\sigma^{*}-\sigma}
$$  

The option’s rho can be calculated in a similar way to vega by changing the risk-free rate by a small amount (and keeping dt, n, U, $D$ the same as in the original tree) which gives $\rho=(f^{*}-f)/(r^{*}-r)$ .  

# 28.4 SUMMARY  

• Delta hedging one written (sold) call, requires a long position in $\Delta_{c}$ stocks. Delta hedging one long (buy) call, requires short-selling $\Delta_{c}$ stocks. Hence, delta hedging calls requires a long-short position.   
• Delta hedging one long (buy) put, requires a long position in $|\Delta_{p}|$ stocks. Delta hedging one written (short) put, requires short (selling) $|\Delta_{p}|$ stocks. Delta hedging puts requires a long-long position or short-short position.   
• Delta is a measure of the sensitivity of option premia to small changes in the price of the underlying stock. The Greek, ‘rho’ measures the sensitivity of option premia to small changes in interest rates, the option’s vega to small changes in volatility and theta to small changes in the time to maturity. The gamma of an option measures the sensitivity of option premia to large changes in the price of the underlying stock.   
• The Greeks can be calculated from any (approximate) closed-form solution for the option price (e.g. Black–Scholes) or alternatively by numerical methods using the BOPM or MCS.   
• ‘The Greeks’ allow an options trader to construct a hedge portfolio whose value is (largely) unafected by small changes in $s,\sigma$ , and $r$ . If the options trader also gamma hedges then the options portfolio is also hedged against large changes in S. In practice, rebalancing takes place at discrete intervals so there is always some risk in any dynamic hedge.   
• If an options trader wishes to hedge against both small and large changes in the stock price $s$ and against (small) changes in volatility then she must frst buy and sell stock options to simultaneously make the options portfolio ‘gamma and vega neutral’ and second, buy or sell the underlying stocks to make the portfolio delta neutral.  

# APPENDIX 28: BLACK–SCHOLES AND THE GREEKS  

The Black–Scholes formula for the price of a European call option on a stock which pays a continuous dividend yield at a rate $\delta$ (per annum) can be obtained by taking the Black–Scholes equation for an option on a non-dividend paying stock and replacing S by 𝐻푒𝑛𝜆𝐸.  

Call and Put Premia: European Options, Dividend Paying Stock  

For calls and puts on a stock (index) paying continuous dividends:  

$$
\begin{array}{c}{{C=S e^{-\delta T}N(d_{1})-K e^{-r T}N(d_{2})}}\\ {{{}}}\\ {{P=K e^{-r T}N(-d_{2})-S e^{-\delta T}N(-d_{1})}}\end{array}
$$  

Since $\ln(S e^{-\delta T}/K)=\ln(S/K)-\delta T$ then:  

$$
\begin{array}{l}{{d_{1}=\displaystyle\frac{\ln(S/K)+(r-\delta+\sigma^{2}/2)T}{\sigma\sqrt{T}}}}\\ {{d_{2}=d_{1}-\sigma\sqrt{T}=\displaystyle\frac{\ln(S/K)+(r-\delta-\sigma^{2}/2)T}{\sigma\sqrt{T}}}}\end{array}
$$  

$C,(P)=$ call (put) premium $T=$ time to maturity (years, fractions of a year) $S=$ stock price $\delta=$ dividend yield (continuously compounded, proportionate, $4\%=0.04\AA,$ ) $\sigma=$ standard deviation of stock return, (proportionate) $r=$ risk-free rate (continuously compounded, proportion)  

Delta: $\Delta=\partial f/\partial S$ Call Delta: $\Delta_{c}=\partial C/\partial S=e^{-\delta T}N(d_{1})$ Put Delta: $\Delta_{p}=\partial P/\partial S=e^{-\delta T}(N(d_{1})-1)$   
Gamma: $\Gamma=\partial^{2}\mathrm{f}/\partial\mathrm{S}^{2}$  

Call Gamma $\c=$ Gamma: $\Gamma=\frac{N^{\prime}(d_{1})e^{-\delta T}}{S\sigma\sqrt{\mathrm{T}}}\geq0$ where $N^{\prime}(x)=\frac{e^{-x^{2}/2}}{\sqrt{2\pi}}\ \geq0$  

Vega: $\Lambda=\partial f/\partial\sigma$ $\mathrm{CallVega}=\mathrm{PutVega};\qquad\Lambda=S\sqrt{T}\ N^{\prime}(d_{1})e^{-\delta T}\ge0$  

Rho: $\rho=\partial f/\partial r$ (for both a dividend paying and non-dividend paying stock)  

Call: $\rho_{c}=T K e^{-r T}N(d_{2})>0$ Put: $\rho_{p}=-T K e^{-r T}N(-d_{2})>0$  

Theta $\theta=\partial f/\partial T$ :  

# a. Non-dividend paying stock  

$$
\theta_{c}=\frac{-S N^{\prime}(d_{1})\sigma}{2\sqrt{T}}-r K e^{-r T}N(d_{2})>0
$$  

$$
\theta_{p}=\frac{-S N^{\prime}(d_{1})\sigma}{2\sqrt{T}}+r K e^{-r T}N(-d_{2})>o r<0
$$  

Note that $T=$ ‘time to maturity’ and therefore as the call gets closer to maturity, $T$ falls. It can be shown that as the option approaches the maturity date, theta increases and the call premium becomes more sensitive to changes in ‘time’ – the call loses time-value more quickly.  

# b. Dividend paying stock  

$$
\theta_{c}(w i t h d i v i d e n d s)=\frac{-S N^{'}(d_{1})\sigma e^{-\delta T}}{2\sqrt{T}}-r K e^{-r T}N(d_{2})+\delta S N(d_{1})e^{-\delta T}
$$  

$$
\ni_{p}(w i t h d i v i d e n d s)=\frac{-S N^{'}(d_{1})\sigma e^{-\delta T}}{2\sqrt{T}}+r K e^{-r T}N(-d_{2})+\delta S N(-d_{1})e^{-\delta T}>o r\ .
$$  

In the above formulas time is measured in years. For example, if $\theta=-20$ , then the change in price of the option over 2 trading days is $-20(2/252)=-0.16$ (16 cents).  

Theta is usually negative for a long position in an option – as time passes the option becomes less valuable – this is ‘time decay’. However, there are some (pathological) cases where theta can be positive – for example, for an ITM European put on a non-dividend paying stock or an ITM European call on a currency that pays a high interest rate.  

If we set $\delta=0$ in any of the above formulas then we will obtain the Black–Scholes ‘Greeks’ for an option on a non-dividend paying stock.  

# Options on Foreign Currency and Options on Futures  

The above formulas for options on dividend paying stocks can be easily adapted to apply to European options on foreign currencies and European options on futures. The changes required are:  

# Foreign currency options:  

Replace $\delta$ with the foreign interest rate $r_{f}$ , $S={\mathrm{spot}}$ exchange rate and $\sigma=$ volatility of the spot FX-rate. There are two rhos, one with respect to the domestic interest rate which is given above and one with respect to the foreign interest rate $\delta=r_{f}$ which is given by:  

$\rho=\partial f/\partial r_{f}$ Call: $\rho_{c}=-T e^{-r_{f}T}S N(d_{1})>0$ Put: $\rho_{p}=-T e^{-r_{f}T}N(-d_{1})>0$  

# Futures option:  

Replace $\delta$ by $r$ (so that $r$ ‘disappears’ from the defnition of $d_{1}$ and $d_{2}$ ), replace $s$ by $F$ (the futures price, with the same expiration date as the option) and $\sigma$ is the volatility of the futures price.  

# EXERCISES  

# Question 1  

Brie\$y explain the concept of the delta of a portfolio of options (on the same underlying asset).  

# Question 2  

What is the vega of an option and why is it useful?  

# Question 3  

How does the gamma of a long call vary as the price of the underlying (stock) changes around the strike price? What are the risk management implications after selling an ATM call with a high gamma?  

# Question 4  

Suppose portfolio-A, which consists of several options, is delta neutral but has a gamma of minus 300. A call option-Z on the same underlying stock is available which has a delta of 0.62 and a gamma of 1.5.  

How can you use option-Z and any stocks you might buy or sell to make your overall portfolio gamma and delta neutral?  

# Question 5  

You are a trader (market maker) who supplies clients with whatever calls or puts they want to buy or sell. At the end of the trading day you have a portfolio of (long and short) calls and put options on Microsoft stock and on AT&T stock. Carefully explain to your risk manager what additional trades you are immediately going to do, to hedge your current options positions over the next 3 days. What are the costs in setting up your hedged postion?  

# Question 6  

You hold a Portfolio-A of options with the following Greeks:  

$$
\Delta_{a}=-450,\qquad\Gamma_{a}=-6,000,\qquad\Lambda_{a}=-4,000
$$  

( $\textstyle\left(\Lambda_{a}$ is the vega of the option). Option $\mathbf{\{}^{\circ}}Z^{\prime}$ is available with $\Delta_{z}=0.6,\Gamma_{z}=1.5,\Lambda_{z}=0.8$ and option $\mathrm{{}^{\circ}Y^{\prime}}$ is available with $\Delta_{y}=0.1,\Gamma_{y}=0.5$ and $\Lambda_{y}=0.6$ .  

Explain how you can combine options A, $\mathrm{Y}$ and $z$ to give a portfolio which is ‘gamma, vega and delta neutral’.  

# Question 7  

In the BOPM how do you calculate the gamma of an option at $t=0?$  