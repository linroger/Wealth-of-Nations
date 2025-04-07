__MASK_7_24__

# Lecture 3-Dynamics of Returns

__MASK_6_14__
## Lecture 3

We now focus on __MASK_6_15__ over time. Recall from lecture 1 the formula for the optimal risky asset share in the single risky asset case:

__MASK_2_0__

The inputs of this optimal allocation formula could potentially vary over time. Perhaps there are times when expected excess returns are high and times when they are low? Perhaps there are times when volatility is high and other times when volatility is low? If such time-variation in expected returns or risk exists,  can it be exploited in a markettiming strategy? Later,  in lecture 5 ,  we will look more detail into optimal __MASK_6_16__ in a multi-period setting when risk and expected return are time-varying. But for now,  let's just think about potentially applying this formula period-by-period,  with a oneperiod investment horizon. To do this,  we need to a statistical model that gives us expectations of next-period returns and/or forecasts of next-period volatility.

With this motivation in mind,  we will now look the data to answer questions such as: Are stock market index returns predictable? If yes,  does such predictability allow market timing? What sort of variables can be useful predictors of returns? Is volatility predictable?

### 3.1 Conditional __MASK_6_17__

Questions about the __MASK_6_18__,  predictability,  and market timing all have to do with the conditional __MASK_6_19__ of returns.

In the past two lectures we focused on the unconditional __MASK_6_20__ of returns. The unconditional distribution describes how likely various outcomes are

in general,  without picking a subset of specific situations. For example,  we discussed how to estimate the unconditional mean of stock returns by taking a simple average of returns.

In contrast,  the conditional distribution describes how likely various outcomes for returns are conditional on a subset of specific situations. For example,  suppose we come to the conclusion that the distribution of next period returns,  __MASK_3_1__ is different depending on whether returns in the current period,  __MASK_3_2__ are negative or positive. In this case,  the current period return __MASK_3_3__ is the conditioning information and the distribution of returns conditional on whether __MASK_3_4__ or __MASK_3_5__ is the conditional distribution of returns.

Now,  the conditional distribution differs from the unconditional distribution only if the conditioning information (lagged returns in our example) actually has some useful information about the shape and location of __MASK_6_21__ of future returns. To describe how the shape and location of this __MASK_6_22__ changes with conditioning information,  we need a statistical model.

For example,  a crude statistical model of the conditional distribution of stock market returns would be to assert that that future returns may be drawn from two different distributions: one that applies when the market went up in the previous month,  the other one when it fell.

Figure 3.1 plots histograms of the two distributions: one depicts the distribution of stock market returns following a gain in the previous month; the other one depicts the distribution of stock market returns following a loss in the previous month. Interestingly,  the distributions do seem to be different! Note how the distribution following a loss is more spread out and less concentrated in the middle. This means that when the stock market has fallen in the previous month then,  historically,  it was followed by a more volatile month in which returns were likely to be either very high or very low.

Just as we can characterize unconditional __MASK_6_23__s in terms of unconditional moments,  we can describe conditional distributions in terms of conditional moments. If __MASK_3_6__ is a variable that represents our conditioning information (in Figure __MASK_3_7__ would be an indicator for whether __MASK_3_8__ or __MASK_3_9__ ),  then we can describe the distribution of __MASK_3_10__ conditional on __MASK_3_11__ with its conditional moments such as,  e.g.,  the conditional expected return,  __MASK_3_12__,  and the conditional variance __MASK_3_13__.

To make these conditional moments useful in applications,  we need a statistical model to describe them. Here is an example: Suppose there was momentum in returns,  by which we mean that high returns in month __MASK_3_6__ are followed,  on average,  by predictably high returns in month __MASK_3_7__. We could capture this with a model for conditional expected returns such as

__MASK_2_0__

 !__MASK_4_20__

Figure 3.1: Distribution of monthly stock market returns 1927-2021 conditional on gain or loss in previous month

for some constants __MASK_3_8__. If we had instead __MASK_3_9__,  this would be a model for reversals where high past returns predict low future returns. We can use regressions to estimate such models of conditional expected returns.

We often omit stating the conditioning information explicitly and just write __MASK_3_10__,  e.g. __MASK_3_11__. This is imprecise because this notation is not explicit about the type of information we are conditioning on,  but reduces clutter in our notation. Typically this notation means that we think of the expectations conditioned on whatever is observable to an investor at time __MASK_3_12__.

If returns are independently and identically (IID) distributed,  then conditional and unconditional distributions are the same. Or,  put differently,  in this case conditioning information about the current state of the economy etc. does not contain information about the distribution of future returns. Our crude analysis of the returns conditional on previous month's gain/loss in Figure 3.1 already suggests that returns are not IID,  as the two conditional distributions shown in this figure differ substantially (although we haven't yet done a formal statistical test to see whether the difference is really statistically significant).

### 3.2 Logarithmic returns

In this lecture and the coming ones,  we will pay more attention to the __MASK_6_21__ over time. This means that we will have to take into account the compounding of returns.

Unfortunately,  working with compound returns is messy,  because compounding is multiplicative. Consider an asset that earns a sequence of returns over time: __MASK_3_13__. Calculation of the long-run return on this asset from time __MASK_3_14__ to __MASK_3_15__ involves compounding of returns over multiple periods:

__MASK_2_1__

This compound return involves products of random single period returns. Products of random variables are statistically difficult to analyze. Things quickly become intractable.

When we analyze such long-run returns,  it is often convenient to work with the natural logarithm of returns,  or short just log returns. __MASK_3_16__ We use lower-case letters to denote __MASK_3_17__ returns

__MASK_2_2__

The nice property of the log transformation is that the log of a product becomes the sum of the log of the factors of the product. Hence,  for the long-run return we get,  after taking the log,

__MASK_2_3__

i.e.,  the long-run log return is a simple sum of the individual period log returns. Sums are much easier to analyze statistically than products of random variables.

Taking the exponential function of the log return gets us back to simple returns

__MASK_2_4__

When we use log returns,  we always need to keep in mind that the log return is not the same as the simple return. For example,  as we will see in more detail in the next lecture,  looking for a portfolio that maximizes the expected log return of the portfolio is not the same as one that maximizes the expected simple return. For now,  let's just note two things that we should keep in mind.

First,  the expected log return is not the same as the log of one plus the expected return. The following relations hold:

__MASK_2_5__

[^8]The first inequality on the left just reflects that __MASK_3_18__ for any real __MASK_3_19__. The second inequality on the right is a special case of a mathematical law called Jensen's inequality. For risky returns with non-zero variance,  both inequalities are strict. We get a more precise statement about the relation between these two expectations if we impose an assumption about the statistical distribution of returns. More on this below.

Second,  the log of weighted average of simple returns (i.e.,  the log of a portfolio return) is not equal to the weighted average of the log returns of the individual assets. Suppose we have __MASK_3_1__ assets and we collect their returns __MASK_3_2__ in the vector __MASK_3_3__. For a portfolio with weights __MASK_3_4__,  the (simple) return on a portfolio is simply the weighted average of individual asset (simple) returns:

__MASK_2_0__

The same is not true for log returns. A weighted average of log returns is not equal to the __MASK_3_5__ return on the portfolio,  __MASK_3_6__.

Now that we have log returns in our toolbox,  we can also get a more realistic in our assumptions about the distribution of returns. In the past two lectures,  we assumed in some analyses and simulations that simple returns are normally distributed. Strictly speaking,  this assumption did not really make economic sense. The support of the normal distribution is unbounded in both tails. This means that assuming normally distributed returns implies positive probability on the event that returns are less than $-100/%,  which is impossible for assets like equity where investors are protected by limited liability and hence can lose at most their initial investment.

At short horizons,  this issue is negligible because typical return magnitudes are so small. But it matters more over longer horizons. This is why now that we are paying more attention to long-run dynamics,  we need to address this issue.

Figure 3.2 illustrates this. It shows the empirical distribution of stock market returns from 1927-2022. The top panel shows the distribution of monthly returns,  the middle panel annual returns,  and the bottom panel 10-year returns. We see that for monthly returns the fact that returns are bounded below at $-100/% does not really matter. It's just extremely unlikely that a monthly return would ever get even close to a loss of this magnitude. As a consequence,  the distribution of monthly returns looks quite symmetric. The magnitudes of upside moves tend to be similar to the magnitudes of downside moves.

In contrast,  for 10-year returns,  the picture is different. Looking at the upside in the bottom panel of Figure 3.2,  we can see 10-year periods with realized returns of 400/% or more. On the downside,  of course,  there are no downside moves of similar magnitude. The biggest losses over 10-year periods in this data set are returns of around -50/%. As a consequence,  the empirical distribution of 10 -year returns is strongly asymmetric. It basically has to be as the upside is unbounded but the downside is limited to -100 %.

 !__MASK_4_25__

Figure 3.2: Empirical stock market return distributions when returns are measured over different horizons,  1927-2022

