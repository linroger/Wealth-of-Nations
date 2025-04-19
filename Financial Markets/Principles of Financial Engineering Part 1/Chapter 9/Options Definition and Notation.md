---
tags:
  - '#american_options'
  - '#black_scholes_model'
  - '#european_options'
  - '#expiration_date'
  - '#option_contracts'
  - '#option_notation'
  - '#option_payoff'
  - '#option_time_value'
  - '#plain_vanilla_options'
  - '#strike_price'
---
# 9.3 OPTIONS: DEFINITION AND NOTATION  

Option contracts are generally divided into the categories of plain vanilla and exotic options, although many of the options that used to be known as exotic are vanilla instruments today. In discussing options, it is good practice to start with a simple benchmark model, understand the basics. of options, and then extend the approach to more complicated instruments. This simple benchmark will be a plain vanilla option treated within the framework of the Black-Scholes model..  

The buyer of an option does not buy the underlying instrument; he or she buys a right. If this right. can be exercised only at the expiration date, then the option is European. If it can be exercised anytime during the specified period, the option is said to be American. A Bermudan option is "in between," given that it can be exercised at more than one of the dates during the life of the option..  

In the case of a European plain vanilla call, the option holder has purchased the right to "buy" the underlying instrument at a certain price, called the strike or exercise price, at a specific date,. called the expiration date. In the case of the European plain vanilla put, the option holder has again purchased the right to an action. The action in this case is to "sell' the underlying instrument at the. strike price and at the expiration date.  

American-style options can be exercised anytime until expiration and hence may be more expensive. They may carry an early exercise premium. At the expiration date, options cease to. exist. In this chapter, we discuss basic properties of options using mostly plain vanilla calls.. Obviously, the treatment of puts would be similar..  

# 9.3.1 NOTATION  

We denote the strike prices by the symbol $K$ , and the expiration date by $T$ The price or value of the underlying instrument will be denoted by $S_{t}$ if it is a cash product, and by $F_{t}$ if the underlying is a forward or futures price. The fair price of the call at time $t$ will be denoted by $C(t)$ , and the price of the put by $P(t)$ 3 These prices depend on the variables and parameters underlying the contract. We use $S_{t}$ as the underlying, and write the corresponding call option pricing function as  

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
\frac{\partial^{2}C(S_{t},t)}{\partial S_{t}^{2}}=C_{s s}
$$  

$$
\frac{\partial C(S_{t},t)}{\partial t}=C_{t}
$$  

More is known on the properties of these partials. Everything else being the same, if $S_{t}$ increases, the call option price,. $C(t)$ , also increases. If $S_{t}$ declines, the price declines. But the. changes in $C(t)$ will never exceed those in the underlying asset, $S_{t}$ Hence, we should have.  

$$
0{<}C_{s}<1
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

The notation in Eq. (9.1) suggests that the partials themselves are functions of $S_{t},r,K,t,T_{i}$ and $\sigma$ .Hence, one may envisage some further higher-order partials. The traditional Black-Scholes vanilla option pricing environment uses the partials, $\{C_{s},C_{s s},C_{t}\}$ only. Further partial derivatives are brought into the picture as the Black-Scholes assumptions are relaxed gradually.  

Figure 9.2 shows the expiration date payoffs of plain vanilla put and call options. In the same figure we have the time t, $t<T$ value of the calls and puts. These values trace a smooth convex curve obtained from the Black-Scholes formula.  

We now consider a real-life application of these concepts. The following example looks at. Microsoft options traded at the Chicago Board of Options Exchange and discusses various parameters within this context.  

![](fcaf7e115081a35a3291ba4e3db84aa7b26ce5fa080edae315652fff53fc5ecc.jpg)  

# FIGURE 9.2  

Expiration date payoffs of plain vanilla put and call options.  

# EXAMPLE  

Suppose Microsoft (MSFT) is "currently" trading at 61.15 at Nasdaq. Further, the overnight rate is $2.7\%$ . We have the following quotes from the Chicago Board of Options Exchange (CBOE).  

