---
tags:
  - bond_valuation
  - coupon_bond
  - default_probability
  - no_arbitrage
  - treasury_notes
aliases:
  - ABC Corp Bond
  - Constant Default Model
key_concepts:
  - Bond valuation
  - Constant default probability
  - Coupon payment
  - Cumulative survival probability
  - Default-free yield curve
---

# 7.2 A CONSTANT DEFAULT PROBABILITY MODEL  

Suppose we want to price a 3-year $5\%$ annual coupon bond issued by the ABC Corp. ABC is a US corporation and the bond's principal and interest are to be paid in US dollars. We observe. that 1-, 2-, and 3-year US Treasury notes with coupon rates equal to $2.500000\%$ $2.623305\%$ and $2.745279\%$ , respectively, trade at par. For simplicity, we assume annual 30/360 interest. calculations. From the Treasury par curve, using the techniques of Chapter 2, we bootstrap the following default-free term structure of interest rates in Table 7.1..  

Table 7.1 Default-free yield curve   


<html><body><table><tr><td>Year</td><td>Forward yield</td><td>Year</td><td>Zero-coupon yield</td><td>Year</td><td>Par coupon yield</td></tr><tr><td>0×1</td><td>2.50</td><td>0×1</td><td>2.500000</td><td>1</td><td>2.500000</td></tr><tr><td>1×2</td><td>2.75</td><td>0×2</td><td>2.624924</td><td>2</td><td>2.623305</td></tr><tr><td>2×3</td><td>3.00</td><td>0×3</td><td>2.749797</td><td>3</td><td>2.745279</td></tr></table></body></html>  

The usual Bond Math no-arbitrage relationships apply to the computed zero-coupon yields which discount cash flows from a point in the future to today and to the computed forward (zero) yields which discount cash flows one year at a time.  

Suppose we assume that the probability that ABC will go bankrupt or default on its bond over the first year is. $0.0011=0.11\%.$ If ABC goes bankrupt during the first year, then not only will it not pay the. $5\%$ coupon due in 1 year, but it will also fail to pay any coupons after that.. For now, we assume no recovery of any value following the default. If ABC survives the first year, then the probability that it will go bankrupt in the second year will again be $0.11\%$ . If ABC fails in year 2, then it will fail to pay the coupon in year 2 and the coupon and principal. in year 3. If it survives year 2, then it will again face the probability of default of. $0.11\%$ for year 3.  

Rather than thinking about the probability of default, it helps to think in terms of the. probability of survival. The constant default probability model is then the same as the constant survival model. Since we assume a Bernoulli (binomial) set-up with only two possibilities -- default or survival - the survival probability is equal to 1 minus the default probability. For. each year, we set the survival probability to a constant 0.9989. Figure 7.5 captures the evolution of outcomes over time. The tree is truncated in the down states since, if there is default, the subsequent cash flows are zero.  

One way to price the ABC bond would be to sweep backwards through the tree, adding the coupon cash flows at every step. We would start at time $t=2$ . We would take the discounted expected value of the cash flows at time $t=3$ and add the current cash flow. That is, at time $t=2$ , right after the coupon payment, the bond would have a value of:  

$$
B_{2}=\frac{1}{1+0.0300}\left[0.9989\times\left(\mathbb{S}100.0000+\mathbb{S}5\right)+0.0011\times\mathbb{S}0\right]=101.8296
$$  

![](e25d86f9480a228f8bf97974342352af8e38487b663ec9ce373281c785f554a2.jpg)  
Figure 7.5 Constant probability of default  

Table 7.2 Bond valuation using the cumulative survival probability   


<html><body><table><tr><td>Year</td><td>CF</td><td>Prob/Year</td><td>Cumulative survival prob.</td><td>Risk-free zero rate</td><td>Risk-free DF</td><td>PV</td></tr><tr><td>1</td><td>5</td><td>0.0011</td><td>0.99890</td><td>2.5000%</td><td>0.975610</td><td>4.8727</td></tr><tr><td>2</td><td>5</td><td>0.0011</td><td>0.99780</td><td>2.6249%</td><td>0.949499</td><td>4.7371</td></tr><tr><td>3</td><td>105</td><td>0.0011</td><td>0.99670</td><td>2.7498%</td><td>0.921843</td><td>96.4745</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>SumPV=</td><td>106.0842</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>Yield =</td><td>2.8550%</td></tr></table></body></html>  

