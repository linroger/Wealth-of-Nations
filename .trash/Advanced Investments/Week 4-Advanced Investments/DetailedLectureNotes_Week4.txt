---
aliases:
- Alias_249_DetailedLectureNotes_Week4.md
- LECTURE 4
- Alias_251_DetailedLectureNotes_Week4.md
linter-yaml-title-alias: LECTURE 4
tags:
- tag_example
title: LECTURE 4
---


# LECTURE 4

In the last lecture we discussed that the aggregate valuation of the stock market, as measured by ratios such as the price-dividend or price-earnings ratios, varies strongly over time. And we discussed that a model with time-varying investor sentiment could potentially explain why stock market valuations vary so much and why the valuation levels are inversely related to future stock market returns.

Now we look more closely at the notion of investor sentiment. What is the nature of time-varying investor sentiment that could be driving these valuation cycles? Better understanding of the nature of investor sentiment could help us make better use of the valuation assessments that we get from valuation ratios. If we can tie variation in valuation levels to investor cash flow growth expectations, we can ask whether we agree with these growth expectations. If we can tie variation in valuation levels to changing perceptions of risk or risk aversion, we can ask whether we share these changing perceptions of risk or risk aversion. If we can tie variation in valuation levels to changing demand for stock market investing coming from certain investor groups, we can ask whether these demand changes are likely informed or uninformed demands. Answers to these questions can help us get more confidence whether a valuation ratio like the price-dividend ratio at a given point in time is a good signal about future excess returns on the stock market.

We start by using our sentiment-based valuation model from the last lecture to understand better the di↵erent potential sources of time-varying sentiment and their e↵ects on stock market valuation. Recall from last lecture the approximate presentvalue identity in (3.25) after we took conditional expectations:

$$v_{t}=\frac{c}{1-\rho}+\sum_{j=1}^{\infty}\rho^{j-1}\,\mathbb{E}_{t}[\Delta d_{t+j}]-\sum_{j=1}^{\infty}\rho^{j-1}\,\mathbb{E}_{t}[r_{t+j}].\tag{4.1}$$

Note also that we can interpret the dividend growth rates dt+j and returns rt+j as real returns. After all, the inflation part of a nominal dt+j cancels with the inflation part

## 115

of a nominal rt+j, so (4.1) holds with nominal or real quantities on the right-hand side
(as long as both are nominal or both are real). In what follows, we'll think of them as real.

In our discussion last lecture we assumed, as a benchmark, that a rational investor, who is not influenced by sentiment, would price the stock market under the belief that dividend growth is constant, Et[dt+j] = g, and expected returns are constant as well, Et[rt+j] = ✓, which yields the valuation

$$v_{t}=\frac{1}{1-\rho}(c+g-\theta),$$
$$(4.2)$$
$$(4.3)$$

while the actual investors' valuation is subject to investor sentiment, st,

$$v_{t}=\frac{1}{1-\rho}(c+g-\theta)+s_{t}.$$

We now have two possibilities regarding the nature of investor sentiment.

First, sentiment could reflect time-varying optimism and pessimism about dividend growth. Suppose investors' growth rate expectation is ˜gt 6= g, but sentiment investors' expected rate of return that they demand from a stock market investment is the same as the rate ✓ that investors not subject to sentiment would demand. More precisely, at time t actual investors are valuing the stock market as if dividends were to grow at an expected rate of ˜gt forever, while the correct expectation is g. In the next period, t + 1, investors may change their mind and their new growth rate expectation may be a di↵erent number ˜gt+1, but at time t they do not anticipate that they will change their mind in the future. The resulting valuation then would be

$$v_{t}=\frac{1}{1-\rho}(c+\tilde{g}_{t}-\theta),$$

which maps into (4.3) with

$$(4.4)$$
$$s_{t}=\frac{1}{1-\rho}(\tilde{g}_{t}-g).$$

So in this version, investor sentiment is driven by excessively volatile expectations of dividend growth that vary around the constant true expected growth rate g.

Second, sentiment could reflect time-varying risk aversion or time-varying risk perceptions that make investors demand a time-varying expected rate of return ˜✓t from stock market investments, while investors' expected growth rate is equal to the true growth rate g. In this case,

$$v_{t}=\frac{1}{1-\rho}(c+g-\tilde{\theta}_{t}),$$
$$(4.5)$$
$$(4.6)$$

116 ©
which maps into (4.3) with

$$s_{t}=\frac{1}{1-\rho}(\theta-\tilde{\theta}_{t}).$$
$$(4.7)$$
(✓  ˜✓t). (4.7)
Both stories could explain variation in price-dividend ratio. Furthermore, both stories imply that the price-dividend ratio should predict future stock market returns, but for very di↵erent reasons: In the first story, a high price-dividend ratio indicates that investors are too optimistic about future cash flows and the low return that follows subsequently is a consequence of the correction of this overvaluation. In the second story, a high price-dividend ratio indicates that investors, possibly for entirely rational reasons, are happy to take on stock market risk for a relatively small risk premium.

The low subsequent return that follows afterwards is a consequence of this small risk premium priced into stocks.

By looking only at data of valuation ratios and returns, we cannot tell these stories apart. But data on investor expectations can help.

The first story would say that a high price-dividend ratio should be associated with high expectations of future cash flow growth that are not matched, on average, by actual strong future cash flow growth, as the sentiment-driven forecast was overly optimistic.

In this story, investors' expectations of the risk premium that they expect to earn from stocks should not vary with the level of the price-dividend ratio.

In the second story, it's exactly the opposite. In this case, there shouldn't be any systematic mismatch between investors' expectations of cash flow growth and subsequent actual realizations of cash flow growth. Instead, investors' expectations of the equity risk premium relative to risk free rates should vary with the price-dividend ratio. If they price stocks at high valuation levels because they are happy with a low risk premium, then they should be aware that they will earn a low risk premium in the future, on average.

## 4.1 EXPECTATIONS DATA

To shed light on the source of sentiment, we now look at expectations data. What do participants in the market expect regarding future cash flows and future returns, and how do these expectations relate to valuation ratios such as the price-dividend ratio?

![3_image_0.png](3_image_0.png)

## 4.1.1 CASH FLOW EXPECTATIONS

If the cash flow growth sentiment story is a substantial part of what's driving variation in the price-dividend ratio over time, we should see a strong relationship between the price-dividend ratio and cash flow growth expectations of investors.

We start by looking at sell-side equity analysts earnings forecasts. Ideally, we would want to look at the cash flow expectations of investors directly, but such data does not exist. But analysts' forecasts do seem to influence investors. There is also a large literature documenting that stock prices respond to analysts' opinions when analysts release their forecasts.

There is also a large literature documenting that sell-side analysts are too optimistic on average. But we focus here on changes over time in their degree of optimism so that they are too optimistic on average is not a problem.

Figure 4.1 shows long-term expected real earnings growth rates for the aggregate stock market based on data from I/B/E/S, expressed as annualized growth rate. Longterm means that these are average growth rates expected over a horizon of about 3 to 5 years in the future.

