---
tags:
  - arbitrage
  - cme_group
  - hedging
  - index_futures
  - stock_index
aliases:
  - SIF
  - futures contracts
key_concepts:
  - contract specification
  - diversified portfolio
  - index arbitrage
  - market risk
  - program trading
  - settlement procedures
---
# Index Futures  

# Aims  

• To provide details of contract speci!cation, settlement procedures and quotes for stock index futures contracts.   
• To demonstrate index arbitrage and program trading using stock index futures.   
• To price a stock index futures contract, when stocks which make up the cash market index (e.g. S&P 500), pay discrete dividends.   
• To determine the number of futures contracts to use when hedging various cash market positions (e.g. a portfolio of stocks or holding barrels of oil).   
• To outline the risks which remain, after hedging with index futures.   
• To demonstrate ‘tailing the hedge’.  

Stock index futures (SIF) are contracts whose price depends on an underlying stock market index such as the S&P 500, FTSE 100 or Nikkei 225 indices. Such futures contracts are widely used in hedging, speculation, and index arbitrage.  

In a well-diversi!ed portfolio of stocks, speci!c (idiosyncratic) risk of individual stocks has been largely eliminated and only ‘market’ (‘systematic’ or ‘non-diversi!able’) risk remains. Stock index futures can be used to eliminate this ‘market risk’ of the portfolio of stocks. In ‘normal times’ a fund manager might be quite happy to hold a diversi!ed portfolio of stocks even though they are risky. But if a fund manager believes the market will become increasingly volatile over the next 3 months (i.e. could rise or fall substantially) and she wished to remove this uncertainty, she could sell stock index futures to eliminate the market risk. At the end of the 3-month period, she would have neither gained nor lost.1 If she believes the stock market has then returned to a ‘normal level of volatility’, she would close out her futures position and her stock portfolio would again be subject to market risk.  

Alternatively, suppose you plan to invest cash that you will receive in 3 months’ time in a diversi!ed portfolio of stocks but you are worried that the stock market will rise over the next 3 months. By buying stock index futures today you can !x the efective future purchase price of the stocks.  

Also, speculation on a bear or bull market is easier to achieve with stock index futures rather than incurring the cost of buying or selling a large number of stocks that make up your prospective speculative stock portfolio. Finally, if the quoted stock index futures price is not equal to the ‘correct’ (no arbitrage) futures price then you can make a (near) risk-free arbitrage pro!t by simultaneously trading in the spot and futures markets. We elaborate on these ideas in this chapter and consider further strategies in later chapters.  

# 5.1 STOCK INDEX FUTURES (SIF)  

Stock index futures contracts are written on aggregate stock market indices and are settled in cash. In the US index futures contracts traded on the CME (Chicago) include those on the S&P 500, the Mini-S&P 500, the Russel 1000 (large cap index), the Dow Jones Industrial Average (DJIA) and the Nikkei 225 (Japanese index), as well as several other indices. Trading volume is highest in the S&P 500 futures contract and taking all of these contracts together, the dollar volume of the underlying stocks traded in these index futures contracts exceeds the dollar volume on the stock market itself.  

On LIFFE2 (pronounced ‘life’), futures contracts are available on various UK stock indices including the FTSE 100 and FTSE 250 indices, on European indices such as the FTSE Eurotop 100 and FTSE Eurotop 300 (including and excluding the UK), and several others. The reason for so many diferent index futures contracts is so that fund managers can efectively hedge their existing equity portfolios, using a futures contract which has an underlying stock index that most closely matches the composition of their own cash market stock portfolio. Details of some of these contracts are given in Table 5.1.  

# 5.1.1 Contract Multiple  

All stock index futures are settled in cash (with settlement procedures difering between the diferent contracts) and nearly all contracts are closed out prior to their maturity date. Cash settlement is based on the value of an index point $\$7$ (or the ‘contract multiple’ ), which is set by the exchange (for the S&P 500, $z=\$250$ ). For the S&P 500 index futures contract, the smallest price change, a tick, is 0.1 index points, representing a $\$25$ change in value of one futures contract. Hence, a 1-point change in the S&P 500 futures index implies a change in the dollar value of one futures contract of $\$250$ . If the futures index on the S&P 500 is currently $F_{0}=2000$ , then:  

TABLE 5.1 Stock index futures contract   


<html><body><table><tr><td></td><td>FTSE 100</td><td>S&P 500</td><td>FTSE Eurotop 300</td><td>Nikkei 225</td><td>DJIA</td></tr><tr><td>Unit of trading</td><td>10 × index</td><td>$250 × index</td><td>20 ×index</td><td>$5 x index</td><td>$10 × index</td></tr><tr><td>Expiration</td><td>Mar/Jun/ Sep/Dec</td><td>Mar/Jun/ Sep/Dec</td><td>Mar/Jun/ Sep/Dec</td><td>Mar/Jun/</td><td>Mar/Jun/</td></tr><tr><td>Exchange</td><td>NYSE- Euronext</td><td>CME Group (IMM)</td><td>NYSE- Euronext</td><td>Sep/Dec CME Group (IMM)</td><td>Sep/Dec CME Group (IMM)</td></tr></table></body></html>  

Dollar value of futures contract $V_{F}=250F_{0}=\mathfrak{F}500,000$  

# 5.1.2 Stock Indices  

The S&P 500 and FTSE 100 stock indices are value (market capitalisation) weighted indices. The S&P 500 and FTSE 100 indices ignore dividend payments and therefore do not truly refect the ‘total returns’ from the constituent shares (which include dividend payments). Often a stock index will have both a ‘price version’ and a ‘total return’ version.  

# 5.1.3 Newspaper Quotes  

Newspaper quotes for diferent stock index futures contracts are very similar. An illustrative example of price quotes (on 27 July) for futures contracts on the S&P 500 (traded on CME) with diferent maturities are given in Table 5.2.  

TABLE 5.2 Quotes, index futures (27 July)   


