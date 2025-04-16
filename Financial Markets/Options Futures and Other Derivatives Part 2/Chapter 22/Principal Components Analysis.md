---
tags:
  - '#ewma_arch_garch'
  - '#factor_loadings'
  - '#factor_scores'
  - '#historical_simulation'
  - '#model_building_approach'
  - '#principal_components_analysis'
  - '#us_treasury_rates'
  - '#var_calculation'
  - '#volatilities_and_correlations'
---
# 22.9 PRINCIPAL COMPONENTS ANALYSIS  

One approach to handling the risk arising from groups of highly correlated market variables is principal components analysis. This is a standard statistical tool with many. applications in risk management. It takes historical data on movements in the market variables and attempts to define a set of components or factors that explain the movements.  

The approach is best illustrated with an example. The market variables we will consider are U.S. Treasury rates with maturities 1 year, 2 years, 3 years, 5 years, 7 years, 10 years, 20 years, and 30 years. Tables 22.9 and 22.10 show results produced for these market variables using 2,631 daily observations between 2010 and 2020. The first column in Table 22.9 shows the maturities of the rates that were considered. The remaining eight columns in the table show the eight factors (or principal components) describing the rate moves. The first factor, shown in the column labeled PC1, corresponds to a shift in the yield curve where all rates move in the same direction. When we have one unit of that factor, the 1-year rate increases by 0.083 basis points, the 2-year rate increases by 0.210 basis points, and so on. The second factor is shown in the column labeled PC2. It corresponds to a "twist" or change of slope of the yield curve. Rates with maturities between 1 year and 7 years move in one direction; rates with maturities between 10 years and 30 years move in the other direction. The third factor corresponds to a "bowing" of the yield curve. Relatively short rates and relatively long rates move in one direction; the intermediate rates move in the other direction. The interest rate move for a particular factor is known as factor loading. In our example, the first factor's loading for the 1-year rate is 0.083.16 (Note that the signs for factor loadings are somewhat arbitrary. We can change the signs for all factor loadings corresponding to a particular factor without changing the model. For example, if we did so for the first factor, $-1$ unit of that factor would result in the same yield curve changes as $+1$ unit does in Table 22.9.)  

Table 22.9 Factor loadings for U.S. Treasury rates.   


<html><body><table><tr><td></td><td>PC1</td><td>PC2</td><td>PC3</td><td>PC4</td><td>PC5</td><td>PC6</td><td>PC7</td><td>PC8</td></tr><tr><td>1yr</td><td>0.083</td><td>-0.242</td><td>0.685</td><td>-0.682</td><td>-0.006</td><td>-0.025</td><td>-0.021</td><td>-0.004</td></tr><tr><td>2yr</td><td>0.210</td><td>-0.465</td><td>0.376</td><td>0.574</td><td>-0.517</td><td>-0.031</td><td>0.011</td><td>-0.008</td></tr><tr><td>3yr</td><td>0.286</td><td>-0.467</td><td>0.006</td><td>0.185</td><td>0.728</td><td>0.347</td><td>0.106</td><td>-0.074</td></tr><tr><td>5yr</td><td>0.386</td><td>-0.315</td><td>-0.332</td><td>-0.145</td><td>0.061</td><td>-0.604</td><td>-0.348</td><td>0.361</td></tr><tr><td>7yr</td><td>0.430</td><td>-0.099</td><td>-0.349</td><td>-0.265</td><td>-0.266</td><td>-0.008</td><td>0.263</td><td>-0.688</td></tr><tr><td>10yr</td><td>0.428</td><td>0.119</td><td>-0.153</td><td>-0.172</td><td>-0.269</td><td>0.515</td><td>0.254</td><td>0.589</td></tr><tr><td>20yr</td><td>0.426</td><td>0.394</td><td>0.172</td><td>0.099</td><td>0.027</td><td>0.244</td><td>-0.722</td><td>-0.205</td></tr><tr><td>30yr</td><td>0.411</td><td>0.478</td><td>0.323</td><td>0.204</td><td>0.234</td><td>-0.434</td><td>0.461</td><td>0.036</td></tr></table></body></html>  

