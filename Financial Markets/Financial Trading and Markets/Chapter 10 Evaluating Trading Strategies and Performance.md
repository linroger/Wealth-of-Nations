---
tags:
  - investment_portfolio
  - net_asset_value
  - portfolio_performance
  - risk_assessment
  - trading_strategies
aliases:
  - Portfolio Performance Analysis
  - Trading Strategy Evaluation
key_concepts:
  - Buy and hold strategy
  - Investment system
  - Net asset value (NAV)
  - Portfolio decision performance
  - Risk and return
---

# Evaluating Trading Strategies and Performance  

# 10.1 EVALUATING INVESTMENT PORTFOLIO PERFORMANCE  

A goal of every investor is to find an investment system that generates large profits. An investment system  is simply a security selection and combination strategy. Huge varieties of systems are used by investors, ranging from making purchase decisions based on moving averages to selling securities based on sunspot cycle theories. Many of these systems have made millions of dollars for investors. It should be noted that while perhaps each of these systems have worked well at some point in the past for some investors, or at least some investors have been lucky using them in the past, they might not perform well in the future. With thousands of investment systems in practice at any point in time, at least one might be expected to perform well over a period of time in any market, inasmuch as at least one out of thousands of randomly selected portfolios might be expected to perform well.  

Among the simplest of investment systems is the simple buy and hold into a diversified portfolio strategy. A large randomly selected portfolio or index portfolio might be used as a benchmark portfolio for comparison of any other investment system. Proper evaluation of an investment system does require consideration of a number of factors and statistical concerns. Perhaps, the most important and difficult of these to account for is risk. One should note that higher-risk portfolios would be expected to generate higher returns over extended periods of time. Furthermore, the evaluator might also wish to account for investor risk preferences or objectives when evaluating an investment system.  

One problem that we encounter when evaluating trading strategies and performance is separating the portfolio selection from the trading decisions. Many traders make both decisions simultaneously. In this section, we will focus first on the portfolio decision performance aspect of the trading decision, leaving trade execution aspects to later sections. The first step in the evaluation of portfolio decision performance is to measure the increase in asset or portfolio value relative to the initial asset value during a given time frame. These returns can then be adjusted by or compared to a relevant benchmark. In addition, the trader will want to evaluate the trading component of performance. This trading decision is often more difficult to evaluate than the overall portfolio performance.  
# Computing Net Asset Value and Returns  

Again, investment portfolio performance can be rather difficult to assess. First, standar diz ation of performance measures and selection of benchmarks are crucial for evaluations and portfolio comparisons. In the case where we evaluate a hypothetical mutual fund, we begin by valuing its net assets at the end of a given trading period, typically at the end of a day, with    $N A V_{t}$   computed as follows:  

