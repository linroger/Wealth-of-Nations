---
title: Discussion of Loan [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]]
  vs. Bond Covenants
tags:
  - bond_covenants
  - bondholder_rights
  - corporate_bonds
  - federal_trust_indenture_act
  - loan_covenants
aliases:
  - Bond Indentures
  - Covenants vs. Bond Covenants
  - Loan Covenants
  - MGM Mirage Bond
key_concepts:
  - Bond contract features
  - Bondholder voting rules
  - Covenants in indentures
  - Excessive debt risk choice
  - Limits to debt renegotiation
  - Loan contract default
  - Make-whole call option
  - US Federal Trust Indenture Act
---

# Discussion of Loan [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] vs. Bond Covenants

Business 35202 Douglas W. Diamond

Options to fix the effect of excessive debt on risk choice. (From week 1)

- Convertible Debt
- Covenants
- Just use equity (or debt-equity swap)
- Let the lender make all decisions
- Reduce the face value of debt
- All require renegotiation.

# Limits to Renegotiation
- Too many small lenders (week 3)
- Lack of information to renegotiate (week 3)
- Legal issues
- The United States Federal Trust Indenture Act.

## The US Federal Trust Indenture Act
- The US Federal Trust Indenture Act prohibits majority voting to restructure debt contracts that reduce principal,  interest,  or extend the debt maturity.
- A 100% vote is required to change these “key covenants."
- Thus,  even if public bondholders had the information,  they probably could not use it.
- Changes to other [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] in bonds are not regulated,  but many bonds require a 2/3 vote in dollar value and 50% measured in the fraction of bondholders (not weighted by dollar value).
- This is the voting rule in US Chapter 11.

1. Why are there more [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] in the loan than in the bond?
- Why do the loans have [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] that are more likely to be violated?
1. Why are there more restrictions in the 2003 Wellman loans than in the 1999 loans?
1. Why is the loan's definition of a default so different from that in the bond?
- The section on default from a 1999 loan agreement has more contingencies defining default than the MGM bond and does not have the bond's requirement that a trustee wishes to declare a default if there are violations of non-financial [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] or any requirement that at least 25% of loan holders want to declare a default in that circumstance.

