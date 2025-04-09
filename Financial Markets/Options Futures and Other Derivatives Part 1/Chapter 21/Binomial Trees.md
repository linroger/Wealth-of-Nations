# 21.1 BINOMIAL TREES  

Binomial trees were introduced in Chapter 13. They can be used to value either.   
European or American options. The Black-Scholes-Merton formulas and their exten-.   
sions that were presented in Chapters 15, 17, and 18 provide analytic valuations for European options.' There are no analytic valuations for American options. Binomial.   
trees are therefore most useful for valuing these types of options.?.  

As explained in Chapter 13, the binomial tree valuation approach involves dividing the life of the option into a large number of small time intervals of length. $\Delta t.$ It assumes that in each time interval the price of the underlying asset moves from its initial value of $S$ to one of two new values, $S u$ and $S d$ . The approach is illustrated in Figure 21.1. In.  

![](images/52bda97399bdf86872fe287a665134eec639336fdc1c41cd21448a7fa11bef4f.jpg)  
Figure 21.1 Asset price movements in time $\Delta t$ under the binomial model..  

general, $u>1$ and $d<1$ The movement from $S$ to $S u$ , therefore, is an "up" movement and the movement from $S$ to $S d$ is a "down" movement. The probability of an up movement will be denoted by $p$ . The probability of a down movement is $1-p$  

# Risk-Neutral Valuation  

The risk-neutral valuation principle, explained in Chapters 13 and 15, states that an option (or other derivative) can be valued on the assumption that the world is risk neutral. This means that for valuation purposes we can use the following procedure:.  

1. Assume that the expected return from all traded assets is the risk-free interest rate. 2. Value payoffs from the derivative by calculating their expected values and discounting at the risk-free interest rate.  

This principle underlies the way trees are used.  

# Determination of $p$ , u, and $d$  

The parameters $p,u$ , and $d$ must give correct values for the mean and variance of asset price changes during a time interval of length $\Delta t.$ Because we are working in a riskneutral world, the expected return from the asset is the risk-free interest rate, $r.$ Suppose that the asset provides a yield of $q$ . The expected return in the form of capital gains must. be $r\mathrm{~-~}q$ This means that the expected value of the asset price at the end of a time interval of length $\Delta t$ must be $S e^{(r-q)\Delta t}$ where $S$ is the asset price at the beginning of the time interval. To match the mean return with the tree, we therefore need.  

$$
S e^{(r-q)\Delta t}=p S u+(1-p)S d
$$  

or  

$$
e^{(r-q)\Delta t}=p u+(1-p)d
$$  

The variance of a variable. $Q$ is defined as $E(Q^{2})\:-\:[E(Q)]^{2}$ .Defining $R$ as the percentage change in the asset price in time $\Delta t$ , there is a probability. $p$ that $1+R$ is $u$ and a probability $1-p$ that it is $d$ . Using equation (21.1), it follows that the variance of $1+R$ is  

$$
p u^{2}+(1-p)d^{2}-e^{2(r-q)\Delta t}
$$  

Since adding a constant to a variable makes no difference to its variance, the variance of $1+R$ is the same as the variance of. $R$ . As explained in Section 15.4, this is. $\sigma^{2}\Delta t$  

Hence,  

$$
p u^{2}+(1-p)d^{2}-e^{2(r-q)\Delta t}=\sigma^{2}\Delta t
$$  

From equation (21.1), $e^{(r-q)\Delta t}(u+d)=p u^{2}+(1-p)d^{2}+u d$ so that  

$$
e^{(r-q)\Delta t}(u+d)-u d-e^{2(r-q)\Delta t}=\sigma^{2}\Delta t
$$  

Equations (21.1) and (21.2) impose two conditions on $p,u$ , and $d$ . A third condition used by Cox, Ross, and Rubinstein (1979) is3  

$$
u=1/d
$$  

A solution to equations (21.1) to (21.3), when terms of higher order than $\Delta t$ are ignored, is4  

$$
\begin{array}{l}{{p=\displaystyle\frac{a-d}{u-d}}}\ {{u=e^{\sigma\sqrt{\Delta t}}}}\ {{d=e^{-\sigma\sqrt{\Delta t}}}}\end{array}
$$  

where  

$$
a=e^{(r-q)\Delta t}
$$  

The variable $a$ is sometimes referred to as the growth factor. Equations (21.4) to (21.7) are the same as those in Sections 13.8 and 13.11.  

