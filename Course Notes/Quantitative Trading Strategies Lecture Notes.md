---
tags:
  - credit_risk
  - market_inefficiency
  - quantitative_trading
  - risk_management
  - trading_strategies
aliases:
  - Quant Trading
  - Quantitative Finance
  - Trading Strategies
key_concepts:
  - Credit risk
  - Market inefficiency
  - Providing services
  - Quantitative trading elements
  - Sources of profit
---

# INTRODUCTION TO QUANTITATIVE TRADING  

# 1.  Basic Features of Quantitative Trading  

The ecosystem of the securities trading industry contains actors of all sorts, from farmers and silver miners attempting to hedge, through individual savers working on their retirement, governments maintaining currency pegs, and investment banks with ﬁngers in nearly every pie. Our goal is to concentrate on those (relatively) few organizations employing  quantitative trading strategies .  

Quantitative trading strategies have a few key elements:  

•  A source of (likely) proﬁt, •  Regular securities trading, generally with stochastic control, •  Regular processing of incoming data ﬂow, and •  Risk management.  

Each of these elements represents a tremendous variety of ideas, and can be expanded into many complex volumes in its own right. We will attempt to treat each one with a keen eye for the tradeo↵between balance and concision, with the goal of bringing an individual who possesses a reasonably quantitative background to a level of passing (or better) familiarity with most extant quantitative strategies found “in the wild”.  

1.1.  Sources of Proﬁt.  Broadly, there are three sources of proﬁt in trading strategies  

•  Providing services,  $\bullet$   Market ineﬃciency, and  $\bullet$   Luck.  

1.1.1.  What To Do About Luck.  We do not, of course, plan on particularly good or bad luck when considering a strategy. However, we can often measure how susceptible our strategy  is to the element of luck. This approaches the realm of uncertainty and risk management, so most of our treatment will occur later when we begin to address risk management issues.  

Note, however, that uncertainty may be reducible by improving a quantitative model (say by using better mathematics or more complete input data). So uncertainty clearly has a role to play even at early stages of ﬁnding sources of proﬁt.  

1.1.2.  Providing Services.  There are many ways for ﬁnancial ﬁrms to proﬁt by providing services. Most do not involve quantitative trading. For example, brokerage fees from trading brokers, data access fees from exchanges and advisory fees from investment ﬁrms are all closely related to trading but do not involve quantitative trading strategies.  

Instead, the way in which trading strategies, quantitative or otherwise, can collect fees for services is somewhat invisibly. Take, for example, the case of an investor in a risky corporate bond, the CRC oil company’s 8% Dec 2022 bonds, trading around 80 points per 100 as of March 2019. Each  \$ 1,000-face bond is a promise to pay  \$ 1,240 in coupons and principal through 2022. That results in a handsome rate of return over   $15\%$   per year.  

Does that make investors in these bonds brilliant paragons of trading savvy? Certainly not. When  high-yield  or  junk  bonds such as this one are issued, everyone understands that there is relatively high risk of those payback promises failing to be honored. This is known as credit risk , and the e↵ect here is that bond holders are providing an insurance service. They are buying the bonds and assuming the risk of CRC declaring bankruptcy, while getting paid for such risk via a high apparent rate of return.  
Many trading strategies follow this pattern: they generate proﬁts at seemingly magical 1 levels until you consider the risks they assume in the process . One role of  quantitative trading strategies is to acknowledge that risk, and optimize its size in relation to the proﬁts.  

Other examples of being paid for services include selling options, market making and foreign exchange carry trades. All are bases for reasonable quantitative trading strategies, and we will discuss them in greater detail later.  

1.1.3.  Market Ineﬃciency.  In an economic sense, we might say markets are exhibiting inefﬁciency whenever exploit able trading strategies exist that are capable of reliably achieving risk/reward ratios sign i cant ly better than “usual”. Everyone hopes to ﬁnd these cases, of course, and if the opportunity is really large, then it will attract more and more attention and trading until its proﬁt margins revert to normal. We will discuss this later when we introduce the concept of  beta creep .  

Securities with the most obvious relationships between them, for example precious metals traded at di↵erent exchanges, will tend to exhibit the least ineﬃciency. As relationships become less obvious, or harder to exploit, the in e cie nci es, and potential proﬁts, expand.  

1.1.4.  P and Q.  For quantitative traders, there are two categories of models used in identifying proﬁt opportunities, identiﬁed by Emanuel Derman as    $\mathbf{P}$   and  Q .  

$\mathbf{P}$   models involve what most of the general public thinks of as the  dark art  in ﬁnancial modeling, namely constructing predictive models for securities prices. These models involve real-world probabilities of prices going up or down and by how much. They usually involve lots of data and tend toward being statistical in nature. An example might be a lead-lag model where the CRC stock price increases or decreases just after oil futures prices go up or down.  

More generally predictive    $\mathbf{P}$   models  require  securities prices to lag other information ﬂow. The information is said to “propagate” to the market prices of those securities. When we are considering prices alone, this information ﬂow usually follows a hierarchy that imitates liquidity , expressing itself ﬁrst in highly liquid securities such as index futures before making its way to less liquid cases like CRC bonds.  

Q  models involve  market consistency , where the prices of one set of securities are used collectively to calibrate a model to risk-neutral probabilities, helping identify individual cases that might be cheap or dear and to price closely related securities that are unquoted. For example, the EMini (SP500) futures options can all be run through the Black-Scholes model to ﬁnd  volatility skews  of  implied volatility  by strike. Options whose implied volatility fails to agree with the rest of the skew curves look like trading opportunities.  

Of course, when a    $\mathbf{Q}$   suggests a trade, there is the implicit assumption the trade will be proﬁtable, so there is an implicit    $\mathbf{P}$   model involved as well. For vanilla options market making it is now common to link the  Q  model with a corresponding    $\mathbf{P}$   model. However, many desks, especially exotics desks, do not bother to construct the    $\mathbf{P}$   model.  

When we construct    $\mathbf{Q}$   models and then ﬁt them, we end up with a set of model parameters that may or may not make sense according to our experience and intuition. If they look  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/c51015f2d88e6e7304a70914183b4aed706115b2e33da57eddeb797f2f71b17a.jpg)  
Figure 1.  Ford Motor Company equity prices versus credit default swap spreads. Clearly there is a relationship, though it is highly nonlinear.  

“strange” we may decide we have a trading opportunity based on the model’s perspective on market prices, even without having identiﬁed any one security whose price is clearly out of line.  

In this case, we say we are trading on  model stress . A simple example is a  yield curve inversion  in US Treasury prices, with a yield curve derived from those prices showing higher rates of return on short-term securities than on long-term securities. These inversions happen from time to time but last for months, not years. Inverted rates of return will be unlikely to last, and investor trading according to that view stands a good chance of proﬁt.  

In our studies, we will take  Q  models to be black boxes, capable of helping use go back and forth from parameter space to security prices, without worrying too much about their underlying mathematics or calibration techniques. For us, they are essentially nonlinear transformations of security prices for purposes of identifying and constructing quantitative    $\mathbf{P}$   trading models. Reasonable models have coeﬃcients (parameters) that only vary within some plausible bounds. If we start to ﬁnd implied parameters approaching or outside those bounds, either the model is unreasonable or the securities prices generating them are unlikely to last for a long time. We will address in greater detail when we consider back testing.  

1.1.5.  Things We Cannot Really Model.  There are some things that are very impractical to model, even though we might really want to  

•  Capital structure events (mergers, acquisitions, buybacks, debt issues, fraud),  
•  Major political events (Brexit, sovereign default), and  $\bullet$   Instinctive trading.  

# 2.  The Role Of Regular Trading  

It is easy to envision a clever trader who identiﬁes some tremendous opportunity in the markets, makes just one or a few big trades, and then relaxes watching the proﬁts roll in. This happened during the 2007-2009 ﬁnancial crisis where some traders (e.g. John Paulson and Steve Eisman) did just that. While the analysis may involve quite a bit of quantitative reasoning, and some trading is necessarily involved, these are not examples of quantitative trading  strategies.  

