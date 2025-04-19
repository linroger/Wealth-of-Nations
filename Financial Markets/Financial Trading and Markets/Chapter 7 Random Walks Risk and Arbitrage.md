---
tags:
  - market_efficiency
  - markov_process
  - martingale
  - random_walks
  - stochastic_process
aliases:
  - Markov Process
  - Random Security Price Changes
key_concepts:
  - Discrete time process
  - Market efficiency
  - Martingale process
  - Random security price changes
  - Stochastic process
---

# Random Walks, Risk, and Arbitrage  

# 7.1 MARKET EFFICIENCY AND RANDOM WALKS  

Market efficiency occurs when prices reflect all available information. Price changes in an efficient market occur when new information becomes available. Since information dissemination (news) arrives randomly, security price changes might be expected to occur randomly. Thus, an efficient market leads to random security price changes. We will discuss market efficiency extensively in Chapter 12; we will introduce sequences of random variables and random walks here.  

# Random Walks and Martin gales  

Why should a trader know about random walks and martin gales? First, consider the well-known investment company advisory: “Past performance is not indicative of future 1   results.” Past performance can be evaluated based on the current price relative to one or more historical prices. If the advisory is true, then future performance is based on a future price and the current price; past prices are irrelevant. In other words, prices follow a Markov process , also known as a  random walk . A random walk is a stochastic process (random sequence) in which a state probability at time  t  depends only on its immediately prior state and not on the remainder of its history.   A stock’s price history has no effect on its future if it follows a random walk. If stock prices do not follow random walks, stock markets cannot be efficient.  
More generally, a  stochastic process  is a sequence of random variables    $X_{t}$   defined on a com $\scriptstyle(\Omega,{\mathcal{F}},\mathbb{P})$   $t$    mon probability space   and indexed by time   . In other  rd  a stochastic process is a random series of values  $X_{t}$   sequenced over time. The values of  $X_{t}$   as  t  varies define one particular sample path of the process associated with a particular state or outcome from    $\Omega$  . A  discrete time process  is defined for a countable set of time periods. A  continuous time process  that is defined over an interval of the real number line consisting of an infinite number of time peri $X$   $\{X_{t}\}$  ods. The  state space   is the set of all possible values of the stochastic process . The state space can be discrete (countable) or continuous. For example, if a stock price changes in increments of  $\S0.01$  , the state space is said to be discrete. The state space for prices is continuous if prices can assume any (positive) real value.  

As might be inferred from above, a  discrete Markov process  or a  discrete random walk  is a non continuous stochastic process in which a state probability at time  $t$   depends only on its immediately prior state at time    $t-1$  :  

$$
P(X_{t}|X_{t-1},X_{t-2},.\,.\,.,X_{0})=P(X_{t}|X_{t-1})
$$  

This means that the probability of a given value for  $X$   at time    $t$   given the historical value of    $X$   one period earlier, two periods earlier, and so on all the back to the start of the process is equal to the probability of that given value for  $X$   at time    $t$   given the value of  $X$   one period earlier. Thus, given the process history    $X_{0},\;X_{1},\;.\;.\;.,\;X_{t-1}$   from its start at time 0 to time  $_{t-1}$  , the probability that that the process will be in state    $X_{t}$   at time    $t$   depends only on its present state  $X_{t-1}$  . This means that a Markov Process has no memory. Only the current state is relevant to predicting its future.  

A  d e martingale process  is a stochastic process    $X_{t}$   in which   $\operatorname{E}[X_{t}|X_{0},X_{1},.\.\.,X_{t-1}]=X_{t-1}$  ½ ' for all  $t=1$   1, 2,  . .. . Thus, a martingale is a process whose future variations have no specific direction that can be discerned from the process history   $(X_{0},\,X_{1},\,.\,.,\,X_{t-1})$  . A martingale is said to be a “fair game” because it will not exhibit consistent trends either up or down. A  submartingale  is a stochastic process  $X_{t}$   in which   $\operatorname{E}[X_{t}|X_{0},\,X_{1},\,X_{2},\,...,\,X_{t-1}]\,\geq\,\bar{X_{t-1}}.$  . A sub martin gale will tend either to trend upward over time or is a martingale. A super martin gale will tend to trend downward over time or is a martingale. Stock prices are often modeled as sub martin gales because they tend to trend upward due to time value of money and investor risk aversion.  

# Brownian Motion Processes  

One particular version of a continuous time-space random walk is a standard  Brownian motion process  $Z_{t},$   also known as a Wiener process. A process    $Z_{t}$   is a standard Brownian motion process if:  

1.  Changes in  $Z_{t}$   over time are independent over disjoint (non-overlapping) intervals of time; that is,  $\mathrm{COV}(Z_{s}-Z_{\tau},\,Z_{u}-Z_{v},)=0$   when  $s>\tau>u>v$  .  

3  $\Omega$  Mathematicians characterize a probability space as consisting of three types of elements: a sample space  of all potential outcomes (e.g., a particular future state of the world), a filtration  ${\mathcal F}.$  , roughly characterized as the information set or history required for valuation (e.g., the security’s price history), and an associated probability measure    $\mathbb{P}$  that maps subsets from    $\Omega$   to [0,1]. Readers are likely to encounter this sort of somewhat formal notation in some finance books (See  Knopf and Teall, 2015  for more complete explanations), but understanding these more technical mathematical definitions is not essential for the remainder of this text.  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/7233cc7506105a02a17d314e36f7453cd72e6c8b42f0dc2e446553bc0d26d068.jpg)  
FIGURE 7.1 Brownian motion: a fractal.  

2.  Changes in  $Z_{t}$   are normally distributed with   $\mathrm{E}[Z_{t}-\,Z_{\tau}]=0$   (standard Brownian motion also a martingale) and  $\dot{\mathrm{E}}[(Z_{t}-Z_{\tau})^{2}]=t-\tau$   for  $t>\tau$  . Thus,   $(Z_{t}-Z_{\tau})\sim\mathrm{N}(0,\,t{-}\tau)$  . 3.  $Z_{t}$   is a continuous function of  t . 4.  The process begins at zero,  $Z_{0}=0$  .  

Brownian motion has a number of interesting traits. First, it is continuous everywhere and differentiable nowhere (it does not smooth as time intervals decrease) under Newtonian calculus. We see in  Figure 7.1  that Brownian motion is a  fractal , meaning that regardless of the length of the observation time period, the process remains a Brownian motion, and can be defined equivalently by a simple change in the time scale. Consider the Brownian motion process represented by the top graph in  Figure 7.1 . If a short segment is cut out and magnified as in the bottom graph in  Figure 7.1 , the graphs look very similar to one another in that they don’t smooth and the variance is proportional to time. Further magnifications of cutouts would continue to result in the same phenomenon. In addition, once a Brownian motion hits a given value, it will return to that value infinitely often. More generally, we will scale the variance by a multiple    $\sigma^{2}$    so that the change in the process  $X_{t}$   from time  $t$   to time    $t+\varDelta t$   takes the form:  

$$
\Delta X_{t}=\sigma\Delta Z_{t}=\sigma(Z_{t+\Delta t}-Z_{t})\!\sim\!N(0,\sigma^{2}\Delta t)
$$  
Consider a more general Brownian motion process    $S_{t}=S_{0}~+~\sigma Z_{t}$  . The graph of a particular possible path of    $S_{t}$   over time  $t$   is similar to the graph of standard Brownian motion. It is continuous and non differentiable (angular movements). The difference is that it can start (time 0) at    $S_{0}\neq0$   rather tha t the origin 0   differ from 1.  $S_{t}$   has a normal distribution with mean  $S_{0}$   and variance  $\upsigma^{2}t\;(S_{t}\,\sim\,N(S_{0},\sigma^{2}t))$  ) since:  

$$
{\frac{S_{t}-S_{0}}{\sigma{\sqrt{t}}}}={\frac{Z_{t}}{\sqrt{t}}}=Z
$$
 ﬃﬃ ﬃﬃ  

where    $Z\sim\Nu(0,\!1)$  . Note that  $\Delta S_{t}=S_{t+\Delta t}-S_{\sf t}\sim\mathrm{N}(0,\sigma^{2}\Delta t).$  .  

We can further generalize this Brownian motion process, to make it more appropriate for modeling stock prices    $S_{t}$  . we will generalize further on the Brownian motion process to allow for a trend or drift  $a$   in the process:  

$$
d S_{t}=a d t+\sigma d Z_{t}
$$  

