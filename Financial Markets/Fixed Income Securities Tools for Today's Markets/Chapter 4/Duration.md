---
tags:
  - bond_valuation
  - duration
  - effective_duration
  - interest_rate_risk
  - yield_based_duration
aliases:
  - DV01
  - bond risk
  - price sensitivity
key_concepts:
  - 'DV01: price change'
  - asset manager perspective
  - bond price sensitivity
  - 'duration: % price change'
  - portfolio duration calculation
---

# 4.4 DURATION  

Another popular metric for interest rate sensitivity is duration. Whereas DV01 measures the change in price for a change in rates, duration measures. the percentage change in price for a change in rates. Like Dv01, duration. can be defined in any one-factor framework, but practitioners often use the. term duration to mean yield-based duration (described in Section 4.7) and use the term effective duration to mean the more general case presented here.  

Using the same notation as in Section 4.2, duration, $D$ , is estimated in terms of the slope as,  

$$
D\approx-{\frac{\Delta P/P}{\Delta y}}=-{\frac{1}{P}}{\frac{\Delta P}{\Delta y}}
$$  

and given in terms of the derivative as,  

$$
D=-{\frac{d P/P}{d y}}=-{\frac{1}{P}}{\frac{d P}{d y}}
$$  

Because $\Delta P/P$ and $d P/P$ both represent percentage change in price, Equations (4.10) and (4.11) express duration as the percentage change in price for a change in rates. Also, for intuition, it is useful to rewrite Equation (4.10) as,  

$$
\frac{\Delta P}{P}\approx-D\Delta y
$$  

Table 4.3 shows the calculation of duration for the three bonds introduced in Table 4.1. Estimating the duration of the NSC 4.10s of 05/15/2121 with Equation (4.10),  

$$
-{\frac{1}{99.9390}}{\frac{99.6990-100.1801}{0.02\%}}=24.1
$$  

Applying Equation (4.12), the percentage change in the price of the NSC bond for a decline in rates of 100 basis points, or $1\%$ , is $-24.1\times$ $(-1\%)=24.1\%$ Hence, a duration of 24.1 roughly means that a fall in rates of 100 basis points increases bond price by $24.1\%$ . This interpretation is only roughly correct because duration, like Dv01, is based on the slope of the price-rate curve and, therefore, is a local measure of price change.  

IABLE 4.3 Calculating Duration for Bonds in Table 4.1, as of Mid-May 2021.   


<html><body><table><tr><td>Bond</td><td>Price -1bp</td><td>Price</td><td>Price +1bp</td><td>Slope</td><td>Duration</td></tr><tr><td>NSC of May 2121</td><td>100.1801</td><td>99.9390</td><td>99.6990</td><td>-2,405.5</td><td>24.1</td></tr><tr><td>Treasury of May 2026</td><td>103.9621</td><td>103.9219</td><td>103.8817</td><td>-402.00</td><td>3.9</td></tr><tr><td>Treasury of Nov. 2050</td><td>84.5899</td><td>84.3906</td><td>84.1919</td><td>-1,990</td><td>23.6</td></tr></table></body></html>  

While traders tend to rely on Dv01, asset managers tend to rely on duration. As in the market-making example of the previous section, traders typically want to ensure that the dollar changes in the value of long and short positions offset each other. Also, because the sizes of their positions can fluctuate rapidly, and because they typically borrow money to buy bonds, they tend to focus on dollar P&L rather than on returns on fixed amounts of invested cash. Asset managers, in contrast, typically invest a slowly changing pool of funds and focus on rates of return. Looking at the durations in Table 4.3, an asset manager immediately sees that the NSC bond has the most interest rate risk, in that an investment in that bond loses $2.41\%$ for a 10-basis point increase in rates. An investment in the Treasury 1.625s of 11/15/2050 has slightly less risk, losing $2.36\%$ for that 10-basis-point increase in rates, while an investment in the Treasury 1.625s of 05/15/2026 has the least risk, losing only. $0.39\%$ in that scenario. The. asset manager can weigh these risks against expected returns and other factors in making a final investment decision..  

This section concludes by noting the duration of a portfolio is equal to the weighted sum of the durations of its component holdings, where the weights are percentages of portfolio value. For example, the duration of a portfolio with $25\%$ of its value in the NSC bonds - with a duration of 24.1 - and $75\%$ of its value in the Treasury 1.625s of $05/15/2026-$ - with a duration of $3.9-$ .5 $25\%\times24.1+75\%\times3.9=8.95$ . The DV01 of a portfolio is the sum of its component Dv01s, while the duration of a portfolio is the value-weighted sum of its component durations, because Dv01 represents a change in price, while duration represents a percentage change in price. A formal proof is in Appendix A4.1.  
