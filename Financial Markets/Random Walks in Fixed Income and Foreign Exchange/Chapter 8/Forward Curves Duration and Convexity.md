---
tags:
  - convexity
  - curve_slope
  - duration
  - forward_curve
  - yield_curve
aliases:
  - 2's-10's trade
  - Curve inversion
  - Forward rate
  - Yield curve shape
key_concepts:
  - Bond duration increase
  - Central bank expectations
  - Convexity value volatility
  - Curve slope forecasts
  - Curve steepening trade
  - Fixed income products
  - Forward curve analysis
  - Implied forward evolution
  - Market anomalies
  - Term premium effect
  - Yield curve convexity
  - Yield curve implications
---

# Chapter 8 Forward Curves, Duration and Convexity

The shape of the yield curve has implications that are not always well understood.1. A curve whose slope rolls off' can imply a future curve inversion, even when such an inversion is very unlikely to take place. Since the 2008 crisis, curves have become lower and flatter, and their implied forecasts' start to look improbable. In this chapter, we report and update a study where we analysed the actual evolution of. curves long-term relative to their implied forecasts, and we show that in particular, forecasts of curve slope are likely to be biased. We investigate whether yield curve convexity is a driver of this effect..

# Are the Forwards a Useful Forecast?

Investors frequently take curve slope positions in liquid fixed income products. For. example, if they have a view that the EUR yield curve is likely to steepen in the near. future, they might do a 2's-10's trade. If the curve does steepen beyond the slope. implied by the forward curve, the trade will deliver a profit. Investors can trade all parts of the curve from a few months tenor to 50 years, and more complex views. where the anticipated yield curve evolution could involve a change in curvature can also be expressed, often with 3 or 4 rather than 2 positions on the curve..

Forecasting these changes is both a science and an art, but one factor that is. frequently taken into consideration is the implied forward evolution of the yield curve. Each rate has a forward curve, and thus a combination of forward curves (or forward surface) will allow us to create a forward evolution path for the curve slope. Are forward curve slopes a useful indicator for the development of the curve?.

# Why are Forward Curves so 'Abnormal'?

Any prudent investor should always be circumspect about market anomalies and ask whether or not there is a justification, which could point to hidden risks when trying to exploit this.

When it comes to forward yield curves, combined technical and fundamental factors explain the unusually flat curves, giving us confidence about a systematic flattening bias in forwards that should not be realised on average.

Arithmetically, a forward curve is always flatter than the spot curve if the spot curve exhibits a concave shape - that is, if the shorter part of the curve is steeper than the longer part of the curve. All major yield curves persistently show this pattern because central bank key rate expectations dominate the shorter part of the curve out to 5y, the term premium effect dominates intermediate maturities out to 10/15y maturities while convexity and supply/demand effects dominate the ultralong part of the curve.

Recall that convexity describes the change in duration for a given change in the underlying yield. When yields fall, the duration of a bond with positive convexity. increases, and vice versa. For a long bond investor, convexity is therefore a positive. attribute. Your duration increases when the market rallies, which means your bond. price increases become larger, and the converse is true in a bear market. This also explains why the larger the convexity value, the higher the expected yield volatility. Finally, the convexity of a non-callable bond rises significantly with time to maturity, so that ultralong bonds have much higher convexity. For any given level of expected volatility, the convexity value of a longer-dated bond will therefore be higher, and the. yield of this bond will hence be lower..

Besides these technical aspects, supply/demand imbalances are also more relevant for longer maturities. Given the long liabilities of pension funds and life insurers and the persistent duration gap of most of these ALM accounts, there is strong structural demand for ultralong duration. At the same time, although prudent issuers should try to increase their duration in order to reduce refinancing risk, most issuers have the bulk of their funding in shorter/intermediate maturities, because this generates interest rate savings in the longer run (given the 'normal' curve slope).

Everything considered, a 'normal' curve slope tends to be not only upwardsloping, but also concave - that is, the shorter part out to 10/15y is steeper than the ultralong part. In turn, this means that the forward curve is usually flatter than the spot curve.

# Simple Spot and Forward Curve Evolution

It is possible to look at the simplest cases of curve evolution using the derivation for the forward rates from discount factors..

Let $D F_{n}$ be the discount factor for tenor from O to $n$ years.

Let $r_{m n}$ be the interest rate from time $m$ to time $n$

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

Using this expression, we derive a set of 1y forward rates from simple spot curves, and plot them in Figures 8.1 and 8.2.

![](4bd2f5f198ccb4270efc27ddac2f201c49531209b5d38b9ddb073261bf408c35.jpg)
Figure 8.1: Linear and convex spot interest curve shapes.

![](0ab533bda4777779e35a5b0598cd2d950c247102fe192b06ad18ca6bb1fe9255.jpg)
Figure 8.2: Concave and inverted curves. Source: Commerzbank

The first chart in Figure 8.2 is perhaps most similar to developed market curves on average. A remarkable feature of this is that even though the spot curve increases throughout the tenor range, the roll-off in slope means that the forward curve is actually inverted. These examples clearly show that a curve that remains static is almost certainly not forecasting its own evolution. So most persistent curve shapes may well be generating opportunities. Note that the spot curves in the concave and inverted cases are not the same, though they look similar; the slight additional rolloff for the inverted case is much more exaggerated in the forward..

# Forward Implied Slopes vs Realised Data

To investigate whether forward implied slopes are useful forecasting indicators for future curve evolution, initially we examine the history of the EUR and USD 2-10y. curve slope. We plot the spot differential of 12y and 10y swap rates together with the. same difference 1y forward in Figure 8.3. We use swap rates because of good availability, simplicity (no time decay or benchmark roll) and because they are highly correlated with other fixed income products; the conclusions we draw from this. study are likely to be highly transferable to other rates..

