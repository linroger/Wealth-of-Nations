---
tags:
  - expectations_hypothesis
  - forward_rates
  - interest_rates
  - risk_premia
  - term_structure
aliases:
  - Interest Rate Structure
  - Term Structure
  - Yield Curve
key_concepts:
  - Expectations hypothesis
  - Forward rates calculation
  - Term structure decomposition
  - Term structure of rates
  - Time-varying risk premia
---

Teaching Notes
### Understanding the Term Structure of Interest Rates
John Heaton
The University of Chicago Booth School of Business NBER
## Introduction
- There are numerous questions that arise when we think about the term structure of interest rates, such as:
1. Why does the term structure of interest rates tend to slope upwards?
2. What is the risk involved in investing in Treasury securities? 3. Can we predict medium-to-long term yields? What about returns?
### The Expectations Hypothesis
 - The [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] is the hypothesis that long-term yields just reflect market participants' expectation of future interest rates
Long-term yield = Expected future short-term rates
- To illustrate, let today be $t$ and consider the case in which investors have perfect foresight of the next 1-year interest rates $y_{t+1}(1)$
 - Investors then also know that the zero coupon bond price next year will be
$$Z_{t+1}(1)=e^{-y_{t+1}(1)\times1}$$
- Because under these assumptions, $Z_{t+1}(1)$ is known today, its value today is the discounted value using the current l-year yield:
$$Z_t(2)=Z_t(1)\times Z_{t+1}(1)=e^{-(y_t(1)+y_{t+1}(1))}$$
 - Because the two-year yield also satisfies $Z_t(2)=e^{-y_t(2)\times2}$ , we obtain that under perfect foresight
$$\begin{aligned}y_t(2)=\frac{1}{2}(y_t(1)+y_{t+1}(1))\end{aligned}$$
## The Expectations Hypothesis (cntd.)
- Extending this reasoning to $n$ future one-year yields, then under perfect foresight the yield of a zero-coupon bond with $n+1$ years to maturity is:
$$)=\text{Average}[y_t(1),y_{t+1}(1),...,y_{t+n}(1)]=\frac{1}{n+1}\sum_{i=0}^{n}$$
- The [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] substitutes the perfect foresight with forecasts:
Erates The long
$$\begin{aligned}&term\:yield\:=\:forecasted\:average\:path\:of\:f\\&y_{t}(n+1)\:=\:E_{t}\left[\frac{1}{n+1}\sum_{i=0}^{n}y_{t+i}(1)\right]\end{aligned}$$
- Subtracting the curent l-year yield, we can also write
$$y_t(n+1)-y_t(1)\:=\:E_t\left[\frac{1}{n+1}\sum\limits_{i=0}^ny_{t+i}(1)\right]-y_t(1)$$
### Preliminary Heuristic Evidence
- Does this relation holds in the data?
- Heuristically, next figure plots the expected future three-month rates from the Survey of Professional Forecasters from 1981 to 2015.
- The forecasts are for the three-month T-bill rate for the current quarter, denote in the figure by $r(t)$ , and for the next three quarters, denoted by $r(t+3m)$ $r(t+6m)$ , and $r(t+9m)$ , respectively.
 ![500](https://storage.simpletex.cn/view/fgx5Hn5nWPvtwr3lh0qL5wdVGWt0Cmx3c)
 - Next figure shows the 1-year term spread, defined as $y_t(1y)-r(t)$ together with the 1-year "expectation spread".
 ![500](https://storage.simpletex.cn/view/fkvnDeNEaUry3cHhon4BOiKtlkg4Dwu4l)
- The 1-year term spread is greater than the "expectation spread" most of the time. $-\Longrightarrow$ the expectation hypothesis does not hold (at least, using survey forecasts).
## The Expectation Hypothesis and Forward Rates
- We saw in Teaching Notes 1 that a forward rate at $t$ for an investment between $\tau_{1}$ and $\tau_{2}$ can be written as
$$\tau_{2})=\frac{1}{\tau_{2}-\tau_{1}}\operatorname{ln}\left(\frac{Z_{t}(\tau_{1})}{Z_{t}(\tau_{2})}\right)=\frac{1}{\tau_{2}-\tau_{1}}\left(y_{t}(\tau_{2})\tau_{2}-y_{t}(\tau_{2})\right)$$
- Consider a sequence of maturities $\tau_{i}=\tau_{i-1}+\Delta t$ , for $i=2,...,n$ . We have
$$\begin{aligned}f_{t}(\tau_{1},\tau_{2})&=\:\frac{1}{\Delta t}\left(y_{t}(\tau_{2})\tau_{2}-y_{t}(\tau_{1})\tau_{1}\right)\\f_{t}(\tau_{2},\tau_{3})&=\:\frac{1}{\Delta t}\left(y_{t}(\tau_{3})\tau_{3}-y_{t}(\tau_{2})\tau_{2}\right)\\f_{t}(\tau_{n-2},\tau_{n-1})&=\:\frac{1}{\Delta t}\left(y_{t}(\tau_{n-1})\tau_{n-1}-y_{t}(\tau_{n-2})\tau_{n-2}\right)\\f_{t}(\tau_{n-1},\tau_{n})&=\:\frac{1}{\Delta t}\left(y_{t}(\tau_{n})\tau_{n}-y_{t}(\tau_{n-1})\tau_{n-1}\right)\end{aligned}$$
## The Expectation Hypothesis and Forward Rates (cntd.)
- Summing over all of the forward rates, we find
$$\sum\limits_{i=2}^nf_t(\tau_{i-1},\tau_i)=\frac{1}{\Delta t}\left(y_t(\tau_n)\tau_n-y_t(\tau_1)\tau_1\right)$$
- Assuming $\tau_{1}=\Delta t$ and defining $f_{t}(0,\Delta t)=y_{t}(\Delta t)$ , we the obtain
$$y_t(\tau_n)=\frac{\Delta t}{\tau_n}\sum\limits_{i=1}^nf_t(\tau_{i-1},\tau_i)=\text{Average forward rate}$$
- The expectation hypothesis then implies that for every $i$ the forward rate is equal to the expected future short-term rate:2
$$f_t(\tau_i,\tau_i+\Delta t)=E_t[y_{t+\tau_i}(\Delta t)]\:.$$
 ![500](https://storage.simpletex.cn/view/fhFQITh8oGy5GrnI7qBnR0gmm4N0nb9Gk)
- Again, expected future rates are mostly lower than forward rates.
### Time Varying Risk Premia
- The violation of the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] (and the time variation in spread) suggests the existence of an additional term in Equation (1):
$$y_t(n+1)\:=\:E_t\left[\frac{1}{n+1}\sum\limits_{i=0}^ny_{t+i}(1)\right]+RP_t$$
·where $RP_{t}$ reflects a risk premium from holding the bond from $t$ to $t+1$
- The time variation in $RP_{t}$ invalidates the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]].
- Even if the expectation of future interest rates does not change, the yield curve may change because $RP_{t}$ changes. - Therefore, movements in the yield curve do not only correspond to variations in expected future short-term yields.
### Term Structure Decomposition
·Let $y_{t}(n+1)=$ yield at $t$ of a bond with time to maturity $(n+1)$ years from $t$
$$Z_t(n+1)=e^{-y_t(n+1)(n+1)}$$
- The value of this bond next year will then be
$$Z_{t+1}(n)=e^{-y_{t+1}(n)\times n}$$
- The yield next year $y_{t+1}(n)$ is not known. Assume it normally distributed
$$y_{t+1}(n)\sim\mathcal{N}\left(\overline{y},V\right))\quad\text{with}\quad\overline{y}=E[y_{t+1}(n)]$$
- $Z_{t+1}(n)$ is risky and so investors at $t$ may require an additional discount $RP$ :
$$Z_t(n+1)=e^{-(y_t(1)+RP_t)\times1}E_t[Z_{t+1}(n)]$$
- Using the properties of the normal distribution, 3 we then obtain
$$E_t[Z_{t+1}(n)]=e^{-\overline{y}\times n+\frac{(n)^2}{2}V}$$
## Term Structure Decomposition (cntd.)
 - Using (6) and (7) we then obtain
