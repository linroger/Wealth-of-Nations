---
tags:
  - bond_pricing
  - bsm_model
  - callable_bonds
  - embedded_options
  - european_style_option
aliases:
  - Bank of America bond
  - BoA bonds
  - Embedded call option
key_concepts:
  - BSM pricing approach
  - Callable bond provisions
  - Effective maturity duration
  - Embedded bond call options
  - European-style option pricing
---

# 16.1 EMBEDDED BOND CALL OPTIONS  

There is not much of a market for stand-alone options on bonds, but many corporate bonds include call provisions that give the issuer the right to call or buy back its bonds at some fixed schedule of prices. These provisions are called embedded options, because they do not trade separately or independently of the bonds. In any case, the relevant institutional background. is given in Chapter 14. This section, for purposes of discussion, takes as. an example the Bank of America (BoA) 2.305s of 02/22/2039, which were issued in February 2019. They are callable by BoA on February 22, 2029, at par, or $100\%$ of face value. Table 16.1 lists this bond, along with two others that are used in this section as reference bonds. All three bonds are denominated in euros, and they were issued by banks that, as of the pricing date, are rated A2 by Moody's. Only the BoA bonds, however, are callable..  

TABLE 16.1 Callable Bank of America Bond and Two Reference Noncallable Bonds. All Cash Flows Are Denominated in Euros. Prices Are as of August 23, 2021. Coupons Are in Percent.   


<html><body><table><tr><td>Issuer</td><td>Coupon</td><td>Maturity</td><td>Call Provisions</td><td>Price</td></tr><tr><td>BankofAmerica</td><td>2.305</td><td>02/22/2039</td><td>Callable on 02/22/29@100</td><td>113.296</td></tr><tr><td>DZBank</td><td>0.75</td><td>02/22/2029</td><td>Noncallable</td><td>104.566</td></tr><tr><td>BancoSantander</td><td>2.28</td><td>02/28/2039</td><td>Noncallable</td><td>118.044</td></tr></table></body></html>  

The DZ Bank bonds mature on the date the BoA bonds are callable, and the.   
Banco Santander bonds mature on the same date as the BoA bonds.  

BoA will exercise its call option if rates on the call date are low relative to BoA's cost of funds. For example, if BoA can issue new 10-year debt at $1.75\%$ as of the call date, it will likely call the 2.305s of 02/22/2039 at a price of 100 and raise the funds to do so by selling new, 10-year debt at $1.75\%$ In this way, BoA reduces its interest cost over the subsequent 10 years from $2.305\%$ to $1.75\%$ . On the other hand, if BoA's cost of new 10-year debt is $2.50\%$ on the call date, it will not exercise its option, and it will leave outstanding its 2.305s of 02/22/2039. Return then to Table 16.1. If rates are low as of the pricing date, it is more likely that the BoA bonds will be called in 2029, which is the maturity of the DZ Bank bonds. If, on the other hand, rates are high as of the pricing date, it is less likely that the BoA bonds will be called in 2029, that is, more likely that they will remain outstanding until 2039, which is the maturity of the Banco Santander bonds. Hence, the effective maturity and duration of the BoA bonds changes from that of a 7.5-year bond, when rates are low and the call is very likely to be exercised, to that of a 17.5-year bond, when rates are high and the call is very unlikely to be exercised.  

Because the BoA embedded call is a European-style option, it is partic-. ularly suitable for pricing by BSM.1 More specifically, consider a fictional, noncallable BoA bond with a coupon of. $2.305\%$ and a maturity of February 22, 2039. The embedded call provision is then a call option on that fictional, underlying bond struck at par, and the value of the BoA callable bond equals the value of the underlying bond minus the value of the option. Essentially, bondholders own the underlying noncallable bond and have sold a call option to the issuer to buy that bond at par..  

The BSM approach to pricing the BoA embedded call option is laid out in Table 16.2. Under the assumption that the forward underlying bond price is lognormally distributed, Appendix A16.3 shows that the value of a call on a bond is,  