118 ©
The I/B/E/S database has forecasts of long-term growth of earnings per share (EPS)
from multiple analysts for each stock. I start the aggregation into stock market level expectations by taking the median forecast for each stock each month. To form a market-level forecast, I calculate a weighted average expected growth rate of all stocks each month, using the earnings forecasted for the current year as weights. In this way, we get the implied forecasted long-term growth rate of aggregate earnings of stocks in the market portfolio. Finally, to get the growth rate forecast in real terms, I subtract a long-term inflation forecast obtained from the Survey of Professional forecasters.

As the figure shows, the forecasted long-term earnings growth align quite well with movements in the stock market's log price-dividend ratio. When the log P/D ratio went up by one log point from 1985 to 1999, which means that P/D more than doubled, the long-term real earnings growth rate expected by analysts doubled. During the financial crisis in 2008, the log P/D ratio fell to low levels and so did analysts long-term real growth expectations. The subsequent fluctuations in log P/D are also matched by movements in real growth rate expectations in the same direction.

So to the extent that time-variation in analyst expectations is a good proxy for timevariation in investor expectations, it looks like a large part of P/D movements during the past four decades can be explained by changing expectations about future long-term real growth. Perhaps changes in risk aversion or changes in perceptions of risk are not needed to explain why the stock market cycles through boom and bust periods with very di↵erent P/D ratio.

Now there are two possibilities. First, analysts' expectations could be good forecasts of future earnings growth and future growth in payouts, i.e., dividends and repurchases
(the cash flows that ultimately matter to investors). In this case, we should see that forecasts of high earnings growth are, on average, followed by actual high earnings growth. Second, it could be that analysts' varying optimism and pessimism are just fluctuations in sentiment that do not really a have a fundamental justification. If so, we should see that forecasts of high earnings growth are, on average, followed by low stock market returns, as investors eventually realize that the earlier forecasts were too optimistic.

Figure 4.2 presents some evidence on this question. The x-axis in these plots shows the analyst growth rate expectation in a given period. In the top panel, the y-axis shows the realized real growth in earnings during the five years following the quarter in which the earnings forecast was made. The bottom panel shows the average realized stock market return in excess of T-bill returns during the five years following the quarter in which the earnings forecast was made.

The takeaway from the plots is quite clear. There is no clear positive relationship

![5_image_0.png](5_image_0.png)

![5_image_1.png](5_image_1.png)

![5_image_2.png](5_image_2.png)

Subsequent 5y log real earnings growth
120 ©
between analyst forecasts and future realized real earnings growth in the top panel, but there is a clear negative relationship between analyst forecasts and future excess returns in the bottom panel. This is consistent with (i) analyst earnings long-term growth forecasts proxying for investor long-term cash flow growth expectations; (ii)
these forecasts are too optimistic in some times, too pessimistic in others, which shows up in a price correction in subsequent returns.

On caveat though is that the statistical confidence in these relationships is not great.

I used almost 40 years of data for this analysis, but since I analyze five-year averages of future earnings growth and excess returns, there are really only 8 independent observations of these 5-year averages in the data set. Quarterly observations of 5-year moving averages of future earnings growth and returns are highly autocorrelated because these 5-year windows largely overlap. Because of this autocorrelation, a regression of quarterly observations of these 5-year moving averages on analyst forecasts in the quarter prior to the 5-year measurement window requires some adjustment in the calculation of standard errors and t-statistics. Using the ordinary least squares regression outputs for standard errors and t-statistics would produce wildly inflated t-statistics, because these outputs are calculated under the assumption that the autocorrelation of regression residuals is zero—which they are not, in this case.

There are techniques for adjusting standard errors and t-statistics for autocorrelation1. If I apply these, fitted to the data in the bottom panel of Figure 4.2, I get the following coecient estimates (and t-statistics in parentheses): The t-statistic of 2.03

| Intercept   | Slope   | adj. R2   |
|-------------|---------|-----------|
| 0.23        | -1.67   | 18%       |
| (3.01)      | (-2.03) |           |

with absolute value bigger than 1.96 suggests that the negative relation between analyst long-term real growth forecasts and future real returns is unlikely to be due to chance.

But it's not far away from 1.96, so there is still substantial statistical uncertainty about the magnitude of the e↵etc. The coecient estimate of -1.67 suggests a large e↵etc:
A one percentage point higher expectation of annualized long-term real growth is associated with 1.67 percentage points lower annualized excess returns over the next five years.

To summarize, over these roughly 40 years, analyst forecasts of long-term earnings growth explain price-dividend ratio movements well, but these growth expectations have largely proven to be wrong in the long run, which led to price corrections. To the extent that analyst forecasts are a good proxy for investor expectations of future earnings, this

![7_image_0.png](7_image_0.png)

finding supports the notion of investor sentiment as time-varying optimism/pessimism about future cash flow growth.

## 4.1.2 RETURN EXPECTATIONS

But are analysts earnings growth expectations a reasonable proxy for investor expectations of stock market cash flow growth? Unfortunately, there are currently no surveys of cash flow growth expectations of professional and retail investors with suciently long time series to answer this question. But surveys of return expectations of di↵erent investor groups (or forecasters and decision makers close to market participants) do exist.

These data allow us to take a look at the second possible story that could explain variation over time in the price-dividend ratio: time-varying risk perceptions or time-varying risk aversion.

Under the time-varying risk perception or time-varying risk aversion story, we should see that expectations of stock market returns are varying strongly with the price-dividend ratio. Specifically, when the price-dividend ratio is high, and hence perceived risk is low or risk aversion is low, return expectations should be low and vice versa.

122 ©
Figure 4.3 shows the return expectations of individual investors2, corporate chief financial ocers (CFOs)3, and professional forecasters4 working in the financial industry
(right y-axis). The numbers are averaged each period among all the respondents in each survey. So just like for equity analysts in our earlier analysis, we are looking at the average opinion of forecasters, but now averages for di↵erent types of forecasters. The plot shows the series of expected one-year return in excess of the one-year yield on U.S.

Treasury securities at the time of the survey. For comparison, the plot also shows the log price-dividend ratio (left y-axis).

If it was true that times of high price-dividend ratio are times of low risk aversion or low perceived risk (rather than high cash flow growth expectations), then we should see that the excess return expectations are systematically lower in these periods. In other words, the expected excess returns shown in the figure should be inversely related to the log P/D ratio.

Eyeballing the figure, neither individual investor nor CFO expectations seem to have much relation to the log P/D ratio. Only the professional forecasters' series in some period seems to move inversely with log P/D. For example, when the log P/D ratio fell in the recessions around 2001 and 2008, professional forecasters sharply raised their excess return expectations. But then there are other periods such as from 2003 to 2007 when their excess return expectations fell along with a fall in the log P/D ratio, so overall it's not clear whether there really is an inverse relationship.

To investigate this more carefully, I run regressions of the excess return expectations series on the log P/D ratio measured at the end of the quarter before the quarter in which the return expectation is measured in the survey. I also include the excess return on the stock market index over the past year as an explanatory variable to check whether the respondents in these surveys have a tendency to form expectations by extrapolating recent returns, or by taking a contrarian view expecting a reversal of recent returns.

