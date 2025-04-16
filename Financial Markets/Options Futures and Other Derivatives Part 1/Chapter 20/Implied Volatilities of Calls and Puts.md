---
tags:
  - '#black_scholes_merton_model'
  - '#call_options'
  - '#european_options'
  - '#implied_volatility'
  - '#no_arbitrage'
  - '#put_call_parity'
  - '#put_options'
  - '#volatility_smile'
  - '#volatility_surface'
---
# 20.1 IMPLIED VOLATILITIES OF CALLS AND PUTS  

This section shows that the implied volatility of a European call option is the same as. that of a European put option when they have the same strike price and time to. maturity. This is a particularly convenient result. It shows that when talking about a volatility smile or volatility surface we do not have to worry about whether the options are calls or puts.  

As explained in earlier chapters, put-call parity provides a relationship between the prices of European call and put options when they have the same strike price and time to maturity. With a dividend yield on the underlying asset of. $q$ , the relationship is  

$$
p+S_{0}e^{-q T}=c+K e^{-r T}
$$  

As usual, $c$ and $p$ are the European call and put price. They have the same strike price, $K$ , and time to maturity, $T.$ The variable $S_{0}$ is the price of the underlying asset today, and $r$ is the risk-free interest rate for maturity $T$  

A key feature of the put-call parity relationship is that it is based on a relatively simple no-arbitrage argument. It does not require any assumption about the probability distribution of the asset price in the future. It is true both when the asset price distribution is lognormal and when it is not lognormal.  

Suppose that, for a particular value of the volatility, $p_{\mathrm{BS}}$ and $c_{\mathrm{BS}}$ are the values of European put and call options calculated using the Black-Scholes-Merton model. Suppose further that $p_{\mathrm{mkt}}$ and $c_{\mathrm{mkt}}$ are the market values of these options. Because put-call parity holds for the Black-Scholes-Merton model, we must have.  

$$
p_{\mathrm{BS}}+s_{0}e^{-q T}=c_{\mathrm{BS}}+K e^{-r T}
$$  

In the absence of arbitrage opportunities, put-call parity also holds for the market prices, so that  

$$
p_{\mathrm{mkt}}+S_{0}e^{-q T}=c_{\mathrm{mkt}}+K e^{-r T}
$$  

Subtracting these two equations, we get  

$$
p_{\mathrm{BS}}-p_{\mathrm{mkt}}=c_{\mathrm{BS}}-c_{\mathrm{mkt}}
$$  

This shows that the dollar pricing error when the Black-Scholes-Merton model is used to price a European put option should be exactly the same as the dollar pricing error. when it is used to price a European call option with the same strike price and time to maturity.  

Suppose that the implied volatility of the put option is. $22\%$ . This means that $p_{\mathrm{BS}}=p_{\mathrm{mkt}}$ when a volatility of $22\%$ is used in the Black-Scholes-Merton model. From. equation (20.2), it follows that $c_{\mathrm{BS}}=c_{\mathrm{mkt}}$ when this volatility is used. The implied volatility of the call is, therefore, also $22\%$ . This argument shows that the implied volatility of a European call option is always the same as the implied volatility of a European put option when the two have the same strike price and maturity date. To put this another way, for a given strike price and maturity, the correct volatility to use in conjunction with the Black-Scholes-Merton model to price a European call should always be the same as that used to price a European put. This means that the volatility smile (i.e., the relationship between implied volatility and strike price for a particular. maturity) is the same for European calls and European puts. More generally, it means that the volatility surface (i.e., the implied volatility as a function of strike price and time to maturity) is the same for European calls and European puts. These results are also true to a good approximation for American options..  

# Example 20.1  

The value of a foreign currency is $\$0.60.$ The risk-free interest rate is $5\%$ per annum in the United States and $10\%$ per annum in the foreign country. The market price of a European call option on the foreign currency with a maturity of 1 year and a strike price of $\$0.59$ is 0.0236. DerivaGem shows that the implied volatility of the. call is $14.5\%$ . For there to be no arbitrage, the put-call parity relationship in. equation (20.1) must apply with $q$ equal to the foreign risk-free rate. The price $p$ of a European put option with a strike price of $\$0.59$ and maturity of 1 year therefore satisfies  

$$
p+0.60e^{-0.10\times1}=0.0236+0.59e^{-0.05\times1}
$$  

so that $p=0.0419$ . DerivaGem shows that, when the put has this price, its implied volatility is also $14.5\%$ . This is what we expect from the analysis just given.  
