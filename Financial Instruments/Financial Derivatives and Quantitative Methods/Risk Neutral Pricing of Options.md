---
cssclasses:
  - academia
title: Risk Neutral Pricing of Options
tags:
  - american_option
  - call_option
  - european_option
  - intrinsic_value
  - maturity_date
  - options
  - put_option
  - strike_price
  - time_value
aliases:
  - Option Holder
  - Option Payoffs
  - Option Pricing
  - Option Writer
key_concepts:
  - Derivative assets
  - Expiration date
  - Option payoffs
  - Option types
  - Underlying asset
---

 
[[Risk Neutral Pricing of Options|Risk Neutral Pricing]]

# Risk Neutral Pricing of Options
# Options

These notes describe the payoffs to European and American put and call options—the so-called plain vanilla options. We consider the payoffs to these options for holders and writers and describe both the time value and intrinsic value of an option. We explain why options are traded and examine some of the properties of put and call option prices. We shall show that longer-dated options typically have higher prices and that call prices are higher when the strike price is lower,  and that put prices are higher when the strike price is higher.

Keywords: Put,  call,  strike price,  maturity date,  in-the-money,  time value intrinsic value,  parity value,  American option,  European option,  early exercise,  bull spread,  bear spread,  butterfly spread.

# 1. Options

Options are derivative assets. That is,  their payoffs are derived from the payoff on some other underlying asset. The underlying asset may be an equity,  an index,  a bond,  or indeed any other type of asset. Options themselves are classified by their type,  class,  and series. The most important distinction of types is between put options and call options. A put option gives the owner the right to sell the underlying asset at specified dates at a specified price. A call option gives the owner the right to buy at specified dates at a specified price. Options are different from forward/futures contracts as a put (call) option gives the owner the right to sell (buy) the underlying asset but not an obligation. The right to buy or sell need not be exercised. There is also a last date on which the right may be exercised,  and this is known as the expiration date or maturity date. The specified price is called the strike price or exercise price.

The most commonly traded option is the American type,  which may be exercised at any trading date prior to or at the expiration date. There are also options of the European type,  which may only be exercised at the expiration date. Thus,  an American put and a European put are different types of options. Another type is the Bermuda option,  which is halfway between the European and American option as it can only be exercised on a limited number of pre-specified days prior to maturity. We shall focus mainly on European options as there is an important parity condition between the prices of European put and call options,  and we shall explain how the prices of American options differ from their European counterparts.

The owner or buyer of an option is often called the holder,  and the seller of an option is termed the writer. Thus,  at the date of sale,  the holder pays the writer the price of the option. For a call option,  there may be a subsequent transaction at the expiration date where the writer provides the underlying asset to the holder in exchange for the agreed strike price. This subsequent transaction is made at the instigation of the holder and will only be undertaken if it is in the holder's interest. The holder's right to buy the stock at or prior to the expiration date need not be exercised. For a put option,  the subsequent transaction is that the holder provides the underlying asset in return for the agreed strike price from the writer.

The difference between American and European options is simply what choices the holder has prior to the expiration date. The holder of the European option has,  at any point prior to the expiration date,  the choice either to sell the option for the prevailing market price or to retain it. The holder of an American option has,  at any point prior to the expiration date,  three choices: either to sell the option for the prevailing market price,  to retain it,  or to exercise it. The latter case is said to involve early exercise. This terminology is not meant to imply that there is anything suboptimal about

exercising before the expiration date. Indeed,  we will give below examples where the American option will be exercised early.

A class of options is all options of a particular type on the same underlying asset. Thus,  all American put options on IBM stock form one class. European call options on the FTSE 100 index form another class. A class will involve a variety of different strike prices and maturity dates. Most options are exchange-traded,  and the exchange will specify a range of maturity dates,  usually every two months,  and a range of strike prices,  usually centered around the prevailing market price. An option series is simply the options of a given class with the same strike price and maturity date.

### Payoff at Maturity

Let $X$ be the exercise price and $S_{T}$ the price of the underlying stock at the maturity date. Then the payoff to a put option is