$$\begin{aligned}
&y_{t}\left(n+1\right) =\:\frac{1}{n+1}\times y_{t}\left(1\right)+\frac{n}{n+1}\times E_{t}\left[y_{t+1}\left(r\right.\right. \\
&+\frac{RP}{n+1} \\
&-\frac{n^2}{2(n+1)}V_t
\end{aligned}$$
(Expected future yield) (Risk premium) (Convexity)
- The current long-term yield $y_{t}(n+1)$ depends on
1. The weighted average between the current short-term yield and the expected long-term yield next year.
2. A risk premium RP that market participants require to hold long-term zero coupon bonds with maturity $n+1$ over safe bonds with maturity 1.
3. A convexity term due to the nonlinear relation that exists between the yield $y_{t+1}(n)$ and the price $Z_{t+1}(n)=e^{-y_{t+1}(n)\times n}$
## Expectation Hypothesis (again)
·Let $RP_{t}=\frac{n^{2}}{2}V_{t}$ . Then the expectation hypothesis holds:
$$y_t\left(n+1\right)\:=\:\frac{1}{n+1}\times y_t\left(1\right)+\frac{n}{n+1}\times E_t\left[y_{t+1}\left(\right.\right]$$
- Subtract $y_{t}\left(n+1\right)\times\left(n\right)/\left(n+1\right)$ on both sides, to get
$$E_t\left[y_{t+1}\left(n\right)\right]-y_t\left(n+1\right)\:=\quad\frac{1}{n}[y_t\left(n+1\right)-y_t$$
 ![500](https://storage.simpletex.cn/view/fsuOQuTk7VbQ72z9qcAyWof3Cc0he0XK1)
- A steep term structure (on the RHS) signals the market expects an increase in the yield $y_{t}\left(n+1\right)$ between $t$ and $t+1$ (on the LHS)
$$E_t\left[y_{t+1}\left(n\right)\right]>y_t\left(n+1\right)$$
$-\Longrightarrow$ market expects a low or negative return on $(n+1)$ maturity bond.
### Long-Term Yield Increase
 ![500](https://storage.simpletex.cn/view/fAde6YhyhNm9rAenbl5TAZNrU5fkCwuN7)
- Example: On $t=1/31/1994$ yield curve was increasing and the spread was $3.3\%$
- High spread may signal long-term yield $y_t(30)=6.87\%$ may increase.
- And indeed, it did: $t+1=1/31/1995$ we have $y_{t+1}(29)=7.81\%$
·This implies a loss on investment:
$$R_{t,t+1}=\frac{Z_{t+1}(29)}{Z_t(30)}-1=\frac{10.3893}{12.7048}-1=-18\%$$
### Does the Expectation Hypothesis Hold in the Data?
 - Does a high slope predict an increase in future yields? (i.e. should you go short?) $\bullet$ In an influential paper, Campbell and Shiller (1988) run the following regressions
$$\text{Changes in yield}=\alpha+\beta\times\text{Slope}_t+\varepsilon_{t+1}$$
- That is, from yield data we can compute a dependent $“Y”$ variable
$$Y_{t}=\mathrm{Changes~in~yield}=y_{t+1}\left(n\right)-y_{t}\left(n+1\right);\quad t=$$
T =1,2,.., T
- and an explanatory ‘ $‘X”$ variable
$$X_t=\mathsf{Slope}_t=\frac{1}{n}\left[y_t\left(n+1\right)-y_t\left(1\right)\right];\quad t=1,2,.$$
 - Then Campbell and Shiller (1988) run the regression
$$Y_t=\alpha+\beta X_t+\varepsilon_{t+1}$$
 - The [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] has $\alpha=0$ and $\beta=1$
 - We can see if this true in the data.
## Campbell and Shiller Regression
Test of the Expectation Hypothesis
<table>
	<tbody>
		<tr>
			<th>Maturity $m$</th>
			<th>$\alpha$</th>
			<th>$Se$ $\alpha$</th>
			<th>$U$ $\beta$</th>
			<th>$\beta$ $Se$</th>
			<th>$R^{2}$</th>
		</tr>
		<tr>
			<td>2</td>
			<td>-0.01</td>
			<td>0.27</td>
			<td>-0.83</td>
			<td>0.52</td>
			<td>0.03</td>
		</tr>
		<tr>
			<td>3</td>
			<td>0.09</td>
			<td>0.24</td>
			<td>-1.23</td>
			<td>0.62</td>
			<td>0.05</td>
		</tr>
		<tr>
			<td>4</td>
			<td>0.16</td>
			<td>0.21</td>
			<td>-1.59</td>
			<td>0.70</td>
			<td>0.07</td>
		</tr>
		<tr>
			<td>5</td>
			<td>0.17</td>
			<td>0.21</td>
			<td>-1.56</td>
			<td>0.76</td>
			<td>0.06</td>
		</tr>
	</tbody>
</table>
Notes: Regression results based on Fama Bliss discount bond data from CRSP. Sample: 1964 - 2006.
- Important to note:
-β ≠ 1 => Expectations Hypothesis is rejected $-\beta<0\Longrightarrow$ steep yield curve predicts a decrease of long-term yield. * This is the opposite of the basic simple intuition about a raising yield curve.
 - Bottom line: A steep yield curve predicts high returns of long-term bonds.
### Long-Term Yield Decrease
 ![500](https://storage.simpletex.cn/view/fyAdfFwbyqr7G0Q4tZoAzOvgVwx5mFzZW)
·Example: On $t=1/30/2004$ yield curve was increasing and the spread was $4.1\%$
 - In the data, high spread forecast a decline of long-term yield $y_{t}(30)=5.347\%$ - And indeed, it did: $t+1=1/31/2005$ wehave $y_{t+1}(29)=4.655\%$ This implies a gain on investment:
$$R_{t,t+1}=\frac{Z_{t+1}(29)}{Z_t(30)}-1=\frac{25.9279}{20.1046}-1=+29\%$$
### Time Varying Risk Premia
 - This result implies that the slope of the term structure predicts
$$LRP_t=RP_t-\frac{n^2}{2}V_t,$$
- $LRP_{t}$ stands for "Log Risk Premium" (see below).
$\bullet$ In fact, we can rewrite (8) as
$$_{t}\left[y_{t+1}\left (n\right)-y_{t}\left (n+1\right)\right]=\frac{1}{n}\left[y_{t}\left (n+1\right)-y_{t}\left (1\right)\right]-$$
 - We know slope is not positively related to the left-hand-side (previous table) $\Longrightarrow$ then it must be positively correlated with $LRP_{t}$
- When slope increases so does $LRP_{t}$ , thereby killing the positive correlation. Implication:
- High slope $\not\Rightarrow$ market expects higher future rates. -High slope $\Rightarrow$ high risk premium $\Rightarrow$ high expected return of long-term bonds $\Rightarrow$ strong price increase $\Rightarrow$ low future yield.
## The Predictability of Bond Returns
- The Log Risk Premium $LRP_{t}$ can also be rewritten as:4
$$LRP_t=E_t\left[\log\left (\frac{Z_{t+1}\left (n\right)}{Z_t\left (n+1\right)}\right)-\log\left (\frac{1}{Z_t\left (1\right)}\right)\right]$$
- The expectation hypothesis implies $LRP_{t}=0$
- To test for this hypothesis, denote the Log Excess Return $(LER)$ from holding a long-term zero coupon bond over the short term bond by
$$LER_t=\log\left (\frac{Z_{t+1}\left (n\right)}{Z_t\left (n+1\right)}\right)-\log\left (\frac{1}{Z_t\left (1\right)}\right)$$
. $LER_{t}$ is the ex-post realized empirical counterpart of $LRP_{t}$
$$LRP_t=E_t[LER_t]$$
## Fama Bliss Regressions
 - Fama and Bliss (1987) then run the following regression
$$LER_t=\alpha+\beta\left[f_t (n, n+1)-y_t (1)\right]+\varepsilon (t)$$
- The expectation hypothesis has $LRP_{t}=0$ , and therefore $\alpha=\beta=0$
<table>
	<tbody>
		<tr>
			<th>Maturity $m$</th>
			<th>$\alpha$</th>
			<th>$Se$ $\alpha$</th>
			<th>$\beta$</th>
			<th>$\delta$ $se$</th>
			<th>$R^{2}$</th>
		</tr>
		<tr>
			<td>2</td>
			<td>-0.01</td>
			<td>0.27</td>
			<td>0.92</td>
			<td>0.26</td>
			<td>0.14</td>
		</tr>
		<tr>
			<td>3</td>
			<td>-0.19</td>
			<td>0.49</td>
			<td>1.22</td>
			<td>0.34</td>
			<td>0.15</td>
		</tr>
		<tr>
			<td>4</td>
			<td>-0.43</td>
			<td>0.69</td>
			<td>1.43</td>
			<td>0.44</td>
			<td>0.16</td>
		</tr>
		<tr>
			<td>5</td>
			<td>-0.16</td>
			<td>0.93</td>
			<td>1.11</td>
			<td>0.51</td>
			<td>0.07</td>
		</tr>
	</tbody>
</table>
- $\beta$ is significantly different from zero, and indeed positive.
 - This finding, again, shows that the excess log return is in fact predictable:
- When the forward spread is strongly positive, on average investments in long- term bonds generate a higher return compared to short term bonds.
## Cochrane and Piazzesi Factor
- Cochrane and Piazzesi (2005) have shown that a specific combination of forward rates successfully predicts excess log returns.
 - The predicting factor is defined by
$$x_t=\gamma_0+\gamma_1 y_t (1)+\gamma_3 f_t (2,3)+\gamma_5 f_t (4,5)$$
·The parameters $\gamma_{i}$ are estimated in a first stage regression:
- Define
$$\overline{LER}_t=0.25\times\sum\limits_{n=2}^5 LER_t (n)$$
- Then, estimate $\gamma_{i}$ 's with:
$$\overline{LER}_t=\gamma_0+\gamma_1 y_t (1)+\gamma_3 f_t (2,3)+\gamma_4 f_t (4,5))+$$
- The estimates for 1964 - 2006 sample are $\widehat{\gamma}_{0}=-3.26$ ， $\widehat{\gamma}_{1}=-1.87$ ,， $\widehat{\gamma}_{3}=3.94$ and $\widehat{\gamma}_{5}=-1.64$
## Cochrane and Piazzesi Regression
- Cochrane and Piazzesi (2005) run the regression
$$LER_t (n)=\alpha+\beta\times x_t+\varepsilon_t$$
Panel C: Log Excess Return Prediction from Cochrane Piazzesi Factor R 2 Maturity n β se (β)
<table>
	<tbody>
		<tr>
			<td>2</td>
			<td>0.47</td>
			<td>0.07</td>
			<td>0.30</td>
		</tr>
		<tr>
			<td>3</td>
			<td>0.88</td>
			<td>0.13</td>
			<td>0.33</td>
		</tr>
		<tr>
			<td>4</td>
			<td>1.22</td>
			<td>0.19</td>
			<td>0.35</td>
		</tr>
		<tr>
			<td>5</td>
			<td>1.43</td>
			<td>0.24</td>
			<td>0.32</td>
		</tr>
	</tbody>
</table>
 - The coefficients are strongly positive, and the $R^{2}$ higher than in Panel B, showing that including information on the whole term structure helps predict bond excess returns.
## Coping with Inflation Risk: Treasury Inflation-Protected Securities
- Treasury coupon bonds are in nominal terms, as they pay in dollars.
 - How much you can buy with those dollars depends on inflation before maturity.
- Over long periods, the inflation can be pretty high.
·CPI index = weighted average of the representative good prices.
 - The change in the CPl measures the realized inflation during the period.
## Simple Example
- We have monthly income of $\$10$ , 000 and let $\mathsf{CPI}=$ price of consumption basket.
- How much we can buy at a given time $t_1$ is $C (t_{1})=\$10,000/\mathsf{CPI}(t_{1}).$ -E.g. if CPI $(t_1)=10\Longrightarrow$ we can buy 1000 units of consumption basket. -If basket only contains $\$10$ -burgers, we can buy $C (t_1)=1000$ burgers at $t_1$
- Let now be $t_2$ and let our income be the same. Because of inflation, now CPI $(t_2)=$ 20.
- We can now only buy $C ( t_2)$ = $\$ 10, 000/$ СРI $( t_2)$ = 500 (t 2) = 500 $(t_2)=500$ burgers: big loss in consumption even if nominal income is the same.
### Inflation Risk and the Loss of Purchasing Power
- The ratio $C (t_2)/C (t_1)=$ loss in purchasing power of a dollar between $t_1$ and $t_2$
- This ratio is given by $C (t_2)/C (t_1)=$ СРI $(t_1)/$ СРI $(t_2).$
- In the previous example $\mathsf{CPI}(t_1)/\mathsf{CPI}(t_2)=0.5\Longrightarrow$ we can only afford at $t_2$ half of the goods we could buy at $t_1$
- Changes in CPl are unknown $\Longrightarrow$ nominal securities have infation risk - Risk that the dollar payoff will afford less consumption goods than expected.
 - Inflation-protected securities are vehicles that hedge against this inflation risk.
## Treasury Inflation Protected Securities (TIPS)
 - TIPS are coupon bonds issued with maturities of 5, 10, and 20 years.
- The coupon rate of TIPS is a constant fraction of the principal.
- The principal changes over time in response to inflation.
- If the CPl increases, then the principal amount increases proportionally.
 - The Treasury publishes Index ratios
$$\text{Index ratio}(t)\:=\:\max\left (\frac{\text{Reference CPI}(t)}{\text{CPI}(\text{issurance})}, 0\right)$$
Reference CPI $( t)$ = $w ( t)$ (t) = w (t) $(t)~=~w (t)~\mathsf{CPI}(t-1)+(1-w (t))~\mathsf{CPI}(t-2)$
-where $w (t)$ is a weight that depends on the quoted day of the month.
 - Next Table contains quotes of Treasury securities on November 26, 2007. - Given the index ratio, the next coupon payment is
Coupon paymet $(t)=\frac{\text{Соupon rate}}2\times 100\times$ Index raio (t)
## Treasury Securities on November 26, 2007
### Panel A: Treasury Bills
ASK BID Coupon Maturity
3.512/20/20073.5432/21/20083.053.235/22/20083.24
Panel B: Nominal Treasury Notes and Bonds
BID ASK CouponMaturity
35/8 10/31/2009 101.25 101.25
4 1/2 5/15/2010 103.75 103.78133 7/8 10/31/2012 102.7188 102.71884 1/4 11/15/2017 103.1563 103.156355/15/2037 111.7813 111.8438
Panel C: TIPS
<table>
	<tbody>
		<tr>
			<th>Coupon</th>
			<th>Maturity</th>
			<th>BID</th>
			<th>$ASK$</th>
			<th>lssue Date</th>
			<th>Price lssue</th>
			<th>First Coupon</th>
			<th>Reference $CPI$</th>
			<th>$CPI$</th>
			<th>lndex Ratio</th>
		</tr>
		<tr>
			<td>2</td>
			<td>./15/2012 4/</td>
			<td>104.2188</td>
			<td>104.2813</td>
			<td>/30/2007 4/</td>
			<td>102.667</td>
			<td>10/15/2007</td>
			<td>202.9214</td>
			<td>208.3945</td>
			<td>1.02697</td>
		</tr>
		<tr>
			<td>5/8 25       </td>
			<td>7/15/2017</td>
			<td>110.125</td>
			<td>110.2188</td>
			<td>7/16/2007</td>
			<td>102.722</td>
			<td>1/15/2008</td>
			<td>207.2564</td>
			<td>208.3945</td>
			<td>1.00549</td>
		</tr>
		<tr>
			<td>23/8   </td>
			<td>1/15/2027</td>
			<td>109.5313</td>
			<td>109.7188</td>
			<td>1/31 /2007</td>
			<td>99.57</td>
			<td>7/15/2007</td>
			<td>201.6645</td>
			<td>208.3945</td>
			<td>1.03337</td>
		</tr>
		<tr>
			<td>33/8</td>
			<td>4/15/2032</td>
			<td>133.4063</td>
			<td>133.625</td>
			<td>10/15/2001 1</td>
			<td>98.314</td>
			<td>4/15/2002</td>
			<td>177.5</td>
			<td>208.3945</td>
			<td>1.17405</td>
		</tr>
	</tbody>
</table>
Data Source: Bloomberg, Inc.
## Reference Index Example
·The quotes in the Table are for November 26, 2007.
- The CPl used to compute the index ratio is not the November CPl.
- CPl values are released by BLS during the third week of the following month.
- CPl used is instead the average between the August and September CPls (207.917 and 208.490, respectively).
- Because November 26 is 25 days after November 1, the calculation is
$$\mathsf{CPI}(t)=\frac{5}{30}\times 207.917+\frac{25}{30}\times 208.490=208.39$$
 - An investor in TIPS is still subject to a small inflation risk during the two months between the CPl measure and the actual payment.
### Real Bonds and the Real Term Structure of Interest Rates
- Borrowing and lending do not need dollars.
- You can borrow a car from a friend and return it in a week. - If you forget your wallet, you can ask your friend to buy a sandwich today with the agreement you will return the same sandwich tomorrow. * If your "friend" see you very hungry today, he may ask you to return a bigger sandwich tomorrow. I.e. charge a big real interest rate.
- Real bonds are bonds that are denominated in units of a good instead of dollars.
- Relevant to inflation linked securities are bonds that are denominated in units of the consumption basket that underlies the CPl index calculation.
- A real discount factor $Z^{real}(t; T)$ defines the ecchange rate between consumption goods at $t$ versus consumption goods at a later date $T$
- How “"bigger" a sandwich are we willing to give back to the “friend" tomorrow to have a sandwich today?
## Real Rates
- From real discounts $Z^{real}(t; T)$ compute the real rate as usual:
$$Z^{real}(t; T)=e^{-r_{real}(t; T)(T-t)}\times 1$$
 Implies
$$r_{real}(t; T)=-\frac{\ln\left (Z^{real}(t; T)\right)}{T-t}$$
- The real term structure of interest rates is $r_{real}(t; T)$ for maturities $T$
- The value (in consumption goods) of a real coupon bond with maturity $TT$ and coupon rate $c$ is
$$P_{c}^{real}(t; T)=\frac{c\times 100}{2}\sum_{i=1}^{n}Z^{real}(t; T_{i})+100\times Z^{real}(t; T)$$
### Real Bonds and TIPS
- Suppose an investment bank purchases a TIPS and strips the coupons from principal, generating a series of zero coupon bonds.
- These zero coupon bonds pay an amount that is tied to the CPl.
- Denoting by $Idx (T)$ the CPl adjustment for maturity $T$ (recall, it depends on the CPl two months earlier), the payoff of a zero coupon TIPS is as follows:
$$\text{Zero coupon TIP payoff at T}=\frac{Idx (T)}{Idx (0)}$$
. $Idx (T)/Idx (0)=$ increase in the consumption basket price between 0 and $T$
 - For simplicity, assume
$Idx (T)=$ CPI $(T)=\$$ price of one unit of consumption basket
- Given $Z^{real}(t; T)$ , the value at $t$ of a security paying $Idx (T)$ (i.e. the amount need to purchase one unit of consumption basket) is
Present value of $Idx (T)=$ PV of one unit of consumption $=Z^{real}(t; T)$
## Real Bonds and TIPS (cntd)
 - This present value though is expressed in terms of units of the consumption basket $(Z^{real}(t,; T)$ is an exchange rate of consumption at $t$ for consumption at $T$ ).
- We can convert this value to dollars by multiplying it by the current price of the consumption basket $Idx (t)$ . We then obtain
$$Idx (T)=Z^{real}(t; T)\times Idx (t)$$
Dollar present value of
 - Finally, to obtain the payoff of the zero-coupon TIPS we must divide by $Idx (0)$
Dollar value of a zero-coupon (22)
$$\textsf{Dollar value of a zero-coupon TIPS}=Z^{TIPS}(t; T)=Z^{real}(t; T){\times}\frac{Idx (t)}{Idx (0)}$$
 - Given the value of zero-coupon TIPS, we can value coupon bearing TIPS.
- Therefore, a TIPS value at $t$ , with maturity $T$ , and coupon rate $C$ is given by
$$P_{c}^{TIPS}(t; T)=\frac{Idx (t)}{Idx (0)}\times\left[\frac{c\times 100}{2}\sum_{i=1}^{n}Z^{real}(t; T_{i})+Z^{real}(t; T)\right]$$
### Fitting the Real Yield Curve
- Clearly, zero-coupon real bonds $Z^{real}(t; T_i)$ are not observable, but they are embedded in the prices of TIPS.
- We can use the price of TIPS to "“back out" the discount factors $Z^{real}(t; T_i)$
- One limitation compared to the case of Treasuries is that we do not have available as many bond prices, and therefore the bootstrapping strategy is not applicable.
 - However, we can use the curve fitting method using a flexible function for the discount factor, such as the Nelson Siegel model
$$r_{real}(0, T)=\theta_0+(\theta_1+\theta_2)\:\frac{1-e^{-\frac{T}{\kappa_1}}}{\frac{T}{\kappa_1}}-\theta_2 e^{-\frac{T}{\kappa_1}}+\theta_3\left (\frac{1-e^{-\frac{T}{\kappa_1}}}{\frac{T}{\kappa_2}}-e^{-\frac{T}{\kappa_2}}\right)$$
- - From the previous table, for instance, we obtain the following results
## Real and Nominal Rates on November 26, 2007
 ![500](https://storage.simpletex.cn/view/fypETZuLDxNx3tG2uWMLcQh5EQLcuVBVB)
Data Source: Bloomberg.
- Next figure shows that the term structure of real rates changes over time.
Real Rates during and after the crisis
 ![500](https://storage.simpletex.cn/view/fIwc9ZuxNM3tOaDfk18pnx6f0O84atMQn)
Data are from Gurkaynak, Sack, and Wright (2010), updated series
- Negative real rates are not uncommon.
- We give back our "friend" a smaller sandwich because its price skyrocketed.
##  Nominal and Real Interest Rates
- What is the relation between real and nominal rates?
- We now show that
Nominal rate = real rate + expected inflation + inflation risk premium — convexity
 - Consider first the value today of $\$1$ at T
$$Z (0, T)=e^{-r (0, T) T}\times\$1$$
 - Alternatively, we can express this in "consumption goods":
\$1 at $T$ will buy $C (T)=\frac{\$1}{\mathsf{CPI}(T)}$ unis of consumption godl
 - Unfortunately, this amount is not known today, because CPI $(T)$ is stochastic.
- To compute the present value we need more assumptions.
$\bullet$ Let $\pi$ be the annualized inflation rate between O and $T$
$$\pi=\frac{1}{T}\ln\left (\frac{\mathsf{CPI}(T)}{\mathsf{CPI}(0)}\right)$$
## The Fisher Equation under Perfect Foresight
- Consider first Perfect Foresight: Assume investors know $\pi$ and hence CPI $(T)$
- Then the value today of $\$1$ at $T$ in consumption good units is
Present value of
$$C (T)=Z^{real}(0, T)\times C (T)=Z^{real}(0, T)\times\frac{\$1}{\mathsf{CPI}(\mathsf{T})}$$
 - To obtain the dollar value, we multiply this by the price of consumption good
$$C (T)=\mathsf{CPI}(0)\left (Z^{real}(0, T)\times\frac{\$1}{\mathsf{CPI}(T)}\right)$$
Dollar present value of
- The RHS is the $ value of the quantity of consumption purchased by $\Phi 1$ at $T$
- It is therefore a nominal discount, yielding the equality
$$Z (0, T)=Z^{real}(0, T)\times\frac{\mathsf{CPI}(0)}{\mathsf{CPI}(T)}$$
 - Substitute to obtain the Fisher equation:
$$r (0, T)=r_{real}(0, T)+\pi $$
## Inflation Risk Premium
 - Assume now inflation rate is not known and assume it is log-normal 5
$$\log\left (\frac{\mathsf{CPI}(T)}{\mathsf{CPI}(0)}\right)=x\sim\mathcal{N}(\overline{\pi}\: T,\sigma\pi^2\:T)$$
 - This implies that the amount of consumption we can buy at $T$ is stochastic:
$$C (T)=\frac{\$1}{\mathsf{CPI}(T)}=\$1\times\frac{e^{-x}}{\mathsf{CPI}(0)}$$
. Because $C (T)$ is now risky, we cannot discount it to today using the real bond $Z^{real}(0, T)=e^{-r_{real}(0, T) T}$ , but we thus must add a risk premium $k$
 - Multiplying also by $\mathsf{CPI}(0)$ to obtain the dollar value, we obtain
Dollar Present value of expected
$$\begin{array}{rcl}{\text{I}C (T)}&{=}& {{e^{-(r_{real}(0,T)+\kappa)T}\times E[e^{-x}]}} \\&{=}& {{e^{-(r_{real}(0,T)+\kappa)T}\times e^{-\overline{\pi}T+\frac{1}{2}\sigma\pi^{2}T}} }\end{array}$$
- This is dollar present value of \$ 1 at $T$ . Therefore it equals $Z (0, T)=e^{-r (0, T) T}$
$$r (0, T)=r_{real}(0, T)+\overline{\pi}+\kappa-\frac{1}{2}\sigma\pi^2$$
## The Economics of Fixed Income Investments
- We now link all this to economic growth and agents' decisions.
- We assume that investors have a utility function $U (C (t), t)$ . This is:
- Decreasing with time: Eating soon is better than eating later. - Increasing in consumption: Eating more is better than eating less. - Concave: $\Longrightarrow$ Risk aversion: An amount of consumption that is certain is better than a fair bet to have more or less.
$$E\left[U (C)\right]<U\left (E[C]\right)$$
- A widely used utility function is the Constant Relative Risk Aversion (CRRA):
$$U (C, t)=e^{-\rho t}\frac{C^{1-\gamma}}{1-\gamma}$$
$-\rho=$ time-preference parameter
$-\gamma=-CU^{\prime\prime}(C)/U^{\prime}(C)=$ relative risk aversion parameter.
## Optimal Savings
- An investor has wage $w (0)$ today and a random amount $w (T)$ at $T$
Then investor consumption plan is $C (0)=\frac{w (0)}{\mathbf{CP}\mathbf{|}_{(0)}}$ and $C (T)=\frac{w (T)}{\mathbf{CP}\mathbf{|}_{(T)}}.$
- Suppose the investor now has an unexpected bonus today of $100 dollar.
- The investor can:
1. Spend $100 today and buy $\frac{\$100}{\text{СРГ}(0)}$ amount of the consumption good, which will procure him/her an additional amount of utility
$$U'\left (C (0), 0\right)\times\frac{\$100}{\mathsf{CPI}(0)}$$
2. Save the 100 dollars, and buy $\frac{\$100}{Z (0, T)}$ zero coupon bonds with maturity $T$ .At that time, the investor can buy $\frac{\$100}{Z (0, T)}\frac 1{\mathbf{CPI}(T)}$ of the cosumptiongod, for an additional amount of utility
$$\frac{\$100}{Z\left (0, T\right)}\frac 1{\mathsf{CPI}(T)}U'\left (C (T), T\right)$$
## Equilibrium
- Equilibrium requires the agent to be indifferent between 1 and 2. Because quantities at $T$ are unknown, the indifference condition is
$$C (0), 0)\times\frac{\$100}{\mathsf{CPI}(0)}=E\left[\frac{\$100}{Z (0, T)}\frac{1}{\mathsf{CPI}(T)}U^{\prime}\left (C (T), T\right.\right]$$
- By reshuffling, we obtain
$$Z (0, T)=E\left[\frac{\mathsf{CPI}(0)}{\mathsf{CPI}(T)}\times\frac{U' (C (T), T)}{U' (C (0), 0)}\right]$$
- In aggregate, real consumption $C (t)$ depends on real GDP $Y (t)$
 - Assume that inflation and real GDP growth have the joint log-normal distribution
$$\begin{pmatrix}{\log\left (\frac{\mathsf{CPI}(T)}{\mathsf{CPI}(0)}\right)}\\{\log\left (\frac{Y (T)}{Y (0)}\right)}\end{pmatrix}=\begin{pmatrix}x\\y\end{pmatrix}\thicksim\mathcal{N}\left (\left (\begin{array}{c}\overline{\pi}T\\\overline{g}T\end{array}\right.\right),\left (\begin{array}{c}\sigma\pi^2 T\\\sigma\pi\sigma_g\rho_{g,\pi}T\end{array},\begin{array}{c}\sigma\pi\sigma_g\rho_{g,\pi}T\\\sigma_g^2 T\end{array}\right)$$
## Equilibrium Prices
- Substitute the CRRA utility function
$$U' (C, t)=e^{-\rho t}C (t)^{-\gamma}$$
- And use $C (t)=Y (t)$ for $t=0, T$ to find
$$\begin{aligned}
Z (0, T)& =\: E\left[e^{-x}\times\frac{e^{-\rho T}Y (T)^{-\gamma}}{Y (0)^{-\gamma}}\right]  \\
&=\: E\left[e^{-\rho T}\times e^{-x-\gamma y}\right] \\
&=\:e^{-\rho T}\:\times\:e^{-\overline{\pi}T-\gamma\overline{g}+\frac{1}{2}(\sigma\pi^{2}+\gamma^{2}\sigma_{g}+2\gamma\sigma\pi\sigma_{g}\rho_{g,\pi}) T}
\end{aligned}$$
·Thus, the nominal rate is
$$\begin{aligned}r (0, T)=\underbrace{\left (\rho+\gamma\overline{g}-\frac{\gamma^2}{2}\sigma_g^2\right)}_{\textbf{real rate }r_{real}(0, T)}+\underbrace{\overline{\pi}-\frac{1}{2}\sigma\pi^2}_{\textbf{exp. Infl. \& conv.}}-\underbrace{\gamma\sigma\pi\sigma_g\rho_{g,\pi}}_{\textbf{risk premium}}\end{aligned}$$
Real rate $r_{real}(0, T)$ exp. Infl. & conv. Risk premium
### The Economics of the Real Rate
- Following the same steps as above but using TIPS zero-coupon bonds $Z^{TIPS}(0, T)$ instead of nominal bonds $Z (0, T)$ we obtain the real rate as:
$$r_{real}(0, T)=\rho+\gamma\overline{g}-\frac{\gamma^2}{2}\sigma_g^2$$
- The real rate depends on:
1. Time preference $\rho$
-High $\rho$ implies investors want to consume today rather then tomorrow. They will sell their (real) bonds which increase their yield.
2. The expected growth rate of the economy $\overline{g}$
-If $\overline{g}$ is high we expect to be rich at $T$ and hence consume a lot then. High $\gamma$ implies we want “stable consumption" over time. Hence we want to borrow to consume more today, which increases real rates.
3. The volatility of GDP growth $\sigma_g$
- Higher economic risk implies a higher desire to save for the "rainy days". We buy more (real) bonds, which push their prices up and decrease yields. - The higher the risk aversion $\gamma$ and the more we want to save.
## Inflation Risk Premium
- We found
Inflation risk premium $=-\gamma\sigma\pi\sigma_{g}\rho_{g,\pi}$
- Where
$\rho_{g,π}$ = Correlation (Inflation, real GDP growth)
 - Intuitively:
-If $\rho_{g,\pi}<0\Longrightarrow$ high inflation occurs when real GDP is low $\Longrightarrow$ nominal bond is devalued in recessions, when people most need the money! $\Longrightarrow$ very risky security $\Longrightarrow$ high risk premium $\Longrightarrow$ high long-term yield
·Next figures show that the correlation $\rho_{g,\pi}$ was negative until late 1990 s. It then became closer to zero. And then became strongly positive around 2008.
- In the meantime, real GDP volatility $\sigma_{g}$ and inflation volatility oπ declined.
- All of these variation are bound to impact the risk premium.
Quarterly Real GDP Growth and CPI Infation
Quarterly Real GDP Growth and CPI Infation
 ![500](https://storage.simpletex.cn/view/f0kGTgyHyanM9iG7SiH1wg6OI7UZc9XXz)
Data Source: Federal Reserve of St. Louis
# Correlation and Real GDP growth and CPI inflation Volatilities.
Backward-looking 10-year Rolling Window.
 ![500](https://storage.simpletex.cn/view/fXdONCuSPPte99MwRrgVnQtvl5HGAiCG2)
Data Source: Federal Reserve of St. Louis
### Expected Excess Return: The Market Model
 - Another way to understand the risk premium of nominal bonds is to look at its variation with the stock market
- Under the CAPM, for instance
$E$ [Excess Return Nominal Bond] $=\beta\times E$ [Excess Return Market]
- Next figure shows the time variation in the correlation between stock and bonds, and the corresponding CAPM beta.
- Why did the CAPM beta change over time?
- David and Veronesi (2013, JPE): Time varying role of inflation signals
* Late 1970 s/ early 1980 s: Fear of stagflation (high inflation and low growth) $\Longrightarrow$ high inflation shocks are bad news for the economy $\Longrightarrow$ both nominal bonds and stock drop * Mid 2000 s: Fear of deflation (low inflation and low growth) $\Longrightarrow$ high inflation shocks are good news for the economy $\Longrightarrow$ nominal bonds drop but stock rise
## The Covariance between Stocks and Bonds, and the CAPM Bond Beta
 ![500](https://storage.simpletex.cn/view/fXF21GBGCFhZgG6ta1Ye1QlIoMBADDDK6)
Source: David and Veronesi (2016）“The Economics of the Comovement of Stocks and Bonds"in the Handbook of Fixed Income, Pietro
Veronesi (Editor), Wiley and Sons
# Nominal and Real Stock Betas
Figure 1: Rolling Nominal and Real Bond-Stock Betas
 ![500](https://storage.simpletex.cn/view/fsg4aE2VoyHIm8LizoDLNB5cn0Xq3GHuo)
Source: Caroline Pflueger (2024)“Back to the 1980 s or Not? The Drivers of Inflation and Real Risks in Treasury Bonds"
### More General Formulas
 - All previous formulas have “"flat" term structures: $r (0, T)$ and $r_{real}(0, T)$ do not depend on $T$
- They can be generalized by assuming that expected inflation $\overline{\pi}_t$ and expected GDP growth $\overline{g}_t$ are time varying.
- Using the continuous time methodology, for instance, we may assume
$$d\overline{\pi}_{t}\:=\: (\alpha\pi-\beta\pi\overline{\pi}_{t}) dt+\sigma_{\overline{\pi}}\: dW_{\overline{\pi}}\\d\overline{g}_{t}\:=\: (\alpha_{g}-\beta_{g}\overline{g}_{t}) dt+\sigma_{\overline{g}}\: dW_{\overline{g}}$$
 - Inflation and real GDP growth themselves are
$$\begin{array}{rcl}d\log (\mathsf{CPI}_t)&=&\pi_tdt+\sigma_\pi&dW_\pi\\d\log (Y_t)&=&\overline{g}_tdt+\sigma_g&dW_g\end{array}$$
- The same argument as above has
$$Z (t, T)=E_t\left[\frac{\mathsf{CPI}(t)}{\mathsf{CPI}(T)}e^{-\rho (T-t)}\left (\frac{Y (T)}{Y (t)}\right)^{-\gamma}\right]$$
### Bond Pricing Formulas
- Solving the expectation, we obtain
$$Z (t, T)=e^{A (t, T)-B (t, T)\overline{\pi}_{t}-C (t, T)\gamma\overline{g}_{t}}$$
·where
$$(t, T)=\frac{1-e^{-\beta\pi (T-t)}}{\beta\pi};\quad C (t, T)=\frac{1-e^{-\beta_{g}(T-t)}}{\beta_{g}}$$
·and $A (t, T)$ is a complicated function of maturity $(T-t)$ which includes risk premia and other terms further discussed below.
·The nominal yield curve is then
$$r (t, T)=\frac{-A (t, T)}{T-t}+\frac{B (t, T)}{T-t}\:\pi_t+\frac{C (t, T)}{T-t}\:\gamma\bar{g}_t$$
- A higher expected inflation increases nominal yield, but differentially across maturities
- A higher expected real growth increases nominal yields, but differentially across maturities
##### The Function A (t, T)
$$ \begin{aligned}
A (t (T -t)- B (t, T))=&\left (-\rho+\frac{1}{2}\sigma_{\pi}^{2}+\frac{1}{2}\gamma^{2}\sigma_{g}^{2}+\gamma\sigma_{\pi}\sigma_{g}\rho_{\pi g}\right)(T-t) \\
&+\left[\sigma_{\pi}\sigma_{\overline{\pi}}\rho_{\pi\overline{\pi}}+\gamma\sigma_{g}\sigma_{\overline{\pi}}\rho_{g\overline{\pi}}-\alpha_{\pi}+{\frac{1}{2}}{\frac{\sigma_{\overline{\pi}}^{2}}{\beta_{\pi}}}+{\frac{\gamma\sigma_{\overline{\pi}}\sigma_{\overline{g}}\rho_{\overline{\pi}\overline{g}}}{\beta_{\pi}+\beta_{g}}}\right]{\frac{1}{\beta_{\pi}}}\left (\left (7\right)\right) \\
&+\left[\sigma_{\pi}\sigma_{\overline{g}}\rho_{\pi\overline{g}}+\gamma\sigma_{g}\sigma_{\overline{g}}\rho_{g\overline{g}}-\alpha_{g}+{\frac{1}{2}}{\frac{\gamma\sigma_{\overline{g}}^{2}}{\beta_{g}}}+{\frac{\sigma_{\overline{\pi}}\sigma_{\overline{g}}\rho_{\overline{\pi}\overline{g}}}{\beta_{\pi}+\beta_{g}}}\right]{\frac{\gamma}{\beta_{g}}}\left (\left (T\right)\right) \\
&-\frac{1}{4}\frac{\sigma_{\overline{\pi}}^{2}}{\beta_{\pi}}B\left (t, T\right)^{2}-\frac{1}{4}\frac{\gamma^{2}\sigma_{\overline{g}}^{2}}{\beta_{g}}C\left (t, T\right)^{2}-\frac{\gamma\sigma_{\overline{\pi}}\sigma_{\overline{g}}\rho_{\overline{\pi g}}}{\left (\beta_{\pi}+\beta_{g}\right)}B\left (t, T\right) C
\end{aligned}$$
- Many risk premia
$$\gamma\sigma_{\pi}\sigma_{g}\rho_{\pi g}.\quad\text{If}\rho_{\pi g}<0\Longrightarrow Z (t, T)\downarrow\Longrightarrow r (t, T$$
2. Expected inflation risk premium: $\gamma\sigma_{g}\sigma_{\overline{\pi}}\rho_{g\overline{\pi}}$ If $\rho_{g,\overline{\pi}}<0\Longrightarrow r (t, T)$ ↑ 3. Expected growth risk premium: $\gamma\sigma_{g}\sigma_{\overline{g}}\rho_{g\overline{g}}$ If $\rho_{g,\overline{g}}<0\Longrightarrow r (t, T)$ ↑ - and many convexity effects.
## The Short-term Rate and Monetary Policy Interpretation
- As we take the limit $T - t \to 0$, we obtain the formula for the "overnight" rate:$$
  R_t = \rho + \gamma \bar{g}_t - \frac{\gamma^2}{2} \sigma_g^2 
  + \pi_t - \frac{1}{2} \sigma_\pi^2 
  - \gamma \sigma_\pi \sigma_g \rho_{\pi, g}
 $$$$
  \underbrace{\rho + \gamma \bar{g}_t - \frac{\gamma^2}{2} \sigma_g^2}_{\text{real rate } r_{\text{real}, t}} 
  \quad + \quad 
  \underbrace{\pi_t - \frac{1}{2} \sigma_\pi^2}_{\text{exp. Infl. \& conv.}} 
  \quad - \quad 
  \underbrace{\gamma \sigma_\pi \sigma_g \rho_{\pi, g}}_{\text{risk premium}}
 $$
- The Federal Reserve is believed to follow the so-called "Taylor rule" in setting its target Federal Fund rate, which specifies:
  $$
  R_t = \alpha + \beta_1 (\text{output}_t - \text{potential output}) 
  + \beta_1 (\text{inflation}_t - \text{target inflation})
 $$
- The "forward looking" Taylor rule uses "expected inflation" and expected output to their realized values.
- The result above can be casted in terms of monetary policy actions:$$
  R_t = \alpha + \gamma (\bar{g}_t - \text{potential output}) + (\pi_t - \text{target inflation})
 $$
- Where:$$
  \alpha = \rho - \frac{\gamma^2}{2} \sigma_g^2 - \frac{1}{2} \sigma_\pi^2 
  - \gamma \sigma_\pi \sigma_g \rho_{\pi, g} 
  + \gamma \text{potential output} + \text{target inflation}.
 $$
### The Dynamics of the Real Rate
- From previous results and using Ito's formula, the real rate follows a Vasicek model
$$dr_{real, t}=\beta_g\left (\overline{r}_{real}-r_{real, t}\right) dt+\sigma_{real}dW_{\overline{g}}$$
Where
$$\overline{r}_{real}=\rho+\gamma\frac{\alpha_g}{\beta_g}-\frac{\gamma^2\sigma_{\overline{g}}^2}{2};\quad\sigma_{real}=\gamma\sigma_{\overline{g}}$$
- The real zero-coupon bond pricing formula is then
$$Z_{real}(t, T)=e^{\overline{A}(t, T)-C (t, T) r_{real, t}}$$
·where
$$T)=\left (\overline{r}_{real}^{*}-\frac{1}{2}\frac{\sigma_{real}^{2}}{\beta_{g}^{2}}\right)[C (t, T)-(T-t)]-\frac{C (t, T)}{4}$$
$\bullet$ where $\overline{r}_{real}^{*}=\overline{r}_{real}-\gamma\sigma_{g}\sigma_{real}\rho_{\rho, real}$
 - The risk neutral process of the real rate is
$$dr_{real, t}=\beta_g\left (\overline{r}_{real}^*-r_{real, t}\right) dt+\sigma_{real}dW_{\overline{g}}^*$$
## Fitting Real Vasicek to TIPS
- We can use TIPS again to extract the real zero coupon bond prices
- The procedure is the same for nominal Vasicek (see TN 7), except with the additional dificulty that we may not know what the short-term real rate $r_{real, t}$ actually is.
- One possibility is to estimate $r_{real, t}$ as well together with other quantities.
- For instance, fixing $\sigma_{real}=. 00967$ (estimated from the time series of real rates), we estimate the following parameters for November 27, 2007:
$$\begin{matrix}\beta_g^*=0.0166,&\overline{r}_{real}^*=0.1695,&r_{real, 0}=0.0046\end{matrix}$$
- The fit is not as good as with the Extended Nelson-Siegel model in this case.
- Next figure shows the fitted term structure of real rates.
## Vasicek Fit to TIPS on November 27, 2007
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/cf2f42bc584a2f12512a8f235f71f4a02ee61b1befec2493a1bdac7ef675b6df.jpg)  
 ![500](/images/fvwgapa19DUglDdLX4l31ZG98Pg0oZEke.png)
Data Source: Bloomberg
## Conclusions
- The term structure of interest rate depend on:
1. Expectation of future inflation 2. Expectation of future real growth 3. A whole set of risk premia - Inflation risk premium - Expected inflation risk premium - Expected growth risk premium
- Multi-factor models tend to fit well the term structure of interest rates
- The above setting with expected inflation and expected GDP growth can be generalized to any factors Φ1, t $\phi_{1, t}$ $\phi _{1, t}$, $\phi _{2, t\ldots }$
- - Moreover, pricing formulas can be obtained using no-arbitrage methodologies, as in TN 7.
### Appendix: Derivation of Two Factor Model
Define
$$\begin{array}{rcl}q&=&\log{(\mathsf{CPI})}\\y&=&\log{(Y)}\end{array}$$
So that
$$\begin{array}{rcl}dq&=&\overline{\pi}_tdt+\sigma_\pi dW_\pi\\dy&=&\overline{g}_tdt+\sigma_gdW_g\end{array}$$
And recall
$$\begin{array}{rcl}d\overline\pi_t&=&(\alpha_\pi-\beta_\pi\pi_t)\:dt+\sigma_{\overline\pi}dW_{\overline\pi}\\d\overline g&=&(\alpha_g-\beta_g\pi_t)\:dt+\sigma_{\overline g}dW_{\overline g}\end{array}$$
From the pricing equation we have.
$$Z\left (t, T\right)=E\left[e^{-\rho (T-t)-(q (T)-q (t))-\gamma (y (T)-y (t))}\right]$$
To be slightly more general, consider the following case
$$\begin{aligned}
Z\left (t, T\right)& =\: E\left[e^{-\rho (T-t)-\eta (q (T)-q (t))-\gamma (y (T)-y (t))}\right] \\
&=\:e^{\eta q (t)+\gamma y (t)}E\left[e^{-\rho (T-t)}G\left (q\left (T\right), y\left (T\right)\right)\right] \\
&=\:e^{\eta q (t)+\gamma y (t)}V\: (q, y,\overline{\pi},\overline{g}, t)
\end{aligned}$$
When $\eta=1$ we have the case for nominal bonds. When $\eta=0$ we have the case of realbonds. When $\eta$ is intermediate, this can be considered. A case in which inflation affects the utility function of agents directly. A case in the literature is the one of money illusion.
From the Feynman Kac formula, we have that $V$ satisfies
$$V_{t}+V_{q}E\left[dq\right]+V_{y}E\left[dy\right]+V_{\overline{\pi}}E\left[d\overline{\pi}\right]+V_{\overline{g}}E\left[d\overline{g}\right]+\frac{1}{2}V_{qq}E\left[dq^{2}\right]+\frac{1}{2}V_{yy}E\left[dy^{2}\right]+\frac{1}{2}\\+V_{qy}E\left[dqdy\right]+V_{q\overline{\pi}}E\left[dqd\overline{\pi}\right]+V_{q\overline{g}}E\left[dqd\overline{g}\right]+V_{y\overline{\pi}}E\left[dyd\overline{\pi}\right]+V_{y\overline{g}}E\left[dyd\overline{g}\right]+V_{\overline{\pi}\overline{g}}E\left[dyd\overline{g}\right]+V_{\overline{\pi}\overline{g}}E\left[dyd\overline{g}\right]$$
With final condition  
$$
V\left (q, y,\overline {{{\pi}} },\overline {{{g}} }, T\right)=e^{-\eta q\left (T\right)-\gamma y\left (T\right)}
$$  
We can conjecture the following  
$$
V\left (q, y,\overline {{{\pi}} },\overline {{{g}} }, t\right)=e^{-\eta q (t)-\gamma y (t)+A (t; T)-\eta B (t; T)\overline {{{\pi}} }-\gamma C (t; T)\overline {{{g}} }}
$$  
Taking the first derivatives  
$$
{\begin{array}{r l}{V_{t}}&{=\,\,\left[A^{\prime}\left (t; T\right)-\eta B^{\prime}\left (t; T\right){\overline {{\pi}} }-\gamma C^{\prime}\left (t; T\right){\overline {{g}} }\right]V}\\ {V_{q}}&{=\,\,-\eta V; V_{q q}=\eta^{2}V; V_{q y}=\eta\gamma V; V_{q\overline {{\pi}} }=\eta^{2}B\left (t; T\right) V; V_{q\overline {{g}} }=\eta\gamma C\left (t; T\right) V}\\ {V_{y}}&{=\,\,-\gamma V; V_{y y}=\gamma^{2}V; V_{y\overline {{\pi}} }=\gamma\eta B\left (t, T\right); V_{y\overline {{g}} }=\gamma^{2}C\left (t, T\right)}\\ {V_{\overline {{\pi}} }}&{=\,\,-\eta B\left (t, T\right) V; V_{\overline {{\pi\pi}} }=\eta^{2}B\left (t, T\right)^{2}V; V_{\overline {{\pi g}} }=\eta\gamma B\left (t, T\right) C\left (t, T\right) V}\\ {V_{\overline {{g}} }}&{=\,\,-\gamma C\left (t, T\right) V; V_{\overline {{g g}} }=\gamma^{2}C\left (t, T\right)^{2}V}\end{array}}
$$  Substituting and deleting the common    $V$  
$$
{\begin{array}{l} \rho= {{\displaystyle[A^{\prime}\left(t;T\right)-\eta B^{\prime}\left(t;T\right)\overline{{\pi}} -\gamma C^{\prime}\left (t; T\right)\overline {{g}} ]-\eta\overline {{\pi}} -\gamma\overline {{g}} -\eta B\left (t,         T\right)\left (\alpha_{\pi}-\beta_{\pi}\overline {{\pi}} \right)-\gamma C\left (t,         T\right)\left (\alpha_{\pi}+\beta_{\pi}\overline {{\pi}} \right)}}\\ {{\displaystyle+{\frac{1}{2}} \eta^{2}\sigma_{\pi}^{2}+{\frac{1}{2}}\gamma^{2}\sigma_{g}^{2}+{\frac{1}{2}}\eta^{2}B\left (t,         T\right)^{2}\sigma_{\overline {{\pi}} }^{2}+{\frac{1}{2}}\gamma^{2}C\left (t,         T\right)^{2}\sigma_{\overline {{g}} }^{2}}}\\ {{\displaystyle+\gamma\eta\sigma_{\pi}\sigma_{g}\rho_{\pi g}+\eta^{2}B\left(t,        T\right)\sigma_{\pi}\sigma_{\overline{{\pi}} }\rho_{\pi\overline {{\pi}} }+\eta\gamma C\left (t,         T\right)\sigma_{\pi}\sigma_{\overline {{g}} }\rho_{\pi\overline {{g}} }}}\\ {{\displaystyle+\gamma\eta B\left(t,        T\right)\sigma_{g}\sigma_{\overline{{\pi}} }\rho_{g\overline {{\pi}} }+\gamma^{2}C\left (t,         T\right)\sigma_{g}\sigma_{\overline {{g}} }\rho_{g\overline {{g}} }+\eta\gamma B\left (t,         T\right) C\left (t,         T\right)\sigma_{\overline {{\pi}} }\sigma_{\overline {{g}} }\rho_{\overline {{\pi g}} }}}\end{array}}
$$  
Factor out variables $\overline {{\pi}} $ and $\overline {{g}} $
$$
\begin{array}{r c l} {{\rho}} & {{=}} & {{\displaystyle-\eta\left[B^{\prime}\left(t;T\right)+1-\beta_{\pi}\right]\overline{{{\pi}} }-\gamma\left[C^{\prime}\left (t; T\right)+1-\beta_{g}\right]\overline {{{g}} }-\eta B\left (t,         T\right)\alpha_{\pi}-\gamma C\left (t,         T\right)}}\alpha_{g}\\ {{}} & {{}} & {{\displaystyle A^{\prime}\left(t;T\right)+\frac{1}{2}\eta^{2}\sigma_{\pi}^{2}+\frac{1}{2}\gamma^{2}\sigma_{g}^{2}+\frac{1}{2}\eta^{2}B\left(t,        T\right)^{2}\sigma_{\overline{{{\pi}} }}^{2}+\frac{1}{2}\gamma^{2}C\left (t,         T\right)^{2}\sigma_{\overline {{{g}} }}^{2}}}\\ {{}} & {{}} & {{\displaystyle+\gamma\eta\sigma_{\pi}\sigma_{g}\rho_{\pi g}+\eta^{2}B\left(t,        T\right)\sigma_{\pi}\sigma_{\overline{{{\pi}} }}\rho_{\pi\overline {{{\pi}} }}+\eta\gamma C\left (t,         T\right)\sigma_{\pi}\sigma_{\overline {{{g}} }}\rho_{\pi\overline {{{g}} }}}}\\ {{}} & {{}} & {{\displaystyle+\gamma\eta B\left(t,        T\right)\sigma_{g}\sigma_{\overline{{{\pi}} }}\rho_{g\overline {{{\pi}} }}+\gamma^{2}C\left (t,         T\right)\sigma_{g}\sigma_{\overline {{{g}} }}\rho_{g\overline {{{g}} }}+\eta\gamma B\left (t,         T\right) C\left (t,         T\right)\sigma_{\overline {{{\pi}} }}\sigma_{\overline {{{g}} }}\rho_{\pi\overline {{{g}} }}}}\end{array}
$$  
This is satisfied for all values of    $\overline {{\pi}} $   and    $\bar{g}$   if and only if the following system is satisfied  
$$
\begin{array}{r l r}{0}&{{}\!=\!}&{\left[B^{\prime}\left (t; T\right)+1-\beta_{\pi}B\left (t, T\right)\right]}\\ {0}&{{}\!=\!}&{\left[C^{\prime}\left (t; T\right)+1-C\left (t, T\right)\beta_{g}\right]}\end{array}
$$  
And  
$$
\begin{array}{r l r}{\rho}& {{}\!=}&{A^{\prime}\left(t;T\right)-\eta B\left(t,T\right)\alpha_{\pi}-\gamma C\left(t,T\right)\alpha_{g}} \end{array}
$$  
$$
\begin{array}{l} {{\displaystyle+\frac{1}{2}\eta^{2}\sigma_{\pi}^{2}+\frac{1}{2}\gamma^{2}\sigma_{g}^{2}+\frac{1}{2}\eta^{2}B\left(t,T\right)^{2}\sigma_{\pi}^{2}+\frac{1}{2}\gamma^{2}C\left(t,T\right)^{2}\sigma_{\overline{{g}} }^{2}}}\\ {{\displaystyle+\gamma\eta\sigma_{\pi}\sigma_{g}\rho_{\pi g}+\eta^{2}B\left(t,T\right)\sigma_{\pi}\sigma_{\overline{{\pi}} }\rho_{\pi\overline {{\pi}} }+\eta\gamma C\left (t, T\right)\sigma_{\pi}\sigma_{\overline {{g}} }\rho_{\pi\overline {{g}} }}}\\ {{\displaystyle+\gamma\eta B\left(t,T\right)\sigma_{g}\sigma_{\overline{{\pi}} }\rho_{g\overline {{\pi}} }+\gamma^{2}C\left (t, T\right)\sigma_{g}\sigma_{\overline {{g}} }\rho_{g\overline {{g}} }+\eta\gamma B\left (t, T\right) C\left (t, T\right)\sigma_{\overline {{\pi}} }\sigma_{\overline {{g}} }\rho_{\pi\overline {{g}} }}}\end{array}
$$  
With final conditions  
$$
B\left (T, T\right)=0; C\left (T, T\right)=0; A\left (t; T\right)=0
$$  
The first two ODEs have solutions  
$$
\begin{array}{r c l} {{B\left(t,T\right)}} & {{=}} & {{\displaystyle\frac{1-e^{-\beta_{\pi}\left(T-t\right)}} {\beta_{\pi}}}}\\ {{C\left(t,T\right)}} & {{=}} & {{\displaystyle\frac{1-e^{-\beta_{g}\left(T-t\right)}} {\beta_{g}}}}\end{array}
$$  
$$\begin{array}{rcl}B\left (t, T\right)&=&\frac{1-e^{-\beta_\pi\left (T-t\right)}}{\beta_\pi}\\C\left (t, T\right)&=&\frac{1-e^{-\beta_g\left (T-t\right)}}{\beta_g}\end{array}$$
The last ODE has solution
$$\begin{aligned}
A\left (t, T\right)& \left (-\rho+\frac{1}{2}\eta^{2}\sigma_{\pi}^{2}+\frac{1}{2}\gamma^{2}\sigma_{g}^{2}+\gamma\eta\sigma_{\pi}\sigma_{g}\rho_{\pi g}\right)(T-t)  \\
&+\left[\eta^{2}\sigma_{\pi}\sigma_{\overline{\pi}}\rho_{\pi\overline{\pi}}+\gamma\eta\sigma_{g}\sigma_{\overline{\pi}}\rho_{g\overline{\pi}}-\eta\alpha_{\pi}+\frac{1}{2}\frac{\eta^{2}\sigma_{\overline{\pi}}^{2}}{\beta_{\pi}}+\frac{\eta\gamma\sigma_{\overline{\pi}}\sigma_{\overline{g}}\rho_{\overline{\pi}\overline{g}}}{\beta_{\pi}+\beta_{g}}\right]\frac{1}{\beta_{\pi}}\left (\left (T-t\right)\right) \\
&+\left[\eta\gamma\sigma_{\pi}\sigma_{\overline{g}}\rho_{\pi\overline{g}}+\gamma^{2}\sigma_{g}\sigma_{\overline{g}}\rho_{g\overline{g}}-\gamma\alpha_{g}+\frac{1}{2}\frac{\gamma^{2}\sigma_{\overline{g}}^{2}}{\beta_{g}}+\frac{\eta\gamma\sigma_{\overline{\pi}}\sigma_{\overline{g}}\rho_{\overline{\pi}\overline{g}}}{\beta_{\pi}+\beta_{g}}\right]\frac{1}{\beta_{g}}\left ((T-t)\right) \\
&-\frac{1}{4}\frac{\eta^{2}\sigma_{\overline{\pi}}^{2}}{\beta_{\pi}}B\left (t, T\right)^{2}-\frac{1}{4}\frac{\gamma^{2}\sigma_{\overline{g}}^{2}}{\beta_{g}}C\left (t, T\right)^{2}-\frac{\eta\gamma\sigma_{\overline{\pi}}\sigma_{\overline{g}}\rho_{\overline{\pi g}}}{\left (\beta_{\pi}+\beta_{g}\right)}B\left (t, T\right) C\left (t, T\right)
\end{aligned}$$
Setting $\eta=1$ provides the formula for $A (t, T)$ in the text. Moreover, the case $\eta=0$ corresponds to the real bond, obtaining
$$\begin{array}{rcl}{A_{\mathrm{real}}\left (t, T\right)}&{=}&{\left (-\rho+\frac{1}{2}\gamma^{2}\sigma_{g}^{2}\right)\left (T-t\right)+\left[\gamma^{2}\sigma_{g}\sigma_{\bar{g}}\rho_{\bar{g}\bar{g}}-\gamma\alpha_{g}+\frac{1}{2}\frac{\gamma^{2}\sigma_{\bar{g}}^{2}}{\beta_{g}}\right]\frac{1}{\beta_{g}}\left (\left (T-t\right)-C\left (t, T\right)\right)-\frac{1}{4}\frac{\gamma^{2}\sigma_{\bar{g}}^{2}}{\beta_{g}}C\left (t, T\right)^{2}}\end{array}$$