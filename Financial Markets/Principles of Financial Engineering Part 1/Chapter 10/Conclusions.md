---
tags:
  - arbitrage
  - bond_pricing
  - convexity
  - fixed_income
  - futures
  - hedging
  - libor
  - quanto
  - term_structure
  - yield_curve
aliases:
  - Bond Convexity
  - Conclusions
  - Convexity Gains
  - Delta Hedging
  - Quanto Instruments
key_concepts:
  - Convexity gains
  - Convexity gains from bonds
  - Covariance between risks
  - Eurodollar contract
  - Fixed income and convexity
  - Interest rate changes
  - Pricing equations and risk factors
  - Replicating portfolios and weights
  - Term structure models
  - Zero-cost portfolio
---

# 10.6 CONCLUSIONS  

Pricing equations depends on one or more risk factors. When the pricing functions are nonlinear,. replicating portfolios that use linear assets with periodically adjusted weights will lead to positive or negative cash flows during the hedging process. If the underlying volatilities and correlations are significant, trading gains from these may exceed the transaction costs implied by periodic rebalan-. cing, and the underlying nonlinearity can be traded.  

In this chapter, we saw two basic examples of this: one from the fixed-income sector which. made convexity of bonds valuable, and the second from quanto instruments, which also brought in the covariance between risks. The example on quantos is a good illustration of what happens when term structure models depend on more than one factor. In such an environment, the covariances as well as the volatilities between the underlying risks may become important..  

# SUGGESTED READING  

Two introductory sources discuss the convexity gains one can extract from fixed-income instruments. They are Serrat and Tuckman (2011) and Jegadeesh and Tuckman (2000). The convexity differences between futures and forwards are clearly handled in Hull (2014). The discussion of the quanto feature used here is from Piros (1998), which is in DeRosa (1998). Wilmott (2006) has a nice discussion of quantoed assets as well.  

# EXERCISES  

1. You are given the following default-free long bond: Face value: 100 Issuing price: 100 Currency: USD Maturity: 30 years Coupon: $6\%$ No implicit calls or puts. Further, in this market there are no bid--ask spreads and no trading commissions. Finally, the yield curve is flat and moves only parallel to itself..  

There is, however, a futures contract on the 1-year LIBOR rate. The price of the contract is determined as  

$$
V_{t}=100(1-f_{t})
$$  

where $f_{t}$ is the "forward rate" on 1-year LIBOR.  

a. Show that if the yield of the 30-year bond is $y_{t},$ then at all times we have.  

$$
y_{t}=f_{t}
$$  

b. Plot the pricing functions for $V_{t}$ and the bond..  

c. Suppose the current yield $y_{0}$ is at $7\%$ . Put together a zero-cost portfolio that is delta-neutral toward movements of the yield curve.  

d. Consider the following yield movements over 1-year periods:  

$$
9\%,7\%,9\%,7\%,9\%,7\%
$$  

What are the convexity gains during this period?  

e.What other costs are there?  

2. You are given a 30-year bond with yield. $y$ . The yield curve is flat and will have only parallel. shifts. You have a liquid 3-month Eurodollar contract at your disposition. You can also borrow and lend at a rate of $5\%$ initially.  

a. Using the long bond and the Eurodollar contract, construct a delta-hedged portfolio that is immune to interest rate changes. b. Now suppose you observe the following interest rate movements over a period of 1 year:  

These observations are each 2 months apart. What are your convexity gains from a long volatility position?  

3. Consider the data given in the previous question.  

a. Suppose an anticipated movement as in the previous question. Market participants suddenly move to an anticipated trajectory such as.  

Assuming that this was the only exogenous change in the market, what do you think will happen to the yield on the 30-year bond?  

4. Assuming that the yield curve is flat and has only parallel shifts, determine the spread between the paid-in-arrear FRAs and market-traded linear FRAs if the FRA rates are expected to oscillate as follows around an initial rate:.  

$$
\{+0.02,-0.02,+0.02,-0.02,+0.02,-0.02\}
$$  

5. Answer the following questions related to the case study \*Convexity of long bonds, convexity and arbitrage."  

a. First the preliminaries. Explain what is meant by convexity of long-dated bonds.   
b. What is meant by the convexity of long-dated interest rate swaps?   
c. Explain the notion of convexity using a graph.   
d. If bonds are convex, which fixed-income instrument is not convex?   
e. Describe the cash flows of FRAs. When are FRAs settled in the market?   
f. What is the convexity adjustment for FRAs?   
g. What is a cap? What volatility do you buy or sell using caps?   
h. Now the real issue. Explain the position taken by \*knowledgeable" professionals. i. In particular, is this a position on the direction of rates or something else? In fact, can you. explain why the professionals had to hedge their position using caps or floors?   
j. Do they have to hedge using caps only? Can floors do as well? Explain your answer graphically.  

k. Is this a true arbitrage? Are there any risks?  

# MATLAB EXERCISES  

6. Consider the Vasicek model  

$$
\mathrm{d}r=\alpha(\mu-r)\mathrm{d}t+\sigma\mathrm{d}W\_t
$$  

Plot the term structure (i.e., plot yield versus time) for the following parameter sets $[\upalpha,\upmu,\upsigma,\mathbf{r}(0)]$  

Now for the first parameter set plot the term structure by varying only one parameter at a time and report your observation.  

7. Consider the "CIR (Cox-Ingersoll-Ross)" model  

$$
\mathrm{d}r=\alpha(\mu-r)\mathrm{d}t+\sigma\sqrt{r\mathrm{d}W\_t}
$$  

Plot the term structure (i.e., plot yield versus time) for the following parameter sets $[\upalpha,\upmu,\upsigma,\mathbf{r}(0)]$  

