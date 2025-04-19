---
tags:
  - black_scholes_model
  - futures_contracts
  - option_books
  - option_greeks
  - volatility
aliases:
  - Futures Options
  - Market Complications
  - Option Hedging
  - Real World
key_concepts:
  - Black-Scholes shortcomings
  - Futures as underlying
  - Option book management
  - Stochastic interest rates
  - Volatility smile effects
---

# 9.7 REAL-LIFE COMPLICATIONS  

In actual markets, the issues discussed here should be applied with care, because there will be significant deviations from the theoretical Black-Scholes world. By convention, traders consider the Black-Scholes world as the benchmark to use, although its shortcomings are well known.  

Every assumption in the Black-Scholes world can be violated. Sometimes these deviations are. harmless or can easily be accommodated by modifying the formula. Some such modifications of the formula would be minor, and others more significant, but in the end they take care of the prob-. lem at a reasonable effort.  

Yet, there are two cases that require substantial modifications. The first concerns the behaviot of volatility. In financial markets, not only is volatility not constant, but it also has some.  

unexpected characteristics. One of these anomalies is the smile effects.25 Volatility has, also, a term structure.  

The second case is when interest rates are stochastic, and the underlying asset is an interest rate-related instrument. Here, the deviation from the Black-Scholes world, again, leads to significant changes.  

# 9.7.1 DEALING WITH OPTION BOOKS  

This chapter discussed gamma, delta, and vega risks for single option positions. Yet, market makers. do not deal with single options. They have option books and they try to manage the delta, gamma, and vega risks of portfolios of options. This complicates the hedging and risk management significantly. The existence of exotic options compounds these difficulties..  

First of all, option books consist of options on different, possibly correlated, assets. Second, implied volatility may be different across strikes and expiration dates, and a straightforward application of delta, gamma, and vega concepts to the portfolio may become impossible. Third, while for single options delta, vega, and gamma have known shapes and dynamics, for portfolios of options, the shapes of delta, gamma, and vega are more complex and their movement over time may be more difficult to track.  

# 9.7.2 FUTURES AS UNDERLYING  

This chapter has discussed options written on cash instruments. How would we analyze options that are written on a futures or forward contract? There are two steps in designing option contracts. First, a futures or a forward contract is introduced on the cash instrument, and second, an option is written on the futures. The holder of the option has the right to buy one or more futures contracts.  

Why would anyone write an option on futures (forwards), instead of writing it on the cast instrument directly?  

In fact, the advantages of such contracts are many, and the fact that option contracts written on futures and forwards are the most liquid is not a coincidence. First of all, if one were to buy and sell the underlying in order to hedge the option positions, the futures contracts are more convenient. They are more liquid, and they do not require upfront cash payments. Second, hedging with cash instruments could imply, for example, selling or buying thousands of barrels of oil. Where would a trader put so much oil, and where would he get it? Worse, dynamic hedging requires adjusting such positions continuously. It would be very inconvenient to buy and sell a cash underlying. Long and short positions in futures do not result in delivery until the expiration date. Hence, the trader can constantly adjust his or her position without having to store barrels of oil at each rebalancing of the hedge. Futures are also more liquid and the associated transactions costs and counterparty risks are much smaller.  

Thus, the choice of futures and forwards as the underlying instead of cash instruments is, in fact, clever contract design. But we must remember that futures come with daily marking to market. Forward contracts, on the other hand, may not require any marking to market until the expiration date.  

# 9.7.2.1 Delivery mismatch  

Note the possibility of a mismatch. The option may result in the delivery of a futures contract at time $T.$ but the futures contract may not expire at that same time. Instead, it may expire at a time $T+\Delta$ and may result in the delivery of the cash commodity. Such timing mismatches introduce new risks.  