$$
N A V_{t}={\frac{{\mathrm{Market~value~of~ascets~minus~limsq~BiLinus~let~the~end~of~time~}}t}{\#~{\mathrm{Sharees~outstending~at~time}}~t}}
$$  

Obviously, NAV depends more on the initial investment amount than on portfolio performance. Thus, it is useful to evaluate returns, which are NAV levels measured relative to initial investment amounts or prior NAV levels. If no capital is added or withdrawn from the fund between times  $t\mathrm{~-~}1$   and  $t,$   the fund’s return    $r_{t}$   for time    $t$   is computed from the change in its NAV during the period  $t$  :  

$$
r_{t}={\frac{N A V_{t}-N A V_{t-1}}{N A V_{t-1}}}
$$  

Equation (10.1)  provides a one-year return for the portfolio. Now, let’s consider the performance of a fund held for    $n$   years. It will be convenient to express returns on an annual basis, as is the convention for most institutions. The measurement of a geometric mean annual return  $r_{g}$   for a portfolio held for    $n$   years is fairly straightforward when there are no funds added to or withdrawn from the portfolio:  

$$
\bar{r}_{g}=\sqrt[n]{\frac{N A V_{n}}{N A V_{0}}}-1
$$  

However, matters can become more complicated when the fund’s investment base is changing. For example, fund investors might deposit and withdraw funds each day. When there is a cash flow    $C F_{t}$   moving in (a deposit to the fund would be represented by a positive value) or out of the portfolio (such as a withdrawal or redemption) at the beginning of each time period  $t$   for    $n$   periods, one might measure the    $n$  -period return with a variation of the internal rate of return  $r,$   solving the following for  $r.$  :  

$$
N A V_{n}=N A V_{0}(1\!+\!r)^{n}-\,\sum_{t=1}^{n}C F_{t}(1\!+\!r)^{n-t}
$$  

A return computed in this manner is called a  dollar-weighted return . For example, consider the case where a given cash flow    $C F_{t}$   was positive because the portfolio received a deposit from an investor. This increases the investment base of the portfolio, reducing the portfolio’s return if no compensating increase in the terminal asset value  $N A V_{n}$   is realized. This dollar-weighted return accounts for the addition (or subtraction) of cash flows to (or from)  
the fund. However, it does not fully account for compounding of returns over time. Bear in mind that computing this dollar-weighted return can be time consuming because substitution is usually required to obtain  $r$   and there can be instances when more than one    $r$  value will solve this equation.  

A second method for computing a return, the  time-weighted average return , requires periodic return computations each time a change to the investment base occurs:  

$$
\overline{{r}}_{g,p}=\sqrt[n]{\prod_{t=1}^{n}(1+r_{t})}-1
$$  

where    $r_{t},$   adjusted for dividends, is the fund return for a single period    $t$   and    $C F_{t}$   represents capital moving in (positive) or out of (negative) the fund at the start of each period  $t$   for  $n$  periods:  

$$
r_{t}={\frac{N A V_{t}-N A V_{t-1}+D I V_{t}-C F_{t}}{N A V_{t-1}}}
$$  

Generally, the time-weighted return will be a more meaningful measure because the returns on funds initially deposited into the portfolio will not be affected by future deposits or withdrawals.  

# Net Asset Value and Returns Illustration  

In  Table 10.1 , we illustrate NAVs and returns for a hypothetical Fund A for each of 10 days starting on January 3, 2017. Note that January 4 is a Friday, and that the fund will not trade over the weekend of January 5 and 6. A three-day return is calculated for January 9; the returns for January 4, 5, and 6 will be    $-3.92\%/3$   or    $-1.31\%$   each day.  

On January 2, the fund initiates activities with a contribution of   $\mathbb{\S}10\mathrm{,}000\mathrm{,}000$   by investors. No return is computed. On January 3, the fund realizes   $\mathbb{\S200,000}$   in trading profits, increasing its total assets to   $\mathbb{S}10{,}200{,}000$  , yielding a return of   $2.00\%$   for the day. On  

TABLE 10.1 Net Asset Value and Return Calculations 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/d25d4ca3b371d6898c1323a5375541194b390b94312ac69cdaa2c8573437c011.jpg)  
January 4, the fund incurred  $\mathbb{\S400,000}$   in trading losses, ending the day with   $\S9{,}800{,}000$  in total assets,   $\S9.8$   in NAV and a return of    $-3.92\%$   for the day, or    $-1.31\%$   for Friday, Saturday, and Sunday. Trading profits for January 7 were   $\S200{,}000$  ; the return was  $2\%$  . On January 8, the fund realized   $\mathbb{\S200,000}$   in trading profits, but paid a dividend of  $\mathbb{\S200,000}$  . NAV remained constant at   $\S10.00$   because the trading profits exactly offset the dividends. The return for the day was  $2\%$  . On January 9, the fund realized trading profits of   $\S200{,}000$  , and investors redeemed 19,608 shares at a value of   $\S10.20$   for a total of   $\mathbb{\S200,000}$  . This withdrawal did not affect NAV or returns. On January 10, investors purchased 19,037 shares for   $\S10.51$   each, totaling   $\mathbb{\S200,000}$  , which combined with trading profits of   $\mathbb{\S300,000}$   increasing total assets to  $\mathbb{\S}10{,}500{,}000$  . The investor contributions to the fund did not affect its  $3\%$   return for the day. On January 11, investor share purchases exceeded share redemption s by 9703. Trading losses for the day totaled  $\S200{,}000$  , producing a return of    $-1.9\%$  . The time-weighted average return for the fund is computed as follows:  

$$
\overline{{r}}_{g,p}=\sqrt[n]{\prod_{t=1}^{n}(1+r_{t})}-1=\sqrt[9]{(1.02)(0.9969)^{3}(1.0204)(1.02)(1.02)(1.03)(0.981)}-1=\sqrt[9]{(1.02)(0.9969)^{3}(1.0202)(1.03)(0.1)^{2}}
$$  

One minor note: The average daily weekend return of    $-1.31\%$   was computed as an arithmetic average; had it been computed as a geometric mean, it would have been    $-1.325\%$  .  

# Portfolio Benchmarking  

Higher returns are generally associated with higher risk. Proper risk-adjusted benchmarks for comparison need to be established when evaluating portfolio returns. Portfolio risk can be measured by portfolio standard deviation    $\upsigma_{p}$  . This portfolio standard deviation measures the risk of the portfolio as a function of the risk levels of individual securities, the investment proportions in the individual securities, and the level of diversification of the portfolio. Portfolio risk can also be measured by the sensitivity of the portfolio’s return to returns on the market portfolio, captured by the portfolio’s beta,  $\upbeta_{p},$   a measure of undivers if i able risk as per the Capital Asset Pricing Model (CAPM).   The following are three well-known risk adjusted measures for portfolio performance evaluation (see  Elton, Gruber, Brown, & Goetzman, 2010 ):  

$$
S_{p}=\frac{r_{p}-r_{f}}{\sigma_{p}}\,\quad T_{p}=\frac{r_{p}-r_{f}}{\upbeta_{p}}
$$  

The  Sharpe and Treynor ratios  calculate the portfolio’s reward to risk ratio, as a function of '  '  overall portfolio risk and as a function of portfolio sensitivity to the market. The  Jensen measure  ( Jensen, 1968 ) is often referred to as the portfolio alpha. Alpha measures the excess return of a portfolio beyond the time value of money and risk. A host of other measures have been described in the public literature, including the Sortino coefficient ( Sortino, 1996 ) and the M-square measure ( Modigliani & Modigliani, 1997 ).  
However, each of these measures has difficulties in addition to the proper computation of returns. For example, what exactly is the riskless rate of return for a given period? Analysts often use the six-month Treasury bill rate as a proxy, but what if the investor has a much longer investment horizon? The Jensen and Treynor measures require computation of market portfolio returns. What is the appropriate index for the market?  Roll (1977) shows that different indices (even if highly correlated) will lead to very different performance rankings. Note that the Sharpe ratio does not require a market proxy. Once returns have been computed, exactly how are portfolio betas computed? This may be a significant problem, given that the composition of the portfolio is likely to constantly be in transition. Should portfolio beta be computed as a “time-weighted” average of individual security betas, or based on historical portfolio returns?  

The following represent additional issues for investment institutions regarding the difficulties of using the above risk-adjusted portfolio performance measures:  

1.  Given that portfolio managers change jobs rather frequently, is it reasonable to measure fund performance rather than manager performance?

 2.  How frequently are we able to obtain enough data to obtain statistically significant measures of performance?

 3.  The CAPM, a model that decomposes return into compensation for time value of money and compensation for risk, serves as the basis for the Treynor and Jensen measures:  

 '  
$$
\mathrm{CAPM};\ E\left[r_{p}\right]=r_{f}+\left[\beta_{p}(r_{m}-r_{f})\right]
$$  

where    $E[r_{p}],\,r_{f},$   and  $r_{m}$   are the expected return on the portfolio, the riskless Treasury bill, and the market as a whole. However, the CAPM is only a single-time-period model. Multiple time periods and multiple cash flows cause problems in its application. In  

addition, many analysts will be concerned about the many assumptions that underlie the CAPM, as well as certain statistical tests that cast doubt on the empirical validity of  

the CAPM.

 4.  Investors holding funds representing only market segments might find that any measure based on the CAPM is inappropriate.

 5.  The Sharpe ratio will understate portfolio performance of un diversified portfolios in a setting where investors, in sum, hold numerous un diversified portfolios. That is, much of the risk captured in the Sharpe ratio can be diversified away. In addition, the Sharpe ratio is a better metric when portfolio returns are distributed normally. Skewness in returns will weaken the usefulness of the Sharpe ratio.

 6.  Errors in computing returns will bias measured betas downwards and will   $"\mathrm{slog}_{\mathrm{\Lambda}}$   over into un systematic variances (the part of risk that is unrelated to the market). Even seemingly minor problems can significantly bias beta measures. However, reasonably good correction procedures for betas measured with error do exist.  
# Portfolio Performance Benchmarking Illustration  

Here, we will use the Jensen alpha measure to evaluate the performance of a portfolio:  

'  
$$
J_{p}=\upalpha_{p}=[r_{p}-r_{f}]-\left[\upbeta_{p}(r_{m}-r_{f})\right]
$$  

Presumably, a positive alpha   $(\boldsymbol{\mathrm{o}}_{p})$   that is statistically significant will indicate that the portfolio outperforms the market on a risk-adjusted basis. Consider  Table 10.2 , which records returns over a 20-year period for a hypothetical portfolio   $(p)$   and the market along with riskless return rates.  

To compute the Jensen alpha measure, we first convert returns to risk premiums by subtracting riskless rates from returns on the portfolio and the market. We then run a regression of portfolio risk premiums against market risk premiums. The following represent the regression results and diagnostics:  

$\begin{array}{r}{\beta_{p}(r_{m,t}-r_{f,t})+e_{t}=\,0.073509\,+\,0.951512(r_{m,t}-r_{f,t})+e_{t}\,\,\,\,r\mathrm{-square}\,=\,0.865127}\\ {(8.5056)\,\quad\,(10.7452)\qquad\qquad\qquad\,\,\mathrm{d.f.}=18}\end{array}$  

The regression    $t.$  -statistics are reported in parentheses below the regression coefficients. First, we can conclude that the portfolio beta (0.951512) is statistically significant at the  $1\%$  level. The portfolio has slightly less systemic (market-related) risk than the market itself. The    $r.$  -squared value suggests that slightly more than  $86\%$   of this fund’s risk premiums are driven by market risk premiums. But most importantly, we can conclude that Jensen’s alpha is positive and statistically significant at the  $1\%$   level. Thus, the fund outperformed the market on a risk-adjusted basis for the reported period. Although we have concluded statistical significance for alpha, we should question the relevance of data as old as 20 years to evaluation of current fund management.  Figure 10.1  provides a pictorial display of our results.  

TABLE 10.2 Portfolio  $\boldsymbol{p}$   and Market Performance 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/5e8a37c86b4354b1376687ea9f6169ca605d3848b77a3158d6e893297553f156.jpg)  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/f8e7c347fde37532013bc9cd952b91c0ad9d41856c145036a705e02732a4fd96.jpg)  
FIGURE 10.1 Jensen’s alpha scatter diagram.  

