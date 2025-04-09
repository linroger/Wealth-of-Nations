# 18.9 VALUATION OF FUTURES OPTIONS USING BINOMIAL TREES  

This section examines, more formally than in Chapter 13, how binomial trees can be used to price futures options. A key difference between futures options and stock. options is that there are no up-front costs when a futures contract is entered into..  

Suppose that the current futures price is 30 and that it will move either up to 33 or down to 28 over the next month. We consider a one-month call option on the futures with a strike price of 29 and ignore daily settlement. The situation is as indicated in Figure 18.1. If the futures price proves to be 33, the payoff from the option is 4 and the value of the futures contract is 3. If the futures price proves to be 28, the payoff from the option is zero and the value of the futures contract is. $^{-2}$ 6.  

To set up a riskless hedge, we consider a portfolio consisting of a short position in one option contract and a long position in $\Delta$ futures contracts. If the futures price. moves up to 33, the value of the portfolio is. $3\Delta\mathrm{~-~}4$ ; if it moves down to 28, the value. of the portfolio is. $-2\Delta$ . The portfolio is riskless when these are the same, that is,. when  

$$
3\Delta\mathrm{~-~}4=-2\Delta
$$  

or $\Delta=0.8$  

For this value of $\Delta$ , we know the portfolio will be worth $3\times0.8-4=-1.6$ in one month. Assume a risk-free interest rate of $6\%$ . The value of the portfolio today must be  

$$
-1.6e^{-0.06\times1/12}=-1.592
$$  

![](ce09c24b76223628a837f0082ad94fc3b7d5347b7badbe45dc40ccca139c7e07.jpg)  
Figure 18.1 Futures price movements in numerical example.  

The portfolio consists of one short option and. $\Delta$ futures contracts. Because the value of the futures contract today is zero, the value of the option today must be 1.592.  

# A Generalization  

We can generalize this analysis by considering a futures price that starts at $F_{0}$ and is. anticipated to rise to $F_{0}u$ or move down to. $F_{0}d$ over the time period $T.$ We consider an option maturing at time $T$ and suppose that its payoff is $f_{u}$ if the futures price moves up and $f_{d}$ if it moves down. The situation is summarized in Figure 18.2.  

The riskless portfolio in this case consists of a short position in one option combined with a long position in $\Delta$ futures contracts, where  

$$
\Delta=\frac{f_{u}-f_{d}}{F_{0}u-F_{0}d}
$$  

The value of the portfolio at time $T$ is then always  

$$
(F_{0}u\mathrm{~-~}F_{0})\Delta\mathrm{~-~}f_{u}
$$  

Denoting the risk-free interest rate by $r$ , we obtain the value of the portfolio today as  

$$
[(F_{0}u-F_{0})\Delta-f_{u}]e^{-r T}
$$  

Another expression for the present value of the portfolio is $-f$ where $f$ is the value of the option today. It follows that.  

$$
-f=[(F_{0}u-F_{0})\Delta-f_{u}]e^{-r T}
$$  

Substituting for $\Delta$ and simplifying reduces this equation to  

$$
f=e^{-r T}[p f_{u}+(1-p)f_{d}]
$$  

where  

$$
p={\frac{1-d}{u-d}}
$$  

This agrees with the result in Section 13.9. Equation (18.10) gives the risk-neutral probability of an up movement..  

Figure 18.2 Futures price and option price in a general situation.  

![](ec158505fdafb3c4d970ff737a652f05304887b091cc595e30e73d9cbdf7ff23.jpg)  

In the numerical example considered previously (see Figure 18.1), $u=1.1$ $d=0.9333,r=0.06$ $T=1/12$ $f_{u}=4$ , and $f_{d}=0$ From equation (18.10),  

$$
p={\frac{1-0.9333}{1.1-0.9333}}=0.4
$$  

and, from equation (18.9),  

$$
f=e^{-0.06\times1/12}[0.4\times4+0.6\times0]=1.592
$$  

This result agrees with the answer obtained for this example earlier.  

# Multistep Trees  

Multistep binomial trees are used to value American-style futures options in much the same way that they are used to value options on stocks. This is explained in Section 13.9. The parameter $u$ defining up movements in the futures price is $e^{\sigma{\sqrt{\Delta t}}}$ where $\sigma$ is the volatility of the futures price and $\Delta t$ is the length of one time step. The probability of an up movement in the future price is that in equation (18.10):  

$$
p={\frac{1-d}{u-d}}
$$  

Example 13.3 illustrates the use of multistep binomial trees for valuing a futures option.   
Example 21.3 in Chapter 21 provides a further illustration..  
