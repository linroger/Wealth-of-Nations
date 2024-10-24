---
alias: TIPS
aliases:
- Alias_198_TIPS Derivations.md
- TIPS
- Alias_197_TIPS Derivations.md
linter-yaml-title-alias: TIPS
tags:
- tag_example
title: TIPS
---



# TIPS Derivations
## INDEX RATIO
$$
\text{Index Ratio}(t) = \max\left(\frac{\text{Reference CPI}(t)}{\text{CPI}(t_{\text{issuance}})}, 1.0\right)
$$
## REFERENCE CPI
$$
\text{Reference CPI} = w(t)\text{CPI}(t-1) + (1-w(t))\text{CPI}(t-2)
$$

where $w(t)$ is a weight that depends on the quoted day of the month.

## COUPON PAYMENT
$$
\text{Coupon Payment}(t) = \left(\frac{\text{Coupon Rate}}{2}\right) \times 100 \times \text{Index Ratio}(t)
$$
# REAL BONDS AND TIPS
## REAL BONDS

Real bonds are bonds denoted in terms of a good instead of dollars.

### REAL DISCOUNT FACTOR
$$
Z^{\text{real}}(t,T) = e^{-r_{real}(t,T)*(T-t)}*1
$$

This defines the exchange rate between consumption goods at $t$ versus consumption goods at a later date $T$.

### REAL DISCOUNT RATE

From real discounts $Z^{\text{real}}(t,T)$, we can compute the real rate as:

$$
r_{\text{real}}(t,T) = \frac{-\ln(Z^{\text{real}}(t,T))}{(T-t)}
$$
### VALUE OF A REAL COUPON BOND

The value (in consumption goods) of a real coupon bond of maturity $T$ and coupon rate $c$ is:

$$
  \frac{c + 100}{2} \sum_{i=1}^{n} Z^{\text{real}}(t, T_i) + 100 \times Z^{\text{real}}(t,T_{{}n})
$$

where $T_i$ are coupon dates.

## DERIVATION OF ZERO COUPON TIPS PRICE

The CPI adjustment for maturity $T$, the payoff of a zero coupon TIPS at maturity is as follows:

$$
\text{Zero Coupon TIPS payoff at } T = 100 \times \frac{\text{Idx}(T)}{\text{Idx}(0)}
$$

where $\frac{\text{Idx}(T)}{\text{Idx}(0)}$ is the increase in consumption basket price between 0 and $T$.

- $\text{Idx}(T) = \text{CPI}(T)$ = real price of 1 unit of consumption basket at $T$.
- $100 \times \text{Idx}(T)$ is the real price of 100 units of the consumption basket at $T$.
- Real Present Value of $100 \times \text{Idx}(T)$ at $t$ is:
  $$
  Z_{\text{real}}(t,T) \times 100 = \text{Real PV expressed in terms of units of consumption baskets}
 $$
- Dollar Present Value of $100 \times \text{Idx}(T)$ at $t$ is:
  $$

  Z_{\text{real}}(t,T) \times 100 \times \text{Idx}(T) = \text{Current dollar PV of 100} \times \text{Idx}(T) \text{ at time } t

 $$
- Dollar Present Value of a Zero Coupon TIPS $B_{z}^{TIPS}(t)$ is:
$$

  B_{z}^{TIPS}(t)=Z^{\text{real}}(t,T) \times 100 \times \frac{\text{Idx}(t)}{\text{Idx}(0)}

 $$
$$B_{z}^{TIPS}(t)=e^{-r_{real}(t,T)*(T-t)} \times 100 \times \frac{\text{Idx}(t)}{\text{Idx}(0)}$$
 
- Dollar Present Value of a Coupon Paying TIPS $B_{c}^{TIPS}(t,T)$ is:
$$B_{c}^{TIPS}(t,T)=\frac{\text{Idx}(t)}{\text{Idx}(0)} \left$\frac{c + 100}{2} \sum_{i=1}^{n} Z^{\text{real}}(t, T_i) + 100 \times Z^{\text{real}}(t,T_{{}n})\right$$$
$$B_{c}^{TIPS}(t,T)=\frac{\text{Idx}(t)}{\text{Idx}(0)} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{-r_{real}(t,T_{i})*(T-t)} + 100 \times e^{-r_{real}(t,T)*(T-t)} \right$$$

# REAL AND NOMINAL RATES UNDER PERFECT FORESIGHT
Consider a nominal zero coupon bond at $t=0$:
$$

B_{0}(T) = 100 \times e^{-r_{\text{nom}}(T-t)}

$$
Having 100 at $t$ affords the investor:
$$

\frac{100}{\text{Idx}(T)} \text{ units of the consumption basket at } T

$$
Suppose we know the CPI index at $T$ (i.e., $\text{Idx}(T)$ is known).
### REAL PRESENT VALUE OF 100
$$

\text{Real Present Value of } \frac{100}{\text{Idx}(T)} \text{ at } 0: \frac{100}{\text{Idx}(T)} = e^{-r_{\text{real}}(0,T) \times T}

$$
### DOLLAR PRESENT VALUE OF 100
$$

\text{Dollar Present Value of } \frac{100}{\text{Idx}(T)} \text{ at } 0: 100 \times \frac{\text{Idx}(0)}{\text{Idx}(T)} = e^{-r_{\text{real}}(0,T) \times T}

$$
Since we can perfectly forecast inflation, it must follow that the two discounts are identical:
$$

e^{-r_{{nominal}}(0,T) \times T} = e^{-r_{\text{real}}(0,T) \times T} \times \frac{\text{Idx}(0)}{\text{Idx}(T)}

$$
Let $\pi$ be the continuously compounded annualized rate of inflation from 0 to $T$:
$$

\text{Idx}(T) = \text{Idx}(0) \times e^{\pi \times T}

$$
$$e^{\pi \times T}= \frac{\text{Idx}(T)}{\text{Idx}(0)}  $$
Then, under perfect foresight, the nominal interest rate is equal to the real interest rate plus inflation:
$$

r_{{nominal}}(0,T) = r_{\text{real}}(0,T) + \pi

$$
$$r_{\text{real}}(0,T)=r_{{nominal}}(0,T)-\pi $$

---

To solve for the duration of $B_{c}^{TIPS}(t,T)$ in terms of inflation $\pi$, we need to differentiate the bond price with respect to $\pi$ and then normalize it by the bond price itself.
Given the bond price equation:
$$

B_{c}^{TIPS}(t,T) = e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)}\right$

$$
We can follow these steps to derive the duration in terms of $\pi$:
1. **Differentiate $B_{c}^{TIPS}(t,T)$ with respect to $\pi$**:
$$

\frac{\partial B_{c}^{TIPS}(t,T)}{\partial \pi} = \frac{\partial}{\partial \pi} \left\{ e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)}\right$ \right\}

$$
2. **Apply the product rule**:
$$

\frac{\partial B_{c}^{TIPS}(t,T)}{\partial \pi} = e^{\pi t} \left\{ \frac{\partial}{\partial \pi} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)} \right$ \right\} + \left(\frac{\partial}{\partial \pi} e^{\pi t} \right) \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)}\right$

$$
3. **Differentiate the exponential terms**:
$$

\frac{\partial B_{c}^{TIPS}(t,T)}{\partial \pi} = e^{\pi t} \left\{ \frac{c + 100}{2} \sum_{i=1}^{n} (T_i - t) e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 (T_n - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)} \right\} + t e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)}\right$

$$
4. **Factor out common terms**:
$$

\frac{\partial B_{c}^{TIPS}(t,T)}{\partial \pi} = e^{\pi t} \left\{ \left$\frac{c + 100}{2} \sum_{i=1}^{n} (T_i - t) e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 (T_n - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)} \right$ + t \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)}\right$ \right\}

$$
5. **Normalize by the bond price**:
$$

D_{\pi}^{TIPS} = \frac{1}{B_{c}^{TIPS}(t,T)} \frac{\partial B_{c}^{TIPS}(t,T)}{\partial \pi}

$$
Substitute the expression for $B_{c}^{TIPS}(t,T)$:
$$

D_{\pi}^{TIPS} = \frac{e^{\pi t} \left\{ \left$\frac{c + 100}{2} \sum_{i=1}^{n} (T_i - t) e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 (T_n - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)} \right$ + t \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)}\right$ \right\}}{e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)}\right$}

$$
Simplify the expression:
$$

D_{\pi}^{TIPS} = \frac{\left$\frac{c + 100}{2} \sum_{i=1}^{n} (T_i - t) e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 (T_n - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)} \right$ + t \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)}\right$}{\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)}}

$$
This is the duration of $B_{c}^{TIPS}(t,T)$ in terms of inflation $\pi$.

To find the convexity of $B_{c}^{TIPS}(t,T)$ in terms of inflation $\pi$, we need to compute the second derivative of the bond price with respect to $\pi$ and then normalize it by the bond price itself. Convexity measures the sensitivity of the duration to changes in the interest rate or inflation.

### STEPS TO FIND CONVEXITY
1. **First Derivative with respect to $\pi$**:
$$

\frac{\partial B_{c}^{TIPS}(t,T)}{\partial \pi} = e^{\pi t} \left\{ \left$\frac{c + 100}{2} \sum_{i=1}^{n} (T_i - t) e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 (T_n - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)} \right$ + t \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)}\right$ \right\}

$$
2. **Second Derivative with respect to $\pi$**:
$$

\frac{\partial^2 B_{c}^{TIPS}(t,T)}{\partial \pi^2} = e^{\pi t} \left\{ \frac{\partial}{\partial \pi} \left$\frac{c + 100}{2} \sum_{i=1}^{n} (T_i - t) e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 (T_n - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)} \right$ \right\}

$$
Applying the product rule and differentiating each term inside the braces:
$$

