# 5.11 FUTURES ON COMMODITIES  

We now move on to consider futures contracts on commodities. First we look at the futures prices of commodities that are investment assets such as gold and silver.6 we then go on to examine the futures prices of consumption assets.  

# Income and Storage Costs  

As explained in Business Snapshot 3.1, the hedging strategies of gold producers leads to.   
a requirement on the part of investment banks to borrow gold. Gold owners such as central banks charge interest in the form of what is known as the gold lease rate when.   
they lend gold. The same is true of silver. Gold and silver can therefore provide income.   
to the holder. Like other commodities they also have storage costs..  

Equation (5.1) shows that, in the absence of storage costs and income, the forward price of a commodity that is an investment asset is given by.  

$$
F_{0}=S_{0}e^{r T}
$$  

Storage costs can be treated as negative income. If. $U$ is the present value of all the. storage costs, net of income, during the life of a forward contract, it follows from equation (5.2) that  

$$
F_{0}=(S_{0}+U)e^{r T}
$$  

# Example 5.8  

Consider a 1-year futures contract on an investment asset that provides no income. It costs $\$2$ per unit to store the asset, with the payment being made at the end of the year. Assume that the spot price is $\$450$ per unit and the risk-free rate is $7\%$ per annum for all maturities. This corresponds to $r=0.07,S_{0}=450,T=1.$ and  

$$
U=2e^{-0.07\times1}=1.865
$$  

From equation (5.11), the theoretical futures price, $F_{0}$ , is given by  

$$
F_{0}=(450+1.865)e^{0.07\times1}=\S484.63
$$  

If the actual futures price is greater than 484.63, an arbitrageur can buy the asset. and short 1-year futures contracts to lock in a profit. If the actual futures price is less than 484.63, an investor who already owns the asset can improve the return by. selling the asset and buying futures contracts..  

If the storage costs (net of income) incurred at any time are proportional to the price of the commodity, they can be treated as negative yield. In this case, from equation (5.3),  

$$
F_{0}=S_{0}e^{(r+u)T}
$$  

where $u$ denotes the storage costs per annum as a proportion of the spot price net of any yield earned on the asset..  

# Consumption Commodities  

Commodities that are consumption assets rather than investment assets usually provide no income, but can be subject to significant storage costs. We now review the arbitrage strategies used to determine futures prices from spot prices carefully. Suppose that, instead of equation (5.11), we have  

$$
F_{0}>(S_{0}+U)e^{r T}
$$  

To take advantage of this opportunity, an arbitrageur can implement the following strategy:  

1. Borrow an amount $S_{0}+U$ at the risk-free rate and use it to purchase one unit of the commodity and to pay storage costs..   
2. Short a futures contract on one unit of the commodity.  

If we regard the futures contract as a forward contract, so that there is no daily settlement, this strategy leads to a profit of $F_{0}-(S_{0}+U)e^{r T}$ at time $T$ There is no problem in implementing the strategy for any commodity. However, as arbitrageurs do so, there will be a tendency for $S_{0}$ to increase and $F_{0}$ to decrease until equation (5.13) is no longer true. We conclude that equation (5.13) cannot hold for any significant length of time.  

Suppose next that  

$$
F_{0}<(S_{0}+U)e^{r T}
$$  

When the commodity is an investment asset, we can argue that many investors hold the commodity solely for investment. When they observe the inequality in equation (5.14), they will find it profitable to do the following:  

1. Sell the commodity, save the storage costs, and invest the proceeds at the risk-free interest rate.   
2. Take a long position in a futures contract.  

The result is a riskless profit at maturity of $(S_{0}+U)e^{r T}-F_{0}$ relative to the position the investors would have been in if they had held the commodity. It follows that equation (5.14) cannot hold for long. Because neither equation (5.13) nor (5.14) can hold for long, we must have $F_{0}=(\bar{S}_{0}+U)e^{r T}$  

This argument cannot be used for a commodity that is a consumption asset rather than an investment asset. Individuals and companies who own a consumption commodity usually plan to use it in some way. They are reluctant to sell the commodity in the spot market and buy forward or futures contracts, because forward and futures contracts cannot be used in a manufacturing process or consumed in some other way. There is therefore nothing to stop equation (5.14) from holding, and all we can assert for a consumption commodity is  

$$
F_{0}\le(S_{0}+U)e^{r T}
$$  

If storage costs are expressed as a proportion $u$ of the spot price, the equivalent result is  

$$
F_{0}\leq S_{0}e^{(r+u)T}
$$  

# Convenience Yields  

We do not necessarily have equality in equations (5.15) and (5.16) because users of a. consumption commodity may feel that ownership of the physical commodity provides benefits that are not obtained by holders of futures contracts. For example, an oil refiner is unlikely to regard a futures contract on crude oil in the same way as crude oil held in inventory. The crude oil in inventory can be an input to the refining process,. whereas a futures contract cannot be used for this purpose. In general, ownership of the physical asset enables a manufacturer to keep a production process running and perhaps profit from temporary local shortages. A futures contract does not do the. same. The benefits from holding the physical asset are sometimes referred to as the. convenience yield provided by the commodity. If the dollar amount of storage costs is known and has a present value. $U$ , then the convenience yield. $y$ is defined such that  

$$
F_{0}e^{y T}=(S_{0}+U)e^{r T}
$$  

If the storage costs per unit are a constant proportion, $u$ , of the spot price, then $y$ is defined so that  

$$
F_{0}e^{y T}=S_{0}e^{(r+u)T}
$$  

or  

$$
F_{0}=S_{0}e^{(r+u-y)T}
$$  

The convenience yield simply measures the extent to which the left-hand side is less than the right-hand side in equation (5.15) or (5.16). For investment assets the convenience yield must be zero; otherwise, there are arbitrage opportunities. Table 2.2 in Chapter 2 shows that, on May 21, 2020, the futures price of soybeans decreased as the maturity of the contract increased from January 2021 to May 2021. This pattern suggests that the convenience yield, $y$ , is greater than $r+u$ during this period.  

The convenience yield reflects the market's expectations concerning the future avail-. ability of the commodity. The greater the possibility that shortages will occur, the higher. the convenience yield. If users of the commodity have high inventories, there is very little chance of shortages in the near future and the convenience yield tends to be low. If inventories are low, shortages are more likely and the convenience yield is usually higher.  
