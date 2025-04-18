---
tags:
  - credit_event
  - credit_indices
  - credit_sector
  - e_trading
  - protection_buyer
  - recovery_value
aliases:
  - Credit Derivatives
  - Definitions
  - Terminology
key_concepts:
  - 'Credit event: specific events'
  - 'Credit indices: arithmetic average'
  - 'E-trading: electronic platform'
  - 'Protection buyer: buys instrument'
  - 'Recovery value: asset default payoff'
  - 'Reference asset: instrument traded'
  - 'Reference name: issuer'
  - 'Tranches: sell default risks'
---

# 18.2 TERMINOLOGY AND DEFINITIONS  

First, we need to define some terminology. The credit sector is relatively new in modern finance, although an ad hoc treatment of it has existed as long as banking itself.? Some of the terms used in this sector come from swap markets, but others are new and specific to the credit sector. The following list is selective.  

1. Reference name. The issuer of a debt instrument on which one is buying or selling default insurance.   
2. Reference asset. The instrument on which credit risk is traded. Note that the credit sector adopts a somewhat more liberal definition of the basis risk. A trader may be dealing in loans but may hedge the credit risk using a bond issued by the same credit.   
3. Credit event. Credit risk is directly or indirectly associated with some specific events (e.g., defaults or downgrades). These are important, discrete events, compared to market risk where events are relatively small and continuous.? The underlying credit event needs to be defined carefully in credit derivative contracts. The industry differentiates between hard credit events. such as bankruptcy versus soft credit events such as restructuring.4 We discuss this issue later in. this chapter.   
4. Protection buyer, protection seller. Protection buyer is the entity that buys a credit instrument such as a CDS. This entity will make periodic payments in return for compensation in the event of default. A protection seller is the entity that sells the CDS.   
5. Recovery value. If default occurs, the payoff of the credit instrument will depend on the recovery value of the underlying asset at the moment of default. This value is rarely zero; some positive amount will be recoverable. Hence, the buyer needs to buy protection over and above the recoverable amount. Major rating agencies such as Moody's or Standard and Poor's have recovery rate tables for various credits which are prepared using past default data. As a result of the 2009 CDS standardization, the recovery rate is now fixed by convention at $40\%$ . Thisd removed some earlier ambiguity related to the calculation of default probabilities and CDS mark-to-market from the quoted spread.   
6. Credit indices. This is the most liquid part of the credit sector. A credit index is put together by first selecting a pool of reference names and then taking the arithmetic average of the CDS rates for the names included in the portfolio. There are economy-wide credit indices with investment grade and speculative grade ratings, as well as indices for particular sectors. iTraxx for Europe and Asia and CDX for the United States and Emerging Markets are the most liquid credit indices.   
7. Tranches. Given a portfolio of reference names, it is not known at the outset which name will default, or for that matter whether there will be defaults at all. Under these conditions the structure may decide to sell, for example, the risks associated with the first $0-3\%$ of the defaults. In a pool of 100 names, the risk of the first three defaults would then be transferred to another investor. The investor would receive periodic payments for bearing this risk. Similarly, the structurer may sell the risk associated with. $3-6\%$ of the defaults, etc. We discuss credit. indices and tranches in detail in Chapter 21..   
8. E-trading. Credit indices are typically traded OTC and, as a result of post-GFC regulation, centrally cleared. Most trading is electronic and certain US trades are required to be executed through an electronic platform called Swaps Execution Facility since October 2013. Exchangetraded futures on credit indices have been launched.   
9. Standardization. In April 2009, ISDA implemented the standardization of CDS contracts. This event is also referred to as the CDS "Big Bang." The objective of this initiative was to facilitate CDS settlement by reducing uncertainty and making credit event management more operationally efficient. The standardization had three main parts: auction hardwiring, standardizing trading conventions, and central clearing. We will discuss these in detail in Section 18.4.  

The credit sector has many other sector-specific terms that we will introduce during our discussion.  

# 18.2.1 TYPES OF CREDIT DERIVATIVES  

Crude forms of credit derivatives have existed since the beginning of banking. These were not liquid, did not trade, and, in general, did not possess the desirable properties of modern financial instruments, like swaps, that facilitate their use in financial engineering. Banking services such as a letter of credit, banker's acceptances, and guarantees are precursors of modern credit instruments and can be found in the balance sheet of every bank around the world.  

Broadly speaking, there are three major categories of credit derivatives.  

1. Credit event-related products make payments depending on the occurrence of a mutually. agreeable event. The CDS is the major building block here..   
2. Credit index products that are used in trading portfolios of credit. Obviously, such indices. would come with their own derivatives such as options, futures, and forwards. An example would be an option written on the iTraxx Europe index..   
3. The structured credit products and the index tranches.  

The difference between the value of risky and riskless debt is typically expressed in terms of a credit spread. The spread is the difference between the (promised) yield on the risky bond and the yield on riskless bonds. Credit risk can be broadly grouped into two different categories: on one hand, credit deterioration. Widening of the underlying credit spread can indicate how credit deteriorates. On the other hand, default risk. This is a separate risk from credit deterioration, although it is certainly correlated with it. Default products trade default risk by separating it from credit deterioration risk.  

As mentioned above, banks have issued letters of credit, guarantees, and insurance. The major distinguishing characteristic of these traditional instruments is that they transfer default risk only. They do not, in particular, transfer market risk or the risk of credit deterioration. Essentially, a payment is made when default occurs. With these products, no compensation changes hands when the underlying credit deteriorates. New credit default products share some of the properties of these old instruments. Some of the new features of credit contracts are as follows:  

1. The payout is dependent on an event rather than an underlying price, similar to insurance. products and unlike other derivatives. The dependence of a payoff on an event leads to new techniques and instruments.   
2. The existence of an event leads to the issue of recovery value. How to determine (model) the value of an asset in case of default is now easy. Throughout this chapter, we will use the assumption that the recovery rate is constant and known at a level $R$   
3. The process of settling credit contracts is more complex than in other markets. In the case of. physical delivery of the underlying, this does not present a major problem. The protection selle. will be the legal owner of the defaulted instrument and may take necessary legal steps for recovery. But if the contract is cash-settled, then neither party has legal recourse to the borrower unless the party owns the underlying credit directly. For this reason, the industry prefers physical delivery, and a large majority of default swaps settle this way.  

We will address the additional characteristics of default products when we study CDSs in more. detail. In the following section, we will look at the most liquid credit derivatives in more detail and study the financial engineering of CDSs.  
