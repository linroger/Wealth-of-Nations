---
tags:
  - forward_rates
  - interest_rates
  - monetary_policy
  - term_premium
  - yield_curve
aliases:
  - Calculating Term Premium
  - Term Premium Calculation
key_concepts:
  - Forward rate errors
  - Interest rate risk
  - Monetary policy impact
  - Term premium importance
  - Yield curve slope
---

# Chapter 6 An Empirical Method of Calculating the Term Premium

Interest rates tend to be higher for longer term instruments, reflecting the additional risk to the lender of longer term loans. Essentially, over a long period, unpredictable and unforeseeable risks accumulate, and the lender (usually) demands an additional return to their capital to compensate for this. This is one explanation for the tendency of yield curves to in general slope upwards. While simple in theory, this term premium is not directly observable and more difficult to measure than one might expect. We present a straightforward empirical calculation method using forward rate errors which works for all liquid currencies and has excellent correlation with more complex methods.

# Introduction

The term premium is important for investors, issuers and policy makers.' Negative rates emphasise the question of whether global fixed income benchmarks expose investors to rate-free risk rather than risk-free returns. Capturing the term premium. allows investors to compare risk/reward across asset markets, and issuers to under-. stand their funding cost and manage their primary market activities. For central banks, variations in the term premium can complicate the transmission of monetary. policy, thus rendering the impact of actions like rate cuts and non-standard measures difficult to predict. This is particularly relevant as reducing long term interest rates and pushing investors into higher yielding assets via a lower term premium is typically cited as a central argument for quantitative easing, most recently by ECB Chief Economist Praet [16].

And, the term premium adds significant uncertainly to the various forecasts which derive from interest rate term spreads. So it is more difficult to influence interest rates, and more difficult to predict the effect of the adjusted rates!

The term premium also relates to economic activity. Various studies connect term premium to GDP and to the probability of recession; however, difficulties in separating term premium from market expectations mean that there is disagreement over its exact effects [11].

Our method has various advantages. The term premium is notoriously difficult to. measure given the interaction with other unobservable yield components, model uncertainty and data issues. We have derived a method of calculating the term premium. by using the 'forward errors' from the swap curve i.e., understanding how moves pre-. dicted by forward rates differ from actual realised moves, as an average over time.. This allows us to easily discover the term premium for any currency and tenor..

# Why is the Term Premium Important?

It has been observed for many years that interest rates are higher for longer term instruments. Besides expectations regarding future short term rates, this reflects the additional risk to the lender compared to rolling over short term instruments and, in liquid markets, the higher price sensitivity of longer-dated bonds or swaps. The difference between genuine short rate expectations and the observable yield is called the term pre-. mium. On the surface it seems to be a simple concept and makes intuitive sense; the. normal upwards sloping shape of yield curves is due to expectations of future moves,. overlaid onto a term premium curve. Some definitions then further separate the term premium component into a part due to inflation expectations and a pure term risk part..

The term premium turns out to be both more important, and less easy to calcu-. late, than might initially be supposed. In the next sections we will focus on calcula-. tion methods; in this section, we discuss why it would be very useful to have a robust term premium estimate, not only for investors but also for policy makers at Central Banks and other governmental institutions.

Time variation in term premium complicates the transmission mechanism of monetary policy. Central banks would like to be able to influence the longer term interest rates most relevant for the decisions of households and businesses [1o]. A historical example would be the tightening of monetary policy in the USA from 2004 to 2006; this was offset in the long end by a fall in rates which was largely attributed to a fall in term premiums. In 2005 Fed Chairman Greenspan suggested that "a significant portion of the sharp decline in the 1Oy rate 1y forward over the past year appears to have resulted from a fall in term premiums". His successor in 2006, Ben Bernanke, appeared to agree, stating "When the term premium declines, a higher short term rate is required to obtain the long term rate and overall mix of financial conditions consistent with maximum sustainable employment and stable prices." [1].

The term premium has become highly relevant in the current era of unconventional policy measures amid very low or negative rates and flat curves. Policy makers would like to know the likely impact upon longer term yields of the volume and maturity of government debt they remove from the market via quantitative easing. The results would also have implications for the exit from such measures, as well as the links between monetary and fiscal policy and debt management. Various studies (see [15] for an excellent overview) show that increases in central bank holdings of debt can significantly reduce the term premium, and forcing investors into higher yielding assets via a lower term premium is typically a key argument for quantitative easing. The ratio of privately held to total outstanding debt is also significant.

