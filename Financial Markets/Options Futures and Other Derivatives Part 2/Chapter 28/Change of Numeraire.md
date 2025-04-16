---
tags:
  - '#bond_options'
  - '#change_of_numeraire'
  - '#equivalent_martingale_measure'
  - '#interest_rate_caps_floors'
  - '#interest_rate_derivatives'
  - '#market_price_of_risk'
  - '#risk_neutral_valuation'
  - '#stochastic_interest_rates'
  - '#swap_options'
---
# 28.8 CHANGE OF NUMERAIRE  

In this section, we consider the impact of a change in numeraire on the process followed. by a market variable. Suppose first that the variable is the price of a traded security, $f.$  

In a world where the market price of $d z_{i}\operatorname{risk}$ is $\lambda_{i}$  

$$
d f=\left[r+\sum_{i=1}^{n}\lambda_{i}\sigma_{f,i}\right]f d t+\sum_{i=1}^{n}\sigma_{f,i}f d z_{i}
$$  

Similarly, when it is $\boldsymbol{\lambda}_{i}^{*}$  

$$
d f=\left[r+\left.\sum_{i=1}^{n}\lambda_{i}^{*}\sigma_{f,i}\right]f d t+\left.\sum_{i=1}^{n}\sigma_{f,i}f d z_{i}\right.
$$  

The effect of moving from the first world to the second is therefore to increase the expected growth rate of the price of any traded security. $f$ by  

$$
\sum_{i=1}^{n}\big(\lambda_{i}^{*}-\lambda_{i}\big)\sigma_{f,i}
$$  

Consider next a variable $\nu$ that is not the price of a traded security. As shown in. Technical Note 20 at www-2.rotman.utoronto.ca/\~hull/TechnicalNotes, the expected growth rate of $\nu$ responds to a change in the market price of risk in the same way as the. expected growth rate of the prices of traded securities. It increases by.  

$$
\alpha_{\nu}=\sum_{i=1}^{n}(\lambda_{i}^{*}-\lambda_{i})\sigma_{\nu,i}
$$  

where $\sigma_{\nu,i}$ is the ith component of the volatility of $\nu$  

When we move from a numeraire of $g$ to a numeraire of $h$ $\lambda_{i}=\sigma_{g,i}$ and $\lambda_{i}^{*}=\sigma_{h,i}$ Define $w=h/g$ and $\sigma_{w,i}$ as the ith component of the volatility of $w$ . From Ito's lemma (see Problem 28.13),  

$$
\sigma_{w,i}=\sigma_{h,i}-\sigma_{g,i}
$$  

so that equation (28.33) becomes  

$$
\alpha_{\nu}=\sum_{i=1}^{n}\sigma_{w,i}\sigma_{\nu,i}
$$  

We will refer to $w$ as the numeraire ratio. Equation (28.34) is equivalent to  

$$
\alpha_{\nu}=\rho\sigma_{\nu}\sigma_{w}
$$  

where $\sigma_{\nu}$ is the total volatility of $\nu,\sigma_{w}$ is the total volatility of $w$ , and $\rho$ is the instantaneous correlation between changes in $\nu$ and $w$ 8.  

This is a surprisingly simple result. The adjustment to the expected growth rate of a variable $\nu$ when we change from one numeraire to another is the instantaneous covariance between the percentage change in $\nu$ and the percentage change in the numeraire ratio. This result will be used when timing and quanto adjustments are considered in Chapter 30.  

A particular case of the results in this section is when we move from the real world to the traditional risk-neutral world (where all the market prices of risk are zero). From. equation (28.33), the growth rate of. $\nu$ changes by $-\textstyle\sum_{i=1}^{n}\dot{\lambda}_{i}\sigma_{\nu,i}.$ This corresponds to thee result in equation (28.13) when $\nu$ is the price of a traded security. We have shown that it. is also true when. $\nu$ is not the price of a traded security. In general, the way that we move. from one world to another for variables that are not the prices of traded securities is the. same as for those that are.  

# A Final Point  

In this chapter we have expressed the processes for variables in terms of their expected returns and volatilities. The results if we use drifts and standard deviations are much the same. Suppose  

$$
d f=\mu f d t+\sigma f d z
$$  

and we write the process as  

$$
d f=\mu^{*}d t+\sigma^{*}d z
$$  

(so that $\mu^{*}=\mu f$ and $\sigma^{*}=\sigma f$ ). Suppose further that these processes reflect a market price of risk of $\lambda_{1}$ . The impact of changing the market price to $\lambda_{2}$ is, as we have explained, to change the process to  

$$
d f=(\mu+\lambda_{2}\sigma-\lambda_{1}\sigma)f d t+\sigma f d z
$$  