A distinguishing feature of quantitative trading strategies is that they involve continual reactions to new information, typically by trading market securities to hedge existing positions, clear out undesirable positions, or take attractive new positions. There may be somewhat long periods where they are completely out of the market, but usually they have some position and activity. As a consequence, there is some degree to which their proﬁts arise from betting multiple times on pro t ability of similar-looking attractive situations, e↵ectively identical independent events. Doing so makes performance steadier and allows for statistical design and stochastic control unattainable by single-event bets.  

# 3.  Information Processing And Data Flow  

All quantitative trading strategies work by taking positions expected to realize “unusual” proﬁts based on the best information available when trades are made. Once positions are in place, new information may dictate changes to the positions. Existing positions may or may not have lost money, but regardless of past outcomes the new information alters our perceptions of position value, and undesirable positions must be discarded while new ones are obtained.  

As positions make money, they can become disproportionately large within the portfolio, causing us to liquidate a portion of our holdings in  rebalancing  operations. Other positions may have lost so much money, that we no longer trust the hypotheses generated by our models. These may be liquidated in a  stop loss  risk control strategy. Further positions may be made more or less desirable, not due to their pro t ability predictions, but because the help or hurt our overall perception of risks. In these cases, rebalancing comes from hedging and risk management motives.  

3.1.  The Cycle.  All of these desired alterations to our positions come from the e↵ects of newly arrived information and the associated changes to our perceptions of risk and value. We ﬁnd ourselves continually executing a cycle of the following steps:  

•  Take, and parse, useful information  $\bullet$   Run pro t ability and risk models  $\bullet$   Attempt to adjust positions accordingly  

There is of course a tremendous amount of con gu ration, model spec i cation, and data control hidden behind these three simple-sounding steps. To the extent the overall system is driven by models and procedures, we say it is a trading system with  stochastic control , i.e. changes to its behavior that depend on random or random-seeming external events.  
3.2.  Risk Management.  As we saw above, risk management is part of our stochastic control. However it is useful at this stage to at least point out major elements of risk management from the point of view of quantitative trading strategies. Most strategies are aimed at trading multiple securities simultaneously, in order to reap the beneﬁts of large    $N$  , as well as spread development and maintenance costs among multiple revenue streams.  
# EXPONENTIALLY WEIGHTED STATISTICS  

# 1.  Motivation  

Very frequently in trading model design, we need to know how a variable compares to recent history. As data points recede into the past, however, their importance to current trading strategies declines. In e!ect, at time    $t$  , we want to include points    in the past with  $x_{t-s}$  declining weight    $W=W(s)$   depending on the age    $s$  . We can then get a weighted sum  

$$
S_{t}=\int_{s=0}^{\infty}W(s)x_{t-s}d s
$$  

or its near equivalent weighted average  

$$
A_{t}=\frac{\int_{s=0}^{\infty}W(s)x_{t-s}d s}{\int_{s=0}^{\infty}W(s)d s}.
$$  

Often, especially for the common operation of averaging, we rescale our weights to make life easier  

$$
w(s):={\frac{W(s)}{\int_{s=0}^{\infty}W(s)d s}}.
$$  

and frequently we deal in discrete sampling where sums take the place of these integrals so that we may say for example  

$$
A_{t_{j}}=\sum_{i=0}^{\infty}w_{i}x_{j-i}.
$$  

Fans of functional analysis or signal processing will recognize this as a convolution operation.  

We could consider many possible functions for such a weighting scheme. The simplest, conceptually, is a moving  boxcar  window where we discard any points older than, say    $s=30$  days. The trouble with boxcar weighting is that, by not smoothly decaying old data, it gives us surprises as we run the business. The reason is easy to see. Imagine we start with a relatively stable set of observations  
#  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/b018fb96509f1a88922f3618a7ab9cb9d768f094849046394671fa244db63108.jpg)  
Figure 1.  A boxcar average doing a nice job  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/0a58012cc91680f9cfc949d141c9d89f6efa9e9f691d8638a0b35cd213f55108.jpg)  
Figure 2.  New information drops the average quite a bit, as expected  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/9f712b8227ef23261c932cb6949ae8177dced0844762566a4a44976af138f21e.jpg)  
Figure 3.  After the boxcar window has passed, we get a  second  jump  

It’s perfectly normal to have your systems react in a big way to a new outlier. After all, that outlier represents important new information arriving. What is  not  normal is to have a big reaction to the outlier falling out of your averaging window. The window size was your arbitrary choice, not a bit of important new data. Especially if the averaging period is more than a few weeks, people will forget about the outlier and then go into panic mode when model parameters take big jumps due to this behavior.  

We can avoid this by choosing a “tent” function where weight declines linearly up to our limit, which on daily data with a 30 day limit would set    $w\,=\,0$   for    $s\,\geq\,30$   and otherwise choose for    $i=0,\ldots,29$  

$$
w_{i}:=w(s_{i})=\frac{30-i}{30\left(\frac{30+1}{2}\right)}
$$  

Any weighting scheme we desire is available to us, but it turns out one of them is special. Namely, if we choose the  exponential weighting  scheme with coe”cient    $\eta<0$   and    $i=0,\ldots,\infty$  

$$
w_{i}:=w(s_{i})=\eta^{i}\cdot(1-\eta)
$$  

with the coe”cient   $1-\eta$   chosen because   $\begin{array}{r}{1+\eta+\eta^{2}+\cdot\cdot\cdot=\frac{1}{1-\eta}}\end{array}$  . →  
#  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/318f6a661120fc611453aa90f9026cdd5d2d686dcdcbd0a7939f325446a6362b.jpg)  

Figure 4.  Weights decaying with age. Here the exponential center of mass was set to 10.  
#  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/7af14db4d5efa60554efebdb6ad5743f7ee6833edbf48e667d88a2340cb99c20.jpg)  
Figure 5.  Little di!erence in weighting schemes on timescale much larger than the window  
#  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/2ed128944550f704b9a67951e7c1f1e778429d0bc9e2713a66f418a7b5e3b9d6.jpg)  
Figure 6.  Signiﬁcant di!erence in weighting schemes on timescale close to the window  
#  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/7ba9d70d40902f969a9906ff9fadaa3d4940f0159c6564701c4b7b9f9b27686b.jpg)  
Figure 7.  All three schemes react to the outlier, but only boxcar su!ers a severe “bounce-back” e!ect  

# 2.  Efficient Algorithms  

Among available weighting schemes, quantitative practitioners greatly favor the boxcar and the exponential. Boxcar is popular due to its simplicity of understanding and implementation. Exponential weighting is popular because it enjoys a particularly clean and e”cient algorithm for computation. To begin with, note that each weight    $w_{i}$   can be computed as    $w_{i}=\eta w_{i-1}$  . Now, note that if we have already computed the old, previous average  

$$
A_{t_{j-1}}=(1-\eta)\sum_{i=0}^{\infty}\eta^{i}x_{j-1-i}.
$$  

then it can be rewritten as  

$$
A_{t_{j-1}}=(1-\eta)\frac{1}{\eta}\sum_{i=0}^{\infty}\eta^{i-1}x_{j-1-i}=(1-\eta)\frac{1}{\eta}\sum_{i=1}^{\infty}\eta^{i}x_{j-i}.
$$  
Our new average is  

$$
\begin{array}{l}{{A_{t_{j}}=(1-\eta)\displaystyle\sum_{i=0}^{\infty}\eta^{i}x_{j-i}}}\\ {{\ }}\\ {{\ \ \ \ \ =(1-\eta)x_{j}+(1-\eta)\displaystyle\sum_{i=1}^{\infty}\eta^{i}x_{j-i}}}\\ {{\ }}\\ {{\ \ \ \ \ =(1-\eta)(x_{j})+\eta A_{t_{j-1}}}}\end{array}
$$  

Therefore, to update our average, we need to perform only a two multiplications and an addition. Furthermore, we need not store any arrays of values or intermediate results (unless we want to). We can discard    $A_{t_{j-1}}$   the moment it has been used  $^{\mathrm{~1~}}$    to compute    $A_{t_{j}}$  . Thus, along with very few computations, updates to the exponential average or sum cost essentially no computer memory.  

The implications for e”cient computation almost cannot be overstated. Back testing and parameter searches become far faster when computation is e”cient.  

We can contrast with, say, boxcar updating. Computationally it is not terribly expensive, but for a window size    $N$   we have to keep track of the last    $N$   values along with their sum  $S_{i}$  . Updating is then a matter of dropping the oldest item out of the list, updating    $S_{i}$   by 2 subtracting its value, and then re computing the quotient for the average .  

