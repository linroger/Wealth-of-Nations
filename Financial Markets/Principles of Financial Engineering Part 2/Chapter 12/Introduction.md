---
tags:
  - asset_pricing
  - financial_engineering
  - martingale_approach
  - risk_neutral_pricing
  - risk_premia
aliases:
  - Introduction to Asset Pricing
  - Pricing Methodology
key_concepts:
  - asset pricing models
  - risk premia
  - risk-neutral environment
  - subjective preferences
  - volatility of cash flows
---

# 12.1 INTRODUCTION  

We have thus far proceeded without a discussion of asset pricing models and the tools associated. with them, as financial engineering has many important dimensions besides pricing. In this chapter,. we will discuss models of asset pricing, albeit in a very simple context. A summary chapter on pricing tools would unify some of the previous topics and show the subtle connections between them. The discussion will approach the issue using a framework that is a natural extension of the. financial engineering logic utilized thus far.  

Pricing comes with at least two problems that seem, at first, difficult to surmount in any satisfactory way. Investors like return, but dislike risk. This means that assets associated with nondiversifiable risks will carry risk premia. But, how can we measure such risk premia objectively when buying assets is essentially a matter of subjective preferences? Modeling risk premia using utility functions may be feasible theoretically, but this is not attractive from a trader's point of view if hundreds of millions of dollars are involved in the process. The potential relationship between risk premia and utility functions of players in the markets is the first unpleasant aspect of practical pricing decisions.  

The second problem follows from the first. One way or another, the pricing approach needs to be based on measuring the volatility of future cash flows. But volatility is associated with randomness and with some probability distribution. How can an asset pricing approach that intends to be applicable in practice obtain a reasonable set of real-world probabilities?'  

Modern finance has found an ingenious and practical way of dealing with both these questions. simultaneously. Instead of using a framework where risk premia are modeled explicitly, the profes-. sion transforms a problem with risk premia into one where there are no risk premia. Interestingly, this transformation is done in a way that the relevant probability distribution ceases to be the realworld probability and, instead, becomes a market-determined probability that can be numerically. calculated at any point in time if there is a reasonable number of liquid instruments.? With this approach, the assets will be priced in an artificial risk-neutral environment where the risk premia are indirectly taken into account. This methodology is labeled the Martingale approach. It is a. powerful tool in practical asset pricing and risk management..  

A newcomer to financial engineering may find it hard to believe that a more or less unified theory for pricing financial assets that can be successfully applied in real-world pricing actually. exists. After all, there are many different types of assets, and not all of them seem amenable to the same pricing methodology, even at a theoretical level. A market practitioner may already have heard of risk-neutral pricing, but just like the newcomer to financial engineering, he or she may regard the. basic theory behind it as very abstract. And yet, the theory is surprisingly potent. This chapter provides a discussion of this methodology from the point of view of a financial engineer. Hence, even. though the topic is asset pricing, the way we approach it is based on ideas developed in previous. chapters. Basically, this pricing methodology is presented as a general approach to synthetic asset creation.  

Of course, like any other theory, this methodology depends on some strict assumptions. The methods used in this text will uniformly make one common assumption that needs to be pointed out at the start. Only those models that assume complete markets are discussed. In heuristic terms, when markets are "complete,' there are "enough" liquid instruments for obtaining the working probability distribution.  

This chapter progressively introduces a number of important theoretical results that are used in pricing, hedging, and risk-management application. The main result is called the fundamental theorem of asset pricing. Instead of a mathematical proof, we use a financial engineering argument to justify it, and a number of important consequences will emerge. Throughout the chapter, we will single out the results that have practical implications.  
