---
linter-yaml-title-alias: OVERVIEW OF FORWARD RATE ANALYSIS
title: Understanding The Yield CurvePart 1
tags:
  - bond_risk
  - convexity_bias
  - forward_rates
  - interest_rates
  - yield_curve
aliases:
  - Salomon Brothers
  - Term Structure
  - Yield Curve Analysis
key_concepts:
  - Bond risk premium
  - Convexity bias impact
  - Forward rate analysis tools
  - Par, spot, forward rates
  - Rate expectations influence
---

Salomon Brothers
ANITI ILMANEN

# Understanding The Yield CurvePart 1
## UNDERSTANDING THE YIELD CURVE: PART 1

Introduction 1
Computation of Par,  Spot and Forward Rates 1
Main Influences on the Yield Curve Shape 5

- Rate Expectations 5
- Bond Risk Premium 6
- Convexity Bias 8
- Putting the Pieces Together 10
- Using Forward Rate Analysis in Yield Curve Trades 11
- Forwards as Break-Even Rates for Active Yield Curve Views 14
- Forwards as Indicators of Cheap Maturity Sectors 13
- Forwards as Relative Value Tools for Yield Curve Trades 14
Appendix A. Notation and Definitions Used in the Series Understanding the Yield Curve 16
Appendix B. Calculating Spot and Forward Rates When Par Rates are Known 17
Appendix C. Relations Between Spot Rates,  Forward Rates,  Rolling Yields,  and Bond Returns 18

## FIGURES

1. Par,  Spot and One-Year Forward Rate Curves 3
1. Yield Curves Given the Market's Various Rate Expectations 6
1. Theoretical and Empirical Bond Risk Premium 7
1. Convexity and the Yield Curve 9
1. Current and Forward Par Yield Curves as of 31 Mar 95 12
1. Historical Three-Month Rates and Implied Forward Three-Month Rate Path,  as of 30 Dec 94 and 31 Mar 95 12
1. Par Yields and Three-Month Forward Rates,  as of 2 Jan 90 13
1. On-the-Run Yield Curves,  as of 30 Dec 94 and 31 Mar 99 15
1. Par,  Spot and One-Year Forward Rates 18
In recent years,  advances have been made in the theoretical and the empirical analysis of the term structure of interest rates. However,  such analysis is often very quantitative,  and it rarely emphasizes practical investment applications. There appears to be a need to bridge the gap between theory and practice and to set up an accessible framework for sophisticated yield curve analysis. This report serves as an overview of a forthcoming series of reports that will examine the theme Understanding the Yield Curve. After briefly describing the computation of par,  spot and forward rates,  it presents a framework for interpreting the forward rates by identifying their main influences and finally,  it develops practical tools for using forward rate analysis in active bond portfolio management.

The three main influences on the Treasury yield curve shape are:

- (1) the market's expectations of future rate changes;
- (2) bond risk premia (expected return differentials across bonds of different maturities); and
- (3) convexity bias.
Conceptually,  it is easy to divide the yield curve (or the term structure of forward rates) into these three components. It is much harder to interpret real-world yield curve shapes,  but the potential benefits are substantial. For example,  investors often wonder whether the curve's steepness reflects the market's expectations of rising rates or positive risk premia. The answer to this question determines whether a duration extension increases expected returns. It also shows whether we can view forward rates as the market's expectations of future spot rates. In addition,  our analysis will describe how the market's curve reshaping expectations and volatility expectations influence the shape of today's yield curve.

These expectations determine the cost of enhancing a portfolio's convexity via a duration-neutral yield curve trade.

Forward rate analysis also can be valuable in direct applications. Forward rates may be used as break-even rates with which subjective rate forecasts are compared or as relative value tools to identify attractive yield curve sectors. Subsequent reports will analyze many aspects of yield curve trades,  such as barbell-bullet trades,  and present empirical evidence about their historical behavior.

## COMPUTATION OF PAR,  SPOT AND FORWARD RATES

At the outset,  it is useful to review the concepts "yield to maturity,  " "par yield,  " "spot rate,  " and "forward rate" to ensure that we are using our terms consistently. Appendix A is a reference that describes the notation and definitions of the main concepts used throughout the series Understanding the Yield Curve. Our analysis focuses on government bonds that have known cash flows (no default risk,  no embedded options). Yield to maturity is the single discount rate that equates the present value of a bond's cash flows to its market price. A yield curve is a graph of bond yields against their maturities. (Alternatively,  bond yields may be plotted against their durations,  as we do in many figures in this report.) The best-known yield curve is the on-the-run Treasury curve. On-the-run bonds are the most recently issued government bonds at each maturity sector.

Because these bonds are always issued with price near par (100),  the on-the-run curve often resembles the par yield curve,  which is a curve constructed for theoretical bonds whose prices equal par.

While the yield to maturity is a convenient summary measure of a bond's expected return - and therefore a popular tool in relative value analysis

- the use of a single rate to discount multiple cash flows can be problematic unless the yield curve is flat. First,  all cash flows of a given bond are discounted at the same rate,  even if the yield curve slope suggests that different discount rates are appropriate for different cash flow dates.