where    $d S_{t}$   is the infinitesimal change in the stock price at time    $t,\,a$   represents the drift tendency in the value of    $S_{t},$   and    $d Z_{t}$   is the infinitesimal change in the standard Brownian motion process. Because prices of many securities such as stocks tend to have a predictable drift component in addition to randomness, this generalized Brownian motion processes might be more practical for modeling purposes than standard Brownian motion, which only includes a random element. We can write a similar process to model stock returns as a Brownian motion with drift:  

$$
d S_{t}/S_{t}=\mu d t+\sigma d Z_{t}
$$  

The instantaneous change in the stock price is    $d S_{t},$   the instantaneous stock return  $d S_{t}/S_{t}$  trends as per the drift term,    $\mu,$   which represents the instantaneous expected return for the stock, and  $\sigma$   is the instantaneous stock return standard deviation. The corresponding process for the stock price    $S_{t}$   itself is called geometric Brownian motion (or a geometric Wiener) process. The process allows for compounding of returns as stock prices grow or change. It is the most common process used to model stock prices    $S_{t}$  . This geometric Brownian motion process is particularly useful for modeling the relationships between stocks and options and other derivatives.  

# 7.2 RISK  

Definitions of risk vary based on context. Measuring risk can be rather difficult when it is difficult to define risk or to capture all of its characteristics. One perspective on the risk of an investment is that it is simply the uncertainty associated with investment returns or cash flows. However, uncertainty can be a complex quality. Analysts often attempt to quantify risk with absolute measures such as variance or relative risk measures such as beta. Although return variance is a quite simple mathematical concept with many desirable characteristics, its estimation is hampered by the lack of ideal data. Suppose, for example, that we wish to estimate the risk or variance associated with a stock’s returns over the next year. Consider the following discrete expression for ex-ante or forecast variance    $\sigma_{F}^{2}$    that considers all potential return outcomes    $R_{i}$   and associated probabilities  $P_{i}$  :  
$$
\sigma_{F}^{2}=\sum_{i=1}^{n}\left(R_{i}\!-\!E[R_{i}]\right)^{2}P_{i}
$$  

While this expression for ex-ante variance is by definition correct, its computation requires that we identify all potential returns for the security (which might range from minus infinity to positive infinity) along with their associated probabilities. This might be practical when the list of potential returns is small or when we can ascertain a specific return generating process (such as Brownian motion). However, associating probabilities with these returns can be a particularly difficult problem. For example, what is the probability that the return for a given stock will range between   $5\%$   and   $6\%?$   In many instances, we will be forced to either make probability assignments of a somewhat subjective nature or define a joint return and probability generating process for the security. Availability of historical price data can make risk estimation based on historical variances more practical.  

# Historical Volatility Indicators  

Because it is frequently difficult to estimate the inputs necessary to estimate security exante variance, analysts often use the volatility of ex-post or historical returns as a surrogate for ex-ante risk:  

$$
\sigma_{H}^{2}=\sum_{t=1}^{n}\frac{(R_{t}\!-\!\overline{{R}}_{t})^{2}}{n-1}
$$  

where  $R_{t}$   represents the return realized during historical period    $t$  :    $(R_{t}=[(P_{t}-\,P_{t\mathrm{~-~}1})/P_{t\mathrm{~-~}1}])$  in this    $n$   time period framework.  Table 7.1  presents sample monthly historical price data for GM stock along with monthly returns computed from these prices. We see below that the traditional sample monthly variance estimator for this stock based on these 23 returns equals 0.012:    $\begin{array}{r}{\sigma_{H}^{2}=\dot{\sum_{t=1}^{n}{(R_{t}-\check{R}_{t})^{2}}}/(n-1)=0.012.}\end{array}$   P   012. If we were to assume that returns follow a Brownian motion process (or at least assume that stock returns are uncorrelated over time), the annualized variance would be   $0.144=0.012\times12.$  . Use of the traditional sample estimator to forecast variance requires the assumption that stock return variances are constant over time, or more specifically, that historical return variance is an appropriate indicator of future return variance. While this can often be a reasonable assumption, firm risk conditions can change and it is well documented that price volatility does fluctuate over time (see, for example,  Officer, 1971 ). In addition, note that the sample variance estimator rather than the  
TABLE 7.1 Traditional Sample Estimators for GM Stock, October 2000 to September 2002 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/0b39d7658c1873b6417c897766a17c35d031f712606a2686c96787f1546ba1cf.jpg)  

population estimator is proposed in  Equation (7.2) . This difference becomes more significant with smaller samples.  

Using  Equation (7.2)  to estimate security variance requires that the analyst choose a sample series of prices (and dividends, if relevant) at  n  regular intervals from which to compute returns. Two problems arise in this process:  

1.  Which prices should be selected and at what intervals?

 2.  How many prices should be selected?  

First, since each of the major stock markets tend to close at regular times on a daily basis, closing prices will usually reflect reasonably comparable intervals, whether selected on a daily, weekly, monthly, annual, or other basis. Those prices closer to the date of computation will probably better reflect security risk (e.g., price volatility of a security 30 years ago hardly seems relevant today). On the other hand, longer-term returns, such as those computed on a monthly or annual basis, might more closely follow a normal distribution than returns computed on a daily or shorter-term basis. This is a highly desirable quality, since many of the statistical estimation procedures used by analysts assume normal (or lognormal) distribution of inputs; the characteristics of most non-normal distributions are not well known.  

Generally speaking, more prices or data points used in the computation process will increase the statistical significance of variance estimates. However, this leads to a dilemma: more data points, particularly pertaining to longer-term returns, will require prices from the more distant, but less relevant past. On the other hand, shorter estimation intervals may result in non-normal return distributions as well as auto correlation issues.  
Hence, the analyst must balance the needs for a large sample to ensure statistical significance, recent data for relevance, and longer-term data for independence and normality of distribution. These conflicting needs call for compromise. One convention that has developed over the years both in academia and in the industry is based on computations of five years of monthly returns.  

Nonetheless, numerous difficulties still remain with this estimation procedure. For example, as we discussed above, variances are not necessarily stable over time. In our numerical illustration, higher-volatility periods are clustered together as are lower volatility periods, in a manner similar to actual return variances. Second, returns themselves might not be independently distributed. In our numerical illustration, returns are somewhat inversely correlated, potentially leading to significant differences in our variance estimates. Thus, both problems arise in our numerical illustration data in Table 7.1 . In addition, nontrading may omit returns data for computations, creating more problems with historical variance estimations. Finally, the traditional historical volatility estimator can involve collecting large amounts of data and tedious calculations.  

# Extreme Value Estimators  

Two difficulties associated with the traditional sample estimator procedure, time required for computation and arbitrary selection of returns from which to compute volatilities might be dealt with by using extreme value estimators. Extreme value estimators are based on high and low values (and sometimes other parameters) realized by the security’s price over a given time period.  

For example, consider the Parkinson extreme value estimator ( Parkinson, 1980 ). This estimating procedure is based on the assumption that underlying stock returns are lognormally distributed without drift. Given this distribution assumption, the underlying stock’s realized high and low prices over a given period provide information regarding the stock’s variance. Thus, if we are willing to assume that the return distribution is to be the same during the future period, Parkinson’s estimate for the underlying stock return variance is determined as follows:  

$$
\sigma_{p}^{2}=0.361\cdot\left[\ln\left({\frac{H I}{L O}}\right)\right]^{2}
$$  

where    $H I$   designates the stock’s realized high price for the given period and    $L O$   designates the low price over the same period. The high and low prices for GM in October 2002 were 47.51 and 38.11 for October 2002, the most recent month listed in  Table 7.1 . The extreme value estimator for this month would be calculated as follows:  

$$
\sigma_{p}^{2}=0.361\cdot\left[\ln\left({\frac{H I}{L O}}\right)\right]^{2}=0.361\cdot\left[\ln\left({\frac{47.51}{38.11}}\right)\right]^{2}=0.017546
$$  

Alternatively, we could obtain an average monthly variance for the 24-month period covered in the table (ignoring the possibility of intraday highs and lows that differ from closing prices).   Since our price data cover 24 months, we will divide this figure by 24 to obtain our monthly variance. The Parkinson measure results in a monthly variance estimate equal to 0.007414 for GM over the period October 2000 to September 2002 in Table 7.1 :  
$$
\sigma_{p}^{2}=0.361\cdot\left[\ln\left(\frac{H I}{L O}\right)\right]^{2}/m=0.361\cdot\left[\ln\left(\frac{63.68}{38.9}\right)\right]^{2}/24=0.007414
$$  

