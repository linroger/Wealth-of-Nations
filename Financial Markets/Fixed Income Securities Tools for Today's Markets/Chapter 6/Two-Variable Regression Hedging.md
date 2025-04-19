---
tags:
  - bond_yields
  - butterfly_strategy
  - regression_hedging
  - relative_value_trade
  - term_structure
aliases:
  - Regression hedging
  - Two-variable hedging
key_concepts:
  - Butterfly trade
  - Hedging face amounts
  - Relative value trader
  - Term structure correlation
  - Two-variable regression hedging
---

# 6.2 TWO-VARIABLE REGRESSION HEDGING  

The hedging approaches of Chapter 5 generalize those of Chapter 4 to. account for the fact that rates across the term structure are not perfectly correlated. Similarly, two-variable regression hedges account for the fact. that changes in a bond's yield might be better explained by changes in the yields of two other bonds, rather than just one, as in a one-variable. regression.  

To illustrate two-variable regression hedging, consider a relative value trader who believes that yields in the 20-year US Treasury bond sector are too high - or prices too low - relative to the 10- and 30-year sectors. Implementing this trade idea by buying a 20-year bond outright is too risky: if. rates increase across the board, the trade loses money even if the trader is right, that is, even if the 20-year bond does outperform 10- and 30-year. bonds. But buying a 20-year bond and hedging the interest rate risk by sell-. ing a 10-year bond also bears too much risk that is unrelated to the trade idea: if the curve steepens (e.g., 30-year yields increase more than 20-year yields, which increase more than 10-year yields), the trade may lose money even if the 20-year bonds outperform. And, finally, buying a 20-year bond and hedging with a 30-year bond can lose money if the curve flattens even. if the 20-year bonds outperform. In practice then, this trade idea is typically implemented with a butterfly: buy 20-year bonds and sell both 10- and. 30-year bonds: both shorts defend against general rate increases; the 10-year short defends against flattening; and the 30-year short defends against steepening. The trader's problem then becomes to choose the face amount of the 10- and 30-year bonds to sell against, say,. $\$100$ million face amount of the. 20-year bond.  

In this illustration, the trader chooses the three Treasury bonds listed in Table 6.1: the 1.375s of 11/15/2040 as the 20-year; the $0.875\mathrm{s}$ of 11/15/2030 as the 10-year; and the 1.625s of 11/15/2050 as the 30-year. The two-variable regression model of changes in yields of these bonds is,  

$$
\Delta y_{t}^{20}=\alpha+\beta^{10}\Delta y_{t}^{10}+\beta^{30}\Delta y_{t}^{30}+\epsilon_{t}
$$  

where the notation is analogous to that of the one-variable regression. Here there are two slope coefficients, describing how changes in the 20-year yield are related to changes in each of the 10-year and 30-year yields..  

Continuing as in the case of one-variable regression, least-squares estimation finds the regression coefficients so as to minimize the sum of the squared residuals,  

$$
\sum_{t}\left(\Delta y_{t}^{20}-\hat{\alpha}+\hat{\beta}^{10}\Delta y_{t}^{10}+\hat{\beta}^{30}\Delta y_{t}^{30}\right)^{2}
$$  

And, with these estimated coefficients, the predicted change of the 20-year rate is,  

$$
\Delta\hat{y}_{t}^{20}=\hat{\alpha}+\hat{\beta}^{10}\Delta y_{t}^{10}+\hat{\beta}^{30}\Delta y_{t}^{30}
$$  

Table 6.3 gives the results of the regression, estimated with data from. January 29, 2021, to May 14, 2021. The R-squared is quite high relative. to that of the single-variable regression, in Table 6.2, in part because two explanatory variables are used, rather than one, and in part because all of the bonds in this regression are Treasuries, whereas the single-variable regression. mixes a corporate bond with a Treasury bond. The standard error is also sig-. nificantly lower here, at 1.15 basis points per day. Again, however, as usual. for regressions of this sort, the estimate of. $\hat{\alpha}$ is small and not significantly. different from zero.  

The slope coefficients say that a one-basis-point increase in the 10-year yield increases the 20-year yield by 0.465 basis points, while a one-basispoint increase in the 30-year yield increases the 20-year yield by 0.669 basis points. With $95\%$ confidence intervals for these coefficients of (0.329, 0.601) and (0.535, 0.803), respectively, both coefficients are significantly different from zero; that is, changes in the yields of both bonds are useful in explaining changes in the yield of the 20-year bond.  

