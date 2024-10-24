---
aliases:
- Alias_265_Forward Rates and the Yield Curve.md
- Forward Rates
- '**-RELATIONSHIPS BETWEEN FORWARD,   SPOT,   AND PAR RATES**'
- Alias_262_Forward Rates and the Yield Curve.md
linter-yaml-title-alias: '**-RELATIONSHIPS BETWEEN FORWARD,   SPOT,   AND PAR RATES**'
tags:
- tag_example
title: Forward Rates and the Yield Curve
---



## **BOND PRICING USING ZERO-COUPON BONDS**

- A coupon bond can be viewed as a bundle of zero-coupon bonds (zeros)
- It can be unbundled into zeros valued separately,  then rebundled
- The recombined price equals the sum of the component prices

## **SPOT RATES,  FORWARD RATES AND DISCOUNT RATES**

- A single cash flow can be decomposed into one-period rates
- A multi-year spot rate is a product of one-year forwards,  the basic building blocks
- **Forward rate** is the interest rate contracted today:
	 - For a loan between any two future dates
	 - Can be locked in by:
		  - 1. Buying 1 unit of n-year zero at price$P_n = \frac{100}{(1+s_n)^n}$
		  - 2. Short selling$\frac{P_n}{P_m}$units of m-year zero at price$P_m = \frac{100}{(1+s_m)^m}​$
- **Par rate** discounts a set of cash flows (par bond) to today
- **Spot rate** discounts a single future cash flow to today
- **Forward rate** discounts a future cash flow to a nearer future date
- The par,  spot,  and forward curves contain the same information about the term structure
## **-FORWARD RATES AS BREAK-EVEN RATES**
- Forward rates equal the spot rates implied for the future that would make all bonds earn the same return
- If forwards are realized,  all self-financed bond positions earn zero return (break even)
- If the curve is unchanged,  an n-year zero's horizon return equals the n-1 year forward rate
# Forward Rates and the Yield Curve
- In this example:
	 - The par and spot curves are upward sloping
	 - The forward rate curve is first upward sloping,  then inverts
		  - This inversion is because the spot curve is flattening
- The spot curve lies above the par curve
- The forward curve lies above the spot curve
- This ordering applies when the spot curve is upward sloping
- If the spot curve is inverted:
	 - The ordering is reversed
		  - The par curve is highest
		  - The forward curve is lowest
- Loose characterizations (e.g. steeply upward sloping) apply to all three curves
- The curves are identical only if horizontal
- The forward curve magnifies variations in the spot curve slope
- **Forward rates** measure:
	 - The marginal reward for extending maturity by 1 year
- **Spot rates** measure:
	 - The average reward from today to maturity n
- Thus:
	 - Spot rates are geometric averages of forward rates
- **Par rates** are averages of spot rates
- Therefore,  par curves have the flattest shape
## **-FORWARD RATES AS BREAK-EVEN RATES**
- The implied 1-year spot rates 1 year forward are:
	 - Equal to future spot rates that equate all bonds' next year return to that of 1-year zero
- The implied 1-year spot rate 1 year forward f 1,  2​ is:
	 - The selling rate that makes the 2-year zero's return (LHS) equal the 1-year spot rate (RHS):
- 2-year zero return=P 1,  in 1 yearP 2,  today−1​
- 1-year spot rate=1+s 1​
- Using example numbers:
	 - 1-year spot rate s 1=6​
	 - 2-year spot rate s 2=8.08​
	 - Plugging into equation:
		  - 1001.1020∇⋅100 (1.08082)−1=1+0.06​
		  - ∴f 1,  2=10.20​
- If f 1,  2​ is realized:
	 - The 2-year zero return equals the 1-year spot rate
	 - All bonds earn equal holding period returns
- If the curve is unchanged:
	 - An n-year zero's return equals the n-1 year forward rate

