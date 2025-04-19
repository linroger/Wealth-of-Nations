---
cssclasses:
  - academia
linter-yaml-title-alias: TREASURY TRANSACTION AND CASH FLOW ANALYSIS
title: Teaching Note 2Interest Rate Risk Management And Factors
tags:
  - coupon_bond
  - duration
  - interest_rate_risk
  - pvbp
  - zero_coupon_bond
aliases:
  - Duration
  - Interest Rate Risk
  - PVBP
key_concepts:
  - Duration definition
  - Interest rate sensitivity
  - Macaulay duration
  - Modified duration
  - Portfolio duration calculation
  - Price value basis point
  - Zero coupon bond duration
---

 ![500](9d5e1f9101a284fff965c5728068e694.webp)

- Interest rates vary quite dramatically over time.
## INTEREST RATE RISK MANAGEMENT

 ![500](508c4b601dd8f61c1d50be915c6d5c21.webp)

- … and so do bond prices.
## INTEREST RATE RISK MANAGEMENT: DURATION
- The *duration - of a security is defined as the sensitivity of the security's price to
small,  uniform changes in the yield curve.
- Traditionally,  the duration is defined with respect to changes in yield-to-maturity. - However,  it is convenient to introduce it using the continuously compounded yield
$r(t,            T)$,  as formulas are easier and the interpretation is also easier.
- The duration of an asset is its sensitivity to small,  uniform changes in$r(t,            T)$.
- That is,  the change in the security's price when we apply a uniform increment
"dr" to the yield curve$r(t,            T)$,  to get$r(t,            T)+ dr$
- Hence,  we define the duration of a security with price P by
$$D_{P}=-\frac{1}{P}\frac{d\ P}{d\ r}$$
- This definition is all you need to remember,  as everything follows from here.
## EXAMPLE: DURATION OF A ZERO COUPON BOND
- Consider a zero coupon bond - with time to maturity T and price$Z(t,            T)$. By
applying the definition we have:
$$D_{Z,           T}=-\frac{1}{Z(t,           T)}\frac{dZ(t,           T)}{dr}$$$$=-\frac{1}{Z(t,           T)}\times\left[-(T-t)\times e^{-r(t,           T)\times(T-t)}\right]$$$$=-\frac{1}{Z(t,           T)}\times\left[-(T-t)\times Z(t,           T)\right]$$$$=T-t$$
  - The duration of a zero coupon bond is simply equal to its time to maturity$T-t$.
## DURATION OF A PORTFOLIO OF SECURITIES
- We now show that the duration of a portfolio of securities is just the weighted
average of the durations of the singles securities (where the weights are the relative
holdings).
- Suppose we have N1 units of security 1 and N2 of security 2. Let P1 and P2 be
the prices of the two securities and D1 and D2 their durations,  respectively.
- Let Π be the value of the portfolio
$$\Pi=N_{1}P_{1}+N_{2}P_{2}$$
- We can then compute:
$$D_{\Pi}\;=\;-\frac{1}{\Pi}\frac{d\;\Pi}{d\;r}$$$$\;=\;\frac{1}{\Pi}\left(-N_{1}\times\frac{d P_{1}}{d r}-N_{2}\times\frac{d P_{2}}{d r}\right)$$$$\;=\;\frac{1}{\Pi}\left(N_{1}P_{1}\times(-1)\frac{1}{P_{1}}\frac{d P_{1}}{d r}+N_{2}P_{2}\times(-1)\frac{1}{P_{2}}\frac{d P_{2}}{d r}\right)$$
## DURATION OF A PORTFOLIO OF SECURITIES
- Obtaining
$$D_\text{П }=\left.w_1D_1+w_2D_2\right.\tag{1}$$
- where
$$w_i=\frac{N_iP_i}\Pi \tag{2}$$
- Clearly,  the same derivation can be applied for any number of assets.
## EXAMPLE: DURATION OF A COUPON BOND
- We know a bond is equivalent to a portfolio of zero-coupon bonds
$$P(0,           T)=\sum_{i=1}^{n}c(T_{i})Z(0,           T_{i})$$
- where$c (T_i) = \frac{c}{2}$for$i < n$
- and$c (T_n) = \frac{c}{2} + 100$.
- ##### Step 1: Apply (2) to have

$$w_{i}=\frac{c(T_{i})Z(0,           T_{i})}{P(0,           T)}$$

- ##### Step 2: Use (1)

$$D\ =\ -\frac{1}{P(0,           T)}\frac{dP(0,           T)}{dr}=\sum\limits_{i=1}^{n}w_{i}D_{Z,           T_{i}}=\sum\limits_{i=1}^{n}w_{i}\times T_{i}\tag{3}$$

- The duration of a Coupon Bond is a weighted average of times to maturity
- From (3),  we can compute the percentage change in the bond due to a small parallel shift in the yield function$r(t,            τ)$as
$$\frac{dP}{P}\approx-D\times dr$$
  - Hence,  if we hold a portfolio of 10-year at-par coupon bonds with duration equal to 5,  we know that a one-basis point increase in the yield function ($dr=\%$) is going to change the value of the bond approximately by$-5\times/100\times\$100$million (par amount)$=-\$50,  000$.
![|800](Z.%20Clippings/Lecture%20Note%202-%20Interest%20Rate%20Risk%20Management%20And%20Factors-20240407053754286.png)
## DURATION DEFINITIONS
- We defined the duration as
$$D=-\frac{1}{P}\frac{dP}{dr}$$
- where$r$is the continuously compounded interest rate.
- This definition entails also the interpretation of duration as the discounted time weighted cash flows (equation (3)).
- With discrete compounding the two things are not exactly the same and take different names:
## MACAULAY DURATION
  - Consider a security with yield to maturity$y$.
  - Its price is$$P=\sum\limits_{j=1}^{n}\frac{c/2}{\left(1+\frac{y}{2}\right)^{j}}+\frac{100}{\left(1+\frac{y}{2}\right)^{m}}\tag{4}$$