Table 4.1 presents the results, with t-statistics shown in parentheses. In line with our visual impression from the figure, none of the three groups has a negative coecient on the log P/D. Instead, for all three, the estimated coecient is positive, but the di↵erence to zero is not statistically significant. The three groups are strikingly similar in their lack of sensitivity to the log P/D ratio.

| Const.                   | Log P/D   | Lagged 1Y Return   | R2     |       |
|--------------------------|-----------|--------------------|--------|-------|
| Professional Forecasters | -0.001    | 0.020              | -0.201 | 0.209 |
| (-0.017)                 | (0.782)   | (-4.591)           |        |       |
| Retail investors         | 0.050     | 0.003              | 0.025  | 0.039 |
| (2.393)                  | (0.429)   | (2.428)            |        |       |
| CFOs                     | -0.010    | 0.015              | 0.006  | 0.029 |
| (-0.381)                 | (1.821)   | (0.526)            |        |       |

In contrast, the estimated coecients for the one-year lagged excess return are very di↵erent. Professional forecasters are strongly contrarian with respect to lagged one-year returns, individual investors are extrapolative, and CFOs are roughly neutral. For example, if the excess return in the last year is higher by 10 percentage points, professional forecasters expect a 2 percentage point lower excess return in the next year. In the same situation, individual investors expect 0.25 percentage points higher returns.

Overall, the evidence on return expectations does not provide much support for the idea that movements in the stock market's price-dividend ratio are due to changes in investors' risk aversion or risk perception. It's not the case that investors systematically view periods of high price-dividend ratios as periods when expected excess returns are low. Therefore, they must view the elevated price levels in these times as justified by their expectations of future cash flows.

## 4.2 WHAT DRIVES INVESTORS' TIME-VARYING GROWTH EXPECTATIONS?

If time-varying optimism/pessimism about future cash flow growth is the driving force of investor sentiment, what gives rise to this time-variation? What are the conditions that are fertile for excessive optimism? What are the conditions that tend to lead to excessive pessimism? This is an active area of research and the subject of much debate among practitioners. I can only o↵er a few hints at what may be going on, not a firm, well-established conclusion.

Various studies of how investors and forecasters come up with expectations of asset returns and macroeconomic variables have found a common regularity. Investors and forecasters tend to be influenced relatively strongly by recently experienced data. For cash flow forecasts, this means that a string of high cash flow growth realizations during an economic boom leads investors and forecasters to be overly optimistic about future cash flow growth. Conversely, a sequence of disappointing cash flow growth realizations in a persistent downturn leads them to be overly pessimistic.

A simple summary of past experienced payout growth history (including dividends and repurchases) that captures this well is the following weighted average

$$(1-k)\left(\Delta d_{t}+k\Delta d_{t-1}+k^{2}\Delta d_{t-2}+k^{3}\Delta d_{t-3}+\ldots\right)$$
$$(4.8)$$

with k = 0.982, where the dividend growth observations are quarterly and measured in real terms.5. I label this weighted average as *experienced payout growth* because it is meant to summarize investors' memory of recent payout growth history. I set the weight parameter k to a value that has worked well for summarizing experienced data and using it to explain expectations data in a number of settings, including inflation expectations of households and of members of the Federal Open Market Committee that sets monetary policy in the U.S., as well as asset allocation decisions (stocks vs. bonds) of individual investors.6 Importantly, the value of k was not picked to make the resulting series of experienced payout growth fit well the analyst forecasts or price-dividend ratio series that we will now look at. The estimate of k was obtained by relating expectations to experienced data in completely di↵erent settings.

Figure 4.4 shows the resulting time series of the experienced payout growth in comparison with the analyst long-term earnings growth forecast series. The series are clearly positively correlated, although the correlation is of course not perfect. Times of high experienced payout growth such as the late 1990s, or the last couple of years in the data, are also years in which analysts are optimistic. In contrast, in the depth of the financial crisis around 2009 both experienced payout growth was low and analysts were pessimistic.

Figure 4.5 compares the payout growth series to the log P/D series. It is apparent that there is similar cyclicality in both series, although with some big deviations, especially in the years immediately before the financial crisis and in the early 1990s.

![11_image_0.png](11_image_0.png)

![11_image_1.png](11_image_1.png)

126 ©

![12_image_0.png](12_image_0.png)

a series of the negative of subsequent 5-year excess returns. This means that in every quarter t, the figure shows the experienced payout growth series that uses data up to quarter t and then the negative of the average excess returns during the subsequent quarters t+1 to t+20. I take the negative of these future average excess returns because high experienced payout growth should mean positive sentiment and hence low future returns. If I take the negative of the future returns, the series should then be positively correlated (which is visually easier to see than a negative correlation). As the figure shows, the two series are quite highly positively correlated. Hence, high experienced payout growth forecasts low future excess returns.

Let's also check whether we can forecast next quarter's stock market returns with the experienced payout growth series. Table 4.2 reruns the same regressions that we ran in the last lecture, but now with experienced payout growth instead of log P/D
as the predictor of t + 1 returns. The slope coecient b captures the strength of the predictive relationship. As the table shows, compared with the log P/D regressions from the last lecture, the predictive relationship is actually a little stronger than for the log P/D ratio: the t-statistics are a little higher and the R2 are somewhat higher as well.

Focusing on the regressions with excess returns as dependent variable in Panel C, a one standard deviation rise in experienced payout growth, which is 0.33 percentage points, is associated with next quarter excess returns being lower by 5.967 ⇥ 0.33 = 1.97

| a                                               | b         | R2       |
|-------------------------------------------------|-----------|----------|
| Panel A: Log returns Estimates 0.066            | -5.664    | 0.028    |
| t-statistic                                     | (4.900)   | (-3.474) |
| Panel B: Simple returns Estimates -0.927 -5.755 | 0.026     |          |
| t-statistic                                     | (-64.692) | (-3.337) |
| Panel C: Excess returns Estimates 0.067 -5.967  | 0.028     |          |
| t-statistic                                     | (4.632)   | (-3.448) |

percentage points (the quarterly excess returns are not annualized, so these are big numbers).

Overall, these results are broadly in line with the notion that investor sentiment about future cash flow growth becomes more positive when investors have experienced a string of several years of high real payout growth.

## 4.3 FUND FLOWS AS SENTIMENT INDICATOR

A di↵erent approach to understanding investor sentiment focuses on who is buying and selling. For example, a popular view in the finance industry is that retail investors are subject to particularly strong time-variation in sentiment for stocks with little connection to stock market fundamentals. If this is true, we should be able to use the quantity of stocks demanded by retail investors as a sentiment indicator. If retail investors' changing demand for stocks has price impact, we should then see a connection between retail investor demand for stocks and valuation levels in the stock market. Under the
(arguably reasonable) assumption that retail investor demand is unlikely to be driven by superior information about stock market fundamentals, a connection between retail investor demand and valuation levels would give us further reason to suspect that timevariation in stock market valuation ratios reflects sentiment-driven deviations of stock market valuations from fundamentals.