2.1.  Inﬁnite Lookback.  Since exponential decay has strictly positive weights, we might want to correct for the use of    $\infty$  in our computations above. For example, if    $N=3$   and we take  $A_{1}=x_{1}$  , then our “e”cient” formula gives  

\$ % 
$$
A_{3}=(1-\eta)(x_{3})+\eta\left((1-\eta)(x_{2})+\eta x_{1}\right)
$$  

which is not the same thing as the truncated geometric series averaging we might expect  

$$
\aleph_{3}=\frac{\left(x_{3}+\eta x_{2}+\eta^{2}\right)}{1+\eta+\eta^{2}}
$$  

In cases of small sample counts, we may well want to adjust for this di!erence.  

So far, we have covered exponential weighting suitable for regular time series, or other cases where the relative importance of data depends on observation count.  

3.1.  Decay By Time.  Let us now consider the case where the importance of data declines with respect to “wall clock” time    $t$  . This is particularly relevant where data updates come in bursts. Here we choose a exponentially decaying weight, dependent on the age   $\Delta t$   of all former data  

$$
w=w_{\lambda}(\Delta t)=e^{-\lambda\cdot\Delta t}
$$  

where    $\lambda$   has units of 1 / time, and our update formula becomes, with observation    at time    $x_{j}$   $t_{j}$  

$$
A_{t_{j}}=e^{-\lambda\cdot\left(t_{j}-t_{j-1}\right)}A_{t_{j-1}}+\left(1-e^{-\lambda\cdot\left(t_{j}-t_{j-1}\right)}\right)x_{j}
$$  

We refer to the quantity   $1/\lambda$   as the  characteristic time  of our averaging, and the weight of data up to age   $1/\lambda$   is of course   $1/e$  .  
For regularly spaced data at intervals   $\Delta t=\tau$  , this is equivalent to our previous formulas with    $\eta=e^{-\lambda\cdot\tau}$  .  

3.2.  Updates For Time-Weighted Averaging.  Our update algorithm is nearly identical, but now we need to track not only our previous average, but also the time    $t_{j-1}$   at which it was computed. This is still a trivial burden, and our calculation and memory e”ciency remain essentially una!ected.  

It is important to note that the time-weighted average will put very low weight on fresh data items if they come in rapid succession, since the decay of old data will be small. Whether or not this property is desirable depends on the speciﬁcs of the economic calculation in play.  

# 4.  Terminology In Exponential Weighting  

If we consider either a discrete scheme with decay on old data of    $c_{\lambda}\,=\,e^{-\lambda}$  , or a timeweighted scheme with decay of size    $e^{-\lambda\Delta t}$  , there are a few equivalent ways in which these may be described:  

•  Characteristic Ti e •  Decay Coe”cie  $\lambda$  •  Unit Decay    $\eta$   $\mathrm{which}=e^{-\lambda}$  ) •  Half-life •  Center Of Mass  $\bullet$   Span  

All of these fully specify an exponential weighting scheme, so you will see various colleagues use these terms, according to their preferences.  

# 5.  Update Formulas For Covariance  

Higher-order moments, including covariance (and hence correlation), enjoy update formulas as found in Pebay (2008). In particular Pebay shows that in the case of no decay  

$$
c_{i+1}=c_{i}+\frac{i}{i+1}(x-\mu_{x})(y-\mu_{y})
$$  
# THE CARRY TRADE  

# 1.  The Principles Of Carry Trades  

A large subset of trading, and especially quantitative trading, can attribute signiﬁcant portions of its pro t ability to holding positions that make money when nothing interesting happens, and (usually) lose money otherwise. In industry vernacular, this is called the  carry trade , because the portfolio is “carrying” risk. For insurers, the business is quite explicit; premiums are collected, and damages are paid.  

In the ﬁnance industry, risks arise from declines in the value of our positions, and proﬁts arise from increases in them. Sometimes it is not so clear whether proﬁts are associated with skill, or with risk. When trading ﬁnancial securities, we may have a persistent risk bias without even knowing it. Associated proﬁts then comprise a carry trade without our even realizing it.  

# 2.  Statistical Indicia Of Carry Trades  

Given a suﬃciently long time series of returns    $r_{i}$  , identifying a carry trade is fairly simple. We expect to see  

•  More frequent positive values,   $\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!\$  •  Negative return skew, with a fatter left tail than right tail in the return histogram •  Positive correlation to broad market indicators •  Negative correlation to “fear” indicators such as VIX •  (Likely) High excess kurtosis of returns  

The hope of the investor, of course, is that future returns will be steady enough, and losses small enough that the strategy will be proﬁtable overall without great damage to performance ratios from the occasional losses. Investors who realize they are taking on a carry trade are liable to be particularly worried about the correlations, which are highly unattractive since the carry trade will lose the most money precisely when everything else is going to hell.  

2.1.  Problems With Statistical Analysis.  The small sample sizes typically found in backtests and historical return series give rise to high uncertainty in skew and kurtosis estimates. For example, with sample size    $N$  , the sample skew of a standard gaussian is distributed roughly as  

$$
\mathrm{skew}_{\Phi}\sim N\left(0,{\frac{6}{\sqrt{N}}}\right)
$$  

and the situation is far worse for data, such as returns, that only vaguely look gaussian.  

Estimates of beta are far better behaved, so the practical way to identify unstated carry risks is to examine downside beta to broad market indicators, especially ones with assets in similar markets to the strategy in question.  
# 3.  Carry Trade Examples  

3.1.  Rates Carry.  A classic example of the carry trade takes place using levered investments in ﬁxed income securities. The principle is to borrow at short tenors and low interest rates, incurring small interest payments, and lend at long tenors and high interest rates, pocketing large interest payments and principal risk accrual. The di↵erence in cashﬂows provides the typical positive returns.  

In mature markets, it is common to have brokerage accounts or other funding sources linked to LIBOR (or  SOFR  after 2019). Thus, borrowing and levering up are possible at LIBOR plus some few basis points of spread. Longer term securities, such as Treasury notes and bonds, are extremely liquid and easy to trade, typically with interest rates a few points above LIBOR.  

For a simple view of rates carry, consider lending by buying a 5 year zero-coupon bond at  $5\%$   rates, and borrowing at 1% rates by selling a 1/4 year bond. The notional amounts are  $1/e^{r\tau}$  . In this case, the weekly increase in 5 year bond value is 12 basis points, and the weekly increase in the value of the borrowings (short bond) is 2 basis points.  

3.2.  FX Carry.  A related example of the carry trade takes place using levered investments in foreign ﬁxed income securities. The principle is similar to that of rates carry, but ﬁnd even higher-paying lending rates by choosing securities in foreign ﬁxed-income markets. Higher returns come at the cost of exposure to both FX rate changes and interest curve ﬂattening.  

3.3.  Crypto Wrapping.  Many crypto tokens have a governance structure in which token holders are given the ability to cryptographically  stake  or  wrap  their existing holdings in smart contracts conveying limited withdrawal rights. In exchange, they receive periodic payments 1 in the form of more tokens . Historically, the risks of crypto token positions are quite high. The additional friction of withdrawal delays multiplies the risks, so it is unsurprising to ﬁnd the corresponding yields at concomitant high levels.  

3.4.  Short Options.  A less well-understood form of the carry trade comes from shorting options, especially with strikes considerably lower than forward prices. Since markets usually rise, these options (in put equivalents) usually expire worthless, allowing the seller to book the premiums as proﬁt. If course, the natural leverage of out-of-the-money options means that market downturns are incredibly painful.  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/fde3b0ef108f41bdd9e72f781a24d8c34f37d2d9f09bc0c67a0ccfd7d0fd1dd4.jpg)  
Figure 1.  Staked Ethereum yields from Convex as measured by DefLlama.  
# TICK-LEVEL ANALYSIS  

# 1.  The Structure of Tick Data  

1.1.  Terminology.  The basic important elements of market state change are trades, bids and o!ers. We use the term  tick data  to denote high-resolution observations of these numbers, and usually assume it is available as of any given time in which the market is open. The trades are collectively considered to comprise the  trade tape  while the bids and o!ers collectively form the  order book  as of any given moment.  

