---
tags:
  - '#correlation_trading'
  - '#exotic_options'
  - '#implied_volatility'
  - '#matlab_exercises'
  - '#nasdaq_100'
  - '#risk_reversals'
  - '#s_and_p_500'
  - '#sterling_volatility'
  - '#volatility_smile'
  - '#volatility_swaps'
---
# 15.9 CONCLUSIONS  

This chapter provided a brief introduction to a sector that may, in the future, play an even more sig-. nificant role in financial market strategies. Our purpose was to show how we can isolate the volatility of a risk factor from other related risks, and then construct instruments that can be used to trade it. An important point should be emphasized here. The introductory discussion contained in this chapter deals with the case where the volatility parameter is a function of time and the underlying. price only. These methods have to be modified for more complex volatility specifications..  

# SUGGESTED READING  

Rebonato (2000) and (2002) are good places to start getting acquainted with the various notions of volatility. Bossu et al. (2o05) provide a good introduction to variance swaps. Some of the material in this chapter comes directly from Demeterfi et al. (1999), where the reader will find proper references to the literature as well. The important paper by Dupire (1992) and the literature it generated can be consulted for local volatility.  

# EXERCISES  

1. Read the quote carefully and describe how you would take this position using volatility swaps. Be precise about the parameters of these swaps..  

a. How would you price this position? What does pricing mean in this context anyway Which price are we trying to determine and write in the contract?.   
b. In particular, do you need the correlations between the two markets?   
c. Do you need to know the smile before you sell the position?.   
d. Discuss the risks involved in this volatility position  

# Volatility Swaps  

A bank is recommending a trade in which investors can take advantage of the wide differential between Nasdaq 100 and S&P500 longer-dated implied volatilities..  

Two-year implied volatility on the Nasdaq 100 was last week near all-time highs, at around $45.7\%$ but the tumult in tech stocks over the last several years is largely played out,. said [a] global head of equity derivatives strategy in New York. The tech stock boom appears to be over, as does the most eye-popping part of the downturn, he added. While there will be. selling pressure on tech companies over the next several quarters, a dramatic sell-off similar to what the market has seen over the last six months is unlikely..  

The bank recommends entering a volatility swap on the differential between the Nasdaq. and the S&P, where the investor receives a payout if the realized volatility in two years is. less than about $21\%$ the approximate differential last week between the at-the-money. forward two-year implied volatilities on the indices. The investor profits here if, in two years, the realized two-year volatility for the Nasdaq has fallen relative to the equivalent volatility on the S&P.  

It might make sense just to sell Nasdaq vol, said [the trader], but it's better to put on a. relative value trade with the Nasdaq and S&P to help reduce the volatility beta in the Nasdaq position. In other words, if there is a total market meltdown, tech stocks and the market as a whole will see higher implied vols. But volatility on the S&P500, which represents stocks in a broader array of sectors, is likely to increase substantially, while volatility on the Nasdaq is already close to all-time highs. A relative value trade where the investor takes a view on the differential between the realized volatility in two years time on the two indices allows the investor to profit from a fall in Nasdaq volatility relative to. the S& P.  

The two-year sector is a good place to look at this differential, said [the trader]. Two years is enough time for the current market turmoil, particularly in the technology sector, to play itself out, and the differential between two-year implied vols, at about $22\%$ last week, is near all-time high levels. Since 1990, the realized volatility differential has tended to be closer to $10.7\%$ over long periods of time.  

[The trader] noted that there are other means of putting on this trade, such as selling two-year at-the-money forward straddles on Nasdaq volatility and buying two-year at-themoney forward straddles on S&P vol. (Derivatives Week (now part of GlobalCapital), October 30, 2000)  

2. The following reading deals with another example of how spread positions on volatility can be taken. Yet, of interest here are further aspects of volatility positions. In fact, the episode is an example of the use of knock-in and knock-out options in volatility positions.  

