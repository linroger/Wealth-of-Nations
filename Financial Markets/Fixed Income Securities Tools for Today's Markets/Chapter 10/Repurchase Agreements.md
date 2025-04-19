---
tags:
  - bond_pricing
  - collateral
  - repurchase_agreement
  - secured_loan
  - variation_margin
aliases:
  - repo
  - repurchase agreements
key_concepts:
  - collateral protection
  - collateral value
  - repo seller
  - secured loan with bonds
  - variation margin
---

# 10.1 REPURCHASE AGREEMENTS  

The most straightforward description of a repurchase agreement or repo is as a secured loan with bonds or other financial instruments as collateral. Figures 10.1 and 10.2 depict an example in which one counterparty - the "repo seller" -- borrows $\$109,898,438$ for 44 days at a rate of $0.015\%$ , while giving $\$100$ million of the 2.75s of $02/15/2028$ as collateral. At the time of the trade, the price of the bond is $109{-}283/4$ , that is, $109+28.75/32=$ 109.898438 per 100 face amount, which means that the value of the collateral at the start of the trade equals the amount loaned. In practice, the value of the collateral typically exceeds the amount loaned, and this feature. of repo is discussed next. Continuing with the present example, however, Figure 10.1 shows the flows of cash and bonds at the initiation of the trade,. and Figure 10.2 shows the flows at the expiration or unwind of the trade. In the latter, the repo seller pays principal plus interest, $\$109,898,438\times(1+$ $0.015\%\times44/360)$ , or $\$109,900,452$ , to discharge the loan, and then takes back its $\$100$ million face amount of bonds.  

![](a6a704697ad665f492e306bb61662a3214df6ebe0bb7bcc4fb582f15282da04a.jpg)  
FIGURE 10.1 Initiation of a Repurchase Agreement.  

![](ab02842fc4352fe975c8bd5c8b27fcef24a7193550b7c43cf0c1aafa3b648606.jpg)  
FIGURE 10.2 Unwind of a Repurchase Agreement.  

The lender of cash in Figures 10.1 and 10.2 is protected by the bonds taken as collateral against the loans: if the borrower of cash defaults, the lender of cash has a claim on those bonds. But lenders of cash in the repo market are protected even further by a safe harbor from the bankruptcy code, by a haircut or initial margin, and by variation margin.  

With respect to the safe harbor, if the borrower of cash defaults on its. loan, the lender may immediately liquidate the bonds held as collateral to. recover the loan amount, returning any realized excess cash to the borrower. This is very different from the general treatment of secured loans, in which lenders are stayed or prevented from liquidating the collateral of defaulting borrowers until given permission to do so by a bankruptcy court. It is. for this reason, in fact, that repo trades are legally structured as repurchase agreements and not as secured loans. Legally, the borrower of cash, that is,. the repo seller, sells the bonds to the repo buyer at the start of the trade and agrees, at unwind, to repurchase the bonds at a slightly higher, prespecified price. While economically the same as a secured loan, this legal structure.  

casts the unwind as the settlement of a securities trade, which enjoys a safe harbor from bankruptcy rules.1  

In addition to the safe harbor, lenders of cash in the repo market are typically protected by haircuts or initial margin. At a haircut of $3\%$ for example, collateral value is reduced by $3\%$ when considered against the loan amount. Therefore, a repo seller can borrow only $\$97$ against a bond worth $\$100$ leaving a margin of $\$3$ , that is, an excess of collateral value over loan value of $\$3$ In the example of this section, with a haircut of $3\%$ , the cash borrower raises only. $97\%$ of $\$109,898,438$ , or $\$106,601,485$ , against the. $\$100$ million of the 2.75s of 02/15/2028, leaving initial margin of $\$3,296,953$ . With this buffer, if the borrower of cash defaults and the bonds fall in value from $\$109.9$ million to, say, $\$108$ million, the lender still has more than enough collateral value to cover the outstanding loan amount of $\$106.6$ million.  

Variation margin, the last of the protections mentioned earlier, requires borrowers to maintain collateral value as prices change so as to keep margin constant. Continuing with the example in the previous paragraph, if the bonds' value falls from $\$109.9$ million to $\$108$ million against the. $\$106.6$ million loan, the cash borrower receives a margin call to post additional bonds with a value of. $\$1.9$ million to restore margin to the original. $\$3.3$ million. Alternatively, the borrower can satisfy the call by paying the lender $\$1.8$ million in cash, which reduces the loan amount from $\$106.6$ million to $\$104.8$ million, which is appropriately collateralized by $\$108$ million of bond value at a haircut of. $3\%$ . If, on the other hand, bond value increases, the cash borrower can take back posted collateral or cash in excess of margin requirements. Variation margin calls in the repo market are typically issued daily.  

Summarizing the protections in a repo agreement, a lender of cash suffers a loss only if the borrower defaults at the same time that collateral declines in value by more than posted margin.2  
