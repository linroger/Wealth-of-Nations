---
tags:
  - hedge_funds
  - market_risk
  - merger_arbitrage
  - stock_index_futures
  - stock_picking
aliases:
  - MaxPill
  - MoneyPlus
  - SIF
  - Stock picks
key_concepts:
  - effective beta
  - hedge market risk
  - merger arbitrage
  - stock index futures
  - underpriced stocks
---
# Strategies: Stock Index Futures  

# Aims  

• To show how stock index futures can be used to protect an active ‘stock picking’ strategy from general movements in the overall stock market return (e.g. S&P 500 index).   
• To demonstrate how an investor (e.g. long-short hedge fund) holding a well-diversi!ed portfolio of stocks can bene!t from speculating on underpriced or overpriced stocks, while also using stock index futures (SIF) contracts to hedge the impact of any unexpected movements in the market return (S&P 500) on the stock portfolio.   
• To show how the ‘efective beta’ of a stock portfolio can be altered using stock index futures. This enables investors (mutual funds and hedge funds) to implement a ‘market timing’ strategy, using stock index futures.   
• To show how hedge funds engaged in ‘merger arbitrage’ can slowly purchase the stocks of a prospective takeover target but also protect themselves from rising prices for the target !rm caused by an unexpected increase in the overall market return (S&P 500 index).  

# 6.1 UNDERPRICED STOCKS: HEDGING MARKET RISK  

Stock index futures (SIF) can be used to protect your speculative ‘stock picks’ from general changes in the overall stock market (e.g. S&P 500 index). For example, the hedge fund MoneyPlus takes on risky bets that are potentially pro!table – but it also tries to hedge any risks it feels it does not have the information and skill to handle. Suppose MoneyPlus thinks a drug company called MaxPill will soon be getting a favourable clearance from the regulator for its new drug (which reduces the incidence of heart attacks). On announcement of the successful licensing of the drug, MoneyPlus estimates that the stock price of MaxPill will rise by $10\%$ (say) from its current price of $P=\$10$ to its ‘true value’ $P({\mathrm{true}})=\S11$ .  

This rise of $10\%$ which is solely due to the mispricing is called the ‘alpha’ of the MaxPill stock. So MoneyPlus thinks MaxPill is currently underpriced and has a positive (expected) alpha of $10\%$ . Suppose all other market participants think MaxPill will not obtain a licence from the regulator and therefore believe the current price of $\$10$ is correct (and the alpha of the stock is zero).  

As a speculator or ‘stock picker’, MoneyPlus should buy (‘go long’) the stock today at $P_{0}=\$10$ . If the hedge fund is correct, then when the licence is granted other investors will realise that the true value of the stock is $\$11$ . These investors will then purchase MaxPill, this will cause its price to rise to $P_{1}=\$11$ , to refect its new ‘true value’ (agreed by all traders). MoneyPlus can now sell its MaxPill stocks at a pro!t of $\$1$ per stock because of its skill in predicting the success of the licence application – well before the other investors.  

Suppose MoneyPlus buys 10,000 stocks of MaxPill at $P_{0}=\$10$ so that its initial investment is $V=\mathfrak{H}100,000$ . After the granting of the licence, it sells at $\$11$ per share and makes a speculative pro!t of $\$10,000$ .1 This assumes MoneyPlus is correct about the underpricing and that the market as a whole (i.e. S&P 500 index) remains unchanged.  

But MoneyPlus is aware that even if it is correct about the underpricing of MaxPill its price could fall if the market as a whole falls (e.g. due to the onset of recession) – this is ‘market risk’. If the beta of MaxPill is $\beta=2$ and the market return (S&P 500) falls by $3\%$ (say), then MaxPill’s price will fall by $6\%$ $(=2\times3\%=\beta R_{m})$ . Hence, even if the mispricing of $10\%$ is corrected, the net change in the price of MaxPill will be:  

Net $\%$ change in MaxPill $\mathbf{\Sigma}=\mathbf{\Sigma}$ Increase to underpricing Fall to market movements  

$$
=10\%-6\%=+4\%
$$  

The !nal value of the hedge fund’s MaxPill stocks will therefore be $\$104,000-$ it has only made $4\%$ rather than the $10\%$ underpricing it thought it would make. This is because it has not hedged the market risk. Furthermore, had the S&P 500 market index fallen by more than $5\%$ then MoneyPlus would have made an overall loss on its purchase of MaxPill even if it was truly underpriced by $10\%$ . How can MoneyPlus protect itself from the impact of a fall in ‘the market’, on the underpriced stocks it has purchased, so that it earns the full $10\%$ of the underpricing?  

We have already solved this problem! MoneyPlus should sell (short) stock index futures contracts. If the market falls by $3\%$ , then we know that the gain on the short futures position will ofset any loss on the MaxPill stocks consequent on the fall in the market. If the hedge is successful, the cash pro!t on the futures will provide an ‘extra’ return of $6\%$ , so that when added to the $4\%$ increase in value of the MaxPill stocks, then MoneyPlus will have earned the full $10\%$ ‘underpricing’. If $V=\$100,000,\beta=2$ and $F_{0}=200(\mathrm{say})^{2}$ then the number of futures contracts to short is:  

$$
N_{F}=-~\frac{V}{V_{F}}\beta=-\frac{\S100,000}{(\S250)(200)}(2)=-4
$$  

To illustrate what is happening assume the S&P 500 index $s$ (i.e. ‘the market index’) and index futures $F$ have the following values:  

$$
\begin{array}{c}{S_{0}=198}\\ {S_{1}=192}\end{array}
$$  

$$
\begin{array}{c}{F_{0}=200}\\ {F_{1}=194}\end{array}
$$  

The S&P 500 has fallen by 6 index points (about $3\%$ ) and the futures index has also fallen by 6 points. Hence:  

Pro!t from the futures position $d V_{F}=N_{F}(F_{0}-F_{1})\$250=4(6)\S250=\S6,000$  

The $\$6,000$ pro!t is $6\%$ of the initial investment in MaxPill of $\$100,000$ , so the pro!t on the futures is equivalent to an extra $6\%$ return – which when added to the actual $4\%$ increase in the value of MaxPill stock makes a total return of $10\%$ – the same as the initial mispricing. Alternatively, the MaxPill shares end up being worth $\$104,000$ , but the $\$6,000$ pro!t from the futures position gives a total of $\$110,000$ that is, $10\%$ of the initial investment of $V=\$100,000$ . The hedge fund’s ‘total return’ of $10\%$ occurs because it has hedged the market risk and only has exposure to the underpricing of MaxPill (based on its consummate skill in forecasting the outcome of the licensing application for the new drug).  

We can also demonstrate the above calculations algebraically:  

$$
d V_{F}=N_{F}\S250(F_{0}-F_{1})=N_{F}V_{F}(d F/F_{0})=N_{F}V_{F}R_{m}
$$  

