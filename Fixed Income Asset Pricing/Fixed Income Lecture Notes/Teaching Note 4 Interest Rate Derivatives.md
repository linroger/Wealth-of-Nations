---
cssclasses:
  - academia
title: Teaching Note 4 Interest Rate Derivatives
tags:
  - forward_contracts
  - hedging_interest_rate
  - interest_rate_derivatives
  - spot_curve
  - swap_rates
aliases:
  - FRA
  - Forward Rate Agreement
  - Interest Rate Swap
  - Swap
  - Teaching Note
key_concepts:
  - Discount factor
  - Fixed-for-floating swap
  - Forward contracts
  - Interest rate risk
  - Spot curve
  - Swap rate
  - Trading strategy
---

# Teaching Note 4 Interest Rate Derivatives

John Heaton

The University of Chicago

Booth School of Business

[[Fixed Income Lecture Notes]]

 [[Introduction to Fixed Income Asset Pricing]]

 [[Lecture Note 2Interest Rate Risk Management And Factors]]

 [[Forward Rates and Term Structure]]

 [[Teaching Note 4 Interest Rate Derivatives]]

 [[Teaching Note 5 Risk Neutral Pricing]]

[Teaching Note 6 Mortgage Backed Securities](Teaching%20Note%206%20Mortgage%20Backed%20Securities.md)

[Teaching Note 7 A Rundown On Continuous Time Models](Teaching%20Note%207%20A%20Rundown%20On%20Continuous%20Time%20Models.md)

[PSET IV- Fixed Income Asset Pricing](PSET%20IV-%20Fixed%20Income%20Asset%20Pricing.md)

## THE NOTIONAL AMOUNT OF OVER-THE-COUNTER DERIVATIVES

![|500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240412232743007.png)

(Data Source: OTC derivatives data are from the Bank for International Settlements,  while global GDP data are from the World Bank.)

