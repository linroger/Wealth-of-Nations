---
tags:
  - cboe
  - market_maker
  - options_markets
  - otc_market
  - strike_price
aliases:
  - CBOE
  - OTC
  - Options
  - Options Markets
key_concepts:
  - Call and put payoffs
  - ITM, ATM, OTM
  - Intrinsic and time value
  - Options market organization
  - Speculation and insurance
---
# OPTIONS  

# Options Markets  

# Aims  

• To discuss the organisation of options markets including the role of the clearing house and interpreting newspaper quotes.   
• To consider the payofs at maturity for long and short positions in calls and puts.   
• To show how options can be used for (i) speculation and (ii) providing insurance against adverse outcomes, while allowing the investor to also beneft from any ‘upside’.   
• To explain some terminology applied to calls and puts, such as in-the-money (ITM), at-the-money (ATM) and out-of-the-money (OTM), as well as intrinsic value and time value.  

# 14.1 MARKET ORGANISATION  

Options are traded on individual stocks, stock indices, commodities (e.g. crude oil, gold), foreign currencies, futures contracts and to a much lesser extent on Treasury notes and Treasury bonds. The major exchanges for fnancial options, are the Chicago Board Options Exchange (CBOE) and the Philadelphia Stock Exchange (PHLX) in the US and Intercontinental Exchange in London. The CBOE was established in 1973, initially trading stock options. It is the largest organised options market, trading standardised contracts and has a deep secondary market.  

The over-the-counter (OTC) options market tailors the option contract to the buyer’s specifcations and is now very large and probably over 10 times larger than the exchange traded options market – although often the secondary OTC market is thin. However, some active secondary OTC markets do exist, particularly the market in European options on foreign exchange negotiated for commercial customers. The advantage of OTC markets can be illustrated by considering a portfolio manager who wishes to alter the risk profle of her ‘specialist’ portfolio of stocks by buying an OTC put option. With the OTC contract:  

• She can exactly match her own portfolio composition with the underlying assets in the tailor-made OTC put option.   
• Expiration date of the put can be tailored to her investment horizon.   
• She maintains anonymity, so her belief that the market will fall is not communicated to other traders.   
• Drawbacks to using the OTC market are possibly higher transaction cost as well as counterparty risk.  

# 14.1.1 US Stock Options  

We use the example of US stock options and stock index options to illustrate some of the administrative procedures which operate when these are traded on an exchange.  

# 14.1.2 Contract Size  

Options are traded on CBOT (in Chicago) and options on individual stocks are usually for delivery of 100 stocks. Options on stock indexes are also available and are cash settled. The exchange sets the dollar value of an index point (e.g. $\$100$ ). For example, the cash payof to a long call option on a stock index (S&P 500) for $S_{T}=2\mathrm{,050}$ and $K=2{,}000$ is $\$100(S_{T}-K)=$ $\$5,000$ , which is paid by an (assigned) writer (seller) of the option (who has not closed out). The cash payment is usually based on the stock index quote (on the NYSE) at the end of the day on which the option is exercised (rather than when the exercise order is made).  

# 14.1.3 Expiration Dates  

These are fxed by the exchange and stock options are traded for expiration up to $4.30\ \mathrm{p.m}$ . (Central Time) on the third Friday of the expiry month. The holder of a long call on a stock can instruct his broker to exercise the option up until $4.30\mathrm{p.m}$ . on that Friday. The broker then has until $10.59\mathrm{p.m}$ . the next day (Saturday) to notify the exchange that exercise will happen.  

Expiration dates for options on individual stocks usually extend to about 9 months – with some exceptions. For example, LEAPS (Long Term Equity Anticipation Securities), which are primarily options on around 500 individual (diferent) stocks (but some are also on stock indices), have expiration dates of about 3 years ahead. Similarly FLEX (short for ‘fexible’) options on stocks and stock indices can have any expiration date of up to 5 years ahead and in addition they permit the purchaser to set any exercise price and can be European or American.  

# 14.1.4 Strike/Exercise Prices  

These, for example, might be set at $\$2.50$ intervals when the underlying stock price is less than $\$25$ , at $\$5$ intervals when the stock price is between $\$25$ and $\$200$ and at $\$10$ intervals for a stock price over $\$200$ . Strike prices are set either side of the current stock price and as the stock price moves up or down, options with new strike prices are added by the exchange.  

# 14.1.5 Trading  

Over $95\%$ of orders on the CBOE are via an electronic platform. But trading still takes place on the foor of the CBOE. An individual who has purchased (or rents) a seat on the CBOE may be a ‘market maker’ who stands ready to quote both bid and ask (ofer) prices on the option. The ‘bid’ price is the price the market maker is prepared to buy the option and the ‘ask’ price is the price at which he is prepared to sell. Prices are quoted by open outcry on the foor of the exchange. Market makers must stand ready to trade with investors. An investor who has purchased an option can close out her position by selling (writing) the same option (i.e. with the same strike and expiration date).  

# 14.1.6 Options Clearing Corporation (OCC)  

For US options markets (except those trading futures options) the Options Clearing Corporation (OCC) standardises contracts and acts as an intermediary, efectively creating two separate contracts.  

For example, if a trader buys a call option the OCC guarantees that the writer will honour the contract. An option writer represents a credit risk to the OCC since she may not have funds to purchase the underlying asset (e.g. stock) in the spot market to facilitate delivery. The OCC therefore requires the writer to post a margin payment (usually in cash and equal to at least $30\%$ of the value of the stocks underlying the option contract plus the call premium). There is also a maintenance margin which might be set at a minimum of $15\mathrm{-}25\%$ of the value of the stocks underlying the option contract. An option buyer has no margin requirement with the OCC since the most she can lose is the option premium, which is paid in full at the outset of the contract.  

Initial margins vary depending on whether one has a naked (uncovered) position (i.e. no ofsetting holding in the underlying stocks) or a covered/hedged position. The latter is less risky and involves less initial margin. Margin positions on strategies such as straddles, spreads etc. are governed by special rules described in publications on the CBOE website.  

Take, for example, a written call on a stock, where the initial margin is $30\%$ of the value of the stock, plus the option premium. However, if the call is out-of-the-money $(S_{0}<K)$ then the margin is reduced by $K-S_{0}$ . If $S_{0}=110$ , $K=120$ (i.e. out-of-the-money) and $C_{0}=\$2$ , and each call is written on 100 stocks, then the margin payment would be $\$2,500=100[0.3S_{0}+C_{0}-(K-S_{0})]$ . If the call had been in-the-money or at-the-money the deduction of $K-S_{0}$ would not be allowable. A similar rule applies to written puts.  

Option prices on a stock index are less volatile and hence (uncovered) written index options would have a margin requirement based on, say, $15\%$ of the dollar value of the stock-index, rather than the $30\%$ for individual stock options.  

# 14.1.7 Orders  

