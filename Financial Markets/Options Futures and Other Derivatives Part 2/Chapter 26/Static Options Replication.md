# 26.17 STATIC OPTIONS REPLICATION  

If the procedures described in Chapter 19 are used for hedging exotic options, some are easy to handle, but others are very difficult because of discontinuities (see Business Snapshot 26.1). For the difficult cases, a technique known as static options replication is sometimes useful.15 This involves searching for a portfolio of actively traded options that. approximately replicates the exotic option. Shorting this position provides the hedge.16.  

The basic principle underlying static options replication is as follows. If two portfolios. are worth the same on a certain boundary, they are also worth the same at all interior points of the boundary. Consider as an example a 9-month up-and-out call option on a non-dividend-paying stock where the stock price is 50, the strike price is 50, the barrier is. 60, the risk-free interest rate is. $10\%$ per annum, and the volatility is. $30\%$ per annum. Suppose that $f(S,t)$ is the value of the option at time. $t$ for a stock price of. $S$ . Any boundary in $(S,t)$ space can be used for the purposes of producing the replicating portfolio. A convenient one to choose is shown in Figure 26.1. It is defined by. $S=60$ and $t=0.75$ The values of the up-and-out option on the boundary are given by.  

$$
\begin{array}{r}{f(S,0.75)=\operatorname*{max}(S-50,0)\quad\mathrm{when}S<60~}\ {f(60,t)=0\quad\mathrm{when}0\le t\le0.75\qquad\quad}\end{array}
$$  

There are many ways that these boundary values can be approximately matched. using regular options. The natural option to match the first boundary is a 9-month European call with a strike price of 50. The first component of the replicating portfolio. is therefore one unit of this option. (We refer to this option as option A.)  

One way of matching the $f(60,t)$ boundary is to proceed as follows:  

1. Divide the life of the option into $N$ steps of length $\Delta t$   
2. Choose a European call option with a strike price of 60 and maturity at time Nt $\v{r}=\v{r}9$ months) to match the boundary at the $\{60,(N-1)\Delta t\}$ point   
3. Choose a European call option with a strike price of 60 and maturity at time $(N-1)\Delta t$ to match the boundary at the $\{60,(N-2)\Delta t\}$ point  

and so on. Note that the options are chosen in sequence so that they have zero value on the parts of the boundary matched by earlier options.17 The option with a strike price.  

<html><body><table><tr><td>Business Snapshot 26.1 Is Delta Hedging Easier or More Difficult forExotics?</td></tr><tr><td>As described in Chapter 19, we can approach the hedging of exotic options by creating a delta neutral position and rebalancing frequently to maintain delta neutrality. When we do this we find some exotic options are easier to hedge than plain vanilla options and some are more difficult. An example of an exotic option that is relatively easy to hedge is an average price option where the averaging period is the whole life of the option. As time passes, we observe more of the asset prices that will be used in calculating the final average. This means that our uncertainty about the payoff decreases with the passage of time.As a</td></tr><tr><td>result, the option becomes progressively easier to hedge. In the final few days, the delta of the option always approaches zero because price movements during this time have very little impact on the payoff.</td></tr><tr><td>By contrast barrier options are relatively difficult to hedge. Consider a down-and- out call option on a currency when the exchange rate is 0.oo05 above the barrier. If the barrier is hit, the option is worth nothing. If the barrier is not hit, the option may prove to be quite valuable. The delta of the option is discontinuous at the barrier</td></tr></table></body></html>  

of 60 that matures in 9 months has zero value on the vertical boundary that is matched by option A. The option maturing at time $i\Delta t$ has zero value at the point $\{60,i\Delta t\}$ that is matched by the option maturing at time $(i+1)\Delta t$ for $1\leq i\leq N-1$  

Suppose that $\Delta t=0.25$ In addition to option A, the replicating portfolio consists of positions in European options with strike price 60 that mature in 9, 6, and 3 months. We will refer to these as options B, C, and $\mathrm{\bfD}$ , respectively. Given our assumptions about volatility and interest rates, option B is worth 4.33 at the $\{60,0.5\}$ point. Option A is worth 11.54 at this point. The position in option B necessary to match the boundary at the $\{60,0.5\}$ point is therefore $-11.54/4.33=-2.66.$ Option C is worth 4.33 at the $\{60,0.25\}$ point. The position taken in options A and B is worth. $-4.21$ at this point. The position in option C necessary to match the boundary at the $\{60,0.25\}$ point is therefore $4.21/4.33=0.97.$ Similar calculations show that the position in. option D necessary to match the boundary at the. $\{60,0\}$ point is 0.28.  

