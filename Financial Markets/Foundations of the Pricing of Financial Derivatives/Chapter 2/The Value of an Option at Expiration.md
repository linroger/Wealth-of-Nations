---
tags:
  - '#american_call_options'
  - '#american_put_options'
  - '#arbitrage_opportunities'
  - '#dividends_impact'
  - '#european_call_options'
  - '#european_put_options'
  - '#exercise_value'
  - '#option_expiration'
  - '#option_lower_bounds'
  - '#option_pricing_model'
---
# 2.4 THE VALUE OF AN OPTION AT EXPIRATION

The value of an option when it is exercised is called the exercise value. At expiration, both a European and an American call are worth their exercise values, which is the same for both, because the American call has no time remaining and, therefore, no benefit to exercising it early,

$$
c_{T}=C_{T}=\operatorname*{max}(0,S_{T}-X).
$$

To exercise the option, the holder will pay. $X$ and will receive an asset worth. $S_{T}$ .Thus, if $S_{T}>X$ and an instant before expiration the call is selling for less than $S_{T}-X$ , it can be purchased and exercised, resulting in an immediate gain to the holder of. $S_{T}-X$ less the price of the call. The ability to earn this risk-free profit will induce trading of this sort that will result in the call price increasing in value until it is equal to $S_{T}-X.$ If $S_{T}\leq X$ the option should not be exercised and, hence, it expires with no value.

Similarly, at expiration both a European and an American put are worth the exercise value,

$$
\begin{array}{r}{\dot{p}_{T}={P}_{T}=\operatorname*{max}(0,X-S_{T}).}\end{array}
$$

To exercise the put, the holder will need to acquire the underlying, which can be done an instant before expiration either by buying it in the open market at. $S_{T}$ or by simply short selling it. If the put holder exercises the put, the holder can purchase shares at $S_{T}$ and subsequently sell them at. $X$ .Thus, if $S_{T}<X$ and the put is selling for less than. $X-S_{T}$ , it can be purchased and exercised resulting in an immediate gain to the holder of $X-S_{T}$ less the price of the put. The ability to earn this risk-free profit will induce trading of this sort that will result in the put price increasing in value until it is equal to. $X-S_{T}$ If $S_{T}>X$ , the option should not be exercised and, hence, it expires with no value.5.

Alternatively, suppose the stock is trading at 90 and a 100-strike put is trading for 11 on the expiration date. In this case, the market put price is too high relative to the exercise value (10). The arbitrageur should sell the put receiving 11. The put buyer will exercise this option. As the seller, the arbitrageur will have to buy the stock at the strike price of 100 and subsequently sell it in the market at 90 for a loss of 10. The proceeds from selling the put more than offset this loss, netting 1.

# 2.5THE LOWER BOUNDS OF EUROPEAN AND AMERICAN OPTIONS AND THE OPTIMALITY OF EARLY EXERCISE

We previously identified zero as the minimum values of European and American options.
It is possible, however, to establish higher minima. By establishing a minimum price that.
is higher than zero, we are able to place more restrictive limits on the prices of options,.
which enables us to narrow the range over which the option price can exist..

# 2.5.1 The Lower Bound of a Call

For an American call, the lower bound can be initially stated as the option's exercise value. At any time $t<T$

$$
C_{t}\geq\operatorname*{max}(0,S_{t}-X).
$$

If $S_{t}>X$ and the call is selling for less than $S_{t}-X.$ it can be purchased and exercised resulting in an immediate gain to the holder of $S_{t}-X$ less the price of the call. The ability to earn this risk-free profit will induce trading of this sort that will result in the call price increasing in value until it is worth at least $S_{t}-X.$ In the other case, $S_{t}<X$ , the option should not be exercised and, hence, we can say only that its minimum value is zero.

For a European call, such a statement is not possible because it cannot be exercised. immediately. It is possible, however, to make a stronger statement, via simple arbitrage. arguments. Suppose we construct two portfolios, A and B, with portfolio A consisting of a long position in a European call, and a zero-coupon bond with face value equal to the. exercise price, and current value equal to the present value of the exercise price. Portfolio B consists of a unit of the asset. Table 2.1 shows the current values of these portfolios and. their values at expiration.

