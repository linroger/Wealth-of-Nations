---
tags:
  - '#american_call_option'
  - '#binomial_model'
  - '#black_scholes_merton_model'
  - '#critical_stock_price'
  - '#dividend_payments'
  - '#early_exercise'
  - '#multivariate_normal_probability'
  - '#two_payment_case'
---
# 19.2 THE TWO-PAYMENT CASE

The single dividend model has been extended to cover the case of two known payments.
during the life of the option (Welch and Chen (1988) and Stephan and Whaley (1990)).
Figure 19.2 illustrates the notation for the two-payment case. The notation follows closely.
the one-payment case and can easily be generalized.

Let the first payment be $D_{1}$ and the time to the payment date be $\tau_{1}$ and the second payment be $D_{2}$ and the time to the second ex-dividend date be $\tau_{2}$ The solution is4

$$
\begin{array}{r l}&{C=\left(S-D_{1}e^{-r_{c}\tau_{1}}\right)\left(1-N_{3}\Big(-a_{1,}-b_{1},-\widehat c_{1};\sqrt{\tau_{1}/\tau_{A}},\sqrt{\tau_{2}/\tau_{A}},\sqrt{\tau_{1}/\tau_{2}}\Big)\right)}\ &{\qquad-X\left[e^{-r_{c}\tau_{1}}N_{1}\big(\widehat c_{2}\big)+e^{-r_{c}\tau_{2}}N_{2}\Big(b_{2},-\widehat c_{2};-\sqrt{\tau_{1}/\tau_{2}}\Big)\right]}\ &{\qquad+e^{-r_{c}\tau_{A}}N_{3}\Big(a_{2},-b_{2},-\widehat c_{2};-\sqrt{\tau_{1}/\tau_{A}},\sqrt{\tau_{2}/\tau_{A}},\sqrt{\tau_{1}/\tau_{2}}\Big)}\ &{\qquad+D_{1}e^{-r_{c}\tau_{1}}N_{1}\big(\widehat c_{2}\big)+D_{2}e^{-r_{c}\tau_{2}}\left[N_{1}\big(\widehat c_{1}\big)+N_{2}\Big(\widehat b_{2},-\widehat c_{2};-\sqrt{\tau_{1}/\tau_{2}}\Big)\right],}\end{array}
$$

where

![](images/41d92110a5aea1c81ffa5cc562871b1ef272dd101eeefb951759caa68116ec42.jpg)
FIGURE 19.2  American Option with Two Dividend Payments Timeline

$$
\begin{array}{r l}&{b_{1}=\frac{\displaystyle\ln\left[\left(S-D_{1}e^{-r_{c}\tau_{1}}-D_{2}e^{-r_{c}\tau_{2}}\right)/S_{t_{2}}^{*}\right]+\left(r_{c}+\sigma^{2}/2\right)\tau_{2}}{\sigma\sqrt{\tau_{2}}}}\ &{b_{2}=b_{1}-\sigma\sqrt{\tau_{2}}}\ &{\widehat{c}_{1}=\frac{\displaystyle\ln\left[\left(S-D_{1}e^{-r_{c}\tau_{1}}-D_{2}e^{-r_{c}\tau_{2}}\right)/S_{t_{1}}^{*}\right]+\left(r_{c}+\sigma^{2}/2\right)\tau_{1}}{\sigma\sqrt{\tau_{1}}}}\ &{\widehat{c}_{2}=\widehat{c}_{1}-\sigma\sqrt{\tau_{1}}.}\end{array}
$$

The critical stock prices are defined by the relationships,

$$
\begin{array}{r l}&{c_{1}^{*}=S_{t_{1}}^{*}+D_{1}+D_{2}e^{-r_{c}\left(\tau_{2}-\tau_{1}\right)}-X}\ &{c_{2}^{*}=S_{t_{2}}^{*}+D_{2}-X.}\end{array}
$$

Note that in the first case, the critical stock price at the first payment date must equate. the exercise value, the right-hand side, to the value of an American call. This American call price would come from the one-payment American call formula that we derived in the. previous section. At the second payment date, the critical price equates the exercise value with the Black-Scholes-Merton price of a European call with time. $T-t_{2}$ remaining.