Term premium adds significant uncertainly to the various forecasts which derive from interest rate term spreads. Many models, some used by policy makers, use term spreads for recession and economic activity forecasting [11]. An inverted yield curve has from the 1970s been a leading indicator of a slowdown. However, a yield curve inversion, especially when overall levels of rates are low, could well be driven more by term premium effects than by 'true' inversion; a forecasting. model which separates the components would be very valuable. In an Economic Letter from the San Francisco Fed, [4], it is stated that "understanding long term interest rate fluctuation requires on to understand what the term premium is and how it may change over time." The BIS agrees; in one Quarterly Review, we read that "The term structure of interest rates can be an invaluable source of information to Central Banks . ... However, this requires separating expectations of future interest rates from the term premium." [12]

Term premium may relate to economic activity. Some studies suggest that the term premium may help to forecast GDP [13], though uncertainties as to how to measure it mean that different methods disagree about whether it is procyclical or countercyclical! More recently [14] Ben Bernanke stated "Researchers have found that term premiums tend to rise in recessions; they also rise in periods in which there is greater disagreement among economic forecasters."

An understanding of the term premium could be very useful for positioning.. Carry strategies and yield curve trades become possible once term premium and. market expectations can be reliably separated (it is essentially the term premium that makes carry strategies profitable in the long-run). A good term premium. model would hence be of significant interest to investors and hedgers. The same holds for issuers as it allows a decomposition of the respective funding costs. and hence better management of primary market activities (e.g. by taking advantage of low/falling term premiums)..

# The Term Premium and Forward Rates

While the concept of a term premium is simple in theory, its consequences in a world. of liquidly traded instruments of varying tenors are interesting (as it were . . .). More-. over, it is not directly observable and thus has to be estimated. The yield curve, available in all liquid currencies, describes interest rates as a function of tenor, and a natural product of this is the construction of forward interest rates; the arbitrage-free contracts for borrowing or lending in the future..

The calculations for forward rates are trivial, complicated only by coupon frequency and day count conventions. As a simple example, a 1 year investment must be equivalent to two consecutive 6 month investments, where the proceeds of the first are invested into the second. This defines the forward rate available for the second 6 month investment.

But, these forward rates can be interpreted as the market 'prediction' of what will.. occur. If there were no term premium, then it is feasible that these predictions could be the market's best guess for the future. As it is, the yield curve embodies at least two drivers; a view on the future, and the term premium. It is also driven by credit and liquidity variations as well as inflation expectations, but at this stage we would like to. consider these as included in the 'view on the future' part and not the term premium.

We would like to be able to assign values for the term premium. Part of the difficulty of doing this is that it is unlikely to stay constant; at least a slow variation through time is to be expected, possibly with faster changes during market crises. But overall we would expect it to change only slightly from one period to the next. If we had values for the term premium, then we might expect a degree of predictive power from the forward rates, as they are likely to embody all available information about future interest rate regimes.

This paper suggests a relatively simple way of extracting an empirical term premium from forward rates, which agrees well with more complex methods.

# An Empirical Method for Determining the Term Premium

# Calculation Method

The problem with calculating the term premium is that, although it is a simple con cept, it is difficult to calculate. Consider a yield curve today. It forecasts its own evolution. Which is the timescale to consider? A month ahead, a year, five? We have market rates going out to 30 years, and forward rates going out beyond that. The entire spot and forward curve structure on any one day are mathematically related by arbitrage constraints. In addition, the term premium interacts with other unobservable components of nominal yields like liquidity and inflation (risk) premia, and separating these is not straightforward.

To account for these issues while fitting across time series is not simple, and various models of the term structure must be assumed. An empirical method which works mostly in the data space would be useful and much easier to use, if available.

We would like to find the adjustment which makes the curve today an unbiased predictor of the curve in the future. Let us say that we start on average with the black central curve on the following illustration in Figure 6.1, which predicts the yellow forward curve at a time in the future. In fact, at that future time, the actual rates are more like the grey curve. We have added some scatter to show that there is considerable variation in both. To be strict we ought to have added scatter on the starting curve as well but refrained in the interests of clarity.

Consider taking the median of the quantity (forecast move - actual move). This is of course not one quantity but many; over what period do we calculate the me-. dian, and for which time forward of moves? And once we choose the period and the move time forward, we don't have one number, but a curve for which we need to separately calculate the median for each rate tenor. But for each time forward, for a given calculation period, if we take this median curve away from the forecast' curve, we will have the future curve about which. $50\%$ of actual rates lie above, and. $50\%$ below.

