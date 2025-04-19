---
tags:
  - asian_options
  - barrier_options
  - bopm
  - chooser_options
  - exotic_options
  - mcs
  - path_dependent
aliases:
  - Average Rate Options
  - Exotic Option Pricing
  - Path-dependent Options
key_concepts:
  - Asian and barrier options
  - BOPM and MCS
  - Closed-form solutions
  - European vs American options
  - Exotic option types
  - Path-dependent payoffs
---
# Exotic Options  

# Aims  

• To analyse various types of exotic option whose payo!s are path dependent. • To use the BOPM and MCS to price various exotic (path dependent) options. • To demonstrate the use of Asian (or average rate) options, barrier options and other exotics such as lookback, forward start and chooser options.  

In this chapter we explain how some of the more exotic options contracts (e.g. on stocks, FX, and commodities) can be used in speculation and hedging. Closed-form solutions for the price of exotic options are often not possible and we demonstrate how some of these options are priced using binomial trees and Monte Carlo simulation (MCS).  

It is difcult to say where plain vanilla options end and exotics begin. Generally speaking, the payo!s from exotics are more complex than those from vanilla options. As a result, exotics are largely OTC instruments and their payo!s may sometimes be ‘structured’ to an individual client’s needs – hence the term structured fnance is sometimes used to denote options with complex payo!s.  

The payo! to a European option depends only on the price of the underlying at maturity, $T$ (since it can only be exercised at maturity) and does not depend on the path taken to reach $T$ . European options are said to be path independent. On the other hand, it may be proftable to exercise an American option prior to expiration and hence this is a path-dependent option. Many exotic options are path dependent. For example, an Asian (average price) call option has a payo! which depends on the di!erence between the average price $S_{a v}$ over the life of the option and the strike price. The Asian call payo! is $\operatorname*{max}(S_{a v}-K,0)$ and the value of $S_{a v}$ depends on the path taken by the stock price over the life of the option. Similarly, some options have a payo! which depend on the maximum or minimum value of the asset price over the life of the option – these are also path-dependent options.  

Some path-dependent options have closed-form solutions for the options price, as long as one assumes that the underlying asset price is monitored continuously. In practice, payo!s to path-dependent options usually depend on observations of the underlying asset price at discrete intervals (e.g. closing prices), and closed-form solutions may not be possible. Path-dependent options (with discrete monitoring) can often be priced using either the BOPM or MCS.  

# 31.1 THREE-PERIOD BOPM  

# 31.1.1 European Plain Vanilla Call Option  

We use the $n=3$ period BOPM model. Assume the stock price can go up by $15\%$ ( $U=1.15)$ or down by $20\%$ $(D=0.8)$ each period.1 The initial stock price $S_{0}=100$ , $r=10\%$ per period and the strike is $K=100$ . The risk-neutral probabilities for ‘up’ and ‘down’ moves are:  

$$
q=(R-D)/(U-D)=0.8571431-q=0.142857
$$  

where $R=1+r$ . The stock price tree is shown in Table 31.1:  

To value a European option all we require are the four possible payo!s at maturity, which for a call option are max $[S(3)_{i}-K,0]$ and for a put are max $\left[K-S(3)_{i},0\right]$ . Using backward recursion through each node of the tree and risk neutral valuation RNV we obtain:  

$$
C=26.02P=1.15
$$  

There are $8(=2^{n})$ alternative paths for the stock price through the 3-period tree (UUU, UUD, UDU, etc.). However, as the price of a European call (or put) depends only on the outcomes for the stock price at maturity of the option contract, we can simplify the above recursive calculation. So instead of looking at all (the nodes across all) the eight possible paths, we can simplify the computation by using the following binomial formula with $n=3$ :  

$$
C=(1/R^{n})\sum_{k=0}^{n}{\binom{n}{k}}q^{k}(1-q)^{n-k}\operatorname*{max}\left[{S U}^{k}D^{n-k}-K,0\right]
$$  

In the above formula the sum is only over $k$ , the number of up moves, which has only four values, 0, 1, 2 and 3. This is a consequence of path independence since we are only concerned with the payo!s at $n=3$ . For example, for the paths with two ‘up moves’ that is UUD, UDU and DUU, they have the same value for $S(3)$ and these three outcomes are given by the term ${\binom{3}{2}}=3.$ Hence for these three paths we obtain the term ${}^{\cdot}3q^{2}(1-q)(S U^{2}D-K)^{,}$ in the above formula and we do not have to deal with each of the three paths separately.  

TABLE 31.1 Stock price tree   


<html><body><table><tr><td colspan="4">Number of ups</td></tr><tr><td>３</td><td colspan="3"></td></tr><tr><td>２</td><td colspan="3">152.09 132.25</td></tr><tr><td>1</td><td>115</td><td>92</td><td>105.80 73.60</td></tr><tr><td>0</td><td>102 80</td><td>64</td><td>51.20</td></tr><tr><td>Time</td><td>0 1</td><td>2</td><td>3</td></tr></table></body></html>  