Clearly, the Parkinson variance estimate will be easy to obtain when periodic high and low prices for a stock are regularly published as they are for the NYSE and many other stocks. Furthermore, the econometric efficiency of the Parkinson procedure is several times higher than the traditional sample estimation procedure. Using the extreme value estimator might be as simple as inserting into  Equation (7.3)  the 52-week high and low prices. Note that the Parkinson estimate is significantly smaller than the monthly historical estimate. This difference draws largely from the negative auto correlation (stock price changes are inversely correlated from one time period to the next) in the returns series.  

# 6 Implied Vol at ili ties  

A problem shared by both the traditional sample estimating procedures and the extreme value estimators is that they require the assumption of stable variance estimates over time; more specifically, that future variances equal or can be estimated from historical variances. A third procedure first suggested by  Latane and Rendleman (1976)  is based on market prices of options that might be used to imply variance estimates. For example, the Black-Scholes option pricing model and its extensions provide an excellent means to estimate underlying stock variances if call prices are known. Essentially, this procedure determines market estimates for underlying stock variance based on known market prices for options on the underlying securities. Consider our stock example from Table 7.1  on September 3, 2002 when GM stock closed at   $\S38.9$  . Suppose that a onemonth   $\mathit{\check{T}}=1,$  ) call on GM stock with a striking price equal to   $\S40$   was at the same time trading for    $c_{0}\!=\!\S1.16$  :  

$$
T=1~~~~~r_{f}=0.005~~~~~c_{0}=\S1.16~~~~~X=\S40~~~~~S_{0}=\S38.9
$$  

5 Accuracy of the Parkinson measure can be improved if the sample period can be subdivided into  $n$   equal sub-periods such that variance is estimated as follows\*:  

$$
\sigma_{p}^{2}={\frac{0.361}{n}}\cdot\left[\sum_{t=1}^{n}\ln\left({\frac{H I_{t}}{L O_{t}}}\right)\right]^{2}
$$  

This is the more general form of the Parkinson estimator. We should obtain an intraday highs and lows for each of the 24 months, and then square the sum of their logs. The constant,  $0.361,$   is the normal density function constant,  $1/\sqrt{2\pi}$  ﬃﬃﬃﬃﬃﬃ .  

6 This section assumes a background in or a basic understanding of the Black-Scholes options pricing model. If necessary, see Section 7. A.2 in this chapter’s appendix for a review of options and the Black-Scholes option pricing model and  Section 7. A.3  for additional discussion and examples of estimating implied vol at ili ties.  
where    $r_{f}$   equals the monthly riskless return rate and  $X$   is the option striking price. If investors use the Black-Scholes option pricing model to value calls, the following must hold:  

$$
\begin{array}{l}{{1.16=38.9\cdot N(d_{1})-40e^{-r_{f}T}\bullet N(d_{2})}}\\ {{\displaystyle d_{1}=\frac{\ln\left({\frac{38.9}{40}}\right)+(0.005+0.5\sigma^{2})\bullet1}{\sigma\sqrt1}}}\\ {{\displaystyle d_{2}=d_{1}-\sigma\sqrt1}}\end{array}
$$  

We find that this system of equations holds when    $\upsigma^{2}=0.01$  . Thus, the market prices this call as though it expects that the variance of anticipated monthly returns for the underlying stock is 0.01. The annualized variance would be 0.12 (12 times the monthly variance).  

Unfortunately, the system of equations required to obtain an implied variance has no closed form solution. That is, we will be unable to solve  Equation (7.4)  explicitly for variance; we must search, iterate, and substitute for a solution. You can substitute trial values for    $\upsigma^{2}$    until you find one that solves the system. A significant amount of time can be saved by using one of several well-known numerical search procedures such as the method of bisection or the Newton-Raphson method.  

Table 7.2  presents, describes, and compares basic risk measures discussed in this chapter. There is no consensus as to which measure is clearly best, although some measures  

TABLE 7.2 Basic Risk Measures 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/23de29773c03460e319cc4ef70b23c137350f1c70fbc3a5bb5c228e2b86c81ec.jpg)  

7 These and other numerical procedures for estimating implied vol at ili ties are discussed in  Section 7. A.3  in the Appendix to this chapter. More discussion of the Black-Scholes and other option pricing models is available in Chapter 9.  
perform better under some circumstances. Risk measures need to be evaluated on the basis of the availability of appropriate data and appropriateness of underlying assumptions. In addition, all of the measures that we have discussed in this chapter are incomplete in that they do not account for factors such as skewness (unequal concentrations of potential outcomes unequally distributed below and above the mean) and fat tails (kurtosis or high probabilities of extreme events). No single risk measure can serve adequately to capture all sources of security risk. Hence, the trader or securities analyst needs to use judgment in the application and interpretation of risk measures.  

# 7.3 ARBITRAGE  

Arbitrage, perhaps the single most important pricing tool in modern finance, is defined as the simultaneous purchase and sale of assets or portfolios yielding identical cash flows. Assets generating identical cash flows should be worth the same amount. This is known as the  Law of One Price . If assets generating identical cash flows sell at different prices, opportunities exist to create a profit by buying the cheaper asset and selling the more expensive asset. The ability to realize a profit from this type of transaction is known as an  arbitrage opportunity . Rational investors in such a scenario will seek to purchase the under priced asset, financing its purchase by simultaneously selling the overpriced asset. The  arb it rage ur  will execute such arbitrage transactions, continuing to earn arbitrage profits in increasing quantities until the arbitrage opportunity is eliminated. If markets are competitive, the arb it rage ur’s purchases of the under priced asset will bid its price up while the arb it rage ur’s selling transactions will force down the price of the overpriced asset. These arbitrage transactions should continue until no assets are over- or under priced. Hence, arb it rage urs should force assets that produce identical cash flow structures to have identical prices.  

Classic arbitrage  is the simultaneous purchase and sale of the same asset at a profit. For example, if gold is selling in London markets for   $\mathbb{S}1200$   per ounce and in New York markets for  $\mathbb{S}1220$   per ounce, a classic arbitrage opportunity exists. An investor could purchase gold in London for   $\mathbb{S}1200$   per ounce and simultaneously sell it in New York for   $\mathbb{S}1220$  . This results in a   $\S20$   profit per “round-trip” transaction. The transactions involve no risk since both the selling and purchase prices are known and are executed simultaneously. Furthermore, no initial net investment is required because the transactions offset each other; the proceeds of the sale are used to finance the purchase. Thus, if a classic arbitrage opportunity exists, an investor will have the opportunity to make a riskless profit without investing any of his own money. If the laws of supply and demand are not impeded by market inefficiencies, investors will flock to exploit this opportunity. Their buying pressure in London markets will force the London price to rise; their selling pressure in New York markets will force the New York price down. Buying and selling pressure will persist until the prices in the two markets are equal. Thus, significant classic arbitrage opportunities are not likely to persist long in unimpeded free markets. Perhaps an even simpler form of arbitrage opportunity exists in a  crossed market , where a bid exceeds an offer price. This can occur when a slow trader’s quote is not withdrawn quickly enough, enabling a prospective buyer to purchase a security at the lower offer price and simultaneously sell it at the higher bid price.  
More generally, arbitrage refers to the near simultaneous purchase and sale of portfolios generating similar cash flow structures. For example, the cash flow structure of a long position in a forward contract can be replicated by a portfolio consisting of a long position in a call and short position in a put. Although the contracts in the options portfolio are different from the forward contract, the anticipated cash flows are identical. Thus, if the portfolio produces a lower initial cash flow, it can be sold (shorted) while a long position is taken in the forward contract. These positions in sum comprise an arbitrage portfolio. Future cash flows are offset because they are identical, and net sales proceeds from the options portfolio will exceed those of the futures contract. Similarly, arbitrage can refer to offsetting trades of securities whose payoff structures are strongly correlated. For example, the cash flow structure of an automobile industry stock can be nearly replicated with the cash flow structure of a portfolio of other securities designed to be strongly correlated with the stock. When prices of the portfolio and the stock diverge, arbitrage opportunities might arise. Sometimes, these opportunities are referred to as  quasi-arbitrage  in that they are not necessarily completely riskless or that their transactions are not necessarily executed simultaneously.  

The principle of arbitrage is the foundation underlying relative securities valuation. That is, we are able to price securities relative to one another or relative to replicating portfolios when arb it rage urs are able to exploit violations of the  law of one price . The noarbitrage price of a security is the value of the portfolio constructed to replicate the security. When the law of one price does not hold, one (or both) of the following will hold:  

