---
title: Teaching Notes 1
cssclasses:
  - academia
tags:
  - federal_reserve
  - fixed_income_securities
  - interest_rates
  - market_dynamics
  - treasury_bonds
aliases:
  - Debt Securities
  - Fixed Income
  - Teaching Notes 1
key_concepts:
  - Federal Reserve actions
  - Fixed income introduction
  - Government debt increase
  - Interest rate compounding
  - Mortgage-backed securities changes
  - Treasury bond behavior
  - U.S. debt overview
---

# Teaching Notes
# Introduction to Fixed Income Securities

# Introduction
- Several changes to fixed-income markets took place in the aftermath of the crisis
1. Many countries increased debt to “"stimulate" the economy.
- Lower tax revenues due to the economic downturn and higher government spending => large increase in government debt
1. The huge mortgage-backed securities market had several changes
- Fannie Mae and Freddie Mac went into conservator ship. Many mortgage companies disappeared. New regulation has been enacted.
1. Aggressive [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] has had large impact on Treasury bonds
- Federal Reserve slashed [[A Guide to the Front End and Basis Swap Markets#Federal Funds Market|Fed Funds Rate]] to zero
- Federal Reserve moved to "unconventional [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]]
1. Massive regulatory changes in derivative markets
Central counter parties (CCP - Impact on pricing of derivatives.
1. Dramatic change in behavior of Treasury bonds
- From positive beta to negative beta securities
- Negative rates in many periods
# The Outstanding Amount U.S. Debt

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/0e98342aeebdbcbf4c3c5d40b5b8024bc83ba4bd7d152a058300e197a2d098a5.jpg)

PanelA. Billions of US Dollars

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/223e187f64dc20a2341da1c355d243bc9fc328dcb0b21e0d3f386739fe8308ca.jpg)

Panel B. Percentage of US GDF (Source: SIFMA and FRED at Federal Reserve of St. Louis.)

# Federal Funds and U.S. Treasury Yields

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/00d4bfb06d8ddf5c00ff6ab3e7edb27588cef7698afaca1686546234288efac1.jpg)

PanelA. Federal Funds Effective Rate

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/88f5abe0103ba857c48a6b1a50f244f89445a3d2c076f618e5255f63c5dde492.jpg)

Panel B. Zero-Coupon Bond Yields (Data: Yields up to 5 years are from CRSP. Yields from 10 to 30 are from Gurkaynak,  Sack,  and Wright (2007),  updated series. )

# The Notional Amount of Over-the-Counter Derivatives

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/dcf309ded8027b1df718b626b3b31dfc98b863aa3cf8a46d15fc651804b93fb3.jpg)

Panel A. Millions of US Dollars

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/55a51c9ecf78e1395d2d81af3c54294a247f760e83f356bf083e9988a62badba.jpg)

Panel B. Multiple of Global GDP

# The Changing Beta of U.S. Treasury Bonds

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/d7d3f5985914a6b995abfe4a1405eba23d622d547c9e4d8201ec79c505fe3e58.jpg)

Stock Bond Covariance (Stock data are from CRSP. 5-year zero-coupon bond data are from Gurkaynak,  Sack,  and Wright (2007,  updated series)

Bond Beta

# The Yields of German Treasury Bonds

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/4c0735bef5b9f6f3fa493afc4a83948241d5f8da999e1473ed943de398e4826b.jpg)

(Data: Bloomberg)

# U.S. Treasury Bills,  Notes,  and Bonds
- U.S. Government issues various kinds of debt securities
1. Treasury Bills: Zero coupon securities with maturity up to one year 2. Treasury Notes: Fixed coupon bonds with maturity up to 10 years 3. Treasury Bonds: Fixed coupon bonds with maturity of 30 years 4. Treasury Inflation-Protected Securities (TIPS): Floating coupon bonds indexed to inflation 5. Floating Rate Notes (FRNs): Floating coupon bonds,  with coupon indexed to T-Bill rates
# Marketable U.S. Treasury Securities (million of dollars) December 31,  2021

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/5cf7701c68e2e03c358db5269b9aed76da99faf0cb849d8ca3e1152c07a427bf.jpg)

Source: U.S. Treasury web site. https://www.treasury direct. Gou

# Interest Rates and Compounding Frequency
- The concept of interest rates is ubiquitous to fixed income securities.
- Problem: An interest rate is not well defined without a compounding frequency -Example: A \$100 investment at $10\%$ interest rate over 10 years has payoffs:
Annual $\begin{array}{r l r}{\mathsf{c o m p o u n d i n g:}\quad}&{{}\mathbb{S}100\times\left(1.1\right)^{10}}&{=\mathbb{S}259.37}\\ {\mathsf{c o m p o u n d i n g:}\quad}&{{}\mathbb{S}100\times\left(1.05\right)^{20}}&{=\mathbb{S}265.33}\\ {\mathsf{c o m p o u n d i n g:}\quad}&{{}\mathbb{S}100\times\left(1.025\right)^{40}}&{=\mathbb{S}268.51}\\ {\mathsf{c o m p o u n d i n g:}\;\,         \mathbb{S}100\times\left(1+\frac{0.1}{365}\right)^{10\times365}}&{=\mathbb{S}271.79}\\ {\mathsf{c o m p o u n d i n g:}\quad}&{{}\mathbb{S}100\times e^{0.1\times10}}&{=\mathbb{S}271.82}\end{array}$ Semi-annual Quarterly Daily Continuous
The general formula to compound $n$ times over the horizon $T$ is
$$
V=\left(1+\frac{r}{n}\right)^{n\times T}
$$  

For $n$ large,  we converge to continuous compounding

$$
V=\left(1+{\frac{r}{n}}\right)^{n\times T}\longrightarrow e^{r\times T}
$$  
# Discounting

Discounting is opposite process from the previous one.

- The question is: "what is the amount we have to invest today to have \$1 dollar in the future,  given a rate $r$ compounded $n$ times per year?"
Inverting the relation above,  we obtain
$$
Z(T)=\frac{1}{\left(1+\frac{r}{n}\right)^{n\times T}}
$$  
- In the limit as $n\rightarrow\infty$ we obtain the usual continuous compounding formula
$$
Z(T)={\frac{1}{\left(1+{\frac{r}{n}}\right)^{n\times T}}}\longrightarrow Z(T)=e^{-r T}
$$  
# Discounts and Rates
- Note that the compounding frequency is mostly a convention
The key question is:
"How much are investors willing to pay today to have \$1 at T"
Such price,  $Z(T)$ ,  is always well defined.
 - Given $Z(T)$ ,  we can derive the rate $r_{n}$ for any given compounding frequency ni
$$
r_{n}=n\times\left(\frac{1}{Z(T)^{\frac{1}{n T}}}-1\right)
$$  
- The continuously compounded rate is instead
$$
r=-{\frac{1}{T}}\log\left(Z(T)\right)
$$  
# The Term Structure of Interest Rates
- When we discount future cash flows to the present,  different discount rates apply for different maturities.
- We denote the discount factor at $t$ for a dollar to be received at time $T$ by
$$
Z(t,         T)=e^{-r(t,         T)(T-t)}
$$  
- r (t,  T) = continuously compounded yield at $t$ for an investment up to $T$
We put two "time" indices:
1. $t=$ calendar time when the discounting is made (e.g. 1/31/2007,  etc.) 2. $T=$ maturity date. $\implies T-t=\mathsf{t i m e\;t o\;m a t u r i t y}$
 - Panel A of next figure shows $Z(t,         T)$ for $t=1/31/2007,         1/31/2008,         …,         3/20/2020,         $ andfor $T-t$ ranging from 0 to 30 years
 - Panel B of next figure shows the corresponding yields $r(t,         T)$
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/42fbe45b23fdf7c59a769f13205e1ef1a00af9553f13131f796e75cbebe579c8.jpg)
Panel A. Zero Coupon Bonds (Data are from Girkaynak,  Sack,  and Wright (2007),  updated series.)
# Panel B. Yield Curves

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/803b54810385b44646c671eeb9e533c64a0d7c054463d0203dcacb70d724ce63.jpg)

(Data are from Girkaynak,  Sack,  and Wright (2007),  updated series.)

# Yield Curves

Yield curves change a lot over time.

They also have many shapes: -Flat (e.g. 1/31/2007) - Increasing (e.g. 1/30/2015) - Hump (e.g. 1/31/2009) - Inverted hump (slightly,  1/31/2007) \* What generates the shape of the term structure of interest rates? \* What does it imply for derivative pricing etc?

- Indeed,  there is much variation not only in level but in slope of the yield curve
- What do these variations tell us about investors' beliefs about future rates?
 - What do they tell us about risk premia required to hold bonds?
# Zero-Coupon Bond Yields

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/cf87b0c085a2e5b586140ada3a9103ab5ca8797c446650ed5f69a9dc5655e304.jpg)

(Data: Yields up to 5 years are from CRSP. Yields from 10 to 30 are from Gurkaynak,  Sack,  and Wright (2007),  updated series. )

# Coupon Bonds

What is the price of coupon bond?

·A coupon bond is just a sequence of cash payments $c/2$ (coupons) for dates $T_{\mathrm{1}},         T_{\mathrm{2}},         …,         T_{n}$ and one big payment of $100+c/2$ (principal) at $T_{n}\ (={\mathsf{m a t u r i t y\ o f}}$ the bond).

 - If we know the time value of money for each maturity,  that is,  the discount function $Z\left(t,         T_{i}\right)$ for all maturities $T_{i}$ 's,  a simple no arbitrage argument implies

Coupon Bonds Pricing Formula and No Arbitrage Argument
A coupon bond represents a sequence of cash payments known as coupons, with each payment typically being $c/2$ for specific dates $T_1, T_2, ..., T_n$. At maturity, $T_n$, there is an additional payment of $100 + c/2$, representing the principal and the final coupon.

To determine the price of such a coupon bond, we use the discount function $Z(t, T_i)$, which represents the time value of money for each maturity $T_i$. The pricing formula for a coupon bond without arbitrage implies:

$$
T_n = \frac{c}{2} \times Z(t, T_1) + \frac{c}{2} \times Z(t, T_2) + \ldots + (1) \
= \sum_{i=1}^{n} \left(\frac{c/2}{\left(1 + \frac{r_2(t, T_i)}{2}\right)^{2 \times (T_i - t)}} + \frac{1}{\left(1 + \frac{r_2(t, T_i)}{2}\right)^{2 \times (T_i - t)}}\right)
$$

Arbitrage Argument
If the market price of a bond is trading at par (e.g., $100) but the right-hand side of the equation sums to $105, there exists an arbitrage opportunity. An arbitrageur can purchase the bond for $100 and sell each cash payment or strip for a total of $105, yielding a profit of $5. This scenario illustrates perfect matching of cash flows, which constitutes a risk-free profit, hence an arbitrage opportunity.

Simplification for Semi-Annual Maturities
When $t = 0$ and $T_i$ are exact semi-annual maturities (e.g., $T_1 = 0.5$, $T_2 = 1$, $T_3 = 1.5$, etc.), the formula simplifies as follows:

$$
P(0, T_n) = \sum_{i=1}^{n} \frac{c/2}{\left(1 + \frac{r_2(0, T_i)}{2}\right)^i} + \frac{100}{\left(1 + \frac{r_2(0, T_n)}{2}\right)^i}
$$

The simplification occurs because $2 \times T_i = i$ for each $i = 1, ..., n$.

Market Conventions and Terminology
Understanding market conventions is crucial for accurate bond pricing and trading:
Accrued Interest: Quoted bond prices often exclude accrued interest, known as clean prices. Accrued interest is calculated as:
$\text{Accrued Interest} = \frac{\text{Interest Due in Full Period} \times \text{Number of Days Since Last Coupon Date}}{\text{Number of Days between Coupon Payments}}$
Invoice Price: Also known as the dirty price, it is the actual payment including accrued interest.
Day Count Conventions: Methods for counting days differ based on the security:
Actual/Actual: Counts the actual number of calendar days.
30/360: Assumes 30 days in a month and 360 days in a year.
Actual/360: Counts actual days per month but assumes 360 days in a year.

Choosing the correct day count convention depends on the specific security in question.

What is the arbitrage argument?

# Coupon Bonds
- Suppose that the price of the bond is trading at par (100) but the right-hand side is 105.
- Then an arb it rage ur can buy the bond (pay 100) and sell the strips (each cash payments) for a total of 105,  thereby making \$5 (million). Since there is perfect matching of cash flows in the future,  the trade is an arbitrage.
- Incidentally,  notice that if $t=0$ and $T_{i}$ are exact semi-annual maturities,  that is $T_{1}=0$ , $T_{2}=1$，$T_{3}=1.5$ etc.,  then we have $2\times T_{i}=i$ for every $i=1,..,n,$ and thus the formula reduces to
$$
\left0.\1,         T_{n}\right)=\sum_{i=1}^{n}\frac{c/2}{\left(1+r_{2}\left(0,         T_{i}\right)/2\right)^{i}}+\frac{100}{\left(1+r_{2}\left(0,         T_{n}\right)/2\right)^{i}}
$$  
# Conventions and Terminology

It is important to spend a few words on some market conventions and terminology

# Accrued Interest
- The market prices of bonds quoted in newspapers are clean prices. That is,  they are quoted without any accrued interest. - The accrued interest is the amount of interest that has built up since the last coupon payment.
Accrued Interest $=$ Interest Due in the Full Period X
Number of Days Since Last Coupon Date Number of Days between Coupon Payments
- The actual payment is called invoice price (or dirty price)
# Day Count Conventions

How do we count days? Three main ways
1. Actual/Actual: Simply Count the number of calendar days; 
2. 30/360: Assume there are 30 days in a month and 360 in a year; 
3. Actual/360: Each month has the right number of days,  but there are only 360 days in a year. Which convention it is used depend on the security considered.
	1. Treasuries use Actual/Actual.
# Discount yield and Bond Equivalent Yield

 - T-bills are quoted on a discount yield $d$ basis. That is,  the quote reports a yield.  - If $n$ is the number of days to maturity,  the price of the T-bill is

$$
P=100\times\left[1-{\frac{n}{360}}\times d\right]
$$  

In other words

$$
d=\frac{100-P}{100}\times\frac{360}{n}
$$  

 - Instead,  it should be

$$
B E Y={\frac{100-P}{P}}\times{\frac{365}{n}}
$$  

BEY = Bond Equivalent Yield Of course,  we obtain

$$
B E Y={\frac{365\times d}{360-d\times n}}
$$  
# Yield-to-Maturity (or internal rate of return
- Given price $P\left(t,         T\right)$ and cash flows $c/2$ at $T_{i}^{\,         \prime}$ s for $i=1,         ..,         n$ ,  and $1+c/2$ at $T_{n}$ the (semi-annually compounded) yield-to-maturity YTM is defined as that rate $y$ such that
$$
P\left(t,         T_{n}\right)=\sum_{i=1}^{n}{\frac{c/2}{\left(1+{\frac{y}{2}}\right)^{2\times(T_{i}-t)}}}+{\frac{100}{\left(1+{\frac{y}{2}}\right)^{2\times(T_{n}-t)}}}
$$  

Recall that given the spot curve $r_{2}\left(t,         T_{i}\right)$ ,  we also had

$$
T_{n})=\sum_{i=1}^{n}{\frac{c/2}{\left(1+r_{2}\left(t,         T_{i}\right)/2\right)^{2\times\left(T_{i}-t\right)}}}+{\frac{1}{\left(1+r_{2}\left(t,         T_{i}\right)/2\right)^{2\times\left(T_{i}-t\right)}}}
$$  

What's the difference?

-The yield to maturity $y$ is a sort of average discount rate that characterizes one particular bond,  and it is used to discount the cash flows of that particular bond.

- Notice that two different bonds with same maturity,  will have different yield to maturities if they have different coupons.
# Yield-to-Maturity

We will almost never use YTM

- It is blatantly wrong as a measure of yield,  as it assumes that all the coupons can be reinvested at the constant y throughout the life of the bond.
- That is: not only it assumes a flat yield curve,  but also one that does not move overtime.
Example: consider the following data:
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/5410c643e3e1f3d88bd1a0ecd4afea2c321746f060e4a6d96ed78323c1ca871e.jpg)
What is the most attractive bond?
# Yield-to-Maturity

Judging from the Yield-to-Maturity,  bond 3 looks great

- However,  it is dominated by a combination of 1 and 2,  as we can mimic exactly its cash flows and find a (slightly) lower price
-Let $N_{1}$ and $N_{2}$ ,  be the number of the first and the second coupon bonds -Then
$$
\begin{array}{c}{{N_{1}\times9+N_{2}\times10\,         =\,         3}}\\ {{N_{1}\times109+N_{2}\times110\,         =\,         103}}\end{array}
$$  
-Solving the system $\Longrightarrow$ the portfolio long $N_{1}=7$ units in bond 1 and short of $N_{2}=-6$ units bond 2 mimics exactly the cash flows of bond 3.
- The value of this portfolio is $N_{1}\times98.57+N_{2}\times100.34=87.95<88.$ - The YTM of the portfolio is even bigger: $\mathsf{Y T M}{=}9.94\%$
# Yield to Maturity

Why is this happening?

- The YTM measures the average return on the bond under the assumption that all coupons are reinvested at the same rate $y$
- With a non-flat term structure,  this is simply not going to happen and using YTM for relative pricing yields bad results
- The low coupon in bond 3 together with the fact that we cannot re-invest at the highrateof $9.91\%$ for the whole life of the bond yields the implication that the third bond is "no better" than a portfolio of the other two (which have lower YTMs).
# Floating Rate Notes
- Floating rate notes are securities whose coupon is not fixed,  but it depends on realized short-termrates $r_{t}$
一 If $r_{t}$ increases => coupon increases. And vice versa.
   - The U.S. Treasury started issuing floating rate notes (FRN) in January 2014
 - They pay quarterly coupons using the 13-week U.S. T-bill rate as a reference rate,  plus a spread determined at the auction of the FRN.
 - Let $T_{\mathrm{1}},         \,         T_{\mathrm{2}},         \,         …,         \,         T_{n}$ denote the coupon payment dates,  with $T_{i+1}=T_{i}+0.25$
 - Then the (annualized) coupon rate at time $T_{i}$ isgivenby
$$
c(T_{i})=r(T_{i-1})+\mathsf{s p r e a d}
$$  

 - where $r(T_{i-1})$ is the quarterly compounded,  (annualized) three-month rate

# Floating Rate Notes: Pricing
- How do we price a security with unknown future coupons?
 - We can use a recursive argument. Let's start with a spread = 0
 - Let Tn = maturity date,  where $n$ is the total number of coupon payments
Suppose that today is actually $T_{n-1}$
$-\Longrightarrow$ Today we know the reference rate $r(T_{n-1})$ and hence
$$
T_{n}=1+\frac{1}{4}c(T_{n})=1+\frac{1}{4}r(T_{n-1})
$$  

 - The value of FRN at $T_{n-1}$ is

$$
{\frac{{\mathsf{C a s h~f l o w~a t~}}T_{n}}{1+{\frac{1}{4}}r(T_{n-1})}}={\frac{1+{\frac{1}{4}}c(T_{n})}{1+{\frac{1}{4}}r(T_{n-1})}}={\frac{1+{\frac{1}{4}}r(T_{n-1})}{1+{\frac{1}{4}}r(T_{n-1})}}
$$  
# Floating Rate Notes: Pricing (cntd.)
- Consider now the value of the FRN at $T_{n-2}$
- At this time,  the investor knows that the FRN will $c(T_{n-1})=r(T_{n-2})$ at $T_{n-1}$ and that its price will revert to $P^{F R N}(T_{n-1})=1$
The FRN value at $T_{n-2}$ is then
$$
r_{n-2})\;=\;{\frac{P^{F R N}(T_{n-1})+{\frac{1}{4}}c(T_{n-1})}{1+{\frac{1}{4}}r(T_{n-2})}}={\frac{1+{\frac{1}{4}}r(T_{n-2}}{1+{\frac{1}{4}}r(T_{n-2}}}
$$  

 - Using the same logic for every reset time $T_{i}\colon\Longrightarrow P^{F R N}(T_{i})=1$

 - Outside reset times,  the price of FRN is different from 1

 - Let $t$ be such that $T_{i-1}<t<T_{i}$ . Then,  the value at $t$ of FRN is

$$
P^{F R N}(t)\;=\;Z(t,         T_{i})(1+r(T_{i-1})/4)
$$  
- Adding a spread to the coupon payments is simple because the spread is constant. Use discounts $Z(t,         T)$ to compute its value
# Repurchase Agreements
- [[Class Note 12 Part 2 Repos|repurchase agreements]] (Repo): Agreement to sell some securities to another party and buy them back at a fixed date and for a fixed amount.
- The price at which the security is bought back is greater than the selling price and the difference implies an interest rate called Repo Rate - A Reverse Repo is the borrowing of a security for a short period at an agreed interest rate.
- The Repo Market is the single most important source of financing for government dealers.
- Since government securities are liquid and default free,  they are excellent collateral. - Dealers can borrow money on a collateralized basis,  so that they can take huge positions even with limited capital. - The Repo Market grew very large. Next table shows the average daily amount outstanding
# Financing by U.S. Government Securities Dealers

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/eb3a1237da1e18f8c51e03d3870bcebf65b78e9e61e69d4a1398a8693436a20c.jpg)

Average Daily Amount Outstanding (\$ Billions) (Source: SIFMA http:/ / www.sifma.org/research/statistics.aspx )

# Bilateral Repurchase Agreements
- A Repo transaction is as follows: Consider a trader and a repo-dealer. The trader attime $t$ wants to take a long position until time $T$ (typically,  overnight!) Then
# Schematic Repo Transaction

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/686d44286c69b7a8a81153cdc1a416e20b3ffab56c7640b36b2fe5008038ef63.jpg)

# Repurchase Agreements
1. At time $t$ ,  the trader buys the bond at market price $P_{t}$ and enters into aRe po with the Repo Dealer. Hence,  the trader delivers the bond as collateral to the repo-dealer and gets the cash to purchase the bond.
- The Repo Dealer typically gives something less than the market price of the bond. The difference is called hair cut. ·The term $T$ is decided at time $t$ : Most [[Class Note 12 Part 2 Repos|repurchase agreements]] are for a very short term (overnight). Some longer term agreements reach 30 days or more.  - The Repo rate is decided at time $t$
1. Attime $T$ ,  the trader gets back the bond from the Repo Dealer,  sells the bond in the market to get $P_{T}$ andpays $P_{t}$ plus the repo rate to the dealer.
-The profit is then $\begin{array}{r}{P_{T}-P_{t}\mathrm{{-}r e p o\r a t e\!\times\!\frac{\partial}{\partial60}\times(P_{t}-\mathsf{h a i r c u t})}.}\end{array}$ - Hence,  the return on capital to the trader is
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/12196b401180ad87a712f040742963ff20921dae7abaa85c0e3ae097cd316053.jpg)
# Repurchase Agreements

·Between $t$ and $T$ the trader earns the accrued interest on the bond

- Positive Carry: If accrued interest > repo rate - Negative Carry: If accrued interest $<$ repo rate.
- Other important definitions/characteristics of Repo markets.
1. General Collateral Rate (GCF): This is the Repo Rate on most Treasury securities. Hence,  using one or another of these as collateral makes little difference in terms of costs.
1. - In a reverse repo,  the trader (A) borrows the security from the repo dealer; (B) sells it; and (C) posts cash collateral with the dealer. - The trader is lending money to the dealer against the bond collateral => the trader would be entitled to the repo rate. - However,  the trader is happy to forgo part (all) of the repo rate in order to get hold of the bond (to sell)
# Reverse Repo Transaction

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/f2fccebcd2677dd0be2aea7e5a31d113e1584a76f93876d8725b2f0c71f5982f.jpg)

$$
\mathsf{P r o f i t}=(P_{t}-P_{T})+P_{t}\times\mathsf{r e p o\r a t e}\times\frac{n}{360}
$$  
# Tri-Party Repo
- Based on clearing and settlement infrastructure supported by Bank of New York Mellon and JPMorgan Chase
- Banks provide collateral valuation,  margining,  and management services to facilitate trading.
- Collateral allocation: automatically selects securities from cash borrower's inventory.
- General Collateral Finance (GCF): cleared through the Fixed Income Clearing Corporation (FICC) GCF repo service. Mostly inter-dealer.
- Ex-GCF: Not cleared through FlCC. Institutional investors such as [[A Primer on Money Market Mutual Funds|money market funds]] lending to broker-dealers
## Forward Rates
- A forward rate determined at time $t$ is the rate implicit in the current spot rate function for an investment in T-bills made at date $T_{1}$ with maturity date $T_{2}$ $(>T_{1})$.
- There are three "dates" in the forward rate:
	- Today $(t)$
	- The first maturity at which the investment is made $\left(T_{1}\right)$
	- The final maturity of the investment $\left(T_{2}\right)$
		- With semiannual compounding, we denote it $f_{2}\left(t, T_{1}, T_{2}\right)$.
		- With continuous compounding, we denote it $f\left(t, T_{1}, T_{2}\right)$.
- How do we determine the forward rates?
	- By no arbitrage.
- Suppose today is $t=0$ and that I have \$10 million to invest for 1 year.

Forward Rates
We have the following two strategies:
Invest in a 1-year zero coupon bond, obtaining at maturity
$$
$10\ \text{million}\times\left(1+r_{2}\left(0, 1\right)\big/2\right)^{2}
$$
Invest in a 6-months zero coupon bond and enter (today) into a forward contract to invest the proceeds at $T_{1}=0.5$ until $T_{2}=1$ for a rate $f_{2}\left(0, 0.5, 1\right)$. At maturity we have
$$
$10\ \text{million}\times\left(1+r_{2}\left(0, 0.5\right)\big/2\right)\times\left(1+f_{2}\left(0, 0.5, 1\right)\big/2\right)
$$
By no arbitrage (and if credit risk is negligible) we must have
$$
\frac{\left(r_{2}(0, 1)\right)}{2}^{2} = \$10\ \text{million} \times \left(1 + \frac{r_{2}(0, 0.5)}{2}\right) \times \left(1 + \frac{f_{2}}{2}\right),
$$
Or
$$
1+\frac{f_{2}\left(0, 0.5, 1\right)}{2}=\frac{\left(1+r_{2}\left(0, 1\right)\big/2\right)^{2}}{\left(1+r_{2}\left(0, 0.5\right)\big/2\right)}
$$

By using the price of bonds we have
$$
1+\frac{f_{2}\left(0, 0.5, 1\right)}{2}=\frac{Z(0, 0.5)}{Z(0, 1)}
$$
More generally, for every $T_{1}$ and $T_{2}$, consider the following strategies:
Invest in a $T_{2}$ -zero coupon bond, obtaining at maturity
$$
\frac{$10\ \text{million}}{Z(0, T_{2})}
$$
Invest in a $T_{1}$ -zero coupon bond and enter (today) into a forward contract to invest the proceeds at $T_{1}$ until $T_{2}$ at the $n$ -times compounded forward rate $f_{n}\left(0, T_{1}, T_{2}\right)$ . At maturity we have
$$
\frac{$10\ \text{million}}{Z(0, T_{1})}\times\left(1+\frac{f_{n}\left(0, T_{1}, T_{2}\right)}{n}\right)^{n(T_{2}-T_{1})}
$$

We then obtain

$$
\left(1+{\frac{f_{n}\left(0, T_{1}, T_{2}\right)}{n}}\right)^{n(T_{2}-T_{1})}={\frac{Z(0, T_{1})}{Z(0, T_{2})}}
$$

Continuously Compounded Forward Rates
Taking the limit as $n\to\infty$, the continuously compounded forward rate is

$$
\begin{array}{l}
f(0, T_{1}, T_{2}), =, \displaystyle\frac{\ln(Z(0, T_{1})), -\ln(Z(0, T_{2}))}{T_{2}, -, T_{1}} \
\qquad\qquad, =, \displaystyle\frac{r(0, T_{2})T_{2}, -, r(0, T_{1})T_{1}}{T_{2}, -, T_{1}}
\end{array}
$$

Another concept, that we will use later, is that of instantaneous forward rate. We can rewrite (2) as (exercise: do it!)

$$
f(0, T_{1}, T_{2})=r(0, T_{1})+T_{2}\times{\frac{r(0, T_{2})-r(0, T_{1})}{T_{2}-T_{1}}}
$$
If we take the limit $T_{2}, \longrightarrow, T_{1}$ (that is, the horizon of the forward contract shrinks to zero), we obtain
$$
f(0, T_{1}, T_{1})=r(0, T_{1})+T_{1}\times{\frac{d r(0, T_{1})}{d T_{1}}}
$$

The Relation between Forward Curve and Spot Curve
The equation for the instantaneous forward curve (4) reveals an interesting (important) property of the forward-spot relationship. We can rewrite
$$
f(0, T_{1}, T_{1})-r(0, T_{1})=T_{1}\times\frac{d r(0, T_{1})}{d T_{1}}
$$

If $$\begin{array}{}
\frac{d r(0, T_{1})}{d T_{1}}>0\implies\text{forward curve is above the spot curve} \\
\frac{dr(0, T_{1})}{d T_{1}}<0\implies\text{forward curve is below the spot curve} \\
\frac{dr(0, T_{1})}{d T_{1}}=0\implies\text{forward curve intersects the spot curve}
\end{array})$$

# Spot Curve and Forward Curve

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/11e1b0cbaddd0a22c8edc1144ab3b8e63b03fd469bd141652224cf8d30b08f40.jpg)

- To obtain the forward curve we need a smooth yield curve
# Estimating the Zero-Coupon Discount Function

. There are several methods to extract the zero-coupon discount curve $Z\left(0,         T\right)$ from bond data.

Why do we want to do that?

1. The discount function $Z\left(0,         T\right)$ determines the time value of money. We need it as a basis to discount future (riskless) cash flows. 2. We cannot observe it: it is implicitly embedded in traded Treasury coupon bonds. 3. You need it to compute forward prices,  for instance,  as well as Swaps (see later). 4. It will be the basis of all future term structure models: it is typically the first step to then calibrate term structure models. The latter are what traders use to (a) Price new securities by no arbitrage (we will see many). (b) Spot out arbitrage opportunities
- The most "famous" is the boots trapping methodology
# Bootstrap
- Suppose we have $n$ coupon bonds. Each bond $i$ has a coupon equal to $c^{i}$ - Recall the pricing equation for coupon bonds with maturity $T_{i}$ is equal tc
$$
P^{i}(t,         T_{i})=\frac{c^{i}}{2}\sum_{j=1}^{i}Z(t,         T_{j})+1\times Z(t,         T_{i})
$$  

 - Today is $t=0$ and that we have data on maturities $T_{j}=0,1,         \,         1,         \,         1.5,         ….T_{n}.$ ·Inverting (5),  we obtain

$$
Z\left(0,         0.5\right)\,         =\,         \frac{P^{1}\left(0,         0.5\right)}{1+c^{1}/2}
$$  
$$
Z\,         (0,         1)\,         =\,         \frac{P^{2}\,         (0,         1)-c^{2}/2\times Z\,         (0,         0.\1)}{1+c^{2}/2}
$$  
$$
\vert,         1.5\rangle\,         =\,         \frac{P^{3}\left(0,         1.5\right)-c^{3}/2\times\left(Z\left(0,         0.\1\right)+Z\left(0,         1\right)\right.}{1+c^{3}/2}
$$  

In general,  for every i:

$$
Z\left(0,         T_{i}\right)=\frac{P^{i}\left(0,         T_{i}\right)-c^{i}/2\times\left(\Sigma_{j=1}^{i-1}Z\left(0,         T_{j}\right)\right)}{1+c^{i}/2}
$$  

Example: suppose we have the following data:

 ![400](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/ece1bac5b5ee3ef853e89b10b5c60ef7c3ff90f5557f003f6b4ba46a39bc6dfa.jpg)

We find:

$$
Z\left(0,         1\right)=92.19;
$$ since
$$
={\frac{100}{\left(1+{\frac{r_{2}(0,         T_{i})}{2}}\right)^{i}}}\Longleftrightarrow r_{2}\left(0,         T_{i}\right)=2\times\left(\left({\frac{100}{Z\left(0,         T_{i}\right)}}\right)\right.
$$  

We obtain

 ![400](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/28d9c48e0735b28eabeb16dc240062f0b5b9e2123c1a3932bd15922341cdef76.jpg)

# Curve Fitting

The above methodologies require that we have all the maturities available

Unfortunately,  this is never the case.

 - To avoid this problem,  the profession moved to "curve fitting" in the following sense:

1. Assume a flexible functional form for $Z\left(0,         T\right)$ ,  such as (Nelson Siegel Model): $Z\left(0,         T_{j}\right)\:=\:100\times e^{-r\left(0,         T_{j}\right)\times T_{j}}$
$$
r(0,         T_{j})\;=\;\theta_{0}+(\theta_{1}+\theta_{2})\,         \frac{1-e^{-\frac{T_{j}}{\lambda}}}{\frac{T_{j}}{\lambda}}-\theta_{2}e^{-\frac{T_{j}}{\lambda}}
$$  
1. We can compute the "theoretical price" given $Z\left(0,         T\right)$
$$
\widehat{P}\left(0,         T_{j}\right)=\sum_{i=1}^{j}c\left(T_{i}\right)\times Z\left(0,         T_{i}\right)
$$  
1. We estimate the parameters $\theta_{0},         \;\theta_{1},         \;\theta_{2},         \;\lambda$ by non-linear least squares That is,  by minimizing
$$
\operatorname*{min}_{\theta_{0},         \theta_{1},         \theta_{2},         \lambda}\sum_{j=1}^{n}\left(P\left(0,         T_{j}\right)-\widehat{P}\left(0,         T_{j}\right)\right)^{2}
$$  

 - There is a large literature on the functional forms for the discount function $Z\left(0,         T\right)$ ,  many of them relying on spline functions.

- Next figure shows the difference between using boots trapping technique and the curve fitting technique
# Zero-Coupon Yield Curves

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/b48444d1b31bb764450eae432c3cf4b7d42843073986996341a521d8afc0ef1c.jpg)

- Clearly,  the fitted curve is much smoother (by construction).
 - An important difference arises when we look at forward rates
# Forward Curves

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/653075e507f7b5f2fb536597b550ff113b33be1e4bc5e7b00bed74fc65dbc651.jpg)

# Interest Rate Risk Management and Factors

# Interest Rate Risk Management
# - Interest rates vary quite dramatically over time

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/d0ef9916b941c2c72f569831cfae026510ccb1755674b8a3401752a1efa9df40.jpg)

(Data: Yields up to 5 years are from CRSP. Yields from 10 to 30 are from Gurkaynak,  Sack,  and Wright (2007),  updated series.)

# Interest Rate Risk Management
# And so do bond prices
# The Life Cycle of a 30-year Bond

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/93255cfd9a6bf82eb89448ee8a9b0dc470bab9172433e9c2b5ddd5a4d21b24b3.jpg)

Source: CRSP

# Interest Rate Risk Management: Duration
- The duration of a security is defined as the sensitivity of the security's price to small,  uniform changes in the yield curve.
 - Traditionally,  the duration is defined with respect to changes in yield-to-maturity.
 - However,  it is convenient to introduce it using the continuously compounded yield $r(t,         T)$ ,  as formulas are easier and the interpretation is also easier.
 - The duration of an asset is its sensitivity to small,  uniform changes in $r(t,         T)$
- That is,  the change in the security's price when we apply a uniform increment dr" to the yield curve $r(t,         T)$ ,  to get $r(t,         T)+d r$
- Hence,  we define the duration of a security with price $P$ by
$$
D_{P}=-\frac{1}{P}\frac{d\mathrm{~}P}{d\mathrm{~}r}
$$  
- This definition is all you need to remember,  as everything follows from here
# Example: Duration of a Zero Coupon Bond
- Consider a zero coupon bond with time to maturity $T$ and price $Z(t,         T)$ .By applying the definition we have:
$$
\begin{aligned}

    D_{Z, T} &= -\frac{1}{Z(t, T)} \frac{d Z(t, T)}{d r} \\

    &= -\frac{1}{Z(t, T)} \times \left[-(T - t) \times e^{-r(t, T) \times (T - t)}\right].

