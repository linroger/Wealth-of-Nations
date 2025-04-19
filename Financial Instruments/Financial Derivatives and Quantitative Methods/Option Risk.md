---
title: Option Risk
tags:
  - binomial_model
  - call_option
  - elasticity
  - option_risk
  - volatility
aliases:
  - Option Risk
  - Option Risk Notes
  - Risk of an Option
key_concepts:
  - Binomial model risk
  - Call option elasticity
  - Expected return calculation
  - Option risk and CAPM
  - Stock volatility
---

# Option Risk

### Introduction

In these notes,  we consider the risk of an option and relate it to the standard capital asset pricing model. If we are simply interested in valuing the option,  then we can largely ignore this issue. We have seen from our notes on the one-period binomial model that to price an option,  we only need to know the price of the underlying asset. It is not necessary to know whether the underlying asset is priced fairly relative to other assets or indeed anything about other assets at all. However,  if we are interested in forming an investment portfolio that includes options or other derivatives,  then the risk and return of that portfolio will depend on the risk and return characteristics of the options. Thus,  we will need to know how the $\beta$ of an option relates to the $\beta$ of the underlying stock.

We can examine the issue of risk in a simple binomial model. So,  this is what we shall do. Most textbooks on options don’t discuss risk,  and therefore,  you will need to keep these notes for your revision.

## Risk in the binomial model

We'll use the simple example we used when discussing the one-period binomial model. Suppose the price of the underlying stock is 100 and at the end of the period it has either risen to 175 or has fallen to 75. That is $u=0.75$ and $d=-0.25$ ,  so that the value of the stock after one period in the up state is $100 (1+u)=175$ and the value in the down state is $100 (1+d)=75$. The net growth rate of the value of the stock in the up state is $75\%$ ,  and the net growth in the value of the stock in the down state is $-25\%$.

We showed that in determining the price of the option,  the probability that the stock price rises or falls was irrelevant. Now,  however,  suppose that the true probability of the up state is $\pi$ = 4/5 and the probability of the down state is $(1-\pi)=1/5$. The expected rate of return on the stock is therefore $\mu_{S}=(4/5) 75+(1/5)(-25)=55\%$ and with an interest rate of $25\%$ the excess over the risk-free rate is $\mu_{S}-r=55-25=30\%$. Given that the price of the call is 30,  the rate of return on the call option is (75-30)/30 or $150\%$ in the up state and $-100\%$ in the down state. Thus,  the expected rate of return on the call option is $\mu_{C}=100\%$ and the excess return over the risk-free rate is $\mu_{C}-r=75\%$. Thus,  the excess return on the call is 2.5 times the excess return on the underlying asset. We know that this extra return will only come at the cost of extra risk.

The standard deviation of the rate of return on the stock is often simply referred to as the stock's volatility. The volatility of the stock is

$$\sigma_S=\sqrt{\frac{4}{5}(75-55)^2+\frac{1}{5}(-25-55)^2}=40\%$$

And the standard deviation of the rate of return on the call option,  or the call's volatility is

$$\sigma_C=\sqrt{\frac{4}{5}(150-100)^2+\frac{1}{5}(-100-100)^2}=100\%.$$

Thus the standard deviation of the call returns is again 2.5 times the standard deviation of the stock returns.

Now remember that $\Delta$ measures the responsiveness of the value of the call to changes in the value of the stock. In our example,  $\Delta=3/4$. It is natural to measure this change in percentage terms. That is,  we define

$$\Omega\equiv\frac{S}{c}\Delta $$

To be the elasticity of the option,  that is,  the percentage change in the call value relative to a given percentage change in the stock value. In our example,  $S=100$ and $c=30$ ,  so that $\Omega=2.5$

This is not a coincidence. If 711 is the probability of the up state and $1-\pi$ is the probability of the down state,  then the expected rate of return on the stock and its volatility are:

$$\mu_S=\pi u+(1-\pi) d\quad\text{and}\quad\sigma_S=\sqrt{\pi (1-\pi)}(u-d).$$

Equally,  the expected rate of return on the call and its volatility are

$$\mu_C=\frac{\pi c_u+(1-\pi) c_d-c}{c}\quad\mathrm{and}\quad\sigma_C=\sqrt{\pi (1-\pi)}\frac{c_u-c_d}{c}.$$

Then,  remembering that $\Delta$ is the change in the call price over the change in the stock price,  we have

$$\Omega\equiv\frac{S}{c}\Delta=\frac{S}{c}\frac{c_{u}-c_{d}}{(u-d) S}=\frac{c_{u}-c_{d}}{c (u-d)}.$$

It is therefore clear using the expressions above for $0 C$ and $0 S$ that

$$\sigma_C=\Omega\sigma_S.$$

Thus the ratio of the call and stock volatilities is exactly the option elasticity.

Remember that in synthesizing the call option we used the equations

$$\Delta (1+u) S+(1+r) B=c_u$$

$$\Delta (1+d) S+(1+r) B=c_d.$$

To show that the call price is $c=\Delta S+B$,  we can therefore substitute for $B=c-\Delta S$ to write these two equations as

$$\Delta (1+u) S-c_u=(1+r)(\Delta S-c)$$

$$\Delta (1+d) S-c_{d}=(1+r)(\Delta S-c).$$

Multiplying the first equation by 71 and the second equation by $(1-\pi)$ and adding the resulting two equations gives

$$\pi (\Delta (1+u) S-c_u)+(1-\pi)(\Delta (1+d) S-c_d)=(1+r)(\Delta S-c).$$

Then dividing by $C$, using the definition of $\Omega$ = $\Delta ( S/ c)$,  and after some rewriting gives

$$\mu_C-r=\Omega (\mu_S-r)$$