In contrast,  it is an economically sensible approximation for many types of assets,  although of course not always literally true,  that __MASK_3_7__ returns,  __MASK_3_8__,  are normally distributed.

If log returns are normally distributed,  this means that simple returns plus one,  __MASK_3_9__,  are log-normally distributed. Since __MASK_3_10__ is bounded below by -1 when __MASK_3_11__ is normally distributed,  the log-normal distribution is consistent exactly with the theoretical lower bound on stock returns of __MASK_3_12__1+R$,  we can have a distribution of one plus simple returns that is realistically right-skewed and bounded below at zero,  but is still fully described by mean

 !__MASK_4_26__

Figure 3.3: Probability distribution of __MASK_3_13__ when __MASK_3_14__ is normally distributed

and variance.

Figure 3.3 presents an example where __MASK_3_15__ is normally distributed and hence __MASK_3_16__ has a log-normal distribution (the plot shows the distribution of __MASK_3_17__,  not __MASK_3_18__ ). Note the lower bound at -1 and also the right-skewness (greater upside) of __MASK_3_19__ compared with __MASK_3_20__.

Going in the reverse direction,  if log-normality is approximately a good description of the return distribution,  then,  if we apply the __MASK_3_21__ transformation,  __MASK_3_22__,  to empirically observed returns __MASK_3_23__,  we should be getting a distribution that looks closer to a normal distribution than the distribution of __MASK_3_24__ does.

We can see the effect of the log transformation if we redo the bottom plot from Figure 3.2 for 10-year returns,  but now with __MASK_3_4__ returns. See Figure 3.4. While the distribution is not quite normal,  it is now much closer to being symmetric. The log transformation has shrunk the long upper tail and hence removed the positive skewness. Instead,  the distribution is now somewhat negatively skewed.

At short horizons,  though,  normal distribution can often be a good approximation to the log-normal distribution. The reason is that for small variance,  the log-normal distribution becomes close to symmetric. One way to see this is to note that __MASK_3_5__

 !__MASK_4_18__

Figure 3.4: Empirical distribution of 10-year log returns on a stock market index,  19272022

__MASK_3_6__ for very small __MASK_3_7__.

Empirically,  we also see that the distribution of historical returns is closer to normal when they are measured over shorter time frames. Check out,  for instance,  the top panel of Figure 3.2. Like a normal distribution,  monthly returns are close to symmetric,  unlike the longer horizon returns in the bottom panel.

But there are some important exceptions from log-normality: Occasionally the stock market experiences violent crashes. This makes the left tail of the distribution much fatter than in a normal distribution. Occasionally,  there are also huge upward movements in a single month. This generates the fat right tail of the distribution in the top panel of Figure 3.2.

The log-normal distribution has a number of properties that we will use in the coming

weeks. If __MASK_3_8__ and __MASK_3_9__,  then

__MASK_2_0__

and hence

__MASK_2_1__

Approximately then,  at least for relatively short return measurement intervals such as monthly returns where the return magnitudes are typically not so big that the transformation by the exponential function matters much,

__MASK_2_2__

This approximation is a useful rule of thumb to keep in mind. If you see someone presenting average log returns from some investment and the variance of log returns,  you can easily get an estimate of the implied average simple returns using this formula.

### 3.3 Stock market valuation models

With log transformations in our toolkit,  we now turn our attention to valuation models that allow us to analyze how investor expectations and __MASK_6_19__ may affect pricing in the stock market (and other risky asset markets). This in turn provides insights about observable variables that may be useful for predicting stock market returns.

For now,  we use __MASK_6_20__ as a catch-all label to describe forces that affect stock prices and that do not reflect rational expectations of future cash flows of firms. This includes,  for example,  the effects of irrational investor optimism or pessimism about future cash flows. It also includes the stock price effects of time-varying risk aversion that investors may have. In the next lecture,  we'll take a more detailed look at what could explain __MASK_6_21__ changes over time.

The discounted cash flow (DCF) valuation models that you are familiar with from your introductory finance classes look somewhat like this

__MASK_2_3__

where __MASK_3_10__ is present value of cash flows,  __MASK_3_11__ are future cash flows,  and __MASK_3_12__ is a (risk-adjusted) discount rate. Here we are interested in the valuation of the stock market in aggregate,  so __MASK_3_13__ would represent the aggregate dividends of all stocks. More precisely,  __MASK_3_14__ would comprise aggregate dividends plus aggregate share repurchases,  i.e.,  the entire flow of cash to investors. To keep it short,  I'll just refer to __MASK_3_15__ as dividends.

You may also recall that if the expected cash flows are growing at constant rate __MASK_3_16__,  so that __MASK_3_17__,  then we get the so-called Gordon growth model

$$

\begin{equation*}

P_{t}=D_{t} \frac{1+G}{R-G} \tag{3.12}

\end{equation*}

__MASK_2_0__

\begin{equation*}

\frac{P_{t}}{D_{t}}=\frac{1+G}{R-G} \tag{3.13}

\end{equation*}

__MASK_2_1__

\begin{equation*}

1+R_{t+1}=\frac{D_{t+1}}{P_{t}} \tag{3.14}

\end{equation*}

__MASK_2_2__

\begin{equation*}

\frac{D_{t+1}}{P_{t}}=\frac{D_{t+1}}{D_{t}} \frac{D_{t}}{P_{t}} \tag{3.15}

\end{equation*}

__MASK_2_3__

\begin{equation*}

v_{t}=\Delta d_{t+1}-r_{t+1} \tag{3.16}

\end{equation*}

__MASK_2_4__

\begin{equation*}

1+R_{t+1}=\frac{P_{t+1}+D_{t+1}}{P_{t}} \tag{3.17}

\end{equation*}

__MASK_2_5__

\begin{equation*}

v_{t}=c+\Delta d_{t+1}-r_{t+1}+\rho v_{t+1} \tag{3.18}

\end{equation*}

__MASK_2_6__

\begin{aligned}

1+R_{t+1} & =\frac{D_{t+1}}{D_{t}} \frac{\frac{P_{t+1}}{D_{t+1}}+1}{\frac{P_{t}}{D_{t}}} \\

& =\frac{D_{t+1}}{D_{t}} \frac{\frac{P_{t+1}}{D_{t+1}}}{\frac{P_{t}}{D_{t}}}\left(1+\frac{D_{t+1}}{P_{t+1}}\right)

\end{aligned}

__MASK_2_7__

r_{t+1}=\Delta d_{t+1}+v_{t+1}-v_{t}+\log \left(1+\exp \left(-v_{t+1}\right)\right)

__MASK_2_8__

\log \left(1+\exp \left(-v_{t+1}\right)\right) \approx c-(1-\rho) v_{t+1}

__MASK_2_9__

r_{t+1} \approx c+\Delta d_{t+1}+v_{t+1}-v_{t}-(1-\rho) v_{t+1}

__MASK_2_10__

\begin{equation*}

v_{t}=c+\mathbb{E}_{t}\left[\Delta d_{t+1}\right]-\mathbb{E}_{t}\left[r_{t+1}\right]+\rho \mathbb{E}_{t}\left[v_{t+1}\right] \tag{3.19}

\end{equation*}

__MASK_2_0__

\begin{equation*}

\mathbb{E}_{t}\left[r_{t+1}\right]=c+\mathbb{E}_{t}\left[\Delta d_{t+1}\right]+\rho \mathbb{E}_{t}\left[v_{t+1}\right]-v_{t} \tag{3.20}

\end{equation*}

__MASK_2_1__

\begin{equation*}

v_{t}=c+\rho c+\Delta d_{t+1}+\rho \Delta d_{t+2}-r_{t+1}-\rho r_{t+2}+\rho^{2} v_{t+2} \tag{3.21}

\end{equation*}

__MASK_2_2__

\begin{equation*}

v_{t}=\frac{c}{1-\rho}\left(1-\rho^{T+1}\right)+\sum_{j=1}^{T+1} \rho^{j-1}\left(\Delta d_{t+j}-r_{t+j}\right)+\rho^{T+1} v_{T+1} \tag{3.22}

\end{equation*}

__MASK_2_3__

\begin{equation*}

\lim _{T \rightarrow \infty} \rho^{T+1} v_{T+1}=0 \tag{3.23}

\end{equation*}

__MASK_2_4__

\begin{equation*}

v_{t}=\frac{c}{1-\rho}+\sum_{j=1}^{\infty} \rho^{j-1}\left(\Delta d_{t+j}-r_{t+j}\right) \tag{3.24}

\end{equation*}

__MASK_2_5__

\begin{equation*}

v_{t}=\frac{c}{1-\rho}+\sum_{j=1}^{\infty} \rho^{j-1} \mathbb{E}_{t}\left[\Delta d_{t+j}\right]-\sum_{j=1}^{\infty} \rho^{j-1} \mathbb{E}_{t}\left[r_{t+j}\right] \tag{3.25}

\end{equation*}

$$

So the price-dividend ratio reflects expectations of future dividend and future returns.

