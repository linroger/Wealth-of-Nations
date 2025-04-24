# MECHANICS OF OPTIONS  

# 9  

# CHAPTER OUTLINE  

9.1 Introduction . 268   
9.2 What Is an Option?. 269   
.3 Options: Definition and Notation.. 271   
9.3.1 Notation .. 271   
9.3.2 On Retail Use of Options.. 275   
9.3.3 Some Intriguing Properties of the Diagram... 275   
.4 Options as Volatility Instruments .. 277   
9.4.1 Initial Position and the Hedge 277   
9.4.2 Adjusting the Hedge Over Time... . 281   
9.4.2.1 Limiting form ... .284   
9.4.3 Other Cash Flows... 285   
9.4.4 Option Gains and Losses as a PDE . 285   
9.4.5 Cash Flows at Expiration . 286   
9.4.6 An Example . 287   
9.4.6.1 Some caveats... .288   
.5 Tools for Options.. 289   
9.5.1 Solving the Fundamental PDE 289   
9.5.2 Black Scholes Formula. 290   
9.5.2.1 Black’s formula .. .291   
9.5.3 Other Formulas . 292   
9.5.3.1 Chooser options . .292   
9.5.3.2 Barrier options . .293   
9.5.4 Uses of Black Scholes Type Formulas 295   
9.6 The Greeks and Their Uses. 296   
9.6.1 Delta . 297   
9.6.1.1 Convention.. .298   
9.6.1.2 The exact expression.. .298   
9.6.2 Gamma.. 300   
9.6.2.1 Market use.. .302   
9.6.3 Vega... 303   
9.6.3.1 Market use.. .305   
9.6.3.2 Vega hedging . .305   
9.6.4 Theta .. 305   
9.6.5 Omega.. 306  

9.6.6 Higher-Order Derivatives . 306   
9.6.7 Greeks and PDEs. 307   
9.6.7.1 Gamma trading . .308   
9.6.7.2 Gamma trading versus Vega .308   
9.6.7.3 Which expectation?.. .309   
9.7 Real-Life Complications... 309   
9.7.1 Dealing with Option Books 310   
9.7.2 Futures as Underlying .. . 310   
9.7.2.1 Delivery mismatch .. .311   
9.8 Conclusion: What Is an Option?... 311   
Suggested Reading .. 311   
Appendix 9.1 ... 311   
Derivation of Delta... 311   
Derivation of Gamma ... 313   
Appendix 9.2 . 313   
Stochastic Differential Equations... 313   
Examples . . 313   
Ito’s Lemma.. . 314   
Girsanov Theorem.. . 314   
Exercises ..... . 315  

# 9.1 INTRODUCTION  

This chapter is an introduction to methods used in dealing with optionality in financial instruments. Compared to most existing textbooks, the present text adopts a different way of looking at options. We discuss options from the point of view of an options market maker. In our setting, options are not presented as instruments to bet on or hedge against the direction of an underlying risk. Instead, options are motivated as instruments of volatility.  

In the traditional textbook approach, options are introduced as directional instruments. This is not how market professionals think of options. In most textbooks, a call option becomes in-the-money and hence profitable if the underlying price increases, indirectly associating it with a bullish view. The treatment of put options is similar. Puts are seen as appropriate for an investor who thinks the price of the underlying asset is going to decrease. For an end investor or retail client, such directional motivation for options may be natural. But, looking at options this way is misleading if we are concerned with the interbank or interdealer market. In fact, motivating options as directional tools will disguise the fundamental aspect of these instruments, namely that options are tools for trading volatility. The intuition behind these two views of options is quite different, and we would like the reader to think like an option trader or market maker.  

This chapter intends to show that an option exposure, when fully put in place, is an impure position on the way volatility is expected to change. A market maker with a net long position in options is someone who is “expecting” the volatility to increase. A market maker who is short the option is someone who thinks that the volatility of the underlying is going to decrease. Sometimes such positions are taken as funding vehicles.  

![](97bdd74e21136f23751f4f425f0b9f5e9703fecb915a46d56d3209a57d1340d6.jpg)  

# FIGURE 9.1  

Two possible stock price trajectories.  

In this sense, a trader’s way of looking at puts and calls is in complete contrast to the directional view of options. For example, market makers look at European calls and puts as if they were identical objects. As we will see in this chapter, from an option market maker’s point of view, there is really no difference between buying a call or buying a put. Both of these transactions, in the end, result in the same payoff. Consider Figure 9.1, where we show two possible intraday trajectories of an underlying price, $S_{t}$ . In one case prices are falling rapidly, while in the other, prices are rising. An option trader will sell puts or calls with the same ease. As we will see, the trader may be concerned with whether he should sell or buy any options, rather than which type of option to sell.  

In this chapter and the next, we intend to clarify the connection between volatility and option prices. However, we first review some basics.  

# 9.2 WHAT IS AN OPTION?  

From a market practitioner’s point of view, options are instruments of volatility. A retail investor who owns a call on an asset, $S_{t}$ , may feel that a persistent upward movement in the price of this asset is “good” for him or her. But, a market maker who may be long in the same call may prefer  

that the underlying price $S_{t}$ oscillate as much as possible, as often as possible. The more frequently and violently prices oscillate, the more long (short) positions in option books will gain (lose), regardless of whether calls or puts are owned.  

The following reading is a good example as to how option traders look at options.  

# EXAMPLE  

Wall Street firms are gearing up to recommend long single-stock vol positions on companies about to report earnings. While earnings seasons often offer opportunities for going long vol via buying Calls or Puts, this season should present plenty of opportunities to benefit from long vol positions given overall negative investor sentiment. Worse-than-expected earnings releases from one company can send shockwaves through the entire market.   
The big potential profit from these trades is from gamma, in other words, large moves in the underlying, rather than changes in implied vol. One promising name. . . announced in mid-February that manufacturing process and control issues have led to reduced sales of certain products in the United States, which it expected to influence its first quarter and full-year sales and earnings. On Friday, options maturing in August had a mid-market implied vol of around $43\%$ , which implies a $2.75\%$ move in the stock per trading day. Over the last month, the stock has been moving on average $3\%$ a day, which means that by buying options on the company, you’re getting vol cheap.  

(Derivatives Week, now part of GlobalCapital, April 1, 2001)  

This reading illustrates several important characteristics of options. First, we clearly see that puts and calls are considered as similar instruments by market practitioners. The issue is not to buy puts or calls, but whether or not to buy them.  

Second, and this is related to the first point, note that market participants are concerned with volatilities and not with the direction of prices—referring to volatility simply as vol. Market professionals are interested in the difference between actual daily volatilities of stock prices and the volatilities implied by the options. Implied volatility is calculated by taking the observed option price in the market and a pricing formula such as the Black Scholes formula that will be introduced below and backing out the volatility that is consistent with the option price given other input parameters such as the strike price of the option, for example. The last sentence in the reading is a good (but potentially misleading) example of this. The reading suggests that options imply a daily volatility of $2.75\%$ , while the actual daily volatility of the stock price is $3\%$ . According to this, options are considered “cheap,” since the actual underlying moves more than what the option price implies on a given day.1 This distinction between implied volatility and “actual volatility” should be kept in mind. Actual volatility is also sometimes referred to as realized volatility.  

Finally, the reading seems to refer to two different types of gains from volatility. One, from “large movements in the underlying price,” leads to gamma gains, and the other, from implied volatility, leads to vega gains. During this particular episode, market professionals were expecting implied volatility to remain the same, while the underlying assets exhibited sizable fluctuations. It is difficult, at the outset, to understand this difference. The present chapter will clarify these notions and reconcile the market professional’s view of options with the directional approach the reader may have been exposed to earlier.2  

# 9.3 OPTIONS: DEFINITION AND NOTATION  

Option contracts are generally divided into the categories of plain vanilla and exotic options, although many of the options that used to be known as exotic are vanilla instruments today. In discussing options, it is good practice to start with a simple benchmark model, understand the basics of options, and then extend the approach to more complicated instruments. This simple benchmark will be a plain vanilla option treated within the framework of the BlackScholes model.  

The buyer of an option does not buy the underlying instrument; he or she buys a right. If this right can be exercised only at the expiration date, then the option is European. If it can be exercised anytime during the specified period, the option is said to be American. A Bermudan option is “in between,” given that it can be exercised at more than one of the dates during the life of the option.  

In the case of a European plain vanilla call, the option holder has purchased the right to “buy” the underlying instrument at a certain price, called the strike or exercise price, at a specific date, called the expiration date. In the case of the European plain vanilla put, the option holder has again purchased the right to an action. The action in this case is to “sell” the underlying instrument at the strike price and at the expiration date.  

American-style options can be exercised anytime until expiration and hence may be more expensive. They may carry an early exercise premium. At the expiration date, options cease to exist. In this chapter, we discuss basic properties of options using mostly plain vanilla calls. Obviously, the treatment of puts would be similar.  

# 9.3.1 NOTATION  

We denote the strike prices by the symbol $K$ , and the expiration date by $T$ . The price or value of the underlying instrument will be denoted by $S_{t}$ if it is a cash product, and by $F_{t}$ if the underlying is a forward or futures price. The fair price of the call at time $t$ will be denoted by $C(t)$ , and the price of the put by $P(t)$ .3 These prices depend on the variables and parameters underlying the contract. We use $S_{t}$ as the underlying, and write the corresponding call option pricing function as  

$$
C(t)=C(S_{t},t|r,K,\sigma,T)
$$  

Here, $\sigma$ is the volatility of $S_{t}$ and $r$ is the spot interest rate, assumed to be constant. In more compact form, this formula can be expressed as  

$$
C(t)=C(S_{t},t)
$$  

This function is assumed to have the following partial derivatives:  

$$
\frac{\partial C(S_{t},t)}{\partial S_{t}}=C_{s}
$$  

$$
\frac{\hat{\sigma}^{2}C(S_{t},t)}{\hat{\sigma}S_{t}^{2}}=C_{s s}
$$  

$$
\frac{\partial C(S_{t},t)}{\partial t}=C_{t}
$$  

More is known on the properties of these partials. Everything else being the same, if $S_{t}$ increases, the call option price, $C(t)$ , also increases. If $S_{t}$ declines, the price declines. But the changes in $C(t)$ will never exceed those in the underlying asset, $S_{t}$ . Hence, we should have  

$$
0<C_{s}<1
$$  

At the same time, everything else being the same, as $t$ increases, the life of the option gets shorter and the time value declines,  

$$
C_{t}<0
$$  

Finally, the expiration payoff of the call (put) option is a convex function, and we expect the $C(S_{t},t)$ to be convex as well. This means that  

$$
0<C_{s s}
$$  

This information about the partial derivatives is assumed to be known even when the exact form of $C\left(S_{t},t\right)$ itself is not known.  

The notation in Eq. (9.1) suggests that the partials themselves are functions of $S_{t},r,K,t,T_{:}$ , and $\sigma$ . Hence, one may envisage some further higher-order partials. The traditional BlackScholes vanilla option pricing environment uses the partials, $\{C_{s},C_{s s},C_{t}\}$ only. Further partial derivatives are brought into the picture as the Black Scholes assumptions are relaxed gradually.  

Figure 9.2 shows the expiration date payoffs of plain vanilla put and call options. In the same figure we have the time t, $t<T$ value of the calls and puts. These values trace a smooth convex curve obtained from the Black Scholes formula.  

We now consider a real-life application of these concepts. The following example looks at Microsoft options traded at the Chicago Board of Options Exchange and discusses various parameters within this context.  

![](e2a74ccb316e1acf1c04ad9d948ea5bfeb0baf6906144f17d1953d4b84cb2a57.jpg)  

# FIGURE 9.2  

Expiration date payoffs of plain vanilla put and call options.  

# EXAMPLE  

Suppose Microsoft (MSFT) is “currently” trading at 61.15 at Nasdaq. Further, the overnight rate is $2.7\%$ . We have the following quotes from the Chicago Board of Options Exchange (CBOE).  

In the table, the first column gives the expiration date and the strike level of the option. The exact time of expiration is the third Friday of every month. These equity options in CBOE are of American style. The bid price is the price at which the market maker is willing to buy this option from the client, whereas the ask price is the price at which he or she is willing to sell it to the client.  

<html><body><table><tr><td>Calls</td><td>Bid</td><td>Volume</td><td></td></tr><tr><td>Nov 55.00</td><td>7.1</td><td>Ask 7.4</td><td>78</td></tr><tr><td>Nov 60.00</td><td>3.4</td><td>3.7</td><td>6291</td></tr><tr><td>Nov 65.00</td><td>1.2</td><td>1.3</td><td>1456</td></tr><tr><td>Nov 70.00</td><td>0.3</td><td>0.4</td><td>98</td></tr><tr><td>Dec 55.00</td><td>8.4</td><td>8.7</td><td>0</td></tr><tr><td>Dec 60.00</td><td>5</td><td>5.3</td><td>29</td></tr><tr><td>Dec 65.00</td><td>2.65</td><td>2.75</td><td>83</td></tr><tr><td>Dec 70.00</td><td>1.2</td><td>1.25</td><td>284</td></tr></table></body></html>  

<html><body><table><tr><td>Puts</td><td>Bid</td><td>Ask Volume</td><td></td></tr><tr><td>Nov 55.00</td><td>0.9</td><td>1.05</td><td>202</td></tr><tr><td>Nov 60.00</td><td>2.3</td><td>2.55</td><td>5984</td></tr><tr><td>Nov 65.00</td><td>5</td><td>5.3</td><td>64</td></tr><tr><td>Nov 70.00</td><td>9</td><td>9.3</td><td>20</td></tr><tr><td>Dec55.00</td><td>2.05</td><td>2.35</td><td>10</td></tr><tr><td>Dec 60.00</td><td>3.8</td><td>4.1</td><td>76</td></tr><tr><td>Dec 65.00</td><td>6.3</td><td>6.6</td><td>10</td></tr><tr><td>Dec70.00</td><td>9.8</td><td>10.1</td><td>25</td></tr></table></body></html>

