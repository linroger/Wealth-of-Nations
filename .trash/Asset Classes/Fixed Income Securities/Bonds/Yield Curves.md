---
Owner: RRoger Lin
URL: https://www.notion.so/Yield-Curves-000680c441ec43c68f8d832e5af8117a?pvs=4
aliases:
- Alias_271_Yield Curves.md
- Alias_274_Yield Curves.md
tags:
- Bonds
- tag_example
---



- A **yield curve** graphs bond yields against their maturities
	 - Alternatively, plot yields against durations
- The two best known yield curves are:
	 1. The on-the-run Treasury curve
	 2. The interest rate swap curve

## **LIMITATIONS OF YIELD TO MATURITY**

- While convenient for relative value analysis, using a single rate to discount multiple cash flows can be problematic unless the curve is flat
	 - All cash flows are discounted at the same rate, even if the curve slope suggests different discount rates are appropriate for different cash-flow dates.
	 - The reinvestment rate depends on the yield of the bond, which varies across bonds

## **BOND PRICING USING ZERO-COUPON BONDS**

- A coupon bond can be viewed as a bundle of zero-coupon bonds (zeros)
- It can be unbundled into zeros valued separately, then rebundled
- The recombined price equals the sum of the component prices

## **SPOT RATES, FORWARD RATES AND DISCOUNT RATES**

- A single cash flow can be decomposed into one-period rates
- A multi-year spot rate is a product of one-year forwards, the basic building blocks
- **Forward rate** is the interest rate contracted today:
	 - For a loan between any two future dates
	 - Can be locked in by:
		  - 1. Buying 1 unit of n-year zero at price$P_n = \frac{100}{(1+s_n)^n}$
		  - 2. Short selling$\frac{P_n}{P_m}$units of m-year zero at price$P_m = \frac{100}{(1+s_m)^m}​$
- **Par rate** discounts a set of cash flows (par bond) to today
- **Spot rate** discounts a single future cash flow to today
- **Forward rate** discounts a future cash flow to a nearer future date
- The par, spot, and forward curves contain the same information about the term structure
## **-FORWARD RATES AS BREAK-EVEN RATES**
- Forward rates equal the spot rates implied for the future that would make all bonds earn the same return
- If forwards are realized, all self-financed bond positions earn zero return (break even)
- If the curve is unchanged, an n-year zero's horizon return equals the n-1 year forward rate
# **-RELATIONSHIPS BETWEEN FORWARD, SPOT, AND PAR RATES**
- In this example:
	 - The par and spot curves are upward sloping
	 - The forward rate curve is first upward sloping, then inverts
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
- Therefore, par curves have the flattest shape
## **-FORWARD RATES AS BREAK-EVEN RATES**
- The implied 1-year spot rates 1 year forward are:
	 - Equal to future spot rates that equate all bonds' next year return to that of 1-year zero
- The implied 1-year spot rate 1 year forward f1,2​ is:
	 - The selling rate that makes the 2-year zero's return (LHS) equal the 1-year spot rate (RHS):
- 2-year zero return=P1,in1yearP2,today−1​
- 1-year spot rate=1+s1​
- Using example numbers:
	 - 1-year spot rate s1=6​
	 - 2-year spot rate s2=8.08​
	 - Plugging into equation:
		  - 1001.1020∇⋅100(1.08082)−1=1+0.06​
		  - ∴f1,2=10.20​
- If f1,2​ is realized:
	 - The 2-year zero return equals the 1-year spot rate
	 - All bonds earn equal holding period returns
- If the curve is unchanged:
	 - An n-year zero's return equals the n-1 year forward rate