<html><body><table><tr><td colspan="7">S&P 500 Index Futures (CME)</td></tr><tr><td></td><td>Open</td><td>Settle</td><td>Change</td><td> High</td><td>Low</td><td>Open interest</td></tr><tr><td>September</td><td>2,484.60</td><td>2,469.00</td><td>-15.50</td><td>2,485.20</td><td>2,466.00</td><td>677,803</td></tr><tr><td>December</td><td>2,499.00</td><td>2,491.30</td><td>-15.70</td><td>2,503.00</td><td>2,490.00</td><td>17,481</td></tr><tr><td>March</td><td>2,520.20</td><td>2,513.30</td><td>-16.20</td><td>2,526.00</td><td>2,514.00</td><td>1,094</td></tr><tr><td>June</td><td>2,537.20</td><td>2,561.80</td><td>-16.20</td><td>2,549.50</td><td>2,537.20</td><td>929</td></tr><tr><td>September</td><td>2,562.20</td><td>2,561.80</td><td>-16.30</td><td>2,574.10</td><td>2,562.10</td><td>146</td></tr></table></body></html>  

The settlement price (‘Settle’) is an average of futures prices for trades at the end of the trading day – the settlement price is used in ‘marking-to-market’ and establishing margin payments. ‘Open interest’ is the number of contracts held (long or short) and is highest for the nearby September index futures contract and tails of rapidly for longer maturity contracts. Note that for S&P 500 futures contracts, the longer maturity contracts have higher quoted settlement prices today, than the nearby maturing contracts (see the ‘Settle’ column, Table 5.2). There are also index futures available on many other stock indices (e.g. on US ‘high tech’ stocks in the NASDAQ-100 (CME); the CAC-40 French stock index (traded in Paris on the MATIF exchange), and the DAX-30 German index (traded on the EUREX exchange in Frankfurt).  

# 5.2 INDEX ARBITRAGE  

In Chapter 3 we used ‘cash-and-carry arbitrage’ to derive the correct (fair, no-arbitrage) futures price on a stock, which also applies to the futures price on a stock index:  

$$
\begin{array}{l}{F=S[1+(r_{s}-\delta_{s})T]\quad\mathrm{(using~simple~rates)}}\\ {F=S(1+r-\delta)^{T}\quad\mathrm{(using~discrete~compound~rates)}}\\ {F=S e^{(r_{c}-\delta_{c})T}\quad\mathrm{(using~continuouslycompounded~rates)}}\end{array}
$$  

where  

$\mathrm{S}=\mathrm{S}\&\mathrm{P}\ 500$ stock index (quoted on the NYSE)   
$\mathrm{F}=\mathrm{S}\&\mathrm{P}\ 500$ futures index (quoted in Chicago)   
${\boldsymbol{\mathrm{T}}}=$ time to maturity of the futures contract, number of years (or fraction of a year)   
$\textbf{r}=$ (domestic) risk-free interest rate (proportionate, p.a.)   
$\delta=$ dividend yield (proportionate, p.a)  

If the current risk-free rate $r$ is greater than the dividend yield (i.e. $r>\delta\bar{}$ ) then the current quoted futures price (in Chicago) will be above the current stock price (on the NYSE), that is $F>S$ , and vice versa. In applying the ‘cost-of-carry’ model we have to make the following assumptions:  

• Investors can purchase or short-sell stocks, to ‘replicate’ the performance of all the stocks in the stock index.   
• Actual discrete dividends paid out from stocks in the S&P 500 index (over the life of the futures) can be approximated by a constant (value weighted) dividend yield, $\delta$ , or actual discrete dividend payments from the stocks in the index are known with certainty (see   
below).  

# 5.2.1 Program Trading  

If the quoted futures price is not given by the equalities in (5.1), then index arbitrage enables (almost) risk-free pro!ts to be made. In large !nancial institutions real time data on $r,\delta,T,S$ and the quoted futures price $F_{q}$ are fed into computers and when $F_{q}\neq F$ in Equation (5.1), an arbitrage strategy is applied.  

Borrowing or lending cash at $r$ to undertake the arbitrage transaction is usually done via the repo market. Suppose an arbitrageur is faced with the following data:  

$$
\delta_{c}=0.03\:(3\%\:\mathrm{p.a.)}
$$  

$$
\begin{array}{l}{r_{c}=0.10\ (10\%\ \mathrm{p.a.})}\\ {T=1/3\ \mathrm{year}\ (\mathrm{i.e.}\ 4\ \mathrm{months})}\end{array}
$$  

‘Fair’ futures price:  

$$
F=\mathrm{S}e^{(r_{c}-\delta_{c})T}=2,000e^{(0.10-0.03)(1/3)}=2,047.2
$$  

The quoted futures price $F_{q}$ is above the fair futures price $F$ , so an arbitrage opportunity (i.e. ‘sell high, buy low’) is possible. You sell the futures contract today at $F_{q}=2,100$ , borrow $S=2{,}000$ at $r_{c}=0.10$ for 4 months $\cdot T=1/3)$ and purchase the underlying stocks today.3 After receiving dividend payments at the (continuously compounded) rate $\delta_{c}=0.03$ on your stocks, you owe 2,047.2 after 4 months. You deliver the stocks against the short futures position after 4 months and receive $F_{q}=2,100$ (in Chicago, from the long futures counterparty), making an arbitrage pro!t of $52.8(=2,100-2,047.2)$ .  

Conversely, suppose the quoted futures price is $F_{q}=2{,}020<F=2{,}047.2$ . Today, the arbitrage strategy is to buy the futures contract ‘low’ at 2,020, simultaneously short-sell a portfolio of stocks for $S=2{,}000$ and invest the proceeds in a bank deposit at the risk-free rate. At maturity of the long futures position you pay out $F_{q}=2,020$ , take delivery of the stocks (in Chicago), which you return to your broker. You also have to pay the broker any dividends due on the borrowed stocks. Hence your net receipts from investing the $S=2{,}000$ at the risk-free rate would be $\mathrm{S}e^{(r_{c}-\delta_{c})T}=2$ 047.2 and the arbitrage pro!t at $T_{:}$ is 27.2 (receipts of 2047.2 minus payments of 2020).  

# 5.2.2 Discrete Dividend Payments  

In practice, dividend payments are clustered around certain months (particularly February and March in the US) so that the assumption of a constant dividend yield is an approximation.  

![](683dc6fac351482e3624d3b8b2669dcd0243ed38b2c2a0591e8443029f0fb15a.jpg)  
FIGURE 5.1 Futures price: dividend paying stock  

