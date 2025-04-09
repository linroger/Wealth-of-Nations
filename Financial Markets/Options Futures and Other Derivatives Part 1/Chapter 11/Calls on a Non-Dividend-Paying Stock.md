# 11.5 CALLS ON A NON-DIVIDEND-PAYING STOCK  

In this section, we first show that it is never optimal to exercise an American call option on a non-dividend-paying stock before the expiration date..  

To illustrate the general nature of the argument, consider an American call option on. a non-dividend-paying stock with one month to expiration when the stock price is $\$70$  

# Business Snapshot 11.1 Put-Call Parity and Capital Structure  

Fischer Black, Myron Scholes, and Robert Merton were the pioneers of option pricing. In the early 1970s, they also showed that options can be used to characterize the capital structure of a company. Today this analysis is widely used by financial institutions to assess a company's credit risk.  

To illustrate the analysis, consider a simple situation where a company has assets. that are financed with zero-coupon bonds and equity. The bonds mature in five years at which time a principal payment of. $K$ is required. The company pays no dividends.. If the assets are worth more than $K$ in five years, the equity holders choose to repay. the bond holders. If the assets are worth less than $K$ , the equity holders choose to. declare bankruptcy and the bond holders end up owning the company..  

The value of the equity in five years is therefore $\mathrm{max}(A_{T}-K,0)$ , where $A_{T}$ is the value of the company's assets at that time. This shows that the equity holders have a five-year European call option on the assets of the company with a strike price of $K$ What about the bond holders? They get $\operatorname*{min}(A_{T},K)$ in five years. This is the same as $K-\operatorname*{max}(K-A_{T},0)$ , so that today the bonds are worth the present value of $K$ minus the value of a five-year European put option on the assets with a strike price of $K$  

To summarize, if $c$ and $p$ are the values, respectively, of five-year call and put options on the company's assets with strike price $K$ , then  

$$
\begin{array}{r l}&{\mathrm{Value~of~company's~equity}=c}\ &{\mathrm{Value~of~company's~debt}=P V(K)-p}\end{array}
$$  

Denote the value of the assets of the company today by $A_{0}$ . The value of the assets must equal the total value of the instruments used to finance the assets. This means that it must equal the sum of the value of the equity and the value of the debt, so that  

$$
A_{0}=c+\left[P V(K)-p\right]
$$  

Rearranging this equation, we have  

$$
c+P V(K)=p+A_{0}
$$  

This is the put-call parity result in equation (11.6) for call and put options on the assets of the company.  

and the strike price is $\$40$ . The option is deep in the money, and the investor who owns the option might well be tempted to exercise it immediately. However, if the investor plans to hold the stock obtained by exercising the option for more than one month, this is not the best strategy. A better course of action is to keep the option and exercise it at the end of the month. The $\$40$ strike price is then paid out one month later than it would be if the option were exercised immediately, so that interest is earned on the. $\$40$ for one month. Because the stock pays no dividends, no income from the stock is. sacrificed. A further advantage of waiting rather than exercising immediately is that. there is some chance (however remote) that the stock price will fall below. $\$40$ in one month. In this case the investor will not exercise in one month and will be glad that the decision to exercise early was not taken!  

This argument shows that there are no advantages to exercising early if the investor.   
plans to keep the stock for the remaining life of the option (one month, in this case).   
What if the investor thinks the stock is currently overpriced and is wondering whether.  

to exercise the option and sell the stock? In this case, the investor is better off selling the option than exercising it.4 The option will be bought by another investor who does. want to hold the stock. Such investors must exist. Otherwise the current stock price would not be $\$70$ . The price obtained for the option will be greater than its intrinsic. value of $\$30$ , for the reasons mentioned earlier..  

For a more formal argument, we can use equation (11.4):  

$$
c\ge S_{0}-K e^{-r T}
$$  

Because the owner of an American call has all the exercise opportunities open to the owner of the corresponding European call, we must have. $C\geq c$ . Hence,  

$$
C\geq S_{0}-K e^{-r T}
$$  

Given $r>0$ , it follows that $C{>}S_{0}{-}K$ when $T>0$ This means that $C$ is always greater than the option's intrinsic value prior to maturity. If it were optimal to exercise at a particular time prior to maturity, $C$ would equal the option's intrinsic value at that time. It follows that it can never be optimal to exercise early.  

To summarize, there are two reasons an American call on a non-dividend-paying. stock should not be exercised early. One relates to the insurance that it provides. A call option, when held instead of the stock itself, in effect insures the holder against the stock price falling below the strike price. Once the option has been exercised and the strike price has been exchanged for the stock price, this insurance vanishes. The other reason concerns the time value of money. From the perspective of the option holder, the later the strike price is paid out the better..  

# Bounds  

Because American call options are never exercised early when there are no dividends, they are equivalent to European call options, so that $C=c$ . From equations (11.1)  

![](be879285b8c4540f960cafa7d5af421fecdc8e03f9aef7185542299963e6afe7.jpg)  
Figure 11.3 Bounds for European and American call options when there are no dividends.  

![](c4152b3627440ea0a445fccbee93217a5c4690d3b8b2560d909d0b5b3a12a377.jpg)  
Figure 11.4  Variation of price of an American or European call option on a non-. dividend-paying stock with the stock price. Curve moves in the direction of the arrows when there is an increase in the interest rate, time to maturity, or stock price volatility..  

and (11.4), it follows that lower and upper bounds for both $c$ and $C$ are given by  

$$
\operatorname*{max}(S_{0}-K e^{-r T},0)\quad\mathrm{and}\quad S_{0}
$$  

respectively. These bounds are illustrated in Figure 11.3.  

The general way in which the call price varies with the stock price, $S_{0}$ is shown in Figure 11.4. As $r$ or $T$ or the stock price volatility increases, the line relating the call price to the stock price moves in the direction indicated by the arrows.  
