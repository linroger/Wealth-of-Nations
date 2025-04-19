---
tags:
  - '#capital_structure_arbitrage'
  - '#convertible_bonds'
  - '#credit_risk'
  - '#equity_analysis'
  - '#financial_engineering'
  - '#fixed_income_instruments'
  - '#merton_model'
  - '#option_pricing'
  - '#structural_models_of_default'
---
# 19.1 INTRODUCTION  

Fixed-income instruments involve payoffs that are, in general, known and "fixed." They also have set maturity dates. Putting aside the credit quality of the instrument, fixed-income assets have relatively simple cash flows that depend on a known, small set of variables and, hence, risk factors. There are also well-established and quite accurate ways to calculate the relevant term structure. Finally, there are several liquid and efficient fixed-income derivatives markets such as swaps, forward rate agreements (FRAs), and futures, which simplify the replication and pricing problems existing in this sector.  

There is no such luxury in equity analysis. The underlying asset, which is often a stock or a stock index, does not have a set maturity date. It depends on a nontransparent, idiosyncratic set of risks, and the resulting cash flows are complex. The timing and the size of future cash flows may not be known. There are also complex issues of growth, investment, and management decisions that further complicate the replication and pricing of equity instruments. Finally, relatively few related derivatives markets are liquid and usable for a replication exercise.  

Yet, the general principles of option pricing and replication can be applied to value equity. In. this chapter, we extend the methods introduced earlier to equity and equity-linked products. We also discuss the engineering applications of some products that are representative of this sector..  

First, we show how the equity of a company can be viewed and priced as an option on the assets of the firm with a strike price equal to the present value of the debt. This approach is based on the so-called Merton (1974) structural model of default. It is an elegant and useful application of financial engineering principles and importantly it allows us to link the pricing of credit and equity instruments. Similar to the Black-Scholes model that we have used in earlier chapters to either price an option based on a given set of input parameters or to back out an implied volatility based on observed market price of the option, the Merton (1974) model can be applied in three main different ways. First, given information about a firm's assets, its capital structure and debt value we can determine the model implied price of the equity. Second, in the equity-to-credit approach we can plug observed market prices of equity into the model to back out the implied credit spread and probability of default for the debt. The third application uses observed market prices for the equity and observed credit spreads (from bond or CDS markets) to back out an implied volatility for the equity.  

These wide-ranging uses have important practical uses. The following example highlights the practical relevance of structural models of default in today's markets.  

# EXAMPLE  

$I...J$ leading investors say Merton models are now so frequently used that they are actually driving the.   
credit market. Take Barclays Global Investors (BGI) in San Francisco, with. $\$780$ billion under management.   
BGI has been using Merton models  an in-house model as well as those available on the market - for a number of years, but its head of US fixed income, Peter Wilson, says the model is now becoming so.   
prevalent with other investors that it is starting to dictate which way credit markets will move..  

(Source: Risk Magazine, November 1, 2003, Barra joins crowded market for Merton models', www.risk.net/1497515/)  

As markets for credit derivatives developed and market prices for credit spreads became more widely available the Merton model became more widely used in the financial sector and many banks integrated their equity and fixed-income divisions to a greater extent and located them on the same trading floor. Previously equity and fixed-income divisions were often found on different trading floors. The underlying intellectual foundation for this reorganization lies in structural models of default. Furthermore, these models can be used for so-called capital structure arbitrage strategies. Such strategies use the Merton model to identify mispricing between credit and equity markets and take positions in equity, bond, or CDS markets to exploit it..  

Given the complexity of equity markets and their risks, as we will see, there are however alsc limitations associated with the basic Merton model and its applications..  

In the previous chapter, we had discussed credit risk, the probability of default of a risky bond, and credit default swaps. We had seen that credit spreads and therefore an implied probability of default can be backed out from both corporate bond spreads as well as CDS spreads. The Merton model provides us with a third source of information for the probability of default, since the model can be used to calculate it if the market value of equity and other parameters about the capital structure are observed.  

The simple Merton model has been extended significantly over the last 40 years and industry versions such as the KMV or the CreditGrades model are widely used. We discuss how hedge funds pursue so-called capital structure arbitrage strategies that are based on structural models of default.  

The second purpose of this chapter is to discuss the engineering of some popular equity instruments such as convertible bonds and hybrid equity products..  

The plan of this section is as follows. First, we discuss how financial engineering and option pricing principles can be applied to value a company's equity. We discuss applications and limitations of the model. Second, we consider convertible bonds and their relative, warrant-linked bonds. Convertible bonds are another example of bonds with embedded options. In Chapter 17, we saw the first example of a bond with an embedded option in the form of callable bonds. In the next chapter, we will discuss structured products including equity structured products and so-called reverse convertibles.  

We begin by applying option replication and financial engineering principles to a company's equity.  
