# 15.5 VARIANCE SWAPS  

One instrument that has invariant exposure to fluctuations in (realized) variance is the variance swap. In this section, we introduce this concept and in the next, we provide a simple framework for studying it.  

A variance swap is, in many ways, just like any other swap. The parties exchange floating risk. against a risk fixed at the contract origination. In this case, what is being swapped is not an interest. rate or a return on an equity instrument, but the variances that correspond to various risk factors.  

# 15.5.1 USES AND USERS OF VARIANCE SWAPS  

Before we study the hedging and pricing of variance swaps it is instructive to think about what the jotential uses of variance swaps are.  

# 15.5.1.1 Uses of variance swaps  

We can distinguish several uses and users of variance swaps. First, some users may be interested in variance swaps as a way of directionally trading variance levels. This could be for hedging or spec-. ulative purposes. Market participants who would like to speculate on the future levels of stock or index variance or volatility can go long or short realized variance with a variance swap. The advantage of such a position over trading and hedging options is that the variance swap is not contaminated by other risk exposures. If an investor expects a sharp decline in political and financial uncertainty after a forthcoming election, for example, a short position in a variance swap may be a. good way to express this view and profit from it..  

Second, some investors may use the variance swap to trade the spread between realized and. implied variance levels. As we will see below, the fair strike price. $F_{t_{0}}$ in a variance swap is related to the level of current-implied volatilities for options with the same expiration as the swap.. Therefore, by unwinding the swap before expiration, a market participant can trade the spread between realized and implied volatility.  

# 15.5.1.2 Market participants with an implicit volatility exposure to hedge  

We can think of at least three groups of market participants with an implicit volatility exposure to hedge. Some event-driven hedge funds engage in merger arbitrage and take positions that assume that the spread between an acquirer and takeover target will narrow. The risk is, however, that if overall market volatility increases the merger may be less likely and the spread may widen leading to loses for merger arbitrage hedge funds.  

Some institutional investors that follow active benchmarking strategies regularly rebalance their portfolios. In volatile periods such rebalancing may need to be more frequent, thus leading to higher portfolio turnover and transaction costs. Independent from transaction costs, higher volatility may also lead to increased tracking error for portfolio managers who are judged against a benchmark. As asset prices move quickly, they may not be able to track the benchmark as effectively as when volatility is low.  

Standard equity funds could be argued to be short volatility since there is a negative empirical correlation between equity market levels and volatility as we will see below. Thus, as global equity correlations rise, diversification across securities and countries becomes less effective. The GFC represents a recent example of many such turbulent periods during which most assets fall, but variances tends to rise, thus leading to a potential hedge.  

The three market participants listed above could all benefit potentially from long positions in variance swaps to hedge their exposures and reduce portfolio risk..  

In the following section, we move to a more technical discussion of variance swaps. However, we emphasize again that the discussion will proceed using the variance rather than the volatility as the underlying.  

# 15.5.2 A FRAMEWORK FOR VARIANCE SWAPS  

Let $S_{t}$ be the underlying price. The time- $T_{2}$ payoff $V\left(T_{1},T_{2}\right)$ of a variance swap with a notional amount, $N.$ is given by the following:.  

$$
V(T_{1},T_{2})=\bigg[\sigma_{T_{1},T_{2}}^{2}-F_{t_{0}}^{2}\bigg](T_{2}-T_{1})N
$$  

where $\sigma_{T_{1},T_{2}}$ is the realized volatility rate of $S_{t b}$ during the interval $t\in[T_{1},T_{2}]$ with $t<T_{1}<T_{2}$ . It is similar to a "floating" rate, and will be observed only when time $T_{2}$ arrives. The. $\boldsymbol{F}_{t_{0}}$ is the "fixed". $S_{t}$ volatility rate that is quoted at time $t_{0}$ by markets. This has to be multiplied by $(T_{2}-T_{1})$ to get the appropriate volatility for the contract period. $N$ is the notional amount that needs to be determined at contract initiation. At time $t_{0}$ the $V(T_{1},T_{2})$ is unknown. The swap is set so that the time- $\cdot t_{0}$ "expected value" of the payoff, denoted by $V(t_{0},T_{1},T_{2})$ is zero. At initiation, no cash changes hands:  