However, the arbitrage relationship is similar when dividends are paid in discrete amounts. Assume there are $N\mathrm{.}$ -dividend payments of $D_{j}$ , each of which is paid $t_{j}$ years (or fraction of a year) from today $t=0$ (Figure 5.1).  

All of the individual discrete dividend payments at time $t=0$ are worth:  

$$
P V(D)=\sum_{j=1}^{N}D_{j}\ e^{-r_{c}t_{j}}
$$  

Each dividend payment $D_{j}$ payable $t_{j}$ years from today is discounted, which puts all dividend payments at $t=0$ , the same point in time as the stock price $S_{0}$ . Hence the net cost of a replication portfolio at $t=0$ is $S_{0}-P V(D)$ , which accrues to $[S_{0}-P V(D)]e^{r_{c}T}$ at $T$ the maturity of the futures, so today’s no-arbitrage futures price is:  

$$
F_{0}=[S_{0}-P V(D)]e^{r_{c}T}
$$  

Above we assumed $r_{c}$ is constant for all maturities (i.e. yield curve is fat over $t=0$ to $T)-$ but if not, this is easily taken care of by using $r_{c,j}$ in place of $r_{c}$ .  

There is basis risk in the arbitrage strategy for several reasons. First, traders might only buy (or sell) a subset of the 500 stocks which make up the S&P 500 index. Hence the change in value of the arbitrageur’s portfolio of stocks might not exactly match the change in value of the S&P 500 stock index. Second, there are the arbitrageur’s transactions costs to consider and any uncertainty in the timing of dividend payments over the life of the futures contract. Third, it might not be possible to execute trades in the index futures contract and all the stocks (in the index) at exactly the same time – in the meantime the prices of some of the underlying stocks might change.  

Because index arbitrage opportunities are calculated using computerised real-time data, it is also known as program trading and is the subject of some controversy when the markets move rapidly (see Finance Blog 5.1).  

Academic studies suggest that index arbitrage pro!ts are di\$cult to exploit but tend to occur more often in those contracts with a longer time to maturity. This may be because these are the less liquid contracts where the ‘fair price’ and the quoted futures price might diverge because traders cannot obtain credit lines for these longer periods and therefore cannot instigate the arbitrage transaction.  

Over the past few years, replicating the movement in a stock market index has been made much simpler by the introduction of Exchange Traded Funds (ETFs). These are ‘funds’ that closely track changes in a speci!c index and can be bought and sold (at all times of the day) in the ‘cash market’, usually on electronic platforms at low transactions costs. This means that it is nearly always the case that index arbitrage ensures that the index futures price is given by $F_{0}=[S_{0}-P V(D)]e^{r_{c}T}$ .  

# Finance Blog 5.1 Program Trading and the 1987 Crash  

There was much discussion, particularly after the 1987 crash, of whether program trading caused increased volatility in the stock market. If program traders are all selling stock via on-the-close orders on the maturity date of the futures contract then this may increase volatility due to order imbalances. Other traders may also be trading stock index options, and options on stock index futures. If these options contracts expire at the same time as the futures contracts, then volatility in the cash market for stocks could be large – such periods are known as the triple witching hour.  

Stoll and Whaley (1986) !nd that the volatility on the stock market is greater on futures maturity dates (by a factor of 3) than on other days – particularly in the last hour of trading. The Brady Commission (1988) also felt that program trading exacerbated problems in the 1987 crash – but it is not clear that program trading results in major problems in more normal periods. The policy suggestions at the time included imposing higher margin on futures trading and more use of circuit breakers where the market is closed for ‘cooling of’ periods. Also, to some extent this problem has recently been overshadowed by the possibility that very high frequency trading using automated computer trades is causing excess volatility in the stock market.  

Source: Adapted from Cuthbertson and Nitzsche (2001).  

# 5.3 HEDGING  

A well-diversi!ed stock portfolio dramatically reduces ‘speci!c (idiosyncratic) risk’, while stock index futures contracts allow investors to hedge against changes in (overall stock) ‘market risk’ which is usually assumed to be adequately measured by some broad stock market index, which we take to be the S&P 500 index.  

Hedging relies on the positive correlation between spot and futures prices. This implies that if you hold a portfolio of stocks (‘long in the cash market’), then shorting stock index futures contracts ‘creates’ a negative correlation – what you lose on your cash market stock portfolio, you hope to gain on your index futures position. If a hedged portfolio entirely eliminates market risk then we might expect it to earn the risk-free rate of return.  

Suppose that on 28 December Ms Midas holds a $\$100$ diversi!ed portfolio of US stocks which exactly mirrors the composition of the S&P 500 index, so the beta of her stock portfolio $\beta_{p}=1$ . She feels the stock market is likely to be more volatile (than normal) over the next 3 months. This presents both opportunities for large price rises and large price falls. But let us assume that Ms Midas is very worried about a general fall in the stock market over the next 3 months, between 28 December and 28 March. This may be because she has already achieved the target return on her portfolio and is worried that her past gains are likely to be eroded over the next 3 months – which is the end of the period over which her performance (and bonus) will be evaluated by her superiors.  

She can use stock index futures to eliminate this market risk (and earn the risk-free rate of interest) over the 3-month period. Of course, she could also earn the risk-free rate by selling all her stocks and holding T-bills. However, this would involve high transactions costs, as she would have to sell and then buy-back the stocks 3 months later. Continuing to hold the portfolio of stocks and hedging using stock index futures is far cheaper.  

To hedge over 3 months she requires a futures contract which has at least 3 months to maturity. Suppose on 28 December Ms Midas decides to use the June-futures (which has a maturity date towards the end of June). Stock index futures (on the S&P 500) are cash settled with each index point (‘tick’) on the futures contract is assigned a value of $\$250$ .  

