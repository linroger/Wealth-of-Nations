---
tags:
  - '#equity_indices'
  - '#expected_shortfall_es'
  - '#historical_simulation'
  - '#market_variables'
  - '#portfolio_risk_management'
  - '#scenario_analysis'
  - '#stressed_var_es'
  - '#value_at_risk_var'
  - '#weighting_observations'
---
# 22.2 HISTORICAL SIMULATION  

Historical simulation is one popular way of estimating VaR or ES. It involves using past data as a guide to what will happen in the future. Suppose that we want to calculate VaR for a portfolio using a one-day time horizon, a. $99\%$ confidence level, and 501 days of data. The first step is to identify the market variables affecting the portfolio. These will typically be interest rates, equity prices, commodity prices, and so on. All prices are measured in the domestic currency. For example, one market variable for a German bank is likely to be the S&P 500 measured in euros..  

Data are collected on movements in the market variablesover the most recent 501 days. This provides 500 alternative scenarios for what can happen between today and tomor-. row. Denote the first day for which we have data as Day 0, the second day as Day 1, and. so on. Scenario 1 is where the percentage changes in the values of all variables are the same as they were between Day 0 and Day 1, Scenario 2 is where they are the same as between Day 1 and Day 2, and so on. For each scenario, the dollar change in the value of. the portfolio between today and tomorrow is calculated. This defines a probability distribution for daily loss (gains are negative losses) in the value of the portfolio. The 99th percentile of the distribution can be estimated as the fifth-highest loss. The estimate. of VaR is this 99th percentile of the loss distribution. We are $99\%$ certain that we will not take a loss greater than the VaR estimate if the changes in market variables in the last 501 days are representative of what will happen between today and tomorrow.  

To express the approach algebraically, define $\nu_{i}$ as the value of a market variable on Day $i$ and suppose that today is Day $n$ . The ith scenario in the historical simulation approach assumes that the value of the market variable tomorrow will be  

$$
{\mathrm{Value~under~}}i\mathrm{th~scenario}=\nu_{n}{\frac{\nu_{i}}{\nu_{i-1}}}
$$  

# Ilustration: Investment in Four Stock Indices  

To illustrate the calculations underlying the approach, suppose that an investor in the. United States owns, on July 8, 2020, a portfolio worth. $\$10$ million consisting of investments in four stock indices: the S&P 500 in the United States, the FTSE 100 in the United Kingdom, the CAC 40 in France, and the Nikkei 225 in Japan. The value of.  

Table 22.1 Investment portfolio used for VaR calculations.   


<html><body><table><tr><td>Index</td><td>Portfolio value ($ooos)</td></tr><tr><td>S&P500</td><td>4,000</td></tr><tr><td>FTSE100</td><td>3,000</td></tr><tr><td>CAC40</td><td>1,000</td></tr><tr><td>Nikkei 225</td><td>2,000</td></tr><tr><td>Total</td><td>10,000</td></tr></table></body></html>  

the investment in each index on July 8, 2020, is shown in Table 22.1. An Excel. spreadsheet containing 501 days of historical data on the closing prices of the four. indices, together with exchange rates and a complete set of VaR and ES calculations are on the author's website:'.  

# www-2.rotman.utoronto.ca/\~hull/OFOD/VaRExample  

The data we use are total return indices where it is assumed that dividends paid on the stocks underlying the indices are reinvested in the indices. Because we are considering a U.S. investor, the value of the FTSE 100, CAC 40, and Nikkei 225 must be measured in U.S. dollars. For example, the FTSE 100 total return index was 6,515.12 on May 9, 2018 (the beginning of the 501-day period considered), when the exchange rate was 1.3553 USD per GBP. This means that, measured in U.S. dollars, it was $6{,}515.12\times1.3553$ $=8{,}830.23$ . An extract from the data with all indices measured in U.S. dollars is in Table 22.2.  

July 8, 2020, is an interesting date to choose in evaluating an equity investment. The COVID-19 pandemic had led to a big drop in equity markets in March 2020. By July. 2020, U.S. markets had largely recovered, but there was still a great deal of uncertainty. about how long the pandemic would continue and when the economy would recover.  

Table 22.3 shows the values of the indices (measured in U.S. dollars) on July 9, 2020, for the scenarios considered. Scenario 1 (the first row in Table 22.3) shows the values of indices on July 9, 2020, assuming that their percentage changes between July 8 and  

Table 22.2 U.S. dollar equivalent of total return stock indices for historical simulation.   


