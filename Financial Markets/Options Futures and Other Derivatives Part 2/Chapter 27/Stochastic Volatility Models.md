---
tags:
  - '#black_scholes_merton_model'
  - '#fractional_brownian_motion'
  - '#garch_1_1_model'
  - '#heston_model'
  - '#implied_volatility'
  - '#monte_carlo_simulation'
  - '#rough_volatility_models'
  - '#sabr_model'
  - '#stochastic_volatility_models'
  - '#variance_gamma_model'
---
# 27.2 STOCHASTIC VOLATILITY MODELS  

The Black-Scholes-Merton model assumes that volatility is constant. In practice, as discussed in Chapter 23, volatility varies through time. The variance-gamma model reflects this with its $g$ variable. Low values of $g$ correspond to a low arrival rate for information and a low volatility; high values of $g$ correspond to a high arrival rate for information and a high volatility.  

An alternative to the variance-gamma model is a model where the process followed by the volatility variable is specified explicitly. Suppose first that the volatility parameter. in the geometric Brownian motion is a known function of time. The risk-neutral process followed by the asset price is then.  

$$
d S=(r-q)S d t+\sigma(t)S d z
$$  

The Black-Scholes-Merton formulas are then correct provided that the variance rate is set equal to the average variance rate during the life of the option (see Problem 27.6). The variance rate is the square of the volatility. Suppose that during a 1-year period the volatility of a stock will be $20\%$ during the first 6 months and $30\%$ during the second 6 months. The average variance rate is  

$$
0.5\times0.20^{2}+0.5\times0.30^{2}=0.065
$$  

It is correct to use Black-Scholes-Merton with a variance rate of 0.065. This corre sponds to a volatility of $\sqrt{0.065}=0.255$ $25.5\%$  

Equation (27.1) assumes that the instantaneous volatility of an asset is perfectly predictable. In practice, volatility varies stochastically. This has led to the develop-. ment of more complex models with two stochastic variables: the stock price and its volatility.  

One model that has been used by researchers is  

$$
\begin{array}{l}{d S/S=(r-q)d t+\sqrt{V}d z_{S}}\ {d V=a(V_{L}-V)d t+\xi V^{\alpha}d z_{V}}\end{array}
$$  

where $a,V_{L},\xi$ , and $\alpha$ are constants, and $d z_{S}$ and $d z_{V}$ are Wiener processes. The variable $V$ in this model is the asset's variance rate. The variance rate has a drift that pulls it back to a level $V_{L}$ at rate $a$  

Hull and White show that, when volatility is stochastic but uncorrelated with the asset price, the price of a European option is the Black-Scholes-Merton price integrated over the probability distribution of the average variance rate during the life of the option.7 Thus, a European call price is  

$$
\int_{0}^{\infty}c({\overline{{V}}})g({\overline{{V}}})d{\overline{{V}}}
$$  

where $\overline{V}$ is the average value of the variance rate, $c$ is the Black-Scholes-Merton price. expressed as a function of. $\overline{V}$ , and $g$ is the probability density function of $\overline{V}$ in a riskneutral world. This result can be used to show that Black-Scholes-Merton overprices options that are at the money or close to the money, and underprices options that are deep-in-or deep-out-of-the-money. The model is consistent with the pattern of implied volatilities observed for currency options (see Section 20.2).  

The case where the asset price and volatility are correlated is more complicated. Option. prices can be obtained using Monte Carlo simulation. In the particular case where $\alpha=0.5$ , Hull and White provide a series expansion and Heston provides an analytic result.8 The pattern of implied volatilities obtained when the volatility is negatively. correlated with the asset price is similar to that observed for equities (see Section 20.3).9  

Chapter 23 discusses exponentially weighted moving average (EWMA) and. GARCH(1,1) models. These are alternative approaches to characterizing a stochastic volatility model. Duan shows that it is possible to use GARCH(1,1) as the basis for an internally consistent option pricing model.10 (See Problem 23.14 for the equivalence of. GARCH(1,1) and stochastic volatility models.)  

# The SABR Model  

A stochastic volatility model that has become very popular with practitioners for valuing European options (particularly interest rate options) maturing at a particular time $T$ is the SABR model developed by Hagan et al. (2002).11 The advantage of the.  

model is that it can fit the volatility smiles observed in practice reasonably well and is useful for managing risks associated with movements in the smile through time.  

The model is  

