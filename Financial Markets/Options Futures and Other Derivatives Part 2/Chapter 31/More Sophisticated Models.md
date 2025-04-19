---
tags:
  - '#bond_pricing'
  - '#cir_model'
  - '#equilibrium_models'
  - '#market_price_of_risk'
  - '#no_arbitrage_models'
  - '#risk_neutral_world'
  - '#short_rate_models'
  - '#term_structure_of_interest_rates'
  - '#two_factor_models'
  - '#vasicek_model'
---
# 31.5 MORE SOPHISTICATED MODELS  

The Vasicek and CIR models are simple one-factor Markov models of the short rate. A two-factor Markov model of the short rate that is an extension of Vasicek is6.  

$$
\begin{array}{c}{d r=\left(u-a r\right)d t+\sigma_{1}d z_{1}}\ {d u=-b u d t+\sigma_{2}d z_{2}}\end{array}
$$  

In this model, the reversion level $(=u/a)$ is not constant. It follows a stochastic process. However, bond prices are analytic:  

$$
P(t,T)=A(t,T)e^{-B(t,T)r-C(t,T)u}
$$  

where $B(t,T)$ is the same as in the Vasicek model and  

$$
C(t,T)=\frac{1}{a(a-b)}e^{-a(T-t)}-\frac{1}{b(a-b)}e^{-b(T-t)}+\frac{1}{a b}
$$  

The function $A(t,T)$ is more complex (see Technical Note 14 on the author's website).  

Another two-factor model which has analytic bond prices and involves similar processes to CIR was developed by Longstaff and Schwartz.' Other multifactor models are sometimes used in practice to describe the real-world evolution of the term structure. In Chapter 33, we will describe how general risk-neutral models can be developed in terms of forward rates.  

# SUMMARY  

When a Markov model of the (instantaneous) short rate has been specified, the current value of the short rate determines the whole term structure of interest rates as a function of the level of the short rate. It is therefore tempting to model the term structure of interest rates by specifying a process for the short rate. Two popular models are the Vasicek and Cox, Ingersoll, and Ross (CIR) models. In both models the short rate follows a mean-reverting process (i.e., it is pulled back toward a central value) and has some uncertainty superimposed on the mean reversion. In the case of Vasicek, the uncertain component of the change over a short period of time of length $\Delta t$ always has zero mean and a constant standard deviation; in CIR, the uncertain component has zero mean and a standard deviation proportional to the square root of the short rate. In Vasicek, rates can become negative; in CIR, this is not possible. In both models the bond price $\textstyle P(t,T)$ has the form $A(t,T)e^{-B(t,T)r}$ , but the $A(t,T)$ and $B(t,T)$ functions in the two models are not the same.  

The market price of interest rate risk is negative. If the market price of risk in Vasicek is constant, the process followed by the short rate in the real world is the same as that in the risk-neutral world except that the reversion level is lower. If the market price of risk in CIR is proportional to the square root of the short rate, the process in the real world has the same form as that in the risk-neutral world except that the reversion rate is higher and the reversion level is lower.  

The models we have considered in this chapter do not provide an exact fit to the. current term structure of interest rates but are useful for simulating the behavior of interest rates in some situations. When derivatives are being valued it is usually. necessary to use a model that provides an exact fit to the current term structure of. interest rates. Short-rate models that do this are considered in the next chapter and more. general models that describe the behavior of forward rates are in Chapter 33..  

# FURTHER READING  

Cox, J. C., J. E. Ingersoll, and S. A. Ross, "A Theory of the Term Structure of Interest Rates," Econometrica, 53 (1985): 385-407.   
Longstaff, F. A. and E. S. Schwartz, "Interest Rate Volatility and the Term Structure: A Two-. Factor General Equilibrium Model," Journal of Finance, 47, 4 (September 1992): 1259-82..   
Vasicek, O. A., "An Equilibrium Characterization of the Term Structure," Journal of Financial. Economics, 5 (1977): 177-88.  

# Practice Questions  

31.1. Suppose that the short rate is currently $4\%$ and its standard deviation in a short period of time $\Delta t$ is $0.01\sqrt{\Delta t}$ What happens to this standard deviation when the short rate. increases to $8\%$ in (a) Vasicek's model, (b) Rendleman and Bartter's model, and. (c) the Cox, Ingersoll, and Ross model?   
31.2. If a stock price were mean reverting or followed a path-dependent process there would be market inefficiency. Why is there not a market inefficiency when the short-term interest rate does so?   
31.3. Explain the difference between a one-factor and a two-factor model.  

31.4. Suppose that in a risk-neutral world the Vasicek parameters are $a=0.1,b=0.03$ , and $\sigma=0.01$ . What is the price of a 5-year zero-coupon bond with a principal of $\$1$ when the short rate is $2\%?$   
31.5. Suppose that in a risk-neutral world the CIR parameters are $a=0.1$ $b=0.03$ , and $\sigma=0.07.$ The market price of interest rate risk is $-1$ times the square root of the short rate. What are the risk-neutral and real-world processes for (a) the short rate and (b) a zerocoupon bond with a current maturity of 4 years.   
31.6. Suppose that the market price of risk of the short rate is $\lambda_{1}+\lambda_{2}r$ (with $\lambda_{1}$ and $\lambda_{2}$ negative). Show that if the real-world process for the short rate is the one assumed by Vasicek, the risk-neutral process has the same functional form as the real-world process. Derive the relationship between (a) the real-world reversion rate and the riskneutral reversion rate and (b) the real-world reversion level and the risk-neutral reversion level.   
31.7. Observations spaced at intervals $\Delta t$ are taken on the short rate. The ith observation is $r_{i}$ $0\leq i\leq m$ ). Show that the maximum-likelihood estimates of a, $b^{*}$ , and $\sigma$ in Vasicek's model are given by maximizing.  

