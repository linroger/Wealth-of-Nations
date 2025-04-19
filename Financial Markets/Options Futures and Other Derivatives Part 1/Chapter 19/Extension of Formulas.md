---
tags:
  - '#currency_options'
  - '#delta_hedging'
  - '#delta_neutral_position'
  - '#dividend_yield'
  - '#european_options'
  - '#foreign_risk_free_rate'
  - '#forward_contracts'
  - '#futures_contracts'
  - '#greek_letters'
  - '#option_pricing_formulas'
---
# 19.12 EXTENSION OF FORMULAS  

The formulas produced so far for delta, theta, gamma, vega, and rho have been for a European option on a non-dividend-paying stock. Table 19.6 shows how they change when the stock pays a continuous dividend yield at rate. $q$ . The expressions for $d_{1}$ and $d_{2}$ are as for equations (17.4) and (17.5). By setting $q$ equal to the dividend yield on an index,. we obtain the Greek letters for European options on indices. By setting $q$ equal to the foreign risk-free rate, we obtain the Greek letters for European options on a currency. By setting $q=r$ we obtain delta, gamma, theta, and vega for European options on a futures contract. The rho for a call futures option is. $-c T$ and the rho for a European put futures. option is $-p T$  

In the case of currency options, there are two rhos corresponding to the two interest. rates. The rho corresponding to the domestic interest rate is given by the formula in Table 19.6 (with $d_{2}$ as in equation (17.11)). The rho corresponding to the foreign. interest rate for a European call on a currency is.  

$$
\mathrm{rho(call,foreignrate)}=-T e^{-r_{f}T}S_{0}N(d_{1})
$$  

For a European put, it is  

$$
\mathrm{rho(put,foreign~rate)}=T e^{-r_{f}T}S_{0}N(-d_{1})
$$  

with $d_{1}$ as in equation (17.11).  

The calculation of Greek letters for American options is discussed in Chapter 21.  

# Delta of Forward Contracts  

The concept of delta can be applied to financial instruments other than options. Consider a forward contract on a non-dividend-paying stock. Equation (5.5) shows that the value of a forward contract is $S_{0}\mathrm{~-~}K e^{-r T}$ where $K$ is the delivery price and $T$ is the forward. contract's time to maturity. When the price of the stock changes by $\Delta S$ , with all else. remaining the same, the value of a forward contract on the stock also changes by $\Delta S.$ The delta of a long forward contract on one share of the stock is therefore always 1.0. This means that a long forward contract on one share can be hedged by shorting one share; a short forward contract on one share can be hedged by purchasing one share.12  

Table 19.6 Greek letters for European options on an asset providing a yield at rate $q$   


<html><body><table><tr><td>Greekletter</td><td>Call option</td><td>Putoption</td></tr><tr><td>Delta</td><td>e-qT N(d)</td><td>e-qT [N(di)- 1]</td></tr><tr><td>Gamma</td><td>N'(d)e-qT SooVT</td><td>N'(d)e-qT SooVT</td></tr><tr><td>Theta</td><td>-SoN'(d)oe-qT /(2VT) + qSoN(d)e-qT - rKe-rT N(d2)</td><td>-SoN'(d)oe-qT /(2VT) - qSoN(-d)e-qT + rKe-rT N(-d2)</td></tr><tr><td>Vega</td><td>SoVTN'(d)e-qT</td><td>SoVTN'(d)e-qT</td></tr><tr><td>Rho</td><td>KTe-rT N(d2)</td><td>-KTe-rT N(-d2)</td></tr></table></body></html>  

For an asset providing a dividend yield at rate $q$ , equation (5.7) shows that the forward contract's delta is $e^{-q T}$ For the delta of a forward contract on a stock index, $q$ is set equal to the dividend yield on the index in this expression. For the delta of a forward foreign exchange contract, it is set equal to the foreign risk-free rate,. $r_{f}.$  

# Delta of a Futures Contract  

From equation (5.1), the futures price for a contract on a non-dividend-paying stock is. $S_{0}e^{r T}$ where $T$ is the time to maturity of the futures contract. This shows that when the. price of the stock changes by $\Delta S$ , with all else remaining the same, the futures price changes by $\Delta S e^{r T}$ Since futures contracts are settled daily, the holder of a long futures position makes an almost immediate gain of this amount. The delta of a futures contract is therefore $e^{r T}.$ For a futures position on an asset providing a dividend yield at rate q, equation (5.3) shows similarly that delta is e(r-q)T.  

It is interesting that daily settlement makes the deltas of futures and forward contracts. slightly different. This is true even when interest rates are constant and the forward price equals the futures price. (A related point is made in Business Snapshot 5.2.).  

Sometimes a futures contract is used to achieve a delta-neutral position. Define:  

$T$ : Maturity of futures contract.   
$H_{A}$ : Required position in asset for delta hedging.   
$H_{F}$ : Alternative required position in futures contracts for delta hedging.  

If the underlying asset is a non-dividend-paying stock, the analysis we have just given shows that  

$$
H_{F}=e^{-r T}H_{A}
$$  

When the underlying asset pays a dividend yield $q$  

$$
H_{F}=e^{-(r-q)T}H_{A}
$$  

For a stock index, we set. $q$ equal to the dividend yield on the index; for a currency, we set it equal to the foreign risk-free rate,. $r_{f}$ so that  

$$
H_{F}=e^{-(r-r_{f})T}H_{A}
$$  

# Example 19.8  

Suppose that a portfolio of currency options held by a U.S. bank can be made delta neutral with a short position of 458,000 pounds sterling. Risk-free rates are $4\%$ in the United States and $7\%$ in the United Kingdom. From equation (19.7),. hedging using 9-month currency futures requires a short futures position.  

$$
e^{-(0.04-0.07)\times9/12}\times458,000
$$  

or 468,442. Since each futures contract is for the purchase or sale of 62,500, seven contracts would be shorted. (Seven is the nearest whole number to 468,442/62,500.)  
