---
tags:
  - capm
  - efficient_frontier
  - modern_portfolio_theory
  - portfolio_returns
  - risk_management
aliases:
  - MPT and CAPM
  - Markowitz Theory
  - Portfolio Optimization
key_concepts:
  - CSCO and XOM returns
  - Diversification effects
  - 'Efficient frontier: portfolios'
  - 'MPT: reward and risk'
  - 'Standard deviation: total risk'
---

# 11.3 THE MODERN PORTFOLIO THEORY AND THE CAPM  

The original modern portfolio theory (MPT), as laid out by Markowitz, and the CAPM have no time dimension. There is now, time prior to investment, and tomorrow, when we know how the investment turns out. Now the investor can work only with a probability distribution, best described by its first two moments. The mean, or expected return, measures the reward. The variance, or its cousin standard deviation, measures the risk. In MPT, standard deviation is synonymous with total risk. A stock whose price appreciates, but swings wildly up and down in the process, is considered risky. A stock whose price goes down, and swings wildly up and down in the process, is also considered risky, perhaps less risky if its standard deviation is lower.  

The way to think about the time dimension is to consider a repeated gambling process. Investors choose their stocks at the beginning of each month based on their probability assessments. A month later, the future reveals itself, and the investors settle their winnings or losings. Then they place new bets for the next month. In this set-up, it still makes sense to think in terms of probabilities, means, and standard deviations. The only potential trouble is that weekly, monthly, and quarterly data will produce different samples and different relative estimates of means and standard deviations.  

# 11.3.1 Diversification and the Efficient Frontier  

We perform a simple experiment. In Table 11.4, we have collected monthly stock returns2 for Cisco (CSCO) and Exxon Mobil (XOM) for 19 months from January 2005 to July 2006. We have added a column labeled "TBill' with a constant return of $0.2\%$ per month. We have also added two portfolio columns. The first labeled $\mathrm{}^{66}70/30^{\circ}$ contains the returns on a risky-risky portfolio invested $70\%$ in CSCO and $30\%$ in XOM. The second labeled $\mathrm{{}^{\leftarrow}60/40^{\mathrm{{}}}}$ contains the returns on a riskless-risky portfolio invested $40\%$ in TBill and. $60\%$ in XOM. We compute the means and standard deviations for all investment strategies. The CSCO-XOM correlation coefficient for the period is 0.08.  

Table 11.4 Risky-risky and riskless-risky portfolio returns   


