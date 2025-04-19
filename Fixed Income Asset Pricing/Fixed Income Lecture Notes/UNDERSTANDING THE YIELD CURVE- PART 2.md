---
cssclasses:
  - academia
linter-yaml-title-alias: Market's Rate Expectations and Forward rates
title: Understanding the Yield CurvePart 2
tags:
  - bond_risk_premia
  - expectations_hypothesis
  - forward_rates
  - rate_expectations
  - yield_curve
aliases:
  - Forward Rate Analysis
  - Market Rate Expectations
  - Yield Curve Part 2
key_concepts:
  - Break-Even Yield Changes
  - Curve Shape Influence
  - Expectations Hypothesis
  - Forward Rate Computation
  - Spot vs Forward Rates
---

# Understanding the Yield Curve-Part 2

MARKET 'S RATE EXPECTATIONS AND FORWARD RATES UNDERSTANDING THE YIELD CURVE: PART 2

## TABLE OF CONTENTS

Introduction Algebraic Relations Between Spot and Forward Rates
- Computation of Forward Rates
 - Forwards as Break-Even Rates e Break-Even Yield Changes for Curve-Flattening Positions The Expectations Hypothesis and the Yield Curve
 - How Do Rate Expectations Influence Today's Yield Curve Shape?
 - Expectations versus Risk Premia
- Alternative Versions of the Expectations Hypothesis and the Convexity Bias Empirical Evidence About Rate Expectations and Forward Rates
 - Forwards' Ability to Forecast Future Rate Changes and Risk Premia
- Survey Evidence
 - Investment Implications of the Empirical Findings
—
Appendix. Relations Between Forward Rates,  Expected Rate Changes and Expected Returns Literature Guide
—
## FIGURES

Spot Curve and Implied Spot Curve One Year Forward

1. Forward and Survey-Expected Yield Curve Steepening Six Months Ahead
2. Link Between Zeros' Rolling Yields and Break-Even Spot Rate Changes

Our recent report Overview of Forward Rate Analysis introduced a series on the theme Understanding the Yield Curve. It argued that three main forces determine the term structure of forward rates: the market's rate expectations; required bond risk premia; and the convexity bias. Separate reports discuss each of these forces. This report focuses on the impact of the market's rate expectations on the yield curve shape.

The impact of rate expectations on today's yield curve shape is best isolated by assuming that the pure [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] holds.

According to this hypothesis,  all government bonds have the same near-term expected return (that is,  all bond risk premia are zero). If the near-term expected returns are equal across maturities,  initial yield differences must offset any expected capital gains or losses that are caused by the market's rate expectations. For example,  if the market expects rates to rise and the long-term bonds to suffer capital losses,  these bonds must have an initial yield advantage over the one-period bond (to offset the expected capital losses). Therefore,  expectations of rising rates tend to make today's yield curve upward sloping. Conversely,  expectations of declining future rates tend to make today's yield curve inverted. In a similar way,  the market's expectations of future curve flattening or steepening influence the curvature of today's yield curve.

We emphasize the distinction between the statements "the forwards imply rising spot rates" and "the market expects rising spot rates." The first statement is related to the forward rates' role as break-even levels of future spot rates. By construction,  the spot rate changes that the forwards imply for the next period are such rate changes that would make all government bonds earn the same one-period return. Whenever the spot rate curve is upward sloping,  the forwards imply rising rates. That is,  rising rates are needed to offset long-term bonds' yield advantage. However,  it does not necessarily follow that the market expects rising rates. An upward-sloping spot rate curve also may reflect higher near-term required returns for long-term bonds than for the riskless one-period bond (so-called positive bond risk premia). The changes in spot rates that the forwards imply would be approximately equal to the expected spot rate changes only if the restrictive pure [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] were true.

In this report,  we also present empirical evidence about rate expectations and conclude that the pure [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] 1s,  in many ways,  at odds with historical experience. We show that forward rates are poor predictors of future spot rates. In fact,  long-term rates tend to move away from the direction implied by the forward rates. We also contrast the expectations "implied" in the forward rate structure to the expectations revealed in explicit surveys among bond market participants. The comparison suggests that forward rates are upward-biased measures of the market's rate expectations because the market appears to require higher expected returns for long-term bonds than for short-term bonds.

## ALGEBRAIC RELATIONS BETWEEN SPOT AND FORWARD RATES

This section reviews the relations between spot rates and forward rates and describes forward rates' role as break-even rates. The discussion in this section overlaps - but expands on - the discussion in Overview of Forward Rate Analysis. Readers familiar with the basic concepts in forward rate analysis may wish to move directly to the section "The Expectations Hypothesis and the Yield Curve."

Computation of Forward Rates A spot rate is the discount rate of a single future cash flow such as a zero-coupon bond (zero). A coupon bond can be viewed and valued as a bundle of zeros. Given the price P,  of an n-year zero,  the annualized n-year spot rate s,  can be computed as in Equation (1):!

$\begin{array}{c}\mbox{\rm n}-\mbox{\rm(1}+\mbox{\rm s}_{\rm n})^{\rm n}\end{array}$.

A forward rate is the interest rate for a loan between any two future dates,  contracted today. The rate may be explicit in the price of a traded forward contract or it may be implicit in today's spot rate curve. A zero's discount rate (a multiyear spot rate) can be decomposed into a product of one-year forward rates. Thus,  the spot rate is a geometric average of one-year forward rates:

(1 + s${}_{n}$)${}^{n}$ = (1+ f${}_{0,      1}$)(1 + f${}_{1,      2}$)(1 + f${}_{2,      3}$)… (1 + f${}_{n-1,      n}$),  (2)

where f,  .).,  is the one-year forward rate between maturities n-1 and n,  and fy

