__MASK_7_24__
# Lecture 1 Probability Distributions of Returns

## Advanced Investments Lecture 1

Investment decisions can be broken down into

- Macro decisions: Allocation to broad asset classes such as equities,  bonds,  private equity,  commodities,  etc.
- Micro decisions: Choice of individual assets within an asset class,  such as selection of individual stocks within the equities asset class

In this course,  we focus mostly on macro decisions. The __MASK_6_14__ decision at the macro level has huge influence on the returns of large portfolios of institutional and private investors. The reason is that returns of securities within an asset class have substantial positive correlation. For example,  most individual stocks' returns are quite strongly positively correlated with the stock market index. So when the index moves up,  these stocks are likely going up,  too. A portfolio that allocates a big share to a somewhat diversified portfolio of equities therefore will very likely fluctuate quite strongly in line with a stock market index. A portfolio that has a small allocation to equities (and,  e.g.,  a much higher allocation to bonds) won't. So once the __MASK_6_15__ is set,  the risk properties of the portfolios are already pinned down to a substantial extent. Which securities are selected within an asset class also matters,  but less so.

We will spend a good portion of the time in this course on learning how we can assess properties of risk and return of different asset classes. Knowing these risk-return properties,  and their economic drivers,  is a prerequisite for implementing optimal __MASK_6_16__ models.

We use __MASK_3_1__ to denote returns of an asset in period __MASK_3_2__. Sometimes when it's clear that we are looking at returns over one period (and not,  say,  a time-series of returns) I may omit the __MASK_3_3__ subscript. An __MASK_3_4__ vector of returns on __MASK_3_5__ assets in period __MASK_3_6__ is denoted with __MASK_3_7__. More generally,  lowercase bold is my notation for vectors; uppercase bold for matrices.

### 1.1 Probability distributions of returns

A fundamental property of most asset returns is that future returns are uncertain. Throughout this course,  we use __MASK_6_17__s to represent this uncertainty. The __MASK_6_18__ tells us how likely it is that an asset delivers returns falling into various ranges.

We often summarize the __MASK_6_19__ in terms of moments. The first (central) moment of __MASK_3_8__ is the expected return,  __MASK_3_9__; the second (central) moment of the portfolio return is the variance,  __MASK_3_10__; the third (central) moment is skewness,  etc. Some simple __MASK_6_20__s can be summarized by a few moments. For example,  if we know the mean and variance of a normally distributed random variable,  we have completely described the distribution. If the distribution of single period (e.g.,  day,  month,  or year) returns __MASK_3_11__ is a normal distribution with mean __MASK_3_12__ and variance __MASK_3_13__,  we write

__MASK_2_0__

The empirical counterpart to a __MASK_6_21__ is the empirical distribution,  which is basically a histogram,  scaled so that the area covered by all bars adds up to one,  just like a __MASK_6_22__ function integrates to one. The size of the area of each bar in the histogram then tells us how often empirical observations of returns have fallen into various ranges. If we have used a sufficiently large sample of returns to construct the histogram,  the histogram should get close to the true __MASK_6_23__ of returns.

Let's focus on the stock market index as a whole as one risky asset (or the return on an exchange-traded fund that invests in essentially all U.S. stocks). I denote the return on the stock market index with __MASK_3_0__. To look at empirical distribution of returns,  I use monthly returns data from 1927 to 2022 on a value-weighted index of the entire U.S. stock market from the Center for Research in Security Prices (CRSP) here at the University of Chicago. In a value-weighed index,  each stock's weight in the index in month __MASK_3_1__ is the stocks' market capitalization at the end of month __MASK_3_2__ ( __MASK_3_3__ price __MASK_3_4__ number shares outstanding) as a fraction of aggregate market capitalization of all U.S. stocks at the end of month __MASK_3_5__.

Figure 1.1 plots a histogram of monthly returns and overlaid on it a curve that shows a normal __MASK_6_12__ function with mean and variance set equal to the empirical historical mean and variance of the return series. As we can see,  broadly speaking,  the fit is not bad. The bell curve shape of the normal distribution also appears in the histogram of the observed historical returns. Most monthly returns are within a few percent of zero,  monthly returns outside the __MASK_3_6__ range are very rare.

 !__MASK_4_11__

Figure 1.1: Empirical distribution of monthly U.S. stock market returns 1927-2022 with normal distribution fit

That said,  if we look more closely,  this figure already shows some empirical features of real-world stock returns that a normal distribution cannot capture properly and that we will have to investigate a bit more in the coming weeks. While monthly returns outside the __MASK_3_7__ range are very rare,  they do happen occasionally. Yet according to the normal distribution,  the probability of this happening should be extremely close to zero.

Another question that we will defer for a couple of weeks concerns changes in the __MASK_6_13__ over time. For example,  is the distribution of future stock returns the same in an economic boom period and in times when we are in a deep recession? Probably not. This is then a question of how the conditional distribution of returns looks like. For example,  following a big market crash (i.e.,  conditional on very low recent returns) does the __MASK_6_14__ of returns look the same as after a boom period in the stock market (i.e.,  conditional on very high recent returns)?

But one thing at a a time. For now,  we are going to stick to the assumption that returns are independently and identically distributed (IID) over time. This means that the conditional distribution of returns is not changing. Under this assumption,  no matter what happened in the past,  looking forward,  the __MASK_6_15__ of future returns is always the same.

