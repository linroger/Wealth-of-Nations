---
tags:
  - bond_yields
  - interest_rate_risk
  - market_maker
  - regression_hedging
  - relative_value_trading
aliases:
  - DV01 Hedge
  - JNJ Bonds
  - Regression Hedge
key_concepts:
  - Regression hedge risk weight
  - Regression hedge variance
  - Single-variable regression hedging
  - Standard deviation residuals
  - Yield-based DV01 hedge
---

# 6.1 SINGLE-VARIABLE REGRESSION HEDGING  

This section considers the problem of a market maker or a relative value trader on May 14, 2021, who purchases $\$100$ million face amount of the JNJ 2.450s of 09/01/2060 and hedges the resulting interest rate risk by selling the US Treasury 1.625s of 11/15/2050. Because there is no 40-year Treasury bond outstanding, the 1.625s of 11/15/2050, with about 30 years to maturity, are selected as the best alternative. Table 6.1 gives the coupons, maturity dates, yields, and Dv01s of these two bonds, along with those of two other bonds that are referenced in the next section.  

The trader can choose the face amount of the Treasury bond in the hedge using the ratio of Dv01s, along the lines of Chapter 4. In this case, the trader sells $\$100$ million $\times0.2124/0.1910$ , or $\$111.2$ million. As discussed in Chapter 4, however, this hedge assumes that the yields of the JNJ and Treasury bonds move up or down in parallel. But because the JNJ bonds sell at a changing corporate spread to Treasuries, and because 40- and 30-year. rates are not perfectly correlated, as emphasized in Chapter 5, there is good. reason to question the assumption of parallel yield shifts in this case.  

The scatter plot in Figure 6.1 shows the daily changes in yield of the JNJ bonds against those of the Treasury bond from January 19, 2021, to May 14, 2021, which is a window of about four months before the date of the hedge. The line in the figure is the regression line fitted through the data, which is discussed presently. The figure teaches two lessons. First, there is a lot of variation in the relationship between these changes. Some days, the Treasury yield changes by more (e.g., the point on the graph at $(-18.2,-11.1))$ ; some days by less (e.g., the point. $(-3.3,-7.7))$ ; and some days even in opposite. directions (e.g., the point. $(2.0,-2.2)$ ). Second, from the slope of the line, the average relationship between yield changes is less than one-to-one; that is, the change in the yield of the JNJ bonds tends to be less than the change in the yield of the Treasury bonds..  

Figure 6.1 implicitly assumes that the most relevant period for designing an empirical hedge is the recent, immediate past. This assumption is often reasonable, but there are times and situations in which some earlier period seems more relevant. For example, if the Federal Reserve is expected to raise short-term rates in the immediate future, a similar episode in the past might be more relevant to the future than the recent past, in which the Federal Reserve left rates unchanged or lowered them. Choosing the length of the observation or estimation window is also part of the art of regression hedging. Too short a window might fail to furnish statistically reliable estimates, but too long a window might include less relevant historical data.  

TABLE 6.1  Yields and Yield-Based DV01s for the JNJ 2.450s of 09/01/2060 and Selected US Treasury Bonds, as of May 14, 2021. Yields Are in Percent.   


<html><body><table><tr><td>Issuer</td><td>Bond</td><td></td><td>DV01</td></tr><tr><td>JNJ</td><td>2.450sof09/01/2060</td><td>2.962</td><td>0.2124</td></tr><tr><td>Treasury</td><td>0.875sof11/15/2030</td><td>1.601</td><td>0.0847</td></tr><tr><td>Treasury</td><td>1.375sof11/15/2040</td><td>2.246</td><td>0.1446</td></tr><tr><td>Treasury</td><td>1.625s of 11/15/2050</td><td>2.364</td><td>0.1910</td></tr></table></body></html>  

![](bc96b39021efbd8561339c24806dea698bb6fffe25f04ecf4194ef1d339d9308.jpg)  
FIGURE 6.1 Regression of Daily Changes in Yields of the JNJ 2.450s of 09/01/2060 on Daily Changes in Yields of the Treasury 1.625s of 11/15/2050, from January 19, 2021, to May 14, 2021.  

In light of the empirical evidence in Figure 6.1, the trader might very well choose to: i) adjust the hedge ratio to account for the less than one-to-one relationships between changes in yields; and ii) measure the variation around the average relationship to gain a better understanding of the risk of the hedged position. Regression analysis is a tool with which to achieve both of these objectives.  