\end{aligned}
$$  
$$
\begin{array}{l}{\displaystyle=\,         -\frac{1}{Z(t,         T)}\times\left[-(T-t)\times Z(t,         T)\right]}\\ {\displaystyle}\\ {\,         =\,         T-t}\end{array}
$$  
- The duration of a zero coupon bond is simply equal to its time to maturity $T-t$
# Duration of a Portfolio of Securities
- We now show that the duration of a portfolio of securities is just the weighted average of the durations of the singles securities (where the weights are the relative holdings).
- Suppose we have $N_{1}$ units of security 1 and $N_{2}$ of security 2. Let $P_{1}$ and $P_{2}$ be the prices of the two securities and $D_{1}$ and $D_{2}$ their durations,  respectively.
Let HI be the value of the portfolio
$$
\Pi=N_{1}P_{1}+N_{2}P_{2}
$$  

We can then compute:

$$
D_{\Pi}\;=\;-\frac{1}{\Pi}\frac{d\;\Pi}{d\;r}
$$  
$$
=\,         \frac{1}{\Pi}\left(-N_{1}\times\frac{d P_{1}}{d r}-N_{2}\times\frac{d P_{2}}{d r}\right)
$$  
$$
=\,         {\frac{1}{\Pi}}\left(N_{1}P_{1}\times(-1){\frac{1}{P_{1}}}{\frac{d P_{1}}{d r}}+N_{2}P_{2}\times(-1){\frac{1}{P_{2}}}{\frac{d P_{2}}{d r}}\right.
$$  
# Duration of a Portfolio of Securities

Obtaining

$$
D_{\Pi}\,         =\,         w_{1}D_{1}+w_{2}D_{2}
$$  

Where

$$
w_{i}=\frac{N_{i}P_{i}}{\prod}
$$  
- Clearly,  the same derivation can be applied for any number of assets
# Example: Duration of a Coupon Bond
- We know a bond is equivalent to a portfolio of zero-coupon bonds
$$
\begin{array}{r}{P(0,         T)=\underset{i=1}{\overset{n}{\sum}}\,         c(T_{i})Z(0,         T_{i})}\end{array}
$$  

where $c\left(T_{i}\right)=c/2$ for $i<n$ and $c\left(T_{n}\right)=c/2+100.$

Step 1: Apply (2) to have

$$
w_{i}=\frac{c(T_{i})Z(0,         T_{i})}{P(0,         T)}
$$  
# Example: Duration of a Coupon Bond

Step 2: Use (1)

$$
D\;=\;-\frac{1}{P(0,         T)}\frac{d P(0,         T)}{d r}=\sum_{i=1}^{n}w_{i}D_{Z,         T_{i}}=\sum_{i=1}^{n}w_{i}
$$  
- The duration of a Coupon Bond is a weighted average of times to maturity
- From (3),  we can compute the percentage change in the bond due to a small parallel shift in the yield function $r(t,         \tau)$ as
$$
{\frac{d P}{P}}\approx-D\times d r
$$  
- Hence,  if we hold a portfolio of 10-year at-par coupon bonds with duration equal to 5,  we know that a one-basis point increase in the yield function $(d r=0.\1\%)$ is going to change the value of the bond approximately by - $$
- 5 \times \frac{0.01}{100} \times 5 \, \text{million (par amount)} = -\$50,000
$$
# Bond Price Approximation with Duration

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/4f31fdf4c3044fd403dd83d917cfd96a298f9dcc370ee52092b0f710bbf64feb.jpg)

# Duration Definitions

We defined the duration as

$$
D=-{\frac{1}{P}}{\frac{d P}{d r}}
$$  

 - where $r$ is the continuously compounded interest rate.

 - This definition entails also the interpretation of duration as the discounted time weighted cash flows (equation (3)).

- With discrete compounding the two things are not exactly the same and take different names:
# Macaulay Duration
# - Consider a security with yield to maturity $y$
- Its price is
$$
P=\sum_{j=1}^{n}\frac{c/2}{\left(1+\frac{y}{2}\right)^{j}}+\frac{100}{\left(1+\frac{y}{2}\right)^{n}}
$$  
- The Macaulay duration is defined as
$$
D^{M c}=-\frac{(1+y/2)}{P}\frac{d P}{d y}
$$  
- Some algebra shows
$$
D^{M c}=\frac{1}{2}\sum_{j=1}^{n}w_{j}\times j
$$  

Where

$$
w_{j}=\frac{1}{P}\left(\frac{c/2}{\left(1+\frac{y}{2}\right)^{j}}\right),         \:w_{n}=\frac{1}{P}\left(\frac{c/2+100}{\left(1+\frac{y}{2}\right)^{n}}\right)
$$  
# Modified Duration

 - The modified duration is instead defined as

$$
M D=-{\frac{1}{P}}{\frac{d P}{d y}}
$$  

where $P$ is given in (4).

 - It is easy to see that

$$
M D={\frac{D^{M c}}{\left(1+{\frac{y}{2}}\right)}}
$$  
# The Price Value of a Basis Point (PVBP)

 - In the industry traders often use a related measure of risk,  called the PVBP.

   - This is simply definedas

$$
P V B P=-{\frac{d P}{d y}}\times0.0001=M D\times P\times0.0001
$$  
- This is also called the dollar value of .o 1,  or DVo 1
- Sometimes expressed per \$1 million of face value.
# Example: Spread Trades
- A trader is evaluating the shape of the yield curve
 - The spread between the 30 year T-Bond and the 2 year T-Note is 266 bps.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/6f5cca589438d60911c61e6f52846b78e545677b89c4502c0fef5f903a95cc31.jpg)
- The trader has a view: The spread will increase in the next few days
- How can the trader devise a trading strategy to bet on his/her view,  without taking (part of) interest rate risk?
- First,  if spread increases,  it must be the case that the price of 30-year bond goes down more than the price of the 2-year bond (or up less!). - Hence,  to profit from the movement,  we need a short position in the long-term bond and a long position in the short-term bond.
- Let n 2 and n 30 be the units of 2-year notes and 30 year bonds involved in the trading strategy.
 - Then,  the trader can hedge the interest rate risk by setting
$$
n_{2}\times P V B P_{2}=n_{30}\times P V B P_{30}
$$  

?Suppose $n_{30}\,         =\,         100$ million (par amount),  we can compute the amount of two year notes necessary to hedge the position:

$$
n_{2}=100\times{\frac{1200.643}{187.3602}}=641
$$  
- The trader will go long 641 million (par amount) of the two year bond,  and go short 100 million par amount of the 30-year I-Bond.
How is this done in practice?
- Through the Repo Market. - The trader can enter into a repo at $5\%$ and a reverse repo at $4.9\%$ - The spread between [[Class Note 12 Part 2 Repos|repos]] is the profit for the Repo Dealer,  who borrows money at $4.9\%$ and lends it at $5\%$ - Finally,  suppose hair cut $=0$
We have the following transactions at Date t
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/e3907b39097cff29f1e87f876795caa96d07d16f3cdeb147612430793a4520a5.jpg)
- These cash flows are just the nominal amount paid or received in the market. The trader is borrowing/lending money with zero hair cut,  it has a zero-net position!
·Suppose that at time $t+2$ the new market data are
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/04ad153fdfe86316ced081408d9e6e1e2d79e7c99b115a858e8a29f1d0491379.jpg)
- The new spread is 270 basis points,  hence the view was right. Did the trader make any money?
Date Transaction Cash Flow Date t + 2 1. Sell 2-year note This becomes (A) $(100.5967+0.\1)\times10,         000\times641=$ 645,  212,  011 2. Repay the amount borrowed plus Repo interest. This is (B) 643 $\begin{array}{r l r}{\mathrm{~}}&{{}}&{,         988,         470\times\left(1+2\times\frac{0.\1}{360}\right)=}\end{array}$ (644,  167,  356) 3. Collect the cash plus interest (C) 109,  249,  $\textstyle154\times\left(1+2\times{\frac{0.\1}{360}}\right)=$ 109,  278,  894 4. Buy the 30-year T-bond to cover the short position (D) $(109.8701+0.\1)\times10,         000\times100=$ (110,  326,  800)
Profits?
$$
\mathsf{(L o s s e s)}\ =\ \mathsf{(A)}+\mathsf{(B)}+\mathsf{(C)}+\mathsf{(D)}\ =(3,         251)
$$  

 - The trader lost money,  even if the spread did increase.

The reason,  of course,  are the transaction costs,  such as [[Class Note 9 Bid and Ask Prices With Private Information|bid-ask spreads]] in the Treasury market and in the Repo market

# Interest Rate Risk Management: Convexity
- Convexity measures the curvature of a security with respect to interest rates
$$
C=\frac{1}{P}\frac{d^{2}\;P}{d\;r^{2}}
$$  
- Example 1. From the definition of a zero coupon bond:
$$
I)=e^{-r(t,         T)(T-t)}\Longrightarrow C_{Z}=\frac{1}{Z(t,         T)}\frac{d^{2}\ Z(t,         T)}{d\ r^{2}}=
$$  

Example 2. From the definition of a coupon bond:

$$
\bar{\bf\Phi}=\frac{c}{2}\sum_{i=1}^{n}Z(t,         T_{i})+Z(t,         T_{n})\Longrightarrow C=\frac{1}{P_{c}}\frac{d^{2}{\bf\Phi}P_{c}}{d{\bf\Phi}r^{2}}=
$$  
-where $w_{i}$ are the same as in previous slide.  - Given $D$ and $C$ ,  a better approximation of the return of a security is
$$
{\frac{d\ P}{P}}\approx-D\ d r+{\frac{1}{2}}\ C\ d r^{2}
$$  
# Duration plus Convexity Approximation

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/47945f3845337ce3b5c96eac5bb78996fe1dd07cf3fb0d7a681278b8fbb98323.jpg)

# Positive Convexity: Good News for Average Returns
- Suppose we have invested \$100 million in a 20-year zero coupon bond.
Using Equation (5) and given $D=20$ and $C=20^{2}=400$ ,  we find
$$
E\left[\frac{d P}{P}\right]\approx-20\times E[d r]+\frac{1}{2}\times400\times E[d r^{2}]
$$  
- Predicting variation in interest rates over a short period (daily) is very hard. So $E[d r]=0$ is a good approximation. However,  note that $E[d r^{2}]=V a r(d r)>0$
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/bda94788bfa1b204e67cf1c10e6f69c0a9d04e17feb271927870d301e4868f21.jpg)
Daily Changes in the Level of Interest Rates Data Source: CRSP.
# Positive Convexity: Good News for Average Returns
- From data,  we can estimate the daily variance of interest rates of about $E[d r^{2}]=$ $5.5351\times10^{-007}$ ,  implying
$$
\frac{P}{\rho}\Big]=-20\times0+\frac{1}{2}\times400\times E[d r^{2}]=1.11\times10^{-6}
$$  
- Although this number seems extremely small,  it is a daily expected return
Annualized expected retu $\mathsf{r n\f r o m\c o n v e x i t y}=1.11\times10^{-04}\times252=2.79\%$
- Similarly,  considering the \$io 0 million investment,  convexity yields a daily dollar return of \$11,  $070=1.11\times10^{-04}\times100\ \mathsf{m}$ illion.
- Is this positive average return stemming from the fluctuation of the level of interest rates a "free lunch"?
- No: As we shall see more formally later on,  this positive average return on the investment is counterbalanced by a lower yield to maturity of the bond,  everything else equal.
# Duration and Convexity Approximation: Example
- A pension fund buys \$100 million (par value) of a 10-year,  $5\%$ couponbond
 - Let the yield curve be flat at the continuously compounded rate of $4.5\%$
 - The approximate losses from an increase in $r$ Of $1\%$ are
$$
{\frac{d P}{P}}\,         \approx\,         -D\times0.01=-0.0803=-8\%
$$  
- To check accuracy,  we can compute the exact loss from an increase of the term structure by $1\%$
- Using the pricing formula with $r=4.5\%$ and $r=5.5\%$ ,  we obtain that price declines to \$95.63 from \$103.58:
$$
{\frac{d P}{P}}={\frac{\S95.63-\S103.58}{\S103.58}}=-7.67\%
$$  
-The “convexity" measure is quite accurate
# Interest Rate Risk Management: Duration Hedging

 - The pension fund is worried about potential losses from an increase in rates.

 - The fund decides to hedge by buying $k$ 10-year zero-coupon bond $Z(0,         T)$

We have $Z(0,         T)=\S63.76$ 5.,  and $D_{z}=10$

 - Denoting again by $P$ the value of the bond ( $(P=\S103.58)$ ,  what is the position $k$ in the zero coupon bond such that the portfolio $V\,         =\,         P+k\,         \times\,         P_{z}(0,         T)$ is insensitive to a parallel shift in the yield curve?

 - Condition $d V=0$ implies

$$
k=-\frac{D\times P}{D_{z}\times P_{z}(0,         T)}=\frac{8.03\times103.58}{10\times63.76}=-1.304
$$  
- Assume for simplicity that fund achieves this short position through the repo market at zero haircut (i.e. the short position is achieved at zero cost for the fund.)
# How Does Duration Hedging Perform ?
Spot Curve Change in Shift 

$$
\begin{array}{|c|c|c|c|c|}
\hline
\text{Shift ($d r$)} & P_{c} & Z (0, T) & \text{Position} & \text{Portfolio Value Change} \\
\hline
\text{Initial Values} & 103.58 & 63.76 & -1.3045 & 0 \\
D r = 0.1\% & 102.75 & 63.13 & -1.3045 & -0.0003 \\
D r = 1.0\% & 95.63 & 57.69 & -1.3045 & -0.0318 \\
D r = 2.0\% & 88.38 & 52.20 & -1.3045 & -0.1210 \\
D r = -0.1\% & 104.41 & 64.40 & -1.3045 & -0.0003 \\
D r = -1.0\% & 112.29 & 70.47 & -1.3045 & -0.0350 \\
D r = -2.0\% & 121.84 & 77.88 & -1.3045 & -0.1474 \\
\hline
\end{array}
$$
- Source of the under performance? From $d\;V=d\;P+k\times d\;Z$ wehave
$$
\begin{array}{l}{{\displaystyle{{\bf\Psi}=\;-D\;P_{c}\;d r+\frac{1}{2}\;P_{c}\;C\;d r^{2}+k\;\left(-D_{z}\;Z\;d r+\frac{1}{2}\right.}}}\\ {{{\displaystyle{{\bf\Psi}=\;-\left(D\;P_{c}+k\;D_{z}\;Z\right)\;d r+\frac{1}{2}\;\left(P_{c}\;C+k\;Z\;C_{z}\right)}}}}\end{array}
$$  
- Duration hedging takes care of the first term but not of the second,  which is always negative in our example
# Interest Rate Risk Management: Duration and Convexity Hedging

 - Let $P_{1}$ and $P_{2}$ be the prices of two securities (e.g. short-term and a long-term zeros)，with $D_{1},         \,         D_{2},         \,         C_{1}$ ,  and $C_{2}$ their durations and convex i ties,  respectively.

 - Let $k_{1}$ and $k_{2}$ be the positions in the bonds. The value of the hedged portfolio is

$$
P_{c}+k_{1}\ P_{1}+k_{2}\ P_{2}\Longrightarrow d\ V=d\ P_{c}+k_{1}\ d\ P_{1}+
$$  
- Developing the expression and pulling together the terms in dr and $d r^{2}$
$$
{\begin{array}{c}{d V\ =\ -\left(D\ P+k_{1}\ D_{1}\ P_{1}+k_{2}\ D_{2}\ P_{2}\right)d r}\\ {+{\displaystyle{\frac{1}{2}}}\ \left(C\ P+k_{1}\ C_{1}\ P_{1}+k_{2}\ C_{2}\ P_{2}\right)\ d r}\end{array}}
$$  

 - Thus,  $d V=0$ yields two equations

$$
\begin{array}{r l}{k_{1}~D_{1}~P_{1}+k_{2}~D_{2}~P_{2}\,         =\,         -D~P_{c}}&{{}\bigl(\mathsf{D e l t a~H e d g i ng)}}\\ {k_{1}~C_{1}~P_{1}+k_{2}~C_{2}~P_{2}\,         =\,         -C~P_{c}}&{{}\bigl(\mathsf{C o n v e x i t y~H e dge)}}\end{array}
$$  

 - The solution of this system of two equations in two unknowns is

$$k_{{1}}=
-{\frac{P_{c}}{P_{1}}}\;\left({\frac{D\;C_{2}-C\;D_{2}}{D_{1}\;C_{2}-C_{1}\;D_{2}}}\right);\;\;\;\;\;k_{2}=-{\frac{P_{c}}{P_{2}}}\;\left({\frac{D\;C_{1}-}{D_{2}\;C_{1}-}}\right)
$$  
# Duration and Convexity Hedging: Example

 - In the previous example,  now let the fund use also a $T_{1}=2.$ -year zero for hedging (priced at $Z(0,         T_{1})=\S91.39)$

 - The convexity of the bond we want to hedge is $C\:=\:73.87$ .Given $D_{1}\,         =\,         2$ $D_{2}=10$ $C_{1}=4$ ,  and $C_{2}=100$ ,  we obtain $k_{1}=-0.4562$ and $k_{2}=-1.1737$

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/e21bb52e56677e4d07dc31b1bdddaa6eb0c8170c58507a8d4bf1cec8e237c5fa.jpg)

- There duration plus convexity hedging strategy achieves a better hedge even with large changes in interest rates
# Convexity Trading and the Passage of Time
- The previous example highlights a seemingly profitable trading strategy.
- If we go long bonds with high convexity,  such as long-term bonds,  and duration hedge the interest rate risk using bonds with low convexity,  such as short-term bonds,  we gain positive returns from convexity.
- That is,  in equation
$$
\approx-\left(D\ P_{c}+k\ D_{z}\ Z\right)\ d r+{\frac{1}{2}}\ \left(P_{c}\ C+k\ Z\ C_{z}\right)
$$  

The first parenthesis is always zero,  because of hedging,  while the second paren thesis is always positive,  entailing a positive flow of money

Is this an arbitrage? Can we make large profits by loading on convexity?

- No. The simple example above leaves out an important component of return and this is the passage of time.
# An Issue with Duration Hedging
- Suppose that on April 1,  2004 a fixed income fund has \$100 million (par amount) invested in a 3.875 coupon bond expiring on February 15,  2013. The price of the bond on that day is \$1 o 1.50 (per \$1 o 0 of face value),  and its duration is $D=7.491$
Let's duration hedges with the zero with $T=\mathsf{F e b}$ 15,  2005 (duration $D_{S}=0.87)$
$$
k_{S}=-\frac{D\times P}{D_{S}\times P_{S}}=\frac{7.491\times101.5}{0.87\times99.0019}=-8.83
$$  
- Between April 1,  2004 and April 15,  2004,  the yield curve shifted up by $0.5\%$ ,  On average.
- An effective duration hedge should have largely hedged the losses due to the shift in interest rates.
-If weadd $0.50\%$ to each of the yield on April 1 and recompute the value of the hedged portfolio,  we find its value would only change from \$101.50 to \$101.57,  implying $0.07\%$ increase invalue
# An Issue with Duration Hedging
- In sharp contrast,  the new yield curve implies the value of the hedged portfolio is
$$
V_{4/15/2004}=\$98.20,         
$$ 
- The hedging strategy did not work as expected. - It did work partially,  as the unhedged portfolio would have dropped instead to
$$
V_{4/15/2004}^{\mathsf{n o\;h e d g e}}=\$97.42,         
$$ 
 - The problem with the duration hedge is that the slope of the terms structure changed.

# 2020 Variation in yields

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/ec2e11a6d1e273b6146ddfed477ece29eb097eb6c2df7c1ebceac027e4177868.jpg)

# The Dynamics of the Term Structure: Level,  Slope,  and Curvature

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/7e405adf7d3f1bbdf5d5b501348347f4986fe8e882fcaaa80ffe1a181d8e17ff.jpg)

Data Source: CRSP

# A Factor Representation of Yield Changes

·Let $\phi_{1}(t)$ $\phi_{2}(t)$ and $\phi_{3}(t)$ be three independent factors that affect the term structure.

- We do not know them yet: The exercise is exactly to find them out.
 - Consider the constant maturities $\tau_{1},         \;\tau_{2},         \ldots,         \tau_{n}$ : that is,  T 1 = one month,  $\tau_{2}=2$ months,  … $\tau_{n}=10$ years,  for instance.
·Denoting $r(t,         t+\tau_{i})$ the continuously compounded yield at $t$ of a zero coupon bond maturing at $t+\tau_{i}$ ,  for each of these maturities $\tau_{i}$ ,  let
$$
\Delta r_{i}(t)=r(t+h,         t+h+\tau_{i})-r(t,         t+\tau_{i}).
$$  
# A Factor Representation of Yield Changes
- Assume that the dynamics of interest rates is:
$$
\begin{aligned}
    \Delta r_{1}(t) &= \alpha_{1} + \beta_{11} \Delta \phi_{1}(t) + \beta_{12} \Delta \phi_{2}(t) + \beta_{13} \Delta \phi_{3}, \\
    \Delta r_{2}(t) &= \alpha_{2} + \beta_{21} \Delta \phi_{1}(t) + \beta_{22} \Delta \phi_{2}(t) + \beta_{23} \Delta \phi_{3}.
\end{aligned}
$$  
# Identifying the Factors: Principal Component Analysis
 - The factors driving the term structure are implicit in the $\Delta r_{1}(t),         ….,         \Delta r_{n}(t).$
- PCA assumes they are linear combination of the underlying yields
	 - That is,  for $i=1,         2,         3$ we have

$$
\Delta\phi_{i}(t)=a_{i1}\times\Delta r_{1}(t)+...+a_{i n}\times\Delta r_{n}(t)
$$  
 - Denote $\sigma_{k\ell}=C o v\left(\Delta\boldsymbol{r}_{k},         \Delta\boldsymbol{r}_{\ell}\right)$
	 - Let's start with the first factor $\phi_{1}(t)$
 - Objective: Find $a_{11},         …,         a_{1n}$ to maximize the variance of $\Delta\phi_{1}(t)$

$$
\operatorname*{max}_{\alpha_{11},         \ldots,         \alpha_{1n}}V a r\left(\Delta\phi_{i}\right)=\sum_{k=1}^{n}\sum_{\ell=1}^{n}a_{1k}a_{1\ell}\sigma_{k\ell}
$$  

 - under the restriction $\Sigma_{j=1}^{n}\,         a_{1j}^{2}=1$

 - Since $\Delta\phi_{1}(t)$ is a linear combination of all the yields and it is found to max imize its variability,  it is intuitive that it will co-vary a lot with all the yields $\Delta r_{1}(t),         …,         \Delta r_{n}\left(t\right).$

# Identifying the Factors: Principal Component Analysis
- It is as if we are maximizing some weighted average of the ${\mathsf{R}}^{2}$ S of the multiple regressions
$$
\begin{array}{l}{\Delta r_{1}(t)\,         =\,         \alpha_{1}+\beta_{11}\Delta\phi_{1}(t)+\varepsilon_{1}(t)}\\ {\Delta r_{2}(t)\,         =\,         \alpha_{2}+\beta_{21}\Delta\phi_{1}(t)+\varepsilon_{2}(t)}\\ {\,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         \,         }\\ {\Delta r_{n}(t)\,         =\,         \alpha_{n}+\beta_{n1}\Delta\phi_{1}(t)+\varepsilon_{n}(t)}\end{array}
$$  

 - After the first component,  we can compute the residual of the regression (15): Forall $i=1,         ..,         n$

$$
\hat{\varepsilon}_{i}\left(t\right)=\Delta r_{i}\left(t\right)-\alpha_{i}-\beta_{i1}\Delta\phi_{1}\left(t\right)
$$  
- The variation of the residuals $\hat{\varepsilon}_{i}(t)$ is what is left to "explain.'
# - Hence,  we can compute the second component as
$$
\Delta\phi_{2}(t)=a_{21}\times\hat{\varepsilon}_{1}(t)+\ldots+a_{2 n}\times\hat{\varepsilon}_{n}(t)
$$  

We find again the $a_{21},         …,          a_{2 n}$ that maximize

$$
\operatorname*{max}_{a_{21},         ...,          a_{2 n}}V a r\left (\Delta\phi_{2}\left (t\right)\right)
$$  

Conditional again on $\Sigma_{j=1}^{n}\,          a_{2 j}^{2}=1$ . And so on.

# The Implementation of PCA
- Start from the $n\times n$ variance-covariance matrix of $\Delta r_{i}\left (t\right)\mathbf{\dot{s}}$：Denote it by
$$
M=C o v\left (\Delta r_{1}(t),         ...,         \Delta r_{n}(t)\right)
$$  
- Compute the eigenvalues and ei gen vectors of $M$ ,  i.e. those scalars $\lambda_{i}$ (eigenvalues) and vectors $\mathbf{v}_{i}=(v_{i 1},         \ldots\vdots,          v_{i n})^{\prime}$ related by
$$
M\mathbf{v}_{i}{=}\lambda_{i}\mathbf{v}_{i}
$$  

·Order $\lambda_{1}>\lambda_{2}>…>\lambda_{n}$ . It can be shown then the ei gen vector $\mathbf{V}_{1}$ is the solution to the first maximization (14),  that is $\mathbf{v}_{1}=(a_{11},         …,          a_{1 n})$

- Accordingly,  we set
$$
\begin{array}{r}{\Delta\phi_{1}\left (t\right)=\underset{k=1}{\overset{n}{\sum}}v_{1 k}\ \Delta r_{k}\left (t\right)}\end{array}
$$  
- We then run the regression (i 5) and compute the residuals $\hat{\varepsilon}_{1}\left (t\right),         ..,         \hat{\varepsilon}_{n}\left (t\right)$
# The Implementation of PCA

$\mathbf{v}_{2}$ is the solution to the second maximization (16). Accordingly,  we set the second factor

$$
\begin{array}{r}{\Delta\phi_{2}\left (t\right)=\underset{k=1}{\overset{n}{\sum}}v_{2 k}\ \hat{\varepsilon}_{k}\left (t\right)}\end{array}
$$  
- We run the regression (13) with two factors. And so on.
Notes:
-This procedure gives $\Delta\phi_{i}(t)$ .Thefactor $\phi_{i}(t)$ is the cumulated sum. - Consider the "beta" from the regression from factor 1. Using vector notation
$$
\begin{array}{l}{=\displaystyle\frac{C o v (\Delta r_{i}(t),         \Delta\phi_{1}(t))}{V a r (\Delta\Phi_{1}(t))}=\frac{C o v (\Delta r_{i}(t),         \Sigma_{k=1}^{n}v_{1 k}\Delta r (\Delta\phi_{1}(t)))}{V a r (\Sigma_{k=1}^{n}v_{1 k}\Delta r (\Sigma_{k=1}^{n}v_{1 k}\Delta r (\Delta\phi_{1}(t)))}}\\ {=\displaystyle\frac{\mathbf{1}_{i}^{\prime}M\mathbf{v_{1}}}{\mathbf{v_{1}^{\prime}}M\mathbf{v_{1}}}=\frac{\mathbf{1}_{i}^{\prime}\lambda_{1}\mathbf{v_{1}}}{\lambda_{1}\mathbf{v_{1}^{\prime}}\mathbf{v_{1}}}=v_{1 i}}\end{array}
$$  
> The beta coefficients in (13) are just the ei gen vectors: $\beta_{i j}=v_{j i}$
# Factors from PCA

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/9d6cf6280c640e28c94a44cc76c6ff4cda75b0964e7f108e75d02118e85accf3.jpg)

Data Source: CRSP

# Parallel Shifts,  Slope Tilts and Curvature Changes

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/39be43471c8e978d0db0b4725c72fa42d341ba0d765ccd4327a8d29c2c690fe9.jpg)

Regression coefficients Bii Data Source: CRSP

# The Sensitivity of Interest Rates to PCA Level,  Slope,  and Curvature

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/a884107978da9c86f0d4ee7035d69dc57340eefe36876cea552c72366df548b3.jpg)

 - The first three PCAs explain the vast majority of the variation in yields - => If we hedge the three PCAs,  we hedge most of interest rate risk

# Interest Rate Risk Management and Factor Duration
- The factor duration of an asset with price $P$ with respect to factor j:
$$
D_{j}=-\frac{1}{P}\frac{d\; P}{d\;\phi_{j}}
$$  

From PCA we can approximate

$$
\frac{d r_{i}}{d\phi_{j}}\approx\beta_{i j}
$$  
- Example 1. From the definition of a zero coupon bond $Z (t,          t+\tau_{i})=e^{-r_{i}(t)\tau_{i}}$ the duration with respect to factor $j$ is
$$
\begin{array}{l}{\displaystyle D_{z,          j}\,         =\,         -\frac{1}{Z (t,         \,          t+\tau_{i})}\frac{d\ Z (t,         \,          t+\tau_{i})}{d\,         \phi_{j}}}\\ {\displaystyle\quad=\,         -\frac{1}{Z (t,         \,          t+\tau_{i})}\frac{d\ Z (t,         \,          t+\tau_{i})}{d\,          r_{i}}\times\frac{d\,          r_{i}}{d\,         \phi_{j}}}\\ {\displaystyle\quad=\,         \tau_{i}\times\beta_{i j}\,         }\end{array}
$$  
# Interest Rate Risk Management and Factor Duration

Example 2. From the definition of a coupon bond:

$$
P_{c}(t,          T)=\frac{c}{2}\sum_{i=1}^{n}Z (t,          T_{i})+Z (t,          T_{n})
$$  

 - the duration of the bond with respect to factor $j$ is

$$
D_{j}=-\frac{1}{P_{c}}\frac{d\; P_{c}}{d\;\phi_{j}}=\sum_{i=1}^{n}w_{i}\tau_{i}\beta_{i j}
$$  

Given $D_{j}$ ,  we can approximate the return of a security by

$$
{\frac{d\; P}{P}}\approx-D_{1}\; d\phi_{1}-D_{2}\; d\phi_{2}-D_{3}\; d\phi_{3}
$$  
# Interest Rate Risk Management: Factor Neutrality
-A portfolio $P$ has factor durations $D_{1}$ and $D_{2}$ with respect to level and slope
- To implement factor neutrality,  we need to select two other securities
- E.g. a shortand a long-dated zero coupon bonds,  denoted by $P_{z}^{S}$ and $P_{z}^{L}$
- For each,  compute the factor durations,  $D_{z,          1}^{S},         \,          D_{z,          2}^{S},         \,          D_{z,          1}^{L}$ and $D_{z,          2}^{L}$
·Wewant tochoose $k_{S}$ and $k_{L}$ ,  such that the variation of the portfolio plus the two bonds is approximately zero. That is,  such that the change in $V\,         =$ $P+k_{S}\times P_{z}^{S}+k_{L}\times P_{z}^{L}$ satisfies
$$
D\; V=d\; P+k_{F}\times d\; P_{z}^{S}+k_{L}\times d\; P_{z}^{L}=0
$$  

 - The same steps as in the case of duration / convexity hedging yield the twc equations:

$$
\begin{array}{c} {{k_{S}\times D_{z1}^{S}\times P_{z}^{S}+k_{L}\times D_{z1}^{L}\times P_{z}^{L}=-D_{1}\times P}} \\ {{k_{S}\times D_{z2}^{S}\times P_{z}^{S}+k_{L}\times D_{z2}^{L}\times P_{z}^{L}=-D_{2}\times P}} \end{array}
$$  
# Interest Rate Risk Management: Factor Neutrality

The solution of this system is:

$$
\begin{array}{l}{\displaystyle k_{S}\,         =\,         -\frac{P}{P_{z}^{S}}\left (\frac{D_{1}\times D_{z 2}^{L}-D_{2}\times D_{z 1}^{L}}{D_{z 1}^{S}\times D_{z 2}^{L}-D_{z 2}^{S}\times D_{z 1}^{L}}\right);}\\ {\displaystyle k_{L}\,         =\,         -\frac{P}{P_{z}^{L}}\left (\frac{D_{1}\times D_{z 2}^{S}-D_{2}\times D_{z 1}^{S}}{D_{z 1}^{L}\times D_{z 2}^{S}-D_{z 2}^{L}\times D_{z 1}^{S}}\right)}\end{array}
$$  
# Factor Neutrality: Example

Consider again the previous example,  but use now a short-term and a long-term zeros to hedge. Specifically,  use the zeros maturing on Feb. 15,  2005 and on Feb 15,  2013.

- Using the data about level and slope,  we find the following factor durationsi
$$
\begin{array}{r l} {{\mathsf{m}} {\mathsf{\ c o u p o n\ b o n d}}\colon D_{1}=6.9624;}&{D_{2}=4.0797;}\\ {{\mathsf{S h o r t\!-\!t e r m\ z e r o}} \colon D_{1}^{S}=0.9729;}&{D_{2}^{S}=-0.221}\\ {{\mathsf{L o n g\!-\!t e r m\ z e r o}} \colon D_{1}^{L}=8.1912;}&{D_{2}^{L}=5.3150.}\end{array}
$$  
- Using Equation (18) we obtain that the positions $k_{S}$ and $k_{L}$ in the shortterm and long-term zero coupon bonds are
$$
K_{S}=-0.5266;\quad k_{L}=-1.1259
$$  

 - In this case,  on April 15 2007 the hedged portfolio is worth

$$
V_{4/15/2004}^{F a c t o r H e d g e}=\$ 100.91,         
$$  
# Teaching Notes 3
# Understanding the Term Structure of Interest Rates

# Introduction

There are numerous questions that arise when we think about the term structure of interest rates,  such as:

1. Why does the term structure of interest rates tend to slope upwards?
 1. What is the risk involved in investing in Treasury securities?
 1. Can we predict medium-to-long term yields? What about returns?
# The Expectations Hypothesis

The [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] is the hypothesis that long-term yields just reflect market participants' expectation of future interest rates

Long-term yield $=$ Expected future short-term rates

- To illustrate,  let today be $t$ and consider the case in which investors have perfect foresight of the next l-year interest rates $y_{t+1}(1)$
- Investors then also know that the zero coupon bond price next year will be
$$
Z_{t+1}(1)=e^{-y_{t+1}(1)\times 1}
$$  
- Because under these assumptions,  $Z_{t+1}(1)$ is known today,  its value today is the discounted value using the current 1-year yield:
$$
Z_{t}(2)=Z_{t}(1)\times Z_{t+1}(1)=e^{-(y_{t}(1)+y_{t+1}(1))}
$$  
- Because the two-year yield also satisfies $Z_{t}(2)=e^{-y_{t}(2)\times 2}$ ,  we obtain that under perfect foresight
$$
Y_{t}(2)={\frac{1}{2}}(y_{t}(1)+y_{t+1}(1))
$$  
# The Expectations Hypothesis (cntd.)
- Extending this reasoning to $n$ future one-year yields,  then under perfect foresight the yield of a zero-coupon bond with $n+1$ years to maturity is:
$$
=\mathsf{A v e r a g e}[y_{t}(1),          y_{t+1}(1),         ...,          y_{t+n}(1)]=\frac{1}{n+1}\sum_{i=0}^{n}
$$  

 - The [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] substitutes the perfect foresight with forecasts

$$
\begin{array}{l} {{e r m\ y i e l d\,         =\,         f o r e c a s t e d\ a v e r a g e\ p a t h\ o f\,         f u t u r e}} \\ {{y_{t}(n+1)\,         =\,         E_{t}\left[\displaystyle\frac{1}{n+1}\sum_{i=0}^{n}y_{t+i}(1)\right]\qquad\qquad\qquad\qquad\qquad}} \end{array}
$$  
- Subtracting the current 1-year yield,  we can also write
$$
Y_{t}(n+1)-y_{t}(1)\,         =\,          E_{t}\left[{\frac{1}{n+1}}\sum_{i=0}^{n}y_{t+i}(1)\right]-y_{t}(1
$$  
# Preliminary Heuristic Evidence

Does this relation holds in the data?

- Heuristic ally,  next figure plots the expected future three-month rates from the Survey of Professional Forecasters from 1981 to 2015
- The forecasts are for the three-month T-bill rate for the current quarter,  denote in the figure by $r (t)$ ,  and for the next three quarters,  denoted by $r (t+3 m)$ $r (t+6 m)$ ,  and $r (t+9 m)$ ,  respectively
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/175cddb3d421b6a3e2dc735342e81c5ea821be49dd56d4016d674fabadb8c048.jpg)
- Next figure shows the 1-year term spread,  defined as $y_{t}(1 y)-r (t)$ together with the 1-year "expectation spread".
# 1-Year Expectation Spread vs 1-Year Term Spread

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/40ef95e25752ef1ec16f356851c0de9a3f19826fd4fb3341725cb0003ef1398d.jpg)

