---
tags:
  - '#dynamic_replication'
  - '#market_liquidity'
  - '#nonlinear_assets'
  - '#optionality'
  - '#rebalancing'
  - '#replicating_portfolio'
  - '#static_replication'
  - '#synthetic_instruments'
---
# 8.1 INTRODUCTION  

The previous chapters have dealt with static replication of cash flows. The synthetic constructions we discussed were static in the sense that the replicating portfolio did not need any adjustments until the target instrument matured or expired. As time passed, the fair value of the synthetic and the value of the target instrument moved in an identical fashion.  

However, static replication is not always possible in financial engineering, and replicating portfolios may need constant adjustment (rebalancing) to maintain their equivalence with the targeted instrument. This is the case for many different reasons. First of all, the implementation of static replication methods depends on the existence of other assets that permit the use of what we called contractual equations. To replicate the targeted security, we need a minimum number of "righthand side" instruments in the contractual equation. If markets in the component instruments do not exist, contractual equations cannot be used directly and the synthetics cannot be created this way.  

Second, the instruments themselves may exist, but they may not be liquid. If the components of a theoretical synthetic do not trade actively, the synthetic may not really replicate the original asset satisfactorily, even though sensitivity factors with respect to the underlying risk factors are the same. For example, if constituent assets are illiquid, the price of the original asset cannot be obtained by "adding" the prices of the instruments that constitute the synthetic. These prices cannot be readily obtained from markets. Replication and marking-to-market can only be done using assets that are liquid and "similar' but not identical to the components of the synthetic. Such replicating portfolios may need periodic adjustments.  

Third, the asset to be replicated can be highly nonlinear. Using linear instruments to replicate nonlinear assets will involve various approximations. At a minimum, the replicating portfolios need to be rebalanced periodically. This would be the case with assets containing optionality. As the next two chapters will show, options are convex instruments, and their replication requires dynamic hedging and constant rebalancing.  

Finally, the parameters that play a role in the valuation of an asset may change, and this may require rebalancing of the replicating portfolio..  

In this chapter, we will see that creating synthetics by dynamic replication methods follows. the same general principles as those used in static replication, except for the need to rebalance periodically. In this sense, dynamic replication may be regarded as merely a generalization of the. static replication methods discussed earlier. In fact, we could have started the book with principles of dynamic replication and then shown that, under some special conditions, we would end. up with static replication. Yet, most "bread-and-butter" market techniques are based on the static. replication of basic instruments. Static replication is easier to understand, since it is less complex. Hence, we dealt with static replication methods first. This chapter extends them now to dynamic replication.  