# Tree of Asset Prices  

Figure 21.2 shows the complete tree of asset prices that is considered when the binomial model is used with four time steps. At time zero, the asset price,. $S_{0}$ , is known. At time $\Delta t$ , there are two possible asset prices, $S_{0}u$ and $S_{0}d$ at time $2\Delta t$ , there are three possible asset prices, $S_{0}u^{2}$ $S_{0}$ , and $S_{0}d^{2}$ ; and so on. In general, at time $i~\Delta t$ we consider $i+1$ asset prices. These are  

$$
S_{0}u^{j}d\mathbf{\omega}^{i-j},\quad j=0,1,\dots,i
$$  

Note that the relationship $u=1/d$ is used in computing the asset price at each node of. the tree in Figure 21.2. For example, the asset price when $j=2$ and $i=3$ is $S_{0}u^{2}d=S_{0}u$ Note also that the tree recombines in the sense that an up movement. followed by a down movement leads to the same asset price as a down movement followed by an up movement..  

# Working Backward through the Tree  

Options are evaluated by starting at the end of the tree (time $T$ ) and working backward. This is known as backward induction. The value of the option is known at time $T$ For example, aput optionis worth max $(K-S_{T},0)$ and a call optionis worth max $(S_{T}-K,0)$  

![](images/7727d870d0315d270f9acfae1458a50fab68d53f19c73408bc85275a2bd04fc6.jpg)  
Figure 21.2 Tree used to value an option.  

where $S_{T}$ is the asset price at time $T$ and $K$ is the strike price. Because a risk-neutral world is being assumed, the value at each node at time $T-\Delta t$ can be calculated as the expected value at time $T$ discounted at rate $r$ for a time period $\Delta t.$ Similarly, the value at each node at time $T-2\Delta t$ can be calculated as the expected value at time $T-\Delta t$ discounted for a time period $\Delta t$ at rate $r$ , and so on. If the option is American, it is necessary to check at each node to see whether early exercise is preferable to holding the option for a further time period $\Delta t.$ Eventually, by working back through all the nodes, we are able to obtain the value of the option at time zero.  

# Example 21.1  

Consider a 5-month American put option on a non-dividend-paying stock when the stock price is $\$50$ , the strike price is $\$50$ , the risk-free interest rate is $10\%$ per annum, and the volatility is $40\%$ per annum. With our usual notation, this means that $S_{0}=50$ $K=50$ $r=0.10$ $\sigma=0.40$ $T=0.4167$ , and $q=0$ . Suppose that we. divide the life of the option into five intervals of length 1 month $\'=0.0833$ year) for the purposes of constructing a binomial tree. Then $\Delta t=0.0833$ and using equations (21.4) to (21.7) gives  

$$
u=e^{\sigma{\sqrt{\Delta t}}}=1.1224,\qquadd=e^{-\sigma{\sqrt{\Delta t}}}=0.8909,\qquada=e^{r\Delta t}=1.0084
$$  

$$
p={\frac{a-d}{u-d}}=0.5073,1-p=0.4927
$$  

Figure 21.3 shows the binomial tree produced by DerivaGem. At each node there. are two numbers. The top one shows the stock price at the node; the lower one shows the value of the option at the node. The probability of an up movement is. always 0.5073; the probability of a down movement is always 0.4927.  

At each node:. Upper value $=$ Underlying Asset Price. Lower value $=$ Option Price Shading indicates where option is exercised  

![](images/3be445d930c4a0221b544e55a56fe950cdcc8c07c404039c7952691c3e3e5856.jpg)  
Figure 21.3 Binomial tree from DerivaGem for Americanput on non-dividendpaying stock (Example 21.1).  

The stock price at the jth node $(j=0,1,\ldots,i)$ at time i $\Delta t(i=0,1,\ldots,5)$ is calculated as $\dot{S}_{0}u^{j}d^{i-j}$ For example, the stock price at node A $(i=4,j=1)$ ) (i.e., the second node up at the end of the fourth time step) is $50\times1.1224\times0.8909^{3}=$ $\$39.69$ The option prices at the final nodes are calculated as $\operatorname*{max}(K-S_{T},0)$ . For example, the option price at node G is $50.00-35.36=14.64.$ The option prices at the penultimate nodes are calculated from the option prices at the final nodes. First, we assume no exercise of the option at the nodes. This means that the option price is calculated as the present value of the expected option price one time step later. For example, at node E, the option price is calculated as  