1.  There exist opportunities to secure riskless arbitrage opportunities by buying  

under priced assets while selling overpriced assets.

 2.  There exists some sort of market imperfection such as high transactions preventing arb it rage urs from exploiting arbitrage opportunities.  

# Pairs Trading and Stat-Arb  

As with other arbitrage strategies,  pairs trading  involves the simultaneous purchase and sale of similar securities. Pairs trading involves taking offsetting positions in two different stocks (perhaps options or index contracts) with strong returns correlations, one long and one short, such that gains in one position are expected to more than offset losses in the other position. One simple strategy illustration might involve taking a long position in GM stock based on recent price decreases along with a short position in Ford based on recent price increases. If the investor generally expects that automobile stock prices ought to be strongly correlated, and should have been performing similarly, she might expect that future short term performance of the under performing stock will exceed the performance of the stock with the stronger current price level. Pairs trading is essentially an arbitrage strategy anticipating that the deviation of a recent pricing relation between two securities is only temporary. Holding periods for most pairs trading strategies tend to be quite short, ranging from seconds to days. Pairs traders typically focus either on the ratio between prices of two securities or the difference between their prices. One cannot expect to consistently earn high returns based on such strategies, so that many pairs traders execute many such trades over many different pairs of stocks with the expectation that their strategies will be correct more often than they are wrong. Furthermore, many pairs traders will seek to hold “portfolios of pairs” whose expected returns will tend to be uncorrelated with those of the market as a whole. Such “beta-neutral” portfolios might be expected to be insulated from large losses related to stock market swings.  
In a manner similar to pairs trading,  stat-arb  (statistical arbitrage) strategies seek to exploit mispricing opportunities while minimizing risk. Stat-arb strategies focus on statistical or historical relationships among securities and seek to exploit price divergences as portfolios of securities diverge from “normal” pricing relationships.  Khandani and Lo (2007)  refer to stat-arb as a set of “highly technical short-term mean-reversion strategies involving large numbers of securities (hundreds to thousands, depending on the amount of risk capital), very short holding periods (measured in seconds to days), and substantial computational, trading, and IT infrastructure.” There is no single stat-arb strategy; there are many types, all of which involve large sets of securities whose statistical price relationships relative to each other diverge from what the investor expects.  

# 7.4 LIMITS TO ARBITRAGE  

Arbitrage opportunities are the traders’ “pot of gold at the end of the rainbow.” Once found, they are free sources of money. In theory, arbitrage is riskless because asset cash flows are known to be offsetting in the future and because initial transactions are executed simultaneously at known prices. Unfortunately, the reality is often quite different. For example,  implementation risk  arises because transactions might not be executed or be executed at prices that differ from what the arb it rage ur anticipated. Perhaps even worse, one leg of the arbitrage transaction might fail to execute, leaving the arb it rage ur unhedged in an undesirable portfolio. Arb it rage ur profit opportunities should cause markets to respond more efficiently to new information and mispricing of securities. However, sometimes arb it rage urs simply don’t fully understand or appreciate the models that they trade on. This misunderstanding is called  model risk . In many instances, model risk arises from a simple failure to appreciate the differences between model assumptions and reality. Despite potential profit opportunities, some markets are slow to react to arbitrage opportunities and some do not react at all. In fact, some markets may move opposite to the arbitrageur’s expectations, at least in the short run. This might render traders unable to survive in the long run. This risk is called  basis risk . If trading is difficult or expensive, perhaps due to high transaction costs, price adjustments to arbitrage may be delayed, prevented, or again, move further in the unanticipated direction. Furthermore, the arb it rage ur is subject to margin calls, forced sell-outs and forced buy-ins, potentially shortening her time horizon to recover from the unanticipated price change. Basis risk is mitigated if the arbitrageur is able to count on a known terminal liquidation position (such as with short-term options, futures, and Treasury bills) and maintain her portfolio hedge until that date.  
Thus, short-lived securities such as options tend to have smaller basis risk than long-lived securities such as common stock. An additional source of arbitrage risk, particularly when instruments are not exchange-traded, is  counter party risk , which is the potential that a trade counter party fails to fulfill his side of a transaction.  

De Long et al. (1990)  argue that the short investment horizons of arb it rage urs can prevent them from taking advantage of errors or noise in market prices. If it appears that price deviations from fundamental values might persist, arb it rage urs might avoid potentially profitable opportunities, causing even greater risk and deviations from fundamental values. This might enable noise traders to earn even higher returns from their pricing errors, causing pricing bubbles to form. For example, consider the case of Long Term Capital Management (LTCM), which was founded in the early 1990s by John Meriwether, formerly head of the fixed income unit of Salomon Brothers, Inc. He brought in famed academics Myron Scholes and Robert Merton, developers of some of the most important derivatives and arbitrage strategies of the time, and the fund focused much of its trading activity on derivatives and fixed income. LTCM realized enormous returns and growth until 1998, when it lost over   $\S4$   billion in one spectacularly disastrous quarter, forcing the fund into liquidation and threatening contagion throughout financial markets and potential market meltdown. In many instances as we will discuss shortly, LTCM took appropriate positions in arbitrage portfolios, but the fund was so highly leveraged that it could not withstand short-term market moves against their positions.  

Among the most important strategies to LTCM was to exploit  convergence trades , which often involved taking long positions in cheaper foreign debt and short positions in more expensive U.S. Treasury securities. The foreign debt instruments were generally cheaper because they were not as liquid; thus they had higher yields. However, holding positions over the long term meant that the cheaper foreign debt would eventually rise in prices relative to the more expensive U.S. Treasury securities. LTCM, with its less than  $\S5$   billion in equity capital, controlled over   $\S100$   billion in assets and approximately   $\S1.25$   trillion notional in derivative contracts. Unfortunately for LTCM, the Southeast Asian financial crisis in 1997 ' 1998 followed by the Russian financial crisis of 1998 caused a “flight to liquidity,” meaning in this case that investors sold non-U.S. debt, forcing down non-U.S. debt prices, and purchased U.S. Treasury securities, forcing U.S. debt prices up. LTCM’s equity capital was wiped out within days, and the fund was bailed out by a consortium of financial institutions under the supervision of the U.S. Federal Reserve System. While LTCM’s strategy may well have been correct had it been able to survive for an extended period of time, the fund was too highly leveraged to survive extreme short-term volatility.  

One of LTCM’s equity market arbitrage ventures involved the Royal Dutch/Shell Group, a dual-listed company independently incorporated in the Netherlands and the UK. This arrangement originated from a 1907 alliance agreement between Royal Dutch and Shell Transport in which the two companies agreed to merge their interests on a   $60/40$   basis. Royal Dutch trades primarily in the United States and the Netherlands while Shell trades primarily in London. After adjusting for foreign exchange rates, shares of the two firms’ stock should trade at a 1.5:1 ratio. However, this anticipated trading ratio has deviated by more than   $35\%$  , well beyond levels of tax differentials and transaction costs. In the summer of 1997, Royal Dutch traded at an  $8\%$   to  $10\%$   premium over its 1.5 expected level relative to Shell. To exploit this differential, LTCM had taken significant arbitrage positions on the two stocks. As the differential widened to   $20\%$   in 1998, LTCM increased its positions until financial distress caused by trading activities elsewhere in the fund (related to the economic crisis in Russia) forced the firm to liquidate. The positions taken in Royal Dutch/Shell by LTCM were ultimately proven correct, but not until 2001 when the fund was no longer in existence. Rosenthal and Young (1990)  argue that significant mispricing in dual-listed companies has prevailed over long periods of time without satisfactory explanations. Nevertheless, arbitrage can sometimes take significant amounts of time to equalize prices, causing arb it rage urs to maintain positions longer than they are able.  
In another well-publicized failure of arbitrage, dating from a March 2000 equity carveout, 3Com spun off its Palm division, a maker of handheld computers. 3Com retained  $95\%$  of the shares of Palm and announced that each 3Com shareholder would ultimately receive 1.5 shares of Palm for each share of 3Com. The remaining  $5\%$   of Palm shares were issued at   $\S38$   per share, increasing to   $\S165$   by its first day of trading before closing at  $\S95.06\$   (see  Lamont, 2002 ). Remember that ownership of one 3Com share implied ownership of 1.5 shares of Palm stock. The stocks of the two companies should have moved in tandem, but on the date of the IPO, 3Com actually decreased by  $21\%$   to   $\S81.81$   as Palm increased. This  $\S81.81$   is substantially less than the  $\S142.59$   price implied by the 1.5 shares of Palm stock due to each 3Com shareholder   $(1.5\ \times\ \S95.06=\S142.59)$  , implying that the remainder of   $3{\mathrm{Co}}{\mathrm{m}},$  , on a per share basis, was worth negative   $\S60.78$  . This negative stub value (the whole is worth less than the sum of the parts; in particular, the parent and the subsidiary are worth less than the subsidiary alone) seems particularly unlikely, since 3Com had about   $\S10$   per share in cash and marketable securities alone. In other words, what happened wasn’t rational, given the numbers, or just could not have been sustainable had investors been able to arbitrage. On the other hand, prospective arb it rage urs found themselves unable to short sell shares because the two stocks were under different national regulatory authorities and the outcome of the Palm carve-out was still uncertain. Thus, arbitrage and price correction could not be implemented because the short selling mechanism was not available for the Palm IPO. Therefore, as  Cherkes, Jones and Spatt (2013)  argue, the apparent mispricing scenario might have been perfectly rational given the prevailing market inefficiencies.  