Note that in the charts in Figure 8.3 we plot the forward curve slope and the actual curve slope at the same date, so that the forecast and its result are simultaneous. This means that the end of the chart lacks data for the period that has been forecast but has not yet arrived.

What can we say about these charts? Initially, we see a correlation with current. values and forecast values. That is hardly news; forward rates are famously prone to predicting the future to continue trends seen in the immediate past. The range of values attained by the actual slope is very much greater than those forecast. The implied slopes are forever predicting convergence which is not, on average, taking. place. We can perhaps interpret this as indicating that the size of moves of longerterm rates is more overestimated relative to shorter-term rates, which could mean that degrees of flattening and steepening are usually forecast to be smaller than they should be, and that as the forecast tenor increases, the size of forecast moves grows, though not enough..

As can be seen in the Appendices, this situation is not confined to EUR; it is. present in all of the G10 currencies we examined, though we only give the USD for. comparison purposes. As the forward tenor increases, the ratio of the standard deviation of the implied forward distribution to the actual distribution at the future time referenced by the forward comes closer to 1, and as the slope tenor increases, the ratio decreases.

However, recall that the forward forecast' is only ever purporting to forecast the mean of a distribution - there is always a range of values allowed around this, which would be indicated by the swaption volatility. While we do not examine this effect here, it could well be that a more complete treatment that includes the implied volatilities would resolve the difference between the implied and actual range of moves. More relevant, however, is the question of whether there is any systematic bias in the forecast.

![](04e8062453351e28ae1cdcfb0bfb41a4beb7e74be29b542742b95f1935564fc5.jpg)

# Analysis of Mean Forecast Slope vs Mean Actual Slope

To understand if there is any systematic effect initially unseen due to volatility, we ana-.
lyse the mean value of curve shifts, implied vs actual. We show the 1y case in Figure 8.4;
other forward times are in the Appendices. Most of the numbers are well below 1, indi-.
cating that the average forecast move is larger than the average actual move..

![](0a21474de9412663a7aa07691eba3667d71955154f24d79ed9b4ea38f3ef8bc5.jpg)
Figure 8.4: Ratio of means of actual moves/forward moves. Source: Commerzbank, Bloomberg

Somehow, though the range of values of moves is underestimated by the forward slope, the average magnitude of the predicted slope is larger than actually occurs (see charts in Figure 8.4). Additionally, the results in the tables are often negative,. indicating that the direction of the mean forecast was incorrect..

# Resolving the Apparent Contradiction

These two empirical observations do not in fact contradict each other. What we are seeing is a consequence of bias. On average, the forward curve in EUR has been biased. Yield curves normally slope up due to the term premium, with the shorter part of the curve being steeper. The slope forecast that this slope of the spot curve delivers will inevitably be a flattening one. While some exceptions exist, this will tend to be the rule. However, curves have not inevitably flattened - on average, there has been a degree of steepening, as the very low rates available for short tenors have. limited ability to drag down. $10\mathrm{y+}$ rates to their levels.

While there has been a persistent bias to the slope forecast values, this has not been the case for the actual slope evolution, which has been on average close to zero. In most cases, forwards predict too much flattening, but if there is a major flattening move, they miss that one as well (and also any big steepening moves). We can thus resolve the contradiction; forwards can indeed forecast too small a range of future values, while their average forecast value is larger in magnitude but more negative than the average actual slope change value.

# Forward Implied Slopes and Direction

The previous analysis, indicating the presence of bias, points the way to the next investigation. To analyse volatility effects, we looked at the 2-10y slope, but we anticipate finding more evidence of consistent bias in the longer tenors, due to effects like term premium becoming more important. Due to term premium and other risk. premia, in all liquid currencies, yield curves tend to slope upwards and level off. The short-dated end of the curve is more active and variable, primarily due to the different policy outlooks for the respective central banks, but in the post-10y tenors, curves tend to look far more similar across currencies and time periods. Thus, to. gain a picture of bias overall, we should investigate the whole curve and not neglect. longer rates. Additionally, any effects present in aggregate over the whole period may be due to dominant sub-samples, so it is essential to analyse different data pe-. riods as well.

# Analysis of Whole Data Period

For different liquid currencies, we first look at the full data period from 2001-2020 in Figures 8.5 to 8.10. We examine three different curve slope sections; the 1-2y, 2-10y and 10-30y. We look at the average forecast slope change from 1 to 5 years forward, and compare it with the actual change over the same period. The slope is defined to be the yield of the longer tenor minus the yield of the shorter tenor - hence a negative number, in either forwards or actual changes, indicates a curve flattening in that set of tenors, while a positive number indicates a steepening.

There is a very clear picture here. Overall, but most clearly in the longer tenors,. the predicted change is a flattening which in general fails to materialise. The move predicted is consistently negative, but actual moves over the same period have been close to neutral for all curve sections. The effect is roughly linear with time forward. Especially over longer tenors and times forward, it can be substantial..

# Analysis of Sub-periods

We examined three sub-periods; the pre-crisis time of 2001 to 2007, the post-crisis from 2007 to 2014, and the modern-day low interest regime in 2014 to 2020. These results are statistically less good especially for longer times forward, as in a 7y data set, the 5y forward data will have only 2y of useful information, so they need to be taken with a grain of salt. The graphs for these different periods can be found in the Appendices, but we summarise the results as follows:

![](727f584f55593bdf4f2cc0a60ba1c19e4082b5cafd00bdf27787777d47e2cd1a.jpg)
Figure 8.5: Implied slope change (1-2y). Source: Commerzbank, Bloomberge

![](9df2f70af29335e80bbfa2327bddb6a2b70c6224cd7b363204272ca7551aad8a.jpg)
Figure 8.6: Actual slope change (1-2y). Source: Commerzbank, Bloomberg

(1) 2001-2007: All sections of the curve imply a flattening on average. Actual re sults, however, vary greatly by currency pair, with no consistent pattern. The range of actual moves is larger than the implied forward moves.
(2) 2007-2014: This period in general had steepening realised curves, with flatten-. ing implied.