Second,  the assumed reinvestment rate of a cash flow paid at a given date can vary across bonds because it depends on the yield of the bond to which the cash flow is attached. This report will show how to analyze the yield curve using simpler building blocks - single cash flows and one-period discount rates - than the yield to maturity,  an average discount rate of multiple cash flows with various maturities.

A coupon bond can be viewed as a bundle of zero-coupon bonds (zeros).

Thus,  it can be unbundled into a set of zeros,  which can be valued separately. These zeros then can be rebundled into a more complex bond,  whose price should equal the sum of the component prices.? The spot rate is the discount rate of a single future cash flow such as a zero. Equation
(1) shows the simple relation between an n-year zero's price P,  and the annualized n-year spot rate s..

A single cash flow is easy to analyze,  but its discount rate can be unbundled even further to one-period rates. That is,  a multiyear spot rate can be decomposed into a product of one-year forward rates,  the simplest building blocks in a term structure of interest rates. A given term structure of spot rates implies a specific term structure of forward rates. For example,  if the m-year and n-year spot rates are known,  the annualized forward rate between maturities m and n,  fp,  p,  is easily computed from Equation (2).

$$(1 + f{}_{\rm m,  n}){}^{\rm n-m} = \frac{(1+s_{\rm n})^{\rm n}}{(1+s_{\rm m})^{\rm m}} \tag{2}$$
The forward rate is the interest rate for a loan between any two dates in the future,  contracted today. Any forward rate can be "locked in" today by buying one unit of the n-year zero at price $P_n,   = \frac{100}{(1+s_n)^n}$ and by shortselling $\frac{P_n}{P_m}$ units of the m-year zero at price $P_m = \frac{100}{(1+s_m)^m}$.

(Such a weighting requires no net investment today because both the cash inflow and the cash outflow amount to P,  .) The one-year forward rate $(f^{n-1,  n}$ such as $f_{1,  2},   f_{2,  3},   f_{3,  4},   …)$ represents a special case of Equation (2) in which $m = n-1$. The spot rate represents another special case in which m = 0; thus,  $s_n = f_{0,  n}$.

To summarize,  a par rate is used to discount a set of cash flows (those of a par bond) to today,  a spot rate is used to discount a single future cash flow to today and a forward rate is used to discount a single future cash flow to another (nearer) future date. The par yield curve,  the spot rate curve and the forward rate curve contain the same information about today's term structure of interest rates? - if one set of rates is known,  it is easy to compute the other sets Figure | shows a hypothetical example of the three curves. In Appendix B,  we show how the spot and forward rates were computed based on the par yields.

In this example,  the par and spot curves are monotonically upward sloping,  while the forward rate curve? first slopes upward and then inverts (because of the flattening of the spot curve). The spot curve lies above the par curve,  and the forward rate curve lies above the spot curve. This is always the case if the spot curve is upward sloping. If it is inverted,  the ordering is reversed: The par curve is highest and the forward curve lowest. Thus,  loose characterizations of one curve (for example,  steeply upward-sloping,  flat,  inverted,  humped) are generally applicable to the other curves.

![500](Understanding%20The%20Yield%20Curve-%20Part%201-20240604145508070.png)
However,  the three curves are identical only if they are horizontal. In other cases,  the forward rate curve magnifies any variation in the slope of the spot curve. One-year forward rates measure the marginal reward for lengthening the maturity of the investment by one year,  while the spot rates measure an investment's average reward from today to maturity $n$.

Therefore,  spot rates are (geometric) averages of one or more forward between zero yields (spot curve). Because these assets have special liquidity characteristics,  these curves may not be representative of the broad Treasury market. Therefore. the par. spot or forward rate curve is typically estimated using a broad universe of coupon Treasury bond prices. Many different "curve fitting" techniques exist,  but a common goal rates. Similarly,  par rates are averages of one or more spot rates; thus,  par curves have the flattest shape of the three curves. In Appendix C,  we discuss further the relationship between spot and forward rate curves.

It is useful to view forward rates as break-even rates. The implied spot rates one year forward $(f_{1,  2},   f_{1,  3},   f_{1,  4},   …)$ are,  by construction,  equal to such future spot rates that would make all government bonds earn the same return over the next year as the (riskless) one-year zero. For example,  the holding-period return of today's two-year zero (whose rate today is s,  ) will depend on its selling rate (as a one-year zero) in one year's time. The implied one-year spot rate one year forward ($f_{0,  5}$) is computed as the selling rate that would make the two-year zero's return (the left-hand side of Equation (3)) equal to the one-year spot rate (the right-hand side of Equation (3))®. Formally,  Equation (3) is derived from Equation (2) by setting $m = 1$ and $n = 2$ and rearranging.

Consider an example using numbers from Figure 1,  in which the one-year spot rate (s;) equals 6% and the two-year spot rate ($S_2$) equals 8.08\%.

- Plugging these spot rates into Equation (3),  we find that the implied one-year spot rate one year forward (f)) equals 10.20%.
- If this implied forward rate is exactly realized one year hence,  today's two-year zero will be worth 100/1.1020 = 90.74 next year.
- Today,  this zero is worth 100/1.08082 = 85.61; thus,  its return over the next year would be 90.74/85.61-1 = 6\%,  exactly the same as today's one-year spot rate.
- Thus,  10.20\% is the break-even level of future one-year spot rate.
	-In other words,  the one-year rate has to increase by more than 420 basis points (10.20\%-6.00\%) before the two-year zero underperforms the one-year zero over the next year.
	- If the one-year rate increases,  but by less than 420 basis points,  the capital loss of the two-year zero will not fully offset its initial yield advantage over the one-year zero.