The probability $N_{3}{\left(x,y,z;\rho_{x y},\rho_{x z},\rho_{y z}\right)}$ is the trivariate normal probability. It can be calculated by defining it in relation to the univariate normal probability as follows:

$$
N_{3}\big(x,y,z;\rho_{x y},\rho_{x z},\rho_{y z}\big)=\int\displaylimits_{-\infty}^{y}N_{1}\left(\frac{y-\rho_{x y}q}{\sqrt{1-\rho_{x y}^{2}}}\right)N_{1}\left(\frac{z-\rho_{y z}q}{\sqrt{1-\rho_{y z}^{2}}}\right)N_{1}(q)d q,
$$

where $n_{1}(q)$ is the univariate normal density function. Numerical integration can usually be used to evaluate this integral.

In the two-payment case, the problem can sometimes be simplified. Simplification can. be very beneficial in coding. In particular, great savings can be amassed when not having to solve for the critical stock prices that trigger early exercise. Consider the following cases, which are collectively exhaustive:

$D_{1}=D_{2}=0$ : Use the Black-Scholes-Merton model..
$D_{1}<X\Big(1-e^{-r_{c}\left(\tau_{2}-\tau_{1}\right)}\Big),D_{2}=0$ : The first cash payment is too small to justify early exercise. Then use the Black-Scholes-Merton model with. $S-D_{1}e^{-r_{c}\tau_{1}}$ as the asset price.
$D_{1}>X\Big(1-e^{-r_{c}\left(\tau_{2}-\tau_{1}\right)}\Big),D_{2}=0$ : Early exercise is possible at the first payment date, but not at the second. Then use the one-payment American call formula.
$D_{1}<X\left(1-e^{-r_{c}\left(\tau_{2}-\tau_{1}\right)}\right)$ and $D_{2}<X\left(1-e^{-r_{c}\left(\tau_{A}-\tau_{2}\right)}\right);$ Both payments are too small to justify early exercise. Then use $S-D_{1}e^{-r_{c}\tau_{1}}-D_{2}e^{-r_{c}\tau_{2}}$ as the asset price in the Black-Scholes-Merton model.

$D_{1}<X\Big(1-e^{-r_{c}\left(\tau_{2}-\tau_{1}\right)}\Big)$ and ${\cal D}_{2}>X\Big(1-e^{-r_{c}\left(\tau_{A}-\tau_{2}\right)}\Big)$ : The option will not be exercised at the first payment date because $D_{1}$ is too small, but it could be exercised at the second. Use the one-payment American call formula, but we will still need to subtract the present value of both payments from the asset price.

$D_{1}>X\left(1-e^{-r_{c}\left(\tau_{2}-\tau_{1}\right)}\right)$ and ${\cal D}_{2}<X\left(1-e^{-r_{c}\left(\tau_{A}-\tau_{2}\right)}\right)$ : The option could be exercised at the first payment date but not the second. Use the one-payment American call formula, but we will still need to subtract the present value of both payments from the asset price.

$D_{1}>X\left(1-e^{-r_{c}\left(\tau_{2}-\tau_{1}\right)}\right)$ and ${\cal D}_{2}>X\Big(1-e^{-r_{c}\left(\tau_{A}-\tau_{2}\right)}\Big)$ : The option could be exercised at either payment date. Then use the two-payment American call formula as described.

The advantage of recognizing these special cases where the two-payment model reverts to something simpler lies in programming efficiency. If any of those conditions are met, the program can execute the simpler formula.

For more than two payments, the model would extend in the same manner. For. $_n$ payments, one would be required to evaluate an. $(n+1)$ variate normal probability distribution, but computation of multivariate normal integrals is quite difficult. In that case, one usually would use a numerical method such as a binomial model or finite difference approach, the latter of which we cover in Chapter 24..

In addition, Macmillan (1986) and Barone-Adesi and Whaley (1987) have developed. approximation techniques for American options. They split the option price into two components: the European option value and the early exercise premium. They then obtain the partial differential equation for the early exercise premium, make some simplifying assumptions, and obtain a quadratic equation that approximates the solution. This method. was very useful during the era in which computers did not have the speed they have today. In more current times, exact multivariate calculations and binomial methods are much more feasible. Research has continued to provide other formulas, but ultimately the best. methods for American call option pricing are the Roll-Geske-Whaley technique and the. binomial model.