Does this help us approximate a term premium? It may get us some of the way. there; it certainly allows us to generate a 'neutral' forward curve which lies in the centre. of the actual rate evolution. If we use this median forward curve to derive a starting. spot curve, we have something which fits many of the criteria for a term premium, in that without it, the forward curve is a forecast of the actual future rates..

However, we have a slight problem, as mentioned above; the calculation will be different for every time forward. We don't have just one median curve, we have a. family going out through future time. What can we do with this family of curves? Initially, it is worth taking a look at them and seeing what they imply. It certainly gets us a little closer to the idea of a term premium from empirical data. Moreover, there is a potential further use from constructing this move matrix. Potentially a fitting method could be used to derive from them the most likely' starting curve, which could indeed have a claim on being a true term premium.

![](0120654bc0077d39cbf0f0601e086c9f1d70a2f4025f6d671b90b1a99fc0d55a.jpg)
The implied moves in yellow differ from the actual moves in grey
Figure 6.1: Illustration of forward rate error model. Source: Commerzbank Research

# Quick Review of Previous Term Premium Calculation Methods

How does this relate to other models of the term premium? We list some of the more important approaches below.

(1) A vector-autoregression (VAR) approach has been used to forecast interest rates.. The idea in this case is that the variation which is not captured by the forecast, on average, is the term premium
(2) One could also use a macroeconomic model to do the forecast. An example of this is the Rudebusch and Wu 2003 model [1].
(3) Cochrane and Piazzesi derive a purely empirical forecast model to forecast long term US treasury excess return, with the unexplained part once more being assigned to the term premium [2].
(4) Kim and Wright [8] fit a 3-factor affine term structure model to US treasury yields. since 1990. A variation of the model also incorporates inflation data. The term premium is defined as the difference between the yield and the expected short term. interest rate.
(5) Adrian, Crump and Moench use a linear regression approach to fit the evolution. of the yield curve, using multiple tenors simultaneously, and their term premium is that portion of the curve shifts unexplained by the forward rates. This. is an elegant but complex paper [3], which is somewhat similar to [8].
(6) Hordahl and Tristani derive a very different model using inflation forecasts and bond yields, maintaining an affine form for curves, but without utilising forward rates as forecasts [5].
(7) Survey-based measures. One could in theory survey market participants about. their interest rate forecasts and calculate the term premium as difference between the consensus forecast and the market forwards. Yet such surveys are in-. frequent and may still differ from the market's genuine rate expectations..

It would be good to be able to compare the range of results which these various dif-. ferent methods give, but to duplicate them all would be a large task! Fortunately,. we may get part of the way there with the help of some useful review papers from the St Louis and the San Francisco Federal Reserve Banks, published in 2007 [1, 4]. In Figures 6.2 and 6.3 we reproduce their graphs, and overlay onto the second a sche-. matic of the results of Adrian, Crump and Moench..

We include both graphs as this allows us to view some additional models. Although there is significant disagreement about term premium levels among the methods, most of them exhibit a similar form and overall variation, and are clearly correlated. The Adrian, Crump and Moench data is not perfectly to scale, having been overlaid onto the graph image for illustration purposes, but it is clearly related to other models. It goes out to later dates, but we do not show these for clarity.

The discerning reader may note that those series which may be directly compared between the two graphs, which ought to be quite identical, exhibit very small differences. This is one more problem to add to the pile of understanding and.

This data includes the Kim-Wright method

![](f29ee6290132b9d17a406fb8309701fa69125484a27ef33a06488941bb0c5a32.jpg)
Figure 6.2: 10y USD term premium using different methods, up to 2006. Source: Rudebusch et al. [1]

The Adrian-Crump-Moench data is manually overlaid from [3] estimating term premium - many papers are published in several updated forms, and the calibration of the various models can differ among the versions, leading to small differences.

![](e2b52e8488003ccd54fd505f366d9e251acc8eeef868d8fcac696aabc0bd6516.jpg)
Figure 6.3: 10y USD term premium using different methods, up to 2007. Source: Crump et al. [3]

We have not shown any data from the Hordahl and Tristani method, mainly be-. cause their paper does not have any graphs of term premium data! However, the BIS use a variant of their model for their regular term premium updates, which we assess later. See the Appendix 6.A for a discussion of this data issue..

# Results

# Median (Predicted -- Actual) Moves for USD

Having established that the quantity median (predicted - actual) moves may be of interest in term premium calculations, we present some results. In Figure 6.4 we graph the neutral forward curves families up to ten years forward for the USD swap curve. What are we actually looking at? Each point is given by

