# 13.4  A PUT EXAMPLE  

The procedures described in this chapter can be used to price puts as well as calls. Consider a 2-year European put with a strike price of. $\$52$ on a stock whose current price is $\$50$ . We suppose that there are two time steps of 1 year, and in each time step. the stock price either moves up by. $20\%$ or moves down by $20\%$ . We also suppose that the risk-free interest rate is $5\%$  

The tree is shown in Figure 13.7. In this case $u=1.2$ $d=0.8$ $\Delta t=1$ , and $r=0.05$ From equation (13.6) the value of the risk-neutral probability, $p$ , is given by.  

$$
p={\frac{e^{0.05\times1}-0.8}{1.2-0.8}}=0.6282
$$  

The possible final stock prices are: $\$72,48$ and $\$32$ . In this case, $f_{u u}=0,f_{u d}=4$ and $f_{d d}=20$ . From equation (13.10),  

$$
f=e^{-2\times0.05\times1}(0.6282^{2}\times0+2\times0.6282\times0.3718\times4+0.3718^{2}\times20)=4.1923
$$  

The value of the put is $\$4.1923$ . This result can also be obtained using equation (13.5)  

![](eb898378e338b287929079d4aeb12d0e6deeb10a788112230ee53f612b97064a.jpg)  
Figure 13.7 Using a two-step tree to value a European put option. At each node, the upper number is the stock price and the lower number is the option price..  

and working back through the tree one step at a time. Figure 13.7 shows the intermediate option prices that are calculated.  
