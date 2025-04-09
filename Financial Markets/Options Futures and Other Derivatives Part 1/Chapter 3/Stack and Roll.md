# 3.6 STACK AND ROLL  

Sometimes the expiration date of the hedge is later than the delivery dates of all the futures contracts that can be used. The hedger must then roll the hedge forward by closing out one futures contract and taking the same position in a futures contract with a later delivery date. Hedges can be rolled forward many times. The procedure is known as stack and roll. Consider a company that wishes to use a short hedge to reduce the risk associated with the price to be received for an asset at time $T.$ If there are futures contracts 1, 2, 3, . . : , $n$ (not all necessarily in existence at the present time) with progressively later delivery dates, the company can use the following strategy:  

Time $t_{1}$ :Short futures contract 1   
Time $t_{2}$ Close out futures contract 1 Short futures contract 2   
Time $t_{3}$ .. Close out futures contract 2 Short futures contract 3   
Time $t_{n}$ :Close out futures contract $n\mathrm{~-~}1$ Short futures contract $n$   
Time $T$ :Close out futures contract $n$  

Suppose that in April 2021 a company realizes that it will have 100,000 barrels of oil to sell in June 2022 and decides to hedge its risk with a hedge ratio of 1.0. (In this example, we do not make the adjustment for daily settlement described in Section 3.4.) The current spot price is $\$49$ . Although futures contracts are traded with maturities stretching several years into the future, we suppose that only the first six delivery months have sufficient liquidity to meet the company's needs. The company therefore shorts 100 October 2021 contracts. In September 2021, it rolls the hedge forward into the March 2022 contract. In February 2022, it rolls the hedge forward again into the July 2022 contract.  

Table 3.5 Data for the example on rolling oil hedge forward.   


<html><body><table><tr><td>Date</td><td>Apr.2021</td><td>Sept.2021</td><td>Feb.2022</td><td>June2022</td></tr><tr><td>Oct. 2021 futures price</td><td>48.20</td><td>47.40</td><td></td><td></td></tr><tr><td>Mar.2022futuresprice</td><td></td><td>47.00</td><td>46.50</td><td></td></tr><tr><td>July 2022 futures price</td><td></td><td></td><td>46.30</td><td>45.90</td></tr><tr><td>Spot price</td><td>49.00</td><td></td><td></td><td>46.00</td></tr></table></body></html>  

One possible outcome is shown in Table 3.5. The October 2021 contract is shorted at $\$48.20$ per barrel and closed out at $\$47.40$ per barrel for a profit of $\$0.80$ per barrel; the March 2022 contract is shorted at $\$47.00$ per barrel and closed out at $\$46.50$ per barrel for a profit of $\$0.50$ per barrel. The July 2022 contract is shorted at $\$46.30$ per barrel and closed out at $\$45.90$ per barrel for a profit of $\$0.40$ per barrel. The final spot price is $\$46$  

The dollar gain per barrel of oil from the short futures contracts is  

$$
(48.20\mathrm{~-~}47.40)\:+\:(47.00\mathrm{~-~}46.50)\:+\:(46.30\mathrm{~-~}45.90)=1.70
$$  

The oil price declined from $\$49$ to $\$46$ . Receiving only. $\$1.70$ per barrel compensation for a price decline of. $\$3.00$ may appear unsatisfactory. However, we cannot expect total compensation for a price decline when futures prices are below spot prices. The best we can hope for is to lock in the futures price that would apply to a June 2022 contract if it. were actively traded..  