- The Macaulay duration is defined as
$$D^{M c}=-\frac{(1+y/2)}{P}\frac{d P}{d y}$$
- Some algebra shows
$$D^{M c}=\frac{1}{2}\sum_{j=1}^{n}w_{j}\times j$$
where
$$w_{j}=\frac{1}{P}\left(\frac{c/2}{\left(1+\frac{y}{2}\right)^{j}}\right),           \;w_{n}=\frac{1}{P}\left(\frac{c/2+100}{\left(1+\frac{y}{2}\right)^{n}}\right)$$
## MODIFIED DURATION
- The modified duration is instead defined as
$$M D=-\frac{1}{P}\frac{d P}{d y}$$
where P is given in (4).
- It is easy to see that
$$M D=\frac{D^{M c}}{\left(1+\frac{y}{2}\right)}$$
## THE PRICE VALUE OF A BASIS POINT (PVBP)
- In the industry traders often use a related measure of risk,  called the PVBP.
- This is simply defined as
$$PVBP=-\frac{dF}{dy}\times0.0001=MD\times P\times0.0001$$
- This is also called the dollar value of 0.0001,  or **DV01**.
- Sometimes expressed per$1 million of face value.
## EXAMPLE: SPREAD TRADES
- A trader is evaluating the shape of the yield curve.
- The spread between the 30 year T-Bond and the 2 year T-Note is 266 bps.
# Teaching Note 2Interest Rate Risk Management And Factors
## TRANSACTIONS AT DATE $T$
- **Borrow Cash and Pay for 2-year Note**
		  - Post 2-year Note as Collateral:$(100.4360 +) \times 10,           000 \times 641 = (643,           988,           470)$
- **Borrow 30-year T-Bond and Sell**
		  - Post Cash as collateral:$(108.8405 +) \times 10,           000 \times 100 = 109,           249,           154$
## TRANSACTIONS AT DATE $T + 2$
- **Sell 2-year note**$(100.5967 +) \times 10,           000 \times 641 = 645,           212,           011$*(A)*
- **Repay the amount borrowed plus Repo interest**$643,           988,           470 \times (1 + 2 \times \frac{}{360}) = (644,           167,           356)$*(B)*
- **Collect the cash plus interest**$109,           249,           154 \times (1 + 2 \times \frac{}{360}) = 109,           278,           894$*(C)*
- **Buy the 30-year T-bond to cover the short position**$(109.8701 +) \times 10,           000 \times 100 = (110,           326,           800)$*(D)*
## PROFITS CALCULATION
- Profits (Losses) =$(A) + (B) + (C) + (D) = (3,           251)$
- The trader lost money,  even if the spread did increase.
- The reason are the transaction costs,  such as [[Class Note 9 Bid and Ask Prices With Private Information|bid-ask spreads]] in the Treasury market and in the Repo market.
## MARKET DATA AT TIME $T$
- **30-year T-Bond**
		  - Bid: 108.8405
		  - Ask: 108.903
		  - Yield$y$: 7.96%
		  - Accrued Interest:
		  - PVBP: 1200.643
- **2-year T-Note**
		  - Bid: 100.3735
		  - Ask: 100.4360
		  - Yield$y$: 5.30%
		  - Accrued Interest:
		  - PVBP: 187.3602
- ![|500](Z.%20Clippings/Lecture%20Note%202-%20Interest%20Rate%20Risk%20Management%20And%20Factors-20240407060007687.png)
## MARKET DATA AT TIME $T + 2$
- **30-year T-Bond**
		  - Bid: 109.8076
		  - Ask: 109.8701
		  - Yield: 7.88%
		  - Accrued Interest:
		  - PVBP: 1218.246
- **2-year T-Note**
		  - Bid: 100.5967
		  - Ask: 100.6592
		  - Yield: 5.18%
		  - Accrued Interest:
		  - PVBP: 187.4086
-  ![500](Z.%20Clippings/Lecture%20Note%202-%20Interest%20Rate%20Risk%20Management%20And%20Factors-20240407060056789.webp)
## OBSERVATIONS AND CONCLUSIONS
- The new spread is 270 basis points,  hence the view was right.
- Did the trader png any money? No,  due to transaction costs.
## TABLES
### INITIAL MARKET DATA AT TIME$T$

| Security      | Bid       | Ask      | Yield   | Accrued Interest | PVBP      |
|---------------|-----------|----------|---------|------------------|-----------|
| 30-year T-Bond| 108.8405  | 108.903  | 7.96%   | 0.408654          | 1200.643  |
| 2-year T-Note | 100.3735  | 100.4360 | 5.30%   | 0.03022           | 187.3602  |

### MARKET DATA AT TIME$T + 2$

| Security       | Bid      | Ask      | Yield | Accrued Interest | PVBP     |
| -------------- | -------- | -------- | ----- | ---------------- | -------- |
| 30-year T-Bond | 109.8076 | 109.8701 | 7.88% | 0.456731         | 1218.246 |
| 2-year T-Note  | 100.5967 | 100.6592 | 5.18% | 0.06044          | 187.4086 |

