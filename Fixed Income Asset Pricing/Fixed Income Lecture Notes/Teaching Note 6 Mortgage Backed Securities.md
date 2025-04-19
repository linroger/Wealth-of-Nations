---
cssclasses:
  - academia
title: Teaching Note 6 Mortgage Backed Securities
tags:
  - house_prices
  - mbs
  - mortgage_backed_securities
  - prepayment_option
  - securitization
aliases:
  - FHLMC
  - FNMA
  - GNMA
  - MBS
  - Teaching Note 6
key_concepts:
  - House prices
  - MBS market
  - Mortgage lenders
  - Prepayment option
  - Securitization process
---

# Teaching Note 6 Mortgage Backed Securities

[[Fixed Income Lecture Notes]]

 [[Introduction to Fixed Income Asset Pricing]]

 [[Lecture Note 2Interest Rate Risk Management And Factors]]

 [[Forward Rates and Term Structure]]

 [[Teaching Note 4 Interest Rate Derivatives]]

 [[Teaching Note 5 Risk Neutral Pricing]]

[Teaching Note 6 Mortgage Backed Securities](Teaching%20Note%206%20Mortgage%20Backed%20Securities.md)

[Teaching Note 7 A Rundown On Continuous Time Models](Teaching%20Note%207%20A%20Rundown%20On%20Continuous%20Time%20Models.md)

[PSET VI Fixed Income](PSET%20VI%20Fixed%20Income.md)

![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513040901834.png)

(Source: SIFMA and FRED at Federal Reserve of St. Louis.)

## HOUSE PRICES AND THE MORTGAGE BACKED SECURITIES MARKET

![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513042227294.png)

## THE SECURITIZATION PROCESS

![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513042528794.png)

## HOUSE PRICES AND THE MORTGAGE BACKED SECURITIES MARKET MBS PLAYERS
- Three main government sponsored agencies exist:
	- FNMA (Federal National Mortgage Association,  or Fannie Mae): Used to be a publicly traded corporation,  but it was placed in conservatorship in September 2008. It provides secondary markets for mortgage loans from FHA (Federal Housing Administration) and VA (Veterans Administration).
	- GNMA (Government National Mortgage Association,  or Ginnie Mae): Government owned. GNMA guarantees loans in FHA and VA.
	- FHLMC (Federal Home Loan Mortgage Corporation,  or Freddie Mac): Similarly to Fannie Mae,  it provides a link between mortgage lenders and capital markets. It buys from S&Ls,  mortgage bankers and commercial banks,  and sell mortgage pass-through securities.
- In addition,  other private labels also exist,  although in recent times they cover a small fraction of the total issuance,  because of credit risk
- There are some differences across the agencies on the type of mortgage pools they guarantee or buy/sell.
- The most common MBS is the **Pass-Through MBS**: all the cash flows from the original pool are passed to the investors.
- Pass through MBSs have their own interest rate rPT,  lower than the average mortgage rate in the pool as agencies keep a fee for arranging the MBS market (and provide default insurance)

## MORTGAGE RELATED ISSUANCE

![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513042733446.png)

## MORTGAGES AND THE PREPAYMENT OPTION
- It is important to review some basic facts about mortgages.
- Consider a 30-year fixed-rate mortgage,  with mortgage rate of $r_{m}$.
- Let $L$ be the amount of the mortgage lent from the bank to the homeowner.
- According to the standard present value relation,  the periodic coupon $C$ must satisfy:

$$L=\sum_{i=1}^{30\times12}\frac{C}{\left(1+\frac{r_{12}}{12}\right)^{i}}=\sum_{i=1}^{30\times12}C\times A^{i}\tag{1}$$

- where
$$A=\frac{1}{1+\frac{r_{12}}{12}}\tag{2}$$

- The coupon in (1) is then given by
$$C=\frac{L}{\sum_{i=1}^{10\times12}A^{i}}\tag{3}$$