$$
(0.5073\times0+0.4927\times5.45)e^{-0.10\times0.0833}=2.66
$$  

whereas at node A it is calculated as  

$$
(0.5073\times5.45+0.4927\times14.64)e^{-0.10\times0.0833}=9.90
$$  

We then check to see if early exercise is preferable to waiting. At node E, early exercise would give a value for the option of zero because both the stock price and strike price are. $\$50$ . Clearly it is best to wait. The correct value for the option at node E is therefore $\$2.66$ . At node A, it is a different story. If the option is exercised, it is worth $\$50.00\mathrm{~-~}\$39.69$ , or $\$10.31$ . This is more than $\$9.90$ . If node. A is reached, then the option should be exercised and the correct value for the option at node A is $\$10.31$  

Option prices at earlier nodes are calculated in a similar way. Note that it is not always best to exercise an option early when it is in the money. Consider node B. If the option is exercised, it is worth $\$50.00\mathrm{~-~}\$39.69$ , 0r $\$10.31$ . However, if it is not exercised, it is worth  

$$
(0.5073\times6.38+0.4927\times14.64)e^{-0.10\times0.0833}=10.36
$$  

The option should, therefore, not be exercised at this node, and the correct option value at the node is $\$10.36$  

Working back through the tree, the value of the option at the initial node is. $\$4.49$ . This is our numerical estimate for the option's current value. In practice, a. smaller value of $\Delta t$ , and many more nodes, would be used. DerivaGem shows. that with 30, 50, 100, and 500 time steps we get values for the option of 4.263, 4.272, 4.278, and 4.283.  

# Expressing the Approach Algebraically  

Suppose that the life of an American option is divided into $N$ subintervals of length $\Delta t$ We will refer to the $j$ th node at time $i~\Delta t$ as the $(i,j)$ node, where $0\leq i\leq N$ and $0\leq j\leq i.$ This means that the lowest node at time $i~\Delta t$ is $(i,0)$ , the next lowest is $(i,1)$ and so on. Define $f_{i,j}$ as the value of the option at the $(i,j)$ node. The price of the underlying asset at the $(i,j)$ node is $S_{0}u^{j}d^{i-j}$ . If the option is a call, its value at time $T$ (the expiration date) is $\operatorname*{max}(S_{T}-K,0)$ , so that  

$$
f_{N,j}=\operatorname*{max}(S_{0}u^{j}d^{N-j}-K,0),j=0,1,\dots,N
$$  

If the option is a put, its value at time $T$ is 1 $\mathrm{nax}(K-S_{T},0)$ , so that  

$$
f_{N,j}=\operatorname*{max}(K-S_{0}u^{j}d^{N-j},0),j=0,1,\dots,N
$$  

There is a probability $p$ of moving from the $(i,j)$ node at time i $\Delta t$ to the $(i+1,j+1)$ node at time $(i+1)\Delta t$ , and a probability $1-p$ of moving from the. $(i,j)$ node at time $i~\Delta t$ to the $(i+1,j)$ node at time $(i+1)\Delta t$ . Assuming no early exercise, risk-neutral valuation gives  

$$
f_{i,j}=e^{-r\Delta t}[p f_{i+1,j+1}+(1-p)f_{i+1,j}]
$$  

for $0\leq i\leq N-1$ and $0\le j\le i$ When early exercise is possible, this value for. $f_{i,j}$ must be compared with the option's intrinsic value, so that for a call  

$$
f_{i,j}=\operatorname*{max}\{S_{0}u^{j}d^{i-j}-K,e^{-r\Delta t}[p f_{i+1,j+1}+(1-p)f_{i+1,j}]\}
$$  

and for a put  

$$
f_{i,j}=\operatorname*{max}\{K-S_{0}u^{j}d^{i-j},e^{-r\Delta t}[p f_{i+1,j+1}+(1-p)f_{i+1,j}]\}
$$  

Note that, because the calculations start at time $T$ and work backward, the value at.  

![](images/50b216fe001ccf28b7abd822ca2272f835d1cd68f2883f2056186d5d429f49b1.jpg)  
Figure 21.4 Convergence of the price of the option in Example 21.1 calculated from the DerivaGem Application Builder functions.  

