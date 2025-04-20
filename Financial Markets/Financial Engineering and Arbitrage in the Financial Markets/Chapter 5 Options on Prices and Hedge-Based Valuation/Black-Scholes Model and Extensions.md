---
tags:
  - binomial_model
  - black_scholes_model
  - dividends
  - option_pricing
  - volatility
aliases:
  - BSM
  - Black-Scholes
  - Option Valuation
key_concepts:
  - Binomial approach
  - Black-Scholes equation
  - Continuous rebalancing
  - Option payoff replication
  - Stock price volatility
---

# 5.7 BLACK-SCHOLES MODEL AND EXTENSIONS  

The well-known Black-Scholes? equation for calls and puts is a continuous generalization of. the binomial approach. There are at least two improvements here. First, the stock price, looking. forward from one date to the next, can take on a continuum of values not just two. Second, there is a continuum of dates, not just month-to-month, or day-to-day. The equation computes. the present value of a hedge strategy where the rebalancing occurs instant-by-instant and over. minute price changes. The overriding principle of payoff manufacturing remains the same. An option payoff is replicated by a position in a stock combined with borrowing or lending. The stock and bond position is adjusted continuously and for infinitesimal value changes. The value of the option today is equal to the cash required to start this dynamic hedge process.  

# 5.7.1 Black-Scholes with No Dividends  

For options on a non-dividend-paying stock, the value of a call and a put option in the Black-Scholes model is equal to:  

$$
\begin{array}{r l}&{C=S N(d_{1})-K e^{-r T}N(d_{2})}\ &{P=K e^{-r T}N(-d_{2})-S N(-d_{1})}\end{array}
$$  

where $\begin{array}{r}{d_{1}=\frac{\ln(S/K)+(r+\sigma^{2}/2)T}{\sigma\sqrt{T}}}\end{array}$ $d_{2}=d_{1}-\sigma\sqrt{T},r$ is a continuously compounded intres rate, and $T$ is the time to maturity. $N(d_{k})$ is the cumulative standard normal probability density function evaluated at $d_{k}$ . Values of $N(d_{k})$ can be found in statistical tables or in Excel by using $N O R M D I S T()$ . The formula provides an explicit link between the annual volatility of the stock return. $\sigma$ and the value of the option. In Black-Scholes, the continuously compounded return on the stock over an infinitesimal interval $d t$ is assumed to be normally distributed. What that means is that instead of the stock price taking on potentially only two values when moving from time $t$ to time $t+d t$ , the stock can take on a continuum of values such that the continuously compounded return on the stock over that interval, $\ln(S_{t+d t}/S_{t})$ , has a standard. deviation of $\sigma\sqrt{d t}$ . This is portrayed in Figure 5.25.  

The probability mass curve in the graph is not the normal bell-curve but rather that of a lognormal curve. The minimal stock price is zero, the maximal price is infinity. The percentage return is normal and would have a bell-shaped curve.  

The inclusion of price volatility in arriving at the value of the option was implicit in our. binomial trees where the width of each branch depended on the variability of the stock. But, it is easy to show that if, in a binomial model with a time step of $\Delta t$ , we set  

![](4fdf4579192afe024988e04f70f96217f5ebcf7f7129974065d696e3f04569a9.jpg)  
Figure 5.25  

$$
u=e^{\sigma\sqrt{\Delta t}},\quad d=1/u,\quad q=\frac{e^{r\Delta t}-d}{u-d},
$$  

then the binomial model is just a discrete approximation and will converge to the Black-Scholes equation4 as we shorten $\Delta t$ , i.e. increase the number of rehedging times in the tree. That is why we chose to present the binomial approach to option pricing first here, rather than go the continuous equation route. The discrete model is intuitive and more general, as it allows us to value American exercise options; the continuous one relies on a stochastic calculus argument. The two can be made equivalent to each other, i.e. they come up with the identical answer for the premium and delta hedge ratios.  

# 5.7.2Dividends  

The inclusion of dividends in option pricing is straightforward, assuming that dividends are a. known cash payout between now and the option expiry. Their effect on option prices should be intuitive. Because they are an outflow of value from the stock, they reduce the potential future price outcomes for the stock. As such, their impact is to decrease the call values and. increase the put values. This can also be argued by considering the delta hedge. The call writer buys less of the stock, and the put writer shorts more of the stock, because when they adjust the hedge the stock price will have been reduced by the amount of the dividends, whether the stock has gone up or down.  

There are two ways to correct option valuation for dividends, depending on whether their amount is known in dollars or as a percentage of the stock price. Consider dividends paid at a constant continuous rate 8. In the Black-Scholes model, the inclusion of dividends is accomplished by multiplying each occurrence of the stock price. $S$ by the continuous compounding term $e^{-\delta T}$  

$$
\begin{array}{r l}&{C=S e^{-\delta T}N(d_{1})-K e^{-r T}N(d_{2})}\ &{P=K e^{-r T}N(-d_{2})-S e^{-\delta T}N(-d_{1})}\ {\mathrm{with}}&{d_{1}=\cfrac{\ln\frac{s}{\mathrm{K}}+(r-\delta+\sigma^{2}/2)T}{\sigma\sqrt{T}}\quad\mathrm{and}\quad d_{2}=d_{1}-\sigma\sqrt{T}}\end{array}
$$  