1. How do the loan contracts allow the lenders to exercise control over the borrower?
 ![500](https://storage.simpletex.cn/view/fBvhPxVfMooQHmOrE3VhB1VOXxp466AqF)
 ![500](https://storage.simpletex.cn/view/f9TanvKDlldmOEsxesdgwoA2H7iGpN9oz)
 ![500](https://storage.simpletex.cn/view/fyBQEsdLHtMg0Y36BdXWWLggfoa62ZBoY)

## Class 2 - Corporate Bond Contracts

Bonds are defined by legal contracts,  called indentures,  which spell out the rights and responsibilities of both sides. We will explore this contracting by reading the prospectus of a recent offering and analyzing its salient features,  and by discussing contract features that arise elsewhere.

On December $13^{\mathrm{th}}$ ,  MGM Mirage issued a bond:
 ![500](https://storage.simpletex.cn/view/fVw0ODH0eAWXnfregsf3RHOr3H4CFSws3)

Inside the prospectus (which I've posted on the canvas webpage),  we see:

```latex
\documentclass{article}
\usepackage{amsmath}
\usepackage{graphicx}
\usepackage{array}

\begin{document}

\centering
\begin{tabular}{|l|c|c|}
\hline
& Per Note & Total \\
\hline
Initial public offering price(1) & 100\% &$750,  000,  000 \\
\hline
Underwriting discount & 0.325\% &$2,  437,  500 \\
\hline
Proceeds,  before expenses,  to MGM MIRAGE(1) & 99.675\% &$747,  562,  500 \\
\hline
\end{tabular}
\bigskip
(1) Plus accrued interest,  if any.
\end{document}
```

So the underwriters,  led by Barclays,  BNP,  UBS,  and Wachovia,  share$2.4375 MM.

The easiest place to start reading a prospectus is at the Summary,  which gives the big picture:

- Seniority
- Coupon rate,  payment dates,  and maturity
- - Call or other option features,  if any
- Issue size
- Trustee
 - Use of proceeds

In this bond's summary,  we see the same material from the Bloomberg,  and also

- There is some sort of optional redemption
- There are several covenants

We'll return to the [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] later. First,  let's look at this optional redemption. On page S-10,  we get this:

### Optional Redemption

The notes are redeemable at our election,  in whole or in part at any time at a redemption price equal to the greater of:

- $100\%$ of the principal amount of the notes then outstanding; or
- As determined by an Independent Investment Banker,  the sum of the present values of the remaining scheduled payments of principal and interest on the notes to be redeemed (not including any portion of such payments of interest accrued to the date of redemption). Discounted to the redemption date on a semiannual basis (assuming a 360-day year consisting of 12 30-day months) at the Adjusted Treasury Rate,  plus 50 basis points.
Plus,  in either of the above cases,  accrued and unpaid interest to the date of redemption on the notes to be redeemed.

What is the purpose of this call? MGM can buy the bond back for the maximum of (i) par,  and (i) the present value of the future payments on the note,  discounted at the Treasury rate plus 50 basis points. To see what this means,  note that

- The present value,  discounted at the Treasury rate plus 50 basis points,  is what the note would sell for if it were totally riskless
 	- Because,  by construction,  that's what a Treasury note with the same payments would sell for

So if we discount at the Treasury rate plus 50 bp,  we get a slightly lower number

- What the note would sell for if it traded 50 bp over Treasuries
- - The bond was issued 304 bp above Treasuries,  so 50 bp would be a much higher price,  corresponding to much higher creditworthiness
	- Even a AAA-rated issuer would not generally expect to trade within 50 bp of the Treasury yield

When the bond was issued

- It sold at par,  which implies a yield-to-maturity of equal to its coupon rate of $7.625%
- Since this was 304 bp above Treasuries,  50 bp above Treasuries would be 254 bp lower,  or $5.085%
- - In order to yield $5.085% ,  the MGM note would have had to sell for 119.72

So to exercise this make-whole call option right now,  MGM would have to pay the maximum of 100 and 119.72,  i.e0.\1.72

So,  putting this together,  the option is to buy the bond back for more than it is worth. Why bother writing this option into the contract? We'll see at the end of class,  it is there to help the bondholder get out of the contract,  should this become necessary.

Much of the rest of the prospectus is boilerplate and standard disclosure

- Currency & location of payments; tax consequences; registration; listing - Dire warnings about risks facing the issuer : Financials related to interest coverage

The key moments in the prospectus,  looking ahead to a distress situation,  are

- Covenants,  positive and negative
- - Rights of creditors if the issuer defaults
- - How the contract can be changed by a vote

### Covenants

An indenture will have a section on covenants,  which are actions the issuer either commits to do (positive covenants) or not do (negative covenants). How do they add value?

- If management always maximizes expected value,  there is no positive role for covenants. They can only reduce expected value by constraining management. A covenant might make debt sell for more,  but if it doesn't increase total value,  then it must simultaneously make equity worth less,  so the net effect to equity from selling the debt is negative.

So [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] must be there to defend against management’s bad incentives,  particularly its willingness to take negative NPV actions that move value from debt to equity.
The MGM bond lists three covenants:

## Negative Pledge

- This bond is not secured. Thus,  the assets supporting it are,  generally speaking,  the company assets that are not already pledged to other creditors.

The purpose of the Negative Pledge clause is to prevent the company from now giving some new debt a prior claim on those assets. In the prospectus on page S-12,  we see

### Limitations on Liens

Other than as provided below under "- Exempted Liens and Sale-Lease-Back Transactions,  neither MGM MIRAGE nor any of the Subsidiary Guarantors may issue,  assume,  or guarantee any indebtedness secured by a Lien upon any Principal Property or on any evidences of Indebtedness or shares of capital stock of,  or other ownership interests in,  any Subsidiaries. (regardless of whether the Principal Property,  Indebtedness,  capital stock,  or ownership interests were acquired before or after the date of the indenture) without effectively providing that the notes shall be secured equally and ratably with (or prior to) such Indebtedness so long as such Indebtedness shall be so secured,  except that this restriction will not apply to: (a) Liens existing on the date of original issuance of the notes; b-l [other exceptions]

## Restrictions on Sale and Leaseback Transactions

A sale-and-leaseback transaction is almost equivalent,  economically,  to secured borrowing.

Firm sells an asset to another firm (e.g. GE Capital) and simultaneously enters a long-term contract to lease the same asset. If the firm defaults on the contract,  the owner can take back the asset. If the lease term covers the economic life of the asset,  this is very,  very close to secured borrowing (note that the owner gets to keep the asset after the lease expires,  but its economic life is over).

So this is similar to the negative pledge clause. However,  it is not possible to pledge some of the value of the sold asset to the bondholders,  so what this restriction says instead is that sale-and-leaseback is OK as long as the sale proceeds either

- Buy new assets that are available to the bondholders,  or -Are spent on retiring MGM debt.

Other than as provided below under "-Exempted Liens and Sale and Lease-Back Transactions,  " neither MGM MiRAGE nor any Subsidiary Guarantor will enter into any Sale and Lease-Back Transaction unless either: i) [the notes would also be secured by the property] or ii)[MGM spends the sale proceeds paying down debt].

Exempted Liens and Sale and Lease-Back Transactions [MGM can enter into such transactions for up to $15\%$ of its Consolidated Net Tangible Assets].

### Consolidation,  Merger,  and Sale of Assets

This just says that MGM will not be involved in a merger or acquisition,  either as acquirer or target,  unless

- The resulting firm is still a U.S. firm responsible for paying this bond
- - The merger does not cause a default.
This prospectus does not contain some other common bond covenants,  such as
-Dividend and share-repurchase restrictions
- Asset-sale restrictions :
- Requirements to maintain and/or insure assets.

With any covenant,  the key questions are

- What bad incentives does it address?
- - What good actions does it interfere with?
- - Does the benefit of the first outweigh the costs of the second?

### Rights of creditors upon default

Following the covenants,  the indenture lists the Events of Default:

a) Default on interest beyond a 30-day grace period b) Default on principal when it’s due c) Acceleration of any other sufficiently big debt of MGM d) A sufficiently big judgment against MGM e) Default on any other covenants,  if either i) the trustee wants to pursue this,  or ii) the trustee does not want to pursue it but holders of at least $25\%$ of the bond do want to pursue it,  and holders of more than $50\%$ of the bond disagree

