---
title: Understanding the Yield Curve Notes
tags:
  - holding_period
  - spot_rate
  - yield_curve
  - yield_spread
  - zero_coupon_bond
aliases:
  - Break-even Yield Change
  - Carry
  - Implied Forward Rate
  - Yield Spread
key_concepts:
  - Break-even yield change
  - Holding-period returns equivalence
  - Implied forward rate calculation
  - Positive and negative carry
  - Yield spread and carry
---

# Understanding the Yield Curve Notes

### EXPLANATION OF THE IMPLIED FORWARD RATE CALCULATION

The calculation of the implied two-year spot rate one year forward (denoted as $f_{1,3}$) involves equating the holding-period returns of two different bonds: a three-year zero-coupon bond and a one-year zero-coupon bond. The key idea is that the value of the two-year spot rate after one year determines the holding-period return of what is today a three-year zero-coupon bond.

#### EQUATION (5): HOLDING-PERIOD RETURNS EQUIVALENCE

The equation given for this equivalence is:

$$
s_3 - Dur_2 * (f_{1,3} - s_3) = s_1 \tag{5}
$$

Let's break down this equation and define all the variables:

- $s_3$: The current three-year spot rate.
- $s_1$: The current one-year spot rate.
- $f_{1,3}$: The implied forward rate for the period from year 1 to year 3 (i.e., the two-year spot rate one year forward).
- $Dur_2$: The duration of the two-year bond (after one year, this is the relevant duration for the three-year zero-coupon bond).
#### INTERPRETATION OF EQUATION (5)
- The left-hand side of Equation (5) represents the approximate holding-period return of the three-year zero-coupon bond, given a selling rate $f_{1,3}$.
- The right-hand side represents the holding-period return of the one-year zero-coupon bond.
### REARRANGING EQUATION (5)

Rearranging Equation (5) to solve for $f_{1,3}$:

1. **Starting with the original equation:**
	$$
    s_3 - Dur_2 \cdot (f_{1,3} - s_3) = s_1
    $$
2. **Isolating $f_{1,3} - s_3$:**
	$$
    -Dur_2 \cdot (f_{1,3} - s_3) = s_1 - s_3
    $$
3. **Dividing both sides by $-Dur_2$:**
	$$
    f_{1,3} - s_3 = \frac{s_3 - s_1}{Dur_2}
    $$

This equation shows that the break-even yield change for the three-year zero-coupon bond is equal to the yield spread divided by the bond's duration at the horizon.

### OBSERVATION ON YIELD SPREAD AND CARRY

A large yield spread $s_3 - s_1$ means that a purchase of a three-year zero financed by the sale of a one-year zero has a large positive "carry." This carry provides a cushion against rising rates because the trade profits from falling rates and suffers from rising rates. The trade will only lose money if the two-year spot rate rises above $f_{1,3}$ in one year.

### BREAK-EVEN YIELD CHANGE

The break-even yield change $f_{1,3} - s_3$ shows how much the three-year zero's yield can rise before its carry advantage is offset. If the yield curve remains unchanged and is upward-sloping, the yield of the zero-coupon bond will fall as it "rolls down" the curve (from $s_3$ to $s_1$), providing additional capital gains.

### EQUATION (6): IMPLIED CHANGE IN THE TWO-YEAR SPOT RATE

The combined effect of the yield advantage and the roll-down component leads to the question: **How much should the constant-maturity two-year spot rate change in the next year to make the three-year zero and the one-year zero earn the same return?** This is given by:

$$
\Delta\mathrm{f}_2 = (f_{1,3} - s_3) + (s_3 - s_2) = f_{1,3} - s_2 \tag{6}
$$

Where:

- $\Delta f_2$: The implied, or break-even, change in the two-year spot rate over the next year.
- $s_2$: The current two-year spot rate.
### EXPLANATION OF YIELD SPREAD AND CARRY
#### WHAT IS "CARRY"?

In finance, **carry** refers to the cost or benefit of holding an investment or a financial position over a period of time. For bonds, carry can be understood as the yield or return obtained from holding the bond.
For example:

- **Positive Carry** Occurs when the yield on the investment is greater than the cost of financing the investment.
- **Negative Carry** Occurs when the cost of financing the investment is greater than the yield obtained from the investment.
#### YIELD SPREAD

The **yield spread** is the difference between the yields of two different bonds or debt instruments. It is a measure of the difference in return between two bonds, often used to assess the relative value or attractiveness of one bond over another.

#### LARGE YIELD SPREAD AND POSITIVE CARRY

When the yield spread between a three-year zero-coupon bond and a one-year zero-coupon bond is large, it implies that the three-year bond has a significantly higher yield compared to the one-year bond. This situation is conducive to **positive carry** when you finance the purchase of the three-year bond by selling the one-year bond.

1. **High Yield on the Three-Year Bond**:
		 - The three-year zero-coupon bond offers a higher yield ($s_3$) compared to the one-year zero-coupon bond ($s_1$).