Although it is more time consuming, we could also value the plain vanilla European call option as if it were path dependent. To do this we follow the stock price along each of the eight paths to get the eight possible payo!s to the call at $n=3$ . Each of these paths $i=1,2,\dots,8$ has a payo! equal to $\operatorname*{max}[S(3)_{i}-K,0]$ . The risk neutral probability for each path is:  

$$
q_{i}^{*}=q^{k}(1-q)^{n-k}
$$  

where $k=$ number of ‘up’ moves and $(n-k)=$ number of ‘down’ moves. For example $q_{i}^{*}$ for the ‘three ups’ UUU-path would equal $q^{3}$ while $q_{i}^{*}$ for each of the three paths with ‘two ups’ (i.e. UUD, DUU, and UDU) is $q^{2}(1-q)$ . The call premium is then the present value of the expected payofs along all eight paths using risk-neutral probabilities $q_{i}^{*}(\mathrm{i}=1,2,\ldots,8)$ and discounting using the (continuously compounded) risk-free rate:  

$$
C=e^{-r T}\sum_{i=1}^{8}q_{i}^{*}\operatorname*{max}[S(3)_{i}-K,0].
$$  

Of course this gives us the same answer as the binomial formula of Equation (31.2), which is computationally easier and quicker. Unfortunately, for path-dependent options we need to calculate the outcomes along every possible path through the lattice, since the payo!s depend on the particular path taken – this can be computationally burdensome – for $n=30$ periods (say).  

# 31.2 ASIAN OPTIONS  

Asian options have a payo! which is based on the average price over the life of the option. For example, an Asian (average price) call option has a payo! which depends on max $[S_{a v}-K,0]$ where $S_{a v}$ is the average price over the life of the option.  

An Asian average price currency option would be useful for a frm that wants to hedge the average level of its future receipts in foreign currency. The frm’s monthly foreign currency receipts may \$uctuate over the year so an Asian option is a cheap way to hedge, rather than using 12 vanilla calls with expiration dates in each of the months.  

Average price Asian options have a payo! which depends on $\operatorname*{max}[S_{a v}-K,0]$ for a call and $[K-S_{a v},0]$ for a put. There are also Asian average strike options and here the average price replaces the strike price, so the payo! for a call is $\operatorname*{max}[S_{T}-S_{a v},0]$ and for a put is $\operatorname*{max}[S_{a v}-S_{T},0]$ . Since the underlying principles are similar, we do not discuss the Asian average strike option.  

The payo! from an Asian option (on a stock) may be based on the arithmetic or the geometric average of the underlying asset. For example, if the underlying price $s$ for one path in a 3-period tree is 100, 115, 132, 152 then the payo! to a call based on the arithmetic average would be $(100+115+132+152)/4]-K$ and for the geometric average it would be $[(100)(115)(132)(152)]^{1/4}-K$ .2 The geometric average is always less than the arithmetic average (except when all values of $s$ are equal) and the di!erence between the two averages is greater, the greater the volatility of the price series.  

Although analytic formulas (similar to Black–Scholes) for the price of an Asian option can be derived when the payo! is based on the geometric average, this is not the case for options based on the arithmetic average – which is unfortunate since the latter options are far more popular. It can be shown that (in a risk-neutral world) the geometric average of the asset price has the same probability distribution as the asset price itself, at maturity of the option, if the asset’s expected growth rate is set equal to $(r-\delta-\sigma^{2}/6)$ rather than the standard $(r-\delta)$ and volatility is set at $\sigma/\sqrt{T}$ rather than $\sigma$ . Hence we can price the geometric average option using the standard Black–Scholes formulas, with the above changes.  

How can we price an arithmetic average option? It can be shown that the distribution of the arithmetic average is approximately lognormal and therefore we can apply Black’s equation for pricing futures-options, with the following changes. We calculate the frst two moments (mean, $M$ and standard deviation, stdv) of the probability distribution of the arithmetic average (in a risk-neutral world) and ft a lognormal distribution to these moments. We then set  

$$
F_{0}=M\mathrm{and}\sigma^{2}=(1/\mathrm{T})\ln(s t d\nu/M^{2})
$$  

and use Black’s equation for futures options (see Chapter 25, Equations 25.15–25.18). Numerical methods such as the BOPM and Monte Carlo simulation are often used to price Asian options.  

Consider an Asian (average price) call option on stock price $s$ , with $n=3$ steps (using the same tree as above) which is reproduced in Table 31.2, for the eight possible paths for the stock price. The steps needed to price the Asian call using the BOPM are:  

TABLE 31.2 Path in BOPM   