Because there are eight rates and eight factors, the interest rate changes observed on. any given day can always be expressed as a linear sum of the factors by solving a set of. eight simultaneous equations. The quantity of a particular factor in the interest rate changes on a particular day is known as the factor score for that day..  

The importance of a factor is measured by the standard deviation of its factor score. The standard deviations of the factor scores in our example are shown in Table 22.10 and the factors are listed in order of their importance. The numbers in Table 22.10 are measured in basis points. A quantity of the first factor equal to 1 standard deviation, therefore, corresponds to the 1-year rate moving by $0.083\times11.54=0.96$ basis points, the 2-year rate moving by $0.210\times11.54=2.42$ basis points, and so on.  

Software for carrying out the calculations underlying Tables 22.9 and 22.10 is on the. author's website (www-2.rotman.utoronto.ca/\~hull/ofod). The factors have the prop-. erty that the factor scores are uncorrelated across the data. For instance, in our example, the first factor score (amount of parallel shift) is uncorrelated with the second factor score (amount of twist) across the 2,631 days. The variances of the factor scores have the property that they add up to the total variance of the data. From Table 22.10, the total variance of the original data (that is, sum of the variance of the observations on the 1-year rate, the variance of the observations on the 2-year rate, and so on) is  

Table 22.10 Standard deviation of factor scores (basis points).   


<html><body><table><tr><td>PC1</td><td>PC2</td><td>PC3</td><td>PC4</td><td>PC5</td><td>PC6</td><td>PC7</td><td>PC8</td></tr><tr><td>11.54</td><td>3.55</td><td>1.78</td><td>1.25</td><td>0.91</td><td>0.69</td><td>0.62</td><td>0.57</td></tr></table></body></html>  

![](9276a2feeee78f1fcc71070f8808402941a13b11ee81b17570639d97c72c4b18.jpg)  
Figure 22.6 The three most important factors driving movements in U.S. Treasury rates.  

$$
11.54^{2}+3.55^{2}+1.78^{2}+\cdot\cdot\cdot+0.57^{2}=152.5
$$  

From this it can be seen that the first factor accounts for $11.54^{2}/152.5=87.3\%$ of the variance in the original data; the first two factors account for  

$$
(11.54^{2}+3.55^{2})/152.5=95.6\%
$$  

of the variance in the data; the third factor accounts for a further. $2.1\%$ of the variance. This shows that most of the risk in interest rate moves is accounted for by the first two. or three factors. It suggests that we can relate the risks in a portfolio of interest rate dependent instruments to movements in these factors instead of considering all eight interest rates.  

The three most important factors from Table 22.9 are plotted in Figure 22.6.17  

# Using Principal Components Analysis to Calculate VaR  

To illustrate how a principal components analysis can be used to calculate VaR, consider. a portfolio with the exposures to interest rate moves shown in Table 22.11. A 1-basispoint change in the 2-year rate causes the portfolio value to increase by. $\$10$ million, a 1-basis-point change in the 3-year rate causes it to increase by. $\$4$ million, and so on. Suppose the first two factors are used to model rate moves. (As mentioned above, this captures $95.6\%$ of the variance in rate moves.) Using the data in Table 22.9, the exposure to the first factor (measured in millions of dollars per factor score basis point) is  

Table 22.11  Change in portfolio value for a 1-basis-point rate move ( $\S$ millions).   


<html><body><table><tr><td>2-year</td><td>3-year</td><td>5-year</td><td>7-year</td><td>10-year</td></tr><tr><td>rate +10</td><td>rate +4</td><td>-8</td><td>rate -7</td><td>rate +2</td></tr></table></body></html>  

$$
10\times0.210+4\times0.286-8\times0.386-7\times0.430+2\times0.428=-1.99
$$  

and the exposure to the second factor is  

$$
10\times(-0.465)+4\times(-0.467)-8\times(-0.315)-7\times(-0.099)+2\times0.119=-3.06
$$  

Suppose that $f_{1}$ and $f_{2}$ are the factor scores (measured in basis points). The change in the portfolio value is, to a good approximation, given by.  