Median over all data of (predicted move - actual move). Predicted move $=$ forward rate - spot rate (for the various tenors). Actual move $=$ spot rate at maturity - spot rate at inception (for the various tenors)

Difference as a function of tenor and time forward, USD swap curve

![](815bf7bc85c0bbd04c03641d49eaa00e12af1cfaf4a216b12bd77a9809995009.jpg)
Figure 6.4: Predicted - actual move. Source: Bloomberg, Commerzbank Research

Each curve is in some sense a 'forecast' of a curve in the future, the time horizon being given by the Time fwd' on the axis. The general pattern is that the curves. begin fairly flat, and at the 2 year time forward, are at a level of. $1\%$ or similar. After this they become strongly downward sloping, with at the 10 year forward point, the

short tenors at a level of something like $4\%$ and the longer tenors at perhaps. $3\%$
What are we seeing?.

In all tenors and short times forward. $(<2\mathrm{y})$ , the predicted move is a little more than the actual move overall. This is very consistent with a term premium effect.. But for longer times forward, we see a very large effect for short tenors (predicted move much larger than actual move) which is not as great for longer tenors..

The effect for longer times forward could well be a simple consequence of yield. curve shape. Curves tend to be steeper at the short tenor end and flatter for longer tenors. Thus, after 10 years, the predicted move for a short term rate is quite large,. but the predicted move for a long term rate will be smaller. Additionally, short term rates have historically been more volatile, reflecting Central Bank rate expectations (at least before the negative interest rate policy regime). More volatile rates attract higher risk premiums.

Finally, we can say that as in general rates have come down rather then moved up (by more than the amount that the consensus had predicted during most years under observation), overall, the value of (Predicted - Actual) moves is positive.

# Choice of Forward Curve

What part of this picture would be useful to determine the term premium? We need. to choose how to proceed. One thing which is important to recall is this; one starting. yield curve predicts all forward curves. So if the set of 'predicted - actual' moves was perfectly consistent with a single starting curve, then we would only need one forward curve to derive all others, including the starting curve..

But this is absolutely unlikely. We would not expect these empirical curves to conform to this set of constraints. In practice, we could try to fit a starting curve to a number of different forward curves, or we could select a single forward curve and back out' the starting curve from it. This latter approach is certainly easier from a mechanical and computational point of view. The 1-year forward curve is a. good place to start, as it would be needed in any case to derive the shorter rates for the starting curve; curves from longer times forward could only contribute to longer tenors on the starting curve. Moreover, longer times forward might be generally less relevant to deriving the underlying starting term premium curve. There is much more information available for a shorter term forecast' over a year or so. than a longer term one over 5 or 10 years, and data is better quality. Thus our initial method for deriving the starting curve (term premium) will be to take the im-. plied 'neutral' curve 1 year forward, as given by the 'predicted - actual' data, for each currency.

The other desirable thing about selecting the 1 year forward curve is that it simplifies the algebra!

# Lookback Period

In order to derive a starting curve, we need to decide how much data to incorporate into it. By definition, we will be using a certain amount of time averaging, as we are taking the median of a set of differences through time. If the term premium and other parameters were stationary or close to stationary, then we would take as long a period as possible to get the best statistics. As we are pretty sure that they are not stationary, but believe that they are time varying, we face the usual trade-off between statistics and varying parameters.

We can probably assume that the term premium can change considerably within the course of a year, and so initially we tested 1m, 6m and 1y as our averaging periods, finally settling on 1m which was most consistent with other models.

What might cause fluctuations over short time periods? Anything which affects. market participants' long term view. It is well known that long term views change. over the short term! An extreme example might be the autumn of 2o08 when the Lehman crisis caused global risk levels to soar, and term premiums to spike. Closer to today, the end of 2015/start of 2016 when rapid oil depreciation caused global growth. and deflation fears saw a quickly declining term premium given rising odds for more. policy easing / less policy tightening from the major central banks. Though one might argue that risk premia should increase during stress periods, the term premium has the potential go lower when interest rates are anticipated to fall, as borrowers face less difficulty in paying off debts.

# Discount Factor Calculation

How to get from this set of median(Predicted-Actual) curves to a term premium? First we need to derive a set of discount factors. The median(Predicted-Actual) curves represents a set of forward rates, and we have selected the 1y forward data. Linear interpolation is used to create rates like the 6 year tenor which are not quoted.

Let $D F_{n}$ be the discount factor for tenor from O to n years.

Let $r_{m n}$ be the interest rate from time m to time n.

We know that

