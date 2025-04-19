---
title: PSET 1 Solution-Financial Instruments
tags:
  - arbitrage
  - financial_instruments
  - forward_contract
  - forward_rates
  - no_arbitrage
aliases:
  - PSET 1
  - PSET 1 Solution
key_concepts:
  - annualized interest rate
  - arbitrage trade
  - buy low sell high
  - forward exchange rate
  - spot exchange rate
---

---

title: PSET 1 Solution

# PSET 1 Solution-Financial Instruments
## Financial Instruments John Heaton Solutions To Homework 1 1 Arbitrage And Forward Rates
1. According to no-arbitrage,  the forward exchange rate is given by
$$M_{0}\cdot e^{(r_{H}-r_{F})\cdot T}\tag{1}$$
where $M_0$ is the spot exchange rate (number of units of the home currency to buy 1 unit of the foreign currency),  rH is the annualized continuously-compounded interest rate in the home country,  rF is the annualized continuously-compounded interest rate in the foreign country,  and T is the maturity we are interested in.
Here,  the home country is the US,  so that rH = r% = 5% and rF = re = 4.5%.
Further,  $M_0$ = 1.2 and T = 1. The forward rate should be:
$$F_{0,  1}=M_{0}\cdot e^{(r_{H}-r_{e})\cdot T}=1.2\cdot e^{5\%-4.5\%}=1.2060$$
1. The traded value of the forward is 1.15,  which is below the no-arbitrage value,  so there is an arbitrage trade to be made. We would like to “buy low” and “sell high.” In other words,  we would like to enter into the forward contract to buy Euros at 1.15 and *synthetically* sell them forward using the bond markets in the countries and the current exchange rate. Let’s suppose we want to do this at the level of 100 Euros.
Here are the trades:
- Buy 100 million Euros forward,  which creates an obligation of $100 · 1.15 = $115 million at time 1 (one year).
- We need to trade today so that we have (at least) the $115 million to deliver at time 1. To do this:1
- Borrow 100 · e−0.045 = 95.5887 Euros today.
- Convert the 95.5887 million Euros today to dollars: 95.5887 × $M_0$ = 114.7197 million dollars today and invest at the rate of 5% in continuously compounded units.
- Notice that the trades in the current bond markets and foreign exchange market create the following cash flows at time 1:
- Euros owed at time 1: $$95.5887\cdot e^{0.045}=100$$ ß which is covered by our receipt of 100 million Euros at time 1 under the forward contract.
- Dollars received at time 1:
$$114.7197\cdot e^{0.05}=120.6015{\mathrm{~million}}$$
which is more than covers our obligation of $115 million under the forward contract. The profit at time 1 is: $120.6 − $115 = $5.6 million.
## 2 Forward Rates And The Covered Interest Rate Parity
1. As above,  according to no-arbitrage the Forward Exchange rate is given by $$M_0\cdot e^{(r_H-r_F)\cdot T}$$ where $M_{0}$ is the spot exchange rate(number of units of the Home currency to buy 1 unit of the Foreign currency),  $TH$ is the annualized continuously-compounded interest rate in the Home country,  $TF$ is the annualized continuously-compounded interest rate in the Foreign country and $T$ is the maturity we are interested in. Be fore applying formula 2 we need to compute the continuously compounded [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] rates.
[[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] rates use linear compounding,  meaning that the ${:}L$ -months [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] is compounded $\frac{12}x$ times in a year. In other words the 1-month [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] has a $\frac{1}{12}=$ monthly compounding frequency,  the 3-month [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] has a $\frac{3}{12}=\frac{1}{4}=$ quarterly compound ing frequency and so on. If we define with $Trn.$ to be the number of times interest is compounded in a year (according to what just said,  $m={\frac{12}{x}}$),  to compute the equivalent continuously-compounded rate we use the equivalence $$e^{r\cdot T}=\left(1+\frac{r_m}{m}\right)^{m\cdot T}$$ where $r_{m}$ denotes an annualized interest rate compounded $Trn.$ times in 1 year (e.g $r1$ is the annualized monthly compounded rate,  $TA$ is the annualized quarterly compounded rate and so on).
To get a formula for the continuously compounded rate,  we take natural logarithms in equation 3
$$ln\left(e^{r\cdot T}\right)\:=\:ln\left[\left(1+\frac{r_m}{m}\right)^{m\cdot T}\right]$$ then,  knowing that $ln(e^{x})=x$ and that $ln(a^{x})=x\cdot ln(a)$
$$r\cdot T=m\cdot T\cdot ln\left(1+\frac{r_m}{m}\right)$$
dividing both sides by $T$ we finally get
$$r=m\cdot ln\left(1+\frac{r_m}{m}\right)$$
Applying formula 4 we can compute the continuously compounded US and EURO [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] rates. Results are shown in Table 1.
Using the above rates we apply formula 2 to compute Forward Exchange rates. Results are provided in Table 2.
Results are provided in Table 2.

```latex
\usepackage{booktabs}
\begin{document}
\renewcommand{\arraystretch}{1.3}
\small
\begin{tabular}{|c|c|c|c|c|c|c|c|c|c|}
\hline
\multicolumn{5}{|c|}{\textbf{US LIBOR}} & \multicolumn{5}{c|}{\textbf{EURO LIBOR}} \\ \hline
\textbf{Date} & \textbf{1M} & \textbf{3M} & \textbf{6M} & \textbf{1Y} & \textbf{Date} & \textbf{1M} & \textbf{3M} & \textbf{6M} & \textbf{1Y} \\ \hline
03-Oct-05 & 3.87\% & 4.06\% & 4.22\% & 4.39\% & 03-Oct-05 & 2.12\% & 2.17\% & 2.20\% & 2.31\% \\ \hline
02-Oct-06 & 5.31\% & 5.33\% & 5.31\% & 5.18\% & 02-Oct-06 & 3.29\% & 3.41\% & 3.55\% & 3.68\% \\ \hline
01-Oct-07 & 5.11\% & 5.20\% & 5.08\% & 4.82\% & 01-Oct-07 & 4.38\% & 4.76\% & 4.70\% & 4.61\% \\ \hline
01-Oct-08 & 4.00\% & 4.13\% & 4.00\% & 3.96\% & 01-Oct-08 & 5.06\% & 5.25\% & 5.32\% & 5.35\% \\ \hline
01-Oct-09 & 0.25\% & 0.28\% & 0.62\% & 1.23\% & 01-Oct-09 & 0.39\% & 0.70\% & 1.00\% & 1.22\% \\ \hline
\end{tabular}
\end{document}
```

```latex
\usepackage{booktabs}
\begin{document}
\renewcommand{\arraystretch}{1.3}
\small
\begin{tabular}{|c|c|c|c|c|}
\hline
\textbf{Date} & \textbf{1M} & \textbf{3M} & \textbf{6M} & \textbf{1Y} \\ \hline
03-Oct-05 & 1.1941 & 1.1980 & 1.2045 & 1.2174 \\ \hline
02-Oct-06 & 1.2760 & 1.2800 & 1.2851 & 1.2932 \\ \hline
01-Oct-07 & 1.4241 & 1.4248 & 1.4260 & 1.4262 \\ \hline
01-Oct-08 & 1.4009 & 1.3982 & 1.3929 & 1.3827 \\ \hline
01-Oct-09 & 1.4531 & 1.4518 & 1.4505 & 1.4535 \\ \hline
\end{tabular}
\end{document}
 ```

Forward Exchange rates
2. We compute the difference between the quoted and the computed Forward Exchange rates,  which are reported in Table 3.
If we exclude October 1st,  2008,  the difference is smaller than 10−3 in most of the cases. For October 1st,  2008 (15 days after Lehman’s failure),  the difference is larger. To understand why this is so,  think about how we determined formula
2 for the Forward Exchange rate. Our assumption was that we could set up a strategy which perfectly matches the cash flows of a short forward position in euros for dollars. The strategy requires borrowing in euros,  exchanging euros into dollars,  and investing the money at the dollar interest rate. If market participants are worried about third-party solvency,  borrowing may be much more difficult,  especially for longer maturities. If borrowing is more difficult,  then arbitrageurs

```latex
\usepackage{booktabs}
\begin{document}
\renewcommand{\arraystretch}{1.3}
\small
\begin{tabular}{|c|c|c|c|c|}
\hline
\textbf{Date} & \textbf{1M} & \textbf{3M} & \textbf{6M} & \textbf{1Y} \\ \hline
03-Oct-05 & 0.0002 & 0.0001 & 0.0002 & 0.0005 \\ \hline
02-Oct-06 & 0.0002 & 0.0001 & (0.0000) & (0.0002) \\ \hline
01-Oct-07 & 0.0004 & 0.0008 & 0.0007 & 0.0018 \\ \hline
01-Oct-08 & 0.0034 & 0.0065 & 0.0102 & 0.0134 \\ \hline
01-Oct-09 & 0.0003 & 0.0015 & 0.0025 & (0.0004) \\ \hline
\end{tabular}
\end{document}
 ```

May experience a time correcting market inefficiencies,  and the result is quoted prices misaligned with the theoretical ones.

1. As we have seen,  the biggest discrepancy occurs for October 1st,  2008. Let’$s$ focus on that date and consider the 1-year Forward Exchange rate.
As mentioned above,  the difference F quoted − F *computed* > 0,  that is,  equivalent to F quoted > F *computed*. The rule of thumb for arbitrage is to buy cheap and sell dear. This his means “buy computed” and “sell quoted.” The computed Forward Exchange rate is a *synthetic* price that we pay if we set up a strategy that replicates the payoff of a forward contract,  while the quoted Forward Exchange rate is what we obtain when entering into a forward position (just sign a contract,  much easier than setting up a replicating strategy). We already know that we enter into a short forward contract to sell 1 euro for dollars (this is the “sell quoted” - we are selling euros and buying dollars; remember that with exchange rates,  we are long / short the Foreign currency). On the other side,  we have to set up a strategy that replicates the payoff of a long forward position to buy 1 euro for dollars. Let’s start by matching the payoffs at maturity.
A long forward contract,  at maturity,  entails:
- An outflow (we pay) of dollars - An inflow (we receive) of euros
To pay dollars tomorrow,  we simply borrow something in the US. To receive euros tomorrow,  we have to invest something in Europe today. How much? Here,  we have to remember our goal. We are matching the cash flows of a forward contract,  and a forward contract does not require any cash flow when we enter into it. As our strategy so far requires borrowing in dollars and investing in euros today,  to get a cash flow equal to 0,  we have to match the amount we borrow with the amount we invest,  or in other words,  we have to invest in Europe the full amount borrowed in the US. To do this,  we just need to exchange the dollars for euros today. The last thing we need to understand is how much to borrow in dollars today. As the forward exchange rate tells us “how many dollars we have to pay in exchange for 1 euro at maturity”,  following our logic of matching the cash flows of a forward contract,  we want to borrow today (in dollars) a sum that will give us 1 euro tomorrow: that’s the very definition of present value.
Summing up,  the “buy computed” strategy requires (please note that the amounts in the first and third rows are in different currencies,  so they cannot be summed):

```latex
\usepackage{booktabs}
\usepackage{amsmath}
\usepackage{amsfonts}
\begin{document}
\renewcommand{\arraystretch}{1.3}
\small
\begin{tabular}{|c|c|c|c|}
\hline
\textbf{Today $t=0$} & \textbf{In formulas} & \textbf{At maturity $t=T$} & \textbf{In formulas} \\ \hline
Borrow in \underline{dollars} the PV or 1 euro & $+e^{-r_e} \cdot M_0$ & Pay \underline{dollars} & $-M_0 \cdot e^{(r_{US} - r_e) \cdot T}$ \\ \hline
Exchange the amount borrowed into euros & & Exchange the euros received into dollars & \\ \hline
Invest the present value of 1 euro today & $-e^{-r_e}$ & Receive 1 euro & $+1$ \\ \hline
\end{tabular}
\end{document}
```

Table: Arbitrage Strategy - Borrowing in dollars and receiving euros
Finally,  we can consider the cash flows from both the short position (again,  short since we are selling euros) and the synthetic long (again,  long since we are buying euros) forward position,  which are reported in Table 5. Please note that the amount MT is simply the value,  in dollars,  of 1 euro at time T.

```latex
\usepackage{booktabs}
\begin{document}
\renewcommand{\arraystretch}{1.3}
\small
\begin{tabular}{|c|c|c|}
\hline
\textbf{Amounts in USD} & \textbf{$t=0$} & \textbf{$t=T$} \\ \hline
Short forward position & 0 & $F^{quoted} - M_T$ \\ \hline
Synthetic long forward position & 0 & $M_T - F^{computed}$ \\ \hline
\textbf{TOTAL} & 0 & $F^{quoted} - F^{computed} > 0$ \\ \hline
\end{tabular}
\end{document}
```

Applying the above formulas to our case,  the strategy becomes:

- Short a forward contract to sell 1 euro for 1.3960 dollars in one year.
- Borrow e−0.0535 · 1.4021 = 0.9479 · 1.4021 = 1.3290 dollars today (October 1st,  2008).
- Exchange 1.3290 dollars for euros,  obtaining 0.9479 euros.
- Invest 0.9479 euros at re = 5.35%.
At maturity,  we will have:
- Pay 1 euro (from the short forward position).
- Receive 1.3960 dollars.
- Receive 1 euro (from the long synthetic forward position).
- Pay 1.3290 · e0.0396 = 1.3827 dollars.
The net cash flow will be a positive amount equal to 1.396 − 1.3827 = 0.0134
dollars per euro traded. If we apply the same strategy on $100 m,   the arbitrage is supposed to generate a positive cash flow at maturity equal to $1.337 m.