- The trader has a view: The spread will increase in the next few days.
- How can the trader devise a trading strategy to bet on their view,  without taking on interest rate risk?
- First,  if spread increases,  it must be the case that the price - of 30-year bond goes down more than the price of the 2-year bond (or up less!).
- Hence,  to profit from the movement,  we need a short position in the long-term bond and a long position in the short-term bond.
> [!NOTE]
> The trader in question expects the yield spread between the 30-year Treasury Bond (T-Bond) and the 2-year Treasury Note (T-Note) to widen. If the spread is anticipated to increase,  this implies that the yield on the 30-year bond is expected to rise more than the yield on the 2-year note,  or equivalently,  the price of the 30-year bond is expected to fall relative to the price of the 2-year note.
>
> Here's how the trader could devise a trading strategy to capitalize on this view without taking on interest rate risk:
>
> 1. **Short the 30-year T-Bond**: By short selling the 30-year T-Bond,  the trader profits if the bond's price decreases,  which corresponds to an increase in its yield. Short selling involves borrowing the security and selling it with the obligation to buy it back in the future. If the bond's price falls as expected,  it can be repurchased at the lower price,  and the difference represents the profit.
>
> 1. **Long the 2-year T-Note**: Simultaneously,  the trader should take a long position in the 2-year T-Note. By buying the 2-year T-Note,  the trader stands to profit if its price doesn't fall as much as the 30-year T-Bond or if it rises. This is because a smaller increase in yield (or a decrease) for the 2-year note means its price remains stable or increases relative to the 30-year bond.
>
> This strategy is known as a **duration-neutral spread trade**. It aims to have equal dollar duration in both the long and the short positions,  thereby neutralizing the interest rate risk. The dollar duration is a measure of how much the value of a security will change in response to a change in interest rates. By balancing the dollar duration of the long and short positions,  the trader is insulated from overall movements in interest rates and is specifically betting on the change in the yield spread.
>
> The rationale behind the strategy:
>
> - If the trader is correct and the yield spread widens,  the yield on the 30-year T-Bond will rise more than the yield on the 2-year T-Note,  leading to a fall in the 30-year bond's price relative to the 2-year note's price.
> - If the yield on the 30-year T-Bond increases significantly while the yield on the 2-year T-Note increases marginally (or not at all),  the short position in the 30-year T-Bond will be profitable,  and the long position in the 2-year T-Note will either be profitable or will lose less than the 30-year T-Bond.
> - This trading strategy allows the trader to profit from the expected change in the yield curve shape without taking a directional bet on interest rates.
>
> To ensure that the interest rate risk is hedged properly,  the trader will have to adjust the sizes of the short and long positions so that the duration of the positions offsets one another. This involves calculating the dollar duration of each position and ensuring that the dollar duration weighted position in the 30-year T-Bond is equal and opposite to that of the 2-year T-Note.
- Let$n_2$and$n_{30}$be the units of 2-year notes and 30 year bonds involved in the trading strategy.
- Then,  the trader can hedge the interest rate risk by setting
$$n_{2}\times P V B P_{2}=n_{30}\times P V B P_{30}$$
- Suppose$n_{30} = 100$million (par amount),  we can compute the amount of two year notes necessary to hedge the position:
$$n_{2}=100\times{\frac{1200.643}{187.3602}}=641$$
- The trader will go long 641 million (par amount) of the two year bond,  and go short 100 million par amount of the 30-year T-Bond.
- How is this done in practice?
	- Through the Repo Market.
	- The trader can enter into a repo at 5% and a reverse repo at 4.9%.
	- Spread between [[Class Note 12 Part 2 Repos|repos]] is the profit for the Repo Dealer,  who borrows money at 4.9% and lends it at 5%.
	- Finally,  suppose hair cut = 0.
- We have the following transactions at Date t
# TRANSACTIONS AT DATE T
## WE HAVE THE FOLLOWING TRANSACTIONS AT DATE T
### DATE TRANSACTION CASH FLOWS
- Date t 1. Borrow Cash and pay for 2-year Note
  Post 2-year Note as Collateral
  $$\begin{align*}
  (100.4360 + ) \times 10,           000 \times 641 &= (643,           988,           470)
  \end{align*}$$
- 2. Borrow 30-year T-Bond and sell
  Post Cash as collateral
  $$\begin{align*}
  (108.8405 + ) \times 10,           000 \times 100 &= 109,           249,           154
  \end{align*}$$
- These cash flows are just the nominal amount paid or received in the market. The trader is borrowing/lending money with zero hair cut,  it has a zero-net position!
- Suppose that at time$t + 2$the new market data are

| Time t         | Bid        | Ask        | Yield $y$ | Interest   | PVBP |
| -------------- | ---------- | ---------- | --------- | ---------- | ---- |
| 30 year T-Bond | $108.8405$ | $108.903$  | $7.96\%$  | $1200.643$ |      |
| 2-year T-Note  | $100.3735$ | $100.4360$ | $5.30\%$  | $187.3602$ |      |

- The new spread is 270 basis points,  hence the view was right. **Did the trader make any money?**
## PROFITS?
- Profit (Losses) = (A) + (B) + (C) + (D) =$3,           251$
- The trader lost money,  even if the spread did increase.
- The reason,  of course,  are the transaction costs,  such as [[Class Note 9 Bid and Ask Prices With Private Information|bid-ask spreads]] in the Treasury market and in the Repo market.
### DATE$T + 2$TRANSACTIONS
1. Sell 2-year note
	This becomes:
$$(100.5967 +) \times 10,           000 \times 641 = 645,           212,           011$$
1. Repay the amount borrowed plus Repo interest. This is
$$643,           988,           470 \times (1 + 2 \times /360) = 644,           167,           356$$
1. Collect the cash plus interest
$$109,           249,           154 \times (1 + 2 \times /360) = 109,           278,           894$$
1. Buy the 30-year T-bond to cover the short position
$$(109.8701 +) \times 10,           000 \times 100 = 110,           326,           800$$
  Profit (Losses) = (A) + (B) + (C) + (D) =$3,           251$