Such negative stub values are not uncommon. For example, in 1923, Benjamin Graham chronicled his purchase of shares of stock in Du Pont, a well-established firm that had negative stub value given its investment in the new company General Motors.  Lamont and Thaler (2003)  identified five other 1990s technology equity carve-outs with negative stub values: UBID, Retek, PFSWeb, Xpedior, and Stratos Lightwave. Arbitrage in each of these cases was impeded by the inability to short sell. Many research analysts (e.g.,  Colvino, 2014 ) argued that between 2014 and 2016, given its investment in Yahoo Japan and Alibaba, the stub value of Yahoo’s core business was negative, perhaps as much as negative  $\S40$   billion, despite significant short interest in the shares.  Mitchell et al. (2002)  found 82 similar negative stub value scenarios in U.S. markets between 1985 and 2000. Nevertheless, in most cases, arbitrage was impeded by inability to short sell, high transaction costs, and difficulty in getting reliable price quotes or other information. But, Mitchell et al. found that approximately  $30\%$   of negative stub values were never eliminated through arbitrage. Some of the spin-offs failed, and others may have faced this risk. But, even these conditions probably cannot explain particularly large negative stub values.  
There are even more obvious limits on many arbitrage opportunities. Restrictions on trading and transaction costs can be major barriers to arbitrage. For example,  Han and Wang (2004)  found that upper and lower fractional ownership bounds on the holdings of a stock can limit institutional arbitrage and contribute to the momentum of returns for that stock. For example, many countries such as China restrict proportional ownership and even the United States imposes insider trading regulations on major shareholders (e.g., the Williams Amendment).  Pontiff (1996)  argued that large differences in prices and net asset values in closed end funds result when fund portfolios are more difficult to replicate, when trading costs are high for the stocks in fund portfolios, and when stocks in the funds paid dividends. Thus, difficulties in replicating assets do limit arbitrage opportunities. Similarly, traders know well that Treasury instruments regularly trade at lower yields than nearly identical “off-the-run Treasuries.” Violations of the simple put-call parity relation regularly arise when there are restrictions on short-selling underlying securities. Transaction costs often require that the arb it rage ur set upper and lower bounds on security purchase and selling prices, essentially determining the interval within which the no-arbitrage security price must fall.  

# Additional Reading  

Pearson (1905)  provides a nice, 100-year-old nontechnical discussion of the random walk process.  Knopf and Teall (2015)  offer a more technical introduction to random walks, martin gales, and stochastic processes in finance.  Lamont (2002)  provides a very readable case study referred to in this chapter concerning the anomalous behavior of the Palm and 3-Com shares following their takeover scenario. The case is important because it depicts the failure of the market to provide rational relative pricing for the two firms.  Lamont and Thaler (2003)  provide a listing of other firms demonstrating negative stub values. Lowenstein’s 2000  book  When Genius Failed: The Rise and Fall of Long-Term Capital Management  is an excellent history of the rise and fall of LTCM.  

# References  

Brenner, M., & Sub rahman yam, M. G. (1988). A simple formula to compute the implied standard deviation. Financial Analysts Journal ,  5 , 80 ' 83. Cherkes, M., Jones, C., & Spatt, C. (2013).  A solution to the Palm—3Com spin-off puzzles.  Unpublished working paper. New York: Columbia University. Colvino, S. (2014).  Yahoo stub value . Markit Research, September 30, 2014. Available at  , https://www.markit.com/ Commentary/News Comment a rie File?CMSID  $=$  aade814d646749c3a7b2701931e606d0 .  Accessed 27.07.16. Corrado,  $\mathrm{C.,}$   & Miller, T. W. (1996). A note on a simple, accurate formula to compute implied standard deviations. Journal of Banking and Finance ,  20 , 595 ' 603. De Long, J. B., Shleifer, A., Summers, L. H., & Waldman, R. J. (1990). Noise trader risk in financial markets. Journal of Political Economy ,  98 (4), 703 ' 738. Han, B., & Wang, Q. (2004).  Institutional investment constraints and stock prices . Dice Center Working Paper No. 2004-24. Available at:  , http://ssrn.com/abstract  $=628683>$   Accessed 12.01.12. Khandani, A. E., & Lo, A. W. (2007). What happened to the quants in August 2007?  Journal of Investment Management ,  5 (4), 5 ' 54. Knopf, P., & Teall, J. (2015).  Risk neutral pricing and financial mathematics: A primer . San Diego: Academic Press. Lamont, O. (2002). The curious case of Palm and 3 Com. In J. Pickford (Ed.),  Mastering investment  (pp. 261 ' 266). New York: Prentice Hall. Lamont, O., & Thaler, R. (2003). Can the market add and subtract? Mispricing in tech stock carve-outs.  Journal of Political Economy ,  111 , 227 ' 268.  
Latane, H., & Rendleman, R. (1976). Standard deviations of stock price ratios implied by option prices.  Journal of Finance ,  31 , 369 ' 381. Lowenstein, R. (2000).  When genius failed: The rise and fall of Long-Term Capital Management . New York: Random House. Mitchell, M., Pulvino, T., & Stafford, E. (2002). Limited arbitrage in equity markets.  Journal of Finance ,  57 (2), 551 ' 584. Officer, R.A. (1971).  A time series examination of the market factor of the new york stock exchange  (Ph.D. dissertation). University of Chicago. Parkinson, M. (1980). The extreme value method for estimating the variance of the rate of return.  Journal of Business ,  57 , 61 ' 65. Pearson, K. (1905). The problem of the random walk.  Nature ,  72 , 342. Pontiff, J. (1996). Costly arbitrage: Evidence from closed end funds.  Quarterly Journal of Economics ,  111 , 1135 ' 1152. Rosenthal, L., & Young, C. (1990). The seemingly anomalous price behavior of Royal Dutch/Shell and Unilever N.V./PLC.  Journal of Financial Economics ,  26 , 123 ' 141.  

# 7.5 EXERCISES  

1.  Now, let’s consider martingale and Markov processes in a standard Blackjack game. Cards are dealt one at a time from a standard 52-card randomly shuffled deck, and points are awarded to the lone recipient based on the number on the card (2 to 10) or 11 if the dealt card is a face card or Ace. Let    $S_{t}$   represent the number of points to be held by the recipient after  $t$   cards have been dealt by the dealer. For parts a through c, suppose that the cards have been dealt without replacement. For parts d, e, and f, assume that the cards have been dealt with replacement and that 1 point is awarded if the number on the card is a 2 through a 6, 0 points are awarded if the number on the card is 7, 8, or 9, and  $^{-1}$   point is awarded if the card is a 10, a face card, or an ace. We note that this is the most common point system used by card counters playing blackjack in casinos. a.  Is this process stochastic? b.  Is this process Markov? This part of the problem is a little more difficult. c.  Is this process a sub martin gale? d.  Is this process (with replacement) Markov? e.  Is this process (with replacement) a sub martin gale? f.  Is this process (with replacement) a martingale?  

2.  Let   $\{r_{\mathrm{t}},\,t\,\geq\,0\}$   (the return on a stock) be an arithmetic Brownian motion. a.  Suppose that  $r_{\mathrm{t}}$   is made up of two components, an instantaneous drift with expected value    $\mu=.05$   and a variance    $\widehat{\sigma}^{2}=.25.$  . What is the probability that  $r_{5}$   is between .3 and .5? b.  Suppose that the price of a stock follows a geometric Brownian motion process. Suppose that the stock’s initial value is  $S_{0}=1.$  , and its instantaneous drift  $r_{\mathrm{t}}$   has an expected value    $\mu=.05$   per year and an annual variance    $\sigma^{2}=.25$  . What is the probability that the stock is worth more than 2 in five years    $P[S_{5}\,>\,2]^{\prime}$  ? c.  Is the return process for this stock a martingale?  

3.  Suppose a stock price    $S_{t}$   follows a Brownian motion process with an initial price of  $S_{0}=\S50$   and a variance per time period equal to  $\sigma^{2}\,{\overset{.}{=}}\,4$  . What is the probability that the stock price is less than  $\S56$   at time 3?  
4.  Historical  percentage  stock returns for the Robinson and Boyer Companies are listed in the following chart along with percentage returns on the market portfolio:  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/0385af33a4f1ece195a3f3bd1e831668df22e40a66c2707ddfbfa22f2d6c9ee2.jpg)  

