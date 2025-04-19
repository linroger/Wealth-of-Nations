---
tags:
  - exotic_options
  - option_strategies
  - payoff_diagrams
  - risk_reversals
  - volatility_strategy
aliases:
  - Chapter 11
  - Conclusions
  - Exotic Options
  - Option Strategies
key_concepts:
  - Bear spread
  - Danish krone assets
  - Engineering similar positions
  - European-style options
  - Plain vanilla futures
  - Risk reversals
  - Short position in strangle
  - Single risk factor
  - Static positions
  - Synthetically create payoff diagrams
---

# 11.7 CONCLUSIONS  

In this chapter, we discussed how to synthetically create payoff diagrams for positions that take a view on the direction of markets and on the direction of volatility. These were static positions. We specifically concentrated on the payoff diagrams that were functions of a single risk factor and that were to be replicated by plain vanilla futures and options positions. The second part of the chapter discussed the engineering of similar positions using simple exotics.  

# SUGGESTED READING  

There are several excellent books that deal with classic option strategies. Hull (2014) is a very good start. The reader may also consult Natenberg (2014) for option basics. See also the textbooks Jarrow and Turnbull (1999) and Kolb (1999). Taleb (1996) is a good source on exotics from a market perspective. For a technical approach, consider the chapter on exotics in Musiela and Ruthkowski (2007). James (2003) is a good source on the technicalities of option trading and option pricing formulas. It also provides a good discussion of exotics.  

# EXERCISES  

1. Construct a payoff and profit diagram for the purchase of a 105-strike call and sale of a 95-. strike call. Verify that you obtain exactly the same profit diagram for the purchase of a 105-. strike put and a sale of 95-strike put. Explain the difference in the initial cost of these positions. Assume the following parameters: $S(0)=100\$ $T=1$ $r=8\%$ $\sigma=30\%$  

2. Assume that a trader believes that during the vacation periods actual realized volatility is lower than the implied volatility. To exploit this opportunity a trader takes a short position in a strangle to cover the cost of the long straddle position. If the actual volatility is $30\%$ less than the implied volatility, sketch out his volatility strategy. Assume the following parameters:  

$$
S(0)=1600;T=3\mathrm{month};r=5\%;\sigma=53\%
$$  

3. Consider a bear spread. An investor takes a short position in a futures denoted by $x_{t}$ But he or she thinks that $x_{t}$ will not fall below a level $x^{\mathrm{min}}$  

a. How would you create a position that trades off gains beyond a certain level against large losses if $x_{t}$ increases above what is expected?   
b. How much would you pay for this position?   
c.What is the maximum gain? What is the maximum loss?   
d. Show your answers in an appropriate figure.  

4. Consider this reading carefully and then answer the questions that follow.  

A bank suggested risk reversals to investors that want to hedge their Danish krone assets,. before Denmark's Sept. 28 referendum on whether to join the Economic and Monetary Union. A currency options trader in New York said the strategy would protect customers against the. Danish krone weakening should the Danes vote against joining the EMU. Danish public. reports show that sentiment against joining the EMU has been picking up steam over the past few weeks, although the "Yes" vote is still slightly ahead. [He] noted that if the Danes vote for joining the EMU, the local currency would likely strengthen, but not significantly..  

Six- to 12-month risk reversals last Monday were. $0.25\%/0.45\%$ in favor of euro calls.. [He] said a risk-reversal strategy would be zero cost if a customer bought a euro call struck at DKK7.52 and sold a euro put at DKK7.44 last Monday when the Danish krone spot was. at DKK7.45 to the euro. The options are European-style and the tenor is 6 months..  

Last Monday, 6- and 12-month euro/Danish krone volatility was at. $1.55\%/l.95\%$ up from $0.6\%/0.9\%$ for the whole year until April 10, 2000, owing to growing bias among Danes. against joining the EMU. On the week of April 10, volatility spiked as a couple of banks bought 6-month and 9-month, at-the-money vol. (Based on Derivatives Week (now part of. GlobalCapital), April 24, 2000.)  

a. Plot the zero-cost risk-reversal strategy on a diagram. Show the DKK7.44 and DKK7.52 put and call explicitly.   
b. Note that the spot rate is at DKK7.45. But, this is not the midpoint between the two. strikes. How can this strategy have zero cost then?.   
c. What would this last point suggest about the implied volatilities of the two options?   
d. What does the statement "Last Monday, 6- and 12-month euro/Danish krone volatility was at $1.55\%/l.95\%$ ," mean?   
e. What does at-the-money vol mean? (See the last sentence.) Is there out-of-the-money. vol, then?  

