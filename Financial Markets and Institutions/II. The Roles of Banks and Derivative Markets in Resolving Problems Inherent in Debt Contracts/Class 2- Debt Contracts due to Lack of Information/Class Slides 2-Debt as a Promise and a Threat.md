---
title: Class Slides 2-Debt as a Promise and a Threat
tags:
  - borrower_lender
  - debt_contract
  - financial_contract
  - free_cash_flow
  - liquidation
aliases:
  - Borrower Payoff
  - Class 2 Slides
  - Debt as Threat
  - Equity Contract
key_concepts:
  - Borrower needs capital
  - Debt face value
  - Equity profit sharing
  - Lender imposes penalty
  - Liquidation as penalty
  - Optimal financial contract
  - Risk neutral parties
---

# Class Slides 2-Debt as a Promise and a Threat

[Class Note 2-Debt Contracts Due to the Lack of Information: Debt as a Promise and a Threat](Class%20Note%202-Debt%20Contracts%20Due%20to%20the%20Lack%20of%20Information%20Debt%20as%20a%20Promise%20and%20a%20Threat.md)

## An Extreme Free Cash Flow Problem

Consider a borrower who needs to raise a large quantity of capital.

- All lenders and borrowers are risk neutral.
 - The borrower has no capital and needs to raise 1 (\$1 million).
- Outside investors do not observe the borrower's operations directly,  not even its sales or cash flows.

### How can the borrower be made to pay some of the cash?

How can the lenders write a contract where they do not need to monitor the information about actual cash flow?

Detailed Example:

- The firm needs to raise 1 (\$1 million)) and investors require an expected return of r=5%.
- An expected repayment of 1.05.