TABLE 16.2 Pricing the Embedded Call Option of the Bank of America 2.305s of 02/22/2039, as of August 23, 2021.   


<html><body><table><tr><td>Quantity</td><td>Value</td></tr><tr><td>So</td><td>103.732</td></tr><tr><td>T</td><td>7.496</td></tr><tr><td>K</td><td>100</td></tr><tr><td></td><td>5.238%</td></tr><tr><td>do(T)</td><td>0.990</td></tr><tr><td>gLN(So, T,K,α)</td><td>7.877</td></tr><tr><td>VBondCall = do(T)LN(So, T, K,c) 0</td><td>7.797</td></tr><tr><td>Forward Rate:August 2021 to Feb 2029</td><td>0.137%</td></tr><tr><td>Forward Rate:Feb 2029 toFeb 2039</td><td>2.050%</td></tr><tr><td>Spread</td><td>-0.158%</td></tr><tr><td>(Fictional) Noncallable Price</td><td>122.347</td></tr><tr><td>Callable Price</td><td>114.551</td></tr></table></body></html>  

$$
d_{0}(T)\xi^{L N}(S_{0},T,K,\sigma)
$$  

where $d_{0}(T)$ is the discount factor to the option expiration date, $T;S_{0}$ is the forward price of the underlying bond for delivery on date $T;K$ is the strike price; and $\sigma$ is the volatility, which, under the lognormal assumption, is expressed as a percentage of price. The function $\xi^{L N}$ is as given in Appendix A16.4.  

Two of the required inputs of (16.1) are not easily available, namely. the forward price to the call date of the fictional, underlying bond, and the volatility. There are several ways to estimate these missing values, but. Table 16.2 takes the following approach. First, find the two forward rates one from the pricing date to the BoA bond's call date, and one from the call date to the BoA bond's maturity date - that recover the prices of the DZ Bank and Banco Santander reference bonds. Then, using these rates, calculate that the forward price of the underlying BoA bond is 102.29. Second, assume that the relevant volatility is $59.8$ basis points, which is that of an at-the-money (ATM) EUR swaption with an option expiration of. seven years and an underlying tenor of 10 years, which terms are close to that of the embedded call option. Then, convert this basis-point volatility. to a percentage volatility. The DV01 of the underlying forward bond, using the term structure just described, is 0.0896. Therefore, a volatility of 59.8 basis points corresponds to a price volatility of 59.8 times 0.0896, or 5.36, which, in turn, corresponds to a percentage price volatility of 5.36/102.29, or $5.24\%$ . Not surprisingly, pricing the callable bond with this forward. price and volatility does not exactly match the observed market price of 114.551 (including accrued interest). The third and final step, therefore, is to add a spread to the constructed forward rates that recovers the market price of the BoA callable bond. More precisely, for any spread, calculate the price of the underlying bond; calculate the value of the call option; and calculate the value of the callable bond as the difference between those two values. Iterate on the spread until the callable bond value equals its market. price. Through this iteration, by the way, the percentage price volatility is kept constant at the $5.24\%$ calculated previously. In any case, Table 16.2 reports the final numbers. The resulting spread is about minus 16 basis. points, which increases the previously calculated underlying forward price to 103.732, and the resulting option value is 7.797. Within this framework, of course, a trader could calculate the Dv01 of the callable bond, which can be used quantify, manage, or hedge its interest rate risk..  

