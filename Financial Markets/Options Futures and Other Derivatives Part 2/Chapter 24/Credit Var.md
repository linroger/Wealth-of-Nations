---
tags:
  - '#collateralized_debt_obligation'
  - '#credit_default_swap'
  - '#credit_derivatives'
  - '#credit_var'
  - '#creditmetrics'
  - '#cva_dva'
  - '#default_probability'
  - '#gaussian_copula_model'
  - '#risk_neutral_probabilities'
---
# 24.9 CREDIT VaR  

Credit value at risk can be defined analogously to the way value at risk is defined for market risks (see Chapter 22). For example, a credit VaR with a confidence level of $99.9\%$ and a 1-year time horizon is the credit loss that we are $99.9\%$ confident will not be exceeded over 1 year.  

Consider a bank with a very large portfolio of similar loans. As an approximation, assume that the probability of default is the same for each loan and the correlation between each pair of loans is the same. When the Gaussian copula model for time to default is used, the right-hand side of equation (24.9) is to a good approximation equal to the percentage of defaults by time $T$ as a function of $F$ The factor $F$ has a standard normal distribution. We are $X\%$ certain that its value will be greater than $N^{-1}(1-X)=-N^{-1}(X)$ . We are therefore $X\%$ certain that the percentage of losses over $T$ years on a large portfolio will be less than $V(X,T)$ , where  

$$
V(X,T)=N{\binom{N^{-1}[Q(T)]+{\sqrt{\rho}}N^{-1}(X)}{\sqrt{1-\rho}}}
$$  

This result was first produced by Vasicek.16 As in equation (24.9), $Q(T)$ is the probability of default by time. $T$ and $\rho$ is the copula correlation between any pair of. loans.  

A rough estimate of the credit VaR when an $X\%$ confidence level is used and the time horizon is. $T$ is therefore. $L(1-R)V(X,T)$ , where. $L$ is the size of the loan portfolio and $R$ is the recovery rate. The contribution of a particular loan of size $L_{i}$ to the credit VaR is ${\cal L}_{i}(1-R)V(X,T)$ This model underlies some of the formulas that regulators use for credit risk capital.17  

# Example 24.8  

Suppose that a bank has a total of $\$100$ million of retail exposures. The 1-year probability of default averages $2\%$ and the recovery rate averages $60\%$ . The copula correlation parameter is estimated as 0.1. In this case,  

$$
V(0.999,1)=N\bigg(\frac{N^{-1}(0.02)+\sqrt{0.1}N^{-1}(0.999)}{\sqrt{1-0.1}}\bigg)=0.128
$$  

showing that the $99.9\%$ worst case default rate is $12.8\%$ . The 1-year $99.9\%$ credit VaR is therefore $100\times0.128\times(1-0.6)$ or $\$5.13$ million.  

# CreditMetrics  

Many banks have developed other procedures for calculating credit VaR. One popular approach is known as CreditMetrics. This involves estimating a probability distribution of credit losses by carrying out a Monte Carlo simulation of the credit rating changes of all counterparties. Suppose we are interested in determining the probability distribution of losses over a 1-year period. On each simulation trial, we sample to determine the credit rating changes and defaults of all counterparties during the year. We then revalue our outstanding contracts to determine the total of credit losses for the year. After a large number of simulation trials, a probability distribution for credit losses is obtained. This can be used to calculate credit VaR.  

This approach is liable to be computationally quite time intensive. However, it has the. advantage that credit losses are defined as those arising from credit downgrades as well as defaults (with credit upgrades being counted as negative losses). Also the impact of credit mitigation clauses such as those described in Section 24.7 can be approximately. incorporated into the analysis.  

Table 24.4 is typical of the historical data provided by rating agencies on credit rating changes and could be used as a basis for a CreditMetrics Monte Carlo simulation. It shows the percentage probability of a bond moving from one rating category to another during a 1-year period. For example, a bond that starts with an A credit rating has  

Table 24.4 One-year ratings transition matrix, 1981-2019, with probabilities expressed as percentages and transitions to the WR (without rating) category being allocated proportionally to other categories, calculated from S&P data.   