If the market is a centralized exchange  $\perp$  , we can consider one or more orders to be at the top of book . For typical exchanges this is the set of highest-price bids and lowest-priced o!ers that have not yet  matched  or been  cancelled , and have not  traded out . The top of book is normally also ranked with highest priority to the oldest orders, in which case the exchange is said to use classic  price-time priority . Incoming new orders are said to comprise the  order ﬂow .  

For a given asset class, the group of exchanges serving it, the rules they use, and the ﬁrms accessing them collectively form the  market micro structure .  

1.1.1.  Data Formats.  Incoming tick data from established fully electronic markets normally arrives in FIX format 2 . Take, for example, data  $^3$    from the CME such as 1128=9 SOR 9=265 SOR 35=X SOR 49=CME SOR 34=10065111 SOR 52=20141013152659076 SOR 75=20141013 SOR 268=2 SOR 279=2 SOR 22=8 SOR 48=656784 SOR 83=215750 SOR 107=ESV4 C1895 SOR 269=1 SOR 270=1775 SOR 271=5 SOR 273=152659000 SOR 336=2 SOR 346=1 SOR 1023=1 SOR 279=0 SOR 22=8 SOR 48=656784 SOR 83=215751 SOR 107=ESV4 C1895 SOR 269=1 SOR 270=1850 SOR 271=291 SOR 273=152659000 SOR 336=2 SOR 346=6 SOR 1023=3 SOR 10=008 SOR  

Less established markets may use JSON-style formats as in this message from the Coinbase crypto currency exchange

 {’type’: ’open’, ’side’: ’sell’, ’price’: ’0.03743000’, ’order_id’: ’88d50b31-d5c6-445b-9134-05989d05e165’, ’remaining_size’: ’0.01000000’, ’product_id’: ’ETH-BTC’, ’sequence’: 1601762096, ’time’: ’2019-02-18T19:42:34.700000Z’, ’received_utc’: 1550518954.092663}  

1.1.2.  A Note On Timestamps.  It is common, and desirable, to represent timestamps using UTC, except for human presentations. However, note that there have been over 15 billion seconds since 1970. Therefore the 15-digit resolution of IEEE double precision ﬂoating point arithmetic will track these timestamps to slightly worse than the microsecond level.  

# 2.  Interesting Alternative Market Structures  

The U.S. equity markets are a  fractured market , in the sense that the same equities are traded on multiple exchanges. They are now legally linked by  Reg NMS  (i.e.  national market structure ) which speciﬁes rules under which they must send orders to each other when prices are better-looking for the customer.  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/3dcaf1a196f48fcb6dd9ab9b85103fc2870df81dd0ea21d072c00f2c7b87a9dd.jpg)  

Foreign exchange  electronic crossing networks (ECN)  allow brokers  last look rights . Futures exchanges may use a combination of price-time priority and  proportional allocation  in which all orders at the top-of-book get a nonzero ﬁll probability.  

Some exchanges allow brokers to give higher priority to  internal crosses  that join the broker’s own customers. The U.S. equity markets now have similar structure, in e!ect, as orders arising from  retail  order ﬂow are internally crossed by Citadel and other ﬁrms who make it their business to purchase the ﬂow, cross where sensible, and then send the  exhaust  as new orders to the usual markets.  

Certain futures markets are traded  pro rata , in which there is no time priority given, or time priority is given only to the very earliest order. In particular the extremely liquid EuroDollar contract at the Chicago Mercantile Exchange trades on a  modiﬁed version of pro rata  allocation.  

Not all exchanges make the orders visible to participants. These  dark pools , common for US equities, match orders without displaying any kind of book to market participants, which in theory allow participants to place large orders, and make trades at lower market impact costs.  
#  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/25cfd1a9003f144b039c512341e2b2e36047f1d2f032a841f1c7b91a18b796cd.jpg)  
Figure 2.  Bitcoin market and trades over a two minute period. Bid/o!er spread is somewhat visible.  

They frequently have minimum size rules for matching. In practice accumulation algorithms have tended to outperform dark pools for that purpose.  

Eric Budish suggests disc ret i zing not only price, in order price ticks, but also times, by altering the matching process  so as to hold periodic auctions.  

# 3.  Tick Level Statistics  

3.1.  Basic Book Statistics.  The most important tick-level statistic is the  mid price , deﬁned as  

$$
{\mathrm{mid}}={\frac{1}{2}}({\mathrm{mid}}+{\mathrm{offer}})
$$  

Next most important is the  VWA  $P$   or  volume-weighted average price  deﬁned for trades of sizes    $V_{i}$   at prices    $P_{i}$   to be  

$$
\mathrm{VWAP}={\frac{1}{N}}\sum_{1}^{N}P_{i}V_{i}
$$  

The VWAP is a minimal representation of tradable position changes.  

Somewhat less useful is a    $T W A P$   or  time-weighted average price , which performs the same sum over time periods rather than trades.  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/ef500761034b1103007f1eb929d0b3dcfa4317a713fd496a7ba0dd9c783b8b51.jpg)  
Figure 3.  Bitcoin market and trades over a 20 second period. Bid/o!er spread is obvious, but the market had no level changes.  

More interesting is an  order-weighted average price , formed from the observation that if we have many more o!ers than bids, the  clearing price  at which participants collectively would be willing to trade were tick sizes smaller is closer to the bid than the mid price. This is not an exact science, but given a top of book with    $N_{B}$   bids at price    $B$   and    $N_{A}$   o!ers at price    $A$  one reasonable formula weights with square roots  

" " 
$$
w=\sqrt{N_{A}}+\sqrt{N_{B}}
$$  

$$
\mathrm{OWA}={\frac{\sqrt{N_{A}}}{w}}B+{\frac{\sqrt{N_{B}}}{w}}A
$$  

Clearly, other weighting schemes, possibly involving further levels of the book, can be incorporated into alternative versions of the OWA.  

Arguably, the OWA is a predictive model, since we can use it to predict whether the next trade will occur on the bid side or the o!er side of the book. The economic intuition is that if an order book has a great deal of orders on the o!er, and very few on the bid, then (A) quite a few people are trying to sell and (B) it would not take many of them crossing the book to eliminate all the remaining bid orders, thereby dropping it one level. The trouble with OWA as a predictive model is that its predictions are strong precisely when many orders are already in the books on one side, ahead of any orders placed by a new participant.  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/c0bdde7ee98390f954de2da91ef61c49868cc4f42ff4a46c2c09f4078a9b103e.jpg)  
Figure 4.  Bitcoin market and trades over a 1 second period. We observe the market trading through the bid.  

3.2.  Trade Marking.  A very common derived statistic is  marked  trades, where bids and o!ers are marked according to whether a buyer initiated the transaction, or the seller initiated it. This process is ﬂattered as the  Lee-Ready Algorithm  and essentially consists of the following for each trade  

•  Find the best bid and o!er as of the trade time •  Compare the trade price to them •  If the trade price equals the best bid, mark as seller-initiated •  If the trade price equals the best o!er, mark as buyer-initiated •  (Optional) Otherwise, mark according to whether trade price was below or above mid price  

As stated, the algorithm may be too simple. For example block trades in equity markets and trades on quoted calendar spreads in futures markets may not be appropriate for marking.  

Easley  et alia ’s  VPIN  or  volume-weighted probability of informed trading  for a time    $t$   compares buyer-initiated versus seller-initiated trades in    $N$   windows preceding    $t$  . The idea is that if many trades are crossing the spread in the same direction, then the market is likely to have more informed directional buyers than  noise traders  who lack particular information.  
We begin by deﬁning  order imbalance  in the    $n$  th window by taking    $V^{B}$    to be the volume of buyer-initiated trades and    $V^{S}$    to be the volume of seller-initiated trades, and setting the imbalance as  

$$
I_{n}=\frac{|V_{n}^{B}-V_{n}^{S}|}{V_{n}^{B}+V_{n}^{S}}
$$  

We can now set VPIN to be the mean  

$$
\mathrm{VPIN}=\frac{1}{N}\sum_{n=1}^{N}I_{n}
$$  

3.3.  Flow.  A common (and simpler) extension of this idea is  trade ﬂow , which is a running tally of signed trade sizes where the sign is deﬁned as 1 if the trade was seller-initiated and -1 if it was buyer-initiated. At any moment, we examine all reported trades within the last time period of length    $\tau$  . Using the notation above, we can then deﬁne ﬂow as  