More generally,  if the yield changes implied by the forward rates are subsequently realized,  all government bonds,  regardless of maturity,  earn the same holding-period return. In addition,  all self-financed positions of government bonds (such as long a barbel! versus short a bullet) earn a return of $0\%;$ that is,  they break even. In contrast,  if the yield curve remains unchanged over a year,  each n-year zero earns the
corresponding one-year forward rate f $_{\mathrm{n-1,  n}}.$ This can be seen from Equation 2 when $m=n-l; 1+f _\mathrm{n-1,  n}$ equals $(1+s_{n})^{n/(1+s_{n-1})^{n-1}}$,  which is the holding-period return from buying an n-year zero at rate s $_\mathrm{n}$,  and selling it one year later at rate s $_{\mathrm{n-1}}.$ Thus,  the one-year forward rate equals a zero's horizon return for an unchanged yield curve (see Appendix C for details).

In this section,  we describe some economic forces that influence the term structure of forward rates or,  more generally,  the yield curve shape. The three main influences are the market's rate expectations,  the bond risk premia (expected return differentials across bonds) and the so-called convexity bias. In fact,  these three components fully determine the yield curve; we will show in later reports that the difference between each one-year forward rate and the one-year spot rate is approximately equal to the sum of an expected spot rate change,  a bond risk premium and the convexity bias. We first discuss how each component influences the curve shape,  and then we analyze their combined impact.

## RATE EXPECTATIONS

It is clear that the market's expectation of future rate changes is an important determinant of the yield curve shape. For example,  a steeply upward-sloping curve may indicate that the market expects near-term Fed tightening or rising inflation. However,  it may be too restrictive to assume that the yield differences across bonds with different maturities only reflect the market's rate expectations. The well-known pure [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] has such an extreme implication. The pure [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] asserts that all government bonds have the same near-term expected return (as the nominally riskless short-term bond) because the return-seeking activity of risk-neutral traders removes all expected return differentials across bonds. Near-term expected returns are equalized if all bonds that have higher yields than the short-term rate are expected to suffer capital losses that offset their yield advantage. When the market expects an increase in bond yields,  the current term structure becomes upward-sloping so that any long-term bond's yield advantage and expected capital loss (due to the expected yield increase) exactly offset each other. In other words,  if investors expect that their long-term bond investments will lose value because of an increase in interest rates,  they will require a higher initial yield as a compensation for duration extension.

Conversely,  expectations of yield declines and capital gains will lower current long-term bond yields below the short-term rate,  making the term structure inverted.

The same logic - that positive (negative) initial yield spreads offset expected capital losses (gains) to equate near-term expected returns - also holds for combinations of bonds,  including duration-neutral yield curve positions. One example is a trade that benefits from the flattening of the yield curve between twoand ten-year maturities: selling a unit of the two-year bond,  buying a duration-weighted amount of the ten-year bond and putting the remaining proceeds from the sale to "cash" (very short-term bonds). Given the typical concave yield curve shape (as a function of duration),  such a curve flattening position earns a negative carry.' The trade will be profitable only if the curve flattens enough to offset the impact of the negative carry. Implied forward rates indicate how much flattening (narrowing of the twoto ten-year spread) is needed for the trade to break even.

In the same way as the market's expectations regarding the future level of rates influence the steepness of today's yield curve,  the market's expectations regarding the future steepness of the yield curve influence the curvature of today's yield curve. If the market expects more curve flattening,  the negative carry of the flattening trades needs to increase (to offset the expected capital gains),  making today's yield curve more concave (curved). Figure 2 illustrates these points. This figure plots coupon bonds' yields against their durations or,  equivalently,  zeros' yields against their maturities,  given various rate expectations. Ignoring the bond risk premia and convexity bias,  if the market expects no change in the level or slope of the curve,  today's yield curve will be horizontal. If the market expects a parallel rise in rates over the next year but no reshaping,  today's yield curve will be linearly increasing (as a function of duration).

If the market expects rising rates and a flattening curve,  today's yield curve will be increasing and concave (as a function of duration).
![500](Z.%20Clippings/Understanding%20The%20Yield%20Curve-%20Part%201-20240604145507930.png)

# BOND RISK PREMIUM

A key assumption in the pure [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] is that all government bonds,  regardless of maturity,  have the same expected return.

In contrast,  many theories and empirical evidence suggest that expected returns vary across bonds. We define the bond risk premium as a longer-term bond's expected one-period return in excess of the one-period bond's riskless return. A positive bond risk premium would tend to make the yield curve slope upward. However,  various theories disagree about the sign (+/-),  the determinants and the constancy (over time) of the bond risk premium. The classic liquidity premium hypothesis argues that most investors dislike short-term fluctuations in asset prices; these investors will hold long-term bonds only if they offer a positive risk premium as a compensation for their greater return volatility. Also some modern asset pricing theories suggest that the bond risk premium should increase with a bond's duration,  its return volatility or its covariance with market wealth.

