---
tags:
  - bear_spreads
  - bull_spreads
  - butterfly_spreads
  - condors
  - financial_engineering
  - option_strategies
  - straddles
  - strangles
  - volatility_strategies
aliases:
  - Call Premium
  - Option Payoffs
  - Put Premium
  - Structured Products
  - Synthetic Securities
key_concepts:
  - Bull and bear spreads
  - Combine options for payoffs
  - Forecasting stock prices
  - Long call payoff
  - Long put payoff
  - Short call payoff
  - Short put payoff
  - Volatility strategies
---
# Option Strategies  

# Aims  

• To show how options can be combined to produce di!erent payo! profles – this is fnancial engineering.   
• To demonstrate how bull and bear spreads are speculative strategies based on forecasting the direction of change in stock prices.   
• To show how options can be combined to beneft from strategies based on forecasting the range (whether up or down) of future movements in stock prices. These are volatility strategies and include straddles, strangles, butterfy spreads, and condors.  

A combination of calls, puts, and stocks can produce a wide variety of payo!s, the generic term for which is fnancial engineering or structured products. One example of fnancial engineering we have already met is the put–call parity relationship, which resulted in a structured product often referred to as a ‘guaranteed bond’. In this chapter we examine how options can be combined in order to speculate on the future value (or range of values) for the underlying asset (or underlying futures contracts). In analysing these trades the main thing to remember is that the call premium is positively related to the price of the underlying asset and the put premium is negatively related to the price of the underlying asset. A second key fact is that both the call and put premia increase (decrease) when the volatility of the underlying asset return increases (decreases).  

The underlying asset in the option’s contract could be the stock of a particular company (AT&T), an industry sector (e.g. Internet Index Options on CBOE), a market index (e.g. S&P 500), a commodity (e.g. oil, silver, wheat), a futures contract, an exchange rate, bond price or interest rates (the latter are dealt with in Chapters 40 and 41). Our examples assume the options are written on a stock.  

# 17.1 SYNTHETIC SECURITIES  

To illustrate possible outcomes from combining several options we frst consider payo!s at maturity, T. A long call, if held to maturity (Figure 17.1) gives a zero payo! if the stock price at maturity is less than the strike price and a $\$1$ payout for every $\$1$ the spot price at expiry exceeds the strike price: this is designated a $\{0,+1\}$ payo!. A short (written) call if held to maturity, has a payo! profle which is the ‘mirror image’ of the long call.  

Prior to expiration, the payo! profle of a long call is the dashed line in Figure 17.1, as given by the Black–Scholes formula. This curve moves towards the ‘kinked’ $\{0,+1\}$ payo! as the option approaches maturity (i.e. as it loses time value). Similarly, prior to maturity a written call has the ‘curved’ payo! profle in Figure 17.1 and its time value increases as the call approaches maturity (for any given stock price).  

A long put (Figure 17.2) involves a zero payo! if the stock price at maturity is above the strike price $S_{T}>K$ . A long put has a positive payo! at maturity if $S_{T}<K$ . The positive payo! increases the lower is the stock price – this is a negative relationship, so the payo! is designated $\{-1,\ 0\}$ .1  

Prior to expiration, the payo! profle of a long put is the dashed line in Figure 17.2. At ‘reasonably high’ stock prices the long put loses time value represented by the curved line moving towards the ‘kinked’ line. However, at ‘very low’ stock prices a long (European) put may increase in value as the time to maturity approaches.2 The payo! for a short put is the mirror image of the long put (see Figure 17.2).  

![](4da6d0a3bbbcc95dec6c835c864cee746fe859d0c00275473922eb6e98c33541.jpg)  

![](44ecd78350c19933d1415f98ce2d3ba822a81ecd23bf3aaeefde324f61757d3b.jpg)  
FIGURE 17.2 Payo! for puts  

The payo! profle from being long stocks is $\{+1,+1\}$ . If you are long stocks and the stock price increases then there is a positive payo!, as your stocks are worth more (Figure 17.3). The payo! profle if you short-sell stocks is $\{-1,-1\}$ . If you short-sell stocks and the stock price increases then your position has fallen in value – since you would have to close out at a higher price and you make a loss – this is a negative relationship between the stock price and the payo! (Figure 17.3). If we assume the futures price moves dollar-for-dollar with the stock price, then the payo! profle for a futures contract is the same as for the stock. We could therefore use the futures price in place of the stock price.  

Suppose we have three assets: stocks, calls, and puts (with the same underlying, maturity dates and strike price, $K,$ . Taking any two of these three assets we can replicate the payo! profle of the remaining one. Put another way we can create a ‘synthetic’ or ‘replication portfolio’ to mimic the outcome for a call, put, or position in the stock.  

![](8240dfb784aa5ce58591780719c73919221a40a4d749d2be335e678d8222c916.jpg)  
FIGURE 17.3 Payo! for futures/stocks  

# 17.1.1 Synthetic Long Call  

Figure 17.4 demonstrates that the payo! profle for a synthetic long call can be obtained by combining a long stock and a long put (with the same strike $K$ , and time to maturity, $T)^{3}$ :  

$$
\begin{array}{l}{{\mathrm{Long~stock+Long~Put=Long~Call}}}\\ {{\{+1,+1\}+\{-1,0\}\ =\{0,+1\}}}\end{array}
$$  

# 17.1.2 Synthetic Short Put  

The payo! profle of a synthetic short put (Figure 17.5) can be obtained from a long stock and short call (with same strike $K$ , and time to maturity $T$ ):  

$$
\begin{array}{l l}{{\mathrm{Short~put}}}&{{=\{+1,0\}}}\\ {{\mathrm{}}}&{{={\mathrm{Long~stock}}=\{+1,+1\}}}\\ {{\mathrm{}}}&{{+{\mathrm{Short~call}}}}&{{=\{0,-1\}}}\end{array}
$$  

![](f45b6ef7093cf5712ef30e23d95df10bb490428acd089c814db5f80c9475b2c5.jpg)  
FIGURE 17.4 Synthetic long call  

![](fbdf7f22e5816e4a26484814c19931c39f2e73749f55abe484e5a348479693c4.jpg)  
FIGURE 17.5 Synthetic short put  

# 17.1.3 Synthetic Long Forward  

A synthetic long stock (or futures) can be generated by combining a short put and a long call (with the same strike, $K$ and time to maturity, $T$ ) – Figure 17.6.  

$$
\begin{array}{l l}{{\mathrm{Long~stock~(futures)}=\{+1,+1\}}}\\ {{\mathrm{~}}}\\ {{\mathrm{~}}}\\ {{\mathrm{~}}}\\ {{\mathrm{~\Tort~put~}}}\\ {{\mathrm{~}}}\\ {{\mathrm{~}}}\end{array}\qquad{\Longrightarrow}{\mathrm{~}}\{+1,\ 0\}}\\ {{\mathrm{~}}}\\ {{\mathrm{~}}}\\ {{\mathrm{~}}}\end{array}
$$  

