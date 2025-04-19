---
title: Lecture 8- Inflation & Sovereign Default Risk
tags:
  - cpi
  - inflation
  - nominal_returns
  - purchasing_power
  - real_returns
aliases:
  - Lecture 8
  - Sovereign Risk
key_concepts:
  - Asset Mix and Portfolio
  - Consumer Price Index (CPI)
  - Inflation and Purchasing Power
  - Long-term Investment Impact
  - Nominal vs. Real Returns
---

  [Teaching Note 2- Interest Rate Risk Management And Factors](Teaching%20Note%202-%20Interest%20Rate%20Risk%20Management%20And%20Factors.md)
  
# Lecture 8- Inflation & Sovereign Default Risk
  
So far we have discussed [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]] in terms of nominal returns. This means, we have not taken into account the loss of purchasing power that an investor may experience over time due to inflation. The loss of purchasing power that a long-term investor experiences over time can be substantial even with moderate inflation rates. From a [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]] viewpoint, the key question is whether the risk of such loss of purchasing power can be altered by choosing an appropriate asset mix in the portfolio.
  
### 8.1 Nominal and real returns
  
If we measure purchasing power with the consumer price index (CPI), the inflation rate is
  
$$
\begin{equation*}
\Pi_{t+1}=\frac{C P I_{t+1}}{C P I_{t}}-1 \tag{8.1}
\end{equation*}
$$
  
The inflation rate based on the CPI does not necessarily provide the correct measurement of the loss of purchasing power of a dollar that an investor experiences. A price index is a weighted average of the prices of a huge number of individual goods and services. The weighting of these goods and services in the CPI is meant to be appropriate for a representative consumer, but in practice different consumers will have different weights of goods and services in their personal consumption baskets. There are also different official price indices, constructed for different purposes, that use different weights, such as the Personal Consumption Expenditures (PCE) price index, or the GDP deflator that is used to estimate the real gross domestic product. We won't go into the details here of how one could better measure an investor's loss of purchasing power and we'll just assume that the CPI is a good proxy to measure investors' loss of purchasing power due to inflation.
 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-268.jpg?height=822&width=1180&top_left_y=302&top_left_x=429)
  
Figure 8.1: U.S. inflation rate based on consumer price index
  
Consider an asset with nominal return $R_{t}$. Then the real return of an asset, after adjusting for the loss of purchasing power, is
  
$$
\begin{equation*}
R_{t}^{r}=\left(1+R_{t}\right) /\left(1+\Pi_{t}\right)-1 \approx R_{t}-\Pi_{t} \tag{8.2}
\end{equation*}
$$
  
For some investors, focusing on optimizing nominal returns may be fine. For example, many insurance companies have liabilities that are largely fixed in nominal terms. They then try to match these nominal liabilities with assets that deliver payoffs fixed in nominal terms. For others, such as investors saving for retirement who care about the purchasing power that they will have in retirement, the focus should be on optimizing real returns. For some investors the objective may be mixed. For example, many public pension funds have pension liabilities that are partially indexed to inflation. The final salaries that determine benefit levels of future retirees tend to grow with inflation, but the payments to existing retirees are often only partially indexed to inflation.
  
In the rest of this lecture, we will take the perspective of an investor who cares about real returns and wants to optimize risk and return in real terms.
  
At long horizons, the difference between nominal and real returns can be huge. Figure 8.1 shows the history of CPI inflation in the U.S. during the post world war II period, measured as the percentage change in CPI over 12-month intervals. Investors in the 1970s and 1980s experienced inflation rates above $10 \%$. These inflation rates could turn
 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-269.jpg?height=936&width=1199&top_left_y=296&top_left_x=474)
  
Figure 8.2: Final values in real and nominal terms of a 20-year long investment in a portfolio of U.S. Treasury bonds with 5-10 year maturity
a $10 \%$ yield on a Treasury bond into a zero return in real terms. Over the subsequent decades, inflation rates fell to much lower levels and were more stable. Only very recently, in the wake of the COVID pandemic, inflation started rising again to levels we had not seen since the early 1980s.
  
Figure 8.2 illustrates the consequences that inflation had for the experiences of longterm bond investors during the past decades. In this figure, I consider an investor who invests 1$ to purchase a portfolio of 5-10 year U.S. Treasury bonds and rebalances this portfolio every month so that it stays within the 5-10 year maturity band. The investor does this rebalancing for 20 years and I then look at the final value of the portfolio after 20 years in nominal terms and in real terms. The bonds in this portfolio are regular U.S. Treasury bonds that have principal and coupons fixed in nominal terms (we'll discuss a different kind that offers inflation-adjusted payoffs later in this lecture).
  
The blue line in the figure shows the nominal final value. For example, the point on the blue line for 1975 says that an investor who held this bond portfolio from 1956 to 1975 turned the initial 1$ into around 2.1$. The real line shows the real value, after removing the effects of inflation. The point for 1975 on the red line therefore says that in terms of purchasing power, the investor who started in 1956 just achieved a preservation of the purchasing power of his investment, but not more than this: the real return was zero.
 ![500](Keep%20It%202024-10-24%2010.52.05.png)
Figure 8.3: Top-10 hyperinflations in world history
Source: Hanke, S.H. and Krus, N., 2013. World hyperinflations. In: Routledge handbook of major events in economic history (pp. 384-394). Routledge.
  
Investors who started a little later, say in 1963 and held the portfolio until 1982, experienced a loss of purchasing power of about $10 \%$, even though in nominal terms their portfolio more than doubled.
  
Investors who started in the mid-1970s and held the portfolio until 1995 had an initially terrible experience in real terms. However, due to bond yields coming down in the second half of the 1980s and the 1990s, and hence increasing bond prices, these investors also benefited from a huge nominal return on their bond holdings. Since inflation rates had come down at that time, too, this also meant a high real return. So overall, while there is a huge gap from real returns to the huge nominal returns of around $700 \%$, by 1995 these investors ended up more than doubling their purchasing power. The low real returns in the first half of their 20-year period were more than offset by the high real returns in the second half.
  
The inflation rates above 10\% per year experienced by the U.S. in the 1970s and 1980s were a substantial drag on real returns for investors holding securities with nominally fixed payoffs. Investors in other developed countries experienced similar rates of inflation around the same time. In Germany inflation peaked at $8 \%$; in the U.K. the peak was at $25 \%$. However, these inflation rates pale against the inflation rates that some countries throughout history have experienced during episodes of hyperinflation.
  
Figure 8.5 lists the most extreme hyperinflations in world history as ranked by the maximum monthly inflation rate. The record was set in Hungary shortly after the end of the second world war. Around the peak of inflation, prices tripled in a single day. Around the peak of the hyperinflation in Germany in 1922/23, it took about four days for prices to double. In each of these cases, owners of assets with nominally fixed payoffs found their wealth completely wiped out. Borrowers with nominally fixed liabilities saw their debts effectively erased in real terms.
  
In present-day developed markets, hyperinflation seems like an extremely remote possibility. But for a cautious long-term investor with a multi-decade horizon, even such extremely low-probability risks perhaps should not be ignored entirely.
  
### 8.2 Nominal and real assets
  
When we discuss the inflation risk of different types of assets, it's useful to distinguish two extremes: nominal assets and real assets. Not all assets fit clearly into these categories. For example, for stocks and real estate it is, in the end, an empirical question how close they are to being a real or a nominal asset.
  
A nominal asset is one with nominal cash flows that are insensitive to inflation, but the real value of cash flows falls with inflation. An example would be a U.S. Treasury bond. Principal and coupon payments of these bonds are specified in nominal terms. But this could also include assets with risky payoffs, e.g. high-yield [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]]. High-yield bonds have a relatively high risk of default, which means the owner of the bond will not receive the full amount that the bond promised to pay. But to the extent there is a payoff, it is a payoff that is fixed in nominal terms. It does not get adjusted upwards if inflation happens to be high.
  
A real asset is one with real cash flows that are insensitive to inflation, which means that nominal cash flows must rise with inflation. The purchasing power of the assets' cash flows then remains unaffected by inflation. An example that gets close to being such a real assets are Treasury Inflation Protected Securities (TIPS), issued by the U.S. Treasury. We will discuss these in more detail shortly.
  
For some assets, such as regular U.S. Treasury bonds or TIPS it's clear whether they are nominal or real assets. For other assets, it's not obvious. For example, there is a debate whether stocks should be considered real or nominal assets, and to what degree. We will look into this question shortly.
  
But first some thoughts on inflation risk exposure of these different types of assets. There are two variants of this risk that are likely related, but not quite the same thing:
  
The risk of unexpected realized inflation
The risk of changing expectations of future inflation
  
To think through the effects of these risks, let's look at a simple valuation model. Consider first a nominal asset $A$ that delivers one future nominal cash flow $D_{A, t+1}$, with conditional expected value $\mathbb{E}_{t}\left[D_{A, t+1}\right]$. Let $R$ be the appropriate nominal discount rate for nominal cash flows. Then, the nominal value at $t$ is
  
$$
\begin{equation*}
V_{A, t}=\frac{\mathbb{E}_{t}\left[D_{A, t+1}\right]}{1+R} \tag{8.3}
\end{equation*}
$$
  
The price level at $t$ is $C P I_{t}$, and the inflation rate of the next period is $\Pi_{t+1}=$ $C P I_{t+1} / C P I_{t}-1$. If the expected inflation rate is not zero, investors at $t$ would demand compensation for the expected inflation in the form of a higher nominal discount rate. If investors require a real expected return of $R^{r}$ from asset $A$, then they discount nominal cash flows with the nominal rate that is the real rate required by investors adjusted for the expected inflation rate, i.e.,
  
$$
\begin{equation*}
R=\left(1+R^{r}\right)\left(1+\mathbb{E}_{t}\left[\Pi_{t+1}\right]\right)-1 \tag{8.4}
\end{equation*}
$$
  
So then we have a nominal value of ${ }^{1}$
  
$$
\begin{equation*}
V_{A, t}=\frac{\mathbb{E}_{t}\left[D_{A, t+1}\right]}{\left(1+R^{r}\right)\left(1+\mathbb{E}_{t}\left[\Pi_{t+1}\right]\right)} \tag{8.5}
\end{equation*}
$$
  
The real value is
  
$$
\begin{equation*}
V_{A, t}^{r}=\frac{C P I_{\text {base }}}{C P I_{t}} \frac{\mathbb{E}_{t}\left[D_{A, t+1}\right]}{\left(1+R^{r}\right)\left(1+\mathbb{E}_{t}\left[\Pi_{t+1}\right]\right)}, \tag{8.6}
\end{equation*}
$$
  
where we expressed the real value in terms of dollars as of some base year in which the CPI level was $C P I_{\text {base }}$.
  
