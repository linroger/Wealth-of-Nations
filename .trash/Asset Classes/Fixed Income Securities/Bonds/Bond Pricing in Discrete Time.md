---
aliases:
- Alias_275_Bond Pricing in Discrete Time.md
- Alias_278_Bond Pricing in Discrete Time.md
tags:
- tag_example
title: Bond Pricing in Discrete Time
---


# Bond Pricing in Discrete Time

Macaulay duration is the weighted average time until a bond's cash flows are received. The weights are the present value of each cash flow divided by the bond’s price.

Let's denote:

- $C$as the bond coupon payment
- $F$as the bond face value
- $i$as the time period index
- $r$as the yield-to-maturity rate (expressed in periods equivalent to the coupon payment period)
- $n$as the number of periods until maturity
- $P$as the price of the bond

The formula for the Macaulay duration (D) is:$${} D = \frac{\sum_{i=1}^n i\frac{C}{(1+r)^i} + n\frac{F}{(1+r)^n}}{P}$$

# MODIFIED DURATION

Modified duration adjusts the Macaulay duration to better measure the bond's price sensitivity to changes in yields.

The formula for the modified duration (D*) is:

$$
 D* = \frac{D}{1+r} 
$$

The bond’s price sensitivity to changes in yields increases with the modified duration.

# CONVEXITY

Convexity measures the curvature,  or the second derivative of the price function with respect to yield changes. Greater convexity is preferred because it presents greater price increases when yields fall,  and smaller price declines when yields rise,  assuming that duration and yields are constant.

The formula for convexity (C) is:

$$
 C = \frac{\sum_{i=1}^n i*(i+1) \frac{C}{(1+r)^{i+2}} + n*(n+1) \frac{F}{(1+r)^{n+2}}}{P*(1+r)^2} 
$$

In general,  the longer the bond maturity,  or the lower the coupon rate,  the greater the convexity. High convexity is desirable for fixed-income investors,  regardless of whether rates rise or fall.

---

### BOND PRICE DERIVATION

Assumptions:

- (C) is the coupon payment per period.
- (F) is the face value or par value of the bond.
- (r) is the yield to maturity (YTM) or discount rate per period.
- (n) is the total number of coupon payments until maturity.

A bond provides two types of cash flows:

1. Coupon payments,  which are received periodically until the bond matures.
1. The face value or par value received at maturity.

Therefore,  the price (P) of a bond is the Present Value (PV) of all expected cash flows:

Therefore,  the price (P) of a bond is the Present Value (PV) of all expected cash flows:$$P = \sum_{i=1}^{n} \frac{C}{(1+r)^i} + \frac{F}{(1+r)^n}$$

#### DERIVATION STEPS

1. To derive the bond price formula,  calculate the present value of an annuity (coupons) plus the present value of a lump sum (face value).
1. To derive the bond price formula,  calculate the present value of an annuity (coupons) plus the present value of a lump sum (face value).$$PV_{\text{coupons}} = C \times \left(\frac{1 - (1+r)^{-n}}{r}\right)$$
1. To derive the bond price formula,  calculate the present value of an annuity (coupons) plus the present value of a lump sum (face value).
	- This formula for$PV_{\text{coupons}}$comes from the general formula for the present value of an annuity.
	- This formula for$PV_{\text{coupons}}$comes from the general formula for the present value of an annuity.$$PV_{\text{FV}} = \frac{F}{(1+r)^n}$$
	- This formula for$PV_{\text{coupons}}$comes from the general formula for the present value of an annuity.
		  - This formula for$PV_{\text{FV}}$comes from the formula for the present value of a single future amount.
1. Combine these two present value calculations to get the total bond price.

	 - $$

 - P = PV_{\text{coupons}} + PV_{\text{FV}}$$$$P = C \times \left(\frac{1 - (1+r)^{-n}}{r}\right) + \frac{F}{(1+r)^n}
	 - $$


### DURATION DERIVATION

Macaulay Duration $D_{\text{Mac}}$ is the weighted average time to receive the bond's cash flows,  weighted by the present value of those cash flows.

#### DERIVATION STEPS

1. The weight of each cash flow is its present value divided by the bond price.
	 - Weight$(w_i = \frac{\frac{C}{(1+r)^i}}{P})$for coupons and$\frac{\frac{F}{(1+r)^n}}{P}$for the face value.