Of course, a finding of a positive correlation between retail investor demand for stocks and valuation levels would not prove causation. For example, it could be that high valuation levels attract retail investor demand for stocks so that causality runs in the

![14_image_0.png](14_image_0.png)

opposite direction. But it would be rather surprising if there was no price impact of retail investor demand. Retail investor flows in and out of the market, including flows through mutual funds and ETFs, are not trivial relative to the overall market capitalization of the stock market. There is little reason to think that professional investors would perfectly accommodate these demands by altering their portfolios without demanding price concessions, i.e., without retail investor flows having some price impact.7 Data on total aggregate retail investor stock holdings is not available. For this reason, I focus here on retail investor flows in and out of mutual funds (MF) and exchange-traded funds (ETF). To get a sense of the magnitudes of retail investor holdings through these intermediated channels, Figure 4.7 shows the time-series of aggregate assets of U.S. MF and ETF from the U.S. Financial Accounts. For comparison, I also plot the aggregate market capitalization of all stocks listed in the U.S. In the fourth quarter of 2021, mutual funds held close to $30 trillion in assets, and this was about half of the total stock market capitalization of $60 trillion.

Not all of the mutual funds included in these aggregate statistics in this figure are

domestic U.S. equity funds. At the end of 2021Q4, about $5.5 trillion was accounted for by bond funds and about $4 trillion by international funds. The international funds may also hold a portion in U.S. stocks, though. Overall, this suggests that MF and ETF assets in U.S. domestic equity account for around 3/4 of the aggregate MF + ETF
assets shown in Figure 4.7.

The majority of these funds' shares are held by retail investors, including holdings through self-directed retirement accounts like 401k accounts and IRAs. Moreover, most of these equity funds are ones where the fund manager may be able to pick which stocks to buy, but does not have discretion to invest in other asset than equity (except for a small holding of cash). In summary, retail investors control a substantial share of the stock market through these mutual funds and ETF holdings.

Figure 4.8 shows how flows into MF and ETF correlate with the stock market's log P/D ratio and recent stock market returns. I calculate flow as the monthly net dollar amount of money flowing into or out from equity MF and ETF combined. To make the numbers comparable across time, I divide each monthly dollar flow by the aggregate stock market capitalization at the end of the previous month.

To relate flow to the log P/D ratio in Figure 4.8a, I cumulate the monthly flow over one-year moving windows, i.e., at each date on the chart, the blue line shows the sum of flow during the 12 months leading up to this date. The numbers are expressed in percent, so, for example, in the early 2000s, the cumulated inflow over the previous 12 months amounted to about 2 percent of the stock market's market capitalization.

As the figure shows the one-year cumulated flow matches well the low-frequency movements in the log P/D ratio. For example, the stock price boom in the 1990s was accompanied by a large cumulative inflow into equity funds. The fall in the log P/D ratio in the financial crisis 2008/09 also coincided with very low equity fund flows. According to this measure, retail investor sentiment for stock market investing is pro-cyclical: eager to invest in equities in booms, pulling out of the stock market in downturns.

Figure 4.8b shows that at a higher frequency, monthly flows (not cumulated) correlate positively with returns on the stock market index over the previous 12 months. There seems to be an extrapolative tendency of retail investors: when recent market returns are high, they seem to be more optimistic about the prospects of stock market investing.

This ties in well with the evidence on individual investor excess return expectations in 4.1: Recall that we found that individual investors excess return expectations are positively related to lagged 12-month returns.

The strong positive connection between fund flows and lagged 12-month returns is a hint that retail investor fund flows are not driven by superior information. In historical data, there is no evidence that lagged 12-month predict future stock market excess

![16_image_0.png](16_image_0.png)

131 ©
returns.8 In addition, the positive association of fund flows and log P/D points to market-timing in the wrong direction. Recall that log P/D is negatively associated with future excess returns. MF and ETF therefore receive inflows at times when future stock market excess returns are low.

Table 4.3: Relation of equity mutual fund and ETF flows to price-dividend ratio and past returns

| Const.   | Log P/D   | Lagged 1Y Return   | R2   |     |
|----------|-----------|--------------------|------|-----|
| (1)      | -0.68     | 0.22               | 25%  |     |
| (-4.73)  | (4.83)    |                    |      |     |
| (2)      | -0.60     | 0.19               | 0.14 | 29% |
| (-4.76)  | (4.75)    | (2.26)             |      |     |

Table 4.3 presents some statistical tests of the relationship between flows, log P/D,
and lagged 12-month returns. The table shows the results of a regression of monthly flows (in percent) on the log P/D at the end of the previous month and stock market returns during the previous 12 months. Since flows are strongly autocorrelated, I adjust the t-statistics for autocorrelation.9.

The results confirm the impression from the figures. Both the log P/D ratio and lagged returns are positively related to equity MF and ETF flows. For example, the second regression with both log P/D ratio and lagged returns as explanatory variables shows that a 10 percentage point higher past return over the past 12 months (less than one standard deviation) is associated with about 10 ⇥ 0.14 = 1.4 percentage points (of aggregate stock market cap) higher equity fund inflow in the next month (which is a bit more than one standard deviations of the monthly flows). The R2 of 29% shows that log P/D and lagged past returns together explain a substantial portion of monthly flows.

Broadly, these facts are consistent with (although not proof of) the view that retail investor sentiment plays a role in driving the cycles in valuation levels that we see in valuation ratios like the P/D ratio.

Now, if equity MF and ETF flows are a good retail investor sentiment indicator, and if this sentiment has price impact, one should be able to use the flows to predict returns.

More precisely, if the e↵ects of sentiment on stock prices accumulate, then measures of cumulative flows over longer periods of time should predict stock market excess returns.

Unfortunately, the data series of flows is rather short.

If we don't have enough data in the time series to get reliable statistical results, we can try to look for cross-sectional di↵erences between di↵erent assets to get more statistical confidence that flows really predict returns negatively. If funds invest in di↵erent assets and get di↵erent flows, do the assets held by these funds perform di↵erently afterwards?

Active MF are not a good set of funds to conduct such an exercise because in active MF the fund manager has discretion which assets to buy if flows come in. Flows do not get mechanically invested in a pre-defined set of assets. Even if the manager is restricted to invest within a specific asset class, the manager of an active fund may still be able to find assets that are fairly valued or undervalued within an asset class and avoid overvalued assets. Conversely, if returns are low following inflows into an active fund, this could just be the consequence of the portfolio manager having made poor investment decisions.

Index MF and most ETFs are therefore better suited for this sort of exercise. Index MF invest flows mechanically in the assets of an index. Many ETFs do so, too. And those ETFs that are not indexing and have an active policy often still follow mechanical rules, just not by strictly replicating an existing index.

Flows di↵er substantially across funds. One reason why flows di↵er across funds is that flows are sensitive to recent fund performance. This is the cross-sectional equivalent of the time-series relationship between recent stock market returns and aggregate fund flows that we discussed above.

