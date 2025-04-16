---
tags:
  - '#binomial_tree'
  - '#no_arbitrage_argument'
  - '#one_step_binomial_model'
  - '#option_delta'
  - '#option_pricing_formula'
  - '#riskless_portfolio'
  - '#stock_option_pricing'
  - '#stock_price_movements'
---
# 13.1 A ONE-STEP BINOMIAL MODEL AND A NO-ARBITRAGEARGUMENT  

We start by considering a very simple situation. A stock price is currently $\$20$ , and it is. known that at the end of 3 months it will be either $\$22$ or $\$18$ We are interested in. valuing a European call option to buy the stock for $\$21$ in 3 months. This option will have one of two values at the end of the 3 months. If the stock price turns out to be $\$22$ the value of the option will be $\$1$ ; if the stock price turns out to be $\$18$ , the value of the. option will be zero. The situation is illustrated in Figure 13.1.  

It turns out that a relatively simple argument can be used to price the option in this. example. The only assumption needed is that arbitrage opportunities do not exist. We. set up a portfolio of the stock and the option in such a way that there is no uncertainty about the value of the portfolio at the end of the 3 months. We then argue that, because the portfolio has no risk, the return it earns must equal the risk-free interest rate. This enables us to work out the cost of setting up the portfolio and therefore the option's price. Because there are two securities (the stock and the stock option) and only two possible outcomes, it is always possible to set up the riskless portfolio.  

![](38bb7f8e8dc74666700d85811ed7ef4684d103bf4e73b02816f74942031f1670.jpg)  
Figure 13.1 Stock price movements for numerical example in Section 13.1.  

Consider a portfolio consisting of a long position in $\Delta$ shares of the stock and a short. position in one call option (. $\Delta$ is the Greek capital letter "delta"). We calculate the value of $\Delta$ that makes the portfolio riskless. If the stock price moves up from $\$20$ to $\$22$ , the value of the shares is. $22\Delta$ and the value of the option is 1, so that the total value of the portfolio is $22\Delta\:-\:1$ . If the stock price moves down from $\$20$ to $\$18$ , the value of the. shares is $18\Delta$ and the value of the option is zero, so that the total value of the portfolio is $18\Delta$ . The portfolio is riskless if the value of $\Delta$ is chosen so that the final value of the portfolio is the same for both alternatives. This means that  

$$
22\Delta\textrm{--}1=18\Delta
$$  

or  

$$
\Delta=0.25
$$  

A riskless portfolio is therefore  

Long: 0.25 shares  

Short: 1 option.  

If the stock price moves up to $\$22$ , the value of the portfolio is  

$$
22\times0.25-1=4.5
$$  

If the stock price moves down to $\$18$ , the value of the portfolio is  

$$
18\times0.25=4.5
$$  

Regardless of whether the stock price moves up or down, the value of the portfolio is always 4.5 at the end of the life of the option..  

Riskless portfolios must, in the absence of arbitrage opportunities, earn the risk-free. rate of interest. Suppose that, in this case, the risk-free rate is. $4\%$ per annum (continuously compounded). It follows that the value of the portfolio today must be the present value of 4.5, or  

$$
4.5e^{-0.04\times3/12}=4.455
$$  

The value of the stock price today is known to be $\$20$ . Suppose the option price is.   
denoted by $f.$ The value of the portfolio today is.  

$$
20\times0.25-f=5-f
$$  

It follows that  

$$
5-f=4.455
$$  

or  

$$
f=0.545
$$  

This shows that, in the absence of arbitrage opportunities, the current value of the. option must be 0.545. If the value of the option were more than 0.545, the portfolio. would cost less than 4.455 to set up and would earn more than the risk-free rate. If the value of the option were less than 0.545, shorting the portfolio would provide a way of borrowing money at less than the risk-free rate..  

Trading 0.25 shares is, of course, not possible. However, the argument is the same if we imagine selling 400 options and buying 100 shares. In general, it is necessary to buy $\Delta$ shares for each option sold to form a riskless portfolio. The parameter. $\Delta$ (delta) is important in the hedging of options. It is discussed further later in this chapter and in Chapter 19.  

# A Generalization  