# 10.2 MARKET TIMING VERSUS SELECTION  

Why might an investment portfolio earn consistently exceptional returns? First, higher risk portfolios tend to earn higher returns. This is why we benchmarked portfolios in the previous section. Second, strong portfolio performance might be due to simple luck. This is why we attempt to examine performance over many time periods and examine the statistical significance of our indicators. If an investment portfolio consistently earns higher than normal returns, it is useful to understand why. An important step in this process is to distinguish between skill at “security selection” and “market timing skill.” Suppose, for example, an analyst is able to discern the future direction of the market. In periods before anticipated market upswings, the analyst should recommend increasing the beta of her portfolio to exploit this upswing. In the case of an anticipated market downturn, the analyst should recommend decreasing the beta of the portfolio.  

# The Quadratic Variable Approach  

The CAPM concludes that there is a linear relationship between the risk premiums of well-diversified portfolios and risk premiums of the market portfolio, as in  Figure 10.1 . However, investors who correctly time the marker will shift their portfolios to lower betas during market downturns, shifting returns to be closer to the riskless rate. During market upturns, investors with strong timing ability will increase portfolio betas. Thus, for investors with strong market timing ability, the relationship between portfolio risk premiums and market risk premiums will be concave up as in  Figure 10.2 .  

We return to our portfolio and market data from  Table 10.2  in the previous section. We create an additional column for   $(r_{m,t}-r_{f,t})^{2}.$  , which will serve as a second explanatory variable (see  Treynor & Mazuy, 1966 ). This new testing variable accounts for the concave up relationship between portfolio and market risk premiums that strong timers will observe. We  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/4be3c266170d87a47a7b1a00b456bf45ae88d9e303f44edbe6e4d243d3d631c2.jpg)  
FIGURE 10.2 Jensen’s alpha and timing ability.  

now run a multiple regression to examine   $[r_{p,t}-r_{f,t}]$   relative to   $(r_{m,t}-r_{f,t})$   and  $(r_{m,t}-r_{f,t})^{2}$  . Our coefficient  $\upgamma_{p}$   for   $\breve{(r_{m,t}-r_{f,t})}^{2}$    reflects timing ability on the part of the manager. A positive coefficient  $\upgamma_{p}$   reflects the extent to which the manager shifts portfolios to reduce betas during periods of low market returns and the extent to which managers shift portfolio weights to increase beta during periods of high market returns. Since  $\upgamma_{p}$   below is not statistically significant, this manager does not exhibit significant market timing ability. However, because Jensen’s alpha is still positive and statistically significant, we conclude that this portfolio manager exhibits portfolio selection ability since overall performance seems superior.  

$$
\begin{array}{r l}&{r_{q,t}-r_{f,t}=\upalpha_{p}+\upbeta_{p}(r_{m,t}-r_{f,t})+\upgamma_{p}(r_{m,t}-r_{f,t})^{2}+e_{t}}\\ &{\qquad\qquad=0.0713+0.9605(r_{m,t}-r_{f,t})+0.2148(r_{m,f}-r_{f,t})^{2}+e_{t}}\end{array}
$$  

Consider a second portfolio  $q$   with returns given in  Table 10.3 . Market returns and riskless rates are identical; however, we will see that returns for this second portfolio reflect beta shifting in particularly strong and weak markets. A similar quadratic regression is run for this second portfolio to check for this apparent timing ability, and results reveal significant timing ability. The plot for the second regression is pictured in  Figure 10.2 . Regression parameters are given by the following equation:  

$$
\begin{array}{r l}&{r_{q,t}-r_{f,t}\!=\!\upalpha_{q}+\upbeta_{q}(r_{m,t}-r_{f,t})+\upgamma_{q}(r_{m,t}-r_{f,t})^{2}+e_{t}}\\ &{\qquad\qquad=0.0580+1.0004(r_{m,t}-r_{f,t})+2.0425(r_{m,f}\!-\!r_{f,t})^{2}+e_{t}}\end{array}
$$  
TABLE 10.3 Portfolio  $q$   and Market Performance 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/21494a7ed9ea5cb56191225d73c22ea537f9b9565626e440d03a7e4cfb9686c0.jpg)  

Coefficients    $\upalpha_{q}$   and  $\upbeta_{q}$   are statistically significant at the   $1\%$   level and coefficient  $\upgamma_{q}$   is significant at the   $6\%$   level. Thus, portfolio    $q$   reflects both superior overall performance  $(\upalpha_{q}=0.0580)$   and likely superior timing ability   $(\gamma_{q}=2.0425\,>\,0)$  . The upward concavity of the relationship between   $(r_{q,t}-\,r_{f,t})$   and   $(r_{m,t}-\,r_{f,t})$   suggests that the investor tends to shift her portfolio beta down (and portfolio returns up towards the riskless return rate) in weak markets, and that she tends to shift her portfolio beta up (and portfolio returns up further away from the riskless return rate) in strong markets. However, in a quadratic regression such as this, the analyst needs to be careful about interpreting    $\upalpha_{q}$  . For example, a negative or statistically insignificant    $\upalpha_{q}$   in this quadratic regression should not be interpreted to imply investment performance inferior to or on par with the market, particularly if    $\upgamma_{q}$   is positive and statistically significant.  

# The Dummy Variable Approach  

An alternative indicator of market timing is based on a regression including an interaction term, which is a combination of a dummy variable    $D$   (takes on a value of 0 or 1) and market risk premiums:  

$$
r_{q,t}-r_{f,t}=\upalpha_{q}+\upbeta_{q}(r_{m,t}-r_{f,t})+\upgamma_{q}D(r_{m,t}-r_{f,t})+e_{t}
$$  

$$
\mathrm{If}\;(r_{m t}-r_{f t})\,{<}\,0,\;D=1
$$  

