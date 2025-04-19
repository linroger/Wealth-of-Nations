---
tags:
  - '#correlation_as_asset_class'
  - '#correlation_swap'
  - '#correlation_trading'
  - '#dispersion_trade'
  - '#equity_correlation'
  - '#hedge_funds'
  - '#implied_correlation'
  - '#pension_funds'
  - '#realized_correlation'
  - '#variance_dispersion_trade'
---
# 16.1 INTRODUCTION TO CORRELATION AS AN ASSET CLASS  

In the previous chapter, we saw that volatility as an asset class is firmly established. Developments in financial engineering did not stop at volatility and have continued their natural progression to correlation.. Equity correlation measures how much stock prices tend to move together. Correlation links the volatility of an index to the volatilities of component stocks. As an approximation, we can write:.  

Index volatility $\approx{\sqrt{\mathsf{c o r r e l a t i o n}}}\times$ average single stock volatility  

This formula shows that correlation is an important driver of index volatility. Historically, more than half of the changes in index volatility are driven by changes in correlation. This shows that correlation exposure is a fundamental component of volatility. Correlation risk is also an important. driver of returns on options and other assets such as hedge funds. How can we use the principles of financial engineering applied in previous chapters to correlation? It turns out that it is quite straightforward to back out the level of forward-looking correlation being priced by the market by calculating the relative levels of implied index and implied single-stock volatilities. As with implied index volatility, this implied correlation tends to trade at a premium to that realized correlation. Figure 16.1 shows the realized and implied correlation for the S&P500.  

![](df6dea373ff40a161b77c378359a54a3b6ebda5f518d4fe152a264709c2f00d7.jpg)  

# FIGURE 16.1  

Cash flows in a correlation swap.  

# 16.1.1 REASONS FOR TRADING CORRELATION  

The reasons for trading correlation are similar to the reasons for trading volatility:  

Since implied correlation has historically been above realized correlation, a short correlation (swap) position can be a good source of return. The hedge fund industry and several hedge fund. strategies are exposed to correlation risk as Buraschi et al. (2014) show.. Correlation is a major component of volatility and similar to volatility it is negatively correlated with equity index returns. Therefore, correlation trading can provide diversification benefits.. Since correlation is the residual from index and single-stock volatility, correlation trading can be used to express views and take positions regarding the relative moves of index versus singlestock volatility.  

# 16.1.2 CORRELATION TRADING VEHICLES  

There are two main vehicles for trading correlation, namely variance dispersion trades and correlation swaps.' Correlation swaps provide direct exposure to correlation. The payoff of a correlation. swap is the difference between the strike of the swap and the subsequent realized average correlation of a pre-agreed basket of stocks or index. Although correlation swaps provide the purest correlation risk exposure, they are less liquid than dispersion trades..  

In recent years, the most common vehicle for trading correlation has been the dispersion trade. The trade involves taking opposing positions in the volatility of an index (or basket) and the volatility of its constitutents. Since a dispersion trade is typically implemented by means of variance swaps, it is called a variance dispersion trade. If variance swaps are used to benefit from unexpectedly higher correlations, the trade consists of a short position in an index variance swap and long positions in single stock variance swaps. Sometimes, for simplicity, options are used instead of variance swaps to generate index and stock-level exposure to volatility.  

Acceptance of correlation as an asset class is growing as the following example illustrates.  

# EXAMPLE  

Correlation trading diversifies:  

With correlation at historic highs across many indices, traders continue to see investors rush to monetise the. widely-held view that correlation will fall over the next 12 months as macro-economic drivers become less prevalent in shaping investor sentiment, triggering the return of alpha strategies and increased stock. dispersion. After effectively shutting down amid heightened uncertainty in the wake of Lehman Brothers'. bankruptcy, correlation trading has been gaining traction in recent months..   
"The correlation market has been re-opened for more than a year now and although the dispersion trade is a standard trade, investors are now tracking every kind of correlation, both within and between different asset classes," said Stephane Mattatia, global head of financial engineering and advisory at SGCIB global. equity flow.  

In recent months, macro hedge funds have made substantial profits by taking leveraged bets on correlation between a variety of asset classes including S&P 500 versus euro-dollar, which was highly correlated following the crisis and broke in September 2009. The strong correlation between gold and euro-dollar, which was also widely traded, broke earlier this year.  

In equity dispersion markets, traders are seeing greater diversity of client types as numerous pension funds become active players, and a greater diversity of trade types is being implemented.  

While macro hedge funds continue to favour the dispersion trade--buying volatility swaps on separate stocks while selling volatility swaps on the index-options strategies such as dispersion straddles have increased in popularity as liquidity in more traditional products declines.  

"Funds are now building dispersion books and the key is diversification," said Mattatia. "They are trading all instrument types including straddles, variance swaps and volatility swaps, and looking across all indices. "  