Now consider the effects of an unexpected sudden increase in the level of the $C P I_{t}$, i.e., unexpected inflation. This does not change the discount rate and, since the asset is a nominal asset, it does not change the expected nominal cash flow, but it lowers the real value of this expected cash flow $\frac{C P I_{\text {base }}}{C P I_{t}} \mathbb{E}_{t}\left[D_{A, t+1}\right]$. As a consequence, $V_{A, t}^{r}$ falls. This [^35]reflects the unexpected loss of purchasing power. A nominal asset does not protect the investors against such loss of purchasing power.
  
If the expected inflation rate increases, then the discount rate $\left(1+R^{r}\right)\left(1+\mathbb{E}_{t}\left[\Pi_{t+1}\right]\right)$ in the denominator rises, which also leads to a fall in $V_{A, t}^{r}$. If inflation subsequently sticks to the expected path, then investors who buy the asset after expected inflation went up will be appropriately compensated by a higher nominal rate of return for the loss of purchasing power. But investors who already hold the asset when the rise in expected inflation occurs suffer a loss in terms of real value.
  
So rises in unexpected inflation and in expected inflation both lower the real value of a nominal asset. In practice, it's likely that the two types of risk at least partly show up at the same time. When newly released inflation number comes in higher than expected, it's also likely that investors will update their expectations of future inflation in the same direction. But this is not always the case, and it's not always the case to the same degree. More on this later.
  
Now what about real assets? Consider a real asset $B$. A real asset would have nominal cash flows that grow one for one with inflation. For example, it seems a reasonable conjecture that for companies in many industries revenues, wages, other costs, and hence also profits all grow approximately one-of-one with inflation. If so, we would have
  
$$
\begin{equation*}
\mathbb{E}_{t}\left[D_{B, t+1}\right]=\mathbb{E}_{t}\left[D_{B, t+1}^{r} \frac{\mathbb{E}_{t}\left[C P I_{t+1}\right]}{C P I_{\text {base }}}\right. \tag{8.7}
\end{equation*}
$$
  
where I assumed that now the real cash flow $D_{t+1}^{r}$ (rather than the nominal c.f.) is insensitive to changing inflation. The real value is expressed in terms of the purchasing power of dollars at time of a base year in which the CPI was at level $C P I_{\text {base }}$. The nominal value therefore grows with inflation
  
$$
\begin{align*}
V_{B, t} & =\frac{\mathbb{E}_{t}\left[D_{B, t+1}^{r}\right]}{\left(1+R^{r}\right)\left(1+\mathbb{E}_{t}\left[\Pi_{t+1}\right]\right)} \frac{\mathbb{E}_{t}\left[C P I_{t+1}\right]}{C P I_{\text {base }}}  \tag{8.8}\\
& =\underbrace{\frac{\mathbb{E}_{t}\left[D_{B, t+1}^{r}\right]}{1+R^{r}}}_{\text {Real value }} \frac{C P I_{t}}{C P I_{\text {base }}}, \tag{8.9}
\end{align*}
$$
  
while the real value
  
$$
\begin{equation*}
V_{B, t}^{r}=\frac{\mathbb{E}_{t}\left[D_{B, t+1}^{r}\right]}{1+R^{r}} \tag{8.10}
\end{equation*}
$$
  
is immune to inflation risk. An unexpected sudden increase in the level of the $C P I_{t}$, i.e., unexpected inflation, has no effect on the real value of this real asset because any increase in the CPI is matched one-for-one by the same percentage increase in the expected
nominal cash flow. A rise in expected inflation leaves the real value of this real asset unchanged because an increase in expected inflation is compensated by an increase in expected nominal cash flow.
  
### 8.3 Inflation risk and hedging
  
Let's now look at data on several asset classes to see whether the properties of returns of these assets are more in line with being a nominal or real asset. Are their real returns immune to the two types of inflation risks that we discussed above, or are they exposed?
  
To check this empirically, I construct measures of unexpected inflation and of changes in expected inflation. This requires a measure of expected inflation. While there is no single best measure of inflation expectations, and people may of course disagree about the inflation outlook, the Survey of Professional Forecasters (SPF) is a good starting point. This is a quarterly survey that asks professional macroeconomic forecasters at financial institutions and other organizations for their forecasts for inflation and other macroeconomic variables. It is currently administered by the Federal Reserve Bank of Philadelphia. Historical SPF data is available for more than 50 years.
  
Each month, I look at the most recent quarterly SPF and I use the forecasters' median forecast of the inflation rate over the next 12 months from end of month $t$ to end of month $t+12, \mathbb{E}_{t}\left[\Pi_{t: t+12}\right]$, and I compare it with the actually realized inflation rate over this period, $\Pi_{t: t+12}$ to construct a series of unexpected inflation:
  
$$
\begin{equation*}
U E_{t: t+12}=\Pi_{t: t+12}-\mathbb{E}_{t}\left[\Pi_{t: t+12}\right] \tag{8.11}
\end{equation*}
$$
  
I also construct a series of 12-month changes in inflation expectations
  
$$
\begin{equation*}
\Delta E_{t: t+12}=\mathbb{E}_{t+12}\left[\Pi_{t+12: t+24}\right]-\mathbb{E}_{t}\left[\Pi_{t: t+12}\right] \tag{8.12}
\end{equation*}
$$
  
For each asset class, I then construct realized real returns over 12-month periods by using the commonly used approximation ${ }^{2}$
  
$$
\begin{equation*}
R_{t: t+12}^{r} \approx R_{t: t+12}-\Pi_{t: t+12} \tag{8.13}
\end{equation*}
$$
  
[^36]To estimate each asset classes' exposure to inflation risk, I then regress these real returns on unexpected inflation and changes in expected inflation ${ }^{3}$
  
$$
\begin{equation*}
R_{t: t+12}^{r}=a+\beta_{\pi} U E_{t: t+12}+\beta_{\mathbb{E} \pi} \Delta E_{t: t+12}+e_{t: t+12} \tag{8.14}
\end{equation*}
$$
  
The two slope coefficients $\beta_{\pi}$ and $\beta_{\mathbb{E} \pi}$ capture exposure to the two types of inflation risk. For a real asset with zero exposure to inflation risk, we would expect $\beta_{\pi}=0$ and $\beta_{\mathbb{E} \pi}=0$. For a nominal asset we would expect $\beta_{\pi}<0$ and $\beta_{\mathbb{E} \pi}<0$.
  
Table 8.1: Inflation betas of asset classes
![400](Keep%20It%202024-10-24%2010.52.14.png)
Table (8.1) shows the results from these regressions for three asset classes: U.S. Treasury bonds with maturities between 5 to 10 years, the CRSP value-weighted stock market index, and gold. The data is from 1971 to 2023. The results in the table show stark differences across asset classes.
  
Real returns of long-term bonds have strong exposure to inflation risks. A one percentage point higher unexpected inflation is associated with 2.39 percentage points lower real return during the same period. A one percentage point rise in one-year inflation expectations is associated with 2.29 percentage points lower long-term bond returns! A rise in inflation expectations is terrible news for nominal long-term bond holders. The $R^{2}$ of this regression of $49 \%$ also highlights that unexpected inflation shocks and changes in inflation expectations together explain a large share of variation
  
[^37]in long-term bond returns. These were the key macro factors for long-term bond returns over the past five decades.
  
For the stock market index in Panel B the picture is more mixed. On the one hand, the estimated regression coefficients have the same direction as those for long-term bonds in Panel A, and the coefficient on unexpected inflation has a similar magnitude. On the other hand, the fact that the absolute value of the $t$-statistics are much smaller than the conventional statistical significance threshold of 1.96 highlights that the true coefficients could perhaps also be zero or somewhat positive. The coefficient on shocks to expected inflation is very close to zero. The much lower $R^{2}$ than in Panel A further shows that inflation risks just aren't a huge influence on stock returns. So there are some hints here that we could perhaps indeed view stocks as a real asset that is largely immune to inflation risks. But the picture is not entirely clear.
  
Panel C shows the results for gold. Gold has a positive exposure to both inflation risk factors. The $t$-statistics are both smaller than the usual threshold of 1.96, but the one on the expected inflation variable is very close and indicates significance at least at a $10 \%$ level. So there are some hints that gold not only provides real returns protected from inflation risk, but in addition, its real returns may have positive exposure to inflation risk factors, so that real returns are actually higher when inflation surges and lower when inflation declines. This may reflect that investors are willing to pay an extra insurance premium for real assets, or equivalently, tolerate a relatively low expected return, as a price of enjoying inflation protection when inflation surges.
  
Figure 8.4 illustrates the relationship of Treasury bond returns and gold returns to unexpected inflation in a bit more detail. The $x$-axis of these scatterplot shows the unexpected inflation realization $U E_{t: t+12}$ and the $y$-axis shows the real return. Interestingly, the relationships seem to be somewhat nonlinear, with bond returns particularly sensitive to unexpectedly low inflation and gold returns particularly sensitive to unexpectedly high inflation. When inflation surprised investors on the low side during the past 50 years, bonds earned big returns; when inflation surprised on the upside, gold prices rocketed. (For the stock market index, a similar scatterplot just shows a cloud without any clear relationship, so I did not add this plot.)
  
A few more thoughts on the question whether we should think of stocks as a real asset, and the somewhat mixed picture on this from Table (8.1). Part of the reason why the picture is mixed could be that the regression in Table (8.1) does not isolate pure inflation risk exposure. In the historical data, bursts of unexpected inflation, or changes in expected inflation, may have coincided with other macroeconomic news, e.g., about growth, that affected investors' expectations of real cash flows. For example, the stagflation episodes of the early 1980s may have led investors to believe that an unexpected rise in inflation will be countered by a recession-inducing and stock-price-
 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-277.jpg?height=1668&width=963&top_left_y=429&top_left_x=597)
  
Figure 8.4: Bond and gold returns and unexpected inflation
 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-278.jpg?height=901&width=1278&top_left_y=360&top_left_x=369)
  
Figure 8.5: Asset prices during German hyperinflation in 1923
Source: Braggion, F., von Meyerinck, F. and Schaub, N., 2022. Inflation and Individual Investors' Behavior: Evidence from the German Hyperinflation. University of St. Gallen, School of Finance Research Paper.
depressing hike in interest rates by the Federal Reserve. This may have contributed to the negative relationship between real stock market returns and unexpected inflation. The potential presence of such confounding factors makes it difficult to cleanly isolate the pure inflation risk exposure effect from the data.
  
One way of doing so is to look at episodes where the inflation shock was just so big that alternative confounding factors are just far too small in comparison to distort the picture. For example, we can ask how well stocks performed during episodes of hyperinflation. Did stock prices rise roughly in line with the CPI as one would expect for a real asset or did a stock market investor experience a substantial loss in purchasing power?
  
