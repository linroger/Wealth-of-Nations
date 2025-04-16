---
tags:
  - '#basis_calculation'
  - '#basis_risk'
  - '#cross_hedging'
  - '#delivery_month'
  - '#example_analysis'
  - '#futures_contracts'
  - '#hedging'
  - '#spot_price'
---
# 3.3 BASIS RISK  

The hedges in the examples considered so far have been almost too good to be true. The hedger was able to identify the precise date in the future when an asset would be bought or sold. The hedger was then able to use futures contracts to remove almost all the risk arising from the price of the asset on that date. In practice, hedging is often not quite as straightforward as this. Some of the reasons are as follows:  

1. The asset whose price is to be hedged may not be exactly the same as the asset underlying the futures contract..  

2. There may be uncertainty as to the exact date when the asset will be bought or sold. 3. The hedge may require the futures contract to be closed out before its delivery month.  

These problems give rise to what is termed basis risk. This concept will now be explained.  

# The Basis  

The basis in a hedging situation is as follows:2  

Basis $=$ Spot price of asset to be hedged - Futures price of contract used  

If the asset to be hedged and the asset underlying the futures contract are the same, the basis should be zero at the expiration of the futures contract. Prior to expiration, the basis may be positive or negative.  

As time passes, the spot price and the futures price for a particular month do not. necessarily change by the same amount. As a result, the basis changes. An increase in the basis is referred to as a strengthening of the basis; a decrease in the basis is referred. to as a weakening of the basis. Figure 3.1 illustrates how a basis might change over time. in a situation where the basis is positive prior to expiration of the futures contract..  

To examine the nature of basis risk, we will use the following notation:  

$S_{1}$ Spot price at time $t_{1}$ $S_{2}$ Spot price at time $t_{2}$ $F_{1}$ .. Futures price at time $t_{1}$ $F_{2}$ Futures price at time $t_{2}$ $b_{1}$ Basis at time $t_{1}$ $b_{2}$ Basis at time $t_{2}$  

We will assume that a hedge is put in place at time $t_{1}$ and closed out at time $t_{2}$ . As an example, we will consider the case where the spot and futures prices at the time the hedge is initiated are $\$2.50$ and $\$2.20$ , respectively, and that at the time the hedge is closed out they are $\$2.00$ and $\$1.90$ , respectively. This means that $S_{1}=2.50,F_{1}=2.20$ $S_{2}=2.00$ , and $F_{2}=1.90$  

![](images/2086bec2cc543cadd9fd3f9ad139c921d19d3c35dcfb836246d70a2bee4654a0.jpg)  
Figure 3.1 Variation of basis over time.  

From the definition of the basis, we have  

$$
b_{1}=S_{1}-F_{1}\quad\mathrm{and}\quad b_{2}=S_{2}-F_{2}
$$  

so that, in our example, $b_{1}=0.30$ and $b_{2}=0.10$  

Consider first the situation of a hedger who knows that the asset will be sold at time $t_{2}$ and takes a short futures position at time $t_{1}$ . The price realized for the asset is $S_{2}$ and the profit on the futures position is $F_{1}\mathrm{~-~}F_{2}$ The effective price that is obtained for the asset with hedging is therefore  

$$
S_{2}+F_{1}-F_{2}=F_{1}+b_{2}
$$  

In our example, this is. $\$2.30$ . The value of $F_{1}$ is known at time $t_{1}$ . If $b_{2}$ were also known at this time, a perfect hedge would result. The hedging risk is the uncertainty associated with $b_{2}$ and is known as basis risk. Consider next a situation where a company knows it will buy the asset at time. $t_{2}$ and initiates a long hedge at time $t_{1}$ . The price paid for the. asset is $S_{2}$ and the loss on the hedge is. $F_{1}-F_{2}$ . The effective price that is paid with hedging is therefore.  

$$
S_{2}+F_{1}-F_{2}=F_{1}+b_{2}
$$  

This is the same expression as before and is $\$2.30$ in the example. The value of. $F_{1}$ is known at time $t_{1}$ , and the term $b_{2}$ represents basis risk.  

Note that basis changes can lead to an improvement or a worsening of a hedger's position. Consider a company that uses a short hedge because it plans to sell the underlying asset. If the basis strengthens (i.e., increases) unexpectedly, the company's position improves because it will get a higher price for the asset after futures gains or losses are considered; if the basis weakens (i.e., decreases) unexpectedly, the company's position worsens. For a company using a long hedge because it plans to buy the asset,. the reverse holds. If the basis strengthens unexpectedly, the company's position worsens because it will pay a higher price for the asset after futures gains or losses are considered; if the basis weakens unexpectedly, the company's position improves.  