$$
F_{t}^{(\tau)}=V_{(t-\tau,t)}^{B}-V_{(t-\tau,t)}^{S}
$$  

Clearly this can be normalized or transformed in many ways, with the goal of achieving more predictive forms.  

The essential idea behind ﬂow as a quantitative metric is that, in circumstances when many sellers are willing to cross that market-making bid-o!er spread to complete their transactions, there is likely to be new information driving their choices. We do not know exactly what it is, but we certainly want to adapt to it.  

When ﬂow has a stable sign over macroscopic periods of time, it is a manifestation of supply and demand imbalance, and so it (usually) corresponds to steady price movements over a given time period. In a price time series, this has the appearance of  momentum  but the fundamental underlying process is economic (rather than the mysticism of momentum).  

3.4.  Returns.  We commonly think of the interval    $T$   return of an asset as of time    $t$   in either absolute terms, as  

$$
r_{t}^{(T)}=\frac{P_{t}}{P_{t-T}}-1
$$  

or in logarithmic terms  

$$
r_{t}^{(T)}=\log\left(\frac{P_{t}}{P_{t-T}}\right)
$$  

but we now see that the idea of knowing a single price    $P_{t}$   at some time    $t$   is somewhat optimistic. Really all we have is a set of order prices, and perhaps a recent trade price to go by.  

Let’s say we were to deﬁne    $P_{t}$   as the mid price. Naturally this stays constant over some time intervals, implying that returns are constantly decreasing in absolute value over this time. In addition, the return in any period becomes fairly sensitive to exactly which ticks the period contains.  

We cannot entirely overcome the ambiguity, but we can certainly alleviate the tick-sensitivity problem by using an EWMA. We deﬁne  

$$
r_{t}^{(T)}=\log\left(\frac{P_{t}}{\mathrm{EWMA}\left(P,\lambda=\frac{1}{T}\right)}\right)
$$  
#  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/9b2f5a80b8ed26974f33e97f0b488ec3e6eefe67f67022a23db49c3c154c87e6.jpg)  
Figure 5.  Price changes and returns are ambiguous in deﬁnition, and appear to vary wildly, at short time scales.  

which can conveniently be computed without saving past ticks.  

A common issue with tick level data is the long periods of boredom interrupted by short intervals of terror. That is, data updates come at certain times (often bunched) so at a su”ciently small timescale correlations appear to drop to zero.  
# PARAMETER REVERSION  
# From  Q  Parameters To  P  models  

To the extent we trust our sense of what parameters in a model are reasonable, “stress” in model parameters equates to proﬁt opportunity. How do we decide when parameters are truly stressed?  
# Parameter Cones  

Burghardt (1990) pointed out an elegant visual means to measure current parameter values of a parameter (in his case, volatility) against past quantiles.  
PBPB Vol Cones  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/084d2b59ddebca3aa8b60efebc1ed758ef95773acfba0d6ccb5061106c20e079.jpg)  

Figure 1.  Volatility cones show recent vols are fairly normal, except perhaps at the 60 day scale.  
# Taxonomy Of Reversion  

Parameters that tend to revert include (some) 10-Q ﬁ- nancial accounting ratios, volatility surfaces and varvol, yield curve shapes, default rates and risks, and general correlation.  

Parameters that revert, but not reliably, include a few other ﬁnancial accounting ratios, FX fundamentals, betas and pairwise correlations, and post-shock prices.  
# Beware Of Regime Shifts  

The less well a model ﬁts the market, and the more parameters it has, the likelier it is to fall victim to apparent changes in regime that have no economic basis. This can lead to an optimization algorithm ﬁnding jumps in model parameters that ultimately lead to noise trading or worse.  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/570b89e1e7241295700e4722ddbc5ab23ad295eb7c26146b6dd38b94b9afd382.jpg)  

Figure 2.  An objective function used for parameter choice may change as time passes and incoming information is updated.  
# The Uses Of Decaying Weights  

Traditional statistics and parameter estimation from historical data have tended to use data windows (rolling ones if necessary). We see this in Burghardt’s original deﬁnition of volatility cones.  

In many cases, however, it is more reasonable to use some weighting scheme, where the weights decay toward zero as data items age. If we choose particular functional forms, particularly exponential weighting, computation costs can be greatly reduced as well.  
# EWMA  

The simplest example of this is the exponentially-weighted moving average where we take some   $0<\lambda<1$   and compute the average  

$$
{\bar{x}}={\frac{\sum_{n=0}^{\infty}\lambda^{n}x_{-n}}{\sum_{n=0}^{\infty}\lambda^{n}}}
$$  
# EWMA Update  

This doesn’t necessarily look cheap or simple, but it enjoys a 1-pass or  online algorithm  where we take (now for increasing    $n$  )  

$$
\bar{x}_{0}=x_{0}
$$  

and  

$$
\bar{x}_{n+1}=\lambda\bar{x}_{n}+(1-\lambda)x_{n+1}
$$  
# Update Algorithms  

Online algorithms, also known as  update algorithms  are algorithms in which a small amount of state information is stored, and each incoming datum allows us to derive the new desired output, and new algorithm state, in relatively few computations.  
# Nontrivial State Example  

In the case of the EWMA, this state is simply the EWMA value   $\bar{x}$   itself. For exponentially-weighted (or even windowed) estimates of variance, the state is actually two data elements corresponding roughly to the sum of squares and sum of square di↵erences.  

Many stochastic control perspectives and machine learning algorithms make heavy use of update algorithms.  
# OPPORTUNITY IDENTIFICATION AND BACK TESTING  

# 1.  The Role of Historical Simulation  

A well-designed quantitative trading strategy nearly always undergoes a certain amount of analysis against historical data. There are various reasons to do this  

•  Find out if the strategy is worth pursuing as a business case  $\bullet$   Make as much money as possible, by optimizing its parameters  $\bullet$   Develop a sense of risks and rewards expected in potential live trading scenarios  

# 2.  Major Strategy Metrics  

When we judge a strategy, either in historical simulation or in actual performance, there are various metrics we can use. They range from extremely simple ones, such as annualized rate of return with no correction for fees, to more complex ones such as cost-adjusted risk/reward ratios. Here we look at some of the common choices.  

2.1.  Return Opportunity.  To compute return  opportunity , we simply take a set of actual or hypothetical trades, often of equal size and sometimes without regard to position accumulation costs (bid/ask spreads), ﬁgure out the corresponding    $P L$   (proﬁts or losses), and then divide each by position notional. This gives a rate of return per trade, which we can then average over all trades to get a return opportunity estimate.  

Certainly, we can do more sophisticated things such as examining the interquartile range of returns, or weighting simulated trades, or altering presumed trade sizes, but that takes us more into the realm of a full backtest. /next frame Opportunity or Backtest The essential di!erence between opportunity and backtest is the ﬁdelity and sophistication. If we are ignoring fees and other signiﬁcant but predictable contributors to PL, then we are looking only at opportunity.  

2.2.  Strategy Returns.  To compute strategy returns, we construct a somewhat more plausible set of trades, sized perhaps by daily traded notional, sum up the PL, and divide by the sum of notionals to develop strategy returns. At this point, we are likely to begin taking costs into account (hedge fund-style management fees if we are addressing outside investors, internal tech and overhead costs for insiders).  

2.3.  Backtested Returns.  Here, we make clear and defensible assumptions about trading costs and trade sizes attainable. We simulate using a reasonable set of risk limits and a reasonable risk model. We assume large positions may require many trades to obtain or liquidate. Preferably, we run any simulations against actual market tick data. We make assumptions about capital requirements and capital held, and report returns on capital rather than on notional.  

2.4.  Metrics Derived From Return Series.  Once we have returns, there are a few important metrics we can derive from them  
2.4.1.  Sharpe Ratio.  The original  Sharpe ratio  was deﬁned in terms of some “risk-free” rate  $r_{f}$   as  

$$
S_{\mathrm{Orig}}={\frac{\mathbb{E}\left[r-r_{f}\right]}{\sqrt{\mathbb{E}\left[r^{2}\right]}}}
$$  

