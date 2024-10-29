---
title: Options
---

# Options

These notes describe the payoffs to European and American put and call options—the so-called plain vanilla options. We consider the payoffs to these options for holders and writers and describe both the time vale and intrinsic value of an option. We explain why options are traded and examine some of the properties of put and call option prices. We shall show that longer dated options typically have higher prices and that call prices are higher when the strike price is lower and that put prices are higher when the strike price is higher.

Keywords: Put,  call,  strike price,  maturity date,  in-the-money,  time value intrinsic value,  parity value,  American option,  European option,  early exercise,  bull spread,  bear spread,  butterfly spread.

# 1 Options

Options are derivative assets. That is their payoffs are derived from the payoff on some other underlying asset. The underlying asset may be an equity,  an index,  a bond or indeed any other type of asset. Options themselves are classified by their type,  class and their series. The most important distinction of types is between put options and call options. A put option gives the owner the right to sell the underlying asset at specified dates at a specified price. A call option gives the owner the right to buy at specified dates at a specified price. Options are different from forward/futures contracts as a put (call) option gives the owner right to sell (buy) the underlying asset but not an obligation. The right to buy or sell need not be exercised. There is also a last date on which the right may be exercised and this is known as the expiration date or maturity date. The specified price is called the strike price or exercise price.

The most commonly traded option is the American type which may be exercised at any trading date prior to or at the expiration date. There are also options of the European type which may only be exercised at the expiration date. Thus an American put and a European put are different types of option. Another type is the Bermudan option which is half way between the European and American option as it can only be exercised on a limited number of pre-specified days prior to maturity. We shall focus mainly on European options as there is an important parity condition between the prices of European put and call options and we shall explain how the prices of American options differ from their European counterparts.

The owner or buyer of an option is often called the holder and the seller of an option is termed the writer. Thus at date of sale the holder pays the writer the price of the option. For a call option there may be a subsequent transaction at the expiration date where the writer provides the underlying asset to the holder in exchange for the agreed strike price. This subsequent transaction is made at the instigation of the holder and will only be undertaken if it is in the holder's interest. The holder's right to buy the stock at or prior to the expiration date need not be exercised. For a put option,  the subsequent transaction is that the holder provides the underlying asset in return for the agreed strike price from the writer.

The difference between American and European options is simply what choices the holder has prior to the expiration date. The holder of the Euro pean option has,  at any point prior to the expiration date,  the choice either to sell the option for the prevailing market price or to retain it. The holder of an American option has,  at any point prior to the expiration date,  three choices: either to sell the option for the prevailing market price,  to retain it or to exercise it. The later case is said to involve early exercise. This terminology is not meant to imply that there is anything sub-optimal about

Exercising before the expiration date. Indeed we will give below examples where the American option will be exercised early

A class of option is all options of a particular type on the same underlying asset. Thus all American put options on IBM stock form one class. European call options on the FTSE 100 index form another class. A class will involve a variety of different strike prices and maturity dates. Most options are exchange traded and the exchange will specify a range of maturity dates,  usually every two months,  and a range of strike prices,  usually centered around the prevailing market price. An option series is simply the options of a given class with the same strike price and maturity date.

### Payoff at Maturity

Let $X$ be the exercise price and $S_{T}$ the price of the underlying stock at the maturity date. Then the payoff to a put option is