Ms Midas can hedge on 28 December by selling (shorting) the June-index futures (on the S&P 500). For the moment, assume a perfect correlation between the underlying market index S and the futures index $\mathrm{~F~}$ (i.e. correlation coe\$cient of $+1$ ) and that both indices move by the same amount. If the S&P 500 index on the NYSE on 28 December is $S_{0}=2\mathrm{,000}$ and the market falls by $10\%$ over the next 3 months, the S&P index will fall to 1,800 (i.e. by 200 points). Ms Midas’s stock portfolio will fall in value by $\S1\mathrm{m}(=\S10\mathrm{m}\times10\%)$ . If we assume $F$ and $s$ move by the same absolute amount then the change in $F=200$ points and the change in value of one futures contract is $\$50,000($ . Hence the number of futures contracts to hedge your stock portfolio is:  

$$
N_{F}=\frac{C h a n g e~i n~\nu a l u e~o f s p o t~p o r t f o l i o}{C h a n g e~i n~\nu a l u e~o f~o n e~f u t u r e s~c o n t r a c t}=\frac{\mathfrak{G}1\mathrm{m}}{\mathfrak{G}50,000}=20~\mathrm{contracts}
$$  

So Ms Midas would hedge by shorting 20 contracts on 28 December. The outcome of the hedged position on 28 March is therefore:  

$$
=\mathfrak{s}10\mathrm{m}\left(10\%\right)=\mathfrak{s}1\mathrm{m}
$$  

$$
=200\times\S250\times20=\Phi1\mathrm{m}
$$  

The reader can verify that a similar hedged outcome would ensue if stock prices rise by $10\%$ . Here, the capital gain on the stocks would be ofset by the loss on the short futures position – after $F$ increases Ms Midas has to buy back the futures at a higher price (i.e. at a loss). In this case, with hindsight it would have been better not to have hedged – but ‘hindsight’ is not ‘available’ on 28 December. In any case the whole idea of a hedge is to remove price risk and in doing so, you also forego any favourable outcomes if stock prices rise. ‘You can’t have your cake and eat it’ – you can be a hedger or a speculator in any given deal, but not both.  

If the beta of Ms Midas’s portfolio of stocks is $\beta_{p}=1.5$ and the market falls by $10\%$ , the return on her portfolio falls by $15\%$ $(=R_{p}=\beta_{p}R_{m})$ . Hence, she needs more futures contracts for an efective hedge. She would in fact need to short 30 futures contracts. This is because the change in the dollar value of her stock portfolio is now expected to be $\$100$ , so $N_{F}=(1.5\mathrm{m}/50,000)=30$ .  

The above example looks a bit too good to be true – a perfect hedge. Yes, this is too optimistic! The reason for this is that we assumed the absolute change in the two indices, $F$ and $s$ are exactly the same. In practice this is not the case. First, $F$ and $s$ do not move exactly together, ‘index point-for-index point’ – they do so only approximately. Second, because interest rates might change over the life of the hedge, this slightly afects the relationship between changes in $F$ and $s$ – recall that $F=S(1+r T)$ – this is basis risk. Third, because the beta of your portfolio of stocks is estimated with error, when the market moves by $10\%$ the value of your stock portfolio might not move by exactly $15\%$ – this is probably the biggest source of error in the hedge.  

Let’s return to the case where $\beta_{p}=1$ and consider a more realistic scenario where there would be some hedging error. On 28 December the S&P 500 index $S_{0}=2\mathrm{,000}$ and the futures index price $F_{0}=2\mathrm{,040}$ . Over the next 3 months the portfolio manager’s worst fears are met and the S&P 500 index falls by $10\%$ (200 index points) to $S_{1}=1\small{,}800$ , so Ms Midas’s stock portfolio falls in value by $\$10$ . On 28 March, the June-futures index falls to $F_{1}=1{,}818$ – a fall of 222 index points4 – the futures contracts are closed out (i.e. buy-back) and the outcome of the hedged position on 28 March is:  

Loss $\$100$ stock portfolio $(10\%)={\mathfrak{S}}1\mathrm{m}$  

$$
\tan\beta=222\times\oint250\times20\mathrm{contracts}=\oint1.11\mathrm{m}
$$  

Hence the hedge position has produced a small pro!t of $\$120,000$ $1.1\%$ of the portfolio value of $\$100$ ). But most importantly, it has averted a possible large loss of $\$10$ had the  

position remained unhedged. In practice hedge positions result in small pro!ts or losses but these average out to zero5 for a large number of hedges, implemented over time.  

# 5.3.1 Minimum Variance Hedge Ratio  

Instead of working out the number of futures contracts you need when you consider a particular fall (e.g. $10\%$ ) in the market index, perhaps the ‘best’ formula to use (known as the minimum variance hedge ratio) is to calculate the number of futures contracts using:  

$$
\begin{array}{c}{{N_{F}=-\left(\frac{\displaystyle\S V a l u e\ o f c a s h\ m a r k e t p o s i t i o n}{\displaystyle\S V a l u e\ o f o n e f u t u r e s\ c o n t r a c t}\right)\beta_{p}}}\\ {{=-\displaystyle\frac{V_{p}}{V_{F}}\beta_{p}=-\frac{\displaystyle\S10\mathrm{m}}{\displaystyle(\S250)(2,040)}=-19.6(=-20\ c o n t r a c t s)}}\end{array}
$$  

where, $\beta_{p}=1,F_{0}=2,040$ and $V_{F}=(\mathbb{\S}250F_{0})=\mathbb{\S}510,000$ . $V_{F}$ is the ‘dollar value of one futures contract’ and is also sometimes referred to as the ‘invoice price’ or ‘contract price’ of the stock index futures. But note that it is a purely notional amount, since this money is not paid at inception of the futures contract (only a small margin payment is made).  

What is important in hedging is that the change in the futures index is (approximately) matched by the change in the (underlying) S&P 500 stock index. The (arbitrary) use of $\$250$ simply converts a 1 point change in the futures index to a dollar amount.6  

The negative sign means Ms Midas needs to short 20 contracts. The above formula gives an answer very close to our ‘simple’ method described above. But it also has the advantage that you can just ‘plug in’ the known value for the (index) futures, $F_{0}=2\mathrm{,040}$ , currently quoted in Chicago (or on your trading screen). A slight variant to Equation (5.7) is to use the dollar value of the S&P 500 stock index $(=\$250\times S_{0})$ in the denominator, where $S_{0}$ is the current level of the S&P 500 stock index, then:  

$$
N_{F}=-\frac{V_{p}}{(\S250)S_{0}}\beta_{p}=-\frac{\S10\mathrm{m}}{(\S250)(2,000)}=-20\mathrm{contracts}
$$  