The model in (3.25) could now be used for fundamental valuation. We would have to build a forecasting model for future dividend growth. This would give us the expectations of future dividend growth,  __MASK_3_6__. We could then also plug the required rate of return for __MASK_3_7__ that we would require from a stock market investment. This would then give us a model implied log price-dividend ratio __MASK_3_8__ that we could compare to the current actual __MASK_3_9__ to estimate current over/undervaluation of stock market. For example,  if the model implied __MASK_3_10__ is higher than the actual current __MASK_3_11__,  we would conclude that the stock market is currently overvalued and hence currently not an attractive investment (and possibly even an opportunity to take a short position).

In the special case that expected log dividend growth is constant,  __MASK_3_4__ and investors price the stock market with a constant required rate of expected (log) return of __MASK_3_5__,  the expression in (3.25) simplifies drastically to

__MASK_2_0__

Compare this to the Gordon growth model in (3.13). It's very similar,  showing that it's the difference between expected growth and the required rate of expected return that determines the level of the price-dividend ratio.

Substituting in this result for __MASK_3_6__ and __MASK_3_7__ from (3.26) into (3.20),  and solving for expected log returns,  we obtain

__MASK_2_1__

which is exactly what it should be: The log return investors can expect to earn is the required rate of expected log return that they priced into the stock market valuation.

### 3.4 A valuation model with __MASK_6_26__

Let's use this framework to understand how time-varying __MASK_6_27__ could affect prices,  how we could measure sentiment,  and how we could potentially exploit it in our __MASK_6_28__ strategy. For the purpose of this exercise,  suppose that equation (3.26) represents how rational investors - who are not subject to sentiment fluctuationswould value the aggregate stock market. This means that these rational investors expect constant growth of dividends __MASK_3_8__ and they would require an expected return of __MASK_3_9__ to hold the outstanding value of all stocks. Let's call the __MASK_3_10__ in (3.26) the (log) fundamental value.

In contrast,  suppose that actual investors are subject to influence of __MASK_6_29__. For example,  they are sometimes more optimistic about dividend growth and sometimes more pessimistic. Their valuation of the aggregate stock market is

__MASK_2_2__

where __MASK_3_11__ is the level of sentiment,  with __MASK_3_12__ reflecting excessive optimism and __MASK_3_13__ excessive pessimism.

Now imagine a rational investor looking at this market,  seeing __MASK_3_14__,  as determined by (3.28),  and wondering what rate of return to expect given that stock prices are subject to the influence of __MASK_6_30__. We can answer this question by substituting __MASK_3_15__ and __MASK_3_16__ from (3.28) into (3.20). Lots of terms cancel,  and we are left with

__MASK_2_3__

Naturally,  if there was no sentiment effect on prices,  as in (3.27),  a rational investor could expect to earn __MASK_3_17__,  the rate of return that rational investors would price the market to earn

according to our assumption. But with sentiment,  there is an additional component that reflects that current high sentiment __MASK_3_18__ makes the market overpriced,  which is bad for next period returns,  while high future sentiment ( __MASK_3_19__ ) makes the market overpriced in the future,  which is good for next period returns.

Also note that if sentiment and hence mispricing is constant,  __MASK_3_20__,  then this mispricing component becomes __MASK_3_21__,  which is not zero,  so it still affects returns the rational investor can expect. For example,  with constant overpricing,  __MASK_3_22__,  we have __MASK_3_23__. This reflects the fact that with a constant level of overvaluation,  even though an investor does not have to suffer from collapses of overpricing in this case,  the investor is paying more for stocks than they are really worth,  given their expected dividends,  which hurts returns.

The relationship in (3.29) also tells us that if we could forecast __MASK_3_24__,  we could calculate expected returns and therefore forecast returns. This means that to forecast returns,  we need to have a model of the dynamics of __MASK_6_31__.

A reasonable starting point for such a model of sentiment could be that sentiment is positively correlated over time (so when sentiment is,  e.g.,  above average today,  it will tend to be above average next quarter) and mean-reverting (so when sentiment is,  e.g.,  above average today,  we expect it to be closer to the average level next quarter). This would mean that sentiment slowly cycles through periods of optimism and pessimism. We can capture these properties with a first-order autoregressive process,  or __MASK_3_25__ process:

$$

\begin{equation*}

s_{t+1}=\phi s_{t}+\eta_{t+1},      \quad \eta_{t+1} \sim \mathcal{N}\left(0,      \sigma_{s}^{2}\right) \tag{3.30}

\end{equation*}

__MASK_2_0__

\begin{equation*}

\mathbb{E}_{t}\left[s_{t+1}\right]=\phi s_{t} \tag{3.31}

\end{equation*}

__MASK_2_1__

\begin{equation*}

\mathbb{E}_{t}\left[r_{t+1}\right]=\theta-(1-\rho \phi) s_{t} \tag{3.32}

\end{equation*}

__MASK_2_2__

\begin{equation*}

s_{t}=v_{t}-\frac{1}{1-\rho}(c+g-\theta) \tag{3.33}

\end{equation*}

__MASK_2_3__

\begin{equation*}

\mathbb{E}_{t}\left[r_{t+1}\right]=\text { const. }-(1-\rho \phi) v_{t} \tag{3.34}

\end{equation*}

$$

where I collected all the constants in the first term. So the log price-dividend ratio,  which we can directly observe,  should capture the time-variation in expected returns induced by __MASK_6_12__. If investors were rational,  under the assumptions we made,  the price-dividend ratio would not vary. So to the extent it varies,  it varies with the __MASK_6_13__ level __MASK_3_4__. This is why the price-dividend ratio predicts returns. Times of high price-dividend ratios,  for example,  are times when a rational investor in this model should expect low future returns.

In practice,  there can be a distortion that can prevent the price-divided ratio from accurately capturing the sentiment level. If rationally expected dividend growth rates are not constant but time-varying,  this would introduce rational reasons for why the pricedividend ratio should vary. If so,  then not all variation in __MASK_3_5__ in our sentiment valuation model (3.28) is due to variation in __MASK_3_6__. Some of the variation would be due to timevarying __MASK_3_7__. Then the price-dividend ratio may be high not because the market is currently overpriced due to positive sentiment,  but rather because because high rationally expected growth of dividends justifies high a current price relative to current dividends. This makes __MASK_3_8__ a less reliable predictor of future returns.

It is also possible that the risk premium that rational investors demand,  and that we have assumed to be constant at __MASK_3_9__ in (3.28),  may in fact be time-varying. Then the price-dividend ratio may be high because investors require a low risk premium. Then future returns will be low because a stock market investment will earn only this low risk premium. So this is just like the sentiment effect that we discussed in the sense that a high current price-dividend ratio forecasts low future returns. So for now we just include time-varying risk aversion as one potential manifestation of sentiment. We can just include the time-varying part of __MASK_3_10__ in __MASK_3_11__.

### 3.5 Macro vs. micro market inefficiency

At this point,  it's useful to reflect a bit on the possibility that sentiment of not-sorational investors could have some impact on the stock market valuation overall. If such sentiment reflects excessive optimism or pessimism about future cash flows and affects prices,  then there is a market inefficiency. In an efficient market,  prices are supposed to reflect a rational assessment of the information available at a point in time,  not sentiment disconnected from fundamentals.

A common argument in modern finance against existence of such market inefficiencies is that "smart money,  " i.e.,  highly sophisticated professional investors,  would take advantage of such market inefficiencies by trading against them and thereby eliminating them. But how strong is this force against market inefficiencies? This depends on the level of aggregation that we are interested in (e.g.,  individual stock level or at an aggregate level,  say the market portfolio) and the nature of the riskiness of the assets involved.

Consider first individual stocks. Suppose there are lots of idiosyncratic mispricings. Idiosyncratic here means that whether a stock is overor undervalued is totally random and not systematically related to,  say,  firms' industry,  their size,  or other common attributes that firms may have. In this case,  a hedge fund can run a "pairs trading" strategy,  taking long positions in undervalued stocks and pairing each long position with a short position in an overvalued stock that has highly correlated returns because it's in the same industry,  has the same size,  etc. The high correlation ensures that the pair long-short position has relatively little risk because the short position to a large extent hedges the risk of the long position. Moreover,  putting lots of such pairs together into a portfolio results in a lot of the remaining risk being diversified away. As a consequence,  very little risk is left in this portfolio. Hence,  if these kinds of market inefficiencies existed,  it would be an extremely attractive opportunity that hedge funds or other smart-money investors would aggressively exploit and thereby largely eliminate. For exactly that reason,  these sorts of inefficiencies are unlikely to be big.

Now consider the stock market as a whole. Suppose,  for instance,  that the stock market portfolio as a whole is overvalued by $50/% and smart-money investors know about this overvaluation (without any uncertainty about the degree of misvaluation). Unfortunately for them,  there is no way to construct a low-risk,  high-return trade that exploits this misvaluation. Unlike in the pairs trading example,  there is no other asset class out there that has a return that is highly correlated with the stock market. In other words,  one cannot really hedge the risk of a short position in the overvalued stock market with a long position in some other asset class. As a consequence,  taking a bet agains stock market overor undervaluation is necessarily risky. Recall that a typical

