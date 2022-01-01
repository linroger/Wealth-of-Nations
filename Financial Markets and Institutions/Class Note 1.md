---
title: "Class Note 1 "
aliases: 
tags:
  - "#debt-management"
  - "#financial-crises"
  - "#risk-management"
  - "#financial-instruments"
  - "#macroeconomics"
  - "#financial-intermediation"
  - "#delegated-monitoring"
  - "#liquidity-risk"
cssclasses: academia
---
# Class Note 1

# Borrower-Lender conflicts and implied agency problems

The amount of leverage has an impact on the incentives of someone who maximizes the value of the residual equity claim. This “asset substitution theory” is a popular theory of capital structure,  but it is not too plausible for large firms. It makes the most sense for owner managed firms,  where the manager is the stockholder. If the owner and manager differ,  one needs to examine the manager's incentive contract to learn his/her incentives. We will see later that the owner’s and manager’s incentives are naturally aligned for nearly insolvent firms and for some financial institutions that have government deposit insurance.

The example illustrates how divided ownership of different parts of the cash flow distribution distorts capital budgeting decisions.

Debt holders own the lower tail of the distribution of firm value,  and equity owners the upper tail. This is the cause of the conflict of interest because some decisions hurt the lower tail and help the upper tail (and can help or hurt the overall value of the firm).

# 1. No debt

Two projects,  the riskier one also has a lower expected return. Each has only two possible outcomes,  one if a depression (D),  one if prosperity (P). The probability of each outcome is $\%$ . Each project requires the an initial outlay of $\S800$ .

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/128fc0fab172dce9a324368cba455f82ced7e0e85b411ea782dbb993a90f712b.jpg)

We could get fancy and use the states model to take account of the positive "beta" of each project (each pays off more in prosperity). Project 2 has a higher beta,  implying that it should require a higher discount rate than project 1. It is sufficient for our purposes to use the expected returns to see the incentive problem with debt.

Clearly,  project 1 is the best investment. An owner-managed firm with no debt would select it,  since all require the same initial outlay.

# 2. What about a firm with debt with face $\pmb{\S600}$ in place?

The fixed payment of $\S600$ is a sunk cost. If the firm is going to default,  then it does not care "how big" the default is. It wants to make more when not in default.

# Cash flows to equity when debt of $\pmb{\S600}$ is in place

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/c4a1507b4faaef8f56f0f6e7a8b4ae5d8d56a0a171fb96f4a3b202817285428d.jpg)

The levered firm would select project number 2,  despite its lower net present value,  because it has a higher present value conditional on not leading to bankruptcy. The equity owner owns the upper tail,  and is only concerned with the returns he owns. Note that no matter how the equity owner values the cash flows if P,  he prefers project 2 since both have identical cash flows if D and project 2 has higher payments if P.

This does not mean that firms "want" to go bankrupt. Instead,  it is a statement about debt capacity . If the [[Leverage Ratio|leverage ratio]] gets too high,  then these perverse incentive effects of debt increase. This can lead the firm to tilt its decisions toward excessively risky projects,  with a lower net present value. Potential bond holders can put themselves into the owner's shoes,  and take this into account when deciding what interest rate to charge on the bond. The lender can predict what the borrower will do,  but there is a problem because the lender cannot directly observe the project choice.

What is the debt capacity of the firm? What is the highest face value,  F,  that the borrower prefers project 1?

The borrower’s equity payoff from Project 1 with debt of face F is:

$\begin{array}{r}{\%\left(1500\!-\!\mathsf{F}\right)+\%\left(500\!-\!\mathsf{F}\right)=1000\cdot\mathsf{F}}\end{array}$ (for F d 500)

 $\%\left(1500–\mathsf{F}\right)+\%$ (0) (for F between 500 and 1500),  0 for $_{\textrm{F>}1500}$ .

# The borrower’s equity payoff from Project 2 with debt of face F is

$\%(1551-\mathsf{F})+\%(0)$ (for $\mathsf{F}<1551)$ ) 0 (for $\mathsf{F}\!\!>$ 1551)

The debt capacity must be less than 500,  because if the firm will certainly default in Depression,  all that matters is what it is worth in Prosperity.

For $\digamma<500$ ,  Project 1 is preferred for all F that satisfy $1000{\mathrm{-}}{\mathsf{F}}\geq1/\!\!2(1551{\mathrm{-}}{\mathsf{F}})$ ,  which solves out to $\mathsf{F}\!\leq449$ . As a result,  449 is the debt capacity in face value.

Suppose lenders require an expected return of r for investing in any security of the firm. If the firm issued debt with face value 448 debt,  it would choose project 1,  and then the debt could raise up to $\frac{448}{1+r}$ . (Project 1 is also selected for face 449,  because the borrower will not hurt the lender if it does not help himself.) If the firm issued debt with face $\mathsf{F}\!\!>\!\!449$ ,  it would lead to project 2 and raise $\frac{\not{1}_{2}\mathrm{F}\;+\;\not{1}_{2}(0)}{1+\mathrm{r}}$ .

Risky debt (debt with a positive probability of bankruptcy) distorts capital budgeting decisions. It provides incentives to make tradeoffs between cash in [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] and not in [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] that differ from the ones that maximize the value of the firm.

The potential bond holders will require a high enough interest rate to give themselves a competitive rate of return,  for example $10\%$ . Thus,  any reductions in the value of the capital budgeting program of the firm will come out of the owner's pockets. If the firm selected too high a leverage ratio,  it would be giving itself a perverse incentive contract. It would not do this in the first place,  if it had alternatives. Thus,  we might not expect a firm to choose a capital structure with as much debt as our example if it faced an unobservable choice between these projects.

This leaves us with some unanswered questions: AHow can these bad effects of debt be reduced? BHow do bank asset services help reduce these bad effects? CIf debt is so bad,  why is it so common,  especially for smaller firms? Why not use another financial contract?

Beginning with question a,  we examine problems with bond covenants,  contractual provisions in bond or loan indentures. See the Wruck paper in the packet for a description of typical covenants.

-Just prohibiting an action in a bond covenant does not prevent it from happening. The lender needs to know about the violation before it happens or soon thereafter. In addition,  the lender must have some bargaining power over the borrower in order to stop a “crime in progress.”

-Enforcement requires effort and monitoring of the borrower. Without substantial monitoring,  the contract cannot depend on anything except the grossest public information.

-If not all contingencies are spelled out,  contracts must be renegotiated over time. This too requires the lender to have lots of information about the borrower's situation.

-If the lender is not one individual,  but many small bond holders,  the [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] can be difficult to enforce. There can be either duplication of effort if each lender monitors the situation carefully,  or more likely,  a "free rider" problem,  where none of the small bond holders find it worthwhile to bother to monitor. Without monitoring,  [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] will not be renegotiated or contain much detail. If there is no monitoring,  [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] will be written contingent only on the grossest public information.

-This gives an advantage to having a single lender,  rather than many lenders. We will see that this is a part of the argument why asset services of banks and other intermediaries are important.

-The US Federal Trust Indenture Act prohibits majority voting to restructure debt contracts that reduce principal or interest or extend the debt maturity. A $100\%$ vote required to change these “key covenants.” Thus,  even if public bond holders had the information,  they probably could not use it. Changes to other [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] in bonds require a $_{2/3}$ vote in dollar value,  and $50\%$ measured in the fraction of bond holders (not weighted by dollar value).
# University of Chicago Chicago Booth School of Business

# Class Note 2

# Debt contracts due to the lack of information: Debt as a promise and a threat

This is our initial view of the role of debt in corporate control. This is simple but abstract. This will not be our only view of this issue.

Consider a borrower who needs to raise a large quantity of capital. All lenders and borrowers are risk neutral. The borrower has no capital and needs to raise 1 ( $\S1$ million).

Outside investors do not observe the borrower’s operations directly,  not even its sales or cash flows. How can the lenders write a contract where they do not need to monitor this information?

The firm needs to raise 1 ( $\S1$ million),  and investors require an expected return of $\mathsf{r=}5\%$

# What is the best financial contract without monitoring?

All lenders and the borrower agree that the borrower has a profitable (positive net present value) project to fund. However,  only the borrower will observe how profitable it turns out to be . The borrower can consume any part of the project's return that he does not pay out to the investor. The interpretation is that the borrower can appropriate the return to himself,  since no one else observes how successful is the project. If the project is a retail store,  the borrower can take some sales in cash to himself. More generally,  the borrower can inflate costs. The net cash flows to the firm are very unobservable in practice for many firms. In addition,  most other conflicts of interest faced by borrowers can be reinterpreted as equivalent to the borrower’s ability to retain under reported cash. The ability to retain under reported cash is simply the most extreme example of a conflict of interest.

The project costs 1 to fund,  and its realized value is a random variable with realization denoted by V. The distribution of V,  the value of the project,  known to all borrowers and lenders

$\mathsf{H}\!\!=\!\!1.4$ million with probability $\mathsf{P}\!\!=\!\!0.\1$ $\mathsf{L}\!=\!\mathsf{1}$ million with probability ${\mathsf{1}}{\mathrm{-}}{\mathsf{P}}{\mathrm{=}}{\mathsf{2}}$ .

# A simple candidate for a financial contract is equity

An equity contract in this context is a profit-sharing agreement,  where the profit shared depends on the profits reported by the borrower.

Let the fraction of reported profits that goes to the outside investor be a,  while the borrower retains the fraction 1  a,  plus any under reported profits. Suppose that the borrower’s contract is just to pay a fraction of reported profits,  with no other details or penalties specified. The borrower's payoff given the true value of V and the reported value,  denoted by Z,  is $V-a Z$ .

# What profit will the borrower report if he is supposed to pay out a fraction of it?

The borrower will choose the smallest value of Z. Supposing that the borrower can’t make the lender take a share of a reported loss (by reporting $Z{<}0)$ ),  the borrower will report $\scriptstyle{Z=0}$ .

No matter what is the true value of V,  the most profitable choice for the borrower is to pay the lowest possible value. If there is no cost to the borrower of understating the amount,  the borrower always does. Even if the lender knew the value of V,  if the borrower obtains it first and thus controls it,  the lender will not be paid unless the borrower suffers some consequence of not paying.

# What can the lender do if the borrower claims a low amount?

The lender would like to impose a penalty for low payments to give incentives for higher payments. There are two interpretations. The lender can liquidate the project if the borrower pays too little,  preventing the borrower from absconding with it,  or the lender can impose a nonmonetary penalty on the borrower. Bankruptcy in the world is some combination of these two effects. In ancient history,  the non-monetary penalties were very common,  i.e.,  debtors’ prisons and physical penalties. Such sanctions are now illegal,  but the loss of reputation of a borrower of a bankrupt firm is similar.

# Bankruptcy,  liquidation,  and the optimal liquidation policy

Suppose that it is not possible to impose a penalty on the borrower or take other assets outside the business that are valued by the borrower. The only sanction available to give the borrower an incentive to pay is liquidation of the borrower’s assets. To focus on the inefficiency of disrupting firm operations,  I assume that liquidating the firm’s assets gives no proceeds to the lender or to the borrower. Liquidation and [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] are useful as a penalty that a borrower can avoid by paying the debt,  but regular liquidation is not a good way to run a firm.

# How does one specify an optimal financial contract between investor and borrower when one can decide to liquidate (to penalize the borrower) or not contingent on any payment?

Liquidation is best used as a payment-contingent penalty in the following way. If the lender is ever to liquidate for a given payment,  he also should liquidate for all lower payments.

Suppose instead that the lender does not liquidate if 1 is paid,  but will liquidate for some higher payment. Then,  whenever the borrower has at least 1,  he will avoid liquidation by paying 1,  and keep the remainder for himself. This makes the threat to liquidate given higher payments meaningless because the payment will never exceed 1.

The borrower will pay the lowest amount that avoids liquidation,  and keep the rest for himself. The only exception is if the borrower has insufficient funds to pay that amount. This implies a description of the optimal financial contract without monitoring: select a payment,  f,  that,  if paid,  liquidation is avoided. The lender then liquidates for all lower payments. This implies that the optimal contract when monitoring is impossible is a debt contract with face f. Face value includes the promised payment of principal and interest. Determination of the face value of non-monitored debt

This section determines the minimum face value,  f,  of non-monitored debt which will lead to payments with an expected return of $5\%$ on a loan of 1 ( $\S1$ million),  or an expected value of 1.05. Any face value below $\mathsf{L}\!=\!\mathsf{1}$ will always be repaid,  but this will not deliver an expected repayment of 1.05. To make this very clear,  here is what $\mathsf{f}\!\!=\!\!1$ would lead to.

Suppose $\scriptstyle{\mathfrak{f}}={\mathfrak{H}}1$ . When $\scriptstyle{\sqrt{=1}}$ ,  the borrower pays 1 (paying less would result in liquidation). The borrower gets 0,  which is as much as if he paid any lower amount. When $\scriptstyle{\sqrt{=1.4}}$ ,  the borrower pays 1 (to avoid liquidation),  and keeps 0.\1 for himself. This implies that with face value of 1,  the lender gets 1 for sure,  which is less than 1.05 and not acceptable.

Any face value of debt between 1 and 1.4 will force the borrower into liquidation when the project returns 1,  but will be paid in full when the project returns 1.4. This will give the lender an expected return of 0.\1 F,  because nothing is received when there is liquidation. Solving . $8\mathsf{F}\!\!=\!\!1.05$ yields $\mathsf{F}\!\!=\!\!1.3125$ . Non-monitored debt with that face value works as follows.

# Suppose f=1.3125

When $\scriptstyle{\forall=1}$ borrower pays less than 1.3125 and the asset is liquidated. The borrower gets 0 for any payment less than or equal to 1. The best interpretation is that the borrower then chooses to pay 0,  because this is the best choice when the borrower can keep any positive fraction of the retained cash. The lender receives 0. This occurs with probability 0.\1. When $\scriptstyle{\forall=1.4}$ the borrower pays 1.3125,  avoids liquidation,  and keeps 1.4-1.3125=. 0875 for himself. This is more than he could get from any smaller payment: any smaller payment gives 0. The payment 1.3125 is received with probability 0.\1. Liquidation is only avoided when $\scriptstyle{\bigvee}=\mathsf{H}$ and the face of 1.3125 is paid. The lender receives 1.3125 with probability 0.\1 and zero with probability 0.\1,  which is an expected payment of . $8(1.3125){=}1.05$ . Any lower face value will give the lender an expected rate of return below $5\%$ .

When outside investors cannot observe the cash flows and cannot monitor the business,  equity contracts do not work. Enforcing them requires excessively costly monitoring. If this monitoring (sitting on the board of directors,  or keeping close tabs on the business in other ways) is too costly,  then simple financial contracts that do not require monitoring are best. These are debt contracts. They induce the borrower to pay investors because default serves as a penalty that the borrower seeks to avoid.

The analysis can be extended to apply not only to defaults on principal and interest [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] of debt contracts,  but to any other covenant that depends on hard-to-observe information. When it too costly for lenders to collect the information to enforce or renegotiate other detailed covenants,  then [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] that "mean what they say" (and involve a default when violated) must be used.

A publicly-traded bond with many lenders needs to have easy to enforce covenants. If it is costly to monitor and enforce detailed loan covenants,  then bond [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] will be based on easily observed information. Because the public will not have better information,  these [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] will not be renegotiated. This is especially true of the "key covenants" of principal,  interest,  and maturity. Public debt will be enforced by the threat of liquidation,  and liquidation will occur whenever there is a default. More generally,  we will later see that public debt is enforced by the threat of filing formal bankruptcy (which may not lead to liquidation). I will not yet add this complication.

Debt contracts can be improved by costly monitoring. The next section shows the value of monitoring in allowing renegotiation of loan contracts.

The Value of monitoring in restructuring and renegotiation of debt

Suppose that it is possible for the lender to monitor the value of the borrower’s operations. Then,  instead of liquidating when less than the face value of debt is paid,  the lender who monitors can instead use the threat of liquidation and offer to refrain from liquidation so long as the borrower repays as much as possible.

Instead of always or never accepting 1 in lieu of liquidation,  the lender who monitors the firm’s cash flow can accept 1 when $\scriptstyle{\forall=1}$ and reject it when $\scriptstyle{\forall=1.4}$ . The lender can use the extra information to allow beneficial renegotiation of loan contracts. This policy leads the borrower to pay f when $\scriptstyle{\sqrt{=1.4}}$ and 1 when $\scriptstyle{\sqrt{=1}}$ . I assume that the lender has all of the bargaining power and can offer to accept less than f only when $\scriptstyle{\bigvee}=1$ . The value of monitoring is the expected savings in financial distress costs,  which are equal to . $2(1){=}0.\1$ .

Monitoring of the exact value of the borrower’s project costs 0.002 $(\S200)$ . If there is a single lender lending his or her own funds,  that lender would monitor because the cost,  0.002,  is less than the saving from monitoring,  0.\1.

The lender must commit the time to monitoring before observing the payment offered by the borrower. This can be interpreted as meaning that the lender learn in advance about the borrower’s business to properly interpret any data about the project’s return. The lender must establish a relationship in order to monitor the borrower. If,  instead,  the lender can wait until after the borrower defaults on a loan to incur monitoring costs,  then monitoring cost is required only when $\scriptstyle{\bigvee}=1$ ,  or with probability 0.\1. In practice,  a relationship is required and in addition there is extra monitoring when the borrower might default.

Duplication of effort in monitoring implies that when monitoring is important,  it may be best to have a single lender (a fat cat) who owns the entire bond issue. This would have an advantage over public security issues. We will see next time how financial intermediaries can replace the single lender,  and offer better financial contracts. Banking is the original type of financial-engineering: a way of manufacturing synthetic fat cats.

# 8 QLYHUVLW\'RI'&KLFDJR'%RRWK'6 FKRRO'%XVLQHVV' 'RXJODV':''LDPRQG Class  – Corporate Bond Contracts

Bonds are defined by legal contracts,  called indentures ,  which spell out the rights and responsibilities of both sides. We will explore this contracting by reading the prospectus of a recent offering and analyzing its salient features,  and by discussing contract features that arise elsewhere.

# On December $13^{\mathrm{th}}$ ,  MGM Mirage issued a bond

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/5f262f6aecf9797e0468178f73fa9684e3d747151cfd971f76629b89bc4b66be.jpg)

10 years (approximately),  7 5/8 coupon,  issued $@$ par,  rated BB/Ba 2,  which is two notches below investment grade.

Inside the prospectus (which I’ve posted on the cDQYDV webpage),  we see:

Initial public offering price (1) Underwriting discount Proceeds,  before expenses,  to MGM MIRAGE (1) (1) Plus accrued interest,  if any

Per Note Total $100\%$ $\pmb{\S750, 000, 000}$

 $\pmb{0.325\%}$ \$ 2, 437, 500

 $\pmb{99.675\%}$ \$747, 562, 500 So the underwriters,  led by Barclays,  BNP,  UBS and Wachovia,  share $\S2.4375\mathrm{MM}$ .

The easiest place to start reading a prospectus is at the Summary,  which gives the big picture:

X Coupon rate,  payment dates and maturity x Call or other option features,  if any x Seniority x Issue size x Trustee x Use of proceeds

In this bond’s summary we see the same material from the Bloomberg,  and also

X There is some sort of optional redemption x The are several covenants

We’ll return to the [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] later. First,  let’s look at this optional redemption. On page S-10,  we get this:

# Optional Redemption

The notes are redeemable at our election,  in whole or in part at any time at a redemption price equal to the greater of:

x $100\%$ of the principal amount of the notes then outstanding; or x as determined by an Independent Investment Banker,  the sum of the present values of the remaining scheduled payments of principal and interest on the notes to be redeemed (not including any portion of such payments of interest accrued to the date of redemption) discounted to the redemption date on a semiannual basis (assuming a 360-day year consisting of 12 30-day months) at the Adjusted Treasury Rate,  plus 50 basis points,

Plus,  in either of the above cases,  accrued and unpaid interest to the date of redemption on the notes to be redeemed.

What is the purpose of this call? MGM can buy the bond back for the maximum of (i) par,  and (ii) the present value of the future payments on the note,  discounted at the Treasury rate plus 50 basis points. To see what this means,  note that

X The present value,  discounted at the Treasury rate plus 0 basis points,  is what the note would sell for if it were totally riskless x Because,  by construction ,  that’s what a Treasury note with the same payments would sell for

So if we discount at the Treasury rate plus 50 bp ,  we get a slightly lower number

X What the note would sell for if it traded 50 bp over Treasuries x The bond was issued 304 bp above Treasuries,  so 50 bp would be a much higher price,  corresponding to much higher credit worthiness

X Even a AAA-rated issuer would not generally expect to trade within 50 bp of the Treasury yield

When the bond was issued

x It sold at par,  which implies a yield-to-maturity of equal to its coupon rate of $7.625\%$ x Since this was 304 bp above Treasuries,  50 bp above Treasuries would be 254 bp lower,  or $5.085\%$ x In order to yield $5.085\%$ ,  the MGM note would have had to sell for 119.72

So to exercise this make-whole call option right now,  MGM would have to pay the maximum of 100 and 119.72,  i.e. 119.72

So,  putting this together,  the option is to buy the bond back for more than it is worth. Why bother writing this option into the contract? We’ll see at the end of class,  it is there to help the bondholder get out of the contract,  should this become necessary.

Much of the rest of the prospectus is boilerplate and standard disclosure

X Currency & location of payments; tax consequences; registration; listing x Dire warnings about risks facing the issuer x Financials related to interest coverage

The key moments in the prospectus,  looking ahead to a distress situation,  are

X Covenants,  positive and negative x Rights of creditors if the issuer defaults x How the contract can be changed by a vote

# Covenants

An indenture will have a section on covenants,  which are actions the issuer either commits to do (positive covenants) or not do (negative covenants). How do they add value?

X If management always maximizes expected value,  there is no positive role for covenants. They can only reduce expected value by constraining management

O A covenant might make debt sell for more,  but if it doesn’t increase total value then it must simultaneously make equity worth less ,  so the net effect to equity from selling the debt is negative

So [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] must be there to defend against management’s bad incentives,  particularly its willingness to take negative NPV actions that move value from debt to equity

The MGM bond lists three covenants:

# Negative Pledge

X This bond is not secured. Thus,  the assets supporting it are,  generally speaking,  the company assets that are not already pledged to other creditors

The purpose of the Negative Pledge clause is to prevent the company from now giving some new debt prior claim on those assets. In the prospectus on page S-12,  we see

# Limitations on Liens

Other than as provided below under “- Exempted Liens and Sale-Lease-Back Transactions, ” neither MGM MIRAGE nor any of the Subsidiary Guarantors may issue,  assume or guarantee any indebtedness secured by a Lien upon any Principal Property or on any evidences of Indebtedness or shares of capital stock of,  or other ownership interests in,  any Subsidiaries (regardless of whether the Principal Property,  Indebtedness,  capital stock or ownership interests were acquired before or after the date of the indenture) without effectively providing that the notes shall be secured equally and ratably with (or prior to) such Indebtedness so long as such Indebtedness shall be so secured,  except that this restriction will not apply to:

 (a) Liens existing on the date of original issuance of the notes;

 (b) – (l) [other exceptions]

# Restrictions on Sale and Leaseback Transactions

A sale-and-leaseback transaction is almost equivalent,  economically,  to secured borrowing

Firm sells an asset to another firm (e.g. GE Capital) and simultaneously enters a long-term contract to lease the same asset If the firm defaults on the contract,  the owner can take back the asset If the lease term covers the economic life of the asset,  this is very,  very close to secured borrowing (note that the owner gets to keep the asset after the lease expires,  but its economic life is over)

So this is similar to the negative pledge clause. However,  it is not possible to pledge some of the value of the sold asset to the bond holders,  so what this restriction says instead is that sale-and-leaseback is OK as long as the sale proceeds either

X Buy new assets that are available to the bond holders,  or x Are spent on retiring MGM debt

Other than as provided below under “ – Exempted Liens and Sale and Lease-Back Transactions, ” neither MGM MIRAGE nor any Subsidiary Guarantor will enter into any Sale and Lease-Back Transaction unless either:

 (i) [the notes would also be secured by the property] or

 (ii)[MGM spends the sale proceeds paying down debt]

Exempted Liens and Sale and Lease-Back Transactions [MGM can enter into such transactions for up to $\scriptstyle{15\%}$ of its Consolidated Net Tangible Assets]

# Consolidation,  Merger and Sale of Assets

This just says that,  MGM will not be involved in a merger or acquisition,  either as acquirer or target,  unless

x The resulting firm is still a U.S. firm responsible for paying this bond x The merger does not cause a default This prospectus does not constrain some other common bond covenants,  such as

X Dividend and share-repurchase restrictions x Asset-sale restrictions x Requirements to maintain and/or insure assets

With any covenant,  the key questions are

X What bad incentives does it address? X What good actions does it interfere with? X Does the benefit of the first outweigh the costs of the second?

# Rights of creditors upon default

Following the covenants,  the indenture lists the Events of Default :

a) Default on interest beyond a 30-day grace period b) Default on principal when it’s due c) Acceleration of any other sufficiently big debt of MGM d) A sufficiently big judgment against MGM e) Default on any other covenants,  if either i) the trustee wants to pursue this,  or ii) the trustee does not want to pursue it but holders of at least $25\%$ of the bond do want to pursue it,  and holders of no more than $50\%$ of the bond disagree

Reading further down,  we can condense the legalese to the following: So to put it another way,  if the debtor defaults,  then

x If the default is a failure to pay this bond on time,  then every creditor has the individual right to take legal action to force payment. This sort of default is called a financial default x But if the default is on anything else,  i.e. a covenant default ,  then the trustee has the right to take action,  but individual creditors do not . Instead,  we see that o A majority (by value) of bond holders can tell the trustee what to do o A quarter of bond holders can take action,  provided that a majority does not oppose them

So while it might seem that a bondholder can pursue any failure on an indenture,  in fact his rights are more limited than that.

# Role of the Trustee

This shows us the role of the bond’s trustee,  which in the case of this MGM Mirage note is U.S. Bank. The trustee is there to represent the rights of bond holders,  but is not an active monitor like a loan officer. Rather,  it receives reports of compliance or non-compliance from the issuer,  and decides on the course of action

# Example: Getty Images

HEADLINE: Getty Images Announces Commencement of Consent Solicitation for

 $0.50\%$ Convertible Subordinated Debentures,  Series B Due 2023