- The l-year term spread is greater than the “expectation spread" most of the time - => the expectation hypothesis does not hold (at least,  using survey forecasts)
# The Expectation Hypothesis and Forward Rates
- We saw in Teaching Notes 1 that a forward rate at $t$ for an investment between $\tau_{1}$ and $\tau_{2}$ can be written as
$$
\mathrm{\Sigma_{2})}=\frac{1}{\tau_{2}-\tau_{1}}\ln\left (\frac{Z_{t}(\tau_{1})}{Z_{t}(\tau_{2})}\right)=\frac{1}{\tau_{2}-\tau_{1}}\left (y_{t}(\tau_{2})\tau_{2}-y_{t}(\tau_{1})\tau_{1}+y_{t}(\tau_{2})\tau_{1}\right).
$$  

Consider a sequence of maturities $\tau_{i}=\tau_{i-1}+\Delta t$ ,  for $i=2,         …,          n$ .Wehave

$$
{\begin{array}{r l}&{f_{t}(\tau_{1},         \tau_{2})\,         =\,         {\cfrac{1}{\Delta t}}\left (y_{t}(\tau_{2})\tau_{2}-y_{t}(\tau_{1})\tau_{1}\right)}\\ &{f_{t}(\tau_{2},         \tau_{3})\,         =\,         {\cfrac{1}{\Delta t}}\left (y_{t}(\tau_{3})\tau_{3}-y_{t}(\tau_{2})\tau_{2}\right)}\\ &{\qquad\qquad\,         \,         \vdots}\\ &{f_{t}(\tau_{n-2},         \tau_{n-1})\,         =\,         {\cfrac{1}{\Delta t}}\left (y_{t}(\tau_{n-1})\tau_{n-1}-y_{t}(\tau_{n-2})\tau_{n-2}\right)}\\ &{f_{t}(\tau_{n-1},         \tau_{n})\,         =\,         {\cfrac{1}{\Delta t}}\left (y_{t}(\tau_{n})\tau_{n}-y_{t}(\tau_{n-1})\tau_{n-1}\right)}\end{array}}
$$  
# The Expectation Hypothesis and Forward Rates (cntd.)
- Summing over all of the forward rates,  we find
$$
\sum_{i=2}^{n}f_{t}(\tau_{i-1},         \tau_{i})=\frac{1}{\Delta t}\left (y_{t}(\tau_{n})\tau_{n}-y_{t}(\tau_{1})\tau_{1}\right)
$$  

·Assuming $\tau_{1}=\Delta t$ and defining $f_{t}(0,         \Delta t)=y_{t}(\Delta t)$ ,  we the obtain

$$
Y_{t}(\tau_{n})={\frac{\Delta t}{\tau_{n}}}\sum_{i=1}^{n}f_{t}(\tau_{i-1},         \tau_{i})=\mathsf{A v e r a g e~f o r w a r d~r a}
$$  

 - The expectation hypothesis then implies that for every $i$ the forward rate is equal to the expected future short-term rate: 2

$$
F_{t}(\tau_{i},         \tau_{i}+\Delta t)=E_{t}[y_{t+\tau_{i}}(\Delta t)]\;.
$$  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/53fea15ec012da879094873f5dfdbef561f27c632e26e33522758966851ca739.jpg)

Again,  expected future rates are mostly lower than forward rates

# Time Varying Risk Premia
- The violation of the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] (and the time variation in spread) suggests the existence of an additional term in Equation (1):
$$
Y_{t}(n+1)\,         =\,          E_{t}\left[{\frac{1}{n+1}}\sum_{i=0}^{n}y_{t+i}(1)\right]+R P_{t}
$$  

Where $R P_{t}$ reflects a risk premium from holding the bond from $t$ to $t+1$  - The time variation in $R P_{t}$ invalidates the [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]]

- Even if the expectation of future interest rates does not change,  the yield curve may change because $R P_{t}$ changes - Therefore,  movements in the yield curve do not only correspond to variations in expected future short-term yields
# Term Structure Decomposition

 - Let $y_{t}(n+1)={\mathsf{y i e l d}}$ at $t$ of a bond with time to maturity $(n+1)$ years from $t$

$$
Z_{t}(n+1)=e^{-y_{t}(n+1)(n+1)}
$$  

 - The value of this bond next year will then be

$$
Z_{t+1}(n)=e^{-y_{t+1}(n)\times n}
$$  

 - The yield next year $y_{t+1}(n)$ is not known. Assume it normally distributed

$$
y_{t+1}(n)\sim{\mathcal{N}}\left ({\overline {{y}} },          V\right)\quad{\mathsf{w i t h}}\quad{\overline {{y}} }=E[y_{t+1}(n)]
$$  

$Z_{t+1}(n)$ is risky and so investors at $t$ may require an additional discount $R P$

$$
Z_{t}(n+1)=e^{-(y_{t}(1)+R P_{t})\times 1}E_{t}[Z_{t+1}(n)]
$$  
- Using the properties of the normal distribution,  ? We then obtain
$$
E_{t}[Z_{t+1}(n)]=e^{-\overline {{y}} \times n+\frac{(n)^{2}}{2}V}
$$  
# Term Structure Decomposition (cntd.)

Using (6) and (7) we then obtain

$$
\begin{array}{l}{y_{t}\left (n+1\right)\,         =\,         \displaystyle\frac{1}{n+1}\times y_{t}\left (1\right)+\frac{n}{n+1}\times E_{t}\left[y_{t+1}\left (n+1\right)\right.}\\ {\displaystyle\qquad\qquad\left.+\frac{R P}{n+1}\right.}\\ {\displaystyle\qquad\qquad\qquad\left.-\frac{n^{2}}{2 (n+1)}V_{t}\right.}\end{array}
$$  

. The current long-term yield $y_{t}(n+1)$ depends on

1. The weighted average between the current short-term yield and the expected long-term yield next year.
1. A risk premium RP that market participants require to hold long-term zero coupon bonds with maturity $n+1$ over safe bonds with maturity 1.
1. A convexity term due to the nonlinear relation that exists between the yielo $y_{t+1}(n)$ and the price $Z_{t+1}(n)=e^{-y_{t+1}(n)\times n}$
# Expectation Hypothesis (again)

 - Let $\begin{array}{r}{R P_{t}=\frac{n^{2}}{2}V_{t}}\end{array}$ . Then the expectation hypothesis holds:

$$
\kappa_{t}(n+1) = \frac{1}{n+1} \times y_{t}(1) + \frac{n}{n+1} \times E_{t}\big[y_{t+1}(n)\big].
$$  
- Subtract $y_{t}\left (n+1\right)\times\left (n\right)/(n+1)$ on both sides,  to get
$$
E_{t}\big[y_{t+1}(n)\big] - y_{t}(n+1) = \frac{1}{n} \big[y_{t}(n+1) - y_{t}\big].
$$  

Expected Change in Yield Slope of Term Structure

- A steep term structure (on the RHS) signals the market expects an increase in theyield $y_{t}\left (n+1\right)$ between $t$ and $t+1$ (on the LHS)
$$
E_{t}\left[y_{t+1}\left (n\right)\right]>y_{t}\left (n+1\right)
$$  
- =→> market expects a low or negative return on $(n+1)$ maturity bond
# Long-Term Yield Increase

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/2abe8e5db1f644210b3364b8330e5c6bf2d754b4df1ffcc8ef8dfe4b2a3bad54.jpg)

·Example: On $t=1/31/1994$ yield curve was increasing and the spread was $3.3\%$

High spread may signal long-term yield $y_{t}(30)=6.87\%$ may increase.

 - And indeed,  it did: t + 1 = 1/31/1995 we have $y_{t+1}(29)=7.81\%.$

 - This implies a loss on investment: $\begin{array}{r}{R_{t,          t+1}=\frac{Z_{t+1}(29)}{Z_{t}(30)}-1=\frac{10.3893}{12.7048}-1=-18\%}\end{array}$

# Does the Expectation Hypothesis Hold in the Data?
- Does a high slope predict an increase in future yields? (i.e. should you go short?)
   - In an influential paper,  Campbell and Shiller (1988) run the following regressions
${\mathsf{C h a n g e s~i n~y i e l d}}=\alpha+\beta\times{\mathsf{S l o p e}}_{t}+\varepsilon_{t+1}$
- That is,  from yield data we can compute a dependent $"Y"$ variable
$$
{\it\Delta}_{t}^{\prime}={\sf C h a n g e s~i n~y i e l d}=y_{t+1}\left (n\right)-y_{t}\left (n+1\right);\quad t
$$  

And an explanatory $"X"$ variable

$$
X_{t}=\mathsf{S l o p e}_{t}=\frac{1}{n}\left[y_{t}\left (n+1\right)-y_{t}\left (1\right)\right];\quad t=1,         2,         .
$$  
- Then Campbell and Shiller (1988) run the regression
$$
Y_{t}=\alpha+\beta X_{t}+\varepsilon_{t+1}
$$  

 - The [[Lecture 7-Risk and Return of Bonds#7.4 Expectations hypothesis|expectations hypothesis]] has $\alpha=0$ and $\beta=1$

We can see if this true in the data.

# Campbell and Shiller Regression
# Test of the Expectation Hypothesis

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/5c2f50138d49655b7344cf93f7033d046dfed8525ddd0c914de2bd55ac2e908f.jpg)

Notes: Regression results based on Fama Bliss discount bond data from CRSP. Sample: 1964 - 2006.

Important to note:

-β ≠ 1 => Expectations Hypothesis is rejected $-\;\beta<0\Longrightarrow$ steep yield curve predicts a decrease of long-term yield \* This is the opposite of the basic simple intuition about a raising yield curve

- Bottom line: A steep yield curve predicts high returns of long-term bonds
# Long-Term Yield Decrease

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/8ccc21eb8c5d2d17f7f7709e9608f0f8c572ce21ac9e0a0bcb492b2141f23163.jpg)

·Example: On $t=1/30/2004$ yield curve was increasing and the spread was $4.1\%$

 - In the data,  high spread forecast a decline of long-term yield $y_{t}(30)=5.347\%$  - And indeed,  it did: t + 1 = 1/31/2005 we have $y_{t+1}(29)=4.655\%$  - This implies a gain on investment: $\begin{array}{r}{R_{t,          t+1}=\frac{Z_{t+1}(29)}{Z_{t}(30)}-1=\frac{25.9279}{20.1046}-1=+29\%}\end{array}$

# Time Varying Risk Premia

 - This result implies that the slope of the term structure predicts

$$
L R P_{t}=R P_{t}-{\frac{n^{2}}{2}}V_{t},         
$$  

$\bullet\; L R P_{t}$ stands for "Log Risk Premium" (see below).

 - In fact,  we can rewrite (8) as

$$
\left[y_{t+1}\left (n\right)-y_{t}\left (n+1\right)\right]=\frac{1}{n}\left[y_{t}\left (n+1\right)-y_{t}\left (1\right)\right]-
$$  

We know slope is not positively related to the left-hand-side (previous table) $\Longrightarrow$ then it must be positively correlated with $L R P_{t}$

- When slope increases so does $L R P_{t}$ ,  thereby killing the positive correlation Implication: - High slope $\nRightarrow$ market expects higher future rates. - High slope $\Rightarrow$ high risk premium $\Rightarrow$ high expected return of long-term bonds $\Rightarrow$ strong price increase $\Rightarrow$ low future yield.
# The Predictability of Bond Returns

The Log Risk Premium $L R P_{t}$ can also be rewritten as: 4

$$
L R P_{t}=E_{t}\left[\log\left (\frac{Z_{t+1}\left (n\right)}{Z_{t}\left (n+1\right)}\right)-\log\left (\frac{1}{Z_{t}\left (1\right)}\right)\right]
$$  

The expectation hypothesis implies $L R P_{t}=0$

- To test for this hypothesis,  denote the Log Excess Return $(L E R)$ from holding a long-term zero coupon bond over the short term bond by
$$
L E R_{t}=\log\left (\frac{Z_{t+1}\left (n\right)}{Z_{t}\left (n+1\right)}\right)-\log\left (\frac{1}{Z_{t}\left (1\right)}\right)
$$  

$L E R_{t}$ is the ex-post realized empirical counterpart of $L R P_{t}$

$$
L R P_{t}=E_{t}[L E R_{t}]
$$  
# Fama Bliss Regressions
- Fama and Bliss (1987) then run the following regression
$$
L E R_{t}=\alpha+\beta\left[f_{t}(n,          n+1)-y_{t}(1)\right]+\varepsilon (t)
$$  

 - The expectation hypothesis has $L R P_{t}=0$ ,  and therefore $\alpha=\beta=0$
$$
\text{\textbf{Panel B: Log Excess Return Prediction from Forward Slope}}
$$
$$
\begin{array}{|c|c|c|c|c|c|}
\hline
\text{Maturity } n & \alpha & se (\alpha) & \beta & se (\beta) & R^{2} \\
\hline
2 & -0.01 & 0.27 & 0.92 & 0.26 & 0.14 \\
3 & -0.19 & 0.49 & 1.22 & 0.34 & 0.15 \\
4 & -0.43 & 0.69 & 1.43 & 0.44 & 0.16 \\
5 & -0.16 & 0.93 & 1.11 & 0.51 & 0.07 \\
\hline
\end{array}
$$
-  $\beta$ is significantly different from zero,  and indeed positive
 - This finding,  again,  shows that the excess log return is in fact predictable
- When the forward spread is strongly positive,  on average investments in longterm bonds generate a higher return compared to short term bonds.
# Cochrane and Piazzesi Factor
- Cochrane and Piazzesi (2005) have shown that a specific combination of forward rates successfully predicts excess log returns
 - The predicting factor is defined by
$$
X_{t}=\gamma_{0}+\gamma_{1}y_{t}(1)+\gamma_{3}f_{t}(2,         3)+\gamma_{5}f_{t}(4,         5)
$$  
- The parameters $\gamma_{i}$ are estimated in a first stage regression:
- Define
$$
L E R_{t}=0.25\times\sum_{n=2}^{5}L E R_{t}(n)
$$  

Then,  estimate $\gamma_{i}$ 's with:

$$
L E R_{t}=\gamma_{0}+\gamma_{1}y_{t}(1)+\gamma_{3}f_{t}(2,         3)+\gamma_{4}f_{t}(4,         5))-
$$  
- The estimates for 1964 - 2006 sample are $\widehat{\gamma}_{0}=-3.26$ ,  1 = -1.87,  $\widehat{\gamma}_{3}=3.94,         $ and $\widehat{\gamma}_{5}=-1.64$
# Cochrane and Piazzesi Regression
- Cochrane and Piazzesi (2005) run the regression
$$
L E R_{t}(n)=\alpha+\beta\times x_{t}+\varepsilon_{t}
$$  

Panel C: Log Excess Return Prediction from Cochrane Piazzesi Factor Maturityn B se (β) R 2

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/cee00874d9b641843020fc44e9d046ca080ad6f8ed2105e25987d567b88420b3.jpg)

- The coefficients are strongly positive,  and the $R^{2}$ higher than in Panel B,  showing that including information on the whole term structure helps predict bond excess returns.
# Coping with Inflation Risk: Treasury Inflation-Protected Securities

Treasury coupon bonds are in nominal terms,  as they pay in dollars

How much you can buy with those dollars depends on inflation before maturity Over long periods,  the inflation can be pretty high

CPI index $=$ weighted average of the representative good prices

The change in the CPl measures the realized inflation during the period

# Simple Example
- We have monthly income of $\$ 10$ ,  000 and let CPI $=$ price of consumption basket
- How much we can buy at a given time $t_{1}$ is $C (t_{1})=\$ 10$ ,  000/CPI $(t_{1})$
-E.g. if CPI $(t_{1})=10\Longrightarrow$ we can buy 1000 units of consumption basket. - If basket only contains \$i 0-burgers,  we can buy $C (t_{1})=1000$ burgers at $t_{1}$
- Let now be $t_{2}$ and let our income be the same. Because of inflation,  now ${\mathsf{C P I}}(t_{2})=$ 20.
- We can now only buy $C (t_{2})\,         =\,         \$ 10,         000/{\sf C P I}(t_{2})\,         =\,          500$ burgers: big loss in consumption even if nominal income is the same.
# Inflation Risk and the Loss of Purchasing Power

The ratio $C (t_{2})/C (t_{1})=\mathsf{l o s s}$ in purchasing power of a dollar between $t_{1}$ and $t_{2}$  - This ratio is given by $C (t_{2})/C (t_{1})=\mathsf{C P I}(t_{1})/\mathsf{C P I}(t_{2}).$ - In the previous example ${\mathsf{C P I}}(t_{1})/{\mathsf{C P I}}(t_{2})=0.5\Longrightarrow$ we can only afford at $t_{2}$ half of the goods we could buy at $t_{1}$ Changes in CPl are unknown $\Longrightarrow$ nominal securities have inflation risk - Risk that the dollar payoff will afford less consumption goods than expected

  Inflation-protected securities are vehicles that hedge against this inflation risk

# Treasury Inflation Protected Securities (TIPS)

TIPS are coupon bonds issued with maturities of 5,  10,  and 20 years

The coupon rate of TlPS is a constant fraction of the principal

The principal changes over time in response to inflation.

- If the CPl increases,  then the principal amount increases proportionally
The Treasury publishes Index ratios
$$
\mathsf{I n d e x\ r a t i o}(t)\;=\;\mathrm{max}\left (\frac{\mathsf{R e f e r e n c e\ C P I}(t)}{\mathsf{C P I}(\mathsf{i s s u r a n c e})},          0\right)
$$  

Reference $:{\mathsf{C P I}}(t)\;=\; w (t)~{\mathsf{C P I}}(t-1)+(1-w (t))~{\mathsf{C P I}}$ (t—2) -where $w (t)$ is a weight that depends on the quoted day of the month

. Next Table contains quotes of Treasury securities on November 26,  2007. - Given the index ratio,  the next coupon payment is

# Treasury Securities on November 26,  2007
##### Panel A: Treasury Bills
$$

\text{\textbf{Panel A: Treasury Bills}}

$$

$$

\begin{array}{|c|c|c|c|}

\hline

\text{Maturity} & \text{Coupon} & \text{BID} & \text{ASK} \\

\hline

12/20/2007 & 3.54 & 3.50 & - \\

2/21/2008 & 3.05 & 3.00 & - \\

5/22/2008 & 3.24 & 3.23 & - \\

\hline

\end{array}

$$
##### Panel B: Nominal Treasury Notes and Bonds
$$

\text{\textbf{Panel B: Nominal Treasury Notes and Bonds}}

$$

$$

\begin{array}{|c|c|c|c|}

\hline

\text{Coupon} & \text{Maturity} & \text{BID} & \text{ASK} \\

\hline

3 \frac{5}{8} & 10/31/2009 & 101.25 & 101.25 \\

4 \frac{1}{2} & 5/15/2010 & 103.75 & 103.7813 \\

3 \frac{7}{8} & 10/31/2012 & 102.7188 & 102.7188 \\

4 \frac{1}{4} & 11/15/2017 & 103.1563 & 103.1563 \\

5           & 5/15/2037 & 111.7813 & 111.8438 \\

\hline

\end{array}

$$
##### Panel C: TIPS

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/968ea44aa267337965de6cd259a6a22496b0632a9b37b7782c8ac2f192935142.jpg)

# Reference Index Example

The quotes in the Table are for November 26,  2007.

- The CPl used to compute the index ratio is not the November CPl.
- CPl values are released by BLS during the third week of the following month
- CPl used is instead the average between the August and September CPls (207.917 and 208.490,  respectively).
- Because November 26 is 25 days after November 1,  the calculation is
$$
{\mathsf{C P I}}(t)={\frac{5}{30}}\times 207.917+{\frac{25}{30}}\times 208.490=208.39
$$  
- An investor in TiPS is still subject to a small inflation risk during the two months between the CPl measure and the actual payment
# Real Bonds and the Real Term Structure of Interest Rates
- Borrowing and lending do not need dollars
- You can borrow a car from a friend and return it in a week - If you forget your wallet,  you can ask your friend to buy a sandwich today with the agreement you will return the same sandwich tomorrow. \* If your "friend" see you very hungry today,  he may ask you to return a bigger sandwich tomorrow. I.e. charge a big real interest rate.
Real bonds are bonds that are denominated in units of a good instead of dollars
: Relevant to inflation linked securities are bonds that are denominated in units of the consumption basket that underlies the CPl index calculation
,  A real discount factor $Z^{r e a l}(t; T)$ defines the erchange rate between consumption goods at $t$ versus consumption goods at a later date T.
- How "bigger" a sandwich are we willing to give back to the "friend" tomorrow to have a sandwich today?
# Real Rates
- From real discounts $Z^{r e a l}(t; T)$ compute the real rate as usual:
$$
Z^{r e a l}(t; T)=e^{-r_{r e a l}(t; T)(T-t)}\times 1
$$  

Implies

$$
R_{r e a l}(t; T)=-\frac{\ln\left (Z^{r e a l}(t; T)\right)}{T-t}
$$  

 - The real term structure of interest rates is $r_{r e a l}(t; T)$ for maturities $T$

 - The value (in consumption goods) of a real coupon bond with maturity $T$ and couponrate $c$ is

$$
P_{c}^{r e a l}(t; T)={\frac{c\times 100}{2}}\sum_{i=1}^{n}Z^{r e a l}(t; T_{i})+100\times Z^{r e a l}
$$  
# Real Bonds and TIPS
- Suppose an investment bank purchases a TlPS and strips the coupons from prin cipal,  generating a series of zero coupon bonds
 - These zero coupon bonds pay an amount that is tied to the CPl
·Denotingby $I d x (T)$ the CPl adjustment for maturity $T$ (recall,  it depends on the CPl two months earlier),  the payoff of a zero coupon TiPS is as follows:
$\cdot\mathit{I d x}(T)/\mathit{I d x}(0)=$ increase in the consumption basket price between O and $T$  - For simplicity,  assume
·Given $Z^{r e a l}(t; T)$ ,  the value at $t$ of a security paying $I d x (T)$ (i.e. the amount need to purchase one unit of consumption basket) is
Present value of $I d x (T)=\mathsf{P V}$ of one unit of consumption $=Z^{r e a l}(t; T)$
# Real Bonds and TIPS (cntd)

 - This present value though is expressed in terms of units of the consumption basket $Z^{r e a l}(t,         ; T)$ is an exchange rate of consumption at $t$ for consumption at $T)$

- We can convert this value to dollars by multiplying it by the current price of the consumption basket $I d x (t)$ .We then obtain
$I d x (T)=Z^{r e a l}(t; T)\times I d x (t)$
- Finally,  to obtain the payoff of the zero-coupon TiPS we must divide by $I d x (0)$
$$P^{\textsf{TIPS}}=Z^{T I P S}(t; T)=Z^{r e a l}(t; T)\times\frac{I d x (t)}{I d x (0)}$$ 
- Given the value of zero-coupon TiPS,  we can value coupon bearing TIPS
 - Therefore,  a TIPS value at $t$ ,  with maturity $T$ ,  and coupon rate $c$ is given by
$$
Z^{TIPS}(0,T)=\frac{I d x (t)}{I d x (0)}\times\bigg[\frac{c\times 100}{2}\sum_{i=1}^{n}Z^{r e a l}(t; T_{i})+Z^{r e a l}(t; T_{i})+Z^{s r e a l}(t; T_{i})\bigg]
$$  
# Fitting the Real Yield Curve

·- Clearly,  zero-coupon real bonds $Z^{r e a l}(t; T_{i})$ are not observable,  but they are embedded in the prices of TiPS.

- We can use the price of TIPS to “back out" the discount factors $Z^{r e a l}(t; T_{i})$
- One limitation compared to the case of Treasuries is that we do not have available as many bond prices,  and therefore the boots trapping strategy is not applicable
- However,  we can use the curve fitting method using a flexible function for the discount factor,  such as the Nelson Siegel model
$$
=\;\theta_{0}+(\theta_{1}+\theta_{2})\,         \frac{1-e^{-\frac{T}{\kappa_{1}}}}{\frac{T}{\kappa_{1}}}-\theta_{2}e^{-\frac{T}{\kappa_{1}}}+\theta_{3}\left (\frac{1-e^{-\frac{T}{\kappa_{2}}}}{\frac{T}{\kappa_{2}}}\right)
$$  
- From the previous table,  for instance,  we obtain the following results
# Real and Nominal Rates on November 26,  2007

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/72a6221195e7211eb3408694610b957e1b685863d3652e940af9d1e55ce775a1.jpg)

- Next figure shows that the term structure of real rates changes over time
# Real Rates during and after the crisis

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/0168a832864dbaf7fd996285d3949aef696bc37ab2c1b80a50e8f2d3b125f479.jpg)

Data are from Gurkaynak,  Sack,  and Wright (2010),  updated series

Negative real rates are not uncommon.

- We give back our "friend" a smaller sandwich because its price skyrocketed
# Nominal and Real Interest Rates

What is the relation between real and nominal rates?

We now show that

Nominal rate $=$ real rate + expected inflation + inflation risk premium — convexity

- Consider first the value today of $\$ 1$ atT
$$
Z (0,          T)=e^{-r (0,          T) T}\times P_{1}
$$  
- Alternatively,  we can express this in "consumption goods":
- Unfortunately,  this amount is not known today,  because CPl $(T)$ is stochastic
 - To compute the present value we need more assumptions.
 - Let $\pi$ be the annualized inflation rate between O and $T$
$$
\pi={\frac{1}{T}}\ln\left ({\frac {{\mathsf{C P I}} (T)} {{\mathsf{C P I}} (0)}}\right)
$$  
# The Fisher Equation under Perfect Foresight
- Consider first Perfect Foresight: Assume investors know T and hence CPl $(T)$
 - Then the value today of $\$ 1$ at $T$ in consumption good units is
$$
\mathcal{\Gamma})=Z^{r e a l}(0,          T)\times C (T)=Z^{r e a l}(0,          T)\times\frac{\$ 1}{\mathsf{C P I}(T)}
$$  
- To obtain the dollar value,  we multiply this by the price of consumption good
$$
C (T)={\mathsf{C P I}}(0)\left (Z^{r e a l}(0,          T)\times\frac{\$ 1} {{\mathsf{C P I}} (T)}\right)
$$  

·The RHS is the $\S$ value of the quantity of consumption purchased by $\$ 1$ at $T$  - It is therefore a nominal discount,  yielding the equality

$$
Z (0,          T)=Z^{r e a l}(0,          T)\times\frac {{\mathsf{C P I}} (0)} {{\mathsf{C P I}} (T)}
$$  
- Substitute to obtain the Fisher equationi
$$
R (0,          T)=r_{r e a l}(0,          T)+\pi
$$  
# Inflation Risk Premium
- Assume now inflation rate is not known and assume it is log-normal
$$
\log\left ({\frac {{\mathsf{C P I}} (T)} {{\mathsf{C P I}} (0)}}\right)=x\sim{\mathcal{N}}(\pi\; T,         \sigma\pi^{2}\; T)
$$  
- This implies that the amount of consumption we can buy at $T$ is stochastic
$$
C (T)=\frac{\$ 1}{\mathsf{C P I}(T)}=\$ 1\times\frac{e^{-x}}{\mathsf{C P I}(0)}
$$  

·Because $C (T)$ is now risky,  we cannot discount it to today using the real bond $Z^{r e a l}(0,          T)=e^{-r_{r e a l}(0,          T) T}$ ,  but we thus must add a risk premium $\kappa$

- Multiplying also by CPl (O) to obtain the dollar value,  we obtain
$$
\begin{array}{l} {{C(T)\;=\;e^{-(r_{r e a l}(0,         T)+\kappa)T}\times E[e^{-x}]}} \\ {{\;=\;e^{-(r_{r e a l}(0,         T)+\kappa)T}\times e^{-\overline{{{\pi}} }T+\frac{1}{2}\sigma\pi^{2}T}}}\end{array}
$$  
- This is dollar present value of $\S~1$ at $T$ . Therefore it equals $Z (0,          T)=e^{-r (0,          T) T}$
$$
r (0,          T)=r_{r e a l}(0,          T)+\overline {{\pi}} +\kappa-\frac{1}{2}\sigma\pi^{2}
$$  
# The Economics of Fixed Income Investments
- We now link all this to economic growth and agents' decisions
- We assume that investors have a utility function $U (C (t),          t)$ . This is
- Decreasing with time: Eating soon is better than eating later. - Increasing in consumption: Eating more is better than eating less. - Concave: → Risk aversion: An amount of consumption that is certain is better than a fair bet to have more or less.
$$
E\left[U (C)\right]<U\left (E[C]\right)
$$  
- A widely used utility function is the Constant Relative Risk Aversion (CRRA):
$$
U (C,          t)=e^{-\rho t}{\frac{C^{1-\gamma}}{1-\gamma}}
$$  
- P = time-preference parameter
$-\,         \gamma=-C U^{\prime\prime}(C)/U^{\prime}(C)=\mathsf{r e l a t i v e\ r i s k\ a v e r s i o n}$ parameter.
# Optimal Savings
- An investor has wage $w (0)$ today and a random amount $w (T)$ at $T$
- Then investor consumption plan is $\begin{array}{r}{C (0)=\frac{w (0)}{\mathsf{C P}[0)}}\end{array}$ and $\begin{array}{r}{C (T)=\frac{w (T)}{\mathsf{C P I}(T)}.}\end{array}$
- Suppose the investor now has an unexpected bonus today of \$io 0 dollar
The investor can:
1. Spend\$S 100 todayand buy $\overline {{\mathsf{C P}_{\mathrm{(0)}} ^{\ }}}$ amount of the consumption good,  which will procure him/her an additional amount of utility
$$
U^{\prime}\left (C (0),          0\right)\times\frac{\Phi 100}{\mathsf{C P I}(0)}
$$  
1. Save the 100 dollars,  and buy $\displaystyle\frac{\$ 100}{Z (0,          T)}$ zero coupon bonds with maturity $T$ .At that time,  the investor can buy $\frac{\P 100}{Z (0,          T)}\frac{1}{\mathsf{C P I}(T)}$ of the consumption good,  for an additional amount of utility
$$
\frac{\$ 100}{Z\left (0,          T\right)}\frac{1}{\mathsf{C P I}(T)}U^{\prime}\left (C (T),          T\right)
$$  
# Equilibrium

 - Equilibrium requires the agent to be in different between 1 and 2. Because quan titiesat $T$ are unknown,  the indifference condition is

$$
C (0),          0)\times\frac{\$ 100}{\mathsf{C P I}(0)}=E\left[\frac{\$ 100}{Z\left (0,          T\right)}\frac{1}{\mathsf{C P I}(T)}U^{\prime}\left (C (T)\right)\right.
$$  

By reshuffling,  we obtain

$$
Z (0,          T)=E\left[{\frac {{\mathsf{C P I}} (0)} {{\mathsf{C P I}} (T)}}\times{\frac{U^{\prime}(C (T),          T)}{U^{\prime}(C (0),          0)}}\right]
$$  
- In aggregate,  real consumption $C (t)$ depends on real GDP $Y (t)$
- Assume that inflation and real GDP growth have the joiny log-normal distribution
$$
\begin{array}{r l}&{\left (\frac{{\sf C P I}(T)}{{\sf C P I}(0)}\right)}\\ &{\mathfrak{g}\left (\frac{Y (T)}{Y (0)}\right)}\end{array}\right)=\left (\begin{array}{l}{x}\\ {y}\end{array}\right)\sim\mathcal{N}\left (\left (\begin{array}{l}{\overline{\pi}\ T}\\ {\overline{g}\ T}\end{array}\right),         \left (\begin{array}{c}{\sigma\pi^{2}\ T}\\ {\sigma\pi\sigma_{g}\rho_{g,         \pi}\ T}\end{array}\right)\right.}\end{array}
$$  
# Equilibrium Prices
- Substitute the CRRA utility function
$$
U^{\prime}(C,          t)=e^{-\rho t}C (t)^{-\gamma}
$$  

And use $C (t)=Y (t)$ for $t=0,          T$ to find

$$
{\begin{array}{r l}&{Z (0,          T)\,         =\,          E\left[e^{-x}\times{\cfrac{e^{-\rho T}Y (T)^{-\gamma}}{Y (0)^{-\gamma}}}\right]}\\ &{\qquad\qquad\,         =\,          E\left[e^{-\rho T}\times e^{-x-\gamma y}\right]}\\ &{\qquad\qquad\,         =\,          e^{-\rho T}\times e^{-\pi T-\gamma{\overline {{g}} }+{\frac{1}{2}}(\sigma\pi^{2}+\gamma^{2}\sigma_{g}+2\gamma\sigma\pi\sigma_{g}\rho_{g,         \pi})}}\end{array}}
$$  

 - Thus,  the nominal rate is

$$
\mathrm{\bf\gamma})\;=\;\left (\rho+\gamma\overline {{{g}} }-\frac{\gamma^{2}}{2}\sigma_{g}^{2}\right)\;\;+\;\;\overline {{{\pi}} }-\frac{1}{2}\sigma\pi^{2}\;\;\;\;\;\;\;-
$$  

Real rate $r_{r e a l}(0,          T)$ exp. Infl. & conv. Risk premium

# The Economics of the Real Rate
- Following the same steps as above but using TIPS zero-coupon bonds $Z^{T I P S}(0,          T)$ instead of nominal bonds $Z (0,          T)$ we obtain the real rate as:
$$
r_{r e a l}(0,          T)=\rho+\gamma\overline {{g}} -\frac{\gamma^{2}}{2}\sigma_{g}^{2}
$$  

The real rate depends on:

1. Time preference $\rho$
-High $\rho$ implies investors want to consume today rather then tomorrow. They will sell their (real) bonds which increase their yield
1. The expected growth rate of the economy $\overline{{g}}$
一 If $\overline{{g}}$ is high we expect to be rich at $T$ and hence consume a lot then. High $\gamma$ implies we want "stable consumption" over time. Hence we want to borrow to consume more today,  which increases real rates
1. The volatility of GDP growth $\sigma_{g}$
- Higher economic risk implies a higher desire to save for the "rainy days" We buy more (real) bonds,  which push their prices up and decrease yields - The higher the risk aversion $\gamma$ and the more we want to save.
# Inflation Risk Premium

We found

Inflation risk premium = —OTOgPg,  m

Where

 - Intuitively:

-If $\rho_{g,         \pi}<0\Longrightarrow$ high inflation occurs when real GDP is low $\Longrightarrow$ nominal bond is devalued in recessions,  when people most need the money! >very risky security $\Longrightarrow$ high risk premium $\Longrightarrow$ high long-term yield

- Next figures show that the correlation $\rho_{g,         \pi}$ was negative until late 1990 s. It then became closer to zero. And then became strongly positive around 2008.
In the meantime,  real GDP volatility $\sigma_{g}$ and inflation volatility oT declined
   - All of these variation are bound to impact the risk premium
# Quarterly Real GDP Growth and CPl Infation

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/707740f7df7fcb90e8c4a586e6c228f1b46e1920435bbd52c5955a10094b454a.jpg)

Quarterly Real GDP Growth and CPI Infation DataSource: Federal Reserve of St. Louis

# Correlation and Real GDP growth and CPI inflation Vol at ili ties

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/1f6c8ad372d12be68521cb72262f95a6796f1df7847dddd5aa140831d5bb3b91.jpg)

Backward-looking 10-year Rolling Window. Data Source: Federal Reserve of St. Louis

# Expected Excess Return: The Market Model
- Another way to understand the risk premium of nominal bonds is to look at its variation with the stock market
 - Under the CAPM,  for instance
E [Excess Return Nominal Bond] $=\beta\times E$ [Excess Return Market]
- Next figure shows the time variation in the correlation between stock and bonds,  and the corresponding CAPM beta.
Why did the CAPM beta change over time?
- David and Veronesi (2013,  JPE): Time varying role of inflation signals
\* Late 1970 s/ early 1980 s: Fear of stagflation (high inflation and low growth) => high inflation shocks are bad news for the economy > both nominal bonds and stock drop \* Mid 2000 s: Fear of deflation (low inflation and low growth) => high inflation shocks are good news for the economy => nominal bonds drop but stock rise
# The Covariance between Stocks and Bonds,  and the CAPM Bond Beta

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/6a6edb6074169dd862cfbec8857dd2d97f7ad77a7722027436f64742ce1b2704.jpg)

