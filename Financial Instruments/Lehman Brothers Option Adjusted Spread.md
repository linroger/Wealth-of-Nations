---
tags:
  - corporate_bond
  - credit_risk
  - lehman_brothers
  - option_adjusted_spread
  - z_spread
aliases:
  - Lehman Brothers OAS
  - OAS
key_concepts:
  - Callable corporate bond
  - Discounted cash flow
  - Treasury and LIBOR curves
  - Z-spread of security
  - Zero-coupon interest rates
---

# Fixed Income Quantitative Credit Research  

February 27, 2006  

# Explaining the Lehman Brothers Option Adjusted Spread of a Corporate Bond  

Claus M. Pedersen  

![](91874e980878dda14b7bf94ac44ba282cd6bcf677f56f2ae1d3a7d63c104e61b.jpg)  

# LEHMAN BROTHERS  

# Explaining the Lehman Brothers Option Adjusted Spread of a Corporate Bond  

Claus M. Pedersen 212-526-7775 cmpeders@lehman.com  

The option adjusted spread (OAs) is a measure of the credit risk in a callable (or putable) corporate bond and has been used by investors for years. We explain what the OAS is and how it is related to the Z-spread. We present the model used at Lehman Brothers to calculate OAS and associated risk measures, e.g. option adjusted duration and convexity. LehmanLive users can access the model through the Corporate Bond Calculator (keyword: ccalc). The OAS and the risk measures for all bonds in the Lehman Brothers Corporate and High Yield Indices are also reported in POINT, where they are used for various analyses'.  

# 1. INTRODUCTION  

This article has been written:  

as a response to numerous inquiries about how the OAS of a corporate bond is calculated at Lehman Brothers,   
to explain recent changes to our OAS model, and   
to explain the limitations of OAS as a credit spread measure and suggest a better one.  

In the rest of this introductory section we give an overview of what an OAS is and how it is related to a Z-spread.  

# We value a fixed income security by discounting cash flow  

The value of a fixed income security is usually thought of as the sum of its discounted. payments. Usually we discount payments scheduled for different dates with different interest rates, the so-called the zero-coupon interest rates. For example, we will discount a payment scheduled to be made five years from today with the 5-year zero-coupon interest rate,. whereas a payment scheduled to be made ten years from today will be discounted with the 10-year zero-coupon interest rate.  

# The Treasury and LlBOR curves are the two discount curves used most often  

To value a particular fixed income security we must first decide which curve of zero-coupon interest rates to use for the discounting. The two curves most often used are the government (or Treasury) and LIBOR curves. Axel and Vankudre (1997) explain how to find the curve of zero-coupon Treasury interest rates, and Zhou (2002) explains how to find the curve of zerocoupon LIBOR interest rates.  

# The Z-spread of a Treasury security  

If we value a Treasury security by discounting its payments with the zero-coupon Treasury. rates, we usually get a value very close to the observed market price of the bond. However, it is generally not possible to find a curve of zero-coupon Treasury rates so that for any. Treasury security the observed market price exactly matches the value found by discounting. the payments with those zero-coupon Treasury rates. To quantify how different the. discounted value and the market price are for a particular security, we can ask how much we need to change (or shift) the zero-coupon rates for the discounted value to equal the market. price. The required shift to the zero-coupon interest rates is called the. $Z$ -spread of the security. The market convention is to use a parallel shift where all zero-coupon rates are.  

increased (or decreased) by the same (absolute) amount. For a Treasury security, the Z-. spread is a relative value measure where a positive Z-spread indicates that the security is. cheap and a negative Z-spread indicates that the security is rich compared with other Treasury securities.  

# The Z-spread to Treasuries for corporate bonds  

We can calculate a Z-spread for a corporate bond exactly as we do for a Treasury security by simply treating the corporate bond as if it were a Treasury security with given fixed payments (that is, ignoring the fact that the corporate bond may default). We thus calculate the Z-spread to Treasuries for the corporate bond. Because of the credit risk, the Z-spread to Treasuries for a corporate bond will be positive. This reflects the fact that the corporate bond is worth less than a Treasury bond with the same maturity and coupon. The higher the credit risk the higher the Z-spread to Treasuries.  

# Z-spread to LIBOR is a better credit risk measure for corporate bonds  

For a corporate bond it is often more meaningful to calculate a. $Z$ -spread to LIBOR rather than to Treasuries. It is often argued that LIBOR rates are close to (credit) risk-free and that it is the liquidity and "safe haven"' benefits of Treasuries that cause Treasury rates to be lower than LIBOR rates. Since most corporate bonds do not have those benefits to the same extent as Treasuries, a Z-spread to LIBOR is likely to reflect more accurately the credit risk in a corporate bond. A Z-spread to LIBOR is calculated the same way as a. $Z$ spread to Treasuries, that is by determining how much the curve of zero-coupon LIBOR rates must be shifted to ensure that when we sum the value of the bond's discounted payments we get the. observed market price of the bond. For a corporate bond, the market convention is simply to call the Z-spread to LIBOR the Z-spread without emphasising that it is a spread to LIBOR.  

# The Z-spread is not appropriate for callable bonds  

For bonds with embedded options, such as callable bonds, the Z-spread is often not meaningful. This is because it is usually not appropriate to value a callable bond simply by discounting its scheduled payments. To value a callable bond properly we need to use a model that explicitly takes into account volatility in interest rates so that the risk of the bond being called can be taken into account. We therefore use a stochastic term structure model.  

# Using a stochastic term structure model to calculate OAS of a callable bond  

A stochastic term structure model takes as input a curve of zero-coupon interest rates and some parameters determining the volatility of these interest rates. From these inputs the model effectively generates a large number of possible scenarios for future interest rates'. A security is valued by first discounting the cash flow/payments of the security in each scenario separately using the interest rates of that scenario (taking into account when the option is exercised in that scenario) and then averaging over all the scenarios. We can also think of this as the model generating a zero-coupon interest rate curve in each scenario which is used for discounting the cash flow in that scenario. The idea behind the OAS is now easy to explain and is exactly the same as the idea behind the Z-spread: The OAS is simply the constant (absolute) shift to the zero-coupon interest rates in all scenarios that is required to ensure that the model value (the average value over all scenarios) of the bond equals the market price.  

For bonds without embedded options, the OAS is exactly the same as the Z-spread (when adjusting for daycount and compounding conventions; see below). This is because: (1) without embedded options the bond has the same cash flow in all scenarios; and (2) the average over all scenarios of the discount factors to a given maturity equals the discount factor to that maturity calculated from the observed zero-coupon interest rate to that maturity (this is a condition we always ensure is satisfied for a stochastic term structure model)..  

