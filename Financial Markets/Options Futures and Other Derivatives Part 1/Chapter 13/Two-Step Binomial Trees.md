# 13.3 TWO-STEP BINOMIAL TREES  

We can extend the analysis to a two-step binomial tree such as that shown in Figure 13.3. Here the stock price starts at $\$20$ and in each of two time steps may go up by $10\%$ or down by $10\%$ . Each time step is 3 months long and the risk-free interest rate is. $4\%$ per annum. We consider a 6-month option with a strike price of. $\$21$  

The objective of the analysis is to calculate the option price at the initial node of the tree. This can be done by repeatedly applying the principles established earlier in the chapter. Figure 13.4 shows the same tree as Figure 13.3, but with both the stock price and the option price at each node. (The stock price is the upper number and the option price is the lower number.) The option prices at the final nodes of the tree are easily calculated. They are the payoffs from the option. At node D the stock price is 24.2 and the option price is $24.2\textrm{-}21=3.2$ ; at nodes E and F the option is out of the money and its value is zero.  

At node $\mathrm{C}$ the option price is zero, because node C leads to either node E or node F. and at both of those nodes the option price is zero. We calculate the option price at node B by focusing our attention on the part of the tree shown in Figure 13.5. Using the.  

![](bc6527e81d880375ad97653d23ab91a898bd3ceeda0d4a8e3c952d531396cfa5.jpg)  
Figure 13.3 Stock prices in a two-step tree.  

notation introduced earlier in the chapter, $u=1.1,d=0.9,r=0.04$ , and $T=0.25$ , SO that $p=0.5503$ , and equation (13.2) gives the value of the option at node B as  

$$
e^{-0.04\times3/12}(0.5503\times3.2+0.4497\times0)=1.7433
$$  

It remains for us to calculate the option price at the initial node A. We do so by focusing. on the first step of the tree. We know that the value of the option at node B is 1.7433 and  

![](e6d04e0d084823804a1433a74d2071f539811f2a5786023ad8d26661c6fd637f.jpg)  
Figure 13.4  Stock and option prices in a two-step tree. The upper number at each node is the stock price and the lower number is the option price..  

![](4417750c79066b074683ff665c4fcfdf05b46154812f7892b91025abb95fc2dd.jpg)  
Figure 13.5 Evaluation of option price at node B of Figure 13.4.  

that at node $\mathrm{C}$ it is zero. Equation (13.2) therefore gives the value at node A as  

$$
e^{-0.04\times3/12}(0.5503\times1.7433+0.4497\times0)=0.9497
$$  

The value of the option is $\$0.9497$  

Note that this example was constructed so that. $u$ and $d$ (the proportional up and down movements) were the same at each node of the tree and so that the time steps were of the same length. As a result, the risk-neutral probability, $p$ , as calculated by equation (13.3) is the same at each node..  

# A Generalization  

We can generalize the case of two time steps by considering the situation in Figure 13.6. The stock price is initially. $S_{0}$ . During each time step, it either moves up to $u$ times its value at the beginning of the time step or moves down to $d$ times this value. The. notation for the value of the option is shown on the tree. (For example, after two up movements the value of the option is $f_{u u}$ .) We suppose that the risk-free interest rate is $r$ and the length of the time step is $\Delta t$ years.  

Because the length of a time step is now $\Delta t$ rather than $T$ equations (13.2) and (1) become  

$$
\begin{array}{c}{{f=e^{-r\Delta t}[p f_{u}+(1-p)f_{d}]}}\ {{{}}}\ {{p=\frac{e^{r\Delta t}-d}{u-d}}}\end{array}
$$  

Repeated application of equation (13.5) gives  

$$
\begin{array}{l}{{f_{u}=e^{-r\Delta t}[p f_{u u}+(1-p)f_{u d}]}}\ {{f_{d}=e^{-r\Delta t}[p f_{u d}+(1-p)f_{d d}]}}\ {{f=e^{-r\Delta t}[p f_{u}+(1-p)f_{d}]}}\end{array}
$$  

Substituting from equations (13.7) and (13.8) into (13.9), we get  

$$
f=e^{-2r\Delta t}[p^{2}f_{u u}+2p(1-p)f_{u d}+(1-p)^{2}f_{d d}]
$$  

This is consistent with the principle of risk-neutral valuation mentioned earlier. The  

![](45daf1a60ec3fcac469294a72e70e50cec267a26a39b21bce88db6ac59535226.jpg)  
Figure 13.6 Stock and option prices in general two-step tree.  

variables $p^{2},2p(1-p)$ , and $(1-p)^{2}$ are the probabilities that the upper, middle, and. lower final nodes will be reached. The option price is equal to its expected payoff in a risk-neutral world discounted at the risk-free interest rate..  

As we add more steps to the binomial tree, the risk-neutral valuation principle. continues to hold. The option price is always equal to its expected payoff in a riskneutral world discounted at the risk-free interest rate..  
