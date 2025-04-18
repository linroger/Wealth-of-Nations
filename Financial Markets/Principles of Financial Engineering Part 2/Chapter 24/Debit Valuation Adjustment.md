---
tags:
  - counterparty_risk
  - cva
  - debit_valuation_adjustment
  - dva
  - otc_derivatives
aliases:
  - DVA
key_concepts:
  - CVA and DVA
  - DVA accounting treatment
  - DVA regulatory capital
  - Monetizing DVA
  - Unilateral DVA
---

# 24.4 DEBIT VALUATION ADJUSTMENT  

Consider the example above that we discussed. From bank B's perspective the price of the derivative was reduced by a positive CVA amount. The same adjustment seen from the perspective of the counterparty is called debit valuation adjustment (DVA). It is positive because the default of the counterparty C would lead to a discount on C's payment obligation and this can be interpreted as a gain. In this case, we continue to assume that the bank B itself is still default free. The DVA is unilateral since only the default risk of the client is included. For the two counterparties to agree, we require that the adjustment to the risk-free price be the same, but that it is added by counterparty C and subtracted by bank B. In other words we require:  

$$
\operatorname{Unilateral}\operatorname{CVA}(\mathrm{Bank}B)=\operatorname{Unilateral}\operatorname{DVA}(\operatorname{Corporate}C)
$$  

Although the concept of DVA looks simple, there are several complications in practice. First, it is difficult to monetize DVA in practice. Consider what would be required to do this. One would need to unwind trades to the counterparty to monetize DVA since it is the reduced NPV of one's derivatives payment obligations to the counterparty. Prior to default this is practically impossible to achieve given that it would involve unwinding a complex derivatives portfolio. Second, it is important to note that the treatment of DVA for purposes of derivatives pricing is distinct from that for accounting purposes. As the second example in Section 24.2 has shown, DVA is a major element in financial reporting and there were recent instances when large banks such as Citibank saw their quarterly profit and loss reports change from a loss to a profit as the credit spreads of the banks widened. Although DVA is widely used to price new OTC derivatives, its accounting treatment is more ambiguous and many firms report DVA on a separate line and identify it as an accounting charge rather than a real profit and loss. Third, the treatment of DVA from a bank capital regulation perspective is also distinct from those for pricing and accounting purposes. Despite its use for accounting and derivatives pricing purposes, until recently the BIS explicitly excluded DVA from regulatory capital calculations. However, a recent Basel Committee on Banking Supervision consultative document discusses several options of recognizing DVA for capital purposes which implies the potential for a convergence between the accounting, regulatory, and derivatives pricing treatment of DVA.9  