For several years Lehman Brothers has used a Black and Karasinsky (1991) stochastic term structure model for corporate bond OAS computations. Recently we have examined that. particular model choice and its implementation and made some changes. The most. significant change is that we have incorporated a shift to the lognormal Black-Karasinsky dynamics to better fit the skew observed in the volatilities implied from prices of interest rate swaptions with different strikes (see Zhou (2003) for an explanation of the volatility skew)..  

# Outline of remaining sections  

The rest of this article is divided into five sections. In section 2 we explain how the Z-spread is computed and its relationship to a CDS spread. In section 3 we discuss the special considerations that must be made for bonds with embedded options and give a more detailed explanation of what the OAS is and the assumptions on which it is based. In section 4 we explain the stochastic term structure model that we use for OAS calculations. In section 5 we show numerical results from our volatility calibration and explain the effects of the recent model change on OAS for individual bonds. Section 6 gives a brief discussion of the issues we face if we want to improve upon the OAS and calculate a credit spread that better captures default risk. There is a summary in section 7.  

# 2. THE Z-SPREAD: DISCOUNTING CASH FLOW  

In the introduction we explained what the $Z$ spread is. In this section we repeat that description, providing details and formulas..  

Consider a bond that has $_{\mathrm{N}>0}$ remaining payments to be paid at times $\mathrm{{t}_{i},}$ $\mathrm{i}{=}1$ , .., N. Let. $\mathrm{C}_{1}$   
denote the size of the payment (in dollars) scheduled for time $\mathrm{{t}_{i}}$ Finally, let r(t) denote the.   
continuously compounded zero-coupon rate for discounting to time t.  

The discounted value of the of the bond payments is:  

$$
\mathrm{exp(-r(t_{1})t_{1})C_{1}}+\ldots+\mathrm{exp(-r(t_{N})t_{N})C_{N}}
$$  

The payment times, $\tan$ ..., tn, are measured in years by taking the actual number of days.   
from the valuation date to the payment date and dividing by 365.25.  

The value in (2.1) will generally be different from the market price of the bond. The continuously compounded $Z$ spread is the constant $\mathrm{^z}$ that solves the equation:  

$$
\mathrm{Market~Price}=\exp(-(\mathrm{r(t_{l})}+\mathrm{z)t_{l}){\cal C}_{1}+\dots+\exp(-(\mathrm{r(t_{N})}+\mathrm{z)t_{N})}{\cal C}_{N}}
$$  

where Market Price is the full (dirty) price of the bond that includes accrued interest'. Notice that two conventions have been used: continuous compounding and actual/365.25 daycount.  

The market standard for quoting a. $Z$ -spread is to use the conventions of the bond (semi-. annual compounding (in US) with 30/360 daycount). With simple compounding, equation (2.2) becomes:  

$$
\mathrm{Market~Price}=\frac{\mathbf{C}_{1}}{\left(1+\Delta(\mathrm{R}(\mathrm{T}_{1})+Z)\right)^{\mathrm{T}_{1}/\Delta}}+\ldots+\frac{\mathbf{C}_{\mathrm{N}}}{\left(1+\Delta(\mathrm{R}(\mathrm{T}_{\mathrm{N}})+Z)\right)^{\mathrm{T}_{\mathrm{N}}/\Delta}}
$$  

where $\Delta=0.5$ for semi-annual compounding, $\mathrm{T}_{1}$ ..., $\mathrm{T}_{\mathrm{N}}$ are the payment times measured in years using the 30/360 bond daycount convention, and the interest rates $\mathrm{R(T_{1})}$ ,..., $\mathrm{R(T_{N})}$ are related to the continuously compounded rates by:  

$$
\mathrm{exp}\big(\mathrm{r(t_{i})t_{i}}\big){=}\big(1+\Delta\mathrm{R(T_{i})}\big)^{\mathrm{T_{i}/\Delta}}
$$  

# The Z-spread is a more detailed measure than a standard yield spread  

The $Z$ -spread is only one of many different credit spreads used for corporate bonds. The simplest credit spread is the quoted yield spread, which is used by traders of investmentgrade corporate bonds to quote prices. The quoted yield spread is simply the standard yield of the bond minus the yield of a benchmark Treasury security with a similar maturity. The advantage of quoting a spread rather than the price is that the quote will not have to be continuously updated as Treasury yields change.  

It is important to recognize the limitations of the yield spread and the additional detail provided by the $Z\cdot$ spread. The yield spread should always be seen as simply a quoting. convention and should usually be avoided for analysis.  

The main advantage of the Z-spread is that it uses the full information contained in the curve of zero-coupon interest rates. In the $Z$ -spread calculation, cash flows are discounted with a different interest rate depending on the timing of the cash flow. In the yield spread, all cash flows are discounted with the same rate. This means that the yield spread is not detailed enough to properly compare two bonds with different coupons even if the maturities (or durations) are similar. The more the interest rate curve deviates from a flat curve, the more important it becomes to use the Z-spread instead of the yield spread. See O'Kane and Sen (2004) for details (and for explanations of other types of credit spreads).  

# Comparing the Z-spread with a CDS spread  

It is not uncommon to see comparisons between the Z-spread of a bond and a credit default swap (CDS) spread. It is important to be cautious about such a comparison and be aware of the differences between these two types of credit spreads.  

The first obvious differences between a $Z$ -spread and a CDS spread are the daycount and compounding conventions. A CDS spread is based on quarterly compounding' with actual/360 daycount, whereas the $Z$ spread is based on semi-annual compounding (in US) with 30/360 daycount.  

The most important difference is that the CDS spread has a transactional interpretation: An investor is paid a running premium equal to the CDS spread for taking the risk of losing one. minus the recovery rate if default occurs. The Z-spread, by contrast, is not a spread/premium. that can be locked in today for taking certain risks. The Z-spread is the excess return that can be earned from buying the bond and holding it to maturity, assuming the issuer does not. default and that coupons can be reinvested at forward LIBOR rates plus the Z-spread..  

CDS are usually valued and analyzed in a hazard rate model which takes as inputs a curve of. CDS spreads, a LIBOR curve, and a recovery rate. Based on these inputs, the hazard rate. model calibrates a curve of survival probabilities using a standard method explained in O'Kane and Turnbull (2003). Based on the survival probabilities, the zero-coupon interest. rates and the recovery rate, it is easy to price default contingent contracts such as CDS. We can also use the model to price a bond and ask the following question: if we were to price a bond using survival probabilities calibrated to a flat CDS spread curve, what spread would be needed to match the observed bond price? We could call the answer a bond-implied CDS spread. This type of bond spread is directly comparable to a CDS spread and we prefer it to the Z-spread.  

