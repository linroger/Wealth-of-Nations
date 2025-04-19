---
tags:
  - factor_exposure
  - forward_rates
  - gauss_model
  - macro_trading
  - relative_value
  - term_structure
aliases:
  - GAU Model
  - Macro-Style Trading
  - Relative Value Trading
key_concepts:
  - Factor exposure minimization
  - Forward rate convergence
  - Macro trading factors
  - Mean reverting trades
  - Relative value trade
  - Term structure model
---

# 9.4 RELATIVE VALUE AND MACRO-STYLE TRADING WITH THE GAU $\S\S+$ MODEL  

In the context of a term structure model, a relative value trade is one that is not exposed to or hedged against changes in the factors. Ideally, a trader would find an individual security that is cheap relative to the model and, from various analyses, is expected to revert soon to being fair to the model. The trader would then buy that security; hedge some or all of its factor exposure by selling fair or rich securities in the same part of the curve; and earn the resulting profits. In practice, however, individual securities are often persistently cheap or rich to the model, so that convergence is not expected in the short run, and securities neighboring in term are often all fair or rich together. Most of the time, therefore, relative value opportunities arise in which a trader receives forward rates in one part of the curve that are high relative to the model but expected to converge promptly to the model; pays forward rates in another part of the curve that are too low, but expected to converge promptly; and structures trades to minimize factor exposures. In this synopsis, the speed at which any detected mispricing is likely to correct itself is an important trading consideration.  

As an example of using the Gauss $+$ model along these lines, consider the following framework. Compute the time series of the nine-year forward rate minus the model-predicted equivalent rate, where each observation can be called a fitting error. Then construct a signal from this times series as the difference between its five-day and 40-day moving averages. If the demeaned fitting error at a given time is positive, so that the nine-year forward is too high relative to the model, and if the signal is negative, so that fitting errors have started to fall, that is, they have started to converge to the model, then receiving at that forward rate might be considered an attractive trade.  

The problem with receiving or paying the nine-year forward in isolation, however, is that it has significant exposure to the medium- and long-term factors, which is not consistent with the spirit of relative value trading. One solution is to pool together and size several attractive relative value trades so that their exposure to the factors is minimal. In addition, traders can diversify across mean reverting trades. It turns out, for example, that nineand five-year fitting errors tend to be positively correlated. This fact makes it attractive to pay in one rate and receive in the other. Figure 9.9 shows, in fact, that the difference between the nine- and five-year signals is strongly mean reverting, which is one of the most important properties of relative value trades.  

Unlike relative value trading, which finds value in the absence of factor exposure, macro trading takes direct or indirect views on the factors. Simple examples include positions based on predictions of changes in rates or in the slope of the term structure that differ from what is priced in the market. A more complex example, which has attracted more interest over time, is trying to trade the long-run level of the short-term rate. As explained earlier,. long-term forward rates are a combination of expectations, risk premium, and convexity. Within the structure of the Gauss $^{+}$ model, with the help of a strategic assumption, long-term forward rates can be separated into these three components. A macro trader can then decide that long-term forwards. are too low or too high and position accordingly. The details of this decomposition of forward rates are complex and, therefore, appear in the appendix to this chapter. The text continues with an intuitive approach.  

In the context of any term structure model, it is relatively straightforward to determine the effect of convexity on forward rates. It is much more difficult, however, to separate expectations from risk premium. A number of approaches appear in the academic literature, but these are not without various shortcomings.7 The method proposed here relies on one key assumption: expectations of future short-term rates do not change past some point in the. future. Anyone with a view of the short-term rate in 15 years, for example, has the same view of the short-term rate in 20 or in 30 years. Consequently,. any difference in forward rates beyond some term is attributable not to rate expectations, but solely to risk premium and convexity. In this way, expectations and risk premium can be separated and calculated from observable rates.  

![](8a806d299c2d1cab3c50e043b449b257548240755122b67c9cda2fa7dda888da.jpg)  
FIGUrE 9.9 Difference Between the Nine- and Five-Year Signals. Each Signal Is Based on a Difference of Moving Averages of Deviations of Market from Gauss $^{+}$ Model Rates.  

Using the assumption just described and the parameters of the Gauss+ model estimated previously, Figure 9.10 graphs the risk premium on the  

10-year forward rate over time, measured along the left axis. A value of 60 basis points on any day, for example, means that, on that day, 60 basis points of the 10-year forward rate is attributable to risk premium. The lighter. line is the level of the 10-year forward rate, measured along the right axis. The risk premium often moves in the opposite direction of rates. As rates decline, the term structure typically steepens, which the model interprets as. an increase in risk premium. This observed behavior is consistent with the. low-inflation regime over the last several decades, in which government bond prices increase as other risky assets fall in value. In that environment, as rates fall, and have less room to fall even further, bonds are less able to hedge the. declining value of other assets and, as a result, are worth less themselves.  

The flip-side of identifying the risk premium, of course, is identifying the long-run expectation of the short-term rate in the estimated Gauss+ model, more specifically, the 10-year forward rate minus the term-appropriate risk premium plus the term-appropriate convexity. The time series of this expectation is shown in Figure 9.11, along with a different estimate, formed from real rate forecasts and inflation estimates at the Federal Reserve Bank of Cleveland.8 while the model and outside series track each other quite well over time, there are trading opportunities to use the difference between the two series as a measure of value. Put another way, the difference between the  

![](731241e3e386cd6c1014cec4cd2b100e29e2b5648b45142e7b555c4bf2d1f534.jpg)  
FIGURE 9.10 Estimated Risk Premium on the 10-Year Forward Rate.  

![](4392cd1e6281cb4c2500757cecc410fe68bf13d228855fda38dfde6b6322d01a.jpg)  
FIGurE 9.11 Long-Run Expectations of the Short-Term Rate, as Implied by Gauss $^{\ast}$ Fitted to Market Rates and by Fundamental Analysis at the Federal Reserve Bank of Cleveland.  

Gauss $^{+}$ market-implied view -- the long-run rate priced in the market - and. the exogenous, economist-generated, fundamental view - what one thinks the long-run rate should be - can be used as a basis for taking outright long. or short positions in bonds..  

# Repurchase Agreements and Financing  

funds (MMFs) and other investors rely on repo as a short-term, liquid asset; broker-dealers and other financial entities use repo to fund their inventory of securities; repo enables market participants to take short positions in fixed income markets; and, as described in Chapter O, the Federal Reserve has historically and continues presently to use repo to conduct monetary policy.. Finally, and most recently, interest rate derivatives and many loan products are transitioning from the London Interbank Offered Rate (LIBOR) indexes to the Secured Overnight Financing Rate (SOFR), which is derived from rates on repo transactions..  

The first few sections of the chapter describe repurchase agreements, the. uses of repo, and the structure and size of the market. A short section then describes the computation of the recently prominent SOFR, a rate featured in Chapters 2, 12, and 13. The subsequent section explains some of the determinants of the interest rates on both general collateral (GC) and special repo transactions. The penultimate section discusses repo in the context of financing risk, along with relevant changes in banking regulation. The final section. is a case study of how MF Global fell in large part due to its inappropriately. sized "repo-to-maturity" trades.  
