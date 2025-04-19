---
linter-yaml-title-alias: PSET 7 SOLUTIONS
title: PSET 7 SOLUTIONS
tags:
  - american_option
  - american_put_option
  - dividend_payments
  - early_exercise
  - european_call_option
aliases:
  - American Options
  - Call Option
  - Homework 7
  - PSET 7
key_concepts:
  - American option payoff
  - Continuously compounded interest
  - Dividend payments impact
  - Early exercise value
  - Risk neutral probability
---

# PSET 7 SOLUTIONS
## WINTER 2024

John Heaton

## SOLUTION TO HOMEWORK

7 1. American Options

- (a) Figure (1) shows the tree for the stock price implied by the parameters.
 ![500](df264bf277d7bc4ab9dfe12e767d9644.png)
Let's start with the call option. The first thing to remember is that at maturity,  T = 3,  the American option payoff will be equivalent to the payoff of a European call option:$max(S_T − K,        0)$. Given this we start working backward along the tree. For each node we compute the value to waiting,  and compare it to the value from early exercise. The value to waiting is just the discounted risk neutral valuation of the option. In general,  say we are in the node (*i,  j*) 1,  the value to waiting is

$$V_{i,       j}^{w a i t}=Z(i+1)\cdot[q^{*}\cdot V_{i+1,       j}+(1-q^{*})\cdot V_{i+1,       j+1}]$$
Where i denotes the period $i − 1$ and $j$ is the index for the node,  starting from the top (e.g.$S_u·u·u = S_{4,       1}$)
where $Z(i + 1)$ is the value of a zero coupon bond maturing the next period and q∗ is the risk neutral probability. Given the continuously compounded interest rate $r$ we can easily find that $Z(i + 1)$ as equal to $Z(i + 1) = e^{−r·dt}$. In our case $r = 0.02$ and $dt = 1$,  so $Z(i + 1) = 0.98$. We also know that the risk neutral probability $q^∗$ is given by

$$q^{*}={\frac{e^{r\cdot d t}-d}{u-d}}={\frac{1.02-0.91}{1.10-0.91}}=0.58$$
Figure (2) shows the starting point for the tree needed to price the American call option.
 ![500](8795385da6e8054a332cf681801651a0.png)

Before proceeding back to period$i = 1$,  we compare the values to waiting ("wait" in the tree) with the values from early exercise. At each node the value from early exercise will be simply equal to$$C_{i,       j}^{E E}=m a x(S_{i,       j}-K)$$where EE stands for "Early Exercise." Figure (3) compares both values. As you can see,  the value to waiting is always greater than the value to early exercise,  so we the option values at period$i = 2$will be equal to the values from waiting. We then keep going backward until we reach period$i = 0$. Figure 4 displays the result. We apply the same procedure for the American put. Figure (5) shows the period$i = 2$comparison between values to waiting and values to early exercise.
 ![500](97212d4591459bf8b7bb76c6a6024a87.png)

In this case we note that$P_{33}^{wait}=15.38<P_{3.3}^{EE}=17.36$,  therefore the option value in node (3,  3) will be equal to$P_{3,       3}=P_{3,       3}^{EE}=17.36.$Going back until period$i=0$we obtain the tree shown in Figure (6). Early exercise nodes are underlined.

(b) As pointed out before,  the put option is exercised before maturity at node (3,  3). This happens because the option is sufficiently in the money and the expected return from waiting is lower than the return from exercising early. The call is never exercised early. We already know it is never optimal to early exercise an American call option on a non dividend paying stock.
(c) The new tree for the American call is reported in Figure (7)
While Figure (8) reports the tree for the American put option. Again,  early exercise nodes are underlined. In this case early exercise of the put is optimal twice,  namely at nodes (2,  2) and (3,  3).

The reason is that when stock price drops,  the benefit that we get from investing the strike price at the risk free rate are greater when the risk free rate is greater,  and this increases the benefits from early exercise. Note that at the same time,  as interest rate goes up the value of the put goes down. More in detail the value of the European put goes down by much more than the American put and this is due to the fact that the value from early exercise increases.

 ![500](af4fa979544f686ce9c72cd984392f15.png)
(d) When we have dividend payments the computation is a bit trickier.
With a dividend we must worry about the drop stock price that occur as a consequence of a payment to shareholders. In other words,  dividends are the amounts of price drops. There are two ways to deal with this: change the stock price outcomes and fix the risk-neutral probabilities or change the stock price outcomes and fix the risk-neutral probabilities. The spreadsheet "HW7 Solution Question 1" provides details on both approaches. Here I outline how to do the calculation with a change in the stock price outcome.
Since we have a proportional dividend at every period,  to compute the tree for the stock price use the following steps:

