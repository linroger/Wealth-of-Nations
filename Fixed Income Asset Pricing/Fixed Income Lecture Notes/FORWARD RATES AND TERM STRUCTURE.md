---
cssclasses:
  - academia
linter-yaml-title-alias: Forward Rates and Term Structure
title: Forward Rates and Term Structure
tags:
  - expectations_hypothesis
  - forward_rates
  - interest_rates
  - term_structure
  - yield_curve
aliases:
  - Expectations
  - Forward Rates
  - Term Structure
  - Yields
key_concepts:
  - Expectations hypothesis
  - Forward rates calculation
  - Risk premium impact
  - Term structure of rates
  - Yield curve decomposition
---

[[Fixed Income Lecture Notes]]

 [[Introduction to Fixed Income Asset Pricing]]

 [[Lecture Note 2Interest Rate Risk Management And Factors]]

 [[Forward Rates and Term Structure]]

 [[Teaching Note 4 Interest Rate Derivatives]]

 [[Teaching Note 5 Risk Neutral Pricing]]

[Teaching Note 6 Mortgage Backed Securities](Teaching%20Note%206%20Mortgage%20Backed%20Securities.md)

[Teaching Note 7 A Rundown On Continuous Time Models](Teaching%20Note%207%20A%20Rundown%20On%20Continuous%20Time%20Models.md)

[PSET III Fixed Income Asset Pricing](PSET%20III%20Fixed%20Income%20Asset%20Pricing.md)

## INTRODUCTION
- There are numerous questions that arise when we think about the term structure
of interest rates,  such as:
1. Why does the term structure of interest rates tend to slope upwards?
1. What is the risk involved in investing in Treasury securities?
1. Can we predict medium-to-long term yields? What about returns?
## THE EXPECTATIONS HYPOTHESIS
- The [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] is the hypothesis that long-term yields just reflect
market participants' expectation of future interest rates
Long-term yield = Expected future short-term rates
- To illustrate,  let today be t and consider the case in which investors have perfect foresight of the next 1-year interest rates$y_ {t+1}(1)$.
- Investors then also know that the zero coupon bond price next year will be
$$Z_{t+1}(1)=e^{-y_{t+1}(1)\times1}$$
- Because under these assumptions,  Z_ {t+1}(1) is known today,  its value today is the
discounted value using the current 1-year yield:
$$Z_{t}(2)=Z_{t}(1)\times Z_{t+1}(1)=e^{-\langle y_{t}(1)+y_{t+1}(1)\rangle}$$
- Because the two-year yield also satisfies$Z_{t}(2)=e^{-y_{t}(2)\times2}$,  we obtain that under perfect foresight$$y_{t}(2)=\frac{1}{2}(y_{t}(1)+y_{t+1}(1))$$
## THE EXPECTATIONS HYPOTHESIS (CNTD.)
- Extending this reasoning to n future one-year yields,  then under perfect foresight
the yield of a zero-coupon bond with n + 1 years to maturity is:
$$y_{t}(n+1)=\mathsf{Average}[y_{t}(1),        y_{t+1}(1),        …,        y_{t+n}(1)]={\frac{1}{n+1}}\stackrel{n}{\underset{i=0}{\Sigma}}y_{t+i}(1)$$
- The **[[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]]** substitutes the perfect foresight with forecasts:
$$The\ long\ term\ yield=\ forecasted\ average\ path\ of\ future\ rates$$$$y_{t}(n+1)\ =\ E_{t}\left[\frac{1}{n+1}\sum\limits_{i=0}^{n}y_{t+i}(1)\right]\tag{1}$$
- Subtracting the current **1-year** yield,  we can also write$$y_{t}(n+1)-y_{t}(1)\ =\ E_{t}\left[\frac{1}{n+1}\sum\limits_{i=0}^{n}y_{t+i}(1)\right]-y_{t}(1)$$
(2)
## PRELIMINARY HEURISTIC EVIDENCE - DOES THIS RELATION HOLDS IN THE DATA?
- Heuristically,  next figure plots the expected future three-month rates from the survey of Professional Forecasters from 1981 to 2015.
- The forecasts are for the three-month T-bill rate for the current quarter,  denote in the figure by$r(t)$,  and for the next three quarters,  denoted by$r(t + 3m)$,  $r(t + 6m)$,  and$r(t + 9m)$,  respectively.
 ![500](Lecture%20Note%203%20Understanding%20The%20Term%20Structure%20Of%20Interest%20Rates-20240405072858865.png
- Next figure shows the 1-year term spread,  defined as yt(1y) − r(t) together with the 1-year "expectation spread".
 ![500](Lecture%20Note%203%20Understanding%20The%20Term%20Structure%20Of%20Interest%20Rates-20240405072953056.png The 1-year term spread is greater than the "expectation spread" most of the time.
	- the expectation hypothesis does not hold (at least,  using survey forecasts).
## THE EXPECTATION HYPOTHpng AND FORWARD RATES
# Forward Rates and Term Structure

We observed in **Teaching Notes 1** that a forward rate at time$t$for an investment between$\tau_1$and$\tau_2$can be represented as:

$$
f_t(\tau_1,         \tau_2) = \frac{1}{\tau_2 - \tau_1} \ln \left( \frac{Z_t(\tau_1)}{Z_t(\tau_2)} \right) = \frac{1}{\tau_2 - \tau_1} \left( y_t(\tau_2)\tau_2 - y_t(\tau_1)\tau_1 \right) \tag{3}
$$
- Consider a sequence of maturities$\tau_i = \tau_{i-1} + \Delta t$,  for$i = 2,         \ldots,         n$. We have:
	- $f_t(\tau_1,         \tau_2) = \frac{1}{\Delta t} \left(y_t(\tau_2)\tau_2 - y_t(\tau_1)\tau_1 \right)$
	- $f_t(\tau_2,         \tau_3) = \frac{1}{\Delta t} \left(y_t(\tau_3)\tau_3 - y_t(\tau_2)\tau_2 \right)$
	- $\vdots$
	- $f_t(\tau_{n-2},         \tau_{n-1}) = \frac{1}{\Delta t} \left(y_t(\tau_{n-1})\tau_{n-1} - y_t(\tau_{n-2})\tau_{n-2} \right)$
	- $f_t(\tau_{n-1},         \tau_n) = \frac{1}{\Delta t} \left(y_t(\tau_n)\tau_n - y_t(\tau_{n-1})\tau_{n-1} \right)$
- Summing over all of the forward rates,  we find
$$\sum_{i=2}^{n}f_{t}(\tau_{i-1},        \tau_{i})=\frac{1}{\Delta t}\left(y_{t}(\tau_{n})\tau_{n}-y_{t}(\tau_{1})\tau_{1}\right)$$
- Assuming τ1 = ∆t and defining ft(0,  ∆t) = yt(∆t),  we the obtain
$$y_{t}(\tau_{n})=\frac{\Delta t}{\tau_{n}}\sum\limits_{i=1}^{n}f_{t}(\tau_{i-1},        \tau_{i})=\mbox{Average forward rates}\tag{4}$$
- The expectation hypothesis then implies that for every i the forward rate is equal to the expected future short-term rate:
$$f_{t}(\tau_{i},        \tau_{i}+\Delta t)=E_{t}[y_{t+\tau_{i}}(\Delta t)].$$
- ![500](Lecture%20Note%203%20Understanding%20The%20Term%20Structure%20Of%20Interest%20Rates-20240405073248911.png Again,  expected future rates are mostly lower than forward rates.
## TIME VARYING RISK PREMIA
- The violation of the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] (and the time variation in sprepnguggests the existence of an additional term in Equation (1):
$$y_{t}(n+1)\ =\ E_{t}\left[\frac{1}{n+1}\sum\limits_{i=0}^{n}y_{t+i}(1)\right]+RP_{t}\tag{5}$$
- where$RP_{t}$reflects a risk premium from holding the bond from$t$to$t+1$.
- The time variation in$RP_t$invalidates the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]].
	 - Even if the expectation of future interest rates does not change,  the yield curve may change because$RP_t$changes.
	- Therefore,  movements in the yield curve do not only correspond to variations in expected future short-term yields.
## TERM STRUCTURE DECOMPOSITION
- Let$y_t(n + 1$) = yield at t of a bond with *time to maturity* (n + 1) years from t
$$Z_{t}(n+1)=e^{-y_{t}(n+1)(n+1)}\tag{6}$$
- The value of this bond next year will then be
$$Z_{t+1}(n)=e^{-y_{t+1}(n)\times n}$$
- The yield next year yt+1(n) is not known. Assume it normally distributed
$$y_{t+1}(n)\sim{\cal N}\left(\bar{y},        V\right))\quad\mbox{with}\quad\bar{y}=E[y_{t+1}(n)]$$
- $Z_{t+1}(n)$is risky and so investors at$t$may require an additional discount$RP$:$$Z_{t}(n+1)=e^{-\left(y(1)+RP_{t}\right)\times1}E_{t}[Z_{t+1}(n)]\tag{7}$$
- Using the properties of the normal distribution we then obtain
$$E_{t}[Z_{t+1}(n)]=e^{-\overline{{{y}}}\times n+\frac{(n)^{2}}{2}V}$$
- Using (6) and (7) we then obtain
$$y_{t}\left(n+1\right)=\frac{1}{n+1}\times y_{t}\left(1\right)+\frac{n}{n+1}\times E_{t}\left[y_{t+1}\left(n\right)\right]\qquad\text{(Expected future yield)}$$$$+\frac{RP}{n+1}\qquad\qquad\qquad\qquad\qquad\qquad\qquad\qquad\qquad\text{(Risk premium)}$$$$-\frac{n^{2}}{2(n+1)}V_{t}\qquad\qquad\qquad\qquad\qquad\qquad\text{(Convexity)}\tag{8}$$
- The current long-term yield$y_t(n + 1)$depends on
	1. The weighted average between the current short-term yield and the expected long-term yield next year.
	1. A risk premium RP that market participants require to hold long-term zero coupon bonds with maturity n + 1 over safe bonds with maturity 1.
	1. A convexity term due to the nonlinear relation that exists between the yield$y_{t+1}(n)$and the price$$Z_{t+1}(n) = e^{−y_{t+1}(n)×n}$$
