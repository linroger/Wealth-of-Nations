---
tags:
  - asset_pricing
  - consumption_model
  - empirical_tests
  - equity_premium
  - risk_aversion
aliases:
  - Asset Pricing
  - Consumption-Based Model
  - Equity Premium Puzzle
key_concepts:
  - Asset pricing puzzles
  - Consumption-based model tests
  - Equity premium
  - Historical average returns
  - Relative risk aversion coefficient
---

# 8.5 Theory meets data - asset pricing puzzles  

The simple consumption-based model has been exposed to numerous empirical tests. Almost all of these tests focus on the question whether the relation (8.33)-or the similar discrete-time relation (8.30)-holds for a broad-based stock index for reasonable values of the relative risk aversion coefficient. Let us use the following stylized figures that are roughly representative for the U.S. economy over the second half of the 20th century:  

. the average annual real excess rate of return on the stock index (relative to the yield on a. short-term government bond) is about $8.0\%$   
. the empirical standard deviation of the annual real rate of return on the stock index is about $20.0\%$   
the empirical standard deviation of annual relative changes in aggregate consumption is about $2.0\%$   
. the empirical correlation between the real return on the stock index and changes in aggregate. consumption is about 0.2.  

Inserting these estimates into (8.33) it follows that the relative risk aversion coefficient $\gamma$ must be 100. This is certainly an unrealistically high risk aversion for a typical individual, cf. the discussion in Section 5.6.2. In fact, this computation-which is standard in the literature - exaggerates the problem somewhat. The estimates of the return and consumption moments are based on discrete observations, not continuous observations, so we should use the discrete-time version of the model. If we drop the approximation in (8.28), the discrete-time simple model says that  

$$
\operatorname{E}_{t}\left[R_{i,t+1}\right]-R_{t}^{f}\approx{\sqrt{e^{\gamma^{2}\sigma^{2}}-1}}\rho_{t}\left[R_{i,t+1},{\frac{C_{t+1}}{C_{t}}}\right]\sigma_{t}\left[R_{i,t+1}\right]
$$  

and plugging in the estimates, we need  

$$
\gamma\approx\frac{1}{\sigma}\sqrt{\ln\left[1+\left(\frac{\mathrm{E}_{t}[R_{i,t+1}]-R_{t}^{f}}{\rho\sigma_{t}[R_{i,t+1}]}\right)^{2}\right]}=\frac{1}{0.02}\sqrt{\ln(5)}\approx63.4.
$$  

But 63.4 is still an unreasonably high relative risk aversion.  

For a reasonable level of risk aversion (probably in the area 2-5), the expected excess rate of return predicted by the theory is much smaller than the historical average. For example with  

<html><body><table><tr><td>Country</td><td>Period</td><td>μm</td><td>0m</td><td>C</td><td>pmC</td><td>人</td><td>**</td></tr><tr><td>U.S.</td><td>1947Q2-1998Q3</td><td>8.1</td><td>15.3</td><td>1.1</td><td>0.205</td><td>240.6</td><td>49.3</td></tr><tr><td>U.S.</td><td>1970Q1-1998Q3</td><td>6.3</td><td>17.0</td><td>0.9</td><td>0.274</td><td>150.1</td><td>41.2</td></tr><tr><td>U.S.</td><td>1891-1997</td><td>6.7</td><td>18.5</td><td>6.4</td><td>0.495</td><td>22.8</td><td>11.3</td></tr><tr><td>Australia</td><td>1970Q1-1998Q4</td><td>3.9</td><td>22.4</td><td>2.1</td><td>0.144</td><td>58.5</td><td>8.4</td></tr><tr><td>Canada</td><td>1970Q1-1999Q1</td><td>4.0</td><td>17.3</td><td>1.9</td><td>0.202</td><td>59.3</td><td>12.0</td></tr><tr><td>France</td><td>1973Q2-1998Q3</td><td>8.3</td><td>23.2</td><td>2.9</td><td>-0.093</td><td>negative</td><td>12.3</td></tr><tr><td>Germany</td><td>1978Q4-1997Q3</td><td>8.7</td><td>20.2</td><td>2.4</td><td>0.029</td><td>599.5</td><td>17.5</td></tr><tr><td>Italy</td><td>1971Q2-1998Q1</td><td>4.7</td><td>27.1</td><td>1.7</td><td>-0.006</td><td>negative</td><td>10.4</td></tr><tr><td>Japan</td><td>1970Q2-1998Q4</td><td>5.1</td><td>21.5</td><td>2.6</td><td>0.112</td><td>82.6</td><td>9.3</td></tr><tr><td>Netherlands</td><td>1977Q2-1998Q3</td><td>11.4</td><td>16.9</td><td>2.5</td><td>0.032</td><td>850.0</td><td>26.9</td></tr><tr><td>Sweden</td><td>1970Q1-1999Q2</td><td>11.5</td><td>23.5</td><td>1.9</td><td>0.015</td><td>1713.2</td><td>26.5</td></tr><tr><td>Sweden</td><td>1920-1997</td><td>6.5</td><td>18.8</td><td>5.6</td><td>0.0167</td><td>74.1</td><td>12.4</td></tr><tr><td>Switzerland</td><td>1982Q2-1998Q4</td><td>14.9</td><td>21.9</td><td>2.1</td><td>-0.112</td><td>negative</td><td>32.1</td></tr><tr><td>U.K.</td><td>1970Q1-1999Q1</td><td>9.2</td><td>21.2</td><td>2.5</td><td>0.093</td><td>186.0</td><td>17.2</td></tr><tr><td>U.K.</td><td>1919-1997</td><td>8.7</td><td>21.3</td><td>5.6</td><td>0.351</td><td>41.2</td><td>14.5</td></tr></table></body></html>  