![](images/d3f32e107e536bc1c8324f47bb42408313083456f0587a5796406d99981fa913.jpg)  
Figure 26.1 Boundary points used for static options replication example.  

Table 26.1 The portfolio of European call options used to replicate an up-and-out option.   


<html><body><table><tr><td>Option</td><td>Strike price</td><td>Maturity (years)</td><td>Position</td><td>value</td></tr><tr><td>A</td><td>50</td><td>0.75</td><td>1.00</td><td>+6.99</td></tr><tr><td>B</td><td>60</td><td>0.75</td><td>-2.66</td><td>-8.21</td></tr><tr><td>C</td><td>60</td><td>0.50</td><td>0.97</td><td>+1.78</td></tr><tr><td>D</td><td>60</td><td>0.25</td><td>0.28</td><td>+0.17</td></tr></table></body></html>  

The portfolio chosen is summarized in Table 26.1. (See also Sample Application F of. the DerivaGem Applications.) It is worth 0.73 initially (i.e., at time zero when the stock price is 50). This compares with 0.31 given by the analytic formula for the up-and-out call earlier in this chapter. The replicating portfolio is not exactly the same as the up-. and-out option because it matches the latter at only three points on the second. boundary. If we use the same procedure, but match at 18 points on the second. boundary (using options that mature every half month), the value of the replicating. portfolio reduces to 0.38. If 100 points are matched, the value reduces further to 0.32.  

To hedge a derivative, the portfolio that replicates its boundary conditions must be shorted. The hedge lasts until the end of the life of the derivative or until the boundary is reached, whichever happens first. If the boundary is reached, the hedge portfolio must be unwound and a new hedge portfolio set up.  

Static options replication has the advantage over delta hedging that it does not. require frequent rebalancing. It can be used for a wide range of derivatives. The user has a great deal of flexibility in choosing the boundary that is to be matched and the. options that are to be used..  

# SUMMARY  

Exotic options are options with rules governing the payoff that are more complicated than standard options. We have discussed 15 different types of exotic options: packages,. perpetual American options, nonstandard American options, gap options, forward start. options, cliquet options, compound options, chooser options, barrier options, binary options, lookback options, shout options, Asian options, options to exchange one asset for another, and options involving several assets. We have discussed how these can be valued using the same assumptions as those used to derive the Black-Scholes-Merton model in Chapter 15. Some can be valued analytically, but using much more complicated formulas than those for regular European calls and puts, some can be handled using analytic approximations, and some can be valued using extensions of the numerical.  

procedures in Chapter 21. We will present more numerical procedures for valuing exotic options in Chapter 27.  

Some exotic options are easier to hedge than the corresponding regular options;. others are more difficult. In general, Asian options are easier to hedge because the payoff becomes progressively more certain as we approach maturity. Barrier options can. be more difficult to hedge because delta is discontinuous at the barrier. One approach. to hedging an exotic option, known as static options replication, is to find a portfolio of regular options whose value matches the value of the exotic option on some boundary. The exotic option is hedged by shorting this portfolio..  

# FURTHER READING  

Carr, P., and R. Lee, "Realized Volatility and Variance: Options via Swaps," Risk, May 2007, 76-83..   
Clewlow, L., and C. Strickland, Exotic Options: The State of the Art. London: Thomson Business. Press, 1997.   
Demeterfi, K., E. Derman, M. Kamal, and J. Zou, "More than You Ever Wanted to Know. about Volatility Swaps," Journal of Derivatives, 6, 4 (Summer, 1999), 9-32.   
Derman, E., D. Ergener, and I. Kani, "Static Options Replication," Journal of Derivatives, 2,. 4 (Summer 1995): 78-95.   
Geske, R., "The Valuation of Compound Options," Journal of Financial Economics, 7 (1979): 63-81..   
Goldman, B., H. Sosin, and M. A. Gatto, "Path Dependent Options: Buy at the Low, Sell at the High, Journal of Finance, 34 (December 1979); 1111-27.   
Margrabe, W., "The Value of an Option to Exchange One Asset for Another," Journal of Finance, 33 (March 1978): 177-86.   
Rubinstein, M., and E. Reiner, "Breaking Down the Barriers," Risk, September (1991): 28-35..   
Rubinstein, M., "Double Trouble," Risk, December/January (1991/1992): 53-56.   
Rubinstein, M., "One for Another," Risk, July/August (1991): 30-32.   
Rubinstein, M., "Options for the Undecided," Risk, April (1991): 70-73.   
Rubinstein, M., "Pay Now, Choose Later," Risk, February (1991): 44-47.   
Rubinstein, M., "Somewhere Over the Rainbow,"' Risk, November (1991): 63-66..   
Rubinstein, M., "Two in One," Risk May (1991): 49..   
Rubinstein, M., and E. Reiner, "Unscrambling the Binary Code," Risk, October 1991: 75-83.   
Stulz, R. M., "Options on the Minimum or Maximum of Two Assets," Journal of Financial Economics, 10 (1982): 161-85.   
Turnbull, S. M., and L. M. Wakeman, "A Quick Algorithm for Pricing European Average Options," Journal of Financial and Quantitative Analysis, 26 (September 1991): 377-89..  