For example, suppose in January Ms Long wants to buy a December-call option on AT&T stocks with a strike of $K=90$ . Her broker would instruct (electronically) a market maker with a seat on the exchange. Trading is conducted in a pit. The buyer shouts out the bid (e.g. $\$4$ ) and accepts the lowest ofers ‘shouted’ to him by the market maker (e.g. $\$4.1$ ), giving a contract price of $\$410$ (for delivery of 100 stocks per contract). The OCC keeps track of all trades on the exchange.  

Next Ms Long deposits $\$410$ with her broker, who passes this on to his OCC ‘clearing frm-ABC’ by the next (business) morning. This money is credited to the option writer’s clearing frm-XYZ. The option writer’s clearing frm-XYZ also receives a margin payment from the writer of the option. The clearing frms ABC and XYZ then aggregate all the transactions of their customers and deposit funds with the OCC as surety on the net contracts outstanding, according to a prearranged formula. The OCC is therefore the ultimate guarantor for Ms Long, the purchaser of the call option. Because the clearing frms also hold some default risk, the OCC imposes minimum capital requirements on them.  

# 14.1.8 Offsetting Order  

If in January Ms Long originally purchased a December-90 call option on AT&T at $\$4.10$ (total $\mathrm{cost}=\$410$ ) then she can sell this contract in June (say) by placing an ofsetting order. If Ms Long sells at $\$4.50$ then $\$450$ will be passed to her clearing frm ABC (and then on to Ms Long) and the OCC will cancel Ms Long’s position in this contract. The trader who buys the call option from Ms Long will usually not be the person from whom Ms Long initially purchased the contract. If the purchaser of Ms Long’s sale of her option is establishing a new long position in the contract then the ‘open interest’ would remain the same, with the new ‘owner’ noted by the OCC. If both traders are closing existing positions, the open interest falls by one contract.  

# 14.1.9 Exercising an Option  

If the buyer (Ms Long) of a December-90 AT&T call option holds the option to maturity and exercises the option, her broker notifes the OCC member (ABC) that clears its trades. ABC then places an exercise order with the OCC who ‘assigns’ a member (XYZ) with an outstanding short position in the same option (i.e. with same strike, same maturity, same underlying asset).  

This may be a random assignment or a ‘frst-in, frst-out’ rule may be used. The OCC member (XYZ) then selects a specifc investor (Ms Short) who has an existing short position – using a specifc procedure, for example random allocation. Ms Short having then been assigned, must fulfl the delivery terms – she must deliver 100 stocks of AT&T and she will receive $K=90$ per stock. A cash amount equal to the strike price is passed from Ms Long’s broker via her clearing frm-ABC to the assigned writer’s clearing frm-XYZ. Hence the ‘assigned writer’ is unlikely to be the original trader who initially sold Ms Long the call option.  

Suppose Ms Long holds a December-90 put option on a stock to its expiration date. Then a trader holding a short position must take delivery of 100 stocks of AT&T from Ms Long and pay her $K=90$ per stock. When an option is exercised the open interest falls by one. All at-the-money options should be exercised (if the payof at maturity is greater than any transactions costs) and some brokers will do this automatically for their clients. A very rough estimate is that about $10\%$ of calls and puts on the CBOE are exercised and about $30\mathrm{-}40\%$ expire out-of-the money.  

# 14.1.10 Commissions  

Market makers trade their own book but are obliged to ‘fll’ all public orders. They make profits (losses) on their own book and also earn the bid–ask spread on a buy-sell ‘round trip’. Market makers buy at the bid price and sell the same contract at a higher ofer (ask) price. The exchange sets upper limits for the bid-ofer spread – for example, $\$0.75$ for options prices between $\$10$ and $\$20$ .  

Commissions for retail investors are usually a fxed cost plus a proportion of the value of the trade – and discount brokers charge less than full-service brokers. For example, a dollar trade of between $\$3,000$ and $\$10,000$ via a discount broker might involve commission of $\$30+1\%$ of the dollar amount’ in the trade. Larger trades generally involve larger fxed costs but lower variable cost. When ofsetting an existing position in an option, the commission must be paid again. When exercising a stock option, the commission will probably be the same as for a buy or sell order and may be around $1\%$ of the stock’s dollar value.  

# 14.1.11 Position Limits and Exercise Limits  

The exchange (often on the instructions of the regulator) also specifes position limits, namely the maximum number of contracts that an investor can hold on one side of the market. For individual stock options (CBOE) with high market capitalisation and trading volume, the position (and exercise) limit might be set at 250,000 contracts (on the same side of the market). Long calls and short puts are on the same side of the market because each contract’s value increases (decreases) as the underlying price increases (decreases). Put diferently, the premia on long calls and short puts are positively correlated. Short calls and long puts are also on one side of the market.  

Investors are also limited in the number of contracts that can be exercised in any fve consecutive business days (i.e. exercise limit). The fgure for the exercise limit is usually the same as the position limit. The purpose of position and exercise limits is to prevent single traders or groups of traders acting together and having a signifcant infuence on the market price. However, theses limits may reduce liquidity and may drive some business into the OTC market.  

# 14.1.12 Newspaper Quotes  

Illustrative price quotes on 2 November for call and put options on stock-XYZ are shown in Table 14.1. The expiration dates are in the frst column. The current price (on the NYSE) of the underlying stock is $\$26.80$ . The strike prices in the second column are set (by the exchange) above and below the current stock price. The columns labelled ‘Price’ denote the closing price for the call or put option (for the $3\ \mathrm{p.m}$ . trade) and these columns are followed by the daily trade volume as well as the open interest (i.e. number of long or short contracts outstanding). Note that the quoted option price for the ‘3pm trade’ in Chicago might not be based on the recorded price for the underlying stock on the NYSE because the two prices might not be taken at exactly the same time, especially if the option is rather illiquid and hence infrequently traded.  

TABLE 14.1 Option on Stock-XYZ (2 November)   


