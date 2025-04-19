---
tags:
  - arbitrage
  - cash_flow_engineering
  - conclusions
  - exercises
  - financial_engineering
  - instrument_characteristics
  - market_conventions
  - market_structure
  - suggested_reading
aliases:
  - Basic Information
  - Chapter 2.9
  - Financial Engineering Student
key_concepts:
  - arbitrage position benefit news
  - borrow funds position
  - cash flow engineering
  - centrally bilaterally cleared derivatives
  - collateral requirements futures OTC
  - deposit funds take position
  - difference initial variation margin
  - financial engineering student
  - instrument characteristics change
  - market conventions, markets, players
  - open interest refer to
  - profits prop dealers affected
  - proprietary dealer buys contract
  - proprietary dealers betting Euribor
  - review basic information
  - risks taking
  - show positions proprietary dealers
  - strategy Euribor higher LIBOR
  - true arbitrage academic sense
  - underlying instruments, markets, conventions
---

# 2.9 CONCLUSIONS  

This chapter reviewed some basic information the reader is assumed to have been exposed to. The discussion provided here is sketchy and cannot be a substitute for a thorough course on conventions, markets, and players. Also, market conventions, market structure, and the instrument characteristics may change over time.  

# SUGGESTED READING  

It is important for a financial engineering student to know the underlying instruments, markets, and conventions well. This chapter provided only a very brief review of these issues. Fortunately, several excellent texts cover these further. Hull (2014) and Wilmott (2006) are first to come to mind. Market-oriented approaches to instruments, pricing, and some elementary financial market strategies can be found in Steiner (2012) and Roth (1996). These two sources are recommended as background material.  

# EXERCISES  

1. What is the difference between initial and variation margin?   
2. How do collateral requirements differ between futures and OTC derivative markets.   
3. What are the differences between centrally and bilaterally cleared derivatives?   
4. What does open interest refer to?   
5. Suppose the following stock prices for GE and Honeywell were observed before any talk o merger between the two institutions: Honeywell (HON) 27.80 General Electric (GE) 53.98  

Also, suppose you "know" somehow that GE will offer 1.055 GE shares for each Honeywell share during any merger talks.  

a. What type of "arbitrage' position would you take to benefit from this news? b. Do you need to deposit any of your funds to take this position?.   
c. Do you need to and can you borrow funds for this position?.   
d. Is this a true arbitrage in the academic sense of the word?.   
e. What (if any) risks are you taking?.  

6. Read the market example below and answer the following questions that relate to it.  

Proprietary dealers are betting that Euribor, the proposed continental European-based. euro money market rate, will fix above the Euro BBA LIBOR alternative... The arbitrage. itself is relatively straightforward. The proprietary dealer buys the Liffe September 1999 Euromark contract and sells the Matif September 1999 Pibor contract at roughly net zero. cost. As the Liffe contract will be referenced to Euro BBA LIBOR and the Matif contract will be indexed to Euribor, the trader in effect receives Euribor and pays Euro BBA LIBOR..  

The strategy is based on the view that Euribor will generally set higher than Euro BBA LIBOR. Proprietary dealers last week argued that Euribor would be based on quotes from 57 different banks, some of which, they claimed, would have lower credit ratings than the eight LIBOR banks. In contrast, Euro BBA LIBOR will be calculated from quotes from just 16 institutions. (From Thomson Reuters IFR, December 18, 1998)  

a. Show the positions of the proprietary dealers using position diagrams..   
b. In particular, what is on the horizontal axis of these diagrams? What is on the vertical. axis?   
c. How would the profits of the "prop' dealers be affected at expiration, if in the meantime there was a dramatic lowering of all European interest rates due, say, to a sudden recession?  

# CASH FLOW ENGINEERING INTEREST RATE FORWARDS AND FUTURES  

# 3  

# SHAPTER OUTLINE  

3.1 Introduction. 54   
3.2 What Is a Synthetic?. 55   
3.2.1 Cash Flows 55   
3.2.1.1 Cash flows in different currencies 57   
3.2.1.2 Cash flows with different market risks 58   
3.2.1.3 Cash flows with different credit risks .58   
3.2.1.4 Cash flows with different volatilities .. 58   
1.3 Engineering Simple Interest Rate Derivatives. 59   
3.3.1 A Convergence Trade.. 60   
3.3.2 Yield Curve . 61   
3.4 LIBOR and Other Benchmarks. 63   
3.5 Fixed Income Market Conventions. 64   
3.5.1 How to Quote Yields.. 65   
3.5.2 Day-Count Conventions .. 67   
3.5.2.1 Holiday conventions . .68   
3.5.3 Two Examples. 69   
3.6 A Contractual Equation . 70   
3.6.1 Forward Loan . 71   
3.6.2 Replication of a Forward Loan ... 72   
3.6.2.1 Bond market replication . .73   
3.6.2.2 Pricing. 74   
3.6.2.3 Arbitrage.... ..74   
3.6.2.4 Money market replication. .75   
3.6.2.5 Pricing. 75   
3.6.3 Contractual Equations.... .76   
3.6.4 Applications. 77   
3.6.4.1 Application 1: creating a synthetic bond. 77   
3.6.4.2 Application 2: covering a mismatch .78   
7 Forward Rate Agreements ... 79  

3.7.1 Eliminating the Credit Risk 8C  

3.7.2 Definition of the FRA 81   
3.7.2.1 An interpretation. 82   
3.7.3 FRA Contractual Equation. 82   
3.7.3.1 Application: FRA strips. 82   
3.8 Fixed Income Risk Measures: Duration, Convexity and Value-at-Risk... 83   
3.8.1 DVO1 and PVO1 84   
3.8.1.1 Dollar duration Dv01 84   
3.8.1.2 PV01.. .85   
3.8.2 Duration . 85   
3.8.3 Convexity 87   
3.8.4 Immunization. 87   
3.8.5 Value-at-Risk, Expected Shortfall, Basel Capital Requirements and Funding Costs ... . 88   
3.9 Futures: Eurocurrency Contracts. 89   
3.9.1 Other Parameters .. 91   
3.9.1.1 The "TED spread" 92   
3.9.2 Comparing FRAs and Eurodollar Futures. 93   
3.9.2.1 Convexity differences.. 93   
3.9.3 Hedging FRAs with Eurocurrency Futures 93   
3.9.3.1 Some technical points . 94   
.10 Real-World Complications . 95   
3.10.1 Bid-Ask Spreads. 95   
3.10.2 An Asymmetry. 96   
3.11 Forward Rates and Term Structure. 96   
3.11.1 Bond Prices.. 96   
3.11.2 What Forward Rates Imply. 97   
3.11.2.1 Remark... .97   
.12 Conventions.. 98   
1.13 A Digression: Strips... 99   
.14 Conclusions. 99   
Suggested Reading - . 100   
ppendix--Calculating the Yield Curve .... 100   
Par Yield Curve... 101   
Zero-Coupon Yield Curve .. 101   
Zero-Coupon Curve from Coupon Bonds. 102   
Exercises . . 103  