# Practice Questions  

26.1. Explain the difference between a forward start option and a chooser option..   
26.2. Describe the payoff from a portfolio consisting of a floating lookback call and a floating lookback put with the same maturity.   
26.3. Consider a chooser option where the holder has the right to choose between a European call and a European put at any time during a 2-year period. The maturity dates and strike prices for the calls and puts are the same regardless of when the choice is made. Is it ever optimal to make the choice before the end of the 2-year period? Explain your answer.  

26.4. Suppose that $c_{1}$ and $p_{1}$ are the prices of a European average price call and a European average price put with strike price $K$ and maturity $T,c_{2}$ and $p_{2}$ are the prices of a European average strike call and European average strike put with maturity $T$ and $c_{3}$ and $p_{3}$ are the prices of a regular European call and a regular European put with strike price $K$ and maturity $T.$ Show that $c_{1}+c_{2}-c_{3}=p_{1}+p_{2}-p_{3}$  

26.5. The text derives a decomposition of a particular type of chooser option into a call maturing at time $T_{2}$ and a put maturing at time. $T_{1}$ . Derive an alternative decomposition into a call maturing at time. $T_{1}$ and a put maturing at time. $T_{2}$  

26.6. Section 26.9 gives two formulas for a down-and-out call. The first applies to the situation where the barrier,. $H.$ is less than or equal to the strike price,. $K$ The second applies to the. situation where $H\geq K$ Show that the two formulas are the same when $H=K$  

26.7. Explain why a down-and-out put is worth zero when the barrier is greater than the strike price.  

26.8. Suppose that the strike price of an American call option on a non-dividend-paying stock grows at rate $g$ . Show that if $g$ is less than the risk-free rate,. $r$ , it is never optimal to exercise the call early.  

26.9. How can the value of a forward start put option on a non-dividend-paying stock be calculated if it is agreed that the strike price will be. $10\%$ greater than the stock price at. the time the option starts?  

26.10. If a stock price follows geometric Brownian motion, what process does $A(t)$ follow where $A(t)$ is the arithmetic average stock price between time zero and time $t?$  

26.11. Explain why delta hedging is easier for Asian options than for regular options.  

26.12. Calculate the price of a 1-year European option to give up 100 ounces of silver in exchange for 1 ounce of gold. The current prices of gold and silver are $\$1,520$ and $\$16$ , respectively; the risk-free interest rate is $10\%$ per annum; the volatility of each commodity price is. $20\%$ and the correlation between the two prices is 0.7. Ignore storage costs.  

26.13. Is a European down-and-out option on an asset worth the same as a European downand-out option on the asset's futures price for a futures contract maturing at the same time as the option?  

26.14. Answer the following questions about compound options:  

(a) What put-call parity relationship exists between the price of a European call on a call and a European put on a call? Show that the formulas given in the text satisfy the relationship.   
(b) What put-call parity relationship exists between the price of a European call on a put and a European put on a put? Show that the formulas given in the text satisfy the relationship.  

26.15. Does a floating lookback call become more valuable or less valuable as we increase the frequency with which we observe the asset price in calculating the minimum?.  

26.16. Does a down-and-out call become more valuable or less valuable as we increase the frequency with which we observe the asset price in determining whether the barrier has been crossed? What is the answer to the same question for a down-and-in call?  

26.17. Explain why a regular European call option is the sum of a down-and-out European call and a down-and-in European call. Is the same true for American call options?.  