<html><body><table><tr><td>Day</td><td>Date</td><td>S&P500</td><td>FTSE100</td><td>CAC40</td><td>Nikkei225</td></tr><tr><td>0</td><td>May 9, 2018</td><td>5,292.90</td><td>8,830.23</td><td>16,910.33</td><td>322.40</td></tr><tr><td>1</td><td>May 10, 2018</td><td>5,343.70</td><td>8,926.56</td><td>16,915.41</td><td>321.24</td></tr><tr><td>2</td><td>May 11, 2018</td><td>5,354.69</td><td>8,982.76</td><td>17,065.64</td><td>326.20</td></tr><tr><td>3</td><td>May 14, 2018</td><td>5,359.66</td><td>8,999.31</td><td>17,121.67</td><td>328.03</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>499</td><td>July 7, 2020</td><td>6,445.59</td><td>7,269.36</td><td>15,784.97</td><td>345.40</td></tr><tr><td>500</td><td>July 8, 2020</td><td>6,496.14</td><td>7,255.04</td><td>15,540.44</td><td>342.01</td></tr></table></body></html>

3 To keep the example as straightforward as possible, only days when all four indices traded were included in the compilation of the data..  

Table 22.3 Scenarios generated for July 9, 2020, using data in Table 22.2. (Negative losses are gains.)   


<html><body><table><tr><td>Scenario number</td><td>S&P500</td><td>FTSE100</td><td></td><td>CAC40Nikkei225</td><td>5Portfoliovalue ($000s)</td><td>Loss ($000s)</td></tr><tr><td>1</td><td>6,558.49</td><td>7,334.19</td><td>15,545.12</td><td>340.79</td><td>10,064.257</td><td>-64.257</td></tr><tr><td>2</td><td>6,509.50</td><td>7,300.72</td><td>15,678.46</td><td>347.28</td><td>10,066.822</td><td>-66.822</td></tr><tr><td>3</td><td>6,502.17</td><td>7,268.41</td><td>15,591.47</td><td>343.93</td><td>10,023.722</td><td>-23.722</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>499</td><td>6,425.90</td><td>7,293.40</td><td>15,543.89</td><td>341.21</td><td>9,968.126</td><td>31.874</td></tr><tr><td>500</td><td>6,547.09</td><td>7,240.75</td><td>15,299.71</td><td>338.66</td><td>9,990.361</td><td>9.639</td></tr></table></body></html>  

July 9, 2020, are the same as they were between May 9 and May 10, 2018; Scenario 2 (the second row in Table 22.3) shows the values of market variables on July 9, 2020,. assuming these percentage changes are the same as those between May 10 and May 11, 2018; and so on. In general, Scenario. $i$ assumes that the percentage changes in the. indices between July 8 and July 9, 2020, are the same as they were between Day. $i\textrm{--}1$ and Day $i$ for $1\le i\le500$ The 500 rows in Table 22.3 are the 500 scenarios considered..  

The S&P 500 total return index was 6,496.14 on July 8, 2020. On May 10, 2018, it was 5,343.70 up from 5,292.90 on May 9, 2018. Therefore, the value of the S&P 500 total return index under Scenario 1 is.  

$$
6,496.14\times\frac{5,343.70}{5,292.90}=6.558.49
$$  

