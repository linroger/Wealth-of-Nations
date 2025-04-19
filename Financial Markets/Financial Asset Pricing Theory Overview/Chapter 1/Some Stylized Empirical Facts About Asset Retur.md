---
tags:
  - arithmetic_average
  - asset_returns
  - empirical_facts
  - geometric_average
  - real_returns
aliases:
  - Asset Return Facts
  - Empirical Findings
key_concepts:
  - Arithmetic Average Return
  - Asset Returns
  - Geometric Average Return
  - Real Stock Return
  - Treasury Bill Return
---

# 1.3 Some stylized empirical facts about asset returns  

This section will summarize some general empirical findings about asset returns. Before doing.   
that, we need to make clear what return means and how we should compute the average return.  

The percentage return or net rate of return on a given asset between time $t-\Delta t$ and time $t$ is  

$$
r_{t}=\frac{D_{t}+P_{t}-P_{t-\Delta t}}{P_{t-\Delta t}}=\frac{D_{t}+P_{t}}{P_{t-\Delta t}}-1,
$$  

where $D_{t}$ is the total dividends paid out over the period for each unit of the asset owned, $P_{t}$ is the unit price of the asset at time $t$ , and $P_{t-\Delta t}$ is the unit price of the asset at time $t-\Delta t$ . Given a time series of such returns $r_{1},r_{2},\ldots,r_{T}$ over time periods of equal length $\Delta t$ , you can compute the arithmetic average (net rate of) return as  

$$
\bar{r}_{\mathrm{arith}}=\frac{1}{T}\sum_{t=1}^{T}r_{t}.
$$  

This may be a good measure of the return you can expect over any period of length $\Delta t$ .On the other hand, it is not necessarily a good measure for the return you can expect to get over a longer periods. This is due to the fact that returns are compounded. If you invested 1 unit of account (i.e. 1 dollar if dividends and prices are measured in dollars) at the starting date of the time series and kept reinvesting dividends by purchasing additional units of the asset, then you will end up with  

$$
(1+r_{1})(1+r_{2})\dotsb(1+r_{T})
$$  

after the last period. The geometric average (rate of) return is computed as  

$$
\bar{r}_{\mathrm{geo}}=\left[(1+r_{1})(1+r_{2})\dots(1+r_{T})\right]^{1/T}-1.
$$  

The geometric average is lower than the arithmetic average. The difference will be larger for a very variable series of returns.  

As a simple example, assume that the percentage return of an asset is $100\%$ in year $^{1}$ and - $50\%$ in year 2. Then the arithmetic average return is $(100\%-50\%)/2=25\%$ and the geometric average return is $[(1+1)(1-0.5)]^{1/2}-1=1-1=0$ , i.e. $0\%$ . An investment of 1 in the beginning of the first year have grown to 2 at the end of year 1 and then dropped to $2\times0.5=1$ at the end of year 2. The zero return over the two periods is better reflected by the geometric average then the arithmetic average.  

Campbell (2003) lists the following stylized facts of U.S. asset returns after World War II (up to around 1998), where average returns are computed as a geometric average:.  

1. The annualized real stock return was $8.1\%$ on average with a standard deviation of $15.6\%$   
2. The annualized real return on a 3-month Treasury bill (U.S. government bond) was $0.9\%$ on average. The standard deviation of the ex post real return was. $1.7\%$ , but much of this is due to short-run inflation risk and the standard deviation of the ex ante real interest rate is considerably smaller.   
3. Real dividend growth at an annual frequency has a standard deviation of 6%.   
4. Quarterly real dividend growth and real stock returns has a correlation of only O.03, but the correlation increases with the measurement period up to a correlation of 0.47 at a 4-year horizon.  

