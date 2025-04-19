---
tags:
  - equity_prices
  - futures_prices
  - hedging
  - hypothetical_portfolio
  - stock_index_futures
aliases:
  - Index Futures
  - Stock Index Futures
  - Stock Indices
key_concepts:
  - futures prices and spot prices
  - hypothetical portfolio of stocks
  - index tracks capital gain/loss
  - stock index tracks
  - weights assigned to stocks
---

# 3.5 STOCK INDEX FUTURES  

We now move on to consider stock index futures and how they are used to hedge or manage exposures to equity prices.  

A stock index tracks changes in the value of a hypothetical portfolio of stocks. The weight of a stock in the portfolio at a particular time equals the proportion of the hypothetical portfolio invested in the stock at that time. The percentage increase in the stock index over a small interval of time is set equal to the percentage increase in the value of the hypothetical portfolio. Dividends are usually not included in the calculation so that the index tracks the capital gain/loss from investing in the portfolio.4  

If the hypothetical portfolio of stocks remains fixed, the weights assigned to individual stocks in the portfolio do not remain fixed. When the price of one particular stock in the portfolio rises more sharply than others, more weight is automatically given to that stock. Sometimes indices are constructed from a hypothetical portfolio consisting of one of each of a number of stocks. The weights assigned to the stocks are then proportional to their market prices, with adjustments being made when there are stock splits. Other indices are constructed so that weights are proportional to market capitalization (stock price $\times$ number of shares outstanding). The underlying portfolio is then automatically. adjusted to reflect stock splits, stock dividends, and new equity issues..  

# Stock Indices  

Table 3.3 shows futures prices for contracts on three different stock indices on May 21, 2021.  

The Dow Jones Industrial Average is based on a portfolio consisting of 30 blue-chip stocks in the United States. The weights given to the stocks are proportional to their prices. The CME Group trades two futures contracts on the index. One is on $\$10$ times  

Table 3.3 Futures quotes for a selection of CME Group contracts on stock indices on May 21, 2020.   


<html><body><table><tr><td></td><td>Open</td><td>High</td><td>Low</td><td>Prior settlement</td><td>Last trade</td><td>Change</td><td>Volume</td></tr><tr><td colspan="8">Mini Dow Jones Industrial Average, $5 times index</td></tr><tr><td>June 2020</td><td>24,545</td><td>24,660</td><td>24,300</td><td>24,519</td><td>24,421</td><td>-98</td><td>210,202</td></tr><tr><td>Sept.2020</td><td>24,426</td><td>24,542</td><td>24,212</td><td>24,411</td><td>24,311</td><td>-100</td><td>140</td></tr><tr><td colspan="8">Mini S&P 500, $50 times index</td></tr><tr><td>June2020</td><td>2,972.25</td><td>2,973.50</td><td>2,933.00</td><td>2,968.50</td><td>2,944.00</td><td>-24.50</td><td>1,542,213</td></tr><tr><td>Sept. 2020</td><td>2,963.00</td><td>2,964.75</td><td>2,924.75</td><td>2,959.75</td><td>2,935.50</td><td>-24.25</td><td>3,048</td></tr><tr><td>Dec.2020</td><td>2,939.50</td><td>2,955.50</td><td>2,928.25</td><td>2,954.50</td><td>2,930.00</td><td>-24.50</td><td>183</td></tr><tr><td colspan="8">Mini NASDAQ-100, $20 times index</td></tr><tr><td>Mar.2019</td><td>9,494.75</td><td>9,510.75</td><td>9,355.00</td><td>9,485.50</td><td>9,372.00</td><td>-113.50</td><td>420,841</td></tr><tr><td>June2019</td><td>9,470.75</td><td>9,495.00</td><td>9,349.50</td><td>9,469.75</td><td>9,360.75</td><td>-109.00</td><td>279</td></tr></table></body></html>  

the index. The other (the Mini DJ Industrial Average) is on $\$5$ times the index. The.   
Mini contract trades most actively.  

