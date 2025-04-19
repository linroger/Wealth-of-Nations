---
tags:
  - derivatives
  - funding
  - fva
  - margin_valuation
  - mva
aliases:
  - FBA
  - FCA
  - Funding Valuation Adjustment
  - Margin Valuation Adjustment
key_concepts:
  - CCP and swaps
  - Funding benefit adjustment
  - Funding cost adjustment
  - Funding cost derivatives
  - Margin valuation adjustment
---

# 9.2 FVA AND MVA  

The funding valuation adjustment (FVA) and margin valuation adjustment (MVA) are adjustments to the value of a derivatives portfolio for the cost of funding derivative. positions. To illustrate how they might arise, suppose that a derivatives dealer, Bank A, is. in the situation illustrated in Figure 9.1. It has entered into a five-year interest rate swap with a corporate end user and has hedged its risk by entering into an exactly offsetting swap with another dealer, Bank B. It appears that Bank A has locked in a profit of. $0.1\%$ per year because it receives $3\%$ from Bank B and pays $2.9\%$ to the end user. We suppose that the transaction between Bank A and Bank B is cleared through a CCP with both sides posting initial margin and variation margin. (As explained in earlier chapters, this is required under post-crisis regulations for a standard swap such as this.).  

If the transaction with the end user in Figure 9.1 were cleared through the same CCP. as the transaction between the banks, Bank A's situation is straightforward. The CCP will net off the two transactions so that they do not lead to any incremental initial margin requirement for Bank A. Indeed, because the transactions always give a net. positive value to the bank, margin requirements should be slightly less than they would be without the two transactions..  

But let us assume that the transaction between Bank A and the end user is cleared bilaterally with no collateral being required while, as already mentioned, the transaction between Bank A and Bank B is cleared through a CCP. The transactions do then have some funding implications. First, the swap with Bank B is liable to lead the CCP requiring additional initial margin from Bank A during the life of the transaction. If we assume that the cost of funding initial margin is greater than the interest paid by the CCP on initial margin there is a cost to Bank A in funding the incremental initial margin. attributable to the transaction. This is referred to as a margin valuation adjustment. (MVA) and reduces the value to the bank of its transaction with the end user.2.  

The CCP's variation margin can also lead to funding requirements. Suppose that the transaction with Bank B has a negative value to Bank A so that the transaction with the end user has a positive value to Bank A. Bank A will have funds tied up in the variation margin it has posted with the CCP.? It will not receive any collateral to offset this initial margin from the end user. This gives rise to a funding need because Bank A has to. increase its funding from external sources. In the opposite situation, where the transaction with Bank B has a positive value and the transaction with the end user has a negative value, it receives variation margin from the CCP and does not have to provide any collateral or margin to the end user. This gives rise to a source of funding.  

We continue to assume that the cost of funding margin is greater than the interest. paid on it. There is a cost in the first case just considered (Bank A has to increase its funding from external sources) and a benefit in the second case (Bank A can reduce its funding from external sources). FVA is an adjustment to the value of derivatives that reflects these costs and benefits. The present value of the expected future funding cost is. referred to as the funding cost adjustment (FCA) and the present value of the expected. future funding benefit is referred to as the funding benefit adjustment (FBA). The. funding value adjustment, FVA, reduces the value of derivatives by the excess of FCA over FBA. Whether there is a positive or negative adjustment to the value of the swaps. in Figure 9.1 depends on whether the swap with Bank B is more likely to have a positive or negative value as time passes. This depends on the shape of the term structure of interest rates, as discussed in Section 7.7.  

![](4ad753624df201bc723b1d399bcd77953a438216b2d2b7a9376346eefb7d7fe0.jpg)  
Figure 9.1 Swaps entered into by Bank A. The transaction with Bank B is cleared through a CCP. The transaction with the end user is cleared bilaterally..  

The situation in Figure 9.1 is not the only way FVA and MVA can arise. An FVA potentially arises whenever a bank enters into an uncollateralized derivative transaction with a counterparty. When the uncollateralized derivative has a positive value, there is a. funding cost. When it has a negative value, there is a funding benefit.4 For example, if the bank buys an uncollateralized option from a counterparty, the option has a positive. value and there is a funding cost equal to the excess of the assumed cost of funding over. the risk-free rate assumed in the pricing of the option. If the bank sells an uncollateralized option to the counterparty, the option has a negative value and there is a funding benefit. MVA can arise whenever a transaction gives rise to incremental initial margin. requirements. As explained in earlier chapters, rules are being implemented requiring initial margin for bilaterally cleared transactions between financial institutions as well as. for those cleared through CCPs.5  