Note: October 24, 2002, 11:02 A.M. data from CBOE.  

CBOE option prices are multiplied by $\$100$ and then invoiced. Of course, there are some additional costs to buying and selling options due to commissions and possibly other expenses. The last column of the table indicates the trading volume of the relevant contract.  

For example, consider the November 55 put. This option will be in-the-money, if the Microsoft stock is below 55.00. If it stays so until the third Friday of November 2001, the option will have a positive payoff at expiration.  

100 such puts will cost  

$$
1.05\times100\times100=\S10,500
$$  

plus commissions to buy, and can be sold at  

$$
0.90\times100\times100=\S9000
$$  

if sold at the bid price. Note that the bid ask spread for one “lot” had a value of $\$1500$ that day.  

We now study option mechanics more closely and introduce further terminology.  

# 9.3.2 ON RETAIL USE OF OPTIONS  

Consider a retail client and an option market maker as the two sides of the transaction. Suppose a business uses the commodity $S_{t}$ as a production input and would like to “cap” the price $\overline{{S_{T}}}$ at a future date T. For this insurance, the business takes a long position using call options on $S_{t}$ . The call option premium is denoted by $C(t)$ . By buying the call, the client makes sure that he or she can buy one unit of the underlying at a maximum price $K$ , at expiration date $T.$ If at time $T_{\mathbf{\delta}}$ , $S_{T}$ is lower than $K$ , the client will not exercise the option. There is no need to pay $K$ dollars for something that is selling for less in the marketplace. The option will be exercised only if $S_{T}$ equals or exceeds $K$ at time $T$ .  

Looked at this way, options are somewhat similar to standard insurance against potential increases in commodities prices. In such a framework, options can be motivated as directional instruments. One has the impression that an increase in $\overline{{S_{t}}}$ is harmful for the client, and that the call “protects” against this risk. The situation for puts is symmetrical. Puts appear to provide protection against the risk of undesirable “declines” in $S_{t}$ . In both cases, a certain direction in the change of the underlying price $S_{t}$ is associated with the call or put, and these appear to be fundamentally different instruments.  

Figure 9.3 illustrates these ideas graphically. The upper part shows the payoff diagram for a call option. Initially, at time $t_{0}$ , the underlying price is at $S_{t_{0}}$ . Note that $S_{t_{0}}<K$ , and the option is out-ofthe-money. Obviously, this does not mean that the right to buy the asset at time $T$ for $K$ dollars has no value. In fact, from a client’s point of view, $S_{t}$ may move up during interval $t\in[t_{O},\ T]$ and end up exceeding $K$ by time $T.$ This will make the option in-the-money. It would then be profitable to exercise the option and buy the underlying at a price $K$ . The option payoff will be the difference $S_{T}-K$ , if $S_{T}$ exceeds $K$ . This payoff can be shown either on the horizontal axis or, more explicitly, on the vertical axis.4 Thus, looked at from the retail client’s point of view, even at the price level $S_{t_{0}}$ , the out-of-the money option is valuable, since it may become in-the-money later. Often, the directional motivation of options is based on these kinds of arguments.  

If the option expires at $S_{T}{=}K$ , the option will be at-the-money (ATM) and the option holder may or may not choose to receive the underlying. However, as the costs associated with delivery of the call underlying are, in general, less than the transaction costs of buying the underlying in the open market, some holders of ATM options prefer to exercise.  

Hence, we get the typical price diagram for a plain vanilla European call option. The option price for $t\in[t_{O},T]$ is shown in Figure 9.3 as a smooth convex curve that converges to the piecewise linear option payoff as expiration time $T$ approaches. The vertical distance between the payoff line and the horizontal axis is called intrinsic value. The vertical distance between the option price curve and the expiration payoff is called the time value of the option. Note that for a fixed $t$ , the time value appears to be at a maximum when the option is ATM—that is to say, when $S_{t}=K$ .  

# 9.3.3 SOME INTRIGUING PROPERTIES OF THE DIAGRAM  

Consider point $\overline{{A}}$ in the top part of Figure 9.3. Here, at time $t$ , the option is deep out-of-the money. $S_{t}$ is close to the origin and the time value is close to zero. The tangent at point $A$ has a positive  

![](2377f6b300ab52aa9d55c1f9140cead7fb4bcfa62312f10752c29f4de3b1e3e1.jpg)  

# FIGURE 9.3  

Value of in-the-money, out-of-the-money, and ATM call.  

slope that is little different from zero. The curve is almost “linear” and the second derivative is also close to zero. This means that for small changes in $S_{t}$ , the slope of the tangent will not vary much.  

Now, consider the case represented by point $B$ in Figure 9.3. Here, at time $t$ , the option is deep in-the-money. $\overline{{S_{t}}}$ is significantly higher than the strike price. However, the time value is again close to zero. The curve approaches the payoff line and hence has a slope close to $+1$ . Yet, the second derivative of the curve is once again very close to zero. This again means that for small changes in $S_{t}$ , the slope of the tangent will not vary much.  

The third case is shown as point $C$ in the lower part of Figure 9.3. Suppose the option was ATM at time $t$ , as shown by point $C$ . The value of the option is entirely made of time value. Also, the slope of the tangent is close to 0.5. Finally, it is interesting that the curvature of the option is highest at point $C$ and that if $\overline{{S_{t}}}$ changes a little, the slope of the tangent will change significantly.  

This brings us to an interesting point. The more convex the curve is at a point, the higher the associated time value seems to be. In the two extreme cases where the slope of the curve is diametrically different, namely at points $A$ and $B$ , the option has a small time value. At both points, the second derivative of the curve is small. When the curvature reaches its maximum, the time value is greatest. The question, of course, is whether or not this is a coincidence.  

Pursuing this connection between time value and curvature further will lead us to valuing the underlying volatility. Suppose, by holding an option, a market maker can somehow generate “cash” earnings as $S_{t}$ oscillates. Could it be that, everything else being the same, the greater the curvature of $C(t)$ , the greater the cash earnings are? Our task in the next section is to show that this is indeed the case.  

# 9.4 OPTIONS AS VOLATILITY INSTRUMENTS  

In this section we see how convexity is translated into cash earnings, as $S_{t}$ oscillates and creates time value.6 The discussion is conducted in a highly simplified environment to facilitate understanding of the relationship between volatility and cash gains (losses) of long (short) option positions.  

Consider a market maker who quotes two-way prices for a European vanilla call option $C(t)$ , with strike $K$ , and expiration $T_{\mathbf{\delta}}$ , written on a nondividend paying asset, denoted by $S_{t}$ .7 Let the riskfree interest rate $r$ be constant. For simplicity, consider an ATM option, $K=S_{t}$ . In the following, we first show the initial steps taken by the market maker who buys an option. Then, we show how the market maker hedges this position dynamically and earns some cash due to $S_{t}$ oscillations.  

# 9.4.1 INITIAL POSITION AND THE HEDGE  

Suppose this market maker buys a call option from a client.8 The initial position of the market maker is shown in the top portion of Figure 9.4. It is a standard long call position. The market maker is not an investor or speculator, and this option is bought with the purpose of keeping it on the books and then selling it to another client. Hence, some mechanical procedures should be followed. First, the market maker needs to fund this position. Second, he or she should hedge the associated risks.  

![](84eb34f3ea011e20e3ee2bf1d98b3aed2d16faf90cd73758c2997c98e39f2c20.jpg)  

# FIGURE 9.4  

Funding a long call position with borrowing.  

We start with the first requirement. Unlike the end investor, market makers never have “money” of their own. The trade needs to be funded. There are at least two ways of doing this. One is to short an appropriate asset in order to generate the needed funds, while the other is to borrow these funds directly from the money market desk.9 Suppose the second possibility is selected and the market maker borrows $C(t)$ dollars from the money market desk at an interest rate $r_{t}=r$ . The net position that puts together the option and the borrowed funds is shown in the bottom part of Figure 9.4.  

Now, consider the risks of the position. It is clear from Figure 9.4 that the long call position funded by a money market loan is similar to going long the $S_{t}$ . If $S_{t}$ decreases, the position’s value will decrease, and a market maker who takes such positions many times on a given day cannot afford this. The market maker must hedge this risk by taking another position that will offset these possible gains or losses. When $S_{t}$ declines, a short position in $S_{t}$ gains. As $S_{t}$ changes by $\Delta S_{t}$ , a short position will change by $-\Delta S_{t}$ . Thus, we might think of using this short position as a hedge.  

But there is a potential problem. The long call position is described by a curve, whereas the short position in $\overline{{S_{t}}}$ is represented by a line. This means that the responses of $C(t)$ and $S_{t},$ , to a change in $S_{t}$ , are not going to be identical. Everything else being the same, if the underlying changes by $\Delta S_{t}$ , the change in the option price will be approximately1  

$$
\Delta C(t)\cong C_{s}\Delta S_{t}
$$  

The change in the short position on the other hand will equal $-\Delta S_{t}$ . In fact, the net response of the portfolio  

$$
V_{t}=\{\log C(t),{\mathrm{short}}S_{t}\}
$$  

to a small change in $S_{t}$ will be given by the first-order approximation,  

$$
\begin{array}{c}{\Delta V_{t}\cong C_{s}\Delta S_{t}-\Delta S_{t}}\\ {}\\ {=(C_{s}-1)\Delta S_{t}<0}\end{array}
$$  

due to the condition $0<C_{s}<1$ . This position is shown in Figure 9.5. It is still a risky position and, interestingly, the risks are reversed. The market maker will now lose money if $S_{t}$ increases. In fact, this position amounts to a long put financed by a money market loan.  

How can the risks associated with the movements in $S_{t}$ be eliminated? In fact, consider Figure 9.5. We can approximate the option value by using the tangent at point $S_{t}=K.$ . This would also be a line. We can then adjust the short position accordingly. According to Eq. (9.14), short selling one unit of $S_{t}$ overdid the hedge. Figure 9.5 suggests that the market maker should short $h_{t}$ units of $S_{t}.$ , selecting the $h_{t}$ according to  

$$
h_{t}=\frac{\partial C(S_{t},t)}{\partial S_{t}}=C_{s}
$$  

To see why this might work, consider the new portfolio, $V_{t}$ :  

If $S_{t}$ changes by $\Delta S_{t},$ everything else being the same, the change in this portfolio’s value will be approximately  

$$
\Delta V_{t}\cong[C(S_{t}+\Delta S_{t},t)-C(S_{t},t)]-C_{s}\Delta S_{t}
$$  

![](411c0d22ad51819ffc981c4ed435d34aef10102a65443308310e8df7cb72d2c6.jpg)  

# FIGURE 9.5  

Long call and short futures position.  

We can use a first-order Taylor series approximation of $C(S_{t}+\Delta S_{t},t)$ , around point $S_{t},$ to simplify this relationship:11  

$$
C(S_{t}+\Delta S_{t},t)=C(S_{t},t)+\frac{\hat{\sigma}C(S_{t},t)}{\hat{\sigma}S_{t}}\Delta S_{t}+R
$$  

Here, $R$ is the remainder. The right-hand side of this formula can be substituted in Eq. (9.17) to obtain  

$$
\Delta V_{t}\cong\left[{\frac{\partial C(S_{t},t)}{\partial S_{t}}}\Delta S_{t}+R\right]-C_{s}\Delta S_{t}
$$  

After using the definition  

$$
\frac{\partial C(S_{t},t)}{\partial S_{t}}=C_{s}
$$  

and simplifying, this becomes  

$$
\Delta V_{t}\cong R
$$  

That is to say, this portfolio’s sensitivity toward changes in $S_{t}$ will be the remainder term, $R$ . It is related to Ito’s Lemma, shown in Appendix 9.2. The biggest term in the remainder is given by  

$$
\frac{1}{2}\frac{\partial^{2}C(S_{t},t)}{\partial S_{t}^{2}}(\Delta S_{t})^{2}
$$  

Since the second partial derivative of $C(t)$ is always positive, the portfolio’s value will always be positively affected by small changes in $S_{t}$ This is shown in the bottom part of Figure 9.6. A portfolio such as this one is said to be delta neutral. That is to say, the delta exposure, represented by the first-order sensitivity of the position to changes in $S_{t}$ , is zero. Note that during this discussion the time variable, $t$ , was treated as a constant.  

This way of constructing a hedge for options is called delta hedging and $h_{t}$ is called the hedge ratio. It is important to realize that the procedure will need constant updating of the hedge ratio, $h_{t}.$ , as time passes and $S_{t}$ changes. After all, the idea depends on a first-order Taylor series approximation of a nonlinear instrument using a linear instrument. Yet, Taylor series approximations are local and they are satisfactory only for a reasonable neighborhood around the initial $S_{t}$ . As $S_{t}$ changes, the approximation needs to be adjusted. Consider Figure 9.7. When $S_{t}$ moves from point $A$ to point $B$ , the approximation at $A$ deteriorates and a new approximation is needed. This new approximation will be the tangent at point $B$ .  

# 9.4.2 ADJUSTING THE HEDGE OVER TIME  

We now consider what happens to the delta-hedged position as $S_{t}$ oscillates. According to our discussion in the previous chapter, as time passes, the replicating portfolio needs to be rebalanced. This rebalancing will generate cash gains.  

We discuss these portfolio adjustments in a highly simplified environment. Considering a sequence of simple oscillations in $S_{t}$ around an initial point $S_{t_{0}}=S^{0}$ , let  

$$
t_{0}<t_{1}<\dots<t_{n}
$$  

with  

$$
t_{i}-t_{i-1}=\Delta
$$  

![](1de5df39d7535e5b2b2c2c81d2ce566acc49ef04e9dda021ab7ea852e4f5c9bc.jpg)  