$2-10\lor,\%,$ from 1y to 5y forward, 2001-2020

![](434526dc505b2c22b5c77cc73efac4967235cff063a41d5cf5730f68108db8e2.jpg)
Figure 8.7: Implied slope change (2-10y). Source: Commerzbank, Bloomberge

2-10y, %, from 1y to 5y forward, 2001-2020

![](e3a496ab9962485473cf54c7e6328d4f287c9dacc261195d0642ac37f41a181d.jpg)
Figure 8.8: Actual slope change (2-10y). Source: Commerzbank, Bloomberg.

(3) 2014-2020: The most recent period shows noise in the shorter tenors but the longest end of the curve preserves the behaviour where the implied flattening is. consistent, and on average, the realised flattening is less..

What does this mean? Perhaps in the longer tenors, the persistence over various periods of the implied flattening exceeding the realised might be useful.

![](7d7b6b013602d62bc7eedd3e174c158ba440052976a48e5f8aff14b7d46bef7e.jpg)
Figure 8.9: Implied slope change (10-30y). Source: Commerzbank, Bloomberge

![](a742dbe5b1c400f8dc41d6c6ea73ff9974f5d4fb635c91cfbc35170ab2531a67.jpg)
Figure 8.10: Actual slope change (10-30y) Source: Commerzbank, Bloomberg

# Can We Monetise This?

Initially, to analyse a tradable feature, we look only one year ahead. The obvious trade to do is a forward steepener trade, whose return is determined by the differ-. ence between the implied steepening and the actual. In Figure 8.11, we tabulate the average annual return of such a steepener trade, over the full data period, for EUR, for different sections of the curve..

![](4149195d2ebc3cbf2ef213aa075cd6ca96735099df620d92ba4e06b6bfe88e5b.jpg)
Figure 8.11: Average deviation of steepener trade vs forwards. Source: Commerzbank, Bloomberg

The sweet spot is very clear at the longer end of the curve. Let us focus on the.
10-30y trade and look at different data periods. In Figure 8.12, we graph the return of.
this trade for our different data periods - it is fairly consistent and rarely makes a loss.

1y forward steepener, various different periods, in bp

![](4d5e944e72e06c67f448a05bad95d07fcfd0da4546707ae69115984f6bc6bc27.jpg)
Figure 8.12: Average deviation of 10-30y steepener vs forwards (different periods). Source: Commerzbank, Bloomberg

It is important to realise that this is only an indication of profitability; we have neglected bid-offer costs and have also neglected the fact that when we unwind the trade, we will use 9-year and 29-year rates, not 10-year or 30-year rates. Addition-. ally, this result is valid for a trade held on the books for a year, which is not always. desirable. However, it does indicate that the persistent curve behaviour holds po-. tential and should be kept in mind when making investment decisions..

We can also create the chart in Figure 8.12 for the 5y forward case, as in Figure 8.13.. In this case, we only look at the full period case and compare it with the 1y for ward, as the data quality is less good for the sub-periods. Though not all investors. will wish to wait 5 years to see their returns, for those who do, they are substantial. However, recall that these returns are over a 5y period and are approximately. linear with time, so it might be better to simply repeat the 1y strategy every year. for five years to generate similar results..

![](e5751c068645ab56decea2f73d12ea1eed99aabf71cb93b1cb093fb1d9f801eb.jpg)
1y and 5y forward steepener, in bp
Figure 8.13: Average deviation of 10-30y steepener vs forwards. Source: Commerzbank, Bloomberg

# The Value of Convexity

It's natural to ask, 'Where on earth is this fairly consistent return coming from?' The natural first answer is probably something to do with convexity'. To understand. how this might be so, first we define convexity for a coupon bond, and then show. how it can take on a value along the yield curve. To do this, first we need to talk about the duration of a bond as well..

# Defining Duration

The duration of a bond is a quantity with a story. Initially, as one might deduce from the name, it was connected with the tenor of the bond. Specifically, it is the weighted average of the times until the cashflows of the bond are received, as shown in Figure 8.14. This is usually known as the Macaulay Duration. There are two good ways to look at MacD - visually and algebraically. The first can lead to the second.

![](9760ef2b5400a3f379845072015895333281c3df89b240bec57b8da16743c4bc.jpg)
Figure 8.14: Macaulay Duration.

The weights of each maturity $\mathrm{(t_{i})}$ of the cashflows are given by the PV of the cashflow divided by the total value of the bond, which gives the factor of $\mathrm{{PV_{i}}/\mathrm{{V}}}$ This ensures that the weights add to $100\%$

In the diagram in Figure 8.14,
$\mathrm{MacD}=\mathrm{1}$ Macaulay Duration
$\mathfrak{t}_{\mathrm{i}}=$ maturity of cashflow (time from now until cashflow)
$\mathfrak{n}=$ number of cashflows $=$ number of years for annual coupon bond. $=5$ $\mathrm{PV_{i}=P V}$ of ith cashflow
${\mathrm{V}}=$ value of bond
${\mathfrak{c}}=$ coupon of bond
and we will also need.
$\mathrm{y=}$ yield of bond

One can see from the definition that the MacD is the balance point' of the bond, and it is useful when thinking about a kind of average lifetime of the bond..

We can put some numbers into this expression. First, we need the present value $P$ of the bond; the following is the sum of the discounted cashflows..

$$
P=\sum_{i=1}^{n-1}{\frac{c}{\left(1+y\right)^{i}}}+{\frac{c+100\%}{\left(1+y\right)^{n}}}
$$

For a 5y bond, coupon $3\%$ , yield $2\%$ , this is:

$$
P={\frac{0.03}{\left(1+0.02\right)^{1}}}+{\frac{0.03}{\left(1+0.02\right)^{2}}}{\frac{0.03}{\left(1+0.02\right)^{3}}}{\frac{0.03}{\left(1+0.02\right)^{4}}}+{\frac{1.03}{\left(1+0.02\right)^{5}}}
$$

$$
\begin{array}{l l}{{\mathrm{P}=0.0294+0.0288+0.0283++0.0277+0.9329}}\ {{\mathrm{}}}\ {{\mathrm{P}=1.0471=104.71\%}}\end{array}
$$

Now, let's use this to find the duration MacD:

$$
\begin{array}{l}{{M a c D=\displaystyle\sum_{i=1}^{n}t_{i}\frac{P V_{i}}{V}}}\ {{\nonumber}}\ {{M a c D=\displaystyle\frac{0.0294}{1.0471}+\displaystyle\frac{0.0288\times2}{1.0471}+\displaystyle\frac{0.0283\times3}{1.0471}+\displaystyle\frac{0.0277\times4}{1.0471}+\displaystyle\frac{0.9329\times5}{1.0471}}}\end{array}
$$

$\mathrm{MacD}=4.725$

Those reading this note who have a science background will note a similarity to this calculation and that for the centre of gravity of a rod.

However, these days, MacD is not used as often as its successor, the modified. duration. Though similar in calculation method, the modified duration has a different and specific purpose. It is a price sensitivity, specifically the percentage. derivative of price with respect to yield (or we could say the first order derivative of bond price with respect to yield). Perhaps it was realised that MacD possessed. this quality to an extent, and thus, modified duration was a better realisation of. sensitivity.

Modified duration is defined as follows:

$$
M o d D={\frac{M a c D}{1+y}}
$$

In this example, $\mathrm{ModD}=4.632$

How do we use duration? (Please note that for the rest of this paper, duration will refer to ModD.) Let's take a look at the graph in Figure 8.15.

![](af374a4c608cf065869f68160bbd501068ca97e16ef4ef8eef472dc0e8cbb745.jpg)
Figure 8.15: Linear price-yield relationship. \*Note that although this graph is always drawn with bond price on the y-axis, it is strictly bond return, as duration and later convexity are defined with respect to return Br rather than price. The graph would look just the same in form, but this distinction is important for later on.

If we can assume that the bond price and the bond yield have a linear relation-. ship, then the duration is the ratio between them, or the slope of the line on the graph. Strictly, there needs to be a minus sign in the definition (2) as well, as the slope of the line is negative, though it is usually quoted as a positive number.

Though taking (1) and (2) together, the calculation of the duration will be a sum over the number of years in the tenor, by some algebraic wizardry, we can express it in closed form. To see the full derivation of this formula, see Chua (1984).

$$
M o d D=\frac{1}{1+y}\left[\frac{1+y}{y}-\frac{1+y+n(c-y)}{c[(1+y)^{n}-1]+y}\right]
$$

Note that if the bond is semi-annual or quarterly, this gets more complex, and there is also a correction for stub periods that can be added if desired..

A note on the yield term: This is the yield-to-maturity of the bond, which is the.. equivalent flat interest rate which would duplicate the value of the bond in the current yield-curve environment. Thus it changes as the interest rate environment changes. and is a useful 'flat' rate to use for the bond lifetime..

# Defining Convexity

If only life were this simple. But the price of the bond is not actually linear with respect to the yield - it is more like the graph in Figure 8.16.

![](45a01d94ade9e7fe0ab20a6cc37f561013b7d91410f421a41d22e84dcc20c324.jpg)
Figure 8.16: Non-linear price-yield relationship.

In fact, the relationship of price to yield is only modelled well by a linear approxima-.
tion over a short range; for anything else, the curvature of the price-yield relationship.
is critical, and it is this curvature which is represented by convexity. We can see that this curvature is very beneficial to the owner of the bond. Why? Because the price.
is always better than the linear approximation would indicate. Thus, the convexity.

measures the change in duration (or slope of the graph) with respect to yield, or we can say it is the second derivative of bond price with respect to yield.

How are we going to calculate this? There are a few ways. First, let's look at good old finite differences. We can derive a value for duration this way as well. We. Set $\Delta\mathrm{r}$ to be $0.01\%$

Table 8.1: Duration and convexity.


<html><body><table><tr><td colspan="6">FiniteDifferenceDurationandConvexityCalculation</td><td>Price</td></tr><tr><td>Priceatdiscount rater-Deltar</td><td>0.029415</td><td>0.028841</td><td>0.028278</td><td>0.027726</td><td>0.93336017</td><td>1.04762</td></tr><tr><td>Priceatdiscountrater</td><td>0.029412</td><td>0.028835</td><td>0.02827</td><td>0.027715</td><td>0.93290273</td><td>1.047135</td></tr><tr><td>Priceatdiscount rater+Deltar</td><td>0.029409</td><td>0.028829</td><td>0.028261</td><td>0.027704</td><td>0.93244556</td><td>1.04665</td></tr></table></body></html>

In Table 8.1, the central line is the same as the previous calculation for the duration;.
we are finding the present value of each cashflow of the bond and summing the val-.
ues to get the price. But given that we know that the duration is the first derivative of the bond with respect to price, and the convexity is the second derivative, we can.
use simple finite difference methods to see that.

$$
M o d D=\frac{P_{r-\Delta r}-P_{r+\Delta r}}{2\times P_{r}\Delta r}=4.632
$$

$$
\large C o n v e x i t y=\frac{P_{r-\Delta r}+P_{r+\Delta r}-2\times P_{r}}{2\times P_{r}\Delta r^{2}}=13.361
$$

In fact, it is usually quoted without the factor of $^1/2$

$$
C o n v e x i t y=\frac{P_{r-\Delta r}+P_{r+\Delta r}-2\times P_{r}}{P_{r}\Delta r^{2}}=27.982
$$

