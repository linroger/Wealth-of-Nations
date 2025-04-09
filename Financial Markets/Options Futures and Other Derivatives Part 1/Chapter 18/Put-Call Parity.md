# 18.4 PUT-CALL PARITY  

In Chapter 11, we derived a put-call parity relationship for European stock options. We now consider a similar argument to derive a put-call parity relationship for European futures options. Consider European futures call and put options, both with strike price $K$ and time to expiration $T.$ We can form two portfolios:  

Portfolio $A$ : a European futures call option plus an amount of cash equal to. $K e^{-r T}$ Portfolio $B$ : a European futures put option plus a long futures contract plus an amount of cash equal to $F_{0}e^{-r T}$ where $F_{0}$ is the futures price  

In portfolio A, the cash can be invested at the risk-free rate, $r$ , and grows to $K$ at time $T$ Let $F_{T}$ be the futures price at maturity of the option. If $F_{T}>K$ , the call option in portfolio A is exercised and portfolio A is worth $F_{T}$ If $F_{T}\leq K$ , the call is not exercised and portfolio A is worth $K$ The value of portfolio A at time $T$ is therefore  

$$
\operatorname*{max}(F_{T},K)
$$  

In portfolio B, the cash can be invested at the risk-free rate to grow to $F_{0}$ at time $T.$ The put option provides a payoff of. $\operatorname*{max}(K-F_{T},0)$ . The futures contract provides a payoff of $F_{T}-F_{0}$ 2 The value of portfolio $\mathrm{B}$ at time $T$ is therefore  

$$
F_{0}+(F_{T}-F_{0})+\operatorname*{max}(K-F_{T},0)=\operatorname*{max}(F_{T},K)
$$  

Because the two portfolios have the same value at time $T$ and European options cannot be exercised early, it follows that they are worth the same today. The value of portfolio A today is  

$$
c\:+\:K e^{-r T}
$$  

where $c$ is the price of the futures call option. The daily settlement process ensures that the futures contract in portfolio $\mathrm{B}$ is worth zero today. Portfolio. $\mathrm{B}$ is therefore worth  

$$
p+F_{0}e^{-r T}
$$  

where $p$ is the price of the futures put option. Hence  

$$
c+K e^{-r T}=p+F_{0}e^{-r T}
$$  

The difference between this put-call parity relationship and the one for a nondividend-paying stock in equation (11.6) is that the stock price,. $S_{0}$ , is replaced by the discounted futures price, $F_{0}e^{-r T}$  

As shown in Section 18.3, when the underlying futures contract matures at the same time as the option, European futures and spot options are the same. Equation (18.1) therefore gives a relationship between the price of a call option on the spot price, the price of a put option on the spot price, and the futures price when both options mature at the same time as the futures contract.  

# Example 18.5  

Suppose that the price of a European call option on a commodity for delivery in six months is $\$0.56$ per ounce when the strike price is. $\$8.50$ . Assume that the.   
futures price for delivery in six months is currently $\$8.00$ , and the risk-free interest.   
rate for an investment that matures in six months is. $10\%$ per annum. From a.   
rearrangement of equation (18.1), the price of a European put option on the spot.   
price with the same maturity and exercise date as the call option is.  

$$
0.56+8.50e^{-0.1\times6/12}-8.00e^{-0.1\times6/12}=1.04
$$  

For American futures options, the put-call relationship is (see Problem 18.21)  

$$
F_{0}e^{-r T}-K<C-{\cal P}<F_{0}-K e^{-r T}
$$  