<html><body><table><tr><td rowspan="2">Country</td><td colspan="2">Stocks</td><td colspan="2">Bonds</td><td colspan="2">Bills</td></tr><tr><td>Mean</td><td>StdDev</td><td>Mean</td><td>StdDev</td><td>Mean</td><td>StdDev</td></tr><tr><td>Australia</td><td>9.0</td><td>17.7</td><td>1.9</td><td>13.0</td><td>0.6</td><td>5.6</td></tr><tr><td>Belgium</td><td>4.8</td><td>22.8</td><td>0.3</td><td>12.1</td><td>0.0</td><td>8.2</td></tr><tr><td>Canada</td><td>7.7</td><td>16.8</td><td>2.4</td><td>10.6</td><td>1.8</td><td>5.1</td></tr><tr><td>Denmark</td><td>6.2</td><td>20.1</td><td>3.3</td><td>12.5</td><td>3.0</td><td>6.4</td></tr><tr><td>France</td><td>6.3</td><td>23.1</td><td>0.1</td><td>14.4</td><td>-2.6</td><td>11.4</td></tr><tr><td>Germany</td><td>8.8</td><td>32.3</td><td>0.3</td><td>15.9</td><td>0.1</td><td>10.6</td></tr><tr><td>Ireland</td><td>7.0</td><td>22.2</td><td>2.4</td><td>13.3</td><td>1.4</td><td>6.0</td></tr><tr><td>Italy</td><td>6.8</td><td>29.4</td><td>-0.8</td><td>14.4</td><td>-2.9</td><td>12.0</td></tr><tr><td>Japan</td><td>9.3</td><td>30.3</td><td>1.3</td><td>20.9</td><td>-0.3</td><td>14.5</td></tr><tr><td>The Netherlands</td><td>7.7</td><td>21.0</td><td>1.5</td><td>9.4</td><td>0.8</td><td>5.2</td></tr><tr><td>South Africa</td><td>9.1</td><td>22.8</td><td>1.9</td><td>10.6</td><td>1.0</td><td>6.4</td></tr><tr><td>Spain</td><td>5.8</td><td>22.0</td><td>1.9</td><td>12.0</td><td>0.6</td><td>6.1</td></tr><tr><td>Sweden</td><td>9.9</td><td>22.8</td><td>3.1</td><td>12.7</td><td>2.2</td><td>6.8</td></tr><tr><td>Switzerland</td><td>6.9</td><td>20.4</td><td>3.1</td><td>8.0</td><td>1.2</td><td>6.2</td></tr><tr><td>United Kingdom</td><td>7.6</td><td>20.0</td><td>2.3</td><td>14.5</td><td>1.2</td><td>6.6</td></tr><tr><td>United States</td><td>8.7</td><td>20.2</td><td>2.1</td><td>10.0</td><td>1.0</td><td>4.7</td></tr></table></body></html>  

Table 1.1: Means and standard deviations (StdDev) of real asset returns in different countries. over the period 1900-2000. Numbers are in percentage terms. The returns used are arithmetic. annual returns. Bonds mean long-term (approximately 20-year) government bonds, while bills. mean short-term (approximately 1-month) government bonds. The bond and bill statistics for. Germany exclude the year 1922-23, where the hyperinflation resulted in a loss of 100 percent for German bond investors. For Swiss stocks the data series begins in 1911. Source: Table 4-2 in Dimson, Marsh, and Staunton (2002).  

5. Excess returns on stocks over Treasury bills are forecastable. The log price-dividend ratio can forecast $10\%$ of the variance of the excess return over a 1-year horizon, 22% over a 2-year horizon, and 38% over a 4-year horizon.  

6. The real interest rate has a positive autocorrelation of 0.5 using quarterly data.  

Although the exact estimates vary, the above stylized facts are fairly consistent across countries. The book Triumph of the Optimists by Dimson, Marsh, and Staunton (2002) provides an abundance of information concerning the historical performance of financial markets in 16 countries. Table 1.1 is a slightly edited version of Table 4-2 in that book. It shows that in any of these countries the average return on stocks is higher than the average return on long-term bonds, which again is higher than the average short-term interest rate. The same ranking holds for the standard deviations. If you take the standard deviation as a measure of risk, the historical estimates thus confirm the conventional wisdom that higher average returns come with higher risk.  

Dimson, Marsh, and Staunton (2002) also report the best and worst realized real returns for each country and asset class over the period covered, cf. their Tables 4-3 and 6-1. For example, over the past century the annual return on the U.S. stock market has varied from a low of -38.0%  