\frac{\partial^2 B_{c}^{TIPS}(t,T)}{\partial \pi^2} = e^{\pi t} \left\{ \frac{c + 100}{2} \sum_{i=1}^{n} (T_i - t)^2 e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 (T_n - t)^2 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)} \right\} + 2t e^{\pi t} \left\{ \frac{c + 100}{2} \sum_{i=1}^{n} (T_i - t) e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 (T_n - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)} \right\} + t^2 e^{\pi t} \left\{ \frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)} \right\}

$$
3. **Simplify the Expression**:
Factor out $e^{\pi t}$:
$$

\frac{\partial^2 B_{c}^{TIPS}(t,T)}{\partial \pi^2} = e^{\pi t} \left\{ \left$\frac{c + 100}{2} \sum_{i=1}^{n} (T_i - t)^2 e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 (T_n - t)^2 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)} \right$ + 2t \left$\frac{c + 100}{2} \sum_{i=1}^{n} (T_i - t) e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 (T_n - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)} \right$ + t^2 \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)} \right$ \right\}

$$
4. **Normalize by the Bond Price**:
$$

C_{\pi}^{TIPS} = \frac{1}{B_{c}^{TIPS}(t,T)} \frac{\partial^2 B_{c}^{TIPS}(t,T)}{\partial \pi^2}

$$
Substitute the expression for $B_{c}^{TIPS}(t,T)$:
$$

C_{\pi}^{TIPS} = \frac{e^{\pi t} \left\{ \left$\frac{c + 100}{2} \sum_{i=1}^{n} (T_i - t)^2 e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 (T_n - t)^2 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)} \right$ + 2t \left$\frac{c + 100}{2} \sum_{i=1}^{n} (T_i - t) e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 (T_n - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)} \right$ + t^2 \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)} \right$ \right\}}{e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)}\right$}

$$
Simplify the expression:
$$

C_{\pi}^{TIPS} = \frac{\left\{ \left$\frac{c + 100}{2} \sum_{i=1}^{n} (T_i - t)^2 e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 (T_n - t)^2 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)} \right$ + 2t \left$\frac{c + 100}{2} \sum_{i=1}^{n} (T_i - t) e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 (T_n - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)} \right$ + t^2 \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)} \right$ \right\}}{\left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i)) (T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_n - t)}\right$}

$$
### NOTABLE FEATURES OF CONVEXITY WITH RESPECT TO INFLATION
1. **Higher Order Sensitivity**:
   - Convexity measures the rate of change of duration with respect to changes in inflation. It captures the curvature of the bond price with respect to inflation, indicating how much the bond price changes as inflation changes.
   - The inclusion of $(T_i - t)^2$ and $(T_n - t)^2$ terms in the convexity formula indicates that the bond's sensitivity to inflation is more pronounced for longer durations and later time periods.
2. **Time Dependency**:
   - Similar to the duration, convexity includes terms that depend on the current time $t$, reflecting the time decay effect on the bond's sensitivity to inflation.
3. **Coupon Structure**:
   - The $\frac{c + 100}{2}$ factor in both the numerator and the denominator shows that the bond's coupon payments significantly influence its convexity with respect to inflation.
4. **Complexity**:
   - Convexity is inherently more complex than duration because it accounts for the second-order effects of inflation changes on the bond price.
In summary, the convexity of a TIPS coupon bond with respect to inflation reflects the bond's sensitivity to changes in inflation, considering both the duration and the time decay effects. This makes the bond more responsive to inflation changes, especially for longer-term bonds and those with higher coupon rates.
---

To compute the hedge ratio for hedging a TIPS security with a nominal interest rate Treasury security, we need to equate the duration of the combined portfolio of TIPS and Treasury securities to zero. This will involve solving for the hedge ratio $k$.
Let's denote:
- $P^{TIPS}(t, T)$ as the price of the TIPS security
- $P^{Treasury}(t, T)$ as the price of the nominal interest rate Treasury security
- $D^{TIPS}$ as the duration of the TIPS security
- $D^{Treasury}$ as the duration of the nominal interest rate Treasury security
The combined portfolio consists of a long position in TIPS and a short position in Treasuries, and the hedge ratio $k$ is defined as the ratio of the value of the Treasury security position to the TIPS position. The goal is to ensure that the duration of the combined portfolio is zero. 
The hedge ratio $k$ can be found by equating the durations of the TIPS and Treasury positions:
$$

V = P^{TIPS} + k \cdot P^{Treasury}

$$
To hedge the TIPS with a nominal interest rate Treasury security, the first derivative of the combined portfolio with respect to the nominal interest rate $r_{\text{nominal}}$ must be zero:
$$

\frac{dV}{dr_{\text{nominal}}} = 0

$$
The first derivative of the TIPS price with respect to the nominal interest rate is:
$$

\frac{dP^{TIPS}}{dr_{\text{nominal}}} = - P^{TIPS} \cdot D^{TIPS}

$$
Similarly, the first derivative of the Treasury price with respect to the nominal interest rate is:
$$

\frac{dP^{Treasury}}{dr_{\text{nominal}}} = - P^{Treasury} \cdot D^{Treasury}

$$
Since the combined duration must be zero, we have:
$$

\frac{dV}{dr_{\text{nominal}}} = \frac{dP^{TIPS}}{dr_{\text{nominal}}} + k \cdot \frac{dP^{Treasury}}{dr_{\text{nominal}}} = 0

$$
Substituting the derivatives:
$$
- P^{TIPS} \cdot D^{TIPS} + k \cdot (P^{Treasury} \cdot D^{Treasury}) = 0
$$
Solving for $k$:
$$

k = \frac{P^{TIPS} \cdot D^{TIPS}}{P^{Treasury} \cdot D^{Treasury}}

$$
Simplifying further:
$$

k = \frac{D^{TIPS}}{D^{Treasury}} \cdot \frac{P^{TIPS}}{P^{Treasury}}

$$
Therefore, the hedge ratio $k$ for hedging the TIPS security with a nominal interest rate Treasury security is given by:
$$

k = \frac{D^{TIPS} \cdot P^{TIPS}}{D^{Treasury} \cdot P^{Treasury}}

$$
### CALCULATION EXAMPLE
Assume the following:
- $D^{TIPS}$ is the duration of the TIPS security.
- $P^{TIPS}$ is the price of the TIPS security.
- $D^{Treasury}$ is the duration of the nominal Treasury security.
- $P^{Treasury}$ is the price of the nominal Treasury security.
To compute the hedge ratio for hedging the TIPS security with a nominal interest rate Treasury security, we need to use the specific formulas for the duration and prices of both securities.
### TIPS DURATION AND PRICE
For TIPS:
- The price $B_{c}^{TIPS}(t,T)$ in terms of nominal rates is:
  $$

  B_{c}^{TIPS}(t,T) = e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i))(T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T))(T_n - t)}\right$

 $$
- The duration $D^{TIPS}$ with respect to nominal rates is:
  $$

  D^{TIPS} = \frac{\sum_{i=1}^{n} (T_i - t) e^{(\pi - r_{\text{nominal}}(t,T_i))(T_i - t)} + 2 (T_n - t) e^{(\pi - r_{\text{nominal}}(t,T))(T_n - t)}}{\sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i))(T_i - t)} + 2 e^{(\pi - r_{\text{nominal}}(t,T))(T_n - t)}}

 $$
### NOMINAL TREASURY DURATION AND PRICE
For a nominal Treasury bond:
- The price $P^{Treasury}$ is:
  $$

  P^{Treasury} = \frac{c \times 100}{2} \sum_{i=1}^{n} e^{-r_{\text{nominal}} T_i} + 100 e^{-r_{\text{nominal}} T_n}

 $$
- The duration $D^{Treasury}$ is:
  $$

  D^{Treasury} = \frac{\sum_{i=1}^{n} T_i e^{-r_{\text{nominal}} T_i} + T_n e^{-r_{\text{nominal}} T_n}}{P^{Treasury}}

 $$
### HEDGE RATIO CALCULATION
Now, we can plug these equations into the hedge ratio formula:
$$

k = \frac{D^{TIPS} \cdot B_{c}^{TIPS}(t,T)}{D^{Treasury} \cdot P^{Treasury}}

$$
Substitute the expressions for $D^{TIPS}$, $B_{c}^{TIPS}(t,T)$, $D^{Treasury}$, and $P^{Treasury}$:
$$

k = \frac{
\left(\frac{\sum_{i=1}^{n} (T_i - t) e^{(\pi - r_{\text{nominal}}(t,T_i))(T_i - t)} + 2 (T_n - t) e^{(\pi - r_{\text{nominal}}(t,T))(T_n - t)}}{\sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i))(T_i - t)} + 2 e^{(\pi - r_{\text{nominal}}(t,T))(T_n - t)}} \right)
\left(e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i))(T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T))(T_n - t)}\right$ \right)
}{
\left(\frac{\sum_{i=1}^{n} T_i e^{-r_{\text{nominal}} T_i} + T_n e^{-r_{\text{nominal}} T_n}}{\frac{c \times 100}{2} \sum_{i=1}^{n} e^{-r_{\text{nominal}} T_i} + 100 e^{-r_{\text{nominal}} T_n}} \right)
\left(\frac{c \times 100}{2} \sum_{i=1}^{n} e^{-r_{\text{nominal}} T_i} + 100 e^{-r_{\text{nominal}} T_n} \right)
}

$$
Simplifying the hedge ratio:
$$

k = \frac{
\left(\sum_{i=1}^{n} (T_i - t) e^{(\pi - r_{\text{nominal}}(t,T_i))(T_i - t)} + 2 (T_n - t) e^{(\pi - r_{\text{nominal}}(t,T))(T_n - t)} \right)
e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i))(T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T))(T_n - t)}\right$
}{
\left(\sum_{i=1}^{n} T_i e^{-r_{\text{nominal}} T_i} + T_n e^{-r_{\text{nominal}} T_n} \right)
}

$$
Thus, the hedge ratio $k$ is:
$$

