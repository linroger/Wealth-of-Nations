---
cssclasses:
  - academia
linter-yaml-title-alias: Class SlIdes On Repurchase Agreements
title: Class Slides On Repurchase Agreements
tags:
  - haircut
  - interest_calculation
  - margin
  - repo_transaction
  - repurchase_agreements
aliases:
  - Repo Slides
  - Repurchase Agreements
key_concepts:
  - Borrowing a security
  - Interest calculation
  - Margin or haircut
  - Repo transaction example
  - Selling the security
---

[[Class Note 12 Part 2 Repos]]

# Class Slides On Repurchase Agreements

#### I. Introduction to Repos
- **Example of a Repo Transaction**:
  - Suppose I have a security with a market value of $V$,  say \$1 M.
  - We can enter into the following agreement (Bilateral Repo):
	- Today,  I sell you my security for $V - m$.
	  - Say: $\$1 M - \$50 K = \$950 K$
	  - We refer to $\frac{m}{V}$,  $5\%$ in this case,  as the margin or haircut.
	- Today,  I also agree to repurchase the security tomorrow for:
	  - $V - m$,  i.e.,  the amount I sold it to you for,  plus
	  - Interest on $V - m$ at a negotiated rate,  say $1\%$ per year.
		- So the interest would be:
		  $$ 
          \text{Interest} = 950K \cdot \left(\frac{1}{360}\right) \cdot (1\%) = 26.38 
          $$ 
		- This is how interest is calculated: loan amount (\$950 K) times the number of days divided by 360 $(\frac{1}{360})$ times the annual rate $(1\%)$.
	- So tomorrow,  I am supposed to pay you:
	  $$
      950K + 26.38 = 950,  026.38
      $$ 
	  - And you are supposed to give me my security back.

#### II. Key Points of the Transaction
- I am simultaneously:
  - Lending a security.
  - Borrowing money (i.e.,  the \$950 K),  on which I pay interest.
- Simultaneously,  you are:
  - Borrowing a security.
  - Lending money,  on which you earn interest.
- If I default on my obligation to repurchase the security,  then you can try to make yourself whole by selling the security:
  - Since the security was originally worth $5\%$ more than the loan,  it will be sufficient to make you whole unless its value dropped by more than $5\%$ during that day.
- If you default on your obligation to sell the security back to me for the negotiated price of \$950,  026.38,  then I keep that amount:
  - Since the security was worth more than the loan amount,  I lose money in this situation unless the security's value dropped by more than $5\%$,  in which case I'm better off with the cash than the security.

#### III. Understanding Repo Agreements
- Think of a repo as collateralized borrowing of cash:
  - I am borrowing against the value of my security by simultaneously selling it and contracting to repurchase it tomorrow (or any other agreed-upon day).
- You can equivalently think of it as collateralized borrowing of the security by the other side of the repo.

##### Key Elements of a Repo Agreement
- The margin (5% in our example).
- The term (1 day in our example).
- The interest rate (1% in our example).

#### IV. [[Class Note 12 Part 2 Repos|Repos]] in Securities Trading
- [[Class Note 12 Part 2 Repos|Repos]] are fundamental to how institutions engaged in securities trading and financing themselves.
- If I wanted to buy the security for \$1 M from someone,  say Albert,  I could do the following:
  1. Agree with Albert to buy the security for \$1 M.
  1. Arrange with Bob for a repo of this security with the terms discussed above.
  1. Simultaneously,  the following things happen:
	 - Albert gives me the security.
	 - I pass it on to Bob.
	 - Bob gives me \$950 K.
	 - I add \$50 K from my own pocket to the \$950 K,  giving a total of \$1 M to Albert.
  - At this point,  Albert is out of the picture; he has delivered his security and received his \$1 M.
  - My remaining relationship is with Bob,  from whom I'm borrowing money at $1\%$.

#### V. Selling the Security
- The next day,  let’s say I want to sell the security to Charles,  who offers \$1.1 M for it:
  1. I can agree to sell it to Charles for \$1.1 M.
  1. Simultaneously:
	 - Bob gives me the security.
	 - I pass it on to Charles.
	 - Charles gives me \$1.1 M.
	 - Out of the \$1.1 M,  I pay \$950,  026.38 to Bob.
	   - Leaving me with:
		 $$
         1.1M - 950,  026.38 = 149,  973.62
         $$
	   - My net profit is:
		 $$
         149,  973.62 - 50,  000 = 99,  973.62
         $$
- Notice that,  as long as Bob and I end our repo according to the contract,  Bob is not exposed to the value of the security. The rise (or fall) of its market value accrues completely to me.
- The margin negotiated with Bob determines how much cash I need for this transaction. With a 5% margin,  I'm paying only 5% of the purchase price.

