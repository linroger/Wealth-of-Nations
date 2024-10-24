---
aliases:
- Alias_145_PSET 1-Financial Instruments.md
- Alias_146_PSET 1-Financial Instruments.md
- PSET 1-FINANCIAL INSTRUMENTS
linter-yaml-title-alias: PSET 1-FINANCIAL INSTRUMENTS
tags:
- tag_example
title: PSET 1-FINANCIAL INSTRUMENTS
---


---
title: PSET 1-FINANCIAL INSTRUMENTS
aliases: [PSET 1-FINANCIAL INSTRUMENTS]
linter-yaml-title-alias: PSET 1-FINANCIAL INSTRUMENTS
tags: [1,  2]
title: PSET 1-FINANCIAL INSTRUMENTS
aliases: [PSET 1-FINANCIAL INSTRUMENTS]
linter-yaml-title-alias: PSET 1-FINANCIAL INSTRUMENTS
tags: [1,  2]
# PSET 1-FINANCIAL INSTRUMENTS
[Teaching Note 1Forward Rates Agreement](Teaching%20Note%201-%20Forward%20Rates%20Agreement.md)
[Teaching Note 2-Futures Contracts](Teaching%20Note%202-Futures%20Contracts.md)
[Arbitrage Opportunity Accounting](Arbitrage%20Opportunity%20Accounting.md)
[Financial Instruments 2024](Financial%20Instruments%202024.md)
Bus 35100
John Heaton Homework 1
Due at the beginning of class week 2.
## 1 ARBITRAGE AND FORWARD RATES
| | |$/EURO FORWARD |  |  |  |
| ---- | ---- | ---- | ---- | ---- | ---- |
| Date |$/EURO SPOT | 1M | 3M | 6M | 1Y |
| Monday,  October 3,  2005 | 1.19235 | 1.19425 | 1.19812 | 1.20462 | 1.21789 |
| Monday,  October 2,  2006 | 1.27385 | 1.27619 | 1.28007 | 1.28505 | 1.29298 |
| Monday,  October 1,  2007 | 1.42325 | 1.42448 | 1.42562 | 1.42667 | 1.42805 |
| Wednesday,  October 1,  2008 | 1.4021 | 1.40422 | 1.4047 | 1.40302 | 1.39603 |
| Thursday,  October 1,  2009 | 1.4533 | 1.45341 | 1.45325 | 1.45307 | 1.45302 |
| US LIBOR |  |  |  | EURO LIBOR |  |  |  |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 1M | 3M | 6M | 1Y | 1M | 3M | 6M | 1Y |
| 3.88 | 4.08 | 4.27 | 4.48 | 2.12 | 2.18 | 2.21 | 2.33 |
| 5.32 | 5.37 | 5.38 | 5.32 | 3.29 | 3.42 | 3.58 | 3.74 |
| 5.12 | 5.23 | 5.15 | 4.94 | 4.39 | 4.79 | 4.76 | 4.72 |
| 4.00 | 4.15 | 4.04 | 4.04 | 5.07 | 5.29 | 5.39 | 5.50 |
| 0.25 | 0.28 | 0.62 | 1.24 | 0.39 | 0.70 | 1.00 | 1.23 |
| |   | |   | |   | |   |
|---|---|---|---|---|---|---|---|
|US LIBOR (c.c. rates)| |   | |EURO LIBOR(c.c. rates)| |   | |
|1M|3M|6M|1Y|1M|3M|6M|1Y|
|3.87|4.06|4.22|4.39|2.12|2.17|2.20|2.31|
|5.31|5.33|5.31|5.18|3.29|3.41|3.55|3.68|
|5.11|5.20|5.08|4.82|4.38|4.76|4.70|4.61|
|4.00|4.13|4.00|3.96|5.06|5.25|5.32|5.35|
|0.25|0.28|0.62|1.23|0.39|0.70|1.00|1.22
|
Consider a one-year forward contract for converting between dollars and Euros. The current exchange rate is$1.20 for each Euro. The one-year risk-free rate in dollars is 5% in continuously compounded units while the one-year risk-free rate in Euros is 4.5%.
(1) According to the principle of no-arbitrage,   what should be the one-year forward rate?$$F_{0,  T}=S_{0}e^{(r_{USD}-r_{{EUR}})T}$$$$F_{0,  T}=1.20*e^{(0.05-0.045)*1}= \$1.20602 \text{ per euro}$$
> [!ANSWER] According to no-arbitrage the Forward Exchange rate is given by
> $$M_{0}\cdot e^{(r_{H}-r_{F})\cdot T}\tag{1}$$
>
> where$M_0$is the spot exchange rate (number of units of the Home currency to buy 1 unit of the Foreign currency),  $r_H$is the annualized continuously-compounded interest rate in the Home country,  $r_F$is the annualized continuously-compounded interest rate in the Foreign country and$T$is the maturity we are interested in.
> Here the home country is the US so that
> - $r_H = r_{USD} = 5\%$and
> - $r_F = r_{EUR} = 4.5\%$.
> Further M0 = 1.2 and T = 1. The forward rate should be:$$F_{0,  1}=M_{0}\cdot e^{(r_{3}-r_{e})\cdot T}=1.2\cdot e^{5\%-4.5\%}=1.2060$$
(2) Suppose that the one-year forward contract is currently trading at$1.15 per Euro. Is there an arbitrage opportunity? If so,  explain in detail the trading you would like to do to exploit this arbitrage opportunity.
| Forward Rate Implied by No Arbitrage | Maturity in Years |  |  |  |
| ---- | ---- | ---- | ---- | ---- |
| Date | 0.083333333 | 0.25 | 0.5 | 1 |
| Monday,   October 3,   2005 | 1.1941 | 1.1980 | 1.2045 | 1.2174 |
| Monday,   October 2,   2006 | 1.2760 | 1.2800 | 1.2851 | 1.2932 |
| Monday,   October 1,   2007 | 1.4241 | 1.4248 | 1.4260 | 1.4262 |
| Wednesday,   October 1,   2008 | 1.4009 | 1.3982 | 1.3929 | 1.3827 |
| Thursday,   October 1,   2009 | 1.4531 | 1.4518 | 1.4505 | 1.4535 |
| Difference from actual |  |  |  |  |
| ---- | ---- | ---- | ---- | ---- |
| Date | 1M | 3M | 6M | 1Y |
| Monday,   October 3,   2005 | 0.0002 | 0.0001 | 0.0002 | 0.0005 |
| Monday,   October 2,   2006 | 0.0002 | 0.0001 | 0.0000 | -0.0002 |
| Monday,   October 1,   2007 | 0.0004 | 0.0008 | 0.0007 | 0.0018 |
| Wednesday,   October 1,   2008 | 0.0034 | 0.0065 | 0.0102 | 0.0134 |
| Thursday,   October 1,   2009 | 0.0003 | 0.0015 | 0.0025 | -0.0004
|
> [!ANSWER]
> 1. The traded value of the forward is 1.15 which is below the no-arbitrage value so there is an arbitrage trade to be made. We would like to "buy low" and "sell high." In other words we would like to enter into the forward contract to buy Euros at 1.15 and *synthetically* sell them forward using the bond markets in the countries and the current exchange rate.
> - Let's suppose we want to do this the level of 100 Euros. Here are the trades:
> 	-Buy 100 million Euros forward which creates an obligation of$100 · 1.15 =$115 million at time 1 (one year).
> 	- We need to trade today so that we have (at least) the$115 million to deliver at time 1. To do this: [^1]
> 		- Borrow 100 · e−0.045 = 95.5887 Euros today.
> 		- Convert the 95.5887 million Euros today to dollars: 95.5887 × M0 = 114.7197 million dollars today and invest at the rate of 5% in continuously compounded units.
> 	-Notice that the trades in the current bond markets and [Foreign Exchange](Foreign%20Exchange%20Quoting%20Conventions.md) market create the following cash flows at time 1:
> - Euros owed at time 1:$$95.5887\cdot e^{0.045}=100$$which is covered by our receipt of 100 million Euros at time 1 under the forward contract.
>
> - Dollars received at time 1:$$114.7197\cdot e^{0.05}=120.6015{\mathrm{~millillion}}$$
> which is more than covers our obligation of$115 million under the forward contract.
> The profit at time 1 is:$120.6 −$115 =$5.6 million.
> [^1] Since there is an arbitrage opportunity. There are several ways to numerically setup the trade to generate extra cash in either Euros or dollars at time 0 or time 1.
>  	- The trade here mimics the "no cash today" outcome of the forward contract
## 2 FORWARD RATES AND COVERED INTEREST RATE PARITY
The Excel file DataHW1 2024.xls contains data on the$/Euro exchange rate on the first business day of October of the years 2005 to 2009. In addition,  it contains Forward Rate quotes,  as well as US and EURO LIBOR rates.
Please,  do the following:
(1) For each date,  use the Forward Rate formula discussed in Teaching Note 2 to compute the Forward Exchange Rate. Please do so for all of the given maturities (1 month,  3 months,  6 months,  1 year).
- (Tip #1: Note that LIBOR rates use linear compounding,  while the formula in the teaching notes use continuous compounding. You will need the transformation like the one on page 14 of Teaching Note 2 to use the forward pricing formula we developed.
- Tip #2: The log function in the notes on page 14 is the *natural logarithm*. To implement this in Excel you use the function LN NOT the function *LOG*).
$$
\begin{array}{rrrrrrrrr}\hline&&&\text{US LIBOR}&&\text{EURO LIBOR}&&&&\\\hline& \text{1M} & \text{3M} & \text{6M} & \text{1Y} & \text{1M} & \text{3M} & \text{6M} & \text{1Y} \\\hline\text{03-Oct-05}&3.87\%&4.06\%&4.22\%&4.39\%&2.12\%&2.17\%&2.20\%&2.31\%\\\hline\text{02-Oc+06}&5.31\%&5.339\%&5.31\%&5.18\%&3.29\%&3.41\%&3.55\%&3.68\%\\\hline\text{01-Oc+07}&5.11\%&5.20\%&5.08\%&4.82\%&4.38\%&4.76\%&4.70\%&4.61\%\\\hline \text{01-Oct-08}&4.00\%&4.13\%&4.00\%&3.96\%&5.06\%&5.25\%&5.32\%&5.35\%\\\hline\text{01-Oct-09}&0.25\%&0.28\% &0.62\%&1.23\%&0.39\%&0.70\%&1.00\%&1.22\%\\\hline\end{array}
$$
$$
\begin{array}{|l|cccc|}
\hline
& \text{1M} & \text{3M} & \text{6M} & \text{1Y} \\
\hline
\text{03-Oct-05} & 1.1941 & 1.1980 & 1.2045 & 1.2174 \\
\text{02-Oct-06} & 1.2760 & 1.2800 & 1.2851 & 1.2932 \\
\text{01-Oct-07} & 1.4241 & 1.4248 & 1.4260 & 1.4262 \\
\text{01-Oct-08} & 1.4009 & 1.3982 & 1.3929 & 1.3827 \\
\text{01-Oct-09} & 1.4531 & 1.4518 & 1.4505 & 1.4535 \\
\hline
\end{array}
$$
> [!ANSWER]
> - 1. As above,  according to no-arbitrage the Forward Exchange rate is given by
> $$M_{0}\cdot e^{(r_{H}-r_{F})\cdot T}\tag{2}$$
> where$M_0$is the spot exchange rate (number of units of the Home currency to buy 1 unit of the Foreign currency),  $r_H$is the annualized continuously-compounded interest rate in the Home country,  $r_F$is the annualized continuously-compounded interest rate in the Foreign country and$T$is the maturity we are interested in.
> 	- Before applying formula 2 we need to compute the continuously compounded LIBOR rates.
> 		- LIBOR rates use linear compounding,  meaning that the x-months LIBOR is compounded 12 x times in a year.
> 			- In other words the 1-month LIBOR has a$\frac{1}{12}$=monthly compounding frequency,  the 3-month LIBOR has a$\frac{3}{12} = \frac{1}{4}$=quarterly compounding frequency and so on. If we define with m to be the number of times interest is compounded in a year (according to what just said,  $m = \frac{12}{x}$,  to compute the equivalent continuously-compounded rate we use the equivalence$$e^{r\cdot T}=\left(1+\frac{r_{m}}{m}\right)^{m\cdot T}\tag{3}$$
> where$r_m$denotes an annualized interest rate compounded m times in 1 year (e.g.$r_1$is the annualized monthly compounded rate,  $r_4$is the annualized quarterly compounded rate and so on). To get a formula for the continuously compounded rate,  we take natural logarithms in equation 3$$ln\left(e^{r\cdot T}\right)=ln\left[\left(1+\frac{r_{m}}{m}\right)^{m\cdot T}\right]$$then,  knowing that$ln(e^{x})=x$and that$ln(a^{x})=x\cdot ln(a)$$$r\cdot T=m\cdot T\cdot ln\left(1+\frac{r_{m}}{m}\right)$$dividing both sides by T we finally get$$r=m\cdot ln\left(1+\frac{r_{m}}{m}\right)\tag{4}$$Applying formula 4 we can compute the continuously compounded US and EURO LIBOR rates. Results are shown in Table 1. Using the above rates we apply formula 2 to compute Forward Exchange rates.
(2) Do your forward exchange rates match (approximately) the quoted ones?
> [!ANSWER]
> 1. We compute the difference between the quoted and the computed Forward Exchange rates,  which are reported in Table 3
> - If we exclude October 1st 2008,  the difference is smaller than 10−3 in most of the cases.
> - For October 1st 2008 (15 days after Lehman failure) the difference is larger. To understand why this is so,  think about how we determined formula 2 for the Forward Exchange rate.
> - Our assumption was that we could set up a strategy which perfectly matches the cash flows of a short forward position in euros for dollars.
> 	- The strategy requires borrowing in euros,  exchanging euros into dollars and investing the money at the dollar interest rate.
> 	- If market participants are worried about third party solvency borrowing may be much more difficult,  especially for longer maturities.
> 	- If borrowing is more difficult then arbitrageurs may experience have a time correcting market inefficiencies and the result is quoted prices misaligned with the theoretical ones.
> 	**- Table 3: Difference between quoted and computed Forward Exchange rates**
> 	- $$
> \begin{array}{ccccc}
> \hline
> \text{Date} & \text{1M} & \text{3M} & \text{6M} & \text{1Y} \\
> \hline
> \text{03-Oct-05} & 0.0002 & 0.0001 & 0.0002 & 0.0005 \\
> \text{02-Oct-06} & 0.0002 & 0.0001 & (0.0000) & (0.0002) \\
> \text{01-Oct-07} & 0.0004 & 0.0008 & 0.0007 & 0.0018 \\
> \text{01-Oct-08} & 0.0034 & 0.0065 & 0.0102 & 0.0134 \\
> \text{01-Oct-09} & 0.0003 & 0.0015 & 0.0025 & (0.0004) \\
> \hline
> \end{array}
> $$
(3) If not,  pick one particular date in which the parity is violated,  and describe the arbitrage strategy you would undertake.
> [!ANSWER]
> 1. As we have seen that the biggest discrepancy occurs for October 1 st 2008.
> Let's focus on that date and consider the 1 year Forward Exchange rate. As mentioned above the difference $F^{quoted} − F^{computed}>0$,  that is equivalent to $F^{quoted} > F^{computed}$.
> - The rule of thumb for arbitrage is to buy cheap and sell dear.
> 	- This means "buy computed" and "sell quoted."
> - The computed Forward Exchange rate is a *synthetic* price that we pay if we set-up a strategy that replicates the payoff of a forward contract,  while the quoted Forward Exchange rate is what we obtain when entering into a forward position (just sign a contract,  much easier than setting up a replicating strategy).
> - We already know that we enter into a short forward contract to sell 1 euro for dollars (this is the "sell quoted" - we are selling euros and buying dollars; remember that with exchange rates we are long / short the Foreign currency).
> - On the other side we have to set up a strategy that replicates the payoff of a long forward position to buy 1 euro for dollars.
> Let's start by matching the payoffs at maturity.
> 	- A long forward contract,  at maturity,  entails:
> 		- An outflow (we pay) of dollars
> 		- An inflow (we receive) of euros To pay dollars tomorrow we simply borrow something in US.
> - To receive euros tomorrow we have to invest something in Europe today. How much? Here we have to remember our goal.
> 	- We are matching the cash flows of a forward contract,  and a forward contract does not require any cash flow when we enter into it.
> 	- As our strategy so far requires borrowing in dollars and investing in euros today,  to get a cash flow equal to 0 we have to match the amount we borrow with the amount we invest,  or in other words we have to invest in Europe the full amount borrowed in US.
> 		- To do this we just need to exchange the dollars for euros today.
> 	- The last thing we need to understand is how much to borrow in dollars today. As the forward exchange rate tells us "how many dollar we have to pay in exchange for 1 euro at maturity",  following our logic of matching the cash flows of a forward contract we want to borrow today (in dollars) a sum that will give us 1 euro tomorrow: that's the very definition of present value.
> [!ANSWER]
> - Summing up,  the "buy computed" strategy requires (please note that the amounts in the first and third rows are in different currencies so they cannot be summed):
> - Table 4: Summary of the synthetic long forward position$$
> \begin{array}{lccc}
> \hline
> \text{Today } t = 0 & & \text{In formulas} \\
> \hline
> \text{Borrow in dollars the PV or 1 euro} & & +e^{-r_e} \cdot M_0 \\
> \text{Exchange the amount borrowed into euros} & & \\
> \text{Invest the present value of 1 euro today} & & -e^{-r_e} \\
> \hline
> \text{At maturity } t = T & & \text{In formulas} \\
> \hline
> \text{Pay dollars} & & -M_0 \cdot e^{(r_{US}-r_e) \cdot T} \\
> \text{Exchange the euros received into dollars} & & \\
> \text{Receive 1 euro} & & +1 \\
> \hline
> \end{array}
> $$
> - Finally we can consider the cash flows from both the short position (again,   short since we are selling euros) and the synthetic long (again,   long since we are buying euros) forward position,   which are reported in Table 5. Please note that the amount$M_T$is simply the value,   in dollars,   of 1 euro at time$T$.
> $$
> \begin{array}{lccc}
> \hline
> \text{Amounts in USD} & t = 0 & & t = T \\
> \hline
> \text{Short forward position} & 0 & & F_{\text{quoted}} - M_T \\
> \text{Synthetic long forward position} & 0 & & M_T - F_{\text{computed}} \\
> \text{TOTAL} & 0 & & F_{\text{quoted}} - F_{\text{compute}} > 0 \\
> \hline
> \end{array}
> $$
> - Applying the above formulas to our case the strategy becomes:
> 	- Short a forward contract to sell 1 euro for 1.3960 dollars in one year
> 	- Borrow$e^{−0.0535} · 1.4021 = 0.9479 · 1.4021 = 1.3290$dollars today (October 1st 2008)
> 	- Exchange 1.3290 dollars for euros obtaining 0.9479 euros
> 	- Invest 0.9479 euros at$r_{EUR} = 5.35$%
> - At maturity we will have
> 	- Pay 1 euro (from short forward position)
> 	- Receive 1.3960 dollars
> 	- Receive 1 euro (from long synthetic forward position)
> 	- Pay$1.3290 · e^{0.0396} = 1.3827$dollars
> - The net cash flow will be a positive amount equal$1.396 − 1.3827 = 0.0134$
> dollars per euro traded. If we apply the same strategy on$100 m,   the arbitrage is supposed to generate a positive cash flow at maturity equal to$1.337 m.