(Thomson Reuters IFR 1850, Correlation trading diversifies', September 11, 2010)  

The above reading illustrates that correlation trading now extends across asset classes. Pension funds are mentioned as participants in correlation trading. They typically go long correlation swaps, which implies that they benefit when correlation unexpectedly increases. Macro hedge funds on the other hand are reported to be short correlation, by selling index and buying single stock variance swaps, thus benefiting when markets remain calm and correlations remain relatively low. To understand how correlation exposure can be created it is instructive to start with relatively simple correlation derivatives linked to one asset class, such as equities. Next we examine the replication and construction of dispersion traders and correlation swaps.  

The purest way to trade correlation is directly via a correlation swap. A correlation swap provides exposure to the average pairwise correlation of a predetermined basket of stocks. Average pairwise correlation $\rho_{A}$ is a simple equally weighted average of the correlations between all pairs of distinct stocks in an index:  

$$
\rho_{A}=\frac{2}{N(N-1)}\sum_{i<j}\rho_{i j}
$$  

where $\rho_{i j}$ is the pairwise correlation of the ith and jth stocks in a basket or index whose variance is given by $\begin{array}{r}{\sigma_{1}^{2}=\sum_{i}\omega_{i}^{2}\sigma_{i}^{2}+2\sum_{i<j}\omega_{i}\omega_{j}\sigma_{i}\sigma_{j}\rho_{i j}}\end{array}$ where $\omega_{i}$ and $\sigma_{i}$ are respectively the weight and the. volatility of the ith stock in the index.  

The swap strike is the level of (average pairwise) correlation that is bought or sold. It is typically scaled by a factor of 100 (that is a correlation of 0.5 is quoted as a strike of 50). Similar to the variance swap (discussed in the previous chapter), the payout of a correlation swap is the notional amount multiplied by the difference between the swap strike and the subsequent realized average pairwise correlation on the basket of underlyings:  

$$
\mathrm{Payout}=\mathrm{notional}\times(\mathrm{realizedaveragepairwisecorrelation}-\mathrm{strike})
$$  

Figure 16.1 shows the cash flows in a typical correlation swap cash flow. Let's examine a correlation swap example.  

# EXAMPLE: CORRELATION SWAPS  

Suppose that on January 6, 2014, a hedge fund sells a 6-month correlation swap on an equally weighted basket of stocks consisting of the constituents of the Eurostoxx 50 index. The counter-party is assumed to be a pension fund. The strike price is 40 and the notional amount is 1o,o00. This means that the hedge fund is short the correlation swap and the pension fund is long the swap. One way to interpret the transaction is to say that, for a fee, the hedge fund sells insurance against unexpected increases of the correlation to the pension fund.  

After 6 months, on July 6, 2014, we calculate the realized 6-month average pairwise correlation of the stocks in our basket as O.3. Then the buyer of the correlation swap, the pension fund, pays the following amount to the seller of the pension fund: Notional $\times(55-42)=610,000(40-30)=6100,000$  

In the above example, the hedge fund received a premium for bearing the risk of unexpected increases in correlations. A good proxy for the correlation strike, also known as implied correlation, is the square of the ratio between the implied index volatility and the average of the equity component implied volatilities (as implied volatility is a good estimate of the forward-realized volatility, we could then also infer that implied correlation is a good estimate of the forward-realized correlation).  

Historically the implied correlation, the strike, has been above the realized correlation. This is. illustrated in Figure 16.2 where the implied correlation is represented by the dashed line and the solid line represents the realized correlation.  

Although correlation swaps and variance swaps appear similar, the stochastic process followed by correlation and variance is different and therefore correlation and variance swaps allow the expression of different views in the form of directional trades or hedges as the following reading illustrates.  

# EXAMPLE  

Implied correlation hits multi-year lows  

Equity correlation has fallen in recent weeks alongside rising equity markets and plummeting volatility.. The result has been a renewed focus on dispersion trades and other strategies that seek to profit from. increased differentiation between stocks, sectors and global indices.. "For investors, dispersion is a great story in the current environment and an interesting market. parameter as it isn't a directional view. It's still very tricky to express a directional view on one market," said Arnaud Jobert, executive director, equity derivatives structuring at JP Morgan.. Despite a long-term rising trend, driven in part by a growing use of index and exchange traded products, implied correlation has dipped across global indices as well as at the sector and single stock level over the past year. And although it remains historically high, the measure is now trending back towards pre-crisis levels. Implied correlation across global indices hit multi-year lows last week as equities ramped up their January. rally with the S&P 500 hitting 1500 for the first time since 2007.. Over the course of just last week, two-year implied levels on a variety of index pairs including EuroStoxx. 50/Nikkei 225 and S&P 500/Nikkei 225 fell by more than five points.. Meanwhile, the CBOE's S&P 500 implied correlation index (January 2014 maturity), which estimates correlation between the index constituents based on options prices of the S&P 500 index itself and its 50.  

largest stocks, has fallen from 70 to 60 since the end of December, having traded in the 80s at the start of 2012.  

Macro shift  

Equity correlation pushed to record highs during the crisis as volatility spiked and investors fled equities for the safer haven of fixed income markets, leaving macro factors as the only real drivers of equity. performance. But even while volatility declined to historic lows, correlation remained relatively high as. abundant liquidity injected by worldwide central bank policy ensured that macro drivers outweighed other factors even as stock prices began to stage a rebound..  

However, that looks set to change as investors increasingly seek to express views on macro divergence as regions move towards different parts of their economic cycles.  

(Thomson Reuters IFR 1968, January 26, 2013)  

![](4a6fe2e18ad261c61011c6c5cbe1759ddd635a1c1163a4a474e59bd420634e92.jpg)  

# FIGURE 16.2  

Implied and realized correlation over time.  