one-standard deviation move in the stock market in a single year is a __MASK_3_0__20/% or more relative to a broad stock index. For an investor who responded to overvaluation by taking short position in the stock market,  the performance shortfall in this case would be even bigger.

Moreover,  even if smart-money investors are correct in their judgment that the stock market is misvalued,  it could take years until the misvaluation is corrected. And since betting against the entire stock market is very risky,  substantial losses can pile up until the position finally pays off. This means smart-money investors may have to write many quarterly letters to their outside investors pleading with them to be patient and arguing that their position will win in the long run. Yet,  outside investors are rarely patient enough to see this through. As the economist John Maynard Keynes,  who,  was also an active speculator in markets,  once remarked: "Markets can stay irrational longer than you can stay solvent."

One well-known example is the famous value investor Julian Robertson of Tiger Management during the technology stock bubble during the late 1990s. Tech stock prices were going through the roof in 1999,  before crashing sharply in March 2000. In mid-1999,  tech stocks seemed extremely overvalued. Julian Robertson decided to exit long positions in tech stocks and to bet against further price rises of tech stocks. Unfortunately for him,  prices kept rising at a fast pace. His funds started to suffer outflows. In October 1999,  Tiger Management increased the redemption period for investors from 3 to 6 months in to curb outflows. But nevertheless,  in the last quarter of 1999,  their funds lost about $25/% of its assets through withdrawals. In March 2000,  Robertson threw in the towel and announced the liquidation of his funds,  just a few days before the start of the technology stock crash.

Figure 3.5 shows the monthly flows of the Jaguar fund,  one of the funds managed by Tiger Management,  and compares with the the flows of the Quantum fund,  managed by George Soros. Soros took a very different approach. He tried to "ride the bubble" until the end,  with long positions in tech stocks until March 2000. At the start of the crash,  he quickly reduced these positions. His performance in late 1999 and early 2000 therefore was much better than Julian Robertson's. As the figure shows,  this made a dramatic difference to the timing of flows. The Jaguar fund had strong outflows in the second half of 1999 before being closed down in the first quarter of 2000. The Quantum fund also suffered outflows once its long positions got hit by the crash in March 2000. But due to the prior inflows as well as the large gains it had achieved on its long positions,  the Quantum fund was able to weather those outflows. After the Quantum fund exited tech stock positions quickly in the wake of the crash,  outflows stopped a couple of months

 !__MASK_4_3__

Figure 3.5: Fund flows of Jaguar fund and Quantum fund

Source: Brunnermeier,  M. and Nagel,  S.,  2004. Hedge funds and the technology bubble. Journal of Finance,  59(5),  pp0.\1-2040. The peak of technology stock prices was in mid-March 2000.

later.

The bottom line of all this is that betting against misvaluation of the entire market,  or large sectors of the market,  is very risky. And it's not even clear that betting early on against misvaluation is necessarily the best strategy for a smart-money investor. Temporarily riding a bubble of inflating misvaluation of the stock market,  like George Soros seems to have done,  may be preferable. In the short run,  therefore,  smart money investors may even further amplify misvaluation.

Overall,  it's quite implausible that smart money would lean aggressively against misvaluation at the aggregate stock market level.

Another argument that is often made is that professional investors manage most of the money invested in the stock market and so it must be professionals,  not the likely less sophisticated individual investors that effectively determine pricing in the stock market. However,  according to the U.S. Financial Accounts,  at the end of 2021,  individual investors held about __MASK_3_1__25/% indirectly through mutual funds,  ETFs,  and direct-contribution retirement products. This means that a substantial share of equity investments is directly or indirectly controlled by individual investors. The investment products that individual investors purchase in the mutual funds and ETF space are often quite narrowly defined (e.g.,  a stock fund,  a bond fund,  or a stock fund focused on a specific sector,  etc.). By

allocating money to these products,  it is the individual investors who are effectively making the allocation decision at the asset-class level,  not the professional managers running these funds. Professionals,  or the computer algorithms they use,  then decide on how the allocated flows are invested in individual securities within the asset class,  but the asset-class level allocation decision is left to individuals.

In contrast,  at the individual stock level,  most of the funds products that individual investors hold leave it to professional investment managers to choose the individual securities within asset class buckets. So we should expect individual investors to have much less influence on the relative pricing of individual securities within asset classes.

In summary,  at the macro level,  for asset classes,  investment flows are more likely to be driven by sentiment-prone retail investors than at the individual security level. These asset-class level flows are also more difficult to counteract for smart money investors because doing so is risky. The conclusion from all this is that we should not expect that smart money investors exert a strong influence to keep markets efficient at the macro level. Markets are likely to be quite efficient at the micro level,  but inefficiencies are more likely at the macro level.

Our next step will be to look into getting estimates of the returns we can expect from a stock market in the presence of misvaluation. We do this first by looking at simulations of the model from above,  then we'll look at actual data.

### 3.6 Return prediction regressions: Simulations

Recall from earlier that our valuation model with sentiment had the following equation for the __MASK_3_2__ price-dividend ratio:

__MASK_2_0__

The fundamental value component of the log price-dividend price ratio is obtained as __MASK_3_5__. We then get the level of the fundamental value,  __MASK_3_6__,  by adding the log dividend and then exponentiating

__MASK_2_0__

The price level is

__MASK_2_1__

I simulate unexpected changes log dividends as a normal random variables,

__MASK_2_2__

and the level of sentiment as in (3.30),

__MASK_2_3__

i.e.,  also with normally distributed shocks. Based on the simulated __MASK_3_7__ and __MASK_3_8__ series,  I then calculate series of first __MASK_3_9__,  and then __MASK_3_10__ and __MASK_3_11__ using the above formulas. Finally,  I get a series of realized log returns by solving (3.18) for __MASK_3_12__,  which yields

__MASK_2_4__

Plugging the simulated __MASK_3_13__ series into this formula then yields the simulated log returns series.

I pick parameters that make the series have properties close to the actual stock market index return and price-dividend ratio series at a quarterly frequency: __MASK_3_14__ (the parameter in the log-linearization that is very close to one),  __MASK_3_15__ (expected log dividend growth); __MASK_3_16__ (unconditional expected log return). I set the volatility of dividend shocks to __MASK_3_17__.

A key question we should look into is how the persistence of sentiment affects the nature of mispricing and the return predictability that follows from it. For this reason,  I will show results for several different values of __MASK_3_18__ in (3.39). For each value of __MASK_3_19__,  I look for a value of the sentiment shocks __MASK_3_20__ that makes the standard deviation of __MASK_3_21__ equal to 0.20 . In other words,  I want to see the effects of changing persistence of sentiment without changing the typical magnitudes of sentiment-induced misvaluation.

Figure 3.6 shows simulated price paths of __MASK_3_22__ and __MASK_3_23__ for total length of 400 quarters and for two different values of __MASK_3_24__ in the top panel and __MASK_3_25__ in the bottom panel. In both cases,  there is a substantial degree of misvaluation due to the time-varying __MASK_6_36__,  often exceeding __MASK_3_26__-30/% of the fundamental value. But which value of __MASK_3_27__ we pick makes a big difference for how fast misvaluation corrects. In the top panel,  if __MASK_6_37__ is not very persistent,  mispricing corrects very quickly and so we get relatively high-frequency variation of the price around fundamental value. In contrast,  with __MASK_3_28__ in the bottom panel,  __MASK_6_38__ is highly persistent and we get long-lasting cycles of misvaluation.

Which of the two cases would make it easier for a smart investor to profit from misvaluation? Clearly the first case. In this case,  if the investor recognizes at a certain point in time that there is big misvaluation,  then,  because sentiment has low persistence,  it's very likely that this misvaluation will correct soon. A bet against misvaluation is therefore likely to pay off soon. In contrast,  in the high-persistence case in the bottom panel,  an investor could correctly diagnose that there is,  say,  undervaluation (such as around quarter 245 in the plot) but then it can take another 5 to 10 years until the

 !__MASK_4_35__

Figure 3.6: Simulated paths of prices and fundamental value for different values of __MASK_3_29__

misvaluation finally gets corrected and the bet against the mispricing eventually pays off.

We can see this more clearly if we look at the scatter plots of log returns in period __MASK_3_30__,  i.e.,  __MASK_3_31__,  on __MASK_3_32__ sentiment in the previous period,  __MASK_3_33__,  shown in Figure 3.7 for these two 400-quarter simulation runs. These scatter plots show us how informative __MASK_3_34__ is about the return in the next quarter.

As the top panel shows,  with low persistence,  there is a clearly visible negative relationship between sentiment and next-quarter returns: high sentiment strongly forecasts low future returns. This reflects the relatively quick correction of mispricing in the low-persistence case.

