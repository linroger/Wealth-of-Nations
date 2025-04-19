---
tags:
  - '#currency_forwards'
  - '#euro_denominated_bonds'
  - '#forwards_futures_contracts'
  - '#fx_forward_contracts'
  - '#no_arbitrage'
  - '#synthetic_instruments'
  - '#synthetic_zero_coupon_bond'
  - '#usd_chf'
---
# 6.1 INTRODUCTION  

Forwards and futures contracts are ideal for creating synthetic instruments for many reasons. Forwards and futures are, in general, linear permitting static replication. They are often very liquid and, in the case of currency forwards, have homogeneous underlying. Many technical complications are automatically eliminated by the homogeneity of a currency. Consider the following interpretation..  

Financial instruments are denominated in different currencies. A market practitioner who needs to perform a required transaction in US dollars (USD) normally uses instruments denoted in USD. In the case of the dollar, this works out fine since there exists a broad range of liquid markets. Market professionals can offer all types of services to their customers using these. On the other. hand, there is a relatively small number of, say, liquid Swiss Franc (CHF) denoted instruments.. Would the Swiss market professionals be deprived of providing the same services to their clients? It turns out that liquid foreign exchange (FX) forward contracts in USD/CHF can, in principle, make USD-denominated instruments available to CHF-based clients as well..  

Instead of performing an operation in CHF, one can first buy and sell USD at. $t_{0}$ and then use a USD-denominated instrument to perform any required operation. Liquid FX forwards permit future USD cash flows to be reconverted into CHF as of time. $t_{0}$ . Thus, entry into and exit from a different. currency is fixed at the initiation of a contract. As long as liquid forward contracts exist, market professionals can use USD-denominated instruments in order to perform operations in any other currency without taking FX risk.  

As an illustration, we provide the following example where a synthetic zero coupon bond is cre ated using an FX forward and the bond markets of another country..  

# EXAMPLE  

Suppose we want to buy, at time $t_{0}$ a USD-denominated default-free discount bond, with maturity at $t_{1}$ and current price $B(t_{0},t_{1})$ . We can do this synthetically using bonds denominated in any other currency, as long as an FX forward exists and the relevant credit risks are the same.  

First, we buy an appropriate number of, say, euro-denominated bonds with the same maturity, default risk, and the pricee $B(t_{0},t_{1})^{\mathrm{EUR}}$ . This requires buying euros against dollarse in the spot market at an exchange rate. $e_{t_{0}}$ . Then, using a forward contract on euro, we sell forward the euros that will be received on December 31, 2015, when the bond matures. The forward exchange rate is $\boldsymbol{F}_{t_{0}}$  

The final outcome is that we pay USD now and receive a known amount of USD at maturity. This should generate the same cash flows as a USD-denominated bond under no-arbitrage conditions. This operation is shown in Figure 6.1.  

![](611bd616d2c349d86ae23d3e92fc10fcccbeb4199c80feae1e544594997305b1.jpg)  

# FIGURE 6.1  

A synthetic USD bond created using an FX forward and a EUR bond.  

In principle, such steps can be duplicated for any (linear) underlying asset, and the ability to execute forward purchases or sales plays a crucial role here..  

Next we discuss the engineering of one of the simplest and most liquid contracts; namely, the currency forward.  