| = 8). If only one spot rate is known,  all forward rates cannot be computed. However,  if spot rates are known for each maturity,  a given term structure of spot rates implies a specific term structure of forward rates. For example,  if the m-year and n-year spot rates are known,  fp.y (the annualized n-m year rate m years forward) can be computed as in Equation

(3):

(1 + f${}_{\rm m,      n}$)${}^{\rm n\cdot m}$ = $\frac{(1\ +\ s_{\rm n})^{\rm n}}{(1\ +\ s_{\rm m})^{\rm m}}$.

Figure | presents a hypothetical spot rate curve and two series derived using Equation (3): the implied forward path of the constant-maturity one-year rate at various future dates and the implied spot curve at one future date,  one year hence. It is important to distinguish the curve of one-year forward rates in column B from the implied spot rate curve one year forward in column C. Unfortunately the terminology varies because both are sometimes called the forward curves. To clarify the relations between these curves,  Figure 2 shows the future years covered by ten spot rates (s; to sj9),  ten one-year forward rates (fo; to fo) and nine implied spot rates one year forward (f; to fj). The three curves are shown graphically in Figures 3 and 4.

lin practice. the spot rates are rarely inferred from the zero-coupon bond (STRIPS) prices because STRIPS differ A B C D=CSpot Rate One-Year Implied Spot Rate Implied Change Today Forward Rate One Year Forward in the Spot Rate Sy 6.00% fo. 6.00% fy 9 8.01% Af,  2.01%

sy 7.00 fy'o 8.01 13 «8.64 Afo 1.64

$3 7.75 fo 3 9.27 fy '4 9.09 Afg 1.34

sq 8.31 fz'4 10.02 fy'5 9.43 Afg 1.42

sa 9.05 {5 10.65 fy7 9.85 Afg 0.80

s7 9.29 fg7 10.72 fy'g «9.97 Af7 0.68

sg 9.47 tz 10.72 fy'g 10.06 Afg 0.59

sg 9.60 fg'g 10.67 fyig 10.12 Afg 0.52

Spot Rates Forwards as Break-Even Rates The numbers in column D in Figure 1 - the difference between the implied spot curve one year forward and today's spot curve - show that

"the forwards imply rising rates." How should this statement be interpreted? It does not necessarily mean that the market expects rising rates. Instead,  the forwards tell how much the spot curve needs to change over the next year to make all bonds earn the same holding-period return.

Recall that the holding-period return is a sum of a bond's initial yield and its capital gains or losses caused by yield changes. For example,  if today's spot curve is upward sloping,  longer-term bonds have a yield advantage over the one-period bond. To equate holding-period returns across bonds,  longer bonds have to suffer capital losses that offset their initial yield advantage. Forwards show exactly how much long-term rates have to increase to cause such capital losses. Stated in terms of rate levels instead of rate changes,  the implied spot rates one year forward (column C in Figure 1) are such future spot rates that would make all government bonds earn the same holding-period return over the next year.

(Moreover,  this same return must be the return of the one-year zero because it is already known today.) This break-even relation follows from Equation (3) by setting m = I and rearranging:

The left-hand side of Equation (4) is the return of buying an n-year zero at rate s,  today and selling it a year later at rate f,     ,  . The right-hand side is the riskless return of the one-year zero. Thus,  fj},  is the selling rate at which the n-year zero's holding-period return equals the return of the riskless asset. A numerical example illustrates the computation of the break-even rate f,  ». The numbers are from Figure |: a 6% one-year spot rate and a 7% two-year spot rate. Over the next year,  the return of a one-year zero is known to be 6%,  while the holding-period return of a two-year zero depends on its selling price at the end of the year - when its remaining maturity is one year. So,  the question is: "What should the one-year spot rate be one year hence to make the longer zero's holding-period return 6%?" A little math shows that the answer is 8.01%.

At this selling rate,  the longer zero's price would rise from 87.34 [=

100/(1.072)] to 92.58 [= 100/1.0801],  earning it 6% [= 92.58/87.34 - 1].

Thus,  the implied one-year spot rate one year forward,  f) = 8.01%,  is the level of future one-year rate that would make investors ex post indifferent to holding either of the two zeros.

It is worth reiterating that the forwards imply distinct yield changes for actual bonds and for constant-maturity rates. The forwards tell how much the yield of a given security - a longer-term bond - needs to change to offset an initial yield spread over the short-term rate. Alternatively,  the forwards tell how much a given point on the spot curve has to shift to equate holding-period returns across bonds,  In the example above,  the two-year zero's yield had to rise by 1.01% and the constant-maturity one-year spot rate had to rise by 2.01%. The 1% difference is due to the so-called "rolling down the yield curve" effect,  which we discuss shortly.

However,  first,  we provide a rule-of-thumb relation between initial yield spreads and break-even yield changes - and some economic intuition about this relation. We compute the implied two-year spot rate one year forward (f,  ) by equating the holding-period returns of the three-year zero and the one-year zero over the next year. (Recall that the value of the two-year spot rate after one year determines the holding-period return of what is today a three-year zero.) The left-hand side of Equation (5) is the approximate holding-period return of the three-year zero* (given a selling rate f; 3),  and the right-hand side is the holding-period return of the one-year zero.

$\rm S_{3}$ - $\rm{Dur}_{2}$ * ($\rm f_{1,    3}$ - $\rm S_{3}$) $\approx$ S${}_{1}$.

Note that f,  - $3 is not the three-year zero's actual subsequent yield change but the break-even yield change implied by the forward rates today.

Rearranging Equation (5) gives a rule-of-thumb that the break-even yield change for the three-year zero equals the yield spread divided by the bond's duration (at horizon): f} - $3 ~ (S3 - $;)/Durz. The following observation may be helpful. A large yield spread means that a purchase of a three-year zero financed by the sale of a one-year zero has a large positive "carry." The profit of this position is the sum of the yield carry