Now for the third parameter set, plot the term structure by varying only one parameter at a time and report your observation.  

# CASE STUDY: CONVEXITY OF LONG BONDS, SWAPS, AND ARBITRAGE  

The yield of a long bond tells you how much you can earn from this bond. Correct? Wrong. You can earn more.  

The reason is that long bonds and swaps have convexity. If there are two instruments, one linear and the other. nonlinear, and if these are a function of the same risk factors, we can form a portfolio that is delta-neutral and that guarantees some positive return.  

This is a complex and confusing notion and the purpose of this case study is to clarify this notion a bit.  

At first, the case seems simple. Take a look at the following single reading provided on an arbitrage position taken 'y market professionals and answer the questions that follow..  

The more sophisticated traders in the swaps market-or at least those who have been willing to work alongside their in-house quants--have until recently been playing a game of one-upmanship to the detriment of their more naive. interbank counterparties. By taking into account the convexity effect on long-dated swaps, they have been able to profit from the ignorance of their counterparties who saw no reason to change their own valuation methods..  

More specifically, several months ago several leading Wall Street US dollar swaps houses--reportedly JP Morgan. and Goldman Sachs among them-realized that there was more value than met the eye when pricing LIBOR-in-arrears swaps. According to London traders, they began to arbitrage the difference between their own valuation models and. those of "swap traders who still relied on naive, traditional methods" and transacting deals where they would receive. LIBOR in arrears and pay LIBOR at the start of the period, typically for notional amounts of Us\$100m and over..  

Depending on the length of the swap and the LIBOR reset intervals, they realized that they could extract up to an additional 8-10 bp from the transaction, irrespective of the shape of the yield curve. The counterparty, on the other hand, would see money "seep away over the life of the swap, even if it thought it was fully hedged," said a trader.  

The added value is only significant on long-dated swaps-typically between five and 10 years-and in particular those based on 12-month LIBOR rather than the more traditional six-month LIBOR basis. This value is due to the convexity effect more commonly associated with the relationship between yields and the price of fixed income. instruments.  

It therefore pays to be long convexity, and when applied to LIBOR-in-arrears structures proved to be profitable earlier this year. The first deals were transacted in New York and were restricted to the US dollar market, but in early May several other players were alerted to what was going on in the market and decided to apply the same concept in London. One trader expressed surprise at the lack of communication between dealers at different banks, a fact which allowed the arbitrage to continue both between banks directly and through swaps brokers.  

Also, "none of the US banks active in the market was involved in trying to exploit the same opportunities in other currencies," he said, adding "you could play the same game in sterling-convexity applies to all currencies."  

In fact, there was one day in May when the sterling market was flooded with these transactions, and it "lasted for several days" according to a sterling swaps dealer, "until everyone moved their prices out," effectively putting a damper on further opportunities as well as making it difficult to unwind positions..  

Further, successful structures depend on cap volatility as the extra value is captured by selling caps against the LIBOR-in-arrears being received, in addition to delta hedging the swap. In this way value can be extracted from yield curves irrespective of the slope. "In some cap markets such as the yen, volatility isn't high enough to make the deal work," said one dealer. Most of the recent interbank activity has taken place in US dollars, sterling, and Australian dollars.. As banks have become aware of the arbitrage, opportunities have become rarer, at least in the interbank market. But as one dealer remarked, "the reason this [structure] works is because swap traders think they know how to value LIBOR-in-arrears swaps in the old way, and they stick to those methods." "Paying LIBOR in arrears without taking the convexity effect into account," he added, "is like selling an option for free, but opportunities will still exist where traders stick to the old pricing method." Many large swap players last week declined to comment, suggesting that the market is still alive, although BZw in London, which has been active in the market, did say that it saw such opportunities as a chance to pass on added value to its own customers. (Thomson Reuters IFR issue 1092, July 29, 1995)  

This page intentionally left blank  

# OPTIONS ENGINEERING WITH 11 APPLICATIONS  

# CHAPTER OUTLINE  

1.1 Introduction. 352   
11.1.1 Payoff Diagrams. 352   
11.1.1.1 Examples ofxt. 354   
1.2 Option Strategies . .355   
11.2.1 Synthetic Long and Short Positions. 355   
11.2.1.1 An application. 357   
11.2.1.2 Arbitrage opportunity?. 360   
11.2.2 A Remark on the Pin Risk. 361   
11.2.3 Risk Reversals.. 361   
11.2.3.1 Uses of risk reversals. 363   
11.2.4 Yield Enhancement Strategies 364   
11.2.4.1 Call overwriting. 365   
1.3 Volatility-Based Strategies.... . 367   
11.3.1 Strangles.... 369   
11.3.1.1 Uses of strangles. 369   
11.3.2 Straddle . 370   
11.3.2.1 Static or dynamic position?... 370   
11.3.3 Butterfly... .372   
I.4 Exotics .... .373   
11.4.1 Binary, or Digital, Options 373   
11.4.1.1 A binary call. . 374   
11.4.1.2 Replicating the binary call.. 374   
11.4.1.3 Delta and price of binaries. 376   
11.4.1.4 Time value of binaries. 377   
11.4.1.5 Uses of the binary. 377   
11.4.2 Barrier Options... 378   
11.4.2.1 A contractual equation. 380   
11.4.2.2 Some uses of barrier options. 383   
11.4.3 New Risks.. 384   
1.5 Quoting Conventions.. 384   
11.5.1 Example 1.. 386   
11.5.2 Example 2. 387  

11.6 Real-World Complications. 387   
11.6.1 The Role of the Volatility Smile. 387   
11.6.2 Existence of Position Limits 388   
1.7 Conclusions. 388   
Suggested Reading . 388   
Exercises 389   
EXCEL Exercises .. 391   
MATLAB Exercise 391  
