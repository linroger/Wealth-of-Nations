---
title: -*coding utf-8 -*import math
tags: 
cssclasses:
  - academia
---

# -*coding utf-8 -*import math

Below is a comprehensive internal report for the Managing Director. It focuses on the 10-year 0.125% TIPS issued on January 15,  2012,  and the 10-year 2% nominal Treasury bond issued on February 15,  2012,  using data as of January 15,  2013. The report provides (1) a theoretical derivation of duration and convexity for TIPS and nominal bonds,  (2) an empirical computation of those metrics on the provided data,  (3) a discussion of the duration-based hedge,  and (4) an evaluation of hedging effectiveness under large interest rate changes. Finally,  Python code is included to illustrate the computations. All mathematical derivations are presented in LaTeX and enclosed in … tags.

**Executive Summary**

- **Inflation-Linked Bonds (TIPS)**: Pay a coupon on a principal amount that is periodically adjusted by an inflation index (e.g.,  CPI-U). We examine a 0.125% TIPS,  originally issued on 1/15/2012,  maturing on 1/15/2022.
- **Nominal Treasury Bond**: Pays a fixed coupon on a fixed principal. We examine a 2% coupon Treasury bond,  originally issued on 2/15/2012,  maturing on 2/15/2022.
- **Duration**: Measures the sensitivity of the bond price to small changes in yields. We derive formulas for both TIPS and nominal bonds.
- **Convexity**: Measures the curvature or second derivative of the bond price–yield relationship,  capturing how duration itself changes for larger yield moves.
- **Hedging**: We construct a duration-based hedge using the nominal bond to hedge the TIPS position. We then extend the analysis to large interest rate changes and discuss the pros/cons of relying on linear approximations.

**Part I: Theoretical Derivation of Duration and Convexity**

Below is a step-by-step derivation of the key formulas for TIPS and nominal bonds,  followed by an empirical application.

**1. Pricing Setup and Notation**

1. **Action**

We first set up the basic notation used in pricing both nominal and inflation-linked bonds.

1. **Mathematical Work**

- Let

$$P = \text{price of the bond}, $$

$$C = \text{annual coupon rate (as a decimal)}, $$

$$F = \text{bond’s face (par) value}, $$

$$N = \text{number of coupon payments until maturity}, $$

$$y = \text{bond’s yield to maturity (continuously compounded)}, $$

$$t_i = \text{time (in years) to each coupon payment } i,  \quad i = 1,  2,  \ldots,  N.$$

For **TIPS**:

- Let

$$I(t_i) = \text{inflation index factor at coupon date } t_i, $$

$$I(0) = \text{inflation index factor at settlement date } t=0.$$

- The _principal_ at time is

$$F \times \frac{I(t_i)}{I(0)}.$$

1. **Reasoning**

We use standard bond pricing but must account for the principal adjustment for TIPS. The difference is that the TIPS coupon is paid on the _inflation-adjusted_ principal.

**2. Nominal Bond Price Formula**

1. **Action**

Write the price of a nominal coupon bond in terms of its yield to maturity (continuously compounded).

1. **Mathematical Work**

The nominal bond price is typically

$$

P_{\text{nom}} = \sum_{i=1}^{N} \left( C \times F \right) e^{-y t_i} + F ,  e^{-y t_N}.

$$

Since is the coupon _rate_ and is the face amount,  is the actual coupon payment in dollars each period.

1. **Reasoning**

Under continuous compounding,  a cash flow at future time is discounted by . At maturity ,  you receive both the final coupon plus the face value .

**3. TIPS Price Formula**

1. **Action**

Incorporate the inflation index adjustments into the TIPS cash flows.

1. **Mathematical Work**

A TIPS paying coupon rate on inflation-adjusted principal has timecoupon:

$$

\left(C_{\text{TIPS}} \times F \times \frac{I(t_i)}{I(0)}\right).

$$

Hence,  the TIPS price under continuous yield is

$$

P_{\text{TIPS}}