$$
\begin{array}{l}{D F_{1}=\cfrac{1}{1+r_{01}}}\ {D F_{2}=\cfrac{1}{\left(1+r_{02}\right)^{2}}}\end{array}
$$

And also, from the definition of the forward rate,

$$
\left(1+r_{02}\right)^{2}=\left(1+r_{01}\right)\left(1+r_{12}\right)
$$

So

$$
1+r_{12}=\frac{D F_{1}}{D F_{2}}
$$

It is easy to see, that if we have a whole set of $r_{m n}$ , that we can easily derive all the. discount factors, and thus all of the. $r_{O n}$ which are our 'term premium' starting. curve - but there is a catch. We need the first rate to start off with, otherwise there is no unique solution. And that is just what we don't have. An alternative method would be to have the last rate on the far end of the tenor curve, which could be obtained by saying that the curve is flat for very long tenors. While appealing, this leads to very unstable fits at the short end and had to be abandoned. Another method which we attempted was to match the sub-1-year discount factors derived from FRA rates to the short end of the curve, but similarly, these were unstable. A simple assumption is that $r_{O1}=r_{12}$ which is unlikely to be accu-. rate but will give an approximate value and enables us to build a discount curve. Once the discount curve is built we can use it to derive the term premium curve, using

$$
r_{0n}=\left[\frac{1}{D F_{n}}\right]^{1/n}-1
$$

The final calculation for the term premium therefore consists of the following steps:

(1) Create time series of Median(predicted moves - actual moves) for each swap tenor. This uses a scrolling window approach with a predefined lookback. period, so each item in the series will incorporate an exogenously defined number of data points, like 1 month or 1 quarter. The move window is 1 year. This forward error series is taken to be a set of 1 year forward rates. We want to use it to derive a starting curve.
(2) Use linear interpolation to create fill in the gaps. This created forward curve will have missing tenors (like 6 years or 11 years). We use simple linear interpo-. lation to fill them in
(3) Back out the discount factors from this set of 1 year forward rates. Unfortunately we need to make an assumption at either the long end or the short end of the curve to do this, as we have one fewer rate than we need to get a unique. solution. We assume that the 1 year rate. $=$ the 1 year forward rate, which gives. an approximate value
(4) Use the discount factors to derive the term premium curve.

# 10y Term Premium Results

A popular tenor for term premium in the literature is 10y. Using this method, for the 10y US term premium through time, and a 1m lookback period, we obtain a time se-. ries for this tenor of term premium. How might we check that this result is reasonable? Some data, namely Kim and Wright, Adrian, Crump and Moench, and the BIS. variant of the Hordahl and Tristani method, may be downloaded and are regularly updated. We graph them together, in Figure 6.5, for the period where all series are. available.

Our own empirical method is James-Leister-Rieger

![](f8edbb702f8f13d0587ab08eb3ee24bb71a71ff7fd8440eee40e29ce3e039cdc.jpg)
Figure 6.5: 10y USD term premium using different methods. $(\%)$ Source: Commerzbank Research, [3, 5, 6] and [8], US treasury data

We can see that the overall form and magnitude of the 10 year term premium are. very similar for all the models graphed. Our James-Leister-Rieger method gives overall slightly lower values with a greater tendency to dip into negative territory but the patterns of return are almost identical. This is encouraging, as the AdrianCrump-Moench for example uses a sophisticated state variable method to derive the term premium from forward rate errors. Our method is more empirical but derives from similar underlying assumptions. The USD swap spread dynamics vs. the treasury curve could explain at least part of this effect; the 10y spread fell 80. bp from Q1 2000 to Q1 2003, but this fall was not seen in the treasury market. Post 2008 swap spreads to treasuries are much more stable, and our method agrees more closely with the others in this period as well.

More recently, we see rising a term premium towards the end of the year as the. rate hike cycle was thought to be starting, followed by a drop off, reflecting deflationary fears.

# 2y Term Premium Results

When we try to extract the 2 year term premium rate using this same method, however, we run into problems. The rate is unstable and varies from $5\%$ to $-2\%$ .This is probably due to the approximations made at the shortest end of the curve, but as previously discussed, it is not easy to find a better data set for the shortest rates. Part of the problem is that we are requiring the term premium to have a proper affine form and to be directly derived from a consistent set of discount factors. The form that this forces upon the curve 'flips' very easily at the short end.

