---
tags:
  - bilateral_counterparty_risk
  - cva
  - dva
  - gfc
  - valuation
aliases:
  - BVA
key_concepts:
  - Bilateral valuation adjustment
  - Corporate and bank risk
  - Counterparty defaults first
  - Default risk-free price
  - Unilateral perspective
---

# 24.5 BILATERAL COUNTERPARTY RISK  

So we have adopted the unilateral perspective. What would happen if both counterparties view each other as risky? For example, the corporate C could view bank B as risky. After the demise of. Lehman Brothers in 2008 and multiple credit events involving financial institutions during the GFC this is a realistic scenario. The only way to deal with this situation is to allow both counterparties. to include their own default besides the default of the counterparty into their valuation. This implies that each counterparty will subtract a positive CVA value from and add a positive DVA to the default risk-free price of the transaction. In other words, the CVA of one party will be the DVA of another party and vice versa. In the example above, we will obtain the following equation from bank B's perspective,  

$$
P_{\mathrm{with}\mathrm{CR}}^{\mathrm{tobank\mathrm{B}}}=P_{\mathrm{noCR}}^{\mathrm{tobank\mathrm{B}}}+\mathrm{DVA}_{\mathrm{Bank\mathrm{B}}}-\mathrm{CVA}_{\mathrm{Bank\mathrm{B}}}
$$  

From the perspective of corporate $\mathrm{^C}$ , the value of the deal has the opposite sign:  

$$
\begin{array}{r}{P_{\mathbf{no}\mathrm{{CR}}}^{\mathbf{to}\mathbf{bank}\mathbf{B}}=-P_{\mathbf{no}\mathrm{{CR}}}^{\mathbf{tocorporate}\mathbf{C}}}\ {\mathrm{DVA}_{\mathrm{{Bank}\mathbf{B}}}=\mathrm{{CVA}_{\mathrm{{Corporate}\mathbf{C}}}}}\ {\mathrm{DVA}_{\mathrm{{Corporate}\mathbf{C}}}=-\mathrm{{CVA}_{\mathrm{{Bank}\mathbf{B}}}}}\end{array}
$$  

Equations (24.12)-(24.15) imply that  

$$
P_{\mathrm{with~CR}}^{\mathrm{to~bank~B}}=P_{\mathrm{with~CR}}^{\mathrm{to~corporate~C}}
$$  

This means that both counterparties agree on the price. It is common to refer to the difference (DVA-CVA) as the bilateral valuation adjustment (BVA). One of the complications that arises with BVA is that it requires agreeing on which counterparty defaults first, since when one counterparty defaults its CVA is triggered and the other parties are not.  