Similarly, the values of the FTSE 100, CAC 40, and Nikkei 225 total return indices are 7,334.19, 15,545.12, and 340.79, respectively. It follows that the total value of the portfolio under Scenario 1 is (in $\$000$  

$$
{\begin{array}{r l}&{\qquad0\times{\frac{6.558.49}{6.496.14}}+3,000\times{\frac{7,334.19}{7,255.04}}+1,000\times{\frac{15,545.12}{15,540.44}}+2,000\times{\frac{340.79}{342.01}}}\ &{\qquad=10,064.257}\end{array}}
$$  

The portfolio therefore has a gain of $\$64,457$ under Scenario 1. A similar calculation is carried out for the other scenarios.  

The losses for the 500 different scenarios are then ranked. An extract from the results of doing this is shown in Table 22.4. The worst scenario is number 427, where indices. are assumed to change in the same way as between March 17 and March 18, 2020.. Other big losses are also as a result of changes observed in March 2020. The one-day. $99\%$ value at risk can be estimated as the fifth worst loss. This is. $\$423,291$  

As explained in Section 22.1, the ten-day. $99\%$ VaR is usually calculated as $\sqrt{10}$ times the one-day $99\%$ VaR. In this case the ten-day VaR would therefore be  

$$
{\sqrt{10}}\times422,291=1,335,401
$$  

or $\$1,335,401$  

Each day the VaR estimate in our example would be updated using the most recent 501 days of data. Consider, for example, what happens on July 9, 2020 (Day 501). We find out new values for all the market variables and are able to calculate a new value for the portfolio. We then go through the procedure we have outlined to calculate a new VaR.. Data on the market variables from May 10, 2018, to July 9, 2020 (Day 1 to Day 501) are. used in the calculation. (This gives us the required 500 observations on the percentage. changes in market variables; the May 9, 2018, Day 0, values of the market variables are no longer used.) Similarly, on the next trading day, July 10, 2020 (Day 502), data from May 11, 2018, to July 10, 2020 (Day 2 to Day 502) are used to determine VaR, and so on..  

Table 22.4 Losses ranked from highest to lowest for 500 scenarios.   


<html><body><table><tr><td>Scenarionumber</td><td>Loss ($000s)</td></tr><tr><td>427</td><td>922.484</td></tr><tr><td>429</td><td>858.423</td></tr><tr><td>424</td><td>653.541</td></tr><tr><td>415</td><td>490.215</td></tr><tr><td>482</td><td>422.291</td></tr><tr><td>440</td><td>362.733</td></tr><tr><td>426</td><td>360.532</td></tr><tr><td>431</td><td>353.788</td></tr><tr><td>417</td><td>323.505</td></tr><tr><td>433</td><td>305.216</td></tr><tr><td>452</td><td>245.151</td></tr><tr><td>418</td><td>241.561</td></tr><tr><td>140</td><td>231.269</td></tr><tr><td>289</td><td>230.626</td></tr><tr><td>152</td><td>229.683</td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr></table></body></html>  

In practice, a financial institution's portfolio is, of course, considerably more complicated than the one we have considered here. It is likely to consist of thousands or tens of thousands of positions (involving exchange rates, commodity prices, interest rates, and so on). Some of the bank's positions are typically in forward contracts, options, and other derivatives. Also, the portfolio itself is likely to change from day to day. If a bank's trading leads to a riskier portfolio, VaR typically increases; if it leads to a less risky portfolio, VaR typically decreases. The VaR is calculated on any given day on the assumption that the portfolio will remain unchanged over the next business day.  

In the case of interest rates, a bank typically needs several term structures of zero-. coupon interest rates in a number of different currencies to value its portfolio. The market. variables that are considered are the ones from which these term structures are calculated (see Chapter 4 for the calculation of the term structure of zero rates). There might be as many as ten market variables for each zero curve to which the bank is exposed..  

# Expected Shortfall  

To calculate expected shortfall using historical simulation we average the observations in the tail of the distribution of losses. In the case of our example, the five worst losses $(\$000$ are from scenarios 427, 429, 424, 415, and 482 (see Table 22.4). The average of the losses for these scenarios is $\$669,391$ . This is the expected shortfall estimate.  

# Weighting Observations  

In the calculations presented so far, the 500 scenarios were given equal weight. In some situations, it might be considered appropriate to give more weight to recent scenarios. One way of doing this is to assign a weight to the ith scenario of  

$$
\frac{\lambda^{n-i}(1-\lambda)}{1-\lambda^{n}}
$$  

where $n$ is the number of scenarios and $\lambda$ is a parameter between zero and one. The weights sum to one and decline at rate $\lambda$ . We rank the scenarios as before and calculate cumulative weights. The $99\%$ VaR is the loss for the first scenario which is such that the cumulative weight exceeds 0.01.  

Suppose we use a value of $\lambda$ equal to 0.995. The weights assigned to scenarios 427, 429, 424, and 415 are 0.003776, 0.003814, 0.003719, and 0.003555, respectively. The cumulative weights are 0.004833, 0.007590, 0.011309, and 0.014864. The VaR is the loss given by the third scenario, or $\$653,541$ . The expected shortfall is calculated by using weights proportional to 0.003776, 0.003814, and $0.01\mathrm{~-~}0.003776\mathrm{~-~}0.003814$ to the losses from the first three scenarios. It is about $\$833,400$  

# Stressed VaR and Stressed ES  

The calculations given so far assume that the most recent data is used for the historical simulation on any given day. For example, when calculating VaR and ES for the fourindex example, we used data from the immediately preceding 501 days. However, historical simulations can be based on data from any period in the past. Periods of high volatility will tend to give high values for VaR and ES, while periods of low volatility will tend to give low values.  

Regulators have introduced measures known as stressed VaR and stressed ES. To calculate these measures, a financial institution must search for a 251-day period of extreme stress for their current portfolio. The data for that 251-day period then plays the same role as the 501-day period in our example. The changes in market variables between Day 0 and Day 1 of the 251-day period are used to create the first scenario; the changes in market variables between Day 1 and Day 2 of the 251-day period are used to create the second scenario; and so on. In total, 250 scenarios are created. The one-day $99\%$ stressed $\mathrm{VaR}$ can be calculated as the loss that is midway between the loss for the. second worst scenario and the loss for the third worst scenario. The one-day. $99\%$ stressed ES can be calculated as $0.4c_{1}+0.4c_{2}+0.2c_{3}$ where $c_{1},c_{2}$ , and $c_{3}$ are the three. worst losses with $c_{1}>c_{2}>c_{3}$  