TABLE 6.3 Regression of Daily Changes in Yields of the Treasury 1.375s of 11/15/2040 on Daily Changes in Yields of the Treasury 0.875s of 11/15/2030 and 1.625s of 11/15/2050, from January 29, 2021, to May 14, 2021.   


<html><body><table><tr><td>No.ofObservations R-Squared</td><td>82 94.7% 1.15</td><td></td></tr><tr><td>Regression Coefficients</td><td>Value</td><td>Std.Error</td></tr><tr><td>Constant (a)</td><td>0.019</td><td>0.129</td></tr><tr><td>Chg 10yr Treasury Yield (B30)</td><td>0.465</td><td>0.068</td></tr><tr><td>Chg 30yr Treasury Yield (B10)</td><td>0.669</td><td>0.067</td></tr></table></body></html>  

To derive the hedge based on these regression results, write the $\mathrm{P}\&\mathrm{L}$ of the hedged position as,.  

$$
P\&L=-F^{20}\frac{D V01^{20}}{100}\Delta y_{t}^{20}-F^{10}\frac{D V01^{10}}{100}\Delta y_{t}^{10}-F^{30}\frac{D V01^{30}}{100}\Delta y_{t}^{30}
$$  

and then substitute for $\Delta y_{t}^{20}$ from (6.15) to see that,  

$$
\begin{array}{c}{{P\&L=\left[-F^{20}\frac{D V{01}^{20}}{100}\hat{\beta}^{10}-F^{10}\frac{D V{01}^{10}}{100}\right]\Delta y_{t}^{10}}}\ {{+\left[-F^{20}\frac{D V{01}^{20}}{100}\hat{\beta}^{30}-F^{30}\frac{D V{01}^{30}}{100}\right]\Delta y_{t}^{30}}}\end{array}
$$  

Next, to ensure that $\mathrm{P}\&\mathrm{L}$ is zero, under the assumption that the change in the 20-year rate follows the regression model, set each of the terms in brackets in Equation (6.17) equal to zero. Solving,  

$$
\begin{array}{c}{{F^{10}=-F^{20}\displaystyle\frac{D V01^{20}}{D V01^{10}}\hat{\beta}^{10}}}\ {{F^{30}=-F^{20}\displaystyle\frac{D V01^{20}}{D V01^{30}}\hat{\beta}^{30}}}\end{array}
$$  

or, in terms of risk weights,  

$$
\begin{array}{r l}&{\frac{-F^{10}\times D V01^{10}}{F^{20}D V01^{20}}=\hat{\beta}^{10}}\ &{\frac{-F^{30}\times D V01^{30}}{F^{20}D V01^{20}}=\hat{\beta}^{30}}\end{array}
$$  

Assuming a trade size of $\$100$ million face amount in the 20-year Trea-. sury, substituting the DV01s of the bonds from Table 6.1 and the results of the regression from Table 6.3, the hedging face amounts and risk weights are. $\$79.44$ million and $46.5\%$ for the 10-year, along with $\$50.69$ million and $66.9\%$ for the 30-year. Note that the sum of the risk weights is. $113.4\%$ which means that the DV01 of the hedging position is. $13.4\%$ greater than the Dv01 of the position being hedged. This follows immediately from the slope coefficients of the regression: a simultaneous one-basis-point change in both the 10- and 30-year yields is associated with a 1.134-basis-point. increase in the 20-year yield. Hence, the hedging portfolio requires an extra. $13.4\%$ in DV01.  

Figure 6.3 compares in-sample and out-of-sample residuals from the. regression in Table 6.3. The out-of-sample residuals are very well behaved, in fact, better behaved than the in-sample residuals: the standard error is 1.15 in-sample, and only 0.70 out-of-sample. Traders are not always so fortunate!  

![](9236e12cd1b5f7f45bd6b22d444a5dc60880a8c50377d83e6aeb9590347f42be.jpg)  
FIGURE 6.3 Residuals Using the Regression Coefficients in Table 6.3, in-Sample -- from January 19, 2021, to May 14, 2021 - and Out-of-Sample - from May 17, 2021, to July 19, 2021.  
