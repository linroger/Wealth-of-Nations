---
tags:
  - asset_pricing
  - continuous_compounding
  - forward_contract
  - known_yield
  - risk_free_rate
aliases:
  - Known Yield
  - Yield Calculation
key_concepts:
  - asset known yield
  - borrow to buy asset
  - continuous compounding yield
  - forward contract income
  - risk-free interest rate
---

# 5.6 KNOWN YIELD  

We now consider the situation where the asset underlying a forward contract provides a. known yield rather than a known cash income. This means that the income is known. when expressed as a percentage of the asset's price at the time the income is paid.. Suppose that an asset is expected to provide a yield of. $5\%$ per annum. This could mean. that income is paid once a year and is equal to. $5\%$ of the asset price at the time it is paid, in which case the yield would beo. $5\%$ with annual compounding. Alternatively, it could. mean that income is paid twice a year and is equal to. $2.5\%$ of the asset price at the time. it is paid, in which case the yield would be $5\%$ per annum with semiannual compounding. In Section 4.4 we explained that we will normally measure interest rates with continuous compounding. Similarly, we will normally measure yields with continuous. compounding. Formulas for translating a yield measured with one compounding frequency to a yield measured with another compounding frequency are the same as. those given for interest rates in Section 4.4..  

Define $q$ as the average yield on the asset during time $T.$ If the income is reinvested in the asset, the number of units held grows at rate $q$ . One unit of the asset at time zero then grows to $e^{q T}$ units of the asset at time $T.$ The strategye  

.Borrow $S_{0}$ to buy one unit of the asset at time zero . Enter into a forward contract to sell $e^{q T}$ units of the asset at time $T$ for $F_{0}$ . Close out the forward contract by selling $e^{q T}$ units of the asset at time $T$ must therefore generate zero profit. Hence,  

$$
S_{0}e^{r T}=e^{q T}F_{0}
$$  

or  

$$
F_{0}=S_{0}e^{(r-q)T}
$$  

# Example 5.3  

Consider a 6-month forward contract on an asset that is expected to provide income equal to $2\%$ of the asset price once during a 6-month period. The risk-. free rate of interest (with continuous compounding) is $10\%$ per annum. The asset price is $\$25$ . In this case, $S_{0}=25,r=0.10$ , and $T=0.5$ . The yield is $4\%$ per annum with semiannual compounding. From equation (4.3), this is. $3.96\%$ per annum with continuous compounding. It follows that. $q=0.0396$ , so that from equation (5.3) the forward price,. $F_{0}$ , is given by  

$$
F_{0}=25e^{(0.10-0.0396)\times0.5}=\S25.77
$$  