k = \frac{
\left(\sum_{i=1}^{n} (T_i - t) e^{(\pi - r_{\text{nominal}}(t,T_i))(T_i - t)} + 2 (T_n - t) e^{(\pi - r_{\text{nominal}}(t,T))(T_n - t)} \right)
\left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_i))(T_i - t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T))(T_n - t)}\right$
}{
\left(\sum_{i=1}^{n} T_i e^{-r_{\text{nominal}} T_i} + T_n e^{-r_{\text{nominal}} T_n} \right)
\left(\frac{c \times 100}{2} \sum_{i=1}^{n} e^{-r_{\text{nominal}} T_i} + 100 e^{-r_{\text{nominal}} T_n} \right)
}

$$
This formula allows you to calculate the hedge ratio required to hedge the interest rate risk of a TIPS security using a nominal Treasury security.


To rewrite the given equation in terms of nominal rates using the given relationships, let's proceed step-by-step.
Given:
1. Let $\pi$ be the continuously compounded annualized rate of inflation from 0 to $T$:
   $$

   \text{Idx}(T) = \text{Idx}(0) \times e^{\pi \times T}

   $$
2. The relationship between nominal and real rates:
   $$

   r(0,T) = r_{\text{real}}(0,T) + \pi

   $$
3. The relationship between discount factors:
   $$

   e^{-r(0,T) \times T} = e^{-r_{\text{real}}(0,T) \times T} \times \frac{\text{Idx}(0)}{\text{Idx}(T)}

   $$
4. The relationship between real and nominal rates:
   $$

   r_{\text{real}}(0,T) = r_{\text{nominal}}(0,T) - \pi

   $$

Starting with the original equation:
$$

B_{c}^{TIPS}(t,T)=\frac{\text{Idx}(t)}{\text{Idx}(0)} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{-r_{\text{real}}(t,T_{i}) \times (T_{i}-t)} + 100 \times e^{-r_{\text{real}}(t,T) \times (T-t)} \right$

$$

We need to replace the real discount factors $e^{-r_{\text{real}}(t,T_{i}) \times (T_{i}-t)}$ and $e^{-r_{\text{real}}(t,T) \times (T-t)}$ with nominal ones.

Using the hint provided:
$$

e^{-r_{\text{nominal}}(0,T) \times T} = e^{-r_{\text{real}}(0,T) \times T} \times \frac{\text{Idx}(0)}{\text{Idx}(T)}

$$

We can express the real discount factors in terms of nominal rates:
$$

e^{-r_{\text{real}}(t,T_{i}) \times (T_{i}-t)} = e^{-r_{\text{nominal}}(t,T_{i}) \times (T_{i}-t)} \times e^{\pi \times (T_{i}-t)}

$$
and
$$

e^{-r_{\text{real}}(t,T) \times (T-t)} = e^{-r_{\text{nominal}}(t,T) \times (T-t)} \times e^{\pi \times (T-t)}

$$

Substitute these into the original equation:
$$

B_{c}^{TIPS}(t,T) = \frac{\text{Idx}(t)}{\text{Idx}(0)} \left$\frac{c + 100}{2} \sum_{i=1}^{n} \left(e^{-r_{\text{nominal}}(t,T_{i}) \times (T_{i}-t)} \times e^{\pi \times (T_{i}-t)}\right) + 100 \times \left(e^{-r_{\text{nominal}}(t,T) \times (T-t)} \times e^{\pi \times (T-t)}\right) \right$

$$

Next, simplify the terms inside the summation and the last term:
$$

B_{c}^{TIPS}(t,T) = \frac{\text{Idx}(t)}{\text{Idx}(0)} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{-r_{\text{nominal}}(t,T_{i}) \times (T_{i}-t)} \times e^{\pi \times (T_{i}-t)} + 100 \times e^{-r_{\text{nominal}}(t,T) \times (T-t)} \times e^{\pi \times (T-t)} \right$

$$

Notice that $\frac{\text{Idx}(t)}{\text{Idx}(0)}$ can be written as $e^{\pi \times t} \times e^{-\pi \times 0} = e^{\pi \times t}$:
$$

B_{c}^{TIPS}(t,T) = e^{\pi \times t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{-r_{\text{nominal}}(t,T_{i}) \times (T_{i}-t)} \times e^{\pi \times (T_{i}-t)} + 100 \times e^{-r_{\text{nominal}}(t,T) \times (T-t)} \times e^{\pi \times (T-t)} \right$

$$

Finally, combine the exponents:
$$

B_{c}^{TIPS}(t,T) = e^{\pi \times t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{-r_{\text{nominal}}(t,T_{i}) \times (T_{i}-t) + \pi \times (T_{i}-t)} + 100 \times e^{-r_{\text{nominal}}(t,T) \times (T-t) + \pi \times (T-t)} \right$

$$

Since $e^{a} \times e^{b} = e^{a+b}$, we get:
$$

B_{c}^{TIPS}(t,T) = e^{\pi \times t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_{i})) \times (T_{i}-t)} + 100 \times e^{(\pi - r_{\text{nominal}}(t,T)) \times (T-t)} \right$

$$

Therefore, the equation in terms of nominal rates is:
$$

B_{c}^{TIPS}(t,T) = e^{\pi \times t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_{i})) \times (T_{i}-t)} + 100 \times e^{(\pi - r_{\text{nominal}}(t,T)) \times (T-t)} \right$

$$




To find the first derivative of
$$

B_{c}^{TIPS}(t,T) = e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)}\right$

$$
with respect to $r_{\text{nominal}}(t,T)$, we will follow these steps:
1. Identify the terms that contain $r_{\text{nominal}}(t,T)$.
2. Differentiate those terms with respect to $r_{\text{nominal}}(t,T)$.
First, let's rewrite the equation for clarity:
$$

B_{c}^{TIPS}(t,T) = e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)}\right$

$$
Now, let's take the derivative with respect to $r_{\text{nominal}}(t,T)$:
### STEP-BY-STEP DERIVATION
#### 1. DIFFERENTIATE THE SUMMATION TERM
The summation term is:
$$

\sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)}

$$
The derivative of each exponential term $e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)}$ with respect to $r_{\text{nominal}}(t,T)$ is:
$$

\frac{\partial}{\partial r_{\text{nominal}}(t,T)} e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} = - (T_{i} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)}

$$
So, the derivative of the summation term is:
$$

\frac{\partial}{\partial r_{\text{nominal}}(t,T)} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} = \sum_{i=1}^{n} \left$- (T_{i} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} \right$

$$
#### 2. DIFFERENTIATE THE FINAL TERM
The final term is:
$$

e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)}

$$
The derivative with respect to $r_{\text{nominal}}(t,T)$ is:
$$

\frac{\partial}{\partial r_{\text{nominal}}(t,T)} e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)} = - (T_{n} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)}

$$
#### 3. COMBINE THE DERIVATIVES
Combining these results, we get:
$$

\frac{\partial B_{c}^{TIPS}(t,T)}{\partial r_{\text{nominal}}(t,T)} = e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} \left$- (T_{i} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} \right$ + 100 \left$- (T_{n} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)} \right$ \right$

$$
Simplify by factoring out the negative sign and combining terms:
$$

\frac{\partial B_{c}^{TIPS}(t,T)}{\partial r_{\text{nominal}}(t,T)} = - e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} (T_{i} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 100 (T_{n} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)} \right$

$$
Therefore, the first derivative of $B_{c}^{TIPS}(t,T)$ with respect to $r_{\text{nominal}}(t,T)$ is:
$$

\frac{\partial B_{c}^{TIPS}(t,T)}{\partial r_{\text{nominal}}(t,T)} = - e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} (T_{i} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 100 (T_{n} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)} \right$

$$


To find the second derivative of $B_{c}^{TIPS}(t,T)$ with respect to $r_{\text{nominal}}(t,T)$, we'll start from the first derivative we previously derived and then differentiate it again with respect to $r_{\text{nominal}}(t,T)$.
The first derivative is:
$$

\frac{\partial B_{c}^{TIPS}(t,T)}{\partial r_{\text{nominal}}(t,T)} = - e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} (T_{i} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 100 (T_{n} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)} \right$

$$
To find the second derivative, we need to differentiate this expression with respect to $r_{\text{nominal}}(t,T)$ again. 
### STEP-BY-STEP DERIVATION
#### 1. DIFFERENTIATE THE SUMMATION TERM
The first summation term inside the brackets is:
$$

\sum_{i=1}^{n} (T_{i} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)}$$

The derivative of each exponential term $e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)}$ with respect to $r_{\text{nominal}}(t,T)$ is:

$$
\frac{\partial}{\partial r_{\text{nominal}}(t,T)} \left( (T_{i} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} \right) = - (T_{i} - t)^2 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)}
$$
#### 2. DIFFERENTIATE THE FINAL TERM

The final term inside the brackets is:

$$
(T_{n} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)}$$

The derivative with respect to $r_{\text{nominal}}(t,T)$ is:
$$

\frac{\partial}{\partial r_{\text{nominal}}(t,T)} \left((T_{n} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)} \right) = - (T_{n} - t)^2 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)}

$$
#### 3. COMBINE THE DERIVATIVES
Combining these results, we get:
$$

\frac{\partial^2 B_{c}^{TIPS}(t,T)}{\partial r_{\text{nominal}}(t,T)^2} = - e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} \left$- (T_{i} - t)^2 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} \right$ + 100 \left$- (T_{n} - t)^2 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)} \right$ \right$$$

Simplify by factoring out the negative sign and combining terms:

$$
\frac{\partial^2 B_{c}^{TIPS}(t,T)}{\partial r_{\text{nominal}}(t,T)^2} = e^{\pi t} \left$ \frac{c + 100}{2} \sum_{i=1}^{n} (T_{i} - t)^2 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 100 (T_{n} - t)^2 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)} \right$$$

