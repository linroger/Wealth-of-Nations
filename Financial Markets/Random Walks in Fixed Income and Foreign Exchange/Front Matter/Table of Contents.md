---
tags:
  - conversion_factor
  - cross_currency_basis
  - empirical_method
  - fixed_income
  - forward_curve
  - fx_hedging
  - maturity_matched
  - rolling_hedges
  - term_premium
  - xva
aliases:
  - FX Hedged Pickup
  - Table of Contents
  - Term Premium
  - XCCY Basis
key_concepts:
  - Conversion Factor Examples
  - Cross-Currency Basis Swap
  - Defining Convexity
  - Defining Duration
  - FX Hedge Strategies
  - Forward Curve Analysis
  - Maturity-Matched Hedges
  - Term Premium Calculation
  - XVA Calculation
---

# Table of Contents - Random Walks in Fixed Income and Foreign Exchange
# Contents

Foreword

Preface

**Chapter 1** What Really is the Cross-Currency Basis?
*   The Calculation Underlying the Cross-Currency Basis Swap
*   A Quick Note on Terminology
*   Perhaps the Simplest Formula in Financial Mathematics
*   How the Calculation Distorts No-Arbitrage Pricing
*   On 29th December 2011
*   So, What Actually is a 'Cross-Currency Basis Swap'?
*   Conversion Factor
*   Where does the Cross-Currency Basis Come from?
*   What Keeps the Basis Swap from Being Arbitraged Away?
*   Capital Cost of FX Derivatives
*   Counterparty Risks and Credit Limits
*   Clearing
*   Horses for Courses
*   How Could an Institution Make Money from the Cross-Currency Basis Swap?
*   Appendix 1.A: The FX Carry Trade
*   Appendix 1.B: The Cross-Currency Toolkit

**Chapter 2** XVA and the Cross-Currency Basis
*   XVA - What is It?
*   A Brief Summary of Counterparty Risk
*   Risk vs Cost
*   CVA - The First Horse in the XVA Stable
*   DVA - The Next Calculation
*   FVA - Funding Impact
*   How XVA Costs Could Affect the Cross-Currency Basis
*   Sample XVA Calculation Using Market Standard Calculation Approach
*   Funding Constraints
*   Detail on Daily Funding/Rollover Process
*   Historical Funding Data
*   Trading the xccy Basis

**Chapter 3** Calculating Novel Cross-Currency Bases and FX Hedged Pickups
*   What is the FX Hedged Pickup?
*   Finding xccy Bases
*   Calculating FX Hedged Pickup
*   Appendix 3.A: Xccy Bases
*   Appendix 3.B: FX Hedged Pickups

**Chapter 4** Hedging of Fixed Income -- What is the Best Way?
*   FX Hedge Strategies
*   Maturity-Matched Hedges
*   Reducing Uncertainty to the Minimum Level for the Whole Tenor
*   Practical Calculation of Maturity-Matched Yield Pickup
*   Historical Results for G10 Maturity-Matched Yield Pickup
*   Rolling Hedges
*   Taking a Short-Term View
*   Possible Actions at 'Roll Point'
*   Historical Results for G10 Rolling Yield Pickup
*   Rolling Pickup 'One Period On' and for the Tenor of the Instrument
*   Translation Effect
*   Volatility Breakdown - What is Driving the Performance?
*   Numerical Example

**Chapter 5** Introducing the Conversion Factor
*   The Issuer's Choices
*   Tenor
*   Credit Spread
*   Cross-Currency Basis
*   Conversion Factor
*   Fees and Charges
*   What is the Conversion Factor?
*   Simplest Possible Example - 1-Year Bond, Zero Basis, USD Corporate
*   More Realistic - Using the Yield Curve
*   Another Way to Think about It
*   Examples of Conversion Factors
*   Forecasting Conversion Factors
*   Translating Spreads across Currencies

**Chapter 6** An Empirical Method of Calculating the Term Premium
*   Introduction
*   Why is the Term Premium Important?
*   The Term Premium and Forward Rates
*   An Empirical Method for Determining the Term Premium
*   Results
*   Median (Predicted - Actual) Moves for USD
*   Choice of Forward Curve
*   Lookback Period
*   Discount Factor Calculation
*   10y Term Premium Results
*   2y Term Premium Results
*   Recent Results: A General Pitfall with Term Premium Methods
*   Discussion of Results
*   Appendix 6.A: BIS Report Graphs
*   References

**Chapter 7** An Update of the Term Premium Calculation
*   Introduction
*   Evolution of Yield Curves
*   Term Premium Values Over Time
*   Term Premium Models; Similarities and Differences
*   Aggregating Model Results

**Chapter 8** Forward Curves, Duration and Convexity
*   Are the Forwards a Useful Forecast?
*   Why are Forward Curves so 'Abnormal'?
*   Simple Spot and Forward Curve Evolution
*   Forward Implied Slopes vs Realised Data
*   Analysis of Mean Forecast Slope vs Mean Actual Slope
*   Forward Implied Slopes and Direction
*   Can We Monetise This?
*   The Value of Convexity
*   Defining Duration
*   Defining Convexity
*   Numerical Calculation of Convexity
*   The Long End of the Curve
*   Value of Convexity through Time
*   Conclusion
*   Appendix 8.A: EUR Ratios
*   Appendix 8.B: USD Ratios
*   Appendix 8.C: Implied vs Actual Slope Changes, 2001-2007
*   Appendix 8.D: Implied vs Actual Slope Changes, 2007-2014
*   Appendix 8.E: Implied vs Actual Slope Changes, 2014-2020

**Chapter 9** Implied vs Realised Convexity
*   Defining Convexity
*   Value of Implied Convexity
*   Value of Realised Convexity

List of Figures

List of Tables

About the Authors

References

Index

# Preface

The first section examines the rise of the cross-currency basis in the post-crisis world, digs into its origins and applications, and investigates the implication of the new credit-sensitive world for issuance, investment and hedging. In Chapter 1, we define and dig into the origins of the basis, which before 2008 would have represented a juicy arbitrage opportunity. Understanding why this is not so today leads us to the discussion in Chapter 2 about the drivers and sustainers of the basis, and in Chapter 3 we show that it is possible to derive and create many cross-currency bases which are not usually quoted in the market but which can represent very real opportunities for issuers and investors. Chapter 4 derives a new way of looking at FX hedging of fixed income assets, followed by Chapter 5, which shows how to analyse these hedged assets and understand the linked effects of the basis and the two yield curves which underly their valuation.

The second section examines the impact of the new world on the yield curve, and vice versa. Term premium, duration and convexity all take on new importance in this new state of ultra-low rates and flat term structures. The search for yield in this brave new world has driven issuers to issue, and investors to buy, century-long bonds, in a world where only a scant handful of currencies have ever survived that long. Convexity has been a driver of this process - whether for good or bad, time will tell. We show how to derive a closed-form solution for both duration and convexity, and show how implied convexity at the start of the life of a bond can be compared to its realised value through its lifetime.