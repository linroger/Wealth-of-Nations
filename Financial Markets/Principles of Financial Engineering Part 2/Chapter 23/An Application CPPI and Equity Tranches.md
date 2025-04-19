---
tags:
  - cppi
  - credit_derivatives
  - equity_tranches
  - itraxx
  - structured_credit
aliases:
  - CPPI Application
  - CPPI and Equity Tranches
  - Structured Credit CPPI
  - iTraxx Tranches
key_concepts:
  - CPPI technique
  - capital protection
  - credit derivatives index
  - equity tranche
  - leverage factor
  - leveraged fund
  - retail investors
  - risky asset
  - synthetic cdo
  - zero-coupon bond
---

# 23.5 AN APPLICATION: CPPI AND EQUITY TRANCHES  

We will use structured credit as an application of the CPPI technique. The credit sector has experi-.   
enced significant growth and innovation in recent years. The GFC did not leave it unaffected but.   
the sector has recovered since and its products are likely to remain a part of the financial landscape.   
Two paradigms are observed in the structured credit sector. The first tracks some credit derivatives index, and the second is managed credit derivatives funds. CPPI techniques can be useful in both.   
of these trends as shown in the example from the markets..  

# EXAMPLE  

Retail credit CPPI first ABN AMRO and AXA last week announced that they had closed the first principal protected credit derivatives fund targeted at retail investors. AXA persuaded its home regulator in France to permit the leveraged fund, and similar deals are expected to be launched in other regimes.  

The fund is structured like an actively managed synthetic collateralized debt obligation. It will. have a minimum of 100 credit default swap references and is starting with just under 120 names.  

It uses CPPI from ABN AMRO to provide the capital protection that was necessary to obtain regulatory approval for its sale to retail investors in France. The insurance is provided on a binary basis if the basket of default swaps managed by AXA performs so poorly that a zero-coupon bond would have to be bought to guarantee investor capital, then there would be an effective wind-up.  

In this section, we discuss the application of the CPPI technique to standard credit index tranches.. It turns out that combining CPPI and iTraxx tranches is quite simple in terms of financial engineering,. although there are some practical issues that need to be resolved in practice. Here is the algorithm.  

1. Receive cash ofr. $N=100$ from the investor..   
2. Calculate the difference between par and the cost of a zero-coupon bond $F_{t},$ and as before let this term be $C u_{t}$ the cushion.   
3. Multiply the cushion $C u_{t}$ by the leverage factor $\lambda$ This is the leveraged amount.   
4. Subtract the leveraged amount, $C u_{t}\times\lambda$ , from the 100 total cash $N$ and invest, $C u_{t}\times\lambda$ , in the risky asset, which in this case is assumed to be the iTraxx. $0-3\%$ equity tranche. Keep the remaining cash or reserve cash,. $\begin{array}{r}{I O O-C u_{t}\times\lambda_{\mathrm{~}}}\end{array}$ in a deposit account or as collateral.'.   
5. As the price of the iTraxx equity tranche goes up and down, adjust the allocation between risk asset and reserve cash to keep the leverage of the trade constant at $\lambda.$  

Thus far this is a straightforward application of the previously discussed CPPI algorithm. The only major complication is in the definition of the risky asset. Standard equity tranches are quoted as upfront percentages and this will lead to a modification of the algorithm. In fact, suppose the amount to be invested in the risky asset is. $R_{t},$ and suppose also that the iTraxx equity tranche quote. is given by $q_{t}$ where the latter is a pure number denoting the upfront payment as a percentage. Then the relationship between the amount allocated in the risky asset and the notional amount invested in the equity tranche $N^{\mathrm{Eq}}$ will be as follows:.  

$$
N_{t_{i}}^{\mathrm{Eq}}=\frac{R_{t_{i}}}{(1-q_{t})}
$$  

In terms of the amount invested in the risky asset, $R_{t_{i}}$ , this can also be written as  

$$
R_{t_{i}}=N_{t_{i}}^{\mathrm{Eq}}\times(1-q_{t})=N_{t_{i}}^{\mathrm{Eq}}-\frac{R_{t_{i}}}{(1-q_{t})}q_{t}
$$  

It may be helpful to discuss a numerical example at this point.  

# 23.5.1 A NUMERICAL EXAMPLE  

The following example shows how CPPI can be combined with the ITraxx and has similarities to a real-world product CPPI product that was called SPRING and developed by the IXIS CDO group..  