In the binomial model, the correction is the same. Each node's stock value is reduced by the. amount of accrued dividends. We change the definitions of the upstate and the downstate to $u=e^{-\delta\Delta t+\sigma\sqrt{\Delta t}},\quad d=e^{-\delta\Delta t-\sigma\sqrt{\Delta t}}$  

The second way to include dividends is to assume that we know the dollar amount and the exact time of their occurrence. We then present-value those dividends and subtract from the current stock price. Denoting the present value of the dividends as $P V(D)$ , the corrected Black-Scholes formula looks like this:  

$$
\begin{array}{r l}&{C=(S-P V(D))N(d_{1})-K e^{-r T}N(d_{2})}\ &{P=K e^{-r T}N(d_{2})-(S-P V(D))N(-d_{1})}\ {\mathrm{with}}&{d_{1}=\frac{\ln\frac{S-P V(D)}{\mathrm{K}}+(r+\sigma^{2}/2)T}{\sigma\sqrt{T}}\quad\mathrm{and}\quad d_{2}=d_{1}-\sigma\sqrt{T}}\end{array}
$$  

In the binomial model, the correction consists of superimposing the dates on the binomial. grid of stock price nodes, and when the date of the dividend is reached, of subtracting the dollar amount of the dividend from the node's stock price.  

# 5.7.3 Options on Currency Rates  

Garman and Kohlhagen (1983) pointed out that options on currencies can be easily accommodated in the Black-Scholes framework by thinking of the denomination currency as a stock and the interest rate of that currency as a continuous dividend paid by that currency. The hedger of a call on the dollar/pound exchange rate will borrow dollars (and pay the dollar interest rate to finance) to buy the delta amount of pounds. Those pounds will earn an interest rate in pounds just as stock would earn a continuous dividend yield. The correction to the Black-Scholes formula to value currency options is thus the same as that for the continuous dividend yield $\begin{array}{r}{\delta=r_{G B P}}\end{array}$ ). Often, however, we see in written relative to the currency forwards rather than to spots. This is how it was first proposed by Fisher Black and has become known as the Black Model. The formula simply includes the spot-forward cash-and-carry parity $F=S e(r_{U S D}-r_{G B P})T$ and therefore looks like this:  

$$
\begin{array}{l}{{C=[F N(d_{1})-K N(d_{2})]e^{-r_{U S D}T}}}\ {{P=[K N(d_{2})-F N(-d_{1})]e^{-r_{U S D}T}}}\ {{d_{1}=\displaystyle\frac{\ln\frac F K+\left(\sigma^{2}/2\right)T}{\sigma\sqrt T}\quad\mathrm{and}\quad d_{2}=d_{1}-\sigma\sqrt T}}\end{array}
$$  

The implicit assumption in this formula is the same as in the Black-Scholes model which. is that the interest rates between now and the expiry of the option are constant. Therefore the formula is most appropriate for short-term currency options..  

# 5.7.4 Black-Scholes Delta, Gamma, and Vega  

Delta is the hedge ratio that tells the hedger how many units of the stock (or currency) to buy or short over the next short time period during the dynamic hedging process. It is also the sensitivity of the option price to the stock price. Mathematically, it is the change in the value of the option per unit change in the value of the stock, and can be defined as  

$$
\Delta_{C a l l}=\frac{d C}{d S},\Delta_{P u t}=\frac{d P}{d S}
$$  

where $d$ denotes the change in the value over an infinitesimal interval.  

If the delta is equal to 0.5 then the call hedger shorts half the amount of stock. Since delta is also the dollar sensitivity of the value of the option, for each dollar movement in the price of the stock, the hedger's call value will move by 50 cents, and so by shorting half the amount the hedge is perfect.  

In the Black-Scholes model, we obtain the delta by taking the first derivative of the option value with respect to the stock price. The result is simply:.  

$$
\begin{array}{l}{\Delta_{C a l l}=e^{-\delta T}N(d_{1})}\ {\Delta_{P u t}=e^{-\delta T}[N(d_{1})-1]}\end{array}
$$  

Gamma is the change in delta per unit change in the value of the stock, defined as:  

$$
\Gamma_{C a l l}=\frac{d\Delta_{C a l l}}{d S},\quad\Gamma_{P u t}=\frac{d\Delta_{P u t}}{d S}
$$  

and can be computed in the Black-Scholes model by taking the second derivative of the option value with respect to the price of the stock. The result is:.  

$$
\Gamma_{C a l l}=\Gamma_{P u t}=e^{-\delta T}n(d_{1})\Big/_{S\sigma\sqrt{T}}
$$  

Vega is the sensitivity of the option value to the unit change in the assumed annual volatility. In the Black-Scholes model, it is equal to:.  

$$
V_{C a l l}=V_{P u t}=e^{-\delta T}n(d_{1})S\sigma\sqrt{T}
$$  

In both equations, $n(d_{1})$ is the standard normal probability density function evaluated at $d_{1}$  

The gamma of an option is an important risk measure from the standpoint of an option hedger. The higher the gamma, the higher the change in delta. A higher gamma therefore implies a more frequent rebalancing of the hedge and more price gap risk. The vega of an option is a measure of the risk relative to the assumed volatility of the stock. Both measures are typically computed using, not the continuous Black-Scholes values but by discretizing the stock space. The gamma is quoted as the change in the delta per. $\$1$ change in the stock, and the vega as the change in the value of the option per. $1\%$ change in annual stock volatility.  