$$
\Delta P=-1.99f_{1}-3.06f_{2}
$$  

The factor scores are uncorrelated and have the standard deviations given in Table 22.10. The standard deviation of $\Delta P$ is therefore  

$$
{\sqrt{1.99^{2}\times11.54^{2}+3.06^{2}\times3.55^{2}}}=25.45
$$  

Assuming normally distributed factors, the 1-day $99\%$ VaR is $25.45\times2.326=59.2$  

A principal components analysis can in theory be used for market variables other than interest rates. Suppose that a financial institution has exposures to a number of different stock indices. A principal components analysis can be used to identify factors describing movements in the indices and the most important of these can be used to replace the market indices in a VaR analysis. How effective a principal components analysis is for a group of market variables depends on how closely correlated they are.  

As explained earlier in the chapter, VaR is usually calculated by relating the actual. changes in a portfolio to percentage changes in market variables (the. $\Delta x_{i}$ ). For a VaR calculation, it may therefore be most appropriate to carry out a principal components analysis on percentage changes in market variables rather than actual changes..  

# SUMMARY  

A value at risk (VaR) calculation is aimed at making a statement of the form:"We are $X$ percent certain that we will not lose more than. $V$ dollars in the next $N$ days." The variable $V$ is the VaR, $X\%$ is the confidence level, and. $N$ days is the time horizon. Expected shortfall (ES) is the expected loss conditional on the loss being greater than the VaR level.  

One approach to calculating VaR or ES is historical simulation. This involves creating a database consisting of the daily movements in all market variables over a period of time. The first simulation trial assumes that the percentage changes in each market variable are the same as those on the first day covered by the database; the second simulation trial assumes that the percentage changes are the same as those on the second day; and so on. The change in the portfolio value, $\Delta P$ , is calculated for each simulation trial, and the VaR is calculated as the appropriate percentile of the probability distribution of $\Delta P$ ES is the average of the observations in the VaR tail.  

An alternative is the model-building approach. This is relatively straightforward if two assumptions can be made:  

1. The change in the value of the portfolio. $(\Delta P)$ is linearly dependent on percentage changes in market variables. 2. The percentage changes in market variables are multivariate normally distributed.  

The probability distribution of. $\Delta P$ is then normal, and there are analytic formulas for. relating the standard deviation of. $\Delta P$ to the volatilities and correlations of the under-. lying market variables. The VaR or ES can be calculated from well-known properties of the normal distribution.  

When a portfolio includes options, $\Delta P$ is not linearly related to the percentage changes in market variables. From knowledge of the gamma of the portfolio, we can derive an approximate quadratic relationship between $\Delta P$ and percentage changes in market variables. Monte Carlo simulation can then be used to estimate VaR.  

In the next chapter we discuss how volatilities and correlations can be estimated and monitored.  

# FURTHER READING  

Artzner P., F. Delbaen, J.-M. Eber, and D. Heath. "Coherent Measures of Risk," Mathematical Finance, 9 (1999): 203-28.   
Basak, S., and A. Shapiro. "Value-at-Risk-Based Risk Management: Optimal Policies and Asset Prices," Review of Financial Studies, 14, 2 (2001): 371-405.   
Boudoukh, J., M. Richardson, and R. Whitelaw. "The Best of Both Worlds,' Risk, May 1998: 64-67.   
Dowd, K. Beyond Value at Risk: The New Science of Risk Management. New York: Wiley, 1998..   
Duffie, D., and J. Pan. "An Overview of Value at Risk," Journal of Derivatives, 4, 3 (Spring 1997): 7-49.   
Embrechts, P., C. Kluppelberg, and T. Mikosch. Modeling Extremal Events for Insurance and Finance. New York: Springer, 1997.   
Hull, J. C., and A. White. "Value at Risk When Daily Changes in Market Variables Are Not Normally Distributed," Journal of Derivatives, 5 (Spring 1998): 9-19.   
Hull, J. C., and A. White. "Incorporating Volatility Updating into the Historical Simulation Method for Value at Risk," Journal of Risk, 1, 1 (1998): 5-19..   
Jackson, P., D. J. Maude, and W. Perraudin. "Bank Capital and Value at Risk." Journal of Derivatives, 4, 3 (Spring 1997): 73-90.   
Jamshidian, F., and Y. Zhu. "Scenario Simulation Model: Theory and Methodology," Finance. and Stochastics, 1 (1997): 43-67.   
Jorion, P. Value at Risk, 3rd edn. McGraw-Hill, 2007..   
Longin, F. M. "Beyond the VaR," Journal of Derivatives, 8, 4 (Summer 2001): 36-48.   
Marshall, C., and M. Siegel. "Value at Risk: Implementing a Risk Measurement Standard, Journal of Derivatives 4, 3 (Spring 1997): 91-111.   
Neftci, S. "Value at Risk Calculations, Extreme Events and Tail Estimation,' Journal of. Derivatives, 7, 3 (Spring 2000): 23-38.   
Rich, D. "Second Generation VaR and Risk-Adjusted Return on Capital," Journal of. Derivatives, 10, 4 (Summer 2003): 51-61.  

