---
tags:
  - fixed_income
  - libor
  - pca
  - principal_component_analysis
  - term_structure
aliases:
  - PCA
  - Principal Components
key_concepts:
  - Empirical description of behavior
  - Interest rate factors
  - Principal components
  - Regression hedging
  - Term structure
---

# 6.5 PRINCIPAL COMPONENT ANALYSIS  

As mentioned in the introduction to this chapter, regression hedging tends.   
to be ad hoc, because the relevant bonds and estimation periods are cho-.   
sen separately for each application. Principal component analysis is useful,.   
by contrast, in providing a single, empirical description of the behavior of.   
the term structure that can be applied across a portfolio of fixed income instruments.  

To illustrate PCA, this section uses daily data on fixed versus threemonth US Dollar (USD) LIBOR swap rates from June 1, 2020, to July 16, 2021.5 The data set consists of 13 times series, one for each of the terms from one to 10 years, as well as three with terms of 15, 20, and 30 years. These data can be summarized by the variances or standard deviations of changes in each rate and with their pairwise covariances or correlations. Another way to describe the data, however, is with 13 interest rate factors or components, where each factor represents a particular pattern of changes across the 13 rates. One factor, for example, might represent a simultane-. ous change of 0.2 basis points in the one-year rate, 0.6 basis points in the two-year rate, 1.2 basis points in the three-year rate, etc., up to 3.7 basis points in the 20-year rate, and 3.8 basis points in the 30-year rate. PCA is a way to construct 13 factors, or principal components (PCs), such that they have the following properties:  

1. The sum of the variances of the PCs equals the sum of the variances of the individual rates. In this sense, the PCs capture the volatility of the set of interest rates.  

2. The PCs are uncorrelated with each other. While changes in rates of one term are highly correlated with changes in rates of another term, the PCs are constructed so that they are uncorrelated.   
3. Subject to (1) and (2), each PC is chosen to have the maximum possible variance given all earlier PCs. Therefore, the first PC explains the largest fraction of the sum of the variances of the rates; the second PC explains the next largest fraction; and so forth.  

PCs of rates are particularly useful because of an empirical regularity: the sum of the variances of the first three PCs is usually an overwhelming fraction of the sum of the variances across all rates. Therefore, the variances and covariances of all rates are not necessary to describe how the term structure fluctuates: the structure and volatilities of only three PCs suffice. In the simplified context of three rates, Appendix A6.2 describes the construction of PCs in more detail. The text continues with a discussion of computed PCs. for USD LIBOR swaps from the data set described earlier.  

Figure 6.4 graphs the first three principal components, while Table 6.5 provides similar information in tabular form. Columns (2) to (4) correspond to the three PC curves in the figure, which can be interpreted as follows. A one standard deviation increase in the level' PC, given both in Column (2) and the solid line in the figure, is a simultaneous increase in the one-year rate of 0.23 basis points; in the two-year rate of 0.59 basis points; in the 10-year rate of 3.44 basis points; and in the 30-year rate of 3.77 basis points. On a particular day, the change in the term structure might be best explained as a 1.5 standard deviation move in the first PC, that is, as adding 1.5 times each element of the first PC to corresponding. swap rates. On another day, the change in the term structure might best be described as a $-0.75$ standard deviation move in the first component, that. is, as subtracting 0.75 times each element of the first PC from current rates. In any case, the first PC has been traditionally called the "level" component because it has typically represented an approximately parallel shift over much of its range. In the empirical results presented here, however, the component is not particularly level for terms from one to seven years..  

![](5ad58d05c4934711dabf1da5746fa9a0597e97b2989f70ac136bf0f608a0c082.jpg)  
FIGURE 6.4  The First Three Principal Components of USD LIBOR Swap Rates, Estimated from June 1, 2020, to July 16, 2021.  

TABLE 6.5 Principal Component Analysis of USD LIBOR Swap Rates from June 1, 2020, to July 16, 2021. Columns (2)-(6) Are in Basis Points; Columns (7)-(10) Are in Percent.   


