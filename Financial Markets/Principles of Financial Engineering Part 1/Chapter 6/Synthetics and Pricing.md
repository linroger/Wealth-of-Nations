---
tags:
  - covered_interest_parity
  - currency_forward
  - pricing
  - synthetic_assets
  - t_bills
aliases:
  - CIRP
  - Pricing Formulas
  - Synthetics
key_concepts:
  - Covered interest parity
  - Currency forward equation
  - Replicating portfolio cost
  - Synthetic asset pricing
  - T-bill market pricing
---

# 6.3 SYNTHETICS AND PRICING  

A major use of synthetic assets is in pricing. Everything else being the same, a replicating portfolio must have the same price as the original instrument. Thus, adding up the values of the constituent assets, we can get the cost of forming a replicating portfolio. This will give the price of the original instrument once the market practitioner adds a proper margin.  

In the present context, pricing means obtaining the unknowns in the currency forward, which is. the forward exchange rate, $\boldsymbol{F}_{t_{0}}$ , introduced earlier. We would like to determine a set of pricing. equations which result in closed-form pricing formulas. Let us see how this can be done.  

Begin with Figure 6.2f. This figure implies that the time. $t_{0}$ market values of $C_{t_{0}}^{\mathrm{USD}}$ and $C_{t_{0}}^{\mathrm{EUR}}$ should be the same. Otherwise, one party will not be willing to go through with the deal. This implies  

$$
C_{t_{0}}^{\mathrm{USD}}=C_{t_{0}}^{\mathrm{EUR}}e_{t_{0}}
$$  

where $e_{t_{0}}$ is the spot EUR/USD exchange rate. Replacing from Eqs. (6.1) and (6.2):  

$$
F_{t_{0}}\left[\frac{100}{1+L_{t_{0}}^{\mathrm{USD}}((t_{1}-t_{0})/360)}\right]=\left[\frac{100}{1+L_{t_{0}}^{\mathrm{EUR}}((t_{1}-t_{0})/360)}\right]e_{t_{0}}
$$  

Solving for the forward exchange rate $F_{t0}$  

$$
F_{t_{0}}=e_{t_{0}}\left[\frac{1+L_{t_{0}}^{\mathrm{USD}}((t_{1}-t_{0})/360)}{1+L_{t_{0}}^{\mathrm{EUR}}((t_{1}-t_{0})/360)}\right]
$$  

This is the well-known covered interest rate parity (CIRP) equation. Note that it expresses the "unknown" $F_{t_{0}}$ as a function of variables that can be observed at time $t_{0}$ . Hence, using the market quotes, $F_{t_{0}}$ can be numerically calculated at time $t_{0}$ and does not require any forecasting effort.  

The second synthetic using T-bills gives an alternative pricing equation. Since the values evaluated at the current exchange rate, $e_{t},$ of the two bond positions needs to be the same, we have  

$$
F_{t_{0}}B(t_{0},t_{1})^{\mathrm{USD}}=e_{t_{0}}B(t_{0},t_{1})^{\mathrm{EUR}}
$$  

Hence, the $\boldsymbol{F}_{t_{0}}$ priced off the T-bill markets will be given by  

$$
F_{t_{0}}=e_{t_{0}}\frac{B(t_{0},t_{1})^{\mathrm{EUR}}}{B(t_{0},t_{1})^{\mathrm{USD}}}
$$  

If the bond markets in the two currencies are as liquid as the corresponding deposits and loans, and if there is no credit risk, the. $F_{t_{0}}$ obtained from this synthetic will be very close to the. $\boldsymbol{F}_{t_{0}}$ obtained from deposits.'  
