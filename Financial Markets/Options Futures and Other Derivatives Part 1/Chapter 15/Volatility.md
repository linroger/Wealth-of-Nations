---
tags:
  - '#arithmetic_mean'
  - '#calendar_days'
  - '#garch_model'
  - '#geometric_mean'
  - '#historical_data'
  - '#implied_volatility'
  - '#mutual_fund_returns'
  - '#stock_volatility'
  - '#trading_days'
  - '#volatility_estimation'
---
# 15.4  VOLATILITY  

The volatility, $\sigma$ , of a stock is a measure of our uncertainty about the returns provided by the stock. Stocks typically have a volatility between $15\%$ and $60\%$  

From equation (15.7), the volatility of a stock price can be defined as the standard deviation of the return provided by the stock in 1 year when the return is expressed. using continuous compounding.  

When $\Delta t$ is small, equation (15.1) shows that $\sigma^{2}\Delta t$ is approximately equal to the variance of the percentage change in the stock price in time $\Delta t.$ This means that $\sigma\sqrt{\Delta t}$ is approximately equal to the standard deviation of the percentage change in the stock price in time $\Delta t.$ Suppose that $\sigma=0.3$ , or $30\%$ , per annum and the current stock price is $\$50$ . The standard deviation of the percentage change in the stock price in 1 week is. approximately  

$$
30\times{\sqrt{\frac{1}{52}}}=4.16\%
$$  

A 1-standard-deviationmove in the stock price in 1 week is therefore $50\times0.0416=2.08$  

Uncertainty about a future stock price, as measured by its standard deviation,. increases-at least approximately-with the square root of how far ahead we are looking. For example, the standard deviation of the stock price in 4 weeks is approximately twice the standard deviation in 1 week..  

# Business Snapshot 15.1 Mutual Fund Returns Can Be Misleading  

The difference between $\mu$ and $\mu-\sigma^{2}/2$ is closely related to an issue in the reporting of mutual fund returns. Suppose that the following is a sequence of returns per annum reported by a mutual fund manager over the last five years (measured using annual compounding): $15\%$ $20\%$ $30\%$ $-20\%$ $25\%$ -.  

The arithmetic mean of the returns, calculated by taking the sum of the returns and dividing by 5, is. $14\%$ . However, an investor would actually earn less than. $14\%$ per annum by leaving the money invested in the fund for 5 years. The dollar value of $\$100$ at the end of the 5 years would be.  

$$
100\times1.15\times1.20\times1.30\times0.80\times1.25=\S179.40
$$  

By contrast, a $14\%$ return with annual compounding would give  

$$
100\times1.14^{5}=\$192.54
$$  

The return that gives. $\$170.40$ at the end of five years is $12.4\%$ . This is because.  

$$
100\times(1.124)^{5}=179.40
$$  

What average return should the fund manager report? It is tempting for the manager to make a statement such as: "The average of the returns per year that we have realized in the last 5 years is. $14\%$ " Although true, this is misleading. It is much less. misleading to say: " The average return realized by someone who invested with us for the last 5 years is $12.4\%$ per year.' In some jurisdictions, regulations require fund. managers to report returns the second way..  

This phenomenon is an example of a result that is well known in mathematics. The geometric mean of a set of numbers is always less than the arithmetic mean. In our example, the return multipliers each year are 1.15, 1.20, 1.30, 0.80, and 1.25. The arithmetic mean of these numbers is 1.140, but the geometric mean is only 1.124 and it is the geometric mean that equals 1 plus the return realized over the 5 years.  

# Estimating Volatility from Historical Data  

To estimate the volatility of a stock price empirically, the stock price is usually observed at fixed intervals of time (e.g., every day, week, or month). Define:  

$n+1$ : Number of observations $S_{i}$ : Stock price at end of ith interval, with $i=0,1,\ldots,n$ $\tau$ : Length of time interval in years  

and let  

$$
u_{i}=\mathrm{ln}\bigg({\frac{S_{i}}{S_{i-1}}}\bigg)\quad\mathrm{for}i=1,2,...,n
$$  

The usual estimate,. $s$ , of the standard deviation of the $u_{i}$ is given by.  