<html><body><table><tr><td>(1)</td><td>(2)</td><td>(3)</td><td>(4)</td><td>(5)</td><td>(6)</td><td colspan="3">(7) (8) (9)</td><td>(10)</td></tr><tr><td></td><td colspan="3">PCs</td><td></td><td></td><td colspan="3">% of PC Variance</td><td rowspan="2">(5)/ (6)</td></tr><tr><td>Term</td><td>Level</td><td>Slope</td><td>Short Rate</td><td>PC Vol</td><td>Total Vol</td><td>Level</td><td>Slope</td><td>Short Rate</td></tr><tr><td>1</td><td>0.23</td><td>-0.16</td><td>0.29</td><td>0.41</td><td>0.55</td><td>32.7</td><td>15.0</td><td>52.3</td><td>74.54</td></tr><tr><td>2</td><td>0.59</td><td>-0.51</td><td>0.47</td><td>0.91</td><td>0.93</td><td>42.3</td><td>31.5</td><td>26.2</td><td>97.47</td></tr><tr><td>3</td><td>1.18</td><td>-0.99</td><td>0.42</td><td>1.59</td><td>1.60</td><td>54.5</td><td>38.5</td><td>7.0</td><td>99.63</td></tr><tr><td>4</td><td>1.77</td><td>-1.16</td><td>0.23</td><td>2.13</td><td>2.13</td><td>69.1</td><td>29.7</td><td>1.2</td><td>99.72</td></tr><tr><td>5</td><td>2.28</td><td>-1.12</td><td>0.02</td><td>2.54</td><td>2.54</td><td>80.6</td><td>19.4</td><td>0.0</td><td>99.78</td></tr><tr><td>6</td><td>2.64</td><td>-0.89</td><td>-0.13</td><td>2.79</td><td>2.79</td><td>89.7</td><td>10.1</td><td>0.2</td><td>99.91</td></tr><tr><td>7</td><td>2.94</td><td>-0.60</td><td>-0.20</td><td>3.01</td><td>3.01</td><td>95.6</td><td>4.0</td><td>0.4</td><td>99.97</td></tr><tr><td>8</td><td>3.14</td><td>-0.36</td><td>-0.24</td><td>3.17</td><td>3.17</td><td>98.2</td><td>1.3</td><td>0.6</td><td>99.96</td></tr><tr><td>9</td><td>3.31</td><td>-0.13</td><td>-0.25</td><td>3.32</td><td>3.32</td><td>99.3</td><td>0.2</td><td>0.6</td><td>99.92</td></tr><tr><td>10</td><td>3.44</td><td>0.07</td><td>-0.23</td><td>3.44</td><td>3.45</td><td>99.5</td><td>0.0</td><td>0.4</td><td>99.87</td></tr><tr><td>15</td><td>3.65</td><td>0.71</td><td>0.00</td><td>3.72</td><td>3.72</td><td>96.3</td><td>3.7</td><td>0.0</td><td>99.98</td></tr><tr><td>20</td><td>3.73</td><td>1.02</td><td>0.17</td><td>3.87</td><td>3.87</td><td>92.8</td><td>7.0</td><td>0.2</td><td>99.98</td></tr><tr><td>30</td><td>3.77</td><td>1.35</td><td>0.36</td><td>4.02</td><td>4.02</td><td>87.9</td><td>11.3</td><td>0.8</td><td>99.93</td></tr><tr><td>Total</td><td>9.99</td><td>2.92</td><td>0.96</td><td>10.45</td><td>10.47</td><td>91.3</td><td>7.8</td><td>0.8</td><td>99.84</td></tr></table></body></html>  

A one standard deviation increase in the "slope' PC, given both in Column (3) of the table and the dashed line in the figure, is a simultaneous fall in the one-year rate of 0.16 basis points; a fall in the two-year rate of 0.51 basis points; an increase in the 10-year rate of 0.07 basis points; and an increase in the 30-year rate of 1.35 basis points. This PC is said to represent a "slope" change in rates because shorter-term rates fall while longer-term rates increase, or vice versa.  

Lastly, a one standard deviation increase in the "short-rate" PC, given both in Column (4) of the table and the dotted line in the figure, is a. simultaneous small increase of very short-term rates; a small decrease in intermediate-term rates, and a small increase in long-term rates. Because of. its shape across terms, this PC is often named "curvature" as well, but, in.  

light of the full discussion in this section, this PC is particularly useful for adding explanatory power to variations in shorter-term rates.  