TABLE 2.1 Establishing a Lower Bound for a European Call


<html><body><table><tr><td rowspan="2"></td><td rowspan="2"></td><td colspan="2">Value at Expiration</td></tr><tr><td>XS</td><td>X<ST</td></tr><tr><td>Portfolio A</td><td></td><td></td><td></td></tr><tr><td>European call</td><td>Ct</td><td>0</td><td>Sr -X</td></tr><tr><td>Zero-coupon bond</td><td>Xe-rct</td><td>X</td><td>X</td></tr><tr><td>Total</td><td>2²-X+</td><td>X</td><td>ST</td></tr><tr><td>Portfolio B</td><td></td><td></td><td></td></tr><tr><td>Asset</td><td>St</td><td>ST</td><td>ST</td></tr></table></body></html>

Note that Portfolio A performs as well as Portfolio B when $S_{T}>X$ (because the Xs cancel) and performs better when $S_{T}\leq X$ Thus, portfolio A is said to dominate Portfolio B. Consequently, the current value of A must be at least as great as the current value of B, which can be stated as $c_{t}+X e^{-r_{c}\tau}{\ge}S_{t}$ . Rearranging, we can write this statement as $c_{t}\geq S_{t}-X e^{-r_{c}\tau}$ For the case where $c_{t}<S_{t}-X e^{-r_{c}\tau}$ and $S_{t}<X e^{-r_{c}\tau}$ , however, it makes little sense to state that a call price must exceed some negative value for we already know that its absolute minimum is zero. Consequently, we can state formally that

$$
c_{t}\geq\operatorname*{max}(0,S_{t}-X e^{-r_{c}\tau}).
$$

For an American call, we previously noted that. $C_{t}\geq\operatorname*{max}(0,S_{t}-X)$ . It is obvious, however, that $S_{t}-X e^{-r_{c}\tau}$ is greater than $S_{t}-X$ except at the expiration where $\tau=0$ 6. Combined with the fact that the American call price is at least as great as the European. call price, we can then state that the lower bound for the European call must also hold for the American call,

$$
C_{t}\geq\operatorname*{max}(0,S_{t}-X e^{-r_{c}\tau}).
$$

To better understand how arbitrage activity influences option prices, consider the following situation: Suppose the stock price is $S_{t}=102$ , the strike price is $X=100$ , the continuously compounded risk-free interest rate is $r_{c}=5.01\%$ , the time to maturity $\tau$ is 0.608 based on its expiration in 222 days $(222/365=0.608)$ , and the quoted American call price is 4.95. How would an arbitrageur trade? The first step is to assess whether there is a boundary violation. Note in this casee $S_{t}-X e^{-r_{c}\tau}=102-1\bar{0}0e^{-0.0501(222/365)}=5.0.$ Thus, the quoted call price is 0.05 below the lower boundary. The arbitrageur seeks to pocket this 0.05 through a series of current trades. Note in this case $S_{t}-X e^{-r_{c}\tau}-C_{t}=0.05$ and the trading strategy is embedded in this expression. Notice that you can generate this result by transactions that generate these specific cash flows; namely, short sell the stock at $S_{t}=102$ buy a zero-coupon bond at $X e^{-r_{c}\tau}=97\$ , and buy the call at. $\mathrm{C}_{t}=4.95$ . Table 2.2 provides a cash flow table that clearly demonstrates that these transactions result in arbitrage profits today with no subsequent chance for future negative cash flows.

The Cash Flow Today column results in the receipt of 0.05 today per share of stock. The column ${\mathit{S}}_{T}\leq X$ is known to be nonnegative because we assumed the terminal stock price is less than or equal to the strike price.

Note that short selling pressure will drive the stock price down, and call buying pres-. sure will drive the call price up. In well-functioning markets, we expect the net cash flow today to quickly move so as to be nonpositive. Also, remember the arbitrageur purchased the American call; hence, they do not have to be concerned with being forced to exercise early. Therefore, the early exercise feature cannot be harmful to the arbitrage trader.