In contrast,  the preferred habitat hypothesis argues that the risk premium may decrease with duration; long-duration liability holders may perceive the long-term bond as the riskless asset and require higher expected returns for holding short-term assets. While academic analysis focuses on risk-related premia,  market practitioners often emphasize other factors that cause expected return differentials across the yield curve. These include liquidity differences between market sectors,  institutional restrictions and supply and demand effects. We use the term "bond risk premium" broadly to encompass all expected return differentials across bonds,  including those caused by factors unrelated to risk.

Historical data on U.S. Treasury bonds provide evidence about the empirical behavior of the bond risk premium. For example,  the fact that the Treasury yield curve has been upward sloping nearly 90% of the time in recent decades may reflect the impact of positive bond risk premia.

Historical average returns provide more direct evidence about expected returns across maturities than do historical yields. Even though weekly and monthly fluctuations in bond returns are mostly unexpected,  the impact of unexpected yield rises and declines should wash out over a long sample period. Therefore,  the historical average returns of various maturity sectors should reflect the /ong-run expected returns.
![500](Understanding%20The%20Yield%20Curve-%20Part%201-20240604145507808.png)
Figure 3 shows the empirical average return curve as a function of average duration and contrasts it to one theoretical expected return curve,  one that increases linearly with duration. The theoretical bond risk premia are measured in Figure 3 by the difference between the annualized expected returns at various duration points and the annualized return of the riskless one-month bill (the leftmost point on the curve). Similarly,  the empirical bond risk premia are measured by the historical average bond returns at various durations in excess of the one-month bill.? Historical experience suggests that the bond risk premia are not linear in duration,  but that they increase steeply with duration in the front end of the curve and much more slowly after two years. The concave shape may reflect the demand for long-term bonds from pension funds and other long-duration liability holders.

Figure 3 may give us the best empirical estimates of the long-run average bond risk premia at various durations. However,  empirical studies also suggest that the bond risk premia are not constant but vary over time.

That is,  it is possible to identify in advance periods when the near-term bond risk premia are abnormally high or low. These premia tend to be high after poor economic conditions and low after strong economic conditions.

A possible explanation for such countercyclic variation in the bond risk premium is that investors become more risk averse when their wealth is relatively low,  and they demand larger compensation for holding risky assets such as long-term bonds.!?

## CONVEXITY BIAS

The third influence on the yield curve - the convexity bias - is probably the least well known. Different bonds have different convexity characteristics,  and the convexity differences across maturities can give rise to (offsetting) yield differences. In particular,  long-term zeros exhibit very high convexity (see top panel of Figure 4),  which tends to depress their yields. Convexity bias refers to the impact these convexity differences have on the yield curve shape.

Convexity is closely related to the nonlinearity in the bond price-yield relationship. All noncallable bonds exhibit positive convexity; their prices rise more for a given yield decline than they fall for a similar yield increase. All else being equal,  positive convexity is a desirable characteristic because it increases a bond's return (relative to return in the absence of convexity) whether yields go up or down - as long as they move somewhere. Because positive convexity can only improve a bond's performance (for a given yield),  more convex bonds tend to have lower yields than less convex bonds with the same duration.!! In other words,  investors tend to demand less yield if they have the prospect of improving their returns as a result of convexity. Investors are primarily interested in expected returns,  and these high-convexity bonds can offer a given expected return at a lower yield level.

10 pants 3 and 4 of this series describe the empirical behavior of the bond risk premia. Does Duration Extension Enhance Long-Term Expected Returns? focuses on the long-run average return differentials across bonds with different maturities. Forecasting U.S. Bond Returns focuses on the near-term expected return differentials across bonds and on the time-variation in the bond risk premia.
![500](Z.%20Clippings/20240604145507670.png)
Note: Volatility of annual yield changes is assumed to be 100 basis points. Thus,  the convexity bias is
-0.5 * the zero's convexity * 1.

The lower panel of Figure 4 illustrates the pure impact of convexity on the curve shape by plotting the spot rate curve and the curve of one-year forward rates when all bonds have the same expected return (8/%) and the short-term rates are expected to remain at the current level. With no bond risk premia and no expected rate changes,  one might expect these curves to be horizontal at 8/%. Instead,  they slope down at an increasing pace because lower yields are needed to offset the convexity advantage of longer-duration bonds and thereby to equate the near-term expected returns across bonds. Short-term bonds have little convexity; therefore,  there is little convexity bias at the front end of the yield curve,  but convexity can have a dramatic impact on the curve shape at very long durations. Convexity bias can be one of the main reasons for the typical concave yield curve shape (that is,  for the tendency of the curve to flatten or invert at long durations).

The value of convexity increases with the magnitude of yield changes.

Therefore,  increasing volatility should make the overall yield curve shape more concave (curved) and widen the spreads between more and less convex bonds (duration-matched coupon bonds versus zeros and barbells versus bullets).
Of course,  all three forces influence bond yields simultaneously,  making the task of interpreting the overall yield curve shape quite difficult. A steeply upward-sloping curve can reflect either the market's expectations of rising rates or high required risk premia. A strongly humped curve (that is,  high curvature) can reflect the market's expectations of either curve flattening or high volatility (which makes convexity more valuable),  or even the concave shape of the risk premium curve.