## INTEREST RATE DERIVATIVES: FORWARDS AND [[A Guide to the Front End and Basis Swap Markets#Forward Rate Agreements (FRAs) Overview|Forward Rate Agreements]]
- Effective risk management is carried out using derivatives,  such as forward,  futures,  and swaps.
- Forward contracts and [[A Guide to the Front End and Basis Swap Markets#Forward Rate Agreements (FRAs) Overview|Forward Rate Agreements]] allow firms to lock in interest rates in the future.
- A **[[A Guide to the Front End and Basis Swap Markets#Forward Rate Agreements (FRAs) Overview|Forward Rate Agreement]](FRA)** is a contract between two counterparties who agree at time 0 to exchange the following net payment at a future date$T_2$

$$\text{Net payment at }T_{2}=N\times\Delta\times[r_{n}(T_{1},  T_{2})-f_{n}]\tag{1}$$

- where$r_n(T_1,   T_2)$is a$n$−times compounded floating reference rate,  $f_n$is a fixed rate,  $N$is the notional,  and$∆ = 1/n$
- Example: Today (T0) is January 2,  2020 (we will treat this as January 1 …) and suppose a firm has a$100 million receivable in six months on June 30,  2020. Ignoring overnight investing:
- If the firm will not need that cash immediately,  but,  say,  six month later,  it can lock-in an investment rate today for the future period$T_1  = 0.5$is July 1,  2020 to$T_2  = 1$is December 31,  2020 by entering into a [[A Guide to the Front End and Basis Swap Markets#Forward Rate Agreements (FRAs) Overview|Forward Rate Agreement]](FRA) with a bank.
- Assume the bank quotes the (semi-annually compounded) annualized rate of$f_2 = 1.59\%$.
- When the firm receive \$100 million in six months ($T_1$) it can invest it at the then current floating rate$r_2(T_1,   T_2) = r_2(0.5,   1)$,  which is not known today.

#### A FORWARD INVESTMENT

 ![500](aforwardinvestment.svg)

## HEDGING INTEREST RATE RISK
- Clearly,  using the banks offer locks in the rate$f_{2}$for the period$T_1$to$T_2$for the firm,  as

$$\text{Total amount} = \left\{ \$100 \text{ million} \times \left[1 + \frac{f_2}{2}\right] \right\} \quad (\text{Return on investment})$$$$+ \left\{ \frac{N}{2} \times [f_2 - r_2(0.5,   1)] \right\} \quad (\text{FRA payment)}$$$$= \$100 \text{ million} \times \left[1 + \frac{f_2}{2}\right]$$$$= \$100\text{million} \times \left[1 + \frac{0.0159}{2}\right]= \$100.79 \text{ million}$$

- The question is: How does the bank determine the forward rate f2?
- Through a simple trading strategy.

## TRADING STRATEGY TO COMPUTE FORWARD RATE

 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240414082741031.png)

- The bank is perfectly hedged.
- Note also that the quoted forward rate is effectively implicit in the ratio

$$M=\frac{Z(0,  0.5)}{Z(0,  1)}=1+\frac{f_{2}}{2}$$

- in the first step of the trading strategy.
- This fact leads to the notion of the forward discount factor,  given by$\frac{1}{M}$.

## THE FORWARD DISCOUNT FACTOR
- The **forward discount factor** at time$t$defines the time value of money between two future dates,  $T_1$and$T_2  > T_{1}$.
- Given the discount factors$Z(t,   T_1)$and$Z(t,   T_2)$,  the forward discount factor is given by

$$F(t,  T_{1},  T_{2})=\frac{Z(t,  T_{2})}{Z(t,  T_{1})}\tag{2}$$

- Indeed,  note that in the example$Z(0,  0.5)=0.9918$and$Z(0,  1)=0.9840$implying a forward discount factor$$F(0,  0.5,  1)=\frac{Z(0,  1)}{Z(0,  0.5)}=0.9921 \tag{3}$$
- From any discount factor (forward or not),  we can compute the$n-$times compound rate as$$f_{n}\left(t,  T_{1},  T_{2}\right)=n\times\left(\frac{1}{F\left(t,  T_{1},  T_{2}\right)^{\frac{1}{\left(n+\left(T_{2}-T_{1}\right)\right)}}}-1\right)\tag{4}$$
- For instance,  in the example we have

$$f_{2}(0,  0.5,  1)=2\times\left(\frac{1}{F\left(0,  0.5,  1\right)^{\frac{1}{2\times {0.5}}}}-1\right)=1.59\%,  $$

## THE SPOT CURVE AND THE FORWARD CURVE

- The **forward curve** gives the relation between the forward rate$f(0,   T,   T + ∆)$and the time of.the investment T. Curves on January 2,  2020
 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240412234143923.png)

## THE VALUE OF A FORWARD RATE AGREEMENT

- In previous example,  suppose 3 months later,  on April 1,  2020,  the firm decides to close its FRA.
- As interest rates changed between January and April,  so did the *value* of the FRA.
- Recall bank's earlier strategy:
	- (a) short one T-bill maturing at$T_1$and
	- (b) long$M = 1.0079$T-bills maturing at$T_2$.
- This portfolio (a) + (b) replicates the cash flow that the firm will receive.
	- =⇒ its value a$t$= value of the [[A Guide to the Front End and Basis Swap Markets#Forward Rate Agreements (FRAs) Overview|FRA]] for the firm. Thus:
Value of [[A Guide to the Front End and Basis Swap Markets#Forward Rate Agreements (FRAs) Overview|FRA]] to the firm at$t$$$=V^{FRA}\left(t\right)=M\times Z(t,  T_{2})-Z(t,  T_{1})\tag{5}$$
- On April 1,  2020 (= t),  we had$Z(t,   T_1) = \$0.9993$and$Z(t,  T_2) = \$0.9981$. Therefore
$$V^{FRA}_t = 1.0079 × Z(t,   T_2) − Z(t,   T_1) = 1.0079 × \$0.9981 − \$0.9993 = \$0.00671 million$$
	- =⇒ On April 1,  2020,  the [[A Guide to the Front End and Basis Swap Markets#Forward Rate Agreements (FRAs) Overview|FRA]] initiated 3 months earlier was worth$671,  176.83 to the firm.
- In general,  using the definition$1 + f_n(t,    T_1,   T_2)∆ = Z(t,    T_1)/Z(t,   T_2)$,  we have

$$V^{FRA}(t)=N\times Z(t,  T_{2})\times\left[M-\frac{Z(t,  T_{1})}{Z(t,  T_{2})}\right]\tag{6}$$$$=N\times Z(t,  T_{2})\times\Delta\times\left[f_{n}(0,  T_{1},  T_{2})-f_{n}(t,  T_{1},  T_{2})\right]$$

## INTEREST RATE DERIVATIVES: SWAPS

- A plain vanilla **fixed-for-floating interest rate swap** is an agreement between two counterparties to exchange cash flows at$T_1,   T_2,  …,   T_n = T$,  with$T_i = T_{i−1} + ∆$,  according to

Net Cash Flow at$$T_{i}=N\times\Delta\times[r_{n}(T_{i-1})-c]\tag{7}$$

- where$n = 1/∆$is the reference rate compounding frequency.
- The constant c is called **swap rate**.

## - HOW DO WE DETERMINE THE **VALUE OF A SWAP**?

- At inception,  the value is zero,  as the counterparties agree to swap future payments,  not today.
- After inception,  as the floating rate changes,  so does the value of the swap.
- Consider the party with net cash flow (7). This party is effectively long a floating rate bond ($P_{FR}(t,   T$)) and short a fixed rate bond with coupon$c (P_c(t,   T))$.
- =⇒ the value of the swap is

$$V^{swap}(t,  c,  T)=P_{FR}(t,  T)-P_{c}(t,  T)\tag{8}$$

- At every$T_i$,  the value of$PFR(T_i,   T) = 100$. Therefore,  at these times

$$V^{swap}(T_{i};c,  T)=100-\left(\frac{c}{2}\times100\times\sum\limits_{j=i+1}^{M}Z(T_{i},  T_{j})+Z(T_{i},  T_{M})\times100\right)\tag{9}$$

## THE SWAP RATE AND THE SWAP CURVE

- How is the swap rate $c$ determined?
- The swap rate $c$ is given by that number that makes $V^{swap}(0; c,   T) = 0$ in (8).
- Rewriting the equation for any payment frequency$n$and payment dates$T_1,   … T_M$,  we have

$$V^{swap}(0;c,  T)=100-\left(\frac{c}{n}\times100\times\sum\limits_{j=1}^{M}Z(0,  T_{j})+Z(0,  T_{M})\times100\right)=0\tag{10}$$

- Solving this equation for$c$we find

$$c=n\times\left(\frac{1-Z\left(0,  T_{M}\right)}{\sum\limits_{j=1}^{M}Z\left(0,  T_{j}\right)}\right)\tag{11}$$

- The swap curve at time $t$ is the set of swap rates (at time $t$) for all maturities $T_{1}$,  $T_{2}$,  …,  $T_{M}$.
- I denote the swap curve at time $t$ by $c (t,   T_{i}) \text{ for } i = 1,   …,   M$.

## THE SWAP CURVE AND THE "CLASSIC" [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] CURVE
- The swap curve implicitly contains the discount factors $Z(0,   T_i)$ that market participants use to quote swaps in the OTC market.
- From the swap curve,  we can then bootstrap out such discounts by inverting (11):

$$Z\left(t,  T_{1}\right)=\frac{1}{1+\frac{c(t,  T_{1})}{n}}\tag{12}$$

while for $i = 2,   …,   M$

$$Z\left(t,  T_{i}\right)=\frac{1-\frac{c\left(t,  T_{i}\right)}{n}\times\Sigma_{j=1}^{i-1}\,  Z\left(t,  T_{j}\right)}{1+\frac{c\left(t,  T_{i}\right)}{n}}\tag{13}$$

- The resulting yield curve is called [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curve.
## TREASURY AND SWAP DISCOUNT AND YIELD ON JANUARY 4,  2005

 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240412234843892.png)

## THE 5-YEAR ZERO COUPON TREASURY AND SWAP YIELD

 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240412234909341.png)

### SWAP SPREAD TRADES AND THE RISK IN CONVERGENCE TRADES
- Today is June 30,  2006,  and we are looking to make a profit on the swap spread.
- The market presented the following data:
	- 3-month LIBOR: 5.5081%.
	- 3-month repo rate: 5.27%.
	- 5-year swap rate: 5.69%.
	- 5-year T-note with a 5.125% coupon priced at$100.1172,
	- and yield-to-maturity 5.10%.
- The swap spread equals the yield to maturity of the Treasury note minus the swap rate

$$S S=5.69\%-5.10\%=0.59\%=59\ b p s$$

- That is,  receiving the fixed rate from the swap and paying the yield in a short T-notes would return 59 basis points per year.
- To secure this return of 59 basis points,  we have to pay the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] rate,  as part of the swap,  and receives the repo rate,  as part of a [Reverse Repurchase](Reverse%20Repurchase%20Agreement%20Operations.md) agreement to short the T-note.

## THE LIBOR-REPO SPREAD
- The spread between [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and repo (LRS) is$LRS = 5.5081\% − 5.27\% = 0.2381\%$
- The net spread is$SS − LRS = 35.19$bps.
- This spread is not very large,  but the LIBOR-repo spread has been historically relatively stable at around 21 bps and so this net spread (SS − *LRS*) still appears a relatively safe trade.
- Using daily data from Jan 2000 to Jun 2006,  the distribution of the LIBOR-repo spread is as
 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413020653936.png)
- Even in extreme circumstances,  the net spread would be at least$0.59\% − 0.37\% = 22 bps$

## THE TRADE
- We finally decided to go ahead,  and enter into the following transactions:
1. Short the 5-year bond through a [Reverse Repo](Reverse%20Repurchase%20Agreement%20Operations.md) transaction. In cash flow terms,  the fund would receive the repo rate and pay the coupon.
1. Enter into a fixed-for-floating swap,  in which we would receive fixed and pay LIBOR.
#### REVERSE REPO
- We want to set up a$100 million trade. Thus,   we need to sell
$$N=\frac{\$100\text{million}}{100.1172}=998,  829\text{ Treasury notes (for }\$100\text{ par value)}\tag{14}$$
- Assuming haircut = 0,  we then borrow N = 998,  829 5-year T-notes from the repo dealer,  sells them in the cash market for$100 million,  and gives this cash to the repo dealer.
- Assume we enter into a term [Reverse Repo](Reverse%20Repurchase%20Agreement%20Operations.md) with 3-months maturity,  and rolls it over every three months.
- Because the repo dealer keeps the \$100 million at every reset date,  our total cash flow every quarter is$$\left.\text{[Reverse Repo] CF}(t)=\left\{\begin{array}{ll}\frac{\$100\textbf{ mm}}{4}\times r(t-0.25)-N\times100\times\frac{5.125\%}{2}&\text{if }t\text{ is a coupon date}\\\frac{\$100\textbf{ mm}}{4}\times r(t-0.25)&\text{otherwise}\end{array}\right.\right.$$

#### FIXED -FOR-FLOATING SWAP
- We have to enter into a 5-year,  fixed-for-floating swap in which we pay the 3-month [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] rate and receive the 5-year fixed swap rate.
- In a plain vanilla fixed-for-floating swap,  the floating payments occur at quarterly frequency,  while the fixed payments occur at semi-annual frequency,  therefore exactly matching the payment frequency of the [Reverse Repo](Reverse%20Repurchase%20Agreement%20Operations.md) transaction discussed earlier.
- Denoting ℓ(t) is the 3-month [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] rate at time t,  the swap cash flows are then given by

$$
\left.\text{Swap CF}(t)=\left\{\begin{array}{c}\$100\mathrm{~mm}\times\frac{5.69\%}2-\frac{\$100\mathrm{~mm}}4\times\ell(t-0.25)\mathrm{~if~}t\mathrm{~is~fixed~payment~date}\\-\frac{\$100\mathrm{~mm}}4\times\ell(t-0.25)\mathrm{~otherwise}\end{array}\right.\right.
$$

## THE QUARTERLY CASH FLOW
-It is useful to decompose the quarterly cash flow in two components,  the swap spread (SS) component and the LIBOR-repo spread (LRS) component.
- We have that every six months,  the swap spread component of the cash flow is

$$\text{SS CF every six months } =\$100\mathtt{mm}\times\dfrac{5.69\%}{2}-N\times100\times\dfrac{5.125\%}{2}$$$$=\$285,  499.73$$

- The second component is the LIBOR-repo spread,  which every quarter is given by

$$\text{LRS CF every three months} =\dfrac{\$100\text{mm}}{4}\times(r(t-0.25)-\ell(t-0.25))$$

- For instance,  on June 30 the$r(0) = 5.27\%$while$ℓ(0) = 5.5081$%,  implying

$$\text{LRS CF on September 30,   2006 }=$-\$59,  525.00$\tag{15}$$

- Since the LIBOR-repo spread is relatively stable,  we expect to receive approximately

$$\text{Total expected net cash flow per year }=2\times\$285,  499.73-4\times\$59,  525.00 =\$332,  898$$

- ….but risk may be just around the corner …

### THE SWAP SPREAD AND LIBOR-REPO SPREAD

![|500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413001901009.png)

### NET CASH FLOWS FROM SWAP SPREAD TRADE

 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413001954481.png)

## UNWINDING THE POSITION?

- Given the large negative quarterly payments due to the increase in the LIBOR-repo spread,  we
may start thinking about whether we should unwind their position.
- First question is: What is the value of the position?

## - THE VALUE OF THE [[Reverse Repurchase]]

- The ex-coupon value of the repo position on rollover quarter$t$is

$$\text{Value [Reverse Repo](} =\$100 mm -N\times P_{note}(t,  T)$$

- where$P_{note}(t,   T)$is the value of the T-note at time t.
#### - THE VALUE OF THE FIXED-FOR-FLOATING SWAP

- As time passes and interest rates fluctuate,  the value of the swap changes. We have:

$$\mathrm{Value~swap~at~}t=P_{c}(t,  T)-P_{F R}(t,  T)$$

- where PFR(*t,  T*) is the LIBOR-based floating rate bond,  and Pc(*t,  T*) is the fixed rate coupon
bond with coupon c = 5.69% =swap rate,  given by

$$P_{c}(t,  T)=\frac{100\times5.69\%}{2}\times\sum_{i=1}^{n_{t}}Z(t,  T_{i})+100\times Z(t,  T_{n_{t}})$$

- Here,  $Z(t,   T_i)$is the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] discount curve (see next Figure)
### THE [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] CURVE: JUNE 2006 – JUNE 2008

 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413002218281.png)

## THE SURPRISE

- On March,  2008,  as we start unwinding the position,  we have a good news: the value of the swap is now$10.21 million.
- Indeed,  the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] yield curve now ranges between 2.7% at 1 month,  and 3.3% at 5 years,  which pushes up the value of the fixed part of the swap to$110.21 million.
- Because the floating part is always equal to$100 million at reset dates,   by closing the position we would obtain an inflow of$10.21 million.
- However,  as we close the swap,  we have also to close the [Reverse Repo](Reverse%20Repurchase%20Agreement%20Operations.md).
- The bad news is that now the T-note we are shorting is trading at$110.23.
- Given the accrued interest of$1.28,   the total losses from the short position amount to$100 million −N ×$111.51 = −$11.38 million.
- In sum,  to close the position on March,  2008,  we receive$10.21 million from the swap,   but we have to pay$11.38 million on the [Reverse Repo](Reverse%20Repurchase%20Agreement%20Operations.md),  for a total loss of$1.16 million. This number far outweighs the cumulative cash flows we have so far received.

## THE SWAP SPREAD TRADE VALUE

 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413002314426.png)

### CONCLUSION: THE RISK IN RELATIVE VALUE TRADES

1. **Cost of Carry**,  due to the variation in the cost-of-carry,  i.e. the cash-flow per period that a trade is expected to generate.
	- In swap spread trade,  it is the difference between the swap spread and the LIBOR-repo rate.
	- An arbitrageurs may find that holding up the trade is generating cash outflows that outstrip the expected gain from convergence.
1. **Market Risk**,  that is,  the potential capital losses due to the variation in the underlying spread.
	- In a relative value trade speculators bet on the convergence of the underlying spread to an average level.
	- However,  such spread may either not converge to the average level,  or just widen for a while.
1. **Funding Risk**,  that is,  the ability to hold up the position until maturity.
	- Even for those (arbitrage) trades in which a hedge fund is certain to make profits if it holds the position until maturity,  it is quite possible that the spread may widen further before it narrows.
	- If the spread widens,  then the hedge fund would potentially suffer large capital losses.
	- It is then key for the hedge fund survival that it has sufficient capital in cash or a large borrowing capacity that makes it able to withstand the capital loss.

## FUNDING RISK DURING THE CRISIS?

- Funding risk is especially important during periods of crisis,  for a number of reasons:
1. All risk-based spreads - the spreads between a risky securities and Treasury securities - tend to widen,  as investors dump risky securities and purchase safe U.S. Treasuries.
	- =⇒ Relative value trades experience large capital losses.
1. Lenders are more wary of default risk,  and increase haircuts,  margins,  etc.,  making capital effectively more scarce
	- It becomes harder for a hedge fund to keep up the position.
1. Investors withdraw money from hedge funds,  if they can.
- Hedge funds must liquidate positions,  at a loss.
- Next figure shows negative swap spreads during the crisis for long term swaps

### NEGATIVE SWAP SPREADS DURING THE CRISIS

 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413002516315.png)

## NEGATIVE SWAP SPREAD AND NO ARBITRAGE

- Negative swap spreads are a textbook arbitrage opportunity:
- Buy Treasury and pay fixed in a fixed for floating swap
$\Longrightarrow$Cash Flow at$t=\left(c^{T-Bond}-c^{swap}\right)+\left(LIBOR_{t}-REPO_{t}\right)$
- Both terms are positive. The first because of the negative swap spread,  and the second because
[[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] is the rate for uncollateralized borrowing,  while REPO is the rate for collateralized borrowing.
- This is a textbook arbitrage opportunity if an arbitrageur can hold the position to maturity.
- The risk of the spread increasing further,  generating severe capital losses,  may make arbitrageurs wary of entering the market.
- At reset dates,  the value of the trade is

$$V_{t}^{T r a d e}=(P_{c}^{T-B o n d}(t,  T)-P_{c}^{S w a p}(t,  T))$$

- If the swap spread becomes even more negative,  e.g. the yield on T-bond increases while the one of the swap remains the same,  then$V^{Trade}_t$decreases even more.

### NEGATIVE SPREADS CONTINUE

 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413002628495.png)

## VIOLATION OF NO-ARBITRAGE DURING THE 2007 - 2008 CRISIS
- The violation of no-arbitrage rules was widespread during the recent crisis
- For instance,  another simple arbitrage restriction that was violated was the covered interest rate parity (CIP)
- The simple rule in the [Foreign Exchange](Foreign%20Exchange%20Quoting%20Conventions.md) market according to which the forward exchange rate$F_{t,  T}$equals the spot$M_t$times the ratio of investment rates in domestic versus foreign country.
- For instance,  if$M_t$= *US/EURO* exchange rate,  then

$$F_{t,  T}=M_{t}e^{(r_{\$$

}-r_{e})(T-t)}$$

- Next figure shows the difference

$$F_{t,  T}^{data}-F_{t,  T}$$

- before and during the crisis.

## CIP VIOLATION DURING THE 2007 - 2009 FINANCIAL CRISIS: EURO / DOLLAR

 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413003013025.png)

### CIP VIOLATION DURING THE 2007 - 2009 FINANCIAL CRISIS: UKP / DOLLAR

 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413003028723.png)

### WHY DID COVERED INTEREST RATE PARITY FAIL DURING THE 2007-2009 CRISIS?
- Holding US Treasuries has its own "convenience yield" when everyone needs cash collateral. - During the crisis,  from the graph,  we had the following violation:

$$F_{t,  t+m}^{d a$t$a}>F_{t,  t+m}=M_{t}\;e^{(r_{\$}-r_{e})m}$$

- Recall that in this case,  an arbitrage trade requires the following:
- (a) Short Euro forward;
- (b) borrow dollars (or sell US Treasuries);
- (c) change them into Euro;
- (d) invest in Euro (or buy Euro bonds)
- But point (b) failed during the crisis,  as:
	1. Increase in credit risk concerns impaired the ability of any financial institution to borrow;
	1. Holding safe dollars (US Treasuries) is valuable during a financial crisis for [[Class Note 10 Liquidity and Class Note 10 Liquidity and Liquidity Managementliquidity management|liquidity management]]
		- US Treasuries are the only collateral accepted for short-term lending transactions.
		- It is very valuable to hold on to them for future cash management

## CROSS-CURRENCY BASIS RISK AFTER THE CRISIS

 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413003210538.png)

###### ISSUES WITH LIBOR
- Until January 31,  2014: British Bankers Association (Bba) Libor
	- Survey of a panel of banks
	- Banks could underestimate their borrowing costs
	- Conflict within the bank: impact of [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] setting on derivatives trading.
###### NOW ICE LIBOR
- ICE now the benchmark administrator
- Regulator in UK: Financial Conduct Authority (FCA)
- Rules for fall-back rates if there are issues

## ALTERNATIVES

- SOFR: "Secured Overnight Financing Rate"
- ARRC: Alternative Reference Rates Committee.
- Others:
- SONIA (Sterling Over Night Indexed Average)
- EONIA (Euro Overnight Index Average) -
- TONAR (Tokyo Overnight Average Rate)
- SARON (Swiss Average Rate Over-Night)
- Measure of overnight *secured* borrrowing.
- Collateralized US Treasuries in the repo market.
- Very liquid and likely resilient markets:$1 trillion in daily volume
- Contrast: USD [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] three-month tenor: about$1 billion
- Published by New York Fed. Along with 30-day,  90-day and 180-day averages

## TRANSITION
- [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] market:$200+ trillion of financial transactions contracts reference LIBOR
- [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] permeates many contracts for in securities markets and the corporate world: leases,  debt,
- Derivatives market with Central Clearing Partners (e.g. CME …).
- Cleared US Dollar interest rate swap contracts at CME: move to SOFR discounting.
- Intercontinental Exchange (ICE) Benchmark Administration: USD [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] benchmarks will stopped
- Fannie and Freddie: have moved bo SOFR contracts - New York Fed: conducts repo and [Reverse Repo](Reverse%20Repurchase%20Agreement%20Operations.md) through tri-party repo. - OTC SOFR swaps - SOFR caps products have developed since September 2020

## SOFR DERIVATIVES

As an example: at the CME

- Futures: 3-month and 1-month. Using compounding or simple averages.
- Term SOFR Reference rates based on futures contracts.

## SOME HISTORY

 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413003435092.png)

### OVERNIGHT INDEX SWAPS (IS)
- In a Is,  the two counterparties agree to exchange fixed for floating payments,  where the floating payment is tied to the cumulative return from an overnight rate
- Federal funds rate,  SOFR in US. Europe: short-term rate (eSTR),  (formerly Euro OverNight Index Average (EONIA) rate).
- Given a notional N,  the floating rate payment at time Ti is

$$CF\left(T_{i}\right)=N\left(\prod\limits_{j=1}^{n_{j}}\left(1+r_{t_{j}}\delta\right)-1\right)\tag{16}$$

- where δis the daily interval,  rt is the reference (annualized) overnight rate,  and nj is the number of days between reset periods.
- The day count convention is normally Actual/360.
- In the continuous time limit ($\delta\to0$),  we have that

$$CF\left(T_{i}\right)=N\left(e^{\frac{T_{i}^{T}}{T_{i-1}}\,  r\left(n\right)\mathrm{d}n}-1\right)\tag{17}$$

- Is with maturity less than 1 year have only one payment at the maturity.
- Is with longer maturities have normally quarterly payments.

## WHAT IS THE VALUE OF IS?
- The value of Is is the difference between the floating leg and the fixed leg:

$$V_{t}^{OIS}=V_{t}^{Floating}-V_{t}^{Fixed}\tag{18}$$

- **Floating Leg**: At reset dates,  and assuming the payment of a principal at maturity of the swap,
the value of the floating leg is par.
- Indeed,  investing the notional N in the overnight index daily gives at$T_i$

$$N\prod_{j=1}^{n_{j}}\left(1+r_{t_{j}}\Delta\right)=C F\left(T_{i}\right)+N$$

- =⇒ we can replicate the floating payments,  plus a residual of notional at maturity$T_i$,  with an
	investment N at time 0.

- lt follows$$V_0^{Floating}=N$$

.

- **Fixed leg:** Given a proper discount function ZOIS (0,  Ti),  we obtain

$$V_{0}^{Fixed}=N\ c\ \Delta\ \sum\limits_{i=1}^{n}Z^{OIS}\left(0,  T_{i}\right)+N\ Z^{OIS}\left(0,  T_{n}\right)\tag{19}$$

- The value of the contract at inception is zero,  $V^{OIS}_0= 0.$
- It follows from (18) then that

$$V_{0}^{O I S}=V_{0}^{F l o a t i n g}-V_{0}^{F i x e d}=0\tag{20}$$

- This equation implies that the swap rate c can be computed from

$$1=c\,  \Delta\,  \,  \sum\limits_{i=1}^{n}Z^{OIS}\left(0,  T_{i}\right)+Z^{OIS}\left(0,  T_{n}\right)\tag{21}$$

- which gives
$$
c(T_{n}) = \frac{1}{\Delta} \frac{1 - Z^{[OLS]}(0,  T_{n})}{\sum_{i=1}^{n} Z^{[OLS]}(0,  T_{i})} \tag{22}
$$

- where we now emphasize that the coupon rate $c$ is for a swap with maturity $T_{n}$,  and thus write $c(T_{n})$.

## IS DISCOUNT CURVE
- Given the Is coupon rates c (Ti) for every maturity Ti,  we can bootstrap the Is zero-coupon curve from (20).
- We obtain the relation:

$$Z^{OIS}\left(0,  T_{i}\right)=\frac{1-c\left(T_{i}\right)\,  \Delta\,  \,  \Sigma_{j=1}^{i-1}\,  Z^{OIS}\left(0,  T_{j}\right)}{1+c\left(T_{i}\right)\Delta}\tag{23}$$

- recalling,  however,  that Is with maturity less than or equal to 1 year generally have only one payment.
- Next Figure shows an example of bootstrapping from Is quotes,  on January 2,  2009. Panel A reports the original Is quotes from Bloomberg. Panel B uses the quotes from Panel A along with bootstrap methodology (23) and defines the Is discount function$Z^{OIS}(0,   T)$.

## IS DISCOUNT CURVE ON JANUARY 2ND,  2009

 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413003734183.png)