The Sharpe ratio is now universally used in its modiﬁed form, sometimes called the  information ratio  where we base on some benchmark return    $r_{b}$   (which might be 0 for some cases)  

$$
S_{\mathrm{Modified}}=\frac{\mathbb{E}[r-r_{b}]}{\sqrt{\mathbb{E}\big[(r-r_{b})^{2}\big]}}
$$  

In the rare case the strategy exactly replicates the    $r_{b}$  , Sharpe ratio is undeﬁned.  

2.4.2.  Sortino Ratio.  The  Sortino ratio is much like the Sharpe ratio, but it only penalizes cases where return disappoints us versus the benchmark  

$$
S_{\mathrm{Corino}}={\frac{\mathbb{E}[r-r_{b}]}{\sqrt{\mathbb{E}\left[(r-r_{b})^{2}\right|r<r_{b}\right]}}}
$$  

Note the Sortino ratio may not be well-deﬁned if our benchmark is not competitive, because then we may have no returns that under perform the benchmark, and thus an empty set in the expectation.  

If everything is close to gaussian, Sharpe ratio and Sortino ratio scale (approximately) with the square root of time, so that a strategy with daily Sharpe ratio of 0.1 will have an annual Sharpe ratio of about 1.6.  

2.4.3.  Largest Single-Period Drawdown.  Taking some pre-deﬁned period, typically a day, week, or month, we examine the history of the strategy for the worst-performing such period.  

2.4.4.  Maximum Drawdown.  We look at maximum drawdown as maximum possible losses incurred by someone who joined the strategy at some peak, and liquidated in some later valley.  

2.4.5.  Downside Beta.  We compute at the beta (essentially, correlation) of strategy returns to market returns in cases when the overall market is losing money. To do so, we look at strategy returns    $r_{t}$   conditional on market returns    $r_{t}^{(M)}$  , and ﬁt the model  

$$
r\sim r^{(M)}+\mathrm{Const}
$$  

on the data set  