1. Multiply each weight by the time period when the cash flow occurs.
	 - Weighted time$(wt_i = i \times w_i)$for coupons and$(n \times w_{\text{FV}})$for face value.

1. Sum the weighted times to calculate Macaulay Duration.$$D_{\text{Mac}} = \sum_{i=1}^{n}wt_i + n \times w_{\text{FV}}$$

	- Explicitly:$$D_{\text{Mac}} = \frac{\sum_{i=1}^{n}i \times \frac{C}{(1+r)^i} + n \times \frac{F}{(1+r)^n}}{P}$$
	 - Substituting P from bond price derivation:$D_{\text{Mac}} = \frac{\sum_{i=1}^{n}i \times \frac{C}{(1+r)^i} + n \times \frac{F}{(1+r)^n}}{C \times \left(\frac{1 - (1+r)^{-n}}{r}\right) + \frac{F}{(1+r)^n}}$$
Duration effectively measures the bond's sensitivity to changes in interest rates,  with a longer duration indicating greater sensitivity. The specific calculation steps provided here allow the derivation of duration from the bond's cash flows and current price.

# MACAULAY DURATION

Macaulay duration is the weighted average time until a bond's cash flows are received. The weights are the present value of each cash flow divided by the bond’s price.

Let's denote:

- $C$as the bond coupon payment
- $F$as the bond face value
- $i$as the time period index
- $r$as the yield-to-maturity rate (expressed in periods equivalent to the coupon payment period)
- $n$as the number of periods until maturity
- $P$as the price of the bond

The formula for the Macaulay duration (D) is: $$
The formula for the Macaulay duration (D) is:  D = \frac{\sum_{i=1}^n i\frac{C}{(1+r)^i} + n\frac{F}{(1+r)^n}}{P}
The formula for the Macaulay duration (D) is:
The formula for the Macaulay duration (D) is: $$

#### DERIVATION STEPS
1. The weight of each cash flow is its present value divided by the bond price.
	 - Weight$(w_i = \frac{\frac{C}{(1+r)^i}}{P})$for coupons and$\frac{\frac{F}{(1+r)^n}}{P}$for the face value.
1. Multiply each weight by the time period when the cash flow occurs.
	 - Weighted time$(wt_i = i \times w_i)$for coupons and$(n \times w_{\text{FV}})$for face value.
1. Sum the weighted times to calculate Macaulay Duration.$$
1. Sum the weighted times to calculate Macaulay Duration. D_{\text{Mac}} = \sum_{i=1}^{n}wt_i + n \times w_{\text{FV}}
1. Sum the weighted times to calculate Macaulay Duration.$$
	- Explicitly:$$
	- Explicitly: D_{\text{Mac}} = \frac{\sum_{i=1}^{n}i \times \frac{C}{(1+r)^i} + n \times \frac{F}{(1+r)^n}}{P}
	- Explicitly:$$
	 - Substituting P from bond price derivation:
	 - Substituting P from bond price derivation:$$D_{\text{Mac}} = \frac{\sum_{i=1}^{n}i \times \frac{C}{(1+r)^i} + n \times \frac{F}{(1+r)^n}}{C \times \left(\frac{1 - (1+r)^{-n}}{r}\right) + \frac{F}{(1+r)^n}}$$
	 - Substituting P from bond price derivation:

Duration effectively measures the bond's sensitivity to changes in interest rates,  with a longer duration indicating greater sensitivity. The specific calculation steps provided here allow the derivation of duration from the bond's cash flows and current price.

---

Step 1. Simplify the numerator:

  The sum $\sum_{i=1}^{n}i \times \frac{C}{(1+r)^i}$ is the present value of
  each coupon payment multiplied by the time it is received.

  And for $n \times \frac{F}{(1+r)^n}$,  it's the present value of the face
  value of the bond.

  Step 2. Simplify the denominator:

  $C \times \left(\frac{1 - (1+r)^{-n}}{r}\right)$ is the present value of a
  series of $n$ coupon payments.

  And $\frac{F}{(1+r)^n}$ is the present value of the face value of the bond.

  The price of a non-callable coupon paying bond can be expressed as:

  $$
   P = C \times \left(\frac{1 - (1+r)^{-n}}{r}\right) + \frac{F}{(1+r)^n} 
  
  $$

  where:

	- P denotes the price of the bond, 
	- C is the annual coupon payment, 
	- n is the number of periods, 
	- F is the face value of the bond, 
	- r is the bond yield or interest rate.

	1 Modified Duration Dmod

  The expression for modified duration can be derived by differentiating the price function with respect to r (yield),  and expressing it in terms of Macaulay duration (Dmac):

  $$
   D_{\text{mod}} = -\frac{1}{P}\frac{dP}{dr} = -\frac{D_{\text{Mac}}}{1+r}
  
  
  $$

  The - sign in the formula refers to the inverse relationship between yield and price (i.e.,  when yield increases,  price decreases,  and vice versa).

	2 Convexity C

  Convexity can be expressed by taking the second derivative of the price function with respect to r (yield):

  $$
   C = \frac {1}{P} \times \frac {d^2P}{dr^2} 
  
  $$

  Please note that Dmod and C capture the sensitivity of the bond's price to
  changes in the yield. Dmod and C are some of the key metrics used to manage
  a bond's interest rate risk,  along with the yield to maturity.