Thus, if the market return equals or exceeds the riskless return,    $\upbeta_{q}$   is the portfolio beta; that is,    $\upbeta_{q}$   can be taken to be the up-market beta. If the market return is less than the riskless return,  $\upbeta_{q}-\upgamma_{q}$   can be taken to be the portfolio beta; that is,    $\upbeta_{q}-\upgamma_{q}$   is the down-market beta. The portfolio’s shift in beta is    $\upgamma_{q},$   so that a negative and statistically significant    $\upgamma_{q}$   is indicative of market timing ability. For our numerical illustration for portfolio    $q.$  , multiple regression results are reported as follows:  
$$
\begin{array}{r l}{r_{q,t}-r_{f,t}=\upalpha_{q}+\upbeta_{q}(r_{m,t}-r_{f,t})+\upgamma_{q}D(r_{m,t}-r_{f,t})+e_{t}}&{}\\ {=0.050+1.311(r_{m,t}-r_{f,t})\!-\!0.672D(r_{m,t}-r_{f,t})+e_{t}}&{}\\ {(2.931)\ (5.853)\quad\quad\quad\quad\quad(-1.928)}\end{array}
$$  

Coefficients    $\upalpha_{q}$   and    $\upbeta_{q}$   once again are statistically significant at the   $1\%$   level and coefficient

  $\upgamma_{q}$   is significant at the   $6\%$   level. Thus, portfolio    $q$   reflects superior overall performance

  $(\upalpha_{q}=0.050)$   and likely superior timing ability   $(\gamma_{q}=-0.672<0)$  . It appears that the portfolio manager shifts the beta of her portfolio down by 0.672 in down markets relative to up markets. Again in this regression with the interactive term, the analyst needs to be careful about interpreting    $\upalpha_{q}$  . For example, a negative or statistically insignificant    $\upalpha_{q}$   in this type of regression should not be interpreted to imply investment performance inferior to or on par with the market, particularly if  $\upgamma_{q}$   is positive and statistically significant.  

# 10.3 TRADE EVALUATION AND VOLUME-WEIGHTED AVERAGE PRICE  

The tools that we discussed in the previous two sections are particularly appropriate for evaluating portfolios and portfolio strategies over longer periods of time. Their focus is on overall portfolio performance, without distinguishing the trading aspect of the investment decision from the selection and timing aspects. Evaluating trader performance independently of portfolio performance is important for trading firms, portfolio managers, funds, and other financial institutions. Unfortunately, evaluating trader performance is not a simple task. The trading decision is different from the investing or portfolio management decision, and needs to be evaluated accordingly. We discussed portfolio benchmarking earlier; here, we discuss trade benchmarking. Trade benchmarking is generally based on comparing a trade or series of trades against the hypothetical results of a series of trades based on a specific or benchmark strategy.  

Traders are expected to seek the “best execution” for their transactions. But what is best execution? As we discussed earlier in the book, this concept is rather vague. The Chartered Financial Analyst (CFA) Institute’s trade-management guidelines (CFA, 2004) characterize best execution “as the trading process firms apply that seeks to maximize the value of a client’s portfolio within the client’s stated investment objectives and constraints.” Obviously, this characterization is ambiguous and difficult to quantify and its complexity leads to many problems. More generally, deciding on an appropriate evaluation metric or benchmarking strategy is a difficult decision. Many firms use one or more of the following:  

•  Volume-Weighted Average Price  (VWAP, introduced by  Berkowitz, Logue, & Noser, 1988 ): Calculated by dividing the dollar volume of trading in a stock by the share volume over a given period of time, typically one day.  
•  Arrival Price : The midpoint of the bid ' offer spread at the time the order is received (bid-ask midpoint or BAM). See also Section 6.4, Adverse Selection and the Spread.

 •  Market-on-Close  (MOC): The last price obtained by a trader at the end of the day relative to the last price reported by the exchange.

 •  Implementation shortfall : The performance difference between the hypothetical profits realized by a paper or theoretical portfolio replicating an actual portfolio ignoring friction costs and the profits realized by the actual portfolio.  

# VWAP  

VWAP, introduced by  Berkowitz et al. (1988)  and popularized by the trading consulting firm Abel/Noser, is the most commonly used of the trading evaluation metrics and benchmarks. VWAP is the average price at which a stock trades in a given period, weighted by the volume traded at each price. Suppose that a customer engaged a broker to purchase a large number of shares. Since the customer has already made the decision to invest in the shares, the broker should be evaluated only on the trade execution. VWAP can be used as a benchmark to evaluate the quality of the execution provided by the broker. If the brokerage firm’s purchases were made at a lower VWAP than the market VWAP for the relevant period, we might infer that the firm handled the order well for the customer. VWAP, either for the trader or for the market, is calculated as follows:  

$$
V W A P=\frac{\sum_{j}Q_{j}P_{j}}{\sum_{j}Q_{j}}
$$  

where    $Q_{j}$   represents the number of shares executed in a given order  $j$   at a price of    $P_{j}.$  Thus, VWAP is the transaction execution average price of over a given period of time. While VWAP is usually computed for the day of the trade, sometimes traders use multiday VWAP. This is likely when orders broken up for execution over several days. In addition, intraday VWAPs can be used for orders executed entirely within a given trading day or some portion thereof. A trader (broker) might be regarded to have abnormal trading performance if she can consistently beat the market or other relevant VWAP on her trades.  

One criticism of VWAP cost is that trader’s own trades will be included in the benchmark price. This is corrected by excluding from VWAP the trader’s own transactions, although it can cause problems when the trader’s own trades account for a significant portion of the total. Suppose, for example, that the trader was counter party to all security trades for that period. Obviously, VWAP would not be useful. But, this issue can arise whenever any illiquid security is being traded. One problem with performance evaluation based on daily VWAP benchmarks is that this benchmark can encourage traders to spread their trades out over the day simply avoid the risk of trading at the high or low prices for the day.  

VWAP is quick and easy to compute, understand, and compare. This simplicity is VWAP’s main strength. In addition, VWAP is also useful for securities that trade in different markets. However, VWAP becomes less meaningful when the security’s price trends up or down over the course of the trading period. In addition, VWAP does not account for costs related to trade delays, trade cancellations or failures to execute trades. In fact, VWAP is not useful when completing the transaction immediately is urgent. An immediate execution requirement does not allow the trader any discretion on which to be evaluated. Nor does VWAP account for slippage, the trader’s price impact on the security. Executing a large transaction at once can certainly impact the security price, but this impact will not necessarily adversely affect the broker’s apparent performance against VWAP. In fact, a trader might even be able to manipulate this price impact and VWAP by increasing the volume of his trades along with the impact on VWAP.  
Traders can practically always match VWAP by merely executing their transactions at the same prices and with the same proportional shifts in volume as the market over the transaction period. Forecasting volume is important for traders benchmarking against VWAP. For example, in U.S. markets, stock trade volume tends to be higher earlier in the morning and later in the afternoon sessions with lower volumes around midday. In European markets, volumes tend increase in afternoon hours when U.S. markets are open.  

# VWAP: A Simple Illustration  

