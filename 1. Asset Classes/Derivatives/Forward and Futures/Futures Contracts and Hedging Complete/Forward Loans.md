---
title: FORWARD LOANS
aliases: [FORWARD LOANS]
linter-yaml-title-alias: FORWARD LOANS
---

# FORWARD LOANS
### DEFINITION
- A **forward loan** is engineered like any forward contract, except that what is being bought or sold is not a currency or commodity, but instead, a loan.
- A. t time t_0, we write a contract that will settle at a future date t_1.
- At settlement, the trader receives (delivers) a loan that matures at t_2.
### SPECIFICATIONS
- The contract will specify the interest rate that will apply to this loan.
- This interest rate is called the **forward rate** and will be denoted by$F(t_0, t_1, t_2)$﻿.
- The forward rate is determined at t_0.
- T_1 is the start date of the future loan.
- T_2 is the date at which the loan matures.
### EXAMPLE
- We write a contract at t_0 such that at a future date, t_1, USD 100 are received; the principal and interest are paid at t_2.
- The interest is F_{t_0} \delta, where \delta is the day-count adjustment,$\frac{ACT}{360}$﻿:
$\delta = \frac{t_2 - t_1}{360}$﻿
### APPLICATIONS
- Forward loans permit a great deal of flexibility in balance sheet, tax, and risk management. The need for forward loans arises under the following conditions:
- A business would like to lock in the "current" low borrowing rates from money markets.
- A bank would like to lock in the "current" high lending rates
- A business may face a floating-rate liability at time t_1. The business may want to hedge this liability by securing a future loan with a known cost.
### CASH FLOW DECOMPOSITION
- It is straightforward to see how forward loans help to accomplish these goals. With the forward loan of Figure 3.10, the party has agreed to receive 100 dollars at t_1 and to pay them back at t_2 with interest.
- The key point is that the interest rate on this forward loan is fixed at time t_0.
- The forward rate$F(t_0, t_1, t_2)$﻿ "locks in" an unknown future variable at time t_0 and thus eliminates the risk associated with the unknown rate.
- The$L_{t_1}$﻿ is the LIBOR interest rate for a$(t_2 - t_1)$﻿ period loan and can be observed only at the future date t_1.
- Fixing$F(t_0, t_1, t_2)$﻿ will eliminate the risk associated with$L_{t_1}$﻿.
- We begin with the cash flow diagram for the forward loan shown in Figure 3.11 a.
1. We detach the two cash flows into separate diagrams. Note that at this stage, these cash flows cannot form tradeable contracts. Nobody would want to buy 3.11 c, and everybody would want to have 3.11 b.
2. We need to transform these cash flows into tradeable contracts by adding compensating cash flows in each case.
- In Figure 3.11 b, we add a negative cash flow, preferably at time$t_0$﻿. This is shown in Figure 3.11 d. Denote the size of the cash flow by -$C_{t_0}$﻿.
- In Figure 3.11 c, add a positive cash flow at time t_0, to obtain Figure 3.11 e. The cash flow has size +$C_{t_0}$﻿.
3. Make sure that the vertical addition of Figure 3.11 d and e will replicate what we started with in Figure 3.11 a. For this to be the case, the two newly added cash flows have to be identical in absolute value but different in sign.
- A vertical addition of Figure 3.11 d and e will cancel any cash exchange at time t_0, and this is exactly what is needed to duplicate Figure 3.11 a.
- At this point, the cash flows of Figure 3.11 d and e need to be interpreted as specific financial contracts so that the components of the synthetic can be identified. There are many ways to do this. Depending on the interpretation, the synthetic will be constructed using different assets.
---
## REPLICATION OF A FORWARD LOAN USING BONDS

![|500](for.png)
![|500](for1.png)