In the table, the first column gives the expiration date and the strike level of the option.. The exact time of expiration is the third Friday of every month. These equity options in. CBOE are of American style. The bid price is the price at which the market maker is willing. to buy this option from the client, whereas the ask price is the price at which he or she is willing to sell it to the client.  

<html><body><table><tr><td>Calls Bid</td><td></td><td>Volume</td></tr><tr><td>Nov 55.00</td><td>Ask 7.1 7.4</td><td></td></tr><tr><td>Nov 60.00</td><td>3.4 3.7</td><td>78</td></tr><tr><td>Nov 65.00</td><td></td><td>6291</td></tr><tr><td>Nov 70.00</td><td>1.2 1.3</td><td>1456</td></tr><tr><td>Dec55.00</td><td>0.3 0.4</td><td>98</td></tr><tr><td></td><td>8.4 8.7</td><td></td></tr><tr><td>Dec 60.00 Dec 65.00</td><td>5 5.3 2.65 2.75</td><td>29</td></tr><tr><td>Dec 70.00</td><td>1.2 1.25</td><td>83</td></tr><tr><td></td><td></td><td>284</td></tr></table></body></html>  

<html><body><table><tr><td>Puts</td><td>Bid</td><td>Ask Volume</td><td></td></tr><tr><td>Nov55.00</td><td>0.9</td><td>1.05</td><td>202</td></tr><tr><td>Nov 60.00</td><td>2.3</td><td>2.55</td><td>5984</td></tr><tr><td>Nov 65.00</td><td>5</td><td>5.3</td><td>64</td></tr><tr><td>Nov 70.00</td><td>9</td><td>9.3</td><td>20</td></tr><tr><td>Dec55.00</td><td>2.05</td><td>2.35</td><td>10</td></tr><tr><td>Dec 60.00</td><td>3.8</td><td>4.1</td><td>76</td></tr><tr><td>Dec 65.00</td><td>6.3</td><td>6.6</td><td>10</td></tr><tr><td>Dec 70.00</td><td>9.8</td><td>10.1</td><td>25</td></tr></table></body></html>

Note: October 24, 2002, 11:02 A.M. data from CBOE.  

CBOE option prices are multiplied by $\$100$ and then invoiced. Of course, there are some additional costs to buying and selling options due to commissions and possibly other expenses. The last column of the table indicates the trading volume of the relevant contract.  

For example, consider the November 55 put. This option will be in-the-money, if the Microsoft stock is below 55.00. If it stays so until the third Friday of November 2001, the option will have a positive payoff at expiration..  

100 such puts will cost  

$$
1.05\times100\times100=\$10,500
$$  

plus commissions to buy, and can be sold at  

$$
0.90\times100\times100=\mathbb{\mathbb{S}}9000
$$  

if sold at the bid price. Note that the bid-ask spread for one \*lot' had a value of $\$1500$ that day.  

We now study option mechanics more closely and introduce further terminology.  

# 9.3.2 ON RETAIL USE OF OPTIONS  

Consider a retail client and an option market maker as the two sides of the transaction. Suppose a business uses the commodity $S_{t}$ as a production input and would like to "cap" the price $S_{T}$ at a future date T. For this insurance, the business takes a long position using call options on $S_{t}$ . The call option premium is denoted by $C(t)$ . By buying the call, the client makes sure that he or she can buy one unit of the underlying at a maximum price $K$ , at expiration date $T.$ If at time $T$ $S_{T}$ is lower than $K$ , the client will not exercise the option. There is no need to pay $K$ dollars for something that is selling for less in the marketplace. The option will be exercised only if $S_{T}$ equals or exceeds $K$ at time $T$  

Looked at this way, options are somewhat similar to standard insurance against potential. increases in commodities prices. In such a framework, options can be motivated as directional instruments. One has the impression that an increase in $S_{t}$ is harmful for the client, and that the call "protects" against this risk. The situation for puts is symmetrical. Puts appear to provide protection. against the risk of undesirable "declines" in $S_{t}$ . In both cases, a certain direction in the change of the underlying price $S_{t}$ is associated with the call or put, and these appear to be fundamentally dif-. ferent instruments.  

