---
cssclasses:
  - academia
linter-yaml-title-alias: PSET 6-Financial Instruments
title: PSET 6-Financial Instruments
tags:
  - financial_instruments
  - implied_volatility
  - morgan_stanley
  - options_data
  - structured_security
aliases:
  - Homework 6
  - PLUS Security
  - PSET 6
key_concepts:
  - Implied Volatility Calculation
  - PLUS Security Decomposition
  - Risk Factors
  - S&P 500 Options Data
  - Structured Security Valuation
---

# PSET 6-Financial Instruments

ma# PSET 6FINANCIAL INSTRUMENTS

## FINANCIAL INSTRUMENTS WINTER 2024 JOHN HEATON

Homework 6

Due at the beginning of class 8

Roger Lin

Suna Bai

## 1 IMPLIED VOLATILITY

Replicate the Implied Volatility of Teaching Note 6,  using current options data on S&P 500 maturing in June (3 months or one quarter from now). Please state the assumptions you make,  if any,  to compute the time to maturity of the options,  that is the value of T that you use in your formulas. (No need to use many options. Choose just a few ITM,  OTM and ATM. Note that the current SP 500 index value is on the top right corner of the table.) The spreadsheet "Options. Xls" provides an example of the implied volatility calculation. See the worksheet "Implied Volatility."

ˆ Current Options Data can be found at CBOE. The ticker is SPX.

http://www.cboe.com/DelayedQuote/QuoteTable.aspx

NOTE: I have downloaded all of this data for you! Please see the file "Quote-Data 2024. Xls."

ˆ You can use federal reserve website (link below) to retrieve the value of the risk Free rate. Use the Treasury Constant Maturity rate that most closely matches the Maturity of the options. Note that TCM are compounded annually,  so be sure to Make the relevant adjustments. Please report the value of the rate that you use. http://www.federalreserve.gov/releases/h15/Current/

ˆ The dividend yield can be estimated using the data collected by Robert Shiller which are available at the link below. You can estimate the dividend yield as the average dividend yield over the last available 12 months. Be sure to make the relevant compounding adjustments and report the dividend yield that you use.

http://www.econ.yale.edu/~shiller/data.htm You should use the data in the "Excel file" used in his book. This gives monthly prices,  dividends,  earnings and other information.

> [!NOTE]
> Risk free rate: Interest rate on 3 month Treasury constant maturities as of 12 February,  2024 = 0.0543,  annually compounded
> - We chose this Treasury because it's maturity closely matches the maturity of the options expiring on June 21 and June 28,  2024.
> - The risk-free rate,  continuously compounded,  is$$e^{r=}1.0543$$
> - $$r=\ln(1.0543)=0.05288$$Average monthly dividend yield on SP 500 from Feb 28,  2023 to Jan 31,  2024 is 0.01621075
> 	- The continuously compounded dividend yield = 0.01608
>

 ![500](03bc29ba4ac59fbc321f2f432023249d.png)

> | |
> |---|---|
> |Assumptions| |
> |Start Date|Feb 12th,  2024|
> |Maturity Date|June 21st,  2024|
> |Days to Expiration|130|
> |Risk Free Rate|5.29% (3 Month Treausry Rate as of Feb,  12th,  2024)|
> |Dividend Yield|1.608% (average dividend yield on SPX over 2023.)|
> |Strike Price|5020|
> |Price of Underlying|5021.84|
> |ITM Call Premium|190.75|
> |IV on ITM Call Option|16.18%|
> |ITM Put Premium|120.5|
> |IV on ITM Put Option|10.35%|

 ![500]/ea19896c234fab61d22703aa002e42dc.png)

## 2 VALUING AND ANALYZING A STRUCTURED SECURITY

- (1) A wealthy investor hires you to help her evaluate a recent security issued by Morgan Stanley,  called PLUS (see prospectus: The security was issued by Morgan Stanely in April 2008. Assume the same security is issued today and has one-year to Maturity,  but it is otherwise identical). To assess its fair value,  you decide to use the appropriate implied volatility from the options markets as in Exercise (1).
	- (a) How can you decompose the PLUS into more basic securities? (Tip: The Solution to the Mock Midterm might be helpful…)

