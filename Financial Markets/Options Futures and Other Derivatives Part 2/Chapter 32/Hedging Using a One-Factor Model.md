---
tags:
  - '#deriva_gem_software'
  - '#european_options'
  - '#hedging_strategies'
  - '#ho_lee_model'
  - '#hull_white_model'
  - '#interest_rate_derivatives'
  - '#model_calibration'
  - '#no_arbitrage_models'
  - '#one_factor_model'
  - '#term_structure_models'
---
# 32.7 HEDGING USING A ONE-FACTOR MODEL  

Section 29.4 outlined some general approaches to hedging a portfolio of interest rate. derivatives. These approaches can be used with the term structure models in this. chapter. The calculation of deltas, gammas, and vegas involves making small changes to either the zero curve or the volatility environment and recomputing the value of the portfolio.  

Note that, although one factor is often assumed when pricing interest rate derivatives, it is not appropriate to assume only one factor when hedging. For example, the deltas calculated should allow for many different movements in the yield curve, not just those that are possible under the model chosen. The practice of taking account of changes that cannot happen under the model considered, as well as those that can, is known as. outside model hedging and is standard practice for traders.17 The reality is that relatively. simple one-factor models if used carefully usually give reasonable prices for instruments, but good hedging procedures must explicitly or implicitly assume many factors..  

# SUMMARY  

When valuing derivatives, it is important that the model used be consistent with the initial term structure observed in the market. No-arbitrage models are designed to have this property. They take the initial term structure as given and define how it can evolve.  

This chapter has provided a description of a number of one-factor no-arbitrage models of the short rate. These are robust and can be used in conjunction with any set of initial zero rates. The simplest model is the Ho-Lee model. This has the advantage that it is analytically tractable. Its chief disadvantage is that it implies that all rates are equally variable at all times. The Hull-White model is a version of the Ho-Lee model that includes mean reversion. It allows a richer description of the volatility environment while preserving its analytic tractability. Lognormal one-factor models avoid the possibility of negative interest rates, but have no analytic tractability.  

# FURTHER READING  

Black, F., E. Derman, and W. Toy, "A One-Factor Model of Interest Rates and Its Application to Treasury Bond Prices," Financial Analysts Journal, January/February 1990: 33-39..   
Black, F., and P. Karasinski, "Bond and Option Pricing When Short Rates Are Lognormal," Financial Analysts Journal, July/August (1991): 52-59.   
Brigo, D., and F. Mercurio, Interest Rate Models: Theory and Practice, 2nd edn. New York:. Springer, 2006.   
Ho, T. S. Y., and S.-B. Lee, "Term Structure Movements and Pricing Interest Rate Contingent Claims," Journal of Finance, 41 (December 1986): 1011-29.   
Hull, J. C., and A. White, "Bond Option Pricing Based on a Model for the Evolution of Bond. Prices," Advances in Futures and Options Research, 6 (1993): 1-13..   
Hull, J. C., and A. White, "Pricing Interest Rate Derivative Securities," The Review of Financial Studies, 3, 4 (1990): 573-92.   
Hull, J. C., and A. White, Using Hull-White Interest Rate Trees," Journal of Derivatives, Spring. (1996): 26-36.   
Rebonato, R., Interest Rate Option Models. Chichester: Wiley, 1998.  

# Practice Questions  

32.1. What is the difference between an equilibrium model and a no-arbitrage model?  

32.2. Can the approach described in Section 32.2 for decomposing an option on a coupon-. bearing bond into a portfolio of options on zero-coupon bonds be used in conjunction with a two-factor model? Explain your answer..  

32.3. Suppose that $a=0.1,b=0.08$ , and $\sigma=0.015$ in Vasicek's model, with the initial value of the short rate being $5\%$ . Calculate the price of a 1-year European call option on a zero-coupon bond with a principal of $\$100$ that matures in 3 years when the strike price is $\$87$  

32.4. Repeat Problem 32.3 valuing a European put option with a strike of $\$87$ . What is the put-call parity relationship between the prices of European call and put options? Show that the put and call option prices satisfy put-call parity in this case.  

