---
tags:
  - estimation_method
  - mean_reversion
  - term_structure
  - volatility_parameters
  - zero_yields
aliases:
  - Gauss Model
  - Practical Estimation
key_concepts:
  - Estimating model parameters
  - Mean reversion parameters
  - Regression coefficients
  - Term structure of volatilities
  - Volatility and correlation
---

# 9.3 A PRACTICAL ESTIMATION METHOD  

The estimation method presented here proceeds in stages, with each stage estimating a subset of the model's parameters.4.  

Figure 9.5 shows the coefficients of regressing the changes in the zero. yields of various terms on changes in the two-year zero yield -- the dark gray. bars - and on changes in the 10-year zero yield - the light gray bars. For example, the regression of the three-year yield gives a coefficient of 0.91 on the two-year yield and 0.22 on the 10-year yield. By contrast, the regression of the 15-year yield gives a coefficient of. $-0.20$ on the two-year yield and 1.10 on the 10-year yield. In any case, as explained before, all these regression coefficients implicitly describe the mean reversion parameters of the model. This stage of the estimation, therefore, chooses the parameters. $\alpha_{r}$ $\alpha_{m}$ and $\alpha_{l}$ so that the model captures the empirically observed regression coefficients as closely as possible. This staging is possible, because, as shown in the appendix, the model regression coefficients depend only on the mean reversion parameters, not on the volatility parameters. In any case, the mottled dark and light gray bars in Figure 9.5 show the success of this stage of the estimation. There are a set of mean reversion parameters, given hereafter, such that implied regression coefficients from the model very closely match the empirically observed regression coefficients. And, while not reported here, these matches are within statistical confidence intervals..  

The next stage of the estimation is to find the volatility and correlation parameters, $\sigma_{m},\sigma_{l}.$ and $\rho$ , so that the term structure of volatilities in the. model matches the term structure of volatilities in the data as closely as pos-. sible. The result of this optimization is shown in Figure 9.6. Once again, the model is flexible enough to do an excellent job of matching empirical properties of the term structure of interest rates..  

![](4e93bb2862cac156232fe746a3c229e9531d0f62f856be76a6a5ff3e7ef5fe2b.jpg)  
FIGURE 9.5 Coefficients of Regressing Zero Coupon Bond Yields of Various Terms on Two- and 10-Year Zero Coupon Bond Yields, from Empirical Analysis and as Implied by the Estimated Gauss $^{\ast}$ Model.  

![](4141108656ce7e2c87414b4fe5dd20e09b092fcce8b0402a369d1741c6a66a89.jpg)  
FIGURe 9.6 Yield Volatility in Annual Basis Points, from Empirical Analysis and as Implied by the Estimated Gauss $^+$ Model.  

The last remaining parameter to be estimated is $\mu$ , the value to which the short-term rate reverts, over the very long-term. The estimation procedure suggested here finds the $\mu$ that minimizes the sum of the squared errors of. observed yields relative to model yields across the whole data sample..  

Following the estimation procedure described, Table 9.1 reports the resulting Gauss+ parameter values. The mean reversion parameters are in the order expected, with the central bank reaction fastest, the speed of the medium-term factor's reversion to the long-term factor next, and the speed of the long-term factor's reversion to $\mu$ slowest. Alternatively, the time for each process to converge halfway to its target, given in the half-life column, is about eight months for $r$ , 13 months for $^m$ , and 42 years for l. Because of the mean reverting nature of the factors, the volatility parameters of 109 and 96 basis points for the medium- and long-term factors, respectively, translate into the lower zero yield volatilities shown in Figure 9.6. The parameter. $\mu$ as the very long-run target for the short-term rate, might seem high at over $10\%$ , but the long-term factor reverts very slowly to this target, and that. target includes a risk premium, which is discussed further next.  

The term-structure properties of the estimated model are well described by Figure 9.7, which graphs the change in forward rates for a change in each of the factors as a function of term. For example, the seven-year forward, changes by 0.9 basis points for every basis point change in the long-term. factor. Taken as a whole, the figure shows that short-term factor affects only. the very short end of the curve. The medium-term factor, which drives the two- to three-year part of the curve, can be thought of as capturing monetary policy in the sense of encapsulating where the market believes the short-term. rate will be in two to three years. The long-term factor has its biggest impact in six to eight years and, beyond 10 years, is the sole factor driving forward rate changes and volatilities.  

The time series properties of the model can be described by graphing its. factors over time. As mentioned already, the short-term rate is set each day to the fed funds target rate, and the medium- and long-term factors are set so as. to match the model and market two- and 10-year forward rates. Figure 9.8. graphs these empirically recovered market factors from January 2007 to January 2022.5 The two-year forward rate is included in the graph to focus. the interpretation of the medium-term factor. When rates are high, this factor. closely tracks the two-year forward rate, confirming that the medium-term factor loosely corresponds to where the market expects the short-term rate to be in two years. When rates are low, however, near the zero lower bound, the medium-term factor can fall into deeply negative territory. In this sense, the medium-term factor is a "forward shadow rate" that reflects future expecta-. tions of the short-term rate and that can be traded explicitly in the Gauss+. model. This interpretation differs from models in which the "shadow rate" is what the short-term rate would be now if it were not bounded above zero.6  

TABLE 9.1 Estimated Parameters of the Gauss+ Model from US Treasury Zero Coupon Yields,. January 2014 to January 2022. Half-Life Is in Years.   


<html><body><table><tr><td>Parameter</td><td>Estimate</td><td>Half-Life</td></tr><tr><td>α</td><td>1.0547</td><td>0.66</td></tr><tr><td>αm</td><td>0.6358</td><td>1.09</td></tr><tr><td>10</td><td>0.0165</td><td>42.01</td></tr><tr><td>Om</td><td>109.2 bps</td><td></td></tr><tr><td>10</td><td>96.4 bps</td><td></td></tr><tr><td>p</td><td>0.212</td><td></td></tr><tr><td>μ</td><td>10.555%</td><td></td></tr></table></body></html>  

![](568047deef43012b4c4193d6e3443939c920456dfbd586708624364a44e087f1.jpg)  
FIGUre 9.7 Changes in Forward Rates Relative to Changes in the Short-Rate, the Medium-Term Factor, and the Long-Term Factor in the Estimated Gauss $^{+}$ Model.  

![](e1f2195674711e0eb5d2abbebd25dfde7fa343bb72ae7e2fa9802d11e2de20b3.jpg)  
FIGURE 9.8 The Two-Year Forward Rate and Gauss $^+$ Factors Extracted from Daily Market Data.  

In any case, the nature of the medium-rate factor as a leading indicator of the short-term rate can be seen by comparing those two series in Figure 9.8. Particularly striking is the steep increase in the medium-term factor starting in early 2014, a couple of years before the Federal Reserve began raising rates.  
