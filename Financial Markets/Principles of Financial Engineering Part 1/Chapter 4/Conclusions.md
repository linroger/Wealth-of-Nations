# 4.10 CONCLUSIONS  

Why buy and sell securities when you can swap the corresponding returns and achieve the same objective efficiently, and at minimal cost?  

In fact, selling or buying a security may not be practical in many cases. First, these operations generate cash which needs to be taken care of. Second, the security may not be very liquid and selling it may not be easy. Third, once a security is sold, search costs arise when, for some reason, we need it back. Can we find it? For how much? What are the commissions? Swapping the corresponding returns may cost less.  

Due to their eliminating the need to use cash in buying and selling transactions, combining these. two operations into one, and eliminating potential credit risks, swaps have become a major tool for financial engineers.  

# SUGGESTED READING  

Swaps are vanilla products, and there are several recommended books that deal with them. This chapter has provided a nontechnical introduction to swaps, hence we will list references at the same level. For a good introduction to swap markets, we recommend McDougall (1999). Flavell (2009) and Das (1994) give details of swaps and discuss many examples. Serrat and Tuckman (2011) describe risk management and hedging involving swaps in greater detail than this chapter allowed for space reasons.  

# EXERCISES  

1. On March 3, 2o00, the Financial Accounting Standards Board, a crucial player in financial engineering problems, published a series of important new proposals concerning the accounting of certain derivatives.34 It is known as Statement 133 and affects the daily lives of risk managers and financial engineers significantly. One of the treasurers who is affected by the new rules had the following comment on these new rules: Statement 133 in and of itself will make it a problem from an accounting point of view to do swaps. The amendment does not allow for a distinction to be made between users of aggressive swap hedges and those involved in more typical swaps. According to Thomson Reuters IFR, this treasurer has used synthetic swaps to get around [the FAS 133].35 a. Ignoring the details of swaps as an instrument, what is the main point in FAS 133 that disturbs this market participant? b. How does the treasurer expect to get around this problem by constructing synthetics?.  

2. Read the following episode carefully. Italian Asset Swap Volumes Soar on Buyback Plans,. Volumes in the basis-swap spread market doubled last week as traders entered swaps in. response to the Italian treasury's announcement that it "does not rule out buybacks." Traders said the increase in volume was exceptional given that so many investors are on holiday at this time of year.. Traders and investors were entering trades designed to profit if the treasury initiates a buyback program and the bonds increase in value as they become scarcer and outperform. the swaps curve. A trader said in a typical trade the investor owns the 30-year Italian government bond and enters a swap in which it pays the $6\%$ coupon and receives 10.5 basis points over 6-month Euribor. "Since traders started entering the position last Monday, the spread has narrowed to 8 bps over Euribor," he added. The trader thinks the spread could narrow to 6.5 bps over Euribor within the next month if conditions in the equity and emerging markets improve. A trader at a major European bank predicts this could go to Euribor flat over the next 6 months. The typical notional size of the trades is E50 million (USD43.65 million) and the maturity is 30 years (Thomson Reuters IFR, Issue 1217). a. Suppose there is an Italian swap curve along with a yield curve obtained from Italian government bonds (sovereign curve). Suppose this latter is upward sloping. Discuss how the two curves might shift relative to each other if the Italian government buys back some bonds. b. Is it important which bonds are bought back? Discuss. c. Show the cash flows of a 5-year Italian government coupon bond (paying $6\%$ ) and the cash flows of a fixed-payer interest-rate swap. d. What is the reason behind the existence of the 10.15 bp spread? e. What happens to this spread when government buys back bonds? Show your conclusions using cash flow diagrams.  

3. You are a swap dealer and you have the following deals on your book: Long  

2-year receiver vanilla interest-rate swap, at. $6.75\%$ p.a. 30/360. USD $N=50$ million. 3-year receiver vanilla interest-rate swap, at. $7.00\%$ p.a. 30/360. USD $N=10$ million. Short 5-year receiver vanilla interest-rate swap, at $7.55\%$ p.a. 30/360. USD $N=10$ million. a. Show the cash flows of each swap.. b. What is your net position in terms of cash flows? Show this on a graph. c. Calculate the present values of each swap using the swap curve:  

<html><body><table><tr><td>Maturity</td><td>Bid-Ask</td></tr><tr><td>2</td><td>6.75-6.80</td></tr><tr><td>3</td><td>6.88-6.92</td></tr><tr><td>4</td><td>7.02-7.08</td></tr><tr><td>5</td><td>7.45-7.50</td></tr><tr><td>6</td><td>8.00-8.05</td></tr></table></body></html>  

d. What is your net position in terms of present value?  

e. How would you hedge this with a 4-year swap? Which position would you take, and what should the notional amount be?   
f.Where would you go to get this hedge?   
g. Can you suggest another hedge?  

This page intentionally left blank  

# REPO MARKET STRATEGIES IN FINANCIAL ENGINEERING  

# 5  

# :HAPTER OUTLINE  

5.1 Introduction. 150   
5.2 Repo Details . 151   
5.2.1 Repo Terminology. 152   
5.2.2 Special Versus General Collateral.. .153   
5.2.2.1 Why do bonds go special?.... .153   
5.2.3 Summary. .154   
5.3 Types of Repo... 154   
5.3.1 Classic Repo 154   
5.3.2 Sell and Buy-Back. 155   
5.3.3 Securities Lending.. 156   
5.3.4 Repo and Custody Types.. 157   
5.3.4.1 What is a matched-book repo dealer? 159   
5.3.5 Aspects of the Repo Deal .. 159   
5.3.6 Types of Collateral .. 160   
5.3.7 Repo and Credit Risk... 160   
5.4 Equity Repos.. .160   
5.5 Repo Market Strategies ... .161   
5.5.1 Funding a Bond Position. . 162   
5.5.1.1 A subtle risk.. .164   
5.5.1.2 The asset swap.. .165   
5.5.1.3 Risks and pricing aspects. 165   
5.5.1.4 An arbitrage approach.. .165   
5.5.2 Futures Arbitrage. 165   
5.5.3 Hedging a Swap .166   
5.5.4 Tax Strategies . 166   
5.6 Synthetics Using Repos .. 168   
5.6.1 A Contractual Equation .... 168   
5.6.2 A Synthetic Repo.. .169   
5.6.3 A Synthetic Outright Purchase. .169   
5.6.4 Swaps Versus Repo.. .169   
5.7 Differences Between Repo Markets and the Impact of the GFC. 170   
5.8 Conclusions. 170   
Suggested Reading. 171   
Exercises 171  