26.18. What is the value of a derivative that pays off $\$100$ in 6 months if an index is greater. than 1,000 and zero otherwise? Assume that the current level of the index is 960, the riskfree rate is $8\%$ per annum, the dividend yield on the index is $3\%$ per annum, and the. volatility of the index is. $20\%$  

26.19. In a 3-month down-and-out call option on silver futures the strike price is $\$20$ per ounce. and the barrier is. $\$18$ The current futures price is $\$19$ , the risk-free interest rate is $5\%$ and the volatility of silver futures is $40\%$ per annum. Explain how the option works and calculate its value. What is the value of a regular call option on silver futures with the same terms? What is the value of a down-and-in call option on silver futures with the same terms?  

26.20. A new European-style floating lookback call option on a stock index has a maturity of 9 months. The current level of the index is 400, the risk-free rate is $6\%$ per annum, the dividend yield on the index is $4\%$ per annum, and the volatility of the index is $20\%$ . Use DerivaGem to value the option.  

26.21. Estimate the value of a new 6-month European-style average price call option on a nondividend-paying stock. The initial stock price is $\$30$ , the strike price is. $\$30$ , the risk-free interest rate is $5\%$ , and the stock price volatility is. $30\%$  

26.22. Use DerivaGem to calculate the value of:  

(a) A regular European call option on a non-dividend-paying stock where the stock price is $\$50$ , the strike price is $\$50$ , the risk-free rate is $5\%$ per annum, the volatility is $30\%$ , and the time to maturity is one year   
(b) A down-and-out European call which is as in (a) with the barrier at $\$45$   
(c) A down-and-in European call which is as in (a) with the barrier at $\$45$  

Show that the option in (a) is worth the sum of the values of the options in (b) and (c)  

26.23. Explain adjustments that have to be made when $r=q$ for (a) the valuation formulas for floating lookback call options in Section 26.11 and (b) the formulas for $M_{1}$ and $M_{2}$ in Section 26.13.  

26.24. Value the variance swap in Example 26.4 of Section 26.16 assuming that the implied. volatilities for options with strike prices 800, 850, 900, 950, 1,000, 1,050, 1,100, 1,150, 1,200 are $20\%$ $20.5\%$ $21\%$ $21.5\%$ $22\%$ $22.5\%$ $23\%$ $23.5\%$ $24\%$ , respectively.  

26.25. Verify that the results in Section 26.2 for the value of a derivative that pays $Q$ when $S=H$ are consistent with those in Section 15.6.  

26.26. Consider an up-and-out barrier call option on a non-dividend-paying stock when the stock price is 50, the strike price is 50, the volatility is $30\%$ , the risk-free rate is. $5\%$ , the time to maturity is 1 year, and the barrier at. $\$80$ . Use the DerivaGem software to value. the option and graph the relationship between (a) the option price and the stock price, (b) the delta and the stock price, (c) the option price and the time to maturity, and (d) the option price and the volatility. Provide an intuitive explanation for the results you get. Show that the delta, gamma, theta, and vega for an up-and-out barrier call option can be either positive or negative..  

26.27. Sample Application F in the DerivaGem Application Builder Software considers the static options replication example in Section 26.17. It shows the way a hedge can be constructed using four options (as in Section 26.17) and two ways a hedge can be. constructed using 16 options.  

(a) Explain the difference between the two ways a hedge can be constructed using 16 options. Explain intuitively why the second method works better.   
(b) Improve on the four-option hedge by changing Tmat for the third and fourth options.   
(c) Check how well the 16-option portfolios match the delta, gamma, and vega of the barrier option.  

26.28. Consider a down-and-out call option on a foreign currency. The initial exchange rate is 0.90, the time to maturity is 2 years, the strike price is 1.00, the barrier is 0.80, the. domestic risk-free interest rate is. $5\%$ , the foreign risk-free interest rate is. $6\%$ , and the volatility is $25\%$ per annum. Use DerivaGem to develop a static option replication strategy involving five options..  

26.29. Suppose that a stock index is currently 900. The dividend yield is. $2\%$ , the risk-free rate is $5\%$ , and the volatility is. $40\%$ . Use the results in Technical Note 27 on the author's. website to calculate the value of a 1-year average price call where the strike price is 900 and the index level is observed at the end of each quarter for the purposes of the averaging. Compare this with the price calculated by DerivaGem for a 1-year average price option where the price is observed continuously. Provide an intuitive explanation for any differences between the prices..  