In theory,  the yield curve can be neatly decomposed into expectations,  risk premia and convexity bias. In reality,  exact decomposition is not possible because the three components vary over time and are not directly observable but must be estimated.'+ Even though an exact decomposition is not possible,  the analysis in this and subsequent reports should give investors a framework for interpreting various yield curve shapes. These reports will characterize the behavior of rate expectations,  risk premia and convexity bias; show how they influence the curve: and evaluate the magnitude of their impact using historical data. Furthermore,  our survey of earlier literature and our new empirical work will evaluate which theories and market myths are correct (consistent with data) and which are false.

#### THE MAIN CONCLUSIONS ARE AS FOLLOWS
- We often hear that "forward rates show the market's expectations of future rates.'' However,  this statement is only true if no bond risk premia exist and the convexity bias is very small.'> If the goal is to infer expected short-term rates one or two years ahead,  the convexity bias is so small that it can be ignored. In contrast,  our empirical analysis shows that the bond risk premia are important at short maturities. Therefore,  if the forward rates are used to infer the market's near-term rate expectations,  some measures of bond risk premia should be subtracted from the forwards,  or the estimate of the market's rate expectations will be strongly upward biased.
- The traditional term structure theories assume a zero risk premium (pure [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]]) or a nonzero but constant risk premium (liquidity premium hypothesis,  preferred habitat hypothesis) which is inconsistent with historical data. According to the pure [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]],  an upward-sloping curve should predict increases in long-term rates,  so that a capital loss offsets the long-term bonds' yield advantage. However,  empirical evidence shows that,  on average,  small declines in long-term rates,  which augment the long-term bonds' yield advantage,  follow upward-sloping curves. The steeper the yield curve is,  the higher the expected bond risk premia. This finding clearly violates the pure [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] and supports hypotheses about time-varying risk premia.
- Modern term structure models make less restrictive assumptions than the traditional theories above. Yet,  many popular one-factor models assume that bonds with the same duration earn the same expected return. Such an assumption implies that duration-neutral positions with more or less convexity earn the same expected return (because a yield disadvantage exactly offsets any convexity advantage). However,  if the market values very highly the insurance characteristics of positively convex positions,  more convex positions may earn lower expected returns. Our analysis of the empirical performance of duration-neutral barbell-bullet trades will show that,  in the long run,  barbells tend to marginally underperform bullets.

## USING FORWARD RATE ANALYSIS IN YIELD CURVE TRADES

Recall that if the pure [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] holds,  all bond positions have the same near-term expected return. In particular,  an upward-sloping yield curve reflects expectations of rising rates and capital losses,  and convexity is priced so that a yield disadvantage exactly offsets the convexity advantage. In such a world,  yields do not reflect value,  no trades have favorable odds and active management can add value only if an investor has truly superior forecasting ability. Fortunately,  the real world is not quite like this theoretical world. Empirical evidence (presented in parts 2-4 of this series of reports) shows that expected returns do vary across bonds. The main reason is probably that most investors exhibit risk aversion and preferences for other asset characteristics; moreover,  investor behavior may not always be fully rational. Therefore,  yields reflect value and certain relative value trades have favorable odds.

The previous section provided a framework for thinking about the term structure shapes. In this section,  we describe practical applications —different ways to use forward rates in yield curve trades. The first approach requires strong subjective rate views and faith in one's forecasting ability.

#### FORWARDS AS BREAK-EVEN RATES FOR ACTIVE YIELD CURVE VIEWS

The forward rates show a path of break-even future rates and spreads. This path provides a clear yardstick for an active portfolio manager's subjective yield curve scenarios and yield path forecasts. It incorporates directly the impact of carry on the profitability of the trade. For example,  a manager should take a bearish portfolio position only if he expects rates to rise by more than what the forwards imply. However,  if he expects rates to rise by less than what the forwards imply (that is,  by less than what is needed to offset the positive carry),  he should take a bullish portfolio position. If the manager's forecast is correct,  the position will be profitable.

In contrast,  managers who take bearish portfolio positions whenever they expect bond yields to rise - ignoring the forwards - may find that their positions lose money,  because of the negative carry,  even though their rate forecasts are correct.

One positive aspect about the role of forward rates as break-even rates is that it does not depend on assumptions regarding expectations,  risk premia or convexity bias. The rules are simple. If forward rates are realized,  all positions earn the same return. If yields rise by more than the forwards imply,  bearish positions are profitable and bullish positions lose money. If yields rise by less than the forwards imply,  the opposite is true. Similar statements hold for any yield spreads and related positions,  such as curve-flattening positions.
![500](Understanding%20The%20Yield%20Curve-%20Part%201-20240604145507540.png)
Figure 5 shows the U.S. par yield curve and the implied par curves three months forward and 12 months forward based on the Salomon Brothers Treasury Model as of March 31,  1995. If we believe that forward rates only reflect the market's rate expectations,  a comparison of these curves tells us that the market expects rates to rise and the curve to flatten over the next year. Alternatively,  the implied yield rise may reflect a bond risk premium and the implied curve flattening may reflect the value of convexity. Either way,  the forward yield curves reflect the break-even levels between profits and losses.