5. The following questions deal with range binaries. These are another example of exotic options. Read the following carefully and then answer the questions at the end.  

Investors are looking to purchase range options. The product is like a straightforward range binary in that the holder pays an upfront premium to receive a fixed pay-off as long as spot maintains a certain range. In contrast to the regular range binary, however, the barriers only come into existence after a set period of time. That is, if spot breaches the range before the barriers become active, the structure is not terminated.  

This way, the buyer will have a short Vega position on high implied volatility levels. (Based on an article in Derivatives Week (now part of GlobalCapital).)  

a. Display the payoff diagram of a range-binary option. b. Why would FX markets find this option especially useful? c. When do you think these options will be more useful? d. What are the risks of a short position in range binaries?  

6. Double no-touch options is another name for range binaries. Read the following carefully, and then answer the questions at the end..  

Fluctuating U.S. dollar/yen volatility is prompting option traders managing their books to capture high volatilities through range binary structures while hedging with butterfly trades.   
Popular trades include one-year double no touch options with barriers of JPY126 and.   
JPY102. Should the currency pair stay within that range, traders could benefit from a.   
USD1 million payout on premiums of. $15{-}20\%$  

On the back of those trades, there was buying of butterfly structures to hedge short vol positions. Traders were seen buying out-of-the-money dollar put/yen calls struck at JPY102 and an out-of-the-money dollar call/yen put struck at JPY126. (Based on an article in Derivatives Week (now part of GlobalCapital).)  

a. Display the payoff diagram of the structure mentioned in the first paragraph.   
b. When do you think these options will be more useful?.   
c. What is the role of butterfly structures in this case?.   
d. What are the risks of a short position in range binaries?.   
e. How much money did such a position make or lose "last Tuesday"?  

7. The next question deals with a different type range option, called a range accrual option. Range. accrual options can be used to take a view on volatility directly. When a trader is short volatility, the trader expects the actual volatility to be less than the implied volatility. Yet, within the bounds of classical volatility analysis, if this view is expressed using a vanilla option, it may require dynamic hedging, otherwise expensive straddles must be bought. Small shops may not. be able to allocate the necessary resources for such dynamic hedging activities..  

Instead, range accrual options can be used. Here, the buyer of the option receives a payout that depends on how many days the underlying price has remained within a range during the life of the option. First read the following comments then answer the questions.  

The Ontario Teachers' Pension Plan Board, with CAD72 billion (USD48.42 billion) under management, is looking at ramping up its use of equity derivatives as it tests programs for. range accrual options and options overwriting on equity portfolios..  

The equity derivatives group is looking to step up its use now because it has recently been awarded additional staff as a result of notching up solid returns, said a portfolio manager for Canadian equity derivatives.... With a staff of four, two more than previously, the group. has time to explore more sophisticated derivatives strategies, a trader explained. Ontario Teachers' is one of the biggest and most sophisticated end users in Canada and is seen as. an industry leader among pension funds, according to market officials..  

A long position in a range accrual option on a single stock would entail setting a range for the value of the stock. For every day during the life of the option that the stock trades within the range, Ontario Teachers would receive a payout. It is, hence, similar to a short vol position, but the range accrual options do not require dynamic hedging, and losses are capped at the initial premium outlay. (Based on an article in Derivatives Week (now part of GlobalCapital).)  

a. How is a range accrual option similar to a strangle or straddle position?   
b. Is the position taken with this option static? Is it dynamic?   
c. In what sense does the range accrual option accomplish what dynamic hedging strategies accomplish?   
d. How would you synthetically create a range accrual option for other "vanilla' exotics?  

# EXCEL EXERCISES  

8. Write a VBA program to show the construction of a bull and bear spread, first using calls only and then using puts only. Also plot both the call spread and put spread in both bull and bear. phases. Explain your observation for the difference in the initial cost of call and put spreads..  

Assume the following parameters: $S(0)=100\$ $T=1$ $r=8\%$ $\sigma=30\%$ ; Spread $=10\%$  

9. Write a VBA program to show the fabrication of the butterfly spread composed of a strangle and straddle. Assume the following parameters: $S(0)=100\$ $T=1$ $r=8\%$ $\sigma=30\%$ ; Spread $=5\%$ Plot the straddle and strangle payoff along with the payoff of the butterfly spread. Repeat the above calculation for the short position in butterfly spread.  

# MATLAB EXERCISE  

10. Write a MATLAB program to plot the following spreads including the time value of the spread as well as its payoff at the expiration.. a. Bull spread  