Figure 4.9 shows results from a study that looked at how flows depend on relative performance in the prior month. Within three classes (active MF, index MF, ETF), at the end of month t funds are ranked by their return in month t and grouped into 20 groups. The figure shows the flows the funds in each group receive on average in month t + 1. For all three classes of funds, there is a positive relationship between lagged performance and flows.

The positive relationship is particularly strong for ETF (blue line in the chart). One one hand, this makes sense. ETFs are designed for investors who want to be able to enter and exit a fund without incurring a lot of transaction costs. On the other hand, unlike for active MF, it's clear that this positive relationship between lagged performance and flows cannot be explained by investors seeking to allocate to the most skilled portfolio managers. These ETFs follow passive indexing strategies or mechanical rebalancing rules. There is no role for skilled, discretionary active management in these ETFs. So it must be that recently high returns induce investors to believe that assets mechanically chosen by the ETF are attractive assets to invest in. In other words,

Figure 2

![19_image_0.png](19_image_0.png)

The flow‐performance relationship
the positive performance-flow relationship we see in this figure captures a positive relationship between recent ETF returns and investor sentiment for the assets held by the ETF.

So how do the ETFs that receive high flows perform in the following months? Figure 4.10 shows that flows are negatively related to future performance in the cross-section of ETFs. In the study that this figure is taken from, the authors sort all ETFs each month into 10 groups based on the prior month's flow. Then they calculate value-weighted returns (i.e., returns weighted by end of prior month total market capitalization of each ETF) during the following 12 months. They then form a long-short portfolio that takes a long position in ETFs in the lowest-flow group and a short position in the ETFs in the highest-flow group. Figure 4.10 shows the cumulative return of this long-short portfolio in the 12 months following portfolio formation. Over the first five months after portfolio formation, the portfolio accumulates positive returns. The error bars in the figure show two-standard-error ranges and so these positive portfolio returns are di↵erent from zero at conventional levels of statistical significance. This means that ETFs with recent strong inflows perform poorly in the future while ETFs with recent strong outflows perform well in the future, i.e., a negative relationship between flows and future performance.

Panel B: Flow ‐performance relation for funds split into deciles This figure splits active mutual funds, index mutual funds, and exchange‐traded funds (ETFs) into groups based on the monthly excess return of the fund over the CRSP value weighted index. For each group we then compute the average flow in the next month.

134 ©
Cumulative Return
-2.0% -1.5% -1.0%
-0.5%
0.0% 0.5%
1.0%
1.5% 2.0%
2.5%
0 1 2 3 4 5 6 7 8 9 10 11 12 Figure 4.10: Returns to a portfolio long in ETFs with low lagged flow and short in ETFs with high lagged flow
(a) Mature ETFs: *ET F Flow* Source: Brown, D.C., Davies, S.W. and Ringgenberg, M.C., 2021. ETF arbitrage, nonfundamental demand, and return predictability. Review of Finance, 25(4), pp.937-972.

These results from the cross-section of ETFs provide some further support to the notion that MF and ETF flows can be a useful (retail) investor sentiment indicator.

Cumulative Return
-8%
-6% -4%
-2%
0%
2% 4%
6%
8%
10% 12%
0 1 2 3 4 5 6 7 8 9 10 11 12

![20_image_0.png](20_image_0.png)

## 4.3.1 USING ARTIFICIAL INTELLIGENCE TO EXTRACT SENTIMENT FROM TEXTUAL INFORMATION

-15% -10%
-5%
0% 5%
10%

## 15% 20%

25%
30%
Cumulative Return Another approach to measuring sentiment is to extract it from textual information that can be found in newspaper articles, corporate filings and earnings call transcripts, or other media sources. In the past, such sentiment measures relied on relatively simple approaches such as counting the number of words in news articles about the stock market or the economy that express a positive or optimistic opinion and those that express a negative or pessimistic opinion.

The recent breakthroughs in artificial intelligence with large language models (LLM)
such as those underlying Open AI's ChatGPT open up opportunities to push these sorts 0 1 2 3 4 5 6 7 8 9 10 11 12 135 ©
Months Since Portfolio Formation Here is a piece of news: "%s" Do you think this news will increase or decrease %s? Write your answer as:
{increase/decrease/uncertain}:
{confidence (0-1)}:
{magnitude of increase/decrease (0-1)}:
{explanation (less than 25 words)}
Note. Reports the prompt format for queries made to GPT. "%s" indicates where in the prompt the headline and target text are inserted.

Figure 4.11: Prompting GPT-3.5 to generate economic expectations Source: Bybee, J.L., 2023, The Ghost in the Machine: Generating Beliefs with Large Language Models, working paper, Yale School of Management.

of analyses to a much more sophisticated level. LLMs can potentially "understand" and interpret textual information in a much deeper way than previous approaches could.

7 One idea is to use LLMs to approximate how humans' expectations about the economy overall, or the stock market specifically, would respond to news. Take some news article. Would reading the article make a typical human more optimistic or more pessimistic? The idea is not that the LLM could become a super-human forecaster of the future. Instead, the idea is that the LLM, by being trained on a huge corpus of text written by humans, may have learned to approximate how humans interpret news.

Figure 4.12 shows an example of how to prompt OpenAI's GPT-3.5 to generate economic expectations based on news article headlines. The first %s is a placeholder for the news headline that is provided to the GPT. To implement the prompt, one would replace it with the text of an actual news article headline. The second %s below is a place holder for the specific type of economic expectation that the GPT is supposed to generate. For example, this could be "GDP growth."
After prompting the GPT with a large number of archived article headlines from various months in the past, one can then summarize the overall sentiment each month by taking the proportion of articles to which GPT responds with "increase" of GDP
growth minus the proportion of articles to which GPT responds with "decrease" of GDP growth. One can do the same thing for other macroeconomic indicators such as industrial production growth, employment, stock market index returns, etc.

Figure 4.12 shows an aggregate measure of economic sentiment that averages over the 136 ©

of disconnect from rational expectations, and as such, make reasonable benchmarks for my measure of economic sentiment.

![22_image_4.png](22_image_4.png)

Figure 13: Time Series of Sentiment against Benchmarks

![22_image_1.png](22_image_1.png)

CAPE vs. Sentiment // Corr: 0.54

![22_image_2.png](22_image_2.png)

BW vs. Sentiment // Corr: 0.22

![22_image_3.png](22_image_3.png)

1920 1940 1960 1980 2000 2020

![22_image_6.png](22_image_6.png)

BW vs. Sentiment // Corr: 0.22

![22_image_5.png](22_image_5.png)

![22_image_7.png](22_image_7.png)

Figure 4.12: Economic sentiment measure extracted from archived New York Times articles and comparison with the cyclically-adjusted price-to-earnings ratio Note. The first panel reports the EAR sentiment measure (the blue line) overlaid with CAPE (the dashed red line). The second panel reports the EAR sentiment measure (the blue line) overlaid with the Baker and Wurgler (2007) sentiment measure (the dashed red line).

Source: Bybee, J.L., 2023, The Ghost in the Machine: Generating Beliefs with Large Language Models, working paper, Yale School of Management.

economic expectations measures for individual macroeconomic indicators every month
(blue line). It also shows the cyclically-adjusted price-to-earnings ratio that we looked at in the last lecture. There is clearly a strong positive correlation between the two series.