Suppose that a broker has been instructed to purchase 600 shares at the market. She does so, purchasing them for a total price of 30,011. Market transactions over the security’s intraday execution period are listed in  Table 10.4 . The broker’s executed transactions were the second through fourth transactions in the table. The total volume of shares exchanged was 2500, with a total value of 125,098. Hence, VWAP for these transactions was 125,098/  $2500=50.0392$  . The broker purchased 100 shares in the second transaction at  $\S50.01$  , 400 shares in the third transaction at  $\S50.02,$   and 100 shares in the fourth transaction at   $\S50.02$  . The average share price paid by the broker was   $30{,}011/600=50{.}0183$  . Our calculations suggest that the broker beat the market VWAP. However, note that she did so by purchasing early or quickly in a rising market.  

TABLE 10.4 Price and Volume for VWAP Calculations 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/ea763bfd167acd6f0b84d39f4eab9a3e08f956d49eb4e52bc8bac4453e2a46a3.jpg)  
# 10.4 IMPLEMENTATION SHORTFALL  

A delay will likely occur between the time an investor, portfolio manager or broker decides to execute a transaction and when the transaction is actually executed. This delay may increase the cost of the transaction to the investor or portfolio manager. Implementation shortfall  can be defined as the difference in prices between the ideal transaction and the actual implemented transaction. The ideal transaction price is typically based on the security price existing when the transaction decision was made, or in the case of an agency broker, at the order arrival. The difference between this decision price and the actual implemented or execution price is construed to be implementation shortfall. Implementation shortfall is indicative of the quality of the trade execution.  

Suppose that a trader or portfolio manager makes a decision to buy or sell a security based on its current price, referred to here as its decision price. Similarly, an agency broker might instead use for her own trade execution evaluation the arrival price (e.g., bid/ask midpoint), the price of the security when she actually receives the order. However, since the execution price of an order normally differs from the original decision or arrival price, the actual implementation of an investment strategy by the trader, broker or portfolio manager leads to four primary types of friction or implementation costs. Implementation shortfall can be decomposed into these four types of friction costs:  

1.  Broker, exchange, and other explicit fees and commissions. Frequently, brokers bundle exchange, SEC, and other fees into their own commissions. Small transactions tend to have higher proportional explicit transactions costs.

 2.  Delay costs, based on the price difference between the portfolio manager’s decision price and the broker’s arrival price.

 3.  Price impact costs associated with transaction executions (slippage). Buy orders will exert upward price pressure on the security; sell orders will exert downward pressure. Larger transactions will tend to have larger impact costs.

 4.  Opportunity costs associated with transactions; that is, the opportunities and profits that were forgone prior to the trade’s completed execution. Opportunity costs can also include the portion of an order that was canceled due to an unfulfilled limit order restriction.  

We will seek to analyze and segregate these four types of costs, which will sum to implementation costs. First, to an extent, the costs of market impact, which increase as the execution speed of the transaction increases, balance against delay and opportunity costs, which increase as complete execution of the transaction is delayed. When paper portfolios are created for back-testing and other purposes, prices for transactions are taken from actual bid and offer quotations or from actual transactions taken from historical market data. These paper transactions do not normally include the costs of implementing the portfolio strategies. Implementation shortfall is the performance difference between the hypothetical profits realized by a paper or theoretical portfolio replicating an actual portfolio ignoring friction costs and the profits realized by the actual portfolio. That is, implementation shortfall is the difference between the decision or order arrival price and the realized price of the execution, including broker and exchange fees, slippage, and transaction opportunity costs.  
It can be difficult to distinguish these four types of implementation costs. Individual judgment is likely to play a role in segregating these costs. Brokerage, market and other explicit costs are usually straightforward. Opportunity costs can also be straightforward if their definition is limited to portions of orders canceled due to non-execution, perhaps due to order limits.  

# Illustration: Implementation Shortfall  

Suppose that a portfolio manager makes a decision to purchase 10,000 shares of a fairly illiquid stock one hour before its open, based on its  $\S50.00$   closing price the prior day (the decision or ideal price), and places a limit order to buy for 50.45. The stock opened at 9:30 at a price of 50.20, and 1000 shares are purchased at 9:31 at a price of 50.25. 50.25 can be considered to be the broker’s arrival price if orders arriving earlier had priority at the open. At 9:32, 5000 shares are purchased for 50.40, and 1000 more for 50.30 at 11:03. An additional 1000 shares are purchased for 50.30 at 2:15, the market price quickly rises to 50.48 and closes at 50.50 with 2000 shares in the order unexecuted. These transactions are represented in  Table 10.5 . The commissions, including all explicit fees, were   $\S0.01$   for each of 8000 shares. The total implementation cost is   $\S3980$  .  

The ideal portfolio profit, based on 10,000 shares, the  $\S50$   decision price and the following day closing price, is  $\S5000=\S505,\!000\!-\!\S500,\!000$  . Howe rized in  Table 10.5 , reveal an actual portfolio cost of \$402,980  $\S402,980=\S50,250+\S252,000+$   $\S50,300+\S50,350+\S80.$  . The end-of-following day portfolio value based on 8000 shares is

  $\S404{,}000$  , yi it of   $\S1020=\S404{,}000{-}\S402{,}980$   and an implementation shortfall of \$3980  $\S3980=\S5000{-}\S1020$  '  Table 10.6  breaks down the implementation shortfall into its component costs.  

Now, we will decompose the implementation shortfall into its various components. First, the delay to the first execution cost 0.25 per share, affecting all 10,000 shares for a total of   $\S2500$   in delay costs. The 11:03 transaction had additional per share delay costs of 0.05 for each of 1000 shares relative to the 9:31 transaction, and the 2:15 transaction had additional delay costs of   $\S0.10$   for each of 1000 shares, leading to a total of  

TABLE 10.5 Implementation Shortfall Executions 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/2c24ed41f5e3dcbfcb3c3ae31e4c5f9c04e00fee761aba85fe8a460824869a38.jpg)  
TABLE 10.6 Implementation Shortfall 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/07b776c7cd93003d8bda429cd3fa154fc770dcc935ac92477a6c3de4ce7472cc.jpg)  

$\S2500+50+100=\S2{,}650$   in total delay costs. The 5000 share transaction executed at 9:32 was particularly large and seemed to exert upward price pressure, as the price rose from 50.25 to 50.40 in about a minute. Potential price pressure is ignored on other transactions because it did not seem pronounced, and the transaction execution were sufficiently delayed relative to previous transactions to not be related. The price impact cost of this 9:32 transaction is estimated at   $5000\cdot(50.40-50.25)=\S750$  ailed to execute, with a “virtual” opportunity cost of 2000  $2000\times(50.50-50.00-0.25)=\S500,$   \$500, where 0.25 is the associated delay cost already accounted for. Thus,  Table 10.6  sums the implementation shortfall of the executions. This breakdown of the explicit and implicit implementation costs illustrates the typical magnitude of the implicit costs relative to the explicit transaction costs. To some extent, it can be difficult to assign costs to the various components, and different analysts, depending on the circumstances, may assign costs differently.  

# 10.5 VALUE AT RISK  