The IID assumption is a useful approximation to get us started,  but this is not to say that this is entirely the right perspective. We will later spend a considerable amount of time precisely on the empirical evidence that returns are not IID. But for now,  to discuss basic properties of risk and return,  it makes sense conceptually to leave the issue of dynamically changing __MASK_6_16__s for the next step of our analysis.

Since we are dealing with IID returns,  we reduce notational clutter by dropping the time-subscripts and just write __MASK_3_8__,  and so on.

### 1.2 What is risk?

The purpose of using __MASK_6_17__s in __MASK_6_18__ analyses is to assess __MASK_6_19__s affect the risk and return of the portfolio. If we pick different assets,  or different combinations of assets,  this changes the risk and return properties of our portfolio and __MASK_6_20__s help us analyze this.

What we mean by return is clear. And when we talk about return in a forwardlooking way,  as the prospective future return on an investment,  we mean the expected return,  __MASK_3_9__.

But what exactly is risk? How can we measure it? Broadly speaking,  it has to do with the uncertainty that we face about future returns. If the assets we invest in are not riskless,  then realized returns are going to deviate from the expected return and so __MASK_3_10__ will be nonzero (positive or negative).

Suppose we evaluate a risky asset investment over a horizon of one period. A risk-free asset earns a certain return __MASK_3_2__ per period. We have several risky assets to choose from which all offer the same expected return __MASK_3_3__,  but different return variances. For now,  we'll think about how to choose one of these assets. (We'll think about combining assets into a portfolio later.) Given that they have the same expected return,  we would like to pick the one with the lowest risk. But what is the right measure of risk?

Variance (or its square root,  the standard deviation) is the most common measure of risk. Variance is calculated as

__MASK_2_0__

i.e.,  the deviations __MASK_3_4__ are squared and then averaged (by taking the expectation). The square root of variance,  __MASK_3_5__,  is the standard deviation. We often refer to the standard deviation of returns as volatility.

Given a time-series of returns from __MASK_3_6__ to __MASK_3_7__,  we can estimate variance as

__MASK_2_1__

i.e.,  we take all the deviations from the mean return,  square them,  and then average them across all time periods from __MASK_3_8__ to __MASK_3_9__.

 !__MASK_4_18__

Figure 1.2: Return distributions with different variances and same expected return

Figure 1.2 shows three __MASK_6_19__s. All with the same expected value __MASK_3_10__ (which is about a typical average monthly return on a broad stock market index),  and three different variances. Using variance to measure risk,  asset A is the preferred asset,  as it has the lowest variance.

There are cases where we know that variance is a perfect measure of risk. This is when the distribution of returns is fully described by mean and variance. This is the case for the normal distribution.