Figure 9.3 illustrates these ideas graphically. The upper part shows the payoff diagram for a call option. Initially, at time $t_{0}$ , the underlying price is at $S_{t_{0}}$ . Note that $S_{t_{0}}<K$ , and the option is out-ofthe-money. Obviously, this does not mean that the right to buy the asset at time $T$ for $K$ dollars has no value. In fact, from a client's point of view,. $S_{t}$ may move up during interval $t\in[t_{O},T]$ and end up exceeding $K$ by time $T.$ This will make the option in-the-money. It would then be profitable to exercise the option and buy the underlying at a price. $K$ The option payoff will be the difference. $S_{T}-K$ if $S_{T}$ exceeds $K.$ This payoff can be shown either on the horizontal axis or, more explicitly,. on the vertical axis.4 Thus, looked at from the retail client's point of view, even at the price level $S_{t_{0}}$ , the out-of-the money option is valuable, since it may become in-the-money later. Often, the directional motivation of options is based on these kinds of arguments.  

If the option expires at $S_{T}=K$ , the option will be at-the-money (ATM) and the option holder. may or may not choose to receive the underlying. However, as the costs associated with delivery of the call underlying are, in general, less than the transaction costs of buying the underlying in the open market, some holders of ATM options prefer to exercise..  

Hence, we get the typical price diagram for a plain vanilla European call option. The option price for $t\in[t_{O},T]$ is shown in Figure 9.3 as a smooth convex curve that converges to the piecewise linear option payoff as expiration time $T$ approaches. The vertical distance between the payoff line and the horizontal axis is called intrinsic value. The vertical distance between the option price curve and the expiration payoff is called the time value of the option. Note that for a fixed $t$ the time value appears to be at a maximum when the option is ATM--that is to say, when $S_{t}=K$  

# 9.3.3 SOME INTRIGUING PROPERTIES OF THE DIAGRAM  

Consider point $A$ in the top part of Figure 9.3. Here, at time $t$ , the option is deep out-of-the money. $S_{t}$ is close to the origin and the time value is close to zero. The tangent at point $A$ has a positive  

![](d46835500a409aa6fdc9930487b46c3b0be1ad853a176ad1b62c851d964e774f.jpg)  

# FIGURE 9.3  

Value of in-the-money, out-of-the-money, and ATM call.  

slope that is little different from zero. The curve is almost "linear' and the second derivative is also close to zero. This means that for small changes in. $S_{t}$ , the slope of the tangent will not vary much..  

Now, consider the case represented by point $B$ in Figure 9.3. Here, at time. $t.$ the option is deep. in-the-money. $S_{t}$ is significantly higher than the strike price. However, the time value is again close to zero. The curve approaches the payoff line and hence has a slope close to $+1$ . Yet, the second. derivative of the curve is once again very close to zero. This again means that for small changes in $S_{t}$ , the slope of the tangent will not vary much.  

The third case is shown as point $C$ in the lower part of Figure 9.3. Suppose the option was. ATM at time $t$ , as shown by point $C$ . The value of the option is entirely made of time value. Also, the slope of the tangent is close to O.5. Finally, it is interesting that the curvature of the option is highest at point $C$ and that if $S_{t}$ changes a little, the slope of the tangent will change significantly..  

This brings us to an interesting point. The more convex the curve is at a point, the higher the associated time value seems to be. In the two extreme cases where the slope of the curve is diametrically different, namely at points. $A$ and $B$ , the option has a small time value. At both points, the. second derivative of the curve is small. When the curvature reaches its maximum, the time value is. greatest. The question, of course, is whether or not this is a coincidence..  

Pursuing this connection between time value and curvature further will lead us to valuing the underlying volatility. Suppose, by holding an option, a market maker can somehow generate "cash"' earnings as $S_{t}$ oscillates. Could it be that, everything else being the same, the greater the curvature Of $C(t)$ , the greater the cash earnings are? Our task in the next section is to show that this is indeed the case.  
