---
tags:
  - '#black_scholes_model'
  - '#digital_options'
  - '#exotic_options'
  - '#fx_markets'
  - '#hedging_strategies'
  - '#knock_out_call'
  - '#option_delta'
  - '#option_pricing'
  - '#risk_reversal'
  - '#volatility_smile'
---
# 16.17 EXOTIC OPTIONS AND THE SMILE  

The second major category of instruments where the existence of the volatility smile can change pricing and hedging practices significantly is exotic options. In this section, we consider a simple knock-out call that is representative of the main ideas we want to convey. Due to the contractual equation between vanilla options, knock-out calls, and knock-in calls, our discussion immediately extends to knock-in calls as well. At the end of this section, we briefly discuss digital options and how the existence of the volatility smile affects them.  

# 16.17.1 A HEDGE FOR A BARRIER  

Knock-out calls were discussed in Chapters 9 and 11. As a reminder, a simple knock-out call is similar to a European vanilla call with strike $K$ and expiration $T_{:}$ written on the underlying $S_{t},$ except that the option will cease to exist if, during the life of the option, $S_{t}$ falls below barrier $H$  

$$
S_{t}<H\quad t\in[t_{0},T]
$$  

The price of a knock-out barrier approaches the price of a vanilla call as the option becomes more in-the-money. However, as the underlying approaches the barrier, the value of the knock-out will approach zero.  

There are several ways of hedging knock-out options used by practitioners. Here, we explain a hedge that (i) has nice financial engineering implications and (ii) shows clearly the important role played by the smile.  

Suppose we bought the corresponding vanilla call and sold a carefully chosen out-of-the money vanilla put with strike $K^{*}$ $K^{*}<K_{\sun}$ with a very precise objective. We want the put and the call to be. such that, as $S_{t}$ approaches the barrier $H$ the portfolio's value becomes zero. This portfolio, which is, in fact, a type of risk reversal, approximately replicates the knock-out option. If. $S_{t}$ moves away from $H_{:}$ the put becomes more out-of-the-money, and its value will decline. Then the portfolio looks more and more like a vanilla call. This is what the knock-out option accomplishes anyway. On the other hand, as $S_{t}$ approaches $H$ , the put becomes more valuable. If it is carefully chosen, at $H$ the value of the put position can equal the value of the vanilla call and the portfolio would have zero value. This is, again, what the knock-out option accomplishes near $H.$ As $S_{t}$ falls below $H.$ the portfolio has to be liquidated. Thus, the portfolio of  

$$
K^{*}-\mathrm{Put},\mathrm{Longone}K{\cdot}\mathrm{Call}\}
$$  

replicates the knock-out call if. $x$ and $K^{*}$ are appropriately selected. One way to do this is to use the "symmetry" principle.  

Suppose there is no smile effect and that all options with different strikes that belong to a series have the same volatility. Then we can choose $x$ and $K^{*}$ as follows. We want the value of $x$ units of. the $K^{*}$ put to equal the value of the vanilla call when $H{\gets}S_{t}$ . This can be achieved by choosing. $K^{*}$ such that  

$$
K^{*}\cdot K=H^{2}
$$  

The prices of these options are assumed to satisfy  

$$
{\frac{K^{*}\operatorname{put}}{K\operatorname{call}}}={\sqrt{\frac{K^{*}}{K}}}
$$  

This means that if $x$ is chosen so that  

$$
x=\frac{K}{K^{*}}
$$  

then the value of $x$ units of these $K^{*}$ puts would equal the value of the $K$ call as $S_{t}$ approaches $H.$ As a result, the portfolio would replicate the knock-out call, except that once the barrier is hit, the portfolio needs to be liquidated.  

# 16.17.2 EFFECTS OF THE SMILE  

Consider first the effect of a stable volatility smile on this procedure. If the smile does not shift over time, then it is easy to incorporate the effect into the previous replicating portfolio. Suppose. the smile is downward sloping over. $[K^{*},K]$ . Then, one could plug different volatility parameters in. Black-Scholes formulas for each vanilla option. The same. $K^{*}$ put selected earlier would be relatively more valuable than in the case of a flat smile. This means that the knockout option could be. sold at a cheaper price. If the smile was upward sloping over the range, then the reverse would be true and the knockout would be more expensive. Hence, the smile has a direct effect that needs to. be taken into account in the pricing and hedging of the knockout..  

There is a second effect of the smile as well. Suppose the smile is not stable during the life of the option, and that it shifts as time passes. Then the logic of replication would fall apart since a smile that shifts over time would make the relative values of the call and the put differ from the originally intended ratio as $S_{t}$ approaches $H.$ Given that in most markets the smile is unstable over time, the hedging technique by this replication is questionable. The pricing of the knock-out would also be unreliable.  

# 16.17.2.1 An example of technical difficulties  

We can look at the complications introduced by the volatility smile using knock-out pricing formulas in case all standard assumptions are satisfied. The pricing formula for knock-outs was given in Chapter 9. In particular, the price of a down-and-out call written on a stock $S_{t},$ satisfying all standard assumptions, and paying no dividends, was given by  

$$
C^{b}(t)=C(t)-J(t)
$$  

where $C(t)$ is the value of a vanilla call, given by the standard Black-Scholes formula, and where $J(t)$ is the "discount' that needs to be applied because the option may die if $S_{t}$ falls below $H$ during the life of the contract. The formula for $J(t)$ was  

