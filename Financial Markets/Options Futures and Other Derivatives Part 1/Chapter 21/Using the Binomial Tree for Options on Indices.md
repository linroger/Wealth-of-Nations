# 21.2 USING THE BINOMIAL TREE FOR OPTIONS ON INDICES, CURRENCIES, AND FUTURES CONTRACTS  

As explained in Chapters 13, 17 and 18, stock indices, currencies, and futures contracts can, for the purposes of option valuation, be considered as assets providing known yields. For a stock index, the relevant yield is the dividend yield on the stock portfolio underlying the index; in the case of a currency, it is the foreign risk-free interest rate; in the case of a futures contract, it is the domestic risk-free interest rate. The binomial tree approach can therefore be used to value options on stock indices, currencies, and futures contracts provided that $q$ in equation (21.7) is interpreted appropriately.  

# Example 21.3  

Consider a 4-month American call option on index futures where the current futures price is 300, the exercise price is 300, the risk-free interest rate is $8\%$ per  

At each node: Upper value $=$ Underlying Asset Price Lower value $=$ Option Price Shading indicates where option is exercised annum, and the volatility of the index is. $30\%$ per annum. The life of the option is. divided into four 1-month periods for the purposes of constructing the tree. In this case, $F_{0}=300$ $K=300$ $r=0.08$ $\sigma=0.3$ $T=0.3333$ , and $\Delta t=0.0833$ Because a futures contract is analogous to a stock paying dividends at a rate. $r,q$ should be. set equal to $r$ in equation (21.7). This gives $a=1$ . The other parameters necessary to construct the tree are  

![](62ad6682765304a79b1751774762966efab46a4778f53caaf1284a46dd1d38de.jpg)  
Figure 21.5  Binomial tree produced by DerivaGem for American call option on an index futures contract (Example 21.3).  

$$
\begin{array}{c}{{u=e^{\sigma\sqrt{\Delta t}}=1.0905,\qquadd=1/u=0.9170}}\ {{p=\displaystyle\frac{a-d}{u-d}=0.4784,\qquad1-p=0.5216}}\end{array}
$$  

The tree, as produced by DerivaGem, is shown in Figure 21.5. (The upper number is the futures price; the lower number is the option price.) The estimated value of the option is 19.16. More accuracy is obtained using more steps. With 50 time steps, DerivaGem gives a value of 20.18; with 100 time steps it gives 20.22.  

At each node: Upper value $=$ Underlying Asset Price Lower value $=$ Option Price Shading indicates where option is exercised  

![](34f1472853f5971e40a8453dac1e2fc0c5eb41b089e217bdf552d365a8f80a51.jpg)  
Figure 21.6 Binomial tree produced by DerivaGem for American put option on a currency (Example 21.4).  

# Example 21.4  

Consider a 1-year American put option on a foreign currency. The cur-. rent exchange rate is 1.6100, the strike price is 1.6000, the domestic risk-free interest rate is $8\%$ per annum, the foreign risk-free interest rate is. $9\%$ per annum, and the volatility of the foreign exchange rate is $12\%$ per annum. In this case,. $S_{0}=1.61,K=1.60,r=0.08$ $r_{f}=0.09$ $\sigma=0.12$ , and $T=1.0$ .The life of the. option is divided into four 3-month periods for the purposes of constructing the. tree, so that $\Delta t=0.25$ . In this case, $q=r_{f}$ and equation (21.7) gives  

$$
a=e^{(0.08-0.09)\times0.25}=0.9975
$$  

The other parameters necessary to construct the tree are  

$$
u=e^{\sigma{\sqrt{\Delta t}}}=1.0618,d=1/u=0.9418,p={\frac{a-d}{u-d}}=0.4642,1-p=0.5358
$$  

The tree, as produced by DerivaGem, is shown in Figure 21.6. (The upper number. is the exchange rate; the lower number is the option price.) The estimated value of the option is $\$0.0710$ . (Using 50 time steps, DerivaGem gives the value of the. option as 0.0738; with 100 time steps it also gives 0.0738.)  