<html><body><table><tr><td>Path number</td><td>Path</td><td>Number of ups</td><td> Prob.</td><td>S(0)</td><td>S(1)</td><td>S(2)</td><td>S(3)</td><td>S (average)</td></tr><tr><td>１</td><td>UUU</td><td>3</td><td>0.6297</td><td>100</td><td>115</td><td>132.25</td><td>152.09</td><td>124.83</td></tr><tr><td>2</td><td>UUD</td><td>2</td><td>0.1050</td><td>100</td><td>115</td><td>132.25</td><td>105.80</td><td>113.26</td></tr><tr><td>3</td><td>UDU</td><td>2</td><td>0.1050</td><td>100</td><td>115</td><td>92</td><td>105.80</td><td>103.20</td></tr><tr><td>4</td><td>DUU</td><td>2</td><td>0.1050</td><td>100</td><td>80</td><td>92</td><td>105.80</td><td>94.45</td></tr><tr><td>5</td><td>UDD</td><td>1</td><td>0.0175</td><td>100</td><td>115</td><td>92</td><td>73.60</td><td>95.15</td></tr><tr><td>6</td><td>DUD</td><td>1</td><td>0.0175</td><td>100</td><td>80</td><td>92</td><td>73.60</td><td>86.40</td></tr><tr><td>7</td><td>DDU</td><td>1</td><td>0.0175</td><td>100</td><td>80</td><td>64</td><td>73.60</td><td>79.40</td></tr><tr><td>8</td><td>DDD</td><td></td><td>0.0029</td><td>100</td><td>80</td><td>64</td><td>51.20</td><td>73.80</td></tr></table></body></html>  

• Calculate average stock price $S_{a v,i}$ at expiry, for each of the 8 possible paths $(i=1,2,\ldots,8)$   
• Calculate the option payo! for each path: max $[S_{a v,i}-K,0]$   
• The risk-neutral probability for a particular path is $q_{i}^{*}=q^{k}(1-q)^{n-k}$   
• Weight each of the eight outcomes for the payo! by their respective probabilities $q_{i}^{*}$ and sum them to give the risk-neutral expected payof:  

$$
\sum_{i=1}^{8}q_{i}^{*}\operatorname*{max}[S_{a v,i}-K,0].
$$  

• The call premium is then the PV of the expected payo! discounted at the risk-free rate:  

$$
C_{A s i a n}=e^{-r T}\left[\sum_{i=1}^{8}q_{i}^{*}\operatorname*{max}[S_{a v,i}-K,0]\right].
$$  

The eight fnal payo!s for the call option are shown in Table 31.3. The call premium for the Asian call option is $C=13.05$ . Similarly the price of an (average price) Asian put option is $P=1.01\$ .  

The payo!s and option premia for Asian average strike options using the BOPM are calculated in a similar way and are shown in the last two columns of Table 31.3. The problem with using the binomial model to price the Asian option is that at least 50 steps are required to get an accurate measure of the option price and this requires evaluating $2^{50}$ alternative paths! Even fast computers might not be quick enough to price the option in order to execute a deal.  

TABLE 31.3 Payo! to asian options   


<html><body><table><tr><td>Price call payoff</td><td>Price put payoff</td><td>Strike call payoff</td><td>Strike put payoff</td></tr><tr><td>24.83</td><td>0</td><td>27.25</td><td>0</td></tr><tr><td>13.26</td><td>0</td><td>0</td><td>7.45</td></tr><tr><td>3.20</td><td>0</td><td>2.60</td><td>0</td></tr><tr><td>0</td><td>5.55</td><td>11.35</td><td>0</td></tr><tr><td>0</td><td>4.85</td><td>0</td><td>21.55</td></tr><tr><td>0</td><td>13.60</td><td>0</td><td>12.80</td></tr><tr><td>0</td><td>20.60</td><td>0</td><td>5.80</td></tr><tr><td>0</td><td>26.20</td><td>0</td><td>22.60</td></tr><tr><td>13.05</td><td>1.01</td><td>13.99</td><td>1.17</td></tr></table></body></html>

Notes: Asian average price options payoffs are, for a call, max[S(average) – K,0] and for a put, max[K – S(average),0]. Asian average strike options payoffs are, for a call, max[S(3) – S(average),0] and for a put, max[S(average) – S(3),0]  

The plain vanilla call costs more at $C=26.02$ than the Asian average call at $C=13.05$ . Why? For a plain vanilla call, the call premium increases the higher is the volatility $\sigma$ of the underlying asset, S. The call premium for an Asian average price call (same underlying, strike, and maturity date) depends positively on the volatility of the average price, $\begin{array}{r}{S_{a v}=(1/n)\overline{{\sum_{i=1}^{n}S_{i}}}\mathrm{.~}}\end{array}$ , where $n$ is the number of values used to compute the average. If $s$ follows a Brownian motion and hence is identically and independently distributed $(i i d)$ then $\sigma_{a v}^{2}=\sigma^{2}/n$ , which is smaller than $\sigma^{2}$ . The Asian call premium that depends positively on $\sigma_{a v}^{2}$ , will therefore be lower than the call premium on a plain vanilla call (which depends positively on $\sigma^{2}$ ).  

# 31.2.1 Monte Carlo Simulation (MCS)  

An alternative and more efcient way to price an Asian option is to use MCS. Under risk-neutral valuation we ‘replace’ the real world growth rate of the stock $\mu$ with the risk-free rate $r$ in the Brownian motion for the stock price. Assume the Asian option contract specifes that the underlying asset price $s$ will be observed each trading day when calculating the average price over the whole year and:  

As we have seen, MCS produces a series of alternative paths for the stock price using a discrete approximation to a Brownian motion. The payo! for an Asian (average price) call option for each run- $i$ of the MCS over $n=T/d t=252$ periods is:  

$$
\mathrm{Callpayoff}=\operatorname*{max}[S_{a v,i}-K,0]
$$  