= \sum_{i=1}^{N} \left(C_{\text{TIPS}} \times F \times \frac{I(t_i)}{I(0)} \right) e^{-y_{\text{real}}, t_i}

• \left(F \times \frac{I(t_N)}{I(0)}\right) e^{-y_{\text{real}}, t_N}.

$$

If we assume _real yield to maturity_ (i.e.,  discounting using real rates),  this formula is standard in TIPS pricing.

1. **Reasoning**

TIPS cash flows differ from nominal bonds because the principal _grows_ by the factor . The real yield,  ,  applies to that inflation-adjusted set of cash flows.

**4. Macaulay Duration for Nominal Bonds**

1. **Action**

Present the standard _Macaulay duration_ formula for the nominal bond,  denoted .

1. **Mathematical Work**

For a nominal bond with continuously compounded yield ,  its Macaulay duration is

$$

D_{\text{nom}}

= \frac{

\sum_{i=1}^{N} t_i \left(C F\right) e^{-y t_i} + t_N F e^{-y t_N}

}{

\sum_{i=1}^{N} \left(C F\right) e^{-y t_i} + F e^{-y t_N}

}.

$$

1. **Reasoning**

Duration is the weighted average time to receive each discounted cash flow,  with weights proportional to present values. For very small changes in ,  the price change .

**5. Macaulay Duration for TIPS**

1. **Action**

Show the TIPS duration formula,  taking into account the inflated principal and real yield.

1. **Mathematical Work**

For TIPS discounted at real yield ,  the Macaulay duration is

$$

D_{\text{TIPS}}

= \frac{

\sum_{i=1}^{N} t_i \left(C_{\text{TIPS}} F \frac{I(t_i)}{I(0)}\right) e^{-y_{\text{real}} t_i} + t_N \left(F \frac{I(t_N)}{I(0)}\right) e^{-y_{\text{real}} t_N}

}{

\sum_{i=1}^{N} \left(C_{\text{TIPS}} F \frac{I(t_i)}{I(0)}\right) e^{-y_{\text{real}} t_i} + \left(F \frac{I(t_N)}{I(0)}\right) e^{-y_{\text{real}} t_N}

}.

$$

1. **Reasoning**

TIPS coupons and redemption amounts increase with inflation. The weighting in the numerator uses the _inflation-adjusted_ principal. In practice,  TIPS also exhibit sensitivity to changes in both real rates and expected inflation. However,  when we speak strictly of “duration to real yield, ” this is the formula.

**6. Convexity for Nominal Bonds**

1. **Action**

Recall that convexity measures the second derivative of price with respect to yield.

1. **Mathematical Work**

For a nominal bond,  the convexity _is_

_$$_

_\mathcal{C}_{\text{nom}}

= \frac{1}{P_{\text{nom}}}

\sum_{i=1}^{N} t_i^2 \left(C F\right) e^{-y t_i} + t_N^2 F e^{-y t_N}.

$$

3. **Reasoning**

The bond’s price–yield relationship is not linear. Convexity refines our approximation of . For a small yield change , 

$$

\Delta P \approx -D ,  P ,  \Delta y + \tfrac{1}{2}, \mathcal{C} ,  P ,  (\Delta y)^2.

$$

  

**7. Convexity for TIPS**

1. **Action**

Express the TIPS convexity formula,  paralleling that of nominal bonds.

2. **Mathematical Work**

For a TIPS discounted with real yield :

$$

\mathcal{C}_{\text{TIPS}}_

_= \frac{1}{P_{\text{TIPS}}}

\sum_{i=1}^{N} t_i^2 \left(C_{\text{TIPS}} F \frac{I(t_i)}{I(0)}\right) e^{-y_{\text{real}} t_i}

- t_N^2 \left(F \frac{I(t_N)}{I(0)}\right) e^{-y_{\text{real}} t_N}.

$$

3. **Reasoning**

Because TIPS have inflation-adjusted principal,  the same structure of summations applies,  except each payment is scaled by .

  

**8. Hedging Perspective: Duration to Nominal Rate vs. Real Rate**

1. **Action**

