---
tags:
  - ester
  - interest_rates
  - libor
  - overnight_rates
  - reference_rates
  - saron
  - sofr
  - sonia
  - tonar
aliases:
  - ESTER
  - London Interbank Offered Rate
  - SARON
  - SOFR
  - SONIA
  - TONAR
key_concepts:
  - LIBOR reference rate
  - SOFR overnight rate
  - new reference rates
  - reference interest rates
  - unsecured borrowing rates
---

# 4.2 REFERENCE RATES  

Reference interest rates are important in financial markets. The parties to transactions. frequently enter into contracts where the future interest rate paid or received is uncertain, but will be set equal the value of an agreed reference interest rate..  

# LIBOR  

LIBOR is short for London Interbank Offered Rate. It has historically been a very. important reference rate. LIBOR rates have been compiled by asking a panel of global banks to provide quotes estimating the unsecured rates of interest at which they could borrow from other banks just prior to 11 a.m. (U.K. time). Several different currencies and several different borrowing periods (ranging from one day to one year) were. considered. The banks submitting quotes typically had good credit ratings. LIBOR rates were therefore considered to be estimates of unsecured borrowing rates for creditworthy banks.  

LIBOR rates have served as reference rates for hundreds of trillions of dollars of transactions throughout the world. For example, the borrowing rate on a five-year loan in a particular situation might be specified as three-month LIBOR plus 30 basis points (i.e., three-month LIBOR plus. $0.3\%$ ). The value of three-month LIBOR would then be. noted at the beginning of each three-month period and interest based on this LIBOR rate would be paid by the borrower at the end of the period..  

A problem with LIBOR is that there is not enough borrowing between banks for a. bank's estimates to be determined by market transactions. As a result, LIBOR submissions by banks involved a certain amount of judgment and could be subject to manipulation. Bank regulators are uncomfortable with this and have developed plans to phase out the use of LIBOR. Originally, the deadline for LIBOR to be discontinued was the end of 2021, but quotes may continue for a period after that to make it easier. to deal with the existing contracts that depend on LIBOR..  

# The New Reference Rates  

The plan is to base reference rates on the overnight rates we have mentioned. For example, the new reference rate in the United States will be SOFR; in the U.K., it will be SONIA; in the eurozone, it will be ESTER; in Switzerland, it will be SARON; in Japan, it will be TONAR. (Note that the overnight rate in the U.S. will be a secured. overnight rate because it is a repo rate; the overnight rate in other countries will be unsecured because, as explained earlier, they are determined from the overnight transactions between banks when they manage reserves.).  

Longer rates such as three-month rates, six-month rates, or one-year rates can be determined from overnight rates by compounding them daily. In the case of SOFR, there are assumed to be 360 days per year. (See Chapter 6 for a discussion of day count conventions) Suppose that the (annualized) SOFR overnight rate on the ith business day of a period is $r_{i}$ $1\leq i\leq n$ ) and the rate applies to $d_{i}$ days. The (annualized) interest rate for the period is.  

$$
[(1+r_{1}\hat{d}_{1})(1+r_{2}\hat{d}_{2})\dots(1+r_{n}\hat{d}_{n})-1]\times\frac{360}{D}
$$  

where $\hat{d}_{i}=d_{i}/360$ and $D=\sum_{i}d_{i}$ is the number of days in the period. On most days. $d_{i}=1$ , but weekends and holidays lead to the overnight rates being applied to more than one day. (For example, on a Friday. $d_{i}$ will normally be equal to 3.).  

The new reference rates are regarded as risk-free because they are derived from oneday loans to creditworthy financial institutions. LIBOR, by contrast, incorporates a credit spread. There is another important difference between the old and new reference rates. LIBOR rates are forward looking. They are determined at the beginning of the period to which they will apply. The new reference rates are backward looking. The rate applicable to a particular period is not known until the end of the period when all the relevant overnight rates have been observed.  

As we will discuss in Chapter 7, swaps are a way in which short-term interest rates can be used to determine the equivalent interest rates that apply to relatively long periods.  

# Reference Rates and Credit Risk  

One problem faced by banks is that credit spreads in the economy increase in stressed market conditions. For example, the spread between three-month LIBOR and a threemonth rate based on overnight rates is usually about 10 basis points $(0.1\%)$ , but it can be much higher in stressed market conditions. For example, it spiked to an all-time high of 364 basis points. $(3.64\%)$ in the United States in October 2008 during the financial crisis. If a bank offers a loan at a reference rate plus. $x\%$ , where $x$ is a constant, it would like the rate to reflect ups and downs in average credit spreads. LIBOR, when used as a reference rate, did this, but the new reference rates (because they are essentially risk-free) do not. This has led banks to ask for a way of creating risky. reference rates by adding a credit spread to the new reference rates. There have been a number of proposals and the new risk-free reference rates may be augmented by credit spread measures in the future..  