# FIGURE 9.6  

Delta neutral portfolio example.  

denote successive time periods that are apart $\Delta$ units of time. We assume that $S_{t}$ oscillates at an annual percentage rate of one standard deviation, $\sigma$ , around the initial point $S_{t_{0}}=S^{0}$ . For example, one possible round turn may be  

$$
S^{0}\to(S^{0}+\Delta S)\to S^{0}
$$  

With $\Delta S=\sigma S^{0}\sqrt{\Delta}$ , the percentage oscillations will be proportional to $\sqrt{\Delta}$ . The mechanics of maintaining the delta-hedged long call position will be discussed in this simplified setting.  

![](eeefe06755b280730f1f21373dd9c19ea535e3aec1c66d1223051bcf12ee8143.jpg)  

# FIGURE 9.7  

Oscillations in underlying and changes in hedge ratio.  

Since $S_{t_{i}}$ moves between three possible values only, we simplify the notation and denote the possible values of St by S2, S0, and S1, where12  

$$
\begin{array}{c}{{S^{+}=S^{0}+\Delta S}}\\ {{S^{-}=S^{0}-\Delta S}}\end{array}
$$  

We now show how these oscillations generate cash gains. According to Figure 9.7, as $S_{t}$ fluctuates, the slope, $C_{s}$ , of the $C(S_{t},t)$ also changes. Ignoring the effect of time, the slope will change, say, between $C_{s}^{+},C_{s}^{0}$ , and $C_{s}^{-}$ , as shown in Figure 9.7.13 We note that  

$$
C_{s}^{-}<C_{s}^{0}<C_{s}^{+}
$$  

12 We can represent this trajectory by a three-state Markov chain that has the following probabilities:  

$$
P(S^{0}\mid S^{+})=1\quad P(S^{-}\mid S^{0})=\frac{1}{2}\quad P(S^{+}\mid S^{0})=\frac{1}{2}\quad P(S^{0}\mid S^{-})=1
$$  

where $S^{0}$ is the sorting value. If prices are at $S^{+}$ or $S^{-}$ they always go back to $S_{\mathbf{0}}$ . From $S_{\mathbf{0}}$ , they can either go up or down.   
$^{13}\mathrm{It}$ is important to realize that these slopes also depend on time $t$ , although, to simplify the notation, we are omitting the time index here.  

for all $t_{i}$ . This means that as $S_{t}$ moves, $h_{t}$ , the hedge ratio will change in a particular way. In order to keep the portfolio delta-hedged, the market maker needs to adjust the number of the underlying $S_{t}$ that was shorted.  

Second, and unexpectedly, the hedge adjustments have a “nice” effect. When $\overline{{S_{t}}}$ moves from $S^{+}$ to ${\boldsymbol{S}}^{0}$ or from ${\boldsymbol{S}}^{0}$ to $S^{-}$ , the market maker has to decrease the size of the short position in $S_{t}$ . To do this, the market maker needs to “buy” back a portion of the underlying asset that was originally shorted at a higher price ${\boldsymbol{S}}^{0}$ or $S^{+}$ .  

Accordingly, the market maker sells short when prices are high and covers part of the position when prices decline. This leads to cash gains.  

Consider now what happens when the move is from $S^{0}$ to $S^{+}$ . The new slope, $C_{s}^{+}$ , is steeper than the old, $C_{s}^{0}$ . This means that the market maker needs to short more of the $S_{t}$ asset at the new price. When $S_{t}$ moves back to $\overline{{S}}^{0}$ , these shorts are covered at $\overline{{S}}^{0}$ , which is lower than $\overline{{S^{+}}}$ .  

Thus, as $S_{t}$ oscillates around $S^{0}$ , the portfolio is adjusted accordingly, and the market maker would automatically sell high and buy low. At every round turn, say, $\{\bar{S^{0}},\bar{S}^{+},S^{0}\}$ , which takes two periods, the hedge adjustments will generate a cash gain equal to  

$$
(C_{s}^{+}-C_{s}^{0})[(S^{0}+\Delta S)-S^{0}]=(C_{s}^{+}-C_{s}^{0})\Delta S
$$  

Here, $(C_{s}^{+}-C_{s}^{0})$ represents the number of $S_{t}$ assets that were shorted after the price moved from $S^{0}$ to $S^{+}$ . Once the price goes back to $\overline{{S}}^{0}$ , the same securities are purchased at a lower price. It is interesting to look at these trading gains as the time interval, $\Delta$ , becomes smaller and smaller.  

# 9.4.2.1 Limiting form  

As $\Delta S{\rightarrow}0$ , we can show an important approximation to the trading (hedging) gains  

$$
(C_{s}^{+}-C_{s}^{0})\Delta S
$$  

The term $(C_{s}^{+}-C_{s}^{0})$ is the change in the first partial derivative of $C\left(S_{t},t\right)$ , as $S_{t}$ moves from $S_{t_{0}}$ to a new level denoted by $S_{t_{0}}+\Delta S$ . We can convert $(C_{s}^{+}-C_{s}^{0})$ into a rate of change after multiplying and dividing by $\Delta S$ :  

$$
(C_{s}^{+}-C_{s}^{0})\Delta S=\frac{C_{s}^{+}-C_{s}^{0}}{\Delta S}(\Delta S)^{2}
$$  

As we let $\Delta S$ go to zero, we obtain the approximation  

$$
\frac{C_{s}^{+}-C_{s}^{0}}{\Delta S}\cong\frac{\hat{\sigma}^{2}C(S_{t},t)}{\hat{\sigma}S_{t}^{2}}
$$  

Thus, the round-turn gains from delta-hedge adjustments shown in Eq. (9.29) can be approximated as  

$$
(C_{s}^{+}-C_{s}^{0})\Delta S\cong\frac{\hat{\sigma}^{2}C(S_{t},t)}{\hat{\sigma}S_{t}^{2}}(\Delta S)^{2}
$$  

Per time unit gains are then half of this,  

$$
\frac{1}{2}\frac{\partial^{2}C(S_{t},t)}{\partial S_{t}^{2}}(\Delta S)^{2}
$$  

These gains are only part of the potential cash inflows and outflows faced by the market maker. The position has further potential cash flows that need to be described. This is done in the next two sections.  

# 9.4.3 OTHER CASH FLOWS  

We just showed that oscillations in $S_{t}$ generate positive cash flows if the market maker delta hedges his or her long option position. Does this imply an arbitrage opportunity? After all, the market maker did not advance any cash yet seems to receive cash spontaneously as long as $S_{t}$ oscillates. The answer is no. There are costs to this strategy, and the delta-hedged option position is not riskless.  

1. The market maker funded his or her position with borrowed money. This means, that, as time passes, an interest cost is incurred. For a period of length $\Delta$ , this cost will equal  

$$
r C\Delta
$$  

under the constant spot rate assumption. (We write $C(t)$ , as $C.$ .)  

2. The option has time value, and as time passes, everything else being the same, the value of the option will decline at the rate  

$$
C_{t}=\frac{\partial C(S_{t},t)}{\partial t}
$$  

The option value will go down by  

$$
{\frac{\partial C(S_{t},t)}{\partial t}}\Delta
$$  

dollars, for each $\Delta$ that passes.  

3. Finally, the cash received from the short position generates $r S_{t}C_{s}\Delta$ dollars interest every time period $\Delta$ .  

The trading gains and the costs can be put together to obtain an important partial differential equation (PDE), which plays a central role in financial engineering.  

# 9.4.4 OPTION GAINS AND LOSSES AS A PDE  

We now add all gains and costs per unit of time $\Delta$ . The options’ gains per time unit from hedging adjustments are  

$$
\frac{1}{2}\frac{\partial^{2}C(S_{t},t)}{\partial S_{t}^{2}}(\Delta S)^{2}
$$  

In case the process $S_{t}$ is geometric, the annual percentage variance will be constant and this can be written as (see Appendix 9.2)  

$$
\frac{1}{2}C_{s s}\sigma^{2}S_{t}^{2}\Delta
$$  

The rest of the argument will continue with the assumption of a constant $\sigma$ .  

Interest is paid daily on the funds borrowed to purchase the call. For every period of length $\Delta$ , a long call holder will pay  

Another item is the interest earned from cash generated by shorting $C_{s}$ units of $S_{t}$ :1  

$$
r C_{s}S_{t}\Delta
$$  

Adding these, we obtain the net cash gains (losses) from the hedged long call position during $\Delta$ :  

$$
\frac{1}{2}C_{s s}\sigma^{2}S_{t}^{2}\Delta+r C_{s}S_{t}\Delta-r C\Delta
$$  

Now, in order for there to be no arbitrage opportunity, this must be equal to the daily loss of time value:  

$$
\frac{1}{2}C_{s s}\sigma^{2}S_{t}^{2}\Delta+r C_{s}S_{t}\Delta-r C\Delta=-C_{t}\Delta
$$  

We can eliminate the common $\Delta$ terms and obtain a very important relationship that some readers will recognize as the Black Scholes PDE:  

$$
\frac{1}{2}C_{s s}\sigma^{2}S_{t}^{2}+r C_{s}S_{t}-r C+C_{t}=0
$$  

Every PDE comes with some boundary conditions and this is no exception. The call option will expire at time $T$ , and the expiration $C(S_{T},T)$ is given by  

$$
C(S_{T},T)=\operatorname*{max}[S_{T}-K,0]
$$  

Solving this PDE gives the Black Scholes equation. In most finance texts, the PDE derived here is obtained from some mathematical derivation. In this section, we obtained the same PDE heuristically from practical trading and arbitrage arguments.  

# 9.4.5 CASH FLOWS AT EXPIRATION  

The cash flows at expiration date have three components: (i) the market maker has to pay the original loan if it is not paid off slowly over the life of the option, (ii) there is the final option settlement, and (iii) there is the final payoff from the short $S_{t}$ position.  

Now, at an infinitesimally short time period, $\mathrm{d}t$ , before expiration, the price of the underlying will be very close to $S_{T}$ Call it $S_{T}^{-}$ . The price curve $C(S_{t},t)$ will be very near the piecewise linear option payoff. Thus, the hedge ratio $h_{T}^{-}=C_{s}$ will be very close to either 0 or 1:  