<html><body><table><tr><td>Month</td><td>CSCO</td><td>XOM</td><td>70/30</td><td>"TBill"</td><td>XOM</td><td>40/60</td></tr><tr><td>Jul 2006</td><td>-8.83%</td><td>9.91%</td><td>-3.21%</td><td>0.20%</td><td>9.91%</td><td>6.02%</td></tr><tr><td>Jun 2006</td><td>-0.77%</td><td>0.72%</td><td>-0.32%</td><td>0.20%</td><td>0.72%</td><td>0.51%</td></tr><tr><td>May 2006</td><td>-6.25%</td><td>-2.99%</td><td>-5.27%</td><td>0.20%</td><td>-2.99%</td><td>-1.71%</td></tr><tr><td>Apr 2006</td><td>-3.38%</td><td>3.57%</td><td>-1.29%</td><td>0.20%</td><td>3.57%</td><td>2.22%</td></tr><tr><td>Mar 2006</td><td>6.83%</td><td>2.49%</td><td>5.52%</td><td>0.20%</td><td>2.49%</td><td>1.57%</td></tr><tr><td>Feb 2006</td><td>8.61%</td><td>-5.01%</td><td>4.53%</td><td>0.20%</td><td>-5.01%</td><td>-2.93%</td></tr><tr><td>Jan 2006</td><td>8.13%</td><td>11.07%</td><td>9.01%</td><td>0.20%</td><td>11.07%</td><td>6.72%</td></tr><tr><td>Dec2005</td><td>-2.42%</td><td>-3.25%</td><td>-2.67%</td><td>0.20%</td><td>-3.25%</td><td>-1.87%</td></tr><tr><td>Nov 2005</td><td>0.51%</td><td>3.82%</td><td>1.50%</td><td>0.20%</td><td>3.82%</td><td>2.37%</td></tr><tr><td>Oct 2005</td><td>-2.66%</td><td>-12.38%</td><td>-5.57%</td><td>0.20%</td><td>-12.38%</td><td>-7.35%</td></tr><tr><td>Sep 2005</td><td>1.69%</td><td>5.90%</td><td>2.95%</td><td>0.20%</td><td>5.90%</td><td>3.62%</td></tr><tr><td>Aug 2005</td><td>-8.33%</td><td>2.43%</td><td>-5.10%</td><td>0.20%</td><td>2.43%</td><td>1.54%</td></tr><tr><td>Jul 2005</td><td>0.37%</td><td>2.19%</td><td>0.91%</td><td>0.20%</td><td>2.19%</td><td>1.39%</td></tr><tr><td>Jun 2005</td><td>-1.66%</td><td>2.24%</td><td>-0.49%</td><td>0.20%</td><td>2.24%</td><td>1.42%</td></tr><tr><td>May 2005</td><td>11.63%</td><td>-0.94%</td><td>7.86%</td><td>0.20%</td><td>-0.94%</td><td>-0.49%</td></tr><tr><td>Apr 2005</td><td>-3.53%</td><td>-4.42%</td><td>-3.79%</td><td>0.20%</td><td>-4.42%</td><td>-2.57%</td></tr><tr><td>Mar 2005</td><td>2.66%</td><td>-6.04%</td><td>0.05%</td><td>0.20%</td><td>-6.04%</td><td>-3.54%</td></tr><tr><td>Feb 2005</td><td>-3.50%</td><td>20.94%</td><td>3.84%</td><td>0.20%</td><td>20.94%</td><td>12.65%</td></tr><tr><td>Jan 2005</td><td>-6.85%</td><td>0.66%</td><td>-4.60%</td><td>0.20%</td><td>0.66%</td><td>0.48%</td></tr><tr><td>Avg.</td><td>-0.41%</td><td>1.63%</td><td>0.20%</td><td>0.20%</td><td>1.63%</td><td>1.06%</td></tr><tr><td>St.Dev</td><td>5.85%</td><td>7.26%</td><td>4.47%</td><td>0.00%</td><td>7.26%</td><td>4.36%</td></tr></table></body></html>  

Figure 11.2 shows the information graphically. In the first graph, what stands out is that,. while the mean of the 70/30 portfolio is simply the average of the means, the standard the. standard deviation of the 70/30 portfolio is lower than the standard deviation of either CSCO or XOM. Because of the imperfect correlation between the two stocks, we achieve risk reduction.. In the second graph, both the mean and the standard deviation of the 40/60 portfolio are the. averages of the individual means and standard deviations..  

In MPT, the efficient frontier is a generalization of the left-hand graph in Figure 11.2 and the line we added to show where all the combinations of CsCO and XOM with varying investment proportions would be. The efficient frontier is the locus of all the "best' stocks and all the "best' portfolios consisting of the stocks (including all combinations of stocks and all. weight combinations) in the mean-standard deviation space. Because few stocks are perfectly positively correlated, we achieve diversification effects with many portfolios, moving them to the left relative to the component stocks while getting the average return. The "best"' here means the lowest standard deviation for a given level of expected return and/or the highest expected return for a given level of standard deviation. Conversely, it also means that horizontally there is no combination of stocks with a lower risk for a given level of expected return than that. on the frontier. Figure 11.3 shows the efficient frontier of the best risky-risky combinations drawn in the mean-standard deviation space. Stocks are portrayed as white dots, portfolios as. black dots. The efficient frontier traces out the northwestern contour of the cloud containing. stocks and their combinations. No rational investor chooses to put all of his money into any. dot in the interior of the cloud. Rational investors choose only from the efficient frontier menu. Risk-averse investors choose the portfolios on the lower part of the frontier (lower risk), less risk-averse on the upper part (higher risk)..  