To reiterate the sense in which the PCs describe changes in the term structure, on a given day, changes across terms might be described - picking. numbers at random - as the combination of: a $+1.5$ standard deviation change in the first PC; a $-0.4$ standard deviation change in the second PC; and a $-1.8$ standard deviation change in the third PC. The term structure at. the end of that day, therefore, would approximately equal the term structure at the end of the previous day plus the contributions from the multiples of each of the three PCs. In this way, as explained shortly, these three PCs can indeed explain an overwhelmingly large proportion of realized term struc-. ture volatility.  

The small values of the PCs at very short-term rates reflect the low volatility of these rates. In the current financial environment, with the Fed-. eral Reserve promising to keep short-term rates low for an extended period of time, current economic shocks are not envisioned as impacting short-term rates until some time in the future. As a result, economic volatility is not reflected in very short-term rates but seeps gradually into intermediate- and longer-term rates as expectations of reactions to future Federal Reserve policy actions.6  

Column (5) of Table 6.5 gives the combined standard deviation or volatility from the three principal components for each rate, while Column (6) gives the total, empirical volatility of each rate over the sample period. For the five-year rate, for example, recalling that PCs are, by construction, uncorrelated, the volatility from the three PCs is,  

$$
\sqrt{2.28^{2}+(-1.12)^{2}+0.02^{2}}=2.54
$$  

The total volatility of the five-year rate in the sample is also, to two decimal places, 2.54, but Column (10) - using more decimal places than shown in Columns (5) and (6) - reports that the ratio of five-year PC volatility to total volatility is $99.78\%$ . Hence, the empirical variation of the five-year rate. is almost completely explained by the first three PCs. Considering Column (10) as a whole, three PCs explain over. $99\%$ of the variation of rates of all.  

terms greater than three years, $97.47\%$ of the variation in the two-year rate, and $74.54\%$ of the variation in the one-year rate. Hence, although there are 13 rates in the data series, three factors alone - three fixed combinations of changes in rates across terms -- go a very long way in explaining the variation in all 13 rates. This is possible, intuitively, because changes in rates across terms are highly correlated; that is, nowhere near 13 factors are actually necessary to explain the variation in 13 rates. The performance of the three factors is less impressive, however, for rates of the shortest term.  

Columns (7) through (9) of Table 6.5 give the variance explained by each of the first three PCs as a fraction of the total variance explained by those three PCs. For the two-year rate, for example, those fractions are calculated as follows,  

$$
\begin{array}{r}{\frac{0.5916^{2}}{0.9091^{2}}=42.3\%}\ {\frac{(-0.5101)^{2}}{0.9091^{2}}=31.5\%}\ {\frac{0.4650^{2}}{0.9091^{2}}=26.2\%}\end{array}
$$  

Note that, to avoid confusion, the values in these equations are reported to greater accuracy than those in the table.  

Looking at Columns (7) to (9) across terms, the level PC dominates the other two as the main contributor to variations in the term structure. The short-rate PC, and then the slope PC, are significant contributors at the short end, however, as is the slope PC for the longest rates. These finding have significant implications for risk management. A trader of eight- to. 10-year swaps, or perhaps even seven- to 15-year swaps, can defend using the one-factor metrics and hedging approaches of Chapter 4 and one-variable. regression hedging described in this chapter: according to Table 6.5, in this. range of terms, term structure variation can be well described by a one-factor. model, like the level PC. On the other hand, traders in the three- to six-year sector or the long end might very well require two factors, while traders in the very short end may not be comfortable without a three-factor framework.  

The last row of Table 6.5 computes the various statistics just discussed across the whole term structure of rates. More specifically, Columns (2) to (6) give the square root of the sum of variances across terms, and Columns (7) to (9) give the respective ratios for these totals. While the sum of variances is not a particularly interesting economic quantity - it does not represent the variance of any particularly interesting portfolio - the last row of the. table does summarize two overall results of the PCA. First,. $99.84\%$ of the  

volatility of the 13 rates in the study is explained by the first three PCs.   
Second, the level PC explains over $90\%$ of that variance, the slope PC about.   
$8\%$ , and the short-rate PC less than. $1\%$  

