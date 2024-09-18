---
title: Teaching Note 1 Introduction To Fixed Income Securities
---

# Teaching Note 1 Introduction To Fixed Income Securities

# INTRODUCTION TO FIXED INCOME SECURITIES

   John Heaton
   The University of Chicago Booth School of Business
   NBER
	[[Fixed Income Lecture Notes]]
	[[Introduction to Fixed Income Asset Pricing]]
	[[Lecture Note 2Interest Rate Risk Management And Factors]]
	[[Teaching Note 3 Understanding The Term Structure Of Interest Rates]]
	[[Teaching Note 4 Interest Rate Derivatives]]
	[[Teaching Note 5 Risk Neutral Pricing]]
   [Teaching Note 6 Mortgage Backed Securities](Teaching%20Note%206%20Mortgage%20Backed%20Securities.md)
   [Teaching Note 7 A Rundown On Continuous Time Models](Teaching%20Note%207%20A%20Rundown%20On%20Continuous%20Time%20Models.md)

   [PSET I Fixed Income Asset Pricing](PSET%20I%20Fixed%20Income%20Asset%20Pricing.md)

## INTRODUCTION

   - Several changes to fixed-income markets took place in the aftermath of the crisis
   1. Many countries increased debt to "stimulate" the economy.
   	- Lower tax revenues due to the economic downturn and higher government spending
   	=⇒ large increase in government debt.
   2. The huge mortgage-backed securities market had several changes
   	- Fannie Mae and Freddie Mac went into conservatorship. Many mortgage companies disappeared. New regulation has been enacted.
   3. Aggressive monetary policy has had large impact on Treasury bonds
   - Federal Reserve slashed Fed Funds rate to zero
   - Federal Reserve moved to "unconventional monetary policy"
   4. Massive regulatory changes in derivative markets
   	- Central counterparties (CCP)
   	- Impact on pricing of derivatives.
   5. Dramatic change in behavior of Treasury bonds
   	- From positive beta to negative beta securities
   	- Negative rates in many

## THE OUTSTANDING AMOUNT U.S. DEBT

![](Introduction%20To%20Fixed%20Income%20Securities-20240331084127851.png)
   (Source: SIFMA and FRED at Federal Reserve of St. Louis.)

## FEDERAL FUNDS AND U.S. TREASURY YIELDS

![](Introduction%20To%20Fixed%20Income%20Securities-20240331084204167.png)

## THE NOTIONAL AMOUNT OF OVER-THE-COUNTER DERIVATIVES

   Panel A. Millions Of Us Dollars
![](Introduction%20To%20Fixed%20Income%20Securities-20240331084224576.png)
   (Data Source: OTC derivatives data are from the Bank for International Settlements, while global GDP data are from the World Bank.)

![](Introduction%20To%20Fixed%20Income%20Securities-20240331084249962.png)

## U.S. TREASURY BILLS, NOTES, AND BONDS

![](Introduction%20To%20Fixed%20Income%20Securities-20240331084310756.png)

   - U.S. Government Issues Various Kinds Of Debt Securities
   1. Treasury Bills: Zero coupon securities with maturity up to one year 2. Treasury Notes: Fixed coupon bonds with maturity up to 10 years 3. Treasury Bonds: Fixed coupon bonds with maturity of 30 years 4. Treasury Inflation-Protected Securities (TIPS): Floating coupon bonds indexed to inflation
   5. Floating Rate Notes (FRNs): Floating coupon bonds, with coupon indexed to T-Bill rates

## MARKETABLE U.S. TREASURY SECURITIES (MILLION OF DOLLARS) DECEMBER 31,2021

   | Debt Held                      | Intragovernmental   |
   |--------------------------------|---------------------|
   | by the Public                  | Holdings            |
   | Dollar                         | Percent Dollar      |
   | Bills                          | 3,767,964           |
   | Notes                          | 12,992,160          |
   | Bonds                          | 3,474,153           |
   | Inflation-Protected Securities | 1,727,968           |
   | Floating Rate Notes            | 603,302             |
   | Federal Financing Bank         | 0                   |
   | Total                          | 22,565,547          |

   Source: U.S. Treasury web site. https://www.treasurydirect.gov

## INTEREST RATES AND COMPOUNDING FREQUENCY

   - The concept of interest rates is ubiquitous to fixed income securities.
   - Problem: An interest rate is not well defined without a compounding frequency.
   - Example: A$100 investment at 10% interest rate over 10 years has payoffs:
   - $$\begin{aligned}
   

   \text{Annual compounding:} \$100\times{(1.1)}^{10} & =\$259.37 \\
   \text{Semi-annual compounding}:\quad\quad\$100\times\left(1.05\right)^{20}& =\$265.33 \\
   \text{Quarterly compounding}:\quad\text{\$}100\times{(1.025)}^{40}& =\$268.51 \\
   \text{Daily compounding: \$}100\times\left(1+\frac{0.1}{365}\right)^{10\times365}& =\$271.79 \\
   \text{Continuous compounding}:\quad\quad\text{\$}100\times e^{0.1\times10}& =\$271.82
   \end{aligned}$$

   - The general formula to compound n times over the horizon T is

   $$V=\left(1+\frac{r}{n}\right)^{n\times T}$$

   $\bullet$ For $n$ large, we converge to continuous compounding

   $$V=\left(1+\frac{r}{n}\right)^{n\times T}\longrightarrow e^{r\times T}$$

## DISCOUNTING

   - Discounting is opposite process from the previous one.
   - The question is: "what is the amount we have to invest today to have $1 dollar In the future, given a rate r compounded n times per year?"
   - Inverting the relation above, we obtain

   $$Z(T)=\frac{1}{\left(1+\frac{r}{n}\right)^{n\times T}}$$

   $\bullet$ In the limit as $n\rightarrow\infty$ we obtain the usual continuous compounding formula

   $$Z(T)=\frac{1}{\left(1+\frac{r}{n}\right)^{n\times T}}\longrightarrow Z(T)=e^{-rT}$$

## DISCOUNTS AND RATES

   - Note that the compounding frequency is mostly a convention.
   - The key question is:
   	- "How much are investors willing to pay today to have $1 at T".
   - Such price, Z (T), is always well defined.
   - Given Z (T), we can derive the rate rn for any given compounding frequency n:

   $$r_{n}=n\times\left(\frac{1}{Z(T)^{\frac{1}{nT}}}-1\right)$$

   - The continuously compounded rate is instead

   $$r=-\frac{1}{T}\log\left(Z(T)\right)$$

## THE TERM STRUCTURE OF INTEREST RATES

   - When we discount future cash flows to the present, different discount rates apply for different maturities.
   - We denote the discount factor at t for a dollar to be received at time T by

   $$Z(t,T)=e^{-r(t,T)(T-t)}$$

   - r (*t, T*) = continuously compounded yield at t for an investment up to T.
   	- We put two "time" indices:
   		1. $t$ = calendar time when the discounting is made (e.g. 1/31/2007, etc.)
   		2. $T$ = maturity date.
   	1. =⇒ $T − t$ = time to maturity

   - Panel A of next figure shows $Z (t, T)$ for $t = 1/31/2007, 1/31/2008, …, 3/20/2020$, and for $T − t$ ranging from 0 to 30 yecasc
   - Panel B of next figure shows the corresponding yields r (*t, T*)
![|500](Introduction%20To%20Fixed%20Income%20Securities-20240331084530427.png)

   ![](Introduction%20To%20Fixed%20Income%20Securities-20240331084555484.png)

## YIELD CURVES

   - Yield curves change a lot over time. - They also have many shapes:
   - Flat (e.g. 1/31/2007)
   - Increasing (e.g. 1/30/2015) - Hump (e.g. 1/31/2009) - Inverted hump (slightly, 1/31/2007)
   - What generates the shape of the term structure of interest rates?
   - What does it imply for derivative pricing etc?
   - Indeed, there is much variation not only in level but in slope of the yield curve
   - What do these variations tell us about investors' beliefs about future rates? - What do they tell us about risk premia required to hold bonds?
   (Data: Yields up to 5 years are from CRSP. Yields from 10 to 30 are from G¨urkaynak, Sack, and Wright (2007), updated series.)

## COUPON BONDS

   - What is the price of coupon bond?
   - A coupon bond is just a sequence of cash payments c/2 (coupons) for dates
   T 1, T 2*, …, T*n and one big payment of 100 + c/2 (principal) at Tn (= maturity of
   The bond).
   - If we know the time value of money for each maturity, that is, the discount function
   Z (*t, T*i) for all maturities Ti's, a simple no arbitrage argument implies

   $$P(t,T_{n})=c/2\times Z(t,T_{1})+c/2\times Z(t,T_{2})+…+(100+c/2)\,Z\,(t,T_{n})$$

    $$=\sum\limits_{i=1}^{n}\frac{c/2}{\left(1+r_{2}\left(t,T_{i}\right)/2\right)^{2\times\left(T_{i}-t\right)}}+\frac{100}{\left(1+r_{2}\left(t,T_{n}\right)/2\right)^{2\times\left(T_{n}-t\right)}}$$

   - What is the arbitrage argument?

## COUPON BONDS

   - Suppose that the price of the bond is trading at par (100) but the right-hand side is 105.
   - Then an arbitrageur can buy the bond (pay 100) and sell the strips (each cash payments) for a total of 105, thereby making $5 (million). Since there is perfect matching of cash flows in the future, the trade is an arbitrage.
   - Incidentally, notice that if t = 0 and Ti are exact semi-annual maturities, that is T 1 =, T 2 = 1, T 3 = 1.5 etc., then we have 2 × Ti = i for every i = 1*,.., n*,
   And thus the formula reduces to

   $$P(0,T_{n})=\sum_{i=1}^{n}\frac{c/2}{\left(1+r_{2}\left(0,T_{i}\right)/2\right)^{i}}+\frac{100}{\left(1+r_{2}\left(0,T_{n}\right)/2\right)^{n}}$$

## CONVENTIONS AND TERMINOLOGY

   - It is important to spend a few words on some market conventions and terminology.

## - ACCRUED INTEREST

   - The market prices of bonds quoted in newspapers are **clean prices**. That is,
   They are quoted without any accrued interest.
   - The accrued interest is the amount of interest that has built up since the last
   Coupon payment.
   - The actual payment is called invoice price (or **dirty price**).

## DAY COUNT CONVENTIONS - HOW DO WE COUNT DAYS? THREE MAIN WAYS

   1. Actual/Actual: Simply Count the number of calendar days; 2. 30/360: Assume there are 30 days in a month and 360 in a year; 3. Actual/360: Each month has the right number of days, but there are only 360
   Days in a year.
   - Which convention it is used depend on the security considered. - Treasuries use Actual/Actual.

## DISCOUNT YIELD AND BOND EQUIVALENT YIELD

   - T-bills are quoted on a discount yield d basis. That is, the quote reports a *yield*.
   - If n is the number of days to maturity, the price of the T-bill is

   $$P=100\times\left[1-\frac{n}{360}\times d\right]$$

   $\bullet$ In other words

   $$d=\frac{100-P}{100}\times\frac{360}{n}$$

   $\bullet$ Instead, it should be

   $$BEY=\frac{100-P}{P}\times\frac{365}{n}$$

   $\bullet$ BEY = Bond Equivalent Yield

   - Of course, we obtain

   $$B E Y={\frac{365\times d}{360-d\times n}}$$

## YIELD-TO-MATURITY (OR INTERNAL RATE OF RETURN)

   - Given price $P\left(t,T\right)$ and cash flows $c/2$ at $T_{i}$ 's for $i=1,..,n$, and $1+c/2$ at $T_{n}$, the (semi-annually compounded) yield-to-maturity YTM is defined as that rate $y$ such that $$P\left(t,T_{n}\right)=\sum\limits_{i=1}^{n}\frac{c/2}{\left(1+\frac{n}{2}\right)^{2\times\left(T_{i}-t\right)}}+\frac{100}{\left(1+\frac{n}{2}\right)^{2\times\left(T_{n}-t\right)}}$$

    (1)

   - Recall that given the spot curve r 2 (*t, T*i), we also had

   $$P\left(t,T_{n}\right)=\sum\limits_{i=1}^{n}{\frac{c/2}{\left(1+r_{2}\left(t,T_{i}\right)/2\right)^{2\times\left(T_{i}-t\right)}}}+{\frac{100}{\left(1+r_{2}\left(t,T_{n}\right)/2\right)^{2\times\left(T_{n}-t\right)}}}$$

   - What's the difference?
   - The yield to maturity y is a sort of average discount rate that characterizes
   One *particular bond*, and it is used to discount the cash flows of *that* particular bond.
   - Notice that two different bonds with same maturity, will have different yield
   To maturities if they have different coupons.

## YIELD-TO-MATURITY

   - We will almost never use YTM - It is blatantly wrong as a measure of yield, as it assumes that all the coupons can
   Be reinvested at the constant y throughout the life of the bond.
   - That is: not only it assumes a flat yield curve, but also one that does not move
   Over time.
   - Example: consider the following data:

   |    |    | Bond Maturity (Years) Coupon   |   Price | Yield-to-Maturity   |
   |----|----|--------------------------------|---------|---------------------|
   |  1 |  2 | 9%                             |   98.57 | 9.82%               |
   |  2 |  2 | 10%                            |  100.34 | 9.80%               |
   |  3 |  2 | 3%                             |   88    | 9.91%               |

   - What is the most attractive bond?