Source: David and Veronesi (2016) “The Economics of the Comovement of Stocks and Bonds" in the Handbook of Fixed Income,  Pietro

# Nominal and Real Stock Betas

Figure 1: Rolling Nominal and Real Bond-Stock Betas

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/c7c760925c94114d09e111a3ee686f55584d67bfcaac8c2319c00dc617278cd1.jpg)

Source: Caroline Pflueger (2024) “Back to the 1980 s or Not? The Drivers of Inflation and Real Risks in Treasury Bonds"

# More General Formulas
- All previous formulas have “flat'" term structures: $r (0,          T)$ and $r_{r e a l}(0,          T)$ donot depend on $T$
- They can be generalized by assuming that expected inflation $\overline {{\pi}} _{t}$ and expected GDPgrowth $\overline {{g}} _{t}$ are time varying
- Using the continuous time methodology,  for instance,  we may assume
$$
\begin{array}{r l}&{d\overline {{\pi}} _{t}\,         =\,          (\alpha\pi-\beta\pi\overline {{\pi}} _{t}) d t+\sigma_{\overline {{\pi}} }\; d W_{\overline {{\pi}} }}\\ &{d\overline {{g}} _{t}\,         =\,          (\alpha_{g}-\beta_{g}\overline {{g}} _{t}) d t+\sigma_{\overline {{g}} }\; d W_{\overline {{g}} }}\end{array}
$$  

Inflation and real GDP growth themselves are

$$
\begin{array}{r}{d\log (\mathsf{C P I}_{t})\,         =\,         \overline{\pi}_{t}d t+\sigma_{\pi}\ d W_{\pi}}\\ {d\log (Y_{t})\,         =\,         \overline{g}_{t}d t+\sigma_{g}\ d W_{g}}\end{array}
$$  

The same argument as above has

$$
Z (t,          T)=E_{t}\left[{\frac {{\mathsf{C P I}} (t)} {{\mathsf{C P I}} (T)}}e^{-\rho (T-t)}\left ({\frac{Y (T)}{Y (t)}}\right)^{-\gamma}\right]
$$  
# Bond Pricing Formulas

Solving the expectation,  we obtain

$$
Z (t,          T)=e^{A (t,          T)-B (t,          T)\overline {{\pi}} _{t}-C (t,          T)\gamma\overline {{g}} _{t}}
$$  

Where

$$
\beta (t,          T)=\frac{1-e^{-\beta\pi (T-t)}}{\beta\pi};~~~~C (t,          T)=\frac{1-e^{-\beta_{g}(T-t)}}{\beta_{g}}
$$  

 - and $A (t,          T)$ is a complicated function of maturity $(T-t)$ which includes risk premia and other terms further discussed below.

 - The nominal yield curve is then

$$
r (t,          T)=\frac{-A (t,          T)}{T-t}+\frac{B (t,          T)}{T-t}\;\overline {{\pi}} _{t}+\frac{C (t,          T)}{T-t}\;\gamma\overline {{g}} _{t}
$$  
- A higher expected inflation increases nominal yield,  but differential ly across maturities
- A higher expected real growth increases nominal yields,  but differential ly across maturities
# The Function A (t, T)
$$
\begin{array}{l} {{\displaystyle=\left(-\rho+\frac{1}{2}\sigma_{\pi}^{2}+\frac{1}{2}\gamma^{2}\sigma_{g}^{2}+\gamma\sigma_{\pi}\sigma_{g}\rho_{\pi g}\right)\left(T-t\right)}} \\ {{\displaystyle\ \ +\left[\sigma_{\pi}\sigma_{\pi}\rho_{\pi\pi}+\gamma\sigma_{g}\sigma_{\pi}\rho_{g\overline{{{\pi}} }}-\alpha_{\pi}+\frac{1}{2}\frac{\sigma_{\pi}^{2}}{\beta_{\pi}}+\frac{\gamma\sigma_{\pi}\sigma_{g}\rho_{\pi\overline {{{g}} }}}{\beta_{\pi}+\beta_{g}}\right]\frac{1}{\beta_{\pi}}}}\\ {{\displaystyle\ \ +\left[\sigma_{\pi}\sigma_{\overline{{{g}} }}\rho_{\pi\overline {{{g}} }}+\gamma\sigma_{g}\sigma_{\overline {{{g}} }}\rho_{g\overline {{{g}} }}-\alpha_{g}+\frac{1}{2}\frac{\gamma\sigma_{g}^{2}}{\beta_{g}}+\frac{\sigma_{\pi}\sigma_{g}\rho_{\pi\overline {{{g}} }}}{\beta_{\pi}+\beta_{g}}\right]\frac{\gamma}{\beta_{g}}\left (t\right)}}\\ {{\displaystyle\ \ -\frac{1}{4}\frac{\sigma_{\pi}^{2}} {\beta_{\pi}}B\left (t,          T\right)^{2}-\frac{1}{4}\frac{\gamma^{2}\sigma_{g}^{2}}{\beta_{g}}C\left (t,          T\right)^{2}-\frac{\gamma\sigma_{\pi}\sigma_{g}\rho_{\pi\overline {{{g}} }}}{\left (\beta_{\pi}+\beta_{g}\right)}B\left (t,          T\right)}}\end{array}
$$  

Many risk premia

1. Inflation risk premium: $\gamma\sigma_{\pi}\sigma_{g}\rho_{\pi g}.\qquad\mathsf{I f}\ \rho_{\pi g}<0\Longrightarrow Z (t,          T)\downarrow\Longrightarrow r (t,          T$ 2. Expected inflation risk premium: $\gamma\sigma_{g}\sigma_{\pi}\rho_{g\overline {{{\pi}} }}$ If $\rho_{g,         \pi}<0\Longrightarrow r (t,          T)$ ↑
 1. Expected growth risk premium: $\gamma\sigma_{g}\sigma_{\overline {{{g}} }}\rho_{g\overline {{{g}} }}$ If $\rho_{g,         \overline {{{g}} }}<0\Longrightarrow r (t,          T)$ ↑ and manv convexitv efferts
# The Shot-term Rate and Monetary Policy Interpretation
- As we take the limit $T-t\rightarrow 0$ we obtain the formula for the "overnight”" rate real rate rreal,  t exp. Infl. & conv. Risk premium
- The Federal Reserve is believed to follow the so-called "Taylor rule'" in setting its target Federal Fund rate,  which specifies
R't = Q + β1 (outputt — potential output) + β1 (inflationt — target inflation)
- The “forward looking" Taylor rule uses "expected inflation" and expected output to their realized values.
 - The result above can be casted in terms of [[Lecture 7-Risk and Return of Bonds#7.6 Asset price reactions to monetary policy surprises|monetary policy]] actions
$$
r_{t}=\alpha+\gamma (\overline {{g}} _{t}-\mathsf{p o t e n t i a l\ o u t p u t})+(\overline {{\pi}} _{t}-\mathsf{t a r g e t}
$$  

Where $\begin{array}{r}{\alpha=\rho-\frac{\gamma^{2}}{2}\sigma_{g}^{2}-\frac{1}{2}\sigma\pi^{2}-\gamma\sigma\pi\sigma_{g}\rho_{\pi,          g}+\gamma\mathsf{p o t e n t i a l\ o u t}}\end{array}$ tput + target inflation

# The Dynamics of the Real Rate
- From previous results and using Ito's formula,  the real rate follows a [[An Overview of the Vasicek Short Rate Model|Vasicek Model]]
$$
d r_{r e a l,          t}=\beta_{g}\left (\overline {{r}} _{r e a l}-r_{r e a l,          t}\right) d t+\sigma_{r e a l}d W_{\overline {{g}} }
$$  

Where

$$
\overline {{{r}} }_{r e a l}=\rho+\gamma\frac{\alpha_{g}}{\beta_{g}}-\frac{\gamma^{2}\sigma_{\overline {{{g}} }}^{2}}{2};\quad\sigma_{r e a l}=\gamma\sigma_{\overline {{{g}} }}
$$  

 - The real zero-coupon bond pricing formula is then

$$
Z_{r e a l}(t,          T)=e^{\overline {{A}} (t,          T)-C (t,          T) r_{r e a l,          t}}
$$  

Where

$$
\negmedspace)=\left (\overline {{r}} _{r e a l}^{*}-\frac{1}{2}\frac{\sigma_{r e a l}^{2}}{\beta_{g}^{2}}\right)[C (t,          T)-(T-t)]-\frac{C (t,          T)}{4}
$$  

 - where $\overline {{r}} _{r e a l}^{*}=\overline {{r}} _{r e a l}-\gamma\sigma_{g}\sigma_{r e a l}\rho_{\rho,          r e a l}$

 - The risk neutral process of the real rate is

$$
d r_{r e a l,          t}=\beta_{g}\left (\overline {{r}} _{r e a l}^{*}-r_{r e a l,          t}\right) d t+\sigma_{r e a l}d W_{\overline {{g}} }^{*}
$$  
# Fitting Real Vasicek to TlPS
- We can use TiPS again to extract the real zero coupon bond prices
·The procedure is the same for nominal Vasicek (see TN 7),  except with the additional difficulty that we may not know what the short-term real rate $r_{r e a l,          t}$ actually is.
- One possibility is to estimate $r_{r e a l,          t}$ as well together with other quantities.
·For instance,  fixing $\sigma_{r e a l}=. 00967$ (estimated from the time series of real rates),  we estimate the following parameters for November 27,  2007:
$$
\beta_{g}^{*}=0.0166,         \ \ {\overline {{r}} }_{r e a l}^{*}=0.1695,         \ \ r_{r e a l,          0}=0.0046
$$  

 - The fit is not as good as with the Extended Nelson-Siegel model in this case

- Next figure shows the fitted term structure of real rates.
# Vasicek Fit to TlPS on November 27,  2007

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/185d4d6134b1c8b8ebcfcef3a300d16377e52f107ee2e39f60d8420d9059ddac.jpg)

Data Source: Bloomberg

# Conclusions
- The term structure of interest rate depend on:
1. Expectation of future inflation 2. Expectation of future real growth 3. A whole set of risk premia - Inflation risk premium - Expected inflation risk premium - Expected growth risk premium
- Multi-factor models tend to fit well the term structure of interest rates
- The above setting with expected inflation and expected GDP growth can be gen eralized to any factors $\phi_{1,          t},         \;\phi_{2,          t}….$
- Moreover,  pricing formulas can be obtained using no-arbitrage methodologies,  as in TN 7.
# Appendix: Derivation of Two Factor Model

Define

$$
\begin{array}{l l l}{q}&{=}&{\log\left ({\mathsf{C P I}}\right)}\\ {y}&{=}&{\log\left (Y\right)}\end{array}
$$  

So that

$$
\begin{array}{r c l} {{d q}} & {{=}} & {{\overline{{{\pi}} }_{t}d t+\sigma_{\pi}d W_{\pi}}}\\ {{d y}} & {{=}} & {{\overline{{{g}} }_{t}d t+\sigma_{g}d W_{g}}}\end{array}
$$  

And recall

$$
\begin{array}{r c l}{d\overline {{\pi}} _{t}\!}&{=}&{\!\left (\alpha_{\pi}-\beta_{\pi}\pi_{t}\right) d t+\sigma_{\overline {{\pi}} }d W_{\overline {{\pi}} }}\\ {d\overline {{g}} \!}&{=}&{\!\left (\alpha_{g}-\beta_{g}\pi_{t}\right) d t+\sigma_{\overline {{g}} }d W_{\overline {{g}} }}\end{array}
$$  

From the pricing equation we have

$$
Z\left (t,          T\right)=E\left[e^{-\rho\left (T-t\right)-\left (q\left (T\right)-q\left (t\right)\right)-\gamma\left (y\left (T\right)-y\left (t\right)\right)}\right]
$$  

To be slightly more general,  consider the following case

$$
\begin{array}{l l l} {{Z\left(t,         T\right)}} & {{=}} & {{E\left[e^{-\rho\left(T-t\right)-\eta\left(q\left(T\right)-q\left(t\right)\right)-\gamma\left(y\left(T\right)-y\left(t\right)\right)}\right]}} \\ {{\ }} & {{=}} & {{e^{\eta q\left(t\right)+\gamma y\left(t\right)}E\left[e^{-\rho\left(T-t\right)}G\left(q\left(T\right),         y\left(T\right)\right)\right]}} \\ {{\ }} & {{=}} & {{e^{\eta q\left(t\right)+\gamma y\left(t\right)}V\left(q,         y,         \overline{{{\pi}} },         \overline {{{g}} },          t\right)}}\end{array}
$$  

WV/hen $\eta=1$ we have the case for nominal bonds. When $\eta=0$ wehave thecase of real bonds. When $\eta$ is intermediate,  this can be considered a case in which inflation affects the utility function of agents directly. A case in the literature is the one of money illusion

From the Feynman Kac formula,  we have that $V$ satisfies

$$
\begin{array}{l} {{V_{t}+V_{q}E\left[d q\right]+V_{y}E\left[d y\right]+V_{\overline{{\pi}} }E\left[d\overline {{\pi}} \right]+V_{\overline {{g}} }E\left[d\overline {{g}} \right]+\displaystyle\frac{1}{2}V_{q q}E\left[d q^{2}\right]+\frac{1}{2}V_{y y}E\left[d y^{2}\right]+}}\\ {{+V_{q y}E\left[d q d y\right]+V_{q\overline{{\pi}} }E\left[d q d\overline {{\pi}} \right]+V_{q\overline {{g}} }E\left[d q d\overline {{g}} \right]+V_{y\overline {{\pi}} }E\left[d y d\overline {{\pi}} \right]+V_{y\overline {{g}} }E\left[d y d\overline {{g}} \right]+V_{\overline {{\pi}} g}P\left[d y^{2}\right].}}\end{array}
$$  

With final condition

$$
V\left (q,          y,         \overline {{{\pi}} },         \overline {{{g}} },          T\right)=e^{-\eta q\left (T\right)-\gamma y\left (T\right)}
$$  

We can conjecture the following

$$
V\left (q,          y,         \overline {{{\pi}} },         \overline {{{g}} },          t\right)=e^{-\eta q (t)-\gamma y (t)+A (t; T)-\eta B (t; T)\overline {{{\pi}} }-\gamma C (t; T)\overline {{{g}} }}
$$  

Taking the first derivatives

$$
{\begin{array}{r l}{V_{t}}&{=\,         \,         \left[A^{\prime}\left (t; T\right)-\eta B^{\prime}\left (t; T\right){\overline {{\pi}} }-\gamma C^{\prime}\left (t; T\right){\overline {{g}} }\right]V}\\ {V_{q}}&{=\,         \,         -\eta V; V_{q q}=\eta^{2}V; V_{q y}=\eta\gamma V; V_{q\overline {{\pi}} }=\eta^{2}B\left (t; T\right) V; V_{q\overline {{g}} }=\eta\gamma C\left (t; T\right) V}\\ {V_{y}}&{=\,         \,         -\gamma V; V_{y y}=\gamma^{2}V; V_{y\overline {{\pi}} }=\gamma\eta B\left (t,          T\right); V_{y\overline {{g}} }=\gamma^{2}C\left (t,          T\right)}\\ {V_{\overline {{\pi}} }}&{=\,         \,         -\eta B\left (t,          T\right) V; V_{\overline {{\pi\pi}} }=\eta^{2}B\left (t,          T\right)^{2}V; V_{\overline {{\pi g}} }=\eta\gamma B\left (t,          T\right) C\left (t,          T\right) V}\\ {V_{\overline {{g}} }}&{=\,         \,         -\gamma C\left (t,          T\right) V; V_{\overline {{g g}} }=\gamma^{2}C\left (t,          T\right)^{2}V}\end{array}}
$$  
# Substituting and deleting the common $V$
$$
{\begin{array}{l} {{\displaystyle[A^{\prime}\left(t;T\right)-\eta B^{\prime}\left(t;T\right)\overline{{\pi}} -\gamma C^{\prime}\left (t; T\right)\overline {{g}} ]-\eta\overline {{\pi}} -\gamma\overline {{g}} -\eta B\left (t,          T\right)\left (\alpha_{\pi}-\beta_{\pi}\overline {{\pi}} \right)-\gamma C\left (t,          T\right)\left (\alpha_{\pi}+\beta_{\pi}\overline {{\pi}} \right)}}\\ {{\displaystyle+{\frac{1}{2}} \eta^{2}\sigma_{\pi}^{2}+{\frac{1}{2}}\gamma^{2}\sigma_{g}^{2}+{\frac{1}{2}}\eta^{2}B\left (t,          T\right)^{2}\sigma_{\overline {{\pi}} }^{2}+{\frac{1}{2}}\gamma^{2}C\left (t,          T\right)^{2}\sigma_{\overline {{g}} }^{2}}}\\ {{\displaystyle+\gamma\eta\sigma_{\pi}\sigma_{g}\rho_{\pi g}+\eta^{2}B\left(t,         T\right)\sigma_{\pi}\sigma_{\overline{{\pi}} }\rho_{\pi\overline {{\pi}} }+\eta\gamma C\left (t,          T\right)\sigma_{\pi}\sigma_{\overline {{g}} }\rho_{\pi\overline {{g}} }}}\\ {{\displaystyle+\gamma\eta B\left(t,         T\right)\sigma_{g}\sigma_{\overline{{\pi}} }\rho_{g\overline {{\pi}} }+\gamma^{2}C\left (t,          T\right)\sigma_{g}\sigma_{\overline {{g}} }\rho_{g\overline {{g}} }+\eta\gamma B\left (t,          T\right) C\left (t,          T\right)\sigma_{\overline {{\pi}} }\sigma_{\overline {{g}} }\rho_{\overline {{\pi g}} }}}\end{array}}
$$  

Factor out variables $\overline {{\pi}}$ and $\overline {{g}}$

$$
\begin{array}{r c l} {{\rho}} & {{=}} & {{\displaystyle-\eta\left[B^{\prime}\left(t;T\right)+1-\beta_{\pi}\right]\overline{{{\pi}} }-\gamma\left[C^{\prime}\left (t; T\right)+1-\beta_{g}\right]\overline {{{g}} }-\eta B\left (t,          T\right)\alpha_{\pi}-\gamma C\left (t,          T\right)}}\\ {{}} & {{}} & {{\displaystyle A^{\prime}\left(t;T\right)+\frac{1}{2}\eta^{2}\sigma_{\pi}^{2}+\frac{1}{2}\gamma^{2}\sigma_{g}^{2}+\frac{1}{2}\eta^{2}B\left(t,         T\right)^{2}\sigma_{\overline{{{\pi}} }}^{2}+\frac{1}{2}\gamma^{2}C\left (t,          T\right)^{2}\sigma_{\overline {{{g}} }}^{2}}}\\ {{}} & {{}} & {{\displaystyle+\gamma\eta\sigma_{\pi}\sigma_{g}\rho_{\pi g}+\eta^{2}B\left(t,         T\right)\sigma_{\pi}\sigma_{\overline{{{\pi}} }}\rho_{\pi\overline {{{\pi}} }}+\eta\gamma C\left (t,          T\right)\sigma_{\pi}\sigma_{\overline {{{g}} }}\rho_{\pi\overline {{{g}} }}}}\\ {{}} & {{}} & {{\displaystyle+\gamma\eta B\left(t,         T\right)\sigma_{g}\sigma_{\overline{{{\pi}} }}\rho_{g\overline {{{\pi}} }}+\gamma^{2}C\left (t,          T\right)\sigma_{g}\sigma_{\overline {{{g}} }}\rho_{g\overline {{{g}} }}+\eta\gamma B\left (t,          T\right) C\left (t,          T\right)\sigma_{\overline {{{\pi}} }}\sigma_{\overline {{{g}} }}\rho_{\pi\overline {{{g}} }}}}\end{array}
$$  

This is satisfied for all values of $\overline {{\pi}}$ and $\bar{g}$ if and only if the following system is satisfied

$$
\begin{array}{r l r}{0}&{{}\!=\!}&{\left[B^{\prime}\left (t; T\right)+1-\beta_{\pi}B\left (t,          T\right)\right]}\\ {0}&{{}\!=\!}&{\left[C^{\prime}\left (t; T\right)+1-C\left (t,          T\right)\beta_{g}\right]}\end{array}
$$  

And

$$
\begin{array}{r l r}{\rho}& {{}\!=}&{A^{\prime}\left(t;T\right)-\eta B\left(t,         T\right)\alpha_{\pi}-\gamma C\left(t,         T\right)\alpha_{g}} \end{array}
$$  
$$
\begin{array}{l} {{\displaystyle+\frac{1}{2}\eta^{2}\sigma_{\pi}^{2}+\frac{1}{2}\gamma^{2}\sigma_{g}^{2}+\frac{1}{2}\eta^{2}B\left(t,         T\right)^{2}\sigma_{\pi}^{2}+\frac{1}{2}\gamma^{2}C\left(t,         T\right)^{2}\sigma_{\overline{{g}} }^{2}}}\\ {{\displaystyle+\gamma\eta\sigma_{\pi}\sigma_{g}\rho_{\pi g}+\eta^{2}B\left(t,         T\right)\sigma_{\pi}\sigma_{\overline{{\pi}} }\rho_{\pi\overline {{\pi}} }+\eta\gamma C\left (t,          T\right)\sigma_{\pi}\sigma_{\overline {{g}} }\rho_{\pi\overline {{g}} }}}\\ {{\displaystyle+\gamma\eta B\left(t,         T\right)\sigma_{g}\sigma_{\overline{{\pi}} }\rho_{g\overline {{\pi}} }+\gamma^{2}C\left (t,          T\right)\sigma_{g}\sigma_{\overline {{g}} }\rho_{g\overline {{g}} }+\eta\gamma B\left (t,          T\right) C\left (t,          T\right)\sigma_{\overline {{\pi}} }\sigma_{\overline {{g}} }\rho_{\pi\overline {{g}} }}}\end{array}
$$  

With final conditions

$$
B\left (T,          T\right)=0; C\left (T,          T\right)=0; A\left (t; T\right)=0
$$  

The first two ODEs have solutions

$$
\begin{array}{r c l} {{B\left(t,         T\right)}} & {{=}} & {{\displaystyle\frac{1-e^{-\beta_{\pi}\left(T-t\right)}} {\beta_{\pi}}}}\\ {{C\left(t,         T\right)}} & {{=}} & {{\displaystyle\frac{1-e^{-\beta_{g}\left(T-t\right)}} {\beta_{g}}}}\end{array}
$$  

The last ODE has solution

$$
\begin{array}{r c l} {{(t,         T)}} & {{=}} & {{\displaystyle\left(-\rho+\frac{1}{2}\eta^{2}\sigma_{\pi}^{2}+\frac{1}{2}\gamma^{2}\sigma_{g}^{2}+\gamma\eta\sigma_{\pi}\sigma_{g}\rho_{\pi g}\right)\left(T-t\right)}} \\ {{}} & {{}} & {{\displaystyle+\left[\eta^{2}\sigma_{\pi}\sigma_{\overline{{\pi}} }\rho_{\pi\overline {{\pi}} }+\gamma\eta\sigma_{g}\sigma_{\overline {{\pi}} }\rho_{g\overline {{\pi}} }-\eta\alpha_{\pi}+\frac{1}{2}\frac{\eta^{2}\sigma_{\pi}^{2}}{\beta_{\pi}}+\frac{\eta\gamma\sigma_{\overline {{\pi}} }\sigma_{\overline {{g}} }\rho_{\overline {{\pi g}} }}{\beta_{\pi}+\beta_{g}}\right]\frac{1}{\beta_{\pi}}\left (\left (T-t\right)\right)}}\\ {{}} & {{}} & {{\displaystyle+\left[\eta\gamma\sigma_{\pi}\sigma_{\overline{{g}} }\rho_{\pi\overline {{g}} }+\gamma^{2}\sigma_{g}\sigma_{\overline {{g}} }\rho_{g\overline {{\pi}} }-\gamma\alpha_{g}+\frac{1}{2}\frac{\gamma^{2}\sigma_{g}^{2}}{\beta_{g}}+\frac{\eta\gamma\sigma_{\overline {{\pi}} }\sigma_{\overline {{g}} }\rho_{\overline {{\pi g}} }}{\beta_{\pi}+\beta_{g}}\right]\frac{1}{\beta_{g}}\left (\left (T-t\right)\right)}}\\ {{}} & {{}} & {{\displaystyle-\frac{1}{4}\frac{\eta^{2}\sigma_{\pi}^{2}} {\beta_{\pi}}B\left (t,          T\right)^{2}-\frac{1}{4}\frac{\gamma^{2}\sigma_{g}^{2}}{\beta_{g}}C\left (t,          T\right)^{2}-\frac{\eta\gamma\sigma_{\overline {{\pi}} }\sigma_{\overline {{g}} }\rho_{\pi\overline {{g}} }}{\left (\beta_{\pi}+\beta_{g}\right)}B\left (t,          T\right) C\left (t,          T\right)}}\end{array}
$$  

Setting $\eta=1$ provides the formula for $A (t,          T)$ in the text. Moreover,  the case $\eta=0$ corresponds to the real bond,  obtaining

$$
\begin{array}{c l}{\displaystyle\left (-\rho+\frac{1}{2}\gamma^{2}\sigma_{g}^{2}\right)(T-t)+\left[\gamma^{2}\sigma_{g}\sigma_{\bar{g}}\rho_{g\bar{g}}-\gamma\alpha_{g}+\frac{1}{2}\frac{\gamma^{2}\sigma_{g}^{2}}{\beta_{g}}\right]\frac{1}{\beta_{g}}\left ((T-t)-C\left (t,         \frac{1}{2}\right)\right).}\end{array}
$$  
# Teaching Note 4
# Interest Rate Derivatives
#

# The Notional Amount of Over-the-Counter Derivatives

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/1522c1eb598d9cfbcdbf0a79e249c90dabdd7ec1213a3716a8a7ab0da272cc9d.jpg)

Panel A.Millions of Us Dollars

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/616d286095da6074941d5d2b75e281bc47dd03a503c5fe560104f80650426cc2.jpg)

Panel B. Multiple of Global GDP