Reading further down,  we can condense the legalese to the following: So to put it another way,  if the debtor defaults,  then:

- If the default is a failure to pay this bond on time,  then every creditor has the individual right to take legal action to force payment. This sort of default is called a financial default. - But if the default is on anything else,  i.e.a covenant default,  then the trustee has the right to take action,  but individual creditors do not. Instead,  we see that a majority (by value) of bondholders can tell the trustee what to do.
- A quarter of bondholders can take action,  provided that a majority does not oppose them. So while it might seem that a bondholder can pursue any failure on an indenture,  in fact,  his rights are more limited than that.

## Role of the Trustee

This shows the role of the bond’s trustee,  which in the case of this MGM Mirage note is U.S. Bank. The trustee is there to represent the rights of bondholders,  but is not an active monitor like a loan officer. Rather,  it receives reports of compliance or non-compliance from the issuer and decides on the course of action.

## Example: Getty Images. HEADLINE: Getty Images Announces Commencement of Consent Solicitation for

0.50% Convertible Subordinated Debentures,  Series B Due 2023

SEATTLE,  Jan. 4 /PRNewswire-FirstCal 1/-- Getty Images,  Inc. (NYSE:GYI) today announced that it is soliciting consents (the "Consent Solicitation") from the holders of record at the close of business on January 4,  2007,  of its outstanding 0.50% Convertible Subordinated Debentures,  Series B due 2023 in the aggregate principal amount of$265 million (the “Debentures") to an amendment toand a waiver of an alleged or existing default or event of default underthe indenture governing the Debentures (the "Indenture"). The terms and conditions of the Consent Solicitation are described in the Consent Solicitation Statement,  dated January 4,  2007 (the "Consent Solicitation Statement"),  a copy of which will be attached as an exhibit to the Current Report on Form 8-K to be furnished by Getty Images to the Securities and Exchange Commission ( “SEC”). On November 9,  2006,  Getty Images announced that its Board of Directors had…

Established a special committee to conduct an internal investigation relating to Getty Images’ stock option grant practices and related accounting for stock option grants and that it would delay the filing of its Quarterly Report on Form 10-Q for the quarter ended September 30,  2006 (the "Third Quarter Form 10-Q") until the special committee's review is complete. On November 29,  2006,  Getty Images announced that it had received notices of a purported default from holders who claim to hold more than 25% in principal amount of the outstanding Debentures asserting that Getty Images’ failure to file its Third Quarter Form 10-Q by the prescribed filing date under SEC regulations was a default under Section 17.01 of the Indenture,  which incorporates by reference Section 314 (a) of the Trust Indenture Act of 1939 (the "TIA").

As previously stated,  Getty Images does not believe that it has failed to perform any of its obligations under the Indenture,  which does not contain an express covenant requiring Getty Images to provide the trustee under the Indenture or the holders with periodic reports,  such as the Third Quarter Form 10-Q. While Section 314 (a) of TIA is incorporated into the Indenture by virtue of Section 17.01 thereof,  Getty Images does not believe that the TIA requires periodic reports to be filed with the SEC or provided within any prescribed period of time.

Notwithstanding Getty Images' position regarding notices of default,  it is seeking an amendment to,  and a waiver of the alleged or existing default or event of default under,  the Indenture. The proposed amendment to the Indenture would provide that no notice of default delivered to Getty Images on or prior to March 2,  2007 that specifies os the basis for the default a failure to file with the SEC the Third Quarter Form 10-Q and/or the Company's Annual Report on Form 10-K for the year ended December 31,  2006,  as applicable,  and to file the applicable reports with the trustee under the Indenture,  shall have any force or effect with respect to the exercise of remedies by the trustee or any holder of Debentures if Getty Images files the applicable reports on or prior to May 1,  2007. The Consent Solicitation also includes a waiver of any defaults and events of default under Section 17.01 of the Indenture that may exist as a result of its failure to file the Third Quarter Form 10-Q. Getty Images proposes to make a cash payment to consenting holders of the Debentures.

of $5.00 per$1,  000 in aggregate principal amount of the Debentures (the "consent payment") held by such consenting holders,  upon or promptly following expiration of the Consent Solicitation. Only registered holders of the Debentures on the January 4,  2007,  record date that validly deliver,  and do not revoke,  consents prior to 5:00 p.m. New York City time on January 17,  2007,  the expiration of the Consent Solicitation,  will be eligible to receive the consent payment. The consummation of the Consent Solicitation (including the payment of the consent payment) is subject to the receipt of valid consents in respect of a majority in aggregate principal amount of all outstanding Debentures,  the execution of the supplemental indenture by us and the trustee under the Indenture,  and the absence of any existing or proposed law or regulation or any proceeding that would make unlawful or invalid or enjoin or delay the proposed amendment,  the entering into of the supplemental indenture,  or the payment of the consent payment.

Why limit bondholders’ rights this way?
Suppose you didn't,  and instead let any bondholder demand immediate repayment after any infraction

- May not be best for bondholders,  particularly if they are junior.
- - A bondholder may not realize this,  or may have a conflict of interest. Trustee is charged with taking the prudent action. Of course,  the trustee might misjudge or have conflicts of its own,  which is why there is the override provision.

Why does this limitation apply to covenant defaults but not to financial defaults?

- Legal Answer: This is required by the Federal Trust Indenture Act. It mandates that each bondholder has the inalienable right to get his principal and interest on time.
- Economic Answer: Bondholders can actually benefit when it is hard for the firm to negotiate with them. More on this later.

How the Contract can be Changed by a Vote
Under Modification and Waiver,  the indenture reads

We and the trustee,  at any time and from time to time,  may modify the indenture in respect of the notes without prior notice to or consent of any holder of the notes for any of the following purposes:

- To permit a successor corporation to assume our [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] and obligations under the indenture and in the notes in accordance with the terms of the indenture; to add to our [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] for the notes;
- To surrender any of our rights or powers conferred in the indenture; to add any additional events of default to supplement any of the provisions of the indenture to the extent needed to permit or facilitate the defeasance and discharge of the notes in a manner that will not adversely affect the interests of the holders of such notes in any material respect;
- to provide for the acceptance of appointment by a successor trustee with respect to the notes and to add to or change any of the provisions of the indenture as is necessary to provide for the administration of the trust by more than one trustee to comply with the requirements of the SEC in connection with qualification of the indenture under the Trust Indenture Act to cure any ambiguity; to correct or supplement any provision in the indenture which may be defective or inconsistent with any other provision in the indenture; to eliminate any conflict between the terms of the indenture and the notes and the Trust Indenture Act;
- Or to make any other provisions with respect to matters or questions arising under the indenture which will not be inconsistent with any provision of the indenture as long as the new provisions do not adversely affect in any material respect the interests of the holders of the notes.

We may also modify the indenture in respect of the notes for any other purpose if we receive the written consent of the holders of not less than a majority in the principal amount of the outstanding notes. However,  we may not,  without the consent of the holder of each note affected thereby,  change the stated maturity or reduce the principal amount or the rate of interest,  or extend the time for payment of interest on the notes or any premium payable upon the redemption of the notes,  or impair the right to institute suit for the enforcement of any payment on or after the due date thereof (including,  in the case of redemption,  on or after the redemption date),  or alter any redemption provisions in a manner adverse to the holders of the notes or release any Subsidiary. Guarantor Subsidiary Guarantee) or collateral,  if any,  securing the notes (except in accordance with the terms of the Indenture or the documents governing such collateral,  if any); reduce the percentage in the principal amount of the notes where the consent of the holder is required for any such amendment,  supplemental indenture,  or waiver which is provided for in the Indenture; or modify any of the waiver provisions,  except to increase any required percentage or to provide that certain other provisions of the Indenture cannot be modified or waived without the consent of the holder of each outstanding note which would be affected.

