---
tags:
  - dynamic_replication
  - hedging
  - option_replication
  - principal_preservation
  - synthetic_options
aliases:
  - Dynamic Hedging
  - Example
key_concepts:
  - Discrete time hedging
  - Dynamic replication
  - Principal preservation
  - Replicating portfolio
  - Synthetic bond options
---

# 8.2 AN EXAMPLE  

Dynamic replication is traditionally discussed within a theoretical framework. It works "exactly" only in continuous time, where continuous, infinitesimal rebalancing of the replicating portfolio is possible. This exactness in replication may quickly disappear with transaction costs, jumps in asset prices, and other complications. In discrete time, dynamic replication can be regarded as an approximation. Yet, even when it does not lead to the exact replication of assets, dynamic replication is an essential tool for the financial engineer..  

In spite of the many practical problems, discrete time dynamic hedging forms the basis of pric-. ing and hedging of many important instruments in practice. The following reading shows how. dynamic replication methods are spreading to areas quite far from their original use in financial engineering-namely, for pricing and hedging plain vanilla options..  

# EXAMPLE  

A San Francisco-based institutional asset manager is selling an investment strategy that uses synthetic bond   
options to supply a guaranteed minimum return to investors.... Though not a new concept--option replication has been around since the late 1980s... the bond option   
replication portfolio... replicates call options in that it allows investors to participate in unlimited upside   
while not participating in the downside.. The replicating portfolio mimics the price behaviour of the option every day until expiration. Each day   
the model provides a hedge ratio or delta, which shows how much the option price will change as the   
underlying asset changes. "They are definitely taking a dealer's approach, rather than an asset manager's approach in that they   
are not buying options from the Street; they are creating them themselves," [a dealer] said.  

(Thomson Reuters IFR, February 28, 1998)  

This reading illustrates one use of dynamic replication methods. It shows that market participants may replicate nonlinear assets in a cheaper way than buying the same security from the dealers. In the example, dynamic replication is combined with principal preservation to obtain a product that investors may find more attractive. Hence, dynamic replication is used to create synthetic options that are more expensive in the marketplace.  