$$
h_{T}^{-}\cong\left\{\begin{array}{l l}{{1}}&{{S_{T}^{-}>K}}\\ {{0}}&{{S_{T}^{-}<K}}\end{array}\right.
$$  

This means that, at time $T.$ , any potential gains from the long call option position will be equal to losses on the short $S_{t}$ position.  

The interesting question is, how does the market maker manage to pay back the original loan under these conditions? There is only one way. The only cash that is available is the accumulation of (net) trading gains from hedge adjustments during $[t,\ T]$ . As long as Eq. (9.44) is satisfied for every $t_{i}.$ , the hedged long option position will generate enough cash to pay back the loan. The option price, $C(t)$ , regarded this way is the discounted sum of all gains and losses from a deltahedged option position the trader will incur based on expected $S_{t}$ volatility.  

We will now consider a numerical example to our highly simplified discussion of how realized volatility is converted into cash via an option position.  

# 9.4.6 AN EXAMPLE  

Consider a stock, $S_{t},$ , trading at a price of 100. The stock pays no dividends and is known to have a Black Scholes volatility of $\sigma=45\%$ per annum. The risk-free interest rate is $4\%$ and $S_{t}$ is known to follow a geometric process, so that the Black Scholes assumptions are satisfied.  

A market maker buys 100 plain vanilla, ATM calls that expire in 5 days. The premium for one call is 2.13 dollars. This is the price found by plugging the above data into the Black Scholes formula. Hence, the total cash outlay is $\$213$ . There are no other fees or commissions. The market maker borrows the $\$213$ , buys the call options, and immediately hedges the long position by short selling an appropriate number of the underlying stock.  

# EXAMPLE  

Suppose that during these 5 days the underlying stock follows the path:  

$$
\{\mathrm{Day~1}=100,\mathrm{Day~2}=105,\mathrm{Day~3}=100,\mathrm{Day~4}=105,\mathrm{Day~5}=100\}
$$  

What are the cash flows, gains, and losses generated by this call option that remain on the market maker’s books?  

# 1. Day 1: The purchase date  

Current Delta: 51 (Found by differentiating the Black Scholes formula with respect to $S_{t},$ , plugging in the data and then multiplying by 100)   
Cash paid for the call options: $\$213$   
Amount borrowed to pay for the calls: $\$213$   
Amount generated by short selling 51 units of the stock: $\$5100$ . This amount is deposited at a rate of $4\%$ .  

# 2. Day 2: Price goes to 105  

Current Delta: 89 (Evaluated at $S_{t}=105,3$ days to expiration)   
Interest on amount borrowed: 213(0.04) $\textstyle\left({\frac{1}{360}}\right)=\$.02$   
Interest earned from deposit: 5100(0.04) $\textstyle\left({\frac{1}{360}}\right)=\$57$ (Assuming no bid ask difference in interest rates)   
Short selling 38 units of additional stock to reach delta neutrality which generate: 38 $(105)=\$3990$ .  

# 3. Day 3: Price goes back to 100  

Current Delta: 51   
Interest on amount borrowed: 213(0.04) $\begin{array}{r}{\left(\frac{1}{360}\right)=\mathbb{\S}0.02}\end{array}$   
Interest earned from deposits: $(5100+3990)(0.04)\left({\frac{1}{360}}\right)=\$1$   
Short covering 38 units of additional stock at 100 each, to reach delta neutrality generates a cash flow of: $38(5)=\$190$ . Interest on these profits is ignored to the first order of approximation.  

# 4. Day 4: Price goes to 105  

Current Delta: 98   
Interest on amount borrowed: 213(0.04) $\left(\frac{1}{360}\right)=\$0.02$   
Interest earned from deposits: 5100(0.04) $\textstyle\left({\frac{1}{360}}\right)=\$0.57$   
Shorting 47 units of additional stock at 105 each, to reach delta neutrality generates: $47(105)=\$4935$ .  

# 5. Day 5: Expiration with ${\cal S}_{T}=100$  

Net cash generated from covering the short position: $47(5)=\$235$ (There were 98 shorts, covered at $\$100$ each; 47 shorts were sold at $\$105$ , 51 shorts at $\$100$ )   
Interest on amount borrowed: 213(0.04) $\textstyle\left({\frac{1}{360}}\right)=\$0.02$   
Interest earned from deposits: $(5100+4935)$ (0.04) $\left(\frac{1}{360}\right)=\$1.1$ . The option expires ATM and generates no extra cash.  

# 6. Totals  

Total interest paid: $4(0.02)=\S0.08$   
Total interest earned: $2(0.57)+1+1.1=\S3.24$   
Total cash earned from hedging adjustments: $\$235+\$190$   
Cash needed to repay the loan: $\$213$   
Total net profit ignoring interest on interest $=\$215.16$   
A more exact calculation would take into account interest on interest earned and the interest earned on $\$190$ for 2 days.  

We can explain why total profit is positive. The path followed by $S_{t}$ in this example implies a daily actual volatility of $5\%$ . Yet, the option was sold at an annual implied volatility of $45\%$ , which corresponds to a “daily” percentage implied volatility of:  

$$
0.45\sqrt{\frac{1}{365}}=2.36\%
$$  

Hence, during the life of the option, $S_{t}$ fluctuated more than what the implied volatility suggested. As a result, the long convexity position had a net profit.  

This example is, of course, highly simplified. It keeps implied volatility constant and the oscillations occur around a fixed point. If these assumptions are relaxed, the calculations will change.  

# 9.4.6.1 Some caveats  

Three assumptions simplified notation and discussion in this section.  

First, we considered oscillations around a fixed ${\boldsymbol{S}}^{0}$ . In real life, oscillations will clearly occur around points that themselves move. As this happens, the partial derivatives, $C_{s}$ and $C_{s s}$ , will change in more complicated ways.   
Second, $C_{s}$ and $C_{s s}$ are also functions of time $t$ , and as time passes, this will be another source of change.   
The third point is more important. During the discussion, oscillations were kept constant at $\Delta S$ In real life, volatility may change over time and be random as well. This would not invalidate the essence of our argument concerning gains from hedge adjustments, but it will clearly introduce another risk that the market maker may have to hedge against. This risk is known as vega risk.   
Finally, it should be remembered that the underlying asset did not make any payouts during the life of the option. If dividends or coupons are paid, the calculation of cash gains and losses needs to be adjusted accordingly.  

These assumptions were made to emphasize the role of options as volatility instruments. Forthcoming chapters will deal with how to relax them.  

# 9.5 TOOLS FOR OPTIONS  

The Black Scholes PDE can be exploited to obtain the major tools available to an option trader or market maker. First of these is the Black Scholes formula, which gives the arbitrage-free price of a plain vanilla call (put) option under specific assumptions.  

The second set of tools is made up of the “Greeks.” These measure the sensitivity of an option’s price with respect to changes in various market parameters. The Greeks are essential in hedging and risk managing options books. They are also used in pricing and in options strategies.  

The third set of tools are ad hoc modifications of these theoretical constructs by market practitioners. These modifications adapt the theoretical tools to the real world, making them more “realistic.”  

# 9.5.1 SOLVING THE FUNDAMENTAL PDE  

The convexity of option payoffs implies an arbitrage argument, namely that the expected net gains (losses) from $\overline{{S_{t}}}$ oscillations are equal to time decay during the same period. This leads to the Black Scholes PDE:  

$$
\frac{1}{2}C_{s s}\sigma^{2}S_{t}^{2}+r C_{s}S_{t}-r C+C_{t}=0
$$  

# with the boundary condition  

$$
C(T)=\operatorname*{max}[S_{T}-K,0]
$$  

Now, under some conditions PDEs can be solved analytically and a closed-form formula can be obtained. See Duffie (2001). In our case, with specific assumptions concerning the dynamics of $S_{t},$ this PDE has such a closed-form solution. This solution is the market benchmark known as the Black Scholes formula.  

# 9.5.2 BLACK SCHOLES FORMULA  

An introduction to the Black Scholes formula first requires a good understanding of the underlying assumptions. Suppose we consider a plain vanilla call option written on a stock at time t. The option expires at time $T>t$ and has strike price $K$ . It is of European style and can be exercised only at expiration date $T.$ . Further, the underlying asset price and the related market environment denoted by $S_{t}$ have the following characteristics:  

1. The risk-free interest rate is constant at $r$ .   
2. The underlying stock price dynamics are described in continuous time by the stochastic differential equation (SDE):15  

$$
\mathrm{d}S_{t}=\mu(S_{t})S_{t}\mathrm{~d}t+\sigma S_{t}\mathrm{~d}W_{t}\quad t\in[0,\infty)
$$  

where $W_{t}$ represents a Wiener process with respect to real-world probability $P$ .16  

To emphasize an important aspect of the previous SDE, the dynamics of $S_{t}$ are assumed to have a constant percentage variance during infinitesimally short intervals. Yet, the drift component, $\mu(S_{t})S_{t}.$ , can be general and need not be specified further. Arbitrage arguments are used to eliminate $\mu(S_{t})$ and replace it with the risk-free instantaneous spot rate $r$ in the previous equation.  

3. The stock pays no dividends, and there are no stock splits or other corporate actions during the period $[t,T]$ .   
4. Finally, there are no transaction costs and no bid ask spreads.  

Under these assumptions, we can solve the PDE in Eqs. (9.49) and (9.51) and obtain the Black Scholes formula:  

$$
C(t)=S_{t}N(d_{1})-K e^{-r(T-t)}N(d_{2})
$$  

where $d_{1},d_{2}$ are  

$$
\begin{array}{l}{d_{1}=\frac{\log(S_{t}/K)+(r+(\sigma^{2}/2))(T-t)}{\sigma\sqrt{T-t}}}\\ {d_{2}=\frac{\log(S_{t}/K)+(r-(\sigma^{2}/2))(T-t)}{\sigma\sqrt{T-t}}}\end{array}
$$  

These increments are the continuous time equivalents of sequences of normally distributed variables. For a discussion of stochastic differential equations and the Wiener process, see, for example, Øksendal (2010). Hirsa and Neftci (2013) provides the heuristics.  

$N(x)$ denotes the cumulative standard normal probability:  

$$
N(x)=\int_{-\infty}^{x}\frac{1}{\sqrt{2\pi}}e^{-(1/2)u^{2}}\mathrm{d}u
$$  

In this formula, $r,\sigma,T_{\mathrm{{;}}}$ , and $K$ are considered parameters, since the formula holds in this version, only when these components are kept constant.17 The variables are $S_{t}$ and $t$ . The latter is allowed to change during the life of the option.  

Given this formula, we can take the partial derivatives of  

$$
C(t)=C(S_{t},t\mid r,\sigma,T,K)
$$  

with respect to the variables $S_{t}$ and $t$ and with respect to the parameters $r,\sigma,T_{\O}$ , and $K$ . These partials are the Greeks. They represent the sensitivities of the option price with respect to a small variation in the parameters and variables. Implied volatility $(\sigma_{\mathrm{IV}})$ is calculated by backing out the $\sigma$ that gives the observed option price $C(t)$ if one was to plug it into the pricing formula (9.52) together with the other input parameters such as $r,T,K,S_{t},$ and $t.$ . Since the implied volatility is implied by the observed market price of the option, its calculation is similar to that of the yield to maturity for bonds which is calculated based on the market price of the bonds, a pricing formula and other input parameters such as maturity and frequency of cash flow payments.  

# 9.5.2.1 Black’s formula  

The Black Scholes formula in Eq. (9.52) is the solution to the fundamental PDE when delta hedging is done with the “cash” underlying. As discussed earlier, trading gains and funding costs lead to the PDE:  

$$
r C_{s}S_{t}-r C+\frac{1}{2}C_{s s}\sigma^{2}S_{t}^{2}=-C_{t}
$$  

with the boundary condition:  

$$
C(S_{T},T)=\operatorname*{max}[S_{T}-K,0]
$$  

When the underlying becomes a forward contract, $S_{t}$ will become the corresponding forward price denoted by $F_{t}$ and the BlackScholes PDE will change slightly.  

Unlike a cash underlying, buying and selling a forward contract does not involve funding. Long and short forward positions are commitments to buy and sell at a future date $T.$ , rather than outright purchases of the underlying asset. Thus, the only cash movements will be interest expense for funding the call, and cash gains from hedge adjustments. This means that the corresponding PDE will look like  

$$
-r C+\frac{1}{2}C_{s s}\sigma^{2}F_{t}^{2}=-C t
$$  

with the same boundary condition:  

$$
C(F_{T},T)=\operatorname*{max}[F_{T}-K,0]
$$  

where $F_{t}$ is now the forward price of the underlying.  

The solution to this PDE is given by the so-called Black’s formula in the case where the options are of European style.  

$$
C(F_{t},t)^{\mathrm{Black}}=e^{-r(T-t)}[F_{t}N(d_{1})-K N(d_{2})]
$$  

with  

$$
d_{1}^{\mathrm{Black}}=\frac{\log(F_{t}/K)+(1/2)\sigma^{2}(T-t)}{\sigma\sqrt{(T-t)}}
$$  

$$
d_{2}^{\mathrm{Black}}=d_{1}^{\mathrm{Black}}-\sigma\sqrt{(T-t)}
$$  

Black’s formula is useful in many practical circumstances where the Black Scholes formula cannot be applied directly. Interest rate derivatives such as caps and floors, for example, are options written on LIBOR rates that will be observed at future dates. Such settings lend themselves better to the use of Black’s formula. The underlying risk is a forward interest rate such as forward LIBOR, and the related option prices are given by Black’s formula. However, the reader should remember that in the preceding version of Black’s formula the spot rate is taken as constant. In Chapter 16, this assumption will be relaxed.  

# 9.5.3 OTHER FORMULAS  

The Black Scholes type PDEs can be solved for a closed-form formula under somewhat different conditions as well. These operations result in expressions that are similar but contain further parameters and variables. We consider two cases of interest. Our first example is a chooser option.  

# 9.5.3.1 Chooser options  

Consider a vanilla put, $P\left(t\right)$ and a vanilla call, $C\left(t\right)$ written on $S_{t}$ with strike $K$ , and expiration $T.$ A chooser option then is an option that gives the right to choose between $C(t)$ and $P(t)$ at some later date $T_{0}$ . Its payoff at time $T_{0}$ , with $T_{0}<T$ is  

$$
C^{h}(T_{0})=\operatorname*{max}\left[C\big(S_{T_{0}},T_{0}\big),P\big(S_{T_{0}},T_{0}\big)\right]
$$  

Arbitrage arguments lead to the equality  

$$
P\big(S_{T_{0}},T_{0}\big)=-\big(S_{T_{0}}-K e^{-r(T-T_{0})}\big)+C\big(S_{T_{0}},T_{0}\big)
$$  

Using this, Equation (9.64) can be written as  

$$
C^{h}(T_{0})=\operatorname*{max}\left[C\big(S_{T_{0}},T_{0}\big),-\big(S_{T_{0}}-K e^{-r(T-T_{0})}\big)+C\big(S_{T_{0}},T_{0}\big)\right]
$$  

or, taking the common term out,  

$$
C^{h}(T_{0})=C\big(S_{T_{0}},T_{0}\big)+\operatorname*{max}\big[-\big(S_{T_{0}}-K e^{-r(T-T_{0})}\big),0\big]
$$  

In other words, the chooser option payoff is either equal to the value of the call at time $T_{0}$ , or it is that plus a positive increment, in the case that  

$$
\left(S_{T_{0}}-K e^{-r(T-T_{0})}\right)<0
$$  

But, this is equal to the payoff of a put with strike price $K e^{-r(T-T_{0})}$ and exercise date $T_{0}$ . Thus, the pricing formula for the chooser option is given by  

$$
C^{h}(t)=[S_{t}N(d_{1})-K e^{-r(T-t)}N(d_{2})]+[-S_{t}N(-\overline{{d}}_{1})+K e^{-r(T-T_{0})}e^{-r(T_{0}-t)}N(-\overline{{d}}_{2})]
$$  

Simplifying:  

$$
C^{h}(t)=[S_{t}(N(d_{1})-N(-\overline{{d}}_{1}))]+K e^{-r(T-t)}(N(-\overline{{d}}_{2})-N(d_{2}))
$$  

with  

$$
d_{1,2}=\frac{\ln(S_{t}/K)+(r\pm(1/2)\sigma^{2})(T-t)}{\sigma\sqrt{T-t}}
$$  

$$
\overline{{d}}_{1,2}=\frac{\ln(S_{t}/K)+(r(T-t)\pm(1/2)\sigma^{2}(T_{0}-t))}{\sigma\sqrt{(T_{0}-t)}}
$$  

A more interesting example from our point of view is the application of the Black Scholes approach to barrier options, which we consider next.  

# 9.5.3.2 Barrier options  

Barrier options will be treated in detail in the next chapter. Here we just define these instruments and explain the closed-form formula that is associated with them under some simplifying assumptions. This will close the discussion of the application spectrum of Black Scholes type formulas.  

Consider a European vanilla call, written on $S_{t}$ , with strike $K$ and expiration $T_{\mathbf{\delta}}$ , $t<T.$ . Assume that $S_{t}$ satisfies all Black Scholes assumptions. Consider a barrier $H$ , and assume that $H<S_{t}<K$ as of time t. Suppose we write a contract stipulating that if, during the life of the contract, $[t,T],S_{t}$ falls below the level $H_{;}$ the option disappears and the option writer will have no further obligation. In other words, as long as $H<S_{u},$ , $u\in[t,~T]$ , the vanilla option is in effect, but as soon as $S_{u}$ falls below $H.$ the option dies. This is a barrier option—specifically a down-and-out barrier. Two examples are shown in Figure 9.8a.  

The pricing formula for the down-and-out call is given by  

$$
\begin{array}{r l}{C^{b}(t)}&{{}=C(t)-J(t)\quad{\mathrm{for~}}H\leq S_{t}}\\ {C^{b}(t)}&{{}=0\quad{\mathrm{for~}}S_{t}<H}\end{array}
$$  

Here $C(t)$ is the value of the vanilla call, which is given by the standard Black Scholes formula, and where $J(t)$ is the discount that needs to be applied because the option may die if $S_{t}$ falls below $H$ during $[t,T]$ . See Figure 9.8b. The formula for $J(t)$ is  

$$
J(t)=S_{t}\left(\frac{H}{S_{t}}\right)^{(2(r-(1/2)\sigma^{2})/\sigma^{2})+2}N(c_{1})-K e^{-r(T-t)}\left(\frac{H}{S_{t}}\right)^{(2(r-\frac{1}{2}\sigma^{2}))/\sigma^{2}}N(c_{2})
$$  

where  

$$
c_{1,2}=\frac{\log(H^{2}/S_{t}K)+(r\pm(1/2)\sigma^{2})(T-t)}{\sigma\sqrt{T-t}}
$$  

It is interesting to note that when $S_{t}$ touches the barrier  

$$
S_{t}=H
$$  

![](8ad4d48fb6135cf90b8031cb664112d67275e8f656fcf6b3a6949235d110eee8.jpg)  

# FIGURE 9.8  

(a) Barrier option example. (b) Vanilla call and knock-in call.  

the formula for $J(t)$ becomes  

$$
J(t)=S_{t}N(d_{1})-K e^{-r(T-t)}N(d_{2})
$$  

That is to say, the value of $C^{b}(t)$ is zero:  

$$
C^{b}(t)=C(t)-C(t)
$$  

This characterization of a barrier option as a standard option plus or minus a discount term is very useful from a financial engineering angle. In the next chapter, we will obtain some simple contractual equations for barriers, and the use of discounts will then be useful for obtaining Black Scholes type formulas for other types of barriers.  

![](6b4698de01833741692429b2be79aa3c701fae9750557383ae934f562afa8ff5.jpg)  

# FIGURE 9.8  

(Continued)  

# 9.5.4 USES OF BLACK SCHOLES TYPE FORMULAS  

Obviously, the assumptions underlying the derivation of the Black Scholes formula are quite restrictive. This becomes especially clear from the way we introduced options in this book. In particular, if options are used to bet on the direction of volatility, then how can the assumption of constant percentage volatility possibly be satisfied? This issue will be discussed further in later chapters where the way market professionals use the Black Scholes formula while trading volatility is clarified.  

When the underlying asset is an interest rate instrument or a foreign currency, some of the Black Scholes assumptions become untenable.18 Yet, when these assumptions are relaxed, the logic used in deriving the Black Scholes formula may not result in a PDE that can be solved for a closed-form formula.  

Hence, a market practitioner may want to use the Black Scholes formula or variants of it, and then adjust the formula in some ad hoc, yet practical, ways. This may be preferable to trying to derive new complicated formulas that may accommodate more realistic assumptions. Also, even though the BlackScholes formula does not hold when the underlying assumptions change, acting as if the assumptions hold yields results that are surprisingly robust.19 We will see that this is exactly what happens when traders adjust the volatility parameter depending on the “moneyness” of the option under consideration.  

This completes our brief discussion of the first set of tools that are essential for option analysis, namely Black Scholes type closed-form formulas that give the arbitrage-free price of an option under some stringent conditions. Next, we discuss the second set of tools that traders and market makers routinely use: various sensitivity factors called the “Greeks.”  

# 9.6 THE GREEKS AND THEIR USES  

The Black Scholes formula gives the value of a vanilla call (put) option under some specific assumptions. Obviously, this is useful for calculating the arbitrage-free value of an option. But a financial engineer needs methods for determining how the option premium, $C(t)$ , changes as the variables or the parameters in the formula change within the market environment. This is important since the assumptions used in deriving the Black Scholes formula are unrealistic. Traders, market makers, or risk managers must constantly monitor the sensitivity of their option books with respect to changes in $S_{t},r,t$ , or $\sigma$ . The role of Greeks should be well understood.  

# EXAMPLE  

A change in $\sigma$ is a good example. We motivated option positions essentially (but not fully) as positions taken on volatility. It is clear that volatility is not constant as assumed in the Black Scholes world. Once an option is bought and delta-hedged, the hedge ratio $C_{\mathrm{s}}$ and the $C_{\mathrm{ss}}$ both depend on the movements in the volatility parameter $\sigma$ .  

Hence, the “hedged” option position will still be risky in many ways. For example, depending on the way changes in $\sigma$ and $S_{t}$ affect the $C_{s s}$ , a market maker may be correct in his or her forecast of how much $S_{t}$ will fluctuate, yet may still lose money on a long option position.  

A further difficulty is that option sensitivities may not be uniform across the strike price $K$ or expiration $T.$ For options written on the same underlying, differences in $K$ and $T$ lead to what are called smile effects and term structure effects, respectively, and should be taken into account carefully.  

Option sensitivity parameters are called the “Greeks” in the options literature. We discuss them next and provide several practical examples.  

# 9.6.1 DELTA  

Consider the Black Scholes formula $C\left(S_{t},t\mid r,\sigma,T,K\right)$ . How much would this theoretical price change if the underlying asset price, $S_{t},$ moved by an infinitesimal amount?  

One theoretical answer to this question can be given by using the partial derivative of the function with respect to $S_{t}$ . This is by definition the delta at time $t\mathbf{\cdot}$ :  

$$
{\mathrm{delta}}={\frac{{\hat{\sigma}}C(S_{t},t\mid r,\sigma,T,K}{{\hat{\sigma}}S_{t}}}
$$  

This partial derivative was denoted by $C_{s}$ earlier. Note that delta is the local sensitivity of the option price to an infinitesimal change in $S_{t}$ only, which incidentally is the reason behind using partial derivative notation.  

To get some intuition on this, remember that the price curve for a long call has an upward slope in the standard $C(t)$ , $S_{t}$ space. Being the slope of the tangent to this curve, the delta of a long call (put) is always positive (negative). The situation is represented in Figure 9.9. Here, we consider three outcomes for the underlying asset price represented by $S_{A},S_{B}$ , and $S_{C}$ and hence obtain three points, $A,B$ , and $C$ , on the option pricing curve. At each point, we can draw a tangent. The slope of this tangent corresponds to the delta at the respective price.  

At point $C$ , the slope, and hence, the delta is close to 0, since the curve is approaching the horizontal axis as $S_{t}$ falls. At point $B$ , the delta is close to 1, since the curve is approaching a line with slope $+1$ . At point $A$ , the delta is in the “middle,” and the slope of the tangent is between 0 and 1.  

![](82f764022106695086e975e1324c091806c44e60fb0c32b0d40932a57b1b5e0c.jpg)  

# FIGURE 9.9  

Payoff of a long call position and slope.  

Thus, we always have $0<d e l t a<1$ in case of a long call position. As mentioned earlier, when the option is ATM, the delta is close to 0.5.  

# 9.6.1.1 Convention  

Market professionals do not like to use decimal points. The convention in option markets is to think about trading, not one, but 100 options, so that the delta of option positions can be referred to in whole numbers, between 0 and 100. According to this convention, the delta of an ATM option is around 50. A 25-delta option would be out-of-the-money and a 75-delta option in-the-money. Especially in FX markets, traders use this terminology to trade options.  

Under these conditions, an options trader may evaluate his or her exposure using delta points. A trader may be long delta, which means that the position gains if the underlying increases, and loses if the underlying decreases. A short delta position implies the opposite.  

# 9.6.1.2 The exact expression  

The partial derivative in Eq. (9.79) can be taken in case the call option is European and the price is given by the Black Scholes formula. Doing so, we obtain the delta of this important special case:  

$$
\frac{\hat{\sigma}C(S_{t},t\mid r,\sigma,T,K)}{\hat{\sigma}S_{t}}=\int_{-\infty}^{\frac{(T-t)(r+(1/2)\sigma^{2})+\log(S_{t}/K)}{\sqrt{(T-t)\sigma}}}\frac{1}{\sqrt{2\pi}}e^{-(1/2)x^{2}}\mathrm{d}x
$$  

This derivation is summarized in Appendix 9.1. It is shown that the delta is itself a function that depends on the “variables” $S_{t},K,r,\sigma$ , and on the remaining life of the option, $T-t.$ . This function is in the form of a probability. The delta is between 0 and 1, and the function will have the familiar $S$ -shape of a continuous cumulative distribution function (CDF). This, incidentally, means that the derivative of the delta with respect to $S_{t}$ , which is called gamma, will have the shape of a probability density function (PDF).20 A typical delta will thus look like the S-shaped curve shown in Figure 9.10.  

We can also see from this formula how various movements in market variables will affect this particular option sensitivity. The formula shows that whatever increases the ratio  

$$
\frac{\log(S_{t}/K)+(r+(1/2)\sigma^{2})(T-t)}{\sigma\sqrt{T-t}}
$$  

will increase the delta; whatever decreases this ratio, will decrease the delta.  

For example, it is clear that as $r$ increases, the delta will increase. On the other hand, a decreas in the moneyness of the call option, defined as the ratio  

$$
\frac{S_{t}}{K}
$$  

decreases the delta. The effect of volatility changes is more ambiguous and depends on the moneyness of the option.  

![](ef3af7c772b41c2cf78e196bb4d36ef0349b217803bd8fbfc4876f6032a6367f.jpg)  

# FIGURE 9.10  

Delta of a long call position based on Black Scholes formula.  

# EXAMPLE  

We calculate the delta for some specific options. We first assume the Black Scholes world, even though the relevant market we are operating in may violate many of the Black Scholes assumptions. This assumes, for example, that the dividend yield of the underlying is zero and this assumption may not be satisfied in real-life cases. Second, we differentiate the function $C(t)$  

$$
C(t)=S_{t}N(d_{1})-K e^{-r(T-t)}N(d_{2})
$$  

where $d_{1}$ and $d_{2}$ are as given in Eqs. (9.53) and (9.54), with respect to $S_{t}$ . Then, we substitute values observed for $S_{t},K,r,\sigma,(T-t)$ .  

Suppose the Microsoft December calls and puts shown in the table from our first example in this chapter satisfy these assumptions. The deltas can be calculated based on the following parameter values:  

$$
S_{t}=61.15,r=0.025,\sigma=30.7\%,T-t=58/365
$$  

Here, $\sigma$ is the implied volatility obtained by solving the equation for $K=60$ ,  

$$
C(61.115,60,0.025,58/365,\sigma)=\mathrm{Observedprice}
$$  

Plugging the observed data into the formula for delta yields the following values:  

<html><body><table><tr><td>Calls</td><td>Delta</td></tr><tr><td>Dec 55.00</td><td>0.82</td></tr><tr><td>Dec60.00</td><td>0.59</td></tr><tr><td>Dec65.00</td><td>0.34</td></tr><tr><td>Dec70.00 0.16</td><td></td></tr></table></body></html>  

<html><body><table><tr><td>Puts</td><td> Delta</td></tr><tr><td>Dec 55.00 -0.17</td><td></td></tr><tr><td>Dec 60.00 -0.40</td><td></td></tr><tr><td>Dec 65.00</td><td>-0.65</td></tr><tr><td>Dec 70.00 -0.84</td><td></td></tr></table></body></html>  

We can make some interesting observations:  

1. The ATM calls and puts have the same price.   
2. Their deltas, however, are different.   
3. The calls and puts that are equally far from the ATM have slightly different deltas in absolute value. According to the last point, if we consider 25-delta calls and puts, they will not be exactly the same.21  

We now point out to some questionable assumptions used in our example. First, in calculating the deltas for various strikes, we always used the same volatility parameter $\sigma$ . This is not a trivial point. Options that are identical in every other aspect, except for their strike $K,$ , may have different implied volatilities. There may be a volatility smile. Using the ATM implied volatility in calculating the delta of all options may not be the correct procedure. Second, we assumed a zero dividend yield, which is not realistic either. Normally, stocks have positive expected dividend yields and some correction for this should be made when option prices and the relevant Greeks are calculated. A rough way of doing it is to calculate an annual expected percentage dividend yield and subtract it from the risk-free rate $r.$ . Third, should we use $S_{t}$ or a futures market equivalent, in case this latter exists, the delta evaluated in the futures or forward price may be more desirable.  

# 9.6.2 GAMMA  

Gamma represents the rate of change of the delta as the underlying risk $S_{t}$ changes. Changes in delta were seen to play a fundamental role in determining the price of a vanilla option. Hence,  

![](660b78aca5e843bad7f55e14f8af32c49b97d0d207b8abe20152fc5a1512d263.jpg)  

# FIGURE 9.11  

Gamma of a long call position based on Black Scholes formula.  

gamma is another important Greek. It is given by the second partial derivative of $C(S_{t},\ t)$ with respect to $S_{t}$ :  

$$
{\mathrm{gamma}}={\frac{{\hat{\sigma}}^{2}C(S_{t},t\mid r,\sigma,T,K}{{\hat{\sigma}}S_{t}^{2}}}
$$  

We can easily obtain the exact expression for gamma in the case of a European call. The derivation in Appendix 9.1 gives  

$$
\frac{\hat{\sigma}^{2}C(S_{t},t\mid r,\sigma,T,K}{\hat{\sigma}S_{t}^{2}}=\frac{1}{S_{t}\sigma\sqrt{T-t}}\left[\frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}\left(\frac{\log(S/k)+r(T-t)+\frac{1}{2}\sigma^{2}(T-t)}{\sigma\sqrt{T-t}}\right)^{2}}{\mathrm{d}{u}}\right]
$$  

Gamma shows how much the delta hedge should be adjusted as $S_{t}$ changes. Figure 9.11 illustrates the gamma for the Black Scholes formula. We see the already-mentioned property. Gamma is highest if the option is ATM, and approaches zero as the option becomes deep in-the-money or out-of-the-money.  

We can gain some intuition on the shape of the gamma curve. First, remember that gamma is, in fact, the derivative of delta with respect to $S_{t}$ . Second, remember that delta itself had the shape of a cumulative normal distribution. This means that the shape of gamma will be similar to that of a continuous, bell-shaped PDF, as expression (9.87) indicates.  

Consider now a numerical example dealing with gamma calculations. We use the same data uti lized earlier in the chapter.  

# EXAMPLE  

To calculate the gamma, we use the same table as in the first example in the chapter. We take the partial derivative of the delta with respect to $S_{t}$ . This gives a new function $S_{t},K,r,$ $\sigma$ , $(T-1)$ , which measures the sensitivity of delta to the underlying $S_{t}$ . We then substitute the observed values for $S_{t},K,r,\sigma,(T-t)$ to obtain gamma at that particular point.  

For the Microsoft December calls and puts shown in the table, gammas are calculated based on the parameter values  

$$
S_{t}=60.0,r=0.025,\sigma=31\%,T-t=58/365,k=60
$$  

where $\sigma$ is the implicit volatility.  

Again we are using the implicit volatility that corresponds to the ATM option in calculating the delta of all options, in-the-money or out.  

Plugging the observed data into the formula for gamma yields the following values:  

<html><body><table><tr><td>Calls</td><td>Gamma</td></tr><tr><td>Dec 55.00</td><td>0.034</td></tr><tr><td>Dec 60.00</td><td>0.053</td></tr><tr><td>Dec 65.00</td><td>0.050</td></tr><tr><td>Dec 70.00</td><td>0.032</td></tr></table></body></html>  

<html><body><table><tr><td>Puts</td><td>Gamma</td></tr><tr><td>Dec 55.00</td><td>0.034</td></tr><tr><td>Dec 60.00</td><td>0.053</td></tr><tr><td>Dec 65.00</td><td>0.050</td></tr><tr><td>Dec 70.00</td><td>0.032</td></tr></table></body></html>  

The following observations can be made:  

1. The puts and calls with different distance to the ATM strike have gammas that are alike but not exactly symmetric.  

2. Gamma is positive if the market maker is long the option; otherwise it is negative.  

It is also clear from this table that gamma is highest when we are dealing with an ATM option.  

Finally, we should mention that as time passes, the second-order curvature of ATM options will increase as the gamma function becomes more peaked and its tails go toward zero.  

# 9.6.2.1 Market use  

We must comment on the role played by gamma in option trading. We have seen that long delta exposures can be hedged by going short using the underlying asset. But, how are gamma exposures  

hedged? Traders sometimes find this quite difficult. Especially in very short-dated, deep out-of-themoney options, gamma can suddenly go from zero to very high values and may cause significant losses (or gains).  

# EXAMPLE  

The forex option market was caught short gamma in GBP/EUR last week. The spot rate surged from GBP0.6742 to GBP0.6973 late the previous week, 1-month volatilities went up from about $9.6\%$ to roughly $I3.3\%$ . This move forced players to cover their gamma.  

(A typical market quote)  

This example shows one way delta and gamma are used by market professionals. Especially in the foreign exchange markets, options of varying moneyness characteristics are labeled according to their delta. For example, consider 25-delta Sterling puts. Given that an ATM put has a delta of around 50, these puts are out-of-the-money. Market makers had sold such options and, after hedging their delta exposure, were holding short gamma positions. This meant that as the Sterling Euro exchange rate fluctuated, hedge adjustments led to higher than expected cash outflows.  

# 9.6.3 VEGA  

A critical Greek is the vega. How much will the value of an option change if the volatility parameter, $\sigma$ , moves by an infinitesimal amount? This question relates to an option’s sensitivity with respect to implied volatility movements. Vega is obtained by taking the partial derivative of the function with respect to $\sigma$ :  

$$
\mathrm{\vega}=\frac{\hat{\sigma}C(S_{t},t\mid r,\sigma,T,K}{\hat{\sigma}\sigma}
$$  

An example of vega is shown in Figure 9.12 for a call option. Note the resemblance to the gamma displayed earlier in Figure 9.11. According to this figure, the vega is greatest when the option is ATM. This implies that if we use the ATM option as a vehicle to benefit from oscillations in $S_{t},$ , we will also have maximum exposure to movements in the implied volatility. We consider some examples of vega calculations using actual data.  

# EXAMPLE  

Vega is the sensitivity with respect to the percentage volatility parameter, $\sigma$ , of the option. According to the convention, this is calculated using the Black Scholes formula. We differentiate the formula with respect to the volatility parameter $\sigma$ .  

Doing this and then substituting  

$$
C(61.15,0.025,60,58/365,\sigma)=\mathrm{Observed}\mathrm{price}
$$  

we get a measure of how this option’s prices will react to small changes in $\sigma$ .  

For the table above, we get the following results:  

<html><body><table><tr><td>Calls</td><td>Vega($)</td></tr><tr><td>Dec 55.00</td><td>6.02</td></tr><tr><td>Dec 60.00</td><td>9.4</td></tr><tr><td>Dec 65.00</td><td>8.9</td></tr><tr><td>Dec 70.00</td><td>5.6</td></tr></table></body></html>  

<html><body><table><tr><td>Puts</td><td>Vega($)</td></tr><tr><td>Dec 55.00</td><td>6.02</td></tr><tr><td>Dec 60.00</td><td>9.4</td></tr><tr><td>Dec 65.00</td><td>8.9</td></tr><tr><td>Dec 70.00</td><td>5.6</td></tr></table></body></html>  

We can make the following comments:  

1. ATM options have the largest values of vega. 2. As implied volatility increases, the ATM vega changes marginally, whereas the out-ofthe-money and in-the-money option vegas do change, and in the same direction.  

![](4bbbbd2e89f6d2a3698de352129e234fd889e6eea873397e25605ae7b8a32387.jpg)  

# FIGURE 9.12  

Vega of a long call position based on Black Scholes formula.  

Option traders can use the vega in calculating the “new” option price in case implied volatilities change by some projected amount. For example, in the preceding example, if the implied volatility increases by 2 percentage points, then the value of the Dec 60-put will increase approximately by 0.19, everything else being the same.  

# 9.6.3.1 Market use  

Vega is an important Greek because it permits market professionals to keep track of their exposure to changes in implied volatility. This is important, since the Black Scholes formula is derived in a framework where volatility is assumed to be constant, yet used in an environment where the volatility parameter, $\sigma$ , changes. Market makers often quote the $\sigma$ directly, instead of quoting the Black Scholes value of the option. Under these conditions, vega can be used to track exposure of option books to changes in $\sigma$ . This can be followed by vega hedging.  

The following reading is one example of the use of vega by the traders.  

# EXAMPLE  

Players dumped USD/JPY vol last week in a quiet spot market, causing volatilities to go down further. One player was selling USD1 billion in six-month dollar/yen options in the market. These trades were entered to hedge vega exposure. The drop in the vols forced market makers to hedge exotic trades they had previously sold.  

According to this reading, some practitioners were long volatility. They had bought options when the dollar yen exchange rate volatility was higher. They faced vega risk. If implied volatility declined, their position would lose value at a rate depending on the position’s vega. To cover these risky positions, they sold volatility and caused further declines in this latter. The size of vega is useful in determining such risks faced by such long or short volatility positions.  

# 9.6.3.2 Vega hedging  

Vega is the response of the option value to a change in implied volatility. In a liquid market, option traders quote implied volatility and this latter continuously fluctuates. This means that the value of an existing option position also changes as implied volatility changes. Traders who would like to eliminate this exposure use vega hedging in making their portfolio vega-neutral. Vega hedging in practice involves buying and selling options, since only these instruments have convexity and hence, have vega.  

# 9.6.4 THETA  

Next, we ask how much the theoretical price of an option would change if a small amount of time, dt, passes. We use the partial derivative of the function with respect to time parameter $t$ , which is called theta:  

$$
{\mathrm{theta}}={\frac{{\hat{\sigma}}C(S_{t},t\mid r,\sigma,T,K}{{\hat{\sigma}}t}}
$$  

![](d2bbfb7bac4427eacc7dfbf2c187ae7e2b94d6f628d13f3cd4104638813f980d.jpg)  

# FIGURE 9.13  

Theta of a long call position based on Black Scholes formula.  

According to this, theta measures the decay in the time value of the option. The intuition behind theta is simple. As time passes, one has less time to gain from future $S_{t}$ oscillations. Option’s time value decreases. Thus, we must have theta $<0$ .  

If the Black Scholes assumptions are correct, we can calculate this derivative analytically and plot it. The derivative is represented in Figure 9.13. We see that, all else being the same, a plain vanilla option’s time value will decrease at a faster rate as expiration approaches.  

# 9.6.5 OMEGA  

This Greek relates to American options only and is an approximate measure developed by market professionals to measure the expected life of an American-style option.  

# 9.6.6 HIGHER-ORDER DERIVATIVES  

The Greeks seen thus far are not the only sensitivities of interest. One can imagine many other sensitivities that are important to market professionals and investors. In fact, we can calculate the sensitivity of the previously mentioned Greeks themselves with respect to $S_{t},~\sigma,~t.$ , and $r$ . These are higher-order cross partial derivatives and under some circumstances will be quite relevant to the trader.  

Two examples are as follows. Consider the gamma of an option. This Greek determines how much cash can be earned as the underlying $S_{t}$ oscillates. But the value of the gamma depends on the $S_{t}$ and $\sigma$ as well. Thus, a gamma trader may be quite interested in the following sensitivities:  

$$
\begin{array}{r l}{\frac{\partial\mathrm{gamma}}{\partial S_{t}}}&{{}\frac{\partial\mathrm{gamma}}{\partial\sigma}}\end{array}
$$  

These two Greeks are sometimes referred to as the speed and zomma, respectively.22 It is obvious that the magnitude of these partials will be useful in determining the risks and gains of gamma positions. Exotic option deltas and gammas may have discontinuities, and such high-order moments may be very relevant.  

Another interesting Greek is the derivative of vega with respect to $S_{t}$ :  

$$
\begin{array}{l}{\displaystyle\frac{\hat{\sigma}\mathrm{vega}}{\hat{\sigma}S_{t}}}\\ {\displaystyle\frac{\hat{\sigma}\mathrm{vega}}{\hat{\sigma}\sigma}=\mathrm{volga}}\end{array}
$$  

This derivative is of interest to a vega trader. In a sense, this is volatility gamma, hence the name. Similarly, the partial derivative of all important Greeks with respect to a small change in time parameter may provide information about the way the Greeks move over time.  

# 9.6.7 GREEKS AND PDEs  

The fundamental Black Scholes PDE that we derived in this chapter can be reinterpreted using the Greeks just defined. In fact, we can plug the Greeks into the Black Scholes PDE  

$$
\frac{1}{2}C_{s s}\sigma^{2}S_{t}^{2}+r C_{s}S_{t}-r C+C_{t}=0
$$  

and recast it as  

$$
\frac{1}{2}\mathrm{gamma}\sigma^{2}S_{t}^{2}+r\mathrm{delta}S_{t}-r C+\mathrm{theta}=0
$$  

In this interpretation, being long in options means, “earning” gamma and “paying” theta.  

It is also worth noting that the higher-order Greeks mentioned in Eqs. (9.92) and (9.93) are not present in Eq. (9.95). This is because they are second-order Greeks. The first-order Greeks are related to changes in the underlying risk $\Delta S_{t},\Delta\sigma$ , or time $\Delta$ , whereas the higher-order Greeks would relate to changes that will have sizes given by the products $(\Delta S_{t}\Delta\sigma)$ or $(\Delta\sigma\Delta)$ . In fact, when $\Delta S_{t},\Delta\sigma,\Delta$ are “small” but non-negligible, products of two small numbers such as $(\Delta S_{t}\Delta\sigma)$ are even smaller and negligible, depending on the sizes of incremental changes in $S_{t}.$ , or volatility.23  

In some real-life applications, when volatility “spikes,” higher-order Greeks may become relevant. Yet, in theoretical models with standard assumptions, where $\Delta\to0$ , they fall from the overall picture, and do not contribute to the PDE in Eq. (9.94).  

# 9.6.7.1 Gamma trading  

The Black Scholes PDE can be used to explain what a gamma trader intends to accomplish. Assume that the real-life gamma is correctly calculated by choosing a formula for $C(S_{t},t\mid r,K,\sigma,$ $T_{\mathbf{\delta}}$ ) and then taking the derivative:  

$$
\mathrm{\gamma}=\frac{\partial^{2}C(S_{t},t\mid r,K,\sigma,T}{\partial S_{t}^{2}}
$$  

Following the logic that led to the Black Scholes PDE in Eq. (9.94), a gamma trader would, first, form a subjective view on the size of expected changes in the underlying using some subjective probability $P^{*}$ , as of time $t_{0}<t$ . The gains can be written as,2  

$$
\boxed{E_{t_{0}}^{P*}\bigg[\frac{1}{2}\mathrm{gamma}(\Delta S_{t})^{2}\bigg]}
$$  

This term would be greater, the greater the oscillations in $S_{t}$ . Then these gains will be compared with interest expenses and the loss of time value. If the expected gamma gains are greater than these costs, then the gamma trader will go long gamma. If, in contrast, the costs are greater, the gamma trader will prefer to be short gamma.  

There are at least two important comments that need to be made about trading gammas.  

# 9.6.7.2 Gamma trading versus Vega  

First of all, the gamma of an option position depends on the implied volatility parameter $\sigma$ . This parameter represents implied volatility. It need not have the same value as the (percentage) oscillations anticipated by a gamma trader. In fact, a gamma trader’s subjective (expected) gains, due to $S_{t}$ oscillations, are given by  

$$
E_{t_{0}}^{p*}\bigg[\frac{1}{2}\mathrm{gamma}(\Delta S_{t})^{2}\bigg]
$$  

There is no guarantee that the implied volatility parameter will satisfy the equality  

$$
\sigma^{2}S_{t}^{2}\Delta E_{t_{0}}[\mathrm{gamma}]=E_{t_{0}}^{P_{*}}[\mathrm{gamma}(\Delta S_{t})^{2}]
$$  

This is even if the trader is correct in his or her anticipation. The right-hand side of this expression represents the anticipated (percentage) oscillations in the underlying asset that depend on a subjective probability distribution, whereas the left-hand side is the volatility value that is plugged into the Black Scholes formula to get the option’s fair price.  

Thus, a gamma trader’s gains and losses also depend on the implied volatility movements, and the option’s vega will be a factor here. For example, a gamma trader may be right about increased real-world oscillations, but, may still lose money if implied volatility, $\sigma$ , falls simultaneously. This will lower the value of the position if  

$$
\frac{\partial C_{s s}}{\partial\sigma}<0
$$  

The following reading illustrates the approaches a trader or risk manager may adopt with respect to vega and gamma risks.  

# EXAMPLE  

The VOLX contracts, (one) the new futures based on the price volatility of three reference markets measured   
by the closing levels of the benchmark cash index. The three are the German (DAX), UK (FT-SE), and   
Swedish (OMX) markets. The designers argue that VOLX products, by creating a term structure of volatility that is arbitrageable,   
offer numerous hedging and trading possibilities. This covers both vega and gamma exposures and also   
takes in the long-dated options positions that are traditionally very difficult to hedge with short options. Simply put, option managers who have net short positions and therefore are exposed to increases in   
volatility, can hedge those positions by being long the VOLX contract. The reverse is equally true. As a pure   
form of vega, the contracts offer particular benefits for vega hedging. Their vega profile is constant for any   
level of spot ahead of the rate setting period, and then diminishes linearly once the RSP has begun. The gamma of VOLX futures, in contrast, is very different from those of traditional options. Although a   
risk manager would traditionally hedge an option position by using a product with a similar gamma profile,   
hedging the gamma of a complex book with diversified strikes can become unwieldy. VOLX gamma,   
regardless of time and the level of the underlying spot, is evenly distributed. VOLX will be particularly   
useful for the traditionally hard to hedge out-of-the-money wings of an option portfolio.  

(Thomson Reuters IFR, November 23, 1996)  

# 9.6.7.3 Which expectation?  

We characterized trading gains expected from $S_{t}$ oscillations using the expression:  

$$
\left(E_{t_{0}}^{P*}\bigg[\frac{1}{2}\mathrm{gamma}(\Delta S_{t})^{2}\bigg]\right.
$$  

Here the expectation $E_{t_{0}}^{P*}[(\Delta S_{t})^{2}]$ is taken with respect to subjective probability distribution $P^{*}$ . The behavior of gamma traders depends on their subjective probability, but the market-determined arbitrage-free price will be objective and the corresponding expectation has to be arbitrage-free. The corresponding pricing formulas will depend on objective risk-adjusted probabilities.  

# 9.7 REAL-LIFE COMPLICATIONS  

In actual markets, the issues discussed here should be applied with care, because there will be significant deviations from the theoretical Black Scholes world. By convention, traders consider the Black Scholes world as the benchmark to use, although its shortcomings are well known.  

Every assumption in the Black Scholes world can be violated. Sometimes these deviations are harmless or can easily be accommodated by modifying the formula. Some such modifications of the formula would be minor, and others more significant, but in the end they take care of the problem at a reasonable effort.  

Yet, there are two cases that require substantial modifications. The first concerns the behavior of volatility. In financial markets, not only is volatility not constant, but it also has some unexpected characteristics. One of these anomalies is the smile effects.25 Volatility has, also, a term structure.  

The second case is when interest rates are stochastic, and the underlying asset is an interest rate-related instrument. Here, the deviation from the Black Scholes world, again, leads to significant changes.  

# 9.7.1 DEALING WITH OPTION BOOKS  

This chapter discussed gamma, delta, and vega risks for single option positions. Yet, market makers do not deal with single options. They have option books and they try to manage the delta, gamma, and vega risks of portfolios of options. This complicates the hedging and risk management significantly. The existence of exotic options compounds these difficulties.  

First of all, option books consist of options on different, possibly correlated, assets. Second, implied volatility may be different across strikes and expiration dates, and a straightforward application of delta, gamma, and vega concepts to the portfolio may become impossible. Third, while for single options delta, vega, and gamma have known shapes and dynamics, for portfolios of options, the shapes of delta, gamma, and vega are more complex and their movement over time may be more difficult to track.  

# 9.7.2 FUTURES AS UNDERLYING  

This chapter has discussed options written on cash instruments. How would we analyze options that are written on a futures or forward contract? There are two steps in designing option contracts. First, a futures or a forward contract is introduced on the cash instrument, and second, an option is written on the futures. The holder of the option has the right to buy one or more futures contracts.  

Why would anyone write an option on futures (forwards), instead of writing it on the cash instrument directly?  

In fact, the advantages of such contracts are many, and the fact that option contracts written on futures and forwards are the most liquid is not a coincidence. First of all, if one were to buy and sell the underlying in order to hedge the option positions, the futures contracts are more convenient. They are more liquid, and they do not require upfront cash payments. Second, hedging with cash instruments could imply, for example, selling or buying thousands of barrels of oil. Where would a trader put so much oil, and where would he get it? Worse, dynamic hedging requires adjusting such positions continuously. It would be very inconvenient to buy and sell a cash underlying. Long and short positions in futures do not result in delivery until the expiration date. Hence, the trader can constantly adjust his or her position without having to store barrels of oil at each rebalancing of the hedge. Futures are also more liquid and the associated transactions costs and counterparty risks are much smaller.  

Thus, the choice of futures and forwards as the underlying instead of cash instruments is, in fact, clever contract design. But we must remember that futures come with daily marking to market. Forward contracts, on the other hand, may not require any marking to market until the expiration date.  

# 9.7.2.1 Delivery mismatch  

Note the possibility of a mismatch. The option may result in the delivery of a futures contract at time $T.$ , but the futures contract may not expire at that same time. Instead, it may expire at a time $T+\Delta$ and may result in the delivery of the cash commodity. Such timing mismatches introduce new risks.  

# 9.8 CONCLUSION: WHAT IS AN OPTION?  

This chapter has shown that an option is essentially a volatility instrument. The critical parameter is how much the underlying risk oscillates within a given interval. We also saw that there are many other risks to manage. The implied volatility parameter, $\sigma$ , may change, interest rates may fluctuate, and option sensitivities may behave unexpectedly. These risks are not “costs” of maintaining the position perhaps, but they affect pricing and play an important role in option trading.  

# SUGGESTED READING  

Most textbooks approach options as directional instruments. There are, however, some nontechnical sources that treat options as volatility instruments directly. The first to come to mind is Natenberg (1994). A reader who prefers a technical approach has to consider more abstract treatments such as Musiela and Rutkowski (1998). Several texts discuss Black Scholes theory. The one that we recommend is Duffie (2001). Readers should look at Wilmott (2006) for the technical details. For the useful combination of options analysis with Mathematica, the reader can consult Stojanovic (2003). Risk publications have several books that collect articles that have the same approach used in this chapter. There, the reader will find a comprehensive discussion of the Black Scholes formula. Examples on Greeks were based on the terminology used in Derivatives Week (now part of GlobalCapital).  

# APPENDIX 9.1  

In this appendix, we derive formulas for delta and gamma. The relatively lengthy derivation is for delta.  

# DERIVATION OF DELTA  

The Black Scholes formula for a plain vanilla European call expiration $T.$ , strike, $K$ , is given by  

$$
C(S_{t},t)=S_{t}\int_{-\infty}^{\frac{\log(S_{I}/K)+(r+(1/2)\sigma^{2})(T-t)}{\sigma{\sqrt{T-t}}}}\frac{1}{\sqrt{2\pi}}e^{-(1/2)u^{2}}\mathrm{d}u-e^{-r(T-t)}K\int_{-\infty}^{\frac{\log(S_{I}/K)+(r-(1/2)\sigma^{2})(T-t)}{\sigma{\sqrt{T-t}}}}\frac{1}{\sqrt{2}\pi}e^{-(1/2)u^{2}}\mathrm{d}u
$$  

Rearrange and let $x_{t}=(S_{t}/K e^{-r(T-t)})$ , to get  

$$
C(x_{t},t)=K e^{-r(T-t)}\left[x_{t}\int_{-\infty}^{\infty}\frac{x_{t}+(1/2)\sigma^{2}(T-t)}{\sqrt{2}\pi}\frac{1}{\sqrt{2}\pi}e^{-(1/2)u^{2}}\mathrm{d}u-\int_{-\infty}^{\log{x_{t}-(1/2)\sigma^{2}(T-t)}}\right]
$$  

$$
\frac{1}{\sqrt{2}\pi}e^{-(1/2)u^{2}}\mathrm{d}u
$$  

Now differentiate with respect to $x_{t}$ :  

$$
\frac{\mathrm{d}C(x_{t},t)}{\mathrm{d}x_{t}}=K e^{-r(T-t)}\left[\int_{-\infty}^{\log{x_{t}+(1/2)\sigma^{2}(T-t)}}\frac{1}{\sqrt{2}\pi}e^{-(1/2)u^{2}}\mathrm{d}u\right]+\frac{1}{\sigma\sqrt{T-t}}
$$  

$$
\left[{\frac{1}{\sqrt{2}\pi}}e^{-{\frac{1}{2}}\left({\frac{\log{x_{I}}+(1/2)\sigma^{2}(T-t)}{\sigma{\sqrt{T-t}}}}\right)^{2}}\right]
$$  

$$
-\left[{\frac{1}{x_{t}\sigma{\sqrt{T-t}}}}{\frac{1}{\sqrt{2\pi}}}e^{-{\frac{1}{2}}\left({\frac{\log x_{t}-(1/2)\sigma^{2}(T-t)}{\sigma{\sqrt{T-t}}}}\right)^{2}}\right]
$$  

Now we show that the last two terms in this expression sum to zero and that  

$$
{\frac{1}{\sigma{\sqrt{T-t}}}}\left[{\frac{1}{\sqrt{2\pi}}}e^{-{\frac{1}{2}}\left({\frac{\log x_{t}+(1/2)\sigma^{2}(T-t)}{\sigma{\sqrt{T-t}}}}\right)^{2}}\right]={\frac{1}{x_{t}\sigma{\sqrt{T-t}}}}{\frac{1}{\sqrt{2\pi}}}e^{-{\frac{1}{2}}\left({\frac{\log x_{t}-(1/2)\sigma^{2}(T-t)}{\sigma{\sqrt{T-t}}}}\right)^{2}}
$$  

To see this, on the right-hand side, use the substitution:  

$$
{\frac{1}{x_{t}}}=e^{-\log x_{t}}
$$  

and then rearrange the exponent in the exponential function.  

Thus, we are left with  

$$
\frac{\partial C(x_{t},t)}{\partial x_{t}}=K e^{-r(T-t)}\left[\int_{-\infty}^{\frac{\log x_{t}+(1/2)\sigma^{2}(T-t)}{\sigma\sqrt{T-t}}}\frac{1}{\sqrt{2}\pi}e^{-(1/2)u^{2}}\mathrm{d}u\right]
$$  

Now use the chain rule and obtain  

$$
\frac{\partial C(S_{t},t)}{\partial S_{t}}=\left[\int_{-\infty}^{\frac{\log{x_{t}}+(1/2)\sigma^{2}(T-t)}{\sigma\sqrt{T-t}}}\frac{1}{\sqrt{2}\pi}e^{-(1/2)u^{2}}\mathrm{d}u\right]
$$  

$$
=N(d_{1})
$$  

# DERIVATION OF GAMMA  

Once delta of a European call is obtained, the gamma will be the derivative of the delta. This gives  

$$
\frac{\hat{\sigma}^{2}C(S_{t},t)}{\hat{\sigma}S_{t}^{2}}=\frac{1}{S_{t}\sigma\sqrt{T-t}}\frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}\left(\frac{\log{x_{t}}+(1/2)\sigma^{2}(T-t)}{\sigma\sqrt{T-t}}\right)^{2}}
$$  

with $x_{t}=(S_{t}/K e^{-r(T-t)})$  

# APPENDIX 9.2  

In this appendix, we review some basic concepts from stochastic calculus. This brief review can be used as a reference point for some of the concepts utilized in later chapters. Øksendal (2010) is a good source that provides an introductory discussion on stochastic calculus. Heuristics can be found in Hirsa and Neftci (2013).  

# STOCHASTIC DIFFERENTIAL EQUATIONS  

An SDE, driven by a Wiener process $W_{t},$ is written as  

$$
\mathrm{d}S_{t}=a(S_{t},t)\mathrm{d}t+b(S_{t},t)\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

This equation describes the dynamics of $S_{t}$ over time. The Wiener process $W_{t}$ has increments $\Delta W_{t}$ that are normally distributed with mean zero and variance $\Delta$ , where the $\Delta$ is a small time interval. These increments are uncorrelated over time. As a result, the future increments of a Wiener process are unpredictable given the information at time $t$ , the $I_{t}$ .  

The $a(S_{t},t)$ and the $b(S_{t},t)$ are known as the drift and the diffusion parameters. The drift parameter models expected changes in $S_{t}$ . The diffusion component models the corresponding volatility. When unpredictable movements occur as jumps, this will be referred as a jump component.  

A jump component would require adding terms such as $\lambda(S_{t},\ t)\mathrm{d}J_{t}$ to the right-hand side of the SDE shown above. Otherwise $S_{t}$ will be known as a diffusion process. With a jump component it becomes a jump-diffusion process.  

# Examples  

The simplest SDE is the one where the drift and diffusion coefficients are independent of the information received over time:  

$$
\mathrm{d}S_{t}=\mu\mathrm{d}t+\sigma\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

Here, $W_{t}$ is a standard Wiener process with variance $t$ . In this SDE, the coefficients $\mu$ and $\sigma$ do not have time subscripts $t$ , as time passes, they do not change.  

The standard SDE used to model underlying asset prices is the geometric process. It is the model assumed in the Black and Scholes world:  

$$
\mathrm{d}S_{t}=\mu S_{t}\mathrm{d}t+\sigma S_{t}\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

This model implies that drift and the diffusion parameters change proportionally with $S_{t}$ .  

An SDE that has been found useful in modeling interest rates is the mean reverting model:  

$$
\mathrm{d}S_{t}=\lambda(\mu-S_{t})\mathrm{d}t+\sigma S_{t}\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

According to this, as $S_{t}$ falls below a “long-run mean” $\mu$ , the term $(\mu-S_{t})$ will become positive, which makes $\mathrm{d}S_{t}$ more likely to be positive, hence, $S_{t}$ will revert back to the mean $\mu$ .  

# ITO’S LEMMA  

Suppose $f(S_{t})$ is a function of a random process $S_{t}$ having the dynamics:  

$$
\mathrm{d}S_{t}=a(S_{t},t)\mathrm{d}t+b(S_{t},t)\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

We want to expand $f\left({{S}_{t}}\right)$ around a known value of $S_{t},$ say $S_{0}$ using Taylor series expansions. The expansion will yield:  

$$
f(S_{t})=f(S_{0})+f_{s}(S_{0})[S_{t}-S_{0}]+\frac{1}{2}f_{s s}(S_{0})[S_{t}-S_{0}]^{2}+R(S_{t},S_{0})\nonumber
$$  

where $R(S_{t},S_{0})$ represents all the remaining terms of the Taylor series expansion.  

First note that $f(S_{t})$ can be rewritten as, $f\left({S_{0}}+{\Delta{S_{t}}}\right)$ , if we define $\Delta S_{t}$ as:  

$$
\Delta S_{t}=S_{t}-S_{0}
$$  

Then, the Taylor series approximation will have the form:  

$$
f(S_{0}+\Delta S_{t})-f(S_{0})\cong f_{s}\Delta S_{t}+\frac{1}{2}f_{s s}\Delta S_{t}^{2}
$$  

The $\Delta S_{t}$ is a “small” change in the random variable $S_{t}$ . In approximating the right-hand side, we keep the term $f_{s}\ \Delta S_{t}$ .  

Consider the second term $(1/2)f_{s s}(\Delta S_{t})^{2}$ . If $S_{t}$ is deterministic, one can say that the term $(\Delta S_{t})^{2}$ is small. This could be justified by keeping the size of $\Delta S_{t}$ non-negligible, yet small enough that its square $(\Delta S_{t})^{2}$ is negligible. However, here, changes in $S_{t}$ will be random. Suppose these changes have zero mean. Then the variance is  

$$
0<E[\Delta S_{t}]^{2}\cong b(S_{t},t)^{2}\Delta
$$  

This equality means that as long as $S_{t}$ is random, the right-hand side of Eq. (9.121) must keep the second-order term in any type of Taylor series approximation.  

Moving to infinitesimal time $\mathrm{d}t$ , this gives Ito’s Lemma, which is the stochastic version of the Chain rule,  

$$
\mathrm{d}f(S_{t})=f_{s}\mathrm{d}S_{t}+\frac{1}{2}f_{s s}b(S_{t},t)^{2}\mathrm{d}t
$$  

This equation can be regarded as the dynamics of the process $f(S_{t})$ , which is driven by $S_{t}$ . The $\mathrm{d}S_{t}$ term in the above equation can be substituted out using the $S_{t}$ dynamics.  

# GIRSANOV THEOREM  

Girsanov Theorem provides the general framework for transforming one probability measure into another “equivalent” measure. It is an abstract result that plays a very important role in pricing.  

In heuristic terms, this theorem says the following. If we are given a Wiener process $W_{t}$ , then, we can multiply the probability distribution of this process by a special function $\boldsymbol{\xi}_{t}$ that depends on time $t.$ , and on the information available at time $t$ , the $I_{t}$ . This way we can obtain a new Wiener process $\tilde{W}_{t}$ with probability distribution $\tilde{P}$ . The two processes will relate to each other through the relation:  

$$
\mathrm{d}\tilde{W}_{t}=\mathrm{d}W_{t}-X_{t}\mathrm{d}t
$$  

That is to say, $\tilde{W}_{t}$ is obtained by subtracting an $I_{t}$ -dependent term $X_{t},$ , from $W_{t}$ .  

Girsanov Theorem is often used in the following way: (i) we have an expectation to calculate, (ii) we transform the original probability measure, such that expectation becomes easier to calculate, and (iii) we calculate the expectation under the new probability.  

# EXERCISES  

1. Consider the following comment dealing with options written on the euro dollar exchange rate:  

Some traders, thinking that implied volatility was too high entered new trades. One example was to sell one-year in-the-money euro Puts with strikes around USD1.10 and buy one-year at-the-money euro Puts. If the euro is above USD1.10 at maturity, the trader makes the difference in the premiums. The trades were put on across the curve. (Based on an article in Derivatives Week (now part of GlobalCapital)).  

a. Draw the profit/loss diagrams of this position at expiration for each option separately.   
b. What would be the gross payoff at expiry?   
c. What would be the net payoff at expiry?   
d. Why would the traders buy “volatility” given that they buy and sell options? Don’t these two cancel each other in terms of volatility exposure?  

2. (Delta Hedge Portfolio)  

Write a VBA program to show the delta-hedged portfolio adjustments and cash flows for a long call from the dealers’ perspective with the following data:  

Total number of long calls $N=100$ Number of adjustments $M=15$ $S(0)=100\$ ; $K=100$ ; $T=1$ ; $r=8\%$ ; $\sigma=30\%$ ; and realized volatility $=50\%$ .  

3. Consider the following quote:  

Implied U.S. dollar/New Zealand dollar volatility fell to $I O.I\%/I I.I\%$ on Tuesday. Traders   
bought at-the-money options at the beginning of the week, ahead of the Federal Reserve   
interest-rate cut. They anticipated a rate cut which would increase short-term volatility. They   
wanted to be long gamma. Trades were typically for one-week maturities, in average notionals   
of USD10 20 million. (Based on an article in Derivatives Week (now part of GlobalCapital)).   
a. Explain why traders wanted to be long gamma when the volatility was expected to increase.   
b. Show your argument using numerical values for Greeks and the data given in the reading.  

c. How much money would the trader lose under these circumstances? Calculate approximately, using the data supplied in the reading. Assume that the position was originally for USD30 million.  

4. Consider the following episode:  

EUR/USD one-month implied volatility sank by $2.7\%$ to $10\%$ Wednesday as traders hedged this euro exposure against the greenback, as the euro plunged to historic lows on the spot market. After the European Central Bank raised interest rates by 25 basis points, the euro fell against leading to a strong demand for euro Puts. The euro touched a low of USD0.931 Wednesday. (Based on an article in Derivatives Week.)  

a. In the euro/dollar market, traders rushed to stock up on gamma by buying short-dated euro puts struck below USD0.88 to hedge against the possibility that the interest rates rise. Under normal circumstances, what would happen to the currency?   
b. When the euro failed to respond and fell against major currencies, why would the traders then rush to buy euro puts? Explain using payoff diagrams.   
c. Would a trader “stock up” gamma if euro-triggered barrier options?  

5. You are given the following table concerning the price of a put option satisfying all Black Scholes assumptions. The strike is 20 and the volatility is $30\%$ . The risk-free rate is $2.5\%$  

<html><body><table><tr><td>Option Price</td><td>Underlying Asset Price</td></tr><tr><td>10</td><td>10</td></tr><tr><td>5</td><td>15</td></tr><tr><td>1.3</td><td>20</td></tr><tr><td>0.25</td><td>25</td></tr><tr><td>0.14</td><td>30</td></tr></table></body></html>  

The option expires in 100 days. Assume (for convenience), that, for every month the option loses approximately one-third of its value.  

a. How can you approximate the option delta? Calculate three approximations for the delta in the previous case.   
b. Suppose you bought the option when the underlying was at 20 using borrowed funds. You have hedged this position in a standard fashion. How much do you gain or lose in four equal time periods if you observe the following price sequence in that order:  

c. Suppose now that the underlying price follows the new trajectory given by  

How much do you gain or lose until expiration? d. Explain the difference between gains and losses.  

6. Search the Internet for the following questions. a. Which sensitivities do the Greeks, volga and Vanna represent? b. Why are they relevant for vega hedging?  

“‘Exploiting the franc peg’  

[. . .]  

The Swiss currency is no longer rallying the way it did during market distress on Eurozone debt concerns. It all changed when the Swiss National Bank (SNB) announcement pegging its currency against the euro at the EUR/CHF rate of 1.20, aimed at preventing excessive franc acceleration against the debt-ridden euro. As credit rating agencies rushed to downgrade the sovereign debt of Southern Europe in late 2009, investors rushed their savings out of the single currency and into safe-haven francs. The exodus took the form of cash flight, property sales and bank transfers as “default” became a recurring theme in Greece, Spain, Portugal, Ireland and Italy.  

Consequently, the franc soared $35\%$ and $40\%$ against the euro and the USD respectively from 2009 to September 2011. The SNB began massive interventions in March 2009 to sell its currency for euros to stem the tide of the soaring franc. But the surge of franc-bound capital caused the SNB to lose more than CHF 20 billion from early 2009 to end of 2010. When the central bank’s losses became a matter of national urgency, it ultimately went with the “nuclear option.” On Sept. 6, 2011 the SNB announced it “will no longer tolerate a EUR/CHF exchange rate below the minimum rate of CHF 1.20. The SNB will enforce this minimum rate with the utmost determination and is prepared to buy foreign currency in unlimited quantities.”  

SNB had pegged its currency once before against the Deutsche mark in 1978 after francs soared close to $100\%$ , near doubling in the prior six years as a result of U.S. stagflation following the oil crisis. The franc/mark peg lasted two years and dragged down the franc’s effective trade index by about $14\%$ .  

The question then becomes whether the SNB remains successful in stemming further CHF strength. Will it make sense to sell the franc into 2012? As of this writing, the Swiss franc lost nearly one third of its value against the euro and U.S. dollar since the euro peg began in September.  

Our favorite pick against the Swiss franc would be the Canadian dollar because of ongoing volatility in oil prices stemming from Mideast uncertainty. Aside from the energy argument sustaining the loonie, any surprise bounce in U.S. growth is likely to help loonie sentiment. CAD/CHF is seen extending gains towards 0.96 from the current 0.90, with support cropping up at 0.88. An alternative but similar trade would be to combine longs in USD/CHF with shorts in USD/CAD.” (source: www.futuresmag.com, Exploiting the franc peg, by Ashraf Laidi, January 1, 2012)  

7. Answer the questions related to the case study Swiss Central Bank, 2012: a. What is the rationale for the proposed futures strategy b. What options strategy could you consider that would also benefit from the peg?  

8. (MATLAB exercise on European Option)  

Write a MATLAB program to determine the initial price of European Call and European Put option using the BSM formula with the following data:  

Now plot the initial price of both call and put options by varying the following parameters at a time while keeping the other parameters fixed.  

a. $S(0)$   
b. $K$   
c. $r$   
d. $\sigma$  

Also plot the initial call and put price juxtaposed by varying two parameters at a time and keeping other parameters fixed.  

e. $S(0)$ & $K$ f. $K$ & $\sigma$ g. $S(0)$ & $\sigma$  

9. (MATLAB exercise on Chooser Option)  

Write a MATLAB program to determine the initial price of chooser option using the BSM formula with the following data:  

$S(0)=100$ ; $K=105$ ; $T_{0}=0.5$ ; $T=1$ ; $r=8\%$ ; $\sigma=30\%$  

Now plot the initial price of option by varying the following parameters at a time while eeping the other parameters fixed.  

a. S(0)   
b. $K$   
c. $T_{0}$ Also plot the variation of option price with $T_{0}$ & $T$ together and keeping other parameters   
fixed.  

10. (MATLAB exercise on Barrier Option)  

Write a MATLAB program to determine the initial price of Barrier Down and In Call option and Barrier Down and Out Call option using the BSM formula with the following data: $S(0)=100$ ; $K=105$ ; $T=1$ ; $r=8\%$ ; $\sigma=30\%$ ; $H=95$  

Now plot the initial price of both call and put options by varying the following parameters at a time while keeping the other parameters fixed.  

a. $S(0)$   
b. $K$   
c. $H$  

11. MATLAB exercise on a Delta-Hedged Portfolio  

Write a MATLAB program to delta hedge the portfolio consisting only of the stock and the risk-free asset to cover the long call option. Observe the number of shorted shares and the cash flow during the adjustment of the portfolio to make it delta neutral at each time point. Report the final cash position at the expiration after settling all the open positions.  

Gradually increase the frequency of adjustment and observe the net cash position and also plot the performance vs frequency of this delta hedging that how correctly it covers the long call position.  

Use the following data:   
$S(0)=100\$ ; $K=105$ ; $T=1$ ; $r=8\%$ ; $\sigma=30\%$ and realized volatility $=50\%$   
Frequency: [6, 12, 50, 100, 300]  