<html><body><table><tr><td rowspan="2">Initial rating</td><td colspan="8">Rating at year-end</td></tr><tr><td>AAA</td><td>AA</td><td>A</td><td>BBB</td><td>BB</td><td>B</td><td>CCC/C</td><td>Default</td></tr><tr><td>AAA</td><td>89.83</td><td>9.37</td><td>0.55</td><td>0.05</td><td>0.11</td><td>0.03</td><td>0.05</td><td>0.00</td></tr><tr><td>AA</td><td>0.51</td><td>90.77</td><td>8.06</td><td>0.50</td><td>0.05</td><td>0.06</td><td>0.02</td><td>0.02</td></tr><tr><td>A</td><td>0.03</td><td>1.74</td><td>92.49</td><td>5.27</td><td>0.28</td><td>0.12</td><td>0.02</td><td>0.05</td></tr><tr><td>BBB</td><td>0.01</td><td>0.10</td><td>3.59</td><td>91.83</td><td>3.73</td><td>0.47</td><td>0.11</td><td>0.17</td></tr><tr><td>BB</td><td>0.01</td><td>0.03</td><td>0.12</td><td>5.23</td><td>86.06</td><td>7.27</td><td>0.60</td><td>0.67</td></tr><tr><td>B</td><td>0.00</td><td>0.02</td><td>0.08</td><td>0.18</td><td>5.43</td><td>85.38</td><td>5.10</td><td>3.80</td></tr><tr><td>CCC/C</td><td>0.00</td><td>0.00</td><td>0.13</td><td>0.22</td><td>0.69</td><td>15.33</td><td>51.61</td><td>32.03</td></tr></table></body></html>  

$92.49\%$ chance of still having an A rating at the end of 1 year. It has a $0.05\%$ chance of defaulting during the year, a $5.27\%$ chance of dropping to BBB, and so on.18  

In sampling to determine credit losses, the credit rating changes for different counterparties should not be assumed to be independent. A Gaussian copula model is typically used to construct a joint probability distribution of rating changes similarly to the way it is used in the model in the previous section to describe the joint probability. distribution of times to default. The copula correlation between the rating transitions for two companies is usually set equal to the correlation between their equity returns. using a factor model similar to that in Section 24.8..  

As an illustration of the CreditMetrics approach suppose that we are simulating. the rating change of a AAA and a BBB company over a 1-year period using the transition. matrix in Table 24.4. Suppose that the correlation between the equities of the two companies is 0.2. On each simulation trial, we would sample two variables. $x_{A}$ and $x_{B}$ from normal distributions so that their correlation is 0.2. The variable. $x_{A}$ determines the new rating of the AAA company and the variable $x_{B}$ determines the new rating of the BBB company. Since $N^{-1}(0.8983)=1.2719$ , the AAA company stays AAA if $x_{A}<1.2719$ ; since $N^{-1}(0.8983+0.0937)=2.4089$ , it becomes AA if $1.2719\leq x_{A}<$ 2.4089; since $N^{-1}(0.8983+0.0937+0.0055)=2.8070$ it becomes A if $2.4089\leq x_{A}<$ 2.8070; and so on. Consider next the BBB company. Since. $N^{-1}(0.0001)=-3.7190$ , the BBB company becomes AAA if $x_{B}<-3.7190$ ; since $N^{-1}(0.0001+0.0010)=-3.0618$ it becomes AA if $-3.7190\leq x_{B}<-3.0618$ ; since $N^{-1}(0.0001+0.0010+0.0359)=$ $-1.7866$ , it becomes A if $-1.7866\leq x_{B}<-3.0618$ and so on. The AAA never defaults during the year. The BBB defaults when $x_{B}>N^{-1}(0.9983)$ , that is, when $x_{B}>2.9290$  

# SUMMARY  

The probability that a company will default during a particular period of time in the future can be estimated from historical data, bond prices, or equity prices. The default. probabilities calculated from bond prices are risk-neutral probabilities; those calculated  

from historical data are real-world probabilities; equity prices can be used to estimate.   
either real-world or risk-neutral probabilities. Real-world probabilities should be used for scenario analysis and the calculation of credit VaR. Risk-neutral probabilities.   
should be used for valuing credit-sensitive instruments. Risk-neutral default probabil-.   
ities are often significantly higher than real-world default probabilities..  