$$
s={\sqrt{{\frac{1}{n-1}}\sum_{i=1}^{n}(u_{i}-{\overline{{u}}})^{2}}}
$$  

or  

$$
s={\sqrt{\frac{1}{n-1}}}\sum_{i=1}^{n}u_{i}^{2}-{\frac{1}{n(n-1)}}{\bigg(}\sum_{i=1}^{n}u_{i}{\bigg)}^{2}
$$  

where $\overline{{u}}$ is the mean of the $u_{i}$  

From equation (15.2), the standard deviation of the $u_{i}$ is $\sigma\sqrt{\tau}$ . The variable $s$ is therefore an estimate of $\sigma\sqrt{\tau}$ It follows that $\sigma$ itself can be estimated as $\hat{\sigma}$ , where  

$$
\hat{\sigma}=\frac{s}{\sqrt{\tau}}
$$  

The standard error of this estimate can be shown to be approximately $\hat{\sigma}/\sqrt{2n}$  

The prices of actively traded options are not usually calculated from volatilities based on historical data. As we shall see later in this chapter, implied volatilities are used by traders. However, estimates of volatility based on historical data are used extensively in risk management. Usually risk managers set $\tau$ equal to one day. A problem that risk managers have to deal with is that volatilities tend to change through time. There are periods of high volatility and periods of low volatility. This affects the amount of data used to estimate volatility (i.e., the choice of $n$ ). If volatilities were constant, the accuracy of an estimate would increase as $n$ increased. However, data that is too old may not be relevant to current market conditions. A compromise that seems to work reasonably well is to use 90 to 180 days of data. An alternative rule of thumb is to set $n$ equal to the number of days to which the volatility is to be applied. If the estimate is to be applied over a two-year future period, two years of historical data would then be used. It is natural to look for a way of giving more weight to recent daily price movements (i.e., values of $u_{i}$ for recent time periods).An approach known as GARCH, which will be discussed in Chapter 23 does this.  

# Example 15.4  

Table 15.1 shows a possible sequence of stock prices during 21 consecutive trading days. In this case, $n=20$ , so that  

$$
\textstyle\sum_{i=1}^{n}u_{i}=0.09531\quad{\mathrm{and}}\quad\sum_{i=1}^{n}u_{i}^{2}=0.00326
$$  

and the estimate of the standard deviation of the daily return is  

$$
{\sqrt{\frac{0.00326}{19}-{\frac{0.09531^{2}}{20\times19}}}}=0.01216
$$  

or $1.216\%$ . Assuming that there are 252 trading days per year,. $\tau=1/252$ and the data give an estimate for the volatility per annum of $0.01216\sqrt{252}=0.193$ or $19.3\%$ . The standard error of this estimate is.  

$$
{\frac{0.193}{\sqrt{2\times20}}}=0.031
$$  

or $3.1\%$ per annum.  

Table 15.1 Computation of volatility.   


<html><body><table><tr><td>Day i</td><td>Closing stock price (dollars), Si</td><td>Price relative Si/Si-1</td><td>Dailyreturn u; = In(Si/Si-1)</td></tr><tr><td>0</td><td>20.00</td><td></td><td></td></tr><tr><td>1</td><td>20.10</td><td>1.00500</td><td>0.00499</td></tr><tr><td>2</td><td>19.90</td><td>0.99005</td><td>-0.01000</td></tr><tr><td>3</td><td>20.00</td><td>1.00503</td><td>0.00501</td></tr><tr><td>4</td><td>20.50</td><td>1.02500</td><td>0.02469</td></tr><tr><td>5</td><td>20.25</td><td>0.98780</td><td>-0.01227</td></tr><tr><td>6</td><td>20.90</td><td>1.03210</td><td>0.03159</td></tr><tr><td>7</td><td>20.90</td><td>1.00000</td><td>0.00000</td></tr><tr><td>8</td><td>20.90</td><td>1.00000</td><td>0.00000</td></tr><tr><td>9</td><td>20.75</td><td>0.99282</td><td>-0.00720</td></tr><tr><td>10</td><td>20.75</td><td>1.00000</td><td>0.00000</td></tr><tr><td>11</td><td>21.00</td><td>1.01205</td><td>0.01198</td></tr><tr><td>12</td><td>21.10</td><td>1.00476</td><td>0.00475</td></tr><tr><td>13</td><td>20.90</td><td>0.99052</td><td>-0.00952</td></tr><tr><td>14</td><td>20.90</td><td>1.00000</td><td>0.00000</td></tr><tr><td>15</td><td>21.25</td><td>1.01675</td><td>0.01661</td></tr><tr><td>16</td><td>21.40</td><td>1.00706</td><td>0.00703</td></tr><tr><td>17</td><td>21.40</td><td>1.00000</td><td>0.00000</td></tr><tr><td>18</td><td>21.25</td><td>0.99299</td><td>-0.00703</td></tr><tr><td>19</td><td>21.75</td><td>1.02353</td><td>0.02326</td></tr><tr><td>20</td><td>22.00</td><td>1.01149</td><td>0.01143</td></tr></table></body></html>  