<html><body><table><tr><td rowspan="2">Expiration</td><td rowspan="2"> Strike</td><td colspan="3">Call </td><td colspan="3">Put</td></tr><tr><td> Price</td><td>Volume</td><td>Open Interest</td><td> Price</td><td>Volume</td><td>Open Interest</td></tr><tr><td>Jan</td><td>20.00</td><td>6.85</td><td>216</td><td>136,915</td><td>0.09</td><td>263</td><td>146,405</td></tr><tr><td>Apr</td><td>20.00</td><td>7.35</td><td>412</td><td>2,259</td><td>0.34</td><td>10</td><td>6,422</td></tr><tr><td>Nov</td><td>22.50</td><td>4.29</td><td>368</td><td>5,888</td><td>0.03</td><td>100</td><td>10,314</td></tr><tr><td>Dec</td><td>22.50</td><td>4.40</td><td>14</td><td>3,603</td><td>0.13</td><td>96</td><td>3,483</td></tr><tr><td>Jan</td><td>22.50</td><td>4.55</td><td>484</td><td>165,421</td><td>0.26</td><td>260</td><td>134,777</td></tr><tr><td>Apr</td><td>22.50</td><td>5.04</td><td>124</td><td>4,788</td><td>0.69</td><td>190</td><td>8,773</td></tr><tr><td>Nov</td><td>25.00</td><td>1.80</td><td>6,064</td><td>35,262</td><td>0.12</td><td>1,127</td><td>62,772</td></tr><tr><td>Dec</td><td>25.00</td><td>2.25</td><td>1,901</td><td>8,490</td><td>0.47</td><td>883</td><td>7,619</td></tr><tr><td>Jan</td><td>25.00</td><td>2.61</td><td>4,048</td><td>204,784</td><td>0.74</td><td>508</td><td>107,419</td></tr><tr><td>Apr</td><td>25.00</td><td>3.45</td><td>172</td><td>21,996</td><td>1.39</td><td>448</td><td>17,931</td></tr><tr><td>Nov</td><td>27.50</td><td>0.27</td><td>13,306</td><td>70,256</td><td>1.07</td><td>5,859</td><td>20,912</td></tr><tr><td>Dec</td><td>27.50</td><td>0.81</td><td>9,834</td><td>20,000</td><td>1.47</td><td>1,594</td><td>6,126</td></tr><tr><td>Jan</td><td>27.50</td><td>1.21</td><td>8,063</td><td>160,038</td><td>1.85</td><td>3,016</td><td>18,254</td></tr><tr><td>Apr</td><td>27.50</td><td>2.01</td><td>1,220</td><td>31,842</td><td>2.51</td><td>293</td><td>14,925</td></tr><tr><td>Nov</td><td>30.00</td><td>0.03</td><td>168</td><td>8,029</td><td>3.31</td><td>70</td><td>1,788</td></tr><tr><td>Dec</td><td>30.00</td><td>0.19</td><td>2,865</td><td>6,864</td><td></td><td></td><td>319</td></tr><tr><td>Jan</td><td>30.00</td><td>0.47</td><td>2,667</td><td>194,423</td><td>3.70</td><td>310</td><td>7,336</td></tr><tr><td>Apr</td><td>30.00</td><td>1.09</td><td>496</td><td>24,296</td><td>4.10</td><td>66</td><td>2,686</td></tr></table></body></html>

Notes: The cash-market price (NYSE) on stock- $\mathsf{X Y Z}=\$26.80$ .  

From Table 14.1 you can see that the alternative exercise (strike) prices range from 20.00 to 30.00 (there are other strike prices available which are not reported here). Call prices (premiums) for the $K=22.50$ strike for expiration months November, December, January and April are 4.29, 4.40, 4.55, and 5.04 respectively – so the call premium increases with the maturity date of the option. The quoted option premium assumes delivery of one stock but 100 stocks must be delivered for each contract, so the invoice price for the option $\mathbf{\tau}=$ $\mathrm{\textperthousand}$ quoted price’.  

By looking at the November contracts with strike prices $K=20.00$ , 22.50, 25.00, 27.50, and 30.00 you can see that the call premia fall as the strike price increases. The converse applies to the put premia which are positively related to the strike price. By looking at the put premia for contracts that have expiration dates of 25 November and 25 April (of the next year), you can see that put premia increase with the time to maturity of the contract.  

# 14.2 CALL OPTIONS  

If today you buy a European call option and pay the call premium/price, then this gives you the right (but not an obligation):  

• to purchase the underlying asset at a   
• designated delivery point at a   
• specifed future date (known as the expiration or maturity date) • for a fxed known price (the exercise or strike price)   
• and in an amount (contract size) which is fxed in advance.  

A European option can only be exercised on the expiry date itself whereas an American option can be exercised any time up to the expiry date. Note, however, that European (and American) options can be sold to another market participant at any time. Most options traded on exchanges are American but as European options are easier to analyse we deal mainly with the latter. Note that we frst concentrate on the payof profles at expiration, in Chapter 16 we discuss what causes the change in options prices second-by-second.  

# 14.2.1 Positions in Options  

As we see below there are always two parties to any options trades and these are classifed as follows:  

Long call $\c=$ call option Short call $\c=$ sell or write call option Long put $\b=$ option Short put $\b=$ sell or write option  

# 14.2.1.1 Long Call: Insurance  

Consider, for example, the purchase of a (European) call option on stock-XYZ on 15 July, when the current price of stock-XYZ on the NYSE is $S_{0}=\$80$ . One contract is for delivery of 100 stocks and if the quoted call premium $C=\$3$ , the contract will cost $\$300$ . Assume the strike price is $K=\$80$ (i.e. an ATM option) and the expiry date $T$ is in about 3 months’ time on 25 October (Figure 14.1).  

First consider how the purchases of a call option can provide insurance. Suppose that in July a pension fund knows it will receive an infow of funds in October and wants to invest in stocks-XYZ. If in July, the pension fund purchases an October-call option (in Chicago), it will have set a maximum purchase price of $K=\$80$ , if it decides to exercise the contract in October – this is a form of insurance.  

Clearly, if on 28 October $S_{T}=\mathbb{\S}88>K=\mathbb{\S}80$ then the pension fund will exercise the option in Chicago, take delivery and pay $\$80$ per stock – which is cheaper than purchasing stocks-XYZ on the NYSE at $\$88$ (Figure 14.1). A trader who has an outstanding short position in the October-call is legally bound to deliver the stock to the pension fund and receives $\$80$ .  

![](74bd3c863ee71657aa512fbb966f0339698c1c29f3bddd38b23350626fc19dbc.jpg)  
Payoff depends on stock price at maturity, $S_{T}=88$ .  Cash settled, $\mathsf{P a y o f f}=\mathsf{m a x}(S_{T}-K,0)$   
FIGURE 14.1 Long call option (payof at maturity)  

Alternatively, the long call option can be ‘cash settled’ by the pension fund which receives $S_{T}-K=\$8$ in Chicago (a trader with an outstanding short position in the October call, provides the $\$8$ ). The pension fund can then buy stock-XYZ on the NYSE for $S_{T}=\$88$ , which when ofset against the receipt of $\$8$ from ‘cash settled’ call, gives an efective cost for the stocks-XYZ of $\$80$ – the same as the strike price in the call option contract. Hence, (ignoring transactions costs) ‘delivery’ or ‘cash settlement’ results in the same value to the holder of the long call.  

On the other hand, if the stock price on 25 October is $S_{T}=\$77$ (i.e. below the strike price of $K=\$80$ ), then the pension fund will not exercise the call, since it can purchase the stocks-XYZ at lower cost on the NYSE.  

Hence, the call option provides insurance in the form of a maximum price payable of $K=\$80$ (if $S_{T}>K)$ ) but also allows the pension fund to not exercise the call option (if $S_{T}<K)$ and then the pension fund buys stock-XYZ at the lower price on the NYSE. The cost of this insurance is the call premium of $C=\$3$ which is paid in July.  