First we note that the equity tranche of the iTraxx Index is quoted as an upfront percentage of the notional plus 500 basis point running-fee paid quarterly. Assume that the upfront fee of the iTraxx equity tranche is $q_{t}=20\%$ of the notional amount invested in the equity tranche. $N^{\mathrm{Eq}}$ and that the annual LIBOR rate is $L_{t}=5\%$ . For simplicity, suppose the swap curve is flat at. $5.095\%$ as well. The CPPI is applied with daily adjustment periods denoted by. $t_{i},i=0,1,...,n.$ The leverage factor is assumed to be 2. Assume no bid-ask spreads. Figure 23.1 illustrates how the leveraged amount $C u_{t}\times\lambda$ is invested in the risky asset. It also shows that the equity tranche of the iTraxx. index is quoted as an upfront cash amount..  

![](0ec9f6fdad0d355964567c64f7fca16abf811c13e9a2d70c823f5c27aec2e464.jpg)  

# FIGURE 23.1  

iTraxx CPPI example.  

We apply the steps above in a straightforward fashion to a 5-year CPPI note where the underlying is the equity tranche.  

# 23.5.1.1 The initial position  

Initially the CPPI will have the following structure.  

1. Receive $N=100$   
2. The floor is  

$$
\begin{array}{r l}{F_{t}}&{{}=\cfrac{100}{\left(1+0.05095\right)^{5}}}\ {~}&{{}=78}\end{array}
$$  

3. The cushion is  

$$
\begin{array}{r l}{C u_{t}}&{{}=100-78}\ {}&{{}=22}\end{array}
$$  

4. Assuming a leverage of  

$$
\lambda=2
$$  

the amount to be invested in the risky asset is  

$$
22\times2=44
$$  

This is the investment to be allocated to the equity tranche.  

5. The iTraxx equity tranche pays an upfront cash amount of $20\%\times N^{\mathrm{Eq}}$ . Therefore, if the risky. asset exposure is $R_{t}=44$ , then the notional amount invested in the equity tranche $N^{\mathrm{Eq}}$ should be  

$$
N^{\mathrm{Eq}}=\frac{44}{(1-0.20)}=55
$$  

Thus, sell equity tranche protection with notional $N^{\mathrm{Eq}}$ of 55. In other words, an equity tranche notional amount $N^{\mathrm{Eq}}$ of 55 implies an uncovered exposure of 55 less 11 $(=q_{t}\times55=20\%\times55)$ received upfront which leaves 44. The 44 is put into reserve cash. 5. When we buy the iTraxx equity tranche we enter into a swap on the iTraxx equity tranche. This implies that the cash allocated to the risky asset, in addition to the upfront cash received, is held as collateral for the swap. This is illustrated in Figure 23.1 in which we can see how the equity tranche notional amount $N^{\mathrm{Eq}}$ consists of the upfront payment (fee) of 11 and the risky asset. Note that the total amount of cash to be kept as collateral for the equity protection position is  

$$
q_{t}N^{\mathrm{Eq}}+(100-\lambda C u_{t})=20\%\times55+44=11+44=55
$$  

Since the risky asset investment is 44 and the cash invested initially is $N=l O O$ , a balance of 56 remains. The balance of 56 is kept in reserve cash and receives LIBOR.  

7. Does the trade indeed have a leverage of $\lambda=2$ as desired? We invested 44 in the risky asset and 56 in reserve cash. The total portfolio value (PV) is 100 which corresponds to the 100 initially invested. The cost of the zero-coupon bond $F_{t}$ was 78. Leverage can be calculated as follows:  

$$
{\mathrm{Leverage}}={\frac{{\mathrm{risky~asset}}}{{\mathrm{portfolio~value}}-F_{t}}}={\frac{44}{100-78}}=2
$$  

8. As the equity tranche quote changes over the rebalancing periods $t_{1},t_{2},\ldots$ adjust the position dynamically, reducing the exposure to the risky asset as $q_{t}$ increases, and increasing the. exposure as $q_{t}$ decreases.  

Note that during this process the equity tranche position is actually taken as an unfunded invest-. ment. Still, the cash allocated to the risky asset, plus the upfront cash, is held as collateral for the position.  

# 23.5.1.2 Dynamic adjustments  