The credit valuation adjustment (CVA) is the amount by which a bank reduces the value of a derivatives portfolio with a counterparty because of the possibility of the counterparty defaulting. The debt (or debit) valuation adjustment (DVA) is the amount by which it increases the value of a portfolio because it might itself default. The calculation of CVA and DVA involves a time-consuming Monte Carlo simulation to determine the expected future exposures of the two sides of the portfolio.  

Credit VaR can be defined similarly to the way VaR is defined for market risk. One approach to calculating it is the Gaussian copula model of time to default. This is used by regulators in the calculation of capital for credit risk. Another popular approach for calculating credit VaR is CreditMetrics. This uses a Gaussian copula model for credit rating changes.  

# FURTHER READING  

Altman, E. I. "Measuring Corporate Bond Mortality and Performance," Journal of Finance, 44 (1989): 902-22.   
Altman, E. I., B. Brady, A. Resti, and A. Sironi. "The Link Between Default and Recovery Rates: Theory, Empirical Evidence, and Implications," Journal of Business, 78, 6 (2005), 2203-28.   
Duffie, D., and K. Singleton "Modeling Term Structures of Defaultable Bonds," Review of Financial Studies, 12 (1999): 687-720.   
Finger, C. C. "A Comparison of Stochastic Default Rate Models," RiskMetrics Journal, 1 (November 2000): 49-73.   
Gregory, J. The xVA Challenge: Counterparty Risk, Funding Collateral, Capital and Initial Margin, 4th edn. Chichester, U.K.: Wiley, 2020..   
Hull, J. C., M. Predescu, and A. White. "Relationship between Credit Default Swap Spreads,. Bond Yields, and Credit Rating Announcements," Journal of Banking and Finance, 28 (November 2004): 2789-2811.   
Kealhofer, S. "Quantifying Credit Risk I: Default Prediction," Financial Analysts Journal, 59, 1 (2003a): 30-44.   
Kealhofer, S. "Quantifying Credit Risk II: Debt Valuation," Financial Analysts Journal, 59, 3 (2003b): 78-92.   
Li, D. X. "On Default Correlation: A Copula Approach," Journal of Fixed Income, March 2000:. 43-54.   
Merton, R. C. "On the Pricing of Corporate Debt: The Risk Structure of Interest Rates," Journal of Finance, 29 (1974): 449-70.   
Vasicek, O. "Loan Portfolio Value," Risk (December 2002), 160-62.  

# Practice Questions  

24.1. The spread between the yield on a 3-year corporate bond and the yield on a similar riskfree bond is 50 basis points. The recovery rate is $30\%$ . Estimate the average hazard rate per year over the 3-year period.  

24.2. Suppose that in Problem 24.1 the spread between the yield on a 5-year bond issued by the same company and the yield on a similar risk-free bond is 60 basis points. Assume the same recovery rate of $30\%$ . Estimate the average hazard rate per year over the 5-year period. What do your results indicate about the average hazard rate in years 4 and 5?  