The information in the forward rate structure can be expressed in several ways. Figure 5 is useful for an investor who wants to contrast his subjective view of the future yield curve with an objective break-even curve at some future horizon. Another graph may be more useful for an investor who wants to see the break-even future path of any constant-maturity rate (instead of the whole curve) and contrast it with his own forecast,  which may be based on a macroeconomic forecast or on the subjective view about the speed of Fed tightening.
As an example,  Figure 6 shows such a break-even path of future three-month rates at the end of March 1995 To add perspective,  the graph also contains the historical path of the three-month rate over the past eight years and the break-even path of the future three-month rates at the end of 1994 when the Treasury market sentiment was much more bearish.
![500](Understanding%20The%20Yield%20Curve-%20Part%201-20240604145507277.png)
16 Note that the first point in each implied forward par curve in Figure 5 is the implied forward three-month rate at a given future date. Therefore. the forward path in Figure 6 can be constructed by tracing through the three-month points in the three curves of Figure 5 and through similar curves at other horizons. Because Figure 6 depicts a rate path over time. the x-axis is calendar years and not maturity.

#### FORWARDS AS INDICATORS OF CHEAP MATURITY SECTORS

The other ways to use forwards require less subjective judgment than the first one. As a simple example,  the forward rate curve can be used to identify cheap maturity sectors visually. Abnormally high forward rates are more visible than high spot or par rates because the latter are averages of forward rates.

Figure 7 shows one real-world example from the beginning of this decade when the par yield curve was extremely flat (although forwards may be equally useful when the par curve is not flat). Even though the par yield curve was almost horizontal (all par yields were within 25 basis points),  the range of three-month annualized forward rates was almost 200 basis points because the forward rate curve magnifies the cheapness/richness of different maturity sectors. High forward rates identify the six-year sector and the 12-year sector as cheap,  and low forward rates identify the four-year sector and the nine-year sector as expensive.
![500](Understanding%20The%20Yield%20Curve-%20Part%201-20240604145507410.png)
Once an investor has identified a sector with abnormally high forward rates
(for example,  between nine and 12 years),  he can exploit the cheapness of this sector by buying a bond that matures at the end of the period (12 years) and by selling a bond that matures at the beginning of the period
(nine years). If equal market values of these bonds are bought and sold,  the position is exposed to a general increase in rates and a steepening yield curve. More elaborate trades can be constructed (for example,  by selling both the nine-year and 15-year bonds against the 12-year bonds with appropriate weights) to retain level and slope neutrality. To the extent that bumps and kinks in the forward curve reflect temporary local cheapness,  the trade will earn capital gains when the forward curve becomes flatter and the cheap sector richens (in addition to the higher yield and rolldown the position earns). In the example of Figure 7,  such "richening" actually did happen over the next three months.

## FORWARDS AS RELATIVE VALUE TOOLS FOR YIELD CURVE TRADES

Above,  forwards are used quite loosely to identify cheap maturity sectors. A more formal way to use forwards is to construct quantitative cheapness indicators for duration-neutral flattening trades,  such as barbell-bullet
trades. We first introduce some concepts with an example of a market-directional trade.

When the yield curve is upward sloping,  long-term bonds’ yield advantage over the riskless short-term bond provides a cushion against rising yields. In a sense,  duration extensions are"cheap" when the yield curve is very steep and the cushion (positive carry) is large. These trades only lose money if capital losses caused by rising rates offset the initial yield advantage. Moreover,  the longer-term bonds’rolling yield advantages $^{18}$ over the short-term bond are even larger than their yield advantages. The one-year forward rate (f $_\mathrm{n-1,  n})$ is,  by construction,  equal to the n-year zero's rolling yield (see Appendix C). Thus,  it is a direct measure of the n-year zero's rolling yield advantage. (Another forward-related measure,  the change in the n-1 year spot rate implied by the forwards ($f_{1,   n},  -s_{n-1}$),  tells how much the yield curve has to shift to offset this advantage and to equate the holding-period returns of the n-year zero and the one-year zero.)

Because one-period forward rates measure zeros' near-term expected returns,  they can be viewed as indicators of cheap maturity sectors. The use of such cheapness indicators does not require any subjective interest rate view. Instead,  it requires a belief,  motivated by history,  that an unchanged yield curve is a good base case scenario If this is true,  long-term bonds have higher (lower) near-term expected returns than short-term bonds when the forward rate curve is upward sloping (downward sloping). In the long run,  a strategy that adjusts the portfolio duration dynamically based on the curve shape should earn a higher average return than constant-duration strategies

Similar analysis holds for curve-flattening trades. Recall that when the yield curve is concave as a function of duration,  any duration-neutral flattening trade earns a negative carry. Higher concavity (curvature) in the yield curve indicates less attractive terms for a flattening trade (larger negative carry) and more"implied flattening" by the forwards (which is needed to offset the negative carry). Therefore,  the amount of spread change implied by the forwards is a useful cheapness indicator for yield curve trades at different parts of the curve. If the implied change is historically wide,  the trade is expensive,  and vice versa. Figure 8 shows an example of a recent situation in which the flattening trades were extremely expensive. At the end of December 1994,  the three-month to two-year sector of the Treasury curve was very steep (a spread of 200 basis points) and the twoto 30-year sector was quite flat (a spread of 20 basis points). The high curvature indicated strong flattening expectations -forwards implied an inversion of the twoto 30-year spread by March-or high expected volatility (high value of convexity).