To calculate the MVA or FVA it is necessary to answer the question: "What is the. cost of funding the margin in a situation such as Figure 9.1?" This is where there is often a disagreement between theory and practice. Many banks argue that the cost of funding margin is equal to their average debt funding cost. Suppose the margin is. provided in U.S. dollars. If the interest received by a bank on U.S. dollar margin is the. federal funds rate minus 20 basis points and a bank's average funding cost is the federal funds rate plus 100 basis points, FVA and MVA would be calculated by these banks on the assumption of a funding cost of 120 basis points per year..  

Financial economics argues that the way an investment is funded should not affect the required return on the investment. The required return should reflect the riskiness of the investment. An investment in initial margin or variation margin usually has very low risk.7 As such, the bank should be comfortable with a return that is close to the risk-free rate. If the return requirement on margin in our example is assumed to be the fed funds rate plus 10 basis points and the interest paid on margin is the federal funds rate minus 20 basis points, then the funding cost (or benefit) is 30 basis points, not the 120 basis points calculated earlier.  

To explain why the average funding cost of the fed funds rate plus 100 basis points should not be used, Hull and White (2012) use two arguments. The first argument is. that there is a gain to the bank from the 100 basis points credit spread because it might default on the debt it issues. This is similar to the DVA discussed earlier and is referred to as DVA2 by Hull and White. Because of this benefit, the bank does not have to pass. the funding cost on to the derivatives desk.9.  

For the second argument, suppose that the risk-free rate is. $2\%$ and the bank's funding cost is $3.5\%$ . If a project comes along that is risk-free and provides a return. of $3\%$ , should the bank undertake it? The answer is that the project should be undertaken. The appropriate discount rate for the project's cash flows is $2\%$ and the project has a positive present value when this discount rate is used. It is not correct to argue that the bank is funding itself at. $3.5\%$ and should therefore only undertake. projects earning more than $3.5\%$  

Consider what happens as the bank enters into projects that are risk-free (or nearly risk-free). Its funding costs should come down in such a way that the incremental costs of funding a risk-free project should be $2\%$ , not $3.5\%$ . To take an extreme example, suppose that the bank we are considering were to double in size by undertaking entirely risk-free projects. The bank's funding cost should change to $2.75\%$ (an average of $3.5\%$ for the old projects and $2\%$ for the new projects). If the average funding cost of $3.5\%$ is used as the required return for all projects, low-risk projects will tend to seem unattractive and high-risk projects will tend to seem attractive.  

Andersen et al. (2016) also question the use of average funding costs in calculating FVA. They consider the situation where debtholders do not anticipate the investment in margin that will be made by the bank and are pleasantly surprised because it leads to the bank becoming less risky.10 There is then a transfer of wealth from the shareholders to the debtholders.  

The XVA debate has an interesting analogy. In a first corporate finance course,. students learn how to calculate a weighted average cost of capital (WACC) for a. (nonfinancial) corporation and how the discount rate used for the expected cash flows of a capital investment project should be calculated. They learn that the discount rate should depend on the risk of the project, not how it is financed. For projects that are more risky than average, the discount rate should be higher than the WACC. For projects that are less risky than average, the discount rate should be lower than the WACC.  

But many companies use a single discount rate for all projects. This tends to make. risky projects more attractive than they should be and safe projects less attractive than they should be. With all else equal, the use of a single discount rate leads to companies becoming more risky over time..  

The XVA analogy is that many of a bank's investments that we are concerned with. when considering FVA and MVA are lower-than-average-risk investments. An investment in initial margin or variation margin is usually low risk compared with other things the bank does. As such, its marginal effect is to lower the average cost of the bank's funding.  

The difference between the views of some financial engineers and financial economists on FVA and MVA is that financial economists work with marginal funding costs while the financial engineers work with average costs. The essence of the debate can be summarized by the following imaginary dialogue:.  

Financial Economist: The cost you should use for funding a project should reflect the risk of the project. By using average funding costs you are assuming that all the bank's projects are equally risky. Financial Engineer: But tying up funds in initial margin or a low-risk hedged derivatives position prevents me from using the funds elsewhere. On average the bank gets a much higher return than it does on things like initial margin. There is a cost to lowrisk, low-return projects.   
Financial Economist: You talk as though funds for your business are in short supply. If you have good projects, whether they are low risk or high risk, the market will provide funding for you.. Financial Engineer: I am not sure that is how things work in practice.  