Another way of estimating the convexity of a bond is to say it is approximately equal to the square of the duration; this is only strictly true for zero-coupon bonds, but is a somewhat useful estimate for other cases.

If we wanted to express convexity as a sum over the tenor of the bond, similar. to (1), then by taking the next derivative of price with respect to yield, we arrive at

$$
C o n v e x i t y=\frac{1}{P(1+y)^{2}}\sum_{i=1}^{n}P V_{i}\left(t_{i}^{2}+t_{i}\right)=27.982
$$

Now, while the expression for duration as a closed form formula (3) is relatively well. known, a similar expression for convexity is not generally found in the literature.. There is an attempt to derive it in Miron and Swannell (1991), but it turns out to be

incorrect. Therefore, we took the time to produce a correct closed-form formula for convexity, which makes it far easier to code into a spreadsheet and to look at depen. dencies. But it's a little longer than the formula for duration.

First, we define

$$
V={\frac{1}{1+y}}
$$

Then

$$
\begin{array}{l}{{C o n v e x i t y=\displaystyle\frac{c V^{4}}{\left(1-V\right)^{3}}\left[n{\left(1-n\right)}{\left(1-V\right)}^{2}V^{n-2}-2n V^{n-1}{\left(1-V\right)}+2{\left(1-V^{n}\right)}\right]}}\ {{\displaystyle\qquad+\frac{2c V^{3}}{\left(1-V\right)^{2}}\left[-n V^{n-1}{\left(1-V\right)}+{\left(1-V^{n}\right)}\right]+{\left(1+c\right)}{\left(n+1\right)}n V^{n+2}=27.982\times2\times2\times2\times3.}}\end{array}
$$

It is very pleasing to be able to write convexity in this way, as it can be seen that it depends only on coupon, yield and tenor. Once more, several terms can be added to account for semi-annual or quarterly coupons or stub periods (see Chua [1984], though there are errors in this reference)..

# Numerical Calculation of Convexity

Obviously, this tendency for the price-yield curvature to benefit the bondholder is. valuable. Also pretty obvious is that its value will be larger for larger bond volatilities. In other words, the more the price moves, the greater the convexity effect will. be. Let's see if we can put numbers onto the effect..

We define bond return. $\mathrm{B_{r}}$ as $\Delta\mathrm{P}/\mathrm{P}$ , where $P$ is the price of the bond. We know that bond return at time $t$ is a function of yield at time. $t_{:}$ $\mathrm{y}_{\mathrm{t}},$ so $\mathrm{B_{r}=B_{r}\left(y_{t}\right)}$

Simply by using a Taylor expansion, we can say that

$$
B_{r}(y_{t})=B_{r}(y_{0})+(y_{t}-y_{0}){B_{r}}^{\prime}(y_{0})+{}^{1}/2\left(y_{t}-y_{0}\right)^{2}{B_{r}}^{\prime\prime}(y_{0})
$$

where $\mathrm{y_{0}}$ is the forward bond yield for a forward contract maturing at time. $t$ and $\mathrm{B_{r}}^{\prime}$ and $\mathrm{B_{r}}^{\prime\prime}$ are the first and second derivatives of bond return with respect to yield.

Of course, we know that $\mathrm{B_{r}}^{\prime}=\mathrm{\Omega}$ duration (ModD), and $\mathrm{B_{r}}^{\prime\prime}{=}$ convexity (C)!

Now, we take expectations of both sides of the equation.

$$
E_{t}[B_{r}(y_{t})]=B_{r}(y_{0})+E_{t}(y_{t}-y_{0}){B_{r}}^{\prime}(y_{0})+{}^{1}/2E_{t}(y_{t}-y_{0})^{2}{B_{r}}^{\prime\prime}(y_{0})
$$

From this point, we can go two ways, and we find both in the literature. First of all,

$$
E_{t}(y_{t}-y_{0})^{2}\approx{\sigma_{y}}^{2}{y_{0}}^{2}t
$$

where $\upsigma_{\upgamma}$ is the relative yield volatility of the yield, i.e. the swaption volatility for the relevant time forward and tenor. For simplicity, we have used $\mathrm{t}{=}1$ year ahead for the following calculations.

This is gives us the first result. The value of the convexity for a bond is defined as follows:

$$
C o n v e x i t y~\nu a l u e=1/_{2}\sigma_{y}{}^{2}y_{0}{}^{2}t\times C
$$

This is the way you will see convexity value quoted in many texts, especially older ones. However, we need to be careful! These days, volatility in the fixed income world is quoted as 'basis point volatility', not 'relative yield volatility', as it used to be. Basis point volatility is the volatility of yield changes $\Delta y$ , and today is something of the order of $1\%$ for most developed markets. If you see an implied swaption volatility of $^{\bullet}40^{,}$ , it will mean 40 basis points, or $0.4\%$ . Some years ago, it was more usual to quote relative yield volatility - in which case, it might be something like $30\%$ , and it was the volatility of yield changes relative to yield, i.e. $\Delta y/y$ Thus, if we are using basis point volatilities, we have

$$
C o n v e x i t y~\nu a l u e=1/_{2}\sigma_{y}{^2}t\times C
$$

Now, we can just use this as a formula to calculate the value of convexity at a future time t. Note that $t$ is the time forward, not the tenor of the bond. The tenor of the. bond will enter via the formula for C. But what yield should we put into the convexity C? That should be the yield that we assume will hold in the future. This is where forecasts and views can enter and affect the value of convexity that we believe will pertain to the future time. Similarly, we can put the volatility into the formula that. we assume will exist at that time.

We can, if we wish, now make a further assumption. This is that the future return of the bond at maturity $T$ is the forward return priced into the market. If this is the case, then

$$
E_{T}[B_{r}(y_{T})]=B_{r}(y_{0})
$$

and putting this into (5), we get