The Standard & Poor's 500 (S&P 500) Index is based on a portfolio of 500 different stocks: 400 industrials, 40 utilities, 20 transportation companies, and 40 financial institutions. The weights of the stocks in the portfolio at any given time are proportional. to their market capitalizations. The stocks are those of large publicly held companies that trade on NYSE Euronext or Nasdaq OMX. The CME Group trades two futures contracts on the S&P 500. One is on $\$250$ times the index; the other (the Mini S&P 500 contract) is on $\$50$ times the index. The Mini contract trades most actively.  

The Nasdaq-100 is based on a portfolio of 100 stocks traded on the Nasdaq exchange. with weights proportional to market capitalizations. The CME Group trades two futures contracts. One is on. $\$100$ times the index; the other (the Mini Nasdaq-100. contract) is on $\$20$ times the index. The Mini contract trades most actively..  

Some futures contracts on indices outside the United States are also traded actively. An example is the contract on the CSI 300 index, a market-capitalization-weighted index of 300 Chinese stocks, which trades on the China Financial Futures Exchange. (CFFEX, www.cffex.com.cn).  

As mentioned in Chapter 2,futures contracts on stock indices are settled in cash, not by delivery of the underlying asset. All contracts are marked to market to either the opening price or the closing price of the index on the last trading day, and the positions are then deemed to be closed. For example, contracts on the S&P 500 are closed out at the opening price of the S&P 500 index on the third Friday of the delivery month.  

# Hedging an Equity Portfolio  

Stock index futures can be used to hedge a well-diversified equity portfolio. Define:  

$V_{A}$ :Current value of the portfolio. $V_{F}$ :Current value of one futures contract (the futures price times the contract size)  

If the portfolio mirrors the index, the optimal hedge ratio can be assumed to be 1.0 and equation (3.3) shows that the number of futures contracts that should be shorted is.  

$$
N^{*}=\frac{V_{A}}{V_{F}}
$$  

Suppose, for example, that a portfolio worth. $\$5,050,000$ mirrors a well-diversified index. The index futures price is 1,010 and each futures contract is on $\$250$ times the index. In. this case $V_{A}=5\small{,}050{,}000$ and $V_{F}=1,010\times250=252{,}500.$ so that 20 contracts should be shorted to hedge the portfolio..  

When the portfolio does not mirror the index, we can use the capital asset pricing model (see the appendix to this chapter). The parameter beta $(\beta)$ from the capital asset pricing model is the slope of the best-fit line obtained when excess return on the portfolio over the risk-free rate is regressed against the excess return of the index over the risk-free rate. When. $\beta=1.0$ , the return on the portfolio tends to mirror the return on the index; when. $\beta=2.0$ , the excess return on the portfolio tends to be twice as great as the excess return on the index; when $\beta=0.5$ , it tends to be half as great; and. so on.  

A portfolio with a $\beta$ of 2.0 is twice as sensitive to movements in the index as a portfolio with a beta 1.0. It is therefore necessary to use twice as many contracts to hedge the portfolio. Similarly, a portfolio with a beta of 0.5 is half as sensitive to market movements as a portfolio with a beta of 1.0 and we should use half as many contracts to hedge it. In general,  

$$
N^{*}=\beta\frac{V_{A}}{V_{F}}
$$  

This formula assumes that the maturity of the futures contract is close to the maturity of the hedge.  

Comparing equation (3.5) with equation (3.3), we see that they imply. $\hat{h}=\beta$ . This is not surprising. The hedge ratio. $\hat{h}$ is the slope of the best-fit line when percentage one-. day changes in the portfolio are regressed against percentage one-day changes in the futures price of the index. Beta. $(\beta)$ is the slope of the best-fit line when the return from. the portfolio is regressed against the return for the index.  

We illustrate that this formula gives good results by extending our earlier example.. Suppose that a futures contract with 4 months to maturity is used to hedge the value of a portfolio over the next 3 months in the following situation:.  

Index level. $=1{,}000$   
Index futures price $=1{,}010$   
Value of portfolio $=\$5,050,000$   
Risk-free interest rate $=4\%$ per annum Dividend yield on index $=1\%$ per annum Beta of portfolio $=1.5$  