## EXPECTATION HYPOTHESIS (AGAIN)
- Let$RP_t = \frac{n^2}{2} V_{t}$Then the expectation hypothesis holds:
$$y_{t}\left(n+1\right)\,        =\,        \frac{1}{n+1}\times y_{t}\left(1\right)+\frac{n}{n+1}\times E_{t}\left[y_{t+1}\left(n\right)\right]\tag{9}$$
- Subtract$y_{t}\left(n+1\right)\times\left(n\right)/(n+1)$on both sides,  to get$$E_{t}\left[y_{t+1}\left(n\right)\right]-y_{t}\left(n+1\right)\,        =\,        \,        \,        \,        \,        \,        \,        \,        \frac{1}{n}[y_{t}\left(n+1\right)-y_{t}\left(1\right)]\tag{10}$$
- A steep term structure (on the RHS) signals the market expects an increase in the yield$y_t (n + 1)$between$t$and$t + 1$(on the LHS)
$$E_{t}\left[y_{t+1}\left(n\right)\right]>y_{t}\left(n+1\right)$$
	- market expects a low or negative return on$(n + 1)$maturity bond.
 ![500](Lecture%20Note%203%20Understanding%20The%20Term%20Structure%20Of%20Interest%20Rates-20240405074610622.webp)
- Example: On t =1/31/1994 yield curve was increasing and the spread was 3.3%.
- High spread *may* signalpng-term yield$y_t(30)$= 6.87% may increase.
- And indeed,  it did:$t + 1 =$1/31/1995 we have$y_{t+1}(29) = 7.81\%.$
- This implies a loss on investment:$R_{t,        t+1}=\frac{Z_{t+1}(29)}{Z_{t}(30)}-1=\frac{10.3893}{12.7048}-1=-18\%$
## DOES THE EXPECTATION HYPOTHESIS HOLD IN THE DATA?
- Does a high slope predict an increase in future yields? (i.e. should you go short?)
- In an influential paper,  Campbell and Shiller (1988) run the following regressions
$$\text{Changes in yield}=\alpha+\beta\times\text{Slope}_{t}+\varepsilon_{t+1}\tag{11}$$
- That is,  from yield data we can compute a dependent "$Y$" variable
$$Y_{t}=\text{Changes in yield}=y_{t+1}\left(n\right)-y_{t}\left(n+1\right);\quad t=1,        2,        …,        T$$
- and an explanatory "X" variable
$$X_{t}=\mathsf{Slope}_{t}=\frac{1}{n}\left[y_{t}\left(n+1\right)-y_{t}\left(1\right)\right];\quad t=1,        2,        …,        T$$
- Then Campbell and Shiller (1988) run the regression
$$Y_{t}=\alpha+\beta X_{t}+\varepsilon_{t+1}\tag{12}$$
- The [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] has$α = 0$and$β = 1.$
- We can see if this true in the data.
## CAMPBELL AND SHILLER REGRESSION

Test of the Expectation Hypothesis

$$\begin{array}{c|c|c|c|c|c}
\text{Maturity } n & \alpha & se(\alpha) & \beta & se(\beta) & R^2 \\
\hline
2 & -0.01 & 0.27 & -0.83 & 0.52 & 0.03 \\
3 & 0.09 & 0.24 & -1.23 & 0.62 & 0.05 \\
4 & 0.16 & 0.21 & -1.59 & 0.70 & 0.07 \\
5 & 0.17 & 0.21 & -1.56 & 0.76 & 0.06 \\
\end{array}
$$

Notes: Regression results based on Fama Bliss discount bond data from CRSP. Sample: 1964 - 2006.

- Important to note:
- β ̸= 1 =⇒ Expectations Hypothesis is rejected
- *β <* 0 =⇒ steep yield curve predicts a **decrease** of long-term yield.
	- This is the opposite of the basic simple intuition about a raising yield curve.
- Bottom line: A steep yield curve predicts high returns of long-term bonds.
 ![500](Lecture%20Note%203%20Understanding%20The%20Term%20Structure%20Of%20Interest%20Rates-20240405074821841.webp)
- Example: On t =1/30/2004 yield curve was increasing and the spread was 4.1%.
- In the data,  high spread forecast a decline of long-term yield$y_t(30) = 5.347\%$.
- And indeed,  it did
- $t + 1$= 1/31/2005 we have$y_{t+1}(29)$= 4.655\%.
- This implies a gain on investment:$$
R_{t,  t+1}=\frac{Z_{t+1}(29)}{Z_t(30)}-1=\frac{25.9279}{20.1046}-1=+29\%
$$
## TIME VARYING RISK PREMIA
-  This result implies that the slope of the term structure predicts
$$L R P_{t}=R P_{t}-\frac{n^{2}}{2}V_{t},        \tag{13}$$
-  *LRP*t stands for "Log Risk Premium" (see below).
-  In fact,         we can rewrite (8) as
$$E_{t}\left[y_{t+1}\left(n\right)-y_{t}\left(n+1\right)\right]=\frac{1}{n}\left[y_{t}\left(n+1\right)-y_{t}\left(1\right)\right]-LRP_{t}\tag{14}$$
-  We know slope is not positively related to the left-hand-side (previous table)
	- then it must be positively correlated with $LRP_{t}$.