- (i) Start from current stock price
- (ii) Compute the price change in the next node given the u and d parameters. This will be referred to as a pre-dividend price
- (iii) Compute the after-dividend price by subtracting the amount of the dividends (in this case multiplying the pre-dividend price times$(1 − y_1)$,  where$y_1$is the proportional dividend paid at the end of each period)
 ![500](b9555bbda73a84037049b736d3e18e0c.png)
- (iv) Repeat steps (ii) and (iii) until the last period We therefore have two stock prices for each period. Optimal exercise will be different for calls and puts. For calls it may be optimal to exercise right before the dividend is paid,  while for puts it may be optimal to exercise right after dividend payment. We compute the **call** payoff and value from early exercise using the **pre-dividend** stock price,  while we compute the **put** payoff and value from early exercise of the **after-dividend** price. Figure (9) shows the stock price tree. The amounts above the arrows are the pre-dividend prices (again,  used for calls) and the amounts below the arrows are the after-dividend prices (used for puts). We can now use the same procedure as above to compute the option prices,  again,  using the same risk neutral probability computed in point (1.a),  that is$p^∗ = 0.58$. Figure (10)
shows the tree for the American call option. Early exercise nodes are underlined. Figure (11) below shows the tree for the American put option. Compared to the results from parts (1.a) and (1.c) we see that the put is now more valuable while the call is less valuable. This is expected as the effect of the dividend is to lower the stock price and the put becomes more valuable as the stock price goes down. If we compare the results only with part (1.c) we see that with low interest rate and high dividends it is optimal to exercise early the American Call,  while with no dividends and high interest rate early exercise of the put is useful.
 ![500](f7c89fdaa4294da77035fa2b8c387ced.png)
 ![500](be3bfccfdda1e78e793c0b4569bd733e.png)
 ![500](29a118e77df33aaa9d4ed27037d34a6a.png)
 ![500](1d891fea8f3f8944a962a62765d95b90.png)
 ![500](48f9ed99105ac33829a1dcfa648c8b48.png)
 ![500](956d1fac8764e5d73f4b01d44f502435.png)

## PART 2: CITIGROUP'S DEFAULT PROBABILITY DURING THE CREDIT CRISIS

- We can start by computing the number of shares using the market capitalization and the stock price on Feb 13 2009. We get (in billions)
$$N={\frac{M C a p}{S}}={\frac{19.02}{3.49}}=5.450$$
- To compute the value of assets and volatility of assets we follow the procedure described at the end of the directions. It is worth it though to quickly describe the theoretical framework that we follow. In a nutshell we solve a system of two equations in two unknowns. Since this system is a bit more complicated than the classical systems we have seen,  we need to use a solver.
What are the two equations and the two unknowns? We need to find the value of assets VA and the volatility of assets σA. These are our unknowns. What are the equations? The Merton Model says that we can consider the equity of a firm as a call option on its assets,  with strike price equal to the face value of the debt. If we make reasonable assumptions and we assume that assets returns are log-normally distributed,  we can use the Black and Scholes formula to price the option. So we can already write

$$V_{E}=B S C$$
where *BSC* means "Black-Scholes-Merton Call". This is one of our two equations.

What are the inputs that we need to apply the Black and Scholes (and Merton) formula?

We need the value of the underlying (VA),  the strike price (K),  the risk free rate (r),  the annualized volatility of the returns of the underlying (σA) and the maturity of the option
(T). So we can write
$$V_{E}=BSC\left(V_{A},       K,       r,       \sigma_{A},       T\right)\tag{1}$$
indeed the two unknowns VA and σA appear in equation (2).

What is the second equation? The idea is if equity is a call option on a firms' assets,  then the volatility of equity (that is the volatility of the call) is related to the volatility of the underlying (that is the volatility of the assets) according to some determined equation.

Under the assumptions above,  the volatility of equity is:
$$\sigma_{E}=\left(\frac{V_{A}\cdot N(d_{1})}{V_{A}\cdot N(d_{1})-K\cdot e^{-r\cdot T}\cdot N(d_{2})}\right)\cdot\sigma_{A}\tag{2}$$
which is our second equation.

Where do we get the other parameters? Some of them are easy to get (like VE,  that is the market capitalization,  or σE which can be computed using historical data),  but for some others we need to make assumptions. For example what's the strike price of the option? This should be "the face value of the Debt." But the Debt is not a zero coupon bond,  since it pays coupons! We just pick a value assuming that it is a zero coupon bond…". A similar reasoning is followed for the other parameters.