$$
\sum_{i=1}^{m}\biggl(-\ln(\sigma^{2}\Delta t)-\frac{[r_{i}-r_{i-1}-a(b^{*}-r_{i-1})\Delta t]^{2}}{\sigma^{2}\Delta t}\biggr)
$$  

31.8. Calculate the alternative duration measure explained in Section 31.2 for a 2-year bond with a principal of $\$100$ paying coupons semiannually at the rate of. $\$3$ per year when Vasicek's model is used with. $a=0.13$ $b=0.012$ $\sigma=0.01$ , and $r=1\%$ . Show that it correctly predicts the effect of an increase in. $r$ to $1.05\%$  

31.9. Suppose that $a=0.1$ and $b=0.1$ and in both the Vasicek and the Cox, Ingersoll, Ross model. In both models, the initial short rate is $10\%$ and the initial standard deviation of the short-rate change in a short time. $\Delta t$ is $0.02\sqrt{\Delta t}$ Compare the prices given by the. models for a zero-coupon bond that matures in year 10.  

31.10. Suppose the short rate. $r$ .1 $4\%$ and its real-world process is. $d r=0.1(0.05-r)d t+0.01d z$ while the risk-neutral process is $d r=0.1(0.11-r)d t+0.01d z$  

(a) What is the market price of interest rate risk?.   
(b) What is the expected return and volatility for a 5-year zero-coupon bond in the riskneutral world?   
(c) What is the expected return and volatility for a 5-year zero-coupon bond in the real world?  

31.11. (a) What is the second partial derivative of. $\textstyle P(t,T)$ with respect to. $r$ in the Vasicek and. CIR models? (b) In Section 31.2, $\hat{D}$ is presented as an alternative to the usual duration measure, $D$ What is a similar alternative,. $\hat{C}$ to the convexity measure in Section 4.11?. (c) What is $\hat{C}$ for $\textstyle P(t,T)?$ How would you calculate $\hat{C}$ for a coupon-bearing bond? (d) Give a Taylor series expansion for. $\Delta P(t,T)$ in terms of $\Delta r$ and $\left(\Delta r\right)^{2}$ for Vasicek and CIR.  

