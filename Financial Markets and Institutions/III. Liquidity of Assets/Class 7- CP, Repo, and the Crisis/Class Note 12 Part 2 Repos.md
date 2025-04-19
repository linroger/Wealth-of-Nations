---
cssclasses:
  - academia
title: Class Note 12 Part 2 Repos
tags:
  - collateralized_borrowing
  - interest_rate
  - margin
  - repo_market
  - security_trading
aliases:
  - Collateralized Borrowing
  - Repo
  - Repos
  - Repurchase Agreement
key_concepts:
  - Collateralized borrowing of cash
  - Margin protects lenders
  - Market value of security
  - Repo agreement elements
  - Subprime mortgage security
---

[[Class Note 12 Part 2 Repos|Repos]]

# Class Note 12 Part 2 Repos
## [[Class Note 12 Part 2 Repos|Repurchase Agreements]] (Repos)

Probably the easiest way to be introduced to [[Class Note 12 Part 2 Repos|repos]] is through an example. Suppose I have a security with a market value of V,  say$1 M. You and I can enter into the following agreement (Bilateral Repo):

- Today,  I sell you my security for V-m. Say : $\xi1$ M-S 50 K $=\xi950K$
	- We would refer to $m/V$,  $5\%$ in this case,  as the margin,  or haircut

·Today,  I also agree to repurchase the security tomorrow for

- V-m,  i.e. the amount I sold it to you for,  plus interest on V-m at a negotiated rate,  say 1\%/year
- So the interest would be $\mathrm{s950K}(1/360)(1\%)=526.38$
- This is how interest is calculated in this case: the loan amount (\$950 K) times the number of days divided by 360 $(1/360)$ times the annual rate $(1\%)$
- So tomorrow,  I am supposed to pay you \$950,  026.38,  and you are supposed to give me my security back

Here are the key things to notice about this transaction:

·I am simultaneously