In contrast,  the bottom panel shows that when persistence is high,  there is at best a very weak relation between sentiment and next-quarter returns. So,  even if we perfectly know the level of mispricing at __MASK_3_1__,  it's still very difficult to predict what returns will be next quarter! And remember that typical magnitudes of mispricing in the simulations in both panels are the same. The only difference is that mispricing in the top panel is meanreverting quickly,  while it can be very long-lasting in the bottom panel. Long-lasting mispricing is difficult to exploit,  even if it's big!

Let's explore this more through the lens of a statistical model that an investor could then use to get estimates of conditional expected returns (which the investor could then fit into a portfolio optimization model). Let's run a regression of log returns on lagged log sentiment:

__MASK_2_0__

Basically,  we are fitting a straight line with slope __MASK_3_2__ and intercept __MASK_3_3__ through the scatter plots we just looked at. Once we have an estimate of the regression coefficients __MASK_3_4__-let's label them __MASK_3_5__-we can form an estimate of the conditional expected next-quarter log return as __MASK_3_6__.

Table 3.1: Predictive regressions of one-quarter-ahead log returns on the log sentiment level __MASK_3_7__
!__MASK_4_31__

To see what such a regression delivers on average (or said differently,  in expectation),  I now generate 1,  000 simulated series of returns and sentiment,  each with length 400 quarters. I run the regression above on each of these simulated 400-quarter series. So for each simulated series,  I get one set of estimates __MASK_3_8__. Table 3.1 shows average __MASK_3_9__ across

 !__MASK_4_32__

Figure 3.7: One period ahead __MASK_3_10__ returns,  __MASK_3_11__ and __MASK_3_12__ sentiment,  __MASK_3_13__

 !__MASK_4_33__

Figure 3.8: Distribution of estimated slope coefficient in return-prediction regression (each simulation run has 400 quarters of data)

the 1,  000 simulations. I also calculate the average __MASK_3_14__,  which shows how much of the variance of __MASK_3_15__ is explained by the predictable component __MASK_3_16__.

In line with the intuition from the scatter plots. When __MASK_3_17__ is low,  there is a strong negative relationship between __MASK_3_18__ and __MASK_3_19__ as shown by the large negative average slope coefficient of -0.85 and the high __MASK_3_20__ of __MASK_3_21__R^{2}__MASK_3_22__\phi=0.15$ where we can see the negative relationship just by eyeballing the scatter plot.

In contrast,  when __MASK_3_23__,  the average slope coefficient is much,  much smaller __MASK_3_24__ and the __MASK_3_25__ is much lower __MASK_3_26__. Again,  this lines up well with what we concluded from the scatter plot: if there is any predictive relationship,  it must be weak,  because we can't really see it in the scatter plot.

In this high persistence case,  __MASK_3_27__,  how difficult is it,  statistically,  to pin down the slope coefficient? We can get an idea by looking at the different estimates __MASK_3_28__ we get across the 1,  000 simulation runs. Figure 3.8 presents a histogram. The variation in __MASK_3_29__ across the different simulation runs is substantial! It is not all that unlikely that an estimates ends up quite close to zero-which looks like returns are only very weakly predictable,  even though the magnitudes of mispricing are substantial.

Moreover,  we get this result that the slope __MASK_3_30__ is difficult to estimate precisely even though we are looking at really long samples here in these simulation runs. In practice,  the sample length of 400 quarters we are using here would be unusually long. And it's not only 400 quarters long here,  but we also know for sure that the underlying process of sentiment and dividend growth,  and their parameters,  are not changing over time. In practice,  using a 400-quarter sample of data to estimate these sorts of predictive relationship runs into questions whether the predictive relationship we are trying to uncover could really be stable over such a long period of time. So,  in practice we would be even less certain about the predictive relationship between measures of misvaluation and future return.

All this shows how exceedingly difficult market timing can be,  even if the stock market goes through cycles of large misvaluations that we can perfectly measure!

And we haven't even gotten to the main difficulty,  which is that a real-world investor must predict out-of-sample. Here we have only examined in-sample regressions. For example,  an investor living in our simulations and trying to make an investment decision at,  say,  quarter 200 does not yet have the benefit of knowing the coefficient estimates of a regression run with data all the way until quarter 400. The investor would only be able to use data up to quarter 200 to inform themselves about the predictive relationship. But before we get to this problem of out-of-sample prediction,  let's first look at actual data on returns and price-dividend ratios to see whether any of the cases for different __MASK_3_2__ that we considered so far could be a good approximation to reality.

### 3.7 Predictive regressions in actual data

Table 4.2,  Panel A,  shows the results from a regression of log returns on the lagged log price-dividend ratio __MASK_3_3__,  i.e.,  the regression

__MASK_2_0__

The dependent variable are quarterly log returns on the CRSP value-weighted index from 1927Q2 to 2022Q4; the predictor variable is the __MASK_3_4__ ratio of this index from end of quarter 1927Q1 to end of quarter 2022Q3. Each quarter __MASK_3_5__,  I compute the P/D ratio as the total aggregate market capitalization of all stocks in the index dividend by the sum of dividends of all stocks in the index during the quarters __MASK_3_6__ to __MASK_3_7__.

As Panel A shows,  the results are quite weak. The sign of the coefficient is as expected from our simulations earlier. A high price-dividend ratio forecasts low future returns. However,  the __MASK_3_8__-statistic of the slope coefficient of -1.776 does not exceed conventional

Table 3.2: Predictive regressions of one-quarter-ahead returns on the lagged log pricedividend ratio,  1927-2022

!__MASK_4_22__

thresholds for statistical significance at a __MASK_3_9__R^{2}__MASK_3_10__0.6/% tells us that the __MASK_3_11__ ratio explains very little of the variation of future returns.

While the present-value identity framework based on log-linear approximation that we used in this lecture relates the __MASK_3_12__ ratio to future __MASK_3_13__ returns and future __MASK_3_14__ dividend growth,  for the purpose of choosing an __MASK_6_24__ we are actually not really interested directly in expected log returns. Instead,  we want to know expected simple returns. Yet,  a regression with log returns as dependent variable gives us forecasts of log returns,  not forecasts of simple returns. To illustrate what difference this makes,  recall from (3.10) that if returns are conditionally log normal,  the conditional expected simple return return relates to the conditional expected log return as follows:

__MASK_2_1__

If __MASK_3_15__ was constant,  then the difference between conditional expected simple and log returns would be roughly constant most of the difference would be absorbed by the intercept term __MASK_3_16__ in the regression without affecting the slope coefficient __MASK_3_17__. However,  in reality volatility is time-varying and it may also vary with __MASK_3_18__,  which means it can affect the slope coefficient. So,  to get usable inputs for __MASK_6_25__ optimization,  it makes sense for us to use simple,  not log returns as the dependent variable in the regression.

Panel B of Table 4.2 shows the result: The slope coefficient is much bigger than in Panel A,  the __MASK_3_19__-statistic is now -2.428 ,  which is statistically significantly different from zero at a __MASK_3_20__R^{2}__MASK_3_21__1.3/%.

 !__MASK_4_23__

Figure 3.9: Conventional and repurchase-adjusted log price-dividend ratio

Finally,  we may want to separate variation in returns that comes from variation over time in the risk-free rate from variation that comes from variation in the conditional equity premium that can be earned by an investor. For this reason,  Panel C puts the quarterly simple stock index return in excess of the return on a U.S. Treasury Bill investment (one-month T-bill,  rolled over within quarters to get a quarterly return) as the dependent variable of the regression. As it turns out,  this does not make much difference compared with Panel B.

Now,  in this regression we have used data that covers time periods stretching over almost 100 years. Lots of things have changed in the world and in the U.S. economy over this long period. Should we be worried that these relationships between returns and __MASK_3_0__ could be unstable?

This is a valid concern and we won't be able in this course to thoroughly investigate this question. But I want to highlight one such source of instability - and offer a way to fix the problem.

To see the problem,  examine Figure 3.9. The red line shows the __MASK_3_1__ ratio we have been using so far. To calculate it,  I accumulate cash dividends of all stocks in the index over moving 12-month windows and divide by the aggregate market value of all

stocks at the end of this window (and then take the log). It's striking that from around 1995 onwards,  the level of the __MASK_3_2__ ratio has been almost always substantially higher than in any period before 1995. It looks as if something had shifted up the log P/D permanently to a higher level.

The reason for this shift is that in the 1980s and 1990s,  many firms switched from paying out dividends to (at least partly) returning cash to shareholders in the form of share repurchases. Repurchases of shares are in some ways equivalent to dividends: cash leaves the company's account and arrives in shareholders' pockets. But repurchases and dividends differ in who gets the payment. With dividends,  every shareholder gets a payment. With repurchases,  the shareholders who sell their shares back to the company get cash.

In the present-value identity model that we worked with in this lecture,  repurchases did not show up explicitly. But since "price" represents the aggregate value of the stock market and "dividends" represent the cash flows that go back to all shareholders in aggregate,  we should really include repurchases in the denominator of the price-dividend ratio.