Calculate the following based on the preceding table:  

a.  mean historical returns for the two companies and the market portfolio. b.  variances associated with Robinson Company returns and Boyer Company returns as well as returns on the market portfolio. c.  Forecast a variance and a standard deviation of returns for both the Robinson and Boyer Companies based on your calculations in parts a and b.  

5.  The following table represents outcome numbers, probabilities, and associated returns for Stock A:  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/db99766b4b7a36b258d5af90d570a235db3dc56bf820466591cd4d14277de26e.jpg)  

Thus, there are 10 possible return outcomes for Stock A. a.  What is the probability associated with outcome 9? b.  What is the standard deviation of returns associated with Stock A?  

6.  The Nettles Company management projects an expected return level of   $15\%$   for the upcoming year. Assuming that returns are normally distributed with a standard deviation equal to. 1, what is the probability that the actual return level will: a.  fall between   $5\%$   and  $25\%?$  b.  fall between   $15\%$   and  $25\%$  ? c.  exceed  $25\%'$  ? d.  exceed  $30\%!$  ?  
7.  What would each of the probabilities in problem 4 be if Nettles Company management were certain enough of its forecast to associate a  $5\%$   standard deviation with its returns projection?  

8.  The following table presents sample daily historical price data for a stock whose returns are given in the third column.  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/7725e0c3e3abe0e02d4987e0d74cd618ce189f2137b1b860c6ad0f20137b2c08.jpg)  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/6338bafcca2b8dd3ca33d250e4e55249076b5fdb42936e7c17621bf7c17a23f8.jpg)  

a.  Based on a traditional sample estimator, calculate a daily variance estimator for this stock. b.  Assume that returns follow a Brownian motion process (at least that stock returns are uncorrelated over time) and that there are 30 trading days per month. What would be the monthly variance for this stock? c.  What would be the Parkinson extreme value estimated daily returns variance for this stock?  

9.  The following daily prices were collected for each of three stocks over a 12-day period.  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/0329bd36911d1de591045737a67402d006597225f093de8cf01410033bcd7849.jpg)  

Based on the data given above, calculate the following:  

a.  Returns for each day on each of the three stocks. There should be a total of 10 returns for each stock ' beginning with the date   $1/10$  . b.  Average daily returns for each of the three stocks. c.  Daily return standard deviations for each of the three stocks.  

10.  Torre Company stock realized a 52-week high of   $\S50$   per share and a 52-week low of  $\S25$  . What is the Parkinson extreme value estimate for variance for this stock? What would be the corresponding standard deviation estimate?  
11.  Suppose that there is a six-month call currently trading for   $\S8.20$   while its underlying stock is currently trading for  $\S75$  . Other details for this example are as follows:  

$$
T=0.5\;\;\;\;\;r_{f}=0.10\;\;\;\;c_{0}=8.20\;\;\;\;X=80\;\;\;\;S_{0}=75\;\;\;
$$  

What is the volatility (standard deviation) implied by the market price of this call?

 12.  Santo Company stock currently trades for   $\S50$   per share. The current riskless return rate is 0.06. Under the Black-Scholes framework, what would be the standard deviations implied by six-month (0.5 year) European calls with current market values based on each of the following striking prices?  

a.    $X=40$  ;  $c_{0}=11.50$  b.  $X=45$ ; $c_{0}\,{=}\,8.25$ c.  $X=50$ ; $c_{0}\,{=}\,4.75$ d.    $X=55$  ;  $c_{0}\,{=}\,2.50$  e.  $X=60$ ; $c_{0}=1.25$  

13.  In principle, simultaneous execution of transactions at known prices producing offsetting future cash flows makes arbitrage riskless. However, in practice, even in the simplest scenarios, such arbitrage does involve several risks. What are these risks?  
# 7. A.1 RETURN AND RISK SPREADSHEET APPLICATIONS  

Table 7. A.1  contains spreadsheet entries for computing stock variances, standard deviations, and co variances. The table lists daily closing prices for Stocks X, Y, and   $Z$  from January 9 to January 20 in cells B3:B14, E3:E14, and H3:H14. From these prices, we compute returns in Cells B19:B29, E19:E29, and H19:H29. Variance, standard deviation, and covariance statistics in rows 30 to 38 are computed from formulas displayed in Table 7. A.2 .  

Formulas for computing returns are given in rows 19 to 29 in  Table 7. A.2 . Means, variances, standard deviations, co variances, and correlation coefficients are computed in rows 30 to 38. Row 30 computes the arithmetic mean return for each of the three stocks.  Table 7. A.2 lists formulas associated with the values in cells A30:H38. The  $=$  (Average) function may be typed in directly as listed in  Table 7. A.2  row 30 or obtained from the Paste Function button  $(f_{x})$   menu under the Statistical submenu. Entry instructions are given in the dialogue box obtained when the Average function is selected. The variance formulas in row 31 are based on the sample formula; the variance (P) formulas in row 32 are based on the population formula. Standard deviation sample and population results are given in rows 33 and 34. Co variances and correlation coefficients are given in rows 35 to 38.  

# 7. A.2 A PRIMER ON BLACK-SCHOLES OPTION PRICING  

# Calls and Puts  

First, we will introduce a few option basics. A  stock option  is a legal contract that grants its owner the right (not obligation) to either buy or sell a given stock. There are two types of stock options: puts and calls. A  call  grants its owner to purchase stock (called underlying shares) for a specified exercise price (also known as a striking price or exercise price) on or before the expiration date of the contract. In a sense, a call is similar to a coupon that one might find in a newspaper enabling its owner to, for example, purchase a roll of paper towels for one dollar. If the coupon represents a bargain, it will be exercised and the consumer will purchase the paper towels. If the coupon is not worth exercising, it will simply be allowed to expire. The value of the coupon when exercised would be the amount by which value of the paper towels exceeds one dollar (or zero if the paper towels are worth less than one dollar). Similarly, the value of a call option at exercise equals the difference between the underlying market price of the stock and the exercise price of the call.  
TABLE 7. A.1 Stock Prices, Returns, Risk, and Co-Movement 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/ade6bff2d42a42e7ce40996a1ecbaa379b4ec60bbcc1639214d3962adbfe9b8c.jpg)  
TABLE 7. A.1 (Continued) 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/cbc0e250d7e21a69118613efc76db7c83684e30ee2a9649b44344f651ce9eefb.jpg)  

Suppose, for example, that there is a call option with an exercise price of   $\S90$   on one share of stock. The option expires in one year. This share of stock is expected to be worth either   $\S80$   or   $\S120$   in one year, but we do not know which at the present time. If the stock were to be worth  $\S80$   when the call expires, its owner should decline to exercise the call. It would simply not be practical to use the call to purchase stock for   $\S90$   (the exercise price) when it can be purchased in the market for   $\S80$  . The call would expire worthless in this case. If, instead, the stock were to be worth   $\S120$   when the call expires, its owner should exercise the call. Its owner would then be able to pay   $\S90$   for a share that has a market value of  $\S120_{.}$  , representing a  $\S30$   profit. In this case, the call would be worth  $\S30$   when it expires. Let    $T$   designate the options term to expiry,    $S_{T}$   the stock value at option expiry, and  $c_{T}$   be the value of the call option at expiry determined as follows:  

$$
c_{T}=M A X[0,\;S_{T}-X]
$$  

$$
\mathrm{when}\;\;S_{T}=80,\;\;c_{T}=\mathbf{M}\mathbf{A}\mathbf{X}[0,\;80-90)=0
$$  

$$
{\mathrm{en}}\ S_{T}=120,\ c_{T}={\mathrm{MAX}}[0,\ 120-90)=30
$$  