### IS AND [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] DISCOUNT CURVE ON JANUARY 2ND,  2007

 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413003806860.png)

- However,  if we try after the crisis,  we obtain the following figure:

## IS AND [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] DISCOUNT CURVE ON JANUARY 2ND,  2009

 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413003826513.png)

- which are quite different.

## CAPS,  FLOORS AND COLLARS
- A cap pays a stream of payments at$T_i,   i = 1,  ..,   n$with$T_{i+1} = T_i + ∆$,  where

$$C F\left(T_{i+1}\right)=\Delta\times N\times\operatorname*{max}\left(r_{n}\left(T_{i},  T_{i+1}\right)-r_{K}\right)$$

- where$∆$is the time interval between payments,  $N$is the notional and$r_n (T_i,   T_{i+1})$is the n−times compounded [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] rate.
- A floor pays$$CF\left(T_{i+1}\right)=\Delta\times N\times\max\left(r_{K}-r_{n}\left(T_{i},  T_{i+1}\right)\right)$$

## BLACK'S FORMULA FOR CAPLET VALUATION

- It is market practice to use Black's model to value Caps and Floors. - The main assumption is that under risk-adjusted probabilities (called "forward risk neutral probabilities"),  the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] rate has a log-normal distribution:

$$\ln\left(r_{n}\left(T_{i},  T_{i+1}\right)\right)\sim N\left(\mu_{i},  \sigma_{f,  i+1}^{2}T_{i}\right)$$

