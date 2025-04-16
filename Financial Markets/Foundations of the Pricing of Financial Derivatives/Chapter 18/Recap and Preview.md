---
tags:
  - '#american_option_pricing'
  - '#black_scholes_merton_model'
  - '#compound_options'
  - '#dividend_payments'
  - '#equity_as_option'
  - '#option_elasticity'
  - '#option_greeks'
  - '#roll_geske_whaley_model'
---
# 18.9 RECAP AND PREVIEW

In this chapter, we examined compound options, which are useful in helping us to understand how the stock of a company is actually an option itself, where the underlying is the assets of the firm.

In Chapter 19, we get into American option pricing in continuous time, where the use of a compound option will be very helpful.

# APPENDIX 18A

# Selected Greeks of the Compound Option

The compound option delta with respect to the underlying instrument is

$$
\Delta_{c o}\equiv\frac{\partial c o}{\partial S}=\iota_{C}\iota_{U}e^{-\widehat{q}\tau_{1}}e^{-\delta\tau_{12}}N_{2}\left(\iota_{\mathrm{C}}\iota_{U}d_{11},\iota_{U}d_{12};\iota_{\mathrm{C}}\rho\right),
$$

and the underlying option, which has a price of $o$ , has a delta with respect to the underlying. instrument, $S$ , is

$$
\Delta_{_o}\equiv\frac{\partial o}{\partial S}=\iota_{U}e^{-\left(\delta-\widehat{q}\right)\tau_{2}}N_{1}\left(\iota_{U}d_{1}\right).
$$

The compound option gamma with respect to the underlying instrument, $S$ is

$$
\Gamma_{c o}\equiv\frac{\partial^{2}c o}{\partial S^{2}}=\frac{e^{-\widehat{q}\tau_{1}}e^{-\delta\tau_{12}}}{S_{t}}\left[\begin{array}{l}{N_{1}\left(\iota_{U}\frac{d_{12}-\rho d_{11}}{\sqrt{1-\rho^{2}}}\right)\frac{n_{1}(d_{11})}{\sigma\sqrt{\tau_{1}}}}\ {+\iota_{C}N_{1}\left(\iota_{C}\iota_{U}\frac{d_{11}-\rho d_{12}}{\sqrt{1-\rho^{2}}}\right)\frac{n_{1}(d_{12})}{\sigma\sqrt{\tau_{2}}}}\end{array}\right],
$$

and the underlying option gamma with respect to the underlying instrument, $S_{:}$ is

$$
\Gamma_{o}\equiv\frac{\partial^{2}o}{\partial S^{2}}=\frac{e^{-\left(\delta-\widehat{q}\right)\tau_{2}}n_{1}\left(d_{1}\right)}{S_{t}\sigma\sqrt{\tau_{2}}}.
$$

The compound option theta is

$$
\begin{array}{l}{{\Theta_{c o}\equiv\displaystyle\frac{\partial c o}{\partial t}=-\frac{\sigma^{2}}2S_{t}e^{-\widehat q\tau_{1}}e^{-\delta\tau_{12}}\left[N_{1}\left({\iota}_{U}\frac{d_{12}-\rho d_{11}}{\sqrt{1-\rho^{2}}}\right)\frac{n_{1}(d_{11})}{\sigma\sqrt{\tau_{1}}}\right.}}\ {{\qquad\left.-{\iota}_{C}N_{1}\left({\iota}_{C}{\iota}_{U}\frac{d_{11}-\rho d_{12}}{\sqrt{1-\rho^{2}}}\right)\frac{n_{1}(d_{12})}{\sigma\sqrt{\tau_{2}}}\right]}}\ {{\qquad+{\iota}_{C}{\iota}_{U}\widehat q S_{t}e^{-\widehat q\tau_{1}}e^{-\delta\tau_{12}}N_{2}\left({\iota}_{C}{\iota}_{U}d_{11},{\iota}_{U}d_{12};{\iota}_{C}\rho\right)}}\ {{\qquad-{\iota}_{C}{\iota}_{U}{\dot{r}}_{c}e^{-r_{c}\tau_{2}}X_{U}N_{2}\left({\iota}_{C}{\iota}_{U}d_{21},{\iota}_{U}d_{22};{\iota}_{C}\rho\right)-{\iota}_{C}{r}_{c}e^{-r_{c}\tau_{1}}B_{t,T_{1},Y}X_{C}N_{1}\left({\iota}_{C}d_{21}\right),}}\end{array}
$$

and the underlying option theta is

$$
\begin{array}{l}{{\Theta_{o}\equiv\displaystyle\frac{\partial o}{\partial t}=\imath_{U}\left(\delta-\widehat{q}\right)S_{t}e^{-\left(\delta-\widehat{q}\right)\tau_{2}}N\left(\imath_{U}d_{1}\right)}}\ {{\qquad-\imath_{U}\left(r-\widehat{q}\right)X e^{-\left(r-\widehat{q}\right)\tau_{2}}N\left(\imath_{U}d_{2}\right)-\displaystyle\frac{\sigma S_{t}e^{-\left(\delta-\widehat{q}\right)\tau_{2}}}{2}n\left(d_{1}\right).}}\end{array}
$$