31.12. Suppose that in the risk-neutral Vasicek process $a=0.15,b=0.025$ , and $\sigma=0.012$ The market price of interest rate risk is. $-0.2$ .What are the risk-neutral and real-world processes for (a) the short rate and (b) a zero-coupon bond with a current maturity of 3 years.  

31.13. Suppose that the market price of risk of the short rate is $\lambda_{1}/\sqrt{r}+\lambda_{2}\sqrt{r}$ Show that if the real world process for the short rate is the one assumed by CIR, the risk-neutral process. has the same functional form. Derive the relationship between (a) the real-world reversion rate and the risk-neutral reversion rate and (b) the real-world reversion level and the risk-neutral reversion level.   
31.14. In the two-factor extension of Vasicek given in Section 31.5, derive the differential equation which must be satisfied by a bond price, $\textstyle P(t,T)$ . Use this to derive differential equations that must be satisfied by $A(t,T)$ $B(t,T)$ ,and $C(t,T)$ in $\textstyle P(t,T)=$ $\hat{A(t,T)e^{-B(t,T)r-C(t,T)u}}$ . Show that the expressions given for. $B(t,T)$ in equation (31.7) and $C(t,T)$ in equation (31.14) satisfy these equations. [Hint: Use equation (14A.10) to obtain the drift of $\textstyle P(t,T)$ and set this drift equal to $r P(t,T)$ 1.   
31.15. Use the result in Problem 31.7 to determine the best fit parameters for the Vasicek model using the same data as in Section 31.4 (see www-2.rotman.utoronto.ca/\~hull/ VasicekCIR). Verify that the regression approach in Section 31.4 and the maximumlikelihood approach give the same answer.   
31.16. What is the result corresponding to that given in Problem 31.7 for the CIR model? Use. maximum likelihood methods to estimate the $a,b$ , and $\sigma$ parameters for the CIR model. using the same data as that used for the Vasicek model in Section 31.4 (see www-2.rotman.utoronto.ca/\~hull/VasicekCIR). Setting the market price of risk equal. to $\kappa\sqrt{r}$ use the market data in Table 31.1 to estimate the best fit $\kappa$  

![](d5f9dd5dfff7a03c79b2271c795e36d285ff7fa9a5655a82db3e53c9ec0177a2.jpg)  

# No-Arbitrage Models of the Short Rate  

The disadvantage of the equilibrium models presented in Chapter 31 is that they do not automatically fit today's term structure of interest rates. By choosing the parameters judiciously, they can be made to provide an approximate fit to many of the term structures that are encountered in practice. But the fit is not an exact one. Most traders, when they are valuing derivatives, find this unsatisfactory. Not unreasonably, they argue that they can have very little confidence in the price of a bond option when the model. used does not price the underlying bond correctly. A $1\%$ error in the price of the underlying bond may lead to a $25\%$ error in an option price.  

A no-arbitrage model is a model designed to be exactly consistent with today's term structure of interest rates. The essential difference between an equilibrium and a noarbitrage model is therefore as follows. In an equilibrium model, today's term structure of interest rates is an output. In a no-arbitrage model, today's term structure of interest rates is an input.  

In an equilibrium model, the drift of the short rate is not usually a function of time. In a no-arbitrage model, the drift is, in general, dependent on time. This is because the shape of the initial zero curve governs the average path taken by the short rate in the. future in a no-arbitrage model. If the zero curve is steeply upward-sloping for maturities. between $t_{1}$ and $t_{2}$ , then $r$ has a positive drift between these times; if it is steeply downward-sloping for these maturities, then $r$ has a negative drift between these times.  