Therefore, the second derivative of $B_{c}^{TIPS}(t,T)$ with respect to $r_{\text{nominal}}(t,T)$ is:
$$
\frac{\partial^2 B_{c}^{TIPS}(t,T)}{\partial r_{\text{nominal}}(t,T)^2} = e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} (T_{i} - t)^2 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 100 (T_{n} - t)^2 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)} \right$$$
---

To find the duration of $B_{c}^{TIPS}(t,T)$ in terms of $r_{\text{nominal}}(t,T)$, we need to calculate the negative of the first derivative of the bond price with respect to the nominal interest rate, divided by the bond price itself:

$$
\text{Duration} = -\frac{1}{B_{c}^{TIPS}(t,T)} \frac{\partial B_{c}^{TIPS}(t,T)}{\partial r_{\text{nominal}}(t,T)}
$$

Using the first derivative of $B_{c}^{TIPS}(t,T)$ with respect to $r_{\text{nominal}}(t,T)$:

$$
\frac{\partial B_{c}^{TIPS}(t,T)}{\partial r_{\text{nominal}}(t,T)} = - e^{\pi t} \left$ \frac{c + 100}{2} \sum_{i=1}^{n} (T_{i} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 100 (T_{n} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)} \right$
$$

The bond price $B_{c}^{TIPS}(t,T)$ is given by:

$$
B_{c}^{TIPS}(t,T) = e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)}\right$$$

Now, we can plug these into the duration formula:
$$

\text{Duration} = -\frac{1}{e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)}\right$} \cdot \left(e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} (T_{i} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 100 (T_{n} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)} \right$ \right)

$$
Simplify the expression by canceling out the $e^{\pi t}$ terms:
$$

\text{Duration} = \frac{\frac{c + 100}{2} \sum_{i=1}^{n} (T_{i} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 100 (T_{n} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)}}{\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)}}

$$
This simplifies further to:
$$

\text{Duration} = \frac{\sum_{i=1}^{n} (T_{i} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 2 \times (T_{n} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)}}{\sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 2 \times e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)}}$$

Therefore, the duration of $B_{c}^{TIPS}(t,T)$ in terms of $r_{\text{nominal}}(t,T)$ is:

$$
\text{Duration} = \frac{\sum_{i=1}^{n} (T_{i} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 2 \times (T_{n} - t) e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)}}{\sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 2 \times e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)}}$$


To find the convexity of $B_{c}^{TIPS}(t,T)$ in terms of $r_{\text{nominal}}(t,T)$, we need to compute the second derivative of the bond price with respect to the nominal interest rate and then use the formula for convexity.
The formula for convexity is:
$$

\text{Convexity} = \frac{1}{B_{c}^{TIPS}(t,T)} \frac{\partial^2 B_{c}^{TIPS}(t,T)}{\partial r_{\text{nominal}}(t,T)^2}$$

We already found the second derivative:

$$
\frac{\partial^2 B_{c}^{TIPS}(t,T)}{\partial r_{\text{nominal}}(t,T)^2} = e^{\pi t} \left$ \frac{c + 100}{2} \sum_{i=1}^{n} (T_{i} - t)^2 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 100 (T_{n} - t)^2 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)} \right$$$

The bond price $B_{c}^{TIPS}(t,T)$ is given by:
$$

B_{c}^{TIPS}(t,T) = e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)}\right$$$

To find the convexity, we need to divide the second derivative by the bond price:

$$
\text{Convexity} = \frac{e^{\pi t} \left$ \frac{c + 100}{2} \sum_{i=1}^{n} (T_{i} - t)^2 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 100 (T_{n} - t)^2 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)} \right$}{e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)}\right$}$$

Simplify by canceling out the $e^{\pi t}$ terms:
$$

\text{Convexity} = \frac{\frac{c + 100}{2} \sum_{i=1}^{n} (T_{i} - t)^2 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 100 (T_{n} - t)^2 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)}}{\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)}}$$

Therefore, the convexity of $B_{c}^{TIPS}(t,T)$ in terms of $r_{\text{nominal}}(t,T)$ is:

$$
\text{Convexity} = \frac{\sum_{i=1}^{n} (T_{i} - t)^2 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 2 \times (T_{n} - t)^2 e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)}}{\sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T)) (T_{i}-t)} + 2 \times e^{(\pi - r_{\text{nominal}}(t,T)) (T_{n}-t)}}$$







---



---

To find the first derivative of $B_{c}^{TIPS}(t,T)$ with respect to $r_{\text{nominal}}(t,T_{i})$, we will use the equation derived previously:
$$

B_{c}^{TIPS}(t,T) = e^{\pi t} \left$\frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_{i})) (T_{i}-t)} + 100 e^{(\pi - r_{\text{nominal}}(t,T_{{n}})) (T_{{n}}-t)}\right$

$$
Since we need the derivative with respect to $r_{\text{nominal}}(t,T_{i})$, we focus on the term involving $r_{\text{nominal}}(t,T_{i})$:
$$

\frac{\partial B_{c}^{TIPS}(t,T)}{\partial r_{\text{nominal}}(t,T_{i})} = \frac{\partial}{\partial r_{\text{nominal}}(t,T_{i})} \left(e^{\pi t} \cdot \frac{c + 100}{2} \sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_{i})) (T_{i}-t)} \right)

$$
First, we can take the constant terms outside the derivative:
$$

\frac{\partial B_{c}^{TIPS}(t,T)}{\partial r_{\text{nominal}}(t,T_{i})} = e^{\pi t} \cdot \frac{c + 100}{2} \cdot \frac{\partial}{\partial r_{\text{nominal}}(t,T_{i})} \left(\sum_{i=1}^{n} e^{(\pi - r_{\text{nominal}}(t,T_{i})) (T_{i}-t)} \right)

$$
The derivative of the exponential term with respect to $r_{\text{nominal}}(t,T_{i})$ is:
$$

\frac{\partial}{\partial r_{\text{nominal}}(t,T_{i})} \left(e^{(\pi - r_{\text{nominal}}(t,T_{i})) (T_{i}-t)} \right) = - (T_{i} - t) e^{(\pi - r_{\text{nominal}}(t,T_{i})) (T_{i}-t)}

$$
Putting it all together:
$$

\frac{\partial B_{c}^{TIPS}(t,T)}{\partial r_{\text{nominal}}(t,T_{i})} = e^{\pi t} \cdot \frac{c + 100}{2} \cdot \left(- (T_{i} - t) e^{(\pi - r_{\text{nominal}}(t,T_{i})) (T_{i}-t)} \right)

$$
Simplifying:
$$

\frac{\partial B_{c}^{TIPS}(t,T)}{\partial r_{\text{nominal}}(t,T_{i})} = - e^{\pi t} \cdot \frac{c + 100}{2} \cdot (T_{i} - t) e^{(\pi - r_{\text{nominal}}(t,T_{i})) (T_{i}-t)}

$$
Therefore, the first derivative of $B_{c}^{TIPS}(t,T)$ with respect to $r_{\text{nominal}}(t,T_{i})$ is:
$$

\frac{\partial B_{c}^{TIPS}(t,T)}{\partial r_{\text{nominal}}(t,T_{i})} = - e^{\pi t} \cdot \frac{c + 100}{2} \cdot (T_{i} - t) e^{(\pi - r_{\text{nominal}}(t,T_{i})) (T_{i}-t)}

$$


---


## NOMINAL ZERO COUPON BOND
Consider a nominal zero coupon bond at $t=0$:
$$

B_{0}(T) = 100 \times e^{-r_{\text{nom}}(T-t)}

$$
Having 100 at $t$ affords the investor:
$$

\frac{100}{\text{Idx}(T)} \text{ units of the consumption basket at } T

$$
## REAL AND NOMINAL RATES UNDER PERFECT FORESIGHT
Suppose we know the CPI index at $T$ (i.e. $\text{Idx}(T)$ is known).
### REAL PRESENT VALUE OF 100
$$

\text{Real Present Value of 100} = \sum_{i=1}^{n} \frac{100}{(1 + r^{R})^{T}}

$$
### DOLLAR PRESENT VALUE OF 100
$$

\text{Dollar Present Value of 100} = \sum_{i=1}^{n} \frac{100 \times \text{Idx}(T)}{(1 + r^{R})^{T}}

$$
Since we can perfectly forecast inflation, it must follow that the two discounts are identical:
$$

\frac{100 \times \text{Idx}(T)}{(1 + r^{R})^{T}} = \frac{100 \times \text{Idx}(T)}{(1 + r_{nom})^{T}}

$$
Let $r(t, T) = r^{R}(t, T) + \pi(t, T)$ be the continuously compounded annualized rate of inflation from 0 to $T$.
Then, under perfect foresight, the nominal interest rate is equal to the real interest rate plus inflation:
$$

r_{nom}(t, T) = r^{R}(t, T) + \pi(t, T)

$$
---

# TIPS
## INDEX RATIO
$$

\text{Index Ratio}(t) = \max\left(\frac{\text{Reference CPI}(t)}{\text{CPI}(t_{\text{issuance}})}, 1.0\right)

$$
## REFERENCE CPI
$$

\text{Reference CPI} = w(e(t))\text{CPI}(t-3) + (1-w(e(t)))\text{CPI}(t-2)

$$

where $w(e(t))$ is a weight that depends on the quoted day of the month.

## COUPON PAYMENT
$$

\text{Coupon Payment}(t) = \left(\frac{\text{Coupon Rate}}{2}\right) \times 100 \times \text{Index Ratio}(t)

$$
# REAL BONDS AND TIPS
## REAL BONDS

Real bonds are bonds denoted in terms of a good instead of dollars.

## REAL DISCOUNT FACTOR
$$

r(t,T) = \left(\frac{P(t)}{P(T)}\right)

$$

This defines the exchange rate between two consumption goods at $t$ versus consumption goods at later date $T$.

## REAL DISCOUNT RATE

From real discounts $r(t,T)$, we can compute the real rate as:

$$

