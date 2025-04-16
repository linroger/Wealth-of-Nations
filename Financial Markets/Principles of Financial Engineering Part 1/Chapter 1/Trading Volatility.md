---
tags:
  - '#convexity_gains'
  - '#dynamic_strategy'
  - '#forward_contract'
  - '#nonlinear_instrument'
  - '#options_trading'
  - '#payoff_function'
  - '#rebalancing_hedge'
  - '#risk_management'
  - '#volatility_swaps'
  - '#volatility_trading'
---
# 1.5 TRADING VOLATILITY  

Practitioners or investors can take positions on expectations concerning the price of an asset.. Volatility trading involves positions taken on the volatility of the price. This is an attractive idea, but how does one buy or sell volatility? Answering this question will lead to a third basic methodology in financial engineering. This idea is a bit more complicated, so the argument here will only be an introduction. Chapter 9 will present a more detailed treatment of the methodology.  

In order to discuss volatility trading, we need to introduce the notion of convexity gains.. We start with a forward contract. Let us stay within the framework of the previous section and  

![](images/eac3325fd4b63df3f354c75daa5be720387519100895602fd2acf22f216ce722.jpg)  

# FIGURE 1.12  

Payoff function of long USD/YEN forward contract.  

assume that $F_{t_{0}}$ is the forward dollar-yen exchange rate.22 Suppose at time. $t_{0}$ we take a long position in USD as shown in Figure 1.12. The upward sloping line is the so-called payoff function.23 For example, if at time $t_{0}+\Delta$ the forward price becomes $F_{t_{0}+\Delta}$ , we can close the position with a gain:  

$$
\mathrm{Gain}=F_{t_{0}+\Delta}-F_{t_{0}}
$$  

It is important, for the ensuing discussion, that this payoff function be a straight line with a constant slope.  

Now, suppose there exists another instrument whose payoff depends on the. $F_{T}$ But this time the dependence is nonlinear24 or convex as shown in Figure 1.13 by the convex curve $C(F_{t})$ . It is important that the curve be smooth, and that the derivative.  

$$
\frac{\partial C(F_{t})}{\partial F_{t}}
$$  

exist at all points.  

Finally, suppose this payoff function has the additional property that as time passes the function changes shape. In fact as expiration time $T$ approaches, the curve becomes a (piecewise) straight line just like the forward contract payoff. This is shown in Figure 1.14.  

![](images/f0b90516260d902f61cef595a5a6460582ebff26a0a14ebdaf86d6ef088dcd63.jpg)  

# FIGURE 1.13  

Payoff function of a nonlinear (convex) instrument.  

![](images/9dbf3524151c8b4401c9de259a194544b6080c4d1c009d89a371f141b50d9c2e.jpg)  

# FIGURE 1.14  

Payoff function before and at expiration.  

# 1.5.1 A VOLATILITY TRADE  

Volatility trades depend on the simultaneous existence of two instruments, one whose value moves.   
linearly as the underlying risk changes, while the other's value moves according to a convex curve.  

First, suppose $\{F_{t_{1}},\ldots.F_{t_{n}}\}$ are the forward prices observed successively at times $t<t_{1}$ $t_{n}<T$ as shown in Figure 1.13. Note that these values are selected so that they oscillate around $F_{t_{0}}$  

Second, note that at every value of $F_{t_{i}}$ we can get an approximation of the curve $C(F_{t})$ using the tangent at that point as shown in Figure 1.13. Clearly, if we know the function $C(.)$ , we can then calculate the slope of these tangents. Let the slope of these tangents be denoted by $D_{i}$  

The third step is the crucial one. We form a portfolio that will eliminate the risk of directional movements in exchange rates. We first buy one unit of the $C(F_{t})$ at time $t_{0}$ . Note that we do need cash for doing this since the value at $t_{0}$ is nonzero.  

$$
0<C(F_{t_{0}})
$$  

Simultaneously, we sell. $D_{0}$ units of the forward contract. $F_{t_{0}}$ . Note that the forward sale does not require any upfront cash at time. $t_{0}$  

Finally, as time passes, we recalculate the tangent $D_{i}$ of that period and adjust the forward sale accordingly. For example, if the slope has increased, sell $D_{i}-D_{i-1}$ units more of the forward  

![](images/4c6c983a7c2f78e95ebdb6e564b22cbc4881259cee1aa3add26a61bdf6714c58.jpg)  

Ignore the movement of the curve, assumed small Note that as the curve moves down slope changes  

# FIGURE 1.15  

Oscillations in the forward price and rebalancing the hedge  

contracts. If the slope has decreased cover $D_{i}-D_{i-1}$ units of the forwards.25 As $F_{t_{i}}$ oscillates continue with this rebalancing.  

We can now calculate the net cash flows associated with this strategy. Consider the oscillations in Figures 1.13 and 1.15,  

$$
(F_{t_{i-1}}=F^{0}){\rightarrow}(F_{t_{i}}=F^{1}){\rightarrow}(F_{t_{i+1}}=F^{0})
$$  

with $F^{0}<F^{1}$ . In this setting if the trader follows the algorithm described above, then at every oscillation, the trader will  

1. First sell $D_{i}-D_{i-1}$ additional units at the price $F^{1}$   
2. Then, buy the same number of units at the price of $F^{0}$  

For each oscillation, the cash flows can be calculated as  

$$
{\mathrm{Gain}}=(D_{1}-D_{0})(F^{1}-F^{0})
$$  

Since $F^{0}<F^{1}$ and $D^{0}<D^{1}$ , this gain is positive as summarized in Figure 1.15. By hedging the orig inal position in $C(.)$ and periodically rebalancing the hedge, the trader has in fact succeeded to monetize the oscillations of $F_{t_{i}}$  

# 1.5.2 RECAP  

Look at what the trader has accomplished. By holding the convex instrument and then trading the linear instrument against it, the trader realized positive gains. These gains are bigger, the bigger the oscillations. Also they are bigger, the bigger the changes in the slope terms. $D_{i}.$ In fact, the trader gains whether the price goes down or up. The gains are proportional to the realized volatility..  

Clearly, this dynamic strategy has resulted in extracting cash from the volatility of the underlying forward rate $F_{t}.$ It turns out that one can package such expected volatility gains and sell them to clients. This leads to volatility trading. It is accomplished by using options and, lately, through volatility swaps.26  
