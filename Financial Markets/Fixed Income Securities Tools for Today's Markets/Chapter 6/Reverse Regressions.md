---
tags:
  - bond_yields
  - hedging
  - reverse_regression
  - treasury_bonds
  - volatility
aliases:
  - Regression Hedge
  - Reverse Regressions
key_concepts:
  - Hedged position volatility
  - JNJ bonds
  - Regression coefficient
  - Treasury bonds
  - Variance of P&L
---

# 6.4 REVERSE REGRESSIONS  

In Section 6.1, a trader regresses changes in yields of the JNJ 2.450s of 09/01/2060 - with a DV01 of 0.2124 - on changes in yields of the Treasury 1.625s of 11/15/2050 - with a DV01 of 0.1910; obtains a regression coefficient of 0.842; and, against $\$100$ million of the JNJ bonds, calculates a regression hedge to sell $\$100$ million $\times(0.2124/0.1910)\times0.842$ , or $\$93.6$ million Treasury bonds.  

What if another trader runs the reverse regression, that is, regresses changes in yield of the Treasury bond on changes in yield of the JNJ bond? Table 6.4 compares the slope coefficients and standard errors of the original regression and the reverse regression. With a reverse regression $\hat{\beta}$ of 0.921, this second trader hedges. $\$93.6$ million Treasury bonds with $\$93.6$ million $\times(0.1910/0.2124)\times0.921$ , or $\$82.8$ million JNJ bonds..  

These hedges are clearly different. The same. $\$93.6$ million of Treasuries. are hedged with a different amount of JNJ bonds. Or, in terms of risk weights, both quoted as the Dv01 of the Treasury bond position as a. percent of the DV01 of the JNJ position, the risk weight of the regression. is $84.2\%$ , while the risk weight of the reverse regression is $1/0.921$ , or $108.6\%$ . Is one of these hedges right and the other wrong?  

This question actually reveals the importance of the trader's decision in Section 6.1 to hedge $\$100$ million face amount of JNJ bonds. Choosing this face amount actually sets the risk of the trade. As shown earlier, the volatility of the hedged position is $\$100$ million $\times0.2124/100\times$ the two-basis-point standard error of the regression, or about $\$423,000$ . However, the risk of the reverse regression, which sets the face amount of the Treasury bonds at $\$93.6$ million, is. $\$93.6$ million $\times0.1910/100\times$ the 2.09 standard error of the reverse regression, or about $\$374,000$ . These trades, therefore, are not comparable.  

Choosing to hedge $\$100$ million face amount of the JNJ bonds, however,. is not just about the risk of the hedged position. There are many combinations of positions in the JNJ and Treasury bonds that have the same volatility.4 For example, a scaled-up reverse regression hedge, with. $\$106.37\mathrm{mil}$ lion Treasury bonds and. $\$88$ million JNJ bonds (i.e.,. $\$106.37$ million $\times$ $(0.1910/0.2124)\times0.921;$ , has the same $\$423,000$ volatility as the regression hedge $(\S106.37\mathrm{million}\times0.1910/100\times2.09$ ). But while this and other  

TABLE 6.4 Regression: Daily Changes in Yields of the JNJ 2.450s of 09/01/2060 on Daily Changes in Yields of the. Treasury 1.625s of 11/15/2050. Reverse Regression: Daily Changes in Yields of the Treasury 1.625s of 11/15/2050 on Daily Changes in Yields of the JNJ 2.450s of 09/01/2060. Observations Are from January 29, 2021, to May 14, 2021.   


<html><body><table><tr><td></td><td>Regression</td><td>Reverse Regression</td></tr><tr><td></td><td>0.842</td><td>0.921</td></tr><tr><td>Standard Error</td><td>2.00</td><td>2.09</td></tr></table></body></html>  

4See Equation (A6.15) in Appendix A6.1, which expresses the variance of the P&L as a quadratic in the Dv01s of each position..  

positions might have the same volatility, because they do not hold $\$100\mathrm{mil}$ lion in JNJ bonds, they are different trades. Most obviously, they do not satisfy the objective of buying $\$100$ million of JNJ bonds from a client. Less obviously, to the extent that the return profile of the JNJ and Treasury bonds differ, different portfolios of the two bonds have different return characteristics as well.  

In short, the regression hedge in Section 6.1 minimizes the variance of. hedging $\$100$ million face amount of the JNJ bonds. Trades with other objec-. tives, like holding a fixed amount of Treasuries or holding a fixed amount of volatility risk with particular return characteristics, are constructed. differently.  