where $S_{a v,i}$ is the average stock price over the 252 simulated trading days. The price of the Asian option is the PV of the payo!s (discounted at the risk-free rate) over all $m$ -runs of the MCS:  

$$
\hat{C}=e^{-r T}(1/m)\sum_{i=1}^{m}\operatorname*{max}[S_{a v,i}-K,0]
$$  

We need to choose m large enough so that the error in estimating $\hat{C}$ is acceptable (we can obtain a standard error for our estimate of $\hat{C}$ as outlined in Chapter 26). Put in a more intuitive way, if we do $m+1$ simulations then the calculated value for $\hat{C}$ should be ‘close to’ that found when using m simulations.  

# 31.3 OTHER EXOTICS: LOOKBACKS, BARRIER, COMPOUND, AND CHOOSER  

There is a virtually unlimited set of exotic options whose payo!s, time to maturity, strike price etc. can be ‘structured’ in the OTC market to suit the client’s needs for either hedging or speculation. Needless to say the more ‘exotic’ the payo! structure, then generally speaking the more difcult they are to price and, often, numerical techniques are required. Below we brie\$y discuss some of the more common exotics.  

# 31.3.1 Lookbacks (No-regrets) and Shout Options  

Lookback options (on a stock) provide an investor with the opportunity to buy a stock at a potentially ‘low’ price $[=$ long call option) or sell a stock at a potentially ‘high’ price $\left(=\log\right.$ put option). For example, $a$ lookback (European) call has the strike price set at expiration, at the lowest price $S_{\mathrm{min}}$ of the stock during the life of the option, so the payo! is $\operatorname*{max}[S_{T}-S_{\operatorname*{min}},0]$ . Similarly, a lookback (European) put sets the strike price at expiration, equal to the highest price reached by the stock over the option’s life, so the payo! is $\operatorname*{max}[S_{\mathrm{max}}-S_{T},0]$ .  

These options are also referred to as no-regrets options since you would never regret not having exercised the option at an earlier date. The worst outcome possible with a lookback option is if it expires at-the-money $\langle S_{T}=S_{\mathrm{min}}\rangle$ ). There are also fxed strike lookbacks with payo!s for a call being $\operatorname*{max}[S_{\mathrm{max}}-K,0]$ and for a put, $\operatorname*{max}[K-S_{\operatorname*{max}},0]$ .  

We have the complete set of paths for the stock price in the BOPM (see Table 31.2) and the associated risk neutral probabilities $q_{i}^{*}$ for each path. Hence, knowing the payo!s of the above lookbacks, it is easy to price them using the BOPM (or MCS). It should be obvious that  

European lookbacks have payo!s which are more favourable than ordinary European options and hence will have higher call and put premia.  

Shout options are European options that allow the holder to lock in a minimum payo! $S_{t}-K>0$ at one point in time $t>0$ during its life, but this payo! is not received until the expiration date, $T_{\cdot}$ . For example, suppose the stock price rises so that a call option is currently in-the-money. With a shout option the holder, who may fear a future fall in stock prices, can ‘shout’ that the current payo! $S_{t}-K$ , will be the minimum payof at maturity. The payo! to the shout (call) option at $T$ is max $\{S_{t}-K,S_{T}-K,0\}$ .  

But if the holder shouts at time $t$ , then the payo! to the shout option (at $T$ ) is $\operatorname*{max}\{S_{T}-S_{t},0\}+S_{t}-K$ . Given the above payo!, the value of the shout option is the present value of $S_{t}-K$ (discounted from time $T$ ) plus the Black–Scholes value of a European call with a strike price $K=S_{t}$ .  

To price a shout call option using the BOPM we work backwards through the tree. At each node we calculate the (recursive) value if the holder does not shout and the value $S_{t}-K$ if the holder shouts and we take the greater of the two. This is similar to pricing a standard American option.  

# 31.3.2 Barrier Options  

Barrier options either ‘die’ or ‘come alive’ before expiration. For example, a knockout option may specify that if the stock price rises or falls to a ‘barrier level’, the option will terminate on that date, and hence cannot be exercised at a later date. If the option is terminated when the stock price falls to a lower barrier, we have a down-and-out option, while if it terminates when the price rises to a higher barrier, they are up-and-out-options. Option premia are paid ‘up front’ (at $t=0$ ).  

Another variant of the barrier option is the up-and-in-option, whereby the option’s ‘life’ does not begin until the stock price hits an upper barrier. The option premium is paid up front but the option cannot be exercised unless the stock price hits or crosses the upper barrier. Similarly a down-and-in-option is not ‘activated’ until the stock price hits (or crosses) the designated lower barrier.  

# 31.3.2.1 Down-and-Out Put  

Suppose you own a stock with current price $S_{0}=\$100$ and you buy a 1-year plain vanilla (European) put with strike $K=100$ . If the stock price falls to $S_{T}=\$91$ at maturity, you obtain a cash payo! of $K-S_{T}=\$9$ from the put, which implies your stock $^+$ put portfolio is worth $\$100$ (the $\$9$ cash plus the value of the stock $\$91$ ) – you have provided a \$oor value for the stock of $K=100$ .  