A put grants its owner the right to sell the underlying stock at a specified exercise price on or before its expiration date. A put contract is similar to an insurance contract. For example, an owner of stock may purchase a put contract ensuring that he can sell his stock for the exercise price given by the put contract. The value of the put when exercised is equal to the amount by which the put exercise price exceeds the underlying stock price (or zero if the put is never exercised).  

To continue the above example, suppose that there is a put option with an exercise price of   $\S90$   on one share of stock. The put option expires in one year. Again, this share of stock is expected to be worth either  $\S80$   or  $\S120$   in one year, but we do not know which yet. If the stock were to be worth  $\S80$   when the put expires, its owner should exercise the put. In this case, its owner could use the put to sell stock for  $\S90$   (the exercise price) when  
TABLE 7. A.2 Stock Returns, Risk, and Co-Movement: Formula Entries 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/5b8250fe2e4c06963d967b1db534286929a59f096818b50454d85fc3d3511964.jpg)  
it can be purchased in the market for  $\S80$  . The put would be worth  $\S10$   in this case. If, instead, the stock were to be worth  $\S120$   when the put expires, its owner should not exercise the put. Its owner should not accept  $\S90$   for a share that has a market value of   $\S120$  . In this case, the put would be worth nothing when it expires. Let  $p_{T}$   be the value of the put option at expiry, determined as follows:  

$$
p_{T}=\mathbf{M}\boldsymbol{\mathrm{A}}\boldsymbol{\mathrm{X}}[0,\;X-S_{T}]
$$  

$$
\mathrm{when}\ S_{T}=80,\,\ p_{T}=\mathrm{MAX}[0,\,90-80)=10
$$  

$$
\mathrm{when}\ S_{T}=120,\,\ p_{T}=\mathrm{MAX}[0,\,90-120)=0
$$  

The owner of the option contract may exercise his right to buy or sell; however, he is not obligated to do so. Stock options are simply contracts between two investors issued with the aid of a clearing corporation, exchange, and broker, which ensure that investors honor their obligations to each other. The corporation whose stock options are traded will probably not issue and does not necessarily trade these options.  

For each owner of an option contract, there is a seller or “writer” who creates the contract, sells it to a buyer, and must satisfy an obligation to the owner of the option contract. The option writer sells (in the case of a call exercise) or buys (in the case of a put exercise) the stock when the option owner exercises. The owner of a call is likely to profit if the stock underlying the option increases in value sufficiently over the exercise price of the option (he can buy the stock for less than its market value); the owner of a put is likely to profit if the underlying stock declines in value sufficiently below the exercise price (he can sell stock for more than its market value). Since the option owner’s right to exercise represents an obligation to the option writer, the option owner’s profits are equal to the option writer’s losses. Therefore, an option must be purchased from the option writer; the option writer receives a “premium” from the option purchaser for assuming the risk of loss associated with enabling the option owner to exercise.  

# The Black-Scholes Model  

The Black-Scholes option pricing model provides a simple mechanism for valuing calls under certain assumptions (see Chapter 9 for more detail on the Black-Scholes model and its assumptions). If circumstances are appropriate to apply the Black-Scholes model, call options can be valued with the following:  

$$
c_{0}=S_{0}N(d_{1})-\frac{X}{e^{r_{f}T}}N(d_{2})
$$  

$$
d_{1}={\frac{\ln(S_{0}/X)+(r_{f}+\sigma^{2}/2)T}{\sigma{\sqrt{T}}}}
$$
 ﬃﬃﬃﬃ  

ﬃﬃﬃﬃ 
$$
d_{2}=d_{1}-\sigma{\sqrt{T}}
$$  

where    $N(d^{*})$   is the cumulative normal distribution function for   $(d^{*})$  . This function might be referred to in a statistics setting as the   $"Z"$   value for   $(d^{*})$  . From a computational perspective, one would first work through  Equation (7.A.2.4 ) and then  Equation (7.A.2.5)  before valuing the call with  Equation (7.A.2.3) .  $N(d_{1})$   and    $N(d_{2})$   are areas under the standard normal distribution curves (  $\boldsymbol{z}$  -values). Simply locate the   $\mathbf{Z}$  -value on an appropriate table (see Table 7. A.1  in the text appendix) corresponding to the  $N(d_{1})$   and  $N(d_{2})$   values.  
Consider the following simple illustration of a Black-Scholes model application: An investor has the opportunity to purchase a six month call option for  $\S7.00$   on a stock that is currently selling for  $\S75$  . The exercise price of the call is  $\S80$   and the current riskless rate of return is   $10\%$   per annum. The variance of annual returns on the underlying stock is  $16\%$  . At its current price of  $\S7.00$  , does this option represent a good investment? First, we note the model inputs in symbolic form:  

$$
\begin{array}{c c c}{{T=0.5}}&{{r_{f}=0.10}}&{{\sigma=0.4\quad S_{0}=75}}\\ {{}}&{{}}&{{}}\\ {{X=80\quad\sigma^{2}=0.16}}&{{e\approx2.71828}}\end{array}
$$  

Our first steps are to find    $d_{1}$   and  $d_{2}$   from  Equations (7.A.2.4) and (7.A.2.5) :  

$$
d_{1}={\frac{\ln(75/80)+(0.1+0.5\cdot0.16)\cdot0.5}{0.4\cdot{\sqrt{0.5}}}}={\frac{\ln(0.9375)+0.09}{0.2828}}=0.09
$$
   

ﬃﬃﬃﬃﬃﬃﬃ 
$$
d_{2}=d_{1}-0.4\bullet\sqrt{0.5}=0.09-0.2828=-\,0.1928
$$
   

Next, by either using a   $_\mathrm{z}$  -table (see  Table 7. A.1  in the text Appendix) or by using an appropriate estimation function from a statistics manual, we find normal density functions for  $d_{1}$   and    $d_{2}$  :  

$$
N(d_{1})=N(0.09)=0.536\quad N(d_{2})=N(-0.1928)=0.420
$$  

Finally, we use  $N(d_{1})$   and  $N(d_{1})$   in  Equation (7.A.2.3)  to value the call:  

$$
c_{0}=75\bullet(0.536)-(80\bullet0.9512)\bullet(0.420)=8.23
$$
     

Since the 8.23 estimated value of the call exceeds its 7.00 market price, the call should be purchased.  

# Appendix Exercises  

1.  Call and put options with an exercise price of  $\S30$   are traded on one share of Company X stock.  

a.  What are the value of the call and the put if the stock is worth   $\S33$   when the options expire? b.  What are the value of the call and the put if the stock is worth  $\S22$   when the options expire? c.  What is the value of the call writer’s obligation if the stock is worth   $\S33$   when the options expire? What is the value of the put writer’s obligation if the stock is worth  $\S33$   when the options expire? d.  What is the value of the call writer’s obligation if the stock is worth   $\S22$   when the options expire? What is the value of the put writer’s obligation if the stock is worth  $\S22$   when the options expire?  
e.  Suppose that the purchaser of a call in part a paid  $\S1.75$   for his option. What was his profit on his investment? f.  Suppose that the purchaser of a call in part b paid  $\S1.75$   for his option. What was his profit on his investment?  

2.  Evaluate calls for each of the following European stock option series:  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/f843834c762806532d12f8cd68afea8abc4cd22147bf8bbae53ba49cdc134ba7.jpg)  

# Appendix Exercise Solutions  

1. a.    $c_{T}=\S33-\S30=\S3,$  ;  $p_{T}=0$  b.  $c_{T}=0.$ ; $p_{T}=\S30-\S22=\S8$ c.    $c_{T}=-\L\!\!\!\!\slash3;\,p_{T}=0$  d.    $c_{T}=0$  ;  $p_{T}\,{=}\,-\S8$  e.    $\S3-\S1.75=\S1.25$  f.    $\S0-\S1.75=-\S1.75$  

2.  The options are valued with the Black-Scholes model in a step-by-step format in the following table:  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/b57ed2245411c7e9f0e24432926be6aa5553abef4be53da9a8fc8e301732b11d.jpg)  

# 7. A.3 ESTIMATING IMPLIED BLACK-SCHOLES VARIANCES  

Analysts often employ historical return variances to estimate the volatility of securities. However, one cannot always assume that variances will be constant over time or that historical data properly reflects current conditions. An alternative procedure to estimate security variances is based on the assumption that investors price options based on consideration of the underlying stock risk. If the price of the option is taken to be correct, and if the Black-Scholes option pricing model is appropriate for valuing options, then one can infer the underlying stock standard deviation based on the known market price of the option and the option pricing model. Consider the following example pertaining to a sixmonth call currently trading for  $\S8.20$   and its underlying stock currently trading for  $\S75$  :  
$$
\begin{array}{l l l}{{T=0.5}}&{{r_{f}=0.10}}&{{c_{0}=8.20}}\\ {{X=80}}&{{S_{0}=75}}&{{}}\end{array}
$$  