Introduce the concept of breakeven inflation and discuss that TIPS are sensitive to _real_ yields,  while nominal bonds are sensitive to _nominal_ yields.

2. **Mathematical Work**

The _breakeven inflation_ rate is

$$

\pi(0, T) = r(0, T) - r_{\text{real}}(0, T),

$$

where is the nominal rate and is the real rate for maturity .

3. **Reasoning**

A standard approach to hedging TIPS with nominal bonds is to match the _duration to nominal rates_ while being cognizant that TIPS are driven by real rates plus inflation expectations. For small changes in nominal yield,  this can be effective; for large changes,  convexity and the interplay of real vs. nominal rates must be considered.

  

</derivation>

  

  

**Part II: Empirical Computation**

  

We now apply these formulas to the **10-year 0.125% TIPS (issued 01/15/2012,  maturing 01/15/2022)** and the **10-year 2% nominal Treasury bond (issued 02/15/2012,  maturing 02/15/2022)** using the snapshot of market data as of January 15,  2013.

  

**Key Inputs**

  

From the data tables provided (excerpts only for these bonds as of 01/15/2013):

1. **Nominal Bond** (2% coupon,  maturity 02/15/2022)

• **Clean Price**: 102.652344

• **Coupon**: 2% annually

• **Accrued Interest**: 0.831522

• **Yield** (continuously compounded,  approximate from the discount factor): 1.292%–1.33% range

• **Face Value** assumed: $100

2. **TIPS** (0.125% coupon,  maturity 01/15/2022)

• **Clean Price**: 108.5742188

• **Coupon**: 0.125% annually on inflation-adjusted principal

• **Index Ratio** (from issuance to settlement): 1.0198259

• **Reference CPI**: 230.82203

• **Real Yield** (continuously compounded) can be approximated from the TIPS discount factor or market quotes in the TIPS table (often around -0.7% to 0.0% range in early 2013).

  

Below,  we illustrate a simplified approach to computing the durations,  ignoring coupon payment frequency details within the year and modeling them as annual payments for demonstration. A more precise approach would break the coupon payments out by actual schedule.

  

**Part III: Duration and Convexity Computations (Illustration)**

  

For brevity,  we highlight the structure of the computations; the accompanying Python code will show step-by-step calculations.

1. **Nominal Bond Duration**

• We assume continuous yield (1.30%).

• Maturity in 9.08 years (since we are at 01/15/2013,  it matures 02/15/2022).

• Annual coupon = $2.00 per $100 face.

2. **TIPS Duration**

• Real yield to 0.00.

• Maturity in 9.0 years.

• Annual coupon = $0.125 per $100 of _adjusted principal_.

• Current adjusted principal = .

3. **Convexity**

• We apply the same logic: sum of (or discounting at for TIPS).

  

**Part IV: Duration Hedge Ratio**

  

To hedge a long position in TIPS with a short position in the nominal bond:

  

• If you are _long_ 1 unit ($100 face) of TIPS,  you would short the above ratio of nominal bonds.

• The objective is to make the overall portfolio’s net duration (with respect to nominal yield changes) close to zero.

  

**Part V: Large Rate Changes and Convexity Adjustments**

  

When yields move significantly:

  

$$

\Delta P \approx -D \,  P \, \Delta y + \tfrac{1}{2}\, \mathcal{C}\, P\, (\Delta y)^2.

$$

• TIPS have different convexity characteristics from nominal bonds. Over large swings in nominal yields,  the mismatch in convexities can cause the hedge to be imperfect.

• Real yields and inflation expectations can shift independently of nominal yields,  further limiting a pure nominal-duration hedge.

  

**Part VI: Python Code Illustration**

  

Below is **fully contained** Python code to demonstrate how one might:

1. Store relevant data for the two bonds (nominal and TIPS).

2. Estimate yields from their prices (in a simplified manner).

3. Compute duration and convexity under annual coupon assumptions.

4. Compute the hedge ratio.

  

