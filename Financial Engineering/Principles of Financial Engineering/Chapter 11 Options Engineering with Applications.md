# OPTIONS ENGINEERING WITH 11 APPLICATIONS  

# CHAPTER OUTLINE  

1.1 Introduction . 352   
11.1.1 Payoff Diagrams .. 352   
11.1.1.1 Examples of xt . 354   
1.2 Option Strategies .... . 355   
11.2.1 Synthetic Long and Short Positions. 355   
11.2.1.1 An application .. 357   
11.2.1.2 Arbitrage opportunity?.. . 360   
11.2.2 A Remark on the Pin Risk . 361   
11.2.3 Risk Reversals. 361   
11.2.3.1 Uses of risk reversals.. . 363   
11.2.4 Yield Enhancement Strategies . 364   
11.2.4.1 Call overwriting . 365   
1.3 Volatility-Based Strategies....... . 367   
11.3.1 Strangles ... 369   
11.3.1.1 Uses of strangles. 369   
11.3.2 Straddle . 370   
11.3.2.1 Static or dynamic position? . 370   
11.3.3 Butterfly ... . 372   
1.4 Exotics .... .. 373   
11.4.1 Binary, or Digital, Options . 373   
11.4.1.1 A binary call .. . 374   
11.4.1.2 Replicating the binary call.. 374   
11.4.1.3 Delta and price of binaries .. . 376   
11.4.1.4 Time value of binaries. 377   
11.4.1.5 Uses of the binary . 377   
11.4.2 Barrier Options... 378   
11.4.2.1 A contractual equation.. 380   
11.4.2.2 Some uses of barrier options.. 383   
11.4.3 New Risks.. 384   
1.5 Quoting Conventions.. 384   
11.5.1 Example 1 .. 386   
11.5.2 Example 2 . 387  

11.6 Real-World Complications . 387   
11.6.1 The Role of the Volatility Smile.. 387   
11.6.2 Existence of Position Limits . 388   
1.7 Conclusions.. 388   
Suggested Reading . 388   
Exercises . 389   
EXCEL Exercises .. 391   
MATLAB Exercise . 391  

# 11.1 INTRODUCTION  

This chapter discusses traditional option strategies from the financial engineering perspective and provides market-based examples. It then moves on to discuss exotic options. We are concerned with portfolios and positions that are taken with a precise gain loss profile in mind. The players consciously take risks in the hope of benefiting or protecting themselves from an expected movement in a certain risk factor. Most investor behavior is of this kind. Investors buy a stock with a higher (systematic) risk, in anticipation of higher returns. A high-yield bond carries a higher default probability, which the bond holder is willing to bear. For all the different instruments, there are one or more risk factors that influence the gains and losses of the position taken. The investor weighs the risks due to potentially adverse movements in these factors against the gains that will result, if these factors behave in the way the investor expected. Some of the hedging activity can be interpreted in a similar way. This chapter deals with techniques and strategies that use options in doing this. We consider classical (vanilla) as well as exotic options tools.  

According to an important theorem in modern finance, if options of all strikes exist, carefully selected option portfolios can replicate any desired gain loss profile that an investor or a hedger desires. We can synthetically create any asset using a (static) portfolio of carefully selected options, since financial positions are taken with a payoff in mind. Hence, we start our discussion by looking at payoff diagrams.  

# 11.1.1 PAYOFF DIAGRAMS  

Let $x_{t}$ be a random variable representing the time- $\cdot t$ value of a risk factor, and let $f(x_{T})$ be a function that indicates the payoff of an arbitrary instrument at “maturity” date $T_{\cdot}$ , given the value of $x_{T}$ at time $T>t.$ . We call $f(x_{T})$ a payoff function. The functional form of $f\left(.\right)$ is known if the contract is well defined.2 It is customary in textbooks to represent the pair $\{f(x_{T}),x_{T}\}$ as in Figure 11.1 or 11.2. Note that, here, we have a nonlinear upward sloping payoff function that depends on the values assumed by $x_{T}$ only. The payoff diagram in Figure 11.1 is drawn in a completely arbitrary fashion, yet, it illustrates some of the general principles of financial exposures. Let us review these.  

![](f8945d12658657cf5d364d0fd8f4f837b6e44df5e505a86699a66036a64ef496.jpg)  

# FIGURE 11.1  

Payoff of nonlinear exposure.  

![](abe4f339a63db51f7b7b5d8ddd172d1decb31c1b42ab85dcf139e1ed5415c2f9.jpg)  

# FIGURE 11.2  

Payoff of a linear exposure.  

First of all, for fairly priced exposures that have zero value of initiation, net exposures to a risk factor, $x_{T}$ , must be negative for some values of the underlying risk. Otherwise, we would be making positive gains, and there would be no risk of losing money. This would be an arbitrage opportunity. Swap-type instruments fall into this category. If, on the other hand, the final payoffs of the contract are non-negative for all values of $x_{T}$ , the exposure has a positive value at initiation, and to take the position an upfront payment will have to be made. Option positions have this characteristic.3  

Second, exposures can be convex, concave, or linear with respect to $x_{T},$ , and this has relevance for an investor or market professional. The implication of linearity is obvious: the sensitivity of the position to movements in $x_{T}$ is constant. The relevance of convexity was discussed in Chapters 9 and 10. With convexity, movements in volatility need to be priced in, and again options are an important category here.  

Finally, it is preferable that the payoff functions $f(x_{T})$ depend only on the underlying risk, $x_{T},$ , and do not move due to extraneous risks. We saw in Chapters 9 and 10 that volatility positions taken with options may not satisfy this requirement. The issue will be discussed in Chapter 15.  

# 11.1.1.1 Examples of $\pmb{x_{\mathrm{f}}}$  

The discussion thus far dealt with an abstract underlying, $x_{t}.$ This underlying can be almost any risk the human mind can think of. The following lists some well-known examples of $x_{t}$ :  

Various interest rates: The best examples are LIBOR rates and swap rates. But the commercial paper (CP) rate, the federal funds rate, the index of overnight interest rates (an example of which is EONIA, Euro Over Night Index Average), and many others are also used as reference rates. Exchange rates, especially major exchange rates such as dollar euro, dollar yen, dollar sterling (“cable”), and dollar Swiss franc. Equity indices: Here also the examples are numerous. Besides the well-known US indices such as the Dow, NASDAQ, and the S&P500, there are European indices such as CAC40, DAX, and FTSE100, as well as various Asian indices such as the Nikkei 225 and emerging market indices. Commodities are also quite amenable to such positions. Futures on coffee, soybeans, and energy are other examples for $x_{T}.$ Bond price indices: One example is the EMBI $+$ prepared by JPMorgan to track emerging market bonds.  

Besides these well-known risks, there are more complicated underlyings that, nevertheless, are central elements in financial market activity:  

1. The underlying to the option positions discussed in this chapter can represent volatility or variance. If we let the percentage volatility of a price, at time $t$ , be denoted by $\sigma_{t},$ then the time $T$ value of the underlying $x_{T}$ may be defined as  

$$
x_{T}=\int_{t}^{T}\sigma_{u}^{2}S_{u}^{2}\mathrm{d}u
$$  

where $S_{u}$ may be any risk factor. In this case, $x_{T}$ represents the total variance of $S_{u}$ during the interval $[t,T]$ . Volatility is the square root of $x_{T}$ .  

2. The correlation between two risk factors can be traded in a similar way.  

3. The underlying, $x_{t}$ , can also represent the default probability associated with a counterparty or instrument. This arises in the case of credit instruments.  

4. The underlying can represent the probability of an extraordinary event happening. This would create a “Cat” instrument that can be used to buy insurance against various catastrophic events. 5. The underlying, $x_{t}$ , can also be a nonstorable item such as electricity, weather, or bandwidth.  

Readers who are interested in the details of such contracts or markets should consult Hull (2014). In this chapter, we limit our attention to the engineering aspects of option contracts.  

# 11.2 OPTION STRATEGIES  

We divide the engineering of option strategies into two broad categories. First, we consider the classical option-related methods. These will cover strategies used by market makers as well as retail investors. They will themselves be divided into two groups, those that can be labeled directional strategies, and those that relate to views on the volatility of some underlying instrument. The second category involves exotic options, which we consider as more efficient and sometimes cheaper alternatives to the classical option strategies. The underlying risks can be any of those mentioned in the previous section.  

# 11.2.1 SYNTHETIC LONG AND SHORT POSITIONS  

We begin with strategies that utilize options essentially as directional instruments, starting with the creation of long and short positions on an asset. Options can be used to create these positions synthetically.  

Consider two plain vanilla options written on a forward price $F_{t}$ of a certain asset. The first is a short put, and the second a long call, with prices $P(t)$ and $C(t)$ , respectively, as shown in Figure 11.3. The options have the same strike price $K$ , and the same expiration time $T.^{4}$ Assume that the Black Scholes conditions hold, and that both options are of European style. Importantly, the underlying asset does not have any payouts during $[t,T]$ . Also, suppose the appropriate short rate to discount future cash flows is constant at $r$ .  

Now consider the portfolio  

$$
\{1\mathrm{Long}K\mathrm{-Call},1\mathrm{Short}K\mathrm{-Put}\}
$$  