#### VI. Run on the Repo Market
- If you are lending money in a repo transaction,  the margin protects against:
  1. Your counterparty failing to repurchase the security.
  1. The security’s price dropping.
- If you believe the scenario is unlikely,  you might not require margin. But if you become anxious about your counterparty or the security's risk,  you start requiring more margin.
- If the security is a subprime mortgage-backed security and you decide that $5\%$ margin isn't enough,  you may want $10\%$.

#### VII. Increased Margin Impact
- When I return to repurchase the security as contracted,  you say,  "Sure,  as long as we increase the margin to $10\%$."
  - $10\%$ margin on a $\$1 M$ security is $\$100 K$,   so I must pay in an additional $\$50 K$.
- If I don't have the extra $\$50 K$,   I can't do the repo,   and if everyone else demands $10\%$,  I'll have to sell the security today,  even without a ready buyer.
- If I sell the security for $\$960 K$ instead of $\$1 M$:
  - Lenders will say,  "This security is now worth $\$960 K$,   not \$1 M."
  - Now,  they will loan only:
	$$
    960K \cdot 90\% = 864K
    $$
  - They are marking the security to market.

#### VIII. Contagion Effects
- Everybody borrowing against it now has to put up the $10\%$ margin and pay more cash to cover the decrease in mark-to-market value.
- Some may not have enough cash and will be forced to sell.
- Forced sales push mark-to-market value down further,  leading to more selling.
- Lenders respond to the increased risk of securities by increasing margin,  adding stress to investors.

##### Bank Run Analogy
- This situation is similar to a bank run,  but with a twist:
  - If my lenders aren't nervous but Fred's lenders are,  and they force Fred to sell at a bad price,  that price affects my lenders' decisions.
  - This leads to a chain reaction,  reducing market prices further.

#### IX. Graph: Margins Over Time

Here’s a graph showing margins (i.e.,  haircuts) of different quality mortgage-backed securities over time:

 ![Margins Over Time](https://storage.simpletex.cn/view/fQ4Luxx6kk6ReDpqTvOVGhhvbe5f92qfv)

- Margins are zero until the summer of 2007.
- Then they increase significantly,  with margin on subprime eventually reaching $100\%$ (meaning no lending against subprime collateral).

#### X. Repo-Haircut Index

 ![Repo-Haircut Index](https://storage.simpletex.cn/view/frS1KsCboZYVEawGCrMqRzanQdvI10qmR)

- The repo-haircut index is the equally weighted average haircut for all nine asset classes.
- As the need for cash increased to hold mortgage-backed securities,  particularly subprime,  investors had to either recapitalize,  sell their securities,  or potentially go bankrupt.

#### XI. Tri-Party Repo
- Much of the repo market is tri-party repo,  involving a third party.
- If I want to do a repo but don’t trust Bob,  and we both trust JP Morgan,  we can do a repo with JP Morgan:
  - I do the same repo as before,  but with JP Morgan instead of Bob,  at $1.25\%$.
  - Bob does the same with JP Morgan instead of me,  at $0.75\%$.

#### XII. Advantages of Tri-Party Repo
- I pay $0.25\%$ more interest for more security (less worry about counterparty default).
- Bob gets $0.25\%$ less interest but also more security.
- JP Morgan makes a spread of $0.50\%$ for bearing our counterparty risk.

##### Haircut Adjustments
- Haircuts in this market do not adjust quickly.
- If haircuts increase for a borrower,  they may get shut out of the tri-party repo market.
- This happened to Lehman and Bear Stearns.

#### XIII. Graph: Differences in Haircuts

  ![Differences in Haircuts](https://storage.simpletex.cn/view/fy2f6XX42bmNZU1prgKPDm58cno45PgBg)

- The difference is calculated as repo median minus tri-party median for each asset class.
- The dotted black line represents zero.

#### XIV. Lehman Brothers' Tri-Party Book

  ![Lehman Brothers' Tri-Party Book](https://storage.simpletex.cn/view/foX43GgnL7rhXqIgrsqRztyrI0W8Wtwtq)

#### XV. Number of Cash Investors in Lehman Brothers

  ![Number of Cash Investors](https://storage.simpletex.cn/view/fwY912r6unGqfqpUgF95faESGGENypyTk)

- The red line corresponds to Lehman [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] filing.

#### XVI. Structural Problems in Tri-Party Market
- Structural issues existed in the tri-party market before 2010.
- A "morning unwind" provided security to cash investors if the borrower was having trouble rolling over.
- Tri-party [[Class Note 12 Part 2 Repos|repos]] are more subject to runs than bilateral [[Class Note 12 Part 2 Repos|repos]] due to this structure.

#### XVII. Fed Intervention
- The Fed introduced the Primary Dealer Credit Facility to loan money to dealers,  using securities as collateral.
- These loans are not [[Class Note 12 Part 2 Repos|repos]] but are similar in nature,  totaling around \$20 B.