A bond implied CDS spread based on a flat CDS curve implies (approximately) a constant. hazard rate (the hazard rate is the instantaneous probability of default; see O'Kane and Turnbull, 2003). With a constant hazard rate we have another approximate relationship:.  

(2.5) $\mathrm{{CDS~Spread}\approx H a z a r d~R a t e\cdot(1-R e c o v e r y~R a t e)}$  

This means that if we use a recovery rate of zero when we calculate the bond-implied CDS. spread, then the spread will approximately equal the hazard rate. This is significant because the continuously compounded $Z\cdot$ -spread is equal to the constant hazard rate necessary to match the market price of the bond if we assume a recovery rate of zero'. This is clear from (2.2) because $\mathrm{exp(-(r(t)+z)t)=exp(-r(t)t)exp(-zt)}$ and exp(-zt) is the survival probability to time t, when the hazard rate is constant at z. In words: in (2.2) all bond payments are multiplied by the survival probability and discounted on the LIBOR curve. Clearly the sum of these discounted expected payments only equals the bond value if the recovery rate is zero (if the recovery rate is greater than zero there will be additional terms in (2.2)).  

It is often useful to have this zero-recovery CDS spread interpretation in mind when looking. at a $Z\cdot$ -spread. Consider a premium bond of an issuer with a given CDS spread. Suppose the. recovery rate of the issuer is. $40\%$ . What happens to the value of the bond if the recovery rate drops to $0\%$ but the CDS spread is unchanged? In this situation default probabilities must have decreased and this will increase the value of the bond because it will increase the expected time over which the bond's high coupon will be paid. This means that if the bond value stays unchanged after the recovery rate drops to $0\%$ , then the CDS spread must. increase. In other words, for a premium bond the $0\%$ -recovery bond-implied CDS spread (which approximates the Z-spread) is higher than the $40\%$ recovery bond-implied CDS spread. The reverse is the case for a discount bond. The effect is larger for high-spread long-. maturity bonds. The effect means that even if the $Z\cdot$ spread of a discount bond is lower than the same-maturity CDS spread, the bond may still be cheap compared with the CDS.  

Consider the following extreme example: On January 23, 2006 a hypothetical $6\%$ bond maturing on January 1, 2036 was trading at. $\$70$ . The bond's $0\%$ -recovery CDS spread is 382bp whereas the $40\%$ recovery CDS spread is 515bp. This is clearly a difference that must be taken into account. As a less extreme example, consider a $6\%$ bond maturing on 1 January. 2016 and trading at $\$80$ on January 23, 2006. The bond's $0\%$ -recovery CDS spread is 415bp whereas its $40\%$ -recovery CDS spread is 464bp.  

# 3. BONDS WITH EMBEDDED OPTIONS  

The OAS (or option adjusted spread) should be thought of as a $Z$ -spread that has been adjusted for any option embedded in the bond (for a bond without an embedded option, the OAS is equal to the continuously compounded Z-spread). Bonds with an embedded option are usually callable, so to simplify the terminology we focus on those, although the principles may be applied to a bond with another type of embedded option (e.g., a putable bond).  

# Separating a callable bond into the bond stripped of the option and a short position in a call option on the stripped bond  

It is useful to compare a callable bond to portfolio with positions in two hypothetical securities. One is the identical bond stripped of its embedded call option. We call this hypothetical security the stripped bond. The other security is a call option on the stripped bond with the same call schedule as the callable bond. We want to compare a long position in the callable bond with a long position in the stripped bond and a short position in the call option.  

Suppose we buy the callable bond, sell the stripped bond and buy the call option. This portfolio is hedged (has a zero net cash flow) in all states of the world (i.e., in all possible. scenarios for interest rates, default, etc.). First, we see that the cash flow from the callable bond matches the cash flow to the stripped bond until both bonds mature or the callable bond is called, whichever comes first. Second, by exercising the call option when/if the callable. bond is called, we can ensure that we are hedged in this situation also: The proceeds from the. callable bond match the exercise price of the call option and the stripped bond bought as a. result of the exercise of the call option can be used to close the short position that was initially established in the stripped bond. The argument shows that we can hedge a long position in a callable bond by selling the stripped bond and buying the call option on the stripped bond. This implies that the callable bond should never cost less than the (theoretical) value of the stripped bond minus the (theoretical) value of the call option. That is:.  

3.1) Market Price of Callable Bond $\geq$ Value of Stripped Bond -- Value of Call Option  

Can we use the above argument to establish a hedge for a short position in a callable bond? Unfortunately not. Suppose we sell the callable bond, buy the stripped bond and sell the call option. As long as the call option is not exercised we have no problem: the cash flow from the stripped bond will cover the cash flow required for the short position in the callable bond. However, if the call option is exercised, we would need to call the callable bond, which can be done only by the issuer. If we could be sure that the issuer would call the callable bond exactly when it is optimal to exercise the call option on the stripped bond, then the hedge would work. However, there are good reasons why this is not the case. For example, an issuer must consider the cost of refinancing before calling (i.e., prepaying) a bond. Usually an issuer would need to issue a new bond, which can be costly. The refinancing cost effectively raises the call price for the issuer and thus reduces the value of the embedded call option. This explains why the callable bond should be worth more than the (theoretical) value of the stripped bond, minus the (theoretical) value of the call option on the stripped bond.  

# The OAS of a callable bond is the Z-spread of the stripped bond when properly adjusting for the value of the call option.  

In our OAS calculation we disregard the possible refinancing cost to the issuer and assume. that the issuer will call the bond exactly when it is optimal for an outside investor to exercise the call option on the stripped bond. With this assumption the value of the callable bond. becomes equal to the value of the stripped bond minus the value of the call option. That is:.  

3.2) Market Price of Callable Bond $=$ Value of Stripped Bond -- Value of Call Option  

If we knew the value of the call option we could subtract it from the market price of the callable bond to arrive at a market-implied value of the stripped bond. Based on this we could calculate a (continuously compounded) Z-spread of the stripped bond and report it as the OAS of the callable bond. This is essentially the approach we use to calculate the OAS except that we need to use a model to value the call option.  

To value the call option we use a model intended for valuing options on Treasury securities or interest rate swaps. The model takes as inputs a curve of zero-coupon interest rates and a set of parameters determining the volatility of these interest rates. Suppose we pass to the model the LIBOR zero-coupon interest rates and volatility parameters calibrated to. appropriate swaption prices with the purpose of using the model to price a Bermudan swaption (say with swap maturity date equal to the bond maturity date). We know that the swap underlying the Bermudan swaption is priced correctly in the model when we input the  

LIBOR rates. However, to value the call option we need to make an adjustment to the model. to ensure that it correctly prices the underlying stripped bond. The adjustment is to shift all. interest rates in all scenarios generated internally in the model by the OAS of the stripped bond (see a more detailed explanation in the next subsection). However, this OAS is unknown to us as it depends on the value of the call option. Putting these pieces together, we see that the OAS has to solve an equation:.  