24.3. Should researchers use real-world or risk-neutral default probabilities for (a) calculating credit value at risk and (b) adjusting the price of a derivative for defaults?   
24.4. How are recovery rates usually defined?   
24.5. Explain the difference between an unconditional default probability density and a. hazard rate.   
24.6. What are the seven-year historical hazard rates that would be calculated from Table 24.1 for companies with different credit ratings? Assuming a $40\%$ recovery rate, what credit spread is necessary to compensate for these hazard rates?   
24.7. Describe how netting works. A bank already has one transaction with a counterparty on its books. Explain why a new transaction by a bank with a counterparty can have the effect of increasing or reducing the bank's credit exposure to the counterparty.   
24.8. "DVA can improve the bottom line when a bank is experiencing financial difficulties." Explain why this statement is true..   
24.9. Explain the difference between the Gaussian copula model for the time to default and CreditMetrics as far as the following are concerned: (a) the definition of a credit loss and (b) the way in which default correlation is modeled.   
24.10. Show that the value of a coupon-bearing corporate bond is the sum of the values of its constituent zero-coupon bonds when the amount claimed in the event of default is the no-default value of the bond, but that this is not so when the claim amount is the face value of the bond plus accrued interest..   
24.11. A 4-year corporate bond provides a coupon of $4\%$ per year payable semiannually and has a yield of $5\%$ expressed with continuous compounding. The risk-free yield curve is flat at $3\%$ with continuous compounding. Assume that defaults can take place at the end of each year (immediately before a coupon or principal payment) and that the recovery rate is $30\%$ . Estimate the risk-neutral default probability on the assumption that it is the same each year.   
24.12. A company has issued 3- and 5-year bonds with a coupon of $4\%$ per annum payable annually. The yields on the bonds (expressed with continuous compounding) are $4.5\%$ and $4.75\%$ , respectively. Risk-free rates are $3.5\%$ with continuous compounding for all maturities. The recovery rate is $40\%$ . Defaults can take place halfway through each year. The risk-neutral default rates per year are $Q_{1}$ for years 1 to 3 and $Q_{2}$ for years 4 and 5. Estimate $Q_{1}$ and $Q_{2}$   
24.13. Suppose that a financial institution has entered into a swap dependent on the sterling interest rate with counterparty $\boldsymbol{\mathrm X}$ and an exactly offsetting swap with counterparty Y. Which of the following statements are true and which are false? Explain your answers. (a) The total present value of the cost of defaults is the sum of the present value of the cost of defaults on the contract with $\boldsymbol{\mathrm X}$ plus the present value of the cost of defaults on the. contract with Y.  

(b) The expected exposure in 1 year on both contracts is the sum of the expected exposure on the contract with X and the expected exposure on the contract with Y..  

(c) The $95\%$ upper confidence limit for the exposure in 1 year on both contracts is the sum. of the $95\%$ upper confidence limit for the exposure in 1 year on the contract with X and the $95\%$ upper confidence limit for the exposure in 1 year on the contract with Y.   
24.14. "A long forward contract subject to credit risk is a combination of a short position in a. no-default put and a long position in a call subject to credit risk." Explain this statement.   
24.15. Why does the credit exposure on a matched pair of forward contracts resemble a straddle?.   
24.16. Explain why the impact of credit risk on a matched pair of interest rate swaps tends to be less than that on a matched pair of currency swaps.   
24.17. "When a bank is negotiating currency swaps, it should try to ensure that it is receiving the lower interest rate currency from companies with low credit risk.' Explain why.   
24.18. Does put-call parity hold when there is default risk? Explain your answer..   
24.19. In what is known as an asset swap, the promised coupons on a bond that is worth par are exchanged for a floating rate plus a spread. Show that the cost of default on the bond is the present value of the spread payments.   
24.20. Show that under Merton's model in Section 24.6 the credit spread on a $T$ year zerocoupon bond is $-\mathrm{ln}[N(d_{2})+N(-d_{1})/L]/T$ , where $L=D e^{-r\bar{T}}/V_{0}$   
24.21. Suppose that the spread between the yield on a 3-year zero-coupon riskless bond and a 3-year zero-coupon bond issued by a corporation is. $1\%$ . By how much does BlackScholes-Merton overstate the value of a 3-year European option sold by the corporation..   
24.22. Give an example of (a) right-way risk and (b) wrong-way risk..   
24.23. The credit spreads for 1-, 2-, 3-, 4-, and 5-year zero-coupon bonds are 50, 60, 70, 80, and 87 basis points, respectively. The recovery rate is $35\%$ . Estimate the average hazard rate. each year.   
24.24. Suppose a 3-year corporate bond provides a coupon of $7\%$ per year payable semiannually and has a yield of. $5\%$ (expressed with semiannual compounding). The yields for all. maturities on risk-free bonds is $4\%$ per annum (expressed with semiannual compounding). Assume that defaults can take place every 6 months (immediately before a coupon payment) and the recovery rate is $45\%$ . Estimate the hazard rate (assumed constant) for the three years. Assume that the probability of default immediately before a coupon payment is the default probability given by the hazard rate for the previous six months.   
24.25. Explain carefully the distinction between real-world and risk-neutral default probabilities. Which is higher? A bank enters into a credit derivative where it agrees to pay $\$100$ at the end of 1 year if a certain company's credit rating falls from A to BBB or lower. during the year. The 1-year risk-free rate is. $5\%$ . Using Table 24.4, estimate a value for the derivative. What assumptions are you making? Do they tend to overstate or under-. state the value of the derivative.   
24.26. The value of a company's equity is $\$4$ million and the volatility of its equity is $60\%$ . The debt that will have to be repaid in 2 years is $\$15$ million. The risk-free interest rate is $6\%$ per annum. Use Merton's model to estimate the expected loss from default, the probability of default, and the recovery rate in the event of default. (Hint: The Solver function in Excel can be used for this question, as indicated in footnote 10.)   
24.27. Suppose that a bank has a total of $\$10$ million of exposures of a certain type. The 1-year. probability of default averages $1\%$ and the recovery rate averages $40\%$ . The copula correlation parameter is 0.2. Estimate the $99.5\%$ 1-year credit $\mathrm{VaR}$   
24.28. Extend Example 24.6 to calculate CVA when default can happen in the middle of each month. Assume that the default probability per month during the first year is 0.001667 and the default probability per month during the second year is 0.0025.   
24.29. Calculate DVA in Example 24.6. Assume that default can happen in the middle of each month. The default probability of the bank is 0.001 per month for the two years and the recovery rate in the event of a bank default is $30\%$  

