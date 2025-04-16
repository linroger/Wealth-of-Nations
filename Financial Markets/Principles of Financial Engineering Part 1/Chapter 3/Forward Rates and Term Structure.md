---
tags:
  - '#arbitrage_equality'
  - '#bond_prices'
  - '#coupon_bond_pricing'
  - '#default_free_cash_flows'
  - '#forward_rates'
  - '#spot_rate'
  - '#term_structure'
  - '#yield_curve_modeling'
  - '#zero_coupon_bond'
---
# 3.11 FORWARD RATES AND TERM STRUCTURE  

A detailed framework for fixed income engineering will be discussed in Chapter 14. However, some preliminary modeling of the term structure is in order. This will clarify the notation and some of the essential concepts.  

# 3.11.1 BOND PRICES  

Let $\{B(t_{0},t_{i}),i=1,2...,n\}$ represent the bond price family, where each $B(t_{0},t_{i})$ is the price of a. default-free zero-coupon bond that matures and pays $\$1$ at time $t_{i}.$ These $\{B(t_{0},t_{i})\}$ can also be viewed as a vector of discounts that can be used to value default-free cash flows.  

For example, given a complicated default-free asset,. $A_{t_{0}}$ , that pays deterministic cash flows. $\{C_{t_{i}}\}$ occurring at arbitrary times,. $t_{i},i=1,...,k$ we can obtain the value of the asset easily if we assume the following bond price process:.  

$$
A_{t_{0}}=\sum_{i}C_{t_{i}}B(t_{0},t_{i})
$$  

That is to say, we just multiply the $t_{v}$ th cash flow with the current value of one unit of currency that belongs to $t_{i},$ and then sum over $i$  

This idea has an immediate application in the pricing of a coupon bond. Given a coupon bond. with a nominal value of $\$1$ that pays a coupon rate of $c\%$ at times $t_{i:}$ the value of the bond can easily be obtained using the preceding formula, where the last cash flow will include the principal as well.  

# 3.11.2 WHAT FORWARD RATES IMPLY  

In this chapter, we obtained the important arbitrage equality  

$$
1+F(t_{0},t_{1},t_{2})\delta=\frac{B(t_{0},t_{1})}{B(t_{0},t_{2})}
$$  

where $F\left(t_{0},t_{1},t_{2}\right)$ is written in the expanded form to avoid potential confusion.32 It implies a forward rate that applies to a loan starting at $t_{1}$ and ending at $t_{2}$ . Writing this arbitrage relationship for. all the bonds in the family. $\{B(t_{0},t_{i})\}$ , we see that  

$$
\begin{array}{r}{1+F(t_{0},t_{0},t_{1})\delta=\cfrac{B(t_{0},t_{0})}{B(t_{0},t_{1})}}\ {1+F(t_{0},t_{1},t_{2})\delta=\cfrac{B(t_{0},t_{1})}{B(t_{0},t_{2})}}\end{array}
$$  

$$
1+F(t_{0},t_{n-1},t_{n})\delta=\frac{B(t_{0},t_{n-1})}{B(t_{0},t_{n})}
$$  

Successively substituting the numerator on the right-hand side using the previous equality and noting that for the first bond we have. $B(t_{0},t_{0})=1$ , we obtain  

$$
B(t_{0},t_{n})=\frac{1}{(1+F(t_{0},t_{0},t_{1})\delta)...(1+F(t_{0},t_{n-1},t_{n})\delta)}
$$  

We have obtained an important result. The bond price family $\{B(t_{0},t_{i})\}$ can be expressed using the forward rate family,.  

$$
\{F(t_{0},t_{0},t_{1}),...,F(t_{0},t_{n-1},t_{n})\}
$$  

Therefore, if all bond prices are given we can determine the forward rates.  

# 3.11.2.1 Remark  

Note that the first' forward rate $F(t_{0},t_{0},t_{1})$ is contracted at time $t_{0}$ and applies to a loan that starts at time $t_{0}$ Hence, it is also the. $t_{0}$ spot rate:  

$$
(1+F(t_{0},t_{0},t_{1})\delta)=(1+L_{t_{0}}\delta)=\frac{1}{B(t_{0},t_{1})}
$$  

We can write this as  

$$
B(t_{0},t_{1})=\frac{1}{(1+L_{t_{0}}\delta)}
$$  

The bond price family $B(t_{0},t_{i})$ is the relevant discounts factors that market practitioners use in. obtaining the present values of default-free cash flows. We see that modeling. $F_{t_{0}}^{\prime}\mathrm{{^{\prime}s}}$ will be quite helpful in describing the modeling of the yield curve or, for that matter, the discount curve.  