# Interest Rate Derivatives: Forwards and [[A Guide to the Front End and Basis Swap Markets#Forward Rate Agreements (FRAs) Overview|Forward Rate Agreements]]

 - Effective risk management is carried out using derivatives,  such as forward,  futures,  and swaps

 - Forward contracts and [[A Guide to the Front End and Basis Swap Markets#Forward Rate Agreements (FRAs) Overview|Forward Rate Agreements]] allow firms to lock in interest rates in the future

- A [[A Guide to the Front End and Basis Swap Markets#Forward Rate Agreements (FRAs) Overview|Forward Rate Agreement]](FRA) is a contract between two counter parties who agree at time O to exchange the following net payment at a future date $T_{2}$
-where $r_{n}(T_{1},          T_{2})$ is a $n$ -times compounded floating reference rate,  $f_{n}$ is a fixed rate,  $N$ is the notional,  and $\Delta=1/n$
·Example: Today $\left (T_{0}\right)$ is January 2,  2020 (we will treat this as January 1 …) and suppose a firm has a $\$ 100$ million receivable in six months on June 30,  2020. Ignoring overnight investing:
- If the firm will not need that cash immediately,  but,  say,  six month later,  it can lock-in an investment rate today for the future period $T_{1}=0.5$ is July 1,  2020 to $T_{2}=1$ isDecember 31,  2020 by entering into a [[A Guide to the Front End and Basis Swap Markets#Forward Rate Agreements (FRAs) Overview|Forward Rate Agreement]](FRA) with a bank. $^*$ Assume the bank quotes the (semi-annually compounded) annualized rate of $f_{2}=1.59\%$ When the firm receive $\$ 100$ million in six months $\left (T_{1}\right)$ it can invest it at the then current floating rate $r_{2}(T_{1},          T_{2})=r_{2}(0.5,         1)$ ,  which is not known today.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/e246247ef2e4e50f005c66a3352e7a42cef41fee938d44809d066af21ca4732c.jpg)
# Hedging Interest Rate Risk

Clearly,  using the banks offer locks in the rate $f_{2}$ for the period $T_{1}$ to $T_{2}$ for the firm,  as

$$
\begin{array}{l}{=\;\left\{\$ 100\;\mathsf{m i l i o n}\;\times\left[1+\displaystyle\frac{r_{2}(0.5,         1)}{2}\right]\right\}}\\ {\quad+\left\{\displaystyle\frac{N}{2}\times[f_{2}-r_{2}(0.5,         1)]\right\}}\\ {=\;\$ 100\;\mathsf{m i l i o n}\;\times\left[1+\displaystyle\frac{f_{2}}{2}\right]}\\ {=\;\$ 100\mathsf{m i l i o n}\times\left[1+\displaystyle\frac{0.0159}{2}\right]}\\ {=\;\$ 100.79\;\mathsf{m i l i o n}}\end{array}
$$  
- The question is: How does the bank determine the forward rate $f_{2}?$
- Through a simple trading strategy.
# Trading Strategy to Compute Forward Rate

Today (Time 0)

$(a)$ Borrow $\mathbb{S}100~\mathsf{m}$ Sell short \$99.180 m of T-bills atrate $r_{2}(0.5,         1)$ $\begin{array}{r}{\mathsf{P a y\$ 100\m}\times\left (1+\frac{r_{2}(0.5,         1)}{2}\right)}\end{array}$ maturingat $T_{1}$ $(b)$ Close short position

Buy $\begin{array}{r}{M=1.0079=\frac{\$ 99.180}{\$ 98.400}}\end{array}$

Of T-bills maturing at $T_{2}$

Receive $1.0079\times\$ 100~\mathsf{m}$

Enter [[A Guide to the Front End and Basis Swap Markets#Forward Rate Agreements (FRAs) Overview|FRA]] with Firm $\begin{array}{r l r}&{}&{\mathsf{P a y~}_{\mathsf{2}}^{\mathsf{100~m}}\times\left[f_{2}\left (0,         0.5,         1\right)-r_{2}\left (0.5,         1\right)\right.}\\ &{}&{\mathsf{T o t a l~N e t~C a s h~F l o w=0~}\quad\mathsf{T o t a l~N e t~C a s h~F l o w=}}\end{array}$ 一 Total Net Cash $\mathsf{F l o w}=0$ 0

 - The bank is perfectly hedged.

- Note also that the quoted forward rate is effectively implicit in the ratic
$$
M=\frac{Z (0,         0.5)}{Z (0,         1)}=1+\frac{f_{\mathrm{2}}}{2}
$$  

In the first step of the trading strategy

- This fact leads to the notion of the forward discount factor,  given by $1/M$
# The Forward Discount Factor

 - The forward discount factor at time $t$ defines the time value of money between two future dates,  $T_{1}$ and $T_{2}>T_{1}$

- Given the discount factors $Z (t,          T_{1})$ and $Z (t,          T_{2})$ ,  the forward discount factor is given by
$$
F (t,          T_{1},          T_{2})=\frac{Z (t,          T_{2})}{Z (t,          T_{1})}
$$  
- Indeed,  note that in the example $Z (0,         0.5)\,         =\,          0.9918$ and $Z (0,         1)\,         =\,          0.9840$ implying a forward discount factor
$$
F (0,         0.5,         1)=\frac{Z (0,         1)}{Z (0,         0.5)}=0.9921
$$  
- From any discount factor (forward or not),  we can compute the $n$ -times compounded rate as
$$
F_{n}\left (t,          T_{1},          T_{2}\right)=n\times\left (\frac{1}{F\left (t,          T_{1},          T_{2}\right)^{\frac{1}{n\times\left (T_{2}-T_{1}\right)}}}-1\right)
$$  

For instance,  in the example we have

$$
F_{2}(0,         0.5,         1)=2\times\left (\frac{1}{F\left (0,         0.5,         1\right)^{\frac{1}{2\times 0.5}}}-1\right)=1.59\%,         
$$  
# The Spot Curve and the Forward Curve
- The forward curve gives the relation between the forward rate $f (0,          T,          T+\Delta)$ and the time of the investment $T$ . Curves on January 2,  2020
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/311a0bd9a819131bc3d91eed4dd9d1055238f9af47a3269a02bb24fd8914c56f.jpg)
Data Source: US Treasury.
# The Value of a Forward Rate Agreement
- In previous example,  suppose 3 months later,  on April 1,  2020,  the firm decides to close its [[A Guide to the Front End and Basis Swap Markets#Forward Rate Agreements (FRAs) Overview|FRA]] - As interest rates changed between January and April,  so did the value of the FRA. -Recall bank's earlier strategy:
$(a)$ short one T-bill maturing at $T_{1}$ and $(b)$ long $M=1.0079$ T-bills maturing at $T_{2}$ This portfolio $(a)+(b)$ replicates the cash flow that the firm will receive. $\Longrightarrow$ its value at $t=$ value of the [[A Guide to the Front End and Basis Swap Markets#Forward Rate Agreements (FRAs) Overview|FRA]] for the firm. Thus:
$\textbf{t}=V^{F R A}\left (t\right)=M\times Z (t,          T_{2})-Z (t,          T_{1})$
- On April 1,  2020 $(=t)$ ,  we had $Z (t,          T_{1})=\$ 0.9993$ and $Z (t,          T_{2})=\$ 0.9981$ . Therefore
VFRA (t) =1.0079 x $: Z (t,          T_{2})-Z (t,          T_{1})=1.0079\times\$ 0.9981-\$ 0.9993=\$ 0.00$ 0671 million - => On April 1,  2020,  the [[A Guide to the Front End and Basis Swap Markets#Forward Rate Agreements (FRAs) Overview|FRA]] initiated 3 months earlier was worth \$671,  176.83 to the firm.
In general,  using the definition $1+f_{n}(t,          T_{1},          T_{2})\Delta=Z (t,          T_{1})/Z (t,          T_{2})$ ,  we have
$$
\begin{array}{l} {{\displaystyle{\cal V}^{F R A}(t)~=~{\cal N}\times{\cal Z}(t,         T_{2})\times\left[{\cal M}-\frac{{\cal Z}(t,         T_{1})}{{\cal Z}(t,         T_{2})}\right]}} \\ {{~=~{\cal N}\times{\cal Z}(t,         T_{2})\times\Delta\times\left[f_{n}(0,         T_{1},         T_{2})-f_{n}(t,         T_{1})\right]}} \end{array}
$$  
# Changing Yield Curve

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/2149aa3314795f714baea328b93cdec2cdce58d983c690200e4e1cc3c6112cd4.jpg)

# Interest Rate Derivatives: Swaps
- A plain vanilla fixed-for-floating interest rate swap is an agreement between two counterparties to exchange cash flows at $T_{1},         \,          T_{2},         …,         \,          T_{n}=T$ With $T_{i}=T_{i-1}+\Delta$ according to
$T_{i}=N\times\Delta\times[r_{n}(T_{i-1})-c]$
Where $n=1/\Delta$ is the reference rate compounding frequency
- The constant $c$ is called swap rate.
- How do we determine the Value of a Swap?
- At inception,  the value is zero,  as the counter parties agree to swap future payments,  not today - After inception,  as the floating rate changes,  so does the value of the swap
- Consider the party with net cash flow (7). This party is effectively long a floating rate bond $(P_{F R}(t,          T))$ and short a fixed rate bond with coupon $c\left (P_{c}(t,          T)\right)$
$-\implies$ the value of the swap is
$$
V^{s w a p}(t; c,          T)=P_{F R}(t,          T)-P_{c}(t,          T)
$$  
-At every $T_{i}$ ,  the value of $P_{F R}(T_{i},          T)=100$ . Therefore,  at these times
$$
C,          T)=100-\left (\frac{c}{2}\times 100\times\sum_{j=i+1}^{M}Z (T_{i},          T_{j})+Z (T_{i},          T_{M})\times 100\right)
$$  
# The Swap Rate and the Swap Curve

How is the swap rate $c$ determined?

The swap rate $c$ is given by that number that makes $V^{s w a p}(0; c,          T)=0$ in (8)

- Rewriting the equation for any payment frequency $n$ and payment dates $T_{1},         \,         \dots\,          T_{M}$ ,  wehave
$$
T)=100-\left (\frac{c}{n}\times 100\times\sum_{j=1}^{M}Z (0,          T_{j})+Z (0,          T_{M})\times 100\right)=
$$  
- Solving this equation for $c$ we find
$$
C=n\times\left (\frac{1-Z\left (0,          T_{M}\right)}{\Sigma_{j=1}^{M}Z\left (0,          T_{j}\right)}\right)
$$  
- The swap curve at time $t$ is the set of swap rates (at time $t$ ) for all maturities $T_{1},         \,          T_{2},         \,         …,         \,          T_{M}$ - I denote the swap curve at time $t$ by $c\left (t,          T_{i}\right)$ for $i=1,         …,         M.$
# The Swap Curve and the "Classic" [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] Curve
- The swap curve implicitly contains the discount factors $Z (0,          T_{i})$ that market participants use to quote swaps in the OTC market.
From the swap curve,  we can then bootstrap out such discounts by inverting (11)
$$
Z\left (t,          T_{1}\right)\;=\;{\frac{1}{1+{\frac{c (t,          T_{1})}{n}}}}
$$  

While for $i=2,         …,          M$

$$
Z\left (t,          T_{i}\right)\;=\;{\frac{1-{\frac{c (t,          T_{i})}{n}}\times\Sigma_{j=1}^{i-1}Z\left (t,          T_{j}\right)}{1+{\frac{c (t,          T_{i})}{n}}}}
$$  

The resulting yield curve is called [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curve.

# Treasury and Swap Discount and Yield on January 4,  2005

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/4795f4b9e88b9e8683e0b72a3e0437466e8ed33fe2b6360439c75e97f3b934bd.jpg)

DataSource: Federal Reserve andCRSP

# The 5-year Zero Coupon Treasury and Swap Yield

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/3e62082eddc8b6ce9bb08e1f883e51c12707ded39bc8dfb78fd645ea82c7884a.jpg)

DataSource: Bloomberg and CRS P

# Swap Spread Trades and the Risk in Convergence Trades
- Today is June 30,  2006,  and we are looking to make a profit on the swap spread.
 - The market presented the following data:
- 3-month LIBOR: 5.5081% - 3-month repo rate: $5.27\%$ - 5-year swap rate: $5.69\%$ - 5-year T-note with a $5.125\%$ coupon priced at \$100.1172,  and yield-to-maturity $5.10\%$
The swap spread equals the yield to maturity of the Treasury note minus the swap rate
$$
S S=5.69\%-5.10\%=0.59\%=59~b p
$$  
- That is,  receiving the fixed rate from the swap and paying the yield in a short T-notes would return 59 basis points per year.
- To secure this return of 59 basis points,  we have to pay the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] rate,  as part of the swap,  and receives the repo rate,  as part of a reverse repo transaction to short the T-note.
# The LIBOR-Repo Spread

The spread between [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] and repo (LRS) is

$$
L R S=5.5081\%-5.27\%=0.2381\%
$$  

The net spread is $S S-L R S=35.19$ bps.

- This spread is not very large,  but the LIBOR-repo spread has been historically relatively stable at around 21 bps and so this net spread $\left (S S-L R S\right)$ still appears a relatively safe trade. - Using daily data from Jan 2000 to Jun 2006,  the distribution of the LlBOR-repo spread is as
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/c7208c1dc23115224d69814caaf6baf565830577ae063ed4466ed3eebcda4c37.jpg)
Data Source: Bloomberg.
- Even in extreme circumstances,  the net spread would be at least $0.59\%-0.37\%=22$ bps
# The Trade

We finally decided to go ahead,  and enter into the following transactions i

1. Short the 5-year bond through a reverse repo transaction. In cash flow terms,  the fund would receive the repo rate and pay the coupon.
1. Enter into a fixed-for-floating swap,  in which we would receive fixed and pay LIBOR
# Reverse Repo
- We want to set up a \$100 million trade. Thus,  we need to sel
$$
N={\frac{\$ 100{\mathsf{m i l i o n}}}{100.1172}}=998,         829{\mathsf{\; T r e a s u r y\; n o t e s\;}}({\mathsf{f o r\;}}\$ 100{\mathsf{\; p}}
$$  
-Assuming haircut $=\,          0$ ,  we then borrow $N\,         =\,          998$ ,  829 5-year T-notes from the repo dealer,  sells them in the cash market for \$1 oo million,  and gives this cash to the repo dealer.
- Assume we enter into a term reverse repo with 3-months maturity,  and rolls it over every three months.
- Because the repo dealer keeps the \$i 00 million at every reset date,  our total cash flow every quarteris
$\mathsf{C F}(t)=\left\{\begin{array}{l l}{\frac{\$ 100\ \mathsf{m m}}{4}\times r (t-0.25)-N\times 100\times\frac{5.125\%}{2}}\\ {\frac{\$ 100\ \mathsf{m m}}{4}\times r (t-0.25)}\end{array}\right.$ if $t$ is a coupon date Reverse repo otherwise
# The Trade
# Fixed-for-Floating Swap
- We have to enter into a 5-year,  fixed-for-floating swap in which we pay the 3-month [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] rate and receive the 5-year fixed swap rate.
\* In a plain vanilla fixed-for-floating swap,  the floating payments occur at quarterly frequency,  while the fixed payments occur at semi-annual frequency,  therefore exactly matching the payment frequency of the reverse repo transaction discussed earlier.
-Denoting $\ell (t)$ is the 3-month [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] rate at time $t$ ,  the swap cash flows are then given by $\mathsf{C F}(t)=\left\{\begin{array}{r}{\underbrace{\$ 100~\mathsf{m m}\times\frac{5.69\%}{2}-\frac{\$ 100~\mathsf{m m}}{4}\times\ell (t-0.25)}}\\ {-\frac{\$ 100~\mathsf{m m}}{4}\times\ell (t-0.25)}\end{array}\right.$ if $t$ is fixed payment date Swap otherwise
# The Quarterly Cash Flow
- It is useful to decompose the quarterly cash flow in two components,  the swap spread (SS) component and the LIBOR-repo spread (LRS) component.
- We have that every six months,  the swap spread component of the cash flow is
$$
=\;\$ 100\;{\sf m m}\times\frac{5.69\%}{2}-N\times 100\times\frac{5.125\%}{2}\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\
$$  

·- The second component is the LIBOR-repo spread,  which every quarter is given by

$$
\mathsf{C F~e v e r y~t h r e e~m o n t h s}\,         ={\frac{\$ 100~m m}{4}}\times (r (t-0.25)-\ell (t-0.25)).
$$  
- For instance,  on June 30 the $r (0)=5.27\%$ while $\ell (0)=5.5081\%$ implying
 - Since the LIBOR-repo spread is relatively stable,  we expect to receive approximately
$$
\begin{array}{r l}{\textsf{l e t c a s h f l o w p e r y e a r}=}&{2\times\$ 285,         499.73-4\times\$ 59,         52}\\ &{=\$ 332,         898}\end{array}
$$  

…. But risk may be just around the corner

# The Swap Spread and LIBOR-Repo Spread

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/9238c2649daad6ff34974cdc4bef8dfd60d8cd1a6f49b4945fae9dbcc6a19092.jpg)

Source: Federal Reserve and Bloomberg.

# Net Cash Flows from Swap Spread Trade

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/65e4fb507e77c84d81edad8f6919acae57723e4535d3d30a177b10b369175cca.jpg)

# Unwinding the Position?
- Given the large negative quarterly payments due to the increase in the LIBOR-repo spread,  we may start thinking about whether we should unwind their position.
- First question is: What is the value of the position?
The Value of the Reverse Repo
-- The ex-coupon value of the repo position on rollover quarter $t$ is
$t=\$ 100\mathsf{m m}-N\times P_{n o t e}(t,          T)$
-where $P_{n o t e}(t,          T)$ is the value of the T-note at time $t$  - The Value of the Fixed-for-Floating Swap - As time passes and interest rates fluctuate,  the value of the swap changes. We have
-where $P_{F R}(t,          T)$ is the LIBOR-based floating rate bond,  and $P_{c}(t,          T)$ is the fixed rate coupon bond with coupon $c=5.69\%=g$ swap rate,  given by
$$
P_{c}(t,          T)=\frac{100\times 5.69\%}{2}\times\sum_{i=1}^{n_{t}}Z (t,          T_{i})+100\times Z (t,          T_{n_{t}})
$$  
-Here,  $Z (t,          T_{i})$ is the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] discount curve (see next Figure)
# The [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] Curve: June 2006 - June 2008

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/143755d223e217eaf8ca2928af96074ca6d27115893c6b0c5b63f5710856ef2b.jpg)

# The Surprise
- On March,  2008,  as we start unwinding the position,  we have a good news: the value of the swap is now \$10.21 million.
- Indeed,  the LlBOR yield curve now ranges between $2.7\%$ at 1 month,  and $3.3\%$ at 5 years,  which pushes up the value of the fixed part of the swap to \$1 io. 21 million. - Because the floating part is always equal to $\$ 100$ million at reset dates,  by closing the position we would obtain an inflow of \$10.21 million.
- However,  as we close the swap,  we have also to close the reverse repo
- The bad news is that now the T-note we are shorting is trading at \$110.23 - Given the accrued interest of $\Updownarrow 1.28$ ,  the total losses from the short position amount to $\$ 100$ million 一 $N\times\$ 111.51=-\$ 11.38$ million.
- In sum,  to close the position on March,  2008,  we receive \$10.21 million from the swap,  but we have to pay \$11.38 million on the reverse repo,  for a total loss of \$1.16 million. This number far outweighs the cumulative cash flows we have so far received.
# The Swap Spread Trade Value

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/8169240a592b485b55a359a25d1f24f055fc7afde840d98b1bd3a7049250ddf9.jpg)

# Conclusion: The Risk in Relative Value Trades
1. Cost of Carry,  due to the variation in the cost-of-carry,  i.e. the cash-flow per period that a trade is expected to generate.
- In swap spread trade,  it is the difference between the swap spread and the LIBOR-repo rate - An arb it rage urs may find that holding up the trade is generating cash outflows that outstrip the expected gain from convergence.
 1. Market Risk,  that is,  the potential capital losses due to the variation in the underlying spread. - In a relative value trade speculators bet on the convergence of the underlying spread to an average level. - However,  such spread may either not converge to the average level,  or just widen for a while
1. Funding Risk,  that is,  the ability to hold up the position until maturity
- Even for those (arbitrage) trades in which a hedge fund is certain to make profits if it holds the position until maturity,  it is quite possible that the spread may widen further before it narrows. - If the spread widens,  then the hedge fund would potentially suffer large capital losses.  - It is then key for the hedge fund survival that it has sufficient capital in cash or a large borrowing capacity that makes it able to withstand the capital loss.
# Funding Risk during the Crisis?
- Funding risk is especially important during periods of crisis,  for a number of reasons
1. All risk-based spreads - the spreads between a risky securities and Treasury securities - tend to widen,  as investors dump risky securities and purchase safe U.S. Treasuries
$-\implies$ Relative value trades experience large capital losses
1. Lenders are more wary of default risk,  and increase haircuts,  margins,  etc.,  making capital effectively more scarce
- It becomes harder for a hedge fund to keep up the position.
1. Investors withdraw money from hedge funds,  if they can - Hedge funds must liquidate positions,  at a loss.
·- Next figure shows negative swap spreads during the crisis for long term swaps
# Negative Swap Spreads during the Crisis

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/486fd7fd6a1adbf391ad80885ec4e628c8daddd3cbdce9e8430cc2042a235a35.jpg)

# Negative Swap Spread and No Arbitrage

Negative swap spreads are a textbook arbitrage opportunity: - Buy Treasury and pay fixed in a fixed for floating swap

$$
T=\left (c^{T-B o n d}-c^{s w a p}\right)+\left (L I B O R_{t}-R E P O_{t}\right)
$$  
- Both terms are positive. The first because of the negative swap spread,  and the second because [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] is the rate for un collateralized borrowing,  while REPO is the rate for collateralized borrowing.
- This is a textbook arbitrage opportunity $i f$ an arb it rage ur can hold the position to maturity
 - The risk of the spread increasing further,  generating severe capital losses,  may make arb it rage urs wary of entering the market.
At reset dates. The value of the trade is
$$
V_{t}^{T r a d e}=(P_{c}^{T-B o n d}(t,          T)-P_{c}^{S w a p}(t,          T))
$$  
- If the swap spread becomes even more negative,  e.g. the yield on T-bond increases while the one of the swap remains the same,  then $V_{t}^{T r a d e}$ decreases even more.
# Negative Spreads Continue

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/bbd5b110214cefb075bbee81556810ca74a28aa89f23308aed097dbb6fd28119.jpg)

Source: Federal Reserve Board,  H0.\1 release

Chart 1 from Boyar chen ko et. Al. (2018) "Negative Swap Spreads,  " Federal Reserve Bank of New York Economic Policy Review

# Violation of no-arbitrage during the 2007 - 2008 crisis
- The violation of no-arbitrage rules was widespread during the recent crisis
 - For instance,  another simple arbitrage restriction that was violated was the covered interest rate parity (CiP)
- The simple rule in the foreign exchange market according to which the forward exchange rate $F_{t,          T}$ equals the spot $M_{t}$ times the ratio of investment rates in domestic versus foreign country. -For instance,  if $M_{t}=U S/E U R O$ exchange rate,  then
$$
F_{t,          T}=M_{t}e^{(r_{\Updownarrow}-r_{e})(T-t)}
$$  

Next figure shows the difference

$$
F_{t,          T}^{d a t a}-F_{t,          T}
$$  

Before and during the crisis.

# CIP Violation during the 2007 - 2009 Financial Crisis: Euro / Dollal

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/94801829ce3dd2037e2867b314eeea380cdc0addf38e78b90dc86d395eea655c.jpg)

# CIP Violation during the 2007 - 2009 Financial Crisis: UKP / Dollal

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/c05e882bf46886cf97eaeddce6636657121113006355e0a1980ad8e0e318e189.jpg)

# Why Did Covered Interest Rate Parity Fail during the 2007-2009 Crisis?
- Holding US Treasuries has its own “convenience yield" when everyone needs cash collateral.
During the crisis,  from the graph,  we had the following violation:
$$
F_{t,          t+m}^{d a t a}>F_{t,          t+m}=M_{t}\ e^{(r_{\Updownarrow}-r_{e}) m}
$$  
- Recall that in this case,  an arbitrage trade requires the following
(a) Short Euro forward; (b) borrow dollars (or sell US Treasuries); (c) change them into Euro; (d) invest in Euro (or buy Euro bonds)
But point (b) failed during the crisis,  as:
1. Increase in credit risk concerns impaired the ability of any financial institution to borrow; 2. Holding safe dollars (US Treasuries) is valuable during a financial crisis for [[Class Note 10 Liquidity and Class Note 10 Liquidity and Liquidity Managementliquidity management|liquidity management]] - US Treasuries are the only collateral accepted for short-term lending transactions. - It is very valuable to hold on to them for future cash management
# Cross-Currency Basis Risk after the Crisis

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/c0148955112dd7b6ccc46589b25bc4e00b87fe8067b046a7ce1ae3ffc23398a5.jpg)

Figure 5 from Du,  Tepper,  and Verdelhan (2017),  “Deviations form Covered Interest Rate Parity,  " working paper.

# Issues with LIBOR

Until January 31,  2014: British Bankers Association (BBA) LlBOR

- Survey of a panel of banks - Banks could underestimate their borrowing costs - Conflict within the bank: impact of [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] setting on derivatives trading
Now ICE LIBOR
- ICE now the benchmark administrator - Regulator in UK: Financial Conduct Authority (FCA) - Rules for fall-back rates if there are issues
# Alternatives

SOFR: "Secured Overnight Financing Rate'

-ARRC: Alternative Reference Rates Committee

Uthers:

- SONlA (Sterling Over Night Indexed Average) - EONlA (Euro Overnight Index Average) - TONAR (Tokyo Overnight Average Rate) -- SARON (Swiss Average Rate Over-Night) - Measure of overnight secured borrrowing. - Collateralized US Treasuries in the repo market. - Very liquid and likely resilient markets: \$1 trillion in daily volume - Contrast: USD [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] three-month tenor: about $\$ 1$ billion - Published by New York Fed. Along with 30-day,  90-day and 180-day averages
# Transition

·[[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] market: $\mathbb{S}200+$ trillion of financial transactions contracts reference LlBOR

- [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] permeates many contracts for in securities markets and the corporate world: leases,  debt;
- Derivatives market with Central Clearing Partners (e.g. CME .. )
- Cleared US Dollar interest rate swap contracts at CME: move to SOFR discounting - Intercontinental Exchange (ICE) Benchmark Administration: USD [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] benchmarks will stopped
- Fannie and Freddie: have moved bo SOFR contracts
- New York Fed: conducts repo and reverse repo through tri-party repo
# SOFR Derivatives

As an example: at the CME

- Futures: 3-month and 1-month. Using compounding or simple averages.
- Term SOFR Reference rates based on futures contracts
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/b905e0214568db6336c8ee10dff43269114bceabfc920c76eb8fc5384d19d252.jpg)
Some History
# Overnight Index Swaps (Is)
- In a OlS,  the two counter parties agree to exchange fixed for floating payments,  where the floating payment is tied to the cumulative return from an overnight rate
- Federal funds rate,  SOFR in US. Europe: short-term rate (ESTR),  (formerly Euro OverNight Index Average (EONlA) rate).
- Given a notional $N$ ,  the floating rate payment at time $T_{i}$ is
$$
C F\left (T_{i}\right)=N\left (\prod_{j=1}^{n_{j}}\left (1+r_{t_{j}}\delta\right)-1\right)
$$  

 - where $\delta$ is the daily interval,  $r_{t}$ is the reference (annualized) overnight rate,  and $n_{j}$ is the number of days between reset periods.

 - The day count convention is normally Actual/360

 - In the continuous time limit $(\delta\to 0)$ ,  we have that

$$
C F\left (T_{i}\right)=N\left (e^{\int_{T_{i-1}}^{T_{i}}r (u) d u}-1\right)
$$  
- Is with maturity less than 1 year have only one payment at the maturity.
Is with longer maturities have normally quarterly payments
# What is the value of Is?

·- The value of Is is the difference between the floating leg and the fixed leg

$$
V_{t}^{O I S}=V_{t}^{F l o a t i n g}-V_{t}^{F i x e d}
$$  
- Floating Leg: At reset dates,  and assuming the payment of a principal at maturity of the swap. The value of the floating leg is par.
-- Indeed,  investing the notional $N$ in the overnight index daily gives at $T_{i}$
$$
N\,         \prod_{j=1}^{n_{j}}\left (1+r_{t_{j}}\Delta\right)=C F\left (T_{i}\right)+N
$$  

$-\implies$ we can replicate the floating payments,  plus a residual of notional at maturity $T_{i}$ ,  withan investment $N$ at time O.

-It follows

$$
V_{0}^{F l o a t i n g}=N
$$  
- Fixed leg: Given a proper discount function $Z^{O I S}\left (0,          T_{i}\right)$ ,  we obtain
$$
V_{0}^{F i x e d}=N\; c\;\Delta\;\sum_{i=1}^{n}Z^{O I S}\left (0,          T_{i}\right)+N\; Z^{O I S}\left (0,          T_{n}\right)
$$  

 - The value of the contract at inception is zero,  $V_{0}^{O I S}=0$

 - It follows from (18) then that

$$
V_{0}^{O I S}=V_{0}^{F l o a t i n g}-V_{0}^{F i x e d}=0
$$  

This equation implies that the swap rate $c$ can be computed from

$$
1=c\,         \Delta\,         \,         \sum_{i=1}^{n}Z^{O I S}\left (0,          T_{i}\right)+Z^{O I S}\left (0,          T_{n}\right)
$$  

Which gives

$$
C (T_{n})=\frac{1}{\Delta}\frac{1-Z^{O I S}(0,          T_{n})}{\Sigma_{i=1}^{n}\,          Z^{O I S}\left (0,          T_{i}\right)}
$$  

 - where we now emphasize that the coupon rate $c$ is for a swap with maturity $T_{n}$ ,  and thus write $c (T_{n})$

# Is Discount Curve
- Given the Is coupon rates $c\left (T_{i}\right)$ for every maturity $T_{i}$ ,  we can bootstrap the OlS zero-coupon curve from (20).
We obtain the relation:
$$
Z^{O I S}\left (0,          T_{i}\right)=\frac{1-c\left (T_{i}\right)\,         \,         \Delta\,         \,         \Sigma_{j=1}^{i-1}\,          Z^{O I S}\left (0,          T_{j}\right)}{1+c\left (T_{i}\right)\Delta}
$$  
- Recalling,  however,  that OlS with maturity less than or equal to 1 year generally have only one payment.
- Next Figure shows an example of boots trapping from OlS quotes,  on January 2,  2009. Panel A reports the original Is quotes from Bloomberg. Panel B uses the quotes from Panel A along with bootstrap methodology (23) and defines the OlS discount function $Z^{O I S}(0,          T)$
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/ec3ed89c2ce67670c671be4a57173f73adcefef91fe9e9c7fa1c7402b854cbe3.jpg)
Data Source: Bloomberg
# Is and [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] Discount Curve on January 2 nd,  2007

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/8a7e2bbbeaa4344066c0d2e21134d4024c427927c017911b015731e5ca825d94.jpg)

- However,  if we try after the crisis,  we obtain the following figure.
# Is and [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] Discount Curve on January 2 nd,  2009

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/44af31ac1c8e3f276b11a8cc9bccbb7efde05aae36bd9e13fb73cee79c0ed0a2.jpg)

Data Source: Bloomberg

Which are quite different.

# Caps,  Floors and Collars

A cap pays a stream of payments at $T_{i},         \,          i=1,         ..,          n$ with $T_{i+1}=T_{i}+\Delta$ where

$$
C F\left (T_{i+1}\right)=\Delta\times N\times\operatorname*{max}{\left (r_{n}\left (T_{i},          T_{i+1}\right)-r_{K},          0\right)}
$$  

 - where $\Delta$ is the time interval between payments,  $N$ is the notional and $r_{n}\left (T_{i},          T_{i+1}\right)$ is the $n$ -times compounded [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] rate.

A floor pays

$$
C F\left (T_{i+1}\right)=\Delta\times N\times\operatorname*{max}\left (r_{K}-r_{n}\left (T_{i},          T_{i+1}\right),          0\right)
$$  
# Black's Formula for Caplet Valuation
- It is market practice to use Black's model to value Caps and Floors
 - The main assumption is that under risk-adjusted probabilities (called “forward risk neutral probabilities"),  the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] rate has a log-normal distribution:
$$
\ln\left (r_{n}\left (T_{i},          T_{i+1}\right)\right)\sim N\left (\mu_{i},         \sigma_{f,          i+1}^{2}T_{i}\right)
$$  
- Where we assume $\sigma_{f,          i+1}$ is a constant volatility and the subscript $i+1$ is maturity of the caplet.
 - The valuation formula is then the following:
$$
\mathsf{c a p l e t}(T_{i+1})=\Delta\times N\times Z\left (0,          T_{i+1}\right)\left[f_{n}(0,          T_{i},          T_{i+1})\mathcal{N}\left (d_{1}\right)\right.
$$  

 - where $f_{n}(0,          T_{i},          T_{i+1}$ is the forward rate,  and

$$
L_{1}=\frac{\ln\left (f_{n}(0,          T_{i},          T_{i+1})/r_{K}\right)+\sigma_{f,          i+1}^{2}T_{i}/2}{\sigma_{f,          i+1}\sqrt{T_{i}}};\quad d_{2}=d_{1}-\sigma_{f,          i+1}
$$  
- Notice: We discount the payoff using $Z\left (0,          T_{i+1}\right)$ and not $Z\left (0,          T_{i}\right)$ as the cash flow is realized at time $T_{i+1}$
# Example
- On November 1,  2004. Consider a 1-year,  quarterly cap with strike rate $r_{K}=2.555\%$
 - Assume this cap is trading at volatility $\sigma_{f}=23.5\%$
 - The current LlBOR discount curve is as follows
- From the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] curve,  we can compute the quarterly compounded forward rates:
- Forward Discount Factors
$$
F (0,          T_{i-1},          T_{i})=\frac{Z (0,          T_{i})}{Z (0,          T_{i-1})}
$$  
- Forward rates
$$
F_{4}(0,          T_{i-1},          T_{i})=4\times\left (\frac{1}{F (0,          T_{i-1},          T_{i})}-1\right)
$$  

We obtain

$$
F_{4}(0,         0.25,         0.5)=2.4562\%;\ f_{4}(0,         0.5,         0.75)=2.6932\%;
$$  
# Example (cntd.)

The last input in the Black's formula is the volatility $\sigma_{f}\times\sqrt{T_{i}}$ - From the quoted volatility $\sigma_{f}=23.5\%$ ,  weobtain

$$
\begin{array}{r l}{\sigma_{f}\sqrt{T_{1}}\ =\ 23.5\%\sqrt{0.25}=11.75\%;}\\ {\sigma_{f}\sqrt{T_{2}}\ =\ 23.5\%\sqrt{0.50}=16.62\%;}\\ {\sigma_{f}\sqrt{T_{3}}\ =\ 23.5\%\sqrt{0.75}=20.35\%.}\end{array}
$$  
- At this point we have all the information to compute the value of each caplet in the cap ·In particular,  using the formula for $d_{1}$ and $d_{2}$ weobtain
$$
\begin{array}{r l r}&{}&{d_{1}(0.5)\;=\;-. 2770;\,          d_{2}(0.5)=-. 3945}\\ &{}&{d_{1}(0.75)\;=\;. 4000;\,          d_{2}(0.75)=. 2338}\\ &{}&{d_{1}(1)\;=\;=. 7218;\,          d_{2}(1)=0.5183}\end{array}
$$  
# Example (cntd.)

Then

Caplet (0.50) $\begin{array}{r l}&{=\;\Delta\times N\times Z\left (0,         0.50\right)\left[2.4562\%\times\mathcal{N}\left (d_{1}(. 50)\right)-2.5554\right.}\\ &{=\; 0.0184}\\ &{=\;\Delta\times N\times Z\left (0,         0.75\right)\left[2.6932\%\times\mathcal{N}\left (d_{1}(. 75)\right)-2.555\right.}\\ &{=\; 0.0617}\\ &{=\;\Delta\times N\times Z\left (0,         1.0\right)\left[2.8987\%\times\mathcal{N}\left (d_{1}(1.0)\right)-2.555\%\times\mathcal{N}\left (d_{1}(1.0)\right)\right]}\\ &{=\; 0.1057}\end{array}$ 50))] caplet (0.75) caplet (1.0)

 - and we obtain the value of the l-year cap:

$$
C a p (1 Y)=0.0184+0.0617+0.1057=0.1859
$$  
# Flat Vol at ili ties and Forward Vol at ili ties

Caps and floors are quoted in terms of flat vol at ili ties - The volatility across caplets is kept constant for each cap.

 - For example,  from Bloomberg (code SSRC),  one finds quotes such as
Table 1: Quotes of Caps and Swaptions on November 1,  2004
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/bdd461eaab545bb6188b67a7bccf74ca8cc19e7ea91e638775f38b2f653ee744.jpg)
Source: Bloomberg.
- Each entry is a flat volatility for an "at-the-money" instrument,  meaning that its strike rate (equal for all the caplets) is the swap rate with the same maturity of the cap.
 - The payment frequency of the underlying caps and floors is 3 months
- Since the first payment at horizon 3 months is known at time O,  it is practice to set this caplet equal to zero.
# Flat Vol at ili ties and Forward Vol at ili ties

As an example,  from Table 1,  we obtain the following prices for caps

Table 2: Cap Prices and Vol at ili ties

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/b494600b0a6bab778090c95c3cc2c0dc698b4f67de728111b430c2a01c36cdf8.jpg)

Data Source: Bloomberg.

# Flat Vol at ili ties and Forward Vol at ili ties

 - Issue: Consider the caps with maturities $T=0.5$ $T=0.75$ $T=1$

- The $T=0.5$ cap has only one caplet with (implied ) volatility 21.156% -The $T=0.75$ cap has two caplets each computed with (implied) volatility $22.066\%$ -The $T=1$ cap has three caplets each computed with (implied) volatility 23.500%
 - It looks like the same caplet would have a different price,  depending on which cap it belongs to
- Instead,  it is only a quoting convention,  and due to the distinction between Flat (or quoted) volatility and Forward Volatility
- The Forward Volatility (or spot volatility) of a caplet with maturity $T$ and strike rate $r_{K}$ is the volatility $\sigma_{f}^{F w d}(T)$ that characterizes that particular caplet.
# Flat Vol at ili ties and Forward Vol at ili ties
- Next table illustrates the relation between forward volatility and flat volatility
- The forward volatility is used to price individual caplets and thus obtain a value of the cap. - The flat volatility is used to quote the cap,  once its price is determined in the previous step. - The flat volatility is a sort of average (forward) volatility used for quoting purposes only
Table 3: The Relation between Forward and Flat Volatility
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/6627494f5d794cf121fc4096b0bb8a2c9e7e67ae72872a40e2c46cbfb3f00b2e.jpg)
# Extracting the Forward Volatility from Flat Volatility
- To set up arbitrage strategies,  we need Forward Vol at ili ties,  and not Flat vol at ili ties.
- How do we extract the Fwd volatility from the Flat volatility?
- It is simple and analogous to the extraction of the discount $Z (t; T)$ from bonds and swaps. - We start from the shortest maturitity,  and then bootstrap the Fwd volatility out of the Flat volatility,  by using an iterative method.
 - Consider a cap with maturity $T_{i}$ and let $\sigma_{f}(T_{i})$ be its “flat volatility"
 - Denote also $\sigma_{f}^{F w d}(T_{j})$ the forward vol at ili ties for $j=1,         2,         …,          n$
 - For all $T_{i}$ the following equations must hold
$$
c a p\left (T_{i}\right)\ =\ \sum_{j=1}^{i}c a p l e t\left (T_{j},         \overline {{r}} _{K,          i},         \sigma_{f}(T_{i})\right)
$$  
$$
=\begin{array}{l}{\displaystyle\sum_{j=1}^{i}c a p l e t\left (T_{j},         \overline {{r}} _{K,          i},         \sigma_{f}^{F w d}(T_{j})\right)}\\ {\displaystyle\left (\mathsf{l m p l i e d\b y\n o\a r b i t r a g e}\right)}\end{array}
$$  
- Where notice that the difference between the first and the second line is just the volatility
# How do we extract the $\sigma_{f}^{F w d}(T_{j})\,         {\bf\dot{s}}?$
- Step 1: Use the quoted (flat) vol at ili ties to obtain cap prices for all maturities (see Table 2)
- Step 2: For the shortest maturity $(T_{1}=0.5)$ ,  the cap has only one caplet,  and thus the forward and flat volatility must coincide. Thus:
$$
\sigma_{f}(0.5)=\sigma_{f}^{F w d}(0.5)=21.156\%.
$$  
- Step 3: For each subsequent time $i=2,         ..$ ,  we use the following three step procedure:
1. Use the previously extracted forward vol at ili ties $\sigma_{f}^{F w d}(T_{j})$ for $j=1,         ..,          i-1$ to compute the caplets up to $T_{j}$，$C a p l e t\left (T_{j},          r_{K,          i},         \sigma_{f}^{F w d}(T_{j})\right)$
1. Obtain the dollar value of the remaining caplet $T_{i}$ as the difference between the cap price for $T_{i}$ (obtained in Step 1) and the sum of caplets up to $T_{i-1}$
$$
T_{i}\ \mathsf{c a p l e t}=C a p (T_{i})-\sum_{j=1}^{i-1}C a p l e t\left (T_{j},          r_{K,          i},         \sigma_{f}^{F w d}(T_{j})\right)
$$  
1. Find the (forward) volatility $\sigma_{f}^{F w d}(T_{i})$ such that
# Example
- For instance,  the second cap ( $'T_{2}=0.75)$ has a dollar price of $C a p (T_{2})=\$ 0.1059$ .Wenowuse the three-step procedure in Step 3 above:
1. Compute the $T_{1}$ caplet using the forward volatility $\sigma_{f}^{F w d}(T_{1})\,         =\,          21.1564\%$ just computed. Using the Black formula,  we obtain
$$
C a p l e t (T_{1},          r_{K,          2},         \sigma_{f}^{F w d}(T_{1}))=\$ 0.0273
$$  
1. The dollar value of the $T_{2}$ caplet is then
$$
\begin{array}{r l}&{\mathsf{p l e t}\ =\ C a p (T_{2})-C a p l e t\left (T_{1},          r_{K,          2},         \sigma_{f}^{F w d}(T_{1})\right)}\\ &{\quad\quad=\ \$ 0.1059-\$ 0.0273=\$ 0.0786}\end{array}
$$  
1. Use the Black formula again to find the (forward) volatility $\sigma_{f}^{F w d}(T_{2})$ suchthat
$$
P l e t\left (T_{2},          r_{K,          2},         \sigma_{f}^{F w d}(T_{2})\right)=\$ 0.0786\,         \,         \,         \,         \Longrightarrow\,         \,         \,         \,         \sigma_{f}^{F w d}(T_{2})=22.
$$  

Example (cntd.)

·Similarly,  the $T_{3}$ forward volatility is obtained as follows:

1. Compute the $T_{1}$ and $T_{2}$ caplets using the forward vol at ili ties $\sigma_{f}^{F w d}(T_{1})\;=\; 21.1564\%$ and $\sigma_{f}^{F w d}(T_{2})=22.81\%$ just computed. Using the Black formula with the new strike rate $r_{K,          3}=$ $2.4420\%$ ,  we obtain
$$
\begin{array}{r l}&{C a p l e t (T_{1},          r_{K,          3},         \sigma_{f}^{F w d}(T_{1}))=\$ 0.0157}\\ &{C a p l e t (T_{2},          r_{K,          3},         \sigma_{f}^{F w d}(T_{2}))=\$ 0.0605}\end{array}
$$  
1. The dollar value of the $T_{3}$ caplet is then
$$
\begin{array}{r}{\begin{array}{l l}{T_{3}\ \mathsf{c a p l e t}\ =\ C a p (T_{3})-\displaystyle\sum_{j=1}^{2}C a p l e t\left (T_{j},          r_{K,          3},         \sigma_{f}^{F w d}(T_{j})\right)}\\ {\qquad\qquad\ =\ \$ 0.1859-(\$ 0.0157+\$ 0.0605)=\$ 0.1096}\end{array}}\end{array}
$$  
1. Use the Black formula again to find the (forward) volatility $\sigma_{f}^{F w d}(T_{3})$ such that
$$
'a p l e t\left (T_{3},          r_{K,          3},         \sigma_{f}^{F w d}(T_{3})\right)=\$ 0.1096\quad\Longrightarrow\quad\sigma_{f}^{F w d}(T_{3})=2
$$  
-Figure 1 plots the forward and flat vol at ili ties on November 1,  2004
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/ce2cf7919f6456d76076c6c66ebd4afa91532bcce10a1fba58872138e8dded9c.jpg)
Figure 1: Forward and Flat Vol at ili ties
- Flat vol at ili ties can be thought of a "cumulated averages" of forward vol at ili ties.
Cap (quoted) volatility changes over time.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/4a07d8427b8b649998d29be97c2c414b47ea697fbb0abf80f03f563842b66f02.jpg)
The average forward volatility curve is hump shapedi
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/b47d4116f2caedbfc91566a3242ef9e22b398804e4aa4fa127a7f110118d974b.jpg)
Figure 2: Average Forward Volatility: 1987 - 2008
- The forward volatility has various shapes through time:
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/602cedaf1fd933fe9937956ce5a7392cca26de1c0c5ea80497af35395679e0a7.jpg)
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/8d8db47de5d8a0ae2da7c3d0d64b172dd6ba261a9af09d64df0ea68f481cb5c3.jpg)
Figure 3: Forward and Flat Vol at ili ties
The forward volatility is strongly time varying:
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/2a7e91ade5011a14997498c5eafabc4b7760a4d08e64553222393aa631aefa37.jpg)
Figure 4: Forward and Flat Vol at ili ties
- Where $\mathsf{\Delta}^{\mathsf{u}}\mathsf{s l o p e}=\sigma_{f}^{F w d}(10)-\sigma_{f}^{F w d}(1)$ $\,         \,         {\it F W d}(1)\ "\ \mathsf{a n d}\ "\mathsf{c u r v a t u r e}=2\sigma_{f}^{F w d}(2)-\sigma_{f}^{F w d}(1)-\sigma_{f}^{F w d}(10)$
# Put-Call Parity
- A put-call parity relationship exists for caps and floors
Clearly,  a portfolio of a long caplet and short floorlet with equal strikes gives
$$
\operatorname*{max}\left (r_{n}\left (\tau,          T\right)-r_{K},          0\right)-\operatorname*{max}\left (r_{K}-r_{n}\left (\tau,          T\right),          0\right)=r_{n}\left (\tau,         
$$  
- But this is the payoff to a swap. Hence,  we have
$$
\mathsf{c a p}=\mathsf{f l o o r}+\mathsf{s w a p}
$$  
# Swaptions

·A buyer of a swaption has the right,  but not the obligation to enter into a swap with given characteristics (such as maturity,  swap rate,  payment frequency,  etc.) at a given maturity $T_{O}$

- In a payer swaption the swaption buyer has the right to enter into a swap as a fixed-rate payer (and receive floating.) In a receiver swaption the swaption buyer has the right to enter into the swap as fixed-rate receiver (and pay floating).
- For instance,  in Table 1,  an investor can purchase an at-the-money six-month option to enter into a 10-year swap at "implied volatility" of $21.883\%$
Table 1: Quotes of Caps and Swaptions on November 1,  2004
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/cbe581cae55eefa3f7aff0baa1f3d7281e226c14a7ffa542bc6b69da70511fe9.jpg)
Source: Bloomberg.
# Swaptions
- A swap,  recall,  is a contract between two parties to exchange at times $T_{1},         ..,          T_{n}$ the net cash flows
$$
C F\left (T_{i+1}\right)=\Delta\times N\times\left (r_{K}-r_{n}\left (T_{i},          T_{i+1}\right)\right)
$$  

 - On each of the reset dates dates,  the value of the swap is

