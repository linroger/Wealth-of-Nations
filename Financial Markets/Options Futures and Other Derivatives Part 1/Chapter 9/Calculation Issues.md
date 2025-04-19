---
tags:
  - calculation_issues
  - cva
  - dva
  - fva
  - kva
  - machine_learning
  - monte_carlo
  - mva
  - xva
aliases:
  - Calculation Problems
  - Credit Valuation Adjustment
  - Debt Valuation Adjustment
  - Funding Valuation Adjustment
  - XVA Calculations
key_concepts:
  - CVA, DVA, FVA, MVA, KVA
  - Computationally time-consuming XVA calculations
  - Incremental FVA calculation
  - Machine learning for XVAs
  - Netting impact on CVA/DVA
---

# 9.4 CALCULATION ISSUES  

All of the XVAs are computationally time-consuming to calculate. Monte Carlo. simulations are necessary to determine expected credit exposures, expected funding costs, and expected capital requirements at future times. CVA is often actively managed. by banks. They sometimes buy protection against their counterparties defaulting using. credit default swaps (see Section 7.12 and Chapter 25) or similar instruments. This reduces their expected losses from defaults.  

As discussed in Section 9.1, CVA and DVA must be calculated on the whole portfolio of derivatives that a bank has with a counterparty. It cannot be calculated on a transaction-by-transaction basis. This is because of the impact of netting. A new. bilaterally cleared transaction with a counterparty will increase or decrease CVA and DVA depending on what happens when it is netted with other transactions that have been entered into with the counterparty. If it tends to increase credit exposure for the bank in the future, the incremental CVA will be positive; if it tends to decrease credit exposure in the future, the incremental CVA will decrease. Similarly for DVA.  

The incremental FVA can be calculated on a transaction-by-transaction basis. This is because the net funding required for a portfolio of transactions at any future time is the sum of that for the individual transactions.13 MVA for transactions cleared through a  

CCP has to be calculated on a portfolio basis. In the case of the example in Figure 9.1, it. is the impact of a new transaction on the initial margin required by the CCP for portfolio that Bank A is clearing through the CCP that determines the incremental initial margin. requirements and therefore MVA. KVA is even more complicated. The rules used by regulators are such that a bank must in theory sometimes model the bank's whole. portfolio when calculating incremental capital requirements..  

# Application of Machine Learning  

Because the calculation of XVAs is computationally quite time-consuming, some banks. are using machine learning to get faster results. They are particularly interested in being. able to quickly answer queries about the incremental effect of a proposed new. transaction on the XVAs. A neural network is a tool that can be used to do this. It is a flexible algorithm that can learn any continuous relationship between the value of a target variable (the output) and the values of features (the inputs) when a huge volume of data is available. Once the network has been constructed, calculating the target from. the features is very fast.  

To create a neural network to calculate incremental XVAs, an analyst randomly creates many different data sets that are inputs to the calculation. (The data set will include features describing the proposed new transaction and features describing relevant aspects of existing trades with the counterparty.) Monte Carlo simulation is used to calculate the XVAs for each data set and an algorithm is used to find a neural network that replicates the Monte Carlo calculations as accurately as possible.  

# SUMMARY  

Banks and other derivatives market participants have for many years been concerned about counterparty credit risk. Two adjustments are the credit valuation adjustment (CVA) and debt or debit valuation adjustment (DVA). CVA is an adjustment by a bank for the possibility that its counterparty will default and it reduces the value of the derivatives portfolio it has with the counterparty. DVA is an adjustment for the possibility that the bank will default and it increases the value of the derivatives portfolio. There is no real argument about whether these adjustments should be made, but many people are less comfortable with DVA than CVA. Why should a bank benefit from the possibility that it will itself default? As the probability of a default increases, the benefit increases.  

The funding valuation adjustment (FVA) is an adjustment to the value of a derivatives position arising from the funding required (or the funding generated) by a derivatives transaction. The margin valuation adjustment (MVA) quantifies the cost of funding initial margin. The capital valuation adjustment (KVA) is a valuation adjustment reflecting the impact of a derivatives position on capital requirements. Finance theory argues that the way a project is funded should not influence its valuation. In particular, the current average debt and equity costs should not be assumed to be the same as the incremental effect of a new transaction on funding costs. In spite of this, many banks do calculate MVA, FVA, and KVA based on these. average costs.  