time $i~\Delta t$ captures not only the effect of early exercise possibilities at time i $\Delta t$ , but also the effect of early exercise at subsequent times..  

In the limit as $\Delta t$ tends to zero, an exact value for the American put is obtained. In. practice, $N=30$ usually gives reasonable results. Figure 21.4 shows the convergence of. the option price in Example 21.1. This figure was calculated using the Application Builder functions provided with the DerivaGem software (see Sample Application A)..  

# Estimating Delta and Other Greek Letters  

It will be recalled that the delta. $(\Delta)$ of an option is the rate of change of its price with. respect to the underlying stock price. It can be calculated as  

$$
\frac{\Delta f}{\Delta S}
$$  

where $\Delta S$ is a small change in the asset price and. $\Delta f$ is the corresponding small change in the option price. At time $\Delta t$ we have an estimate $f_{1,1}$ for the option price when the asset price is $S_{0}u$ and an estimate $f_{1,0}$ for the option price when the asset price is $S_{0}d$ This means that, when $\Delta S=S_{0}u-S_{0}d,\Delta f=f_{1,1}-f_{1,0}$ Therefore an estimate of delta at time $\Delta t$ is  

$$
\Delta=\frac{f_{1,1}-f_{1,0}}{S_{0}u-S_{0}d}
$$  

To determine gamma. $(\Gamma)$ , note that we have two estimates of. $\Delta$ at time $2\Delta t$ When $S=(S_{0}u^{2}+S_{0})/2$ (halfway between the second and third node), delta is $(f_{2,2}-f_{2,1})/(S_{0}u^{2}-S_{0})$ ; when ${\cal S}=(S_{0}+S_{0}d^{2})/2$ (halfway between the first and second node), delta is. $(f_{2,1}-f_{2,0})/(S_{0}-S_{0}d^{2})$ . The difference between the two values of $S$ .15 $h$ where  

$$
h=0.5(S_{0}u^{2}-S_{0}d^{2})
$$  

Gamma is the change in delta divided by $h$  

$$
\Gamma=\frac{[(f_{2,2}-f_{2,1})/(S_{0}u^{2}-S_{0})]-[(f_{2,1}-f_{2,0})/(S_{0}-S_{0}d^{2})]}{h}
$$  

These procedures provide estimates of delta at time $\Delta t$ and of gamma at time $2\Delta t.$ In practice, they are usually used as estimates of delta and gamma at time zero as well.5  

A further hedge parameter that can be obtained directly from the tree is theta (O). This is the rate of change of the option price with time when all else is kept constant. The value of the option at time zero is. $f_{0,0}$ and at time $2\Delta t$ it is $f_{2,1}$ . An estimate of theta is therefore  

$$
\Theta=\frac{f_{2,1}-f_{0,0}}{2\Delta t}
$$  

Vega can be calculated by making a small change, $\Delta\sigma$ , in the volatility and constructing a new tree to obtain a new value of the option. (The number of time steps should be kept the same.) The estimate of vega is  

$$
\gamma=\frac{f^{*}-f}{\Delta\sigma}
$$  

where $f$ and $f^{*}$ are the estimates of the option price from the original and the new tree, respectively. Rho can be calculated similarly.  

# Example 21.2  

Consider again Example 21.1. From Figure 21.3, $f_{1,0}=6.96$ and $f_{1,1}=2.16$ Equation (21.8) gives an estimate for delta of  

$$
\frac{2.16-6.96}{56.12-44.55}=-0.41
$$  

From equation (21.9), an estimate of the gamma of the option can be obtained from the values at nodes B, C, and. $\mathrm{F}$ as  

$$
\frac{[(0.64-3.77)/(62.99-50.00)]-[(3.77-10.36)/(50.00-39.69)]}{11.65}=0.03
$$  

From equation (21.10), an estimate of the theta of the option can be obtained from the values at nodes. $\mathrm{\bfD}$ and C as  

$$
\frac{3.77-4.49}{0.1667}=-4.3\mathrm{peryear}
$$  

or $-0.012$ per calendar day. These are only rough estimates. They become pro-. gressively better as the number of time steps on the tree is increased. Using 50 time steps, DerivaGem provides estimates of. $-0.415,0.034$ and $-0.0117$ for delta, gamma, and theta, respectively. By making small changes to parameters and recomputing values, vega and rho are estimated as 0.123 and $-0.072$ , respectively.  
