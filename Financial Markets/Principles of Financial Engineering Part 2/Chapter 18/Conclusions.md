---
tags:
  - cds_pricing
  - credit_derivatives
  - credit_event
  - sovereign_cds
  - value_at_risk
aliases:
  - CDS Summary
  - Chapter Conclusions
  - Credit Derivatives
  - Value at Risk
key_concepts:
  - CDS contractual equation
  - CDS pricing example
  - Credit derivative usage
  - Credit derivatives introduction
  - Credit event triggers
  - Currency swap usage
  - Forward caps/floors
  - Hazard rate calculation
  - IRS usage
  - Implied hazard rate
  - Recovery clauses
  - Risky bond transformation
  - Swaption contract need
  - Value-at-risk calculations
---

# 18.10 CONCLUSIONS  

This chapter is only a very brief introduction to this important class of credit derivatives. We saw that CDS play a key role in completing the methodology of financial engineering. We developed a. contractual equation for CDS and applied it to negative basis trades. We discussed real-world complications related to recovery clauses and drew lessons about the importance of credit event triggers and settlement following recent sovereign defaults and sovereign CDS triggers.  

# SUGGESTED READING  

Several recent books deal with this new sector. For a good theoretical background and some empirical work, Duffie and Singleton (2003) is very useful. Bielecki and Rutkowski (2001) is. more mathematically involved, but excellent. The Barclays Capital Standard Corporate CDS Handbook 2010 provides a good summary of the main changes in the CDS market after the GFC. The monthly Risk publication, Credit, is also good reading on market activity. We only covered a simple example of CDS pricing in this chapter. For a detailed description of CDS pricing under. real-world market conventions see White (2013). Hull (2014) and O'kane (2008) are also go0d. references. The classic reading here is Merton (1974). Giesecke (2002) is a good survey on pricing. The reader should also consult the very good source, Schonbucher (2003). The April 2013 IMF Global Financial Stability Report reviews recent issues in sovereign CDS markets.  

# EXERCISES  

1. This exercise deals with value-at-risk calculations for credit portfolios. Using the data on a. corporate financial statement, answer the following questions:. a. How would you calculate the default probabilities? b. How can one obtain the migration matrix for a credit? c. How can one obtain the joint migration probabilities for the relevant credits in a bank's portfolio.  

2. You are given two risky bonds with the following specifications: Bond A  

a. Par: 100   
b. Currency: USD   
c. Coupon: 10   
d. Maturity: 4 years   
e. Callable after 3 years   
f. Credit: AA  
Bond B   
a. Par: 100   
b. Currency: EUR   
c. Coupon: LIBOR $+78$ bp   
d. Maturity: 5 years   
e. Credit: AAA  

You will be asked to transform Bond A into Bond B by acquiring some proper derivative contracts. Use cash flow diagrams and be precise.  

Show how you would use a currency swap to switch into the right currency.. Show how you would use an IRS to switch to the needed interest rate.. Is there a need for using a swaption contract? Can the same be accomplished using forward caps and floors? Finally, show two ways of using credit derivatives to switch to the desired credit qualit  

3. Consider the CDS pricing example in Section 18.7. Assume that hazard rate is. $3\%$ instead of $5\%$ but all other input parameters remain the same. Calculate the value of the CDS by finding the CDS spread cds that sets the expected present value of the protection leg payments equal to the expected present value of the premium leg payments as in the text.  

4. In the CDS pricing example in the text we assumed a hazard rate to derive the CDS spread and to price the contract. Now assume that the hazard rate is unknown, but assume that you can observe a CDS spread of 200 bp in the market for this credit. The recovery rate is still $40\%$ , the maturity is 5 years, the riskless rate is. $4\%$ and the yield curve is flat. Assumptions about the timing of defaults and accrued premia are unchanged. Calculate the. implied hazard rate.  

5. a. Consider the following quote from Reuters: The poor correlation between CDS and cash in Swedish utility Attentat (VTT.XE) is an anomaly and investors can benefit by setting up negative basis trades, says ING. 5-yr CDS for instance has tightened by approx. 5 bp since mid-May while the Attentat 2010 is actually approx. 1 bp wider over the same period.  

Buy the 2010 bond and CDS protection at approx midas $+27$ bp. (MO)  

i. Display this position on a graph with cash flows exactly marked..   
ii. Explain the logic of this position..   
ii. Explain the numbers involved. In particular, suppose you have 100 to invest in such a position, what would be the costs and expected returns?.   
iv. What other parameters may have caused such a discrepancy?  

6. Consider the following news from Reuters: 1407 GMT [Dow Jones] LONDON-According to a large investment bank investors can boost yields using the following strategies: a. In the strategy, sell 5-yr CDS on basket of Greece $(9b p)$ , Italy $(8.5b p)$ , Japan (4 bp), Poland (12 bp), and Hungary (16 bp), for $34$ bp spread. Buy 5-yr protection on iTraxx Europe at 38 bp to hedge. Trade gives up 4 bp but will benefit if public debt outperforms credit. b. To achieve neutral or positive carry, adjust notional amounts-for example in the first trade, up OECD basket's notional by $20\%$ for spread neutral position. c. Emerging market basket was $65\%$ correlated with iTraxx in 2005, hence use the latter a. hedge. i. Explain the rationale in item (a). In particular, explain why the iTraxx Xover is used as a hedge.  

ii. Explain how you would obtain positive carry in (b). Ii. What is the use of the information given in statement (c)?  

7. Consider the following news from Reuters: HVB Suggests Covered Bond Switches. 0843 GMT [Dow Jones] LONDON-Sell DG Hyp $4.25\%$ 2008s at 6.5 bp under swaps and buy Landesbank Baden-Wuerttemberg(LBBW) $3.5\%$ 2009s at swaps-4.2 bp, HVB says. The. LBBW deal is grandfathered and will continue to enjoy state guarantees; HVB expects spreads to tighten further in the near future. a.What is a German Landesbank? What are their ratings?. b. What is the logic behind this credit strategy?. c. Can you take the same position using CDSs? Describe how..  

8. Explain the logic behind the two following strategies using cash flow diagrams.  

a. WestLB mortgage Pfandbriefe trade too tight. Sell the WestLB $3\%$ 2009s at 5.4 bp under swaps and buy the zero risk weighted Land Berlin. $2.75\%$ 2010s at 2.7 bp under. (TMA)   
b. The following quote deals with implied forward rates in the credit sector. Using proper. diagrams explain what the trade is.. Implied forward CDS levels look high because shorter-dated CDS are currently too cheap. to 5-year, says BNP Paribas. Using the iTraxx Main curve as reference gives a. theoretical 3-year forward curve that shows. $\epsilon$ month and $I$ -year CDS both at 60 bp. "In 3-years time, we find that 6-month and. $I$ -year CDS are very unlikely to be trading. above 60 bp." Take advantage through the 3-5-10-year barbell, buying iTraxx 3-year at 20.75 bp for EUR20M, selling iTraxx 5-year at 38 bp for EUR25M, and buying iTraxx 10-year at 61.25 bp for EUR7M. The trade has a yearly carry of EUR32,000 for a short nominal exposure of EUR2M.  

This page intentionally left blank  

# ENGINEERING OF EQUITY INSTRUMENTS AND STRUCTURAL MODELS OF DEFAULT  

# 19  

# CHAPTER OUTLINe  