SEATTLE,  Jan. 4 /PRNewswire-FirstCall/ -- Getty Images,  Inc. (NYSE:GYI) today announced that it is soliciting consents (the "Consent Solicitation") from the holders of record at the close of business on January 4,  2007 of its outstanding $0.50\%$ Convertible Subordinated Debentures,  Series B due 2023 in the aggregate principal amount of $\S265$ million (the "Debentures") to an amendment to,  and a waiver of an alleged or existing default or event of default under,  the indenture governing the Debentures (the "Indenture"). The terms and conditions of the Consent Solicitation are described in the Consent Solicitation Statement,  dated January 4,  2007 (the "Consent Solicitation Statement"),  a copy of which will be attached as an exhibit to the Current Report on Form 8-K to be furnished by Getty Images to the Securities and Exchange Commission (the "SEC").

On November 9,  2006,  Getty Images announced that its Board of Directors had established a special committee to conduct an internal investigation relating to Getty Images' stock option grant practices and related accounting for stock option grants and that it would delay the filing of its Quarterly Report on Form 10-Q for the quarter ended September 30,  2006 (the "Third Quarter Form 10-Q") until the special committee's review is complete. On November 29,  2006,  Getty Images announced that it had received notices of a purported default from holders who claim to hold more than $25\%$ in principal amount of the outstanding Debentures asserting that Getty Images' failure to file its Third Quarter Form 10-Q by the prescribed filing date under SEC regulations was a default under Section 17.01 of the Indenture,  which incorporates by reference Section 314 (a) of the Trust Indenture Act of 1939 (the "TIA") .

As previously stated,  Getty Images does not believe that it has failed to perform any of its obligations under the Indenture,  which does not contain an express covenant requiring Getty Images to provide the trustee under the Indenture or the holders with periodic reports,  such as the Third Quarter Form 10-Q. While Section 314 (a) of TIA is incorporated into the Indenture by virtue of Section 17.01 thereof,  Getty Images does not believe that the TIA requires periodic reports to be filed with the SEC or provided within any prescribed period of time.

Notwithstanding Getty Images' position regarding notices of default,  it is seeking an amendment to,  and a waiver of the alleged or existing default or event of default under,  the Indenture. The proposed amendment to the Indenture would provide that no notice of default delivered to Getty Images on or prior to March 2,  2007 that specifies as the basis for the default a failure to file with the SEC the Third Quarter Form 10-Q and/or the Company's Annual Report on Form 10-K for the year ended December 31,  2006,  as applicable,  and to file the applicable reports with the trustee under the Indenture,  shall have any force or effect with respect to the exercise of remedies by the trustee or any holder of Debentures if Getty Images files the applicable reports on or prior to May 1,  2007. The Consent Solicitation also includes a waiver of any defaults and events of default under Section 17.01 of the Indenture that may exist as a result of its failure to file the Third Quarter Form 10-Q.

Getty Images proposes to make a cash payment to consenting holders of the Debentures of $\S5.00$ per $\S1, 000$ in aggregate principal amount of the Debentures (the "consent payment") held by such consenting holders ,  upon or promptly following expiration of the Consent Solicitation. Only registered holders of the Debentures on the January 4,  2007 record date that validly deliver,  and do not revoke,  consents prior to 5:00 p.m. New York City time on January 17,  2007,  the expiration of the Consent Solicitation,  will be eligible to receive the consent payment.

The consummation of the Consent Solicitation (including the payment of the consent payment) is subject to the receipt of valid consents in respect of a majority in aggregate principal amount of all outstanding Debentures ,  the execution of the supplemental indenture by us and the trustee under the Indenture,  and the absence of any existing or proposed law or regulation or any proceeding that would make unlawful or invalid or enjoin or delay the proposed amendment,  the entering into of the supplemental indenture or the payment of the consent payment.

Why limit bond holders’ rights this way? Suppose you didn’t,  and instead let any bondholder demand immediate repayment after any infraction

X May not be best for bond holders,  particularly if they are junior x A bondholder may not realize this,  or may have a conflict of interest x Trustee is charged with taking the prudent action o Of course,  the trustee might misjudge or have conflicts of its own,  which is why there is the override provision

Why does this limitation apply to covenant defaults but not to financial defaults?

X Legal Answer: This is required by the Federal Trust Indenture Act o Mandates that each bondholder has the inalienable right to get his principal and interest on time x Economic Answer: Bond holders can actually benefit when it is hard for the firm to negotiate with them. More on this later.

# How the Contract can be Changed by a Vote

Under Modification and Waiver ,  the indenture reads

We and the trustee,  at any time and from time to time,  may modify the indenture in respect of the notes without prior notice to or consent of any holder of the notes for any of the following purposes:

X to permit a successor corporation to assume our [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] and obligations under the indenture and in the notes in accordance with the terms of the indenture; x to add to our [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] for the benefit of the holders of the notes; x to surrender any of our rights or powers conferred in the indenture; x to add any additional events of default; x to supplement any of the provisions of the indenture to the extent needed to permit or facilitate the defeasance and discharge of the notes in a manner that will not adversely affect the interests of the holders of such notes in any material respect; x to provide for the acceptance of appointment by a successor trustee with respect to the notes and to add to or change any of the provisions of the indenture as is necessary to provide for the administration of the trust by more than one trustee; x to comply with the requirements of the SEC in connection with qualification of the indenture under the Trust Indenture Act; x to cure any ambiguity; x to correct or supplement any provision in the indenture which may be defective or inconsistent with any other provision in the indenture; x to eliminate any conflict between the terms of the indenture and the notes and the Trust Indenture Act; or x to make any other provisions with respect to matters or questions arising under the indenture which will not be inconsistent with any provision of the indenture as long as the new provisions do not adversely affect in any material respect the interests of the holders of the notes.

We may also modify the indenture in respect of the notes for any other purpose if we receive the written consent of the holders of not less than a majority in principal amount of the outstanding notes. However,  we may not,  without the consent of the holder of each note affected thereby;

X change the stated maturity or reduce the principal amount or the rate of interest,  or extend the time for payment of interest of the notes or any premium payable upon the redemption of the notes,  or impair the right to institute suit for the enforcement of any payment on or after the due date thereof (including,  in the case of redemption,  on or after the redemption date),  or alter any redemption provisions in a manner adverse to the holders of the notes or release any Subsidiary Guarantor Subsidiary Guarantee) or collateral,  if any,  securing the notes (except in accordance with the terms of the Indenture or the documents governing such collateral,  if any); x reduce the percentage in principal amount of the notes where the consent of the holder is required for any such amendment,  supplemental indenture or waiver which is provided for in the indenture; or x modify any of the waiver provisions,  except to increase any required percentage or to provide that certain other provisions of the indenture cannot be modified or waived without the consent of the holder of each outstanding note which would be affected.

What this says is,  the issuer can change almost anything in the indenture if a majority of the bond agrees (the text in green ). What they can’t change,  due to the Trust Indenture Act,  is anything having to do with timely payment of principal and interest (the text in red ). That can be amended only with a unanimous vote.

Holding a vote to remove [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] and other contract features turns out to be a useful tactic for distressed firms,  which we will cover in detail. For now,  notice that one could seriously damage the value of a bond without changing its principal,  interest or maturity

X For example,  with this bond,  one could remove the part of the indenture that says the bond is senior,  and instead make it junior

The law does not mandate that [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] be changeable by majority vote. An indenture could require a $\%$ vote or some other super majority,  and it could also require a unanimous vote.

# Defeasance

Essentially all [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]] allow for defeasance and discharge:

Defeasance and Discharge. The indenture provides that we may be discharged from any and all obligations under the notes other than: x certain obligations to pay additional amounts,  if any,  upon the occurrence of certain tax,  assessment or governmental charge events regarding payments on the notes; x to revister the transfer or exchange of the notes; x to replace stolen,  lost or mutilated notes; or x to maintain paying agencies and to hold money for payment in trust.

# We may only defease and discharge all of our obligations under the notes if

x we irrevocably deposit with the trustee,  in trust,  the amount,  as certified by an officers’ certificate,  of money and/or U.S. government obligations that,  through the payment of interest and principal in respect thereof in accordance with their terms,  will be sufficient to pay and discharge each installment of principal and premium,  if any and any interest on,  and any mandatory sinking fund payments in respect of,  the notes on the dates such payments are due; and x we deliver to the trustee an opinion of counsel or a ruling from the United States Internal Revenue Service,  in either case to the effect that holders of the notes will not recognize income,  gain or loss for United States federal income tax purposes as a result of such deposit,  defeasance and discharge.

In other words,  the issuer can get out of,  i.e. be discharged of,  whatever it committed to in the indenture by arranging for the bond to be paid by a trust containing sufficient securities,  i.e. to be defeased . So the firm will

X Assemble a portfolio of government bonds whose scheduled payments will pay off the bond x On or before each coupon or principal repayment date of the bond,  the portfolio pays at least as much as the scheduled payment x Place this portfolio in an irrevocable trust which is directed to use the portfolio’s payments to make the remaining payments on the bond x The investors in a defeased bond would regard it as riskless,  and it would trade at something very close to the Treasury yield x By the same token,  the cost of the portfolio of Treasuries is the present value of the bond’s future payments,  discounted at the Treasury rate

If the bond’s indenture gives the issuer the right to defease the bond,  then the issuer is no longer bound by the [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] after defeasance

Connection between defeasance and make-whole call options:

If MGM were to exercise its make-whole call option,  it would pay bond holders the present value of its bond’s future payments,  discounted at the Treasury rate plus 50 bp

X If MGM were to defease the bond,  it would buy the portfolio of Treasury bonds. The cost is the present value of its bond’s future payments,  discounted at the Treasury rate. By construction,  this is a somewhat higher cost

The net effect of exercising the make-whole option is the same as the net effect of defeasing the bond

X After exercising the make-whole option,  the bond is gone x After defeasing the bond,  it is effectively gone – the payments to bond holders will come from the trust,  not from MGM,  and the [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] are no longer in effect

From the bond holders’ point of view,  the two strategies are very similar

X With the make-whole call,  they get an amount slightly less than the present value of the future payments discounted at the Treasury rate x With the defeasance,  they get a bond that is now as safe as a Treasury bond,  but isn’t a Treasury bond. It is still an MGM note,  and is probably somewhat illiquid Which do they prefer? They might actually prefer the

 Make-whole call,  depending on how close the defeased bond trades to the

 Treasury rate. In any case,  they are very similar.

Business 35202

# Class Note 3

Financial Inter mediation and Delegated Loan Monitoring: Bank Asset Services This continues the discussion from class note 2

# Financial Inter mediation

If there is a small supply of large investors who can lend 1 on personal account and then monitor (fewer such investors than profitable large projects),  and no way to delegate monitoring,  then some projects that would benefit from monitoring would be financed with non-monitored,  publicly-traded,  debt.

I want to show how financial intermediaries can be set up to create synthetic large investors. There will be a profit opportunity to set up such intermediaries if none are present and there is a short supply of large investors. If there are few large investors and no intermediaries then we saw in class note 2 that loans are made at $31.25\%$ and finding a way to make monitored loans at $31.25\%$ can allow a banker to make a profit. Of course,  if other banks can enter and compete,  the loan rates will be pushed down.

# The Example from class note 2

Suppose that there are no large investors,  only small investors each with 0.\1 $(\mathbb{S}100)$ to lend,  and 10, 000 small lenders are needed to finance 1 $\mathfrak{S}1$ million). Suppose the cost of monitoring 0.0002 $(\S200)$ for each. If each of 10, 000 lenders were to monitor whenever there is a default on the loan,  the cost would be 2,  which is prohibitive,  and no one would monitor. When monitoring cost is prohibitive,  the optimal contract is publicly-traded debt with face value 1.3125 (see class note 2). Delegating monitoring to one agent avoids the duplication,  but causes incentive problems for the agent delegated the monitoring task. Small lenders will not observe the effort put into monitoring,  or the information monitored by the agent. The agent (let's call him or her "the banker") has a conflict of interest with the small lenders. The conflict is similar to the conflict of interest between the borrower and the small lenders. How can the monitoring task be delegated without the need to monitor the monitor? Answer: The banker can face liquidation as a function of the amount paid to the 10, 000 small lenders.

# Delegated Monitoring Requires Diversification: the one-loan bank

Suppose that the banker monitors a single loan (runs a one-loan bank) on behalf of the small lenders,  and does not diversify across loans. When the borrower’s project returns 1,  the banker can monitor and collect the 1 without actually liquidating. However,  the bank itself would need to be liquidated in this case,  because the face value of the bank’s debt must exceed 1. If the bank’s debt contract with the small depositors has a face value of 1 or less,  the small depositors never receive more than 1,  which delivers less that the 1.05 expected repayment they need to receive the required $5\%$ expected return. If the bank is liquidated when its loan defaults by paying 1,  the bank is liquidated whenever the borrower would have been liquidated,  had the borrower used publicly-traded debt. Unless the 10, 000 lenders each monitor the banker (costing 0.\1 each,  or a prohibitive total of 2),  the one-loan bank will default and be liquidated just as often as the borrower. This seems to imply that delegating the loan monitoring to the banker will not succeed.

# Can the banker use diversification to reduce delegation costs?

# The two-loan bank

Suppose the banker monitored not one loan,  but a diversified portfolio of loans. A very simple way to show the value of diversification is to examine the two-loan bank.

In particular,  suppose the banker monitors loans of two borrowers,  whose returns are independently distributed but are otherwise just like that of the single borrower (each loan has a 0.\1 probability of returning 1.4 and 0.\1 probability of returning 1). The banker attracts 2 ( $\mathfrak{F}2$ million) in "deposits" from 20, 000 investors and lends it out to two different borrowers.

The banker gives each borrower a debt contract with face F ( $\$ F$ million) and collects F when the borrower has 1.4 and monitors to collect 1 when the borrower has 1. As a result,  the banker does not need to use costly liquidation to enforce his loan contract with either borrower. The banker issues deposits that are like publicly-traded debt: the bank is liquidated whenever it pays less than face value to any investor. This is the best contract because it requires no monitoring by the 20, 000 small investors. Let B denote the face value of bank deposits per loan,  implying that the two-loan bank has total deposits of 2 B,  and each 0.0001 $(\mathbb{S}100)$ deposit has face value $\mathrm{\frac{1}{10, 000}\, B}$ .

Suppose the banker monitors both loans. If both borrowers pay if full,  the bank will

receive 2 F. If one defaults but not the other,  the bank will receive $\mathsf{1+F}$ . If both default,  the bank will receive 1 from each,  or 2. The diversification from having two borrowers borrow from the bank will reduce agency costs. The distribution of payments to the bank,  if the banker monitors,  is:

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/fc39cfc6f2ddba6d8a18391633b8acf98ccfbfdab94b58021da1a905de81f0cc.jpg)

Assume that liquidating the bank yields nothing to depositors or to the banker,  similar to the liquidation of borrowing firms. The bank has total face value of deposits of 2 B. If the bank must be liquidated when it collects face value of F from one borrower and 1 from the other,  it will be liquidated whenever at least one loan defaults,  and there will be no possible savings in costs of financial distress. Alternatively,  if the bank can and will pay its deposits when exactly one loan defaults,  it defaults only when both loans default,  and can reduce the probability of liquidation to $0.04{=}(1{-}\mathsf{P})^{2}$ . To examine when payment of all deposits is possible when just one loan defaults,  the total payment received by all depositors will be 2 B with probability 0.\1 and 0 with probability 0.\1. The expected payment is . $96(2)\mathsf{B}$ . The initial capital needed to make two loans is 2 ( $\S2$ million),  and it requires a $5\%$ expected rate of return,  implying that . $96(2)\mathtt{B}{=}2(1.05)$ ,  or $2\, \mathsf{B}\!\!=\!\!2.1875$ is the promised payment to 2 ( $\S2$ million) in deposits. Equivalently,  let the promised interest rate on bank deposits be $\mathsf{r}_{\mathsf{B}}$ ,  then from 2 B $\scriptstyle=2(1+\mathsf{r_{B}})=2(1.09375)$ )=2 (1.09375) the promised interest rate on the bank deposit is $9.375\%$ .

If the bank is to be able to pay 2.1875 when one loan defaults (paying 1) and the other does not default (paying F),  then $\mathsf{1+F}$ must be at least 2.1875,  and the face value of each loan must satisfy $\mathsf{F}\geq1.1875$ . If the bank made loans with this face value,  it could avoid liquidation with probability 0.\1. In summary,  if the bank monitors its loans,  it will have the cash and the incentives to pay bank deposits in full with probability 0.\1 so long as $\mathbf{\mathsf{F}}\geq\mathbf{\mathsf{1}}0.\1\mathbf{\mathsf{75}}$ ,  or the interest rate on bank loans is at least $\mathbf{18.75\%}$ .

# Will the bank monitor?

Without monitoring,  the bank would not be able to offer to take 1 when only 1 is available,  and would instead liquidate the borrower’s asset. Monitoring provides no benefit to the banker when all loans pay in full (monitoring is not needed to force a borrower to pay F) nor when all loans default (because the bank fails and is liquidated). If the banker obtains nothing whenever at least one loan defaults,  there will be no incentive to monitor. An incentive to

monitor requires that the increase in the bank’s expected payment exceed 0.0002 $(\S200)$ per loan. The banker’s return when just one loan defaults,  $\mathsf{1+F{-}2B}=\mathsf{1+F{-}2.1875}$ ,  times the probability of exactly one default,  0.\1,  must exceed 0.\1,  the cost of monitoring two loans. This works out to . $0004\ensuremath{\, \leq\, }0.\1(1\!+\!\mathsf{F}\!-\!2.1875)$ ,  or $\mathsf{F}\ge1.18875$ . So long as the interest rate on bank loans exceeds $\mathbf{18.875\%}$ ,  the banker is willing to invest $\pmb{\S400}$ worth of time to increase the value of his residual claim on the bank . If the loan rate were below $18.875\%$ ,  banking would be too unprofitable to make monitoring worthwhile.

The two-loan banker must earn a small profit in excess of the cost of monitoring. The need to provide the bank an incentive to monitor and to avoid bank failure when just one loan defaults (by cross-subsidizing the losses from the defaulting loan with the profit from the nondefaulting loan),  lead to profits for the banker delegated the monitoring of the loan. The banker will only monitor if it yields a profit,  and due to limited liability and limited wealth,  the banker never makes deposit payments in excess of loan repayments. The need to provide incentives puts a floor on the banker’s expected profit,  which is sometimes called a control rent,  because the banker’s control of decisions requires that the rent (profit) go to him. If further diversification is not possible,  either because there are just two loans or because a two-eyed banker can only monitor two loans,  bank profits cannot be driven to zero by competition. The two-loan bank has the following profits. The banker gets the residual claim above 2.1875,  or:

$2.3775-2.1875=\!0.19$ with probability 0.\1,  when neither loan defaults,

 $2.18875-2.1875{=}0.00125$ with probability 0.\1,  when one loan defaults,  and

0 with probability 0.\1,  when both loans default.

This works out to a total expected payment of 0.122 $(\S122, 000)$ ,  or (. 19 ) $0.\1\, \textrm{+}$

(. 00125) $0.\1{=}0.122$ . This is a return to the banker of 0.061 per loan,  which is in excess of

 0.\1. The cost per borrower of monitoring,  and the banker earns a control rent of 0.061 - 0.0002

 $=0.0608$ . 3 The delegation cost per borrower,  D,  equals the cost of financial distress of the bank or

$0.\1(1){=}0.\1$ ,  plus control rent to the banker of 0.\1,  or a total of 0.1008. All parties are better off with the banker as delegated monitor. The borrower prefers to borrow at $18.875\%$ from the bank,  versus $31.25\%$ direct. The investors get a $5\%$ expected return in either situation. The banker is happy with any claim with an expected payment above $\S400$ ,  and ends up with an expected payment of $\mathbb{S}122{, }000$ .

# Summary of Financial Inter mediation and Diversification

We considered three types of contracting arrangements:

1. No monitoring: a publicly traded debt contract with $\mathsf{f a c e}\!\!=\!\!1.3125$ for each borrower.
 1. Direct monitoring by investors,  which saves distress costs of $\tt S\mathrm{=}0.\1$ but costs 2.
 1. Delegated monitoring by an intermediary,  which saves distress costs $\tt S\mathrm{=}0.\1$ at monitoring plus delegation cost,  0.\1.

Diversification within the intermediary works to make option 3 work by reducing the liquidation cost of providing the bank an incentive to repay small investors. To simplify,  we use an example where the diversification from a bank making only two loans was sufficient to give the bank reduced delegation costs. However,  it is more generally true that diversification allows financial inter mediation to provide low cost delegated monitoring. The law of large numbers implies that if the bank gets sufficiently diversified across independent loans with expected repayments in excess of the face value of bank deposits,  then the chance that it defaults on its deposits gets arbitrarily close to zero. In the limit of a perfectly diversified bank,  the bank would never default and would face no liquidation costs. In addition,  the control rent needed to provide incentives to monitor approaches zero. The delegation cost for the bank approaches zero,  and the only cost of inter mediation is the (unavoidable) cost of monitoring. Competitive and fullydiversified inter mediation would drive borrowers’ expected cost of capital down to $5.02\%$ . In the limit of perfect diversification,  the face value of bank debt approaches $\mathsf{F}\!\!=$ 1.06275 which is the solution to . $\begin{array}{r}{8\mathsf{F}+0.\1(1)\!\!=1.0502;}\end{array}$ ; it gives the bank a $5\%$ expected return after covering the 0.0002 $(\S200)$ cost of monitoring. This is too strong because in practice the default risk of borrowers is not independent,  but is positively correlated,  and because the number of loans in the bank’s portfolio is limited.

# Mathematical Appendix: The General Case for monitoring versus not monitoring

If you don’t like math,  don’t read this. It is not required. Some students like to see more generally what is making things work. This year I have yielded to these requests. Do not memorize these as formulae-- they will rot your brain.

This appendix briefly generalizes the example given above. The derivation is only sketched because the details are provided with the example given above.

# Publicly traded debt without monitoring

Debt uses the threat of liquidation to get the borrower to pay. Recall that the realized payoff of the project is $\vee$ (either $\scriptstyle{\bigvee}=\mathsf{H}$ or $\scriptstyle{\bigvee}=\mathsf{L}$ ),  and that the probability that $\scriptstyle\forall=\mathsf{H}$ is P. The lenders will get an expected repayment of: Pf if f is between H and L,  or $\boldsymbol{\mathsf{f}}, $ ,  if f does not exceed L. This implies that the lowest face value,  f,  that provides an expected repayment of $\uparrow+\mathsf{r}$ is given by: $$\begin{array}{r l}&{\mathrm{~\frac{l+r}{P}~}\quad\mathrm{if~L<l+r~}}\\ {\mathrm{f=\Omega\}}\\ &{\mathrm{~\l~l~+r~}\quad\mathrm{if~L\gel+r~}, }\end{array}$$

so long as this value of f does not exceed H. If it exceeds $\mathsf{H}$ ,  the borrower cannot raise publiclytraded debt.

If there is never default on debt (because ${\mathsf{L}}\geq1\!+\!{\mathsf{r}})$ ,  there is no cost of financial distress. I assume that the borrower cannot issue default free debt $(\mathsf{L}\!<\!1\!+\!\mathsf{r})$ ,  but the borrower can raise risky publicly-traded debt ( $\mathrm{H}>\frac{\mathrm{1}+\mathrm{r}}{\mathrm{P}}$ ). Publicly-traded debt’s cost of financial distress is then given by ${\mathsf{S}}{=}{\mathsf{L}}(1{-}{\mathsf{P}})$ ,  because L is the loss from inefficient liquidation when $\scriptstyle{\bigvee}=\mathsf{L}$ ,  and the probability of this is $\mathsf{1-P}$ .

When there is a cost to financial distress there is value to monitoring to avoid it. The saving due to monitoring is S,  because a lender who monitors does not need to liquidate when $\scriptstyle{\bigvee}=\mathsf{L}$ . Monitoring and restructuring the debt outside [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] increases the borrower’s payment when the project returns L from 0 to L. Monitoring can make both borrower and lender weakly better off if its cost is less than the cost of financial distress,  $\mathsf{S=}(1\mathrm{-}\mathsf{P})\mathsf{L}$ .

If there were many large investors willing to make and monitor loans of size 1,  then monitoring would be used whenever its cost is below S. Suppose instead that all investors have wealth of $1/{\mathfrak{m}}$ and that ${\mathsf{m}}\to\infty$ ,  implying that all investors are small and the costs of direct monitoring are very large $(\mathsf{m K}{\rightarrow}\infty)$ ). Some projects will need to be funded by publicly-traded debt,  unless there is a way to delegate monitoring.

As before,  financial inter mediation is a way to delegate monitoring by manufacturing synthetic high-wealth investors. Delegated monitoring by one banker takes place without any monitoring of the banker,  because monitoring the banker costs mK. If the bank is liquidated,  the value to depositors is zero,  similar to the conclusion about liquidation of a borrower’s assets. The banker’s cost of monitoring is K per loan. As we saw above,  when an un monitored borrower’s project returns L a lender receives a payment net of liquidation costs of 0. With monitoring the payment is L. Let the face value of a bank loan (a loan from the banker) be given by F,  to distinguish it from the face value of a publicly traded bond,  with face value f. Delegated monitoring banking is feasible only if the borrower,  lenders and the banker can be made at least as well off as with publicly traded debt,  and when the banker is provided with the proper incentives.

A bank that monitored a single loan with face value F would issue deposits to m lenders to raise the amount 1. The total face value of bank debt (per loan) is B,  and there is one loan so total face value is B. Whenever the bank does not pay B,  the bank is liquidated. Using the

Bank to monitor is not a free method of making the value of V known to the public by liquidating the bank. The bank will need to diversify in order to act as a delegated monitor. This is because a bank that did not diversify would need to default on its claims whenever its single loan defaulted. I examine the diversification of making two independent and identically distributed loans,  with face value F each. The bank raises deposits from 2 m lenders,  and these deposits have total face value of 2 B.

The face value of each loan is F. The constraint that the borrower not default when $\scriptstyle{\bigvee}=\mathsf{H}$ is:

The bank will provide an expected return of exactly r to each depositor if the face value per loan is given by: $$\mathrm{B}\;=\;{\frac{(1+\mathrm{r})}{1\;-\;(1-\mathrm{P}\, )^{2}}}.\;\;\;\;\;(\mathrm{Facc~value~of~brank~deposits, ~per~loop})$$