# FURTHER READING  

Andersen, L. B. G., D. Duffie, and Y. Song. "Funding Value Adjustments," Working Paper, SSRN 2746010.   
Gregory, J. The XVA Challenge: Counterparty Credit Risk, Funding, Collateral, and Capital. Chichester: Wiley, 2015.   
Hull, J. C. Machine Learning in Business: An Introduction to the World of Data Science, 2nd edn., 2020. Available from Amazon. See: www-2.rotman.utoronto.ca/\~hull.   
Hull, J. C., and A. White. "The FVA Debate," Risk, 25th anniversary edition (July 2012): 83-85.   
Hull, J. C., and A. White. "Valuing Derivatives: Funding Value Adjustments and Fair Value," Financial Analysts Journal, 70, 3 (May/June 2014): 46-56.   
Hull, J. C., and A. White. "Collateral and Credit Issues in Derivatives Pricing," Journal of Credit Risk, 10, 3 (2014): 3-28.   
Hull, J. C., and A. White. "XVAs: A Gap Between Theory and Practice," Risk, 29, 5 (May 2016): 50-52.   
Kenyon, C., and Green, A. D. (eds.) Landmarks in XVA. London: Risk Books, 2016.  

# Short Concept Questions  

9.1. Explain what CVA and DVA measure.   
9.2. Explain what MVA and FVA measure.   
9.3. Explain what KVA measures.   
9.4. Explain how the "cure period" is used in the calculation of CVA.   
9.5. If the market considers that the default probability for a bank has increased, what   
happens to its DVA? What happens to the income it reports?  

# Practice Questions  

9.6. Explain the difference between the views of financial economists and most practitioners on how MVA and FVA should be calculated. 9.7. Explain the difference between the views of financial economists and most practitioners on how KVA should be calculated.   
9.8. Explain why FVA can be calculated for a transaction without considering the portfolio to which the transaction belongs, but that the same is not true of MVA.. 9.9. Suppose that a bank buys an option from a client. The option is uncollateralized and. there are no other transactions outstanding with the client. The expected values of the option at the midpoint of years 1, 2, and 3 are 6, 5, and 4. The probability of the counterparty defaulting in each of the three years is $3\%$ . The probability of the bank. defaulting in each of the three years is. $2\%$ . Estimate the bank's CVA and DVA for the. transaction. Assume no recovery in the event of a default and zero interest rates.   
9.10. "The impact of DVA on earnings volatility is generally greater than that of CVA."  

Explain this statement.  

9.11. A company is trying to decide between issuing debt and equity to fulfill a funding need. What in theory should happen to the return required by equity holders if it chooses. (a) debt and (b) equity?   
9.12. Explain the meaning of "netting". Suppose no collateral is posted. Why does a netting agreement usually reduce credit risks to both sides? Under what circumstances does. netting have no effect on credit risk?.   
9.13. The average funding cost for a company is. $5\%$ per annum when the risk-free rate is $3\%$ The company is currently undertaking projects worth $\$9$ million. It plans to increase its. size by undertaking. $\$1$ million of risk-free projects. What would you expect to happen to its average funding cost?.  

![](1ce4b24af23b5ac52adfb5a9f9928fe28ec70353d7cf60a3336dfbcaedd3d431.jpg)  

# Mechanics of Options Markets  

We introduced options in Chapter 1. This chapter explains how options markets are. organized, what terminology is used, how the contracts are traded, how margin requirements are set, and so on. Later chapters will examine such topics as trading. strategies involving options, the determination of option prices, and the ways in which portfolios of options can be hedged. This chapter is concerned primarily with stock options. It also presents some introductory material on currency options, index options, and futures options. More details concerning these instruments can be found in Chapters 17 and 18.  

Options are fundamentally different from forward and futures contracts. An option. gives the holder of the option the right to do something, but the holder does not have to exercise this right. By contrast, in a forward or futures contract, the two parties have. committed themselves to some action. It costs a trader nothing (except for the margin/. collateral requirements) to enter into a forward or futures contract, whereas the. purchase of an option requires an up-front payment..  

When charts showing the gain or loss from options trading are produced, the usual. practice is to ignore the time value of money, so that the profit is the final payoff minus the initial cost. This chapter follows this practice..  