![](abc339df9e1867cd85e9b411355e98fff14c6b6543ece59ab171d4a5c00c3cc1.jpg)  
FIGURE 17.6 Synthetic long futures  

# 17.1.4 Spreads and Straddles  

Investors use option spreads because they involve less risk than an open or naked option’s position but this risk reduction comes at a cost in terms of lower potential profts. Spreads may involve just calls or just puts or a combination of calls and puts. There are several di!erent types of spread:  

• Vertical (or money) spread: Use either calls or puts with the same expiration date but with di!erent strike prices $K$ – these are directional bets – that is, a speculative position which depends either on a rise or fall in the underlying asset price.   
• Straddle, Strangle, Butterfy, and Condor: These use calls and puts and are speculative bets which depend on the volatility of the underlying asset price – large movements in either direction can cause profts or losses.   
• Horizontal (or time or calendar) spreads: Use options with the same strike price $K$ but with di!erent maturity dates.   
• Diagonal spread: Use options with di!erent maturities and with di!erent strike prices.  

The term ‘vertical spread’ arises from the fact that newspaper quotes list the di!erent strike prices in a (vertical) column and the term ‘horizontal spread’ because di!erent expiry months are printed across the row. We use the convention that ‘buying the spread’ (i.e. a long spread position) involves a positive net payments (at time $t=0$ ) to set up the options trade. For example, buying an April-call at $C_{1}$ with a low strike price $K_{1}=102$ and selling an April-call at $C_{2}$ with a high strike price $K_{2}=105$ (i.e. both with the same expiry date in April) will involve an ‘up front’ net cash payment since $C_{1}>C_{2}$ . This would usually be referred to as buying the April-102/105 call spread, where it is understood that the frst fgure $\cdot_{102}\cdot$ refers to the option which is purchased. The April-102/105 put spread would be ‘selling the spread’ since the cost of purchasing the 102-put would be less than the receipts from selling the 105-put.  

If we are dealing with a time-spread with only one strike price, then the position will be long if we buy the nearby contract and sell the far contract. Hence, buying the April-102 call and selling the July-102 call would be a net long position (i.e. buy the spread). The investor would receive a net cash infow from a long time-spread, as the price of the July contract is higher than the price of the April contract.  

# 17.2 BULL AND BEAR SPREADS  

In the frst set of money spreads we consider, the investor takes a bet on the direction the stock price will move but she wishes to insure against large downside losses should the bet subsequently prove to be incorrect. These strategies are known as bull and bear spreads.  

# 17.2.1 Bull Spread with Calls  

If an investor expects a rise in stock prices then she could proft either by:  

• purchasing the stock (or forward contract) today or • buying a call option or   
• selling a put option.  

Buying stocks could be expensive (e.g. bid–ask spreads, commissions, price impact) and involves downside risk and selling a put option has a large downside risk, if the stock price subsequently falls.  

An alternative to the above strategies, which involves a loss of some upside potential, but also reduces the downside risk, is to undertake a bull spread – the payo! is given in Figure 17.7 and is of the form $\left\{0,+1,\ 0\right\}$ . A bull spread can be constructed using two calls with the same maturity $T$ but di!erent strikes $K$ :  

Bull spread payo! 0 1 0 $\mathbf{\beta}=B u y$ call with strike price K1 0 1 1 and Sell call high strike price $K_{2}>K_{1}=\{0,0,-1\}$  

There is a ‘trick’ to producing these results, which may be useful. Start with the bull spread payo! $\{0,+1,0\}$ – this payo! profle is what we are aiming for (line-1 above). Start producing this payo! by working from the left. First you ‘fx’ the $\cdot\mathrm{0^{\cdot}}$ and $^{\cdot}{+}1^{\cdot}$ but then you must continue with another $^{\circ}+1^{\circ}-\mathsf{a s}$ an option only has one ‘kink’ in its payo! profle (line-2 above). When deciding on the entries in line-3 you make sure you do not alter your original $\cdot_{0,+1},$ (in line-2), by putting $\cdot\mathrm{0},0^{\cdot}$ as the frst two elements on the left (line-3) and then include $\cdot_{-1}\cdot$ so that the sum of the third column for lines 2 and 3 is 0 – as required to reproduce line-1. Practise this, it can be useful.  

![](db8d5515418599a1b2951ca6647aa7d5eaa87e209c498d43afcb00e1a883565b.jpg)  
FIGURE 17.7 Bull spread with calls  