- where we assume σf,  i+1 is a constant volatility and the subscript i + 1 is maturity of the caplet.
- The valuation formula is then the following:

$$\mathsf{caplet}(T_{i+1})=\Delta\times N\times Z\left(0,  T_{i+1}\right)\left[f_{n}(0,  T_{i},  T_{i+1})\mathcal{N}\left(d_{1}\right)-r_{K}\mathcal{N}\left(d_{2}\right)\right]\tag{24}$$

- where$f_{n}(0,  T_{i},  T_{i+1}$is the forward rate,  and$$d_{1}=\frac{\ln\left(f_{n}(0,  T_{i},  T_{i+1})/r_{K}\right)+\sigma_{j+i+1}^{2}T_{i}/2}{\sigma_{j+i+1}\sqrt{T_{i}}};\quad d_{2}=d_{1}-\sigma_{j+i+1}\sqrt{T_{i}}$$
- Notice: We discount the payoff using$Z (0,   T_{i+1}$) and not$Z (0,   T_i)$as the cash flow is realized at time$T_{i+1}$.

## EXAMPLE
- On November 1,  2004. Consider a 1-year,  quarterly cap with strike rate$r_K = 2.555\%$.
- Assume this cap is *trading* at volatility$σ_f = 23.5\%$.
- The current [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] discount curve is as follows
- $Z(0,   0.25) = 99.4580$;
- $Z(0,   0.5) = 98.8510$;
- $Z(0,   0.75) = 98.1899$;
- $Z(0,   1) = 97.4834$.
- From the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curve,  we can compute the quarterly compounded forward rates:
- Forward Discount Factors

$$F(0,  T_{i-1},  T_{i})=\frac{Z(0,  T_{i})}{Z(0,  T_{i-1})}$$

- Forward rates

$$f_{4}(0,  T_{i-1},  T_{i})=4\times\left(\frac{1}{F(0,  T_{i-1},  T_{i})}-1\right)$$

- We obtain
- $f_4(0,   0.25,   0.5) = 2.4562\%;$
- $f_4(0,   0.5,   0.75) = 2.6932\%;$
- $f_4(0,   0.75,   1) = 2.8987\%$
- The last input in the Black's formula is the volatility$σ_f × √T_i$
- From the *quoted* volatility$σ_f = 23.5\%$,  we obtain

$$\begin{array}{l c l}{{\sigma_{f}\sqrt{T_{1}}}}&{{=}}&{{23.5\%\sqrt{0.25}=11.75\%;}}\\ {{\sigma_{f}\sqrt{T_{2}}}}&{{=}}&{{23.5\%\sqrt{0.50}=16.62\%;}}\\ {{\sigma_{f}\sqrt{T_{3}}}}&{{=}}&{{23.5\%\sqrt{0.75}=20.35\%.}}\end{array}$$

- At this point we have all the information to compute the value of each caplet in the cap.
- In particular,  using the formula for$d_1$and$d_2$we obtain
- $d_1(0.5) = -0.2770$;
- $d_2(0.5) = -0.3945$
- $d_1(0.75) = 0.4000;$
- $d_2(0.75) = 0.2338$
- $d_1(1) = 0.7218$;
=$d_2(1) = 0.5183$
- Then
$\text{caplet } (0.50)\ =\ \Delta\times N\times Z\,  (0,  0.50)\,  [2.4562\%\times{\cal N}\,  (d_{1}())-2.555\%\times{\cal N}\,  (d_{2}())]$$=\ 0.0184$

$\text{caplet } (0.75)\ =\ \Delta\times N\times Z\,  (0,  0.75)\,  [2.6932\%\times{\cal N}\,  (d_{1}())-2.555\%\times{\cal N}\,  (d_{2}())]$$=\ 0.0617$

$\text{caplet } (1.0)\ =\ \Delta\times N\times Z\,  (0,  1.0)\,  [2.8987\%\times{\cal N}\,  (d_{1}(1.0))-2.555\%\times{\cal N}\,  (d_{2}(1.0))]$$=\ 0.1057$

- and we obtain the value of the 1-year cap:

$$C a p(1Y)=0.0184+0.0617+0.1057=0.1859$$

## FLAT VOLATILITIES AND FORWARD VOLATILITIES
- Caps and floors are *quoted* in terms of flat volatilities.
- The volatility across caplets is kept constant for each cap.
- For example,  from Bloomberg (code SSRC),  one finds quotes such as

 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413004737317.png)