The blue line in Figure 3.9 adds repurchases to dividends when computing the log price-dividend ratio. As the figure shows,  this completely eliminates the unusual level shift in the __MASK_3_3__ ratio.

Table 3.3: Predictive regressions of one-quarter-ahead returns on the lagged repurchaseadjusted __MASK_3_4__ price-dividend ratio,  1927-2022
!__MASK_4_21__

Table 3.3 shows that the repurchase-adjustment also improves the ability of the log price-dividend ratio to predict returns: In all three panels for the different types of returns,  the __MASK_3_5__-statistics are of greater magnitude and the __MASK_3_6__ are higher than in Table 4.2 .

Interestingly,  the results in Table 3.3,  and,  specifically,  the estimates of the regression slope coefficient and __MASK_3_7__,  are quite close to what we obtained in the simulations in Table 3.1 in the case __MASK_3_8__. (In these simulations,  __MASK_3_9__ and __MASK_3_10__ are equal up to a constant,  so the slope coefficient and __MASK_3_11__ would be the same if we had run the regressions in the simulated data on __MASK_3_12__ instead of __MASK_3_13__.) Recall that for this value of __MASK_3_14__,  sentimentinduced misvaluation was very large and persistent. So our empirical finding of seemingly small __MASK_3_15__ of around $2/% can be consistent with large,  highly persistent sentiment-driven time-varying misvaluation of the aggregate stock market.

But this also means,  as in our simulations,  that the return predictability is likely difficult to exploit in an investment strategy. For example,  as in our simulations,  the uncertainty about the magnitude of the slope coefficient is substantial. For example,  in Panel C the __MASK_3_16__-statistic for the estimate of __MASK_3_17__ is around -3 ,  and one standard error is a little less than 0.02. This means that it's quite likely (again using a Bayesian interpretation of statistical estimates) that the true coefficient could be substantially smaller or bigger than the estimate shown in Panel C. So our prediction of returns based on these estimates in Panel C is quite likely to be wrong in a substantial way. And that the __MASK_3_18__ is only around $2/% tells us that most of the future returns will be unpredictable,  even if we happened to stumble on the true slope coefficient in our estimates.

### 3.8 Other valuation measures

Investment practitioners frequently use a number of alternative measures along with the __MASK_3_19__ ratio. The common idea underlying all of these measures,  including the __MASK_3_20__ ratio,  is to compare the aggregate stock price level with a variable that should,  at least roughly,  be proportional to the fundamental value of the fundamental value of stocks,  so that the ratio is informative about the degree of sentiment-induced misvaluation.

### 3.8.1 Cyclically adjusted price-earnings ratio

Economics Nobel laureate Robert Shiller at Yale created the cyclically-adjusted priceearnings ratio (CAPE). __MASK_3_2__ It uses aggregate earnings of firms instead of their dividends. The hope is that earnings may be a better proxy for fundamental value than dividends,  which may be distorted as a measure of fundamental value by certain quirks in firms' payout policy,  such as their tendency to smooth dividends over time,  or firms' substitu-

[^9] !__MASK_4_18__

Figure 3.10: Repurchase-adjusted log price-dividend ratio and log price-earnings ratio

tion of stock repurchases for dividends in recent decades (which we tried to address by repurchase-adjusting dividends in our analysis above).

However,  just using current-year earnings as the denominator in a price-earnings ratio does not always work well because annual earnings are notoriously volatile. In particular,  when a recession hits and earnings fall,  firms often like to take big "earnings baths" by taking all sorts of asset write downs. Firms tend to prefer to take such a big earnings bath once in a while rather than having more frequent moderately low earnings. The consequence of this is that annual aggregate earnings fall much more in recessions than the fundamental value of stocks. They often fall so much that the price/earnings ratio with current-year earnings goes __MASK_3_3__ when the economy hits a recession,  even though stock prices fall substantially.

As Figure 3.10 shows,  this happened during the Great Recession in 2008/09 and,  to a lesser extent in the recession in 2001. The figure also shows the repurchase-adjusted __MASK_3_4__ ratio for comparison. Earnings fell so much that the log price-to-earnings ratio actually went up very sharply in 2008/09,  despite the huge drop in stock prices that took place back then! This very different from how the __MASK_3_5__ ratio behaved. This upward spike completely destroyed the ability of the __MASK_3_6__ ratio to serve as a __MASK_6_20__ valuation measure around this time.

 !__MASK_4_19__

Figure 3.11: Repurchase-adjusted log price-dividend ratio and log of cyclically adjusted price-earnings ratio

Shiller noticed that using a ten-year moving average of earnings instead of annual earnings gets around this problem. Because this average of earnings over the past ten years smoothes out business cycle fluctuations in earnings,  the price/earnings ratio with this ten-year moving average in the denominator is called the cyclically-adjusted price/earnings ratio.

Moreover,  Shiller's calculation uses real (i.e.,  inflation-adjusted) earnings and prices in this calculation. He divides the real stock price by the ten-year moving average of real earnings. This is an important detail especially in times when inflation is high. If the calculation was instead done with nominal earnings and prices,  then high inflation would distort the valuation ratio. When inflation is high,  comparing current nominal stock price levels to nominal earnings from several years ago would compare apples and oranges because nominal earnings a few years ago are expressed in units of dollars that had much higher purchasing power than current dollars. Nominal earnings from a few years ago would therefore not be a good measure of future nominal earnings potential.

Figure 3.11 show the time-series of the log of CAPE in comparison with the repurchaseadjusted __MASK_3_7__ ratio. The two series are quite highly correlated.

### 3.8.2 Fed model

Another popular gauge of the stock market's valuation level is the so-called Fed modelwhich,  despite the name,  has almost nothing to do with the Federal Reserve. __MASK_3_8__ Recall the equation for the __MASK_3_9__ ratio in the Gordon growth model (3.13):

__MASK_2_0__

The idea behind the Fed model is that the discount rate on stocks is a long-term bond yield __MASK_3_10__ plus a fixed risk premium __MASK_3_11__,  i.e.,  __MASK_3_12__. Substituting this into the equation above and solving for __MASK_3_13__,  we get

__MASK_2_1__

Then,  the reasoning goes,  with the growth rate __MASK_3_14__ fixed,  whether stocks are attractive in terms of the risk premium __MASK_3_15__ that one can expect to earn depends on the relative magnitudes of the dividend-price ratio (calculated with "forward" dividends __MASK_3_16__ ) and the bond yield. If stocks are too "expensive" with low dividend-price ratio compared with the nominal yield __MASK_3_17__ offered by bonds,  then bonds are a better investment in expectation.

By the same logic,  higher bond yields should be bad for stocks in equilibrium in the sense that to keep earning the same risk premium __MASK_3_3__,  the dividend-price ratio must rise (via a fall in stock prices) when __MASK_3_4__ rises. Conversely,  lower bond yields would justify higher stock prices relative to dividends.

There is a likely flaw in this argument though. The flaw is in thinking of __MASK_3_5__ as fixed while we consider variation in __MASK_3_6__. In the past decades,  especially in the 1970s and 1980s,  and again very recently,  a lot of time-variation in nominal long-term bond yields is driven by inflation. We will look at this in much more detail when we discuss bonds and interest rates,  but,  broadly,  investors require higher nominal yields when inflation is higher. And if inflation is higher,  it's also likely that corporate earnings rise with inflation,  at least in the long run. After all,  inflation is nothing else than firms charging higher prices for the goods and services they provide. If so,  __MASK_3_7__ should rise with expected inflation. It's not clear that it should rise one-for-one with expected inflation,  but for simplicity suppose that dividend growth and bond yields rise one-for-one with inflation

__MASK_2_0__

[^10] !__MASK_4_21__

Figure 3.12: Fed model: Repurchase-adjusted log price-dividend ratio minus 10-year yield

where __MASK_3_8__ is the inflation rate,  __MASK_3_9__ is the real growth rate,  and __MASK_3_10__ is the real bond yield. Plugging this into (3.43),  we get

__MASK_2_1__

This suggests that one should compare the forward __MASK_3_11__ ratio with the real bond yield __MASK_3_12__ to assess the magnitude of the risk premium __MASK_3_13__ priced into the stock market,  not the nominal bond yield __MASK_3_14__. Basically,  if stocks' payouts grow with inflation,  this means that stocks are a real asset,  and so their dividend yield should be compared with real yields.

### 3.9 Out-of-sample prediction

The predictive regressions we looked at so far are not regressions that an actual investor could have run before they made investment decisions. We used decades of data all the way until the end of 2022. But an investor making decisions in,  say,  1990 would not have had access to the data after 1990. So perhaps the return predictability that we see

in the full sample regression now with data all the way until 2022 was not apparent to the same extent to an investor in 1990?

