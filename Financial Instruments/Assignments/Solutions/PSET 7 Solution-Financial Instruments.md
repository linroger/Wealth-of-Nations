---
linter-yaml-title-alias: 1. American Options
title: 1. American Options
tags:
  - american_option
  - binomial_tree
  - early_exercise
  - option_pricing
  - put_option
aliases:
  - American Options
  - Homework 7 Solution
key_concepts:
  - American call option
  - American put option
  - Early exercise value
  - Option payoff
  - Risk-neutral valuation
---

---

title: 1. American Options
aliases: [1. American Options]
linter-yaml-title-alias: 1. American Options
title: 1. American Options
aliases: [1. American Options]
linter-yaml-title-alias: 1. American Options
title: 1. American Options
aliases: [1. American Options]
linter-yaml-title-alias: 1. American Options
Financial Instruments Winter 2024 John Heaton
Solution to Homework 7

# 1. American Options

(a). Figure (l) shows the tree for the stock price implied by the parameters.
 ![500](https://storage.simpletex.cn/view/fz1nvxaUqXbGvy22Bibwd9SAvALG77gQD)
Figure l:Stock price tree
Let’s start with the call option. The first thing to remember is that at maturity,  $T=3$,  the American option payoff will be equivalent to the payoff of a European call option $max(S_{T}-K,       0)$. Given this,  we start working backward along the tree. For each node,  we compute the value to waiting and compare it to the value from early exercise. The value to waiting is just the discounted risk-neutral valuation of the option. In general,  if we are in the node $(I,       j)$ 1,  the value to waiting is
$$V_{I,       j}^{wait}=Z(I+1)\cdot[q^{*}\cdot V_{I+1,       j}+(1-q^{*})\cdot V_{I+1,       j+1}]$$
where $Z(I+1)$ is the value of a zero coupon bond maturing the next period and $q^{*}$ is the risk-neutral probability. Given the continuously compounded interest rate 7,  we can easily find that $Z(I+1)$ is equal to $Z(I+1)\:=\:e^{-r\cdot dt}$. In our case,  $T=0.02$ and $dt=1$,  so $Z(I+1)=0.98$. We also know that the risk-neutral probability $q^*$ is given by
$$q^*=\frac{e^{r\cdot dt}-d}{u-d}=\frac{1.02-0.91}{1.10-0.91}=0.58$$
Figure (2) shows the starting point for the tree needed to price the American call option.
 ![500](https://storage.simpletex.cn/view/f9VG1pgMYoz4BAnHl4nAN2Pg6mrXZGFuw)
Figure 2:Initial steps for American call tree
Before proceeding back to period $I=1$,  we compare the values to waiting (“wait” in the tree)with the values from early exercise. At each node,  the value from early exercise will be simply equal to
$$C_{I,       j}^{EE}=max(S_{I,       j}-K,       0)$$
where EE stands for Early Exercise. Figure (3) compares both values.
As you can see,  the value to waiting is always greater than the value to early exercise,  so we the option values at period $I=2$ will be equal to the values from waiting. We then keep going backward until we reach period $\dot{I}=0$. Figure 4 displays the result.
We apply the same procedure for the American put. Figure (5) shows the period $I=2$ comparison between values to waiting and values to early exercise.
 ![500](https://storage.simpletex.cn/view/fuyAl5Y7aBfkpLsBngFXyufIRiQiRmAGI)
Figure 3: Period $I=2$ comparison between $C^{wait}$ and $C^{EE}$
In this case,  we note that $P_{3,       3}^{wait}=15.38<P_{3,       3}^{EE}=17.36$,  therefore the option value in node (3,  3) will be equal to $P_{3,       3}=P_{3,       3}^{EE}=17.36$. Going back until period $I=0$,  we obtain the tree shown in Figure (6). Early exercise nodes are underlined.
(b). As pointed out before,  the put option is exercised before maturity at node (3,  3). This happens because the option is sufficiently in the money,  and the expected return from waiting is lower than the return from exercising early. The call is never exercised early. We already know it is never optimal to early exercise an American call option on a non-dividend-paying stock.
(c). The new tree for the American call is reported in Figure (7).
While Figure (8) reports the tree for the American put option. Again,  early exercise nodes are underlined.
In this case,  early exercise of the put is optimal twice,  namely at nodes (2,  2) and (3,  3). The reason is that when the stock price drops,  the benefit that we get from investing the strike price at the risk-free rate is greater when the risk-free rate is greater,  and this increases the benefits from early exercise. Note that at the same time,  as the interest rate goes up,  the value of the put goes down. More in detail,  the value of the European put goes down by
 ![500](https://storage.simpletex.cn/view/frG66yt9UADMNhtFy6m3tS8y3KO5DMp7C)
Figure 4: American call option tree
much more than the American put,  and this is due to the fact that the value from early exercise increases.
(d). When we have dividend payments,  the computation is a bit trickier. With a dividend,  we must worry about the drop in stock price that occurs as a consequence of a payment to shareholders. In other words,  dividends are the amounts of price drops. There are two ways to deal with this: change the stock price outcomes and fix the risk-neutral probabilities or change the stock price outcomes and fix the risk-neutral probabilities. The spreadsheet “HW7 Solution Question 1” provides details on both approaches. Here,  I outline how to do the calculation with a change in the stock price outcome.
Since we have a proportional dividend at every period,  to compute the tree for the stock price,  use the following steps:
(i). Start from the current stock price.
(ii) Compute the price change in the next node given the $2L$ and $d$ parameters. This will be referred to as a pre-dividend price.
(i). Compute the after-dividend price by subtracting the amount of the dividends (in this case,  multiplying the pre-dividend price times $(1-y_{1})$where $y1$ is the proportional
 ![500](https://storage.simpletex.cn/view/fIOuzPgpKaXNLKhnuZwmIvg62BDHkYgcW)
Figure 5: Period $I=3$ comparison between $P^{wait}$ and $PEE$
dividend paid at the end of each period).
(iv)Repeat steps (ii) and (iii) until the last period.
We therefore have two stock prices for each period. The optimal exercise will be different for calls and puts. For calls,  it may be optimal to exercise right before the dividend is paid,  while for puts,  it may be optimal to exercise right after dividend payment. We compute the call payoff and value from early exercise using the pre-dividend stock price,  while we compute the put payoff and value from early exercise of the after-dividend price. Figure (9) shows the stock price tree.
The amounts above the arrows are the pre-dividend prices (again,  used for calls),  and the amounts below the arrows are the after-dividend prices (used for puts).
We can now use the same procedure as above to compute the option prices,  again,  using the same risk-neutral probability computed in point (1.a),  that is,  $p^{*}=0.58$. Figure (10) shows the tree for the American call option. Early exercise nodes are underlined.
Figure (11) below shows the tree for the American put option.
Compared to the results from parts (1.a) and (1.c),  we see that the put is now more valuable,  while the call is less valuable. This is expected as the effect of the dividend is to lower the
 ![500](https://storage.simpletex.cn/view/ftnn2zSIDNkcZIRYhPKdu8gTZ5NvZyeEv)
Figure 6: American put option tree
stock price,  and the put becomes more valuable as the stock price goes down. If we compare the results only with part (1.c),  we see that with low interest rates and high dividends,  it is optimal to exercise early the American Call,  while with no dividends and high interest rates,  early exercise of the put is useful.
 ![500](https://storage.simpletex.cn/view/f5XtDXv4HgG0Eq6V2bzHR9pMzZVxPoD5X)
Figure 7: American call option tree when $r=0.05$
 ![500](https://storage.simpletex.cn/view/fnxI8deO5kbTL0ICKOD10IYHfQ7hAieDi)
Figure 8: American put option tree when $r=0.05$
 ![500](https://storage.simpletex.cn/view/fsgn8bnLRuZrVZ1oVmyLt5XxUCmWyzxZX)
Figure 9: Stock price tree with a proportional dividend equal to $y_{1}=0.05$
 ![500](https://storage.simpletex.cn/view/fwmi8DrXykkDYCmfaDUqGW55T6zGsCYGq)
Figure 10: American call option tree when $r=0.02$ and $y_{1}=0.05$
 ![500](https://storage.simpletex.cn/view/ftg4m15htYQe15tFY21nCeTkhgcLMbW6H)
Figure 1l: American put option tree when $T=0.02$ and $y_{1}=0.05$

# Part 2: Citigroup’s Default Probability during the Credit Crisis
-We can start by computing the number of shares using the market capitalization and the stock price on Feb 13,  2009. We get (in billions)
$$N=\frac{MCap}{S}=\frac{19.02}{3.49}=5.450$$
- To compute the value of assets and volatility of assets,  we follow the procedure described at the end of the directions. It is worth it though to quickly describe the theoretical framework that we follow. In a nutshell,  we solve a system of two equations in two unknowns. Since this system is a bit more complicated than the classical systems we have seen,  we need to use a solver.
What are the two equations and the two unknowns? We need to find the value of assets $V_{A}$ and the volatility of assets $0A$. These are our unknowns. What are the equations? The Merton Model says that we can consider the equity of a firm as a call option on its assets,  with a strike price equal to the face value of the debt. If we make reasonable assumptions and we assume that assets’ returns are log-normally distributed,  we can use the Black and Scholes formula to price the option. So we can already write
$$V_{E}=BSC$$
where $BSC$ means “Black-Scholes-Merton Call. This is one of our two equations.
What are the inputs that we need to apply the Black-Scholes (and Merton) formula? We need the value of the underlying ($V_{A}$),  the strike price (K),  the risk-free rate(r),  the annualized volatility of the returns of the underlying ($\sigma_{A}$),  and the maturity of the option (T). Sc $1^{2}$,  we can write
$$V_{E}=BSC\left(V_{A},       K,       r,       \sigma_{A},       T\right)$$
Indeed,  the two unknowns V_A and V_A appear in equation (2).
What is the second equation? The idea is that if equity is a call option on a firm’s assets,  then 2Note that I have not mentioned the dividend yield as in this case,  we can ignore it.
The volatility of equity (that is,  the volatility of the call) is related to the volatility of the underlying (that is,  the volatility of the assets) according to some determined equation. Under the assumptions above,  the volatility of equity is
$$\sigma_E=\left(\frac{V_A\cdot N(d_1)}{V_A\cdot N(d_1)-K\cdot e^{-r\cdot T}\cdot N(d_2)}\right)\cdot\sigma_A$$
which is our second equation.
Where do we get the other parameters? Some of them are easy to get (like $V_{E}$，that is,  the market capitalization,  orUE,  which can be computed using historical data),  but for some others,  we need to make assumptions.
For example,  what’s the strike price of the option? This should be “the face value of the Debt.” But the Debt is not a zero-coupon bond,  since it pays coupons! We just pick a value assuming that it is a zero-coupon bond. A similar reasoning is followed for the other parameters.
Let’s get back to the Citi case. We use the Excel file to compute both $V_{A}$ and $0A$. Let’s start with the inputs: for the strike price (cell B6),  what value do we use? We have information on deposits,  short-term debt,  long-term debt,  and other liabilities. The directions tell us to assume that the short-term debt is paid out immediately. Why so? Simply because we are making adjustments that will let equity resemble a call option as much as possible in the case of a bank. The idea is that with banks,  deposits and short-term debt will fee the bank when trouble approaches so that they will be repaid in full no matter what. For example,  these will be repaid by cash and other short-term securities on the balance sheet. What’s left? We still have long-term debt,  other liabilities,  and the equity. Equity is still a call option,  but it is a call option on a smaller firm; the underlying security for the option is the residual (after short-term debt has been paid) assets of the firm,  that we can denote by $V_{RA}$. We can still use our system of equations,  but we have to be careful with the parameters:
$$V_{E}=BSC\left(V_{RA},       K,       r,       \sigma_{RA},       T\right)\\=\left(\frac{V_{A}\cdot N(d_{1})}{V_{RA}\cdot N(d_{1})-K\cdot e^{-r\cdot T}\cdot N(d_{2})}\right)\cdot\sigma_{RA}$$
We assume that the volatility of assets remains the same after having paid the short-term debt,  so we can safely write $0\:RA=0\:A$. Now that we don’t have the short-term debt anymore,  it’s easier to think about Citi equity as an option. What’s the strike? We need to make an assumption. We can assume,  for instance,  that the residual debt (that is,  long-term debt + other liabilities) is a zero-coupon bond,  with face value equal to $K=LT+OL=791.79$. And the maturity? Let’s assume $T=7$. Below is a table showing how the results would have changed for different values of $TI$. What about the risk-free rate? We get it from the Excel file (I assume that it is annually compounded. Note that we have two interest rates,  one for each date,  that are $r_{1}^{10/10}=3.27\%$ and $r_{1}^{10/14}=3.48\%$). Same for the volatility of equity,  we have $\sigma_{E}^{10/10}=1.7551$ and $\sigma_{E}^{10/14}=1.8947$. We are now ready to use the solver. Here are the steps (for Oct 10 only. You can do the same for Oct 14 and check the results):
Continuously compounded risk-free rate: Cell B8 equal to $ln(1+0.0327)=0.0322$ — Dividend yield: Cell B9 equal to 0
 Call Price: this is the market value (that is,  the market capitalization) of equity. We get $MCap^{10/10}=S^{10/10}\cdot N=75.75$,  so Cell B10 equal to 75.75
Strike price: Cell B6 equal to 791.79. Maturity: Cell B7 equal to 7. —Vol Call: this is the volatility of the call option,  that is,  the volatility of equity. Cell B11 equal to 1.7551. Adj. Vol Call: this cell,  as explained,  allows us to adjust the formula for the volatility of assets. You need to plug the short-term debt (that is,  short-term borrowings + deposits). Cell B12 equal to 1,  132.617. Call the solver: (Excel 2003 shortcut ALT 十T,  V).
Setup the solver: Target Cell is B26 (simply write “TargetCall”). “By changing cells” write “S_2,  sig-2c“. Note: you don’t need to be an Excel genius to do this,  since everything was written in the cells highlighted in purple.
- Run the solver: press Enter.
We can read the results in cells E5 and E6. We find that the value of the residual assets is $V_{RA}^{10/10}=583.75$ and that the volatility of residual assets Va is the same by assumption as the volatility of assets) is
$$\sigma_{RA}^{10/10}=\sigma_{A}^{10/10}=0.1539$$
We need one last step,  that is,  computing the value of assets $V_{A}^{10/10}$. Since $V_{RA}=V_{A}-S-D$,  then
$$V_{A}^{10/10}=V_{RA}^{10/10}+S+D=583.75+1,       132.62=1,       716.37$$
Applying this same procedure for Oct 14,  2008,  we get
$$\sigma_{RA}^{10/14}=\sigma_{A}^{10/14}=0.2098$$
$$V_A^{10/14}=1,       692.51$$
-According to the KMV model,  the default probability in $T_{d}$ years (or expected default frequency)is given by
$$p_{T_d}=N\left(-d_2^d\right)$$
with $d_2^d$ being the distance to default defined as
$$d_2^d=\frac{ln\left(\frac{V_{A_0}}{F}\right)+\left(\mu-\frac{\sigma_A^2}{2}\right)\cdot T_d}{\sigma_A\cdot\sqrt{T_d}}$$
where $V_{A_{0}}$ is the value of assets,  $F$ is the default point,  $\mu$ is the expected risk-natural return of assets,  and $\sigma_{A}$ is the volatility of assets. We have computed $V_{A_{0}}$ and $\sigma_{A}$. In addition,  we know that according to KMV
$$F=STD+\frac{1}{2}\cdot LTD$$
We just need to make an assumption about $H$. It is reasonable to assume $\mu=0.15$ (same as the value used in the Teaching Notes for Enron). We can thus compute $d_{2}^d$ and $N\left(d_{2}^{d}\right)$ for both days. We find (I will simplify the notation taking out the $d$ superscript
$$\left\{\begin{array}{c}d_2^{10/10}=1.6509\\\\N\left(-d_2^{10/10}\right)=0.0494\end{array}\right.$$
and
$$\begin{cases}&d_2^{10/14}=1.096\\\\&N\left(-d_2^{10/14}\right)=0.1365\end{cases}$$
We are now ready to answer the questions:
(a). After the bailout,  on Oct 14,  the probability of default increases counterintuitively. Indeed,  we would expect the bailout to ensure markets that the institution will be safer. This is an issue with the Merton model: For given $UA$,  there is a very tight relation between equity value and volatility of equity. The bailout announcement made equity increase from 75 to 100 billion. According to the relationship assumed in the Merton model,  after the bailout announcement,  the volatility of equity should have declined substantially (as $V_{E}$ is inversely related to $0E$). Since the realized volatility of equity did not decrease (as $\sigma_{E}^{10/14}>\sigma_{E}^{10/10}$),  the volatility of assets has to increase dramatically in order to match both the new equity value and the value of volatility. The higher volatility of assets increases the probability of default.
(b). To overcome the issue,  we can instead keep the volatility of assets constant. In this case,  we only need to solve for the value of assets. Same steps as above,  but we keep the volatility of assets equal to $\sigma_{A}^{10/10}=0.1539$ and we ask the solver to change cell E5 only. In this case,  we obtain a much greater asset value
$$V_{A_{cv}}^{10/14}=1,       760.89$$
where $CU$ stands for “constant volatility”. Using this value,  we can compute the default probability. We obtain $p_{1,       cv}^{10/14}=3.5\%$ which is lower than expected than the one prevailing on Oct 10. The intuition,  as mentioned in point (a),  is that now we are breaking the tight relationship between volatility of assets and volatility of equity.
(c). The credit spread can be computed as
$$cs=-\frac{1}{T}\cdot ln\left[1-e^{r\cdot T}\cdot BSP\left(\frac{V_0}{F},       1,       r,       T,       \sigma\right)\right]$$
Where BSP stands for “Black and Scholes Put”. This comes from the fact that under the Merton model,  debt is a combination of a bond and a short position in a put option. We can make the same assumptions made for computing the value of equity,  namely that the short term is paid immediately and that the strike price of the option ($F$ in the formula is equal to the long-term liabilities. Of course,  this implies that the value of the underlying $V_{0}$ is the value of the Residual Assets $V_{RA_{0}}$ computed above. Finally,  $U$ is the volatility of assets $\sigma_{A}$.
Note that
$$BSP\left(\frac{V_{RA_0}}{F},       1,       r,       T,       \sigma_A\right)=\frac{1}{F}\cdot BSP\left(V_{RA_0},       F,       r,       T,       \sigma_A\right)$$
and $BSP\left(V_{RA_{0}},       F,       r,       T,       \sigma_{A}\right)$ is already provided in cell F13. We follow these steps for the three cases (Oct 10,  Oct 14 with varying assets volatility,  and Oct 14 with fixed assets volatility),  yielding
$$\begin{aligned}&cs^{10/10}&&=\quad3.12\%\\&cs^{14/10}&&=\quad4.42\%\\&cs_{cv}^{14/10}&&=\quad2.56\%\end{aligned}$$
As expected from our calculation of the probability of default,  the credit spread increases if we let asset volatility vary. But when we constrain volatility,  we get a lower credit spread.
(d). After the cash infusion,  the value of the assets increases by an amount equal to the cash infusion itself. We can compute the new value of the equity (still as a call option on firms’ assets). We finally compute the change (if any) in the market value of debt. In particular,  given the value of assets $V_{A}$ and the value of equity $V_{E}$,  we compute the market value of debt as $V_{D}=V_{A}-V_{E}$. Do this before and after the cash infusion. The results are reported below:

```latex
\begin{document}
\renewcommand{\arraystretch}{1.5}
\begin{tabular}{|c|c|c|}
\hline
 & \textbf{Before} & \textbf{After} \\ \hline
$V_E$ & 76 & 89 \\ \hline
$V_A$ & 1,      716 & 1,      741 \\ \hline
$V_D$ & 1,      640 & 1,      652 \\ \hline
\end{tabular}
\end{document}
```

Table 1: Values of Debt,  Equity,  and Assets before and after the cash injection
So we see that the value of Debt has actually increased by 12 billion. That is the transfer to bondholders.(^\n)|(^[-]+\n\n)