Source: Bloomberg.

- Each entry is a flat volatility for an "at-the-money" instrument,  meaning that its strike rate (equal for all the caplets) is the swap rate with the same maturity of the cap.
- The payment frequency of the underlying caps and floors is 3 months.
- Since the first payment at horizon 3 months is known at time 0,  it is practice to set this caplet equal to zero.

## FLAT VOLATILITIES AND FORWARD VOLATILITIES
- As an example,  from Table 1,  we obtain the following prices for caps
 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413005322596.png)
## FLAT VOLATILITIES AND FORWARD VOLATILITIES
- Issue: Consider the caps with maturities$T = 0.5,   T = 0.75,   T = 1.$
- The$T = 0.5$cap has only one caplet with (implied)volatility 21.156%
- The$T = 0.75$cap has two caplets each computed with (implied) volatility 22.066%
- The$T = 1$cap has three caplets each computed with (implied) volatility 23.500%
- It looks like the *same* caplet would have a different price,  depending on which cap it belongs to.
- Instead,  it is only a quoting convention,  and due to the distinction between **Flat** (or quoted) volatility and Forward Volatility
- The **Forward Volatility** (or spot volatility) of a caplet with maturity$T$and strike rate$r_K$is the volatility$σ^{Fwd}_f(T)$that characterizes that particular caplet.