However, do we really require that the term premium curve have this form? There are no practical arbitrage constraints which would force it to conform. It is more reasonable to simply require that it be fairly smooth. Moreover, it seems possible to make one more simplifying assumption; we can say that the term premium is zero for zero time. Thus the 'short rate' of the term premium curve can be set to zero, and we can retain some of the better fitted long term rates to allow us to create a smooth curve which passes through all the selected points.

We use a Lagrange interpolation so that

$$
y={\frac{(x-x_{2})(x-x_{3})}{(x_{1}-x_{2})(x_{1}-x_{3})}}y_{1}+{\frac{(x-x_{1})(x-x_{3})}{(x_{2}-x_{1})(x_{2}-x_{3})}}y_{2}+{\frac{(x-x_{1})(x-x_{2})}{(x_{3}-x_{1})(x_{3}-x_{2})}}y_{3}
$$

Additionally, $\mathrm{y}_{1}=$ term premium for zero time $=0$ ${\tt y}_{2}$ and ${\tt y}_{3}$ can be set to be something like the 10y and 20y rates, and x are the tenors. This method (with a 1m lookback) yields the following result for the US 2 year rate.

Our own empirical method is James-Leister-Rieger (JLR)

![](b1bf55059ebe684eced34f426f5926b3d213bf4feaeed457d2500c37c811ab65.jpg)
Figure 6.6: 2y USD term premium using different methods. $(\%)$ Source: Commerzbank Research [3] and [8], US treasury data

Once more we see that the results are close both in magnitude and form, though we have a longer data series. Unfortunately there is no 2y data available for the BIS Hordahl and Tristani model, but the James-Leister-Rieger 2y results (Figure 6.6) are pleasingly close to both the Adrian, Crump and Moench model and the Kim and Wright model, showing strong similarities to each at different times.

# Comparison with BSI EUR Data from Quarterly Report

The BSI produce a quarterly report [6, 7], which frequently contains some term premium estimates. The data for the Hordahl and Tristani model are in fact taken from the data download facility for this report. Fortunately, they also include EUR data which we can use to compare our term premium estimates with as well (Figures 6.7 and 6.8).

Taken from BIS Quarterly Review (full data set)

![](f23048ad818b2792cfc22eb8c4dcf45af9b6a7bdb89123ea4f2306e566e7a125.jpg)
Figure 6.7: 10y EUR Comparison with BIS term premium data $(\%)$ Source: Commerzbank Research, [7]

There is certainly a similarity in level and form once more. The BIS variant of the Hordahl and Tristani model has some divergences, including a greater recent decline. It is hard to understand how the early 2015 BIS result of $-2\%$ for a term premium can be justified. With a TP of. $-2\%$ and observed forward rates of. ${\sim}1.5\%$ the corresponding 'short rate expectation' would be $3.5\%$ , which seems quite high. See. Appendix 6.A for a discussion on the derivation of this model.

![](aa9bfce4f1c39b9b74bba8bd934ff20a8945a0dd21d5b9e685c9cda71e79dd5f.jpg)
Taken from BIS Quarterly Review (zoom to recent history)
Figure 6.8: 1Oy EUR Comparison with BIS term premium data $(\%)$ (focus on recent history).. Source: Commerzbank Research, [7]

# Recent Results: A General Pitfall with Term Premium Methods

As our results emerged, naturally we sought to connect changes in term premium. with observed changes in market conditions. We focussed on events in 2015, when. the Euro term premium was perceived to fall early in the year before rising sharply in the yield spike of May and June. But, we did not see what we expected. There was. no sharp rise and no indication that the term premium had reacted to the abrupt increase in yields. Carefully scrutinising the data to understand this result, we came to an interesting realisation. We had assigned the 'date' of a term premium number to the point in time when it was fully known; i.e., at the point where the actual move was completed and could be compared with its forecast of a year earlier. But - though. this is the earliest point that the term premium could be known, it is not the point at which it occurred. That point, in fact, should be the point at which the forecast was. known, i.e., a year previous to the date we had assigned it..

This is a problem! Most of the term premium methods we have examined rely on evolution vs expectation/predictability. Basically, if one is looking at a 1-year timeframe, one cannot properly compare predicted and actual rates until the predicted rates are realised. So one does not have a true' measure of the term premium until the goodness of prediction is known, i.e., until a year has passed.

