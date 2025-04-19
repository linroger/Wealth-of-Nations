---
cssclasses:
  - academia
linter-yaml-title-alias: 'Class Note 2 Debt Contracts Due to the Lack of Information:
  Debt as a Promise and a Threat'
title: Class Note 2Debt Contracts Due to the Lack of Information Debt as a Promise
  and a Threat
tags:
  - borrower_lender
  - debt_contracts
  - information_asymmetry
  - liquidation
  - monitoring_costs
  - renegotiation
aliases:
  - Borrower's Dilemma
  - Debt as Promise
  - Debt as Threat
key_concepts:
  - Borrower's profitable project
  - Borrower's underreported cash
  - Debt in corporate control
  - Lender's monitoring cost
  - Lenders write a contract
---

# Class Note 2Debt Contracts Due to the Lack of Information Debt as a Promise and a Threat

[Class Notes 2 – Corporate Bond Contracts](Class%20Notes%202%20–%20Corporate%20Bond%20Contracts.md)

[Class Slides 2-Debt as a Promise and a Threat](Class%20Slides%202-Debt%20as%20a%20Promise%20and%20a%20Threat.md)

[Discussion of Loan [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] vs. Bond Covenants](Discussion%20of%20Loan%20Covenants%20vs.%20Bond%20Covenants.md)

   This is our initial view of the role of debt in corporate control. This is simple but abstract.

   This will not be our only view of this issue.

   - Consider a borrower who needs to raise a large quantity of capital.
	  - All lenders and borrowers are risk neutral.
	  - The borrower has no capital and needs to raise $1 (\$1 million).
   - Outside investors do not observe the borrower's operations directly,  not even its sales or cash flows.
	  - How can the lenders write a contract where they do not need to monitor this information?
	  - The firm needs to raise $1 (\$1 million),  and investors require an expected return of $r=5\%$.
		 - What is the best financial contract without monitoring?
   - All lenders and the borrower agree that the borrower has a profitable (positive net present value) project to fund.
	  - However,  only the **borrower will observe how profitable it** turns out to be.
		 - The borrower can consume any part of the project's return that he does not pay out to the investor.
		 - The interpretation is that the borrower can appropriate the return to himself,  since no one else observes how successful the project is.
			- If the project is a retail store,  the borrower can take some sales in cash to himself.
			- More generally,  the borrower can inflate costs.
		 - The net cash flows to the firm are very unobservable in practice for many firms.
		 - In addition,  most other conflicts of interest faced by borrowers can be reinterpreted as equivalent to the borrower's ability to retain underreported cash.
			- The ability to retain underreported cash is simply the most extreme example of a conflict of interest.
   - The project costs $1 to fund,              and its realized value is a random variable with realization denoted by $V$.
	  - The distribution of $V$,  the value of the project,  known to all borrowers and lenders is:
		 - $H=1.4$ million with probability $P=0.8$
		 - $L=1$ million with probability $1−P=0.2$.
   - A simple candidate for a financial contract is equity.
	  - An equity contract in this context is a profit-sharing agreement,  where the profit shared depends on the profits reported by the borrower.
	  - Let the fraction of reported profits that goes to the outside investor be $a$,  while the borrower retains the fraction $1-a$,  plus any underreported profits.
		 - Suppose that the borrower's contract is just to pay a fraction of reported profits,  with no other details or penalties specified.
		 - The borrower's payoff given the true value of $V$ and the reported value,  denoted by $Z$,  is $V − aZ$.
   - What profit will the borrower report if he is supposed to pay out a fraction of it?
	  - The borrower will choose the smallest value of $Z$.
	  - Supposing that the borrower can't make the lender take a share of a reported loss (by reporting $Z<0$),  the borrower will report $Z=0$.
   - No matter what is the true value of $V$,  the most profitable choice for the borrower is to pay the lowest possible value.
	  - If there is no cost to the borrower of understating the amount,  the borrower always does.
	  - Even if the lender knew the value of $V$,  if the borrower obtains it first and thus controls it,  the lender will not be paid unless the borrower suffers some consequence of not paying.