32.5. Suppose that $a=0.05,b=0.08$ , and $\sigma=0.015$ in Vasicek's model with the initial shortterm interest rate being $6\%$ . Calculate the price of a 2.1-year European call option on a. bond that will mature in 3 years. Suppose that the bond pays a coupon of $5\%$ semiannually. The principal of the bond is 100 and the strike price of the option is 99. The strike price is the cash price (not the quoted price) that will be paid for the bond.   
32.6. Use the answer to Problem 32.5 and put-call parity arguments to calculate the price of a put option that has the same terms as the call option in Problem 32.5.   
32.7. In the Hull-White model, $a=0.08$ and $\sigma=0.01$ . Calculate the price of a 1-year European call option on a zero-coupon bond that will mature in 5 years when the term structure is flat at $10\%$ , the principal of the bond is $\$100$ , and the strike price is $\$68$   
32.8. Suppose that $a=0.05$ and $\sigma=0.015$ in the Hull-White model with the initial term. structure being flat at. $6\%$ with semiannual compounding. Calculate the price of a. 2.1-year European call option on a bond that will mature in 3 years. Suppose that the bond pays a coupon of. $5\%$ per annum semiannually. The principal of the bond is 100. and the strike price of the option is 99. The strike price is the cash price (not the quoted price) that will be paid for the bond..   
32.9. Suppose $a=0.05$ $\sigma=0.015$ , and the term structure is flat at $10\%$ . Construct a trinomial tree for the Hull-White model where there are two time steps, each 1 year in length.   
32.10. Calculate the price of a 2-year zero-coupon bond from the tree in Figure 32.4.   
32.11. Calculate the price of a 2-year zero-coupon bond from the tree in Figure 32.7 and verify that it agrees with the initial term structure..   
32.12. Calculate the price of an 18-month zero-coupon bond from the tree in Figure 32.8 and verify that it agrees with the initial term structure.   
32.13. What does the calibration of a one-factor term structure model involve?   
32.14. Prove equations (32.15), (32.16), and (32.17).   
32.15. A trader wishes to compute the price of a 1-year American call option on a 5-year bond with a face value of 100. The bond pays a coupon of $6\%$ semiannually and the (quoted) strike price of the option is $\$100$ . The continuously compounded zero rates for maturities of 6 months, 1 year, 2 years, 3 years, 4 years, and 5 years are $4.5\%$ $5\%$ $5.5\%$ $5.8\%$ $6.1\%$ , and $6.3\%$ . The best-fit reversion rate for either the normal or the lognormal model has been estimated as $5\%$ A 1-year European calloption with a (quoted) strike price of 100on the bond is actively traded. Its market price is $\$0.50$ The trader decides to use this option for calibration. Use.  

the DerivaGem software with 10 time steps to answer the following questions:.  

(a) Assuming a normal model, imply the. $\sigma$ parameter from the price of the European option. (b) Use the $\sigma$ parameter to calculate the price of the option when it is American.  

(c) Repeat (a) and (b) for the lognormal model. Show that the model used does not significantly affect the price obtained providing it is calibrated to the known European price.   
(d) Display the tree for the normal model and calculate the probability of a negative interest rate occurring.   
(e) Display the tree for the lognormal model and verify that the option price is correctly calculated at the node where, with the notation of Section. $32.4,i=9$ and $j=-1$  

32.16. Verify that the DerivaGem software gives Figure 32.9 for the example considered. Use. the software to calculate the price of the American bond option for the lognormal and normal models when the strike price is 95, 100, and 105. In the case of the normal model, assume that $a=5\%$ and $\sigma=1\%$ . Discuss the results in the context of the heavy-tails. arguments of Chapter 20.  

32.17. Modify Sample Application G in the DerivaGem Application Builder software to test the convergence of the price of the trinomial tree when it is used to price a 2-year call. option on a 5-year bond with a face value of 100. Suppose that the strike price (quoted) is 100, the coupon rate is $7\%$ with coupons being paid twice a year. Assume that the zero. curve is as in Table 32.2. Compare results for the following cases:.  

(a) Option is European; normal model with. $\sigma=0.01$ and $a=0.05$ (b) Option is European; lognormal model with $\sigma=0.15$ and $a=0.05$ (c) Option is American; normal model with. $\sigma=0.01$ and $a=0.05$ (d) Option is American; lognormal model with $\sigma=0.15$ and $a=0.05$  

![](211a9be27deb03c073e4657e1d495db1fbe8611ee052db309898205341fd588c.jpg)  

# Modeling Forward Rates  

The interest rate models discussed in Chapter 32 are widely used for pricing instruments. when the simpler models in Chapter 29 are inappropriate. They are easy to implement. and, if used carefully, can ensure that most nonstandard interest rate derivatives are priced consistently with actively traded instruments such as interest rate caps, European swap options, and European bond options. Two limitations of the models are:.  

1. Most involve only one factor (i.e., one source of uncertainty).   
2. They do not give the user complete freedom in choosing the volatility structure.  

By making the parameters $a$ and $\sigma$ functions of time, an analyst can use the models so that they fit the volatilities observed in the market today, but as mentioned in Section 32.6 the volatility term structure is then nonstationary. The volatility structure in the future is liable to be quite different from that observed in the market today.  

This chapter discusses some general approaches to building term structure models that give the user more flexibility in specifying the volatility environment and allow. several factors to be used.  

This chapter also covers the agency mortgage-backed security market in the United. States and describes how some of the ideas presented in the chapter can be used to price instruments in that market..  
