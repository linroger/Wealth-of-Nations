---
tags:
  - '#american_call_options'
  - '#american_put_options'
  - '#bivariate_normal_distribution'
  - '#black_scholes_merton_model'
  - '#compound_option_pricing'
  - '#dividend_payments'
  - '#early_exercise'
  - '#ex_dividend_date'
---
# 19.3 RECAP AND PREVIEW

In this chapter, we looked at the pricing of American call options. We had previously learned how to price them using the binomial model, but here we see that a closed-form. solution, which uses the compound option pricing model, is possible. We saw that the complicating factor is the existence of a dividend during the life of the option. The model must accommodate whether the holder exercises early to get the dividend or holds on to the option. The bivariate normal distribution is used to accommodate the existence of two exercise decisions-the one early and the one at expiration. Multiple dividends can be handled using a multivariate normal distribution..

In Chapter 20, we show that this approach can also be applied to put options.

# APPENDIX 19A

# Numerical Example of the One-Dividend Model

Consider a stock priced at $S=100$ with a volatility of. $20\%$ and a time to expiration of $\tau_{A}=1$ (one year). Suppose in nine months, the stock pays a dividend of 2.0. Thus,. $D_{1}=2.0$ , and $\tau_{1}=0.75$ . The continuously compounded risk-free rate is $4\%$ . Let us first calculate the price if this option were European. Recall that we determine the stock price minus the present value of the dividends, which is.

$$
S_{t}-D e^{-r_{c}\tau_{1}}=100-2e^{-0.04(0.75)}=98.0591.
$$

We then insert this value for the stock price into the Black-Scholes-Merton formula, and we obtain a value of 8.7622..

For the compound option model, we must first find the critical ex-dividend price for early exercise. Remember that we are looking for a stock price,. $S^{*},$ that forces the value of a standard European option to equal, $S^{*}+D-X=S^{*}+2-100=S^{*}-98$ By trial and error, we find that this price is 108.5172. To demonstrate that this is true, simply. plug 108.5172 into the Black-Scholes-Merton model with time to expiration of 0.25. We would obtain 10.5197. Then find. $S^{*}-98=108.5172-98=10.5172$ These values are close enough.5

Recall that the American call formula is Equation (19.11), which is as follows:

$$
\begin{array}{r l r}&{}&{\left(100-2e^{-0.04(0.75)}\right)N_{1}{\left(b_{1}\right)}+\left(100-2e^{-0.04(0.75)}\right)N_{2}{\left(a_{1},-b_{1};-\rho\right)}}\ &{}&{-100e^{-0.04(1)}N_{2}{\left(a_{2},-b_{2};-\rho\right)}-\left(100-2\right)e^{-0.04(0.75)}N_{1}{\left(b_{2}\right)}.}\end{array}
$$

The various values that go into the normal probabilities are as follows:

$$
a_{1}=\frac{\ln\left[\left(100-2e^{-0.04(0.75)}\right)/100\right]+\left(0.04+(0.2)^{2}/2\right)(1)}{0.2\sqrt{1}}=0.202001
$$

$$
b_{1}=\frac{\ln\left[\left(100-2e^{-0.04(0.75)}\right)/108.5172\right]+\left(0.04+\left(0.2\right)^{2}/2\right)\left(0.75\right)}{0.2\sqrt{0.75}}=-0.32527
$$

Now we calculate the probabilities using spreadsheet routines as covered in Chapter 5:

$$
\begin{array}{c}{N_{1}(b_{1})=N_{1}(-0.32527)=0.372489}\ {N_{2}\big(a_{1},-b_{1};-\rho\big)=N_{2}(0.202001,0.32527;-0.8660)=0.224492}\end{array}
$$

$$
N_{2}{\left(a_{2},-b_{2};-\rho\right)}=N_{2}(0.002001,0.49847;-0.8660)=0.209849
$$

$$
N_{1}\left(b_{2}\right)=N_{1}(-0.49847)=0.309075.
$$