This is the same as  

$$
d f=(\mu^{*}+\lambda_{2}\sigma^{*}-\lambda_{1}\sigma^{*})d t+\sigma^{*}d z
$$  

# SUMMARY  

The market price of risk of a variable defines the trade-offs between risk and return for traded securities dependent on the variable. When there is one underlying variable, a.   
derivative's excess return over the risk-free rate equals the market price of risk multiplied.   
by the derivative's volatility. When there are many underlying variables, the excess return.   
is the sum of the market price of risk multiplied by the volatility for each variable..  

A powerful tool in the valuation of derivatives is risk-neutral valuation. This was introduced in Chapters 13 and 15. The principle of risk-neutral valuation shows that, if. we assume that the world is risk neutral when valuing derivatives, we get the right answer- not just in a risk-neutral world, but in all other worlds as well. In the traditional risk-neutral world, the market price of risk of all variables is zero. This chapter has extended the principle of risk-neutral valuation. It has shown that, when interest rates are stochastic, there are many interesting and useful alternatives to the traditional risk-neutral world.  

A martingale is a zero drift stochastic process. Any variable following a martingale has the simplifying property that its expected value at any future time equals its value today. The equivalent martingale measure result shows that,if. $g$ is a security price, there is a world in which the ratio $f/g$ is a martingale for all security prices $f.$ It turns out that, by appropriately choosing the numeraire security. $g$ , the valuation of many interest rate dependent derivatives can be simplified.  

This chapter has used the equivalent martingale measure result to extend Black's. model to the situation where interest rates are stochastic and to value an option to exchange one asset for another. In Chapters 29 to 34, it will be useful in valuing interest. rate derivatives.  

# FURTHER READING  

Baxter, M., and A. Rennie, Financial Calculus. Cambridge University Press, 1996.   
Cox, J. C., J. E. Ingersoll, and S. A. Ross, "An Intertemporal General Equilibrium Model of Asset Prices," Econometrica, 53 (1985): 363-84.   
Duffie, D., Dynamic Asset Pricing Theory, 3rd edn. Princeton University Press, 2001.   
Harrison, J. M., and D. M. Kreps, "Martingales and Arbitrage in Multiperiod Securities Markets," Journal of Economic Theory, 20 (1979): 381-408.   
Harrison, J. M., and S. R. Pliska, "Martingales and Stochastic Integrals in the Theory of Continuous Trading," Stochastic Processes and Their Applications, 11 (1981): 215-60.  

# Practice Questions  

28.1. How is the market price of risk defined for a variable that is not the price of an investment asset?   
28.2. Suppose that the market price of risk for gold is zero. If the storage costs are $1\%$ per annum and the risk-free rate of interest is $6\%$ per annum, what is the expected growth rate in the price of gold? Assume that gold provides no income..   
28.3. Consider two securities both of which are dependent on the same market variable. The expected returns from the securities are $8\%$ and $12\%$ . The volatility of the first security is $15\%$ . The instantaneous risk-free rate is $4\%$ . What is the volatility of the second security?   
28.4. An oil company is set up solely for the purpose of exploring for oil in a certain small area of Texas. Its value depends primarily on two stochastic variables: the price of oil and the quantity of proven oil reserves. Discuss whether the market price of risk for the second of these two variables is likely to be positive, negative, or zero.   
28.5. Deduce the differential equation for a derivative dependent on the prices of two nondividend-paying traded securities by forming a riskless portfolio consisting of the derivative and the two traded securities.  

28.6. Suppose that an interest rate $x$ follows the process  

$$
d x=a(x_{0}-x)d t+c{\sqrt{x}}d z
$$  

where $a,x_{0}$ and $c$ are positive constants. Suppose further that the market price of risk for $x$ is $\lambda$ . What is the process for $x$ in the traditional risk-neutral world?  