## SYNTHETIC USING BOND MARKET REPLICATION
- As usual, we assume credit risk away. A first synthetic can be obtained using bond and T-bill markets.
- Although this is not the way preferred by practitioners, we will see that the logic is fundamental to financial engineering.
- Suppose default-free pure discount bonds of specific maturities denoted by$\{B (t_0, t_i), i = 1,…, n\}$﻿trade actively.
- They have par value of 100.
- Then, within the context of a pure discount bond market, we can interpret the cash flows in Figure 3.11 d as a long position in the t_1 -maturity discount bond.
- The trader is paying$C_{t_0}$﻿ at time t_0 and receiving 100 at t_1.
- This means that$B(t_0,t_1) = C_{t_0}$﻿
- Hence, the value of$C_{t_0}$﻿ can be determined if the bond price is known.
- The synthetic for the forward loan will be fully described once we put a label on the cash flows in Figure 3.11 e.
- What do these cash flows represent? These cash flows look like an appropriate short position in a t_2 -maturity discount bond.
- Does this mean we need to short one unit of the$B(t_0,t_2)$﻿? The answer is no, since the time t_0 cash flow in Figure 3.11 e has to equal C_{t_0}.
- However, we know that a t_2 -maturity bond will necessarily be cheaper than a t_1 -maturity discount bond.
$B(t_0,t_2) < B(t_0,t_1) = C_{t_0}$
- Thus, shorting one t_2 -maturity discount bond will not generate sufficient time t_0 funding for the position in Figure 3.11 d.
- The problem can easily be resolved, however, by shorting not one but \lambda bonds such that:
$\lambda B(t_0,t_2) = C_{t_0}$
- But we already know that$B (t_0, t_1) = C_{t_0}$﻿. So the$\lambda$﻿ can be determined easily:
$\lambda = \frac{B(t_0,t_1)}{B(t_0,t_2)}$﻿
- According to Eq. (3.3) \lambda will be greater than one.
- This particular short position will generate enough cash for the long position in the t_1 -maturity bond.
- Thus, we finalized the first synthetic for the forward loan:
- Buy one t_1 -discount bond;
- Short$\frac{B (t_0, t_1)}{B (t_0, t_2)}$﻿units of the t_2 -discount bond
- To double-check this result, we add Figure 3.11 d and e vertically and recover the original cash flow for the forward loan in Figure 3.11 a.
---
## PRICING USING THE BOND MARKET SYNTHETIC
- If markets are liquid and there are no other transaction costs, arbitrage activity will make sure that the cash flows from the forward loan and from the replicating portfolio (synthetic) are the same.
- In other words, the sizes of the time t_2 cash flows in Figure 3.11 a and e should be equal.
- This implies that:
$$1+F(t_0,t_1,t_2)\delta = \frac{B(t_0,t_1)}{B(t_0,t_2)}$$
Where the \delta is, as usual, the day-count adjustment.
- This arbitrage relationship is of fundamental importance in financial engineering.
- Given liquid bond prices$\{B(t_0,t_1), B(t_0,t_1)\}$﻿, we can price the forward loan off the bond markets using this equation.
- More important, equality (3.23) shows that there is a crucial relationship between forward rates at different maturities and discount bond prices.
- But discount bond prices are discounts which can be used in obtaining the present values of future cash flows.
- This means that forward rates are of primary importance in pricing and risk managing financial securities.
- Before we consider a second synthetic for the forward loan, we prefer to discuss how all this relates to the notion of arbitrage.
## ARBITRAGE ANALYSIS
1. What happens when$$1 + F_{t_0}\delta > \frac{B(t_0,t_1)}{B(t_0,t_2)}$$
	- This means that the forward rate$F_{t_0}$is higher than the implied forward rate from the bond prices$\frac{B (t_0, t_1)}{B (t_0, t_2)}$﻿.
	- The funding cost for the "synthetic" under this scenario is:
$$F_{t_0}^{*} = \frac{B(t_0,t_1)}{\delta B(t_0,t_2)} - \frac{1}{\delta}$$
	- This is the cost of funding the long position in the$t_1$bond and the short position in the$t_2$bond.
		- This implies that the market forward rate$F_{t_0}$is higher than the synthetic forward rate$F_{t_0}^{*}$﻿.
		- Therefore, it is cheaper to fund the forward loan position directly rather than synthetically replicating it.
