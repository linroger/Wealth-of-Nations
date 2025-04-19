---
tags:
  - derivatives
  - finite_difference
  - mathematical_finance
  - option_pricing
  - put_option
aliases:
  - FDP
  - Option Valuation
  - Put Pricing
key_concepts:
  - Boundary conditions
  - Finite difference method
  - Option valuation
  - Put option pricing
  - Time steps
---

# 24.4 FINITE DIFFERENCE PUT OPTION PRICING

If the options are puts, then the procedure is exactly the same but the following three conditions replace the corresponding conditions for calls:

$$
\begin{array}{r l}&{w_{y,t}=X e^{-r_{c}\tau}\mathrm{~when~}\eta\to0}\ &{w_{y,t}=0\mathrm{~for~all~}t\mathrm{~when~}y\to\infty}\ &{w_{y,t}=\operatorname*{max}(0,X-e^{y})\mathrm{~for~all~}y.}\end{array}
$$
