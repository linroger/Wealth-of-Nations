# 23.10 CONCLUSIONS  

There may be several other real-world complications. For example, consider the application of the CPPI to the credit sector. One very important question is what happens on a roll? Clearly the structurer would like to stay with on-the-run series, and during the roll there will be mark-to-market adjustments which may be infinitesimal and similar to jumps.  

A second question is how to pick the leverage factor in some optimal fashion. It is clear that this will involve some Monte Carlo approach but the more difficult issue is how to optimize this.  

# SUGGESTED READING  

The first academic papers on CPPI were by Perold (1986) who discusses CPPI for fixed-income. instruments and Black and Jones (1987) who study CPPI for equity instruments. We also recom-. mend the recent paper by Cont and Tankov (2009). Joossens and Schoutens (2010) discuss and compare CPPI and CPDO structures. Jin and Whetten (2005) summarize the evolution of CreditLinked CPPI Variations.  

# EXERCISES  

1. Consider the iTraxx CPPI example in this chapter. We assumed an increase in the value of the iTraxx tranche as $q_{t_{1}}$ dropped from $20\%$ to $15\%$ . Now assume that spreads widen and credit quality decreases so that $q_{t_{1}}$ increases from $20\%$ to $25\%$ . Calculate the resulting change in the leverage and explain the adjustment in detail required to return to the target leverage of 2.  

2. The iTraxx crossover index followed the path given below during three successive time periods:  

Assume that there are 30 reference names in this portfolio.  

a. You decide to select a leverage ratio of 2 and structure a five-year CPPI note on iTraxx crossover index. LIBOR rates are $5\%$ . Describe your general strategy and, more important, show your initial portfolio composition.   
b. Given the path above, calculate your portfolio adjustments for the three periods..   
c. In period four, iTraxx becomes 370 and one company defaults. Show your portfolio adjustments. (Assume a recovery of $40\%$ . Reminder: Do not forget that there are 30 names in the portfolio.)  

# COUNTERPARTY RISK MULTIPLE CURVES, CVA, DVA, AND FVA  

# 24  

# CHAPTER OUTLINE  

24.1 Introduction. 827   
24.2 Counterparty Risk. . 829   
24.3 Credit Valuation Adjustment. .831   
24.3.1 Counterparty Risk Example and CVA . 831   
24.3.2 CVA as an Option.. 833   
24.3.2.1 Close-out proceedings 834   
24.3.3 Counterparty Risk and Unilateral CVA in a Single IRS.. 836   
24.3.4 Numerical CVA Example for IRS Portfolio. 837   
24.4 Debit Valuation Adjustment.. .842   
24.5 Bilateral Counterparty Risk. .843   
24.6 Hedging Counterparty Risk.. 843   
24.6.1 CVA and DVA Hedging in Practice. 844   
24.6.2 Contingent CDS. 845   
24.7 Funding Valuation Adjustment ... .845   
24.8 CVA Desk.. .846   
24.9 Choice of the Discount Rate and Multiple Curves .... 847   
.4.10 Conclusions.. .849   
Suggested Reading . .849   
Exercises ... .850   
MATLAB Exercise. 850  