When one of the bank’s two loans defaults,  and it has monitored,  it will collect $\mathsf{F}{+}\mathsf{L}$ . The bank owes deposits of 2 B. The bank will have the ability and incentive to pay its deposits when one of two loans default if and only if $\mathsf{F}\!+\!\mathsf{L}\ge\,  2\mathsf{B}\!\!=\!\! 2 (1\!+\!\mathsf{r})/[1\!\!-\!\! (1\!-\!\mathsf{P})^{2}\, ]$ ] or $$\mathrm{F\!\geq\!\frac{2 (1\!+\! R)}{1\!-\! (1\!-\! P)^{2}}\!-\! L\!\equiv\! F_{\mathrm{pav}}}.\quad\mathrm{(brank~can~pav~deposits~with~one~default)}$$

In addition,  the banker must have incentives to monitor the loans. The cost of

Monitoring is incurred before the banker knows the return of the loan. When neither loan defaults,  there is no effect of monitoring on the banker’s receipts. When both loans default,  the bank must default on its deposits,  leading to liquidation giving the bank zero,  and again there is no benefit to the banker from monitoring. When exactly one loan defaults,  the banker’s payoff if he monitors and repays the deposits is $\mathsf{F}\!+\!\mathsf{L}\!-\! 2\mathsf{B}$ ,  while if the banker does not monitor the payoff is 0. Taking the expectation of the increase in the banker’s payoff and subtracting the cost of monitoring 2 loans implies that when the banker has incentives to monitor,  and the bank is not to fail when only one loan defaults,  it must be true that:

$2\mathsf{P}(1\!\!-\!\!\mathsf{P})\{\mathsf{F}\!\!+\!\!\mathsf{L}\!\!-\!\! 2\mathsf{B}\}\!\!-2\mathsf{K}\ge 0$ ,  or $$\mathrm{F}\, {\ge}\, \frac{\mathrm{K}}{\mathrm{P}(1\, {\cdot}\, \mathrm{P})}\, +\, \frac{2 (1+\mathrm{r})}{1\, {\cdot}\,  (1\, {\cdot}\, \mathrm{P}\, )^{2}}\, -\, \mathrm{L}\, {\equiv}\, \mathrm{F}_{\mathrm{IC}}\, .$$

Because of the cost of monitoring,  $\mathsf{K}\!\!>\!\! 0$ ,  the incentive to monitor is the binding constraint,  and $\mathsf{F}_{\mathsf{I C}}\!>\!\mathsf{F}_{\mathsf{P a y}}$ . For the two-loan bank,  the face value of each loan is $\begin{array}{r}{\mathrm{F=F_{IC}=\frac{K}{P (1\mathrm{-}P)}~+~\frac{2 (1+r)}{1\mathrm{-}(1\mathrm{-}P)^{2}}~-~L}}\end{array}$ . The bank loan is cheaper for the borrower if $\mathsf{F}\leq\mathsf{f}=\frac{\mathsf{1+r}}{\mathsf{P}}$ ,  or $$\mathrm{K}\leq\frac{\mathrm{P}(1\, {\cdot}\, \mathrm{P})[1+\mathrm{r}{\cdot}\, \mathrm{L}(2\, {\cdot}\, \mathrm{P})]}{2\cdot\mathrm{P}}.$$

One can show that the delegation cost of monitoring declines as the bank becomes more diversified,  but in cases where the number of independent loans is above 2 the equations become a bit messy. The easiest way to show the benefits of increased diversification is the show what happens as N,  the number of independent loans monitored,  gets arbitrarily large.

# The Limiting Case: Fully Diversified Banks

Suppose the bank became so diversified that a proportion exactly equal to $\mathsf{P}$ of its loans were able to pay in full and $\mathsf{1-P}$ could not. The bank will face no uncertainty,  and will either always default or never default. Unless it will always default,  the well-diversified bank can borrow at the riskless rate of interest. If the average amount of loan payments received per loan,  were less than ${\sf I}\!+\!{\sf r}, $ ,  the bank would default. When the average exceeds $\uparrow+\mathsf{r}$ ,  the bank will repay $\uparrow+\mathsf{r}$ per unit of deposits.

If the bank can pay $\uparrow+\mathsf{r}$ per loan with monitoring,  then at the margin it will keep all of the gains from monitoring,  and will monitor.

If the bank monitors all of its loans with face value F,  incurring cost K per loan and paying $\uparrow+\mathsf{r}$ in deposits per loan,  it will receive an average payoff per loan of exactly $\mathsf{P F}+(1\!\!-\!\!\mathsf{P})\mathsf{L}-(1\!\!+\!\!\mathsf{r})-\mathsf{K}$ . The banker will receive a non negative profit from making and monitoring loans so long as this is non negative or:

$\mathrm{~F~}\geq\mathrm{~}\frac{1+\mathbf{r}\!+\!\mathrm{K}\!-\! (1\!-\!\mathrm{P})\, \mathrm{L}}{\mathrm{P}}$ . (minimal compensation for a monitored loan)

The value of the minimum face value of a publicly-traded non-monitored loan,  $\mathsf{f}\!\!=\!\!\frac{\mathsf{1}\!+\!\mathrm{r}}{\mathsf{P}}$ ,  is the lowest such that an expected return of $\uparrow+\mathsf{r}$ is received without monitoring. If the bank makes loans with face value below $\textstyle{\frac{1+\mathrm{r}}{\mathrm{P}}}$ ,  the bank will fail if it monitors none of its loans. As a result,  if the bank monitors none of its loans,  the banker receives nothing. For any face value of bank debt where it is preferred by borrowers to non-monitored debt,  the banker will receive at least as much profit from monitoring all of its loans as monitoring none.

To compare the banker’s profit from monitoring some of its loans,  note there is a positive fraction that it must monitor to avoid failure. If the fraction of loans monitored is $\upmu$ ,  and the bank does not default given the fraction,  the banker’s payoff is PF $\mathsf{+(1\mathrm{-}P) u\ L-(1\mathrm{+}r)-}\mathsf{u K}, $ ,  which is increasing in $\upmu$ if monitoring is worth its cost or $({\mathsf{1}}{\mathrm{-}}{\mathsf{P}}){\mathsf{L}}{\mathrm{>}}{\mathsf{K}}.$ . When monitoring is worth its cost,  the banker prefers to monitor all loans and the optimal value of $\upmu$ is 1. In the limit where the bank is perfectly diversified,  the face value of a loan is $\operatorname{F}=\;{\frac{1+\mathbf{r}+\mathbf{K}{\mathbf{-}}(1\mathbf{-}\mathbf{P})\operatorname{L}}{\mathbf{P}}}$ ,  because otherwise a competing intermediary can be set up with a positive profit. The expected return received by the bank is $\mathsf{1}\!+\!\mathsf{r}\!+\!\mathsf{K}$ ,  just enough to cover its cost of capital,  $\uparrow+\mathsf{r}$ ,  plus its monitoring cost,  K.

University of Chicago Booth School of Business

Financial Markets and Institutions Business 35202

# Class Note 4: Restructuring debt outside bankruptcy

We have seen that because public bond holders cannot make informed concessions outside bankruptcy,  a structure of all public debt will get into [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] court too often. The reasons are the individual bond holders' lack of information and the U.S. Federal trust indenture act. In practice,  there is almost never a successful vote on these issues on public bond issues in the United States.

All private placement debt with a single lender would avoid this problem. However,  the single bank lender solution is sometimes too expensive because of bank operating costs and reserve requirement type taxes on inter mediation. In addition,  for large borrowers,  the single bank lender solution cannot be used because individual banks have a lending limit of $100\%$ (or less) of their capital to a single borrower. Further,  with only one lender,  that lender may have too much power,  from the borrower's point of view. In practice,  large borrowers have both public and bank debt. We now examine how the inability to renegotiate public debt outside [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] influences the [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] decision for borrowers with public and bank debt. There are two lenders: one bank,  one public.

# 1. NO PUBLIC DEBT CONCESSIONS AT ALL

The easiest case is when the public can never make a concession. This implies the use of [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] court and possibly liquidation whenever there is a default. The only party who can make concessions outside [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] is the bank lender. In practice,  the bank loans are short term and senior,  the public is long term and junior to the bank . Later in the course,  we will examine why this is the structure that is commonly used. For now,  we will just look at the structure's implications for [[Class Slide 4-Restructuring Debt Outside Bankruptcy|Restructuring Debt]] outside bankruptcy. If the public never makes a concession,  the bank decides whether to make a concession of its own to stay out of bankruptcy,  or instead to force the borrower into bankruptcy. If the bank forces bankruptcy,  then it is paid from the [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] proceeds by its specified priority (it is senior). The bank debt is maturing today and needs to be refinanced. The public debt is long-term,  and matures in the future.

The future ("date 2") value of the firm is 2,  1,  or 0,  with probability ${\bf q}_{2}, \, {\bf q}_{1}$ ,  and ${\bf q}_{0}$ respectively. The current going concern value of the firm is then $2\mathbf{q}_{2}+\mathbf{q}_{1}$ .

Let ${\bf q}_{2}{=}. 2$ ,  ${\bf q}_{1}{=}. 6$ and ${\bf q}_{0}{=}. 2$ . The going concern value,  $\mathrm{V_{GO}}$ ,  is the $2 (. 2)+. 6 (1)=1.0$ .

If the firm gets into [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] court,  some going-concern value is destroyed. Let L be the value if the firm gets into bankruptcy. This can be interpreted as the value that the firm will sell for if liquidated,  or the value under current management net of direct and indirect costs of bankruptcy. The face value of maturing bank debt is B,  the face value of public debt (which matures in the future,  on date 2) is P.

# Example 1: Going concern value may be lost

Let the value in [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] be $\mathrm{L}{=}. 4$ (this example holds for all L exceeding 0.\1).

The going concern value,  $\mathrm{V_{GO}}$ ,  is 1,  but this can be achieved only if the bank does not force [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] now. There are two ways the firm can avoid bankruptcy ,  it can fully repay the bank,  or it can convince the bank to make a concession.

The Bank is owed $\mathbf{B}{=}. 3$ and the loan matures today. The Public is owed $\mathrm{{P}{=}1.6}$ ,  maturing on date 2. There is no current interest payment owed the public (it has already been paid).

If the firm gets into [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] court,  the firm will be worth only $\mathrm{L}{=}. 4$ . The difference V $\mathrm{V_{GO}}\cdot\mathrm{L}{=}1\cdot. 4=. 6$ is the going concern value at risk if no agreement can be reached outside bankruptcy.

Suppose that the bank extends the maturity of its loan to date 2,  and keeps the face value equal to 0.\1. It is senior,  and gets paid 0.\1 when the firm is worth 1 or 2. Therefore it will get 0.\1 with probability 0.\1,  and the claim is worth . $8 (. 3){=}. 24$ . The bank would not accept this because it can get paid in full by forcing bankruptcy (it is senior,  and L exceeds B).

There is a third option (besides [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] or extending maturity with face 0.\1). This is to extend maturity and increase the face value of the debt (increase the interest rate). However,  the existence of the public debt limits how much the bank can obtain by increasing the face value.

The public debt has a covenant that prohibits issuing future debt that is senior to it (this is sometimes called a "me first" rule). Although the bank debt is senior to the public debt,  the me first rule limits the part of the future cash that can go to the bank. The bank has a senior claim of $\mathbf{B}{=}. 3$ ,  then the public has a claim on $\mathrm{{P}{=}1.6}$ . Any new claims that the borrower issues (to the bank or to other lenders) must be junior to the public.

This implies that the most the bank can receive from the borrower at date 2 is 0.\1. It can get 0.\1 by extending the maturity of the senior claim that it already has. Any other claim would be junior to the public. The public's claim of 1.6,  plus the bank's senior claim of 0.\1,  adds up to 1.9. The maximum value

Of the firm is 2,  implying that at most an additional $2{\cdot}1.9{=}. 1$ can be paid to the bank. This 0.\1,  plus the 0.\1 senior claim add up to 0.\1.

If the bank took this junior claim on 0.\1 in addition to its senior claim on 0.\1,  its payoff would be as follows. If the firm is worth 1,  it would get 0.\1 (because its junior claim would be worthless). If the firm is worth 2,  it would get 0.\1. The expected value of its claim is then . $2 (. 4)+. 6 (. 3)=. 26.$ .

Because the bank can get $_\mathrm{B}{=}. 3$ (which is more than 0.\1) from forcing bankruptcy,  it will force [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] and destroy the going concern value.

The public can make no concessions. Therefore the public cannot prevent the bank from forcing bankruptcy,  and the going concern value will be destroyed.

# Example 2: Maybe Going Concern Value will be preserved

Example 2 a: Even more going concern value is at risk

Keep everything from the first example,  except make [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] even more inefficient. Let the value of the firm in [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] be $\mathrm{L}{=}. 2$ . Now the bank will not force bankruptcy. This is because the value of extending maturity and taking the junior claim of 0.\1 is worth 0.\1 (see above),  which is worth more than 0.\1. Suppose [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] is even more inefficient,  and $\scriptstyle\mathrm{L}=0$ . Then the bank would never force [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] when making a concession gives it something in the future.

Example 2 b: Less public debt,  but same total amount of debt (This puts the bank at sufficient risk)

Keep everything from example 1 except let the amount of bank debt be $_\mathrm{B}{=}. 5$ and the amount of public debt be $\mathrm{{P}{=}1.4}$ . Note that $\mathrm{L}{=}. 4$ . The amount of total debt is still 1.9,  but less of it is public debt. The public makes no concessions.

The bank can force [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] and get $\mathrm{L}{=}. 4$ (because the bank is senior). Alternatively,  it can extend maturity on its senior claim on 0.\1 to date 2,  and take an additional claim junior to the public. This junior claim is worth at most 0.\1 (2-1.9),  as in example 1. The value of the bank's claim if it does not force [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] is as follows. If the firm is worth 1,  it receives 0.\1. If the firm is worth 2,  it receives 0.\1 $(. 5+. 1)$ . The expected value of the bank's claim is $2 (. 6)+. 6 (. 5)=. 42$ . This exceeds the 0.\1 that the bank gets in bankruptcy.

What matters is the value at risk from going into [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] relative to the amount of public debt. It is not just the size of the value at risk. If the amount of public debt is large relative to the value at risk,  then the value at risk will be destroyed.

In the next class note,  we examine [[Class Note 6 Restructuring Public Debt Out of Bankruptcy Exchange Offers|Exchange Offers]] of one public debt issue for another as a way of forcing concessions by the public.

Financial Markets and Institutions Douglas W. Diamond Business 35202

# Class Note 5: US Bankruptcy Rules

Now I want to highlight some of the most important features of the rules when actually filing for [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] under chapter 11.

1. Automatic Stay of all Creditor claims . This prevents a rush to foreclose ahead of the other creditors,  which would have all creditors trying to get effective priority by getting paid first in time. This allows an orderly renegotiation of claims without giving excess bargaining power to the lenders whose claims are due immediately (or those who can call their loans and make them due immediately,  or trade creditors who can take away supplies to protect their claim).
1. [[Notes on Debtor-in-Possession DIP Financing|debtor in possession]] Financing. This allows new debt to come in senior to all unsecured debt in place before the filing. This allows the firm access to cash to continue operations. This would have been impossible outside [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] if the existing debt had negative pledge clauses that the existing lenders were unwilling to waive.
1. The [[Notes on Debtor-in-Possession DIP Financing|debtor in possession]] (typically the management) has the exclusive right to propose reorganization plans for the first 120 days of the bankruptcy. The [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] judge can extend this exclusive period. This gives the debtor substantial bargaining power because the firm's profits are reduced by longer periods in bankruptcy,  and the power to delay is then the power to destroy value. Other creditors are then willing to vote for plans that are more pro-borrower than they would be otherwise,  because if they vote no,  they must wait longer for a better plan to be proposed. It is rare and difficult for creditor-originated plans to be proposed even after the exclusive period expires. The rules require a formal appraisal only for creditor-proposed plans.
1. Voting not only can be used,  it must be used. Outside bankruptcy,  the trust indenture act prohibits a majority vote from imposing concessions on holdouts. The chapter 11 rules impose concessions on holdouts if $50\%$ of each class of lender,
Representing at least 2/3 of the dollar value of each class,  vote in favor of the plan. This imposes the will of the majority on minority holdouts. Note that only "impaired classes" get to vote. Classes that make no concessions and lose no priority or collateral then would not be able to vote. Because all impaired classes vote,  there will generally be violation of absolute priority among unsecured creditors in the form of larger than absolute priority payments to very junior classes to attract their vote. Absent a difficult to get “cram down, ” the junior creditors can delay and this makes it worth giving them something.

1. There is substantial discretion in setting up the definition of a class. Secured lenders are entitled to be a class by themselves,  but the plan proposed by the borrower has substantial freedom to choose how to group unsecured creditors into classes. This implies that the only sure way to get priority over another class is for the senior class to be secured.
1. Lenders do not accrue interest during bankruptcy. This provides them with an incentive to settle quickly. The only exception is secured creditors who are pledged collateral worth more than they are currently owed.
# Class Note  : Restructuring public debt out of bankruptcy: [[Class Note 6 Restructuring Public Debt Out of Bankruptcy Exchange Offers|Exchange Offers]] Includes Note  A: Coercive [[Class Note 6 Restructuring Public Debt Out of Bankruptcy Exchange Offers|Exchange Offers]] and exit consents at the end

The primary way that borrowers and banks try to get concessions from the public is to get the public to exchange their bond for one that requires a smaller payment (i.e.,  either a principal,  interest or maturity concession). Although the Federal Trust Indenture Act prohibits such concessions by voting,  it does not prohibit [[Class Note 6 Restructuring Public Debt Out of Bankruptcy Exchange Offers|Exchange Offers]].

Because the public consists of many small holders,  each holder may assume that he is so small that his decision to tender his bond for exchange will not influence the outcome of the exchange offer. As a result,  each decides by comparing the value of the new security with the value of the old security that is expected to prevail after the exchange offer. This evaluation of the future value is made by making a forecast of how much of the issue will be exchanged by other holders.

# Example 3: Public exchanges for junior securities tend to fail

Keep everything from example 1: going concern value of $\mathrm{V_{Go}}{=}1$ ,  bankruptcy value of $\mathrm{L}{=}. 4$ . The Bank is owed $\mathbf{B}{=}. 3$ and the Public is owed $\mathrm {{P}{=}1.6}$ The public is junior and long-term. If the public does not make a concession,  we saw in example 1 that the bank will force bankruptcy,  and the public will then get $_\mathrm{L-B=}4\mathrm{-}0.\1\mathrm{=}0.\1$ . Suppose that the public is offered the chance to exchange for a bond with face $\scriptstyle{\mathrm{P}} =1$ ,  and the bank agrees not to force [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] if the exchange succeeds. Suppose that the offer succeeds if $99\%$ of the bonds are exchanged. Let "f" denote the fraction of the total bond issue that you expect to be exchanged by other holders.

The key point in this example is to look at the case where the new bonds (with face $P^{\prime}{=}I_{c}$ ) are junior to the old bonds with face $\mathrm{{P}{=}1.6}$ . The bank's claim of 0.\1 remains senior to the public.

Suppose that you own $1\%$ of the old bonds,  with face value 0.\1. Your return from tendering of holding out depends on whether you expect the exchange offer to succeed in keeping the firm out of bankruptcy.

1. ' Suppose that you expect the offer to succeed,  for example because every other holder ' tenders,  and $\mathbf{f}{=}.\mathbf{99}$ . You choose between tendering and "holding out" by not tendering.

A. To determine what you get if you tender ,  do the following calculation. If you tender,  then all are tendered. Your new bond is paid ( $1\%$ of) 1 when the firm is worth 2,  and worth ( $1\%$ of) $1\!-\!. 3\!=\!. 7$ when the firm is worth 1 (this is because the bank has a senior claim on 0.\1). The expected value of this claim is ( $1\%$ of) $. 2 (1)+. 6 (. 7)=. 62$ . $1\%$ of 0.\1 is 0.\1.

B. If,  instead,  you hold out and refuse to tender the bond,  the offer will still succeed (because only $99\%$ is needed). Then your bond is senior to the public bonds that tender: you will get paid before those that tender when the firm is worth 1. The bank is first paid 0.\1,  leaving $1\!-\!. 3\!=\!. 7$ . This means you are paid the full face value of 0.\1 if you hold out instead of exchanging. You receive 0.\1 when the firm is worth 1 and when it is worth 2: as a holdout,  you receive 0.\1 with probability 0.\1,  an expected value of 0.\1. This exceeds the 0.\1 that you get from tendering your bond.

Therefore,  if you expect the exchange offer to succeed you will not tender because your claim will be worth more if you hold out! If all bond holders expect the offer to succeed,  none of them will tender. A prophesy that the offer will succeed is not self-fulfilling!

1. Consider the case where you expect the exchange offer to fail (less than $\bf{98\%}$ of bonds exchanged: ${\bf f}{<}.{\bf 98}$ ). If the offer fails,  the bank will force bankruptcy. The firm will then be worth $\mathrm{L}{=}. 4$ . After the bank is paid its 0.\1,  there remains 0.\1 to be divided among the public.

If you hold out,  and so does everyone else,  you get $1\%$ of 0.\1. If you hold out and anyone exchanges,  you get more than $1\%$ of 0.\1,  because the holdouts are senior and are paid first. If more than $93.75\%$ exchange (f>. 9375),  the holdouts (who are senior) get paid in full (then $1\mathrm{-f}{<}. 0625$ ,  and $6.25\%$ of $1.6=$ 0.\1).

If you exchange,  you get nothing if less than $93.75\%$ of the others exchange; holding out dominates this. If more than $93.75\%$ exchange,  the holdouts get paid in full,  and if you exchange for a reduced face value you do not,  implying that you prefer to hold out.

No matter what fraction of others you expect to exchange,  you prefer to hold out. One is always worse off with a junior claim with lower face value,  so here you would still not tender.

[[Class Note 6 Restructuring Public Debt Out of Bankruptcy Exchange Offers|Exchange Offers]] for junior securities with lower face value will always fail if aimed at small holders. The small holders each expect that their decision to exchange will not tip the balance between the offer succeeding (staying out of bankruptcy) and failing (going into bankruptcy). In the example,  you do not influence success unless you expect more than $98\%$ but less than $99\%$ of others to exchange. If you do not tip the balance,  you never prefer a new bond with lower face value and lower priority,  because it is never worth more than the old bond.

If,  instead,  the bonds you exchange for are equal in priority to the original bonds,  the same arguments apply. If the offer succeeds,  or if it does not,  you are better off with an equal priority claim of higher promised payment (which you get by holding out and not tendering),  because when there is equal priority the payment is proportional to the amount promised. You would only tender for a junior security if you though that your bond would tip the balance between the bank forcing [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] and not forcing bankruptcy.

Example 4: Public exchanges for Senior securities are more successful,  if allowed.

Keep everything from the last example,  except let the bonds with face $\scriptstyle{\mathrm{P}}=1$ offered to the public in exchange for their bonds with face $\mathrm {{P}{=}1.6}$ be senior to the original 1.6 bonds. This means that if you exchange for the new bond,  you will be paid prior to those who hold out. This added priority is not relevant when the firm is worth 0 (all bonds are worthless) or when the firm is worth 2 (both the bonds with face $\mathrm{{P}{=}1.6}$ and those with $\scriptstyle{\mathrm{P}} =1$ are paid in full). The added priority is useful when the firm is worth 1. I now examine the relative value of senior bonds with $\scriptstyle{\mathrm{P}}=1$ and junior bonds with face $\mathrm{{P}{=}1.6}$ ,  when the firm is worth 1.

As before,  suppose that you own $1\%$ of the bonds,  and you expect all of the other bonds to tender $\mathrm{(f{=}}. 99)$ . If you tender,  all of the bonds are tendered,  and you get $1\%$ of $1{\mathrm{-}}{\mathrm{B}}{=}1{\mathrm{-}}. 3{\mathrm{=}}. 7$ ,  or 0.\1. Your expected return from tendering is then ( $1\%$ of) ${\bf q}_{2}{\bf P}^{\prime}+{\bf q}_{1}(1{\bf-}{\bf B})=(1\%$ of) $2 (1)+. 6 (. 7)=(1\%$ of) 0.\1. This is 0.\1.

If you hold out,  then those who tender are senior to you. When the firm is worth 1,  the public as a whole gets $1{\mathrm{-}}{\mathrm{B}}{=}1{\mathrm{-}}. 3{\mathrm{=}}. 7$ . There are bonds with face value of $(99\%$ of) 1,  senior to you,  they are owed 0.\1,  but get only 0.\1. Therefore,  as a holdout you will get nothing when the firm is worth 1. By holding out,  you will get $\mathrm{{P}{=}1.6}$ when the firm is worth 2,  and nothing otherwise. Your expected payment from holding out is then ( $1\%$ of) $\mathbf{q}_{1}\mathbf{P}=(1\%$ of) 0.\1(1.6),  or 0.\1. This is less than the 0.\1 that you obtain from exchanging your bond. Therefore if you expect the offer to succeed,  you exchange. A prophesy that the offer to exchange will succeed is self-fulfilling.

When the new security offered in exchange is senior to the old,  there is a lower payment received by the old security whenever the new one is not paid in full. This is in contrast to the case where the new security is junior,  and the old one gets more than the new whenever the new is not paid in full. This makes small holders willing to join in the bond exchange. Exchanging for a senior security can put the bond holders in a rush to exchange to jump ahead of the holdouts. I will later show that rushing to exchange for something senior is very similar to a bank run.

Now consider what happens when the offer is expected to fail (less than $\bf{98\%}$ of the bonds are tendered: f<0.\1). If the exchange offer is expected to fail (leading to bankruptcy),  you will want to exchange. The reason follows. If you exchange you divide L  B $(=\!0.\1\!\!-\!0.\1\!\!=\!0.\1)$ with the others who exchange (a positive number). For example,  if others representing less than $9\%$ exchange,  and you exchange too (a total of $10\%$ or less exchange),  then those who exchange are paid in full (because those who exchange and are senior are owed less than 0.\1). You get $1\%$ of $1=0.\1$ if you exchange. If you hold out,  those who exchange get paid first,  and you divide $\mathrm{L-B-fP^{\prime}}=0.\1-\mathrm{f}, $ ,  among the other holdouts (unless $\mathrm{f}\!\!>\!. 1$ and this is a negative number,  and holdouts get nothing). The other holdouts represent a fraction 1-f of the bond issue,  and you represent a fraction 0.\1. If you hold out,  you then get a fraction 0.\1/(1-f) of L  B  fP $\mathit{\Pi}_{=. 1}$  f. If $\mathrm{f}{=}0$ ,  this is exactly 0.\1 ( $1\%$ of 0.\1),  and it is less than 0.\1 for all greater values of f. Therefore,  you will exchange. If you expect that f will exceed 0.\1,  you get nothing if you hold out,  and something positive if you exchange. For all values of f,  you are better off exchanging.