IABLE 2.2 Numerical Illustration Establishing a Lower Bound for a European Call


<html><body><table><tr><td rowspan="2"></td><td rowspan="2"></td><td colspan="2">Cash Flow atExpiration</td></tr><tr><td>Sr ≤X</td><td>ST</td></tr><tr><td>Shortsellstock</td><td>+S, = 102</td><td>-ST</td><td>-ST</td></tr><tr><td>Buy bond</td><td>-Xe-rc=-97</td><td>X+</td><td>+X</td></tr><tr><td>Buy call</td><td>-Ct =-4.95</td><td>0</td><td>ST-X</td></tr><tr><td>Net</td><td>0.05</td><td>100-St</td><td>0</td></tr></table></body></html>

![](images/661685096385f68af16b143bc1de3d8b925644e7c706b1ee13a8e4adc7e87609.jpg)
FGURE 2.1Illustration of Lower Bound for a Non-Dividend-Paying Call(Expressed as Percentage)

Figure 2.1 illustrates what we have asserted thus far. As is common in industry practice,. the strike price, call price, and lower bound are normalized by the underlying price. That is, these values are divided by the underlying price. By normalizing values, we can easily. compare option information across different instruments. Thus, the call mid price is the average of the bid and ask call price for an American call option on an index ETF (266.86) on the last trading day of a recent year divided by the index ETF price. This anecdote shows with actual data that the call price remains above the lower bound. Also, note that for calls, the exercise value is below the lower bound. As such, the exercise value is not binding in real markets. Specifically, the higher lower bound is binding and nothing else.

The market risk-free interest rate is $1.6\%$ , the time to maturity is 49 days, and there are no anticipated dividends. Please note that these graphs look the opposite of what you may have seen before: Here we normalize by the underlying price. The opposite image would appear if normalizing by the strike.

# 2.5.2 Early Exercise of an American Call

From this result, we can discern that the American call will never be exercised early because the minimum value of an in-the-money call is. $S_{t}-X e^{-r_{c}\tau}$ , which is more than its value if. exercised, $S_{t}-X.$ In other words, an American call is worth more by simply selling this call in the market. This point may seem somewhat counterintuitive when one considers that a deep-in-the-money call might seem worth exercising. A holder of such a call might be unlikely to expect further gains, but one must consider that exercise of such a call would simply result in the holder possessing the asset. If the asset is indeed going no higher, it would satisfy the holder no more to hold it instead of the call and would be out the exercise price and the interest it could continue to earn if they waited until expiration to exercise. It should also be apparent that exercise of a call early is equivalent to simply paying someone for an asset before it is necessary and then forgoing the right to change one's mind about its purchase at a later date. We shall soon see, however, that if the asset makes cash payments, then it may be worth exercising early..

Thus, for the case where the asset makes no cash payments, the absence of early exercise will render the American and European calls equivalent in value:

$c_{t}=\mathrm{C}_{t}$ if there are no dividends or cash payments on the underlying.

Now let us assume that the asset makes cash payments, such as dividends on a stock, over the life of the option that have a present value of. $D_{t}$ . To derive the lower bound, it is necessary that we change the current value of the bond from. $X e^{-r_{c}\tau}$ to $X e^{-r_{c}\tau}+D_{t}$ . The bonds will, thus, have a current value of. $X+D_{t}e^{r_{c}\tau}$ at expiration in either case. Portfolio B, the asset, will have a value of $S_{T}+D_{t}e^{r_{c}\tau}$ in either case at expiration, which reflects the. accumulation and reinvestment of the dividends. It should be apparent that Portfolio A is still dominant but the slight change in the composition of A leaves us with the following. lower bound,

$$
c_{t}\geq M a x(0,S_{t}-D_{t}-X e^{-r_{c}\tau}).
$$

Unlike the case of no dividends, we now see that the lower bound of a European call can be less than $S_{t}-X$ , the exercise value of the American call. This case would occur if. $X(1-e^{-r_{c}\tau})<D_{t}$ , meaning that the interest on the exercise price is less than the present. value of the dividends. That is,.