$$
V\left (T_{i},          r_{K}\right)=P\left (T_{i},          T; r_{K}\right)-100
$$  

 - where $P\left (T_{i},          T; r_{K}\right)$ is the price of a coupon bond with $r_{K}$ as coupon rate and maturity $T$

 - Consider an option that gives its holder the right (not the obligation) to enter as the fixed rate receiver in the swap at time $T_{O}=T_{i^{*}}$ forsome $i^{*}<n$ ,  at the exercise rate $r_{K}$

 - Let $c\,          (T_{i^{*}},          T)$ be the market swap rate at time $T_{i^{*}}$ for a swap maturing at $T$

-If $c\left (T_{i^{\ast}},          T\right)<r_{K}$ ,  optimal to exercise the option (and receive $r_{K}$ instead of lower $c\left(T_{i^{*}},         T\right))$ $\mathsf{I f}\,         c\left(T_{i^{*}},         T\right)>r_{K}$ ,  optimal not to exercise the option (better receive the market rate $c\left (T_{i^{*}},          T\right))$

# Swaption Payoff
- We now show that the payoff of a receiver swaption is positive if and only if the market swap rate is below the strike swap rate:
$$
V\left (T_{i^{\ast}},          r_{K}\right)>0\Longleftrightarrow c\left (T_{i^{\ast}},          T\right)<r_{K}
$$  

The payoff from the Swaption can be written as

$$
\begin{array}{r l}{\mathsf{P a y o f f}}&{=\ V\left (T_{i^{*}},          r_{K}\right)-}\\ &{=\ V\left (T_{i^{*}},          r_{K}\right)-V\left (T_{i^{*}},          c\left (T_{i^{*}},          T\right)\right)}\\ &{=\ \left[P\left (T_{i^{*}},          T; r_{K}\right)-100\right]-\left[P\left (T_{i^{*}},          T; c\left (T_{i^{*}},          T\right)\right)-\right.}\\ &{=\ P\left (T_{i^{*}},          T; r_{K}\right)-P\left (T_{i^{*}},          T; c\left (T_{i^{*}},          T\right)\right)}\\ &{=\ \underset{j=i^{*}+1}{\overset{n}{\sum}}\ Z\left (T_{i^{*}},          T_{j}\right) r_{K}\Delta N+Z\left (T_{i^{*}},          T_{n}\right)\times 1}\\ &{\qquad-\underset{j=i^{*}+1}{\overset{n}{\sum}}Z\left (T_{i^{*}},          T_{j}\right) c\left (T_{i^{*}},          T\right)\Delta N-Z\left (T_{i^{*}},          T_{n}\right.}\\ &{=\ \underset{j=i^{*}+1}{\overset{n}{\sum}}\ Z\left (T_{i^{*}},          T_{j}\right)\Delta N\left (r_{K}-c\left (T_{i^{*}},          T\right)\right)}\end{array}
$$  

 - The value of a swap at time $T_{O}$ is positive if and only if $\left (r_{K}-c\left (T_{i^{*}},          T\right)\right)$

# Swaption Payoff
- Clearly,  the option buyer exercises the option if and only if the payoff is positive,  so the receiver swap tion payoff at $T_{i^{*}}$ is
Payoff of Receive $\textsf{r S w a p t i o n}\;=\;\sum_{j=i^{*}+1}^{n}Z\left (T_{i^{*}},          T_{j}\right)\Delta N\operatorname*{max}\left (r_{K}-c\left (T_{i^{*}},          T\right),         \right.$ 0
The payoff to the swap is equivalent to the cash flow
$$
\Delta N\operatorname*{max}\left (r_{K}-c\left (T_{i^{*}},          T\right),          0\right)
$$  

Determined at $T_{i}^{*}$ ,  paid out at times $T_{i^{*}+1},          T_{i^{*}+2},         …,          T_{n}$ ,  and thus discounted to $T_{i^{*}}$ through the terms $\begin{array}{r}{\sum_{j=i^{*}+1}^{n}Z\left (T_{i^{*}},          T_{j}\right)}\end{array}$

-- The payoff at each time $T_{i^{*}+j}$ is always the same determined at $T_{i^{*}}$

- Similar,  the payer swaption payoff at $T_{i^{*}}$ is
$$
\mathsf{S w a p t i o n~}=\sum_{j=i^{*}+1}^{n}Z\left (T_{i^{*}},          T_{j}\right)\Delta N\operatorname*{max}\left (c\left (T_{i^{*}},          T\right)-r_{K},          0\right)
$$  
# Payoff of Receiver Swaption

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/c20616253c864c218df6d07c92d9c8a063d683e062cc36e01326005d12b01db0.jpg)

# Swaption Pricing

 - The price of the receiver swaption is obtained by pricing each of those payments $\Delta N\operatorname*{max}\left (r_{K}-c\left (T_{i^{*}},          T\right),          0\right)$ at times $T_{i^{*}+1},          T_{i^{*}+2},         …,          T_{i^{*}+n}$ ,  individually

 - Like for caps and floors,  the Black's formula assumes that under the proper risk-adjusted probabilities,  the swap rate $c\,          (T_{i^{*}},          T)$ is log-normally distributed

$$
\log c\left (T_{i^{*}},          T\right)\sim\mathcal{N}(\mu,         \sigma_{T_{i^{*}}}^{2}T_{i^{*}})
$$  

 - where $\sigma_{T_{i^{*}}}$ is the swap rate volatility,  which is what is quoted by market participants. 2

 - Thus,  the (risk adjusted) expected value of a payer and receiver cash flows at $T_{i^{*}+j}$ are,  respectively,

$$
\begin{array}{r l}{\left.\left (c\left (T_{i^{*}},          T\right)-r_{K},          0\right)\right]\right]\;=}& {{}Z\left(0,         T_{i^{*}+j}\right)\;\left[f_{n}^{s}(0,         T_{i^{*}} ,          T)\mathcal{N}\left (d_{1}\right)\right.}\\ {\left.\left (r_{K}-c\left (T_{i^{*}},          T\right),          0\right)\right]\right]\;=}& {{}Z\left(0,         T_{i^{*}+j}\right)\;\left[-f_{n}^{s}(0,         T_{i^{*}} ,          T)\mathcal{N}\left (-\frac{r_{i^{*}}^{2}}{2\pi\epsilon}\right)\right],         }\end{array}
$$  

 - where $f_{n}^{s}(0,          T_{i^{*}},          T)$ is the forward swap rate. And

$$
L_{1}=\frac{\ln{\left (f_{n}^{s}(0,          T_{i^{*}},          T)/r_{K}\right)}+\sigma_{T_{i^{*}}}^{2}T_{i^{*}}/2}{\sigma_{T_{i^{*}}}\sqrt{T_{i^{*}}}};\ \ \ \ d_{2}=d_{1}-\sigma_{T_{i^{*}}}\sqrt{T_{i^{*}}}
$$  
# Quoted Swaption Implied Volatility Surface

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/42a66ee6c0dbbee11e399f48f761157153ebf3514621ea40c80908841d144c31.jpg)

# Swaption Pricing

Hence,  the value of a payer swaption

$$
\begin{array}{r l}{\mathsf{t i o n}\ =}&{\underset{j=i^{*}+1}{\overset{n}{\sum}}\Delta\times N\times Z\left (0,          T_{j}\right)\left[f_{n}^{s}(0,          T_{i^{*}},          T)\mathcal{N}\left (d_{1}\right)-r_{H}\mathcal{N}\left (d_{2}\right)\right]}\\ &{=\ A N\left[f_{n}^{s}(0,          T_{i^{*}},          T)\mathcal{N}\left (d_{1}\right)-r_{K}\mathcal{N}\left (d_{2}\right)\right]}\end{array}
$$  

Where

$$
A=\sum_{j=i^{*}+1}^{n}\Delta\times Z\left (0,          T_{j}\right)
$$  

Similarly,  the value of a receiver swaption is

$$
\mathsf{R e c e i v e r~S w a p t i o n~=~A N}\left[-f_{n}^{s}(0,          T_{i^{*}},          T)\mathcal{N}\left (-d_{1}\right)+r_{K}\mathcal{N}\left (d_{1},          d_{2}\right)\right]
$$  
# How do we compute the Forward Swap Rate?

This is implicit in the forward discount curve

$$
F\left (0,          T_{i^{*}},          T\right)=\frac{Z\left (0,          T\right)}{Z\left (0,          T_{i^{*}}\right)}
$$  

 - Using that just as a discount function and following the same steps as for regular swap rate,  we can compute the Forward Swap Rate $f_{n}^{s}(0,          T_{i^{*}},          T)$ ,  for a swap starting at time $T_{i^{*}}$ andlasting until time $T_{n}$ ,  as

$$
F_{n}^{s}(0,          T_{i^{*}},          T)=\frac{1}{\Delta}\frac{1-F\left (0,          T_{i^{*}},          T_{n}\right)}{\Sigma_{j=i^{*}+1}^{n}F\left (0,          T_{i^{*}},          T_{i}\right)}
$$  
# Example
- Today is November 1,  2004. Consider a 1-year swaption to enter into a 5-year swap at strike rate $r_{K}=3.751\%.$
 - Table 1 shows that such a swaption is trading at implied volatility $\sigma_{f}^{s}=27.404\%$
 - Table 4 provides the [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] discount curve up to $T=6$
 - to derive the Forward Discount curve we also need $Z (0,         1)\times 100=97.48.$
 - We then obtain
$$
A=\Delta\times\sum_{i=1}^{n}Z (0,          T_{i})=4.4046
$$  

 - The forward swap rate can be computed from the forward discounts using the previous formula $f_{4}^{s}(0,          T_{O},          T_{S})=4.261\%$

$$
\frac{3.751\%)+0.27404^{2}\times 1/2}{0.27404\times\sqrt{1}}=0.6023\ ,         \ d_{2}=0.6023-0.274
$$

  $d_{2}=0.6023-0.27404\times{\sqrt{1}}=0.3282$

The Black's formula then gives for a receiver swaption with $N=100$

$$
\begin{array}{r l}{\mathsf{t i o n}\!\!}&{=\underset{j=i^{*}+1}{\overset{n}{\sum}}\Delta\times N\times Z\left (0,          T_{j}\right)\left[-f_{n}^{s}(0,          T_{i^{*}},          T)\mathcal{N}\left (-d_{1}\right)-\right.}\\ {\!\!}&{=\left.\$ 1.0026\right.}\end{array}
$$  

Table 4: LlBOR Discount and Forward Discount

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/00946d352773cb766d7a8cc6a2786a2edfdb83b6b24a729679f0a4ca6765ef33.jpg)

Original Swap Data Source: Bloomberg.

# Fixed Income Pircing Black and Scholes Formula

The University of Chicago

Booth School of Business

1. Black and Scholes Formula
1.1 Dynamic Replication
1.2 Black and Scholes and the Binomial Trees
# Option Premium
- Black,  Scholes and Merton show that (under certain conditions) there exists a trading strategy involving only stocks and bonds that replicate the payoff at $T$ of a call or a put option.
·Assume a stock $S_{t}$ has constant expected (log) return $\mu$ and constant volatility $\sigma$
- That is,  if the log return during a small time interval $h$ be $R_{t}=l o g (S_{t+h}/S_{t})$ ,  assume
$$
E[R_{t}]=\mu\times h;~~E[R_{t}^{2}]=\sigma^{2}\times h
$$  

—( $\mu$ and $\sigma$ are the annualized expected log return and volatility)

 - Consider now a put option with strike price $K$ and maturity $T$  - The following trading strategy replicates the final payoff $\operatorname*{max}(K-S_{T},          0)$
# Option Premium by Dynamic Replication
1. At time O:
A Short $\Delta_{0}=-N (-d_{1,         0})$ of stocks
Here $N (x)$ is the standard normal cumulative density function,  and $d_{1,          t}$ iS
$$
D_{1,          t}={\frac{\ln\left (S_{t}/K\right)+\left (r+\sigma^{2}/2\right)(T-t)}{\sigma{\sqrt{T-t}}}}
$$  

$r$ is the continuously compounded risk free rate; $\sigma$ is the volatility of stock returns

(b) Buy an amount $B_{0}=K\times e^{-r\times T}\times N (-d_{2,         0})$ of Treasury Zero Coupon bonds

Here $d_{2,         0}=d_{1,          t}-\sigma\times\sqrt{T}$ The portfolio so constructed has value at time 0

$$
P_{0}=B_{0}+\Delta_{0}S_{0}
$$  

(it can be shown $P_{0}>0$

1. From now on,  rebalance the portfolio,  to make sure that at every $t$ ,  the portfolio has a position in stocks given by $\Delta_{t}=-N (-d_{1,          t})$
·E.g. if $S_{t}\downarrow\implies\Delta_{t}\downarrow\implies$ short more stocks and put proceeds into bonds $\Longrightarrow B_{t}$ ·Or if $S_{t}\uparrow\implies\Delta_{t}\uparrow\implies$ buy back stocks by liquidating some bonds $\Longrightarrow B_{t}\downarrow$
# Option Premium by Dynamic Replication

 - For instance,  let $S=K=100$，$T=1$，$r=5\%$，$\sigma=20\%$ . Then

D 1 = . $-d_{1})=0.3632; N (-d_{2})=0.4404\Longrightarrow\Delta_{0}=-N (-d_{1})=-d_{1}=0.3632; N (d_{1})=-d_{1}=0.3632; N (d_{2})=0.3632; N (d_{1})=-d_{1}=0.3632; N (d_{2})=0.3632; N (d_{1})=-d_{1}=0.3632; N (d_{2})=0.3632; N (d_{1})=-d_{1}=0.3632; N (d_{2})=0.3632; N (d_{1})=-d_{1}=0.3632; N (d_{2})=0.3632; N (d_{1})=-d_{1}=0.3632; N (d_{2})=0.3632; N (d_{1})=-d_{1}=0.3632; N (d_{2})=0.3632; N (d_{1})=-d_{1}=0.3632; N (d_{2})=0.3632; N (d_{1})=-d_{1}=0.3632; N (d_{2})=0.3632; N (d_{1})=-d_{1}=0.3632; N (d_{2})=0.$ -0.3632Initial short position in stocks: $\Delta\times 100=-N (d_{1})\times 100=-0.3632\times 100=-\$ 36.3$ 2 -- Initial bond position: $B_{0}=K e^{-r T}N (-d_{2})=\$ 41.89$

- Initial value of the portfolio: $P_{0}=B_{0}+\Delta_{0}S_{0}=\$ 41.89-\$ 36.32=\$ 5.57$
- One day later ( $(h=1/252=1~\mathrm{day})$ ) the stock is $S_{h}=99\Longrightarrow\Delta_{h}=-N (-d_{1,          h})=-. 3821$ - Need to short more,  and thus sell $|\Delta_{h}-\Delta_{0}|=|-. 3821-(-0.3632)|=0.0189$ shares. $-\;\mathrm{Obstain}\;\mathrm{cosh}=0.0189\times 99=\$ 1.879$ ,  and put it in bonds:
NewBond $=\; B_{h}=B_{0}\times e^{r\times h}+\$ 1.879=\$ 41.89-\$ 1.879=\$ 43.777$ New Portfolio Po
# Option Premium by Dynamic Replication
- Fact: The portfolio $P_{t}=\Delta_{t}S_{t}+B_{t}$ obtained from the above trading strategy replicates the put option payoff.
- That is,  at maturity
$$
P_{T}=\Delta_{T}S_{T}+B_{T}=\operatorname*{max}(K-S_{T},          0)
$$  
- Proof by simulation: Next two figures shows that the strategy works,  even when portfolio rebalancing is at daily interval ( $h=1/252)$
- I simulate stock price paths. And then performed the above trading strategy
# Option Premium by Dynamic Replication

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/8338eaea403240924d29f598dc73f55ad66bd69929d8d97b89c8e58105feabd8.jpg)

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/fe3708b428c3c7ec89fe675a60748522241105d0a58f593663f322204c56c8dd.jpg)

# Option Premium by Dynamic Replication

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/44179ab394fca12b36326dbdaf84c088ad61bb9ec6a5eba31d8bf9215727d333.jpg)

# Black and Scholes Formula

·Since portfolio $P_{t}$ replicates the payoff of the put option,  the value of the portfolio at any time must equal the value of the put option.

- Why?
- Arbitrage: “Buy Cheap / Sell Dear". - For instance,  if $P_{t}$ < Put Option Premium => 1. Sell option and set up the replicating portfolio (which costs $P_{t}$ 2. Today make ( Put Option Premium $-P_{t})>0$ 3. At maturity $T$ the replicating portfolio provides the payoff,  exactly
In particular,  at time O,  the value of the option must be
$$
\begin{array}{r l}{\mathrm{Put~Primal~at~0,         ~}p_{0}\;=\; P_{0}=B_{0}+\Delta_{0}\times S_{0}}\\ &{}\\ {\;=\; K\times e^{-r T}\times N (-d_{2,         0})-S_{0}\times N}\end{array}
$$  

This is the celebrated “Black and Scholes’ formula for option pricing

Similarly,  a call option formula is given by

$c_{0}=S_{0}\times N (d_{1,         0})-K\times e^{-r T}\times N (d_{2,         0})$

# Delta Hedging and Dynamic Replication

Why does the dynamic replication strategy work?

- Suppose you sold a put option and decide to hedge using the replicating portfolio $P$ - Let II be the portfolio short the put $(-p)$ and long the replicating portfolio
$$
\begin{array}{r l}{\Pi\;=}& {{}{-p+P}} \\ {\;=}& {{}{-p+\Delta S+B}} \end{array}
$$  
- What is the sensitivity of $\prod$ to small variations in stocks?
$$
\frac{d\;\Pi}{d\; S}=-\frac{d\; p}{d\; S}+\Delta\times 1+0
$$  
- The portfolio $\mathrm{II}$ is delta hedged $\left (d\;\Pi/d\; S=0\right)$）if
$$
\Delta={\frac{d\; p}{d\; S}}
$$  
- It can be shown that indeed $\Delta=-N (-d_{1})$ is exactly $d\; p/d\; S$
- This implies that for every small variation in stock $S$ ,  the portfolio and the option move exactly by the same amount.
=> the dynamic replication works.
# Delta Hedging and Dynamic Replication

The next figure shows the dynamic replication at work in a graph

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/dddaba764cbd269003353f1f81a24a71fb676b328c31c83abe2638fe94514bf4.jpg)

The Put Price Profile and the Replicating Portfolic

# Black and Scholes Formula

Example: Consider an at-the-money option.

- The stock price is $S\,         =\,          100$ ,  the strike price is $K\,         =\,          100$ ,  the (continuously compounded) interest rate is $r=5\%$ ,  maturity is $T=1$ ,  and the return volatility $\sigma=30\%$
We then have
$$
\frac{\binom{S}{K}+(r-\delta+\sigma^{2}/2) T}{\sigma\sqrt{T}}=\frac{\log\left (\frac{100}{100}\right)+(. 05+(0.30)^{2}/2)\times 1}{0.30\sqrt{1}}
$$  
$$
D_{2}=d_{1}-\sigma{\sqrt{T}}=0.3167-. 3{\sqrt{1}}=0.0167
$$  

 - Therefore $N (d_{1})=0.62425$ and $N (d_{2})=0.50665$

The value of the call option is

$$
\mathrm{V}(d_{1})-K e^{-r T}N (d_{2})=100\times 0.62425-100\times e^{. 05\times 1}\times 0.
$$  

 - The value of a put option can be computed from these data by recalling that

$$
N (-d_{1})=1-N (d_{1})=0.37575;\quad N (-d_{2})=1-N (d_{2})=0.37575;
$$  

 - so that

$$
N (-d_{1})+K e^{-r T}N (-d_{2})=-100\times 0.37575+100\times e^{. 05\times}
$$  
# The Binomial Tree and Black and Scholes Formula
- 'To interpret the Black and Scholes formula it is convenient to go back to binomial trees
- Black and Scholes model assumes continuous trading - That is,  traders can trade at any instant $t$
- Moreover,  stock prices can take on any value,  and not only the values on a tree
- Both conditions are approximately met as we let the time interval binomial tree go to zero.
- To see the similarity of Black and Scholes formula with the one stemming from a binomial tree. Consider the following example.
# The Binomial Tree and Black and Scholes Formula

$i=0$ $i=1$

$$
\begin{array}{r l}{\lefteqn{S_{1,          u}=S_{0}\times u}}\\ {\qquad}&{{}c_{1,          u}=\operatorname*{max}(S_{1}-K,          0)=S_{1}-K}\end{array}
$$  

$S_{0}$ $c_{0}=e^{-r\times T}E^{*}\left[\operatorname*{max}(S_{1}-K,          0)\right]$

$S_{1,          d}=S_{0}\times d$ $c_{1,          d}=\operatorname*{max}(S_{1}-K,          0)=0$

Consider $i=0$ and $i=1$ With $S_{1,          u}=S_{0}\times u$ and $S_{1,          d}=S_{0}\times d$

- Assume the price of the option has $S_{1,          u}\,         >\,          K\,         >\,          S_{1,          d}$ ,  so that the payoffs from the tree above result.
·Let $q^{*}$ be the risk neutral probability of going up in the tree
# The Binomial Tree and Black and Scholes Formula

The price of the option at time O according to risk neutral pricing is the

$$
\begin{array}{r l}{\mathfrak{z}_{0}\;=\; e^{-r\times T}E^{*}\left[\operatorname*{max}(S_{1}-K,          0)\right]}\\ {\;=\; e^{-r\times T}\times[q^{*}\times\operatorname*{max}(S_{1,          u}-K,          0)+(1-q^{*})\times\operatorname*{max}(S_{2,          u}-K,          0)]}\\ {\;=\; e^{-r\times T}\times q^{*}\times (S_{1,          u}-K)}\\ {\;=\; S_{0}\times e^{-r\times T}\times q^{*}\times u-e^{-r\times T}\times K\times q^{*}}\\ {\;=\; S_{0}\times N_{1}-e^{-r\times T}\times K\times N_{2}}\end{array}
$$  
- where,  defining by $u_{c c}$ the annualized c.c. return from an up movement $S_{1,          u}/S_{0}=e^{u_{c c}\times T}=u$
$$
N_{1}=e^{-r\times T}\times q^{*}\times u=e^{(u_{c c}-r)\times T}\times q^{*}\quad\mathrm{and}\quad N_{2}=q^{*}
$$  

 - 'The similarity with Black and Scholes formula is not coincident i al

$$
{\mathrm{Call}}=S\times N (d_{1})-K\times e^{-r T}\times N (d_{2})
$$  

 - Interpretation:

$-\ N_{2}=N (d_{2})$ risk neutral probability to be in the money at maturity; $-\ N_{1}=N (d_{1})$ risk neutral expected excess return conditional on exercise at $T$

# The Binomial Tree and Black and Scholes Formula

For a large number of binomial steps,  $n$ for a fixed maturity:

$$
\begin{array}{l} {{c_{0}~=~e^{-r T}E^{*}\left[\operatorname*{max}(S_{T}-K,         0)\right]}} \\ {{\ }} \\ {{\quad=~e^{-r\times T}\displaystyle\sum_{j=0}^{n}\left(\frac{n!}{j!(n-j)!}\right)\operatorname*{max}(S_{T,         j}-K,         0)}} \end{array}
$$  

Where $S_{T,          j}=S_{0}\times u^{(n-j)}\times d^{j}$

 - Let $a$ be the smallest integer for which $S_{T,          j}>K$ for $j\geq a$ ,  and $S_{T,          j}<K$ for $j<a$

Putting all together:

$$
\begin{array}{l} {{\displaystyle c_{0}~=~e^{-r\times T}\sum_{j=a}^{n}\left(\frac{n!}{j!(n-j)!}\right)(S_{T,         j}-K)}} \\ {{\displaystyle\qquad=~S_{0}\times N_{1}-K\times e^{-r\times T}\times N_{2}} }\\ {{\displaystyle\sum_{=a}^{n}\left(\frac{n!}{j!(n-j)!}\right)\times u^{(n-j)}\times d^{j}\right)\quad\mathrm{and}\quad N_{2}=\sum_{j=a}^{n}\left(\frac{n!}{j!(n-j)!}\right)\times d^{j}} }\end{array}
$$  

 - It can be shown that $N_{1}\rightarrow N (d_{1})$ and $N_{2}\to N (d_{2})$ as $n\to\infty$

The interpretation,  though,  is the same as in the simple 2-period model Teaching Notes 5

# Risk Neutral Pricing: Binomial Trees and Monte Carlo Simulations

The University of Chicago Booth School ofBusiness

# Binomial Trees

Let's start from an example.

- Let's assume the six-month,  continuously compounded risk-free rate is estimated to move according to the following tree $({\mathsf{s t e p}}=1/2$ year),  wherethere is probability $p=1/2$ to move up or down.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/7fa6a7740900644756bbfb942e9ec039972a7875e7a81e904602678868ca9157.jpg)
# Binomial Trees

The expected rate in six and twelve months are

$$
\begin{array}{l}{E\left[r_{1}\right]\;=\;\displaystyle\frac{1}{2}r_{1,          u}+\frac{1}{2}r_{1,          d}=0.02305}\\ {E\left[r_{2}\right]\;=\;\displaystyle\frac{1}{4}r_{2,          u u}+\frac{1}{2}r_{2,          u d}+\frac{1}{4}r_{2,          d d}=. 0279}\end{array}
$$  
-Note: $r_{t}$ here is the continuously compounded,  one period interest rate.
 - For trees,  it is convenient to denote bonds in terms of steps and nodes
 - Let
$$
Z_{i,          j}\left (k\right)
$$  
- be the value of a zero coupon bond at index time $i$ (e.g. $i=1$ ),  at node $j$ (e.g. $j=u,         d…)$ and with maturity at index $k$ (e.g. $k=2$
For instance
# Relative Pricing on Trees

Example: Bond and Option

 - Suppose that by using any of the methodologies in TN 1 we obtained the following discounts:

$$
Z_{0}\left (1\right)=0.9916,         \; Z_{0}\left (2\right)=0.9781,         \; Z_{0}\left (3\right)=0.9615
$$  

 - Let $C_{0}$ be a call option on a six-month zero-coupon bond with maturity $i=1$ and strike price $K$

- A call option on a zero coupon bond gives its owner the right,  but not the obligation,  to buy a six-month zero couponat $i$ forprice $K$
 - The payoff to the buyer of the option is
$$
C_{1}=\operatorname*{max}\left (Z_{1}\left (2\right)-K,          0\right)
$$  

·At time $i=1$，weknow $Z_{1}\left (2\right)$ under the two scenarios that the yield went up or down

 - Thus we can compute $C_{1}$ . Assuming $K=0.99$ ,  consider the tree

# I=0
$$
I=1
$$  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/0fec6a685c1fe21a6e587dc137b694bed8933b031028d2e2d535626708106132.jpg)

- We now consider a hedging strategy that allows us to evaluate options on the tree.
# The Option Hedging Strategy
- Consider a portfolio at time $i=0$ that is long the option and short $\Delta$ units of the 2-period zero coupon bonds - Its value at time $j=0$ is
$$
\Pi_{0}=C_{0}-\Delta\times Z_{0}\left (2\right.
$$  
- What is its value at time $j=1?$
$$
\begin{array}{r l}{\mathsf{I n\ u p\ n o d e}\ :\ }& {{}\Pi_{1,         u}=C_{1,         u}-\Delta Z_{1,         u}} \\ {\mathsf{I n\ d o w n\ n o d e}\ :\ }&{{}\Pi_{1,          d}=C_{1,          d}-\Delta Z_{1,          d}\,         .}\end{array}
$$  

Besides △,  all quantities on the right-hand side are known.

Key step

Choose $\Delta$ to make $\Pi_{1,          u}{=}\Pi_{1,          d}$

# The Option Hedging Strategy

Imposing equality

$$
C_{1,          u}-\Delta Z_{1,          u}\left (2\right)=C_{1,          d}-\Delta Z_{1,          d}
$$  

Yields

$$
\Delta=\frac{C_{1,          u}-C_{1,          d}}{Z_{1,          u}\left (2\right)-Z_{1,          d}\left (2\right)}
$$  

$-\Delta$ is now known. For instance,  if $K=. 99$ we have $\Delta=. 4076$

- In this case,  we find $\Pi_{1,          u}=C_{1,          u}-\Delta Z_{1,          u}\left (2\right)=-0.3998\;\left (\mathsf{a l s o\e q u a l\ t o}=\Pi_{1,          d}\right)$
What is the value of the portfolio at time $i=0?$
- The portfolio is riskless between time $i=0$ and $i=1$ - Therefore,  its value must be the discounted value of $\Pi_{1,          u}$ using the risk free rate to discount
$$
\left|~\mathsf{N o\A r b i t r a g e}\Longrightarrow\Pi_{0}=Z_{0}\left (1\right)\Pi_{1,          u}\right.
$$  
-(Recall $\Pi_{1,          u}{=}\Pi_{1,          d}$ so it does not matter what you put on the RHS)
# The Option Value
# Therefore
$$
C_{0}-\Delta Z_{0}\left (2\right)=Z_{0}\left (1\right)\Pi_{1,          u}
$$  

Implying

$$
C_{0}\,         \,         =\,         \,         \Delta Z_{0}\left (2\right)+Z_{0}\left (1\right)\Pi_{1,          u}=0.00223
$$  
-(recall $Z_{0}\left (1\right)=0.9916$ $Z_{0}\left (2\right)=0.9781)$
# The Replicating Portfolio
- Note that the option is a portfolio of zerosi
$-\; N_{1}=\Delta=. 4076$ of one-year zero $Z_{0}(2)$ ; and $-\ N_{2}=\Pi_{1,          u}=-0.3998$ of six-month zero $Z_{0}(1)$
 - That is,  the portfolio of bonds
$$
P_{0}=N_{1}\times Z_{0}(2)+N_{2}\times Z_{0}(1)
$$  

Exactly replicates the payoff of the option

# The Replicating Portfolio

$i=0$ =1

$Z_{1,          u}\left (1\right)=1$ $Z_{1,          u}\left (2\right)=0.9808$ $P_{1,          u}=N_{1}Z_{1,          u}(2)+N_{2}=0$

$Z_{0}\left (1\right)=0.9916$ $Z_{0}\left (2\right)=0.9781$ $P_{0}=N_{1}Z_{0}(2)+N_{2}Z_{0}(1)=0.00223$

$Z_{1,          d}\left (1\right)=1$ $Z_{1,          d}\left (2\right)=0.9963$ $P_{1,          d}=N_{1}Z_{1,          d}(2)+N_{2}=. 006307$

$P$ is called "replicating portfolio,  " a key concept.

# A No Arbitrage Relation
- What was special about the fact that $C_{0}$ was an option on zero-coupon bond?
- Nothing in particular!
- We could do the same derivation with any other security
- Let's do the same steps,  but now using ANY other security,  that depends on interest rates.
·Generically,  let $Z_{0}\left (j\right)$ be any zero coupon bond,  and let's consider the following generic tree
$$
I=0\qquad\qquad\qquad i=1
$$  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/18a297c8ccea38d567183d2ec14506eecb76d27898dcb4a76e16f21f65044d0e.jpg)

# A No Arbitrage Relation

Let's follow the same steps:

Step 1: Portfolio

$$
\Pi_{0}=V_{0}-\Delta Z_{0}\left (j\right)
$$  
- Step 2: Choose $\Delta$ to make portfolio at time $j=1$ independent of interest rates
$$
\begin{array}{r l r}{\Pi_{1,          u}}&{=}&{\Pi_{1,          d}\;}\\ &{\Longleftrightarrow}&\\ {V_{1,          u}-\Delta Z_{1,          u}\left (j\right)}&{=}&{V_{1,          d}-\Delta Z_{1,          d}\left (j\right)}\\ &{\Longleftrightarrow}&\\ {\Delta}&{=}&{\frac{V_{1,          u}-V_{1,          d}}{Z_{1,          u}\left (j\right)-Z_{1,          d}\left (j\right)}}\end{array}
$$  
- Step 3: The portfolio is riskless,  no arbitrage requires
# A No Arbitrage Relation
- In fact,  we can take the expected value using any probability $\tilde{p}$
$$
\Pi_{1,          u}=\Pi_{1,          d}=E^{\tilde{p}}\left[\Pi_{1}\right]
$$  

Where

$$
\begin{array}{r l}{E^{\tilde{p}}\left[\Pi_{1}\right]\ =\ \tilde{p}\Pi_{1,          u}+\left (1-\tilde{p}\right)\Pi_{1,          d}}\\ &{}\\ {=\ \tilde{p}\left[V_{1,          u}-\Delta Z_{1,          u}\left (j\right)\right]+\left (1-\tilde{p}\right)\left[V_{1,          d}-\Delta Z_{1,          d}\left (j\right)\right]}\\ &{}\\ {=\ E^{\tilde{p}}\left[V_{1}\right]-\Delta E^{\tilde{p}}\left[Z_{1}\left (j\right)\right]}\end{array}
$$  

—Substituting

$$
\begin{array}{r l r}{\Pi_{0}}& {{}=}&{Z_{0}\left(1\right)E^{\tilde{p}} \left[\Pi_{1}\right]}\\ {\iff}& {{}} &{}\\ {V_{0}-\Delta Z_{0}\left (j\right)}& {{}=}&{Z_{0}\left(1\right)\left\{E^{\tilde{p}} \left[V_{1}\right]-\Delta E^{\tilde{p}}\left[Z_{1}\left (j\right)\right]\right\}}\end{array}
$$  
# A No Arbitrage Relation
- Step 4: Rearrange
$$
V_{0}=Z_{0}\left (1\right) E^{\tilde{p}}\left (V_{1}\right)-\Delta\times\left\{Z_{0}\left (1\right) E^{\tilde{p}}\left[Z_{1}\left (j\right)\right]-Z_{0}\left (j\right)\right\}
$$  
-Substitute $\Delta$ from (1) and rearrange again
$$
\frac{Z_{0}\left (1\right) E^{\tilde{p}}\left[Z_{1}\left (j\right)\right]-Z_{0}\left (j\right)}{Z_{1,          u}\left (j\right)-Z_{1,          d}\left (j\right)}=\frac{Z_{0}\left (1\right) E^{\tilde{p}}\left (V_{1}\right)-V_{0}}{V_{1,          u}-V_{1,          d}}
$$  

This last expression is key to the whole fixed income asset pricing

To interpret it,  let's rewrite the equality as

$$
\frac{E^{\tilde{p}}\left[\frac{V_{1}}{V_{0}}\right]-\frac{1}{Z_{0}(1)}}{\left[\frac{V_{1,          u}}{V_{0}}-\frac{V_{1,          d}}{V_{0}}\right]}=\frac{E^{\tilde{p}}\left[\frac{Z_{1}(j)}{Z_{0}(j)}\right]-\frac{1}{Z_{0}(1)}}{\left[\frac{Z_{1,          u}(j)}{Z_{0}(j)}-\frac{Z_{1,          d}(j)}{Z_{0}(j)}\right]}
$$  
# A No Arbitrage Relation