(sz - S;) and the capital gains or losses caused by the longer zero's yield changes. The position is bullish - it profits from falling rates and suffers from rising rates - but the positive carry provides a cushion against rising rates. The trade will lose money only if the two-year spot rate rises above f) in one year.

The break-even yield change f) - s3 shows how much the three-year zero's yield can rise before its carry advantage is offset. However,  if an upward-sloping yield curve remains unchanged,  the zero's yield will fall as it rolls down the curve (from s3 to sz). The capital gains from this rolldown tendency provide the three-year zero with an additional cushion against rising rates. The yield advantage component and the rolldown component can be added up to answer the question,  ''How much should the constant-maturity two-year spot rate change in the next year to make the three-year zero and the one-year zero earn the same return?" The answer is the implied,  or break-even,  change in the two-year spot rate over the next year (Af,  in column D in Figure 1):

$\Lambda$f${}_{2}=($f${}_{1,      3}$ - s${}_{3}$) + (s${}_{3}$ - s${}_{2}$) = f${}_{1,      3}$ - s${}_{2}$.

If only the spot rates in Figure | are known (s; = 6%,  s2 = 7%,  83 =

7.75%),  the yield advantage component is 0.875% [= (7.75 - 6.00)/2] and the rolldown component is 0.75% [= 7.75 - 7.00]. Thus,  Af,  = 1.625%

[= 0.875 + 0.75] and f;3 = 8.625% [= 7.00 + 1.625]. In words,  Af> is the difference between the implied two-year spot rate one year forward and the two-year spot rate today. Figure 3 illustrates graphically how this break-even yield change is decomposed into the break-even yield change needed to offset the carry (f,  - s3) and the rolldown yield change

(S3 - Sp).°