One further thing to note is that the maximum price the pension fund ‘locks in’ is the strike price in the options contract and not the stock price (on the NYSE) when the pension fund purchases the call option in July. For example, suppose the actual stock price on the NYSE on 15 July, is $S_{0}=\$78$ . This price of $\$78$ is not the maximum purchase price the pension fund will pay on 25 October when it exercises the call option. The maximum price the pension fund will pay in October when exercising the call option is the strike price $K=\$80$ .  

# 14.2.1.2 Long Call: Speculation  

Now consider purchasing an October-call option on 15 July for $C=\$3$ , in order to speculate on the future price of stock-XYZ over the next 3 months (Table 14.2). If the actual price of stock-XYZ on 25 October turns out to be $S_{T}=\$88$ , then the holder of the call option can take delivery at $K=\$80$ and sell each stock-XYZ on the NYSE at $\$88$ – which implies a payof of $\$8$ . Alternatively the speculator can cash settle the long call and receive $\$8$ (from the options clearing house). In either case the ‘payof’ from exercising the call on 15 October is $\$8$ per stock:  

TABLE 14.2 Buy (long) call option   


<html><body><table><tr><td>Current stock price, S = $78</td></tr><tr><td>Traders' desk (today, 15 July)</td></tr><tr><td>Contract size = 100 stocks</td></tr><tr><td>Strike price, K = $80 Call premium (price), C = $3</td></tr><tr><td>Premiumpaid=100($3)= $300</td></tr><tr><td>Outcome (3 months later on 15 October, time T)</td></tr><tr><td>Stock price at expiry, S = $88</td></tr><tr><td>Cash payoff at expiration: (S - K)100 = ($88 - $80) 100 = $800 Profit (net of call price): (S - K - C) 100 = ($8 - $3) 100 = $500</td></tr></table></body></html>  

![](9f879e392a1f3ca5705bf94ffc95360b70a1738251c6998f3051c83c1f1dd5b1.jpg)  
FIGURE 14.2 Long call option (proft at maturity)  

$$
P a y o f f\colon l o n g c a l l=(+1)[m a x(0,S_{T}-K)J^{1}
$$  

if $S_{T}>K$ exercise the option.  

The $\cdot_{+1}\cdot$ implies we are long one call option. In October, the ‘proft’ $\Pi$ (after deduction of the call premium $C=\$3$ ) is $\$5$ per stock (Figure 14.2).2  

$$
\begin{array}{l}{\Pi=(+1)[\operatorname*{max}(0,S_{T}-K)-C]}\\ {=(S_{T}-K)-C\qquad\quad\mathrm{for}S_{T}>K(\mathrm{exercisetheoption})}\\ {=-C\qquad\quad\mathrm{for}S_{T}<K(\mathrm{donotexercise})}\end{array}
$$  

The breakeven stock price occurs when $\Pi=0$ :  

$$
S_{B E}=K+C=\S80+\S3=\S83
$$  

Each call option contract is for ‘delivery’ of 100 stocks; hence, if $S_{T}=\$88$ the speculator makes an overall proft of $\$500$ . On the other hand, if at expiration $S_{T}=\mathbb{\mathbb{S}}78\left(<\mathrm{K}\right)$ the speculator would not exercise the option. The call option expires worthless but the speculator has only lost the call premium of $\$300$ , which was paid when she initially purchased the option in July.  

Hence a speculator who holds (i.e. is long) a call option can at most lose the call premium. However, the speculator can beneft from an unlimited upside potential, if the stock price in October ends up well above the strike price. The return to the speculator from a long call is asymmetric.  

If the stock price at expiration is $\$82$ then the proft to the speculator from the long call is $-\$1$ $\left(=\$82-\$80-\$3\right)$ , that is, a loss of $\$1$ . However, in this case it is still worth exercising the long call, since if the speculator does not do so, her net loss is the premium of $C=\$3$ , which is larger than the $\$1$ loss from exercising the call. In fact, if the stock price exceeds the strike price $(S_{T}>K)$ at the expiration date, it always pays to exercise the call option (since this positive payof will contribute to reducing the efective cost of the call premium).  

It is useful to designate the payof profle from options in terms of direction vectors – this will be especially useful when we look at options strategies in Chapter 17. The payof from a long call is represented by the direction vector $\{0,+1\}$ . When $S_{T}<K$ , the payof to the long call is zero – hence the use of $\cdot\mathrm{0^{\circ}}$ in the payof vector. When $S_{T}>K$ , the long call earns a positive payof which increases dollar-for-dollar with the stock price – this is a positive relationship, hence the use of $^{\cdot}{+}1^{\cdot}$ in the direction vector (see inset in Figures 14.1 and 14.2). For a light-hearted view of how call options can be used, see Finance Blog 14.1.  

# Finance Blog 14.1 Call Options – Ken and Barbie  

Assume there are lots of ‘Kens’ (i.e. desirable but identical males) which can be picked up at the local nightclub. It is January and Barbie decides she likes the Kens she has met but is unsure about marrying one of them. She wants to wait a year to see how things work out for these Kens and only then will she decide whether to marry a Ken in 1 year’s time. She will marry a Ken in a year’s time if his prospects then look good. But she knows that if Kens behave badly and don’t have a decent job at the end of the year, it will probably not be worth marrying any Ken, at that point.  

Let’s get Barbie to buy a December-call option on Ken with a strike price of $K=\$100$ where the delivery point at the maturity date of the option in December, is the local church. She pays a call premium of $C=\$3$ in January (which is paid to the market maker who sells the call option to Barbie). Barbie’s long call option sets a maximum price of $K=\$100$ , she will pay for ‘delivery’ of a Ken December (if she then wishes to take delivery).  

If over the next year, Kens improve their salaries so that they are worth $S_{T}=\$110$ , then Barbie will exercise her call option. She then turns up at the church in December and marries Ken for a mere payment of $K=\$100$ (to the clergyman o\$ciating), even though a ‘spot’ or ‘cash-market’ Ken would cost her $S_{T}=\mathfrak{S}110$ at the local nightclub round the corner. (Note that if Barbie holds the call option to maturity and decides to exercise the option then Ken is contractually bound to turn up at the church, he has no choice.)  

Hence, Barbie by purchasing the December $\$100$ -call option in January has a form of ‘insurance’. By paying $C=\$3$ in January she knows the maximum price she will pay for delivery of Ken next December is $K=\$100$ .  

On the other hand, if Kens have no pay rises, get demoted or lose their jobs over the next year, their spot (cash market) price in the local club might drop to say $S_{T}=\$90$ (i.e. fall below $K=\$100$ ). In this case Barbie would not exercise her call option and would simply  

(continued)  

# (continued)  

not turn up at the church. Under the terms of the option contract, she does not even have to tell Ken she will not be turning up – so Ken could sufer abject humiliation at the altar in December.  

If the spot-price for Kens in December is $S_{T}=\$90$ then Barbie could if she wished, purchase a Ken in the spot market at her local club for $\$90$ , and take immediate delivery. So Barbie’s long call option ensures that in 1 year’s time, she pays a maximum price of $K=\$100$ for delivery of a Ken, yet she can take advantage of the lower spot price for Kens, in December should this occur.  

If you saw the flm Four Weddings and a Funeral you will know that Hugh Grant’s character ‘Charles’ did turn up at the church with the intention of marrying ‘Duckface’ (Henrietta). But he really could have saved himself the trouble and embarrassment by purchasing a long call on Duckface earlier in the year – then he would have had the option of whether to turn up or not (depending on what he thought the value of Duckface was at the maturity of the call option, on the prospective wedding day).  

Again, those of you who know the ending of Four Weddings and a Funeral will realise that what Hugh Grant (Charles) probably held was an embedded rainbow call option (or alternative option). This type of option has two underlying assets (e.g. two diferent stocks/people) and at maturity of the option, you can take delivery of the underlying asset which has the best ‘payof’ of the two.  

In Four Weddings and a Funeral, Charles implicitly held a long rainbow call option based on two underlying assets: Duckface and the Andie MacDowell character, Carrie. He took the view that the highest payof at the expiration date was Carrie rather than Duckface – so he took delivery of Carrie. Incidentally, a rainbow option is more expensive to buy than either a plain vanilla option on Carrie or a plain vanilla option on Duckface. But you already know that ‘dating’ two people simultaneously is generally more expensive than dating just one of them.  

Those of you who have seen the flm several times will recall that Duckface actually had an option of her own. This was a down-and-out knockout call option on Charles, which she executed with a right hook – before the ceremony was completed (i.e. before maturity of the option) – so for her, Charles was ‘knocked out’ (literally) and hence Duckface accepted that the payof to the call would be zero, at any point thereafter.  

Duckface realised the low ‘cash-market’ value she placed on Charles that day because his behaviour had fallen below the barrier of decency even expected of an English ‘fop’. Therefore she decided to terminate (‘knockout’) her call option on Charles. Even if Charles had later redeemed himself in Duckface’s eyes, she could not in future exercise the call option and pay $K$ for delivery of Charles – the option she held had been ‘knocked out’ before maturity (i.e. before the exchange of rings at the wedding ceremony).  

Down-and-out options do exist in the real world. For example, a down-and-out call option on a stock is one that ‘dies’ (i.e. efectively no longer exists) if the stock price falls below a pre-specifed level (‘the lower barrier’), before the maturity date of the option contract. Then even if the stock price at maturity of the call option contract has risen above the strike price (i.e. $S_{T}>K)$ ), the ‘down-and-out call is worthless at maturity – as it had ‘died’ before maturity.  

