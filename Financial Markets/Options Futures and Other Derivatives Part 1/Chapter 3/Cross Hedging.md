---
tags:
  - '#cross_hedging'
  - '#daily_settlement'
  - '#futures_contracts'
  - '#heating_oil_futures'
  - '#hedge_effectiveness'
  - '#hedge_ratio'
  - '#jet_fuel'
  - '#minimum_variance_hedge_ratio'
  - '#optimal_number_of_contracts'
  - '#tailing_the_hedge'
---
# 3.4 CROSS HEDGING  

In Examples 3.1 and 3.2, the asset underlying the futures contract was the same as the asset whose price is being hedged. Cross hedging occurs when the two assets are different. Consider, for example, an airline that is concerned about the future price of jet fuel. Because jet fuel futures are not actively traded, it might choose to use heating oil futures contracts to hedge its exposure.  

The hedge ratio is the ratio of the size of the position taken in futures contracts to the size of the exposure. When the asset underlying the futures contract is the same as the asset being hedged, it is natural to use a hedge ratio of 1.0. This is the hedge ratio we have used in the examples considered so far. For instance, in Example 3.2, the hedger's exposure was on 20,o00 barrels of oil, and futures contracts were entered into for the delivery of exactly this amount of oil.  

When cross hedging is used, setting the hedge ratio equal to 1.0 is not always. optimal. The hedger should choose a value for the hedge ratio that minimizes the variance of the value of the hedged position. We now consider how the hedger can. do this.  

# Calculating the Minimum Variance Hedge Ratio  

We first present an analysis assuming no daily settlement of futures contracts. The minimum variance hedge ratio depends on the relationship between changes in the spot price and changes in the futures price. Define:  

AS: Change in spot price,. $S$ , during a period of time equal to the life of the hedge $\Delta F$ : Change in futures price,. $F_{:}$ during a period of time equal to the life of the hedge.  

If we assume that the relationship between $\Delta S$ and $\Delta F$ is approximately linear (see Figure 3.2), we can write:  

$$
\Delta S=a+b\Delta F+\epsilon
$$  

where $a$ and $^b$ are constants and $\epsilon$ is an error term. Suppose that the hedge ratio is. $h$ (i.e., a percentage $h$ of the exposure to $S$ is hedged with futures). Then the change in the. value of the position per unit of exposure to $S$ is  

$$
\Delta S-h\Delta F=a+(b-h)\Delta F+\epsilon
$$  

The standard deviation of this is minimized by setting $h=b$ (so that the second term on the right-hand side disappears).  

Denote the minimum variance hedge ratio by. $h^{*}$ . We have shown that. $\boldsymbol{h}^{*}=\boldsymbol{b}$ . It follows from the formula for the slope in linear regression that  

$$
h^{\ast}=\rho\frac{\sigma_{S}}{\sigma_{F}}
$$  

Figure 3.2  Regression of change in spot price against change in futures price.  

![](images/d0c8916772fd20119a123cfc0ecd094afb6d08d972ec0cb062539cf2b06e21bd.jpg)  

![](images/24c979b6b1a492a888680f83b9f1e79943484be2701c72a51751dc8fa366215b.jpg)  
Figure 3.3 Dependence of variance of hedger's position on hedge ratio.  

where $\sigma_{S}$ is the standard deviation of $\Delta S,\sigma_{F}$ is the standard deviation of $\Delta F$ , and $\rho$ is the coefficient of correlation between the two.  

Equation (3.1) shows that the optimal hedge ratio is the product of the coefficient of correlation between $\Delta S$ and $\Delta F$ and the ratio of the standard deviation of. $\Delta S$ to thee standard deviation of $\Delta F$ Figure 3.3 shows how the variance of the value of the. hedger's position depends on the hedge ratio chosen.  

If $\rho=1$ and $\sigma_{F}=\sigma_{S}$ , the hedge ratio,. $h^{*}$ , is 1.0. This result is to be expected, because. in this case the futures price mirrors the spot price perfectly. If $\rho=1$ and $\sigma_{F}=2\sigma_{S}$ the hedge ratio $h^{*}$ is 0.5. This result is also as expected, because in this case the futures price always changes by twice as much as the spot price. The hedge effectiveness can be defined as the proportion of the variance that is eliminated by hedging. This is the $R^{2}$ from the regression of. $\Delta S$ against $\Delta F$ and equals $\rho^{2}$  

The parameters $\rho,\sigma_{F}$ and $\sigma_{S}$ in equation (3.1) are usually estimated from historical. data on $\Delta S$ and $\Delta F$ (The implicit assumption is that the future will in some sense be. like the past.) A number of equal nonoverlapping time intervals are chosen, and the. values of $\Delta S$ and $\Delta F$ for each of the intervals are observed. Ideally, the length of each. time interval is the same as the length of the time interval for which the hedge is in effect. In practice, this sometimes severely limits the number of observations that are available, and a shorter time interval is used..  

# Optimal Number of Contracts  

To calculate the number of contracts that should be used in hedging, define:  

$Q_{A}$ : Size of position being hedged (units) $Q_{F}$ : Size of one futures contract (units) $N^{*}$ : Optimal number of futures contracts for hedging.  

The futures contracts should be on. $h^{*}Q_{A}$ units of the asset. The number of futures contracts required is therefore given by.  

$$
N^{*}=\frac{h^{*}Q_{A}}{Q_{F}}
$$  