However, all is not lost. At all points in time, we have the implied move derived. from the forward curve, and this gives us the information about market expectations. As we move forward in time, we may collect data about the actual move - for example, after 6 months, we can see whether markets have moved towards or away. from the forecast, and after 11 months we will be nearly there. Thus, we may con-. struct a term premium 'estimate' for the final year which initially relies more on the forecast than the realised result, but which contains market expectations about term premium. Below left we show some 2015 results; we can see that the yield spike in May/June 2015 looks precisely as we would expect. This method has a downside, however. The last year of data will slowly evolve so the curve above will not be fixed' until a year has passed. If a sudden sharp move occurred then the curve might change noticeably month-on-month. As an example, if we had looked at this data in December of 2015, we would see the slightly lower black line. It is encouraging that the overall form of the data does not change; the sharp. rise in May/June is faithfully portrayed (Figure 6.9)..

![](01973f044d669b8762ab0619360b283a897a5ff23dbe2ebf59e00e9af2c19dae.jpg)
Recent results as of different dates, but plotted to Dec 15
Figure 6.9: EUR 10y term premium as of different points. Source: Bloomberg, Commerzbank Research

Is this 'term premium estimate' a good enough measure to use day-on-day? It uses all available data at any point in time and embodies market expectations, though not market evolution. As long as its conceptual pitfalls are fully understood, it certainly offers an insight into the market view of the price of risk, and moreover it could be interesting to look back a year to see how the curve has evolved as the data series extend.

We may summarise this by saying that today our method calculates the term premium estimate; after a year has passed, we can know the 'true' term premium.

# Discussion of Results

We have certainly derived an empirical data based method of finding the term premium.
which is consistent with several far more complex models, and is pleasingly intuitive.
The levels of the term premium seem broadly consistent with other results; the patterns.

of return are very similar though levels can be a little different, but this is not unexpected given the broad range of results among other term premium models..

Have we done this in too complicated a way? Given that our final stage involved. an assumption of zero rates for zero tenor, could we have short cut the process by assuming this earlier?

This was one of the (several) ways we attempted to model the short end of the. curve, and the problem that arose was that it increased (again) instability at the short end, introducing a steep gradient which led to a noisy fit. Introducing the zero rates right at the last stage meant that all data could be incorporated up to that point, so contributions to the level of the term premium from both long and short. rates are preserved.

The effects of varying some of our fitting choices and parameters have been investigated. The lookback period seems to work well at up to 62 days. Additionally, we investigated the effect on the 2 UsD year term premium of varying the selection of long term rates. As long as the tenors are greater than 10 years there is little effect other than a slight overall level change.

What further investigations would be useful? It would be valuable to understand exactly the effect of the input data set. Our input data is from the swap markets and it would be interesting to substitute sovereign bond data for the swap rates - this is what is used in the BIS study and the one by Adrian et al. [3]. One could argue, however, that perhaps swap data gives the term premium relevant to general market participants whereas bond data incorporates different credit effects. On the other hand, swap spreads themselves represent a risk premium which has been significant since 2008. So the difference between the swap term premium and the government bond term premium could reveal interesting effects.

# Appendix 6.A: BIS Report Graphs

One method of discovering term premium is laid out in [5] by Hordahl et al. This is apparently used by the BIS in their quarterly report, which we compare our results to as well. Hordahl et al. do a multi-factor panel estimation of their model, which, although it maintains an affine form to the bond yield curve, does not use forward rates as an input. Thus, one would anticipate that this effect where the slope of the curve is important would be less picked up by their method. They also incorporate data from inflation surveys - it is a very different approach to the term premium problem.

Their results are, as might be expected, not similar to other methods - indeed,. with the incorporation of inflation data, it could be said that they are not really mea-. suring the same thing. Below right is the graph of the 10 year term premium for USD and Eurozone from their paper in [5]. By comparing it with the data taken from the BIS paper, which apparently uses the same method to calculate the term premium for UsD on the left, we see that there is very little resemblance, either with the.

dynamics, or the range. The results from the paper are confined to a tight range around zero, whereas the BIS data have in general been higher..

A careful reading of the paper reveals the likely answer, however. The Hordahl paper is actually focussed more on the inflation risk premium, and it is these that appear in the graph (Figure 6.11). Quoting from the paper, we then find in footnote 8, that 'Our model can also be used to compute nominal and real term premium for any maturity. We do not report these variables, because our focus is on the inflation risk premium.' Additionally, a further BIS paper by Mohanty and Rishabh [9], which graphs the same data as in Figure 6.10, has in a footnote to the graph that the data is the "sum of inflation and real risk premium, the latter calculated using the BIS term structure model". Thus the BIS term premium data seems to be derived both from the Hordahl paper and an internal model. It is fairly closely correlated with other results for the UsD, though as stated the use of French government bond data for the EUR results could cause differences.

