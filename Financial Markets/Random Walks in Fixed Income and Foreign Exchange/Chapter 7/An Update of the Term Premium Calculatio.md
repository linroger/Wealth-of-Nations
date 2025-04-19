---
tags:
  - interest_rates
  - monetary_policy
  - recession
  - term_premium
  - yield_curve
aliases:
  - Term Premium Update
  - Yield Curve Analysis
key_concepts:
  - Inverted yield curves
  - Monetary policy impact
  - Quantitative easing (QE)
  - Term premium measurement
  - Yield curve evolution
---

# Chapter 7 An Update of the Term Premium Calculation

# Introduction

Chapter 6 is simply a reproduction of the 2017 paper which introduced our model for the Term Premium. In 2019, we updated the results as yields fell to lower levels than ever before, and this chapter contains a further update where possible.' We were able to source data from a selection of different models to form a useful comparison.

# Evolution of Yield Curves

As explained in Chapter 6, the term premium is difficult to measure and extract from the other factors that determine the level and shape of the interest rate yield curve. With interest rates in many major economies dipping in and out of negative territory, even at longer-dated maturities, the term premium can now be the dominant factor that determines whether the yield curve slope is positive or negative. Inverted yield curves have historically been a harbinger of recessions and economic problems, as they signal that monetary policy is restrictive (short-term rates set by the central bank are higher than the market's equilibrium rate), and thus embody a market view of an economic slowdown ahead. Thus, it becomes a matter of critical interest to be able to extract the 'true' yield curve, the actual market view on future interest rate, separate from the term premium.

Figures 7.1 and 7.2 show the evolution of the USD and EUR yield curves, at quar. terly frequency, as a surface.

It is argued in Cohen et al. (2018), Li et al. (2017) and Swanson (2007) that the general lowering and flattening or even inversion of the yield curve as seen in Figures 7.1 and 7.2 is largely due to falling-term premia over the same period. Accordingly, studies (e.g. Haltom et al. [2018]) argue that curve inversions are no longer as valid a proxy for recessions as in the past, as the falling-term premium (and thus the curve flattening) relates to factors other than recessions fears.

The term premium is a critical element in monetary policy. For one, dissecting significant rate moves into changes in genuine rate expectations and varying risk premia is crucial for determining the policy response. While monetary policy can directly address short-rate expectations via rate cuts (and hikes), adjusting the term premium is primarily done via QE.

![](bd292e144b5787824b42cd79059b7eaeff7299553681062fa458abe44e4596c8.jpg)
Figure 7.1: Evolution of EUR yield curve, various tenors, in $\%$ Source: Bloomberg

![](a9339027aebe3fc94ac6d0a965ef6dd2ab2e710d2aa51ffdcefc917cb7625842.jpg)
Figure 7.2: Evolution of UsD yield curve, various tenors, in $\%$ Source: Bloomberg

Various papers conclude that monetary policy can only impact long-term yields by modifying term premia (Bernanke et al. [2005], Crump et al. [2016], and Kopp and Williams [2018]). Policymakers would like to know the likely impact upon longerterm yields of the volume and maturity of government debt they remove from the market via quantitative easing.

Policymakers could also refrain from countering a change in yields driven by changes in the term premium if it were deemed to be driven by factors outside its control, like the so-called savings glut (more savings chasing fewer investments in an ageing society), a general flight-to-safety or hedging demand from ALM investors. The same holds true for a shift in the market's risk assessment, which does not equate to unwarranted policy easing or tightening (note for example that regarding declining EUR inflation break-evens, the ECB frequently attributes these to a declining inflation risk premium, which does not warrant a policy response).

Investors would like to be able to capture the term premium and compare risk/. reward across currencies and asset classes, while a robust risk-free rate is a key. input into equity (and other DCF) valuation models. Likewise, issuers could under-. stand which parts of their funding costs reflect their unique credit profile and which. are simply due to fluctuations in the term premium (i.e. the fundamental market price of risk demanded by investors)..

Accordingly, the lack of clarity about variations in the term premium arising from various approaches to measuring it (i.e. model risk) makes the impact of rate cuts and non-standard measures even harder to predict than they would be otherwise.

Crucially, varying signals from different term premium models imply different. policy responses as well as relative value and valuation assessments. A good understanding of term premia values and their variation has seldom been more important than it is today.

# Term Premium Values Over Time

There have been a number of different attempts to calculate current and historical values of the term premium. A literature review might discover perhaps 15 separate. methods, some of these subdivided into several variants. The data that they are based on is varied; yield curves through time are of course popular sources of term premium information, but so are inflation, economic inputs, and surveys of market participants. What is surprising is not so much that they all give different results,. but that they all do tend to agree on overall shape and direction, to an extent. It is difficult to source live or even historical data for all of them, as many are not published in data form or updated, but for those which we could discover, we have graphed the results in Figure 7.3. Although most models in theory would give a term premium value as a function of tenor, in practice the 1Oy term premium is the most often calculated and published. Although it should be possible to generalise any model to any currency, in practice the US dollar tends to get most of the. attention.

![](24a558da7a27c0a819d6ee1a62a4f49a1f8f29a8b0d85b72028b0a9af006571c.jpg)
Figure 7.3: Term premium results, 10y term premium, in $\%$ Source: Bloomberg, Commerzbank Research, San Francisco Federal Reserve, St. Louis Federal Reserve, BlS Quarterly Report Sep 2018

Overall, it is certainly true to say that there has been a decline in term premium. values over time. All show a peak and then decline at the start of the millennium, and all show a spike and decline after the 2o08 crisis. After that period, there is a brief recovery in 2014, followed by an overall downtrend until the present day..

# Term Premium Models; Similarities and Differences

As can be seen in Figure 7.3, we have six separate models that give term premium results for a period since 2001. We can categorise them by the data that they use as inputs, as well as the pricing model and estimation technique to compute the pricing factors they use to create the final term premium number. Note however that not all of the models are quite up to date, as not all data were available for the most recent time.

Overall, those that include only yield curve data (like ACM and Coba) tend to be. the most volatile and perhaps the most responsive, though anomalous curve behaviour can translate into noisy results. Those models that access broader data sources, like Hordahl-Tristani, tend to be less volatile and give smoother returns..

1. HT: Hordahl-Tristani (Hordahl and Tristani [2014]) - Input data is nominal and real (index-linked) yields, inflation, survey data on future short-term interest rates and future inflation rates, and a measure of economic slack (the output gap). The method uses a forward-looking Phillips curve model. ACM: Adrian, Crump and Moench (Adrian et al. [2013]) - Uses only yield curve data as inputs. Uses an affine term structure model with principal components of bond yields as pricing factors that are assumed to follow an vector autore-. gressive (VAR) process.

3.KW: Kim-Wright (Kim and Wright [2005]) - Similar to ACM, but KW incorporates Blue Chip surveys of professional forecasters' short-rate expectations in the data set used to estimate the model. SPF: Survey of Professional Forecasters - This is a model-free estimate, calculated as the 10y yield minus the corresponding 10y average short rate expectation, as reported once a year by the Survey of Professional Forecasters (SPF). CR: Christensen and Rudebusch (Christensen and Rudebusch [2019]) - This model uses inflation-indexed US Treasuries (TIPs) and a dynamic term structure model. Coba: Commerzbank Research (see James et al. [2016] and Chapter 6) - This model takes swap rates as inputs but uniquely includes historical yields as well as current yields. The method assumes that forward rates, in the absence of a term premium, would be on average a good predictor of the future, and takes this forward error' to be a forward curve of the term premium spot curve.

It is useful to look at the volatilities of the different models to see how their construction and methodology affect their output. In Table 7.1, we see that the models that incorporate econometric data like HT have lower volatility, whereas those with only yield curve data like ACM and Coba are higher. Note that the SPF data is annual, so this figure is only from linear interpolation and is thus bound to be lower.

Table 7.1: Volatilities of term premium models, standard deviation of monthly changes in $\%$


<html><body><table><tr><td>Model</td><td>HT</td><td>ACM</td><td>KW</td><td>SPF</td><td>CR</td><td>Coba</td></tr><tr><td>St.Dev.</td><td>0.47%</td><td>1.05%</td><td>0.64%</td><td>0.53%</td><td>1.08%</td><td>1.00%</td></tr></table></body></html>

Source: Commerzbank Research

# Aggregating Model Results

Is there any utility in attempting to pin down the sources of the differences in levels that these models give? Can we approach a 'true' term premium any more closely? There are some useful discussion papers on this topic (for a good summary, see. Cohen et al. [2018]), but it seems that there is no consensus as to the 'best' one out there. All term premium estimates are model-dependent and are subject to parameter uncertainty. Some are not 'up to date' until a while after their initial publication, and values will change due to macro data revisions and delays. For example, in the case of the Coba model, it is not 'accurate' until there is a year of back-data included. (i.e. the initial forwards are realised and can be 'evaluated'), though before that time, the model gives approximate results.

Recent problems with econometric models have arisen where they need adjustment to cope with the relatively new phenomenon of rates being bounded at zero or slightly below it. Thus, we do not attempt to pick and choose, but it is interesting to look at an aggregation of available data and the degree of model variation as a function of time.

In Figure 7.4, we graph a simple average of the available models (the black line). For each month, we then calculate a standard deviation of the cross section of the model results (so, seven data points for each standard deviation calculation). Then we use this to put 1 standard deviation band around the monthly results. The bands provide an indication of the spread of model values at each point in time; wider bands indicate a greater degree of model 'disagreement'. Finally, the shaded grey area is the actual value of this standard deviation.

Unsurprisingly, there is significant noise around the 2008 financial crisis. After this, the models tend to agree more and more closely up to around 2016, with more divergence thereafter as yield curves entered often uncharted territory. What is notable, however, is the correlation between the level of standard deviation and rises in the term premium. The models seem to diverge more on the way up and achieve a degree of consensus on the way down.

It is clear that we are on a downward slope. Current values of the aggregated. term premium are headed for a record low, with models lining up to agree. Is the current decline to record lows in long-term yields due to (1) caution about the future and insurance-buying behaviour, or (2) is it just that the market has decided that policy normalisation is a long way off? If (1), then the term premium would be the dominant driver, but (2) would indicate that rate expectations are responsible..

![](0969f20af2a9e1bfa2fb7c05a0c50592b63896825e738ad68ac020939e882e4e.jpg)
Figure 7.4: Average 10y USD term premium, term premium averaged over models, with standard deviation bands. Source: Bloomberg, Commerzbank Research, San Francisco Federal Reserve, St. Louis Federal Reserve, BIS Quarterly Report Sep 2018