- The interest and the principal paid at any time $t$ are given by:
$$
\begin{align*}
\text{Interest paid at } t &= I_t = \frac{\bar{r}_{12}^m}{12} \times L_t & (4) \\
\text{Principal paid at } t &= L_t^{\text{paid}} = C - I_t & (5) \\
\text{Principal outstanding at } t+1 &= L_{t+1} = L_t - L_t^{\text{paid}} & (6)
\end{align*}
$$

## SCHEDULED PRINCIPAL BALANCE,  SCHEDULED INTEREST,  AND PRINCIPAL PAYMENTS

![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513043858376.png)

## THE REFINANCING OPTION
- The value of the mortgage debt changes over time as mortgage rates change:
$$\text{Value of mortgage debt}  = P(t)=\sum\limits_{i=1}^n{\frac{C}{{\left({1+r_{12}^m(t, T_i)/12}\right)^i}}}$$
	- where $n$ is the number of payments left at time $t$ and $r_{m}^{12}(t,  T_i)$ are appropriate spot rates,  related to the current term structure of mortgage rates.
- At every $t$,  the homeowner can compare the amount of principal left to pay,  $L_{t}$,  with the market value of his liability to the bank $P(t)$.
- As in any bond,  $P(t)$ increases in value whenever interest rates decline.
	- $\Rightarrow$ when interest rates decline,  $P(t)$ may increase to a higher level than $L_{t}$
	- $\Rightarrow$ optimal to _refinance_ the mortgage.

## REFINANCING AND THE FEDERAL FUNDS RATE: 1990 - 2008

![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513044025239.png)

## MORTGAGE PREPAYMENTS

- Interest rate declines are one component of prepayment,  albeit very important.
- Other reasons include the following:
	1. Seasonality: (Late) summers are characterized by larger prepayments due to relocation.
	1. Age of mortgage pool: Young (but not too young) mortgage pools tend to be refinanced more heavily.
	1. Family circumstances: Defaults,  disasters,  or sale of the house.
	1. Housing prices: Higher prices make it easier to refinance.
	1. Burnout effect: Mortgage pools heavily refinanced in the past tend to be insensitive to interest rates.
		- If a mortgage pool has been heavily refinanced in the past,  most homeowners who could refinance already did.
		- The only homeowners left in the pool are those who could not refinance.
	1. Media effect: The more newspaper talk about refinancing possibilities,  the more refinancing actually occurs.

## STANDARD MEASURES OF PREPAYMENT SPEED
- The industry developed some standard measures of prepayments to "characterize" the type of prepayment.
- **Constant Maturity Mortality**: It assumes a constant probability $p$ that the mortgage will be prepaid after the next coupon.
$$\Pr\left(\mathrm{Prepayment~at~time~}t=n\mathrm{~months~from~now}\right)~=~\left(1-p\right)^{n}p$$
- The annualized rate,  the **conditional prepayment rate** (CPR) is given by:
$$\operatorname{Pr}{\mathrm{Survival~up~to~time~}t=12)}=(1-p)^{12}=(1-CPR)$$
- Thus,  the CPR is computed from $p$ as $CPR = 1 - (1 - p)^{12}$
- **PSA Experience** The benchmark 100% PSA (Public Securities Association),  makes the following assumptions:
	1. CPR = 0.2% of the principal is paid in the first month;
	1. CPR increases by 0.2% in each of the following 30 months; and
	1. CPR then levels off at 6% until maturity.
- This measure makes the amount of prepayment depend only on the age of the mortgage pool.
- By scaling up or down the CPR in the PSA description,  we obtain faster or slower speeds of prepayments.

## PSA PREPAYMENT CONVENTION

![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513044122162.png)