<html><body><table><tr><td></td><td>bills</td><td>gov. bonds</td><td>corp. bonds</td><td>large stocks</td><td>small stocks</td><td>inflation</td></tr><tr><td>bills</td><td>1.00</td><td>0.24</td><td>0.22</td><td>-0.03</td><td>-0.10</td><td>0.41</td></tr><tr><td>gov. bonds</td><td>0.24</td><td>1.00</td><td>0.91</td><td>0.16</td><td>0.00</td><td>-0.14</td></tr><tr><td>corp. bonds</td><td>0.22</td><td>0.91</td><td>1.00</td><td>0.24</td><td>0.09</td><td>-0.15</td></tr><tr><td>large stocks</td><td>-0.03</td><td>0.16</td><td>0.24</td><td>1.00</td><td>0.79</td><td>-0.03</td></tr><tr><td>small stocks</td><td>-0.10</td><td>0.00</td><td>0.09</td><td>0.79</td><td>1.00</td><td>0.08</td></tr><tr><td>inflation</td><td>0.41</td><td>-0.14</td><td>-0.15</td><td>-0.03</td><td>0.08</td><td>1.00</td></tr></table></body></html>  

Table 1.2: Cross correlations of annual nominal returns between bills (short-term government bonds), long-term government bonds, long-term corporate bonds, stocks in companies with large capitalization, stocks in companies with small capitalization, and the inflation rate. Data from the United States in the period 1926-2000. Source: Ibbotson Associates (2000).  

<html><body><table><tr><td></td><td>bills</td><td>gov. bonds corp. bonds</td><td>large stocks</td><td>small stocks</td></tr><tr><td>bills</td><td>1.00</td><td>0.59</td><td>0.12</td><td>-0.06</td></tr><tr><td>gov. bonds</td><td>0.58 1.00</td><td>0.95</td><td>0.24</td><td>0.04</td></tr><tr><td>corp. bonds</td><td>0.59 0.95</td><td>1.00</td><td>0.30</td><td>0.12</td></tr><tr><td>large stocks</td><td>0.12 0.24</td><td>0.30</td><td>1.00</td><td>0.79</td></tr><tr><td>small stocks</td><td>-0.06 0.04</td><td>0.12</td><td>0.79</td><td>1.00</td></tr></table></body></html>  

Table 1.3: Cross correlations of annual real returns between bills (short-term government bonds), long-term government bonds, long-term corporate bonds, stocks in companies with large capitalization, and stocks in companies with small capitalization. Data from the United States in the period 1926-2000. Source: Ibbotson Associates (2000).  

in 1931 to a high of 56.8% in 1933. For the German stock market the minimum return of -89.6% in 1948 was immediately followed by the maximum return of 155.9% in 1949. For long-term bonds, the annual U.S. real returns have varied from -19.3% in 1918 to. $35.1\%$ in 1982. The fluctuations around the mean are thus substantial..  

Ibbotson Associates Inc. publishes an annual book with a lot of statistics on the U.S. financial. markets. The cross correlations of annual nominal returns on different asset classes in the U.S. are shown in Table 1.2. The cross correlations of annual real returns can be seen in Table 1.3. Note. a fairly high correlation between the real returns on the two stock classes and between the real. returns on the three bond classes, whereas the correlations between any bond class and any stock class is modest.  

Table 1.4 shows the autocorrelations of the annual returns in the different asset classes. The autocorrelation of the short-term interest rate measured by the return on short-term government bonds is quite high, while the autocorrelation for stock returns is close to zero. Autocorrelations can be significant for very short intraday periods..  

According to Cont (2o00) return distributions of individual stocks (and some other assets) exhibit the following characteristics:  

1. Heavy tails: a higher frequency of very low and of very high returns compared to the normal  

<html><body><table><tr><td></td><td>nominal return</td><td>real return</td></tr><tr><td>bills</td><td>0.92</td><td>0.67</td></tr><tr><td>gov. bonds</td><td>-0.06</td><td>0.03</td></tr><tr><td>corp. bonds</td><td>0.07</td><td>0.18</td></tr><tr><td>large stocks</td><td>0.00</td><td>-0.00</td></tr><tr><td>small stocks</td><td>0.08</td><td>0.05</td></tr></table></body></html>  

Table 1.4: Autocorrelations of annual nominal and real returns on bills (short-term government bonds), long-term government bonds, long-term corporate bonds, stocks in companies with large capitalization, and stocks in companies with small capitalization. Data from the United States in the period 1926-2000. Source: Ibbotson Associates (2000).  

distribution. However, increasing the length of the period over which returns are computed, the distribution comes closer to a normal distribution. So the shape of the return distribution varies with the period length.  

2. Gain/loss asymmetry: higher frequency of large negative returns than of large positive returns.  

3. High variability of returns over any period length.  

4. Volatility clustering: positive autocorrelation in volatilities over several days.  

5. Volatility tends to be negatively correlated with the return.  