The overall lessons from PCA are often similar across global markets. Estimated over the same time period as the USD PCs in Figure 6.4, Figures 6.5 and 6.6 graph the first three PCs of British Pound Sterling (GBP) LIBOR and Euribor swap rates, respectively.7 The GBP PCs are extremely similar to their USD equivalents, with respect to both shape and. magnitude. The biggest difference seems to be that the slope PC in USD is. more volatile. The shapes of the EUR PCs are qualitatively similar to those in USD and GBP, but volatility in EUR is significantly lower. The EUR level. PC, for example, flattens in the long end at a bit above 2.5 basis points per day, whereas the USD and GBP level PCs flatten at over 3.5. This lower volatility might be explained by the current aggressiveness of the European. Central Bank, relative to the Federal Reserve and the Bank of England, to keep short-term rates low over an extended period of time..  

Hedges based on PCA are constructed like the multi-factor approaches of Chapter 5. Using the current term structure, calculate the current price of the portfolio being hedged; shift the current term structure by each PC,. in turn, to get new term structures and new portfolio prices; with these new prices, calculate a portfolio $^{\ '}01$ with respect to each PC; and find a portfolio of hedging securities that neutralizes these $^{\circ_{1s}}$  

![](dbfd19bb35f2a8449580b4b5e9360b13639aa5269a1fee901d12c4b7b3d238e8.jpg)  
FIGURE 6.5 The First Three Principal Components of GBP LIBOR Swap Rates, Estimated from June 1, 2020, to July 16, 2021.  

![](f37d77ceed15875bdf839f15d87fef50c9027d54b262177e09d1d147619f062e.jpg)  
FIGURe 6.6 The First Three Principal Components of Euribor Swap Rates, Estimated from June 1, 2020, to July 16, 2021.  

IABLE 6.6USD LIBOR Par Swap Rates and DV01s, as of July 16, 2021, and PC Elements from Table 6.5. Rates Are in Percent, and PC Elements Are in Basis Points.   


<html><body><table><tr><td>Term</td><td>Rate</td><td>DV01</td><td>Level</td><td>Slope</td><td>Short Rate</td></tr><tr><td>10</td><td>1.303</td><td>0.09347</td><td>3.44</td><td>0.07</td><td>-0.23</td></tr><tr><td>15</td><td>1.501</td><td>0.13387</td><td>3.65</td><td>0.71</td><td>0.00</td></tr><tr><td>20</td><td>1.596</td><td>0.17064</td><td>3.73</td><td>1.02</td><td>0.17</td></tr><tr><td>30</td><td>1.646</td><td>0.23600</td><td>3.77</td><td>1.35</td><td>0.36</td></tr></table></body></html>  

This section illustrates hedging with PCA in a context described earlier,. namely, hedging a relative value 10s-20s-30s butterfly, but this time in swaps. Specifically, a trader believes that USD 20-year swap rates are too high relative to 10- and 30-year swap rates, and plans, therefore, to receive fixed in 20s and pay in 10s and 30s. Par swap rates and Dv01s of par swaps are. given in Table 6.6. Also, corresponding to rates of the listed terms, the table gives the elements of each of the three PCs from Table 6.5. By definition, a. one standard deviation shift in each PC changes these swap rates by these PC elements. The inclusion of the 15-year swap rate is discussed later.  

Assume that the trader plans to receive fixed on 100 notional amount of the 20-year swap and on $F^{10}$ and $F^{30}$ notional amount of 10- and 30-year swaps, respectively. Paying fixed is reflected, in this notation, with negative notional amounts. In any case, from the data in Table 6.6, the exposure of this overall relative value portfolio is hedged against a one standard deviation shift of the level and slope PCs, respectively, if the following equations obtain,  

$$
\begin{array}{r l r}&{}&{-F^{10}\displaystyle\frac{0.09347}{100}\times3.44-F^{30}\displaystyle\frac{0.23600}{100}\times3.77-100\displaystyle\frac{0.17064}{100}\times3.73=0}\ &{}&{\quad\quad\quad\quad\quad\quad(6.309347)\times0.07-F^{30}\displaystyle\frac{0.23600}{100}\times1.35-100\displaystyle\frac{0.17064}{100}\times1.02=0}\end{array}
$$  

The first two terms of Equation (6.30) give the change in the value of the. hedge position under a one standard deviation shift of the first PC, that is,. a shift of $+3.44$ basis points in the 10-year and. $+3.77$ basis points in the. 30-year swap rate. The third term gives the change in the value of the position being hedged under the same PC shift, which is $+3.73$ basis points in the 20-year swap rate. Note that the negative signs indicate that receiving. fixed (i.e., positive notional amounts) when rates increase results in position losses. The equation as a whole, therefore, sets the total position gain. or loss under a one standard deviation shift of the first PC equal to zero. Equation (6.31) can be interpreted similarly, but under a one standard deviation shift of the second PC. Note, of course, that if these two equations hold for a one standard deviation shift, they hold for any size shift: to see this, simply multiply both sides of each equation by the intended number of. standard deviations.  

Solving Equations (6.30) and (6.31) reveals that. $F^{10}=-49.56$ and $F^{30}=$ -53.60. Or, in terms of risk weights relative to the DV01 of the 20-year swap,  

$$
\begin{array}{r l}&{\frac{49.56\times\frac{0.09347}{100}}{0.17064}=27.1\%}\ &{\frac{53.60\times\frac{0.23600}{100}}{0.17064}=74.1\%}\end{array}
$$  

Intuitively, most of the risk of the 20-year swap - $74\%$ - is hedged with 30-year swaps, because the exposures of 20-year swaps to both the level and slope PCs more closely resemble those of 30-year swaps than of 10-year swaps. Note also that the sum of the risk weights is $101.2\%$ , so that the DV01 of the hedge position is greater than the DV01 of the position being. hedged. Only under the assumption of parallel shifts do the risk weights always sum to $100\%$ . In the present case, more Dv01 risk is needed in the hedge because the hedge includes a significant amount of 10-year swaps,.  

which are much less sensitive to the level and slope shifts than the 20-year swaps.  

In this illustration, the trader chooses to hedge with 10- and 30-year swaps. But, with only two hedging securities, the risks of only two PCs can be hedged. What is the risk of the hedged position just derived to the next most important PC, that is, the short-rate or curvature PC? Following the same logic as in Equations (6.30) and (6.31), the exposure of the hedged position to the third PC (adding a significant digit to avoid confusion) is,  

$$
{\begin{array}{r l}&{-(-49.6){\frac{0.09347}{100}}\times(-0.228)-(-53.6){\frac{0.23600}{100}}\times0.360}\ &{-100{\frac{0.17064}{100}}\times(0.166)=0.007}\end{array}}
$$  

which is less than one cent per 100 face amount. The trader might very well decide, therefore, that it is not worth the transaction costs of trading an additional swap to hedge out this residual risk from the third PC. Also, because this is a relative value trade, the trader wants to pay fixed only in swaps with. rates that are believed to be too low. In any case, if hedging out the residual risk is desired, a 15-year swap can be added to the hedging portfolio; an equation for exposure to the third PC can be added to Equations (6.30) and (6.31); and, using the data from Table 6.6, the notional amounts for the 10-, 15-, and 30-year swaps can be determined. This is left as an exercise for the reader.  

# Arbitrage Pricing with Term Structure Models.  

fore, assumptions about how these few factors evolve over time, combined with arbitrage arguments, can deliver strong predictions about the prices and interest rate sensitivities of bonds and other interest rate contingent claims (i.e., securities with cash flows that depend on interest rates, like bond options). Formulating assumptions about the evolution of interest rate factors, pricing fixed income securities, and determining hedge ratios comprise the art and science of term structure models.  

Term structure models are presented in three chapters. This chapter uses a very simple setting to show how assumptions about the evolution of the short-term rate over time allows for the arbitrage pricing of bonds of all maturities and of interest rate contingent claims. Option-adjusted spread (OAS) is introduced both as a metric of a security's mispricing relative to a model and as the spread that can be earned - if the model is correct - by trading that security. Chapter 8 shows how the shape of the term structure is determined by: expectations about future short-term rates, the risk premium required by investors to bear interest rate risk, and convexity, whose effect is a result of interest rate volatility. Chapter 9 then illustrates the art of modeling the evolution of short-term rates by presenting two term structure models: the classic Vasicek model and the two-factor $\mathrm{Gauss+}$ model, which has proven popular in industry for both relative value and macro-style trading.  
