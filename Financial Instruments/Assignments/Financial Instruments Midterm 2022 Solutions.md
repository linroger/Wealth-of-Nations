---
cssclasses:
  - academia
aliases: 
linter-yaml-title-alias: FINANCIAL INSTRUMENTS MIDTERM SOLUTIONS
tags:
  - "#financial-instruments"
  - "#foreign-exchange-market"
  - "#exchange-rates"
  - "#risk-management"
  - "#swap-rates"
  - "#binomial-trees"
title: Financial Instruments Midterm 2022 Solutions
---

---

title: FINANCIAL INSTRUMENTS MIDTERM SOLUTIONS

aliases: [FINANCIAL INSTRUMENTS MIDTERM SOLUTIONS]

linter-yaml-title-alias: FINANCIAL INSTRUMENTS MIDTERM SOLUTIONS

# Financial Instruments Midterm 2022 Solutions

Problem 1. (15 Points) True-False Questions (There Are 3 Of Them). Grade Depends On Completeness Of Answer.

(a) (5 points) In a [Foreign Exchange](Foreign%20Exchange%20Quoting%20Conventions.md) forward contract,  the value of the forward contract is always positive.

> [!ANSWER]
> False: the value of a forward exchange contract is given by
$$f_\{t,   T\}=M(t)\cdot e^\{-r_\{e\}\cdot(T-t)\}-F_\{0,   T\}\cdot e^\{-r_\{\mathrm\{g\}\}\cdot(T-t)\}=e^\{-r_\{\mathrm\{g\}\}\cdot(T-t)\}\cdot[F_\{t,   T\}-F_\{0,   T\}]$$
where$M(t)$is the spot rate (e.g. USD / EUR exchange rate,  that is the price in USD of 1 euro) at time$t$,  $r^e$is the continuously compounded EUR risk free rate and$r_\text\{usd\}$is the continuously compounded USD risk free rate. As we know,  at inception,  $f_\{0,   T\} = 0$,  since$F_\{0,   T\} = M_0 \cdot e^\{(r\uc0\u8722 r_e)\'b7T\}$. At any time$t$such that$0 < t < T$the value of the contract can actually be either positive or negative. If,  for example,  the dollar appreciates,  that is if$M_t$falls significantly,  then the value of the contract can become negative.
> An intuitive way of thinking about it is that as at time$t = 0$we have signed a contract to buy 1 EUR in$T$years,  at a given price$F_\{0,   T\}$,  but now the market conditions are much more favorable (as$F_\{t,   T\} < F_\{0,   T\}$) therefore under the initial contract we have agreed to pay "too much" for a EUR. This means that the value of our position is negative.
###### (B) IT IS POSSIBLE TO CALCULATE THE SWAP RATE$S$OF A SWAP ON ANY UNDERLYING FACTOR$X_T$(E.G. EXCHANGE RATES,  GOLDS,  OIL) WITH SPOT RATE$X_T$AND NET CASH FLOWS$X_T - S$FROM THE CURRENT FORWARD RATES$F_\{T,   T\}$ON THE FACTOR ITSELF
> [!ANSWER]
> True: One example we know well is a [Foreign Exchange](Foreign%20Exchange%20Quoting%20Conventions.md) swap. The swap requires an exchange of cash flows in two different currencies.
At each time period,  the total cash flow can be considered as a purchase of some units of foreign currency in exchange for some known quantity of home currency. In other words each cash flow represents a forward position (purchase or sale,  depending on the swap) on the foreign currency. In order to prevent arbitrage opportunities therefore the swap rate has to be such that the sum of the values of the various forward positions$^\{1\}$is equal to the value of the swap. Given this it is therefore possible to compute the swap rate$K$from the current forward curve. [The following example was not required to get full credit]. Consider a simple 3 years swap that requires to pay$c = 8$USD and to receive$K$EUR at the end of each year (we don't consider the exchange of principal for simplicity).
The cash flows will be
$$\begin{array}{llr}\text{Maturity}&\text{USD}&\text{BPD}\\1\text{year}&2\%&3\%\\2\text{years}&3\%&3\%\end{array}$$
The two streams of payments (two columns) are two annuities in two different currencies.
One way to compute the value of$K$is to find a number such that the value of the two annuities (in the same currency) matches. To do this we need the zeros in both currencies and the spot exchange rate. An alternative way is to consider Table (1) row by row. Each row represents the purchase of$K$EUR for 8 USD,  or in other words the purchase of 1 EUR for$\frac\{8\}\{K\}$dollars. Therefore each row represents a long forward position in EUR,  with a delivery price equal to$\frac\{8\}\{K\}$. Let's set$K^\text\{fwd\} = \frac\{8\}\{K\}$. Given the current forward curve we can compute the value of each forward position in Table (1) using$$f_\{0,   T\}=e^\{-r_\{5\}\cdot T\}\cdot\left(F_\{0,   T\}-K^\text\{fwd\}\right)$$We will then obtain$f_\{0,   1\}$,  $f_\{0,   2\}$and$f_\{0,   3\}$. Now since the swap is a sum of three forward positions,  its value has to be equal to the sum of the values of each forward contract. In addition,  at inception the swap rate is such that the value of the SWAP is 0. Therefore by setting$$f_\{0,   1\}+f_\{0,   2\}+f_\{0,   3\}=0$$We have an equation in 1 unknown ($K$),  that we can easily solve. We can apply the same reasoning to any kind of swap (commodity,  equity,  etc.).
###### (C) THE CURRENT EXCHANGE RATE BETWEEN THE UNITED STATES AND CANADA IS 1.02 US DOLLARS

per Canadian dollar. The one-year forward exchange rate is 1.03 US dollars per Canadian dollar. The market must be expecting that over the next year the US

dollar will depreciate relative to the Canadian dollar.

![|500](IMG-20240913171226876.png)

> [!ANSWER]
> False The forward exchange rate is determined by the current exchange rate and the interest rate differential between the US and Canada. Further the forward rate reflects both expectations and risk premia.
#### PROBLEM 2. (25 POINTS) BINOMIAL TREES

SUPPOSE THAT STOCK XYZ,  WHOSE CURRENT PRICE IS\$50,  CAN EITHER INCREASE BY$U = 1.1$OR DECREASE BY${} D = \frac{1}{1.1} {}$EACH YEAR OVER THE NEXT 2 YEARS. THE CONTINUOUSLY-COMPOUNDED INTEREST RATE IS 1% PER YEAR

![|500](IMG-20240913171230388.png)

###### (A) (10 POINTS) WHAT IS THE NO-ARBITRAGE PRICE OF A EUROPEAN PUT OPTION WITH STRIKE PRICE OF$48 AND MATURITY OF 2 YEARS

Solution: Dynamics for the stock price and option payoff:

> [!ANSWER]
> - (a) (10 points) What should be the price of the Capital Protected Note? Is it properly priced? What is the Delta of the Note?-
> - The risk-neutral probability of an "up" move is:
>   - $q' = \frac{e^{r\delta t} - d}{u - d} = \frac{e^{1\%} - 1/1.1}{1.1 - 1/1.1} = 0.5288$
>
> - The price of the option at time zero is therefore:
>   - $p_0 = e^{-0.01\times2}(1 - 0.5288) \times 6.78 = 1.43$
>
> - Consider now an 2-year *look-back* call option on the stock with a strike price of$50.
>   - With this option,  at maturity the buyer as the option to pay the strike price and receive the *maximum* value the stock achieves during the life of the option.
>   - The maximum stock price,  $S_{max}$across paths and value of the option are:
>
> - Since we need to replicate the option to answer the question below,  let’s price the option with replication. The delta and bond positions at each node are given by:
>   - $\Delta_{1,   u} = \frac{V_{2,   uu} - V_{2,   ud}}{S_{2,   uu} - S_{2,   ud}} = \frac{10.5 - 5}{60.5 - 50} = 0.5238$
>   - $B_{1,   u} = e^{-r\delta t}(V_{2,   uu} - \Delta_{1,   u}S_{2,   uu}) = e^{0.01}(10.5 - 0.5238 \times 60.5) = -20.98$
>   - $V_{1,   u} = \Delta_{1,   u} \times S_{1,   u} + B_{1,   u} = 0.5238 \times 55 - 20.98 = 7.8299$
>   - $\Delta_0 = \frac{V_{1,   u} - V_{1,   d}}{S_{1,   u} - S_{1,   d}} = \frac{7.8299 - 0}{55 - 45.45} = 0.8203$
>   - $B_0 = e^{-r\delta t}(V_{1,   u} - \Delta_0S_{1,   u}) = e^{-0.01}(7.8299 - 0.8203 \times 55) = -36.9142$
>   - $V_0 = \Delta_0 \times 50 + B_0 = 0.8203 \times 50 - 36.9142 = 4.0995$
For each Capital Protected Note hold 1.1347 1-year options.
To hedge this note we would hold the short data option in the proportion:
 For each Capital Protected Note hold 1.1347 1-year options.
#### (D) (5 POINTS) IF IMMEDIATELY AFTER YOU ENTER INTO THE HEDGING POSITIONS OF PART (B),  THE S&P500 INCREASES IN PRICE. DESCRIBE $IN$ $WORDS$ THE DIRECTIONS IN WHICH YOU WOULD HAVE TO CHANGE YOUR POSITIONS AND WHY. (INTUITION ONLY,  NO CALCULATIONS HERE)
> [!ANSWER] Solution:
> Yes because the Delta of each position increases but not by the same amount.