# 32.4  INTEREST RATE TREES  

An interest rate tree is a discrete-time representation of the stochastic process for the short rate in much the same way as a stock price tree is a discrete-time representation of the process followed by a stock price. If the time step on the tree is. $\Delta t$ , the rates on the. tree are the continuously compounded $\Delta t$ -period rates. The usual assumption when a. tree is constructed is that the. $\Delta t$ -period rate, $R$ , follows the same stochastic process as the instantaneous rate,. $r$ in the corresponding continuous-time model. The main. difference between interest rate trees and stock price trees is in the way that discounting. is done. In a stock price tree, the discount rate is usually assumed to be the same at each node or a function of time. In an interest rate tree, the discount rate depends on $r$ and varies from node to node..  

It often proves to be convenient to use a trinomial rather than a binomial tree for interest rates. The main advantage of a trinomial tree is that it provides an extra degree of freedom, making it easier for the tree to represent features of the interest rate process such as mean reversion. As mentioned in Section 21.8, using a trinomial tree is equivalent to using the explicit finite difference method.  

# Illustration of Use of Trinomial Trees  

To illustrate how trinomial interest rate trees are used to value derivatives, consider the simple example shown in Figure 32.4. This is a two-step tree with each time step equal to 1 year in length so that $\Delta t=1$ year. Assume that the up, middle, and down probabilities are 0.25, 0.50, and 0.25, respectively, at each node. The assumed $\Delta t$ period rate is shown as the upper number at each node.6  

![](75f14a748ce7f5a2311820dd615d99fa2a90b4a7ae9adf7845849e9162c36137.jpg)  
Figure 32.4 Example of the use of trinomial interest rate trees. Upper number at each node is rate; lower number is value of instrument..  

The tree is used to value a derivative that provides a payoff at the end of the second time step of  

$$
\operatorname*{max}[100(R-0.11),0]
$$  

where $R$ is the $\Delta t$ -period rate. The calculated value of this derivative is the lower number at each node. At the final nodes, the value of the derivative equals the payoff. For example, at node E, the value is $100\times(0.14-0.11)=3.$ At earlier nodes, the value of the derivative is calculated using the rollback procedure explained in Chapters 13 and 21. At node B, the 1-year interest rate is $12\%$ . This is used for discounting to obtain the value of the derivative at node B from its values at nodes E, F, and $\mathrm{G}$ as  

$$
[0.25\times3+0.5\times1+0.25\times0]e^{-0.12\times1}=1.11
$$  

At node C, the 1-year interest rate is. $10\%$ . This is used for discounting to obtain the value of the derivative at node $\mathrm{C}$ as  

$$
(0.25\times1+0.5\times0+0.25\times0)e^{-0.1\times1}=0.23
$$  

At the initial node, A, the interest rate is also $10\%$ and the value of the derivative is  

$$
(0.25\times1.11+0.5\times0.23+0.25\times0)e^{-0.1\times1}=0.35
$$  

# Nonstandard Branching  

It sometimes proves convenient to modify the standard trinomial branching pattern that. is used at all nodes in Figure 32.4. Three alternative branching possibilities are shown in Figure 32.5. The usual branching is shown in Figure 32.5a. It is "up one/straight along/ down one". One alternative to this is "up two/up one/straight along", as shown in.  

![](aa492c0e4ef45464fcde97316d4c68206f5047c80c3da9ea7e95f3c5b79d77f3.jpg)  
Figure 32.5 Alternative branching methods in a trinomial tree.   
Figure 32.5b. This proves useful for incorporating mean reversion when interest rates are very low. A third branching pattern shown in Figure. $32.5\mathrm{c}$ is "straight along/down one/. down two". This is useful for incorporating mean reversion when interest rates are very. high. The use of different branching patterns is illustrated in the following section..  