Consider instead purchasing a 1-year down-and-in (European) put with $K=100$ and a ‘knock-in’ lower barrier set at $L=90$ . If the stock price falls monotonically to say $S_{T}=91$ at maturity, then your option will not have knocked-in and you will receive no payo! – this is a worse outcome than for the plain vanilla put. If at maturity $S_{T}=91$ but sometime over the past year the stock price fell below $L=90$ , then your down-and-in put would have ‘come alive’ earlier and will now payo! $K-S_{T}=\$9$ at maturity.  

Hence for the down-and-in put to be worthwhile in providing a \$oor (at $T$ ), you must think that the stock price is going to be highly volatile over the next year, so it is likely that it would go through the lower barrier, $L=90$ , prior to expiration of the put. But why buy a down-and-in put when the vanilla put pays o! in more states of the world? The answer is that a down-and-in put is cheaper than a vanilla put (with the same underlying, strike and maturity) since the down-and-in put doesn’t come ‘alive’ until the lower barrier is hit. In other words you get what you pay for. With the down-and-in put, the payo! (at maturity) may be less than with the plain vanilla put, hence you pay less today for the down-and-in put.  

# 31.3.2.2 Up-and-Out Put  

Who might buy a European ‘up-and-out’ put? Consider a pension fund manager (Ms Long) who holds stocks that she wishes to ‘cash in’ after 1 year, or an oil producer (Mr Barrel) who will have barrels of oil ‘ready for sale’ in 1 year. Assume the stocks and oil are currently worth $S_{0}=100\$ . In both cases suppose they think prices are highly unlikely to cross an upper barrier $H=110$ over the next year. Also, assume they are both willing to ‘take a hit’ of a price fall of up to $10\%$ (in oil or stock prices, but no more), by the year-end. They could protect their position by buying a 1-year out-of-the-money (OTM) vanilla put with a strike of $K=90$ – but this might be expensive, given the volatility in stock or oil prices.  

Instead, suppose Ms Long buys a European up-and-out put with a strike of $K=90$ and a ‘knock-out’ upper barrier of $H=110$ . If the stock price hits $H=110$ on any day through the year, Ms Long loses her insurance (policy) on that day – that is, the put is now ‘dead’ and cannot be used to provide a \$oor of $K=90$ if prices fall below that level in 1 year’s time. But if prices do not rise above $H=110$ on any day over the next year but they do fall below $S_{T}=90$ by the end of the year, the up-and-out put ‘remains alive’ and provides a \$oor of $K=90$ . So there is more risk if you hold an up-and-out put rather than the vanilla put, but the up-and-out put costs you less.  

# 31.3.2.3 Pricing Barrier Options  

Pricing path-dependent barrier options using the BOPM or MCS is straightforward in principle. Again, consider the stock price lattice applied to down-and-out and down-and-in calls with the lower barrier set at $L=90$ , the upper barrier with $H=110$ and the call is initially at-the-money, $S_{0}=K=100$ (Table 31.4).  

Consider a down-and-out call. The payo! is $\operatorname*{max}[S_{T}-K,\ 0]$ as long as $s$ does not fall below $L=90$ . If any value of $s$ along a particular path falls below $L$ then the option knocks out (indicated by ‘knock’ in Table 31.4) and even if at expiration $S_{T}>K$ , the payo! to this call is zero. Consider path number 4 (which is $D U U)$ at $t=1$ where $S=80<L=90.$ . So even though along this path, at expiry $S(3)=105.8>K=100$ , nevertheless this call has a zero payo!, since it has already ‘died’. The payo!s for this call at $n=3$ , for all eight paths are shown in Table 31.4, column [1]. The call premium for the down-and-out call is simply the expected value of these eight payo!s (using risk-neutral probabilities $q_{i}^{*}$ ), discounted at the risk-free rate, which gives C down-and-out $=25.56$ .  

TABLE 31.4 Barrier options   