Because $F_{0}$ and $S_{0}$ do not difer greatly, the above two formulas usually give similar answers for $N_{F}$ . Notice that in the above we used stock index futures contracts to hedge a portfolio of stocks – and this is usually the case in practice. But you might also wish to hedge your holdings of individual stocks (e.g. Microsoft). Here you have an alternative which is to use a futures contract on Microsoft stock, itself. The above formula still applies but of course here the futures contract on Microsoft has a beta of unity (with respect to Microsoft’s stock return). You can also use the above formulas (with slight modi!cations) to set up a hedge position for oil, wheat, foreign exchange, etc. (see Appendix 5).  

# EXAMPLE 5.1  

# Hedging, Key Decisions  

• If you are long (i.e. own) the spot asset (e.g. portfolio of stocks, oil) then to hedge you sell (short) futures contacts, today.   
• If you are planning to purchase the underlying asset (e.g. portfolio of stocks, oil) in the future (i.e. you are short in the cash market) then to hedge you purchase (go long) futures contracts, today.   
• Hedging works because the actions of arbitrageurs ensures that $F$ and $s$ move together, almost dollar-for-dollar. Hence a long position in the spot asset (e.g. stocks) and a short position in the futures contract creates a (near perfect) negative correlation between the spot and futures prices – so the net change in the value of the hedged position is (close to) zero.   
• Note that any losses on your (long or short) futures position may involve additional margin calls. Hence a hedger must have lines of credit or other collateral available to meet possible margin calls.  

# 5.3.2 Hedging in Practice  

Let us now consider a slightly more complex hedging example using SIF, where we explicitly calculate futures prices, use the CAPM equation to work out the expected return on the stock portfolio and where the stocks in the portfolio earn dividends. It is 28 December and Ms Midas holds a $\$100$ portfolio of stocks and she wishes to hedge over the next 3 months (to 28 March). She uses the June-futures index to hedge.  

# 28 December, Ms Midas Portfolio (Hedge period $\mathbf{\lambda}=3$ months)  

Portfolio value $V_{p}=\mathfrak{F}10\mathrm{m}$ $\beta_{p}=1.5$ Stock index $S_{0}=2\mathrm{,000}$ index points $r=4\%$ continuously compounded  

# 28 December: Stock Index Futures  

Maturity of June-forward contract $=6$ months (i.e. $T_{0}=1/2$ year)  

Dividend yield on market index $\delta=6\%$ (continuously compounded)  

$$
\begin{array}{l}{F_{0}=S_{0}e^{(r-\delta)T_{0}}=2000e^{-0.02/2}=1980}\\ {V_{F}=(\S250F_{0})=\S495\mathrm{,000}}\end{array}
$$  

$$
N_{F}=-{\frac{V_{p}}{V_{F}}}\beta_{p}=-{\frac{\mathfrak{H}10\mathrm{m}}{\mathfrak{H}495,000}}(1.5)\ {\mathrm{(i.e.~short~}}30\ \mathrm{contracts)}
$$  

# 28 March (3 months later)  

Assume the S&P 500 has fallen by $10\%$ to $S_{1}=1\small{,}800$ and Ms Midas closes out her June-futures contracts, which now have 3 months to maturity $\langle T_{1}=1/4$ year :  

$$
F_{1}=S_{1}e^{(r-\delta)T_{1}}=1800e^{-0.02/4}=1,791(F_{0}-F_{1})=189\mathrm{p}
$$  

The percentage return on the market portfolio (S&P 500) $\boldsymbol{R_{m}}$ is the capital loss plus the dividend yield (over 3 months):  

$$
\begin{array}{l}{{R_{m}=[(S_{1}-S_{0})/S_{0}]+(\delta/4)}}\\ {{\ \qquad=((1,800-2,000)/2,000)+0.015=-0.085(8.5\%)}}\end{array}
$$  

The expected return on your stock portfolio over 3 months (using the CAPM)7:  

$$
R_{p}=r+\beta_{p}(R_{m}-r)=1\%+1.5(-8.5\%-1\%)=-13.25\%
$$  

Expected value of the stock portfolio after 3 month $\mathbf{\beta}_{\mathrm{3}}=\S10\mathbf{m}\left(1-0.1325\right)=\S8.675\mathbf{m}$  

$$
={\S}8.675\mathrm{{m}}+{\S}1.4175{\mathrm{m}}={\S}10.0925{\mathrm{m}}
$$  

Percentage change in hedged position (over 3 months $)=(\S10.0925\mathrm{m}/\S10\mathrm{m}-1)=0.925\%.$  

The hedged portfolio has gained $\$92,500$ $(0.925\%$ of $\$100$ ) in value. Had Ms Midas not hedged she would have lost about $13.25\%$ on her stock portfolio.  

The risks in the hedge are:  

• beta of the stock portfolio may be estimated incorrectly or it may change over the hedge period.   
• The stock portfolio is not well diversi!ed so that some speci!c risk is present – hence the return on the stock portfolio will not be correctly measured by its beta and the market   
return.8   
• the risk-free rate and the dividend yield – the sources of basis risk – may change over the hedge period (which will alter the correlation between $F$ and $S$ ).  

The !rst point is perhaps the most serious and may arise if beta is really time varying but the regression analysis assumes a constant value for beta, estimated using a long data period. The variability in beta can be analysed using recursive regressions – that is, to re-estimate beta as you add more data or you can simply estimate beta over diferent sample periods, to see how variable its empirical value appears to be. There are also methods for forecasting time varying parameters like beta (e.g. using the Kalman !lter). Alternatively, note that a time varying beta can also be directly calculated by using direct estimates of variances and covariances:  

$$
\beta_{p}=\frac{\sigma_{R_{p},R_{m}}}{\sigma_{R_{m}}^{2}}
$$  

The modelling of time varying variances and covariances using ARCH and GARCH models (see Cuthbertson and Nitzsche 2004, 2008) has been rather successful (especially with ‘high frequency’, daily data) and these models can also be used to forecast $\beta_{p}$ over the hedge period using (5.13). There is some evidence that this may improve the hedge outcome compared with using a !xed value for $\beta_{p}$ (see, for example, Baillie and Myers 1991). Also note that the hedge ratio given by Equation (5.7) implies that as stock prices change, we should re-calculate $V_{p}$ and hence $N_{F}$ periodically. The return on a stock portfolio is:  

$$
R_{p}=\alpha_{p}+\beta_{p}R_{m}+\varepsilon_{p}
$$  