Coercive [[Class Note 6 Restructuring Public Debt Out of Bankruptcy Exchange Offers|Exchange Offers]] and exit consents . See the Kahan and Tuckman paper in the packet.

An exit consent vote is one where a change in [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] is combined with an exchange offer where a new bond is given in exchange for the old bond if and only if one votes to change the [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] in the old . As a result,  those who are exiting the old bond are the ones choosing to change its covenants. If a holder prefers the new bond given his or her belief that the vote will pass,  any reduction in the value of the old bond will not matter (because he or she will hold the new bond).

Suppose there is an exit consent vote that will pass if $\mathrm{M}{+}1$ bond holders vote yes and tender their bond in exchange for a new one. The deal is structured so that you may only get the new bond if you vote to change the [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] in the old bond to make it drop in value. If fewer than M other holders tender,  you can't make it pass,  if $\mathrm{M}{+}1$ or more tender,  it passes no matter what you do.

Value of bond as it stands $\scriptstyle\varepsilon=$ B

Value of new bond that you get if you tender,  vote yes and the vote passes: $\mathrm {{B_{n}} }$

Value of old bond if the consent vote passes (some [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] are removed): B'

Payment for consent vote,  in addition to new bond ${\boldsymbol{\mathbf{\tau}}}={\boldsymbol{\mathbf{p}}}$ . This is called the consent payment.

If you hold it all the issue,  you compare $\boldsymbol{\mathrm{p}}+\boldsymbol{\mathrm{B}}_{\mathrm{n}}$ to B.

There are N old bond holders,  it passes if $\mathrm{M}{+}1$ holders accept the new bond and vote to change the covenant.

If you expect less than M to accept,  you expect to have the tender fail,  and even if you tender you get the old bond back. As a result,  you get B no matter what. It does not matter if you tender or not.

If you hold the bond and expect more than $\mathrm{M}{+}1$ to accept and tender their bonds,  you get $\mathbf{B}^{\prime}$ if you keep the old bond,  and $\mathsf{p}\mathrm{+}\mathbf{B}_{\mathrm{n}}$ if you take the new one. Call this expecting the consent vote to succeed.

If you expect the consent vote to succeed,  you will tender if and only if $\mathbf{p}+\mathbf{B}_{\mathbf{n}}>\mathbf{B}^{\prime}$ .

This might be coercive,  if the old bond drops in value by more than the cash payment $(\mathtt{p}+\mathtt{B}_{\mathtt{n}}<\mathtt{B})$ .

You would tender here,  even though you would not if you owned the total bond issue. That is if $\mathrm {{p+B_{n}<B}} $ while $\mathbf{p}+\mathbf{B}_{\mathfrak{n}}>\mathbf{B}^{\prime}$ .

Example 1. Suppose there was no trust indenture act,  and the exit consent vote was to set the principal and interest of the old bond to zero: that is $\scriptstyle\mathbf{B}=0$ . Suppose that there is no consent payment,  $\scriptstyle{\mathfrak{p}}=0$ . And suppose that you expect the consent vote to succeed,  you tender if $\bf{p}+\bf{B_{n}}$ $\scriptstyle>\mathbf{B^{\prime}}$ ,  which is $\bf{B_{n}\!>\! 0}$ . You will take a bond worth a penny if you expect the old bond to be made worthless. Perhaps this is the scenario that made them pass the trust indenture act!

Example 2 If there are no covenant changes in the old bond,  the consent payment is zero,  and the new bond is junior to the old bond and has a lower face value,  as in class note 4. Here the offer will fail because the new bond is worth less than the old bond will be worth if others exchange their bonds: $\mathrm{B_{n}{<}B^{\prime}}$ .

Example 3 If there are no other covenant changes in the old bond,  the consent payment is zero,  and the new bond is senior to the old bond and has a lower face value,  as in class note 4,  then it is possible that the offer will succeed. The reason is that $\mathrm {{B_{n}} }$ may exceed $\mathbf{B}^{\prime}$ . In the example in note 4,  exchanging the old bond with face $\mathrm {{P}{=}1.6}$ for a new bond with face value $\scriptstyle{\mathrm{P}} =1$ resulted in success.

Suppose you own 1/100 of the old bond,  with face value 0.\1,  you are offered a new senior bond with face value 0.\1. If you expect everyone else to take the new bond,  we saw that their face value of 0.\1 will be senior to you,  and you get zero unless the firm is worth 2 in the future.

The value of the old bond,  $\mathbf{B}^{\prime}$ ,  drops to $0.2 (. 016)\, +0.8\left (0\right)=0.0032$

The new bond is worth $\mathrm{\DeltaB_{n}{=}0.2 (. 01)+0.6 (1{-}B)/100+0.2 (0)=\Delta 0.2 (0.1)+0.6 (0.007)=}$ 0.0062.

Thus the new bond is of higher value.

If the new senior bond had a smaller face value of $\scriptstyle\mathrm{P}=0.5$ ,  the offer would fail,  because it would not reduce the payment to the old junior bond in the case where $\scriptstyle{\mathrm{V}}=1$ . The new bond with face value $\scriptstyle\mathrm{P}=0.5$ is small enough that it will be paid in full when $\scriptstyle{\mathrm{V}}=1$ as well as $\mathrm{V}{=}2$ ,  because there is 0.7 left when $\scriptstyle{\mathrm{V}}=1$ after the bank takes 0.3. More importantly,  it allows the old (junior) bond to be fully repaid when $\scriptstyle{\mathrm{V}}=1$ .

Your 1/100 part of the new bond has face value $\scriptstyle\mathrm{P=}0.005$ and would be worth $\mathrm{B_{n}}{=}0.2 (0.005)+0.6 (0.005)+0.2 (0){=}0.8 (0.005){=}0.004.$

The old bond with face value 0.016 would be paid in full when $\mathrm{V}{=}2$ and when $\scriptstyle{\mathbf{V}}=1$ because there is 0.\1 left after the bank,  and $0.99 (0.5){=}0.495$ of debt is senior to you ( $99\%$ are assumed to take the 0.5 face value senior bond). This leaves $0.7\cdot 0.495{=}\,  0.205>0.016$ to pay your bond,  so the value of the old bond is:

$\mathrm{B^{\prime}}=0.2\ (0.016)+0.6 (0.016)+0.2 (0)=\!\! 0.0128$ . The loss of priority does not reduce the value of the old bond here.

Think of the extreme case where the new bond had zero face value. A bond with face value zero does not causes pain by coming in senior to you! In that case $\mathrm {{B_{n}} {=}0}$ and $\mathbf{B}{=}\mathbf{B}$ .

# Financial Inter mediation as Delegated Monitoring: A Simple Example

Douglas W. Diamond

B anks and other ﬁnancial intermediaries are the main source of external funds to ﬁrms. Intermediaries provided more than 50 percent of external funds from 1970 to 1985 in the United States,  Japan,  the United Kingdom,  Germany,  and France (Mayer 1990). Why do investors ﬁrst lend to banks who then lend to borrowers,  instead of lending directly? What is the ﬁnancial technology that gives the banks the ability to serve as middleman? To answer these questions,  this article presents a simpliﬁed version of the model in Financial Inter mediation and Delegated Monitoring (Diamond 1984). The results explain the key role of debt contracts in bank ﬁnance and the importance of divers i cation within ﬁnancial intermediaries. The framework can be used to understand the organizational form of intermediaries,  the role of banks in capital formation,  and the effects of policies that limit bank divers i cation.

Financial intermediaries are agents,  or groups of agents,  who are delegated the authority to invest in ﬁnancial assets. In particular,  they issue securities in order to buy other securities. A ﬁrst step in understanding intermediaries is to describe the features of the ﬁnancial markets where they play an important role and highlight what allows them to provide beneﬁcial services. It is important to understand the ﬁnancial contracts written by intermediaries,  how the contracts differ from those that do not involve an intermediary,  and why these are optimal ﬁnancial contracts. Debt contracts are central to the understanding of intermediaries. The cost of monitoring and enforcing debt contracts issued directly to investors (widely held debt) is a reason that raising funds through an intermediary can be superior. Debt contracts include contracts issued to intermediaries by the borrowers that they fund (these are bank loans) and the contracts issued by intermediaries when they borrow from investors (these are bank deposits). Portfolio divers i cation within ﬁnancial intermediaries is the ﬁnancial-engineering technology that facilitates a bank’s transformation of loans that need costly monitoring and enforcement into bank deposits that do not.

This article both simpliﬁes and extends the analysis in Diamond (1984). Adding an assumption about the [[Lecture 1- Probability Distributions of Returns|probability distribution]] of the returns of borrowers’ projects makes the analysis simpler. There are a few new results that extend the analysis because this article drops the assumption that non pecuniary penalties can be imposed on borrowers. The change of assumption implies that there is a minimum level of bank pro t ability required to provide incentives for bankers to properly monitor loans. This article is not a general survey of the ﬁnancial inter mediation literature. Two recent surveys are Hellwig (1991) and Bhatt acharya and Thakor (1993). For a survey of the role of debt in corporate ﬁnance,  see Lacker (1991).

Intermediaries provide services: this is clear because intermediaries issue “secondary” ﬁnancial assets to buy “primary” ﬁnancial assets. If an intermediary provided no services,  investors who buy the secondary securities issued by the intermediary might as well purchase the primary securities directly and save the intermediary’s costs. To explain the sorts of services that intermediaries offer,  it is useful to categorize them in terms of a simpliﬁed balance sheet. Asset services are those provided to the issuers of the assets held by an intermediary,  e.g.,  to bank borrowers. An intermediary that provides asset services is distinguished by its atypical asset portfolio. Relative to an intermediary that provides no asset services,  it will concentrate its portfolio in assets that it has a comparative advantage in holding. The model presented below provides a foundation for understanding this aspect of inter mediation,  showing that reduced monitoring costs are a source of this comparative advantage. There are other important aspects of inter mediation that we do not discuss here: liability services and transformation services. Liability services are those provided to the holder of intermediary liabilities in addition to the services provided by most other securities. Examples include the ability to use bank demand deposits as a means of payment and the personalization of contingent contracts available from life insurance companies. Some liability services,  such as check clearing,  are well understood,  while others relate to difﬁcult issues in micro economic theory regarding the role of money. Transformation services involve the conversion of illiquid assets into liquid liabilities,  offering improved risk sharing and better liquidity compared with investment in the assets held by intermediaries (see Diamond and Dybvig [1983] and Diamond [1995]). Although there may be interactions between these types of service,  this article focuses only on asset services.

If intermediaries provide asset services,  they provide services to borrowers who issue assets to them. That is,  it matters to the issuer of an asset that the asset is to be held by an intermediary rather than directly by investors. Some costs are lower if the asset is held by an intermediary rather than a large number of individuals. The imperfections that give rise to costs of issuing securities by primary borrowers also give rise to similar costs to an intermediary that issues deposits. I examine how a ﬁnancial intermediary acting as a middleman can lead to net cost savings,  and I develop the implications of this role for the structure of intermediaries. The model yields strong predictions about the contracts used by intermediaries and this provides a setting to analyze important issues in banking policy.

# 1. AN OVERVIEW OF FINANCIAL INTER MEDIATION: THE COSTS AND BENEFITS OF MONITORING

Theories based on the collection of private information by an intermediary require that there be some beneﬁt to using this additional information in lending. A key result in the agency theory literature is that monitoring by a principal can allow improved contracts. The net demand for this monitoring also depends on the cost of monitoring. This cost depends on the number of lenders who contract with a given borrower.

In contracting situations involving a single lender and a single borrower,  one compares the physical cost of monitoring with the resulting savings of contracting costs. Let $K$ be the cost of monitoring and $S$ the savings from monitoring. When there are multiple lenders involved,  either each must be able to monitor the additional information directly at a total cost of $m\times K$ ,  where $m$ is the number of lenders per borrower,  or the monitoring must be delegated to someone. Delegating the monitoring gives rise to a new private information problem: the person doing the monitoring as agent now has private information. It is not even veriﬁable whether the monitoring has been undertaken. Delegated monitoring can lead to delegation costs. Let $D$ denote the delegation cost per borrower. A complete ﬁnancial intermediary theory based on contracting costs of borrowers must model the delegation costs and explain why inter mediation leads to an overall improvement in the set of available contracts. That is,  delegated monitoring pays when $$K+D\leq\operatorname*{min}\, \left[S,  m\times K\right]\!, $$

Because $\textit{K}+\textit{D}$ is the cost using an intermediary,  $S$ is the cost without monitoring,  and $m\times K$ is the cost of direct monitoring.

The model in this article illustrates the more general results in Diamond (1984),  which analyzes delegation costs by characterizing the organizational structure and contractual form that minimize the costs of delegating monitoring to an intermediary. The ﬁrst step in studying the beneﬁts of inter mediation is to ﬁnd the best available contracts between borrowers and lenders if there is no intermediary and no monitoring. The optimal un monitored ﬁnancial contract between a borrower and lenders is shown to be a debt contract that involves positive expected deadweight liquidation costs which are necessary to provide incentives for repayment. The gross demand for monitoring arises because one can use lower cost contracts (with reduced liquidation costs),  if the project’s return can be monitored,  with an ex ante cost saving of S .

Monitoring is costly,  especially if duplicated. If not duplicated,  the act of monitoring must be delegated,  and then the information obtained is not publicly observed. As a result of the remaining information disadvantage of those who do not monitor,  there may be delegation costs associated with providing incentives for delegated monitoring. The best way to delegate monitoring is for the delegated monitor to issue un monitored debt,  which will be subject to liquidation costs. The delegated monitor is a ﬁnancial intermediary because it borrows from small investors (depositors),  using un monitored debt (deposits) to lend to borrowers (whose loans it monitors).

# 2. AN EXAMPLE OF OPTIMAL DEBT WITHOUT DELEGATED MONITORING

Consider a borrower who needs to raise a large quantity of capital. All lenders and borrowers are risk neutral,  but borrowers have no capital,  and each lender’s capital to invest is small relative to the amount needed to fund the borrower’s investment. The borrower needs to raise 1 (where the units are millions of dollars,  and these units will be mentioned only parenthetically),  while each investor has $1/m$ units to invest,  implying that a borrower needs to raise capital from $m$ investors if $m>1$ . The example assumes that $m$ is very large: $m=10{, }000$ ,  and each lender has capital or 0.0001 $(\mathbb{S}100)$ . Monitoring the borrower costs $K=0.0002$ $(\$ 200)$ ,  and duplicated monitoring by each of $m$ investors costs $m K=2$ and is prohibitively expensive. Because monitoring is expensive,  one should examine the best contract available without any monitoring.

Investors do not observe the borrower’s operations directly,  not even its sales or cash ﬂows. How can the lenders write a contract in which they do not need to monitor this information?

# The Best Contract without Monitoring

The ﬁrm needs to raise 1 ( $\$ 1$ million),  and each investor requires an expected return of $r=5\%$ . All lenders and the borrower agree that the borrower has a proﬁtable,  positive net present value project to fund,  but only the borrower will observe how proﬁtable it turns out to be. The borrower can consume any part of the project’s return that he does not pay out to the investor. The interpretation is that the borrower can appropriate the return to himself,  since no one else observes the project’s success. If the project is a retail store,  the borrower can take some sales in cash to himself. More generally,  the borrower can inﬂate costs. In practice,  the net cash ﬂows to the ﬁrm are very unobservable for many ﬁrms. In addition,  most other conﬂicts of interest faced by borrowers can be reinterpreted as equivalent to the borrower’s ability to retain under reported cash. The ability to retain under reported cash is simply the most extreme example of a conﬂict of interest.

The project costs 1 to fund,  and its realized value is a random variable with realization denoted by $V$ . The distribution of $V$ ,  the value of the project,  known to all borrowers and lenders is $$\begin{array}{r l}&{H=1.4~\mathrm{million}, ~\mathrm{with~probability}~P=0.8, }\\ &{L=1~\mathrm{million}, ~\mathrm{with~probability}~1-P=0.2.}\end{array}$$

# A Simple Candidate for a Contract is Equity

An equity contract in this context is a proﬁt-sharing agreement,  where the proﬁt shared depends on the proﬁts reported by the borrower. Let the fraction of reported proﬁts that goes to the outside investor be $a$ ,  while the borrower retains a fraction $1-a$ ,  plus any under reported proﬁts. Suppose that the borrower’s contract is just to pay a fraction of reported proﬁts,  with no other details or penalties speciﬁed. The borrower’s payoff,  given the true value of $V$ and the reported value,  denoted by $Z$ ,  is $V-a Z$ . What proﬁt will the borrower report if he is supposed to pay out a fraction of it? The borrower will choose the smallest value of $Z$ . Supposing that the borrower can’t make the lender take a share of a reported loss (by reporting $Z<0$ ),  the borrower will report $Z=0$ . A simple proﬁt-sharing contract works very poorly when proﬁts cannot be veriﬁed. It does not even provide incentives to repay $L=1$ ,  the minimum possible value of proﬁt. Even adding the requirement that proﬁt reports can never be less than $L=1$ does nothing to induce higher payments.

No matter what the true value of $V$ ,  the best response of the borrower to a proﬁt sharing contract is to pay the lowest possible value. If there is no cost to the borrower of understating the amount,  the borrower always does. Even if the lender knows the value of $V$ ,  if the borrower obtains it ﬁrst and thus controls it,  the lender will not be paid unless the borrower suffers some consequence of not paying.

# What Can the Lender Do If the Borrower Claims a Low Amount?

The lender would like to impose a penalty for low payments to give incentives for higher payments. There are two interpretations. The lender can liquidate the project if the borrower pays too little,  preventing the borrower from absconding with it,  or the lender can impose a non monetary penalty on the borrower. Bankruptcy in the world today is some combination of these two actions. In ancient history,  the non monetary penalties were very common,  i.e.,  debtors’ prisons and physical penalties. Such sanctions are now illegal,  but the loss of reputation of a borrower of a bankrupt ﬁrm is similar to a sanction.

# Bankruptcy,  Liquidation,  and the Optimal Liquidation Policy

Suppose that it is not possible to impose a penalty on the borrower or take other assets (outside the business) that are valued by the borrower. See Diamond (1984) for analysis when these non pecuniary penalties are possible. The only sanction available to give the borrower an incentive to pay is liquidation of the borrower’s assets (as in Diamond [1989,  1991]). To focus on the in ef cie n cy of disrupting ﬁrm operations,  I assume that liquidating the ﬁrm’s asset gives no proceeds to the lender or to the borrower. The results are similar when liquidation yields a positive amount that is much less than the value of the un liquidated asset. Liquidation and [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] are useful penalties that a borrower can avoid by paying the debt,  but regular liquidation is not a good way to run a ﬁrm. How does one specify an optimal ﬁnancial contract between investor and borrower when one can decide to liquidate (to penalize the borrower) or not,  contingent on any payment?

Liquidation is best used as a payment-contingent penalty in the following way. If the lender is ever to liquidate for a given payment,  he also should liquidate for all lower payments. Suppose instead that the lender does not liquidate if 1 is paid but will liquidate for some higher payment. Then,  whenever the borrower has at least 1,  he will avoid liquidation by paying 1 and keep the remainder for himself. This makes meaningless the threat to liquidate given higher payments,  because the payment will never exceed 1.

The borrower will pay the lowest amount that avoids liquidation,  and keep the rest for himself. The only exception is if the borrower has in suf cie nt funds to pay that amount. This implies a description of the optimal ﬁnancial contract without monitoring: select a payment,  $f$ ,  that,  if paid,  avoids liquidation. The lender then liquidates for all lower payments. This implies that the optimal contract when monitoring is impossible is a debt contract with face $f$ . The face value includes the promised payment of principal and interest.

# Determination of the Face Value of Un monitored Debt

This section determines the minimum face value,  $f$ ,  of un monitored debt which will lead to payments with an expected return of 5 percent on a loan of 1 (\$1 million),  or an expected value of 1.05.

Suppose $\mathbf f=1$ . When $V=1$ ,  the borrower pays 1 (paying less would result in liquidation). The borrower gets 0,  which is as much as if he paid any lower amount. When $V=1.4$ ,  the borrower pays 1 (to avoid liquidation),  and keeps 0.4 for himself. This implies that with face value of 1,  the lender gets 1 for sure,  which is less than 1.05 and not acceptable.

Any face value of debt between 1 and 1.4 forces the borrower into liquidation when the project returns 1 but is paid in full when the project returns 1.4. This gives the lender an expected return of $0.8 f$ ,  because nothing is received when there is liquidation. Solving for the face value of debt (between 1 and 1.4) that gives lenders a 5 percent expected return solves $0.8 f\, =\,  1.05$ and yields $f=1.3125$ . Un monitored debt with that face value works as follows.

Suppose $\mathbf{f}=\mathbf{1.3125}$ . When $V=1$ ,  the borrower pays less than 1.3125,  and the asset is liquidated. The borrower gets zero for any payment less than or equal to 1. The best interpretation is that the borrower chooses to pay zero when $V=1$ because it is the best choice when liquidation is generalized to allow the borrower to keep a positive fraction of the retained cash. This leads the lender to liquidate and receive zero,  which occurs with probability 0.2. When $V=1.4$ the borrower pays 1.3125,  avoids liquidation,  and keeps $1.4-1.3175=0.0825$ for himself. This is more than he could get from any smaller payment: any smaller payment gives zero. The payment 1.3125 is received with probability 0.8. Liquidation is only avoided when $V=H$ and the face of 1.3125 is paid. The lender receives 1.3125 with probability 0.8 and zero with probability 0.2,  which is an expected payment of $0.8 (1.3125)=1.05$ . Any lower face value will give the lender an expected rate of return below 5 percent.

When outside investors cannot observe the cash ﬂows and cannot monitor the business,  equity contracts do not work. Enforcing them requires excessively costly monitoring. If this monitoring (sitting on the board of directors or keeping close tabs on the business in other ways) is too costly,  then simple ﬁnancial contracts that do not require monitoring are best. These are debt contracts. They induce the borrower to pay investors because default serves as a penalty that the borrower seeks to avoid.

The analysis can be extended to apply not only to defaults on principal and interest [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] of debt contracts but to any other covenant whose violation implies a potential default on a debt contract. Consider a covenant that might be violated for a variety of hard-to-observe reasons. When it is too costly for lenders to determine the reason for the covenant violation,  the covenant will “mean what it says, ” and involve a default whenever it is violated,  rather than being renegotiated based on the reason for the violation.

# The Value of Monitoring

Suppose that it is possible for the lender to monitor the value of the borrower’s operations. Then,  instead of liquidating when less than the face value of debt is paid,  the lender who monitors can instead use the threat of liquidation and offer to refrain from liquidation so long as the borrower repays as much as possible. Instead of always or never offering to accept 1 in lieu of liquidation,  the lender can offer to accept it when $V=1$ but not when $V=1.4$ . This policy leads the borrower to pay $f$ when $V=1.4$ and 1 when $V=1$ . I assume that the lender has all of the bargaining power and will offer to accept less than $f$ only when $V=1$ .

The value of monitoring is the expected savings in ﬁnancial distress costs,  which are equal to $0.2 (1)\ =\ 0.2$ . This is the savings from monitoring,  S ,  described in Section 1. This savings must be compared with the cost of monitoring. The cost of monitoring the value of the borrower’s project is $K$ . If there were a single lender,  then monitoring would cost $K$ . Duplicated monitoring by each of $m$ lenders would cost $m K$ and would be equivalent to a single lender facing a monitoring cost of mK . I assume that the cost of monitoring is incurred ex ante,  before a loan is repaid. Ex ante monitoring implies that the lender must learn in advance about the borrower’s business to properly interpret any data about the project’s return. In this case,  the lender or lenders must establish a costly relationship in order to monitor the borrower. The results can be reinterpreted as also applying to ex post monitoring,  where no relationship is needed and where the costs of monitoring are incurred only when the borrower defaults on the debt. If the lender or lenders can commit in advance to monitor if and only if the borrower pays less than face value,  the ex ante monitoring results can be adapted as follows. In place of the ﬁxed cost of ex ante monitoring,  $K$ ,  use the expected cost of ex post monitoring,  which is the cost $K$ ,  multiplied by the probability that the borrower must default. If the borrower knows he will be monitored given a default,  he will default only when he has no choice,  i.e.,  when $V=1$ (see Townsend [1979]). The ability to wait to incur the ex post cost of monitoring yields an expected cost of monitoring equivalent to an ex ante cost of monitoring of $(1-P) K$ or $0.2 K$ .

# 3. FINANCIAL INTER MEDIATION

If all m lenders monitor,  and $m$ is large,  then the cost of monitoring is $m K$ ,  and monitoring is too expensive. If there were many large investors with personal capital above 1,  then monitoring at cost $K$ would be available. With a small supply of large investors who can lend 1 on personal account (fewer such investors than proﬁtable large projects),  and no way to delegate monitoring,  some projects that would beneﬁt from monitoring will be ﬁnanced with un monitored,  widely held debt. This section shows how ﬁnancial intermediaries can be set up to create synthetic large investors. There will be a proﬁt opportunity to set up such intermediaries if none are present. If there are few large investors and no intermediaries,  then loans are made at 31.25 percent. Finding a way to make monitored loans at 31.25 percent can allow a banker to make a proﬁt. If inter mediation reduces the cost of making monitored loans and there is free entry,  bankers will not earn excess proﬁts but instead loan rates will be pushed down.

Suppose that there are no large investors,  only small investors each with 0.0001 $(\mathbb{S}100)$ to lend,  and 10, 000 small lenders are needed to ﬁnance 1 $\langle\$ 1$ million). Suppose the cost of monitoring $V$ is $K\, =\,  0.0002$ $(\$ 200)$ for each. If each of 10, 000 lenders were to monitor whenever there is a default on the loan,  the cost would be 2,  which is prohibitive,  and no one would monitor. When the monitoring cost is prohibitive,  the optimal contract is widely held debt with face value 1.3125 (see the subsection entitled “Determination of the Face Value of Un monitored Debt”). Delegating monitoring to one agent avoids duplication,  but can cause incentive problems for the agent who was delegated the monitoring task. Small lenders will not observe the effort put into monitoring,  or the information monitored by the agent. The agent (let’s call him or her “the banker”) has a conﬂict of interest with the small lenders. The conﬂict is similar to the conﬂict of interest between the borrower and the small lenders. How can the monitoring task be delegated without the need to monitor the monitor? The answer is for the banker to face liquidation as a function of the amount paid to the 10, 000 small lenders (depositors). This provides incentives to the banker in the same way it does to a borrower: the banker is always better off paying a sufﬁcient amount to avoid liquidation.