<html><body><table><tr><td rowspan="5">Path</td><td rowspan="5"></td><td rowspan="5"></td><td rowspan="5"></td><td rowspan="5"></td><td rowspan="5"></td><td colspan="9">90 90 Down-out and</td></tr><tr><td colspan="9">down-in options Payoffs</td></tr><tr><td colspan="9">Out call [1]</td></tr><tr><td></td><td></td><td>In call [2]</td><td>Out put [3]</td><td>In put [4]</td><td>Out call [5]</td><td>In call [6]</td><td>Out put [7]</td><td>In put [8]</td></tr><tr><td>１</td><td>UUU</td><td>100</td><td>115.00</td><td>132.25</td><td>152.09</td><td>52.09</td><td>Knock</td><td>0</td><td>Knock</td><td>Knock</td><td>52.09</td><td>Knock</td><td>0</td></tr><tr><td>2</td><td>UUD</td><td>100</td><td>115.00</td><td>132.25</td><td>105.80</td><td>5.80</td><td>Knock</td><td>0</td><td>Knock</td><td>Knock</td><td>5.80</td><td>Knock</td><td>0</td></tr><tr><td>3</td><td>UDU</td><td>100</td><td>115.00</td><td>92.00</td><td>105.80</td><td>5.80</td><td>Knock</td><td>0</td><td>Knock</td><td>Knock</td><td>5.80</td><td>Knock</td><td>0</td></tr><tr><td>4</td><td>DUU</td><td>100</td><td>80.00</td><td>92.00</td><td>105.80</td><td>Knock</td><td>5.80</td><td>Knock</td><td>0</td><td>5.80</td><td>Knock</td><td>0</td><td>Knock</td></tr><tr><td>5</td><td>UDD</td><td>100</td><td>115.00</td><td>92.00</td><td>73.60</td><td>0</td><td>Knock</td><td>26.40</td><td>Knock</td><td>Knock</td><td>0</td><td>Knock</td><td>26.40</td></tr><tr><td>6</td><td>DUD</td><td>100</td><td>80.00</td><td>92.00</td><td>73.60</td><td>Knock</td><td>0</td><td>Knock</td><td>26.40</td><td>0</td><td>Knock</td><td>26.40</td><td>Knock</td></tr><tr><td>7</td><td>DDU</td><td>100</td><td>80.00</td><td>64.00</td><td>73.60</td><td>Knock</td><td>0</td><td>Knock</td><td>26.40</td><td>0</td><td>Knock</td><td>26.40</td><td>Knock</td></tr><tr><td>8</td><td>DDD</td><td>100</td><td>80.00</td><td>64.00</td><td>51.20</td><td>Knock</td><td>0</td><td>Knock</td><td>48.80</td><td>0</td><td>Knock</td><td>48.80</td><td>Knock</td></tr><tr><td colspan="8">Value of the option</td><td>0.46</td><td>0.35</td><td>0.80</td><td>0.46</td><td>25.56</td><td>0.80</td><td>0.35</td></tr></table></body></html>  

Notice that for $L=90$ , the sum of the option premia on the down-and-out call and the down-and-in call (i.e. $25.56+0.46)$ , equals the premium for a plain vanilla European call, $C=26.01\$ . This is because whenever the down-and-out call ‘dies’, the down-and-in call, ‘comes alive’, so if you hold both it is equivalent to holding a European vanilla call. This also demonstrates that the individual premia on the knock-out options are lower than the premia on the equivalent European vanilla options.  

Take another example. If you want to insure a minimum value for a stock portfolio $(S_{0}=100)$ ) using a put with a strike of $K=100$ , you might consider buying an up-and-out put with an upper barrier at $H=110$ which costs $P_{U\&O}=0.80$ – this is cheaper than buying a vanilla put, $P=1.15$ (Table 31.4) – with the same strike and maturity date.  

Also, a speculator who expects a strong bull market but with little prospect of a steep fall in stock prices, might consider purchasing a down-and-out call because it costs less than (an equivalent) vanilla call. If the stock price over the life of the option does not fall below the lower barrier but a bull market also ensues, then the speculator can make a handsome proft.  

Note that for barrier options, the nodes in the BOPM lattice would need to be aligned with the exact time the stock price is ‘checked’ against the barrier (e.g. each day at 4 p.m.). Table 31.4 also shows the outcomes and premia for some other European barrier options.  

It should be clear from the above that MCS can easily be adapted to price barrier options. Consider a European knock-out call option. We simulate the stock price using a Brownian motion (under risk-neutrality) and if on a particular run of the Monte Carlo a barrier is crossed, then the payo! at expiration is set to zero even if $S_{T}>K$ If the barrier is not crossed, the payo! is max $(S_{T}-K,0)$ .  

Excel and MATLAB fles that price barrier options using the BOPM and MCS are on the website.  

# 31.3.3 Compound Options  

There are also options on options, known as compound options. Compound options have two strike prices and two exercise dates. For example, consider a call on a call. At $T_{1}$ the holder of the compound option can pay $K_{1}$ and take delivery of a call option, which gives her right to buy the underlying asset for $K_{2}$ at time $T_{2}$ . The holder of the compound option will exercise at $T_{1}$ only if the value of this option exceeds $K_{1}$ .  

On 15 January an investor Ms Caution, decides that in 6 months’ time (at $T=15$ June) she wants to buy a 2-year call option (on Apple stock) with a strike $K_{1}$ . But on 15 January she is worried that by 15 June, the price of cash-market 2-year call options on Apple may have increased (above $K_{1}$ ).  

On 15 January she therefore wants to fx the maximum price $K_{1}=\$10$ she will pay on 15 June for ‘delivery’ of the 2-year call option on Apple, but she also wants to be able to take advantage of lower call premiums in the cash-market on 15 June, should this occur. Hence, on 15 January Ms Caution buys a ‘call on a call’, with a strike price $K_{1}=\$10$ and pays (Morgan Stanley) the compound-option call premium of $C_{0}^{c o m p}=\$1$ (say).  