26.30. Use the DerivaGem Application Builder software to compare the effectiveness of daily. delta hedging for (a) the option considered in Tables 19.2 and 19.3 and (b) an average price call with the same parameters. Use Sample Application C. For the average price option you will find it necessary to change the calculation of the option price in cell C16, the payoffs in cells H15 and H16, and the deltas (cells G46 to G186 and N46 to N186). Carry out 20 Monte Carlo simulation runs for each option by repeatedly pressing F9. On each run record the cost of writing and hedging the option, the volume of trading over the whole 20 weeks and the volume of trading between weeks 11 and 20. Comment on the results.  

26.31. In the DerivaGem Application Builder Software modify Sample Application. $\mathbf{D}$ to test the effectiveness of delta and gamma hedging for a call on call compound option on a. 100,000 units of a foreign currency where the exchange rate is 0.67, the domestic risk-free. rate is $5\%$ , the foreign risk-free rate is $6\%$ , the volatility is $12\%$ . The time to maturity of the first option is 20 weeks, and the strike price of the first option is 0.015. The second option matures 40 weeks from today and has a strike price of 0.68. Explain how you modified the cells. Comment on hedge effectiveness.  

26.32. Outperformance certificates (also called "sprint certificates," "accelerator certificates, or "speeders") are offered to investors by many European banks as a way of investing in. a company's stock. The initial investment equals the stock price,. $S_{0}$ . If the stock price. goes up between time 0 and time $T$ , the investor gains. $k$ times the increase at time $T$ where $k$ is a constant greater than 1.0. However, the stock price used to calculate the gain at time. $T$ is capped at some maximum level $M$ . If the stock price goes down, the. investor's loss is equal to the decrease. The investor does not receive dividends.  

(a) Show that an outperformance certificate is a package.   
(b) Calculate using DerivaGem the value of a one-year outperformance certificate when the stock price is 50 euros,. $k=1.5,M=70$ euros, the risk-free rate is. $5\%$ , and the stock price volatility is $25\%$ . Dividends equal to 0.5 euros are expected in 2 months,. 5 months, 8 months, and 11 months..   
26.33. Carry out the analysis in Example 26.4 of Section 26.16 to value the variance swap on the assumption that the life of the swap is 1 month rather than 3 months.   
26.34. What is the relationship between a regular call option, a binary call option, and a gap call option?   
26.35. Produce a formula for valuing a cliquet option where an amount $Q$ is invested to produce a payoff at the end of $n$ periods. The return earned each period is the greater of the return on an index (excluding dividends) and zero.  

![](images/1aa0a7f0929074f1bef3973d5d519d4ea90236fa9cd369d3301225dfcdf69095.jpg)  

# More on Models and Numerical Procedures  

Up to now the models we have used to value options have been based on the geometric Brownian motion model of asset price behavior that underlies the Black-Scholes-- Merton formulas and the numerical procedures we have used have been relatively. straightforward. In this chapter we introduce a number of new models and explain how the numerical procedures can be adapted to cope with particular situations..  

Chapter 20 explained how traders overcome the weaknesses in the geometric Brown-. ian motion model by using volatility surfaces. A volatility surface determines an. appropriate volatility to substitute into Black-Scholes-Merton when pricing plain vanilla options. Unfortunately it says little about the volatility that should be used for exotic options when the pricing formulas of Chapter 26 are used. Suppose the. volatility surface shows that the correct volatility to use when pricing a one-year plain. vanilla option with a strike price of $\$40$ $27\%$ . This is liable to be totally inappropriate for pricing a barrier option (or some other exotic option) that has a strike price of. $\$40$ and a life of one year.  

The first part of this chapter discusses a number of alternatives to geometric Brownian motion that are designed to deal with the problem of pricing exotic options consistently with plain vanilla options. These alternative asset price processes fit the market prices of plain vanilla options better than geometric Brownian motion. As a result, we can have more confidence in using them to value exotic options.  

The second part of the chapter extends the discussion of numerical procedures. It explains how convertible bonds and some types of path-dependent derivatives can be. valued using trees. It discusses the special problems associated with valuing barrier options numerically and how these problems can be handled. Finally, it outlines alternative ways of constructing trees for two correlated variables and shows how Monte Carlo simulation can be used to value derivatives when there are early exercise. opportunities.  

As in earlier chapters, results are presented for derivatives dependent on an asset providing a yield at rate $q$ . For an option on a stock index, $q$ should be set equal to the dividend yield on the index; for an option on a currency, it should be set equal to the foreign risk-free rate; for an option on a futures contract, it should be set equal to the domestic risk-free rate.  
