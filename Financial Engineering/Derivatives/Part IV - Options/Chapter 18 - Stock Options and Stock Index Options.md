---
tags:
  - dynamic_hedging
  - protective_put
  - ratio_spread
  - stock_index_options
  - stock_options
aliases:
  - Covered Call
  - Options on Stocks
  - Protective Put
  - Ratio Spread
  - Static Hedge
key_concepts:
  - Dynamic delta hedging
  - Mispriced options profit
  - Protective put strategy
  - Risk-free portfolio creation
  - Stock options and indexes
---
# Stock Options and Stock Index Options  

# Aims  

• To examine stock options and stock index options.   
• To show how you can provide a minimum (foor) value for a portfolio of stocks but also be able to capture most of the ‘upside’ if stock prices rise – this is a protective put.   
• To show how you can hedge a portfolio of stocks using dynamic delta hedging.   
• To show how several options (on the same underlying asset) can be combined to give a risk-free portfolio – this is a ratio spread.   
• To demonstrate how you can make a proft from mispriced options, while hedging any changes in market risk.  

We have seen in Chapter 17 that investors can use stock options to speculate on the direction of stock price changes and on changes in the volatility of stock returns. Investors can also insure or hedge a cash market position consisting of stocks held in a specifc frm (e.g. 50,000 stocks in AT&T) or in certain specifc industries (e.g. oil industry) or in a ‘market portfolio’ (e.g. S&P 500) by using various types of stock index options. First we discuss hedging using options on individual stocks and then using stock index options.  

# 18.1 OPTIONS ON STOCKS  

If you hold a number of stocks in one particular company (e.g. AT&T) you can alter or eliminate the (market and specifc) risk, using options on this stock.  

# 18.1.1 Static Hedge: Covered Call  

A static hedge assumes the initial options positions are held to maturity. Suppose an investor holds AT&T stocks. She can ofset some of the downside risk by writing (selling) a call – this is a covered call strategy. Downside risk is reduced slightly because the investor receives the call premium:  

$$
\begin{array}{l l}{{\mathrm{Long\stock}}}&{{\{+1,+1\}}}\\ {{\mathrm{+Short\call}}}&{{\{\ 0,-1\}}}\\ {{\mathrm{=Covered\call\payoff}}}&{{\{+1,0\}}}\end{array}
$$  

Figure 18.1 shows the payof to a covered call with $C=\$3$ , $K=\$25$ and an initial stock price $S_{0}=\$24$ . The proft at maturity, is given by:  

$$
\begin{array}{c}{{\Pi=S_{T}-S_{0}-m a x(0,S_{T}-K)+C}}\\ {{{}}}\\ {{=S_{T}-S_{0}+C\quad\mathrm{for}\:S_{T}<K}}\end{array}
$$  

$$
S_{B E}=S_{0}-C=\S24-\S3=\S21
$$  

$$
\Pi=K-S_{0}+C=\S4\quad\mathrm{for}\:S_{T}>K
$$  

For $S_{0}=\$24$ the downside risk is reduced by the amount of the call premium of $\$3$ to a breakeven of $\$21$ . However, the upside potential is considerably reduced – the maximum proft is $K-S_{0}+C=\S4$ .1  

![](1b348ce551dee89b762d4c9979e4cdaf8678827cb5ae2003efb1f2497781e795.jpg)  
FIGURE 18.1 Covered call  

# 18.1.2 Static Hedge: Protective Put  

An investor can protect her long stock position but without sacrifcing all the upside potential (of holding stocks) by buying a put – this is a protective put (Figure 18.2) also sometimes called a ‘guaranteed bond’ – see Chapter 15.  

$$
\begin{array}{l l}{{\mathrm{Long\stock}}}&{{\{+1,+1\}}}\\ {{\mathrm{~}+\mathrm{Long\put}}}&{{\{-1,\ 0\}}}\\ {{\mathrm{~}=\mathrm{Protective\put}}}&{{\{0,+1\}}}\end{array}
$$  