r^{R}(t,T) = \left(\frac{r(t,T)^{-1} - 1}{T - t}\right)^{-1}

$$

implying:

$$

r^{R}(t,T) = \left(\frac{P(T)}{P(t)}\right)^{\frac{1}{T - t}} - 1

$$

The value in consumption goods $(z)$ of a real coupon bond of maturity $T$ and coupon rate $c$ is:

$$

P_{C}(t) = \sum_{i=1}^{n} \frac{cP(T_{i})}{P(t)} + \frac{P(T)}{P(t)}

$$

where $T_{i}$ are coupon dates.

## DERIVING THE PRICE OF ZERO COUPON TIPS

The CPI adjustment for maturity $T$, the payoff of a zero coupon TIPS is as follows:

$$

\text{Zero Coupon TIPS payoff at } T = 100 \times \text{Idx}(T)

$$

where $\text{Idx}(T)$ is the increase in consumption basket price between 0 and $T$.

## IDX(T) DEFINITIONS
- $\text{Idx}(T) = \frac{\text{CPI}(T)}{\text{CPI}(t)}$ = real price of 100 units of consumption basket at $T$.
- $100 \times \text{Idx}(T)$ is the real price of 100 units of the consumption basket at $T$.
- Real Present Value of $100 \times \text{Idx}(T)$ is:
  $$

  \sum_{i=1}^{n} \frac{100 \times \text{Idx}(T)}{P(t)}

 $$
- Dollar Present Value of a Zero Coupon TIPS $B_{I}(t)$ is:
  $$

  \sum_{i=1}^{n} \frac{100 \times \text{Idx}(T)}{P(t)}

 $$
- Dollar Present Value of a Coupon Paying TIPS $B_{I}(t)$ is:
  $$

  \sum_{i=1}^{n} \frac{100 \times c \times \text{Idx}(T)}{P(t)} + \frac{100 \times \text{Idx}(T)}{P(t)}

 $$
- Consider a nominal zero coupon bond at $t=0$: 
  $$

  B_{0}(T) = \frac{100}{(1 + r_{nom})^{T}}

 $$
- Having $100 \times \text{Idx}(T)$ affords the investor 100 units of the consumption basket at $T$.
# REAL AND NOMINAL RATES UNDER PERFECT FORESIGHT
## PERFECT FORESIGHT ASSUMPTIONS
Suppose we know the CPI index at $T$ is $\text{Idx}(T)$. The real present value of 100 is:
$$

\text{Real Present Value of 100} = \sum_{i=1}^{n} \frac{100}{(1 + r^{R})^{T}}

$$
Dollar Present Value of 100:
$$

\text{Dollar Present Value of 100} = \sum_{i=1}^{n} \frac{100 \times \text{Idx}(T)}{(1 + r^{R})^{T}}

$$
Since we can perfectly forecast inflation, it must follow that the two discounts are identical:
$$

\frac{100 \times \text{Idx}(T)}{(1 + r^{R})^{T}} = \frac{100 \times \text{Idx}(T)}{(1 + r_{nom})^{T}}

$$
Let $r(t, T) = r^{R}(t, T) + \pi(t, T)$ be the continuously compounded annualized rate of inflation from 0 to $T$.
Then, under perfect foresight, the nominal interest rate is equal to the real interest rate plus inflation:
$$

r_{nom}(t, T) = r^{R}(t, T) + \pi(t, T)

$$

---

To find the result of multiplying the derivative of the price of TIPS with respect to $r_{n}$ by $\frac{1}{P_{c}^{TIPS}(0, T_n)}$, we need to carefully carry out the multiplication. Let's start by rewriting each expression for clarity.

### ORIGINAL PRICE OF TIPS

The price of TIPS is given by:

$$

P_{c}^{TIPS}(0, T_{n}) = \frac{I_{dx}(t)}{I_{dx}(0)} \times \left$\frac{c \times 100}{2} \sum_{i=1}^{n} e^{-r_{n} T_{i} + \pi T_{i}} + 100 e^{-r_{n} T_{n} + \pi T_{n}} \right$

$$
### DERIVATIVE OF THE PRICE OF TIPS WITH RESPECT TO $R_{N}$

The derivative is:

$$

\frac{dP_{c}^{TIPS}(0, T_{n})}{dr_{n}} = \frac{I_{dx}(t)}{I_{dx}(0)} \times \left$\frac{c \times 100}{2} \sum_{i=1}^{n} \left(-T_{i} e^{-r_{n} T_{i} + \pi T_{i}} \right) - 100 T_{n} e^{-r_{n} T_{n} + \pi T_{n}} \right$

$$
### MULTIPLICATION OF THE DERIVATIVE BY $\frac{ 1}{P_{C}^{TIPS}(0, T_N)}$

To find the result, we multiply the derivative by the reciprocal of the original price:

$$

\frac{1}{P_{c}^{TIPS}(0, T_{n})} = \frac{I_{dx}(0)}{I_{dx}(t)} \times \frac{1}{\left$\frac{c \times 100}{2} \sum_{i=1}^{n} e^{-r_{n} T_{i} + \pi T_{i}} + 100 e^{-r_{n} T_{n} + \pi T_{n}} \right$}

$$

Therefore,

$$

\frac{dP_{c}^{TIPS}(0, T_{n})}{dr_{n}} \times \frac{1}{P_{c}^{TIPS}(0, T_{n})} = \frac{\frac{I_{dx}(t)}{I_{dx}(0)} \left$\frac{c \times 100}{2} \sum_{i=1}^{n} \left(-T_{i} e^{-r_{n} T_{i} + \pi T_{i}} \right) - 100 T_{n} e^{-r_{n} T_{n} + \pi T_{n}} \right$}{\frac{I_{dx}(t)}{I_{dx}(0)} \left$\frac{c \times 100}{2} \sum_{i=1}^{n} e^{-r_{n} T_{i} + \pi T_{i}} + 100 e^{-r_{n} T_{n} + \pi T_{n}} \right$}

$$
### SIMPLIFYING THE EXPRESSION

The terms $\frac{I_{dx}(t)}{I_{dx}(0)}$ cancel out, giving us:

$$

\frac{dP_{c}^{TIPS}(0, T_{n})}{dr_{n}} \times \frac{1}{P_{c}^{TIPS}(0, T_{n})} = \frac{\left$\frac{c \times 100}{2} \sum_{i=1}^{n} \left(-T_{i} e^{-r_{n} T_{i} + \pi T_{i}} \right) - 100 T_{n} e^{-r_{n} T_{n} + \pi T_{n}} \right$}{\left$\frac{c \times 100}{2} \sum_{i=1}^{n} e^{-r_{n} T_{i} + \pi T_{i}} + 100 e^{-r_{n} T_{n} + \pi T_{n}} \right$}

$$

This expression can be further simplified by factoring out common terms where possible:

$$

= \frac{\frac{c \times 100}{2} \sum_{i=1}^{n} \left(-T_{i} e^{-r_{n} T_{i} + \pi T_{i}} \right) - 100 T_{n} e^{-r_{n} T_{n} + \pi T_{n}}}{\frac{c \times 100}{2} \sum_{i=1}^{n} e^{-r_{n} T_{i} + \pi T_{i}} + 100 e^{-r_{n} T_{n} + \pi T_{n}}}

$$
### FINAL SIMPLIFIED EXPRESSION
$$

= \frac{\frac{c}{2} \sum_{i=1}^{n} \left(-T_{i} e^{-r_{n} T_{i} + \pi T_{i}} \right) - T_{n} e^{-r_{n} T_{n} + \pi T_{n}}}{\frac{c}{2} \sum_{i=1}^{n} e^{-r_{n} T_{i} + \pi T_{i}} + e^{-r_{n} T_{n} + \pi T_{n}}}

$$

This is the result of multiplying the derivative of the price of TIPS by the reciprocal of the price of TIPS.

---

To expand the series and simplify the expression, we need to explicitly write out each term in the summation for $n = 20$ and $T_{i} = 0.5i$ where $i$ ranges from 1 to 20. Let's start by expanding the terms.

### GIVEN PARAMETERS
- $n = 20$
- $T_{i} = 0.5i$ for $i = 1, 2, \ldots, 20$
- $T_{20} = 10$
### ORIGINAL EXPRESSION

The original expression is:

$$

\frac{dP_{c}^{TIPS}(0, T_{n})}{dr_{n}} \times \frac{1}{P_{c}^{TIPS}(0, T_{n})} = \frac{\frac{c}{2} \sum_{i=1}^{n} \left(-T_{i} e^{-r_{n} T_{i} + \pi T_{i}} \right) - T_{n} e^{-r_{n} T_{n} + \pi T_{n}}}{\frac{c}{2} \sum_{i=1}^{n} e^{-r_{n} T_{i} + \pi T_{i}} + e^{-r_{n} T_{n} + \pi T_{n}}}

$$
### EXPANDING THE SUMMATION

First, let's expand the numerator:

#### NUMERATOR EXPANSION
$$

\frac{c}{2} \sum_{i=1}^{n} \left(-T_{i} e^{-r_{n} T_{i} + \pi T_{i}} \right) = \frac{c}{2} \left(-0.5 e^{-r_{n} \cdot 0.5 + \pi \cdot 0.5} - 1.0 e^{-r_{n} \cdot 1.0 + \pi \cdot 1.0} - 1.5 e^{-r_{n} \cdot 1.5 + \pi \cdot 1.5} - \cdots - 10 e^{-r_{n} \cdot 10 + \pi \cdot 10} \right)

$$

Including the term $-T_{n} e^{-r_{n} T_{n} + \pi T_{n}}$:

$$
- T_{n} e^{-r_{n} T_{n} + \pi T_{n}} = - 10 e^{-r_{n} \cdot 10 + \pi \cdot 10}
$$

So, the numerator becomes:

$$