## PSA AND MBS PRICING
- A PSA prepayment speed is simply a quoting convention to allow traders to quote RMBS (Residential Mortgage-Backed Securities).
- Given a PSA speed,  it defines the path for the monthly prepayment probability $p_{t}$.
- Given the path $\{p_{t}\}$,  the MBS cash flows follow. Let $L_{t}$ be the outstanding principal,  then:
$$\begin{align*}
\text{Mortgage interest payment:} \quad & I_t = \frac{\bar{r}_{12}^m}{12} \times L_t & (7) \\
\text{Scheduled principal:} \quad & \text{Pay}_{t}^{\text{scheduled}} = C_t - I_t & (8) \\
\text{Principal prepayment:} \quad & \text{Pay}_{t}^{\text{prepaid}} = p_t \times (L_t - \text{Pay}_{t}^{\text{scheduled}}) & (9) \\
\text{Outstanding principal:} \quad & L_{t+1} = L_t - \text{Pay}_{t}^{\text{scheduled}} - \text{Pay}_{t}^{\text{prepaid}} & (10) \\
\text{Update of scheduled coupon:} \quad & C_{t+1} = (1 - p_t) \times C_t & (11)
\end{align*}$$
- Given the dynamics of $L_{t}$ implicit in PSA,  we can compute the path through future cash flows.
- $$ \begin{align*} \text{Pass-through interest payment:} \quad & I_t^{PT} = \frac{r_{12}^{PT}}{12} \times L_t & (12) \\ \text{Total cash flow:} \quad & CF_t = I_t^{PT} + \text{Pay}_{t}^{\text{scheduled}} + \text{Pay}_{t}^{\text{prepaid}} & (13) \end{align*} $$
- The price of the pass-through MBS is then simply:
$$P^{MBS}(0, T)=\sum_{t=1}^{T}Z(0, t)CF_{t}\tag{14}$$
## THE NEGATIVE CONVEXITY OF MORTGAGE BACKED SECURITIES
- When interest rates drop,  regular T-bonds increase in a convex manner.
- However,  if prepayment occurs,  then Mortgage Backed Securities will move towards principal.
	- $\Rightarrow$ negative convexity
- Indeed,  MBS is equal to a portfolio with long bond and short call option.
- While long bond has positive convexity,  the short call has a strong negative convexity.
- Negative convexity implies a negative loss on average:
$$P^{MBS}(t+1, T)\thickapprox P^{MBS}(t, T)+\frac{dP^{MBS}(t, T)}{dr}(r(t+1)-r(t))+\frac{1}{2}\frac{d^{2}P^{MBS}(t, T)}{dr^{2}}(r(t+1)-r(t))^{2}+..$$

_Thus,  assuming_ *over a short period*: $E\left[r(t+1)-r(t)\right]=0$,  we have:
$$E\left[\frac{P^{MBS}(t+1, T)-P^{MBS}(t, T)}{P^{MBS}(t, T)}\right]\approx\frac{1}{2}\;C\;E\left[(r(t+1)-r(t))^{2}\right]$$
- Because $E\left[(r(t+1)-r(t))^{2}\right]>0$,  the negative convexity $C$ implies an average loss generated by the average variation in interest rates.

## THE VALUE OF A PASS-THROUGH MBS WITH RESPECT TO THE INTEREST RATE
![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513044611881.png)

## THE CONVEXITY OF MBS: GNMA 7 PRICES AND MORTGAGE RATES 
![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513044633319.png)
## REFINANCING SPEED AND RATES: GNMA 7 PSA AND MORTGAGE RATES 
![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513044708416.png)

## A HIGHER YIELD FOR MBS 
A Sample Of Par Value Ginnie Mae Pass-Through Prices And Treasury Yields
![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513044731231.png)
 - MBS securities pay a higher coupon than similar Treasury securities,  even if credit risk is the same 
	 – Ginnie Mae-issued RMBS have the full backing of the US government.
## RMBS AND INTEREST RATE RISK MANAGEMENT: EXAMPLE
- Let today be June 8,  2007,  and assume we have invested $300 million in the GNSF 6 pass-through.
	- The underlying pool of this pass through has a WAC of 6.5% and a WAM of 320 months.
	- The pass through has a 6% coupon,  and it is quoted at bid/ask prices = 99.4375 / 99.40625.
- We want to hedge the risk against an increase in interest rates. How do we compute duration and convexity?
	- For instance,  simply using the same formulas as for bonds seems wrong. Indeed,  two simple formulas are:
$$D\\ =\\ -\frac{1}{P^{MBS}(0, T)}\frac{dP^{MBS}(0, T)}{dr}=\sum_{i=1}^{n}w_{i}T_{i};\quad\mbox{and}\tag{15}$$
$$C\\ =\\ \frac{1}{P^{MBS}(0, T)}\frac{d^{2}P^{MBS}(0, T)}{dr^{2}}=\sum_{i=1}^{n}w_{i}T_{i}^{2}\tag{16}$$
-- where
$$w_{i}=\frac{CF_{t}Z(0, T_{i})}{P^{MBS}(0, T)}$$
- This calculation yields D = 4.39 and C = 36.1590.
	- Where is the negative convexity?
## RMBS AND INTEREST RATE RISK MANAGEMENT: PSA-ADJUSTED EFFECTIVE DURATION
- The earlier computations do not take into account that PSA speed,  and thus CFs,  change with the interest rate.
- The PSA-adjusted Effective Duration corrects for this.
- How can we forecast the change in PSA speed for a given interest rate?
	- SIFMA survey forecasts provide a simple way:
	- ![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513044935959.png)

## RMBS AND IRRM: PSA-ADJUSTED EFFECTIVE DURATION AND CONVEXITY
- We can use these projections to adjust the cash flows.
- Using for instance a 50bps increase / decrease,  we obtain:
$$D\\ \approx\\ -\frac{1}{P}\frac{P(+50bps)-P(-50bps)}{2\times50bps}=-\frac{1}{99.43}\frac{96.79-101.43}{2\times50bps}=4.68$$
$$C\\ \approx\\ \frac{1}{P}\frac{P(+50bps)+P(-50bps)-2\times P}{(50bps)^{2}}=\frac{1}{99.43}\frac{96.79+101.43-2\times99.43}{(50bps)^{2}}=-251.08$$
- Using instead a 100bps increase / decrease,  we obtain:
$$D\\ \approx\\ -\frac{1}{P}\frac{P(+100bps)-P(-100bps)}{2\times100bps}=-\frac{1}{99.43}\frac{94.00-102.24}{2\times100bps}=4.14$$
$$C\\ \approx\\ \frac{1}{P}\frac{P(+100bps)+P(-100bps)-2\times P}{(100bps)^{2}}=\frac{1}{99.43}\frac{94.00+102.24-2\times99.43}{(100bps)^{2}}=-262.63$$
- These numbers for convexity are much more in line with the intuition that cash flows increase when interest rate decline,  because of the prepayment option.
## RMBS AND IRRM: EMPIRICAL DURATION AND CONVEXITY
- A third methodology is to use past data to inform about the sensitivity of MBS to changes to interest rates.
	- This methodology can be particularly useful as we can check the relation between MBS prices and the relevant interest rate for hedging.
	- Given the liquidity of the OTC swap market,  interest rate swaps are typically the preferred derivative instrument to hedge against changes in interest rates.