Table 8.1: The equity premium puzzle internationally. The information is taken from Table 4 in Campbell (2003). Data is quarterly when there are Qx suffices on the years in period column, otherwise annual data is used. The headings of the columns are explained in the text.  

$\gamma=5$ , the expected excess rate of return on the market portfolio should be $5\cdot0.2\cdot0.02\cdot0.2=0.004$ or $0.4\%$ according to (8.33). The simple consumption-based asset pricing model cannot explain the high average stock returns observed in the data. This so-called equity premium puzzle was first pointed out by Mehra and Prescott (1985).  

The equity premium puzzle is not specific to the U.S. or to the post World War II period. Similar results are obtained for other countries and other data periods. Table 8.1 is based on Campbell (2003) who considers the log-return equation (8.31). In the table, $\ddot{\mu}_{m}$ is the historical estimate of the left-hand side of (8.31), i.e. the average excess log return on the stock market adjusted by half the variance. $\ddot{\sigma}_{m}$ is the standard deviation of that excess return, and $\tilde{\sigma}_{C}$ is the standard deviation of the log growth rate of aggregate consumption. The means and standard deviations are annualized and in percentage terms. $\widetilde{\rho}_{m C}$ is the historical correlation between the excess log return on the stock market and the log consumption growth. The values in the column $\gamma^{*}$ is then computed as the value you need to apply for the relative risk aversion in order for (8.31) to hold given the estimates of the other parameters. The $\gamma^{**}$ in the right-most column is the relative risk aversion needed if you fix the return-consumption correlation to 1.  

It is clear from the table that the historical equity premium is pretty high in all the countries. and, given the other estimates, require a very high level of risk aversion. In some of the countries, the estimated correlation between consumption growth and stock returns is negative so that the. equity premium should be negative according to the model or you have to use a negative value for the risk aversion coefficient. The correlation may be difficult to estimate precisely but the right-. most column shows that even if you pick the correlation values most favorable to the model (i.e.. a correlation of 1), you still need a fairly high risk aversion coefficient. The value of the required.  

risk aversion is very sensitive to the estimated consumption volatility. The table reveals that the post World War II U.S. consumption volatility is small compared to the other countries and also. to a longer U.S. data series. Consequently, fixing the correlation at 1, you need a particularly high. risk aversion coefficient to match recent U.S. data..  

With $\gamma=100$ , Equation (8.32) indicates that an increase of one percentage point in the expected growth rate of aggregate consumption will be accompanied by an increase in the short-term interest rate of 100 percentage points also very unrealistic.  

Weil (1989) notes that the simple model predicts a higher level of interest rates than observed empirically. This is the so-called risk-free rate puzzle..  

In the simple model, the real short-term interest rate and the Sharpe ratios of risky assets are. constant over time, which is also inconsistent with empirical observations. Interest rates vary. over time, and recent studies indicate that Sharpe ratios, expected returns, and volatilities on stocks vary over the business cycle with high values in recessions and low values in periods of high economic growth rates, cf. e.g. Cochrane (2001). The future values of these variables are therefore. to some extent predictable, contrasting the simple model. This could be called a predictability. puzzle.  

In addition, empirical studies show that the simple model can explain only a small part of the differences in the average returns on different stocks, cf. e.g. Breeden, Gibbons, and Litzenberger (1989). This is a cross-sectional stock return puzzle.  

Based on the apparently large discrepancy between the model and the data, it is tempting to conclude that the consumption-based approach to asset pricing is not applicable, and otherwise intelligent economists have not been able to withstand this temptation. The conclusion is not fair, however. Firstly, as explained in the following section, there are a number of problems with the empirical tests of the model which make their conclusions less clear. Secondly, it is only the very simple special case of the general consumption-based asset pricing model which is tested. The consumption-based approach in itself is based on only very few and relatively undisputed assumptions so the lack of empirical support must be blamed on the additional assumptions of the simple model. In the last 10-15 years, a number of alternative specifications of the general model have been developed. Most of these alternatives assume either a different representation of preferences than in the simple model or that the market is incomplete so that the representative individual approach is invalid. We will discuss these two types of model extensions in Sections 8.7 and 8.9.  