$$
\begin{array}{r l}&{S_{t}-X e^{-r_{c}\tau}-D_{t}<S_{t}-X}\ &{~X-X e^{-r_{c}\tau}<D_{t}}\ &{~X(1-e^{-r_{c}\tau})<D_{t}.}\end{array}
$$

In such a case, we cannot state an equivalence of the European and American call prices. In the case where the inequality is reversed, however, we have a sufficient condition for

no early exercise of the American call and such a call would be priced as a European call. That is,

$$
\begin{array}{r l}&{S_{t}-X e^{-r_{c}\tau}-D_{t}>S_{t}-X}\ &{~X-X e^{-r_{c}\tau}>D_{t}}\ &{~X(1-e^{-r_{c}\tau})>D_{t}.}\end{array}
$$

So, if the interest on the exercise price is more than the present value of the dividends, then there is absolutely no reason to exercise the call early. This leads to the condition,.

$$
C_{t}=c_{t}\operatorname{if}X(1-e^{-r_{c}\tau})>D_{t}.
$$

The American call clearly has a positive probability of early exercise except in this special case of sufficiently small dividends relative to the present value of the exercise price. This result establishes the fact that it may be optimal to exercise an American call early to capture a dividend. When the call is exercised early, the holder throws away the time value and claims the exercise value. To avoid throwing away any more time value than necessary, however, it is always optimal to exercise only at the last instant before the asset goes ex-dividend. Also, note that if the condition in Equation (2.11) is not met, it does not automatically imply that the option will be exercised early.

Figure $2.2{\a}^{}{\mathrm{a}}$ illustrates the influence of actual dividends on the call lower bound. Recall in Figure 2.1 that the exercise value is less than the lower bound for a 49-day call option. For this longer dated option, there are two future quarterly dividends before this 203-day option expires. The present value of these dividends was estimated to be 2.326, based on a market risk-free interest rate of. $1.79\%$ . Thus, the present value factor is 0.990094 or. $e^{-r_{c}\tau}{=}e^{-0.0179(203/365)}=0.990094$ . Based on Equation (2.11), $X(1-e^{-r_{c}\tau})=D_{t}$ at $88\%$ of the underlying value or $[2.326/(1-0.990094)]/266.86.$ As shown in Figure 2.2b, the exercise value is higher than the lower bound for strike prices below. $88\%$ of the underlying price. The observed call prices appear to be converging to the call exercise value for lower strike prices, which are deep in-the-money calls..

![](images/bf07603b20a7275680379c3f093d07bd0fc1d3259a4beefa62dba34c9665945f.jpg)
FIGURE 2.2a Illustration of Dividend Impact on Call Lower Bound (Expressed as Percentage)

![](images/2889be062a82151c221197f0832329bf54e1ee07a527ba99dc855866640c4f87.jpg)
FIGURE 2.2b Call Lower Bound Less Call Exercise Value

TABLE 2.3 Establishing a Lower Bound for a European Put


<html><body><table><tr><td></td><td></td><td colspan="2">Value atExpiration</td></tr><tr><td>Instrument</td><td>CurrentValue</td><td>Xs</td><td>ST</td></tr><tr><td>Portfolio E</td><td></td><td></td><td></td></tr><tr><td>European put</td><td>Pt</td><td>X-ST</td><td>0</td></tr><tr><td>Asset</td><td>'s</td><td>ST</td><td>ST</td></tr><tr><td>Total</td><td>Pt+ St</td><td>X</td><td>ST</td></tr><tr><td>Portfolio F</td><td></td><td></td><td></td></tr><tr><td>Zero-coupon bond</td><td>2²-X</td><td>X</td><td>X</td></tr></table></body></html>

# 2.5.3 The Lower Bound of a Put

Now we look at the lower bound of a European put. First, we consider the case of no dividends. We construct Portfolio E, consisting of a European put and a unit of the asset, and Portfolio F, consisting of a zero-coupon bond with face value $X$ and current value of $X e^{-r_{c}\tau}$ .7 Table 2.3 shows the outcomes.