Figure 8.5 presents evidence from the German hyperinflation during the 1920s. The authors of this study hand-collected data on stock prices of several hundred stocks listed
on the Berlin stock exchange. The time series shown in the chart cover the period from start of 1920 until September 1923 during which the CPI in Germany (red solid line) rose by a bit less than 10 million times. As the figure shows, stock prices (blue solid line) rose largely in lockstep by the same factor. In contrast, nominal long-term bonds (4.5\% Deutsche Reichsschatzanweisung) of course did not rise at all and hence owners of these bonds basically experienced a total loss in real terms.
  
The last two months until the peak and end of inflation in November 1923 are missing in the authors' data (during these two months prices increased by a factor of 1000), but other studies have data that suggests that the stocks in Germany maintained much of their real value during these two months and the following currency reform. ${ }^{4}$
  
Overall, data from this hyperinflation episode provides strong support to the notion that stocks are a real asset and that stockholders' real wealth is largely protected against extreme rises in inflation. (That said, if hyperinflation were to trigger social unrest, revolution and expropriation, then stockholders would lose nevertheless.)
### 8.4 Inflation-protected bonds
While stocks may provide some protection from inflation risks, stocks of course are exposed to many other macroeconomic risk factors. A risk averse investor seeking inflation protection may prefer a bond-like investment that offers coupons and principal that are fixed in real terms rather than uncertain. In many countries, such inflation-protected bonds are now available. The U.S. Treasury started issuing Treasury Inflation Protected Securities (TIPS) in 1997. The British government has issued inflation-protected bonds since 1981 .
  
Here is how TIPS work. Coupon and principal of TIPS are not fixed in nominal terms, but they grow with the CPI, as measured by the CPI three months before the coupon or principal payment date. For example, suppose a 10-year TIPS is issued at the end of month $t$ with a 10-year maturity. For simplicity, suppose the principal value is 1$ and the coupon payments occur every 12 months (instead of the actual semi-annual payment frequency) at a coupon rate of $c^{r} \%$. This coupon rate specified in the terms of TIPS is a real coupon rate. Then the first coupon payment in month $t+12$ in nominal terms will be
$$
\begin{equation*}
c^{r} \times $ 1 \times \frac{C P I_{t+9}}{C P I_{t-3}} \tag{8.15}
\end{equation*}
$$
  
[^38]The coupon payment a year later will be
  
$$
\begin{equation*}
c^{r} \times $ 1 \times \frac{C P I_{t+21}}{C P I_{t-3}} \tag{8.16}
\end{equation*}
$$
  
and so on, and then the final payment of principal and coupon,
  
$$
\begin{equation*}
\left($ 1+c^{r} \times $ 1\right) \times \frac{C P I_{t+117}}{C P I_{t-3}} \tag{8.17}
\end{equation*}
$$
  
This means that at time $t$ the future nominal cash flows of TIPS are uncertain. They depend on the yet-unknown future values of the CPI. But the real cash flows are essentially certain. The reason why I write 'essentially' is that there is a little deviation from truly fixed and certain real cash flow values due to the fact that the indexing is to the CPI three months before and not the CPI during the measurement month. (The reason for this lag is the practical issue that the CPI first needs to be calculated and published before it can be used to adjust coupon and principal payments). Without this imperfection, deflating the coupon and principal payments with the CPI at the time of the payments would lead to real cash flows, expressed in time $t$ dollars, that are $c^{r} \times  1$ before maturity, and $\left( 1+c^{r} \times  1\right)$ at maturity. In the following discussion, we ignore the slight timing mismatch between CPI measurement and payment dates and we assume that TIPS cash flows are fixed and certain in real terms. ${ }^{5}$
  
TIPS are immune to both types of inflation risk we discussed above. If the current CPI unexpectedly goes up by $x \%$, then all future coupons and principal payments will be $x \%$ higher in nominal terms, but in real terms they remain unchanged, hence the real value of TIPS stays unchanged and there is no loss of purchasing power. If current expectations of future inflation go up by $x$ percentage points per year until bond maturity, coupon payments and the outstanding principal amount are expected to grow by an additional $x$ percentage points more per year in nominal terms, but in real terms they will stay the same. Hence, the real value of TIPS stays unchanged and there is no loss of purchasing power.
  
Therefore, the value of TIPS then reflects the fixed real cash flows discounted at a real yield-to-maturity. For example, the 10-year real yield-to-maturity $Y_{10, t}^{r}$ is the real discount rate that makes the discounted real cash flows of 10-year TIPS equal to the price of 10-year TIPS:
  
$$
\begin{equation*}
P_{10, t}=\left(\sum_{k=1}^{10} \frac{c^{r}}{\left(1+Y_{10, t}^{r}\right)^{k}}\right)+\frac{1}{\left(1+Y_{10, t}^{r}\right)^{10}} \tag{8.18}
\end{equation*}
$$
  
[^39] ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-281.jpg?height=823&width=1183&top_left_y=304&top_left_x=493)
  
Figure 8.6: Real yields extracted from TIPS prices
  
So by observing TIPS prices, we can directly observe real yields! Given $P_{10, t}$, we can extract the real yield $Y_{10, t}^{r}$. We can also do this for other maturities and get a real yield curve.
  
Figure 8.6 shows the real yields extracted from 5- and 10-year TIPS. While real yields were between 1 and 2 percent prior to the Great Financial Crisis (GFC) in 2008/09, real yields after the GFC spent extended periods of time in negative territory. It is unusual for nominal yields to be negative since investors could also hold money as zero-interest cash instead of bonds. ${ }^{6}$ But there is nothing necessarily unusual about real yields turning negative if the inflation rate is above zero. A zero-interest deposit account or holding paper money would also have a negative real return in this case.
  
The figure also shows that the 10-year real yield tends to be above the 5 -year real yield. This suggests that the real yield curve may be upward-sloping on average, like the nominal yield curve. Evidence from the U.K. where a longer history of real yields is available than in the U.S. indicates that the real yield curve may be flatter than the nominal yield curve. How big the wedge is between the slopes may depend on whether we are in an inflationary environment or not. If inflation risk is high, long-term nominal bonds are risky, as our analysis showed earlier, and so it makes sense that investors would ask for an additional risk premium, in the form of additional yield, for long-term nominal bonds compared with inflation-protected bonds that are not exposed to inflation risk.
  
[^40] ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-282.jpg?height=822&width=1180&top_left_y=302&top_left_x=429)
  
Figure 8.7: Breakeven inflation rates extracted from TIPS prices
  
The spike of real yields in Figure 8.6 in the fall of 2008 highlights a potential problem with TIPS. TIPS are not as liquid as regular Treasury bonds. In the fall of 2008, some big investors liquidated large positions in TIPS that lead to depressed prices of TIPS and the spike in real yields that we see in the figure. This was a time when the economy entered a deep recession and the Fed had rapidly lowered short-term interest rates. It would be very unusual for real interest rates to go up in such an environment. But these real yields from TIPS at the time were distorted due to the price pressure of these liquidations in an illiquid market.
  
The fact that we can back out real yields from TIPS prices brings us to another very useful piece of information we can extract from TIPS and regular Treasury bonds jointly: A measure of expected inflation!
  
The price of 10-year nominal Treasury bond reflects the fixed nominal cash flows discounted at a nominal yield-to-maturity $Y_{10, t}$ :
  
$$
\begin{equation*}
P_{10, t}=\left(\sum_{k=1}^{10} \frac{c}{\left(1+Y_{10, t}\right)^{k}}\right)+\frac{1}{\left(1+Y_{10, t}\right)^{10}} \tag{8.19}
\end{equation*}
$$
  
and the difference between the nominal yield extracted from regular Treasury bond prices and the real yield extracted from TIPS is known as breakeven inflation:
  
$$
\begin{equation*}
\text { Breakeven inflation }=Y_{10, t}-Y_{10, t}^{r} \tag{8.20}
\end{equation*}
$$
  
It's called breakeven inflation because when inflation is higher than the breakeven inflation rate over the time until maturity of the bonds, TIPS will have earned a higher return; if inflation is lower, regular Treasury bonds will have done better.
  
This also shows why we can interpret breakeven inflation as a measure of the inflation expectations that investors must have. When they price TIPS and regular Treasury bonds, they should price them such that both of them are an ex-ante equally attractive investments. The nominal yield on regular Treasury bonds should be the real on TIPS plus the average inflation rate that investors expect over the 10 years until the bonds mature.
  
There is one qualification though. While breakeven inflation may be a good approximate measure of inflation expectations, they are unlikely to be an exact measure because investors may also demand a risk premium for the inflation risk of regular Treasury bonds, i.e., the nominal yield has an inflation risk premium component that real yields of TIPS don't have:
  
$$
\begin{equation*}
Y_{10, t}=Y_{10, t}^{r}+\text { expected inflation }+ \text { inflation risk premium } \tag{8.21}
\end{equation*}
$$
  
This means that
  
$$
\begin{equation*}
\text { Breakeven inflation }=\text { expected inflation }+ \text { inflation risk premium } \tag{8.22}
\end{equation*}
$$
  
The reason why the inflation risk premium shows up in breakeven inflation is that nominal Treasury bonds and TIPS are not the same type of asset, so the nominal yield that we compare with a real yield in the calculation of breakeven inflation are yields of two different types of assets that investors consider to be different in terms of their riskiness with respect to inflation: Nominal bonds are exposed to inflation risk while TIPS are not. However, empirical estimates suggest that relative to the magnitude of expected inflation, the inflation risk premium is relatively small. So it's not a bad approximation to use breakeven inflation as a proxy for investors' inflation expectations. (Price distortions of TIPS due to illiquidity like in 2008 are a bigger problem).
  
Breakeven inflation has significant advantages compared with survey-based inflation expectations measures. First, it is based on market prices and investors have stronger incentives to get their forecast "right" than the respondents in surveys. Second, breakeven inflation is available at high frequency. Based on TIPS prices, we can therefore observe inflation expectations at daily or even higher frequency. Third, there is a whole term structure of breakeven inflation rates based on the outstanding maturities of TIPS. So we can see investors' views about future inflation over short and long horizons.
  
In terms of seeing how investments in TIPS and Treasury bonds perform in a relative comparison, comparing individual bonds directly is somewhat cumbersome because an investor aiming at bond positions within a certain maturity range would typically roll over a portfolio of bonds. Conveniently, there are TIPS and Treasury bond ETFs that allow us to track the performance of such regularly rebalanced portfolios easily. I will show data for two ETFs: The Schwab U.S. TIPS ETF (ticker SCHP), one of the largest TIPS ETFs, that holds TIPS with average maturity around 7 years. For comparison, I look at the Vanguard Intermediate-Term Treasury ETF (ticker VGIT), which holds regular Treasury bonds with average maturity around 6 years. We can use the ETF data to study how well a TIPS investment would have protected a bond investor from the rapid rise in inflation that the U.S. experienced following the COVID pandemic.
  