![Forward3s.png](file:///Users/rogerlin/Downloads/a6e011dc-0304-4657-a83a-45529d28a9b2%252FExport-d6f59a94-eb94-4c36-a827-7adc40e6813d/Yield%20Curves%20000680c441ec43c68f8d832e5af8117a/Forward3s.png?lastModify=1706363157)

# FORWARD RATES AND EXPECTATIONS

- Suppose,  for example,  that the 3-month rate now is 10.0 percent and the market expects that there will be a 0.25 percent cut in rates during the next 3 months – so that at the end of 3 months,  the 3-month rate will be 9.75 percent. Given these data,  what should the 6-month rate be now?
- The answer must be the rate achieved by taking the 3-month rate now,  compounded with the expected 3-month rate in 3 months’ time; otherwise there would be an expected profit in going long for 3 months and short for 6 months or vice versa,  and the market would tend to move the rates. In this way,  the 6-month rate now can be calculated as:

	 (1 + 0.100) x (1 + 0.0975) - 1 = 0.097375 = 9.74%

# CARRY TRADE [Carry Trade 1](Carry%20Trade%201.md)

Carry trade involves borrowing funds at a lower interest rate and investing them in assets that yield a higher interest rate. The difference between the interest earned and the interest paid is known as the “carry,  ” and it represents the profit from the trade.

Negative carry trade is the opposite of carry trade,  where the cost of borrowing exceeds the yield on the investment. A negative carry trade occurs when an investor borrows funds at a higher interest rate and invests in assets yielding a lower interest rate. This leads to a loss,  or negative carry.

### SECTION 3: CARRY TRADE AND YIELD CURVES [Yield Curves](1.%20Financial%20Instruments/Fixed%20Income%20Securities/Yield%20Curves.md)

The relationship between carry trades and yield curves is nuanced and depends on the shape of the yield curve.

**3.1 Upward-Sloping Yield Curve**

- In an upward-sloping yield curve,  long-term yields are higher than short-term yields. This scenario is favorable for carry trades as investors can borrow short-term at lower rates and invest long-term at higher rates.

**3.2 Inverted Yield Curve**

- An inverted yield curve,  where long-term yields are lower than short-term yields,  is unfavorable for carry trades. This scenario may lead to negative carry trades,  where the cost of borrowing short-term exceeds the yield on long-term investments.

**3.3 Flat Yield Curve**

- A flat yield curve,  where short-term and long-term yields are nearly equal,  may offer limited opportunities for carry trades,  as the difference between borrowing and investing rates is minimal.

---

# **MAIN INFLUENCES ON THE YIELD-CURVE SHAPE**

[17. The Yield Curve and Spot Rates](17.%20The%20Yield%20Curve%20and%20Spot%20Rates.pdf)

The three main influences on the Treasury yield-curve shape are:

1. **The market's expectations of future rate changes**
1. **Bond risk premiums** (expected return differentials across bonds of different maturities)
1. **Convexity bias**

These three components fully determine the yield-curve; it can be shown that the difference between each one-year forward rate and the one-year spot rate is approximately equal to the sum of an expected spot-rate change,  a bond risk premium,  and the convexity bias

---
# EXPECTATIONS

- A steeply upward-sloping curve may indicate market expectations of near-term Fed tightening or of rising inflation
	 - The pure expectations hypothesis asserts that all government bonds have the same near-term expected return (as the nominally riskless short-term bond) because the return-seeking activity of risk-neutral traders removes all expected return differentials across bonds.
	 - Near-term expected returns are equalized if all bonds that have higher yields than the short-term rate are expected to suffer capital losses that offset their yield advantage.
	 - When the market expects an increase in bond yields,  the current term structure becomes upward-sloping so that any long-term bond's yield advantage and expected capital loss (owing to the expected yield increase) exactly offset each other.
- Stated differently,  if investors expect that their long-term bond investments will lose value owing to an increase in interest rates,  they will require a higher initial yield as a compensation for duration extension.
- Conversely,  expectations of yield declines and capital gains will lower current long-term bond yields below the short-term rate,  making the term structure inverted.
	 - The same logic--that positive (negative) initial yield spreads offset expected capital losses (gains) to equate near-term expected returns--also holds for combinations of bonds,  including duration-neutral yield-curve positions.
- One example is a trade that benefits from the flattening of the yield-curve between 2 and 10-year maturities:
	 - Selling a unit of the 2-year bond,
	 - Buying a duration-weighted amount (market value) of the 10-year bond,  and
	 - Putting the remaining proceeds from the sale to "cash" (very short-term bonds).
- Given the typical concave yield-curve shape,  such a curve-flattening position earns a negative carry.
	 - The trade will be profitable only if the curve flattens enough to offset the impact of the negative carry.
	 - Implied forward rates indicate how much flattening (narrowing of the twoto ten-year spread) is needed for the trade to break even.
- A concave shape means that the (upward-sloping) yield-curve is steeper in the front end than in the long end.
	 - The yield loss of moving from the two-year bond to cash is greater than the yield gain of moving from the two-year bond to the ten-year bond.
	 - Thus the yield earned from the combination of cash and tens is lower than the forgone yield from twos.

---

- The market's expectations about future yield curve steepness influence today's curve curvature
- If the market expects more curve flattening,  the negative carry of the flattening trades needs to be larger (to offset the expected capital gains),  which makes today’s yield- curve more concave (curved).
- If more flattening is expected:
	 - The negative carry of flattening trades must be larger
		  - To offset expected capital gains
	 - This makes today's curve more concave
- With no expected level/slope changes:
	 - Today's curve is horizontal
- With parallel rise expected:
	 - Today's curve is linearly increasing
- With rising rates and flattening expected:
	 - Today's curve is increasing and concave

![Untitled](file:///Users/rogerlin/Downloads/a6e011dc-0304-4657-a83a-45529d28a9b2%252FExport-d6f59a94-eb94-4c36-a827-7adc40e6813d/Yield%20Curves%20000680c441ec43c68f8d832e5af8117a/Untitled.jpeg?lastModify=1706363157)

![Untitled](data: image/svg+xml,  %3 Csvg xmlns=" http://www.w3.org/2000/svg" viewBox="0 0 1550 832"%3 E%3 C/svg%3 E)

|Stage:|Full Recession|Early Recovery|Full Recovery|Early Recession|
|---|---|---|---|---|
|Consumer Expectations:|Reviving|Rising|Declining|Falling Sharply|
|Industrial Production:|Bottoming Out|Rising|Flat|Falling|
|Interest Rates:|Falling|Bottoming Out|Rising Rapidly (Fed)|Peaking|
|Yield Curve:|Normal|Normal (Steep)|Flattening Out|Flat/Inverted|

[A 3-D View of a Chart That Predicts The Economic Future: The Yield Curve (Published 2015)](https://www.nytimes.com/interactive/2015/03/19/upshot/3d-yield-curve-economic-growth.html)

[A 3-D View of a Chart That Predicts The Economic Future: The Yield Curve (Published 2015)](https://www.nytimes.com/interactive/2015/03/19/upshot/3d-yield-curve-economic-growth.html)

## **MARKET EXPECTATIONS**

- The market's expectations of future rate changes are an important determinant of the yield-curve shape
	 - For example,  a steeply upward-sloping curve may indicate expectations of:
		  - Near-term Fed tightening
		  - Rising inflation
- The **pure expectations hypothesis** asserts that:
	 - All government bonds have the same expected return as the riskless short-term bond
	 - Return-seeking traders remove all expected return differentials across bonds
	 - Expected returns are equalized if higher yielding bonds are expected to suffer capital losses that offset their yield advantage
- When the market expects yield increases:
	 - The current term structure becomes upward sloping
	 - Long-term bonds' yield advantage and expected capital loss offset each other
	 - Investors require a higher initial yield to compensate for duration extension
- Conversely,  expected yield declines make the term structure inverted
- The same logic holds for duration-neutral positions like curve flattening trades
	 - Sell 2-year bond
	 - Buy duration-weighted 10-year bond
	 - Put remaining proceeds in cash
	 - This has a negative carry
		  - The trade is profitable only if the curve flattens enough to offset the carry
- The implied forwards indicate how much flattening is needed to break even

## **BOND RISK PREMIUM
- The bond risk premium is a longer-term bond's expected return in excess of the riskless short-term return
- The pure expectations hypothesis assumes equal expected returns across maturities
	 - In contrast:
		  - Many theories and evidence suggest varying expected returns
	 - **Bond risk premium**:
		  - Long-term bond's expected excess return over short-term riskless rate
	 - Possible reasons for positive premium:
		  - Liquidity premium hypothesis:
				- Investors dislike return volatility
				- Require compensation for longer durations
		  - Asset pricing theories
				- Premium increases with duration,  volatility,  market covariance
		  - Preferred habitat theory:
				- Premium decreases with duration
				- Long-term is perceived as riskless
- A positive premium may exist because
	 - Investors dislike return volatility and require compensation for longer durations
	 - Asset pricing theories suggest the premium should increase with:
		  - Duration
		  - Return volatility
		  - Covariance with market wealth
- The premium may decrease with duration according to the preferred habitat theory
- Empirical evidence suggests premiums vary over time
	 - High after poor economic conditions when the curve is steep
	 - High amid high inflation expectations and uncertainty
	 - Low or negative when:
		  - Treasury prices benefit from safe haven flows (1998,  2002)
		  - Bond supply is shrinking (2000)

![](Untitled6565.png)

---

# **CONVEXITY BIAS**

[Lecture Notes- Bond Duration](Lecture%20Notes-%20Bond%20Duration.md)

- Long-term bonds have high convexity
- **Convexity**:
	 - Nonlinear relationship between price and yield
	 - Prices rise more than they fall for equal yield changes
- Convexity improves returns if yields change
- More convex bonds have lower yields
	 - Investors demand less yield given prospect of convexity gains
- With no premiums or rate changes:
	 - Yields should be flat at expected return
	 - Instead they slope down due to convexity advantage
- Convexity impact increases with volatility
	 - Makes curve more concave
	 - Widens spreads between more and less convex bonds
- Exhibit 31-2 illustrates these points. This figure plots coupon bonds’ yields against their durations or,  equivalently,  zeros’ yields against their maturities,  given various rate expectations.
![](Untitled%201%201.png)

- Long-term bonds exhibit high convexity
- Convexity refers to how a bond's price-yield relationship is nonlinear
- **Convexity** means:
	 - Bond prices rise more for a given yield decline than they fall for a similar yield increase
- For a given yield,  positive convexity improves bond returns whether yields rise or fall
- More convex bonds tend to have lower yields than less convex bonds with the same duration
	 - Investors demand less yield given the prospect of return improvements from convexity
- With no premiums or expected rate changes:
	 - Yields should be flat at expected return
	 - Instead they slope down due to convexity advantage of long durations
- Convexity impact increases with volatility
	 - Makes the curve more concave
	 - Widens spreads between more and less convex bonds
![Untitled](file:///Users/rogerlin/Downloads/a6e011dc-0304-4657-a83a-45529d28a9b2%252FExport-d6f59a94-eb94-4c36-a827-7adc40e6813d/Yield%20Curves%20000680c441ec43c68f8d832e5af8117a/Untitled%203.png?lastModify=1706363157)![](Untitled21.png)
## **PUTTING THE PIECES TOGETHER**

- A steeply upward sloping curve may reflect:
	 - Rising rate expectations
	 - High required risk premium
- A strongly humped curve may reflect:
	 - Expectations of curve flattening
	 - High volatility making convexity more valuable
	 - Concave shape of risk premium curve
- If yields rise more than forwards imply,  bearish positions profit and bullish positions lose
- If yields rise less than forwards,  the opposite occurs
- Similar logic applies to yield spreads and related positions like curve flattening
# **-USING FORWARD RATE ANALYSIS IN YIELD CURVE TRADES**

**-Local expectations hypothesis:**

- All bonds/positions have equal near-term expected returns
- Upward sloping curve reflects:
	 - Expectations of rising rates
	 - Capital losses
- Convexity priced so disadvantage offsets advantage
- Yields don't reflect value
- No trades have favorable odds
- Active management only adds value with superior forecasting
**-Reality:**
- Expected returns vary across bonds
- Yields reflect value
- Certain trades have favorable odds
## **-FORWARDS AS BREAK-EVEN RATES**
- Forwards show path of break-even future rates and spreads
- Provide yardstick for subjective yield curve forecasts
- Incorporate carry impact on trade profitability
**-Examples:**
- Take bearish position only if rates expected to rise more than forwards imply
- Take bullish position if rates expected to rise less than forwards imply
- If forecast correct,  position profitable
- Ignoring forwards can lead to losses even if rate forecast correct
- Rules simple:
	 - If forwards realized,  all positions earn same return
	 - If yields rise more than forwards,  bearish profits and bullish loses
	 - If yields rise less than forwards,  opposite occurs
- Same logic applies to yield spreads and curve trades
**Exhibit 31-5**

![Untitled](file:///Users/rogerlin/Downloads/a6e011dc-0304-4657-a83a-45529d28a9b2%252FExport-d6f59a94-eb94-4c36-a827-7adc40e6813d/Yield%20Curves%20000680c441ec43c68f8d832e5af8117a/Untitled%204.png?lastModify=1706363157)

![Untitled](file:///Users/rogerlin/Downloads/a6e011dc-0304-4657-a83a-45529d28a9b2%252FExport-d6f59a94-eb94-4c36-a827-7adc40e6813d/Yield%20Curves%20000680c441ec43c68f8d832e5af8117a/Untitled%205.png?lastModify=1706363157)

- Shows dollar swap curve and 3-month and 12-month forwards in April 2004
- Comparing curves shows market expects:
	 - Rising rates
	 - Flattening curve
- Alternatively may reflect:
	 - Risk premium
	 - Convexity value
- But still reflect break-even levels

**Exhibit 31-6**

- Shows break-even path of future 3-month rates
- Alternative to whole curve view
- Based on macro forecast or Fed policy expectations
- Contrast with historical path and past expectations

## **FORWARDS AS CHEAPNESS INDICATORS**

- High forwards identify cheap sectors more clearly than spot/par rates

**Exhibit 31-7**

![Untitled](file:///Users/rogerlin/Downloads/a6e011dc-0304-4657-a83a-45529d28a9b2%252FExport-d6f59a94-eb94-4c36-a827-7adc40e6813d/Yield%20Curves%20000680c441ec43c68f8d832e5af8117a/Untitled%206.png?lastModify=1706363157)

- Once an investor has identified a sector with abnormally high forward rates (e.g.,  between 9 and 12 years),  she can exploit the cheapness of this sector by buying a bond that matures at the end of the period (12 years) and by selling a bond that matures at the beginning of the period (9 years).
 - Example from 2000:
	 - Par curve very flat
	 - But 1-year forwards spanned 100 bps
	 - High 9-12 year forwards signal cheap sector
- To exploit:
	 - Buy 12-year bond
	 - Sell 9-year bond
	 - Captures cheap 3-year rate 9 years forward
- If temporary,  gains when curve flattens and sector richens
## **-FORWARDS IN DURATION-NEUTRAL TRADES**
- Formally using forwards as cheapness indicators
- Cheap when curve very steep
	 - Cushion against rising yields
- 1-year forward = n-year zero's rolling yield
	 - Direct measure of yield advantage
- Implied spread change tells required flattening for profit
- Wide historically = expensive flattener
**-Exhibit 31-8**
- Oct 2003:
	 - High curvature signaled flattening expectations
	 - Barbell over 2-year bullet expensive
		  - Needed more flattening than forwards implied
	 - Bullet appeared cheap on yield grounds
- In hindsight,  carry signal was correct
	 - Curve flattened less than implied
	 - Bullet outperformed amid flattening
## **-YIELD CURVE TRADES**
- When the yield-curve is upward-sloping,  long-term bonds’ yield advantage over the riskless short-term bond provides a cushion against rising yields.
	 - In a sense,  duration extensions are “cheap” when the yield-curve is very steep and the cushion (positive carry) is large.
- Buying long-term,  selling short-term when curve upward sloping:
	 - Long-term yield advantage cushions against rising yields
		  - Trades lose only if rising rates exceed yield advantage
	 - Long-term bonds have larger rolling yield advantage
		  - Directly measured by 1-year forward rate f_{n-1,  n}
		  - Equals n-year zero's horizon return if curve unchanged
	 - Other measure:
		  - Change in (n-1)-year spot rate implied by forwards$(f_{1,   n} - s_{n-1})$
		  - Tells yield shift needed to offset advantage of n-year zero over 1-year zero
**Relation between 1-year forward and rolling yield**
-Approximate equation:$$f_{m,   n} \approx \frac{n S_{n}-m S_{m}}{n-m}$$
For 1-year forwards (m = n - 1):$$f_{n-1,   n} \approx S_{n}+(n-1)\left (S_{n}-S_{n-1}\right)$$
- Forward rate = sum of:
	 - N-year zero initial yield
	 - Rolldown return
		  - Zero duration * Roll down curve as ages
- Thus 1-year forwards proxy for expected returns if curve unchanged
**-Realized holding period return**$$h_{n} = S_{n}+(n-1)\left (S_{n}-S^*_{n-1}\right)$$
- Initial yield + Capital gain/loss
- Gain/loss approximated by duration * yield change
---
## -COMPONENTS **OF BOND RETURNS**
- The total expected return of any government bond position can be viewed as the sum of:
	 - 1. The **yield income**
	 - 2. The **rolldown return**
	 - 3. The **value of convexity**
	 - 4. The **duration impact of the rate view**
- A bond's near-term expected return is a sum of:
	 - Its **horizon return** given an unchanged yield-curve
	 - Its **expected return** from expected changes in the yield-curve
- The horizon return is also called the **rolling yield** because it is a sum of:
	 - The bond's **yield income**
	 - The **rolldown return** (the capital gain from the yield declining as maturity shortens on an upward-sloping curve)
## **-DETERMINANTS OF THE YIELD CURVE SHAPE**
- In the absence of risk premia and convexity bias,  the pure expectations hypothesis states that a long rate is a weighted average of expected future short rates over the life of the long bond.
	 - If short rates are expected to **rise**,  the expected future short rate (the long rate) is **higher** than the current short rate,  making the yield curve **upward sloping**.
	 - If short rates are expected to **fall**,  the expected future short rate (the long rate) is **lower** than the current short rate,  making the yield curve **inverted**.
- With no risk premia,  all bonds have the same expected return. Initial yield differentials offset expected capital gains/losses.
	 - In reality,  investors require **higher returns** for **long bonds** than short bonds.
	 - Historical returns increase substantially with duration at the front end but only modestly beyond intermediate durations.
	 - The bond risk premia make the term structure upward-sloping and **concave**,  on average.
- **Convexity bias** makes the term structure inverted. With positive bond risk premia,  convexity bias makes the term structure **humped**.
	 - On a given day,  the curve shape depends on the market's **rate expectations**.
- In the long run,  positive and negative rate expectations wash out. The **average** shape reflects **bond risk premia** and **convexity bias**.
## **DECOMPOSING FORWARD RATES**

![Untitled](file:///Users/rogerlin/Downloads/a6e011dc-0304-4657-a83a-45529d28a9b2%252FExport-d6f59a94-eb94-4c36-a827-7adc40e6813d/Yield%20Curves%20000680c441ec43c68f8d832e5af8117a/Untitled%207.png?lastModify=1706363157)

The one-period forward rate can be decomposed as:

Where:

- $E (ΔS_{n−1)}​$= Expected change in (n-1) year spot rate
- Bond Risk Premium =$E (h_n−s_1)​$
- Convexity Bias≈$−0.5×Convexity×[vol (ΔS_{n−1)}]^2​$

![Note: The one-year forward rates are based on the dollar swap curve in April 2004. The bond risk premia are based on the historical arithmetic average returns of various maturity-subsector bond portfolios between 1972–2001,  expressed in excess of the riskless one-year return. The convexity bias is based on the historical volatilities of various maturity swaps in 2004. The rate expectation term for each duration is then backed out as the difference—one-year forward rate − one-year spot rate − bond risk premium − convexity bias.](file:///Users/rogerlin/Downloads/a6e011dc-0304-4657-a83a-45529d28a9b2%252FExport-d6f59a94-eb94-4c36-a827-7adc40e6813d/Yield%20Curves%20000680c441ec43c68f8d832e5af8117a/Untitled%208.png?lastModify=1706363157)

 Note: The one-year forward rates are based on the dollar swap curve in April 2004. The bond risk premia are based on the historical arithmetic average returns of various maturity-subsector bond portfolios between 1972–2001,  expressed in excess of the riskless one-year return. The convexity bias is based on the historical volatilities of various maturity swaps in 2004. The rate expectation term for each duration is then backed out as the difference—one-year forward rate − one-year spot rate − bond risk premium − convexity bias.

## **CURRENT YIELD VS. YIELD TO MATURITY**

- **Current yield**: Annual return on bond price paid. Coupon interest / Purchase price.
- **Yield to maturity**: Total return if held to maturity. Includes interest,  reinvestment of interest,  and any price appreciation or depreciation.
- **Yield to call**: Total return if called before maturity. Assumes repurchase at face value on call date.
- **Yields to maturity/call** are more meaningful than current yield for comparing bonds.

## **THE YIELD CURVE**

- Graphs relationship between yields to maturity and time to maturity for same asset class/credit quality.
- Depicts yield differences due to maturity differences. Conveys relationship between yields and maturities (term structure).
- Normal upward slope means yields rise with maturity. Occasionally inverts but not for long.

## **THEORIES OF THE YIELD CURVE**

- **Pure Expectations Theory**: Slope reflects expected future short rates.
- **Liquidity Preference Theory**: Long rates reflect expectations and **term premium** for holding long bonds.
- **Preferred Habitat Theory**: Investors have distinct preferred habitats and require premiums to buy outside them.

## **USES OF THE YIELD CURVE**

- Leading indicator of economic conditions
- Benchmark for pricing other fixed income securities
- Fixed income strategies:
	 - **Bullet** strategy: Maturities concentrated at one point
	 - **Barbell** strategy: Maturities concentrated at two extremes
	 - **Ladder** strategy: Equal maturities periodically
	 - **Riding the curve**: Holding as bond price rises and selling before maturity
- Fixed-income managers can also seek extra return with a bond investment strategy known as riding the yield curve,  or rolling down the yield curve. When the yield curve slopes upward,  as a bond approaches maturity or “rolls down the yield curve,  ” it is valued at successively lower yields and higher prices. Using this strategy,  a bond is held for a period of time as it appreciates in price and is sold before maturity to realize the gain. As long as the yield curve remains normal,  or in an upward slope,  this strategy can continuously add to total return on a bond portfolio.