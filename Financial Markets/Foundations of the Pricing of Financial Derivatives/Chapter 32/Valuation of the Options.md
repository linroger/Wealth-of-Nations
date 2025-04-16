---
tags:
  - '#black_scholes_merton_model'
  - '#call_option_premium'
  - '#currency_options_valuation'
  - '#domestic_interest_rate'
  - '#euro_exchange_rate'
  - '#foreign_interest_rate'
  - '#numerical_example'
  - '#option_valuation_formula'
  - '#put_option_premium'
---
# 32.3 VALUATION OF THE OPTIONS

Now we demonstrate how the premiums of these two options are equivalent in the BlackScholes-Merton model. The BSM value of the call option is.

$$
c=S_{0}e^{-r_{F}\tau}N\big(d_{1}^{D}\big)-X e^{-r_{D}\tau}N\big(d_{2}^{D}\big),
$$

where

$$
\begin{array}{l}{{d_{1}^{D}=\frac{\displaystyle\ln\left(\frac{S_{0}e^{-r_{F}\tau}}{X e^{-r_{D}\tau}}\right)+\left(\frac{\sigma^{2}}{2}\right)\tau}{\sigma\sqrt{\tau}}}}\ {{d_{2}^{D}=d_{1}^{D}-\sigma\sqrt{\tau}.}}\end{array}
$$

Note that we use the $D$ superscript on the normal distribution function to indicate that this is the normal probability for the call written on the foreign currency and denominated in the domestic currency. That is, it is being viewed from the domestic standpoint.

We now provide a numerical example: Suppose the euro exchange rate is $\$1.15$ per euro, the exercise price is. $\$1.14$ per euro, the time to maturity is 0.25, the domestic US. interest rate is $0.8815\%$ , the foreign euro interest rate is. $0.4\%$ , and the volatility is. $15\%$ First, solving for the values of $d_{1}^{D}$ and $d_{2}^{D}$ , we havee

$$
d_{1}^{D}={\frac{\ln\left({\frac{S_{0}e^{-r_{F}\tau}}{X e^{-r_{D}\tau}}}\right)+\left({\frac{\sigma^{2}}{2}}\right)\tau}{\sigma{\sqrt{\tau}}}}={\frac{\ln\left({\frac{1.15e^{-(0.00813)0.25}}{1.14e^{-(0.008815)0.25}}}\right)+\left({\frac{0.15^{2}}{2}}\right)0.25}{0.15{\sqrt{0.25}}}}=0.17
$$

$$
d_{2}^{D}={\frac{\ln\left({\frac{S_{0}e^{-r_{F}\tau}}{X e^{-r_{D}\tau}}}\right)-\left({\frac{\sigma^{2}}{2}}\right)\tau}{\sigma{\sqrt{\tau}}}}={\frac{\ln\left({\frac{1.15e^{-(0.004)0.25}}{1.14e^{-(0.008815)0.25}}}\right)-\left({\frac{0.15^{2}}{2}}\right)0.25}{0.15{\sqrt{0.25}}}}=0.095.
$$

Based on Table 5.1: Standard Normal Cumulative Distribution Function Table, we have

$$
\begin{array}{r l}&{c=S_{0}e^{-r_{F}\tau}N\big(d_{1}^{D}\big)-X e^{-r_{D}\tau}N\big(d_{2}^{D}\big)}\ &{\quad=1.15e^{-(0.004)0.25}(0.567495)-1.14e^{-(0.008815)0.25}(0.537843)=0.0402.}\end{array}
$$

As we stated, this call is equivalent to $X$ puts written on the domestic currency denominated in the foreign currency with a strike of $X_{R}=1/X$ We now validate that this result is upheld in the BSM model.

From the foreign investor's perspective, the value of a single unit of the reciprocal put is

$$
\begin{array}{r}{p_{R}=X_{R}e^{-r_{F}\tau}\big[1-N\big(d_{2}^{F}\big)\big]-R_{0}e^{-r_{D}\tau}\big[1-N\big(d_{1}^{F}\big)\big],}\end{array}
$$

where $\scriptstyle{p_{R}}$ is denominated in the foreign currency and2