$$p_T=\left\{\begin{array}{ll}X-S_T&\text{if}S_T\leq X\\0&\text{if}S_T>X.\end{array}\right.$$

For more simply $p_{T}=\operatorname*{max}[X-S_{T},    0]$. If $S_{T}<X$,  then the put is said to finish in-the-money and the option will be exercised. The holder of this option will buy the underlying stock at a price of $S_{T}$ and exercise their right to sell it to the writer at the strike price of $X$ to make a profit of $X-S_{T}$. If $S_{T}>X$,  the option is said to finish out-of-the-money and exercising the right to sell the underlying asset would result in a loss. So the right to sell won't be exercised. The payoff will be zero in this case. Hence,  with an option,  the payoff is never negative. Assets with non-negative payoffs are known as limited liability assets.

Suppose that you hold a put option on a stock $PDQ$. The exercise price is 1000 and the expiration date is in four weeks. The current stock price of $PDQ$ is 1109. If the stock is still at 1109 in four weeks’ time,  you may let the option expire without exercising your right to sell at 1000. If you exercised your right to sell,  you would have to deliver the stock,  which would cost you 1109,  and you would receive only 1000 in return. Clearly,  exercising the option to sell would result in a loss. You will not exercise,  and your payoff is $\operatorname*{max}[X-S_{T},    0]=\operatorname*{max}[1000-1109,    0]=0$. However,  if $PDQ$ does badly and the stock price falls to 900 after four weeks,  you,  as the holder of the put option,  will do well. In that case,  you can exercise your right to sell,  buying the stock at the reduced price of 900 and selling it to the holder at 1000. The payoff at maturity is $\operatorname*{max}[X-S_{T},    0]=\operatorname*{max}[1000-900,    0]=100$ per unit.

Equally,  the payoff to the holder of a call option is

$$c_T=\left\{\begin{array}{ll}0&\text{if}S_T\leq X\\S_T-X&\text{if}S_T>X.\end{array}\right.$$

For more simply,  $c_{T}=\max[0,    S_{T}-X]$. In this case,  the call finishes in the money if $S_{T}>X$ as the option holder can exercise the right to buy the underlying asset at a price of $X$ when it is worth the greater amount $S_{T}$. If $S_{T}\leq X$ ,  the call option finishes out of the money,  and the right to buy will go unexercised.

The writer of the call option has exactly the reverse of the payoff to the holder. The writer of the call has a payoff of $-c_{T}$ = $- \max [ 0,    S_{T}X]$ = $\operatorname*{min}[0,    X-S_{T}]$. When the option is exercised,  the writer will have to deliver a stock worth $S_{T}$ and receives a payment of $X$ from the holder. Since $S_{T}>X$,  the writer makes a loss of $X-S_{T}$. Likewise,  the payoff at maturity to the writer of a put option is $-p_{T}=-\operatorname*{max}[X-S_{T},    0]=\operatorname*{min}[S_{T}-X,    0]$.

The intrinsic value or parity value of an option at time $t$ is the payoff to the option if the current date were the maturity date. Thus,  the intrinsic value of the call option at time $t$ is $\operatorname*{max}[0,    S_{t}-X]$ where $S_{t}$ is the current price of the underlying asset,  and the intrinsic value of a put option is $\operatorname*{max}[X-S_{t},    0]$.

An American option will always trade at a price at or above its intrinsic value since with an American option,  it is always possible to exercise the

option now and realise the intrinsic value. The difference between the price of an option and its intrinsic value is known as the premium or time value of the option. Thus,  the price of an option is the sum of its intrinsic value plus its premium

$$\text{price of option}=\text{intrinsic value}+\text{time value}.$$

If an option is initially set up at date 0 when the stock price is $S_{0}$ and with the strike price set such that $X=S_{0}$,  then the intrinsic value of the option is 0 and the premium and price are equivalent. Many options were historically set up with the strike price equal to the prevailing price of the underlying asset (or at-the-money as it is called),  and this accounts for why the option price is sometimes referred to as the option premium. We will use the term time value rather than premium to avoid confusion.

## Why trade options?

It is easy to see why it might be desirable to trade options. Suppose you buy a call option with an exercise price equal to the current stock price. If the stock goes up in value,  you can still buy at the low current price and sell at the new higher price. And if you are unlucky and the price falls,  then you simply don’t exercise the option. All you lose is the price you paid for the option in the first place. You only buy the stock when the price has gone up. You get all the upside benefits and eliminate the downside risk. You don't have to risk buying the stock in that hope that the price will rise. You simply buy the option which costs a fraction of the price of the stock itself.

Because you only pay for the stock at maturity,  buying a call option is equivalent to borrowing most of the money to buy the stock and repaying only if the bet goes well. Thus,  a call option is a highly levered or geared position in the stock and thus with a return that is higher but also highly risky.

To see this,  consider the following simple example. The current price of the stock is 100,  and a call option on the stock with a strike price of 100 costs 30. Suppose that the stock price at maturity has risen to 175. The rate of return on the stock is a handsome75%. However,  the return on the call option is greater still. If the stock price rises to 175,  the call option can be exercised to make a profit of 175 - 10=75. Since the call costs 30,  the rate of return is $\frac{75}{30} - 1=1.5$ or150% . The high leverage makes possible a high rate of return on the relatively small investment. On the other hand,  suppose the stock finishes out of the money at 75. Owning the stock results in a rate of return of -25%. The call option,  however,  expires valueless,  so the rate of return on the investment in the call option is -100%. Not such a good prospect.

Suppose these are the only two possible values for the stock at maturity and suppose that TT is the probability the stock price rises and $(1 - \pi)$ is the probability it falls. Suppose that the interest rate over the period is25%. The risk premium on the stock is

$$rp_S=75\pi+(-25)(1 - \pi) - 25=100\pi - 50$$

And the risk premium on the call option is

$$rp_C=150\pi+(-100)(1 - \pi) - 25=250\pi - 100.$$

It is clear that the risk premium on the call is 2.5 times the risk premium for the stock irrespective of the value of 71. This ratio is known as the option elasticity,  and it can be shown that for a call option,  it is always greater than one. Thus,  the call option is always riskier than the underlying stock. The high risk means that options are good and cheap ways to hedge risk,  as we shall see later on.

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
			<th>CallsAug</th>
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

Table 1 gives the prices of options on two stocks,  Tesco and Rolls Royce,  given in the Financial Times on Tuesday,  March 6,  2000. The starred number in the left column gives the closing stock price on the previous day,  and the paper reports the prices for puts and calls of three maturities,  May,  August,  and November,  for strike prices on either side of the closing price.

Three things are immediately obvious from this table. First,  the option prices increase with the maturity date for any given strike price. Second,  the price of calls falls with the strike price for any given maturity date,  and third,  the price of puts rises with the strike price with any given maturity date.

For a given strike price,  the table shows that the price of calls increases with the date to maturity. That is,  $C_{t}(T_{2})\geq C_{t}(T_{1})$ for $T_{2}>T_{1}$,  where $C_{t}(T_{1})$ is the price of an American call option at date $t$ that matures at date $T_{1}$,  and $C_{t}(T_{2})$ is an option of the same type and class and with the same strike price but with a longer maturity. 1 From the table,  we can see that August calls on Tesco stock with a strike price of 160 trade at 27,  but the longer maturity November calls trade at 31. There would be a simple arbitrage opportunity if $C_{t}(T_{1})>C_{t}(T_{2})$ for $T_{2}>T_{1}$. Suppose that the prices were reversed and the

November call on Tesco trades at 27,  and the August call trades at 31. Then,  buying the lower-priced November call and writing the August call yields a net inflow of 4 today. Either the August call expires or is exercised prior to maturity. In either case,  its value is $\operatorname*{max}[0,    S_{t^{\prime}}-X]$ where $t^{\prime}$ is the maturity date in August or some time prior to the maturity date when the call is exercised. The value of the position is $C_{t^{\prime}}(Nov)-\operatorname*{max}[0,    S_{t^{\prime}}-X]$ . If this is positive,  then sell the November call at date $t^{\prime}$ to make a profit. Otherwise,  exercise the November call. Exercising the call yields the same value of $\operatorname*{max}[0,    S_{t^{\prime}}-X]$ no matter what the maturity date. So,  there is a completely offsetting gain from the bought November call and the written August call. In either case,  an arbitrage profit has been made. Note that this does not say anything about how the call value changes over time until maturity. It only compares prices at a particular date of options with different expiration dates. Neither does the argument work for European options,  which cannot be exercised early. However,  as an empirical matter,  European options do demonstrate the same pattern of prices rising with date to maturity.

Equally clear is that a call with a lower strike price must command a higher price. Thus,  $C_{t}(X_{1})\geq C_{t}(X_{2})$ if $X_{2}>X_{1}$ . This can be seen from Table 1. For example,  May calls on Rolls-Royce with a strike price of 200 are worth 11,  but the May calls with the lower strike price of 180 are worth 22. This is simply because the call gives the holder the option to buy,  and the lower the exercise price at which the stock can be bought,  the more valuable is the option. If this were not true and $C_{t}( X_{1})$ < $C_{t}( X_{2})$ for $X_{2}>X_{1}$,  then there is an arbitrage opportunity,  and the appropriate response is a bull spread. The payoffs can be seen in Table 2. This strategy buys the call with the lower strike price of $X_{1}$ and writes the call with the higher strike price of $X_{2}$,  leading to a cash inflow now of $C_{t}(X_{2})-C_{t}(X_{1})>0$ . In each case,  the payoff at maturity is non-negative. Thus,  for European options,  $c_{t}(X_{1})\geq c_{t}(X_{2})$ for $X_{2}>X_{1}$. Equally,  suppose the options are of the American type. Then,  if the written option is exercised early,  the holder of that option will pay us $X_{2}$ for the stock. If we exercise the bought option immediately,  the stock can be

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
			<td>0 overall</td>
			<td>0</td>
			<td>$S_{T}-X_{1}>0$</td>
			<td>$X_{2}-X_{1}>0$</td>
		</tr>
	</tbody>
</table>

Table 2: Bull Spread

Bought for $X_{1}$ and then sold for $X_{2}$,  leading to a profit of $X_{2}-X_{1}$. Hence,  we have for American options $C_{t}(X_{1})\geq C_{t}(X_{2})$ for $X_{2}>X_{1}$.

Another property that we can see from the table is that the differences in the call or put option prices for a given stock and maturity date are less than the difference between the strike prices. For example,  the difference in the option prices for November calls on Tesco stock is 31-23=8,  which is less than the difference in strike prices,  which is 180-160=20. Thus,  for call options,  we have $C_{t}(X_{1})-C_{t}(X_{2})\leq X_{2}-X_{1}$ for $X_{2}>X_{1}$. Indeed,  if this were not the case and $C_{t}(X_{1})-C_{t}(X_{2})>X_{2}-X_{1}$,  there would again be an arbitrage opportunity. The strategy to exploit the arbitrage opportunity would be a bear spread where the option with the higher strike price is purchased,  and the lower strike price option is sold,  together saving the difference in the strike prices,  that is,  buying $(X_{2}-X_{1})$ risk-free bonds with maturity at date $T$ and an interest rate of 7 between the current date $t$ and the maturity date. The payoffs from this strategy are given in Table 3,  and the payoff is always positive at maturity,  and so the value of the portfolio $V_{t}$ must itself be positive. Thus,  for European options,  $V_{t}=c_{t}(X_{2})-c_{t}(X_{1})+(X_{2}-X_{1})>0$. If the options are American,  the value of the portfolio is $V_{t}$ = $C_{t}( X_{2})$ - $C_{t}(X_{1})+(X_{2}-X_{1})>0$,  but we need to decide what to do if the written call is exercised prior to maturity. Suppose it is exercised at time $t^{\prime}$ when the stock price is $S_{t^r}$. To meet our obligations on the written call,  we must buy the stock at $S_{t^{\prime}}$ and sell it at $X_{1}$. The purchased call is worth $C_{t^{\prime}}(X_{2})$ at time $t^{\prime}$. If $C_{t^{\prime}}(X_{2})>S_{t^{\prime}}-X_{2}$,  then we simply sell our call to cover our obligation and make a net profit and,  in addition,  have our risk-free bonds. If

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
			<td>$(X_{2}-X_{1})(1+i)$</td>
		</tr>
		<tr>
			<td>0 overall</td>
			<td>$V_{t}$</td>
			<td>$(X_{2}-X_{1})(1+r)$ </td>
			<td>$(X_{2}-S_{T})+r (X_{2}-X_{1})>0$</td>
			<td>$r (X_{2}-X_{1})>0$</td>
		</tr>
	</tbody>
</table>

Table 3: Bear Spread plus Savings

$C_{t^{\prime}}(X_{2})<S_{t^{\prime}}-X_{2}$ ,  then we exercise the call,  buying the stock at $X_{2}$ and selling it at $X_{1}<X_{2}$. The loss on this transaction is covered by closing out our bond position,  so we retain the accumulated interest $r^{\prime}(X_{2}-X_{1})$ where $r^{\prime}$ is the interest rate from $t$ to $t^{\prime}$.

One property not apparent from the table is the relationship between options with more than two strike prices. Suppose that May puts on Rolls-Royce with a strike price of 190 are traded. It is to be expected that they trade at a price somewhere between the 8 and 18. Suppose that all the puts are European,  then it is simple to show that the May European put with a strike of 190 cannot trade at a price above 13,  which is the mid-way point between 8 and 18. To establish this claim,  consider another popular trading strategy,  the butterfly spread. This spread consists of a portfolio of buying one put with a strike price of 180,  buying another put with a strike price of 200,  and selling two puts with a strike price of 190. The payoffs at maturity to this strategy are given in Table 4. In each case,  the payoffs at maturity are positive,  so we can be assured that the value of the portfolio is non-negative. Hence,  $26-2p_{t}(190)\geq0$ or $p_{t}(190)\leq13$. This argument again applies to American as well as European options. If the written puts are exercised early,  then either exercise both puts immediately to cash-out the position or one or both of the puts can be sold if this yields a higher profit.

Using butterfly spreads in this way establishes that for puts with strike prices $X_{1}$ and $X_{3}$ ,  the price of the put with the mid-way strike price of

<table>
	<tbody>
		<tr>
			<th>$\mathbf{Position}$</th>
			<th>Value</th>
			<th>$S_T <180$ </th>
			<th>$180<S_{T}<190$</th>
			<th>$190<S_T<200$</th>
			<th>$S_{T}$ 200 $<i>$</th>
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
			<td>2nd Long Put</td>
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

Table 4: Butterfly Spread with Puts

## $\frac{1}{2}X_{1}+\frac{1}{2}X_{3}$ satisfies

$$P_{t}(\frac12X_{1}+\frac12X_{3})\leq\frac12P_{t}(X_{1})+\frac12P_{t}(X_{3}).$$

A slightly more general interpretation would be to buy a fraction $\lambda$ units of the put with strike price of $X_{1}$ and buy a fraction $(1-\lambda)$ units of the put with strike price $X_{3}>X_{1}$ and write one put with a strike price of $X_{2}=\lambda X_{1}+(1-\lambda)X_{3}$. With this portfolio,  it can be found that

$$P_{t}(\lambda X_{1}+(1-\lambda)X_{2})\leq\lambda P_{t}(X_{1})+(1-\lambda)P_{t}(X_{2}).$$

It therefore follows from arbitrage principles that the put price is a convex function of the strike price. Equally,  constructing a butterfly spread for calls also shows that the call price is a convex function of the strike price.

## 3 Summary

We have seen how the payoffs to put and call options depend on the underlying assets and how the prices of puts and calls depend on the length of time to maturity and strike price. We shall explore other properties of option prices and ultimately derive an expression for how option prices depend on the strike price,  time to maturity,  interest rate,  volatility,  and current price of the underlying asset. Indeed,  we shall see how any derivative asset can be priced.

# Options

These notes consider the way put and call options and the underlying can be combined to create hedges,  spreads,  and combinations. We will consider the parity condition that applies to put and call options and consider arbitrage bounds that apply to the prices of puts and calls.

Keywords: American option,  European option,  early exercise,  put-call parity,  hedge,  spread,  combination,  bull spread,  bear spread,  strap,  arbitrage bounds,  covered call,  protective put.

Reading: Chapters 9 and 10 from Hull.

# 1 Option Trading Strategies

There are basically three varieties of trading strategies. A hedge combines an option with an underlying stock to protect either the option or the stock against loss. A spread combines options of the same class but different series,  where some are bought and others written. A combination combines options of different types,  both bought or both written,  on the same underlying stock.

## A hedge

Suppose that you write a call option. The payoff to a call option at maturity is $\operatorname*{max}[0,    S_{T}-X]$ where $X$ is the strike price and $S_{T}$ is the price of the underlying at maturity. Your payoff at maturity having written the call is therefore min $[0,    X-S_{T}]$ . If the price of the underlying rises above the strike price,  you will make a loss. Moreover,  these losses are potentially unlimited.

If the price rises far above the strike price,  you are in a very exposed position. You may want to hedge or cover this risk. The obvious way to do so is to buy the stock,  which you will be obliged to deliver if the call is exercised. Taking a long position in the stock to hedge a written call is known as writing a covered call.

The payoff at maturity to writing a covered call is $\operatorname*{min}[S_{T},    X]$ . This is far less risky than the naked short position in the call itself,  as now the worst that can happen is that you sell the underlying at a price below its market value. Of course,  the hedged position is costly; it costs $S_{t}-c_{t}$,  whereas the naked position has a positive initial inflow of cash of $Ct$,  the price of the call option.

Likewise,  if you buy a put option,  there will be a loss if the price of the underlying rises equal to the cost of the put option,  $p_{t}$. The payoff at maturity will be $\max[0,    X-S_{T}]$. However,  you will have to buy the stock if you wish to exercise the right to sell at the strike price,  $X$. Thus,  you may wish to buy the stock in advance at the cost of $S_{t}$. In this case,  the payoff at maturity is $\max[S_{T},    X]$ and the initial cost is $S_{t}+p_{t}$. Going long in the put and the stock is known as a protective put strategy.

## A spread

There are many examples of spreads. Vertical spreads use options of the same maturity but different strike prices; horizontal spreads use options with the same strike prices but different maturities; and diagonal spreads use options with both different strike prices and maturities.

One popular type of vertical spread is the bull spread,  which is a position taken by an investor who thinks that the price of the underlying will rise.

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
			<td>0 overall</td>
			<td>0</td>
			<td>$S_{T}-X_{1}>0$</td>
			<td>$X_{2}-X_{1}>0$</td>
		</tr>
	</tbody>
</table>

Table 1: Bull Spread

A bull spread can be created by buying a call with a low strike price and writing a call with a higher strike price. Suppose that the written call has a strike price of $X_{2}$ and the long call has a strike price of $X_{1}<X_{2}$. The payoffs at maturity are given in Table 1. The value of the spread is $c^{1}-c^{2}$ where $c^{1}$ is the price of the call option with a strike price of $X_{1}$ and $c^{2}$ is the price of the call option with a strike price of $X_{2}$. Since the bull spread always yields a non-negative payoff at maturity (it is a limited liability asset),  it follows that $c^{1}>c^{2}$.

Another type of spread is a bear spread. A bear spread can be created by holding a put with a higher strike price and writing a put with a lower strike price. In this case,  the investor benefits if the market is falling. This is in contrast to a bull spread where the investor gains when the market rises.

Exercise: An investor buys a March put on Reed Elsevier with a strike price of 649 for a price of 55.5 and writes a March put on Reed Elsevier with a strike price of 609 for a price of 34. Calculate the payoff now and the possible payoffs in March when the puts expire. Draw a table and a diagram to illustrate the payoffs.

## A combination

A combination involves taking a position in both puts and calls on the same underlying asset. One particular combination is a strap. A strap consists of a long position in two calls and one put with the same strike price and expiration date.

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
			<td>0 overall</td>
			<td>$v_t$ -</td>
			<td>$X-S_T$</td>
			<td>0</td>
		</tr>
	</tbody>
</table>

expiration date. This position is appropriate if it is thought that there is likely to be a large change in the price of the underlying but the direction of change is unknown. However,  it is thought that an increase is more probable than a decrease. The payoff at maturity from the strap is $X-S_{T}$ if $S_{T}<X$ and $2(S_{T}-X)$ if $S_{T}>X$.

# 2 Put-Call Parity Condition (European)

Consider buying a call option with a strike price of $X$ and a maturity date of 7 and at the same time going short in a forward contract on the same underlying and with a delivery price of $X$.

The overall position of this portfolio is the same as a long position in an equivalent put option on the same underlying with the same strike price and maturity date. Thus,  the two portfolios must have equal values: $c_{t}-v_{t}= p_t$,  where $v_t$ is the value of the forward contract. From our previous knowledge of forward contracts,  we know that $v_t= S_t - (X/(1+r))$ . Therefore,

$$c_t+\frac{X}{(1+r)}=p_t+S_t$$

where 7 is shorthand for $r_t^{T}$. This condition is the put-call parity condition for European options. This equation is known as the put-call parity condition as it was first derived under the assumption that the options were at the money,  $S_t=X$,  and that the interest rate was 0.

It can be seen directly from this equation that the portfolio which is long in the stock and long in the put option is equivalent to a portfolio which is long in the call and long in a discount bond with a face value of $X$.

### Exercise: Check it out

Another way to see this is as follows. Consider simultaneously buying a call and writing a put. If $S_T>X$,  then exercise the call for a profit of $S_T - X$. If $X> S_T$ ,  then the put will be exercised,  resulting in a payoff of $X - S_T$ for the holder and a payoff of $S_T - X$ for the writer. Thus,  the portfolio of one call and one written put results in a payoff of $S_T - X$ in all circumstances. The value of this payoff can be evaluated using the stochastic discount factor $k$. The value of the portfolio at time $t$ is

$$c_t - p_t=E[k\cdot(S_T - X)]=E[k\cdot S_T] - XE[k]= S_t - \frac{X}{(1+r)}$$

since by definition,  the appropriately discounted value of the stock price at time $T$ is the stock price now,  $S_t$ ,  and $E[k]$ is the appropriate discount factor. Again,  we have the same put-call parity condition.

To labour the point once more,  remember that the payoff at maturity from writing a covered call is $\operatorname*{min}[S_{T},    X]$. Suppose that in addition,  you go short in a risk-free bond with a face value of $X$. The overall payoff at maturity is $\operatorname*{min}[S_{T}-X,    0]$ ,  the same as writing a put option. The value of this portfolio is $S_{t}-c_{t}-\frac{X}{(1+r)}$ ,  which must equal the value of writing the put option,  $-p_{t}$.

# 3 Arbitrage Bounds

We will now consider the payoff to the option prior to maturity. We will establish bounds for the option value prior to maturity.

The intrinsic value or parity value of an option at time $t$ is the payoff to the option if the current date were the maturity date. Thus,  the intrinsic

value of the call option at time $t$ is $\operatorname*{max}[0,    S_{t}-X]$ where $St$ is the current price of the underlying asset,  and the intrinsic value of a put option is $\max[X-S_{t},    0]$.

An American option will always trade at a price at or above its intrinsic value since,  with an American option,  it is always possible to exercise the option now and realise the intrinsic value. The difference between the price of an option and its intrinsic value is known as the premium or time value of the option. Thus,  the price of an option is the sum of its intrinsic value plus its premium

$$\text{price of option}=\text{intrinsic value}+\text{time value}.$$

If an option is initially set up at the money,  $S_{0}=X$,  then the intrinsic value of the option is 0,  and the premium and price are equivalent. This accounts for why the option price is sometimes referred to as the premium. We will use the term time value to avoid confusion.

A European call option also has a positive time value. That is,  the price of a European call option cannot be less than its intrinsic value. Remember that the payoff to the call option is $Max[S_{T}-X,    0]$ .The call can be valued using the stochastic discount factors $k$ .Thus the value of the call option at time $t$ is $c_{t}=E[k\cdot Max[S_{T}-X,    0]]$ . Clearly

$$c_t\ge E[k\cdot(S_T-X)]=E[k\cdot S_T]-XE[k]=S_t-\frac{X}{(1+r)}$$

where the first inequality comes from the definition of the maximum and the other equalities follow as $E[k\cdot S_{T}]=S_{t}$ 1,  the stochastically discounted value of the stock at maturity is its current value,  and the fact that $E[k]=\frac{1}{(1+r)}$ Equally since $S_{T}\geq0$ and $X\geq0$ ,  it follows that $Max[S_{T}-X,    0]\leq S_{T}$；so $c_{t}\leq E[k\cdot S_{T}]=S_{t}$ .Since the call cannot command a negative price we have for the arbitrage bounds for a call option

$$S_t\ge c_t\ge\max\left[S_t-\frac{X}{(1+r)},    0\right].$$

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
			<td>0 overall</td>
			<td>$S_t-$ $c_t$ </td>
			<td>$S_T$</td>
			<td>$X$</td>
		</tr>
	</tbody>
</table>

Since the strike price on the RHS is discounted we have $\frac{X}{(1+r)}<X$ ,  so that

$$c_t\ge\max\left[S_t-\frac{X}{(1+r)},    0\right]>\max[S_t-X,    0]$$

for $t<T$ and $r>0$ ,  so the European call has a value greater than its intrinsic value at any date prior to maturity.

To see how the inequalities in (2)can be derived without using the stochastic discount factor first,  let's consider the upper bound on the European call option. The value of the call cannot be greater than the value of the stock. This is obvious because the call option only gives you the right to buy the stock. If the call option cost more than the stock,  it would simply be cheaper to buy the stock now and have nothing further to pay. To see this more clearly,  consider writing a covered call,  that is,  buy the stock and write a call option. The payoff now is $c_{t}-S_{t}$ ,  which is positive if the call price is greater than the current stock price. At maturity,  either the call goes unexercised,  if $S_{T}<X$ ,  and we are left with the stock with a value of $S_{T}$ or the call is exercised,  in which case we give up the stock we own for the agreed strike price of $X$. Either way,  we end up with a positive payoff at maturity,  so the value of the portfolio must be positive: $S_{t}-c_{t}>0$ if $X>0$ or $S_{T}>0$. If $c_{t}>S_{t}$,  there is an arbitrage possibility formed by writing a covered call. The payoffs are summarised in Table 3.

To see the lower bound on the call option,  $c_{t}$ $\geq$ $S_{t}$ - $\frac{ X}{( 1+ r) }$. Recall that we have already shown that a long position in the call option with a strike price of $X$ combined with a short position in a forward contract on the same underlying asset.

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

Table : All Lower Bound: $c_{t}\geq S_{t}-\frac{X}{(1+r)}$

Underlying and with a delivery price of $X$ is equivalent to a long position in a put option with the same strike price. A short position in the forward contract with a delivery price of $X$ is itself equivalent to selling the stock short now and buying a risk-free bond with a face value of $X$. The payoffs are summarised in Table 4. The portfolio has a payoff of 0 if $X<S_{T}$; the bond pays out $X$,  and the call is exercised using the bond payoff to pay the strike price,  and the purchase of the stock closes out the short position. The portfolio has a payoff of $X - S_{T}$ if $S_{T}<X$ as the call option goes unexercised. Thus,  the portfolio replicates the put option and,  in particular,  never has a negative payoff. The value of the portfolio must therefore be positive by the no-arbitrage principle,  $c_{t}\geq S_{t} - \frac{X}{(1+r)}$.

An American option cannot be less valuable than the equivalent European option as the American option provides all the same rights as the European option and the opportunity to exercise early. Thus,  $C_{t}\geq c_{t}$ and $P_{t}\geq p_{t}$. However,  although it is possible to exercise an American call option on a non-dividend-paying stock prior to maturity,  it is never optimal to do so. This is because the European call option has a positive time value and thus its price is greater than its intrinsic value. Since $C_{t}\geq c_{t}>S_{t} - X$ for $t<T$,  it will always be better to sell the call option and get $C_{t}$ rather than exercise it and get $S_{t} - X$. Thus,  the option to exercise the American option early is redundant,  and the American and European options on non-dividend-paying assets are equivalent and hence must trade at the same price,  $C_{t}=c_{t}$.

The qualification that the underlying asset should be non-dividend-paying is important. It may be optimal to exercise an American option early if the underlying asset is a dividend-paying stock. Let $D_{t}$ denote the present value of dividends paid on the underlying during the remainder of the option’s life. Then the lower bound for the call option is $S_{t}-D_{t}-\frac{X}{(1+r)}$. If $D_{t}$ is large enough,  then this lower bound can be below the intrinsic value of $S_{t}-X$. In this case,  it may be optimal to exercise early. To take an extreme case,  suppose that the call is in the money but the firm on which the option is written is unexpectedly to be liquidated and all the asset value is to be paid out in dividends. Then after the dividend payment,  the stock is worthless and the call option can never be in the money. In this case,  it is best to exercise early and take the positive value of exercise now.

By analogy,  the arbitrage bounds for a European put option on a non-dividend-paying stock with a payoff of $Max[X-S_{T},    0]$ are

$$X\ge p_t\ge\max\left[\frac{X}{(1+r)}-S_t,    0\right].$$

Note that an American put option cannot be less than its intrinsic value,  so the arbitrage bounds for an American put option are

$$X\geq P_t\geq\max[X-S_t,    0].$$

For an American put option,  early exercise can be optimal even if the underlying asset pays no dividends. To take an extreme example,  suppose that $S_{t}=0$ but $X>0$. It is impossible to gain more by waiting since the stock price cannot fall further. In addition,  the gain to be had by waiting is discounted at the risk-free rate,  and if the interest rate is positive,  it is better to exercise now rather than wait. If exercise is ever optimal before maturity,  then $P_{t}=X-S_{t}$ since if $P_{t}>X-S_{t}$ it would be better to sell the option rather than exercise it.

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

There is a put-call parity condition for American options on non-dividend-paying stocks. The condition,  however,  is one of inequalities rather than equality and is given by:

$$S_t-\frac{X}{(1+r)}\geq C_t-P_t\geq S_t-X.$$

The first inequality follows from three facts. First,  the parity condition for European puts and calls (equation (1)) that $c_{t}-p_{t}$ = $S_{t}- ( X/ ( 1$ + $r) )$ Second,  the fact that American call options are not exercised early,  so $C_{t}=$ $Ct$ and third,  the fact that the American put cannot be worthless than the European put,  that is $P_{t}\geq p_{t}$ .Hence,  combining these three facts,  we get $c_{t}-p_{t}=S_{t}-(X/(1+r))\geq C_{t}-P_{t}$ .To see the second inequality,  consider the portfolio of a long call,  a short put,  shorting the stock,  and saving $X$ .The payoffs to this portfolio are summarised in Table 5. Since the portfolio yields a certain return of $rX$ at maturity,  the portfolio must have a positive value at date $t$ ,  and hence we can conclude that $C_{t}-P_{t}\geq S_{t}-X$

Note the bounds in equation (3) are quite tight and become tighter the smaller the interest rate is. 7. If the interest rate is zero ( $r=0$）then the inequalities in equation (3) become an equality

$$C_t-P_t=S_t-X.$$

If,  in addition,  the option is set up at date $t$ and the strike price is set so that the option is at-the-money (that is,  $X=S_{t}$ ) then we have exact parity between the put and call prices for American options too and $C_{t}=P_{t}$

# One Period Binomial Model

These notes consider the one-period binomial model to exactly price an option. We will consider three different methods of pricing an option: delta-hedging,  creating a synthetic option using the underlying asset and the risk-free asset,  and calculating the risk-neutral probabilities or stochastic discount factors. All methods will be used again when we extend the binomial model beyond one period and when we consider continuous trading

Keywords: Delta-hedging,  synthetic options,  replication,  risk-neutral probabilities,  risk-neutral valuation.

Reading: Start of chapter 11 from Hull.

### Binomial Model

To value options exactly,  it is necessary to make specific assumptions about the determinants of the price of the underlying security. In practice,  this often means that a continuous stochastic process for the underlying is estimated or inferred from observations on past prices. However,  the essential aspects can all be embodied in a simple binomial model in which the underlying asset can be one of two possible values at the end of each period; to put it starkly,  the asset can either go up or go down in value. By considering more than one period,  a binomial tree is constructed,  where the price that an asset has branches out,  either upward or downward at each point in time. These binomial trees can provide a remarkably good approximation to a more complex stochastic process provided that the number of periods is reasonably large,  say above thirty.

In fact,  nearly all the basic principles of derivative pricing can be explained with a oneor two-period binomial model,  and this section develops the one-period binomial model to study how options are exactly priced and the riskiness and elasticity of options.

## Delta Hedging

Buying a stock is a risky investment. Buying a call option on that stock is even riskier. Yet combining the stock with the option can produce an investment that is risk-free. That is,  it is possible to hedge a position in the stock by taking an opposite position in the call option. To create such a risk-free investment,  it is necessary to buy the stock and the option in exactly the right proportions. The number of units of the stock required per option is known as the $\Delta$ (Delta) of the stock,  and taking these positions to create a risk-free investment is known as Delta Hedging.

We will now illustrate how to calculate $\Delta$ in a simple binomial example. Once $\Delta$ is known,  the option price itself can be calculated as any risk-free investment must,  in the absence of arbitrage opportunities,  earn the risk-free rate of return.

Consider a simple example where the price of the underlying stock is 100 and at the end of three months it has either risen to 175 or has fallen to 75. There is an "up" state and a"down” state. Let $u=0.75$ and $d=-0.25$ ,  so that the value of the stock in three months in the up state is $100 (1+u)=175$ and the value in the down state is $100 (1+d)=75$. The net growth rate of the value of the stock in the up state is $75\%$ ,  and the net growth in the value of the stock in the down state is $-25\%$.

Since the stock can either rise by $75\%$ or fall by $25\%$,  buying the stock is a risky investment. Now consider an at-the-money call option on this stock with a strike price of 100. If the stock goes up,  then in three months the

Call can be exercised for a profit of 175-100=75 and if the price of the stock goes down,  then the call will not be exercised. Thus the payoff to the call option is 75 in the up state and 0 in the down state. So the call is also risky. Suppose,  however,  that we consider buying $\Delta$ units of the stock and writing one call. The payoff from this portfolio is $175\Delta-75$ in the up state: the stock has gone up to 175 but the call option we have written will be exercised against us so we have an obligation of 75. The payoff in the down state is simply $75\Delta$ as the call option is not exercised in the down state. To make this portfolio risk-free,  it is necessary to choose $\Delta$ such that

$$175\Delta-75=75\Delta $$

So that the payoff is the same no matter whether we are in the up state or the down state. Solving for $\Delta$ gives $\Delta=3/4$. Thus,  to completely hedge out the risk in the stock,  we should sell four call options for every three units of stock we buy. The payoff from such a portfolio is given in Table 1. The value in three months’ time is 225 in both states,  and hence the portfolio is risk-free. Since it is risk-free,  it can be valued using the risk-free rate of interest. Suppose the risk-free rate of interest is 1/4 or $25\%$. The present value of this portfolio is 225/(1+1/4)=180. The value of the portfolio now is simply the current value of the share,  $3\times 100=300$ less $4 c$,  where $C$ is the price of the call option. If there are no arbitrage possibilities,  then the value of this portfolio must also have a value of 3180:

$$300-4 c=180.$$

So solving for the call price gives $c=30$. This shows that the $\Delta$ -hedge can be used to price the option.

The same procedure can be generalized. Let S be the value of the underlying stock,  so its terminal value is $S_{u}=(1+u) S$ in the up state and $S_{d}=(1+d) S$ in the down state. Let $K$ be the strike price of the option and $c_{u}=\operatorname*{max}[0,    S_{u}-K]$ be the value of the call option in the up state and

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
			<td>0 overall</td>
			<td>$300-4 c$</td>
			<td>225</td>
			<td>225</td>
		</tr>
	</tbody>
</table>

Table 1: Risk-Free Portfolio - Example

$c_{d}=\operatorname*{max}[0,    S_{d}-K]$ is the value of the call option in the down state. Remember,  that the call option gives us the right to buy the underlying at a price of $K$,  so for example in the up state when the stock is worth $S_{u}$ the option gives the right to buy at $K$ and asset that can be sold for $S_{u}$ .Thus the option will be exercised for a profit of $S_{u}-K$ if $S_{u}-K>0$ and won't be exercised otherwise.

Now consider the $\Delta$ -hedge portfolio that writes one call and buys $\Delta$ units of the underlying. The payoffs from this portfolio are given in Table 2. The value of $\Delta$ is chosen so that the portfolio is riskless,  $\Delta S_{d}-c_{d}=\Delta S_{u}-c_{u}$ i.e.

$$\Delta=\frac{c_u-c_d}{S_u-S_d}=\frac{c_u-c_d}{(u-d) S}.$$

The value of the risk-free portfolio is evaluated at the risk-free rate of interest 7% ,  so that

$$\Delta S-c=\frac{\Delta S_d-c_d}{(1+r)}.$$

Using the value of $\Delta$ just derived,  and substituting $(1+d) S$ for $S_{d}$ and solving for $C$ gives after some manipulation

$$c=\frac{pc_u+(1-p) c_d}{(1+r)}$$

Where $p$ = $( rd) / ( ud)$ .Thus for any values of $S$，$K$，7，$UL$ and $d$ the value of the call option can be calculated from this formula.

There is a natural interpretation for $\Delta$. It is the difference in the value of the call at maturity $c_{u}-c_{d}$ in the up state rather than the down state.

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
			<td>$0_{\mathrm{overall}}$</td>
			<td>$\Delta S-c$</td>
			<td>$\Delta S_{d}-c_{d}$</td>
			<td>$\Delta S_{u}-c_{u}$</td>
		</tr>
	</tbody>
</table>

Table 2: Risk-Free Portfolio

Relative to the difference in the value of the stock $S_{u}-S_{d}$. It tells us the change in the value of the call relative to the change in the value of the stock or how much the value of the call changes when the stock changes by a given amount. Thus $\Delta$ tells us how responsive the call value is to changes in the value of the stock. We will return to this interpretation when we consider the elasticity of an option later on.

## Synthetic Options

The idea underlying $\Delta$ -Hedging is to create a risk-free asset using a combination of the stock and the option that can be valued at the risk-free rate of interest. The risk-free asset and the underlying asset can themselves be combined to replicate the payoffs of the option itself. Such a combination is called a synthetic option.

Consider again our simple example where the price of the underlying stock is 100 and at the end of three months it has either risen to 175 or has fallen to 75. Now consider how an at-the-money call option on this stock with a strike price of 100 can be synthesized. The payoff to the call option in the up state is 75 and the payoff in the down state is 0 as the option will not be exercised. Consider buying $\Delta$ units of the stock and investing $B$ units of funds at the risk-free interest rate of 1/4. The payoff from this portfolio in the up state is $175\Delta+(1+1/4) B$ and the payoff in the down state is $75\Delta+(1+1/4) B$. To synthesize the option,  we must match these payoffs to

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
			<td>0 overall</td>
			<td>30</td>
			<td>0</td>
			<td>75</td>
		</tr>
	</tbody>
</table>

Table 3: Synthetic Option

The payoffs from the option. That is,  we must find $\Delta$ and $B$ to solve

$$175\Delta+(1+1/4) B=75$$

$$75\Delta+(1+1/4) B=0.$$

Solving these two equations simultaneously gives $\Delta=3/4$ and $B$ = -45. Thus,  the option can be replicated by borrowing 45 and buying $\frac{3}{4}$ units of the stock. Since the stock costs 100,  the cost of buying 3/4 of a unit of stock is 75. Thus,  the net cost of synthesizing the option is the price we pay minus the amount borrowed,  75-45=30. Again,  the portfolio that replicates or synthesizes the call must have the same price as the call itself. Hence,  $c=30$ and we reach exactly the same conclusion as before. The payoffs are summarized in Table 3.

Again,  it is simple to generalize this procedure. To find the number of shares to be bought $\Delta$ and the amount to invest $B$ to synthesize the option,  it is only necessary to solve simultaneously the following two equations:

$$\begin{array}{c}\Delta S_u+(1+r) B=c_u\\\\\Delta S_d+(1+r) B=c_d.\end{array}$$

Solving these two equations gives

$$\Delta=\frac{c_u-c_d}{S_u-S_d}$$

and

$$B=\frac{1}{1+r}(c_d-\Delta S_d)=\frac{1}{1+r}\left (c_d-\frac{(1+d) S (c_u-c_d)}{(S_u-S_d)}\right).$$

This is illustrated graphically in Figure 1. The payoff at maturity to the call option is illustrated by the thick line. The two possible end values for the stock $S_{u}$ and $S_{d}$ are drawn on the horizontal axis. The strike price $K$ has been chosen between the two values $S_{u}$ and $S_{d}$ so that in the down state the call option expires valueless and $c_{u}=0$. The value of the call in the up state is $c_{u}=S_{u}-K$ and this is illustrated on the vertical axis. Also drawn is the line connecting the two points $(S_{d},    c_{d})$ and $(S_{u},    c_{u})$. The slope of this line is $\Delta$ and the intercept with the vertical axis is $-\Delta S_{d}=-(1+r) B$. It can be seen that the line is never downward sloping,  so $\Delta\geq 0$ and the slope is always less than $45^{o}$. So $\Delta\leq 1$. The intercept with the vertical axis is zero or negative indicating that the portfolio that synthesizes the call option involves borrowing (selling rather than buying the risk-free asset).

The cost of synthesizing the option is the cost of the portfolio of $\Delta$ units of the shares and investing $B$ in bonds.

$$c=\Delta S+B=\frac{pc_u+(1-p) c_d}{(1+r)}.$$

Where $p=(r-d)/(u-d)$ exactly as before.

### Risk Neutral Pricing

The previous two subsections have derived a simple expression for the price of the call option.

$$c=\frac{pc_u+(1-p) c_d}{(1+r)}.$$

In this expression,  the value of the call optionisthepresentvalue ofaweighted average of the call at maturity,  either $Cu$ in the up state or $Cd$ in the down state. It is tempting to interpret $P$ in this equation as a probability. It is

 ![500](./images/fHofODYmUoRXx8ufoFcmd4reB9x2D6irg.png)

Figure 1: THE $\Delta$ OF A CALL OPTION IN THE BINOMIAL MODEL

Important to notice two things about this formula. First,  $P$ cannot be the probability of an up movement in the stock as the probabilities of stock movements were not used in the calculation of the call value. Thus,  the value of the call is independent of the probabilities of the up or down movements in the stock price. Second,  the formula for the call is based on the present value of $pc_{u}+(1-p) c_{d}$ and is therefore valued as if this payoff was risk-free. Thus,  the probability $P$ is a risk-adjusted probability. It is simply the future value of the state price for the up-state.

To give an interpretation to $\not P$,  imagine a situation where all individuals were indifferent to risk. Such a situation is known as a risk-neutral world. In such a situation,  all individuals would agree to value any risky prospect

Simply by its expected present value. Since the formula for the value of the call is the expected present value when $p$ is interpreted as the probability of an upward movement in the stock,  $\rho$ is interpreted as a risk-neutral probability,  and this method of valuing the derivative is called risk-neutral valuation. It is a simple and general principle that can be used for valuing all derivative securities.

To see how it can be used,  let's revisit our simple example again. Using the method of risk-neutral valuation,  the expected value of the stock at the end of the period is $175 p+75 (1-p)$ ,  so the expected present value using the risk-neutral probabilities is

$$\frac{175 p+75 (1-p)}{(1+1/4)}.$$

This must equal the actual value of the stock,  which is 100. This gives one equation in one unknown,  $P$ ,  and solving gives $p=\frac{1}{2}$. To value the call,  we simply use risk-neutral valuation again. The call at maturity is worth 75 in the up state and 0 in the down state,  so the expected value using the risk-neutral probabilities is (1/2) 75,  and the present value of this expectation is (1/2) 75/(5/4)= 30.

Again,  generalising this method,  $P$ is solved from the equation

$$S=\frac{p (1+u) S+(1-p)(1+d) S}{(1+r)}$$

To give $p=(r-d)/(u-d)$ exactly as before,  and this value of $P$ can then be used to compute the risk-neutral valuation for the option.

## Summary

We've considered a one-period binomial model where the stock price can go either up or down by factors $(1+u)$ and $(1+d)$. We can then use information

On the current stock price $S$ ,  the risk-free interest rate 7,  and the strike price $K$ to determine the value of the option. We did this in three different ways. First,  by creating a riskless portfolio of the stock and the option. Second,  by creating a synthetic option that replicates the payoffs to the option using the underlying stock and the risk-free asset. In both cases,  we use an arbitrage argument that any two portfolios or assets that deliver the same payoffs must trade at the same price. Thirdly,  we derived the risk-neutral probability such that all assets and portfolios are valued by their expected present value. This then allows the option to be evaluated in the same way using these risk-adjusted probabilities.

The next thing to do is to allow for more than one period in the binomial model to see if the price of the option can still be calculated in a similar and similarly simple fashion.