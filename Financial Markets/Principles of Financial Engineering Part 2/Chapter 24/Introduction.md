---
tags:
  - cds
  - counterparty_risk
  - credit_risk
  - cva
  - derivatives_pricing
  - financial_engineering
  - option_valuation
aliases:
  - CVA and Derivatives
  - Credit Valuation Adjustment
  - Introduction to Counterparty Risk
key_concepts:
  - CDS and credit risk models
  - CVA and its applications
  - Counterparty risk in derivatives
  - Financial engineering tools used
  - Impact on market makers
---

# 24.1 INTRODUCTION  

In this chapter, we review recent innovations in financial engineering that attempt to better incorporate counterparty risk into derivatives pricing. The topics covered in this chapter are very much at the forefront of financial engineering practice and derivatives research. In previous chapters, we showed how basic principles such as swap cash flow engineering, option valuation, and dynamic replication. can be used to construct and value more complex products. Our hope is that the reader now appreciates the commonality in the approaches to different asset classes and financial engineering problems.. In this chapter, we will see how some of the tools that we studied earlier can be used to better account.  

for counterparty risk. We will see that it is possible to model and incorporate counterparty risk in a derivatives transaction by applying several financial engineering tools that we encountered before including option valuation and CDS. In particular, credit valuation adjustment (CVA) is shown to resemble an option on the residual value of the portfolio with a random maturity given the default time of the counterparty. The default probability and default intensity for the counterparty can be backed out from CDS spreads. Thus some approaches to counterparty risk build on credit risk financial engineering tools such as CDS and structural models of default that we saw in Chapters 18 and 19. Some collateral agreements allow the choice of collateral and this choice leads to an embedded option. This optionality has recently been addressed by ISDA's so-called SCSA (standard credit support annex). Finally, some solutions that attempt to hedge counterparty risk build on CDO structuring ideas that we encountered in Chapter 21. Thus, as in previous chapters we can use basic financial engineering principles to address counterparty risk.  

Incorporating counterparty risk-related adjustments significantly changes pricing formulae for. derivatives and in practice it significantly changes valuations and behavior by market makers whose. perspective is central to this book. The reason why we chose not to deal with counterparty risk by. asset class in each chapter is that we first needed to develop the option valuation, CDS and CDO toolkit that we apply to address counterparty risk. Therefore, despite their importance, it is best to deal with more advanced counterparty risk issues at the end of the book so that the reader has had. time to absorb the tools studied in the previous chapters..  

Throughout this book, we have used financial engineering tools that price derivatives as if we lived in a world without counterparty risk. Counterparty risk affects many aspects of financial markets and banking including but not limited to derivatives pricing. First, incorporating counterparty risk has implications for financial derivatives pricing and the organization of banks. Many banks now make adjustments to the default-free derivatives that reflect the risk of their counterparty defaulting, so-called CVAs.' The principle of CVA is similar to that of a price discount for default risk assets in the sense that the value of a generic claim traded with a counterparty subject to default risk is always smaller than the value of the same claim traded with a counterparty having a null default probability. We discuss a case study that shows how CVA can be calculated for a portfolio of interest rates swaps. It is beyond the scope of this book to show how counterparty risk changes the pricing of derivatives for every asset class but we provide references at the end of the chapter that guide the interested reader to such applications.  

The increasing attention that is being paid to counterparty risk led to an expansion in the role and workload of so-called CVA desks in banks, a functional unit that did not exist in many banks a few years ago. Banks also make adjustments arising from the bank's own default risk in the form of debit valuation adjustments (DVAs). Finally funding costs affect the valuation of derivatives and this is reflected in so-called funding valuation adjustments (FVAs). Therefore, the price of a derivative that incorporates counterparty risk can be decomposed in the default-free price plus an adjustment related. to CVA, DVA, and FVA. The modeling choices related to CVA, DVA, and FVA are extensive and they imply that there is a wide dispersion in their application between banks. In previous chapters, we applied the overarching finance principle that the price of an asset should depend on the risk of the asset and be discounted by a discount rate that reflects this risk. However, in practice different borrowers have different funding costs and market practice is moving towards using different discount rates that reflect differences in funding costs which represents a breach of the fundamental principle. As a result of counterparty risk adjustments there is no such thing as a fair value for a derivatives transaction since the value will depend on the counterparty. Moreover, counterparty risk introduces a new source of model risk. We had seen the prevalence of Black-Scholes-Merton option. pricing model approaches, the Merton structural model of default, and the standard Gaussian copula. market model. Our discussion will show that it is even conceptually not clear whether such a standard model can be found to reflect counterparty risk valuation in practice..  

Second, counterparty risk affects capital requirements. In Basel II, there was a credit VaR charge related to counterparty risk. The most recent Basel III proposals require that capital requirements reflect risk that arises from mark-to-market losses related to CVA. However, these proposals do not allow for DVA which leads to a divergence between the treatment of counterparty risk from a capital charge regulation perspective and a derivatives pricing perspective.  

Third, accounting standards (including IFRS and US GAAP) require credit risk to be reflected in the fair value measurement of derivatives. This has had multibillion dollar profit and loss implications for banks as they report the effects of DVA and CVA in their financial accounts.  

Finally in this chapter, we will find that this discussion is everything but theoretical. These issues have transformed market practice, led to gains and losses for banks of the order of magnitude of several billion dollars over the last years and also created new professional opportunities and functions in the financial sector such as CVA desks.  

The issue of counterparty risk also affects the choice of the discount rate that is used to discount. cash flows under the risk-neutral measure. Typically LIBOR was used as a proxy for the riskless rate but after the GFC market practice has moved to the usage of OIS rates as a discount rate in collateralized transactions. This is partly due to the fact that LIBOR rates were significantly higher than OIS rates as a result of the counterparty risk that was priced into LIBOR rates. The move to OIS rates has. three fundamental implications for derivatives pricing which we discuss in this chapter..  

The topic of counterparty risk in financial engineering is a vast area and this chapter can only. provide a brief summary. However, our focus is, as throughout the book, on showing how our existing financial engineering toolkit can be used to address these challenges and what the most important valuation and risk management issues are..  