## FLAT VOLATILITIES AND FORWARD VOLATILITIES
- Next table illustrates the relation between forward volatility and flat volatility
- The forward volatility is used to price individual caplets and thus obtain a value of the cap. - The flat volatility is used to *quote* the cap,  once its price is determined in the previous step. - The flat volatility is a sort of average (forward) volatility used for quoting purposes only.
 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413005455100.png)

## EXTRACTING THE FORWARD VOLATILITY FROM FLAT VOLATILITY

- To set up arbitrage strategies,  we need Forward Volatilities,  and not Flat volatilities.
- How do we extract the Fwd volatility from the Flat volatility?
- It is simple and analogous to the extraction of the discount$Z(t; T)$from bonds and swaps.
- We start from the shortest maturitity,  and then bootstrap the Fwd volatility out of the Flat volatility,  by using an iterative method.
- Consider a cap with maturity$T_i$and let$σ_f(T_i)$be its "flat volatility".
- Denote also$σ^{Fwd}_f(T_j)$the forward volatilities for$j = 1,   2,   …,   n.$
- For all$T_i$the following equations must hold

$$\begin{array}{l l}{{c a p\left(T_{i}\right)\ =\ \sum\limits_{j=1}^{i}c a p l e t\left(T_{j},  \overline{{{r}}}_{K,  i},  \sigma_{f}(T_{i})\right)}}\\ {{\qquad\qquad\qquad\left(\mathrm{How~the~market~quotes}\right)}}\\ {{\qquad\qquad\qquad\left(T_{j},  \overline{{{r}}}_{K,  i},  \sigma_{f}^{F w d}(T_{j})\right)}}\end{array}$$

$$\begin{array}{r l}{={}}&{{}\sum\limits_{j=1}^{i}c a p l e t}\\ {{}}&{{}{\mathrm{(Implied~by~no~arbitrage)}}}\end{array}$$

- where notice that the difference between the first and the second line is just the volatility.

## HOW DO WE EXTRACT THE$Σ^{FWD}_F(T_J)$?
- **Step 1**: Use the quoted (flat) volatilities to obtain cap prices for all maturities (see Table 2).
- **Step 2**: For the shortest maturity ($T_1  = 0.5$),  the cap has only one caplet,  and thus the forward and flat volatility must coincide. Thus:

$$\sigma_{f}(0.5)=\sigma_{f}^{F w d}(0.5)=21.156\%.$$

- Step 3: For each subsequent time$i=2,  ..$,  we use the following three step procedure:
1. Use the previously extracted forward volatilities$\sigma_f^{Fwd}(T_j)$for$j=1,  ..,  i-1$to compute the caplets up to$T_j,  Caplet\left(T_j,  r_{K,  i},  \sigma_f^{Fwd}(T_j)\right)$
1. Obtain the dollar value of the remaining caplet$T_i$as the difference between the cap price for$T_i$(obtained in Step 1) and the sum of caplets up to$T_{i-1}$

$$\text{Dollar value of }T_i \text{ caplet }=Cap(T_i)-\sum_{j=1}^{i-1}Caplet\left(T_j,  r_{K,  i},  \sigma_f^{Fwd}(T_j)\right)$$

1. Find the (forward) volatility$\sigma_f^{Fwd}(T_i)$such that

$$Caplet\left(T_i,  r_{K,  i},  \sigma_f^{Fwd}(T_i)\right)= \text{Dollar value of$T_i$caplet}$$

Dollar value of$T_{i}$**caplet**$=Cap(T_{i})-\sum\limits_{j=1}^{i-1}Caplet\left(T_{j},  r_{K,  i},  \sigma_{f}^{Fwd}(T_{j})\right)$

1. Find the (forward) volatility$σ^{Fwd}_f(T_j)$such that

$$C a p l e t\left(T_{i},  r_{K,  i},  \sigma_{f}^{F v d}(T_{i})\right)=\mathrm{Dollar~value~of~}T_{i}\mathrm{~caplet}$$

## EXAMPLE
- For instance,  the second cap ($T_2  = 0.75$) has a dollar price of$*Cap*(T_2) = \$0.1059$. We now use the three-step procedure in Step 3 above:
1. Compute the$T_1$caplet using the forward volatility$σ^{Fwd}_f(T_i)$= 21.1564\% just computed.
Using the Black formula,  we obtain