- When slope increases so does *LRP*t,         thereby killing the positive correlation.
-  Implication:
	- High slope ̸⇒ market expects higher future rates.
	- High slope ⇒ high risk premium ⇒ high expected return of long-term bonds
		- strong price increase ⇒ low future yield.
## THE PREDICTABILITY OF BOND RETURNS
-  The Log Risk Premium $LRP_t$ can also be rewritten as:
$$LRP_{t}=E_{t}\left[\log\left(\frac{Z_{t+1}\left(n\right)}{Z_{t}\left(n+1\right)}\right)-\log\left(\frac{1}{Z_{t}\left(1\right)}\right)\right]\tag{15}$$
- The expectation hypothesis implies $LRP_{t}=0$.
 +  To test for this hypothesis,         denote the Log Excess Return (LER) from holding a long-term zero coupon bond over the short term bond by
$$LER_{t}=\log\left(\frac{Z_{t+1}\left(n\right)}{Z_{t}\left(n+1\right)}\right)-\log\left(\frac{1}{Z_{t}\left(1\right)}\right)\tag{16}$$
- LER ${}_{t}$* is the ex-post realized empirical counterpart of *LIRP*:
$$LRP_{t}=E_{t}[LER_{t}]$$
4To see this,         substitute in (15) the expressions log(Zt+1(n)/Zt(n + 1)) = −yt+1(n)n + yt(n + 1)(n + 1) and
− log(1/Zt(1)) = yt(1) and then use (8).
## FAMA BLISS REGRESSIONS
-  Fama and Bliss (1987) then run the following regression
$$LER_{t}=\alpha+\beta\left[f_{t}(n,        n+1)-y_{t}(1)\right]+\varepsilon(t)\tag{17}$$
- The expectation hypothesis has $LPR_{t}=0$,         and therefore $\alpha=\beta=0$.
$$

\text{Panel B: Log Excess Return Prediction from Forward Slope} $$

$$\begin{array}{c|c|c|c|c|c}
\hline
\text{Maturity } n & \alpha & se(\alpha) & \beta & se(\beta) & R^2 \\
\hline
2 & -0.01 & 0.27 & 0.92 & 0.26 & 0.14 \\
3 & -0.19 & 0.49 & 1.22 & 0.34 & 0.15 \\
4 & -0.43 & 0.69 & 1.43 & 0.44 & 0.16 \\
5 & -0.16 & 0.93 & 1.11 & 0.51 & 0.07 \\
\end{array}
$$

Panel B: Log Excess Return Prediction from Forward Slope

- β is significantly different from zero,  and indeed positive.
- This finding,  again,  shows that the excess log return is in fact predictable:
- When the forward spread is strongly positive,  on average investments in longterm bonds generate a higher return compared to short term bonds.
## COCHRANE AND PIAZZESI FACTOR
- Cochrane and Piazzesi (2005) have shown that a specific combination of forward
rates successfully predicts excess log returns.
- The predicting factor is defined by
$$x_{t}=\gamma_{0}+\gamma_{1}y_{t}(1)+\gamma_{3}f_{t}(2,        3)+\gamma_{5}f_{t}(4,        5)$$
- The parameters γi are estimated in a first stage regression:
- Define
$$\overline{{{L}}}E\overline{{{R}}}_{t}=0.25\times\sum\limits_{n=2}^{5}L E R_{t}(n)$$
- Then,  estimate γi's with:
$$\overline{{{L}}}E R_{t}=\gamma_{0}+\gamma_{1}y_{t}(1)+\gamma_{3}f_{t}(2,        3)+\gamma_{4}f_{t}(4,        5))+\varepsilon_{t}$$
- The estimates for 1964 - 2006 sample are cγ0 = −3.26,  cγ1 = −1.87,  cγ3 = 3.94,
and cγ5 = −1.64.
## COCHRANE AND PIAZZESI REGRESSION
- Cochrane and Piazzesi (2005) run the regression
$$L E R_{t}(n)=\alpha+\beta\times x_{t}+\varepsilon_{t}\tag{18}$$
Panel C: Log Excess Return Prediction from Cochrane Piazzesi Factor
$$\text{Panel C: Log Excess Return Prediction from Cochrane Piazzesi Factor}$$
$$\begin{array}{c|c|c|c}
\hline
\text{Maturity } n & \beta & se(\beta) & R^2 \\
\hline
2 & 0.47 & 0.07 & 0.30 \\
3 & 0.88 & 0.13 & 0.33 \\
4 & 1.22 & 0.19 & 0.35 \\
5 & 1.43 & 0.24 & 0.32 \\
\end{array}$$
-  The coefficients are strongly positive,         and the R2 higher than in Panel B,         showing that including information on the whole term structure helps predict bond excess returns.
## COPING WITH INFLATION RISK: TREASURY INFLATION-PROTECTED SECURITIES
-  Treasury coupon bonds are in nominal terms,         as they pay in dollars.
-  How much you can buy with those dollars depends on inflation before maturity.
-  Over long periods,         the inflation can be pretty high.
-  CPI index = weighted average of the representative good prices.
-  The change in the CPI measures the realized inflation during the period.
## SIMPLE EXAMPLE
-  We have monthly income of $10,         000 and let CPI = price of consumption basket.
-  How much we can buy at a given time $t_1$ is $C(t_1) =\$10,         000/CPI(t_1)$.
	+ E.g. if $CPI(t_1)$ = 10 =⇒ we can buy 1000 units of consumption basket.
- If basket only contains$10-burgers,         we can buy  $C(t_1)$  = 1000 burgers at t1.
-  Let now be t2 and let our income be the same. Because of inflation,         now  $CPI(t_2)$  =
	- We can now only buy  $C(t_2)$  =$10,         000/ $CPI(t_2)$  = 500 burgers: big loss in consumption even if nominal income is the same.
## INFLATION RISK AND THE LOSS OF PURCHASING POWER
-  The ratio  $C(t_2)$ / $C(t_1)$  = loss in purchasing power of a dollar between t1 and t2.
-  This ratio is given by  $C(t_2)$ / $C(t_1)$  =  $CPI(t_1)$ / $CPI(t_2)$ .
	- In the previous example  $CPI(t_1)$ / $CPI(t_2)$  = 0.5 =⇒ we can only afford at t2 half of the goods we could buy at t1.
-  Changes in CPI are unknown =⇒ nominal securities have inflation risk
	- Risk that the dollar payoff will afford less consumption goods than expected.
-  Inflation-protected securities are vehicles that hedge against this inflation risk.
## TREASURY INFLATION PROTECTED SECURITIES (TIPS)
-  TIPS are coupon bonds issued with maturities of 5,         10,         and 20 years.
-  The coupon rate of TIPS is a constant fraction of the principal.
-  The principal changes over time in response to inflation.
	- If the CPI increases,         then the principal amount increases proportionally.
-  The Treasury publishes Index ratios
$$\mbox{Index ratio}(t)\ =\ \max\left(\frac{\mbox{Reference CPI}(t)}{\mbox{CPI}(\mbox{issurance})}\right)$$
Reference CPI$(t)\ =\ w(t)\ \mbox{CPI}(t-1)+(1-w(t))\ \mbox{CPI}(t-2)$
- where $w(t)$ is a weight that depends on the quoted day of the month.
-  Next Table contains quotes of Treasury securities on November 26,         2007.
	- Given the index ratio,         the next coupon payment is