### What Can the Lender Do If the Borrower Claims a Low Amount?

   - The lender would like to impose a penalty for low payments to give incentives for higher payments.
	  - There are two interpretations:
		 - The lender can *liquidate* the project if the borrower pays too little,  preventing the borrower from absconding with it,  or
		 - The lender can impose a nonmonetary *penalty* on the borrower.
			- Bankruptcy in the world is some combination of these two effects.
			- In ancient history,  the non-monetary penalties were very common,  i.e.,  debtors' prisons and physical penalties.
			- Such sanctions are now illegal,  but the loss of reputation of a borrower of a bankrupt firm is similar.

### Bankruptcy,  Liquidation,  and the Optimal Liquidation Policy

   - Suppose that it is not possible to impose a penalty on the borrower or take other assets outside the business that are valued by the borrower.
   - The only sanction available to give the borrower an incentive to pay is liquidation of the borrower's assets.
	  - To focus on the inefficiency of disrupting firm operations,  I assume that liquidating the firm's assets gives no proceeds to the lender or to the borrower.
	  - Liquidation and [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] are useful as a penalty that a borrower can avoid by paying the debt,  but regular liquidation is not a good way to run a firm.
   - How does one specify an optimal financial contract between investor and borrower when one can decide to liquidate (to penalize the borrower) or not contingent on any payment?
	  - Liquidation is best used as a payment-contingent penalty in the following way.
		 - If the lender is ever to liquidate for a given payment,  he also should liquidate for all lower payments.
		 - Suppose instead that the lender does not liquidate if $1$ is paid,  but will liquidate for some higher payment.
			- Then,  whenever the borrower has at least $1$,  he will avoid liquidation by paying $1$,  and keep the remainder for himself.
			- This makes the threat to liquidate given higher payments meaningless because the payment will never exceed $1$.
   - The borrower will pay the lowest amount that avoids liquidation,  and keep the rest for himself.
	  - The only exception is if the borrower has insufficient funds to pay that amount.
	  - **This** implies a description of the optimal financial contract without monitoring:
		 - select a payment,  $f$,  that,  if paid,  liquidation is avoided.
		 - The lender then liquidates for all lower payments.
		 - This implies that the optimal contract when monitoring is impossible is a debt contract with face $f$.
			- Face value includes the promised payment of principal and interest.

### Determination of the Face Value of Non-Monitored Debt

   - This section determines the minimum face value,  $f$,  of non-monitored debt which will lead to payments with an expected return of $5\%$ on a loan of $1$ (\$1 million),  or an expected value of $1.05$.
	  - Any face value below $L=1$ will always be repaid,  but this will not deliver an expected repayment of $1.05$.
	  - To make this very clear,  here is what $f=1$ would lead to.
   - Suppose $f=\$1$.
	  - When $V=1$,  the borrower pays $1$ (paying less would result in liquidation).
	  - The borrower gets $0$,  which is as much as if he paid any lower amount.
	  - When $V=1.4$,  the borrower pays $1$ (to avoid liquidation),  and keeps $1.4-1=0.4$ for himself.
		 - This implies that with face value of $1$,  the lender gets $1$ for sure,  which is less than $1.05$ and not acceptable.
   - Any face value of debt between $1$ and $1.4$ will force the borrower into liquidation when the project returns $1$,  but will be paid in full when the project returns $1.4$.
	  - This will give the lender an expected return of $0.8F$,  because nothing is received when there is liquidation.
	  - Solving $0.8F=1.05$ yields $F=1.3125$.
		 - Non-monitored debt with that face value works as follows.
   - Suppose $f=1.3125$.
	  - When $V=1$,  the borrower pays less than $1.3125$ and the asset is liquidated.
	  - The borrower gets $0$ for any payment less than or equal to $1$.
		 - The best interpretation is that the borrower then chooses to pay $0$,  because this is the best choice when the borrower can keep any positive fraction of the retained cash.
		 - The lender receives $0$.
			- This occurs with probability $0.2$.
	  - When $V=1.4$ the borrower pays $1.3125$,  avoids liquidation,  and keeps $1.4-1.3125=0.0875$ for himself.
		 - This is more than he could get from any smaller payment: any smaller payment gives $0$.
		 - The payment $1.3125$ is received with probability $0.8$.
		 - Liquidation is only avoided when $V=H$ and the face of $1.3125$ is paid.
			- The lender receives $1.3125$ with probability $0.8$ and zero with probability $0.2$,  which is an expected payment of $0.8(1.3125)=1.05$.
			- Any lower face value will give the lender an expected rate of return below $5\%$.
   - When outside investors cannot observe the cash flows and cannot monitor the business,  equity contracts do not work.
	  - Enforcing them requires excessively costly monitoring.
	  - If this monitoring (sitting on the board of directors,  or keeping close tabs on the business in other ways) is too costly,  then simple financial contracts that do not require monitoring are best.
		 - These are debt contracts.
		 - They induce the borrower to pay investors because default serves as a penalty that the borrower seeks to avoid.
   - The analysis can be extended to apply not only to defaults on principal and interest [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] of debt contracts,  but to any other covenant that depends on hard-to-observe information.
	  - When it is too costly for lenders to collect the information to enforce or renegotiate other detailed covenants,  then [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] that "mean what they say" (and involve a default when violated) must be used.
   - A publicly-traded bond with many lenders needs to have easy to enforce covenants.
	  - If it is costly to monitor and enforce detailed loan covenants,  then bond [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] will be based on easily observed information.
		 - Because the public will not have better information,  these [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] will not be renegotiated.
		 - This is especially true of the "key covenants" of principal,  interest,  and maturity.
	  - Public debt will be enforced by the threat of liquidation,  and liquidation will occur whenever there is a default.
		 - More generally,  we will later see that public debt is enforced by the threat of filing formal bankruptcy (which may not lead to liquidation).
		 - I will not yet add this complication.