> The x-axis in Figure 3 (and in subsequent figures) is denoted as maturity. but it could as well be denoted as Macaulay duration because for zeros,  duration equals maturity. (This report does not emphasize the distinction between Macaulay duration and modified duration.)
An interesting relation exists between the curve of one-year forward rates and the implied spot curve one year forward (columns B and C in Figure
1). The steeper the former curve is,  the higher the latter curve must be. A
steep curve of one-year forward rates reflects a large rolling yield advantage for long-term bonds over the one-year bond. (We show in the Appendix that the one-year forward rate between maturities n-1 and n is equal to the n-year zero's rolling yield,  that is,  its one-year horizon return if the yield curve does not change. Thus,  the one-year forward rate f,  .).,  is equal to the spot rate s,  plus the rolldown return.) The larger this rolling yield advantage is,  the larger the yield increase required to offset it is,  and the higher the implied spot curve one year forward is (see the Appendix for details).
Break-Even Yield Changes for Curve-Flattening Positions We can extend the above analysis to more complex yield curve positions.
If the implied spot rates one year forward are realized,  all self-financed positions of government bonds will break even (earn a return of 0%). To break even,  any position with a positive carry will have to suffer capital losses; the forwards show how large spread changes over the next period would cause capital losses that offset the positive carry. Conversely,  any position with a negative carry will have to earn capital gains to break even; thus,  forwards imply spread changes that cause such capital gains. The following example clarifies this point.
Consider an investor who has a strong view,  with a one-year horizon,  that the spot curve will flatten between twoand four-year maturities. He could implement this curve flattening view by selling a three-year zero and by buying with the sale proceeds equal market values of a five-year zero and a one-year zero (which represents cash at horizon).® Such a "barbell-bullet"
trade is duration-neutral; thus,  the position is not sensitive to parallel changes in interest rates,  but it profits from the curve flattening. In a typical yield curve environment,  this trade earns a negative carry. That is,  when the spot curve is concave (steeper slope in the front end than in the long end),  the yield loss of moving from the three-year zero to the one-year zero will be greater than the yield gain of moving from the three-year zero to the five-year zero. For example,  in Figure | the negative carry is 39 basis points (0.5 * (6.00 - 7.75) + 0.5 * (8.73 - 7.75) = -0.88 +
0.49 = -0.39). For the trade to make money,  capital gains caused by future flattening of the spot curve must offset the negative carry.
The implied spot curve one year forward indicates the future level of the twoto four-year spread at which the trade - like any bond position with no net investment - exactly breaks even. This is the sense in which the forward rates "imply" flattening of the spot curve. More curvature in today's spot curve (a lower one-year rate or five-year rate for a given three-year rate) indicates less attractive terms for a flattening trade (a larger negative carry) and more implied flattening by the forwards
(which is needed to offset the negative carry). If today's spot curve were linear and not at all curved,  the flattening trade would give up no yield,  and,  consequently,  the forwards would imply no flattening of the spot curve. The break-even change in the twoto four-year spread would be zero. Finally,  if today's spot curve were convex,  the (barbell-bullet)
flattening trade would actually pick up yield,  and the forwards would imply steepening of the spot curve.
Note that the break-even change in the (constant-maturity) twoto four-year yield spread depends not only on the barbell's and the bullet's initial yields,  but also on their rolldown tendencies. When the spot curve is concave,  a rolldown return advantage augments the bullet's yield advantage. (The three-year zero rolls down a steeper part of the curve than the five-year zero,  and the one-year zero earns no rolldown return because it has zero duration at horizon.) Thus,  the rolling yield curve - that is,  the curve of one-year forward rates - is even more concave than the spot curve. The amount of implied flattening (which is needed to offset the negative yield carry and the difference in rolldown returns) really depends on the curvature of the rolling yield curve.
Figure 4 illustrates a typical spot curve and the corresponding curve of one-year forward rates (columns A and B in Figure 1). To evaluate the degree of curvature in these curves,  we draw a straight line between a pair of zeros with different maturities (durations). Each point on these lines represents a barbell portfolio of the two zeros. The curvature is measured by the vertical distance between a barbell portfolio and a duration-matched bullet bond. The curvature of the spot curve reflects the bullet-barbell yield spread,  while the curvature of the curve of one-year forward rates reflects the bullet-barbell rolling yield differential. The larger the vertical distance between the barbell and the duration-matched bullet is,  the more
"expensive" the barbell is in the sense that larger curve flattening is needed for the trade to break even. For example,  the initial rolling yield differential of 105 basis points at the three-year point (0.5 * 6.00 + 0.5 *
10.44 - 9.27 = -1.05) will only be offset if the twoto four-year spread narrows by 52 basis points in one year. The break-even spread change can be computed from column D in Figure 1: 112 - 164 = -52 basis points.
11% 11%
to L One-Year Forward Rates 10
aa eee Spot Rates oF "| Bullet-Barbell Balling Yield Differential 79
@ a eee D
= 8k (Oe 48 ®
x °_ 7] Bullet-Barbell Yield Spread ®
7h | 47
6 F 7 6
5 | l 1 l | 1! i 1 5
0 1 2 3 4 5 6 7 8 9 10
## MATURITY THE EXPECTATIONS HYPOTHESIS AND THE YIELD CURVE

How Do Rate Expectations Influence Today's Yield Curve Shape?

It is widely agreed that the market's rate expectations have a strong influence on the yield curve shape.' It is much more controversial to argue that such expectations are the only determinant of the yield curve shape.

However,  this is roughly what the pure [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] (PEH)

claims. This hypothesis assumes that all government bonds,  regardless of their maturity,  have the same near-term expected return. The motivation is that the market prices of bonds are set by risk-neutral traders,  whose activity eliminates any expected return differentials across bonds.

If all government bonds have the same near-term expected return,  any yield differences across bonds must imply expectations of future rate changes (so that expected capital gains or losses offset the impact of initial yield differences). For example,  if investors expect rates to rise and long-term bonds to lose value,  they require higher initial yields for long-term bonds than for short-term bonds,  making today's yield curve upward sloping. This kind of break-even argument is similar to the one used in the previous section,  except that now the expected (as opposed to realized) returns are being equalized across bonds.

Figure 5 illustrates how different types of expectations influence today's spot curve (if there are no expected return differences across bonds and if the convexity bias is ignored). Expectations of unchanged future rates lead to a horizontal spot curve,  rising rate expectations (for example,  a parallel shift of 100 basis points over one year) lead to a linearly upward-sloping spot curve and curve-flattening expectations lead to a concave curve shape.

A break-even type of argument can motivate each situation:

 - If the market expects no rate changes,  today's spot curve is flat because no expected gains or losses need to be offset by an initial yield spread.

 - If the market expects rates to rise in a parallel fashion,  longer-term bonds are expected to earn greater capital losses than shorter-term bonds.

An initial yield advantage must offset these expected losses. Because the expected capital losses are proportional to duration,  the yield advantage is also proportional to duration. Therefore,  today's spot curve 1s linearly upward sloping. In a similar way,  expectations of declining future rates make today's spot curve inverted.

7 This report takes the market's rate expectations as given. except that this footnote briefly discusses the economic determinants of these expectations. An old Wall Street adage - that the central bank determines the level of

 - If the market expects the curve to flatten in the future,  barbells and other curve-flattening positions are expected to earn capital gains. An initial negative carry must offset these expected capital gains. Therefore,  today's spot curve is concave,  and barbell portfolios have lower yields and rolling yields than duration-matched bullet bonds. In a similar way,  expectations of future curve steepening tend to make today's spot curve convex,  and barbells have higher yields than bullets.

11% 11%

10 —

= 4 10

gb Expected Yield Increase and Curve Flattening 9

2 - BY

o 8 Fr = 8 >

cq. Expected Parallel Yield Increase ®

7 Pr 47

6 No Change Expected in Level or Slope 6

5 J! | | 5

0 2 4 6 8 10

Expectations versus Risk Premia We emphasize that the PEH is nothing more than a hypothesis. Much empirical evidence shows that the extreme assumption of equal expected returns across bonds is false. Thus,  it is unreasonable to assume that an upward-sloping yield curve reflects only expectations of rising rates. It is at least as reasonable to assume that such a shape reflects only the premium that investors require for holding long-term bonds. (We ignore the convexity bias until the next subsection.) In this light,  the numbers in Figure 1 (s; = 6%,  Ss) = 7%,  f) = 8.01%) can be interpreted in two ways.

- According to the PEH,  the oneand two-year zeros have the same expected return over the next year. The return of the shorter zero is known to be 6%. The one-year return of the longer zero will be 6% only if its yield rises to 8.01% (thereby causing capital losses that offset its initial yield advantage). Thus,  f| reflects the expected level of the one-year spot rate one year hence.
 - According to the risk premium hypothesis,  f;.. reflects only the longer zero's one-year expected return and no expected rate changes. Recall that one-year forward rates measure the zeros' one-year expected returns given no change in the yield curve. If the spot curve is unchanged in a year,  the longer zero earns the initial 7% yield plus a 1.01% rolldown return when its yield declines to 6%.