- The trader lost money,  even if the spread did increase.
- The reason,  of course,  are the transaction costs,  such as [[Class Note 9 Bid and Ask Prices With Private Information|bid-ask spreads]] in the Treasury market and in the Repo market.
- The trader lost money,  even if the spread did increase. - The reason,  of course,  are the transaction costs,  such as [[Class Note 9 Bid and Ask Prices With Private Information|bid-ask spreads]] in the
Treasury market and in the Repo market.
## INTEREST RATE RISK MANAGEMENT: CONVEXITY
- Convexity measures the curvature of a security with respect to interest rates
$$C=\frac{1}{P}\frac{d^{2}\ P}{d\ r^{2}}$$
- Example 1. From the definition of a zero coupon bond:
$$Z(t,           T)=e^{-r(t,           T)(T-t)}\Longrightarrow C_{Z}=\frac{1}{Z(t,           T)}\frac{d^{2}\ Z(t,           T)}{\ d\ r^{2}}=(T-t)^{2}$$
- Example 2. From the definition of a coupon bond:
$$P_{c}(t,           T)={\frac{c}{2}}\sum\limits_{i=1}^{n}Z(t,           T_{i})+Z(t,           T_{n})\Longrightarrow C={\frac{1}{P_{c}}}{\frac{d^{2}\ P_{c}}{d\ r^{2}}}=\sum\limits_{i=1}^{n}\ w_{i}\ (T_{i}-t)^{2}$$
- where wi are the same as in previous slide.
- Given D and C,  a better approximation of the return of a security is
$${\frac{d\ P}{P}}\approx-D\ d r+{\frac{1}{2}}\ C\ d r^{2}\tag{5}$$
 ![500](Z.%20Clippings/Lecture%20Note%202-%20Interest%20Rate%20Risk%20Management%20And%20Factors-20240407055320856.png)
## POSITIVE CONVEXITY: GOOD NEWS FOR AVERAGE RETURNS
- Suppose we have invested$100 million in a 20-year zeropngon bond.
- Using Equation (5) and given D = 20 and C = 202 = 400,  we find$$\left[\frac{dF}{P}\right]\approx-20\times E[dr]+\frac{1}{2}\times400\times E[dr^{2}]\tag{6}$$
- Predicting variation in interest rates over a short period (daily) is very hard. So,  $E[dr]=0$is a good approximation. However,  note that$E[dr^{2}]=Var(dr)>0$.
 ![500](Z.%20Clippings/Lecture%20Note%202-%20Interest%20Rate%20Risk%20Management%20And%20Factors-20240407055340553.png)
## POSITIVE CONVEXITY: GOOD NEWS FOR AVERAGE RETURNS
  - From data,  we can estimate the daily variance of intepng rates of about$E[dr^{2}]=5.5351\times10^{-007}$,  implying$$E\left[\frac{dF}{P}\right]=-20\times0+\frac{1}{2}\times400\times E[dr^{2}]=1.11\times10^{-04}>0 \tag{7}$$
  - Although this number seems extremely small,  it is a daily expected return.
	  - Annualized expected return from convexity = 1.11 × 10−04 × 252 = 2.79%
 - Similarly,  considering the$100 million investment,            convexity yields a daily dollar return of$11,  070 = 1.11 × 10−04 × 100 million.
- Is this positive average return stemming from the fluctuation of the level of interest rates a "free lunch"?
- No: As we shall see more formally later on,  this positive average return on the investment is counterbalanced by a lower yield to maturity of the bond,  everything else equal.
## DURATION AND CONVEXITY APPROXIMATION: EXAMPLE
- A pension fund buys$100 million (par value) of a 10-year,  5% coupon bond.
- Let the yield curve be flat at the continuously compounded rate of 4.5%.
- =⇒$P_c(t,            T) =\$103.58,  D = 8.03,  and \ C = 73.87.$
- The approximate losses from an increase in$r$of 1% are$$\frac{dP}{P}\approx-D\times0.01=-0.0803=-8\%\tag{8}$$$$\frac{dP}{P}\approx-D\times0.01+\frac{1}{2}\times C\times(0.01)^{2}=-0.07662=-7.66\%\tag{9}$$
  - To check accuracy,  we can compute the exact loss from an increase of the term structure by 1%.
  - Using the pricing formula with$r=4.5\%$and$r=5.5\%$,  we obtain that price declines to$95.63from$103.58:$$$\frac{dP}{P}=\frac{\$95.63-\$103.58}{\$103.58}=-7.67\%$$
- The "convexity" measure is quite accurate
## INTEREST RATE RISK MANAGEMENT: DURATION HEDGING
- The pension fund is worried about potential losses from an increase in rates.
- The fund decides to hedge by buying k 10-year zero-coupon bond$Z(0,            T)$.
- We have$Z(0,            T) =\$63.76$.,            and$D_z = 10$.
- Denoting again by P the value of the bond (P =$103.58),            what is the position k in the zero coupon bond such that the portfolio$V = P + k × P_z(0,  T)$is insensitive to a parallel shift in the yield curve?
- Condition$dV = 0$implies
$$k=-\frac{D\times P}{D_{z}\times P_{z}(0,           T)}=\frac{8.03\times103.58}{10\times63.76}=-1.3045\tag{10}$$
  - Assume for simplicity that fund achieves this short position through the repo market at zero haircut (i.e. the short position is achieved at zero cost for the fund.)