Liquidation is a sanction that the banker tries to avoid. For simplicity and for symmetry with the assumption made about liquidation of borrowers’ projects,  I assume that liquidation of the bank is only a sanction and yields no cash to the small depositors or to the banker. There are several ways to interpret this high cost of bank liquidation. One interpretation is that when too little is paid to the depositors,  the assets of the bank’s borrowers are liquidated to make sure that the banker and the borrowers have not colluded to take funds owed to depositors. Another interpretation is that liquidating the bank’s assets consumes all of the assets. In addition,  because the banker gets zero when there is a default on deposits,  a banker who anticipates that the bank is about to fail will reduce any discretionary component of monitoring. The reduced monitoring will decrease the value of bank assets. The assumption that borrowers and lenders get zero serves as a simple shorthand for these more complicated aspects of the cost of bank liquidation.

# Delegated Monitoring without Divers i cation Does Not Succeed

Suppose that the banker monitors a single loan (runs a one-loan bank) on behalf of the small lenders,  and does not diversify across loans. When the borrower’s project returns 1,  the banker can monitor and collect the 1 without actually liquidating. However,  the bank itself would need to be liquidated in this case,  because the face value of the bank’s debt must exceed 1. If the bank’s debt contract with the small depositors has a face value of 1 or less,  the small depositors never receive more than 1,  which delivers less that the 1.05 expected repayment they need to receive the required 5 percent expected return. If the bank is liquidated when its loan defaults by paying 1,  the bank is liquidated whenever the borrower would have been liquidated,  had the borrower used widely held debt. Unless the 10, 000 lenders each monitor the banker (costing 0.0002 each or a prohibitive total of 2),  the one-loan bank will default and be liquidated just as often as the borrower. This one-loan bank example seems to imply that delegating the loan monitoring to the banker will not succeed.

# Can the Banker Use Divers i cation to Reduce Delegation Costs?

Suppose the banker monitored not one loan,  but a diversiﬁed portfolio of loans. A very simple way to show the value of divers i cation is to examine the twoloan bank. In particular,  suppose the banker monitors the loans of two borrowers whose returns are independently distributed but are otherwise just like that of the single borrower (each loan has a 0.8 probability of returning 1.4 and a 0.2 probability of returning 1). The banker attracts 2 ( $\$ 2$ million) in “deposits” from 20, 000 investors and lends it out to two different borrowers. The banker gives each borrower a debt contract with face $F$ ( $\$ F$ million) and collects $F$ when the borrower has 1.4 and monitors to collect 1 when the borrower has 1. As a result,  the banker does not need to use costly liquidation to enforce his loan contract with either borrower. The banker issues un monitored debt deposits that are widely held,  and the bank is liquidated whenever it pays less than face value to any investor. This requires no monitoring by the 20, 000 small investors. Let $B$ denote the face value of bank deposits per loan,  implying that the two-loan bank has total deposits of $2 B$ and each 0.001 $(\mathbb{S}100)$ deposit has face value $\frac{1}{10\small{, }000}\textbf{B}$ B.

Suppose the banker monitors both loans. If both borrowers pay in full,  the bank will receive $2 F$ . If one defaults but not the other,  the bank will receive $1{+}F$ . If both default,  the bank will receive 1 from each,  or 2. The divers i cation from having two borrowers borrow from the bank will reduce agency costs. The distribution of payments to the bank,  if the banker monitors,  is as follows:

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/0e2d96077dd3f8a0ce57168307b6e5826d697174adf1d2f74adb96ea84dc35ef.jpg)

Assume that liquidating the bank yields nothing to depositors or to the banker,  similar to the liquidation of borrowing ﬁrms. The bank has total face value of deposits of $2 B$ . If the bank must be liquidated when it collects face value of $F$ from one borrower and 1 from the other,  it will be liquidated whenever at least one loan defaults,  and there will be no possible savings in costs of ﬁnancial distress. Alternatively,  if the bank can and will pay its deposits when one loan defaults,  it defaults only when both loans default,  and it can reduce the probability of liquidation to $0.04=(1-P)^{2}$ . To examine when payment of all deposits is possible when just one loan defaults,  the total payment received by all depositors will be $2 B$ with probability 0.96 and 0 with probability 0.04. The expected payment is $0.96 (2) B$ . The initial capital needed to make two loans is 2 ( $\mathbb{S}2$ million),  and it requires a 5 percent expected rate of return,  implying that $0.96 (2) B=2 (1.05)$ ,  or $2 B=2.1875$ ,  is the promised payment to 2 ( $\mathfrak{S}2$ million) in deposits. Equivalently,  let the promised interest rate on bank deposits be $r_{B}$ . Then,  because $2 B=2 (1+r_{B})$ ,  the promised interest rate on the bank deposit is $r_{B}=9.375\%$ .

If the bank is to be able to pay 2.1875 when one loan defaults (paying 1) and the other does not default (paying $F$ ),  then $1+F$ must be at least 2.1875,  and the face value of each loan must satisfy $F\geq 1.1875$ . If the bank made loans with this face value,  it could avoid liquidation with probability 0.96. In summary,  if the bank monitors its loans,  it will have the cash and the incentives to pay bank deposits in full with probability 0.96 so long as $F\geq 1.1875$ or the interest rate on bank loans is at least 18.75 percent.

# Will the Bank Monitor?

A remaining question is whether the banker will choose to monitor the loans. Without monitoring,  the bank would not be able to offer to take 1 when only 1 is available and would instead liquidate the borrower’s asset. Monitoring provides no beneﬁt to the banker when all loans pay in full (monitoring is not needed to force a borrower to pay $F$ ) nor when all loans default (because the bank fails and is liquidated). The entire increase in the banker’s return comes from increasing the return when just one loan defaults.

If the banker who monitors obtains nothing whenever at least one loan defaults,  there will be no incentive to monitor. An incentive to monitor requires that monitoring increases the bank’s expected payment by at least 0.0002 $(\$ 200)$ per loan. If the banker monitors neither loan,  then the bank will fail when just one loan defaults,  and the banker will get zero. If a loan that is monitored defaults,  and the other loan does not,  the banker’s return will be $1+F-2 B=1+F-2.1875$ . This is the ex post increase in the banker’s return due to monitoring. Monitoring one of the loans gives this increased return with the probability that it alone defaults,  or with probability 0.16. Monitoring of one of the loans will be in the banker’s interest if $0.16 (1+F-2.1875)$ exceeds the cost of monitoring or 0.0002. Monitoring one loan will pay if $F\geq 1.18875$ . Monitoring both loans gives the same increased return with the probability that one of the two loans is the only default,  or with probability 0.32. Monitoring both loans is in the banker’s interest so long as $0.32 (1+F-2.1875)$ exceeds 0.0004,  which also implies $F\geq 1.18875$ . So long as the intere e on bank loans exceeds 18.875 percent,  the banker is willing to invest \$400 worth of time to monitor all loans because it increases the value of his residual claim on the bank.

The two-loan banker must earn a small proﬁt in excess of the cost of monitoring. The need to provide the bank an incentive to monitor and to avoid bank failure when just one loan defaults (by cross-subsidizing the losses from the defaulting loan with the proﬁt from the non defaulting loan) leads to proﬁts for the banker who was delegated the monitoring of the loan. The banker will monitor only if it yields a proﬁt,  and due to limited liability and limited wealth,  the banker never makes deposit payments in excess of loan repayments. The need to provide incentives puts a ﬂoor on the banker’s expected proﬁt,  which is sometimes called a control rent,  because the banker’s control of decisions requires that the rent (proﬁt) go to him. If further divers i cation is not possible,  either because there are just two loans or because a two-eyed banker can only monitor two loans,  bank proﬁts cannot be driven to zero by competition. The two-loan bank has the following proﬁts. The banker gets the residual claim above 2.1875,  or

$2.3775\:-\: 2.1875\:=\: 0.19$ th probability 0.64,  when neither loan defaults;

 $2.18875\, -\,  2.1875=0.00125$ ° 0.00125,  with probability 0.32,  when one loan defaults; and 0,  with probability 0.04,  when both loans default.

This works out to a total expected payment of 0.122 $(\mathbb{S}122{, }000)$ or $(0.19) 0.64+(0.00125) 0.32=0.122.$ . This is a return to the banker of 0.061 per loan,  which is in excess of 0.0002 the cost per borrower of monitoring,  and the banker earns a control rent of $0.061-0.0002=0.0608.$ .

The delegation cost per borrower,  $D$ ,  equals the cost of ﬁnancial distress of the bank or $0.04 (2)=0.08$ ,  plus control rent to the banker of 0.0608 or a total of 0.1408. All parties are better off with the banker as delegated monitor. The borrower prefers to borrow at 18.875 percent from the bank,  versus at 31.25 percent direct. The investors get a 5 percent expected return in either situation. The banker is happy with any claim with an expected payment above $\$ 400$ and ends up with an expected payment of $\mathbb{S}122{, }000$ .

# Summary of Financial Inter mediation and Divers i cation

I consider three types of contracting arrangements: (1) no monitoring: a widely held traded debt contract with face $, =1.3125$ for each borrower; (2) direct monitoring by investors,  which saves distress costs of $S=0.2$ but costs $m K=2$ ; and (3) delegated monitoring by an intermediary,  which saves distress costs $S=0.2$ at cost monitoring plus delegation cost,  $K+D=0.1408$ .

Divers i cation within the intermediary works to make option (3) work by reducing the liquidation cost of providing the bank an incentive to repay small investors. To simplify,  I use an example where the divers i cation from a bank making only two loans was sufﬁcient to give the bank reduced delegation costs. However,  it is more generally true that divers i cation allows ﬁnancial inter mediation to provide low-cost delegated monitoring. The law of large numbers implies that if the bank gets suf cie ntl y diversiﬁed across independent loans with expected repayments in excess of the face value of bank deposits,  then the chance that it will default on its deposits gets arbitrarily close to zero. In the limit of a perfectly diversiﬁed bank,  the bank would never default and would face no liquidation costs. In addition,  the control rent needed to provide incentives to monitor approaches zero. The delegation cost for the bank approaches zero,  and the only cost of inter mediation is the (unavoidable) cost of monitoring. Competitive and fully diversiﬁed inter mediation would drive borrowers’ expected cost of capital down to 5.02 percent. In the limit of perfect divers i cation,  the face value of bank debt approaches $F=1.06275$ ,  which is the solution to $0.8 F+0.2 (1)=1.0502$ ; it gives the bank a 5 percent expected return after covering the 0.0002 $(\$ 200)$ cost of monitoring. This is too strong because in practice the default risk of borrowers is not independent,  it is positively correlated. In addition,  the number of loans in the bank’s portfolio is limited.

The general message is that divers i cation allows banks to transform monitored debt into un monitored debt,  delegating the monitoring to bankers. The banks’ organizational form minimizes the sum of monitoring and ﬁnancial distress costs.

# Policy Implications

There are important implications of this view of intermediaries. Because there are costs of bank failure,  and there are incentive beneﬁts from the bank receiving the proﬁt derived from its monitoring,  banks can increase their value by hedging or avoiding risks that they cannot control or reduce via monitoring. For example,  monitoring can do nothing to inﬂuence the level of riskless interest rates. Thus,  there is no incentive reason for the bank to bear general interest rate risk. The bank’s high leverage means that a small loss might force a costly default. Hedging of interest rate risk is desirable,  through futures markets or interest rate swaps,  because it can remove risks that have no incentive value to bank managers. Banks rely on divers i cation to eliminate the risks of being very highly levered. Unless a risk is intimately related to their monitoring task,  banks should avoid risks that are not divers i able unless the bank can remove the risk from its balance sheet through another (swap or futures) transaction.

Divers i cation makes bank deposits much safer than bank loans,  and in the limit of fully diversiﬁed banks with independently distributed loans,  bank deposits become riskless. This suggests that even without deposit insurance,  deposits ought to be very low risk. Laws that limit bank divers i cation remove much of the technological advantage of the banking contract. The prohibition on interstate banking in the United States,  only recently eliminated,  made delegation costs much larger and banks much riskier than they would be without the prohibition. The delegation cost from excessively limited divers i cation has two components. One is the increased probability of bank failure,  which may also have contributed to the historical political pressure for deposit insurance. The other component is excessively high control rents: small un divers i ed banks require higher levels of future proﬁts to remove their manager’s otherwise poor incentives. This suggests that in the United States,  where the economy is large enough to have several competing,  well-diversiﬁed intermediaries,  the increased divers i cation from geographical deregulation may reduce managerial moral hazard and help eliminate the need for high future bank proﬁts (high charter value) to provide good incentives to bankers. If this is correct,  banks and similar ﬁnancial intermediaries will be more stable in the future than in recent experience in the United States.

# 4. CONCLUSIONS

The purpose of this article is to clarify the roles of debt and divers i cation in the ﬁnancial engineering that is banking. Debt has several roles related to ﬁnancial inter mediation. The right to liquidate on default provides any outside lender with power over the borrower,  inducing the borrower to repay the debt. This power is limited by the borrower’s right to repay the debt in full and remove the lender’s liquidation rights. However,  liquidation is potentially inefﬁcient. If the lender cannot monitor the borrower’s business,  then the lender should liquidate whenever there is a default,  no matter what the cause. If the lender can monitor the situation,  then the ability to selectively remove the threat to liquidate in return for a concession from the borrower can provide power over the borrower without using inefﬁcient liquidation. Financial intermediaries such as banks can centralize costly monitoring and avoid the duplication of effort of the monitoring of borrowers by small investors. Banks monitor debt (loan) contracts,  and issue un monitored debt (deposit) contracts. Divers i cation is the ﬁnancial-engineering technology that makes monitoring of deposit contracts unnecessary when monitoring of loan contracts is necessary. This allows banks to deliver delegated monitoring. Debt,  monitoring,  and divers i cation are the keys to understanding the link between ﬁnancial inter mediation and delegated monitoring.

# REFERENCES

Bhatt acharya,  Sudipto,  and Anjan V. Thakor. “Contemporary Banking Theory, ” Journal of Financial Inter mediation,  vol. 3 (October 1993),  pp. 2–50. Boyd,  John H.,  and Edward C. Prescott. “Financial Intermediary-Coalitions, ” Journal of Economic Theory,  vol. 38 (April 1986),  pp. 211–32. Diamond,  Douglas W. “Liquidity,  Banks,  and Markets, ” University of Chicago CRSP Working Paper. December 1995. . “Monitoring and Reputation: The Choice between Bank Loans and Directly Placed Debt, ” Journal of Political Economy,  vol. 99 (August 1991),  pp. 689–721.

. “Reputation Acquisition in Debt Markets, ” Journal of Political Economy,  vol. 97 (August 1989),  pp. 828–62. . “Financial Inter mediation and Delegated Monitoring, ” Review of Economic Studies,  vol. 51 (July 1984),  pp. 393–414. ,  and Philip H. Dybvig. “Bank Runs,  Deposit Insurance,  and Liquidity, ” Journal of Political Economy,  vol. 91 (June 1983),  pp. 401–19. Fama,  Eugene F. “What’s Different about Banks?” Journal of Monetary Economics,  vol. 15 (January 1985),  pp. 29–39. Gale,  Douglas,  and Martin Hellwig. “Incentive-Compatible Debt Contracts: The One-Period Problem, ” Review of Economic Studies,  vol. 52 (October 1985),  pp. 647–64. Hellwig,  Martin. “Banking,  Inter mediation and Corporate Finance, ” in Alberto Giovannini and Colin Mayer,  eds.,  European Financial Integration . Cambridge: Cambridge University Press,  1991. Krasa,  Stefan,  and Anne P. Villamil. “Monitoring the Monitor: An Incentive Structure for a Financial Intermediary, ” Journal of Economic Theory,  vol. 57 (June 1992),  pp. 197–221. Lacker,  Jeffrey M. “Why Is There Debt?” Federal Reserve Bank of Richmond Economic Review,  vol. 77 (July/August 1991),  pp. 3–19. Ramakrishna n,  Ram T. S.,  and Anjan V. Thakor. “Information Reliability and a Theory of Financial Inter mediation, ” Review of Economic Studies,  vol. 51 (July 1984),  pp. 415–32. Townsend,  Robert M. “Optimal Contracts and Competitive Markets with Costly State Ver i cation, ” Journal of Economic Theory,  vol. 21 (October 1979),  pp. 265–93. Williamson,  Stephen D. “Costly Monitoring,  Loan Contracts,  and Equilibrium Credit Rationing, ” Quarterly Journal of Economics,  vol. 102 (February 1987),  pp. 135–45. Winton,  Andrew. “Costly State Ver i cation and Multiple Investors: The Role of Seniority, ” Review of Financial Studies,  vol. 8 (Spring 1995),  pp. 91–123.

# Class note 9 BID and ASK PRICES WITH ADVERSE SELECTION/PRIVATE INFORMATION Based on The Only Game in Town ,  and Glosten-Milgrom

# I. The Setup

1. Two types of trader: informed and liquidity (can lump the "misinformed" of The Only Game in Town together with the uninformed). All traders and market makers are risk neutral,  so there is no risk premium.

a. Simple private information: informed traders know exactly what the firm will be worth on some fixed date in the future.

i. V is the unknown value. Everyone knows V will be either zero or one,  and the informed know which of the values will occur.

Ii. The uninformed liquidity traders start out believing that the probability that $\scriptstyle{\mathrm{V}}=1$ is $\%$ ( $\%$ is also the probability that $\mathrm{V}{=}0$ ).

b. Each instant,  at most one trade comes in ,  and we assume all trades are the same size (abstracts from block trading). This means at each instant,  at most one trader either gets private information about $\mathrm{V}$ (and then has a reason to speculate),  or finds out about his (or her) need for liquidity (implying a non-speculative reason to buy or sell).

c. Informed traders buy when stock is under priced at the ask,  sell when overpriced at the bid

 (and do nothing if value is between the bid and the ask).

i. Liquidity traders buy when they have excess liquidity (money to invest) and sell when they need liquidity. The need for liquidity is not related to the value of the stock or the private information that they do not have. Half of all liquidity traders buy and the other half sell. Any given liquidity trader buys with probability one-half.

Ii. A trader buys one share if he buys and sells one if he sells. We abstract from block trading and note that introducing risk aversion would result in a limit to the size of trades made by even very well informed traders.

d. The competitive market makers earn zero monopoly profits and break even on average across trades.

i.Market makers do not observe the private information of the informed traders. As a result,  market makers lose money when trading with the informed.

Ii. The market maker sets prices first,  then traders can choose the type of trade they want at the fixed price. To break even,  market makers set a bid-ask spread. This implies that they make money from trades with liquidity traders. The competitive break even condition implies that the average loss to informed traders is equal to the average profit from liquidity

Iii. The market maker cannot distinguish between liquidity trades and information trades and must quote a single bid and ask price pair. Break even on average implies that:

(1) The bid is the expected value of the stock given public information and the fact that a sell order arrives this instant.

(2) The ask is the expected value of the stock given all public information and the fact that a buy order arrives this instant.

For example,  if there are no informed traders the [[Class Note 9 Bid and Ask Prices With Private Information|bid-ask spread]] is zero. If there are nothing but informed traders,  there is no [[Class Note 9 Bid and Ask Prices With Private Information|bid-ask spread]] which allows the market maker to break even,  because he loses on all trades to informed.

# e.One Period Example

i. Absent a trade,  price of the stock would be $\%$ because there is a 50-50 chance of being worth 1 or 0. If no informed traders existed,  this would be the price,  with no spread. This represents the "grand mean" average value of the stock.

Ii. $\%$ of all traders are informed (more than in reality),  $\%$ uninformed. This means that when an order comes in,  the probability it is an informed trade is $\%$ .

Iii. Consider first the ask price. If a buy order comes in,  and it is from an informed,  it must be that the private information is that the stock is worth 1 (otherwise the informed trader would sell) and the market maker will make a "profit" of:

Ask-1 ( $\acute{=}$ a loss of 1-ask).

If the buy is from a liquidity trader,  the stock is equally likely to be worth 0 as 1,  so the average profit from the trade is: ask $\cdot[(\not{1}/_{2}{\mathrm{\bf~x}}1)+(\not{1}/_{2}{\mathrm{\bf~x}}\; 0)]={\mathrm{ask}}\;\cdot^{1/2}\!\!.$ .

The average profit is the average of these two "profits, " so break even is when $$\mathrm{\%\(ask-1)+\%\; x\;(ask-1)}=0$$ $$\mathrm{ask}{=}\, \%.$$

(Equivalently,  $\%$ is the expected value of the stock given a buy order).

Iv. Bid price determination

If a sell order comes in,  and it is from an informed,  it must be that the private information is that the stock is worth 0 (otherwise the informed trader would buy) and the market maker will make a "profit" of: 0 - bid ( $\left.\dot{\right.}$ a loss of bid - 0).

If the sell is from a liquidity trader,  the stock is equally likely to be worth 0 as 1,  so the average profit from the trade is: $\left[\left (^{1}\!\!/_{2}\mathrm{\Deltax}1\right)+\left (^{1}\!\!/_{2}\mathrm{\Deltax}0\right)\right]\cdot\mathrm{bit}=1\!\!/_{2}$ - bid.

A similar calculation to that for the ask,  but for the bid price solves: $$\mathrm{~\rlap/v~x~}(\mathrm{0-bid})\ \ +\ \ \mathrm{~\rlap/v~x~}(\mathrm{\rlap/v~x-bid})=0\quad\mathrm{or}$$ $$\mathrm{\Deltabind}=\%.$$

(Equivalently,  $\%$ is the expected value of the stock given a sell order).

A positive [[Class Note 9 Bid and Ask Prices With Private Information|bid-ask spread]] is due to the losses to informed trading. It also makes the price reveal and reflect some of the private information of information traders.

If the first trade were a buy (at the ask of $\%$ ),  then $\%$ would be the transaction price,  and would be the "baseline" for the next transaction. The new ask would be above $\%$ and the new bid above $\%$ . Trade by informed traders makes the price adjust toward the value that is not yet known to the public.

# 2. Results

- Private information reduces liquidity. The larger the fraction of informed traders,  the larger the bid-ask spread,  but the quicker the price reflects the private information.
- Private information implies that buying or selling a security will move the price,  even if you have no information and the market is competitive.
- Market efficiency is consistent with the ability to make money by trading if you have private information (but it is often difficult to tell if you have information that is really private!).
# Class Note 10 Liquidity and [[Class Note 10 Liquidity and Class Note 10 Liquidity and Liquidity Managementliquidity management|liquidity management]]

# I. An Overview of [[Class Note 10 Liquidity and Class Note 10 Liquidity and Liquidity Managementliquidity management|liquidity management]]

A common measure of the liquidity of an asset is the $\%$ of its true value one can obtain from a quick "forced" sale. Adverse selection issues and special asset services (such as monitoring of special information about the borrower) can make assets illiquid. An illiquid asset is,  roughly,  one with a large bid-ask spread. This is only rough because il liquidity also implies that one expects to get a better price if one has time to wait until the asset is sold (i.e.,  a bigger [[Class Note 9 Bid and Ask Prices With Private Information|bid-ask spread]] for quick sales or (in the case of assets which mature,  for sales before maturity).

An asset is perfectly liquid if the holder does not expect to care if he is forced to sell at an unknown date. Apart from tax considerations,  treasury securities and most NYSE stocks are in this category. If you (an individual) owned such an asset and were forced to sell (liquidate) with one day's notice (not on the weekend) you would not be upset,  because you would get a fair market price.

On the other hand,  it the asset were a house or a private placement bond,  you would be very upset if you were forced to sell on one day's notice. In less developed countries,  the financial markets are often illiquid,  with little abitity to get a fair price on short notice.

If you knew in advance that you would need cash on some fixed date in advance,  you could arrange to hold an illiquid asset which matured on that date. The demand for always having liquidity is due to uncertainty about when you will be forced to liquidate. These uncertainties for an individual include unexpected expenses,  loss of a job,  etc.

The liquidity of an asset does not relate directly to the risk of the asset,  i.e.,  not to fluctuations in its true value. Instead,  it relates to the "costs" of selling it in a hurry.

# Liquidity risk sharing

Given that certain assets are illiquid,  someone must hold illiquid assets. If there were no financial intermediaries,  then individuals would have to hold them directly,  and incur the liquidation costs whenever there was a personal need for liquidity.

A partial substitute for holding liquid assets is the ability to borrow in the future at a favorable rate of interest. An individual or firm can get into a liquidity crisis if unable to borrow and unable to sell off assets. The two ways to avoid such a crisis are to hold liquid assets and to have a sure ability to borrow (either due to an explicit contract,  like a line of credit,  or absolute faith that you will be able to borrow in the market).

# Liquidity and financial intermediaries

Banks can provide liquidity to customers either by offering deposits which are very liquid,  or by offering lines of credit. Offering either one when a bank owns some illiquid assets exposes the bank to some liquidity risk of its own.

When the net effect of withdrawals of deposits and take-downs of lines of credit yields an outflow of cash from the bank,  something else on the bank's balance sheet must adjust. If the bank has substantial uncertainty about these net flows of cash,  then it must structure its balance sheet to take these fluctuations into account. If the bank was not expected to be able to meet the liquidity demands that is implied by offering liquid deposits and lines of credit,  then the bank would not be able to credibly offer these products. We will see that this "credibility" issue means that having liquidity today in the form of the ability to issue new deposits requires the expectations that the bank will have access to liquidity in the future. That is,  anticipations of liquidity problems can lead to current liquidity problems.

Sources of a Bank's Liquidity

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/d3651ab2681a1852d4202027789a5be99fc44e06a2c63d9f01d0ac7ab3f4cfd7.jpg)

Asset management of liquidity implies that when the bank experiences a net cash outflow,  it adjusts by reducing the size of assets (selling assets) and it protects itself by having many liquid assets around to make the cost of this adjustment low. Until the last 10-15 years,  this was the main method of managing liquidity risk. A bank would hold a portfolio of government bonds to sell off if it needed to make loans under its lines of credit,  or to fund net withdrawals of deposits. This used to be the only option when rates were regulated on deposits,  since the bank could not adjust the interest rate to attract additional deposits. In addition,  the interbank Federal Funds market was less active than it is today,  and was not used as a major source of funds by many banks. As a result,  the banks' borrowing opportunities were limited and sale of liquid assets was the primary available source of liquidity.

The more recent liability management approach lets the bank adjust interest rates on liabilities to attract additional funds when needed. This approach works well if the bank can attract large quantities of new funds without making a large change in the interest rate which it pays. In some sense,  this is related to the elasticity of supply of deposits to the bank. If the bank can attract sufficient new deposits when current depositors withdraw or when lines of credit are taken down,  then it never need liquidate any assets. The problem is,  that the bank may not be able to borrow exactly when it most needs to borrow. In extreme,  this is the problem of the threat of bank runs. Continental Bank (among others) experienced this problem.