We can see from Eq. (23.28) that if the value of the risky asset increases or decreases, the leverage is going to change. Let, for example, $q_{t_{1}}=15\%$ , which can be interpreted as perceived risk decreasing (compared to the original value of $q_{t_{1}}=15\%$ , the index tightening, and the quoted price for protection falling. This corresponds to an increase in the value of the iTraxx equity tranche and the value of the risky asset investment. After all, one can buy protection at $15\%$ and close the position with a profit. Yet, with the structured note the position is continued after an adjustment. We cover these steps below.  

1. The value of the risky asset is  

$$
\begin{array}{r l}{N\bigl(1-q_{t_{1}}\bigr)}&{{}=44\times(1-15\%)}\ {}&{{}=46.75}\end{array}
$$  

Due to unrealized gains, the value of the risky asset has gone up by  

$$
R_{t_{1}}-R_{t_{0}}=2.75
$$  

This is the case since we can close the position by buying equity protection at $15\%$ upfront. Then we recover the 44 deposited as collateral for the equity tranche investment, and in addition we receive the realized gain  

$$
55\times0.05=2.75
$$  

by not losing this position, it is as if we are investing 46.75 in the risky asset.  

2. Calculate the $V_{t_{1}}$ using  

$$
V_{t_{1}}=F_{t_{0}}\big(1+L_{t_{0}}\big)+N_{t_{0}}\big(q_{t_{1}}-q_{t_{0}}\big)+N_{t_{0}}\big(1+L_{t_{0}}\big)+N(0.05)
$$  

In this case, this amounts to  

$$
105.095+2.75+(11)(0.05)+55(0.05)
$$  

The first term is the interest on the 100 kept as cash or collateral. The second term is the capital gains from the $q_{t}$ move, the third is the LIBOR earned from the upfront deposit. Finally, the fourth term is the 500 bp running fee on the 55.  

3. What is the effect on leverage? The new leverage can be calculated as follows:  

$$
\mathrm{Leverage}={\frac{\mathrm{risky~asset}}{\mathrm{portfolio~value}-F_{t}}}={\frac{46.75}{102.75-78}}=1.8
$$  

To bring leverage back to the target level of 2, the portfolio needs to be rebalanced. The risky assets have a value of 46.75 and the reserve cash remains at 56. To obtain a leverage of 2 we need risky assets to increase to 49.5. This can be achieved by reallocating 2.75 from reserve cash to risky assets. As a result risky assets increase to 49.5 and reserve cash falls to 53.25. The increase in risky assets is used to buy more units of the iTraxx equity tranche. Since the current new upfront fee $q_{t_{1}}$ is $15\%$ , we can buy an equity notional amount of  

$$
N^{\mathrm{Eq}}=\frac{2}{\left(1-0.15\right)}=2.353
$$  

Since the upfront fee. $q_{t_{1}}$ is $15\%$ , this implies that we receive an upfront payment or fee that can be calculated as follows:  

$$
\begin{array}{r}{\mathrm{fee}=2.353\times(1-q_{t})=2.353\times(1-15\%)=0.353.}\end{array}
$$  

We can verify the cash collateral corresponding to the notional amount $N^{\mathrm{Eq}}$ of the equity tranche.  

Collateral $=$ risky asset cash $^+$ initial upfront cash $+$ additional upfront cash $=49.5+11+0.353=60.853$  

Figure 23.2 illustrates the difference between the value of risky assets, which is 49.5, and the cash allocated to risky assets, which is 46.75. The difference of 2.75 is due to the unrealized capital gains. Here we have assumed that the zero-coupon bond value will remain unchanged, but in reality, changes in the value of the zero-coupon bond and income flows will also affect leverage.  

The opposite adjustment will be implemented if $q_{t_{1}}$ decreases. We leave the details of this case to the end-of-chapter exercises. Instead, we will consider the case of a default.  

![](5e9b62df93ce62e480834f0660c736201521176d747d40a2f32fed68e3e47919.jpg)  

# FIGURE 23.2  

Dynamic adjustment.  

# 23.5.1.3 Default and switching out of CPPI into zero-coupon bond  

What is the liability of the bank that structures the CPPI if the iTraxx portfolio defaults? In the original numerical example, the investor received 100 and placed 56 into reserve cash and 44. into the risky asset. The notional amount of the equity tranche was 55 and it was backed by col-. lateral of 44 in addition to the upfront fee of 11. In the scenario of a default of the iTraxx equity. tranche, the equity tranche value would fall to zero. The structuring bank had bought principal protection for 78 which will be paid out to the purchase of the CPPI product. The principal protection costs the bank 78. Since the equity notional amount of the iTraxx tranch is 55, the bank needs to pay 55 to the counterparty, which implies that the total liability is 133. $(=55+78)$ . In terms of collateral, the bank holds cash of 44 related to the risky asset, reserve cash of 56 and the upfront fee payment of 11. The total cash assets are therefore 111. If we subtract assets from liabilities, we obtain a loss of 22. One possible strategy to avoid such a loss is to reduce the risk before default occurs. For example, if the value of the equity tranche deteriorates as credit quality drops, the portfolio could be switched from the CPPI structure to a zero-coupon bond when the value passes a certain threshold such as falling close to the cost of the zerocoupon bond.  