$$
V(t_{0},T_{1},T_{2})=0
$$  

Thus, variance swaps are similar to a vanilla (interest rate) swap in that a "floating" $\sigma_{T_{1},T_{2}}^{2}(T_{2}-T_{1})N$ is received against a "fixed" $(T_{2}-T_{1})F_{t_{0}}^{2}N$  

The cash flows implied by a variance swap are shown in Figure 15.8. The contract is initiated at time $t_{0}$ and the start date is $T_{1}$ . It matures at $T_{2}$ . The "floating" volatility (variance) is the total. volatility (variance) of $S_{t}$ during the entire period $[T_{1},T_{2}].F_{t_{0}}$ has the subscript $t_{0}$ , and, hence, has to be determined at time $t_{0}$  

![](images/5151adc062e5b2a184c15c07823e6dbae512206a25699a9fd1c59021c9c67d85.jpg)  

# FIGURE 15.8  

Variance swap cash flows.  

# 15.5.2.1 Real-world example of a variance swap  

Below we provide a real-world example of a variance swap.  

# EXAMPLE: VARIANCE SWAP ON S&P5OO-SPX INDICATIVE TERMS AND CONDITIONS  

<html><body><table><tr><td>Instrument:</td><td>Swap</td></tr><tr><td>Variancebuyer:</td><td>TBD (e.g.,JPMorganChase)</td></tr><tr><td>Variance seller:</td><td>TBD (e.g., Investor)</td></tr><tr><td>Denominatedcurrency:</td><td>USD</td></tr><tr><td>Vega amount:</td><td>100,000</td></tr><tr><td>Varianceamount:</td><td>3125 (determined as vega amount/(strike× 2))</td></tr><tr><td>Underlying:</td><td>S&P500(Bloomberg ticker:SPXindex)</td></tr><tr><td>Strike price Kvol:</td><td>16</td></tr><tr><td>Equity amount:</td><td>T + 3 after the observation end date, the Equity Amount will be calculated and paid in accordancewith thefollowingformula:</td></tr></table></body></html>  

Final Equity payment $=$ variance amount $\times$ (final realized volatility2 -- strike price?)  

If the Equity Amount is positive the Variance Seller will pay the Variance Buyer the Equity Amount. If the Equity Amount is negative the Variance Buyer will pay the Variance Seller an amount equal to the absolute value of the Equity Amount, where  

$$
{\mathrm{Final~realized~volatility}}={\sqrt{\frac{252\times\sum_{t=1}^{t=N}\left(\ln(P_{t}/P_{t-1})\right)^{2}}{{\mathrm{Expected}}_{-}N}}}\times100 
$$  

and  

Expected_ $N=$ [number of days], being the number of days which, as of Trade Date, are expected to be Scheduled Trading Days in the Observation Period $P_{0}=$ The Official Closing of the underlying at the Observation Start Date $P_{t}=$ Either the Official Closing of the underlying in any observation date tor, at Observation End Date, the Official Settlement Price of the Exchange-Traded Contract.  

(Bossu et al. (2005))  

The terms and conditions of the variance swap contract show that if realized variance is higher than the strike price $K_{\mathrm{vol}}$ the variance buyer will receive a payment from the variance seller.. Similar to other derivative contracts, variance swaps can be used for hedging or speculation. Let's consider an example in which the contract is used for hedging purposes. The variance buyer buys the variance swap as insurance, that is, for the purpose of hedging against unexpected. increases in variance. Why would the variance buyer want to hedge against variance increases?. The variance buyer (i.e., JPMorganChase, here) might have, for example, issued structured equity. products with a capital guarantee to retail investors and now wants to hedge the structured product by means of a variance swap. The capital guarantee protects the retail investor against losses. The structured product could consist of an equity market exposure and a capped downside. JPMorganChase could use a long position in a put option on the index, or if it is cheaper, a long. position in a variance swap to generate the cash flow to pay for the capital guarantee. When stock. markets plunge variances and correlations tend to increase. The variance contract term sheets show a strike price $K_{\mathrm{vol}}$ of 16, that is a volatility of 16. A stock market plunge might occur in a scenario. when the realized volatility is (substantial) above 16. The variance buyer (JPMorganChase) could buy, that is go long, the variance swap. Who would be the counterparty? The "Investor' could be a. hedge fund for example. We could economically interpret the transaction as JPMorganChase buying insurance from the hedge fund against unexpected increases in variance.  