- Next figure shows the relation between GNMA prices,  and the 5-year swap rate.
- Using these data,  and denoting $c_{t}(5)$ the 5-year swap rate at $t$,  we can estimate a (simple) polynomial regression:
$$P_{t}=\alpha+\sum_{i=1}^{4}\beta_{i}\times c_{t}(5)^{i}+\epsilon_{t}$$
- Given the estimates,  we can easily compute $dP/dr$ and $d^2P/dr^2$,  obtaining then:$$\text{Empirical Duration}=-\frac{1\\ d\\ P}{P\\ d\\ c(5)}=\frac{444.66}{99.4219}=4.4725\tag{17}$$ $$ \text{}{Empirical Convexity}=\frac{1\\ d^{2}\\ P}{P\\ d\\ c(5)^{2}}=\frac{-14731.4}{99.4219}=-148.17\tag{18}$$
- Given D and C,  hedging can then be achieved using the same methodologies as before.
## GNSF 6 PRICE AND THE 5-YEAR SWAP RATE
![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513045223878.png)
## PRICING PREPAYMENT OPTION ON BINOMIAL TREES
- Mortgages have an implicit American option. We can use Binomial Trees to evaluate its fair value.
- This is the first step to compute the fair value of Mortgage Backed Securities using no-arbitrage methods.
- **Example**: consider the simple case with annual rather than monthly payments.
- Suppose that interest rate tree is the following:
![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513045252337.png)
- Consider a $10, 000 mortgage with 4 years to maturity,  and mortgage rate $r^{m}=0.0372$ (annually compounded).
- We need to compute the principal amounts left after each coupon payment.
- What is the annual coupon?
$$\sum_{i=1}^{4}{\frac{C}{(1+\overline{r}^{m})^{i}}}$$
- Need to solve
$$10000 = \sum_{i=1}^{4}{\frac{C}{(1+0.0372)^{i}}}$$
- This yields C = 2736.7581.
- We then obtain:
![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513045320580.png)
- We now need to compute the value of the American option implicit in the mortgage.
- At every payment date,  we must compare the net present value of future mortgage payments with the principal remaining.
- Refinancing occurs when the NPV of future payments is above principal.
- So,  first we compute the NPV of future payments:
![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513045404788.png)

$V_{3, uuu}^{*} = = Ce^{-r_{3, uuu}} = 2480.8488$
$V_{2, uu} = e^{-r_{2, uu}} \times (C + +(V_{3, uuu} + V_{3, uud}^{*})/2) = 4829.9989$
$V_{3, uud}^{*} = = Ce^{-r_{3, uud}} = 2560.4575$
$V_{1, u} = e^{-r_{1, u}} \times (C + +(V_{2, uu} + V_{2, ud})/2) = 7230.0589$
$V_{0} = e^{-r_{0}} \times (C + +(V_{1, u} + V_{1, d})/2) = 10075.5088$
$V_{2, ud} = e^{-r_{2, ud}} \times (C ++(V_{3, uud} + V_{3, udd}^{*})/2) = 5059.7826$
$V_{3, udd}^{*} = = Ce^{-r_{3, udd}} = 2609.4939$
$V_{1, d} = e^{-r_{1, d}} \times (C + +(V_{2, dd} + V_{2, ud})/2) = 7788.8393$
$V_{2, dd} = e^{-r_{2, dd}} \times (C + +(V_{3, ddd} + V_{3, udd}^{*})/2) = 5301.7548$
${{V_{3, ddd}}} {{=Ce^{-r_{3, ddd}}=2693.2308}}$
- The net present value of future mortgage payments is 10075.5089.
- Notice that the bank has only given them $10000.
- However,  the bank is selling an American call to the home-owner,  which is valued in the next tree.
- (For the sake of simplicity,  denote by $(a,  b)^{+} = \max(a,  b)$)
- From the tree,  we see that the value of the mortgage is fair:
![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513045442377.png)
$CA_{3, uuu}^{*} = = (V_{3, uuu}^{*} - P_{3},  0)^{+} = 0$
$CA_{2, uu} = (V_{2, uu} - P_{2},  e^{-r_{2, uu}}\frac{CA_{3, uuu}+CA_{3, uud}}{2} )^{+} = 0$
$CA_{1, u} = (V_{1, u} - P_{1},  e^{-r_{1, u}}\frac{CA_{2, uu}+CA_{2, ud}}{2} )^{+} = 0$
$CA_{3, uud}^{*} = = (V_{3, uud}^{*} - P_{3},  0)^{+} = 0$
$CA_{2, ud} = (V_{2, ud} - P_{2},  e^{-r_{2, ud}}\frac{CA_{3, uud}+CA_{3, udd}}{2} )^{+} = 0$
$CA_{0} = e^{-r_{0}}\times \times\frac{CA_{1, u}+CA_{1, d}}{2} ) = 75.5089$
$CA_{1, d} = (V_{1, d} - P_{1},  e^{-r_{1, d}}\frac{CA_{2, ud}+CA_{2, dd}}{2} )^{+} = 153.5762$
$CA_{3, udd}^{*} = = (V_{3, udd}^{*} - P_{3},  0)^{+} = 0$
$CA_{2, dd} = (V_{2, dd} - P_{2},  e^{-r_{2, dd}}\frac{CA_{3, udd}+CA_{3, ddd}}{2} )^{+} = 119.2019$
$CA_{3, ddd}^{*} = = (V_{3, ddd}^{*} - P_{3},  0)^{+} = 54.6340$
## PRICING PASS THROUGH'S ON BINOMIAL TREES
- We now look at how to value PT securities on a binomial tree
- The main difference between valuing a PT security and valuing the mortgage in the previous example is that the PT security has a lower interest rate than the coupon rate.
- The lower coupon paid by the issuer of the PT security to investors compared to the average mortgage coupon rate (WAC) is due in part as a compensation for holding default risk and in part as a service fee.
- The following is the same example as earlier,  but now we compute the value of a PT security with coupon rate $r_{PT}=2\%$.
- In the original tree,  exercise only occurs at the nodes $(1,  d)$,  $(2,  dd)$,  $(3^{*},  ddd^{*})$.
- At these nodes,  the value of the PT security simply equals the outstanding principal.
- Given these cash flows,  the computation of the value of the PT security proceeds exactly as any other fixed income security.
- As a sanity check,  note that if we use $r_{PT}=$,  we indeed obtain $V^{PT}_{0}$ =10000
![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513045514772.png)