$$
E_{T}(y_{T}-y_{0}){B_{r}}^{\prime(y_{0})}=1/2E_{T}(y_{T}-y_{0})^{2}{B_{r}}^{\prime\prime}(y_{0})
$$

And inserting Duration ModD and Convexity C, and using $\mathrm{E}_{\mathrm{t}}(\mathrm{y}_{0}){=}\mathrm{y}_{0}$ , we have

$$
E_{T}(y_{T})=y_{0}-{1\mathord{\left/{\vphantom{1{y_{0}-{1\mathord{\left/{\vphantom{12}}\right.\kern-\nulldelimiterspace}}2}}}\right.\kern-\nulldelimiterspace}2}E_{T}(y_{t}-y_{0})^{2}{\frac{C}{M o d D}}
$$

Which tells us that if we assume that the future bond return is the forward bond re. turn at maturity $T_{:}$ then the forward yield should be adjusted, using equation (6), by

$$
y i e l d a d j u s t m e n t=-1_{/2}\sigma_{y}{}^{2}{y_{0}}^{2}T\frac{C}{M o d D}
$$

or, with basis point volatilities,

$$
y i e l d a d j u s t m e n t=-1_{/2}{\sigma_{y}}^{2}T\frac{C}{M o d D}
$$

Though the forward yield assumption is certainly one assumption that may be made, it is not the only one, and convexity values may be calculated using wider assump-. tions than this by using (8) for a wide range of future scenarios. A popular assump-. tion is that current bond returns (represented by current bond yields) will pertain in the future.

We can see that (7) and (8) are similar because a very rough approximation for the convexity calculation (only accurate for zero-coupon bonds) is that $\mathsf{C}=\mathbf{M}\mathsf{o d}\mathsf{D}^{2}$ If we also say that $\mathrm{ModD=T}$ (modified duration is somewhat similar to tenor, once. more only accurate for a zero-coupon bond), then they come out to be the same if time ahead $=$ tenor.

Let's put some numbers into these calculations.

We can use the EUR German government bond yields and the current swaption. volatilities to create Figures 8.17 and 8.18, taken from 26 June 2018. We need to. input a value for the bond coupons, and also ideally have this value available back through time. There is not much smooth time series data available for long bond tenors - the available Bloomberg series are only given as averages for. ${\tt>}10{\tt y}$ tenors,

$1n\%,$ vs Tenor

![](6d0c1bc5ee97887e12bea25248331e171fdc89a45b5485070dbdeee287914504.jpg)
Figure 8.17: Convexity adjustment - bond returns constant. Source: Commerzbank, Bloomberg

![](505a0c3e28724b190bc2f9e9a4ac1b866537544cd35fb704ac2e834306464d7c.jpg)
Figure 8.18: Convexity adjustment - bond prices follow forwards. Source: Commerzbank, Bloomberge

for example. Thus we have taken the bond yield as equal to the coupon, which is a reasonable approximation over the long term.

How have we created the convexity adjustment? We have used (7) to calculate. convexity value for Figure 8.17, and (8) for Figure 8.18, and then we added this amount to the bond yield. Figure 8.17 assumes that current bond returns (repre-. sented by yields) persist into the future, not that the bond prices will follow the forward price curve.

It is important to note that though the calculation for the value of convexity is fairly well known, there are different ideas about how to integrate it into the current yield curve. If we assume that the entire market knows the value of convexity and. that this is priced into the curves, then the true' curve would be lower than the mar-. ket values. This is assumed in Ilmanen (1995), but it is by no means universal, and would indicate that the 'true' long-dated returns are close to zero. If, rather, we believe that convexity value adds to the current returns, we would add the convexity value to the yield curve, as in Figures 8.17 and 8.19. It would certainly be possible to make a case that 'some part' of the convexity value is priced in, but that then involves another set of calculations and assumptions, all increasingly made with little data to rely upon. We have therefore used the simplest method and have added convexity value to the current curve, resulting in Figures 8.17 and 8.18.

Many previous papers have shown that generally, prices in FX and interest rates don't necessarily follow the forward curve. Thus if we use the current curve to calculate convexity value (as for Figure 8.17), how much value is there in the curve at the long end? Right at the long end, at the 30y tenor, we see nearly 70 bp of value, whereas at the 10y point, we see about 10 bp of value. Thus, is there perhaps 40 bp (average of 10 and 70) to capture at the current time? Or is some already priced in?

If we say that our 10y-30y steepener trade was at least partly driven by convex-. ity, it regularly captured 15-20 bp of value. From our quick initial calculation, there is certainly enough convexity value in the curve to supply this, even if some is al-. ready priced in.

It is worth a quick note on bond returns vs bond yields. Strictly speaking, they. are not the same, but for example in Figure 8.18, following Ilmanen (1995), we have conflated them, which is a frequent assumption. Ilmanen (1995) also assumes that. the convexity-adjusted black curve in Figure 8.17 is analogous to a 1y forward curve and backs out a spot curve from it. However, to our mind, it is not clear what this spot curve would represent, as it is not necessarily a forecast or an adjustment..

# The Long End of the Curve

There is increasing interest in very long-dated instruments from investors, not least because they have desirable high convexity. Though there is little useful timeseries data for bonds with tenors greater than 30 years, the swap market is another matter. Spot and forward swap data are available for the 50y tenor for some years. Though swaption volatility is not available, volatility curves tend to flatten at the long end. so the 30y vol may be used as a proxy for the 50y. In Figures 8.19 and 8.20, we show the swap yield with and without convexity adjustment, and then in Figure 8.20, we show the 1y forward swap rate with the same adjustment, which is another way of looking at the expected return in a year's time. In fact, in the current environment, forward and spot curves are almost identical..

![](ac89f20007e71ada15d50f9b0b1cfef709410e87f35da71d96680052d97f4496.jpg)
Figure 8.19: Convexity adjustment - swap yield. Source: Commerzbank, Bloomberg