In both cases,  the longer zero will earn the same return over a two-year period (14.49%); this return is known from its 7% annual yield today.
However,  in the first case the zero is expected to earn 6% in year one and
1.01% in year two,  while in the second case,  it is expected to earn 8.01%
in year one and 6% in year two.
Let us put this example in a broader context. We show in the Appendix
(Equation (13)) that,  as a linear approximation,  the yield change implied by the forwards can be split to an expected change in the n-1 year spot rate over the next year,  E(As,  .;),  and a bond risk premium (that is,  the expected return of an n-year bond over the next year in excess of the riskless one-year rate,  BRP,  ):
$\rm f_{1,      n}$ - $\rm S_{n}\approx E(\Delta s_{n})$ + BRP${}_{n}$/(n-1)
Equation (7) helps in contrasting different assumptions about the yield curve behavior. For better understanding,  one can think of f|.,  - Sy. loosely as one measure of the yield curve steepness. Thus,  the equation says that the curve steepness reflects market's future rate expectations,  or expected return differentials across bonds,  or some combination. The two cases above make two polar assumptions:
e The PEH assumes that BRP = 0. Thus,  all government bonds have the same near-term expected return as the riskless asset,  and forwards reflect only the market's expectations of future rate changes.
 - The risk premium hypothesis assumes that E(As,  .,  ) = 0. Thus,  forwards reflect only the near-term expected return differentials across bonds.
In reality,  of course,  neither polar assumption is correct; the truth lies somewhere between.' Fortunately,  the interpretation of forward rates as break-even rates is valid whether forward rates reflect the market's expectations of future rates,  risk premia,  or both. We will present some empirical evidence later that indicates that if one of the two polar assumptions has to be chosen,  the risk premium hypothesis is the more realistic one.
Alternative Versions of the Expectations Hypothesis and the Convexity Bias The bond risk premium is not the only reason that the forward rates are not equal to expected spot rates. Another reason is the so-called convexity bias. The PEH is often identified with two statements: "All bonds have the same near-term expected return" and "forward rates are optimal (unbiased)
forecasts of future spot rates." It turns out that these two statements are not exactly consistent with each other. That is,  two distinct versions of the PEH exist; the local [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] is associated with the first statement and the unbiased [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] is associated with the second statement. The difference between these hypotheses is related to convexity,  that is,  the nonlinearity in a bond's price-yield curve.
We only try to give here some intuition about the convexity bias. Consider a situation in which the spot curve and the implied forward curves are flat at the 6% level. Because there are no yield differences across bonds and no rolldown,  will the expected returns be equal across bonds? No,  they will not,  because some bonds are more convex than others. Positive convexity can only increase expected return for a given yield; thus,  the longerduration bonds,  which exhibit greater convexity,  will have higher expected returns. Therefore,  even though forward rates equal expected spot rates in this example,  all bonds will not have the same expected return. We refer to the impact of convexity on the yield curve shape as the convexity bias
To conclude,  in this section we have described how the market's rate expectations influence the shape of the yield curve,  but we also emphasized that expectations are not the only determinants of the curve. The statement
"forward rates show the market's expectations of future spot rates" is valid only if the bond risk premia and the convexity bias can be ignored.
Ordinarily they cannot. In general,  it is difficult to say whether the yield curve's upward slope reflects rising rate expectations or positive bond risk premia. It is equally difficult to say how much of the curvature in the yield curve reflects the market's flattening expectations and how much of it reflects the convexity bias. We will discuss these issues in the next section.
## ICAL EVIDENCE ABOUT RATE EXPECTATIONS AND FORWARD

Do forwards reflect the market's rate expectations,  required risk premia or both? Are forward rates or current spot rates better forecasts of future spot rates? Are expected bond returns equal across maturities,  as the PEH asserts? In this final section,  we address these questions and evaluate empirically what we really know about forward rates and the market's expectations. (We ignore nonlinear effects such as convexity bias and,  thus,  make no distinction between the different versions of the PEH.)

Because expectations are not observable,  academic researchers have studied these questions using two different methods. Many authors examine the forward rates' ability to predict actual subsequent rate changes and required bond risk premia. Others take a more direct approach and use surveys of interest rate forecasts to proxy for the market's rate expectations.

Forwards' Ability to Forecast Future Rate Changes and Risk Premia We first examine forwards' ability to forecast future spot rate changes and realized future bond risk premia. The underlying idea is that the market's expectations are rational,  and any forecast errors are "noise" that should wash out during the sample period. If the PEH holds,  forwards are optimal predictors of future spot rates. (By "optimality,  " we mean here unbiasedness. The forwards do not need to be very accurate predictors,  but they should not contain systematic forecast biases.) However,  if the risk premium hypothesis holds,  forwards are optimal predictors of near-term expected bond returns,  and the current spot curve is the optimal forecast for future spot curves. The implications of the two extreme hypotheses are summarized in Figure 6.

Figure 7 reports the correlation of the forward-spot premium (fn-1.n - $1 OF

FSP,  ; see Equation (16) in the Appendix),  first,  with the subsequent change in the n-1 year spot rate Asj.; over the next month and,  second,  with the subsequent realized bond risk premium (realized BRP,  or the monthly holding-period return of an n-year zero in excess of the one-month rate).

For better understanding,  one can view FSP,  as another measure of the yield curve steepness. We compute these correlations for six maturities

(threeand six-month bills and estimated two-,  three-,  four-,  and five-year zeros) using monthly Treasury market data from the 1970-94 period.

Pure Expectations Hypothesis

Risk Premium Hypothesis

What Is the Information in Forward Rates? Market's Rate Expectations Required Risk Premia What Future Events Should Forward Rates Forecast? Future Rate Changes Near-Term Return Differentials Across Bonds What Is the Best Forecast of an n-Year Zero's One-Period Forward Rate (f,     ),  One-Period Expected Return? One-Period Riskless Rate that is,  the Zero's Rolling Yield)

What ts the Best Forecast of Next Period's Spot Curve? Implied Spot Curve One Year Forward Current Spot Curve CORR(FSP,     As,  ) Positive 0

CORR(FSP,     Realized BRP.) 0 Positive

3 Month 6 Month 2 Year 3 Year 4 Year 5 Year CORR(FSP),  ASp-4) 0.12 0.05 -0.05 -0.07 -0.11 -0.08

CORR(FSP,     ,  Realized BRP,     ) 0.37 0.22 0.17 0.17 0.19 0.15