$$V_{3, uuu}^{PT}=\\=e^{-r_{3, uuu}}\times\\
\left(2638.597\times r_{PT}\\+2638.597\right)\\=2439.704\\\\\\\\V_{3, uud}^{PT}=\\=e^{-r_{3, uud}}\times\\
\left(2638.597\times r_{PT}\\+2638.597\right)\\=2517.992\\\\\\\\\\\\V_{3, udd}^{PT}=\\=e^{-r_{3, udd}}\times\\
\left(2638.597\times r_{PT}\\+2638.597\right)\\=2566.215$$
## PRICING PASS THROUGH'S ON BINOMIAL TREES
- On a "bigger tree",  consider a 5-year mortgage with $N = $100,  000$ and semi-annual payments.
- The semi-annually compounded mortgage rate is $r^{m}_{2}=7.564\%$ $\Rightarrow C=\$12196$.
- Today is January 31,  2000: What is the value of this mortgage? What is the value of a pass-through security on a pool of mortgages with WAC = 7.564% and WAM = 5 years?
- First,  we fit a tree to the current term structure of interest rates:
## ZERO COUPON BONDS AND THE SIMPLE BDT MODEL ON JANUARY 31,  2000
![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513045658819.png)

## THE MORTGAGE VALUE WITHOUT PREPAYMENT OPTION AND THE OUTSTANDING PRINCIPAL
![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513045742140.png)
## THE PASS THROUGH SECURITY DISPLAYS NEGATIVE CONVEXITY
![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513045804185.png)
- Third,  consider now a Pass Through security with coupon rate $r_{PT} = 7$%.  
	- We can compute its value by backward computation,  remembering that at those nodes where there is exercise,  the investor gets all of the (remaining) principal back.
![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513045849640.png)

- The Pass Through security displays negative convexity
![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513045955147.png)

![500](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513050011188.png)
## COLLATERALIZED MORTGAGE OBLIGATIONS (CMOS)
- The idea is to redistribute the cash flows from a pool of mortgages in relation to their sensitivity to prepayment risk.
	- $\Rightarrow$ Varying levels of protection against prepayment risk,  suited for different types of investors.
- Characteristics:
	- High credit rating
	- Total value of bonds issued (CMOs) is less than value of collateral (Pool of mortgages) even under extreme prepayment scenario;
	- CMOs pay quarterly or semi-annual,  while mortgages pay monthly. Some reinvestment takes place.