# Practice Questions  

22.1. Consider a position consisting of a. $\$100,000$ investment in asset A and a $\$100,000$ investment in asset B. Assume that the daily volatilities of both assets are $1\%$ and that the coefficient of correlation between their returns is 0.3. Estimate the 5-day $99\%$ VaR and ES for the portfolio assuming normally distributed returns..   
22.2. Describe three ways of handling instruments that are dependent on interest rates when the model-building approach is used to calculate VaR. How would you handle these instruments when historical simulation is used to calculate VaR?   
22.3. A financial institution owns a portfolio of options on the U.S. dollar-sterling exchange. rate. The delta of the portfolio is 56.0. The current exchange rate is 1.5000. Derive an approximate linear relationship between the change in the portfolio value and the percentage change in the exchange rate. If the daily volatility of the exchange rate is. $0.7\%$ , estimate the 10-day $99\%$ VaR.   
22.4. Suppose you know that the gamma of the portfolio in the previous question is 16.2. How. does this change your estimate of the relationship between the change in the portfolio value and the percentage change in the exchange rate?   
22.5. Suppose that the daily change in the value of a portfolio is, to a good approximation, linearly dependent on two factors, calculated from a principal components analysis. The. delta of a portfolio with respect to the first factor is 6 and the delta with respect to the second factor is $^{-4}$ The standard deviations of the factors are 20 and 8, respectively. What is the 5-day $90\%$ VaR? 22.6 Suppose that a company has a portfolio consisting of positions in stocks and bonds. Assume that there are no derivatives. Explain the assumptions underlying (a) the linear model and (b) the historical simulation model for calculating VaR.   
22.7. Explain how a forward contract to sell foreign currency is mapped into a portfolio of zero-coupon bonds with standard maturities for the purposes of a VaR calculation.   
22.8. Explain the difference between value at risk and expected shortfall.   
22.9. Explain why the linear model can provide only approximate estimates of VaR for a portfolio containing options.   
22.10. Some time ago a company entered into a forward contract to buy f1 million for $\$1.5$ million. The contract now has 6 months to maturity. The daily volatility of a. 6-month zero-coupon sterling bond (when its price is translated to dollars) is $0.06\%$ and the daily volatility of a 6-month zero-coupon dollar bond is. $0.05\%$ . The correlation between returns from the two bonds is 0.8. The current exchange rate is 1.53. Calculate the standard deviation of the change in the dollar value of the forward contract in 1 day. What is the 10-day $99\%$ VaR? Assume that the 6-month interest rate in both sterling and. dollars is $5\%$ per annum with continuous compounding.  

22.11. The text calculates a VaR estimate for the example in Table 22.11 assuming two factors. How does the estimate change if you assume (a) one factor and (b) three factors.  

22.12. A bank has a portfolio of options on an asset. The delta of the options is $-30$ and the gamma is $-5$ . Explain how these numbers can be interpreted. The asset price is 20 and its volatility is $1\%$ per day. Adapt Sample Application E in the DerivaGem Application Builder software to calculate VaR.  