$$
\mathrm{Market~Price}=\exp(-(\mathrm{r(t_{1})}+\mathrm{OAS)t_{1}})\mathrm{C_{1}}+\ldots+\exp(-(\mathrm{r(t_{N})}+\mathrm{OAS)t_{N}})\mathrm{C_{N}}
$$  

OptionValue( $\{\mathrm{r(t)}\}_{\mathrm{t>0}}$ , Volatility Parameters, OAS)  

where Market Price is the observed price of the callable bond, the first terms on the right-hand side of the equation sum to the value of the stripped bond, and the last term is the value of the call option. The option value is written as a function of the zero-coupon interest rates $\{\mathrm{r(t)}\}_{\mathrm{t>0}},$ the volatility parameters and the OAS. Note that the OAS appears for the valuation of both the. stripped bond and the call option. The OAS is found by numerically solving equation (3.3).  

# Incorporating OAS into the option valuation model  

We value the option using a model that has been implemented in a recombining tree (lattice) for the short rate. The short rate is the continuously compounded interest rate earned over one period in the lattice. This is called a short rate model and is shown in Fig. 3.1..  

![](e07774d7cf6862ed4405bea393c662a1e4135f7983c05af9c6956153a4b41863.jpg)  
Figure 3.1. Example of a short-rate model. For simplicity, we assume that all branching probabilities are 0.5 and the period length is 1 year  

Source: Lehman Brothers.  

To value a security in this type of model we determine the security's cash flow in each state. (i.e., node) and discount backwards in the tree. For example, if we value the bullet bond with. the cash flow shown in Figure 3.2 (think of this as the stripped bond underlying the call option we want to value), we get the values shown in Figure 3.3..  

![](1d9152af14c4e5b252664f29cdff95d51b9830821b18269093efb1c60b47577a.jpg)  
Figure 3.2. Cash flow of a bullet bond to values in the short rate model in Fig. 3.1   
Source: Lehman Brothers.  

![](d0c59879f2733ace991ae77c3a07c69d788317c0dd320dfb927e83ec3f48d12b.jpg)  
Figure 3.3. Values of a bullet bond (ex coupon) from Figure 3.2 in the short rate model in Figure 3.1   
Source: Lehman Brothers.  

The value of a security in a given state is the expected value of the security in the next period. (including cash flow/coupon) discounted with the short rate in the state. This procedure is also used to price a call option on the bullet bond. Suppose the exercise price of the call option is 100. The option is then worthless at time 2 (end of. $2^{\mathrm{nd}}$ period) and in the $6\%$ rate state at time 1. In the $4\%$ rate state at time 1, the option should be exercised because it is. worthless at time 2 and worth $100.8829-100=0.8892$ if exercised. At time 0 the option is worth $\exp(-5\%){\cdot}0.5{\cdot}0.8829=0.4199$ if it is not exercised and has a negative value if it is. exercised. This means that the option should not be exercised at time 0 and is worth 0.4199.  

As explained above, when we value the call option we need to make sure that the underlying bond is priced correctly. For example, if the value of the bond is 98.8 and not 99.8 as in Figure 3.3, we need to adjust the interest rates in the tree with the OAS of the bond. This adjustment is done, as illustrated in Figure 3.4, by increasing the continuously compounded short rate in all states by the OAS.  

![](9f67a724e032ec01510d1d5381bc407d2b66870b881a08b6090ec356af3ce182.jpg)  
Figure 3.4. The short rate model in Figure 3.1 has been shifted by the OAS   
Source: Lehman Brothers.  

If we choose an $\mathrm{OAS}=50\mathrm{bp}$ we get a bullet bond price of 98.7997. With this OAS the call. option is worth only 0.1797. This means that if the callable bond (the bullet bond minus the call option) was trading at. $98.80–0.18=98.62$ , the callable bond would have a 50bp OAS..  

Before proceeding to the next section and explaining which type of stochastic term structure model we use, we show why the OAS and Z-spread of a bullet bond are equal when we use continuous compounding. To calculate the $Z$ -spread we need zero-coupon interest rates to time 1 and 2. The zero-coupon rate to time 1 is clearly. $5\%$ . The zero-coupon rate to time 2, denoted $\mathrm{R}$ , must satisfy the equation:  

$$
\exp(-\mathrm{R}\cdot2)=\exp(-5\%)\cdot(0.5\cdot\exp(-6\%)+0.5\cdot\exp(-4\%))
$$  

where the right-hand side of the equation is the value calculated in the tree of a zero-coupon bond paying $\$1$ at time 2. Using this equation and letting Z denote the $Z$ spread we can write the value of the bond as:  

$$
\begin{array}{r l}&{\exp(-(5^{0}\%+Z))\cdot5+\exp(-(\mathrm{R}+Z)\cdot2)\cdot105}\ &{=\exp(-(5^{0}\%+Z))\cdot5+\exp(-5^{0}\%)\cdot(0.5\cdot\exp(-6^{0}\%)+0.5\cdot\exp(-4^{0}\%))\cdot\exp(-Z\cdot2)\cdot105}\ &{=\exp(-(5^{0}\%+Z))\cdot(5+0.5\cdot\exp(-(6^{0}\%+Z))\cdot105+0.5\cdot\exp(-(4^{0}\%+Z))\cdot105)}\end{array}
$$  

but this is also the value of the bond calculated in the tree when rates have been shifted by an ${\mathrm{OAS}}=Z$ . This shows that the OAS and. $Z$ spread are the same. The two assumptions that. make this calculation work are: (1) bond payments for a given time are independent of the state; and (2) with continuous compounding the OAS adjustment becomes a multiplicative factor on the discount factors (i.e. $\exp(-(\mathrm{R+Z})\cdot\mathrm{T})=\exp(-\mathrm{R\cdotT})\cdot\exp(-Z\cdot\mathrm{T}))$  

# 4. THE STOCHASTIC TERM STRUCTURE MODEL  

In this section we explain which stochastic term structure model we use to calculate OAS. We use a short rate model as explained in the previous section. There is extensive academic as well as practitioner literature describing the theory and uses of short rate models. Hull (2000) gives an introduction to stochastic term structure models, including short rate models. In this section we assume a familiarity with the models at the level of Hull (2000).  

# The Black-Karasinsky model  

For several years Lehman Brothers has used a Black-Karasinsky (BK) model for corporate. bond OAS computations. In the BK model the short rate is lognormally distributed. More precisely, the short rate r(t) is given by:.  

$$
\begin{array}{r l}&{\mathbf{r}(\mathrm{t})=\mathbf{\boldsymbol{a}}(\mathrm{t})\mathbf{\boldsymbol{e}}\mathbf{\boldsymbol{x}}\mathbf{\boldsymbol{p}}(\mathbf{\boldsymbol{x}}(\mathrm{t}))}\ &{}\ &{\mathbf{d}\mathbf{\boldsymbol{x}}(\mathrm{t})=-\mathbf{\boldsymbol{\kappa}}(\mathrm{t})\mathbf{\boldsymbol{x}}(\mathrm{t})\mathbf{d}\mathrm{t}+\mathbf{\boldsymbol{\sigma}}(\mathrm{t})\mathbf{d}\mathbf{\boldsymbol{W}}(\mathrm{t})}\end{array}
$$  

