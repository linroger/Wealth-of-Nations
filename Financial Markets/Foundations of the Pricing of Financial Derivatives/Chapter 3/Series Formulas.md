---
tags:
  - '#bond_valuation'
  - '#coupon_bond'
  - '#finite_series'
  - '#infinite_series'
  - '#series_formulas'
  - '#spreadsheet_application'
  - '#yield_to_maturity'
---
# 3.4 SERIES FORMULAS

The following formulas for the sums of various finite and infinite series can be useful.. These expressions are not easy to memorize and do not show up often in finance, but they. can be used on occasion to simplify results, and you should have an accessible list such as the following:

$$
\sum_{i=0}^{n-1}x^{i}={\frac{1-x^{n}}{1-x}},
$$

$$
\begin{array}{r l}&{\begin{array}{r l}&{\sum_{i=0}^{K-\infty}\frac{1-\operatorname{tr}_{i}^{(k+1)}}{(k+1)!},}\ &{+\frac{1}{(k+1)!},}\ &{\frac{1}{(k+1)!},}\end{array}}\ &{\begin{array}{r l}&{\sum_{i=0}^{K-\infty+1}\frac{1-2\operatorname{tr}_{i}^{(k+1)}}{(k+1)!},}\ &{+\frac{1}{(k+1)!},}\ &{\frac{1}{(k+1)!},}\ &{-\frac{1}{(k+1)!}-\frac{1}{(k+1)!},}\end{array}}\ &{\begin{array}{r l}&{\sum_{i^{\prime}}^{K}\exp\left(-\frac{1-(k+1)!}{(k+1)!}+\frac{1}{(k+1)!}\right)}\ &{\frac{1}{(k+1)!},}\ &{\frac{1}{(k+1)!}+\frac{1-(k+1)!^{2}+(k^{2}+2-1)!\times(k+1-\frac{1}{\sqrt{k}})^{2}+1}{(k+1)!}}\ &{-\frac{1}{(k+1)!},}\ &{\frac{1}{(k+1)!}-\frac{1}{(k+1)!},}\ &{\frac{1}{(k+1)!}+\frac{1}{(k+1)!},}\ &{\frac{1}{(k+1)!}-\frac{1}{(k+1)!},}\ &{\frac{1}{(k}\cdot-\frac{1}{(k+1)!}\sum_{i^{\prime}}^{K}\exp\left(-\frac{1}{k}\right)+\frac{1}{(k+1)!}.}\end{array}}\end{array}
$$

$$
\sum_{i=1}^{\infty}{\frac{x^{i}}{i}}=\ln\left({\frac{1}{1-x}}\right){\mathrm{~assuming~}}|x|<1.
$$

For example, the value of a simple annual coupon-paying bond $\left(V_{B}\right)$ can be expressed as

$$
V_{B}=\sum_{i=1}^{N}\frac{\mathrm{C}}{\left(1+y\right)^{i}}+\frac{P a r}{\left(1+y\right)^{N}},
$$

where $C$ denotes the dollar amount of coupon, Par denotes the principle or par amount of the bond, $y$ denotes the yield to maturity expressed in decimal terms, and. $N$ denotes the number of remaining coupons (or years in this case). Rearranging, we have.

$$
V_{B}=C\sum_{i=1}^{N}\frac{1}{\left(1+y\right)^{i}}+\frac{P a r}{\left(1+y\right)^{N}}.
$$

Based on Equation (3.29) and $x=1/\left(1+y\right)$ , we have

$$
\begin{array}{l}{{\displaystyle V_{B}=C\sum_{i=1}^{N}x^{i}+P a r\left(x^{N}\right)=C x\left(\frac{1-x^{n}}{1-x}\right)+P a r\left(x^{N}\right)}}\ {{\displaystyle~=C\frac1{\left(1+y\right)}\left(\frac{1-\frac1{\left(1+y\right)^{N}}}{1-\frac1{\left(1+y\right)}}\right)+\frac{P a r}{\left(1+y\right)^{N}}=\frac C y\left[1-\frac1{\left(1+y\right)^{N}}\right]+\frac{P a r}{\left(1+y\right)^{N}}.}}\end{array}
$$

This result is much easier to manipulate and express in a spreadsheet or other programming platforms.