In practice, a company usually has an exposure every month to the underlying asset and uses a 1-month futures contract for hedging because it is the most liquid. Initially it enters into (\*stacks") sufficient contracts to cover its exposure to the end of its hedging horizon. One month later, it closes out all the contracts and "rolls' them into new 1-month contracts to cover its new exposure, and so on.  

As described in Business Snapshot 3.2, a German company, Metallgesellschaft,. followed this strategy in the early 1990s to hedge contracts it had entered into to supply. commodities at a fixed price. It ran into difficulties because the prices of the commodities declined so that there were immediate cash outflows on the futures and the expectation of eventual gains on the contracts. This mismatch between the timing of the cash flows on hedge and the timing of the cash flows from the position being hedged. led to liquidity problems that could not be handled. The moral of the story is that potential liquidity problems should always be considered when a hedging strategy is. being planned.  

# SUMMARY  

This chapter has discussed various ways in which a company can take a position in. futures contracts to offset an exposure to the price of an asset. If the exposure is such  

# Business Snapshot 3.2 Metallgesellschaft: Hedging Gone Awry  

Sometimes rolling hedges forward can lead to cash flow pressures. The problem was. illustrated dramatically by the activities of a German company, Metallgesellschaft (MG), in the early 1990s.  

MG sold a huge volume of 5- to 10-year heating oil and gasoline fixed-price. supply contracts to its customers at 6 to 8 cents above market prices. It hedged its. exposure with long positions in short-dated futures contracts that were rolled forward. As it turned out, the price of oil fell and there were margin calls on the futures positions. Considerable short-term cash flow pressures were placed on MG. The members of MG who devised the hedging strategy argued that these short-term. cash outflows were offset by positive cash flows that would ultimately be realized on. the long-term fixed-price contracts. However, the company's senior management and its bankers became concerned about the huge cash drain. As a result, the. company closed out all the hedge positions and agreed with its customers that the fixed-price contracts would be abandoned. The outcome was a loss to MG of $\$1.33$ billion.  

that the company gains when the price of the asset increases and loses when the price of the asset decreases, a short hedge is appropriate. If the exposure is the other way round (i.e., the company gains when the price of the asset decreases and loses when the price of the asset increases), a long hedge is appropriate.  

Hedging is a way of reducing risk. As such, it should be welcomed by most executives. In reality, there are a number of theoretical and practical reasons why. companies do not hedge. On a theoretical level, we can argue that shareholders, by holding well-diversified portfolios, can eliminate many of the risks faced by a company.. They do not require the company to hedge these risks. On a practical level, a company may find that it is increasing rather than decreasing risk by hedging if none of its. competitors does so. Also, a treasurer may fear criticism from other executives if the company makes a gain from movements in the price of the underlying asset and a loss on the hedge.  

An important concept in hedging is basis risk. The basis is the difference between the spot price of an asset and its futures price. Basis risk arises from uncertainty as to what the basis will be at maturity of the hedge..  

The hedge ratio is the ratio of the size of the position taken in futures contracts to the size of the exposure. It is not always optimal to use a hedge ratio of 1.0. If the hedger wishes to minimize the variance of a position, a hedge ratio different from 1.0 may be appropriate. The optimal hedge ratio is the slope of the best-fit line obtained when changes in the spot price are regressed against changes in the futures price.  

Stock index futures can be used to hedge the systematic risk in an equity portfolio. The number of futures contracts required is the beta of the portfolio multiplied by the ratio of the value of the portfolio to the value of one futures contract. Stock index futures can also be used to change the beta of a portfolio without changing the stocks that make up the portfolio.  

When there is no liquid futures contract that matures later than the expiration of the. hedge, a strategy known as stack and roll may be appropriate. This involves entering. into a sequence of futures contracts. When the first futures contract is near expiration, it is closed out and the hedger enters into a second contract with a later delivery month.. When the second contract is close to expiration, it is closed out and the hedger enters. into a third contract with a later delivery month; and so on. The result of all this is the creation of a long-dated futures contract by trading a series of short-dated contracts..  

# FURTHER READING  

Adam, T., S. Dasgupta, and S. Titman. "Financial Constraints, Competition, and Hedging in Industry Equilibrium, Journal of Finance, 62, 5 (October 2007): 2445-73.   
Adam, T. and C.S. Fernando. "Hedging, Speculation, and Shareholder Value,' Journal of Financial Economics, 81, 2 (August 2006): 283-309.   
Allayannis, G., and J. Weston. "The Use of Foreign Currency Derivatives and Firm Market Value,' Review of Financial Studies, 14, 1 (Spring 2001): 243-76.   
Brown, G. W. "Managing Foreign Exchange Risk with Derivatives' Journal of Financial Economics, 60 (2001): 401-48.   
Campbell, J. Y., K. Serfaty-deMedeiros, and L. M. Viceira. "Global Currency Hedging, Journal of Finance, 65, 1 (February 2010): 87-121.   
Campello, M., C. Lin, Y. Ma, and H. Zou. "The Real and Financial Implications of Corporate Hedging, Journal of Finance, 66, 5 (October 2011): 1615-47.   
Cotter, J., and J. Hanly. "Hedging: Scaling and the Investor Horizon,' Journal of Risk, 12, 2 (Winter 2009/2010): 49-77.   
Culp, C. and M. H. Miller. "Metallgesellschaft and the Economics of Synthetic Storage,' Journal of Applied Corporate Finance,7, 4 (Winter 1995): 62-76.   
Edwards, F. R. and M. S. Canter. "The Collapse of Metallgesellschaft: Unhedgeable Risks, Poor Hedging Strategy, or Just Bad Luck?" Journal of Applied Corporate Finance,8, 1 (Spring 1995):. 86105.   
Graham, J. R. and C. W. Smith, Jr. "Tax Incentives to Hedge,' Journal of Finance, 54, 6 (1999): 2241-62.   
Haushalter, G. D. "Financing Policy, Basis Risk, and Corporate Hedging: Evidence from Oil and Gas Producers,' Journal of Finance, 55,1 (2000): 107-52.   
Jin, Y., and P. Jorion. "Firm Value and Hedging: Evidence from U.S. Oil and Gas Producers,' Journal of Finance, 61, 2 (April 2006): 893-919.   
Mello, A. S. and J. E. Parsons. "Hedging and Liquidity, Review of Financial Studies, 13 (Spring. 2000): 127-53.   
Neuberger, A. J. "Hedging Long-Term Exposures with Multiple Short-Term Futures Contracts,' Review of Financial Studies, 12 (1999): 429-59.   
Petersen, M. A. and S. R. Thiagarajan, "Risk Management and Hedging: With and Without Derivatives,' Financial Management, 29, 4 (Winter 2000): 5-30.   
Rendleman, R. "A Reconciliation of Potentially Conflicting Approaches to Hedging with. Futures,' Advances in Futures and Options, 6 (1993): 81-92.   
Stulz, R. M. "Optimal Hedging Policies,' Journal of Financial and Quantitative Analysis, 19 (June 1984): 127-40.   
Tufano, P. "Who Manages Risk? An Empirical Examination of Risk Management Practices in the Gold Mining Industry,' Journal of Finance, 51, 4 (1996): 1097-1138..  

# Short Concept Questions  

3.1. Under what circumstances are short hedges and long hedges appropriate?.   
3.2. Give three reasons why the treasurer of a company might choose not to hedge a. particular risk.   
3.3. Explain how basis risk arises in hedging.   
3.4. What is the formula for the minimum variance hedge ratio when daily settlement is ignored?   
3.5. How is the formula for the minimum variance hedge ratio changed to take account of. daily settlement?   
3.6. How is the number of contracts used for hedging calculated from the minimum variance hedge ratio?   
3.7. How can index futures be used to change the beta of a well-diversified portfolio?.   
3.8. How might investors who consider themselves adept at stock picking use index futures?   
3.9. Explain what the stack and roll hedging strategy involves.   
3.10. Explain how hedging using futures can lead to cash-flow problems such as those experienced by Metallgesellschaft.  

# Practice Questions  

3.11. Explain what is meant by a perfect hedge. Does a perfect hedge always lead to a better outcome than an imperfect hedge? Explain your answer.   
3.12. Under what circumstances does a minimum variance hedge portfolio lead to no hedging at all?   
3.13. Suppose that the standard deviation of quarterly changes in the prices of a commodity is $\$0.65$ , the standard deviation of quarterly changes in a futures price on the commodity is $\$0.81$ , and the coefficient of correlation between the two changes is 0.8. What is the optimal hedge ratio for a 3-month contract? What does it mean?   
3.14. A company has a $\$20$ million portfolio with a beta of 1.2. It would like to use futures contracts on a stock index to hedge its risk. The index futures price is currently standing at 1080, and each contract is for delivery of $\$250$ times the index. What is the hedge that minimizes risk? What should the company do if it wants to reduce the beta of the portfolio to 0.6?   
3.15. In the corn futures contract traded on an exchange, the following delivery months are available: March, May, July, September, and December. Which of the available contracts should be used for hedging when the expiration of the hedge is in (a) June, (b) July, and (c) January.   
3.16. Does a perfect hedge always succeed in locking in the current spot price of an asset for a. future transaction? Explain your answer.   
3.17. Explain why a short hedger's position improves when the basis strengthens unexpectedly and worsens when the basis weakens unexpectedly.  

3.18. Imagine you are the treasurer of a Japanese company exporting electronic equipment to the United States. Discuss how you would design a foreign exchange hedging strategy and the arguments you would use to sell the strategy to your fellow executives.  

3.19. Suppose that in Example 3.2 of Section 3.3 the company decides to use a hedge ratio of 0.8. How does the decision affect the way in which the hedge is implemented and the result?   
3.20. "If the minimum variance hedge ratio is calculated as 1.0, the hedge must be perfect.' Is this statement true? Explain your answer.   
3.21. If there is no basis risk, the minimum variance hedge ratio is always 1.0.' Is this statement true? Explain your answer.   
3.22. When the futures price of an asset is less than the spot price, long hedges are likely to be particularly attractive.' Explain this statement.   
3.23. The standard deviation of monthly changes in the spot price of live cattle is (in cents per pound) 1.2. The standard deviation of monthly changes in the futures price of live cattle for the closest contract is 1.4. The correlation between the futures price changes and the spot price changes is 0.7. It is now October 15. A beef producer is committed to purchasing 200,000 pounds of live cattle on November 15. The producer wants to use the December live cattle futures contracts to hedge its risk. Each contract is for the delivery of 40,000 pounds of cattle. What strategy should the beef producer follow?   
3.24. A corn farmer argues "I do not use futures contracts for hedging. My real risk is not the price of corn. It is that my whole crop gets wiped out by the weather.' Discuss this viewpoint. Should the farmer estimate his or her expected production of corn and hedge to try to lock in a price for expected production?   
3.25. On July 1, an investor holds 50,o00 shares of a certain stock. The market price is. $\$30$ per share. The investor is interested in hedging against movements in the market over the next. month and decides to use an index futures contract. The index futures price is currently 1,500 and one contract is for delivery of $\$50$ times the index. The beta of the stock is 1.3. What strategy should the investor follow? Under what circumstances will it be profitable?   
3.26. Suppose that in Table 3.5 the company decides to use a hedge ratio of 1.5. How does the decision affect the way the hedge is implemented and the result?   
3.27. An airline executive has argued: "There is no point in our using oil futures. There is just as much chance that the price of oil in the future will be less than the futures price as there is that it will be greater than this price.' Discuss the executive's viewpoint..   
3.28. Suppose that the 1-year gold lease rate is $1.5\%$ and the 1-year risk-free rate is $5.0\%$ . Both rates are compounded annually. Use the discussion in Business Snapshot 3.1 to calculate the maximum 1-year gold forward price Goldman Sachs should quote to the gold-mining. company when the spot price is $\$1,200$   
3.29. The expected return on the S&P 500 is $12\%$ and the risk-free rate is $5\%$ . What is the expected return on an investment with a beta of (a) 0.2, (b) 0.5, and (c) 1.4?   
3.30. It is now June. A company knows that it will sell 5,o00 barrels of crude oil in September. It uses the October CME Group futures contract to hedge the price it will receive. Each. contract is on 1,o00 barrels of "light sweet crude.' What position should it take? What price risks is it still exposed to after taking the position?   
3.31. Sixty futures contracts are used to hedge an exposure to the price of silver. Each futures contract is on 5,000 ounces of silver. At the time the hedge is closed out, the basis is $\$0.20$  

per ounce. What is the effect of the basis on the hedger's financial position if (a) the trader is hedging the purchase of silver and (b) the trader is hedging the sale of silver?  

3.32. A trader owns 55,000 units of a particular asset and decides to hedge the value of her position with futures contracts on another related asset. Each futures contract is on 5,000 units. The spot price of the asset that is owned is $\$28$ and the standard deviation of the change in this price over the life of the hedge is estimated to be. $\$0.43$ . The futures price of the related asset is $\$27$ and the standard deviation of the change in this over the life of the. hedge is $\$0.40$ The coefficient of correlation between the spot price change and futures price change is 0.95.  

(a) What is the minimum variance hedge ratio?   
(b) Should the hedger take a long or short futures position?   
(c) What is the optimal number of futures contracts when adjustments for daily settlement are not considered?   
(d) How can the daily settlement of futures contracts be taken into account?  

3.33. A company wishes to hedge its exposure to a new fuel whose price changes have a 0.6 correlation with gasoline futures price changes. The company will lose. $\$1$ million for each 1 cent increase in the price per gallon of the new fuel over the next three months. The new fuel's price changes have a standard deviation that is. $50\%$ greater than price changes in gasoline futures prices. If gasoline futures are used to hedge the exposure, what should the hedge ratio be? What is the company's exposure measured in gallons of the new fuel? What position, measured in gallons, should the company take in gasoline futures? How many gasoline futures contracts should be traded? Each contract is on 42,000 gallons.  

3.34. A portfolio manager has maintained an actively managed portfolio with a beta of 0.2. During the last year, the risk-free rate was $5\%$ and equities performed very badly providing a return of $-30\%$ . The portfolio manager produced a return of $-10\%$ and claims that in the circumstances it was a good performance. Discuss this claim.  

3.35. It is July 16. A company has a portfolio of stocks worth $\$100$ million. The beta of the portfolio is 1.2. The company would like to use the December futures contract on a stock index to change the beta of the portfolio to 0.5 during the period July 16 to November 16. The index futures price is currently 2,000 and each contract is on $\$250$ times the index.  

(a) What position should the company take?. (b) Suppose that the company changes its mind and decides to increase the beta of the portfolio from 1.2 to 1.5. What position in futures contracts should it take?.  

# APPENDIX CAPITAL ASSET PRICING MODEL  

The capital asset pricing model (CAPM) is a model that can be used to relate the expected return from an asset to the risk of the return. The risk in the return from an asset is divided into two parts. Systematic risk is risk related to the return from the market as a whole and cannot be diversified away. Nonsystematic risk is risk that is unique to the asset and can be diversified away by choosing a large portfolio of different assets. CAPM argues that the return should depend only on systematic risk. The CAPM formula is6  

$$
\mathrm{Expectedreturnonasset}=R_{F}+\beta(R_{M}-R_{F})
$$  

where $R_{M}$ is the return on the portfolio of all available investments, $R_{F}$ is the return on a risk-free investment, and $\beta$ (the Greek letter beta) is a parameter measuring systematic risk.  

The return from the portfolio of all available investments, $R_{M}$ , is referred to as the. return on the market and is usually approximated as the return on a well-diversified stock index such as the S&P 500. The beta. $(\beta)$ of an asset is a measure of the sensitivity. of its returns to returns from the market. It can be estimated from historical data as the slope obtained when the excess return on the asset over the risk-free rate is regressed against the excess return on the market over the risk-free rate. When $\beta=0$ , an asset's returns are not sensitive to returns from the market. In this case, it has no systematic risk and equation (3A.1) shows that its expected return is the risk-free rate; when $\beta=0.5$ , the excess return on the asset over the risk-free rate is on average half of the excess return of the market over the risk-free rate; when $\beta=1$ , the expected return on. the asset equals to the return on the market; and so on.  

Suppose that the risk-free rate $R_{F}$ is $5\%$ and the return on the market is $13\%$ Equation (3A.1) shows that, when the beta of an asset is zero, its expected return is $5\%$ When $\beta=0.75$ , its expected return is $0.05+0.75\times(0.13-0.05)=0.11$ , or $11\%$  

The derivation of CAPM requires a number of assumptions.' In particular:  

1. Investors care only about the expected return and standard deviation of the return. from an asset.   
2. The returns from two assets are correlated with each other only because of their. correlation with the return from the market. This is equivalent to assuming that. there is only one factor driving returns..   
3. Investors focus on returns over a single period and that period is the same for all. investors.   
4. Investors can borrow and lend at the same risk-free rate.   
5. Tax does not influence investment decisions.   
6. All investors make the same estimates of expected returns, standard deviations of returns, and correlations between returns..  

These assumptions are at best only approximately true. Nevertheless CAPM has proved. to be a useful tool for portfolio managers and is often used as a benchmark for assessing their performance.  

When the asset is an individual stock, the expected return given by equation (3A.1) is. not a particularly good predictor of the actual return. But, when the asset is a welldiversified portfolio of stocks, it is a much better predictor. As a result, the equation  

$$
\mathrm{Returnondiversifiedportfolio}=R_{F}+\beta(R_{M}-R_{F})
$$  

can be used as a basis for hedging a diversified portfolio, as described in Section 3.5. The $\beta$ in the equation is the beta of the portfolio. It can be calculated as the weighted average of the betas of the stocks in the portfolio.  

![](46f0b70095d70f5694da0f5130485a3e63ee61b5bb79931d3ef1e59c9a29b92b.jpg)  

# Interest Rates  

Interest rates are a factor in the valuation of virtually all derivatives and will feature prominently in much of the material that will be presented in the rest of this book. This chapter introduces a number of different types of interest rate. It deals with some fundamental issues concerned with the way interest rates are measured and analyzed. It explains the compounding frequency used to define an interest rate and the meaning of continuously compounded interest rates, which are used extensively in the analysis of derivatives. It covers zero rates, par yields, and yield curves, discusses bond pricing, and outlines a "bootstrap' procedure commonly used to calculate zero-coupon interest rates. It also covers forward rates and forward rate agreements and reviews different theories of the term structure of interest rates. Finally,it explains the use of duration and convexity measures to determine the sensitivity of bond prices to interest rate changes.  

Chapter 6 will cover interest rate futures and show how the duration measure can be used when interest rate exposures are hedged. For ease of exposition, day count conventions will be ignored throughout this chapter. The nature of these conventions and their impact on calculations will be discussed in Chapters 6 and 7.  