where ${\mathfrak{a}}({\mathfrak{t}}),\kappa({\mathfrak{t}})$ and $\upsigma(\mathrm{t})$ are deterministic functions of time and W(t) is a Brownian motion. $\kappa(\mathfrak{t}),\mathfrak{t}{\ge}0$ , are referred to as the mean reversion speed parameters. $\upsigma(\mathrm{t}),\mathrm{t}{\geq}0$ , are the volatility parameters.  

Suppose we already know the mean reversion speed and volatility parameters and that they are constant, we can then implement the model in a trinomial lattice as described in Hull (2000) in the section on the Hull and White model (starting at page 580). Although this type of trinomial lattice implementation works well, at Lehman Brothers we use a more sophisticated implementation that allows arbitrary time steps in the lattice and timedependent volatility and mean reversion speed.  

# Calibrating the model  

As explained in Hull (2o00), given the mean reversion speed and volatility parameters. $\upkappa(\mathrm{t})$ and $\upsigma(\mathrm{t}),\mathrm{t}{\geq}0$ the remaining parameters $\mathfrak{a}(\mathfrak{t}),\mathfrak{t}{\ge}0$ , are determined to ensure that the zero-. coupon interest rates calculated in the model match those supplied to the model. This is called calibrating to the term structure (of interest rates).  

We calibrate the volatility parameters to a set of at-the-money interest rate swaption prices. Our calibration routine uses numerical optimization to minimize a weighted sum of squared differences between model and market swaption prices. At each step in the optimization iteration, we calibrate to the LIBOR term structure.  

There are two different approaches to the volatility calibration. The approach we do not use is to jointly calibrate the volatility and mean reversion speed parameters to best fit the entire matrix of at-the-money swaption prices, that is prices of X into $\mathrm{Y}$ swaptions where X ranges from 1 month to 30 years and $\mathrm{Y}$ ranges from 6 months to 30 years. We do not use this approach because the fit is not good.  

Our approach is to use different calibrations for different maturity bonds. Suppose we want to calculate the OAS of a 10-year bond. We will then calibrate to prices of. $\mathrm{T}_{\mathrm{n}}$ into $\mathrm{T}{-}\mathrm{T}_{\mathrm{n}}$ swaptions where. $\mathrm{T}=10$ years and $\mathrm{T_{n}}=1$ month, 3 months, 6 months, 1 year, ... 9 years, that. is swaptions where the swap maturity date is 10 years from the calibration date'. With this limited set of swaptions, we can do an exact calibration. The calibration could also be done iteratively by first calibrating $\upsigma_{0}=\upsigma(\mathrm{t}),0{\le}\mathrm{t}{<}\mathrm{T}_{0}.$ to a $\mathrm{T}_{0}$ into $\mathrm{T}\mathrm{-}\mathrm{T}_{0}$ swaption, then taking. $\upsigma_{0}$ as given and calibrating ${\upsigma}_{1}={\upsigma}(\mathrm{t})$ $\mathrm{T}_{0}{\le}\mathrm{t}{<}\mathrm{T}_{1}$ , to a $\mathrm{T}_{1}$ into $\mathrm{T}\mathrm{-}\mathrm{T}_{1}$ swaption, and so forth. We do the. calibration for bond maturities of 1, 2, 3, ..., 10, 15, 20, 25, and 30 years. For a bond with maturity in between two calibration maturities, say a 9.5-year bond, we linearly interpolate the calibrated volatility parameters (in this case between the 9- and 10-year parameters).  

We exogenously fix the mean reversion speed and calibrate only the volatility parameters. Currently we use. $\upkappa(\up t)=0$ between 0 and 5 years and. $\upkappa(\mathrm{t})=0.03$ for t greater than 5 years.. The mean reversion speed is difficult to estimate empirically. The estimation is complicated by the fact the mean reversion speed under the risk-neutral probability measure (the measure used to price securities) is different from the mean reversion speed estimated directly from a time series of the short rate and by the poor empirical performance of a one-factor model. We use the stability of the calibrated. $\upsigma(\mathrm{t}),\mathrm{t}{\geq}0$ , as a criterion for evaluating a particular choice of $\kappa(\mathfrak{t}),\mathfrak{t}{\ge}0$ , but this is done only on an ad hoc basis.  

# Shifting the Black-Karasinsky model to better fit the Black volatility skew  

The volatility skew in interest rate swaptions describes the fact that the implied Black volatility of an interest rate swaption usually increases with decreases in the strike. The simple explanation is that the Black volatility is a proportional volatility and this volatility tends to be higher when the interest rate is low than when it is high. For example, suppose. the Black volatility for 1-year into 1-year swaption is $20\%$ A 1-year into 1-year forward rate of $5\%$ then implies a standard deviation of roughly $1\%$ . On the other hand, if the forward rate was $2.5\%$ , the $20\%$ volatility would imply a standard deviation of $0.5\%$ .The skew can be. thought of as simply reflecting the belief that when a rate decreases, say from. $5\%$ to $2.5\%$ then the standard deviation of the rate does not decrease enough to keep the volatility. constant. In the example, this means that if the forward rate is $5\%$ and the implied volatility. of a $5\%$ strike swaption is. $20\%$ , then the implied Black volatility of a swaption with a lower. strike should be higher than. $20\%$ . Zhou (2003) explains this phenomenon in significantly more detail.  

The BK model gives rise to swaption prices with implied Black volatilities that are almost constant as a function of the strike. This is because in the BK model, the short rate is lognormally distributed which roughly means that its standard deviation is proportional to its level.  

Another model choice is to replace (4.1) with:  

$$
\mathbf{r}(\mathbf{t})=\mathbf{a}(\mathbf{t})+\mathbf{x}(\mathbf{t})
$$  

The model then becomes the Hull-White model where the short rate is normally distributed, which roughly means that its standard deviation is independent of its level. The Hull-White. model gives rise to a more pronounced volatility skew than is usually observed..  

Our approach is to replace (4.1) with  

$$
\begin{array}{r l}&{\dot{\mathbf{r}}(\mathfrak{t})=\mathfrak{a}(\mathfrak{t})\mathrm{exp}(\mathbf{x}(\mathfrak{t}))}\ &{}\ &{\mathbf{r}(\mathfrak{t})=\dot{\mathbf{r}}(\mathfrak{t})-\gamma}\end{array}
$$  