Coupon payment$(t)=\dfrac{\text{Coupon rate}}{2}\times100\times\text{Index ratio}(t)$
## TREASURY SECURITIES ON NOVEMBER 26,         2007
 ![500](Lecture%20Note%203%20Understanding%20The%20Term%20Structure%20Of%20Interest%20Rates-20240405081418999.webp)
Data Source: Bloomberg,         Inc.
## REFERENCE INDEX EXAMPLE
-  The quotes in the Table are for November 26,         2007. -  The CPI used to comppngdex ratio is not the November CPI.
- CPI values are released by BLS during the third week of the following month.
-  CPI used is instead the average between the August and September CPIs (207.917
and 208.490,         respectively).
- Because November 26 is 25 days after November 1,         the calculation is
$${\mathsf{C P I}}(t)={\frac{5}{30}}\times207.917+{\frac{25}{30}}\times208.490=208.3945.$$
-  An investor in TIPS is still subject to a small inflation risk during the two months
between the CPI measure and the actual payment.
## REAL BONDS AND THE REAL TERM STRUCTURE OF INTEREST RATES
-  Borrowing and lending do not need dollars.
	- You can borrow a car from a friend and return it in a week.
	- If you forget your wallet,         you can ask your friend to buy a sandwich today with the agreement you will return the same sandwich tomorrow.
- If your "friend" see you very hungry today,         he may ask you to return a bigger sandwich tomorrow. I.e. charge a big *real* interest rate.
-  **Real bonds** are bonds that are denominated in units of a good instead of dollars.
-  Relevant to inflation linked securities are bonds that are denominated in units of the consumption basket that underlies the CPI index calculation.
-  A **real discount factor** $Z^{real}(t,         T)$ defines the *exchange rate* between consumption goods at t versus consumption goods at a later date T.
	- How "bigger" a sandwich are we willing to give back to the "friend" tomorrow to have a sandwich today?
## REAL RATES
-  From real discounts $Z_{real}(t,         T)$ compute the **real rate** as usual:
$$Z^{real}(t;T)=e^{-r_{real}(t;T)(T-t)}\times1\tag{19}$$
-  implies
$$r_{real}(t;T)=-\frac{\ln\left(Z^{real}(t;T)\right)}{T-t}\tag{20}$$
-  The **real term structure of interest rates** is r*real*(t; T) for maturities T.
-  The value (in consumption goods) of a real coupon bond with maturity T and coupon rate c is
$$P_{c}^{r e a l}(t;T)=\frac{c\times100}{2}\sum\limits_{i=1}^{n}Z^{r e a l}(t;T_{i})+100\times Z^{r e a l}(t;T)$$
## REAL BONDS AND TIPS
-  Suppose an investment bank purchases a TIPS and strips the coupons from principal,         generating a series of zero coupon bonds.
-  These zero coupon bonds pay an amount that is tied to the CPI.
-  Denoting by *Idx*(T) the CPI adjustment for maturity T (recall,         it depends on the CPI two months earlier),         the payoff of a zero coupon TIPS is as follows:
Zero-coupon TIPS payoff at $T$ = $$Z_{TIPS}=\dfrac{Idx(T)}{Idx(0)} \tag{21}$$ 
-  Idx(T)*/Idx*(0) = increase in the consumption basket price between 0 and T.
-  For simplicity,         assume $Idx(T) = CPI(T) =$ price of one unit of consumption basket
+  Given $Z^{real}(t,         T)$,         the value at t of a security paying *Idx*(T) (i.e. the amount needed to purchase one unit of consumption basket) is
	+ Present value of $Idx(T) = PV$ of one unit of consumption = $Z^{real}(t,         T)$
## REAL BONDS AND TIPS (CNTD)
-  This present value though is expressed in terms of units of the consumption basket ($Z_{real}(t,         T$) is an exchange rate of consumption at t for consumption at T).
-  We can convert this value to dollars by multiplying it by the *current* price of the consumption basket $Idx(t)$. We then obtain
	- Dollar present value of $Idx(T)=Z^{real}(t;T)\times Idx(t)$
Finally,         to obtain the payoff of the zero-coupon TIPS we must divide by$Idx(0)$:
Dollar value of a zero-coupon TIPS =$Z^{TIPS}(t;T)=Z^{real}(t;T)\times\frac{Idx(t)}{Idx(0)}$(22)
-  Given the value of zero-coupon TIPS,         we can value coupon bearing TIPS. -  Therefore,         a TIPS value at t,         with maturity T,         and coupon rate c is given by
$$P_{c}^{TIPS}(t;T)=\frac{Idx(t)}{Idx(0)}\times\left[\frac{c\times100}{2}\sum\limits_{i=1}^{n}Z^{real}(t;T_{i})+Z^{real}(t;T)\right]\tag{23}$$
## FITTING THE REAL YIELD CURVE
-  Clearly,         zero-coupon real bonds Z*real*(t; Ti) are not observable,         but they are embedded in the prices of TIPS.
-  We can use the price of TIPS to "back out" the discount factors Z*real*(t; Ti).
-  One limitation compared to the case of Treasuries is that we do not have available
as many bond prices,         and therefore the bootstrapping strategy is not applicable.
-  However,         we can use the curve fitting method using a flexible function for the
discount factor,         such as the Nelson Siegel model
$$r_{real}(0,        T)\ =\ \theta_{0}+(\theta_{1}+\theta_{2})\,        \frac{1-e^{-\frac{T}{\kappa_{1}}}}{\frac{T}{\kappa_{1}}}-\theta_{2}e^{-\frac{T}{\kappa_{1}}}+\theta_{3}\left(\frac{1-e^{-\frac{T}{\kappa_{2}}}}{\frac{T}{\kappa_{2}}}-e^{-\frac{T}{\kappa_{2}}}\right)\tag{24}$$
- From the previous table,         for instance,         we obtain the following results
## REAL AND NOMINAL RATES ON NOVEMBER 26,         2007
 ![500](Lecture%20Note%203%20Understanding%20The%20Term%20Structure%20Of%20Interest%20Rates-20240405081803258.webp)
Data Source: Bloomberg.
 -  NEXT FIGURE SHOWS THAT THE TERM STRUCTURE OF REAL RATES CHANGES OVER TIME. REAL RATES DURING AND AFTER THE CRISIS
 ![500](Lecture%20Note%203%20Understanding%20The%20Term%20Structure%20Of%20Interest%20Rates-20240405081827409.webp)