A final comment is that the BIS data appears to evolve slightly through time. The. 10 term premium data taken from the September review [6] differs somewhat from the apparently identical data in the December review [7]. As the overall form of the graph. is very similar, it seems likely that some kind of market calibration is to blame..

This data is apparently created using the Hordahl and Tristani data

![](b728fd8d725670f8bf550a8d80ad93e7438748fdfec17bef7dcff5ea781d356f.jpg)
Figure 6.10: 10y USD treasury term premium from BIS data. Source: Bloomberg, BIS [6]

Hordahl and Tristani data from paper

![](1ef4787b1490db86b3b3d7a47e92f22548d3d47da6363781598d7ae3b3362718.jpg)
Figure 6.11: 10y USD treasury inflation based term premium. Source: Bloomberg, Hordahl et al. [5]

# References

[1] Glenn Rudebusch, Brian Sack, and Eric Swanson. 2o07. "Macroeconomic Implications of Changes in the Term Premium." FRB St. Louis Review 89 (4) July/August) pp. 241-269. http://research.stlouisfed.org/publications/review/07/07/Rudebusch.pdf
[2] John Cochrane and Monika Piazzesi. 2o05. "Bond Risk Premia." American Economic Review. 95 (1) (March) pp. 138-160. http://www.nber.org/papers/w9178
[3] Tobias Adrian, Richard K. Crump and Emanuel Moench, 2008, updated 2013. "Pricing the Term Structure with Linear Regressions", FRB New York Staff Report #340, https://www.new yorkfed.org/research/data_indicators/term_premia.html.
[4] Eric Swanson, 2007 FRBsF Economic Letter. "What We Do and Don't Know about the Term Premium" http://www.frbsf.org/economic-research/publications/economic-letter/2007/ july/term-premium/
[5] Peter Hordahl and Oreste Tristani, International Journal of Central Banking, Sep 2014, "Inflation Risk Premia in the Euro Area and the United States" http://www.ijcb.org/journal/ ijcb14q3a1.htm
[6] Bank of International Settlements Quarterly Review, Sep 2015, http://www.bis.org/publ/ qtrpdf/r_qt1509.htm
[7] Bank of International Settlements Quarterly Review, Dec 2015, http://www.bis.org/publ/. qtrpdf/r_qt1512.htm
[8] Kim and Wright, 2o05 Federal Reserve Board, Washington, "An Arbitrage-Free Three-Factor Term Structure Model and the Recent Behavior of Long-Term Yields and Distant-Horizon Forward Rates" http://www.federalreserve.gov/pubs/feds/2005/200533/200533abs.html
[9] Mohanty and Rishabh, BIS working papers no 546, March 2016, "Financial intermediation anc monetary policy transmission in EMEs: What has changed post-2008 crisis?" http://www.bis. org/publ/work546.pdf
[10] Jonathan H. Wright, Finance and Economics Discussion Series, Federal Reserve Board,. Washington DC, 2o08 "Term Premiums and Inflation Uncertainty: Empirical Evidence from an International Panel Dataset" http://www.federalreserve.gov/pubs/feds/2008/200825/. 200825pap.pdf
[11] Joshua V. Rosenberg and Samuel Maurer, Federal Reserve Bank of New Hor, Economic Policy Review July 2o08 "Signal or noise? Implications of the term premium for recession. forecasting" https://www.newyorkfed.org/medialibrary/media/research/epr/08v14n1/ 0807rose.pdf
[12] Don H. Kim and Athanasios Orphanides, Bank of International Settlements Quarterly Review, Jun 2o07, "The bond market term premium: what is it, and how do we measure it?" http://. www.bis.org/publ/qtrpdf/r_qt0706e.pdf
[13] James Hamilton, Econbrowser November 2006, "The Yield Curve and the term premium". http://econbrowserlcom/archives/2006/the-yield-curve_2
[14] Ben Bernanke, April 2015, Brookings "Bernanke's Blog", http://www.brookings.edu/blogs/ ben-bernanke/posts/2015/04/13-interest-rate-term-premiums
[15] Jagjit Chadha, Centre for Economic Policy Review, Vox Policy Portal, November 2014, "The impact of the maturity of US government debt on forward rates and the term premium: New results from old data" http://www.voxeu.org/article/government-debt-and-term-premiumnew-results-old-data
[16] Speech by Peter Praet, Member of the Executive Board of the ECB, at ECB and Its Watchers XVII conference organised by Center for Financial Studies, Frankfurt, 7 April 2016 http://www.. ecb.europa.eu/press/key/date/2016/htmfal/sp160407.en.html