## HOW DOES DURATION HEDGING PERFORM ?
$$
\begin{aligned}
& \text{Spot Curve Change in} \\
& \begin{array}{|c|c|c|c|c|}
\hline
\textbf{Shift} & P_c & Z(0,           T) & \textbf{Position} & \textbf{Portfolio Value} \\
\hline
\text{Initial Values} & 103.58 & 63.76 & -1.3045 & \\
dr = 0.1\% & 102.75 & 63.13 & -1.3045 & -0.0003 \\
dr = 1.0\% & 95.63 & 57.69 & -1.3045 & -0.0318 \\
dr = 2.0\% & 88.38 & 52.20 & -1.3045 & -0.1210 \\
dr = -0.1\% & 104.41 & 64.40 & -1.3045 & -0.0003 \\
dr = -1.0\% & 112.29 & 70.47 & -1.3045 & -0.0350 \\
dr = -2.0\% & 121.84 & 77.88 & -1.3045 & -0.1474 \\
\hline
\end{array}
\end{aligned}
$$

$$d\;V=-D\;P_{c}\;dr+\frac{1}{2}\;P_{c}\;C\;dr^{2}+k\;\left(-D_{z}\;Z\;dr+\frac{1}{2}\;Z\;C_{z}\;dr^{2}\right)$$

$$
=-\left(D\;P_{c}+k\;D_{z}\;Z\right)\;dr+\frac{1}{2}\;\left(P_{c}\;C+k\;Z\;C_{z}\right)\;dr^{2} \tag{11}$$ 
- Duration hedging takes care of the first term but not of the second,            which is always negative in our example.
## INTEREST RATE RISK MANAGEMENT: DURATION AND CONVEXITY HEDGING
- Let $P_1$ and $P_2$ be the prices of two securities (e.g. short-term and a long-term zeros),            with $D_1,           D_2,           C_1$,            and $C_2$ their durations and convexities,            respectively.
- Let $k_1$ and $k_2$ be the positions in the bonds. The value of the hedged portfolio is
$$V=P_{c}+k_{1}\ P_{1}+k_{2}\ P_{2}\Longrightarrow d\ V=d\ P_{c}+k_{1}\ d\ P_{1}+k_{2}\ d\ P_{2}$$
  - Developering the expression and pulling together the terms in$dr$and$dr^{2}$:$$dV=-\left(D\ P+k_{1}\ D_{1}\ P_{1}+k_{2}\ D_{2}\ P_{2}\right)dr$$$$+\frac{1}{2}\ \left(C\ P+k_{1}\ C_{1}\ P_{1}+k_{2}\ C_{2}\ P_{2}\right)\ dr^{2}$$
# HEDGING WITH DURATION AND CONVEXITY
## HEDGING EQUATIONS
- Setting $dV = 0$ yields two equations for hedging:
        - **Delta Hedging** $k_1 D_1 P_1 + k_2 D_2 P_2 = -D P_c$
        - **Convexity Hedging** $k_1 C_1 P_1 + k_2 C_2 P_2 = -C P_c$
- The solution to this system of equations is:
        - For $k_1$: $k_1 = -\frac{P_c}{P_1} \left( \frac{D_2 C_1 - C_2 D_1}{D_1 C_2 - C_1 D_2} \right)$
        - For $k_2$: $k_2 = -\frac{P_c}{P_2} \left( \frac{D_1 C_2 - C_1 D_2}{D_2 C_1 - C_2 D_1} \right)$
## EXAMPLE HEDGING STRATEGY
- Given $P_c$,            $D_1$,            $D_2$,            $C_1$,            and $C_2$,            the hedge ratio $k_1$ and $k_2$ are calculated as $k_1 = -0.4562$ and $k_2 = -1.1737$.
## SPOT CURVE SHIFT AND HEDGING OUTCOME
- Panel B: Duration and Convexity Hedging
        - **Spot Curve Shift**
          - Initial Value: $P = 103.58$,            $P_z(0,            T_1) = 91.39$,            $P_z(0,            T_2) = 63.76$
          - $dr = 0.1\%$: $P = 102.75$,            $P_z(0,            T_1) = 91.21$,            $P_z(0,            T_2) = 63.13$
          - $dr = 1.0\%$: $P = 95.63$,            $P_z(0,            T_1) = 89.58$,            $P_z(0,            T_2) = 57.69$
          - $dr = 2.0\%$: $P = 88.38$,            $P_z(0,            T_1) = 87.81$,            $P_z(0,            T_2) = 52.20$
          - $dr = -0.1\%$: $P = 104.41$,            $P_z(0,            T_1) = 91.58$,            $P_z(0,            T_2) = 64.40$
          - $dr = -1.0\%$: $P = 112.29$,            $P_z(0,            T_1) = 93.24$,            $P_z(0,            T_2) = 70.47$
          - $dr = -2.0\%$: $P = 121.84$,            $P_z(0,            T_1) = 95.12$,            $P_z(0,            T_2) = 77.88$
        - **Position and Portfolio Value**
          - The position $k_1$ remains constant at -0.4562.
          - The position $k_2$ remains constant at -1.1737.
          - Change in Portfolio Value varies with the spot curve shift,            from 0.0000 to -0.0027.