### Debt Contracts Can Be Improved by Costly Monitoring
   - The next section shows the value of monitoring in allowing renegotiation of loan contracts.

#### The Value of Monitoring in Restructuring and Renegotiation of Debt

   - Suppose that it is possible for the lender to monitor the value of the borrower's operations.
	  - Then,  instead of liquidating when less than the face value of debt is paid,  the lender who monitors can instead use the threat of liquidation and offer to refrain from liquidation so long as the borrower repays as much as possible.
   - Instead of always or never accepting $1$ in lieu of liquidation,  the lender who monitors the firm's cash flow can accept $1$ when $V=1$ and reject it when $V=1.4$.
	  - The lender can use the extra information to allow beneficial renegotiation of loan contracts.
	  - This policy leads the borrower to pay $f$ when $V=1.4$ and $1$ when $V=1$.
	  - I assume that the lender has all of the bargaining power and can offer to accept less than $f$ only when $V=1$.
		 - The value of monitoring is the expected savings in financial distress costs,  which are equal to $0.2(1)=0.2$.
   - Monitoring of the exact value of the borrower's project costs $0.002$ (\$200).
	  - If there is a single lender lending his or her own funds,  that lender would monitor because the cost,  $0.002$,  is less than the saving from monitoring,  $0.2$.
   - The lender must commit the time to monitoring before observing the payment offered by the borrower.
	  - This can be interpreted as meaning that the lender learns in advance about the borrower's business to properly interpret any data about the project's return.
	  - The lender must establish a relationship in order to monitor the borrower.
		 - If,  instead,  the lender can wait until after the borrower defaults on a loan to incur monitoring costs,  then monitoring cost is required only when $V=1$,  or with probability $0.2$.
		 - In practice,  a relationship is required and in addition there is extra monitoring when the borrower might default.
   - Duplication of effort in monitoring implies that when monitoring is important,  it may be best to have a single lender (a fat cat) who owns the entire bond issue.
	  - This would have an advantage over public security issues.
	  - We will see next time how financial intermediaries can replace the single lender,  and offer better financial contracts.
		 - Banking is the original type of financial-engineering: a way of manufacturing synthetic fat cats.
Tags: #debt #contracts #monitoring #renegotiation #liquidation #covenants #borrowers #lenders #monitoring-costs #information-asymmetry