At expiration, the payoff from this portfolio will be the vertical sum of the graphs in Figure 11.3 and is as shown in Figure 11.4. This looks like the payoff function of a long forward contract entered into at $K$ . If the options were at-the-money (ATM) at time $t$ , the portfolio would exactly duplicate the long forward position and hence would be an exact synthetic. But there is a close connection between this portfolio and the forward contract, even when the options are not ATM.  

At expiration time $T.$ , the value of the portfolio is  

$$
C(T)-P(T)=F_{T}-K
$$  

![](506f9271cfd19afe788919e81c49da873bbdf50410491162ad9a790bd75aeae1.jpg)  

# FIGURE 11.3  

Payoff of a long call and a short put position.  

where $F_{T}$ is the time- $T$ value of the forward price. This equation is valid because at $T,$ only one of the two options can be in-the-money. Either the call option has a value of $F_{T}-K$ while the other is worthless, or the put is in-the-money and the call is worthless, as shown in Figure 11.3.  

Subtract the time- ${\bf\nabla}\cdot{\bf\nabla}t$ forward price, $F_{t}$ , from both sides of this equation to obtain  

$$
C(T)-P(T)+(K-F_{t})=F_{T}-F_{t}
$$  

This expression says that the sum of the payoffs of the long call and the short put plus $(K-F_{t})$ units of cash should equal the time- $T$ gain or loss on a forward contract entered into at $F_{t},$ at time $t$ . Take the expectation of Eq. (11.4). Then the time- ${\mathbf{\nabla}}\cdot t$ value of the portfolio,  

$$
\{1\mathrm{Long}K\mathrm{-Call},1\mathrm{Short}K\mathrm{-Put},e^{-r(T-t)}(K-F_{t})\mathrm{Dollars}\}
$$  

![](c4d824ed94ebe4a752f2b1c97cf026fce4b8b3f03c79d471102711946215bf9b.jpg)  

# FIGURE 11.4  

Joint payoff of a long call and short put.  

should be zero at $t$ , since credit risks and the cash flows generated by the forward and the replicating portfolio are the same. This implies that  

$$
C(t)-P(t)=e^{-r(T-t)}(F_{t}-K)
$$  

This relationship is called put-call parity. It holds for European options. It can be expressed in terms of the spot price, $S_{t},$ as well. Assuming zero storage costs, and no convenience yield:5  

$$
F_{t}=e^{r(T-t)}S_{t}
$$  

Substituting in the preceding equation gives  

$$
C(t)-P(t)=(S_{t}-e^{-r(T-t)}K)
$$  

Put-call parity can thus be regarded as another result of the application of contractual equations, where options and cash are used to create a synthetic for the $S_{t}$ . This situation is shown in Figure 11.5.  

# 11.2.1.1 An application  

Option market makers routinely use the put-call parity in exploiting windows of arbitrage opportunities. Using options, market makers construct synthetic futures positions and then trade them  

![](f61c7d6ab4476e27deeb8b5f816e8b69b6f0aec4d1eff8fbc72a524e79d0a05a.jpg)  

# FIGURE 11.5  

Put-call parity illustration and payoff of a synthetic stock position.  

against futures contracts. This way, small and temporary differences between the synthetic and the true contract are converted into “riskless” profits. In this section, we discuss an example.  

Suppose, without any loss of generality, that a stock is trading at  

$$
S_{t}=100
$$  

and that the market maker can buy and sell ATM options that expire in 30 days. Suppose also that the market maker faces a funding cost of $5\%$ . The stock never pays dividends and there are no corporate actions.  

Also, and this is the real-life part, the market maker faces a transaction cost of 20 cents per traded option and a transaction cost of 5 cents per traded stock. Finally, the market maker has calculated that to be able to continue operating, he or she needs a margin of 0.25 cent per position. Then, we can apply put-call parity and follow the conversion strategy displayed in Figure 11.6.  

Borrow necessary funds overnight for 30 days, and buy the stock at price $S_{t}$ . At the same time, sell the $S_{t}$ -call and buy the $S_{t}$ -put that expires in 30 days, to obtain the position shown in Figure 11.6.  

The position is fully hedged, as any potential gains due to movement in $S_{t}$ will cover the potential losses. This means that the only factors that matter are the transaction costs and any price differentials that may exist between the call and the put. The market maker will monitor the difference between the put and call premiums and take the arbitrage position shown in Figure 11.6 if this difference is bigger than the total cost of the conversion.  

![](cf62839c2bebfa0fdd0033be553a87272ef1d2c2ab09ec5291c4bca03b9184d7.jpg)  

Adding together...If prices are different enough" then there will be arbitrage opportunity.  

![](2fd870ffa25ebd2f617a9e69550088b95543d5653694d0a8d8488c3088e518ee.jpg)  

# FIGURE 11.6  

Put-call parity application and conversion strategy.  

# EXAMPLE  

Suppose $S_{t}=100$ , and 90-day call and put options trade actively. The interest cost is $5\%$ . A market maker has determined that the call premium, $C(t)$ , exceeds the put premium, $P(t)$ , by $\$2.10$ :  

$$
C(t)-P(t)=2.10
$$  

The stock will be purchased using borrowed funds for 90 days, and the ATM put is purchased and held until expiration, while the ATM call is sold. This implies a funding cost of  

$$
100(0.05){\binom{90}{360}}=\$1.25
$$  

Add all the costs of the conversion strategy:  

# Cost per Security \$  

<html><body><table><tr><td>Funding cost 1.25</td><td></td></tr><tr><td>Stock purchase 0.05</td><td></td></tr><tr><td>Put purchase 0.20</td><td></td></tr><tr><td>Call sale 0.20</td><td></td></tr><tr><td>Operating costs 0.25</td><td></td></tr><tr><td>Total cost 1.95</td><td></td></tr></table></body></html>  

The market maker incurs a total cost of $\$1.95$ . It turns out that under these conditions, the net cash position will be positive:  

$$
\mathrm{Net\profit}=2.10-1.95
$$  

and the position is worth taking.  

If, in the example just discussed, the put-call premium difference is negative, then the market maker can take the opposite position, which would be called a reversal.6  

# 11.2.1.2 Arbitrage opportunity?  

An outside observer may be surprised to hear that such “arbitrage” opportunities exist, and that they are closely monitored by market makers on the trading floor. Yet, such opportunities are available only to market makers on the “floor” and may not even constitute arbitrage in the usual sense.  

This is because of the following: (i) Off-floor investors pay much higher transaction costs than the on-floor market makers. Total costs of taking such a position may be prohibitive for off-floor investors. (ii) Off-floor investors cannot really make a simultaneous decision to buy (sell) the underlying, and buy or sell the implied puts or calls to construct the strategy. By the time these strategies are communicated to the floor, prices could move. (iii) Even if such opportunities are found, net gains are often too small to make it worthwhile to take such positions sporadically. It is, however, worthwhile to a market maker who specializes in these activities. (iv) Finally, there is also a serious risk associated with these positions, known as the pin risk. Pin risk refers to the situation when the market price of the underlying of an option contract at the time of the contract’s expiration is close to the option’s strike price. Traders pay attention to whether an underlying such as a stock, for example, may be close to pinning, since a small movement of the price of the underlying through the strike can have a large impact on a trader’s net position in the underlying on the trading day after expiration.  

# 11.2.2 A REMARK ON THE PIN RISK  

It is worthwhile to discuss the pin risk in more detail, since similar risks arise in hedging and trading some exotic options as well. Suppose we put together a conversion at 100, and waited 90 days until expiration to unwind the position. The positions will expire some 90 days later during a Friday. Suppose at expiration $S_{t}$ is exactly 100. This means that the stock closes exactly at the strike price. This leads to a dilemma for the market maker.  

The market maker owns a stock. If he or she does not exercise the long put and if the short call is not assigned (i.e., if he or she does not get to sell at $K$ exactly), then the market maker will have an open long position in the stock during the weekend. Prices may move by Monday and he or she may experience significant losses.  