## TWO MAIN TYPES OF CMOS (OR REMICS = REAL ESTATE MORTGAGE INVESTMENT CONDUIT):
##### 1. CMO SEQUENTIAL STRUCTURE
- In tranches: A,  B,  C plus a residual Z class.
- Cash Flows in tranches A,  B,  C receive:
	- (a) A Fixed Coupon Payment
	- (b) Sequentially,  prepayments on the principal.
- Class Z receives no cash flows,  but a coupon is accrued over time. Once all the other classes have been retired,  then prepayments go to Z.
- Each Tranche appeals to a certain types of investors:
	- Tranche A/B: Short-medium duration. Investors = money managers,  commercial banks;_
	- Tranche C: Longer duration. Investors = insurance companies,  pension funds;_
	- Tranche Z: Longest duration. Investors = insurance companies,  pension funds._
##### 2. CMO PLANNED AMORTIZATION CLASS (PAC)
- In Tranches: A,  B,  C and Companion.
	- Tranches A,  B etc receive prepayments according to a specified schedule,  related to some PSA level.
	- Companion absorbs the difference between the PSAs schedule and the actual prepayments.
- Tranches A,  B etc then have very stable (and known) cash flows ex ante.
- The companion tranche is instead very unstable.
## MONTE-CARLO SIMULATIONS
- Given a path dependent pre-payment function,  the valuation of a mortgage backed security is generally carried out by MC simulations.
- What do we simulate?
	1. Interest rates.
	2. Housing prices.
	3. Macro-economic factors.
- For each _risk-neutral_ simulation,  Cash Flows are computed $CF_{t}^{s}$,  which depend on path of various factors,  age of the mortgage etc.,  and we compute
$$P^{s}=\sum_{t=1}^{T}Z^{s}(0, t)CF_{t}^{s}$$
- where $Z^{s}(0,  t) = e^{-\sum_{i=0}^{t-1}r^{s}_{i}\Delta}$ is the zero-coupon bond in simulated path $s$.
- The price is then computed as
$$P={\frac{1}{N}}\sum_{s=1}^{N}P^{s}$$
- We simulate all the processes under the risk-neutral probabilities.
## OPTION ADJUSTED SPREAD
- Consider a given (pool of) mortgage,  and suppose that its quoted for $P_{M}(t)$ at time $t$.
- Since homeowners have a prepayment option,  it is not correct to compare the $P_{M}(t)$ just with the expected value of future payments $V(t)$.
	- We know that probably $V(t) > P_{M}(t)$
	- For example,  in the earlier tree example,  we had $V(0) = 10, 075.50$ while $P_{M}(0) = 10, 000$;
- Given a model for prepayment - either rational prepayment or one of the models discussed - a trader can calculate the value of the net present value of future mortgage payments,  net of the prepayment option.
- Call this model price $P(t,  r_{t})$,  which depends on the current interest rate $r_{t}$.
- The Option Adjusted Spread is that value _OAS_ such that $$P\left(t, r_{t}+OAS\right)=P_{M}\left(t\right)$$
- That is,  it is the spread on the interest rate that makes the model price (adjusted for the prepayment option) equal to market value.
- Notice that there are then two adjustments in $P(t,  r_{t})$: One for risk,  because we use the risk-neutral model,  and one for the option.
- The spread captures what is left,  if anything.
- In the previous example,  $OAS=0$,  as $V_{0}-CA_{0}=10, 000$.
- Suppose instead,  for the sake of argument,  that the mortgage rate $r^{m}=$.
- The same calculations yield $C=2716.0513$,  $V_{0}=9999.2757$ and $CA_{0}=52.0968$.
- Hence,  the risk-adjusted,  _option adjusted price_ is
$$V_{0}^{A}=V_{0}-CA_{0}=9947.1719$$
- If we think of the original loan = 10000 as the market value of the loan,  it would be overpriced.
- Thus,  $OAS=-0.004123$,  as we need to reduce the interest rate on the tree to ensure the market value equals the model-value.