Notice

$$
\begin{array}{r l}{E^{\tilde{p}}\left[\cfrac{V_{1}}{V_{0}}\right]~=~}&{\mathsf{E x p e c t e d~R e t u r n~}\left (\mathsf{u n d e r~\tilde{p}}\right)\mathsf{f r o m~p u r c h a s}}\\ {E^{\tilde{p}}\left[\cfrac{V_{1}}{V_{0}}\right]-\cfrac{1}{Z_{0}\left (1\right)}~=~}&{\mathsf{E x p e c t e d~R e t u r n~i n~E x c e s s~o f~T r e a s u r y}}\\ {\left[\cfrac{V_{1,          u}}{V_{0}}-\cfrac{V_{1,          d}}{V_{0}}\right]~=~}&{\mathsf{R i s k~f r o m~i n v e s t i n~V_{0}}}\end{array}
$$  

 - The above hold for any $\tilde{p}$ . To have economic meaning,  we must though use the true $\tilde{p}=p=0.5$

 - Denoting $E[.]$ (without superscript) the expectations under the true probability,  we have

$$
\frac{E\left[\frac{V_{1}}{V_{0}}\right]-\frac{1}{Z_{0}(1)}}{\left[\frac{V_{1,          u}}{V_{0}}-\frac{V_{1,          d}}{V_{0}}\right]}\ =\ \frac{\mathsf{E x p e c t e d~E x c e s~R e t u r n}}{\mathsf{R i s k~f r o m~i n v e s t m e n t}}=\left\{\begin{array}{c}{\mathsf{S h a r p e~R a t i o}}\\ {o r}\\ {\mathsf{M a r k e t~P r i c e~o f}}\\ {\mathsf{l n t e r e s t~R a t e~R i s k}}\end{array}\right.
$$  

Similarly for the right hand side of (3).

# No Arbitrage Implication 1

Equality (3) applies to all securities that depend on the interest rate.

All assets that depend on the interest rate No Arb it rage $\Rightarrow$ have the same market price of risk

 - That is,  for any security $V$ ,  we have

$$
{\frac{E\left[{\frac{V_{1}}{V_{0}}}\right]-{\frac{1}{Z_{0}(1)}}}{\left[{\frac{V_{1,          u}}{V_{0}}}-{\frac{V_{1,          d}}{V_{0}}}\right]}}=\lambda
$$  
-where $\lambda$ does not depend on the security considered
- This includes options,  long term bonds and so on.
- Caveat: The quantity
$$
\left[\frac{V_{1,          u}}{V_{0}}-\frac{V_{1,          d}}{V_{0}}\right]
$$  
- Can be positive or negative (for bonds,  it is negative: if interest rate is “up'",  then $V_{u}$ is“down". Thus $V_{1,          u}<V_{1,          d})$
# No Arbitrage Implication 2
- If weknow $\lambda$ ,  we can compute the price of any other security simply by inverting (4)
$$
V_{0}=Z_{0}\left (1\right)\left\{E\left[V_{1}\right]-\lambda\left[V_{1,          u}-V_{1,          d}\right]\right\}
$$  

Where do we get $\lambda?$

-- Since relation (4) holds for all securities,  it holds for the 2-period bond:

$$
\lambda=\frac{E\left[\frac{Z_{1}(2)}{Z_{0}(2)}\right]-\frac{1}{Z_{0}(1)}}{\left[\frac{Z_{1,          u}(2)}{Z_{0}(2)}-\frac{Z_{1,          d}(2)}{Z_{0}(2)}\right]}
$$  
- From the original tree we can compute
$$
\lambda={\frac{1.010705882-1.008435379}{-0.015817224}}=-0.1435
$$  

Using (5),  the price of the call option is

$$
C_{0}\ =\ Z_{0}\left (1\right)\left\{E\left[C_{1}\right]+0.1435\times\left[C_{1,          u}-C_{1,          d}\right]\right\}=0.00223
$$  

·Onceweknow $\lambda$ ,  we can compute the price of any derivative security on the interest rate,  maturing (for now) one period ahead,  by using (5).

# Option Pricing Example

: Example: How do we price a caplet? That is,  a security that pays at $i=1$ the amount

$$
\mathsf{p a y}\left (i\right)=\mathsf{N}\times\operatorname*{max}\left (r_{i}-\overline{r},          0\right)
$$  

Where $\mathsf{N}$ is some notional.

-If $N=1000$ and $\overline {{r}} =. 0168$ (at the money),  we have

$$
\begin{array}{r l}&{\mathsf{p a y}_{u}(1)\ =\ N\times\operatorname*{max}(0.0387-0.0168,         0)=21.9}\\ &{\mathsf{p a y}_{d}(1)\ =\ N\times\operatorname*{max}(0.0074-0.0168,         0)=0.}\end{array}
$$  
- We then immediately obtain
$$
\begin{array}{r l}{\mathsf{C a p l e t}\left (0\right)\!}&{=\!\; Z_{0}\left (1\right)\left\{E\left[\mathsf{p a y}\left (1\right)\right]+0.1435\left[\mathsf{p a y}_{u}-\mathsf{p a y}_{d}\right]\right\}}\\ {\!}&{=\!\; 13.97}\end{array}
$$  
# No Arbitrage Pricing
- Can we obtain the price of a 2-period bond itself $Z_{0}\left (2\right)^{\prime}$ - No! That's one of our inputs. (We used it to compute $\lambda$ - Can we obtain the price of any security that matures in period $j=2$ (rather than $j=1]$
- Yes,  by moving backward (but need more work) - We will see how to do so using a different pricing methodology
# Risk Neutral Pricing

·Recall that“Step $4^{\prime}$ in our derivations above gave us the equation (2) is

$$
V_{0}=Z_{0}\left (1\right) E^{\tilde{p}}\left (V_{1}\right)-\Delta\times\left\{Z_{0}\left (1\right) E^{\tilde{p}}\left[Z_{1}\left (j\right)\right]-Z_{0}\left (j\right)\right\}
$$  
- This equation held for any probability $\tilde{p}$ . We can thus choose a $\tilde{p}$ that makes life easier
 - What is the probability $\tilde{p}$ that makes the second term $=0^{\cdot}$
 - That is,  we want to find the probability $\pi^{*}$ suchthat
$$
Z_{0}\left (1\right) E^{\ast}\left[Z_{1}\left (j\right)\right]-Z_{0}\left (j\right)=0
$$  

Where $E^{*}[]$ denotes the expectation that uses the probability $\pi^{*}$

Develop the expectation

$$
Z_{0}\left (1\right)\left[\pi^{*}Z_{1,          u}\left (j\right)+(1-\pi^{*}) Z_{1,          d}\left (j\right)\right]-Z_{0}\left (j\right)=0
$$  

To get

$$
\pi^{*}\left[Z_{1,          u}\left (j\right)+Z_{1,          d}\left (j\right)\right]+Z_{1,          d}\left (j\right)=Z_{0}\left (j\right)/Z_{0}\left (1\right.
$$  
# Risk Neutral Probabilities

Solving the previous equation,  we obtain

$$
\pi^{*}=\frac{Z_{0}\left (j\right)/Z_{0}\left (1\right)-Z_{1,          d}\left (j\right)}{Z_{1,          u}\left (j\right)-Z_{1,          d}\left (j\right)}
$$  

$\pi^{*}$ is the risk neutral probability or risk adjusted probability of moving up in the tree. $:E^{*}\left[.\right]-$ the expectation computed using $\pi^{*}$ - is called risk neutral expectation  - The term "risk neutral" refers to the fact that under $\pi^{*}$ ,  all assets yield the risk free rate of return.  - In fact,  from its derivation in equation (7) we also have Ex on 1-period Bond

Indeed,  because under $\tilde{p}=\pi^{*}$ the last term in (6) is zero,  we have the risk-neutral pricing formula

$$
V_{0}=Z_{0}\left (1\right) E^{*}\left[V_{1}\right]
$$  
# Risk Neutral Pricing

The risk neutral pricing formula implies

$$
\begin{array}{r}{\underbrace{E^{*}\left[\frac{V_{1}}{V_{0}}\right]}_{E^{*}\left[\mathsf{R e t u r n\ o n\}V\right]}\ =\ \mathsf{R e t u r n\ o n\6-m o n t h\T b i l}}\end{array}
$$  
- Risk neutral pricing is nothing more than a "trick" to easily compute the price of derivatives.
- It implies a simple recipe to price securities:
-Recipe: 1. Assume agents are risk neutral. 2. Find risk neutrality probabilities,  that is,  find $\pi^{*}$ 3. Compute the price of derivatives using $\pi^{*}$ and discounting at the risk free rate.
# Does Risk Neutral Pricing Work?
- In the example above,  using the 2-period bond $(j=2)$ weobtain $\pi^{*}=0.643546229$
 - The call price is then
$$
\begin{array}{r l}{C_{0}\ =\ Z_{0}\left (1\right)\left (\pi^{*}\times C_{1,          u}+\left (1-\pi^{*}\right)\times C_{1,          d}\right)}\\ {\ =\ 0.9916\times\left (0.6435\times 0+0.35645\times. 006307\right)}\\ {\ =\ 0.00223}\end{array}
$$  

The price of the caplet is

$$
\begin{array}{r l} {{\mathsf{C a p l e t}} _{0}\ =\ Z_{0}\left (1\right)\times E^{*}\left[{\mathsf{p a y}}\left (1\right)\right]}\\ {=\ 0.9916\times\left (0.6435\times 21.9+0.35645\times 0\right)}\\ {=\ 13.97}\end{array}
$$  

It works beautifully

# Risk Neutral vs. True Probabilities
# Question
- Under the risk neutral probabilities,  the expected interest rate is
$$
\boldsymbol{E}^{*}\left[\boldsymbol{r}_{1}\right]=\boldsymbol{\pi}^{*}\times\boldsymbol{r}_{1,          u}+\left (1-\boldsymbol{\pi}^{*}\right)\times\boldsymbol{r}_{1,          d}=0.0275
$$  
- If your boss asks you what is your forecast of the interest rate in six months,  would you tell him $2.75\%?$
In the real world,  the expected interest rate was
$$
E\left[r_{1}\right]=2.305\%<2.75\%=E^{*}\left[r_{1}\right]
$$  
- Passing from the real to the risk neutral world implies increasing the expected interest rate.
- Interestingly,  note that the forward rate is (recall the time step is 0.5)
$$
F (0,         1,         2)=-2\times\ln\left (\frac{Z_{0}(2)}{Z_{0}(1)}\right)=2.7487\%
$$  

This is very close to the risk-neutral expected future rate

# Using Risk Neutral Trees
- From now on,  we assume that the tree that we are using is "risk neutral'
- Rather than finding probabilities that make an original "true" tree into a risk neutral one,  we start immediately from the latter.
- We will see later how to build a tree that is risk neutral directly from traded securities
- Suppose that the short-term,  continuously compounded interest rate moves according to the following tree.
- At every time (1 period $=6$ months),  there is equal risk neutral probability ( $'\pi^{*}=1/2)$ to move up or down.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/5faaa98f8519ffffa172a4a8b2c30f6907b6f191a2d12ef3b5a250bb3736183f.jpg)
- The value of a zero-coupon bond paying one dollar in period $i=1$ is (the time step $\Delta t=0.5)$
$$
Z_{0}\left (1\right)=e^{-r_{0}\times\Delta t}\times 1=0.9916
$$  
- What is the value of bond paying $\$ 1$ in one year $(i=2)?$
 - It can be obtained by proceeding backward on the tree:
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/6d5b52d232183b94803dc4d7fc869dd40e7c06e89d7172f4afcb01417b6eced1.jpg)
# - Similarly,  a bond paying $\$ 1$ in 1.5 years $(i=3)$

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/a3e2b390fb0cb17777c1c6fc99c72e022fd2b32cd3dd891505ea8b715650a03d.jpg)

These prices imply the zero-coupon yields

$$
Y_{0}(1)\ =\ -\frac{\ln[Z_{0}(1)]}{\Delta t}=0.0168
$$  

·The methodology is actually quite simple.

- In addition,  computers can be programmed rather easily to carry out the backward computation.
Example:
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/e447543da05843dd99e3a84b2d43ef6a0f28309298449854a43cd737346567a9.jpg)
# Describing Big Trees
# How do we describe a long tree?
- Using the earlier notation $u$ ,  uu etc is $\mathsf{O K}$ for small trees
 - When we start looking at long trees (30-60 steps),  then we use a slightly different notation
 - Specifically,  each point on the tree can be described by a time index $i$ and a node index $j$ - In the example in Table 2,  $i=0,         …,          10$ and $j=1,         …,          11$
# Intermediate Cash Flows
- Notice that given a tree,  we can insert any type of known cash flow.
- Specifically,  at any time-node $(i,          j)$ ,  we just must add the CF
$$
P_{i,          j}=e^{-r_{i,          j}\Delta t}\left (\frac{1}{2}P_{i+1,          j}+\frac{1}{2}P_{i+1,          j+1}+C F_{i+1}\right)
$$  
- So,  for example,  a 1.5 year,  $4\%$ coupon bond is just given by
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/c593ca25acf22b7ec62de03287e0de8a70de69231d3e0b5a137bbe70458bf1ac.jpg)
This tree gives “ex-coupon" prices.
- Using ex-coupon prices is useful in a number of circumstances,  as we shall see
# Examples
- Trees turn out to be very useful tools (not only pedagogical ly)
- One of the most important features of them is the ability to deal with "American options.
- As a consequence,  a very simple application of the "tree" methodology is the computation of prices of callable bonds.
# Callable Bonds

Consider the 1.5 year,  $4\%$ coupon bond we discussed earlier,  but assume it is callable at par 100

- That is,  at any point in time before maturity,  the issuer (Treasury) may "call it back" in exchange of 100. - In general,  bonds become callable after some period of time. - For example,  the Nov 2012 Treasury bond is callable at par starting on Nov 2007. - If issuer calls the bond between coupon days,  it has to pay the accrued interest to the bond holder.
# How do we Compute the Price of American Options?

We move backwards on the tree:

- At any node $(i,          j)$ the issuer can decide whether to “exercise" option or wait - If exercises,  the payoff ( $\acute{=}$ value of the option) is
$$
C a l l_{i,          j}^{\mathtt{E x}}=P_{i,          j}-100
$$  
- If waits,  the value of the option
$$
C a l l_{i,          j}^{\mathsf{W a i t}}\ =\ e^{-r_{i,          j}\Delta t}E^{*}\left[C a l l_{i+1}\right]=e^{-r_{i,          j}\Delta t}\left (\frac{1}{2}C a l l_{i+1,          j}+\frac{1}{2}C a l l_{i+1,          j}\right)
$$  
- Therefore,  the value at node $i,          j$ is
$$
\begin{array}{r l}{C a l l_{i,          j}}&{=\ \operatorname*{max}\left (C a l l_{i,          j}^{\mathsf{W a i t}},          C a l l_{i,          j}^{\mathsf{E x}}\right)}\\ &{=\ \operatorname*{max}\left (e^{-r_{i,          j}\times\Delta t}E^{*}\left[C a l l_{i+1}\right],          P_{i,          j}-100\right)}\end{array}
$$  
- Since at maturity $I=T/\Delta t$ we have
$$
C a l l_{I,          j}=0\textsf{f o r a l l}_{j}
$$  
- (the option expires worthless at maturity,  as the issuer has to redeem the bond at par) - we can start the procedure (1 o) backward.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/0e2b105bed484ef0c52c7b8185c7975328d2d6f06e64a90bcd34482567e276fd.jpg)
# Callable Bond Pricing
# What is then the price of the callable bond?
- The buyer of a callable bond is: (1) buying a non-callable bond; $+$ (2) Selling a call to the issuer. -Hence,
$$
\begin{array}{l}{P_{\mathrm{0}}^{\mathbf{C}^{\mathbf{all}}}\left (3\right)\ =\ P_{\mathrm{0}}^{\mathbf{No}\mathbf{C}^{\mathbf{all}}}\left (3\right)-C_{0}\left (\right.}\\ {\ =\ 101.93-1.16\ }\\ {\ =\ 100.77}\end{array}
$$  
# Caps and Floors
- A cap is a security that pays the stream of cash-flows
$$
C F\left (t\right)=\Delta t\times N\times\operatorname*{max}\left (r\left (t-1\right)-\overline {{r}} ,         0\right)
$$  

 - where $\bar{r}$ is the strike rate,  $r\left (t\right)$ is some floating rate interest rate,  such as the three month t-bill rate or LlBOR,  $N$ is the notional and $\Delta t$ is the amount of time between payments.

 - Each payment (11) is called “caplet"

- Caps offer insurance against the interest rate increasing to above some level. - They are often attached to floating rate bonds,  so as to limit the amount of interest to pay
- A floor is instead a security paying
$$
C F\left (t\right)=\Delta t\times N\times\operatorname*{max}\left (\overline {{r}} -r\left (t-1\right),          0\right)
$$  
# Cap Pricing Example
- Consider a 1.5 years cap,  with continuously compounded strike rate $\overline {{r}} =3\%$ ,  semi-annual payments ( $\Delta t=1/2$ and $N=100$
 - Assume that the risk-neutral tree is given by (18) and let
$$
\begin{array}{r l}{C F_{i,          j}\left (i+1\right)}&{=\textsf{C a s h F l o w a t i m e}i+1,         \textsf{e}}\\ &{=\mathrm{\small~\displaystyle\frac{1}{2}\times N\times\operatorname*{max}\left (r_{i,          j}-\overline {{r}} ,         0\right)~}}\end{array}
$$  

We then have:

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/273fea836de087904517e4522a4cca7f0befedadd2b10446c15ce60ce3578472.jpg)

# Cap Pricing Example

Given these cash flows,  define

$$
\begin{array}{r}{V_{i,          j}\ =\ \mathsf{V a l u e\ a t\ t i m e\ i\ o f\ a l l\ C a s h\ F l o w s\ a t\ t i m e s\ k}>}\\ {\ =\ e^{-\frac{1}{2}r_{i,          j}}\times\left (\frac{1}{2}V_{i+1,          j}+\frac{1}{2}V_{i+1,          j+1}+C F_{i,          j}\left (i+1\right)\right)}\end{array}
$$  
- Then,  the following backward tree gives a cap price $V_{0}=0.87$
 - Table 3 shows the pricing of a cap on the bigger tree in Table 2,  with $\overline {{r}} =5\%$ ;and $N=100$
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/4d3fb85ecd6efbc0508695ee304af156ee2781858c0d4ad9c191ac7a5e540a69.jpg)
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/51d603aa19ddeb9cc122b4c939df1562112e4d01272c38eac905b1d3c5944f48.jpg)
# Swaps and Swaptions
- Similarly,  the computation of Swaps and Swaptions (options to enter into a Swap) are simple
- Consider a 2 year swap (Maturity $=i=4.$ ),  with swap rate (c.c.) $\overline {{r}} =. 0304$，$N=100$
Again,  denote by
$$
C F_{i,          j}\left (i+1\right)\ =\ \mathsf{C a s h\ F l o w\ a t\ t i m e}
$$  

We obtainthe treeof cash flowsi

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/8e142808268b9967cc24efc4cf04b186d278725e1b0708d4bd2cfc0d7d67d669.jpg)

- The tree for the value of the swap (for the fixed payer) is then immediately computed.
Denoting again
$$
\begin{array}{c l} {{V_{i,         j}} }& {{=\mathrm{\sf~V a l u e~a t~t i m e~}i\mathrm{\sf~of~}{\sf a}{\sf I}\backslash\mathrm{\sf~C a s h F l o w s~a t~t i m e s~}k>i}} \\ {{}} & {{=\mathrm{\it~e}^{-{\frac{1}{2}} r_{i,          j}}\times\left ({\frac{1}{2}}V_{i+1,          j}+{\frac{1}{2}}V_{i+1,          j+1}+C F_{i,          j}\left (i+1\right)\right)}}\end{array}
$$  

We obtain

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/430146ba98cf274450388394123e3187d8628f9115823dfeb502436200a0b812.jpg)

·The swap rate $\overline {{r}} =0.0304$ was chosen to make the value of the Swap contract $=0$ attime $i=0$

# Swaptions
- A Swaption is an option to enter into a swap,  at a given swap rate $r_{X}$
- A Receiver Swaption is an option to enter into a swap and receive fixed $r_{X}$ -- A Payer Swaption is an option to enter into a swap and pay fixed $r_{X}$
- Computing now the value of a European Swaption is simple
- Consider for instance a European Swaption with maturity $T=1$ (i.e. $i=2$ ) to enter a one year swap and pay fixed $r_{X}=. 0304$ -Let $\overline {{r}} _{i j}$ be the swap rate in the node $i j$ 2. -Then: $^*$ If $\overline {{{r}} }_{2 j}>r_{X}$ we exercise the option (we pay $r_{X}$ instead of current rate $\bar{r}_{2 j}$）$^*$ If $\overline {{r}} _{2 j}<r_{X}$ we do not exercise the option (we are better off paying the market rate $\overline {{r}} _{2 j}$
 - It looks complicated. How do we model this decision?
- We remember that the swap rate $\overline {{r}} _{i j}$ is determined in node $i j$ to make the value of the swap at that node equal to O.
# Swaptions
- Therefore,  we first compute the value of the swap with given swap rate $r_{X}$ along the tree $V_{i,          j}$
$$
V_{i,          j}=e^{-r_{i,          j}\Delta t}\left (\frac{1}{2}V_{i+1,          j}+\frac{1}{2}V_{i+1,          j+1}+(r_{i,          j}-r_{X})\right)
$$  

Since

- We exercise at time $i=2$ in node $j$ if and only if $V_{2 j}>0$
- The payoff of the swaption at $i=2$ is then
$$
\mathsf{P a y o f f_{2 j}}=C_{2,          j}=\operatorname*{max}\left (V_{2 j},          0\right)
$$  
- The value of the European Swaption can then be computed by backward calculations:
$$
C_{i,          j}=e^{-r_{i j}\Delta t}\left (\frac{1}{2}C_{i+1,          j}+\frac{1}{2}C_{i+1,          j+1}\right)
$$  
# Swaptions: Example
- Consider receiver swaption with a strike swap rate $r_{X}=. 0304$
 - The swaption is at the money,  that is $r_{X}=\overline{r}_{0}=$ current swap rate at 0.
 - The relevant tree for $V_{i,          j}$ is then the one given earlier.
 - Since $V_{2,          u u}=3.31$，$V_{2,          u d}=0.86$ and $V_{2,          d d}=-1.68$ ,  we only exercise in the top two nodes at $i=2$
 - The tree to value the swaption is then given by:
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/677ea1759fa6607fabf1b023d9e2278ad12208922575bd73b308c1140d4645f1.jpg)
# American Swaptions: Example
- Computing an American style swaption exploits the same methodology illustrated earlier. That is,  we must have
$$
C_{i,          j}^{A m}=\operatorname*{max}\left (V_{i,          j},         \ e^{-r_{i,          j}\Delta t}\times\left (\frac{1}{2}C_{i+1,          j}^{A m}+\frac{1}{2}C_{i+1,          j+1}^{A m}\right)\right)
$$  

In this case,  we find

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/f87aec40503ac495b4f169fcf41d0ab3dbdbb06d36492cd9699f05efaa6ae276.jpg)

# Swaptions: Examples

 - Note that $C_{0}^{A m}=1.53>C_{0}=1.22$ . An American option always gives more “rights" than the European option

 - Note also that we exercise before maturity at node $(1,          u)$

 - In a slightly more serious exercise,  we have a table like the following:

 - Let the "Terms'" be:

$-\;\overline {{{r}} }=0.03999;$ $-\; T=5$ years; -Semi-annual payments; - At-the-money Payer Swaption with $T^{*}=3$ years: - (In the last panel,  a "\*” denotes early exercise of the option)

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/976bef913c4d6d12057cbbca274dea804a9f5ea58781609b652248e3cc54fde9.jpg)

European Option

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/8860826d0ada9575f06dad15a986f603acbc01aab72c84028ac88c157046a1b1.jpg)

# Tree Building
# How can we construct a tree?
- There are various models and methodologies. We consider two simple models here.
# The Ho-Lee Model

 - The Ho-Lee model makes a simple assumption about the dynamics of the short-term interest rate.

 - Let $\Delta t$ be the time step. Then,  for every node $(i,          j)$ the next interest rate is given by

$$
\begin{array}{r}{r_{i+1,          j}\ =\ r_{i,          j}+\theta_{i}\times\Delta t+\sigma\times\sqrt{\Delta t}\quad\mathsf{f o r\ a\ "u p}\mathrm{"\m o v e m e n t}}\\ {r_{i+1,          j+1}\ =\ r_{i,          j}+\theta_{i}\times\Delta t-\sigma\times\sqrt{\Delta t}\quad\mathsf{f o r\ a\ "d o w n"\m o v e m e n t}}\end{array}
$$  
- Where the risk neutral probability of an up movement is $\pi^{*}=0.5;$ $\sigma$ is the annualized volatility; and $\theta_{i}$ arechosen recursively so as to fit the current term structure of interest rates.
- The tree from Ho Lee is naturally recombining: an “up $+$ down" movement produces the same interest rate as a"down $+$ up' movement.
-- To see this easily,  consider $r_{0}$ and use the $"u,         \,          d,         $ ud,  du' notation.
$$
\begin{array}{r}{r_{1,          u}\ =\ r_{0}+\theta_{0}\times\Delta t+\sigma\times\sqrt{\Delta t}}\\ {r_{1,          d}\ =\ r_{0}+\theta_{0}\times\Delta t-\sigma\times\sqrt{\Delta t}}\end{array}
$$  
- Similarly,  the next steps are:
$$
\begin{array}{l}{r_{2,          u d}\ =\ r_{1,          u}+\theta_{1}\times\Delta t-\sigma\times\sqrt{\Delta t}}\\ {\ =\ r_{0}+\left (\theta_{0}+\theta_{1}\right)\times\Delta t}\end{array}
$$  
- And
$$
\begin{array}{r l}{r_{2,          d u}\ =\ r_{1,          d}+\theta_{1}\times\Delta t+\sigma\times\sqrt{\Delta t}}\\ {=\ r_{0}+\left (\theta_{0}+\theta_{1}\right)\times\Delta t}\\ {=\ r_{2,          u d}}\end{array}
$$  

How do we select $\theta_{i}$ ?

-Wechoose $\theta_{i}$ iterative ly from $i=0,         \,          1,         \,         \ldots,         \,          n,         $ ,  to fit the zero-coupon bond prices. - To illustrate,  consider the zero-coupon bonds

$$
Z_{0}\left (1\right)=0.9916,         \; Z_{0}\left (2\right)=0.9781,         \; Z_{0}\left (3\right)=0.9615
$$  
- We already have the root of the tree: $r_{0}=-\ln (Z_{0}(1))/2=0.0169.$ - We next must choose $r_{1 u}$ and $r_{1 d}$ .Let volatility be $\sigma=. 015$ -We can search for $\theta_{0}$ such that the value of the bond from the tree equals $Z_{0}\left (2\right)=0.9781$
# -- Given a $\theta_{0}$ we have
$$
I=0
$$  
$$
\begin{array}{c}{r_{1,          u}=r_{0}+\theta_{0}\times\Delta t+\sigma\times\sqrt{\Delta t}}\\ {Z_{1,          u}\left (2\right)=e^{-r_{1 u}\times\Delta t}}\end{array}
$$  

$r_{0}=1.69\%$ $Z_{0}\left (2\right)=Z_{0}(1)\times\left[\textstyle{\frac{1}{2}}Z_{1,          u}(2)+\textstyle{\frac{1}{2}}Z_{1,          d}(2)\right]$ = 0.9781

$$
\begin{array}{r}{r_{1,          d}=r_{0}+\theta_{0}\times\Delta t-\sigma\times\sqrt{\Delta t}}\\ {Z_{1,          d}\left (2\right)=e^{-r_{1,          d}\times\Delta t}}\end{array}
$$  
- We want to search over $\theta_{0}$ so that
$$
Z_{0}(2)=0.9781
$$  
- Searching over $\theta_{0}$ we find $\theta_{0}=. 021145$ ,  resulting thus in
# $i=0$
$$
I=1
$$  
-Given $\theta_{0}$ ,  we now look for $\theta_{1}$ by trying to match the next bond $Z_{0}(3)=0.9615$
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/fdbcf1bd8076cc08d02a9601485aa29510578aba24b346e1acebe7072819a775.jpg)
 - Clearly,  $Z_{0}(3)$ from the tree only depends on $\theta_{1}$
 - Searching for $\theta_{1}$ yields $\theta_{1}=0.013807$ ,  yielding
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/4226fa90f3875e1a2433a7e855955de7050a2efabf74c55116ac090677ae6e12.jpg)
- And so on for all the possible available maturities.
# The Simple Black-Derman-Toy
- One potential issue with the Ho-Lee model is that interest rates can easily get negative. If $\sigma$ is large,  for instance there is nothing in the procedure above that guarantees that $r_{i,          j}>0$
- A simple solution is to model the Ho-Lee mode in “"logarithm",  that is,  let $z_{i j}=\ln (r_{i j})$ and then assume
$$
\begin{array}{r}{z_{i+1,          j}\ =\ z_{i,          j}+\theta_{i}\times\Delta t+\sigma\times\sqrt{\Delta t}}\\ {z_{i+1,          j+1}\ =\ z_{i,          j}+\theta_{i}\times\Delta t-\sigma\times\sqrt{\Delta t}}\end{array}
$$  

Clearly,  even if $z_{i j}<0$ we have $r_{i j}=e^{z_{i j}}>0$

 - Note that now $\sigma$ is the standard deviation of log interest rates. It can be estimated from $\Delta\ln (r_{t})$ - Note that to a first order approximation $\begin{array}{r}{\Delta z_{t}\approx\frac{1}{r_{t}}\Delta r_{t}}\end{array}$ - Therefore,  $\sigma (\boldsymbol{z}_{t})\approx\sigma (\boldsymbol{r}_{t})/r_{t}$ - In the previous example,  $\sigma (r_{t})=0.015$ and $r_{0}=1.69\%$ ,  and thus $\sigma (z_{t})\approx 88.91\%.$ - Using the same procedure,  we obtain $\theta_{0}=0.603652218$，$\theta_{1}=0.089246544$ and the binomial tree

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/991b1effc316f809254e91720ea82f1c2b4e8ce05115219835b460053f8ea2f9.jpg)

# The Black-Derman-Toy Mode
- The previous models are popular,  but they have constant volatility.
 - It is hard for them to match the term structure of volatility,  that is,  the fact that options of different maturity may have different volatility.
 - The Black-Derman-Toy model still assume $z_{i,          j}=l o g (r_{i,          j})$ as in the simple BDT,  but it assumes that between $i$ and $i+1$ ,  for every two adjacent nodes $j$ and $j+1$ ,  the variance is
$$
\sigma_{i+1}^{2}\Delta t=V a r i a n c e[z_{i}|z_{i-1,          j}]
$$  

 - This implies that for every node $j$

$$
\begin{array}{r l}{\sigma_{i+1}^{2}\Delta t\ =\ V a r i a n c e[z_{i}|z_{i-1,          j}]}\\ {\ =\ \cfrac{1}{2}\left (z_{i,          j}-E[z_{i}|z_{i-1,          j}]\right)^{2}+\cfrac{1}{2}\left (z_{i,          j+1}-E[z_{i}|z_{i-1,          j}]\right)^{2}}\\ {\ =\ \cfrac{1}{2}\left (z_{i,          j}-\cfrac{1}{2}z_{i,          j}-\cfrac{1}{2}z_{i,          j+1}\right)^{2}+\cfrac{1}{2}\left (z_{i,          j+1}-\cfrac{1}{2}z_{i,          j}-\cfrac{1}{2}z_{i,          j+1}\right)^{2}}\\ {\ =\ \cfrac{1}{2}\left (\cfrac{1}{2}z_{i,          j}-\cfrac{1}{2}z_{i,          j+1}\right)^{2}+\cfrac{1}{2}\left (\cfrac{1}{2}z_{i,          j+1}-\cfrac{1}{2}z_{i,          j}\right)^{2}}\\ {\ =\ \cfrac{1}{4}\left (z_{i,          j}-z_{i,          j+1}\right)^{2}}\end{array}
$$  

The final equation is then

$$
\sigma_{i+1}\sqrt{\Delta t}=\frac{1}{2}\left (z_{i,          j}-z_{i,          j+1}\right)
$$  
- We then need two types of inputs in this model
1. The current term-structure of yields 2. The current term-structure of forward volatility of interest rates
- The forward volatility can be estimated from options (caps and floors),  and it reflects the volatility of forward rates with the indicated maturity.
Therefore,  assume the following data
Table 1: Inputs to BDT Model
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/6c1964c8b9a175c35b079c72debf035f72e99501aaed9772122b81fe97d2568d.jpg)
- Objective: Construct an interest rate tree that matches the data in Table 1 exactly
$$
I=0\qquad\quad i=1\qquad\quad i=2\qquad\quad i=3
$$  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/6842b4c6aa5daab5d96960b04de6a2df5cf2597952937bbfd81775a979ecaa77.jpg)

(18)

- For every two states $j$ and $j+1$ ,  using equation (17) we can rewrite
$$
Z_{i,          j+1}=z_{i,          j}-2\sigma_{i+1}\sqrt{\Delta t}
$$  

Or

$$
Z_{i,          j+1}=z_{i,          1}-2\times j\times\sigma_{i+1}\sqrt{\Delta t}
$$  
- The unknowns in our original model,  with $\Delta t=1$ arethen
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/4217a513628b2f41150dfb289e83a21cb4330eed0058f5c0a934abaea5951dae.jpg)
·At time $i=1$ we look for $z_{1,          u}$ ,  at time $i=2$ we need to look for $z_{2,          u u}$ etc.
 - Since we are already using the "volatility” condition,  the only equation to satisfy for every $i$ is the bond price out of the tree corresponds to the data $Z (0,          T_{i})$ that we have available.
 - This last computation can be done recursively by going backward from the end of the tree,  as usual.
- Example: Suppose you had the data (extracted from Bloomberg)
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/69681711219bff520e7f1b314a667b7fd0b35da38323e55b189959c71b6ba3ec.jpg)
- The implied BDT tree (already in interest rate format $r_{i j}=e x p (z_{i j})$ that matches the data is
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/b7152f3a01088c202436cf6c438f206b15ea682d5cd13f7d42ab8370b2dedb5a.jpg)
# Monte Carlo Simulations on Binomial Trees
- Monte Carlo simulations is the most popular methodology to price securities
- Consider a one-step risk neutral binomial tree with equal chance of up or down movement.
 - We want to price an interest rate option that pays at time $i=1$
$$
C_{1}=100\times\operatorname*{max}(r_{1}-r_{K},          0)
$$  

Where $r_{K}$ is the strike rate.

 - Using risk neutral pricing,  the value of the option is

$$
C_{0}=E^{*}\left[e^{-r_{0}\times T}\times c_{1}\right]=e^{-r_{0}\times T}\left[{\frac{1}{2}}\times c_{1,          u}+{\frac{1}{2}}\times c_{1,          d}\right]
$$  

Next figure computes the value of the option for a given binomial tree.

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/163a8126a834ebb33a27c829aab8de145efa1a9782918c57393ee35bb27f7fb0.jpg)

# Monte Carlo Simulations on Binomial Tree
- Another way of computing the expected future payoff is to simulate upward and downward movements in the tree using a computer
- In Excel and Matlab the function $R A N D ()$ simulates a uniform $[0,         1]$ random variable We can simulate $R A N D ()$ a large number $N$ of times,  and then impose the following?
$(a)$ If $R A N D ()<0.5\Longrightarrow$ the interest rate moved up the tree $(b)$ If $R A N D ()\geq 0.5\Longrightarrow$ the interest rate moved down the tree
- For each of realization $s$ of $R A N D ()$ ,  we use the correspond ong simulated $r_{1,          u}^{s}$ or $r_{1,          d}^{s}$ to compute the option payoff.
$$
C_{1}^{s}=100\times\operatorname*{max}\left (r_{1}^{s}-r_{K},          0\right)
$$  
- We can compute the expected discounted payoff in (21) as the average of the discounted payoff across all simulations:
$$
\begin{array}{l} {{\displaystyle\hat{c}_{0}~=~\mathsf{a v e r a g e\ o f}~\left\{e^{-r_{0}\times T}\times c_{1}^{1},         e^{-r_{0}\times T}\times c_{1}^{2},         e^{-r_{0}\times T}\times c_{1}^{3},         ...,         e^{-r_{0}\times T}\right\}} }\\ {{\displaystyle}} \\ {{\displaystyle=~\frac{1}{N}\sum_{s=1}^{N}e^{-r_{0}\times T}c_{1}^{s}} }\end{array}
$$  

