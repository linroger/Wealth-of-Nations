---
tags:
  - '#arbitrage_free_conditions'
  - '#binomial_tree_structure'
  - '#bond_pricing'
  - '#dynamic_replication_strategy'
  - '#martingale_dynamics'
  - '#one_factor_model'
  - '#risk_free_rate'
---
# 8.6 SOME IMPORTANT CONDITIONS  

In order for these methods to work, some important assumptions are needed. These are discussed in detail here.  

# 8.6.1 ARBITRAGE-FREE INITIAL CONDITIONS  

The methods discussed in this chapter will work only if we start from dynamics that originally exclude any arbitrage opportunities. Otherwise, the procedures shown will give "wrong" results. For example, some bond prices $B(j,T_{2})^{i},j=0$ , 1 or the option price may turn out to be negative.  

There are many ways the arbitrage-free nature of the original dynamics can be discussed. One. obvious condition concerns the returns associated with the savings account and the other constituent. asset. It is clear that, at all nodes of the binomial trees in Figure 8.7, the following condition needs to be satisfied:  

$$
R_{j}^{\mathrm{down}}<L_{j}<R_{j}^{\mathrm{up}}
$$  

where $L_{j}$ is the one-period spot rate that is observed at that node and the. $R_{j}^{\mathrm{{down}}}$ and $R_{j}^{\mathrm{up}}$ are two possible returns associated with the bond at the same node.  

According to this condition, the risk-free rate should be between the two possible returns that one can obtain from holding the "risky"' asset, $B(t,T)$ . For the case of bonds, before expiration we must also have, due to arbitrage,  

$$
R_{j}^{\mathrm{down}}=L_{j}=R_{j}^{\mathrm{up}}
$$  

Otherwise, we could buy or sell the bond, and use the proceeds in the risk-free investment to make unlimited gains.  

Yet, the arbitrage-free characteristic of binomial trees normally requires more than this simple condition. As Chapter 11 will show, the underlying dynamics should be conformable with proper. Martingale dynamics in order to make the trees arbitrage-free..  

# 8.6.2 ROLE OF BINOMIAL STRUCTURE  

There is also a very strong assumption behind the binomial tree structure that was used during the discussion. This assumption does not change the logic of the dynamic replication strategy, but can make it numerically more complicated if it is not satisfied.  

Consider Figure 8.7. In these trees, it was assumed that when the short rate dropped, the long rate always dropped along with it. Conversely, when the short rate increased, the long rate increased with it. That is to say, the long bond return and the short rate were perfectly correlated. It is thanks to this assumption that we were able to associate a future value of $B_{t}$ with another future value of $B(t,T_{3})$ . These "associations"' were never random. A similar assumption was made concerning the binomial trees for $S_{t}$ and $C_{t}$ The movements of these two assets were perfectly correlated.  

This is a rather strong assumption and is due to the fact that we are using the so-called onefactor model. It is assumed that there is a single random variable that determines the future value of the assets under consideration at every node. In reality, given a possible movement in the short rate $L_{t}$ , we may not know whether a bond price $B(t,T)$ will go up or down in the immediate future, since other random factors may be at play. Under such conditions, it would be impossible to obtain. the same equations, since the up or down values of the two assets would not be associated with certainty.  

Yet, introducing further random factors will only increase the numerical complexity of the tree models. We can, for example, move from binomial to trinomial or more complicated trees. The general logic of the dynamic replication does not change. However, we may need further base assets to form a proper synthetic.  