In an actual production environment,  yield calculations would be more precise (e.g.,  using root-finding on actual coupon cash flows with exact payment dates). Here,  we illustrate the approach with approximate annualization.

  

#!/usr/bin/env python3

# -*coding: utf-8 -*import math

  

def price_nominal_bond(face,  coupon_rate,  y,  maturity,  freq=1):

    """

    Approximate nominal bond price with continuous compounding and annual payment.

    face: face value

    coupon_rate: annual coupon rate,  e.g. 0.02 for 2%

    y: continuous yield

    maturity: years to maturity

    freq: coupon frequency (1 = annual for simplicity)

    """

    coupon_payment = coupon_rate * face

    price = 0.0

    # Assume integer count of coupons for simplicity

    N = int(round(maturity * freq))

    for i in range(1,  N+1):

        t = i / freq

        discount_factor = math.exp(-y * t)

        if i < N:

            price += coupon_payment * discount_factor

        else:

            # final coupon plus redemption

            price += (coupon_payment + face) * discount_factor

    return price

  

def duration_nominal_bond(face,  coupon_rate,  y,  maturity,  freq=1):

    """

    Approximate Macaulay duration for a nominal bond with continuous compounding.

    """

    coupon_payment = coupon_rate * face

    # Price first

    P = price_nominal_bond(face,  coupon_rate,  y,  maturity,  freq=freq)

    N = int(round(maturity * freq))

    d_sum = 0.0

    for i in range(1,  N+1):

        t = i / freq

        # Cashflow

        if i < N:

            cf = coupon_payment

        else:

            cf = coupon_payment + face

        pv_cf = cf * math.exp(-y * t)

        d_sum += t * pv_cf

    D = d_sum / P

    return D

  

def convexity_nominal_bond(face,  coupon_rate,  y,  maturity,  freq=1):

    """

    Approximate convexity for a nominal bond with continuous compounding.

    """

    coupon_payment = coupon_rate * face

    P = price_nominal_bond(face,  coupon_rate,  y,  maturity,  freq=freq)

    N = int(round(maturity * freq))

    c_sum = 0.0

    for i in range(1,  N+1):

        t = i / freq

        if i < N:

            cf = coupon_payment

        else:

            cf = coupon_payment + face

        pv_cf = cf * math.exp(-y * t)

        c_sum += (t**2) * pv_cf

    C = c_sum / P

    return C

  

def price_tips(face,  coupon_rate,  real_yield,  maturity,  index_ratio,  freq=1):

    """

    Approximate TIPS price with continuous real yield.

    face: face value

    coupon_rate: TIPS coupon rate,  e.g. 0.00125 for 0.125%

    real_yield: continuous real yield

    maturity: years to maturity

    index_ratio: I(t)/I(0) at evaluation

    freq: coupon frequency

    """

    coupon_payment = coupon_rate * face * index_ratio

    N = int(round(maturity * freq))

    price = 0.0

    for i in range(1,  N+1):

        t = i / freq

        if i < N:

            cf = coupon_payment

        else:

            # final coupon + adjusted face

            cf = coupon_payment + face * index_ratio

        price += cf * math.exp(-real_yield * t)

    return price

  

def duration_tips(face,  coupon_rate,  real_yield,  maturity,  index_ratio,  freq=1):

    """

    Macaulay duration for TIPS under continuous compounding.

    """

    P = price_tips(face,  coupon_rate,  real_yield,  maturity,  index_ratio,  freq=freq)

    coupon_payment = coupon_rate * face * index_ratio

    N = int(round(maturity * freq))

    d_sum = 0.0

    for i in range(1,  N+1):

        t = i / freq

        if i < N:

            cf = coupon_payment

        else:

            cf = coupon_payment + face * index_ratio

        pv_cf = cf * math.exp(-real_yield * t)

        d_sum += t * pv_cf

    D = d_sum / P

    return D

  

