---
title: BUS 35130 SPRING 2024 SOLUTION TO HOMEWORK 1
tags:
  - ar1_process
  - estimation_forecast
  - interest_rates
  - mean_reversion
  - ols_regression
aliases:
  - BUS 35130 HW1
  - Homework 1 Solution
key_concepts:
  - AR(1) Process
  - BEY Calculation
  - Bid and Ask Yields
  - Mean Reversion Modeling
  - OLS Regression
---

---

title: BUS 35130 SPRING 2024 SOLUTION TO HOMEWORK 1

# BUS 35130 SPRING 2024 SOLUTION TO HOMEWORK 1

John Heaton March 25,  2024

## ESTIMATION AND FORECAST

(PP) The difference between the bid and ask yields reflects the difference between bid and ask prices. Bid prices from dealers are less than ask prices and hence the bid yields are higher than ask yields. To convert to the "Asked Yield" we use the formulas in TN1,  on page 22,  to obtain BEY for maturities 6/11/2020 (quoted ask d = 0.093/100,  n = 66) and 3/25/2021 (quoted ask d = 0.160/100,  n = 353) as follows:
$$BEY_{6/11/2020}={\frac{365\times0.00093}{360-0.00093\times66}}=0.0943\%$$
$$B E Y_{3/25/2021}={\frac{365\times0.00160}{360-0.00160\times353}}=0.1625\%.$$
which are close to the corresponding asked yields in the quoted table.
(CP) We first eliminate the days that missing values. These are non-business dates (such as Christmas and Thanksgiving) on which no prices were recorded. Next,  note that the rates given in the datafile are in percentages. To get the BEY,  use the formula on Page 22 of TN1,  BEY = 365 ⇥ d 360 d ⇥ 91.

- The quoted discounts and BEYs are plotted below in Figure 1. You can see that the differences are very small.
1. The parameters can be estimated using an OLS regression.
(PP) We regress rt+1's on rt's. There are 17542 observations for the T-bill rates. Thus,  the observations 1-17541 can be treated as the independent variable X,  and observations 2-17542 as the dependent variable Y In general,  for a univariate regression of the form Yi = ff + Xi + ui,  i = 1*,  …,  n* the OLS estimates are
$$\begin{array}{r c l}{{\hat{\beta}}}&{{=}}&{{\frac{\sum_{i=1}^{n}\left(X_{i}-{\overline{{X}}}\right)\left(Y_{i}-{\overline{{Y}}}\right)}{\sum_{i=1}^{n}\left(X_{i}-{\overline{{X}}}\right)^{2}},  }}\\ {{\hat{\alpha}}}&{{=}}&{{{\overline{{Y}}}-{\hat{\beta}}{\overline{{X}}},  }}\end{array}$$
![1_image_0.png](1_image_0.png)
![1_image_1.png](1_image_1.png)
Finally,  to estimate the standard error of the error term,  we can first compute the sample standard errors,
$${\hat{u}}_{i}=Y_{i}-{\hat{\alpha}}-{\hat{\beta}}X_{i},  $$
uˆi = Yi ffˆ ˆXi,  i = 1*,  …,  n.*
Then
$${\hat{\sigma}}={\sqrt{\frac{1}{n}\sum_{i=1}^{n}{\hat{u}}_{i}^{2}}}.$$
$i=1,  …,  n$.
NOTE: The adjustment in ˆ for degrees of freedom is not typical in time series regression. Because the right-hand-side variable is a random variable the typical results about unbiasedness of regression estimates do not apply here. Main point: if you divided by n versus n2 with such are large sample there will be little numerical difference!
(P P) AR(1) process for interest rates is the following:
rt+1 = ff + rt + "t (1)
"Mean reversion" of interest rates can be modeled with AR(1) process since,  according to AR(1) process,  the projected interest rates converge to the long-term level of interest rates over time under stationarity condition,  i.e. when || < 1. In this case,  the long-term level of interest rates,  i.e. "unconditional mean",  under AR(1) process is the following:
$$E(r)={\overline{{r}}}={\frac{\alpha}{1-\beta}}$$
1
To better see the mean reversion,  subtract rt from both sides and rewrite rt+1 rt = (1) [r rt] + "t (2)
Thus,  if rt > r,  we have E[rt+1 rt] = (1) [r rt] < 0,  and hence a high rate tends to be followed by a negative *change* in interest rates,  and vice-versa.
(CP) The results of the regression are summarized in Table 1.
Table 1: Estimation of the AR(1)

| Coecients   | t-value     |            |
|-------------|-------------|------------|
| ff           | 2.01702e-05 | 1.7677     |
|             | 0.9996      | 4.7224e+03 |
|             | 9.05099e-04 |            |

Given these estimates,  the average long-run interest rate is
$${\overline{{r}}}={\frac{\alpha}{1-{\hat{\beta}}}}=0.04874$$

1. The most current interest rate is from 2024-03-14,  r*T ODAY* = 5.3945%.
(P P) Let r*T ODAY* (n) denote the forecast for the interest rate n days from today. From the equation for AR(1) process above,  using the estimates of ff and,  we have r*T ODAY* (1) = ˆff + ˆ ⇥ r*T ODAY*.
If we compare the equation above with the equation for AR(1) process,  we see that the error term does not show up in the forecast. That is because we expect it to be 0. Next,  in order to forecast the interest rate 2 days from today,  we can just use the forecast we just made for tomorrow:
r*T ODAY* (2) = ˆff + ˆ ⇥ r*T ODAY* (1).
More generally,  r*T ODAY* (n + 1) = ˆff + ˆ ⇥ rT ODAY (n),  n = 1,  2,  3…
As a result,  the interest rate forecast for the following three days is the following:
r*T ODAY* (1) = ˆff + ˆr*T ODAY* = (2.01702e 05) + 0.9996 ⇥ 5.3945% = 5.3943%
r*T ODAY* (2) = ˆff + ˆr*T ODAY* (1) = (2.01702e 05) + 0.9996 ⇥ 5.3943% = 5.3941%
r*T ODAY* (3) = ˆff + ˆr*T ODAY* (2) = (2.01702e 05) + 0.9996 ⇥ 5.3941% = 5.3939%
Figure 2:
![3_image_0.png](3_image_0.png)
(CP) You can use a loop in Matlab or Python to compute the forecasts. The results are plotted below in Figure 2:
Our forecast of the AR(1) process also gets closer and closer to its long-run average1 as the forecasting horizon increases.
1. We can calculate yields from the Strip prices Z(*t,  T*) using the formula on page 12 of TN1:
Here,  t is the present date,  2024-03-14. We have multiple maturities T,  so we can calculate yields for different maturities. From these prices we can calculate the 6-month forward rates from the formula on page 41 of TN1:
f(t,  T1,  T2) = ln(Z(t,  T1)) ln(Z(*t,  T*2))
$$:\frac{l n(Z(t,  T_{1}))-l n(Z(t,  T_{2}))}{T_{2}-T_{1}}$$
(P P) Using the formula above,  i.e. y(*t,  T*) = 1T ln(Z(*t,  T*)),  the current yields for the first three maturities are determined as follows:
$${r}{\left({0},  {0.5}\right)}=-\frac{{1}}{{0.5}}{l}{n}{\left({0.9745}\right)}={5.174}\%$$ $${r}{\left({0},  {1}\right)}=-\frac{{1}}{{1}}{l}{n}{\left({0.9526}\right)}={4.859}\%$$ $${r}{\left({0},  {1.5}\right)}=-\frac{{1}}{{1.5}}{l}{n}{\left({0.9330}\right)}={4.622}\%$$
Using the formula above,  i.e. f(t,  T1,  T2) = ln(Z(t,  T1))ln(Z(t,  T2))
T2T1,  the forward rates for the first three maturities are determined as follows:
1The long-run average of this AR(1) process is given by ff/ (1) when < 1.
$\ln\left(Z(t,  T_{0})\right)=\ln\left(Z(t,  T_{0})\right)$.
![Financial Distress,  Reorganization,  And Organizational Efficiency-2.png](Financial%20Markets%20and%20Institutions/I-%20Introduction%20to%20Financial%20Markets%20and%20Intermediation/Class%201-Introduction%20to%20Financial%20Markets%20and%20Intermediation/Financial%20Distress,  %20Reorganization,  %20And%20Organizational%20Efficiency%20(attachments)/Financial%20Distress,  %20Reorganization,  %20And%20Organizational%20Efficiency-2.png)
(CP) Figure 3 shows the yield and forward curve extracted from the strips,  while Figure 4 shows the implicit forecasts from the Strips and the forecasts calculated in question
(3):
These forward rates are often thought of as market forecasts of future (6-month)
interest rates. As we shall see,  this is not correct,  as we need to adjust for "a market risk premium" (as well as a convexity factor). In the terminology that we will develop,  forward rates are "expected future rates" under the risk neutral dynamics (plus a convexity factor). But the market participants are not risk neutral,  and therefore forgetting the risk premium may yield serious forecast errors.
![5_image_0.png](5_image_0.png)
## BUS 35130 SPRING 2024

Solution to Homework 2 John Heaton
 March 31,  2024 $\phantom{\rule{0ex}{0ex}}$.
1

