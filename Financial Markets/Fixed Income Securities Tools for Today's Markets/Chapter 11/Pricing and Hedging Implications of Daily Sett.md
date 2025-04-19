---
tags:
  - bond_pricing
  - daily_settlement
  - forward_contract
  - futures_contract
  - hedge_ratio
aliases:
  - Daily Settlement
  - Futures vs. Forwards
key_concepts:
  - Bond Price and Interest
  - Daily P&L Realization
  - Futures vs. Forwards Pricing
  - Hedging with Futures
  - Tailing the Hedge
---

# 11.5 PRICING AND HEDGING IMPLICATIONS OF DAILY SETTLEMENT  

Daily settlement has implications for the pricing of futures relative to forwards and for hedging using futures rather than forwards. This section considers these two issues in turn..  

Consider a forward contract and a futures contract on the same, sin-. gle underlying bond, and assume for the moment that the initial forward and futures prices are the same. From the discussion in the previous section,. changes in the prices of the forward contract are realized as profit and loss. $(\mathrm{P}\&\mathrm{L})$ cumulatively, as of expiration, while changes in the prices of the. futures contract are realized as P&L daily. Which pattern of P&L realization is preferable to the buyer of a contract?.  

Because bond prices increase when interest rates fall, and vice versa, the buyer of a futures contract realizes profit early when rates fall, that is, when reinvestment opportunities are relatively poor. Similarly, the buyer realizes losses early when rates rise, that is, when the costs of financing those losses. are relatively high. In other words, whether rates fall or rise, the early realization of $\mathrm{P}\&\mathrm{L}$ from a long bond futures position is undesirable. Hence, buyers. are willing to pay less to purchase bonds through futures than through forwards, and, therefore, the futures price of a bond is less than its forward price. Appendix A11.3 formally proves this result..  

In practice, the difference between futures and forward bond prices tends to be small. As evident from the previous paragraph and the appendix to this chapter, the magnitude of the difference depends on the covariance of the underlying bond price with the reinvestment or financing rate to contract expiration.4 But for note and bond futures, this covariance tends to be low: the time to contract expiration is typically short relative to the maturity of the underlying bonds; short-term rates have relatively low volatility; and short-term rates are imperfectly correlated with long-term rates.  

While the futures-forward price difference tends to be small, traders nor-. mally do account for the difference in the timing of P&L cash flows when. calculating hedge ratios. This is called tailing the hedge and is particularly. common and useful for basis trades, which, as discussed presently, are trades of futures against synthetic bond forwards..  

Consider a forward and futures contract on the same underlying security for delivery in $d$ days, when the term repo rate is. $r$ . Assume for simplic ity that, over a given day, the forward and futures prices increase by the same amount, $\Delta$ . The futures contract, then, through daily settlement, pays. $\Delta$ immediately to the long. The value to the long of the forward contract, by contrast, increases by $\Delta$ as of the delivery date, or, in present value terms, by. $\Delta/(1+r d/360)$ . Hence, for positive $r$ , less than one futures contract hedges. the change in value of one forward contract. More specifically, to hedge. $N^{\bar{f}w d}$ forward contracts with $N^{f u t}$ futures contracts,e  

$$
N^{f u t}=\frac{N^{f w d}}{1+\frac{r d}{360}}
$$  

where the difference between. $N^{f w d}$ and $N^{f u t}$ is known as the tail of the hedge.  

This section closes with a comment on terminology. The terms "mark-to-market," "variation margin," and "daily settlement" are often used interchangeably, although, strictly speaking, they have distinct and different meanings. Mark-to-market is the process of adjusting security prices. in an accounting framework to match market values. For example, securities in the trading book of a bank have to be marked-to-market when reported on its balance sheet, while securities designated as "held-to-maturity" can be reported at cost. The term mark-to-market, therefore, does not imply any exchange of cash. Variation margin refers to cash or securities that have to be posted as collateral to secure obligations under a contract. For example, as discussed in Chapter 10, borrowers of cash in the repo market have to make variation margin payments in the form of additional cash or securities as the value of their existing collateral declines. Counterparties posting collateral maintain ownership of that collateral, which means that i) interest is earned on the collateral either by being paid interest on cash collateral or by keeping interest earned on securities posted as collateral, and ii) collateral is returned when the associated contractual obligations have been fulfilled. Daily settlement, as described in this section, refers to the payment of gains or losses. These payments are irrevocable; that is, they do not earn interest and are never returned.5  