This is quite remarkable since the construction of the economic sentiment measure did not use any direct information about the price level of the stock market. Even so, the sentiment measure matches quite well the depressed value of the stock market relative to earnings in the late 1970s, the boom in the late 1990s, and the drop during the financial crisis in 2007/08, for example.

Wurgler (2007) sentiment measure. The first panel shows the EAR measure overlaid with 1920 1940 1960 1980 2000 2020 Date CAPE - the two series have a correlation of 0.54 over the full sample. Both CAPE and Note. The first panel reports the EAR sentiment measure (the blue line) overlaid with CAPE (the dashed red line). The second panel reports the EAR sentiment measure (the blue line) overlaid with the Baker and Wurgler (2007) sentiment measure (the dashed red line).

31 Figure 13 overlays my economic sentiment measure with both CAPE and the Baker and Wurgler (2007) sentiment measure. The first panel shows the EAR measure overlaid with CAPE - the two series have a correlation of 0.54 over the full sample. Both CAPE and This example of sentiment extraction using LLMs is surely just a first cut of what can be done in relatively simple ways by using publicly available pre-trained versions of LLMs. A lot of new advances seem likely in this area in the coming years.

31

## 4.4 BUBBLY ASSETS

Occasionally assets trade at prices that seem far removed from any notion of fundamental value. Meme stocks like GameStop and AMC may fall into this category. In early 2021, prices for these stocks exploded. See Figure 4.13. Previously almost worthless stocks became stocks with huge multi-billion dollar market capitalization.

The notion of sentiment we have considered so far—expectations about cash flows, and, possibly, time-varying risk aversion and risk perceptions—may not help much to explain why valuations of these stocks reached stratospheric levels. We now consider

![22_image_0.png](22_image_0.png)

Market Summary > GameStop Corp

## 14.51 USD

+10.53 (264.57%) ↑ past 5 years Closed: Jan 19, 7:59 PM EST - Disclaimer After hours 14.51 0.00 (0.00%)
1D
5D
1M
^ 6M
^ Max
^ 5Y

![23_image_0.png](23_image_0.png)

Market Summary > AMC Entertainment Holdings Inc

## 4.51 USD

-50.03 (-91.73%) ✦ past 5 years Closed: Jan 19, 7:59 PM EST - Disclaimer After hours 4.51 0.00 (0.00%)
- Follow 1D
5D
1M
1 6M
^ 5Y
✔ Max

![23_image_1.png](23_image_1.png)

Figure 4.13: Prices of meme stocks

- Follow c Stefan Nagel 2024 the possibility that investors may be willing to pay a high price for an asset today even if they are not convinced, based on their own beliefs, that cash flow expectations can justify this high price. Instead, investors' motivation for paying a high price in these situations may be that they expect that they can resell the asset to an investor in the future who is willing to pay an even higher price. We will explore how we can modify our valuation models to capture such cases.

Recall (3.18) from last lecture:

$$(4.9)$$
$$v_{t}=c+\Delta d_{t+1}-r_{t+1}+\rho v_{t+1}$$

vt = c + dt+1  rt+1 + ⇢vt+1 (4.9)
Iterating forward on this equation, imposing the transversality condition limT!1 ⇢T +1vT +1 =
0 and taking time-t conditional expectations gave us the present-value relation (4.1).

Assuming additionally that investors price the asset to earn, in expectation, a constant required rate of return ✓, (4.1) becomes

$$v_{t}=\frac{c-\theta}{1-\rho}+\sum_{j=1}^{\infty}\rho^{j-1}\,\mathbb{E}_{t}[\Delta d_{t+j}].\tag{4.10}$$

where time-variation in the log price-dividend ratio vt is linked to time-varying expectations of future dividend growth.

There are two points that we should revisit now. First, by iterating forward on
(4.9) and then taking expectations, we assumed that current (i.e., time-t) investors' expectations of returns and cash flows at all horizons, all the way to infinity, pin down the value of the asset. This e↵ectively assumes that time-t investors value the asset as if they are planning to hold the asset forever. It's not necessarily consistent with current investors having the view that they will resell the asset at some point in the future to di↵erent investors—unless one is willing to assume that these di↵erent investors that they will eventually resell to have the same beliefs about stu↵ in the future that the current investors have. Second, we should have another look at the assumption of imposing the transversality condition.

## 4.4.1 SPECULATION ON SHORT-TERM CAPITAL GAINS

On the first issue, let's explore a di↵erent approach now where we first take expectations, then iterate. So take expectations of (4.9):

$$v_{t}=c+\mathbb{E}_{t}^{A}[\Delta d_{t+1}]-\theta+\rho\,\mathbb{E}_{t}^{A}[v_{t+1}].\tag{4.11}$$

I labeled these expectations with superscript A to denote that they reflect the expectations of investor group A who are pricing the asset at time t. And ✓ is the expected

 $\text{(C)Stefan Nagel}2024$.
139 ©
return that investors in group A require for holding the asset for one period. At time t + 1 there may be a (partly) di↵erent group of investors pricing the assets. For example, some new investors may have entered the market. Let's label the investors that are setting the price at t + 1 with B. For simplicity, let's assume that A and B investors, and all investors periods farther in the future always demand the same expected return
✓. The same valuation equation as (4.11) but at time t + 1 then gives

$$v_{t+1}=c+\mathbb{E}_{t+1}^{B}[\Delta d_{t+2}]-\theta+\rho\,\mathbb{E}_{t+1}^{B}[v_{t+2}]$$
$$(4.12)$$
$$_{\textrm{-}1}[\Delta d_{t+2}]-(1+\rho)t$$

Substituting into (4.11),
vt = c + EAt [dt+1] + ⇢ EAt EBt+1[dt+2]  (1 + ⇢)✓ + ⇢2 EAt EBt+1[vt+2] (4.13)
where EAt EBt+1[.] is the expectation of investors in group A of group B's expectation one period later.

If groups A and B were the same, i.e., if it was always just group A pricing the asset in all periods (and if investors are not delusional about the properties of their own expectations in the future), the law of iterated expectations10 would imply

$$[v_{t+2}]$$
$$(4.13)$$

$$\begin{array}{c}{{\mathbb{E}_{t}^{A}\,\mathbb{E}_{t+1}^{B}[\Delta d_{t+2}]=\mathbb{E}_{t}^{A}[\Delta d_{t+2}]}}\\ {{\quad\quad\mathbb{E}_{t}^{A}\,\mathbb{E}_{t+1}^{B}[v_{t+2}]=\mathbb{E}_{t}^{A}[v_{t+2}].}}\end{array}$$

This would bring us back, after iterating forward, to our earlier valuation model (4.10)
where everything boils down to cash flow expectations of the investors pricing the asset at time t. But if the groups of investors pricing the asset at di↵erent times are not the same, and their expectations are not the same, the law of iterated expectations does not hold.