Value at Risk  ( VaR ) is a standard tool for risk management in financial institutions. It provides a figure for the loss in a portfolio over a given time frame, with a given set of distribution al assumptions at a given confidence level. In other words, in typical usage, if asset values are distributed normally with a given variance, the analyst can calculate a loss figure that will not be exceeded at a specified level of confidence. Thus, for example, with given normally distributed asset values, the analyst can calculate a “worst case scenario” at a given confidence level, typically  $95\%$   or  $99\%$  . For a confidence level of    $\upalpha=99\%$  , one can be   $99\%$   certain that at the end of the given time horizon there will be no greater loss than just the  VaR —as long as the model’s assumptions hold true. Thus, the  VaR model concerns the probability that a loss of a given size will not be exceeded over a given period of time:  

$$
\begin{array}{r l}&{V a R=A s s e t\;V a l u e\times D a i l y\;R e t u r n\;S t a n d a r d\;D e v i a t i o n}\\ &{\qquad\quad\times\;C o n f i d e n c e\;I n t e r v a l\;F a c t o r\times t h e\;S q u a r e\;R o o t\;o f\;T i m e}\\ &{V a R=A s s e t\;V a l u e\times\sigma\times z\times\sqrt{t}}\end{array}
$$  

Asset value is the total value of the institution, or its relevant unit, which might even be the portfolio of a single trader or desk. The daily (or some other time interval) return standard deviation applies to this asset value, the confidence interval factor represents the maximum acceptable probability that this loss will be exceeded (typically a   $\mathbf{Z}$  -value such as   $1\%$   from a normal distribution), and time is measured in days or some other period.  
# Derivatives Portfolio  VaR : Illustration  

Suppose a bank with  $\S1$   billion in its derivatives portfolio experiences a  $0.5\%$   standard deviation in its normally distributed daily returns. The one-tailed   $\mathbf{Z}$  -value corresponding with the  $1\%$   confidence interval is 2.326. The bank seeks to determine the size of a loss that has a  $1\%$   probability of being incurred over a five-day week:  

ﬃﬃﬃ 
$$
V a R=\S1,000,000,000\times0.005\times2.326\times\sqrt{5}=\S26,005,471
$$  

Thus, assuming that daily asset returns are normally distributed (this is an extremely important assumption) with a standard deviation of 0.005, there is a   $1\%$   probability that the bank will experience a loss exceeding  $\mathbb{S26,005,471}$  . While this figure is fairly small compared to the total asset level, its importance is enhanced by the bank’s borrowing levels. For example, if the bank were 30-to-1 debt financed, its initial equity level would be

  $\mathbb{S}33{,}333{,}333{\,}$  , and this loss would wipe out almost   $80\%$   of the bank’s equity stake. This

 \$26,005,471  VaR  figure would normally be regarded to be extremely high given the level of this bank’s equity capital. Thus, if bank profits are normally distributed,   $99\%$   of the time, losses realized by the institution will be less than the computed 5-day  VAR  figure. However, if the bank’s profits were not normally distributed as assumed, but instead were subject to a distribution with more extreme observations than implied by normal distributions (fat tails), equity capital might have a significantly higher probability of being wiped out after five days.  

Calculating, using, and interpreting  VaR  for a single asset with a known volatility and normal distribution of returns is fairly straightforward. As we will demonstrate shortly, the same is true for a portfolio of similarly “well-behaved” assets. However, portfolios of derivative securities or significantly different assets can be more of a problem. For example, the returns of put and call options are not normally distributed. Calculating  VaR  for a larger mix of options, even on a single security, can be quite difficult. Some traders will focus on deltas and gammas of portfolio components, but even these are problematic when underlying security variances are large. Recall from Chapter 9 that the “Greeks” only apply when underlying security price changes are small. But changes required to be consistent with   $95\%$   or  $99\%$   confidence intervals are normally large. In such instances,  VaR calculations can be facilitated with the use of Monte-Carlo simulations. Again, as we alluded to above, working with appropriate and realistic distributions is essential to interpreting  VaR .  

# Issues Arising with  VaR  Applications  

VaR  assumptions, methodology, and applications have been heavily criticized, in large part because of  VaR ’s reliance on potentially unrealistic assumptions and giving traders  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/840aeebabe8d1d8adc9b5066c25f2ed19163a633140a50cfb55f3411d9e8f2b1.jpg)  
FIGURE 10.3 Bottom  $1\%$   area under the normal curve.  

and institutions false hopes concerning their ability to measure and control risk. Perhaps the most important of these criticisms concerns the assumption of normally distributed returns. Notice in  Figure 10.3  the depiction of the narrow tails in the normal distribution, suggesting that the most disastrous outcomes (sometimes referred to in a risk measurement context as black swans) are very unlikely (see  Taleb [2010] ). If worst-case or nearworst-case scenarios are not actually rare, those extreme situations might instead be parts of  “fat tails,”  and their probabilities might be underestimated by the thin tails consistent with a normal distribution. Thus, do consider the implications of the normal distribution before relying too heavily on the assumption of normality. Remodel with another distribution if necessary. Similarly, if standard deviation is not the best or most complete measure of variability of returns, or if variability of returns does not provide a good indicator of risk, then adapt the  VaR  methodology to a more appropriate measure of risk, and/or rely on other risk measurement methods.  

# VaR  and  SPAN  

As discussed in Chapter 3, the Chicago Mercantile Exchange (CME) developed and implemented its  Standard Portfolio Analysis of Risk  ( SPAN ) model in 1988 to evaluate overall portfolio risk for its clients and other stakeholders. SPAN, and its updated generations such as SPAN2, are market simulations based on  VaR  methods and have served as widely used performance bond mechanisms or risk-based margin requirement calculations for a wide variety of combinations of securities and instruments. Older SPAN simulations typically calculated security and portfolio outcomes based on 16 potential “what-if” risk scenarios or hypothetical shocks in a grid. Newer simulations account for security correlations and many more scenarios. The outcomes of the simulations, conducted at least once per day by CME, can be used to evaluate the risk positions of relevant securities, combinations of securities, portfolios, and institutions themselves and to calculate performance bond (margin) requirements for CME clients, including exchanges and clearinghouses throughout the world.   Other exchanges have developed or are developing somewhat similar products, including Prisma (Eurex) and PAIRS (LCH).  
# Equity Portfolio  VaR : Illustration  

Here, we illustrate a simple  VaR  calculation for an equity portfolio made up of three stocks. For sake of simplicity, we will assume that portfolio returns are normally distributed. The trader has “borrowed”   $\S900{,}000$   from his employer and invested   $\mathbb{\S}100{,}000$   of his “own” money, for a total of   $\mathbb{S}1{,}000{,}000$  . This trader’s employer requires that the trader’s one-week portfolio  VaR  not exceed his trading capital of   $\mathbb{\S}100{,}000$  , with a  $99\%$   degree of confidence. We will examine the trader’s portfolio and its three component stocks to determine whether he is within his risk limits.  

