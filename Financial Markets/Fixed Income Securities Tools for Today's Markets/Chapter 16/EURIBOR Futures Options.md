---
tags:
  - daily_settlement
  - euribor_futures
  - futures_style_options
  - option_payoff
  - strike_price
aliases:
  - Euribor Options
  - Futures-style Options
key_concepts:
  - Call option on rate
  - Euribor futures contracts
  - Final settlement price
  - Futures-style call option
  - Trader's daily settlement payments
---

# 16.2 EURIBOR FUTURES OPTIONS  

Euribor futures contracts are discussed in Chapter 12. Options on Euribor futures are futures-style options, because, like futures, all of their profits or losses are in the form of daily settlement payments. To explain the workings of this kind of option, consider a futures-style call option with a strike of 97.0 on some underlying futures contract. If the futures price at the expiration of the option is 99.0, then the final settlement price of the call option is 99.0 minus 97.0, or 2.0. If the futures price at expiration of the option is 95.0, then the final settlement price of the call option is zero. In other words, the final settlement price of the call option is its intrinsic value, that is, the maximum of zero and the difference between the underlying price and the strike.2  

Now say that a trader buys the 97 call sometime before expiration at a price of 0.20. Because this is a future-style option, the trader does not pay that 0.20 as a premium. Instead, the trader enters into the option contract like any other futures contract: the current contract price is 0.20, and all subsequent changes in the option price trigger daily settlement payments. If, at expiration, the underlying futures price is 99, the final settlement of the 97 call is 2.0, and the total of the trader's daily settlement payments will have been 2.0 minus 0.20, or 1.80. Hence, the total profit of the trader is the same 1.80 as that of a traditional call option - the final underlying price of 99, minus the strike of 97, minus the premium of 0.20. But in the case of the futures-style option, that 1.80 is realized as a sequence of daily settlement payments. Similarly, if, at expiration, the underlying futures price is 95.0, the final settlement price of the 97 call is zero, and the total of the trader's daily settlement payments will have been negative 0.20. Again, the total payoff is the same as that of a traditional call option that finishes out-of-the-money, that is, the loss of the premium, but this loss is realized in the form of daily settlement payments.  

As explained in Chapter 12, the price of a Euribor futures contract is set. to 100 minus its percentage rate. In the example of the previous paragraph, the strike price of 97 corresponds to a rate of. $(100-97)/100$ , or $3\%$ , and the final underlying futures settlement price of 99 corresponds to a rate of $1\%$ Furthermore, as also explained in Chapter 12, Euribor futures contracts are scaled so that a decline of one basis point in rate is worth. $\epsilon25$ . Hence, the difference between the strike and final settlement rates, which is. $3\%$ minus $1\%$ or 200 basis points, is worth 200 times $\epsilon25$ , or $\epsilon5{,}000$ . More generally, if the call option strike in terms of rate is. $K$ , and the final settlement rate of. the underlying futures contract is. $R$ , then the final settlement price of the call option is,  

$$
[K-R]^{+}\times10,000\times\in25=\in250,000\times[K-R]^{+}
$$  

where $[K-R]^{+}$ is shorthand for the maximum of. $K-R$ and 0, and the factor. of 10,000 simply converts the rate gain, if any, to basis points, so as to be multiplied by $\epsilon25$ . Analogously, the payoff of a put option on a rates futures contract is,  

$$
[R-K]^{+}\times10,000\times\in25=\in250,000\times[R-K]^{+}
$$  

Equations (16.2) and (16.3) show that a call option on the futures price can be expressed as a put option on its rate, and a put option on the price can. be expressed as a call option on its rate. With this insight and the assumption that futures rates are normally distributed, Appendix A16.3 shows that the.  

TABLE 16.3 A 100.25 Call on September 2022 Three-Month Euribor Futures, as of February 28, 2022. The Futures Price Is 100.235. The Contract and Option Mature on September 19, 2022.   


<html><body><table><tr><td>Quantity Value</td></tr><tr><td>So -0.2350%</td></tr><tr><td>203 T ：0.5562</td></tr><tr><td>365 K -0.25%</td></tr><tr><td>0.6842%</td></tr><tr><td>πN(So, T,K,o) 0.1961%</td></tr><tr><td>Vo= 250,000 ×πN 490.34</td></tr></table></body></html>  

prices of call and put options on Euribor futures are given by the following expressions, respectively,  

$$
\begin{array}{r}{\in250,000\times\pi^{N}(S_{0},T,K,\sigma)}\ {\in250,000\times\xi^{N}(S_{0},T,K,\sigma)}\end{array}
$$  

where $S_{0}$ is the current futures rate; $T$ is the time to option expiration in. years; $K$ is the strike, in terms of rate; and. $\sigma$ is the basis-point volatility of. the futures rates. The functions $\pi^{N}$ and $\xi^{N}$ are as given in Appendix A16.4. Note that these formulae are not preceded by a discount factor, because these options are themselves futures: their prices equal their expected value under the risk-neutral measure, or equivalently, there is no initial premium on which a return need be earned. Also, the BSM model is readily applied here, because American futures-style options are not optimally exercised early: with daily settlement of the option value, there is no intrinsic value to be realized by exercise and, therefore, no reason to sacrifice the remaining time value of the option.  

Table 16.3 applies Equation (16.4) to a call on the September 2022 Euribor futures contract with a strike of 100.125. As of the pricing date,. the futures price is 100.235, which corresponds to a rate of. $-0.2350\%$ . The futures contract and the option both mature on September 19, 2022, which is 203 days from the pricing date..  