$$
\begin{array}{c}{{d F=\sigma F^{\beta}d z}}\ {{d\sigma}}\ {{\sigma}}\end{array}
$$  

where $F$ is a forward interest rate or the forward price of an asset, $d z$ and $d w$ are Wiener processes, $\sigma$ is the stochastic volatility, and $\beta$ and $\nu$ are constants.12 Three other parameters are $\rho$ , the correlation between $d z$ and $d w$ $\sigma_{0}$ , the initial value of $\sigma$ , and $F_{0}$ the initial value of $F$  

Hagan et al. derive an approximate formula for the Black-model implied volatility given by SABR for a European option with strike price. $K$ (see Sections 18.7 and 18.8 for Black's model). Define.  

$$
\begin{array}{r c l}{{}}&{{}}&{{x=(F_{0}K)^{(1-\beta)/2},\qquady=(1-\beta)\ln(F_{0}/K)}}\ {{}}&{{}}&{{A=\displaystyle{\frac{\sigma_{0}}{x(1+y^{2}/24+y^{4}/1920)}},\qquadB=1+\bigg(\displaystyle{\frac{(1-\beta)^{2}\sigma_{0}^{2}}{24x^{2}}}+\displaystyle{\frac{\rho\beta\nu\sigma_{0}}{4x}}+\displaystyle{\frac{2-3\rho^{2}}{24}}\nu^{2}\bigg)T}}\ {{}}&{{}}&{{\phi=\displaystyle{\frac{\nu x}{\sigma_{0}}\ln\bigg(\displaystyle{\frac{F_{0}}{K}}\bigg)},\qquad\chi=\ln\bigg(\displaystyle{\frac{\sqrt{1-2\rho\phi+\phi^{2}}+\phi-\rho}{1-\rho}}\bigg)}}\end{array}
$$  

The implied volatility is $A B\phi/\chi$ If $F_{0}=K$ , this becomes. $\sigma_{0}B/(F_{0}^{1-\beta})$ 13  

The parameter $\sigma_{0}$ defines the level of the volatility. (It is roughly equivalent to the volatility estimate in the usual lognormal model multiplied by $F_{0}^{1-\beta}$ .) The parameter $\rho$ defines the shape of the smile. For a large positive $\rho$ , the smile is upward sloping; for a large negative $\rho$ , it is downward sloping; and for intermediate values of $\rho$ , it is U-shaped. As the parameter $\nu$ increases, the smile become more accentuated. (See Problem 27.23.) The SABR model is implemented in DerivaGem 4.00.  

Often $\beta$ is chosen equal to 0.5 in interest rate applications of the SABR model. The. parameters $\rho,\sigma_{0}$ and $\nu$ that fit the smile typically depend on the maturity $T$ being considered. However, as mentioned earlier, the model has proved a useful way of managing the risks in smile movements.  

# Rough Volatility Models  

In Section 14.8, we introduced fractional Brownian motion. Gatheral, Jaisson, and Rosenbaum (2018) argue that fractional Brownian motion gives a better description of the behavior of volatility than regular Brownian motion.14 Using high-frequency data, they find that a Hurst exponent between 0.06 and 0.20 fits the behavior of a range of different stock indices well. It also fits the volatility surfaces that are observed in practice better than simpler stochastic volatility models. Models which are based on fractional Brownian motion are known as rough volatility models..  

One well-known rough volatility model is referred to as "rough Heston." It has the. advantage of being analytically tractable. The original Heston model is given by equations (27.2) and (27.3) with $\alpha=0.5$ and can be written as  

$$
\begin{array}{l}{\displaystyle\frac{d S_{t}}{S_{t}}=(r-q)d t+\sqrt{V_{t}}(\rho d z_{t}+\sqrt{1-\rho^{2}}d w_{t})}\ {\displaystyle d V_{t}=a(V_{L}-V_{t})d t+\xi\sqrt{V_{t}}d z_{t}}\end{array}
$$  

where $d{z_{t}}$ and $d w_{t}$ are uncorrelated Wiener processes and $\rho$ is the correlation between the stock price and its volatility. In the rough Heston model the process followed by the variance rate involves fractional Brownian motion rather than regular Brownian motion.  

To value exotic options it is often necessary use Monte Carlo simulation. As. explained in Section 14.8, in fractional Brownian motion the change in a future time. period must be simulated so that it has the right correlation with changes in all previous time periods. This is computationally very slow and has led Jaber (2019) to suggest the lifted Heston model, which imitates rough Heston using only regular. Brownian motion.15  
