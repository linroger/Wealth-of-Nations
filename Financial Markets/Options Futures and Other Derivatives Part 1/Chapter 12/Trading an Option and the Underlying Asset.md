# 12.2 TRADING AN OPTION AND THE UNDERLYING ASSET  

For convenience, we will assume that the asset underlying the options considered in the. rest of the chapter is a stock. (Similar trading strategies can be developed for other underlying assets.) We will also follow the usual practice of calculating the profit from a. trading strategy as the final payoff minus the initial cost without any discounting..  

There are a number of different trading strategies involving a single option on a stock. and the stock itself. The profits from these are illustrated in Figure 12.1. In this figure and in other figures throughout this chapter, the dashed line shows the relationship. between profit and the stock price for the individual securities constituting the portfolio, whereas the solid line shows the relationship between profit and the stock price for the whole portfolio.  

In Figure 12.1a, the portfolio consists of a long position in a stock plus a short position in a European call option. This is known as writing a covered call. The long stock position "covers" or protects the investor from the payoff on the short call that becomes necessary if there is a sharp rise in the stock price. In Figure 12.1b, a short. position in a stock is combined with a long position in a call option. This is the reverse of writing a covered call. In Figure 12.1c, the investment strategy involves buying a European put option on a stock and the stock itself. This is referred to as a protective put strategy. In Figure 12.1d, a short position in a put option is combined with a short. position in the stock. This is the reverse of a protective put..  

The profit patterns in Figures 12.1a, b, c, and d have the same general shape as the. profit patterns discussed in Chapter 10 for short put, long put, long call, and short call, respectively. Put-call parity provides a way of understanding why this is so. From Chapter 11, the put-call parity relationship is.  

![](images/03a93cacbf9c725ddbbec713441bcbf4463bfcfb64bd4a81d125c7bb79c8e57d.jpg)  
Figure 12.1  Profit patterns (a) long position in a stock combined with short position in a call; (b) short position in a stock combined with long position in a call; (c) long position in a put combined with long position in a stock; (d) short position in a put combined with short position in a stock.  

$$
p+S_{0}=c+K e^{-r T}+D
$$  

where $p$ is the price of a European put, $S_{0}$ is the stock price, $c$ is the price of a European call, $K$ is the strike price of both call and put, $r$ is the risk-free interest rate, $T$ is the time to maturity of both call and put, and $D$ is the present value of the dividends anticipated during the life of the options.  

Equation (12.1) shows that a long position in a European put combined with a long. position in the stock is equivalent to a long European call position plus a certain. amount $(=K e^{-r T}+D)$ of cash. This explains why the profit pattern in Figure 12.1c is. similar to the profit pattern from a long call position. The position in Figure 12.1d is the reverse of that in Figure 12.1c and therefore leads to a profit pattern similar to that from a short call position.  

Equation (12.1) can be rearranged to become  

$$
S_{0}-c=K e^{-r T}+D-p
$$  

This shows that a long position in a stock combined with a short position in a European call is equivalent to a short European put position plus a certain amount $(=\Bar{K e^{-r T}}+D)$ of cash. This equality explains why the profit pattern in Figure 12.1a is similar to the profit pattern from a short put position. The position in Figure 12.1b is the reverse of that in Figure 12.1a and therefore leads to a profit pattern similar to that from a long put position.  