Let y/NJ and Ay30 be the changes in yields of the JNJ and 30-year Treasury bonds on date $t$ , respectively. A regression model linking these changes is,  

$$
\Delta y_{t}^{J N J}=\alpha+\beta\Delta y_{t}^{30}+\epsilon_{t}
$$  

Equation 6.1 says that the dependent variable, here the change in the yield of the JNJ bond, equals: a constant or intercept, $\alpha$ ; plus a slope, $\beta$ , times the independent variable, here the change in the yield of the 30-year Treasury bond; plus an error term, $\epsilon_{t}$ . The unknown constant and slope parameters are estimated from the data, in a manner explained presently. These estimated parameters, denoted $\hat{\alpha}$ and $\hat{\beta}$ , respectively, can then be used for prediction. Given the change in the Treasury bond yield on date $t$ , the predicted change in the yield of the JNJ bonds on that date, denoted $\Delta\hat{y}_{t}^{J N J}$ is,  

$$
\Delta\hat{y}_{t}^{J N J}=\hat{\alpha}+\hat{\beta}\Delta y_{t}^{30}
$$  

and the realized error or residual on that day, $\hat{\epsilon}_{t}$ , is given by,.  

$$
\begin{array}{r}{\hat{\epsilon}_{t}=\Delta y_{t}^{J N J}-\hat{\alpha}-\hat{\beta}\Delta y_{t}^{30}}\ {=\Delta y_{t}^{J N J}-\Delta\hat{y}_{t}^{J N J}}\end{array}
$$  

For example, say that the estimated constant and slope parameters are 0 and 0.84, respectively, and that the Treasury bond yield changes by $-18.2$ basis points. Then, by Equation (6.2), the predicted change in the yield of the JNJ bond is $0+0.84\times(-18.2)=-15.3$ basis points. If, furthermore, the actual change in the JNJ bond is $-11.1$ basis points, then, by (6.3) or (6.4), the realized error or residual is $-11.1-(-15.3)$ or 4.2 basis points. In Figure 6.1, this residual can be thought of as a vertical line dropped from the data point, $(-18.2,-11.1)$ , to the regression line.  

Least-squares estimation of the unknown parameters finds $\hat{\alpha}$ and $\hat{\beta}$ to minimize the sum of the squares of the residuals over the observation period,  

$$
\sum_{t}\hat{\epsilon}_{t}^{2}=\sum_{t}\left(\Delta y_{t}^{J N J}-\hat{\alpha}-\hat{\beta}\Delta y_{t}^{30}\right)^{2}
$$  

where the equality follows from Equation (6.3). Squaring of the errors. ensures that offsetting positive and negative errors are not considered. as acceptable as zero errors, and that large errors in absolute value are penalized heavily relative to smaller errors..  

Least-squares estimation assumes that the regression model is a true description of the dynamics of the dependent and independent variables, that the errors across time have the same probability distribution, that they are independent of each other, and that they are uncorrelated with the independent variable. Under these assumptions, least-squares parameter estimates are linear, unbiased, consistent, and efficient.1  

Least-squares estimation is available in many statistical packages and. spreadsheets. Table 6.2 gives a typical summary output from estimatinge Equation (6.1) using the data shown in Figure 6.1. The estimate of the slope coefficient, $\hat{\beta}$ , is 0.842, which says that, on average, the change in the yield of. the JNJ bond is only 0.842 times the change in the yield of the Treasury bond, which is very different from a parallel shift. The estimate of the constant, $\hat{\alpha}$ is not very different from zero, which is typically the case in regressions of this sort. From an economic perspective, it would be odd if, over an extended period of time, changes in the yield of the JNJ bond tended to be positive or negative when there is no change in the yield of the Treasury bond. The line in Figure 6.1 is the fitted regression line, which is Equation (6.2) with its estimated coefficients,  

$$
\Delta\hat{y}_{t}^{J N J}=0.060+0.842\Delta y_{t}^{30}
$$  

