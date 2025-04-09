# 13.9 INCREASING THE NUMBER OF STEPS  

The binomial model presented above is unrealistically simple. Clearly, an analyst can. expect to obtain only a very rough approximation to an option price by assuming that stock price movements during the life of the option consist of one or two binomial steps.  

![](images/0610470e46a9d59ac8a0a0005a6bfbec7333f552204554c853930e63a2a1823d.jpg)  
Figure 13.10 Two-step tree to value a 2-year American put option when the stock price is 50, strike price is 52, risk-free rate is. $5\%$ , and volatility is $30\%$  

When binomial trees are used in practice, the life of the option is typically divided. into 30 or more time steps. In each time step there is a binomial stock price movement. With 30 time steps there are 31 terminal stock prices and $2^{30}$ , or about 1 billion, possible stock price paths are implicitly considered..  

The equations defining the tree are equations (13.15) to (13.18), regardless of the number of time steps. Suppose, for example, that there are five steps instead of two in the example we considered in Figure 13.10. The parameters would be $\Delta t=2/5=0.4$ $r=0.05$ and $\sigma=0.3$ These values give $u=e^{0.3\times\sqrt[3]{0.4}}=1.2089$ $d=1/1.2089=0.8272$ $a=e^{0.05\times0.4}=1.0202$ and $p=(1.0202-0.8272)/(1.2089-0.8272)=0.5056.$  

As the number of time steps is increased (so that. $\Delta t$ becomes smaller), the binomial tree model makes the same assumptions about stock price behavior as the BlackScholes-Merton model, which will be presented in Chapter 15. When the binomial tree. is used to price a European option, the price converges to the Black-Scholes-Merton. price, as expected, as the number of time steps is increased. This is proved in the appendix to this chapter.  
