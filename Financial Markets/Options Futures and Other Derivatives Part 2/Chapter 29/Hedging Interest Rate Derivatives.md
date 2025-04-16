---
tags:
  - '#black_model'
  - '#bond_options'
  - '#cap_floor'
  - '#convexity_adjustment'
  - '#european_options'
  - '#hedging'
  - '#interest_rate_derivatives'
  - '#swaptions'
  - '#volatility'
  - '#zero_curve'
---
# 29.4  HEDGING INTEREST RATE DERIVATIVES  

This section discusses how the material on Greek letters in Chapter 19 can be extended to cover interest rate derivatives.  

In the context of interest rate derivatives, delta risk is the risk associated with a shift in the zero curve. Because there are many ways in which the zero curve can shift, many. deltas can be calculated. Some alternatives are:.  

1. Calculate the impact of a 1-basis-point parallel shift in the zero curve. This is sometimes termed a DV01.   
2. Calculate the impact of small changes in the quotes for each of the instruments. used to construct the zero curve.   
3. Divide the zero curve (or the forward curve) into a number of sections (or buckets). Calculate the impact of shifting the rates in one bucket by 1 basis point,. keeping the rest of the initial term structure unchanged. (This is described in Business Snapshot 6.3.)   
4. Carry out a principal components analysis as outlined in Section 22.9. Calculate a. delta with respect to the changes in each of the first few factors. The first delta then measures the impact of a small, approximately parallel, shift in the zero curve; the. second delta measures the impact of a small twist in the zero curve; and so on.  

In practice, traders tend to prefer the second approach. They argue that the only way the zero curve can change is if the quote for one of the instruments used to compute the zero curve changes. They therefore feel that it makes sense to focus on the exposures arising from changes in the prices of these instruments.  

When severaldeltameasures are calculated, there are many possible gammameasures. Suppose that 10 instruments are used to compute the zero curve and that deltas are calculated by considering the impact of changes in the quotes for each of these. Gamma is a second partial derivative of the form $\partial^{2}\Pi/\partial x_{i}\partial x_{j}$ where $\Pi$ is the portfolio value.. There are 10 choices for. $x_{i}$ and 10 choices for. $x_{j}$ and a total of 55 different gamma. measures. This may be information overload". One approach is ignore cross-gammas and focus on the 10 partial derivatives where $i=j$ . Another is to calculate a single gamma measure as the second partial derivative of the value of the portfolio with respect to a parallel shift in the zero curve. A further possibility is to calculate gammas with respect to the first two factors in a principal components analysis.  

The vega of a portfolio of interest rate derivatives measures its exposure to volatility.   
changes. One approach is to calculate the impact on the portfolio of making the same small change to the Black volatilities of all caps and European swap options. However,.   
this assumes that one factor drives all volatilities and may be too simplistic. A better.   
idea is to carry out a principal components analysis on the volatilities of caps and swap.   
options and calculate vega measures corresponding to the first two or three factors.  

# SUMMARY  

Black's model and its extensions provide a popular approach for valuing Europeanstyle interest rate options. The essence of Black's model is that the value of the variable underlying the option is assumed to be lognormal at the maturity of the option. In the case of a European bond option, Black's model assumes that the underlying bond price is lognormal at the option's maturity. For a cap, the model assumes that the interest rates underlying each of the constituent caplets are lognormally distributed. In the case of a swap option, the model assumes that the underlying swap rate is lognormally distributed.  

The models presented in this chapter are not consistent with each other. For example, when future bond prices are lognormal, future interest rates and swap rates are not lognormal; when future interest rates are lognormal, future bond prices and swap rates are not lognormal. The models cannot easily be extended to value instruments such as American swap options. Chapters 32 and 33 present more general interest rate models, which, although more complex, can be used for a much wider range of products.  

Black's model involves calculating the expected payoff based on the assumption that. the expected value of a variable equals its forward value and then discounting the expected payoff at the zero rate observed in the market today. This is the correct procedure for the "plain vanilla' instruments we have considered in this chapter.. However, as we shall see in the next chapter, it is not correct in all situations..  

# FURTHER READING  

Black, F. "The Pricing of Commodity Contracts," Journal of Financial Economics, 3 (March 1976): 167-79.   
Hull, J. C., and A. White. "OIS Discounting, Interest Rate Derivatives, and the Modeling of Stochastic Interest Rate Spreads," Journal of Investment Management, 13, 1 (2015): 64-83.  