## INVERSE FLOATER
1. (PP) The size of the Treasury securities data available on February 17,  2009 is huge. In order to perform the bootstrap procedure,  we need securities at semi-annual frequency.
We can cherry-pick from the dataset such securities. Table 1 contains the data used in the bootstrap procedure. Unfortunately,  already at T = 10 years we do not have notes with maturities at semi-annual frequency; using bonds we can get to T = 12.5,  but they may have some price di!erences due to liquidity. (For instance,  see the break at T = 10 in both Figure 1 and 2.) Even using bonds,  we must stop the procedure after T = 12.5 as there is no more data at semi-annual frequency. To bootstrap the discounts,  we can use the procedure illustrated in teaching notes:
For every i
$$Z(0,  T_{i})=\frac{P(0,  T_{i})-c^{i}/2(\sum_{j=1}^{i-1}Z(0,  T_{j}))}{1+c^{i}/2}$$
Alternative,  we can use a matrix formulation. In line with the semi-annual frequency,  let Ti = i2 for 1 ↑ i ↑ 25. Define a cash-flow matrix,  C,  where an element cij denotes the payo! at time Tj of the bond with maturity Ti. By ordering the bonds increasing in maturity,  C is lower diagonal. Also,  let P denote a column vector with element pi equal to the price of bond with maturity Ti. In particular,  we have
$${\left[\begin{array}{l}{P^{1}(0,  T_{1})}\\ {P^{2}(0,  T_{2})}\\ {\vdots}\\ {P^{n}(0,  T_{n})}\end{array}\right]}={\left[\begin{array}{l l l l l}{c^{1}/2+100}&{0}&{0}&{\cdots}&{0}\\ {c^{2}/2}&{c^{2}/2+100}&{0}&{\cdots}&{0}\\ {\vdots}&{\vdots}&{\ddots}&{}\\ {c^{n}/2}&{c^{n}/2}&{c^{n}/2}&{\cdots}&{c^{n}/2+100}\end{array}\right]}{\left[\begin{array}{l}{Z^{1}(0,  T_{1})}\\ {Z^{2}(0,  T_{2})}\\ {\vdots}\\ {Z^{n}(0,  T_{n})}\end{array}\right]}$$
![6_image_0.png](6_image_0.png)
$${\mathrm{or,  ~in~vector~notation}}$$
$$P=C Z$$
where Z is a column vector with i element equal to Z(0,  Ti). Then,  we obtain
$$Z=C^{-1}P$$
Note that the P vector is made up of the invoice or *dirty* prices. Here,  the securities are handpicked to have zero accrued interest,  so this simplifies. The calculations below take the price to be the mean of the bid and ask quotes.
(PP) Use the bond data as of February 17,  2009 and applying formulas on page 48 from TN1,  the bootstrapped yields to maturity for maturity 0.5,  1,  and 1.5 are
calculated as follows: $Z(0,  0.5)=\dfrac{P^1(0,  0.5)}{1+\frac{c^2}{2}}=\dfrac{1.0150}{1+\frac{0.025}{2}}=0.9975$ $Z(0,  1)=\dfrac{P^2(0,  1)-\frac{c^2}{2}Z(0,  0.5)}{1+\frac{c^2}{2}}=\dfrac{1.0291-\frac{0.035}{2}0.9975}{1+\frac{0.025}{2}}=0.9942$ $Z(0,  1.5)=\dfrac{P^3(0,  1.5)-\frac{c^3}{2}(Z(0,  0.5)+Z(0,  1))}{1+\frac{c^3}{2}}=\dfrac{1.0522-\frac{0.0413}{2}(0.9975+0.9942)}{1+\frac{0.0413}{2}}=0.9907$
where the bond prices are determined as the average of bid and ask values
(CP) Table 1 displays the data from the selected securities. We show the di!erence in term structure depending on the type of securities used. The left panels shows the bonds that were issued most recently ("new bonds") while the right panel shows the bonds that were issued long aog. The column type is 2 for a note and 1 for a bond.
Figures 1 and 2 plot the discount function and the yield curve implied by these calculations. The vertical dotted line denotes the point at which bond securities are used to bootstrap also for the "new bonds". Clearly,  depending on the type of securities used,  we can get quite di!erent results. The period surrounding 2009 showed large di!erences between new bonds and old bond prices,  due to liquidity. Newly issued bonds were much more liquid than old bonds,  which resulted in large price discrepancies. (The comparison between old and new bonds was not part of the assignment).
Table 1: Securities used in Bootstrap
Maturity Type Coupon Ask Bid Ti Maturity Type Coupon Ask Bid Ti
New Bonds Old Bonds
20090815 2 3.5 101.4844 101.5156 0.4944 20090815 2 6 102.6797 102.7109 0.4944 20100215 2 3.5 102.8945 102.9258 0.9944 20100215 2 6.5 105.7461 105.7773 0.9944
20100815 2 4.125 105.2031 105.2422 1.4944 20100815 2 5.75 107.6875 107.7344 1.4944
20110215 2 5 108.5313 108.5625 1.9944 20110215 2 5 108.5313 108.5625 1.9944 20110815 2 5 110.2656 110.3125 2.4944 20110815 2 5 110.2656 110.3125 2.4944 20120215 2 1.375 100.4453 100.4766 2.9944 20120215 2 4.875 110.7656 110.8125 2.9944
20120815 2 4.375 110.8672 110.8984 3.4944 20120815 2 4.375 110.8672 110.8984 3.4944
20130215 2 3.875 109.9063 109.9531 3.9944 20130215 2 3.875 109.9063 109.9531 3.9944 20130815 2 4.25 112.1563 112.2188 4.4944 20130815 2 4.25 112.1563 112.2188 4.4944 20140215 2 4 111.6719 111.7344 4.9944 20140215 2 4 111.6719 111.7344 4.9944
20140815 2 4.25 113.3594 113.3906 5.4944 20140815 2 4.25 113.3594 113.3906 5.4944
20150215 2 4 111.9063 111.9375 5.9944 20150215 1 11.25 150.4375 150.4688 5.9944 20150815 2 4.25 113.2031 113.2344 6.4944 20150815 1 10.625 149.9219 149.9531 6.4944 20160215 2 4.5 114.875 114.9063 6.9944 20160215 1 9.25 142.7813 142.8125 6.9944 20160815 2 4.875 117.0781 117.1094 7.4944 20160815 2 4.875 117.0781 117.1094 7.4944 20170215 2 4.625 115.4844 115.5313 7.9944 20170215 2 4.625 115.4844 115.5313 7.9944 20170815 2 4.75 116.8438 116.875 8.4944 20170815 1 8.875 144.9531 145 8.4944
20180215 2 3.5 107.5781 107.6406 8.9944 20180215 2 3.5 107.5781 107.6406 8.9944
20180815 2 4 111.6875 111.7188 9.4944 20180815 2 4 111.6875 111.7188 9.4944 20190215 2 2.75 100.875 100.9375 9.9944 20190215 1 8.875 149.5938 149.625 9.9944 20190815 1 8.125 143.8438 143.875 10.4944 20190815 1 8.125 143.8438 143.875 10.4944
20200215 1 8.5 147.7266 147.7578 10.9944 20200215 1 8.5 147.7266 147.7578 10.9944
20200815 1 8.75 151.1563 151.1875 11.4944 20200815 1 8.75 151.1563 151.1875 11.4944 20210215 1 7.875 143.5391 143.5703 11.9944 20210215 1 7.875 143.5391 143.5703 11.9944 20210815 1 8.125 147.1094 147.1406 12.4944 20210815 1 8.125 147.1094 147.1406 12.4944
![8_image_0.png](8_image_0.png)
3
![9_image_0.png](9_image_0.png)
1. (PP) The value of the Leveraged Inverse Floater can be computed as follows. The coupon rate at any time t is given by
## C(TI) = 10% → 2 ↓ R2(TI→1) (1)

The investor who is long the Leveraged Inverse Floater receives a 10% fixed coupon and pays "floating" at the rate that is twice the floating six month T-bill rate (six months lag). At maturity,  in addition,  the investor will receive the principal. Therefore,  it is *as if* the investor is long one 10% coupon bond with five year to maturity and short 2 floating rate bonds with five year to maturity. This combination ensures receiving a cash flow over time identical to (1). However,  such a position would imply an outflow of the principal at maturity,  instead of an inflow. It follows that we need to add two zero coupon bonds with five year maturity to exactly mimic all of the cash flows from the Leveraged Inverse Floater.
(CP) The price of the inverse floater is then
$$P_{I F L}(0;5)=P_{F i x e d}(0,  5)-2\times P_{F l}(0;5)+2\times Z(0;5)$$
Given the discount function in Table 1 above,  we have
$$(2)$$
$$\begin{array}{r c l}{{P_{F i x e d}(0;5)}}&{{=}}&{{140.74;}}\\ {{}}&{{P_{F l}(0;5)}}&{{=}}&{{100;}}\\ {{}}&{{Z(0;5)}}&{{=}}&{{92.35}}\end{array}$$
obtaining a value for the Leveraged Inverse Floater equal to PIFL(0; 5) = 125.43 Note that in the computation above we are implicitly assuming that the coupon c(Ti) will never get negative,  as the Leverage Inverse Floater would never require an additional payment from investors.
(PP) What is the benefit from going long the Leveraged Inverse Floater? The current semi-annual rate on February 17,  2009 was 0.49%. Therefore,  the current cash flow from this security is 9.02% so long the short term rate does not increase. Given the data above,  a fixed rate coupon bond with the a 5-year maturity has a coupon equal to c = 4.0%. Of course,  this bond is also cheaper at 111.70. However,  the discount function above implies that the price of a fixed-rate 5-year bond with coupon of 9.2% would have a price of 135.97. As long as the short rate does not move,  the Leveraged Inverse Floater generate a higher cash flow without increasing the price comparably. For this reason,  investments in this type of instruments are called "yield enhancing strategies". Yet,  they imply a speculation on the direction of interest rates movements,  as discussed next.

1. (PP) The duration of the fixed rate bond is based on the following general formula
$$D_{F i x e d}=\sum_{i=1}^{n}w_{i}T_{i}=4.2141$$
where $T_{i}=0.5,  1,  …$ and
$$w_{i}={\frac{Z(0;T_{i})c_{i}/2}{P_{F i x e d}}}{\mathrm{~for~}}i=T_{i}=0.5,  …5{\mathrm{~and~}}w_{n}={\frac{Z(0;T_{n})(1+c_{i}/2)}{P_{F i x e d}}}{\mathrm{~for~}}T_{n}=5.$$
The duration of the Leveraged Inverse Floater can be computed from the rule "the duration of a portfolio is equal to the weighted average of the durations." So,  first,  we need to compute the duration of each of the securities in formula (2). The duration of the zero coupon bond Z(0,  5) is DZ = 5,  while the duration of the Floating Rate Bond is DF L = 0.5,  six months,  and the duration of the fixed rate bond is D*F ixed* = 4.2141 as shown above.
(CP) It then follows that the duration of the Leveraged Inverse Floater is
$$D_{L I F}$$
DLIF = 1
$$\begin{array}{r l}{={}}&{{}{\frac{1}{P_{L I F}}}\times(P_{F i x e d}(0,  5)\times D_{F i x e d}-2\times P_{F I}(0;5)\times D_{F I}+2\times Z(0;5)\times D_{Z})}\\ {={}}&{{}{\frac{1}{125.43}}\times(140.74\times4.214-2\times1\times0.5+2\times92.35)\times5)}\\ {={}}&{{}11.29}\end{array}$$
(PP) According to the duration of LIF of 11.29,  it is obvious that it has quite a high sensitivity to interest rates. Figure 3 plots the value of the Leveraged Inverse Floater,  plotted against a parallel shift in the term structure of interest rates. The decline in value for a shift up in interest rates is quite dramatic. The dash-dotted line plots the decline in value for the 5-year fixed rate bond,  with coupon rate 4.0%,  which is valued at 111.70 on February 17,  2009. The duration of the 5-year fixed bond is 4.60.
Thus,  the sensitivity to interest rates is much smaller,  as illustrated in Figure 3. Finally,  note in Figure 3 that the peturbations are mainly positive. This is because the short rate is already at 0.49%,  so negative parallel shifts must be quite small to keep the short rate sensible.
(PP) In general,  convexity of the fixed rate bond is calculated as follows:
$$C_{F i x e d}=\sum_{i=1}^{n}w_{i}T_{i}^{2}=19.6431$$
Accordingly,  convexity of the inverse floater can be computed as the weighted average of the convexities of the securities in the mimicking portfolio. The convexity of the zero coupon bond is CZ = 52 = 25,  while the convexity of the floating rate bond is essentially zero CF l = 0.52 = 0.25.
(CP) It follows that the convexity of the inverse floater is
$$C_{LIF}=\frac{1}{P_{LIF}}\times(P_{Fixed}(0,  5)\times C_{Fixed}-2\times P_{Fl}(0;5)\times C_{Fl}+2\times Z(0;5)\times C_{Z})$$ $$=\frac{1}{125.43}\times(140.74\times19.6431-2\times100\times0.25+2\times92.35)\times25)$$ $$=58.45$$
Compare this to the quoted 5-year fixed rate bond which has a much lower convexity of 22.30.
![12_image_1.png](12_image_1.png)
![12_image_0.png](12_image_0.png)
Figure 3:
# BUS 35130 SPRING 2024

Solution to Homework 3 John Heaton
 April 7,  2024 $\text{}$

## PART I. DURATION HEDGING AND FACTOR NEUTRALITY

For simplicity,  we are going to assume that at the two dates the LIF still has 5 years to maturity. To find the price of the LIF,  we need to find zero coupon prices to discount the cash flows of the security. The Z's are embedded in the yield curve data given so we need to extract them. Unlike homework 2,  this time we cannot proceed by bootstrapping since we do not have price data for bonds of di!erent maturities as of each date. An alternative is to interpolate the [[Lecture 7-Risk and Return of Bonds#7.1 Zero-coupon yield curve|zero-coupon yield curve]] using the data given. Interpolation is fine in this case because these are zero coupon yields,  and so there is no theoretical error in doing this approximation. In Matlab we can do the interpolation as follows:

## Y INT=INTERP1(MAT,  YIELDS,  MATINT,  'CUBIC')

where Mat is a vector of the maturities for which we have data,  yields is a vector with the corresponding data on yields,  MatInt is the vector of maturities (in this case semiannual) for which we need yields,  and cubic is just the interpolation method (cubic uses a polynomial of degree 3 to approximate the yield curve). Once we have built the yield curve we can back out the Z's and calculate the value of the LIF as we did in homework 2. The price of the LIF as of the two dates is:
Table 1: LIF Prices

| PLIF March 31,   2009   | PLIF April 30,   2009   |
|-----------------------|-----------------------|
| 124.30                | 119.04                |

![13_image_0.png](Z.%20Clippings/13_image_0.png)
Now we can compare the change in price between the two dates with the one predicted by the duration and convexity calculation performed in homework 2. For the duration-based calculation we need to compute an average change across maturities. The reason is that 1
![14_image_0.png](14_image_0.png)
![14_image_1.png](14_image_1.png)

| Dur-based   | Dur/Conv-based   | Actual     |
|-------------|------------------|------------|
| Return (%)  | Return (%)       | Return (%) |
| -2.015      | -2.005           | -4.233     |

As we can see,  both the duration based computation and the duration/convexity based computation understate the change in value. The reason is that the yield curve is changing its shape in a non-parallel manner as shown in Figure 1. One way to take into account these non-parallel changes is to use two or more factors from the principal components analysis.
The principal components approach is explained in detail in TN2. Notice that the magnitude of the eigenvalues is related to the proportion of the variance in the data explained by their corresponding factors. Matlab orders the eigenvalues in ascending order. Therefore,  if we want to use a two-factor model the eigenvectors that we must use are the last two in
![15_image_0.png](15_image_0.png)

| Maturity(years)   |        |        |        |         |         |         |         |         |         |         |
|-------------------|--------|--------|--------|---------|---------|---------|---------|---------|---------|---------|
| 0.5               | 1      | 1.5    | 2      | 2.5     | 3       | 3.5     | 4       | 4.5     | 5       |         |
| ε1,  i              | 0.3391 | 0.3657 | 0.3519 | 0.3321  | 0.3178  | 0.3060  | 0.2976  | 0.2900  | 0.2804  | 0.2669  |
| ε2,  i              | 0.6615 | 0.3785 | 0.1677 | -0.0047 | -0.1024 | -0.1752 | -0.2558 | -0.3132 | -0.3182 | -0.2916 |