If investors have used the Black-Scholes option pricing model to evaluate this call, the following must hold:  

$$
\begin{array}{c}{{8.20=75\times N(d_{1})-80\times e^{-0.01\times0.5}\times N(d_{2})}}\\ {{{}}}\\ {{d_{1}=\{\ln(75/80)+(0.1\;+\;0.5\sigma^{2})\times0.5\}\div\sigma\sqrt{0.5}}}\\ {{{}}}\\ {{d_{2}=d_{1}-\sigma\sqrt{0.5}}}\end{array}
$$
 ﬃﬃﬃﬃﬃﬃﬃ  

Thus, we wish to solve the above system of equations for    $\upsigma$  . This is equivalent to solving for the root of:  

$$
f(\sigma^{*})=0=75\times N(d_{1})-80\times e^{-0.1\times0.5}\times N(d_{2})-820
$$  

based on equations above for  $d_{1}$   and  $d_{2}$  . There exists no closed form solution for  σ . Thus, we will use the method of bisection to search for a solution. We first arbitrarily select endpoints    $b_{1}=0.2$   and  $a_{1}=0.5$   such that    $f(b_{1})<0$   and  $f(a_{1})>0$  . Since these endpoints result in  $f(\upsigma)$   with opposite signs, our first iteration will use    $\upsigma_{1}=0.5(0.2\,+\,0.5)=0.35.$  . We find that this estimate for sigma results in a value of    $-1.30009$   for  $f(\upsigma)$  . Since this  $f(\upsigma)$   is negative, we know that    $\upsigma^{*}$   is in the segment  $b_{2}=0.35$   and    $a_{2}=0.5$  . We repeat the iteration process, finding after 19 iterations that  $\upsigma^{*}=0.411466.$  .  Table 7. A.3  details the process of iteration.  

The Newton-Raphson method can also be used to more efficiently iterate for an implied volatility. Consider the following example where we wish to estimate the volatility implied by a six-month option with an exercise price of   $\S80$   currently selling for   $\S8.20$  . Assume that the underlying stock price is currently  $\S75$   and that the riskless return rate is 0.10. We shall solve for the implied standard deviation using the Newton-Raphson method, with an arbitrarily selected initial trial solution of    $\upsigma_{1}=0.6$  . First, we need the derivative of the Black-Scholes model with respect to the underlying stock return standard 8 deviation :  

$$
\frac{\partial C}{\partial\sigma}=S\sqrt{t}\frac{e^{\frac{-(d_{1}^{2})}{2}}}{\sqrt{2\Pi}}>0\ \ \ \ V e g a=\nu
$$
 ﬃﬃﬃﬃﬃﬃﬃ  

We see from  Table 7. A.4  that this standard deviation results in a value of  $f(\sigma_{0})=3.950117$  . Plugging 0.6 into  Equation (7.A.3.1)  for    $\upsigma,$   we find that  $f^{\prime}(\upsigma_{1})=20.82508$  . Thus, our second trial value for  σ  is determined by:    $\sigma_{2}=0.6\,-\,(3.950117\,\div\,20.82508)=0.410319.$  . This process continues until we converge to a solution of approximately 0.411466. Note that the rate of convergence is much faster by using the Newton-Raphson method than by using the method of bisection.  
TABLE 7. A.3 Using the Bisection Method to Estimate Implied Volatility  

# Initial Equation:  $S N(d_{1})-X e_{\mathrm{~\bf~f~}}^{-r_{\mathrm{~\bf~T~}}}N(d_{2})$  

a 1  5  0 : 5 b 1  5  0 : 2 σ 1  5  0 : 35 r f  5  0 : 1 S 0  5  75 X  5  80 c  5  8 : 2 T  5  0 : 5  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/dd9745a9c9e965faa23367c135151b6f222e084ec17e14d670604fe1b41ac369.jpg)  
TABLE 7. A.4 Newton-Raphson Method and Implied Vol at ili ties 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/e068551fc0203aa856ded774e68edca3c2529d98e36a1e73e0abdf81241cde37.jpg)  
Initial Equation:    $S_{0}N(d_{1})-X e^{-r_{f}T}N(d_{2})$  
$$
\begin{array}{c c c}{r_{f}=0.1}&{S_{0}=75}&{X=80}\\ {}&{}&{}\\ {c_{0}=8.20}&{T=0.5}&{\sigma_{0}=0.6}\end{array}
$$  

# Simple Closed-Form Procedures  

The implied vol at ili ties described above have the desirable characteristic of having an ex-ante orientation. However, their use is somewhat complicated by the frequently timeconsuming methodology of iterating for solutions. Spreadsheet file and even computer program solutions packages can sometimes be cumbersome. This section provides two methodologies for obtaining simple closed form solutions for implied underlying asset vol at ili ties.  

Brenner and Sub rahman yam (1988)  provide a simple formula to estimate an implied standard deviation (or variance) from an option whose striking price equals the current market price of the underlying asset. As the market price differs more from the option striking price, the estimation accuracy of this formula will worsen:  

$$
\sigma_{B S}^{2}=\frac{2\pi c_{0}^{2}}{t S_{0}^{2}}
$$  

The accuracy of  Equation (7.A.3.2)  when the option strike and underlying asset market prices are unequal can be improved with use of a quadratic procedure proposed by Corrado and Miller (1996) . Their formula makes use of a second-order approximation of the cumulative normal density function and an approximation for  $\ln(S_{0}/X)$   as  $2(S_{0}-\mathit{X})/\mathit{\Omega}$   $(S_{0}\mathrm{~+~}X)$  . Several additional simplifications and approximations lead to the following formula for  σ :  

$$
\sigma_{C M}^{2}=\frac{2\pi}{t(S_{0}+X)^{2}}\times\left[c_{0}-\frac{S_{0}-X}{2}+\sqrt{\left(c_{0}-\frac{S_{0}-X}{2}\right)^{2}-\frac{\left(s_{0}-X\right)^{2}}{\pi}}\right]
$$  
While the accuracy of this formula is improved when the market price of the underlying asset is close to the striking price of the option, it is not nearly as sensitive to differences between these prices as is the Brenner-Sub rahman yam formula.  

# Aggregating Procedures  

A difficulty arising with estimating implied variances results from the fact that there will typically be more than one option trading on the same stock. However, what if the short- and long-term uncertainty of a stock differs? Each option’s market price will imply its own underlying stock variance, and these variances are likely to differ. Worse, what if the implied volatility of option contracts differs with respect to exercise prices? (This is called a volatility smile.) How might we use this conflicting information to generate the most reliable variance estimate? Each of our implied variance estimates is likely to provide some information, yet has the potential for having measured with error. We can preserve much of the information from each of our estimates and eliminate some of our estimating error if we use for our own implied volatility a value based on an average of all of our estimates. However, because volatility might be expected to vary over time, one should average only those variances implied by options with comparable terms to expiration. The following suggests two methods for averaging implied standard deviation estimates:  

1.  Simple average: Here, the final standard deviation estimate is simply the mean of the standard deviations implied by the market prices of the calls.

 2.  Average based on price sensitivities to  σ : Calls that are more sensitive to  σ  as indicated by  $\partial c_{j}/\partial\upsigma_{j}$   are more likely to imply a correct standard deviation estimate. Suppose we have  $n$   calls on a stock and each of which implies a stock standard deviation    $\upsigma_{j}.$  . Each call price will have a sensitivity to its implied underlying stock standard deviation  $\partial c_{j}/\partial\sigma_{j}$  . The sensitivities can be summed, and a weighted average standard deviation estimate for the underlying stock can be computed from the following weighting scheme:  

$$
\omega_{i}=\frac{\displaystyle\frac{\partial c_{0,i}}{\partial\sigma_{i}}}{\displaystyle\sum_{j=1}^{n}\frac{\partial c_{0,j}}{\partial\sigma_{j}}}
$$  

where    $w_{i}$   represents the weight for the implied standard deviation estimate for call option  i . Thus, the final standard deviation estimate for a given stock  $k$   based on all of the implied standard deviations from each of the call prices is:  

$$
\sigma_{k}=\sum_{i=1}^{n}\omega_{i}\sigma_{i}
$$  
