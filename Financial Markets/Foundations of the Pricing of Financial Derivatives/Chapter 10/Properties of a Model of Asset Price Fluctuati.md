# 10.3 PROPERTIES OF A MODEL OF ASSET PRICE FLUCTUATIONS

We know that asset price fluctuations have several important characteristics. First, over. the long run, asset prices typically go up, especially in the case of a stock, which is what we mostly model. They are said to "drift." This upward movement or drift represents the return from bearing risk. The Wiener process contains no drift, but as we show later, it is easy to make it drift either upward or even downward..

Second, asset prices are random. We know that Wiener processes are random, though we cannot use the basic Wiener process for assets because different assets have different volatilities. We can, however, transform the basic Wiener process in such a way to give it any volatility we desire.

Third, it should be more difficult to forecast asset prices further into the future than. nearby. This point does not mean that asset prices are very predictable at all but that the margin of error, which is related to the variance of the future asset price, should be greater when predicting far into the future than when predicting into the near future. Imagine, for example, that the latest closing Dow Jones Industrial Average is 24,597.38. Suppose you. can choose to make a prediction of the tomorrow's closing average or the average in six. months. Which are you likely to be closer to? That answer should be obvious. There is. certainly more uncertainty further out because the uncertainty of each day accumulates.

The final property is that an asset price should never be allowed to become negative. Corporate shareholders have limited liability, so the minimum value of their shares is zero.

We briefly illustrate these properties with an exchange-traded fund that seeks to track the S&P 500 index with dividends included with ticker symbol SPY. Figure 10.1 illustrates the value of $\$100$ invested in SPY both with and without dividends. We see clearly. the important role of dividends. Further, over this period, SPY moved up significantly, on. average, whether including dividends or not. Although there is an upward drift, stocks often experience long periods of time without any substantial appreciation exhibiting the second property of randomness. Clearly, even with an ETF tracking the S&P 500 index, dividends are a significant consideration and cannot be ignored..

Figure 10.2 illustrates the notion that longer time periods have more uncertainty based on analyzing dividend adjusted prices. Panel A presents daily returns, Panel B presents

![](images/4601f25c15003e1ab13e51a4eecf2aeaefcf9cfcce49882d5fcdb36213aeb806.jpg)
SPY Normalized Price Series

![](images/7225a1eb220e2c5707bb7246c5fdcb54c10897886af5f2bd85dec93eaa4d904e.jpg)
FIGURE 10.1 20-Year History of SPY, an Exchange-Traded Fund Source: Yahoo Finance..
FIGURE 10.2  20-Year History of Holding Period Returns for Dividend Adjusted SPY
Panel A. Daily Returns

![](images/ac302f85bf7eaeb93aca15d05e0f2d18891693fd430f728d6fd28aef3ca9be3b.jpg)

Panel B. Weekly Returns Source: Yahoo Finance.

![](images/083d5eca63b2662797dace431e5c3ed56320d5ac5f2b47922bb73626baaa0ef8.jpg)

Panel C. Monthly Returns Source: Yahoo Finance.

# FIGURE 10.2 Continued

weekly returns, and Panel C presents monthly returns. The $y$ -axis is fixed to ease observing the increased variability with longer holding period. The great recession of 2008-2009 is clearly visible in each time series.

Now our objective is to build a model that has these properties.