On 15 June if the cash-market price of 2-year call options on Apple stock (with strike $K_{2}$ ) being o!ered by Goldman’s (say) is $\dot{C}_{T_{1}}^{2y r}>K_{1}\dot{$ , Ms Caution will exercise her compound option with Morgan Stanley and take delivery of a 2-year call option (on Apple) at the low price $K_{1}=$ $\$10$ . Alternatively, on 15 June if 2-year call options on Apple from Goldman’s cost $\bar{C}_{T_{1}}^{2y r}<\bar{K}_{1}$ , she will not exercise the compound option with Morgan Stanley (and hence pay $K_{1}$ ) and instead buys a cash-market 2-year call option on Apple stock from Goldman’s, at the lower price of $C_{T_{1}}^{2\breve{y}r}$ . Hence a compound call option provides insurance against a future increase in call options prices. There are also puts-on-puts, puts-on-calls and calls-on-puts – but ‘enough already’. If we assume a GBM then European compound options have a complex closed-form solution that depends on integrals of the bivariate normal distribution (but we do not pursue that here).  

# 31.3.4 Rainbow Options  

Options can be structured to have a payo! based on the better or worse of two underlying assets and these are referred to as min-max, rainbow options or alternative options. For example, a rainbow call may pay o! according to which of two underlying stocks (A or B) has the larger payo! at expiration.  

$$
\mathrm{Payoff~rainbow~call}=\operatorname*{max}[S_{T}^{A}-K_{A},S_{T}^{B}-K_{B},0]
$$  

# 31.3.5 Chooser Option  

Sometimes an exotic option can be priced analytically because it can be decomposed into two ‘simpler options’ that do have exact pricing formulas. A chooser option or as-you-like-it option allows an investor to choose at a (known) specifc point in time $t<T$ , whether the option is to be a call or a put. Once this choice has been made at $t$ , the option remains as either a call or a put (to its expiration date, $T$ ). In a ‘standard chooser’, the call and put both have the same strike price and maturity and the choice has to be made at the prearranged time, t. ‘Complex choosers’ allow the holder to decide at any time before expiration whether to choose a call or put and the calls and puts may have di!erent strikes and maturities. We only consider the standard chooser.  

TABLE 31.5 Payo! to a chooser at $T$   


<html><body><table><tr><td>Choice at t</td><td colspan="2">Payoff at T</td></tr><tr><td>Chooser option</td><td>S<K</td><td>S> K</td></tr><tr><td>Call</td><td>0</td><td>S-K</td></tr><tr><td>Put</td><td>K-S</td><td>0</td></tr></table></body></html>  

A chooser option is useful for speculating that there will either be a large rise (choose the call) or a large fall (choose the put) in the stock price between $t$ and $T$ . The prospective payo! at $t=0$ is therefore like a straddle but the chooser option has a lower premium. The reason for the lower premium is that a straddle always has a positive (gross) payo!, if either the call or the put is in-the-money at expiration (i.e. $S_{T}>K$ or $S_{T}<K\`$ ). But with a ‘chooser’, after the choice is made at $t$ , there is a possibility that the chooser option will end up out-of-the-money (e.g. if you choose a call at $t$ and $S_{T}<K$ at expiration, then your chooser option has a zero payo!). The closer is the choice date to the maturity date of the options, the lower the probability of a wrong choice at $t$ and hence the chooser becomes more like a straddle.  

An analytic solution for pricing a chooser option (on a stock which pays no dividends) is possible because it can be replicated using a long call and a long put – hence the price of the chooser is simply the sum of the ‘replication’ call and put premia. The analysis is a little involved and requires several steps.  

First calculate whether the investor (Ms Dizzy) will choose a call or put. At $t$ , Ms Dizzy will choose the type of option which has the highest value. For example, she will choose a call if:  

$$
C(S_{t},T-t,K)>P(S_{t},T-t,K)
$$  

Substituting for $P_{t}$ from put–call parity, $P_{t}=C_{t}-e^{-\delta(T-t)}S_{t}+K e^{-r(T-t)}$ (where the underlying asset has a constant dividend yield, $\delta$ ) this implies:  

$$
C_{t}>C_{t}-e^{-\delta(T-t)}S_{t}+K e^{-r(T-t)}\Rightarrow S_{t}>K e^{-(\delta-r)(T-t)}
$$  

Hence Ms Dizzy chooses the call at $t$ whenever the stock price at $t$ exceeds $K^{*}=$ $K e^{-(\delta-r)(T-t)}$ . Given the choice at $t$ , of either a call or put, the payo!s at maturity $T$ consequent on this choice are given in Table 31.5.  

To price the chooser option we need to consider a replication portfolio made up of ‘plain vanilla’ options that we can price using Black–Scholes. The price of the chooser option will then equal the price of this replication portfolio. The holder of the chooser at time $t$ will choose the more valuable of the two options:  

$$
\operatorname*{max}[C(S_{t},K,T-t),P(S_{t},K,T-t)]
$$  

Put–call parity at time $t$ :  

$$
P(S_{t},K,T-t)=C(S_{t},K,T-t)+K e^{-r(T-t)}-e^{-\delta(T-t)}S
$$  

Substituting in (31.11) for $P$ :  

$$
\operatorname*{max}[C(S_{t},K,T-t),C(S_{t},K,T-t)+K e^{-r(T-t)}-e^{-\delta(T-t)}S]
$$  

Rearranging (31.13):  

$$
C(S_{t},K,T-t)+\{e^{-\delta(T-t)}\mathrm{max}[0,e^{-(r-\delta)(T-t)}K-S_{t}]\}
$$  

The second term (in curly brackets) is the payo! from $e^{-\delta(T-t)}$ put options with strike $K^{*}=$ $e^{-(r-\delta)(T-t)}K$ which matures at $t$ . From (31.14) we see that the chooser is equivalent to the following replication portfolio at $t=0$ :  

(a) Long one European call with maturity $T$ and strike price $K$ plus (b) Long $e^{-\delta(T-t)}$ European puts with maturity $t$ and strike price $K^{*}=e^{-(r-\delta)(T-t)}K$  

Hence using Black–Scholes the price of the chooser $V_{c h}$ (at $t=0$ ) is  

$$
V_{c h}=C(S,K,T)+e^{-\delta(T-t)}P(S,K^{\ast},t)
$$  

A straddle is a call and put with the same strike $K$ and maturity $T(>t)$ , so it di!ers from a chooser because for the chooser, the put matures at $t<T$ . If $\delta=0$ then the chooser has the same call as the straddle but the chooser has a put with a lower strike and a shorter maturity – hence the chooser costs less than the straddle.  

# 31.4 SUMMARY  

• Exotic (European) options have payo!s that are more complex than those from plain vanilla European options. Exotics are largely OTC instruments and their payo!s are structured to suit the needs of individual clients, in terms of maturity date, strike price, and di!erent types of payo!s.   
• Asian options have a payo! which is based on the average price of the underlying asset over the life of the option. They are useful when a corporate or an investor is paying or receiving periodic ‘cash \$ows’ (e.g. foreign currency).   
• Barrier options either ‘die’ or ‘come alive’ before the expiration date, depending on whether the underlying asset price hits (or crosses) one or more barriers. These types of option cost less than the equivalent vanilla options (with the same underlying asset, strike price and time to maturity).   
• Compound options are ‘options on options’. For example, buying a ‘call-on-a-call’ from Morgan Stanley sets the maximum price $K_{1}$ that you pay at $T_{1}$ for ‘delivery’ of a ‘second’ call option on Apple stock (say). This deliverable call option (on Apple stock) will have its own strike $K_{2}$ and maturity date $T_{2}$ $(>T_{1})$ . Like all call options, a compound call option also allows the holder to take advantage of lower cash-market call premia should this occur at $T_{1}$ . At expiration of the compound option at $T_{1}$ , if the premium for a cash-market call option on Apple stock (with strike $K_{2}$ and maturity date $T_{2}$ ), quoted by Goldman is $C_{2}<K_{1}$ then the compound option (with Morgan Stanley) is not exercised but instead the investor simply buys an identical cash-market call option from Goldman’s at the lower price $C_{2}$ .   
• A chooser option allows the investor to choose at a specifc point in time, whether the option is to be a call or a put.   
• Lookback (European) options provide the investor with the opportunity to buy the stock (at maturity of the option) at the lowest price (lookback call) or to sell the stock at the highest price (lookback put) that has occurred over the life of the option.   
• Many exotic (European) options are path dependent with a payo! at maturity that depends on all the possible paths taken by the underlying asset price and not just on the value of the underlying asset price on the expiration date of the option.   
• For many exotic options closed-form solutions (like Black–Scholes) are not possible. Often, they are priced using numerical techniques such as binomial trees or Monte Carlo simulation or by solving a PDE by numerical methods (see Chapter 48).  

# EXERCISES  

# Question 1  

Why might a US importer hedge using a long Asian (average price) call option on euros, with monthly averaging and maturity of one year?  

# Question 2  

Explain the di!erence between path-dependent options and path-independent options and state why an American option is path dependent.  

# Question 3  

Why might an investor holding stocks buy an up-and-out put. Intuitively, why is the price of an up-and-out put less than the price of a plain vanilla put?  

# Question 4  

Why might a speculator buy an up-and-out put?  

# Question 5  

Calculate the price of an (average price) Asian call option on a stock, using a two-period binomial model. Assume $S_{0}=100$ and the stock can go up $15\%$ or down $10\%$ per period. The risk-free rate $r=5\%$ per period and $K=95$ . Include the current stock price when determining the average price.  

# Question 6  

Explain the steps used to price a knock-out call option with an upper barrier $H=110$ (which is greater than the current stock price, $S_{1}=100\$ ) using Monte Carlo simulation. The maturity of the option is $T=1$ year, $\sigma=20\%$ , $r=3\%$ p.a. (continuously compounded) and the barrier condition is monitored every 0.01 years (approximately every 2.5 trading days).  

# Question 7  

You are given the following information. Current stock price $S_{1}=100$ , the drift rate of stock price, $\upmu=5\%$ p.a., risk-free rate $r=0.03$ (continuously compounded), the volatility of stock returns $\sigma=20\%$ p.a., $K=105$ and the time to maturity $T=1$ year. Assume that $d t=0.01$ years (i.e. approximately 2.5 trading days) for the length of each timestep in the MCS.  

Set out the steps you would take to price an Asian (average price) call option using Monte Carlo simulation. Assume $S_{1}=100$ is included in the averaging. (You can also set up the problem in Excel or some other convenient software.)  