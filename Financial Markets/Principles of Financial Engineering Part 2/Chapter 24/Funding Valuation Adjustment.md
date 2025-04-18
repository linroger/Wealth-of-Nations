---
tags:
  - counterparty_risk
  - credit_support_annex
  - cva
  - dva
  - funding_valuation_adjustment
  - fva
  - trading_desk
aliases:
  - FVA
  - Funding Cost
key_concepts:
  - Counterparty Risk
  - Funding Costs Increased
  - Funding Valuation Adjustment
  - Monetary Incentives
  - Recursive Pricing Problem
---

# 24.7 FUNDING VALUATION ADJUSTMENT  

A final aspect of counterparty risk that needs to be taken into account relates to funding. When a trader manages a trading position, he or she must obtain cash in order to carry out different operations including (i) hedging the position and (ii) posting collateral. These operations have a cost and need to be funded. Accounting for this funding cost is called funding valuation adjustment. If we incorporate CVA, DVA, and FVA into the valuation of derivatives under counterparty risk, we obtain the following equation:  

$$
P_{\mathrm{with~CR}}^{\mathrm{to~bank~B}}=P_{\mathrm{no~CR}}^{\mathrm{to~bank~B}}+\mathrm{DVA}_{\mathrm{Bank~B}}-\mathrm{CVA}_{\mathrm{Bank~B}}-\mathrm{FVA}_{\mathrm{Bank~B}}
$$  

The practical implementation of FVA is not straightforward. The reason is that including fund-. ing costs leads to a recursive pricing problem that can be expressed as a backwards stochastic differential equation.  

The pre-GFC market practice related to funding was that collateral and funding were secondorder concerns when assessing the profit and loss of a trading desk. Banks were used to borrowing money by posting collateral via a variety of low-cost funding options. The borrowing cost was to a large extent offset by the interest paid on collateral by the receiving party. After the GFC, a fundamental shift occurred in the role of funding in the derivatives business since funding costs increased. What changed market practice is that the risk of credit lines being pulled if a firm is perceived as being at risk of default became very real. One practical example of the relevance of funding considerations is that a trade may appear to have a positive profit and loss, but it may also have high potential future exposure. If a credit support annex (CSA) is in place, then an adverse market could lead to significant additional funding needs in the form of a requirement to immediately post additional collateral.'' Even if there is no CSA in place, expected future losses related to the trade may cause a loss of confidence in the bank and a withdrawal of credit lines to the firm. In practice, the primary role of FVA is to provide monetary incentives for trading desks to use less funding. FVA is currently not supported by accounting rules.  