The barbell (of the 30-year bond and three-month bill) over the duration-matched two-year bullet would become profitable only if the curve flattened even more than the forwards implied or if a sudden increase in volatility occurred. Purely on yield grounds,  the two-year bullet (a steepening position) appeared cheap in an absolute comparison (across bonds) and in a historical comparison (over time). With the benefit of hindsight,  we know that the cheapness indicator gave a correct signal. The two-year bullet outperformed various duration-matched barbell positions substantially over the next quarter as it earned large capital gains in addition to its high initial yield and rolldown advantage. By the end of March,  the front end of the curve had flattened by 108 basis points and the long end had steepened by 45 basis points. Figure 8 illustrates the decline in curvature by plotting the Treasury on-the-run yield curves (as a function of duration) on December 30 and on March 31. In later reports,  we will show how to use forward rate analysis to evaluate opportunities like this.
![500](Understanding%20The%20Yield%20Curve-%20Part%201-20240604145507126.png)

## APPENDIX A. NOTATION AND DEFINITIONS USED IN THE SERIES UNDERSTANDING THE YIELD CURVE
- $P$: Market price of a bond.
- $P_n$: Market price of an n-year zero.
- $C$: Coupon rate (in percentage; other rates are expressed as a decimal).
- $y$: Annualized yield to maturity (YTM) of a bond.
- $n$: Time to maturity of a bond (in years).
- $s_n$: Annualized n-year spot rate; the discount rate of an n-year zero.
- $s^*_{n-1}$: Annualized n-1 year spot rate next period; superscript * denotes next period's (year's) value.
- $\Delta s_{n-1}$: Realized change in the n-1 year spot rate between today and next period $(= s^*_{n-1} - s_{n-1})$.
- $f_{m,  n}$: Annualized forward rate between maturities m and n.
- $f_{n-1,  n}$: One-year forward rate between maturities (n-1) and n; also the n-year zero’s rolling yield.
- $f_{1,  n}$: Annualized forward rate between maturities 1 and n; also called the implied forward.
- $\Delta f_{n-1}$: Implied change in the n-1 year spot rate between today and next period $(= f_{1,  n} - s_{n-1})$; also called the break-even yield change (over the next period) implied by the forwards.
- $\Delta f_{z_n}$: Implied change in the yield of an n-year zero,  a specific bond,  over the next period $(= f_{1,  n} - s_n)$.
- $FSP$: Forward-spot premium $(FSP_n = f_{n-1,  n} - s_1)$.
- $h_n$: Realized holding-period return of an n-year zero over one period (year).
- Rolling Yield: A bond’s horizon return given a scenario of unchanged yield curve; sum of yield and rolldown return.
- Bond Risk Premium (BRP): Expected return of a long-term bond over the next period (year) in excess of the riskless one-period bond; for the n-year zero,  $BRP_n = E(h_n - s_1)$.
- Realized BRP: Realized one-year holding-period return of a long-term bond in excess of the one-year bond; also called excess bond return; realized $BRP_n = h_n - s_1$.
- Persistence Factor (PF): Slope coefficient in a regression of the annual realized BRP$_n$ on FSP$_n$.
- Term Spread: Yield difference between a long-term bond and a short-term bond; for the n-year zero,  $= s_n - s_1$.
- Real Yield: Difference between a long-term bond yield and a proxy for expected inflation; our proxy is the recently published year-on-year consumer price inflation rate.
- Inverse Wealth: Ratio of exponentially weighted past wealth to the current wealth; we proxy wealth $W$ by the stock market level; $= (W_{t-1} + 0.9*W_{t-2} + 0.92*W_{t-3} + \ldots)*0.1/W_t$.
- Duration (Dur): Measure of a bond price’s interest rate sensitivity; $Dur = -(\mathrm{d}P/\mathrm{d}y) * (1/P)$.
- Convexity (Cx): Measure of the nonlinearity in a bond’s P/y -relation; $Cx = (\mathrm{d}^2P/\mathrm{d}y^2) * (1/P)$.
- Convexity Bias (CB): Impact of convexity on the curve of one-year forward rates; $CB_n = -0.5 * Cx_n * (\text{Volatility of } \Delta s_n)^2$.

![500](Understanding%20The%20Yield%20Curve-%20Part%201-20240604151021545.png)

## BETWEEN SPOT RATES,  FORWARD RATES,  RELATIONS AND BOND RETURNS

Investors often want to make quick "back-of-the-envelope" calculations with spot rates,  forward rates and bond returns. In this appendix,  we discuss some simple relations between these variables,  beginning with a useful approximate relation between spot rates and one-year forward rates.

These relations are discussed in more detail in the appendix of Market's Rate Expectations and Forward Rates. Equation (2) showed exactly how the forward rate between years m and n is related to mand n-year spot rates. Equation (8) shows the same relation in an approximate but simpler form; this equation ignores nonlinear effects such as the convexity bias.

The relation is exact if spot rates and forward rates are continuously compounded.