## CONCLUSION
- Duration plus convexity hedging strategy achieves a better hedge even with large changes in interest rates.
- There duration plus convexity hedging strategy achieves a better hedge even with large changes in interest rates.
## CONVEXITY TRADING AND THE PASSAGE OF TIME
- The previous example highlights a seemingly profitable trading strategy.
- If we go long bonds with high convexity,            such as long-term bonds,            and duration
hedge the interest rate risk using bonds with low convexity,            such as short-term bonds,            we gain positive returns from convexity.
- That is,            in equation
$$d V\approx-\left(D\ P_{c}+k\ D_{z}\ Z\right)\ d r+\frac{1}{2}\ \left(P_{c}\ C+k\ Z\ C_{z}\right)\ d r^{2}$$
the first parenthesis is always zero,            because of hedging,            while the second parenthesis is always positive,            entailing a positive flow of money.
- Is this an arbitrage? Can we make large profits by loading on convexity?
- No. The simple example above leaves out an important component of return,           
and this is the passage of time.
## AN ISSUE WITH DURATION HEDGING
- Suppose that on April 1,            2004 a fixed income fund has$100 million (par amount)
invested in a 3.875 coupon bond expiring on February 15,            2013. The price of
the bond on that day is$101.50 (per$100 of face value),            and its duration is
D = 7.491
- Let's duration hedges with the zero with T =Feb 15,            2005 (duration DS = 0.87):
$$k_{S}=-{\frac{D\times P}{D_{S}\times P_{S}}}={\frac{7.491\times101.5}{0.87\times99.0019}}=-8.83$$
- Between April 1,            2004 and April 15,            2004,            the yield curve shifted up by 0.5%,            on
average.
- An effective duration hedge should have largely hedged the losses due to the shift
in interest rates.
- If we add 0.50% to each of the yield on April 1 and recompute the value of the
hedged portfolio,            we find its value would only change from$101.50 to$101.57,           
implying 0.07% increase in value.
## AN ISSUE WITH DURATION HEDGING
- In sharp contrast,            the new yield curve implies the value of the hedged portfolio is
$$V_{4/15/2004}=\$98.20,           \text{ a decline of 3.30%}$$
$$
- The hedging strategy did not work as expected.
- It did work partially,  as the unhedged portfolio would have dropped instead to
$$V_{4/15/2004}^{\mathrm{no~hedge}}=\$97.42,            \text{ a decrease of \$4.01}$$
- The problem with the duration hedge is that the slope of the terms structure changed.
- The problem with the duration hedge is that the *slope - of the terms structure changed.
## 2020 VARIATION IN YIELDS

 ![500](Lecture%20Note%202-%20Interest%20Rate%20Risk%20Management%20And%20Factors-20240407060822882.webp)

## THE DYNAMICS OF THE TERM STRUCTURE: LEVEL,   SLOPE,   AND CURVATURE

 ![500](Lecture%20Note%202-%20Ipngest%20Rate%20Risk%20Management%20And%20Factors-20240407060845696.webp)

