---
tags:
  - bond_convexity
  - bond_portfolio
  - convexity_risk
  - duration
  - yield_curve
aliases:
  - Bond Convexity
  - Convexity in Bonds
key_concepts:
  - Bond portfolio curvature
  - Convexity definition
  - Duration relationship
  - Parallel yield shifts
  - Taylor series expansion
---

# 4.11 CONVEXITY  

The duration relationship applies only to small changes in yields. This is illustrated in Figure 4.2, which shows the relationship between the percentage change in value and change in yield for two bond portfolios having the same duration. The gradients of the two curves are the same at the origin. This means that both bond portfolios change in value by the same percentage for small yield changes and is consistent with equation (4.12). For large yield changes, the portfolios behave differently. Portfolio $X$ has more curvature in its relationship with yields than portfolio Y. A factor known as convexity measures this curvature and can be used to improve the relationship in equation (4.12).  

A measure of convexity is  

$$
C=\frac{1}{B}\frac{d^{2}B}{d y^{2}}=\frac{\sum_{i=1}^{n}c_{i}t_{i}^{2}e^{-y t_{i}}}{B}
$$  

From Taylor series expansions, we obtain a more accurate expression than equation (4.9), given by  

$$
\Delta B=\frac{d B}{d y}\Delta y+\frac{1}{2}\frac{d^{2}B}{d y^{2}}\Delta y^{2}
$$  

This leads to  

$$
\frac{\Delta B}{B}=-D\Delta y+\frac{1}{2}C(\Delta y)^{2}
$$  

For a portfolio with a particular duration, the convexity of a bond portfolio tends to be greatest when the portfolio provides payments evenly over a long period of time. It is least when the payments are concentrated around one particular point in time. By choosing a portfolio of assets and liabilities with a net duration of zero and a net convexity of zero, a financial institution can make itself immune to relatively large. parallel shifts in the zero curve. However, it is still exposed to nonparallel shifts..  

![](63ab9ec7d18fe0dd81529dcbd87f3a2e9a1b6345dfd330869d1e4ee5547a9268.jpg)  
Figure 4.2 Two bond portfolios with the same duration.  
