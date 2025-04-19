---
tags:
  - dividend_yield
  - drift
  - futures_options
  - futures_price
  - risk_neutral
aliases:
  - Futures Price Behavior
  - Risk-Neutral Futures
key_concepts:
  - Differential equation futures
  - Dividend yield analogy
  - Futures options valuation
  - Futures price drift
  - Risk-neutral world futures
---

# 18.6 DRIFT OF A FUTURES PRICE IN A RISK-NEUTRAL WORLD  

There is a general result that allows us to use the analysis in Section 17.3 for futures options. This result is that in a risk-neutral world a futures price behaves in the same way as a stock paying a dividend yield at the domestic risk-free interest rate $r$  

One clue that this might be so is given by noting that the put-call parity relationship for futures options prices is the same as that for options on a stock paying a dividend yield at rate $q$ when the stock price is replaced by the futures price and. $q=r$ (compare equations (18.1) and (17.3)).  

To prove the result formally, we calculate the drift of a futures price in a risk-neutral world. We define $F_{t}$ as the futures price at time $t$ and suppose the settlement dates are at times $0,\Delta t,2\Delta t,\dots$ If we enter into a long futures contract at time 0, its value is zero. At time $\Delta t$ , it provides a payoff of $F_{\Delta t}-F_{0}$ . If $r$ is the very-short-term ( $\Delta t$ -period) interest rate at time 0, risk-neutral valuation gives the value of the contract at time O as  

$$
e^{-r\Delta t}\hat{E}[F_{\Delta t}-F_{0}]
$$  

where $\hat{E}$ denotes expectations in a risk-neutral world. We must therefore have  

$$
e^{-r\Delta t}\hat{E}(F_{\Delta t}-F_{0})=0
$$  

showing that  

$$
\hat{E}(F_{\Delta t})=F_{0}
$$  

Similarly, $\hat{E}(F_{2\Delta t})=F_{\Delta t},\hat{E}(F_{3\Delta t})=F_{2\Delta t},$ and so on. Putting many results like this together, we see that  

$$
\hat{E}(F_{T})=F_{0}
$$  

for any time $T$  

The drift of the futures price in a risk-neutral world is therefore zero. From equation (17.7), the futures price behaves like a stock providing a dividend yield $q$ equal to $r$ This result is a very general one. It is true for all futures prices and does not depend on any assumptions about interest rates, volatilities, etc.3  

The usual assumption made for the process followed by a futures price $F$ in the riskneutral world is  

$$
d F=\sigma F d z
$$  

where $\sigma$ is a constant.  

# Differential Equation  

For another way of seeing that a futures price behaves like a stock paying a dividend yield at rate $q$ , we can derive the differential equation satisfied by a derivative dependent  

on a futures price in the same way as we derived the differential equation for a derivative dependent on a non-dividend-paying stock in Section 15.6. This is4  

$$
{\frac{\partial f}{\partial t}}+{\frac{1}{2}}{\frac{\partial^{2}f}{\partial F^{2}}}\sigma^{2}F^{2}=r f
$$  

It has the same form as equation (17.6) with $q$ set equal to $r$ This confirms that, for the purpose of valuing derivatives, a futures price can be treated in the same way as a stock providing a dividend yield at rate. $r$  