The SIF hedge removes the market risk $\beta_{p}R_{m}$ , (see Chapter 6) so one source of the hedging error is speci!c risk $\varepsilon_{p}$ . The dollar hedging error $d V$ and the variance of the hedging error are:  

$$
\begin{array}{c}{d V=V_{p}\varepsilon_{p}}\\ {\sigma_{d V}^{2}=V_{p}^{2}\sigma_{\varepsilon_{p}}^{2}}\end{array}
$$  

It is shown (see Chapter 6) that the variance of the (dollar) hedging error can also be expressed as:  

$$
\sigma_{d V}^{2}=V_{p}^{2}\sigma_{R_{p}}^{2}(1-R s q)
$$  

where is the ‘R-squared’ from the OLS regression (5.14). Equation (5.15c) can be used to calculate the expected error in the hedge.  

# EXAMPLE 5.2  

# Hedging Error – Stock Portfolio  

BigCapital, a mutual fund, has decided to hedge its $\$100,000$ stock portfolio using SIF over the next month and wants to measure the potential hedging error. The OLS regression of the portfolio monthly return on the market return, has $R s q=0.8$ and $\beta_{p}=1.4$ . The monthly  

(continued)  

# (continued)  

standard deviation of the portfolio return is $\sigma_{R_{p}}=10\%$ . The variance of the (monthly) dollar hedging error is:  

$$
\sigma_{d V}^{2}=(\mathbb{8}100,000^{2})(0.10^{2})(1-0.8)=\mathbb{8}20\mathrm{{m}}
$$  

The monthly (dollar) hedging error is therefore $\sigma_{d V}=\sqrt{20\mathrm{m}}=\S4{,}472$ ( $4.5\%$ of the initial value of the portfolio of $\$100,000$ ). Over shorter horizons the dollar hedging error will be smaller. For example, the hedging error over 1 week uses the weekly standard deviations in (5.15c), where approximately, $\sigma_{d V,w e e k}^{2}=\sigma_{d V,m o n t h}^{2}/4$ .  

# 5.4 TAILING THE HEDGE  

There is one other practical issue we should deal with, namely adjusting the hedge to take account of interest paid or received on the margin account. This is called ‘tailing the hedge’. Suppose you hedge with a short futures position. If the futures price rises, your short position will make losses, and you may have to make additional margin payments which will increase the overall cost of your hedge. You could ofset this increased cost, if you also held some additional long futures positions which would increase in value, when futures prices increase. Hence, if you are initially short (long) $N_{F}$ futures, then tailing the hedge will involve going long (short) some additional futures contracts. The ‘tail’ is always an opposite position to the initial futures position (of $N_{F}$ futures). One method of calculating this tail adjustment is:  

$$
N_{t a i l}=-N_{F}r T
$$  

where $N_{t a i l}$ is the number of contracts to tail the hedge, $N_{F}=$ the initial number of futures contracts (see Equation (5.7)), $r=8\%$ is the risk-free lending or borrowing rate on variation margin payments (any surplus over the maintenance margin is assumed to remain in the margin account), $T=$ time to maturity of the futures. Suppose initially using Equation (5.7) you require $N_{F}=-100$ (short) futures contracts on the S&P 500 and the maturity of the futures is $T=90/360.$ . If the futures index increases by one point, then the short-futures position will lose value:  

Increased variation margi $\mathrm{1=(+1\point)\times(100\contracts)\times\S250=\S25,000}$ Loss of interest margin $)=\S25,000\times(0.08)\times(90/360)=\S500$ $N_{t a i l}=-N_{F}r T=-(-100)\times0.08\times90/360=+2$ Gain futures ‘tail $\mathbf{\Sigma}^{\prime}=(+1\mathrm{point})\times(2\mathrm{contracts})\times\S250=\S500$  

Hence, with ‘the tail’ in place, the additional interest cost of the variation margin is ofset by tailing the hedge. In practice, $r$ will vary over the life of the futures and hence tailing the hedge will not produce the perfect result given above. Of course, given the initial $N_{f}=-100$ contracts and $N_{t a i l}=+2$ contracts, then the actual initial hedge position taken would have been to short 98 contracts:  

$$
N_{n e w}=N_{F}-N_{F}r T=N_{F}(1-r T)
$$  

The value for $N_{n e w}$ , which ‘tails the hedge’ has to be recalculated periodically and the hedged position rebalanced as $r$ and $T$ change.  

# 5.5 SUMMARY  

• There are a number of diferent index futures contracts on various stock market indices.   
• Index futures prices can be determined using the cost-of-carry approach and violations of this relationship give rise to (risk-free) arbitrage – known as program trading, which today involves high-frequency trading on electronic exchanges, using computer algorithms.   
• Stock index futures (SIF) provide a low cost method of hedging an existing diversi!ed equity portfolio or in hedging a future purchase of a diversi!ed portfolio of stocks.   
• Hedging using SIF is not perfect, because the changes in the index futures price will not exactly match changes in the stock index (S&P 500) and the portfolio beta is an estimate and may not be accurate over the hedge period. There are also transactions costs in the futures market to consider and potential margin payments.  

# APPENDIX 5: HEDGE RATIOS  

In this appendix we use a common methodology to derive the optimal number of futures contracts required in a variety of practical hedging situations. To calculate the hedge-ratio where the underlying asset to be hedged (e.g. crude oil) is the same as the underlying asset in the futures contract (i.e. futures on crude oil), is straightforward. For example, suppose it is January and you expect to sell $10\mathrm{m}$ barrels of crude oil in 3 months’ time in April and you are worried that the oil price in the cash market might fall over the next 3 months. The contract size for one futures on crude oil is for delivery of $z=1,000$ barrels, hence to hedge you would short:  

$$
N_{F}=-N/z=-\mathrm{{\o{N/z}}}=-\mathrm{{\o{N/z}}}=0\mathrm{{.000}}\mathrm{{barrels}}=-10,000\mathrm{{contracts}}\mathrm{{(short)}}
$$  

# Cross Hedge  

Now consider the case where the cash market asset you wish to hedge difers from the asset deliverable in the futures contract – this is a cross hedge. To demonstrate a ‘quick method’ of deriving the hedge ratio, assume the airline AirOFly wishes to hedge a future cash market purchase of jet fuel using heating oil futures. (We assume there are no highly liquid futures contracts on jet fuel).9 We have:  