## A FACTOR REPRESENTATION OF YIELD CHANGES
- Let$ϕ_1(t),            ϕ_2(t)$and$ϕ_3(t$) be three independepngactors that affect the term structure.
- We do not know them yet: The exercise is exactly to find them out.
- Consider the constant maturities$τ_1,            τ_2,           …,           τ_n$: that is,  $τ_1$= one month,  $τ_2 = 2$months,  …$τ_n = 10$years,  for instance.
- Denoting$r(t,            t -+ τ_i)$the continuously compounded yield at$t$of a zero coupon bond maturing at$t + τ_i$,  for each of these maturities$τ_i$,  let
$$\Delta r_{i}(t)=r(t+h,           t+h+\tau_{i})-r(t,           t+\tau_{i}).$$
- Assume that the dynamics of interest rates is:
$$\Delta r_{1}(t)\ =\ \alpha_{1}+\beta_{11}\Delta\phi_{1}(t)+\beta_{12}\Delta\phi_{2}(t)+\beta_{13}\Delta\phi_{3}(t)+\varepsilon_{1}(t)$$
$$\Delta r_{2}(t)\ =\ \alpha_{2}+\beta_{21}\Delta\phi_{1}(t)+\beta_{22}\Delta\phi_{2}(t)+\beta_{23}\Delta\phi_{3}(t)+\varepsilon_{2}(t)$$
$$\vdots\ =\ \vdots\tag{13}$$
$$\Delta r_{n}(t)\ =\ \alpha_{n}+\beta_{n1}\Delta\phi_{1}(t)+\beta_{n2}\Delta\phi_{2}(t)+\beta_{n3}\Delta\phi_{3}(t)+\varepsilon_{n}(t)$$
## IDENTIFYING THE FACTORS: PRINCIPAL COMPONENT ANALYSIS
- The factors driving the term structure are implicit in the ∆r1(t)*,  ….,  - ∆rn(t).
- PCA assumes they are linear combination of the underlying yields.
- That is,  for$i = 1,            2,            3$we have
$$\Delta\phi_{i}(t)=a_{i1}\times\Delta r_{1}(t)+…+a_{in}\times\Delta r_{n}(t)$$
- Denote$\sigma_{k\ell}=Cov\left(\Delta r_{k},           \Delta r_{\ell}\right)$
- Let's start with the first factor ϕ1(t).
- **Objective**: Find$a_{11},            …,            a_{1n}$to maximize the variance of$∆ϕ_1(t)$
$$\max_{\alpha_{11},           …,           \alpha_{1n}}Var\left(\Delta\phi_{i}\right)=\sum\limits_{k=1}^{n}\sum\limits_{\ell=1}^{n}a_{1k}a_{1\ell}\sigma_{k\ell}\tag{14}$$
- under the restriction$\Sigma_{j=1}^na_{1j}^2=1$
- Since$∆ϕ_1(t)$is a linear combination of all the yields and it is found to maximize its variability,  it is intuitive that it will co-vary a lot with all the yields$∆r_1(t),            …,            ∆r_n (t).$
## IDENTIFYING THE FACTORS: PRINCIPAL COMPONENT ANALYSIS
- It is *as if - we are maximizing some weighted average of the$R^2$s of the multiple regressions
$$\begin{array}{l}\Delta r_{1}(t)\ =\ \alpha_{1}+\beta_{11}\Delta\phi_{1}(t)+\varepsilon_{1}(t)\\ \Delta r_{2}(t)\ =\ \alpha_{2}+\beta_{21}\Delta\phi_{1}(t)+\varepsilon_{2}(t)\\ \vdots\ =\ \vdots\\ \Delta r_{n}(t)\ =\ \alpha_{n}+\beta_{n1}\Delta\phi_{1}(t)+\varepsilon_{n}(t)\end{array}\tag{15}$$
- After the first component,  we can compute the residual of the regression (15):
For all$i = 1,      ..,            n$
$$\hat{\varepsilon}_{i}\left(t\right)=\Delta r_{i}\left(t\right)-\alpha_{i}-\beta_{i1}\Delta\phi_{1}\left(t\right)$$
- The variation of the residuals$\hat{\varepsilon}_{i}(t)$is what is left to "explain."
- Hence,  we can compute the second component as
$$\Delta\phi_{2}(t)=a_{21}\times\varepsilon_{1}(t)+…+a_{2n}\times\varepsilon_{n}(t)$$
- We find again the$a_{21},           …,           a_{2n}$that maximize
$$\max_{a_{21}^{\max}…a_{2n}}Var\left(\Delta\phi_{2}\left(t\right)\right)\tag{16}$$
- conditional again on$\Sigma_{j=1}^na_{2j}^2=1$And so on.
## THE IMPLEMENTATION OF PCA
- Start from the n × n variance-covariance matrix of ∆ri (t)'s. Denote it by
$$M = Cov (∆r_{1}(t),            …,             ∆r_{n}(t))$$
- Compute the eigenvalues and eigenvectors of M,  i.e. those scalars$λ_i$(eigenvalues) and vectors$v_i = (v_{i1},            ……,            v_{in})$′ related by
$$M\mathbf{v}_{i}{=}\lambda_{i}\mathbf{v}_{i}$$
- Order$λ_1 > λ_2> … > λ_n$. It can be shown then the eigenvector v1 is the solution to the first maximization (14),  that is$v_1 = (a_{11},            …,            a_{1n})$
- Accordingly,  we set
$$\Delta\phi_{1}\left(t\right)=\sum\limits_{k=1}^{n}v_{1k}\ \Delta r_{k}\left(t\right)$$
- We then run the regression (15) and compute the residuals$\hat{\varepsilon}_{1}\left(t\right),           …,           \hat{\varepsilon}_{n}\left(t\right)$
## THE IMPLEMENTATION OF PCA
- v${}_{2}$is the solution to the second maximization (16). Accordingly,  we set the second factor
$$\Delta\phi_{2}\left(t\right)=\sum\limits_{k=1}^{n}v_{2k}\ \varepsilon_{k}\left(t\right)$$
- We run the regression (13) with two factors. And so on.
- Notes:
- This procedure gives$∆ϕ_i(t)$. The factor$ϕ_i(t)$is the cumulated sum.
- Consider the "beta" from the regression from factor 1. Using vector notation
$$\beta_{i1}=\frac{C o v(\Delta r_{i}(t),           \Delta\phi_{1}(t))}{V a r(\Delta\Phi_{1}(t))}=\frac{C o v(\Delta r_{i}(t),           \Sigma_{k=1}^{n}\,           v_{1k}\Delta r_{k}\left(t\right))}{V a r(\Sigma_{k=1}^{n}\,           v_{1k}\Delta r_{k})}$$$$=\frac{\mathbf{1}_{i}^{\prime}M\mathbf{v}_{1}}{\mathbf{v}_{1}^{\prime}M\mathbf{v}_{1}}=\frac{\mathbf{1}_{i}^{\prime}\lambda_{1}\mathbf{v}_{1}}{\lambda_{1}\mathbf{v}_{1}^{\prime}\mathbf{v}_{1}}=v_{1i}$$
=⇒ The beta coefficients in (13) are just the eigenvectors: βij = vji
## FACTORS FROM PCA

 ![500](Lecture%20Note%202-%20Interest%20Rate%20Risk%20Management%20And%20Factors-20240407062316871.webp)

## PARALLEL SHIFTS,  SLOPE TILTS AND CURVATURE CHANGES

 ![500](Lecture%20Note%202-%20Interest%20Rate%20Risk%20Management%20And%20Factors-20240407062330304.webp)

## THE SENSITIVITY OF INTEREST RATES TO PCA LEVEL,  SLOPE,  AND CURVATURE
## PANEL A: LEVEL

| Maturity    | 1 month | 6 months | 1 year | 2 year | 3 year | 4 year | 5 year |
|-------------|---------|----------|--------|--------|--------|--------|--------|
|$\beta^{PCA}_{i1}$| 0.4416  | 0.4167   | 0.4315 | 0.3762 | 0.3421 | 0.3169 | 0.2935 |
|$R^2$| 61.15%  | 79.52%   | 91.66% | 88.61% | 83.89% | 75.06% | 73.03% |

## PANEL B: SLOPE

| Maturity    | 1 month | 6 months | 1 year | 2 year | 3 year | 4 year | 5 year |
|-------------|---------|----------|--------|--------|--------|--------|--------|
|$\beta^{PCA}_{i2}$| -0.7307 | -0.2774   | 0.0848 | 0.2425 | 0.2909 | 0.3559 | 0.3344 |
|$R^2$| 95.91%  | 86.83%   | 92.39% | 96.25% | 96.48% | 94.72% | 92.71% |

## PANEL C: CURVATURE