Figure 8.8a shows the investment experience in real terms of an investor in the two ETFs. For this analysis, I invest 1$ in each ETF at the beginning in 2010. I then track the value of this investment (with reinvested dividends). Over the entire sample period, the investment in the TIPS ETF grew to slightly less than 1.20$ in real terms (i.e., after deflating by the CPI). In contrast, the investment in Treasury bonds almost did not grow at all in real terms over the full period. This wedge in performance indicates that over this 12-year period, inflation must have been higher than the inflation expectations, i.e., breakeven inflation, that were priced into the prices of TIPS and regular Treasury bonds initially.
  
The figure also shows that the performance advantage of TIPS started showing up around 2012 and later disappeared, before it reappeared very strongly at the end of the period starting in 2020. Figure 8.8 b shows that this lines up well with the path of inflation rates that realized during these years: Around 2012 there was a strong rise in inflation rates that subsequently disappered, with inflation falling to very low levels around 2014. And then there was the very strong re-emergence of inflation after 2020. Both unexpected inflation was high and expected inflation rose during this period, and both eroded the real value of regular Treasury bonds while the real value of TIPS stayed unaffected.
  
### 8.5 Portfolio optimization in real terms
  
An investor aiming to optimize risk and return in terms of the purchasing power that investments eventually provide should optimize the portfolio in terms of real returns. This can still be done with the same mean-variance optimization framework that we
 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-285.jpg?height=1605&width=969&top_left_y=458&top_left_x=600)
  
Figure 8.8: TIPS and regular Treasury Bond ETF cumulative performance
discussed in earlier lectures, but with some modifications. In the following, consider a long-term investor wants to maximize the expected utility of real wealth in $h$ periods by trading off expected real return on wealth against the variance of the real return. Let's assume the investor wants to combine a risky asset with a risk-free asset with a fixed-weight strategy like the one we analyzed in lecture 5 , but now with a focus on real returns.
  
As in lecture 5 , we will work with $\log$ returns here. Let $r_{t}$ be the log nominal return and $\pi_{t}=\log \left(1+\Pi_{t}\right)$ the $\log$ inflation rate. Then the log real return is
  
$$
\begin{equation*}
r_{t}^{r}=\log \left(\frac{1+R_{t}}{1+\Pi_{t}}\right)=r_{t}-\pi_{t} \tag{8.23}
\end{equation*}
$$
  
In our analysis, we will also need the log real yield of TIPS, which is, for TIPS with maturity $n$,
  
$$
\begin{equation*}
y_{n, t}^{r}=\log \left(1+Y_{n, t}^{r}\right) \tag{8.24}
\end{equation*}
$$
  
More precisely, assume that this log real yield $y_{n, t}^{r}$ is a zero-coupon log real yield extracted from the prices of TIPS.
  
Recall that in lecture 5 the solution to the optimal portfolio problem for the fixedweight strategy and horizon $h$ was
  
$$
\begin{equation*}
\omega=\frac{\mathbb{E}\left[r_{t+1}\right]-r_{f}+\frac{1}{2} \operatorname{var}\left(r_{t: t+h}\right) / h}{\gamma \operatorname{var}\left(r_{t: t+h}\right) / h} \tag{8.25}
\end{equation*}
$$
  
where $r_{f}$ was a nominal risk-free rate and $\operatorname{var}\left(r_{t: t+h}\right)$ was the variance of the longterm log portfolio return, also in nominal terms. The investor then needs make several adjustments to our approach in lecture 5 to do the optimization in real terms.
  
The first adjustment concerns the risk-free rate to be used. When the investor cares about real, not nominal returns, a nominally risk-free asset like Treasury bond is not risk-free in real terms. In the presence of inflation risk, the real return on Treasury bonds is uncertain, even if the maturity of the bond exactly matches the optimization horizon. Instead, for the investor with a $h$-year horizon, TIPS with $h$ years of remaining maturity would be virtually risk-free and hence the real yield of these securities can then be used as the real risk-free rate over this horizon. Now, as TIPS pay coupons semi-annually and hence TIPS with $h$ years of remaining to maturity are not exactly a $T$-year zero-coupon bond, which creates a slight mismatch with the optimization horizon of $h$ years. So let's assume the investor can invest in a real zero-coupon bond that offers a log real yield of $y_{h, t}^{r}$ with maturity $h$ matched to the investor's horizon. This is the risk-free asset for this investor and $y_{h, t}^{r}$ should therefore replace $r_{f}$ in (8.25).
 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-287.jpg?height=938&width=1348&top_left_y=298&top_left_x=405)
  
Figure 8.9: Treasury bill yields and inflation
  
There is a potential alternative to using TIPS yields: A strategy of rolling over an investment in short-term T-bills (say, 3-month T-bills) over a longer horizon is not as low risk in real terms as a TIPS investment, but it actually gets quite close. As we discussed in the last lecture, the Federal Reserve tends to raise short-term interest rates if it sees inflation rise. As a consequence, when inflation rises, an investment in a 3-month T-bill will initially suffer a loss of real value when inflation rises after the T-bill was purchased, but already in the next quarter, the yields on T-bills may have gone up to compensate for the higher inflation rate. As a consequence, the real loss of wealth remains small. Figure 8.9 shows the strong comovement of 3 -month T-bill yields and inflation in most of the previous decades. The most recent years since the onset of the COVID pandemic have been somewhat of an exception: Here the Federal Reserve was unusually slow in responding to the rise in inflation with raising short-term interest rates. To the extent one accepts the rolling-over-T-bills strategy as safe in real terms, one can use the average historical real return of this strategy as a proxy for $y_{h, t}^{r}$.
  
The optimal portfolio share for the investor concerned about risk and return in real terms then is
  
$$
\begin{equation*}
\omega=\frac{\mathbb{E}\left[r_{t+1}^{r}\right]-y_{h, t}^{r}+\frac{1}{2} \operatorname{var}\left(r_{t: t+h}^{r}\right) / h}{\gamma \operatorname{var}\left(r_{t: t+h}^{r}\right) / h} \tag{8.26}
\end{equation*}
$$
  
now with $y_{h, t}^{r}$ as the risk-free rate and with long-term variance of real returns var $\left(r_{t: t+h}^{r}\right)$.
How to estimate expected excess returns in this case? Given that the investor cares about real returns and the relevant real risk-free rate is now $y_{h, t}^{r}$, the investor needs an estimate of $\mathbb{E}\left[r_{t+1}^{r}\right]-y_{h, t}^{r}$. One possibility would be to calculate realized log real risky asset returns in historical data by subtracting realized log inflation each period and taking the average to estimate $\mathbb{E}\left[r_{t+1}^{r}\right]$. But average real yields may have been different in the past than what they are currently, and so a better approach may be to focus on average excess returns to estimate $\mathbb{E}\left[r_{t+1}^{r}\right]-y_{h, t}^{r}$. One could estimate this expected excess return by calculating the average difference between real returns on the risky asset and real returns of TIPS of maturity $h$ (or, ideally, $h$-year zero-coupon bond real returns implied by TIPS returns) in historical data. Equivalently, one could look at the average difference of the nominal return on the risky asset and the nominal return on TIPS.
  
One problem with this approach is that the available data series of TIPS returns are still quite short as the TIPS market did not exist before 1997. To the extent that T-bills rolled over are actually a reasonably good risk-free asset in real terms for a long-term investor, one could also look at the average difference between nominal returns on the risky asset and the nominal return on T-bills-i.e., exactly what we were doing in lecture 5 when we focused on nominal returns.
  
Finally, the investor needs an estimate of the variance of long-run real returns $\operatorname{var}\left(r_{t: t+h}^{r}\right)$. Here, too, one could potentially just look at the variance of realized log risky asset returns adjusted for inflation. That said, if we look back at historical data, real yields have varied over time, and so the best estimate of what var $\left(r_{t: t+h}^{r}\right)$ will be going forward may be one that looks at the variance of the excess real return over and above real yields. Since real yields don't vary all that much, this should not make all that much difference, though, for most risky asset classes.
  
But there is again the issue that real yield data is not available for long historical time periods. To the extent that T-bills provide reasonably good protection from inflation risk, the real return of rolled-over T-bills could again be an alternative series to look at. For example, one could use historical data to calculate the variance single period (e.g., quarterly) nominal returns of the risky asset relative to nominal yields of T-bills, possibly adjusted for a potential long-term variance-reducing effect of negative serial correlation if such negative serial correlation exists, to get the implied estimate of $\operatorname{var}\left(r_{t: t+h}^{r}\right) / h$.
  
With multiple risky assets, estimation of covariances could be done analogously to the variance estimation discussed above, e.g., with the covariances of nominal risky asset returns relative to T-bill yields as proxy for the covariances of real returns in excess of real yields.
  
### 8.6 Inflation in foreign countries
  
For a U.S. investor, a rise in the U.S. inflation rate leads to a loss of purchasing power, unless the assets are hedged against U.S. inflation risk. But if the portfolio includes foreign assets, what does foreign inflation do to the real value of the U.S. investor's portfolio? To be concrete, suppose that the U.S. investor owns a foreign government bond with nominally fixed cash flows in foreign currency. The investor's purchasing power depends on the nominal dollar value of the bond deflated by the U.S. consumer price index. Hence, foreign inflation does not directly reduce the purchasing power that the U.S. investor gets from this bond. But foreign inflation is likely to have an effect on the exchange rate that reduces the value of the foreign bond in terms of U.S. dollars, and thereby affects the investor's purchasing power indirectly.
  
Let $S_{t}$ be the exchange rate in terms of units of foreign currency that must be paid to get 1$. A theory of exchange rates called purchasing-power parity (PPP) says that exchange rates should reflect the different levels of purchasing power that currencies have. The idea is that in an ideal world in which trade is frictionless, the prices of goods and services should be the same across countries once they are expressed in the same currency,
  
$$
\begin{equation*}
S_{t}=\frac{C P I_{\text {foreign }}}{C P I_{U S}} \tag{8.27}
\end{equation*}
$$
  
so if prices in local currency are higher in the foreign country, one should have to pay more than one unit of foreign currency to obtain 1$ so that the exchange rate undoes the differences in price levels. In terms of exchange rate changes over time, we then get
  
$$
\begin{equation*}
\frac{S_{t+1}}{S_{t}}=\frac{1+\Pi_{\text {foreign }, t+1}}{1+\Pi_{U S, t+1}} \tag{8.28}
\end{equation*}
$$
  