-  Negative *real* rates are not uncommon.
- We give back our "friend" a smaller sandwich because its price skyrocketed.
## NOMINAL AND REAL INTEREST RATES
-  What is the relation between real and nominal rates?
-  We now show that nominal rate = real rate + expected inflation + inflation risk premium− convexity
-  Consider first the value today of$1 at T
$$Z(0,        T)=e^{-r(0,        T)T}\times\$1$$
- Alternatively,         we can express this in "consumption goods": $1 at T will buy C(T) = $\frac{1}{CPI(T)}$ units of consumption good.
-  Unfortunately,         this amount is not known today,         because CPI(T) is stochastic.
-  To compute the present value we need more assumptions.
-  Let π be the annualized inflation rate between 0 and T
$$\pi=\frac{1}{T}\ln\left(\frac{\mathsf{C P I}(T)}{\mathsf{C P I}(0)}\right)$$
## THE FISHER EQUATION UNDER PERFECT FORESIGHT
-  Consider first *Perfect Foresight*: Assume investors know π and hence CPI(T).
-  Then the value today of$1 at T in consumption good units is
$$\mathrm{Present~value~of}\;\;\;C(T)=Z^{r e a l}(0,        T)\times C(T)=Z^{r e a l}(0,        T)\times{\frac{\S1}{\mathsf{CPI}(T)}}$$
-  To obtain the *dollar* value,         we multiply this by the price of consumption good
$$\mathsf{D o l l a r \ pre se n t\;v a lu e\;o f\;\;}C(T)=\mathsf{C P I}(0)\left(Z^{r e a l}(0,        T)\times{\frac{\$1}{\mathsf{C P I}(T)}}\right)$$
-  The RHS is the$value of the quantity of consumption purchased by$1 at T.
-  It is therefore a *nominal* discount,         yielding the equality
$$Z(0,        T)=Z^{r e a l}(0,        T)\times\frac{\mathsf{C P I}(0)}{\mathsf{C P I}(T)}$$
-  Substitute to obtain the Fisher equation:
$$r(0,        T)=r_{r e a l}(0,        T)+\pi$$
## INFLATION RISK PREMIUM
-  Assume now inflation rate is not known and assume it is log-normal
$$\log\left(\frac{\mathsf{CPI}(T)}{\mathsf{CPI}(0)}\right)=x\sim\mathcal{N}(\pi\ T,        \sigma\pi^{2}\ T)$$
- This implies that the amount of consumption we can buy at $T$ is stochastic:
$$C(T)=\frac{\$1}{\mathsf{CPI}(T)}=\$1\times\frac{e^{-x}}{\mathsf{CPI}(0)}$$
-  Because C(T) is now risky,         we cannot discount it to today using the real bond
$$Z_{real}(0,         T) = e^{−r_{real}(0,        T)T}$$,         but we thus must add a risk premium κ.
-  Multiplying also by CPI(0) to obtain the dollar value,         we obtain
Dollar Present value of expected $C(T)=e^{-(r_{real}(0,        T)+\kappa)T}\times E[e^{-x}]$
$$=e^{-(r_{real}(0,        T)+\kappa)T}\times e^{-\pi T+\frac{1}{2}\sigma^{2}T}$$
- This is dollar present value of \$1 at $T$. Therefore it equals$ Z(0,        T)=e^{-r(0,        T)T}$.
$$r(0,        T)=r_{real}(0,        T)+\pi+\kappa-\frac{1}{2}\sigma\pi^{2}$$
## THE ECONOMICS OF FIXED INCOME INVESTMENTS
-  We now link all this to economic growth and agents' decisions.
-  We assume that investors have a utility function $U(C(t),         t)$. This is:
	- Decreasing with time: Eating soon is better than eating later.
	- Increasing in consumption: Eating more is better than eating less.
	- Concave: =⇒ Risk aversion: An amount of consumption that is *certain* is better than a fair bet to have more or less.
$$E\left[U(C)\right]<U\left(E[C]\right)$$
-  A widely used utility function is the Constant Relative Risk Aversion (CRRA):
$$U(C,        t)=e^{-\rho t}\frac{C^{1-\gamma}}{1-\gamma}$$
$-\rho=$time-preference parameter
$-\gamma=-CU^{\prime\prime}(C)/U^{\prime}(C)=$relative risk aversion parameter.
## OPTIMAL SAVINGS
## INVESTMENT CONTEXT 
- An investor has wage $w(0)$ today and a random amount $w(T)$ at $T$. 
- Then investor consumption plan is $C(0) = \frac{w(0)}{CPI(0)}$ and $C(T) = \frac{w(T)}{CPI(T)}$.
- Suppose the investor now has an unexpected bonus today of $100 dollars.
- ## Decision Scenarios 
- ### Scenario 1: Immediate Consumption
1. Spend $100 today and buy $\frac{\$100}{CPI(0)}$ amount of the consumption good,         which will procure him/her an additional amount of utility
   - $$U'(C(0),         0) \times \frac{\$100}{CPI(0)}$$
   ### SCENARIO 2: DEFERRED CONSUMPTION
1. Save the 100 dollars,         and buy $\frac{\$100}{Z(0,        T)}$ zero coupon bonds with maturity $T$. At that time,         the investor can buy $\frac{1}{Z(0,        T) CPI(T)}$ of the consumption good,         for an additional amount of utility
$$\frac{\$100}{Z\left(0,        T\right)}\frac{1}{\mathsf{CPI}(T)}U^{\prime}\left(C(T),        T\right)$$
## EQUILIBRIUM
-  Equilibrium requires the agent to be indifferent between 1 and 2. Because quantities at T are unknown,         the indifference condition is
$$U^{\prime}\left(C(0)\right)\times{\frac{\$100}{\mathsf{CPI}(0)}}=E\left[{\frac{\$100}{Z\left(0,        T\right)\mathsf{CPI}(T)}}U^{\prime}\left(C(T),        T\right)\right]$$
-  By reshuffling,         we obtain
$$Z(0,        T)=E\left[\frac{\mathsf{CPI}(0)}{\mathsf{CPI}(T)}\times\frac{U^{\prime}(C(T),        T)}{U^{\prime}(C(0))}\right]$$
- In aggregate,         real consumption $C(t)$ depends on *real*$\mathsf{GDP}\ Y(t)$.
-  Assume that inflation and real GDP growth have the joiny log-normal distribution
$$\left.\begin{pmatrix}\log\left(\frac{\mathsf{CPl}(T)}{\mathsf{CPl}(0)}\right)\\\log\left(\frac{Y(T)}{Y(0)}\right)\end{pmatrix}=\begin{pmatrix}x\\y\end{pmatrix}\thicksim\mathcal{N}\left(\begin{pmatrix}\overline{\pi}\\\overline{g}T\end{pmatrix}\right.,        \begin{pmatrix}\sigma\pi^2T&,        &\sigma\pi\sigma_g\rho_{g,        \pi}T\\\sigma\pi\sigma_g\rho_{g,        \pi}T&,        &\sigma_g^2T\end{pmatrix}\right)$$
## EQUILIBRIUM PRICES 
### CRRA UTILITY FUNCTION
- Substitute the CRRA utility function:
  - $$U'(C,         t) = e^{-\rho t} C(t)^{-\gamma}$$
- And use $C(t) = Y(t)$ for $t = 0,         T$ to find:
  - $$Z(0,         T) = E\left[ e^{-x} \times \frac{e^{-\rho T} Y(T)^{-\gamma}}{Y(0)^{-\gamma}} \right]$$
  - $$Z(0,         T) = E\left[ e^{-\rho T} \times e^{-x-\gamma y} \right]$$
  - $$Z(0,         T) = e^{-\rho T} \times e^{-\pi T -\gamma} + \frac{1}{2}(\pi^2 + \gamma^2 \sigma_g^2 + 2 \gamma \sigma_g \sigma_{g,        \pi})T$$
### NOMINAL RATE CALCULATION
- Thus,         the nominal rate is:
  - $$r(0,         T) = \left( \rho + \gamma g - \frac{\gamma^2}{2} \sigma_g^2 \right) + \left( \pi - \frac{1}{2} \pi^2 \right) - \gamma \pi \sigma_g \rho_{g,        \pi}$$
    - **Real Rate $r_{real}(0,         T)$**: $\rho + \gamma g - \frac{\gamma^2}{2} \sigma_g^2$
    - **Expected Inflation & Convexity**: $\pi - \frac{1}{2} \pi^2$
    - **Risk Premium**: $-\gamma \pi \sigma_g \rho_{g,        \pi}$
## THE ECONOMICS OF THE REAL RATE
-  Following the same steps as above but using TIPS zero-coupon bonds ZTIPS(0,         T)
instead of nominal bonds Z(0,         T) we obtain the real rate as:
$$r_{r e a l}(0,        T)=\rho+\gamma\overline{{{g}}}-\frac{\gamma^{2}}{2}\sigma_{g}^{2}$$
-  The real rate depends on:
1. Time preference $ρ$:
	- High $ρ$ implies investors want to consume today rather then tomorrow. They will sell their (real) bonds which increase their yield.
