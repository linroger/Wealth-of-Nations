---
tags:
  - derivatives_mishaps
  - financial_institutions
  - hedge_funds
  - liquidity_crisis
  - nonfinancial_corporations
  - option_pricing
  - systemic_risk
  - yield_curve
aliases:
  - Derivatives Failures
  - Derivatives Lessons
  - Mishaps Analysis
key_concepts:
  - Derivatives use and pricing
  - Financial institution losses
  - Hedge fund losses
  - Lehman bankruptcy
  - Lessons for derivatives users
  - Liquidity and crisis
  - Nonfinancial org losses
  - Put-call parity
  - Systemic risk
  - Yield curve plays
---

# Chapter 37. Derivatives mishaps and what we can learn from them . .. 793  

37.1 Lessons for all users of derivatives .793   
37.2 Lessons for financial institutions .797   
37.3 Lessons for nonfinancial corporations ..802   
Summary .804   
Further reading ..804   
Glossary of terms .805   
DerivaGem software ... .829   
Exchanges. trading futures and options ..... ..834   
Tables for $N(x)$ ...835   
Author index . ..837   
Subeect indeex .... .841   
1.1 The Lehman Bankruptcy 4   
1.2 Systemic Risk 5   
1.3 Hedge Funds 12   
1.4 SocGen's Big Loss in 2008 .. .18   
2.1 The Unanticipated Delivery of a Futures Contract . 25   
2.2 Long-Term Capital Management's Big Loss .34   
3.1 Hedging by Gold Mining Companies .53   
3.2 Metallgesellschaft: Hedging Gone Awry .69   
4.1 Orange County's Yield Curve Plays .. ..89   
4.2  Liquidity and the 2007-2009 Financial Crisis .97   
5.1 Kidder Peabody's Embarrassing Mistake .107   
5.2 A Systems Error? .. .112   
5.3 The CME Nikkei 225 Futures Contract. .114   
5.4 Index Arbitrage in October 1987 .115   
6.1 Day Counts Can Be Deceptive .131   
6.2 The Wild Card Play .. ..137   
6.3 Asset-Liability Management by Banks . ..145   
7.1 Extract from Hypothetical Swap Confirmation. .158   
7.2 The Hammersmith and Fulham Story .172   
8.1 The Basel Committee .. .190   
10.1 Tax Planning Using Options ... .219   
11.1 Put-Call Parity and Capital Structure .236   
12.1 Losing Money with Box Spreads 255   
12.2 How to Make Money from Trading Straddles ..260   
15.1 Mutual Fund Returns Can be Misleading ..321   
15.2 What Causes Volatility? . ..324   
15.3 Warrants, Employee Stock Options, and Dilution ..335   
17.1 Can We Guarantee that Stocks Will Beat Bonds in the Long Run? ..371   
19.1 Dynamic Hedging in Practice .416   
19.2 Was Portfolio Insurance to Blame for the 1987 Crash?. .422   
20.1  Making Money from Foreign Currency Options. .433   
20.2 Crashophobia ..... .436   
21.1 Calculating Pi with Monte Carlo Simulation .467   
21.2  Checking Black-Scholes-Merton in Excel .470   
22.1 How Bank Regulators Use VaR .493   
24.1 Downgrade Triggers and AIG .553   
25.1 Who Bears the Credit Risk? ... .566   
25.2 The CDS Market . .568   
26.1 Is Delta Hedging Easier or More Difficult for Exotics? .611   
29.1 Put-Call Parity for Caps and Floors . .673   
29.2 Swaptions and Bond Options ... .678   
30.1 Siegel's Paradox .692   
33.1 IOs and POs . .747   
34.1 Hypothetical Confirmation for Nonstandard Swap .752   
34.2 Hypothetical Confirmation for Compounding Swap .753   
34.3 Hypothetical Confirmation for an Equity Swap . .756   
34.4 Procter and Gamble's Bizarre Deal . .760   
36.1 Valuing Amazon.com . .785   
37.1 Big Losses by Financial Institutions .794   
37.2 Big Losses by Nonfinancial Organizations. .. .795  

![](69c47875ab0fcec2401cb93139cbf6cea3bf5a7d30901d8be65d77cc76ecdb9b.jpg)  

# Introduction  

In the last 40 years, derivatives have become increasingly important in finance. Futures. and options are actively traded on many exchanges throughout the world. Many different types of forward contracts, swaps, options, and other derivatives are entered. into by financial institutions, fund managers, and corporate treasurers in the over-the-. counter market. Derivatives are added to bond issues, used in executive compensation plans, embedded in capital investment opportunities, used to transfer risks in mortgages from the original lenders to investors, and so on. We have now reached the stage where those who work in finance, and many who work outside finance, need to understand how derivatives work, how they are used, and how they are priced..  

Whether you love derivatives or hate them, you cannot ignore them! The derivatives market is huge-much bigger than the stock market when measured in terms of underlying assets. The value of the assets underlying outstanding derivatives transactions is several times the world gross domestic product. As we shall see in this chapter, derivatives can be used for hedging or speculation or arbitrage. They can transfer a wide range of risks in the economy from one entity to another.  

A derivative involves two parties agreeing to a future tranasaction. Its value depends. on (or derives from) the values of other underlying variables. Very often the variables underlying derivatives are the prices of traded assets. A stock option, for example, is a derivative whose value is dependent on the price of a stock. However, derivatives can be dependent on almost any variable, from the price of hogs to the amount of snow falling. at a certain ski resort.  

Since the first edition of this book was published in 1988 there have been many developments in derivatives markets. For example:.  

Many new instruments such as credit derivatives, electricity derivatives, weather derivatives, and insurance derivatives have been developed..   
Many new types of interest rate, foreign exchange, and equity derivatives now trade.   
There have been many new ideas in risk management and risk measurement.   
Real option methods for capital investment appraisal have been developed.   
The financial crisis of 2008 occurred, with derivatives (perhaps unfairly) getting much of the blame.   
Many regulations affecting the over-the-counter derivatives market have been introduced.   
The "risk-free' discount rate used to value derivatives has changed and the. decision has been taken to phase out LIBOR.   
Derivatives dealers now adjust the way they price derivatives to allow for credit risks, funding costs, and capital requirements. Collateral and credit issues are now given much more attention and have led to. changes in the way derivatives are traded.   
. Machine learning is now becoming widely used for managing derivatives portfolios. The book has evolved to keep up to date with these developments. For example: the.   
2008 financial crisis is discussed in Chapter 8; changes in the interest rates used for derivatives pricing are discussed in Chapter 4; valuation adjustments are covered in.   
Chapter 9; real options are explained in Chapter 36; credit derivatives are covered in.   
Chapter 25; energy, weather, and insurance derivatives are covered in Chapter 35..   
Machine learning applications are discussed at various points in the book..  

In this opening chapter, we take a first look at derivatives markets and how they are. changing. We contrast exchange-traded and over-the-counter derivatives markets and review recent regulatory changes affecting the markets. We describe forward, futures, and options markets and provide examples of how they are used by hedgers, specu-. lators, and arbitrageurs. Later in the book we will elaborate on many of the points. made in this chapter.  
