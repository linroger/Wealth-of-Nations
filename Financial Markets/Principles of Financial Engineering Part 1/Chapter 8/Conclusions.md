---
tags:
  - algebraic_equations
  - contractual_equations
  - dynamic_replication
  - static_replication
  - synthetic_instruments
aliases:
  - Chapter 8
  - Conclusions
  - Dynamic Synthetics
key_concepts:
  - Algebraic equations
  - Contractual equations
  - Dynamic synthetic creation
  - Immunization example
  - Static replication
---

# 8.8 CONCLUSIONS  

We finish the chapter with an important observation. Static replication was best done using cash flow diagrams and resulted in contractual equations with constant weights..  

Creating synthetics dynamically requires constant adjustments and careful selection of portfolio weights $\theta_{t}^{i}$ , in order to make the synthetic self-financing. Thus, we again use contractual equations, but this time, the weights placed on each contract change as time passes. This requires the use of algebraic equations and is done with computers.  

Finally, the dynamic synthetic is nothing but the sequence of weights $\{\theta_{1}^{i},\theta_{2}^{i},...,\theta_{n}^{i}\}$ that the financial engineer will determine at time $t_{0}$  

# SUGGESTED READING  

Several books deal with dynamic replication. Often these are intermediate-level textbooks on derivatives and financial markets. We have two preferred sources that the reader can consult for further examples. The first is Jarrow (2002). This book deals with fixed-income examples only. The second is Jarrow and Turnbull (1999), where dynamic replication methods are discussed in much more detail with a broad range of applications. The reader can also consult the original Cox and Ross (1976a) article. It remains a very good summary of the procedure.  

# EXERCISES  

1. Consider the immunization example given in Section 8.4. Assume that the zero-coupon yield. curve is flat at $y=5\%$ and not $8\%$ as in the example. The shifts in the yield curve are parallel.. What positions and how many units of the 6-month bond and the 3-year bond are needed to create an approximate synthetic that will fund the 2-year bond?.  

2. Suppose you are given the following data: The risk-free interest rate is $6\%$ The stock price follows:  

$$
\mathrm{d}S_{t}=\mu S_{t}\mathrm{~d}t+\sigma S_{t}\mathrm{~d}W_{t}
$$  

Volatility is $12\%$ a year.   
The stock pays no dividends and the current stock price is 100.  

Using these data, you are asked to approximate the current value of a European call option on the stock. The option has a strike price of 100 and a maturity of 200 days.  

a. Determine an appropriate time interval $\Delta$ , such that an implied binomial tree has five steps.   
b. What is the implied up probability? Hint: To obtain the probability we need to discretize the stochastic differential equation.   
c. Determine the tree for the stock price $S_{t}$   
d. Determine the tree for the call premium $C_{t}$  

3. Suppose the stock discussed in Exercise 1 pays dividends. Assume all parameters are the same. Consider three forms of dividends paid by the firm:.  

a. The stock pays a continuous, known stream of dividends at a rate of $4\%$ per time.   
b. The stock pays $5\%$ of the value of the stock at the third node. No other dividends are paid.   
c. The stock pays a $\$5$ dividend at the third node..  

In each case, determine the tree for the ex-dividend stock price. For the first two cases, determine the premium of the call. In what way(s) does the third type of dividend payment. complicate the binomial tree?  

4. You are going to use binomial trees to value American-style options on the British pound. Assume that the British pound is currently worth $\$1.40$ .Volatility is $10\%$ . The current British risk-free rate is $5\%$ , and the US risk-free rate is $2\%$ . The put option has a strike price of $\$1.50$ It expires in 200 days. American-style options can be exercised before expiration.  

a. The first issue to be settled is the role of US and British interest rates. This option is being purchased in the United States, so the relevant risk-free rate is $2\%$ . But British pounds can be used to earn British risk-free rates. So this variable can be treated as a continuous rate of dividends.  

Taking this into account, determine a. $\Delta$ such that the binomial tree has five periods.. b. Determine the relevant probabilities. Use a similar method to the one used to value the European stock call option above.. c. Determine the tree for the exchange rate.. d. Determine the tree for a European put with the same characteristics.. e. Determine the price of an American style put with these properties.  

5. Consider the reading that follows which deals with the effects of straightforward delta hedging. Read the events described and then answer the questions that follow.  

Dynamic Hedging  

US equity option market participants were of one voice last week in refuting the notion that [dynamic hedging due to] equity options trading had exacerbated the stock market correction of late October, which saw the Dow Jones Industrial Average fall 554.26 points, or some $7\%$  

Dynamic hedging is a strategy in which investors buy and sell stocks to create a payout,. which is the same as going long and short options. Thus, if the market takes a big drop, a. writer of puts sells stock to cut their losses. Dynamic hedgers buy and sell stock to achieve the position they desire to equalize their exposure to volatility.  