1. To profit from this, a trader would:
	- Borrow$B(t_0, t_1)$at rate$F_{t_0}$
	- Lend$B(t_0, t_2)$at rate$F_{t_0}$
	- Pocket the difference in interest between the two rates
1. The costs and payoffs are:
	- Borrow$B (t_0, t_1)$﻿ at t_0, pay back$(1+F_{t_0}\delta) B (t_0, t_1)$﻿ at$t_1$
	- Lend$B (t_0, t_2)$﻿ at t_0, receive back$(1+F_{t_0}\delta) B (t_0, t_2)$﻿ at$t_2$
	- Interest cost =$F_{t_0}\delta B (t_0, t_1)$﻿
	- Interest earned =$F_{t_0}\delta B (t_0, t_2)$﻿
	- Net profit =$F_{t_0}\delta (B (t_0, t_2) - B (t_0, t_1))$﻿

2. Now let's analyze$$1 + F_{t_0}\delta < \frac{B (t_0, t_1)}{B (t_0, t_2)}$$﻿
	- This means the forward rate$F_{t_0}$is lower than the synthetic forward rate.
		- So it is cheaper to replicate the forward synthetically.
			- Go long 1$t_1$bond
			- Go short$\lambda = \frac{B (t_0, t_1)}{B (t_0, t_2)}$﻿$t_2$bonds
			- Fund the long position by shorting the$t_2$bonds
			- Receive$1+F_{t_0}\delta$at$t_1$on$t_1$bond
			- Pay$\lambda (1+F_{t_0}\delta)$at$t_2$on short$t_2$bonds
		- Net profit =$$(1+F_{t_0}\delta) B (t_0, t_1) - \lambda (1+F_{t_0})\delta) B (t_0, t_2) = F_{t_0}\delta (B (t_0, t_2) - B (t_0, t_1))$$
1. So in both cases, the trader can exploit the difference between the market forward rate and the synthetic forward rate for riskless arbitrage profit.
---
## MONEY MARKET SYNTHETIC
- Now assume that all maturities of deposits up to 1 year are quoted actively in the interbank money market.
- Also assume there are no arbitrage opportunities.
- Figure 3.12 shows how an alternative synthetic can be created.
- The cash flows of a forward loan are replicated in Figure 3.12 a.
- Figure 3.12 c shows a Euromarket loan.
- C_{t_0} is borrowed at the interbank rate L_{t_0}^2
- The time t_2 cash flow in Figure 3.12 c needs to be discounted using this rate. This gives:$$C_{ t_0}=\frac{100\left (1+F_{t} \delta\right)}{\left (1+L_{t_{0}}^{2} \delta^{2}\right)}$$Where
$$\delta_{1}=\frac{t_{1}-t_{0}}{360}$$
## PRICING THE MONEY MARKET SYNTHETIC
- We can obtain another pricing equation using the money market replication.
- In Figure 3.12, if the credit risks are the same, the cash flows at time t_2 would be equal, as implied by Eq. (3.27).
- This can be written as:
$(1+F_{t_0}\delta) 100 = c_t (1+L_{t_0\rightarrow t_1}\delta_{t_1\rightarrow t_2})$
Where
$\delta_{t_1\rightarrow t_2} = \frac{t_2-t_1}{360}$
- We can substitute further from formula (3.28) to get the final pricing formula:
$\frac{100 (1+L_{t\rightarrow t_2}\delta_{t_0\rightarrow t_2})}{1+L_{t_0\rightarrow t_1}\delta_{t_0\rightarrow t_1}}$
---
## CONTRACTUAL EQUATIONS

Using the bond market replication, we obtain
![](contrsct.jpeg)

