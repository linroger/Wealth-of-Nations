---
tags:
  - '#butterfly_strategy'
  - '#delta_hedging'
  - '#fx_options'
  - '#implied_volatility'
  - '#option_payoffs'
  - '#static_vs_dynamic_positions'
  - '#straddles'
  - '#strangles'
  - '#volatility_based_strategies'
---
# 11.3 VOLATILITY-BASED STRATEGIES  

The first set of strategies dealt with directional uses of options. Option portfolios combined with the underlying were used to take a view on the direction of the underlying risk. Now we start looking at the use of options from the point of view of volatility positioning. The strategy used in putting together volatility positions in this section is the following: First, we develop a static position that eliminates exposure. to market direction. This can be done using straddles and their cheaper version, strangles. Second, we combine strangle and straddle portfolios to get more complicated volatility positions, and to reduce costs.  

Thus, the basic building blocks of volatility positions considered in this section are straddles. and strangles. The following example indicates how an option position is used to take a view on volatility, rather than the price of the underlying.  

# EXAMPLE  

An Italian bank recommended the following position to a client. We will analyze what this means for the client's expectations [views] on the markets. First we read the episode.  

A bank last week sold $4\%$ out-of-the-money puts and calls on ABC stock, to generate a premium on behalf of an institutional investor. The strangle had a tenor of six weeks.... The strategy generated $2.5\%$ of the equity's spot level in premium.  

At the time of the trade, the stock traded at roughly UsD1874.6. Volatilities were at. $22\%$ when the options were sold. ABC was the underlying, because the investor does not believe the stock will move much over the coming weeks and thus is unlikely to break the range and trigger the options..  