For the __MASK_6_20__s shown in this figure,  most people would probably agree with this choice. If all three assets offers the same return on average,  it makes sense to pick asset A whose realized returns tend to be much more closely concentrated around the expected return and hence less uncertain. (These distributions may look like normal distributions,  but they aren't. They are log-normal distributions and have a

slightly skewed to the right. We'll look in more detail at log-normal distributions later in this course).

To many people,  including some investment practitioners,  using variance to measure risk seems odd,  as variance considers upside and downside deviations symmetrically. Recall the definition of variance above: positive deviations of __MASK_3_11__ from __MASK_3_12__ contribute to variance in the same way as negative deviations. But shouldn't investors be concerned about the downside,  not the upside? Isn't upside a good thing so we shouldn't include positive deviations in a risk measure?

This intuition that risk measures should focus on the downside only may also come from the way risk is commonly understood in non-financial everyday usage. The Oxford English Dictionary for example defines risk as "(Exposure to) the possibility of loss,  injury,  or other adverse or unwelcome circumstance; a chance or situation involving such a possibility."

But as intuitive as this may seem,  purely focusing on the downside leads to some fallacies that we should avoid.

The first fallacy is to think that when we compare assets in terms of variance,  we are completely ignoring the fact that having an upside of potentially high returns is beneficial. We are already accounting for the upside in the expected return __MASK_3_13__. For example,  imagine taking the __MASK_6_21__ of asset (B) in Figure 1.2 and pulling the right tail of the distribution further to the right,  so that high returns become more likely,  while leaving the left half of the distribution unchanged. This would increase __MASK_3_14__,  which is the property of variance as a risk measure that some people find objectionable,  but note this that this would also,  at the same time,  raise __MASK_3_15__. Since we are considering __MASK_3_16__ and __MASK_3_17__ jointly in assessing risk and return,  we are not ignoring the benefits of greater upside.

A more subtle issue is whether __MASK_3_3__ and __MASK_3_4__ jointly properly capture the information that an investor needs to make a decision. Is the impact of right-tail observations on __MASK_3_5__ perhaps misleading and would it perhaps be better to consider __MASK_3_6__ in conjunction with a risk measure focused on downside risk?

Let's have a look at a common downside risk measure that is sometimes proposed as a better alternative to variance: the semi-variance

__MASK_2_0__

where __MASK_3_7__ is an indicator function that takes a value of one for __MASK_3_8__ and zero otherwise. The semi-variance is calculated like the variance,  but after setting observations of __MASK_3_9__ to zero if __MASK_3_10__.

Note that for a symmetric distribution,  such as a normal distribution,  semi-variance is always equal to one-half the variance. So semi-variance really only measures something different from the variance if the distributions are not symmetric.

 !__MASK_4_38__

Figure 1.3: Return distributions with same variances and same expected return

An example of non-symmetric (or skewed) distributions is shown in Figure 1.3. Both __MASK_6_39__s of returns of assets (A) and (B) in this figure have the same mean __MASK_3_11__ and the same variance __MASK_3_12__. So if we judge risk just based on variance,  we would be indifferent between asset (A) and (B).

In contrast,  semi-variances differ. Asset (A) has __MASK_3_13__,  while asset (B) has __MASK_3_14__. So based on semi-variance,  and forced to choose one asset,  one would choose asset (B). The returns of asset (B) have a longer left tail,  i.e.,  higher probability of big losses,  which tends to increase semi-variance,  but also overall a smaller probability that returns fall below the mean. Unlike for (A),  less than __MASK_3_15__ of the probability mass,  i.e.,  less than __MASK_3_16__ of the area under the __MASK_6_40__ function,  is accounted for by returns lower than the expected return of __MASK_3_17__. This second feature dominates and leads to a lower semi-variance than for asset (A).

That asset (B) is better for a risk averse investor is not obvious at all. For example,  an investor who does not worry too much about small losses but is very averse to big losses might prefer asset (A).

Generally,  there are certainly reasons for variance not being a perfect measure of risk,  but the idea that semi-variance is typically a better criterion is a fallacy.

Consider the following example. Suppose asset __MASK_3_18__ has a price of __MASK_3_19__ and in the following period delivers payoffs __MASK_3_20__ each with probability __MASK_3_21__ (see Figure 1.4a). Asset __MASK_3_22__ also has a price of __MASK_3_23__ and a low payoff of __MASK_3_24__ with __MASK_3_25__, but the higher payoff is split into two: __MASK_3_26__ with probability __MASK_3_27__ and __MASK_3_28__ also with __MASK_3_29__ (see Figure 1.4b).

Note that both assets have the same expected return __MASK_3_30__. But the risks are different. Asset __MASK_3_31__ 's payoffs are symmetric around the expected payoff of __MASK_3_32__. In contrast,        __MASK_3_33__ 's payoff has positive skewness. There is a chance of a positive payoff of __MASK_3_34__ that is far above the expected payoff.

What do variance and semi-variance tell us? Variances are

__MASK_2_1__

So choosing based on lower variances leads us to choose asset __MASK_3_35__.

In contrast,  semi-variances are the same

__MASK_2_2__

& \operatorname{var}\left(R_{A}\right)^{-}=\frac{1}{2}(-0.375-0.25)^{2} \approx 0.19  \tag{1.7}

& \operatorname{var}\left(R_{B}\right)^{-}=\frac{1}{2}(-0.375-0.25)^{2} \approx 0.19 \tag{1.8}

\end{align*}$$

This should be intuitive from the payoff diagram: Both assets's payoffs have the same downside. They only differ on the upside. Hence,  semivariances are the same. A measure of risk that focuses only on the magnitude of potential losses is useless here in helping us choose between these two assets - unless we think that we should really be indifferent between asset __MASK_3_36__ and asset __MASK_3_37__.

But this would be an odd choice. Any risk averse person,  no matter how weak their risk aversion is,  as long as they have slight risk aversion,  would prefer asset __MASK_3_2__. We can see this by thinking of asset __MASK_3_3__ as a compound gamble __MASK_3_4__. The payoff diagram 1.4 c depicts this compound gamble. First,  we take the gamble associated with asset __MASK_3_5__. Then,  if we reached the upper node,  where we receive 1.50 we immediately reinvest these proceeds in an additional gamble with price of 

__MASK_2_0__

 2.00

__MASK_3_6__ and get payoffs with an expected value of __MASK_3_7__ 2.00+\frac{1}{2} __MASK_3_8__ 1.50__MASK_3_9__0 \%__MASK_3_10__A__MASK_3_11__B__MASK_3_12__A__MASK_3_13__B$.

Focusing on semi-variance would mislead us by ignoring uncertainty on the upside in gamble __MASK_3_14__. It makes a difference to us whether there is uncertainty on the upside. Holding the expected return conditional on being on the upside fixed,  knowing for sure what you get conditional on being on the upside is better than being uncertain about how much upside you will get.

The broader point here is that the idea that we should not care about uncertainty on the upside is just wrong. A sure upside is still preferable for a risk averse investor relative to an uncertain upside with the same expected payoff (conditional on being on the upside part of the payoff distribution).

This does not mean that variance is always a good measure of risk. Later in this course,  we will also encounter investment strategies that produce highly skewed return distributions for which variance is,  indeed,  a poor measure of risk. Depending on the investor's preferences,  a measure that gives more weight to downside risks than variance does may well be appropriate. For now,  we'll just keep in mind that some of the oftenmentioned arguments against variance as a measure of risk are not well founded.

Another common downside-risk measure is Value-at-Risk. Value-at-Risk (VaR) is a number for the loss that won't be exceeded with __MASK_3_15__ or sometimes __MASK_3_16__ confidence. Here we focus on the __MASK_3_17__ version. Losses bigger than the VaR should only arise,  on average,  __MASK_3_18__ of the time. Figure 1.5 illustrates this for the distribution of monthly U.S. stock market returns from Figure 1.1 earlier. The estimated VaR in this case is __MASK_3_19__. This means that in __MASK_3_20__ of all months in the sample monthly losses exceeded __MASK_3_21__.

For comparison,  I also added lines that show the mean and the mean minus 2.326 times the standard deviation. If the distribution of stock returns was exactly normal,  then the VaR would be equal to the mean minus 2.326 times the standard deviation,  which is __MASK_3_22__. This a smaller loss than the VaR we estimated,  but not much smaller. So in terms of the VaR,  normality is not a bad approximation in this case.

Another indication that normality is not a bad approximation here,  the semi-variance is almost identical to the one-half the variance of these returns (and hence __MASK_3_23__ times the square root of the semi-variance is almost identical to the standard deviation). So I did not plot a semi-variance measure.

 !__MASK_4_26__

Figure 1.5: Estimated Value-at-Risk based on empirical distribution of monthly U.S. stock market returns 1927-2022

An obvious shortcoming of the VaR measure is that it does not take into account how big the losses are that exceed the VaR. It only tells us about the probability that we will see losses bigger than the VaR,  but not the magnitude.

One measure that fixes this is the Expected Shortfall. It tells us the expected value of the losses that exceed the VaR,  i.e. __MASK_3_24__. For the monthly stock returns in Figure 1.5,  the expected shortfall is __MASK_3_25__. To estimate it,  I took all the monthly stock return observations that are lower than the VaR. I averaged them to get the estimated of the expected shortfall.

Semi-variance,  VaR,  and expected shortfall measures can be useful as an additional risk metric if losses beyond a certain threshold are of particular relevance. For example,  if we want to find a portfolio strategy subject to the constraint that losses (or probability of losses) do not exceed a certain threshold. Such thresholds sometimes also have regulatory relevance (e.g.,  in bank or insurance regulation). But even these measures struggle with capturing the risk of extreme market crashes.

### 1.2.1 Crash risk

As we saw above,  for monthly stock returns normality doesn't seem to be a bad approximation for returns on a broad stock market index. As a note of caution though: if one looks farther out into the left tail,  beyond the __MASK_3_0__ VaR,  the normal distribution no longer provides a good approximation of the distribution. By assuming a normal distribution,  we would underestimate the frequency and severity of occasional stock market crashes.

We can see this best in daily data. Figure 1.6a plots the empirical distribution of daily returns on the same U.S. stock market index that provided the monthly returns earlier in Figure 1.5,  overlaid with a best-fitting normal distribution. From this plot the deviations from normality seem minor.

However,  we are interested in tail behavior,  so we need to zoom into the tails to see what's going on there. This is done in Figure 1.6b. The 99% VaR for these daily returns is __MASK_3_1__. If we look at losses that exceed this threshold,  their empirical probability is far higher than the probability implied by a normal distribution. For losses exceeding __MASK_3_2__,  the normal distribution would imply probabilities that are essentially zero,  for all practical purposes. But several crashes of this magnitude happened in the past one hundred years.

The biggest loss in Figure 1.6b at the very left happened on October 19,  1987,  a day that came to be known as Black Monday. The CRSP value-weighted index that we are working with here fell by __MASK_3_3__ on that day. The S&P500 index,  which focuses on the largest firms in the U.S. stock market fell by about __MASK_3_4__. Figure 1.7 shows the price chart of the S&P500 index around Black Monday. This was (and still is) the biggest daily drop in (U.S.) history!

If daily stock returns were normally distributed,  a drop by __MASK_3_5__ in a single day should happen,  on average,  less than once in __MASK_3_6__ days. For comparison,  the age of the universe is estimated to be less than 20 billion years,  which is less than __MASK_3_7__ days! So it's safe to say that the normal distribution severely underestimates the possibility of large stock market crashes.

That the stock market is exposed to such crash risk is useful to keep in mind. Many standard quantitative models built into __MASK_6_11__ software rely heavily on variances and covariances as measures of risk and hence they do not fully account for the presence of this crash risk (because it's mathematically difficult to do so). For this reason,  it may make sense to use simulation methods to check the extent to which the return on a target portfolio is exposed to crash risk and whether this level of crash risk is acceptable,

 !__MASK_4_8__

(a) Empirical distribution of daily stock returns

 !__MASK_4_9__

(b) Zooming in to the tails

Figure 1.6: Fat tails in daily U.S. stock market returns with best fitting normal distribution,  1927-2022

 !__MASK_4_10__

Figure 1.7: S&P500 Index around October 19,  1987 (Black Monday)

or whether financial engineering should be used to obtain insurance against big losses (we'll get to this later in the course).

### 1.3 Risk aversion

In the end,  there is no such thing as a universal,  one-size-fits-all risk measure. How risk should be measured ultimately depends on an investors attitude toward risk. How much does the investor value upside of high returns relative to the possibility of poor returns on the downside? How much does the investor fear small losses compared with large losses? This is determined by the investors' risk preferences,  which typically involve risk aversion.

The hallmark of risk aversion is that a risk-averse investor finds an asset with __MASK_3_3__ __MASK_3_4__ and an uncertain return less desirable than one that earns __MASK_3_5__ for sure. The way to represent such risk aversion is to assume that the investor maximizes the expectation of a concave function __MASK_3_6__ of wealth. For a concave function __MASK_3_7__ if __MASK_3_8__ is uncertain. Broadly speaking,  more uncertainty about __MASK_3_9__,  while holding __MASK_3_10__ fixed,  lowers __MASK_3_11__. In this way,  the assumption that the investor maximizes __MASK_3_12__ captures the investor's aversion to risk.

We will label __MASK_3_13__ a utility function and its first derivative,  __MASK_3_14__ marginal utility.

Marginal utility captures how valuable an addition to wealth would be in different states of the world. Since __MASK_3_15__ is concave,  marginal utility is declining with higher wealth. This means that an additional dollar from a positive return raises the investor's utility less than a dollar of losses lowers utility. This generates a motive for insurance: the investor would be willing to give up some payoffs in high wealth states to get higher payoffs in low wealth states.

Utility functions are typically associated with preferences of individual consumers. But for our purposes here,  __MASK_3_16__ can be a stand-in for anything that might make an investor (which could be a financial institution rather than an individual investor) assign higher value to payoffs in some states than in other states. For example,  a bank concerned about violating regulatory thresholds for minimum equity capital has a strong motivation to avoid even getting to close to this threshold. Hence,  for this bank,  "marginal utility" is high in states of the world where they are close to breaching their capital requirement thresholds. They may have a motive to obtain insurance (e.g.,  hedging with derivatives) that delivers payoffs in such states of the world.

How exactly the investor's aversion to risk looks like,  e.g.,  which types of risk the investor fears the most,  is determined by the functional form of __MASK_3_17__. We work with a power-utility function

\begin{equation*}

U(W)=\frac{W^{1-\gamma}-1}{1-\gamma},        \quad U^{\prime}(W)=W^{-\gamma} \tag{1.9}

\end{equation*}

__MASK_2_0__

\begin{equation*}

U(W)=\log (W) \quad \text { if } \quad \gamma=1 \tag{1.10}

\end{equation*}

__MASK_2_1__

\begin{equation*}

U^{\prime}(W)=W^{-\gamma} \tag{1.11}

\end{equation*}

__MASK_2_2__ 1,  000$ in wealth and finds it optimal,  say,  to put half of it into risky assets and half of it into a risk-free asset,

[^0] !__MASK_4_21__

Figure 1.8: Power utility and marginal utility

then an investor with __MASK_3_18__ of wealth and the same __MASK_3_19__ would also put half of it into risky assets and half into the risk-free asset. Thus,  a power-utility investor's exposure to risky bets,  measured as the proportion of wealth invested in risky assets,  does not change with the wealth level. Another way of saying this is that relative risk aversion is constant. We therefore refer to power utility also as constant relative risk aversion (CRRA) preferences. __MASK_3_20__

CRRA may not be entirely empirically realistic,  but it's quite reasonable. Certainly

[^1] !__MASK_4_22__

Figure 1.9: Equity share conditional on stock market participation for households of different wealth levels (Survey of Consumer Finances 2022)

it is much more reasonable than a utility function that implies that the dollar amount of risky asset investments rather than the proportion is constant with respect to wealth (this would happen with utility functions of the constant absolute risk aversion kind).

Figure 1.9 shows some data on this from the 2022 version of the Survey of Consumer Finances conducted by the Federal Reserve Board. I grouped all survey respondents into 20 groups based on their total level of financial assets (stocks,  bonds,  including retirement accounts,  bank deposits,  etc.). The x-axis shows the average log wealth of respondents in each group,  i.e.,  the wealthiest households are in the right-most group. The y-axis shows the average equity share,  i.e.,  the proportion of financial assets invested in stocks (directly held and via mutual funds,  including retirement accounts). I use only data from survey respondents who have at least some investment in stocks. __MASK_3_6__

There is a slight increase of the equity share going from the poorest to the richest households. But the increase from about __MASK_3_7__ to __MASK_3_8__ is small considering that the wealth differences between the different bins are huge. Households in the lowest bin have,  on

[^2]average,  __MASK_2_0__ 90 \mathrm{~m}$ on average.

Moreover,  if we want to use a utility function to capture the risk attitude of an institutional investor such as a pension fund or an endowment,  there is little reason to think that an institution with a bigger portfolio would necessarily want to devote more or less of its portfolio to risky assets. Hence,  CRRA preferences seem like a useful starting point for modeling the risk attitudes of institutions.

### 1.4 Optimal __MASK_6_35__

Let's now consider a simple __MASK_6_36__ problem using CRRA preferences. Suppose the investor wants to choose among two assets: A risk-free asset that offers return __MASK_3_9__ and a risky asset that offers IID returns __MASK_3_10__. If the investor starts with __MASK_3_11__ at the beginning of a period and invests a proportion __MASK_3_12__ into the risky asset,  then the return on their wealth portfolio is
__MASK_2_1__
Below we'll use the rules that __MASK_3_13__ and __MASK_3_14__.

If the wealth portfolio earns the overall return __MASK_3_15__,  then the investor's wealth at the end of the period is __MASK_3_16__. Therefore,  the investors' objective is to
__MASK_2_2__
which we can write as
__MASK_2_3__
Now note from (1.15) that if we increase __MASK_3_17__ by one unit,  we're changing the wealth return __MASK_3_18__ by __MASK_3_19__,  so __MASK_3_20__. Using the chain rule,  the first-order condition of the problem (1.17),  then is
__MASK_2_4__
or,  after dividing by __MASK_3_21__ (which is known at the beginning of the period),
__MASK_2_5__
Let's consider a simple example to understand the meaning of this first-order condition and also solve for the optimal portfolio weight. Suppose __MASK_3_22__ and __MASK_3_23__ so that __MASK_3_24__. Further,  assume that the risky asset return can only take two values,

__MASK_3_25__ or __MASK_3_26__,  with equal probability. In this simple case,  we'll be able to figure out the optimal portfolio weight of risky assets.

But first let's use this simple special case to understand the meaning of the first-order condition. Consider what happens to wealth if we take one dollar from risk-free asset and put it into risky asset: __MASK_3_27__ changes by -0.10 ,  and __MASK_3_28__ changes by 0.20 . So the difference in wealth between the good state,  when the risky asset return is high,  and the bad state,  when the risky asset return is low,  becomes bigger.

What happens to utility? For a small shift of just one dollar to the risky asset,  the effect on utility is given by the marginal utility times the wealth change (this is an application of the chain rule). __MASK_3_29__ So in the bad state,  __MASK_3_30__ changes by __MASK_3_31__ __MASK_3_32__. In the good state,  __MASK_3_33__ changes by __MASK_3_34__.

The reduction of utility in the bad state is the marginal cost,  in utility terms,  of increasing the risky asset exposure of the portfolio. The increase in the utility in the good state is the marginal benefit. As in any economic optimization problem,  the optimum choice is where marginal costs and benefits are equal,  because this means the utility from the portfolio cannot be improved in any way. (In contrast,  if,  we are at a point where,  say,  the marginal cost exceed the marginal benefit,  we can improve the portfolio by reducing the risky asset share because the reduction of cost in this case outweighs the reduction of benefit.)

One additional consideration here is the probability with which the good or bad state happen. After all,  it matters not only how big marginal cost and benefit are,  but also how likely they are to arise. We take this into account by multiplying the marginal cost and benefit by the probability that they occur,  which is simply __MASK_3_3__ each here. So at the optimum we must have __MASK_3_4__. Rearranging,  we get
__MASK_2_0__
which is exactly the first-order condition (1.19) for this special case. The equation says that the expected marginal benefit must be equal to the expected marginal cost at the optimum.

Figure 1.10 illustrates this with a power utility example __MASK_3_5__. The blue line shows the marginal benefit __MASK_3_6__. As we increase the risky asset share,  we are shifting more wealth to the good state in which the risky asset has a high return. But the benefit,  in terms of the marginal increase in utility from doing this,  declines as we shift more and more to the risky asset toward the right in the plot. This is a consequence of

[^3] !__MASK_4_15__

Figure 1.10: Two-state example: Marginal benefit and cost of higher risky asset share (power utility with __MASK_3_7__ )

risk aversion and the associated concavity of utility. The yellow line shows the marginal cost. As we shift more into the risky asset,  and as we are getting poorer in the state in which the risky asset has losses,  the marginal cost of wealth reductions in the bad state are getting bigger. This is again a consequence of risk aversion and the associated concavity of utility. The red line shows the combined consequence in terms of expected marginal benefits and costs. We reach the optimum,  where expected marginal benefits and costs exactly balance,  at a risky asset share slightly below __MASK_3_8__.

If the risky asset's return in the good state was higher,  then the marginal benefit would be higher and the optimum where marginal cost and benefit balance in expectation would be at a higher risky asset share. The same would be true if the loss of the risky asset in the bad state was smaller.

We would now like to solve the first-order condition in 1.19 for __MASK_3_9__ with CRRA preferences in the general case of more realistic __MASK_6_16__s of returns that allow returns to take infinitely many values,  not just two. But this turns out to be an intractable problem. There is no mathematical solution that delivers a simple formula.

For this reason,  we will now use an approximation approach. As it turns out,  this approximation will lead us to a solution that trades off mean and variance of returns,  and hence provides foundation for the mean-variance approach to __MASK_6_17__ that you encountered in your introductory investments course and that is pervasive in industry practice. We first scale the first-order condition 1.19 to
__MASK_2_1__
where we divided by __MASK_3_10__. With power utility,  where __MASK_3_11__,  we can approximate __MASK_3_12__ linearly as __MASK_3_13__
__MASK_2_2__
Figure 1.11 shows how this approximation looks like for power utility with __MASK_3_14__. True marginal utility is nonlinear,  but we approximate it with a linear function. This also means that we approximated utility with a quadratic function,  locally around the point at which we are approximating. Most importantly,  this approximation preserves the risk aversion property,  as the approximate utility function is still concave.

As with any approximation,  there is some approximation error,  though. We may be losing the somewhat stronger curvature of the power utility function away from the approximation point. For small risks,  where wealth does not deviate too far from the point where we approximated,  the approximation is accurate. Relatedly,  for __MASK_6_10__ problems over short horizons until the next rebalancing point (say a month or quarter),  very large changes in wealth are unlikely,  so the approximation should be fine. But we should keep in mind that it would not be accurate for very big shocks that move wealth far from the approximation point.

Substituting this approximation into the first-order condition (1.19),  we get
__MASK_2_0__
and hence
__MASK_2_1__
[^4] !__MASK_4_9__

Figure 1.11: Actual marginal utility and first-order approximation (power utility with __MASK_3_3__ ). Risky asset return on __MASK_3_4__-axis shown in excess of __MASK_3_5__

which we can solve for the optimal risky asset share
__MASK_2_2__
This is the mean-variance optimal portfolio solution for the single risky asset case.

In this solution,  variance of returns measures risk. This reinforces the conclusion from our earlier discussion of risk measures that using a symmetric measure of risk that equally weights positive and negative (squared) deviations from the expected return is not in contradiction to being averse to risk.

That said,  by linearizing marginal utility,  we may have approximated away that marginal utility may rise particularly drastically when we get into region of huge losses. In other words,  the approximation may not well capture concerns about downside risks beyond what's captured by variance. By the same token,  the linear approximation overstates how much marginal utility falls in the region of big gains. Therefore,  if an asset has positively skewed payoffs,  with some large positive outliers,  the linear approximation

of marginal utility may substantially overstate the risks. This may be relevant especially for extremely risky assets,  or at long horizons. (In contrast,  if the distribution of returns is symmetric,  such as with a normal distribution,  then the errors on the upside and downside would offset to zero on average.)

Taking this into account,  variance would have to be supplemented by skewness,  or some other measures that capture asymmetry in outliers. But variance would still be an important chunk of the risk.

The longer the horizon over which we measure returns,  the bigger the deviations of ending wealth from the wealth level around which we are approximating marginal utility. Moreover,  at long horizons returns basically have to be skewed because they can't be less than __MASK_3_6__,  while the upside is unlimited. So approximation errors are likely to grow with the return measurement horizon. But we can avoid large approximating errors due to long horizons by using means and variances measured over short horizons such as monthly rather than multi-year periods (and,  correspondingly,  rebalancing the portfolio more frequently back to the optimal portfolio share).

### 1.5 Calibrating risk aversion

Risk aversion determines which distribution of portfolio returns we want. But what is a plausible value for __MASK_3_7__ ? How much does a typical investor really care about risk?

One way of getting some rough idea about likely plausible magnitudes for risk aversion is to look at the portfolio of the "average" investor (with "average" we really mean wealth-weighted average,  but to reduce clutter,  we'll just say "average"). How does the average investor's portfolio look like? Let's do a rough back-of-the-envelope calculation where we treat all bonds,  government and corporate,  as risk-free asset and let's treat stocks as the risky asset class. We ignore other assets. Then we compute the average investor's equity share as the total market value of equity securities divided by the sum of outstanding equity and debt securities held by U.S. domestic investors. The Financial Accounts of the United States tells us that this share is __MASK_3_8__ at the end of 2022. Figure 1.12 shows the post-WWII history of this equity share.

So to explain the average investor's __MASK_6_11__ at the end of 2022 with our formula (1.26),  we need it to yield
$$

\begin{equation*}

0.57=\frac{\mathbb{E}\left[R-R_{f}\right]}{\gamma \operatorname{var}(R)} \tag{1.27}

\end{equation*}

$$
At an annual horizon,  a plausible value for __MASK_3_0__,  based on historical data,  is __MASK_3_1__; a plausible value for __MASK_3_2__ is 0.03 . Plugging in these values,  we can solve for __MASK_3_3__.

 !__MASK_4_13__

Figure 1.12: Equity share as a fraction of total debt and equity securities held by U.S. domestic investors

This tells us that relative risk aversion in the range of around 2 to 3 is a plausible value for a typical investor.

### 1.6 Market equilibrium

When we try to figure out the best choices for our own portfolio,  it's also useful to keep an eye on what this implies for what the rest of the market,  i.e.,  other investors must be doing. In other words,  it's useful to consider how our own choices fit into the bigger scheme of things in terms of market equilibrium.

Consider the data we just discussed that the average investor in the U.S. seems to have an equity share of roughly __MASK_3_4__. Now suppose according to our beliefs about expected returns and risk,  and considering our own risk aversion,  we come to the conclusion that we want to hold __MASK_3_5__ percent in equities. But for us to hold more in equities than the average investor,  someone else must be willing to hold less than the average investor.

Along the same lines,  if we decide to increase our equity share (for example,  because

our beliefs about future risk and return have changed),  then for us to be able to do so,  someone else must be willing to decrease it. In the short-run at least,  the supply of bonds and stocks is fixed. So for every buyer,  there must be a seller. Otherwise the market would not clear. Supply would not equal demand.

This equilibrium thinking leads to a number of important insights:

Price can change without (much) buying or selling: For example,  what happens if the average investor wants to get more exposure to equities and hold a portfolio with a higher equity share? Again,  in the short-run at least,  the supply of bonds and stocks is fixed. So investors' desire for a higher equity share cannot be satisfied by giving them a greater number of shares. Instead,  the price must adjust. If investors want to hold more shares of stocks than the total supply available to the market,  stock prices will go up (and possibly bond prices go down). This has two effects. First,  a rise in the price with expectations of future prices and fundamentals unchanged lowers the expected return of equities. This makes equities less attractive and lowers investors' desired equity share. At the same time,  the rise in the price raises the aggregate equity share at market prices. Both of these effects contribute to getting investors' desired equity share to equal the aggregate equity share at market prices. If the price rise is big enough,  desired portfolio weights and market portfolio become equal,  supply equals demand and the market clears and is in equilibrium.

If we aim to hold a risky asset share that differs from the market's aggregate equity share at current prices,  we are implicitly expressing the view that we are different from the average investor,  either in terms of beliefs about risk and return __MASK_3_6__ and __MASK_3_7__ or risk aversion __MASK_3_8__. For example,  if the market's aggregate equity share is __MASK_3_9__,  but we hold an equity share of __MASK_3_10__,  we are implicitly taking a stand that we are less risk averse than the typical investor or more optimistic about equity risk and return than the average investor.

Similarly,  if we change our share differently from how the market's aggregate equity share changes,  we are implicitly expressing the view that our beliefs about risk and return,  or our risk aversion,  have changed differently from the average investor's.

The idea that cash flows "into the stock market" from the "sidelines" or "out of the stock market" to the "sidelines" doesn't make any sense (except perhaps somewhat in the long-run when the supply of securities may respond to demand,  e.g.,  via initial and seasoned equity offerings by companies). For every buyer who goes (more) into the stock market,  there is a seller that (partly) exits the market. Flows of cash can be going to or from some investors,  say equity mutual funds,  but

not to or from the market as a whole. When mutual funds that received inflows buy stocks,  someone else has to sell stocks. So the net flow into the market is always zero. If highly motivated buyers of stocks meet reluctant sellers of stocks,  stock prices will go up to get supply to equal demand. But it will still be the case that for every __MASK_3_11__ dollars in total the buyers spend on stocks,  the sellers will receive the same __MASK_3_12__ dollars.

### 1.7 Estimation of optimization inputs

The optimal portfolio formula we developed needs inputs: Expected returns and variances. In practice,  we don't know these numbers and we need to estimate them from data. A lot of what we do in this course is looking at data that can be informative about these unknown moments.

Other problems,  such as whether the mean-variance approximation of the portfolio problem is sufficiently accurate,  often pale relative to the problem of how to get reliable inputs to the optimal portfolio formulas.

We can estimate expected returns __MASK_3_6__ with the sample mean
__MASK_2_0__
To see what this does,  write the return on the asset as the expected return __MASK_3_7__ plus random noise:
__MASK_2_1__
Here __MASK_3_8__ is the "signal" that we would like to tease out from returns; __MASK_3_9__ is noise that obscures this signal. This noise is the reason why we can't observe expected returns directly in the sample. What we can observe is a mix of the true expected return and noise. If the variance of __MASK_3_10__ is big,  this will make __MASK_3_11__ a more imprecise estimate of __MASK_3_12__. Specifically,  in a given sample,  our estimate
__MASK_2_2__
has the true expected return __MASK_3_13__ obscured by the noise __MASK_3_14__. Since we don't know the true __MASK_3_15__ and the __MASK_3_16__,  we cannot tell the two apart. The only thing we can do is to try to quantify how big the noise distortion in our estimate __MASK_3_17__ is likely to be. Statistics tells us that if the __MASK_3_18__ each periods are IID (which means,  among other things,  that knowing

__MASK_3_19__ or earlier returns we can't predict __MASK_3_20__ ) and they have variance __MASK_3_21__,  then the standard error of the mean that quantifies our uncertainty about __MASK_3_22__ can be calculated as __MASK_3_23__
__MASK_2_3__
The assumption of IID noise is actually not a bad approximation. As we will discuss in the next lecture,  returns in various asset classes generally have little autocorrelation,  i.e.,  returns in earlier periods don't help to predict __MASK_3_24__. This is one requirement for the independence in "IID." Also note that this assumption of serial independence is about lack of dependence across different time periods. Within time periods,  returns in different asset classes can (and typically will be) correlated with each other. We are not ruling out such correlation between asset class returns.

If we make the additional assumption that the noise shocks are normally distributed,
__MASK_2_4__
and we have no other knowledge about the location of __MASK_3_25__ than what we saw in the data set of returns from __MASK_3_26__ to __MASK_3_27__,  then
__MASK_2_5__
This means that our knowledge about the location of __MASK_3_28__ is now summarized by __MASK_3_29__ and normal distribution around __MASK_3_30__ with standard deviation equal to the standard error s.e. __MASK_3_31__ The higher the standard error,  the more uncertain we are about the location of __MASK_3_32__. There is a __MASK_3_33__ chance that the true __MASK_3_34__ lies within __MASK_3_35__ s.e. __MASK_3_36__,  or approximately,  __MASK_3_37__ s.e. __MASK_3_38__.

[^5] !__MASK_4_44__

Figure 1.13: Uncertainty about expected return with __MASK_3_39__ and s.e. __MASK_3_40__

Figure 1.13 illustrates the uncertainty we have about the expected return after seeing estimates __MASK_3_41__ and s.e. __MASK_3_42__.

Now,  the formula for the standard error of the mean requires knowing the variance __MASK_3_43__. How do we get this? We estimate it,  too,  as
$$

\begin{equation*}

\hat{\sigma}^{2}=\frac{1}{T-1} \sum_{t=1}^{T}\left(R_{t}-\hat{\mu}\right)^{2} \tag{1.34}

\end{equation*}

__MASK_2_0__

\begin{equation*}

S R=\frac{E[R]-R_{f}}{\sigma} \tag{1.35}

\end{equation*}

$$
If there are two assets with different __MASK_3_1__,  and the investor can pick only one of them,  not a combination of the two,  then any risk averse investor (for whom variance is the correct risk measure) would go for the one with the higher __MASK_3_2__.

The reason is that if one,  say asset __MASK_3_1__,  has a higher __MASK_3_2__ than the other,  asset __MASK_3_3__,  then we could always use leverage or a combination with an investment in the risk-free asset to make our investment in __MASK_3_4__ deliver the same variance,  but a higher expected excess return than an investment in __MASK_3_5__. To be concrete,  suppose asset __MASK_3_6__ has __MASK_3_7__ and __MASK_3_8__ and hence __MASK_3_9__ while asset __MASK_3_10__ has __MASK_3_11__ and __MASK_3_12__ and hence __MASK_3_13__. If we put __MASK_3_14__ into asset __MASK_3_15__ and the rest in the risk-free asset,  then this portfolio will have expected excess return of __MASK_3_16__ and return standard deviation __MASK_3_17__. Hence,  it will have the same standard deviation as asset __MASK_3_18__,  but a higher expected excess return,  which makes it clearly better: same risk,  but higher expected return.

Once we have picked the asset,  we can then lever up or down to achieve the optimal risky asset share
__MASK_2_0__
Of course,  combining risky asset classes may be much better than picking a single one. For this,  we need to take into account the correlation of an asset returns. We'll get to this important point in the next session.
$$