## YIELD-TO-MATURITY

   - Judging from the Yield-to-Maturity, bond 3 looks great. - However, it is dominated by a combination of 1 and 2, as we can mimic exactly
   Its cash flows and find a (slightly) lower price.
   - Let N 1 and N 2, be the number of the first and the second coupon bonds
   - Then

   $$\begin{array}{c}{{N_{1}\times9+N_{2}\times10\;=\;3}}\\ {{N_{1}\times109+N_{2}\times110\;=\;103}}\end{array}$$

   - Solving the system =⇒ the portfolio long N 1 = 7 units in bond 1 and short of
   N 2 = −6 units bond 2 mimics exactly the cash flows of bond 3.
   - The value of this portfolio is N 1 × 98.57 + N 2 × 100.34 = 87.95 < 88.
   - The YTM of the portfolio is even bigger: YTM=9.94%.
   - Why is this happening?
   - The YTM measures the average return on the bond under the assumption that
   all coupons are reinvested at the same rate y.
   - With a non-flat term structure, this is simply not going to happen and using YTM
   For relative pricing yields bad results.
   - The low coupon in bond 3 together with the fact that we cannot re-invest at the
   High rate of 9.91% for the whole life of the bond yields the implication that the third bond is "no better" than a portfolio of the other two (which have lower YTMs).

## FLOATING RATE NOTES

   - Floating rate notes are securities whose coupon is not fixed, but it depends on
   Realized short-term rates rt.
   - If rt increases =⇒ coupon increases. And vice versa.
   - The U.S. Treasury started issuing floating rate notes (FRN) in January 2014. - They pay quarterly coupons using the 13-week U.S. T-bill rate as a reference rate,
   Plus a spread determined at the auction of the FRN.
   - Let T 1, T 2, …, Tn denote the coupon payment dates, with Ti+1 = Ti + 0.25.
   - Then the (annualized) coupon rate at time Ti is given by

   $$c(T_{i})=r(T_{i-1})+\mathrm{spread}$$

   - Where r (Ti−1) is the quarterly compounded, (annualized) three-month rate.

## FLOATING RATE NOTES: PRICING

   - How do we price a security with unknown future coupons?
   - We can use a recursive argument. Let's start with a spread = 0
   - Let Tn = maturity date, where n is the total number of coupon payments.
   - Suppose that today is actually Tn−1.
   - =⇒ Today we know the reference rate r (Tn−1) and hence

   Cash flow at Tn = 1 + 1 4 c (Tn) = 1 + 1 4 r (Tn−1)

   - The value of FRN at Tn−1 is

   $$P^{F R N}(T_{n-1})\;=\;\frac{\mathsf{C a s h\;f l o w\;a t\;}T_{n}}{1+\frac{1}{4}r(T_{n-1})}=\frac{1+\frac{1}{4}c(T_{n})}{1+\frac{1}{4}r(T_{n-1})}=\frac{1+\frac{1}{4}r(T_{n-1})}{1+\frac{1}{4}r(T_{n-1})}=1$$

   - Consider now the value of the FRN at Tn−2.
   - At this time, the investor knows that the FRN will c (Tn−1) = r (Tn−2) at Tn−1,
   And that its price will revert to P FRN (Tn−1) = 1.

   - The FRN value at $T_{n-2}$ is then $$P^{FRN}(T_{n-2})\,=\,\frac{P^{FRN}(T_{n-1})+\frac{1}{4}c(T_{n-1})}{1+\frac{1}{4}r(T_{n-2})}=\frac{1+\frac{1}{4}r(T_{n-2})}{1+\frac{1}{4}r(T_{n-2})}=1$$
   - Using the same logic for every reset time Ti: =⇒ P FRN (Ti) = 1
   - Outside reset times, the price of FRN is different from 1.
   - Let t be such that Ti−1 *< t < T*i. Then, the value at t of FRN is

   $$P^{F R N}(t)\;=\;Z(t,T_{i})(1+r(T_{i-1})/4)$$

   - Adding a spread to the coupon payments is simple because the spread is constant.

   =⇒ use discounts Z (*t, T*) to compute its value.

## REPURCHASE AGREEMENTS

   - **Repurchase Agreements (Repo)**: Agreement to sell some securities to another party and buy them back at a fixed date and for a fixed amount.
   - The price at which the security is bought back is greater than the selling price
   And the difference implies an interest rate called *Repo Rate*.
   - A **Reverse Repo** is the borrowing of a security for a short period at an agreed
   Interest rate.
   - The Repo Market is the single most important source of financing for government
   Dealers.
   - Since government securities are liquid and default free, they are excellent collateral.
   - Dealers can borrow money on a collateralized basis, so that they can take huge
   Positions even with limited capital.
   - The Repo Market grew very large. Next table shows the average *daily* amount
   Outstanding