The asset that gives rise to the hedger's exposure is sometimes different from the asset underlying the futures contract that is used for hedging. This is known as cross. hedging and is discussed in the next section. It leads to an increase in basis risk. Define $S_{2}^{*}$ as the price of the asset underlying the futures contract at time $t_{2}$ . As before, $S_{2}$ is the price of the asset being hedged at time. $t_{2}$ . By hedging, a company ensures that the. price that will be paid (or received) for the asset is.  

$$
S_{2}+F_{1}-F_{2}
$$  

This can be written as  

$$
F_{1}+(S_{2}^{*}-F_{2})+(S_{2}-S_{2}^{*})
$$  

The terms $S_{2}^{*}-F_{2}$ and $S_{2}-S_{2}^{*}$ represent the two components of the basis. The $S_{2}^{*}-F_{2}$ term is the basis that would exist if the asset being hedged were the same as the asset underlying the futures contract. The $S_{2}-S_{2}^{*}$ term is the basis arising from the difference between the two assets.  

# Choice of Contract  

One key factor affecting basis risk is the choice of the futures contract to be used for hedging. This choice has two components:.  

1. The choice of the asset underlying the futures contract   
2. The choice of the delivery month..  

If the asset being hedged exactly matches an asset underlying a futures contract, the first. choice is generally fairly easy. In other circumstances, it is necessary to carry out a careful analysis to determine which of the available futures contracts has futures prices. that are most closely correlated with the price of the asset being hedged..  

The choice of the delivery month is likely to be influenced by several factors. In the. examples given earlier in this chapter, we assumed that, when the expiration of the hedge corresponds to a delivery month, the contract with that delivery month is chosen. In fact, a contract with a later delivery month is usually chosen in these circumstances. The reason is that futures prices are in some instances quite erratic during the delivery. month. Moreover, a long hedger runs the risk of having to take delivery of the physical asset if the contract is held during the delivery month. Taking delivery can be expensive. and inconvenient. (Long hedgers normally prefer to close out the futures contract and. buy the asset from their usual suppliers.)  

In general, basis risk increases as the time difference between the hedge expiration and the delivery month increases. A good rule of thumb is therefore to choose a delivery month that is as close as possible to, but later than, the expiration of the hedge. Suppose delivery months are March, June, September, and December for a futures contract on a particular asset. For hedge expirations in December, January,. and February, the March contract will be chosen; for hedge expirations in March, April, and May, the June contract will be chosen; and so on. This rule of thumb assumes that there is sufficient liquidity in all contracts to meet the hedger's requirements. In practice, liquidity tends to be greatest in short-maturity futures contracts. Therefore, in some situations, the hedger may be inclined to use shortmaturity contracts and roll them forward. This strategy is discussed later in the. chapter.  

# Example 3.1  

It is March 1. A U.S. company expects to receive 50 million Japanese yen at the end of July. Yen futures contracts on the CME Group have delivery months of March, June, September, and December. One contract is for the delivery of 12.5 million yen. The company therefore shorts four September yen futures contracts on March 1. When the yen are received at the end of July, the company closes out its position. We suppose that the futures price on March 1 in cents per yen is 1.0800 and that the spot and futures prices when the contract is closed out are 1.0200 and 1.0250, respectively.  

The gain on the futures contract is. $1.0800-1.0250=0.0550$ cents per yen. The basis is $1.0200-1.0250=-0.0050$ cents per yen when the contract is closed out.. The effective price obtained in cents per yen is the final spot price plus the gain on the futures:  

$$
1.0200+0.0550=1.0750
$$  

This can also be written as the initial futures price plus the final basis:  

$$
1.0800+(-0.0050)=1.0750
$$  

The total amount received by the company for the 50 million yen is $50\times0.01075$ million dollars, or. $\$537,500$  

# Example 3.2  

It is June 8 and a company knows that it will need to purchase 20,o00 barrels of crude oil at some time in October or November. Oil futures contracts are currently. traded for delivery every month by the CME Group and the contract size is 1,000. barrels. The company therefore decides to use the December contract for hedging and takes a long position in 20 December contracts. The futures price on June 8 is. $\$48.00$ per barrel. The company finds that it is ready to purchase the crude oil on November 10. It therefore closes out its futures contract on that date. The spot. price and futures price on November 10 are. $\$50.00$ per barrel and $\$49.10$ per barrel.  

The gain on the futures contract is. $49.10-48.00=\$1.10$ per barrel. The basis when the contract is closed out is $50.00-49.10=\$0.90$ per barrel. The effective price paid (in dollars per barrel) is the final spot price less the gain on the futures, or  

$$
50.00-1.10=48.90
$$  

This can also be calculated as the initial futures price plus the final basis,  

$$
48.00+0.90=48.90
$$  

The total price paid is $48.90\times20.000=\S978.000.$  
