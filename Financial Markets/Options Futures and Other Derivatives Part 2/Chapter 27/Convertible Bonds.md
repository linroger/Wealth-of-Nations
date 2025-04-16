---
tags:
  - '#binomial_tree'
  - '#bond_call_feature'
  - '#bond_valuation'
  - '#convertible_bonds'
  - '#credit_risk'
  - '#default_probability'
  - '#geometric_brownian_motion'
  - '#risk_neutral_hazard_rate'
  - '#stock_price_modeling'
---
# 27.4 CONVERTIBLE BONDS  

We now move on to discuss how the numerical procedures presented in Chapter 21 can be modified to handle particular valuation problems. We start by considering convertible bonds.  

Convertible bonds are bonds issued by a company where the holder has the option to exchange the bonds for the company's stock at certain times in the future. The conversion ratio is the number of shares of stock obtained for one bond (this can be a function of time). The bonds are almost always callable (i.e., the issuer has the right to buy them back at certain times at a predetermined prices). The holder always has the right to convert the bond once it has been called. The call feature is therefore usually a way of forcing conversion earlier than the holder would otherwise choose. Sometimes the holder's call option is conditional on the price of the company's stock being above a certain level.  

Credit risk plays an important role in the valuation of convertibles. If credit risk is ignored, poor prices are obtained because the coupons and principal payments on the bond are overvalued. Ingersoll provides a way of valuing convertibles using a model similar to Merton's (1974) model discussed in Section 24.6.21 He assumes geometric. Brownian motion for the issuer's total assets and models the company's equity, its. convertible debt, and its other debt as claims contingent on the value of the assets. Credit risk is taken into account because the debt holders get repaid in full only if the value of the assets exceeds the amount owing to them..  

A simpler model that is widely used in practice involves modeling the issuer's stock price. It is assumed that the stock follows geometric Brownian motion except that there is a probability $\lambda\Delta t$ that there will be a default in each short period of time $\Delta t$ . In the event of a default the stock price falls to zero and there is a recovery on the bond. The variable $\lambda$ is the risk-neutral hazard rate defined in Section 24.2.  

The stock price process can be represented by varying the usual binomial tree so that at each node there is:  

1. A probability $p_{u}$ of a percentage up movement of size $u$ over the next time period of length $\Delta t$   
2. A probability $p_{d}$ of a percentage down movement of size $d$ over the next time period of length $\Delta t$   
3. A probability $\lambda\Delta t$ or more accurately $1-e^{-\lambda\Delta t}$ , that there will be a default with the stock price moving to zero over the next time period of length $\Delta t$  

Assume that $\sigma$ is the volatility of the stock price conditional on no default and $p_{\mathrm{def}}$ is the probability of default. Parameter values that match $\sigma$ and give an overall expected return for the stock of $r-q$ are:  

$$
p_{u}=\frac{a-d e^{-\lambda\Delta t}}{u-d},p_{d}=\frac{u e^{-\lambda\Delta t}-a}{u-d},p_{\mathrm{def}}=1-e^{-\lambda\Delta t},u=e^{\sigma\sqrt{\Delta t}},d=\frac{1}{u-d},
$$  

where $a=e^{(r-q)\Delta t}$ $r$ is the risk-free rate, and. $q$ is the dividend yield on the stock.  

The life of the tree is set equal to the life of the convertible bond. The value of the convertible at the final nodes of the tree is calculated based on any conversion options that the holder has at that time. We then roll back through the tree. At nodes where the terms of the instrument allow conversion we test whether conversion is optimal. We also test whether the position of the issuer can be improved by calling the bonds. If so, we assume that the bonds are called and retest whether conversion is optimal.  

# Example 27.1  

Consider a 9-month zero-coupon bond issued by company XYZ with a face value of $\$100$ . Suppose that it can be exchanged for two shares of company XYZ's stock at any time during the 9 months. Assume also that it is callable for $\$113$ at any time. The initial stock price is $\$50$ , its volatility is $30\%$ per annum, and there are no dividends. The hazard rate $\lambda$ is $1\%$ per year, and all risk-free rates for all maturities are $5\%$ . Suppose that in the event of a default the bond is worth $\$40$ (i.e., the recovery rate, as it is usually defined, is. $40\%$  

![](ed5b69837ff71918c0a33b8523d5ee363a44611b9027685d1bd0f66f017d2a03.jpg)  
Figure 27.2 Tree for valuing convertible. Upper number at each node is stock price; lower number is convertible bond price..  

Figure 27.2 shows the stock price tree that can be used to value the convertible when there are three time steps ( $\Delta t=0.25$ ). The upper number at each node is the stock price; the lower number is the price of the convertible bond. The tree parameters are:  

$$
{\begin{array}{c}{u=e^{0.3{\sqrt{0.25}}}=1.1618,d=1/u=0.8607}\ {a=e^{0.05\times0.25}=1.0126,p_{u}=0.5115,p_{d}=0.4860,p_{\mathrm{def}}=0.0025}\end{array}}
$$  

At the three default nodes the stock price is zero and the bond price is 40.  

Consider first the final nodes. At nodes G and H the bond should be converted and is worth twice the stock price. At nodes I and. $\mathbf{J}$ the bond should not be. converted and is worth 100.  

Moving back through the tree enables the value to be calculated at earlier nodes. Consider, for example, node E. The value, if the bond is converted, is $2\times50=\$100.$ If it is not converted, then there is (a) a probability 0.5115 that it will move to node H, where the bond is worth 116.18, (b) a 0.4860 probability that it will move down to node I, where the bond is worth 100, and (c) a 0.0025 probability that it will default and be worth 40. The value of the bond if it is not converted is therefore  

$$
(0.5115\times116.18+0.4860\times100+0.0025\times40)\times e^{-0.05\times0.25}=106.78
$$  

This is more than the value of 100 that it would have if converted. We deduce that. it is not worth converting the bond at node E. Finally, we note that the bond issuer would not call the bond at node E because this would be offering 113 for a bond worth 106.78.  

As another example consider node B. The value of the bond if it is converted is $2\times58.09=116.18$ If it is not converted a similar calculation to that just given. for node E gives its value as 119.54. The convertible bond holder will therefore. choose not to convert. However, at this stage the bond issuer will call the bond for 113 and the bond holder will then decide that converting is better than being. called. The value of the bond at node B is therefore 116.18. A similar argument is used to arrive at the value at node D. With no conversion the value is 135.08. However, the bond is called, forcing conversion and reducing the value at the. node to 134.99.  

The value of the convertible is its value at the initial node A, or 107.44.  

When interest is paid on the debt, it must be taken into account. At each node, when valuing the bond on the assumption that it is not converted, the present value of any interest payable on the bond in the next time step should be included. The risk-neutral hazard rate $\lambda$ can be estimated from either bond prices or credit default swap spreads. In a more general implementation,. $\lambda,\sigma$ and $r$ are functions of time. This can be. handled using a trinomial rather than a binomial tree (see Section 21.4).  

One disadvantage of the model we have presented is that the probability of default is independent of the stock price. This has led some researchers to suggest an implicit finite difference method implementation of the model where the hazard rate $\lambda$ is a function of the stock price as well as time.22  