Source: Center of Research for Security Prices at the University of Chicago and Salomon Brothers Inc.

The first row in Figure 7 provides the main finding. The forward-spot premia are negatively correlated with future changes in long-term rates. That is,  when the yield curve is upward sloping,  long-term rates do not tend to increase,  as the PEH says they should,  to offset their initial yield advantage over short-term bonds. Instead,  long-term rates tend to decline,  causing capital gains that augment the long-term bonds' yield advantage.!° Thus,  it is not surprising that the forward-spot premia are positively correlated with future bond risk premia (the second row). In the front end of the curve,  forwards tend to at least predict the rate direction correctly. Therefore,  the optimal forecast of a future spot rate is a weighted average of the current spot rate and the implied spot rate one period forward. In the long end,  forwards appear to be inverse indicators of future rate changes. Overall,  Figure 7 suggests that the yield curve steepness tends to reflect more near-term expected return differentials across bonds than the market's rate expectations. These findings are clearly inconsistent with the pure [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]],  but they may be explained by time-varying bond risk premia.

We can relate our empirical analysis to the so-called persistence factors

(PFs) that reflect the expectation that spot rates will remain at their current levels.!! The two polar assumptions that we presented earlier - the PEH

and the risk premium hypothesis - are associated with PFs 0 and 1. A

zero value means that today's spot curve is expected to give way to the implied spot curve one period forward. A unit value means that today's spot curve is expected to remain unchanged (that is,  to persist). Thus,  if PF

equals zero,  forwards are optimal (unbiased) forecasts of future spot rates,  and if PF equals one,  current spot rates are the optimal forecasts. The PF

can be estimated empirically by the slope coefficient in a regression of the annualized realized bond risk premium on the forward-spot premium (see Equation (16) in the Appendix). The value of the PF tells by how much an asset's near-term expected return increases for a given increase in the forward-spot premium. We find that for maturities beyond one year,  for which forwards tend to give the wrong signal about future rate changes,  the estimated PFs are greater than one (1.4 - 2.3). For maturities less than one year,  for which forwards at least predict the rate direction correctly,  the estimated PFs are smaller than one (about 0.8). These findings are consistent with the signs of the correlations in Figure 7.

Survey Evidence A more direct approach is to use surveys of bond market analysts' interest rate forecasts to proxy for the market's rate expectations. The survey forecasts can be compared with forward rates; any difference should reflect a required risk premium.

We use the Wall Street Journal's semiannual survey of Wall Street economists and analysts conducted 27 times between December 1981 and December 1994. In each survey,  the participants predict the three-month bill rate and the 30-year bond yield at the end of the next June

(December). We compute the expected rate change by subtracting the mid-December (June) rate from the survey median.!2 We then compare these survey forecasts with the yield changes that the forwards imply and with actual subsequent yield changes over each 6.5-month period. The forward yield changes are computed based on the on-the-run Treasury yield curve in mid-December (June). Figure 8 shows the main results separately for the six-month change in the bill rate and the bond rate and their spread.

A. Average Size of the Forecast Error (Mean Absolute Deviation)

Forward Survey No Change A 3-Month 1.21 1.03 1.03 A 30-Year 0.88 1.00 0.86 A Spread (30 Year-3 Month) 0.91 0.75 0.81

B. Correlations Between Rate Changes Forward/Survey Forward/Actual Survey/Actual A 3-Month 0.43 0.03 0.26

A 30-Year 0.23 -0.01 -0.22

A Spread (30 Year-3 Month) 0.21 0.33 0.28

C. Average (Expected) Rate Change Over Six Months Forward Survey Actual A 3-Month +0.80 -0.26 -0.25

A 30-Year +0.10 -0.14 -0.24

A Spread (30 Year-3 Month} -0.70 +0.12 +0.01

Panel A examines the accuracy of the forwards,  the surveys and the no-change predictions by showing the average magnitude of the difference between the predicted yield change and the subsequent yield change. (Note that the no-change prediction is consistent with the risk premium hypothesis and that its forecast error is simply the actual yield change.)

Panel A shows that all forecasts are quite poor; average errors are of the same order of magnitude as the average yield changes,  roughly 100 basis points in six months. Another observation is that the forwards have somewhat larger forecast errors than the no-change predictions,  suggesting that the current spot curve predicts future spot curves better than the implied forward curve does. Given the small number of observations,  these differences are not statistically significant. A more serious problem regarding the forwards' predictive ability is that long-term rates tend to move away from the forwards,  not toward them - recall the evidence in Figure 7. However,  the negative correlation is quite small in this sample

(-0.01),  and the expert forecasters have been even worse predictors of long-rate changes (the correlation is -0.22 in panel B). Panel C is the most interesting part of Figure 8. It reveals a systematic bias in the forward rates; during the 13-year period,  the forwards typically implied rising short-term and long-term rates and a flattening yield curve,  unlike the survey forecasts and the actual rate changes.

Why are the forwards' implied rate predictions higher than survey forecasts and actual rate changes? A possible explanation is that the market requires a positive risk premium for holding the long-term bond. In fact,  we can use the survey forecasts of future rates to compute a direct estimate of the average bond risk premium. The difference between the yield change implied by the forwards and the expected future yield change is approximately proportional to the risk premium. The 106 [80 - (-26)]basis-point difference for the three-month bill translates to an average annualized risk premium of 53 basis points.!3 A similar calculation shows that the 24 [10 - (-14)]-basis-point difference for the 30-year bond translates to an average annualized risk premium of 480 basis points. These findings suggest that positive bond risk premia exist.

Figure 9 shows how consistently the forward prediction of the three-month rate exceeds the survey forecast. Both series move together with the actual three-month bill rate (which is typically between the two series). As explained above,  the difference between the two series is proportional to a bond risk premium. Figure 9 shows that this risk premium is not constant over time. Its time-variation appears economically sensible in that the premium is exceptionally high around the

