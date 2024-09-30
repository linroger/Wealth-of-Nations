---
title: FORWARD LOANS
aliases: [FORWARD LOANS]
linter-yaml-title-alias: FORWARD LOANS
---

# FORWARD LOANS
## DEFINITION
- A **forward loan** is engineered like any forward contract,  except that what is being bought or sold is not a currency or commodity,  but instead,  a loan.
	 - At time$t_0$,  we write a contract that will settle at a future date$t_1$.
	 - At settlement,  the trader receives (delivers) a loan that matures at$t_2$.
## SPECIFICATIONS
- The contract will specify the interest rate that will apply to this loan.
	 - This interest rate is called the **forward rate** and will be denoted by$F(t_0,  t_1,  t_2)$.
- The forward rate is determined at$t_0$.
- $T_1$is the start date of the future loan.
- $T_2$is the date at which the loan matures.
## EXAMPLE
- We write a contract at$t_0$such that at a future date, $t_1$,  USD 100 are received; the principal and interest are paid at$t_2$
- The interest is$F_{t_0} \delta$,  where$\delta$is the day-count adjustment, $\frac{ACT}{360}$:$$\delta = \frac{t_2 - t_1}{360}$$
## APPLICATIONS

- Forward loans permit a great deal of flexibility in balance sheet,  tax,  and risk management. The need for forward loans arises under the following conditions:
	 - A business would like to lock in the "current" low borrowing rates from money markets.
	 - A bank would like to lock in the "current" high lending rates
	 - A business may face a floating-rate liability at time$t_1$. The business may want to hedge this liability by securing a future loan with a known cost.

## CASH FLOW DECOMPOSITION

- It is straightforward to see how forward loans help to accomplish these goals. With the forward loan of Figure 3.10,  the party has agreed to receive 100 dollars at$t_1$and to pay them back at$t_2$with interest.
- The key point is that the interest rate on this forward loan is fixed at time$t_0$.
- The forward rate$F(t_0,  t_1,  t_2)$"locks in" an unknown future variable at time$t_0$and thus eliminates the risk associated with the unknown rate.
- The$L_{t_1}$is the LIBOR interest rate for a$(t_2 - t_1)$period loan and can be observed only at the future date$t_1$.
- Fixing$F(t_0,  t_1,  t_2)$will eliminate the risk associated with$L_{t_1}$.

We begin with the cash flow diagram for the forward loan shown in Figure 3.11 a.

1. We detach the two cash flows into separate diagrams. Note that at this stage,  these cash flows cannot form tradeable contracts. Nobody would want to buy 3.11 c,  and everybody would want to have 3.11 b.
1. We need to transform these cash flows into tradeable contracts by adding compensating cash flows in each case.
	 - In Figure 3.11 b,  we add a negative cash flow,  preferably at time$t_0$. This is shown in Figure 3.11 d. Denote the size of the cash flow by -$C_{t_0}$.
	 - In Figure 3.11 c,  add a positive cash flow at time$t_0$,  to obtain Figure 3.11 e. The cash flow has size +$C_{t_0}$.
1. Make sure that the vertical addition of Figure 3.11 d and e will replicate what we started with in Figure 3.11 a. For this to be the case,  the two newly added cash flows have to be identical in absolute value but different in sign.
	 - A vertical addition of Figure 3.11 d and e will cancel any cash exchange at time$t_0$,  and this is exactly what is needed to duplicate Figure 3.11 a.
- At this point,  the cash flows of Figure 3.11 d and e need to be interpreted as specific financial contracts so that the components of the synthetic can be identified. There are many ways to do this. Depending on the interpretation,  the synthetic will be constructed using different assets.

# FORWARD RATE AGREEMENTS (FRAS)
- Suppose we write a contract that specifies a notional amount,  N,  the dates$t_1$and$t_2$,  and the “price”$F_{t_0}$,  with payoff$N(L_{t_1} - F_{t_0}) \delta$
- Thus,  the buyer of the FRA will pay fixed and receive floating.
- This instrument is a paid-in-arrears FRA. In an FRA contract,  the purchaser accepts the receipt of the following sum at time$t_2$:
- FRA contract specifies:
	 - Notional amount N
	 - Dates$t_1,  t_2$
	 - "Price"$F_{t_0}$
	 - Payoff is:$$N(L_{t_1} - F_{t_0})\delta$$
	 - Buyer pays fixed$F_{t_0}\delta N$
	 - Receives floating$L_{t_1}\delta N$
	- N is notional principal,  never exchanged
		- But needed to determine interest
- Paid-in-arrears:
		 -$L_{t_1}$is known at$t_1$
		 - Interest exchanged at$t_2$
	- Market-traded FRAs settle at$t_1$:
	- Receive$\frac{(L_{t_1} - F_{t_0})\delta N }{1 + L_{t_1}\delta}$if$L_{t_1} > F_{t_0}$
	- Pay$\frac{(F_{t_0} - L_{t_1})\delta N}{1 + L_{t_1}\delta}$if$L_{t_1} < F_{t_0}$
	- Settling at$t_1$reduces seller's credit risk
	- $F_{t_0}\delta N$is fair value of$L_{t_1}\delta N$at$t_0$
