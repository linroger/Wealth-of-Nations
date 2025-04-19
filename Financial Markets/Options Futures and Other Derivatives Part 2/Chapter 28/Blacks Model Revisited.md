---
tags:
  - asset_pricing
  - black_model
  - european_options
  - forward_price
  - option_pricing
  - stochastic_interest_rates
aliases:
  - Black's Model
  - European Option Pricing
key_concepts:
  - Black's model pricing
  - European call option
  - Forward asset price volatility
  - Forward price asset
  - Stochastic interest rates
---

# 28.6 BLACK'S MODEL REVISITED  

Section 18.8 explained that Black's model is a popular tool for pricing European. options in terms of the forward or futures price of the underlying asset when interest rates are constant. We are now in a position to relax the constant interest rate assumption and show that Black's model can be used to price European options in terms of the forward price of the underlying asset when interest rates are stochastic.  

Consider a European call option on an asset with strike price $K$ that lasts until time $T$ From equation (28.20), the option's price is given by.  

$$
c=P(0,T)E_{T}[\operatorname*{max}(S_{T}-K,0)]
$$  

where $S_{T}$ is the asset price at time $T$ and $E_{T}$ denotes expectations in a world defined by. numeraire $\textstyle P(t,T)$ . Define $F_{0}$ and $F_{T}$ as the forward price of the asset at time O and time $T$ for a contract maturing at time $T$ Because $S_{T}=F_{T}$  

$$
c=P(0,T)E_{T}[\operatorname*{max}(F_{T}-K,0)]
$$  

Assume that $F_{T}$ is lognormal in the world being considered, with the standard deviation of $\ln(F_{T})$ equal to $\bar{\sigma_{F}}\sqrt{T}$ This could be because the forward price follows a stochastic process with volatility. $\sigma_{F}$ Equation (15A.1) shows that  

$$
E_{T}[\operatorname*{max}(F_{T}-K,0)]=E_{T}(F_{T})N(d_{1})-K N(d_{2})
$$  

where  

$$
\begin{array}{l}{{d_{1}={\frac{\ln[E_{T}(F_{T})/K]+\sigma_{F}^{2}T/2}{\sigma_{F}{\sqrt{T}}}}}}\ {{d_{2}={\frac{\ln[E_{T}(F_{T})/K]-\sigma_{F}^{2}T/2}{\sigma_{F}{\sqrt{T}}}}}}\end{array}
$$  

From equation (28.21), $E_{T}(F_{T})=E_{T}(S_{T})=F_{0}.$ Hence,  

$$
c=P(0,T)[F_{0}N(d_{1})-K N(d_{2})]
$$  

where  

$$
\begin{array}{l}{{d_{1}={\displaystyle\frac{\ln[F_{0}/K]+\sigma_{F}^{2}T/2}{\sigma_{F}\sqrt{T}}}}}\ {{d_{2}={\displaystyle\frac{\ln[F_{0}/K]-\sigma_{F}^{2}T/2}{\sigma_{F}\sqrt{T}}}}}\end{array}
$$  

Similarly,  

$$
p=P(0,T)[K N(-d_{2})-F_{0}N(-d_{1})]
$$  

where $p$ is the price of a European put option on the asset with strike price $K$ and time to maturity $T$ This is Black's model. It applies to both investment and consumption assets and, as we have just shown, is true when interest rates are stochastic provided that $F_{0}$ is the forward asset price for a contract with the same maturity as the option. The variable $\sigma_{F}$ can be interpreted as the volatility of the forward asset price.  