![](images/452c16c6a7aa2a80d80359862e5ab62041afba897a277e6833bb3460f2672544.jpg)  

# Credit Derivatives  

Credit derivatives began trading in the over-the-counter market in the late 1990s. In 2000, the total notional principal for outstanding credit derivatives contracts was about $\$800$ billion. By the financial crisis of 2007, this had become. $\$50$ trillion. After the crisis,. the size of the market declined. The total notional principal was about. $\$7.5$ trillion in December 2019. Credit derivatives are contracts where the payoff depends on the creditworthiness of one or more companies or countries. This chapter explains how credit derivatives work and how they are valued..  

Credit derivatives allow companies to trade credit risks in much the same way that they. trade market risks. Banks and other financial institutions used to be in the position where they could do little once they had assumed a credit risk except wait (and hope for the best). Now they can actively manage their portfolios of credit risks, keeping some and. entering into credit derivative contracts to protect themselves from others (see Business. Snapshot 25.1). Banks have historically been the biggest buyers of credit protection and. insurance companies have been the biggest sellers..  

Credit derivatives can be categorized as "single-name" or "multi-name." The most. popular single-name credit derivative is a credit default swap. The payoff from this instrument depends on the creditworthiness of one company or country. There are two. sides to the contract: the buyer and seller of protection. There is a payoff from the seller of protection to the buyer of protection if the specified entity (company or. country) defaults on its obligations. One multi-name credit derivative is a collateralized debt obligation. In this, a portfolio of debt instruments is specified and a complex structure is created where the cash flows from the portfolio are channelled to different categories of investors. Chapter 8 describes how multi-name credit derivatives were created from residential mortgages during the period leading up to the financial crisis. This chapter focuses on the situation where the underlying credit risks are those of corporations or countries.  

The chapter starts by explaining how credit default swaps work and how they are. valued. It then explains credit indices and the way in which traders can use them to buy. protection on a portfolio. After that it moves on to cover basket credit default swaps,. asset-backed securities, and collateralized debt obligations. It expands on the material in Chapter 24 to show how the Gaussian copula model of default correlation can be used to value tranches of collateralized debt obligations..  

# Business Snapshot 25.1 Who Bears the Credit Risk?  

Traditionally banks have been in the business of making loans and then bearing the credit risk that the borrower will default. However, banks have for some time been reluctant to keep loans on their balance sheets. This is because, after the capital required by regulators has been accounted for, the average return earned on loans is often less attractive than that on other assets. As discussed in Section 8.1, banks created asset-backed securities to pass loans (and their credit risk) on to investors. In. the late 1990s and early 2000s, banks also made extensive use of credit derivatives to shift the credit risk in their loans to other parts of the financial system.  

The result of all this is that the financial institution bearing the credit risk of a loan is often different from the financial institution that did the original credit checks. As the financial crisis starting in 2007 has shown, this is not always good for the overall health of the financial system.  