Example: Suppose investors in group A are pessimistic about dt+2, i.e., EAt [dt+2]
is low, but, at the same time, they believe that investor group B that sets prices next period will be optimistic. Then EAt EBt+1[dt+2] will be high. Therefore, group A investors may still be willing to pay a high price, or a high-price dividend ratio vt for the asset at t, despite their own pessimism about future dividend growth.

This means that the price today depends on *higher-order* beliefs: It depends on what group A at t expects group B to expect at t + 1 about dividend growth at t + 2. If we 140 ©
do one further round of iteration on (4.13), we will get expectations of group A about the expectations of group B about the expectations of group C at t + 2, and so on.

Expectations of expectations of expectations …

This analysis points to potential limitations of fundamental valuation approaches.

If investors currently holding an asset base their investment case on belief that future investors will be optimists (about cash flows, or about the beliefs of investors further in the future, etc.), and that they will be able to resell the assets profitably to these optimists, then current prices could be unanchored from fundamentals. This is also known as the "Greater Fool Theory" of investing: Buying an overvalued asset in the hope of reselling it to a "greater fool" at an even higher price in the future.

The value that A investors would be willing to pay at t if they knew that investors next period, and in all following periods, shared their own beliefs, is what we could define as fundamental value of the asset in this case. The di↵erence between the actual asset price, which is based on expectations about the price of resale to future optimists, and this fundamental value is what we could call the bubble component of the asset price.

If this is what's going on, if investors are betting on resale to "greater fools" in the future, then we should not see investors holding on to assets for a long time. They should resell once new optimists have entered the market and the price has moved up.

Trading volume therefore should be high in such situations.

Figure 4.14 shows that this is what happened when the stock price of GameStop took o↵ in early 2021. Trading volume was incredibly high. Around the price peak on January 22, 2021, almost 200 million shares changed hands in a single day. This was about three times the total number of shares outstanding of GameStop at the time!

So each existing share of GameStop changed hands several times per day, on average!

The total dollar amount of shares traded on January 22, 2021 was about $13bn. For comparison, less than 1% of outstanding Apple shares changed hands on the same day
(and somewhat less than 1% per day is a typical number for liquid stocks). And these numbers are still missing a big part of the trading activity, because there was also frantic trading going on in GameStop options, not only in the stock.

GameStop is an extreme case, but similar dynamics may be at work at other times in other assets. Links between speculative trading based on short-term capital gain expectations and trading volume appear in historical accounts of asset price bubbles throughout the centuries.11 The New York Stock Exchange set a trading volume records

![27_image_0.png](27_image_0.png)

during the stock price boom in 1928 and 1929 before the "Black Thursday" stock market crash of October 24, 1929.12 Figure 4.15 shows on prices and volume from the internet stock bubble in the late 1990s. Trading volume in this figure is show in terms of monthly turnover, which is the number of shares traded in a month divided by the number of shares outstanding. In the years after the internet appeared in the 1990s, hundreds of newly listed internet stocks appeared in US stock markets. As the figure shows, trading volume in these stocks was elevated throughout 1998 and 1999 and it reached a peak of more than 100% turnover per month. This is far less than what we saw above for GameStop, but it's still extreme relative to the typical non-internet stock which has a turnover of less than 20% per month.

What drives investors' beliefs that future resale to an optimistic investor may be possible? Some possibilities:

![28_image_0.png](28_image_0.png)

returns may forecast higher future asset demand of optimistic investors. In our analysis of retail investor return expectations above, we saw some evidence for such extrapolative tendencies.

- Entry of new investors: If recent high returns, or media attention to an asset, predictably draw in new investors—perhaps due to "fear of missing out" (FOMO)—
this may be a predictable source of higher asset demand in the future.

- Short sellers throw in the towel: Price rises generate losses for short sellers betting against an asset's price rise, which can in turn generate liquidity problems for these short sellers. These problems may force them to liquidate their short positions.

Figure 4.16 shows that this happened in dramatic fashion in the case of GameStop.

Before January 2021, short interest (i.e., how many shares were shorted by short sellers) was very high, close to 100% of shares outstanding. But when the price exploded in January 2021, short interest collapsed as short sellers closed their positions by buying back shares. This further exacerbated the price rise, because to close a short position, they have to buy back the shares that they sold short earlier.13 13To sell shares they don't own, short sellers (or their brokers) borrow shares from investors holding

![29_image_0.png](29_image_0.png)

2 / 24 Figure 4.16: GameStop short interest Source: Li, Fulin, 2022. Retail Trading and Asset Prices: The Role of Changing Social Dynamics. Working paper, University of Chicago.

These mechanisms can generate positive feedback dynamics: Normally when the price goes up with everything else (expected cash flows) unchanged, the expected return goes down. In contrast, in bubbly situations, due to such positive feedback dynamics, investors may have reasons to believe a rise in price generates higher expected returns.

## 4.4.2 PURE BUBBLES

So far we focused on a type of asset price bubble where expectations of some investors may be biased, but the expectations are still about fundamentals. If we iterate on (4.13), everything boils down to expectations about expectations about …. cash flow growth.

In some cases, though, investors are willing to pay substantial prices for assets where there may be no prospect at all of any cash flow from the asset. Cryptocurrencies are one recent example. For example, bitcoin does not pay any dividends and it will never pay any dividends. Yet people are willing to pay thousands of dollars for one bitcoin.