# Practice Questions  

29.1. A company caps a 3-month floating rate at $2\%$ per annum. The principal amount is. $\$20$ million. On a reset date, the floating rate is. $4\%$ per annum. What payment would. this lead to under the cap? When would the payment be made?.   
29.2. Explain why a swap option can be regarded as a type of bond option.   
29.3. Use the Black's model to value a 1-year European put option on a 10-year bond. Assume that the current cash price of the bond is $\$125$ , the strike price is $\$110$ , the 1-year risk-free. interest rate is $10\%$ per annum, the bond's forward price volatility is $8\%$ per annum, and. the present value of the coupons to be paid during the life of the option is. $\$10$   
29.4. Explain carefully how you would use (a) spot volatilities and (b) flat volatilities to value a 5-year cap.   
29.5. Calculate the price of an option that caps the 3-month rate, observed in 15 months for the 15-18 month period, at $13\%$ (quoted with quarterly compounding) on a principal amount. of $\$1,000$ The forward interest rate for the period in question is. $12\%$ per annum (quoted) with quarterly compounding), the 18-month risk-free interest rate (continuously compounded) is $11.5\%$ per annum, and the volatility of the forward rate is. $12\%$ per annum.   
29.6. A bank uses Black's model to price European bond options. Suppose that an implied price volatility for a 5-year option on a bond maturing in 10 years is used to price a 9-year option on the bond. Would you expect the resultant price to be too high or too low? Explain your answer.  

29.7. Calculate the value of a 4-year European call option on bond that will mature 5 years from today using Black's model. The 5-year cash bond price is $\$105$ , the cash price of a. 4-year bond with the same coupon is $\$102$ and both bonds have a principal of $\$100$ . Thee strike price of the option is $\$100$ , the 4-year risk-free interest rate is $10\%$ per annum with. continuous compounding, and the forward bond price volatility for the bond underlying the option is. $2\%$ per annum.  

29.8. If the yield volatility for a 5-year put option on a bond maturing in 10 years time is. specified as $22\%$ , how should the option be valued? Assume that, based on today's. interest rates the modified duration of the bond at the maturity of the option will be 4.2 years and the forward yield on the bond is. $7\%$  

29.9. What other instrument is the same as a 5-year zero-cost collar where the strike price of the cap equals the strike price of the floor? What does the common strike price equal?.  

29.10. Derive a put-call parity relationship for European bond options.  

29.11. Derive a put-call parity relationship for European swap options.  

29.12. Explain why there is an arbitrage opportunity if the implied Black (flat) volatility of a cap is different from that of a floor.  

29.13. When a bond's price is lognormal can the bond's yield be negative? Explain your answer.  

29.14. What is the value of a European swap option that gives the holder the right to enter into a 3-year annual-pay swap in 4 years where a fixed rate of. $5\%$ is paid and floating is. received? The swap principal is $\$10$ million. Assume that the volatility of the swap rate is. $20\%$ , all swap rates are are. $5\%$ , and all OIS rates are. $4.7\%$ . Compare your answer with that given by DerivaGem.  

29.15. Suppose that the yield. $R$ on a zero-coupon bond follows the process  

$$
d R=\mu d t+\sigma d z
$$  

where $\mu$ and $\sigma$ are functions of $R$ and $t$ , and $d z$ is a Wiener process. Use Ito's lemma to show that the volatility of the zero-coupon bond price declines to zero as it approaches maturity.  

29.16. Carry out a manual calculation to verify the option prices in Example 29.2.  

29.17. Suppose that all risk-free (OIS) zero rates are $6.5\%$ (continuously compounded). The price of a 5-year semiannual cap on LIBOR with a principal of $\$100$ and a cap rate of $8\%$ (semiannually compounded) is $\$3$ Use DerivaGem to determine:  

(a) The implied 5-year flat volatility for caps and floors. (b) The floor rate in a zero-cost 5-year collar when the cap rate is $8\%$  

Assume that all 6-month LIBOR forward rates are $6.7\%$ with semiannual compounding.  