2. The expected growth rate of the economy $g$:
	- If $g$ is high we expect to be rich at $T$ and hence consume a lot then. High $γ$ implies we want "stable consumption" over time. Hence we want to borrow to consume more today,         which increases real rates.
3. The volatility of GDP growth $σg$
	- Higher economic risk implies a higher desire to save for the "rainy days". We buy more (real) bonds,         which push their prices up and decrease yields.
	- The higher the risk aversion γ and the more we want to save.
## INFLATION RISK PREMIUM
-  We found $$\text{inflation risk premium} = −γσπσ_gρ_{g,        π}$$
-  where $$ρ_{g,        π} = \text{Correlation (Inflation,         real GDP growth)}$$
+  Intuitively:
	+ If $ρ_{g,        π} <0 \rho_{g\pi}$ =⇒ high inflation occurs when real GDP is low
		+ nominal bond is devalued in recessions,         when people most need the money! 
		+ -very risky security =⇒ high risk premium =⇒ high long-term yield
-  Next figures show that the correlation $ρ_{g,        π}$ was negative until late 1990s. It then became closer to zero. And then became strongly positive around 2008.
-  In the meantime,         real GDP volatility σg and inflation volatility σπ declined.
-  All of these variation are bound to impact the risk premium.
## QUARTERLY REAL GDP GROWTH AND CPI INFLATION QUARTERLY REAL GDP GROWTH AND CPI INFLATION
 ![500](Lecture%20Note%203%20Understanding%20The%20Term%20Structure%20Of%20Interest%20Rates-20240405082451473.webp)
Data Source: Federal Reserve of St. Louis Data Source: Federal Reserve of St. Louis
## CORRELATION AND REAL GDP GROWTH AND CPI INFLATION VOLATILITIES. 
 ![500](Lecture%20Note%203%20Understanding%20The%20Term%20Structure%20Of%20Interest%20Rates-20240405233914662.webp)
## EXPECTED EXCESS RETURN: THE MARKET MODEL
-  Another way to understand the risk premium of nominal bonds is to look at its
variation with the stock market
-  Under the CAPM,         for instance
$$E\ [\text{ Excess Return Nominal Bond}] = β × E\ [\text{ Excess Return Market}]$$
-  Next figure shows the time variation in the correlation between stock and bonds,        
and the corresponding CAPM beta.
-  Why did the CAPM beta change over time?
- David and Veronesi (2013,         JPE): Time varying role of inflation signals
- Late 1970s/ early 1980s: *Fear of stagflation* (high inflation and low growth)
=⇒ high inflation shocks are bad news for the economy =⇒ both nominal bonds and stock drop
- Mid 2000s: *Fear of deflation* (low inflation and low growth)
=⇒ high inflation shocks are good news for the economy =⇒ nominal bonds drop but stock rise
## THE COVARIANCE BETWEEN STOCKS AND BONDS,         AND THE CAPM BOND
 ![500](Lecture%20Note%203%20Understanding%20The%20Term%20Structure%20Of%20Interest%20Rates-20240405234100364.webp)
Source: David and Veronesi (2016) "The Economics of the Comovement of Stocks and Bonds" in the Handbook of Fixed Income,         Pietro
## NOMINAL AND REAL STOCK BETAS
 ![500](Lecture%20Note%203%20Understanding%20The%20Term%20Structure%20Of%20Interest%20Rates-20240405234120813.webp)
Source: Caroline Pflueger (2024) "Back to the 1980s or Not? The Drivers of Inflation and Real Risks in Treasury Bonds"
Note: This figure shows betas from regressing quarterly ten-year Treasury bond excess returns onto quarterly US equity excess returns over five-year rolling windows for the period 1979. Q4-2022.Q3. Quarterly excess returns are in excess of three-month T-bills. Prior to 1999,         I replace US Treasury Inflation Protected (TIPS)
returns with UK ten-year linker returns. Bond excess returns are computed from changes in yields. Zero coupon yield curves from Gurkaynak,         Sack and Wright (2006,         2008) and the Bank of England. Vertical lines indicate 2001. Q2 and the start of the pandemic 2020. Q1.
Simsek (2022),         Bianchi,         Lettau and Ludvigson (2022a),         Bianchi,         Ludvigson and Ma (2022c)).
## MORE GENERAL FORMULAS
-  All previous formulas have "flat" term structures: r(0,         T) and rreal(0,         T) do not depend on T.
-  They can be generalized by assuming that expected inflation πt and expected GDP growth gt are time varying.
-  Using the continuous time methodology,         for instance,         we may assume
$$\begin{array}{r c l}{{}}&{{d\pi_{t}\;=\;(\alpha\pi-\beta\pi\pi_{t})d t+\sigma_{\pi}\;d W_{\pi}}}\\ {{}}&{{d\bar{g}_{t}\;=\;(\alpha_{g}-\beta_{g}\bar{g}_{t})d t+\sigma_{\bar{g}}\;d W_{\bar{g}}}}\end{array}$$
- Inflation and real GDP growth themselves are
$$\begin{array}{r c l}{{}}&{{d\log(\mathsf{CPI}_{t})\;=\;\pi_{t}d t+\sigma_{\pi}\;d W_{\pi}}}\\ {{}}&{{}}&{{d\log(Y_{t})\;=\;\bar{g}_{t}d t+\sigma_{g}\;d W_{g}}}\end{array}$$
-  The same argument as above has
$$Z(t,        T)=E_{t}\left[\frac{\mathsf{C P I}(t)}{\mathsf{C P I}(T)}e^{-\rho(T-t)}\left(\frac{Y(T)}{Y(t)}\right)^{-\gamma}\right]$$
## BOND PRICING FORMULAS
-  Solving the expectation,         we obtain
$$Z(t,        T)=e^{A(t,        T)-B(t,        T)\overline{{{\pi}}}_{t}-C(t,        T)\gamma\overline{{{g}}}_{t}}$$
-  where
$$B(t,        T)=\frac{1-e^{-\beta\pi(T-t)}}{\beta\pi};\ \ \ \ \ C(t,        T)=\frac{1-e^{-\beta_{g}(T-t)}}{\beta_{g}}$$
- and $A(t,        T)$ is a complicated function of maturity $(T-t)$ which includes risk premia and other terms further discussed below.
-  The nominal yield curve is then
$$r(t,        T)=\frac{-A(t,        T)}{T-t}+\frac{B(t,        T)}{T-t}\ \pi_{t}+\frac{C(t,        T)}{T-t}\ \gamma g_{t}$$
- A higher expected inflation increases nominal yield,         but differentially across maturities
- A higher expected real growth increases nominal yields,         but differentially across maturities
## THE FUNCTION A(T,        T)
## BOND PRICING WITH MULTIPLE RISKS AND CONVEXITIES
- $A(t,         T)$ represents the pricing kernel for a bond from time $t$ to maturity $T$,         incorporating various risks and convexity effects:$$
  A(t,         T) = \left( -\rho + \frac{1}{2} \pi^2 + \frac{1}{2} \gamma^2 \sigma_g^2 + \gamma \rho_{g} \sigma_{\pi} \sigma_g \right) (T - t)
  + \left[ \sigma_{\pi} \rho_{\pi \pi} \sigma_{\pi} \sigma_{\pi} + \gamma \sigma_g \rho_{\pi g} \sigma_{\pi} \sigma_g - \alpha_{\pi} + \frac{1}{2} \gamma^2 \sigma_{\pi}^2 + \frac{\gamma \rho_{\pi g} \sigma_{\pi} \sigma_g}{\beta_{\pi} + \beta_g} \right] \left( \frac{1}{\beta_{\pi}} \left( (T - t) - B(t,         T) \right) \right)
  + \left[ \sigma_g \rho_{g \pi} \sigma_{\pi} \sigma_g + \gamma \sigma_g \rho_{gg} \sigma_g - \alpha_g + \frac{1}{2} \gamma^2 \sigma_g^2 + \frac{\gamma \rho_{\pi g} \sigma_{\pi} \sigma_g}{\beta_{\pi} + \beta_g} \right] \left( \gamma \left( (T - t) - C(t,         T) \right) \right)
  - \frac{1}{4} \gamma^2 \sigma_{\pi}^2 B(t,         T)^2 - \gamma \rho_{\pi g} \sigma_{\pi} \sigma_g B(t,         T) C(t,         T)
  $$

 ![500](Lecture%20Note%203%20Understanding%20The%20Term%20Structure%20Of%20Interest%20Rates-20240405235507207.webp)