# II. An Outline of Managing Liquidity When Depositors Can Panic (best read after class note 11 on bank runs)

# 1. Tactical [[Class Note 10 Liquidity and Class Note 10 Liquidity and Liquidity Managementliquidity management|liquidity management]]

a. Predict the volatility normal fluctuations (those without a panic) in the withdrawal of deposits and takedowns of lines of credit.

b. Determine the costs of asset management (foregone expected return from holding very liquid assets) and liability management (the costs of maintaining borrowing ability) to deal with these normal liquidity needs.

c. Take account of how news about the bank's net worth or future profitability will influence its ability to borrow and to maintain its current deposits. This involves estimating how quickly those who lend to the bank will get nervous and pull out their funds. This is a measure of how risks in the bank's fundamentals will effect liquidity risk.

d. Choose the assets and liabilities that reflect these risks and costs of a liquidity crisis.

# 2. Strategic [[Class Note 10 Liquidity and Class Note 10 Liquidity and Liquidity Managementliquidity management|liquidity management]]: Influencing the risk of a panic for given fundamentals

a. Control the response to news or rumors about your institution by managing the information flow to your clients. This involves having access to your depositors to disclose information if there are rumors regarding your institution's soundness.

b. Control the ability for identical information (especially misinformation) to reach your depositors simultaneously. This is important to prevent a coordinated move in expectations of others expectations; the input for a bank run. In the old days,  this meant preventing the line of people who are withdrawing from spilling into the street (add more tellers,  have a large lobby,  etc.). If "N" is the number of people withdrawing,  do not put $_\mathrm{N}$ on the time and temperature sign.

c. A modern way of putting N on the time and temperature sign is to allow all depositors to see information about the secondary market price of a bank's uninsured CD's. Not putting it on the time and temperature sign requires that they not see this price. When the secondary market price drops (relative to other banks' CD's of the same maturity),  it indicates excess supply of the CD's that have not yet matured (selling pressure indicating possible bad news or bad misinformation). This common information to all large depositors of excess supply can indicate that a bank run may be starting (currently maturing deposits are being withdrawn),  or it may start one,  just like a mistaken headline in the newspaper "Bank Run Today."

Because there is a secondary market for bank CD's,  the only way from keeping depositors from learning about the information that causes the price to change (relative to other banks) is to prevent the price from changing (relative to other banks). To avoid information contagion,  many large banks stabilize the secondary market price of their CD's. By having an investment bank keep their CD trading at the same secondary market price as other large money-center banks,  no information is revealed from the price (the N on the time and temperature sign never changes). However,  keeping the price (relative to other CD's) constant in the face of selling pressure requires that the investment bank buy the CD's from the sellers at the fixed price. The CD's bought by the investment bank are then cashed in early by the bank (one day later),  effectively turning the time deposits into demand deposits. The direct effects of this are to make any already given run worse: not only maturing deposits must be paid off,  but also those that did not mature but were repurchased.

The indirect effects are favorable,  because it prevents coordinated contagion of beliefs about N. This serves to keep a panic from beginning. The fact that banks choose to do this suggests that they are concerned about panics,  and have some notion of how to deal with them.

The role of the investment bank involves a small amount of delegated monitoring. It the I-bank sees an excess supply of the bank's CD's,  it will buy them at the fixed price only if it expects the bank to stay in business until it can sell them back to the bank (stay open at least one more day). If the news generating the run were that the bank was about to be closed,  the I-bank would not stabilize the price.

Chicago Booth,  Business 35202,  Douglas Diamond Extra Class note to read before Fremont Financial

# Addressing Risk with Se curit iz ation Design

A se curit iz ation is a trust: a legal entity with assets but not employees. It makes no judgments,  but rather just follows a flow chart. Servicing the assets requires some judgment,  but servicing is subcontracted to an outside firm that does have employees.

The trust’s flow chart describes how the cash flows coming in will be paid back out to different claims. This income generally comes from three sources

- Interest paid on the receivable s
 - Principal paid on the receivable s o Scheduled principal o Prepayment
 - Recoveries on defaulted receivable s o Foreclosing on collateral o Extracting payment on unsecured receivable s

One additional source used in some situations is a bank account used to store money for a rainy day

- Called a spread account ,  or reserve account ,  its role is to be a last resort when the receivable s perform badly

The securities issued by the trust generally have a senior/subordinated structure. The most senior tranche is typically the largest,  and typically is rated AAA. What the trust could do is pay all money coming in to the most senior tranche until it is paid down,  and then to next-most senior until it is paid down,  and so on down to the most junior. But that is typically not what happens. Instead of paying securities sequentially like this,  in good times the trust typically pays down securities the senior and junior in parallel,  maintaining their relative sizes

- If and when bad times hit,  then the trust will start favoring the senior over the junior piece,  focusing on getting the senior paid down
 - So the senior creditors know that,  in this situation,  there will be a prearranged amount of protection ready for them
Let’s look at a large,  representative se curit iz ation to see this in action. Consider this se curit iz ation of car loans:

#

#

#

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/47cc8be990fb9c741cc1993dd76d77c7337ae61e2e42d2a48586e929ea250972.jpg)

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/dd6925d9781258498487fce72fd20639dc20ef9e7fb623efe98079f2d319961e.jpg)

# Inside the prospectus,  we learn

$35.00\%$ $25.00\%$ $21.00\%$ $7.50\%$

# We also learn

# And

$6.72\%$

# And

$0.50\%$

# And

$3.00\%$ $7.50\%$ $1.50\%$

# And finally

What does all this mean?

Hyundai sells $\$ 774\mathrm{MM}$ face value of asset-backed bonds,  where the assets are car loans with \$855.5 MM Aggregate Principal Balance

- However,  some of these car loans are low-interest car loans Hyundai has offered has sales inducements o e.g. $0\%$ APR loans
 - These loans are worth less than their face value. To account for that,  Hyundai calculates the Yield Supplement Over collateral iz ation Amount ,  which is intended to be the difference between the face value of these loans and what they’re actually worth
 - Initially,  this amount is $\$ 57.5\mathrm{MM}$ ,  so Hyundai adjusts the Aggregate Principal Balance downward by this much,  so the Adjusted Pool Balance (APB) is \$855.5 MM - $\$ 57.5\mathrm{MM}=\$ 798\mathrm{MM}$
 - And therefore,  the Over collateral iz ation is $\$ 798\mathbf{M}\mathbf{M}-\$ 744\mathbf{M}\mathbf{M}=$ $\$ 24\mathrm{MM}$ ,  which is $3\%$ of the APB
 - So Hyundai says this pool starts with $3\%$ over collateral iz ation
Hyundai also pays cash of $\$ 4\mathrm{MM}$ ,  which constitutes the initial Reserve Account Balance . Notice that this is $0.5\%$ of the initial APB

So,  at the beginning of the deal,  the investors as a whole enjoy Total Credit Enhancement ,  i.e. credit enhancement from over collateral iz ation plus credit enhancement from cash in the reserve account,  of $3\%+0.5\%=3.5\%$ of the APB

Going forward,  what happens depends on whether we’re in good times or bad times

Good Times The trust always pays each tranche interest according to its remaining principal balance and stated coupon rate. The tranches get principal as follows

- First,  all principal goes to A 1 until it is completely paid down
 - Then,  principal is spread across A,  B,  C and D so that o The remaining balance of tranches A 2-A 4 is ( $65\%$ of the APB) plus (the cash in the reserve account) $\bigcirc$ The remaining balance of tranche B is $10\%$ of the APB $\bigcirc$ The remaining balance of tranche $\mathrm{C}$ is $4\%$ of the APB $\bigcirc$ The remaining balance of tranche D is $13.5\%$ of the APB
- Note that this adds up to $92.5\%$ of the APB

So let’s say the Car loans pay $\$ 1\mathbf{M}\mathbf{M}$ of principal to the trust,  and there are no defaults (we’ll get to those in a moment),  so the APB goes down by

 $\$ 1\mathbf{M}\mathbf{M}$ . The trust takes this $\$ 1\mathbf{M}\mathbf{M}$ and pays

$\bigcirc$ $\$ 650 K$ to the A notes $\bigcirc$ Notice that the A notes,  among themselves,  are sequential-pay,  so all this $\$ 650 K$ will go to the A tranche currently being paid down

$\bigcirc$ $\$ 100\mathrm{K}$ to the B notes

 $\bigcirc$ $\$ 40\mathrm{K}$ to the C notes

 $\bigcirc$ $\$ 135\mathrm{K}$ to the D notes

 $\bigcirc$ $\$ 75\mathrm{K}$ to the certificate holder,  i.e. the issuer

Bad Times

The idea behind how the trust pays out in good times is for each tranche to have a prearranged amount of credit enhancement protecting it in bad times,  where this amount is fixed as a fraction of the ABP

$\bigcirc$ A notes: $35\%$ of ABP

 $\bigcirc$ B notes: $25\%$ of ABP

 $\bigcirc$ C notes: $21\%$ of ABP

 $\bigcirc$ D notes: $7.5\%$ of ABP

Suppose,  for example,  we have good times for a while,  and the ABP now stands at $\$ 400\mathrm{MM}$ ,  and there is still the $\$ 4\mathrm{MM}$ in the reserve account. Consequently,  the remaining principal balances are

$\bigcirc$ A notes: (. 6 $5)\mathbb{S}400\mathbf{M}\mathbf{M}+\mathbb{S}4\mathbf{M}\mathbf{M}=$ $\$ 264\mathrm{MM}$

 $\bigcirc$ B notes: (. 10) $\$ 400\mathbf{M}\mathbf{M}=$ $\$ 40\mathbf{M}\mathbf{M}$

 $\bigcirc$ C notes: $(. 04)\mathbb{S}400\mathbf{M}\mathbf{M}=$ $\$ 16\mathbf{M}\mathbf{M}$

 $\bigcirc$ D notes: (. 135) $\$ 400\mathbf{M}\mathbf{M}=$ $\$ 52\mathrm{MM}$

Now suppose we liquidated the pool and paid the proceeds to the notes according to absolute priority,  using the $\$ 4\mathrm{MM}$ reserve account to cover any shortfall

$\bigcirc$ A notes could withstand $35\%$ credit loss on the receivable s,  because that would leave $65\%$ of $\$ 400\mathbf{M}\mathbf{M}=\$ 260\mathbf{M}\mathbf{M}$ cash,  which,  combined with the reserve account,  covers the $\$ 264\mathrm{MM}$ remaining balance o B notes could withstand $25\%$ credit loss,  because that would leave $75\%$ of $\$ 400\mathbf{M}\mathbf{M}=\$ 300\mathbf{M}\mathbf{M}$ cash,  minus $\$ 264\mathrm{MM}$ paid to the A notes,  leaves $\$ 36\mathbf{M}\mathbf{M}$ ,  plus the $\$ 4\mathrm{MM}$ from the reserve account $+\, \$ 40\mathrm{MM}$ o Likewise,  C notes could withstand $21\%$ credit loss and D notes could withstand $7.5\%$

In actuality,  the pool is not liquidated in bad times. Rather,  the trust follows absolute priority each month,  giving each tranche its scheduled cash only if the tranche ahead of it was paid in full. Whether this happens depends entirely on whether the excess interest coming in is sufficient to cover the net default losses that have occurred

Covering Defaults in Good Times and Bad Times

Suppose we are in the situation just described,  where the APB is $\$ 400\mathbf{M}$ ,  the reserve account balance is $\$ 4\mathrm{MM}$ and the tranches have the indicated remaining balances.

Good Times

Let’s say the receivable s pay $\$ 10\mathbf{M}\mathbf{M}$ principal,  and $\$ 1\mathbf{M}\mathbf{M}$ of them default,  so the APB goes down by $\!\!\$ 10\mathbf{M}\mathbf{M}\mathbf{+}\!\!\$ 1\mathbf{M}\mathbf{M}=\!\!\$ 11\mathbf{M}\mathbf{M}.$ . Let’s say further that

O the receivable s pay $\$ 4\mathrm{MM}$ in interest $\bigcirc$ the servicer recovers $\$ 0.5\mathbf{M}\mathbf{M}$ on the defaulted receivable s $\bigcirc$ the servicer is owed $\$ 0.4\mathrm{MM}$ in servicing fees,  and $\bigcirc$ the trust owes $\$ 2.5\mathrm{MM}$ interest to the tranches

In this case,  the trust has $\$ 1\mathbf{M}-\$ 0.5\mathbf{M}=\$ 0.5\mathbf{M}$ in net default losses,  and has $\$ 4\mathrm{MM}-\$ 0.4\mathrm{MM}-\$ 2.5\mathrm{MM}=\$ 1.1\mathrm{MM}$ in excess spread,  so it can easily cover the net default losses out of the excess spread.

$\bigcirc$ The trust adds $\$ 0.5\mathbf{M}\mathbf{M}$ out of the excess spread to the $\$ 0.5\mathbf{M}\mathbf{M}$ in recoveries to come up with $\$ 1\mathbf{M}\mathbf{M}$ ,  which it adds to the $\$ 10\mathbf{M}\mathbf{M}$ in principal that came in,  so now it has $\$ 11\mathbf{M}\mathbf{M}$ to make principal distributions out of,  just as if no defaults had occurred

All tranches get exactly their scheduled interest and principal,  and the residual claimant gets $7.5\%$ of the $\$ 11\mathbf{M}\mathbf{M}$ principal plus the $\$ 0.6\mathbf{M}\mathbf{M}$ of excess spread left over after covering defaults

Bad Times

Say all numbers are the same except now,  there are $\$ 8 M M$ in defaults and only $\$ 1\mathbf{M}\mathbf{M}$ in recoveries,  so net default losses are $\$ 7\mathrm{MM}$ and the ABP goes down by $\$ 10\mathbf{M}\mathbf{M}+\$ 8\mathbf{M}\mathbf{M}=\$ 18\mathbf{M}\mathbf{M}$

$\bigcirc$ Trust takes the $\$ 1.1\mathbf{M}\mathbf{M}$ excess spread,  brings it down to $\$ 5.9\mathrm{MM}$

 $\bigcirc$ Trust takes the $\$ 4\mathrm{MM}$ out of the reserve account,  bringing the shortfall down to $\$ 1.9\mathbf{M}\mathbf{M}$

So now the trust is scheduled to pay $(92.5\%)(\$ 18\mathbf{M}\mathbf{M})=16.65\mathbf{M}\mathbf{M}$ principal to the tranches with only $\$ 10\mathbf{M}\mathbf{M}+\$ 1.1\mathbf{M}\mathbf{M}+\$ 4\mathbf{M}\mathbf{M}=\$ 15.1\mathbf{M}\mathbf{M}$ cash,  and it can’t. So the junior tranches will get no payment,  and will instead go into arrears

$\bigcirc$ Principal balance will be below the target balance

 $\bigcirc$ Have to be brought up to the target balance before residual claimant gets anything

O Also,  the reserve account has to be brought back up to $\$ 4\mathrm{MM}$

So to an investor in this se curit iz ation,  there are four layers of protection against default losses

$\bigcirc$ Excess spread

 $\bigcirc$ Reserve Account

 $\bigcirc$ Over collateral iz ation

 $\bigcirc$ Subordination of the tranches below

#

$1.00\%$

So the servicer gets $1\%$ of the receivable s balance as a servicing fee,  and gets to keep any fees or other charges it extracts from borrowers. Note that Hyundai Motor Finance Company is the servicer.

# Class Note 12 – [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]]

2 YHUYLHZ –

X What is [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]]? What is its significance? X How are [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] prices quoted? X Where do [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] prices come from? X What are backup lines of credit,  and why do all [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] issuers have them? X What is meant by the “early-exit mechanism” of the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] market? What has been the default experience of [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] investors? X How do regulations affect the demand for different maturities? X What happened LQ''&ULVLV? X Alternative – Extendible Commercial Notes

CP is the simplest security that corporations issue. It is a short-term promissory note. As long as issuers obey certain guidelines,  their [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] is exempt from the hassles and expense of registration requirements. The most important of these guidelines are

X Maturity is less than 270 days x Issued in denominations too big for individual investors

Almost all [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] meets these guidelines. In fact,  most [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] satisfies the guidelines by a wide margin.

X Average maturity of outstanding [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] is around 40 days x Average trade size is around $\$ 20\mathbf{M}\mathbf{M}$

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/72004663914242263c033ed3d99a38f8eb6218f3b494e6630b66c137fb956d12.jpg)

CP Issuance Volume,  by Initial Maturity February 2008

The quantity of [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] grew steadily and substantially until the 2001/2 recession,  and then it surged until its recent drop. Here’s the growth in [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] outstanding since the beginning of 1991:

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/aa7ac55139f71f7a607027e8d0dbfabe62a56f3ef61edfcf5f430ba5fe727898.jpg)

At last count,  there was $\$ 1.85$ Trillion in [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] outstanding,  down $14\%$ from its all-time high of $\mathbb{S}2.16$ Trillion last July,  but up from its recent low of $\$ 1.79$ Trillion in December.

The plunge in [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] outstanding is due specifically to Asset-Backed Paper:

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/27cd65adf33c147343b56dff77d27f7faccf2cdbfc00941739e272d332ea22e8.jpg)

Asset-Backed paper is sold not by a regular company,  but rather by a special-purpose vehicle ,  or conduit

X Buys financial assets and finances by selling securities backed by these assets

X Separate legal entity from the sponsoring institution,  so the buyers of the securities have recourse only to the financial assets,  and not to the sponsoring institution

We FRQVLGHU such se curit iz at ions in aQRWKHU'FODVV'QRWH

Notice that,  compared to Tbills,  [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] is issued in

X Generally shorter maturities – Tbills are 28,  91,  or 182 days to maturity when issued x Greater variety of maturities – Tbills mature only on Thursdays. You can buy [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] maturing on any day you are interested in x Greater frequency – The government floats Tbills just once a week,  whereas there is new [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] every day x Larger trade sizes – You can easily buy $\$ 10\mathrm{K}$ face value of Tbills,  but not CP

/Ŷ'ƐƵŵŵĂƌǇ͕' C W comes from three main categories of issuers

 Financial [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] – issued by financial corporations such as bank holding companies,  GE Capital,  etc.

  Non-Financial [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] – from any other kind of corporate issuer

  Asset-Backed [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] – issued by a special-purpose entity that holds financial assets such as mortgagebacked securities,  car loans,  etc.

Here are the quantities of these different kinds of [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] over ϮϬϬϭͲϭϮ :

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/13d484bde42522dd7cfae82047bcac9c4df11cfd7096c97d027273af9556e7a9.jpg)

This graph makes several points

 The [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] market is big – altogether it’s about $\mathsf{S}1$ Trillion,  though it is half of what it was (peak was $\mathsf{S 2.18}$ Trillion on 8/8/07)  Non-financial issuers are not a big part of the market,  only about $18\%$  All categories are about $2/3$ of where they were 11 years ago  Asset-backed paper fell off a cliff o Down about $70\%$ from the $8/07$ peak,  and $\mathsf{S 350 B B}$ of this fall occurred in just 4 months starting in early August 2007,  with $\mathsf{S 200 B B}$ of that in just 3 weeks

It’ s worth focusing for a moment on the ABCP crash. Here’s the weekly issuance volume:

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/e43def4b60f837fc6ba9065ad85fc9a3e30a7891da9ea7813de19c8bfc34de2b.jpg)

You can see that in the early part of the decade,  there was $\mathsf{S}200$ Billion or so of new ABCP sold each week,  which ramped up to $\$ 500$ Billion at the peak. Now it’s down to around $\mathsf{S 100}$ Billion each week. If we look just at 2007,  we don’t see the is suance volume crash quite as hard as in the previous graph,  but that’s because these numbers combine long -dated and short-dated paper. If we look at the distribution of maturities,  we see that in August 2007,  issuance abruptly shifted away from longer maturities:

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/9923c9efa61575120be11ab4542a8f3618a8250826830b34c1927c3d073a6266.jpg)

You can see issuance tilting heavily toward shorter paper in the latter half of 2007. You can also see that,  in recent months,  issuance of $41+$ day paper has shrunk significantly,  in favor of shorter paper.

Consider also the discount rates this paper paid over this period:

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/921df7cd9eafa784002da1e53de92c3034dc74b62f640465bd2bb535bed95b26.jpg)

This shows the rates for the three categories,  plus a fourth category $\mathcal{U}\mathsf{A}2$ non financial” which is the lower-rated paper from non-financial issuers. The discount rates generally follow the prevailing moneymarket rate (known as LIBOR,  for L ondon I nter B ank O ffered R ate):

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/0bec27b05829c2c59eb9efc5dd61ae1431b313ae81e957b0836ac6b887d7f343.jpg)

What happened to these issuers was essentially a bank run. Firms that go to the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] market know they are exposed to bank-run risk. This is because when they issue CP,  they expect to repay it by issuing [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] again,  i.e. by rolling it over. If they can’t roll it over,  they’ve got a problem. For this reason ,  a [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] issuer generally has a committed bank facility at least as big as the amount of [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] he has outstanding. This “backup line” plays exactly the role of the lender of last resort in the bank-run model: if the issuer needs extra cash to let investors out,  it doesn’t have to sell assets for bad prices,  it just needs to borrow the necessary cash from the bank . Knowing this,  a [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] investor calculates that there’s no benefit from joining a ru n,  i.e. not rolling over his paper,  so he rolls over his paper and there’s no run.

 The backup line is intended to be insurance against the market melting down,  not the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] issuer melting down,  and it often contains [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] that limit or revoke the issuer’ s right to take down the line if its condition has deteriorated sufficiently

  This limitation is known as a Material Adverse Change clause. You can read further in the discussions by Dominion Bond Rating Service and A M Best

It’s important to distinguish this backup line of credit from a Letter of credit,  which is explicitly a credit enhancement. A letter of credit says that if the issuer doesn’t repay the paper,  the bank will. So the credit quality of the paper is at least as high as the credit quality of the bank.

 So a backup line of credit is more accurately viewed as a liquidity facility ,  i.e. insurance against the market drying up,  than a credit enhancement,  i.e. insurance against the issuer going bad

Backup lines became widespread in the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] business after the Penn Central ZĂŝůƌŽĂĚ' default in 1970. Penn Central was a big issuer of CP,  and this was the first default in many years,  and the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] market crashed. The Fed eased this crash by providing liquidity to banks so issuers could borrow to pay their

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/8cfea68b0e49319331564800500d44c5495af48b2e04c561f89291923cc00e25.jpg)

In 1970 some [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] issuers had backup lines,  and others did not. It was widely suspected during the Penn Central crisis that banks had an easier time borrowing at the discount window when they could show the Fed that they were borrowing more because issuers were taking down their lines.

X In other words,  if you didn’t have a backup line,  and wanted a bank loan to pay off your maturing paper,  the bank might say “we’re low on cash right now because of other issuers taking down their lines,  and if we try to borrow the money for you from the Fed,  they won’t lend because you’re not taking down a backup line”

Ever since the Penn Central crisis,  it has been essentially impossible for issuers to sell [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] without arranging a backup line of credit. Investors worry that a company without backup credit will have a financial crisis,  which could precipitate default,  if the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] market panics.

X The thing to remember of backup lines of credit is that they are not credit enhancements. If a company goes bankrupt,  the bank is not going to pay off its CP. They are insurance not against the company going bad,  but against the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] market going bad. If the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] market panics,  a backup line allows an issuer to substitute bank borrowing for his [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] borrowing,  and the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] investor gets out whole. X A backup line of credit is a [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] issuer’s indirect access to the lender of last resort x Mercury Finance had backup lines,  but the banks cut off the lines when Mercury got into trouble (from fraudulent accounting).

So in today’s market,  issuers have backup lines. Now consider the typical issuer. As we saw,  the typical issuer has the top credit rating,  so if it is downgraded,  it is generally still investment grade

X The issuer’s banks are not unconditionally obligated to let the issuer use its backup lines,  but since the issuer is still investment grade,  they generally will let the issuer borrow

Th ĞƌĞ'ǁĂƐ a trend that grew over the last couple years of the ABCP boom,  which was a trend away from backup liquidity. That is,  a number of ABCP issuers decided to save the money they would have spent on a backup line,  and instead rely on what they called internal liquidity .

 So instead of a backup line,  these issuers would be over collateralized ,  which is to say that the assets they held (typically mortgage-backed securities) were worth sufficiently more than their liabilities  Typically,  the issuer would value its portfolio each week,  and if the value exceeded the liabilities by more than a stated percentage,  then everything was considered to be fine  This was considered to be “internal liquidity” because the issuer could,  in theory at least,  pay down its liabilities by selling its assets  The proximate cause of the collapse of ABCP issuance in August,  2007,  was the failure by several ABCP issuers to meet this valuation test

A related strategy to this “internal liquidity” is what was sometimes called “extendible commercial notes”,  or just “extendible notes.” This was a way to issue something almost like [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] without paying for backup liquidity. It worked like this:

Today,  I sell an extendible note

 In 30 days,  I can pay down the note. However,  I have the option to instead extend the note up to a year. That is,  instead of paying my creditors th e principal amount,  I tell them “your security now matures in a year. Over that year,  I’ll pay you interest keyed to the prevailing interest rate paid by paper with the same rating.”''dŚĞƐĞ'ĞŶĚĞĚ'ƵƉ'ŐĞƚƚŝŶŐ'ĞǆƚĞŶĚĞĚ'ĚƵƌŝŶŐ'ƚŚĞ'ĐƌŝƐŝƐ'ĂŶĚ'ƚŚĂƚ'ĞŶĚĞĚ ƚŚĞŝƌ'ƵƐĞ'ŝŶ'ŶĞǁ'W'ŝƐƐƵĞƐ͘

 Here’s a typical schedule of interest rates for such paper: Rating % of [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] Minimum Spread over LIBOR

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/f6e16e4372dfd7532acf40744bfbecfd3dc3e5efacfb23e70c396139901341f7.jpg)

The message the issuer sends is “A backup line of credit would give some assurance that the paper won’t default if the market goes bad. Same here – if the market goes bad,  the paper won’t default. But instead of paying off right away,  it will convert to longerterm paper with a high interest rate.”

Newstex Web Blogs Copyright 2007 felix salmon. Com

# Felix salmon. Com

# August 30,  2007 Thursday 7:38 AM EST HEADLINE: [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]] Market Still in Distress