Or

$$\mu_C=r+\left (\frac{\mu_S-r}{\sigma_S}\right)\sigma_C.$$

This is,  of course,  the standard equation used to express an asset as a portfolio of the stock and the risk-free asset,  that we have seen previously in Asset Pricing and [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]]. As we know,  the call option can be replicated by a fraction of the stock and selling the risk-free asset; this should not be surprising. That is,  the risk and return of the call lie somewhere on the risk-return line with an intercept of 7 and a slope of $(\mu_{S}-r)/\sigma_{S}$. The elasticity $\Omega_{ 2}$ gives the position of the call along this line. Rewriting our equation on the excess return again:

$$\mu_C=\Omega\mu_S+(1-\Omega)r.$$

Thus,  the call can be seen as the portfolio of the stock and the risk-free asset with a weight of $\leq 2$ attached to the stock. Since we have seen that to synthesize the call requires borrowing the risk-free asset,  we have that $\Omega>1$ and the call volatility is always greater than the stock volatility.

This is seen in Figure 1. In the diagram,  the call option is always to the right of the underlying stock as it will have higher volatility and higher expected return than the underlying asset itself. It can also be seen that a call with a higher strike price will be more risky and therefore will lie further out along the risk and return line.

If the same analysis is repeated for a put option,  it is found that $\Delta$ is negative and $B$ is positive. This means that replicating the put option involves:

 ![500](./images/fS3aWRHCn97wSgeec43nok6ydwF4uck3Y.png)

Figure 1: RISK-RETURN DIAGRAM: $(\sigma,  \mu)$

Selling the underlying asset and buying the risk-free asset (investing). As the underlying asset is sold short,  a put option will be located on the lower arm of the risk-return diagram. The expected return is reduced because there is a future obligation from the short sale rather than a return,  although the obligations are still risky and therefore have a positive standard deviation. It can therefore be seen that put options are never of themselves efficient portfolios,  although since they will be negatively correlated with the underlying asset,  they can provide good hedging opportunities.

We now consider the $\beta$ of a call option. The Capital Asset Pricing Model shows that for any asset,  the excess return or risk-premium satisfies

$$\mu_S-r=\beta_S (\mu_M-r)$$

Where $\mu_{M}$ is the expected rate of return on the market portfolio and $\beta_{S}$ is the covariance of the stock's rate of return with the market divided by the variance of the rate of return on the market portfolio.

It is therefore simple to combine our excess return equation for the call and the CAPM formula to derive

$$\mu_C-r=\Omega\beta_S (\mu_M-r).$$

It can be shown that $\Omega\beta_{S}$ is the covariance of the rate of return of the call with the market divided by the variance of the rate of return of the market,  so that the beta of the call is $\beta_{C}=\Omega\beta_{S}$. The option beta is simply the elasticity of the beta of the underlying asset. Provided that $\beta_{S}>0$ ,  since $\Omega>1$ for a call option,  it is the case that $\beta_{C}>\beta_{S}$ and the beta for the call is higher than the beta of the underlying asset. 2 This is illustrated in Figure 2 which shows the security market line which plots expected return $\mu$ against $\beta$. The security market line intercepts the vertical axis at 7 the rate of return on the risk-free asset which is uncorrelated with the market return (as it is risk-less) and hence has a zero beta. Since $\Omega\geq 1$ the call option has a higher $\beta$ than the underlying asset and so lies to the right of the stock on the security market line. Put options on the other hand are anti-correlated with the stock,  their value goes up as the stock goes down,  so they have a negative $\beta$ and are located to the left of the risk-free asset on the security market line.

 ![500](./images/fldFEUqZq5HbQYGRmx1yNbXhTNK4pFgWx.png)

## Figure 2: SECURITY MARKET LINE: $(\beta,  \mu)$

Let's return once again to our simple example and suppose that the expected rate of return on the market portfolio is $40\%$. Then,  since the excess return on the stock is $30\%$ and the excess return on the market portfolio is $40-25=15\%$ ,  the beta of the stock is $\beta_{S}=2$ and the beta of the option is $\beta_{C}=\Omega\beta_{S}=5$. Since $\beta>0$ and the expected rate of return on the market portfolio is greater than the risk-free rate,  the expected rate of return on the call is also greater than the risk-free rate. Remember that the expected rate of return on the call using the risk-neutral probabilities is equal to the risk-free rate. Thus,  the risk-neutral probability for the up state is less than the true probability,  $p<\pi$. This simply reflects that in adjusting for the risk of the call,  the probability of the high rate of return is shaded downward to

reflect an aversion to risk. In our example,  the risk-neutral probability is 1/2 and the actual probability of the up state is 4/5.

## Summary

These notes have provided a connection between option pricing and standard models of [[Lecture 5- Dynamic Portfolio Choice|portfolio choice]] and the Capital Asset Pricing Model (CAPM). The connection is provided by the option elasticity $S_2$. We have seen previously that $\Delta$ measures how much of the stock to buy to create a riskless hedge or to replicate the option. The option elasticity,  $\leq 2$,  is a proportionate measure of $\Delta$,  $\Omega=S\Delta/c$. The elasticity $S_2$:therefore,  measures the proportion of the portfolio placed in the underlying asset in order to replicate the option. It is therefore a portfolio weight rather than a quantity of stock bought. The elasticity of the call option will be no less than one since to replicate the call option it will be necessary to borrow,  that is,  go short in the risk-free asset,  to fund the acquisition of the underlying asset. The elasticity also can be combined with the beta of the stock,  $\beta_S$,  to calculate the beta of the call option $\beta_C=\Omega\beta_C$. Since $\Omega\geq 1$,  the call option will be a more aggressive asset than the underlying stock.