1982 recession and after the 1987 stock market crash when a recession was widely expected. The premium was quite low in 1993,  despite the yield curve steepness,  and it rose substantially in 1994.14

market price of convexity.

1.0% 1.0%

) Survey &

o 0.5 rm /N \ Pa <

x= \--*" _—_—" \ ac oO

oO / _—ae / ed ©

3 0.0 \ 4 NY ZN =

2 @

a5 05 + S

£ 3

Cc a

< 10 D

on o

2 45 Forward 4

: 9

> ~ -2.0 x
3 3
-25 1 i i 1 1 J lL l l i 1 il 1 1 1 2.5
investment Implications of the Empirical Findings Overall,  the empirical evidence is much more consistent with the risk premium hypothesis than with the pure [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]]. Forwards tell us more about near-term expected return differentials across bonds than about future rate changes. If either today's spot curve or the implied spot curve one period forward must be used as a predictor of the next period's spot curve,  the evidence supports the use of the former as the neutral base case. These findings have obvious investment implications; rolling yield differentials between bonds or the corresponding break-even yield changes provide potentially useful relative value indicators for duration-extension trades. Intuitively,  because the rate changes that forwards imply are not realized,  on average,  bonds with high rolling yields tend to keep their yield and rolldown advantage. Similarly,  break-even changes of yield spreads may be good relative value indicators for duration-neutral yield curve positions such as barbells versus bullets. In later reports,  we will evaluate the historical performance of these indicators and traditional cheapness indicators such as yield spreads.
More generally,  the empirical failure of the pure [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] is good news for active managers. If all bond positions always had the same near-term expected returns,  it would be extremely difficult to add value.
Therefore,  our findings provide some empirical justification for yield-seeking active investment strategies.
## N FORWARD RATES,  EXPECTED RATE RNS

This Appendix shows how forward rates are related to expected spot rate changes and expected holding-period returns and how one-year forward rates are related to implied spot rates one year forward. These relations are linear approximations that ignore nonlinear effects such as the convexity bias. Equation (3) shows how the annualized forward rate between maturities m and n is related to mand n-year spot rates. By taking a first-order approximation of both sides of this equation and rearranging,  we get a nice linear relation:

NSy —_ MSm finn ~ n-m - (8)

To compute the implied spot curve one year forward,  we set m = I:

$$\sim\frac{\rm n-1}{\rm n-1}.\tag{9}$$

Equation (10) shows the n-year zero-coupon bond's holding period return over the next period (h,  ). The zero earns its initial yield,  s,     plus a_ capital gain which is approximated by the product of the zero's duration at horizon (n-1) and its yield change.

$\rm h_{n}\approx s_{n}+(n-1)\ ^{*}\ (s_{n}-s_{n-1}^{*})\,      $ (10)

where s° is the next period's rate (at which the bond is sold). Now we substitute Equation (10) into Equation (9),  noting that ns,  = s,  + (n-1) * s,  :

$$\mathrm{f}_{1,      n}\approx\frac{\mathrm{h}_{n}+(n-1)\ *\ \mathrm{s}_{n-1}^{*}-\mathrm{s}_{1}}{n-1}=\mathrm{s}_{n-1}^{*}+\frac{\mathrm{h}_{n}-\mathrm{s}_{1}}{n-1}.\tag{11}$$

We call h,  - s; (the one-year holding-period return in excess of the short-term rate) the realized risk premium of the n-year zero. Because the equality in Equation (11) holds for realized returns,  it also should hold in expectations if they are rational. Thus,

$$\mathrm{f}_{1,      n}\approx\mathrm{E}(s_{n-1}^{*})+\frac{\mathrm{B}\mathrm{P}_{n}}{n-1}\,     ,      \tag{12}$$

where BRP,  (the bond risk premium) is the expected holding-period return of an n-year zero in excess of the riskless one-year rate or E(h,  - $}).

Subtracting s,  .; from both sides of Equation (12) gives the break-even change in the n-1 year spot rate:

$$\Delta{\rm f}_{{\rm n}-1}\equiv{\rm f}_{1,      {\rm n}}\ -\ {\rm s}_{{\rm n}-1}\ \approx{\rm E}(\Delta{\rm s}_{{\rm n}-1})\ +\ \frac{{\rm BRP}_{{\rm n}}}{{\rm n}-1}\,      \tag{13}$$

; is the difference between two rates that are known

where As,  ; = S"n-1 - Sp-1. (Note that As,  .; denotes actual rate change over time,  whereas Af,  today.) Equation (13) states that the break-even change in the n-1 year spot rate,  implied by the forwards,  is equal to the sum of the expected change in the n-1 year spot rate over the next year and the bond risk premium of the n-year zero (divided by n-1). The information in the forward rates reflects either expected future yield changes,  or expected bond risk premia,  or some combination of the two.

Similarly,  we can compute an approximation of the one-year forward rates

(m = n-1 in Equation (8)):

$$\int_{\rm n-1,      n}\approx\Pi{\rm S}_{\rm n}\ -\ (\eta-1)\ ^{\ast}\ {\rm S}_{\rm n-1}={\rm S}_{\rm n}+(\eta-1)\ ^{\ast}\ ({\rm S}_{\rm n}\ -\ {\rm S}_{\rm n-1}).\tag{14}$$

Now we substitute Equation (10) into Equation (14):

f${}_{\rm n-1,    n}\approx$ (n-1) * ($\Delta$s${}_{\rm n-1}$) + h${}_{\rm n}$.

If the yield curve remains unchanged,  the first term in the right-hand side of Equation (15) equals zero and fy). = hy. In other words,  the one-year forward rate is equal to a zero's holding-period return given an unchanged yield curve,  or its rolling yield. Equation (14) shows that such return 1S