A bull spread is a money spread since the options have the same expiration date but different strike prices. So, for example, setting up this position in January, both calls could be for expiration in October (say). Compared with holding a naked long-call, there is a lower breakeven and a reduction in cost because of the premium received from the sold (written) call. However, there is also the loss of some upside potential, compared with holding just the long call.  

Let us examine this strategy in a little more detail. Consider the following two calls (which have the same expiration date):  

$$
C_{1}=5\ K_{1}=102\ C_{2}=2\ K_{2}=110
$$  

Note that the low strike price call $\left(K_{1}=102\right)$ has the higher call premium and hence it costs $C_{1}-C_{2}=3$ to go ‘long $K_{1}^{\mathrm{~,~}}$ and ‘short $K_{2}^{:}$ ’, to set up the spread trade. Since you pay out cash at $t=0$ , you are buying the spread. The proft (net payo!) at expiration is4:  

$$
\begin{array}{r l}&{\Pi=\operatorname{Max}(0,\ -K_{1})-\operatorname{Max}(0,\ S_{T}-K_{2})-(C_{1}-C_{2})}\\ &{S_{T}\le K_{1}\le K_{2}\colon\ \Pi=-(C_{1}-C_{2})}\\ &{K_{1}<S_{T}\le K_{2}\colon\ \Pi=S_{T}-K_{1}-(C_{1}-C_{2})}\\ &{S_{T}>K_{1}>K_{2}\colon\ \Pi=S_{T}-K_{1}-(S_{T}-K_{2})-(C_{1}-C_{2})}\\ &{\qquad=K_{2}-K_{1}-(C_{1}-C_{2})}\end{array}
$$  

When the stock price $S_{T}$ is less than both $K_{1}$ and $K_{2}$ then both options expire out-ofthe-money and you pay the premium $C_{1}=5$ and receive the premium $C_{2}=2$ on the written call, making an overall loss of 3 (which is independent of how far $S_{T}$ is below $K_{1}$ ). When $S_{T}$ exceeds both $K_{1}$ and $K_{2}$ then both calls are exercised. The stock delivered in the long call is used to deliver against the short call with net payo! $K_{2}-K_{1}>0$ . Alternatively, both calls could be cash settled (i.e. no delivery) and again the payo! is $K_{2}-K_{1}>0.$ . The cash proft is:  

$$
\Pi=K_{2}-K_{1}-(C_{1}-C_{2})=8-3=5
$$  

which is independent of $S_{T}$ . (This payo! will always be positive since the maximum payo! is $K_{2}-K_{1}$ and this must always exceed the cost of setting up the position, namely  

$(C_{1}-C_{2})$ , given by the Black–Scholes formula.) For the intermediate case, the proft is $\Pi=S_{T}-K_{1}-(C_{1}-C_{2})$ and the breakeven stock price (i.e. $\Pi=0$ ) is:  

$$
S_{B E}=K_{1}+(C_{1}-C_{2})=102+3=105
$$  

The breakeven stock price $S_{B E}$ (at expiry) must exceed the strike price $K_{1}$ by at least the up-front cost of setting up the bull spread $C_{1}-C_{2}$ .  

What about the payo! profle when the bull spread has been in existence for some time? Suppose the original bull spread was purchased in January with a maturity date in October. In March the payo! profle is given by the curved line in Figure 17.7 and notice that the arrows indicate possible time decay characteristics. If the stock price is above the break-even price, then the bull spread has positive time value and benefts the holder. This is because the positive time value of the written option benefts the holder of the bull spread and this more than counteracts the negative time decay of the long call option. The converse applies if the stock price is ‘low’ – then the time decay works against the holder of the bull spread – and its value falls over time (at any given stock price).  

# 17.2.2 Bull Spread with Puts  

The bull spread proft profle $\{0,+1,0\}$ can also be constructed from puts with di!erent strike prices:  

$$
\begin{array}{l l}{{}}&{{\mathrm{Bull~spread~with~payoff}\qquad\{\begin{array}{l l}{{0,+1,0}\}}\\ {{+1,+1,0}\end{array}}}}\\ {{\mathrm{and~buy~a~put~with~}K_{2}(>K_{1})\qquad\{-1,\quad0,0\}}}\end{array}
$$  

Our above ‘trick’ works with puts by starting at the right-hand side, in order to end up with $\{0,+1,0\}$ bull spread profle. In the second line starting with the frst two entries on the right we have 0 followed by $+1$ but we must then continue with the $+1$ to give the full second line as $^{\cdot}\{+1+1,0\}^{\cdot}$ . Then we complete the third line (starting at the right-hand side). We ‘insert’ $\{0,0\}$ in the third line to keep the 0 followed by $+1$ in line-2, unchanged. Then in the third line we include $^{-1}$ , so the frst column in rows 2 and 3, sum to 0 – which gives the payo! for the bull spread, as required.  

# 17.2.3 Bear Spread with Calls  

The payo! here (Figure 17.8) is the mirror image of the bull spread and is undertaken when the investor believes stock prices will fall. The strategy requires a payo! $\{0,-1,0\}$ – the opposite of that for a bull spread.  

$$
{\begin{array}{l l l}{{\mathrm{Bull~spread~with~payoff}}}&{{\underline{{{\{0,-1,}}}}}}&{{0};}\\ {\ =S e l l\ a\ p u t{\mathrm{~with~}}K_{1}}&{{\{0,-1,-1\}}}\\ {a n d b u y\ a\ p u t{\mathrm{~with~}}K_{2}\ (>K_{1})}&{{\{0,}}}&{{0,+1\}}\end{array}}
$$  

![](377ff3b189cde096ecc339436c97613fccbee5761b5bf1c899b0bf77fa930b2c.jpg)  
FIGURE 17.8 Bear spread with calls  

# 17.2.4 Bear Spread with Puts  