![](e00909eb7bafc4c9e1197128fe23f71748d038049e02163301eacd34bce3b471.jpg)  
Figure 11.2 $Y=$ mean vs $X=\operatorname{st}$ deviation for risky-risky and riskless-risky portfolios  

![](ca113408abf77043b4628fe4aaaa84fa84052da86b97a28b808a2b447ccb5008.jpg)  
Figure 11.3 The efficient frontier of risky assets and portfolios  

# 11.3.2Two-Fund Separation  

In Figure 11.3, we also show the locus of portfolios that are even better than those on the efficient frontier. These are labeled "CML' for the capital market line. The CML portfolios lie to the northwest of the efficient frontier. They offer even better reward-to-risk tradeoffs: lower risk for a given return or higher return for a given level of risk. However, these combinations are not risky-risky of stocks alone. These are the combinations of the risk-free asset (the T-Bill), which has zero risk and lies on the vertical axis, and of the tangent portfolio, one very special portfolio lying on the efficient frontier. The CML is the generalization of the right-hand graph of Figure 11.2 with a riskless-risky combinations lying on a straight line.  

In order to achieve the best reward-to-risk tradeoff, investors must divide their money between the T-Bill and the tangent portfolio. What is the tangent portfolio? If all investors are risk-averse and think in mean-variance terms and all choose to diversify, then no investors choose the portfolios on the efficient frontier except for the tangent one. They combine it with the risk-free asset. All investors compute the same weights for the stocks in the preferred risky-risky part of their portfolio. If they compute the same weights, they all own a part of the same portfolio - just as if there was only one investor in the whole market called the representative agent. The agent owns a portfolio of stocks, and all the stocks are owned by someone. But there is only one investor, so that investor owns all the stocks. This simple accounting argument leads to the identification of the tangent portfolio as the capitalizationweighted portfolio of all the stocks in the market. The weights in the portfolio are simply the total dollar numbers it would take to buy all the stocks in the entire economy.  

The two-fund separation theorem states that the best portfolio choices for a mean-variance investor lie on the CML and the investor does not have consider all the combinations of assets (including riskless), but can divide his job into two stages. First, based on his risk aversion. he must decide where on the CML he wants to be, lower left or upper right. This decision on how many dollars to allocate to the risk-free asset and how many to the risky assets is called the asset allocation decision. Second, the investor must invest the allocated risky dollars to the cap-weighted market portfolio, and not to try to beat the market in some way. In modern. financial advising, that second stage means choosing an index fund and supplementing it with non-equity asset classes to represent the entire universe of risky assets.  

# 11.3.3 Systematic Risk and the CAPM  

If all investors engage in indexing with their risky dollars, then no investors ever hold stocks individually. If they never hold stocks individually, they never experience the standard deviation risk of a stock. Investors are never exposed to the total "wiggliness" of the stock's price as this total risk is muted in their diversified portfolios. The total risk is not priced in the market, but only the portion of risk that contributes to the wiggliness of the market portfolio (which is what all investors own). In statistics we use ANOVA to break down the total variance into the explained variance and the residual variance. The total risk of the individual stock can be broken into systematic risk (explained variance) and specific risk (residual variance). The systematic portion can be thought of as coming from the common market factors; the specific portion comes from any unique risk posed by the stock's individual characteristics. If investors always form diversified portfolios, and always end up with the same overall market portfolio, then the systematic risk can further be identified as that pertaining to market portfolio risk. Since we are optimizing in mean-variance terms - which is what a regression process does (minimize sum of squared deviations from the characteristic line) - the systematic portion of the stock risk can also be precisely defined as the slope coefficient of the regression of a security's excess returns on the market portfolio's excess return. The excess return, or the risk premium, is defined as the difference between the return and the risk-free return. Statistically, the total return (variance) can be broken into two parts:  

$$
\sigma_{i}^{2}=\beta_{i}^{2}\times\sigma_{m}^{2}+\sigma_{e}^{2}
$$  