$$
\begin{array}{r l}&{d_{1}^{F}=\frac{\ln\left(\frac{R_{0}e^{-r_{D}\tau}}{X_{R}e^{-r_{F}\tau}}\right)+\left(\frac{\sigma^{2}}{2}\right)\tau}{\sigma\sqrt{\tau}}}\ &{d_{2}^{F}=\frac{\ln\left(\frac{R_{0}e^{-r_{D}\tau}}{X_{R}e^{-r_{F}\tau}}\right)-\left(\frac{\sigma^{2}}{2}\right)\tau}{\sigma\sqrt{\tau}}.}\end{array}
$$

Before reconciling this put formula to the prior call formula, we circle back to our example. Recall the euro exchange rate is. $\$1.15$ per euro, or $\in0.869565$ per dollar, the

exercise price is $\$1.14$ per euro, or $\in0.877193$ per dollar, the time to maturity is 0.25, the domestic euro interest rate is $0.4\%$ , the foreign US interest rate is $0.8815\%$ , and the volatility is $15\%$ . Again, solving for the value of $d_{1}^{F}$ and $d_{2}^{F}$ , we have

$$
l_{1}^{t}=\frac{\ln\left(\displaystyle\frac{R_{0}e^{-r_{D}\tau}}{X_{R}e^{-r_{F}\tau}}\right)+\left(\displaystyle\frac{\sigma^{2}}{2}\right)\tau}{\sigma\sqrt{\tau}}=\frac{\ln\left(\displaystyle\frac{0.869565e^{-(0.004)0.25}}{0.877193e^{-(0.00815)0.25}}\right)+\left(\displaystyle\frac{0.15^{2}}{2}\right)0.25}{0.15\sqrt{0.25}}=-0.0
$$

Note how these are related to their corresponding call terms, a point we return to later.
Again based on Table 5.1 we have3.

$$
\begin{array}{r l}&{\boldsymbol{p}_{R}=X_{R}e^{-r_{F}\tau}\big[1-N\big(d_{2}^{F}\big)\big]-R_{0}e^{-r_{D}\tau}\big[1-N\big(d_{1}^{F}\big)\big]}\ &{\quad=0.877193e^{-(0.004)0.25}(1-0.432505)-0.869565e^{-(0/008815)0.25}(1-0.462157)}\ &{\quad=0.0306.}\end{array}
$$

Clearly, this put value of $\in0.0306$ is not equal to the call value of $\$0.0402$ , even after adjusting for the exchange rate.

Now let us examine why this is still the correct put formula at the core. In words, the BSM formula for the value of a put is the strike times the present value factor for the investor's currency times $1-N(d_{2}^{F})$ minus the underlying price in the investor's currency. times the present value factor for the yield on the currency, times $1-N(d_{2}^{F})$ . Thus, in the previous formula for $\boldsymbol{p}$ , the strike is properly designated as $X_{R}=1/X$ . The strike is then multiplied by the present value factor for the investor's currency. Because this put is being valued from the foreign investor's perspective, it is appropriate to discount the strike at the foreign rate. Then we use the normal probability based on $-d_{2}^{F}$ with the $F$ superscript to distinguish it from $d_{2}^{D}$ in the call. From the product of these three terms, we. subtract the exchange rate in foreign currency, $R_{0}=1/S_{0}$ , times the present value factor for the opposite currency. From the foreign investor's perspective, this rate is. $r_{D}$ . Then this product is multiplied by one minus the normal probability for. $d_{1}^{F}$

Now let us work with $d_{1}^{F}$ and $d_{2}^{F}$ . First, note the following:

$$
\begin{array}{r l}&{\ln\left(\frac{R_{0}e^{-r_{D}\tau}}{X_{R}e^{-r_{F}\tau}}\right)=\ln\left(\frac{\frac{1}{S_{0}}e^{-r_{D}\tau}}{\frac{1}{X}e^{-r_{F}\tau}}\right)}\ &{~=\ln1-\ln S_{0}-r_{D}\tau-\ln1+\ln X+r_{F}\tau}\ &{=-\ln S_{0}-r_{D}\tau+\ln X+r_{F}\tau}\ &{=-\ln\left(\frac{S e^{-r_{F}\tau}}{X e^{-r_{D}\tau}}\right).}\end{array}
$$

Thus,