As in the teaching notes,  the first factor came out to have loadings (i.e. ε's) approximately constant across maturities,  and for this reason can be referred to as a "level" factor. The second factor has loading that switch sign between positive (at the short end) to negative (at the long end),  implying that when this factor kicks in,  the short-end of the term structure increases,  while the long end decreases. Such a behavior implies a shift in the slope of the term structure,  from which the name "Slope factor". Note that di!erently from the TN,  the betas of the second factor are positive at the short end and negative at the long end of the maturity spectrum,  rather than the other way around. In PCA there is an indeterminacy between the signs of ε's and the sign of the factor. If we define a new factor ϑ!2 = →ϑ2,  we obtain a factor that has loadings that are negative at the short end and positive at the long end of the maturity spectrum. The important fact is that when this factor kicks in,  it changes the slope. To calculate the factor durations we use the formulas in TN2. The duration of the LIF and its components with respect to the level and slope factors is

| Security   | Level Duration   | Slope Duration   |
|------------|------------------|------------------|
| LIF        | 3.007            | -3.953           |
| Fixed      | 1.155            | -1.118           |
| Zero       | 1.335            | -1.458           |
| Floating   | 0.170            | 0.331            |

With the factor durations now we can calculate the predicted change in the value of the LIF given the change in the factors between the two dates as follows
$$\phi_{l e v e l}-l$$
%"PLIF = →DLIF,  level ↑ "ϑlevel → DLIF,  slope ↑ "ϑ*slope* Table 5: Duration,  Convexity and Factor Approximations

| Dur-based   | Dur/Conv-based   | Factor-Based   | Actual     |
|-------------|------------------|----------------|------------|
| Return (%)  | Return (%)       | Return (%)     | Return (%) |
| -2.015      | -2.005           | -3.786         | -4.233     |

We see that the factor-based prediction is much closer to the actual return. The reason is that the factors incorporate changes along the entire term structure taking into account that those changes do not a!etc all maturities in the same magnitude or in the same direction.

## PART II: PREDICTABILITY OF BOND RETURNS

We start by looking at some plots. Consider the forward spread and the annual return on the 5-year bond. Figure 3 show their time series,  where we lag the return by 5-year to make it synchronous with the forward spread so as to highlight the correlation (if any). Figure
![17_image_0.png](17_image_0.png)
Figure 3: Annual Returns of 5-year Bond and 5-year Forward Spread 4 also shows a scatter plot of the 5 year forward spread versus the bond return of a 5 year bond. The figures show an association between forward rates and subsequent bond return,  although the cloud is rather wide and so the forward spread does not appear to explain a lot of the variation in bond returns. Figure 5 shows the (in sample) fit of the model,  when we predict future bond returns using the lagged forward spread.
Table 6 below formalizes this evidence using OLS regressions. We regress the log excess bond return on the forward spread: Let Zt(n) denote the zero coupon bond in year t with n year to maturity. Define the log excess bond return using a n→year bond as
$$L E R_{t}(n)=l o g\left(\frac{Z_{t+1}(n-1)}{Z_{t}(n)}\right)-l o g\left(\frac{1}{Z_{t}(1)}\right)$$
Denote also ft(n) the forward rate at t for an investment at n → 1 and maturity n. As we know ft(n) = log $ Zt(n)
Zt(n→1)%. We then run the regression
$$L E R_{t}(n)=\alpha+\beta[f_{t}(n)-y_{t}(1)]+\epsilon_{t}$$
Table 6 shows the results for each zero-coupon bonds with maturity n = 2*,  ..,  * 5
![18_image_0.png](18_image_0.png)
6
![19_image_0.png](19_image_0.png)

| n      | ϖ       | ε      | t(ϖ)    | t(ε)   | R2     |
|--------|---------|--------|---------|--------|--------|
| 2.0000 | 0.0467  | 0.7926 | 0.1937  | 2.4776 | 0.0839 |
| 3.0000 | -0.0935 | 1.0326 | -0.1907 | 2.4469 | 0.0820 |
| 4.0000 | -0.0918 | 1.0014 | -0.1327 | 2.1900 | 0.0668 |
| 5.0000 | -0.2947 | 1.1750 | -0.3536 | 2.3812 | 0.0780 |

## TABLE 6: FAMA - BLISS REGRESSIONS 1953 - 2023

Note implication of the empirical results:
A high forward spread =↓ predict high future bond excess return.
A positive bond excess return requires its yield to *decline* (yield ↔ Z(*t,  n*) ↗)
The forward spread is high when term structure slopes upwards
=↓ a rising term structure predicts lower future yields.
Cochrane - Piazzesi Factor. Cochrane - Piazzesi propose a single factor to predict future bond returns. In essence,  they define a factor as a linear combination of forward rates xt = a0yt + a1f(2)
t + … + a5f(5)
t The coe\#cients a0,  …,  a5 are estimated from another regression of average bond returns on forward rates. (This is slightly di!erent from the question in assignment,  in which you were allow to (a) use the regression coe\#cient in the Teaching Notes; and (b) use only 3 forwards instead of 5 as in original Cochrane and Piazzesi paper).
Table 7 shows the results of the regression

## TABLE 7: COCHRANE - PIAZZESI REGRESSIONS: 1953 - 2023

| n      | ϖ       | ε      | t(ϖ)    | t(ε)   | R2     |
|--------|---------|--------|---------|--------|--------|
| 2.0000 | -0.0353 | 0.4761 | -0.1501 | 3.1582 | 0.1296 |
| 3.0000 | -0.0791 | 0.8960 | -0.1848 | 3.2647 | 0.1372 |
| 4.0000 | -0.1820 | 1.2770 | -0.3113 | 3.4044 | 0.1475 |
| 5.0000 | -0.4561 | 1.6369 | -0.6162 | 3.4468 | 0.1506 |

Figures 6 to 8 show the performance of the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] factor to predict the return of a 5-year bond. Note that Figure 8 shows that the expected excess return predicted by [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] factor at
![21_image_0.png](21_image_0.png)
![22_image_0.png](22_image_0.png)
![23_image_0.png](23_image_0.png)
the end of sample is negative. That is,  the model implies a negative risk premium on the 5-year bond for the next year.
In-Sample vs Out-of-Sample Predictive Regressions (this was not part of the assignment). One important issue with Cochrane - Piazzesi factor compared to Fama - Bliss is that the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] regression is *in sample*. That is,  the factor [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] is first computed with a regression over the overall sample,  and *then* it is used to predict future bond returns. For the purpose of the paper - namely,  the inference about the existence of a common factor a!ecting bond returns - the procedure is fine. The objective of investigation in Cochrane and Piazzesi was to discover if there is a common factor a!ecting all bond expected excess returns. In sample regressions are perfectly fine for this investigation. However,  if we want to have an *investment strategy* we cannot use an in-sample regression,  but we need an outof-sample one. One possibility is to use data up to t to compute the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] factor,  and then use data after t for the regression. This can be done. However,  another methodology is to just use the forward rates used by [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] to predict future bond returns. That is,  run LERt(n) = ϖ + ε1yt(1) + ε2ft(3) + ε3ft(5) + ϱt
(we leave out ft(2) and ft(4) to avoid multicollinearity). Table 8 reports the result. As can be seen,  using the forward rates has a strong predictive power on future bond returns.
That is,  the results of the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] factor are not only due to it being an in-sample predictor,  but there is something in the forward rates that help explain future bond returns.

| n      | ϖ       | yt(1)   | ft(3)   | ft(5)   | t(ϖ)    | t(yt(1))   | t(ft(3))   | t(ft(5))   | R2     |
|--------|---------|---------|---------|---------|---------|------------|------------|------------|--------|
| 2.0000 | -0.9287 | -0.4445 | 0.5145  | 0.1040  | -2.0245 | -1.8193    | 1.0977     | 0.3114     | 0.1473 |
| 3.0000 | -1.3791 | -1.0557 | 1.3420  | -0.0475 | -1.6366 | -2.3523    | 1.5585     | -0.0774    | 0.1395 |
| 4.0000 | -1.8014 | -1.6754 | 2.0315  | -0.0831 | -1.5644 | -2.7319    | 1.7265     | -0.0991    | 0.1500 |
| 5.0000 | -2.6458 | -2.0297 | 1.9953  | 0.3936  | -1.8130 | -2.6116    | 1.3381     | 0.3705     | 0.1515 |

## TABLE 8: FORWARD-BASED REGRESSIONS: 1953 - 2023

PCA Regressions. (Also this part was not part of the homework). A final interesting question is whether PCA factors - level,  slope,  and curvature factors - described in previous section,  are able to explain future bond return. Indeed,  slope has been used several times as a predictor of future bond returns. Table 9 shows the result. Interestingly these factors are also predicting returns.
Table 9: PCA Regressions: 1953 - 2023

| n      | ϖ       | Level   | Slope   | Curvature   | t(ϖ)    | t(Level)   | t(Slope)   | t(Curvature)   | R2     |
|--------|---------|---------|---------|-------------|---------|------------|------------|----------------|--------|
| 2.0000 | -0.5401 | -0.0147 | -0.4397 | 0.9258      | -1.3640 | -0.4423    | -2.0009    | 1.1241         | 0.1319 |
| 3.0000 | -1.0036 | -0.0382 | -0.9823 | 1.2145      | -1.3835 | -0.6271    | -2.4399    | 0.8049         | 0.1286 |
| 4.0000 | -1.5253 | -0.0715 | -1.5455 | 1.5574      | -1.5478 | -0.8642    | -2.8258    | 0.7598         | 0.1494 |
| 5.0000 | -2.2703 | -0.1024 | -2.1469 | 1.7551      | -1.8359 | -0.9864    | -3.1282    | 0.6823         | 0.1675 |

# BUS 35130 SPRING 2024 SOLUTION TO HOMEWORK 4

John Heaton April 14,  2024 Part I: Real and Nominal Bonds The relation between nominal rates and real rates is
$$r_{n o m i n a l}(T)=r_{r e a l}(T)+\pi(T)-1/2\sigma_{\pi}^{2}+R P$$
That is,  the nominal rate equals the real rate,  plus expected inflation (this is the Fisher equation) plus a risk premium (RP) minus a (minor) convexity term,  as inflation increases nominal bonds in a convex manner. Higher expected inflation or higher risk premia increase the nominal rate. See discussion in the teaching notes.
The real rate can be negative. From the above relation,  this may simply mean that expected inflation is higher than the nominal rate (and the other terms). However,  economically,  why can a negative real rate can occur. A simple decomposition of real rates has
$r_{real}(T)=\rho+\gamma$Expected GDP Growth $-\dfrac{\gamma^2}{2}$Macroeconomics Risk.
That is,  why would an investor buy Treasury bonds? To set aside the issue of inflation,  consider TIPS (or real bonds). Why would an investor buy real bonds? Well,  for saving purposes. However,  this desire to save depends on two quantities: The prediction of economic growth and the amount of uncertainty in the economy. The higher the expected economic growth,  and the lower is the interest in savings. If the economy is strong,  our jobs are secure,  etc.,  then we can actually borrow (save less) to purchase homes,  cars and the like. This willingness of people to borrow for consumption tends to increase real rates
(r*real*(T) increases). On the other hand,  the higher is the macroeconomic risk in the economy,  the higher is the likelihood of "rainy days" which provides an incentive to borrow less and rather purchase bonds (real bonds) to have a bu!er against bad times (many financial advisors recommend families to set up "emergency funds". Well,  do not invest your emergency fund in stocks,  as you may need it exactly in bad times!). This savings requirement for rainy dais tend to decrease bond rates (as households bid up the price of bonds).
Negative rates therefore may due to a combination of low economic growth prospects but large macroeconomic risk. These quantities are weighted by the risk aversion ϖ of agents in the economy: the higher the risk aversion and the stronger the e!ects.
1 How do risk premia a!etc all this? In the first quarter of 2013,  the median forecast of professional forecaster about the average three month rate for the next 10 years was 2.4.
Our estimates of the yield curve on Jan 15 2013 show a 10-year yield around 2%. This implies that the average expected future short-term rate over the next 10 years is 0.4% higher than the 10-year yield. From the simple formula in TN 3
$$y_{t}(10)=E_{t}\left[\sum_{i=1}^{n}{\frac{1}{n}}y_{t+i}(0.25)\right]+R P_{t}$$
where n = 40 is the number of quarters in 10 years. If the yield is lower than the expected future yield,  according to the expectation hypothesis,  it should be due to a *negative* risk premium. A negative risk premium can occur whenever Treasury bonds have hedging properties against variation in the stock market. We finally move to fit the Nelson Siegel model to the TIPS on Jan 15,  2013. From the formula in the teaching notes
$$P^{T I P S}=\frac{I d x(T)}{I d x(0)}\left[\sum_{i=1}^{n}\frac{c}{2}Z(0,  T_{i})+Z(0,  T_{n})\right]$$
Quoted prices are already net of the index ratio. Moreover,  there is no accrued interest because the maturity are on the round semi-annual cycle. Therefore,  bid/ask reflect only the parenthesis itself. This makes it easier to compute the term structure of real rates then,  because we can use directly the bid/ask price (midpoint) and use those directly together with the cash flow matrix to compute the real zero coupon bonds. Figure 1 shows the fitting of the NS model to the data. As it can be seen,  the model fits well the data. Figure 2 shows the discount factor. Di!erently from nominal discount factor,  real discount factor can be *increasing* which imply that (real) interest rates are negative. Negative rates are indeed shown in Figure 3. Negative rates may signify an expected decline in real economic growth - which is though unlikely in the 2013 - or still a large economic uncertainty and high risk aversion. The latter scenario is a bit more likely. One possibility is that median forecasts are not too reliable,  and there is much uncertainty about future inflation and future interest rates.
![28_image_0.png](28_image_0.png)
3
![29_image_0.png](29_image_0.png)
We next fit the nominal yields using the NS model to the data. In this case,  there are many more data points than in the case of real bonds,  but the model does a good job in fitting the data,  as shown in Figure 4. Figure 5 shows the nominal discount factor Z(T),  which seems to be well behaved. Figure 6 shows the nominal yield and the forward curve (the latter was not required) We finally use the nominal yields and the real yield to compute "breakeven inflation rates",  that is,  the di!erence between the nominal and the real yield. These are shown in Figure 7. The breakeven rate range between 2% and 2.7%. These implied forecasts of inflation rates seem reasonable,  although we should always remember that the di!erence between nominal and real yields also include risk premia. Breakeven rates depend on risk premia,  as explained above. Interestingly,  from the survey of professional forecasters,  we find that the median forecast of average CPI inflation for the next 10 years is 2.3%,  a bit lower than the breakeven inflation rate at the 10-year mark,  which is around 2.67%. The di!erence could be due to a positive risk premium RP,  as discussed above. Indeed,  we have
$$R P=2.67\%-2.4\%+1/2\sigma_{\pi}^{2}=0.27\%+1/2\sigma_{\pi}^{2}$$
This positive risk premium is in contrast with the negative risk premium obtained above using the forecasts of future short-term rates.
![30_image_0.png](30_image_0.png)
![31_image_0.png](31_image_0.png)