$$
\left\{r_{t},r_{t}^{(M)}\right|r^{(M)}<0\right\}
$$
 '''  

2.4.6.  Stress Scenarios and Stress Beta.  We can choose some scenarios we think would be particularly stressful for the strategy, and examine is average returns or betas to the market in those cases.  

2.4.7.  Return Moments.  In addition to the ﬁrst moment (mean) of returns, we can learn important information about risk from seconds and third moments,  skew  and  kurtosis .  
2.5.  Choice of Benchmarks.  Good benchmarks for a strategy consist of tradable alternatives that are highly formulaic (often buy-and-hold), work with publicly traded and marked liquid assets, and are expected to be related in some meaningful way. For example, a strategy trading convertible bonds might be judged against a buy-and-hold strategy of simply maintaining a position in some convertible bond ETF ( exchange-traded fund ). Occasionally a reasonable benchmark may be comprised of a competing internal strategy.  

It is a common phenomenon that, over time, we observe  beta creep  in quantitative investing, where at ﬁrst no simple benchmark appears to correlate to a strategy returns. As markets learn and mature, products and methods arise to replicate the strategy (at least partially). Whereas they previously had no “beta” to any other security, they begin to exhibit beta to these new securities. it has “crept up” on them.  

We have observed this in the equity markets from original risk-free benchmarks, through CAPM and index benchmarks, Fama/French and now ETFs.  

2.5.1.  Fama, French and Carhart.  Long ago, asset managers were judged only by gross returns. Eventually, investors realized only market-beating performance was truly worth rewarding. As managers and investors have grown more sophisticated, the concept of out performance has become more sophisticated.  

The Fama French factor model is rightly famous, because it has a long pedigree of explaining otherwise unusual-seeming out performance in returns. It contains a market factor, a value minus growth factor, and a small minus big factor. Carhart added a momentum factor, though the validity of a momentum factor remains debatable.  

2.6.  Return Decomposition s.  Once we have a (historical or simulated) time series of strategy returns, it is a simple matter to regress them against a few benchmarks simultaneously. By examining the coe”cients and residuals of the regression, we are able to form a  return decomposition , which attributes a proportion of PL to each benchmark, and the residual PL, denoted alpha or    $\alpha$  , to strategy novelties. Those novelties can then be presumed to consist of some combination of luck, statistical bias, and skill.  

Reasonable benchmarks for this purpose include  

•  Fama/French/Carhart •  Yield Curve Duration, Credit Risk  $\bullet$   Macroeconomic growth and inﬂation  $\bullet$   Market state (volatility, market volume and spreads)  

Table 1.  CalPERS Performance, 21 Years 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/c9093087ee29f38fe915c8503d5c09366342d6a3bec6240db89b48573075cf25.jpg)  
Take for example the retirement savings fund for California public employees in Table  1 . This is a large, professionally managed fund with performance information distributed publicly. We ﬁnd very strong correlation to overall market performance.  

2.6.1.  Short Positions, Benchmarks And Alpha.  One under appreciated property of buy-andhold benchmarks is that, while they are easy to create for a   $100\%$   long or   $100\%$   short strategy, it is puzzling to form benchmarks for strategies that are long some securities and short others. Even a 130/30 mutual fund is tricky to handle.  

If we simultaneously run against a reasonably complete set of benchmarks, the residual return, which has theoretically been controlled for factor exposures of any important kind, is called  portable alpha . In principle it will be uncorrelated with any other strategy and so can be advantageously combined with other portfolios. When it really exists, it is highly desirable for those reasons.  

By hedging, we can truly construct the portable alpha. At any moment, for each benchmark  $B$  , we take its beta from the regression and enter an “extra” position of size  

$$
-{\boldsymbol{\beta}}\cdot{\boldsymbol{B}}
$$  

The gross pool of alpha available to all actors is zero. Of course, each of them has overhead so the net alpha is in fact negative. Any actor has some ﬁnite supply available to them given their skills, and it is constantly reduced by beta creep.  

For any given trade, the trader on the other side is likely an informed investor. Overall, seeking alpha is extremely di”cult.  

2.7.  Further Metrics.  We have further metrics that are important to examine for a strategy. In particular, we care about trade frequency, turnover, capacity, competition/crowding.  

# 3.  Backtest Prerequisites  

What do we need to form a good backtest?  

3.1.  Asset Prices.  We cannot get very far without some way of judging PL, for which we need asset prices. In public markets such as US equity and futures markets, this is usually fairly simple. For OTC and closed markets, such as exotic options or rates options, the problem becomes more di”cult. If we have not already got the data we must ﬁnd a vendor. Certain markets, notably  distributed exchanges  for crypto tokens are inherently public (though technical skill is often needed to extract historical information from them). Others, such as developed-economy equity and futures markets, have some limited historical data available, with most professionals paying for cleaned and normalized data streams. Over-the-counter markets tend to be quite obscure, thereby manifesting a barrier to entry for outsiders and startups.  

3.2.  Trading cost assumptions.  We often assume that trades happen only by crossing bid/o!er spreads. This raises questions of the quality of historical data we have on spread sizes and quantities available for liquidity takers. For equities, the information is at least public. For corporate ﬁxed income, the spreads can be   $2–5\%$  , for government ﬁxed income about   $1/8\%$   and for liquid FX pairs about   $1/4\%$  .  

Transactions taking place on public exchanges also attract fees. The typical structure is that the liquidity taker (the entity crossing the spread) pays a small fee, while the market maker collects a slightly smaller fee, with the di!erence going to the exchange.  
Trading costs are higher for bigger transactions. A rule of thumb is for total transaction sizes of    $N$   unit in some security    $S$  , trading costs will look like  

$$
c_{0}^{(S)}+c_{\frac{1}{2}}^{(S)}\sqrt{N}
$$  

where the constants    $c_{0}$   and    $c_{\frac{1}{2}}$    vary by security.  

Almgren and Chriss (2000) provide a more sophisticated picture combining a GBM-like random walk with  price impact functions  including a permanent impact based on trading rate  $v$  

$$
g(v)=\gamma v
$$  

This sums to a quadratic in size and trading rate, varying from  

$$
\frac{1}{2}\gamma N^{2}+\epsilon N+(\eta-\frac{1}{2}\gamma\tau)\frac{N^{2}}{T}
$$  

to  

$$
\epsilon N+\eta\frac{N^{2}}{\tau}
$$  

depending on the scaling plan.  

3.3.  Capital Size and Funding Rates.  Bigger capital means more dollars of proﬁt, but probably smaller returns. It is normal to operate with  leverage  where the capital used is rather less than the notional of positions taken. In this case, one has to  fund  ones positions by borrowing, typically from the prime broker. This is done with reference to some standard rate like  SOFR  (or formerly LIBOR).  

Excess capital in a portfolio may receive interest, but never at the same rate pad for borrowing. The overall di!erence is called the  borrow/lend spread .  

3.4.  Taxes and fees.  Asset trades are frequently subject to taxes, for example SEC Section 31 fees on US equity transactions. These are passed on to investors.  

In addition, asset managers nearly always charge fees to outside investors. Therefore, backtest results of interest to investors are based on returns net of these fees, and all other predictable costs.  

3.5.  Available Assets.  We call the assets presumed available for trade at a given time the universe . A wider universe means the strategy has a broader choice of investments, and can either cherry-pick the very best return opportunities, or deploy more capital in the pursuit of higher absolute PL. A broad universe a!ords better  divers i cation  allowing more reliable performance.  

3.6.  Human/Computer System Performance Assumptions.  Lags from decision time to action vary widely by the systems in place as well as what the market makes practical. For futures, equities and FX, largely traded electronically, it is reasonable to assume 1 second to 5 minutes. For government ﬁxed income, 30 seconds to 60 minutes, and for corporate ﬁxed income 1 to 10 days.  

3.7.  Position Size and Scaling Rules.  Part of any trading strategy is a means of deciding target position size and how to scale into a position. One might choose equal-weighting within a universe, or weight by liquidity, expected pro t ability, a Markowitz-style analysis, or any combination of these.  
Most historical databases are limited to point-in-time capture of prices, either of transactions or quotes. It is important not to rely heavily on the assumption that point-in-time prices would have been transact able in signiﬁcant size. There is a lot of complexity in inferring, from historical point-in-time data, what transactions really  could  have been made. The question has to do with market size and structure, desired position size, and so on.  

When a desired position is small compared to the liquidity of a security, scaling into it isn’t an issue. However in many cases we desire position sizes that can take hours, days or weeks to accumulate. There is of course risk in missing out on good positions or continuing to hold bad positions which must be balanced against costs and availability. The seminal paper in this ﬁeld is Almgren and Chriss, whose work is often described as  implementation shortfall .  

A common rough solution begins with    $V W A P$  , or volume-weighted average pricing.  

The classical perspective on position sizing is the  Kelly criterion  where we have a given size of capital and want to make the most of it without risking ruin. We have just one “thing” we can do, and know its expected return and variability. Kelly ﬁnds under simple assumptions that we should invest a proportion    $s$   of trading capital where  

$$
s=\frac{\operatorname*{Pr}\{\mathrm{w}>0\}}{\mathbb{E}\!\left[\left.w\right|w<0\right]}-\frac{\operatorname*{Pr}\{\mathrm{w}<0\}}{\mathbb{E}\!\left[\left.w\right|w>0\right]}
$$  

is based on proﬁt probability and expected PL sizes.  

The criterion is slow to converge to optimality, requires  a priori  probabilities, assumes event independence, and ignores the vanishing edge of pro t ability as    $s$   goes to zero. Some of this can be addressed with the  fractional Kelly  criterion.  

Another way to address some of these problems is due to  Browne , who noted that by altering the investment schedule one can obtain far better short-term behavior at the cost of a small positive risk of ruin. This corresponds more closely to true human interests and behavior.  

Browne’s mathematical target is to maximize the probability of achieving a given wealth    $b$  before some time    $T$   deadline, given some expected excess pro t ability    $x$  . It results in  

$$
s={\frac{1}{\sigma{\sqrt{T}}}}{\frac{b e^{-r T}}{x}}\,\phi\!\left(\Phi^{-1}\left({\frac{x}{b}}e^{r T}\right)\right)
$$  

which readers familiar with options will recognize as the hedging strategy of a binary call.  

The result is that, given some threshold    $\epsilon$   Browne will outperform Kelly by that threshold with probability   $(1+\epsilon)^{-1}$  . A Kelly criterion on a strategy with   $30\%$   volatility requires about 10,000 years to beat a buy-and-hold strategy with   $95\%$   conﬁdence. A Browne criterion that accepts 5% ruin probability reduces the time to 85 years.  

3.8.  Hedging Rules.  Most quantitative trading strategies aim to hedge out certain risks. A long-short equity strategy may be run a 0%,   $25\%$  ,   $100\%$   or any other proportion net long. An options strategy will hedge delta and maybe gamma. Credit strategies often hedge using CDX or bond ETFs.  

Note that (fully) hedging against some security at least theoretically removes it from the list of reasonable benchmarks.  

Both the Kelly and Browne criteria are mainly useful for allocation of capital to strategies (where they are useful at all). This is because position sizing considerations typically need to take into account multiple potential investments, with various risk-reward criteria among them, and where they are far from independent of each otehr.  
3.9.  Evaluation Frequencies.  Fully algorithmic trading strategies attempt to handle all incoming information in real time. Others must decide on target time periods in which to let analyses lie fallow. These time periods need not be purely clock-based, since a ﬂood of news in the market should naturally be accompanied by re-evaluations.  

3.10.  Position Age Rules.  Sometimes quantitative models just “like” certain positions, and we don’t really believe they should be held for extended periods. To this end, many strategies create aging rules in which positions are liquidated as they become too “stale”.  

3.11.  Short Position Assumptions.  Terminology for short positions includes  shorting  a security, which means opening a short position  $\mathbf{\chi}^{1}$  , and  covering a short , which means closing the position by buying securities in the market and sending them to the lender. Shorting securities is quite di!erent from the common perception. Except in futures and options, is not easy to do, it costs extra money, and it involves (invisibly) selling an option. Unless bypassed by a swap agreement, creating a short position involves ﬁnding a  locate (usually through the prime broker but sometime in a  self-locate ), agreeing on  repo rate  which may be  special , abiding by regulations and contracted limits, and running the risk of forced buy-in . For equities, most shorting is done at  general collateral  or GC rates, but some cases, the “special” ones, provide less repo or even cost money, in e!ect having a special rate less than zero. For most other securities, the repo rate is nearly always special. One big problem is that historical information on repo rates and short availability is generally hard to obtain, expensive and of poor quality, unless you are at a large institution with good record-keeping.  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/017e760fa1e63e077c0ddea412dcdb5453aab8970c9d09c164e9f944bf06a8ee.jpg)  
4.  Back testing Considerations By Asset Class  

# 4.1.  Equities.  

4.1.1.  As-of data.  Equity models often take into account SEC ﬁlings, which are subject to correction.  

4.1.2.  Mergers and spino!s.  Mergers and spino!s modify the available universe while also

 (typically) invalidating the economic assumptions behind our models.  

4.1.3.  Dividends and splits.  Equity analyses are often performed with  split and dividend adjusted  data. It is important to keep in mind that this in itself is e!ectively a back testing assumption of instant costless reinvestment. For a long-horizon strategy that is reasonable but at anything ﬁner than monthly frequency it begins to break down.  

We sometimes see  special dividends  in equities, which saddle a portfolio with unusually large cashﬂows while also modifying e!ective position sizes. These can cause problems for casual data aggregator s, such as Yahoo, as seen in Figure  1  . In this case, XLF spun o!    $\P4.44356$  per share, in a combination of cash and XLRE positions. Note the data sources agree on raw and adjusted data  after  the dividend, but that Yahoo is incorrect before it.  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/b089b64a30cf92ef2e01b8b2ce8f362f74353c54eaf68b1c97394a676e8be804.jpg)  
Figure 1.  XLF dividend adjustment problems for Yahoo: a special dividend and its e!ect on reported prices on Sep 16, 2016 (as of May 2019) are reﬂected.  

Naively, one might think it reasonable to use the Yahoo “Raw” series. However, then standard dividends would remain unadjusted for the remainder of the price series. In addition, returns inferred from the Yahoo “Raw” price, though computed from a time series without discontinuity, would be slightly di!erent.  

4.1.4.  High sensitivity to common benchmarks.  If we take overall market return as a benchmark, we ﬁnd most equities have correlations over 60%. If we allow further benchmarks to include Fama French or a set of ETFs, it can be surprising how much the rest resembles low-volatility noise.  

# 4.2.  Credit Instruments.  

4.2.1.  Finding hedging instruments.  There are not many credit ETFs, and credit indexes tend to be untradable, so the only reasonable hedging instruments in corporate credit are CDX (in very mature markets) or highly liquid corporate bonds in related companies, which take care of market risk without addressing default risk.  

4.2.2.  Scaling and inventory.  The credit markets are OTC and are traded in large lot sizes, making minimum position sizes quite large. At the same time, scaling strategies need to take into account the fact that these markets are quite slow relative to electronic markets. nextframe  
4.2.3.  Historical data.  Databases of historical prices are relatively easy to obtain, though many are only approximate. Historical quote databases are more expensive but considerably better, but it is important to keep in mind that quotes in over-the-conuter markets (such as CDS and bonds) are almost never “hard”.  

Historical trade data for non-144A US bonds have TRACE data, though it does not give accurate sizes.  

Though credit instruments ultimately trade on probability of default,    $h$  , there is no historical data for    $h$  .  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/40bd77fbc890eb51945aa3ba7bfc59a45fd9cceaa23d70a67acb862f03e085f9.jpg)  
4.2.4.  Tradable instruments.  There are extremely many tradable bonds in the universe because most issuers have several bonds outstanding at any given time. This is in contrast to equity, where it is extremely rare for a corporation to have more than one type of publicly traded equity.  

4.2.5.  Optional it y adjustments.  Corporate bonds often come with optional it y clauses, most commonly embedded calls, but also puts, green shoes, conditionals and more.  

4.2.6.  Long time horizons.  Many players in credit markets have very long time horizons, making liquidity very di!erent from outstanding notional, and lengthening the time horizons quantitative traders must be willing to consider.  

4.2.7.  Market sentiment regimes.  Credit markets undergo long periods of over- and underestimates of default risk. Clever strategies therefore should generally hedge against overall sentiment.  
4.3.  Foreign Exchange.  Foreign exchange, or    $F X$   trading involves currency transactions. A certain number of euros are swapped for yen, or a contract is made to engage in such a transaction sometime in the future. The markets here a split into widely traded futures and options, plus a cash market that operates on crossing networks mainly controlled by large banks. This latter point has important consequences for capital usage, because o!setting trades in di!erent markets may get poor treatment.  

4.3.1.  Interventions.  FX rates follow general market principles most of the time, interspersed with sizable government interventions of varying predictability. The majority of the time, quantitative models are useful, but the interventions are poor fodder for modeling.  

4.3.2.  Pegs.  A common form of ongoing intervention is a peg (or sometimes a pair of lower and upper bounds), maintained by frequent interventions. Strategies relying on pegs may go suddenly bad, and strategies expecting pegs to fail can take a very long time to come to fruition.  

4.3.3.  Sizing.  

4.3.4.  Similarity to common strategies.  FX rates are clearly linked to many assets, such as foreign equities and bonds. Crises therefore tend to come with high covariance to other asset classes. In addition, these links mean that one should consider which elements of foreign economies may be driving FX rates.  

Unlike equities, a net long portfolio of foreign currencies has no theoretical positive excess return expectation. In each respective country, the currency is, of course, just cash, so the risk premium is zero.  

# 4.4.  Options.  

4.4.1.  Probability of ruin at high leverage.  Options are often very highly levered investments, so their use comes with enhanced probability of ruin. Hedging can control this to an extent, but markets can begin crashing just when liquidity disappears. The problem is exacerbated for market makers, who tend to be structurally short options.  

4.4.2.  Volatility hedging.  Options strategies almost always involve delta-hedging. It is extremely common to demand control of gamma/vega (volatility exposure) as well.  
# A SIMPLE QUANTITATIVE TRADING EXAMPLE: SPREADS  

# 1.  Working Out A Spread Trade  

Let’s work out what the bones of a quantitative trading strategy might entail by examining one of the simplest examples: the spread trade.  

Spread trading strategies have a long history and many current forms. Because they involve trading more than one asset, they are just about the simplest example of a case where we can stochastic ally control risk versus reward.  

1.1.  What Is A Spread?  Let’s say we monitor prices or returns on a pair of securities. For sake of argument, we will say we are monitoring the prices    $f_{t}^{(2)},f_{t}^{(5)}$  of 2 and 5 year CME   1 treasury note futures . We can construct a new variable consisting of the di!erence between them  

$$
s_{t}:=f_{t}^{(5)}-f_{t}^{(2)}
$$  

This value    $s_{t}$   is called the  spread  or  di!erence spread  between the 2 and 5 year note futures, and we often think in terms of trading spreads, even when in practice the trades are expressed in underlying securities such as futures contracts.  

1.1.1.  Return Spreads.  For assets with clear fundamental relations, we tend to use di!erence spreads as above. Frequently, we prefer to assume that old di!erences are are “priced in” and therefore unlikely to change, in which case we may prefer  return spreads  in which we consider how much returns for the two assets have di!ered in recent history.  

1.2.  Reversion To The Mean.  We might ﬁnd that, during the 20 years from 1995 to 2015, the average of    was   $\bar{s}=8.5$  . It is easy to conceive of a strategy that would plausibly make  $s_{t}$  money by always making bets that, whatever the value of    $s_{t}$  , it is expected to revert back to around 8.5. How would such a spread trading strategy look?  

It probably does not make sense to make bets when the current    $s_{t}$   is very close to 8.5. So, for example, if    $s_{t}=8.499$   or    $s_{t}=8.501$   we should not hold a position. On the other hand, if  $s_{t}=4.0$   this looks like a good opportunity to bet that    $s$   will soon rise. We do not necessarily know if    $f_{t}^{(2)}$  will fall or    $f_{t}^{(5)}$  will rise, but we think some combination of those things will happen. So it makes sense to both short some 2 year note futures and buy some 5 year note futures. We call this “buying” the spread because we are trading securities in such a way that we think the spread will rise.  

For similar reasons, if we see    $s_{t}=12.0$   then we ought to buy some 2 year note futures and short some 5 year note futures. We call this “shorting” the spread.  

Now, if    $s_{t}\,=\,14.0$  , it is easy to argue that the opportunity is greater and we should be shorting even more of the spread. But remember, it probably only got to 14.0 by going through 12.0 at some point. We are likely  already  short the spread and, since it has risen further, have lost money on the position. Are we prepared to lose more?  
In spread trading, it is common to have some point at which you admit that your hypothesis (of spread reverting to its mean) has been so contradicted by market data that you are no longer willing to believe it, at least not with your dollars. Such a point is often deﬁned in terms of PL – dollars lost to the position, and is called a  stop loss level . Once you have reached it, you resolve to close out all positions, and perhaps wait a while before attempting a similar spread trade again.  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/9c27641d88d833ba3026cad8c42064e1c67e36c51be82e409e6081013275ab4c.jpg)  
Figure 1.  Trading A Hypothetical Spread  

The  human  complexity of spread trading is very low. It can be done in 50-150 lines of R or Python, and is feasible even in Excel. However, when we consider how might approach it in practice, we ﬁnd there are many parameters to determine and they are likely to make us run simulations over and over. These parameters include  

•  Which security pairs to run on •  Entry and exit boundaries •  Hedge proportions, if not 1:1 •  Hedge determination algorithms  $\bullet$   Lookback periods for hedge (and possibly returns) computations  $\bullet$   Stop loss/ position sizing boundaries  
Testing 16 possibilities for each of the above would, in an exhaustive grid search, lead to running over 15 million backtests. If each one takes 5 seconds, we will need about 3 years to run them all.  

1.3.  Generalizations To More Stochastic Control.  Though the (nominally) zero-centered series we have based our scheme on was a direct spread, we can easily imagine ﬁrst running a regression of future returns against current observed spread. This crude estimate of  alpha can then serve as the basis on which we choose to send orders to the market in a very simple trading scheme.  

If our scheme is controlling market orders, we may well assume that (given a cost model) we are able to take on a small position with relative certainty. If instead the scheme is controlling resting orders  (i.e.  liquidity-adding  or  passive  orders) then we must further account for tracking outstanding orders and when to cancel them. This does not apply only to electronic markets. Over-the-counter markets have human equivalents (often called  standing  orders) to the passive electronic orders.  