| Start Date | Feb 12th,    2024 |
| ---- | ---- |
| Maturity Date | Feb 12th,    2025 |
| T | 1 |
| Risk Free Rate | 4.87% (1 yearconstant maturity  Treausry Rate as of Feb,    12th,    2024) |
| Dividend Yield | 1.608% (average dividend yield on SPX over 2023.) |
| Implied Volatility | 16.18% |

| Stock Index Price | B0 | normalized index price |
| ---- | ---- | ---- |
| 1329.51 | 0.00752 | 9.997915 |
| 1417 | 0.00752 | 10.65584 |

> [!NOTE]
> - We can decompose the PLUS security into
> 	- a zero coupon bond with face value of 10
> 			-$$B_{Z}= 10 e^{-0.0487*1}$$
> 	- 3 Long At the Money Call Options with Strike Price of 10
> 	- 3 Short Out of the Money Call Options with Strike of 10.65584
> 	- 1 Short At the Money Put Option with Strike Price of 10

- (b) Use the decomposition obtained in point (2.1. A) and the information obtained In exercise (1) to value the PLUS.

> [!NOTE]
> - a zero coupon bond with face value of 10$$B_{Z}= 10 e^{-0.0487*1}=9.52467$$
> 	- 3 Long At the Money Call Options with Strike Price of 10
$$\text{BSCall}(S,   K,   \sigma,   r,   T,   \delta)$$
> $$3 \times \text{BSCall}(10,   10,   16.18\%,   4.87\%,   1.60\%) \approx 0.8 \times 3 = 2.4$$3 Short Out of the Money Call Options with Strike of 10.65584$$3 \times \text{BSCall}(10.65,   10,   16.18\%4.87\%,    1.608\%) \approx -0.17975 \times 3 = -0.539251$$- 2 Short At the Money Put Option with Strike Price of 10
> - $$BSPUT(10,   10,   16.18\%,    4.87\%,    1.60\%)=-0.48$$
> - Total Value of Replicating Portfolio = 9.52467+2.4-0.539-0.48=10.899032
>

 ![500]/6c4e3667220d343e13994175049a7193.jpg)

 ![500]/c07b3c05093e1981d064faaca657d2eb.png)

- (c) If the value you obtain is not at par,  what might you modify to make sure the value of the security is par as of today? (Words only,  but for a bonus,  see if you can actually set the value to par by changing one of the terms.)

> [!NOTE]
> I would change the cap on the maximum return. since this would affect the out of the money call option's value. We cannot change the risk free rate,  volatility,  dividend yield,  or stock price,  so our best option is to change the strike price on the out of the money call option which forms the cap of the maximum returns we can earn.