Figure 16.1 illustrates the interest rate behavior of callable bonds by graphing the prices of the three bonds in Table 16.7 against the yield of the Banco Santander bonds. The start of the pandemic and economic shutdowns is omitted, leaving pre-pandemic data, from April 30, 2019, to February. 28, 2020, and post-pandemic data from May 4, 2020, to September 17, 2021. The Banco Santander and DZ Bank bonds, which are not callable, have price-yield relationships that are close to linear. These curves are actually positively convex, of course, like all fixed-coupon bonds, but the nonlinearities are too small to be seen in the figure. Prices of the DZ Bank. bond are relatively low, because of its low coupon. The price-yield curves. of both the DZ Bank bond and the Banco Santander bond are downward sloping, of course, but the DZ curve is relatively flat, while the Santander. curve is relatively steep, because the former matures in 7.5 years and the. latter in 17.5 years. The price behavior of the callable BoA bond, however, is quite different, as it displays sharp and noticeable negative convexity. At high yield levels, where the likelihood of its being called in the future is low, its price-yield behavior resembles that of the similar-maturity Banco Santander bond. On the other hand, at low yield levels, where the likelihood of its being called in the future is high, its price sensitivity to rates declines: investors are likely to enjoy the now relatively high-coupon of the bond for only another 7.5 years, not for another 17.5 years. Hence, the slope of the BoA bond's price-yield curve flattens and approaches that of the 7.5-year DZ Bank bond. The BoA bonds seem to have experienced a particularly large price drop relative to Banco Santander bonds after the pandemic. This might be a divergence of issuer-specific spreads, or it might be that increased rate volatility increased the value of the embedded call and reduced the price of the callable bond.  

![](dae3b3cd9c0d8bb63791150d319851299cbc19a3062b9b7beecc175224d46f48.jpg)  
FIGURE 16.1 Prices of the Banco Santander 2.28s of 02/28/2039, the Bank of. America 2.305s of 02/22/2039, and the DZ Bank 0.75s of 02/22/2029, Against the Yield of the Santander Bonds. The "Pre-Pandemic" Period Is April 30, 2019, to February 28, 2020, and the "Post-Pandemic Period" Is May 4, 2020, to September 17, 2021. The DZ Bank Bonds Were Issued in February 2021..  

Many callable bonds have more complex call provisions that that of the. BoA bonds. For example, a new 30-year bond with a coupon of. $5\%$ might be callable in 10 years at a price of 102.50, and callable thereafter at prices that decline gradually each year until reaching 100. When this bond is issued, and the first call date is 10 years distant, most of the value of the call is at that first date and the BSM approach described in this section might be perfectly adequate. To elaborate, if the bond is unlikely to be called in 10 years at a. price of 102.50, it is also unlikely to be called in 11 years at a price of, say,. 102.375. Closer to the period over which the call provision is live, however,. its American or Bermudan features can become more important, and the European-style assumption of BSM becomes less suitable. In these situations, it is more appropriate to apply a term structure model along the lines of Chapters 7 through 9:  

1. Create an appropriate risk-neutral tree of short-term rates. In some cases the short-term rate process is designed to price bonds of the issuer selling. the callable bond, but in most cases the process would correspond to a swap or government bond benchmarks. A firm- or bond-specific spread or option-adjusted spread (OAS) would then be added to rates for bond valuations.   
2. Using the risk-neutral tree methodology, calculate the value along the. tree of an otherwise identical, noncallable bond, that is, a noncallable bond with the same scheduled coupon and principal payments as the. callable bond being priced.  

3. Calculate the value along the tree of the call option embedded in the callable bond. Consistent with the well-known methods for pricing. American- or Bermudan-style options along a tree, start from the. maturity date of the option and work backwards, using the rules that i) the value of the option at any node equals the maximum of the value of immediately exercising the option and the value of holding. the option for another period; and ii) the value of holding the option for another period at any node is its expected discounted value in the. risk-neutral tree.  

4. The value of the callable bond equals the value of the otherwise identical noncallable bond minus the value of the option.  

With this valuation procedure in place, other computations are straightforward. Given a market price for the callable bond, an OAS can be computed along the lines of Chapter 7. Also, an option-adjusted duration (OAD) or Dv01 can be calculated by perturbing the short-term rate factor and repeating steps 1 to 4 or, for a metric more similar to yield-based sensitivities, by perturbing the initial term structure and repeating the valuation procedure.  