![](Introduction%20To%20Fixed%20Income%20Securities-20240331091908885.png)
## FINANCING BY U.S. GOVERNMENT SECURITIES DEALERS AVERAGE DAILY AMOUNT OUTSTANDING ($ BILLIONS)

   (Source: SIFMA http://www.sifma.org/research/statistics.aspx)

## BILATERAL REPURCHASE AGREEMENTS

   - A Repo transaction is as follows: Consider a trader and a repo-dealer. The trader
   At time t wants to take a long position until time T (typically, overnight!)

![](Z.%20Clippings/Lecture%20Note%201%20Introduction%20To%20Fixed%20Income%20Securities-20240415223856802.png)

   Pay (Pt− haircut)× (1+repo rate × n

## REPURCHASE AGREEMENTS

   1. At time t, the trader buys the bond at market price $P_t$ and enters into a Repo with the Repo Dealer. Hence, the trader delivers the bond as collateral to the repo-dealer and gets the cash to purchase the bond.
   	- The Repo Dealer typically gives something less than the market price of the bond. The difference is called **hair cut**.
   	- The term T is decided at time t: Most Repurchase agreements are for a very short term (overnight). Some longer term agreements reach 30 days or more.
   	- The Repo rate is decided at time t.
   1. At time T, the trader gets back the bond from the Repo Dealer, sells the bond
   In the market to get PT and pays Pt plus the repo rate to the dealer.
   - The profit is then PT − Pt−repo rate× n
   360 × (Pt − haircut).

   - Hence, the return on capital to the trader is

   $\text{Return}=\dfrac{P_{T}-P_{t}-\text{repo rate}\times\frac{n}{360}\times(P_{t}-\text{haircut})}{\text{haircut}}$

## REPURCHASE AGREEMENTS

   - Between t and T the trader earns the accrued interest on the bond
   - Positive Carry: If accrued interest > repo rate - Negative Carry: If accrued interest < repo rate.
   - Other important definitions/characteristics of Repo markets:
   1. **General Collateral Rate (GCF)**: This is the Repo Rate on most Treasury
   Securities.
   Hence, using one or another of these as collateral makes little
   Difference in terms of costs.
   2. - In a reverse repo, the trader (A) borrows the security from the repo dealer;
   (B) sells it; and (C) posts cash collateral with the dealer.
   - The trader is lending money to the dealer against the bond collateral =⇒
   The trader would be entitled to the repo rate.
   - However, the trader is happy to forgo part (all) of the repo rate in order to
   Get hold of the bond (to sell)

## REVERSE REPO TRANSACTION

   ![](Z.%20Clippings/Lecture%20Note%201%20Introduction%20To%20Fixed%20Income%20Securities-20240415224136376.png)

## TRI-PARTY REPO

   - Based on clearing and settlement infrastructure supported by Bank of New York
   Mellon and JPMorgan Chase
   - Banks provide collateral valuation, margining, and management services to facilitate trading.
   - Collateral allocation: automatically selects securities from cash borrower's inventory.
   - General Collateral Finance (GCF): cleared through the Fixed Income Clearing
   Corporation (FICC) GCF repo service. Mostly inter-dealer.
   - Ex-GCF: Not cleared through FICC. Institutional investors such as money market
   Funds lending to broker-dealers.
   - A forward rate determined at time t is the rate implicit in the current spot rate
   Function for an investment in T-bills made at date T 1 with maturity date T 2
   (> T 1).
   - There are three "dates" in the forward rate:
   1. Today (t);
   2. The first maturity at which the investment is made (T 1);
   3. The final maturity of the investment (T 2)
   - With semiannual compounding, we denote it f 2 (t, T 1, T 2)
   - With continuous compounding, we denote it f (t, T 1, T 2)
   - How do we determine the forward rates?
   	- By no arbitrage.
   - Suppose today is t = 0 and that I have $10 million to invest for 1 year.
   - We have the following two strategies
   1. Invest in a 1-year zero coupon bond, obtaining at maturity

   $$\$10\mathrm{~million}\times\left(1+r_{2}\left(0,1\right)/2\right)^{2}$$

   2. 2.Invest in a 6-months zero coupon bond and enter (today) into a forward contract to invest the proceeds at $T_1=0.5$ until $T_2=1$ for a rate $f_2\left(0,0.5,1\right)$. At maturity we have

   $$10 m × $(1+r_2\left(0,0.5\right)/2)\times\left(1+\frac{f_2\left(0,0.5,1\right)}{2}\right)$$

   - By no arbitrage (and if credit risk is negligible) we must have

   $$\$10\ \textsf{m}\times\left(1+{\frac{r_{2}\left(0,1\right)}{2}}\right)^{2}=\$10\ \textsf{m}\times\left(1+{\frac{r_{2}\left(0,0.5\right)}{2}}\right)\times\left(1+{\frac{f_{2}\left(0,0.5,1\right)}{2}}\right)$$

   - Or

   $$1+{\frac{f_{2}\left(0,0.5,1\right)}{2}}={\frac{\left(1+r_{2}\left(0,1\right)/2\right)^{2}}{\left(1+r_{2}\left(0,0.5\right)/2\right)}}$$

   - By using the price of bonds we have

   $$1+\frac{f_{2}\left(0,0.5,1\right)}{2}=\frac{Z(0,0.5)}{Z(0,1)}$$

   - More generally, for every T 1 and T 2, consider the following strategies:
   1. Invest in a $T_{2}-$ zero coupon bond, obtaining at maturity

   $$\frac{\$10\text{m}}{ Z (0, T _ 2)}$$

   2. Invest in a 6-months zero coupon bond and enter (today) into a forward contract to invest the proceeds at $T_1=0.5$ until $T_2=1$ for a rate $f_2\left(0,0.5,1\right)$. At maturity we have

   $$\frac{\$10\ m}{Z(0,T_{1})}\times\left(1+\frac{f_{n}\left(0,T_{1},T_{2}\right)}{n}\right)^{n(T_{2}-T_{1})}$$

   - We then obtain

   $$\left(1+\frac{f_{n}\left(0,T_{1},T_{2}\right)}{n}\right)^{n(T_{2}-T_{1})}=\frac{Z(0,T_{1})}{Z(0,T_{2})}$$

## CONTINUOUSLY COMPOUNDED FORWARD RATES

   - Taking the limit as $n\rightarrow\infty$ the continuously compounded forward rates is $$f(0,T_{1},T_{2})\ =\ \frac{\ln(Z(0,T_{1}))-\ln(Z(0,T_{2}))}{T_{2}-T_{1}}$$

    $$=\ \frac{r(0,T_{2})T_{2}-r(0,T_{1})T_{1}}{T_{2}-T_{1}}\tag{2}$$

   - Another concept, that we will use later, is that of instantaneous forward rate.
   - We can rewrite (2) as (exercise: do it!)

   $$f(0,T_{1},T_{2})=r(0,T_{1})+T_{2}\times\frac{r(0,T_{2})-r(0,T_{1})}{T_{2}-T_{1}}\tag{3}$$

   - If we take the limit $T_{2}\longrightarrow T_{1}$ (that is, the horizon of the forward contract shrinks to zero) we obtain

   $$f(0,T_{1},T_{1})=r(0,T_{1})+T_{1}\times\frac{dr(0,T_{1})}{dT_{1}}\tag{4}$$

## THE RELATION BETWEEN FORWARD CURVE AND SPOT CURVE

   - The equation for the instantaneous forward curve (4) is revealing of an interesting (important) property of the forward-spot relationship.
   - We can rewrite

   $$f(0,T_{1},T_{1})-r(0,T_{1})=T_{1}\times\frac{dr(0,T_{1})}{dT_{1}}$$

   - This implies:

   $$\begin{gathered}
   \text{If }\quad\frac{dr(0,T_1)}{dT_1}>0 \Longrightarrow\text{ forward curve is above the spot curve} \\
   \text{If }\quad\frac{dr(0,T_1)}{dT_1}<0 \Longrightarrow\text{ forward curve is below the spot curve} \\
   \begin{aligned}\mathsf{If}\quad\frac{dr(0,T_1)}{dT_1}=0\end{aligned} \Longrightarrow\text{ forward curve intersects the spot curve}
   \end{gathered}$$
   - To obtain the forward curve we need a smooth yield curve.
   ![](Introduction%20To%20Fixed%20Income%20Securities-20240331091950722.png)
   ## ESTIMATING THE ZERO-COUPON DISCOUNT FUNCTION
   - There are several methods to extract the zero-coupon discount curve $Z (0, T)$ from bond data.
   - Why do we want to do that?
   1. The discount function Z (0, T) determines the time value of money. We need it as a basis to discount future (riskless) cash flows.
   2. We cannot observe it: it is implicitly embedded in traded Treasury coupon bonds.
   3. You need it to compute forward prices, for instance, as well as Swaps (see later).
   4. It will be the basis of all future term structure models: it is typically the first step to then calibrate term structure models. The latter are what traders use to
   	- (a) Price new securities by no arbitrage (we will see many).
   	- (b) Spot out arbitrage opportunities.
   		- The most "famous" is the bootstrapping methodology.
   
   ## BOOTSTRAP
   
   - Suppose we have n coupon bonds. Each bond i has a coupon equal to $c_i$.
   - Recall the pricing equation for coupon bonds with maturity $T_i$ is equal to
   $$P^{i}(t, T_{i})=\frac{c^{i}}{2}\sum\limits_{j=1}^{i}Z (t, T_{j})+1\times Z (t, T_{i})\tag{5}$$
   - Today is t = 0 and that we have data on maturities $T_j = 0.5, 1, 1.5*, …. T_n$.
   - Inverting (5), we obtain
   $$Z\left (0,0.5\right)\;=\;\frac{P^{1}\left (0,0.5\right)}{1+c^{1}/2}$$
   
   $$Z\left (0,1\right)\;=\;\frac{P^{2}\left (0,1\right)-c^{2}/2\times Z\left (0,. 5\right)}{1+c^{2}/2}$$
   
   $$Z\left (0,1.5\right)\;=\;\frac{P^{3}\left (0,1.5\right)-c^{3}/2\times\left (Z\left (0,. 5\right)+Z\left (0,1\right)\right)}{1+c^{3}/2}$$
   - In general, for every i:
   $$Z\left (0, T_{i}\right)=\frac{P^{i}\left (0, T_{i}\right)-c^{i}/2\times\left (\Sigma_{j=1}^{i-1}\, Z\left (0, T_{j}\right)\right)}{1+c^{i}/2}$$
   - Example: suppose we have the following data:
   $$\begin{array}{ccccc}
   \hline \text { Maturity } & \text { Period } i & \text { Coupon } & \text { YTM } & \text { Price } \\
   \hline 0.5 & 1 & 0.000 & 0.080 & 96.15 \\
   1 & 2 & 0.000 & 0.083 & 92.19 \\
   1.5 & 3 & 0.085 & 0.089 & 99.45 \\
   2 & 4 & 0.090 & 0.092 & 99.64 \\
   2.5 & 5 & 0.110 & 0.094 & 103.49 \\
   3 & 6 & 0.095 & 0.097 & 99.49 \\
   3.5 & 7 & 0.100 & 0.100 & 100.00 \\
   \hline
   \end{array}$$
   
   - We find:
   $$\begin{array}{l l} {{Z\left(0,\right)\;=\;96.15;\qquad Z\left(0,1\right)=92.19;}} \\ {{}} \\ {{Z\left(0,1.5\right)\;=\;\frac{99.45-\times\left(96.15+92.19\right)}{1.0425}=87.72;\ldots.}} \end{array}$$
   
   - Since
   
   $$Z\left (0, T_{i}\right)=\frac{100}{\left (1+\frac{r_{2}\left (0, T_{i}\right)}{2}\right)^{i}}\Longleftrightarrow r_{2}\left (0, T_{i}\right)=2\times\left (\left (\frac{100}{Z\left (0, T_{i}\right)}\right)^{\frac{1}{i}}-1\right)$$
   
   We Obtain
   $$

   \begin{array}{cccc}
   \hline \text { Maturity } & \text { Period } i & \text { YTM } & \text { Spot Yield } \\
   \hline 0.5 & 1 & 0.080 & 0.080 \\
   1 & 2 & 0.083 & 0.083 \\
   1.5 & 3 & 0.089 & 0.0893 \\
   2 & 4 & 0.092 & 0.09247 \\
   2.5 & 5 & 0.094 & 0.09468 \\
   3 & 6 & 0.097 & 0.09787 \\
   3.5 & 7 & 0.100 & 0.10129 \\
   \hline
   \end{array}

   $$
   ## CURVE FITTING
   
   - The above methodologies require that we have all the maturities available. 
   - Unfortunately, this is never the case. 
   - To avoid this problem, the profession moved to "curve fitting" in the following sense:
   1. Assume a flexible functional form for Z (0, T), such as (Nelson Siegel Model):
   $$Z\left (0, T_{j}\right)\;=\; 100\times e^{-r\left (0, T_{j}\right)\times T_{j}}$$
   
   $$r (0, T_{j})\;=\;\theta_{0}+(\theta_{1}+\theta_{2})\,\frac{1-e^{-\frac{T_{j}}{\lambda}}}{\frac{T_{j}}{\lambda}}-\theta_{2}e^{-\frac{T_{j}}{\lambda}}$$
   2. We can compute the "theoretical price" given Z (0, T)
   $$\widehat{P}\left (0, T_{j}\right)=\sum\limits_{i=1}^{j}c\left (T_{i}\right)\times Z\left (0, T_{i}\right)$$
   3. We estimate the parameters θ0, θ1, θ2, λ by **non-linear least squares**.
   That is, by minimizing
   $$\operatorname*{min}_{\theta_{0},\theta_{1},\theta_{2},\lambda}\sum_{j=1}^{n}\left (P\left (0, T_{j}\right)-\widehat{P}\left (0, T_{j}\right)\right)^{2}$$
   - There is a large literature on the [Functional Forms](Lecture%2010-%20Functional%20Forms.md) for the discount function
   Z (0, T), many of them relying on spline functions.
   - Next figure shows the difference between using bootstrapping technique and the
   Curve fitting technique
   
   ## ZERO-COUPON YIELD CURVES
![](Teaching%20Note%201%20Introduction%20To%20Fixed%20Income%20Securities-1.octet-stream)
   ![](Introduction%20To%20Fixed%20Income%20Securities-20240331152353486.png)
   
   - Clearly, the fitted curve is much smoother (by construction).
   - An important difference arises when we look at forward rates
```embed
title: "Fetching"
image: "data:image/svg+xml;base64,PHN2ZyBjbGFzcz0ibGRzLW1pY3Jvc29mdCIgd2lkdGg9IjgwcHgiICBoZWlnaHQ9IjgwcHgiICB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxMDAgMTAwIiBwcmVzZXJ2ZUFzcGVjdFJhdGlvPSJ4TWlkWU1pZCI+PGcgdHJhbnNmb3JtPSJyb3RhdGUoMCkiPjxjaXJjbGUgY3g9IjgxLjczNDEzMzYxMTY0OTQxIiBjeT0iNzQuMzUwNDU3MTYwMzQ4ODIiIGZpbGw9IiNlMTViNjQiIHI9IjUiIHRyYW5zZm9ybT0icm90YXRlKDM0MC4wMDEgNDkuOTk5OSA1MCkiPgogIDxhbmltYXRlVHJhbnNmb3JtIGF0dHJpYnV0ZU5hbWU9InRyYW5zZm9ybSIgdHlwZT0icm90YXRlIiBjYWxjTW9kZT0ic3BsaW5lIiB2YWx1ZXM9IjAgNTAgNTA7MzYwIDUwIDUwIiB0aW1lcz0iMDsxIiBrZXlTcGxpbmVzPSIwLjUgMCAwLjUgMSIgcmVwZWF0Q291bnQ9ImluZGVmaW5pdGUiIGR1cj0iMS41cyIgYmVnaW49IjBzIj48L2FuaW1hdGVUcmFuc2Zvcm0+CjwvY2lyY2xlPjxjaXJjbGUgY3g9Ijc0LjM1MDQ1NzE2MDM0ODgyIiBjeT0iODEuNzM0MTMzNjExNjQ5NDEiIGZpbGw9IiNmNDdlNjAiIHI9IjUiIHRyYW5zZm9ybT0icm90YXRlKDM0OC4zNTIgNTAuMDAwMSA1MC4wMDAxKSI+CiAgPGFuaW1hdGVUcmFuc2Zvcm0gYXR0cmlidXRlTmFtZT0idHJhbnNmb3JtIiB0eXBlPSJyb3RhdGUiIGNhbGNNb2RlPSJzcGxpbmUiIHZhbHVlcz0iMCA1MCA1MDszNjAgNTAgNTAiIHRpbWVzPSIwOzEiIGtleVNwbGluZXM9IjAuNSAwIDAuNSAxIiByZXBlYXRDb3VudD0iaW5kZWZpbml0ZSIgZHVyPSIxLjVzIiBiZWdpbj0iLTAuMDYyNXMiPjwvYW5pbWF0ZVRyYW5zZm9ybT4KPC9jaXJjbGU+PGNpcmNsZSBjeD0iNjUuMzA3MzM3Mjk0NjAzNiIgY3k9Ijg2Ljk1NTE4MTMwMDQ1MTQ3IiBmaWxsPSIjZjhiMjZhIiByPSI1IiB0cmFuc2Zvcm09InJvdGF0ZSgzNTQuMjM2IDUwIDUwKSI+CiAgPGFuaW1hdGVUcmFuc2Zvcm0gYXR0cmlidXRlTmFtZT0idHJhbnNmb3JtIiB0eXBlPSJyb3RhdGUiIGNhbGNNb2RlPSJzcGxpbmUiIHZhbHVlcz0iMCA1MCA1MDszNjAgNTAgNTAiIHRpbWVzPSIwOzEiIGtleVNwbGluZXM9IjAuNSAwIDAuNSAxIiByZXBlYXRDb3VudD0iaW5kZWZpbml0ZSIgZHVyPSIxLjVzIiBiZWdpbj0iLTAuMTI1cyI+PC9hbmltYXRlVHJhbnNmb3JtPgo8L2NpcmNsZT48Y2lyY2xlIGN4PSI1NS4yMjEwNDc2ODg4MDIwNyIgY3k9Ijg5LjY1Nzc5NDQ1NDk1MjQxIiBmaWxsPSIjYWJiZDgxIiByPSI1IiB0cmFuc2Zvcm09InJvdGF0ZSgzNTcuOTU4IDUwLjAwMDIgNTAuMDAwMikiPgogIDxhbmltYXRlVHJhbnNmb3JtIGF0dHJpYnV0ZU5hbWU9InRyYW5zZm9ybSIgdHlwZT0icm90YXRlIiBjYWxjTW9kZT0ic3BsaW5lIiB2YWx1ZXM9IjAgNTAgNTA7MzYwIDUwIDUwIiB0aW1lcz0iMDsxIiBrZXlTcGxpbmVzPSIwLjUgMCAwLjUgMSIgcmVwZWF0Q291bnQ9ImluZGVmaW5pdGUiIGR1cj0iMS41cyIgYmVnaW49Ii0wLjE4NzVzIj48L2FuaW1hdGVUcmFuc2Zvcm0+CjwvY2lyY2xlPjxjaXJjbGUgY3g9IjQ0Ljc3ODk1MjMxMTE5NzkzIiBjeT0iODkuNjU3Nzk0NDU0OTUyNDEiIGZpbGw9IiM4NDliODciIHI9IjUiIHRyYW5zZm9ybT0icm90YXRlKDM1OS43NiA1MC4wMDY0IDUwLjAwNjQpIj4KICA8YW5pbWF0ZVRyYW5zZm9ybSBhdHRyaWJ1dGVOYW1lPSJ0cmFuc2Zvcm0iIHR5cGU9InJvdGF0ZSIgY2FsY01vZGU9InNwbGluZSIgdmFsdWVzPSIwIDUwIDUwOzM2MCA1MCA1MCIgdGltZXM9IjA7MSIga2V5U3BsaW5lcz0iMC41IDAgMC41IDEiIHJlcGVhdENvdW50PSJpbmRlZmluaXRlIiBkdXI9IjEuNXMiIGJlZ2luPSItMC4yNXMiPjwvYW5pbWF0ZVRyYW5zZm9ybT4KPC9jaXJjbGU+PGNpcmNsZSBjeD0iMzQuNjkyNjYyNzA1Mzk2NDE1IiBjeT0iODYuOTU1MTgxMzAwNDUxNDciIGZpbGw9IiNlMTViNjQiIHI9IjUiIHRyYW5zZm9ybT0icm90YXRlKDAuMTgzNTUyIDUwIDUwKSI+CiAgPGFuaW1hdGVUcmFuc2Zvcm0gYXR0cmlidXRlTmFtZT0idHJhbnNmb3JtIiB0eXBlPSJyb3RhdGUiIGNhbGNNb2RlPSJzcGxpbmUiIHZhbHVlcz0iMCA1MCA1MDszNjAgNTAgNTAiIHRpbWVzPSIwOzEiIGtleVNwbGluZXM9IjAuNSAwIDAuNSAxIiByZXBlYXRDb3VudD0iaW5kZWZpbml0ZSIgZHVyPSIxLjVzIiBiZWdpbj0iLTAuMzEyNXMiPjwvYW5pbWF0ZVRyYW5zZm9ybT4KPC9jaXJjbGU+PGNpcmNsZSBjeD0iMjUuNjQ5NTQyODM5NjUxMTc2IiBjeT0iODEuNzM0MTMzNjExNjQ5NDEiIGZpbGw9IiNmNDdlNjAiIHI9IjUiIHRyYW5zZm9ybT0icm90YXRlKDEuODY0NTcgNTAgNTApIj4KICA8YW5pbWF0ZVRyYW5zZm9ybSBhdHRyaWJ1dGVOYW1lPSJ0cmFuc2Zvcm0iIHR5cGU9InJvdGF0ZSIgY2FsY01vZGU9InNwbGluZSIgdmFsdWVzPSIwIDUwIDUwOzM2MCA1MCA1MCIgdGltZXM9IjA7MSIga2V5U3BsaW5lcz0iMC41IDAgMC41IDEiIHJlcGVhdENvdW50PSJpbmRlZmluaXRlIiBkdXI9IjEuNXMiIGJlZ2luPSItMC4zNzVzIj48L2FuaW1hdGVUcmFuc2Zvcm0+CjwvY2lyY2xlPjxjaXJjbGUgY3g9IjE4LjI2NTg2NjM4ODM1MDYiIGN5PSI3NC4zNTA0NTcxNjAzNDg4NCIgZmlsbD0iI2Y4YjI2YSIgcj0iNSIgdHJhbnNmb3JtPSJyb3RhdGUoNS40NTEyNiA1MCA1MCkiPgogIDxhbmltYXRlVHJhbnNmb3JtIGF0dHJpYnV0ZU5hbWU9InRyYW5zZm9ybSIgdHlwZT0icm90YXRlIiBjYWxjTW9kZT0ic3BsaW5lIiB2YWx1ZXM9IjAgNTAgNTA7MzYwIDUwIDUwIiB0aW1lcz0iMDsxIiBrZXlTcGxpbmVzPSIwLjUgMCAwLjUgMSIgcmVwZWF0Q291bnQ9ImluZGVmaW5pdGUiIGR1cj0iMS41cyIgYmVnaW49Ii0wLjQzNzVzIj48L2FuaW1hdGVUcmFuc2Zvcm0+CjwvY2lyY2xlPjxhbmltYXRlVHJhbnNmb3JtIGF0dHJpYnV0ZU5hbWU9InRyYW5zZm9ybSIgdHlwZT0icm90YXRlIiBjYWxjTW9kZT0ic3BsaW5lIiB2YWx1ZXM9IjAgNTAgNTA7MCA1MCA1MCIgdGltZXM9IjA7MSIga2V5U3BsaW5lcz0iMC41IDAgMC41IDEiIHJlcGVhdENvdW50PSJpbmRlZmluaXRlIiBkdXI9IjEuNXMiPjwvYW5pbWF0ZVRyYW5zZm9ybT48L2c+PC9zdmc+"
description: "Fetching 
# Teaching Note 1 Introduction To Fixed Income Securities

# INTRODUCTION TO FIXED INCOME SECURITIES

   John Heaton
   The University of Chicago Booth School of Business
   NBER
	[[Fixed Income Lecture Notes]]
	[[Introduction to Fixed Income Asset Pricing]]
	[[Lecture Note 2Interest Rate Risk Management And Factors]]
	[[Teaching Note 3 Understanding The Term Structure Of Interest Rates]]
	[[Teaching Note 4 Interest Rate Derivatives]]
	[[Teaching Note 5 Risk Neutral Pricing]]
   [Teaching Note 6 Mortgage Backed Securities](Teaching%20Note%206%20Mortgage%20Backed%20Securities.md)
   [Teaching Note 7 A Rundown On Continuous Time Models](Teaching%20Note%207%20A%20Rundown%20On%20Continuous%20Time%20Models.md)

   [PSET I Fixed Income Asset Pricing](PSET%20I%20Fixed%20Income%20Asset%20Pricing.md)

## INTRODUCTION

   - Several changes to fixed-income markets took place in the aftermath of the crisis
   1. Many countries increased debt to "stimulate" the economy.
   	- Lower tax revenues due to the economic downturn and higher government spending
   	=⇒ large increase in government debt.
   2. The huge mortgage-backed securities market had several changes
   	- Fannie Mae and Freddie Mac went into conservatorship. Many mortgage companies disappeared. New regulation has been enacted.
   3. Aggressive monetary policy has had large impact on Treasury bonds
   - Federal Reserve slashed Fed Funds rate to zero
   - Federal Reserve moved to "unconventional monetary policy"
   4. Massive regulatory changes in derivative markets
   	- Central counterparties (CCP)
   	- Impact on pricing of derivatives.
   5. Dramatic change in behavior of Treasury bonds
   	- From positive beta to negative beta securities
   	- Negative rates in many

## THE OUTSTANDING AMOUNT U.S. DEBT

![](Introduction%20To%20Fixed%20Income%20Securities-20240331084127851.png)
   (Source: SIFMA and FRED at Federal Reserve of St. Louis.)

## FEDERAL FUNDS AND U.S. TREASURY YIELDS

![](Introduction%20To%20Fixed%20Income%20Securities-20240331084204167.png)

## THE NOTIONAL AMOUNT OF OVER-THE-COUNTER DERIVATIVES

   Panel A. Millions Of Us Dollars
![](Introduction%20To%20Fixed%20Income%20Securities-20240331084224576.png)
   (Data Source: OTC derivatives data are from the Bank for International Settlements, while global GDP data are from the World Bank.)

![](Introduction%20To%20Fixed%20Income%20Securities-20240331084249962.png)

## U.S. TREASURY BILLS, NOTES, AND BONDS

![](Introduction%20To%20Fixed%20Income%20Securities-20240331084310756.png)

   - U.S. Government Issues Various Kinds Of Debt Securities
   1. Treasury Bills: Zero coupon securities with maturity up to one year 2. Treasury Notes: Fixed coupon bonds with maturity up to 10 years 3. Treasury Bonds: Fixed coupon bonds with maturity of 30 years 4. Treasury Inflation-Protected Securities (TIPS): Floating coupon bonds indexed to inflation
   5. Floating Rate Notes (FRNs): Floating coupon bonds, with coupon indexed to T-Bill rates

## MARKETABLE U.S. TREASURY SECURITIES (MILLION OF DOLLARS) DECEMBER 31,2021

   | Debt Held                      | Intragovernmental   |
   |--------------------------------|---------------------|
   | by the Public                  | Holdings            |
   | Dollar                         | Percent Dollar      |
   | Bills                          | 3,767,964           |
   | Notes                          | 12,992,160          |
   | Bonds                          | 3,474,153           |
   | Inflation-Protected Securities | 1,727,968           |
   | Floating Rate Notes            | 603,302             |
   | Federal Financing Bank         | 0                   |
   | Total                          | 22,565,547          |

   Source: U.S. Treasury web site. https://www.treasurydirect.gov

## INTEREST RATES AND COMPOUNDING FREQUENCY

   - The concept of interest rates is ubiquitous to fixed income securities.
   - Problem: An interest rate is not well defined without a compounding frequency.
   - Example: A$100 investment at 10% interest rate over 10 years has payoffs:
   - $$\begin{aligned}
   

   \text{Annual compounding:} \$100\times{(1.1)}^{10} & =\$259.37 \\
   \text{Semi-annual compounding}:\quad\quad\$100\times\left(1.05\right)^{20}& =\$265.33 \\
   \text{Quarterly compounding}:\quad\text{\$}100\times{(1.025)}^{40}& =\$268.51 \\
   \text{Daily compounding: \$}100\times\left(1+\frac{0.1}{365}\right)^{10\times365}& =\$271.79 \\
   \text{Continuous compounding}:\quad\quad\text{\$}100\times e^{0.1\times10}& =\$271.82
   \end{aligned}$$

   - The general formula to compound n times over the horizon T is

   $$V=\left(1+\frac{r}{n}\right)^{n\times T}$$

   $\bullet$ For $n$ large, we converge to continuous compounding

   $$V=\left(1+\frac{r}{n}\right)^{n\times T}\longrightarrow e^{r\times T}$$

## DISCOUNTING

   - Discounting is opposite process from the previous one.
   - The question is: "what is the amount we have to invest today to have $1 dollar In the future, given a rate r compounded n times per year?"
   - Inverting the relation above, we obtain

   $$Z(T)=\frac{1}{\left(1+\frac{r}{n}\right)^{n\times T}}$$

   $\bullet$ In the limit as $n\rightarrow\infty$ we obtain the usual continuous compounding formula

   $$Z(T)=\frac{1}{\left(1+\frac{r}{n}\right)^{n\times T}}\longrightarrow Z(T)=e^{-rT}$$

## DISCOUNTS AND RATES

   - Note that the compounding frequency is mostly a convention.
   - The key question is:
   	- "How much are investors willing to pay today to have $1 at T".
   - Such price, Z (T), is always well defined.
   - Given Z (T), we can derive the rate rn for any given compounding frequency n:

   $$r_{n}=n\times\left(\frac{1}{Z(T)^{\frac{1}{nT}}}-1\right)$$

   - The continuously compounded rate is instead

   $$r=-\frac{1}{T}\log\left(Z(T)\right)$$

## THE TERM STRUCTURE OF INTEREST RATES

   - When we discount future cash flows to the present, different discount rates apply for different maturities.
   - We denote the discount factor at t for a dollar to be received at time T by

   $$Z(t,T)=e^{-r(t,T)(T-t)}$$

   - r (*t, T*) = continuously compounded yield at t for an investment up to T.
   	- We put two "time" indices:
   		1. $t$ = calendar time when the discounting is made (e.g. 1/31/2007, etc.)
   		2. $T$ = maturity date.
   	1. =⇒ $T − t$ = time to maturity

   - Panel A of next figure shows $Z (t, T)$ for $t = 1/31/2007, 1/31/2008, …, 3/20/2020$, and for $T − t$ ranging from 0 to 30 yecasc
   - Panel B of next figure shows the corresponding yields r (*t, T*)
![|500](Introduction%20To%20Fixed%20Income%20Securities-20240331084530427.png)

   ![](Introduction%20To%20Fixed%20Income%20Securities-20240331084555484.png)

## YIELD CURVES

   - Yield curves change a lot over time. - They also have many shapes:
   - Flat (e.g. 1/31/2007)
   - Increasing (e.g. 1/30/2015) - Hump (e.g. 1/31/2009) - Inverted hump (slightly, 1/31/2007)
   - What generates the shape of the term structure of interest rates?
   - What does it imply for derivative pricing etc?
   - Indeed, there is much variation not only in level but in slope of the yield curve
   - What do these variations tell us about investors' beliefs about future rates? - What do they tell us about risk premia required to hold bonds?
   (Data: Yields up to 5 years are from CRSP. Yields from 10 to 30 are from G¨urkaynak, Sack, and Wright (2007), updated series.)

## COUPON BONDS

   - What is the price of coupon bond?
   - A coupon bond is just a sequence of cash payments c/2 (coupons) for dates
   T 1, T 2*, …, T*n and one big payment of 100 + c/2 (principal) at Tn (= maturity of
   The bond).
   - If we know the time value of money for each maturity, that is, the discount function
   Z (*t, T*i) for all maturities Ti's, a simple no arbitrage argument implies

   $$P(t,T_{n})=c/2\times Z(t,T_{1})+c/2\times Z(t,T_{2})+…+(100+c/2)\,Z\,(t,T_{n})$$

    $$=\sum\limits_{i=1}^{n}\frac{c/2}{\left(1+r_{2}\left(t,T_{i}\right)/2\right)^{2\times\left(T_{i}-t\right)}}+\frac{100}{\left(1+r_{2}\left(t,T_{n}\right)/2\right)^{2\times\left(T_{n}-t\right)}}$$

   - What is the arbitrage argument?

## COUPON BONDS

   - Suppose that the price of the bond is trading at par (100) but the right-hand side is 105.
   - Then an arbitrageur can buy the bond (pay 100) and sell the strips (each cash payments) for a total of 105, thereby making $5 (million). Since there is perfect matching of cash flows in the future, the trade is an arbitrage.
   - Incidentally, notice that if t = 0 and Ti are exact semi-annual maturities, that is T 1 =.5, T 2 = 1, T 3 = 1.5 etc., then we have 2 × Ti = i for every i = 1*,.., n*,
   And thus the formula reduces to

   $$P(0,T_{n})=\sum_{i=1}^{n}\frac{c/2}{\left(1+r_{2}\left(0,T_{i}\right)/2\right)^{i}}+\frac{100}{\left(1+r_{2}\left(0,T_{n}\right)/2\right)^{n}}$$

## CONVENTIONS AND TERMINOLOGY

   - It is important to spend a few words on some market conventions and terminology.

## - ACCRUED INTEREST

   - The market prices of bonds quoted in newspapers are **clean prices**. That is,
   They are quoted without any accrued interest.
   - The accrued interest is the amount of interest that has built up since the last
   Coupon payment.
   - The actual payment is called invoice price (or **dirty price**).

## DAY COUNT CONVENTIONS - HOW DO WE COUNT DAYS? THREE MAIN WAYS

   1. Actual/Actual: Simply Count the number of calendar days; 2. 30/360: Assume there are 30 days in a month and 360 in a year; 3. Actual/360: Each month has the right number of days, but there are only 360
   Days in a year.
   - Which convention it is used depend on the security considered. - Treasuries use Actual/Actual.

## DISCOUNT YIELD AND BOND EQUIVALENT YIELD

   - T-bills are quoted on a discount yield d basis. That is, the quote reports a *yield*.
   - If n is the number of days to maturity, the price of the T-bill is

   $$P=100\times\left[1-\frac{n}{360}\times d\right]$$

   $\bullet$ In other words

   $$d=\frac{100-P}{100}\times\frac{360}{n}$$

   $\bullet$ Instead, it should be

   $$BEY=\frac{100-P}{P}\times\frac{365}{n}$$

   $\bullet$ BEY = Bond Equivalent Yield

   - Of course, we obtain

   $$B E Y={\frac{365\times d}{360-d\times n}}$$

## YIELD-TO-MATURITY (OR INTERNAL RATE OF RETURN)

   - Given price $P\left(t,T\right)$ and cash flows $c/2$ at $T_{i}$ 's for $i=1,..,n$, and $1+c/2$ at $T_{n}$, the (semi-annually compounded) yield-to-maturity YTM is defined as that rate $y$ such that $$P\left(t,T_{n}\right)=\sum\limits_{i=1}^{n}\frac{c/2}{\left(1+\frac{n}{2}\right)^{2\times\left(T_{i}-t\right)}}+\frac{100}{\left(1+\frac{n}{2}\right)^{2\times\left(T_{n}-t\right)}}$$

    (1)

   - Recall that given the spot curve r 2 (*t, T*i), we also had

   $$P\left(t,T_{n}\right)=\sum\limits_{i=1}^{n}{\frac{c/2}{\left(1+r_{2}\left(t,T_{i}\right)/2\right)^{2\times\left(T_{i}-t\right)}}}+{\frac{100}{\left(1+r_{2}\left(t,T_{n}\right)/2\right)^{2\times\left(T_{n}-t\right)}}}$$

   - What's the difference?
   - The yield to maturity y is a sort of average discount rate that characterizes
   One *particular bond*, and it is used to discount the cash flows of *that* particular bond.
   - Notice that two different bonds with same maturity, will have different yield
   To maturities if they have different coupons.

## YIELD-TO-MATURITY

   - We will almost never use YTM - It is blatantly wrong as a measure of yield, as it assumes that all the coupons can
   Be reinvested at the constant y throughout the life of the bond.
   - That is: not only it assumes a flat yield curve, but also one that does not move
   Over time.
   - Example: consider the following data:

   |    |    | Bond Maturity (Years) Coupon   |   Price | Yield-to-Maturity   |
   |----|----|--------------------------------|---------|---------------------|
   |  1 |  2 | 9%                             |   98.57 | 9.82%               |
   |  2 |  2 | 10%                            |  100.34 | 9.80%               |
   |  3 |  2 | 3%                             |   88    | 9.91%               |

   - What is the most attractive bond?

## YIELD-TO-MATURITY

   - Judging from the Yield-to-Maturity, bond 3 looks great. - However, it is dominated by a combination of 1 and 2, as we can mimic exactly
   Its cash flows and find a (slightly) lower price.
   - Let N 1 and N 2, be the number of the first and the second coupon bonds
   - Then

   $$\begin{array}{c}{{N_{1}\times9+N_{2}\times10\;=\;3}}\\ {{N_{1}\times109+N_{2}\times110\;=\;103}}\end{array}$$

   - Solving the system =⇒ the portfolio long N 1 = 7 units in bond 1 and short of
   N 2 = −6 units bond 2 mimics exactly the cash flows of bond 3.
   - The value of this portfolio is N 1 × 98.57 + N 2 × 100.34 = 87.95 < 88.
   - The YTM of the portfolio is even bigger: YTM=9.94%.
   - Why is this happening?
   - The YTM measures the average return on the bond under the assumption that
   all coupons are reinvested at the same rate y.
   - With a non-flat term structure, this is simply not going to happen and using YTM
   For relative pricing yields bad results.
   - The low coupon in bond 3 together with the fact that we cannot re-invest at the
   High rate of 9.91% for the whole life of the bond yields the implication that the third bond is "no better" than a portfolio of the other two (which have lower YTMs).

## FLOATING RATE NOTES

   - Floating rate notes are securities whose coupon is not fixed, but it depends on
   Realized short-term rates rt.
   - If rt increases =⇒ coupon increases. And vice versa.
   - The U.S. Treasury started issuing floating rate notes (FRN) in January 2014. - They pay quarterly coupons using the 13-week U.S. T-bill rate as a reference rate,
   Plus a spread determined at the auction of the FRN.
   - Let T 1, T 2, …, Tn denote the coupon payment dates, with Ti+1 = Ti + 0.25.
   - Then the (annualized) coupon rate at time Ti is given by

   $$c(T_{i})=r(T_{i-1})+\mathrm{spread}$$

   - Where r (Ti−1) is the quarterly compounded, (annualized) three-month rate.

## FLOATING RATE NOTES: PRICING

   - How do we price a security with unknown future coupons?
   - We can use a recursive argument. Let's start with a spread = 0
   - Let Tn = maturity date, where n is the total number of coupon payments.
   - Suppose that today is actually Tn−1.
   - =⇒ Today we know the reference rate r (Tn−1) and hence

   Cash flow at Tn = 1 + 1 4 c (Tn) = 1 + 1 4 r (Tn−1)

   - The value of FRN at Tn−1 is

   $$P^{F R N}(T_{n-1})\;=\;\frac{\mathsf{C a s h\;f l o w\;a t\;}T_{n}}{1+\frac{1}{4}r(T_{n-1})}=\frac{1+\frac{1}{4}c(T_{n})}{1+\frac{1}{4}r(T_{n-1})}=\frac{1+\frac{1}{4}r(T_{n-1})}{1+\frac{1}{4}r(T_{n-1})}=1$$

   - Consider now the value of the FRN at Tn−2.
   - At this time, the investor knows that the FRN will c (Tn−1) = r (Tn−2) at Tn−1,
   And that its price will revert to P FRN (Tn−1) = 1.

   - The FRN value at $T_{n-2}$ is then $$P^{FRN}(T_{n-2})\,=\,\frac{P^{FRN}(T_{n-1})+\frac{1}{4}c(T_{n-1})}{1+\frac{1}{4}r(T_{n-2})}=\frac{1+\frac{1}{4}r(T_{n-2})}{1+\frac{1}{4}r(T_{n-2})}=1$$
   - Using the same logic for every reset time Ti: =⇒ P FRN (Ti) = 1
   - Outside reset times, the price of FRN is different from 1.
   - Let t be such that Ti−1 *< t < T*i. Then, the value at t of FRN is

   $$P^{F R N}(t)\;=\;Z(t,T_{i})(1+r(T_{i-1})/4)$$

   - Adding a spread to the coupon payments is simple because the spread is constant.

   =⇒ use discounts Z (*t, T*) to compute its value.

## REPURCHASE AGREEMENTS

   - **Repurchase Agreements (Repo)**: Agreement to sell some securities to another party and buy them back at a fixed date and for a fixed amount.
   - The price at which the security is bought back is greater than the selling price
   And the difference implies an interest rate called *Repo Rate*.
   - A **Reverse Repo** is the borrowing of a security for a short period at an agreed
   Interest rate.
   - The Repo Market is the single most important source of financing for government
   Dealers.
   - Since government securities are liquid and default free, they are excellent collateral.
   - Dealers can borrow money on a collateralized basis, so that they can take huge
   Positions even with limited capital.
   - The Repo Market grew very large. Next table shows the average *daily* amount
   Outstanding
![](Introduction%20To%20Fixed%20Income%20Securities-20240331091908885.png)
## FINANCING BY U.S. GOVERNMENT SECURITIES DEALERS AVERAGE DAILY AMOUNT OUTSTANDING ($ BILLIONS)

   (Source: SIFMA http://www.sifma.org/research/statistics.aspx)

## BILATERAL REPURCHASE AGREEMENTS

   - A Repo transaction is as follows: Consider a trader and a repo-dealer. The trader
   At time t wants to take a long position until time T (typically, overnight!)

![](Z.%20Clippings/Lecture%20Note%201%20Introduction%20To%20Fixed%20Income%20Securities-20240415223856802.png)

   Pay (Pt− haircut)× (1+repo rate × n

## REPURCHASE AGREEMENTS

   1. At time t, the trader buys the bond at market price $P_t$ and enters into a Repo with the Repo Dealer. Hence, the trader delivers the bond as collateral to the repo-dealer and gets the cash to purchase the bond.
   	- The Repo Dealer typically gives something less than the market price of the bond. The difference is called **hair cut**.
   	- The term T is decided at time t: Most Repurchase agreements are for a very short term (overnight). Some longer term agreements reach 30 days or more.
   	- The Repo rate is decided at time t.
   1. At time T, the trader gets back the bond from the Repo Dealer, sells the bond
   In the market to get PT and pays Pt plus the repo rate to the dealer.
   - The profit is then PT − Pt−repo rate× n
   360 × (Pt − haircut).

   - Hence, the return on capital to the trader is

   $\text{Return}=\dfrac{P_{T}-P_{t}-\text{repo rate}\times\frac{n}{360}\times(P_{t}-\text{haircut})}{\text{haircut}}$

## REPURCHASE AGREEMENTS

   - Between t and T the trader earns the accrued interest on the bond
   - Positive Carry: If accrued interest > repo rate - Negative Carry: If accrued interest < repo rate.
   - Other important definitions/characteristics of Repo markets:
   1. **General Collateral Rate (GCF)**: This is the Repo Rate on most Treasury
   Securities.
   Hence, using one or another of these as collateral makes little
   Difference in terms of costs.
   2. - In a reverse repo, the trader (A) borrows the security from the repo dealer;
   (B) sells it; and (C) posts cash collateral with the dealer.
   - The trader is lending money to the dealer against the bond collateral =⇒
   The trader would be entitled to the repo rate.
   - However, the trader is happy to forgo part (all) of the repo rate in order to
   Get hold of the bond (to sell)

## REVERSE REPO TRANSACTION

   ![](Z.%20Clippings/Lecture%20Note%201%20Introduction%20To%20Fixed%20Income%20Securities-20240415224136376.png)

## TRI-PARTY REPO

   - Based on clearing and settlement infrastructure supported by Bank of New York
   Mellon and JPMorgan Chase
   - Banks provide collateral valuation, margining, and management services to facilitate trading.
   - Collateral allocation: automatically selects securities from cash borrower's inventory.
   - General Collateral Finance (GCF): cleared through the Fixed Income Clearing
   Corporation (FICC) GCF repo service. Mostly inter-dealer.
   - Ex-GCF: Not cleared through FICC. Institutional investors such as money market
   Funds lending to broker-dealers.
   - A forward rate determined at time t is the rate implicit in the current spot rate
   Function for an investment in T-bills made at date T 1 with maturity date T 2
   (> T 1).
   - There are three "dates" in the forward rate:
   1. Today (t);
   2. The first maturity at which the investment is made (T 1);
   3. The final maturity of the investment (T 2)
   - With semiannual compounding, we denote it f 2 (t, T 1, T 2)
   - With continuous compounding, we denote it f (t, T 1, T 2)
   - How do we determine the forward rates?
   	- By no arbitrage.
   - Suppose today is t = 0 and that I have $10 million to invest for 1 year.
   - We have the following two strategies
   1. Invest in a 1-year zero coupon bond, obtaining at maturity

   $$\$10\mathrm{~million}\times\left(1+r_{2}\left(0,1\right)/2\right)^{2}$$

   2. 2.Invest in a 6-months zero coupon bond and enter (today) into a forward contract to invest the proceeds at $T_1=0.5$ until $T_2=1$ for a rate $f_2\left(0,0.5,1\right)$. At maturity we have

   $$10 m × $(1+r_2\left(0,0.5\right)/2)\times\left(1+\frac{f_2\left(0,0.5,1\right)}{2}\right)$$

   - By no arbitrage (and if credit risk is negligible) we must have

   $$\$10\ \textsf{m}\times\left(1+{\frac{r_{2}\left(0,1\right)}{2}}\right)^{2}=\$10\ \textsf{m}\times\left(1+{\frac{r_{2}\left(0,0.5\right)}{2}}\right)\times\left(1+{\frac{f_{2}\left(0,0.5,1\right)}{2}}\right)$$

   - Or

   $$1+{\frac{f_{2}\left(0,0.5,1\right)}{2}}={\frac{\left(1+r_{2}\left(0,1\right)/2\right)^{2}}{\left(1+r_{2}\left(0,0.5\right)/2\right)}}$$

   - By using the price of bonds we have

   $$1+\frac{f_{2}\left(0,0.5,1\right)}{2}=\frac{Z(0,0.5)}{Z(0,1)}$$

   - More generally, for every T 1 and T 2, consider the following strategies:
   1. Invest in a $T_{2}-$ zero coupon bond, obtaining at maturity

   $$\frac{\$10\text{m}}{ Z (0, T _ 2)}$$

   2. Invest in a 6-months zero coupon bond and enter (today) into a forward contract to invest the proceeds at $T_1=0.5$ until $T_2=1$ for a rate $f_2\left(0,0.5,1\right)$. At maturity we have

   $$\frac{\$10\ m}{Z(0,T_{1})}\times\left(1+\frac{f_{n}\left(0,T_{1},T_{2}\right)}{n}\right)^{n(T_{2}-T_{1})}$$

   - We then obtain

   $$\left(1+\frac{f_{n}\left(0,T_{1},T_{2}\right)}{n}\right)^{n(T_{2}-T_{1})}=\frac{Z(0,T_{1})}{Z(0,T_{2})}$$

## CONTINUOUSLY COMPOUNDED FORWARD RATES

   - Taking the limit as $n\rightarrow\infty$ the continuously compounded forward rates is $$f(0,T_{1},T_{2})\ =\ \frac{\ln(Z(0,T_{1}))-\ln(Z(0,T_{2}))}{T_{2}-T_{1}}$$

    $$=\ \frac{r(0,T_{2})T_{2}-r(0,T_{1})T_{1}}{T_{2}-T_{1}}\tag{2}$$

   - Another concept, that we will use later, is that of instantaneous forward rate.
   - We can rewrite (2) as (exercise: do it!)

   $$f(0,T_{1},T_{2})=r(0,T_{1})+T_{2}\times\frac{r(0,T_{2})-r(0,T_{1})}{T_{2}-T_{1}}\tag{3}$$

   - If we take the limit $T_{2}\longrightarrow T_{1}$ (that is, the horizon of the forward contract shrinks to zero) we obtain

   $$f(0,T_{1},T_{1})=r(0,T_{1})+T_{1}\times\frac{dr(0,T_{1})}{dT_{1}}\tag{4}$$

## THE RELATION BETWEEN FORWARD CURVE AND SPOT CURVE

   - The equation for the instantaneous forward curve (4) is revealing of an interesting (important) property of the forward-spot relationship.
   - We can rewrite

   $$f(0,T_{1},T_{1})-r(0,T_{1})=T_{1}\times\frac{dr(0,T_{1})}{dT_{1}}$$

   - This implies:

   $$\begin{gathered}
   \text{If }\quad\frac{dr(0,T_1)}{dT_1}>0 \Longrightarrow\text{ forward curve is above the spot curve} \\
   \text{If }\quad\frac{dr(0,T_1)}{dT_1}<0 \Longrightarrow\text{ forward curve is below the spot curve} \\
   \begin{aligned}\mathsf{If}\quad\frac{dr(0,T_1)}{dT_1}=0\end{aligned} \Longrightarrow\text{ forward curve intersects the spot curve}
   \end{gathered}$$
   - To obtain the forward curve we need a smooth yield curve.
   ![](Introduction%20To%20Fixed%20Income%20Securities-20240331091950722.png)
   ## ESTIMATING THE ZERO-COUPON DISCOUNT FUNCTION
   - There are several methods to extract the zero-coupon discount curve $Z (0, T)$ from bond data.
   - Why do we want to do that?
   1. The discount function Z (0, T) determines the time value of money. We need it as a basis to discount future (riskless) cash flows.
   2. We cannot observe it: it is implicitly embedded in traded Treasury coupon bonds.
   3. You need it to compute forward prices, for instance, as well as Swaps (see later).
   4. It will be the basis of all future term structure models: it is typically the first step to then calibrate term structure models. The latter are what traders use to
   	- (a) Price new securities by no arbitrage (we will see many).
   	- (b) Spot out arbitrage opportunities.
   		- The most "famous" is the bootstrapping methodology.
   
   ## BOOTSTRAP
   
   - Suppose we have n coupon bonds. Each bond i has a coupon equal to $c_i$.
   - Recall the pricing equation for coupon bonds with maturity $T_i$ is equal to
   $$P^{i}(t, T_{i})=\frac{c^{i}}{2}\sum\limits_{j=1}^{i}Z (t, T_{j})+1\times Z (t, T_{i})\tag{5}$$
   - Today is t = 0 and that we have data on maturities $T_j = 0.5, 1, 1.5*, .... T_n$.
   - Inverting (5), we obtain
   $$Z\left (0,0.5\right)\;=\;\frac{P^{1}\left (0,0.5\right)}{1+c^{1}/2}$$
   
   $$Z\left (0,1\right)\;=\;\frac{P^{2}\left (0,1\right)-c^{2}/2\times Z\left (0,. 5\right)}{1+c^{2}/2}$$
   
   $$Z\left (0,1.5\right)\;=\;\frac{P^{3}\left (0,1.5\right)-c^{3}/2\times\left (Z\left (0,. 5\right)+Z\left (0,1\right)\right)}{1+c^{3}/2}$$
   - In general, for every i:
   $$Z\left (0, T_{i}\right)=\frac{P^{i}\left (0, T_{i}\right)-c^{i}/2\times\left (\Sigma_{j=1}^{i-1}\, Z\left (0, T_{j}\right)\right)}{1+c^{i}/2}$$
   - Example: suppose we have the following data:
   $$\begin{array}{ccccc}
   \hline \text { Maturity } & \text { Period } i & \text { Coupon } & \text { YTM } & \text { Price } \\
   \hline 0.5 & 1 & 0.000 & 0.080 & 96.15 \\
   1 & 2 & 0.000 & 0.083 & 92.19 \\
   1.5 & 3 & 0.085 & 0.089 & 99.45 \\
   2 & 4 & 0.090 & 0.092 & 99.64 \\
   2.5 & 5 & 0.110 & 0.094 & 103.49 \\
   3 & 6 & 0.095 & 0.097 & 99.49 \\
   3.5 & 7 & 0.100 & 0.100 & 100.00 \\
   \hline
   \end{array}$$
   
   - We find:
   $$\begin{array}{l l} {{Z\left(0,.5\right)\;=\;96.15;\qquad Z\left(0,1\right)=92.19;}} \\ {{}} \\ {{Z\left(0,1.5\right)\;=\;\frac{99.45-.0425\times\left(96.15+92.19\right)}{1.0425}=87.72;\ldots.}} \end{array}$$
   
   - Since
   
   $$Z\left (0, T_{i}\right)=\frac{100}{\left (1+\frac{r_{2}\left (0, T_{i}\right)}{2}\right)^{i}}\Longleftrightarrow r_{2}\left (0, T_{i}\right)=2\times\left (\left (\frac{100}{Z\left (0, T_{i}\right)}\right)^{\frac{1}{i}}-1\right)$$
   
   We Obtain
   $$

   \begin{array}{cccc}
   \hline \text { Maturity } & \text { Period } i & \text { YTM } & \text { Spot Yield } \\
   \hline 0.5 & 1 & 0.080 & 0.080 \\
   1 & 2 & 0.083 & 0.083 \\
   1.5 & 3 & 0.089 & 0.0893 \\
   2 & 4 & 0.092 & 0.09247 \\
   2.5 & 5 & 0.094 & 0.09468 \\
   3 & 6 & 0.097 & 0.09787 \\
   3.5 & 7 & 0.100 & 0.10129 \\
   \hline
   \end{array}

   $$
   ## CURVE FITTING
   
   - The above methodologies require that we have all the maturities available. 
   - Unfortunately, this is never the case. 
   - To avoid this problem, the profession moved to "curve fitting" in the following sense:
   1. Assume a flexible functional form for Z (0, T), such as (Nelson Siegel Model):
   $$Z\left (0, T_{j}\right)\;=\; 100\times e^{-r\left (0, T_{j}\right)\times T_{j}}$$
   
   $$r (0, T_{j})\;=\;\theta_{0}+(\theta_{1}+\theta_{2})\,\frac{1-e^{-\frac{T_{j}}{\lambda}}}{\frac{T_{j}}{\lambda}}-\theta_{2}e^{-\frac{T_{j}}{\lambda}}$$
   2. We can compute the "theoretical price" given Z (0, T)
   $$\widehat{P}\left (0, T_{j}\right)=\sum\limits_{i=1}^{j}c\left (T_{i}\right)\times Z\left (0, T_{i}\right)$$
   3. We estimate the parameters θ0, θ1, θ2, λ by **non-linear least squares**.
   That is, by minimizing
   $$\operatorname*{min}_{\theta_{0},\theta_{1},\theta_{2},\lambda}\sum_{j=1}^{n}\left (P\left (0, T_{j}\right)-\widehat{P}\left (0, T_{j}\right)\right)^{2}$$
   - There is a large literature on the [Functional Forms](Lecture%2010-%20Functional%20Forms.md) for the discount function
   Z (0, T), many of them relying on spline functions.
   - Next figure shows the difference between using bootstrapping technique and the
   Curve fitting technique
   
   ## ZERO-COUPON YIELD CURVES
![](Teaching%20Note%201%20Introduction%20To%20Fixed%20Income%20Securities-1.octet-stream)
   ![](Introduction%20To%20Fixed%20Income%20Securities-20240331152353486.png)
   
   - Clearly, the fitted curve is much smoother (by construction).
   - An important difference arises when we look at forward rates
   -    ![](Introduction%20To%20Fixed%20Income%20Securities-20240331152522582.png)"
url: "
# Teaching Note 1 Introduction To Fixed Income Securities

# INTRODUCTION TO FIXED INCOME SECURITIES

   John Heaton
   The University of Chicago Booth School of Business
   NBER
	[[Fixed Income Lecture Notes]]
	[[Introduction to Fixed Income Asset Pricing]]
	[[Lecture Note 2Interest Rate Risk Management And Factors]]
	[[Teaching Note 3 Understanding The Term Structure Of Interest Rates]]
	[[Teaching Note 4 Interest Rate Derivatives]]
	[[Teaching Note 5 Risk Neutral Pricing]]
   [Teaching Note 6 Mortgage Backed Securities](Teaching%20Note%206%20Mortgage%20Backed%20Securities.md)
   [Teaching Note 7 A Rundown On Continuous Time Models](Teaching%20Note%207%20A%20Rundown%20On%20Continuous%20Time%20Models.md)

   [PSET I Fixed Income Asset Pricing](PSET%20I%20Fixed%20Income%20Asset%20Pricing.md)

## INTRODUCTION

   - Several changes to fixed-income markets took place in the aftermath of the crisis
   1. Many countries increased debt to "stimulate" the economy.
   	- Lower tax revenues due to the economic downturn and higher government spending
   	=⇒ large increase in government debt.
   2. The huge mortgage-backed securities market had several changes
   	- Fannie Mae and Freddie Mac went into conservatorship. Many mortgage companies disappeared. New regulation has been enacted.
   3. Aggressive monetary policy has had large impact on Treasury bonds
   - Federal Reserve slashed Fed Funds rate to zero
   - Federal Reserve moved to "unconventional monetary policy"
   4. Massive regulatory changes in derivative markets
   	- Central counterparties (CCP)
   	- Impact on pricing of derivatives.
   5. Dramatic change in behavior of Treasury bonds
   	- From positive beta to negative beta securities
   	- Negative rates in many

## THE OUTSTANDING AMOUNT U.S. DEBT

![](Introduction%20To%20Fixed%20Income%20Securities-20240331084127851.png)
   (Source: SIFMA and FRED at Federal Reserve of St. Louis.)

## FEDERAL FUNDS AND U.S. TREASURY YIELDS

![](Introduction%20To%20Fixed%20Income%20Securities-20240331084204167.png)

## THE NOTIONAL AMOUNT OF OVER-THE-COUNTER DERIVATIVES

   Panel A. Millions Of Us Dollars
![](Introduction%20To%20Fixed%20Income%20Securities-20240331084224576.png)
   (Data Source: OTC derivatives data are from the Bank for International Settlements, while global GDP data are from the World Bank.)

![](Introduction%20To%20Fixed%20Income%20Securities-20240331084249962.png)

## U.S. TREASURY BILLS, NOTES, AND BONDS

![](Introduction%20To%20Fixed%20Income%20Securities-20240331084310756.png)

   - U.S. Government Issues Various Kinds Of Debt Securities
   1. Treasury Bills: Zero coupon securities with maturity up to one year 2. Treasury Notes: Fixed coupon bonds with maturity up to 10 years 3. Treasury Bonds: Fixed coupon bonds with maturity of 30 years 4. Treasury Inflation-Protected Securities (TIPS): Floating coupon bonds indexed to inflation
   5. Floating Rate Notes (FRNs): Floating coupon bonds, with coupon indexed to T-Bill rates

## MARKETABLE U.S. TREASURY SECURITIES (MILLION OF DOLLARS) DECEMBER 31,2021

   | Debt Held                      | Intragovernmental   |
   |--------------------------------|---------------------|
   | by the Public                  | Holdings            |
   | Dollar                         | Percent Dollar      |
   | Bills                          | 3,767,964           |
   | Notes                          | 12,992,160          |
   | Bonds                          | 3,474,153           |
   | Inflation-Protected Securities | 1,727,968           |
   | Floating Rate Notes            | 603,302             |
   | Federal Financing Bank         | 0                   |
   | Total                          | 22,565,547          |

   Source: U.S. Treasury web site. https://www.treasurydirect.gov

## INTEREST RATES AND COMPOUNDING FREQUENCY

   - The concept of interest rates is ubiquitous to fixed income securities.
   - Problem: An interest rate is not well defined without a compounding frequency.
   - Example: A$100 investment at 10% interest rate over 10 years has payoffs:
   - $$\begin{aligned}
   

   \text{Annual compounding:} \$100\times{(1.1)}^{10} & =\$259.37 \\
   \text{Semi-annual compounding}:\quad\quad\$100\times\left(1.05\right)^{20}& =\$265.33 \\
   \text{Quarterly compounding}:\quad\text{\$}100\times{(1.025)}^{40}& =\$268.51 \\
   \text{Daily compounding: \$}100\times\left(1+\frac{0.1}{365}\right)^{10\times365}& =\$271.79 \\
   \text{Continuous compounding}:\quad\quad\text{\$}100\times e^{0.1\times10}& =\$271.82
   \end{aligned}$$

   - The general formula to compound n times over the horizon T is

   $$V=\left(1+\frac{r}{n}\right)^{n\times T}$$

   $\bullet$ For $n$ large, we converge to continuous compounding

   $$V=\left(1+\frac{r}{n}\right)^{n\times T}\longrightarrow e^{r\times T}$$

## DISCOUNTING

   - Discounting is opposite process from the previous one.
   - The question is: "what is the amount we have to invest today to have $1 dollar In the future, given a rate r compounded n times per year?"
   - Inverting the relation above, we obtain

   $$Z(T)=\frac{1}{\left(1+\frac{r}{n}\right)^{n\times T}}$$

   $\bullet$ In the limit as $n\rightarrow\infty$ we obtain the usual continuous compounding formula

   $$Z(T)=\frac{1}{\left(1+\frac{r}{n}\right)^{n\times T}}\longrightarrow Z(T)=e^{-rT}$$

## DISCOUNTS AND RATES

   - Note that the compounding frequency is mostly a convention.
   - The key question is:
   	- "How much are investors willing to pay today to have $1 at T".
   - Such price, Z (T), is always well defined.
   - Given Z (T), we can derive the rate rn for any given compounding frequency n:

   $$r_{n}=n\times\left(\frac{1}{Z(T)^{\frac{1}{nT}}}-1\right)$$

   - The continuously compounded rate is instead

   $$r=-\frac{1}{T}\log\left(Z(T)\right)$$

## THE TERM STRUCTURE OF INTEREST RATES

   - When we discount future cash flows to the present, different discount rates apply for different maturities.
   - We denote the discount factor at t for a dollar to be received at time T by

   $$Z(t,T)=e^{-r(t,T)(T-t)}$$

   - r (*t, T*) = continuously compounded yield at t for an investment up to T.
   	- We put two "time" indices:
   		1. $t$ = calendar time when the discounting is made (e.g. 1/31/2007, etc.)
   		2. $T$ = maturity date.
   	1. =⇒ $T − t$ = time to maturity

   - Panel A of next figure shows $Z (t, T)$ for $t = 1/31/2007, 1/31/2008, …, 3/20/2020$, and for $T − t$ ranging from 0 to 30 yecasc
   - Panel B of next figure shows the corresponding yields r (*t, T*)
![|500](Introduction%20To%20Fixed%20Income%20Securities-20240331084530427.png)

   ![](Introduction%20To%20Fixed%20Income%20Securities-20240331084555484.png)

## YIELD CURVES

   - Yield curves change a lot over time. - They also have many shapes:
   - Flat (e.g. 1/31/2007)
   - Increasing (e.g. 1/30/2015) - Hump (e.g. 1/31/2009) - Inverted hump (slightly, 1/31/2007)
   - What generates the shape of the term structure of interest rates?
   - What does it imply for derivative pricing etc?
   - Indeed, there is much variation not only in level but in slope of the yield curve
   - What do these variations tell us about investors' beliefs about future rates? - What do they tell us about risk premia required to hold bonds?
   (Data: Yields up to 5 years are from CRSP. Yields from 10 to 30 are from G¨urkaynak, Sack, and Wright (2007), updated series.)

## COUPON BONDS

   - What is the price of coupon bond?
   - A coupon bond is just a sequence of cash payments c/2 (coupons) for dates
   T 1, T 2*, …, T*n and one big payment of 100 + c/2 (principal) at Tn (= maturity of
   The bond).
   - If we know the time value of money for each maturity, that is, the discount function
   Z (*t, T*i) for all maturities Ti's, a simple no arbitrage argument implies

   $$P(t,T_{n})=c/2\times Z(t,T_{1})+c/2\times Z(t,T_{2})+…+(100+c/2)\,Z\,(t,T_{n})$$

    $$=\sum\limits_{i=1}^{n}\frac{c/2}{\left(1+r_{2}\left(t,T_{i}\right)/2\right)^{2\times\left(T_{i}-t\right)}}+\frac{100}{\left(1+r_{2}\left(t,T_{n}\right)/2\right)^{2\times\left(T_{n}-t\right)}}$$

   - What is the arbitrage argument?

## COUPON BONDS

   - Suppose that the price of the bond is trading at par (100) but the right-hand side is 105.
   - Then an arbitrageur can buy the bond (pay 100) and sell the strips (each cash payments) for a total of 105, thereby making $5 (million). Since there is perfect matching of cash flows in the future, the trade is an arbitrage.
   - Incidentally, notice that if t = 0 and Ti are exact semi-annual maturities, that is T 1 =.5, T 2 = 1, T 3 = 1.5 etc., then we have 2 × Ti = i for every i = 1*,.., n*,
   And thus the formula reduces to

   $$P(0,T_{n})=\sum_{i=1}^{n}\frac{c/2}{\left(1+r_{2}\left(0,T_{i}\right)/2\right)^{i}}+\frac{100}{\left(1+r_{2}\left(0,T_{n}\right)/2\right)^{n}}$$

## CONVENTIONS AND TERMINOLOGY

   - It is important to spend a few words on some market conventions and terminology.

## - ACCRUED INTEREST

   - The market prices of bonds quoted in newspapers are **clean prices**. That is,
   They are quoted without any accrued interest.
   - The accrued interest is the amount of interest that has built up since the last
   Coupon payment.
   - The actual payment is called invoice price (or **dirty price**).

## DAY COUNT CONVENTIONS - HOW DO WE COUNT DAYS? THREE MAIN WAYS

   1. Actual/Actual: Simply Count the number of calendar days; 2. 30/360: Assume there are 30 days in a month and 360 in a year; 3. Actual/360: Each month has the right number of days, but there are only 360
   Days in a year.
   - Which convention it is used depend on the security considered. - Treasuries use Actual/Actual.

## DISCOUNT YIELD AND BOND EQUIVALENT YIELD

   - T-bills are quoted on a discount yield d basis. That is, the quote reports a *yield*.
   - If n is the number of days to maturity, the price of the T-bill is

   $$P=100\times\left[1-\frac{n}{360}\times d\right]$$

   $\bullet$ In other words

   $$d=\frac{100-P}{100}\times\frac{360}{n}$$

   $\bullet$ Instead, it should be

   $$BEY=\frac{100-P}{P}\times\frac{365}{n}$$

   $\bullet$ BEY = Bond Equivalent Yield

   - Of course, we obtain

   $$B E Y={\frac{365\times d}{360-d\times n}}$$

## YIELD-TO-MATURITY (OR INTERNAL RATE OF RETURN)

   - Given price $P\left(t,T\right)$ and cash flows $c/2$ at $T_{i}$ 's for $i=1,..,n$, and $1+c/2$ at $T_{n}$, the (semi-annually compounded) yield-to-maturity YTM is defined as that rate $y$ such that $$P\left(t,T_{n}\right)=\sum\limits_{i=1}^{n}\frac{c/2}{\left(1+\frac{n}{2}\right)^{2\times\left(T_{i}-t\right)}}+\frac{100}{\left(1+\frac{n}{2}\right)^{2\times\left(T_{n}-t\right)}}$$

    (1)

   - Recall that given the spot curve r 2 (*t, T*i), we also had

   $$P\left(t,T_{n}\right)=\sum\limits_{i=1}^{n}{\frac{c/2}{\left(1+r_{2}\left(t,T_{i}\right)/2\right)^{2\times\left(T_{i}-t\right)}}}+{\frac{100}{\left(1+r_{2}\left(t,T_{n}\right)/2\right)^{2\times\left(T_{n}-t\right)}}}$$

   - What's the difference?
   - The yield to maturity y is a sort of average discount rate that characterizes
   One *particular bond*, and it is used to discount the cash flows of *that* particular bond.
   - Notice that two different bonds with same maturity, will have different yield
   To maturities if they have different coupons.

## YIELD-TO-MATURITY

   - We will almost never use YTM - It is blatantly wrong as a measure of yield, as it assumes that all the coupons can
   Be reinvested at the constant y throughout the life of the bond.
   - That is: not only it assumes a flat yield curve, but also one that does not move
   Over time.
   - Example: consider the following data:

   |    |    | Bond Maturity (Years) Coupon   |   Price | Yield-to-Maturity   |
   |----|----|--------------------------------|---------|---------------------|
   |  1 |  2 | 9%                             |   98.57 | 9.82%               |
   |  2 |  2 | 10%                            |  100.34 | 9.80%               |
   |  3 |  2 | 3%                             |   88    | 9.91%               |

   - What is the most attractive bond?

## YIELD-TO-MATURITY

   - Judging from the Yield-to-Maturity, bond 3 looks great. - However, it is dominated by a combination of 1 and 2, as we can mimic exactly
   Its cash flows and find a (slightly) lower price.
   - Let N 1 and N 2, be the number of the first and the second coupon bonds
   - Then

   $$\begin{array}{c}{{N_{1}\times9+N_{2}\times10\;=\;3}}\\ {{N_{1}\times109+N_{2}\times110\;=\;103}}\end{array}$$

   - Solving the system =⇒ the portfolio long N 1 = 7 units in bond 1 and short of
   N 2 = −6 units bond 2 mimics exactly the cash flows of bond 3.
   - The value of this portfolio is N 1 × 98.57 + N 2 × 100.34 = 87.95 < 88.
   - The YTM of the portfolio is even bigger: YTM=9.94%.
   - Why is this happening?
   - The YTM measures the average return on the bond under the assumption that
   all coupons are reinvested at the same rate y.
   - With a non-flat term structure, this is simply not going to happen and using YTM
   For relative pricing yields bad results.
   - The low coupon in bond 3 together with the fact that we cannot re-invest at the
   High rate of 9.91% for the whole life of the bond yields the implication that the third bond is "no better" than a portfolio of the other two (which have lower YTMs).

## FLOATING RATE NOTES

   - Floating rate notes are securities whose coupon is not fixed, but it depends on
   Realized short-term rates rt.
   - If rt increases =⇒ coupon increases. And vice versa.
   - The U.S. Treasury started issuing floating rate notes (FRN) in January 2014. - They pay quarterly coupons using the 13-week U.S. T-bill rate as a reference rate,
   Plus a spread determined at the auction of the FRN.
   - Let T 1, T 2, …, Tn denote the coupon payment dates, with Ti+1 = Ti + 0.25.
   - Then the (annualized) coupon rate at time Ti is given by

   $$c(T_{i})=r(T_{i-1})+\mathrm{spread}$$

   - Where r (Ti−1) is the quarterly compounded, (annualized) three-month rate.

## FLOATING RATE NOTES: PRICING

   - How do we price a security with unknown future coupons?
   - We can use a recursive argument. Let's start with a spread = 0
   - Let Tn = maturity date, where n is the total number of coupon payments.
   - Suppose that today is actually Tn−1.
   - =⇒ Today we know the reference rate r (Tn−1) and hence

   Cash flow at Tn = 1 + 1 4 c (Tn) = 1 + 1 4 r (Tn−1)

   - The value of FRN at Tn−1 is

   $$P^{F R N}(T_{n-1})\;=\;\frac{\mathsf{C a s h\;f l o w\;a t\;}T_{n}}{1+\frac{1}{4}r(T_{n-1})}=\frac{1+\frac{1}{4}c(T_{n})}{1+\frac{1}{4}r(T_{n-1})}=\frac{1+\frac{1}{4}r(T_{n-1})}{1+\frac{1}{4}r(T_{n-1})}=1$$

   - Consider now the value of the FRN at Tn−2.
   - At this time, the investor knows that the FRN will c (Tn−1) = r (Tn−2) at Tn−1,
   And that its price will revert to P FRN (Tn−1) = 1.

   - The FRN value at $T_{n-2}$ is then $$P^{FRN}(T_{n-2})\,=\,\frac{P^{FRN}(T_{n-1})+\frac{1}{4}c(T_{n-1})}{1+\frac{1}{4}r(T_{n-2})}=\frac{1+\frac{1}{4}r(T_{n-2})}{1+\frac{1}{4}r(T_{n-2})}=1$$
   - Using the same logic for every reset time Ti: =⇒ P FRN (Ti) = 1
   - Outside reset times, the price of FRN is different from 1.
   - Let t be such that Ti−1 *< t < T*i. Then, the value at t of FRN is

   $$P^{F R N}(t)\;=\;Z(t,T_{i})(1+r(T_{i-1})/4)$$

   - Adding a spread to the coupon payments is simple because the spread is constant.

   =⇒ use discounts Z (*t, T*) to compute its value.

## REPURCHASE AGREEMENTS

   - **Repurchase Agreements (Repo)**: Agreement to sell some securities to another party and buy them back at a fixed date and for a fixed amount.
   - The price at which the security is bought back is greater than the selling price
   And the difference implies an interest rate called *Repo Rate*.
   - A **Reverse Repo** is the borrowing of a security for a short period at an agreed
   Interest rate.
   - The Repo Market is the single most important source of financing for government
   Dealers.
   - Since government securities are liquid and default free, they are excellent collateral.
   - Dealers can borrow money on a collateralized basis, so that they can take huge
   Positions even with limited capital.
   - The Repo Market grew very large. Next table shows the average *daily* amount
   Outstanding
![](Introduction%20To%20Fixed%20Income%20Securities-20240331091908885.png)
## FINANCING BY U.S. GOVERNMENT SECURITIES DEALERS AVERAGE DAILY AMOUNT OUTSTANDING ($ BILLIONS)

   (Source: SIFMA http://www.sifma.org/research/statistics.aspx)

## BILATERAL REPURCHASE AGREEMENTS

   - A Repo transaction is as follows: Consider a trader and a repo-dealer. The trader
   At time t wants to take a long position until time T (typically, overnight!)

![](Z.%20Clippings/Lecture%20Note%201%20Introduction%20To%20Fixed%20Income%20Securities-20240415223856802.png)

   Pay (Pt− haircut)× (1+repo rate × n

## REPURCHASE AGREEMENTS

   1. At time t, the trader buys the bond at market price $P_t$ and enters into a Repo with the Repo Dealer. Hence, the trader delivers the bond as collateral to the repo-dealer and gets the cash to purchase the bond.
   	- The Repo Dealer typically gives something less than the market price of the bond. The difference is called **hair cut**.
   	- The term T is decided at time t: Most Repurchase agreements are for a very short term (overnight). Some longer term agreements reach 30 days or more.
   	- The Repo rate is decided at time t.
   1. At time T, the trader gets back the bond from the Repo Dealer, sells the bond
   In the market to get PT and pays Pt plus the repo rate to the dealer.
   - The profit is then PT − Pt−repo rate× n
   360 × (Pt − haircut).

   - Hence, the return on capital to the trader is

   $\text{Return}=\dfrac{P_{T}-P_{t}-\text{repo rate}\times\frac{n}{360}\times(P_{t}-\text{haircut})}{\text{haircut}}$

## REPURCHASE AGREEMENTS

   - Between t and T the trader earns the accrued interest on the bond
   - Positive Carry: If accrued interest > repo rate - Negative Carry: If accrued interest < repo rate.
   - Other important definitions/characteristics of Repo markets:
   1. **General Collateral Rate (GCF)**: This is the Repo Rate on most Treasury
   Securities.
   Hence, using one or another of these as collateral makes little
   Difference in terms of costs.
   2. - In a reverse repo, the trader (A) borrows the security from the repo dealer;
   (B) sells it; and (C) posts cash collateral with the dealer.
   - The trader is lending money to the dealer against the bond collateral =⇒
   The trader would be entitled to the repo rate.
   - However, the trader is happy to forgo part (all) of the repo rate in order to
   Get hold of the bond (to sell)

## REVERSE REPO TRANSACTION

   ![](Z.%20Clippings/Lecture%20Note%201%20Introduction%20To%20Fixed%20Income%20Securities-20240415224136376.png)

## TRI-PARTY REPO

   - Based on clearing and settlement infrastructure supported by Bank of New York
   Mellon and JPMorgan Chase
   - Banks provide collateral valuation, margining, and management services to facilitate trading.
   - Collateral allocation: automatically selects securities from cash borrower's inventory.
   - General Collateral Finance (GCF): cleared through the Fixed Income Clearing
   Corporation (FICC) GCF repo service. Mostly inter-dealer.
   - Ex-GCF: Not cleared through FICC. Institutional investors such as money market
   Funds lending to broker-dealers.
   - A forward rate determined at time t is the rate implicit in the current spot rate
   Function for an investment in T-bills made at date T 1 with maturity date T 2
   (> T 1).
   - There are three "dates" in the forward rate:
   1. Today (t);
   2. The first maturity at which the investment is made (T 1);
   3. The final maturity of the investment (T 2)
   - With semiannual compounding, we denote it f 2 (t, T 1, T 2)
   - With continuous compounding, we denote it f (t, T 1, T 2)
   - How do we determine the forward rates?
   	- By no arbitrage.
   - Suppose today is t = 0 and that I have $10 million to invest for 1 year.
   - We have the following two strategies
   1. Invest in a 1-year zero coupon bond, obtaining at maturity

   $$\$10\mathrm{~million}\times\left(1+r_{2}\left(0,1\right)/2\right)^{2}$$

   2. 2.Invest in a 6-months zero coupon bond and enter (today) into a forward contract to invest the proceeds at $T_1=0.5$ until $T_2=1$ for a rate $f_2\left(0,0.5,1\right)$. At maturity we have

   $$10 m × $(1+r_2\left(0,0.5\right)/2)\times\left(1+\frac{f_2\left(0,0.5,1\right)}{2}\right)$$

   - By no arbitrage (and if credit risk is negligible) we must have

   $$\$10\ \textsf{m}\times\left(1+{\frac{r_{2}\left(0,1\right)}{2}}\right)^{2}=\$10\ \textsf{m}\times\left(1+{\frac{r_{2}\left(0,0.5\right)}{2}}\right)\times\left(1+{\frac{f_{2}\left(0,0.5,1\right)}{2}}\right)$$

   - Or

   $$1+{\frac{f_{2}\left(0,0.5,1\right)}{2}}={\frac{\left(1+r_{2}\left(0,1\right)/2\right)^{2}}{\left(1+r_{2}\left(0,0.5\right)/2\right)}}$$

   - By using the price of bonds we have

   $$1+\frac{f_{2}\left(0,0.5,1\right)}{2}=\frac{Z(0,0.5)}{Z(0,1)}$$

   - More generally, for every T 1 and T 2, consider the following strategies:
   1. Invest in a $T_{2}-$ zero coupon bond, obtaining at maturity

   $$\frac{\$10\text{m}}{ Z (0, T _ 2)}$$

   2. Invest in a 6-months zero coupon bond and enter (today) into a forward contract to invest the proceeds at $T_1=0.5$ until $T_2=1$ for a rate $f_2\left(0,0.5,1\right)$. At maturity we have

   $$\frac{\$10\ m}{Z(0,T_{1})}\times\left(1+\frac{f_{n}\left(0,T_{1},T_{2}\right)}{n}\right)^{n(T_{2}-T_{1})}$$

   - We then obtain

   $$\left(1+\frac{f_{n}\left(0,T_{1},T_{2}\right)}{n}\right)^{n(T_{2}-T_{1})}=\frac{Z(0,T_{1})}{Z(0,T_{2})}$$

## CONTINUOUSLY COMPOUNDED FORWARD RATES

   - Taking the limit as $n\rightarrow\infty$ the continuously compounded forward rates is $$f(0,T_{1},T_{2})\ =\ \frac{\ln(Z(0,T_{1}))-\ln(Z(0,T_{2}))}{T_{2}-T_{1}}$$

    $$=\ \frac{r(0,T_{2})T_{2}-r(0,T_{1})T_{1}}{T_{2}-T_{1}}\tag{2}$$

   - Another concept, that we will use later, is that of instantaneous forward rate.
   - We can rewrite (2) as (exercise: do it!)

   $$f(0,T_{1},T_{2})=r(0,T_{1})+T_{2}\times\frac{r(0,T_{2})-r(0,T_{1})}{T_{2}-T_{1}}\tag{3}$$

   - If we take the limit $T_{2}\longrightarrow T_{1}$ (that is, the horizon of the forward contract shrinks to zero) we obtain

   $$f(0,T_{1},T_{1})=r(0,T_{1})+T_{1}\times\frac{dr(0,T_{1})}{dT_{1}}\tag{4}$$

## THE RELATION BETWEEN FORWARD CURVE AND SPOT CURVE

   - The equation for the instantaneous forward curve (4) is revealing of an interesting (important) property of the forward-spot relationship.
   - We can rewrite

   $$f(0,T_{1},T_{1})-r(0,T_{1})=T_{1}\times\frac{dr(0,T_{1})}{dT_{1}}$$

   - This implies:

   $$\begin{gathered}
   \text{If }\quad\frac{dr(0,T_1)}{dT_1}>0 \Longrightarrow\text{ forward curve is above the spot curve} \\
   \text{If }\quad\frac{dr(0,T_1)}{dT_1}<0 \Longrightarrow\text{ forward curve is below the spot curve} \\
   \begin{aligned}\mathsf{If}\quad\frac{dr(0,T_1)}{dT_1}=0\end{aligned} \Longrightarrow\text{ forward curve intersects the spot curve}
   \end{gathered}$$
   - To obtain the forward curve we need a smooth yield curve.
   ![](Introduction%20To%20Fixed%20Income%20Securities-20240331091950722.png)
   ## ESTIMATING THE ZERO-COUPON DISCOUNT FUNCTION
   - There are several methods to extract the zero-coupon discount curve $Z (0, T)$ from bond data.
   - Why do we want to do that?
   1. The discount function Z (0, T) determines the time value of money. We need it as a basis to discount future (riskless) cash flows.
   2. We cannot observe it: it is implicitly embedded in traded Treasury coupon bonds.
   3. You need it to compute forward prices, for instance, as well as Swaps (see later).
   4. It will be the basis of all future term structure models: it is typically the first step to then calibrate term structure models. The latter are what traders use to
   	- (a) Price new securities by no arbitrage (we will see many).
   	- (b) Spot out arbitrage opportunities.
   		- The most "famous" is the bootstrapping methodology.
   
   ## BOOTSTRAP
   
   - Suppose we have n coupon bonds. Each bond i has a coupon equal to $c_i$.
   - Recall the pricing equation for coupon bonds with maturity $T_i$ is equal to
   $$P^{i}(t, T_{i})=\frac{c^{i}}{2}\sum\limits_{j=1}^{i}Z (t, T_{j})+1\times Z (t, T_{i})\tag{5}$$
   - Today is t = 0 and that we have data on maturities $T_j = 0.5, 1, 1.5*, .... T_n$.
   - Inverting (5), we obtain
   $$Z\left (0,0.5\right)\;=\;\frac{P^{1}\left (0,0.5\right)}{1+c^{1}/2}$$
   
   $$Z\left (0,1\right)\;=\;\frac{P^{2}\left (0,1\right)-c^{2}/2\times Z\left (0,. 5\right)}{1+c^{2}/2}$$
   
   $$Z\left (0,1.5\right)\;=\;\frac{P^{3}\left (0,1.5\right)-c^{3}/2\times\left (Z\left (0,. 5\right)+Z\left (0,1\right)\right)}{1+c^{3}/2}$$
   - In general, for every i:
   $$Z\left (0, T_{i}\right)=\frac{P^{i}\left (0, T_{i}\right)-c^{i}/2\times\left (\Sigma_{j=1}^{i-1}\, Z\left (0, T_{j}\right)\right)}{1+c^{i}/2}$$
   - Example: suppose we have the following data:
   $$\begin{array}{ccccc}
   \hline \text { Maturity } & \text { Period } i & \text { Coupon } & \text { YTM } & \text { Price } \\
   \hline 0.5 & 1 & 0.000 & 0.080 & 96.15 \\
   1 & 2 & 0.000 & 0.083 & 92.19 \\
   1.5 & 3 & 0.085 & 0.089 & 99.45 \\
   2 & 4 & 0.090 & 0.092 & 99.64 \\
   2.5 & 5 & 0.110 & 0.094 & 103.49 \\
   3 & 6 & 0.095 & 0.097 & 99.49 \\
   3.5 & 7 & 0.100 & 0.100 & 100.00 \\
   \hline
   \end{array}$$
   
   - We find:
   $$\begin{array}{l l} {{Z\left(0,.5\right)\;=\;96.15;\qquad Z\left(0,1\right)=92.19;}} \\ {{}} \\ {{Z\left(0,1.5\right)\;=\;\frac{99.45-.0425\times\left(96.15+92.19\right)}{1.0425}=87.72;\ldots.}} \end{array}$$
   
   - Since
   
   $$Z\left (0, T_{i}\right)=\frac{100}{\left (1+\frac{r_{2}\left (0, T_{i}\right)}{2}\right)^{i}}\Longleftrightarrow r_{2}\left (0, T_{i}\right)=2\times\left (\left (\frac{100}{Z\left (0, T_{i}\right)}\right)^{\frac{1}{i}}-1\right)$$
   
   We Obtain
   $$

   \begin{array}{cccc}
   \hline \text { Maturity } & \text { Period } i & \text { YTM } & \text { Spot Yield } \\
   \hline 0.5 & 1 & 0.080 & 0.080 \\
   1 & 2 & 0.083 & 0.083 \\
   1.5 & 3 & 0.089 & 0.0893 \\
   2 & 4 & 0.092 & 0.09247 \\
   2.5 & 5 & 0.094 & 0.09468 \\
   3 & 6 & 0.097 & 0.09787 \\
   3.5 & 7 & 0.100 & 0.10129 \\
   \hline
   \end{array}

   $$
   ## CURVE FITTING
   
   - The above methodologies require that we have all the maturities available. 
   - Unfortunately, this is never the case. 
   - To avoid this problem, the profession moved to "curve fitting" in the following sense:
   1. Assume a flexible functional form for Z (0, T), such as (Nelson Siegel Model):
   $$Z\left (0, T_{j}\right)\;=\; 100\times e^{-r\left (0, T_{j}\right)\times T_{j}}$$
   
   $$r (0, T_{j})\;=\;\theta_{0}+(\theta_{1}+\theta_{2})\,\frac{1-e^{-\frac{T_{j}}{\lambda}}}{\frac{T_{j}}{\lambda}}-\theta_{2}e^{-\frac{T_{j}}{\lambda}}$$
   2. We can compute the "theoretical price" given Z (0, T)
   $$\widehat{P}\left (0, T_{j}\right)=\sum\limits_{i=1}^{j}c\left (T_{i}\right)\times Z\left (0, T_{i}\right)$$
   3. We estimate the parameters θ0, θ1, θ2, λ by **non-linear least squares**.
   That is, by minimizing
   $$\operatorname*{min}_{\theta_{0},\theta_{1},\theta_{2},\lambda}\sum_{j=1}^{n}\left (P\left (0, T_{j}\right)-\widehat{P}\left (0, T_{j}\right)\right)^{2}$$
   - There is a large literature on the [Functional Forms](Lecture%2010-%20Functional%20Forms.md) for the discount function
   Z (0, T), many of them relying on spline functions.
   - Next figure shows the difference between using bootstrapping technique and the
   Curve fitting technique
   
   ## ZERO-COUPON YIELD CURVES
![](Teaching%20Note%201%20Introduction%20To%20Fixed%20Income%20Securities-1.octet-stream)
   ![](Introduction%20To%20Fixed%20Income%20Securities-20240331152353486.png)
   
   - Clearly, the fitted curve is much smoother (by construction).
   - An important difference arises when we look at forward rates
   -    ![](Introduction%20To%20Fixed%20Income%20Securities-20240331152522582.png)"
```