One futures contract is for delivery of. $\$250$ times the index. As before,. $V_{F}=$ $250\times1{,}010=252{,}500.$ From equation (3.5), the number of futures contracts that should be shorted to hedge the portfolio is.  

$$
1.5\times\frac{5,050,000}{252,500}=30
$$  

Suppose the index turns out to be 900 in 3 months and the futures price is 902. The gain from the short futures position is then  

$$
30\times(1010-902)\times250=\S810,000
$$  

The loss on the index is. $10\%$ . The index pays a dividend of. $1\%$ per annum, or. $0.25\%$ per 3 months. When dividends are taken into account, an investor in the index would therefore earn $-9.75\%$ over the 3-month period. Because the portfolio has a $\beta$ of 1.5, the capital asset pricing model gives  

The risk-free interest rate is approximately $1\%$ per 3 months. It follows that the expected return $(\%)$ on the portfolio during the 3 months when the 3-month return on the index is $-9.75\%$ is  

$$
1.0+[1.5\times(-9.75-1.0)]=-15.125
$$  

The expected value of the portfolio (inclusive of dividends) at the end of the 3 months is  

Table 3.4 Performance of stock index hedge.   


<html><body><table><tr><td>Valueofindexinthreemonths:</td><td>900</td><td>950</td><td>1,000</td><td>1,050</td><td>1,100</td></tr><tr><td>Futures price of index today:</td><td>1,010</td><td>1,010</td><td>1,010</td><td>1,010</td><td>1,010</td></tr><tr><td>Futures price of index</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>in three months:</td><td>902</td><td>952</td><td>1,003</td><td>1,053</td><td>1,103</td></tr><tr><td>Gain on futures position ($):</td><td>810,000</td><td>435,000</td><td>52,500</td><td></td><td>-322,500 -697,500</td></tr><tr><td>Return on market:</td><td>-9.750%</td><td>-4.750%</td><td>0.250%</td><td>5.250%</td><td>10.250%</td></tr><tr><td>Expected return on portfolio:</td><td></td><td>-15.125% -7.625% -0.125%</td><td></td><td>7.375%</td><td>14.875%</td></tr><tr><td>Expected portfolio value in three months including dividends ($):</td><td>:4,286,187</td><td>4,664,937 5,043,687 5,422,437 5,801,187</td><td></td><td></td><td></td></tr><tr><td>Total value of position</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>in three months ( ($):</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>5,096,187</td><td></td><td></td><td>75,099,937 5,096,187 5,099,937 5,103,687</td><td></td></tr></table></body></html>  

therefore  

$$
\$050,0000\times(1-0.15125)=\S4,286,187
$$  

It follows that the expected value of the hedger's position, including the gain on the hedge, is  

$$
\$4,286,187+5810,000
$$  

Table 3.4 summarizes these calculations together with similar calculations for other values of the index at maturity. It can be seen that the total expected value of the hedger's position in 3 months is almost independent of the value of the index. This is what one would expect if the hedge is a good one.  

The only thing we have not covered so far is the relationship between futures prices and spot prices. We will see in Chapter 5 that the 1,010 assumed for the futures price today is roughly what we would expect given the interest rate and dividend we are assuming. The same is true of the futures prices in 3 months shown in Table 3.4.5  

# Reasons for Hedging an Equity Portfolio  

Table 3.4 shows that the hedging procedure results in a value for the hedger's position. at the end of the 3-month period being about. $1\%$ higher than at the beginning of the. 3-month period. There is no surprise here. The risk-free rate is. $4\%$ per annum, or $1\%$ per 3 months. The hedge results in the investor's position growing at the risk-free rate.  

It is natural to ask why the hedger should go to the trouble of using futures contracts. To earn the risk-free interest rate, the hedger can simply sell the portfolio and invest the. proceeds in a risk-free security..  

One answer to this question is that hedging can be justified if the hedger feels that. the stocks in the portfolio have been chosen well. In these circumstances, the hedger might be very uncertain about the performance of the market as a whole, but confident that the stocks in the portfolio will outperform the market (after appropriate adjustments have been made for the beta of the portfolio). A hedge using index futures removes the risk arising from market moves and leaves the hedger exposed only to the performance of the portfolio relative to the market. This will be discussed further shortly. Another reason for hedging may be that the hedger is planning to hold a portfolio for a long period of time and requires short-term protection in an uncertain market situation. The alternative strategy of selling the portfolio and buying it back later might involve unacceptably high transaction costs.  

# Changing the Beta of a Portfolio  

In the example in Table 3.4, the beta of the hedger's portfolio is reduced to zero so that the hedger's expected return is almost independent of the performance of the index. Sometimes futures contracts are used to change the beta of a portfolio to some value other than zero. Continuing with our earlier example:.  

$$
{\begin{array}{r l}&{{\mathrm{Index~level}}=1,000}\ &{{\mathrm{Index~futures~price}}=1,010}\ &{{\mathrm{Value~of~portfolio}}=\S5,050,000}\ &{{\mathrm{Beta~of~portfolio}}=1.5}\end{array}}
$$  

As before, $V_{F}=250\times1,010=252{,}500$ and a complete hedge requires  

$$
1.5\times\frac{5,050,000}{252,500}=30
$$  

contracts to be shorted. To reduce the beta of the portfolio from 1.5 to 0.75, the number of contracts shorted should be 15 rather than 30; to increase the beta of the portfolio to 2.0, a long position in 10 contracts should be taken; and so on. In general, to change the beta of the portfolio from $\beta$ to $\boldsymbol{\beta}^{\ast}$ , where $\beta>\beta^{*}$ , a short position in  

$$
(\beta-\beta^{*})\frac{V_{A}}{V_{F}}
$$  

contracts is required. When $\beta<\beta^{*}$ , a long position in  

$$
(\beta^{*}-\beta)\frac{V_{A}}{V_{F}}
$$  

contracts is required.  

# Locking in the Benefits of Stock Picking  

Suppose you consider yourself to be good at picking stocks that will outperform the market. You own a single stock or a small portfolio of stocks. You do not know how well the market will perform over the next few months, but you are confident that your portfolio will do better than the market. What should you do?  

You should short. $\beta V_{A}/V_{F}$ index futures contracts, where. $\beta$ is the beta of your. portfolio, $V_{A}$ is the total value of the portfolio, and $V_{F}$ is the current value of one. index futures contract. If your portfolio performs better than a well-diversified portfolio with the same beta, you will then make money.  

Consider an investor who in April holds 20,000 shares of a company, each worth. $\$100$ The investor feels that the market will be very volatile over the next three months but that. the company has a good chance of outperforming the market. The investor decides to use the August futures contract on the Mini S&P 500 to hedge the market's return during the three-month period. The. $\beta$ of the company's stock is estimated at 1.1. Suppose that the current futures price for the August contract on the Mini S&P 500 is 2,100. Each contract. is for delivery of. $\$50$ times the index. In this case,. $V_{A}=20,000\times100=2,000,000$ and $V_{F}=2,100\times50=105,000.$ The number of contracts that should be shorted is therefore.  

$$
1.1\times\frac{2,000,000}{105,000}=20.95
$$  

Rounding to the nearest integer, the investor shorts 21 contracts, closing out the position in July. Suppose the company's stock price falls to $\$90$ and the futures price of the. Mini S& P 500 falls to 1,850. The investor loses $20\mathrm{,000}\times(\S100-\S90)=\S200\mathrm{,000}$ on the stock, while gaining $21\times50\times(2,100-1,850)=\S262,500$ on the futures contracts.  

The overall gain to the investor in this case is $\$62,500$ because the company's stock price did not go down by as much as a well-diversified portfolio with a $\beta$ of 1.1. If the market had gone up and the company's stock price went up by more than a portfolio with a $\beta$ of 1.1 (as expected by the investor), then a profit would be made in this case as well.  