$$C a p l e t(T_{1},  r_{K},  \sigma_{f}^{F w d}(T_{1}))=\$0.0273$$

1. The dollar value of the$T_2$caplet is then

$$\text{Dollar value of$T_2$caplet} =Cap(T_{2})-Caplet\left(T_{1},  r_{K},  \sigma_{f}^{Fwd}(T_{1})\right)$$

$=$$\$0.1059-\$0.0273=\$0.0786$

1. Use the Black formula again to find the (forward) volatility$σ^{Fwd}_f(T_2)$such that

$$C a p l e t\left(T_{2},  r_{K},  \sigma_{f}^{F w d}(T_{2})\right)=\$0.0786\ \implies\ \sigma_{f}^{F w d}(T_{2})=22.81\%$$

- Similarly,  the T3 forward volatility is obtained as follows:
1. Compute the$T_1$and$T_2$caplets using the forward volatilities$σ^{Fwd}_f(T_1)$= 21.1564% and
$σ^{Fwd}_f(T_2)$= 22.81% just computed. Using the Black formula with the new strike rate$r_K =$
1.4420%,  we obtain

$$\begin{array}{l}{{C a p l e t(T_{1},  r_{K},  \sigma_{f}^{F w d}(T_{1}))=\$0.0157}}\\ {{C a p l e t(T_{2},  r_{K},  \sigma_{f}^{F w d}(T_{2}))=\$0.0605}}\end{array}$$

1. The dollar value of the$T_3$caplet is then

$$\text{Dollar value of$T_3$caplet} =Cap(T_{3})-\sum\limits_{j=1}^{2}Caplet\left(T_{j},  r_{K},  \sigma_{f}^{Fud}(T_{j})\right)$$

$=$$\$0.1859-(\$0.0157+\$0.0605)=\$0.1096$

3. Use the Black formula again to find the (forward) volatility$σ^{Fwd}*f(T_3)$such that

$$C a p l e t\left(T_{3},  r_{K},  \sigma_{f}^{F w d}(T_{3})\right)=\$0.1096\ \ \Longrightarrow\ \ \sigma*{f}^{F w d}(T_{3})=25.54\%$$

- Figure 1 plots the forward and flat volatilities on November 1,  2004
 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413010625250.png)
- Flat volatilities can be thought of a "cumulated averages" of forward volatilities.
- Cap (Quoted) Volatility Changes Over Time.
 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413010654352.png)
- The average forward volatility curve is hump shaped:
 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413010713355.png)
- The forward volatility has various shapes through time:
 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413010740064.png)
- The forward volatility is strongly time varying:
 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413010802155.png)

- where "slope$=\sigma_{f}^{Fwd}(10)-\sigma_{f}^{Fwd}(1)$" and "curvature$=2\sigma_{f}^{Fwd}(2)-\sigma_{f}^{Fwd}(1)-\sigma_{f}^{Fwd}(10)$.

## PUT-CALL PARITY
- A put-call parity relationship exists for caps and floors.
- Clearly,  a portfolio of a long caplet and short floorlet with equal strikes gives

$$\operatorname*{max}\left(r_{n}\left(\tau,  T\right)-r_{K}\right)-\operatorname*{max}\left(r_{K}-r_{n}\left(\tau,  T\right)\right)=r_{n}\left(\tau,  T\right)-r_{K}$$

- But this is the payoff to a swap. Hence,  we have

$$\mathsf{c a p=f l o o r+s w a p}$$

## SWAPTIONS
- A buyer of a swaption has *the right,  but not the obligation* to enter into a swap with given characteristics (such as maturity,  swap rate,  payment frequency,  etc.) at a given maturity$T_O$.
- Ina *payer swaption* the swaption buyer has the right to enter into a swap as a fixed-rate payer (and receive floating.) In a *receiver swaption* the swaption buyer has the right to enter into the swap as fixed-rate receiver (and pay floating).
- For instance,  in Table 1,  an investor can purchase an at-the-money six-month option to enter into a 10-year swap at "implied volatility" of 21.883%.

 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413010916470.png)

- A swap,  recall,  is a contract between two parties to exchange at times$T_1,  ..,   T_n$the net cash flows

$$C F\left(T_{i+1}\right)=\Delta\times N\times\left(r_{K}-r_{n}\left(T_{i},  T_{i+1}\right)\right)$$

- On each of the reset dates dates,  the value of the swap is

$$V\left(T_{i},  r_{K}\right)=P\left(T_{i},  T;r_{K}\right)-100$$

