# 26.14 OPTIONS TO EXCHANGE ONE ASSET FOR ANOTHER  

Options to exchange one asset for another (sometimes referred to as exchange options) arise in various contexts. An option to buy yen with Australian dollars is, from the point of view of a U.S. investor, an option to exchange one foreign currency asset for  

another foreign currency asset. A stock tender offer is an option to exchange shares in one stock for shares in another stock.  

Consider a European option to give up an asset worth $U_{T}$ at time $T$ and receive in return an asset worth. $V_{T}$ . The payoff from the option is.  

$$
\operatorname*{max}(V_{T}-U_{T},0)
$$  

A formula for valuing this option was first produced by Margrabe.12 Suppose that the asset prices, $U$ and $V$ , both follow geometric Brownian motion with volatilities $\sigma_{U}$ and $\sigma_{V}$ . Suppose further that the instantaneous correlation between $U$ and $V$ is $\rho$ , and the yields provided by $U$ and $V$ are $q_{U}$ and $q_{V}$ , respectively. The value of the option at time zero is  

$$
V_{0}e^{-q\nu T}N(d_{1})\:-\:U_{0}e^{-q_{U}T}N(d_{2})
$$  

where  

$$
d_{1}=\frac{\ln(V_{0}/U_{0})+(q_{U}-q_{V}+\hat{\sigma}^{2}/2)T}{\hat{\sigma}\sqrt{T}},d_{2}=d_{1}-\hat{\sigma}\sqrt{T}
$$  

and  

$$
\hat{\sigma}=\sqrt{\pmb{\sigma}_{U}^{2}+\pmb{\sigma}_{V}^{2}-2\rho\sigma_{U}\sigma_{V}}
$$  

and $U_{0}$ and $V_{0}$ are the values of $U$ and $V$ at times zero.  

This result will be proved in Chapter 28. It is interesting to note that equation (26.5). is independent of the risk-free rate. $r.$ . This is because, as $r$ increases, the growth rate of both asset prices in a risk-neutral world increases, but this is exactly offset by an increase in the discount rate. The variable. $\hat{\sigma}$ is the volatility of $V/U$ . Comparisons with equation (17.4) show that the option price is the same as the price of. $U_{0}$ European call options on an asset worth $V/U$ when the strike price is 1.0, the risk-free interest rate is. $q_{U}$ , and the dividend yield on the asset is. $q_{V}$ . Mark Rubinstein shows that the American. version of this option can be characterized similarly for valuation purposes.13 It can be. regarded as $U_{0}$ American options to buy an asset worth. $V/U$ for 1.0 when the risk-free interest rate is. $q_{U}$ and the dividend yield on the asset is $q_{V}$ . The option can therefore be valued as described in Chapter 21 using a binomial tree.  

An option to obtain the better or worse of two assets can be regarded as a position in one of the assets combined with an option to exchange it for the other asset:  

$$
\begin{array}{r}{\operatorname*{min}(U_{T},V_{T})=V_{T}-\operatorname*{max}(V_{T}-U_{T},0)}\ {\operatorname*{max}(U_{T},V_{T})=U_{T}+\operatorname*{max}(V_{T}-U_{T},0)}\end{array}
$$  