![](b4d8f37ffba6a417fe4a190ede8d5bfcee36d9fd41aa8d8536d47629d65eac68.jpg)
Figure 8.20: Convexity adjustment - 1y forward swap. Source: Commerzbank, Bloomberge

As can be seen, the convexity adjustment means that longer-term instruments become much more desirable - which may go some way to explain investors' appetite for long-dated instruments.

# Value of Convexity through Time

To see how this convexity adjustment has varied in the past, we take historical 1y forward swaption volatilities and German government bond rates, and look at the convexity value of the 30-year point by using the coupon timeseries scaled as previously described. In Figure 8.21, it is about 60-70 bp at the current time. We see that this is in fact fairly modest and that convexity has had significant value in previous years. We then perform the same operation for the 50y swap rates to obtain Figure 8.22. As may be expected, they show similar patterns, but the adjustment is much larger for the longer tenor.

![](2838542b8e849e58d085c7ca93fb52b82f8e68d303cf4ffb22fc851b03ccf0f4.jpg)
Figure 8.21: Convexity adjustment - 30y German bonds. Source: Commerzbank, Bloomberg

![](bc81d89e2c071a3a191b11981af4b2d3ee3bdce68d7ac042b4dbd2fb515747d5.jpg)
Figure 8.22: Convexity adjustment - 50y EUR swaps. Source: Commerzbank, Bloomberg

The swaption data was patchy and had to be interpolated and extrapolated at. times, and we have also used an annual approximation for the calculation of convexity -- however, this seems to make little difference..

# Conclusion

Having identified a 10s-30s steepener trade in the long end of the yield curve which seems to deliver consistent returns over many currencies, delivering 15-20 bp of value annually, we find that the convexity value extant at those tenors is certainly enough to deliver that level of return, perhaps more. At the 30 year point, the current values of yield and convexity indicate that the convexity value is about 60-70 basis points, which is very significant in these low-yield times. However, in addition to delivering insight to the origin of the returns delivered by the trade, this substantial convexity value goes a long way to justifying the current flat curve and. inverted forward curve. We can say that the longer tenor investments are still offering value despite the flat curve environment, once convexity effects are taken into consideration.

It is clear from this analysis that the market systematically undervalues convexity. Current values would indicate that the long-dated bonds are cheap, but today's convexity values are moderate compared to some in the past, so clearly this misvaluation has been in place for some time. This agrees with the persistence of the 10s-30s steepener trade.

As an example of how long-dated instruments can have unexpectedly good value, consider the UK government's decision in 2014 to repay part of the First World War. debt. These bonds were issued as paying $5\%$ and $3.5\%$ , which at the time was low. In 2014, investors holding the 'consols' were doing very well! After one hundred years, the UK government paid off the bonds, along with some others, some of which were issued by William Gladstone in 1853 to consolidate the capital stock of the South Sea. Company. It's safe to say that the holders of those bonds had done extremely well, on average, over the years.

Looking for other opportunities, it would seem that in general, 'non-inversion'. curve plays, that the 10s-30s steepener belongs to, would be profitable. However,. there are probably features of the shorter end of the curve that also fall into this category and would reward investors, which may repay further investigation..

# Appendix 8.A: EUR Ratios

![](bf8495b9801b0aa76732a00bab1c0a4b1e25d7a620111230ef9117fd8fd8f692.jpg)
Figure 8.23: Ratio of standard deviations of forecast moves/actual moves (EUR 1y forward). Source: Commerzbank, Bloomberg

![](0706a1aea204c9be7f0d451da91c9d7fb2dcf34e34634b413cdbd14227af0610.jpg)
Figure 8.24: Ratio of standard deviations of forecast moves/actual moves (EUR 2y forward). Source: Commerzbank, Bloomberg

EUR Swap Slopes, 5y forward, s.d.(forward)/s.d.(actual)

![](e8ccc2ad0bf9c51c49d15da738727ea8aeb05b5c0b65f42105973252ce7004c1.jpg)
Figure 8.25: Ratio of standard deviation of forecast moves/actual moves (EUR 5y forward). Source: Commerzbank, Bloomberg

![](cbab855a5333709cc35d760c4fe07751b95553a999a22bf82e1985974183009c.jpg)
Figure 8.26: Ratio of means of actual moves/forward moves (EUR 1y forward). Source: Commerzbank, Bloomberg

![](d0c790ab0326534a6683ae9882208d928505bbd426623084f454a8aeadb5f4e3.jpg)
Figure 8.27: Ratio of means of actual moves/forward moves (EUR 2y forward). Source: Commerzbank, Bloomberg

![](fd6d190fe5cdca30936d44008044431275cfecfce791d80cd6ba42789ab0c94e.jpg)
Figure 8.28: Ratio of means of actual moves/forward moves (EUR 5y forward). Source: Commerzbank, Bloomberge

# Appendix 8.B: USD Ratios

![](f40e7d961a48b483f6f26cb03c54adedf08d90e2bc6bd0ccfe37bf0f36e9c5a6.jpg)
Figure 8.29: Ratio of standard deviations of forecast moves/actual moves (UsD 1y forward). Source: Commerzbank, Bloomberg

![](662ada318d519135312e543e614ea1ca4843f54facace692fef28f6bcf403d6e.jpg)
Figure 8.30: Ratio of standard deviations of forecast moves/actual moves (UsD 2y forward). Source: Commerzbank, Bloomberg

![](cbb3894b7b793a6d74b6e1c84fe658ab38e24050996a45ca253467d39a137cb6.jpg)
Figure 8.31: Ratio of standard deviations of forecast moves/actual moves (UsD 5y forward). Source: Commerzbank, Bloomberg

![](ede1227d57b92de167a740623808d1f4788ce992e52ae84b4a5b41332a3f050f.jpg)
Figure 8.32: Ratio of means of actual moves/forward moves (UsD 1y forward). Source: Commerzbank, Bloomberge