In line with market practice the variance notional is defined in volatility terms:  

$$
\mathrm{Variancenotional}=\frac{\mathrm{veganotional}}{2\times K_{\mathrm{vol}}}
$$  

The vega amount is $\$100,000$ (which implies a variance amount of $\$3125(=\$100,000$ $(2\times16),$ . The implication of the above adjustment is that when the realized volatility is 1 "vega" or 1 volatility point above the strike at maturity, the payoff is approximately equal to the Vega Notional.  

In the variance swap term sheet, it is interesting to observe that returns are calculated on a logarithmic basis and that the mean return is assumed to be zero for simplicity which means that the payoff is perfectly additive: 6-month $+6$ month variance $=1$ month variance.  

If the index realizes a $20\%$ volatility over the next year, for example, the Variance Buyer-the long position-will receive $\begin{array}{r}{\sqrt{450,000}\stackrel{cdot}{=}3I25\times(R e a l i\dot{z}e d~\nu o l a t i l i t y^{2}\stackrel{-}{-}K_{\nu o l}{}^{2})=3I25\times(20\dot{^{2}}-I6^{2}).}\end{array}$ This could be interpreted as a realized insurance payout from the hedge fund to JPMorganChase. Why would the hedge fund enter into such a transaction as a counterparty? As we will see below, historically, the implied variance (the fixed leg) has been above the realized variance (floating leg)  

on average. For example, if the index only realizes. $12\%$ , the long will pay $\$350,000$ (Realized volatility $^{2}-\overset{\cdot}{K}_{\nu o l}{}^{2})=3{\cal I}25\times({\cal I}2^{2}-{\cal I}6^{2})$ to the seller. Here JPMorganChase would pay the investor or hedge fund $\$350,000$ 7 This could be interpreted as an insurance premium. In the past over certain time periods it was possible for a hedge fund to earn a substantial risk or insur-. ance premium by selling variance swaps or being short variance swaps. This is by no means a risk-. less trade, however, since in crises times, the realized volatility tends to exceed and rise above the implied volatility.  

Figure 15.9 shows the floating and fixed leg for a S&P500 variance swap contract from 1996 to. 2014. The contract is for 30-day variance. The floating leg is based on the realized variance and  

![](images/a3baef602c2ecbcc6e36dfae480d49ee35b8ac8afefe3895bfc13f1028a65bec.jpg)  

# FIGURE 15.9  

Floating and fixed leg for a S&P500 variance swap contract.  

the fixed leg is based on the implied variance. As we can see the implied variance was above the. realized variance for most of the pre-GFC and post-GFC period. This highlights the insurance premium that a variance seller could have pocketed for selling variance swaps..  

However, the variance seller would have made large losses during the GFC. As the figure illustrates, on September 29, 2008, the realized variance reached a level of 0.70 while implied variance was O.13. Many trading desks and hedge funds that were short variance in 2008 suffered substantial losses and some were forced to close. Note that variance swaps were traded as OTC contracts and no historical data from exchange traded variance contracts are currently available. Therefore, the plot is based on synthetic variance swap contracts based on S&P500 index options and Optionmetrics volatility surface data.  

Figure 15.9 also illustrates an important feature of volatility, which is its tendency to revert to the mean. If we were to compare the volatility plot to the realized return of the S&P500 we would also see that equity volatility is negatively correlated with the equity index and tends to rise in times of elevated uncertainly or risk.  

# 15.5.2.2 Real-world conventions  

As the term sheet illustrates it is important for counterparties to agree the procedure for calculating the realized volatility, in particular, the sources and the frequency of the price of the underlying as. well as the annualization factor used in moving from daily to annual volatilities. It also matters whether the standard deviation is calculated by subtracting the sample mean from each return, or. by assuming a zero return. The zero mean method has theoretical advantages since it corresponds most closely to the contract that can be replicated by means of option portfolios..  

# 15.5.2.3 Floating leg  

Variance (volatility) positions need to be taken with respect to a well-defined time interval. After. all, the volatility rate is like an interest rate: It is defined for a specific time interval. Thus, we subdivide the period $[T_{1},T_{2}]$ into equal subintervals, say, days:  

$$
T_{1}=t_{1}<t_{2}\cdots<t_{n}=T_{2}
$$  

with  

$$
t_{i}-t_{i-1}=\delta
$$  

and then define the realized variance for period $\delta$ as  

$$
\sigma_{t_{i}}^{2}\delta=\left[{\frac{S_{t_{i}}-S_{t_{i-1}}}{S_{t_{i-1}}}}-\mu\delta\right]^{2}
$$  

where $i=1,...,n$ . Here, $\mu$ is the expected rate of change of $S_{t}$ during a year. This parameter can be set equal to zero or any other estimated mean. Regardless of the value chosen, $\mu$ needs to be carefully defined in the contract. If. $\mu$ is zero, then the right-hand side is simply the squared returns. during intervals of length $\delta$  

Adding the marginal variances for successive intervals, $\sigma_{T_{1},T_{2}}^{2}$ is equal to  

$$
\left(\sigma_{T_{1},T_{2}}^{2}\right)(T_{2}-T_{1})=\sum_{i=1}^{n}{\left[\frac{S_{t_{i}}-S_{t_{i-1}}}{S_{t_{i}}}-\mu\delta\right]}^{2}
$$  

Thus, $\sigma_{T_{1},T_{2}}^{2}$ represents the realized percentage variance of the $S_{t}$ during the interval $[T_{1},T_{2}]$ If the intervals become smaller and smaller, $\delta\to0$ , the last expression can be written as  

$$
\begin{array}{c}{{\displaystyle\Big(\sigma_{T_{1},T_{2}}^{2}\Big)(T_{2}-T_{1})=\int_{T_{1}}^{T_{2}}\left[\frac{1}{S_{t}}\mathrm{d}S_{t}-\mu\mathrm{d}t\right]^{2}}}\ {{=\displaystyle\int_{T_{1}}^{T_{2}}\sigma_{t}^{2}\mathrm{d}t}}\end{array}
$$  

This formula defines the realized variance. It is a random variable at time. $t_{0}$ , and can be viewed as the floating leg of the swap. Obviously, such floating variances can be defined for any interval in the future and can then be exchanged against a "fixed' leg.  

# 15.5.2.4 Determining the fixed variance  

Determining the fixed volatility, $\boldsymbol{F}_{t_{0}}$ , will give the fair value of the variance swap at time. $t_{0}$ . How do we obtain the numerical value of. $F_{t_{0}}$ ? We start by noting that the variance swap is designed so. that its fair value at time $t_{0}$ is equal to zero. Accordingly, the $F_{t_{0}}^{2}$ is that number (variance), which makes the fair value of the swap equal zero. This is a basic principle used throughout the text and it applies here as well.  

We use the fundamental theorem of asset pricing and try to find a proper arbitrage-free measure $\tilde{P}$ such that  

$$
E_{t_{0}}^{\tilde{P}}\Big[\sigma_{T_{1},T_{2}}^{2}-F_{t_{0}}^{2}\Big](T_{2}-T_{1})N=0
$$  

What could this measure $\tilde{P}$ be? Suppose markets are complete.  

We assume that the continuously compounded risk-free spot rate $r$ is constant. The random pro-. cess $\sigma_{T_{1},T_{2}}^{2}$ is, then, a nonlinear function of $S_{u}$ $T_{1}\leq u\leq T_{2}$ , only:  

$$
\sigma_{T_{1},T_{2}}^{2}(T_{2}-T_{1})=\int_{T_{1}}^{T_{2}}\left[\frac{1}{S_{t}}{\mathrm{d}}S_{t}-\mu{\mathrm{d}}t\right]^{2}
$$  

Under some conditions, we can use the normalization by the money market account and let $\tilde{P}$ be the risk-neutral measure.10 Then, from Eq. (15.41), taking the expectation inside the brackets and arranging, we get  

$$
F_{t_{0}}^{2}=E_{t_{0}}^{\tilde{P}}\bigg[\sigma_{T_{1},T_{2}}^{2}\bigg]
$$  

This leads to the pricing formula  

$$
F_{t_{0}}^{2}=\frac{1}{T_{2}-T_{1}}E_{t_{0}}^{\tilde{P}}\left[\int_{T_{1}}^{T_{2}}\left[\frac{1}{S_{t}}\mathrm{d}S_{t}-\mu\mathrm{d}t\right]^{2}\right]
$$  

Therefore, to determine. $F_{t_{0}}^{2}$ we need to evaluate the expectation under the measure $\tilde{P}$ of the integral of $\sigma_{t}^{2}$ . The discrete time equivalent of this is given by.  

$$
F_{t_{0}}^{2}=\frac{1}{T_{2}-T_{1}}E_{t_{0}}^{\tilde{P}}\left[\sum_{i=1}^{n}\left[\frac{S_{t_{i}}-S_{t_{i-1}}}{S_{t_{i-1}}}-\mu\delta\right]^{2}\right]
$$  

Given a proper arbitrage-free measure, it is not difficult to evaluate this expression. One can use Monte Carlo or tree methods to do this once the arbitrage-free dynamics are specified.  

# 15.5.3 A REPLICATING PORTFOLIO  

The representation using the risk-neutral measure can be used for pricing. But how would we hedge a variance swap? To create the right hedge, we need to find a replicating portfolio. We discuss this issue using an alternative setup. This alternative has the side advantage of the financial engineering interpretation of some mathematical tools being clearly displayed. The following model starts with Black-Scholes assumptions.  

The trick in hedging the variance swap lies in isolating $\sigma_{T_{1},T_{2}}^{2}$ in terms of observable (traded) quantities. This can be done by obtaining a proper synthetic. Assume a diffusion process for $S_{t}$  

$$
\mathrm{d}S_{t}=\mu(S_{t},t)S_{t}\mathrm{d}t+\sigma(S_{t},t)S_{t}\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

where $W_{t}$ is a Wiener process defined under the probability. $\tilde{P}$ . The diffusion parameter $\boldsymbol{\sigma}(\boldsymbol{S}_{t},t)$ is :alled local volatility. Now consider the nonlinear transformation:  

$$
Z_{t}=f(S_{t})=\log(S_{t})
$$  

We apply Ito's Lemma to set up the dynamics (i.e., the SDE) for this new process $Z_{t}$  

which gives  

$$
\mathrm{d}Z_{t}=\frac{\partial f(S_{t})}{\partial S_{t}}\mathrm{d}S_{t}+\frac{1}{2}\frac{\partial^{2}f(S_{t})}{\partial S_{t}^{2}}\sigma(S_{t},t)^{2}S_{t}^{2}\mathrm{d}t\quad t\in[0,\infty)
$$  

$$
\mathrm{d}\log(S_{t})=\frac{1}{S_{t}}\mu(S_{t},t)S_{t}\mathrm{d}t-\frac{1}{2S_{t}^{2}}\sigma(S_{t},t)^{2}S_{t}^{2}\mathrm{d}t+\sigma(S_{t},t)\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

where the $S_{t}^{2}$ term cancels out on the right-hand side. Collecting terms, we obtain  

$$
\mathrm{d}\log(S_{t})=\left[\mu(S_{t},t)-\frac{1}{2}\sigma(S_{t},t)^{2}\right]\mathrm{d}t+\sigma(S_{t},t)\mathrm{d}W_{t}
$$  

Notice an interesting result. The dynamics for $\mathrm{d}S_{t}/S_{t}$ and $\mathrm{~d~}\log(S_{t})$ are almost the same except for the factor involving $\sigma(S_{t},t)^{2}\mathrm{d}t$ . This means that we can subtract the two equations from each other and obtain  

$$
\frac{\mathrm{d}S_{t}}{S_{t}}-\mathrm{d}\log(S_{t})=\frac{1}{2}\sigma(S_{t},t)^{2}\mathrm{d}t\quad t\in[0,\infty)
$$  

This operation has isolated the instantaneous percentage local volatility on the right-hand side. But, what we need for the variance swap is the integral of this term. Integrating both sides we get  

$$
\int_{T_{1}}^{T_{2}}\left[\frac{1}{S_{t}}\mathrm{d}S_{t}-\mathrm{d}\log(S_{t})\right]=\frac{1}{2}\int_{T_{1}}^{T_{2}}\sigma(S_{t},t)^{2}\mathrm{d}t
$$  

We now take the integral on the left-hand side,  

$$
\int_{T_{1}}^{T_{2}}\mathrm{d}\log(S_{t})=\log\left(S_{T_{2}}\right)-\log\left(S_{T_{1}}\right)
$$  

We use this and rearrange to obtain the result:  

$$
2\left[\int_{T_{1}}^{T_{2}}\frac{1}{S_{t}}\mathrm{d}S_{t}\right]-2\log\left(\frac{S_{T_{2}}}{S_{T_{1}}}\right)=\int_{T_{1}}^{T_{2}}\sigma(S_{t},t)^{2}\mathrm{d}t
$$  

We have succeeded in isolating the percentage total variance for the period. $[T_{1},T_{2}]$ on the right-hand side. Given that $S_{t}$ is an asset that trades, the expression on the left-hand side replicates this variance.  

# 15.5.4 THE HEDGE  

The interpretation of the left-hand side in Eq. (15.54) is quite interesting. It will ultimately provide a hedge for the variance swap. In fact, the integral in the expression is a good example of what Ito integrals often mean in modern finance. Consider.  

$$
\int_{T_{1}}^{T_{2}}\frac{1}{S_{t}}\mathrm{d}S_{t}
$$  

How do we interpret this expression?  

Suppose we would like to maintain a long position that is made of. $1/S_{t}$ units of $S_{t}$ held during each infinitesimally short interval of size. $\mathrm{d}t$ , and for all $t.$ In other words, we purchase. $1/S_{t}$ units of the underlying at time $t$ and hold them during an infinitesimal interval dt. Given that at time $t.$ $S_{t}$ is observed, this position can easily be taken. For example, if. $S_{t}=100$ , we can buy O.01 units of. $S_{t}$ at a total cost of 1 dollar. Then, as time passes, $S_{t}$ will change by. $\mathrm{d}S_{t}$ and the position will gain or. lose $\mathrm{d}S_{t}$ dollars for every unit purchased. We readjust the portfolio, since the. $S_{t+\mathrm{d}t}$ will presumablye be different, and the portfolio needs to be. $1/S_{t+\mathrm{d}t}$ units long.  

The resulting gains or losses of such portfolios during an infinitesimally small interval ${\mathrm{d}}t$ are given by the expression11  

$$
\frac{1}{S_{t}}\left(S_{t+\mathrm{d}t}-S_{t}\right)=\frac{1}{S_{t}}\mathrm{d}S_{t}
$$  

Proceeding in a similar fashion for all subsequent intervals $\mathrm{d}t$ , over the entire period $[T_{1},T_{2}]$ the gains and losses of such a dynamically maintained portfolio add up to  

$$
\int_{T_{1}}^{T_{2}}\frac{1}{S_{t}}\mathrm{d}S_{t}
$$  

The integral, therefore, represents the trading gains or losses of a dynamically maintained portfolio.12  

The second integral on the left-hand side of Eq. (15.52)  

$$
\int_{T_{2}}^{T_{2}}\mathrm{d}\log(S_{t})=\log\left(S_{T_{2}}\right)-\log\left(S_{T_{1}}\right)
$$  

is taken with respect to time $t$ , and is a standard integral. It can be interpreted as a static position. In this case, the integral is the payoff of a contract written at time $T_{1}$ , which pays, at time $T_{2}$ , the difference between the unknown log $\left({{S}_{{T}_{2}}}\right)$ and the known $\log\left({{S}_{{T}_{1}}}\right)$ . This is known as a log contract. The long and short positions in this contract are logarithmic functions of $S_{t}$  

In a sense, the left-hand side of Eq. (15.54) provides a hedge of the variance contract. If the trader is short the variance swap, he or she would also maintain a dynamically adjusted long position on $S_{t}$ and be short a static log contract. This assumes complete markets.  