For this reason,  we now look at out-of-sample (OOS) regressions. Strictly speaking,  the regressions won't be truly out of sample. To run a true OOS test,  we would have to wait a few years to collect entirely new,  truly out-of-sample data. Instead,  we will look at pseudo-OOS tests where we recreate regressions that investors in the past could have run,  based on the data that was available at the time. As we proceed through time,  and more data becomes available,  the regressions use more observations. But to avoid clutter,  I'll still refer to these sorts of tests simply as OOS tests.

In more detail,  I fix an initial burn-in period of 40 quarters as minimum data requirement before one can run a regression. This means that I run the first regression of excess returns on the lagged repurchased-adjusted price-dividend ratio with 40 quarters of data up until the end of 1937Q1. I record the estimated coefficients and compute predicted excess returns for quarter 1937Q2. I then use this predicted excess return as portfolio weight __MASK_3_15__ for the stock market index.

Investing weight __MASK_3_16__ in the stock market and the rest in the risk-free asset means that this market-timing strategy then has a realized excess return (i.e.,  in excess of the risk-free return) in quarter 1937Q2 of

__MASK_2_2__

Then I move forward one quarter and use all data until the end of quarter 1937Q2 to estimate the regression and calculate a portfolio return in quarter 1937Q3,  and so on,  until the end of 2021 .

If it happens to be the case that stock market excess returns are predictable out-ofsample,  then it should be somewhat likely that __MASK_3_17__ will be high in times when the portfolio weight __MASK_3_18__ is high,  and that __MASK_3_19__ low when __MASK_3_20__ is low. In this case,  the market-timing strategy will be successful and should earn a higher Sharpe ratio than the Sharpe ratio an investor would have earned from holding a constant portfolio share invested in the stock market.

The blue line in Figure 3.13 shows the time-series of predicted excess return __MASK_3_0__ that comes out of this exercise. When it's positive,  the pseudo-OOS trading strategy takes a long position in the stock market index,  when it's negative,  it takes a short position.

For comparison,  the red line in the figure shows the predicted excess return if one restricts the regression to have just an intercept. In this case,  there is no predictor variable and the predicted excess return at time __MASK_3_1__ is just he historical mean excess return in the data up to time __MASK_3_2__. I label this the "trailing mean." This trailing mean

 !__MASK_4_3__

Figure 3.13: Predicted excess returns from recursively expanding window estimation

forecast will be a useful benchmark for evaluating how much OOS-useful information about future excess returns there is in the price-dividend ratio.

To evaluate the realized return of the market timing strategy in (3.46),  I first standardize these returns by dividing them by the full sample standard deviation (which turns the average of these realized returns into a "realized Sharpe ratio" because the are then a ratio of mean excess return to standard deviation). I then cumulate these standardized returns over time (by simply adding up). The blue line in Figure (3.14) shows the result. Strategies with higher Sharpe ratios will end up at a higher point at the end of the sample period at the right-hand side of the plot.

To interpret this cumulative standardized return,  we need a benchmark for comparison. I use the trading strategy that uses the trailing mean instead of the price-dividend ratio regression prediction as the portfolio weight. Returns are again standardized and cumulated. The solid black line shows the result. The result is striking (and disappointing for anyone hoping to find an easy way to time the stock market using the price-dividend ratio): By 2022,  the strategy using the trailing mean as forecast is just as good in terms of its cumulative performance as the strategy that used information from the price-dividend ratio in a predictive regression. Thus,  despite the forecasting power that the price-dividend ratio seems to have in in-sample regressions run over the full

 !__MASK_4_4__

Figure 3.14: Cumulative standardized excess returns of different out-of-sample portfolio strategies

sample from 1927 to 2022,  it does not seem to have been of much use for investors who had to make out-of-sample forecasts based only on data that was observable to them.

Another interesting benchmark is a strategy that keeps a constant weight in stocks without any time-variation in this weight. Returns are again standardized and cumulated. The black dotted line shows the result. In this case,  the cumulated returns at the end in 2022 are even a little higher than the cumulated return of the predictive regression strategy that uses the price-dividend ratio.

But perhaps the way we have constructed the excess return forecasts in this pseudoOOS forecasting exercise did not use the information in the price-dividend ratio to its full extent. Recall what we discussed in earlier lectures about estimation error and shrinkage. The estimates of the coefficients of the predictive regression come with substantial statistical uncertainty. They could be quite far from their true values due to estimation error. At the same time,  we know that excess return predictability cannot be huge,  otherwise market timing would be too easy. It can't be easy in a world where smart investors are hunting for opportunities to earn profits. These two circumstances together mean that a good forecast should not really use the regression coefficient estimates directly to construct excess return forecasts,  but first shrink them towards zero.

 !__MASK_4_5__

Figure 3.15: Distribution of the difference in cumulative standardized excess returns of predictive regression minus trailing mean strategy in sentiment model simulations

I won't try to figure out the optimal degree of shrinkage here. Instead,  I'll try something very simple. I take the predictive regression coefficient estimates every period and I shrink them halfway towards the trailing mean. Put differently,  my forecast now is a weighted average of the predictive regression forecast and the trailing mean with weight $50/%. The red line shows the result. This simple shrinkage strategy does better than all the others!

Even so,  it's quite clear that OOS forecasting of excess returns on a stock market investment is not easy. Some observers conclude from this that the market must be macro efficient,  i.e.,  that there is little mispricing at the aggregate stock market level. While this could be true,  it does not follow necessarily from the fact that returns are hard to forecast OOS. Stock market excess returns would also be difficult to forecast in a world in which there is substantial mispricing,  with large deviations in stock prices from their fundamental values at the aggregate market level,  if this mispricing is very persistent. If mispricing is not followed by quick price corrections,  the mispricing does not represent a great investment opportunity even for the smartest investors.

Figure 3.15 illustrates this based on simulated data from the sentiment model that we looked at earlier. Each simulation run produces returns and price-dividend ratio samples

of similar length as the ones I used in Figure 3.14. I then run the pseudo-OOS forecasting exercise from Figure 3.14 on the simulated data and I record the differences between the cumulated standardized excess returns of the predictive regression strategy and a trailing mean strategy. The histogram of these differences shows that the predictive regression wins on average,  but there is a huge amount of variation around it. About a third of the time,  the trailing mean forecast wins! And this is in a simulated model where we know for sure that there is big time-varying mispricing in the stock market.

That returns are not easily forecastable prevents smart investors from aggressively trading against and thereby eliminating the mispricing. So the difficulty of OOS forecasting even if mispricing is big may be an important part of the story why big deviations of aggregate market values from fundamentals are possible in the first place. There is little reason to think that the value of stocks in aggregate should be close to fundamental values if deviations don't represent much of a profit opportunity.

### 3.10 The trouble with market timing

Given the earlier evidence from in-sample predictive regressions that the price-dividend ratio predicts returns,  why is it so difficult to construct a market-timing strategy that outperforms?

To understand this better,  a first point to note is that our evaluation of performance in Figure 3.14 was based on cumulated standardized excess returns. Standardizing excess returns by their standard deviation over the full sample means we effectively compared the alternative strategies in terms of their Sharpe ratios. So we'll focus here on understanding why market-timing attempts can produce a poor Sharpe ratio even if the portfolio weights are based on a return-prediction model that actually produces a somewhat informative signal about expected excess returns.

The root of the problem is that the signal we are getting from a predictive regression is not a perfect signal of expected returns. It is distorted by noise because the predictive regression coefficients we use to construct the predicted returns and then the portfolio weight are subject to estimation error. To examine the consequences of such noise in portfolio weights,  let's consider the extreme case where expected returns are actually constant and the investor's timing strategy is based purely on noise. Is timing based on noise worse,  in terms of Sharpe ratio,  than just being fully invested with $100/% weight in the stock market at all times?

Let __MASK_3_4__ for simplicity. Stock market returns are generated as

__MASK_2_0__

so that market timing is not possible. A strategy with constant weight __MASK_3_5__ would earn expected return and variance

__MASK_2_1__

But let's say an investor tries to time the market nevertheless. The investor builds a market-timing strategy based on a signal that is a constant plus pure noise. More precisely,  the investor sets the portfolio weight equal to the unconditional expected return __MASK_3_6__ plus noise:

__MASK_2_2__

where __MASK_3_7__ is uncorrelated with __MASK_3_8__ (so this is noise that does not predict returns). While the timing based on pure noise clearly can't boost performance,  one might hope that it at least does not hurt. But this hope would be misguided. The expected return is not hurt as

__MASK_2_3__

is the same as the expected return of a constant-weight strategy with weight equal to __MASK_3_2__. But the attempt to time the market produces a bigger variance

__MASK_2_0__

So relative to the constant-weight strategy variance in (3.48),  there is the additional __MASK_3_3__ term here. And this term is bigger the bigger the noise variance __MASK_3_4__. Timing based on noise induces additional variance,  from two sources:

__MASK_3_5__ : By sometimes taking a high exposure,  sometimes a low exposure to stocks,  the timing strategy generates time-varying expected returns,  which then shows up as one source of higher variance of realized returns. (If __MASK_3_6__ was zero,  the expected return would always stay zero,  and this component of variance would not exist.)