where $\gamma{\geq}0$ is a fixed parameter that we call the shift. We call the model the shifted BK model. Notice that with $\gamma=0\%$ we have $\dot{\mathbf{r}}(\mathrm{t})=\mathbf{r}(\mathrm{t})$ and get the BK model itself.  

The parameters $\mathfrak{a}(\mathfrak{t}),\mathfrak{t}{\ge}0$ , are still calibrated to ensure that the model matches the zerocoupon interest rates. On average, loosely speaking, the level of the short rate $\mathrm{r(t)}$ cannot be affected by the shift. Second, since the mean of $\mathbf{\boldsymbol{x}}(\mathbf{\boldsymbol{t}})$ is zero, $\exp(\mathbf{x}(\mathbf{t}))$ fluctuates around 1. These two observations may be reconciled only if the as make up for the effect of the shift. This means that the as must be higher with a shift than with no shift and that r(t) will evolve at a level that, loosely speaking, has been shifted up by $\upgamma$ relative to the interest rate in the BK model.  

The volatility parameters $\upsigma(\mathrm{t}),\mathrm{t}{\geq}0$ , determine the volatility of $\dot{\mathrm{r}}(\mathrm{t})$ as for a BK model where the short rate is increased by $\upgamma$ . This means that the standard deviation of r(t) will be larger than the standard deviation of the short rate, $\mathrm{r(t)}$ , in the BK model if we use the same os. We therefore need to use lower os in the shifted model.  

To better understand the effects of the shift, consider the following example. Suppose the short rate starts at $5\%$ and has a one-period simple volatility of. $20\%$ . If we model this in a. binomial tree we get the results illustrated in Figure 4.1..  

![](ef089ba31010284e64ec2dca2c53af7eac81575dad54477add91ae1d5e187e61.jpg)  
Figure 4.1.  Simplified binominal tree for the short rate in a lognormal model with simple $20\%$ volatility per period10   
Source: Lehman Brothers.  

After one period, the short rate either goes up to. $1.2{\cdot}5\%=6\%$ or down to $0.8{\cdot}5\%=4\%$ . In the second period, if the rate increased in the first period, it either increases to $1.2{\cdot}6\%=7.2\%$ or decreases to $0.8{\cdot}6\%=4.8\%$ whereas if the rate decreased the first period, it either increases to $1.2{\cdot}4\%=4.8\%$ or decreases to $0.8{\cdot}4\%=3.2\%$ .In the second period, the. volatility in the up state is. $20\%=7.2\%/6\%-1=-(4.8\%/6\%-1)$ . In the down state, the. volatility is also $20\%=4.8\%/4\%-1=1-3.2\%/4\%$ 10  

Now consider the model with a $45\%$ shift (Figure 4.2). Suppose we use a volatility parameter of $2\%$ . This means that after one period the short rate either increases to $1.02\cdot(5\%+45\%)-$ $45\%=6\%$ or decreases to $0.98\cdot(5\%+45\%)-45\%=4\%$ We see that this is the same. $20\%$ volatility that we got in Figure 4.1 without a shift. In the second period, if the rate increases to $6\%$ , it either continues up to $1.02\cdot(6\%+45\%)-45\%=7.02\%$ or falls to $0.98\cdot(6\%+45\%)$ $-~45\%=4.98\%$ . This implies a volatility of $17\%=7.02\%/6\%-1=-(4.98\%/6\%-1)$ which is below the $20\%$ in the non-shifted model. On the other hand, if the rate decreases in the first period, it will either rise to. $1.02\cdot(4\%+45\%)-45\%=4.98\%$ or decrease to $0.98{\cdot}(4\%$ $+45\%)-45\%=3.02\%$ in the second period. So if the rate decreases in the first period, the volatility over the second period is. $24.5\%=4.98\%/4\%-1=-(3.02\%/4\%-1)$ which is higher than the $17\%$ volatility faced if the rate increases in the first period.  

![](e76bace4fe485bad4a9fe7db42b98128ea2ea7678a395cb782c99b015c3665a4.jpg)  
Figure 4.2. Simplified binominal tree for the short rate in a shifted lognormal model with 45% shift and simple 2% lognormal volatility per period10  

Source: Lehman Brothers.  

# Comments about our model choices  

The BK (and the shifted BK) model is a one-factor model with one state variable. At Lehman Brothers we have more sophisticated models with several state variables and/or factors'1. Adding state variables significantly increases the computation time to the point where threefour state variables is the maximum number practically feasible.  

In a one-factor model, changes in interest rates of all maturities are perfectly correlated and the shape of the curve cannot change without the short rate, and thus the level of the curve, changing. This is an unrealistic feature that is contradicted by the data. Several empirical studies have shown that at least three factors are required to properly describe the dynamics of the interest rate curve (see Dai and Singleton (2003) and their references). Another potential problem with one-factor models is that the time-dependent parameters tend to be less constant than in multifactor models (the $\upsigma(\mathrm{t}),\mathrm{t}{\geq}0$ , calibrated on a given day are often decreasing or hump-shaped, and os change more from one day to the next).  

There are two main reasons why we have decided to use a one-factor/one-state variable model (at least for the time being):  

Simplicity: the model is much easier to explain and implement (and thus replicate). The impact of explicitly modelling default is greater than the impact of improving the interest rate modelling (especially for higher spread issuers). We model default by adding the hazard rate (the instantaneous probability of default) as a stochastic factor. This is more easily done for a one-state variable interest rate model. (See section 6 for more on this extension of the model.)  

Another important modelling decision is our calibration procedure. As explained above, we perform 14 different calibrations, each using swaptions with the same underlying swap maturity date. This is because calculating an OAS is a pricing exercise, and when pricing it is important that the model is calibrated to the swaptions most similar to the option we are pricing. The option embedded in a callable bond is usually an American call option on a bullet bond which (when forgetting about default risk) is closest to an American option on a swap with the same maturity date as the bond. With our calibration choice we are calibrating to the set of European swaptions most relevant for this American swaption. In contrast, a global calibration to the entire matrix of swaption prices is unlikely to match the prices of these most relevant swaptions.  

Another important calibration consideration regards the shift that must be used to best fit the skew. Here we focus on below-ATM swaptions (strike below the forward rate) with swap. maturity dates about 5-30 years out and option maturity dates 1-10 years out because these are the swaptions most relevant for the typical callable bond..  

# 5. NUMERICAL RESULTS  

In this section we show differences in the volatility calibration for the BK and the shifted BK model on two days: January 23, 2006, when the curve was almost flat and June 28, 2004, when the curve was steeply upward-sloping. We also discuss the differences in OAS in the two models.  

# Volatility calibration  

Figure 5.1 shows the fitted zero-coupon LIBOR curves on the two dates. The differences between the two dates are very clear..  