2. **Financing the Position**:
		 - To finance the purchase of the three-year bond, you sell a one-year bond. Essentially, you are borrowing at the one-year yield ($s_1$) and investing in the three-year yield ($s_3$).

3. **Positive Carry**:
		 - The **carry** in this context is the difference between the yield on the three-year bond and the cost of financing through the one-year bond.
		 - When the yield spread ($s_3 - s_1$) is large, this difference is positive, indicating that the yield from holding the three-year bond is greater than the financing cost from selling the one-year bond.
		 - This **positive carry** means you earn more from the investment in the three-year bond than what you pay to finance it through the one-year bond.
#### WHY THIS MUST BE SO

The concept of carry relies on the relationship between the yield on the investment and the cost of financing it:

- **Positive Carry** If the investment yield ($s_3$) exceeds the financing cost ($s_1$), the position generates a net positive return. The larger the yield spread, the greater this positive return or carry.
- **Risk Management** Investors often seek positive carry positions as they can provide returns even if market conditions remain stable. The positive carry offers a cushion against adverse movements in yields.
### BREAKEVEN YIELD CHANGE FOR THE THREE-YEAR ZERO-COUPON BOND
#### CONCEPT OF BREAKEVEN YIELD CHANGE

The **breakeven yield change** for a bond is the amount by which the yield on the bond can change before the benefits of holding the bond are exactly offset by the costs or risks associated with changes in the yield. For a three-year zero-coupon bond, this concept is particularly important because it helps investors understand the yield movement threshold that would negate the carry advantage of the bond.

#### DERIVATION FROM EQUATION (5)

The breakeven yield change can be derived from the holding-period returns equivalence equation:

$$
s_3 - Dur_2 \cdot (f_{1,3} - s_3) = s_1 \tag{5}
$$

Let's break this down:

- $s_3$: Current three-year spot rate.
- $s_1$: Current one-year spot rate.
- $f_{1,3}$: Implied forward rate for the period from year 1 to year 3 (two-year spot rate one year forward).
- $Dur_2$: Duration of the two-year bond (after one year, this is the relevant duration for the three-year zero-coupon bond).
#### REARRANGING EQUATION (5)

To find the breakeven yield change, we need to isolate $f_{1,3} - s_3$:

1. **Starting with the original equation:**
   $$
   s_3 - Dur_2 \cdot (f_{1,3} - s_3) = s_1
   $$
2. **Isolating $f_{1,3} - s_3$:**
   $$
   -Dur_2 \cdot (f_{1,3} - s_3) = s_1 - s_3
   $$
3. **Dividing both sides by $-Dur_2$:**
   $$
   f_{1,3} - s_3 = \frac{s_3 - s_1}{Dur_2}
   $$

This equation tells us that the **breakeven yield change** for the three-year zero-coupon bond is the yield spread divided by the bond's duration at the horizon.

#### INTERPRETATION OF THE BREAKEVEN YIELD CHANGE
1. **Yield Spread** The numerator $s_3 - s_1$ represents the yield spread between the three-year and the one-year bonds.
2. **Duration** The denominator $Dur_2$ represents the duration of the bond, which measures its sensitivity to changes in yield.
The breakeven yield change, therefore, quantifies the yield change that would offset the carry advantage of the three-year zero-coupon bond. If the yield on the three-year bond changes by this amount, the bond's price change would precisely offset the yield advantage provided by the carry.
#### WHY IT MATTERS

The breakeven yield change is crucial for understanding the risk and potential return of holding a longer-duration bond. If the actual yield change is less than the breakeven yield change, the bondholder benefits from a positive carry. If the actual yield change exceeds the breakeven yield change, the bondholder faces a loss that outweighs the carry advantage.

![500](Understanding%20the%20Yield%20Curve%20Notes-20240606051910146.png)
![500](Untitled%204-20240606050433558.png)

### SUMMARY
- The calculation aims to find the implied forward rate $f_{1,3}$ by equating the holding-period returns of a three-year and a one-year zero-coupon bond.
- The break-even yield change for the three-year zero is $f_{1,3} - s_3 = \frac{s_3 - s_1}{Dur_2}$.
- The combined effect of yield spread and roll-down effect leads to the implied change in the two-year spot rate $\Delta f_2 = f_{1,3} - s_2$.
- A large yield spread between the three-year zero-coupon bond and the one-year zero-coupon bond results in a large positive carry when you finance the purchase of the three-year bond by selling the one-year bond. This must be so because the yield obtained from the investment exceeds the cost of financing it, generating a net positive return. Carry, in this context, is the yield advantage you gain from holding the longer-duration bond over the shorter-duration bond.
- The breakeven yield change for a three-year zero-coupon bond indicates the amount by which the bond's yield can rise before the carry advantage is offset.
- It is derived from the holding-period returns equivalence equation.
- The breakeven yield change is calculated as the yield spread divided by the bond's duration.
- It is a key measure for assessing the risk and potential return of holding the bond, helping investors understand the yield movement threshold that impacts their investment.