where $\beta_{i}$ is the slope of the regression,. $\sigma_{i}^{2}$ is stock $i$ s variance, $\sigma_{m}^{2}$ is the market (portfolio) variance, and $\sigma_{e}^{2}$ is the residual variance. If we divide both sides by the total $\sigma_{i}^{2}$ , then we.  

get the breakdown in percentage terms. The $R^{2}$ of a regression is the percentage of explained variation.  

The CAPM model is the representation of the two-fund separation principle and the ANOVA logic applied to stock pricing. It relates the random variables $r_{i}$ , the individual stock returns to the risk-free rate, and the random variable $r_{m}$ , the market portfolio return. It states that the expected excess returns on the individual stocks in the markets are not driven by the total risks of the stocks, but are proportional to the systematic risk $\beta_{i}$ only. The proportionality factor is the expected excess return on the overall market portfolio, also known as the market risk premium.  

The CAPM equation is:  

$$
E[r_{i}]=r_{F}+\beta_{i}\times(E[r_{M}]-r_{F})
$$  

The best way to think about this equation is that it is a relative value statement about the investors' confluence of beliefs about the long-term expected return on each stock or portfolio of stocks. That long-term mean return is proportional to the response parameter $\beta_{i}$ which multiplies the overall return on the total stock market. Diversifying investors do not expect that a stock will return $600\%$ annually if it is highly correlated with the stock index and only mildly more volatile, and they expect the market to return $10\%$ . Instead they use the regression slope coefficient:  

$$
\beta_{i}=\rho_{i}\times\frac{\sigma_{i}^{2}}{\sigma_{M}^{2}}
$$  

to relate individual stock returns to the overall market returns. $\rho_{i}$ denotes the correlation of the individual stock returns to the market portfolio return. The CAPM equation also states that investors expect a zero alpha over time - that is, in the rearranged equation,.  

$$
E\left[r_{i}\right]-r_{F}=\beta_{i}\times\left(E\left[r_{M}\right]-r_{F}\right)
$$  

there is no intercept term on the right-hand side.  

Figure 11.4 shows the CAPM graphically. In the mean-beta space, the CAPM equation is represented by the straight Security Market Line (SML). Ex ante, prior to investing, all stocks and risky portfolios lie on the CML. Stocks do not have a positive alpha and lie above the line, or have negative alpha and lie below the line. Stocks with low betas are defensive. As the market moves up and down, they wiggle very little. Stocks with high betas are aggressive. As the market moves up and down, they wiggle a lot.  

# 11.3.4 Using the CAPM as a Stock Screen to Discover Alpha  

While the CAPM is the result of a neat theory of diversification, it can be used as a simple screen of under- or overpriced individual stocks. We compute the CAPM-expected returns on stocks and compare them to the implied rates of return based on some fundamental analysis of cash flows. We are looking for Benjamin Graham's "margin of error' on top of a "fair return."  

Suppose we are looking at three stocks with the following characteristics in the first four columns of Table 11.5.  

The risk-free rate is $3\%$ and the market risk premium is $6.5\%$ . In column 5, we compute the CAPM-"warranted" returns. In column 6, we compute the expected return based on the. constant-growth fundamental valuation model of Section 11.2.2 using the recent prices in column 7. Column 8 contains the "fair' price based on the fundamental discounting of FCFE using the CAPM discount rate. Column 9 contains a proxy for the price/earnings ratio..  

![](83238d1427dbbe5e42df45e848f23e1a20078ec9331f260b6aae964c044c8248.jpg)  
Figure 11.4 The CAPM security market line (SML)   
Figure 11.5 shows graphically our stock selection analysis.  

Stock A's recent price is very low relative to the cash flow and the growth rate we estimate for the stock. The implied return on the stock, given the recent price, is high. The stock is "underpriced.' Stock B's recent price is high relative to the cash flow and growth rate; the resulting implied return is lower than that appropriate for the level of risk. Stock C appears to be mildly underpriced with CAPM and cash flow-implied returns close to each other. Note also that the traditional value investing based on P/E ratios would produce a similar screen favoring A over C. However, in our analysis A is a high growth stock, and B is a low growth stock.  