| Maturity           | 1 month | 6 months | 1 year  | 2 year  | 3 year | 4 year | 5 year |
| ------------------ | ------- | -------- | ------- | ------- | ------ | ------ | ------ |
|$\beta^{PCA}_{i3}$| 0.5186  | -0.7099  | -0.2869 | -0.0231 | 0.1411 | 0.2267 | 0.2700 |
|$R^2$| 99.99%  | 97.99%   | 94.35%  | 96.27%  | 97.17% | 96.58% | 95.70% |

- The first three PCAs explain the vast majority of the variation in yields
- =⇒ If we hedge the three PCAs,  we hedge most of interest rate risk.
## INTEREST RATE RISK MANAGEMENT AND FACTOR DURATION
- **Factor Duration Definition**
		  - The factor duration$D_j$of an asset with price$P$with respect to factor$j$is given by:$$D_j = -\frac{1}{P} \frac{dP}{d\phi_j}$$
- **PCA Approximation**
		  - From PCA,  the change in yield$dr_i$with respect to the change in factor$\phi_j$can be approximated by the PCA beta coefficient$\beta_{ij}$:$$\frac{dr_i}{d\phi_j} \approx \beta_{ij}$$
- **Example Calculation**
		  - For a zero coupon bond$Z(t,            t + \tau_i) = e^{-r_i(t)\tau_i}$,  the duration with respect to factor$j$is calculated as:$$D_{z,           j} = -\frac{1}{Z(t,            t + \tau_i)} \frac{dZ(t,            t + \tau_i)}{d\phi_j}$$This simplifies to:$$D_{z,           j} = \tau_i \times \beta_{ij}$$
by considering that$\frac{dZ}{d\phi_j}$relates to$\frac{dr_i}{d\phi_j}$through the chain rule and the relation of$Z$to$r_i$.
## INTEREST RATE RISK MANAGEMENT AND FACTOR DURATION
- Example 2. From the definition of a coupon bond:
$$P_{c}(t,           T)=\frac{c}{2}\sum\limits_{i=1}^{n}Z(t,           T_{i})+Z(t,           T_{n})$$
- the duration of the bond with respect to factor j is
$$D_{j}=-\frac{1}{P_{c}}\frac{d~P_{c}}{d~\phi_{j}}=\sum_{i=1}^{n}\,           w_{i}\tau_{i}\beta_{i j}$$
- Given Dj,  we can approximate the return of a security by
$$\frac{d\ P}{P}\approx-D_{1}\ d\phi_{1}-D_{2}\ d\phi_{2}-D_{3}\ d\phi_{3}$$
## INTEREST RATE RISK MANAGEMENT: FACTOR NEUTRALITY
- A portfolio$P$has factor durations$D_1$and$D_2$with respect to level and slope.
- **Objective**
		  - To achieve factor neutrality,  select two other securities. For instance,  consider a short-dated ($P^S_z$) and a long-dated ($P^L_z$) zero coupon bond.
		  - Compute the factor durations$D^S_{z}$,  $D^S_{z}$,  $D^L_{z}$,  and$D^L_{z}$for both.
- **Strategy**:
		  - Determine the positions$k_S$and$k_L$such that the variation of the portfolio including the two bonds approximates zero. The change in value$V$,  represented as$dV$,  should satisfy:
$$dV = dP + k_F \times dP^S_z + k_L \times dP^L_z = 0$$
- **Equations for Hedging**:
		  - Following the method used in duration and convexity hedging,  we arrive at two equations:
$$k_S \times D^S_{z} \times P^S_z + k_L \times D^L_{z} \times P^L_z = -D_1 \times P$$
$$k_S \times D^S_{z} \times P^S_z + k_L \times D^L_{z} \times P^L_z = -D_2 \times P$$
		  - These equations can be solved to find the exact positions$k_S$and$k_L$required to neutralize the impact of level and slope factor changes on the portfolio.
- The solution of this system is:
$$k_{S}=-\frac{F}{P_{z}^{S}}\left(\frac{D_{1}\times D_{z2}^{L}-D_{2}\times D_{z1}^{L}}{D_{z1}^{S}\times D_{z2}^{L}-D_{z2}^{S}\times D_{z1}^{L}}\right);\tag{18}$$$$k_{L}=-\frac{F}{P_{z}^{L}}\left(\frac{D_{1}\times D_{z2}^{S}-D_{2}^{L}\times D_{z1}^{S}}{D_{z1}^{L}\times D_{z2}^{S}-D_{z2}^{L}\times D_{z1}^{S}}\right)\tag{19}$$
## FACTOR NEUTRALITY: EXAMPLE
- Consider again the previous example,  but use now a short-term and a long-term zeros to hedge. Specifically,  use the zeros maturing on Feb. 15,  2005 and on Feb. 15,  2013.
 - Using the data about level and slope,  we find the following factor durations:
- **Factor Durations Identified**:
		  - For the long-term coupon bond:$D_1 = 6.9624$;$D_2 = 4.0797$;
		  - For the short-term zero:$D^S_1 = 0.9729$;$D^S_2 = -0.2215$;
		  - For the long-term zero:$D^L_1 = 8.1912$;$D^L_2 = 5.3150$.
- **Determining Positions**:
		  - Using Equation (18),  the positions$k_S$and$k_L$in the short-term and long-term zero coupon bonds are calculated as:
			 -$k_S = -0.5266$
			 -$k_L = -1.1259$
- **Portfolio Value Post-Hedge**:
		  - As of April 15,  2007,  the value of the hedged portfolio is represented as:
			 -$V^{FactorHedge}_{4/15/2004} = \$100.91$,  indicating a drop of only 0.58%