#### Future Cash Flow is uncertain,  all know the probabilities
- Actual final cash flow not observed by lenders,  who observe only the amount repaid.
 ![500](https://storage.simpletex.cn/view/fF7ryLCbuVsNVL1G51SMGsNTy4Xycp7iH)

#### A simple candidate for a financial contract is equity
- An equity contract in this context is a profit-sharing agreement,  where the profit shared depends on the profits reported by the borrower.
- Much more detailed than public equity,  where there is no obligation to pay any dividends,  but similar in spirit (as we will see).

##### Equity: Pay a fraction “a" of reported cash flow (or profits) P
- A fraction of "a" of reported cash flow (or,  equivalently,  profits) goes to the outside investor,  while the borrower retains the fraction 1-a,  plus any under reported cash flow.

###### Actual cash=V ,  reported cash=Z
- Suppose that the borrower's contract is just to pay a fraction of reported profits,  Z,  with no other details or penalties specified.
- Borrower Payoff = Va (Z)
- Poll: How much would you report (Z),  if V=1.4 and a=0.5?

###### Report as little as possible
 - If a>0,  this is strictly decreasing in Z! Report as little as possible!
- Supposing that the borrower can't make the lender take a share of a reported loss (by reporting Z<0),  the borrower will report Z=0.
- Even if the lender knew the value of V,  when the borrower obtains it first and controls it,  the borrower will not pay unless the borrower suffers a consequence of not paying.

##### What can the lender do if the borrower claims a low amount?
- The lender would like to impose a penalty for low payments to give incentives for higher payments.

##### Suppose there is a penalty
- Liquidate the project if the borrower pays too little,  preventing the borrower from absconding with it
- Impose a non-monetary penalty on the borrower.
 -In ancient history,  the non-monetary penalties were very common,  i.e.,  debtors' prisons and physical penalties

#### Bankruptcy or liquidation as penalty
- I assume that liquidating the firm's assets gives no proceeds to the lender or to the borrower (zero to each).
Liquidation is useful as a penalty that a borrower can avoid by paying the debt,  but regular liquidation is not a good way to run a firm

##### When to Liquidate?
- How does one specify an optimal financial contract between investor and borrower?
- This means choosing when to liquidate (to penalize the borrower) and when to not liquidate,  as a function of the payment made.

###### Lets see how to use liquidation
- If liquidate the payoff of (borrower,  lender)= (0,  0)
- For payment without liquidation,  the payoff of (borrower,  lender) is: (V-payment,  payment)

##### A list of payments (Equity,  a),  V=1.4

<table>
	<tbody>
		<tr>
			<th>Payment</th>
			<th>Liquidate $(Y,  \mathbb{N})$</th>
			<th>(Borrower,  Lender)</th>
		</tr>
		<tr>
			<td>1.5</td>
			<td>$N$</td>
			<td>$1.4-a (1.5)$</td>
		</tr>
		<tr>
			<td>1.4</td>
			<td>$N$</td>
			<td>1.4-a (1.4)</td>
		</tr>
		<tr>
			<td>1.3125</td>
			<td>$N$</td>
			<td>$1.4-a (1.3125)$</td>
		</tr>
		<tr>
			<td>1</td>
			<td>$N$</td>
			<td>1.4-a (1)</td>
		</tr>
		<tr>
			<td>0.75</td>
			<td>$N$</td>
			<td>$1.4-a (0.75)$</td>
		</tr>
		<tr>
			<td>0.5</td>
			<td>$N$</td>
			<td>$1.4-a (0.5)$</td>
		</tr>
		<tr>
			<td>0.25</td>
			<td>$N$</td>
			<td>$1.4-a (0.25)$</td>
		</tr>
		<tr>
			<td>0</td>
			<td>$N$</td>
			<td>1.4</td>
		</tr>
	</tbody>
</table>

A list of payments

<table>
	<tbody>
		<tr>
			<th>Payment</th>
			<th>Liquidate $(Y,  \mathbb{N})$</th>
			<th>(Borrower,  Lender)</th>
		</tr>
		<tr>
			<td>1.5</td>
			<td>$N$</td>
			<td> </td>
		</tr>
		<tr>
			<td>1.4</td>
			<td>$N$</td>
			<td> </td>
		</tr>
		<tr>
			<td>1.3125</td>
			<td>$N$</td>
			<td> </td>
		</tr>
		<tr>
			<td>1</td>
			<td>$N$</td>
			<td> </td>
		</tr>
		<tr>
			<td>0.75</td>
			<td>$N$</td>
			<td> </td>
		</tr>
		<tr>
			<td>0.5</td>
			<td>$Y$</td>
			<td> </td>
		</tr>
		<tr>
			<td>0.25</td>
			<td>$Y$</td>
			<td> </td>
		</tr>
		<tr>
			<td>0</td>
			<td>$Y$</td>
			<td>(Poll)</td>
		</tr>
	</tbody>
</table>

### A list of payments Debt face F=1.3

<table>
	<tbody>
		<tr>
			<th>Payment</th>
			<th>Liquidate $(Y,  \mathbb{N})$</th>
			<th>(Borrower,  Lender)</th>
		</tr>
		<tr>
			<td>1.5</td>
			<td>$N$</td>
			<td> </td>
		</tr>
		<tr>
			<td>1.4</td>
			<td>$N$</td>
			<td> </td>
		</tr>
		<tr>
			<td>1.3125</td>
			<td>$N$</td>
			<td> </td>
		</tr>
		<tr>
			<td>$1.3=F ($face)</td>
			<td>$N$</td>
			<td> </td>
		</tr>
		<tr>
			<td>0.75</td>
			<td>$Y$</td>
			<td> </td>
		</tr>
		<tr>
			<td>0.5</td>
			<td>$Y$</td>
			<td> </td>
		</tr>
		<tr>
			<td>0.25</td>
			<td>$Y$</td>
			<td> </td>
		</tr>
		<tr>
			<td>0</td>
			<td>$Y$</td>
			<td>(Poll if V=1.4)</td>
		</tr>
	</tbody>
</table>

A list of payments

<table>
	<tbody>
		<tr>
			<th>Payment</th>
			<th>Liquidate $(Y,  \mathbb{N})$</th>
			<th>(Borrower,  Lender)</th>
		</tr>
		<tr>
			<td>1.5</td>
			<td>$N$</td>
			<td> </td>
		</tr>
		<tr>
			<td>1.4</td>
			<td>$N$</td>
			<td> </td>
		</tr>
		<tr>
			<td>$1.3125=F$</td>
			<td>$N$</td>
			<td> </td>
		</tr>
		<tr>
			<td>1.3</td>
			<td>$Y$</td>
			<td> </td>
		</tr>
		<tr>
			<td>0.75</td>
			<td>$Y$</td>
			<td> </td>
		</tr>
		<tr>
			<td>0.5</td>
			<td>$Y$</td>
			<td> </td>
		</tr>
		<tr>
			<td>0.25</td>
			<td>$Y$</td>
			<td> </td>
		</tr>
		<tr>
			<td>0</td>
			<td>$Y$</td>
			<td>(Poll)</td>
		</tr>
	</tbody>
</table>

### Let "F" be the face value of a debt contract
- If the borrower pays F or more,  the lender has no right to liquidate.
- If less than f is made,  liquidation is contractually forced and happens automatically
- If F >1,  then there will be liquidation with probability at least 0.2 (the probability that V=1).

### Future Cash Flow is uncertain,  all know the probabilities
- Actual cash flow not observed by lenders,  who observe only the amount repaid.
 ![500](https://storage.simpletex.cn/view/feiDa8AcVE5YB1M4Zvzp7nvtz41LX9cEr)
- Borrower & lender get 0
- The lender's Expected Return must be at least 1.05
- Actual cash flow not observed by lenders,  who observe only the amount repaid.
 ![500](https://storage.simpletex.cn/view/feRkEB4EDhNBagQ1Whc2sDpm7NgNWbfM4)
- 0.8 F + 0.2 (0) ≥1.05
- $$F\geq1.05/0.8=1.3125$$

## Debt does not require monitoring just proof of payment or default
- When outside investors cannot observe the cash flows and cannot monitor the business,  equity contracts do not work. Enforcing them requires excessively costly monitoring.
- Debt is simpler induces the borrower to pay investors because default serves as a penalty that the borrower seeks to avoid.

## Extend this to Loan Covenants
- This applies not only to defaults on principal and interest covenants,  but to any other covenant that depends on hard-to-observe information.
- When it too costly for lenders to collect the information to enforce or renegotiate other detailed covenants,  then [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] that "mean what they say" (and involve a default when violated) must be used.

#### Don't renegotiate if you can't monitor
- Why not?
- How does this relate to the US Federal Trust Indenture Act?
- Debt contracts can be improved by costly monitoring

##### Debt contracts can be improved by costly monitoring
- What would you do if you could monitor the true cash flow,  V?

###### Renegotiation
- Instead of always or never accepting 1 in lieu of liquidation,  the lender who monitors the firm's cash flow can accept 1 when V=1 and reject it when V=1.4.
- This saves 0.2 (\$1 M) = \$0.2 M.
- If this monitoring cost \$200 (\$. 002 M),  it would certainty be worth doing.

##### A single lender would monitor
- Monitoring of the exact value of the borrower's project costs 0.002 ($200). If there is a single lender lending his or her own funds,  that lender would monitor because the cost,  0. O 02,  is less than the saving from monitoring,  0.\1.

##### Duplication of effort
- With many small investors in a publicly traded bond,  the total cost of having each of them monitor may exceed the benefits.
- We examine this in Class Note 3.

Tags: #debt #financial_contracts #liquidation #borrowing #lending #risk_management #covenants #monitoring #bankruptcy