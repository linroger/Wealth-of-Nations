---
tags:
  - basis_trades
  - deliverable_bond
  - futures_contract
  - gross_basis
  - net_basis
aliases:
  - Basis Trade
  - CTD
  - Package Trade
  - TYU1
key_concepts:
  - Basis Trade Definition
  - Carry Calculation Example
  - Conversion Factor Definition
  - Deliverable Bond Price
  - Futures Contract Price
  - Gross and Net Basis
---

# 11.9 GROSS AND NET BASIS AND BASIS TRADES  

The gross basis and net basis of a deliverable bond measure the difference between the price of that bond and the relevant futures contract. The gross basis of a bond is convenient for quoting the prices of packages, that is,  

the terms at which traders can buy a futures contract and short a deliverable bond, or vice versa. The net basis is a measure of a bond's proximity to being.   
CTD, and changes in a bond's net basis give the P&L of a basis trade. Lastly,.   
a basis trade is the purchase of a futures contract and the forward sale of.   
a deliverable bond, or vice versa, usually to take advantage of a perceived.   
mispricing of futures relative to the deliverable bonds..  

Let $p_{t}^{i}$ denote the spot price of bond. $i$ at time t; $p_{t}^{i}(T)$ its forward price at time $t$ to the last delivery date,. $T$ ; and $c f^{i}$ its conversion factor. Let. $F_{t}$ be the futures price at time $t$ . Then, the gross basis and net basis of bond $i$ at time $t$ $G B_{t}^{i}$ and $N B_{t}^{i}$ , respectively, are defined as,  

$$
\begin{array}{c}{{G B_{t}^{i}={p}_{t}^{i}-c{f}^{i}\times F_{t}}}\ {{}}\ {{N B_{t}^{i}={p}_{t}^{i}(T)-c{f}^{i}\times F_{t}}}\end{array}
$$  

Table 11.8 gives the futures price and the spot and forward prices of each bond deliverable into TYU1, along with its gross basis, carry, and net basis.7 For example, the gross basis of the 2 7/8s of 05/15/2028 is,  

$$
{\begin{array}{r l}&{(110-243/4)-0.8338\times131-17+}\ &{=110.7734-0.8338\times131.5469}\ &{=1.0896}\end{array}}
$$  

which is 32 times 1.0896, or 34.9 ticks. The net basis of that bond is,  

$$
{\begin{array}{l}{109.7172-0.8338\times131-17+}\ {=0.0334}\end{array}}
$$  

or 1.1 ticks.  

As defined, the difference between the gross basis and the net basis of. a bond equals the difference between its spot and forward prices, which, as shown earlier, equals its carry. This explains the terminology: the net basis. is the gross basis net of carry. Continuing with the example, the carry of the 2.875s of 05/15/2028 - from May 17, 2021 (spot settlement), to September 30, 2021 (last delivery date) - is calculated earlier in the chapter as 1.057 or 33.8 ticks. Hence, the bond's gross basis of 34.9 ticks minus its carry of 33.8. ticks equals its net basis of 1.1 ticks. It similarly follows from the definitions that, as of contract expiration - when the forward price for settlement on contract expiration is the same as its spot price at contract expiration - gross and net basis are equal to each other and to the bond's cost of delivery, as. defined in Equation (11.5). Furthermore, because the cost of delivery at expi-. ration of the CTD is zero, its gross and net basis at expiration are also zero.  

TABLE 11.8 Gross and Net Basis of Deliverable Notes into TYU1 as of May 14, 2021. Repo Rate from Spot Settlement to the Last Delivery Date is. $0.015\%$ . Gross Basis, Carry, and Net Basis Are in Ticks (32nds)..   


<html><body><table><tr><td>TYU1</td><td>Price:</td><td colspan="6">131-17+</td></tr><tr><td>Coupon</td><td>Maturity</td><td>Conv. Factor</td><td>Spot Price</td><td>Gross Basis</td><td>Fwd Price</td><td>Carry</td><td>Net Basis</td></tr><tr><td>2.875</td><td>05/15/2028</td><td>0.8338</td><td>110-24 3/4</td><td>34.9</td><td>109.7172</td><td>33.8</td><td>1.1</td></tr><tr><td>2.875</td><td>08/15/2028</td><td>0.8286</td><td>110-27</td><td>59.0</td><td>109.7759</td><td>34.2</td><td>24.8</td></tr><tr><td>1.250</td><td>04/30/2028</td><td>0.7474</td><td>99-26 1/4</td><td>48.1</td><td>99.3615</td><td>14.7</td><td>33.4</td></tr><tr><td>1.250</td><td>03/31/2028</td><td>0.7474</td><td>99-29 1/4</td><td>51.1</td><td>99.4578</td><td>14.6</td><td>36.5</td></tr><tr><td>3.125</td><td>11/15/2028</td><td>0.8376</td><td>112-22 1/4</td><td>80.4</td><td>111.5468</td><td>36.8</td><td>43.6</td></tr><tr><td>2.625</td><td>02/15/2029</td><td>0.8039</td><td>109-03+</td><td>107.5</td><td>108.1348</td><td>31.2</td><td>76.3</td></tr><tr><td>2.375</td><td>05/15/2029</td><td>0.7836</td><td>107-07 1/4</td><td>132.7</td><td>106.3549</td><td>27.9</td><td>104.8</td></tr><tr><td>1.625</td><td>08/15/2029</td><td>0.7320</td><td>101-13+</td><td>164.1</td><td>100.8205</td><td>19.2</td><td>144.9</td></tr><tr><td>1.750</td><td>11/15/2029</td><td>0.7331</td><td>102-07+</td><td>185.5</td><td>101.5934</td><td>20.5</td><td>165.0</td></tr><tr><td>1.500</td><td>02/15/2030</td><td>0.7105</td><td>99-271/4</td><td>204.4</td><td>99.2968</td><td>17.8</td><td>186.6</td></tr><tr><td>0.625</td><td>05/15/2030</td><td>0.6462</td><td>92-05 1/4</td><td>229.1</td><td>91.9383</td><td>7.2</td><td>221.8</td></tr><tr><td>0.625</td><td>08/15/2030</td><td>0.6382</td><td>91-24 3/4</td><td>250.2</td><td>91.5451</td><td>7.3</td><td>242.9</td></tr><tr><td>0.875</td><td>11/15/2030</td><td>0.6476</td><td>93-201/4</td><td>270.2</td><td>93.3147</td><td>10.2</td><td>260.0</td></tr><tr><td>1.125</td><td>02/15/2031</td><td>0.6577</td><td>95-16 1/4</td><td>287.7</td><td>95.0929</td><td>13.3</td><td>274.4</td></tr></table></body></html>  