\frac{c}{2} \left(-0.5 e^{-r_{n} \cdot 0.5 + \pi \cdot 0.5} - 1.0 e^{-r_{n} \cdot 1.0 + \pi \cdot 1.0} - 1.5 e^{-r_{n} \cdot 1.5 + \pi \cdot 1.5} - \cdots - 10 e^{-r_{n} \cdot 10 + \pi \cdot 10} \right) - 10 e^{-r_{n} \cdot 10 + \pi \cdot 10}

$$

Simplify this further:

$$

= \frac{c}{2} \left(-0.5 e^{-r_{n} \cdot 0.5 + \pi \cdot 0.5} - 1.0 e^{-r_{n} \cdot 1.0 + \pi \cdot 1.0} - 1.5 e^{-r_{n} \cdot 1.5 + \pi \cdot 1.5} - \cdots - 10 e^{-r_{n} \cdot 10 + \pi \cdot 10} \right) - 10 e^{-r_{n} \cdot 10 + \pi \cdot 10}

$$
#### DENOMINATOR EXPANSION
$$

\frac{c}{2} \sum_{i=1}^{n} e^{-r_{n} T_{i} + \pi T_{i}} + e^{-r_{n} T_{n} + \pi T_{n}} = \frac{c}{2} \left(e^{-r_{n} \cdot 0.5 + \pi \cdot 0.5} + e^{-r_{n} \cdot 1.0 + \pi \cdot 1.0} + e^{-r_{n} \cdot 1.5 + \pi \cdot 1.5} + \cdots + e^{-r_{n} \cdot 10 + \pi \cdot 10} \right) + e^{-r_{n} \cdot 10 + \pi \cdot 10}

$$
### FULL EXPANSION

The full expanded expression is:

$$

\frac{dP_{c}^{TIPS}(0, T_{n})}{dr_{n}} \times \frac{1}{P_{c}^{TIPS}(0, T_{n})} = \frac{\frac{c}{2} \left(-0.5 e^{-r_{n} \cdot 0.5 + \pi \cdot 0.5} - 1.0 e^{-r_{n} \cdot 1.0 + \pi \cdot 1.0} - 1.5 e^{-r_{n} \cdot 1.5 + \pi \cdot 1.5} - \cdots - 10 e^{-r_{n} \cdot 10 + \pi \cdot 10} \right) - 10 e^{-r_{n} \cdot 10 + \pi \cdot 10}}{\frac{c}{2} \left(e^{-r_{n} \cdot 0.5 + \pi \cdot 0.5} + e^{-r_{n} \cdot 1.0 + \pi \cdot 1.0} + e^{-r_{n} \cdot 1.5 + \pi \cdot 1.5} + \cdots + e^{-r_{n} \cdot 10 + \pi \cdot 10} \right) + e^{-r_{n} \cdot 10 + \pi \cdot 10}}

$$

We can simplify the common factor of $e^{-r_{n} T_{i} + \pi T_{i}}$ terms for clarity, but they cannot be further combined algebraically since each term has a different exponent value. This is the fully expanded and simplified form, taking into account the specific values of $T_{i}$.

---

Given that both the real and nominal bonds are coupon bonds, we'll adjust our approach to account for coupon payments in the duration and convexity formulas.

### III. **DURATION AND CONVEXITY HEDGING FOR COUPON BONDS**

#### 1. FORMULAS FOR DURATION AND CONVEXITY FOR TIPS

To derive the formulas for duration and convexity for TIPS (Treasury Inflation-Protected Securities), we'll consider the bond's cash flows, which include periodic coupon payments and the principal repayment at maturity.

1. **Duration Formula**:
   - **Definition**: Duration measures the sensitivity of the price of a bond to changes in interest rates.
   - Assume the real coupon bond price is $P_{\text{real}}$ and the nominal coupon bond price is $P$.
   - For TIPS, we can use the notion of break-even inflation $\pi(0, T)$ to relate real and nominal rates.
   - The present value of cash flows for a coupon bond is:

   $$ P = \sum_{i=1}^{N} \frac{C}{e^{r T_i}} + \frac{F}{e^{r T}} $$

   - The real bond price $P_{\text{real}}$ can be expressed as:

   $$ P_{\text{real}} = \sum_{i=1}^{N} \frac{C}{e^{r_{\text{real}} T_i}} + \frac{F}{e^{r_{\text{real}} T}} $$

   - Here, $r_{\text{real}} = r - \pi(0, T)$.
   - Differentiating the real bond price with respect to the nominal rate $r$:

   $$ D_{\text{TIPS}} = \frac{1}{P_{\text{real}}} \left(\sum_{i=1}^{N} \frac{C T_i}{e^{r_{\text{real}} T_i}} + \frac{F T}{e^{r_{\text{real}} T}} \right) $$

2. **Convexity Formula**:
   - **Definition**: Convexity measures the sensitivity of the duration of the bond to changes in interest rates.
   - The formula for convexity $C$ is:

   $$ C = \frac{1}{P} \frac{d^2P}{dr^2} $$

   - Using the same approach for real bond prices:

   $$ C_{\text{TIPS}} = \frac{1}{P_{\text{real}}} \left(\sum_{i=1}^{N} \frac{C T_i^2}{e^{r_{\text{real}} T_i}} + \frac{F T^2}{e^{r_{\text{real}} T}} \right) $$

### IV. **INFLATION DURATION AND INFLATION SWAPS**

#### 1. INFLATION DURATION OF TIPS

- **Definition**: Inflation duration measures the sensitivity of the TIPS price to changes in break-even inflation.
- Using the methodology for nominal duration, we can derive the inflation duration for coupon bonds:

$$ D_{\pi} = \frac{1}{P_{\text{real}}} \left( \sum_{i=1}^{N} \frac{C T_i}{e^{r_{\text{real}} T_i}} + \frac{F T}{e^{r_{\text{real}} T}} \right) $$

- Comment: This result indicates that the inflation duration is similar in form to the nominal duration but specifically measures the impact of changes in $\pi(0, T)$ on the TIPS price.

#### 2. VALUATION OF ZERO-COUPON INFLATION SWAPS

- **Definition**: Zero-coupon inflation swaps allow for trading inflation claims and hedging inflation risk.
- The value $V_{\text{ZCIS}}$ of the swap at time $t=0$ can be expressed as:

$$ V_{\text{ZCIS}} = N \left( \frac{e^{\pi_{\text{actual}} T}}{e^{\pi_{\text{fixed}} T}} - 1 \right) $$

- We can compare this with the Lehman Brothers formula, which does not use continuous compounding, to check for consistency.

#### 3. SENSITIVITY OF INFLATION SWAPS TO NOMINAL AND BREAK-EVEN RATES

- **Sensitivity to Nominal Rates**:
  - The value of the inflation swap can be sensitive to nominal rates right after inception.
  - Compute traditional duration for the swap:

  $$ D_{\text{swap}} = -\frac{1}{V_{\text{swap}}} \frac{dV_{\text{swap}}}{dr} $$

- **Sensitivity to Break-Even Rates**:
  - Compute similarly using break-even rates:

  $$ D_{\pi,\text{swap}} = \frac{1}{V_{\text{swap}}} \frac{dV_{\text{swap}}}{d\pi} $$

#### 4. OPTIMAL DURATION AND INFLATION HEDGE

- Using the results from the above calculations, we can determine the optimal hedge by balancing the durations:

$$ \text{Hedge Ratio} = \frac{D_{\text{TIPS}}}{D_{\text{swap}}} $$

#### 5. PERFORMANCE EVALUATION OF THE HEDGE

- Use the provided dataset "DataFinal2021.xls" (tab "TimeSeries TIPS Treasury") to evaluate the hedge.
- Compare performance with and without the inflation hedge post-January 15, 2013.

Next, let's finalize the valuation formula for zero-coupon inflation swaps and compute the term structures of real interest rates and break-even inflation rates using TIPS and Nominal Bonds.

We will proceed with the necessary calculations and comparisons based on the cleaned data from `TimeSeries_TIPS_Treasury` and `InflationSwaps`.

### COMPUTE THE VALUATION FORMULA FOR ZERO-COUPON INFLATION SWAPS

First, we will compute the real interest rates and break-even inflation rates based on the data provided.

#### 1. COMPUTE REAL INTEREST RATES USING INFLATION SWAPS

We'll compute the real interest rates from the zero-coupon inflation swaps and compare them with those obtained from TIPS.

#### 2. COMPUTE BREAK-EVEN INFLATION RATES

We'll calculate the break-even inflation rates and compare them with those from TIPS and nominal bonds.

#### 3. EVALUATE HEDGE PERFORMANCE

We will use the cleaned data to evaluate the hedge's performance post-January 15, 2013.

Let's proceed with the calculations.

---

## INTRODUCTION TO TREASURY INFLATION-PROTECTED SECURITIES (TIPS)

   Treasury Inflation-Protected Securities (TIPS) are government bonds whose principal is adjusted by changes in the
   Consumer Price Index (CPI). With inflation, the principal increases, and interest payments, which are a fixed rate
   applied to the adjusted principal, increase as well. In times of deflation, the principal decreases but is guaranteed
   by the U.S. Treasury to not fall below its original amount at issuance.

### PURPOSES AND USERS

   TIPS are predominantly used by investors seeking protection against inflation. The adjustment in principal, tied to t
   CPI, ensures that the bond’s purchasing power is preserved irrespective of the rate of inflation. Common investors
   include retirement funds, long-term savers, and risk-averse individuals who are looking to maintain the value of thei
   capital in real terms over time.

   ---

   Next, I will gather information necessary to discuss the relationships between nominal and real interest rates. This
   includes a brief mathematical explanation along with the role each type plays in financial planning and investment.

  Let’s proceed with gathering the data and constructing the argument for how nominal and real rates are related to each
  other. Shall we start by summarizing the theoretical aspects and formulas involving the relationship between nominal
  and real interest rates?

