---
tags:
  - bull_spread
  - european_call_option
  - option_strategy
  - spread_trading
  - strike_price
aliases:
  - bull spreads
  - spreads
key_concepts:
  - bull spread definition
  - call option strike price
  - option expiration date
  - payoff from bull spread
  - spread trading strategy
---

# 12.3 SPREADS  

A spread trading strategy involves taking a position in two or more options of the same type (i.e., two or more calls or two or more puts).  

# Bull Spreads  

One of the most popular types of spreads is a bull spread. This can be created by buying a European call option on a stock with a certain strike price and selling a European call option on the same stock with a higher strike price. Both options have the same expiration date. The strategy is illustrated in Figure 12.2. The profits from the two option positions taken separately are shown by the dashed lines. The profit from the whole strategy is the sum of the profits given by the dashed lines and is indicated by the solid line. Because a call price always decreases as the strike price increases, the value of the option sold is always less than the value of the option bought. A bull spread, when created from calls, therefore requires an initial investment.  

Suppose that $K_{1}$ is the strike price of the call option bought, $K_{2}$ is the strike price of the call option sold, and. $S_{T}$ is the stock price on the expiration date of the options.. Table 12.1 shows the total payoff that will be realized from a bull spread in different. circumstances. If the stock price does well and is greater than the higher strike price, the payoff is the difference between the two strike prices, or. $K_{2}\mathrm{~-~}K_{1}$ . If the stock price on the expiration date lies between the two strike prices, the payoff is $S_{T}-K_{1}$ . If the stock price on the expiration date is below the lower strike price, the payoff is zero. The profit. in Figure 12.2 is calculated by subtracting the initial investment from the payoff..  

![](b2be3e6ce8edf0a30b658a9dc8df02d74a75ab917c9f8250a76ec29742a4e62b.jpg)  
Figure 12.2 Profit from bull spread created using call options  

Table 12.1 Payoff from a bull spread created using calls   


<html><body><table><tr><td>Stockprice range</td><td>Payofffrom longcalloption</td><td>Payofffrom shortcalloption</td><td>Total payoff</td></tr><tr><td>ST ≤ K1</td><td>0</td><td>0</td><td>0</td></tr><tr><td>K1 < S < K2</td><td>ST - K1</td><td>0</td><td>ST - K1</td></tr><tr><td>ST ≥ K2</td><td>Sr - K1</td><td>-(ST - K2)</td><td>K2 - K1</td></tr></table></body></html>  

A bull spread strategy limits the investor's upside as well as downside risk. The strategy can be described by saying that the investor has a call option with a strike price equal to $K_{1}$ and has chosen to give up some upside potential by selling a call option with strike price $K_{2}$ $(K_{2}>K_{1})$ . In return for giving up the upside potential, the investor gets the price of the option with strike price $K_{2}$ . Three types of bull spreads can be distinguished:  

1. Both calls are initially out of the money..   
2. One call is initially in the money; the other call is initially out of the money.   
3. Both calls are initially in the money.  

The most aggressive bull spreads are those of type 1. They cost very little to set up and. have a small probability of giving a relatively high payoff. $(=K_{2}-K_{1})$ . As we move from type 1 to type 2 and from type 2 to type 3, the spreads become more conservative.  

# Example 12.2  

An investor buys forr $\$3$ a 3-month European call with a strike price of $\$30$ and sells for $\$1$ a 3-month European call with a strike price of $\$35$ . The payoff from. this bull spread strategy is. $\$5$ if the stock price is above. $\$35$ , and zero if it is. below $\$30$ If the stock price is between $\$30$ and $\$35$ , the payoff is the amount by which the stock price exceeds. $\$30.$ The cost of the strategy is $\$3-\$1=\$2.$ So the profit is:  

<html><body><table><tr><td>Stock price range</td><td>Profit</td></tr><tr><td>Sr ≤ 30</td><td>-2</td></tr><tr><td>30 <Sr<35</td><td>ST - 32</td></tr><tr><td>Sr ≥ 35</td><td>3</td></tr></table></body></html>  

Bull spreads can also be created by buying a European put with a low strike price and selling a European put with a high strike price, as illustrated in Figure 12.3. Unlike bull spreads created from calls, those created from puts involve a positive up-front cash flow to the investor, but have margin requirements and a payoff that is either negative Or zero.  

![](06d42582f8d5501d30f06e2d9b4020fc2f1071da0652ed2b993471480985bfb3.jpg)  
Figure 12.3 Profit from bull spread created using put options.  

# Bear Spreads  