Table 6.2 also gives the standard errors of the constant and slope coefficients, which provide confidence intervals around the estimates: the interval of each estimate plus or minus two standard errors falls around the true parameter values approximately $95\%$ of the time. In this regression, the confidence intervals are 0.060 plus or minus 2 times 0.223, or $(-0.386,0.446)$ and 0.842 plus or minus 2 times 0.051, or (0.740, 0.944). Hence, because the. confidence interval around the estimated constant includes zero, the hypothesis that $\alpha=0$ cannot be rejected with $95\%$ confidence. But, because the confidence interval for the slope coefficient does not include one, the hypoth-. esis that $\beta=1$ can be rejected with $95\%$ confidence. Hence, the hypothesis of parallel shifts in the yields of the two bonds is rejected by the data..  

Table 6.2 reports that the R-squared of the regression is $77.5\%$ , meaning that $77.5\%$ of the variance of changes in the JNJ yield can be explained by the model, that is, by changes in the yield of the 30-year Treasury bond. In a one-variable regression, the R-squared is just the square of the correlation between the dependent and independent variables, which gives a correlation here of $\sqrt{77.5\%}$ , or $88.0\%$ . That these statistics are well below 1.0 indicates that hedging in this case does not come close to eliminating all interest rate risk.  

TABLE 6.2 Regression of Daily Changes in Yields of the JNJ 2.450s of 09/01/2060 on Daily Changes in Yields of the Treasury 1.625s of 11/15/2050, from January 29, 2021, to May 14, 2021.   


<html><body><table><tr><td>No.ofObservations R-Squared</td><td>82 77.5% 2.00</td></tr><tr><td>Regression Coefficients</td><td>Value</td><td>Std. Error</td></tr><tr><td>Constant (@)</td><td>0.060</td><td>0.223</td></tr><tr><td>Chg 30yr Treasury Yield (β)</td><td>0.842</td><td>0.051</td></tr></table></body></html>  

The remaining statistic to be discussed in Table 6.2 is the standard error of the regression, which is essentially the standard deviation of the realized errors or residuals, as defined in Equations (6.3) and (6.4).2 This standard error is a measure of how well the model fits the data and is in the same units as the dependent variable, in this case, basis points. Roughly speaking, then, the standard deviation of the errors in explaining daily changes in the yield of the JNJ bond with daily changes in the yield of the Treasury bond is two basis points. This statistic is particularly useful in describing the risk of a regression-based hedge, as discussed presently.  

All the results in Table 6.2 are in-sample; that is, they are computed from the particular data sample used to estimate the regression model. Relying on these results for hedging assumes that the future will be sufficiently like this particular historical period. The success or failure of this assumption is discussed at the end of the section.  

Turning now to regression hedging, assume for the moment that the yield of the JNJ bonds changes by exactly $\hat{\beta}$ basis points for every one-basis-. point change in the yield of the Treasury bonds. Let $F^{J N J}$ $D V01^{J N J},F^{30}$ and $\dot{D}V01^{30}$ be the face amounts and DV01s of the $\mathrm{JNJ}$ and 30-year Treasury bonds, respectively. Then, the position is hedged against changes in yields if,  

$$
\begin{array}{c}{{F^{J N J}{\frac{D V01^{J N J}}{100}}\hat{\beta}+F^{30}{\frac{D V01^{30}}{100}}=0}}\ {{F^{30}=-F^{J N J}{\frac{D V01^{J N J}}{D V01^{30}}}\hat{\beta}}}\end{array}
$$  

Plugging in numbers, $\$100$ million for the face amount of the JNJ bonds to be hedged, DV01s from Table 6.1, and $\hat{\beta}$ from Table 6.2,  

$$
F^{30}=-\S100m m\frac{0.2124}{0.1910}0.842=-\S93.6m m
$$  

The yield-based Dv01 hedge for the JNJ bonds, which is given by Equation (6.9), is given earlier without the slope coefficient of 0.842 as $\$111.2$ million. The regression hedge of (6.9) sells only $\$93.6$ million because it recognizes that the yield of the JNJ bonds does not move as much as the yield of the 30-year Treasury bond. Hence, fewer Treasury bonds need be sold to hedge the interest rate risk of the JNJ bonds.  

Regression hedges are sometimes described in terms of risk weights. Rearranging terms in Equation (6.7) or (6.8),.  

$$
\frac{-F^{30}\times D V01^{30}/100}{F^{J N J}\times D V01^{J N J}/100}=\hat{\beta}=84.2\%
$$  