a. Suppose the investor sells short-dated (1-month) volatility and buys 6-month volatility. In what sense is this a naked volatility position? What are the risks? Explain using volatility swaps as an underlying instrument.   
b. Explain how a 1-month break-out clause can hedge this situation.   
c. How would the straddles gain value when the additional premium is triggered?   
d. What are the risks, if any, of the position with break-out clauses?  

e. Is this a pure volatility position?  

Sterling volatility is peaking ahead of the introduction of the euro next year. A bank suggests the following strategy to take advantage of the highly inverted volatility curve.. Sterling will not join the euro in January and the market expects reduced sterling positions. This view has pushed up one-month sterling/Deutsche mark vols to levels of $12.6\%$ early last week. In contrast, six-month vols are languishing at under. $9.2\%$ This suggests selling short-. dated vol and buying six-month vols. Customers can buy a six-month straddle with a onemonth break-out clause added to replicate a short volatility position in the one-month maturity. This way they don't have a naked volatility position. (Based on an article in. Derivatives Week (now part of GlobalCapital).).  

# MATLAB EXERCISES  

3. (Variance swap price). Write a MATLAB program to illustrate the variation of the price of an (equity) variance swap with respect to the change in the mean return of the underlying stock and also show this on a graph. Use the following parameters for the specification of the stochastic process followed by the underlying. : $S(0)=100\$ $T=1$ $r=8\%$ $\sigma=30\%$ $\mu=10\%$  

4. (Volatility swap price). Write a MATLAB program to show the invariance of the volatility payoff of a delta hedged long call for the various frequency of delta adjustment until the time of expiry of the call. Use the following data: $S(0)=100\$ $K=105$ $T=1$ $r=8\%$ $\sigma=30\%$ and realized volatility $=50\%$ Plot the graph for the volatility payoff for 20 simulations for the adjustment frequencies 10, 20, 50, 100, and 500.  

This page intentionally left blank  

# CORRELATION AS AN ASSET CLASS AND THE SMILE  

# 16  

# CHAPTER OUTLINE  

16.1 Introduction to Correlation as an Asset Class. 546   
16.1.1 Reasons for Trading Correlation. 547   
16.1.2 Correlation Trading Vehicles 547   
16.2 Volatility as Funding.. 551   
16.3 Smile .. . 551   
16.4 Dirac Delta Functions . 552   
16.5 Application to Option Payoffs .. 554   
16.5.1 An Interpretation of Dynamic Hedging.. 556   
16.6 Breeden-Litzenberger Simplified.. 558   
16.6.1 The Proof.. 560   
16.7 A Characterization of Option Prices as Gamma Gains.. 561   
16.7.1 Relationship to Tanaka's Formula. 562   
16.8 Introduction to the Smile 562   
16.9 Preliminaries. 563   
16.10 A First Look at the Smile 564   
6.11 What Is the Volatility Smile?. . 565   
16.11.1 Some Stylized Facts.. 567   
16.11.2 How Can We Define Moneyness?.. 570   
16.11.3 Replicating the Smile . 572   
16.11.3.1 Contractual equations. 573   
16.12 Smile Dynamics .. 574   
16.13 How to Explain the Smile. .574   
16.13.1 Case 1: Nongeometric Price Processes. 577   
16.13.2 Case 2: Possibility of Crash. 577   
16.13.2.1 Modeling crashes 580   
16.13.3 Other Explanations 581   
16.13.3.1 Structural and regulatory explanations. 582   
16.14 The Relevance of the Smile .. 582   
16.15 Trading the Smile.. . 583   
16.16 Pricing with a Smile. 583   
16.17 Exotic Options and the Smile 584   
16.17.1 A Hedge for a Barrier. 584  

16.17.2 Effects of the Smile. 585  

Principles of Financial Engineering. Copyright $\copyright$ 2015 Elsevier Inc. All rights reserved. 545  

16.17.2.1 An example of technical difficulties. 586   
16.17.2.2 Pricing exotics. 586   
16.17.3 The Case of Digital Options. 587   
16.17.4 Another Application: Risk Reversals. 587   
16.18 Conclusions... . 588   
Suggested Reading 588   
Exercises ... . 588   
Excel Exercise.. 589   
MATLAB Exercises. . 590  