$$p_T=\left\{\begin{array}{ll}X-S_T&\text{if}S_T\leq X\\0&\text{if}S_T>X.\end{array}\right.$$

or more simply $p_{T}=\operatorname*{max}[X-S_{T},      0]$ .If $S_{T}<X$，then the put is said to finish in-the-money and the option will be exercised. The holder of this option will buy the underlying stock at a price of $S_{T}$ and exercise their right to sell it to the writer at the strike price of $X$ ,  to make a profit of $X-S_{T}$ If $S_{T}>X$，the option is said to finish out-of-the-money and exercising the right to sell the underlying asset would result in a loss. So the right to sell won't be exercised. The payoff will be zero in this case. Hence with an option the payoff is never negative. Assets with non-negative payoffs are know as limited liability assets.

Suppose that you hold a put option on a stock $PDQ$ .The exercise price is 1000 and the expiration date is in four weeks. The current stock price of $PDQ$ is 1109. If the stock is still at 1109 in four weeks time,  you we let the option expire without exercising your right to sell at 1000. If you exercised your right to sell you would have to deliver the stock,  which would cost you 1109,  and you would receive only 1000 in return. Clearly exercising the option to sell would result in a loss. You will not exercise and your payoff is $\operatorname*{max}[X-S_{T},      0]=\operatorname*{max}[1000-1109,      0]=0$ .However,  if $PDQ$ does badly and the stock price falls to 900 after four weeks,  you as holder of the put option will do well. In that case you can exercise your right to sell,  buying the stock at the reduced price of 900 and selling it to the holder at 1000. The payoff at maturity is $\operatorname*{max}[X-S_{T},      0]=\operatorname*{max}[1000-900,      0]=100$ per unit.

Equally the payoff to the holder of a call option is

$$c_T=\left\{\begin{array}{ll}0&\text{if}S_T\leq X\\S_T-X&\text{if}S_T>X.\end{array}\right.$$

or more simply $c_{T}=\max[0,      S_{T}-X]$ .In this case the call finishes in the money if $S_{T}>X$ as the option holder can exercise the right to buy the underlying asset at a price of $X$ when it is worth the greater amount $S_{T}$ .If $S_{T}\leq X$ ,  the call option finishes out of the money and the right to buy will go unexercised

The writer of the call option has exactly the reverse of the payoff to the holder. The writer of the call has a payoff of $- c_{T}$ = $- \max [ 0,       S_{T}- X]$ = $\operatorname*{min}[0,      X-S_{T}]$ .When the option is exercised the writer will have to deliver a stock worth $S_{T}$ and receives a payment of $X$ from the holder. Since $S_{T}>X$ the writer makes a loss of $X-S_{T}$ .Likewise the payoff at maturity to the writer of a put option is $-p_{T}=-\operatorname*{max}[X-S_{T},      0]=\operatorname*{min}[S_{T}-X,      0]$

The intrinsic value or parity value of an option at time $t$ is the payoff to the option if the current date were the maturity date. Thus the intrinsic value of the call option at time $t$ is $\operatorname*{max}[0,      S_{t}-X]$ where $S_{t}$ is the current price of the underlying asset and the intrinsic value of a put option is $\operatorname*{max}[X-S_{t},      0]$

An American option will always trade at a price at or above its intrinsic value,  since with an American option it is always possible to exercise the

Option now and realise the intrinsic value. The difference between the price of an option an its intrinsic value is known as the premium or time value of the option. Thus the price of an option is the sum of its intrinsic value plus its premium

$$\text{price of option}=\text{intrinsic value}+\text{time value}.$$

If an option is initially set up at date 0 when the stock price is $S_{0}$ and with the strike price set such that $X=S_{0}$ then the intrinsic value of the option is 0 and the premium and price are equivalent. Many options were historically set up with the strike price equal to the prevailing price of the underlying asset (or at-the-money as it is called) and this accounts for why the option price is sometimes referred to as the option premium. We will use the term time value rather than premium to avoid confusion

## Why trade options?

It is easy to see why it might be desirable to trade options. Suppose you buy a call option with an exercise price equal to the current stock price. If the stock goes up in value,  you can still buy at the low current price and sell at the new higher price. And if you are unlucky and the price falls,  then you simply don’t exercise the option. All you lose is the price you paid for the option in the first place. You only buy the stock when the price has gone up. You get all the upside benefits and eliminate the downside risk. You don't have to risk buying the stock in that hope that the price will rise. You simply buy the option which costs a fraction of the price of the stock itself.

Because you only pay for the stock at maturity,  buying a call option is equivalent to borrowing most of the money to buy the stock and repaying only if the bet goes well. Thus a call option is a highly levered or geared position in the stock and thus with a return that is higher but also highly risky.

To see this consider the following simple example. The current price of the stock is 100 and a call option on the stock with a strike price of 100 costs 30. Suppose that the stock price at maturity has risen to 175. The rate of return on the stock is a handsome $75\%$ .However the return on the call option is greater still. If the stock price rises to 175 the call option can be exercised to make a profit of 175-10=75 .Since the call costs 30 the rate of return is $\frac{75}{30}-1=1.5$ or $150\%$ . The high leverage makes possible a high rate of return on the relatively small investment. On the other hand suppose the stock finishes out of the money at 75. Owning the stock results in a rate of return of $-25\%$ .The call option however,  expires valueless,  so the rate of return on the investment in the call option is $-100\%$ .Not such a good prospect.

Suppose these are the only two possible values for the stock at maturity and suppose that TT is the probability the stock price rises and $(1-\pi)$ is the probability it falls. Suppose that the interest rate over the period is $25\%$ The risk premium on the stock is

$$rp_S=75\pi+(-25)(1-\pi)-25=100\pi-50$$

And the risk premium on the call option is

$$rp_C=150\pi+(-100)(1-\pi)-25=250\pi-100.$$

It is clear that the risk premium on the call is 2.5 times the risk premium for the stock irrespective of the value of 71 .This ratio is known as the option elasticity and it can be shown that for a call option it is always greater than one. Thus the call option is always riskier than the underlying stock. The high risk means that options are good and cheap ways to hedge risk as we shall see later on.

<table>
	<tbody>
		<tr>
			<th> </th>
			<th> </th>
			<th> </th>
			<th>Calls</th>
			<th> </th>
			<th> </th>
			<th>Puts</th>
			<th> </th>
		</tr>
		<tr>
			<th>Option</th>
			<th> </th>
			<th>May</th>
			<th>Calls $\operatorname{Aug}$</th>
			<th>Nov</th>
			<th>May</th>
			<th>Puts Aug</th>
			<th>Nov</th>
		</tr>
		<tr>
			<th>Option</th>
			<th> </th>
			<th>May</th>
			<th>$\operatorname{Aug}$</th>
			<th>Nov</th>
			<th>May</th>
			<th>Aug</th>
			<th>Nov</th>
		</tr>
		<tr>
			<td>Tesco</td>
			<td>160</td>
			<td>1 22</td>
			<td>27</td>
			<td>31</td>
			<td>7</td>
			<td>1 10 $\overline{2}$</td>
			<td>$14\frac{1}{n}$</td>
		</tr>
		<tr>
			<td>$(^*176)$</td>
			<td>180</td>
			<td>111</td>
			<td>17</td>
			<td>23</td>
			<td>16</td>
			<td>$\underline{1}$ 19.</td>
			<td>25</td>
		</tr>
		<tr>
			<td>Rolls $\operatorname{Royce}$</td>
			<td>180</td>
			<td>22</td>
			<td>27</td>
			<td>30 $\underline{1}$</td>
			<td>8</td>
			<td>12 1 I</td>
			<td>16</td>
		</tr>
		<tr>
			<td>$(^*194\frac{1}{2})$</td>
			<td>200</td>
			<td>11</td>
			<td>$17^{\frac{1}{a}}$ - $\overline{2}$</td>
			<td>$\frac 12$ 21</td>
			<td>18</td>
			<td>23</td>
			<td>$26\frac 12$ </td>
		</tr>
	</tbody>
</table>

Table 1: Call and Put Prices

# 2 Properties of Puts and Calls

Table 1 gives the prices of options on two stocks,  Tesco and Rolls Royce given in the Financial Times on Tuesday March 6 th 2000. The starred number in the left column gives the closing stock price on the previous day and the paper reports the prices for puts and calls of three maturities,  May,  August and November,  for strike prices on either side of the closing price.

Three things are immediately obvious from this table. First the option prices increase with the maturity date for any given strike price. Second the price of calls falls with the strike price for any given maturity date and third the price of puts rises with the strike price with any given maturity date.

For a given strike price,  the table shows that the price of calls increases with the date to maturity. That is $C_{t}(T_{2})\geq C_{t}(T_{1})$ for $T_{2}>T_{1}$ where $C_{t}(T_{1})$ is the price of an American call option at date $t$ that matures at date $T_{1}$ and $C_{t}(T_{2})$ is the an option of the same type and class and with the same strike price but with a longer maturity. 1 From the table we can see that August calls on Tesco stock with a strike price of 160 trade at 27 but the longer maturity November calls trade at 31. There would be a simple arbitrage opportunity if $C_{t}(T_{1})>C_{t}(T_{2})$ for $T_{2}>T_{1}$ .Suppose that the prices were reversed and the

November call on Tesco trades at 27 and the August call trades at 31. Then buying the lower priced November call and writing the August call yields a net infow of 4 today. Either the August call expires or is exercised prior to maturity. In either case its value is $\operatorname*{max}[0,      S_{t^{\prime}}-X]$ where $t^{\prime}$ is the maturity date in August or some time prior to the maturity date when the call is exercised. The value of the position is $C_{t^{\prime}}(Nov)-\operatorname*{max}[0,      S_{t^{\prime}}-X]$ . If this is positive then sell the November call at date $t^{\prime}$ to make a profit. Otherwise exercise the November call. Exercising the call yields the same value of $\operatorname*{max}[0,      S_{t^{\prime}}-X]$ no matter what the maturity date. So there is a completely offsetting gain from the bought November call and the written August call. In either case an arbitrage profit has been made. Note that this does not say anything about how the call value changes over time until maturity. It only compares prices at a particular date of options with different expiration dates. Neither does the argument work for European options which cannot be exercised early. However as a empirical matter European options do demonstrate the same pattern of prices rising with date to maturity

Equally clear is that a call with a lower strike price must command a higher price. Thus $C_{t}(X_{1})\geq C_{t}(X_{2})$ if $X_{2}>X_{1}$ . This can be seen from Table 1. For example,  May calls on Rolls-Royce with a strike price of 200 are worth 11 but the May calls with the lower strike price of 180 are worth 22. This is simply because the call gives the holder the option to buy and the lower the exercise price at which the stock can be bought the more valuable is the option. If this were not true and $C_{t}( X_{1})$ < $C_{t}( X_{2})$ for $X_{2}>X_{1}$ then there is an arbitrage opportunity and the appropriate response is a bull spread. The payoffs can be seen in Table 2. This strategy buys the call with the lower strike price of $X_{1}$ and writes the call with the higher strike price of $X_{2}$ leading to cash inflow now of $C_{t}(X_{2})-C_{t}(X_{1})>0$ . In each case the payoff at maturity is non-negative. Thus for European options $c_{t}(X_{1})\geq c_{t}(X_{2})$ for $X_{2}>X_{1}$ .Equally suppose the options are of the American type,  then if the written option is exercised early,  the holder of that option will pay us $X_{2}$ for the stock. If we exercise the bought option immediately,  the stock can be

<table>
	<tbody>
		<tr>
			<th>Position</th>
			<th>$S_{T}<X_{1}<X_{2}$</th>
			<th>$X_{1}<S_{T}<X_{2}$</th>
			<th>$X_{1}<X_{2}<S_{T}$</th>
		</tr>
		<tr>
			<td>Long Call</td>
			<td>0</td>
			<td>$S_{T}-X_{1}$</td>
			<td>$S_{T}-X_{1}$</td>
		</tr>
		<tr>
			<td>Short Call =1</td>
			<td>0</td>
			<td>0</td>
			<td>$X_2-S_T$</td>
		</tr>
		<tr>
			<td>0 verall</td>
			<td>0</td>
			<td>$S_{T}-X_{1}>0$</td>
			<td>$X_{2}-X_{1}>0$</td>
		</tr>
	</tbody>
</table>

Table 2: Bull Spread

bought for $X_{1}$ and then sold for $X_{2}$ leading to a profit of $X_{2}-X_{1}$ .Hence we have for American options $C_{t}(X_{1})\geq C_{t}(X_{2})$ for $X_{2}>X_{1}$

Another property that we can see from the table is that the differences in the call or put option prices for a given stock and maturity date is less than the difference between the strike prices. For example the difference in the option prices for November calls on Tesco stock is 31-23=8 which is less than the difference in strike prices,  which is 180-160=20 .Thus for call options we have $C_{t}(X_{1})-C_{t}(X_{2})\leq X_{2}-X_{1}$ for $X_{2}>X_{1}$ .Indeed if this were not the case and $C_{t}(X_{1})-C_{t}(X_{2})>X_{2}-X_{1}$ there would againbe an arbitrage opportunity. The strategy to exploit the arbitrage opportunity would be a bear spread where the the option with the higher strike price is purchased and the lower strike price option sold,  together saving the difference in the strike prices,  that is buying $(X_{2}-X_{1})$ risk free bonds with maturity at date $T$ and an interest rate of 7 between the current date $t$ and the maturity date. The payoffs from this strategy are given in Table 3 and the payoff is always positive at maturity and so the value of the portfolio $V_{t}$ must itself be positive. Thus for European options $V_{t}=c_{t}(X_{2})-c_{t}(X_{1})+(X_{2}-X_{1})>0$ If the options are American the value of the portfolio is $V_{t}$ = $C_{t}( X_{2})$ - $C_{t}(X_{1})+(X_{2}-X_{1})>0$ but we need to decide what to do if the written call is exercised prior to maturity. Suppose it is exercised at time $t^{\prime}$ when the stock price is $S_{t^r}$ .To meet our obligations on the written call we must buy the stock at $S_{t^{\prime}}$ and sell it at $X_{1}$ .The purchased call is worth $C_{t^{\prime}}(X_{2})$ at time $t^{\prime}$ .If $C_{t^{\prime}}(X_{2})>S_{t^{\prime}}-X_{2}$，then we simply sell our call to cover our obligation and make a net profit and in addition have our risk-free bonds. If

<table>
	<tbody>
		<tr>
			<th>Position</th>
			<th>Value</th>
			<th>$S_{T}<X_{1}<X_{2}$</th>
			<th>$X_{1}<S_{T}<X_{2}$</th>
			<th>$X_{1}<X_{2}<S_{T}$</th>
		</tr>
		<tr>
			<td>Long Call</td>
			<td>$C_t (X_2)$</td>
			<td>0</td>
			<td>0</td>
			<td>$S_{T}-X_{2}$</td>
		</tr>
		<tr>
			<td>Short Call</td>
			<td>$-C_{t}(X_{1})$</td>
			<td>0</td>
			<td>$X_{1}-S_{T}$</td>
			<td>$X_{1}-S_{T}$</td>
		</tr>
		<tr>
			<td>Buy Bonds</td>
			<td>$(X_{2}-X_{1})$</td>
			<td>$(X_{2}-X_{1})(1+r)$</td>
			<td>$(X_{2}-X_{1})(1+r)$</td>
			<td>$(X_{2}-X_{1})(1$ $1+i$</td>
		</tr>
		<tr>
			<td>0 verall</td>
			<td>$V_{t}$</td>
			<td>$(X_{2}-X_{1})(1+r)$ </td>
			<td>$(X_{2}-S_{T})+r (X_{2}-X_{1})>0$</td>
			<td>$r (X_{2}-X_{1})>0$</td>
		</tr>
	</tbody>
</table>

Table 3: Bear Spread plus Savings

$C_{t^{\prime}}(X_{2})<S_{t^{\prime}}-X_{2}$ ,  then we exercise the call,  buying the stock at $X_{2}$ and selling it at $X_{1}<X_{2}$ .The loss on this transaction is covered by closing out our bond position,  so we retain the accumulated interest $r^{\prime}(X_{2}-X_{1})$ where $r^{\prime}$ is the interest rate from $t$ to $t^\prime$

One property not apparent from the table is the relationship between options with more than two strike prices. Suppose that May puts on RollsRoyce with a strike price of 190 are traded. It is to be expected that they trade at a price somewhere between the 8 and 18. Suppose that all the puts are European,  then it is simple to show that the May European put with a strike of 190 cannot trade at a price above 13 which is the mid-way point between 8 and 18. To establish this claim consider another popular trading strategy the butterfy spread. This spread consists of a portfolio of buying one put with a strike price of 180,  buying another put with a strike price of 200 and selling two puts with a strike price of 190. The payoffs at maturity to this strategy are given in Table 4. In each case the payoffs at maturity are positive so we can be assured that the value of the portfolio is non-negative. Hence $26-2p_{t}(190)\geq0$ or $p_{t}(190)\leq13$ .This argument again applies to American as well as European options. If the written puts are exercised early,  then either exercise both puts immediately to cash-out the position or one or both of the puts can be sold if this yields a higher profit.

Using butterfy spreads in this way establishes that for puts with strike prices $X_{1}$ and $X_{3}$ ,  the price of the put with the mid-way strike price of

<table>
	<tbody>
		<tr>
			<th>$\mathbf{Position}$</th>
			<th>Value</th>
			<th>$S_T$ <180 </th>
			<th>$180<S_{T}<190$</th>
			<th>$190<S_T<200$</th>
			<th>$S_{T}$ 200 $<i$</th>
		</tr>
		<tr>
			<td>1 st I Long Put</td>
			<td>8</td>
			<td>$180-S_T$</td>
			<td>0</td>
			<td>0</td>
			<td>0</td>
		</tr>
		<tr>
			<td>Short Puts</td>
			<td>$-2 p_{t}(190)$</td>
			<td>$2 (S_T-$ -190)</td>
			<td>$2 (S_{T}-190)$</td>
			<td>0</td>
			<td>0</td>
		</tr>
		<tr>
			<td>2 nd Long Put</td>
			<td>18</td>
			<td>$200-S_{T}$</td>
			<td>$200-S_{T}$</td>
			<td>$200-S_{T}$</td>
			<td>0</td>
		</tr>
		<tr>
			<td>Overall</td>
			<td>$26-2 p_{t}(190)$</td>
			<td>0</td>
			<td>$S_{T}-180$</td>
			<td>$200-S_{T}$</td>
			<td>0</td>
		</tr>
	</tbody>
</table>

Table 4: Butterfy Spread with Puts

## $\frac{1}{2}X_{1}+\frac{1}{2}X_{3}$ satisfies

$$P_{t}(\frac12X_{1}+\frac12X_{3})\leq\frac12P_{t}(X_{1})+\frac12P_{t}(X_{3}).$$

A slightly more generalinterpretation would be tobuy a fraction $\lambda$ units of the put with strike price of $X_{1}$ and buy a fraction $(1-\lambda)$ units of the put with strike price $X_{3}>X_{1}$ and write one put with a strike price of $X_{2}=\lambda X_{1}+(1-\lambda)X_{3}$ .With this portfolio it can be found that

$$P_{t}(\lambda X_{1}+(1-\lambda)X_{2})\leq\lambda P_{t}(X_{1})+(1-\lambda)P_{t}(X_{2}).$$

It therefore follows from arbitrage principles that the put price is a convex function of the strike price. Equally constructing a butterfy spread for calls also shows that the call price is a convex function of the strike price.

## 3 Summary

We have seen how the payoffs to put and call options depend on the underlying assets and how the prices of puts and calls depend on the length of time to maturity and strike price. We shall explore other properties of option prices and ultimately derive an expression for how option prices depend on the strike price,  time to maturity,  interest rate,  volatility and current price of the underlying asset. Indeed we shall se how any derivative asset can be priced.

# Options

These notes consider the way put and call options and the underlying can be combined to create hedges,  spreads and combinations. We will conside the parity condition that applies for put and call option and consider arbitrage bounds that apply to the prices of puts and calls.

Keywords: American option,  European option,  early exercise,  put-call parity,  hedge,  spread,  combination,  bull spread,  bear spread,  strap,  arbitrage bounds,  covered call,  protective put.

Reading: Chapters 9 and 10 from Hull.

# 1 Option Trading Strategies

There are basically three varieties of trading strategies. A hedge combines an option with an underlying stock to protect either the option or the stock against loss. A spread combines options of the same class but different series,  where some are bought and others written. A combination combines options of different types,  both bought or both written,  on the same underlying stock.

## A hedge

Suppose that you write a call option. The payoff to a call option at maturity is $\operatorname*{max}[0,      S_{T}-X]$ where $X$ is the strike price and $S_{T}$ is the price of the underlying at maturity. Your payoff at maturity having written the call is therefore min $[0,      X-S_{T}]$ . If the price of the underlying rises above the strike price you will make a loss. Moreover,  these losses are potentially unlimited

If the price rises far above the strike price you are in a very exposed position. You may want to hedge or cover this risk. The obvious way to do so is to buy the stock which you will be obliged to deliver if the call is exercised. Taking a long position in the stock to hedge a written call is known as writing a covered call.

The payoff at maturity to writing a covered call is $\operatorname*{min}[S_{T},      X]$ . This is far less risky than the naked short position in the call itself as now the worst that can happen is that you sell the underlying at a price below its market value. Of course the hedged position is costly,  it costs $S_{t}-c_{t}$，whereas the naked position has a positive initial inflow of cash of $Ct$ the price of the call option.

Likewise if you buy a put option there will loss if the price of the underlying rises equal to the cost of the put option $p_{t}$ .The payoff at maturity will be $\max[0,      X-S_{T}]$ .However,  you will have to buy the stock if you wish to exercise the right to sell at the strike price $X$ .Thus you may wish to buy the stock in advance at the cost of $S_{t}$ .In this case the payoff at maturity is $\max[S_{T},      X]$ and the initial cost is $S_{t}+p_{t}$ .Going long in the put and the stock is known as a protective put strategy

## A spread

There are many examples of spreads. Vertical spreads use options of the same maturity but different strike prices; horizontal spreads use options with the same strike prices but different maturities and diagonal spreads use option with both different strike prices and maturities.

One popular type of vertical spread is the bull spread which is a position taken by an investor who thinks that the price of the underlying will rise.

<table>
	<tbody>
		<tr>
			<th>Position</th>
			<th>$S_{T}<X_{1}<X_{2}$</th>
			<th>$X_{1}<S_{T}<X_{2}$</th>
			<th>$X_{1}<X_{2}<S_{T}$</th>
		</tr>
		<tr>
			<td>Long Call</td>
			<td>0</td>
			<td>$S_{T}-X_{1}$</td>
			<td>$S_{T}-X_{1}$</td>
		</tr>
		<tr>
			<td>Short Call =1</td>
			<td>0</td>
			<td>0</td>
			<td>$X_2-S_T$</td>
		</tr>
		<tr>
			<td>0 verall</td>
			<td>0</td>
			<td>$S_{T}-X_{1}>0$</td>
			<td>$X_{2}-X_{1}>0$</td>
		</tr>
	</tbody>
</table>

Table 1: Bull Spread

A bull spread can be created by buying a call with a low strike price and writing a call with a higher strike price. Suppose that the written call has a strike price of $X_{2}$ and the long call has a strike price of $X_{1}<X_{2}$ .The payoffs at maturity are given in the Table 1. The value of the spread is $c^{1}-c^{2}$ where $c^{1}$ is the price of the call option with a strike price of $X_{1}$ and $c^{2}$ is the price of the call option with a strike price of $X_{2}$ .Since the bull spread always yields a non-negative payoff at maturity (it is a limited liability asset) it follows that $c^{1}>c^{2}$

Another type of spread is a bear spread. A bear spread can be created by holding a put with a higher strike price and writing a put with a lower strike price. In this case the investor benefits if the markets is falling. This is in contrast to a bull spread where the investor gains when the market rises.

Exercise: An investor buys a March put on Reed Elsevier with a strike price of 649 for a price of 55.5 and writes a March put on Reed Elsevier with a strike price of 609 for a price of 34. Calculate the payoff now and the possible payoffs in March when the puts expire. Draw a table and a diagram to illustrate the payoffs.

## A combination

A combination involves taking a position in both puts and calls on the same underlying asset. One particular combination is a strap. A strap consists of a long position in two calls and one put with the same strike price and

<table>
	<tbody>
		<tr>
			<th>Position</th>
			<th>Value</th>
			<th>$S_T$ $X$ <. </th>
			<th>$X$ $S_{T}$ $<i$</th>
		</tr>
		<tr>
			<td>Long Call</td>
			<td>$c_t$</td>
			<td>0</td>
			<td>$S_T-$ $X$ </td>
		</tr>
		<tr>
			<td>Short Forward</td>
			<td>$-v_t$</td>
			<td>$S_T$ $X$ 一</td>
			<td>$X$ $S_T$ 一</td>
		</tr>
		<tr>
			<td>0 verall</td>
			<td>$v_t$ -</td>
			<td>$X-S_T$</td>
			<td>0</td>
		</tr>
	</tbody>
</table>

expiration date. This position is appropriate if it is thought that there is likely to be a large change in the price of the underlying but the direction of change is unknown. However it is thought that an increase is more probable than a decrease. The payoff at maturity from the strap is $X-S_{T}$ if $S_{T}<X$ and $2(S_{T}-X)$ if $S_{T}>X$

# 2 Put-Call Parity Condition (European)

Consider buying a call option with a strike price of $X$ and a maturity date of 7 and at the same time going short in a forward contract on the same underlying and with a delivery price of $X$

The overall position from this portfolio is the same as a long position in an equivalent put option on the same underlying with the same strike price and maturity date. Thus the two portfolios must have equal values,  $c_{t}-v_{t}=p_{t}$ where $v_{t}$ is the value of the forward contract. From our previous knowledge of forward contracts we know that $v_{t}=S_{t}-(X/(1+r))$ . Therefore

$$c_t+\frac{X}{(1+r)}=p_t+S_t$$

where 7 is shorthand for $r_{t}^{T}$ .This condition is the put-call parity condition from European options. This equation is known as the put-call parity condition as it was first derived under the assumption that the options were at the money,  $S_{t}=X$ and that the interest rate was 0

It can be seen directly from this equation that the portfolio which is long in the stock and long in the put option is equivalent to a portfolio which is long in the call and long in a discount bond with a face value of $X$

### Exercise: Check it out

Another way to see this is as follows. Consider simultaneously buying a call and writing a put. If $S_{T}>X$ then exercise the call for a profit of $S_{T}-X$ If $X>S_{T}$ ,  then the put will be exercised resulting in a payoff of $X-S_{T}$ for the holder and a payoff of $S_{T}-X$ for the writer. Thus the portfolio of one call and one written put results in a payof of $S_{T}-X$ in all circumstances The value of this payoff can be evaluated using the stochastic discount factor $k$ .The value of the portfolio at time $t$ is

$$c_t-p_t=E[k\cdot(S_T-X)]=E[k\cdot S_T]-XE[k]=S_t-\frac{X}{(1+r)}$$

since by definition the appropriately discounted value of the stock price at time $T$ is the stock price now,  $S_{t}$ ,  and $E[k]$ is the appropriate discount factor. Again we have the same put-call parity condition.

To labour the point once more remember that the payoff at maturity from writing a covered call is $\operatorname*{min}[S_{T},      X]$ .Suppose that in addition you go short in a risk free bond with a face value of $X$ .The overall payoff at maturity is $\operatorname*{min}[S_{T}-X,      0]$ ,  the same as writing a put option. The value of this portfolio is $S_{t}-c_{t}-\frac{X}{(1+r)}$ ,  which must equal the value of writing the put option,  $-p_{t}$

# 3 Arbitrage Bounds

We will know consider the payoff to the option prior to maturity. We will establish bounds for the option value prior to maturity

The intrinsic value or parity value of an option at time $t$ is the payoff to the option if the current date were the maturity date. Thus the intrinsic

value of the call option at time $t$ is $\operatorname*{max}[0,      S_{t}-X]$ where $St$ is the current price of the underlying asset and the intrinsic value of a put option is $\max[X-S_{t},      0]$

An American option will always trade at a price at or above its intrinsic value,  since with an American option it is always possible to exercise the option now and realise the intrinsic value. The difference between the price of an option an its intrinsic value is known as the premium or time value of the option. Thus the price of an option is the sum of its intrinsic value plus its premium

$$\text{price of option}=\text{intrinsic value}+\text{time value}.$$

If an option is initially set up at the money,  $S_{0}=X$ then the intrinsic value of the option is 0 and the premium and price are equivalent. This accounts for why the option price is sometimes referred to as the premium. We will use the term time value to avoid confusion

A European call option also has a positive time value. That is the price of a European call option cannot be less than its intrinsic value. Remember that the payoff to the call option is $Max[S_{T}-X,      0]$ .The call can be valued using the stochastic discount factors $k$ .Thus the value of the call option at time $t$ is $c_{t}=E[k\cdot Max[S_{T}-X,      0]]$ . Clearly

$$c_t\ge E[k\cdot(S_T-X)]=E[k\cdot S_T]-XE[k]=S_t-\frac{X}{(1+r)}$$

where thefirst inequality comes from the definition of the maximum and the other equalities follow as $E[k\cdot S_{T}]=S_{t}$ 1,  the stochastically discounted value of the stock at maturity is its current value,  and the fact that $E[k]=\frac{1}{(1+r)}$ Equally since $S_{T}\geq0$ and $X\geq0$ ,  it follows that $Max[S_{T}-X,      0]\leq S_{T}$；sO $c_{t}\leq E[k\cdot S_{T}]=S_{t}$ .Since the call cannot command a negative price we have for the arbitrageboundsfor a call option

$$S_t\ge c_t\ge\max\left[S_t-\frac{X}{(1+r)},      0\right].$$

<table>
	<tbody>
		<tr>
			<th>Position</th>
			<th>Value</th>
			<th>$S_T$ $X$ <</th>
			<th>$<S_{T}$ $X$</th>
		</tr>
		<tr>
			<td>Write Call</td>
			<td>$-c_t$</td>
			<td>0</td>
			<td>$\overline{X-S_T}$</td>
		</tr>
		<tr>
			<td>Buy Stock</td>
			<td>$S_t$</td>
			<td>$S_T$</td>
			<td>$S_T$</td>
		</tr>
		<tr>
			<td>0 verall</td>
			<td>$S_t-$ $c_t$ </td>
			<td>$S_T$</td>
			<td>$X$</td>
		</tr>
	</tbody>
</table>

Since the strike price on the RHS is discounted we have $\frac{X}{(1+r)}<X$ ,  so that

$$c_t\ge\max\left[S_t-\frac{X}{(1+r)},      0\right]>\max[S_t-X,      0]$$

for $t<T$ and $r>0$ ,  so the European call has value greater than its intrinsic value at any date prior to maturity

To see how the inequalities in (2）can be derived without using the stochastic discount factor first let's consider the upper bound on the European call option. The value of the call cannot be greater than the value of the stock. This is obvious because the call option only gives you the right to buy the stock. If the call option cost more than the stock,  it would simply be cheaper to buy the stock now and have nothing further to pay. To see this more clearly consider writing a covered call,  that is buy the stock and write a call option. The payoff now is $c_{t}-S_{t}$ ,  which is positive if the call price is greater than the current stock price. At maturity,  either the call goes unexercised,  if $S_{T}<X$ ,  and we are left with the stock with value of $S_{T}$ or the call is exercised,  in which case we give up the stock we own for the agreed strike price of $X$ .Either way we end up with a positive payoff at maturity so the value of the portfolio must be positive $S_{t}-c_{t}>0$ if $X>0$ or $S_{T}>0$ If $c_{t}>S_{t}$ there is an arbitrage possibility formed by writing a covered call. The payoffs are summarised in the Table 3.

To see the lower bound on the call option,  $c_{t}$ $\geq$ $S_{t}$ - $\frac X{( 1+ r) }$ recall that we have already shown that a long position in the call option with a strike price of $X$ combined with a short position in a forward contract on the same

<table>
	<tbody>
		<tr>
			<th>Position</th>
			<th>Value</th>
			<th>$e$</th>
			<th>$S_T$ $X$ $\zeta$</th>
			<th>$X$ $S_{T}$ $<i$</th>
		</tr>
		<tr>
			<td>Buy Call</td>
			<td>$C_t$</td>
			<td> </td>
			<td>0</td>
			<td>$S_{T}$ $X$ -</td>
		</tr>
		<tr>
			<td>Sell Stock</td>
			<td>$-S_{t}$</td>
			<td> </td>
			<td>$-S_T$</td>
			<td>$-S_T$</td>
		</tr>
		<tr>
			<td>Buy Bond</td>
			<td>$\underline{X}$</td>
			<td> </td>
			<td>$X$</td>
			<td>$X$</td>
		</tr>
		<tr>
			<td>Overall</td>
			<td>$c_{t}-S_{t}+$</td>
			<td>$\overline{X}$ $\overline{(1+r^{\prime})}$</td>
			<td>$\overline{X-S_T}$</td>
			<td>0</td>
		</tr>
	</tbody>
</table>

Table : all Lower Bound: $c_{t}\geq S_{t}-\frac{X}{(1+r)}$

Underlying and with a delivery price of $X$ is equivalent to a long position in a put option with the same strike price. A short position in the forward contract with a delivery price of $X$ is itself equivalent to selling the stock short now and buying a risk-less bond with a face value of $X$ .The payoffs are summarised in Table 4. The portfolio has a payoff of 0 if $X<S_{T}$ the bond pays out $X$ and the call is exercised using the bond payoff to pay the strike price and the purchase of the stock closes out the short position. The portfolio has a payoff of $X-S_{T}$ if $S_{T}<X$ as the call option goes unexercised. Thus the portfolio replicates the put option and in particular never has a negative payoff. The value of the portfolio must therefore be positive by the no-arbitrage principle,  $c_{t}\geq S_{t}-\frac{X}{(1+r)}$

An American option cannot beless valuable than the equivalent European option as the American option provides all the same rights as the European option and the opportunity to exercise early. Thus $C_{t}\geq c_{t}$ and $P_{t}\geq p_{t}$ However,  although it is possible to exercise an American call option on a non-dividend paying stock prior to maturity,  it is never optimal to do so. This is because the European call option has a positive time value and thus its price is greater than its intrinsic value. Since $C_{t}\geq c_{t}>S_{t}-X$ for $t<T$ it will always be better to sell the call option and get $C_{t}$ rather than exercise it and get $S_{t}-X$ .Thus the option to exercise the American option early is redundant and the American and European options on non-divided paying assets are equivalent and hence must trade at the same price,  $C_{t}=c_{t}$

The qualification that the underlying asset should be non-dividend paying is important. It may be optimal to exercise an American option early if the underlying asset is a dividend paying stock. Let $D_{t}$ denote the present value of dividends paid on the underlying during the remainder of the options life. Then the lower bound for the call option is $S_{t}-D_{t}-\frac{X}{(1+r)}$ .If $D_{t}$ is large enough,  then this lower bound can below the intrinsic value of $S_{t}-X$ .In this case it may be optimal to exercise early. To take an extreme case suppose that the call is in the money but the firm on which the option is written is unexpectedly to be liquidated and all the asset value is to be paid out in dividends. Then after the dividend payment,  the stock is worthless and the call option can never be in the money. In this case it is best to exercise early and take the positive value of exercise now.

By analogy the arbitrage bounds for a European put option on a nondividend paying stock with a payoff of $Max[X-S_{T},       0]$ are

$$X\ge p_t\ge\max\left[\frac{X}{(1+r)}-S_t,       0\right].$$

Note that an American put option cannot be less than its intrinsic value,  so the arbitrage bounds for an American put option are

$$X\geq P_t\geq\max[X-S_t,       0].$$

For an American put option early exercise can be optimal even if the underlying asset pays no dividends. To take an extreme example,  suppose that $S_{t}=0$ but $X>0$ .It is impossible to gain more by waiting since the stock price cannot fall further. In addition the gain to be had by waiting is discounted at the risk-free rate,  and if the interest rate is positive it is better to exercise now rather than wait. If exercise is ever optimal before maturity then $P_{t}=X-S_{t}$ since if $P_{t}>X-S_{t}$ it would be better to sell the option rather than exercise it.

Exercise: Find an arbitrage opportunity if $p_{t}>X$

Exercise: Find an arbitrage opportunity if $p_{t}<\frac{X}{(1+r)}-S_{t}$

<table>
	<tbody>
		<tr>
			<th>Position</th>
			<th>Value</th>
			<th>$S_T$ $<X$</th>
			<th>${\overline{<S_{T}}}$ $X$</th>
		</tr>
		<tr>
			<td>Buy Call</td>
			<td>$C_t$</td>
			<td>0</td>
			<td>$S_T-X$</td>
		</tr>
		<tr>
			<td>Write put</td>
			<td>$-P_t$</td>
			<td>$S_T-.$ $X$ -</td>
			<td>0</td>
		</tr>
		<tr>
			<td>Short Stock</td>
			<td>$-S_{t}$</td>
			<td>$-S_T$</td>
			<td>$-S_T$</td>
		</tr>
		<tr>
			<td>Save $X$</td>
			<td>$X$</td>
			<td>$X (1$ $1+r)$</td>
			<td>$X (1$ $+r$</td>
		</tr>
		<tr>
			<td>Overall</td>
			<td>$C_{t}-P_{t}-S_{t}+X$</td>
			<td>$rX$</td>
			<td>$rX$</td>
		</tr>
	</tbody>
</table>

Table 5: American Put-Call Parity: $C_{t}-P_{t}\geq S_{t}-X$

# 4 Put-Call Parity Condition (American)

There is a put-call parity condition for American options on non-dividend paying stocks. The condition however,  is one of inequalities rather than equality and is given by:

$$S_t-\frac{X}{(1+r)}\geq C_t-P_t\geq S_t-X.$$

The first inequality follows from three facts. First the parity condition for European puts and calls (equation (1)) that $c_{t}- p_{t}$ = $S_{t}- ( X/ ( 1$ + $r) )$ Second the fact that American call options are not exercised early,  so $C_{t}=$ $Ct$ and third the fact that the American put cannot be worthless than the European put,  that is $P_{t}\geq p_{t}$ .Hence combining these three facts we get $c_{t}-p_{t}=S_{t}-(X/(1+r))\geq C_{t}-P_{t}$ .To see the second inequality consider the portfolio of a long call,  a short put,  shorting the stock and saving $X$ .The payoffs to this portfolio are summarised in the Table 5. Since the portfolio yields a certain return of $rX$ at maturity,  the portfolio must have a positive value at date $t$ ,  and hence we can conclude that $C_{t}-P_{t}\geq S_{t}-X$

Note the bounds in equation (3) are quite tight and become tighter the smallers is the interest rate 7 .If the interest rate is zero ( $r=0$）then the inequalities in equation (3) becomes an equality

$$C_t-P_t=S_t-X.$$

If in addition the option is set up at date $t$ and the strike price is set so that the option is at-the-money (that is $X=S_{t}$ ) then we have exact parity between the put and call prices for American options too and $C_{t}=P_{t}$

# One Period Binomial Model

These notes consider the one period binomial model to exactly price an option. We will consider three different methods of pricing an option: deltahedging,  creating a synthetic option using the underlying asset and the riskfree asset and calculating the risk-neutral probabilities or stochastic discount factors. All methods will be used again when we extend the binomial model beyond one period and when we consider continuous trading

Keywords: Delta-hedging,  synthetic options,  replication,  risk-neutral probabilities,  risk-neutral valuation.

Reading: Start of chapter 11 from Hull.

### Binomial Model

To value options exactly it is necessary to make specific assumptions about the determinants of the price of the underlying security. In practice this often means that a continuous stochastic process for the underlying is estimated or inferred from observations on past prices. However,  the essential aspects can all be embodied in a simple binomial model in which the underlying asset can be one of two possible values at the end of each period; to put in starkly the asset can either go up or go down in value. By considering more than one period a binomial tree is constructed,  where the price that an asset has branches out,  either upward or downward at each point in time. These binomial trees can provide a remarkably good approximation to a more complex stochastic process provided that the number of periods is reasonably large,  say above thirty.

In fact nearly all the basic principles of derivative pricing can be explained with a one or two period binomial model and this section develops the one period binomial model to study how options are exactly priced and the riskiness and elasticity of options.

## Delta Hedging

Buying a stock is a risky investment. Buying a call option on that stock is even riskier. Yet combining the stock with the option can produce an investment that is risk-free. That is it is possible to hedge a position in the stock by taking an opposite position in the call option. To create such a risk-free investment it is necessary to buy the stock and the option in exactly the right proportions. The number of units of the stock required per option is known as the $\Delta$ (Delta) of the stock and taking these positions to create a risk-free investment is known as Delta Hedging.

We will now illustrate how to calculate $\Delta$ in a simple binomial example Once $\Delta$ is known the option price itself can be calculated as any risk-free investment must in the absence of arbitrage opportunities earn the risk-free rate ofreturn.

Consider a simple example where the price of the underlying stock is 100 and at the end of three months it has either risen to 175 or has fallen to 75. There is an "up" state and a"down” state. Let $u=0.75$ and $d=-0.25$ ,  SO that the value of the stock in three months in the up state is $100 (1+u)=175$ and the value in the down state is $100 (1+d)=75$ .The net growth rate of the value of the stock in the up state is $75\%$ ,  and the net growth in the value of the stock in the down state is $-25\%$

Since the stock can either rise by $75\%$ or fall by $25\%$ buying the stock is a risky investment. Now consider an at the money call option on this stock with a strike price of 100. If the stock goes up then in three months the

Call can be exercised for a profit of 175-100=75 and if the price of the stock goes down,  then the call will not be exercised. Thus the payoff to the call option is 75 in the up state and 0 in the down state. So the call is also risky. Suppose however,  that we consider buying $\Delta$ units of the stock and writing one call. The payoff from this portfolio is $175\Delta-75$ in the up state: the stock has gone up to 175 but the call option we have written will be exercised against us so we have an obligation of 75 The payoff in the down state is simply $75\Delta$ as the call option is not exercised in the down state. To make this portfolio risk-free it is necessary to choose $\Delta$ such that

$$175\Delta-75=75\Delta $$

So that the payof is the same no matter whether we are in the up state or the down state. Solving for $\Delta$ gives $\Delta=3/4$ .Thus to completely hedge out the risk in the stock,  we should sell four call options for every three units of stock we buy. The payoff from such a portfolio is given in Table 1. The value in three months time is 225 in both states and hence the portfolio is riskfree. Since it is risk-free it can be valued using the risk-free rate of interest Suppose the risk-free rate of interest is 1/4 or $25\%$ .The present value of this portfolio is 225/(1+1/4)=180 .The value of the portfolio now is simply the current value of the share,  $3\times 100=300$ less $4 c$ where $C$ is the price of the call option. If there are no arbitrage possibilities then the value of this portfolio must also have a value of 3180:

$$300-4 c=180.$$

So solving for the call price gives $c=30$ .This shows that the $\Delta$ -hedge can be used to price the option.

The same procedure can be generalized. Let S be the value of the underlying stock,  so its terminal value is $S_{u}=(1+u) S$ in the up state and $S_{d}=(1+d) S$ in the down state. Let $K$ be the strike price of the option and $c_{u}=\operatorname*{max}[0,       S_{u}-K]$ be the value of the call option in the up state and

<table>
	<tbody>
		<tr>
			<th>${\mathbf{P}}$osition</th>
			<th>Value Now</th>
			<th>Value in down state</th>
			<th>Value in $up$ $\mathbf{state}$ 1 4</th>
		</tr>
		<tr>
			<td>4: Short Calls 1</td>
			<td>$-4 c$</td>
			<td>0</td>
			<td>300</td>
		</tr>
		<tr>
			<td>Long Shares 3 I</td>
			<td>300</td>
			<td>225</td>
			<td>525</td>
		</tr>
		<tr>
			<td>0 verall</td>
			<td>$300-4 c$</td>
			<td>225</td>
			<td>225</td>
		</tr>
	</tbody>
</table>

Table 1: Risk-Free Portfolio - Example

$c_{d}=\operatorname*{max}[0,       S_{d}-K]$ is the value of the call option in the down state. Remember,  that the call option gives us the right to buy the underlying at a priceof $K$，so for example in the up state when the stock is worth $S_{u}$ .the option gives the right to buy at $K$ and asset that can be sold for $S_{u}$ .Thus the option will be exercised for a profit of $S_{u}-K$ if $S_{u}-K>0$ and won't be exercised otherwise.

Now consider the $\Delta$ -hedge portfolio that writes one call and buys $\Delta$ units of the underlying. The payoffs from this portfolio are given in Table 2. The value of $\Delta$ is chosen so that the portfolio is riskless,  $\Delta S_{d}-c_{d}=\Delta S_{u}-c_{u}$ i.e.
$$\Delta=\frac{c_u-c_d}{S_u-S_d}=\frac{c_u-c_d}{(u-d) S}.$$

The value of the risk-free portfoliois evaluated at the risk-free rate ofinterest 7 ,  so that
$$\Delta S-c=\frac{\Delta S_d-c_d}{(1+r)}.$$

Using the value of $\Delta$ just derived,  and substituting $(1+d) S$ for $S_{d}$ and solving for $C$ gives after some manipulation

$$c=\frac{pc_u+(1-p) c_d}{(1+r)}$$

Where $p$ = $( rd) / ( ud)$ .Thus for any values of $S$，$K$，7，$UL$ and $d$ the value of the call option can be calculated from this formula.

There is a natural interpretation for $\Delta$ .It is the difference in the value of the call at maturity $c_{u}-c_{d}$ in the up state rather than the down state

<table>
	<tbody>
		<tr>
			<th>$\mathbf{P}_{\mathrm{osition}}$</th>
			<th>Value Now</th>
			<th>Value in down state</th>
			<th>Value in $up$ $\mathbf{state}$ T</th>
		</tr>
		<tr>
			<td>Short Call 上 1</td>
			<td>$-c$</td>
			<td>$-c_d$</td>
			<td>$-c_u$</td>
		</tr>
		<tr>
			<td>Long Shares $\Delta$</td>
			<td>$\Delta S$</td>
			<td>$\Delta S_d$</td>
			<td>$\Delta uS_{u}$</td>
		</tr>
		<tr>
			<td>$0_{\mathrm{verall}}$</td>
			<td>$\Delta S-c$</td>
			<td>$\Delta S_{d}-c_{d}$</td>
			<td>$\Delta S_{u}-c_{u}$</td>
		</tr>
	</tbody>
</table>

Table 2: Risk-Free Portfolio

Relative to the difference in the value of the stock $S_{u}-S_{d}$ .It tells us the change in the value of the call relative to the change in the value of the stock or how much the value of the call changes when the stock changes by a given amount. Thus $\Delta$ tells us how responsive is the call value to changes in the value of the stock. We will return to this interpretation when we consider the elasticity of an option later on.

## Synthetic Options

The idea underlying $\Delta$ -Hedging is to create a risk-free asset using a combination of the stock and the option that can be valued at the risk-free rate of interest. The risk-free asset and the underlying asset can themselves be combined to replicate the payoffs of the option itself. Such a combination is called a synthetic option.

Consider again our simple example where the price of the underlying stock is 100 and at the end of three months it has either risen to 175 or has fallen to 75. Now consider how an at the money call option on this stock with a strike price of 100 can be synthesized. The payoff to the call option in the up state is 75 and the payoff in the down state is 0 as the option will not be exercised. Consider buying $\Delta$ units of the stock and investing $B$ units of funds at the risk-free interest rate of 1/4 .The payoff from this portfolio in the up state is $175\Delta+(1+1/4) B$ and the payoff in the down state is $75\Delta+(1+1/4) B$ .To synthesize the option we must match these payoffs to

<table>
	<tbody>
		<tr>
			<th>$\mathbf{P}$osition</th>
			<th>Value Now</th>
			<th>Value in down state</th>
			<th>Value in $up$ state</th>
		</tr>
		<tr>
			<td>Borrow $B$</td>
			<td>-45</td>
			<td>225/4</td>
			<td>225/4</td>
		</tr>
		<tr>
			<td>Buy shares $\Delta$</td>
			<td>75</td>
			<td>225/4</td>
			<td>525/4</td>
		</tr>
		<tr>
			<td>0 verall</td>
			<td>30</td>
			<td>0</td>
			<td>75</td>
		</tr>
	</tbody>
</table>

Table 3: Synthetic Option

The payoffs from the option. That is we must find $\Delta$ and $B$ to solve

$$175\Delta+(1+1/4) B=75$$

$$75\Delta+(1+1/4) B=0.$$

Solving these two equations simultaneously gives $\Delta=3/4$ and $B$ = -45 Thus the option can be replicated by borrowing 45 and buying $\frac{3}{4}$ units of the stock. Since the stock costs 100 the the cost of buying 3/4 of a unit of stock is 75. Thus the net cost of synthesizing the option is the price we pay minus the amount borrowed,  75-45=30 .Again the portfolio that replicates or synthesizes the call must have the same price as the call itself. Hence $c=30$ and we reach exactly the same conclusion as before. The payoffs are summarized in Table 3.

Again it is simple to generalize this procedure. To find the number of shares to be bought $\Delta$ and the amount to invest $B$ to synthesize the option it is only necessary to solve simultaneously the following two equations:

$$\begin{array}{c}\Delta S_u+(1+r) B=c_u\\\\\Delta S_d+(1+r) B=c_d.\end{array}$$

Solving these two equations gives

$$\Delta=\frac{c_u-c_d}{S_u-S_d}$$

And

$$B=\frac{1}{1+r}(c_d-\Delta S_d)=\frac{1}{1+r}\left (c_d-\frac{(1+d) S (c_u-c_d)}{(S_u-S_d)}\right).$$

This is illustrated graphically in Figure 1. The payoff at maturity to the call option is illustrated by the thick line. The two possible end values for the stock $S_{u}$ and $S_{d}$ are drawn on the horizontal axis. The strike price $K$ has been chosen between the two values $S_{u}$ and $S_{d}$ so that in the down state the call option expires valueless and $c_{u}=0$ .The value of the call in the up stateis $c_{u}=S_{u}-k$ and this is illustrated on the vertical axis. Also drawn is the line connected the two points $(S_{d},       c_{d})$ and $(S_{u},       c_{u})$ .The slope of this line is $\Delta$ and the intercept with the vertical axis is $-\Delta S_{d}=-(1+r) B$ .It can be seen that the line is never downward sloping,  so $\Delta\geq 0$ and the slope is always less than $45^{o}$ ,  SO $\Delta\leq 1$ 0.\1 The intercept with the vertical axis is zero or negative indicating that the portfolio that synthesizes the call option involves borrowing (selling rather than buying the risk-free asset)

The cost of synthesizing the option is the cost of the portfolio of $\Delta$ units of the shares and investing $B$ in bonds

$$c=\Delta S+B=\frac{pc_u+(1-p) c_d}{(1+r)}$$

Where $p=(r-d)/(u-d)$ exactly as before

### Risk Neutral Pricing

The previous two subsections have derived a simple expression for the price of the call option
$$c=\frac{pc_u+(1-p) c_d}{(1+r)}.$$

In this expression the value of the call optionisthepresentvalue ofaweighted average of the call at maturity,  either $Cu$ in the up state,  or $Cd$ in the down state. It is tempting to interpret $P$ in this equation as a probability. It is

![](./images/fHofODYmUoRXx8ufoFcmd4reB9x2D6irg.png)

Figure 1: THE $\Delta$ OF A CALL OPTION IN THE BINOMIAL MODEL

Important to notice two things about this formula. First $P$ cannot be the probability of an up movement in the stock as the probabilities of stock movements were not used in the calculation of the call value. Thus the value of the call is independent of the probabilities of the up or down movements in the stock price. Second the formula for the call is based on the present value of $pc_{u}+(1-p) c_{d}$ and is therefore valued as if this payoff was risk-free. Thus the probability $P$ is a risk-adjusted probability. It is simply the future value of the state price for the up-state.

To give an interpretation to $\not P$ imagine a situation where all individuals were indifferent to risk. Such as situation is known as a risk-neutral world In such a situation all individuals would agree to value any risky prospect

Simply by its expected present value. Since the formula for the value of the call is the expected present value when $p$ is interpreted as the probability of an upward movement in the stock,  $\rho$ is interpreted as a risk-neutral probability and this method of valuing the derivative is calledrisk neutral valuation. It is a simple and general principle that can be used for valuing all derivative securities.

To see how it can be used,  let's revisit our simple example again. Using the method of risk neutral valuation,  the expected value of the stock at the end of the period is $175 p+75 (1-p)$ ,  so the expected present value using the risk-neutral probabilities is

$$\frac{175 p+75 (1-p)}{(1+1/4)}.$$

This must equal the actual value of the stock which is 100. This gives one equation in one unknown,  $P$ ,  and solving gives $p=\frac{1}{2}$ .To value the call we simple use risk-neutral valuation again. The call at maturity is worth 75 in the up state and 0 in the down state,  so the expected value using the risk neutral probabilities is (1/2) 75 and the present value of this expectation is (1/2) 75/(5/4)=30

Again generalising this method,  $P$ is solved from the equation

$$S=\frac{p (1+u) S+(1-p)(1+d) S}{(1+r)}$$

To give $p=(r-d)/(u-d)$ exactly as before and this value of $P$ can then be used to compute the risk-neutral valuation for the option.

## Summary

We've considered a one period binomial model where the stock price can go either up or down by factors $(1+u)$ and $(1+d)$ .We can the use information

On the current stock price $S$ ,  the risk-free interest rate 7 and the strike price $K$ to determine the value of the option. We did this in three different ways. First by creating a riskless portfolio of the stock and the option. Second by creating a synthetic option that replicates the payoffs to the option using the underlying stock and the risk-free asset. In both cases we use an arbitrage argument that any two portfolios or assets that deliver the same payoffs must trade at the same price. Thirdly we derived the risk-neutral probability such that all assets and portfolios are valued by their expected present value. This ten allows the option to be evaluated in the same way using these riskadjusted probabilities.

The next thing to do is to allow for more than one period in the binomial model to see if the price of the option can still be calculated in a similar and similarly simple fashion.

# The $T_{1}$ -period Binomial Model

### Introduction

Once we have understood the one period binomial model it is very easy to extend the model to two or more periods so that derivatives with maturity in two or more periods can be examined. We will later show that using the binomial model can produce a very good approximation when it is extended to a sufficiently great number of periods. In these notes we consider how to extend the binomial model to more than two periods. This is relatively straightforward but requires the use of the binomial coefficients

Reading: Hull Chapter 11.

### The Two-Period Model

The binomial model is extended by adding to new branches of the tree after each node. Proceeding in the same way as with the one period model after each node the price of the underlying asset either increases by a factor of $u$ or decreases by a factor $d$ 1 Thus whether the value of the underlying after two periods is either $(1+u)^{2}S$ if the stock has gone up in two successive periods. $(1+d)^{2}S$ if the stock has gone down in two successive periods,  $(1+u)(1+d) S$ if the stock first went up and then went down,  or $(1+d)(1+u) S$ if the stock went down and then went up in the second period. Since $(1+u)(1+d)=$ $(1+d)(1+u)$，the value of the stock is the same whether it first went up and then down or down and then up. Thus the two branches of the tree recombine after two periods and there are only three possible values for the

Value of the underlying after two periods. (After $7 L$ periods there will be $n-1$ possible ending values for the underlying asset in such a recombinant tree).

The objective is to find the value of the option or derivative at the initial node of the tree. Let's consider an example with $u=0.75$ . $d$ = -0.25 $S=100$ ,  . $X=100$ and $r=0.25$ and extend it to two periods. The ending values for the underlying asset are 306.25,  131.25 and 56.25. To value the call option at the initial node we first value the call at the final nodes and then work backward. The value of the call at the final nodes is simply 206.25,  31.25 and 0 ,  that is the stock value minus the strike price. The value at the intermediate note then can than be computed using the methods of delta hedging,  synthetic options or risk neutral valuation used in the section on the one period model. The method of risk neutral valuation is simple because the risk neutral probability is the same for each period as it depends only on $u$，$d$ and 7 that are unchanging. Taking this risk-neutral valuation method,  the value following the first up move is

$$\frac{\frac{1}{2}(206.25+31.25)}{(1+\frac{1}{4})}=95$$

And the value of the call option following a down movement in the stock is

$$\frac{\frac 12 (31.25)}{(1+\frac 14)}=\frac{25}2.$$

Having foundthe value of the option after the firstperiod. The samemethod can be used to find the value at the initial node

$$\frac{\frac{1}{2}(95+\frac{25}{2})}{(1+\frac{1}{4})}=43.$$

### Risk Neutral Valuation and State Prices

The risk neutral valuation method also gives a very simple method of calculating the value of the option at the initial node. The risk neutral probability

Of two up movements in the underlying stock is ${\frac{1}{2}}\times{\frac{1}{2}}={\frac{1}{4}}$ . The probability of stock ending with a value of 131.25 is the probability of an up movement followed by a down movement plus the probability of a down movement followed by an up movement. Thus the risk neutral probability for this event is ${\frac{1}{2}}\times{\frac{1}{2}}+{\frac{1}{2}}\times{\frac{1}{2}}={\frac{1}{2}}$ . Thus the value of the call option can also be evaluated directly as
$$\frac{\frac{1}{4}(206.25)+\frac{1}{2}(31.25)}{(1+\frac{1}{4})^2}=43.$$

Likewise the state prices are easily calculated (by dividing the risk neutral probabilities by $(1+r)^{2}=\frac{25}{16}$ ) tobe $q_{uu}=\frac{4}{25}$：$q_{ud}=q_{du}=\frac{8}{25}$ and $q_{dd}=\frac{4}{25}$ Thus the call value could also easily be calculated as

$$\frac{4}{25}(206.25)+\frac{8}{25}(31.25)=43.$$

### American Options

As we have seen a European call option will have a positive time value as the lower bound for the European call is $S_{t}-X/(1+r)\geq S_{t}-X$ with inequality if $r>0$ .Since American options can'tbe worth less than equivalent European options it follows that American call options on non-dividend paying stock will not be exercised early because selling the option will always dominate exercising it. Intuitively an early exercise will involving paying the strike price earlier and this is undesirable. However,  American put options can be exercised early because this will involve receiving the strike price earlier. The two period binomial model can be used to illustrate this possibility

Consider a put option in our example with a strike price $X=100$ .The value of this put option at the final nodes is 0，0 and 43.75. Thus the value of the put option following an up movement in the first period is 0 as the option can never get back in the money. However,  following a down movement in the first period the value of the option is using the state prices

${\frac{2}{5}}(41.75)=17.5$ .But early exercise of the option would give 25. Thus early exercise is the better alternative and the option must have a value of 25 if it is of the American type. At the initial node the option is thus worth 10 if it is an American option and 7 if it is a European option that cannot be exercised early at the end of the first period.

## Extending the model to $n>2$ periods

### Pascal's Triangle

In the one-period binomial model there are two possible end values and in the two-period binomial model there are three possible end values. Extrapolating we have that in the $7 l$ -period binomial model there are $n+1$ possible end values. The number of ways that each value is reached is determined by Pascal's triangle. Pascal's triangle is shown in Table 1 for $n=5$ .Period 0 corresponds to the initialnode of the binomial tree. Period 1 corresponds to the possible values after the first period and so on. In period 2 there is one way to reach the two outer sides of the triangle corresponding to either two up or two down returns. There are two ways to reach the middle node. Either an up followed by a down or a down followed by an up. The numbers in Pascal's triangle are easy to calculate. Simply put 1 s along the edges of the triangle and to find the other numbers take the two numbers above and add them together

### Binomial Coefficients

The numbers inPascal's triangle are called the binomial coefficients and the binomial coefficients are usually written $\binom nk$ for $n,       k\geq 0$ where

$$\begin{pmatrix}n\\k\end{pmatrix}=\frac{n!}{k! (n-k)!}$$

<table>
	<tbody>
		<tr>
			<th>Period 0 1</th>
			<th> </th>
			<th> </th>
			<th> </th>
			<th> </th>
			<th>1</th>
			<th>1</th>
			<th> </th>
			<th> </th>
			<th> </th>
			<th> </th>
		</tr>
		<tr>
			<td>Period 1</td>
			<td> </td>
			<td> </td>
			<td>1</td>
			<td>1</td>
			<td>1</td>
			<td>1</td>
			<td>1</td>
			<td> </td>
			<td> </td>
			<td> </td>
		</tr>
		<tr>
			<td>$\mathbf{Period}$ 2</td>
			<td> </td>
			<td>1 1</td>
			<td>1</td>
			<td> </td>
			<td>2</td>
			<td>2</td>
			<td>1</td>
			<td> </td>
			<td> </td>
			<td> </td>
		</tr>
		<tr>
			<td>Period 3</td>
			<td> </td>
			<td>1</td>
			<td>3</td>
			<td>3</td>
			<td>3</td>
			<td>3</td>
			<td>3</td>
			<td>1</td>
			<td> </td>
			<td> </td>
		</tr>
		<tr>
			<td>Period 4</td>
			<td>1</td>
			<td>1</td>
			<td>4</td>
			<td> </td>
			<td>6</td>
			<td>6</td>
			<td>$\angle 1$</td>
			<td colspan="3">1 1</td>
		</tr>
		<tr>
			<td>Period 5 1 T</td>
			<td>1</td>
			<td>5</td>
			<td>10</td>
			<td>10</td>
			<td>0</td>
			<td>10</td>
			<td>10</td>
			<td>5</td>
			<td> </td>
			<td>1</td>
		</tr>
	</tbody>
</table>

Table 1: Pascal's Triangle

Is the $(k+1)$ -th number in the $(n+1)$ -th row of the triangle. Here $k!=$ $k\times k-1\times k-2\times\ldots\times 2\times 1$ and by convention 0!=1 .Thus if $n=4$ and $k=2$ ,  then
$$\begin{pmatrix}4\\2\end{pmatrix}=\frac{4!}{2!\times 2!}=\frac{4\times 3\times 2\times 1}{(2\times 1)(2\times 1)}=\frac{24}{4}=6.$$

The binomial coefficients show us the number of ways the returns can be generated by $k$ down returns and $n-k$ up returns

### Binomial Variable

In our binomial model there are two outcomes for the stock price “up"or "down". We can treat this as a random variable and associate with each event a probability. Let $\pi~=~{\mathrm{Prob}}[$ "up-state] and probability $1-\pi=$ Prob[down-state]. The probability of having $k$ up states after $7 L$ periods is given by
$$\pi (k)=\begin{pmatrix}n\\k\end{pmatrix}\pi^k (1-\pi)^{n-k}.$$

We say this is a binomial random variable with parameter 71 .For example say $n=4$ and there are $k=2$ “"up"-states. The are ${\binom 42}=6$ ways in which this can occur. Thus the probability of ‘up"-states in four periods is $6\pi^{2}(1-\pi)^{2}$ We shall need to know the probability of having more than a certain number of “up"-states. Let $B_{\pi}(x)$ denote the probability that the binomial random variable with parameter 7 T is greater than $JL$ after 772 periods. That is the

Probability that we have $JL$ or more than $iL$ “up"-states in $TL$ periods. This is given by
$$B_\pi (x)=\sum_{k=x}^n\binom{n}{k}a^k (1-a)^{n-k}.$$

For example,  if we want to know the probability that we have two or more up states in four periods we have to calculate

$$\begin{pmatrix}4\\2\end{pmatrix}\pi^2 (1-\pi)^2+\begin{pmatrix}4\\3\end{pmatrix}\pi^3 (1-\pi)^1+\begin{pmatrix}4\\4\end{pmatrix}\pi^4 (1-\pi)^0=6\pi^2 (1-\pi)^2+4\pi^3 (1-\pi)+\pi^4.$$

### The distribution of the end values

Let $U$ = $( 1+ u)$，$D$ = $( 1+ d)$ and $R$ = (1 + $r)$ .If there are $k$ down returns and $n-k$ up returns then the end value of the asset after 772 periods is $S_{n}=S_{0}U^{n-k}D^{k}$ .The number of ways of attaining this ending value is given by the binomial coefficient $\binom nk$ .Suppose that the probability of an "up”return is $7 i$ and the probability of a down return is $(1-\pi)$ .Then the probability of reaching the end value of $S_{n}=S_{0}U^{n-k}D^{k}$ by any one route is $\pi^{n-k}(1-\pi)^{k}$ . Thus the probability of reaching this end value is the number of ways of reaching it $\binom nk$ times the probability $\pi^{n-k}(1-\pi)^{k}$ of reaching it by any given route. The information is summarized in Table 2

The expected value of the asset after $Tl$ periods is givenby the equation

$$\sum\limits_{k=0}^n\binom{n}{k}\pi^k (1-\pi)^{n-k}S_0 U^kD^{n-k}.$$

Although complicated in form this is very routine computation that can be madein a spreadsheet or other software

<table>
	<tbody>
		<tr>
			<th>$; S_n$ End Value</th>
			<th>Returns</th>
			<th>${\mathrm{Probability}}$</th>
		</tr>
		<tr>
			<td>$S_0 U^{n}D^{0}$ $n$</td>
			<td>$n$ ups and 0 downs</td>
			<td>$\pi^n (1-\pi)^0$</td>
		</tr>
		<tr>
			<td>$S_{0}U^{n-1}$ ${}^{1}D^{1}$ $r 2$</td>
			<td>$n-1$ ups and 1 downs</td>
			<td>- (1 ,  一 - $\pi )$ T</td>
		</tr>
		<tr>
			<td>$S_{0}U^{n-2}D^{2}$ $r\boldsymbol{l}$</td>
			<td>$l-2$ ups and 2 downs $\boldsymbol{r}2$ </td>
			<td>(1) $\pi$ -</td>
		</tr>
		<tr>
			<td>$S_{0}U^{n-3}D^{3}$ $m$</td>
			<td>$\boldsymbol{r}2$ $\imath-3$ ups and 3 downs</td>
			<td>$)\pi^{n-3}(1-\pi) 3$ 1.</td>
		</tr>
		<tr>
			<td>$S_{0}U^{3}D^{n-3}$ 3 $u$</td>
			<td>ups and $n-3$ downs 3</td>
			<td>$^{3}(1-\pi^{\prime}$ TI</td>
		</tr>
		<tr>
			<td>$S_{0}U^{2}D^{n-2}$ 2 u$_{\mathrm{I}}$</td>
			<td>2 ups and $n-2$ downs</td>
			<td>7 {:}(1 一 T</td>
		</tr>
		<tr>
			<td>$S_{0}U^{1}D^{n-1}$ $1 u]$</td>
			<td>ups and $n-1$ downs 1</td>
			<td>7 1 (1 一 T</td>
		</tr>
		<tr>
			<td>$S_{0}U^{0}D^{n}$ 0</td>
			<td>0 ups and $n$ downs</td>
			<td>$^{0}(1-\pi)$</td>
		</tr>
	</tbody>
</table>

Table 2: End Asset Values and Probabilities in $7 l$ -period Binomial Mode

### Pricing the Call Option

Using risk-neutral valuation,  the price of the call which matures in. $Tt$ periods is calculated as

$$c_0=\frac{1}{R^n}\left (\sum_{k=0}^n\binom{n}{k}\rho^k (1-\rho)^{n-k}\max[S_0 U^kD^{n-k}-X,       0]\right)$$

Where $\rho=(R-D)/(U-D)$ is the risk-neutral probability and $U$ and $D$ are the factors given above. Thus given the strike price $X$ ,  the time to maturity $7 t$ ,  the risk-free interest rate 7 it is possible to calculate the callvalue

Let $JL$ denote the minimum number of up branches that need to be taken for the terminalvalue $S_{0}U^{x}D^{n-x}$ tobe greater than the strike price $X$ .Then the above formula can bewritten as

$$c_0=S_0\sum_{k=x}^n\begin{pmatrix}n\\k\end{pmatrix}\rho^k (1-\rho)^{n-k}\frac{U^k}{R^k}\frac{D^{n-k}}{R^{n-k}}-\frac{X}{R^n}\sum_{k=0}^n\begin{pmatrix}n\\k\end{pmatrix}\rho^k (1-\rho)^{n-k}.$$

Remember that $B_{\pi}(x)$ denotes the probability that the binomial random variable with parameter 71 has at least $2 L$ up-states after $Tl$ periods. Letting

$iL$ be the number of “up-states"such that the end value of the stock is at least the strike price $X$，the call option price can be written more simply as

$$c_0=S_0 B_s (x)-\frac{X}{R^n}B_\rho (x)$$

Where $s=\rho U/R$ .This follows since

$$\begin{aligned}
(1-s)& =\left (1-\frac{\rho U}{R}\right)=\left (1-\frac{(R-D) U}{(U-D) R}\right) \\
&=\frac{(U-D) R-(R-D) U}{(U-D) R}=\frac{D}{R}\frac{(U-R)}{(U-D)}=\frac{D}{R}\rho.
\end{aligned}$$

This is really exactly the same as in the one period model. To see Suppose for simplicity thatthe callhasapositive value in theup state so $x=1$ and $n=1$ .Then we have seen that the value of the call in the one period model is
$$c_0=\frac{1}{R}\rho (US_0-X)=S_0\rho\frac{U}{R}-\frac{X}{R}\rho=sS_0-\rho\frac{X}{R}.$$

Likewise using the formula for replicating the call we have

$$\Delta=\frac{US_0-X}{(U-D) S_0}\quad\text{and}\quad B=-\frac{D}{R}\frac{US_0-X}{(U-D)}.$$

Therefore the value of the replicating portfolio is

$$\Delta S_0+B=\frac{US_0-X}{(U-D)}-\frac{D}{R}\frac{US_0-X}{(U-D)}$$

Which can be rewritten as

$$\Delta S_{0}+B=\frac{1}{R}\left (\frac{US_{0}(R-D)}{(U-D)}-X\frac{(R-D)}{(U-D)}\right)=\rho S_{0}\frac{U}{R}-\rho\frac{X}{R}=sS_{0}-\rho\frac{X}{R}.$$

## Example

Afour period example is illustrated inFigure 1. The example is the same as before with with $u=0.75$ ， $d=-0.25$ ， $S=100$ ， $X=100$ and $r=0.25$ but

Extended over four periods. The upper diagrams shows the stock price in all possible cases,       the middle diagram the call price and the lower diagram the replicating portfolio of $\Delta$ units of the stock and borrowing a certain amount of the risk-free asset

As can be seen the amount of stock required and the amount borrowed in order to replicate the call change over time. Thus the replicating portfolic is dynamic and it is necessary to reoptimise the portfolio every period. It is however,       true that the change in the portfolio required is self-financing That is the proceeds from the sale of the old portfolio are just that required to buy the new portfolio at every node of the tree.

Exercise: Check that the replicating portfolio is self-financing

## Arithmetic and geometric rates of return

This section shows an important difference between the arithmetic and the geometric mean rate of return. It is shown that the geometric mean is always less than the arithmetic mean and that the difference between the two is approximately half the variance of the return. This is an important distinction because it implies that if the rate of return is symmetrically distributed then the final asset value will be asymmetrically distributed. In particular the median of the distribution willfall below the mean of the distribution. Thus one should conclude that one should "expect less than the expected". An important lesson tolearn in finance

Suppose we have an asset worth 100 and for two successive periods it increases by $20\%$ .Then the value at the end of the first period is 120 and the value at the end of the second period is 144.

Now suppose that instead the asset increases in the first period by $30\%$ and in the second period by $10\%$ .The average or arithmetic mean of the

Return is $20\%$ .However the value of the asset is 130 at the end of first period and 143 at the end of the second period. The variability of the returnhas meant that the asset is worth less after two periods even though the average return is the same. We can calculate the equivalent per period return that would give the same value of 143 after two periods if there were no variance in the returns. That is the value $V$ that satisfies

$$143=100 (1+\nu)^2.$$

This value is known as the geometric mean. It is another measure of the average return over the two periods. Solving this equation gives the geometric mean as $\nu=0.195826$ or 19.58% per period? Which is less than the arithmetic rate of return per period.

There is a simple relationship between the arithmetic mean return,       the geometric mean return and the variance of the return. Let $\mu_{1}=\mu+\sigma$ be the rate of return in the first period and let $\mu_{2}=\mu-\sigma$ be the rate of return in the second period. Here the average rate of return is $=\frac{1}{2}(\mu_{1}+\mu_{2})=\mu$ and the variance of the two rates is $\sigma^{2}$ .The geometric rate of return $\mu$ satisfies $(1+\nu)^{2}=(1+\mu_{1})(1+\mu_{2})$ .Substituting and expanding this gives

$$1+2\nu+\nu^2=(1+\mu+\sigma)(1+\mu-\sigma)=(1+\mu)^2-\sigma^2=1+2\mu+\mu^2-\sigma^2$$

Or

$$\nu=\mu-\frac{1}{2}\sigma^{2}+\frac{1}{2}(\mu^{2}-\nu^{2}).$$

Since rates of return are typically less than one,       the square of the return is even smaller and hence the difference between two squared percentage terms is smaller still. Hence we have the approximation $\nu\approx\mu-\frac{1}{2}\sigma^{2}$ or

$$\mathrm{geometric~mean}\approx\mathrm{arithmetic~mean}-\frac{1}{2}\mathrm{variance}.$$

This approximation will be better the smaller are the interest rates and the smaller is the variance. In the example $\mu=0.2$ and $\sigma=0.1$ SO $\frac{1}{2}\sigma^{2}=0.005$ and $\mu-\frac{1}{2}\sigma^{2}=0.1950$ which is close to the actual geometric mean of 0.1958.

## Expectless than the expected

We can see the same difference between arithmetic and geometric rates of return in our binomial model to show that the end values for the underlying asset will be asymmetrically distributed. Consider a binomial model where the $up$ and down factors are $U=1.3$ and $D=1.1$ .Thus the asset either increases by $30\%$ or by $10\%$ .Suppose that each is equally likely so that the average return is $20\%$ .Let the initial value of the asset be 100. Then after one period the ending values are 130 or 110 each with probability $\frac{1}{2}$ . This is a symmetric distribution centered around the average value of 120. After two periods the ending value is either 169 if there are two successive ups,       143 if there is either one up and one down or one down and one up,       or 121 if there are two downs. The probability of these three outcomes,       169,      143 and 121 are $\frac{1}{4}$ ， $\frac{1}{2}$ and $\frac{1}{4}$ respectively. Thus the expected value after two periods is

$$\frac{1}{4}\times 69+\frac{1}{2}\times 143+\frac{1}{4}\times 121=144.$$

However the return is less than 144 in three of the four possible ending values Thus after two periods the distribution of the end values is asymmetric with most of the distribution below the average value. We say that the distribution of the ending values is skewed to the right. The most likely out,       the mode,       is 143 and it is also in this case equal to the median as the ending value is equally likely to be above or below 143.

Consider the two-period model where the up and down factors are $1+\mu+\sigma$ and $1+\mu-\sigma$ ， the initial value of the asset is $S_{0}$ and both up and down

Movements are equallylikely. Then the expectedvalue after two periods is

$$S_0\left (\frac{1}{4}(1+\mu+\sigma)^2+\frac{1}{2}(1+\mu+\sigma)(1+\mu-\sigma)+\frac{1}{4}(1+\mu-\sigma)^2\right)=S_0 (1+\mu)^2.$$

The median value however is

$$S_0 (1+\mu+\sigma)(1+\mu-\sigma)=S_0\left ((1+\mu)^2-\sigma^2\right)$$

So that the median is below themean by an amount equal to the variance Since we have already shown that $(1+\nu)^{2}=(1+\mu)^{2}-\sigma^{2}$ ， the median of the end value is just $S_{0}(1+\nu)^{2}$

The binomial modelis easily extended from two to 77 periods. We have in each period the return changes by the factor $U$ or $D$ ,      thus the returns in each period are identically and independently distributed. Let $U=1+\mu+\sigma$ and $D=1+\mu-\sigma$ as before and suppose that the probability of either return is equally likely. Then the median return (if $Tl$ is large and even) is

$$S_0\left ((1+\mu+\sigma)^{\frac{n}{2}}\right)\left ((1+\mu-\sigma)^{\frac{n}{2}}\right)=((1+\mu+\sigma)(1+\mu-\sigma))^{\frac{n}{2}}$$

As there will be roughly an equal number of up returns and down returns Thegeometric return thatproduces the same outcome after $Tl$ periods is $(1+g)^{n}$ ,      thus
$$(1+\nu)^n=((1+\mu+\sigma)(1+\mu-\sigma))^\frac{n}{2}$$

Or $(1+\nu)^{2}=(1+\mu+\sigma)(1+\mu-\sigma)$ which is exactly as before. Thus the same approximation $\nu\approx\mu-\frac{1}{2}\sigma^{2}$ applies in the $7 t.$ -period model as well. Since the geometric return gives the median value for the underlying asset and the arithmetic mean gives the average value,       the median is always below the average. Thus one should always expect tohave less than the average value more than half the time.

Example:u=0.75,       $d=-0.25$ $r=0.25$ $x=100$

![](./images/fnaAhnGefU3qDKBgLiUkRuOTfKUeeicVz.png)

Figure 1: FOUR-PERIOD BINOMIAL EXAMPLE

# OPTION RISK

### Introduction

In these notes we consider the risk of an option and relate it to the standard capital asset pricing model. If we are simply interested in valuing the option then we can largely ignore this issue. We have seen from our notes on the oneperiod binomial model that to price an option we only need to know the price of the underlying asset. It is not necessary to know whether the underlying asset is priced fairly relative to other assets or indeed anything about other assets at all. However,       if we are interested in forming an investment portfolic that includes options or other derivatives,       then the risk and return of that portfolio will depend on the risk and return characteristics of the options. Thus we will need to know how the $\beta$ of an option relates to the $\beta$ of the underlying stock.

We can examine the issue of risk in a simple binomial model. So this is what we shall do. Most textbooks on options don’t discuss risk and therefore you will need to keep these notes for your revision.

## Risk in the binomial model

We'll use the simple example we used when discussing the one period binomial model. Suppose the price of the underlying stock is 100 and at the end of the period it has either risen to 175 or has fallen to 75. That is $u=0.75$ and $d=-0.25$ ,       so that the value of the stock after one period in the up state is $100 (1+u)=175$ and the value in the down state is $100 (1+d)=75$ .The net growth rate of the value of the stock in the up state is $75\%$ ,       and the net growth in the value of the stock in the down state is $-25\%$

We showed that in determining the price of the option,       the probability that the stock price rises of falls was irrelevant. Now however suppose that the true probability of the up state is $\pi$ = 4/5 and the probability of the down state is $(1-\pi)=1/5$ 0.\1 The expected rate of return on the stock is therefore $\mu_{S}=(4/5) 75+(1/5)(-25)=55\%$ and with an interest rate of $25\%$ the excess over the risk-free rate is $\mu_{S}-r=55-25=30\%$ .Given that the price of the call is 30,       the rate of return on the call option is (75-30)/30 or $150\%$ in the up state and $-100\%$ in the down state. Thus the expected rate of return on the call option is $\mu_{C}=100\%$ and the excess return over the risk-free rate is $\mu_{C}-r=75\%$ .Thus the excess return on the call is 2.5 times the excess return on the underlying asset. We know that this extra return will only come at the cost of extra risk.

The standard deviation of the rate of return on the stock is often simply referred to as the stock's volatility. The volatility of the stock is

$$\sigma_S=\sqrt{\frac{4}{5}(75-55)^2+\frac{1}{5}(-25-55)^2}=40\%$$

And the standard deviation of the rate of return on the call option,       or the call's volatility is

$$\sigma_C=\sqrt{\frac{4}{5}(150-100)^2+\frac{1}{5}(-100-100)^2}=100\%.$$

Thus the standard deviation of the call returns is again 2.5 times the standard deviation of the stock returns.

Now remember that $\Delta$ measures the responsiveness of the value of the call to changes in the value of the stock. In our example $\Delta=3/4$ .It is natural to measure this change in percentage terms. That is we define

$$\Omega\equiv\frac{S}{c}\Delta $$

To be the elasticity of the option,       that is the percentage change in the call value relative to a given percentage change in the stock value. In our example $S=100$ and $c=30$ ,      so that $\Omega=2.5$

This is not a coincidence. If 711 is the probability of the up state and $1-\pi$ is the probability of the down state then expected rate of return on the stock and its volatility are：

$$\mu_S=\pi u+(1-\pi) d\quad\text{and}\quad\sigma_S=\sqrt{\pi (1-\pi)}(u-d).$$

Equally the expected rate of return on the call and its volatility are

$$\mu_C=\frac{\pi c_u+(1-\pi) c_d-c}{c}\quad\mathrm{and}\quad\sigma_C=\sqrt{\pi (1-\pi)}\frac{c_u-c_d}{c}.$$

Then remembering that $\Delta$ is the change in the call price over the change in the stock price,       we have

$$\Omega\equiv\frac{S}{c}\Delta=\frac{S}{c}\frac{c_{u}-c_{d}}{(u-d) S}=\frac{c_{u}-c_{d}}{c (u-d)}.$$

It is therefore clear using the expressions above for $0 C$ and $0 S$ that

$$\sigma_C=\Omega\sigma_S.$$

Thus the ratio of the call and stock volatilities is exactly the option elasticity

Remember thatin synthesizing the calloption we used the equations

$$\Delta (1+u) S+(1+r) B=c_u$$

$$\Delta (1+d) S+(1+r) B=c_d.$$

To show that the call price is $c=\Delta S+B$ .We can therefore substitute for $B=c-\Delta S$ to write these two equations as

$$\Delta (1+u) S-c_u=(1+r)(\Delta S-c)$$

$$\Delta (1+d) S-c_{d}=(1+r)(\Delta S-c).$$

Multiplying the first equation by 71 and the second equation by $(1-\pi)$ and adding the resulting two equations gives

$$\pi (\Delta (1+u) S-c_u)+(1-\pi)(\Delta (1+d) S-c_d)=(1+r)(\Delta S-c).$$

Then dividing by $C$ ，using the definition of $\Omega$ = $\Delta ( S/ c)$ and after some rewriting gives

$$\mu_C-r=\Omega (\mu_S-r)$$

Or

$$\mu_C=r+\left (\frac{\mu_S-r}{\sigma_S}\right)\sigma_C.$$

This is of course the standard equation used to express an asset as a portfolic of the stock and the risk-free asset,       that we have seen previously in Asset Pricing and Portfolio Choice. As we know the call option can be replicated by a fraction of the stock and selling the risk-free asset this should not be surprising. That is the risk and return of the call lie on somewhere on the risk-return line with intercept of 7 and slope of $(\mu_{S}-r)/\sigma_{S}$ .The elasticity $\Omega 2$ gives the position of the call along this line. Rewriting our equation on the excess return again

$$\mu_C=\Omega\mu_S+(1-\Omega)r.$$

Thus the call can be seen as the portfolio of the stock and the risk-free asset with a weight of $\leq 2$ attached to the stock. Since we have seen that to synthesize the call requires borrowing the risk-free asset,       we have that $\Omega>1$ and the callvolatility is always greater than the stock volatility

This is seen in Figure 1. In the diagram the call option is always to the right of the underlying stock as it will have higher volatility and higher expected return than the underlying asset itself. It can also be seen that a call with a higher strike price will be more risky and therefore will lie further out along the risk and return line.

If the same analysis is repeated for a put option it is found that $\Delta$ is negative and $B$ is positive. This means that replicating the put option involves

![](./images/fS3aWRHCn97wSgeec43nok6ydwF4uck3Y.png)

Figure 1: RISK-RETURN D 1 AGRAM: $(\sigma,      \mu)$

Selling the underlying asset and buying the risk-free asset (investing). As the underlying asset is sold short a put option will be located on the lower arm of the risk-return diagram. The expected return is reduced because there is a future obligation from the short sale rather than a return although the obligations are still risky and therefore have a positive standard deviation. It can therefore be seen that put options are never of themselves effcient portfolios although since they will be negatively correlated with the underlying asset they can provide good hedging opportunities

We now consider the $\beta$ of a call option. The Capital Asset Pricing Model shows that for any asset,       the ezcess return or risk-premium satisfies

$$\mu_S-r=\beta_S (\mu_M-r)$$

Where $\mu_{M}$ is the expected rate of return on the market portfolio and $\beta_{S}$ is the covariance of the stock's rate of return with the market divided by the variance of the rate of return on the market portfolio

It is therefore simple to combine our excess return equation for the call and the CAPMformula to derive

$$\mu_C-r=\Omega\beta_S (\mu_M-r).$$

It can be shown that $\Omega\beta_{S}$ is the covariance of the rate of return of the call with the market divided by the variance of the rate of return of the market,       so that the beta of the call is $\beta_{C}=\Omega\beta_{S}$ .The option beta is simply the elasticity time the beta of the underlying asset. Provided that $\beta_{S}>0$ ,      since $\Omega>1$ for a call option,       it is the case that $\beta_{C}>\beta_{S}$ and the beta for the call is higher than the beta of the underlying asset. 2 This is illustrated in Figure 2 which shows the security market line which plots expected return $\mu$ against $\beta$ .The security market line intercepts the vertical axis at 7 the rate ofreturn on the risk-free asset which isuncorrelatedwith the market return (as it is risk-less) and hence has a zero beta. Since $\Omega\geq 1$ the call option has a higher $\beta$ than the underlying asset and so lies to the right of the stock on the security market line. Put options on the other hand are anti-correlated with the stock,       their value goes up as the stock goes down,       so they have a negative $\beta$ and are located to the left of the risk-free asset on the security market line.

![](./images/fldFEUqZq5HbQYGRmx1yNbXhTNK4pFgWx.png)

## Figure 2: SECURITY MARKET LINE: $(\beta,      \mu)$

Let's return once again to our simple example and suppose that the expected rate of return on the market portfolio is $40\%$ .Then since the excess return on the stock is $30\%$ and the excess return on the market portfolio is $40-25=15\%$ ,      the beta of the stock is $\beta_{S}=2$ and the beta of the option is $\beta_{C}=\Omega\beta_{S}=5$ .Since $\beta>0$ and the expected rate of return on the market portfolio is greater than the risk-free rate,       the expected rate of return on the call is also greater than the risk-free rate. Remember that the expected rate of return on the call using the risk-neutral probabilities is equal to the risk-free rate. Thus the risk-neutral probability for the up state is less than the true probability,       $p<\pi$ .This simply reflects that in adjusting for the risk of the call the probability of the high rate of return is shaded downward to

Refect an aversion to risk. In our example the risk-neutral probability is 1/2 and the actual probability of the up state is 4/5

## Summary

These notes have provided a connection between option pricing and standard models of portfolio choice and the Capital Asset Pricing Model (CAPM). The connection is provided by the option elasticity $S 2$ .We have seen previously that $\Delta$ measures how much of the stock to buy to create a riskless hedge or to replicate the option. The option elasticity,       $\leq 2$ is a proportionate measure of $\Delta$ ， $\Omega=S\Delta/c$ .The elasticity $S 2$ ：therefore measures the proportion of the portfolio placed in the underlying asset in order to replicate the option. It is therefore a portfolio weight rather a quantity of stock bought. The elasticity of the call option will be no less than one since to replicate the call option it will be necessary to borrow,       that is go short in the risk-free asset,       to fund the acquisition of the underlying asset. The elasticity also can be combined with the beta of the stock,       $\beta_{S}$ to calculate the beta of the call option $\beta_{C}=\Omega\beta_{C}$ Since $\Omega\geq 1$ the call option will be a more aggressive asset that the underlying stock.

# Exotic Options

These notes describe the payoffs to some of the so-called erotic options. There are a variety of different types of exotic options. Some of these options are path dependent so that the value of the option depends on the previous values of the underlying as well as the current price of the underlying

Keywords: Digital options,       Barrier options,       Path dependent options,       Lookback options,       Asian options.

Reading Hull Chapter 22 [Just read about the different types exotic options and their payoffs. Ignore the equations describing how they are priced for the moment.]

### Introduction

American and European puts and calls are sometimes referred to as plain vanilla options. There are however a wide variety of other types of options that are traded. These are sometimes referred to as exotic options. In the past most exotic options were traded in over the counter markets rather than exchanges,       but more recently these alternative option types can be found on exchange markets too. The variety and types of options that are available are really only limited by imagination. As long as the payoff can be well specified,       it can depend on any property of the price of the underlying asset. The following list just gives a few examples

## Digital Options

One simple type is the digital or binary option. The payoff to a digital option depends on whether the price of the underlying asset at maturity is greater

Or less than the strike price. Thus for a digital call option the payoff at maturity is:
$$c_T^b=\left\{\begin{array}{ll}0&\text{if}S_T\leq X\\1&\text{if}S_T>X\end{array}\right.$$

And the payoff at maturity to a digital put option is

$$p_T^b=\left\{\begin{array}{ll}1&\text{if}S_T\leq X\\0&\text{if}S_T>X.\end{array}\right.$$

## Range Forward Contract

A range forward contract specifies a band $[X_{2},       X_{1}]$ .If the price of the underlying at maturity is within the band then the holder is obliged to buy the asset at its current price. If the price of the underlying at maturity is below $X_{2}$ then the holder has to buy at $X_{2}$ and if the price of the underlying at maturity is above $X_{1}$ then the holder has to buy at $X_{1}$ .The range forward is designed so that the initial value of the contract is zero and therefore similar to a forward contract. It is equivalent to a combination of a long call option with a strike price of $X_{1}$ and a written put option with a strike price of $X_{2}$ ，where the strike prices are chosen so that the put and the call have the same prices. The payoff at maturity to a range forward contract is $\operatorname*{max}[S_{T}-X_{1},       0]-\operatorname*{max}[X_{2}-S_{T},       0]$

### Break Forward

A break forward contract specifies a delivery price $K$ and a break price $B$ at which the forward price can be broken. Thus at the maturity date,       the break price will be paid on a long forward position if $-B>S_{T}-K$ .For example if the break price is $\$10$ and the delivery price is S 100,       the payoff to the long forward position is $S_{T}-100$ .If $S_{T}<90$ ,       there will be a loss of more than S 10 and it will be worth while to pay the break price of $\$10$ .The payof

At maturity is therefore $\operatorname*{max}[S_{T}-100,      -10]=\operatorname*{max}[S_{T}-90,      0]-10$ .This then is just like a call option with a strike price of S 90 but where a payment of $\$10$ is paid at maturity. Since the break forward costs nothing when it is initiated,       it is essentially a deferred payment option,       where the payment of the initial cost of the option is deferred until maturity. Suppose that the interest rate until maturity is $\frac{1}{9}$ ,       then in our example a call option with a strike price of $\$90$ which costs $\$9$ us equivalent to a long break forward with a delivery price of $\$100$ and break price of $\$10$ .In general letting 7 denote the interest to maturity and $C_{t}$ the current price of the call option with a strike price $X$ ,       then the call option is equivalent to a long position in a break forward contract with delivery price $X+(1+r) c_{t}$ and break price $(1+r) c_{t}$

## Rainbow Options

It is possible to write options on more than one underlying asset. Such options are called rainbow options. For example a put option may specify that you have the option to deliver one from a range of different assets. Clearly if the exercise price is the same for all assets specified,       and if you decide to exercise your option to sell,       you will choose to deliver that asset with the lowest current price. Thus if there are two assets specified and their prices are $S^{\mathrm{I}}$ and $S^{2}$ ,       then the intrinsic value of the put option is

$$x\text{Intrinsic value}=\left\{\begin{array}{ll}X-\min[S^1,       S^2]&\text{if}\min[S^1,       S^2]\leq X\\0&\text{if}\min[S^1,       S^2]>X.\end{array}\right.$$

## "As-you-like-it" Options

This is an option where the holder can decide at a specific time whether the option is a put or a call option. Suppose that the where the decision must be made is $t$ . The value of the option at this time is $\max[c_{t},       p_{t}]$ .If the as-you-like-option offers the choice between a European put and a European

Call with the same strike price and same maturity date $T$ ,      then the put call parity condition can be used and

$$\max[c_t,       p_t]=\max\left[c_t,       c_t+\frac{X}{(1+r)}-S_t\right]=c_t+\max\left[0,      \frac{X}{(1+r)}-S_t\right]$$

Where 7 is the risk-free interest rate between $t$ and thematurity date $T$ .The as-you-like-it option therefore consist of aportfolio of a call option with strike price $X$ and maturity at date $T$ and a put option with strike price $\frac{X}{(1+r)}$ and maturity at date $t$

## Barrier Options

Barrier options have a payoff that depends on whether the underlying asset reaches a certain level,       the barrier,       prior to maturity. There are two main varieties of barrier option. The knock-in only pays out if the price of the underlying reaches the barrier and the knock-out only pays out if the underlying does not reach the barrier. These can be further classified by whether the barrier is set above or below the initial value of the underlying asset. If the barrier is above the initial value of the underlying,       it is said to be an up option. If the barrier is below the initial value of the underlying asset,       it is said tobe a down option. The payoff at maturity for a down-and-out call option is
$$c_T^{down-out}=\left\{\begin{array}{lll}c_T&\text{if}\:S_t>B&\text{for all}\: t\leq T\\0&\text{if}\:S_t<B&\text{for any}\: t\leq T\end{array}\right.$$

Where $B$ is the barrier and. $CT$ is the value of the plain vanilla call option. Clearly if you own both a down and out call option together with a down an in call option on the same underlying with the same barrier,       strike prices and maturity,       then you have a plain vanilla call option. So for calls and puts and down and up options:

$$\mathrm{vanilla}=\mathrm{in}+\mathrm{out}.$$

Barrier option sometimes specify a double barrier with an upper and lower limit. Sometimes the barrier changes over time. Sometimes a rebate is paid if the barrier is hit. Some options become barrier options if a particulan value,       usually the strike price,       for the underlying is reached

### Lookback Options

Lookback options have a payof that depends on the maximum or minimum value that the underlying asset reaches during the lifetime of the option. The payoff to maturity of a European-style lookback call is $S_{T}-S_{min}$ where $S_{min}$ is the minimum value that the underlying achieves over the option’s lifetime The payoff to maturity of a European-style lookback put is $S_{max}-S_{T}$ where $S_{max}$ is the maximum value that the underlying achieves over the option’s lifetime. Note that if you hold both a lookback put and a lookback call your payoff is $S_{max}-S_{min}$ . It is like you bought when the price was lowest and sold when the price was highest. Of course such sweet deals are likely to be costly.

## Asian Options

An Asian option has a payoff that depends on the average price of the underlying asset from its starting date. Thus the intrinsic value of an average price Asian call option is $\operatorname*{max}[0,       S_{ave}-X]$ ,      where $S_{ave}$ is the average value of the asset from the start of the option to the current date. Another type of Asian option is the average strike price type,       where the strike price is the average value. In this case the intrinsic value of the call is $\operatorname*{max}[0,       S_{t}-S_{ave}]$ and the intrinsic value of the put is $\operatorname*{max}[S_{ave}-S_{t},       0]$

# Asset Price Dynamics

### Introduction

These notes give assumptions of asset price returns that are derived from the efficient markets hypothesis. Although a hypothesis,       there is widespread empirical evidence that broadly supports the hypothesis and therefore the assumptions made on the process governing asset price changes. Continuous time stochastic processes are discussed and the geometric Brownian motion model for stock price changes is derived. We first look at rates of return as if they are known for certain and then consider the realistic case that asset price returns are unknown in advance

Keywords: continuously compounded rate of return,       stochastic process,       ran dom walk,       martingale,       Markov property Wiener process,       geometric Brownian motion,       Ito calculus

Reading: You should read Hull chapter 12 and perhaps the very first part of chapter 13.

### Rates of Return

### The Rate of Return

The rate of return is simply the end value less the initial value as a proportion of the initial value. Thus if 100 is invested and at the end value is 120 then the rate of return is $\frac{120-100}{100}=\frac{1}{5}$ or $20\%$ .If the the initial investment is $B_{0}$ and the end value is $B_{T}$ after $T$ periods then the rate of return is

$$r (T)=\frac{B_T-B_0}{B_0}$$

Or equivalently the rate of return $r (T)$ satisfies $B_{T}=B_{0}(1+r (T))$

It is important to know the rate of return. However to compare rates of return on different investments with different time horizons it is also important to have a measure of the rate of return per period. One method of making this comparison is to use continuously compounded rates of return. To explain this we first consider compound returns and then show what happens when the compounding is continuous.

## Compound Rates of Return

Compound interest rates are calculated by assuming that the principal (initial investment) plus interest is re-invested each period. Compounding might be done annually,       semi-annually,       quarterly,       monthly or even daily. Assuming the re-investment is done after each period,       the per-period interest rate 7 On the investment satisfies

$$(1+r (T))=(1+r)^T.$$

Now consider dividing up each period into 772 sub-periods each of length $\Delta t$ This is illustrated in Figure 1. Then if the compounding is done $7 t$ times per period,       the compound interest rate 7 satisfies

$$(1+r (T))=(1+\frac{r}{n})^{nT}.$$

For example consider a time period of one-year and suppose an investment of 100 that yields 120 after two years ( $T=2$ ) has arateof return $r (2)=0.2$ If the interest rate is annualised using annual compounding ( $n=1$ ，T= 2)，then $r=0.09544$ ; with semi-annual compounding $n=2$ ， $T=2$ ）the annualised interest rate is $r=0.09327$ ; with quarterly compounding ( $n=4$ $T=2$ ) the annualised interest rate is $r=0.0922075$ etc.

![](./images/fSOe4IyI3HVARu6ZbngTkEnwBwnLWYtnD.png)

Figure 1: DIVIDING A TIME INTERVAL $Tl$ SUB-PERIODS

### Continuous Compounding

Suppose that compounding is done $7 t.$ times per period and let the length of time between compounding be denoted by $\Delta t=\frac{1}{n}$ . Continuous compounding occurs as $\Delta t\rightarrow 0$ or equivalently as $n\to 0$ .In this case the compounding factor $T$ satisfies
$$(1+\frac{r}{n})^{nT}=(1+r\Delta t)^{\frac{T}{\Delta t}}.$$

Let $m=\frac{1}{r\Delta t}$ ,       then

$$(1+r\Delta t)^{\frac{T}{\Delta t}}=(1+\frac{1}{m})^{mrT}=\left ((1+\frac{1}{m})^{m}\right)^{rT}.$$

As we let the intervalbetween compounding $\Delta t$ go to zero then $TIl\longrightarrow\mathcal{X}$ The limit of (1 + ) m as $TIl\to\mathbb{X}$ is well known. In particular wehave

$$\begin{aligned}
&m=1:&& \left (1+\frac{1}{m}\right)^{m} && =\left (1+\frac{1}{1}\right)=2 \\
&m=10:&& \left (1+\frac{1}{m}\right)^{m} && =\left (1+\frac{1}{10}\right)^{10}=2.59374 \\
&m=100:&& \left (1+\frac{1}{m}\right)^{m} && =\left (1+\frac{1}{100}\right)^{100}=2.70481 \\
&m=1000:&& \left (1+\frac{1}{m}\right)^{m} && =\left (1+\frac{1}{1000}\right)^{1000}=2.71692 \\
&m=10000:&& \left (1+\frac{1}{m}\right)^{m} && =\left (1+\frac{1}{10000}\right)^{10000}=2.71815 \\
&m=\vdots && =: \\
&m=\infty && \left (1+\frac{1}{m}\right)^{m} && =e=2.71828. \\
&&&\text{1}
\end{aligned}$$

In thelimit as $m\rightarrow\infty$ 1+newhere $e=2.7182818$ is the base of the natural logarithm. Thus the compounding factor is given by

$$(1+\frac{r}{n})^{nT}=\left ((1+\frac{1}{m})^{m}\right)^{rT}\to e^{rT}.$$

This gives a simplemethod for calculating the continuously compounded rate of return 7 from the formula $(1+r (T))=e^{rT}$ .Since $(1+r (T))=B_{T}/B_{0}$ simply take logs of both sides gives (since $\ln e^{r^{\prime}I^{\prime}}=rT$

$$r=\frac{1}{T}\ln\left (\frac{B_T}{B_0}\right)=\frac{1}{T}(\ln S_B-\ln B_0).$$

This isknown as the continuously compounded rate ofreturn

## The Continuously Compounded Rate of Return

The continuously compounded rate of return has the property that longer period rates of return can be computed simply by adding shorter continuously

Compounded rates of return. This is a very convenient feature which makes using the continuously compounded rates of return especially simple. To see this let $7 t$ denote the continuously compounded rate of return from period $t$ to $t+1$ ,      that is
$$r_t=\ln\left (\frac{B_{t+1}}{B_t}\right)$$

Where $B_{t}$ is the value of the asset at time $t$ .Let $r (T)$ denote the continuously compounded rate of return over the period 0 to $T$

$$r (T)=\ln\left (\frac{B_T}{B_0}\right)=\ln B_T-\ln B_0.$$

Suppose that $T=2$ then we can write this as

$$r (2)=\ln B_2-\ln B_0=(\ln B_2-\ln B_1)+(\ln B_1-\ln B_0)=r_2+r_1.$$

Thus the continuously compoundedrate of return over two periods is simply the sum of the two periodby periodreturns. In generalfor any value of $T$ we can write

$$\begin{aligned}\cdot (T)&=\quad (\ln B_{T}-\ln B_{T-1})+(\ln B_{T-1}-\ln B_{T-2})+\ldots+(\ln B_{2}-\ln B_{1})+(\ln B_{1})\\&=\quad r_{T-1}+r_{T-2}+\ldots+r_{1}+r_{0}=\sum_{t=0}^{T-1}r_{t}.\end{aligned}$$

Thus the continuously compounded rate of return over time $T$ is simply the sum of the period by period returns. If $Tt$ is constant over time then $r (T)=rT$

### A Differential Equation

Let $Tt$ denote the rate of return between $t$ and $t+1$ .Then over any subinterval of $\Delta t$ say between $t$ and $t+\Delta t$ ， $Tt$ satisfies

$$B_{t+\Delta t}=(1+r_t\Delta t) B_t.$$

Then taking the limit as $\Delta t\to 0$ wehave $B_{t+\Delta t}-B_{t}\rightarrow dB (t)$ where $B (t)$ is the price at time $t$ and $\Delta t\to dt$ .Hence we can write

$$dB (t)=r_tB (t) dt$$

Or equivalently

$$\frac{dB (t)}{B (t)}=r_tdt.$$

This is a differential equation. If we assume that $r_{t}=r$ is independent of the time $t$ ，then this equation can be solved at by integration to give the asset price at time $T$
$$\ln B_T-\ln B_0==\ln\left (\frac{B_T}{B_0}\right)=rT$$

Or

$$B_T=B_0 e^{rT}.$$

### Stochastic Processes

Wehave assumed so far that the rate of return was known so that we were dealing with a risk-free asset. But for most assets the rate of return is uncertain or stochastic. As the asset value also changes through time the we say that the asset price follows a stochastic process. Fortunately the efficient markets hypothesis provides some strong indication of what properties this stochastic process will have.

## A Coin Tossing Example

To examine the form that uncertain returns may take it is useful to think first of a very simple stochastic process. This we have already seen as the binomial model is itself a stochastic process. As an example consider the case of tossing a fair coin where one unit is won if the coin ends up Heads

And one unit is lost if the coin ends up Tails. An example of the possible payoffs for a particular sequence of Heads and Tails is illustrated in Figure 2.

![](./images/fWYtb8i9upM6bpaHIO6k1MYGn71wr3MpQ.png)

Figure 2: A CoIN TOsSING STOCHASTIC PROCESS

The important properties of this example are that the distribution of returns are 1) identically distributed at each toss (there is an equal chance of a Head or a Tail); 2) independently distributed (the probability of a Head today is independent of whether there was a Head yesterday); 3) the expected return is the same each period (equal to zero); 4) the variance is constant at each period (equal to one).

There are some important implications to note about this process. First let $\mathcal{L}_{t}$ denote the winnings on the $t$ th toss. Wehave $x_{0}=0$ and $\operatorname{E}[x_{1}]=0$ where $\operatorname{E}[x_{t}]$ denotes the expected winnings at date $t$ .Then we also have at any date

$$\mathrm{E}[x_{t+1}]=x_t.$$

Any process with this property is said to be a martingale. Another important property is that the variance of $JL$ is increasing proportionately to the number of tosses. In particular letting $\sigma_{t}^{2}$ denote the variance of the winnings atthe $t$ th toss we have $\sigma_{t}^{2}=t$ or in terms of the standard deviation (the square root of the variance
$$\sigma_t=\sqrt{t}.$$

This is illustrated in Figure 3. Figure 3 shows all possible winnings through four tosses. The variance of winnings is easily calculated at each toss. For example at the second toss the expected winnings are zero so the variance is given by

$$\sigma_2^2=\frac{1}{4}(2-0)^2+\frac{1}{2}(0-0)^2+\frac{1}{4}(-2-0)^2=1+1=2$$

And so the standard deviation is $\sigma_{2}={\sqrt{2}}$

### A Stochastic Process for Asset Prices

The efficient markets hypothesis implies that all relevant information is rapidly assimilated into asset prices. Thus asset prices will respond only to new information (news) and since news is essentially unforecastable so to are asset prices. The efficient market hypothesis also implies that it is impossible to consistently make abnormal profits by trading on publically available information and in particular the past history of asset prices. Thus only the current asset price is relevant in predicting future prices and past prices are irrelevant. This property is know as the Markov property for stock prices. If we add a further assumption that the variability of asset prices is roughly constant over time,       then the asset price is said to follow a random walk. This was true of our coin tossing example above.

Let $u_{t}$ denote the random rate of return from period $t$ to $t+1$ .Then

$$S_{t+1}=(1+u_t) S_t.$$

![](./images/fmHDdcVTECfFgL1cPn1R5Z5TwHAqCpgs4.png)

Figure 3: COIN TOSSING EXAMPLE: THE VARIANCE IS PROPORTIONAL TO TIME

The return $ut$ is now random because the future asset price is unknown. It can be considered as a random shock or disturbance. Taking natural logarithm of both sides gives

$$\ln S_{t+1}=\ln S_t+\ln (1+u_t).$$

We can then see how the stochastic process for the asset price evolves. Sup pose we start from a given value $S_{0}$ ,      then

$$\begin{aligned}
&\ln S_{1} =\ln S_0+\ln (1+u_0) \\
&\ln S_{2} =\ln S_{1}+\ln (1+u_{1})=\ln S_{0}+\ln (1+u_{0})+\ln (1+u_{1}) \\
&\ln S_{3} =\ln S_2+\ln (1+u_2)=\ln S_0+\ln (1+u_0)+\ln (1+u_1)+\ln (1+u_2) \\
&=: \\
&\ln S_{T} =\ln S_0+\sum_{i=0}^{T-1}\ln (1+u_i). 
\end{aligned}$$

Let $\omega_{t}=\ln (1+u_{t})$ .We can then write

$$\ln S_T=\ln S_0+\sum_{i=0}^{T-1}\omega_i.$$

We shall assume that $\omega_{t}$ is a random variable which is identically and independently distributed and such that the expected value $\operatorname { E} [ \omega _{t}]$ = $\nu$ and variance $\operatorname{Var}[\omega_{t}]=\sigma^{2}$ .There is a great deal of evidence to support the assumption that $w_{t}$ is independently and identically distributed and over short time horizons. It is also usually reasonable to assume that the expected value $V$ and variance $\sigma^{2}$ are independent of time for the short time horizons that we normally consider in pricing options.

We shall make a further assumption that each $\omega_{t}$ is normally distributed Since the sum of randomly distributed random variables is normally distributed,       and since $S_{0}$ is known the natural logarithm of the asset price will also be normally distributed. Taking expectations we can therefore show that

$$\mathrm{E}[\ln S_T]=\ln S_0+\nu T$$

And

$$\mathrm{Var}[\ln S_T]=\sigma^2 T.$$

Since the logarithm of the asset price is normally distributed the asset price itself is said to be lognormally distributed. In practice when one looks at the empirical evidence asset prices are reasonably closely lognormally distributed

### Lognormal Random Variable

We have assumed that that $\omega_{t}=\ln (1+u_{t})$ is normally distributed with an expected value of $V$ and variance $\sigma^{2}$ .But $1+u_{t}$ is a lognormal variable. Since $1+u_{t}=e^{\omega t}$ we might guess that the expected value of $u_{t}$ is $\operatorname{E}[u_{t}]=e^{\nu}-1$ However this would be WRONG. The expected value of $Ut$ is

$$\mathrm{E}[u_t]=e^{\nu+\frac{1}{2}\sigma^2}-1.$$

The expected value is actually higher than anticipated by half the variance. The reason why can be seen from looking at an example of the lognormal distribution which is drawn in Figure 4. The distribution is skewed and as the variance increases the lognormal distribution will spread out. It cannot spread out too much in a downward direction because the variable is always non-negative. But it can spread out upwards and this tends to increase the mean value. One can likewise show that the expected value of the asset price at time $T$ is
$$\mathrm{E}[S_{T}]=S_{0}e^{(\nu+\frac{1}{2}\sigma^{2}) T}.$$

Letting $\mu=\nu+\frac{1}{2}\sigma^{2}$ we have

$$\mathrm{E}[S_T]=s_0 e^{\mu T}$$

So that $\mu$ is the expected continuously compounded rate of return. We will explain the relationship between $\mu$ and $V$ a little bit further below.

### Standard Normal Variable

We have seen that $\ln S_{T}$ is normally distributed with mean (expected value) of $\ln S_{0}+\nu T$ and variance of $\sigma^{2}T$ .It isuseful to transform this to a variable



![](./images/fVlhrLk3kUTgO0H3aQwkHVBfxz1umLw8G.png)

Figure 5: A STANDARD NORMAL DISTRIBUTION. $N (0)=0.5$

Arithmetic and geometric rates of return

We now consider $\mu$ and $U$ again. Suppose we have an asset worth 100 and for two successive periods it increases by $20\%$ .Then the value at the end of the first period is 120 and the value at the end of the second period is 144.

Now suppose that instead the asset increases in the first period by $30\%$ and in the second period by $10\%$ .The average or arithmetic mean of the return is $20\%$ .However the value of the asset is 130 at the end of first period and 143 at the end of the second period. The variability of the return has meant that the asset is worth less after two periods even though the average return is the same. We can calculate the equivalent per period return that would give the same value of 143 after two periods if there were no variance in the returns. That is the value $V$ that satisfies

$$143=100 (1+\nu)^2.$$

This value is known as the geometric mean. It is another measure of the average return over the two periods. Solving this equation gives the geometric

Mean as $\nu=0.195826$ or $19.58\%$ per period² which is less than the arithmetic rate of return per period.

There is a simple relationship between the arithmetic mean return,       the geometric mean return and the variance of the return. Let $\mu_{1}=\mu+\sigma$ be the rate of return in the first period and let $\mu_{2}=\mu-\sigma$ be the rate of return in the second period. Here the average rate of return is $\frac{1}{2}(\mu_{1}+\mu_{2})=\mu$ and the variance of the two rates is $\sigma^{2}$ .The geometric rate of return $\mu$ satisfies $(1+\nu)^{2}=(1+\mu_{1})(1+\mu_{2})$ .Substituting and expanding this gives

$$1+2\nu+\nu^2=(1+\mu+\sigma)(1+\mu-\sigma)=(1+\mu)^2-\sigma^2=1+2\mu+\mu^2-\sigma^2$$

Or

$$\nu=\mu-\frac{1}{2}\sigma^{2}+\frac{1}{2}(\mu^{2}-\nu^{2}).$$

Since rates of return are typically less than one,       the square of the return is even smaller and hence the difference between two squared percentage terms is smaller still. Hence we have the approximation $\nu\approx\mu-\frac{1}{2}\sigma^{2}$ O 1

$$\mathrm{geometric~mean}\approx\mathrm{arithmetic~mean}-\frac{1}{2}\mathrm{variance}.$$

This approximation will be better the smaller are the interest rates and the smaller is the variance. In the example $\mu=0.2$ and $\sigma=0.1$ SO $\frac{1}{2}\sigma^{2}=0.005$ and $\mu-\frac{1}{2}\sigma^{2}=0.1950$ which is close to the actual geometric mean of 0.1958. Thus the difference between $\mu$ and $V$ is that $V$ is the geometricrate of return and $\mu$ is the arithmetic rate of return. It is quite usual to use the arithmetic rate and therefore to write that the expected value of thelogarithm of the stock price satisfies

$$\operatorname{E}[\ln S_T]=\ln S_0+\left (\mu-\frac{1}{2}\sigma^2\right) T$$

And

$$\mathrm{Var}[\ln S_T]=\sigma^2 T.$$

### Continuously Compounded Rate of Return

The value $V$ is the continuously compoundedrate of return. It is given by

$$\nu=\frac{1}{T}[\ln S_{T}-\ln S_{0}].$$

Hence taking expectations we can calculate

$$\mathrm{E}[\nu]=\frac{1}{T}\mathrm{E}[\ln S_{T}-\ln S_{0}]==\frac{1}{T}\left (\mathrm{E}[\ln S_{T}]-\ln S_{0}\right)=\mu-\frac{\sigma^{2}}{2}.$$

Similarly the variance satisfies.

$$\mathrm{Var}[\nu]=\frac{1}{T^{2}}\mathrm{Var}[\ln S_{T}-\ln S_{0}]=\frac{1}{T^{2}}\mathrm{Var}[\ln S_{T}]=\frac{\sigma^{2}T}{T^{2}}=\frac{\sigma^{2}}{T}.$$

Hence the standard deviation of $V$ is simply $\sigma/{\sqrt{T}}$

### A WienerProcess

We will now consider the stochastic process in more detail and see how to take limits as the length of the time interval goes to zero. This will produce a continuous time stochastic process.

Consider a variable $iL$ which takes on values at discrete points in time $t=0,      1,      \ldots,       T$ and suppose that $Z$ evolves according to the following rule:

$$z_{t+1}=z_{t}+\epsilon;\quad W_{0}\quad\mathrm{fixed}$$

Where $t$ is a random drawing from a standardized normal distribution,       that is with mean of zero and variance of one. The draws are assumed to be independently distributed. This represents a random walk where on average $iL$ remains unchanged each period but where the standard deviation of the realized value is one each period. At date $t=0$ ,      we have $E[z_{T}]=z_{0}$ and the variance $Var[z_{T}]=T$ as the draws are independent.

Now divide the periods into $TL$ subperiods each of length $\Delta t$ .To keep the process equivalent the variance in the shock must also be reduced so that the standard deviation is $\sqrt{\Delta t}$ .The resulting process isknown as aWiener process. The Wiener process has two important properties:

Property 1 The change in $iL$ over a small interval of time satisfies:

$$z_{t+h}=z_{t}+\epsilon\sqrt{\Delta t}.$$

Then as of time $t=0$ ，it is still the case that $E[ z_{T}]$ = $z_{0}$ and the variance $Var[z_{T}]=T$ . This relation may be written

$$\Delta z (t+\Delta t)=\epsilon\sqrt{\Delta t}$$

Where $\Delta z (t+\Delta t)=z_{t+\Delta t}-z_{t}$ . This has an expected value of zero and standard deviation of $\sqrt{\Delta t}$

Property 2 The values of $\Delta z$ for any two different short intervals of time are independent.

It follows from this that

$$z (T)-z (0)=\sum_i^N\epsilon_i\sqrt{\Delta t}$$

Where $N=T/\Delta t$ is the number of time intervals between 0 and $T$ .Hence we have

$$\mathrm{E}[Z (T)]=z (0)$$

And

$$\mathrm{Var}[z (T)]=N\Delta t=T$$

 Or the standard deviation of $z (T)$ is $\sqrt{T}$

Now consider what happens in the limit as $\Delta t\to 0$ ,      that is as the length of the interval becomes an infinitesimal $dt$ .We replace $\Delta z (t+\Delta t)$ by $dz (t)$

Which has a mean of zero and standard deviation of $dt$ .This continuous time stochastic process is also known as Brownian Motion after its use in physics to describe the motion of particles subject to a large number of small molecular shocks

This process is easily generalized to allow for a non-zero mean and arbitrary standard deviation. A generalized Wiener process for a variable $3 L$ is defined in terms of $dz (t)$ as follows

$$dx=a\:dt+b\:dz$$

where $U.$ and $b$ are constants. This formula for the change in the value of ${:}L$ consists of two components,       a deterministic component adt and a stochastic component $b$ $dz ( t)$ .The deterministic component is $dx= a$ $dt$ or $\frac {dx}{dt}$ = $a$ which shows that $x$ = $x_{0}+ at$ sothat $d.$ is simply the trend term for $JL$ Thus the increase in the value of ${:}\boldsymbol{L}$ over one time period is $d$ .The stochastic component $b$ $dz ( t)$ adds noise or variability to the path for $2 L$ .The amount of variability added is $b$ times the Wiener process. Since the Wiener process has a standard deviation of one the generalized process has a standard deviation of $b$

### The Asset Price Process

### Remember that wehave

$$\ln S_{t+1}-\ln S_t=\omega_t$$

Where $\omega t$ is are independent random variables withmean $U$ and standard deviation of 0 .The continuous time version of this equationis therefore

$$d\:\ln S (t)=\nu\:dt+\sigma\:dz$$

Where Z is a standard Wiener process. The right-hand-side of the equation is just a random variable that is evolving through time. The term $V$ is called the

Drift parameter and the standard deviation of the continuously compounded rate of return is $\sqrt{Var[r (t)]}=\sigma\sqrt{\Delta t}$ and the term $U$ is referred to as the volatility of the asset return

### Ito Calculus

We have written the process in terms of $\ln S (t)$ rather than $S (t)$ itself. This is convenient and shows the connection to the binomial model. However it is usual to think in terms of $S (t)$ itself too. In ordinary calculus we know that

$$d\ln S (t)=\frac{dS (t)}{S (t)}.$$

Thus we might think that $dS ( t) / S ( t)$ = $\nu$ $dt$ + $\sigma$ $dz$ .But this would be WRONG. The correct version is

$$\frac{dS (t)}{S (t)}=\left (\nu+\frac{1}{2}\sigma^2\right)\:dt+\sigma\: dz.$$

This is a special case of Ito's lemma. Ito's lemma shows that for any process of the form

$$dx=a (x,       t) dt+b (x,       t) dz$$

Then the function $G (x,       t)$ follows the process

$$dG=\left (\frac{\partial G}{\partial x}a (x,       t)+\frac{\partial G}{\partial t}+\frac{1}{2}\frac{\partial^2 G}{\partial x^2}b^2 (x,       t)\right) dt+\frac{\partial G}{\partial x}b (x,       t) dz.$$

We'll see how to use Ito's lemma. We have

$$d\:\ln S (t)=\nu\:dt+\sigma\: dz.$$

Then let $\ln S (t)=x (t)$ s 0 $s (T)=G (x,       t)=e^{x}$ . Then upon differentiating

$$\frac{\partial G}{\partial x}=e^x=S,      \quad\frac{\partial^2 G}{\partial S^2}=e^x=S,      \quad\frac{\partial G}{\partial t}=0.$$

Hence using Ito's lemma

$$dS (t)=(\nu S (t)+0+\frac{1}{2}\sigma^{2}S (t)) dt+\sigma S (t)\:dz$$

Or

$$d\: S (t)=(\nu+\frac 12\sigma^2) S (t)\:dt+\sigma S (t)\:dz$$

Since $\mu=\nu+\frac{1}{2}\sigma^{2}$ we can write this as

$$d\: S (t)=\mu S (t)\:dt+\sigma S (s)\: dz.$$

This process is know as geometric Brownian motion as it is the rate of change which is Brownianmotion. Thus sometimes the above equation is written as

$$\begin{aligned}\frac{d\: S (t)}{S (t)}=\mu\:dt+\sigma\: dz.\end{aligned}$$

We can also do the same calculation the other way around. Suppose that we start from the process

$$ds (t)=\mu S (t)\:dt+\sigma S (s)\: dz.$$

Now consider the function $G (S)=\ln S$ . Differentiating we have

$$\frac{\partial G}{\partial S}=1,      \quad\frac{\partial^2 G}{\partial S^2}=-\frac{1}{S^2},      \quad\frac{\partial G}{\partial t}=0.$$

Hence substituting into Ito's lemma we get.

$$dG=d\ln S (t)=\left (\mu-\frac{1}{2}\sigma^2\right)\:dt+\sigma\: dz.$$

### The forward price.

As we have seen before the forwardprice just depends on the current price of the underlying,       the interest rate and the time to expiration. With continuous compounding we can write the forward price equation as

$$F (S (t),       t)=S (t) e^{r (T-t)}.$$

This shows the forward price is a stochastic process which depends on the price of the underlying asset which itself is a stocastic process. Since we have

That the forward price is a function of a stochastic process we can use Ito's lemma. Upon differentiation we have

$$\frac{\partial F}{\partial S}=e^{r (T-t)};\quad\frac{\partial F}{\partial t}=-rS (t) e^{r (T-t)};\quad\frac{\partial^2 F}{\partial S^2}=0.$$

Hence substituting into Ito's lemma

$$\begin{aligned}dF&=\left (e^{r (T-t)}\mu S (t)-rS (t) e^{r (T-t)}\right) dt+\sigma S (t) e^{r (T-t)}dz\\&=(\mu-r) S (t) e^{r (T-t)}\sigma S (t) e^{r (T-t)}dz\\&=(\mu-r) F (t) dt+\sigma F (t) dz.\end{aligned}$$

This shows that the forward price also follows a geometric Brownian motion process with expected return given by the risk premium on the underlying $\mu-r$ and volatility 0 (the same as the underlying asset).

## Summary

We have shown how returns are continuously compounded and introduced the geometric Brownian motion process for stock prices. We have shown how Ito's lemma can be used. The next thing to do will be to show how to use the assumption of geometric Brownian motion to price an option or derivative using Ito's lemma.

# The Black-Scholes Formula.

These notes examine the Black-Scholes formula for European options. The Black-Scholes formula are complex as they are based on the geometric Brownian motion assumption for the underlying asset price. Nevertheless they can be interpreted and are easy to use once understood. We start off by examining digital or binary options which are easy and intuitive to price. We shall show how the Black-Scholes formula can be derived and derive and justify the Black-Scholes-Merton partial differential equation.

Keywords: Black-Scholes formula,       Black-Scholers-Merton partial differential equation,       replication,       self-financing portfolio,       martingale pricing,       bound-. Ary conditions,       PDE.

Reading: Hull Chapter 13.

## Digital Options

To help understand the Black-Scholes formula for call and put options we start by looking at digital options. Digital options are very simple. A digital call with a strike price $K$ and maturity date $T$ pays out one unit if $S (T)>K$ and nothing otherwise. Likewise a digital put with a strike price $K$ and maturity date $T$ pays out one unit if $S (T)<K$ and nothing otherwise

Thus for a digital call option the payoff at maturity is:

$$c^b (T)=\begin{cases}0&\text{if}S (T)\leq K\\1&\text{if}S (T)>K\end{cases}$$

And the payoff at maturity to a digital put option is:

$$p^b (T)=\begin{cases}1&\text{if}S (T)\leq K\\0&\text{if}S (T)>K.\end{cases}$$

We now show how to value the digital call option. The end price $S_{T}$ is a random variable. We have by assumption that $\ln S (T)$ is normally distributed with
$$\operatorname{E}[\ln S (T)]=\ln S (0)+\left (\mu-\frac{1}{2}\sigma^2\right) T$$

And

$$\mathrm{Var}[\ln S (T)]=\sigma^2 T.$$

Thus

$$\frac{\ln S (T)-\ln S (0)-\left (\mu-\frac{1}{2}\sigma^2\right) T}{\sigma\sqrt T}$$

Is a standard normal variable with expected value of zero and standard deviation of one. We want to know the probability that the call option is exercised. The call option is exercised if $S_{T}>K$ or equivalently if $\ln S (T)>\ln K$ .Thus the probability of exercise is given by $1-N (x^{*})$ where

$$x^*=\frac{\ln K-\ln S (0)-\left (\mu-\frac{1}{2}\sigma^2\right) T}{\sigma\sqrt T}$$

As we have seen options can be evaluated using risk-neutral pricing,       that is as if allassets earn the same rate of return. 7 as the riskless asset. Thus we replace $\mu$ by 7 in the above equation to get

$$x=\frac{\ln K-\ln S (0)-\left (r-\frac{1}{2}\sigma^2\right) T}{\sigma\sqrt{T}}.$$

Thus the probability of exercise in a risk-neutral world is $1-N (x)=N (-x)$ The call option pays out one unit if it is exercised but only after $T$ periods. Thus the expected discounted value of the digital call option is

$$c^b (0)=e^{-rT}N (-x).$$

There is a simple condition for put call parity for digital options. This is given by

$$c^b (0)+p^b (0)=e^{-rT}$$

Since if one buys a digital call and a digital put with the same strike price and maturity date,       one is sure to have one unit at time $T$ no matter what the price of the underlying asset. Hence the put price satisfies

$$p^b (0)=e^{-rT}-c^b (0)=e^{-rT}-e^{-rT}N (-x)=e^{-rT}(1-N (-x))=e^{-rT}N (x).$$

Equivalently we can see that the risk-neutral probability that $S_{T}<K$ is given by $N (x)$ and hence the value of the binary or digital put is $e^{-rT}N (x)$ where $\mathcal{L}$ is given above.

### The Black-Scholes Formula

Plain options have slightly more complex payoffs than digital options but the principles for calculating the option value are the same.

The payoff to a European call option with strike price $K$ at thematurity date $T$ is

$$c (T)=\max[S (T)-K,       0]$$

Where $S (T)$ is the price of the underlying asset at the maturity date. At maturity if $S (T)>K$ the option to buy the underlying at $K$ can be exercised and the underlying asset immediately sold for $S (T)$ to give a net payoff of $S (T)-K$ .Since the option gives only the right and not the obligation to buy the underlying asset,       the option to buy the underlying will not be exercised if doing so would lead to a loss,       $S (T)-K<0$ . The Black-Scholes formula for the price of the call option at date $t=0$ prior to maturity is given by

$$c (0)=S (0) N (d_1)-e^{-rT}KN (d_2)$$

Where $N (d)$ is the cumulative probability distribution for a variable that has a standard normal distribution with mean of zero and standard deviation of

One. It is the area under the standard normal density function from $-\infty$ to $d$ and therefore gives the probability that a random draw from the standard normal distribution will have a value less than or equal to $d$ .Wehave there fore that $0\leq N (d)\leq 1$ with $N (-\infty)=0$ $N (0)={\frac{1}{2}}$ and $N (+\infty)=1$ .The term 7 is the continuously compounded risk-free rate of interest and $d_{1}$ and $d_{2}$ satisfy

$$\begin{array}{rcl}d_1&=&\frac{\ln (\frac{S (0)}{K})+(r+\frac{1}{2}\sigma^2) T}{\sigma\sqrt{T}}\\\\d_2&=&d_1-\sigma\sqrt{T}=\frac{\ln (\frac{S (0)}{K})+(r-\frac{1}{2}\sigma^2) T}{\sigma\sqrt{T}}\end{array}$$

Here $\sigma^{2}$ is the variance of the continuously compounded rate of return on the underlying asset.

Likewise the payoff to a European put option with strike price $K$ at the maturity date $T$ is

$$p (T)=\max[K-S (T),       0]$$

As the put option gives the right to sell underlying asset at the strike price of $K$ .The Black-Scholes formula for the price of the put option at date $t=0$ prior to maturity is given by

$$p (0)=c (0)+e^{-rT}K-S (0)=e^{-rT}K (1-N (d_2))-S (0)(1-N (d_1))$$

Where $d_{1}$ and $d_{2}$ are defined above. By the symmetry of the standard normal distribution $N (-d)=(1-N (d))$ so the formula for the put option is usually written as

$$p (0)=e^{-rT}KN (-d_2)-S (0) N (-d_1).$$

### Interpretation of the Formula

Rewrite the Black-Scholes formula as

$$c (0)=e^{-rT}\begin{pmatrix}S (0) e^{rT}N (d_1)-KN (d_2)\end{pmatrix}.$$

The formula can be interpreted as follows. If the call option is exercised at the maturity date then the holder gets the stock worth $S (T)$ but has to pay the strike price $K$ .But this exchange takes place only if the call finishes in the money. Thus $S (0) e^{rT}N (d_{1})$ represents the future value of the underlying asset conditional on the end stock value $S (T)$ being greater than the strike price $K$ .The second term in the brackets $KN (d_{2})$ is the value of the known payment $K$ times the probability that the strike price will be paid $N (d_{2})$ .The terms inside the brackets are discounted by the risk-free rate 7 to bring the payments into present value terms. Thus the evaluation inside the brackets is made using the risk-neutral or martingale probabilities. The term $N (d_{2})$ represents the probability that the call finishes in the money where $d_{2}$ is also evaluated using the risk-free rate.

Remember that in a risk-neutral world all assets earn the risk-free rate. We are assuming the the logarithm of the stock price is normally distributed. Thus $ij$ the expected continuously compounded rate of return in a risk neutral world is equal to $r-\frac{1}{2}\sigma^{2}$ where the variance is deducted to calculate the certainty equivalent rate of return. Therefore at time $T$ ln $S (T)$ is normally distributed with a mean value of ln $S (0)+(r-\frac{1}{2}\sigma^{2}) T$ and a standard deviation of $\sigma{\sqrt{T}}$ Thus
$$\frac{\ln\: S (T)-(\ln\: S (0))+(r-\frac{1}{2}\sigma^2) T)}{\sigma\sqrt{T}}$$

is a standard normal variable. The probability that $S (T)<K$ is therefore given by $N(-d_{2})$ and the probability that $S(T)>K$ is given by $1-N (-d_{2})=$ $N (d_{2})$

It is more complicated to show that $S (0) e^{rT^{\prime}}N (d_{1})$ is the future value of underlying asset in a risk-neutral world conditional on $S (T)>K$ but a proof can be found in more advanced textbooks

The formula also has another useful interpretation. From our analysis of thebinomialmodelweknow that the value of the callis

$$c (0)=S (0)\Delta-B$$

Where $\Delta$ is the amount of the underlying asset bought and $B$ is the amount of money borrowed needed to synthesize the call option. From the formula therefore $N (d_{1})$ is the hedge parameter indicating the number of shares bought and $e^{-rT}KN (d_{2})$ indicates the amount of cash borrowed to part finance the share purchase. Since 0 $\leq$ $N ( d)$ $\leq$ 1 the formula shows that the replicating portfolio consists of a fraction of the underlying asset and a positive amount of cash borrowed. The $\Delta$ of this formula is also found by partially differentiating the call price formula

$$\frac{\partial c (0)}{\partial S (0)}=\Delta.$$

It is the slope of the curve relating the option price with the price of the underlying asset. The cost of buying $\Delta$ units of the stock and writing one call option is $S (0)\Delta-c (0)$ .This portfolio is said to be delta neutral as a small change in the stock price will not affect the value of the portfolio.

### Boundary Conditions

We shall consider theboundary conditions for the call option. Consider first the boundary condition for the call at expiration when $T=0$ .To do this consider the formula for the call option as $T\longrightarrow 0$ ,      that is as the time until maturity goes to zero. At maturity $c (T)=\operatorname*{max}[S (T)-K,       0]$ so we need to show that as $T\longrightarrow 0$ the formula converges to $c ( 0)$ = $\operatorname* { max} [ S ( 0) - K,       0]$ .If $S (0)>K$ then $\ln ({\frac{S (0)}{K}})>0$ so that as $T\longrightarrow 0$ ， $d_{1}$ and $d_{2}\to+\infty$ .Thus $N (d_{1})$ and $N (d_{2})\to 1$ .Since $e^{-rT}\to 1$ as $T\longrightarrow 0$ we have that $c ( 0)$ $\longrightarrow$ $S ( 0) - K$ if $S (0)>K$ . Alternatively if $S (0)<K$ then $\ln(\frac{S(0)}{K})<0$ so that as $T\longrightarrow0$ $d_{1}$ and $d_{2}\rightarrow-\infty$ and hence $N(d_{1})$ and $N( d_{2})$ $\to$ 0 .Thus $c( 0)$ $\longrightarrow$ 0 if $S(0)<K$ .This is precisely as expected. If the option is in the money at maturity,       $S(0)>K$ ,       it is exercised for a profit of $S (0)-K$ and if it is out of the money,       $S (0)<K$ ,       the option expires unexercised and valueless.

As another example consider what happens as $\sigma\rightarrow 0$ .In this case the underlying asset becomes riskless so grows at the constant rate of $T$ .Thus the future value of the stock is $S (T)=e^{rT^{\prime}}S (0)$ and the payoff to the call option at maturity is $\operatorname*{max}[e^{r^{\prime}I^{\prime}}S (0)-K,       0]$ . Thus the value of the call at date $t=0$ is $\operatorname*{max}[S (0)-e^{-rT}K,       0]$ .To see this from the formula first consider the case where $S (0)-e^{-rT}K>0$ or $\ln (\frac{S (0)}{K})+rT>0$ .Then as $\sigma\longrightarrow 0$ ， $d_{1}$ and $d_{2}\to+\infty$ and hence $N (d_{1})$ and $N (d_{2})\to 1$ .Thus $c ( 0)$ $\to$ $S ( 0)$ - $e^{- rT^{\prime }}K$ Likewise when $S (0)-e^{-rT}K<0$ or $\ln (\frac{S (0)}{K})+rT<0$ then $d_{1}$ and $d_{2}\to-\infty$ as $\sigma\rightarrow 0$ .Hence $N (d_{1})$ and $N (d_{2})\to 0$ and so $c (0)\to 0$ .Thus combining both conditions $c (0)\longrightarrow\operatorname*{max}[e^{rT}S (0)-K,       0]$ as $\sigma\rightarrow 0$

## At-the-money Options.

Consider an option that is currently at-the-money,       $S ( 0)$ = $K$ .Then the formula for the call option becomes

$$c (0)=S (0)\begin{pmatrix}N (d_1)-e^{-rT}N (d_2)\end{pmatrix}$$

Where

$$d_1=\frac{(r-\frac{1}{2}\sigma^2) T}{\sigma\sqrt{T}};\quad d_2=d_1-\sigma\sqrt{T}.$$

Thus the price of an at-the-money call option is simply a fraction the price of the underlying..

There is an even more convenient approximation if we take $K=S (0) e^{rT}$ that is where the strike price is forward price of the underlying asset. Then

$$c (0)=S (0)\left (N (d_1)-N (d_2)\right)$$

And

$$d_1=\frac{\ln (\frac{S (0)}{K})+(r+\frac{1}{2}\sigma^2) T}{\sigma\sqrt{T}}=\frac{\frac{1}{2}\sigma^2 T}{\sigma\sqrt{T}}=\frac{1}{2}\sigma\sqrt{T}$$

And $d_{2}=-(1/2)\sigma\sqrt{T}$ .By Taylor's theorem,       expanding $N (x)$ about $x=0$ gives
$$N (x)\approx N (0)+xN' (0)+\frac{1}{2}x^{2}N'' (0).$$

Thus we have

$$\begin{aligned}N (d_1)-N (d_2)&\approx\left (N (0)+d_1 N' (0)+(1/2) d_1^2 N'' (0)\right)\\&-\left (N (0)+d_2 N' (0)+(1/2) d_2^2 N'' (0)\right)\end{aligned}$$

Hence since $d_{1}^{2}=d_{2}^{2}$ and $d_{1}=-d_{2}=(1/2)\sigma\sqrt{T}$ wehave

$$c (0)\approx S (0)\left (N' (0)\sigma\sqrt{T}\right)$$

And since $N^{\prime}(0)=1/{\sqrt{2\pi}}$ we have

$$c (0)\approx\frac{S (0)\sigma\sqrt T}{\sqrt{2\pi}}\approx 0.4 S (0)\sigma\sqrt T.$$

This can be used as a rough and ready method for calculating the implied volatility if the price is known. Note this formula applies equally to puts as well as calls.

### The Black-Scholes-Merton Partial Differential Equation

Wewish to price a callon an underlying stock. Assume that the time to maturity is 7 and the strike price is $K$ the volatility ofthe underlying asset is 0 .We assume that the underlying asset follows a geometric Brownian motion process

$$d\: S (t)=\mu S (t)\:dt+\sigma S (t)\: dz (t)$$

where $dz$ is a Wiener process,      i.e. has zero mean an unit variance and increments are independent. We assume there is arisk-free asset that has a

Constant continuously compounded rate of return 7 so that a money market account follows the process

$$d\: B (t)=rB (t)\: dt.$$

The latter is equivalent to $B (t)=B (0) e^{rt}$ .The excess return on the stock is $\mu-r$ and the ratio. $\lambda=(\mu-r)/\sigma$ is known as the market price of risk. The call option changes value over time as the stock price and the time to maturity changes and therefore we can write the call price $c (s (t),       t)$

The objective is to show that $c (S (t),       t)$ is well defined (there is a unique price) and describe how the call price depends on $S (t)$ and $t$

Since $c (S (t),       t)$ is just a function we can apply Ito's lemma to derive

$$d\:c=\left (\frac{\partial c}{\partial t}+\mu S\frac{\partial c}{\partial S}+\frac{1}{2}\sigma^2 S^2\frac{\partial^2 c}{\partial S^2}\right) dt+\sigma S\frac{\partial c}{\partial S}\: dz.$$

We now consider a portfolio of one option and $\Delta$ units of the underlying itself. The process for this portfolio is

$$d (c+\Delta S)=\left (\frac{\partial c}{\partial t}+\mu S\frac{\partial c}{\partial S}+\frac{1}{2}\sigma^2 S^2\frac{\partial^2 c}{\partial S}+\Delta\mu S\right) dt+\left (\frac{\partial c}{\partial S}+\Delta\right)\sigma S\: dz.$$

Now setting $\Delta=-\partial c/\partial S$ eliminates the random $dz$ term togive

$$d (c+\Delta S)=\left (\frac{\partial c}{\partial t}+\frac{1}{2}\sigma^2 S^2\frac{\partial^2 c}{\partial S}\right) dt.$$

This is our $\Delta$ -hedged portfolio which has eliminated all risk. Since this port folio is riskless it must satisfy exactly the same equation as the money-market account,       i.e.

$$d (c+\Delta S)=r (c+\Delta S) dt$$

And hence we have by equating these two terms that

$$\begin{pmatrix}\frac{\partial c}{\partial t}+\frac{1}{2}\sigma^2 S^2\frac{\partial^2 c}{\partial S}\end{pmatrix}=r\begin{pmatrix}c-\frac{\partial c}{\partial S}S\end{pmatrix}$$

Where we've replace $\Delta$ by $-\partial c/\partial S$ .Rewriting we have

$$c=\frac{1}{r}\left\{\left (\frac{\partial c}{\partial t}+rS\frac{\partial c}{\partial S}+\frac{1}{2}\sigma^2 S^2\frac{\partial^2 c}{\partial S}\right)\right\}.$$

This is a second-order partial differential equation (PDE). It is known as the Black-Scholes-Merton Partial Differential Equation. Indeed since we did not yet specify anything about the nature of the option,       this equation will apply to any derivative security. What determines how the equation applies to a particular derivative is given by the boundary condition. For the cal option we have the boundary condition that at maturity

$$c (S (T),       T)=\max\{S (T)-K,       0\}.$$

Solving this second order differential equation together with the boundary condition gives the Black-Scholes formula we have seen before

$$c (0)=S (0) N (d_1)-e^{-rT}KN (d_2)$$

Where $d_{1}$ and $d_{2}$ satisfy

$$\begin{array}{rcl}d_1&=&\frac{\ln (\frac{S (0)}{K})+(r+\frac{1}{2}\sigma^2) T}{\sigma\sqrt{T}}\\\\d_2&=&d_1-\sigma\sqrt{T}=\frac{\ln (\frac{S (0)}{K})+(r-\frac{1}{2}\sigma^2) T}{\sigma\sqrt{T}}.\end{array}$$

## A Replication Argument

We consider a portfolio that invests $\boldsymbol{\alpha}$ in the underlying asset and $\beta$ in the risk free asset.

The value of this portfolio at the initial date is

$$P (0)=\alpha S (0)+\beta B (0).$$

We shall require that this strategy is both replicating and self-financing. A portfolio is self-financing if it involves no injection or extraction of cash at

Any time and thus the change in the value of the portfolio depends on how the stock price and value of the risk-free asset changes. Thus the portfolio is self-financing if and only if

$$d\:P=\alpha\:dS+\beta\: dB.$$

To satisfy this equation $\boldsymbol{\alpha}$ and $\beta$ will in general be changing over time and as $S (t)$ varies. However it is also clear that once $\alpha (S (t),       t)$ is specified,       d $\beta (S (t),       t)$ is determined as well by the fact that the portfolio is self-financing and thus has to satisfy the above equation. We shall follow what we did in the previous section and suppose that $\alpha=\partial C/\partial S$ .Here we are taking a long position in the stock as we are trying to replicate the portfolio (whereas in the previous section we were taking a short position to hedge out the risk of the option itself). We want to show that the value of the portfolio equals the value of the call at every instant. That is we want to show that $P (S (t),       t)=c (S (t),       t)$ Therefore we consider the difference

$$\begin{aligned}
&d (P (S (t),       t)-c (S (t),       t))&& =d\: P-d\: c \\
&&&=\alpha (S,       t)\:dS+\beta (S,       t)\: dB \\
&&&-\left (\frac{\partial c}{\partial t}+\mu S\frac{\partial c}{\partial S}+\frac{1}{2}\sigma^{2}S^{2}\frac{\partial^{2}c}{\partial S^{2}}\right) dt-\sigma S\frac{\partial c}{\partial S}\: dz. \\
&\text{100000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000}
\end{aligned}$$

Then substituting for $dS$ ， $dB$ and $\alpha (S,       t)$ gives

$$d (P (S (t),       t)-c (S (t),       t))=\left (\beta (S,       t) rB-\frac{\partial c}{\partial t}-\frac{1}{2}\sigma^2 S^2\frac{\partial^2 c}{\partial S^2}\right) dt.$$

Again the risk has been eliminated from this equation. Then using the Black Scholes equation gives

$$d (P (S (t),       t)-c (S (t),       t))=\left (\beta (S,       t) rB-r\left (c-S\frac{\partial c}{\partial S}\right)\right) dt$$

And since $\beta (S,       t) B=P (S,       t)-\alpha (S,       t) S$ this gives

$$\begin{gathered}
D (P (S (t),       t)-c (S (t),       t)) =r\left (P (S,       t)-\alpha (S,       t) S\right) dt-r\left (c-S\frac{\partial c}{\partial S}\right) dt \\
=r\left (P (S,       t)-c (S,       t)\right) dt. 
\end{gathered}$$

Let $D (S,       t)=P (S,       t)-c (S,       t)$ .By construction we want the portfolio to be replicating so $P (S (0),       0)=c (S (0),       0)$ and hence $D (S,       0)=0$ .But we have from the above equation that $dD=rD (S,       t) dt$ and so $D (S,       t)=D (S,       0) e^{rt}=$ 0 .Thus the portfolio because it is self-financing and all risk has been hedged away replicates the call value at every instant. Moreover,       unlike the previous argument which assumed a call value function $c (S,       t)$ and differentiated,       the present approach proves the existence of this value and shows that it is well defined.

## Martingale Pricing

We now consider the ratio $\varrho (t)=S (t)/B (t)$ .In the binomial case we have seen that this is a martingale so that the ratio $\varrho (t)$ satisfies the property $\mathrm{E}_{*}[x (t+1)]=x (t)$ where the the expectation is taken using the risk-neutral probabilities. Equivalently we have $\mathrm{E}_{*}[x (t+1)-x (t)]=0$ or in the limit $\mathrm{E}_{*}[dx (t)]=0$

Using the equations above for $S (t)$ and $B (t)$ we have upon differentiation that
$$d\:\varrho (t)=\frac{d\: S (t)}{B (t)}+S (t)\: d (B (t)^{-1}).$$

We have $d (B (t)^{-1})=-rB (t)^{-1}dt^{1}$ so that

$$\begin{aligned}
D\:\varrho (t)& =\frac{1}{B (t)}\left (\mu S (t)\:dt+\sigma S (t) dz\right)-\frac{1}{B (t)}rS\: dt \\
&=(\mu-r)\varrho (t)\:dt+\sigma\varrho (t)\: dz.
\end{aligned}$$

This does not satisfy the martingale property because the drift rate is not equal to 7 . We remember however,       that in the Binomial model we never had to specify the true probabilities but could derive risk-neutral probabilities.

We can do do something similar here by changing the probabilities or measure of the distribution. It turns out that if we specify a process $\ddot{z}=z-\eta t$ where $Z$ is a Wiener process then so to is $\tilde{z}$ 2 Thus

$$d\:\varrho (t)=(\mu-r)\varrho (t)\:dt+\sigma\varrho (t)\: d\tilde{z}+\sigma\varrho (t)\eta dt.$$

If we choose $\eta$ to be equal to the market price of risk,       $\lambda=(\mu-r)/\sigma$ ,      then the drift terms cancel out and $\varrho (t)$ is a martingale,       that is $d$ $\varrho ( t) = \sigma \varrho ( t)$ $d\tilde{z}$ Hence since $d$ $B ( t) = rB ( t)$ $dt$ weget

$$d\:\varrho (t)=\frac{d\: S (t)}{B (t)}-\frac{rS (t)}{B (t)}\:dt=\sigma\frac{S (t)}{B (t)}\: d\tilde{z}$$

Or after cancelling out the $B (t)$ term and rewriting

$$d\: S (t)=rS (t)\:dt+\sigma S (t)\: d\tilde{z}$$

So that $S (t)$ is a geometric Brownian motion process using the new variable $z$ .Here the drift with the new variable is just the risk-free rate. It is as if we are in a risk-neutral world and all assets are growing at the same expected rate equal to the risk-free rate.

We can thenproceedasbefore to show that

$$\frac{\ln S (T)-\ln S (0)-(r-\frac{1}{2}\sigma^2) T}{\sigma\sqrt{T}}$$

Is a standard normal variable with mean zero and unit variance. The value of a call option can be calculated as the discounted value of the expected intrinsic value using the risk neutral expectation. That is

$$c (0)=e^{-rT}\mathrm{E}_*[\max\{S (T)-K,       0\}].$$

Thus we need to calculate the expected value of $S (T)-K$ conditional on the option ending in the money,       $S (T)>K$ .The value of the option consists of

Two parts: the future value of the underlying asset conditional on $S (T)>K$ and the strike price paid times the probability the option is exercised. The probability the option is exercised is the probability $S (T)>K$ .This will be given by $1-N (x)$ where

$$x=\frac{\ln K-\ln S (0)-(r-\frac{1}{2}\sigma^2) T}{\sigma\sqrt{T}}.$$

Since $1-N (x)=N (-x)$ the probability of exercise is $N (d_{2})$ where

$$-x=d_2=\frac{\ln (S (0)/K)+(r-\frac{1}{2}\sigma^2) T}{\sigma\sqrt{T}}.$$

It canalsobe shown by integration that the expected future value of the underlying asset conditional on $S (T)>K$ is $S (0) e^{rT^{\prime}}N (d_{1})$ where $d_{1}=d_{2}+$ $\sigma{\sqrt{T}}$ Hence

$$c (0)=e^{-rT}\left (S (0) e^{rT}N (d_1)-KN (d_2)\right)$$

Which is the Black-Scholes formula

### Summary

We have considered three ways in which the Black-Scholes formula may be derived. The first is to develop a second-order partial differential equation by creating a riskless portfolio by dynamically $\Delta$ -hedging. The second is to synthesize the option by using the underlying and the risk-free asset. This second method is more satisfactory as it does not assume the existence of a well defined option price but derives it from the assumption that all arbitrage opportunities are eliminated in the market. The third method considers replaced actual probabilities by fictitious risk-neutral probabilities so that all assets satisfy a martingale property. This then allows one to replace the actual return on the underlying asset with the risk-free rate. This allows a straightforward derivation of the formula.

# The Greeks

### Introduction

We have studied how to price an option using the Black-Scholes formula. Now we wish to consider how the option price changes,       either over time or as the parameters in the formula are changed. As the price of an option changes the risk of the option changes too. Therefore knowing how the option prices changes enables the trader to hedge the risks of holding the option.

These notes will consider the various measures of how the option price changes. These measures are known as the Greeks as each of them is given a Greek letter. 1 We shall consider what these Greek letters measure and how they relate to each other. We shall also consider implied volatility and volatility smiles. We shall make use of the put-call parity condition for European options.

Keywords: Delta,       Gamma,       Rho,       Vega,       Theta,       Hedging,       Volatility smiles

Reading: Hull Chapters 15 and 16

### The Greeks

We have from the Black-Scholes formula that the price of a call option depends on on the price of the underlying asset,       $S$ ，the strike price $K$ ，the time to maturity,       $T$ ,      the interest rate,       $T$ and the volatility,       02 Write this as

A function $C=C (S,       K,       T,       r,      \sigma)$ .Then using a first-order approximation we have

$$\begin{aligned}
C (S+\delta S,       K,       T+\delta T,       r+\delta r,      \sigma+\delta\sigma)& =C (S,       K,       T,       r,      \sigma) \\
&+\delta S\frac{\partial C}{\partial S}+\delta T\frac{\partial C}{\partial T}+\delta r\frac{\partial C}{\partial r}+\delta\sigma\frac{\partial C}{\partial\sigma}.
\end{aligned}$$

This show the effect of varying each of the parameters,       $S$ ， $T$ ， $T$ ， 0 by small amounts $\delta S$ $\delta T$ ， $\delta r$ and $\delta\sigma$ but with $K$ fixed. The same will be true for any option or portfolio of options. Thus if $\Pi=C (S,       T,       r,      \sigma)$ is the value of the option or portfolio of options then the value of the portfolio after a smal change in the parameters is given by 3

$$\begin{aligned}
\Pi (S+\delta S,       K,       T+\delta T,       r+\delta r,      \sigma+\delta\sigma)& =\Pi (S,       K,       T,       r,      \sigma) \\
&+\delta S\frac{\partial\Pi}{\partial S}+\delta T\frac{\partial\Pi}{\partial T}+\delta r\frac{\partial\Pi}{\partial r}+\delta\sigma\frac{\partial\Pi}{\partial\sigma}.
\end{aligned}$$

Each of the partial effects is given a Greek letter.

Delta $\Delta$ = $\partial \Pi / \partial S$ . $\Delta$ measures how the option price changes when the price of the underlying asset changes.

Theta $\Theta=-\partial\Pi/\partial T$ . $\Theta$ measures how the option price changes as the time to maturity decreases.

Rho $\rho=\partial\Pi/\partial r$ ： $\rho$ measures how the option price changes as the interest rate changes.

Vega $v=\partial\Pi/\partial\sigma$ . $U$ measures how the option price changes as the volatility changes

There is also another Greek that measures how $\Delta$ changes as $S$ changes This is known as Gamma.

Gamma $\Gamma$ = $\partial \Delta / \partial S$ = $\partial ^{2}\Pi / \partial S^{2}$ ： $\Gamma$ measures the rate of change of the option's $\Delta$ as the price of the underlying changes.

We shall discuss each of these a little further.

### Delta

We have shown in the binomial model that holding a position that is $\Delta$ units long in the stock and short one call option we have a portfolio that is risk free. The price of this portfolio is $\Pi (S,       K,       T,       r,      \sigma)=\Delta S-C (S,       K,       T,       r,      \sigma)$ TheDelta of the portfoliois therefore

$$\Delta_{\Pi}=\frac{\partial\Pi}{\partial S}=\Delta-\frac{\partial C}{\partial S}=\Delta-\Delta_{C}$$

Where $\Delta_{C}$ is the Delta of the call option. If the portfolio is risk-free it will not depend on $S$ and hence $\Delta_{\Pi}=0$ .Such aportfolio is said tobe delta neutral. It therefore follows that $\Delta_{C}=\Delta$ .That is the $\Delta$ we calculate in replicating the option or creating a risk neutral portfolio is the Delta of the option itself

This gives a convenient method for finding $\Delta$ from the Black-Scholes formula. Let's take the Black-Scholes formula

$$C (S,       K,       T,       r,      \sigma)=SN (d_1)-e^{-rT}KN (d_2)$$

Where

$$\begin{array}{rcl}d_1&=&\frac{\ln (\frac{S}{K})+(r+\frac{1}{2}\sigma^2) T}{\sigma\sqrt{T}}\\\\d_2&=&d_1-\sigma\sqrt{T}=\frac{\ln (\frac{S}{K})+(r-\frac{1}{2}\sigma^2) T}{\sigma\sqrt{T}}\end{array}$$

We wish to find $\partial C/\partial S$ where we have to remember that both $d_{1}$ and $d_{2}$ depend on $S$ .To find $\Delta$ we first note that the call price has the property

That if we double the strike $K$ and double the price of the underlying $S$ the call price doubles. This is exactly what we should expect. If we change the currency denomination of the asset from pounds to dollars and there are two dollars per pound then the strike price and the price of the underlying should double and the call price should also be double. A function with this property is said to be linearly homogeneous in $S$ and $K$ .More generally this means that

$$\lambda C (S,       K,       T,       r,      \sigma)=C (\lambda S,      \lambda K,       T,       r,      \sigma)$$

For any $\lambda>0$ .It therefore follows from Euler's Theorem that

$$C (S,       K,       T,       r,      \sigma)=S\frac{\partial C}{\partial S}+K\frac{\partial C}{\partial K}.$$

Since the Black-Scholes formula has the form $C ( S,       K,       T,       r,       \sigma )$ = $Sx- Ky$ where $x=N (d_{1})$ and $y=e^{-rT}N (d_{2})$ .This therefore implies that $\partial C/\partial S=$ $N (d_{1})$ and ( $\partial C/\partial K=-e^{-rT^{\prime}}N (d_{2}))$ and therefore that $\Delta=N (d_{1})$

Question: Give an interpretation for $\partial C/\partial K$ [Hint: Consider the effect of a one unit increase in the strike price on the profitability of holding the option.

Notice that since $\Delta$ = $N ( d_{1})$ ， 0 $\leq$ $\Delta$ $\leq$ 1 as $N (d_{1})$ is a cumulative probability. This is again what we should expect. The $\Delta$ tell us how much of the underlying asset to buy to replicate the option. Only if we know for sure that the option will be exercised will we replicate it by buying the underlying asset. If there is some possibility that the option will not be exercised then we only need to buy a fraction of the underlying asset (whilst partly borrowing in order to pay for the asset).

Question: What is the $\Delta$ Of a forward contract? [Hint: The forward contract has a value of $S-Ke^{-rT}$

It is important to remember that $\Delta$ changes (with $S$ and 7 ) and therefore a portfolio that replicates the call will change over time and as the time to

Maturity gets closer. The appropriate replicating portfolio or hedge thus changes over time. This is known as rebalancing and the the the strategy of keeping a delta-neutral portfolio is known as dynamic delta-hedging

The $\Delta$ of a put option can easily be calculated from the put-call parity conditions for European options:

$$C=P+(S-Ke^{-rT}).$$

Differentiating the above equation with respect to $S$

$$\Delta_C=\Delta_P+1$$

Where $\Delta_{C}=\partial C/\partial S$ and $\Delta_{P}=\partial P/\partial S$ .Thus

$$\Delta_P=\Delta_C-1=N (d_1)-1.$$

The $\Delta$ of the put option is negative ( -1 $\leq$ $\Delta _{P}$ $\leq$ 0 ）indicating that to replicate the put option we mush short sell the underlying asset or tohedge a long position in the option we buy the underlying asset.

Question: How would you hedge a long position in the forward contract? What is the $\Delta$ of a forward contract?

## Theta

Theta measures how the option price changes as the time to maturity approaches. With some differentiation and manipulation it can be shown that

$$\Theta_C=-\frac{\partial C}{\partial T}=-\frac{SN' (d_1)\sigma}{2\sqrt{T}}-rKe^{-rT}N (d_2).$$

This shows that $\Theta_{C}<0$ .That is the price of the option declines as maturity approaches or that longer dated options are more valuable. We know that

This is true for American options because the longer dated options give all the opportunities for profit as the earlier dated options and more besides. The same applies for European options (on non-dividend paying stocks) because the early exercise of an American call option is never optimal and therefore European and American call options are equivalent. To see that early exercise is not optimal consider again the put-call parity condition $C=P+(S-$ $Ke^{-rT}$ ). Since the put option is a limited liability asset its price must be non-negative. Hence $P\geq 0$ and therefore $C\geq S-Ke^{-rT}$ .Thus a lower bound for the call price is $C$ $\geq$ $\operatorname* { max} \{ 0,       S- Ke^{- r^{\prime }T}\}$ .Now if $r>0$ this means $C>S-K$ .Since the American option cannot be worth less than the equivalent European option we therefore also have $C^{A}>S-K^{6}$ and hence it will always be better to sell the option rather than exercise it early. Thus American and European options on non-dividend paying stock are equivalent.

The situation is slightly different for European put options. From differentiating the put-call parity condition with respect to $T$ weget

$$-\Theta_C=-\Theta_P+rKe^{-rT}.$$

Hence

$$\Theta_{P}=-\frac{\partial C}{\partial T}=-\frac{SN' (d_{1})\sigma}{2\sqrt{T}}-rKe^{-rT}N (d_{2})+rKe^{rT}$$

Which may be of either sign. The same argument applies as for a call option. The longer dated option will in general be more valuable. However for an American put option early exercise may be optimal. This is because by exercising early the investor gets the strike price earlier. In the extreme case where the option is deep-in-the money and the stock price is close to zero then there is little chance of falling lower. As there may be some chance of it increasing,       it may be optimal to exercise early and get the maximum gain at an earlier point in time. 7 Thus an American put option will be worth more

Than a European option. Thus although $\Theta$ for an American put option will be negative the $\Theta$ of a European put option may in some cases be positive.

It should be remembered that $\Theta$ should not really be considered a hedge parameter in the way $\Delta$ is a hedge parameter for $S$ .There is no uncertainty about the approach of the expiration date and hence no risk against which to hedge. Nevertheless $\Theta$ is related to another hedge parameter Gamma and therefore it is information that is normally tracked by traders.

### Gamma

Gamma measures how much $\Delta$ changes as the price of the underlying asset S changes and thus provides information about the appropriate dynamic hedging strategy and how $\Delta$ should be changed as S changes. If $\Gamma$ is large then it will be necessary to change $\Delta$ by a large amount as $S$ changes. In this case it will be risky to leave $\Delta$ unchanging even over shorter periods. On the other hand if $\Gamma$ is small then the costs of leaving $\Delta$ unchanged will be relatively small. Often traders wish to create a portfolio which is gamma. Neutral as well as delta-neutral. The reason for this is that it may not be feasible or desirable to change $\Delta$ continuously to keep a completely deltaneutral portfolio and hence a gamma-neutral portfolio will mean that the costs of not keeping the portfolio completely delta-neutral will be minimised. It is important to realise however,       that a gamma-neutral portfolio cannot be achieved by using only the underlying asset (or a forward contract) since the Gamma of the underlying asset is zero. Thus suppose that the delta-neutral portfolio has a Gamma of $\Gamma_{x}$ and that there is another traded option that has a gamma of $\Gamma_{y}$ . Then selling $\Gamma_{x}/\Gamma_{y}$ of the traded options will create a new portfolio that is gamma-neutral.

Given that for a call option $\Delta=N (d_{1})$ and $\Gamma$ = $\partial \Delta / \partial S$ it is easy to calculate that the Gamma for a call option is

$$\Gamma_C=\frac{N' (d_1)}{S\sigma\sqrt{T}}$$

Where $d_{1}$ is as given above and $N^{\prime }( d)$ = $( e^{d^{2}/ 2}) / \sqrt {2\pi }$ .Since $N^{\prime}(d)>0$ we have that $\Gamma_{C}>0$ which shows that the call price is a conver function of the price of the underlying asset. Since $\Delta_{P}=\Delta_{C}-1$ from the put-call parity condition,       we have by differentiating that

$$\Gamma_P=\Gamma_C$$

So that the Gamma of a put and an equivalent call are the same.

We can see the relationship between. $\Delta$ ， $\Theta$ and $\Gamma$ from the Black-ScholesMerton Partial Differential Equation. This states that the price $C^{r}$ of any option or portfolio of options satisfy.

$$C=\frac{1}{r}\left\{\left (\frac{\partial C}{\partial T}+rS\frac{\partial C}{\partial S}+\frac{1}{2}\sigma^2 S^2\frac{\partial^2 C}{\partial S}\right)\right\}$$

Which can be re-written as

$$C=\frac{1}{r}\left\{\left ((-\Theta+rS\Delta+\frac{1}{2}\sigma^2\Gamma\right)\right\}.$$

This equation canbe used for calculating one of $\Theta$ ， $\Gamma$ and $\Delta$ if the other two are known. Also it follows directly from this equation that any portfolio which is delta-neutral and gamma-neutral is also theta-neutral

## Vega

Vega measures how the option price changes as volatility changes. The Vega of a call option is given by

$$v_C=S\sqrt{T}N' (d_1).$$

Also from the put-call parity condition we have that $UC=UP$ .It isimportant to understand why Vega is studied. In the Black-Scholes model volatility is assumed to be constant. Thus it makes much less sense to consider how the Black-Scholes formula changes in response to a change in volatility than to a change in the underlying price. However,       the relevant volatility for calculating the option price is the volatility of the underlying asset over the lifetime of the option. This is a future volatility,       which is not observable. It can be seen that the Vega of a call or put option is positive? And so ,      10 itis possible to use the known market price of the option to impute the volatility This is known as the implied volatility. It is therefore possible to use market prices to calculate implied volatility. More on this later.

R.ho

Rho measures the sensitivity of the option price with respect to theinterest rate. As with the volatility an assumption of the Black-Scholes modelis that interest rates are constant over the life of the option. For a call option it can be shown that

$$\rho_C=KTe^{-rT}N (d_2)$$

Which is non-negative. This is because a rise in the interest rate reduces the present value of the strike price to be paid out if the option is exercised and this will raise the option price. From the put-call parity condition $C=$ $P+(S-Ke^{-rT})$ weget

$$\rho_C=\rho_P+KTe^{-rT}$$

Sothat

$$\rho_P=KTe^{-rT}(N (d_2)-1)=-KTe^{-rT}N (-d_2)$$

Which is non-positive. This is because as the interest rate rises the present value of the strike price received at expiration,       if the option is exercised declines reducing the price of the put.

## Volatility

### Implied volatility and volatility smiles

As we have discussed the volatility that is required to calculate the BlackScholes formula is a future volatility which is in principle unknown. It may be calculated on the basis of historic volatility but this may not be an accurate reflection of future volatility. It is therefore common to take the market prices for options and calculate the volatility which if used in the BlackScholes formula would give the market price. This can be done as Vega is positive so that no two different volatilities can imply the same price.

If the Black-Scholes formula were correct then all similarly dated options on the same underlying should have the same implied volatility. If however,       the implied volatility is calculated and plotted against the strike price then there is typically a u-shaped pattern with the bottom of the U near the atthe-money strike price. Such a pattern is known as a volatility smile. Given that Vega is positive one might imagine that this implies some arbitrage opportunity. Either the low volatility options are underpriced or the higher volatility options are overpriced and one can buy the low volatility options and sell the high volatility options to yield a profit. However,       these smiles appear to persist so the arbitrage opportunity is probably more apparent than real.

The smile is more an expression of the market's view of the imperfections of the Black-Scholes model itself. The two main imperfections are first the assumption that the underlying prices follow geometric Brownian motion and

So are lognormally distributed and second that the dynamic hedging which requires continuous adjustment can be carried out without cost.

## Fat tails,       jumps and stochastic volatility

The assumption of geometric Brownian motion matches the data well but not perfectly. When one compares actual data to that expected one finds that actualdata exhibits kurtosis. Thismeans that the tails are fatter or thicker than expected and the distribution is more highly peaked at the centre.

One way of modelling fat tails is to assume that volatility is itself stochastic and itself follows something like a geometric Brownian motion process Another approach is to assume tat volatility is a function of changes in the stock price so that big changes increase volatility.

Another approach is to consider processes that allow for jumps at some discrete points. The jumps themselves follow a Poisson process and this is added to the continuous Brownian motion process for the stock return. These mixed models are know as jump-diffusion processes

These alternatives for the Black-Scholes model are not universally better. Which model fits better will depend on the market being studied. Thus jumps in stock prices are quite common but are less common in foreign exchange markets. This leaves much open for analysis and future work and most trading banks will have teams of analysts working on exactly this. They will typically be using discrete and numerical methods as well as mathematical models. This of course also makes a topic for dissertation work.

### Conclusion

We have discussed what is meant by the Delta,       Theta,       Gamma,       Rho and Vega of an option. We have considered the relationship between $\Theta$ ， $\Delta$ and $\Gamma$ for an option or portfolio of option. We have also discussed how to impute volatility from knowledge of market prices and the empirical phenomenon of volatility smiles and how these might be accounted for by stochastic modelling of volatility