29.18. Show that $V_{1}+f=V_{2}$ , where $V_{1}$ is the value of a swaption to pay a fixed rate of $s_{K}$ and receive floating between times $T_{1}$ and $T_{2},f$ is the value of a forward swap to receive a fixed rate of $s_{K}$ and pay floating between times $T_{1}$ and $T_{2}$ , and $V_{2}$ is the value of a swaption to receive a fixed rate of $s_{K}$ between times $T_{1}$ and $T_{2}$ . Deduce that $V_{1}=V_{2}$ when $s_{K}$ equals the current forward swap rate.  

29.19. Suppose that risk-free zero rates and LIBOR forward rates are as in Problem 29.17. Use DerivaGem to determine the value of an option to pay a fixed rate of $6\%$ and receive LIBOR on a 5-year swap starting in 1 year. Assume that the principal is $\$100$ million, payments are exchanged semiannually, and the swap rate volatility is $21\%$  

684 CHAPTER 29   
29.20. Describe how you would (a) calculate cap flat volatilities from cap spot volatilities and (b) calculate cap spot volatilities from cap flat volatilities.   
29.21. Consider an 8-month European put option on a Treasury bond that currently has 14.25 years to maturity. The current cash bond price is $\$910$ , the exercise price is $\$900$ , and the. volatility for the bond price is $10\%$ per annum. A coupon of $\$35$ will be paid by the bond in 3 months. The risk-free interest rate is $8\%$ for all maturities up to 1 year. Use Black's model to determine the price of the option. Consider both the case where the strike price corresponds to the cash price of the bond and the case where it corresponds to the quoted price.   
29.22. A swaption gives the holder the right to receive $7.6\%$ in a 5-year swap starting in 4 years. Payments are made annually. The forward swap rate is $8\%$ with annual compounding and its volatility is $25\%$ per annum. The principal is $\$1$ million and risk-free (OIS) rates for all maturities are $7.8\%$ (with continuous compounding). Use Black's model to price the swaption. Compare your answer to that given by DerivaGem.   
29.23. Use the DerivaGem software to value a 5-year collar that guarantees that the maximum and minimum interest rates on a LIBOR-based loan (with quarterly resets) are $7\%$ and $5\%$ , respectively. All 3-month LIBOR forward rates are $6\%$ per annum (with quarterly compounding). The flat volatility is $20\%$ . Assume that the principal is. $\$100$ and the risk-free (OIS) term structure is flat at $5.8\%$   
29.24. Use the DerivaGem software to value a European swaption that gives you the right in   
2 years to enter into a 5-year swap in which you pay a fixed rate of. $6\%$ and receive floating. Cash flows are exchanged semiannually on the swap. The continuously compounded 1-year, 2-year, 5-year, and 10-year risk-free (Ois) zero rates are $5\%$ $6\%$ $6.5\%$ , and $7\%$ , respectively. Assume a principal of $\$100$ . The forward swap rate. is $7\%$ (compounded semiannually) and its volatility is $15\%$ per annum. Give an example of how the swaption might be used by a corporation. What bond option is equivalent to the swaption?  

![](17e6222841178b1c960a7e1fa24058eb6b4dfd71e1847a10297f4b27c10f23ef.jpg)  

# Convexity, Timing, and Quanto Adjustments  

A popular two-step procedure for valuing a European-style derivative is:  

1. Calculate the expected payoff by assuming that the expected value of each underlying variable equals its forward value   
2. Discount the expected payoff at the risk-free rate applicable for the time period between the valuation date and the payoff date.  

We first used this procedure when valuing FRAs and swaps. Chapter 4 shows that an FRA can be valued by calculating the payoff on the assumption that the forward interest rate will be realized and then discounting the payoff at the risk-free rate. Similarly, Chapter 7 extends this, showing that swaps can be valued by calculating cash flows on the assumption that forward rates will be realized and discounting the cash flows at risk-free rates. Chapters 18 and 28 show that Black's model provides a general approach to valuing a wide range of European options--and Black's model is an application of the two-step procedure. The models presented in Chapter 29 for bond options, caps/floors, and swap options are all examples of the two-step procedure.  

This raises the issue of whether it is always correct to value European-style interest rate derivatives by using the two-step procedure. The answer is no! For nonstandard interest rate derivatives, it is sometimes necessary to modify the two-step procedure so that an adjustment is made to the forward value of the variable in the first step. This chapter considers three types of adjustments: convexity adjustments, timing adjustments, and quanto adjustments.  