so exchange rate changes should reflect differentials in inflation rates. (Equation (8.28) is actually more general than equation (8.27) because it also holds if there is a constant wedge in purchasing power of the two currencies, e.g., due to different levels of economic development. This would lead to a constant factor multiplying the right-hand side of (8.27), which drops out after taking the ratio of exchange rates in different periods in (8.28).)
  
Now, the empirical evidence does not suggest that (8.28) is a great description of how exchange rates behave in the short run. But over longer periods, PPP helps understand exchange rate movements. ${ }^{7}$ PPP provides a good guide to exchange rate movements during hyperinflation episodes.
  
[^41] ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-290.jpg?height=915&width=1327&top_left_y=315&top_left_x=361)
  
Figure 8.10: Inflation and exchange rate to USD in Turkey
  
A recent example is the hyperinflation that started in Turkey in 2022. Figure 8.10 plots the consumer price index in Turkey since 2017. Prices more than quadrupled during the seven years shown in the plot, a rise by about $350 \%$, which means the local purchasing power of the Turkish lira fell by about $78 \%$. The same plot also shows the exchange rate, expressed in units of Turkish lira per 1$. As the purchasing power of the lira fell, the exchange rate depreciated strongly from around $1 / 4=0.25$ dollars per lira down to $1 / 27=0.037$ dollars per lira, which is a lira depreciation of about $85 \%$, which is roughly in the same ballpark as the loss of purchasing power of the lira, and hence roughly in line with (8.28).
  
The consequences of the Turkish inflation for an U.S. investor holding Turkish bonds is that the dollar value of these bonds has fallen by a large percentage. So foreign inflation risk is highly relevant for the U.S. investor, but it manifests indirectly through exchange rate movements.
  
### 8.7 Economic causes of inflation
  
To understand how inflation risk may materialize, we need to understand the economic causes of inflation. Most macroeconomic models of inflation suggest that the following factors influence inflation.
  
Output gap: Recall from the last lecture that the output gap measures the level of GDP or employment relative to the economy's maximum current capacity. Situations in which the economy is operating close to capacity, and hence the output gap small, gives firms more room to raise prices and workers more bargaining power to demand wage rises.
  
Cost-push shocks: These are shocks that drive up firms marginal cost of production. The supply chain problems that the U.S. economy experienced in the wake of the COVID pandemic are an example of such shocks. The huge increase in energy prices in some parts of the world following the start of the war in Ukraine in 2022 are another example.
  
Inflation expectations: The reason why expectations of future inflation can generate current inflation are more subtle than the more intuitive output gap and cost-push shock channels. Among other things, the expectations channel reflects the forward-looking nature of firms' price setting coupled with frictions in how often prices are revised. Consider two parties negotiating a long-term contract that fixes prices for the delivery of some goods over the next year. If the seller anticipates that prices will rise during the next year, the seller will demand that the long-term contract fixes higher prices already today. In this way, expectations of future inflation can lead to upward pressure on prices already today. So there can be a self-fulfilling aspect to inflation expectations. If everyone expects high inflation it's likely that inflation is pushed higher. The same mechanism can apply in wage negotiations if a contract to be negotiated fixes wages over a certain term into the future.
  
Central banks, tasked with ensuring price stability, worry about this expectations effect because a mere change in people's beliefs about the future could generate inflation. Possibly, inflation could be completely self-fulfilling. Then if people expect $10 \%$ inflation going forward, this generates current inflation of $10 \%$; if people will expect $100 \%$ going forward, this generates current inflation of $100 \%$; and so on. Any level of current inflation could arise. Put differently, if such self-fulfilling dynamics take hold, inflation will be extremely unstable and could easily explode. Once this happens, it would take big changes in interest rates to generate a big output gap, i.e., a deep recession, to counteract this self-fulfilling inflationary dynamic.
  
This is why central banks put a lot of emphasis on stabilizing, or anchoring, inflation expectations. If the central bank can convince people that it will always take action
to quickly bring inflation back to the target rate of inflation, then people's inflation expectations may stay close to the the central bank's inflation target $\Pi^{*}$, irrespective of the shocks that hit the economy. In particular, the self-fulfilling inflationary dynamics are not going to start. As a consequence, the central bank can then counteract output gap and cost-push shocks with relatively small changes in interest rates, i.e., without causing a deep recession.
  
How can central banks achieve anchored inflation expectations? In a central banker's ideal world, public statements of central bankers would be perfectly credible. If so, the central bank could just announce what its inflation target is and people would immediately adjust their expectations to $\mathbb{E}_{t}\left[\Pi_{t+1}\right]=\Pi^{*}$.
  
In practice, influencing expectations is a bit more difficult, especially if people had recent experiences with high inflation rates. To convince people that inflation will actually come down in the future, after an experience of high inflation over an extended period to time, they often need to see some action by the central bank that actually brings inflation down for a while before they are convinced that low inflation will prevail in the future. Beliefs shaped by personal experiences are not easy to overcome.
  
That people have a tendency to rely on past experiences in forming their views about future inflation (rather than, say, just adopting the guidance provided by central bankers' announcements) is actually not that easy to tease out from the data. If we look at the time-series of the average or median individual's expectation of future inflation and their correlation with past inflation rates, it's hard to disentangle whether past inflation rates are correlated with the average individual's expected inflation rate simply because individuals correctly predict (e.g., based on what they hear from central bankers, and other experts) that inflation will persist into the future, or whether individuals rely too much on their past experiences in forming their expectations.
  
But if we look at heterogeneity in individuals' expectations, we can clearly see the experience effects at work. In a research project some years ago, my co-author Ulrike Malmendier and I showed that people's inflation expectations are heavily shaped by their life-time experiences of inflation. This is clearly visible as age-heterogeneity in inflation expectations. Younger people's expectations are influenced by more recent data while older individuals' expectations are influenced by data from earlier years because their lifetime experiences stretch farther back into the past. The expectations of young and old therefore differ. For example, after a surge in inflation rates, young people's lifetime experience is quickly dominated by these high inflation rates, leading them to forecast higher future inflation rates. In contrast, older people average these recently high inflation rates with a larger set of historical experiences, and so the reaction of their expectations to this surge is more muted.
 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-293.jpg?height=1012&width=1435&top_left_y=605&top_left_x=367)
  
Figure 8.11: Differences in inflation expectations by age
One-year inflation expectations of age groups in excess of the cross-sectional mean across age groups each period. Data from the Michigan Survey of Consumers. Until 2009Q4: Malmendier, U. and Nagel, S., 2016. Learning from inflation experiences. Quarterly Journal of Economics, 131(1), pp.53-87; out-of-sample periods after 2009Q4 are updates post-publication. Solid lines show inflation forecasts from an $\mathrm{AR}(1)$ model estimated on each age group's lifetime data of inflation.
  
Figure 8.11 presents the evidence for these sorts of life-time experience effects in the Michigan Survey of Consumers, a monthly survey that has been conducted for many decades. The small circles show the average inflation expectation every quarter of people in three age groups: young (age $<40$ ) in blue, middle-aged $(40 \leq a g e \leq 60)$ in red, older people (age $>60$ ) in black. To focus purely on cross-sectional differences at each point in time between these age groups, the figure shows the inflation expectations relative to the overall cross-sectional mean of everyone's inflation expectation at that point in time. In other words, when a group shows up with a value above zero in this plot, it means that this group has above-average inflation expectations in this period; if it shows up below zero, it has below-average inflation expectations in this period.
  
Examining the plot, we see that as inflation rates were rising throughout the 1970s until the early 1980s, a gap opens up between young and old. By 1981, around the time inflation peaked, younger individuals expected about 3 percentage points higher inflation over the next year than older individuals. Over the following decades, this gap closed and eventually reverted. In the noughties, the gap turned negative. In the noughties, older individuals had higher inflation expectations than younger individuals, consistent with the memory of the high inflation in the 1970s that is absent in younger individuals' life-time experience.
  
The solid lines in the figure show the inflation prediction that comes out of a model in which each birth cohort of individuals forms inflation expectations by estimating an $\mathrm{AR}(1)$ model of the inflation rate using inflation data that they have seen during their lifetimes. These solid lines match quite well the opening of the gap between young and old in the 1970s/80s, and the subsequent closing of this gap and eventual reversal. This means that we can approximately understand people's inflation expectations as being informed by the mean and persistence of the inflation rates that they have experienced during their lifetimes.
  
From a central banker's viewpoint, the fact that we see these experience-dependent differences between young and old means that experiences exert a force that is not so easy to overcome just with words and announcements. Moreover, the unanchoring of inflation expectations that central bankers are typically worried about is likely to happen more quickly for younger individuals. ${ }^{8}$ On the other hand, once expectations of the general population have become unanchored, it will be particularly difficult to re-anchor those of older individuals because a few quarters of low inflation will do little to alter their extensive set of historical experiences.
  
[^42]
 ![500](Keep%20It%202024-10-24%2010.52.29.png)

=
  
Source: Young \[36, vol. 2, p. 393].
Figure 8.12: Government budget in Germany in years leading up to 1923 hyperinflation Source: Sargent, T.J., 1982. The ends of four big inflations. In Inflation: Causes and effects (pp. 41-98). University of Chicago Press.
  
It's good news for the Federal Reserve that a big unanchoring of inflation expectations has not happened yet following the recent surge of inflation in 2022. The breakeven inflation rates in Figure 8.7 shows that the bond market prices in somewhat higher expected inflation, but this is still far from the expected inflation rates of around $10 \%$ that were registered the last time inflation surged in the early 1980s.
  
### 8.8 Fiscal crises and inflation
  
The macroeconomic forces influencing inflation that we discussed so far may explain quite well how inflation is determined in times when the economy is exposed to moderatelysized shocks, the general economic policy environment is functioning well, and the central bank can stay focused on its job of stabilizing the economy.
  
In more extreme situations, however, there is a risk in the background that the central bank may be drawn away from the job of stabilizing the economy towards supporting a fiscally challenged government. A condition for the central bank to be able to carry out [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] that stabilizes the economy and inflation is that the government pursues a sound fiscal policy. If the government gets into a budget crisis, or even if investors just anticipate that it might, the central bank may be forced into supporting government finances.
  
Many big inflationary episodes in history occurred in situations when the country's government was in fiscal trouble. As a typical example, the table in Figure 8.12 shows the budget situation of Germany's government in the years leading up to the hyperinflation in 1923. The numbers are shown in millions of goldmarks, which was a gold-backed money in use in Germany at the time (and which did not lose real value during the hyperinflation). In parallel, there was fiat money (which lost all its real value) that the central bank printed in massive amounts to finance the government's budget deficit. As the table shows, in the 1922-23 fiscal year, about two thirds of government expenditure was financed by government borrowing.
  