__MASK_3_7__ : This one is a bit more subtle,  but quantitatively much more important. Noise makes the strategy risky in some time periods,  with high return variance when __MASK_3_8__ is high in absolute value and sometimes low return variance when __MASK_3_9__ is low. But averaged across time periods,  this variance averages to a higher value than the variance of a constant weight strategy because the variance depends on the squared portfolio weight. To see this,  take a simplified case with a binary noisy signal: suppose the portfolio weight is equal to 0.5 half the time and equal to 1.5 in the remaining time periods and hence 1.0 on average. So then the conditional variance of the resulting investment strategy return based on this signal is __MASK_3_10__ half the time and __MASK_3_11__ in the remaining periods. The

average conditional variance then is __MASK_3_12__,  which is bigger than the return variance of a strategy that invests with a constant portfolio weight of 1.0! So mean-zero noise in portfolio weights raises the average conditional variance,  because the portfolio variance depends on the squared portfolio weight,  which means it is convex in the portfolio weight. So having portfolio weights vary over time for no good reason hurts the Sharpe ratio!

### 3.11 Volatility timing

The general idea underlying market timing strategies is that we would like to increase exposure to the stock market when the reward-to-risk ratio is high and keep the exposure lower when the reward-to-risk ratio is low. This should then boost the Sharpe ratio of the long-run return of the strategy. Recall the optimal __MASK_6_17__ formula for the single risky asset case (3.1),  now written with conditional moments:

__MASK_2_1__

So far we have focused on the numerator,  trying to identity variation in __MASK_3_13__ in the data. But we can also improve our __MASK_6_18__ if we focus on the denominator and identify variation in __MASK_3_14__ in the data. To identify periods when the reward for taking risk in the stock market is high,  we can look for periods in which expected returns are higher than average,  or periods in which volatility is lower than average (or a combination of both). We now focus on predicting volatility.

To generate a time-series of volatility,  I take a series of daily returns on the CRSP value-weighted stock market index. Each quarter I calculate the standard deviation of daily returns and I annualize (multiply by __MASK_3_15__ ). Figure 3.16 displays the time-series of these annualized quarterly standard deviations of daily returns.

As the figure shows,  there is a lot of variation over time in the level of volatility. Tranquil periods like the early 1990s or the years prior to the financial crisis in 2008/09 have volatility below __MASK_3_16__40/% annualized.

The first thing we should check is whether our earlier market-timing strategy based on the __MASK_3_0__ ratio,  which tried to exploit variation in __MASK_3_1__,  inadvertently also timed volatility,  and perhaps in the wrong direction. We can check this by regressing

 !__MASK_4_25__

Figure 3.16: Annualized quarterly standard deviations of daily stock market index returns

the quarterly volatility observations on the repurchase-adjusted __MASK_3_2__ ratio at the end of the previous quarter. Table 3.4 shows the result.

Table 3.4: Predicting standard deviations with the lagged repurchase-adjusted __MASK_3_3__ ratio,  1927-2022
!__MASK_4_26__

__MASK_8_28__
The negative slope coefficient means that volatility tends to be somewhat higher when __MASK_3_8__ is lower. These are the times when our market-timing strategy raised the weight on the stock market index. So our market-timing strategy did inadvertently time volatility in the wrong direction. This may have lowered the Sharpe ratio that we achieved with this strategy a little bit,  but probably not by much as the relationship between the repurchase-adjusted __MASK_3_9__ ratio and future volatility is very weak: as the __MASK_3_10__-statistic shows,  the slope coefficient estimate is not statistically significant at

conventional significance levels.

Now let's turn to predicting volatility with lagged values of volatility. Looking back at Figure 3.16,  one can see just by eyeballing the chart that volatility is much more predictable than returns. Volatility is strongly positively autocorrelated and hence strongly predictable. When volatility is high in quarter __MASK_3_11__,  it is very likely that volatility is also going to be quite high in quarter __MASK_3_12__. The stock market history in this figure shows that there have been multiple cycles of high and low volatility that lasted several years. In terms of predictability,  this makes volatility very different from returns. While returns are hard to predict and the __MASK_3_13__ in any predictive regression for returns necessarily has to be low (at best perhaps a few percent in quarterly data for a good prediction model),  volatility can be predicted quite well.

Table 3.5: Predicting excess returns and standard deviations with lagged standard deviations,  1927-2022
!__MASK_4_27__

__MASK_8_29__
We can see this in the regressions show in Table 3.5. Panel A shows the parameter estimates from regressing the annualized standard deviation of daily returns within quarter __MASK_3_21__ on the lagged standard deviation in quarter __MASK_3_22__. In other words,  the __MASK_3_23__ coefficient in this regression is the autocorrelation coefficient of the volatility time series from Figure 3.16. The estimate for this coefficient of 0.650 shows that volatility is strongly positively autocorrelated. And the __MASK_3_24__ of $42.1/% shows that just with its own lagged value,  we can predict a substantial share of next-quarter variation in volatility. Thus,  volatility is indeed strongly persistent and predictable. This means that when volatility is above its long-run average in the current quarter,  it is also likely to be above the long-run average in the next quarter,  but also,  on average,  somewhat closer to the long-term average than in the current quarter. By the same token,  if volatility is below the long-run average in the current quarter,  it is also likely to be below the long-run average in the next quarter,  but also,  on average,  closer to the to the long-term average than in the current quarter.

Whether volatility timing could improve the Sharpe ratio of an investment strategy depends on whether conditional expected excess returns of the stock market index are

positive related to volatility or not. If they are,  then a strategy that scales down the weight of the stock market index in favor of the risk-free asset in times of high volatility may stay out of the market in times when expected excess returns are also high. If the relationship between conditional expected excess returns of the stock market index and volatility is sufficiently strongly positive,  then the attempt at volatility timing may actually result in a lower Sharpe ratio. In contrast,  if the conditional expected excess return of the stock market index does not vary with the level of volatility,  then the reward-to-risk ratio in the stock market is low when volatility is high,  and it may be beneficial to scale back the stock market exposure and dial it up in times of low volatility when the reward-to-risk ratio is higher.

To check whether conditional expected excess returns are positively related to volatility,  Panel B shows a regression of quarterly excess returns on lagged volatility. The estimated slope coefficient on lagged volatility is positive,  so there is a positive empirical relationship. But with a __MASK_3_2__-statistic a little below two,  it is not statistically significant at conventional significance levels,  despite about __MASK_3_3__ years of data,  and the __MASK_3_4__ is quite low. So it's not a strong positive relationship. It may be sufficiently weak for a volatilitytiming strategy to still have some beneficial effect on performance.

I will not attempt to derive the optimal utility-maximizing volatility-timing strategy here. Instead,  let's just start with the observation that if the expected excess return conditional on lagged volatility is constant,  __MASK_3_5__,  a mean-variance optimizing investor who looks one period ahead and uses the formula (3.52) would select a risky asset share of

__MASK_2_0__

Thus,  this investor's portfolio share would be proportional to __MASK_3_6__. Since multiplying the portfolio share by a proportionality constant does not affect the Sharpe ratio,  we can work directly with __MASK_3_7__ as the portfolio weight to investigate potential gains from volatility timing.

However,  we do not observe conditional volatility directly. Instead,  we are going to work with lagged volatility __MASK_3_8__ that was realized in quarter __MASK_3_9__. Volatility is,  as the regressions above showed,  very persistent,  but lagged volatility translates less than one-for-one into expected next-period volatility. Moreover,  the regressions above showed that conditional expected excess returns are actually at least somewhat positively related to lagged volatility,  and not exactly constant. So we should temper the aggressiveness of volatility timing a little bit. I try to address both of these issues with a very simple tweak: Rather than setting the portfolio weight __MASK_3_10__ equal to the reciprocal of __MASK_3_11__,  I set it

 !__MASK_4_15__

Figure 3.17: Cumulative standardized excess returns of the volatility-timing strategy

equal to the reciprocal of the standard deviation,

__MASK_2_1__

For this simple volatility-timing strategy,  we don't need to estimate any parameters. It is directly out-of-sample implementable. All we need is a measure of lagged volatility.

I calculate the time series of volatility-timing strategy excess returns as __MASK_3_12__ __MASK_3_13__ ). I then standardize the realized return by dividing by the full sample standard deviation (recall that this standardization turns the returns into a "realized Sharpe ratio"). I then cumulate these standardized returns over time. The red line in Figure (3.17) shows the result. For comparison,  I also show the cumulative standardized returns of a strategy that is always __MASK_3_14__100/% stock market index strategy. Looking closer,  we can also see that the volatility-timing strategy managed to partly avoid big downturns like in late 2008,  during the financial crisis,  or in the early 1930s,  during the onset of the Great Depression. The big down-moves in the stock market in these episodes were preceded in earlier months by elevated levels of volatility,  which leads the volatility-timing strategy to reduce equity exposure prior to the downturn.