The payof profle for the protective put is the same as for a long call. (This is put–call parity again.) Suppose $S_{0}=\$24$ and the put has $K=\$25$ and $P=\$5$ . The proft from the protective put is:  

$$
\Pi=S_{T}-S_{0}-P\mathrm{for}S_{T}\geq K
$$  

and $S_{B E}=S_{0}+P=\mathbb{S}29$  

$$
\begin{array}{c l}{{\Pi=S_{T}-S_{0}+(K-S_{T})-P\quad\mathrm{for}S_{T}<K}}\\ {{}}&{{}}\\ {{=K-S_{0}-P=-4}}\end{array}
$$  

As can be seen in Figure 18.2 the protective put has a lower limit (a ‘foor’) on losses but allows most of the upside capture. The protective put is an insurance contract – in return for the put-premium, a minimum value for the stock is guaranteed at maturity. (Note that for an at-the-money put $K=S_{0}$ , so the ‘foor value’ would be the current value of the stock.)  

![](9122d3b3848b14a1ba37c17aa13fb82724f1f566f34e3bf08a81217a786dc83b.jpg)  
FIGURE 18.2 Protective put  

# 18.1.3 Delta Hedging a Stock Portfolio with Puts  

The static protective put does not ensure that the value of the portfolio remains unchanged at all times. Instead, it ensures a minimum value $(=K)$ for the stock $^+$ put portfolio, at maturity of the option contract. However, it is possible to continuously hedge a stock put portfolio. We require any change in the cash-market value of the stocks to be ofset by changes in the value of the puts. Suppose you hold $N_{s}$ stocks (of AT&T) with price $s$ , with $\$8$ -value $V_{s}=N_{s}S$ . A portfolio of $N_{s}$ stocks plus $N_{p}$ puts is worth:  

$$
V=N_{s}S+N_{p}\phi P
$$  

where $\phi=100$ is the number of stocks underlying each put contract. A dynamically hedged portfolio has to satisfy:  

$$
\partial V/\partial S=N_{s}+N_{p}\phi\Delta_{p}=0
$$  

$$
\Rightarrow N_{p}=-\frac{N_{s}}{\phi\Delta_{p}}=-\frac{V_{s}}{(100\:S)\Delta_{p}}
$$  

If you are long stocks $V_{s}>0$ then as $\Delta_{p}<0$ , the hedge portfolio consists of buying $N_{p}$ puts. The term $\cdot_{100\ S^{\prime}}$ is the dollar value of the 100 AT&T stocks deliverable in each put contract. Suppose the investor is long $N_{s}=800$ stocks at $S=\$10$ , so that $V_{s}=\$8,000$ and assume $\Delta_{p}=$ $-0.4$ . Then $N_{p}=20$ put contracts should be purchased to hedge against (small) changes in the stock price. As the option’s delta changes (because of changes in $S,r,\sigma$ , and $T$ ), the number of put option contracts to maintain the delta hedge needs rebalancing over time.  

A dynamic hedge for a portfolio of stocks on AT&T using puts, can eliminate the market and specifc risk of the AT&T stocks. As the put-delta is only valid for small changes in the stock price, the value of the stock $^+$ put portfolio is not hedged against large changes in stock prices (gamma risk) or changes in volatility (vega risk) – these issues are elaborated on in Chapter 28.  

# 18.1.4 Ratio Spread  

If you already hold a position in options then you can create a ‘delta neutral’ (i.e. risk-free) options portfolio by combining two (or more) options (on the same underlying asset). The latter possibility also gives rise to a ratio spread whereby traders attempt to make profts from mispriced options (on the same underlying asset).  

The analysis below applies to both calls and puts. Two stock options (both on the same underlying) might have diferent deltas because they have diferent strike prices or maturity dates. Each option contract is for delivery of $\phi=100$ stocks. The value of a portfolio consisting of $N_{A}$ holdings of option-A and $N_{B}$ holdings in option-B (on the same underlying) if the option prices are $f_{A},f_{B}$ is:  

$$
V=(N_{A}f_{A}+N_{B}f_{B})\phi
$$  

For a zero change in value of the options portfolio:  