One possible explanation (but not the only one—we'll get to a second one soon)
is that the asset is a pure bubble. To analyze assets with zero cash flows, our earlier analysis based on the present-value identity for the price-dividend ratio obviously won't be suitable. But, to illustrate the main idea, we can work with a simpler framework.

Suppose investors are willing to hold a pure bubble asset that never pays any dividends at an expected return equal to a (constant) risk-free rate Rf. For this to make any sense, these investors must be expecting that the asset has a resale value at a later date. More precisely, it should be the case that

$$P_{t}={\frac{1}{1+R_{f}}}\mathbb{E}_{t}[P_{t+1}].$$
$$(4.14)$$

Hence, as long as investors expect a non-zero price at t + 1, the asset will have a nonzero price at t. What about expectations where Et[Pt+1]/Pt > 1 + Rf? In this case, investors at t would regard the asset as attractive. The asset's expected return then exceeds the return they require to hold the asset. As a consequence, they would bid up the price of the asset at t up to the point where price growth is equal to Rf. Conversely, if Et[Pt+1]/Pt < 1 + Rf the price at t would have to fall the point where price growth is equal to Rf, consistent with (4.14).

Iterating forward on (4.14) under the assumption that the law of iterated expectations holds, we get

$$P_{t}=\left(\frac{1}{1+R_{f}}\right)^{T}\mathbb{E}_{t}[P_{t+T}].$$
$$(4.15)$$

Now consider the limit as T! 1. For the asset to have a non-zero value at t, and hence for there to be a non-zero pure asset price bubble, investors must expect that the price in the future keeps growing each period forever at a rate equal to the risk-free rate.

If expected price growth is smaller than Rf, then we would have

$$\operatorname*{lim}_{T\to\infty}\left({\frac{1}{1+R_{f}}}\right)^{T}\mathbb{E}_{t}[P_{t+T}]=0.$$
$$(4.16)$$

This is a version of the transversality condition that we discussed earlier after (4.9). If it holds, then the value of the asset at t must be zero. So to sustain a pure bubble, there must be an expectation of future price growth that is suciently high.

Along the same lines as for the cash flow expectations we discussed above, these expectations about future price growth could also involve expectations of future expectations of other investors of future expectations … of price growth. This is then the pure bubble version of the greater fool theory.

145 ©
This analysis illustrates how an asset could fetch a price above zero even if there is no promise of any monetary payo↵ in terms of a dividend or interest payments from the asset at any point in the future. But the valuation is extremely fragile. If at any point in time doubts emerge in investors' minds whether the price growth forever can be maintained, the price will collapse.

Empirically it is dicult to tell whether any asset prices contain such a pure bubble component.

## 4.4.3 ASSETS WITH CONVENIENCE YIELD

Even for assets such as cryptocurrencies that do seem to be candidate examples for pure asset price bubbles, there may be a di↵erent explanation why they fetch prices substantially above zero. An asset may provide non-monetary intangible benefits that support its value in similar ways as dividends and interest payments do for most assets.

One example is fiat money. People are willing to hold certain amounts of paper money or deposits in low-yielding checking accounts despite the fact that the rate of return on these money holdings is smaller than the risk-free rate they could earn by investing in government treasury bills instead. They do so because holding a certain amount of balances in highly liquid form has convenience benefits: it can be used for transactions instantly. For this reason, such benefits are called a convenience yield.

Another classic example is gold. Some people are willing to store part of their wealth in gold even though gold does not pay dividends. Many owners of gold have the hope that in the case extreme crisis situations arise in the future (economically, politically)
gold will allow them to preserve their wealth and still have some purchasing power.

Converted into jewelry or decorations, gold may provide benefits of enjoyment to future owners. Just as in the case of an asset paying (monetary, tangible) dividends, the price of the asset today reflects expectations of future convenience benefits many years into the future.

For cryptocurrencies, opinions di↵er about the convenience benefits they may provide. But a list of potential benefits includes their usefulness in facilitating illicit transactions, circumventing capital controls, and, perhaps eventually, widespread use in transactions.

We should think of the convenience benefits as net benefits in real terms after subtracting the costs of storing the asset and obtaining the convenience benefits. For physical holdings of gold, the gross benefits have to be netted against the cost of safe storage.

For cryptocurrencies, costs in the form of transaction fees (e.g., Ethereum "gas fees")
and potential losses from hacking can be substantial.

We can apply our price-dividend ratio based valuation approach in (4.1) straightforwardly here with just minor modifications:

$$v_{t}=\frac{c}{1-\rho}+\sum_{j=1}^{\infty}\rho^{j-1}\,\mathbb{E}_{t}[\Delta d_{t+j}]-\sum_{j=1}^{\infty}\rho^{j-1}\,\mathbb{E}_{t}[r_{t+j}]\tag{4.17}$$

We just need to think of the dividend as the net per-period real convenience benefits of the asset. Then vt is the log price to net convenience benefits ratio and dt+j is the growth in log net convenience benefits.

I won't do this explicitly here, but one could again think of the present-value relations here in terms of expectations of future investors expectations … etc. This introduces a speculative motive: Holding an asset today may be attractive if there is reason to believe that future investors will come in with optimistic beliefs about the asset's future convenience benefits.

Getting a handle on investor expectations about future convenience benefits of gold or cryptocurrencies is dicult. It's not even clear how to measure these benefits. But even so, we can use the present-value relation above to figure out some factors that should a↵etc the valuation of these assets.

Since we think of the convenience benefits dt+j in (4.17) as real benefits, the expected returns Et[rt+j] represent expected real returns. What (4.17) tells us then is that when investors' required real returns go up, prices of assets like gold and cryptocurrencies should fall, unless it happens to be the case that expectations of future real convenience benefits go up at the same time.

Figure 4.17 presents some evidence that this mechanism for valuation changes seems highly relevant. The figure shows an index of real gold prices. I took an import price index of gold prices and converted it to real prices by dividing by the Consumer Price Index (CPI). In addition, the chart shows a series of real interest rates. The real interest rates are extracted from the prices of Treasury Inflation-Protected Securities (TIPS).

They represent long-term real interest rates over a 10-year horizon. We will talk in much more detail about how TIPS work in a few weeks. For now, just note that one can extract long-term real interest rates (or real "yields") from prices of these securities.

According to the logic of the present-value relation in (4.17), real interest rates should be inversely related to the value of gold: higher real interest rates should coincide with lower gold prices. For this reason, to facilitate a graphical comparison, I convert the real yield series as 1/(1 + real yield).

$$\operatorname{al}\,2024$$

![33_image_0.png](33_image_0.png)

As the figure shows, there is indeed a strong relationship. When real interest rates went down, such as from 2009 to 2012 or 2019 to 2021, the gold price rose. Conversely, rises in real interest rates are associated with falling gold prices. This is consistent with the logic of our present-value model above: higher real rates mean that investors are discounting future convenience benefits at a higher rate, which leads to lower valuation today.

An equivalent way of thinking about this: higher real interest rates make interestpaying assets more attractive relative to gold. Hence the gold price has to fall, so that it has a greater chance of appreciating in the future, in order to still attract demand.

Figure 4.18 shows similar dynamics at work in the price of bitcoin in recent years. The price of bitcoin in recent years also moved inversely with real interest rates. For bitcoin and other cryptocurrencies, the e↵ects of real interest rate changes may be particularly dramatic because a lot of the promised convenience benefits have not yet materialized but are expected to kick in at some point in the still somewhat distant future. The more the bulk of expected convenience benefits is tilted toward the distant future, the stronger (due to compounding) the e↵etc of real interest rate changes.

So while the wild price movements of cryptocurrencies seem dicult to understand, at least some of the factors driving the price movements can be traced to some standard 148 ©

![34_image_0.png](34_image_0.png)

economic forces. This helps evaluate how adding gold or crypto assets to a portfolio influences overall portfolio volatility. For example, we should expect substantial positive correlation of gold and crypto asset returns with the returns of bonds, especially inflationprotected bonds like TIPS.

Finally, asset supply is another important factor to consider. It may not matter much for short-run price fluctuations, but supply is important for the value in the long-run.

Imagine someone found gigantic new supplies of gold that can be mined at low cost.

Suppose this would double the supply of available gold within a few years. There is no reason why the convenience benefits that investors get in aggregate from holding gold should double as well. So the convenience benefits per ounce of gold would fall, perhaps dramatically so. As a consequence, the price per ounce of gold should fall as well. The new supply dilutes the per-ounce convenience benefits of gold.

The same logic applies to cryptocurrencies. The supply of bitcoin, for example, follows a fixed schedule and the maximum supply that can ever be created is limited.

This was done presumably precisely to prevent the dilution of its value from an everincreasing supply. But there is no limit to how many other cryptocurrencies can be created. If other cryptocurrencies grab market share and users get their convenience benefits from an increasingly broad array of cryptocurrencies, the value of each individual

currency will be diluted.

150 ©