Table 10.7  lists the three securities, 1, 2, and 3, along with their portfolio weights, annualized return variances, and co variances with each other. We calculate the portfolio variance with either  Equations (10.9) , ( 10.10) , or ( 10.11) .  Equation 10.9  is the general expression for an    $n$  -security portfolio variance.  Equation 10.10 , written for  $n=3$   securities, combines terms from  Equation 10.9 .  Equation 10.11  is simply  Equation 10.9 , written in matrix format for    $n\:=\:3$   securities.  Equation 10.11  might be the easiest to set up on a spreadsheet using the matrix multiplication calculation functions (see the Mathematics Appendix A.2 near the end of the text for matrix computation details). We find that portfolio variance equals 0.0904, and its standard deviation of returns is 0.3. Weekly  VaR  is calculated with  Equation (10.8)  within a  $99\%$   confidence interval, using a   $"Z"$   value of 2.326, and    $t=\sqrt{1/52}$  p years. This  VaR  calculation suggests that the trader’s portfolio does lie within his 99% confidence interval  VaR  risk limits for one week.  

$$
\sigma_{p}^{2}=\sum_{i=1}^{n}\sum_{j=1}^{n}w_{i}\;w_{j}\;\sigma_{i j}
$$  

σ 2  $\begin{array}{r}{\overline{{\qquad\quad}}=(w_{1}^{2}\bullet\sigma_{1}^{2})+(w_{2}^{2}\bullet\sigma_{2}^{2})+(w_{3}^{2}\bullet\sigma_{3}^{2})+2(w_{1}\bullet w_{2}\bullet\sigma_{1,2})+2(w_{1}\bullet w_{3}\bullet\sigma_{1,3})+2(w_{2}\bullet w_{3}\bullet\sigma_{1,3})}\end{array}$     σ   3 2 ; 3 Þ  $\begin{array}{r l}{\nu}&{=(0.04\,\cdot0\,.04)+(0.25\cdot0\,.16)(0.09\bullet0\,.36)+2(0.2\cdot0\,.5\cdot0.01)+2(0.2\cdot0.3\cdot0.04)}\\ &{\phantom{=}+2(0.5\cdot0\,.3\bullet0.04)=0.0904}\end{array}$     

2 
$$
r_{p}^{2}=\left[w_{1}\quad w_{2}\quad w_{3}\right]\left[\begin{array}{l l l}{\sigma_{1}^{2}}&{\sigma_{1,2}}&{\sigma_{1,3}}\\ {\sigma_{2,1}}&{\sigma_{2}^{2}}&{\sigma_{2,3}}\\ {\sigma_{3,1}}&{\sigma_{3,2}}&{\sigma_{3}^{2}}\end{array}\right]\left[\begin{array}{l}{w_{1}}\\ {w_{2}}\\ {w_{3}}\end{array}\right]=\left[0.2\quad0.5\quad0.3\right]\left[\begin{array}{l l l}{0.04}&{0.01}&{0.02}\\ {0.01}&{0.16}&{0.04}\\ {0.02}&{0.04}&{0.36}\end{array}\right]
$$
 64  

ﬃﬃ ﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃ p ﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃ 
$$
\begin{array}{r}{/a R=A s s e t\,V a l u e\times\sigma\times z\sqrt{t}=\S1,000,000\times\sqrt{0.0904}\times2.326\bullet\sqrt{1/52}=\S96,996.}\end{array}
$$
  :  

TABLE 10.7 Portfolio Weights and Security Characteristics 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/3784818144719498ef1fbeb79692ef4f20453a13088f3d901d5745bcd4c03b8c.jpg)  
We infer from this  VaR  calculation that there is a   $99\%$   chance that the loss on this million dollar portfolio will not exceed   $\S96{,}996{.}84$  , or approximately   $97\%$   of the trader’s equity capital.  

# Additional Reading  

The  CFA Institute’s (2004)  Trade Management Guidelines  is helpful for better understanding of the ambiguous concept of “best execution,” and the need for and how to establish trade execution policies, disclosures, and record-keeping. In addition, issues related to trade performance have appeared on recent CFA Level III exams and will appear on blogs and study sites related to the CFA Level III. The portfolio management textbook by Elton et al. (2010)  provides an excellent introduction to portfolio evaluation techniques in chapter 25.  Perold (1988)  provides a readable practitioner-oriented introduction to implementation shortfall, and  Hasbrouck (2007)  discusses implementation shortfall and trading costs in chapters 14 and 15.  Jorion (1997)  offers a standard and comprehensive introduction to  VaR .  Harris (2003)  offers excellent reading on transaction costs and performance evaluation in chapters 21 and 22.  Wagner (2008)  wrote a highly readable account of his personal experiences as a consultant in performance evaluation and with transaction costs. Chapter 9 of  Gregory (2014) provides a nice and somewhat more technical description of various margin and default fund methods, including  VaR  and its applications, particularly in a derivatives context.  

# References  

Berkowitz, S. A., Logue, D. E., & Noser, E. A. (1988). The total costs of transacting on the NYSE.  Journal of Finance , 43 , 97 ' 112. CFA Institute. (2004).  Trade management guidelines . Available at:  , http://www.cfapubs.org/doi/pdf/10.2469/ccb. v2004.n3.4007 .  Accessed 25.03.11. s s CME Group. (2019). CME SPAN : Standard Portfolio Analysis of Risk . Unpublished slides. Available at: , http://www.cmegroup.com/clearing/files/span-methodology.pdf .  Accessed 10.20.21. Elton, E., Gruber, M., Brown, S., & Goetzman, W. (2010).  Modern portfolio theory and investment analysis  (8th ed.). New York: John Wiley. Gregory, J. (2014).  Central counter parties: Mandatory clearing and bilateral margin requirements for OTC derivatives . Chichester, UK: Wiley. Harris, L. (2003).  Trading and exchanges: Market micro structure for practitioners . Oxford: Oxford University Press. Hasbrouck, J. (2007).  Empirical market micro structure: The institutions, economics and econometrics of securities trading . New York: Oxford University Press. Jensen, M. (1968). The performance of mutual funds in the period 1945 ' 1964.  Journal of Finance ,  23 (2), 389 ' 416. Jorion, P. (1997).  Value at risk . Chicago: Irwin Press. Modigliani, F., & Modigliani, L. (1997). Risk-adjusted performance.  Journal of Portfolio Management, Winter , 45 ' 54. Perold, A. (1988). The implementation shortfall: Paper versus reality.  Journal of Portfolio Management ,  14 (3), 4 ' 9. Roll, R. (1977). A critique of the asset pricing theory’s tests, Part I: On past and potential test ability of the theory. Journal of Financial Economics ,  4 (2), 129 ' 176. Sortino, F. (1996). On the use and misuse of downside risk.  Journal of Portfolio Management ,  22 (2), 35 ' 42. Taleb, N. N. (2010).  The Black Swan: The impact of the highly improbable  (2nd ed.). London: Penguin. Treynor, J. L., & Mazuy, M. (1966). Can mutual funds outguess the market?  Harvard Business Review ,  44 (4), 131 ' 136. Wagner, W. H. (2008). The incredible story of transaction cost management: A personal recollection.  Journal of  

Trading ,  3 (3), 8 ' 14. Available at:  , http://www.scribd.com/doc/6419002/Incredible-Story-of-Transaction-CostMeasurement .  Accessed 25.03.11.  
# 10.6 EXERCISES  