The Indenture provides that the holders of not less than a majority in the aggregate principal amount of the notes,  by notice to the trustee,  may on behalf of the holders of the notes waive any default and its consequences under the Indenture in respect of the notes,  except (1) a continuing default in the payment of interest on,  premium,  if any,  or the principal of,  any note held by a nonconsenting holder or (2) a default in respect of a covenant or provision hereof which cannot be modified or amended without the consent of the holder of each note.

What this says is that the issuer can change almost anything in the indenture if a majority of the bondholders agree (the text in green). What they can't change,  due to the Trust Indenture Act,  is anything having to do with timely payment of principal and interest (the text in red). That can be amended only with a unanimous vote.

Holding a vote to remove [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] and other contract features turns out to be a useful tactic for distressed firms,  which we will cover in detail. For now,  notice that one could seriously damage the value of a bond without changing its principal,  interest,  or maturity - For example,  with this bond,  one could remove the part of the indenture that says the bond is senior and instead make it junior.

The law does not mandate that [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] be changeable by majority vote. An indenture could require a 3/4 vote or some other supermajority,  and it could also require a unanimous vote.

### Defeasance

Essentially,  all [[Class Notes 2 – Corporate Bond Contracts|Corporate Bonds]] allow for defeasance and discharge.

Defeasance and Discharge. The indenture provides that we may be discharged from any and all obligations under the notes other than certain obligations to pay additional amounts,  if any,  upon the occurrence of certain tax,  assessment,  or governmental charge events regarding payments on the notes; : tree eforeenta trust