Aug. 30,  2007 (felix salmon. Com delivered by Newstex) -- Yves Smith at Naked Capitalism Bloomberg tells us that the [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]] market is shrinking.

This is a more serious issue than might appear. [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]] is an important,  if not the most important,  source of short-term funding for sizable corporations,  mainly because it's cheap and flexible. They can readily adjust the amount outstanding to reflect changes in their need for cash. When [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] matures,  and an issuer cannot "roll" it,  as in replace it with new CP,  he has two choices. If he has the option,  he can draw down standby lines of credit with his friendly bank. If he has no,  or insufficient,  backup lines,  he has to get the cash somehow. Both option 1 and option 2 have costs. Option 1 means he is using higher-cost funding and has limited the company's alternatives for dealing with emergencies. But more important,  the demand for cash at banks means it crowds out other bank lending,  such as to small businesses. Option 2 means the company goes into crisis mode,  delaying payments to vendors,  trying to accelerate payment from customers,  possibly even deferring payroll if that is at all an option.

Now on a small scale,  these moves would create a few casualties. But on a large scale,  as is happening now,  both will put a damper on the real economy. They suggest that the $4\%$ GDP growth release for the second quarter may have perilous little relevance now. From The U.S. [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]] market shrank for a third week,  extending the biggest slump in at least seven years,  as investors balked at buying short-term debt backed by mortgage assets. Asset-backed [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]],  which accounted for half the market,  tumbled $\$ 59.4$ billion to $\$ 998$ billion in the week ended yesterday,  the lowest since December,  according to the Federal Reserve. Total short-term debt maturing in 270 days or less fell $\$ 62.8$ billion to a seasonally adjusted $\$ 1.98\$ trillion. [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]] outstanding has fallen $\$ 244.1$ billion,  or 11 percent,  in the past three weeks,  suggesting the Fed's Aug. 17 reduction in the discount rate has yet to entice buyers back into the market. More than 20 companies and funds including Cheyne Finance and Thornburg Mortgage (TMA) Co. Failed to sell new paper as investors fled to safer investments. ''I don't think the Fed understands how critical the situation is, '' said Neal Neilinger,  co-founder of NSM Capital Management in Greenwich,  Connecticut,  in an interview today. ''The market is going to overshoot itself and not lend money to people who deserve it.''…

The 11 percent decline over three weeks is the biggest since 2000,  according to data compiled by Bloomberg…. In a sign that buyers are still favoring safer assets,  an $\$ 18$ billion auction yesterday for two-year U.S. government debt drew the most demand since 1992. The sale drew $\$ 3.97$ for every $\$ 1$ sold,  the most since at least 1992,  according to Bloomberg data.

# The Globe and Mail (Canada)

September 26,  2007 Wednesday HEADLINE: Credit problems put companies on ice BYLINE: Bloomberg News

On Baffin Island in the Arctic Circle,  Baffinland Iron Mines Corp. Almost missed its window to ship provisions to workers before winter arrives. The delay came not from the weather,  but from a sudden freeze in the market for shortterm debt 3, 200 kilometres south in Toronto.

Baffinland ran short of funds to pay for food,  fuel and drilling equipment after investing in [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]] that borrowers couldn't repay. Without the money,  the company had to arrange an emergency line of credit before shipping lanes froze over.

"We have 200 people to keep alive, " chief executive officer Gordon McCreary said in Toronto. "Our lifeline to getting critical materials to the north" was the $\$ 43.8$ -million invested in [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]],  he said.

Investors fled Canada's asset-backed [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]],  paralyzing the $\$ 40\cdot$ -billion market for debt that carried the highest credit ratings,  after losses from home loans to people with poor credit histories roiled global credit markets.

That left Baffinland and other investors in the lurch because 17 funds run by finance companies,  including Torontobased Coventree Inc.,  Newshore Financial Corp. And Quanto Financial Corp.,  couldn't raise money to pay back lenders,  according to ratings company DBRS Ltd.

No [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]] borrower had failed to pay on time in two decades and Toronto-based DBRS gave the securities its top rating of R-1. The funds also had backup lines of credit from banks.

"You can get what the bank pays you,  which is not very much,  or you can put it in asset-backed [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]],  which have always been rated as high as you can get, " said Geoff Chapter,  a spokesman for Vancouver-based First Quantum Resources Minerals Ltd.

First Quantum hasn't been repaid on $\upzeta 7.5$ -million of debt issued by Coventree that matured on Aug. 14 and Aug. 15,  he said. It had about 28 per cent of its cash in [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]].

Starting in July,  growing defaults in U.S. home loans caused the cost of borrowing to increase for all but the most credit worthy companies. Rates on asset-backed [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]] soared.

Investors began demanding yields of about 6.03 per cent to own Coventree's [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]]. On Aug. 13,  the company said it couldn't find enough buyers to refinance $\$ 950$ -million of short-term debt and its banks refused to provide emergency funds. Company spokesman Craig Armitage declined to comment.

A group of 10 banks and pension funds agreed on Aug. 16 to convert $\$ 35$ -billion of debt into notes maturing in as much as 10 years. Terms of the debt won't be released until mid-October,  said Purdy Crawford,  a lawyer at the Toronto firm Osler Hoskin & Harcourt LLP,  who heads the group.

Until then,  investors won't know when they will get their money back,  or whether they will be repaid in full.

# From an H&R Block earnings conference call,  August 30,  2007 –

… I want to comment on our announcement to draw $\$ 85\Theta$ million on our committed backup lines of credit. These lines,  with total capacity of $\$ 2$ billion,  were put in place to give us flexibility and assure adequate liquidity for short-term needs. In recent weeks,  the [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]] market has become increasingly constrained and unstable,  especially for A 2/P 2 issuers like Block Financial. As a result,  we decided to substitute this more stable source of funds for our working capital needs. These lines of credit extend through August of 2010 and are accessed today at a rate of [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] plus 30.5 basis points. We're using proceeds to pay down [[Class Note 12 - Commercial Paper#Class Note 12 – Commercial Paper|Commercial Paper]] balances and to meet our ongoing working

Capital needs. We expect to have adequate liquidity for the upcoming tax season and into our fiscal fourth quarter when we typically become cash flow positive.

# How [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] is brought to market

An issuer can sell its [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] by hiring a dealer,  who then shows the issuer’s paper along with the other issue r the dealer handles. An issuer can also sell its [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] by itself. That is,  it has its own trading floor,  where its people show the issuer’s rates on trading screens,  and interact directly with investors. Here is a Bloomberg screen showing the biggest such issuers:

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/52f85fe36db78ea0792c007efc79e89ed0f7d9e5962f60dce8a3a770fb153363.jpg)

You can see the size of the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] program on the far right,  and the program’s ratings from S&P,  Moody’s and Fitch just to the left of that

 These three are the major (but not only) raters of [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] programs

  In order to be considered “top tier” for regu latory purposes,  a program needs at least two top ratings from “Nationally Recognized Statistical Rating Organizations” (i.e. NRSROs)

O Probably the most important of these regulatory purposes is to qualify for investment by money funds,  which are extremely limited in their ability to invest in [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] that is not top tier by this definition o Top tier is A-1 (or $\mathsf{A}\!\!-\!\! 1\!\!+$ ) from S&P,  P 1 from Moody’s,  and F 1 (or $\mathsf{F}1+$ ) from Fitch  Sometimes $\mathsf{A}\!\!-\!\! 1\!+$ and $\mathsf{F}1+\mathsf{\Omega}$ are called “top top tier”

 You can see that Sears is $\scriptstyle"\mathsf{N P^{\prime\prime}}$ ,  or “ Not Prime ” ,  and offers rates way above the top tier issuers o You almost never see junk [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] like that. For the most part,  the lower tier of [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] is the A 2/P 2 paper in the graph a few pages back

Here is how [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] rates fit into the money market in general

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/67691396dad9a3f3fd66fcae3361c5ecf2c8c15b443f0b9b116fe143b3580a4b.jpg)

Who buys CP,  if not individuals? The biggest customers are money market mutual funds,  managing the cash of individuals. The Federal Reserve attempted to identify the owners of the $\$ 1.79$ Trillion of [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] outstanding on 12/31/07,  and found

X $\mathbb{S}711\mathrm{B}$ held by money funds -  $\$ 85\mathrm{B}$ held by pension funds x $\$ 42\mathrm{B}$ held by life insurance companies x $\$ 125\mathrm{B}$ held by mutual funds other than money funds x $\$ 83\mathrm{B}$ by brokers and dealers

And so on.

In other words,  the investors in [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] are big institutional investors with some short-term money. Selling [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] is very much like selling [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]] – a short list of potential investors who buy in big lots.

X The difference is that [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] matures very quickly,  so sellers are going back to the short list of investors many times a year.

Quotation of [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] – Discount Rate

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/16871d5b2efcad47f12709c36d75bd80c9a9e44e0ff18f607661c0145b1f25c9.jpg)

CP pays no coupons,  it just pays face value at maturity. If you buy $\$ 10\mathbf{M}$ face value of [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] from GE Capital (the biggest issuer,  by the way) maturing on April 18 (i.e.,  30-day paper),  then you will get $\$ 10\mathbf{M}$ on 4/18. It is therefore issued and traded at a discount,  and when traders quote prices to each other,  they talk in terms of discount rates ,  just like Tbills. So again if we call the face value $F.$ ,  then number of days to maturity $n$ ,  and the discount rate $d.$ ,  then the price $P$ is $$P=F-(d/100)(n/360) F$$

So for example,  if the discount rate for the $\$ 10\mathbf{M}$ of GECC paper is $2.63\%$ ,  then the price is $$\mathbb{S}10\mathbf{M}-(2.63/100)(30/360)\mathbb{S}10\mathbf{M}=\mathbb{S}9, \! 978, \! 083$$

Compared to Treasury bills of the same maturity,  [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] has the exact same promised cash flows,  but also has three disadvantages,  each of which imposes a discount when investors purchase

X [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] issues can default,  and sometimes they do. X Biggest ever was \$457 MM of Pacific Gas & Electric paper in 2001 x Treasury bills are widely regarded as free of default risk

X [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] is less liquid. The secondary market for [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] is not as active as the secondary market for Treasury bills.

X On any given day,  an investor can buy [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] maturing on any near-term date he wants x He can customize his [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] investment to his liquidity needs,  so there is little chance he will bring it back to the market

X [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] interest is subject to the income taxes of many states and municipalities,  but TB interest is not

As a result of the credit risk,  liquidity,  and taxation drawbacks,  [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] trades at a discount relative to Tbills with the same maturity

Pricing of CP:

Here are the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] and TB rates of recent years:

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/b8b15f33dec9f133b112ee9d41173c69556b8e7d258922e240e700f59f925e9e.jpg)

The magnitude of this spread has varied considerably over this period:

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/5d0442d0012b809899d08e14628f31dcd24bc141cdcd0dad5e94056ce1fa00bd.jpg)

It was quite high,  over 100 bp,  in the 90-91 recession but it has been even higher lately. Notice the volatility around year-ends.

Some of this is due to variation in the TB rate. Notice that,  if the state tax on [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] interest is $8\%$ (about what it is here in PA),  then

-  if TB is paying $8\%$ ,  [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] has to pay $8.70\%$ to have the same after-state-tax return. That is,  $(1–. 08)(8.70)=8.00$ ,  so after paying your state tax you’ll have the same return as a TB investor x If TB is paying $3\%$ ,  [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] has to pay $3.26\%$ to have the same after-state-tax return

So in other words,  the spread has to be higher when rates in general are higher,  just to keep the after-tax returns the same. It is therefore useful to consider not only the spread itself,  but the spread divided by the TB rate:

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/219277323da20ee2465cc159b9a1a48b37cc82459bfa6c1c831688c7ad1ee661.jpg)

CP-TB Spread as Fraction of TB

By this measure,  the spread is somewhat steadier over time,  generally oscillating around $8\%$ .

X Spread was so low during the recession because the short rate was so low,  so the portion of the spread driven by taxes was small

But the recent spike looks even more extreme by this measure,  given the decreases in short rates.

Spikes during higher market uncertainty (esp. The big defaults)

Like other corporate debt,  [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] is rated by the major agencies. Drexel Burnham sometimes issued unrated CP,  but now it is almost unheard-of. All rating agencies have four main categories,  which correspond to the categories of Moody’s:

X P-1 Top of Investment-Grade,  corresponding roughly to the longterm ratings A 3 though Aaa (A-1 by S&P) x P-2 Middle to bottom of Investment-Grade,  corresponding roughly to long-term ratings Baa 2 through A 2 (A-2) x P-3 Very bottom of Investment-Grade (A-3) x NP Not Prime,  corresponding to Speculative-Grade (B)

Not only is [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] always rated,  but almost all of the outstanding volume is highly-rated. As of 2/29/08 the Fed reports

X $\mathbb{S}1{, }599\mathrm{B}$ of Tier 1 paper (Rated A 1 or P 1) x $\$ 66\mathrm{B}$ of Tier 2 paper (A 2 or P 2) x Minimal amount below that

Of course the lower-rated paper trades at a discount. Here’s the spread between 30-day P 2 and P 1 paper over the past ten years:

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/6473ba1ff93a43f76fb4ea8a44214ebd05b9ac145ef66e134f4aa37f415b33a6.jpg)

This spread has of course gone nuts too. Notice the run-up in the spread before each year-end,  and in particular before this past year-end. Investors are especially reluctant to hold risky paper at disclosure time

# Regulations that affect demand for CP

Money market mutual funds do everything they can to maintain their share prices at exactly $\$ 1$ .

Money fund has ever broken the buck The SEC helps them in this regard by allowing an account standard known as straight-line amortization for instruments with 60 days or fewer to maturity. It works like this: suppose you buy n -day [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] with face value $F$ at a discount $D$ . In other words,  you paid $F–D$ for it today,  and in $n$ days you’ll get $F$ .

As long as $n$ is no more than 60,  you can

X Value the investment at $F–D$ x Book $D/n$ of interest every day for those n days

Investors will get interest at the rate $D$ over those $n$ days,  even if the market rate has changed . If you bought all your paper at $5\%$ and rates go to $4\%$ ,  your investors keep getting $5\%$ until that paper matures.

The virtue of doing your valuations this way is that you know that your valuation of the [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] will not decrease,  which could threaten your $\$ 1$ share price

X This accounting rule makes money funds especially interested in buying [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] with 60 or fewer days to maturity x Or in other words,  if you as a [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] issuer keep your maturities in this range,  you’ll get better prices from the biggest part of your customer base

Another influence on [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] maturities is the Fed’s rule that banks can use [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] as collateral for borrowing at the discount rule as long as its maturity is not greater than 90 days

X Banks therefore have little interest in buying longer-maturity CP

SEC regulations also affect the relative demand for highand low-rated paper. The SEC divides all [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] into three categories

X Tier-1: At least two ratings of A-1 or the equivalent from NRSROs x Tier-2: At least two ratings of A-2,  but not two of A-1 x Everything else

A money fund can invest only in Tier-1 and Tier-2,  and can invest only $1\%$ of its money in any one Tier-2 issuer,  and only $5\%$ of its money in all Tier-2 issuers put together

X So the investment of money funds in Tier-2 paper is limited to $5\%$ of their total assets. This holds down demand for Tier-2 paper x This is part of why demand goes down abruptly when paper is downgraded

# University of Chicago

Booth School of Business

# Financial Markets and Institutions

# Business 35202

Class Note 12 Part '5 HSRV

# [[Class Note 12 Part 2 Repos|repurchase agreements]] (Repos)

Probably the easiest way to be introduced to [[Class Note 12 Part 2 Repos|repos]] is through an example. Suppose I have a security with a market value of $V_{s}$ ,  say $\$ 1\mathbf{M}$ . You and I can enter into the following agreement:

Today,  I sell you my security for $V\!.$ - m . Say $\$ 1\mathrm{M-}\$ 50\mathrm{K}=\$ 950\mathrm{K}$ $\bigcirc$ We would refer to $m/V,  5\%$ in this case,  as the margin ,  or haircut Today,  I also agree to repurchase the security tomorrow for $\bigcirc$ V - m ,  i.e. the amount I sold it to you for,  plus $\bigcirc$ Interest on $V\!.$ -m at a negotiated rate,  say $1\%/$ year  So the interest would be $\$ 950\mathrm{K}(1/360)(1\%)=\$ 26.38$  This is how interest is calculated in this case: the loan amount (\$950 K) times the number of days divided by 360 (1/360) times the annual rate $(1\%)$ o So tomorrow,  I am supposed to pay you $\$ 950{, }026{.}38$ ,  and you are supposed to give me my security back

Here are the key things to notice about this transaction

I am simultaneously $\bigcirc$ Lending a security,  and $\bigcirc$ Borrowing money (i.e.,  the $\$ 950\mathrm{K}$ ),  on which I pay interest Simultaneously,  you are o Borrowing a security,  and o Lending money,  on which you get interest If I default on my obligation to repurchase the security,  then you can try to make yourself whole by selling the security. O Since the security was originally worth $5\%$ more than the loan,  it will be sufficient to make you whole unless its value dropped by more than $5\%$ during that day If you default on your obligation to sell the security back to me for the negotiated price of $\$ 950{, }026{.}38$ ,  then I keep that amount

O Since the security was worth more than the loan amount,  I am losing money in this situation unless the security’s value dropped by more than $5\%$ ,  in which case I’m better off with the cash than the security

So you can think of a repo as collateralized borrowing of cash – I am borrowing against the value of my security by simultaneously selling it and contracting to repurchase it tomorrow (or,  instead of tomorrow,  whatever other day we agree upon).

You can equivalently think of it as collateralized borrowing of the security by the other side of the repo. We will return to that perspective tomorrow

Notice that there are three key elements to a repo agreement

The margin ( $5\%$ in our example) The term (1 day in our example) The interest rate ( $1\%$ in our example)

[[Class Note 12 Part 2 Repos|Repos]] are fundamental to how institutions engaged in securities trading and dealing finance themselves. Notice that if I wanted to buy the security in our example for $\$ 1\mathbf{M}$ from someone,  say Albert,  I could do the following

Agree with Albert that I’ll buy the security from him for $\$ 1\mathbf{M}$ Arrange with Bob to do a repo of this security with him,  say at the terms discussed above

Then simultaneously,  the following things all happen $\bigcirc$ Albert gives me the security $\bigcirc$ I pass it on to Bob $\bigcirc$ Bob gives me the $\$ 950 K$ $\bigcirc$ I add $\$ 50\mathrm{K}$ out of my own pocket to the $\$ 950 K$ ,  and give the $\$ 50\mathrm{K}{+}\$ 950\mathrm{K}{=}\$ 1\mathrm{M}$ to Albert

At this point,  Albert is out of the picture. He’s delivered his security and gotten his $\$ 1\mathbf{M}$ ,  so he’s all done. My remaining relationship is with Bob,  from whom I’m borrowing money at $1\%$

The next day,  let’s say I want to sell the security to Charles,  who’s offering $\$ 1.1\mathbf{M}$ for it. I can agree to sell it to Charles for that much,  and then the following things all happen simultaneously

Bob gives me the security I pass it on to Charles Charles gives me the $\$ 1.1\mathbf{M}$ Out of the $\$ 1.1\mathbf{M}$ ,  I pay $\$ 950{, }026{.}38$ to Bob $\bigcirc$ Which leaves me with $\$ 1.1\mathbf{M}{\cdot}\$ 950, 026.38=\$ 149{, }973.62$ $\bigcirc$ So my net profit it is $\$ 149{, }973{.}62{\cdot}\$ 50{, }000{=}\$ 99{, }973{.}62$

Notice that,  as long as Bob and I end our repo according to the contract,  Bob is not exposed at all to the value of the security. The rise (or fall) of its market value accrues completely to me.

Notice also that the margin I negotiate with Bob is what determines how much cash of my own I need to do this transaction. With a $5\%$ margin,  $\mathrm{I}"\mathrm{m}$ paying in only $5\%$ of the purchase price

# Tri-Party Repo

Much of the repo that occurs is what is called tri-party repo . All this means is that a third party gets involved as follows. Suppose I want to do the repo described above,  and suppose Bob wants to do it too,  but I don’t trust Bob and he doesn’t trust me. Suppose also,  though,  that we both trust JP Morgan. Then we could both do repo with JP Morgan:

I do the same repo as above,  except now the other side of the trade isn’t Bob ,  it’s JP Morgan,  and the interest rate isn’t $1\%$ ,  it’s $1.25\%$ Bob does the same repo as above,  except now the other side of the trade isn’t me,  it’s JP Morgan,  and the interest rate isn’t $1\%$ ,  it’s $0.75\%$ So now I’m paying $0.25\%$ more interest,  but what I get for that is more security: I am less worried that my counter party will default on its obligation to sell me the security back at the prearranged price And Bob is getting $0.25\%$ less interest,  but he also gets more security: he is less worried that his counter party will default on its obligation to buy the security back at the prearranged price JP Morgan makes the spread of $1.25\%–0.75\%=0.50\%$ in exchange for bearing our counter party risk

# Run on the Repo Market

If you are lending money in a repo transaction,  the margin is what’s protecting you against the scenario where 1) your counter party fails to repurchase the security,  and 2) the security’s price has dropped.

If you think this scenario is highly unlikely,  then maybe you wouldn’t require any margin at all. But as you start getting worried about your counter party,  or about the risk of the security,  then you start requiring more margin

Let’s say the security in our example is a subprime mortgage-backed security,  and you get a little anxious about these. So you decide that $5\%$ margin isn’t enough; now you want $10\%$ .

So when I return to you tomorrow to repurchase the security as contracted,  and I ask you if we can do it again,  you say “Sure,  as long as we increase the margin to $10\%$ ” $10\%$ margin on a $\$ 1\mathbf{M}$ security is $\mathbb{S}100\mathbb{K}$ . So this means I have to pay in $\$ 50\mathrm{K}$ more

What if I don’t have $\$ 50\mathrm{K}$ more? Then I can’t do the repo with you,  and if everybody else demands $10\%$ ,  then I’ll just have to sell the security today,  even if there’s no ready buyer for it.

So let’s say I sell the security,  and I don’t get a good price,  say $\$ 960 K$ rather than $\$ 1\mathbf{M}$ . Now everybody else doing [[Class Note 12 Part 2 Repos|repos]] of that security are going to be affected,  because the lenders will say

 “This security is now apparently worth $\$ 960 K$ ,  not $\$ 1\mathbf{M}$ . So now,  I’m willing to loan only

 $(\$ 960\mathrm{K})(90\%){=}\$ 864\mathrm{K}$ against it”

That is,  they are marking the security to market So everybody else borrowing against it now has to not only put up the $10\%$ margin,  but they also have to pay even more cash to cover this decrease in the mark-to-market value of the security Some of them won’t have this much cash,  and will be forced to sell These forced sales will push the mark-to-market value down even more,  and force even more investors to sell,  and so on Lenders are likely to respond to the increased risk of the securities by increasing margin,  which increases the stresses on investors even more

This is again like a bank run,  though with a twist. The twist is that marking-to-market spreads the contagion from borrower to borrower . That is,  if my lenders aren’t nervous but Fred’s lenders are,  and they force Fred to sell at a bad price,  then that bad price is used by my lenders to reduce how much they’ll lend to me,  which makes me more likely to sell,  and that reduces the market price more,  and that makes someone else sell,  and so on. So the whole market ends up shrinking.

Here’s a graph showing margins (i.e. haircuts) of different quality mortgage-backed securities over time:

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/ab8cf23d042196459d9c7375f8f35b572102bea8c761861d9c21009612fce633.jpg)

G. Gorton,  A. Metrick / Journal of Financial Economics 104 (2012) 425–451

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/a81d806a6d5b77e0d23a571d838d787049a4a8143329a171c40f7a59a7df8954.jpg)

Fig. 4. The repo-haircut index. The repo-haircut index is the equally weighted average haircut for all nine asset classes included in Table 2,  Panel D.

Notice that

Margins are zero until the summer of 2007 Then they start ramping up and up,  with margin on subprime eventually reaching $100\%$ o Meaning,  we won’t lend a dime against subprime collateral So the amount of cash investors needed to keep holding their mortgage-backed securities,  particularly the subprime ones,  went way up. So they had to either re capitalize,  sell their securities,  or go bankrupt (maybe all 3) There are no hard numbers on how much the repo market shrank. Obviously it shrank significantly

What has the Fed done about the repo market? They have introduced a program known as the Primary Dealer Credit Facility ,  whereby the Fed will loan money to dealers,  taking as collateral the kind of securities that would normally be used in repo transactions. These loans aren’t [[Class Note 12 Part 2 Repos|repos]] but they are similar. The total size of this program is about $\$ 20\mathrm{B}$ .

# Money Market Mutual Funds

Retail investors have two similar alternatives

Deposit in a bank

Invest in a money market mutual fund

Money market mutual funds (I’ll call them just money funds) were invented to simulate bank deposits,  and yet pay more interest. The first money fund,  the Reserve Fund,  was rolled out in the 1970 s,  when banks were limited in how much interest they could pay,  and the interest rate that could be earned on [[Class Note 12 – Commercial Paper#Class Note 12 – Commercial Paper|CP]] and similar securities went much higher. Even though those limits on banks are gone now,  money funds remain popular as a way to get more interest than banks pay. However,  while banks have deposit insurance,  money funds are not insured,  so with that extra yield comes extra risk.

Over the years,  money-fund investors experienced almost exactly zero risk. This is because every time a money fund made an investment that went bad,  the fund family ate the loss by buying the bad investment from the fund at 100 cents on the dollar. That is,  the fund families did not have to protect money-fund investors from the loss,  but they did anyhow to protect the impression that money funds are virtually risk-free. What this has meant is that the share price of (virtually) all money funds has always stayed at precisely $\$ 1/$ /share. In the language of the industry,  the funds avoided “breaking the buck.” Money funds prospered,  and their total assets are now $\$ 3.75$ Trillion.

But on September $16^{\mathrm{th}}$ ,  2008,  after Lehman went down,  it turned out that a big investor in Lehman paper was none other than the Reserve Fund,  the original money fund. The loss was far too big for the fund to cover,  so they broke the buck. This led to a run on money funds,  which in turn led to a giant spike in money-market rates,  as money funds became sellers rather than buyers of money-market instruments,  and this in turn was causing severe stress to corporations funding themselves in the money market. The Treasury intervened on September $19^{\mathrm{th}}$ ,  announcing that it would guarantee all existing investments in money funds that 1) had not already broken the buck,  and 2) paid a small fee to be included in the program. All the major fund families have joined this program

