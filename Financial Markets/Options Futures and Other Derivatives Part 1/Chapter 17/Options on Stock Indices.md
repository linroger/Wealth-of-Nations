---
tags:
  - american_options
  - beta
  - cboe
  - index_options
  - portfolio_insurance
  - stock_indices
aliases:
  - Index Option Contracts
  - Index Options
  - Options on Indices
key_concepts:
  - Index option contract size
  - Index options cash settlement
  - Options on stock indices
  - Portfolio beta and options
  - Portfolio insurance with options
---

# 17.1 OPTIONS ON STOCK INDICES  

Several exchanges trade options on stock indices. Some of the indices track the movement of the market as a whole. Others are based on the performance of a particular sector (e.g., computer technology, oil and gas, transportation, or telecoms). Among the index options traded on the Chicago Board Options Exchange (CBOE) are American and European options on the S&P 100 (OEX and XEO), European options on the S&P 500 (SPX), European options on the Dow Jones Industrial Average (DJX), and European options on the Nasdaq 100 (NDX). In Chapter 10, we explained that the CBOE trades LEAPS and flex options on individual stocks. It also offers these option products on indices.  

One index option contract is usually on 100 times the index. (Note that the Dow Jones index used for index options is 0.01 times the usually quoted Dow Jones index.) Index options are settled in cash. This means that, on exercise of the option, the holder of a call option contract receives. $(S-K)\times100$ in cash and the writer of the option pays. this amount in cash, where. $S$ is the value of the index at the close of trading on the day of the exercise and. $K$ is the strike price. Similarly, the holder of a put option contract receives $(K-S)\times100$ in cash and the writer of the option pays this amount in cash.  

# Portfolio Insurance  

Portfolio managers can use options on a well-diversified index to limit their downside. risk. Suppose that the value of the index today is. $S_{0}$ . Consider a manager in charge of a well-diversified portfolio whose beta is 1.0. A beta of 1.0 implies that the returns from the portfolio mirror those from the index. Assuming the dividend yield from the portfolio is. the same as the dividend yield from the index, the percentage changes in the value of the portfolio can be expected to be approximately the same as the percentage changes in the value of the index. Since each contract is on 100 times the index, it follows that the value of the portfolio is protected against the possibility of the index falling below. $K$ if, for each $100S_{0}$ dollars in the portfolio, the manager buys one put option contract with strike price. $K$ Suppose that the manager's portfolio is worth $\$500,000$ and the value of the index is currently 1,000. The portfolio is worth 500 times the index. The manager can obtain insurance against the value of the portfolio dropping below $\$450,000$ in the next three months by buying five three-month put option contracts on the index with a strike price of 900.  

To illustrate how the insurance works, consider the situation where the index drops to 880 in three months. The portfolio will be worth about $\$440,000$ . The payoff from the options will be $5\times(900-880)\times100=\S10.000$ , bringing the total value of the portfolio up to the insured value of $\$450,000$  

# When the Portfolio's Beta Is Not 1.0  

If the portfolio's beta. $(\beta)$ is not $1.0,\beta$ put options must be purchased for each. $100S_{0}$ dollars in the portfolio, where. $S_{0}$ is the current value of the index. Suppose that the. $\$500,000$ portfolio just considered has a beta of 2.0 instead of 1.0. We continue to assume that the index is 1,000. The number of put options required is  

$$
2.0\times{\frac{500,000}{1,000\times100}}=10
$$  

rather than 5 as before.  

To calculate the appropriate strike price, the capital asset pricing model can be used (see the appendix to Chapter 3). Suppose that the risk free rate is $12\%$ , the dividend yield on both the index and the portfolio is. $4\%$ , and protection is required against the. value of the portfolio dropping below. $\$450,000$ in the next three months. Under the.  

Table 17.1  Calculation of expected value of portfolio when the index is 1,040 in three months and $\beta=2.0$   


<html><body><table><tr><td>Value of index in three months:</td><td>1,040</td></tr><tr><td>Return from change in index: Dividends from index:</td><td>40/1,000, or 4% per three months 0.25 × 4 = 1% per three months</td></tr><tr><td>Total return from index:</td><td>4 + 1 = 5% per three months</td></tr><tr><td>Risk-freeinterestrate:</td><td>0.25 × 12 = 3% per three months</td></tr><tr><td>Excessreturnfromindex over risk-freeinterestrate:</td><td>5 - 3 = 2% per three months</td></tr><tr><td>Expected excess return from portfolio</td><td></td></tr><tr><td>over risk-free interest rate:</td><td></td></tr><tr><td></td><td>2 × 2 = 4% per three months</td></tr><tr><td>Expected return from portfolio:</td><td>3 + 4 = 7% per three months</td></tr><tr><td>Dividends from portfolio:</td><td>0.25 × 4 = 1% per three months</td></tr><tr><td>Expected increase in value of portfolio:</td><td>7 - 1 = 6% per three months</td></tr><tr><td>Expected value of portfolio:</td><td>$500,000 × 1.06 = $530,000</td></tr></table></body></html>  

Table 17.2 Relationship between value of index and value of portfolio for. $\beta=2.0$   


<html><body><table><tr><td>Valueofindex inthreemonths</td><td>Value of portfolio in three months ($)</td></tr><tr><td>1,080</td><td>570,000</td></tr><tr><td>1,040</td><td>530,000</td></tr><tr><td>1,000</td><td>490,000</td></tr><tr><td>960</td><td>450,000</td></tr><tr><td>920</td><td>410,000</td></tr><tr><td>880</td><td>370,000</td></tr></table></body></html>  

capital asset pricing model, the expected excess return of a portfolio over the risk-free rate is assumed to equal beta times the excess return of the index portfolio over the riskfree rate. The model enables the expected value of the portfolio to be calculated for different values of the index at the end of three months. Table 17.1 shows the calculations for the case where the index is 1,040. In this case, the expected value of the portfolio at the end of the three months is $\$530,000$ Similar calculations can be carried out for other values of the index at the end of the three months. The results are shown in Table 17.2. The strike price for the options that are purchased should be the index level corresponding to the protection level required on the portfolio. In this case, the protection level is $\$450,000$ and so the correct strike price for the 10 put option contracts that are purchased is 960.'  

To illustrate how the insurance works, consider what happens if the value of the index falls to 880. As shown in Table 17.2, the value of the portfolio is then about $\$370,000$ The put options pay off $(960-880)\times10\times100=\S80{,}000$ , and this is exactly what is necessary to move the total value of the portfolio manager's position up from $\$370,000$ to the required level of. $\$450,000$  

The examples in this section show that there are two reasons why the cost of hedging. increases as the beta of a portfolio increases. More put options are required and they have a higher strike price..  