- The N represents a notional principal since the principal amount will never be exchanged. However,  it needs to be specified in order to determine the amount of interest to be exchanged.
- It is paid-in-arrears because the unknown interest, $L_{t_1}$,  will be known at time$t_1$,  the interest payments are exchanged at time$t_2$,  when the forward (fictitious) loan is due.
- In the case of market-traded FRA contracts,  there is one additional complication. The settlement is not done in-arrears at time$t_2$. Instead,  FRAs are settled at$t_1$,  and the transaction will involve the following discounted cash flows.
## DEFINITION OF THE FRA

![|500](Pasted%20image%2020240214003114.png)

If a client has the objective of locking in the future borrowing or lending costs using the portfolio in Eq. (3.37),  why not offer this to him or her in a single contract? This contract will involve only the exchange of two interest payments shown in Figure 3.14 c.

$$settlement~sum = \frac{(i_r - i_c) \times A \times \frac{DAYS}{BASIS}}{1 + (i_r \times \frac{DAYS}{BASIS})}$$

Where:

- $i_r$is the reference interest rate
- $i_c$is the contract interest rate
- A is the contract amount
- DAYS is the number of days in the contract period
- BASIS is the day count convention (e.g. 360 for dollars,  365 for sterling)
- Settling at$t_1$instead of$t_2$has one subtle advantage for the FRA seller,  which is often a bank.
- If during$[t_0,  t_1]$the interest rate has moved in favor of the bank,  time$t_1$settlement will reduce the marginal credit risk associated with the payoff.
	- The bank can then operate with a lower credit line.
- Note one important interpretation. An FRA contract can be visualized as an exchange of two interest payments.
- The purchaser of the FRA will be paying the known interest$F_{t_0} \delta N$and is accepting the (unknown) amount$L_{t_1} \delta N$.
- Depending on which one is greater,  the settlement will be a receipt or a payment.
- The sum$F_{t_0} \delta N$can be considered,  as of time$t_0$,  as the fair payment market participants are willing to make against the random and unknown$L_{t_{1}} δN$﻿. It can be regarded as the time to "market value" of$L_{t_{1}} δN$
- - It is clear from the construction in Figure 3.14 that the FRA contract eliminates the credit risk associated with the principals--since the two N's will cancel out--but leaves behind the exchange of interest rate risk.

### FRA CONTRACTS AND EUROCURRENCY FUTURES CONTRACTS

- **FRA Contracts**: Involves exchanges of interest payments associated with a floating and a fixed-rate loan.
- **Eurocurrency [Teaching Note 2-Futures Contracts](Teaching%20Note%202-Futures%20Contracts.md)**: Trade future loans indirectly and result only in an exchange of interest rate payments,  but with some differences from FRA contracts.
- **Trading Homogenized Contracts**: Eurocurrency futures trade the forward loans (deposits) as homogenized contracts.
- **Deposit Lock**: The buyer locks in a future deposit rate but does not deliver the deposit itself.
- **Cash Settlement**: At expiration date$t_1$,  the contract is cash settled.
- **Price Denotation**: The price of the futures contract quoted in the market is denoted by$Q_{t_0}$.
### UNDERSTANDING THE EURODOLLAR CONTRACT

The buyer of a 3-month Eurodollar contract “promises” to deposit $100(1 − \tilde{F}_{t_0} + \frac{1}{4})$ dollars at expiration date $t_1$ and receive $100$ in $3$ months. The implied annual interest rate on this loan is then calculated by a specific formula.

- **Price Quotations and Forward Rates**: The price quotations are related to forward rates through a specific formula.
- **Interest Rate Convention**: The interest rate convention for forward loans is equivalent to a money market yield.
- **Futures Contracts**: Use a convention similar to discount rates to calculate the time$t_1$value of the forward loan.

### EXAMPLE: INTERBANK MONEY MARKET LOAN

Consider the interbank money market loan as shown in Figure 4.1.

- **Loan Principal**:$100$,  paid at time$t_1$.
- **Interest and Principal Reception**: At$t_2$.
- **Interest Rate**: LIBOR rate$L_{t_1}$,  observed at time$t_1$.
- **Forward Contract**:$100$is borrowed at$t_1$,  and the prevailing interest rate is paid at that time.

Mathematically,

- The$t_2$cash flows are given by:$$100 + 100L_{t_{1}\delta}\tag{(4.1)}$$
- Discounting this value to time$t_1$:$$\frac{100(1 + L_{t_1}\delta)}{1 + L_{t_1}\delta} = 100$$
- Total value of the cash flows generated by the forward loan contract: Exactly zero for all times$t$during the interval$[t_0,  t_1]$.

So in summary:

- FRA contracts allow locking in interest rates on a notional loan amount.
- Eurocurrency futures also trade interest rates but have some differences from FRAs.
- Futures contracts imply interest rates using price quotations and specific formulas.
- The total value of a forward loan is zero between contract initiation and settlement.