Let's get back to Citi case. We use the Excel file to compute both VA and σA. Let's start with the inputs: for the strike price (cell B6),  what value do we use? We have information on deposits,  short term debt,  long term debt and other liabilities. The directions tells us to assume that the short term debt is paid out immediately. Why so? Simply because we are making adjustments that will let equity resemble a call option as much as possible in the case of a bank. The idea is that with banks deposits and short-term debt will flee the bank when trouble approaches so that they will be repaid in full no matter what. For example these will be repaid by cash and other short-term securities on the balance sheet. What's left? We still have long term debt,  other liabilities and the equity. Equity is still a call option,  but it is a call option on a smaller firm; the underlying security for the option is the residual (after short term debt has been paid) assets of the firm,  that we can denote by VRA. We can still use our system of equations,  but we have to be careful with the parameters
$$\left\{\begin{array}{c}{V_{E}=BSC\left(V_{RA},       K,       r,       \sigma_{RA},       T\right)}\\ \\ {\sigma_{E}=\left(\frac{V_{A}\cdot N(d_{1})}{V_{RA}\cdot N(d_{1})-K\cdot e^{-T}\cdot T\cdot N(d_{2})}\right)\cdot\sigma_{RA}}\end{array}\right.$$
We assume that the volatility of assets remains the same after having paid the short term debt,  so we can safely write$σ_{RA} = σ_A$. Now that we don't have the short term debt any more it's easier to think about Citi equity as an option. What's the strike? We need to make an assumption. We can assume for instance that the residual debt (that is long term debt + other liabilities) is a zero coupon bond,  with face value equal to$K = LT +OL = 791.79.$

And the maturity? Let's assume$T=7.$Below is a table showing how the results would have changed for different values of$T$) What about the risk free rate? We get it from the Excel file (I assume that it is annually compounded. Note that we have two interest rates,  one for each date,  that are$$r_1^{10/10}= 3.27\% \text{ and } r_1^{10/14}= 3.48\%)$$Same for the volatility of equity,  we have$$\sigma_E^{10/10}= 1.7551 \text{ and } \sigma_E^{10/14}= 1.8947$$We are now ready to use the solver Here are the steps (for Oct$10$only. You can do the same for Oct 14 and check the results):

 - Strike price: Cell B6 equal to 791.79
 - Maturity: Cell B$7$equal to 7
 - Continuously compounded risk free rate: Cell B8 equal to$ln(1+ 0.0327) = 0.0322$
 - Dividend yield: Cell B9 equal to$0$
 - Call Price: this is the market value (that is the market capitalization) of equity. We get$$MCap^{10/10}=S^{10/10}\cdot N=75.75$$,  so Cell B10 equal to 75.75
- Vol Call: this is the volatility of the call option,  that is the volatility of equity. Cell B11 equal to 1.7551
- Adj. Vol Call: this cell,  as explained,  allows us to adjust the formula for the volatility of assets. You need to plug the short term debt (that is short term borrowings + deposits). Cell B12 equal to 1,  132.617
- Call the solver: (Excel 2003 shortcut ALT+T,  V)
- Setup the solver: Target Cell is B26 (simply write "TargetCall"); "By changing cells": write "S 2,  sig 2c". **Note:** you don't need to be an Excel genius to do this,  since everything was written in the cells highlighted in purple.
- Run the solver: press Enter
We can read the results in cells E5 and E6. We find that the value of the residual assets is$V^{10/10}_{RA}= 583.75$and that the volatility of residual assets (that is the same,  by assumption as the volatility of assets) is

$$\sigma_{R A}^{10/10}=\sigma_{A}^{10/10}=0.1539$$
We need one last step,  that is computing the value of assets$V^{10/10}_A$Since$V_{RA} = V_A−S−D$,  then$$V_A^{10/10}=V_{RA}^{10/10}+S+D=583.75+1,       132.62=1,       716.37$$
Applying this same procedure for Oct 14 2008 we get
$$\sigma^{10/14}_{RA}=\sigma^{10/14}_{A}=0.2098V^{10/14}_{A}=1,       692.51$$

- According to KMV model,  the default probability in Td years (or expected default frequency) is given by

$$
    p_{T_d} = N\left(-d_2^d\right)$$

with $d_2^d$ being the distance to default defined as $$
    d_2^d = \frac{\ln\left(\frac{V_{A0}}{F}\right) + \left(\mu - \frac{\sigma_A^2}{2}\right) \cdot T_d}{\sigma_A \cdot \sqrt{T_d}}$$
where $V_A^0$ is the value of assets,        $F$ is the default point,        $µ$ is the expected risk natural return of assets and $σ_A$ is the volatility of assets. We have computed $V_A^0$ and $σ_A$. In addition we know that according to KMV
$$F=S T D+{\frac{1}{2}}\cdot L T D$$
we just need to make an assumption about $\mu.$ It is reasonable to assume $\mu=0.15$ (same as the value used in the Teaching Notes for Enron). We can thus compute $d_2^d$ and $N\left ( d_2^d\right )$ for both days. We find (I will simplify the notation taking out the $d$ superscript) $$\left\{\begin{array}{c}d_{2}^{10/10}=1.6509\\ \\ N\left(-d_{2}^{10/10}\right)=0.0494\end{array}\right.$$
and
$$\left\{\begin{array}{c}d_{2}^{10/14}=1.096\\ \\ N\left(-d_{2}^{10/14}\right)=0.1365\end{array}\right.$$

We are now ready to answer to the questions:
- (a)After the bailout,        on Oct 14,        the probability of default increases counterintuitively. Indeed we would expect the bailout to insure markets that the institution will be safer. This is an issue with the Merton model: For given $σ_A$,        there is a very tight relation between equity value and volatility of equity. The bailout announcement made equity increase from 75 to 100 billion. According to the relationship assumed in the Merton model,        the volatility of equity should have declined substantially (as $V_E$ is inversely related to $σ_E$). Since the realized volatility of equity did not decrease (as $σ^{10/14}_E >σ^{10/10}_E$),        volatility of assets has to increase dramatically in order to match both the new equity value and the value of volatility. The higher volatility of assets increases the probability of default.
- (b) To overcome the issue we can instead keep the volatility of assets constant. In this case we only need to solve for the value of assets. Same steps as above but we keep the volatility of assets equal to $σ^{10/10}_A= 0.1539$ and we ask the solver to change cell E5 only. In this case we obtain a much greater assets value where cv stands for "constant volatility".
$$V_{A_{c v}}^{10/14}=1,       760.89$$Using this value we can compute the default probability. We obtain $p^{10/14}_{1,       cv}= 3.5\%$ which is lower (as expected) than the one prevailing on Oct 10. The intuition,        as mentioned in point (a) is that now we are breaking the tight relationship between volatility of assets and volatility of equity.
- (c) The credit spread can be computed as
$$c s=-{\frac{1}{T}}\cdot l n\left[1-e^{r\cdot T}\cdot B S P\left({\frac{V_{0}}{F}},       r,       T,       \sigma\right)\right]$$
where BSP stands for "Black and Scholes Put". This comes from the fact that under the Merton model debt is a combination of a a bond and a short position in a put option. We can make the same assumptions made for computing the value of equity,        namely that the short term is paid immediately and that the strike price of the option ($F$ in the formula) is equal to the long term liabilities. Of course this implies that the value of the underlying $V_0$ is the value of the Residual Assets $V_{RA}^0$ computed above. Finally $σ$ is the volatility of assets $σ_A$.

Note that
$$B S P\left(\frac{V_{R A_{0}}}{F},       r,       T,       \sigma_{A}\right)=\frac{1}{F}\cdot B S P\left(V_{R A_{0}},       F,       r,       T,       \sigma_{A}\right)$$
and $BSP (V_{RA}^0*,        F,        r,        T,        σ_*A)$ is already provided in cell F13. We follow these steps for the three cases (Oct 10,        Oct 14 with varying assets volatility and Oct 14 with fixed assets volatility) yielding:
$$\begin{array}{ccc}\csc^{10/10}&=&3.12\%\\ \\[-3mm]\csc^{14/10}&=&4.42\%\\ \\[-3mm]\csc^{14/10}&=&2.56\%\\\end{array}$$
 
As expected from our calculation of the probability of default,        the credit spread increases if we let asset volatility vary. But when we constrain volatility we get a lower credit spread.

- (d) After the cash infusion the value of the assets increases by an amount equal to the cash infusion itself. We can compute the new value of the equity (still as a call option on firms assets). We finally compute the change (if any) in the market value of debt. In particular given the value of assets $V_A$ and the value of equity $V_E$ we compute the market value of debt as $V_D = V_A −V_E$. Do this before and after the cash infusion. The results are reported below:
	- $$\overline{\begin{array}{ccc}\hline&\text{Before}&\text{After}\\\hline V_E&76&89\\\hline V_A&1,       716&1,       741\\\hline V_D&1,       640&1,       652\\\hline\end{array}}$$
- Table 1: Values of Debt,        Equity and Assets before and after the cash injection

So we see that the value of Debt has actually increased by 12 billion. That is the transfer to bond holders.