---

# MODIFIED DURATION

Modified duration adjusts the Macaulay duration to better measure the bond's price sensitivity to changes in yields.
The formula for the modified duration (D*) is:

$$
 D* = \frac{D}{1+r} 
$$

The bond’s price sensitivity to changes in yields increases with the modified duration.

# CONVEXITY

Convexity measures the curvature,  or the second derivative of the price function with respect to yield changes. Greater convexity is preferred because it presents greater price increases when yields fall,  and smaller price declines when yields rise,  assuming that duration and yields are constant.

The formula for convexity (C) is:

$$
 C = \frac{\sum_{i=1}^n i*(i+1) \frac{C}{(1+r)^{i+2}} + n*(n+1) \frac{F}{(1+r)^{n+2}}}{P*(1+r)^2} 
$$

In general,  the longer the bond maturity,  or the lower the coupon rate,  the greater the convexity. High convexity is desirable for fixed-income investors,  regardless of whether rates rise or fall.

---

To derive the equation for the price of a non-callable coupon bond in continuous time,  we'll follow a step-by-step approach. The derivation will be based on the principles of no-arbitrage,  risk-neutral valuation,  and will incorporate the use of stochastic processes. Let's begin:

1. **Define the Bond and Cash Flows:**
	- A non-callable coupon bond pays a fixed coupon at regular intervals until maturity,  and then pays the face value.
	- Let the bond have a maturity of$T$years,  a face value of$F$,  and an annual coupon rate of$c$.

1. **Determine the Cash Flow Structure:**
	- The bond pays coupons continuously at a rate of$cF$per annum.
	- The present value of these coupons needs to be calculated from the current time$t$to maturity$T$.

1. **Assumptions:**
	- Assume a constant risk-free rate$r$for simplicity.
	- The bond is priced in a risk-neutral world,  meaning investors are indifferent to risk.

1. **Present Value of Future Cash Flows:**
	- The present value of a continuous cash flow can be calculated using the formula:

	  $$
      PV = \int_t^T e^{-r(s-t)} \cdot \text{Cash Flow at time } s \,  ds 
	  $$

	- For the coupon bond,  the cash flow is$cF$(the annual coupon payment).

1. **Calculate Present Value of Coupons:**
	- The present value of the continuous coupon payments is thus:

	  $$
      PV_{\text{coupons}} = \int_t^T e^{-r(s-t)} \cdot cF \,  ds 
	  $$

1. **Solve the Integral:**
	- Solving the integral,  we get:

	  $$
      PV_{\text{coupons}} = cF \int_t^T e^{-r(s-t)} \,  ds 
	  $$

	  $$
		= cF \left[ \frac{-1}{r} e^{-r(s-t)} \right]_t^T
	  $$

	  $$
		= cF \left( \frac{1}{r} - \frac{e^{-r(T-t)}}{r} \right)
	  $$

1. **Present Value of Face Value:**
	- The present value of the face value$F$paid at maturity is:

	  $$
      PV_{\text{face value}} = e^{-r(T-t)} \cdot F 
	  $$

1. **Price of the Bond:**
	- The price of the bond is the sum of the present value of the coupons and the present value of the face value:

	  $$
      \text{Bond Price} = PV_{\text{coupons}} + PV_{\text{face value}} 
	  $$

	  $$
		= cF \left( \frac{1}{r} - \frac{e^{-r(T-t)}}{r} \right) + e^{-r(T-t)} \cdot F
	  $$

1. **Simplify the Equation:**
	- Finally,  simplify the equation to get the general form of the pricing equation for a non-callable coupon bond in continuous time.