(Based on an article in Derivatives Week (now part of GlobalCapital)  

![](images/a93fc4ac3f99a237898bf9e3a473037328ce8f19f43ec41c9b41b2d499cebb24.jpg)  

# FIGURE 11.11  

Payoff of a strangle position related to ABC stock.  

Figure 11.11 shows the payoff diagram of these option positions at expiration. Adding. the premiums received at the initial point we get the second diagram in the bottom part of. the figure. This should not be confused with the anticipated payoff of the client. Note that the eventual objective of the client is to benefit from volatility realizations. The option position is only a vehicle for doing this..  

We can discuss this in more detail. The second part of Figure 11.11 shows that at expiration, the down and up breakeven points for the position are 1762 and 1987, respectively These are obtained by subtracting and adding the $\$37.5$ received from the strangle position, to the respective strike prices.  

But the reading also gives the implied volatility in the market. From here we can use the square root formula and calculate the implied volatility for the period under consideration  

$$
\sigma S_{t}\cdot\Delta=0.22{\sqrt{\frac{6}{52}}}1874.6=140.09
$$  

Note that the breakeven points are set according to $4\%$ movements toward either side,. whereas the square root formula gives. $7.5\%$ expected movements to either side..  

According to this, the client who takes this position expects the realized volatility to be significantly less than the $7.5\%$ quoted by the market. In fact, the client expects volatility to be somewhat less than $4\%$  

![](images/fc33355a46a92e5fe057105c1e99f66314cb7b1191018111d030db61a3f70655.jpg)  

# FIGURE 11.12  

Typical short strangle's expiration payoff.  

This brings us to a formal discussion of strangles and straddles, which form the main building blocks for classical volatility positions.  

# 11.3.1 STRANGLES  

Assume that we sell (buy) two plain vanilla, European-style options with different strikes on the asset $S_{t}$ The first is a put, and has strike $K_{\mathrm{p}}$ ; the second is a call, and has strike $K_{\mathrm{c}}$ with $K_{\mathrm{p}}<K_{\mathrm{c}}$ Suppose at the time of purchase, we have $K_{\mathrm{p}}<S_{t_{0}}<K_{\mathrm{c}}$ . The expiration date is $T.$ This position dis-e cussed in the previous example is known as a strangle. Because these options are sold, the seller collects a premium, at time $t$ of  

$$
C(t)+P(t)
$$  

The position makes money if, by expiration,. $S_{t}$ has moved by a "moderate" amount, otherwise. the position loses money. Clearly, this way of looking at a strangle suggests that the position is static.. A typical short strangle's expiration payoff is shown in Figure 11.12. The same figure indicates the value of the position at time $t$ when it was initially put in place..  

# 11.3.1.1 Uses of strangles  

The following is an example of the use of strangles from foreign exchange markets. First there is a switch in terminology: Instead of talking about options that are out-of-the-money by. $k\%$ of the strike, the episode uses the terminology "10-delta options." This is the case because, as mentioned earlier, FX markets like to trade 10-delta, 25-delta options, and these will be more liquid than, say,. an arbitrarily selected $k\%$ out-of-the-money option.  

# EXAMPLE  

A bank is recommending its clients to sell 1-month 10-delta euro/dollar strangles to take advantage of low holiday volatility. The strategists said the investors should sell $I$ month strangles with puts struck at USD1.3510 and calls struck at USD1.3610. This will generate a premium of $0.3875\%$ of the notional size. Spot was trading at UsD1.3562 when the trade was designed last week. The bank thinks this is a good time. to put the trade on because implied volatility traditionally falls over Christmas and New Years, which means spot is likely to stay in this range.  

(Based on Derivatives Week (now part of GlobalCapital))  

This is a straightforward use of strangles. According to the strategist, the premium associated with the FX options implies a volatility that is higher than the expected future realized volatility during the holiday season due to seasonal factors. If so, the euro/dollar exchange rate is likely to be range-bound, and the options used to create the strangle will expire unexercised.7  

# 11.3.2 STRADDLE  

A straddle is similar to a strangle, except that the strike prices, $K_{\mathrm{p}}$ and $K_{\mathrm{c}}$ , of the constituent call and put options sold (bought), are identical:.  

$$
K_{\mathrm{p}}=K_{\mathrm{c}}
$$  

Let the underlying asset be. $S_{t},$ and the expiration time be $T$ The expiration payoff and time. value of a long straddle are shown in Figure 11.13. The basic configuration is similar to a long. strangle. One difference is that a straddle will cost more. At the time of purchase, an ATM straddle is more convex than an ATM strangle, and hence has "maximum' gamma..  

# 11.3.2.1 Static or dynamic position?  

It is worthwhile to emphasize that the strangle or straddle positions discussed here are static, in the sense that, once the positions are taken, they are not delta-hedged. However, it is possible to con-. vert them into dynamic strategies. To do this, we would delta-hedge the position dynamically. At initiation, an ATM straddle is automatically market-neutral, and the associated delta is zero. When the price moves up, or down, the delta becomes positive, or negative. Thus, to maintain a market-. neutral position, the hedge needs to be adjusted periodically.  

Note a major difference between the static and dynamic approaches. Suppose we take a static straddle position, and $S_{t}$ fluctuates by small amounts very frequently and never leaves the region $[S_{1},S_{2}]$ shown in Figure 11.14. Then, the static position will lose money, while the dynamic deltahedged position may make money, depending on the size and frequency of oscillations in $S_{t}.$  

![](images/e8d440c6bc8d5094bd4f4001ce1b5a24d509c4846fcfc042a458a78a44c85a95.jpg)  

# FIGURE 11.13  

Expiration payoff and time value of a long straddle.  

![](images/7539f1069858237a65df4f538f15ec1087bfb06ed121c52eac37032c1c2ec3d2.jpg)  

# FIGURE 11.14  

Payoff and net profit from straddle position.  

# 11.3.3 BUTTERFLY  

A butterfly is a position that is built using combinations of strangles and straddles. Following the same idea used throughout the book, once we develop strangle and straddle payoffs as building blocks, we can then combine them to generate further synthetic payoffs. A long butterfly position is shown in Figure 11.15. The figure implies the following contractual equation:  

This equation immediately suggests one objective behind butterflies. By selling the strangle, the trader is, in fact, lowering the cost of buying the straddle. In the case of the short butterfly, the situation is reversed:  

Short butterfly. $=$ Short ATM straddle $+$ Long $k\%$ out-of-the-money strangle  

![](images/5f3128a993b183db5e762f54e47c883b2e74408413560eb10dc83bec9aea4a6d.jpg)  

# FIGURE 11.15  

Long butterfly position.  

A short straddle generates premiums but has an unlimited downside. This may not be acceptable to a risk manager. Hence, the trader buys a strangle to limit these potential losses. But this type of insurance involves costs and the net cash receipts become smaller. The following shows a practical use of the short butterfly strategy.  

# EXAMPLE  

As the Australian dollar continues to strengthen on the back of surging commodity prices, dealers are looking to take advantage of an anticipated lull in the currency's bull run by putting in place butterfly structures. One structure is a 3-month butterfly trade. The dealer sells an ATM Aussie dollar call and put against the US dollar, while buying an Aussie call struck at $A U D O.682$ and buying puts struck at AUD0.6375. The structure can be put in place for a premium of $0.3\%$ of notional, noted one trader, adding that there is value in both the puts and the calls.  

(Based on an article in Derivatives Week (now part of GlobalCapital)  

This structure can also be put in place by making sure that the exposure is vega-neutral.  