The purpose of dynamic hedging, also known as delta hedging, is to remain marketneutral. The hedger's objective is to have no directional exposure to the market. For example, the hedgers will buy puts, giving them the right to sell stock. They are thus essentially short the market. To offset this short position, the hedger will purchase the underlying stock. The investor is now long the put and long the stock, and thereby market-neutral.  

If the market falls, the investor's put goes in-the-money, increasing the short exposure to the market. To offset this, the investor will sell the underlying...  

"It is my humble opinion that few investors use dynamic hedging. If somebody is selling options, i.e. selling volatility, they will have an offsetting position where they are long volatility. People don't take big one-sided bets," said a senior official at another U.S. derivatives exchange. (Thomson Reuters IFR, issue 832)  

a. Suppose there are a lot of put writers. How would these traders hedge their position? Show using appropriate payoff diagrams.   
b. What would these traders do when markets start falling? Show on payoff diagrams.   
c. Now suppose an option's trader is short volatility as the last paragraph implies. Describe how this trader can be long volatility "somewhere else.".   
d. Is it possible that the overall market is a bit short volatility, yet that this amount is still very. substantial for the underlying (cash) markets?.  

There are many special terms in this reading, but at this point we would like to emphasize. one important aspect of dynamic hedging that was left unmentioned in the chapter. As mentioned in the reading, in order to dynamically hedge a nonlinear asset, we need a delta..  

Delta is the sensitiveness of the option to underlying price changes. Now if this asset is indeed. nonlinear, then the delta will depend on the volatility of underlying risks. If this volatility is itself dependent on many factors, such as the strike price, then there will be a volatility smile and delta hedging may be inaccurate..  

To this effect, suppose you have a long options' position on FTSE-100. How would you. delta hedge this position? More important, how would this delta hedge be affected by the observations in the last paragraph of the reading?.  

5. How could you determine whether the trees in Figure 8.7 are arbitrage-free or not?  

7. Consider the replication of a European call option. Write a VBA program to show the dynamic hedging strategy using only stocks and a saving account to replicate a short European option. Calculate the position in both the stock and the savings account for all the intermediate time points and all possible states. Use the binomial model with the following data:  

$S(0)=100\$ $K=110$ $T=3$ $\sigma=30\%$ $M=3$   
$L(0)=1$ $\sigma=5\%$   
Use the value of $u=\mathrm{e}^{(\sigma\sqrt{\Delta t+(r-\sigma^{2}/2)\Delta t)}}$ and $d={\mathrm{e}}^{(-\sigma{\sqrt{\Delta t+(r-\sigma^{2}/2)\Delta t)}}}$  

# MECHANICS OF OPTIONS  

#  

# CHAPTER OUTLINE  

3.1 Introduction. 268   
9.2 What Is an Option?. 269   
9.3 Options: Definition and Notation. 271   
9.3.1 Notation.. 271   
9.3.2 On Retail Use of Options. 275   
9.3.3 Some Intriguing Properties of the Diagram... 275   
4 Options as Volatility Instruments... 277   
9.4.1 Initial Position and the Hedge 277   
9.4.2 Adjusting the Hedge Over Time... .281   
9.4.2.1 Limiting form..... .284   
9.4.3 Other Cash Flows... 285   
9.4.4 Option Gains and Losses as a PDE. 285   
9.4.5 Cash Flows at Expiration 286   
9.4.6 An Example . 287   
9.4.6.1 Some caveats.. .288   
.5 Tools for Options. 289   
9.5.1 Solving the Fundamental PDE 289   
9.5.2 Black-Scholes Formula. 290   
9.5.2.1 Black's formula .291   
9.5.3 Other Formulas .. 292   
9.5.3.1 Chooser options .292   
9.5.3.2 Barrier options .293   
9.5.4 Uses of Black-Scholes Type Formulas 295   
9.6 The Greeks and Their Uses. 296   
9.6.1 Delta. 297   
9.6.1.1 Convention... 298   
9.6.1.2 The exact expression. 298   
9.6.2 Gamma.. 300   
9.6.2.1 Market use.. .302   
9.6.3 Vega... 303   
9.6.3.1 Market use. .305   
9.6.3.2 Vega hedging. .305   
9.6.4 Theta . 305   
9.6.5 Omega.. 306  

9.6.6 Higher-Order Derivatives 306   
9.6.7 Greeks and PDEs. 307   
9.6.7.1 Gamma trading .308   
9.6.7.2 Gamma trading versus Vega .308   
9.6.7.3 Which expectation?. .309   
9.7 Real-Life Complications... 309   
9.7.1 Dealing with Option Books 310   
9.7.2 Futures as Underlying.. 310   
9.7.2.1 Delivery mismatch.. .311   
9.8 Conclusion: What Is an Option?... 311   
Suggested Reading . 311   
Appendix 9.1 ... 311   
Derivation of Delta.... 311   
Derivation of Gamma ..... 313   
Appendix 9.2 . 313   
Stochastic Differential Equations... 313   
Examples . 313   
Ito's Lemma. 314   
Girsanov Theorem.. .314   
Exercises .... .315  