The foregoing analysis assumes that the stock pays no dividends, but it can be adapted to accommodate dividend-paying stocks. The return,. $u_{i},$ during a time interval that includes an ex-dividend day is given by  

$$
u_{i}=\ln\frac{S_{i}+D}{S_{i-1}}
$$  

where $D$ is the amount of the dividend. The return in other time intervals is still  

$$
u_{i}=\ln{\frac{S_{i}}{S_{i-1}}}
$$  

However, as tax factors play a part in determining returns around an ex-dividend date, it is probably best to discard altogether data for intervals that include an ex-dividend date.  

# Trading Days vs. Calendar Days  

An important issue is whether time should be measured in calendar days or trading days when volatility parameters are being estimated and used. As shown in Business Snapshot 15.2, research shows that volatility is much higher when the exchange is open for trading than when it is closed. As a result, practitioners tend to ignore days when the exchange is closed when estimating volatility from historical data and when calculating the life of an option. The volatility per annum is calculated from the volatility per  

# Business Snapshot 15.2 What Causes Volatility?  

It is natural to assume that the volatility of a stock is caused by new information reaching the market. This new information causes people to revise their opinions about the value of the stock. The price of the stock changes and volatility results. This view of what causes volatility is not supported by research. With several years of daily stock price data, researchers can calculate:  

1. The variance of stock price returns between the close of trading on one day and the close of trading on the next day when there are no intervening nontrading days   
2. The variance of the stock price returns between the close of trading on Friday and the close of trading on Monday  

The second of these is the variance of returns over a 3-day period. The first is a variance over a 1-day period. We might reasonably expect the second variance to be three times as great as the first variance. Fama (1965), French (1980), and French and Roll (1986) show that this is not the case. These three research studies estimate the second variance to be, respectively, $22\%$ $19\%$ , and $10.7\%$ higher than the first variance.  

At this stage one might be tempted to argue that these results are explained by more. news reaching the market when the market is open for trading. But research by Roll (1984) does not support this explanation. Roll looked at the prices of orange juice. futures. By far the most important news for orange juice futures prices is news about the weather and this is equally likely to arrive at any time. When Roll did a similar analysis to that just described for stocks, he found that the second (Friday-to-Monday). variance for orange juice futures is only 1.54 times the first variance..  

The only reasonable conclusion from all this is that volatility is to a large extent caused by trading itself. (Traders usually have no difficulty accepting this conclusion!)  

trading day using the formula  

$$
\begin{array}{r}{\mathrm{Volatility}\vphantom{\mathrm{\operatorname{per}t a n n u m}}=\mathrm{\operatorname{Volatility}\vphantom{\operatorname{Volatil}}}\times\sqrt{\mathrm{\operatorname{Number~of}{t r a d i n g}~d a y s}}\vphantom{\operatorname{Volatil}}}\ {\mathrm{per~annum}\vphantom{\operatorname{per}{t r a d i n g}}}\end{array}
$$  

This is what we did in Example 15.4 when calculating volatility from the data in Table 15.1. The number of trading days in a year is usually assumed to be 252 for stocks.  

The life of an option is also usually measured using trading days rather than calendar days. It is calculated as $T$ years, where  

$$
T={\frac{\mathrm{Number~of~trading~days~until~option~maturity}}{252}}
$$  