- (2) What is the sensitivity of this security to changes in the underlying stock price? How can you compute its market "beta",  namely,  the **percentage** sensitivity of the security to **percentage** changes in the underlying? Compute the "beta" of the PLUS for several stock prices "S" as of
	- Option elasticity is computed by the percentage change in the option price relative to the percentage change in the stock price. The percentage change in the stock price is change in stock price,  dS divided by$S$. The percentage change in the options price is given by the dollar change in the price of the option,  divided by the option price,  $C$,  or$\frac{dS*\Delta}{C}$The option elasticity is then the percentage change in option price over the percentage change in stock price,  which simplifes to$\frac{S\Delta}{C}$
	- ([](f3fc6795259bcbb5a42f30795567bf23.png)
	- (b) m now,
	-  ![500](attachment/a8921e8205d813706483563730cd7f9b.png)
	- (c) 1 year from now. Discuss your findings.
		- As the PLUS note approaches maturity,  the beta increases,  meaning that it becomes more sensitive to changes in the price of the underlying stock
 ![500](aa4d12a40d58406aa012877a83a05b9a.png)

|   |   |   |   |
|---|---|---|---|
|maturity|1/365|6 months|1 year|
|Value of zero coupon bond|9.99864731|9.7594407|9.52466827|
|ATM Call(K0=10)|0.03447201|0.53365626|0.79484313|
|N(d1)|0.5059398|0.57916686|0.61122258|
|N(d2)|0.50253798|0.5340095|0.54803841|
|||||
|OTM Call (K1=11.9)|-4.831E-95|-0.0472135|-0.1797505|
|N(d1)|1.1608E-92|0.09330454|0.21400364|
|N(d2)|9.7511E-93|0.07563117|0.16993903|
|||||
|ATM Put(K0=10)|-0.0335647|-0.3702476|-0.4709137|
|N(d1)|0.49746202|0.4659905|0.45196159|
|N(d2)|0.49746202|0.4659905|0.45196159|
|||||
|dV/dS|0.01519207|0.0147959|0.01272506|
|β|2.00605971|1.81327046|1.55225645|

## STRUCTURED INVESTMENTS OPPORTUNITIES IN EQUITIES PLUS BASED ON THE VALUE OF THE S&P 500® INDEX DUE APRIL 20,  2009 PERFORMANCE LEVERAGED UPSIDE SECURITIES

The PLUS are senior unsecured obligations of Morgan Stanley,  will pay no interest,  do not guarantee any return of principal at maturity and have the terms described in the prospectus supplement for PLUS and the prospectus,  as supplemented or modified by this pricing supplement. A

| Term | Details |
| ---- | ---- |
| Issuer | Morgan Stanley |
| Maturity date | April 20,    2009 |
| Underlying index | S&P 500® Index |
| Aggregate principal amount |$47,   500,   000 |
| Payment at maturity | If final index value is greater than initial index value,   $10 + leveraged upside payment. In no event will the payment at maturity exceed the maximum payment at maturity. If final index value is less than or equal to initial index value,   $10 x (final index value / initial index value) This amount will be less than or equal to the stated principal amount of$10. |
| Leveraged upside payment |$10 x leverage factor x index percent increase |
| Index percent increase | (final index value – initial index value) / initial index value |
| Initial index value | 1,   329.51,    the index closing value of the underlying index on the pricing date |
| Final index value | The index closing value of the underlying index on the valuation date |
| Valuation date | April 16,    2009,    subject to adjustment for certain market disruption events |
| Leverage factor | 300% |
| Maximum payment at maturity |$11.90 (119% of the stated principal amount) per PLUS |
| Stated principal amount |$10 per PLUS |
| Issue price |$10 per PLUS (see “Commissions and Issue Price” below) |
| Pricing date | March 20,    2008 |
| Original issue date | March 31,    2008 |
| CUSIP | 61747W166 |
| Listing | The PLUS have been approved for listing on the American Stock Exchange LLC under the ticker symbol “SKE,  ” subject to official notice of issuance. It is not possible to predict whether any secondary market for the PLUS will develop. |
| Agent | Morgan Stanley & Co. Incorporated |

| Commissions and Issue Price: | Price to Public | Agent’s Commissions | Proceeds to Company |
|------------------------------|-----------------|---------------------|---------------------|
| Per PLUS                     |$10             |$0.15               |$9.85               |
| Total                        |$47,   500,   000     |$712,   500            |$46,   787,   500         |

(1) The actual price to public and agent's commissions for a particular investor may be reduced for volume purchase discounts depending on the aggregate amount of PLUS purchased by that investor. The lowest price payable by an investor is$9.95 per PLUS. Please see "Syndicate Information" on page 4 for further details.

(2) For additional information,  see "Plan of Distribution" in the accompanying prospectus supplement for PLUS.

The PLUS involve risks not associated with an investment in ordinary debt securities. See "Risk Factors" beginning on page 7.

The Securities and Exchange Commission and state securities regulators have not approved or disapproved these securities,  or determined if this pricing supplement or the accompanying prospectus supplement and prospectus is truthful or complete. Any representation to the contrary is a criminal offense.

YOU SHOULD READ THIS DOCUMENT TOGETHER WITH THE RELATED PROSPECTUS SUPPLEMENT AND PROSPECTUS,  EACH OF WHICH CAN BE ACCESSED VIA THE HYPERLINKS BELOW.

Amendment No. 2 to Prospectus Supplement for PLUS dated October 24,  2007

Prospectus dated January 25,  2006