where $V_{F}=\$250F_{0}$ . We assume the futures index (written on the S&P 500) moves by the same percentage amount (in Chicago) as the (S&P 500) ‘market index’, on the NYSE (i.e. $d F/F_{0}=$ $\boldsymbol{R_{m}}\mathrm{~,~}$ and the simpli!ed CAPM relationship is $R_{p}=\beta R_{m}$ . The change in value of MoneyPlus hedge portfolio (i.e. long MaxPill and short SIF) is:  

$$
\begin{array}{r l}&{d V=V(\beta R_{m})+N_{F}V_{F}R_{m}}\\ &{\qquad=\mathfrak{H}00,000(2)R_{m}-4(\mathfrak{F}250\times200)R_{m}=[\mathfrak{F}200,000-\mathfrak{F}200,000]R_{m}}\end{array}
$$  

Hence, for each $1\%$ fall in the market return, the long position in MaxPill falls by $\$200,000$ – which is exactly ofset by a gain of $\$200,000$ on the short SIF’s position in four contracts. The $\$200,000$ gain on the short futures occurs when the futures are closed out (by buying them back at a lower price).  

Hence MoneyPlus holdings of MaxPill stocks are now hedged against rises (or falls) in the market return – as expected. This implies that if there is a correction in the underpricing of $10\%$ (while the futures hedge is maintained), then MoneyPlus will make an overall pro!t of $\$10,000$ . Note that the index-futures hedge must remain in place until the mispricing is corrected – the timing of the latter is uncertain and hence the futures hedge may have to be ‘rolled over’ (i.e. when one hedge terminates another must be put in place). Hence this strategy may involve ‘roll over’ risk.  

# 6.1.1 Futures on MaxPill Stocks  

Note that, above, MoneyPlus hedges by using index futures (on the S&P 500 index) and not futures contracts written on the MaxPill stocks, themselves. Let’s see why. MoneyPlus is long the underpriced MaxPill stocks. Again, suppose the net rise in MaxPill stock is $R=4\%$ (due to a fall in the market return of $3\%$ which causes a fall in MaxPill’s price of $6\%$ , coupled with a $10\%$ gain from the mispricing).  

If MoneyPlus had shorted futures contracts on MaxPill stocks, the MaxPill futures price will increase (approximately) by $4\%$ – so the short futures position loses $4\%$ , when closed out. The overall result is a net $4\%$ rise $(10\%-6\%)$ in the cash price of MaxPill stocks but a loss of $4\%$ on the short futures position – giving a zero net gain from the hedged position – rather than the $10\%$ gain from the underpricing that we expect!  

Clearly, this is not what MoneyPlus wants to do. Instead, MoneyPlus wants to ofset the impact of changes in the market return (S&P 500) on the value of its MaxPill stocks and for this MoneyPlus must use stock index futures. At the same time, MoneyPlus wants to ‘take a gamble’ (i.e. be unhedged) on the prospective underpricing of MaxPill – so it must not hedge the underpricing of MaxPill, with futures contracts on MaxPill. Hence when MoneyPlus hedges using index futures, it ofsets any efects due to overall stock market movements but it remains exposed to the mispricing of MaxPill, itself.  

# 6.2 OVERPRICED STOCKS: HEDGING MARKET RISK  

# 6.2.1 Overpriced Stocks: Long SIF  

If MaxPill is viewed as an overpriced stock then MoneyPlus should short-sell $V=\mathbb{\ s}100,000$ (say) of MaxPill stocks and it should hedge the market risk by going long four stock index futures contracts:  

$$
N_{F}=-{\frac{V}{V_{F}}}\beta=-{\frac{(-\S100,000)}{\S250(200)}}2=4~(\mathrm{long~futures~contracts})
$$  

For example, if the market return increases by $3\%$ , this results in a loss of $6\%$ on the short-position in MaxPill (as $\beta=2\AA$ ) since you would have to close out (buy back) the stock (on the NYSE) at a higher price. However, correction of the overpricing gives a gain of $10\%$ on the short position in MaxPill – implying a net gain on the MaxPill short position of $4\%$ .  

But an increase in the market return of $3\%$ implies an increase in value of four long stock index futures contracts of $\$6,000$ , which provides an additional return of $6\%$ (on the initial $\$100,000$ when the long-futures are closed out (i.e. sold). Hence, overall, MoneyPlus again makes $10\%$ , with a net $4\%$ coming from short-selling the overpriced stock in the cash market and $6\%$ from going long stock index futures.  

# 6.2.2 Portfolio of Stocks  

Now consider the case where MoneyPlus buys (goes long in) several underpriced stocks (e.g. Apple, AT&T, Exxon-Mobile, Cisco Systems, Ford, Starbucks, etc.) with $V_{i}>0$ (dollars) in each underpriced stock. To hedge the market risk of this portfolio, the number of stock index futures to short is given by Equation (6.1) where $\beta_{p}$ is the beta of the underpriced portfolio of stocks:  

$$
\beta_{p}=\sum_{i=1}^{n}w_{i}\beta_{i}
$$  

where  

$$
\sum_{i=1}^{n}V_{i}=V_{p},\quad w_{i}\equiv V_{i}/V_{p},\quad\sum_{i=1}^{n}w_{i}=1
$$  

# EXAMPLE 6.1  

# Hedge a Long Stock Portfolio  

MoneyPlus invests $V_{1}=\$100,000$ of its own funds in underpriced stock-1 with $\beta_{1}=1.5$ and $V_{2}=\$200,000$ in underpriced stock-2 with $\beta_{2}=2$ . The total amount invested is $V_{p}=$ $V_{1}+V_{2}=\$300,000$ and the portfolio beta is:  

$$
\beta_{p}=(1/3)1.5+(2/3)2=1.8333.
$$  

If the stock index futures $F_{0}=200$ points, the number of short contracts required to hedge the market risk of this speculative position in underpriced stocks is:  

$$
N_{F}=-{\frac{V_{p}}{V_{F}}}\beta_{p}=-{\frac{\mathfrak{F}300,000}{(\mathfrak{F}250)(200)}}(1.833)=-11\ (s h o r t,f u t u r e s\ c o n t r a c t s)
$$  

(continued)  

(continued)  

Also, taking positions in a portfolio of many underpriced stocks reduces the speci!c risk of the hedge fund’s stock portfolio.  

Conversely if stock-1 and stock-2 are thought to be overpriced then MoneyPlus would short-sell $\$100,000$ and $\$200,000$ (i.e. $V_{s}=\$300,000$ of these two stocks and go long $N_{F}=$ 11 stock index futures contracts.  

# 6.3 MARKET-NEUTRAL HEDGE FUND  

Here we initially consider holding only a portfolio of stocks – initially we do not hold SIF contracts. MoneyPlus can construct a long-short, stock-picking strategy which is ‘dollar neutral’ (‘market neutral’) by altering the dollar amounts it has in its long $(V_{L,i}>0)$ and short $(V_{S,i}>0)$ positions in stocks. Note that for a short position of say $\$50$ in a stock we assign a positive value for $V_{S,i}=+\$50$ . The change in the dollar value of a long-short stock portfolio (comprising $n$ -stocks held long and $m$ -stocks which have been short-sold), due to a change in the market return, is3:  

$$
d V_{L S}\equiv d V_{L}-d V_{S}=\sum_{i=1}^{n}V_{L,i}R_{L,i}-\sum_{i=1}^{m}V_{S,i}R_{S,i}=\left[\sum_{i=1}^{n}V_{L,i}\beta_{L,i}-\sum_{i=1}^{m}V_{S,i}\beta_{S,i}\right]R_{m}
$$  

Using the (simpli!ed) CAPM (single index model), Equation (6.5) can be written in terms of portfolio betas (see Appendix 6.A), $R_{L}=\beta_{L}R_{m}$ and $R_{S}=\beta_{S}R_{m}$ :  

$$
d V_{L S}=V_{L}R_{L}-V_{S}R_{S}=[V_{L}\beta_{L}-V_{S}\beta_{S}]R_{m}
$$  

where $V_{L}=\sum_{i=1}^{n}V_{L,i}$ and $V_{S}=\sum_{i=1}^{m}V_{S,i}$ are the total dollar amounts held long and short, respectively and $\beta_{L}=\sum_{i=1}^{n}w_{L,i}\beta_{L,i}$ , and $\beta_{S}=\sum_{i=1}^{m}w_{S,i}\beta_{S,i}$ are the long and short portfolio betas, respectively. The individual stock-betas $\beta_{i}$ are !xed. But the hedge fund can choose the dollar amounts $V_{L,i}>0$ held long and $V_{S,i}>0$ which are short-sold, to ensure that the term in brackets in (6.6) is zero – then any change in the market return will result in no change in the dollar-value of its long-short stock portfolio.  

For example, a market-neutral position might involve the hedge fund going long $V_{L}=$ $\$200,000$ in a portfolio of underpriced stocks with portfolio beta of $\beta_{L}=1.5$ and short-selling $V_{S}=\$150,000$ of overpriced stocks with portfolio beta $\beta_{S}=2$ , giving a ‘long-short, dollar-beta’, $\left[V_{L}\beta_{L}-V_{S}\beta_{S}\right]=0$ .4  

Clearly in this case, MoneyPlus does not have to take a position in futures to hedge its market risk – and it simply has to wait to see if the over-pricing and under-pricing are corrected. However, it is worth noting that in practice, a hedge fund which describes itself as ‘market neutral’ may not always have its stock portfolio completely insulated from movements in the market return. In this case there may be some residual market risk in the stock portfolio and we should more accurately describe this fund as a ‘long-short’ hedge fund.  

# 6.4 LONG-SHORT HEDGE FUND  

In practice, a ‘long-short’ hedge fund will often !nd that its portfolio of overpriced and underpriced stocks will not have a portfolio dollar-beta of exactly zero. In this case MoneyPlus might choose to hedge its remaining market risk using stock index futures as this is less costly than altering the stocks in its portfolio to generate a zero dollar-beta. As we shall see, this just involves treating the long and short positions separately. The number of futures contracts required to hedge the long-short position is just the ‘diference’ between the number required to hedge the long positions and the number required to hedge the short positions, hence:  

$$
\begin{array}{r}{N_{L}=-(V_{L}/V_{F})\beta_{L}\ (\mathrm{short}\ \mathrm{futures}),\ V_{L}>0}\\ {N_{S}=(V_{S}/V_{F})\beta_{S}\ (\mathrm{long}\ \mathrm{futrures}),\ V_{S}>0}\end{array}
$$  

The net position in futures is:  

$$
N_{F}=N_{L}+N_{S}
$$  

which could be a net-long or net-short (depending on the size of the long and short positions and the portfolio betas). Suppose the fund manager has two underpriced stocks held long and also has short-sold two overpriced stocks – the calculation of the long and short portfolio betas are given in Table 6.1.  

TABLE 6.1 Calculation of long and short portfolio beta   


<html><body><table><tr><td colspan="3">Long</td></tr><tr><td></td><td>Asset 1 Asset 2</td><td>Portfolio</td></tr><tr><td>Value, VL,i</td><td>$120 $80</td><td>$200</td></tr><tr><td>Weights, WL,i</td><td>0.4</td><td>1</td></tr><tr><td>Beta, βL,i</td><td>1.05</td><td>1.5</td></tr><tr><td colspan="3">Short</td></tr><tr><td>Asset 1</td><td>Asset 2</td><td>Portfolio</td></tr><tr><td>Value, Vs,i</td><td>$30 $20</td><td>$50</td></tr><tr><td>Weights, Ws,i</td><td>0.6</td><td>1</td></tr><tr><td>Beta, βs,i</td><td>2.1</td><td>2</td></tr></table></body></html>

Note: Amounts are in thousands of dollars. $w_{L,1}=$ $\mathsf{V}_{L,1}/\mathsf{V}_{L},\mathsf{w}_{L,2}=\mathsf{V}_{L,2}/\mathsf{V}_{L},\beta_{L}=\Sigma\mathsf{w}_{L,i}\beta_{L,i},\beta_{S}=\Sigma\mathsf{w}_{S,i}\beta_{S,i},$ are the long and short portfolio betas.  

# EXAMPLE 6.2  

# Hedge a Net-Long Stock Portfolio  

Using the data in Table 6.1, if $F_{0}=200$ (and each index point is worth $\$250$ ) then:  

$$
N_{F}=N_{L}+N_{S}=-{\frac{200,000}{(\S250)(200)}}1.5+{\frac{\S50,000}{(\S250)(200)}}2=-6+2=-4\odot
$$  

The change in value of the futures position is $d V_{F}=N_{F}V_{F}R_{m}$ where we assume $d F/F_{0}=R_{m}$ . The dollar change in value of the long-short stock portfolio plus the futures contracts is:  

$$
\begin{array}{r l}&{d V=\S200,000\ \beta_{L}R_{m}-\S50,000\ \beta_{S}R_{m}+N_{F}V_{F}R_{m}}\\ &{\qquad=\S200,000\ (1.5)R_{m}-\S50,000\ (2)R_{m}-4(\S250\times200)R_{m}}\\ &{\qquad=[\S300,000-\S100,000-200,000]R_{m}}\end{array}
$$  

For the net-long portfolio in the above example, if the market return rises by $1\%$ the long stock position increases in value by $\$300,000$ , the short stock position loses $\$100,000$ , making a net gain on the long-short stock position of $\$200,000$ , which is then exactly ofset by a loss of $\$200,000$ on the short futures position in four contracts. The $\$200,000$ loss on the short futures occurs when the futures are closed out by buying them back at a higher price, consequent on the rise in the index futures price. Hence the initial (non-market neutral) long-short stock portfolio is now hedged against rises (or falls) in the market return – as required.  

Whether you go long or short in stock index futures to hedge the market risk of your long-short stock portfolio depends on the sign of $[V_{L}\beta_{L}-V_{S}\beta_{S}]$ . For example, if the dollar amount MoneyPlus decides to go short is relatively large and the stocks which it shorts have relatively high betas, then $[V_{L}\beta_{L}-V_{S}\beta_{S}]$ may be negative. The hedge fund would then hedge by having a net long position in SIF (as in Example 6.3).  

# EXAMPLE 6.3  

# Hedge a Net-Short Stock Portfolio  

MoneyPlus is long $V_{L}=\$200,000$ in underpriced stocks with $\beta_{L}=1.5$ and short-sells $V_{S}=\$300,000$ in overpriced stocks with $\beta_{S}=2$ . Hence, $[V_{L}\beta_{L}-V_{S}\beta_{S}]=-\$300,000$ . If $F_{0}=200$ , then $V_{F}=(\$250\times200)=\S50,000$ and to hedge the market risk of this net-short stock portfolio requires:  

$$
N_{F}=-{\frac{V_{L}}{V_{F}}}\beta_{L}+{\frac{V_{S}}{V_{F}}}\beta_{S}=-6+12=+6\mathrm{~(long~futures~contracts)}
$$  

The outcome of the hedge portfolio due to changes in the market return is:  

$$
\begin{array}{l}{d V=\S200,000(1.5)R_{m}-\S300,000(2)R_{m}+6(\S250\times200)R_{m}}\\ {=[\S300,000-\S600,000+\S300,000]R_{m}}\end{array}
$$  

Hence if the market return increases by $1\%$ the long stock position increases by $\$300,000$ , the short position loses $\$600,000$ , a net loss of $\$300,000$ on the ‘cash market’ stock portfolio – which is exactly compensated by the $\$300,000$ pro!t when the initial six long futures are closed out (by selling them at a higher price).  

Note that in all the above examples we hedge the market risk of a long-short stock portfolio consisting of both overpriced and underpriced stocks. If the hedge fund has correctly identi!ed stocks which are genuinely overpriced (e.g. a biotech !rm that will have relatively few successful patents in the future) and stocks which are genuinely underpriced (e.g. a media company that will produce exceptionally popular TV shows in the future), then the hedge fund will earn speculative pro!ts when the mispricing of the two stocks is corrected – regardless of what happens to the market return (S&P 500) – since changes in the market return are hedged by the position in $N_{F}$ futures contracts.  

# 6.5 CHANGING STOCK MARKET EXPOSURE  

# 6.5.1 Reducing Stock Market Exposure  

Suppose you hold a $\$10$ diversi!ed portfolio of stocks with $\beta_{p}=2$ but there are no underpriced stocks in the portfolio – you merely hold a ‘passive’ diversi!ed portfolio. This portfolio is subject to substantial market risk because if the market falls $10\%$ , the value of the ‘passive’ portfolio will fall by $20\%$ – that is by $\$200,000$ . Normally, you are willing to tolerate this risk since there is an equivalent ‘up-side’ – should the stock market rally by $10\%$ , your portfolio would increase in value by $20\%$ . However, if your wish to completely hedge your stock portfolio using futures (when $F_{0}=200\mathrm{\Omega}$ ) you require:  

$$
N_{F}=-(V_{p}/V_{F})\beta_{p}=-(\S1\mathrm{m/(\S250\times200)})2=-40\mathrm{contracts}
$$  

By shorting 40 stock index futures contracts you have made the ‘efective beta’ of your ‘long stocks $+$ short futures’ portfolio equal to zero – the hedge has reduced your ‘efective beta’ from 2 to zero.  

Suppose you currently feel the market over the next 2 months is likely to be more volatile than normal and therefore you want to reduce but not eliminate your market exposure. For example, suppose your desired beta is $\beta_{d}=0.5\textrm{--}$ a reduction of $75\%$ compared to its current value of 2. To achieve a desired beta $\beta_{d}=0.5$ , you would short 30 futures contracts today $(=0.75\times40)$ and close out the position in 2 months’ time (when the efective beta of your stock portfolio would again revert to 2). This is cheaper than reducing your portfolio beta by selling some high beta stocks today and buying them back after 2 months (when you want to reinstate your portfolio beta of 2). The formula for the number of futures required to achieve your desired beta is:  

$$
N_{F}={\frac{V_{p}}{V_{F}}}(\beta_{d}-\beta_{p})={\frac{\mathfrak{H}1{\mathrm{m}}}{\mathfrak{H}250(200)}}(0.5-2)=-30{\mathrm{~contracts}}
$$  

By shorting 30 futures contracts today you have reduced your efective beta from 2 to 0.5. Hence if the market return moves up or down by $10\%$ the value of your hedged portfolio will change by only plus or minus $5\%$ – that is, by plus or minus $\$50,000$ . Without the futures hedge it would have changed by plus or minus $\$200,000$ . This ‘partial hedge’ has substantially reduced the volatility of your portfolio, compared with not being hedged – but (by construction) the volatility has not been reduced to zero – you are not fully hedged.  

# 6.5.2 Market Timing Using Index Futures  

Suppose the current beta of (a passive) stock portfolio is $\beta_{p}=2$ , so the return on your stock portfolio is $R_{p}=\beta_{p}R_{m}$ . If you think the market return is going to increase by a large amount in the near future then you could increase your return by selling some of your low-beta stocks and using the funds to buy high-beta stocks – thus increasing your overall portfolio beta to, say, $\beta_{p}=4$ . If the market return subsequently increases by $10\%$ as predicted, then you will make a return of $40\%$ (rather than $20\%$ ). You may then wish to revert back to having a desired portfolio beta of 2 and to achieve this you will have to reverse your previous trades. This method of increasing your beta just before a market rise and then returning to your initial beta may involve high transactions costs of buying and selling stocks (e.g. brokerage fees, bid–ask spreads, price impact efects, etc.). An alternative and cheaper method of increasing (decreasing) your exposure when you think the market will rise (or fall) is to use stock index futures.  

Suppose you hold a $\$10$ diversi!ed portfolio of stocks with $\beta_{p}=2$ . Above, we noted that you can completely hedge this position and efectively move to a beta of zero by shorting 40 futures contracts. By shorting 40 contracts your efective beta is reduced from 2 to zero. Now, suppose you think the stock market is going to rise (more than average) over the next two months. You could double the beta of your portfolio to a ‘desired beta’ of $\beta_{p}=4$ by buying 40 futures contracts today. Again, the formula required to achieve your desired beta is:  

$$
N_{F}=\frac{V_{p}}{V_{F}}(\beta_{d}-\beta_{p})=\frac{\S1\mathrm{m}}{\S250(200)}(4-2)=+40\mathrm{contracts}
$$  

If your prediction is correct and the stock market rises by say $10\%$ over the next 2 months, the value of your stock portfolio plus the cash pro!ts after closing out your long futures contracts, will result in the equivalent of a $40\%$ increase $(=\beta_{d}R_{m}=40\%)$ in value, from $\$10$ to $\$1.45$ . Without the long futures, you would have made only $20\%$ on your stock portfolio. With $N_{F}=40$ the change in value of the ‘stock $^+$ futures’ portfolio, using $R_{p}=\beta_{p}R_{m},d F/F=R_{m}$ and $R_{m}=0.10\left(10\%\right)$ is:  

$$
\begin{array}{r l}&{d V=V_{p}R_{p}+N_{F}V_{F}(d F/F)=V_{p}(\beta_{p}R_{m})+N_{F}V_{F}R_{m}}\\ &{\qquad=\$1m(2)0.10+40(50,000)0.10=(\S200,000+\S200,000)}\end{array}
$$  

Hence your new portfolio value is $\$1.45$ , made up of $\$200,000$ from the increase in value of your stock portfolio and a $\$200,000$ cash pro!t after closing out your index futures. You started with a $\$10$ stock portfolio and ended up being worth $\$1.45$ , an increase of $40\%$ . The stock market increased by $10\%$ but your wealth increased by $40\%$ – that is, you achieved an efective (desired) beta of 4.  

Here you have used SIF to leverage up the returns on your stock portfolio – this is exactly how some hedge funds leverage their returns (particularly those using ‘global macro-strategies’ on domestic and foreign stock markets). Of course, leverage is a ‘two-way street’, if you guess wrong and the stock market falls by $10\%$ , then you lose on both your stock portfolio and the long futures contracts and your total losses will be $40\%$ , $(\$400,000)$ – that is, a $\$200,000$ fall in the value of your stocks and a $\$200,000$ cash loss when you close out (i.e. sell) your long futures contract at a lower price.  

# 6.6 MERGER ARBITRAGE  

Suppose you want to purchase 1 million shares of !rm-A because after doing careful research, you believe it will be announced in 1 month’s time5 that !rm-A is a takeover target. However, other traders do not yet realise it is a takeover target. When the takeover is !nally announced or !nally agreed (after ‘due diligence’), you hope to make a speculative pro!t – as takeovers usually result in a rise in the target !rm’s price by over $30\%$ , when the takeover is announced/completed. This $30\%$ potential pro!t would be referred to as ‘the alpha from merger arbitrage’. Precisely what actions you take to ‘capture’ this potential $30\%$ pro!t depends on what risks you are willing to take and what risks you want to hedge.  

Clearly, to gain from the $30\%$ increase in price you need to purchase the stock before the takeover is announced (or information about the takeover leaks to the market). If you delay your purchases of stock-A, two things could happen. First, the stock market as a whole might increase, thus increasing the cost of purchasing stock-A in the future; and second, information about the takeover could become widely available and that would also increase the price of stock-A, before you have time to complete your speculative purchases.  

# 6.6.1 Using Stock Index Futures Contracts  

Consider the scenario whereby you do not think any information about the takeover will become available for at least 1 month. Suppose you want to ‘stagger’ your purchases over several days of the month using several brokers, so you do not alert other traders to your actions and put possible upward price pressure on target-A’s stock price. However, you also fear a general rise in the stock market over the next month (as the economy recovers) which would increase the purchase price of your target stock-A (this is ‘beta’ again) and hence reduce your speculative pro!ts.  

You can hedge this market risk by today going long stock index futures contracts (and closing them out when you are ready to purchase stock-A). Any gain on your index futures will ofset the higher cost of your purchases of stock-A over the next month – consequent on any rise in the market return. This is the ‘standard’ anticipatory hedge when you fear a price rise due to an increase in the market return.  

Assume !rm-A’s stock price is $\$3$ per share and $\beta_{A}=2$ . You want to buy 1m shares (in 1 month’s time) at a cost of $V_{A}=\$3m$ . The number of index futures contracts (with $F_{0}=200\mathrm{\Omega}$ you need to purchase today, to hedge the impact of a (possible) rise in the market as a whole is:  

$$
N_{F}=\frac{V_{A}}{V_{F}}\beta_{A}=\frac{\S3\mathrm{m}}{\S250(200)}2=120\mathrm{contracts}
$$  

Suppose the stock market rises $R_{m}=10\%$ over the next month. The net increase in cost of purchasing stock-A in 1 month’s time, after closing out your long index futures positions, is:  

increase in $\begin{array}{r}{c o s t{=}.}\end{array}$ Increase cost of stocks Gain from long index futures  

$$
\begin{array}{l}{{=V_{A}R_{A}-N_{F}V_{F}(d F/F)=V_{A}(\beta_{A}R_{m})-N_{F}V_{F}R_{m}}}\\ {{=\S3\mathrm{m}(2)0.10-120(\S250\times200)0.10=0}}\end{array}
$$  

If the market return increases by $10\%$ then stock-A’s price rises by $20\%$ $(\$600,000)$ but this extra cost of buying 1m stocks in !rm-A is completely ofset by the $\$600,000$ pro!t from closing out the long position in index futures. You have hedged the market risk of a future purchase of stock-A.6 The success of this hedge depends on an accurate measure of stock-A’s beta.  

A position in index futures protects you from market risk. But, if information about the takeover target ‘leaks out’ during the month, then stock-A’s price will move more than that given by its ‘beta’. Your index futures position only hedges the increase in the purchase price due to market risk – but any increase in price (during the month) because other traders push up the price due to a leak of information about the takeover, will not be hedged. (This is speci!c risk.)  

If you really believe information about the potential takeover announcement will become generally known to the market during the next month, then you need to purchase !rm-A’s shares immediately or before this information becomes widely known (and hence is incorporated in a higher market price of stock-A). However, if you purchase stock-A today you are also exposed to market risk – the market might fall substantially and this could wipe out (or substantially reduce) the $30\%$ pro!t, when the takeover is eventually announced. So once you have purchased the stocks you need to hedge this market risk by shorting (stock) index futures today – while waiting for the o\$cial announcement of the takeover.  

Hence, your future purchases of the stock can be hedged by going long SIF today. But once you actually purchase the stocks, you need to short index futures to hedge the stocks you now hold against a potential fall in the market return (while you wait for the merger announcement).  

# 6.6.2 Using Futures Contracts on Stock-A  

Alternatively, you can speculate on the takeover being announced/completed during the next month by today, purchasing futures contracts on stock-A. Note that you are purchasing futures on stock-A, not stock index futures.7 Also, here we assume you only take a position in futures contracts on stock-A and you do not buy stock-A on the NYSE. When the takeover is announced/completed then you can close out your futures positions on stock-A at a pro!t.8 As futures only require a small margin payment, you do not require much ‘own capital’ to set up your long futures position.  

Note, however, that if you are long futures contracts on stock-A, you are also exposed to market risk over the next month. If the market (S&P 500) falls then the price of stock-A will fall, as will the futures price of stock-A (because of arbitrageurs) – and you may have to close out your long futures at a loss. Clearly, your long futures position on stock-A will earn (net) pro!ts if the rise in price of stock-A, due to the takeover announcement, is not ofset by a fall in the price of stock-A due to a fall in the market – but there is no guarantee that this will happen.  

When you buy futures contracts on stock-A you are gambling on both the takeover being announced/completed and ‘the market’ not falling substantially. However, you can remove the market risk of your long position in the futures contract on stock-A by shorting index futures contracts. You then have a long position in futures on stock-A and a short position in stock index futures contracts – the former provides the pro!ts from the takeover announcement/completion and the latter provides protection against falls in the market return, while you wait for the takeover to be announced/completed. Just after the takeover is announced/completed you close out both the futures on stock-A and your index-futures contracts.  

There are other variants on the above scenarios. Hedge funds may not gamble on the future announcement of a takeover target because this is di\$cult to predict (unless you act on inside information, which is illegal). However, it has been noted that after the announcement of a takeover target, the stock price of the target tends to increase over the next 5–10 days and will rise further if the takeover is completed (after due diligence). The hedge fund can take advantage of this ‘post-announcement price drift’ by either buying stock-A or buying futures contracts on stock-A, on the day of the merger announcement. It could hedge either of these long positions by also shorting index futures to protect against falls in the price of stock-A due to falls in the market.  

In addition, hedge funds often go long the target company’s stock and short-sell the acquirer’s stock because the latter tends to fall slightly after the takeover announcement – this long-short position also provides some (but not total) protection against falls in the market return as it lowers the efective beta. If the hedge fund simultaneously implements several ‘merger arbitrage’ strategies then it will have a more diversi!ed portfolio and this will reduce the speci!c risk of these gambles. Finally, note that if the hedge fund relies on ‘post-announcement price drift’ and the proposed takeover is eventually abandoned, then the price of the target company tends to fall dramatically and the hedge fund’s long position in the target company will be closed out at a loss.  

# 6.7 SUMMARY  

• A hedge fund can implement a market timing strategy by altering the ‘efective beta’ of its existing stock portfolio by buying or selling index futures. A hedge fund can then achieve its desired level of exposure to changes in the market return (S&P 500).   
• If a hedge fund has a long position in a portfolio of stocks, it can increase its ‘efective beta’ by buying index futures when it thinks the market will rise in the future. Alternatively it can reduce its efective beta by selling index futures. If it sells enough index futures, the hedge fund can have an efective beta which is negative and hence pro!t if there is a fall in the market return in the future.   
• A ‘market-neutral’ hedge fund short-sells overpriced stocks, buys underpriced stocks and also holds some stocks that it thinks are correctly priced (to reduce speci!c risk). It may also alter the composition of its stock portfolio to ensure that the overall (dollar) beta is zero. The value of the market-neutral hedge fund’s stock portfolio is then protected from changes in the market return (e.g. S&P 500), but it can still bene!t when any over- or underpricing are corrected. The hedge fund can then close out its underand overpriced stocks at a pro!t.   
• Some ‘long-short’ hedge funds short-sell overpriced stocks and buy underpriced stocks but the resulting overall (dollar) beta of the stock portfolio may be non-zero – hence, it is not ‘market neutral’. Stock index futures can then be used to protect the value of this ‘active portfolio’ from changes in the market return (S&P 500) while the hedge fund waits for the mispricing in its ‘stock picks’ to be corrected.   
• A hedge fund that correctly identi!es a future takeover target (before other merger arbitrage funds) may stagger its purchases of the target’s stock, to avoid an adverse price impact which would raise the purchase price. Alternatively, it may have to wait until funds are available to purchase the stock. If it delays its purchases of the stock, a rise in the market will increase the cost of buying the stocks in the future. It can hedge the risk of the target’s stock price increasing, solely because of an increase in the market return, by buying stock index futures, today. Once the merger arbitrage hedge fund has purchased the target company’s stock then it can hedge the market risk by shorting index futures.  

# APPENDIX 6.A: STOCK PICKING AND MARKET RISK  

In this section we assume a hedge fund MoneyPlus only takes long positions in a portfolio of underpriced stocks – this makes the initial algebra fairly straightforward. Next we discuss short-selling. Then we show how short-selling can be incorporated in the analysis of hedging the market risk of a long-short portfolio of both underpriced and overpriced stocks.  

Suppose we hold a (long) stock portfolio with $V_{i}(>0)$ dollars in each stock, some of which we assume are potentially underpriced (and others are ‘correctly priced’). The total portfolio value is $V_{p}$ . Assume the portfolio return $R_{p}$ can be represented using the Single Index Model, SIM9  

$$
R_{p}=\alpha_{p}+\beta_{p}R_{m}+\varepsilon_{p}
$$  

where  

$$
R_{p}=\sum_{i=1}^{n}w_{i}R_{i},\quad w_{i}=V_{i}/V_{p},\quad V_{p}=\sum_{i=1}^{n}V_{i},\quad\sum_{i=1}^{n}w_{i}=1
$$  

and  

$$
\alpha_{p}=\sum_{i=1}^{n}w_{i}\alpha_{i},\quad\beta_{p}\equiv\sum_{i=1}^{n}w_{i}\beta_{i},\quad\varepsilon_{p}=\sum_{i=1}^{n}w_{i}\varepsilon_{i}
$$  

$\varepsilon_{i}$ is a random error which represents the speci!c risk of a stock and has an expected value of zero as does the speci!c risk on the portfolio of stocks $\varepsilon_{p}=\sum_{i=1}^{n}w_{i}\varepsilon_{i}$ . The portfolio alpha $\alpha_{p}$ is determined by the dollar amount held long $(V_{i}>0)$ in underpriced stocks $(\alpha_{i}>0)$ and the dollar amounts $V_{i}>0$ held in ‘correctly priced’ or ‘passive stocks’ $(\alpha_{i}=0)$ ) – the latter are included in the stock portfolio to reduce speci!c risk and reap the bene!ts of (naïve) diversi!cation.  

MoneyPlus buys individual ‘underpriced’ stocks to produce an expected positive value for $\alpha_{p}$ , and this would be referred to as an ‘active portfolio strategy’ or ‘stock picking’. For example, if MoneyPlus takes long positions in underpriced stocks which it forecasts will add $1\%$ over the next month to its portfolio return when their mispricing is corrected, then $\alpha_{p}=1\%$ , per month.10 Note that $\alpha_{p}$ is independent of movements in the market return and depends only on the mispricing being corrected in the future. But the overall return on the (unhedged) stock portfolio $R_{p}$ , depends on the market return, via the portfolio beta. To eliminate the market risk over the next month, the number of index futures contracts to short $\mathrm{is^{11}}$ :  

$$
N_{F}=-(V_{p}/V_{F})\beta_{p}
$$  

The change in value of the hedged-portfolio is:  

$$
\begin{array}{l}{{d V=V_{p}R_{p}+N_{F}V_{F}\left(d F/F\right)=V_{p}[\alpha_{p}+\beta_{p}R_{m}+\varepsilon_{p}]-\frac{V_{p}}{V_{F}}\beta_{p}(V_{F}R_{m})}}\\ {{\ }}\\ {{\ =V_{p}(\alpha_{p}+\varepsilon_{p})}}\end{array}
$$  

where $d F/F\approx R_{m}$ , as over short horizons the futures index moves with the stock market index (e.g. S&P 500). Portfolio speci!c risk $\varepsilon_{p}$ should be relatively small (i.e. close to zero) for a well-diversi!ed portfolio – however, it will not be zero, for any single hedge. The variability in the (dollar) outcome of a series of hedges (using Equation (6.A.3)) is:  

$$
\sigma_{d V}=V_{p}\sigma_{\varepsilon_{p}}
$$  

and the variability in the hedged return $R_{H}\equiv d V/V_{p}$ is $\sigma_{R_{H}}=\sigma_{\varepsilon_{p_{.}}}$ . From (6.A.4) and using results from OLS regression, it can be shown that the variance of the (dollar) hedging error is:  

$$
\sigma_{d V}^{2}=V_{p}^{2}\sigma_{R_{p}}^{2}(1-R s q)
$$  

is the regression $^{\circ}R$ -squared’ from the OLS regression of Equation (6.A.1)12: In moving from (6.A.4) to (6.A.5) we use $\sigma_{\varepsilon_{p}}^{2}=\sigma_{R_{p}}^{2}-\beta_{p}^{2}\sigma_{R_{n}}^{2}$ m(from 6.A.1) and the (OLS) de!nition, $R s q\equiv$ $\beta_{p}^{2}\sigma_{R_{m}}^{2}/\sigma_{R_{p}}^{2}$ .  

If the overall stock portfolio is ‘passive’ (i.e. contains only ‘correctly priced’ stocks) then $\alpha_{p}=0$ and from (6.A.3) the expected return on the hedged portfolio is zero. Note that this zero outcome for the hedged portfolio also depends on the estimated beta of the stock portfolio being an accurate (unbiased) estimate of the ‘true portfolio beta’. On the other hand, if the diversi!ed portfolio contains genuine underpriced stocks then the expected return on the hedge portfolio containing these ‘positive alpha-stocks’ is $E(d V/V_{p})=\alpha_{p}>0$ .  

For any stock portfolio, the out-turn value for portfolio speci!c risk $\varepsilon_{p}$ over a particular hedge period may not be zero. For example, if the portfolio consists of long positions in underpriced stocks but is hedged against market risk, there may still be some residual portfolio speci!c risk remaining. The impact on stock returns of environmental or regulatory risks, labour relations, IT failures, legal disputes, patents granted, etc. may vary across !rms in the portfolio but may not average out to zero, over the hedge period – that is, the out-turn for $\varepsilon_{p}$ may be positive or negative. This implies that even if MoneyPlus successfully picks underpriced stocks so that the out-turn value is $\alpha_{p}>0$ , the actual outcome for the hedged portfolio $d V=V_{p}(\alpha_{p}+\varepsilon_{p})$ is uncertain because the outcome for $\varepsilon_{p}$ is not known in advance.  

The hedge strategy relies on two elements. First, that the stock portfolio is well diversi!ed so that the out-turn value for $\varepsilon_{p}$ is ‘small’ (relative to $\alpha_{p.}$ ), over the 1-month period it expects the mispricing to be corrected.13 However, the latter cannot be guaranteed. Second, over repeated ‘stock picks’ in diferent months, the hedge fund expects that portfolio speci!c risk will average out to be relatively small over time.14  

The more diversi!ed the portfolio, the smaller is speci!c risk. Usually a reasonably small amount of speci!c risk may be achieved by holding around 25 ‘passive stocks’ (e.g. that could be chosen randomly from all stocks on the NYSE or more likely are chosen by sector, to match a particular passive index, such as a large cap or small cap index). These passive stocks could be ‘equally weighted’ which means that if you have a total of $\$1,000$ invested in 25 ‘passive stocks’ then you initially hold $\$40$ in each stock. As the value of your ‘passive stocks’ changes (some rise in price and others fall in price) then their total value might be $\$1,100$ (say) after one month. To maintain ‘equal weights’ you must now rebalance your ‘passive stocks’ so you have $\$44$ in each stock. Also, you have to choose the frequency with which you rebalance the portfolio back to equal weights and this depends on transactions costs of buying and selling stocks.  

Of course, the ‘passive component’ of your stock portfolio need not be equally weighted to achieve diversi!cation bene!ts (e.g. you might choose to use market capitalisation weights, or global minimum variance weights, or (‘fundamental’) weights based on the relative dollar earnings paid by each company, etc.). The ‘optimal choice’ for your passive weighting scheme is a matter of ongoing research (see, for example, DeMiguel et al. 2009) and some methods of choosing the appropriate weights are often referred to as ‘smart beta’ by professional investors. If you hold positions in several underpriced stocks that are not too large relative to your holdings in passive stocks, then the speci!c risk of your ‘active plus passive portfolio’ may remain relatively small – but some speci!c risk is always present.  

# APPENDIX 6.B: MARKET TIMING  

Suppose MoneyPlus holds a diversi!ed long position $V_{p}>0$ in a portfolio of stocks with an overall portfolio beta $\beta_{p}>0$ . But it wants to increase or decrease its exposure to market  

(systematic) risk and hence achieve a new ‘desired beta’. This can be done using stock index futures (on the S&P 500). We need to determine how many futures contracts $N_{F}$ are required to achieve a ‘desired beta’ $\beta_{d}$ .  

MoneyPlus continues to hold its initial stock portfolio and now takes a position in $N_{F}$ index futures contracts. The dollar change in value of MoneyPlus stocks plus $N_{F}$ futures (SIF) contracts is:  

$$
d V=V_{p}R_{p}+N_{F}V_{F}\left(d F/F\right)=V_{p}(\beta_{p}R_{m})+N_{F}V_{F}R_{m}
$$  

where $d F/F\approx R_{m}$ , $V_{F}=(\$250)F$ and the return on MoneyPlus initial stock portfolio is $R_{p}=$ $\beta_{p}R_{m}$ . If MoneyPlus desired beta is $\beta_{d}$ , then its desired portfolio return is $R_{p}^{d}=\beta_{d}R_{m}$ and hence, the desired dollar change in MoneyPlus stock portfolio is:  

$$
d\boldsymbol{V}^{d}=V_{p}R_{p}^{d}=V_{p}(\beta_{d}R_{m})
$$  

Equating (6.B.1) and (6.B.2) and solving for (the unknown) $N_{F}$ gives the required number of futures contracts for MoneyPlus to achieve its desired beta:  

$$
N_{F}=(V_{p}/V_{F})(\beta_{d}-\beta_{p})
$$  

For example, assume MoneyPlus currently holds a portfolio which is (net) long $(V_{p}>0)$ with $\beta_{p}>0$ , then alternative desired betas give rise to the following futures positions:  

If $\beta_{d}>\beta_{p}$ then $N_{F}>0$ (buy, go long futures) If $\beta_{d}<\beta_{p}$ then $N_{F}<0$ (sell, go short futures)  

Hence, if MoneyPlus wants a larger (smaller) efective beta than its current portfolio beta, then it should buy (sell) index futures today. Of course, even when MoneyPlus achieves its desired beta (using Equation (6.B.3)), the (ex-post) return on its hedged portfolio will also depend on $\alpha_{p}$ and $\varepsilon_{p}$ .  

# Special Cases  

Equation (6.B.3) subsumes our initial hedging result of Equation (6.B.1) above. When MoneyPlus wants to hedge all the market risk of its existing stock portfolio, then this implies that after taking a position in $N_{F}$ futures it wants a desired $\beta_{d}=0$ . Setting $\beta_{d}=0$ in (6.B.3) gives:  

$$
N_{F}=-(V_{p}/V_{F})\beta_{p}
$$  

For our second ‘special case’ suppose MoneyPlus holds no stocks $(\mathsf{s o}\beta_{p}=0)$ ). But by using only stock index futures contracts it wants to achieve an exposure to the market return, with a desired beta of $\beta_{d}$ $\displaystyle{3_{d}(=2\operatorname{say})}$ , on a notional dollar amount of $V_{p}=\mathfrak{F}1\mathrm{m}$ (say).15 Then MoneyPlus’  

required position in stock index futures is:  

$$
N_{F}=(V_{p}/V_{F})\beta_{d}
$$  

This may be a cheaper way of gaining exposure to the stock market than directly using MoneyPlus’ own funds to purchase an index tracker fund or an ETF.  

# APPENDIX 6.C: HEDGING: LONG-SHORT PORTFOLIO  

Long Position in Stocks  

The dollar change in value of long positions in $n$ -stocks with $V_{L,i}>0$ held in each stock is:  

$$
d V_{L}=\sum_{i=1}^{n}V_{L,i}R_{L,i}=\sum_{i=1}^{n}V_{L,i}(\beta_{L,i}R_{m})=(\S\beta_{L})R_{m}
$$  

where we assume (a simpli!ed Single Index Model/CAPM) $R_{L,i}=\beta_{L,i}R_{m}$ . The ‘dollar (long) beta’ is de!ned as $\S\beta_{L}\equiv\sum_{i=1}^{n}V_{L,i}\beta_{L,i}-$ it is a dollar weighted sum of the individual stock betas. For example, if the dollar-beta $\$3$ then a $1\%$ change in the market return will lead to a $\$3,000$ change in the value of the portfolio of (long) stocks. In !nance it is often convenient to express the dollar change in value using the portfolio return $R_{L}$ and the (standard) portfolio beta $\beta_{L}$ . An equivalent expression to (6.C.1) for $d V_{L}$ in terms of the portfolio return $R_{L}$ is:  

$$
d{\cal{V}}_{L}=\sum_{i=1}^{n}{\cal{V}}_{L,i}R_{L,i}=V_{L}\sum_{i=1}^{n}\frac{V_{L,i}}{V_{L}}R_{L,i}=V_{L}R_{L}
$$  

$$
=\sum_{i=1}^{n}V_{L,i},\quad R_{L}=\sum_{i=1}^{n}w_{L,i}R_{L,i},\quad w_{L,i}=\sum_{i=1}^{n}(V_{L,i}/V_{L}),\quad\sum_{i=1}^{n}w_{L,i}=1,
$$  

If we assu=me $R_{L,i}=\beta_{L,i}R_{m}$ then $R_{L}=\beta_{L}R_{m}$ w=here $\beta_{L}=\sum w_{L,i}\beta_{L,i}$ is the beta of the (long) portfolio then:  

$$
d V_{L}=V_{L}R_{L}=V_{L}(\beta_{L}R_{m})
$$  

Note that portfolio return $R_{L}$ and the beta of the portfolio $\beta_{L}$ are de!ned using $V_{L}$ in the denominator for the portfolio weights $w_{L,i}$ , which then sum to one – consistent with the usual textbook presentation. Also $R_{L}=\beta_{L}R_{m}$ and therefore the portfolio beta $\beta_{L}$ represents the relationship between the percentage return on the stock portfolio and the percentage return on the market index – this is the usual textbook representation of beta (and difers from the ‘dollar beta’ de!ned earlier, which relates the dollar change in portfolio value to the percentage change in the market return). However, both (6.C.1) and (6.C.3) give exactly the same value for $d V_{L}$ – they are just diferent ways of calculating $d V_{L}$ .  

# Short-sell Stocks  

Consider the change in value of a portfolio of $m$ -stocks when you have short-sold $V_{S,i}>0$ in each stock – note that we represent a short position as a positive value for $V_{S,i}$ . The change in value of the short position can be expressed in a similar fashion to the long position (but incorporating a minus sign where appropriate). First, using the ‘dollar beta’:  

$$
d\boldsymbol{V_{S}}=-\sum_{i=1}^{m}V_{S,i}R_{S,i}=-\sum_{i=1}^{m}V_{S,i}\beta_{S,i}R_{m}=-(\S\beta_{S})R_{m}
$$  

where the ‘dollar (short) beta’ is de!ned as $\S\beta_{S}\equiv\sum_{i=1}^{m}V_{S,i}\beta_{S,i}$ . In terms of the portfolio return and (standard) portfolio beta we have:  

$$
d{\cal{V}}_{S}=-\sum_{i=1}^{m}V_{S,i}R_{S,i}=-V_{S}\sum_{i=1}^{m}\frac{V_{S,i}}{V_{S}}R_{S,i}=-V_{S}R_{S}
$$  

where $V_{S}=\sum_{i=1}V_{S,i}$ $\sum_{i=1}^{m}V_{S,i},~R_{S}=\sum_{i=1}^{m}w_{S,i}R_{S,i},~w_{S,i}=\sum_{i=1}^{m}(V_{S,i}/V_{S}),~\sum_{i=1}^{m}w_{S,i}=1,$  

If we assume $R_{S,i}=\beta_{S,i}R_{m}$ then $R_{S}=\beta_{S}R_{m}$ where $\beta_{S}=\sum_{i=1}w_{S,i}\beta_{S,i}$ is the beta of the (short) portfolio then:  

$$
d V_{S}=-V_{S}R_{S}=-V_{S}(\beta_{S}R_{m})
$$  

# Hedging a Long-Short Stock Portfolio  

To hedge the long position or the short position in stocks, using stock index futures we require:  

$$
\begin{array}{r l}&{d V_{L}=V_{L}R_{L}+N_{F}^{L}V_{F}R_{m}=V_{L}(\beta_{L}R_{m})+N_{F}^{L}V_{F}R_{m}=0}\\ &{d V_{S}=-V_{S}R_{S}+N_{F}^{S}V_{F}R_{m}=V_{S}(\beta_{S}R_{m})+N_{F}^{S}V_{F}R_{m}=0}\end{array}
$$  

Hence: $N_{L}=-(V_{L}/V_{F})\beta_{L}$ (i.e. short futures) and $N_{S}=(V_{S}/V_{F})\beta_{S}$ (i.e. long futures).  

The net position in futures is therefore $N_{F}=N_{L}+N_{S}$ , which could be a net-long or net-short position depending on the dollar value of the long and short positions and their portfolio betas.  

# APPENDIX 6.D: MERGER ARBITRAGE AND HEDGING  

Long in Cash Market for Stock-A  

Assume today, MoneyPlus purchases $V_{A}=\$300,000$ stocks in the takeover target (stock-A) and hedges the market risk using stock index futures. The change in value of the stocks plus index futures position is:  

$$
\begin{array}{r l}{\lefteqn{d V=V_{A}R_{A}+N_{F}V_{F}(d F/F)}}\\ &{=V_{A}[\alpha_{A}+\beta_{A}R_{m}+\varepsilon_{A}]+N_{F}V_{F}R_{m}}\\ &{=V_{A}(\alpha_{A}+\varepsilon_{A})+[V_{A}\beta_{A}+N_{F}V_{F}]R_{m}}\end{array}
$$  

where we have used the SIM, $R_{A}=\alpha_{A}+\beta_{A}R_{m}+\varepsilon_{A}$ and using stock index futures implies $d F/F=R_{m}$ . To hedge the market risk, MoneyPlus shorts $N_{F}$ stock index futures contracts:  

$$
N_{F}=-(V_{A}/V_{F})\beta_{A}=-[\S300,000/\S250(200)]2=-12
$$  

When the merger announcement takes place, MoneyPlus closes out the stock index futures contracts, which compensates for any dollar change in the value of stock-A due to changes in the market return. To see this substitute (6.D.2) in (6.D.1):  

$$
d V=V_{A}(\alpha_{A}+\varepsilon_{A})
$$  

This leaves MoneyPlus with a potential abnormal percentage return (‘bid premium’) $\alpha_{A}=$ 0.30 ( $30\%$ say) due to merger arbitrage (and any positive or negative contribution due to speci!c risk $\pmb{\varepsilon}_{A}$ ).16  

# Long Futures on Stock-A  

Instead of purchasing stock-A in the cash market to take advantage of the merger arbitrage underpricing, assume MoneyPlus purchases futures contracts on stock-A, today. The contract size for futures on stock-A might be for delivery of $z_{A}=100$ stocks so that $V_{F}^{A}=z_{A}F_{A}$ , where $F_{A}=P_{A}\exp(r T)$ is the current price of a futures contract on stock-A (we assume the stock pays no dividends, over the speculative horizon considered). Assume the current spot price of stock-A is $P_{A}=\$3$ and $F_{A}=\$3.1$ .  

The futures price (on stock-A) in Chicago moves with the NYSE price of stock-A, $R_{A}\equiv$ $d P_{A}/P_{A}\approx d F_{A}/F_{A}$ . If MoneyPlus wants to take a long position in futures (on stock-A), equivalent to $a$ position of $V_{A}=\$300,000$ in the cash market, then it needs to choose the number of futures contracts $N_{F}^{A}$ so the dollar change in the futures position $d V_{F}^{A}$ equals that in the cash market $d V_{A}$ :  

$$
\begin{array}{l}{{d V_{A}=V_{A}R_{A}}}\\ {{{}}}\\ {{d V_{F}^{A}=N_{F}^{A}V_{F}^{A}(d F_{A}/F_{A})=N_{F}^{A}V_{F}^{A}R_{A}}}\end{array}
$$  

Hence: $N_{F}^{A}=V_{A}/V_{F}^{A}=\S300,000/(100(3.1))=967.74.$ . The long position in 968 futures contracts on stock-A gives MoneyPlus exposure to the merger announcement and to the market return. MoneyPlus may then choose to hedge its exposure to changes in the market return by going short 12 stock index futures (see Equation (6.D.2)). MoneyPlus can then close out both futures positions just after the merger announcement is made. It will earn the ‘bid premium’ on the rise in price of stock-A due to the merger announcement, after closing out its long futures contracts on stock-A at a higher price.  

Again, the above analysis applies to any strategy based on having ‘discovered’ (by any method) an underpriced stock-A and taking advantage of the perceived underpricing by using only futures contracts on stock-A (i.e. not stock index futures contracts). For overpriced stocks-B, the analysis is the same but you would short $N_{F}^{B}=V_{B}/V_{F}^{B}$ futures contracts on stock-B, to bene!t from the perceived overpricing.  

# EXERCISES  

# Question 1  

You are a stock analyst/trader and have just purchased a $\$100$ position in stock-XYZ which has a beta of 1.5 and based on current information, you believe it is underpriced by $6\%$ . You think the underpricing is likely to be ‘corrected’ within the year. However, you also think that the stock market may fall by $10\%$ over the next year and you wish to hedge against this fall, while still being able to take advantage of the underpricing of $6\%$ . The current level for index futures on the S&P 500 is 1,000 (points). Each contract is for $\$250$ .  

What information do you need in order to determine the optimum number of futures contracts to use in the hedge? What are the risks in your strategy?  

What is the outcome if the stock market does fall by $10\%$ and the mispricing of stock-XYZ is corrected? Assume that the stock index futures price also falls by $10\%$ .  

# Question 2  

How can stock index futures be used as a low cost speculative, ‘market timing’ strategy?  

# Question 3  

You are ‘long’ a diversi!ed portfolio of stocks a with current value of $\$200$ . The beta of your portfolio (with respect to the market portfolio) $=1.2$ . The value of the futures contract on the S&P 500 market index is $F_{0}=400$ points (each contract is for $\$250$ times the index).  

(a) How many futures contracts are required to hedge the portfolio of stocks? (b) If you want to reduce the ‘beta’ of the hedged portfolio to 0.6, what should you do?  

# Question 4  

You hold $\$200$ of OMG-stocks on 1 September and the stock index futures on the S&P 500 (stock index) is 1,600. You are forecasting an increase in the S&P 500 over the next 3 months and as your OMG-stocks have a beta of 1.5 these will also rise. How can you increase your exposure to the stock market using stock index futures on the S&P 500? What determines the number of futures contracts you need to increase your efective beta to 3?  

# Question 5  

It is 25 July and you are considering a takeover bid for the !rm Hotshots whose current stock price is $\$26$ with a beta of 1.8. You are going to purchase 100,000 stocks but not until 25 August. The stocks do not pay dividends. The yield curve is fat at $5\%$ p.a. (continuously compounded).  

The nearby September-futures contract on the S&P 500 expires on 25 September (i.e. in 2 months). The price of Hotshots stock on 25 August is $\$27.9$ .  

(a) If the S&P 500 index $S_{0}=1\small{,}000$ on 15 July and $S_{1}=1\mathrm{,}050$ on 25 August, what is the futures index on these two dates?   
(b) How might you hedge the cost of your purchases in August, using a futures contract on the S&P 500 $\$250$ per index point)?   
(c) What is the outcome of your hedge? Explain.  

# Question 6  

In September you decide that the S&P 500 stock index will increase over the next 3 months and hence your £10m portfolio of stocks with a beta of 1.8, will also increase in value.  

How can you increase your exposure to this rise in the S&P 500 using stock index futures, so that your efective (desired) beta is 2.5? What determines how many futures contracts you will buy or sell in September? The current level for index futures on the S&P 500 is 1,000 (points) and the tick value is $\$250$ .  