Admittedly, our analysis is a bit naive and relies heavily on the estimates of earnings,. cash flows, and growth rates. Philosophically, it is, however, identical to the many \*rigorous" analyses advertised by financial advisers and asset managers. Theirs is perhaps strengthened by the use of a multifactor systematic model paired with additional fundamental selection parameters (revenue growth, R&D expenditure, CAPEX, etc.) which further support the cash flow and growth estimates. It is certainly not less rigorous than the blind P/E ratio-based. selection.  

Table 11.5 CAPM-based stock screen   


<html><body><table><tr><td>1 Stock</td><td>2 Beta</td><td>3 FCFE/shr</td><td></td><td>4 Growth</td><td>5 CAPM ret</td><td>6 Implied ret</td><td>7 Recent price</td><td>8 Fair price</td><td></td><td>9 P/FCFE</td></tr><tr><td>A</td><td>1.10</td><td>$L</td><td>4.50</td><td>5%</td><td>10.15%</td><td>14.00%</td><td>$5 50.00</td><td></td><td>$ 87.38</td><td>11</td></tr><tr><td>B</td><td>0.93</td><td>$2</td><td>2.45</td><td>3%</td><td>9.05%</td><td>8.16%</td><td>$ 47.50</td><td>$</td><td>40.50</td><td>19</td></tr><tr><td>C</td><td>1.33</td><td>$ 11.20</td><td></td><td>6%</td><td>11.65%</td><td>11.79%</td><td>$193.25</td><td></td><td>$198.23</td><td>17</td></tr></table></body></html>  

![](051ceca00471c386cc2ddfe0f33caabf875a3fe487be5b0a699c5ff42f1d2302.jpg)  
Figure 11.5 A stock screen using the CAPM  

# 11.4MULTIFACTOR INDEX MODELS  

The CAPM model is very elegant, but untestable as it is an ex ante statement about the means of stock returns based on tight utility (risk aversion) and/or distributional (normality) assumptions. If we are not interested in a general equilibrium theory, but simply want to discover what works. statistically, then why not just regress stock returns on a bunch of variables to see what works? That is exactly what index modeling is.  

In the 1970s, researchers ran tests of the CAPM and generally became dissatisfied with the low explanatory power of the model and persistent positive intercepts. Broadening the definition of the market portfolio to include other assets and consumption, and allowing for time-changing betas did not help much. In 1975, BARRA launched its equity analysis platform allowing users to use a multifactor framework to decompose stock returns. However, the addition of macroeconomic factors (GDP, yield curve, inflation) did not lead to significantly improved results. One last attempt at elegant theory came in 1986 from Stephen Ross in the form of the arbitrage pricing theory (APT) that relied on the spanning principle of factor analysis. The intuition goes as follows. If we have 8,000 stocks then at most we have 8,000 risk factors. What if we form various portfolios of those stocks and discover that a few of these portfolios, when used as independent regression variables, explain most of the stock variation? Ross was able to show that a three-factor specification  

$$
r_{i}-r_{f}=\alpha_{i}+\beta_{i1}(f_{1}-r_{f})+\beta_{i2}(f_{2}-r_{f})+\beta_{i3}(f_{3}-r_{f})+\tilde{e}
$$  

could explain close to $95\%$ of the variance. The $\beta_{i n}$ 's are the risk loadings for stock. $i$ on factor $n$ . Each stock's excess return is decomposed into the risk premiums on three common factors. The main trouble with the APT which doomed it from the beginning was the fact that the factors were not identified as some macro variables, but were portfolios of stocks that did not resemble anything intuitive.  

# 11.4.1 The Fama-French Three-Factor Model  

Fama and French (1996) proposed the following index model for US stock returns:  

$$
r_{i}-r_{f}=\alpha_{i}+\beta_{i1}(r_{M}-r_{f})+\beta_{i2}(r_{s m a l l}-r_{b i g})+\beta_{i3}(r_{h i g h B/V}-r_{l o w B/V})+\tilde{e}
$$  