So if you had $\$ 10\mathrm{K}$ in a money fund on September $19^{\mathrm{th}}$ ,  and you’ve left it there,  and your ' fund family paid into this program,  then that $\$ 10\mathrm{K}$ was guaranteed by the Treasury Essentially,  this is complete deposit insurance for these deposits The program was extended to September $18^{\mathrm{th}}\,  2009$ . This program succeeded in stopping ' the run. New regulations of MMF were put into place,  but more are probably on the way. 3 ULPH'PRQH\'PDUNHW'IXQGV'H[SHULHQFHG'UXQV'DJDLQ'LQ'0 DUFK''DQG'JRW'D'QHZ' JRYHUQPHQW') HGHUDO'5 HVHUYH'OHQGLQJ'SURJUDP'WR'VWRS'LW

University of Chicago Booth School of Business

Financial Markets and Institutions Business 35202

Class note 13: The [[Class Note 13 The LTCM Meltdown|LTCM]] meltdown

# I. Introduction

To understand Long Term Capital Management’s ([[Class Note 13 The LTCM Meltdown|LTCM]]) meltdown,  note that they were taking liquidity risk in two ways. First,  they were long less liquid assets and short more liquid assets that provided almost the same cash flows. For example,  they were long the 29.5 year off the run treasury and short the 30 year on the run treasury bond. Second,  they took large margined positions. They were subject to the liquidity risk of a margin call where they would be forced to close out the position. If they faced liquidation losses from unwinding positions,  and if their capital was sufficiently impaired to make losses to lenders possible,  they could have a "run" as lenders foreclose in anticipation of other lenders foreclosing.

Whenever there is a limit to liquidity creation,  illiquid assets will need to offer higher expected returns than more liquid assets. Institutions like banks can be set up to partially arbitrage away this price of il liquidity. The arbitrage between the more and less liquid assets is a significant part of the [[Class Note 13 The LTCM Meltdown|LTCM]] strategy. They specialize in near arbitrage between assets for which it was hard to see that their only difference is liquidity (although this is not their stated goal,  it is my interpretation). [[Class Note 13 The LTCM Meltdown|LTCM]] has a comparative advantage in making these bets. They have the quantitative and creative skills to value the assets (probably the best such skills in the world). And because they lock in investors for a long term,  it seemed unlikely that they would need to liquidate early.

Their losses got so large that they faced problems with margin calls rather than investor withdrawals. Thus,  they lost their long horizon. Second,  during the period of panic after the Russian default,  the significance of liquidity on asset prices increased. The Russian default revealed information that the International Monetary Fund (the closest thing to an international lender of last resort) would not bail out a country that did not live up to its promises,  even if this might damage the stability of world financial markets. Investors gravitated toward more liquid assets,  depressing the price of illiquid assets relative to liquid. This caused the correlation between their positions to increase beyond

What had existed in the previous data they had used to estimate the value at risk in their positions.

All of this we can easily understand in the Diamond-Dybvig bank run model. It shows that it pays to try to earn the liquidity premium,  but that you are exposed to the risk that you might melt down. That model does not stress that some liquidity bets are hard to see and require special asset pricing skills to identify. In addition,  there is more that we can learn by focusing in general on the risk of taking long-term arbitrage-like positions.

The goal of this class note is to understand the risks in taking positions that are very similar to riskless arbitrage opportunities. I want to both simplify and extend the ideas in the Shleifer-Vishny paper in the packet,  "The Limits to Arbitrage." Read the words in that paper. You can use the math in this note if you do not want to invest in the math in their model.

Begin with a traditional arbitrage opportunity. Suppose that shares of ExxonMobil on the NYSE sold for $\$ 90$ per share,  and those on the Chicago stock exchange sold for $\$ 80$ per share. If you can simultaneously buy 1 million in Chicago shares and sell short 1 million on the NYSE,  you make a sure profit by immediately covering the short with the shares you buy in Chicago. If the cost were less than $\$ 10$ per share,  anyone who saw this would make the trade. It takes little skill to see that all ExxonMobil shares are the same security,  so we expect that the price will not be much different on the two exchanges.

Suppose that instead,  there were two "effectively similar" trades. For example,  suppose that a share of a holding company would distribute one share of ExxonMobil plus one of Chevron Texaco in exactly two years,  and that the holding company was selling for less than the price of one share of ExxonMobil plus one of Chevron Texaco. You can't just short one share of ExxonMobil and one of Chevron Texaco and buy one share of the holding company to immediately cover the short. There are two problems: the items are not legally identical,  and it may be that some others do not see that the holding company will eventually be exactly identical to the two shares of oil stock. Because they are not legally identical,  you must carry the position for two years to cover the short. Further,  if not everyone sees that positions are identical; the prices will not

Necessarily always be in line. The fact that not everyone sees them to be identical is the reason that they might be out of line today,  presenting the apparent profit opportunity to you.

Because not everyone sees the opportunity today,  it is quite possible that not everyone will see it in one year. If you need to close out the position in one year,  the gap may have widened. This is not a problem if you never need to close it out in one year and you have no limit to the amount of capital that you can bring to such positions.

Because outside investors and lenders do not know the ability or see the models of hedge fund managers,  they will limit the amount of capital that they provide to managers. Investors and lenders do see their ex-post performance and use it to estimate the ability of managers. This is the reason for arb it rage urs' limited access to capital and for things that work like margin calls after a loss. Shelifer and Vishny call it performance based arbitrage ("PBA") . If an a rbi tr ague r ("arb") loses money,  then outsiders reduce their estimate of the quality of the arb’s analysis,  and pull out funds or force him or her to liquidate positions (or,  if the outsider is a lender,  force margin calls). This note examines how limits on the amount of capital that an arb can raise,  and these possible future losses of capital under management,  can influence the bets that an arb will place. We examine a very simple version of this: investors will pull all funds under management out whenever there is a loss. More generally,  the amount of capital available would be a function of the extent of the loss,  but we can see the main point with the more extreme assumption that if the arb loses any money at all,  he loses all assets under management. This simplifies the analysis because the arb will just choose whether to invest at date 1 or date 2,  instead of choosing the fraction of funds to invest at each date.

# II

# An Example

Consider two assets that will be identical on date 3,  but it is not clear yet that they are identical. On date 3,  asset A will be worth 100 units of asset B. If A is not selling for 100 times the price of B,  there is a long-term arbitrage opportunity.

Today is date 1 and the price of asset A is ${\mathfrak{p}}_{1}$ ( ${\bf\hat{p}}_{1}$ is the date 1 relative price of asset A to asset B,  and the relative price will become 100 on date 3). On date 2,  the assets will revert toward the proper price of 100 (possibly all the way) with probability 1q. We will refer to this revision toward the proper price as a “ news trade .” With probability q,  however,  the mis-pricing will get worse,  and the price will be $\mathtt{p}_{2}{<}\mathtt{p}_{1}{<}100$ . Following Shleifer-Vishny,  we will say that this further mis-pricing is due to misinformed “ noise traders .” It could be for any reason,  however. If the assets differ in liquidity,  and the significance of liquidity increases,  this is an alternative motivation for the prices diverging.

Extreme performance based arbitrage works as follows. If the arb loses money at date t,  he is out of the arb business forever (could generalize this to "if he loses enough money, " but this makes the math a little harder).

The arb gets compensated as a percentage of assets under management (a very similar analysis applies if instead the arb gets a percent of profits).

Suppose that the price at date 1 is ${\mathsf{p}}_{1}=80$ ,  and that on date 2 with probability q it will fall to $\mathtt{p}_{2}{=}70$ (due to a noise trade) and with probability 1-q it will rise to by 20 to ${\mathfrak{p}}_{2}$ $=100$ (due to a news trade). On date 3 the bet will mature and as a result,  $\mathtt{p}_{3}{=}100$ for sure.

To see the effect of PBA,  let us compare it with a benchmark of the case of someone investing his or her own money ,  which is equivalent to a hedge fund not subject to PBA.

# II. A. Decisions by an investor not subject to Performance Based Arbitrage

If the non PBA investor invests at date 1 ,  the value at date 3 is 100 for sure,  so if the investor invests $\mathbf{D}_{1}$ at date 1,  the date 3 value is: $$\begin{array}{c} {{(100/80){\bf D}_{1}~\mathrm{or}} }\\ {{{}} }\\ {{(\mathrm{V}/{\bf p}_{1}){\bf D}_{1}~.}} \end{array}$$

If instead the non PBA investor waits until date 2 to invest (and just holds treasury bills yielding $0\%$ for the period),  then the price will be 70 or 100 (with prob q and 1-q respectively). When the price drops to 70,  the non PBA investor will buy $\mathrm{D}_{1}$ units,  and when the price is 100,  the investor will continue to hold treasury bills. The expected date 3 value of waiting until date 2 to take a position is:

in general $$\begin{array}{r l} {{\mathrm{[q(100/70)+(1\!\!-\!\!q)1]D_{1}} }}& {{\qquad\mathrm{or, }} }\\ {{\mathrm{[q(V/p_{2})+(1\!\!-\!\!q)]D_{1}} }.}& {{}} \end{array}$$

The non PBA investor will go ahead and invest at date 1 when it gives a larger expected value of assets,  or: $$100/80\ \geq\mathbf{q}(100/70)+(1\mathbf{-}\mathbf{q}), \, \mathrm{or}$$ $$\mathrm{q}<7/12=0.58$$

A regular investor would wait only if the increased expected return from waiting to invest times the probability that the return increases,  exceeds the return from investing today.

# II. B. Decisions by a hedge fund that is subject to PBA

If the PBA arb invests $\mathbf{D}_{1}$ at date 1,  his fund is closed with probability q,  when the price moves away from fundamental value.

Investing $\mathbf{D}_{1}$ at date 1 produces expected date 2 assets under management of: $$(1{\cdot}{\mathrm{q}})(100/80){\mathrm{D}}_{1}+{\mathrm{q}}(0).$$

The last term,  ${\bf q}(0)$ is zero because,  if he loses money,  he is out of business.

If the PBA arb waits until date 2 to invest ,  he won't lose assets under management,  but with probability 1-q,  the profit opportunity goes away. The expected value of date 3 assets under management if he waits to invest at date 2 it then: $$\mathrm{q (100/70) D_{1}+(1\!\!-\!\! Q) D_{1}}.$$

The PBA arb invests at date 1 when: $$\mathrm{(1\mathrm{-}q)(100/80)\geqq (100/70)+(1\mathrm{-}q)\quad~\mathrm{or}}$$ $$\mathsf{q}<7/47=0.15$$

Thus,  arbs subject to PBA are averse to profitable long-term bets that might go against them .

If it takes special skill to see these opportunities,  and all with those skills are subject to PBA,  long-term risky investments won't be undertaken by arb's.

Table 1: Current and future prices:

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/28310ecfa7f04d40a9d94f39b386155cdf295520b29db569c8ee4b19e3cbbb25.jpg)

On date 2,  any arbs that see the opportunity will invest in it,  so long as $\mathfrak{p}_{2}{<}100$ . But that need not prevent the market from being out of line at date 2. The arbs who see the date 2 opportunity have limited access to capital,  and as a result they will not push the price all the way to 100,  despite being a pure arbitrage. Remember that it is not obvious to all that this is an arbitrage opportunity.

The prices in table 1 already reflect the activities of arbs. We will assume that $\mathbf{q}=$ 0.25 for some examples,  and for other examples we assume $\mathrm{q=0.5}$ . For both values,  no arb subject to PBA will trade at date 1 $\scriptstyle (q>0.15)$ ,  but non PBA arbs will trade at date 1 $(\mathrm{q}{<}0.58)$ .

# II . C. [[Class Note 13 The LTCM Meltdown|LTCM]] as a long term arb

Suppose that your fund had a very good reputation,  and you could get funds locked in and avoid PBA. You would have a relatively easy life (assuming that you really did have the skill to see opportunities),  because long term opportunities would be passed over by short term PBA funds.

Suppose that at date 1 there are PBA funds and your long-term fund. The PBA funds wait until date 2 to get in,  hold treasuries from dates 1 to 2,  and hold treasuries from 2 to 3 if the arbitrage opportunity is gone by then.


 - The two-period expected return of a PBA fund is : $$\begin{array}{r l}{\mathrm{q}(100/70)\;+\;\;(1\;\cdot\;\mathrm{q})\;(1)\;=\;\mathrm{q}(1+3/7)\;+\;(1\;\cdot\;\mathrm{q}) 1\;}&{\;=\;\mathrm{q}(3/7)\;+\; 1}\\ &{\;=\; 0.25 (3/7)\;+1=1.0525\;(\mathrm{for~q=0.25})}\end{array}$$

The twoperiod return of the long-term fund (assuming that it raises no new capital at date 2,  so it can't scale up its bet if the price goes down at date 2),  $100/80\ =1.25.$

The ability to lock in the funds for the long term allows the fund to take different bets in markets with less competition. This is part of the story behind the establishment of [[Class Note 13 The LTCM Meltdown|LTCM]]. Their reputation was so strong that they could get money locked in.

The problem arose when they lost so much money that they faced margin calls. For a large enough loss,  even [[Class Note 13 The LTCM Meltdown|LTCM]] had the equivalent of PBA,  leading to forced sales at the bottom. [[Class Note 13 The LTCM Meltdown|LTCM]] had locked in investor's old money. But once they had lost enough to face margin calls,  their ability to raise new capital to meet the calls without liquidating their positions was limited. Not only was there standard PBA uncertainty about [[Class Note 13 The LTCM Meltdown|LTCM]]'s ability to continue to make excess returns at low risk,  but there was a bank run style collective action problem. Unless [[Class Note 13 The LTCM Meltdown|LTCM]] could attract enough capital to meet all near term margin calls,  it would be forced to get out at the bottom. Anticipating this,  they would be unable to raise smaller amounts of capital. Since the market thought it was likely that they would soon liquidate and push down the price,  the current price of their positions moved against them due to front running.

Let us modify the notion that [[Class Note 13 The LTCM Meltdown|LTCM]] will not lose funds under management,  to assume instead that they will lose them only if their loss is very large (defined below). If [[Class Note 13 The LTCM Meltdown|LTCM]] assumed that their losses would not be “very large”,  this would not affect the position that they take. And if they (and others like them) did get such a loss,  it would push down the price as they were forced to liquidate.

A large unanticipated price drop would result in a meltdown (forced liquidation). A meltdown causes an even larger price drop when the arbs ([[Class Note 13 The LTCM Meltdown|LTCM]] in particular)

Liquidate. Normally,  the trades of arbs are a stabilizing force,  offsetting the trades of noise traders who would push the price further below 100. When there is a meltdown,  this reverses. Instead of being a stabilizing force,  the arbs further destabilize the price by joining the selling.

To evaluate this further,  we need to think about price formation . This gets a bit complicated,  and we will just follow Shelifer-Vishny.

The prices we used in table 1 are those that prevail AFTER the arbs have put on their trades. If there were no trades coming in during a period,  the price would remain unchanged. If there were only noise trading,  the price goes down when noise traders sell and up when they buy. If there is also some trade by arbs,  the price changes by the net amount of trade. That is: $$P_{t}=\left\{\!\!{\cal P}_{t-1}\!+\!\mathrm{Noise~trace}+\mathrm{orb~trades}\quad\mathrm{(happens~with~prob~q)}\right\}.$$

We could allow for arb trades in addition to news trades,  but in normal circumstances,  news trades from many investors who see the mis-pricing will be sufficient to remove arbitrage opportunities.

Let us assume that [[Class Note 13 The LTCM Meltdown|LTCM]] already had established a position in the trade before date 1 (because of past mis-pricing),  and was long 20 units. Thus if [[Class Note 13 The LTCM Meltdown|LTCM]] was not long 20 units,  the price would be lower by 20. Arbs who are subject to PBA would not trade before date 2. (In practice,  other arbs sometimes copied [[Class Note 13 The LTCM Meltdown|LTCM]],  so there might be some others who each took smaller positions in the same bets as [[Class Note 13 The LTCM Meltdown|LTCM]]. We will ignore this.) The prices in back in table 1 include the efforts of various arbs. If they were not present,  the date 1 and 2 prices would be lower,  in part because of liquidity differences,  in part because of "noise trader" selling.

Table 2 shows the impact of the arbs. Before date 1,  [[Class Note 13 The LTCM Meltdown|LTCM]] had a position of 20. On date 1,  the price is 80. The price would have dropped on that date,  but [[Class Note 13 The LTCM Meltdown|LTCM]] bought 5 more,  offsetting selling of 5 by noise traders on date 1. There is further noise trade on date 2 with probabiliy q. If the noise trade occurs at date 2 it is noise trader selling of 25. This is partly offset by added buying of 5 more units by [[Class Note 13 The LTCM Meltdown|LTCM]],  and buying of 10 units by PBA arbs who see the opportunity (and are willing to bet now that it is short-term arbitrage).

Table 2: Trades by arbs and noise traders that produce prices in table 1.

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/871b9df27e279ba80632713b19f2db6bba1a270798cfae02d4234a81a52eca6d.jpg)

Suppose instead that things play out differently on and after date 1. The Russian default causes panic selling at date 1 by noise traders,  when [[Class Note 13 The LTCM Meltdown|LTCM]] already has a position of 20. The noise trade at 1 is now $-30$ . If this loss is large enough to force [[Class Note 13 The LTCM Meltdown|LTCM]] out immediately at date 1,  forcing them to sell 20 at date 1,  look at the meltdown in table 3:

Table 3: A meltdown after the Russian default ,  if [[Class Note 13 The LTCM Meltdown|LTCM]] must liquidate immediately

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/da328f4bf59206b939017556ffaba195af84be05a4aee8b12f5441a8f0baae63.jpg)

The panic from the Russian crisis would make the price fall by 30 (from 80 to 50 on date 1) by itself. By forcing the [[Class Note 13 The LTCM Meltdown|LTCM]] to liquidate,  it makes the price fall by 50 (80 to 30). The losses force a liquidation,  in a way very similar to a bank run.

In practice,  [[Class Note 13 The LTCM Meltdown|LTCM]] was careful to get some advanced assurance from margin lenders not to force immediate margin calls. As a result,  they had some time to meet the calls. We can interpret this as meaning that they are not forced out at date 1,  but can wait until date 2 to sell. If the news trade were to arrive on date 2 (which happens with

Probability 1-q),  they could avoid liquidating their position. However,  with probability q,  the noise trade of $-25$ comes in at date 2,  and [[Class Note 13 The LTCM Meltdown|LTCM]] would be forced to sell on date 2.

Suppose that [[Class Note 13 The LTCM Meltdown|LTCM]] could delay liquidation until date 2,  and it could still buy 5 at date 1 to seek a profit. Then the prices after the Russian default would be those shown in table 4.

# Table 4: A delayed meltdown if [[Class Note 13 The LTCM Meltdown|LTCM]] can wait to liquidate

![](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/c068cd18b3be01146ebab2bcc82a12e452ece2071cdc4cf9b1203b9607d98837.jpg)

Let us compute the expected price change from date 1 to 2. With probability q,  there is a noise trade that forces it down to 15,  because [[Class Note 13 The LTCM Meltdown|LTCM]] is forced out. With probability ${\mathsf{1}}{\mathrm{-}}{\mathsf{q}}.$ ,  there is a news trade,  that pushes the price up to 75 (and then [[Class Note 13 The LTCM Meltdown|LTCM]] is not forced out). The expected price change is then: $$\mathbf{q}(15{-}55)+(1{\cdot}\mathbf{q})(75{-}55)=\ 20-\mathbf{q}(60)$$

For $\mathrm{q}{=}. 25$ ,  this is $+5$ ,  but for $\mathrm{q=0.5}$ ,  it is $-10$ . Let’s assume $\scriptstyle{\mathrm{q}=0.5}$ ,  and we will learn something about the front running problem faced by [[Class Note 13 The LTCM Meltdown|LTCM]].

When the expected price change from date 1 to 2 is negative,  any trader who knows that he or she must sell on date 2 will instead sell on date 1. Further,  if not subject to PBA,  it will be profitable to short on date 1 so long as the expected price change is negative. If some of this trade occurs,  it will further reduce the date 1 price. We will examine this in homework .

University of Chicago

# Booth School of Business

Financial Markets and Institutions Business 35202

New Class note (May 22,  2022 revision) TerraUSD as a bank run or as a failure of fixed exchange rates.

Here is a description of TerraUSD from CoinDesk. Com:

So,  how does it actually work?

It all has to do with arbitrage . This usually refers to the process of making small profits by finding discrepancies between asset prices on different exchanges. However,  in the case of LUNA and UST,  it works slightly differently.

In the Terra ecosystem,  users can always swap the LUNA token for UST,  and vice versa,  at a guaranteed price of $\mathsf{S}\boldsymbol{1}-$ regardless of the market price of either token at the time. This is important to note because it means if demand for UST rises and its price rises above $\mathsf{S}\boldsymbol{1}$ ,  LUNA holders can bank a risk-free profit by swapping $\mathsf{S}\boldsymbol{1}$ of LUNA to create one UST token (which due to a rise in demand in this example,  is worth more than $\mathsf{S}\boldsymbol{1}$ ).

During the swapping process,  a percentage of LUNA is burned (permanently removed from circulation) and the remainder is deposited into a community treasury. Funds in the treasury are then used to invest in applications and services that expand the utility of the Terra ecosystem.

Burning a percentage of LUNA tokens reduces the number of overall tokens left in circulation,  making them more scarce and,  therefore,  more valuable. By minting more UST tokens,  it has the effect of diluting the existing tokens in circulation and bringing the overall price back down to its $\mathsf{S}\boldsymbol{1}$ level.

Similarly,  if demand is low for UST and the price falls below $\mathsf{S}\boldsymbol{1}, $ ,  UST holders can exchange their UST tokens at a ratio of 1:1 for LUNA – which is worth more because of their scarcity and so the user can bank another risk-free profit. (End of quote from CoinDesk. Com)

What does this mean? We can see that this is a highly flawed design and is subject to runs or speculative attacks. Start with two analogies. The first is fixed exchange rates,  as the UK Pound in 1992 and the East Asian currencies in 1998. The second is a bank run.

# TerraUSD as fixed exchange rates

The fiat currencies the UK Pound in 1992 and the East Asian currencies in 1998 tried to keep fixed exchange rates to the dollar,  but failed. Each had speculative attacks on them (George Soros in the 1992 event),  but the attacks probably just speeded up an inevitable devaluation. The local governments and central banks tried to defend and maintain the exchange rate. They held US Dollar reserves to use to buy their currency to offset selling that would push down their exchange rate. This is like reserves serving as collateral held to back other crypto currencies (such as Tether),  or the one-day liquid assets held by a money market fund. Once they are gone,  an expected devaluation is probably self-fulfilling. As it turns out,  there were no reserves held at Luna or TerraUSD (see below,  about Luna Foundation Guard). The only collateral keeping the TerraUSD fixed at 1 USD was Luna,  which had no value unless it was useful as a crypto currency. If there was selling pressure on Terra,  they could be converted into $\$ 1$ worth of Luna. But if everyone is expected to swap TerraUSD for Luna and the market value of Luna is believed to be less than all the TerraUSD,  the value of TerraUSD will drop below \$1 USD. The supply of Terra will drop but nothing prevents the value of all Luna from dropping to zero (or almost zero as it is on 5/19/2022). An analogy with UK Pound is useful. There is demand for UK pounds and the UK could say that you are free to swap pounds for dollars at fixed exchange rate. This works if all believe it works forever. But if many believe that it may not work in the future all will sell pounds to buy dollars,  and the exchange rate peg will break. That’s what happened in 1992 and what happened to TerraUSD in 2022. We can see the exact same point a bit more precisely,  if we think of this as a bank run (in the next section).

TerraUSD as a bank run.

The second analogy is tranching claims into short-term “safe” debt (TerraUSD) and equity (Luna). First think of Luna as equity in the value added of Terra and Luna together. The value of the combination is much higher if TerraUSD is a stable coin than if it is predicted to blow up. Call the value if it persists as stable: VS. The value of TerraUSD coins at $\$ 1$ each is T.

There is a lower value of value of Terra and Luna together if Terra is not a stable coin. An example of a coin that is not a stable coin is Bitcoin. Call the value if TerraUSD is not a stable coin (is Unstable),  VU<VS,  the value if a stable coin. For example,  $\scriptstyle\mathrm{VO}=10<\mathrm{VS}=30.$ .

Case A (no run) Suppose everyone expects TerraUSD to survive,  be worth $\$ 1$ and be stable,  and $\mathrm{T}{<}\mathrm{V}\mathrm{S}$ the value if it persists as a stable coin. In this case the value of Luna (equity) is $\mathrm{VS-T}>0$ . One could convert Terra to Luna at $\$ 1$ ,  but would have no reason to do so once the value of Terra is $\$ 1$ . This is a self-fulfilling prophesy. For the numbers,  suppose that $\mathrm{T}{=}25$ . Then Terra USD is worth 25 and Luna is worth $\mathrm{VS-T}=30{-}25=5$ .

Case B (run). Suppose that the value of Terra satisfies $\mathrm{T}{>}\mathrm{VO}$ . If this happens then the value of Luna today is zero because it would be VU $\cdot_{}\mathrm{T}{<}0$ ,  apart from limited liability. For the numbers,  suppose that $\mathrm{T}{=}25$ ,  then Terra is worth $\mathrm{FWHM}{=}10$ and Luna is worth zero.

In a run,  anyone who holds Terra would want to convert to Luna if the price valued a TerraUSD at $\$ 1$ ,  and the stable coin Terra will not persist. Terra will drop in value to VU,  Luna will be worth zero and there will be run on the stable coin because it is unstable. Terra will become an unstable coin.

There are two self-fulling prophecies: Terra is Stable and Terra is Unstable. There is no real collateral so the most the combined entity is worth in a panic is VU. There was a reserve of some Bitcoin in Luna Foundation Guard,  a separate organization,  which was to serve a similar function reserves foreign currency (US

Dollar) reserves that a government would use to defend its fixed exchange rate against a speculative attack. But it was not enough.

TerraUSD plus Luna could be worth $\mathrm{V}\mathrm{S}{=}30$ if everyone was sure it would be worth that amount. However,  the right to convert to equity at $\$ 1$ is worthless if the value of equity is wiped out,  which occurs if everyone wants to convert. Thus,  the ability to convert TerraUSD to Luna does not provide stability or value if it is expected to melt down and have a run. In a run,  Terra plus Luna is worth only $\mathrm{VU}{=}10$ . To a first approximation,  this is what happened in May 2022. TerraUSD was a fake safe asset.

This is just a part of what was going on. The ability convert Terra to other stable coin crypto currencies provided another way to exit TerraUSD in a run (you can read about Anchor,  but that gets quite complicated).
