---
tags:
  - curve_building
  - hedging
  - interest_rate_swaps
  - pv01
  - swap_markets
aliases:
  - DV01
  - Partial PV01
key_concepts:
  - Curve refitting caveats
  - Hedging with swaps
  - Partial PV01 definition
  - Present value calculation
  - Swap rate curve
---

# 5.5 PARTIAL 'O1S AND PV01  

Interest rate swap trading desks are firmly in the category of market participants that require robust, multi-factor frameworks for hedging. These desks are mostly market makers in swaps, regularly paying fixed to and receiving fixed from customers, while trying to hedge any residual interest rate and curve risk. In order to value these trading books, swap rate curves are constructed to fit or pass through rates of all terms that trade with significant. liquidity. There are typically quite a few of these fitting rates or fitting points, perhaps between 15 to 25, depending on the application and currency. In any case, swap desks often leverage their curve-building machinery to compute $P V O1s$ (i.e., present value of an. $^{\cdot}O1$ ) and partial $^{\bullet}O1s$ or partial PV01s. The term PV01 is standard in swap markets, but it is really a synonym for the general conception of DV01 described in the early sections of Chapter 4. The term is likely preferred so as to differentiate between that general conception and yield-based DV01, which is particularly widespread in bond markets.1  

The PV01 of a portfolio of swaps is found as follows: compute its present value with the current swap rate curve; shift all fitted rates by one basis point; refit the curve; recompute the present value; and subtract one present value from the other. The sign convention for PV01 is the same as for DV01: positive numbers mean that value increases when rates fall.  

A partial $^{\ '}01$ of a portfolio is defined for each rate used to fit the swap curve. To find a partial $^{\ '}01$ with respect to a particular fitted rate, compute the present value of the portfolio with the current swap curve; shift that fitted rate, keeping all other fitted rates the same; refit the curve; recompute the present value; and subtract one present value from the other, again observing the usual sign convention.  

The advantages and caveats of using key-rate $^{\ '}01s$ apply to partial PV01s as well. Partial $^{\circ_{01s}}$ decompose the overall PV01 into exposures to the indi-. vidual fitted swap rates. Hedging is simple by construction: given a portfo-. lio's partial $\mathbf{\nabla}^{\circ}01$ with respect to a particular fitted rate, offset that exposure. by receiving or paying fixed in a swap whose term corresponds to that fitted rate. In this respect, hedging is actually simpler with partial $^{\circ_{1s}}$ than with key-rate $^{\circ_{1s}}$ . Because new, hedging swaps are always at par (see Chapter 2), each partial $^{\ '}01$ can be hedged individually, as in the simplified example of. Table 5.2, where key-rate exposures are hedged with par bonds.  

With respect to caveats, refitting a curve after shifting one fitted swap rate, keeping all other fitted rates the same, can result in oddly shaped term structures of swap rates and even more so, of spot and forward rates. Furthermore, additional problems can arise if the curve-fitting methodology is. not local enough, that is, for example, if shifting the 10-year swap rate, keeping other rates the same, unintentionally moves rates between the fitted five- and seven-year rates. In that case, the present value of a six-year swap would show an unintended sensitivity to the 10-year swap rate, and, even. though five- and seven-year swap rates are included as hedging instruments, the methodology would call for hedging six-year swaps not only with five-. and seven-year swaps, but also with some amount of 10-year swaps. This outcome is fine if intended, but not fine if just an artifact of the curve-fitting methodology. Because the success of using partial $^{\circ_{1s}}$ is very dependent on the properties of the curve fitting methodology, many market participants. are careful to use robust curve fitting methodologies or use forward-bucket $^{\ '}01s$ , which are described in the next section.2  

Before concluding this section, it is noted that the term Cv01 denotes the change in value of a swap for a one-basis-point decrease in its coupon or fixed swap rate. CV01 is particularly easy to compute, because a moment's reflection reveals that it is proportional to the sum of the discount factors. used to discount the fixed payments of the swap. CV01 and PV01 are quite different conceptually, with the former shifting the coupon and the latter. shifting discount rates. The two are sometimes used interchangeably and confused, however, perhaps because they are essentially equal for par swaps,. which constitute the bulk of swaps trading activity.3.  