- Lending a security,  and
- Borrowing money (i.e.,  the \$950 K),  on which I pay interest
- Simultaneously,  you are
- Borrowing a security,  and
- Lending money,  on which you get interest
- If I default on my obligation to repurchase the security,  then you can try to make yourself whole by selling the security.
- Since the security was originally worth $5\%$ more than the loan,  it will be sufficient to make you whole unless its value dropped by more than $5\%$ during that day
- `If you default on your obligation to sell the security back to me for the negotiated price of$950,  026.38,  then I keep that amount
- Since the security was worth more than the loan amount,  I am losing money in this situation unless the security's value dropped by more than $5\% ,  in which case I'm better off with the cash than the security

So you can think of a repo as collateralized borrowing of cash:

- I am borrowing against the value of my security by simultaneously selling it and contracting to repurchase it tomorrow (or,  instead of tomorrow,  whatever other day we agree upon).
- You can equivalently think of it as collateralized borrowing of the security by the other side of the repo.

Notice that there are three key elements to a repo agreement:

- The margin ( $5\%$ in our example) -The term (1 day in our example) -The interest rate ( $1\%$ in our example)

[[Class Note 12 Part 2 Repos|Repos]] are fundamental to how institutions engaged in securities trading and dealing finance themselves. Notice that if I wanted to buy the security in our example for $1 M from someone,  say Albert,  I could do the following:

- Agree with Albert that I'll buy the security from him for$1 M
- Arrange with Bob to do a repo of this security with him,  say at the terms discussed above
- Then simultaneously,  the following things all happen:
- Albert gives me the security so I pass it on to Bob
- Bob gives me the$950 K so I add$50 K out of my own pocket to the$950 K,     and give the$50 K +$950 K =$1 M to Albert
- At this point,  Albert is out of the picture. He's delivered his security and gotten his$1 M,     so he's all done. My remaining relationship is with Bob,     from whom I'm borrowing money at $1%
- The next day,  let's say I want to sell the security to Charles,  who's offering$1.1 M for it. I can agree to sell it to Charles for that much,  and then the following things all happen simultaneously:
- Bob gives me the security
- I pass it on to Charles
- Charles gives me the$1.1 M
- Out of the$1.1 M,     I pay$950,  026.38 to Bob so which leaves me with$1.1 M -$950,  026.38 =$149,  973.62
- So my net profit is$149,    973.62 -$50,  000 =$99,  973.62
- Notice that,  as long as Bob and I end our repo according to the contract,  Bob is not exposed at all to the value of the security. The rise (or fall) of its market value accrues completely to me.
- Notice also that the margin I negotiate with Bob is what determines how much cash of my own I need to do this transaction. With a 5% margin,  I'm paying in only 5% of the purchase price.

## Run on the Repo Market

If you are lending money in a repo transaction,  the margin is what's protecting you against the scenario where

- 1) your counterparty fails to repurchase the security,  and
- 2) the security's price has dropped.
- If you think this scenario is highly unlikely,  then maybe you wouldn't require any margin at all. But as you start getting worried about your counterparty,  or about the risk of the security,  then you start requiring more margin.

Let's say the security in our example is a subprime mortgage-backed security. And you get a little anxious about these. So you decide that $5\%$ margin isn't enough; now you want $10\%

- So when I return to you tomorrow to repurchase the security as contracted,  and I ask you if we can do it again,  you say "Sure,  as long as we increase the margin to $10\%^{\prime}$ · $10\%$ margin on a $1 M security is $100 K. So this means I have to pay in $50 K more.

What if I don't have $50 K more? Then I can't do the repo with you,     and if everybody else demands $10\% ,  then I'll just have to sell the security today,  even if there's no ready buyer for it.

So let's say I sell the security,  and I don't get a good price,  say $960 K rather than $1 M. Now everybody else doing [[Class Note 12 Part 2 Repos|repos]] of that security are going to be affected,  because the lenders will say "this security is now apparently worth $960 K,     not $1 M. So now,  I'm willing to loan only ($960 K)(90%)=$864 K against it"

- That is,  they are marking the security to market.
- So everybody else borrowing against it now has to not only put up the $10\%$ margin,  but they also have to pay even more cash to cover this decrease in the mark-to-market value of the security.
- Some of them won't have this much cash,  and will be forced to sell.
- These forced sales will push the mark-to-market value down even more,  and force even more investors to sell,  and so on.
- Lenders are likely to respond to the increased risk of the securities by increasing margin,  which increases the stresses on investors even more.

This is again like a bank run,  though with a twist. The twist is that marking-to-market spreads the contagion from borrower to borrower. That is,  if my lenders aren't nervous but Fred's lenders are,  and they force Fred to sell at a bad price,  then that bad price is used by my lenders to reduce how much they'll lend to me,  which makes me more likely to sell,  and that reduces the market price more,  and that makes someone else sell,  and so on. So the whole market ends up shrinking.

Here's a graph showing margins (i.e. haircuts) of different quality mortgage-backed securities over time:

 ![500](https://storage.simpletex.cn/view/fQ4Luxx6kk6ReDpqTvOVGhhvbe5f92qfv)

Notice that margins are zero until the summer of 2007.

- Then they start ramping up and up,  with margin on subprime eventually reaching $100\%
 	- Meaning,  we won't lend a dime against subprime collateral.

 ![500](https://storage.simpletex.cn/view/frS1KsCboZYVEawGCrMqRzanQdvI10qmR)

Fig. 4. The repo-haircut index. The repo-haircut index is the equally weighted average haircut for all nine asset classes.

- So the amount of cash investors needed to keep holding their mortgage-backed securities,  particularly the subprime ones,  went way up. So they had to either recapitalize,  sell their securities,  or go bankrupt (maybe all 3). ·There are no hard numbers on how much the repo market shrank. Obviously,  it shrank significantly.

This graph is from a paper by Gary Gorton and Andrew Metrick,  "Securitized banking and the run on the repo,  "on the canvas site as recommended.

### Tri-Party Repo

Much of the repo that occurs is what is called tri-party repo. All this means is that a third party gets involved as follows. Suppose I want to do the repo described above,  and suppose Bob wants to do it too,  but I don't trust Bob and he doesn't trust me.

Suppose also,  though,  that we both trust JP Morgan.

Then we could both do repo with JP Morgan:

- I do the same repo as above,  except now the other side of the trade isn't Bob ,  it's JP Morgan,  and the interest rate isn't $1\%$ ,  it's 1.25%
- Bob does the same repo as above,  except now the other side of the trade isn't me,  it's JP Morgan,  and the interest rate isn't $1\%$ ,  it's 0.75%
- So now I'm paying $0.25\%$ more interest,  but what I get for that is more security: I am less worried that my counterparty will default on its obligation to sell me the security back at the prearranged price
- And Bob is getting $0.25\%$ less interest,  but he also gets more security: he is less worried that his counterparty will default on its obligation to buy the security back at the prearranged price
- JP Morgan makes the spread of $1.25\%-0.75\%=0.50\%$ in exchange for bearing our counterparty risk.
- The haircuts do not adjust quickly in this market (they did not change at all in 2008),  so if required haircuts go up,  say for a borrower who might default on a repo,  that borrower will get shut out of the tri-party repo market. This happened to Lehman and Bear Stearns. See data on the next page.

# Figure 26: Differences in Haircuts Between Bilateral Repo and Tri-Party Repo

 ![500](https://storage.simpletex.cn/view/fy2f6XX42bmNZU1prgKPDm58cno45PgBg)

Note: Difference calculated as repo median minus triparty median for each asset class.

Dotted black line represents zero.

Figure 20: Lehman Brothers' Tri-Party Book

 ![500](https://storage.simpletex.cn/view/foX43GgnL7rhXqIgrsqRztyrI0W8Wtwtq)

Figure 21: Number of Cash Investors in Lehman Brothers

 ![500](https://storage.simpletex.cn/view/fwY912r6unGqfqpUgF95faESGGENypyTk)

Note: Red line corresponds to Lehman [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] filing.

There were some structural problems with the tri-party market before 2010 (which might have caused problems in 2008-9 but did not).

- For tri-party repos,  there was a "morning unwind" where the bank in the middle (JP Morgan or BONY in practice) would be responsible for providing cash to a cash investor/ lender who did not roll over his repo loan of cash. Thus,  if the borrower (e.g.,  Lehman) was going to have a hard time rolling over,  the cash investor gets out with no loss. In bilateral,  the cash investor would instead be left holding the collateral for the repo (which may or may not result in a zero loss). Therefore,  tri-party [[Class Note 12 Part 2 Repos|repos]] are more subject to runs than bilateral repos. There is a bigger gain from getting out "first" in a tri-party repo.
- What did the Fed do about the repo market? They introduced a program known as the Primary Dealer Credit Facility,  whereby the Fed will loan money to dealers,  taking as collateral the kind of securities that would normally be used in repo transactions. These loans aren't repos,  but they are similar. The total size of this program is about $20 B.