A bear spread $\{0,\ -1,\ 0\}$ can also be engineered using puts with di!erent strike prices, as follows:  

$$
\begin{array}{l r}{\mathrm{Bull~spread~with~payoff}}&{\{\begin{array}{l l}{0,-1,}&{0\}}\\ {-B u y\mathrm{~a~put~with~}K_{2}(>K_{1})}&{\{-1,-1,}&{0\}}\end{array}}\\ {a n d s e l l\mathrm{a~put~with~}K_{1}}&{\{+1,\begin{array}{l l}{0,}&{0\}}\end{array}
$$  

Not surprisingly, selling a bull spread would also result in a bear spread.  

# 17.3 STRADDLE, STRANGLE, BUTTERFLY, AND CONDOR  

Another type of money spread can be used when the investor thinks the stock price is likely to change by a substantial amount but she is uncertain about the direction of movement. Here, the investor can make a proft if stock prices move outside a particular range (either up or down) or remain within a particular range. These are often referred to as volatility strategies – we consider straddles, strangles, butterfies, and condors. Before considering how to create these synthetic securities let us examine each of their payo!s (see Figure 17.9).  

There is favourable payo! to the long straddle if the stock price moves up or down from its initial value of $S_{0}=K=102$ by a relatively large amount (i.e. to below 94 or above 110: Figure 17.9, panel A). There is also a limited loss of $\$8$ should price changes turn out to be small and lie between 94 and 110.  

For example, a long straddle might be a sensible investment strategy if there is going to be a ‘yes/no’ decision on a contract bid by a particular frm, or when awaiting a decision on whether a merger with another frm will be allowed to go ahead, or awaiting the outcome of a pharmaceutical company’s licence application to manufacture a new drug. All of these straddles have a positive payo! if there is a subsequent large rise or fall in the stock price, depending on the outcome of these ‘yes/no’ decisions.  

![](5a2298de7117f44e562e1fa190795892c1f79813d0b986eba71ac8759171e782.jpg)  
FIGURE 17.9 Payo!, volatility strategies  

The strangle (Figure 17.9, panel B) has a large payo! if the underlying price moves in either direction by an even larger amount than for the strangle, and the downside risk is limited as indicated by the ‘fat bottom’ – it is a volatility strategy. The short butterfy (Figure 17.9, panel C) and the short condor (Figure 17.9, panel D) limit the upside potential compared with a long straddle or strangle. The short butterfy and short condor each have a positive outcome if stock prices move up or down by a ‘large’ amount, but after a certain point the proft does not increase with further movements in the stock price. Because the payo! to a short butterfy and short condor limit the upside compared with the straddle, they will cost less to set up (in terms of the option premia paid) than the straddle. The above strategies are often undertaken by the trading desks of large institutional investors or by foor traders on the exchange.  

# 17.3.1 Long Straddle  

On 15 April (say) a long straddle involves buying a call $\{0,1\}$ and put $\{-1,0\}$ with the same strike price $K$ (and time to maturity) to give the $\{-1,1\}$ payout profle in Figure 17.9. Assume the options purchased are at-the-money $\begin{array}{r}{\left(S_{0}=K=102\right)}\end{array}$ and both expire in October:  

$$
K=102\qquadP=3\qquadC=5
$$  

The proft outcomes in October from the long straddle are (see Figure 17.10):  

$$
\Pi=\operatorname*{max}(0,S_{T}-K)-C+\operatorname*{max}(0,K-S_{T})-P
$$  

![](6b47cec3b89b1be4decf710a324ea77d36701723f8cd2f9b4dab3472f65ffa79.jpg)  

Long call $(C=5)$ ) plus   
Long put $(P=3)$ equals   
Long straddle  

Relatively slow time decay when there is a long time to maturity but rather vicious time decay in the last month.  

FIGURE 17.10 Long straddle  

$$
\begin{array}{r l}{S_{T}>K}&{\Pi=S_{T}-K-(C+P)}\\ &{\Rightarrow S_{B E}^{+}=K+(C+P)=102+8=110}\\ &{}\\ {S_{T}<K}&{\Pi=K-S_{T}-(C+P)}\\ &{\Rightarrow S_{B E}^{-}=K-(C+P)=102-8=94}\end{array}
$$  

The breakeven stock price is that value of $S_{T}$ which makes $\Pi=0$ . Notice that the breakeven prices are symmetric around the strike price $K=102$ , with $S_{B E}^{+}=110$ and $S_{B E}^{-}=94$ . The ‘gap’ between the breakeven stock prices is $S_{B E}^{+}-S_{B E}^{-}=2(C+P)=16\AA$ , so for at-the-money options the stock price will have to move by plus or minus 8 before the straddle moves into proft. The maximum loss occurs when $S_{T}=K$ since then both the long call and put will not be exercised and the loss equals the sum of the call and put premia $C+P=8$ .  