Next Table illustrates the procedure

- The first column reports the simulation number. -The second column displays the actual realization of the $R A N D ()$ function inExcel - The third column tells us the movement in the tree implied by the $R A N D ()$ realization - The fourth column reports the payoff at maturity,  i.e. $c_{1}^{s}=100\times\mathrm{max}(r_{1}^{s}-r_{K},          0)$ - The last column computes the discounted payoff,  $e^{-r_{0}\times T}\times c_{1}^{s}$
Ten Simulations on the Binomial Tree
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/5c9a700702d8ec27869d29b3d3c7187e38d41b836bc999e3b45349fe10a83e29.jpg)
# The simulated value is
$$
\begin{array}{r}{\hat{c}_{0}=0.693.}\end{array}
$$  
-With only $N\,         =\,          10$ simulation,  it is no surprise that the value of the security $\hat{c}_{0}\,         =\,          0.693$ comes in rather different than the value from the tree ( $\left. C_{0}=0.8660\,         \right\}$ 一：
- However,  as the number of simulations $N$ increases,  the value from the simulations becomes more and more accurate.
For instance
# Monte Carlo Simulations on Binomial Trees

Consider once again the same option,  but now with one year to maturity,  i.e. $i=2$

$$
I=1
$$  
$$
I=2
$$  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/f77d804db5da7e1faea94cc681d1d5e95bd3b65d51f8530ce5a32e6800921113.jpg)

- First note that the backward computation methodology is equivalent to the outright calculation of the value of the security as the risk neutral present discounted value of the payoff at maturity,  discounted at the risk free rate.
That is,  the value of the security is equal to
$$
\begin{array}{r l}{c_{0}~=~}&{E^{*}\left[\underbrace{\left (e^{-r_{0}\times 0.5}\right)}_{\begin{array}{l}{(\mathsf{D i s c o u n t}~1\to 0)}\\ {(\mathsf{D i s c o u n t}~2\to 1)}\end{array}}\times\underbrace{\left (e^{-r_{1}\times 0.5}\right)}_{\begin{array}{l}{(\mathsf{D i s c o u n t}~3\to 1)}\\ {(\mathsf{D i s c o u n t}~2\to 1)}\end{array}}\times\underbrace{c_{2}}_{\begin{array}{l}{\mathsf{P a y o f f~a t}~2}\end{array}}\right]}\\ {~}&{~}\\ {~=~E^{*}\left[e^{-(r_{0}+r_{1})\times 0.5}\times c_{2}\right]}\end{array}
$$  
- Indeed,  the interest rates $r_{2,          u u},         \; r_{2,          u d},         \; r_{2,          d u}$ and $r_{2,          d d}$ occur with a $25\%$ chance.
Thus,  the value of the option is also equal to
$$
\begin{array}{r l}{c_{0}~=~0.25\times e^{-(r_{0}+r_{1,          u})\times 0.5}\times c_{2,          u u}+0.25\times e^{-(r_{0}+r_{1,          u})\times 0.5}\times c_{2,          u d}}\\ &{+0.25\times e^{-(r_{0}+r_{1,          d})\times 0.5}\times c_{2,          d u}+0.25\times e^{-(r_{0}+r_{1,          d})\times 0.5}\times c_{2,          d d}}\\ {~=~1.7784,         }\end{array}
$$  

 - the same price as from the tree

- We now perform exactly the same simulation exercise as before two realization s of $R A N D ()$
- The only caveat now is to figure out how we should discount simulated cash flows back to time Ol
- From (24),  and its explicit development in (25) and (26) we must discount cash flow by using the realized interest rate path in that simulation.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/eabc9799bcb39b49ea6ac3a121eb96e51e26ee495b9373a2fc2da82f814634e7.jpg)
Higher number of simulations improves accuracy:
$$
\begin{array}{l}{N\ =\ 10\Longrightarrow\hat{c}_{0}=1.975}\\ {N\ =\ 1,         000\Longrightarrow\hat{c}=1.839}\end{array}
$$  
# Monte Carlo Simulations for Path Dependent Securities
- Many securities have payoffs that are path dependent
- The payoff at maturity depends on the whole path taken by interest rates before maturity -Examples include $^*$ Asian options: Payoff at maturity depend on average interest rates; $^*$ Corridor bonds: Pay coupon so long interest rate is within a band; \* Amortizing Interest Rate Swaps: The notional of IRS depend on path of interest rates: \* Mortgage Backed Securities: Because of frictions in deciding when to pay back mortgage,  payoff depends on path of interest rates (and many other variables)
- The pricing of path dependent securities is easier to perform using Monte Carlo simulations
# Example: Asian Options
- An Asian interest rate option is an option whose payoff at maturity is given by
- This payoff makes the binomial tree non-recombining,  as the payoff from "up-down movement" is different from the payoff from a"down-up movement'
 - Denote by $\overline {{r}} _{i,          j}=a v e r a g e (r_{k})$ for $k\leq j$ on the path to $(i,          j)$
 - For such short binomial tree we can still compute the value of path-dependent security using backward calculation
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/269c974a8795fd7d57ce2689b3b2a795a525d077559688bd4977a3d467cc563a.jpg)
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/1c3983ddd488a60b650336c5261fb79419a55bef91bfe9ef4054df41ecabcb25.jpg)
# Monte Carlo Simulations for Path Dependent Securities

·The tree becomes non-recombining. When we use "big trees",  this is a serious problem

- For instance,  for mortgage backed security with monthly payment we need a tree with 360 steps. This implies a treewith $2^{360}=2.345 E+108$ nodes by the end of the tree (!).
- MC simulations do not require a backward calculation. Problem solved!
 - In the example above,  with 10 simulations,  we obtain the following table
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/a62f02b4259072b1e79b13fd03dafb094d5ee64cc2d9c7f1020717d20c8f0e18.jpg)
# Monte Carlo Simulations with Multi Step Trees
- The approach readily extends to multi-period binomial trees,  which is an important extension as it allows us to evaluate relatively complex securities
- For instance,  in the Ho-Lee model we can simulate directly the tree
$$
\begin{array}{r}{r_{i+1,          j}\ =\ r_{i,          j}+\theta_{i}\times\Delta+\sigma\times\sqrt{\Delta}}\\ {r_{i+1,          j+1}\ =\ r_{i,          j}+\theta_{i}\times\Delta-\sigma\times\sqrt{\Delta}}\end{array}
$$  
# Ho-Lee Binomial Tree

PanelA: TheHo-Lee Interest Rate Tree

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/1f81e1ba7c162aae8887bea17ef7804c486b848e8882160e24367eb80c583348.jpg)

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/bc48b1d29a75880d1efcf266df06b0828e405786f2fe6dfffb58907b269c35b1.jpg)

# Simulations on Ho-Lee Binomial Tree

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/b67a444a55086a25cf8e3bfbf560bd6233c84980f701785e17b6dfce462f0d22.jpg)

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/e501be0a61ffabe18d0324b920ac213df4d1ae582a2a2b9fb369ae10a179a8a4.jpg)

# Ho-Lee Binomial Tree: Simulated Discounts
- For each simulated path $r_{0},         \; r_{1}^{s},         \; r_{2}^{s},         …,          r_{k-1}^{s}$ ,  compute the simulated zero with maturity $T_{k}$ as
$$
Z^{s}(0,          T_{k})=e^{-\sum_{i=1}^{k-1}r_{i}^{s}\Delta t}
$$  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/68dbd4c329bc64e44a7248f321926728fb851cbfbfc87b53f70e1aeccc93ae7e.jpg)

- Maturity $T_{i}$
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/0f28b132c23347553ea3f104cb91b927f580e8e3a1665bb1b272defaf2c272eb.jpg)
# Simulated Ho-Lee Binomial Tree: Valuation of Zero-Coupon Bonds
- The simulated value of a zero coupon bond is the average across simulated discounts
$$
\widehat{Z}(0,          T_{k})=\frac{1}{N}\sum_{s=1}^{N}Z^{s}(0,          T_{k})
$$  
- The simulated values with $N=1000$ are reported in the next table,  together with the data used to fit the Ho-Lee treemodel
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/c9e952c1f2b7d30d42d7d99b5307faf970743989aef01f80ccd4f5d6c22f0e36.jpg)
# Simulated Ho-Lee Binomial Tree: Valuation of an Interest Rate Option
- The same valuation methodology can be used to price long-term options,  such as one paying at $i=1,         …,          10$
Risk neutral pricing implies that the price of this option is given by
$$
\begin{array}{r l}{c_{0}(T_{i})}&{\!=\!\phantom{\frac{}{}}E^{*}\left[\mathsf{P r e s e n t\ v a l u e\ o f\ p a y o f f\ a t\}T_{i}\right]}\\ &{\!=\!\phantom{\frac{}{}}E^{*}\left[e^{-(r_{0}+r_{1}+\ldots+r_{i-1})\times\Delta}\times 100\times\operatorname*{max}\left (r_{i}-r_{K},          0\right)\right]}\end{array}
$$  
- For each simulation path $s,         \; r_{0},         \; r_{1}^{s},         \; r_{2}^{s},         ….,         \; r_{n}^{s},         \; s=1,         ..,          N$ ,  we compute the discounted payoff
$$
\begin{array}{r l}{c_{0}^{s}(T_{i})}&{\!=\!\phantom{\frac{1}{1}}e^{-\left (r_{0}+r_{1}^{s}+r_{2}^{s}+\ldots+r_{i-1}^{s}\right)\times\Delta}\times 100\times\operatorname*{max}\left (r_{i}^{s}-r_{K},          0\right)}\\ &{\!=\!\phantom{\frac{1}{1}}Z^{s}(0,          T_{i})\times\times 100\times\operatorname*{max}\left (r_{i}^{s}-r_{K},          0\right)}\end{array}
$$  
- Where we used. $Z^{s}(0,          T_{i})=e^{-\left (r_{0}+r_{1}^{s}+r_{2}^{s}+\ldots+r_{i-1}^{s}\right)\times\Delta}.$
- Today's value of the option with maturity $T_{i}$ is then given by the average of $c_{0}^{s}(T_{i})$
$$
\hat{c}_{0}(T_{i})=\frac{1}{N}\sum_{s=1}^{N}c_{0}^{s}(T_{i})
$$  
- Panel A of next table reports the value of interest rate options with maturity from $T_{i}=0.5$ to $T_{i}=5$ and fora strikerate $r_{K}=1.74\%$
- Panel B of next table shows the results of the first ten simulated discounted payoffs in (32) - For instance,  the first element of the first row is given by
$$
\i (0.5)=Z^{1}(0,         0.5)\times 100\times\operatorname*{max}(r_{1}^{1}-r_{K},          0)=0.9913\times 100\times\operatorname*{max}(r_{1}^{0}-r_{K},          0)
$$  
- Where the sequence of the simulated interest rate and discounts are given in Panels B and C of previous table. Similarly,  the second entry in the first row is given by
$$
100\times\operatorname*{max}(r_{2}^{1}-r_{K},          0)=0.9849\times 100\times\operatorname*{max}(3.61\%-1.74\%,          0)=
$$  
- The option values in Panel A are then computed as the average of values in the corresponding column in Panel B - (although the average is taken over all the 1,  0 o 0 simulated paths,  rather than only the ten paths reported in Panel B).
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/e1a39cc0dba6085f4a39ec1a4a44bf57fb51b38ae1c91d849e4ba68ac46e2705.jpg)
# How Many Simulations are Enough?
- A price of a security computed by Monte Carlo Simulations is an estimate of the true price. - Using simulations we are generating a sample of observations of the price of the security - Because it is an estimate,  we can compute the price's standard error.
- For instance,  the first two rows in next Table reports the prices (again) and standard errors of the long-term interest call options discussed earlier .
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/653497b3ade6a44e0b88a0c3fdcaad2e0e48caec0dc517d96f2a0f3324b0c2d3.jpg)
# Monte Carlo Simulations and Confidence Intervals
- How small should a standard error be to make a trader confident on the price of the option?
 - The related concept of a $\left (95\%\right)$ confidence interval answers this question:
Confidence interval $=[\hat{c}_{0}-2\times\mathsf{S t}$ .Err.,  $\hat{c}_{0}+2\times\mathsf{S t}$ . Err.]
-There $95\%$ probability that the true value $c_{0}$ is between the upper and lower boundary of the confidence interval.
- In previous Table,  the upper and lower boundaries of the confidence interval are reported in the third and fourth rows,  respectively.
- The last row of the table reports the value of the option from the Binomial Tree itself.
- In all but one case,  the true price is within the confidence interval. - Is this surprising?
$\ast\textsf{N o}$ ,  because there is only $95\%$ chance that the true value lies within the confidence interval. $*~{\mathsf{I.e}}$ .for $5\%$ of the time,  the true value will not be within the confidence interval.
 - The confidence intervals in the Table are quite wide,  and so no trader would use them.
 - Raising the number of simulations reduces the spread in the confidence interval.
# Long-term Asian Options
- At this point,  we can estimate the values of a long-term Asian options with maturities $T_{i}=0.5,         …,          5$
- Next table computes the value (Panel A),  and the first 10 simulated discounted payoffs (Panel B)
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/5d172209b07fc6ed1ce8d7079ae2e638f3a6fac8d57e36ef6f010050d15b6792.jpg)
# Duration Calculations by Monte Carlo Simulations
- How can we compute measures of risk if we use Monte Carlo simulations for valuation? - We can use Monte Carlo simulations to compute the "spot rate" duration,  3 defined as
$$
\mathsf{S p o t\ r a t e\ d u r a t i o n}=-\frac{1}{P}\frac{d P}{d r}\approx-\frac{1}{\hat{P}(r_{0})}\frac{\hat{P}(r_{0}+d r)-\hat{P}(r_{0})}{d r}
$$  

That is,  compute the price starting from $r_{0}$ and from $r_{0}+d r$ . Then approximate the duration numerically

- Important: To avoid introducing simulation errors,  use the same realization s of the RAND () for the computation of the two prices
 ·Does itwork?
- Panel A of next Table contains the duration approximation for zero coupon bonds. It works pretty nicely - Panel B and C compute the durations for long-term options and Asian options discussed earlier. Note:
$^*$ First,  the duration of the interest rate call option is negative $^*$ Second,  the duration of Asian options is also negative and higher than the one of plain vanilla options. . This may be surprising,  as Asian options' underlying (the average of interest rates) is less volatile than the interest rate itself. . However,  the price of an Asian option is also smaller. Thus,  in percentage,  the sensitivity of the Asian option to changes in interest rates ishigher.
# Duration Calculations by Monte Carlo Simulations

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/3f66a8fa1307f3f4b8c7b91b70de0480d5e4df8b71834ca5bb970e9859d8f1d7.jpg)

# Monte Carlo Simulations in General
- The Monte Carlo simulation method is far more general than what I presented so far
 - For instance,  the Ho-Lee model also works with "continuous' shocks
$$
R_{t+\Delta{t}}=r_{t}+\theta_{t}\Delta{t}+\sigma\sqrt{\Delta{t}}\varepsilon_{t+\delta}
$$  

Where $\Delta t$ is a small interval of time,  and

$$
\varepsilon_{t+\Delta t}\sim N (0,         1)
$$  

More generally,  we can have

$$
R_{t+\Delta t}=r_{t}+\mu (r_{t})\Delta t+\sigma (r_{t})\sqrt{\Delta t}\varepsilon_{t+\delta}
$$  

For some function $\mu (r_{t})$ and $\sigma (r_{t})$

- Important: The functions $\mu (r_{t})$ and $\sigma (r_{t})$ must be estimated with securities data,  to obtain “risk neutral" (or risk adjusted) processes.
- The methodology is an extension of what we did to estimate $\theta_{i}$ with Ho-Lee model on trees - The price of a security with payoff $g (r_{T})$ at maturity $T$ ,  with a time interval $\Delta t=T/n$ ,  is
$$
Z (0,          T)\;\;=\;\; E^{*}\left[e^{-\sum_{j=0}^{n-1}r_{j}\Delta t}\times g (r_{T})\right]\approx\frac{1}{N}\sum_{s=1}^{N}\left[e^{-\sum_{j=0}^{n-1}r_{j}^{s}\Delta t}\times g (r_{T}^{s})\right]
$$  
# Teaching Note 6
# Mortgage Backed Securities t

# PanelA. Billionsof USDollars

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/44cd5f982f0a5c242a9275e360245bfcdc10ca4b35b8428607c1cf221c7d3c28.jpg)

Panel B. Percentage of US GDF

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/697487df73db1056c459378362e74b5bc9723900c0055407efb322bf9e488198.jpg)

(Source: SIFMA and FRED at Federal Reserve of St. Louis.)

# House Prices and the Mortgage Backed Securities Market

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/3d909ad043c5dc12f114c2f8adedb93a918b03d3f92f13ac8d9ff8a940271959.jpg)

Source: SIFMA and Standard & Poor/ Case-Shiller

# The Se curit iz ation Process

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/e0494099b8be2d5b0a7a222acd5f5ec3d7aecc1c8d56dfe0e156b68d2cddb99c.jpg)

# MBS Players

Three main government sponsored agencies exist

- FNMA (Federal National Mortgage Association,  or Fannie Mae): Used to be a publicly traded corporation,  but it was placed in conservator ship in September 2008. It provides secondary markets for mortgage loans from FHA (Federal Housing Administration) and VA (Veterans Administration). - GNMA (Government National Mortgage Association,  or Ginnie Mae): Government owned. GNMA guarantees loans in FHA and VA - FHLMC (Federal Home Loan Mortgage Corporation,  or Freddie Mac): Similarly to Fannie Mae,  it provides a link between mortgage lenders and capital markets. It buys from S&Ls,  mortgage bankers and commercial banks,  and sell mortgage pass-through securities.
- In addition,  other private labels also exist,  although in recent times they cover a small fraction of the total issuance,  because of credit risk
- There are some differences across the agencies on the type of mortgage pools they guarantee or buy/sell.
- The most common MBS is the Pass-Through MBS: all the cash flows from the original pool are passed to the investors. - Pass through MBSs have their own interest rate $r^{P T}$ ,  lower than the average mortgage rate in the pool as agencies keep a fee for arranging the MBS market (and provide default insurance)
# Mortgage Related Issuance

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/87e6a88185b3cc6aefb486d6b5680d4a696c1350aa546a0ddfcaf21c65b0230d.jpg)

Notes: Agency issuance includes GNMA,  FNMA,  and FHLMC mortgage backed securities and CMOs Nonagency issuance includes both private-label RMBS,  Res e curit iz ation,  and Home Equity Loans. Quantities are\$billions. Source: SIFMA. Government-Sponsored Enterprises,  Thomson Financial,  Bloomberg

# Mortgages and the Prepayment Option

 - It is important to review some basic facts about mortgages

 - Consider for instance a 30-year fixed-rate mortgage,  with mortgage rate of $\overline {{r}} _{12}^{m}$

 - Let $L$ be the amount of the mortgage lent from the bank to the homeowner.

 - According to the standard present value relation,  the periodic coupon $C$ must then satisfy

$$
L=\sum_{i=1}^{30\times 12}\frac{C}{\left (1+\frac{\bar{r}_{12}^{m}}{12}\right)^{i}}=\sum_{i=1}^{30\times 12}C\times A^{i}
$$  
-where
The coupon in (1) is then given by
$$
A=\frac{1}{1+\frac{\overline {{r}} _{12}^{m}}{12}}
$$  
$$
C=\frac{L}{\Sigma_{i=1}^{30\times 12}\,          A^{i}}
$$  
- The interest and the principal paid at any time $t$ are givenby:
$$
\begin{array}{c c}{\mathsf{I n t e r e s t\ p a i d\ a t\ t=\ }}&{\!\!\!\! I_{t}\!\!\!\!\!\!\!\!\!=\!\!\!\!\!\!\!\!\!\frac{\overline {{r}} _{12}^{m}}{12}\times L_{t}}\\ {\mathsf{P r i n c i p a l\ p a i d\ a t\ t=\}L_{t}^{p a i d}\!\!\!\!\!\!\!=\!\!\!\!\!\! C-I_{t}}\\ {\mathsf{P r i n c i p a l\ o u t s t a n d i n g\ a t\ t+1=}L_{t+1}\!\!\!\!\!\!}&{\!\!\!\!\!\!=\!\!\!\!\!\!\! L_{t}-L_{t}^{p a i d}}\end{array}
$$  
# Scheduled Principal Balance,  Scheduled Interest,  and Principal Payments

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/3d5f79821704b1a16c97fd3b879e4dc93577007e2e5ddc7bf9a421d25d26d0e0.jpg)

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/810bc18173b8d3c506c67769f22c220d87927c099707e132803a5219e293be1b.jpg)

# The Refinancing Option
- The value of the mortgage debt changes over time as mortgage rates change
$$
{\mathsf{V a l u e\ o f\ m o r t g a g e\ d e b t}}=P (t)=\sum_{i=1}^{n}{\frac{C}{(1+r_{12}^{m}(t,          T_{i})/12)^{i}}}
$$  
-where $n$ is the number of payments left at time $t$ and $r_{12}^{m}(t,          T_{i})$ are appropriate spot rates,  related to the current term structure of mortgage rates.
·Atevery $t$ ,  the homeowner can compare the amount of principal left to pay,  $L_{t}$ ,  with the market value of his liability to the bank $P (t)$
- As in any bond,  $P (t)$ increases in value whenever interest rates decline.
$-\implies$ when interest rates decline,  $P (t)$ may increases to a higher level than $L_{t}$ $-\implies$ optimal to refinance the mortgage.
# Refinancing and the Federal Funds Rate: 1990 - 2008

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/4c1b1d1caf8ddea4c64e1200ce9261e8994167328db067c34dbf07a3f2488191.jpg)

Source: Federal Reserve and Bloomberg.

# Mortgage Prepayments
- Interest rates declines are but one component of the prepayment,  albeit very important
Other reasons include the following
1. Seasonality: (Late) summers are characterized by larger prepayments,  because of the relocation seasonality.
1. Age of mortgage pool: Young (but not too young) mortgage pools tend to be refinanced more heavily.
1. Family circumstances: Defaults,  disasters,  or sale of the house
1. Housing prices: Higher prices makes it easier to refinance
1. Burnout effect: Mortgage pools heavily refinanced in the past tend to be insensitive to interest rates.
- If a mortgage pool has been heavily refinanced in the past,  most homeowners that could refinance alreadydid.
The only homeowners left in the pool are those who could not refinance
1. Media effect: The more newspaper talk about refinancing possibilities,  the more refinancing actuallyoccurs.
# Standard Measures of Prepayment Speed
- The industry developed some standard measures of prepayments,  mainly to have available one number to “characterize" the type of prepayment.
- Constant Maturity Mortality: It assumes a constant probability $p$ that the mortgage will be prepaid after the next coupon.
Pr (Prepayment at time $t=n$ months from now) = (1 - p)^ p
- The annualized rate,  the conditional prepayment rate (CPR) given by
- Thus,  the CPR is computed from $p$ as $C P R=1-\left (1-p\right)^{12}$
- PSA Experience The benchmark $100\%$ PSA (Public Securities Association),  makes the fol lowing assumptions:
1. $\mathsf{C P R}=0.2\%$ of the principal is paid in the first month; 2. CPR increases by $0.2\%$ in each of the following 30 months; and 3. CPR then levels off at $6\%$ until maturity. - This measure makes the amount of prepayment depend only on the age of the mortgage pool. - By scaling up or down the CPR in the PSA description,  we obtain faster or slower speeds of prepayments.
# PSA Prepayment Convention

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/1cb78096a6e7b0abc7cb766519800fc471e1e7acc08c3feca52f2f9e1d71ac6c.jpg)

# PSA and MBS Pricing
- A PSA prepayment speed is simply a quoting convention to allow traders to quote RMBS
- Indeed,  given a PSA speed defines the path for the monthly prepayment probability $p_{t}$
- Given the path $\{p_{t}\}$ ,  the MBS cash flows follow. Let $L_{t}$ be the outstanding principal,  then Mortgage interest payment:
Scheduled principal: Principal prepayment: Outstanding principal: Update of scheduled coupon:
$$
\begin{array}{r l}{\displaystyle I_{t}\ =\ \frac{\boldsymbol{r}_{12}^{m}}{12}\times L_{t}}&{}\\ {P a y_{t}^{s c h e d u l e d}\ =\ C_{t}-I_{t}}&{}\\ {P a y_{t}^{p r e p a i d}\ =\ p_{t}\times\left (L_{t}-P a y_{t}^{s c h e d u l e d}\right)}&{}\\ {\displaystyle L_{t+1}\ =\ L_{t}-P a y_{t}^{s c h e d u l e d}-P a y_{t}^{p r e p a i d}}&{}\\ {\displaystyle C_{t+1}\ =\ \left (1-p_{t}\right)\times C_{t}}&{}\end{array}
$$  
- Given the dynamics of $L_{t}$ implicit in PSA,  we can compute the path thourgh future cash flows:
Pass-through interest payment:
$$
\begin{array}{r l}&{I_{t}^{P T}\ =\ \displaystyle\frac{r_{12}^{P T}}{12}\times L_{t}}\\ &{C F_{t}\ =\ I_{t}^{P T}+P a y_{t}^{s c h e d u l e d}+P a y_{t}^{p r e p a i d}}\end{array}
$$  

 - The price of the pass-through MBS is then simply:

$$
{\cal P}^{M B S}(0,          T)=\sum_{t=1}^{T}~Z (0,          t)~C F_{t}
$$  
# The Negative Convexity of Mortgage Backed Securities
- When interest rates drop,  regular T-bonds increase in a convex manner.
- However,  if prepayment occurs,  then Mortgage Backed Securities will move towards principal =→negative convexity
Indeed,  MBS is equal to a portfolio with long bond and short call option - While long bond has positive convexity,  the short call has a strong negative convexity
  Negative convexity implies a negative loss on average
$$
T)\approx P^{M B S}(t,          T)+\frac{d P^{M B S}(t,          T)}{d r}(r (t+1)-r (t))+\frac{1}{2}\frac{d^{2}P^{M B}}{d r}
$$  
- Thus,  assuming over a short period $E\left[r (t+1)-r (t)\right]=0$ we have:
$$
\left.\frac{P^{M B S}(t+1,          T)-P^{M B S}(t,          T)}{P^{M B S}(t,          T)}\right]\approx\frac{1}{2}\;{\cal C}\; E\left[(r (t+1)-r (t))\right.
$$  

·Because $E\left[(r (t+1)-r (t))^{2}\right]>0$ ,  the negative convexity $C$ implies an average loss generated by the average variation in interest rates.

# The Value of a Pass-Through MBS with Respect to the Interest Rate

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/a91c4a0a16274b2466417c54a72740a78a1a9b2a1ce74c9d067048b73e35bdbf.jpg)

# The Convexity of MBS: GNMA 7 Prices and Mortgage Rates

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/87fdf8d7aed1a22e32670c20145244a79fe32a47a1b5b67772b45f20f81968c6.jpg)

Data source: Bloomberg and Federal Reserve Board

# Refinancing Speed and Rates: GNMA 7 PSA and Mortgage Rates

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/f8b52691d8e81152dfc18b827a3c8080051bf41bd404eecf9c6356cfaefafa4a.jpg)

Data source: Bloomberg and Federal Reserve Board

# A Higher Yield for MBS

A Sample of Par Value Ginnie Mae Pass-Through Prices and Treasury Yields

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/fd57400f883b970ee5cc0e6d800fbcdd4c0fbe36f78c2e251085708f2f243778.jpg)

WAC $=$ Weighted Average Coupon of underlying Pool; WAM $=$ Weighted Average Maturity of underlying Pool.

Source: Bloomberg andFederal Reserve Board.

- MBS securities pay a higher coupon than similar Treasury securities,  even if credit risk is the same - Ginnie Mae-issued RMBS have the full backing of the US government
# RMBS and Interest Rate Risk Management: Example
- Let today be June 8,  2007,  and assume we have invested $\$ 300$ million in the GNSF 6 pass-through - The underlying pool of this pass through has a WAC of $6.5\%$ and a WAM of 320 months. - The pass through has a $6\%$ coupon,  and it is quoted at bid/ask prices $=$ [99.4375 / 99.40625]
- We want to hedge the risk against an increase in interest rates. How do we compute duration and convexity?
- For instance,  simply using the same formulas as for bonds seems wrong. Indeed,  two simple formulas are
$$
\begin{array}{r}{D\ =\ -\frac{1}{P^{M B S}(0,          T)}\frac{d P^{M B S}(0,          T)}{d r}=\sum_{i=1}^{n}\ w_{i}\ T_{i};}\\ {C\ =\ \frac{1}{P^{M B S}(0,          T)}\frac{d^{2}P^{M B S}(0,          T)}{d r^{2}}=\sum_{i=1}^{n}\ w_{i}\ T_{i}^{2}}\end{array}
$$  

Where

$$
W_{i}=\frac{C F_{T_{i}}Z (0,          T_{i})}{P^{M B S}(0,          T)}
$$  

This calculation yields $D=4.39$ and $C=36.1590$ - Where is the negative convexity?

# RMBS and Interest Rate Risk Management: PSA-adjusted Effective Duration
- The earlier computations does not take into account that PSA speed,  and thus CFs,  change with the interest rate.
 - The PSA-adjusted Effective Duration corrects for this - How can we forecast the change in PSA speed for given interes rate? - SIFMA survey forecasts provide a simple way Mortgage Prepayment Projection Yield Curve Scenarios
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/4efac770a73e96d16361bd138fe24ba2973788b7e9ff393e9360d9b73d3fe712.jpg)
# RMBS and IRRM: PSA-adjusted Effective Duration and Convexity
- We can use these projections to adjust the cash flows.
 - Using for instance a 50 bps increase / decrease,  we obtain
D $\frac{-1}{P}\frac{P (+50 b p s)-P (-50 b p s)}{2\times 50 b p s}=-\frac{1}{99.43}\frac{96.79-101.43}{2\times 50 b p s}=}\\ {\frac{1}{P}\frac{P (+50 b p s)+P (-50 b p s)-2\times P}{(50 b p s)^{2}}=\frac{1}{99.43}\frac{96.79+101}{(50.698)^{3}}}\end{array}$ 4.68 0.\1 - 2 × 99.43 C -251.08 0 bps) 2
Using instead a 1 o 0 bps increase / decrease,  we obtair
$$
\frac{-\frac{1}{P}\frac{P (+100 b p s)-P (-100 b p s)}{2\times 100 b p s}=-\frac{1}{99.43}\frac{94.00-102.24}{2\times 100 b p s}}{1}
$$  
- These numbers for convexity are much more in line with the intuition that cash flows increase when interest rate decline,  because of the prepayment option.
# RMBS and IRRM: Empirical Duration and Convexity
- A third methodology is to use past data to inform about the sensitivity of MBS to changes to interest rates.
- This methodology can be particularly useful as we can check the relation between MBS prices and the relevant interest rate for hedging. - Indeed,  given the liquidity of the OTC swap market,  interest rate swaps are typically the preferred derivative instrument to hedge against changes in interest rates
- Next figures shows the relation between GNMA prices,  and the 5-year swap rate
- Using these data,  and denoting $c_{t}(5)$ the 5-year swap rate at $t$ ,  we can also estimate a (simple) polynomial regression
$$
P_{t}=\alpha+\sum_{i=1}^{4}\beta_{i}\times c_{t}(5)^{i}+\epsilon_{t}
$$  
- Given the estimates,  we can easily compute $d P/d r$ and $d^{2}P/d r^{2}$ ,  obtaining then
$$
\begin{array}{l}{\mathsf{E m p i r i c a l\Delta D u r a t i o n\;=\;-}\displaystyle\frac{1}{P}\frac{d\; P}{d\; c (5)}=\frac{444.66}{99.4219}=4.4725}\\ {\mathsf{E m p i r i c a l\Delta C o n v e x i t y\;=\;}\displaystyle\frac{1}{P}\frac{d^{2}\; P}{d\; c (5)^{2}}=\frac{-14731.4}{99.4219}=-148.17}\end{array}
$$  

·Given $D$ and $C$ ,  hedging can then be achieved using the same methodologies as before.

# GNSF 6 Price and the 5-Year Swap Rate

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/8d1dbb3733efd555e78d4769d3f1439b055923faf3c81d117fe668a1078fca40.jpg)

# Pricing Prepayment Option on Binomial Trees

Mortgages have an implicit American option. We can use Binomial Trees to evaluate its fair value.

 - This is the first step to compute the fair value of Mortgage Backed Securities using no-arbitrage methods

- Example: consider the simple case with annual rather than monthly payments Suppose that interest rate tree is the following:
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/17e7c3a4b8ca5ebc171366ef7f11ed78b143191b59151102e8ba4ab45c309ad2.jpg)
- Consider a 10,  000 mortgage with 4 years to maturity,  and mortgage rate $\overline{r}^{m}=0372$ (annually compounded).
- We need to compute the principal amounts left after each coupon payment
 -What is the annual coupon?
- Need to solve
$$
10,         000=\sum_{i=1}^{4}\frac{C}{(1+\overline {{r^{m}} })^{i}}
$$  
- This yields $C=2736.7581$
- We then obtain
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/8fb7cd345c6b14ffcb701bd93b7833b8bc2848256f570c3ff38bd425eb2d59e9.jpg)
- We now need to compute the value of the American option implicit in the mortgage
- At every payment date,  we must compare the net present value of future mortgage payments with the principal remaining.
-- Refinancing occurs when the NPV of future payments is above principal
- So,  first we compute the NPV of future payments
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/1b00c97890ffa00c8331245fdd810e1c65b0659303c574faf74bb21d3139ea4d.jpg)
- The net present value of future mortgage payments is 10075.5089.
  Notice that the bank has only given them \$10000.
 - However,  the bank is selling an American call to the home-owner,  which is valued in the next tree
 - (For the sake of simplicity,  denote by $(a,          b)^{+}=\operatorname*{max}(a,          b))$ - From the tree,  we see that the value of the mortgage is fair:
$\mathsf{M o r t g a g e}=10000=\mathsf{N P V}(\mathsf{F u t u r e\ C F s})$ - Prepayment Cal
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/1b1b336246ae6a2a7dcb2caebf28641696cb3190918d9c66a294cd826deccd32.jpg)
# Pricing Pass Through's on Binomial Trees

We now look at how to value PT securities on a binomial tree

- The main difference between valuing a PT security and valuing the mortgage in the previous example is that the PT security has a lower interest rate than the coupon rate.
- The lower coupon paid by the issuer of the PT security to investors compared to the average mortgage coupon rate (WAC) is due in part as a compensation for holding default risk and in partas a service fee.
- The following is the same example as earlier,  but now we compute the value of a PT security with couponrate $r_{P T}=2\%$
- In the original tree,  exercise only occurs at the nodes $(1,          d),          (2,          d d),          (3,          d d d).$ - At these nodes,  the value of the PT security simply equals the outstanding principal
- Given these cash flows,  the computation of the value of the PT security proceeds exactly as any other fixed income security
- As a sanity check,  note that if we use $r_{P T}=. 0372$ ,  we indeed obtain $V_{0}^{P T}=10000$
$$
\begin{array}{l l}{i=0}\\ {\mathsf{P r i n c i p a l}=10000}\end{array}
$$  

$i=1$ Principal $=7635.263$ Interest $=10000\times r_{P T}$ Sched. $\mathsf{P r i n}=2364.737$ $i=2$ Principal $=5182.553$ Interest $=7635.263\times r_{P T}$ Sched. $\mathsf{P r i n}=2452.710$

$i=3$ Principal $=2638.597$ Interest $=5182.553\times r_{P T}$ Sched. $\mathsf{P r i n}=2543.956$

$i=4$ Principal $=0$ Interest $=2638.597\times r_{P T}$ Sched. $\mathsf{P r i n}=2638.597$

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/a8a2ca61db67e8eff1c104e0ad48d27b98f016b41e8b921cb7aae150fb0b4b5b.jpg)

# Pricing Pass Through's on Binomial Trees

On a “bigger tree",  consider a 5-year mortgage with $N=