28.7. Prove that, when the security $f$ provides income at rate $q$ , equation (28.9) becomes $\mu+q-r=\lambda\sigma$ (Hint: Form a new security $f^{*}$ that provides no income by assuming that all the income from $f$ is reinvested in $f.$  

28.8. Show that when. $f$ and $g$ provide income at rates $q_{f}$ and $q_{g}$ respectively, equation (28.15) becomes  

$$
f_{0}=g_{0}e^{(q_{f}-q_{g})T}E_{g}\bigg({\frac{f_{T}}{g_{T}}}\bigg)
$$  

(Hint: Form new securities $f^{*}$ and $g^{*}$ that provide no income by assuming that all the income from $f$ is reinvested in $f$ and all the income in $g$ is reinvested in $g$  

28.9. "The expected future value of an interest rate in a risk-neutral world is greater than it is in the real world." What does this statement imply about the market price of risk for. (a) an interest rate and (b) a bond price. Do you think the statement is likely to be true?. Give reasons.  

28.10. The variable $S$ is an investment asset providing income at rate $q$ measured in currency A. It follows the process  

$$
d S=\mu_{S}S d t+\sigma_{S}S d z
$$  

in the real world. Defining new variables as necessary, give the process followed by $S$ and the corresponding market price of risk, in:  

(a) A world that is the traditional risk-neutral world for currency A   
(b) A world that is the traditional risk-neutral world for currency B   
(c) A world defined by a numeraire equal to a zero-coupon currency A bond maturing at time $T$   
(d) A world defined by a numeraire equal to a zero-coupon currency B bond maturing at time $T$  

28.11. Explain the difference between the way a forward interest rate is defined and the way the forward values of other variables such as stock prices, commodity prices, and exchange rates are defined.  

28.12. Prove the result in Section 28.5 that when  

and  

$$
{\begin{array}{l}{{d}f={\biggl[}r+\displaystyle{\sum_{i=1}^{n}}\lambda_{i}\sigma_{f,i}{\biggr]}f d t+\displaystyle{\sum_{i=1}^{n}}\sigma_{f,i}f d z_{i}}\ {{d}g=\left[r+\displaystyle{\sum_{i=1}^{n}}\lambda_{i}\sigma_{g,i}{\biggr]}g d t+\displaystyle{\sum_{i=1}^{n}}\sigma_{g,i}g d z_{i}}\end{array}}\right.
$$  

with the. $d z_{i}$ uncorrelated, $f/g$ is a martingale for $\lambda_{i}=\sigma_{g,i}$ (Hint: Start by using equation (14A.11) to get the processes for $\ln f$ and $\ln g$  

28.13. Show that when $w=h/g$ and $h$ and $g$ are each dependent on $n$ Wiener processes, the ith component of the volatility of $w$ is the ith component of the volatility of $h$ minus the ith component of the volatility of $g$ . (Hint: Start by using equation (14A.11) to get the processes for $\ln g$ and $\ln h$  

28.14. "If $X$ is the expected value of a variable, $X$ follows a martingale." Explain this statement.  

28.15. Suppose that the price of a zero-coupon bond maturing at time $T$ follows the process  

$$
d P(t,T)=\mu_{P}P(t,T)d t+\sigma_{P}P(t,T)d z
$$  

and the price of a derivative dependent on the bond follows the process  

$$
d f=\mu_{f}f d t+\sigma_{f}f d z
$$  

Assume only one source of uncertainty and that $f$ provides no income.  

(a) What is the forward price $F$ of $f$ for a contract maturing at time $T\mathrm{?}$ (b) What is the process followed by $F$ in a world defined by the numeraire. $\textstyle P(t,T){\mathrm{}}^{\cdot}$ (c) What is the process followed by $F$ in the traditional risk-neutral world? (d) What is the process followed by $f$ in a world defined by a numeraire equal to a bond maturing at time $T^{*}$ , where $T^{*}\neq T?$ Assume that $\boldsymbol{\sigma}_{P}^{*}$ is the volatility of this bond.  

28.16. Consider a variable that is not an interest rate:  

(a) In what world is the futures price of the variable a martingale?   
(b) In what world is the forward price of the variable a martingale?   
(c) Defining variables as necessary, derive an expression for the difference between the drift of the futures price and the drift of the forward price in the traditional riskneutral world.   
(d) Show that your result is consistent with the points made in Section 5.8 about the circumstances when the futures price is above the forward price.  

![](images/f21190f9ac3490fd14e74124c267ae5c42118543d463ddd705568e332406a84a.jpg)  

# Interest Rate Derivatives: The Standard. Market Models  

Interest rate derivatives are instruments whose payoffs are dependent in some way on the level of interest rates. Since the 1980s, the volume of trading in interest rate derivatives in boththe over-the-counter andexchange-tradedmarkets hasincreased rapidly. Manynew products have been developed to meet particular needs of end users. A key challenge for derivatives traders has beento find good, robust procedures for pricing and hedging these products. Interest rate derivatives are more difficult to value than equity and foreign exchange derivatives for the following reasons:  

1. The behavior of an individual interest rate is more complicated than that of a stock price or an exchange rate.   
2. For the valuation of many products it is necessary to develop a model describing the behavior of the entire zero-coupon yield curve.   
3. The volatilities of different points on the yield curve are different.   
4. Interest rates are used for discounting the derivative as well as defining its payoff.  

This chapter considers the three most popular over-the-counter interest rate option products: bond options, interest rate caps/floors, and swap options. It explains how the products work and the standard market models used to value them..  