Selling bonds becomes difficult for the government as investors start doubting the ability of the government to honor its debt. Historically, when this happened, it often led to the central bank stepping in to buy bonds or bills issued by the government and paying for it with newly printed money. This is what happened in Germany in the years leading up to the hyperinflation. In modern economies, this would not involve actual printing of paper money, but a rise in the aggregate amount of bank deposits and the aggregate amount of reserves that banks hold in their account at the central bank. When the central bank buys government debt from investors and pays for it with reserves, then investors get more money in their bank accounts, and the investors' banks will in turn see their reserve deposits at the central bank go up.
  
But just like government bonds, money in paper form, or in the form of bank deposits backed by reserve deposits at the central bank, is ultimately backed by the willingness of the government to raise sufficient taxes relative to expenditure to support the value of these claims. If households and firms no longer believe that this is the case, they will not like holding on to large amounts of money. They will try to exchange money for items that are more likely to keep their value if the government fails to honor its commitments: real estate, stocks, durable goods, foreign assets, etc. The consequence of this desire to spend money quickly is a rise in prices, which in turn may generate higher expected future inflation, which can in turn further fuel current inflation.
  
Fiscal reforms that bring the budget back into balance have been key in ending many hyperinflations in history. The table in Figure 8.13 shows how dramatically the German government budget swung into surpluses in the months after the hyperinflation. Tangible signs that the government was committed to this path of ending deficits (by raising taxes, taking action to cut expenditure, renegotiation of war reparation payments) helped convince people that they can hold on to their money and bank deposits without trying to get rid of them like a hot potato. Also keep in mind that the hyperinflation reduced the outstanding government debt to a real value of effectively zero. So fiscal consolidation required only bringing current and future revenues in line with expenditure, it did not require making large payments in real terms to previous debtholders.
  
## Table G5 Ordinary Revenues and Expenditures of the German Federal Government (from Wirtschift and Statistik, issued by the Statistisches Reichsamt, in millions of gold marks)
  
|  | Ordinary Revenue |
| :--- | :---: | :---: | :---: | :---: |
  
Source: Young [36, vol. 1, p. 422].
Figure 8.13: Government budget in Germany in months after hyperinflation ended Source: Sargent, T.J., 1982. The ends of four big inflations. In Inflation: Causes and effects (pp. 41-98). University of Chicago Press.
 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-298.jpg?height=988&width=1338&top_left_y=308&top_left_x=361)
  
Figure 8.14: Treasury yields (3-month and 10-year maturity) around March 2020
Source: He, Z., Nagel, S. and Song, Z., 2022. Treasury inconvenience yields during the covid-19 crisis. Journal of Financial Economics, 143(1), pp.57-79.
  
Many other hyperinflations in history, e.g., several in Latin America in the second half of the 20th century, show similar connections to fiscal turmoil in the rise of inflation and fiscal consolidation in the eventual end of inflationary episodes.
  
While these historic episodes may not be immediately relevant for developed markets in the current environment, some recent events during the COVID pandemic show at least a qualitative similarity with budget deficits, jittery bond markets, large-scale bond purchases by the central bank, higher inflation, and some investors looking for ways to preserve their purchasing power. The situation was far, far less dramatic, but still, perhaps some caution is warranted.
  
The COVID pandemic lead to government programs that strongly increased government budget deficits. Somewhat surprisingly, in March 2020 the U.S. Treasury bond market seemed to have trouble digesting the high supply of Treasury bonds. During several days in March 2020, long-term Treasury bond yields rose, even though the Fed lowered interest rates and short-term yields came down strongly, as shown in Figure 8.14.
 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-299.jpg?height=958&width=1332&top_left_y=323&top_left_x=424)
  
Figure 8.15: Federal Reserve Treasury holdings in 2020 ($bn.)
Source: He, Z., Nagel, S. and Song, Z., 2022. Treasury inconvenience yields during the covid-19 crisis. Journal of Financial Economics, 143(1), pp.57-79.
  
Compared to other historical episodes of market turmoil in response to bad economic news, this reaction of Treasury yields was highly unusual. The usual crisis pattern was that Treasury bond yields would fall strongly in anticipation of steep interest rate cuts by the Federal Reserve.
  
The Federal Reserve then quickly stabilized the situation toward the end of March by starting a massive bond purchase program. As Figure 8.15, the Fed added around 1.5 trillion dollars worth of bonds to its balance sheet within a few weeks. And the Fed kept these bonds on its balance sheet even after the crisis subsided. It is not clear what the effect on Treasury yields would have been if the Fed had tried to sell these bonds back to the public in the months following the crisis episode.
  
The bottom line from all this is that to judge whether inflation risk might emerge, it's important to keep an eye on fiscal conditions in addition to the central bank's conduct of [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]].
 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-300.jpg?height=706&width=1180&top_left_y=319&top_left_x=424)
  
Figure 8.16: Share of countries in a given year that are in external or internal default
Source: Reinhart, C.M. and Rogoff, K.S., 2011. The forgotten history of domestic debt. The Economic Journal, 121(552), pp.319-350.
  
### 8.9 Fiscal crises and sovereign default
  
When governments get into a fiscal crisis and have much of their debt denominated in domestic currency, inflation is the typical consequence of fiscal crisis. In principle, governments could also choose the path of defaulting on their debts, but monetary financing and inflation are much more common for dealing with large domestic debts.
  
Looking at the world history of such crises, the solid line in Figure 8.16 shows what the authors call "Composite Probability of Domestic Default": this is the share of countries in a given year that have either high inflation (above 20\%) or are in a state of default on their domestic debt. ${ }^{9}$ The vast majority of these cases are hyperinflations, not default.
  
In contrast, when a government has external debt, denominated in foreign currency, inflation does not reduce the real value of the debt. If inflation takes off strongly, the exchange rate will collapse, so that the value of the foreign debt expressed in domestic currency rises. Inflation therefore cannot resolve a fiscal crisis. So for external debts,
  
[^43]governments choose the path of default instead. As the dashed line in Figure 8.16 shows, there are time periods when a large share of countries in the world are in a state of default on external debt, including the 1980s when many developing countries experienced fiscal crises and default.
  
When a bond is at risk of default, investors reduce the price they are willing to pay. This raises the yield of the bond and as a compensation for the risk of default. To be concrete, consider the following example. Outstanding debt is in the form of a zero-coupon bond with principal of 1$ and maturity in one period. The probability that the government will default is $10 \%$. Suppose that if the government defaults, it will restructure the debt so that bond holders obtain a value that is worth only $40 \%$ of the principal that they are owed. Hence, the recovery rate is $40 \%$, or the loss given default is $1-0.40=60 \% .{ }^{10}$ Suppose that investors price default-free bonds to earn a yield of $5 \%$.
  
Let's first consider the case of risk-neutral investors. Risk-neutral investors would price this bond subject to default risk at the expected payoff discounted at the defaultfree yield,
  
$$
\begin{equation*}
P=\frac{0.90 \times $ 1+0.10 \times $ 0.40}{1+0.05}=$ 0.8952 \tag{8.29}
\end{equation*} $$
which means that the promised yield is \$1 / 0.8952-1=11.71 \%$. It's called the promised yield because this is what the borrower promises to pay, but the investor (fully) earns it only if the issuer does not default on the obligations of the bond. The higher the default probability, and the lower the recovery rate, the lower the price.
  
The credit spread relative to the default-free yield, \$11.71 \%-5 \%=6.71 \%$ is the additional yield that the investor earns in the event that there is no default. This additional yield the investor earns in the no-default case is compensation for the losses the investor will experience if there is default. In the case of risk-neutral investors that we are considering here, the magnitude of the credit spread is exactly equal to the expected loss as a percentage of the price of the bond:
  
$$
\begin{equation*}
0.1 \times \frac{0.60}{0.8952}=6.71 \% \tag{8.30}
\end{equation*}
  
Despite the elevated credit spread, the expected return on this risky bond is the same as the default-free yield,
  
$$
$$\begin{equation*}
\mathbb{E}[R]=0.9 \times 11.71 \%+0.1 \times\left(\frac{0.40}{0.8952}-1\right)=5 \% \tag{8.31}
\end{equation*}
$$
  
[^44]which simply reflects the fact that risk-neutral investors would price all assets to have the same expected return.
  
Now, in practice investors are not risk neutral. And defaults are typically viewed as systematic risks. They are more likely to happen in economic downturns in which other risky assets perform poorly, too. Hence, investors require an expected return premium to hold default-risky bonds. Suppose that investors are willing to pay only 0.83$ for this bond. Then the promised yield is $1 / 0.83-1=20.48 \%$, and hence the expected return is
$$
\begin{equation*}
\mathbb{E}[R]=0.9 \times 20.48 \%+0.1 \times\left(\frac{0.40}{0.83}-1\right)=13.25 \% \tag{8.32}
\end{equation*}
$$
which is hence $8.25 \%$ higher than the default-free yield. In this case, the promised yield of $20.48 \%$ has three components:
  
The default-free yield of $5 \%$
Expected loss due to default $0.1 \times \frac{0.60}{0.83}=7.23 \%$
Expected excess return $8.25 \%$
  
The credit spread of $20.48 \%-5 \%=15.48 \%$ is the sum of the last two components.
This makes clear that for bonds with substantial risk of default one should not interpret the promised yield as an expected return. If default risk is substantial, the expected return can be far lower than the promised yield.
  
Is sovereign default risk compensated with higher expected excess returns? Evidence from two centuries of data in Figure 8.17 suggests so. The plots show risk and return of countries' external debt issued in U.S. dollars or British pounds, using real returns calculated by deflating with the U.S. or U.K. inflation rate, respectively.
  
Figure 8.17a shows return standard deviations of sovereign debt of different countries on the x-axis and average real returns on the y-axis. Countries marked in red are countries that are serial defaulters; they had multiple default events during the past 200 years, and their returns are generally riskier. But as the plot shows, investors also earned a higher expected excess return.
  
Figure 8.17b shows betas with respect to the U.S. (for U.S. dollar bonds) or U.K. (for British pound bonds) equity market indices. On the y-axis is the excess return relative to U.S. or U.K. government bonds. This analysis focuses on a more recent period since 1995 since before that time the number of dollar or pound bonds outstanding has been very small and the data sparse. The plot shows that systematic risk of the debt of serial
 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-303.jpg?height=828&width=1205&top_left_y=318&top_left_x=468)
(a) Returns and standard deviations of sovereign debt, 1815-2016
 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-303.jpg?height=744&width=1071&top_left_y=1273&top_left_x=489)
(b) Returns and betas of sovereign debt, 1995-2016
  