22.13. Suppose that in Problem 22.12 the vega of the portfolio is $^{-2}$ per $1\%$ change in the annual volatility. Derive a model relating the change in the portfolio value in 1 day to delta, gamma, and vega. Explain without doing detailed calculations how you would use the model to calculate a VaR estimate.  

22.14. The 1-day $99\%$ VaR is calculated using historical simulation for the four-index example in Section 22.2 as $\$423,231$ . Look at the underlying spreadsheets on the author's website. and calculate using historical simulation: (a) the 1-day. $95\%$ VaR, (b) the 1-day $95\%$ ES, (c) the 1-day $97\%$ VaR, and (d) the 1-day $97\%$ ES. Repeat your calculations using the. model-building approach.  

22.15. Use the spreadsheets on the author's website to calculate the 1-day $99\%$ VaR and ES, employing the basic methodology in Section 22.2, if the four-index portfolio considered in Section 22.2 is equally divided between the four indices. Repeat your calculations using the model-building approach.  

22.16. A company has a position in bonds worth. $\$6$ million. The modified duration of the. portfolio is 5.2 years. Assume that only parallel shifts in the yield curve can take place and that the standard deviation of the daily yield change (when yield is measured in percent) is 0.09. Use the duration model to estimate the 20-day. $90\%$ VaR for the portfolio. Explain carefully the weaknesses of this approach to calculating VaR. Explain two alternatives that give more accuracy.  

22.17. Consider a portfolio of options on a single asset. Suppose that the delta of the portfolio. is 12, the value of the asset is $\$10$ , and the daily volatility of the asset is $2\%$ . Estimate the 1-day $95\%$ VaR for the portfolio from the delta. Suppose next that the gamma of the. portfolio is $-2.6$ . Derive a quadratic relationship between the change in the portfolio. value and the percentage change in the underlying asset price in one day. How would you use this in a Monte Carlo simulation?  

22.18. A company has a long position in a 2-year bond and a 3-year bond, as well as a short position in a 5-year bond. Each bond has a principal of. $\$100$ and pays a $5\%$ coupon annually. Calculate the company's exposure to the 1-year, 2-year, 3-year, 4-year, and 5-year rates. Use the data in Tables 22.9 and 22.10 to calculate a 20-day $95\%$ VaR on the assumption that rate changes are explained by (a) one factor, (b) two factors, and (c) three factors. Assume that the zero-coupon yield curve is flat at $5\%$  

22.19. A bank has written a call option on one stock and a put option on another stock. For. the first option the stock price is 50, the strike price is 51, the volatility is. $28\%$ per annum, and the time to maturity is 9 months. For the second option the stock price is 20, the strike price is 19, the volatility is $25\%$ per annum, and the time to maturity is 1 year. Neither stock pays a dividend, the risk-free rate is. $6\%$ per annum, and the correlation between stock price returns is 0.4. Calculate a 10-day $99\%$ VaR: (a) using only deltas, (b) using the partial simulation approach, and (c) using the full simulation. approach.  

22.20. Use equation (22.1) to show that when the loss distribution is normal, VaR with $99\%$ confidence is almost exactly the same as ES with $97.5\%$ confidence.  

![](64a20f671099ce8c1a8846eb9b1f02fd1e58e81a8c5315aa2a22f081797dd721.jpg)  

# Estimating Volatilities and Correlations  

In this chapter we explain how historical data can be used to produce estimates of the current and future levels of volatilities and correlations. The chapter is relevant both to the calculation of value at risk using the model-building approach and to the valuation of derivatives. When calculating value at risk, we are most interested in the current levels of volatilities and correlations because we are assessing possible changes in the value of a portfolio over a very short period of time. When valuing derivatives, forecasts of volatilities and correlations over the whole life of the derivative are usually required.  

The chapter considers models with imposing names such as exponentially weighted. moving average (EWMA), autoregressive conditional heteroscedasticity (ARCH), and generalized autoregressive conditional heteroscedasticity (GARCH). The distinctive feature of the models is that they recognize that volatilities and correlations are not. constant. During some periods, a particular volatility or correlation may be relatively low, whereas during other periods it may be relatively high. The models attempt to keep. track of the variations in the volatility or correlation through time..  