1.  On February 1, a hedge fund initiated activities with a trading account of   $\mathbb{1}{,}000{,}000$  and 20,000 outstanding shares of stock. On January 2, the fund realized  $\S30{,}000$   in trading profits. On February 3, the fund again realized  $\S30{,}000$   in trading profits, but paid a dividend of  $\S30{,}000$  . On February 4, the fund incurred  $\S50{,}000$   in trading losses. Trading profits for February 5 were  $\mathbb{S}10{,}000$  . In addition, on February 5, investors redeemed 1000 shares at the NAV. a.  What were NAVs for the fund for each day of the week beginning February 1?  

b.  What were daily returns for February 2 through February 5? c.  What was the time-weighted average return for this four-day period?  

2.  Suppose that we wished to compute monthly returns for Fund A over a period of five months. We collect relevant end-of-month NAVs along with any dividends. The following table lists NAV’s and dividends collected for Fund A from June 30 to November 30. Following the NAV data are sample return calculations:  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/79a3bbbb23fdf1a461c0d7fc1ee1cafdb8f69a6c666b7f2cb1c3528c1b7b2915.jpg)  

a.  Calculate returns for each month starting with July. b.  The following lists NAVs for Fund B. Calculate monthly returns for Fund B.  

Fund B 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/bb6857d1fe55a225605ac399881731faf9eda603798e9d8a37a356838b33b3ea.jpg)  

c.  Calculate geometric mean returns for Funds A and B. d.  Calculate time-weighted average returns for Funds A and B.

 3.  The following table provides historical  percentage  returns for the Patterson and Liston Funds along with percentage returns on the market portfolio (index or fund):  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/ab4d5167a72b1155710097cac0412cf0be9daf08c2849a8eff90e95f1dd09a40.jpg)  

Suppose that the riskless rate of return (or T-Bill rate) was  $3\%$   for each year. Calculate the following based on the preceding table:  

a.  Mean historical returns for the two funds and the market portfolio. b.  Variances associated with Patterson Fund returns and Liston Fund returns along with returns on the market portfolio. c.  The historical covariance and coefficient of correlation between returns of the Patterson Fund and returns on the market portfolio. d.  The historical covariance and coefficient of correlation between returns of the Liston Fund and returns on the market portfolio. e.  Historical betas for Patterson and Liston Funds, based on five years of returns data. (Note that the data sets are too limited in size to be considered very reliable.) f.  Suppose that a market return of  $8\%$   was obtained in the year 2017, and that the  $3\%$  riskless return for 2017 was . Further suppose that the Patterson and Liston Funds earned   $10\%$   and   $14\%$  , respectively, over 2017. Based on a Treynor Index, how did each of these funds perform relative to the market? g.  Comment on the 2017 risk-adjusted performance for each of the two funds based on Treynor Index results.  

4.  Historical returns for the Ripco Fund and the market portfolio along with Treasury bill (T-Bill) rates   $(r_{f})$   are summarized in the following table:  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/3c6a17e060a1de9a54181bfd6ed875cca5d8344f56ce85f567ca30cd9b1a3c7d.jpg)  
a.  Calculate the fund beta over the 20-year period. b.  Calculate Jensen’s alpha for the fund over the 20-year period. Did the fund outperform the market during this period based on Jensen’s alpha? c.  Based on a squared market risk premium term, does the Ripco Fund demonstrate market timing ability? d.  Based on an appropriate interaction term, does the Ripco Fund demonstrate market timing ability?  

5.  Many analysts argue that the Sharpe ratio is a more appropriate performance metric for an investor’s overall portfolio than for a given segment or sector of her portfolio. Prepare a statement to support this perspective.  

6.  Suppose that the market for Stock X on a given date consisted of the transactions listed in the following table. The left two columns represented transactions for Stock X, excluding the broker’s orders. The right two columns consisted of the broker’s orders only, all of which were orders to buy. What was the VWAP for shares of X stock for that day? What was the VWAP excluding the broker’s own orders? How did the broker perform relative to the market for his buy transactions?  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/57a10be291da502969fdc74601b5026f623b97f177ebf3e42d1a85e6144c04f4.jpg)  

7. a. On what factors does implementation shortfall depend? That is, what affects the various types of implementation costs?  

b.  Why might increasing the speed at which a large transaction is executed increase the implementation shortfall of an order? c.  Why might decreasing the speed at which a large transaction is executed increase the implementation shortfall of an order?  

8.  A fund manager decided to purchase 1000 shares of General Statics stock after the market closed with a price of 20. The fund manager placed a limit order at 20.15 to buy 1000 shares before the market opened on the following day. The market opened at 20.10. 400 shares of the limit order quickly executed at 20.10 and 400 more at the limit order price of 20.15. The remaining 200 shares of the order failed to execute and the market closed at 20.20. The commission paid to the broker was 0.04 per share.  
a.  Calculate the implementation shortfall for this order. b.  Decompose implementation shortfall into its commissions, delay costs, price impact costs, and opportunity costs components. c.  Is it possible for implementation costs to be negative? Why or why not? 9.  A small trading firm has a securities portfolio with a current value equal to  $\S80{,}000{,}000$  . The portfolio’s returns tend to be normally distributed with a  $1\%$   daily standard deviation and uncorrelated over time. The firm will use its  VaR  calculation to produce the maximum value of the loss that it is willing to incur on its portfolio at several thresholds. In particular, the firm seeks to calculate its portfolio  VaR  at   $95\%$  and  $99\%$   over a single day and over a 30-day month. That is, the firm seeks to calculate the maximum loss that it can incur at these probability thresholds. What are these four threshold values? How might these  VaR  figures be interpreted?

 10.  The  VaR  method can be applied to individual or institutional investment portfolios. For example, suppose that you have a  $\mathbb{\S}100{,}000$   asset portfolio for which you seek to compute  VaR . The portfolio experiences a   $1\%$   weekly standard deviation on its returns. What is the lower-end range size of a loss that occurs with  $5\%$   probability over a 4-week month?

 11.  What are the most essential criticisms of the  VaR  method as an indicator of stress of a financial institution (or unit thereof)?

 12.  An investor has combined securities X, Y, and  $Z$   into a portfolio. He has invested  $\mathbb{S}1000$   in Security X,  $\S2000$   into Security Y, and  $\S3000$   into Security Z. Security X has an expected return of  $10\%$  ; Security Y has an expected return of   $15\%$  ; and security Z has an expected return of   $20\%$  . The standard deviations associated with Securities X, Y, and  $Z$   are  $12\%$  ,   $18\%$  , and  $24\%$  , respectively. The coefficient of correlation between returns on Securities X and  $\Upsilon$   is 0.8; the correlation coefficient between X and Z returns is 0.7; and the correlation coefficient between  $\Upsilon$   and Z returns is 0.6. a.  Find the expected return and standard deviation of the resultant portfolio. b.  Over the course of one week, what is the  VaR  of this 3-security portfolio at the  $1\%$  confidence level?  