# QUESTIONS AND PROBLEMS

1 When equity is viewed as a call option on the firm where the par value of debt is the exercise price, prove that $N\left(-d_{2}\right)$ is the probability of default on the debt under the equivalent martingale measure.

2Within the context of compound options, explain the relationship between the volatility of the firm and the volatility of the common stock.

3  Prove the call on put option upper bound is $c{\/{\/{p}}}_{t}\big[{\/{p}}_{t}\left(S,X_{U},T_{2}\right),X_{C},T_{1}\big]\leq e^{-\widehat{q}\tau_{1}}{\/{p}}_{t}\left(S,X_{U},T_{2}\right).$

4 Prove the call on put option lower bound is

$$
c h_{t}\left[p_{t}\left(S,X_{U},T_{2}\right),X_{C},T_{1}\right]\geq\operatorname*{max}\left[0,e^{-\widehat{q}\tau_{1}}p_{t}\left(S,X_{U},T_{2}\right)-X_{C}e^{-r\tau_{1}}\right].
$$

5  Prove the following parity:

$$
c{p}_{t}-p{p}_{t}=e^{-\hat{q}\tau_{12}}p_{t}-e^{-r_{c}\tau_{1}}X_{\mathrm{C}}.
$$

# NOTES

1. For the generic case, $S_{t}$ will denote the underlying instrument price. Unfortunately, this notation. would conflict with the stock price that we will see here is really an option.
2. See https://www.moodysanalytics.com/about-us/history/kmv-history.
3. Although we are not specifically covering American options in this chapter, compound options will play an important role in the pricing of American options, which we cover in Chapters 19. and 20.
4. At this point, we shall diverge slightly from the original Geske derivation.

5. Note that this is consistent with Equation (18.5).

6. Geske's alternative formulation requires that we express the stochastic process for the call as $d c/c=\alpha_{c}d t+\sigma_{c V}d W_{c}$ which will imply that the market price of risk for the call, $\left(\alpha_{c}-r_{c}\right)/\sigma_{c V}$ equals the market price of risk of the asset, $\left(\alpha_{V}-r_{c}\right)/\sigma_{V}$ . Although this statement will be true. under the assumptions of the model, introducing it without proof and relying on it can cause some confusion.
7. Note that option yields would be expected to be different between calls and puts within the context of common stocks as options, although puts in this context are difficult to interpret. Within the context of the generic compound options model, one could easily have yield paying. calls and puts.
8. At this point, we begin borrowing from Rubinstein (1991), who shows more of the details of the solution.
9. A useful technique for taking these derivatives is to use the derivatives in the Black-Scholes-Mertor model. Hence, $\partial c/\partial w=(\partial c/\partial S)(\partial S/\partial w)$ where $\boldsymbol{\mathscr{w}}$ is the variable of differentiation and $\partial S/\partial\boldsymbol{\boldsymbol{w}}$ is obtained from the standard Black-Scholes-Merton derivatives.
10. The elasticity of S with respect to. $V$ is the percentage change in $S$ over the percentage change in $V$ and can be expressed as $(\partial S/\partial V)(V/S)$
11. Because this right is built into the contract, failure to pay an installment is not viewed as a default.

# American Call Option Pricing

t is well known, as we covered in Chapter 2, that an American call option on an asset that makes no cash payments, such as dividends on stocks, during the life of the option will not be exercised early and, hence, can be valued as a European option with the standard Black-Scholes-Merton formula. If the underlying asset makes a cash payment during the life of the option, early exercise could possibly be optimal, thereby giving the American call a premium over a European call and rendering the Black-Scholes-Merton model inappropriate.1 As we showed when covering the binomial model, valuation of such an option can be done by numerical methods, such as the binomial model, but it is also possible to obtain a closed-form valuation model. For an asset making a single payment during the life of the option, the model is called the Roll-Geske-Whaley model after Roll (1977), Geske (1979a, 1981), and Whaley (1981), and it is based on Geske's (1979b) compound option model.

Similar to Chapter 18, the analysis in this chapter will require more precise notation as we will work our way toward more than one dividend payment. Figure 19.1 illustrates this notation for a single dividend payment. Recall with a compound option we used $T_{2}$ to denote the underlying option expiration, whereas here we will use. $T_{A}$ to denote the expiration of the American option. Thus,. $\tau_{A}$ denotes the time to expiration of an American option. As we will see, interim dividend payments are creating a condition analogous to the exercise of compound options. We denote the dividend dates as. $T_{1}$ $T_{2}$ , and so forth to allow for generalizations. Similarly,. $\tau_{1}$ denotes the time until the first dividend payment and $\tau_{1A}$ denotes the time between the first dividend payment and the option time to expiration. The values of different instruments, such as assets and options, will use only the subscript to denote the observation date. For example,. $S_{1}$ denotes the asset value at time. $T_{1}$ . Where possible, we will drop the subscript. $t$ as it will be understood, thus. $S_{t}=S$

![](images/575471ff4f91bf970e489f3745016ca154ad0dd4f371bd9a26281d39402bfcd5.jpg)
FIGURE 19.1 American Option with Single Dividend Payment Timeline
