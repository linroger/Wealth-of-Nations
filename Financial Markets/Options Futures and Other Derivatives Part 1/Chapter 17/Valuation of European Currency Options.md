---
tags:
  - currency_options
  - european_options
  - exchange_rate
  - interest_rates
  - valuation
aliases:
  - Currency Options
  - European Currency Options
  - Valuation
key_concepts:
  - Foreign currency yield
  - Forward exchange rates
  - Pricing formulas
  - Put-call parity
  - Spot exchange rate
---

# 17.5 VALUATION OF EUROPEAN CURRENCY OPTIONS  

To value currency options, we define $S_{0}$ as the spot exchange rate. To be precise, $S_{0}$ is the value of one unit of the foreign currency in U.S. dollars. As explained in Section 5.10, a foreign currency is analogous to a stock paying a known dividend yield. The owner of foreign currency receives a yield equal to the risk-free interest rate, $r_{f},$ in the. foreign currency. Equations (17.1) and (17.2), with $q$ replaced by $r_{f},$ provide bounds for the European call price, $c$ , and the European put price, $p$  

$$
c\geq\operatorname*{max}(S_{0}e^{-r_{f}T}-K e^{-r T},0)\quad\mathrm{and}\quad p\geq\operatorname*{max}(K e^{-r T}-S_{0}e^{-r_{f}T},0)
$$  

Equation (17.3), with. $q$ replaced by $r_{f},$ provides the put-call parity result for Europear. currency options:  

$$
c+K e^{-r T}=p+S_{0}e^{-r_{f}T}
$$  

Finally, equations (17.4) and (17.5) provide the pricing formulas for European currency options when $q$ is replaced by $r_{f}$  

$$
\begin{array}{r l}{\lefteqn{c=S_{0}e^{-r_{f}T}N(d_{1})-K e^{-r T}N(d_{2})}}\ &{p=K e^{-r T}N(-d_{2})-S_{0}e^{-r_{f}T}N(-d_{1})}\end{array}
$$  

where  

$$
\begin{array}{l}{{d_{1}=\displaystyle\frac{\ln(S_{0}/K)+(r-r_{f}+\sigma^{2}/2)T}{\sigma\sqrt{T}}}}\ {{d_{2}=\displaystyle\frac{\ln(S_{0}/K)+(r-r_{f}-\sigma^{2}/2)T}{\sigma\sqrt{T}}=d_{1}-\sigma\sqrt{T}}}\end{array}
$$  

Both the domestic interest rate, $r$ , and the foreign interest rate, $r_{f}$ , are the rates for a. maturity $T$  

# Example 17.2  

Consider a 4-month European call option on the British pound. Suppose that the current exchange rate is 1.6000, the exercise price is 1.6000, the risk-free interest rate in the United States is $8\%$ per annum, the risk-free interest rate in Britain is $11\%$ per annum, and the option price is 4.3 cents. In this case, $S_{0}=1.6,K=1.6,r=0.08$ $r_{f}=0.11$ $T=0.3333$ , and $c=0.043$ . The implied volatility can be calculated by trial and error. A volatility of. $20\%$ gives an option price of 0.0639; a volatility of $10\%$ gives an option price of 0.0285; and so on. The implied volatility is $14.1\%$  

Put and call options on a currency are symmetrical in that a put option to sell one unit of currency A for currency B at strike price $K$ is the same as a call option to buy $K$ units of B with currency A at strike price $1/K$ (see Problem 17.12).  

# Using Forward Exchange Rates  

Because banks and other financial institutions trade forward contracts on foreign exchange rates actively, forward exchange rates are often used for valuing options. From equation (5.9), the forward exchange rate, $F_{0}$ , for a maturity $T$ is given by  

$$
F_{0}=S_{0}e^{(r-r_{f})T}
$$  

This relationship allows equations (17.11) and (17.12) to be simplified to  

where  

$$
\begin{array}{l}{{c=e^{-r T}\left[F_{0}N(d_{1})-K N(d_{2})\right]}}\ {{{\displaystyle p=e^{-r T}\left[K N(-d_{2})-F_{0}N(-d_{1})\right]}}}\ {{{}}}\ {{d_{1}={\displaystyle{{\frac{\ln(F_{0}/K)+\sigma^{2}T/2}{\sigma{\sqrt{T}}}}}}}}\ {{d_{2}={\displaystyle{{\frac{\ln(F_{0}/K)-\sigma^{2}T/2}{\sigma{\sqrt{T}}}}}}=d_{1}-\sigma{\sqrt{T}}}}\end{array}
$$  

Equations (17.13) and (17.14) are the same as equations (17.8) and (17.9). As we shall see in Chapter 18, a European option on the spot price of any asset can be valued in. terms of the price of a forward or futures contract on the asset using equations (17.13). and (17.14). The maturity of the forward or futures contract must be the same as the maturity of the European option..  