$N=$ number of barrels of fuel required $P=$ cash market price of fuel barrel $R_{J F}\equiv d P/P$ the return fuel $V_{J F}=\$8$ -value of cash market position in fuel $(=N P)$ $F=$ price of heating oil futures gallon $z=$ contract size for futures heating oil delivery of $z=1,000$ gallons $V_{F}=\$8$ -value of futures contract heating ${\mathrm{oil}}=z F_{0}$ $N_{F}=$ number of futures contracts for the hedge to determined  

The dollar change in the hedge-portfolio is:  

$$
\begin{array}{r l}&{=N(P_{1}-P_{0})+N_{F}(F_{1}-F_{0})z}\\ {}&{=N P_{0}(d P/P_{0})+N_{F}(z F_{0})(d F/F_{0})=V_{p}(d P/P_{0})+N_{F}V_{F}(d F/F_{0})}\\ {}&{=V_{J F}R_{J F}+(N_{F}V_{F})R_{F}}\end{array}
$$  

The proportionate change in cash market jet fuel prices (i.e. the return on jet fuel) is $R_{J F}\equiv$ $d P/P_{0}$ . The return on heating oil futures is de!ned as $R_{F}\equiv d F/F_{0}$ . But $F$ depends on the cash market price of heating oil, $s$ and arbitrage ensures futures and spot prices of heating oil move together. Hence $R_{F}=R_{H O}$ where $R_{H O}$ is the percentage change in the spot price of heating oil. We assume that the return on jet fuel and heating oil (spot) prices are linearly related, $R_{J F}=\beta R_{H O}$ . A hedge position should involve neither a gain nor a loss so we set $d V=0$ and after rearranging:  

$$
N_{F}=-{\frac{V_{J F}}{V_{F}}}\beta
$$  

This is the ‘quick method’ of obtaining the optimal hedge ratio.10 It is !ne except that the relationship for beta, $R_{J F}=\beta R_{H O}$ will only hold ‘on average’ – so the hedge will not give $d V=0$ exactly – but over a number of hedges the dollar change in value $d V$ should be small. As we see below, given that prices are stochastic what we are really trying to do in the hedge is to choose that value for $N_{F}$ which minimises the variance of $d V$ . The correct expression for beta comes from a regression of spot jet fuel returns on the (spot) returns on heating oil:  

$$
R_{J F}=\alpha+\beta R_{H O}+\varepsilon
$$  

Sometimes for hedging over short time periods, absolute rather than percentage changes in prices are used to obtain an estimate of beta, $d P_{J F}=\alpha+\beta d S_{H O}+\varepsilon$ – but the two methods usually give similar estimates.  

# Hedging a Portfolio of Stocks  

We can use the above analysis with minor re-de!nitions to hedge a portfolio of stocks.  

$V_{p}=\mathbb{S}$ -value of cash market stock portfolio   
$F=$ index price of futures contract underlying $\mathbf{\tau}=$ S&P 500 stock market index   
$V_{F}=\S250F_{0}=\mathrm{nc}$ otional $\$1$ -value of futures contract $\$250$ is the value of an index point on the futures contract   
$N_{F}=$ number of futures contracts in the hedge to determined  

# Long in the Cash Market  

The cash market position consists of $n$ -stocks with $V_{i}(>0)$ dollars in each stock and a total amount invested of $V_{p}$ dollars. The change in value of the stock portfolio is:  

$$
d V_{p}=\sum_{i=1}^{n}d V_{i}=V_{p}\sum_{i=1}^{n}(V_{i}R_{i})/V_{p}=V_{p}\sum_{i=1}^{n}w_{i}R_{i}=V_{p}R_{p}
$$  

For example, if you hold $V_{p}=\$10$ in a diversi!ed portfolio of stocks and the return on the portfolio is $R_{p}=-10\%$ over 1 month (say) then your stock portfolio falls in value by $\$100,000$ . The change in the dollar value of a hedged portfolio consisting of $V_{p}$ dollars held in a stock portfolio and $N_{F}$ , stock index futures (SIF) is:  

$$
\begin{array}{l}{d V=\nleq\mathrm{{s}-\mathrm{{change}~i n~s t o c k~p o r t f o l i o}+\nleq\mathrm{{s}-\mathrm{{change}~i n~f u t u r e s~p o s i t i o n}}}}\\ {=V_{p}R_{p}+N_{F}(F_{1}-F_{0})\S250}}\\ {=V_{p}R_{p}+N_{F}V_{F}R_{F}}\end{array}
$$  

where $V_{F}=\$250F_{0}$ and $R_{F}\equiv d F/F_{0}$ . We assume that the index futures price $F$ and the stock market index (S&P 500) move together (because of arbitrage) so ${\cal R}_{F}\equiv{\cal R}_{m}$ (and $R_{m}\equiv d S/S$  

where $S={\mathrm{S}}\&{{\mathrm{P}}~500}$ index). If we assume the return on our portfolio of stocks is (exactly) linearly related to the market return, $R_{p}=\beta_{p}R_{m}$ and setting $d V=0$ in (5.A.4) then:  

$$
N_{F}=-\frac{V_{p}}{V_{F}}\beta_{p}
$$  

If you are long a portfolio of stocks then $V_{i}>0$ and hence $V_{p}>0$ and as the betas of nearly all stocks are positive then $\beta_{p}>0$ . Hence to hedge a long position in a portfolio of stocks, the minus sign in (5.A.5a) indicates that you will short stock index futures.  

Short-sell in the Cash Market  

Let a short-sale of stock- $j$ be represented by a positive (dollar) value $V_{j}>0$ . So a short-sale of say $\$100$ of stock- $j$ implies a positive value for $V_{j}=+100$ . If you short-sell $m$ -stocks then the total value of the short sales is $V_{S}=\sum_{j=1}^{m}V_{j}>0$ . As we always de!ne the return on a stock as positive (negative) when the price rises (falls) then $d V_{S}=-V_{S}R_{S}$ implies that your cash market short position will increase in value if stock prices fall that is $R_{S}<0$ (and vice-versa). The number of futures contracts to hedge your short position in stocks is then:  

$$
N_{F}=\frac{V_{S}}{V_{F}}\beta_{S}
$$  

Hence to hedge a short position in stocks, you go long (buy) stock index futures. (This is discussed further in Chapter 6.)  

Minimum Variance Hedge Ratio (MVHR)  