Portfolio E clearly dominates Portfolio F, matching its outcome in one case and beating it in the other. Thus, the current value of Portfolio E must be no less than the current value of Portfolio F, giving us $p_{t}+S_{t}\geq X e^{-r_{c}\tau}$ . Rewriting this expression to isolate the put and noting that a negative lower bound is dominated by a lower bound of zero gives

$$
\begin{array}{r}{p_{t}\geq\operatorname*{max}(0,X e^{-r_{c}\tau}-S_{t}).}\end{array}
$$

For an American put, however, the lower bound is still $\operatorname*{max}(0,X-S_{t})$ because this value exceeds the European lower bound. Consequently,

$$
P_{t}\geq\operatorname*{max}(0,X-S_{t}).
$$

Recall that if. $S_{t}<X$ the put is in-the-money, if. $S_{t}>X$ the put is out-of-the-money, and if $S_{t}=X$ the put is at-the-money..

Figure 2.3 illustrates the results for an American put option. We again normalize values by the underlying price. With this actual data, we observe that the put bid price remains above the exercise value. Remember for calls, the exercise value is below the lower bound. This is not true for puts. As such, the exercise value is binding in real markets due to arbitrage activity.

For the case of a European put on an asset that makes cash payments, such as a dividend-paying stock, we modify portfolio F so that its bond has a face value of $X e^{-r_{c}\tau}+D_{t}$ This makes its payoff be. $X+D_{t}e^{r_{c}\tau}$ . Then the payoff of portfolio E will include. $D_{t}e^{r_{c}\tau}$ Thus, Portfolio E is still dominant, but the resulting boundary now becomes

$$
p_{t}\geq\operatorname*{max}(0,X e^{-r_{c}\tau}+D_{t}-S_{t}).
$$

![](images/08a44e9f1b02ae51a2d57b65306c115bcfb38f2480c54853fbb7248b4fe8acac.jpg)
FGURe 2.3 Illustration of Lower Bound for a Non-Dividend-Paying Put (Expressed as Percentage)

The plus sign on the dividends implies that they have a positive effect on put options, which is easy to rationalize. When a firm pays a dividend, it reduces its ability to grow, which is harmful to holders of calls, who benefit only from growth in the asset, but the dividend benefits holders of puts who gain from less growth, which keeps the stock price down.

Consider the following situation similar to the previous example: Suppose the stock price has fallen and now is $S_{t}=97.93$ , the strike price is. $X=100$ , the risk-free interest. rate is $r_{c}=5.01\%$ continuously compounded, annualized, the time to maturity is 0.608 (or more precisely 222 days in a 365-day year), and the quoted European put price is 0.95. Now, however, there is one anticipated dividend in 111 days of $D_{t D}=1.96$ where the appropriate risk-free interest rate for this dividend is $4.17\%$ . How would an arbitrageur trade? The first step is to assess whether there is a boundary violation. Note in this case the value of the lower bound can be computed as

$$
\begin{array}{c}{{X e^{-r_{c}\tau}+D_{t}-S_{t}=100e^{-0.0501(222/365)}+1.96e^{-0.0417(111/365)}-97.93}}\ {{{}}}\ {{=97+1.93-97.93=1.0.}}\end{array}
$$