- Many risk premia are accounted for in bond pricing:
	  1. **Inflation risk premium**:$\gamma \sigma_{\pi} \rho_{\pi g} \sigma_g$. If$\rho_{\pi g} < 0 \Rightarrow Z(t,         T) \uparrow \Rightarrow r(t,         T) \uparrow$
	  1. **Expected inflation risk premium**:$\gamma \sigma_g \rho_{\pi g} \sigma_{\pi}$. If$\rho_{g,         \pi} < 0 \Rightarrow r(t,         T) \uparrow$
	  1. **Expected growth risk premium**:$\gamma \sigma_g \rho_{g g} \sigma_g$. If$\rho_{g,         g} < 0 \Rightarrow r(t,         T) \uparrow$
- Bond pricing also includes multiple convexity effects.
## THE SHORT-TERM RATE AND MONETARY POLICY INTERPRETATION
## INTEREST RATE FORMULATION AND MONETARY POLICY
### OVERNIGHT RATE FORMULA
- As we take the limit$T - t \rightarrow 0$,  we obtain the formula for the "overnight" rate:
  $$
  r_t = \rho + \gamma g_t - \frac{\gamma^2}{2} \sigma_g^2 + \pi_t - \frac{1}{2} \sigma_{\pi}^2 - \gamma \pi_t \sigma_g \rho_{\pi,         g}
  $$
  - **Real Rate$r_{real,        t}$**:$\rho + \gamma g_t - \frac{\gamma^2}{2} \sigma_g^2$
  - **Expected Inflation & Convexity**:$\pi_t - \frac{1}{2} \sigma_{\pi}^2$
  - **Risk Premium**:$-\gamma \pi_t \sigma_g \rho_{\pi,         g}$
### TAYLOR RULE
- The Federal Reserve is believed to follow the so-called "Taylor rule" in setting its target Federal Fund rate,  which specifies:
  $$
  r_t = \alpha + \beta_1(\text{output}_t - \text{potential output}) + \beta_1(\pi_t - \text{target inflation})
  $$
- The "forward looking" Taylor rule uses "expected inflation" and expected output to their realized values.
- The result above can be casted in terms of [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] actions:
  $$
  r_t = \alpha + \gamma(g_t - \text{potential output}) + (\pi_t - \text{target inflation})
  $$
  - where$\alpha = \rho - \frac{\gamma^2}{2} \sigma_g^2 - \frac{1}{2} \sigma_{\pi}^2 - \gamma \pi_t \sigma_g \rho_{\pi,         g} + \gamma \text{potential output} + \text{target inflation}$
## THE DYNAMICS OF THE REAL RATE
- From previous results and using Ito's formula,  the real rate follows a Vasicek model
$$d r_{r e a l,        t}=\beta_{g}\left(\bar{r}_{r e a l}-r_{r e a l,        t}\right)d t+\sigma_{r e a l}d W_{\bar{g}}$$
where
$$\overline{{{r}}}_{r e a l}=\rho+\gamma\frac{\alpha_{g}}{\beta_{g}}-\frac{\gamma^{2}\sigma_{\overline{{{g}}}}^{2}}{2};\quad\sigma_{r e a l}=\gamma\sigma_{\overline{{{g}}}}$$
- The real zero-coupon bond pricing formula is then
$$Z_{r e a l}(t,        T)=e^{\overline{{{A}}}(t,        T)-C(t,        T)r_{r e a l,        t}}$$
- where
$$\overline{A}(t,        T)=\left(\overline{r}_{real}^{*}-\frac{1}{2}\frac{\sigma_{real}^{2}}{\beta_{g}^{2}}\right)\left[C(t,        T)-(T-t)\right]-\frac{C(t,        T)^{2}\sigma_{real}^{2}}{4\beta_{g}}$$
- where$\overline{r}_{real}^{*}=\overline{r}_{real}-\gamma\sigma_{g}\sigma_{real}\rho_{\rho,        real}$
- The above result was found in
- The risk neutral process of the real rate is
$$d r_{r e a l,        t}=\beta_{g}\left(\overline{{{r}}}_{r e a l}^{*}-r_{r e a l,        t}\right)d t+\sigma_{r e a l}d W_{g}^{*}$$
## FITTING REAL VASICEK TO TIPS
- We can use TIPS again to extract the real zero coupon bond prices - The procedure is the same for nominal Vasicek (see TN 7),  except with the
additional difficulty that we may not know what the short-term real rate rreal,  t
actually is.
- One possibility is to estimate r*real,  t* as well together with other quantities.
- For instance,  fixing σ*real* = (estimated from the time series of real rates),
we estimate the following parameters for November 27,  2007:
$$\beta_{g}^{*}=0.0166,        \;\;\;\bar{r}_{r e a l}^{*}=0.1695,        \;\;\;r_{r e a l}=0.0046$$
- The fit is not as good as with the Extended Nelson-Siegel model in this case. - Next figure shows the fitted term structure of real rates.
 ![500](Lecture%20Note%203%20Understanding%20The%20Term%20Structure%20Of%20Interest%20Rates-20240406000703291.webp)
## CONCLUSIONS
- The term structure of interest rate depend on:
1. Expectation of future inflation 2. Expectation of future real growth 3. A whole set of risk premia
- Inflation risk premium
- Expected inflation risk premium - Expected growth risk premium
- Multi-factor models tend to fit well the term structure of interest rates
- The above setting with expected inflation and expected GDP growth can be generalized to any factors$ϕ_{1,        t},         ϕ_{2,        t}….$
- Moreover,  pricing formulas can be obtained using no-arbitrage methodologies,  as in TN 7.
----
# APPENDIX: DERIVATION OF TWO FACTOR MODEL

Define

$$\begin{array}{r c l}{{q}}&{{=}}&{{\log\left(\mathsf{C P I}\right)}}\\ {{y}}&{{=}}&{{\log\left(Y\right)}}\end{array}$$

so that

$$\begin{array}{r c l}{{d q}}&{{=}}&{{\overline{{{\pi}}}_{t}d t+\sigma_{\pi}d W_{\pi}}}\\ {{d y}}&{{=}}&{{\overline{{{g}}}_{t}d t+\sigma_{g}d W_{g}}}\end{array}$$

and recall$$d\overline{\pi}_{t}=\left(\alpha_{\pi}-\beta_{\pi}\pi_{t}\right)dt+\sigma_{\overline{\pi}}dW_{\overline{\pi}}$$$$d\overline{g}=\left(\alpha_{g}-\beta_{g}\pi_{t}\right)dt+\sigma_{\overline{\pi}}dW_{\overline{g}}$$