![](07f3056eb6b1bc7c92625450409ca01823659c0e5316b9039a0dc0a452bc6218.jpg)  
Figure 5.1.  Zero-coupon UsD LIBOR interest rates on June 28, 2004 and January 23, 2006   
Source: Lehman Brothers.  

Figure 5.2 shows implied Black volatilities for a subset of the ATM swaptions to which we calibrate the volatility parameters. Notice that the volatilities for short-term swaptions on short-term swaps (e.g., for 3-month into 1-year) are much higher on June 28, 2004 than on. January 23, 2006 whereas the volatilities for long-term swaptions on long-term swaps are. lower.  

Figure 5.2. Implied Black volatilities. $(\%)$ for at-the-money swaptions on 28 June 2004 and 23 January 2006 for USD   


<html><body><table><tr><td>28-Jun-2004</td><td colspan="6">Option Maturity</td><td>23-Jan-2006</td><td colspan="6">OptionMaturity</td></tr><tr><td>Swap Term</td><td>3M</td><td>1Y</td><td>2Y</td><td>5Y</td><td>10Y</td><td>30Y</td><td>Swap Term</td><td>3M</td><td>1Y</td><td>2Y</td><td>5Y</td><td>10Y</td><td>30Y</td></tr><tr><td>1Y</td><td>37.0</td><td>30.2</td><td>24.8</td><td>18.7</td><td>13.6</td><td>9.5</td><td>1Y</td><td>13.5</td><td>17.7</td><td>20.2</td><td>20.4</td><td>18.0</td><td>12.7</td></tr><tr><td>2Y</td><td>33.8</td><td>27.5</td><td>23.2</td><td>18.0</td><td>13.1</td><td>9.4</td><td>2Y</td><td>15.8</td><td>18.7</td><td>20.1</td><td>20.1</td><td>17.7</td><td>12.8</td></tr><tr><td>3Y</td><td>30.5</td><td>25.4</td><td>22.0</td><td>17.3</td><td>12.8</td><td>9.3</td><td>3Y</td><td>16.2</td><td>18.8</td><td>19.9</td><td>19.8</td><td>17.4</td><td>12.8</td></tr><tr><td>5Y</td><td>26.1</td><td>22.4</td><td>20.0</td><td>16.2</td><td>12.1</td><td>9.2</td><td>5Y</td><td>16.7</td><td>18.8</td><td>19.6</td><td>19.2</td><td>16.7</td><td>12.8</td></tr><tr><td>10Y</td><td>20.1</td><td>18.4</td><td>17.1</td><td>14.3</td><td>10.9</td><td>8.5</td><td>10Y</td><td>16.1</td><td>18.1</td><td>18.6</td><td>17.9</td><td>15.7</td><td>12.4</td></tr><tr><td>30Y</td><td>14.2</td><td>13.4</td><td>12.7</td><td>10.9</td><td>9.0</td><td>6.1</td><td>30Y</td><td>15.3</td><td>16.4</td><td>16.4</td><td>15.3</td><td>13.6</td><td>11.8</td></tr></table></body></html>

Source: Lehman Brothers.  

Figures 5.3 and 5.4 show a subset of the calibrated volatility parameters for the two dates. using the two different models. In Figure 5.3 we see that on June 28, 2004 the BK volatility parameter curve for the shortest bond maturity (3Y) is the highest, whereas the curve for the longest bond maturity (30Y) is the lowest, and we see that this relationship has switched on January 23, 2006. This observation can also be made for the shifted BK model in Figure 5.4. The volatility parameter curves have very similar shapes in the two models and both capture. the market information about the volatility changes seen in Figure 5.2. We find it interesting that the relative change in the calibrated volatility parameters between the two dates is smaller in the $40\%$ shifted model.  

![](bc2e61df4c12b5910445971fdcd3575d4c23924729ab6e1770aec5d657b2a232.jpg)  
Figure 5.3. Calibrated volatility parameters $(\%)$ for four different bond maturities in the BK model   
Source: Lehman Brothers.  

![](ae88fe1d36c233adaad8c99889288f5e4379fad05c99fa1a68a89c49a336718d.jpg)  

# Figure 5.4. Calibrated volatility parameters. $(\%)$ for four different bond maturities in BK model with $40\%$ shift  

![](0dd39bbd909d8ba8237fbdf1f9f0313578bc51dc72752b57651d3be9875e0e79.jpg)  
Source: Lehman Brothers.  

![](ace6c6a7f3f59c06bcc72738677d1909b650a955e921e63823feb55ae7da3f33.jpg)  

# Effect of volatility skew parameter (shift) on OAS  

In this subsection we examine the differences in the OAS between the two models. Our bond universe is a combination of the Lehman Brothers US Corporate and High Yield indices. The. comparison is done using data from January 23, 2006.12  