Source: Adapted from Cuthbertson and Nitzsche (2008).  

# 14.2.1.3 Write (Sell) a Call  

One simple way to fnd out what happens to the proft at maturity for the writer of a call is to work out the proft to the long call $(+\$55)$ and simply reverse the sign. If the long call makes a cash proft of $\$5$ then the person who wrote (sold) the call makes a cash loss of $\$5$ . Let us look at this in more detail.  

If $S_{T}=\$88$ , on 25 October then the writer of the call has to purchase the stock in the cash market (NYSE) at $S_{T}=\$88$ but receives only $K=\$80$ when she delivers the stock (in Chicago) to the holder of the long call (Figure 14.3). The writer of the call has a payof of $^{-\$8}$ $(=-(S_{T}-K)$ .  

Alternatively, if the long call is cash settled then the trader with an outstanding short positon (i.e. the writer) makes a cash payment of $\$8$ to the holder of the call but on 15 July she had received $C=\$3$ when she sold the call option, so her proft is $-\mathbb{S}5=-(S_{T}-K)+C$ , that is, a loss. The writer makes a total loss on one contract of $\$500$ which is the mirror image of the $\$500$ gain, made by the long call.  

Alternatively, if the actual stock price on 25 October is (say) $S_{T}=\$77$ (i.e. below the strike price of $K=\$80$ ), then the holder of the call option (‘the long’) will not exercise it (in Chicago), since she can purchase the stocks at lower price on the NYSE. Hence, when $S_{T}<K$ , the writer of the call option makes a proft of $\$3$ , which is the option premium she received in July. The payof at maturity from one written call is:  

![](5263128ee3da74c35c7b6afc02491a22d78ddda72260539393d799fa07f1c300.jpg)  
FIGURE 14.3 Short (sell, write) call option  

$$
\mathrm{Payoff:written\call}=(-1)[\operatorname*{max}(0,S_{T}-K)]
$$  

The $\cdot_{-1}\cdot$ implies you initially wrote (sold) one call option. The proft at maturity for the writer of the call is:  

$$
\begin{array}{r l r}{\lefteqn{\Pi=(-1)\left[\operatorname*{max}(0,S_{T}-K]+C\right.}}\\ &{=-[S_{T}-K]+C}&{{\mathrm{for}}~S_{T}>K}\\ &{=+C}&{{\mathrm{for}}~S_{T}\leq K}\end{array}
$$  

# 14.3 PUT OPTIONS  

If you buy a European put option (in Chicago) this gives you the right to sell the underlying asset (in Chicago) at some time in the future, at a strike price fxed in the option contract.  

If today you buy a European put option and pay the put premium/price, then this gives you the right (but not an obligation):  

• to sell the underlying asset at a   
• specifed future date (the expiration/maturity date) at a • designated delivery point   
• for a known fxed price (strike/exercise price)   
• in an amount (contract size) which is fxed in advance.  

# 14.3.1 Long Put $+$ Stock: Insurance  

First let us see how the purchase of a put option (i.e. you go long the put) can be used to set a minimum value you will receive in the future, for stocks that you already own. The stock $^+$ put is like an insurance contract which sets a minimum future selling price for the stock but allows most of the ‘upside capture’ should stock prices rise in the future.  

Suppose on 15 July Ms Prudence, a pension fund manager, holds 100 stocks of XYZ, with a price of $S_{0}=\$72$ on the NYSE. Ms Prudence has to pay out someone’s lump-sum pension in 3 months’ time (on 25 October) and she is worried that the stock price will fall below $\$70$ . But she also wants to take advantage of any rise in stock prices, should this occur. Ms Prudence can eliminate most of the downside risk by purchasing a put option, with a strike price $K=\$70$ and expiration date on 25 October. Each put contract is for delivery of 100 stocks. Ms Prudence must pay the put premium $P=\$2$ today.  

By purchasing the put, Ms Prudence guarantees that she can, if she wishes, sell her stocks for $K=\$70$ each, by exercising the put contract in Chicago on 25 October – even if the price of the stocks on the NYSE is much lower, say $S_{T}=\$20$ per stock. The options market in Chicago must honour Ms Prudence’s decision to exercise the put, by delivering her stocks to Chicago, for which she receives the strike price $K=\$70$ in the put contract. The $K=\$70$ paid to Ms Prudence, will be provided by a Chicago options trader (Mr Short) who has a short position in the October-70 put, on the 25 October (i.e. Mr Short has previously sold an October-put with a strike of $K=\$70$ and has not closed out his position before 25 October). Mr Short’s $\$70$ payment to Ms Prudence will be paid via the options clearing house.  

Alternatively, the long put can be ‘cash settled’ by Ms Prudence for receipt of $K-S_{T}=$ $\$70-\$820=450$ cash (provided by Mr Short via the options clearing house). Ms Prudence then sells the stock (owned by the pension fund) on the NYSE for $S_{T}=\$20$ , giving an ‘efective’ cash value for the put stock position of Ms Prudence of $\$70$ – the same as the strike price in the put contract.  

On the other hand, if in October, $S_{T}=\mathbb{S}75(>K=\mathbb{S}70)$ then Ms Prudence can ‘walk away’ from the put contract (i.e. not exercise it in Chicago) but instead sell stocks-XYZ on the NYSE at the high price of $\$75$ per stock.  

This means that whatever happens to the stock price on the NYSE over the next 3 months, Ms Prudence can either exercise the put and sell stocks-XYZ at a minimum price of $K=\$70$ (in Chicago), or if the stock price rises above $\$70$ , she can ‘throw away’ the put option (i.e. not exercise it in Chicago) and sell her stocks-XYZ at the higher spot price on the NYSE. Hence, if you already own some stocks, buying a put option today provides insurance in the form of a guaranteed minimum price when you sell your stocks (on the expiration date of the put), whilst also allowing you to beneft from any ‘upside potential’, should the stock prices rise on the NYSE.  

For a light-hearted analysis of the payofs when holding a ‘spot market asset’ and using puts to insure a minimum selling price, see Finance Blog 14.2.  

# Finance Blog 14.2 Put Options – Ken and Barbie  

Let’s get Barbie to insure the minimum future value she will obtain for ‘Ken’ by using a put option. Suppose that Barbie has been married to Ken for some time but she is getting rather tired of him. So Barbie already holds a Ken who is currently worth $S_{0}=\$100$ but she is worried he may be worth much less in 1 year’s time.  

Should she have a trial separation and then divorce him at the end of the year? The problem is that if she waits a year to divorce him, Ken may lose his job and his market value may fall over the year, thus reducing Barbie’s pay-out in the divorce settlement. On the other hand, if Ken does rather well in the jobs market and is worth more at the end of the year then she may wish to stay married to Ken. How can options help to solve Barbie’s dilemma?  

In January Barbie can buy (go long) a December-Ken put contract with strike price $K=\$100$ . Assume the put contract costs Barbie $P=\$2$ (which she pays in January to the  

(continued)  

# (continued)  

options trader who sells Barbie her put contract). The long put contract gives Barbie the right to ‘deliver’ Ken in Chicago next December and receive $K=\$100$ , but only if she fnds this advantageous.  

Next December, if Ken’s earning power and hence his ‘cash market’ price has deteriorated to say $S_{T}=\$90$ , Barbie will deliver him (along with the put contract) to the attorney’s o\$ce in Chicago (the designated delivery point) and get divorced. Under the terms of the put contract she will receive the generous divorce settlement of $K=\$100$ on delivery of Ken to the attorney’s o\$ce, even though Ken is only currently worth $S_{T}=\$90$ in the ‘jobs market’.  

Of course, if Ken’s earning power and his cash-market price rises over the coming year to $S_{T}=\$110$ , then Barbie will not exercise her put contract to sell Ken for $\$90$ at the attorney’s o\$ce, since he is currently worth $\$110$ . So Barbie will ‘throw away’ her put contract – it is worthless. She may stay with Ken and the marriage will continue. Or, she can sell Ken in the ‘cash market’ in her local club for $S_{T}=\$110$ (to another ‘Barbie’ who is looking for immediate delivery that night of a Ken). Again, Ken has no choice in the matter – Barbie has purchased the put contract on Ken and hence holds ‘all the cards’, which is sometimes the case in a divorce. This ‘insurance contract’ on Ken may have cost Barbie a mere $\$2$ last January, when she purchased the put option on Ken.  

Source: Adapted from Cuthbertson and Nitzsche (2008).  

# 14.3.2 Long Put: Speculation  

There are also opportunities for speculation with put options. On 15 July, suppose a speculator Ms Doom, expects the price of stock-XYZ to fall substantially between July and October (say). To beneft from a future stock price fall, Ms Doom buys an October-put option contract on 15 July, with $K=\$70$ , exercise date 25 October and pays the put premium $P=\$2$ on 15 July. (Note that here Ms Doom only holds a put option, she does not hold any stocks).  

Suppose the price of stock-XYZ on the NYSE on 25 October is $S_{T}=\$65$ $\mathop{\bf{\tilde{\rho}}}\angle K=$ $\$70$ – Figure 14.4. Then on 28 October, Ms Doom could buy 100 stocks-XYZ on the NYSE for $S_{T}=\$65$ per stock, and then exercise the put option by delivering these to Chicago for which she receives $K=\$70$ per stock from the options clearing house. Ms Doom has a positive payof of $\$5$ $(=K-S_{T})$ per stock3 and a net proft of $\$3$ after paying the put premium of $P=\$2$ (Figure 14.5). If one put contract is for delivery of 100 stocks then the outcome is given in Table 14.3.  

![](432ad62d67bd5cdcc91ae46dbdf22cddcec31421c4402076895c782175f271b3.jpg)  
Payoff depends on stock price at maturity, $S_{T}=65$ . Cash settled, Payoff $\mathbf{\Sigma}=\mathbf{\Sigma}$ max $(K{-}S_{T},0$ )  

![](bdb367e83f71aafd7ebd858402ee5d440aa13b70febc934b86815876787286d4.jpg)  
FIGURE 14.4 Long put option (payof at maturity)   
FIGURE 14.5 Long put option (proft at maturity)  

TABLE 14.3 Buy (long) put option   


<html><body><table><tr><td>Current stock price, Sg= $72</td></tr><tr><td>Traders' desk (today, 15 July) Contract size = 100 stocks</td></tr><tr><td>Strike price, K = $70</td></tr><tr><td>Put premium (price), P = $2</td></tr><tr><td>Premium paid =100($2)= $200</td></tr><tr><td>Outcome (3 months later: 25 October, time T)</td></tr><tr><td>Stock price at expiry, S = $65</td></tr><tr><td>Cash payoff at expiration: (K - S) 100 = ($70 - $65) 100 = $500</td></tr></table></body></html>  

Hence the payof from holding one long put is:  

P ${\mathfrak{y o f f:l o n g}}\operatorname{put}=(+1)[\operatorname*{max}(0,K-S_{T})]^{4}$ exercise the put if $S_{T}<K$  

The proft from the long put is:  

$$
\begin{array}{l}{\Pi=(+1)[\operatorname*{max}\left(0,K-S_{T}\right)-P]}\\ {\quad=(K-S_{T})-P\qquad\quad\mathrm{for}\ S_{T}<K}\\ {\quad=-P\qquad\quad\mathrm{for}\ S_{T}>K}\end{array}
$$  

If $S_{T}>K$ then Ms Doom does not exercise the put (which expires worthless) but the most she loses is the put premium, $P=\$2$ . The breakeven stock price occurs when $\Pi=0$ :  

$$
S_{B E}=K-P=\S70-\S2=\S68
$$  

The payof profle for a long put (Figure 14.5) is represented by the direction vector $\{-1,0\}$ . When $S_{T}>K$ , the payof to the long put is zero – hence the use of $\cdot\mathrm{0}^{\cdot}$ in the payof vector. When $S_{T}<K$ , the long put earns a positive payof which increases dollar-for-dollar as the stock price falls – this is a negative relationship, hence the use of $\cdot_{-1}\cdot$ in the direction vector.  

# 14.3.3 Write (Sell) a Put  

The payof to the seller of a put is the opposite of that of the buyer of a put – there are two sides to every trade – if one side ‘wins’ the other ‘loses’. Let us look at this in more detail.  

Suppose Ms Doom already has a long position in the October-put. If $S_{T}=\mathbb{\S}65<K=\mathbb{\S}70$ , then Ms Doom will exercise the put and receive a payof of $\$5$ . Hence, Ms Writer, who has previously sold (written) a put, will have a negative payof if the (long) put is exercised (i.e. $S_{T}<K)$ . Ms Writer is legally obliged to ‘receive’ the stock from Ms Doom in Chicago and pay Ms Doom $K=\$70$ . But Ms Writer can only sell the stock for $S_{T}=\$65$ on the NYSE (Figure 14.6) – a loss of $\$5$ to Ms Writer. But Ms Writer when she initially sold (written) the October-put in July received the put premium $P=\$2$ , so her net loss is $\$3$ . Hence the payof to Ms Writer (at expiration) is:  

$$
P a y o f f\colon S h o r t p u t=(-1)[m a x(0,K-S_{T})J
$$  

(–1, implies Ms Writer has sold a put).  

The proft at maturity for Ms Writer is:  

$$
\begin{array}{l}{\Pi=(-1)[\operatorname*{max}\left(0,K-S_{T}\right)-P]}\\ {\quad=-[K-S_{T}]+\mathrm{P}}\\ {\quad=+P\qquad\quad\mathrm{for}\ S_{T}>K}\end{array}
$$  

![](0183220a958af1f51b9c79e93311741361b6f919c7634e1c2b0e8e268f2694de.jpg)  
FIGURE 14.6 Short (sell, write) put option  

The payof to the writer of the put option is just the ‘mirror image’ of the payof for Ms Doom who is long the put (see Equation 14.4).  

# 14.4 INTRINSIC VALUE AND TIME VALUE  

Illustrative prices for call options (on stock-A), on 1 July for strike prices $K=\$360$ and $K=\$390$ are shown in Table 14.4. These are American call options so they can be exercised immediately by the holder, if this is advantageous. The current stock price on the NYSE is $S_{0}=\$376$ .  

In exchange traded options markets there would be many more strike prices and maturity (expiration) dates available and the OTC market (i.e. mainly large banks such as JPMorgan-Chase, Barclays) will in principle provide equity options with almost any strike and maturity date.  

TABLE 14.4 Call premia on stock-A, 1 July   


<html><body><table><tr><td rowspan="2">Strike price</td><td colspan="3">Expiry month</td></tr><tr><td>October</td><td>January</td><td>April</td></tr><tr><td>360</td><td>36.5 (16 / 20.5)</td><td>50.0 (16 / 34)</td><td>57.5 (16/41.5)</td></tr><tr><td>390</td><td>21.5 (0 \ 21.5)</td><td>35.5 (0/35.5)</td><td>44.0 (0 \ 44)</td></tr><tr><td colspan="2">Stock Price (NYSE, 1 July): Sg = $376</td><td></td><td></td></tr></table></body></html>

Notes: Prices denoted in dollars. $\left(.\backslash.\right)=$ (intrinsic \ time value) of call option.  

# 14.4.1 In, Out, and At-the-Money  

For a long position in a call option the option is said to be:  

In-the-Money (ITM): if Current Spot Price $>$ Strike Price $(S_{0}>K)$ At-the-Money (ATM): if Current Spot Price $\c=$ Strike Price $(S_{0}=K)$ ) Out-of-the-Money (OTM): if Current Spot Price $\prec$ Strike Price $(S_{0}<K)$  

Strictly speaking an option is ‘in-the-money’ if $S_{0}$ exceeds the present value of the strike price (i.e. $\begin{array}{r}{\dot{S}_{0}\dot{>}K e^{-r\widetilde{T}},}\end{array}$ ) but the simpler defnitions above are usually used.  

# 14.4.2 Newspaper Quotes: Calls  

On 1 July, the 360-October calls (Table 14.4) must be worth at least $\$16$ because the long has the right to exercise the American call option and buy stock-A at $K=\$360$ (in Chicago) and immediately sell the stocks for $S_{0}=\$376$ on the NYSE. The cash payout from immediately exercising a call option is the ‘intrinsic value’ of the option.  

$$
I n t r i n s i c\nu a l u e=S_{0}-K=376-360=\S16
$$  

The October-390 call has a call premium of $\$36.5$ , which is greater than the intrinsic value of $\$16$ . The reason for this is that there is a chance that between 1 July and the October expiration date, the stock price will increase even further (thus increasing the value of the call). Hence, the option has an additional source of value known as the ‘time value’ of the option.  

$$
{\begin{array}{r l}&{T i m e V a l u e=C a l l P r e m i u m-I n t r i n s i c V a l u e}\\ &{}\\ &{\qquad=36.5-16=\S20.5}\end{array}}
$$  

Now consider the October-390 call. This has an intrinsic value of zero since the holder of this call would not wish to take immediate delivery in the option contract and pay $K=\$390$ and then immediately sell the stock on the NYSE for $S_{0}=\$376$ . However, there is a chance that on or before the maturity date of the option, the stock price will rise above $K=\$390$ . For the October-390 call, the long is willing to pay $\$21.5$ on 1 July, for that chance.  

Notice that for either of the calls $\mathbf{\zeta}^{K}=\$360$ or $K=\$390$ the long is willing to pay a higher call premium, the longer the time to expiry – hence these options have time value that increases with time to maturity (look along the rows in Table 14.4). This is because there is a longer time over which the stock price might rise above (or well above) the strike price. In summary we have:  

Intrinsic Value IV max S0 K 0 For Long Calls: Time Value = C0 IV  

# 14.4.3 Newspaper Quotes: Puts  

Let us undertake a similar analysis of put options on stock-A (Table 14.5). The October-390 puts have an intrinsic value of $\begin{array}{r}{\mathrm{~\boldmath~\s~}_{14}(=K-S_{0})}\end{array}$ . This is because the holder of the put option could buy the stocks on the NYSE for $S_{0}=\$376$ and sell (deliver) them immediately for $K=\$390$ (in Chicago) by immediately exercising the American put option.  

The 390-puts have an intrinsic value of $I V=\$14$ , but the put premium for the October expiry is $P=\$31$ . The time value is therefore $\$17$ $.7\:(=P-I V=31-14)$ . This refects the possibility that between 1 July and the October maturity date of the option, the price of stock-A might fall futher, thus increasing the payof $K-S$ to holding the put option.  

$$
F o r L o n g P u t s.I n t r i n s i c V a l u e,I V=\operatorname*{max}\{K-S_{0},0\}
$$  

Put premia increase as the time to expiry increases (look along the rows in Table 14.5), since over a long horizon there is an increased chance that the stock price will end up below the strike price and the put payof will be positive.  

# 14.4.4 In/Out-of-the-Money  

Note that the 360-calls (Table 14.4) are in-the-money (ITM) (i.e. $S_{0}-K>0\big>$ while the 390-calls are out-of-the-money (OTM). Hence the 360-calls have relatively high intrinsic values and relatively low time values. The converse applies for the 390-calls which are OTM and hence have zero intrinsic value and relatively large time values. Similar considerations apply to the puts.  

TABLE 14.5 Put premia on company-A, 1 July   


<html><body><table><tr><td rowspan="2">Strike price</td><td colspan="3">Expiry month</td></tr><tr><td>October</td><td>January</td><td>April </td></tr><tr><td>360</td><td>16 (0 / 16)</td><td>25 (0 / 25)</td><td>27.5 (0 \ 27.5)</td></tr><tr><td>390</td><td>31 (14 \ 17)</td><td>40 (14 \ 26)</td><td>43.5 (14\29.5)</td></tr><tr><td>Stock price (NYSE, 1 July): S = $376</td><td></td><td></td><td></td></tr></table></body></html>

Notes: Prices denoted in dollars. $\left(.\backslash.\right)=$ (intrinsic \ time value)  

4.5 SUMMARY • For a speculator, a long call allows for the possibility of large upside gains to be made if the price of the underlying asset (e.g. stock) ends up well above the strike price, $K.$ . Downside losses for the speculator are limited to the call premium paid, C. • A speculator should buy a (European) call option if she thinks stock prices will rise (above $K+C)$ at maturity of the option. For a speculator who holds a long call, it provides payof $\mathrm{nax}(S_{T}-K,0)$ when exercised. • For a speculator, a long put allows for the possibility of large gains to be made if the price of the underlying asset ends up well below the strike price $K.$ . Downside losses for the speculator who is long a put is limited to the put premium paid, $P$ . • A speculator who holds a long put, has a payof of max $(K-S_{T},0)$ on the exercise date of the put. • A speculator should buy a (European) put option if she thinks stock prices will fall (below $\ensuremath{\boldsymbol{K}}-\ensuremath{\boldsymbol{P}})$ at the expiration date of the option. • A written (short) call gives unlimited downside risk should stock prices rise. A written (short) put gives substantial downside risk should the stock price fall. Writers of options therefore have to post margin payments with the clearing house. • A long call can be used to provide insurance. A long call implies the maximum price you will pay for a stock (at maturity of the option) is the strike price, K. But if the stock price falls in the future then you can ‘walk away’ from the call option contract (i.e. not exercise the call) and purchase stocks on the NYSE at their current low price. Hence a long call provides insurance (i.e. an asymmetric payof) and the call premium is the price of this insurance. • If you already hold stocks then a long put can be used to provide insurance. Holding a stock and a put implies you can exercise the put and deliver the stock (in Chicago) at expiration of the put contract and receive a minimum selling price of $K$ for your stocks (in Chicago) – even if the stock price on the NYSE is less than $K.$ . But you can also take advantage of high stock prices $(S_{T}>K)$ should they materialise by not exercising the put and selling your stock on the NYSE for $S_{T}{\big(}>K{\big)}$ . The put premium is the price of this insurance. • The call premium comprises two components. The intrinsic-value of a long call is the payof to be made on immediate exercise, $I V\equiv\operatorname*{max}[S_{0}-K,0]$ . But option premia also incorporate time value, which refects the fact that the option may eventually end up in-the-money, at (or before) the maturity date. The time-value of a call option with current price $C_{0}$ is $C_{0}-I V$ .  

• For a long put option the intrinsic value is $I V\equiv\operatorname*{max}[K-S_{0},0]$ and the time-value is $P_{0}-I V.$   
• The options clearing house facilitates an active market in traded options by minimising credit (default) risk, as traders holding short positions in either calls or puts have to post margin payments.  

# EXERCISES  

# Question 1  

If the stock price at maturity of a long call option is $S_{T}=\$82$ , and $K=\$80$ and $C=\$3$ would you exercise the option? What is the payof and proft for the long call?  

# Question 2  

You think the stock market will rise over the next 2 months. What are the advantages and disadvantages of purchasing a call with either a low or a high strike price?  

# Question 3  

Suppose you have written a call option on a stock-XYZ. What will happen at maturity if the option is either out-of-the-money or in-the-money?  

# Question 4  

You purchase a long call option on Apple stocks (on CBOE) from the writer, ‘Writecorp’, using clearing frm-XYZ and hold it to maturity. At maturity the assigned short in this option is ‘Shortcorp’. What happens at maturity if delivery takes place?  

# Question 5  

When is a long call ‘in-the-money’ (ITM) and when is a long put ‘out-of-money’ (OTM)?  

# Question 6  

Why does the buyer of a call option not have to provide margin payments to the options clearing house?  

# Question 7  

Why does the writer of a call option have to make margin payments to the options clearing house? Consider the possible outcomes at maturity of the call.  

# Question 8  

Suppose you purchase a put. In what sense does the strike price act like a ‘deductible’ in a standard insurance contract?  

# Question 9  

Frank purchased a call option on 100 stocks of Gizmo plc 1 year ago at a call premium of $C=\$10$ . (Each call delivers one stock at maturity). The stock price at the time was $S=\$110$ and the strike price $K=\$120$ . At expiration, 1 year later, the stock price is $S_{T}=\$135$ .  

(a) State whether the option should be exercised.   
(b) Calculate the payof and the proft or loss on the option (including the option premium)   
(c) Would Frank have done better by investing the same amount of cash 1 year ago in a bank ofering $10\%$ p.a.?  