If $S_{T}$ is above (below) $K$ then the call (put) will be exercised. Although $\Pi$ increases symmetrically as $S_{T}$ increases or decreases (relative to $K$ ), the maximum gain is infnite for $S_{T}>K$ but is limited for $S_{T}<K$ by $S_{T}=0$ (e.g. for $S_{T}=0$ , $\begin{array}{r}{\mathrm{~,~}\Pi=K-(C+P)=94\mathrm{,}}\end{array}$ .  

Note that for a straddle to be proftable the investor must have a view about possible price movements which is more extreme than that held by the ‘average’ of all market participants. This is because if ‘the market’ as a whole expects extreme price movements, this will be refected in a higher value for the volatility of stock returns $\sigma$ and hence higher call and put premia. This implies that the ‘market determined’ breakeven stock prices for the long straddle will be ‘wider’. Hence a speculator, using a long straddle must expect even wider movements in stock prices than does the average market participant.  

The proft from holding a long straddle prior to maturity is given by the curved line in Figure 17.10. If stock prices remain unchanged, then as we get closer to maturity the ‘curve’ moves down towards the $\mathrm{^{*}V}^{\ }$ , but an interesting feature of the straddle is that this movement is slow, until about 1 month before expiry. Hence, if the anticipated large shift in the stock price (in either direction) does not occur until the end of September, the holder of the October long straddle can sell the options a month before the expiration date and the speculator will not have lost much of the initial ‘call plus put premia’ of $\$8$ , she paid in April. In other words, the straddle has relatively slow time decay when there is a long time to maturity but unfortunately it has a rather vicious time decay in the last month of its life. (Maybe this is a metaphor for life in general.)  

Above, we have interpreted ‘volatility’ as an actual movement up or down in stock prices. Now consider what happens to the value of the long straddle if market participants’ perception of stock price volatility $\sigma$ increases (while the stock price remains constant). For example, if market participants think the forecast for future growth in output and profts is unchanged at $3\%$ then there will be no change in stock prices. But increased uncertainty about the outcome of trade negotiations (say) might imply an increase in the forecast volatility of stock returns from $20\%$ p.a. to $23\%$ p.a. (say).  

Since the long straddle consists of a long call and a long put, the value of the long straddle will increase as $\sigma$ increases. In fact, the dashed line in Figure 17.10 will move up (down) as $\sigma$ increases (decreases). To show the change in value of the straddle when both the stock price and implied volatility change requires a three dimensional diagram (see Finance Blog 17.1).  

# 17.3.2 Short Straddle  

It is fairly obvious that a short straddle which involves selling a call and put will have a $\{+1,-1\}$ payo! at expiry that is, an inverted $\mathbf{\Delta}^{\leftmoon}\mathbf{V}^{\rightmoon}$ shape. Providing the stock price at expiry is ‘close to’ the strike price $(S_{T}\approx K)$ an at-the-money short straddle has a positive proft at maturity, equal to the initial receipt of the call and put premia. However, the short straddle is subject to potentially large losses if there is a large rise or fall in stock prices. Perhaps the most famous loss on short straddles is that of Nick Leeson whose total losses on options (and futures) positions caused Barings Bank to go bankrupt with derivatives losses of $\$1.45\mathrm{n}$ (see Finance Blog 17.1).  

By the end of 1994 Nick Leeson, working for Barings Bank (London) but trading from Singapore on the Tokyo exchange, had sold about 35,000 Nikkei 225 straddles – that is, he sold 35,000 puts and 35,000 calls (with the same maturity and strike price). The calls and puts were written on the Nikkei 225 stock market index. Leeson therefore received the call and put premia. These positions were built up over several months and the strike prices were in the range of 18,500–20,000 (on the Nikkei 225 index). He did not report these trades to Barings Bank (as he was o\$cially not allowed to sell options) but hid the trades in his secret ‘error account 88888’. The value of the Nikkei 225 index, underlying these options positions was around $\$70n$ .  

The Nikkei at the end of 1994 had been trading in the range 19,000–20,000. If the Nikkei 225 had remained in its ‘historic range’ then Leeson’s short straddles would earn a proft at maturity. Leeson’s receipts from selling the calls and puts would more than cover any ‘small’ payo!s at maturity to investors holding either the long calls or long puts. This is obvious from the inverted-V payo! for Leeson who held the short straddle. For example, if Figure 17.10 represents a long straddle, then Leeson’s short straddle would be proftable at expiration, providing the stock index does not move more than 8 points in either direction, but the maximum gain to Leeson at expiration is the sum of the call and put premia $C+P$ (if $S_{T}\approx K)$ . However, if the options are held to maturity, and the Nikkei moves in either direction by a large amount, the potential losses to Leeson could be very high since either the calls $(S_{T}>K)$ or the puts $(S_{T}<K)$ could be exercised by the ‘long’.  

![](987c2b4742acfc9d3b31809b39b24b8b63ffc77a0cffb961132c3193148dd236.jpg)  
FIGURE 17.11 Leeson’s short straddle  

Leeson’s short straddle positions change in value day-by-day as the Nikkei 225 stock market index and its volatility change over time, as shown in Figure 17.11.  

Lesson’s short straddle position became very problematic as it resulted in large losses prior to maturity of the options – see Finance Blog 17.1.  

# Finance Blog 17.1 Leeson’s Straddle  

Prior to maturity, as the Nikkei moved outside the 19,000–20,000 range Leeson’s short straddle fell in value (Figure 17.11) and Leeson as the ‘short’ would have to provide increased margin payments. The payo! before maturity is represented by the ‘arch shape’ at the front in Figure 17.11 (the Nikkei 225 index is on the ‘x-axis’). The value of Leeson’s position is on the vertical axis and as the Nikkei 225 index moves up or down (while implied volatility remains constant), the value of Leeson’s position follows this ‘arch shape’.  

On 17 January 1995 the Nikkei was at 19,350 but then the Kobe earthquake struck and by the end of the week the Nikkei was around 18,950 so Leeson’s written puts fell in value and these losses triggered additional margin calls (from the Tokyo exchange). Had Leeson been forced to close out his short straddle he would have crystallised these losses. Prior to expiry, the value of Leeson’s short straddle position is:  

$$
V=N(P+C)
$$  

where $N=-35,000=$ number of written puts calls. The change in value of the straddle position for small changes in the Nikkei 225 is given by the deltas of the calls and puts (see Chapter 16):  

$$
\partial V/\partial S=N(\Delta_{p}+\Delta_{c})
$$  

From put–call parity (for a European option, on a non-dividend paying stock), $(1+\Delta_{p})=\Delta_{c}$ . For example, if the calls and puts are (close to) ATM then we might have $\Delta_{c}=0.51$ , $\Delta_{p}=-0.49$ then $d V=+(0.02)N d S=0.02(-35,000)d S=-700d S$ . Hence Leeson’s position would deteriorate as the Nikkei 225 fell, but the deterioration at frst sight does not look too drastic as the delta of the straddle is small so that a 1 point fall in $d S$ would lead to a 700 fall in value of Leeson’s straddle.  

The short-straddle position falls in value by $\mathrm{\Delta}^{\circ}700\times$ change in the Nikkei 225 index’. But note that delta only gives a frst order approximation for $d V$ which is only accurate for small changes in the Nikkei – and pictorially is represented by the nearly ‘fat top’ of the arch in the above fgure, which has a slope that is very small. It is clear from the above fgure that the actual losses would be much higher if the Nikkei moved substantially – which it did.  

This illustrates the danger in using the ‘delta approximation’ to calculate the change in value of an option’s position – using a delta-gamma-vega approximation to the change in value of the straddle would be more accurate and we deal with this in Chapter 27.  

After the Kobe earthquake the increased uncertainty about the future course of the Japanese economy, increased traders’ perceptions of future volatility $\sigma$ (of the Nikkei 225) and this immediately caused an increase in both call and put premia (see Chapter 16). Hence Leeson’s written calls and puts experienced additional (mark-to-market) falls in value (see the volatility axis in Figure 17.11). This is known as vega risk.  

As Leeson’s mark-to-market losses on his short straddle became larger, the clearing house (in Tokyo) asked for additional margin payments which Barings did not provide and Leeson’s straddle positions were closed out at a loss (by the clearing house). This was part of the reason Barings Bank went bust.  

Source: Adapted from Cuthbertson and Nitzsche (2001).  

# 17.3.3 Long (Buy) Strangle  

This strategy is very similar to the long straddle except the long call and put have di!erent strike prices, which gives a $\mathrm{v}$ -shaped proft profle but with a ‘fat bottom’ between the two strike prices. If $K_{0}$ is the strike in a straddle, then a long strangle involves buying a call with $K_{c}>K_{0}$ and buying a put with $K_{p}<K_{0}$ . Because the calls and puts in a strangle are more out-of-the-money than in the straddle, the strangle costs less than the straddle. The payo! for a long strangle is $\{-1,0,1\}$ which gives a fat-bottomed ‘bucket shape’ (see Figure 17.12).  

$$
{\begin{array}{r l r}&{{\mathrm{Long~strangle~with~payoff}}\quad}&{{\frac{\left\{-1,0,+1\right\}}{\left\{-1,0,\right.0\}}}}\\ &{={\mathrm{Buy~put~with~}}K_{p}\quad}&{{\left\{-1,0,0\right\}}}\\ &{+\ {\mathrm{Buy~at~call~with~}}K_{c}(>K_{p})\quad}&{\left\{\begin{array}{r l r}{0,0,+1\}}&{}\end{array}\right.}
$$  

The breakeven stock prices are:  

$$
\begin{array}{r l}&{\mathrm{for}S_{T}>K_{c}:S_{T}-K_{c}-(C+P)=0\Rightarrow S_{B E}^{+}=K_{c}+(C+P)}\\ &{\mathrm{for}S_{T}<K_{p}:K_{p}-S_{T}-(C+P)=0\Rightarrow S_{B E}^{-}=K_{p}-(C+P)}\end{array}
$$  

The ‘gap’ between the breakeven points for the strangle is $S_{B E}^{+}-S_{B E}^{-}=K_{c}-K_{p}+2(C+P)$ and this is greater than that for the straddle, $S_{B E}^{+}-S_{B E}^{-}=2(C+P)$ . T퐵h,us although the strangle costs less than the straddle, the stock pri퐵c,e has퐵f,urther to move before the strangle is in-the-money.  

The strangle has one positive feature relative to the straddle. It can be shown that the strangle increases in value by the same amount as the straddle, as implied volatility $\sigma$ increases, but the strangle costs less at the outset. The strangle is therefore ‘better value’ than the straddle if you are speculating on an increase in volatility.  

![](66b1b25132f3986a12fbbf84c8ba8ffcb6f0ceec0d48fb58375afdc4441d7738.jpg)  
FIGURE 17.12 Long strangle  

# 17.3.4 Short Butterfly  

A butterfy spread is another variant on the straddle – it is a V-shape with ‘wings’. A short butterfy can be ‘engineered’ entirely from calls: selling one call at a low strike, buying two calls at the middle strike and buying one call at the highest strike price. This gives a payo! profle of $\{0,-1,1,0\}$ , see Figure 17.13.  

A proft is made if the stock price either increases or decreases by a substantial amount – it is a volatility strategy but has a limited upside (whichever direction stock prices move). The short butterfy requires:  

$$
\begin{array}{l l}{{}}&{{\mathrm{Short~butterfly~with~payoff}\quad\underbrace{\{0,-1,+1,\:0\}}_{\displaystyle\{0,-1,-1,-1\}}}}\\ {{}}&{{=\mathrm{Sell~a~call~with~}K_{1}\qquad}}\\ {{}}&{{+\mathrm{Buy~a~call~with~}K_{2}(>K_{1})\quad\{0,\:\:0,+1,+1\}}}\\ {{}}&{{+\mathrm{Buy~a~call~with~}K_{2}(>K_{1})\quad\{0,\:\:0,+1,+1\}}}\\ {{}}&{{+\mathrm{Sell~a~call~with~}K_{3}(>K_{1})\qquad\{0,\:\:0,\:\:0,-1\}}}\end{array}
$$  

That is, sell two ‘outer-strike price’ call options $(K_{1},K_{3})$ and purchase two ‘inner-strike price’ call options (with strike price, $K_{2}$ ).  

Sell call at $\boldsymbol{K}_{1}$  

Buy 2 calls at $K_{2}$  

Sell 1 call at $K_{3}$  

# equals  

Short butterfly  

![](4647267bc1fa3c786778cde7fd43dd4f599855d13f8902b5ef053007885075e9.jpg)  
FIGURE 17.13 Short butterfy  

The payo! profle when the options are not close to expiration is the almost fat dashed line at the bottom of Figure 17.13 – hence the butterfy spread does not change in value by much, when the stock price changes (that is, the delta of the butterfy is close to zero). When the options are close to the expiration date, the short butterfy loses time value rather quickly.  

Also, the payo! profle before maturity is almost invariant to changes in implied volatility. This is because for long-dated options, vega does not change very much with the stock price and hence the positive vega of the two purchased options will almost exactly o!set the negative vega of the options sold (see Chapter 28 for a detailed discussion of vega). Hence if you wish to speculate on changes in volatility $\sigma$ , you would use straddles and strangles rather than butterfy spreads.  

A short butterfy can also be replicated with puts. Again, selling two ‘outer strike’ puts and purchasing two ‘inner strike’ puts we obtain:  

Short butterfy with payo! $\begin{array}{r}{\frac{\{\quad0,-1,+1,\ 0\}}{\{+1,+1,+1,\ 0\}}}\\ {\{-1,-1,\quad0,\ 0\}}\\ {\{-1,-1,\quad0,\ 0\}}\\ {\{+1,\quad0,\ 0,\ 0\}}\end{array}$   
$\mathbf{\tau}=\mathbf{S}\mathbf{e}\mathbf{l}\mathbf{l}$ with $K_{3}$   
$+$ with $K_{2}$   
$+$ with $K_{2}$   
$+\mathrm{Sell}$ with $K_{1}$  

# 17.3.5 Long Butterfly  

A long butterfy spread has the shape given in Figure 17.14 and can be engineered from either calls or puts by ‘reversing the trades’ for the short butterfy, given above.  

A long butterfy spread can also be constructed from bull and bear spreads:  

long call bull spread $\mathbf{\tau}=$ buy $K_{1}$ -call and sell $K_{2}–c a l l=\{0,+1,0,0\}$   
plus   
long call bear spread $\mathbf{\tau}=$ buy $K_{3}$ -call and sell $K_{2}–c a l l=\{0,0,-1,0\}$   
equals   
long butterfy $\{0,+1,-1,0\}$  

![](6b04dd3b00e84637e8a11e5faea6c5f1539981fa6d7c8392d69f3d9def58b082.jpg)  
FIGURE 17.14 Long butterfy  

# 17.3.6 Short Condor  

This is similar to the short butterfy (Figure 17.13) but with a ‘fat bottom’ and a proft profle of $\{0,-1,0,+1,0\}$ . The ‘fat bottom’ is obtained by replacing the two ‘central options’ with the same strike price $K_{2}$ in the butterfy, with two options with di!erent strike prices – this fattens the ‘V-shape’ of the short butterfy – see Figure 17.9d. (This is similar to the relationship between the straddle and the strangle.) A short condor with calls is constructed as follows:  

<html><body><table><tr><td>Short condor with payoff</td><td>{0,-1，0,+1, 0}</td></tr><tr><td>= Sell a call at K</td><td>{0,-1,-1, -1, -1}</td></tr><tr><td>+Buy a call at K(> K)</td><td>{0，0,+1，+1,+1}</td></tr><tr><td>+Buy a call at K(> K)</td><td>{0， 0，0,+1，+1}</td></tr><tr><td>+Sell a call at K4(> K)</td><td>{0, 0, 0， 0，-1}</td></tr></table></body></html>  

Specifcally, a short condor with calls involves selling a call at the lowest strike $K_{1}$ , buying a call at a higher strike $K_{2}$ , buying another call at the next strike $K_{3}$ and selling a call at the highest strike $K_{4}$ . To see how you engineer a short condor with puts use our above ‘trick’ by starting at the right-hand side, of the short condor payo! $\{0,-1,0,+1,0\}$ . You will fnd that a short condor with puts requires the same position in puts as given for calls above – try it.  

A condor costs about the same as the equivalent butterfy and the gap between their respective breakeven points and the maximum gain possible are similar. The maximum loss for the short condor occurs over the range of stock prices between the middle strikes (see Figure 17.9d), rather than at a single point as with the butterfy. The value of the condor prior to maturity behaves similarly to that of the butterfy, noted above.  

# 17.4 HORIZONTAL (TIME, CALENDAR) SPREADS  

All of the above strategies are ‘vertical spreads’ which are constructed from options with di!erent strike prices but all have the same maturity date. Horizontal or time spreads have options with di!erent maturity dates but the same strike price. A horizontal spread cannot be held until both options expire (because the short maturity option will have expired some time before the longer maturity option!). Because the long-maturity option will have time value when the ‘nearby option’ reaches maturity, the expected payo! from horizontal (time) spreads depends on the specifc options used. There are no general rules we can apply here.  

However, consider a simple case of buying a long-dated ( $T_{L}=360$ -days) call option for $C_{L}$ and selling a short-dated option $T_{S}=180$ -days) at $C_{S}$ where both options are at-the-money (i.e. $K={\cal S}_{0}\dot{}$ ). The cost of setting up the calendar spread will be positive, since $C_{L}>C_{S}$ . The time decay will be positive for the short-dated option and negative for the long-dated option.  

But the positive time decay of the short-dated option is faster than for the long-dated option, so the spread will make money as time passes (Figure 17.15, dashed line) – as long as the stock price does not change over time $S_{t}\approx S_{0}\approx K$ .  

The proft profle of a calendar spread is usually shown when the short-maturity option matures and it is assumed that the long maturity option is then closed out. The proft at expiration of the calendar spread is the solid curved line (Figure 17.5) and shows that if $S_{T}\approx S_{0}\approx K$ the (calendar) spread-investor makes a proft but if the stock price is well above or below the strike price the investor makes a loss.  

At maturity of the short-dated option, the long-dated option still has 180 days to maturity. First consider what happens at expiration on the short-maturity option if $S_{T}\approx S_{0}\approx K$ . The short call is worth virtually nothing but the long maturity call is quite valuable because of its positive time value – so the calendar spread makes a proft. If $S_{T}\gg K$ then the short call option (which is exercised by the long) costs the investor $S_{T}-K$ . But the long call is also close to being worth $S_{T}-K$ (plus some positive time value). Overall when the investor in the calendar spread closes out she makes a payo! of zero but there is a net loss which is about equal to the initial cost of setting up the spread (i.e. $C_{L}-C_{S})$ . If $S_{T}\ll K$ when the short maturity option expires, then the short-maturity call option is worthless and the value of the long maturity call option (which is also well out-of-the-money) is also close to zero. In this case, the investor in the calendar spread makes a net loss which is close to the cost of setting up the spread. This explains the payo! profle for the outcomes at maturity of the short-dated call which are represented by the solid line in Figure 17.15.  

To summarise. In a relatively static market (i.e. stock price does not change $S_{t}\approx S_{0}\approx K)$ the horizontal call-spread will make money from time decay. However, it will lose money if the stock price moves substantially either side of its initial value, $S_{0}$ (Figure 17.15). Calendar spreads can be created with put options and buying a long-maturity put and selling a short-maturity put gives a proft profle similar to that when using calls.  

![](54a3ab4022775d07c775db2bebd472f1db8f4c2e8e4f3af5042ce64cf5b91b7e.jpg)  
Calendar Spread: A long position in a 360-day option and a short position in a 180-day option, both at-the-money.   
FIGURE 17.15 Calendar spread (proft profle)  

# 17.5 SUMMARY  

• Combinations of di!erent options can be used to set up positions which have a wide variety of alternative payo! structures.   
• Bull and bear spreads using (stock) options are directional bets – the investor is gambling on the stock price either rising (bull spread) or falling (bear spread). For both strategies losses and gains are capped.   
• Straddles, strangles, butterfy spreads, and condors (on stock options) are bets on the movement of stock prices in either direction – they are volatility bets.   
• A long straddle or strangle may have a substantial positive proft if there is either a large rise or fall in the stock price – but losses are limited to the cost of buying the options.   
• A short straddle or strangle has a positive proft if the stock price does not change much in either direction but can result in large losses if the stock price either rises or falls by a large amount.   
• Short butterfy spreads and short condors have positive profts if the stock price moves in either direction by a large amount, but results in losses if the stock price changes by a small amount, in either direction. For both the short butterfy and condor, losses and gains are capped. Long butterfy spreads and long condors have the opposite (‘mirror image’) proft profles to their respective short positions.   
• All options strategies can lead to gains or losses ‘second-by-second’ if either the stock price changes or volatility changes.  

# EXERCISES  

# Question 1  

What is a long straddle and why might you hold this position to maturity?  

# Question 2  

You construct a long straddle by buying an at-the-money (ATM) call and an ATM put (both with the same underlying asset, strike price and time to maturity). Is the e!ective delta of this straddle large or small? Does the delta imply the straddle is not very risky?  

# Question 3  

A long strangle has a payo! profle of $\{-1,0,+1\}-$ a ‘bucket shape’. Show how you can construct a long strangle and algebraically derive the break-even stock price.   
Draw the payo! diagram for $C=5$ , $P=3$ , $S_{0}=100$ , $K_{\mathrm{p}}=90$ (put) and $K_{\mathrm{c}}=105$ (call), when $S_{T}>K_{\mathrm{c}}$ and $S_{T}<K_{\mathfrak{p}}$ .  

# Question 4  

You expect the stock market to rise over the next 3 months. What are the advantages and disadvantages of buying (i) a call (with a low strike price, $K_{1}$ ) versus buying (ii) a (call) bull spread (with strikes $K_{1}<K_{2}$ )?  

# Question 5  

How do you set up a long straddle and a short butterfy spread? Qualitatively, how are the outcomes di!erent at maturity and is this intuitively reasonable? More specifcally, explain how the butterfy costs you less, but potentially it gives you less at maturity.  

# Question 6  

A put option with a strike $K_{1}=35$ , costs $P_{1}=\S4$ and a put with a strike of $K_{2}=40$ costs, $P_{2}=\$8$ . How can you construct a bull spread using these puts?  

What are the payo!s and profts from the strategy?  

For di!erent values of the stock price at maturity: $S_{T}>K_{2}$ , $K_{1}>S_{T}>K_{2}$ and $S_{T}<K_{1}$ show the payo!s from the bull spread (with puts) and also show the profts from the strategy and the breakeven stock price. Put your results in the following table.  

<html><body><table><tr><td>ST<K = 35</td><td>K>ST> K</td><td>ST > K = 40</td></tr><tr><td>Payoff long K put</td><td></td><td></td></tr><tr><td>Payoff short K2 put</td><td></td><td></td></tr><tr><td>Payoff bull spread</td><td></td><td></td></tr><tr><td>Option premia</td><td></td><td></td></tr><tr><td>Profit</td><td></td><td></td></tr></table></body></html>  

# Question 7  

You purchased a (call) bull spread some time ago. Later you note that the bull spread is currently well ‘in-the-money’ and has positive value. Would you gain or lose by holding on a bit longer before closing out, if you felt the stock price (as well as volatility, interest rates etc.) would remain unchanged?  