equal to a sum of the initial yield and the rolldown return (the zero's duration at horizon (n-1) multiplied by the amount that the zero rolls down the yield curve as it ages).

We can subtract s,  from both sides of Equation (15) to get the forward-spot premium (f,  .,  - $; or FSP,  ) and realized risk premium

(h,  - $1),  and then take expectations:

$${\rm FSP}_{\rm n}\equiv{\rm f}_{\rm n-1,      n}\ -\ {\rm s}_{1}\ \approx\ ({\rm n-1})\ ^{*}\ {\rm E}(\Delta{\rm s}_{\rm n-1})\ +\ {\rm BRP}_{\rm n}.\tag{16}$$

A comparison of Equations (13) and (16) shows that the forward-spot premium is proportional to the break-even yield change:!> FSP,  =

(n-1) * Af,  .;. Intuitively,  FSP,  measures the rolling yield advantage of the n-year zero over the riskless one-year zero,  while Af,     _,  shows how large change in the n-1 year spot rate is needed to offset such a rolling yield advantage. The ratio of proportionality is n-1 because the product of duration-at-horizon and the break-even yield change gives a capital loss that is as large as the rolling yield advantage. Figure 11 illustrates this relation. The top panel shows a spot curve and the corresponding curve of one-year forward rates (rolling yields) which increase linearly with maturity. If the spot curve remains unchanged over the next year,  the ten-year zero earns its annual yield 10.50% as well as a rolldown return of

4.50% (nine years end-of-horizon duration times 50 basis points rolldown yield change). Thus,  its holding-period return is 15% if the spot curve does not change over the next year - as shown by the right-most point on the curve of one-year forward rates. The ten-year zero has a 9% rolling yield advantage over the one-year zero. The lower panel shows the implied spot curve one year forward (together with the same spot curve as in the top panel); that is,  the break-even levels of future spot rates that would offset the longer-term bonds' rolling yield advantage over the one-year zero. The nine-year spot rate needs to increase by 100 basis points to cause a 9%

capital loss for today's ten-year zero (whose maturity is nine years after a year). Similar calculations for various-maturity zeros show that a parallel increase of 100 basis points would make all government bonds earn the same 6% holding-period return as the one-year zero. (If convexity effects are taken into account,  the break-even yield shift would not be exactly parallel.)

14% F | 14%

7 One-Year Forward Rates >) 12

@ ee D

@o 10 - ---°°°4 10 8

cc Deer" @

8 Fr Dee aan 4 8

oe Spot Rates

6 Fr "" 46

|! | 1 | 1 J i |

0 1 2 3 4 5 6 7 8 9 10

Maturity

14% - =" 14%

12 + 1

o Implied Spot Rates One Year Forward x

6 1J0F 10 ®

am)

gb - 8

a Spot Rates

6 F a + 6

The link between initial rolling yields and the break-even changes in the spot rates is straightforward because the relationship is mathematical. If today's spot curve and the rolling yield curve were flatter than in the top panel in Figure 11,  a smaller increase in the spot curve would be needed to offset the long-term bonds' rolling yield advantage over the one-year zero,  and the forwards would imply smaller rate increases. If today's spot curve were inverted,  long-term bonds would even have lower yields and rolling yields than the one-year zero,  and the forwards would imply a rate decline to offset the long-term bonds' rolling yield disadvantage. If today's spot curve were upward sloping and concave (the "typical" shape; see Figure 4,  which corresponds to the top panel in Figure 11),  the forwards would imply rising rates and flattening curve to offset the rolling yield advantage of long-term bonds and steepening positions (bullets versus barbells; see Figure 3,  which corresponds to the lower panel in Figure 11).

Broad Surveys Shiller,  "The Term Structure of Interest Rates,  " Handbook of Monetary Economics,  1990.

McEnally and Jordan,  "The Term Structure of Interest Rates,  " Handbook of Fixed Income Securities,  1995.

On the Alternative Versions of the Pure Expectations Hypothesis and the Convexity Bias Cox,  Ingersoll,  and Ross,  "A Re-examination of Traditional Hypotheses about the Term Structure of Interest Rates,  " Journal of Finance,  1981. Campbell,  "A Defense of Traditional Hypotheses about Term Structure of Interest Rates,  " Journal of Finance,  1986.

On the Forward Rates' Ability to Predict Future Rate Changes and Future Bond Risk Premia.

Shiller,  Campbell and Schoenholtz,  "Forward Rates and Future Policy:

Interpreting the Information in the Term Structure of Interest Rates,  "

Brooking Papers on Economic Activity,  1983.

Fama,  "The Information in the Term Structure" Journal of Financial Economics,  1984.

Mankiw,  "The Term Structure of Interest Rates Revisited,  " Brooking Papers on Economic Activity,  1986.

Fama and Bliss,  "The Information in Long-Maturity Forward Rates,  "

American Economic Review,  1987.

Hardouvelis,  "The Term Structure Spread and Future Changes in Long and Short Rates in the G7 Countries: Is There a Puzzle?,  " Journal of Monetary Economics,  1994.

Campbell,  "Some Lessons from the Yield Curve,  " National Bureau of Economic Research working paper #5031,  1995.

On Comparing Survey Expectations and the Forward Rates' Implied Expectations of Future Rates.

Froot,  "New Hope for the Expectations Hypothesis of the Term Structure of Interest Rates,  " Journal of Finance,  1989.

Hafer,  Hein and MacDonald,  "Market and Survey Forecasts of the Three-Month Treasury Bill Rate,  " Journal of Business,  1992.

DeBondt and Bange,  "Inflation Forecast Errors and Time Variation in the Term Premia,  "" Journal of Financial and Quantitative Analysis,  1992.