Figure 8.17: Risk and average excess returns on sovereign debt
Source: Meyer, J., Reinhart, C.M. and Trebesch, C., 2022. Sovereign bonds since Waterloo. The Quarterly Journal of Economics, 137(3), pp.1615-1680.
defaulters is substantial: many betas reach 0.4 to 0.6 and in annualized terms their excess return was about $10 \%$. For comparison, the U.S. stock market earned about $10 \%$ excess return annually during this period, so the risk compensation that sovereign bond investors earned during this period was actually quite a bit higher than predicted by the CAPM.
  
From a [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]] viewpoint, the above illustrates that the risk of sovereign debt is clearly systematic. Concerns about defaults that lead to declines in prices of risky sovereign debt seem to be concentrated in periods when developed equity markets are also doing poorly.
  
As a final remark, I want to point out that countries in Europe that have adopted the euro as currency are in a somewhat unusual position. They don't fit the rule of thumb that domestic debt problems tend to be resolved through inflation and external debt problems through default. Countries in the eurozone have issued predominantly domestic debt in the currency that they use domestically (the euro), but because they are in a currency union, countries do not have control of [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]]. Instead, [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] is set by the European Central Bank (ECB). So individual countries do not have control of a central bank that could create money to buy up their sovereign debt and inflate away the debt. As a consequence, fiscal crises play out less like in other developed countries that have control of their own central banks, but rather like in emerging markets countries that have issued lots of external debt in foreign currency.
  
A few years after the Great Financial Crisis, the eurozone experienced a realization of such a crisis. Greece went through a default (restructuring of debt). Other countries (Spain, Portugal, Ireland, Italy) were subject to concerns about possible default. Bond yields reflected these elevated default probabilities as shown in Figure 8.18. Things calmed down eventually when the ECB developed programs that could be used to purchase sovereign debt of eurozone member countries. To this day, these problems are still simmering under the surface and have not been resolved.
 ![500](https://cdn.mathpix.com/cropped/2024_10_19_48a1c4654e845915c45cg-305.jpg?height=860&width=1218&top_left_y=828&top_left_x=475)
  
Figure 8.18: Sovereign bond yields of eurozone countries
[^0]:    ${ }^{1}$ This follows from applying L'Hôpital's rule. We'll skip the derivation.
  
[^1]:    ${ }^{2}$ For those interested in the details: The ratio $-\frac{U^{\prime \prime}\left(W_{0}\right) W_{0}}{U^{\prime}\left(W_{0}\right)}$ is is Arrow-Pratt relative risk aversion. With power utility we have
  
$$
\begin{align*}
U^{\prime}(W) & =W^{-\gamma}  \tag{1.12}\\
U^{\prime \prime}(W) & =-\gamma W^{-\gamma-1} \tag{1.13}
\end{align*}
$$
  
and so
$$
\begin{equation*}
\frac{U^{\prime \prime}\left(W_{0}\right) W_{0}}{U^{\prime}\left(W_{0}\right)}=-\gamma \tag{1.14}
\end{equation*}
  $$
i.e., indeed constant.
  
[^2]:    ${ }^{3}$ There are a variety of reasons why poorer people do not participate in the stock market at all (i.e., have zero holdings of stocks or stock mutual funds) that have nothing to do with risk aversion. To control for these other factors driving participation, I condition on having at least some stock market investment.
  
[^3]:    ${ }^{4}$ Formally, this is true for an infinitesimally small change, but for a reasonably sized wealth portfolio, a one dollar change is like an infinitesimally small change.
  
[^4]:    ${ }^{5}$ For those interested in the details: A first-order Taylor approximation of $U^{\prime}(W)$ around expected wealth $\mathbb{E}[W]$ yields
  
$$
\begin{equation*}
\frac{U^{\prime}(W)}{U^{\prime}(\mathbb{E}[W])} \approx 1+\frac{U^{\prime \prime}(\mathbb{E} W)}{U^{\prime}(\mathbb{E}[W])}(W-\mathbb{E}[W]) . \tag{1.22}
\end{equation*}
$$
  
With power utility, $U^{\prime \prime}(\mathbb{E} W) / U^{\prime}(\mathbb{E}[W])=-\gamma / \mathbb{E}[W]$. Combining with the approximation $W_{0} \approx \mathbb{E}[W]$ and $W-\mathbb{E}[W]=W_{0} \omega(R-\mathbb{E}[R])$, we then get the stated result.
  
[^5]:    ${ }^{6}$ For those of you interested in the more philosophical underpinnings: The interpretation I'm giving here is the interpretation in the Bayesian branch of statistics. In this interpretation, $\mu$ is uncertain, and $\sigma(\hat{\mu})$ tells us in which range around $\hat{\mu}$ the true $\mu$ is likely to be located. The formal interpretation of the standard error in a different branch of statistics that follows the frequentist tradition-which is what taught in most statistics courses - is different. There one thinks of a fixed true $\mu$ and hypothetically imagines re-running the world many times, calculating $\hat{\mu}$ in each of new samples. The standard error tells how much the $\hat{\mu}$ would vary across these samples given a fixed true $\mu$. From a decision-making perspective in investments, where we cannot re-run world (and asset market) history, we are not really interested in how estimates would vary if, hypothetically, we could re-run the world. Instead, we have one set of data from the history our world lived through that we want to use to assess $\mu$. From this viewpoint, the Bayesian perspective is more appropriate. We want to quantify how much uncertainty about $\mu$ we are left with, given the data we have been able to observe.
${ }^{7}$ In fact, we would get something like this even if the $\varepsilon_{t}$ were not normal. A result in statistics called the (Bayesian) central limit theorem tells us that $\mu$ would still be well approximated by a normal distribution as long as we have a relatively large sample of data, i.e., $T$ is large, even if the individual draws of $\varepsilon_{t}$ are not from a normal distribution.
  
[^6]:    ${ }^{1}$ For those interested in some more (optional) detail: Using high-frequency data to estimate variances works perfectly, in the sense that we could get infinitely precise estimates in the limit of infinitesimally small return measurement periods, when returns are generated as a continuous-time diffusion (a continuous-time diffusion does not have any discrete jumps, no matter how small we make the return measurement interval). This point was shown in Merton, Robert C., 1980, On estimating the expected return on the market, Journal of Financial Economics 8, 323-361.
  
[^7]:    ${ }^{2}$ For those who are interested in how to show this: Take the decomposition of the covariance matrix that we used earlier, $\boldsymbol{\Sigma}=\boldsymbol{S C S}$. Let $\omega^{*}$ be the weights of the risk parity portfolio which are proportional to $1 / \sigma_{i}$ for each asset class. The covariances of each asset class with the risk parity portfolio, using (2.8), are $\boldsymbol{\Sigma} \omega^{*}$, which is proportional to $\boldsymbol{S} \boldsymbol{C} \boldsymbol{\iota}$ because the standard deviations in $\boldsymbol{S}$ multiply with their reciprocals in $\omega^{*}$. Premultiplying each covariance with the weight $1 / \sigma_{i}$ to get the total risk contribution of each asset class to the portfolio, we get $\boldsymbol{C} \boldsymbol{\iota}$. As we discussed earlier, each element of the vector $\boldsymbol{C} \boldsymbol{\iota}$ is equal if $\boldsymbol{C}$ is an equicorrelation matrix. Therefore, the total risk contribution of each asset class is eqaual.
  
[^8]:    ${ }^{1}$ Log returns are also called continuously compounded returns.
  
[^9]:    ${ }^{3}$ Data is available at http://www.econ.yale.edu/ shiller/data.htm
  
[^10]:    ${ }^{4}$ According to Asness, C.S., 2003. Fight the Fed model. The Journal of Portfolio Management, 30(1), pp.11-24, the name apparently originates from the model's appearance in some obscure Federal Reserve report, but it's not a model officially used or endorsed by the Federal Reserve.
  
[^11]:    ${ }^{1}$ The method I used is known as Newey-West standard errors with 30 lags.
  
[^12]:    ${ }^{2}$ Combined data from the Michigan Survey of Consumers, UBS/Gallup survey of individual investors, Conference Board survey, and several smaller surveys. See Nagel, S. and Xu, Z., 2022. Asset pricing with fading memory. The Review of Financial Studies, 35(5), pp.2190-2245.
${ }^{3}$ https://www.richmondfed.org/cfosurvey/
${ }^{4}$ https://www.philadelphiafed.org/surveys-and-data/real-time-data-research/ livingston-survey
  
[^13]:    ${ }^{5}$ The geometric sequence of weights I have chosen here guarantees that the weights always sum to one for any value of $k$
${ }^{6}$ For more details, see Nagel, S. and Xu, Z., 2022. Asset pricing with fading memory. Review of Financial Studies, 35(5), pp.2190-2245 and Malmendier, U. and Nagel, S., 2016. Learning from inflation experiences. Quarterly Journal of Economics, 131(1), pp.53-87.
  
[^14]:    ${ }^{7}$ Studies relying on clever empirical techniques to infer causal relationships suggest the price impact could be substantial. See Lou, D., 2012. A flow-based explanation for return predictability. The Review of Financial Studies, 25(12), pp.3457-3489; Gabaix, X. and Koijen, R.S., 2021. In search of the origins of financial fluctuations: The inelastic markets hypothesis, working paper, University of Chicago.
  
[^15]:    ${ }^{8}$ Note that we are focusing here on the time-series of excess returns at the aggregate stock market index level. If one instead looks at the cross-section of individual stock returns, the result is different: stocks that did well in the past 12 months tend to earn higher returns in the following months than stocks that earned low returns in the past 12 months. This effect is known as the momentum effect. But momentum only exists in the cross-section of individual stock returns, not in the aggregate market index return time series.
${ }^{9}$ Newey-West method with 18 lags
  
[^16]:    ${ }^{10}$ The law of iterated expectations is a proposition in probability theory that implies $\mathbb{E}[\mathbb{E}[X \mid Y]]=$ $\mathbb{E}[X]$. If we think of $Y$ as the information that investors have at $t+1$ and that investors at $t$ could not yet observe, then we can write this as $\mathbb{E}_{t}\left[\mathbb{E}_{t+1}\left[X_{t+2}\right]\right]=\mathbb{E}_{t}\left[X_{t+2}\right]$. But this law does not apply to expectations of other people's future expectations if there is disagreement. For example, if I expect that investors next period will be too optimistic about future earnings growth, then my expectation of their expectation of earnings growth is not the same as my own expectation of future earnings growth.
  
[^17]:    ${ }^{11}$ See Aliber, R.Z. and Kindleberger, C.P., 2015. Manias, panics, and crashes: A history of financial crises (p. 256). Basingstoke: Palgrave Macmillan.
  
[^18]:    ${ }^{12}$ Hong, H. and Stein, J.C., 2007. Disagreement and the stock market. Journal of Economic perspectives, 21(2), pp.109-128.
  
[^19]:    ${ }^{13}$ To sell shares they don't own, short sellers (or their brokers) borrow shares from investors holding
  
[^20]:    ${ }^{1}$ Why does the sentiment model produce lower expected long run returns when we switch from the cases with sentiment to the no-sentiment case? In these simulations, I hold the short-run expected log return constant. While return volatility is the same in all the different cases with sentiment, and hence the expected simple short-term return is the same in all those, return volatility is much lower in the case without sentiment. As a consequence, by (5.12), the expected simple short-term return, and hence also the arithmetic mean of short-term returns, is lower in the the no-sentiment case. Hence, as the compounded expected simple short-term return is equal to the expected long-term return, the expected long-term return is lower.
  
[^21]:    ${ }^{2}$ For those interested in further details: The formula for an approximately unbiased estimate of the long-run expected return in this case is
  
$$
\begin{equation*}
\frac{T-h}{T-1} \times(1+\text { arithm. mean })^{h}+\frac{h-1}{T-1} \times(1+\text { geom. mean })^{h}-1 \tag{5.16}
\end{equation*}
$$
  
which yields a high weight on the arithmetic mean when $T$ is much bigger than $h$ and a high weight on the geometric mean when $T$ is not much larger than $h$. See equation (4.1) in Blume, M.E., 1974. Unbiased estimators of long-run expected rates of return. Journal of the American Statistical Association, 69(347), pp.634-638.
  
[^22]:    ${ }^{3}$ I'm calculating these 10-year log return variances from quarterly 10-year moving sums of log returns. Since these moving windows are moved forward one quarter of a time, they have a large degree of overlap. As a consequence, the number of overlapping 10-year log return observations I have is greater than the number of independent 10-year log return observations. For this reason, the usual degrees-of-freedom correction by dividing by $T-1$ instead of $T$ that functions in python or statistical packages implement is not correct. To correct this, I multiply the variance that I receive based on the standard degrees-offreedom correction by $((T-40-1) /(T-80))$. I do the same when I calculate long-run return variances from empirical data in the table that follows.
  
[^23]:    ${ }^{4}$ For the derivation of this approximation, see Campbell, J.Y. and L.M Viceira, Appendix to Strategic [[Lecture 2- Asset Allocation with Multiple Risky Assets|asset allocation]], Section 2.1.1, available at https://scholar.harvard.edu/files/campbell/files/ bookapp.pdf.
  
[^24]:    ${ }^{5}$ Sharpe, W.F., 2010. Adaptive [[Lecture 2- Asset Allocation with Multiple Risky Assets|asset allocation]] policies. Financial Analysts Journal, 66(3), pp.45-59.
  
[^25]:    ${ }^{1}$ If two investment strategies deliver cash flows in two periods and the cash flows of the two strategies are identical in one period, they must also be equal in the other period, otherwise an investor could make riskless profits by going long in one strategy and short in the other strategy. Absence of such arbitrages is a fundamental pricing principle in finance.
${ }^{2}$ And in turn, futures contracts are almost equivalent to forward contracts, with some differences about the way margining is handled. Moreover, futures contracts are traded on exchanges, while forward contracts and swaps are arranged over-the-counter bilaterally between counterparties.
  
[^26]:    ${ }^{3}$ For the European put options that we are considering here, it can happen that $P_{t}<K-S_{t}$ in extreme situations where it is virtually certain that the option will end up in the money and will be exercised at maturity, e.g., if the current index level is so far below the strike price, that it's virtually impossible that the option expires out of the money. To see why, suppose $S_{t}$ is far below $K$. As owner of a put option, you basically know for sure that a combined position of the index and the put will be worth $K$ after you exercise the option at maturity. The present value of this combined payoff is $\left.\operatorname{Kexp}\left[-r_{f}(T-t)\right]\right]$, so it must be true that $\left.S_{t}+P_{t}=\operatorname{Kexp}\left[-r_{f}(T-t)\right]\right]$, and hence $\left.P_{t}=\operatorname{Kexp}\left[-r_{f}(T-t)\right]\right]-S_{t}$, which is smaller than $K-S_{t}$. But unless interest rates are very high, even in this extreme scenario here, $P_{t}$ can be just a very small amount below $K-S_{t}$.
  
[^27]:    ${ }^{4} \mathrm{~A}$ recent example that may fall in this category was the pension fund Calpers. Calpers unwound a
  
[^28]:    ${ }^{5}$ See Eraker, B. and Wu, Y., 2017. Explaining the negative returns to volatility claims: An equilibrium approach. Journal of Financial Economics, 125(1), pp.72-98.
${ }^{6}$ To me more precise, holdings is not quite the correct description. VXX is an exchange traded note,
  
[^29]:    ${ }^{1}$ More precisely, U.S. Treasury securities with short maturities up to 12 months at issuance are called bills; those with maturities 2 to 10 years are called notes, and only those with maturities longer than 10 years are called bonds. Here I often refer to all of them just as "bonds".
  
[^30]:    ${ }^{2}$ These zero-coupon yields have been extracted by a team of researchers at the Federal Reserve Board. They are available online at https://www.federalreserve.gov/pubs/feds/2006/200628/ 200628abs.html and this page also has material that explains the methods used for extraction.
  
[^31]:    ${ }^{3}$ One caveat. The zero-coupon yields I am using here have been extracted from coupon-bond yields with a method that already induces some smoothing in yields. It may therefore understate a little bit the idiosyncratic variation in yields of individual-maturity bonds and overstate the explanatory power of these three factors. But smoothing only has a small effect, the $R^{2}$ is also very close to one if one uses methods of zero-coupon bond yield construction that do not involve such smoothing.
  
[^32]:    ${ }^{4}$ One basis point (bp) is equal to 0.01 percentage points.
  
[^33]:    ${ }^{5}$ This is an approximation. We should really be setting expected simple returns equal. For example, if the short-term yield was conditionally log-normal, then setting expected returns equal would yield $y_{t, 2}=\lambda+\frac{1}{2}\left[y_{t, 1}+\mathbb{E}_{t}\left[y_{t+1,1}\right]+\frac{1}{2} \operatorname{var}_{t}\left(y_{t+1,1}\right)\right]$, i.e., there is an additional conditional variance term, also known as a convexity term, as it reflects the convexity of $\exp \left(y_{t+1,1}\right)$. If the conditional variance term is constant, we can just absorb it in the $\lambda_{2}$ in (7.13), but if it's time-varying, it would generate deviations from (7.13). Plausible values of this distortion are relatively small, though. So we ignore them here.
  
[^34]:   ${ }^{6}$ Note that for this channel to be operative, the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] does not have to hold exactly. All that is required is that expectations of future short-term interest rates are one driver of long-term
  