$$
\begin{array}{c}{{\partial V/\partial S=0\Rightarrow\quad N_{A}\Delta_{A}+N_{B}\Delta_{B}=0}}\\ {{N_{A}=-(\Delta_{B}/\Delta_{A})N_{B}}}\end{array}
$$  

Suppose we already hold a naked position in $N_{B}=10$ (long) call options, with $\Delta_{B}=+0.5$ and we are worried about the risk to our options position from small changes in the stock price. If another call option (on the same underlying) has $\Delta_{A}=+0.25$ , then a ‘delta neutral’ portfolio requires $N_{A}=-20$ that is, short 20 calls of option-A. (But if option-A is a put option with $\Delta_{A}=-0.25$ , the delta-neutral position would involve buying $N_{A}=20$ put options-A).  

# 18.1.5 Underpriced Options  

Consider a trader Ms Long, who thinks that call option-B (on Boeing stocks) with $\Delta_{B}=0.5$ is under-priced by $1\%$ because of stale price quotes. To take advantage of the under-pricing Ms Long could today buy $N_{B}=10$ of options-B, hoping to close out later at a $1\%$ proft – after the mispricing is corrected.  

But if the stock market as a whole falls (i.e. S&P 500) then the price $S_{B}$ of Boeing stock will also fall, which would produce a fall in the price of call option-B (written on Boeing), and this might eliminate any proft due to Ms Long’s position in the ‘underpriced’ option-B.  

In Chapter 16 on delta hedging we noted that Ms Long could create a delta-neutral portfolio by short-selling $N_{s}=0.5(10)=5$ stocks of Boeing. If option-B is correctly priced then the hedge position does not change in value (for small rises or falls in $S_{B}$ ). So the delta-hedge protects the value of the (option- $^{\cdot\mathrm{B}+}$ Boeing-stocks) portfolio, while the investor waits for the option-B’s mispricing to be corrected.  