Gross and net basis are particularly useful in the context of basis trades.. To buy or be long a bond's basis, a trader buys a bond forward to contract expiration and sells a conversion-factor weighted number of futures contracts. To sell or be short a bond's basis, a trader sells a bond forward to contract expiration and buys a conversion-factor weighted number of futures contracts. In the US Treasury market, where spot and repo mar-. kets are much more liquid than forward markets, forward purchases and. sales of bonds are typically synthetic, as described earlier in the chapter. A conversion-factor weighted number of contracts is the number of contracts corresponding to the face amount of the bonds times the bond's conversion factor. For example, a trader buying. $\$100$ million of the 2.875s of 05/15/2028 TYU1 basis buys $\$100$ million face amount of the bonds for-. ward and sells 0.8338 times $\$100$ million divided by $\$100,000$ , or about 834 contracts.  

Gross basis is often used to quote a package trade of bonds against futures. A trader might put in an order, for example, to buy $\$100$ million face amount of the 2.875s of $08/15/2028$ and sell 834 TYU1 contracts at a gross basis of 34.9 ticks or less. If prices subsequently line up such that the bond price minus 0.8338 times the futures price is less than or equal to 34.9 ticks, the trade is executed. The trader then sells the repo to TYU1's expiration date to complete the basis trade.  

Abstracting for a moment from interest on daily settlement payments, the P&L of a long basis position is the sum of the profit or loss from the forward bond position and from the futures position. Algebraically, with $G^{i}$ face amount of bond $i$ and a trade from time $t$ to time $s$ , the $\mathrm{P}\&\mathrm{L}$ is,  

$$
G^{i}\times[P_{s}^{i}(T)-P_{t}^{i}(T)]-G^{i}\times c f^{i}\times[F_{s}-F_{t}]
$$  

But, from the definition of the net basis in Equation (11.15), (11.18) can be rewritten as,  

$$
G^{i}\times[N B_{s}^{i}(T)-N B_{t}^{i}(T)]
$$  

In words, the $\mathrm{P}\&\mathrm{L}$ of a long basis trade is the face amount of bonds. times the change in the bond's net basis. The P&L of a short basis trade is. the negative of that. Consider, then, a trader who is sure that a particular. bond will be CTD at expiration but sees that the net basis of the bond is trading at five ticks. This trader might very well sell the basis in the hope of. making five ticks: if the bond does turn out to be CTD, its net basis will be zero at expiration, and the trader's profit will be the difference between the initial net basis of five ticks and the final net basis of zero ticks. Along these lines, therefore, the net basis of a bond is an indicator of a bond's becoming CTD. With respect to TYU1 as of May 14, 2021, the net bases in Table 11.8 strongly indicate that the 2.875s of 05/15/2028 will be CTD at expiration. Price are such that traders cannot make much money by betting that the 2.875s of 05/15/2028 will be CTD, that is, by selling its basis at only 1.1 ticks. But they can make a lot of money by taking a contrarian view that turns out to be right, for example, by selling the 2.875s of 08/15/2028 basis. at 24.8 ticks in the hope that this bond will turn out to be CTD.  

The interpretation of net basis in the previous paragraph implicitly. assumes that the futures price is fair, or valued correctly, relative to the prices of the underlying bonds and their volatility. In terms of TYU1 as of May 14, 2021, assuming that the futures price is fair is equivalent to saying. that the net basis of the 2.875s of 05/15/2028 is 1.1 ticks - rather than zero - because there is still some chance that another bond will turn out to be CTD at delivery. But some trader might believe that bond price volatility. from May 14, 2021, to September 30, 2021, is much too small for a change. in the CTD to be possible. From that trader's perspective, the market's net basis of the 2.875s of 05/15/2028, at 1.1 ticks, is too high; that is, the price of the 2.875s of 05/15/2028 is too high relative to the futures price. In this sense, net basis can be an indicator of relative value..  

This section closes with two details about gross and net basis and basis trades. First, Equations (11.18) and (11.19) are not completely accurate expressions of the P&L of basis trades as described, because interest is paid or earned on daily settlements of the futures contract. As mentioned earlier, however, tailing the hedge does account for daily settlements. Therefore, these P&L equations are accurate representations of P&L for basis trades with a tail hedge, that is, not with a conversion-factor weighted number of futures contracts, but with a conversion-factor weighted and tailed number of futures contracts. Second, some traders, instead of selling or buying. the repo to the term of the futures contract, sell or buy overnight repo. These traders are not really buying or selling the bonds forward against. their futures positions, and the resulting. $\mathrm{P}\&\mathrm{L}$ is not equal to that given in. Equations (11.18) and (11.19). The case study at the end of this chapter discusses the risks of a "basis" trade with overnight rather than term repo.  