- The expression shown in formula (3.32) is a contractual equation. The left-hand-side contract leads to the same cash flows generated jointly by the contracts on the right-hand side.
- Essentially the equation says that the risk and cash flow attributes of the two sides are the same. If there is no credit risk, no transaction costs, and if the markets in all the involved instruments are liquid, we expect that arbitrage will make the values of the two sides of the contractual equation equal.
- If we use the money markets to construct the synthetic, the contractual equation above becomes
### CREATING A SYNTHETIC BOND
- Suppose a trader would like to buy a t_1-maturity bond at time t_0. The trader also wants this bond to be liquid. Unfortunately, he discovers that the only bond that is liquid is an on-the-run Treasury with a longer maturity of t_2. All other bonds are off-the-run. How can the trader create the liquid short-term bond synthetically assuming that all bonds are of discount type and that, contrary to reality, forward loans are liquid?
- A t 1-maturity bond can be constructed synthetically by arranging a forward loan from t_1 to t_2 and then by going long$\frac{B (t_0, t_1)}{B (t_0, t_2)}$﻿ units of the bond with maturity t_2.
- The resulting cash flows would be identical to those of a short bond. More important, if the forward loan and the long bond are liquid, then the synthetic will be more liquid than any existing off-the-run bonds with maturity$t_1$.

$$B (t_0, t_2)<B (t_0, t_1)= C_{t_0}$$
![|500](sb.png)
![|500](sb2.png)
Thus, shorting one t 2-maturity discount bond will not generate sufficient time t 0 funding for the position in Figure 3.11 d. The problem can easily be resolved, however, by shorting not one but λ bonds such that $λ B (t_0, t_2) = C_{t_0}$
But we already know that $B (t_0, t_1)= C_{t_0}$﻿ . So the λ can be determined easily: λ 5 Bðt 0; t 1Þ Bðt 0; t 2Þ (3.21) According to Eq. (3.3) λ will be greater than one. This particular short position will generate enough cash for the long position in the t 1-maturity bond. Thus, we finalized the first synthetic for the forward loan: Buy one t 1-discount bond; short Bðt 0; t 1Þ Bðt 0; t 2Þ units of the t 2-discount bond (3.22) To double-check this result, we add Figure 3.11 d and e vertically and recover the original cash flow for the forward loan in Figure 3.11 a
$$\lambda B\left (t_{0}, t_{1}\right)=C_{t_{0}}\lambda B\left (t_{0}, t_{2}\right)=B\left (t_{0}, t_{1}\right) \rightarrow \lambda=\frac{B\left (t_{0}, t_{1}\right)}{B\left (t_{0}, t_{2}\right)}$$

### PRICING

If markets are liquid and there are no other transaction costs, arbitrage activity will make sure that the cash flows from the forward loan and from the replicating portfolio (synthetic) are the same. In other words, the sizes of the time t 2 cash flows in Figure 3.11 a and e should be equal. This implies that $$1+F\left(t_{0}, t_{1}, t_{2}\right) \delta=\frac{B\left(t_{0}, t_{1}\right)}{B\left(t_{0}, t_{2}\right)}\tag{3.23}$$

Where the δ is, as usual, the day-count adjustment.

- This arbitrage relationship is of fundamental importance in financial engineering.
- Given liquid bond prices${B (t_{0}, t_{1})}$, we can price the forward loan off the bond markets using this equation. More important, equality (3.23) shows that there is a crucial relationship between forward rates at different maturities and discount bond prices.
- But discount bond prices are discounts which can be used in obtaining the present values of future cash flows.
- This means that forward rates are of primary importance in pricing and risk managing financial securities.

## FORWARD LOAN

- A forward loan is engineered like any forward contract, except that what is being bought or sold is not a currency or commodity, but instead, a loan. At time t 0, we write a contract that will settle at a future date t 1. At settlement, the trader receives (delivers) a loan that matures at t 2,

|  |  |  |  |
| ---- | ---- | ---- | ---- |
| Table 17.1 Forward Contracts and Their Cash Flows |  | Cash Flows from a Forward Contract |  |
| Date | Forward Price | Cash (Spot) Price | Cash Flows |
| T | 140.00 | 138.00 |  |
| t+ 1 | 141.50 | 139.50 |  |
| t+ 2 | 142.50 | 140.00 |  |
| s= t+3 | 141.50 | 141.50 | 141.50 — 140.00 = 1.50 |