## INTEREST ONLY AND PRINCIPAL ONLY STRIPS
- From the MBS markets,  a number of mortgage "derivatives" can be constructed to fit the needs of investors.  
- Strips: Obtained by dividing the cash flows from an underlying pool of mortgages through specific allocation of interest and principal.
    - The most famous strips are the Interest Only (IO) strips and the Principal Only (PO) strip.

##### INTEREST-ONLY (IO) STRIP:
- Receive all of the interest payment from the underlying collateral and none from the principal.
- The price movements of IO are highly sensitive to interest rate changes.
    - If $r_{t} \downarrow \Rightarrow$ prepayment $\uparrow \Rightarrow$ no more interest payments $\Rightarrow$ IO Strip loses value.
- Notice that most Fixed Income instruments tend to appreciate when $r_{t}$ declines.
- IO Strips are very different.

##### PRINCIPAL-ONLY (PO) STRIP: 
- PO Strips receive all of the principal payments from the underlying collateral and none from interest.
- The price movement of PO strips is also highly sensitive to interest rate movements
    - If $r_{t} \downarrow \Rightarrow$ prepayment $\uparrow \Rightarrow$ PO value tend to increase.

## SIMPLE EXAMPLE

- Consider a mortgage pool with 10 years to maturity and average mortgage rate of $r^{m}=6.5\%$.
- Suppose prepayments depend only on past interest rates and assume the following simple function for the probability that a homeowner would refinance its mortgage at time $t$:
    $$p_{t}=c\times\operatorname{max}{\big(}r_{m}-sp-r_{t}{\big)}$$
- This is a simple function of just the past interest rate: If interest rate drops below some spread below the mortgage rate,  the probability increases,  with sensitivity $c$.
    - In the industry,  much more complicated pre-payment functions are used.
        - In general,  $$p_{t}=f\left(r_{t}, r_{t-}, age_{t}, h_{t}, …, \right)$$
        - where $h_{t}$ denotes the housing price.
    - But the above simple function makes the point.

## SIMPLE EXAMPLE: MONTE CARLO SIMULATIONS

- Simulate a (risk-neutral) Ho-Lee model at the daily frequency ($\Delta=1/252$)
    $$r_{t+1}=r_{t}+\theta_{t}\Delta+\sigma\sqrt{\Delta}\varepsilon_{t+1}$$
- Compute monthly payments as
    $$CF_{t+21}=C_{t+21}+prepay_{t+21}$$
- where
    $$\begin{array}{rcl}
    C_{t+21} &=& C_{t}\left(1-p_{t}\right)\\
    prepay_{t+21} &=& p_{t}\times\text{principal}_{t}
    \end{array}$$
- The principal is adjusted for the principal payments over time
    $$\begin{array}{rcl}
    \text{Interest Paid}_{t} &=& \frac{r_{m}}{12}\times\text{principal}_{t}\\
    \text{Principal Paid}_{t} &=& C_{t}+prepay_{t}-\text{Interest Paid}_{t}\\
    \text{principal}_{t+21} &=& \text{principal}_{t}-\text{Principal Paid}_{t}
    \end{array}$$
- Then cash flows can be divided at leisure
- For example,  for $c=1.5$ and $sp=0.0484$,  we obtain:
![300](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513050323828.png)
- For c = 1.5 and sp = 0,  we obtain
![300](Z.%20Clippings/Teaching%20Note%206%20Mortgage%20Backed%20Securities-20240513050404018.png)

- In thislatter case,  we are assuming a quicker responsiveness of prepayments to changes in interest rates,  which increase the prepayment rate. This implies that the $MBS_{Prepay}$ would decline.

## SIMPLE EXAMPLE: OPTION ADJUSTED SPREAD

- Suppose that in the market,  the price of the $MBS_{Prepay}$ is quoted at 99.38.
- This implies that the OAS = 10 basis points. 
- In fact,  by increasing the discount rate by 10 basis points and re-simulating the CFs,  one obtains a price equal to the quoted price.
- A positive OAS shows that the market price of the security is too low,  calling for a strategy to buy it and contemporaneously hedge it using other traded securities with similar (non-linear) duration,  such as portfolios of caps and floors.