$$
\begin{array}{r l}&{d_{1}^{F}=\frac{-\ln\left(\frac{S_{0}e^{-r_{F}\tau}}{X e^{-r_{D}\tau}}\right)+\left(\frac{\sigma^{2}}{2}\right)\tau}{\sigma\sqrt{\tau}}=-\left(\frac{\ln\left(\frac{S_{0}e^{-r_{F}\tau}}{X e^{-r_{D}\tau}}\right)-\left(\frac{\sigma^{2}}{2}\right)\tau}{\sigma\sqrt{\tau}}\right)=-d_{2}^{D}}\ &{d_{2}^{F}=\frac{-\ln\left(\frac{S_{0}e^{-r_{F}\tau}}{X e^{-r_{D}\tau}}\right)-\left(\frac{\sigma^{2}}{2}\right)\tau}{\sigma\sqrt{\tau}}=-\left(\frac{\ln\left(\frac{S_{0}e^{-r_{F}\tau}}{X e^{-r_{D}\tau}}\right)+\left(\frac{\sigma^{2}}{2}\right)\tau}{\sigma\sqrt{\tau}}\right)=-d_{1}^{D}.}\end{array}
$$

We saw this in the numerical calculations already. Therefore,

$$
\begin{array}{l}{{N\big(-d_{1}^{F}\big)=N\big(d_{2}^{D}\big)}}\ {{}}\ {{N\big(-d_{2}^{F}\big)=N\big(d_{1}^{D}\big).}}\end{array}
$$

Our put formula will, thus, be

$$
\begin{array}{r l}{\lefteqn{P_{R}=X_{R}e^{-r_{F}\tau}N\big(-d_{2}^{F}\big)-R_{0}e^{-r_{D}\tau}N\big(-d_{1}^{F}\big)}}\ &{\quad=X_{R}e^{-r_{F}\tau}N\big(d_{1}^{D}\big)-R_{0}e^{-r_{D}\tau}N\big(d_{2}^{D}\big)}\ &{\quad=\bigg(\frac{1}{X}\bigg)e^{-r_{F}\tau}N\big(d_{1}^{D}\big)-\bigg(\frac{1}{S_{0}}\bigg)e^{-r_{D}\tau}N\big(d_{2}^{D}\big).}\end{array}
$$

Recall that the isomorphic put is actually $X$ puts, so the aggregate put premium is

$$
\begin{array}{l l}{{}}&{{X p_{R}=X\displaystyle\left(\frac{1}{X}\right)e^{-r_{F}\tau}N\displaystyle(d_{1}^{D})-X\left(\frac{1}{S_{0}}\right)e^{-r_{D}\tau}N\displaystyle(d_{2}^{D})}}\ {{}}&{{~}}\ {{{\cal X}p_{R}=e^{-r_{F}\tau}N\displaystyle\left(d_{1}^{D}\right)-\left(\frac{X}{S_{0}}\right)e^{-r_{D}\tau}N\displaystyle\left(d_{2}^{D}\right)~\mathrm{(in{units~of}t h e~f o r e i g n~c u r r e n c y)}.}}\end{array}
$$

This value is in units of the foreign currency. To convert to the domestic currency, we simply multiply by $S_{0}$

$$
X p_{D}=S_{0}e^{-r_{F}\tau}N\bigl(d_{1}^{D}\bigr)-X e^{-r_{D}\tau}N\bigl(d_{2}^{D}\bigr)\mathrm{~(inunits~ofthe~domestic~currency).}
$$

This is the same as the right-hand side of the call formula.

Once again, we illustrate the correspondence between models with our numerical example. Recall

$$
\begin{array}{l}{c=S_{0}e^{-r_{F}T}N\big(d_{1}^{D}\big)-X e^{-r_{D}T}N\big(d_{2}^{D}\big)}\ {=1.15e^{-(0.004)0.25}(0.567495)-1.14e^{-(0.008815)0.25}(0.537843)=50.0402}\end{array}
$$

and

$$
\begin{array}{r l}&{\boldsymbol{p}_{R}=X_{R}e^{-r_{F}T}\bigl[1-N\bigl(d_{2}^{F}\bigr)\bigr]-R_{0}e^{-r_{D}T}\bigl[1-N\bigl(d_{1}^{F}\bigr)\bigr]}\ &{\quad=0.877193e^{-(0.004)0.25}(1-0.432505)-0.869565e^{-(0.008815)0.25}(1-0.462157)}\ &{\quad=0.03066.}\end{array}
$$

Assuming we purchase $X=1.14$ puts and then convert to USD, we note that $S_{0}X\boldsymbol{p}=$ (\$1.15/)(1.14) $\in0.0306=\S0.0402$ This numerical example highlights the two different ways to express currency options..
