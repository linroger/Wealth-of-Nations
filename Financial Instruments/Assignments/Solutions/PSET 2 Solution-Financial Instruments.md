---
title: PSET 2 Solution-Financial Instruments
tags:
  - bond_pricing
  - bootstrap_procedure
  - financial_instruments
  - inverse_floater
  - term_structure
  - yield_curve
aliases:
  - Homework 2 Solution
  - PSET 2
key_concepts:
  - Bond prices
  - Bootstrap procedure
  - Leveraged Inverse Floater
  - Semi-annual frequency
  - Treasury securities data
---

---

title: PSET 2 Solution
title: PSET 2 Solution
title: PSET 2 Solution
title: PSET 2 Solution
title: PSET 2 Solution
title: PSET 2 Solution

# PSET 2 Solution-Financial Instruments

Solution to Homework 2
John Heaton March 31,  2024

### Inverse Floater
1. (PP) The size of the Treasury securities data available on February 17,  2009,  is huge. In order to perform the bootstrap procedure,  we need securities at a semi-annual frequency. We can cherry-pick from the dataset such securities. Table 1 contains the data used in the bootstrap procedure. Unfortunately,  already at $T=10$ years,  we do not have notes with maturities at a semi-annual frequency; using bonds,  we can get to $T=12.5$,  but they may have some price differences due to liquidity. (For instance,  see the break at $T=10$ in both Figure 1 and 2.) Even using bonds,  we must stop the procedure after $T=12.5$ as there is no more data at a semi-annual frequency.
To bootstrap the discounts,  we can use the procedure illustrated in the teaching notes. For every $\dot{i}$,
$$Z(0,       T_i)=\frac{P(0,       T_i)-c^i/2(\sum_{j=1}^{i-1}Z(0,       T_j))}{1+c^i/2}$$
Alternatively,  we can use a matrix formulation. In line with the semi-annual frequency,  let $T_{i}=\frac{i}{2}$ for $1\leq i\leq25$. Define a cash-flow matrix,  $C$,  where an element $t_{ij}$ denotes the payoff at time $T_{j}$ of the bond with maturity $T_{i}$. By ordering the bonds increasing in maturity,  $C$ is lower diagonal. Also,  let $P$ denote a column vector with element $P_{i}$ equal to the price of the bond with maturity $T_{i}$. In particular,  we have
$$\left.\left[\begin{array}{c}P^1(0,  T_1)\\P^2(0,  T_2)\\\vdots\\P^n(0,  T_n)\end{array}\right.\right]=\left[\begin{array}{ccccc}c^1/2+100&0&0&\ldots&0\\c^2/2&c^2/2+100&0&\ldots&0\\\vdots&\vdots&\ddots&&\\c^n/2&c^n/2&c^n/2&\ldots&c^n/2+100\end{array}\right]\left[\begin{array}{c}Z^1(0,  T_1)\\Z^2(0,  T_2)\\\vdots\\Z^n(0,  T_n)\end{array}\right] {}$$
Or,  in vector notation
$$P=CZ$$
where $Z$ is a column vector with $\dot{\boldsymbol{i}}$ element equal to $Z(0,    T_{i})$.Then,  we obtain
$$Z=C^{-1}P$$
Note that the $P$ vector is made up of the invoice or dirty prices. Here,  the securities are handpicked to have zero accrued interest,  so this simplifies. The calculations below take the price to be the mean of the bid and ask quotes.
(PP) Use the bond data as of February 17,  2009,  and applying formulas on page 48 from TN 1,  the bootstrapped yields to maturity for maturity 0.5,  1,  and 1.5 are calculated as follows:
$$\begin{aligned}
&Z(0,    0.5)={\frac{P^{1}(0,    0.5)}{1+{\frac{c^{1}}{2}}}}={\frac{1.0150}{1+{\frac{0.035}{2}}}}=0.9975 \\
&Z(0,    1)={\frac{P^{2}(0,    1)-{\frac{c^{2}}{2}}Z(0,    0.5)}{1+{\frac{c^{2}}{2}}}}={\frac{1.0291-{\frac{0.035}{2}}0.9975}{1+{\frac{0.035}{2}}}}=0.9942 \\
&Z(0,    1.5)=\frac{P^{3}(0,    1.5)-\frac{c^{3}}{2}(Z(0,    0.5)+Z(0,    1))}{1+\frac{c^{3}}{2}}=\frac{1.0522-\frac{0.0413}{2}(0.9975+0.9942)}{1+\frac{0.0413}{2}}= 0.9907
\end{aligned}$$
Where the bond prices are determined as the average of bid and ask values.
(CP) Table 1 displays the data from the selected securities. We show the difference in term structure depending on the type of securities used. The left panels show the bonds that were issued most recently (“new bonds“),    while the right panel shows the bonds that were issued long ago. The column type is 2 for a note and 1 for a bond.
Figures 1 and 2 plot the discount function and the yield curve implied by these calculations. The vertical dotted line denotes the point at which bond securities are used to bootstrap also for the “new bonds“. Clearly,      depending on the type of securities used,      we can get quite different results. The period surrounding 2009 showed large differences between new bonds and old bond prices,      due to liquidity. Newly issued bonds were much more liquid than old bonds,   which resulted in large price discrepancies. (The comparison between old and new bonds was not part of the assignment).
Table 1: Securities used in Bootstrap
```latex
\usepackage{booktabs}
\begin{document}
\tiny
\renewcommand{\arraystretch}{1.3}
\begin{tabular}{|c|c|c|c|c|c|c|c|c|c|c|c|}
\hline
\textbf{Maturity} & \textbf{Type} & \textbf{Coupon} & \textbf{Ask} & \textbf{Bid} & $\mathbf{T_i}$ & \textbf{Maturity} & \textbf{Type} & \textbf{Coupon} & \textbf{Ask} & \textbf{Bid} & $\mathbf{T_i}$ \\ \hline
20090815 & 2 & 3.5   & 101.4844 & 101.5156 & 0.4944 & 20090815 & 2 & 6.0   & 102.6797 & 102.7109 & 0.4944 \\ \hline
20100215 & 2 & 4.125 & 102.8945 & 102.9258 & 0.9944 & 20100215 & 2 & 5.75  & 105.7461 & 105.7773 & 0.9944 \\ \hline
20100815 & 2 & 3.5   & 105.2031 & 105.2422 & 1.4944 & 20100815 & 2 & 5.875 & 107.6875 & 107.7344 & 1.4944 \\ \hline
20110215 & 2 & 5.0   & 108.5313 & 108.5625 & 1.9944 & 20110215 & 2 & 5.0   & 108.5313 & 108.5625 & 1.9944 \\ \hline
20110815 & 2 & 3.875 & 110.2656 & 110.2969 & 2.4944 & 20110815 & 2 & 5.0   & 110.2656 & 110.2969 & 2.4944 \\ \hline
20120215 & 2 & 1.375 & 100.4453 & 100.4766 & 2.9944 & 20120215 & 2 & 4.875 & 110.7656 & 110.8125 & 2.9944 \\ \hline
20120815 & 2 & 3.875 & 109.9063 & 109.9531 & 3.4944 & 20120815 & 1 & 3.875 & 109.9063 & 109.9531 & 3.4944 \\ \hline
20130215 & 2 & 4.25  & 111.6719 & 111.7188 & 3.9944 & 20130215 & 1 & 4.25  & 111.6719 & 111.7188 & 3.9944 \\ \hline
20130815 & 2 & 4.25  & 113.3594 & 113.3906 & 4.4944 & 20130815 & 1 & 4.25  & 113.3594 & 113.3906 & 4.4944 \\ \hline
20140215 & 2 & 4.25  & 113.2031 & 113.2344 & 4.9944 & 20140215 & 1 & 10.625 & 149.9219 & 149.9531 & 4.9944 \\ \hline
20150215 & 2 & 3.5   & 107.0156 & 107.0469 & 5.4944 & 20150215 & 1 & 10.625 & 149.9219 & 149.9531 & 5.4944 \\ \hline
20150815 & 2 & 3.5   & 107.6406 & 107.6719 & 5.9944 & 20150815 & 1 & 4.875  & 117.0781 & 117.1094 & 5.9944 \\ \hline
20160215 & 2 & 4.875 & 117.0781 & 117.1094 & 6.4944 & 20160215 & 1 & 4.875  & 117.0781 & 117.1094 & 6.4944 \\ \hline
20160815 & 2 & 4.625 & 115.4844 & 115.5156 & 6.9944 & 20160815 & 1 & 4.625  & 115.4844 & 115.5156 & 6.9944 \\ \hline
20170215 & 2 & 4.75  & 116.8438 & 116.875  & 7.4944 & 20170215 & 1 & 8.875  & 144.9531 & 145.0000 & 7.4944 \\ \hline
20170815 & 2 & 3.5   & 107.6406 & 107.6719 & 7.9944 & 20170815 & 1 & 8.875  & 144.9531 & 145.0000 & 7.9944 \\ \hline
20180215 & 2 & 4.75  & 111.875  & 111.9063 & 8.4944 & 20180215 & 1 & 3.5   & 107.5781 & 107.6406 & 8.4944 \\ \hline
20180815 & 2 & 8.125 & 143.8438 & 143.875  & 8.9944 & 20180815 & 1 & 4.875 & 111.8750 & 111.7188 & 8.9944 \\ \hline
20190215 & 2 & 2.75  & 100.875  & 100.9375 & 9.4944 & 20190215 & 1 & 8.875 & 149.5938 & 149.6250 & 9.4944 \\ \hline
20190815 & 2 & 8.125 & 143.8438 & 143.875  & 9.9944 & 20190815 & 1 & 8.125 & 143.8438 & 143.8750 & 9.9944 \\ \hline
20200215 & 2 & 8.75  & 147.7266 & 147.7578 & 10.4944 & 20200215 & 1 & 8.875 & 147.7266 & 147.7578 & 10.4944 \\ \hline
20200815 & 2 & 8.75  & 151.1563 & 151.1875 & 10.9944 & 20200815 & 1 & 8.75  & 151.1563 & 151.1875 & 10.9944 \\ \hline
20210215 & 2 & 7.875 & 143.5391 & 143.5703 & 11.4944 & 20210215 & 1 & 7.875 & 143.5391 & 143.5703 & 11.4944 \\ \hline
20210815 & 2 & 8.125 & 147.1094 & 147.1406 & 12.4944 & 20210815 & 1 & 8.125 & 147.1094 & 147.1406 & 12.4944 \\ \hline
\end{tabular}
\end{document}
```
%%caption ![500](https://storage.simpletex.cn/view/ff2ZSGmy0NZgg8nslPSF36PDEMxs3ARmc)
Figure 1: Zero Coupon Discount Curves
%%caption ![500](https://storage.simpletex.cn/view/frkXwNpZpG1RX0Oaq3k94sVV3motESwTt)
Figure 2: Zero Coupon Yield Curves
2. (PP) The value of the Leveraged Inverse Floater can be computed as follows. The coupon rate at any time $t$ is given by
$$c(T_i)=10\%-2\times r_2(T_{i-1})$$
The investor who is long the Leveraged Inverse Floater receives a $10\%$ fixed coupon and pays “floating" at the rate that is twice the floating six-month T-bill rate (six months lag). At maturity,    in addition,    the investor will receive the principal. Therefore,    it is as if the investor is long one $10\%$ coupon bond with five-year maturity and short 2 floating rate bonds with five-year maturity. This combination ensures receiving a cash flow over time identical to (1). However,    such a position would imply an outflow of the principal at maturity,    instead of an inflow. It follows that we need to add two zero-coupon bonds with five-year maturity to exactly mimic all of the cash flows from the Leveraged Inverse Floater.
(CP) The price of the inverse floater is then
$$P_{IFL}(0;5)=P_{Fixed}(0,      5)-2\times P_{Fl}(0;5)+2\times Z(0;5)$$
Given the discount function in Table 1 above,    we have
$$\begin{array}{rcl}P_{Fixed}(0;5)&=&140.74;\\P_{Fl}(0;5)&=&100;\\Z(0;5)&=&92.35\end{array}$$
Obtaining a value for the Leveraged Inverse Floater equal to
$$P_{IFL}(0;5)=125.43$$
Note that in the computation above,    we are implicitly assuming that the coupon $c(T_{i})$ will never get negative,    as the Leveraged Inverse Floater would never require an additional payment from investors.
(PP) What is the benefit from going long the Leveraged Inverse Floater? The current semi-annual rate on February 17,    2009,    was $0.49\%$. Therefore,    the current cash flow from this security is $9.02\%$ so long as the short-term rate does not increase. Given the data above,    a fixed-rate coupon bond with a 5-year maturity has a coupon equal to $c=4.0\%$. Of course,    this bond is also cheaper at 111.70. However,    the discount function above implies that the price of a fixed-rate 5-year bond with a coupon of $9.2\%$ would have a price of 135.97. As long as the short rate does not move,    the Leveraged Inverse Floater generates a higher cash flow without increasing the price comparably. For this reason,    investments in this type of instruments are called “yield-enhancing strategies“. Yet,    they imply a speculation on the direction of interest rate movements,    as discussed next.
3. (PP) The duration of the fixed-rate bond is based on the following general formula
$$D_{Fixed}=\sum_{I=1}^nw_iT_i=4.2141$$
where $T_{I}=0.5,      1,      …,      5$ and
for $T_{n}=5$
$$w_i=\frac{Z(0;T_i)c_i/2}{P_{Fixed}}\text{for}I=T_i=0.5,      …,      4.5\text{and}w_n=\frac{Z(0;T_n)(1+c_i/2)}{P_{Fixed}}\text{for}$$
The duration of the Leveraged Inverse Floater can be computed from the rule“the duration of a portfolio is equal to the weighted average of the durations.” So,    first,    we need to compute the duration of each of the securities in formula (2). The duration of the zero coupon bond $Z(0,      5)$ is $D_{Z}=5$,    while the duration of the Floating Rate Bond is $D_{FL}=0.5$,    six months,    and the duration of the fixed rate bond is $D_{Fixed}=4.2141$ as shown above.
As shown above.
(CP) It then follows that the duration of the Leveraged Inverse Floater is
$$\begin{aligned}D_{LIF}&=\quad\frac{1}{P_{LIF}}\times(P_{Fixed}(0,      5)\times D_{Fixed}-2\times P_{Fl}(0;5)\times D_{Fl}+2\times Z(0;5)\times D_{Z})\\&=\quad\frac{1}{125.43}\times(140.74\times4.214-2\times1\times0.5+2\times92.35)\times5)\\&=\quad11.29\end{aligned}$$
(PP) According to the value of the Leveraged Inverse Floater,    it is obvious that it has quite a high sensitivity to interest rates. Figure 3 plots the value of the Leveraged Inverse Floater,    plotted against a parallel shift in the term structure of interest rates. The decline in value for a shift up in interest rates is quite dramatic. The dash-dotted line plots the decline in value for the 5-year fixed rate bond,    with coupon rate $4.0\%$,    which is valued at 111.70 on February 17,    2009. The duration of the 5-year fixed bond is 4.60. Thus,    the sensitivity to interest rates is much smaller,    as illustrated in Figure 3.
Finally,    note in Figure 3 that the perturbations are mainly positive. This is because the short rate is already at $0.49\%$,    so negative parallel shifts must be quite small to keep the short rate sensible.
(PP) In general,    convexity of the fixed-rate bond is calculated as follows:
$$C_{Fixed}=\sum_{I=1}^nw_iT_i^2=19.6431$$
Accordingly,    convexity of the inverse float can be computed as the weighted average of the convexities of the securities in the mimicking portfolio. The convexity of the zero-coupon bond is $C_{Z}=5^{2}=25$,    while the convexity of the floating-rate bond is essentially zero $C_{Fl}=0.5^{2}=0.25$.
(CP) It follows that the convexity of the inverse float is
$$\begin{aligned}C_{LIF}&=\quad\frac{1}{P_{LIF}}\times(P_{Fixed}(0,      5)\times C_{Fixed}-2\times P_{Fl}(0;5)\times C_{Fl}+2\times Z(0;5)\times C_{Z})\\&=\quad\frac{1}{125.43}\times(140.74\times19.6431-2\times100\times0.25+2\times92.35)\times25)\\&=\quad58.45\end{aligned}$$
Compare this to the quoted 5-year fixed-rate bond which has a much lower convexity of 22.30.
%%caption![Figure 3](https://storage.simpletex.cn/view/fC6VUtUhbSTbnFXLqVBsgzhuG222mTeaw)
Figure 3: