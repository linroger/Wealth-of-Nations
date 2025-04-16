---
tags:
  - '#bid_ask_spreads'
  - '#dynamic_replication'
  - '#liquidity_risk'
  - '#model_risk'
  - '#operational_costs'
  - '#static_replication'
  - '#transaction_costs'
  - '#volatility_changes'
---
# 8.7 REAL-LIFE COMPLICATIONS  

Real-life complications make dynamic replication a much more fragile exercise than static replication. The problems that are encountered in static replication are well known. There are operational problems, counterparty risk, and the theoretically exact synthetics may not be identical to the original asset. There are also liquidity problems and other transaction costs. But, all these are relatively minor and in the end, static replicating portfolios used in practice generally provide good synthetics.  

With dynamic replication, these problems are magnified because the underlying positions need to be readjusted many times. For example, the effect of transaction costs is much more serious if dynamic adjustments are required frequently. Similarly, the implications of liquidity problems will also be more serious. But more important, the real-life use of dynamic replication methods brings forth new problems that would not exist with static synthetics. We study these briefly.  

# 8.7.1 BID-ASK SPREADS AND LIQUIDITY  

Consider the simple case of bid-ask spreads. In static replication, the portfolio that constitutes the synthetic is put together at time. $t$ and is never altered until expiration. $T.$ In such an environment, the existence of bid--ask spreads may be non-negligible, but this is hardly a major aspect of the problem. After all, any bidask spread will end up increasing (or lowering) the cost of the associated synthetic, and in the unlikely case that these are prohibitive, then the synthetic will not be put together.  

Yet, with dynamic replication, the practitioner is constantly adjusting the replicating portfolio.. Such a process is much more vulnerable to widening bid--ask spreads or the underlying liquidity. changes. At the time dynamic replication is initiated, the future movements of bid-ask spreads or of liquidity will not be known exactly and cannot be factored into the initial cost of the synthetic.. Such movements will constitute additional risks and increase the costs even when the synthetic is. held until maturity.  

# 8.7.2 MODELS AND JUMPS  

Dynamic replication is never perfect in real life. It is done using models in discrete time. But models imply assumptions and discrete time means approximation. This leads to a model risk. Many factors and the possibility of having jumps in the underlying risks may have serious consequences if not taken into account properly during the dynamic replication process.  

# 8.7.3 MAINTENANCE AND OPERATIONAL COSTS  

It is easy to obtain a dynamic replication strategy theoretically. But in practice, this strategy needs to be implemented using appropriate position-keeping and risk-management tools. The necessary. software and human skills required for these tasks may lead to significant new costs..  

# 8.7.4 CHANGES IN VOLATILITY  

Often, dynamic replication is needed because the underlying instruments are nonlinear. It turns out.   
that, in dealing with nonlinear instruments, we will have additional exposures to new and less transparent risks such as movements in the volatility of the associated risk factors. Because.   
risk-managing volatility exposures are much more delicate (and difficult) than the management of.   
interest rate or exchange rate risks, dynamic replication often requires additional skills.  

In the exercises at the end of this chapter, we briefly come back to this point and provide a reading (and some questions) concerning the role of volatility changes during the dynamic hedging. process.  