def convexity_tips(face,  coupon_rate,  real_yield,  maturity,  index_ratio,  freq=1):

    """

    Convexity for TIPS under continuous real yield.

    """

    P = price_tips(face,  coupon_rate,  real_yield,  maturity,  index_ratio,  freq=freq)

    coupon_payment = coupon_rate * face * index_ratio

    N = int(round(maturity * freq))

    c_sum = 0.0

    for i in range(1,  N+1):

        t = i / freq

        if i < N:

            cf = coupon_payment

        else:

            cf = coupon_payment + face * index_ratio

        pv_cf = cf * math.exp(-real_yield * t)

        c_sum += (t**2) * pv_cf

    C = c_sum / P

    return C

  

# ---------------------------

# Example usage (simplified)

# ---------------------------

  

if __name__ == "__main__":

    # Given/Approximate Market Info for 01/15/2013

    face_value = 100.0

    # Nominal Bond: 2%,  matures ~9.08 years from 01/15/13

    nominal_coupon_rate = 0.02

    nominal_yield = 0.013  # approximate continuous yield

    nominal_maturity = 9.08

    # TIPS: 0.125%,  matures ~9 years from 01/15/13

    tips_coupon_rate = 0.00125

    tips_real_yield = -0.0005  # approximate real yield

    tips_maturity = 9.0

    tips_index_ratio = 1.0198259  # from data

    # Compute Prices from simplified model

    model_price_nom = price_nominal_bond(face_value,  nominal_coupon_rate,  nominal_yield,  nominal_maturity)

    model_price_tips = price_tips(face_value,  tips_coupon_rate,  tips_real_yield,  tips_maturity,  tips_index_ratio)

    # Compute Durations

    D_nom = duration_nominal_bond(face_value,  nominal_coupon_rate,  nominal_yield,  nominal_maturity)

    D_tips = duration_tips(face_value,  tips_coupon_rate,  tips_real_yield,  tips_maturity,  tips_index_ratio)

    # Compute Convexities

    C_nom = convexity_nominal_bond(face_value,  nominal_coupon_rate,  nominal_yield,  nominal_maturity)

    C_tips = convexity_tips(face_value,  tips_coupon_rate,  tips_real_yield,  tips_maturity,  tips_index_ratio)

    # Hedge Ratio

    hedge_ratio = (D_tips * model_price_tips) / (D_nom * model_price_nom)

    # Print Results

    print("Nominal Bond (2%) - Model Price: {:f},  Duration: {:f},  Convexity: {:f}".format(

        model_price_nom,  D_nom,  C_nom

    ))

    print("TIPS (0.125%) - Model Price: {:f},  Duration: {:f},  Convexity: {:f}".format(

        model_price_tips,  D_tips,  C_tips

    ))

    print("Hedge Ratio (Short nominal to hedge 1 unit TIPS): {:f}".format(hedge_ratio))

  

**Explanation of the Code**

1. **price_nominal_bond**: Sums discounted cash flows of coupon + principal at maturity using continuous discounting.

2. **duration_nominal_bond**: Uses Macaulay duration logic: .

3. **convexity_nominal_bond**: Sums and normalizes by .

4. **price_tips**,  **duration_tips**,  **convexity_tips**: Similarly but for real yields,  inflation-adjusted coupons,  and principal.

5. **Main**:

• We input approximate yields and maturities (continuous compounding).

• We compute model prices,  durations,  convexities,  then compute the hedge ratio.

  

**Part VII: Conclusions and Recommendations**

1. **Duration Mismatch**: TIPS have slightly different duration from a nominal bond of similar maturity due to real yield vs. nominal yield discounting and the lower coupon.

2. **Convexity Differences**: TIPS can exhibit different convexity behavior,  especially if real yields are very low or negative,  causing the hedge to be imperfect for large yield changes.

3. **Hedge Ratio**: A simple duration hedge ratio can mitigate small parallel shifts in nominal yields; however,  if the yield curve moves nonlinearly or real vs. nominal yields diverge,  the hedge effectiveness will drop.

4. **Implementation**: In practice,  we recommend rebalancing the hedge periodically,  monitoring inflation swap markets to gauge changes in inflation expectations,  and carefully tracking the TIPS index ratio changes over time.

  

**End of Report**