But if, as Ms Long believes, option-B is under-priced then when the mispricing is corrected, option-B’s price will rise by $1\%$ more than implied by the hedge $\phantom{}^{'}d C_{B}=\Delta_{B}d S_{B})$ , Hence, when Ms Long closes her positions in option-B and stocks-B she earns a proft of $1\%$ , even if $S_{B}$ has fallen due to a fall in the market (S&P 500) index.  

To undertake the above arbitrage transaction requires short-selling stock-B.2 This may not be possible because of the ‘uptick rule’ (i.e. in the US you are only allowed to short-sell if the last quote was a price rise), and may be expensive to implement because of high transactions costs (e.g. $50\%$ margin on short-selling in the US plus any ‘haircuts’ demanded by the broker from whom you borrow the stocks and also the risk of a ‘short-squeeze’). However, all is not lost.  

The trader can exploit $N_{B}=10$ under-priced calls (on Boeing) by simultaneously selling $N_{A}=(\Delta_{B}/\Delta_{A})N_{B}=20$ call options-A (also on Boeing) but with diferent strikes or time to maturity and hence a diferent delta, $\Delta_{A}=+0.25,$ . This is a ratio spread.  

If option-A and option-B (both on Boeing) are correctly priced, the ratio spread provides a hedge (for small changes in the stock price of Boeing). However, given that option-B is actually under-priced by $1\%$ , the ratio spread makes a riskless proft of $1\%$ , when option-B eventually rises to its correct (fair) value given by Black–Scholes.3  

# 18.2 STOCK INDEX OPTIONS (SIO)  

Stock index options (SIO) are frequently used to hedge the market (systematic) risk of a diversifed portfolio of stocks. A fund manager using index options can either obtain insurance or can dynamically hedge the market risk of her portfolio of stocks.  

# 18.2.1 Contract Specification  

We focus on the S&P 100 (American style) and the FTSE 100 (European-style) contracts. The S&P 100 (American) index option is often referred to by its ticker symbol (OEX) and is the most actively traded option on CBOE. SIO are settled in cash. If $z$ is the dollar-value of one index point and the current stock index is $s$ , then the dollar-value of the S&P index is $V_{I}=z S$ . For S&P 100 index options, $z=\$100$ (Table 18.1), hence if the S&P 100 index is $S=1{,}000$ , then $V_{1}=\$100,000$ . Put slightly diferently, if the S&P 100 index changes by one point (e.g. from 1,000 to 1,001) then this implies a change in the value of the S&P index of $\$100$ .  

TABLE 18.1 S&P 100 (American-OEX) Index Option (CBOE)   


<html><body><table><tr><td>Unit of trading:</td><td>$100 × S&P 100 Index</td></tr><tr><td>Expiry month:</td><td>Four, near term months (plus one additional month from the March quarterly cycle)</td></tr><tr><td></td><td>Min. price movements: For an option trading below 5, the minimum tick is 0.05 ($5) and for all other series 0.10 ($10)</td></tr><tr><td>Tick size (& value):</td><td>Either 0.05 ($5)or 0.10 ($10)</td></tr><tr><td>Exercise:</td><td>American. May be exercised on any business day before the maturity date. European also available.</td></tr><tr><td>Settlement day:</td><td>Cash settled based on closing index value on the business day of exercise</td></tr><tr><td>Last trading day:</td><td>Business day preceding the expiration date</td></tr><tr><td>Settlement:</td><td>In cash, based on (S - K)+ × $100 for α long call and (K - S)+ x $100 for c long put.</td></tr></table></body></html>

Source: CBOE website.  

The ‘settlement price’ $S_{T}$ is the index value at the market close. If, at maturity $S_{T}=1\mathrm{,000}$ (index points) and the strike price in a put contract is $K=1{,}100$ (index points), then the holder of a long put receives:  

$$
\mathcal{S}\mathrm{-}P a y o f f o r o n e p u t=z\left(K-S_{T}\right)=\mathfrak{H}00\left(1,100-1,000\right)=\mathfrak{H}10,000
$$  

Call and put premia are quoted in terms of index points. Suppose a quote for the S&P 100, March-950 call is $C=38$ (index points). This implies that one call contract costs $\$3,800$ $\mathrm{\Phi}(=\$100\times38)$ , hence:  

$$
I n\nu o i c e p r i c e o f o n e S\&P\mathrm{\}l00\mathrm{\}C a l l=C z
$$  

Index options are also available on the S&P 500 (a European-style option traded on CBOE), the Major Market Index (traded on AMEX) and the Value Line Index (traded on PHLX) and the NYSE-Composite (traded on NYSE). In the US there are also index options available on industry indices (e.g. oil, utilities).  

For the FTSE 100 (European Style) index option (Table 18.2) the value of an index point is set at $z=£10$ . So if the FTSE 100 index is at 6,500 then the value of the index is $V_{1}=£65,000$ . Quotes for option premia are in index points. For example, the April-6500 put on the FTSE 100 (European Style) index option, quoted at $P=63$ would have an invoice price of £630 $\stackrel{\prime}{=}£10\times63\$ .  

# 18.2.2 Static Hedge Using Stock Index Options: Protective Put  

Suppose you hold a stock portfolio-A with current value $V_{A}=\mathbb{S}1\mathrm{m}$ , whose composition mirrors the S&P 100 $(\beta_{A}=1)$ and want to protect its value in 1 year’s time. You fear a price fall so you buy index puts with maturity $T=1$ year. This is a protective put. If the S&P 100  

TABLE 18.2 FTSE 100 (European) Index Option   


<html><body><table><tr><td>Unit of trading:</td><td>10 per index point</td></tr><tr><td>Expiry month:</td><td>March, June, September, December (plus additional months so that the nearest 3 calendar months are always available for trading)</td></tr><tr><td>Min.price movements: 0.5 (index point)</td><td></td></tr><tr><td>Tick size (&value):</td><td>0.5 (5) (Min. block trade is 500 contracts)</td></tr><tr><td>Exercise:</td><td>By 18.30 on last trading day only</td></tr><tr><td>Settlement day:</td><td>1st business day after maturity date</td></tr><tr><td>Last trading day:</td><td>10.15 (London time) on 3rd Friday of expiry month</td></tr></table></body></html>

Source: ICE-Intercontinental Exchange website.  

index currently stands at $S_{A}=1\mathrm{,000}$ index points, then to insure a diversifed portfolio of stocks (with $\beta_{A}=1\mathbf{\dot{\Omega}}.$ ), the number of puts required is (see Appendix 18.A):  

$$
N_{p}=\frac{\S-\nu a l u e\ o f s t o c k\ p o r t f o l i o}{\S-\nu a l u e\ o f s t o c k\ i n d e x}\beta_{A}=\frac{V_{A}}{z S_{0}}\ \beta_{A}=10
$$  

To insure your stock portfolio at $T$ from all downside risk (given $\beta_{A}=1\mathrm{\i}$ ) you need to choose ATM-puts with a strike price $K=1{,}000$ . At $T_{:}$ , if you lose on your stock portfolio you want to be fully compensated by the payof from the puts. If the S&P 100 index falls $20\%$ to $S_{T}=800$ , then the value of your stock portfolio falls by $\$200,000$ . But if you exercise the puts you make a proft of 200 index points $\left(=K-{S_{T}}\right)$ per contract and with 10 contracts the dollar payof is $\$200,000$ $00\left(=10\times200\times\$100$ point . The loss on the stock portfolio over the year is exactly ofset by the payof to the puts. If the put premium paid was $P=30$ index points, the 10 put contracts cost $\$30,000$ $(=10\times\$100\times30$ points which is the cost of the insurance.  

Let’s take a slightly more complex case, where $\beta_{A}=1.2$ so that $N_{p}=12$ . The key factor is the choice of strike price in the put. If the S&P 100 index currently stands at $S_{0}=1\small{,}000$ and you choose a strike of $K=900$ , this implies you are willing to accept a fall in the market index of $10\%$ . Hence, the maximum acceptable fall in the value of your stock portfolio is $12\%$ $(=1.2\times10\%)$ that is $\$120,000$ .  

Suppose the S&P 100 index falls by $20\%$ to $S_{T}=800$ index points, so your stock portfolio falls by $24\%$ , $(=\$240,000)$ . The payof to the puts is ${\$120,0000}\left({=12\mathrm{puts}\times(K-S_{T})\times\S100}\right)$ hence, the net outcome from the protective put strategy is a loss of $\$120,000$ . This is exactly the loss you were willing to incur when choosing a strike of $K=900$ at the outset.  

If the S&P index rises (above $K$ ) you do not exercise the puts but the value of your stock portfolio has increased. In this case the ‘insurance’ provided by the put was not needed but of course insurance does not come ‘free’ – as you pay the put premium. This is a static stock-put hedge because we have assumed the option contract is held to maturity. It provides a ‘foor’ for the value of the stock portfolio but also allows most of the upside potential.  

# 18.2.3 Dynamic Delta Hedge Using Stock Index Options  

Assume you hold $V_{A}$ (dollars) in a diversifed stock portfolio-A with beta $\beta_{A}$ (with respect to the S&P 100 ‘market index’). The change in value of portfolio-A is $d V_{A}=V_{A}R_{A}$ . To preserve the value of our stock portfolio over a small interval of time, we use a dynamic hedging strategy of stocks $+$ puts. It can be shown (see Appendix 18.B) that the number of index puts to delta-hedge stock portfolio-A is:  

$$
N_{p}=-\frac{V_{A}}{z S_{0}}\left(\frac{\beta_{A}}{\Delta_{p}}\right)=\frac{V_{A}}{z S_{0}}\left(\frac{\beta_{A}}{|\Delta_{p}|}\right)
$$  

Equation (18.11) implies that if you are long a portfolio of stocks, then to delta-hedge you go long $(\mathsf{b u y})N_{p}$ index puts. Note that the cost of setting up the protective put is $N_{p}(z P)$ and  

there will be transactions costs of rebalancing the portfolio as the delta of the option changes over time. We discuss dynamic hedging in Chapter 27.  

# 18.3 SUMMARY  

• Options are available on individual stocks (e.g. AT&T, Coca-Cola), broad groups of stocks (e.g. index of oil stocks) and on broad market indexes (e.g. S&P 100, S&P 500, FTSE 100, Russell 2000).   
• A static stock-put hedge provides a minimum (foor) value for a portfolio of stocks and also allows upside gains if stock prices are high, at maturity of the option.   
• A dynamic stock-put delta hedge ensures that any gains (losses) on the stock portfolio over a small interval of time are ofset by losses (gains) on the puts. Hence, over a small interval of time there is no change in the value of the ‘stock $^+$ put’ portfolio. A dynamic delta hedge requires frequent rebalancing.   
• Ratio spreads allow traders to delta hedge an existing option position using ‘other’ options with diferent strikes or time to maturity (but on the same underlying asset). If an option is mispriced, then a ratio spread can be used to hedge the position, while waiting for the mispricing to be corrected.  

# APPENDIX 18.A: STATIC HEDGE: INDEX PUTS  

You have $V_{A}=\$10$ in portfolio-A of stocks, with $\beta_{A}=1.2$ . If the S&P 100 stock index is currently $S_{0}=1\small{,}000$ and you choose an index put with a strike $K=900$ , this implies the acceptable maximum dollar-loss on your portfolio of stocks is $V_{A}\beta_{A}(K-S_{0})/S_{0}=\mathfrak{G}120,000$ (and hence the minimum (foor) value required is $\$880,000$ .  

To calculate $N_{p}$ consider the outcome at maturity of the put. If the S&P 100 stock index falls to $S_{T}=800~(<K)$ (at expiration of the put option) then the actual loss on your stock portfolio is $V_{A}\beta_{A}(S_{T}-S_{0})/S_{0}=\mathbb{{\mathbb{S}}}240,000$ . The payof from $N_{p}$ index puts is $N_{p}(K-S_{T})z$ where $z=\$100$ per index point. Hence, for $S_{T}<K$ we choose the number of puts so that:  

Actual loss stock portfolio $^+$ payof from puts $\b=$ Acceptable max loss stock portfolio  

$$
V_{A}\beta_{A}(S_{T}-S_{0})/S_{0}+N_{p}(K-S_{T})\S100=V_{A}\beta_{A}(K-S_{0})/S_{0}
$$  

$$
\Rightarrow N_{p}=\frac{\mathcal{S}-\nu a l u e\ o f s t o c k\ p o r t f o l i o}{\mathcal{S}-\nu a l u e\ o f s t o c k\ i n d e x}\beta_{A}=\frac{V_{A}}{z S_{0}}\ \beta_{A}=12
$$  

The payof from the 12 long puts is $N_{p}(K-S_{T})z=\mathbb{\S}120,000$ so that Equation (18.A.1) is satisfed. The actual loss on the stock portfolio is $\$240,000$ , the payof from the puts is $\$120,000$ which gives a net loss of $\$120,000$ , which equals your maximum acceptable loss set by your choice of strike price, $K=900$ .  

Equation (18.A.2) is often described as follows. The number of index units held in the stock portfolio is $V_{A}/S_{0}$ . If $\beta_{A}=1$ then the number of index units held in puts should therefore also equal $V_{A}/S_{0}$ . But as each index point is worth $z=\$100$ , and the stock portfolio beta $\beta_{A}$ may not be equal to one, then the required $N_{p}$ is given by (18.A.2).  

# APPENDIX 18.B: DYNAMIC DELTA HEDGE  

A diversifed stock portfolio consists of $N_{i}$ diferent stocks- $i$ with prices $X_{i}$ . The value of portfolio-A consisting of $m$ -stocks is $\begin{array}{r}{V_{A}=\dot{\sum_{i=1}^{m}}N_{i}X_{i}=\sum_{i=1}^{m}V_{i}}\end{array}$ hence:  

$$
d V_{A}=V_{A}R_{A}
$$  

where $\begin{array}{r}{R_{A}\equiv\sum_{i=1}^{m}w_{i}R_{i}}\end{array}$ is the return on portfolio-A, $R_{i}=d X_{i}/X_{i}$ is the return on stock- $i$ and $w_{i}\equiv V_{i}/V_{A}$ is pr=oportion held in each stock- $i$ . Assume, portfolio-A has a market beta $\beta_{A}$ with respect to the S&P 100 market index, $R_{m}$ . To preserve the value of the stock portfolio over a small interval of time, we use a dynamic hedging strategy with stocks $+$ puts. The value of the hedge portfolio is $V=V_{A}+N_{p}z\ P$ , hence:  

$$
d V=V_{A}R_{A}+N_{p}z\ \Delta_{p}\ d S=V_{A}R_{A}+N_{p}\Delta_{p}(z S_{0})\ (d S/S_{0})=0
$$  

where $\Delta_{p}\equiv\partial P/\partial S<0$ . Substituting $R_{m}=d S/S_{0}$ , the return on the S&P 100 ‘market index’ (which is the underlying in the put contract) and $R_{A}=\beta_{A}R_{m}$ then from (18.B.2):  

$$
N_{p}=-\frac{V_{A}}{z S_{0}}\left(\frac{\beta_{A}}{\Delta_{p}}\right)=\frac{V_{A}}{z S_{0}}\left(\frac{\beta_{A}}{|\Delta_{p}|}\right)
$$  

# EXERCISES  

# Question 1  

If the initial stock price is $S_{0}$ and the call premium is $C_{0}$ show the payof and profts at maturity for a covered call. Is a covered call strategy risk free?  

# Question 2  

A pension fund has to pay out a ‘lump sum’ to its pensioners in 6 months’ time.  

Why might the pension fund (which holds a diversifed portfolio of stocks), purchase index puts, with 6 months to maturity, that are currently $3\%$ out of-the-money (OTM)?  

# Question 3  

What is a protective put? Why is the payof (profle) to a protective put, qualitatively like the payof to a long call?  

# Question 4  

What is the payof profle (at expiration) and the breakeven strike price for a portfolio consisting of an equal number of long stocks and long puts? The puts have $K=164$ and $P=\$6$ . What is the proft at expiration of the puts, if $S_{T}=163?$ Assume the initial stock price is $S_{0}=162$ .  

# Question 5  

The current stock price is $S_{0}=100\$ . A put with a strike of $K=98$ (with 6 months to maturity) is available at a price of $P=\$4$ . In a table, show the payof and proft from a protective put for outcomes at maturity of $S_{T}\geq K$ and $S_{T}<K$ . What is the breakeven stock price (which gives zero proft)? Who might use a protective put?  

<html><body><table><tr><td>Stock price (Note: K = 98)</td><td>Payoff Long stock and long put</td><td>Profit</td></tr><tr><td>ST≥K</td><td></td><td></td></tr><tr><td>ST<K</td><td></td><td></td></tr></table></body></html>  

# Question 6  

You hold a portfolio of $N_{s}=1\mathrm{,000}$ stocks of Coca-Cola with current price $S=\$80$ . A put option on Coca-Cola is available with $K=\$75$ , put premium $P=\$10$ and a delta of $\Delta_{p}=-0.2$ . (Each put is written on $\phi=100$ stocks). How would you delta-hedge your stock position and what would happen to the value of your stock-put portfolio if stock prices rise by $\$2$ over the next day?  

# Question 7  

You hold a position in $N_{p}=40$ put options (on stock-A), with market price $P=\$3$ and $\Delta_{p}=$ $-0.40$ . Assume each put option is written on $\phi=100$ stocks. You believe these puts are underpriced by $1\%$ because you think volatility will increase in the future – although all other options traders believe volatility will not change).  

(a) How can you take advantage of the underpricing of the put options, while protecting yourself against the change in the put premium, due to unexpected changes in the stock price?   
(b) If the stock price falls by $\$2$ over the next day and the underpricing of the put is not corrected, what is the outcome of your strategy? Explain.   
(c) If the stock price falls by $\$2$ and the underpricing of the put option of $1\%$ is corrected, what is the outcome of your strategy? Explain.   
(d) What are the risks in your strategy?  