At time $t=1$ , right after the coupon payment, the bond would have a value of:  

$$
B_{1}=\frac{1}{1+0.0275}\left[0.9989\times\left(\mathbb{S}101.8296+\mathbb{S}5\right)+0.0011\times\mathbb{S}0\right]=103.8561
$$  

Finally, at time $t=0$ , we would compute the price of the bond as the probability-weighted present value of the bond's cash flows, equal to.  

$$
B_{0}=\frac{1}{1+0.0250}\left[0.9989\times\left(\mathbb{S}103.8561+\mathbb{S}5\right)+0.0011\times\mathbb{S}0\right]=106.0842
$$  

There is a simpler way. Since the tree is truncated in the down nodes, all we have to worry about is the cumulative survival probability up to any given time (or year) $n$ , which is equal to $0.9989^{n}$ . What follows is that the expected present value of any coupon payment is equal to the cumulative survival probability times the promised cash flow times a discount factor, where. the discount factor is computed using default-free rates. In the backward sweep, we used the. one-step default-free forward rates, but since each cash flow is discounted to today, we can. simply use the spot discount factors based on spot zero rates. These simplified calculations are:  

$$
B_{0}={\frac{0.9989\times{\bar{\mathrm{\mathbb{S}}}}5}{1.02500000}}+{\frac{0.9989^{2}\times{\bar{\mathrm{\mathbb{S}}}}5}{1.02624924^{2}}}+{\frac{0.9989^{3}\times{\bar{\mathrm{\mathbb{S}}}}105}{1.02749797^{3}}}=106.0842
$$  

as summarized in Table 7.2.  

Table 7.2 also shows the yield to maturity on the ABC bond implied from the formula:  

$$
\frac{\mathbb{S}\mathbb{S}}{1+y}+\frac{\mathbb{S}\mathbb{S}}{(1+y)^{2}}+\frac{\mathbb{S}105}{(1+y)^{3}}=106.0842
$$  

which turns out to be 2.855. Given the risk-free par coupon rate of $2.745\%$ for a 3-yeal maturity, the corporate credit spread on the ABC bond would be quoted as 11 bp.  

We use our simple default valuation method to compute, in Table 7.3, what would happen to the same 3-year $5\%$ ABC bond if ABC drops to a "junk" rating as the perceived probability. of default changes to $10\%$ per year.  

The promised cash flows do not change, but their probability-weighted discounted value. does. The price of the bond drops to 78.7982, and the yield-to-maturity increases to $14.156\%$ The credit spread is now $11.411\%$ over the same maturity Treasury.  

The deterministic default probability model is easy to calibrate. Just as in a standard yield curve construction, we need to observe the default-free yield curve and an array of bonds of the same issuer with increasing maturities. We can then bootstrap the implied probability of default for each forward period starting with 6-month or 1-year bonds and ending with the longest maturity bonds. Once that is done, we can use the term structure of default probabilities to price any cash flow structure offered by the same issuer..  

Table 7.3 The ABC bond with a $10\%$ default probability   


<html><body><table><tr><td>Year</td><td>CF</td><td>Prob/Year</td><td>Cumulative survival prob</td><td>Risk-free zero rate</td><td>Risk-free DF</td><td>PV</td></tr><tr><td>1</td><td>5</td><td>0.1000</td><td>0.90000</td><td>2.5000%</td><td>0.975610</td><td>4.3902</td></tr><tr><td>2</td><td>5</td><td>0.1000</td><td>0.81000</td><td>2.6249%</td><td>0.949499</td><td>3.8455</td></tr><tr><td>3</td><td>105</td><td>0.1000</td><td>0.72900</td><td>2.7498%</td><td>0.921843</td><td>70.5625</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>SumPV=</td><td>78.7982</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>Yield =</td><td>14.1562%</td></tr></table></body></html>  
