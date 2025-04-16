---
tags:
  - '#european_options'
  - '#liquidity_problems'
  - '#option_portfolios'
  - '#pure_volatility_positions'
  - '#smile_effect'
  - '#strike_price'
  - '#synthetic_instruments'
  - '#vega_sensitivity'
  - '#volatility_risk_hedging'
---
# 15.4 PURE VOLATILITY POSITIONS  

The key to finding the right way to hedge volatility risk or to take positions in it is to isolate the "volatility"' completely, using existing liquid instruments. In other words, we have to construct a synthetic such that the value of the synthetic changes only when "volatility" changes. This position should not be sensitive to variations in variables other than the underlying volatility. The exposure should be invariant. Then, we can use the synthetic to take volatility exposures or to hedge volatility risk. Such volatility instruments can be quite useful.  

First, we know from Chapters 12 and 13 that by using options with different strikes we can essentially create any payoff that we like-if options with a broad range of strikes exist and if markets are complete. Thus, we should, in principle, be able to create pure volatility instruments by using judiciously selected option portfolios..  

![](images/bcd5e284bad6082c08783036fa601e138279961fb2321234d6e1c792e48fe5d9.jpg)  

# FIGURE 15.6  

Vega of three plain vanilla European call options.  

Second, if an option position's vega drops suddenly once. $S_{t}$ moves away from the strike, then,. by combining options of different strikes appropriately, we may be able to obtain a portfolio of options whose vega is more or less insensitive to movements in. $S_{t}$ . Heuristically speaking, we can. put together small portions of smooth curves to get a desired horizontal line..  

When we follow these steps, we can create pure volatility instruments. Consider the plot of the vega of three plain vanilla European call options, two of which are out-of-the-money. The options are identical in all respects, except for their strike. Figure 15.6 shows an example. Three $\sigma^{2}$ sensitivity factors for the strikes $K_{0}=100$ $K_{1}=110$ $K_{2}=120$ are plotted. Note that each variance vega is very sensitive to movements in $S_{t}$ , as discussed earlier. Now, what happens when we consider the portfolio made of the sum of all three calls? The sensitivity of the portfolio,  

$$
V(S_{t},t)=\{C(S_{t},t,K_{0})+C(S_{t},t,K_{1})+C(S_{t},t,K_{2})\}
$$  

again varies as $S_{t}$ changes, but less. So, the direction taken is correct except that the previous portfolio did not optimally combine the three options. In fact, according to Figure 15.6, we should have combined the options by using different weights that depend on their respective strike price. The more out-of-the-money the option is, the higher should be its weight, and the more it should be present in the portfolio.  

Hence, consider the new portfolio where the weights are inversely proportional to the square of the strike $K$  

$$
V(S_{t},t)=\frac{1}{K_{0}^{2}}C(S_{t},t,K_{0})+\frac{1}{K_{1}^{2}}C(S_{t},t,K_{1})+\frac{1}{K_{2}^{2}}C(S_{t},t,K_{2})
$$  

![](images/68e9db1b8941c79aee8e7e3f508893b8cd5676a07e5125c878d190e8d8210855.jpg)  
Variance vega of a portfolio of options with weights inversely proportional to the square of the strike price.  

# FIGURE 15.7  

The variance vega of this portfolio that uses the parameter values given earlier, is plotted in Figure 15.7. Here, we consider a suitable. $0<\in$ , and the range  

$$
K_{0}-\in<S_{t}<K_{2}+\in
$$  

Figure 15.7 shows that the vega of the portfolio is approximately constant over this range when $S_{t}$ changes. This suggests that more options with different strikes can be added to the portfolio, weighting them by the corresponding strike prices. In the example below we show these calculations.  

# EXAMPLE  

Consider the portfolio  

$$
V(S_{t},t)=\left[\frac{1}{80^{2}}C(S_{t},t,80)+\frac{1}{90^{2}}C(S_{t},t,90)+\frac{1}{100^{2}}C(S_{t},t,100)\right.
$$  

$$
\left.+\frac{1}{110^{2}}C(S_{t},t,110)+\frac{1}{120^{2}}C(S_{t},t,120)\right]
$$  

This portfolio has an approximately constant vega for the range  

$$
80-\in{<S}_{t}<120+\in
$$  

By including additional options with different strikes in a similar fashion, we can lengthen this section further.  

We have, in fact, found a way to create synthetics for volatility positions using a portfolio of liquid options with varying strikes, where the portfolio options are weighted by their respective strikes.  

# 15.4.1 PRACTICAL ISSUES  

In our attempt to obtain a pure volatility instrument, we have essentially followed the same strategy that we have been using all along. We constructed a synthetic. But this time, instead of matching the cash flows of an instrument, the synthetic had the purpose of matching a particular sensitivity factor. It was put together so as to have a constant (variance) vega.  

Once a constant vega portfolio is found, the payoff of this portfolio can be expressed as an approximately linear function of. $\sigma^{2}$  

$$
V(\sigma^{2})=a_{0}+a_{1}\sigma^{2}+\mathrm{small}
$$  

with  

$$
a_{1}={\frac{\partial V(\sigma^{2},t)}{\partial\sigma^{2}}}
$$  

as long as $S_{t}$ stays within the range  

$$
S^{\operatorname*{min}}=K_{0}<S_{t}<K_{n}=S^{\operatorname*{max}}
$$  

Under these conditions, the volatility position will look like any other long (or short) position, with a positive slope $a_{1}$  

The portfolio with a constant (variance) vega can be constructed using vanilla European calls. and puts. The rules concerning synthetics discussed earlier apply here also. It is important that ele-. ments of the synthetic be liquid; therefore, liquid calls and puts have to be selected. The previous discussion referred only to calls. Practical applications of the procedure involve puts as well. This. brings us to two somewhat complicated issues. The first has to do with the smile effect. The second concerns liquidity.  

# 15.4.1.1 The smile effect  

Suppose we form a portfolio at time $t_{0}$ that has a constant vega as long as $S_{t}$ stays in a reasonable. range  

$$
S^{\operatorname*{min}}<S_{t}<S^{\operatorname*{max}}
$$  

Under these conditions, the portfolio consists of options with different "moneyness" properties, and the volatility parameter in the option pricing formulas may depend on $K$ if there is a volatility  

smile. In general, as $K$ decreases, the implied $\sigma(K)$ would increase for constant $S_{t}$ Under these conditions, the trader needs to accurately determine the smile and the way to model it before the portfolio is formed.  

# 15.4.1.2 Liquidity problems  

From the preceding it follows that we need to select out-of-the-money options for the synthetic since they are more liquid. But as time passes, the moneyness of these options changes and this affects their liquidity. Those options that become in-the-money are now less liquid. Other options that were not originally included in the synthetic become more liquid. Even though the replicating portfolio was static, the illiquidity of the constituent options may become a drawback in case the position needs to be unwound.  