An investor who enters into a bull spread is hoping that the stock price will increase. By. contrast, an investor who enters into a bear spread is hoping that the stock price will. decline. Bear spreads can be created by buying a European put with one strike price and. selling a European put with another strike price. The strike price of the option purchased is greater than the strike price of the option sold. (This is in contrast to a bull spread, where the strike price of the option purchased is always less than the strike price of the option sold.) In Figure 12.4, the profit from the spread is shown by the solid line. A bear spread created from puts involves an initial cash outflow because the price of the put sold is less than the price of the put purchased. In essence, the investor has bought a put with a certain strike price and chosen to give up some of the profit potential by selling a put with a lower strike price. In return for the profit given up, the investor gets the price of the option sold..  

Assume that the strike prices are $K_{1}$ and $K_{2}$ with $K_{1}<K_{2}$ . Table 12.2 shows the payoff that will be realized from a bear spread in different circumstances. If the stock  

![](2f774f7e2c3bd90892f97d89b157fac045078e407b0cdee3b8c603a21744e53c.jpg)  
Figure 12.4 Profit from bear spread created using put options.  

Table 12.2 Payoff from a bear spread created with put options.   


<html><body><table><tr><td>Stockprice range</td><td>Payofffrom longputoption</td><td>Payofffrom shortputoption</td><td>Total payoff</td></tr><tr><td>Sr ≤ K1</td><td>K2 - ST</td><td>(s - ly)-</td><td>K2 - K1</td></tr><tr><td>K1 < S < K2</td><td>K2 - ST</td><td>0</td><td>K2 - ST</td></tr><tr><td>ST ≥ K2</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>  

price is greater than. $K_{2}$ , the payoff is zero. If the stock price is less than. $K_{1}$ , the payoff is.   
$K_{2}\mathrm{~-~}K_{1}$ . If the stock price is between $K_{1}$ and $K_{2}$ , the payoff is. $K_{2}-S_{T}.$ The profit is.   
calculated by subtracting the initial cost from the payoff.  

# Example 12.3  

An investor buys for. $\$3$ a 3-month European put with a strike price of $\$35$ and sells for $\$1$ a 3-month European put with a strike price of $\$30$ The payoff from this bear spread strategy is zero if the stock price is above $\$35$ , and $\$5$ if it is below. $\$30.$ If the stock price is between $\$30$ and $\$35$ , the payoff is $35-S_{T}.$ The options cost $\$3-\$1=\$2$ up front. So the profit is:  

<html><body><table><tr><td>Stock pricerange</td><td>Profit</td></tr><tr><td>Sr ≤ 30</td><td>+3</td></tr><tr><td>30<S<35</td><td>33 - ST</td></tr><tr><td>Sr≥35</td><td>-2</td></tr></table></body></html>  

Like bull spreads, bear spreads limit both the upside profit potential and the downside risk. Bear spreads can be created using calls instead of puts. The investor buys a call with a high strike price and sells a call with a low strike price, as illustrated in Figure 12.5. Bear spreads created with calls involve an initial cash inflow, but have margin requirements and a payoff that is either negative or zero.  

![](595760e3f8c3d804f64a5fc1837861662f6b8bd1b77f9679c4a8124e0a93271b.jpg)  
Figure 12.5 Profit from bear spread created using call options.  

Table 12.3 Payoff from a box spread.   
Figure 12.6 Profit from butterfly spread using call options.   


<html><body><table><tr><td>Stockprice range</td><td>Payofffrom bullcallspread</td><td>Payofffrom bearputspread</td><td>payoff</td></tr><tr><td>Sr ≤K1</td><td>0</td><td>K2 - K1</td><td>K2 - K1</td></tr><tr><td>K1 < Sr < K2</td><td>ST - K1</td><td>K2 - ST</td><td>K2 - K1</td></tr><tr><td>ST ≥ K2</td><td>K2 - K1</td><td>0</td><td>K2 - K1</td></tr></table></body></html>  

# Box Spreads  

A box spread is a combination of a bull call spread with strike prices. $K_{1}$ and $K_{2}$ and a bear put spread with the same two strike prices. As shown in Table 12.3, the payoff. from a box spread is always $K_{2}\mathrm{~-~}K_{1}$ The value of a box spread is therefore always the present value of this payoff or $(K_{2}-K_{1})e^{-r T}$ . If it has a different value there is an arbitrage opportunity. If the market price of the box spread is too low, it is profitable to. buy the box. This involves buying a call with strike price $K_{1}$ , buying a put with strike price $K_{2}$ , selling a call with strike price $K_{2}$ , and selling a put with strike price $K_{1}$ . If the market price of the box spread is too high, it is profitable to sell the box. This involves buying a call with strike price $K_{2}$ , buying a put with strike price $K_{1}$ , selling a call with strike price $K_{1}$ , and selling a put with strike price $K_{2}$  