The option value is, therefore,

$$
98.0591(0.372489)+98.0591(0.224492)
$$

$$
-100e^{-0.04(1)}0.209849-(100-2)e^{-0.04(0.75)}(0.309075)
$$

# QUESTIONS AND PROBLEMS

1 "An American call option on a stock that does not pay a dividend during the life of the option will not be exercised early and, hence, can be valued as a European option with the standard Black-Scholes-Merton formula." Prove this statement.

2 An American call option with one dividend payment can be valued based on the following equation. Provide an interpretation of this expression:.

$$
\begin{array}{l}{{C=\left(S-D e^{-r_{c}\tau_{1}}\right)N_{1}{\left(b_{1}\right)}-\left(X-D\right)e^{-r_{c}\tau_{1}}N_{1}{\left(b_{2}\right)}}}\ {{\qquad+\left(S-D e^{-r_{c}\tau_{1}}\right)N_{2}{\left(a_{1},-b_{1};-\rho\right)}-X e^{-r_{c}\tau_{A}}N_{2}{\left(a_{2},-b_{2};-\rho\right)}.}}\end{array}
$$

3Explain the variable,. $S_{t}^{*}$ , contained in the American call option model with one dividend presented in this chapter..

4Explain the variables $S_{t_{1}}^{*}$ and $S_{t_{2}}^{*}$ contained in the American call option model with two dividends presented in this chapter.

5 Interpret the variable $N_{3}(x,y,z;\rho_{x y},\rho_{x z},\rho_{y z})$ contained in the American call option model with two dividends presented in this chapter.

6[Contributed by Jason Priddle] Explain why it is necessary to use a compound option to value an American call on a dividend-paying stock.

7[Contributed by Dennel McKenzie] Write out the equations that implicitly solve for the critical stock price for early exercise of an American call if the underlying stock pays three dividends, $D_{1},D_{2}$ , and $D_{3}$ , with respective times with ex-dividend dates of. $t_{1},t_{2}$ , and $t_{3}$ . There will be three equations, one for each ex-dividend date.

# NOTES

1. It is well known that the lower bound of an American call on an asset that makes cash payments is. $S-P V\left(X\right)-P V\left(D\right)$ where $S$ is the current asset price, $\operatorname{PV}(X)$ is the present value of the exercise price, and $\mathrm{PV}(D)$ is the present value of the cash payments (dividends) over the life of the option.. If this option were exercised, it would give a payoff of. $S-X$ . Clearly if $X-P V\left(X\right)>P V\left(D\right)$ meaning, the interest forgone on paying the exercise price early exceeds the benefit of the divi-. dends, early exercise will not be justified. This scenario will occur with a combination of small

cash payments, a high interest rate, and a high exercise price. Because such options will not be exercised early, they can, therefore, be valued using the Black-Scholes-Merton model with the asset price reduced by the present value of the dividends. Because this condition is not always met, it could be possible to justify early exercise.
2. For stocks, the relevant date is the ex-dividend date, because that is the date on which the stock price falls to reflect the fact that anyone holding the stock after that time forgoes the dividend. If the ex-dividend day is 35 days from now, $\tau_{1}=35/365$ . We ignore the delay between the ex-dividend date and the actual payment date a few weeks later.
3. Roll (1977) assumed that the asset price follows the lognormal diffusion, but this cannot be true if the dividend component of the asset price is non-stochastic. This correction was made by Whaley. (1981). In other words, the statistical process that follows a lognormal diffusion is the asset price. minus the present value of the dividends..
4. We use $\hat{\boldsymbol{c}}$ to distinguish these values from the call price.
5. How close we make them depends on what we tell the iterative technique about how close is close enough so that it can stop. Here we are within a tenth of a penny..

# American Put Option Pricing

n this chapter, we take a look at American put options. It is well known that irrespective of any dividends or cash payouts on the underlying, it could be optimal to exercise an. American put option early. Dividends, in fact, reduce the likelihood of early exercise, but. they do not eliminate it..