USD Swap Slopes, 1y forward, mean(actual)/mean(forward)

![](3d686c65660fc82f8ba5e6e6bad9328db3d2410c4b3e40a734587d5a6bbffb86.jpg)
Figure 8.33: Ratio of means of actual moves/forward moves (UsD 2y forward). Source: Commerzbank, Bloomberg

![](1d4abfb165815efee13b2d1fe7ca596da053ce47c715ca12489e583f60b78c17.jpg)
Figure 8.34: Ratio of means of actual moves/forward moves (UsD 5y forward). Source: Commerzbank, Bloomberg

# Appendix 8.C: Implied vs Actual Slope Changes, 2001-2007

$1-2y,\%,$ from 1y to 5y forward, 2001-2007

![](dfa49ad81536b462528f9e57773e2a7b30df93b800656505219123f1cc4d94f6.jpg)
Figure 8.35: Implied slope change (2001-7, 1-2y). Source: Commerzbank, Bloomberge

![](4dbf106ae34546cbfdfaa7b5dbbeff5c8bf3fa5204c2507b9f3fa39f12c40e71.jpg)
Figure 8.36: Actual slope change (2001-7, 1-2y) Source: Commerzbank, Bloomberg

![](a4143b9d1b74b2263f021fed5c9e9be45514d4451f086a54827c8c619662ef5a.jpg)
Figure 8.37: Implied slope change (2001-7, 2-10y). Source: Commerzbank, Bloomberge

$2-10\lor,\%,$ from 1y to 5y forward, 2001-2007

![](ecc529ef2d31fb40ab26069bf75958a2b9a8a6608511a5cebc448457ef6c8701.jpg)
Figure 8.38: Actual slope change (2001-7, 2-10y). Source: Commerzbank, Bloomberge

![](037184d505542eb5c834060d11a9370c8ef34660f4930e74feadf3a8a168613a.jpg)
Figure 8.39: Implied slope change (2001-7, 10-30y). Source: Commerzbank, Bloomberg

![](3fb0261bc25c9835199bddb9948e310231a3a13640561a59bc718d9835362a91.jpg)
Figure 8.40: Actual slope change (2001-7, 10-30y) Source: Commerzbank, Bloomberg

# Appendix 8.D: Implied vs Actual Slope Changes, 2007-2014

$1-2y,\%$ from 1y to 5y forward, 2007-2014

![](5af9b70ededec2425b3291c342476357ad114eed2c3e930b128edb021fd6b3ad.jpg)
Figure 8.41: Implied slope change (2007-14, 1-2y). Source: Commerzbank, Bloomberg

$1-2y,\%$ from 1y to 5y forward, 2007-2014

![](6a9b7b6e4d84f78324a4760485a253e08bb86805f6072c4d44d0f43750b0eb3d.jpg)
Figure 8.42: Actual slope change (2007-14, 1-2y). Source: Commerzbank, Bloomberge

$2-10\lor,\%,$ from 1y to 5y forward, 2007-2014

![](a8700bd8c52eff6a8bb184f08bd020eb39f74f49c84364d938102d5448bddb15.jpg)
Figure 8.43: Implied slope change (2007-14, 2-10y). Source: Commerzbank, Bloomberg

$2\scriptstyle-10\vee,\%,$ from 1y to 5y forward, 2007-2014

![](a763eaf0b9ed50ba432a3dc79d2ee55eff0912979bfa4533e7563b6eb5b3ed7a.jpg)
Figure 8.44: Actual slope change (2007-14, 2-10y). Source: Commerzbank, Bloomberg

![](a5e8122c596fe0ddadc184b1dcbfbf685180bc591d565885c88cb947201cacda.jpg)
Figure 8.45: Implied slope change (2007-14, 10-30y). Source: Commerzbank, Bloomberg

![](14b7bf23d53fdfc1f4704bf94875defc082529197d319acae45d7eb00aaafb3d.jpg)
Figure 8.46: Actual slope change (2007-14, 10-30y). Source: Commerzbank, Bloomberg

# Appendix 8.E: Implied vs Actual Slope Changes, 2014-2020

$1-2y,\%,$ from 1y to 5y forward, 2014-2020

![](2099fba62bb36e869cf519dec8b896e3ecf19eda95d1ccccd1a561a6cd2de97c.jpg)
Figure 8.47: Implied slope change (2014-20, 1-2y) Source: Commerzbank, Bloomberg

![](39e70e1e945cc20d507f0807ecbd0ebdde4b9a9e0eddfaaa688e2675f5bbf3db.jpg)
Figure 8.48: Actual slope change (2014-20, 1-2y). Source: Commerzbank, Bloomberge

![](dc3141a349c734316deb713620418c0f5bf8da072222d25d133d6671ffc9ed0c.jpg)
Figure 8.49: Implied slope change (2014-20, 2-10y). Source: Commerzbank, Bloomberge

$2-10\lor,\%,$ from 1y to 5y forward, 2014-2020

![](abd4e1b670c75f7ea604c9936b690f55aff2b6b07ea32dd9de13bb573b42ec9a.jpg)
Figure 8.50: Actual slope change (2014-20, 2-10y). Source: Commerzbank, Bloomberge

$10-30\vee,\%,$ from 1y to 5y forward, 2014-2020

![](1becf74c8d72ea60a1a0480f8d7c06c361445675a23893c521083dce29d3ac3e.jpg)
Figure 8.51: Implied slope change (2014-20, 10-30y). Source: Commerzbank, Bloomberg

$10-30\vee,\%,$ from 1y to 5y forward, 2014-2020

![](1a146210330f37a7f105cff9a613a78fd5ad8a99e134dcf2083dd18ce7cac07a.jpg)
Figure 8.52: Actual slope change (2014-20, 10-30y). Source: Commerzbank, Bloomberg