> y

  To effectively explain the relationship between nominal and real interest rates, we need to include a clear
  mathematical representation and discuss their relevance in the context of financial planning. Here's how we can
  structure this discussion:

                                              Nominal vs. Real Interest Rates                                              
                                                                                                                           
                                                Definition and Relationship                                                
                                                                                                                           
   - Nominal Interest Rate: The rate of interest before adjustment for inflation. It represents the rate at which the
	 interest is paid by borrowers for the use of money that they borrow.
   - Real Interest Rate: This is the nominal rate adjusted for the effects of inflation. Real rate more accurately
	 reflects the true cost of borrowing and the true yield to lenders or investors.

	                                             Mathematical Relationship                                                 
                                                                                                                           

  The relationship between nominal interest rate ((r)), real interest rate ((r_{real})), and inflation rate ((i))
  can typically be approximated by the Fisher Equation, which is given by: $1 + r = (1 + r_{real})(1 + i)$ This
  equation can be rearranged to solve for the real interest rate: $r_{real} = \frac{1 + r}{1 + i} - 1$

                                             Importance in Financial Decisions                                             
                                                                                                                           

  Understanding this relationship is crucial for investors and financial planners:

   - Investors need to consider the real interest rate to determine the real growth of their investments after adjusting
	 for inflation.
   - Borrowers evaluate the real cost of borrowing, an important aspect when inflation rates are high.

  We should also consider including a practical example to illustrate these concepts more vividly. Would you like to
  proceed with drafting a brief example or move on to discussing the differences between inflation-linked bonds and real
  bonds?

> continue on to the next part about inflation indexed bonds and real bonds(ie bonds denominated in units of real goods)

  To further develop the report for JCH Asset Management, let's delve into the differences between inflation-linked
  (inflation-indexed) bonds and real bonds, explaining their distinct characteristics and uses.

                                 Differences Between Inflation-Linked Bonds and Real Bonds                                 
                                                                                                                           
                                     Inflation-Linked Bonds (Inflation-Indexed Bonds)                                      
                                                                                                                           
   - Definition: Inflation-linked bonds are types of bonds where the principal amount and the interest payments are
	 adjusted according to the rate of inflation. Common examples include Treasury Inflation-Protected Securities (TIPS)
	 in the U.S.
   - Adjustment Mechanism: The principal is adjusted by an inflation index (e.g., CPI). If inflation rises, both the
	 principal and interest payments increase accordingly, preserving the purchasing power of the investor’s money.
   - Investor Benefit: Provides protection against inflation risk, making them appealing for long-term investments where
	 preserving the real value of capital is crucial.

	                               Real Bonds (Bonds Denominated in Units of Real Goods)                                   
                                                                                                                           
   - Definition: Real bonds are not as commonly discussed but can be conceptualized as bonds denominated in units of real
	 goods or commodities rather than monetary units. For example, a bond might be issued with principal and interest
	 payments tied to the price of a commodity like gold or a basket of goods.
   - Adjustment Mechanism: There are no regular interest rate adjustments as seen with inflation-linked bonds. Instead,
	 the repayments are inherently adjusted because they are denominated in physical goods or their equivalent value.
   - Investor Benefit: Provides a hedge against both inflation and currency risk, especially in economies experiencing
	 high inflation or currency volatility.

	                                                  Key Comparison                                                       
                                                                                                                           
   - Protection Mechanism: While both types of bonds offer inflation protection, inflation-linked bonds adjust cash
	 payouts directly linked to an inflation index. In contrast, real bonds provide an indirect hedge by tying repayments
	 to stable or appreciative assets in real terms.
   - Market Use: Inflation-linked bonds are more prevalent in financial markets and have well-established mechanisms and
	 indices guiding adjustments. Real bonds, being less common, are not as liquid and lack standardized mechanisms for
	 trading and valuation.

	                                          Usage in Investment Portfolios                                               
                                                                                                                           
   - Inflation-Linked Bonds: Preferred by conservative investors, pension funds, and those seeking clear,
	 inflation-adjusted returns without exposure to volatile markets.
   - Real Bonds: Suited for investors seeking direct exposure to commodities or who are operating in high-risk or
	 unstable currency environments.

  By illustrating these differences, the managing director can appreciate the distinct roles these securities can play in
  diversifying the firm’s investment portfolio and mitigating various types of financial risks.

  Would you like to include specific historical performance data or case studies to support this section, or should we
  move on to discussing the expected returns of inflation-linked bonds compared to nominal bonds?

> move on

  Next, let's explore the expected returns from inflation-linked bonds compared to nominal bonds, providing a detailed
  analysis that includes theoretical expectations as well as potential variations based on market conditions.

                               Expected Returns on Inflation-Linked Bonds vs. Nominal Bonds                                
                                                                                                                           
                                                   Theoretical Framework                                                   
                                                                                                                           
   - Inflation-Linked Bonds: The returns on these securities are designed to preserve the purchasing power of capital by
	 adjusting both the principal and interest payments according to inflation. The real rate of return is generally the
	 yield determined at the time of purchase, adjusted periodically for inflation.
   - Nominal Bonds: These bonds pay a fixed rate of interest throughout the term of the bond. The real return on these
	 bonds, however, can be negative or positive depending on the inflation rate. If inflation is higher than expected,
	 the real return decreases; if it's lower, the real return increases.

	                                            Expected Return Calculation                                                
                                                                                                                           

  For inflation-linked bonds, the expected return can be modeled as: $\text{Expected Return}{\text{ILB}} = \text{Real
  Yield} + \text{Inflation Rate}$ For nominal bonds, the expected return is simply the nominal yield: $\text{Expected
  Return}{\text{NB}} = \text{Nominal Yield}$

                                                Risk and Return Trade-offs                                                 
                                                                                                                           
   - Inflation Risk: Inflation-linked bonds provide a hedge against inflation, making them safer in terms of preserving
	 capital value during inflationary periods. Nominal bonds, however, are susceptible to inflation risk, meaning that
	 high inflation can erode the real value of the returns.
   - Interest Rate Risk: Both types of bonds are subject to interest rate risk. If interest rates rise, bond prices
	 generally fall, and vice versa. However, the impact may be more pronounced for nominal bonds since inflation
	 expectations significantly influence interest rate movements.
   - Market Demand and Liquidity: Nominal bonds typically enjoy higher liquidity due to their more extensive and
	 established market. Inflation-linked bonds, while increasingly popular, may have lesser liquidity, affecting their
	 price and ease of trading.

	                                        Practical Example for Illustration                                             
                                                                                                                           

  Consider two scenarios: one where inflation is rising and another where it is stable or falling. In a rising inflation
  scenario, inflation-linked bonds are likely to perform better in terms of real returns. In stable or falling inflation
  scenarios, nominal bonds might offer better nominal and potentially better real returns if inflation rates drop below
  the rates at which the bonds were issued.

                                            Conclusion for JCH Asset Management                                            
                                                                                                                           

  For a firm like JCH Asset Management, incorporating both types of bonds into the portfolio can balance the trade-offs
  between risk and return, ensuring that the investment strategy covers various economic scenarios. Inflation-linked
  bonds should be favored when long-term inflation protection is a priority, while nominal bonds could be utilized for
  potentially higher yields when inflation forecasts are lower.

  Shall we proceed to summarize the findings and recommendations in a concluding section, or is there anything else
  specific you would like to further detail in the report?

> It is January 15, 2013, and JCH has a $ 200 million holdings (par value) of the %, Jan 15 2022 TIPS. The Principals of JCH are worried about their exposure to potential changes in interest rates and inflation expectations. Before you compute risk measures (Question III below), you should discuss some properties of real and nominal rates in the data, using both historical data and today's prices. The dataset DataFinal2021.xls contains the data required for the analysis. Do the following:  - The price of a zero coupon $$Z(0,t)=100*exp(r,T)$$  - The spot rate is a geometric average of one year forward rates, $$(1+s_n)^n=(1+f_{0,1})(1+f_{1,2})(1+f_{2,3})+…+(1+f_{n-1,n})$$  - For an m-year and n-year spot rates, the annualized n-m year rate m year forward rate $f_{m,n}$ is given as $$(1+f_{m,n})^{n-m}=\frac{(1+s_{n})^n}{(1+s_m)^m}$$

  To analyze JCH Asset Management's exposure to interest rate and inflation risk due to their holdings in TIPS, we first
  need to understand the behavior of real and nominal rates, using the provided historical data and the formulas for
  calculating rates and bond pricing. This analysis will provide the foundation for subsequently computing appropriate
  risk measures.

                                   Step 1: Understanding and Utilizing Key Rate Formulas                                   
                                                                                                                           

  Let's break down the formulas and how they will be used:

   1 Zero Coupon Bond Price Formula: (Z(0, t) = 100 \times \exp(-r \cdot T))
	  - This formula describes the price of a zero-coupon bond which does not pay any interest but is sold at a discount
		and pays its face value at maturity. The variable (r) represents the yield or the spot rate to maturity, and (
		T) is the time to maturity in years.
   2 Spot Rate Formula: ((1+s_n)^n = (1+f_{0,1})(1+f_{1,2}) \ldots (1+f_{n-1,n}))
	  - The spot rate ((s_n)) for a period of (n) years is the geometric average of one-year forward rates over (n)
		years. This offers a way to derive spot rates used to discount cash flows for bonds.
   3 Forward Rate Formula: ((1+f_{m,n})^{n-m} = \frac{(1+s_n)^n}{(1+s_m)^m})
	  - This formula is used to calculate the forward rate of interest between year (m) and year (n), essential for
		analyzing future interest rate expectations embedded in current rates.

                                           Step 2: Applying Formulas to Dataset                                            
                                                                                                                           

  We'll need to load the data from DataFinal2021.xls to pull historical spot rates and calculate forward rates
  accordingly:

   - Extract spot rates ((s_n)) and calculate forward rates ((f_{m,n})).
   - Visualize these rates to understand trends over time—this will be crucial for identifying patterns or anomalies,
	 allowing for better risk predictions.

	                         Step 3: Analyze Historical Data for Interest and Inflation Rates                              
                                                                                                                           

  Utilizing historical spot rates and derived forward rates, we can:

   - Discuss how historically real and nominal rates have behaved in relation to inflation and other economic variables.
   - Identify how changes in these rates have affected the valuations of TIPS and traditional nominal bonds in JCH's
	 portfolio.

	                                            Plan of Action for Analysis                                                
                                                                                                                           
   - Task 1: Write the code to load and read the dataset DataFinal2021.xls, then extract necessary spot rate data.
   - Task 2: Apply formulas to compute forward rates and any other required rate analysis.
   - Task 3: Conduct a graph visual analysis to see trends and predictive patterns.
   - Task 4: Prepare insights and findings to include in the report, focused on the investment decisions related to TIPS.

  This comprehensive analytical approach should help address the concerns of the principals at JCH by showing not only
  the current valuations and risks but also projected risks based on rate changes.

  Let's start by loading the data from DataFinal2021.xls. I will proceed to write the code to access and inspect this
  file, ensuring we have the correct data. Shall we continue with this step?