Example 3.3 shows how the results in this section can be used by an airline hedging the purchase of jet fuel.3  

# Example 3.3  

An airline expects to purchase 2 million gallons of jet fuel in 1 month and decides to use heating oil futures for hedging. We suppose that Table 3.2 gives, for 15 successive months, data on the change, $\Delta S$ , in the jet fuel price per gallon and the corresponding change, $\Delta F$ , in the futures price for the contract on heating oil that would be used for hedging price changes during the month. In this case, the usual formulas for calculating standard deviations and correlations give $\sigma_{F}=0.0313$ $\sigma_{S}=0.0263$ , and $\rho=0.928$  

From equation (3.1), the minimum variance hedge ratio, $h^{*}$ , is therefore  

$$
0.928\times{\frac{0.0263}{0.0313}}=0.78
$$  

Each heating oil contract traded by the CME Group is on 42,000 gallons of heating oil. From equation (3.2), the optimal number of contracts is  

$$
\frac{0.78\times2,000,000}{42,000}
$$  

which is 37 when rounded to the nearest whole number.  

Table 3.2 Data to calculate minimum variance hedge ratio when heating oil futures contract is used to hedge purchase of jet fuel.   


<html><body><table><tr><td>Month i</td><td>Change in heating oil futures price per gallon (= △F)</td><td>Changeinjet fuel price per gallon (= △S)</td></tr><tr><td>1</td><td>0.021</td><td>0.029</td></tr><tr><td>2</td><td>0.035</td><td>0.020</td></tr><tr><td>3</td><td>-0.046</td><td>-0.044</td></tr><tr><td>4</td><td>0.001</td><td>0.008</td></tr><tr><td>5</td><td>0.044</td><td>0.026</td></tr><tr><td>6</td><td>-0.029</td><td>-0.019</td></tr><tr><td>7</td><td>-0.026</td><td>-0.010</td></tr><tr><td>8</td><td>-0.029</td><td>-0.007</td></tr><tr><td>9</td><td>0.048</td><td>0.043</td></tr><tr><td>10</td><td>-0.006</td><td>0.011</td></tr><tr><td>11</td><td>-0.036</td><td>-0.036</td></tr><tr><td>12</td><td>-0.011</td><td>-0.018</td></tr><tr><td>13</td><td>0.019</td><td>0.009</td></tr><tr><td>14</td><td>-0.027</td><td>-0.032</td></tr><tr><td>15</td><td>0.029</td><td>0.023</td></tr></table></body></html>

3 Derivatives with payoffs dependent on the price of jet fuel do exist, but heating oil futures are often used to hedge an exposure to jet fuel prices because they are traded more actively..  

# Impact of Daily Settlement  

The analysis we have presented so far is appropriate when forward contracts are used for hedging. The daily settlement of futures contract means that, when futures contracts are used, there are a series of one-day hedges, not a single hedge. Define:  

$\hat{\sigma}_{S}$ : Standard deviation of percentage one-day changes in the spot price $\hat{\sigma}_{F}$ : Standard deviation of percentage one day changes in the futures price $\hat{\rho}$ :Correlation between percentage one-day changes in the spot and futures.  

The standard deviation of one-day changes in spot and futures are $\hat{\sigma}_{S}S$ and $\hat{\sigma}_{F}F.$ Also, $\hat{\rho}$ is the correlation between one-day changes. It follows from equation (3.1) that the optimal one-day hedge is  

$$
h^{*}=\hat{\rho}\frac{\hat{\sigma}_{S}S}{\hat{\sigma}_{F}F}
$$  

so that from equation (3.2)  

$$
\boldsymbol{N}^{*}=\hat{\rho}\frac{\hat{\sigma}_{S}S Q_{A}}{\hat{\sigma}_{F}F Q_{F}}
$$  

The hedge ratio in equation (3.1) is based on regressing actual changes in spot prices against actual changes in futures prices. An alternative hedge ratio,. $\hat{h}$ , can be derived in the same way by regressing daily percentage changes in spot against daily percentage. changes in futures:  

$$
\hat{h}=\hat{\rho}\frac{\hat{\sigma}_{S}}{\hat{\sigma}_{F}}
$$  

Then  

$$
N^{*}=\frac{\hat{h}V_{A}}{V_{F}}
$$  

where $V_{A}=S Q_{A}$ is the value of the position being hedged and ${\cal V}_{\cal F}={\cal F}Q_{\cal F}$ is the futures price times the size of one contract..  

Consider another situation where 2 million gallons of jet fuel is being hedged with heating oil futures. Suppose that the spot and futures price are 1.10 and 1.30, respectively. In this case, $V_{A}=2$ , 000, $000\times1.10=2$ , 200, 000 while $V_{F}=42,000\times1.30=54,600.$ If $\hat{\rho}=0.8$ , the optimal number of contracts for a one-day hedge is.  

$$
\frac{0.8\times2{,}200{,}000}{54{,}600}=32.23
$$  

or 32 when rounded to the nearest whole number. The optimal hedge is liable to change from day to day as the relative values of spot and futures prices change. But the changes are usually small and often ignored.  

The analysis can be refined by taking account of the the interest that is earned or paid over the remaining life of the hedge. Suppose that the interest rate is $5\%$ per annum and the hedge has a remaining life of one year. It is then appropriate to divide $N^{*}$ by 1.05. This is referred to as tailing the hedge.  