The model exhibits $R^{2}$ 's above $90\%$ for a variety of historical periods. What is new is the identification of the factors. It is somewhat surprising that the factors are not macroeconomic variables, but relate to innate characteristics of the stocks (which perhaps subsume macroeconomics?). The first factor is the cap-weighted market index; factors 2 and 3 are long/short-sorted portfolios. They are built by sorting all the stocks from the first to the last, dividing them into deciles (top $10\%$ , second $10\%$ ,.. ., tenth $10\%$ ), forming cap-weighted portfolios for the top and bottom $10\%$ , and subtracting the bottom (shorting) from the top (long). The sorting criterion for factor 1 is the size of the company defined by total capitalization and we sort from the smallest to the largest. The sorting criterion for factor 2 is the book-to-market value ratio, and we sort from the highest to the lowest. Once the portfolios are formed for any given historical period (say last 5 years of monthly data), we regress individual excess stock returns on the three factors to estimate the factor loadings (betas).  

Fama and French publish the data for the factors and distribute the factor realizations through. the CRSP database widely used in academia. On French's website, as of the end of April 2011, one could find the following factor realizations for the trailing 12 months:.  

$$
\begin{array}{r}{r_{M}-r_{f}=18.82\%}\ {r_{s m a l l}-r_{b i g}=4.36\%}\ {r_{h i g h B/V}-r_{l o w B/V}=-8.73\%}\end{array}
$$  

The market excess return was $18.82\%$ . The smallest stocks outperformed the biggest by $4.36\%$ and the high book-to-market companies trailed the low book-to-market companies by $8.73\%$ . Fama and French have an association with Dimensional Fund Advisors of Austin, Texas.  

There is no solid theory as to why size or book value should be priced systematic factors. One. story sometimes told in support of alternative weighting is that cap-weighting overweights large. caps and underweights growth, and the two additional factors correct for that. An alternative story told from the perspective of the reward for risk is that small size and high book value pose additional risks to survivability and additional value creation.  

# 11.4.2 The Carhart Fourth Factor: the Momentum  

Carhart (1997) added the fourth systematic factor related to the momentum. "Momentum" intuitively refers to the increased likelihood of a positive return following a positive return and a negative following a negative return. In the popularly used factor database available. from Kenneth French, the momentum factor is defined as follows. Form six portfolios as the. intersection of two metrics: two sorted size groups (Big and Small, demarcated by the median NYSE size) and three sorted return groups (past 12 month) portfolios (High, Mid, and Low, demarcated by the $30\mathrm{th}$ and 7Oth percentiles). Then average the good recent returns across Big and Small and average the poor recent performance across Big and Small to compute, for. each month, the difference of the two:  

$$
r_{M O M}=(r_{S m a l l H i g h}+r_{B i g H i g h})/2-(r_{S m a l l L o w}+r_{B i g L o w})/2
$$  

Then regress individual returns to obtain individual stock loadings on $r_{M O M}$ . Note that each month the formed portfolios will contain different stocks. The factor loading for a stock can be interpreted as a response function to recent winners minus losers, irrespective of which stocks they are.  

# 11.4.3 International Index Factors  

Fama and French make available factor data for international stocks that belong to the MSCI EAFE index. For each country, they construct risk factor value-weighted portfolios based on book-to-market, earnings-to-price, cash earnings-to-price, and dividend-to-price ratios. They also construct international index portfolios where the factor portfolios are weighted by the country EAFE weights.  

While the CAPM theory is a bit thorny for several reasons (like the definition of risk-free. and monetary numeraire), there is nothing stopping anyone from constructing optimal global. stock portfolios based on one factor - global market index - or many factors. There are some hurdles to overcome when dealing with international data, like dual shareholding classes and float-to-total cap, which complicate the definitions of the universe of risky assets. Also, generally speaking, the availability of trustworthy clean data outside of the USA and Europe,. and a few other countries, is quite poor, but improving.  