It is important to realize that a box-spread arbitrage only works with European options. Many of the options that trade on exchanges are American. As shown in Business Snapshot 12.1, inexperienced traders who treat American options as European are liable to lose money.  

# Butterfly Spreads  

A butterfly spread involves positions in options with three different strike prices. It can be created by buying a European call option with a relatively low strike price $K_{1}$  

![](4b32db945385e370e84f10f6c35fa5c8a5e704f1e80bdbd5b1ff7aa7f8f7ae82.jpg)  

# Business Snapshot 12.1 Losing Money with Box Spreads  

Suppose that a stock has a price of. $\$50$ and a volatility of. $30\%$ . No dividends are. expected and the risk-free rate is $8\%$ . A trader offers you the chance to sell on the. CBOE a 2-month box spread where the strike prices are $\$55$ and $\$60$ for $\$5.10$ Should you do the trade?  

The trade certainly sounds attractive. In this case $K_{1}=55,K_{2}=60$ , and the payoff is certain to be $\$5$ in 2 months. By selling the box spread for $\$5.10$ and investing the funds for 2 months you would have more than enough funds to meet the $\$5$ payoff in 2 months. The theoretical value of the box spread today is $5\times e^{-0.08\times2/12}=\dot{\S}4.93$ -  

Unfortunately there is a snag. CBOE stock options are American and the $\$5$ payoff from the box spread is calculated on the assumption that the options comprising the box are European. Option prices for this example (calculated using DerivaGem) are shown in the table below. A bull call spread where the strike prices are $\$55$ and $\$60$ costs $0.96\mathrm{~-~}0.26=\$0.70.$ (This is the same for both European and American options. because, as we saw in Chapter 11, the price of a European call is the same as the price of an American call when there are no dividends.) A bear put spread with the same strike prices costs $9.46-5.23=\$4.23$ if the options are European and $10.00-5.44=\$4.56$ if they are American. The combined value of both spreads if they are created with European options is $0.70+4.23=\$4.93$ This is the theoretical box spread price. calculated above. The combined value of buying both spreads if they are American is $0.70+4.56=\$5.26$ Selling a box spread created with American options for. $\$5.10$ would not be a good trade. You would realize this almost immediately as the trade involves selling a $\$60$ strike put and this would be exercised against you almost as soon as you sold it!  

<html><body><table><tr><td>Option type</td><td>Strike price</td><td>European option price</td><td>American option price</td></tr><tr><td>Call</td><td>60</td><td>0.26</td><td>0.26</td></tr><tr><td>Call</td><td>55</td><td>0.96</td><td>0.96</td></tr><tr><td>Put</td><td>60</td><td>9.46</td><td>10.00</td></tr><tr><td>Put</td><td>55</td><td>5.23</td><td>5.44</td></tr></table></body></html>  

Table 12.4 Payoff from a butterfly spread.   


<html><body><table><tr><td>Stockprice range</td><td>Payofffrom firstlongcall</td><td>Payofffrom second longcall</td><td>Payofffrom shortcalls</td><td>Total payoff</td></tr><tr><td>ST ≤ K1</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>K1 < Sr ≤ K2</td><td>Sr - K1</td><td>0</td><td>0</td><td>Sr - K1</td></tr><tr><td>K2 < S < K3</td><td>ST - K1</td><td>0</td><td>-2(ST - K2)</td><td>K3 - ST</td></tr><tr><td>ST ≥ K3</td><td>Sr - K1</td><td>ST - K3</td><td>-2(ST - K2)</td><td>0</td></tr></table></body></html>

\*These payoffs are calculated using the relationship $K_{2}=0.5(K_{1}+K_{3})$  

buying a European call option with a relatively high strike price. $K_{3}$ , and selling two European call options with a strike price. $K_{2}$ that is halfway between $K_{1}$ and $K_{3}$ Generally, $K_{2}$ is close to the current stock price. The pattern of profits from the strategy. is shown in Figure 12.6. A butterfly spread leads to a profit if the stock price stays close to $K_{2}$ , but gives rise to a small loss if there is a significant stock price move in either direction. It is therefore an appropriate strategy for an investor who feels that large. stock price moves are unlikely. The strategy requires a small investment initially. The payoff from a butterfly spread is shown in Table 12.4..  

Suppose that a certain stock is currently worth. $\$61$ . Consider an investor who feels. that a significant price move in the next 6 months is unlikely. Suppose that the market prices of 6-month European calls are as follows:.  

<html><body><table><tr><td>Strike price ($)</td><td>Call price ($)</td></tr><tr><td>55</td><td>10</td></tr><tr><td>60</td><td>7</td></tr><tr><td>65</td><td>5</td></tr></table></body></html>  

