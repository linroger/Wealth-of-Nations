---
tags:
  - '#arbitrage_free_price'
  - '#asset_pricing'
  - '#black_scholes_merton_model'
  - '#capital_asset_pricing_model_capm'
  - '#expected_return'
  - '#option_pricing'
  - '#required_return'
  - '#risk_premium'
---
# 30.1 THE BASIC FRAMEWORK

The CAPM is as follows:

$$
\begin{array}{r}{E\big(R_{s}\big)=r+\big[E\big(R_{m}\big)-r\big]\beta_{s},}\end{array}
$$

where

$$
\frac{\mathrm{cov}\bigl(R_{s},R_{m}\bigr)}{\mathrm{var}\bigl(R_{m}\bigr)}
$$

$\mathrm{cov}\left(\mathrm{R}_{s},R_{m}\right)=\mathrm{}$ covariance betweeen return on asset $s$ and market portfolio m $\sigma_{m}^{2}=$ variance of the return on market portfolio $^m$

Note that here we use the terms expected return and required return interchangeably.. As noted, the expected return is the return the investor expects, given the market price.. The required return is the return that is justified given the risk. The latter assumes the. market is in equilibrium, along with a number of other assumptions. Although the CAPM technically gives the required return, this rate is usually referred to as the expected return,. as noted by the use of the expectations operator.

The CAPM is not typically expressed in the form of the price of an asset, though that can be done using a model specifying how the asset price is obtained from its future cash flow. For example, define the one-period return on an asset $S$ as

$$
R_{s}=\frac{S^{\prime}}{S}-1,
$$

where $S^{\bullet}$ is the asset price one period later.2 The expected return would be

$$
E\big(R_{s}\big)=\frac{E\big(S^{\prime}\big)}{S}-1.
$$

Note that Equations (30.1) and (30.3) both provide the expected return, the left-hand side, in terms of an expression on the right-hand side. Using the definition of beta as stated and equating these two specifications for the expected return, we have.

$$
\frac{E\big(R_{s}\big)}{S}-1=r+\big[E\big(R_{m}\big)-r\big]\frac{\mathrm{cov}\big(R_{s},R_{m}\big)}{\sigma_{m}^{2}}.
$$

Given the rules for covariance, we can also say that

$$
\begin{array}{c}{\displaystyle{\mathrm{cov}\big(R_{s},R_{m}\big)=\mathrm{cov}\bigg(\frac{S^{\prime}}{S}-1,R_{m}\bigg).}}\ {\displaystyle{=\frac{1}{S}\mathrm{cov}\big(S^{\prime},R_{m}\big).}}\end{array}
$$

We can substitute this result into (30.4) and solve for $S$ to obtain

$$
S=\frac{E\big(S^{\prime}\big)-\lambda\mathrm{cov}\big(S^{\prime},R_{m}\big)}{1+r},
$$

where

$$
\lambda=\frac{E\bigl(R_{m}\bigr)-r}{{\sigma_{m}}^{2}}.
$$

This equation is the CAPM written in the form of a price. In the numerator, we have the expected value of the asset at the next date,. $E\big(S^{\prime}\big)$ minus the risk premium, $\lambda\mathrm{cov}\left(S^{\prime},R_{m}\right)$ The term $\lambda$ is the market risk premium and reflects the average level of risk in the market. The numerator is a risk-adjusted future value of the asset, which is then discounted by the. risk-free rate to obtain the price. Financial economists typically refer to this form of the model as a certainty equivalent, a concept that we have previously encountered.3

Option pricing models, in contrast to asset pricing models, are nearly always written in the form of a price. In the case of Black-Scholes-Merton, which we derived in Chapter 13, the price is, of course,

$$
\begin{array}{r}{c=S N\big(d_{1}\big)-X e^{-r_{c}\tau}N\big(d_{2}\big),}\end{array}
$$

where

$$
d_{1}=\frac{\ln(S/X)+\left(r_{c}+\sigma^{2}/2\right)\tau}{\sigma\sqrt{\tau}},
$$

and

$$
d_{2}={\frac{\ln(S/X)+\left(r_{c}-\sigma^{2}/2\right)\tau}{\sigma{\sqrt{\tau}}}}=d_{1}-\sigma{\sqrt{\tau}}.
$$

As you should recall, the Black-Scholes-Merton model is obtained in continuous time by forming a risk-free hedge consisting of the underlying asset and the option. The option price formula is derived as the solution given the constraint that the riskless portfolio must earn the risk-free rate to prevent arbitrage.

It is rare that the option pricing model is expressed in the form of the expected return of the option. We provide the linkage between the notion of an equilibrium expected return and an arbitrage-free price of a call option. The same result can be obtained if the option is a put with nothing but minor notational changes.