[^35]:    ${ }^{1}$ This equation also demonstrates an important principle of valuation. To value an asset, we need to either discount nominal cash flows with a nominal discount rate, as done in this equation, or, alternatively, we can discount real cash flows with real discount rates. The latter approach would be to calculate $V_{t}=\frac{\mathbb{E}_{t}\left[D_{t+1}\left(C P I_{t} / C P I_{t+1}\right)\right]}{1+R^{r}}=\frac{\mathbb{E}_{t}\left[D_{t+1}\right] E_{t}\left[C P I_{t} / C P I_{t+1}\right]}{1+R^{r}}$ where we used the fact that for a nominal asset cash flow and inflation are uncorrelated so we can write the expectation of the product as the product of the expectations. We can then divide numerator and denominator by $E_{t}\left[C P I_{t} / C P I_{t+1}\right]$ and we get the same expression as (8.5).
  
[^36]:    ${ }^{2}$ Unless the inflation rate is huge $R_{t: t+12}^{r}=\left(1+R_{t: t+12}\right) /\left(1+\Pi_{t: t+12}\right)-1 \approx R_{t: t+12}-\Pi_{t: t+12}$. With returns and inflation in logs, i.e., $r_{t: t+12}^{r}=\log \left(1+R_{t: t+12}^{r}\right)$ and $\pi_{t: t+12}=\log \left(1+\Pi_{t: t+12}\right)$, it would be exact: $r_{t: t+12}^{r}=r_{t: t+12}-\pi_{t: t+12}$.
  
[^37]:    ${ }^{3}$ In this regression, the data is monthly, but the windows over which returns and inflation are measured span 12 months. Hence, the observations are from overlapping measurement windows. In this case, the usual regression formulas do not provide the correct standard errors and $t$-statistics. I use a simple and somewhat conservative fix for this: I calculate the standard errors from a similar regression that uses only non-overlapping data, i.e., I use only every 12 th observation of $R_{t: t+12}^{r}, U E_{t: t+12}$, and $\Delta E_{t: t+12}$.
  
[^38]:    ${ }^{4}$ Bittlingmayer, G., 1998. Output, stock volatility, and political uncertainty in a natural experiment: Germany, 1880-1940. Journal of Finance, 53(6), pp.2243-2257.
  
[^39]:    ${ }^{5}$ There is one further detail: In case there is deflation, the principal is not adjusted below $C P I_{t-3}$, so a deflation adjustment can only remove prior accumulated inflation adjustments, but once they are used up, the adjustments stop and TIPS become like nominal Treasury bonds. That's another reason why real cash flows of TIPS are not perfectly certain.
  
[^40]:    ${ }^{6}$ However, some countries have also seen slightly negative nominal yields in recent years following bond purchase programs of central banks. After all, holding large amounts of paper money is costly, and bank deposit rates turned negative, too, in these countries, so holding a negative nominal yield bond may not be worse than these alternatives.
  
[^41]:    ${ }^{7}$ See, e.g., Taylor, A.M. and Taylor, M.P., 2004. The purchasing power parity debate. Journal of Economic Perspectives, 18(4), pp.135-158.
  
[^42]:    ${ }^{8}$ The Chairman of the Federal Reserve Paul Volcker, who started his term during the high inflation of the late 1970s, once articulated this concern in a hearing in Congress in 1979 by saying: "An entire generation of young adults has grown up since the mid-1960s knowing only inflation, indeed an inflation that has seemed to accelerate inexorably. In the circumstances, it is hardly surprising that many citizens have begun to wonder whether it is realistic to anticipate a return to general price stability, and have begun to change their behavior accordingly."
  
[^43]:    ${ }^{9}$ The latter means that they have recently missed some coupon or principal payments on their outstanding debt, or they forced an exchange of old debt obligations for new debt with less favorable terms, and they have not yet reached an agreement with creditors on how to restructure the debt, resume payments, etc.
  
[^44]:    ${ }^{10}$ During the past century, this has been the average loss given default in sovereign default events. See Cruces, J.J. and Trebesch, C., 2013. Sovereign defaults: The price of haircuts. American economic Journal: macroeconomics, 5(3), pp.85-117.