The correct (and slightly more involved) way to obtain the above expression for $N_{F}$ given that prices are stochastic, is to derive the minimum variance hedge ratio MVHR. From (5.A.4):  

$$
\sigma_{d V}^{2}=V_{p}^{2}\sigma_{R_{p}}^{2}+(N_{F}V_{F})^{2}\sigma_{R_{F}}^{2}+2V_{p}V_{F}N_{F}\sigma_{R_{p},R_{F}}
$$  

where $\sigma_{R_{p}}^{2}$ is the variance of the portfolio return, $\sigma_{R_{p},R_{F}}$ is the covariance between the portfolio return and the index futures return. The value of $N_{F}$ which minimizes the variance of the hedge portfolio is the solution to $\partial{\sigma_{\scriptscriptstyle d V}^{2}}/\partial{N_{\scriptscriptstyle F}}=0$ , that is:  

$$
N_{F}=-{\frac{V_{p}}{V_{F}}}\beta_{p}{\mathrm{~}}{\mathrm{~where~}}\beta_{p}\equiv{\frac{\sigma_{R_{p},R_{F}}}{\sigma_{R_{F}}^{2}}}
$$  

It can be shown that the above expression for $\beta_{p}$ equals the slope coe\$cient in the OLS regression:  

$$
R_{p}=\alpha+\beta_{p}R_{F}+\varepsilon_{p}
$$  

where $R_{p}$ is the proportionate return on the stock portfolio and $\varepsilon_{p}$ is a random error. For SIF we assume (because of arbitrage) that the index futures return $R_{F}$ (in Chicago) equals the return on the S&P 500 market index $R_{m}$ (on the NYSE). The ‘market return’ is simply the percentage change in the stock market index $s$ , so that $R_{m}\equiv d S/S$ where $S=\mathrm{level}$ of S&P 500 index.  

A time series regression of portfolio returns $R_{p}$ on the market return (S&P 500) gives a direct estimate of $\beta_{p}$ . An alternative is to calculate the portfolio beta from the individual betas of the constituent stocks in the portfolio using $\begin{array}{r}{\beta_{p}=\sum_{i=1}^{n}w_{i}\beta_{i}}\end{array}$ . The individual stock betas11 are obtained from a ‘beta book’ purchased from an investment bank. The $w_{i}=V_{i}/V_{p}$ are the proportions held in each stock, where $V_{i}$ is the dollar amount in stock- $i$ and $V_{p}$ is the total value held in the stock portfolio. Note that replacing $V_{F}=\$250F_{0}$ in (5.A.7) by the dollar value of the S&P index $\mathbf{\Phi}=\$2505_{0}$ gives:  

$$
N_{F}=-\frac{V_{p}}{\S250S_{0}}\beta_{p}
$$  

which if $F_{0}\approx S_{0}$ gives approximately the same value for $N_{F}$ as (5.A.7).  

# EXERCISES  

# Question 1  

You own a stock. A perfect (futures) hedge locks in the current spot price of the stock, after you close out your futures position at some later date (before the maturity of the futures). True or false?  

# Question 2  

In January an investor has a $\$1.20$ long position in a share. The beta of the share is 1.1. The investor intends to close out her position in the share around mid-March and wants to hedge the price-risk using futures. The March Mini S&P 500 future is currently trading at 1,450 (for delivery of $\$50$ times the index). Outline the investor’s hedging strategy.  

# Question 3  

You are a US resident. It is 30 January and you plan to purchase a $\$100$ portfolio of around 30 US stocks in 6 months’ time with a portfolio beta of 0.5. You are worried about a rise in prices over the next 6 months. The S&P 500 index futures is currently at 1,000.  

How could you hedge your future purchases using stock index futures? Would you take a long or short futures hedge?  

# Question 4  

It is 8 November and the stock market index is $S_{0}=441.15$ . The dividend yield is $3\%$ p.a. and the risk free rate $r=3.2\%$ p.a. (both continuously compounded). The December index-futures contract which expires in 40 days (at $T=18$ December) has a quoted price of $F_{q}=444$ . The contract multiple for the index-futures contract is $z=\$250$ .  

(a) Calculate the fair (no-arbitrage) price of the December index-futures.   
(b) Work out an arbitrage strategy with your maximum allowed credit line from the bank of $V_{s}=\$20\mathrm{m}$ .   
(c) Calculate the risk-free pro!ts, if the stock market index on 18 December (i.e. at maturity of the index futures contract) is $S_{T}=439$ .  

Assume any stocks you buy or sell ‘mimic’ the movement in the stock market index, that is your stock portfolio has a ‘beta’ of unity.  

# Question 5  

You are the manager of a pension fund with $\$500$ in a diversi!ed portfolio of stocks. You think the stock market over the next 6 months will be more volatile than normal so the potential for losses (and gains) are more extreme – but you believe the stock market will return to ‘normal’ after that. You want to hedge your stock position over the next 6 months and then return to your initial unhedged stock portfolio.  

What are the relative merits of selling the stocks and moving into risk-free assets (e.g. T-bills) over the next 6 months, versus using futures contracts to hedge your portfolio?  

# Question 6  

What is the minimum variance hedge ratio, when hedging a portfolio of stocks? Derive the optimal number of futures contracts in the hedge.  

# Question 7  

Suppose you hold a diversi!ed portfolio of stocks with a market value of $\$100$ and a beta of unity. A futures contract on the S&P 500 has 3 months to maturity. Each index point on the futures contract is worth $\$250$ . The current interest rate is $r=4\%$ (simple rate) and the current value of the S&P 500 stock index is $S_{0}=1\mathrm{,}420$ .  

(a) Show that the (no arbitrage) ‘fair’ futures price $F_{0}=1434.2$ (use simple, not compound interest). You want to hedge your $\$100$ stock portfolio over the next month, using stock index futures.   
(b) How many futures contracts are required to hedge your portfolio of stocks?   
(c) What is the outcome of your hedged position if in 1 month’s time the S&P 500 has fallen by $8\%$ and the futures index stands at $F_{1}=1315.1\?$ Compare the hedged and unhedged positions.   
(d) How do we know that the futures index will be $F_{1}=1$ 315.1 (in 1 month’s time) after the fall in the S&P 500? Briefy comment on the relationship between the change in the futures and stock indices.  