We may only defease and discharge all of our obligations under the notes if: we irrevocably deposit with the trustee,  in trust,  the amount,  as certified by an officer.

certificate,  of money and/or U.S. government obligations that,  through the payment of interest and principal in respect thereof in accordance with their terms,  will be sufficient to pay and discharge each installment of principal and premium,  if any,  and any interest on,  and any mandatory sinking fund payments in respect of,  the notes on the dates such payments are due,  and we deliver to the trustee an opinion of counsel or a ruling from the United States Internal Revenue Service,  in either case to the effect that holders of the notes will not recognize income,  gain,  or loss for United States federal income tax purposes as a result of such deposit defeasance and discharge.

In other words,  the issuer can get out of,  i.e.be discharged of,  whatever it committed to in the indenture by arranging for the bond to be paid by a trust containing sufficient securities,  i.e. to be defeased. So the firm will.

Assemble a portfolio of government bonds whose scheduled payments will pay off the bond - On or before each coupon or principal repayment date of the bond,  the portfolio pays at least as much as the scheduled payment - Place this portfolio in an irrevocable trust which is directed to use the portfolio's payments to make the remaining payments on the bond. - The investors in a defeased bond would regard it as riskless,  and it would trade at something very close to the Treasury yield - By the same token,  the cost of the portfolio of Treasuries is the present value of the bond’s future payments,  discounted at the Treasury rate. If the bond's indenture gives the issuer the right to defease the bond,  then the issuer is no longer bound by the [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] after defeasance.

Connection between defeasance and make-whole call options.

If MGM were to exercise its make-whole call option,  it would pay bondholders the present value of its bond's future payments,  discounted at the Treasury rate plus 50 bp.

- If MGM were to defease the bond,  it would buy the portfolio of Treasury bonds. The cost is the present value of its bond's future payments,  discounted at the Treasury rate. By construction,  this is a somewhat higher cost.

The net effect of exercising the make-whole option is the same as the net effect of defeasing the bond.

- After exercising the make-whole option,  the bond is gone.
- After defeasing the bond,  it is effectively gone—the payments to bondholders will come from the trust,  not from MGM,  and the [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] are no longer in effect.

From the bondholders' point of view,  the two strategies are very similar.

- With the make-whole call,  they get an amount slightly less than the present value of the future payments discounted at the Treasury rate.
- With the defeasance,  they get a bond that is now as safe as a Treasury bond,  but isn't a Treasury bond. It is still an MGM note and is probably somewhat illiquid. Which do they prefer? They might actually prefer the make-whole call,  depending on how close the defeased bond trades to the Treasury rate. In any case,  they are very similar.