At the aggregate level there is very little change in OAS. However, for individual bonds. some differences can be found. Out of the 4,812 bonds in our universe 1,215 are callable and 68 are putable. For 1,095 bonds there is a difference in the OAS, but only 388 of the bonds have a relative difference in OAS greater than. $2\%$ (the maximum OAS among those is. 306bp). There are 78 bonds with an OAS difference greater than. $10\%$ , but among those the OAS is greater than 40bp for only 12 bonds and greater than 20bp for only 22 bonds. The maximum absolute OAS difference among all bonds is 31bp, but several of the bonds with a large absolute OAS difference have a negative OAS (this could be the result of a stale price or maybe the bond has just been called'3). Most bonds with a negative OAS in the BK model. have a higher OAS in the shifted model..  

The two main observations regarding the effect of the model change on the OAS of an individual bond are:  

1. Bonds where the call option is in the money tend to have higher OAS in the shifted model. Bonds where the call option is far out of the money tend to have lower OAS in the shifted model.  

The extent to which the option is in or out of the money affects the difference in the OAS in the two models. In the shifted model, high (rate) strike swaptions will have lower Black volatility, whereas the low (rate) strike swaptions will have a higher Black volatility (Figure 5.5). Since a high rate strike swaption corresponds to an option on a high-coupon bond, inthe-money call options will tend to have a higher OAS in the shifted BK model. This is because a lower Black volatility means a lower option value which gives rise to a lower value of the stripped bond (to keep the value of the callable bond constant, see equation (3.2)). A lower value of the stripped bond means a higher OAS. Similarly, an out-of-themoney call option will tend to have a lower OAS in the shifted model.  

![](fc1b8f15d9d5e7bcbf529cc5d35da7804f817423c1c5356f1649f85948e2137c.jpg)  
Figure 5.5. Implied Black volatilities for a 5-year into 5-year receiver swaption assuming a flat interest rate curve at $5\%$ and constant volatility parameters   
Source: Lehman Brothers.  

# 6. ADJUSTING FOR DEFAULT RISK  

In the last subsection of section 2 we discussed how the Z-spread can be interpreted as an approximate $0\%$ -recovery bond-implied CDS spread calculated in a hazard rate model. We. can improve upon the Z-spread by calculating a bond-implied CDS spread assuming a more realistic recovery rate.  

It is important to use a realistic recovery rate not only when we compare a bond with a CDS but also when we calculate the duration (interest rate sensitivity) of a bond. Consider the following extreme example. On 23 January 2006 a $6\%$ bond maturing on January 1, 2036. was trading at $\$70$ . The bond's $0\%$ -recovery CDS spread is 382 and the $40\%$ -recovery CDS spread is 515. If LIBOR rates are increased by $100\mathrm{bp}$ , we assume recovery $=0\%$ , and hold $0\%$ -recovery CDS spread constant, then the price drops $\$7.1$ . If we assume recovery $=40\%$ and hold the $40\%$ -recovery CDS spread constant then the price only drops $\$4.8$  

If we want to assume a recovery rate greater than $0\%$ and directly model default, the natural next question is how to deal with a callable bond. Just as going from Z-spread to OAS means going from deterministic to stochastic interest rates, going from the bond-implied CDS spread of a non-callable bond to that of a callable bond means going from deterministic interest rates and hazard rates to stochastic interest rates and hazard rates. It is outside the scope of this paper to fully describe this type of two-factor model and at this point we just. want to comment on the approach (a later publication will discuss the approach in detail).  

There are two fundamentally different ways to implement a stochastic interest/hazard rate. model. One possibility is to use Monte Carlo techniques. The advantages of this approach are. that we can use a more realistic multifactor interest rate model and we can more easily. incorporate a non-zero correlation between interest rates and hazard rates. The main disadvantage is that dealing with an American (or Bermudan) exercise is complicated significantly. Monte Carlo models also take longer to run to achieve the same level of. accuracy as lattice-based models, which is the second type of approach..  

We have implemented a stochastic interest/hazard rate model in a two-factor lattice. The.   
main drawback of our lattice-based approach is that only one-factor is used to model interest rates which is less realistic (see section 4) and that incorporating a non-zero correlation is.   
more difficult. The advantages of our model are that it calculates quickly, gives accurate risk.   
measures (Greeks), and easily deals with American and Bermudan exercise..  

In addition to the recovery rate (and potentially a CDS curve that will be shifted - see the discussion of bond-implied CDS spread in section 2, particularly footnote 6), a stochastic interest rate/hazard rate model needs a hazard rate volatility and an interest rate/hazard rate correlation. These two parameters are difficult to estimate and are highly dependent on the issuer of the bond. We think, in general, that if nothing else is known, the correlation should be set to zero or slightly negative. There are some market data on default swaptions that can be used to get a handle on the hazard rate volatility. For more discussion of this issue, including an account of how to build a stochastic hazard rate model (not including a stochastic interest rate), see Pedersen and Sen (2004).  

# 7. SUMMARY  

We have explained what the. $Z\cdot$ -spread of a corporate bond is and how it is calculated. We introduced the concept of a bond-implied CDS spread and explained how the Z-spread can be interpreted as an approximate $0\%$ -recovery bond-implied CDS spread. This was used to. establish the limitations of the. $Z$ -spread for comparing a bond to a CDS. Next the OAS of a callable bond was introduced as the Z-spread of the bond stripped of its call option where the value of the stripped bond is calculated as the price of the callable bond minus the theoretical value of the call option. We explained how we use a stochastic term structure model to find. the value of the call option and how to incorporate the OAS in the valuation of the call option. We also described the specific stochastic term structure model we use, its limitations,. and how it has recently been changed to better fit the volatility skew observed in the interest rate swaption market. Next we presented numerical results illustrating the effect of the model. change on the calibrated volatility parameters and the OAS of the bonds in the Corporate and  

High Yield Credit Indices. Finally, we briefly described the type of model required to calculate a bond-implied CDS spread for a callable bond.  

# REFERENCES  

Axel, Ralph and Prashant Vankudre (1997) The Lehman Brothers U.S. Treasury Spline Model, Lehman Brothers Government Bond Research, December 1997.   
Black, F. and P. Karasinsky (1991) Bond and Option Pricing when Short Rates are Lognormal." Financial Analysts Journal 46, pp33-39..   
Dai, Q. and K. Singleton (2003) "Term Structure Dynamics in Theory and Reality." Review of Financial Studies Vol. 16, No. 3, pp631-678.   
Hull, J. (2o00), Options, Futures, & Other Derivatives, Fourth Edition, Prentice Hall. Joneja, Dev, Lev Dynkin, et al. (2005) The Lehman Brothers Global Risk Model: A Portfolio Manager's Guide, Lehman Brothers Fixed Income Research, April 2005..   
Mashal, Roy, Marco Naldi and Peili Wang (2005) "Default-Adjusted Credit Curves and Bond Analytics: A User's Guide," Lehman Brothers Quantitative Credit Strategies, September 16, 2005.   
O'Kane, Dominic and Saurav Sen (2004) "Credit Spreads Explained," Lehman Brothers Quantitative Credit Research Quarterly, March 2004.   
O'Kane, Dominic and Stuart Turnbull (2003) "Valuation of Credit Default Swaps,' Lehman Brothers Quantitative Credit Research Quarterly, April 2003.   
Pedersen, Claus and Saurav Sen (2004) "Valuation of Constant Maturity Default Swaps," Lehman Brothers Quantitative Credit Research Quarterly, June 2004.   
Zhou, Fei (2002) The Swap Curve, Lehman Brothers Fixed Income Research, August 26, 2002. Zhou, Fei (2003) Volatility Skews, Lehman Brothers Fixed Income Research, September 30, 2003.  

To the extent that any of the views expressed in this research report are based on the firm's quantitative research model, Lehman Brothers. hereby certify (1) that the views expressed in this research report accurately reflect the firm's quantitative research model and (2) that no part of the firm's compensation was, is or will be directly or indirectly related to the specific recommendations or views expressed in this report..  

The views expressed in this report accurately reflect the personal views of Claus M. Pedersen, the primary analyst(s) responsible for this report. about the subject securities or issuers referred to herein, and no part of such analyst(s)' compensation was, is or will be directly or indirectly related to the specific recommendations or views expressed herein.  

Any reports referenced herein published after 14 April 2003 have been certified in accordance with Regulation AC. To obtain copies of these reports and their certifications, please contact Larry Pindyck (Ipindyck@lehman.com; 212-526-6268) or Valerie Monchi (vmonchi@lehman.com; 44-(0)207-102-8035).  

ehman Brothers Inc. and any affiliate may have a position in the instruments or the Company discussed in this report. The Firm's interests ma :onflict with the interests of an investor in those instruments.  

The research analysts responsible for preparing this report receive compensation based upon various factors, including, among other thing.   
the quality of their work, firm revenues, including trading, competitive factors and client feedback..  