$$\mathrm{f}_{\mathrm{m,  n}}\approx\frac{\mathrm{ns}_{\mathrm{n}}-\mathrm{ms}_{\mathrm{m}}}{\mathrm{n}-\mathrm{m}}\tag{8}$$
For one-year forward rates ($m = n-1$),  Equation (8) can be simplified to $$\rm f_{n-1,  n}\approx s_{n}+(n-1)* (\rm s_{n}-s_{n-1})$$
Equation (9) shows that the forward rate is equal to an n-year zero's one-year horizon return given an unchanged yield curve scenario: a sum of the initial yield and the rolldown return (the zero's duration at horizon
(n-!) multiplied by the amount the zero rolls down the yield curve as it ages). This horizon return is often called the rolling yield. Thus,  the one-year forward rates proxy for near-term expected returns at different parts of the yield curve if the yield curve is expected to remain unchanged.

We can gain intuition about the equality of the one-year forward rate and the rolling yield by examining the n-year zero's realized holding-period return h,  over the next year,  in Equation (10). The zero earns its initial yield s,  plus a capital gain/loss,  which is approximated by the product of the zero's year-end duration and its realized yield change.

$$
h_n\approx s_n+(n-1)*(s_n-s_{n-1}^*)
$$

## CALCULATING SPOT AND FORWARD RATES WHEN PAR ARE KNOWN

A simple example illustrates how spot rates and forward rates are computed on a coupon date when the par curve is known (and coupon payments and compounding frequency are annual). The basis of the procedure is the fact that a bond's price will be the same,  the sum of the present values of its cash flows,  whether it is priced via yield to maturity
(Equation (4)) or via the spot rate curve (Equation (5)):

$$

P = \frac{C}{1 + y} + \frac{C}{(1 + y)^2} + \cdots + \frac{C + 100}{(1 + y)^n} 
$$
$$
P = \frac{C}{1 + s_1} + \frac{C}{(1 + s_2)^2} + \cdots + \frac{C + 100}{(1 + s_n)^n}$$
where P is the bond price,   C is the coupon rate (in percentage),   y is the annual yield to maturity (expressed as a decimal),   s is the annual spot rate (expressed as a decimal),   and n is the time to maturity (in years).

We only show the computation for the first two years,   which have par rates of 6% and 8%. For the first year,   par,   spot,   and forward rates are equal (6%). Longer spot rates are solved recursively using known values of the par bond's price and cash flows and the previously solved spot rates.

Every par bond's price is 100 (par) by construction; thus,   its yield (the par rate) equals its coupon rate. Because the two-year par bond's market price (100) and cash flows (8 and 108) are known,   as is the one-year spot rate
(6%),   it is easy to solve for the two-year spot rate as the only unknown in the following equation:

$$100=\frac{\rm C}{1+\rm s_{1}}+\frac{\rm C}{(1+\rm s_{2})^{2}}=\frac{8}{1.06}+\frac{108}{(1+\rm s_{2})^{2}}\,  .\tag{6}$$
A little manipulation shows that the solution for s> is 8.08%. Equation (6) also can be used to compute par rates when only spot rates are known. If the spot rates are known,   the coupon rate C,   which equals the par rate,   is the only unknown in Equation (6).

The forward rate between one and two years is computed using Equation
(3) and the known one-year and two-year spot rates.

$$(1+\mathrm{f}_{1,  2})=\frac{(1+\mathrm{s}_{2})^{2}}{1+\mathrm{s}_{1}}=\frac{(1.0808)^{2}}{1.06}=1.1020\tag{7}$$
The solution for f; is 10.20%. The other spot rates and one-year forward rates (f23,   f3.4,   etc.) in Figure 9 are computed in the same way. These numbers are shown graphically in Figure 1.

where s*,  .) is the n-1 year spot rate next year. If the yield curve follows a random walk,   the best forecast for s*,  .; is (today's) s,  

1. Therefore,   the n-year zero's expected holding period return equals the one-year forward rate in Equation (9). The key question is whether it is more reasonable to assume that the current spot rates are the optimal forecasts of future spot rates than to assume that forwards are the optimal forecasts. We present later empirical evidence which shows that the "random walk" forecast of an unchanged yield curve is more accurate than the forecast implied by the forwards.

Equation (9) shows that the (one-year) forward rate curve lies above the spot curve as long as the latter is upward sloping (and the rolldown return is positive). Conversely,   if the spot curve is inverted,   the rolldown return is negative,   and the forward rate curve lies below the spot curve. If the spot curve is first rising and then declining,   the forward rate curve crosses it from above at its peak. Finally,   the forward rate curve can become downward sloping even when the spot curve is upward sloping,   if the spot curve's slope is first steep and then flattens (reducing the rolldown return).

The calculations below illustrate this point and show that the approximation is good - within a few basis points from the correct values
$$

f_{1,  2} \approx 8.08 + 1 \times (8.08 - 6.00) = 8.08 + 2.08 = 10.16;

$$
$$

f_{2,  3} \approx 9.72 + 2 \times (9.72 - 8.08) = 9.72 + 3.28 = 13.00;

$$
$$

f_{3,  4} \approx 10.86 + 3 \times (10.86 - 9.72) = 10.86 + 3.42 = 14.28;

$$
$$

f_{4,  5} \approx 11.44 + 4 \times (11.44 - 10.86) = 11.44 + 2.32 = 13.76.

$$