We can generalize the no-arbitrage argument just presented by considering a stock whose price is. $S_{0}$ and an option on the stock (or any derivative dependent on the stock). whose current price is $f.$ We suppose that the option lasts for time. $T$ and that during. the life of the option the stock price can either move up from. $S_{0}$ to a new level, $S_{0}u$ where $u>1$ , or down from $S_{0}$ to a new level, $S_{0}d$ where $d<1$ The percentage increase in the stock price when there is an up movement is. $u-1$ ; the percentage decrease when. there is a down movement is. $1-d$ If the stock price moves up to. $S_{0}u$ , we suppose that. the payoff from the option iss. $f_{u}$ ; if the stock price moves down to $S_{0}d$ we suppose the. payoff from the option is. $f_{d}$ The situation is illustrated in Figure 13.2..  

As before, we imagine a portfolio consisting of a long position in $\Delta$ shares and a short position in one option. We calculate the value of $\Delta$ that makes the portfolio riskless. If there is an up movement in the stock price, the value of the portfolio at the end of the life of the option is  

$$
S_{0}u\Delta\mathrm{~-~}f_{u}
$$  

Figure 13.2 Stock and option prices in a general one-step tree.  

![](30b26acc1895528c931671080278dcdc5c6a1fba6c100201700a000efbe0699a.jpg)  

If there is a down movement in the stock price, the value becomes  

$$
S_{0}d\Delta\:-\:f_{d}
$$  

The two are equal when  

$$
S_{0}u\Delta\mathrm{~-~}f_{u}=S_{0}d\Delta\mathrm{~-~}f_{d}
$$  

or  

$$
\Delta=\frac{f_{u}-f_{d}}{S_{0}u-S_{0}d}
$$  

In this case, the portfolio is riskless and, for there to be no arbitrage opportunities, it must earn the risk-free interest rate. Equation (13.1) shows that. $\Delta$ is the ratio of the change in the option price to the change in the stock price as we move between the nodes at time $T$  

If we denote the risk-free interest rate by $r$ , the present value of the portfolio is.  

$$
(S_{0}u\Delta-f_{u})e^{-r T}
$$  

The cost of setting up the portfolio is  

$$
S_{0}\Delta\mathrm{~-~}f
$$  

It follows that  

$$
S_{0}\Delta-f=(S_{0}u\Delta-f_{u})e^{-r T}
$$  

or  

$$
f=S_{0}\Delta(1-u e^{-r T})+f_{u}e^{-r T}
$$  

Substituting from equation (13.1) for $\Delta$ , we obtain  

or  

$$
f=S_{0}\bigg({\frac{f_{u}-f_{d}}{S_{0}u-S_{0}d}}\bigg)(1-u e^{-r T})+f_{u}e^{-r T} 
$$  

$$
f=\frac{f_{u}(1-d e^{-r T})+f_{d}(u e^{-r T}-1)}{u-d}
$$  

or  

$$
f=e^{-r T}[p f_{u}+(1-p)f_{d}]
$$  

where  

$$
p={\frac{e^{r T}-d}{u-d}}
$$  

Equations (13.2) and (13.3) enable an option to be priced when stock price movements are given by a one-step binomial tree. The only assumption needed for the equation is that there are no arbitrage opportunities in the market.  

In the numerical example considered previously (see Figure 13.1), $u=1.1$ $d=0.9$ $r=0.04$ $T=0.25,f_{u}=1$ , and $f_{d}=0.$ From equation (13.3), we have  

$$
p={\frac{e^{0.04\times3/12}-0.9}{1.1-0.9}}=0.5503
$$  

and, from equation (13.2), we have  

$$
f=e^{-0.04\times0.25}(0.5503\times1+0.4497\times0)=0.545
$$  

The result agrees with the answer obtained earlier in this section.  

# Irrelevance of the Stock's Expected Return  

The option pricing formula in equation (13.2) does not involve the probabilities of the stock price moving up or down. For example, we get the same option price when the probability of an upward movement is 0.5 as we do when it is 0.9. This is surprising and seems counterintuitive. It is natural to assume that, as the probability of an upward movement in the stock price increases, the value of a call option on the stock increases and the value of a put option on the stock decreases. This is not the case.  

The key reason is that we are not valuing the option in absolute terms. We are. calculating its value in terms of the price of the underlying stock. The probabilities of future up or down movements are already incorporated into the stock price: we do not need to take them into account again when valuing the option in terms of the stock price.  