- where$P (T_i,   T; r_K)$is the price of a coupon bond with$r_K$as coupon rate and maturity$T$.
- Consider an option that gives its holder the right (not the obligation) to enter as the fixed rate
receiver in the swap at time$T_O = T_{i^∗}$for some$i^∗ < n$,  at the exercise rate$r_K$.
- Let$c (T_{i^∗},   T)$be the market swap rate at time$T_{i^∗}$for a swap maturing at$T$.
- If$c (T_{i^∗},   T) < r_K$,  optimal to exercise the option (and receive$r_K$instead of lower$c (T_{i^∗},   T).$
- If$c (T_{i^∗},   T) *> r_K$,  optimal not to exercise the option (better receive the market rate$c (T_{i^∗},   T).$

## SWAPTION PAYOFF
- We now show that the payoff of a receiver swaption is positive if and only if the market swap rate is below the strike swap rate:

$$V\left(T_{i^{*}},  r_{K}\right)>0\Longleftrightarrow c\left(T_{i^{*}},  T\right)<r_{K}$$

- The payoff from the Swaption can be written as

$$
\begin{align} \text{Payoff} &= V\left(T_{i^*},  r_K\right)-0 \\ &= V\left(T_{i^*},  r_K\right)-V\left(T_{i^*},  c\left(T_{i^*},  T\right)\right) \\ &= \left[P\left(T_{i^*},  T;r_K\right)-100\right]-\left[P\left(T_{i^*},  T;c\left(T_{i^*},  T\right)\right)-100\right] \\ &= P\left(T_{i^*},  T;r_K\right)-P\left(T_{i^*},  T;c\left(T_{i^*},  T\right)\right) \\ &= \sum_{j=i^*+1}^n Z\left(T_{i^*},  T_j\right)r_K\Delta N+Z\left(T_{i^*},  T_n\right)\times1 \\ &- \sum_{j=i^*+1}^n Z\left(T_{i^*},  T_j\right)c\left(T_{i^*},  T\right)\Delta N-Z\left(T_{i^*},  T_n\right)\times1 \\ &= \sum_{j=i^*+1}^n Z\left(T_{i^*},  T_j\right)\Delta N\left(r_K-c\left(T_{i^*},  T\right)\right) \end{align}
$$

- The value of a swap at time$T_O$is positive if and only if$(r_K − c (T_{i^∗},   T)$)
- Clearly,  the option buyer exercises the option if and only if the payoff is positive,  so the receiver
swaption payoff at$T_{i^∗}$is

$$\mathrm{Payoff~of~Receiver~Swaption}~=~\sum\limits_{j=i^{*}+1}^{n}{Z\left(T_{i^{*}},  T_{j}\right)\Delta N\operatorname*{max}\left(r_{K}-c\left(T_{i^{*}},  T\right)\right)}$$

- The payoff to the swap is equivalent to the cash flow

$$\Delta N\max\left(r_{K}-c\left(T_{i^{*}},  T\right)\right)$$

determined at$T_{i^∗}$,  paid out at times$T_{i^{*}+1},  T_{i^{*}+2},  …,  T_{n}$,  and thus discounted to$T_{i^{*}}$through the terms$\Sigma_{j=i^{*}+1}^{n}\,  Z\left(T_{i^{*}},  T_{j}\right)$.

- The payoff at each time Ti∗+j is always the same determined at$T_{i^∗}$.
- Similar,  the payer swaption payoff at$T_{i^∗}$is

$$\mathrm{Payoff~of~Payer~Swaption}~=~\sum\limits_{j=i^{*}+1}^{n}Z\left(T_{i^{*}},  T_{j}\right)\Delta N\operatorname*{max}\left(c\left(T_{i^{*}},  T\right)-r_{K}\right)$$

### PAYOFF OF RECEIVER SWAPTION

 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413011725253.png)

## SWAPTION PRICING

- The price of the receiver swaption is obtained by pricing each of those payments
$∆N max (r_K − c (T_{i^∗},   T),   0)$at times$T_{i^∗+1},   T_{i^∗+2}*,   …,   T_{i^∗+n}$,  individually.
- Like for caps and floors,  the Black's formula assumes that under the proper risk-adjusted probabilities,  the swap rate$c (T_{i^∗},   T)$is log-normally distributed

$$\log c\left(T_{i^{*}},  T\right)\sim\mathcal{N}(\mu,  \sigma_{T_{i^{*}}}^{2}T_{i^{*}})$$

- where$σ_{T_i^∗}$is the swap rate volatility,  which is what is quoted by market participants
- Thus,  the (risk adjusted) expected value of a payer and receiver cash flows at$T_{i^∗+j}$are,  respectively,

$$\begin{array}{l c l}{{E^{*}\left[P V\left[\max\left(c\left(T_{r},  T\right)-r_{K}\right)\right]\right]}}&{{=}}&{{Z\left(0,  T_{r^{*}+j}\right)\,  \left[f_{n}^{s}(0,  T_{r},  T)\mathcal{N}\left(d_{1}\right)-r_{K}\mathcal{N}\left(d_{2}\right)\right]}}\\ {{E^{*}\left[P V\left[\max\left(r_{K}-c\left(T_{i},  T\right)\right)\right]\right]}}&{{=}}&{{Z\left(0,  T_{r^{*}+j}\right)\,  \left[-f_{n}^{s}(0,  T_{i^{*}},  T)\mathcal{N}\left(-d_{1}\right)+r_{K}\mathcal{N}\left(-d_{2}\right)\right]}}\end{array}$$

- where$f^s_n(0,   T_{i^∗},   T)$is the **forward swap rate.** and

$$d_{1}=\frac{\ln{(f_{n}^{s}(0,  T_{i^{*}},  T)/r_{K})}+\sigma_{T_{i^{*}}}^{2}T_{i^{*}}/2}{\sigma_{T_{i^{*}}}\sqrt{T_{i^{*}}}};\quad d_{2}=d_{1}-\sigma_{T_{i^{*}}}\sqrt{T_{i^{*}}}$$

- $µ$is set up so that$f^s_n(0,   T_{i^∗},   T) = E^∗_f[c (T_{i^∗},   T)]$under the proper risk-adjusted probabilities.

### QUOTED SWAPTION IMPLIED VOLATILITY SURFACE

 ![500](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413012213337.png)

## SWAPTION PRICING

- Hence,  the value of a payer swaption$$\mbox{Payer Swaption}=\sum\limits_{j=i^{\prime}+1}^{n}\Delta\times N\times Z\left(0,  T_{j}\right)\left[f_{n}^{*}(0,  T_{i^{\prime}},  T){\cal N}\left(d_{1}\right)-r_{K}{\cal N}\left(d_{2}\right)\right]$$$$=AN\left[f_{n}^{*}(0,  T_{i^{\prime}},  T){\cal N}\left(d_{1}\right)-r_{K}{\cal N}\left(d_{2}\right)\right]$$
- where$$A=\sum\limits_{j=i^{\prime}+1}^{n}\Delta\times Z\left(0,  T_{j}\right)$$
- Similarly,  the value of a receiver swaption is

$$\text{Receiver Swaption}\ =\ A N\left[-f_{n}^{s}(0,  T_{i^{*}},  T){\mathcal{N}}\left(-d_{1}\right)+r_{K}{\mathcal{N}}\left(-d_{2}\right)\right]$$

## HOW DO WE COMPUTE THE FORWARD SWAP RATE?
- This is implicit in the forward discount curve

$$F\left(0,  T_{i^{*}},  T\right)=\frac{Z\left(0,  T\right)}{Z\left(0,  T_{i^{*}}\right)}$$

- Using that just as a discount function and following the same steps as for regular swap rate,  we can compute the Forward Swap Rate$f_{n}^{*}(0,  T_{i^{*}},  T)$,  for a swap starting at time$T_{i}$,  and lasting until time$T_{i}$,  as$$f_{n}^{*}(0,  T_{i^{*}},  T)=\frac{1}{\Delta\sum_{j=i^{*}+1}^{n}F\left(0,  T_{i^{*}},  T_{i}\right)}$$

## EXAMPLE
- Today is November 1,  2004. Consider a 1-year swaption to enter into a 5-year swap at strike rate$r_K = 3.751\%$.
- Table 1 shows that such a swaption is trading at implied volatility$σ^s_f = 27.404\%$.
- Table 4 provides the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] discount curve up to$T = 6$.
- to derive the Forward Discount curve we also need$Z(0,   1) × 100 = 97.48.$
- We then obtain$$A=\Delta\times\sum\limits_{i=1}^{n}Z(0,  T_{i})=4.4046$$
- The forward swap rate can be computed from the forward discounts using the previous formula$f_{4}^{i}(0,  T_{O},  T_{S})=4.261\%$

$$d_{1}=\frac{ln(4.261\%/3.751\%)+0.27404^{2}\times1/2}{0.27404\times\sqrt{1}}=0.6023\,  \ d_{2}=0.6023-0.27404\times\sqrt{1}=0.3282$$

- The Black's formula then gives for a receiver swaption with$N=100$:$$\mathsf{Swaption}=\sum\limits_{j=i+j+1}^{n}\Delta\times N\times Z\left(0,  T_{j}\right)\left[-f_{n}^{\circ}(0,  T_{i},  T)\mathcal{N}\left(-d_{1}\right)+r_{K}\mathcal{N}\left(-d_{2}\right)\right]$$$$=\$1.0026$$

![|400](Z.%20Clippings/Lecture%20Note%204%20Interest%20Rate%20Derivatives-20240413012519770.png)