## II. SWAP SPREAD TRADES
1. On February 17,  2009,  we had the following data: *LIBOR*(0) = 1.25%,  *Repo*(0) =
1.30%,  Thirty-year Swap Rate = 3.21% while the price and coupon of a thirty year note were P(0,  30) = 100.36 and c = 3.50%,  respectively. The (semi-annually) compounded yield to maturity of the 30 year note y is obtained from the formula
$$100.36={\frac{c}{2}}\sum_{j=1}^{60}{\frac{1}{(1+{\frac{y}{2}})^{j}}}+{\frac{1}{(1+{\frac{y}{2}})^{60}}}$$
Computation gives y = 3.49%,  very close to the constant maturity rate for the same maturity,  which was CMT=3.47%. We can define the swap spread in various ways,  but it is essentially the di!erence in coupon from a swap and the YTM on the Treasury. (Here,  this is almost the exact same as using the coupon of the treasury instead. This is because the bond is trading near par.) Thus SS = 3.21% → 3.49% = →28 basis points. Additionally,  the LIBOR-repo spread,  or LRS,  is 1.2456→ = 0.95%. In the past we typically observed a fixed rate on the swap that is larger than the treasury. In this case the issue was whether the excess was large enough to make up for the loss on the LRS given that the trade involves receiving repo and paying LIBOR. (For instance,  see Figure 8 for a feel of how the trade worked.) However,  in this situation a trader can make money on both ends of the deal by doing the opposite. Namely,
(a) Go long the 30 year bond through a repo transaction. In cash flow terms,  pay Repo and receive the treasury coupon.
(b) Enter into a fixed for floating swap in which I receive [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and pay the fixed.
The net quarterly cash flows are CF(Ti)=0.25 ↑ [Coupon → Repo(Ti→1)] + 0.25 ↑ [LIBOR(Ti→1) → Swap Rate]
where notice that we consider an "accrued" coupon to be "paid" at quarterly frequency,  for simplicity.
More precisely,  consider a trade of size 100 million. The number of T-Notes (with 100 principal) corresponding to 100 million is N = 9,  964,  191. Therefore,  adjusting for the size of the trade,  and assuming no hair cut,  the cash flow at time Ti
$$\begin{array}{r c l}{{C F(T_{i})}}&{{=}}&{{0.25\times[N\times\mathrm{coupon}-100\ m i l\times\mathrm{Swap~Rate}]}}\\ {{}}&{{}}&{{+100\ m i l\times0.25\times[\mathrm{LIBOR}(T_{i-1})-\mathrm{Repo}(T_{i-1})]}}\end{array}$$
1. Use the above cash flow equation to get that the first cash-flow realized is CF(May) ↓
305,  774.23,  (for an annualized value of 1,  223,  096.92 if rates were to hold constant.)
The first term in CF(Ti) above is always the same each quarter,  as neither the swap rate nor the coupon of the initial swap and T-note change over time. The second parenthesis is instead reset every 3 months. Still,  the trade would be profitable unless [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] dropped to where it was below the repo rate,  which is quite unlikely given the lower risk of collateralized debt. Thus,  the trade locks in the less stable profit,  the SS,  and profits on the stable fact that [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] is above repo. See Figure 8 for the historical relationship using 5 year swaps and 5-year coupon bonds.
![33_image_0.png](33_image_0.png)
Figure 9 uses daily data to illustrate the evolution of the LRS side of the trade over the following quarters (for this solution,  the data have been updated to June 2010,  for illustrative purposes). The spread drops substantially—almost half—but is still well above zero. Combined with the locked in profit on the SS side,  the trade is still generating positive cash-flow.
Given the data provided,  we only have one quarter of data after the position is put on,  so it would seem that we can only calculate one cash flow generated by the trade.
However,  we can actually compute the cash flow for August using the data given in May. The SS cash flow is fixed,  and the August LRS cash flow depends on LIBOR
and the repo rate quoted one quarter earlier—the floating part resets one quarter before payment. With updated data to June 2010,  we can follow the cash flows all the way to August 2010. Figure 10 displays the cash flows of the trade,  and Figure 11 displays the net cash flows.
1. We can also compute the value of the position. From the strategy above,  we are long
![34_image_0.png](34_image_0.png)
N T-notes,  short 100 million in the Repo market,  and short a fixed for floating swap.
The computation of the value of the long T-note (minus Repo) is straightforward. Assuming we take the repo interest paid over time,  the value of this position at reset dates is VT →*N ote* = N ↑ P(t; T) → 100 mil where P(t; T) is the value of the 30 year note.
To value the swap is slightly more cumbersome,  as we need to compute the value of the swap as the swap rate change over time. Recall that the value of the swap at reset date is
## VSWAP = PF IXED(0; T) → PF L(0; T)

where P*F ixed*(0; T) is the value of the fixed rate bond implicit in the fixed part of the swap. In particular,  the coupon on this component equals the swap rate at initiation,  namely,  c*swap* = 3.21%. Therefore,  at every reset date Ti,  let ni be number of *remaining* payments in the swap. We have
$$P_{F i x e d}(T_{i};T)=\frac{c^{s w a p}}{4}\sum_{j=1}^{n_{i}}Z^{\mathrm{LIBOR}}(T_{i};T_{j})+Z^{\mathrm{LIBOR}}(T_{i};T_{n_{i}})$$
If we knew the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curve Z*LIBOR*(Ti; Tj),  we are done. We can use current swap rates to compute the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curve every Ti. Since we only have a sample of swap
![35_image_0.png](35_image_0.png)
$$\begin{array}{r c l}{{Z^{\mathrm{LIBOR}}(T_{i};T_{i+1})}}&{{=}}&{{\frac{1}{1+L I B O R(T_{i})\times0.25}}}\\ {{}}&{{}}&{{}}\\ {{Z^{\mathrm{LIBOR}}(T_{i};T_{j})}}&{{=}}&{{\frac{1-0.25\times c(T_{i};T_{j})\sum_{k=1}^{j-1}Z^{\mathrm{LIBOR}}(T_{i};T_{i+k})}{1+c(T_{i};T_{j})\times0.25}}}\end{array}\qquad\qquad(1)$$
From the swap curve,  we can compute the value of the fixed leg of the swap.
The floating leg of the swap is much simpler,  as PF l(0; T) = 1. The value of the swap follows. Figure 12 plots the value of the swap and the Treasury (minus Repo) over time. Both start at zero by construction,  and as rates change,  so do the value of both quantities. In particular,  the price of the T-note decreased,  and so did the treasury coupon minus repo position. This was partly o!set by the increase in value in the swap trade. However,  Figure 13 shows that the T-note price dropped by more than the increase in the swap value,  generating a drop in the value of the overall position. Thus,  while the cash flows are positive,  there is a capital loss if the position is unwound after a
![36_image_0.png](36_image_0.png)

## 4. ARBITRAGE OPPORTUNITY?

It is important to consider whether the above trade is an arbitrage opportunity. As mentioned earlier,  the cash flows are comprised of two parts,  the SS and LRS. The former is fixed every period,  and we showed that by taking the short end it will be a positive inflow. The LRS varies with changes in [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and the repo,  but we strongly expect [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] to always be larger as securitized loans,  (the repo,  ) are less risky. Thus,  while the amount gained from the LRS varies it is incredibly unlikely it will become negative,  especially so negative as to outweigh the positive flow from the SS position. Thus,  by holding the position to maturity one realizes positive cash flows for 30 years and does not need to worry about possible losses from unwinding early. In this view,  the above trade is an arbitrage. However,  this conclusion hinges on the ability to hold the position to maturity. Unwinding the position early could induce significant losses,  as demonstrated above in Figure 13,  due to the fact that the value of the position fluctuates up until maturity where it is known. In fact,  the fluctuating
![37_image_0.png](37_image_0.png)
![38_image_0.png](38_image_0.png)

# BUS 35130 SPRING 2024 SOLUTION TO HOMEWORK 5

John Heaton April 22,  2024

## PART I. USING BLACK'S FORMULA FOR CAPS,  FLOORS,  AND SWAPTIONS
1. (CP) Use the data in the attached Bloomberg screen to compute
The dollar value of a two-year Cap; The dollar value of a 1-year swaption to enter into a 5-year swap.
1. (PP) In the exercise above,  make sure to illustrate the option-pricing formulas used for (a) the first caplet in the cap (i.e. the one with 6-months to maturity); and (b) the swaption. Show your work.
We first interpolate the available Swap data to fill in the curve for the quarterly maturities. The zero yield on the Zero with maturity of 0.25 is given by the first interpolated swap rate:
$$Z(0,  0.25)={\frac{1}{1+c(0.25)\times0.25}}$$
Beyond that date we use the Bootstrap method:
$=\;\;\dfrac{1-c(0.5)\times0.25\times Z(0.25)}{1+c(0.5)\times0.25}$ $\vdots$ $\quad1-c(T)\Delta\sum_{t=0.25}^{T-0.25}Z(t)$.
$$\begin{array}{r l}{Z(0.5)}&{{}=}\\ {\ }&{{}}\\ {\ }&{{}\vdots}\\ {Z(T)}&{{}=}\end{array}$$
… …
![39_image_0.png](39_image_0.png)
Clearly,  there are important issues here
The interpolation is only approximate. We normally have far more data to do this.
1
We have anchored the swap curve with the one-month [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curve. LIBOR
is for uncollateralized borrowing - and thus is risky - while swaps now are fully collateralized,  and thus there is less risk.
1. Once we have the zero-coupon curve,  we can compute quarterly forward rates from the forward discount F(0,  Ti,  Ti+1) = Z(0,  Ti)
Z(0,  Ti+1)
1. From the forward rates,  we employ the formula in the teaching notes to compute the caplets. The following table shows the results for the interpolations the 1st and 2nd caplet and the swaption,  and then the next table shows the reults for the caplets:

| CAP        | CAP   | SWAPTION    |         |          |         |          |
|------------|-------|-------------|---------|----------|---------|----------|
| LIBOR/SWAP | Fwd   | Fwd         | Fwd     |          |         |          |
| i          | Ti    | Interpolate | Z(0,  Ti) | Discount | Rate    | Discount |
| 1          | 0.25  | 0.003212    | 0.99920 |          |         |          |
| 2          | 0.50  | 0.003428    | 0.99829 | 0.99909  | 0.00364 |          |
| 3          | 0.75  | 0.003569    | 0.99733 | 0.99904  | 0.00385 |          |
| 4          | 1.00  | 0.003620    | 0.99639 | 0.99906  | 0.00377 |          |
| 5          | 1.25  | 0.003558    | 0.99556 | 0.99917  | 0.00331 | 0.99917  |
| 6          | 1.50  | 0.003422    | 0.99488 | 0.99932  | 0.00274 | 0.99849  |
| 7          | 1.75  | 0.003285    | 0.99427 | 0.99939  | 0.00246 | 0.99787  |
| 8          | 2.00  | 0.003220    | 0.99358 | 0.99931  | 0.00276 | 0.99719  |
| 9          | 2.25  | 0.003216    | 0.99279 | 0.99921  | 0.00318 | 0.99639  |
| 10         | 2.50  | 0.003213    | 0.99201 | 0.99920  | 0.00318 | 0.99560  |
| 11         | 2.75  | 0.003211    | 0.99121 | 0.99920  | 0.00319 | 0.99481  |
| 12         | 3.00  | 0.003210    | 0.99042 | 0.99920  | 0.00320 | 0.99401  |
| 13         | 3.25  | 0.003246    | 0.98951 | 0.99908  | 0.00369 | 0.99310  |
| 14         | 3.50  | 0.003337    | 0.98839 | 0.99887  | 0.00452 | 0.99197  |
| 15         | 3.75  | 0.003454    | 0.98713 | 0.99873  | 0.00511 | 0.99071  |
| 16         | 4.00  | 0.003570    | 0.98582 | 0.99867  | 0.00532 | 0.98939  |
| 17         | 4.25  | 0.003685    | 0.98446 | 0.99862  | 0.00554 | 0.98803  |
| 18         | 4.50  | 0.003813    | 0.98298 | 0.99850  | 0.00601 | 0.98654  |
| 19         | 4.75  | 0.003947    | 0.98141 | 0.99841  | 0.00639 | 0.98497  |
| 20         | 5.00  | 0.004080    | 0.97979 | 0.99834  | 0.00664 | 0.98334  |
| 21         | 5.25  | 0.004211    | 0.97811 | 0.99829  | 0.00686 | 0.98166  |
| 22         | 5.50  | 0.004342    | 0.97637 | 0.99822  | 0.00715 | 0.97991  |
| 23         | 5.75  | 0.004476    | 0.97455 | 0.99814  | 0.00745 | 0.97808  |
| 24         | 6.00  | 0.004610    | 0.97267 | 0.99807  | 0.00775 | 0.97619  |

| 1-year Cap                            | 2-year Cap                           |          |                     |             |          |                     |
|---------------------------------------|--------------------------------------|----------|---------------------|-------------|----------|---------------------|
| Strike Rate = 0.0.00362; Vol = 1.0679 | Strike Rate = 0.00322; Vol = 1.28170 |          |                     |             |          |                     |
| Ti                                    | f(Ti→1,   Ti)                          | Z(0,   Ti) | Caplets(Ti) (x 100) | f(Ti→1,   Ti) | Z(0,   Ti) | Caplets(Ti) (x 100) |
| 0.25 0.50                             | 0.003644                             | 0.99829  | 0.01939             | 0.00364     | 0.99829  | 0.02721             |
| 0.75                                  | 0.003853                             | 0.99733  | 0.03040             | 0.00385     | 0.99733  | 0.03927             |
| 1.00                                  | 0.003772                             | 0.99639  | 0.03472             | 0.00377     | 0.99639  | 0.04389             |
| 1.25                                  | 0.00331                              | 0.99556  | 0.04003             |             |          |                     |
| 1.50                                  | 0.00274                              | 0.99488  | 0.03326             |             |          |                     |
| 1.75                                  | 0.00246                              | 0.99427  | 0.03108             |             |          |                     |
| 2.00                                  | 0.00276                              | 0.99358  | 0.03929             |             |          |                     |
| Total                                 | 0.08451                              | Total    | 0.25403             |             |          |
|

1. The swaption uses a similar strategy. We have to compute the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curve up to year 5 in order to compute the discounts Z(0,   Ti),   as described in previous point.
1. From the teaching notes,   we have to compute the quantity
$$A=\Delta\sum_{i=5}^{24}Z(0,  T_{i})$$
and then use Black's formula as in the teaching notes. The next table shows the calculations

| Strike Rate (5-year swap rate)   | 0.00408   |
|----------------------------------|-----------|
| Forward 5-year Swap Rate         | 0.00481   |
| Swaption Volatility              | 0.9912    |
| Swaption Maturity                | 1         |
| d1                               | 0.6617    |
| d2                               | -0.3295   |
| A                                | 4.9315    |
| Swaption                         | 0.01023   |

## PART II. INTEREST RATE TREES
1. (PP) Consider the following interest rate tree,   where each time interval is 1-year (that is,  ! = 1).
![42_image_0.png](42_image_0.png)
The probability of an "up" movement can either be p = 40% or p = 70%
You also know the current value of a 2-period zero coupon bond is Z0(2) = 0.94
(a) Find the risk neutral probability ω↑ (see TN4,   page 238) and confirm you get the same price for the option in point (b). What is the market price of risk under ω↑?
First,   compute the tree for the 2-period bond i = 0 i = 1 i = 2
![43_image_0.png](43_image_0.png)
The risk neutral probability can be readily computed from
$$\tau=\frac{Z_{0}(2)/Z_{0}(1)-Z_{1d}(2)}{Z_{1u}(2)-Z_{1d}(2)}$$
Z1u(2) ↑ Z1d(2) = 0.96862 ↑ 0.9802 0.96079 ↑ 0.9802 = 0.59646
(b) You have to compute the value of a one-year call option on the interest rate r1 at the strike rate rK = 3% and notional N = 1000,   that is,   with payo"f payo"1u = 1000 ↓ max(r1u ↑ rK,   0) in the "up" node; and payo"1d = 1000 ↓ max(r1d ↑ rK,   0) in the "down" node Does it matter which probability p is the true one? Compute the value of the option under both probabilities (p = 40% and p = 70%) using the pricing formula that involves a market price of risk ε (see TN4,   page 231). Show your work. Comment on the results.
We have to compute the value using the formula
 $ax(x_1,  \dots,  x_N)$ $ax(x_1,  \dots,  x_N)$.
V = Z0(1){E↑[payo"1]}
So,   we have
$$\mathrm{D}_{4}$$
payo"1u = 1000 ↓ max(r1u ↑ rK,   0) = 1000 ↓ max(↑,   0) = 10 payo"1d = 1000 ↓ max(r1d ↑ rK,   0) = 1000 ↓ max(↑,   0) = 0 In this case,  the pricing formula is V = Z0(1)E↑[payo"1] = Z0(1) → [0.59646 → 10] = 0.97045 → 59646 = 5.79
(c) The probability to go up the tree does not show up in the formula,  and therefore it does not matter. Intuitively,  the risk neutral methodology is only a tool to price securities by no arbitrage. The risk from the strategy (discussed in the next point) has been eliminated by the replication strategy. Therefore,  the true probability does not enter the calculation anymore.
(d) Find the portfolio of securities that replicates the payo" of the option in point
(b). What is the value of this portfolio at time 0? How does it compare with the value of the option computed in point (b)? Show your work and comment.
The portfolio in general is
$$P_{0}=N_{1}Z_{0}(2)+N_{2}Z_{0}(1)$$
The position in long-term bonds can be computed from its "delta"
$$N_{1}=\Delta={\frac{V_{1u}-V_{1d}}{Z_{1u}(2)-Z_{1d}(2)}}=-515.21868$$
The value of N2 can be computed as N2 = \#1d = payo"1d ↑! → Zid(2) = 0 ↑ (↑515.21868) → Z1d(2) = 505.0166666 The value of the portfolio is
$$P_{0}=N_{1}Z_{0}(2)+N_{2}Z_{0}(1)=5.79$$
as before. To check,  note that the value of the portfolio tomorrow is indeed
$$P_{1u}=N_{1}Z_{1u}(2)+N_{2}=10$$
$$P_{1d}=N_{1}Z_{1d}(2)+N_{2}=0$$
It replicates the value of the option.
(e) Assume the risk neutral probability ω↑ computed in point (c) is constant throughout the binomial tree. Use the risk neutral methodology to compute 1. the value of a 3-year zero-coupon bond
The binomial tree is
$\dfrac{3}{1}$ 1.
![45_image_1.png](45_image_1.png)
$$\frac{3}{1}$$
 $\begin{array}{l}1\\ 1\\ 1\end{array}$ 1.
Zij (3) = e→rij (ω↑Zi+1,  j + (1 ↑ ω↑)Zi+1,  j+1)
1. the value of a 3-year coupon bond with annual coupon equal to 3%.
 $\begin{array}{c|ccc}\text{The binomial tree is}\\ j\backslash i&0&1&2\\ \hline0&0.993472&0.977852&0.979766\\ 1&1.017165&0.999559\\ 2&1.019751\\ 3&\end{array}$ At any node $i,  j$,  we have
$\mathbf{l}$ 1.
Pij (3) = e→rij (ω↑Pi+1,  j (3) + (1 ↑ ω↑)Pi+1,  j+1(3) +)
1. We finally compute the replicating portfolio at time i = 0. We have to find N0 in the 3-period bond and N1 in the 1-period bond to replicate the coupon bond. First,  recall the tree for a 3-period zero-coupon bond is the following
![45_image_2.png](45_image_2.png)
We want to choose N0 and N1 so that the portfolio P0 = N1Z0(3)+N2Z0(1)
is such that
$$\begin{array}{l l l}{{P_{1,  u}}}&{{=}}&{{P_{1,  u}^{C}(3)+c}}\\ {{}}&{{}}&{{}}\\ {{P_{1,  d}}}&{{=}}&{{P_{1,  d}^{C}(3)+c}}\end{array}$$
7
![45_image_0.png](45_image_0.png)
where P Cij (3) is the price of the coupon bond. Note that we inserted also the coupon c. Substitute the expression for Pij
$$\begin{array}{r c l}{{N_{1}Z_{1,  u}(3)+N_{2}}}&{{=}}&{{P_{1,  u}^{C}(3)+c}}\\ {{N_{1}Z_{1,  d}(3)+N_{2}}}&{{=}}&{{P_{1,  d}^{C}(3)+c}}\end{array}$$
where we used the fact that Z1,  u(1) = Z1,  d(1) = 1. Solving the system,  we obtain
$$\begin{array}{r c l}{{N_{1}}}&{{=}}&{{\frac{P_{1,  u}^{C}(3)-P_{1,  d}^{C}(3)}{Z_{1,  u}(3)-Z_{1,  u}(3)}}}\\ {{N_{2}}}&{{=}}&{{P_{1,  u}^{C}(3)+c-N_{0}Z_{1,  u}(3)}}\end{array}$$
which is the same value we obtained in TN 4 (page 9,  where N2 = \#1u =
(C1u ↑!Z1u(2))). Substitute to find
(1) $\binom{2}{}$ (2) …
$$\begin{array}{r c l}{{N_{1}}}&{{=}}&{{1.045485}}\\ {{N_{2}}}&{{=}}&{{0.044556}}\end{array}$$
$$\begin{array}{c}{{(3)}}\\ {{(4)}}\end{array}$$
Its value today is then P0 = N1Z0(3) + N2Z0(1) = 0.993472 which is the same as the value of the 3-period coupon bond. The replicating portfolio replicates,  we we have the tree i = 0 i = 1
$$\boxed{\boxed{P_{0}=0.993472}}$$
![46_image_1.png](46_image_1.png)
| P1,  u = 1.007852 P1,  d = 1.047165   |
|-----------------------------------|
![46_image_0.png](46_image_0.png)
Note that the portfolio replicates the full payo" of the coupon bond at time i = 1,  *including the coupon*.
Fixed Income Asset Pricing Bus 35130 Spring 2024 John Heaton
## SOLUTION TO HOMEWORK 6 PART I. PRICING FREDDIE MAC 6% CALLABLE BOND

The prospectus of Freddie Mac 6%,  20-year callable bond,  issued on June 7,  2007,  shows that the bond becomes callable in June 2011,  and it can only be called on coupon dates.
We are going to follow the same steps as in the note,  but now on a much bigger tree. We can concentrate on a tree with 40 steps,  that is,  20-year binomial tree with semi-annual increments! = 0.5.
We begin with fitting the model to the current interest rates. We proceed as follows:

1. First,  we use the data in "HW4 Data *Bonds.xls"* and extract the discount curve Z(0,  T) from the Treasuries using Nelson-Siegel model,  as we did in HW4. Figures 1 through 3 show the resulting fit.
![47_image_0.png](47_image_0.png)
![48_image_0.png](48_image_0.png)
![48_image_1.png](48_image_1.png)
1. Next,  we build the Ho-Lee tree,  given by
$$\sigma\times{\sqrt{\Delta}}\times\epsilon_{i+1}$$
ri+1,  j = ri,  j + ω(i) →! + ε → ↑! → ϑi+1 where ε is the volatility of interest rates,  ω(i) are chosen to fit the term structure of interest rates exactly,  and
$$\epsilon(i)=\left\{\begin{array}{l l}{{+1}}&{{\mathrm{with~probability}}}\\ {{-1}}&{{\mathrm{with~probability}}}\end{array}\right.\;\;1/2$$
We need to estimate ε. We use the data provided,  which are monthly. If we use the formula *St.Dev.(dr*t) where drt = rt+1 ↓ rt is the change in interest rate,  we obtain a volatility in *monthly unit*. Because ε needs to be annualized,  we choose
$$\sigma=S t.D e v.(d r_{t}){\sqrt{12}}=1.60\%$$
Using the routine provided,  we obtain the following tree (first 10 steps)
![50_image_0.png](50_image_0.png)

| 0   | 1      | 2      | 3      | 4      | 5      | 6       | 7       | 8       | 9       |         |
|-----|--------|--------|--------|--------|--------|---------|---------|---------|---------|---------|
| 0   | 5.0684 | 6.0195 | 7.1238 | 8.303  | 9.5166 | 10.7459 | 11.9782 | 13.2075 | 14.4367 | 15.6597 |
| 1   | 0      | 3.761  | 4.8653 | 6.0445 | 7.2581 | 8.4874  | 9.7197  | 10.949  | 12.1782 | 13.4012 |
| 2   | 0      | 0      | 2.6068 | 3.786  | 4.9997 | 6.2289  | 7.4613  | 8.6905  | 9.9197  | 11.1427 |
| 3   | 0      | 0      | 0      | 1.5276 | 2.7412 | 3.9704  | 5.2028  | 6.432   | 7.6613  | 8.8843  |
| 4   | 0      | 0      | 0      | 0      | 0.4827 | 1.7119  | 2.9443  | 4.1735  | 5.4028  | 6.6258  |
| 5   | 0      | 0      | 0      | 0      | 0      | -0.5466 | 0.6858  | 1.9151  | 3.1443  | 4.3673  |
| 6   | 0      | 0      | 0      | 0      | 0      | 0       | -1.5727 | -0.3434 | 0.8858  | 2.1088  |
| 7   | 0      | 0      | 0      | 0      | 0      | 0       | 0       | -2.6019 | -1.3727 | -0.1497 |
| 8   | 0      | 0      | 0      | 0      | 0      | 0       | 0       | 0       | -3.6312 | -2.4082 |
| 9   | 0      | 0      | 0      | 0      | 0      | 0       | 0       | 0       | 0       | -4.6667 |

![50_image_1.png](50_image_1.png)
Clearly,  there is no di"erence between the inputs used and the outcome of the tree,  by construction.
What does ω(i) look like? Next figure shows ω(i) together with the following
![51_image_0.png](51_image_0.png)
![51_image_1.png](51_image_1.png)
Interestingly,  the two curves are very close to each other. It turns out that as the time steps decreases to 0 we obtain exactly the same value. That is,  as! ↓↔ 0,  we indeed obtain
$$\theta(t)={\frac{\partial f(0,  t)}{\partial t}}+\sigma^{2}t$$
where f(0,  t) is the instantaneous forward rate,  namely,  the forward rate at 0 for an investment between t and t + dt.

1. We finally come to price the Freddie Mac Callable bond. We follow the instructions as in the assignment,  and proceed as follows:
Obtain the price of the non-callable bond,  using the algorithm
PP(:,  :)=zeros(n,  n); % initialize matrix for security PP(1:n,  n)=100; % set final payo" of bond i equal to 1 for all nodes for j=n-1:-1:1 % move backward on the tree,  from i-1,  back to 1 PP(1:j,  j)=exp(-ImTree(1:j,  j)*dt).*(0.5*PP(1:j,  j+1)+0.5*PP(2:j+1,  j+1,  i)+3*dt);
end We obtain the tree (first 10 steps)

| 0   | 1        | 2       | 3        | 4        | 5        | 6        | 7        | 8        | 9        |          |
|-----|----------|---------|----------|----------|----------|----------|----------|----------|----------|----------|
| 0   | 108.5546 | 93.8025 | 81.8832  | 72.1938  | 64.2522  | 57.6845  | 52.2033  | 47.588   | 43.6682  | 40.3136  |
| 1   | 0        | 122.879 | 105.454  | 91.511   | 80.2557  | 71.0825  | 63.5339  | 57.2627  | 52.0051  | 47.5602  |
| 2   | 0        | 0       | 138.9691 | 118.5906 | 102.3822 | 89.3609  | 78.794   | 70.1328  | 62.9649  | 56.98    |
| 3   | 0        | 0       | 0        | 156.994  | 133.3317 | 114.5868 | 99.5816  | 87.4452  | 77.53    | 69.3533  |
| 4   | 0        | 0       | 0        | 0        | 177.0637 | 149.7566 | 128.1869 | 110.967  | 97.0764  | 85.7617  |
| 5   | 0        | 0       | 0        | 0        | 0        | 199.2266 | 167.901  | 143.2089 | 123.5376 | 107.7075 |
| 6   | 0        | 0       | 0        | 0        | 0        | 0        | 223.4648 | 187.7465 | 159.6359 | 137.2828 |
| 7   | 0        | 0       | 0        | 0        | 0        | 0        | 0        | 249.6826 | 209.2128 | 177.4063 |
| 8   | 0        | 0       | 0        | 0        | 0        | 0        | 0        | 0        | 277.6979 | 232.1573 |
| 9   | 0        | 0       | 0        | 0        | 0        | 0        | 0        | 0        | 0        | 307.2459 |

Obtain the price of the call option written on the non-callable bond. In this case we define *iF CT* the first time when the option can be exercised. And then we use the algorithm
Call(:,  :)=zeros(n,  n); % initialize matrix for security Call(1:n,  n)=0; % set final payo" of bond i equal to 0 for all nodes for j=n-1:-1:1 % move backward on the tree,  from i-1,  back to 1 if j>=*iFCT*
Call(1:j,  j)=max(exp(-ImTree(1:j,  j)*dt).*(0.5*Call(1:j,  j+1)+0.5*Call(2:j+1,  j+1,  i)),  PP(i:j,  j)

- 100);
else Call(1:j,  j)=exp(-ImTree(1:j,  j)*dt).*(0.5*Call(1:j,  j+1)+0.5*Call(2:j+1,  j+1,  i));
end end

| Call option tree 01   | 2       | 3       | 4       | 5       | 6       | 7       | 8        | 9        |          |          |
|-----------------------|---------|---------|---------|---------|---------|---------|----------|----------|----------|----------|
| 0                     | 17.0245 | 10.0772 | 5.6257  | 2.9688  | 1.4963  | 0.7219  | 0.3319   | 0.1444   | 0.0590   | 0.0224   |
| 1                     | 0       | 24.8458 | 15.1445 | 8.6906  | 4.6931  | 2.4165  | 1.1917   | 0.5604   | 0.2495   | 0.1044   |
| 2                     | 0       | 0       | 35.4904 | 22.3442 | 13.2214 | 7.3166  | 3.8508   | 1.9417   | 0.9342   | 0.4260   |
| 3                     | 0       | 0       | 0       | 49.5678 | 32.3211 | 19.7955 | 11.2453  | 6.0526   | 3.1216   | 1.5374   |
| 4                     | 0       | 0       | 0       | 0       | 67.5744 | 45.7388 | 29.1396  | 17.0307  | 9.3793   | 4.9494   |
| 5                     | 0       | 0       | 0       | 0       | 0       | 89.7366 | 63.1244  | 42.1129  | 25.4003  | 14.3228  |
| 6                     | 0       | 0       | 0       | 0       | 0       | 0       | 115.8591 | 84.5694  | 59.6359  | 37.2828  |
| 7                     | 0       | 0       | 0       | 0       | 0       | 0       | 0        | 145.3338 | 109.2128 | 77.4063  |
| 8                     | 0       | 0       | 0       | 0       | 0       | 0       | 0        | 0        | 177.6979 | 132.1573 |
| 9                     | 0       | 0       | 0       | 0       | 0       | 0       | 0        | 0        | 0        | 207.2459 |

7

| Callable Bond Tree 01   | 2       | 3       | 4        | 5        | 6        | 7        | 8        | 9        |           |          |
|-------------------------|---------|---------|----------|----------|----------|----------|----------|----------|-----------|----------|
| 0                       | 91.5301 | 83.7253 | 76.2575  | 69.2249  | 62.7560  | 56.9625  | 51.8714  | 47.4436  | 43.6092   | 40.2911  |
| 1                       | 0       | 98.0332 | 90.3096  | 82.8205  | 75.5626  | 68.6660  | 62.3422  | 56.7024  | 51.7555   | 47.4558  |
| 2                       | 0       | 0       | 103.4788 | 96.2464  | 89.1608  | 82.0444  | 74.9432  | 68.1912  | 62.0307 5 | 6.5540   |
| 3                       | 0       | 0       | 0        | 107.4263 | 101.0105 | 94.7912  | 88.3364  | 81.3926  | 74.4084   | 67.8159  |
| 4                       | 0       | 0       | 0        | 0        | 109.4893 | 104.0178 | 99.0473  | 93.9364  | 87.6971   | 80.8122  |
| 5                       | 0       | 0       | 0        | 0        | 0        | 109.4900 | 104.7766 | 101.0960 | 98.1373   | 93.3847  |
| 6                       | 0       | 0       | 0        | 0        | 0        | 0        | 107.6057 | 103.1770 | 100.0000  | 100.0000 |
| 7                       | 0       | 0       | 0        | 0        | 0        | 0        | 0        | 104.3487 | 100.0000  | 100.0000 |
| 8                       | 0       | 0       | 0        | 0        | 0        | 0        | 0        | 0        | 100.0000  | 100.0000 |
| 9                       | 0       | 0       | 0        | 0        | 0        | 0        | 0        | 0        | 0         | 100.0000 |

Note that the value of the bond is P C0 (40) = $91.5301,   which is well below 100,   the likely issue price. The value of the non-callable bond does not depend on the tree used,   because the tree exactly fits the zero coupon bonds Z(T) and the non-callable bond can be valued directly from Z(T). Thus,   the low value of the callable bond must come from an excessive value of the call option *Call*0. That is,   the volatility ε = 1.60% is too high. The likely reason is that the data set also includes the extremely high volatility of interest rates in the 1980s. If we restrict the data to the last 10 years in the sample (120 months). The volatility is much smaller,   and equal to ε = 0.67%. In this case,   indeed,   we obtain P C0 = $99.45,  which is very close to par.

1. Figure 6 plots the price of the non-callable and of the callable security against interest rates at call time,  as well as 1,  2,  3 semesters before.
The non-callable bond shows the usual pattern,  with positive convexity. Instead,  the callable security shows a negatively convex pattern with respect to interest rates. The reason is that as interest rates decline,  it becomes more and more likely that the bond will be called at par. Hence,  the value of the bond reflect this loss in future upside potential of the callable bond,  and thus results in a negatively convex pattern. Indeed,  in the first top left panel,  we see that at first call date,  if interest rates are low enough,  then the value of the bond exactly equals 100,  as
the bond gets called.
1. We finally get to compute the duration and convexity of callable and non-callable bond at time 0. This exercise required a bit of thinking,  but the idea is to use the
![55_image_0.png](55_image_0.png)
! = P C1u ↓ P C1d
$$\frac{P_{1u}^{C}-P_{1d}^{C}}{r_{1u}-r_{1d}}$$
and the dollar convexity is the change in "Delta" (not of duration!) due to changes in the interest rate
C$ =!1u ↓!1d
We then obtain $\,  $.
$$\frac{\Delta_{1u}-\Delta_{1d}}{r_{1u}-r_{1d}}$$
$$\Delta=$$
$$C^{\$$}=$$
$$D=-{\frac{\Delta}{P_{0}^{C}}}$$
D = ↓!P C0and C = C$
$$\mathrm{~and~}\quad C={\frac{C^{\$$}}{P_{0}^{C}}}$$
By applying these formulas to the two types of bonds,   we obtain
$$D^{N C}=11.8598;\quad D^{C a l l a b l e}=6.9214$$
and
$$C^{N C}=179.59;$$
CNC = 179.59; C*Callable* = ↓18.9098
$$C^{C a l l a b l e}=-18.9098$$
The non-callable security is strongly positively convex,  while the callable security is mildly positive convex. The reason is that at issuance,  the call time is still pretty far away. For instance,  if we were to consider the first-call time to be just one year from now,  and redo the computations,  we would find C*Callable* = ↓86.60.
1. Ho Lee versus Simple BDT. Redo all of the points above for the Simple BDT
model. Switching to logarithm produces a di"erent tree for interest rates. The di"erence from before is that ε needs to use log interest rates
## Ε = ST.DEV.(D LOG(RT))↑12

where *d log(r*t) = log(rt+1) ↓ *log(r*t). The non-callable bond of course does not depend on the tree,  as discussed earlier,  as the tree fits the current term structure of interest rates. Instead,  the callable bond becomes more expensive,  at 95.6329.
That is,  using the same inputs,  but just a di"erent model,  we obtain a higher price. The value of the option depends on the distribution of future interest rates,  and the two models produced di"erent statistical distributions in the two cases.

## FIXED INCOME ASSET PRICING
# BUS 35130 SPRING 2024 JOHN HEATON

Solution to Homework 7 Relative Value Trades and Mortgage Backed Securities

## PART I. RELATIVE VALUE TRADE ON TREES

The binomial tree of the coupon bond with coupon rate c = 3 that we need to replicate
(the "theoretical" price) is

| 3-year,   3% coupon bond Pij   |          |          |       |
|------------------------------|----------|----------|-------|
| t = 0                        | t = 1    | t = 2    | t = 3 |
| 99.34716                     | 97.7852  | 97.97663 | 100   |
| 101.7165                     | 99.95589 | 100      |       |
| 101.9751                     | 100 100  |          |       |

As mentioned,  the 3-year zero coupon bond is fairly priced and it is on the following tree

| 3-year,   zero-coupon bond Zij (3)   |          |          |       |
|------------------------------------|----------|----------|-------|
| t = 0                              | t = 1    | t = 2    | t = 3 |
| 90.88915                           | 92.13868 | 95.12294 | 100   |
| 95.89893                           | 97.04455 | 100      |       |
| 99.00498                           | 100 100  |          |       |

Finally,  we need the interest rate tree,  which is given by

| interest rate tree   |           |       |
|----------------------|-----------|-------|
| t = 0                | t = 1     | t = 2 |
| 0.03                 | 0.04      | 0.05  |
| 0.02                 | 0.03 0.01 |       |

We replicate the coupon-bond using the zero-coupon bond. At time 0,  we have
!0 = ((P1u + c) → (P1d + *c))/*(Z1u(3) → Z1d(3)) = 1.045485 The position in "cash" (borrowing) is (we use "up" but we could use down as well,  given that it gives the same result)
$$C_{0}=e^{-r_{0}}(-P_{1u}-c+\Delta_{0}Z_{1u}(3))=-4.323913$$
Note that we take into account the fact that we have to pay the coupon tomorrow ("c")
in the present value.
The value of the replicating portfolio today is
$=\;4$.
"0 =!0Z0(3) → C0 = 99.34716 which is equal to the "theoretical" value of the coupon bond. So,  we sell the mispriced bond at 100,  and purchase the portfolio "0 for 99.34718,  and make a profit today.

| The next table shows the trading strategy going forward: t=0 t=1 (start) t=1 (end)   | t=2        |                       |           |                                  |          |
|--------------------------------------------------------------------------------------|------------|-----------------------|-----------|----------------------------------|----------|
|!1,  u =                                                                               | 1.03       | "cum 2,  uu =           | 100.9766  |                                  |          |
|!0 =                                                                                 | 1.045485   | C1,  u =                | -2.882368 | "ex 2,  uu =                       | 97.97663 |
| C0 =                                                                                 | -4.323913  | "cum 1,  u =            | 100.7852  | "1,  u =                           | 97.7852  |
| "0 =                                                                                 | 99.34716   | "ex 1,  u =             | 97.7852   | "cum 2,  ud = "cum 2,  du = 102.9559 |          |
|!1,  d =                                                                               | 1.03       | "ex 2,  ud = "ex 2,  du = | 99.95589  |                                  |          |
| C1,  d =                                                                               | - 2.940596 |                       |           |                                  |          |
| "cum 1,  d =                                                                           | 104.7165   | "1,  d =                | 101.7165  |                                  |          |
| "ex 1,  d =                                                                            | 101.7165   | "cum 2,  dd =           | 104.9751  |                                  |          |
| "ex 2,  dd =                                                                           | 101.9751   |                       |           |                                  |          |

In particular,  we divide time t = 1 in two periods. The start of the period shows the value of the portfolio designed at time 0 as the result of an up or down movement in interest rate. The start of the period includes the payment of the coupon c = 3. As can be seen,  the ex-coupon price is indeed equal to the theoretical value in the first binomial tree.
The end of the period included the rebalancing,  that is,  the new position in the zero coupon bond,  e.g.!1u = ((P2uu + c) → (P2ud + *c))/*(Z2uu(3) → Z2ud(3)) = 1.03,  the new position in cash,  e.g. C1u = e→r1u (→P2uu → c +!1uZ2uu(3)) = →2.882368,  and the check that the new portfolio after rebalancing has the same value of the old portfolio (as it has). This means that the strategy is self financing. (This is equivalent to noticing that C1u = C0er0 + (!1u →!0)Z1u(3) + c = →2.882368)
The other periods are similar. We stop at time t = 2 as clearly the last! is always zero,  as the bonds converge to 100 in the last period. Therefore,  the position in cash in the last period must be equal to the present value of 103 one period later,  as in fact it is. For instance,  "2,  uu = 97.97663 = e→r2uu. Hence,  simply investing the last value of the portfolio at the risk free rate provides the last cash flow of the bond we want to replicate.

## PART II. INTEREST RATE TREES
1. (PP) Consider the interest rate tree examined in HW5,  reported below. Recall that each time interval is 1-year (that is,  ! = 1).
![59_image_0.png](59_image_0.png)
The probability of an "up" movement is p = 40%,  and the risk neutral probability ω↑ is in the solution to HW5 (or recompute it for this homework). You also know the current value of a 2-period zero coupon bond is Z0(2) = 0.94.
(a) Compute the value of a 3% Pass-Through MBS with maturity i = 3. The underlying pool has a coupon rate of rm = 3.469%,  principal value N = 100,  and maturity i = 3. Follow the steps in TN 5 (but recall the risk neutral probability is not 0.5).
The value of the coupon is
$$C={\frac{100}{\sum_{i=1}^{3}(1+r^{m})^{i}}}=35.67228$$
$\mathbf{\hat{j}}$

| year        | Principal   | Interest   | Principal   |
|-------------|-------------|------------|-------------|
| Outstanding | Payment     | Payment    |             |
| 0           | 100         | 3.469      | 32.20328    |
| 1           | 67.79672    | 2.351868   | 33.32042    |
| 2           | 34.4763     | 1.195983   | 34.4763     |
| 3           | 0           |            |             |

Therefore,  the principal outstanding,  interest payments,  and principal payments are as given in the next table We next compute the non-callable tree,  whose entries are the present values of future coupons C. The risk neutral probability,  recall,  is ω↑ =. We obtain

| Principal Outstanding   | 100               | 67.79672   | 34.4763   |
|-------------------------|-------------------|------------|-----------|
| Non Callable Tree Vij   |                   |            |           |
| time i                  | 0                 | 1          | 2         |
| 100.5722                | 67.14152          | 33.93253   |           |
| 69.17526                | 34.61801 35.31734 |            |           |

We can compute the call options by comparing the value from waiting CW ait ij = e→rij!t(ω↑Ci+1,  j + (1 → ω↑)Ci+1,  j+1) and the value from exercising CEx ij = Vij→OPi where Vij is the non-callable tree,  and OPi is the outstanding principal (which depends only on i).

| Call option   |                   |    |
|---------------|-------------------|----|
| 0.57204       | 0.05498           | 0  |
| 1.378546      | 0.141708 0.841038 |    |

The value of the mortgage is indeed close to 100: V0→C0 = 100.0002. Exercise occurs at the following nodes,  indicated by"1":
| Exercise Times 00 0 1 1 1   |

|-----------------------------|
We can finally compute the value of a Pass Through Security with interest rate r = 3%.

| time i                | 0               | 1        | 2        | 3   |
|-----------------------|-----------------|----------|----------|-----|
| Outstanding Principal | 100             | 67.79672 | 34.4763  |     |
| Principal Payment     | 32.20328        | 33.32042 | 34.4763  |     |
| Interest Payment (3%) | 3               | 2.033901 | 1.034289 |     |
| Pass Through Security |                 |          |          |     |
| 99.31729              | 66.69294        | 33.77872 |          |     |
| 67.79672              | 34.4763 34.4763 |          |          |     |

Whenever node (ij) corresponds to a exercise time,  then the value of PT
equals the value of outstanding principal at i. Whenever it is not a exercise node,  then we use the usual formula
$$P_{i j}^{P T}=e^{-r_{i j}\Delta t}(\pi^{*}P_{i+1,  j}^{P T}+(1-\pi^{*})P_{i+1,  j+1}^{P T}+C F_{i+1})$$
where
$\text{par}\;\text{1or}\;\text{4y}$.
$\mathbf{a}^{\pm}$
CFi+1 = Principal Paymenti+1 + Interest Paymenti+1 given in the top rows.

## PART III. PRICING MBS ON TREES

We want to price the Ginnie Mae Pass-Through security GNSF 4,  which on November 1,  2014 was trading at 106.5781.1 This pass-through security was collateralized by a pool of mortgages with a weighted average coupon (WAC) = 4.492%,  and a weighted average maturity (WAM) = 311 (months). We proceed as follows:

## 1. COMPUTE FORWARD VOLATILITIES FROM CAP VOLATILITY QUOTES: THE SOFTWARE

was set up to compute both the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curve from the swap data and the forward volatilities from the available cap volatilities. Figure 1 plots the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curve and the Forward Curve,  quarterly compounded. Instead,  Figure 2 plots the forward and flat volatility. As it can be seen,  the data are rather sparse,  and so interpolation methods are required. Moreover,  we can also see a couple of "humps" in the volatility,  around maturity of 7 year and 10 year. These humps may be artificial
![62_image_0.png](62_image_0.png)

1. Fit the BDT model to the discount curve and forward volatilities. The
next step is to fit the BDT model. Both the Matlab code and Excel spreadsheet guides were set up to do this automatically. The algorithm is described in Teaching Notes 5,  but essentially,  the methodology ensures that the tree is consistent with
the current yield curve and the option implied,  percent volatilities obtained above.
Because the coupons will be paid monthly,  we would need to have the binomial tree be calibrated at the monthly frequency,  that is,  dt = 1/12. While this could
![63_image_0.png](63_image_0.png)
How does this tree price the original caps? As it can be seen from Figure 4 the model does not do much of a good job on this dimension,  especially at the long horizon. The convergence of εi as becoming the volatilities for the binomial tree 3. Use the BDT model to value GNSF4. We finally obtain the price of the the pass-through security GNSF 4. We proceed as follows:

| Table 1: BDT Tree (First 10 Steps)   |        |        |        |        |        |        |        |         |         |         |
|--------------------------------------|--------|--------|--------|--------|--------|--------|--------|---------|---------|---------|
| 0                                    | 1      | 2      | 3      | 4      | 5      | 6      | 7      | 8       | 9       |         |
| 0                                    | 0.2325 | 0.5547 | 0.6716 | 0.8328 | 1.9113 | 4.0470 | 7.1525 | 10.5522 | 13.1973 | 15.3500 |
| 1                                    | 0      | 0.2787 | 0.3374 | 0.4214 | 0.9822 | 2.1204 | 3.8172 | 5.8239  | 7.6334  | 9.3127  |
| 2                                    | 0      | 0      | 0.1695 | 0.2132 | 0.5048 | 1.1109 | 2.0372 | 3.2143  | 4.4152  | 5.6500  |
| 3                                    | 0      | 0      | 0      | 0.1079 | 0.2594 | 0.5821 | 1.0872 | 1.7740  | 2.5538  | 3.4278  |
| 4                                    | 0      | 0      | 0      | 0      | 0.1333 | 0.3050 | 0.5802 | 0.9791  | 1.4771  | 2.0796  |
| 5                                    | 0      | 0      | 0      | 0      | 0      | 0.1598 | 0.3097 | 0.5404  | 0.8544  | 1.2617  |
| 6                                    | 0      | 0      | 0      | 0      | 0      | 0      | 0.1653 | 0.2983  | 0.4942  | 0.7655  |
| 7                                    | 0      | 0      | 0      | 0      | 0      | 0      | 0      | 0.1646  | 0.2858  | 0.4644  |
| 8                                    | 0      | 0      | 0      | 0      | 0      | 0      | 0      | 0       | 0.1653  | 0.2818  |
| 9                                    | 0      | 0      | 0      | 0      | 0      | 0      | 0      | 0       | 0       | 0.1709  |

![64_image_0.png](64_image_0.png)
![65_image_0.png](65_image_0.png)
(a) We compute the dollar coupon and the scheduled interest and principal payments. These calculations allow us to compute the scheduled outstanding principal balance. We do these computations assuming outstanding principal of 100 (so that,  the price will be also in percentage of 100,  like the quoted value of the security).
The coupon must satisfy the equation
$$P_{0}=C\sum_{j=1}^{n}\left({\frac{1}{1+r_{m}*d t}}\right)^{j}$$
where n is the number of coupon payments and dt is the time step. A useful formula is the following: define a =
% 1 1+rm↑dt&,  then we have the result that2
$$\sum_{j=1}^{n}a^{j}={\frac{a-a^{n+1}}{1-a}}$$
2To see this,  one just need to remember the geometric progression!→j=0 aj = 1/(1 → a). Then:
$$\sum_{j=1}^{n}a^{j}=\sum_{j=1}^{\infty}a^{j}-\sum_{j=n+1}^{\infty}a^{j}=a\sum_{j=0}^{\infty}a^{j}-a^{n+1}\sum_{j=0}^{\infty}a^{j}={\frac{a-a^{n+1}}{1-a}}.$$
![66_image_0.png](66_image_0.png)
$$C=P_{0}{\frac{(1-a)}{a-a^{n+1}}}=1.6347$$
Given C,  you can compute the scheduled principal and interest payment and remaining principal over time Interest paid in step i: *IntPaid(i) = WAC*dtstep*PP(i);*
Principal paid in step i: *PriPaid(i) = MCoupon-IntPaid(i);* Principal remaining for next period i + 1: *PP(i+1) = PP(i)-PriPaid(i)*.
Figure 5 shows the scheduled interest payments and the scheduled principal payments (top panel) as well as the remaining balance (bottom panel). The latter is the "strike price" for the call option to prepay,  discussed next.
(b) We finally compute the value of the non-callable mortgage on the tree (i.e.
present value of future coupons. This part is identical to previous cases,  except that there is no bullet capital payment at maturity) as well as the call option. That is,  for every (*j,  i*) we move backward by computing
VNoC(j,  i) = exp(-ImTree(j,  i)*dtstep)*(MCoupon+1/2*(VNoC(j,  i+1)+VNoC(j+1,  i+1)));
and if i > 1 (assume exercise can only be after time 1)
Call(j,  i)=max(VNoC(j,  i)-PP(i),  exp(-ImTree(j,  i)*dtstep)*(1/2*(Call(j,  i+1)+Call(j+1,  i+1))));
while at i = 1 Call(j)=exp(-ImTree(j)*dtstep)*(1/2*(Call(j)+Call(j+1,  2)));
The value of callable mortgage at every node is therefore VC(j,  i)=VNoC(j,  i)-Call(j,  i); We obtain the value of the pool of mortgages at time 0 equal to 100.7935,  and without prepayment option the value is 119.3734
(c) We finally price the GNSF 4. We use the new coupon rate (4%) and the new optimal prepayment time computed in the previous point to compute the cash flows of the pass-through security and thus its value at time 0. We use a backward algorithm like before (and explained in TN5) with the additional issue that we need to know when exercise occurred. Exercise occurs when the value of the call option (already computed) equals the payo$ from exercise,  that is,  when *Call(j,  i*) = V NoC(j,  i) → P P(i). Therefore,  at these times we have that the pass through investors get the full principal back.
If at node (j,  i) if *Call(j,  i)==VNoC(j,  i)-PP(i)* then the value of pass through security equal to principal *VPT(j,  i)=PP(i)* Otherwise there is no exercise and the cash flow of Pass Through equal to interest plus scheduled principal paid (all next period)
(a) The pass-through cash flow CFPassThrough(i+1,  1)=rbar*dtstep*PP(i)+PriPaid(i)
(b) the value of PT security given by backward computation
VPT(j,  i)=exp(-ImTree(j,  i)*dtstep)*(CFPassThrough(i+1,  1)+1/2*(VPT(j,  i+1)+VPT(j+1,  i+1)));

| Table 2: GNSF 4 (First 10 Steps)   |          |         |         |         |         |         |         |         |         |         |
|------------------------------------|----------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| 0                                  | 1        | 2       | 3       | 4       | 5       | 6       | 7       | 8       | 9       |         |
| 0                                  | 100.1208 | 97.8462 | 93.9685 | 88.7171 | 82.4991 | 75.7702 | 68.8145 | 61.9621 | 55.3699 | 48.9792 |
| 1                                  | 0        | 99.4883 | 98.9708 | 96.5098 | 92.2775 | 86.9897 | 81.2369 | 75.1187 | 68.8343 | 62.4412 |
| 2                                  | 0        | 0       | 98.9708 | 98.4474 | 97.9183 | 94.9904 | 90.6372 | 85.8818 | 80.5740 | 74.8459 |
| 3                                  | 0        | 0       | 0       | 98.4474 | 97.9183 | 97.3831 | 96.8420 | 93.2870 | 89.5428 | 85.0567 |
| 4                                  | 0        | 0       | 0       | 0       | 97.9183 | 97.3831 | 96.8420 | 96.2948 | 94.8280 | 92.1418 |
| 5                                  | 0        | 0       | 0       | 0       | 0       | 97.3831 | 96.8420 | 96.2948 | 95.7414 | 95.1819 |
| 6                                  | 0        | 0       | 0       | 0       | 0       | 0       | 96.8420 | 96.2948 | 95.7414 | 95.1819 |
| 7                                  | 0        | 0       | 0       | 0       | 0       | 0       | 0       | 96.2948 | 95.7414 | 95.1819 |
| 8                                  | 0        | 0       | 0       | 0       | 0       | 0       | 0       | 0       | 95.7414 | 95.1819 |
| 9                                  | 0        | 0       | 0       | 0       | 0       | 0       | 0       | 0       | 0       | 95.1819 |

We obtain that the the value of GNSF 4 without Option to Exercise is 113.3296,  while the value of GNSF 4 with optimal exercise is 100.1208. The tree is as The price is not close to the traded price (106.5781). The reason is that optimal exercise make all agents exercise too soon. However,  in reality,  many households cannot exercise the prepayment option. If the call option is not optimized,  then the value of the pass through security increases. The question then is what probability of exercise should we give in the various nodes to obtain a value of the security that is close to the one in the data. We use Monte Carlo Simulations for that.

## PART IV. USE MONTE CARLO SIMULATIONS ON TREES
1. We can simulate interest rate paths from the tree and then compute the value of complicated securities on the tree. The Matlab codes and the Excel spreadsheets were set up to be able to run such simulations.
1. We can use MC simulations to compute the value of 30-year cap and the 30year Asian cap. Generically speaking,  for each simulated path s of interest rates
[r0,  rs1*,  …,  r*sn→1] we can associate its sequence of cash flows [CFs1,  CFs2 *,  …,  CF*sn] and then compute its present value
$$V_{0}^{s}=\sum_{i=0}^{n-1}e^{-\sum_{j=0}^{i-1}r_{j}^{s}\Delta t}C F_{i}^{s}$$
Note that to discount a cash flow at time i we need to use interest rates until i→1,  the step before (because the last rate rsi→1 is the discount from i back to i → 1).
The value of the security is then
$$\widehat{V}_{0}=\frac{1}{N S i m}\,  \sum_{s=1}^{N S i m}V_{0}^{s}$$
We can also compute the standard errors by computing first the standard deviation of V s0 and divide by the square root of the number of simulations Nsim
$$s t.e r r o r={\frac{S t.D e v i a t i o n[V_{0}^{1},  V_{0}^{2},  …,  V_{0}^{N S i m}]}{\sqrt{N S i m}}}$$
1. For instance,  in a Cap we have
$$C F_{i}^{s}=\operatorname*{max}(r_{i}^{s}-r_{k})$$
Note that this is not a plain vanilla cap but a Cap in Arrears,  as the interest rate at time i is paid at time i and not at i + 1 (moreover,  we are simulating continuously compounded rates. In principle,  we should change rsi into a quarterly compounded rate through the usual formula). With *NSim* = 5000,  the methodology above yields V Cap 0 = 276.1099; *st.error* = 3.2422 Still a pretty large standard error. We would need to increase the number of simulations to 100,  000 to start having some reasonably small standard error.
1. Once we know how to do MC simulations,  computing the value of an Asian Cap is straightforward. The only thing we have to change is the payo$,   which now is
$$C F_{i}^{s}=\operatorname*{max}(a v e r a g e[r_{0},  r_{1}^{s},  …,  r_{i}^{s}]-r_{k})$$
That's it. No other changes needed. The same code yields
$${}^{\prime}=116.5956;\;\;\;\;s t.e r r c$$
$=\;1.9$.
V *AsianCap* 0 = 116.5956; *st.error* = 1.8092 Quite a smaller value: Asian options are often preferred to standard options because they cost much less,  although clearly,  there is more risk. For instance,  if the average is small due to a low period of interest rates and then interest rate suddenly increase,  the Asian Cap (or Caplet) may be out of the money,  while a regular Cap would actually be in-the-money,  implying that the Cap would be better able to hedge against sudden variation in interest rates.
1. The same methodology can be used to compute the value of Mortgage Backed Security through a Prepayment Function. In this case,  the logic is to simulate paths of interest rates,  and for each path,  provide a probability pt that investors will prepay the mortgage (i.e. a fraction pt of investors prepay the mortgages).
Both the Matlab guide and the Spreadsheet guide were already set up to do all of these calculations,  and the task was to compute the value of the pass through security - and interest only / principal only securities - for various values of the parameters. The prepayment function was simple:
$$p_{i}=c_{1}\operatorname*{max}(r_{m}-s p-r_{i},  c_{2})$$
Given a sequence of interest rates rsi and thus corresponding simulated psi,  we can compute the full cash flow sequence as per TN 5,  page that is,  we can compute sequentially the following items (now at quarterly frequency but this can be done at any frequency):
Mortgage interest payment: Isi = rm44 Scheduled principal: P ayscheduled,  s Principal prepayment: P ayprepaid,  s Outstanding principal: Lsi+1 = Lsi → P ayscheduled,  s
$$\frac{r_{4}^{m}}{4}\times L_{i}^{s}\eqno(1)$$ $$C_{i}^{s}-I_{i}^{s}\eqno(2)$$ $$p_{i}^{s}\times\left(L_{i}^{s}-Pay_{i}^{scheduled,  s}\right)\eqno(3)$$ $$L_{i}^{s}-Pay_{i}^{scheduled,  s}-Pay_{i}^{repaid,  s}\eqno(4)$$
$$\begin{array}{r l}{C_{i+1}^{s}}&{{}=}\\ {\end{array}$$
i = psi ↔
Update of scheduled coupon: Csi+1 = (1 → psi) ↔ Csi (5)
Pass-through interest payment: $$I_{i}^{PT,  s}=\frac{r_{i}^{PT}}{4}\times L_{i}^{s}$$ (6) Total cash flow: $$CF_{i}^{s}=I_{i}^{PT,  i}+Pay_{i}^{scheduled,  s}+Pay_{i}^{repeated}$$ (7)
$$V_{0}^{P T,  s}=\sum_{i=0}^{n-1}e^{-\sum_{j=0}^{i-1}r_{j}^{s}\Delta t}C F_{i}^{s}$$
IO cash flow: $\;\;CF^{IO,  s}_i\;=\;I^{PT,  i}_i$ $\text{PO cash flow:}\;\;CF^{IO,  s}_i\;=\;Pay^{scheduled,  s}_i+Pay^{propaid,  s}_i$ (1)
$$\begin{array}{r c l}{{V_{0}^{I O,  s}}}&{{=}}&{{\sum_{i=0}^{n-1}e^{-\sum_{j=0}^{i-1}r_{j}^{s}\Delta t}C F_{i}^{I O,  s}}}\\ {{}}&{{}}&{{}}\\ {{V_{0}^{P O,  s}}}&{{=}}&{{\sum_{i=0}^{n-1}e^{-\sum_{j=0}^{i-1}r_{j}^{s}\Delta t}C F_{i}^{P O,  s}}}\end{array}\tag{1}$$
$$(11)$$
$$(12)$$
Given the dynamics of Lsi from the simulations we can compute the path through future cash flows:
The price of the pass-through MBS in simulation s is thus the same as for the general case:
Note that computing the value of IO and PO is immediate from above,  after we know the full amount of cash flows. The idea is simply to divide up the interest only cash flows from the principal only cash flows and the prices for each simulated rate path are The final values of the pass through and the IO and PO securities is given by the average of these simulated values,  as discussed earlier.
 (1) (2) (3) $\textit{aid,  s}$ …
$$\left(5\right)$$
$$(1-p_{i}^{s})\times C_{i}^{s}$$
$$\quad(6)$$
$$({\mathfrak{S}})$$
(4)
1. Given rm = 0.04492,  we use the parameters c1 = 5,  c2 = 0 and sp = 0.015,  and we obtain the value of GNSF 4 equal to V' *GNSF*4 0 = 106.1751 with standard errors s.e. = 0.1747. This is not too far from the traded price,  actually. Note that the parameters c1,  c2 and sp determine a *Risk Neutral* probability p↑i of prepayment,  as we obtained this value not from an estimate of the true prepayment frequency of homeowners,  but to match the price of the PT itself. That is,  there could be a risk premium component in this probability as well.
1. These are given by V'IO
0 = 26.1264 and V' P O
0 = 80.0487. Clearly,  because the sum of the cashflows flowing to PO and IO equal the total cash flows to GNSF 4,  the sum of the prices of IO and PO must be the same as the price of GNSF 4.