In words, the left-hand side of the equation is the Dv01 of the hedge as. a fraction of the Dv01 of the bonds being hedged. The risk weight of a yield-based DV01 hedge is always $100\%$ - the DV01s of the two sides of the trades are, by construction, equal. In this regression hedge, however, the DV01 of the Treasury bonds is only $84.2\%$ of the DV01 of the JNJ bonds. In general, as Equation (6.10) shows, the risk weight of a regression hedge exactly equals the estimated slope coefficient, $\hat{\beta}$  

The best argument for the regression hedge is actually not the earlier. assumption that bond yields change exactly according to the regression model. Write the P&L of the position as,.  

$$
P\&L=-F^{J N J}\frac{D V01^{J N J}}{100}\Delta y_{t}^{J N J}-F^{30}\frac{D V01^{30}}{100}\Delta y_{t}^{30}
$$  

where the negative signs reflect that a positive face amount with a positive change (i.e., increase) in yield lowers $\mathrm{P}\&\mathrm{L}$ . It can then be shown that the regression hedge in Equation (6.8) minimizes the variance (6.11). (See. Appendix A6.1.) In other words, to the extent that $\mathrm{P}\&\mathrm{L}$ variance is an appropriate measure of risk, the regression hedge minimizes the risk of the hedged position.  

Appendix A6.1 also derives the standard deviation of the regressionhedged P&L. Denote this standard deviation by. $\sigma_{P\&L}$ and the standard deviation of the residuals by. $\sigma_{\epsilon}$ . Then,  

$$
\sigma_{P\&L}=\left|F^{J N J}\frac{D V01^{J N J}}{100}\right|\sigma_{\epsilon}
$$  

where $|\cdot|$ is the symbol for absolute value, so that the standard deviation is positive whether the original position is long (positive $F^{J N J}$ ) or short (negative $F^{J N J}$ ). In words, the P&L of the hedged position is the Dv01 of the position being hedged times the standard error of the regression residuals. Intuitively, the hedged P&L on any given day is exactly zero if the yield of. the JNJ bonds moves by 0.842 basis points times the change in the Treasury. yield. But if the residual is one basis point, so that the yield of the JNJ bond increases by one basis point more than that, the hedged position loses the DV01 of the JNJ bonds; and if the residual is minus two basis points, then the hedged position gains twice the DV01 of the JNJ bonds; etc. Hence, the volatility of the hedge is proportional to the variability of the residuals..  

Applying Equation (6.12) to the case at hand, the DV01 of the JNJ bond position is $\$100$ million $\times0.2124/100$ , or $\$212,400$ , and the standard error. of the regression, reported in Table 6.2, is two basis points per day. Therefore, the standard deviation of the hedged. $\mathrm{P}\&\mathrm{L}$ in the sample is $\$212,400\times2$ or $\$424,800$ per day. Whether this is too much risk or not depends on how. much and how fast the trader is making money buying the JNJ bonds and hedging them. If the trader is making five basis points on the position and holding it for a day, then a standard deviation of two basis points per day likely represents a reasonable risk-return trade-off. If, on the other hand, the trader is making 1.5 basis points and holding the position for a week, a standard deviation of two basis points per day likely ruins the trade from a risk-return perspective.  

This section concludes with an out-of-sample analysis of the estimated. regression model. Figure 6.2 shows the same regression line as estimated in Table 6.2 and graphed in Figure 6.1. The plus signs, however, are the changes in yields over the period May 17, 2021, to July 19, 2021. The regression model, estimated over the earlier period, January 29, 2021, to May 15, 2021, holds up quite well. In fact, the standard error of the residu-. als of the out-of-sample data against the original regression line is 1.5 basis. points, which is actually smaller than the in-sample equivalent. The trader hedging as of May 14, 2021, cannot, of course, run this analysis. But other out-of-sample tests can be informative. A trader might see how a regression model performed over a period before the estimation period, perhaps a period right before that window or perhaps an even earlier period that might be more likely to resemble the future. In any case, poor out-of-sample performance should raise questions about the stability of the regression coefficients over time and, therefore, the reliability of the resulting hedge.  

![](cb18f9eb9daed17455c086d2a6d2cc7ff172381b0e24933c5f674e38bdebc6a6.jpg)  
FIGURE 6.2 Yield Changes of the JNJ 2.450s of 09/01/2060 and the Treasury 1.625s of 11/15/2050 from May 17, 2021, to July 19, 2021, and the Regression Line Estimated over the Period January 19, 2021, to May 14, 2021.  
