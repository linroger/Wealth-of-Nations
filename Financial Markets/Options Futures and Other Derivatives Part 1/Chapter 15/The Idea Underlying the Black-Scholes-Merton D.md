# 15.5 THE IDEA UNDERLYING THE BLACK-SCHOLES-MERTON DIFFERENTIAL EQUATION  

The Black-Scholes-Merton differential equation is an equation that must be satisfied.   
by the price of any derivative dependent on a non-dividend-paying stock. The equation.   
is derived in the next section. Here we consider the nature of the arguments we will use.  

![](images/0276c5487a98bec521c3da68a6041843f9b3d6db416eb51ec7f9953fb93aa80b.jpg)  
Figure 15.2 Relationship between call price and stock price. Current stock price is $S_{0}$ -  

These are similar to the no-arbitrage arguments we used to value stock options in. Chapter 13 for the situation where stock price movements were assumed to be binomial. They involve setting up a riskless portfolio consisting of a position in the derivative and a position in the stock. In the absence of arbitrage opportunities, the return from the portfolio must be the risk-free interest rate,. $r.$ This leads to the Black-Scholes-Merton. differential equation.  

The reason a riskless portfolio can be set up is that the stock price and the derivative price are both affected by the same underlying source of uncertainty: stock price movements. In any short period of time, the price of the derivative is perfectly correlated with the price of the underlying stock. When an appropriate portfolio of the stock and the derivative is established, the gain or loss from the stock position always offsets the gain or loss from the derivative position so that the overall value of the portfolio at the end of the short period of time is known with certainty.  

Suppose, for example, that at a particular point in time the relationship between a small change $\Delta S$ in the stock price and the resultant small change. $\Delta c$ in the price of a European call option is given by.  

$$
\Delta c=0.4\Delta S
$$  

This means that the slope of the line representing the relationship between $c$ and $S$ is 0.4, as indicated in Figure 15.2. A riskless portfolio would consist of:.  

1. A long position in 40 shares   
2. A short position in 100 call options.  

Suppose, for example, that the stock price increases by 10 cents. The option price will increase by 4 cents and the $40\times0.1=\$4$ gain on the shares is equal to the $100\times0.04=$ $\$4$ loss on the short option position.  

There is one important difference between the Black-Scholes-Merton analysis and. our analysis using a binomial model in Chapter 13. In Black-Scholes-Merton, the position in the stock and the derivative is riskless for only a very short period of time. (Theoretically, it remains riskless only for an instantaneously short period of time.) To remain riskless, it must be adjusted, or rebalanced, frequently.6 For example, the.  

relationship between $\Delta c$ and $\Delta S$ in our example might change from $\Delta c=0.4\Delta S$ today to $\Delta c=0.5\Delta S$ tomorrow. This would mean that, in order to maintain the riskless. position, an extra 10 shares would have to be purchased for each 100 call options sold. It is nevertheless true that the return from the riskless portfolio in any very short period. of time must be the risk-free interest rate. This is the key element in the Black-Scholes-- Merton analysis and leads to their pricing formulas.  

# Assumptions  

The assumptions we use to derive the Black-Scholes-Merton differential equation are as follows:  

1. The stock price follows the process developed in Chapter 14 with $\mu$ and $\sigma$ constan   
2. The short selling of securities with full use of proceeds is permitted.   
3. There are no transaction costs or taxes. All securities are perfectly divisible.   
4. There are no dividends during the life of the derivative.   
5. There are no riskless arbitrage opportunities.   
6. Security trading is continuous.   
7. The risk-free rate of interest, $r$ , is constant and the same for all maturities.  

As we discuss in later chapters, some of these assumptions can be relaxed. For example,.   
$\sigma$ and $r$ can be known functions of. $t$ We can even allow interest rates to be stochastic.   
provided that the stock price distribution at maturity of the option is still lognormal.  