If, on the other hand, the market maker does exercise the long put (i.e., he or she sells the stock at $\boldsymbol{K}$ and if the call is assigned (i.e., he or she needs to deliver a stock at $K_{\cdot}$ ), then the market maker will have a short stock position during the weekend. These risks may not be great for an end investor who takes such positions occasionally, but they may be substantial for a professional trader who depends on these positions. There is no easy way out of this dilemma. This type of risk is known as the pin risk.  

The main cause of the pin risk is the kink in the expiration payoff at $S_{T}=K.$ . A kink indicates a sudden change in the slope—for a long call, from zero to one or vice versa. This means that even with small movements in $S_{t},$ the hedge ratio can be either zero or one, and the market maker may be caught significantly off guard. If the slope of the payoff diagram changed smoothly, then the required hedge would also change smoothly. Thus, a risk similar to pin risk may arise whenever the delta of the instrument shows discrete jumps.  

# 11.2.3 RISK REVERSALS  

A more advanced version of the synthetic long and short futures positions is known as risk reversals. These are liquid synthetics especially in the foreign exchange markets, where they are traded as a commodity. Risk reversals are directional positions but differ in more than one way from synthetic long short futures positions discussed in the previous section.  

The idea is again to buy and sell calls and puts in order to replicate long and short futures positions—but this time using options with different strike prices. Figure 11.7 shows an example. The underlying is $S_{t}$ . The strategy involves a short put struck at $K_{1}$ , and a long call with strike $K_{2}$ . Both options are out-of-the-money initially, and the $S_{t}$ satisfies  

$$
K_{1}<S_{t}<K_{2}
$$  

![](b76febf566e9d95d6547032cb33b35a25264202206931cd10741253305e914b5.jpg)  

# FIGURE 11.7  

Payoff of a long call, short put, and a risk reversal position.  

Since strikes can be chosen such that the put and call have the same premium, the risk reversal can be constructed so as to have zero initial price.  

By adding vertically the option payoffs in the top portion of Figure 11.7, we obtain the expiration payoff shown at the bottom of the figure. If, at expiration, $S_{T}$ is between $K_{1}$ and $K_{2}$ , the strategy has zero payoff. If, at expiration, $S_{T}{<}K_{1}$ , the risk reversal loses money, but under $K_{2}<S_{T}$ , it  

makes money. Clearly, what we have here is similar to a long position but the position is neutral for small movements in the underlying starting from $S_{t}$ . If taken naked, such a position would imply a bullish view on $S_{t}$ .  

We consider an example from foreign exchange (FX) markets where risk reversals are traded as commodities.  

# EXAMPLE  

Twenty-five delta 1-month risk reversals showed a stronger bias in favor of euro calls (dollar puts) in the last 2 weeks after the euro started to strengthen against the greenback.  

Traders said market makers in EUR calls were buying risk reversals expecting further euro upside. The 1-month risk reversal jumped to 0.91 in favor of euro calls Wednesday from 0.3 3 weeks ago. Implied volatility spiked across the board. One-month volatility was $13.1\%$ Wednesday from $11.78\%$ 3 weeks ago as the euro appreciated to USD1.0215 from USD1.0181 in the spot market.  

The 25-delta risk reversals mentioned in this reading are shown in Figure 11.8. The risk reversal is constructed using two options, a call and a put. Both options are out-of-the-money and have a “current” delta of 0.25. According to the reading, the 25-delta EUR call is more expensive than the 25-delta EUR put.  

# 11.2.3.1 Uses of risk reversals  

Risk reversals can be used as “cheap” hedging instruments. Here is an example.  

# EXAMPLE  

A travel company in Paris last week entered a zero-cost risk reversal to hedge US dollar exposure to the USD. The company needs to buy dollars to pay suppliers in the United States, China, Indonesia, and South America.  

The head of treasury said it bought dollar calls and sold dollar puts in the transaction to hedge $30\%$ of its USD200 300 million dollar exposure versus the USD. The Americanstyle options can be exercised between November and May.  

The company entered a risk reversal rather than buying a dollar call outright because it was cheaper. The head of treasury said the rest of its exposure is hedged using different strategies, such as buying options outright. (Based on an article in Derivatives Week (now part of GlobalCapital).)  

Here we have a corporation that has EUR receivables from tourists going abroad but needs to make payments to foreigners in dollars. Euros are received at time $t$ , and dollars will be paid at some future date $T,$ with $t<T$ . The risk reversal is put together as a zero-cost structure, which means that the premium collected from selling the put (on the USD) is equal to the call premium on the USD. For small movements in the exchange rate, the position is neutral, but for large movements it represents a hedge similar to a futures contract.  

![](fc7f14f57cc136a376431000bdcacb63dadf033a946a2bf92e28b3dbe5cd47e7.jpg)  

# FIGURE 11.8  

Payoff of a long put, short call a risk reversal position.  

Of course, such a position could also be taken in the futures market. But one important advantage of the risk reversal is that it is “composed” of options, and hence involves, in general, no daily mark-to-market adjustments.  

# 11.2.4 YIELD ENHANCEMENT STRATEGIES  

The class of option strategies that we have studied thus far is intended for creating synthetic short and long futures positions. In this section, we consider option synthetics that are said to lead to yield enhancement for investment portfolios.  

![](15c822a9d3da99f73b7c280e0fb6b5f1cefb5ddc27228d7311d92784a5316085.jpg)  

# FIGURE 11.9  

Payoff of call overwriting strategy components.  

# 11.2.4.1 Call overwriting  

The simplest case is the following. At time $t$ , an investor takes a long position in a stock with current price $S_{t}.$ , as shown in Figure 11.9. If the stock price increases, the investor gains; if the price declines, he or she loses. The investor has, however, a subjective expected return, $\bar{R}_{t}$ , for an interval of time $\Delta$ , that can be expressed as  

$$
\hat{R}_{t}=E_{t}^{\hat{P}}\left[\frac{S_{t+\Delta}-S_{t}}{S_{t}}\right]
$$  

where $\hat{P}$ is a subjective conditional probability distribution for the random variable $S_{\mathrm{t+}\Delta}$ . According to the formula, the investor is expecting a gain of $\hat{R_{t}}$ during period $\Delta$ . The question is whether we can provide a yield-enhancing alternative to this investor. The answer depends on what we mean by “yield enhancement.”  

![](66e3101694f82acc3f219531a406993861fef34c2b0facd52b662692eac52b16.jpg)  

# FIGURE 11.10  

Payoff of call overwriting strategy.  

Suppose we ask the investor the following question: “What is the maximum gain you would like to make on this stock position?” and the investor indicates $S^{\mathrm{max}}$ as the price he or she is willing to sell the stock and realize the “maximum” desired gain:  

$$
(S^{\mathrm{max}}-S_{t})
$$  

Next, consider a call option $C(t)^{\mathrm{max}}$ that has the strike  

$$
K=S^{\mathrm{max}}
$$  

and that expires at $T=t+\Delta$ . This option sells for $C(t)^{\mathrm{max}}$ at time $t$ . We can then recommend the following portfolio to this investor:  

$$
\mathrm{Yield\enhanced\portfolio}=\{\mathrm{Long}S_{t},\mathrm{Short}C(t)^{\mathrm{max}}\}
$$  

Assuming zero interest rates, at time $T=t+\Delta$ , this portfolio has the following value, $V_{t+\Delta}$ :  

$$
V_{t+\Delta}={\left\{\begin{array}{l l}{C(t)^{\operatorname*{max}}+S_{t+\Delta}}&{{\mathrm{Option~not~exercised}}}\\ {C(t)^{\operatorname*{max}}+S_{t+\Delta}(S_{t+\Delta}-S^{\operatorname*{max}})=C(t)^{\operatorname*{max}}+S^{\operatorname*{max}}}&{{\mathrm{Option~exercised}}}\end{array}\right.}
$$  

According to this, if at expiration, the price stays below the level $S^{\mathrm{max}}$ , the investor “makes” an extra $C(t)^{\mathrm{max}}$ dollars. If $S_{t+\Delta}$ exceeds the $S^{\mathrm{max}}$ , the option will be exercised, and the gains will be truncated at $S^{\mathrm{max}}+C(t)^{\mathrm{max}}$ . But, this amount is higher than the price at which this investor was willing to sell the stock according to his or her subjective preferences. As a result, the option position has enhanced the “yield” of the original investment. However, it is important to realize that what is being enhanced is not the objective risk-return characteristics, but instead, the subjective expected returns of the investor.  

Figure 11.9 shows the situation graphically. The top portion is the long position in the stock. The bottom profile is the payoff of the short call, written at strike $S^{\mathrm{max}}$ . If $S_{t+\Delta}$ exceeds this strike, the option will be in-the-money and the investor will have to surrender his or her stock, worth $S_{t+\Delta}$ dollars, at a price of $S^{\mathrm{max}}$ dollars. But, the investor was willing to sell at $S^{\mathrm{max}}$ anyway. The sum of the two positions is illustrated in the final payoff diagram in Figure 11.10.  

This strategy is called call overwriting and is frequently used by some investors. The following reading illustrates one example. Fund managers who face a stagnant market use call overwriting to enhance yields.  

# EXAMPLE  

Fund manager motivation for putting on options strategies ahead of the Russell indices annual rebalance   
next month is shifting, say some options strategists. “The market has had no direction since May last year,” said a head of equity derivatives strategy in   
New York. Small cap stocks have only moved up slightly during the year, he added. Fund managers are proving increasingly willing to test call overwriting strategies for the rebalance as   
they seek absolute returns, with greater competition from hedge funds pushing traditional fund managers in   
this direction, [a] head of equity derivatives strategy said. Employing call overwriting strategies—even   
though they suppress volatility levels—looks attractive, because the worst outcome is that they outperform   
the stock on the downside. As such, it can help managers enhance their returns.  

(Thomson Reuters IFR, Issue 1433, May 11, 2002)  

The situation described in this reading is slightly more complicated and would not lend itself to the simple call overwriting position discussed earlier. The reading illustrates the periodic and routine rebalancing that needs to be performed by fund managers. Many funds “track” well-known indices. But, these indices are periodically revised. New names enter, others leave, at known dates. A fund manager who is trying to track a particular index, has to rebalance his or her portfolio as indices are revised.  

# 11.3 VOLATILITY-BASED STRATEGIES  

The first set of strategies dealt with directional uses of options. Option portfolios combined with the underlying were used to take a view on the direction of the underlying risk. Now we start looking at the use of options from the point of view of volatility positioning. The strategy used in putting together volatility positions in this section is the following: First, we develop a static position that eliminates exposure to market direction. This can be done using straddles and their cheaper version, strangles. Second, we combine strangle and straddle portfolios to get more complicated volatility positions, and to reduce costs.  

Thus, the basic building blocks of volatility positions considered in this section are straddles and strangles. The following example indicates how an option position is used to take a view on volatility, rather than the price of the underlying.  

# EXAMPLE  

An Italian bank recommended the following position to a client. We will analyze what this means for the client’s expectations [views] on the markets. First we read the episode.  

A bank last week sold $4\%$ out-of-the-money puts and calls on ABC stock, to generate a premium on behalf of an institutional investor. The strangle had a tenor of six weeks. . .. The strategy generated $2.5\%$ of the equity’s spot level in premium.  

At the time of the trade, the stock traded at roughly USD1874.6. Volatilities were at $22\%$ when the options were sold. ABC was the underlying, because the investor does not believe the stock will move much over the coming weeks and thus is unlikely to break the range and trigger the options.  

(Based on an article in Derivatives Week (now part of GlobalCapital))  

![](7f5b568bdbbe0530578aaea5348806b94bef5337a8a776df88d48eebabd7f97d.jpg)  

# FIGURE 11.11  

Payoff of a strangle position related to ABC stock.  

Figure 11.11 shows the payoff diagram of these option positions at expiration. Adding the premiums received at the initial point we get the second diagram in the bottom part of the figure. This should not be confused with the anticipated payoff of the client. Note that the eventual objective of the client is to benefit from volatility realizations. The option position is only a vehicle for doing this.  

We can discuss this in more detail. The second part of Figure 11.11 shows that at expiration, the down and up breakeven points for the position are 1762 and 1987, respectively. These are obtained by subtracting and adding the $\$37.5$ received from the strangle position, to the respective strike prices.  

But the reading also gives the implied volatility in the market. From here we can use the square root formula and calculate the implied volatility for the period under consideration  

$$
\sigma S_{t}\cdot\Delta=0.22\sqrt{\frac{6}{52}}1874.6=140.09
$$  

Note that the breakeven points are set according to $4\%$ movements toward either side, whereas the square root formula gives $7.5\%$ expected movements to either side.  

According to this, the client who takes this position expects the realized volatility to be significantly less than the $7.5\%$ quoted by the market. In fact, the client expects volatility to be somewhat less than $4\%$ .  

![](546d9b70a91cd1211859a408e250d2bea11c80c008044f3d6e4097f328281ddc.jpg)  

# FIGURE 11.12  

Typical short strangle’s expiration payoff.  

This brings us to a formal discussion of strangles and straddles, which form the main building blocks for classical volatility positions.  

# 11.3.1 STRANGLES  

Assume that we sell (buy) two plain vanilla, European-style options with different strikes on the asset $S_{t}.$ . The first is a put, and has strike $K_{\mathrm{p}}$ ; the second is a call, and has strike $K_{\mathrm{c}}$ , with $K_{\mathrm{p}}{<}K_{\mathrm{c}}$ . Suppose at the time of purchase, we have $K_{\mathrm{p}}<S_{t_{0}}<K_{\mathrm{c}}$ . The expiration date is $T.$ . This position discussed in the previous example is known as a strangle. Because these options are sold, the seller collects a premium, at time $t$ , of  

$$
C(t)+P(t)
$$  

The position makes money if, by expiration, $S_{t}$ has moved by a “moderate” amount, otherwise the position loses money. Clearly, this way of looking at a strangle suggests that the position is static. A typical short strangle’s expiration payoff is shown in Figure 11.12. The same figure indicates the value of the position at time $t$ , when it was initially put in place.  

# 11.3.1.1 Uses of strangles  

The following is an example of the use of strangles from foreign exchange markets. First there is a switch in terminology: Instead of talking about options that are out-of-the-money by $k\%$ of the strike, the episode uses the terminology “10-delta options.” This is the case because, as mentioned earlier, FX markets like to trade 10-delta, 25-delta options, and these will be more liquid than, say, an arbitrarily selected $k\%$ out-of-the-money option.  

# EXAMPLE  

A bank is recommending its clients to sell 1-month 10-delta euro/dollar strangles to take advantage of low holiday volatility. The strategists said the investors should sell $I$ -month strangles with puts struck at USD1.3510 and calls struck at USD1.3610. This will generate a premium of $0.3875\%$ of the notional size. Spot was trading at USD1.3562 when the trade was designed last week. The bank thinks this is a good time to put the trade on because implied volatility traditionally falls over Christmas and New Years, which means spot is likely to stay in this range.  

(Based on Derivatives Week (now part of GlobalCapital))  

This is a straightforward use of strangles. According to the strategist, the premium associated with the FX options implies a volatility that is higher than the expected future realized volatility during the holiday season due to seasonal factors. If so, the euro/dollar exchange rate is likely to be range-bound, and the options used to create the strangle will expire unexercised.7  

# 11.3.2 STRADDLE  

A straddle is similar to a strangle, except that the strike prices, $K_{\mathrm{p}}$ and $K_{\mathrm{c}}$ , of the constituent call and put options sold (bought), are identical:  

$$
K_{\mathrm{p}}=K_{\mathrm{c}}
$$  

Let the underlying asset be $S_{t},$ and the expiration time be $T$ . The expiration payoff and time value of a long straddle are shown in Figure 11.13. The basic configuration is similar to a long strangle. One difference is that a straddle will cost more. At the time of purchase, an ATM straddle is more convex than an ATM strangle, and hence has “maximum” gamma.  

# 11.3.2.1 Static or dynamic position?  

It is worthwhile to emphasize that the strangle or straddle positions discussed here are static, in the sense that, once the positions are taken, they are not delta-hedged. However, it is possible to convert them into dynamic strategies. To do this, we would delta-hedge the position dynamically. At initiation, an ATM straddle is automatically market-neutral, and the associated delta is zero. When the price moves up, or down, the delta becomes positive, or negative. Thus, to maintain a marketneutral position, the hedge needs to be adjusted periodically.  

Note a major difference between the static and dynamic approaches. Suppose we take a static straddle position, and $S_{t}$ fluctuates by small amounts very frequently and never leaves the region $[S_{1},S_{2}]$ shown in Figure 11.14. Then, the static position will lose money, while the dynamic deltahedged position may make money, depending on the size and frequency of oscillations in $S_{t}.$ .  

![](871a8bc4301fa6b8fdce4f2cfe318aebb7e1acaf42834c55300bb941bfcd7523.jpg)  

# FIGURE 11.13  

Expiration payoff and time value of a long straddle.  

![](b7915e65b498db835a509d4494594bf02962f936a4aa9a774b233871b68e75d5.jpg)  

# FIGURE 11.14  

Payoff and net profit from straddle position.  

# 11.3.3 BUTTERFLY  

A butterfly is a position that is built using combinations of strangles and straddles. Following the same idea used throughout the book, once we develop strangle and straddle payoffs as building blocks, we can then combine them to generate further synthetic payoffs. A long butterfly position is shown in Figure 11.15. The figure implies the following contractual equation:  

This equation immediately suggests one objective behind butterflies. By selling the strangle, the trader is, in fact, lowering the cost of buying the straddle. In the case of the short butterfly, the situation is reversed:  

Short butterfly $\b=$ Short ATM straddle $^+$ Long $k\%$ out-of-the-money strangle  

![](0a6d1f0c718943beed23bc33921ef7182a3e6314de9eefaf79247c3c3ce1f540.jpg)  

# FIGURE 11.15  

Long butterfly position.  

A short straddle generates premiums but has an unlimited downside. This may not be acceptable to a risk manager. Hence, the trader buys a strangle to limit these potential losses. But this type of insurance involves costs and the net cash receipts become smaller. The following shows a practical use of the short butterfly strategy.  

# EXAMPLE  

As the Australian dollar continues to strengthen on the back of surging commodity prices, dealers are looking to take advantage of an anticipated lull in the currency’s bull run by putting in place butterfly structures. One structure is a 3-month butterfly trade. The dealer sells an ATM Aussie dollar call and put against the US dollar, while buying an Aussie call struck at $A U D0.682$ and buying puts struck at AUD0.6375. The structure can be put in place for a premium of $0.3\%$ of notional, noted one trader, adding that there is value in both the puts and the calls.  

(Based on an article in Derivatives Week (now part of GlobalCapital))  

This structure can also be put in place by making sure that the exposure is vega-neutral.  

# 11.4 EXOTICS  

Up to this point, the chapter has dealt with option strategies that used only plain vanilla calls and puts. The more complicated volatility building blocks, namely straddles and strangles, were generated by putting together plain vanilla options with different strike prices or expiration. But the use of plain vanilla options to take a view on the direction of markets or to trade volatility may be considered by some as “outdated.” There are now more practical ways of accomplishing similar objectives.  

The general principle is this. Instead of combining plain vanilla options to create desired payoff diagrams, lower costs, and reach other objectives, a trader would directly design new option contracts that can do similar things in a “better” fashion. Of course, these new contracts imply a hedge that is, in general, made of the underlying plain vanilla options, but the new instruments themselves would sell as exotic options.8 Before closing this chapter, we would like to introduce further option strategies that use exotic options as building blocks. We will look at a limited number of exotics, although there are many others that we relegate to the exercises at the end of the chapter.  

# 11.4.1 BINARY, OR DIGITAL, OPTIONS  

To understand binary options, first remember the static strangle and straddle strategies. The idea was to take a long (short) volatility position, and benefit if the underlying moved more (less) than what the implied volatility suggested. Binary options form essential building blocks for similar volatility strategies, which can be implemented in a cheaper and perhaps more efficient way. Also, binary options are excellent examples of option engineering. We begin with a brief description of a European-style binary option.  

![](26c51f1c6398db60e089472ef9307acd7d917648befaaee549d75132128d2b7f.jpg)  

# FIGURE 11.16  

Intrinsic value of a binary call.  

# 11.4.1.1 A binary call  

Consider a European call option with strike $K$ and expiration time $T.\ S_{t}$ denotes the underlying risk. This is a standard call, except that if the option expires at or in-the-money, the payoff will be either (i) a constant cash amount or (ii) a particular asset. In this section, we consider binaries with cash payoffs only.  

Figure 11.16 shows the payoff structure of this call whose time- $\cdot t$ price is denoted by $C^{\mathrm{{bin}}}\left(t\right)$ The time- $T$ payoff can be written as  

$$
C^{\mathrm{bin}}(T)={\left\{\begin{array}{l l}{R}&{{\mathrm{If~}}K\leq S_{T}}\\ {0}&{{\mathrm{Otherwise}}}\end{array}\right.}
$$  

According to this, the binary call holder receives the cash payment $R$ as long as $S_{T}$ is not less than $K$ at time $T.$ . Thus, the payoff has an $R$ -or-nothing binary structure. Binary puts are defined in a similar way.  

The diagram in Figure 11.16 shows the intrinsic value of the binary where $R=1$ . What would the time value of the binary option look like? It is, in fact, easy to obtain a closed-form formula that will price binary options. Yet, we prefer to answer this question using financial engineering. More precisely, we first create a synthetic for the binary option. The value of the synthetic should then equal the value of the binary.  

The logic in forming the synthetic is the same as before. We have to duplicate the final payoffs of the binary using other (possibly liquid) instruments, and make sure that the implied cash flows and the underlying credit risks are the same.  

# 11.4.1.2 Replicating the binary call  

Expiration payoff of the binary is displayed by the step function shown in Figure 11.16. Now, make two additional assumptions. First, assume that the underlying $S_{t}$ is the price of a futures contract traded at an exchange, and that the exchange has imposed a minimum tick rule such that, given $S_{t}.$ , the next instant’s price, $S_{t+\Delta}$ , can only equal  

$$
S_{t+\Delta}=S_{t}+i h
$$  

![](1b9654af1b05e7995658053d607a1a5f5f7940fe3e5e2a54f2e75cda5d4fa481.jpg)  

# FIGURE 11.17  

Expiration payoff of a binary call.  

where $i$ is an integer, and $h$ is the minimum tick chosen by the exchange. Second, we assume without any loss of generality that  

$$
R=1
$$  

Under these conditions, the payoff of the binary is a step function that shows a jump of size 1 at $S_{T}{=}K$ .  

It is fairly easy to find a replicating portfolio for the binary option under these conditions. Suppose the market maker buys one vanilla European call with strike $K$ , and, at the same time, sells one vanilla European call with strike $K+h$ on the $S_{t}$ . Figure 11.17 shows the time- $T$ payoff of this portfolio. The payoff is similar to the step function in Figure 11.16, except that the height is $h$ , and not 1. But this is easy to fix. Instead of buying and selling 1 unit of each call, the market maker can buy and sell $\frac{1}{h}$ units. This implies the approximate contractual equation  

![](c16a0be822b3648941fc3f398147947d70f6dbc718398b4f6c5e7aa3e1845bad.jpg)  

The existence of a minimum tick makes this approximation a true equality, since  

$$
|S_{t}-S_{t+\Delta}<h|
$$  

cannot occur due to minimum tick requirements. We can use this contractual equation and get two interesting results.  

# 11.4.1.3 Delta and price of binaries  

There is an interesting analogy between binary options and the delta of the constituent plain vanilla counterparts. Let the price of the vanilla $K$ and $K+h$ calls be denoted by $C^{K}(t)$ and $\boldsymbol{C}^{K+h}(t)$ , respectively. Then, assuming that the volatility parameter $\sigma$ does not depend on $K.$ , we can let $h\to0$ in the previous contractual equation, and obtain the exact price of the binary, $C^{\mathrm{{bin}}}(t)$ , as  

$$
\begin{array}{l}{{\displaystyle C^{\mathrm{bin}}(t)=\operatorname*{lim}_{h\rightarrow0}\frac{C^{K}(t)-C^{K+h}(t)}{h}}}\\ {{\displaystyle~=\frac{\partial C^{K}(t)}{\partial K}}}\end{array}
$$  

assuming that the limit exists.  

That is to say, at the limit the price of the binary is, in fact, the partial derivative of a vanilla call with respect to the strike price $K.$ If all Black Scholes assumptions hold, we can take this partial derivative analytically, and obtain9  

$$
C^{\mathsf{b i n}}(t)={\frac{\hat{\sigma}C^{K}(t)}{\hat{\sigma}K}}=e^{-r(T-t)}N(d_{2})
$$  

where $d_{2}$ is, as usual,  

$$
d_{2}=\frac{\mathrm{Log}(S_{t}/K)+r(T-t)-\frac{1}{2}\sigma^{2}(T-t)}{\sigma\sqrt{(T-t)}}
$$  

$\sigma$ being the constant percentage volatility of $S_{t},$ and, $r$ being the constant risk-free spot rate.  

This last result shows an interesting similarity between binary option prices and vanilla option deltas. In Chapter 9 we showed that a vanilla call’s delta is given by  

$$
\mathrm{Delta}=\frac{\partial C^{K}(t)}{\partial S_{t}}=N(d_{1})
$$  

Here we see that the price of the binary has a similar form. Also, it has a shape similar to that of a probability distribution:  

$$
C^{\mathrm{bin}}(t)=e^{-r(T-t)}N(d_{2})=e^{-r(T-t)}\int_{-\infty}^{\log(S_{t}/K)+r(T-t)-\frac12\sigma^{2}(T-t)}\frac{1}{\sqrt{2\pi}}e^{-\frac12u^{2}\displaystyle\mathrm{d}u}
$$  

This permits us to draw a graph of the binary price, $C^{\mathrm{{bin}}}(t)$ . Under the Black Scholes assumptions, it is clear that this price will be as indicated by the S-shaped curve in Figure 11.16.  

![](dd2ca36f624d414ae6353f91c48d959ceb702f299cbfc0217949c46fa9ca0495.jpg)  

# FIGURE 11.18  

Gamma of a binary as a function of underlying.  

# 11.4.1.4 Time value of binaries  

We can use the previous result to obtain convexity characteristics of the binary option shown in Figure 11.16. The deep out-of-the-money binary10 will have a positive price close to zero. This price will increase and will be around $\frac{1}{2}$ when the option becomes ATM. On the other hand, an in-the-money binary will have a price less than one, but approaching it as $S_{t}$ gets larger and larger. This means that the time value of a European in-the-money binary is negative for $K<$ barrier. The $C^{\mathrm{{bin}}}(t)$ will never exceed 1 (or $R$ ), since a trader would never pay more than $\$1$ in order to get a chance of earning $\$1$ at $T.$  

From this figure, we see that a market maker who buys the binary call will be long volatility if the binary is out-of-the-money, but will be short volatility, if the binary option is in-the-money. This is because, in the case of an in-the-money option, the curvature of the $\mathbf{\bar{\mathbf{\Lambda}}}(C^{K+h}(t)$ will dominate the curvature of the $C^{K}(t)$ , and the binary will have a concave pricing function. The reverse is true if the binary is out-of-the-money. An ATM binary will be neutral toward volatility.  

To summarize, we see that the price of a binary is similar to the delta of a vanilla option. This implies that the delta of the binary looks like the gamma of a vanilla option. This logic tells us that the gamma of a binary looks like that in Figure 11.18, and is similar to the third partial with respect to $S_{t}$ of the vanilla option.  

# 11.4.1.5 Uses of the binary  

A range option is constructed using binary puts and calls with the same payoff. This option has a payoff depending on whether the $S_{t}$ remains within the range $[H^{\operatorname*{min}},H^{\operatorname*{max}}]$ or not. Thus, consider the portfolio  

$$
\mathrm{Range\option}=\{\mathrm{Long\}H^{\mathrm{min}}-\mathrm{Binary\call,Short\}H^{\mathrm{max}}-\mathrm{Binary\call\}}
$$  

The time- $T$ payoff of this range option is shown in Figure 11.19. It is clear that we can use binary options to generate other, more complicated, range structures.  

![](b8689b6dd5851c01870f35c65bb9670e851f7dfd118aafa36f2773c6393a2c04.jpg)  

# FIGURE 11.19  

Payoff of a range option.  

The expiration payoff denoted by $C^{\mathrm{range}}(T)$ of such a structure will be given by  

$$
C^{\mathrm{range}}(T)=\left\{{\begin{array}{l l}{R}&{{\mathrm{if}}\quad H^{\mathrm{min}}<S_{u}<H^{\mathrm{max}}\quad u\in[t,T]}\\ {0}&{{\mathrm{Otherwise}}}\end{array}}\right.
$$  

Thus, in this case, the option pays a constant amount $R$ if $S_{u}$ is range-bound during the whole life of the option, otherwise the option pays nothing. The following example illustrates the use of such binaries.  

![](a4e84445dea78af7807045f0424ecd1fc64cae36ef2899f2b845577e0644c0b1.jpg)  

Figure 11.19 illustrates the long binary options mentioned in the example. Looked at from the angle of yen, the binary options have similarities to selling dollar strangles.11  

# 11.4.2 BARRIER OPTIONS  

To create a barrier option, we basically take a vanilla counterpart and then add some properly selected thresholds. If, during the life of the option, these thresholds are exceeded by the underlying, the option payoff will exhibit a discrete change. The option may be knocked out, or it may be knocked in, meaning that the option holder either loses the right to exercise or gains it.  

Let us consider the two most common cases. We start with a European-style plain vanilla option written on the underlying, $S_{t},$ with strike $K.$ , and expiration T. Next, we consider two thresholds  

![](8c1b4c374097456d2bf42ce5155ad262b85dc3ba97e41fb5b716250dee3e4d4b.jpg)  

# FIGURE 11.20  

Payoff examples of a knock-out put and a knock-out call.  

$\boldsymbol{H}^{\mathrm{min}}$ and $H^{\mathrm{max}}$ , with $H^{\mathrm{min}}<H^{\mathrm{max}}$ . If, during the life of the option, $S_{t}$ exceeds one or both of these limits in some precise ways to be defined, then the option ceases to exist. Such instruments are called knock-out options. Two examples are shown in Figure 11.20. The lower part of the diagram is a knock-out call. If, during the life of the option, we observe the event  

$$
S_{u}<H^{\operatorname*{min}}\quad u\in[t,T]
$$  

then the option ceases to exist. In fact, this option is down-and-out. The upper part of the figure displays an up-and-out put, which ceases to exist if the event  

$$
H^{\operatorname*{max}}<S_{u}\quad u\in[t,T]
$$  

is observed.  

An option can also come into existence after some barrier is hit. We then call it a knock-in option. A knock-in put is shown in Figure 11.21. In this section, we will discuss an $H$ knock-out  

![](017c62630346b51c835078902c6bc629b461613f5229da4bba5648f9045c16aa.jpg)  

# FIGURE 11.21  

Payoff of a knock-in put.  

call and an $H$ knock-in call with the same strike $K$ . These barrier options we show here have the characteristic that when they knock-in or -out, they will be out-of-the-money. Barrier options with positive intrinsic value at knock-in and -out also exist but are not dealt with (for these, see James (2003)).  

# 11.4.2.1 A contractual equation  

We can obtain a contractual equation for barrier options and the corresponding vanilla options. Consider two European-style barrier options with the same strike $K.$ . The underlying risk is $S_{t},$ and, for simplicity, suppose all Black Scholes assumptions are satisfied. The first option, a knock-out call, whose premium is denoted by $C^{O}(t)$ , has the standard payoff $i f$ the $S_{t}$ never touches, or falls below, the barrier $H$ . The premium of the second option, a knock-in call, is denoted by $C^{I}{(t)}$ . It entitles its holder to the standard payoff of a vanilla call with strike $K$ , only if $S_{t}$ does fall below the barrier $H$ . These payoffs are shown in Figure 11.22. In each case, $H$ is such that, when the option knocks in or out, this occurs in a region with zero intrinsic value. Now consider the following logic that will lead to a contractual equation.  

1. Start with the case where $S_{t}$ is below the barrier, $S_{t}{<}H$ . Here, the $S_{t}$ is already below the threshold $H.$ So, the knock-out call is already worthless, while the opposite is true for the knock-in call. The knock-in is in, and the option holder has already earned the right to a standard vanilla call payoff. This means that for all $S_{t}{<}H$ , the knock-in call has the same value as a vanilla call. These observations mean  

$$
{\mathrm{~\e\range~}}S_{t}<H,{\mathrm{Knock-in+Knock-out=Vanilla~call=Knock-in~}}
$$  

The knock-out is worthless for this range.  

![](00e35b4c847e1a3d295b0f643062724fa685e2026a01e46dff216be449e8e961.jpg)  

# FIGURE 11.22  

Payoffs of a knock-out call and a knock-in call.  

2. Now suppose $S_{t}$ is initially above the barrier, $H.$ . There are two possibilities during the life of the barrier options: $S_{t}$ either stays above $H$ , or falls below $H$ . One and only one of these events will happen during $[t,T]$ . This means that, if we buy the knock-in call simultaneously with a knock-out call, we guarantee access to the payoff of a vanilla call. In other words,  

$$
\mathrm{For~the~range~}H<S_{t},\mathrm{Knock-in+Knock-out=Vanilla~call}
$$  

Putting these two payoff ranges together, we obtain the contractual equation:  

![](6a44528910a80cba657e361c3f20d15408c5a8a5b021a6af41134c8453ad0acd.jpg)  

From here, we can obtain the pricing formulas of the knock-in and knock-out barriers. In fact, determining the pricing function of only one of these barriers is sufficient to determine the price of  

the other. In Chapter 9, we provided a pricing formula for the knock-out barrier where the underlying satisfied the Black Scholes assumptions.12 The formula was given by  

$$
C^{O}(t)=C(t)-J(t)\quad{\mathrm{for}}\quad H\leq S_{t}
$$  

where  

$$
J(t)=S_{t}\left(\frac{H}{S_{t}}\right)^{\frac{2\left(r-\frac{1}{2}\sigma^{2}\right)}{\sigma^{2}}+2}N(c_{1})-K e^{-r(T-t)}\left(\frac{H}{S_{t}}\right)^{\frac{2\left(r-\frac{1}{2}\sigma^{2}\right)}{\sigma^{2}}}N(c_{2})
$$  

where  

$$
c_{1,2}=\frac{\ln(H^{2}/S_{t}K)+(r\pm\frac{1}{2}\sigma^{2})(T-t)}{\sigma\sqrt{T-t}}
$$  

The $C(t)$ is the value of the vanilla call given by the standard Black Scholes formula, and the $J(t)$ is the discount that needs to be applied because the option may disappear if $S_{t}$ falls below $H$ during $[t,T]$ .  

But we now know from the contractual equation that a long knock-in and a long knock-out call with the same strike $K$ and threshold $H$ is equivalent to a vanilla call:  

$$
C^{O}(t)+C^{I}(t)=C(t)
$$  

Using Eq. (11.41) with this gives the formula for the knock-in price as  

$$
C^{I}(t)=J(t)
$$  

Thus, the expressions in Eqs. (11.42) (11.44) provide the necessary pricing formulas for barrier options that knock-out and knock-in, when they are out-of-the-money under the Black Scholes assumptions. It is interesting to note that when $S_{t}$ touches the barrier,  

$$
S_{t}=H
$$  

the formula for $J(t)$ reduces to the standard Black Scholes formula:  

$$
J(t)=S_{t}N(d_{1})-K e^{-r(T-t)}N(d_{2})
$$  

That is to say, the value of $C^{O}(t)$ will be zero. The knock-out call option price is shown in Figure 11.22. We see that the knock-out is cheaper than the vanilla option. The discount gets larger, the closer $S_{t}$ is to the barrier, $H.$ . Also, the delta of the knock-out is higher everywhere and is discontinuous at $H$ .  

Finally, Figure 11.22 shows the pricing function of the knock-in. To get this graph, all we need to do is subtract $C^{O}(t)$ from $C(t)$ , in the upper part of Figure 11.22. The reader may wonder why the knock-in call gets cheaper as $S_{t}$ moves to the right of $K$ . After all, doesn’t the call become more in-the-money? The answer is no, because as long as $H<S_{t}$ the holder of the knock-in does not have access to the vanilla payoff yet. In other words, as $S_{t}$ moves rightward, the chances that the knock-in call holder will end up with a vanilla option are going down.  

# 11.4.2.2 Some uses of barrier options  

Barrier options are quite liquid, especially in FX markets. The following examples discuss the payoff diagrams associated with barrier options.  

The next example illustrates another way knock-ins can be used in currency markets. Figures 10.20 and 10.21 illustrate these cases.  

# EXAMPLE  

US dollar puts (yen calls) were well bid last week. Demand is coming from stop-loss trading on the back of exotic knock-in structures. At the end of December, some players were seen selling 1-month dollar puts struck at JPY119 which knock-in at JPY109.30. As the yen moved toward that level early last week, those players rushed to buy cover.   
Hedge funds were not the only customers looking for cover. Demand for short-term dollar puts was widely seen. “People are still short yen,” said a trader. “The risk reversal is four points in favor of the dollar put, which is as high as I have ever seen it.”  

(Based on an article in Derivatives Week (now part of GlobalCapital))  

According to the example, as the dollar fell toward 110.6 yen, the hedge funds who had sold knock-in options were suddenly facing the possibility that these options would come into existence, and that they would lose money.13 As a result, the funds started to cover their positions by buying out-of-the-money puts. This is a good illustration of new risks often associated with exotic structures. The changes during infinitesimal intervals in mark-to-market values of barrier options can be discrete instead of “gradual.”  

The next example concerning barrier options involves a more complex structure. The barrier may in fact relate to a different risk than the option’s underlying. The example shows how barrier options can be used by the airline industry.  

Airlines face three basic costs: labor, capital, and fuel. Labor costs can be “fixed” for long periods using wage contracts. However, both interest rate risk and fuel price risk are floating, and sudden spikes in these at any time can cause severe harm to an airline. The following example shows how airlines can hedge these two risks using a single barrier option.  

# EXAMPLE  

Although these are slow days in the exotic option market, clients still want alternative ways to hedge cheaply, particularly if these hedges offer payouts linked to other exposures on their balance sheets. Barrier products are particularly popular. Corporates are trying to cheapen their projections by asking for knockout options.  

For example, an airline is typically exposed to both interest rate and fuel price risks. If interest rates rose above a specified level, a conventional cap would pay out, but under a barrier structure it may not if the airline is enjoying lower fuel prices. Only if both rates and fuel prices are high is the option triggered. Consequently, the cost of this type of hedge is cheaper than separate options linked to individual exposures.  

(Thomson Reuters IFR, May 13, 1995)  

The use of such barriers may lower hedging costs and may be quite convenient for businesses. The exercises at the end of the chapter contain further examples of exotic options. In the next section, we discuss some of the new risks and difficulties associated with these.  

# 11.4.3 NEW RISKS  

Exotic options are often inexpensive and convenient, but they carry their own risks. Risk management of exotic options books is nontrivial because there are (i) discontinuities in the respective Greeks due to the existence of thresholds and (ii) smile effects in the implied volatility.  

As the previous three chapters have shown, risk management of option books normally uses various Greeks or their modified counterparts. With threshold effects, some Greeks may not exist at the threshold. This introduces discontinuities and complicates risk management. We review some of these new issues next.  

1. Barrier options may exhibit jumps in some Greeks. This is a new dimension in risk-managing option books. When spot is near the threshold, barrier option Greeks may change discretely even for small movements in the underlying. These extreme changes in sensitivity factors make the respective delta, gamma, and vega more complicated tools to use in measuring and managing underlying risks.   
2. Barrier options are path dependent. For example, the threshold may be relevant at each time point until the option expires or until the barrier is hit. This makes Monte Carlo pricing and risk-managing techniques more delicate and more costly. Also, near the thresholds the spot may need further simulated trajectories and this may also be costly.   
3. Barrier option hedging using vanilla and digital options may be more difficult and may be strongly influenced by smile effects.  

We will not discuss these risk management and hedging issues related to exotic options in this book. However, smile effects will be dealt with in Chapter 16.  

# 11.5 QUOTING CONVENTIONS  

Quoting conventions in option markets may be very complicated. Given that market makers look at options as instruments of volatility, they often prefer quoting volatility directly, rather than a cash value for the option. These quotes can be very confusing at times. The best way to study them is to consider the case of risk reversals. Risk reversal quotes illustrate the role played by volatility, and show explicitly the existence of a skewness in the volatility smile, an important empirical observation that will be dealt with separately in Chapter 16.  

One of the examples concerning risk reversals presented earlier contained the following statement:  

The 1-month risk reversal jumped to 0.81 in favor of euro calls Wednesday from 0.2 2 weeks ago.  

It is not straightforward to interpret such statements. We conduct the discussion using the euro/dollar exchange rate as the underlying risk. Consider the dollar calls represented in  

![](8994eebe7b17c5796cf8f92e747417e24422f73f5e1bdd036f59af7d69c840ef.jpg)  

# FIGURE 11.23  

Payoffs of ATM and 25-delta calls and puts.  

Figure 11.23a, where it is assumed that the spot is trading at 0.95, and that the option is ATM. In the same figure, we also show a 25-delta call. Similarly, Figure 11.23b shows an ATM dollar put and a 25-delta put, which will be out-of-the-money. All these options are supposed to be plain vanilla and European style.  

Now consider the following quotes for two different 25-delta USD risk reversals:  

The interpretation of such bid ask spreads is not straightforward. The numbers in the quotes do not relate to dollar figures, but to volatilities. In simple terms, the number to the right of the slash is the volatility spread the market maker is willing to receive for selling the risk reversal position and the number to the left is the volatility spread he is willing to pay for the position.  

The numbers to the right are related to the sale by the market maker of the 25-delta USD call and simultaneously the purchase of a 25-delta USD put, which, from a client’s point of view is the risk reversal shown in Figure 11.24a. Note that, for the client, this situation is associated with “dollar strength.” If the market maker sells this risk reversal, he will be short this position.  

![](8520021d4c5f50058998b03cdaafcc54709b4969d77bfba5a4080275b025fa30.jpg)  

# FIGURE 11.24  

Payoffs of two different 25-delta USD risk reversals.  

The numbers to the left of the slash correspond to the purchase of a 25-delta USD call and the sale of a 25-delta USD put, which is shown in Figure 11.24b. This outcome, when in demand, is associated with “dollar weakness.”  

# 11.5.1 EXAMPLE 1  

Now consider the interpretation of the numerical values in the first example:  

Example 1:}flat=0:3 USD call bid}  

The left side in this quote is “flat.” This means that the purchase of the 25-delta USD call, and a simultaneous sale of the 25-delta USD put, would be done at the same volatilities. A client who sells this to the market maker pays or receives nothing extra and the deal has “zero cost.” In other words, the two sides would agree on a single volatility and then plug this same number into the Black Scholes formula to obtain the cost of the put and the cost of the call. The right-hand number in the quote shows a bias. It means that the market maker is willing to sell the 25-delta USD call, and buy the 25-delta USD put, only if he can earn 0.3 volatility points net. This implies that the volatility number used in the sale of USD call will be 0.3 points higher than the volatility used for the 25-delta USD put. The market maker thinks that there is a “bias” in the market in favor of dollar strength; hence, the client who purchases this risk reversal will incur a net cost.  

# 11.5.2 EXAMPLE 2  

The second quote given by  

Example $2{:}^{\prime\prime}0.3/0.6$ USD call bid}  

is more complicated to handle, although the interpretation of the 0.6 is similar to the first example. With this number, the market maker is announcing that he or she needs to receive 0.6 volatility points net if a client wants to bet on the dollar strength.  

However, the left-hand element of the quote is not “flat” anymore but is a positive 0.3. This implies that the bias in the market, in favor of dollar strength is so large, and so many clients demand this long position that, now the market maker is willing to pay net 0.3 volatility points when buying the 25-delta call and selling the 25-delta put.  

Thus, in risk reversal quotes, the left-hand number is a volatility spread that the market maker is willing to pay, and the second number is a volatility spread the market maker would like to earn. In each case, to see how much the underlying options would cost, market participants have to agree on some base volatility and then, using it as a benchmark, bring in the volatility spreads.  

# 11.6 REAL-WORLD COMPLICATIONS  

Actual implementation of the synthetic payoff structures discussed in this chapter requires dealing with several real-world imperfections. First of all, it must be remembered that these positions are shown at expiration, and that they are piecewise linear. In real life, payoff diagrams may contain several convexities, which is an equivalent term for nonlinear payoffs. We will review these briefly.  

# 11.6.1 THE ROLE OF THE VOLATILITY SMILE  

The existence of volatility smile has especially strong effects on pricing and hedging of exotic options. If a volatility smile exists, the implied volatility becomes a function of the strike price $K$ . For example, the expression that gave the binary option price in Eqs. (11.30) (11.31) has to be modified to  

$$
\begin{array}{l}{{\displaystyle C^{\mathrm{bin}}(t)=\operatorname*{lim}_{h\rightarrow0}\frac{C^{K}(t)-C^{K+h}(t)}{h}}}\\ {{\displaystyle~=\frac{\hat{\partial}C^{K}(t)}{\hat{\partial}K}+\frac{\hat{\partial}C^{K}(t)}{\hat{\partial}\sigma(K)}\frac{\hat{\partial}\sigma(K)}{\hat{\partial}(K)}}}\end{array}
$$  

The resulting formula and the analogy to plain vanilla deltas will change. These types of modifications have to be applied to hedging and synthetically creating barrier options as well. Major modification will also be needed for barrier options.  

# 11.6.2 EXISTENCE OF POSITION LIMITS  

At time $t$ before expiration, an option’s value depends on many variables other than the underlying $x_{t}$ . The volatility of $x_{t}$ and the risk-free interest rate $\boldsymbol{r}_{t}$ are two random variables that affect all the positions discussed for $t<T.$ This is expressed in the Black Scholes formula for the call premium of $t<T$ :  

$$
C_{t}={C}({x}_{t},t|\sigma,r)
$$  

which is a function of the “parameters” $r,\sigma$ . At $t=T$ this formula reduces to  

$$
C_{T}=\operatorname*{max}[x_{T}-K,0]
$$  

Now, if the $r$ and $\sigma$ are stochastic, then during the $t\in[0,T)$ , the positions considered here will be subject to vega and rho risks as well. A player who is subject to limits on how much of these risks he or she can take, may have to unwind the position before $T.$ . This is especially true for positions that have vega risk. The existence of limits will change the setup of the problem since, until now, sensitivities with respect to the $r$ and $\sigma$ parameters, did not enter the decision to take and maintain the positions discussed.  

# 11.7 CONCLUSIONS  

In this chapter, we discussed how to synthetically create payoff diagrams for positions that take a view on the direction of markets and on the direction of volatility. These were static positions. We specifically concentrated on the payoff diagrams that were functions of a single risk factor and that were to be replicated by plain vanilla futures and options positions. The second part of the chapter discussed the engineering of similar positions using simple exotics.  

# SUGGESTED READING  

There are several excellent books that deal with classic option strategies. Hull (2014) is a very good start. The reader may also consult Natenberg (2014) for option basics. See also the textbooks Jarrow and Turnbull (1999) and Kolb (1999). Taleb (1996) is a good source on exotics from a market perspective. For a technical approach, consider the chapter on exotics in Musiela and Ruthkowski (2007). James (2003) is a good source on the technicalities of option trading and option pricing formulas. It also provides a good discussion of exotics.  

# EXERCISES  

1. Construct a payoff and profit diagram for the purchase of a 105-strike call and sale of a 95- strike call. Verify that you obtain exactly the same profit diagram for the purchase of a 105- strike put and a sale of 95-strike put. Explain the difference in the initial cost of these positions. Assume the following parameters: $S(0)=100\$ ; $T=1$ ; $r=8\%$ ; $\sigma=30\%$  

2. Assume that a trader believes that during the vacation periods actual realized volatility is lower than the implied volatility. To exploit this opportunity a trader takes a short position in a strangle to cover the cost of the long straddle position. If the actual volatility is $30\%$ less than the implied volatility, sketch out his volatility strategy. Assume the following parameters:  

$$
S(0)=1600;T=3\ \mathrm{month};r=5\%;\sigma=53\%
$$  

3. Consider a bear spread. An investor takes a short position in a futures denoted by $x_{t}$ . But he or she thinks that $x_{t}$ will not fall below a level $x^{\mathrm{min}}$ .  

a. How would you create a position that trades off gains beyond a certain level against large losses if $x_{t}$ increases above what is expected?   
b. How much would you pay for this position?   
c. What is the maximum gain? What is the maximum loss?   
d. Show your answers in an appropriate figure.  

4. Consider this reading carefully and then answer the questions that follow.  

A bank suggested risk reversals to investors that want to hedge their Danish krone assets, before Denmark’s Sept. 28 referendum on whether to join the Economic and Monetary Union. A currency options trader in New York said the strategy would protect customers against the Danish krone weakening should the Danes vote against joining the EMU. Danish public reports show that sentiment against joining the EMU has been picking up steam over the past few weeks, although the “Yes” vote is still slightly ahead. [He] noted that if the Danes vote for joining the EMU, the local currency would likely strengthen, but not significantly.  

Six- to 12-month risk reversals last Monday were $0.25\%/0.45\%$ in favor of euro calls. [He] said a risk-reversal strategy would be zero cost if a customer bought a euro call struck at DKK7.52 and sold a euro put at DKK7.44 last Monday when the Danish krone spot was at DKK7.45 to the euro. The options are European-style and the tenor is 6 months.  

Last Monday, 6- and 12-month euro/Danish krone volatility was at $I.55\%/I.95\%$ , up from $0.6\%/0.9\%$ for the whole year until April 10, 2000, owing to growing bias among Danes against joining the EMU. On the week of April 10, volatility spiked as a couple of banks bought 6-month and 9-month, at-the-money vol. (Based on Derivatives Week (now part of GlobalCapital), April 24, 2000.)  

a. Plot the zero-cost risk-reversal strategy on a diagram. Show the DKK7.44 and DKK7.52 put and call explicitly.   
b. Note that the spot rate is at DKK7.45. But, this is not the midpoint between the two strikes. How can this strategy have zero cost then?   
c. What would this last point suggest about the implied volatilities of the two options?   
d. What does the statement “Last Monday, 6- and 12-month euro/Danish krone volatility was at $I.55\%/I.95\%$ ,” mean?   
e. What does at-the-money vol mean? (See the last sentence.) Is there out-of-the-money vol, then?  

5. The following questions deal with range binaries. These are another example of exotic options. Read the following carefully and then answer the questions at the end.  

Investors are looking to purchase range options. The product is like a straightforward range binary in that the holder pays an upfront premium to receive a fixed pay-off as long as spot maintains a certain range. In contrast to the regular range binary, however, the barriers only come into existence after a set period of time. That is, if spot breaches the range before the barriers become active, the structure is not terminated.  

This way, the buyer will have a short Vega position on high implied volatility levels. (Based on an article in Derivatives Week (now part of GlobalCapital).)  

a. Display the payoff diagram of a range-binary option. b. Why would FX markets find this option especially useful? c. When do you think these options will be more useful? d. What are the risks of a short position in range binaries?  

6. Double no-touch options is another name for range binaries. Read the following carefully, and then answer the questions at the end.  

Fluctuating U.S. dollar/yen volatility is prompting option traders managing their books to capture high volatilities through range binary structures while hedging with butterfly trades. Popular trades include one-year double no touch options with barriers of JPY126 and JPY102. Should the currency pair stay within that range, traders could benefit from a USD1 million payout on premiums of $15-20\%$ .  

On the back of those trades, there was buying of butterfly structures to hedge short vol positions. Traders were seen buying out-of-the-money dollar put/yen calls struck at JPY102 and an out-of-the-money dollar call/yen put struck at JPY126. (Based on an article in Derivatives Week (now part of GlobalCapital).)  

a. Display the payoff diagram of the structure mentioned in the first paragraph. b. When do you think these options will be more useful?   
c. What is the role of butterfly structures in this case?   
d. What are the risks of a short position in range binaries?   
e. How much money did such a position make or lose “last Tuesday”?  

7. The next question deals with a different type range option, called a range accrual option. Range accrual options can be used to take a view on volatility directly. When a trader is short volatility, the trader expects the actual volatility to be less than the implied volatility. Yet, within the bounds of classical volatility analysis, if this view is expressed using a vanilla option, it may require dynamic hedging, otherwise expensive straddles must be bought. Small shops may not be able to allocate the necessary resources for such dynamic hedging activities.  

Instead, range accrual options can be used. Here, the buyer of the option receives a payout that depends on how many days the underlying price has remained within a range during the life of the option. First read the following comments then answer the questions.  

The Ontario Teachers’ Pension Plan Board, with CAD72 billion (USD48.42 billion) under management, is looking at ramping up its use of equity derivatives as it tests programs for range accrual options and options overwriting on equity portfolios.  

The equity derivatives group is looking to step up its use now because it has recently been awarded additional staff as a result of notching up solid returns, said a portfolio manager for Canadian equity derivatives. . .. With a staff of four, two more than previously, the group has time to explore more sophisticated derivatives strategies, a trader explained. Ontario Teachers’ is one of the biggest and most sophisticated end users in Canada and is seen as an industry leader among pension funds, according to market officials.  

A long position in a range accrual option on a single stock would entail setting a range for the value of the stock. For every day during the life of the option that the stock trades within the range, Ontario Teachers would receive a payout. It is, hence, similar to a short vol position, but the range accrual options do not require dynamic hedging, and losses are capped at the initial premium outlay. (Based on an article in Derivatives Week (now part of GlobalCapital).)  

a. How is a range accrual option similar to a strangle or straddle position?   
b. Is the position taken with this option static? Is it dynamic?   
c. In what sense does the range accrual option accomplish what dynamic hedging strategies accomplish?   
d. How would you synthetically create a range accrual option for other “vanilla” exotics?  

# EXCEL EXERCISES  

8. Write a VBA program to show the construction of a bull and bear spread, first using calls only and then using puts only. Also plot both the call spread and put spread in both bull and bear phases. Explain your observation for the difference in the initial cost of call and put spreads.  

Assume the following parameters: $S(0)=100$ ; $T=1$ ; $r=8\%$ ; $\sigma=30\%$ ; Spread $=10\%$ .  

9. Write a VBA program to show the fabrication of the butterfly spread composed of a strangle and straddle. Assume the following parameters: $S(0)=100$ ; $T=1$ ; $r=8\%$ ; $\sigma=30\%$ ; Spread $=5\%$ Plot the straddle and strangle payoff along with the payoff of the butterfly spread. Repeat the above calculation for the short position in butterfly spread.  

# MATLAB EXERCISE  

10. Write a MATLAB program to plot the following spreads including the time value of the spread as well as its payoff at the expiration. a. Bull spread  

b. Bear spread   
c. Straddle   
d. Strangle   
e. Butterfly Assume the following parameters: $S(0)=100\$ ; $T=1$ ; $r=8\%$ ; $\sigma=30\%$ ; Spread $=5\%$ .  