$$
J(t)=S_{t}\left(\frac{H}{S_{t}}\right)^{(2(r-(1/2)\sigma^{2})/\sigma^{2})+2}N(c_{1})-K e^{-r(T-t)}\left(\frac{H}{S_{t}}\right)^{2(r-(1/2)\sigma^{2})/\sigma^{2}}N(c_{2})
$$  

where  

$$
c_{1,2}={\frac{\log(H^{2}/S_{t}K)+(r\pm{\frac{1}{2}}\sigma^{2})(T-t)}{\sigma{\sqrt{T-t}}}}
$$  

Note that just like the Black-Scholes formula, this pricing function contains a single volatility parameter $\sigma$ . In the plain vanilla case, this parameter could be manipulated to make the formula yield the correct answer, even when the underlying assumptions do not hold. Thus, in a smile environment with nonconstant volatilities, the trader could use one value for volatility and make the formula yield the correct answer. In fact, this was used in pricing caps and floors even though the volatilities of the individual forward rates that are relevant to these instruments were different.  

Unfortunately, this approach is not guaranteed to work for the down-and-out call pricing formula given here if a volatility smile exists and if this smile is continuously (and stochastically) shifting over time. In fact, there may not be a single well-behaved volatility value to replace in Eq. (16.94) to obtain the correct price of the down-and-out call. Even when the realized and ATM implied volatilities remain the same, if the slope of the smile changes, the price of the down-andout call may change as in the previous argument. In fact, if the smile becomes less negatively. sloped, the short put component of the replicating portfolio will become relatively less expensive and the value of the down-and-out call may increase. Hence, in the case of exotic options, the relationship between volatility adjustments and the correct option price may become much more complex as smile effects become significant.  

# 16.17.2.2 Pricing exotics  

Actual trading takes place in the presence of a volatility smile, and the prices of exotic options need to be set so as to take into account the future costs and benefits of adjusting the hedge to the exotic option. With the presence of smile, as time passes, the vega hedge of an exotic option book needs to be adjusted for the reasons explained earlier. As this happens, depending on the net position of the option book, the trader may realize some net cash gains or losses. The present value of these "expected" cash gains and losses needs to be incorporated into the market price. At the end, the market price of the exotic may be higher or lower than the theoretical price indicated by. Eq. (16.94).  

# 16.17.3 THE CASE OF DIGITAL OPTIONS  

Chapter 11 showed that a theoretical replication of a European digital call with strike $K$ and expiration $T$ would be to buy $1/h$ units of the vanilla call with strike $K$ and to sell $1/h$ units of the vanilla call with strike $K+h$ In this case $h$ would be the minimum tick in a futures market.  

If there is a volatility smile, then the prices of these vanilla calls would need to be adjusted since they have different strikes and, therefore, different volatilities. Of course, if. $h$ is small, this volatility difference would be small as well, but then. $1/h$ would be large and the position would. involve buying and selling a large number of vanilla calls. With such numbers, small variations in volatilities can make a difference to the end result.6  

# 16.17.4 ANOTHER APPLICATION: RISK REVERSALS  

One of the most liquid ways of trading the smile is using risk reversals from FX markets. Consider options written on an exchange rate $e_{t}.$ Fix the expiration at $T.$ and arrange the puts and calls by their strike price $K_{i}.$ Then calculate these options' deltas and consider a grid of reasonable deltas. We use the options' deltas to represent the moneyness.  

A typical smile for these exchange rate options will then look like the one shown in. Figure 16.13. It is a "symmetric" curve and is plotted in a two-dimensional graph having the percentage volatility on the vertical axis and the option's delta on the. $x\cdot$ -axis. In particular, consider the 25, 50, and 75-delta options.17  

We look at the following example.  

# EXAMPLE  

Activity in the dollar/yen foreign exchange markets over the past fortnight has emphasized the severe complexities associated with pricing exotic options. More importantly, it has provided sophisticated option houses with an opportunity to test their pricing theories against each other and against their less-advanced competitors. ..  

However, it was not the decline in the spot rate itself that provided the interest for options dealers but the resulting risk-reversal position. Risk-reversal is an expression of the directional preference in the market. If spot is expected to fall, as in the case of dollar/yen, then there will be greater demand for puts relative to calls, and so the volatility trader will pay a higher price for the puts than the calls. The upshot of this, said one commentator, is that volatility is not constant, as assumed by the standard Black-Scholes option-pricing model, but instead changes according to the option delta.  

One-month dollar/yen risk reversal shot up to nearly 3 last week and has continued to hover at levels not seen since the summer of 1995. This extraordinary situation enabled sophisticated traders to find value in the pricing of their so-called naive counterparts..  

"A lot of banks must have learned a lot about risk-reversal over the past few days," said one trader.. According to market insiders, the less advanced houses failed to adequately account for the effects of riskreversal in pricing and hedging exotic structures such as knock-out and path-dependent options..  

They also asserted that simple off-the-shelf option pricing software was unable to cope with pricing. exotic derivatives in a risk-reversal scenario. These packages did not allow the user to enter different volatilities for different deltas and so failed to capture the nuances of exotics pricing.. However, other commentators argued that this too was an over-simplification and that other "thirdorder" effects came into play when hedging certain types of options in very high risk-reversal scenarios.. They added that the third-order effects meant the barrier described might not be overpriced by the Black-Scholes user, merely mispriced.  

(Thomson Reuters IFR Issue 1188, June 1997)  

As this reading illustrates, risk reversals are creations of the volatility smile in FX markets. and are heavily traded. But, as indicated in the reading, market practitioners involved in riskreversal trading are clearly dealing with the underlying smile dynamics. The dynamics can become very complex. Pricing and hedging such positions on exotic options may become much. more difficult.  