> no

  Understood. Since we won't be loading and analyzing the data right now, let's discuss the next steps or any other areas
  you would like to focus on regarding the TIPS and inflation-dependent securities project.

  Would you like to discuss theoretical risk measures for these assets, proceed with another type of analysis, or need
  assistance with a different part of your project? Please let me know how you would like to proceed!

> for the following coupon paying bonds, ## III. **Duration and Convexity Hedging (20 points)** Consider again JCH the $200 million position in %, 01/15/22 TIPS. As mentioned, principals at JCH are worried about its risks. Obtain a formula for duration and convexity for TIPS, where they are both defined against shifts in the nominal term structure of interest rates, assuming nothing else changes. (Hints.    - (1) It is useful to use continuous compounding as in TN 2.    - (2) Usethe notion of break-even rate π(0, T) obtained earlier, to transform real rates into nominal rates minus break-even inflation.     - (3) Assume π(0, T) is not affected by a parallel shift in the nominal term structure of interest rates.     - (4) Exploit this formula and thus the relation between Zreal(0, T) and Z(0, T) to obtain the formulas for duration and convexity. The steps are the same as in TN 2.)

  To analyze the duration and convexity of TIPS (Treasury Inflation-Protected Securities), particularly for the JCH's
  $200 million position in a % coupon TIPS maturing on 01/15/22, we will follow a detailed process. These risk
  metrics are critical for understanding the price sensitivity of TIPS to changes in interest rates within the nominal
  term structure. Let’s outline the steps needed to derive formulas for both duration and convexity of TIPS.

                                               Key Definitions and Formulas                                                
                                                                                                                           

   1 Duration and Convexity Overview:
	  - Duration is a measure of the bond's price sensitivity to changes in interest rates and gives an approximate
		percentage change in price for a 1% change in interest rates.
	  - Convexity is a measure of the curvature of how the price changes in response to interest rate changes, providing
		a refinement to the duration measure by accounting for changes in duration as interest rates change.
   2 Transforming Real Rates to Nominal Rates:
	  - Using the break-even rate (\pi(0, T)) allows the transformation of real rates into nominal rates adjusted for
		expected inflation. This break-even inflation rate is the difference needed to equate the return on TIPS to an
		equivalent nominal bond.
	  - Formula: (r_{nominal} = r_{real} + \pi(0, T))
   3 Continuous Compounding:
	  - The bond prices using continuous compounding can be expressed as (Z(0, T) = 100 \times \exp(-r_{nominal} \times
		T)).

                              Step-by-Step Approach to Derive Duration and Convexity Formulas                              
                                                                                                                           

   1 Express Real Bond Price:
	  - Using continuous compounding for TIPS, the price of TIPS (Z_{real}(0, T)) can be modelled as: $Z_{real}(0, T)
		= 100 \times \exp(-r_{real} \times T)$
   2 Connect Real and Nominal Bond Prices:
	  - From the formula, the nominal zero-coupon bond price (Z(0, T)) related to the real rate and break-even
		inflation: $Z(0, T) = Z_{real}(0, T) \times \exp(-\pi(0, T) \times T)$
	  - This represents how TIPS are priced in the market accounting for expected inflation.
   3 Duration Calculation:
	  - Duration formula under continuous compounding for nominal bonds: $D = -\frac{1}{P} \frac{dP}{dr}$
	  - For TIPS, incorporating the relationship with nominal rates: $D_{TIPS} = -\frac{1}{Z(0, T)} \times \frac{d}{dr}
		\left$Z_{real}(0, T) \times \exp(-\pi(0, T) \times T)\right$$
	  - Simplify using the product rule in differentiation.
   4 Convexity Calculation:
	  - Convexity formula under continuous compounding: $C = \frac{1}{P} \frac{d^2P}{dr^2}$
	  - Applying it to TIPS using the simplified price formula: $C_{TIPS} = \frac{1}{Z(0, T)} \times \frac{d^2}{dr^2}
		\left$Z_{aligned}(0, T)\right$$

                                                    Steps to Implement                                                     
                                                                                                                           

   1 Mathematical Derivation:
	  - Should proceed with deriving these formulas precisely, applying calculus to handle differentiation.
   2 Numerical Validation:
	  - Check computations with actual data or hypothetical scenarios to validate the theoretical derivations.

  Would you like to continue with the detailed mathematical derivations for these formulas, or should we discuss the
  conceptual approach further?

> detailed mathematical derivation

  Let's move forward with a detailed mathematical derivation for the duration and convexity of TIPS based on the nominal

  Let's move forward with a detailed mathematical derivation for the duration and convexity of TIPS based on the nominal

  Let's move forward with a detailed mathematical derivation for the duration and convexity of TIPS based on the nominal

  Let's move forward with a detailed mathematical derivation for the duration and convexity of TIPS based on the nominal

  Let's move forward with a detailed mathematical derivation for the duration and convexity of TIPS based on the nominal

  Let's move forward with a detailed mathematical derivation for the duration and convexity of TIPS based on the nominal

  Let's move forward with a detailed mathematical derivation for the duration and convexity of TIPS based on the nominal

  Let's move forward with a detailed mathematical derivation for the duration and convexity of TIPS based on the nominal

  Let's move forward with a detailed mathematical derivation for the duration and convexity of TIPS based on the nominal

  Let's move forward with a detailed mathematical derivation for the duration and convexity of TIPS based on the nominal

  Let's move forward with a detailed mathematical derivation for the duration and convexity of TIPS based on the nominal

  Let's move forward with a detailed mathematical derivation for the duration and convexity of TIPS based on the nominal

  Let's move forward with a detailed mathematical derivation for the duration and convexity of TIPS based on the nominal
  term structure of interest rates, using continuous compounding and considering the break-even rate (\pi(0, T)).

                                              Deriving Duration and Convexity                                              
                                                                                                                           

  We need to start by setting up the relationship between real bond prices and nominal bond prices, incorporating the
  break-even inflation rate.

                                                1. Real Bond Price Formula:                                                
                                                                                                                           

  For TIPS, the real bond price using continuous compounding over time to maturity (T) is: $Z_{real}(0, T) = 100
  \times \exp(-r_{real} \times T)$

                                           2. Connection to Nominal Bond Prices:                                           
                                                                                                                           

  Given (Z_{real}(0, T)) and the break-even rate (\pi(0, T)), the nominal bond price (Z(0, T)) can be expressed as:
  $Z(0, T) = Z_{real}(0, T) \times \exp(-\pi(0, T) \times T)$ $Z(0, T) = 100 \times \exp(-r_{real} \times T) \times
  \exp(-\pi(0, T) \times T)$ $Z(0, T) = 100 \times \exp(-(r_{real} + \pi(0, T)) \times T)$

  Here, (r_{nominal} = r_{real} + \pi(0, T)) represents the nominal rate after adjustment for inflation expectation.

                                                   3. Deriving Duration:                                                   
                                                                                                                           

  Duration (D) measures the price sensitivity to infinitesimal changes in the interest rate: $D = -\frac{1}{Z(0, T)}
  \cdot \frac{dZ(0, T)}{dr_{nominal}}$

  Using the price formula given: $$\frac{dZ(0, T)}{dr_{nominal}} = \frac{d}{dr_{nominal}} \left 100 \times
  \exp(-(r_{real} + \pi(0, T)) \times T) \right = -T \cdot 100 \times \exp(-(r_{real} + \pi(0, T)) \times T) =-T \cdot Z(0, T)$$

  So, duration given by: $D = - \frac{1}{Z(0, T)} \times (-T \cdot Z(0, T))$ $D = T$

                                                  4. Deriving Convexity:                                                   
                                                                                                                           

  Convexity (C) measures the sensitivity of the duration of a bond to changes in interest rates: $C = \frac{1}{Z(0,
  T)} \cdot \frac{d^2Z(0, T)}{dr_{nominal}^2}$

  Using the earlier derivative: $\frac{d^2Z(0, T)}{dr_{nominal}^2} = \frac{d}{dr_{nominal}} \left$-T \cdot 100 \times
  \exp(-(r_{real} + \pi(0, T)) \times T) \right$$ $= T^2 \cdot 100 \times \exp(-(r_{real} + \pi(0, T)) \times T)$ $=
  T^2 \cdot Z(0, T)$

  So, convexity given by: $C = \frac{1}{Z(0, T)} \times (T^2 \cdot Z(0, T))$ $C = T^2$

                                                        Conclusion                                                         
                                                                                                                           

  Both duration and convexity for TIPS when considered with continuous compounding and against shifts in the nominal term
  structure are dependent directly on the time to maturity, with the effects of the real rate and break-even inflation
  inherently included in the calculations through the nominal rate modified by inflation expectations.

  Would you like to proceed with practical examples using these formulas, or is there another aspect of the risk
  management for TIPS you'd like to explore?