From the pricing equation we have

$$Z\left(t,        T\right)=E\left[e^{-\rho\left(T-t\right)-\left(q\left(T\right)-q\left(t\right)\right)-\gamma\left(y\left(T\right)-y\left(t\right)\right)}\right]$$

To be slightly more general,  consider the following case.

$$\begin{array}{l l l}{{Z\left(t,        T\right)}}&{{=}}&{{E\left[e^{-\rho\left(T-t\right)-\eta\left(q\left(T\right)-q\left(t\right)\right)-\gamma\left(y\left(T\right)-y\left(t\right)\right)}\right]}}\\ {{}}&{{=}}&{{e^{\eta q\left(t\right)+\gamma y\left(t\right)}E\left[e^{-\rho\left(T-t\right)}G\left(q\left(T\right),        y\left(T\right)\right)\right]}}\\ {{}}&{{=}}&{{e^{\eta q\left(t\right)+\gamma y\left(t\right)}V\left(q,        y,        \overline{{{\pi}}},        \overline{{{g}}},        t\right)}}\end{array}$$

When$\eta = 1$we have the case for nominal bonds. When$\eta = 0$we have the case of real bonds. When$\eta$is intermediate,  this can be considered a case in which inflation affects the utility function of agents directly. A case in the literature is the one of money illusion.

From the Feynman Kac formula,  we have that$V$satisfies

$$\rho V = V_t + V_q E[dq] + V_y E[dy] + V_{\pi} E[d\pi] + \frac{1}{2} V_{qq} E[dq^2] + \frac{1}{2} V_{yy} E[dy^2] + \frac{1}{2} V_{\pi\pi} E[d\pi^2] + \frac{1}{2} V_{qy} E[dq dy] + \frac{1}{2} V_{q\pi} E[dq d\pi] + \frac{1}{2} V_{y\pi} E[dy d\pi]$$

with final condition

- $V(q,         y,         \pi,         T,         T) = e^{-\eta q(T) - y(T)}$
We can conjecture the following
- $V(q,         y,         r,         t,         T) = e^{-\eta q(T) - y(T)}$
Taking the first derivatives
- $V_{\pi} = A'(t; T) - \eta B'(t; T) - C'(t; T) V$
- $V_q = -\eta V; V_{qq} = \eta^2 V; V_{qy} = \eta V; V_{q\pi} = \eta B'(t; T) V; V_g = \gamma C'(t; T) V$
- $V_y = -V; V_{yy} = V; V_{y\pi} = \gamma B'(t; T) V; V_{\pi\pi} = \gamma^2 C'(t,         T) V$
- $V_g = -\gamma B(t,         T) V; V_{gg} = \gamma^2 C(t,         T) V^2$
Substituting and deleting the common$V$
$$\rho = A'(t; T) - \eta B'(t; T) - \gamma C'(t; T) + \eta \pi - \eta \gamma \pi B(t,         T) - \gamma C'(t,         T) - (\alpha_{\pi} - \beta_{\pi}\pi) + \frac{1}{2} \eta^2 \sigma_{\pi}^2 + \frac{1}{2} \gamma^2 \sigma_g^2 + \eta \gamma \sigma_{\pi} \sigma_g \rho_{\pi g} + \eta B'(t,         T) \sigma_{\pi} \rho_{\pi\pi} + \gamma C'(t,         T) \sigma_g \rho_{gg} + \eta \gamma B(t,         T) \sigma_{\pi} \sigma_g \rho_{\pi g} + \gamma C(t,         T) \sigma_g^2$$
Factor out variables$\pi$and$g$:
$$\rho = -\eta B'(t; T) + 1 - \eta \gamma C'(t; T) + \eta \pi - \eta \gamma \pi B(t,         T) - \gamma C'(t,         T) + A'(t; T) + \frac{1}{2} \eta^2 \sigma_{\pi}^2 + \frac{1}{2} \gamma^2 \sigma_g^2 + \eta \gamma \sigma_{\pi} \sigma_g \rho_{\pi g} + \eta B'(t,         T) \sigma_{\pi} \rho_{\pi\pi} + \gamma C'(t,         T) \sigma_g \rho_{gg} + \eta \gamma B(t,         T) \sigma_{\pi} \sigma_g \rho_{\pi g} + \gamma C(t,         T) \sigma_g^2$$
This is satisfied for all values of$\pi$and$g$if and only if the following system is satisfied:
- $0 = B'(t; T) + 1 - B(t,         T)$
- $0 = C'(t; T) + 1 - C(t,         T)$
and
$$\rho = A'(t; T) - \eta B'(t,         T) - \gamma C'(t,         T) + \frac{1}{2} \eta^2 \sigma_{\pi}^2 + \frac{1}{2} \gamma^2 \sigma_g^2 + \eta \gamma \sigma_{\pi} \sigma_g \rho_{\pi g} + \eta B'(t,         T) \sigma_{\pi} \rho_{\pi\pi} + \gamma C'(t,         T) \sigma_g \rho_{gg} + \eta \gamma B(t,         T) \sigma_{\pi} \sigma_g \rho_{\pi g} + \gamma C(t,         T) \sigma_g^2$$
with final conditions
- $B(T,         T) = 0; C(T,         T) = 0; A'(T; T) = 0$
The first two ODEs have solutions
- $B(t,         T) = \frac{1 - e^{-\beta_{\pi}(T-t)}}{\beta_{\pi}}$
- $C(t,         T) = \frac{1 - e^{-\beta_g(T-t)}}{\beta_g}$
The last ODE has solution
$$A(t,         T) = \left(-\rho + \frac{1}{2} \eta^2 \sigma_{\pi}^2 + \frac{1}{2} \gamma^2 \sigma_g^2 + \eta \gamma \sigma_{\pi} \sigma_g \rho_{\pi g}\right)(T - t) + \left[\eta \sigma_{\pi} \rho_{\pi\pi} + \gamma \sigma_g \rho_{gg} - \rho \sigma_{\pi} \rho_{\pi g} + \frac{\eta \gamma \sigma_{\pi} \sigma_g}{\beta_{\pi} + \beta_g}\right] \frac{1}{\beta_{\pi}} \left((T - t) - B(t,         T)\right) + \left[\eta \sigma_g \rho_{\pi g} + \gamma \sigma_g \rho_{gg} - \rho \sigma_g \rho_{gg} + \frac{\gamma \sigma_g}{\beta_{\pi} + \beta_g}\right] \frac{1}{\beta_g} \left((T - t) - C(t,         T)\right) - \frac{1}{4} \gamma^2 \sigma_{\pi}^2 B(t,         T)^2 - \frac{1}{2} \gamma^2 C(t,         T)^2 - \frac{\eta \gamma \sigma_{\pi} \sigma_g \rho_{\pi g} B(t,         T) C(t,         T)}{\beta_{\pi} + \beta_g}$$
Setting$\eta = 1$provides the formula for$A(t,         T)$in the text. Moreover,  the case$\eta = 0$corresponds to the real bond,  obtaining
$$A_{real}(t,         T) = \left(-\rho + \frac{1}{2} \sigma_{\pi}^2\right)(T - t) + \left[\eta \sigma_{\pi} \sigma_g \rho_{\pi g} - \rho \sigma_{\pi} \sigma_g \rho_{\pi g}\right] + \left[\gamma \sigma_g \rho_{gg} - \frac{1}{2} \eta \gamma^2 \sigma_{\pi}^2\right](T - t) + \left[\frac{1}{2} \gamma^2 \sigma_g^2\right] - \frac{1}{2} \gamma^2 \sigma_g^2 C(t,         T)^2$$