The investor could create a butterfly spread by buying one call with a $\$55$ strike price, buying one call with a. $\$65$ strike price, and selling two calls with a. $\$60$ strike price. It. costs $\$10+\$5$ to create the spread. If the stock price in 6 months is. greater than $\$65$ or less than. $\$55$ , the total payoff is zero, and the investor incurs a net. loss of $\$1$ . If the stock price is between. $\$56$ and $\$64$ , a profit is made. The maximum profit, $\$4$ , occurs when the stock price in 6 months is. $\$60$  

Butterfly spreads can be created using put options. The investor buys two European. puts, one with a low strike price and one with a high strike price, and sells two European puts with an intermediate strike price, as illustrated in Figure 12.7. The butterfly spread in the example considered above would be created by buying one put. with a strike price of $\$55$ , another with a strike price of. $\$65$ , and selling two puts with a. strike price of $\$60$ The use of put options results in exactly the same spread as the use of call options. Put-call parity can be used to show that the initial investment is the. same in both cases.  

![](5e101bb5ba3ace351e9c82f032da78e7132d8c428eb58385d99d8b91615da69c.jpg)  
Figure 12.7 Profit from butterfly spread using put options.  

A butterfly spread can be sold or shorted by following the reverse strategy. Options. are sold with strike prices of. $K_{1}$ and $K_{3}$ , and two options with the middle strike price. $K_{2}$ are purchased. This strategy produces a modest profit if there is a significant movement in the stock price.  

# Calendar Spreads  

Up to now we have assumed that the options used to create a spread all expire at the same time. We now move on to consider calendar spreads in which the options have the same strike price and different expiration dates.  

A calendar spread can be created by selling a European call option with a certain strike price and buying a longer-maturity European call option with the same strike. price. The longer the maturity of an option, the more expensive it usually is. A calendar spread therefore usually requires an initial investment. Profit diagrams for calendar spreads are usually produced so that they show the profit when the short-maturity option. expires on the assumption that the long-maturity option is closed out at that time. The. profit pattern for a calendar spread produced from call options is shown in Figure 12.8. The pattern is similar to the profit from the butterfly spread in Figure 12.6. The investor makes a profit if the stock price at the expiration of the short-maturity option is close to. the strike price of the short-maturity option. However, a loss is incurred when the stock. price is significantly above or significantly below this strike price..  

To understand the profit pattern from a calendar spread, first consider what happens. if the stock price is very low when the short-maturity option expires. The short-maturity option is worthless and the value of the long-maturity option is close to zero. The. investor therefore incurs a loss that is close to the cost of setting up the spread initially.. Consider next what happens if the stock price, $S_{T}$ is very high when the short-maturity option expires. The short-maturity option costs the investor. $S_{T}-K$ , and the longmaturity option is worth close to $S_{T}-K$ where $K$ is the strike price of the options. Again, the investor makes a net loss that is close to the cost of setting up the spread initially. If $S_{T}$ is close to $K$ , the short-maturity option costs the investor either a small. amount or nothing at all. However, the long-maturity option is still quite valuable. In this case a net profit is made..  

![](192b0170b4112e1fa0a065a85d197dfdcf4070e1653faa8b22447e8f8934624a.jpg)  
Figure 12.8 Profit from calendar spread created using two call options, calculated at the time when the short-maturity call option expires..  

![](8ad74a505e106403b6ff4671130e4d90090aafc580b9911ac9540aac67da2542.jpg)  
Figure 12.9 Profit from calendar spread created using two put options, calculated at the time when the short-maturity put option expires..  

In a neutral calendar spread, a strike price close to the current stock price is chosen.. A bullish calendar spread involves a higher strike price, whereas a bearish calendar spread involves a lower strike price..  

Calendar spreads can be created with put options as well as call options. The investor buys a long-maturity put option and sells a short-maturity put option. As shown in Figure 12.9, the profit pattern is similar to that obtained from using calls.  

A reverse calendar spread is the opposite to that in Figures 12.8 and 12.9. The investor. buys a short-maturity option and sells a long-maturity option. A small profit arises if. the stock price at the expiration of the short-maturity option is well above or well below. the strike price of the short-maturity option. However, a loss results if it is close to the strike price.  

# Diagonal Spreads  

Bull, bear, and calendar spreads can all be created from a long position in one call and a short position in another call. In the case of bull and bear spreads, the calls have different strike prices and the same expiration date. In the case of calendar spreads, the calls have the same strike price and different expiration dates.  

In a diagonal spread both the expiration date and the strike price of the calls are different. This increases the range of profit patterns that are possible..  