![Forward3s.png](file:///Users/rogerlin/Downloads/a6e011dc-0304-4657-a83a-45529d28a9b2%252FExport-d6f59a94-eb94-4c36-a827-7adc40e6813d/Yield%20Curves%20000680c441ec43c68f8d832e5af8117a/Forward3s.png?lastModify=1706363157)

# FORWARD RATES AND EXPECTATIONS

- Suppose, for example, that the 3-month rate now is 10.0 percent and the market expects that there will be a 0.25 percent cut in rates during the next 3 months – so that at the end of 3 months, the 3-month rate will be 9.75 percent. Given these data, what should the 6-month rate be now?
- The answer must be the rate achieved by taking the 3-month rate now, compounded with the expected 3-month rate in 3 months’ time; otherwise there would be an expected profit in going long for 3 months and short for 6 months or vice versa, and the market would tend to move the rates. In this way, the 6-month rate now can be calculated as:

	 (1 + 0.100) x (1 + 0.0975) - 1 = 0.097375 = 9.74%

# CARRY TRADE

Carry trade involves borrowing funds at a lower interest rate and investing them in assets that yield a higher interest rate. The difference between the interest earned and the interest paid is known as the “carry,” and it represents the profit from the trade.

Negative carry trade is the opposite of carry trade, where the cost of borrowing exceeds the yield on the investment. A negative carry trade occurs when an investor borrows funds at a higher interest rate and invests in assets yielding a lower interest rate. This leads to a loss, or negative carry.

### SECTION 3: CARRY TRADE AND YIELD CURVES

The relationship between carry trades and yield curves is nuanced and depends on the shape of the yield curve.

**3.1 Upward-Sloping Yield Curve**

- In an upward-sloping yield curve, long-term yields are higher than short-term yields. This scenario is favorable for carry trades as investors can borrow short-term at lower rates and invest long-term at higher rates.

**3.2 Inverted Yield Curve**

- An inverted yield curve, where long-term yields are lower than short-term yields, is unfavorable for carry trades. This scenario may lead to negative carry trades, where the cost of borrowing short-term exceeds the yield on long-term investments.

**3.3 Flat Yield Curve**

- A flat yield curve, where short-term and long-term yields are nearly equal, may offer limited opportunities for carry trades, as the difference between borrowing and investing rates is minimal.

---

# **MAIN INFLUENCES ON THE YIELD-CURVE SHAPE**

The three main influences on the Treasury yield-curve shape are:

1. **The market's expectations of future rate changes**
2. **Bond risk premiums** (expected return differentials across bonds of different maturities)
3. **Convexity bias**

These three components fully determine the yield-curve; it can be shown that the difference between each one-year forward rate and the one-year spot rate is approximately equal to the sum of an expected spot-rate change, a bond risk premium, and the convexity bias

---
# EXPECTATIONS

- A steeply upward-sloping curve may indicate market expectations of near-term Fed tightening or of rising inflation
	 - The pure expectations hypothesis asserts that all government bonds have the same near-term expected return (as the nominally riskless short-term bond) because the return-seeking activity of risk-neutral traders removes all expected return differentials across bonds.
	 - Near-term expected returns are equalized if all bonds that have higher yields than the short-term rate are expected to suffer capital losses that offset their yield advantage.
	 - When the market expects an increase in bond yields, the current term structure becomes upward-sloping so that any long-term bond's yield advantage and expected capital loss (owing to the expected yield increase) exactly offset each other.
- Stated differently, if investors expect that their long-term bond investments will lose value owing to an increase in interest rates, they will require a higher initial yield as a compensation for duration extension.
- Conversely, expectations of yield declines and capital gains will lower current long-term bond yields below the short-term rate, making the term structure inverted.
	 - The same logic--that positive (negative) initial yield spreads offset expected capital losses (gains) to equate near-term expected returns--also holds for combinations of bonds, including duration-neutral yield-curve positions.
- One example is a trade that benefits from the flattening of the yield-curve between 2and 10-year maturities:
	 - selling a unit of the 2-year bond,
	 - buying a duration-weighted amount (market value) of the 10-year bond, and
	 - putting the remaining proceeds from the sale to "cash" (very short-term bonds).
- Given the typical concave yield-curve shape, such a curve-flattening position earns a negative carry.
	 - The trade will be profitable only if the curve flattens enough to offset the impact of the negative carry.
	 - Implied forward rates indicate how much flattening (narrowing of the twoto ten-year spread) is needed for the trade to break even.
- A concave shape means that the (upward-sloping) yield-curve is steeper in the front end than in the long end.
	 - The yield loss of moving from the two-year bond to cash is greater than the yield gain of moving from the two-year bond to the ten-year bond.
	 - Thus the yield earned from the combination of cash and tens is lower than the forgone yield from twos.

---

- The market's expectations about future yield curve steepness influence today's curve curvature
- If the market expects more curve flattening, the negative carry of the flattening trades needs to be larger (to offset the expected capital gains), which makes today’s yield- curve more concave (curved).
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

![Untitled](data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1550 832"%3E%3C/svg%3E)

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
	 - For example, a steeply upward-sloping curve may indicate expectations of:
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
- Conversely, expected yield declines make the term structure inverted
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
				- Premium increases with duration, volatility, market covariance
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
		  - Treasury prices benefit from safe haven flows (1998, 2002)
		  - Bond supply is shrinking (2000)

![](Untitled6565.png)

---

# **CONVEXITY BIAS**

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
- Exhibit 31-2 illustrates these points. This figure plots coupon bonds’ yields against their durations or, equivalently, zeros’ yields against their maturities, given various rate expectations.
![](Untitled%201%201.png)

- Long-term bonds exhibit high convexity
- Convexity refers to how a bond's price-yield relationship is nonlinear
- **Convexity** means:
	 - Bond prices rise more for a given yield decline than they fall for a similar yield increase
- For a given yield, positive convexity improves bond returns whether yields rise or fall
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
- If yields rise more than forwards imply, bearish positions profit and bullish positions lose
- If yields rise less than forwards, the opposite occurs
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
- If forecast correct, position profitable
- Ignoring forwards can lead to losses even if rate forecast correct
- Rules simple:
	 - If forwards realized, all positions earn same return
	 - If yields rise more than forwards, bearish profits and bullish loses
	 - If yields rise less than forwards, opposite occurs
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

- Once an investor has identified a sector with abnormally high forward rates (e.g., between 9 and 12 years), she can exploit the cheapness of this sector by buying a bond that matures at the end of the period (12 years) and by selling a bond that matures at the beginning of the period (9 years).
 - Example from 2000:
	 - Par curve very flat
	 - But 1-year forwards spanned 100 bps
	 - High 9-12 year forwards signal cheap sector
- To exploit:
	 - Buy 12-year bond
	 - Sell 9-year bond
	 - Captures cheap 3-year rate 9 years forward
- If temporary, gains when curve flattens and sector richens
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
- In hindsight, carry signal was correct
	 - Curve flattened less than implied
	 - Bullet outperformed amid flattening
## **-YIELD CURVE TRADES**
- When the yield-curve is upward-sloping, long-term bonds’ yield advantage over the riskless short-term bond provides a cushion against rising yields.
	 - In a sense, duration extensions are “cheap” when the yield-curve is very steep and the cushion (positive carry) is large.
- Buying long-term, selling short-term when curve upward sloping:
	 - Long-term yield advantage cushions against rising yields
		  - Trades lose only if rising rates exceed yield advantage
	 - Long-term bonds have larger rolling yield advantage
		  - Directly measured by 1-year forward rate f_{n-1,n}
		  - Equals n-year zero's horizon return if curve unchanged
	 - Other measure:
		  - Change in (n-1)-year spot rate implied by forwards$(f_{1,n} - s_{n-1})$
		  - Tells yield shift needed to offset advantage of n-year zero over 1-year zero
**Relation between 1-year forward and rolling yield**
-Approximate equation:$$f_{m, n} \approx \frac{n S_{n}-m S_{m}}{n-m}$$
For 1-year forwards (m = n - 1):$$f_{n-1, n} \approx S_{n}+(n-1)\left(S_{n}-S_{n-1}\right)$$
- Forward rate = sum of:
	 - n-year zero initial yield
	 - Rolldown return
		  - Zero duration * Roll down curve as ages
- Thus 1-year forwards proxy for expected returns if curve unchanged
**-Realized holding period return**$$h_{n} = S_{n}+(n-1)\left(S_{n}-S^*_{n-1}\right)$$
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
- In the absence of risk premia and convexity bias, the pure expectations hypothesis states that a long rate is a weighted average of expected future short rates over the life of the long bond.
	 - If short rates are expected to **rise**, the expected future short rate (the long rate) is **higher** than the current short rate, making the yield curve **upward sloping**.
	 - If short rates are expected to **fall**, the expected future short rate (the long rate) is **lower** than the current short rate, making the yield curve **inverted**.
- With no risk premia, all bonds have the same expected return. Initial yield differentials offset expected capital gains/losses.
	 - In reality, investors require **higher returns** for **long bonds** than short bonds.
	 - Historical returns increase substantially with duration at the front end but only modestly beyond intermediate durations.
	 - The bond risk premia make the term structure upward-sloping and **concave**, on average.
- **Convexity bias** makes the term structure inverted. With positive bond risk premia, convexity bias makes the term structure **humped**.
	 - On a given day, the curve shape depends on the market's **rate expectations**.
- In the long run, positive and negative rate expectations wash out. The **average** shape reflects **bond risk premia** and **convexity bias**.
## **DECOMPOSING FORWARD RATES**

![Untitled](file:///Users/rogerlin/Downloads/a6e011dc-0304-4657-a83a-45529d28a9b2%252FExport-d6f59a94-eb94-4c36-a827-7adc40e6813d/Yield%20Curves%20000680c441ec43c68f8d832e5af8117a/Untitled%207.png?lastModify=1706363157)

The one-period forward rate can be decomposed as:

Where:

- $E(ΔS_{n−1)}​$= Expected change in (n-1) year spot rate
- Bond Risk Premium =$E(h_n−s_1)​$
- Convexity Bias≈$−0.5×Convexity×[vol(ΔS_{n−1)}]^2​$

![Note: The one-year forward rates are based on the dollar swap curve in April 2004. The bond risk premia are based on the historical arithmetic average returns of various maturity-subsector bond portfolios between 1972–2001, expressed in excess of the riskless one-year return. The convexity bias is based on the historical volatilities of various maturity swaps in 2004. The rate expectation term for each duration is then backed out as the difference—one-year forward rate − one-year spot rate − bond risk premium − convexity bias.](file:///Users/rogerlin/Downloads/a6e011dc-0304-4657-a83a-45529d28a9b2%252FExport-d6f59a94-eb94-4c36-a827-7adc40e6813d/Yield%20Curves%20000680c441ec43c68f8d832e5af8117a/Untitled%208.png?lastModify=1706363157)

	 Note: The one-year forward rates are based on the dollar swap curve in April 2004. The bond risk premia are based on the historical arithmetic average returns of various maturity-subsector bond portfolios between 1972–2001, expressed in excess of the riskless one-year return. The convexity bias is based on the historical volatilities of various maturity swaps in 2004. The rate expectation term for each duration is then backed out as the difference—one-year forward rate − one-year spot rate − bond risk premium − convexity bias.

## **CURRENT YIELD VS. YIELD TO MATURITY**

- **Current yield**: Annual return on bond price paid. Coupon interest / Purchase price.
- **Yield to maturity**: Total return if held to maturity. Includes interest, reinvestment of interest, and any price appreciation or depreciation.
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
- Fixed-income managers can also seek extra return with a bond investment strategy known as riding the yield curve, or rolling down the yield curve. When the yield curve slopes upward, as a bond approaches maturity or “rolls down the yield curve,” it is valued at successively lower yields and higher prices. Using this strategy, a bond is held for a period of time as it appreciates in price and is sold before maturity to realize the gain. As long as the yield curve remains normal, or in an upward slope, this strategy can continuously add to total return on a bond portfolio.

---

# **FUTURES, FORWARDS, AND OPTIONS CONTRACTS**
## **FUTURES CONTRACTS**
- A futures contract is an agreement to buy or sell a specified amount of a commodity, financial instrument, or index at a specified price on a specified date.
- The buyer of a futures contract is long the futures.
- The seller of a futures contract is short the futures.
- Financial futures contracts include:
	 - Interest rate futures
	 - Stock index futures
	 - Currency futures
- Example:
	 - X buys a futures contract to buy a 6% 5-year Treasury note in 1 year for$100
	 - Y sells a futures contract, agreeing to sell the note in 1 year for$100
	 - If market price in 1 year is 110,Xprofits​10 and Y loses$10
	 - If market price in 1 year is 90,Xloses​10 and Y profits$10
- Marking to market:
	 - Investor's equity in the position changes daily with price fluctuations
	 - Gains increase equity, losses decrease equity
	 - If equity falls below exchange minimum, investor must add margin
	 - If equity rises, investor may withdraw funds
## **FORWARD CONTRACTS**
- A customized, non-standardized agreement for future delivery of a commodity or financial instrument.
- Traded over-the-counter, not on an exchange.
- Intended for final settlement, though some settle in cash.
- Exposes both parties to credit risk of default.
## **DIFFERENCES BETWEEN FUTURES AND FORWARDS**
- Futures are standardized, forwards are customized.
- Futures traded on exchanges, forwards over-the-counter.
- Futures rarely settled by delivery, forwards intended for delivery.
- Futures have minimal credit risk due to exchange clearinghouse. Forwards have bilateral credit risk.
## **OPTION CONTRACTS**
- Gives buyer the right, but not obligation, to buy or sell an instrument at a specified price (strike) by a specified date (expiration).
- Seller (writer) grants the right in exchange for the option premium.
- Call option gives right to buy the instrument.
- Put option gives right to sell the instrument.
- Buyer is long the option, seller is short.
- Example:
	 - 1-year call option on 5-year Treasury note with$100 strike
	 - If price rises to 110,buyerexercisesandprofits​8 (110value−​100 strike -$2 premium)
	 - If price falls below 100,buyerdoesnotexerciseandloses​2 premium
- Options on futures called futures options, traded on exchanges.
	 - Options on cash instruments traded over-the-counter or on exchanges.
-## **DIFFERENCES BETWEEN OPTIONS AND FUTURES/FORWARDS**
- Option buyer has right, not obligation. Seller has obligation.
- Option buyer pays premium to seller. No premium for futures/forwards.
- Futures long and short have symmetric risk/reward.
- Option long risk is limited to premium paid. Short risk is unlimited.

# **TREASURY BOND FUTURES CONTRACT**

- - Prices are quoted in terms of a hypothetical 20-year 6% T-bond, but many different actual T-bonds can be delivered.
- Any T-bond with 15-25 years remaining maturity on the first day of the delivery month is acceptable.
- The Ultra Long T-bond futures contract differs in requiring ≥ 25 years remaining maturity.
- The short seller must deliver$100,000 face value of a qualifying T-bond.
- The futures price is adjusted by a conversion factor reflecting the price the bond would sell for at 6% yield.
- The conversion factor is constant over time for a given bond and delivery month.
- The short seller chooses which qualifying bond to deliver and when in the delivery month.
- The buyer pays the futures price x conversion factor + accrued interest.
- The contract is physically settled by delivery of a qualifying bond, not cash-settled.
- The delivery mechanism provides options that make the contract successful:
	 - **Cheapest-to-deliver option**: The short can deliver the cheapest qualified bond and make a more profitable delivery.
	 - **Timing option**: Within CME guidelines, the short chooses the delivery date and can time it advantageously.
	 - **Wildcard play**: The short can give delivery notice after the settlement price is fixed. In a falling market, this allows profiting from the fixed price.
---

## **TREASURY NOTE FUTURES**

- There are 7 Treasury note futures contracts
	 - 10-year on-the-run
	 - 10-year
	 - Ultra 10-year
	 - 5-year on-the-run
	 - 5-year
	 - 2-year on-the-run
	 - 2-year
- 4 are modeled after the T-bond futures contract and traded on CME.
- The on-the-run contracts are cash-settled
- 10-year note futures:
	 - Underlying is$100,000 face of hypothetical 10-year 6% note.
	 - Deliverable notes must have 6.5-10 year maturity on first delivery day.
	 - Same delivery options as T-bond futures.
- 5-year note futures
	 - Underlying is$100,000 face note with 4-5 year maturity on first delivery day.
- 2-year note futures:
	 - Underlying is$200,000 face note with 1-2 year maturity on first delivery day.
	 - Original maturity ≤ 5 years, 3 months.
- The 6% coupon is far from current yields, inflating futures price.
- Actual delivery bonds are converted to 6% theoretical bond.
- Cheapest-to-deliver has lowest converted futures price. Typically lower duration when yields < 6%, higher when > 6%.

## **TREASURY BILL FUTURES**

- First short-term debt instrument futures contract.
- Based on$1 million face value 3-month T-bills.
- Quoted as "price" which is 100 - annualized rate.
- Example: 97.50 price = 2.50% rate
- Invoice price depends on rate and days to maturity.
- Simpler than T-bond/note futures
	 - Only one deliverable issue - 3-month T-bills.
	 - Narrow delivery window, set in advance.
	 - No conversion factors or wildcard play.
- Provides means to hedge/speculate on short end of yield curve.

**Example 1**

> To illustrate this, let us take a look at the 2020 September 10-year Treasury futures contract as of June 10, 2020. The futures price is 138-05+, optically quite high, given the gap between the 6% theoretical coupon and the below 1% 10-year yield these days. The following table shows three of the many eligible securities:

Security, Price,Conversion Factor,Gross Basis

T 2 3/8 05/15/27,112-05,1⁄4, 0.8072, 20.215

T 2 1⁄4 08/15/27 ,111-18,3⁄4, 0.7943, 58.753

T 0 5/8 03/31/27,100-09,0.7142, 51.165

_Question: Which bond is the cheapest-to-deliver?_

**Solution:** To find the cheapest-to-deliver, we look at the gross basis. The lower the gross basis, the cheaper it is to deliver that bond.

The first bond, T 2 3/8 05/15/27, has the lowest gross basis of 20.215. Therefore, this is the cheapest-to-deliver bond.

**Example 2**

> The actual price that the buyer pays the seller is calculated using the usual formula for Treasury bills: Invoice price = 1,000,000×[1−rate×(daystomaturity/360)]wheretherateisexpressedindecimalform.Asthisformulashows,eachbasispointchangeintheinterestrate(oreach0.01changeinthefuturesprice)leadstoa​25 change in the invoice price for a 90-day bill.

_Question: If the 90-day T-bill futures price is 96.50 (implying a rate of 3.50%), what is the invoice price for a contract with 60 days to maturity?_

**Solution:

- Futures price = 96.50
- Rate = 100 - Futures price = 100 - 96.50 = 3.50%
- Days to maturity = 60
- Rate in decimal form = 0.035
Plugging into the formula
- Invoice price = 1,000,000x[1−0.035x(60/360)]=​1,000,000 x [1 - 0.0175] = 1,000,000x0.9825=​982,5
Therefore, with a futures price of 96.50 and 60 days to maturity, the invoice price is$982,500.

---

**Treasury Bill Futures Contract**

The actual invoice price paid by the buyer of the futures contract is calculated using the standard T-bill pricing formula:

Invoice Price=$1,000,000×[1−(rate×days to maturity/360)]​

Where the rate is expressed as a decimal, not percent.

As this formula shows, a 0.01 change in the futures price is equivalent to a $25 change in the invoice price for a 90-day T-bill.

**Example 2**

The actual price that the buyer pays the seller is calculated using the usual formula for Treasury bills:

where the rate is expressed in decimal form. As this formula shows, each basis point change in the interest rate (or each 0.01 change in the futures price) leads to a $25 change in the invoice price for a 90-day bill.

_Question:_ If the 90-day T-bill futures price is 96.50 (implying a rate of 3.50%), what is the invoice price for a contract with 60 days to maturity?

_Solution:

- Futures price = 96.50
- Rate = 100 - Futures price = 100 - 96.50 = 3.50%
- Days to maturity = 60
- Rate in decimal form = 0.035
Therefore, with a futures price of 96.50 and 60 days to maturity, the invoice price is$982,500.
The Treasury bill futures contract is simpler than the Treasury bond and note futures contracts in several ways
- There is effectively only one deliverable security - Treasury bills with exactly 3 months remaining maturity.
- The delivery window is very narrow, just 3 days, and set well in advance
- There are no conversion factors or wildcard play possible.

Despite its simplicity, the T-bill futures contract provides an important means to hedge or speculate on the short end of the yield curve. The T-bill rate is a benchmark for other short-term rates, so the futures contract fills a key need for many market participants.

---

the total expected return of any government bond position can be viewed as the sum of a few simple building blocks: (1) the yield income, (2) the rolldown return, (3) the value of convexity, and (4) the duration impact of the rate view

A bond’s near-term expected return is a sum of its horizon return given an unchanged yield-curve and its expected return from expected changes in the yield-curve. The first item, the horizon return, is also called the rolling yield because it is a sum of the bond’s yield income and the rolldown return (the capital gain that the bond earns because its yield declines as its maturity shortens and it “rolls down” an upward-sloping yield-curve). The second item, the expected return from expected changes in the yield-curve, can be approximated by duration and convexity effects. The duration impact is zero if the yield-curve is expected to remain unchanged, but it may be the main source of expected return if the rate predictions are based on an investor’s or economist’s market view or on a quantitative forecasting model.

Expectations for parallel increases in yields tend to make today’s term structure linearly upward sloping, and expectations for falling yields tend to make today’s term structure inverted. Expectations for future curve flattening induce today’s spotand forward-rate curves to be concave (functions of maturity), and expectations for future curve steepening induce today’s spotand forward-rate curves to be convex

- The traditional intuition is based on the pure expectations hypothesis. In the absence of risk premia and convexity bias, a long rate is a weighted average of the expected short rates over the life of the long bond. If the short rates are expected to rise, the expected average future short rate (i.e., the long rate) is higher than the current short rate, making today’s term structure upward-sloping.
- A similar logic explains why expectations of falling rates make today’s term structure inverted.
- The absence of risk premia means that all bonds, independent of maturity, have the same near-term expected return. Recall that a bond’s holding- period return equals the sum of the initial yield and the capital gains/losses that yield changes cause. Therefore, if all bonds are to have the same expected return, initial yield differentials across bonds must offset any expected capital gains/ losses.
- The preceding analysis presumes that all bond positions have the same near-term expected returns. In reality, investors require higher returns for holding long bonds than short bonds.
- Historical average returns increase substantially with duration at the front end of the curve but only modestly beyond intermediate durations. Thus the bond risk premia make the term structure upward-sloping and concave, on average.
- A positively convex price/yield-curve has the property that a given yield decline raises the bond price more than a yield increase of equal magnitude reduces it. All else equal, this property makes a high-convexity bond more valuable than a lowconvexity bond, especially if the volatility is high. It follows that investors tend to accept a lower initial yield for a more convex bond because they have the prospect of enhancing their returns as a result of convexity. Because a long bond exhibits much greater convexity than a short bond, it can have a lower yield and yet offer the same near-term expected return

Thus, in the absence of bond risk premia, the convexity bias would make the term structure inverted. In the presence of positive bond risk premia, the convexity bias tends to make the term structure humped—because the negative effect of convexity bias overtakes the positive effect of bond risk premia only at long durations. An increase in the interest-rate volatility makes the bias stronger and thus tends to make the term structure more humped

---

- Forward rates are good measures of the mar- ket’s rate expectations only if the bond risk premia and the convexity bias can be ignored.
- The steepness of the curve on a given day depends mainly on the market’s view regarding the rate direction, but in the long run, the impact of positive and negative rate expecta- tions largely washes out. Therefore, the average upward slope of the yield- curve is mainly attributable to positive bond risk premia.
- On a given day, the spot-rate curve is especially concave (humped) if market participants have strong expec- tations of future curve flattening or of high future volatility. In the long run, the reshaping expectations should wash out, and the average concave shape of the term structure reflects the concavity of the risk premium curve and the convexity bias.

## DECOMPOSING FORWARD RATES INTO THEIR MAIN DETERMINANTS

- Exhibit 32-1 shows how the yield change of an n-year zero-coupon bond over one period (dashed arrow) can be split to the rolldown yield change and the one- period change in an n − 1 year constant-maturity spot rate sn−1(∆sn−1=s∗n−1−sn−1)​ (two solid arrows).4 A zero-coupon bond’s price can be split in a similar way (see Appendix 32A). Thus an n-year zero’s holding-period return over the next period h_{n} is
- hn​ = return if the curve is unchanged + return from the curve changes = rolling yield + percentage price change (at horizon) ≈ (one-period) forward rate + [(−duration × ∆Sn−1​)
- The second source of a zero’s holding-period return, the price change caused by the yield-curve shift, is approximated very well by duration and convexity effects for all but extremely large yield-curve shifts.
- It is more interesting to relate the forward rates to expected returns and expected rate changes than to the realized ones. We take expectations of both sides of Eq. (32-1), split the bond’s expected holding-period return into the short rate and the bond risk premium, and recall that E(∆sn−1)2≈[vol(∆sn−1)]​
- Then we can rearrange the equation to express the one-period forward rate as a sum of the other terms:
	 - Forward rate ≈ short rate + duration × E(∆sn−1​)
- bond risk premium + convexity bias (32-2) where bond risk premium = E(hn−s1)​, and convexity bias ≈ −0.5 × convexity × [vol(∆sn−1)]2​ . If we move the short rate to the left-hand side of the equation, we decom- pose the “forward-spot premium” (fn−1,n–s1)​ into a rate-expectation term, a risk-premium term, and a convexity term

---

- It is more interesting to relate the forward rates to expected returns and expected rate changes than to the realized ones. We take expectations of both sides of Eq. (32-1), split the bond’s expected holding-period return into the short rate and the bond risk premium, and recall that E(∆sn−1)2≈[vol(∆sn−1)]2​. Then we can rearrange the equation to express the one-period forward rate as a sum of the other terms: Forward rate ≈ short rate + duration × E(∆sn−1​)
- bond risk premium + convexity bias (32-2) where bond risk premium = E(hn−s1)​, and convexity bias ≈ −0.5 × convexity × [vol(∆sn−1)]2​  . If we move the short rate to the left-hand side of the equation, we decom- pose the “forward-spot premium” (fn−1,n–s1)​ into a rate-expectation term, a risk-premium term, and a convexity term We interpret the expectations in Eq. (32-2) as the market’s rate and volatility expec- tations and as the expected risk premium that the market requires for holding long-term bonds. The market’s expectations are weighted averages of individ- ual market participants’ expectations.

---

![Untitled](file:///Users/rogerlin/Downloads/a6e011dc-0304-4657-a83a-45529d28a9b2%252FExport-d6f59a94-eb94-4c36-a827-7adc40e6813d/Yield%20Curves%20000680c441ec43c68f8d832e5af8117a/Untitled%209.png?lastModify=1706363157)

E(ΔSn−1)2≈[vol(ΔSn−1)]2​

- Current yield is the annual return earned on the price paid for a bond. It is calculated by dividing the bond's annual coupon interest payments by its purchase price.
- Yield to maturity reflects the total return an investor receives by holding the bond until it matures. A bond’s yield to maturity reflects all of the interest payments from the time of purchase until maturity, including interest on interest. Equally important, it also includes any appreciation or depreciation in the price of the bond.
- Yield to call is calculated the same way as yield to maturity, but assumes that a bond will be called, or repurchased by the issuer before its maturity date, and that the investor will be paid face value on the call date.
- Because yield to maturity (or yield to call) reflects the total return on a bond from purchase to maturity (or the call date), it is generally more meaningful for investors than current yield. By examining yields to maturity, investors can compare bonds with varying characteristics, such as different maturities, coupon rates or credit quality.

## WHAT IS THE YIELD CURVE?
- The yield curve is a line graph that plots the relationship between yields to maturity and time to maturity for bonds of the same asset class and credit quality. The plotted line begins with the spot interest rate, which is the rate for the shortest maturity, and extends out in time, typically to 30 years.
- A yield curve depicts yield differences, or yield spreads, that are due solely to differences in maturity. It therefore conveys the overall relationship that prevails at a given time in the marketplace between bond interest rates and maturities. This relationship between yields and maturities is known as the term structure of interest rates.
- The normal shape, or slope, of the yield curve is upward (from left to right), which means that bond yields usually rise as maturity extends. Occasionally, the yield curve slopes downward, or inverts, but it generally does not stay inverted for long.
- The Pure Expectations Theory holds that the slope of the yield curve reflects only investors’ expectations for future short-term interest rates. Much of the time, investors expect interest rates to rise in the future, which accounts for the usual upward slope of the yield curve.
- The Liquidity Preference Theory, an offshoot of the Pure Expectations Theory, asserts that long-term interest rates not only reflect investors’ assumptions about future interest rates but also include a premium for holding long-term bonds, called the term premium or the liquidity premium. This premium compensates investors for the added risk of having their money tied up for a longer period, including the greater price uncertainty. Because of the term premium, long-term bond yields tend to be higher than short-term yields, and the yield curve slopes upward.
- Another variation on the Pure Expectations Theory, the Preferred Habitat Theory states that in addition to interest rate expectations, investors have distinct investment horizons and require a meaningful premium to buy bonds with maturities outside their “preferred” maturity, or habitat. Proponents of this theory believe that short-term investors are more prevalent in the fixed-income market and therefore, longer-term rates tend to be higher than short-term rates.
- A sharply upward sloping, or steep yield curve, has often preceded an economic upturn. The assumption behind a steep yield curve is interest rates will begin to rise significantly in the future. Investors demand more yield as maturity extends if they expect rapid economic growth because of the associated risks of higher inflation and higher interest rates, which can both hurt bond returns.
- A sharply upward sloping, or steep yield curve, has often preceded an economic upturn. The assumption behind a steep yield curve is interest rates will begin to rise significantly in the future. Investors demand more yield as maturity extends if they expect rapid economic growth because of the associated risks of higher inflation and higher interest rates, which can both hurt bond returns.

---

- A flat yield curve frequently signals an economic slowdown. The curve typically flattens when the Federal Reserve raises interest rates to restrain a rapidly growing economy; short-term yields rise to reflect the rate hikes, while long-term rates fall as expectations of inflation moderate. A flat yield curve is unusual and typically indicates a transition to either an upward or downward slope.

---

- An inverted yield curve can be a harbinger of recession. When yields on short-term bonds are higher than those on long-term bonds, it suggests that investors expect interest rates to decline in the future, usually in conjunction with a slowing economy and lower inflation. Historically, the yield curve has become inverted 12 to 18 months before a recession

---

- What are the different uses of the yield curve?
- The yield curve provides a reference tool for comparing bond yields and maturities that can be used for several purposes.
	 - First, the yield curve has an impressive record as a leading indicator of economic conditions, alerting investors to an imminent recession or signaling an economic upturn, as noted above.
- Second, the yield curve can be used as a benchmark for pricing many other fixedincome securities. Because U.S. Treasury bonds have no perceived credit risk, most fixed-income securities, which do entail credit risk, are priced to yield more than Treasury bonds.
	 - For example, a three-year, high-quality corporate bond could be priced to yield 0.60%, or 60 basis points, more than the three-year Treasury bond. A three-year, high-yield bond could be valued 4% more than the comparable Treasury bond, or 400 basis points “over the curve.”
- Third, by anticipating movements in the yield curve, fixed-income managers can attempt to earn above-average returns on their bond portfolios. Several yield curve strategies have been developed in an attempt to boost returns in different interestrate environments.

---

- Three yield curve strategies focus on spacing the maturity of bonds in a portfolio.
	 - In a bullet strategy, a portfolio is structured so that the maturities of the securities are highly concentrated at one point on the yield curve.
		  - For example, most of the bonds in a portfolio may mature in 10 years. In a barbell strategy, the maturities of the securities in a portfolio are concentrated at two extremes, such as five years and 20 years.
	 - In a ladder strategy, the portfolio has equal amounts of securities maturing periodically, usually every year. In general, a bullet strategy outperforms when the yield curve steepens, while a barbell outperforms when the curve flattens.
	 - Investors typically use the laddered approach to match a steady liability stream and to reduce the risk of having to reinvest a significant portion of their money in a low interest-rate environment.

---

- Fixed-income managers can also seek extra return with a bond investment strategy known as riding the yield curve, or rolling down the yield curve.
	 - When the yield curve slopes upward, as a bond approaches maturity or “rolls down the yield curve,” it is valued at successively lower yields and higher prices.
		  - Using this strategy, a bond is held for a period of time as it appreciates in price and is sold before maturity to realize the gain.
		  - As long as the yield curve remains normal, or in an upward slope, this strategy can continuously add to total return on a bond portfolio.

