---
tags:
  - cash_flow_engineering
  - finance_textbook
  - hedge_funds
  - investment_banking
  - market_participants
  - market_segments
  - relative_value
  - security_valuation
aliases:
  - Book Preview
  - Cash Flow
  - Finance Book Overview
  - Relative Value
key_concepts:
  - asset-liability management
  - cash flow diversion
  - demand side participants
  - internal workings of markets
  - market segments
  - relative value trades
  - security valuation
  - spot, forward, option contracts
  - structured products
---

# 1.8  PREVIEW OF THE BOOK  

Many finance textbooks are organized by market segments: stocks, money markets, bonds, real estate, currencies, commodities, etc. This is analogous to reviewing the car industry alphabetically by make, starting with Audi and BMW, and ending with Volkswagen and Volvo.  

This book is arranged structurally. First, we learn the common features of all the segments:. spot, forward, and option contracts, analogous to describing the car engines, body, safety. features, and interior comforts. Second, we review some highly structured products (floating. notes, mortgage securities, and CDOs) similar to showcasing finished cars (small Fiat 500, mid-size Honda Accord, and larger Porsche Cayenne). Last, we cover the participants in the markets and the problems they are trying to solve. This allows the reader to fully understand the internal workings of the markets, rather than learn about unimportant institutional details. The book is thus divided into three parts..  

Part I: Relative Value Building Blocks - Chapters 2-7 cover spot, forward/futures, options, swaps, and credit derivatives; they review the mechanics of the transactions and the arbitrage linkages within and across markets, as well as pricing methods.   
Part II: Cash Flow Engineering - This part is definitely not exhaustive; we devote just three chapters (Chapters 8-10) to highlight those markets that exhibit very complex cash flow diversion rules; one can legitimately claim that in many cases they are over-engineered: structured floaters with inverse, cap, and call features, mortgage-backed securities subject to sequential tranching and planned amortization schemes, and cash and synthetic CDOs with default risk tranching;   
Part III: Players - In Chapters 11-14, we focus on the main participant groups on the demand side: individuals planning for retirement or investing actively by valuing securities; hedge funds striving to identify relative value arbitrage alpha; banks trying to solve the. perennial duration gap problem of their long assets and short liabilities; and the private markets players - pension funds, private equity, and venture capital. We omit the capital. deficit agents/suppliers of securities: corporations and governments and we also omit mildly. asset transforming mutual funds that engineer basket vehicles for individuals. We split the. ETFs between Chapters 8, 11, and 12 - their structuring and their replication role for individuals and hedge funds.  

The objective is to keep things simple. In Parts I and II we use cash flow diagrams and tables in place of equations, and we digest the complicated theory of risk-return management for the players in Part III down to concrete real-life numeric and accounting examples.  

Parts I, II, and III may appeal to different audiences. Part I is a must read for those wanting to work in trading, structuring and hedge funds. It provides the fundamentals of building relative value trades and pricing. Part III is a must read for investment and derivative marketing, investment banking candidates and general economics candidates. It provides the basics of security valuation, asset-liability management and private equity processes. Part II should be of interest to both groups. While not titled "Financial Markets for Dummies," the entire book should be readable by all college graduates interested in finance, including accountants, doctors and engineers. I don't know about politicians. . .  

# Part I Relative Value Building Blocks  

The art of present valuing, otherwise known as Bond Math, is the basis of all security valuation, and the majority of this chapter will be devoted to Bond Math. We abstract from the reality of the many types of borrowers in the world such as sovereign governments, corporations, and municipalities, each of which is subject to different regulations and taxes, and each has its own credit worthiness - all of which affect yield levels in each market. We assume that we are within one of these markets with one issuer and a set of bonds issued by that issuer. We introduce the most basic bond structures - zero-coupon, coupon, amortizing, and floating rate -- which are going to serve as building blocks for all other concepts. We go through simple annual calculations, then introduce real-life complications: compounding more frequently than annually, day counting for interest calculations and accruals. We then arrive at the fundamental concept of the discount curve or the term structure of discount or zero-coupon rates. Using the arbitrage principle that the whole must equal the sum of its parts (in value) for all the bonds in any given market, we build one set of discount rates or factors that allow us to value any new bond in that market. The value of a bond with arbitrary cash flows is equal to the sum of all its cash flows multiplied by the correct spot discount factors. This is not because our math says so, but because the greed of financial traders will not allow the same item, repackaged under a disguised name, to trade at a different value. Any bond can be shown to be a package of positions in bonds already existing in the market, and the bond's value can be computed from the sum of these positions. In general, some of these positions can be long (bought) and some short. At the end of the chapter, when we cover equity, commodity, and currency markets, we highlight the important concept of shorting securities. With that, our overview of the spot transactions as the most basic building blocks in financial engineering is complete.  