Thus, the quoted put price of 0.95 is below the lower boundary. The arbitrageur seeks to pocket this 0.05 through a series of current trades. Note in this case $X e^{-r_{c}\tau}+D_{t}-S_{t}-c_{t}=$ 0.05 and the trading strategy is embedded in this expression. Notice that you can generate this result by executing transactions that produce these specific cash flows, namely, short sell the zero-coupon bond. $(X e^{-r_{c}\tau}+D_{t}=98.93)\$ , buy stock $(S_{t}=97.93\$ , and buy the put $(-\ensuremath{p_{t}}=-0.95)$ . Table 2.4 clearly demonstrates that these transactions result in arbitrage. profits today with no subsequent chance for future negative cash flows.

Note in Table 2.4 that the net cash flow today is 0.05. The positive cash flow on the dividend date from the stock is captured today through short selling a bond or borrowing. Finally, the net cash flow when $S_{T}>X$ is positive because we know $S_{T}>100$ by assumption. Further note that buying pressure will drive the stock and put price up. Again, in well-functioning markets, we expect the net cash flow today to quickly move so as to be nonpositive.

# 2.5.4 Early Exercise of an American Put

The lower bound dominance in the case of an American call, where $S_{t}-X e^{-r_{c}\tau}>S_{t}-X$ provided a simple condition under which we demonstrated that an American call will not be exercised early except in the event of a dividend. For an American put, it is sufficient to demonstrate that the case of an asset price falling to zero will trigger early exercise. The holder of the put will gain no more by waiting because the asset can go down no further, nor can it ever attain a positive value again. It is not true, however, that the holder must wait until the asset falls to zero. The exact point of early exercise is a complex matter to determine, and we do not cover it in this chapter. We shall see under what conditions American puts are exercised early after we have developed a full pricing model.

IABLE 2.4 Establishing a Lower Bound for a European Put


<html><body><table><tr><td rowspan="2">Instrument</td><td rowspan="2">CashFlowToday</td><td rowspan="2">CashFlow at Dividend Date</td><td colspan="2">Cash Flow at Expiration</td></tr><tr><td>Sr≤X</td><td>X<ST</td></tr><tr><td>Shortsellbond</td><td>Xe-rc+Dt</td><td>-DtD = -1.96</td><td>-X=-100</td><td>-X=-100</td></tr><tr><td></td><td>= 98.93</td><td></td><td></td><td></td></tr><tr><td>Buy stock</td><td>-Sr =-97.93</td><td>+DtD = 1.96</td><td>+ST</td><td>+ST</td></tr><tr><td>Buy put</td><td>-pt=-0.95</td><td>0</td><td>X-ST</td><td>0</td></tr><tr><td>Net</td><td>0.05</td><td>0</td><td>0</td><td>Sr -100</td></tr></table></body></html>

If the put were American, the existence of dividends paid by the stock renders it less likely to be exercised early. An American put can clearly be sold for at least its minimum European value of $X e^{-r_{c}\tau}+D_{t}-S_{t}$ or exercised for $X-S_{t}$ . If $D_{t}\geq X(1-e^{-r_{c}\tau})$ , then it cannot be worth more to exercise it. Clearly, high dividends make a put more attractive alive than exercised. If it is, however, optimal to exercise a put early, it will be done immediately after the asset goes ex-dividend. One might as well wait an instant to let the stock price drop before exercising the put..

In summary, the lower bound for an American put has three conditions as illustrated in the following expression,.

$$
P_{t}\ge\operatorname*{max}(0,X-S_{t},X e^{-r_{c}\tau}+D_{t}-S_{t}).
$$

Clearly, as time passes, the present value of the strike price and dividends increase until an ex-dividend date. On that date, the stock price typically falls by the dividend amount and the present value of the dividends also falls by the dollar dividend paid. Thus, a dividend payment generally has no significant impact on the third condition $(X e^{-r_{c}\tau}+D_{t}-S_{t})$ but the second condition increases with the drop in stock price $(X-S_{t})$

Prior to expiration, both American put and call option prices will exceed the exercise. values because sellers of the options will bear the risk that the options will be worth substantially more than their current exercise values by the time expiration has arrived. The option price, thus, is said to consist of two components: the exercise value and the time. value, the latter reflecting the premium that disappears as expiration nears. The full price of the option--the exercise value plus the time value--is the objective of developing anoption pricing model, a topic to which much of this book is devoted..

Figure 2.4 illustrates the influence of dividends on the put lower bound. Recall in. Figure 2.3 that the exercise value is higher than the lower bound for a 49-day put option. Recall from Figure 2.2 that this longer dated option has two future quarterly dividends with present value 2.326. Clearly the exercise value and lower bound are much closer together due to the influence of dividends..
