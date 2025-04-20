---
tags:
  - arbitrage
  - asset_pricing
  - derivatives
  - financial_mathematics
  - interest_rates
  - mathematical_modeling
  - options
  - quantitative_finance
  - risk_management
  - stochastic_processes
aliases:
  - Financial Mathematics
key_concepts:
  - Arbitrage theory
  - Asset pricing models
  - Black-Scholes model
  - Complete markets
  - Continuous-time models
  - Derivative securities
  - Discrete-time models
  - Financial mathematics
  - Interest rate theory
  - Martingale measures
  - Option pricing
  - Risk management
  - Risk-neutral pricing
  - Stochastic calculus
  - Term structure models
---
# Financial Mathematics I  

Lecture Notes Universitat Ulm  
# Content.  

This course covers the fundamental principles and techniques of financial mathematics in discrete and continuous-time models. The focus will be on probabilistic techniques which will be discussed in some detail. Specific topics are  

Classical Asset Pricing: Mean-Variance Analysis, CAPM, Arbitrage,
Martingale-based stochastic market models: Fundamental Theorems of Asset Pricing.   
Contingent Claim Analysis: European, American and Exotic Options.   
.Interest Rate Theory: Term Structure Models, Interest Rate Derivatives.  
Pre-requisites. Probability Theory, Calculus, Linear Algebra  
# Contents  

# Arbitrage Theory 5  

# 1.1 Derivative Background . 5  

1.1.1 Derivative Instruments . 5   
1.1.2 Underlying securities 7   
1.1.3 Markets 8   
1.1.4 Types of Traders 8   
1.1.5 Modelling Assumptions 9   
1.2 Arbitrage 10   
1.3 Arbitrage Relationships 12   
1.3.1 Fundamental Determinants of Option Values 12   
1.3.2Arbitrage bounds . 14   
1.4 Single-Period Market Models 15   
1.4.1 A fundamental example 15   
1.4.2 A single-period model 17   
1.4.3 A few financial-economic considerations 22  

# 2 Financial Market Theory 24  

# 2.1 Choice under Uncertainty. 24  

2.1.1 Preferences and the Expected Utility Theorem 24   
2.1.2 Risk Aversion . 25   
2.1.3 Further measures of risk 28   
2.2 Optimal Portfolios 31   
2.2.1 The mean-variance approach 31   
2.2.2 Capital asset pricing model. 34   
2.2.3 Portfolio optimisation and the absence of arbitrage 35  

# 3 Discrete-time models 39  

# 3.1 The model. 39  

3.2 Existence of Equivalent Martingale Measures 42   
3.2.1 The No-Arbitrage Condition 42   
3.2.2Risk-Neutral Pricing . 45   
3.3 .3Complete Markets 47   
3.4 The Cox-Ross-Rubinstein Model 49   
3.4.1 Model Structure 50   
3.4.2 Risk-Neutral Pricing 51   
3.4.3 Hedging .. 53   
3.5 Binomial Approximations 56   
3.5.1Model Structure 56   
3.5.2 The Black-Scholes Option Pricing Formula. 57   
3.6 American Options 60   
3.6.1 Stopping Times, Optional Stopping and Snell Envelopes 60   
3.6.2 The Financial Model .. 67   
3.6.3 American Options in the Cox-Ross-Rubinstein model . 68   
3.6.4A Three-period Example 69  

# Continuous-time Financial Market Models 72  

4.1 The Stock Price Process and its Stochastic Calculus 72  

4.1.1 Continuous-time Stochastic Processes 72   
4.1.2 Stochastic Analysis .. 73   
4.1.3 Ito's Lemma 76   
4.1.4 Girsanov's Theorem. 79   
Financial Market Models .. 80   
4.2.1 The Financial Market Model 80   
4.2.2 Equivalent Martingale Measures 82   
4.2.3 Risk-neutral Pricing 83   
4.2.4 The Black-Scholes Model 84   
4.2.5 The Greeks 87   
4.2.6 Barrier Options . 89  

# 5 Interest Rate Theory 91  

# 5.1 The Bond Market .  

5.1.1 The Term Structure of Interest Rates. 91   
5.1.2 Mathematical Modelling 92   
5.1.3 Bond Pricing, ... 96   
5.2 Short-rate Models 96   
5.2.1 The Term-structure Equation. 97   
5.2.2 Martingale Modelling 98   
5.3 Heath-Jarrow-Morton Methodology 99   
5.3.1 The Heath-Jarrow-Morton Model Class 99   
5.3.2 Forward Risk-neutral Martingale Measures 101   
5.4 Pricing and Hedging Contingent Claims 102   
5.4.1 Gaussian HJM Framework .. 102   
5.4.2 Swaps 103   
5.4.3 Caps 104  

# A Basic Probability Background 106  

A.1 Fundamentals 106   
A.2 Convolution and Characteristic Functions 108   
A.3 The Central Limit Theorem 112  

# B Facts form Probability and Measure Theory 115  

B.1 Measure 115   
B.2 Integral 118   
B.3Probability 120   
B.4 Equivalent Measures and Radon-Nikodym Derivatives 124   
B.5 Conditional expectation 125   
B.6 Modes of Convergence 131  

# C Stochastic Processes in Discrete Time 133  

C.1 Information and Filtrations 133   
C.2 Discrete-Parameter Stochastic Processes 134   
C.3 Definition and basic properties of martingales 135   
C.4 Martingale Transforms 136  

# Chapter 1  

# Arbitrage Theory  

# 1.1 Derivative Background  

Definition 1.1.1. A derivative security, or contingent claim, is a financial contract whose value at expiration date $T$ (more briefly, expiry) is determined exactly by the price (or prices within $a$ prespecified time-interval) of the underlying financial assets (or instruments) at time $T$ (within the time interval $[0,T]$  

This section provides the institutional background on derivative securities, the main groups of underlying assets, the markets where derivative securities are traded and the financial agents involved in these activities. As our focus is on (probabilistic) models and not institutional considerations we refer the reader to the references for excellent sources describing institutions such as Davis (1994), Edwards and Ma (1992) and Kolb (1991).  

# 1.1.1 Derivative Instruments  

Derivative securities can be grouped under three general headings: Options, Forwards and Futures and Swaps. During this text we will mainly deal with options although our pricing techniques may be readily applied to forwards, futures and swaps as well..  

# Options.  

An option is a financial instrument giving one the right but not the obligation to make a specified transaction at (or by) a specified date at a specified price. Call options give one the right to buy. Put options give one the right to sell. European options give one the right to buy/sell on the specified date, the expiry date, on which the option expires or matures. American options give one the right to buy/sell at any time prior to or at expiry.  

Over-the-counter (OTC) options were long ago negotiated by a broker between a buyer and a seller. In 1973 (the year of the Black-Scholes formula, perhaps the central result of the subject), the Chicago Board Options Exchange (CBOE) began trading in options on some stocks. Since. then, the growth of options has been explosive. Options are now traded on all the major world. exchanges, in enormous volumes. Risk magazine (12/97) estimated \$35 trillion as the gross figure. for worldwide derivatives markets in 1996. By contrast, the Financial Times of 7 October 2002 (Special Report on Derivatives) gives the interest rate and currency derivatives volume as. $\S$ 83 trillion - an indication of the rate of growth in recent years! The simplest call and put options. are now so standard they are called vanilla options. Many kinds of options now exist, including so-called exotic options. Types include: Asian options, which depend on the average price over a period, lookback options, which depend on the maximum or minimum price over a period and barrier options, which depend on some price level being attained or not.  

Terminology. The asset to which the option refers is called the underlying asset or the un-. derlying. The price at which the transaction to buy/sell the underlying, on/by the expiry date (if exercised), is made, is called the exercise price or strike price. We shall usually use $K$ for the strike price, time $t=0$ for the initial time (when the contract between the buyer and the seller of. the option is struck), time. $t=T$ for the expiry or final time..  

Consider, say, a European call option, with strike price $K$ ; write $S(t)$ for the value (or price). of the underlying at time. $t$ . If $S(t)>K$ , the option is in the money, if $S(t)=K$ , the option is. said to be at the money and if $S(t)<K$ , the option is out of the money.  

The payoff from the option, which is  

$$
S(T)-K{\mathrm{~if~}}S(T)>K\quad{\mathrm{and}}\quad0{\mathrm{~otherwise}}
$$  

(more briefly written as $(S(T)-K)^{+}$ ). Taking into account the initial payment of an investor one obtains the profit diagram below..  

profit  

![](b991efadb49b157353998ac2e67d54bd7f559e61c063d9c0be1e944df81b545c.jpg)  
Figure 1.1: Profit diagram for a European call  

# Forwards  

A forward contract is an agreement to buy or sell an asset. $S$ at a certain future date $T$ for a certain price $K$ . The agent who agrees to buy the underlying asset is said to have a long position, the. other agent assumes a short position. The settlement date is called delivery date and the specified price is referred to as delivery price. The forward price. $f(t,T)$ is the delivery price which would make the contract have zero value at time $t$ . At the time the contract is set up, $t=0$ , the forward price therefore equals the delivery price, hence $f(0,T)=K$ . The forward prices $f(t,T)$ need not (and will not) necessarily be equal to the delivery price $K$ during the life-time of the contract.  

The payoff from a long position in a forward contract on one unit of an asset with price $S(T)$ at the maturity of the contract is  

$$
S(T)-K.
$$  

Compared with a call option with the same maturity and strike price $K$ we see that the investor. now faces a downside risk, too. He has the obligation to buy the asset for price $K$  

# Swaps  

A swap is an agreement whereby two parties undertake to exchange, at known dates in the future, various financial assets (or cash flows) according to a prearranged formula that depends on the  

value of one or more underlying assets. Examples are currency swaps (exchange currencies) and interest-rate swaps (exchange of fixed for floating set of interest payments)..  

# 1.1.2 Underlying securities  

# Stocks.  

The basis of modern economic life - or of the capitalist system - is the limited liability company (UK: & Co. Ltd, now plc - public limited company), the corporation (US: Inc.), 'die Aktiengesellschaft' (Germany: AG). Such companies are owned by their shareholders; the shares.  

provide partial ownership of the company, pro rata with investment, have value, reflecting both the value of the company's (real) assets and the earning power of the company's dividends..  

With publicly quoted companies, shares are quoted and traded on the Stock Exchange. Stock is the generic term for assets held in the form of shares.  

# Interest Rates.  

The value of some financial assets depends solely on the level of interest rates (or yields), e.g. Treasury (T-) notes, T-bills, T-bonds, municipal and corporate bonds. These are fixed-income securities by which national, state and local governments and large companies partially finance their economic activity. Fixed-income securities require the payment of interest in the form of a fixed amount of money at predetermined points in time, as well as repayment of the principal at. maturity of the security. Interest rates themselves are notional assets, which cannot be delivered.. Hedging exposure to interest rates is more complicated than hedging exposure to the price movements of a certain stock. A whole term structure is necessary for a full description of the level of interest rates, and for hedging purposes one must clarify the nature of the exposure carefully. We will discuss the subject of modelling the term structure of interest rates in Chapter 8..  

# Currencies.  

A currency is the denomination of the national units of payment (money) and as such is a financial asset. The end of fixed exchange rates and the adoption of floating exchange rates resulted in a. sharp increase in exchange rate volatility. International trade, and economic activity involving it, such as most manufacturing industry, involves dealing with more than one currency. A company. may wish to hedge adverse movements of foreign currencies and in doing so use derivative instru-. ments (see for example the exposure of the hedging problems British Steel faced as a result of the. sharp increase in the pound sterling in 96/97 Rennocks (1997)).  

# Indexes.  

An index tracks the value of a (hypothetical) basket of stocks (FT-SE100, S&P-500, DAX), bonds (REX), and so on. Again, these are not assets themselves. Derivative instruments on indexes may be used for hedging if no derivative instruments on a particular asset (a stock, a bond, a commodity) in question are available and if the correlation in movement between the index and the asset is significant. Furthermore, institutional funds (such as pension funds, mutual funds etc.), which manage large diversified stock portfolios, try to mimic particular stock indexes and use derivatives on stock indexes as a portfolio management tool. On the other hand, a speculator may wish to bet on a certain overall development in a market without exposing him/herself to a particular asset.  

A new kind of index was generated with the Index of Catastrophe Losses (CAT-Index) by the. Chicago Board of Trade (CBOT) lately. The growing number of huge natural disasters (such as. hurricane Andrew 1992, the Kobe earthquake 1995) has led the insurance industry to try to find new ways of increasing its capacity to carry risks. The CBOT tried to capitalise on this problem. by launching a market in insurance derivatives. Currently investors are offered options on the CAT-Index, thereby taking in effect the position of traditional reinsurance..  

Derivatives are themselves assets - they are traded, have value etc. - and so can be used as underlying assets for new contingent claims: options on futures, options on baskets of options, etc. These developments give rise to so-called exotic options, demanding a sophisticated mathematical machinery to handle them.  

# 1.1.3 Markets  

Financial derivatives are basically traded in two ways: on organized exchanges and over-thecounter (OTC). Organised exchanges are subject to regulatory rules, require a certain degree of standardisation of the traded instruments (strike price, maturity dates, size of contract etc.) and have a physical location at which trade takes place. Examples are the Chicago Board Options Exchange (CBOE), which coincidentally opened in April 1973, the same year the seminal contributions on option prices by Black and Scholes Black and Scholes (1973) and Merton Merton (1973) were published, the London International Financial Futures Exchange (LIFFE) and the Deutsche Terminborse (DTB).  

OTC trading takes place via computers and phones between various commercial and investment banks (leading players include institutions such as Bankers Trust, Goldman Sachs - where Fischer Black worked, Citibank, Chase Manhattan and Deutsche Bank).  

Due to the growing sophistication of investors boosting demand for increasingly complicated, made-to-measure products, the OTC market volume is currently (as of 1998) growing at a much faster pace than trade on most exchanges.  

# 1.1.4 Types of Traders  

We can classify the traders of derivative securities in three different classes:  

# Hedgers.  

Successful companies concentrate on economic activities in which they do best. They use the.   
market to insure themselves against adverse movements of prices, currencies, interest rates etc.   
Hedging is an attempt to reduce exposure to risk a company already faces. Shorter Oxford English.   
Dictionary (OED): Hedge: 'trans. To cover oneself against loss on (a bet etc.) by betting, etc.,.   
on the other side. Also fig. 1672.'.  

# Speculators.  

Speculators want to take a position in the market - they take the opposite position to hedgers. Indeed, speculation is needed to make hedging possible, in that a hedger, wishing to lay off risk, cannot do so unless someone is willing to take it on.  

In speculation, available funds are invested opportunistically in the hope of making a profit: the underlying itself is irrelevant to the investor (speculator), who is only interested in the potential. for possible profit that trade involving it may present. Hedging, by contrast, is typically engaged in by companies who have to deal habitually in intrinsically risky assets such as foreign exchange next year, commodities next year, etc. They may prefer to forgo the chance to make exceptional windfall profits when future uncertainty works to their advantage by protecting themselves against exceptional loss. This would serve to protect their economic base (trade in commodities, or manufacture of products using these as raw materials), and also enable them to focus their effort in their chosen area of trade or manufacture. For speculators, on the other hand, it is the market. (forex, commodities or whatever) itself which is their main forum of economic activity.  

# Arbitrageurs.  

Arbitrageurs try to lock in riskless profit by simultaneously entering into transactions in two or more markets. The very existence of arbitrageurs means that there can only be very small arbitrage opportunities in the prices quoted in most financial markets. The underlying concept of this book is the absence of arbitrage opportunities (cf. 1.2).  

# 1.1.5 Modelling Assumptions  

# Contingent Claim Pricing.  

The fundamental problem in the mathematics of financial derivatives is that of pricing. The modern theory began in 1973 with the seminal Black-Scholes theory of option pricing, Black and Scholes (1973), and Merton's extensions of this theory, Merton (1973).  

To expose the relevant features, we start by discussing contingent claim pricing in the simplest. (idealised) case and impose the following set of assumptions on the financial markets (We will relax these assumptions subsequently):  

Table 1.1: General assumptions   


<html><body><table><tr><td>Nomarketfrictions No default risk Competitivemarkets Rationalagents Noarbitrage</td><td>No transaction costs, no bid/ask spread, no taxes, no margin requirements, no restrictions on short sales Implying e interest for borrowing and lending same Market participants act as price takers Market participants prefer more to less</td></tr></table></body></html>  

All real markets involve frictions; this assumption is made purely for simplicity. We develop. the theory of an ideal - frictionless - market so as to focus on the irreducible essentials of the theory and as a first-order approximation to reality. Understanding frictionless markets is also a necessary step to understand markets with frictions..  

The risk of failure of a company - bankruptcy - is inescapably present in its economic activity:. death is part of life, for companies as for individuals. Those risks also appear at the national level: quite apart from war, or economic collapse resulting from war, recent decades have seen default of interest payments of international debt, or the threat of it. We ignore default risk for simplicity. while developing understanding of the principal aspects (for recent overviews on the subject we. refer the reader to Jameson (1995), Madan (1998)).  

We assume financial agents to be price takers, not price makers. This implies that even large amounts of trading in a security by one agent does not influence the security's price. Hence agents can buy or sell as much of any security as they wish without changing the security's price.  

To assume that market participants prefer more to less is a very weak assumption on the preferences of market participants. Apart from this we will develop a preference-free theory.  

The relaxation of these assumptions is subject to ongoing research and we will include comments on this in the text.  

We want to mention the special character of the no-arbitrage assumption. If we developed a. theoretical price of a financial derivative under our assumptions and this price did not coincide with the price observed, we would take this as an arbitrage opportunity in our model and go on to. explore the consequences. This might lead to a relaxation of one of the other assumptions and a. restart of the procedure again with no-arbitrage assumed. The no-arbitrage assumption thus has a special status that the others do not. It is the basis for the arbitrage pricing technique that we. shall develop, and we discuss it in more detail below..  

# 1.2 Arbitrage  

We now turn in detail to the concept of arbitrage, which lies at the centre of the relative pricing.   
theory. This approach works under very weak assumptions. We do not have to impose any.   
assumptions on the tastes (preferences) and beliefs of market participants. The economic agents may be heterogeneous with respect to their preferences for consumption over time and with respect.   
to their expectations about future states of the world. All we assume is that they prefer more to.   
less, or more precisely, an increase in consumption without any costs will always be accepted..  

The principle of arbitrage in its broadest sense is given by the following quotation from OED: '3 [Comm.]. The traffic in Bills of Exchange drawn on sundry places, and bought or sold in sight of the daily quotations of rates in the several markets. Also, the similar traffic in Stocks. 1881.'  

Used in this broad sense, the term covers financial activity of many kinds, including trade. in options, futures and foreign exchange. However, the term arbitrage is nowadays also used in a narrower and more technical sense. Financial markets involve both riskless (bank account) and risky (stocks, etc.) assets. To the investor, the only point of exposing oneself to risk is. the opportunity, or possibility, of realising a greater profit than the riskless procedure of putting all one's money in the bank (the mathematics of which - compound interest - does not require. a textbook treatment at this level). Generally speaking, the greater the risk, the greater the return required to make investment an attractive enough prospect to attract funds. Thus, for instance, a clearing bank lends to companies at higher rates than it pays to its account holders. The companies' trading activities involve risk; the bank tries to spread the risk over a range of different loans, and makes its money on the difference between high/risky and low/riskless interest. rates.  

The essence of the technical sense of arbitrage is that it should not be possible to guarantee a profit without exposure to risk. Were it possible to do so, arbitrageurs (we use the French spelling, as is customary) would do so, in unlimited quantity, using the market as a 'money-pump' to extract arbitrarily large quantities of riskless profit. This would, for instance, make it impossible for the market to be in equilibrium. We shall restrict ourselves to markets in equilibrium for simplicity - so we must restrict ourselves to markets without arbitrage opportunities.  

The above makes it clear that a market with arbitrage opportunities would be a disorderly. market - too disorderly to model. The remarkable thing is the converse. It turns out that the minimal requirement of absence of arbitrage opportunities is enough to allow one to build a model. of a financial market which - while admittedly idealised - is realistic enough both to provide real. insight and to handle the mathematics necessary to price standard contingent claims. We shall see that arbitrage arguments suffice to determine prices - the arbitrage pricing technique. For an. accessible treatment rather different to ours, see e.g. Allingham (1991)..  

To explain the fundamental arguments of the arbitrage pricing technique we use the following:  

# Example.  

Consider an investor who acts in a market in which only three financial assets are traded: (riskless) bonds $B$ (bank account), stocks $S$ and European Call options. $C$ with strike. $K=1$ on the stock.. The investor may invest today, time. $t=0$ , in all three assets, leave his investment until time. $t=T$ and get his returns back then (we assume the option expires at $t=T$ , also). We assume the current. $\mathcal{L}$ prices of the financial assets are given by.  

$$
B(0)=1,S(0)=1,C(0)=0.2
$$  

and that at $t=T$ there can be only two states of the world: an up-state with $\mathcal{L}$ prices  

$$
B(T,u)=1.25,S(T,u)=1.75,\mathrm{and~therefore}C(T,u)=0.75,
$$  

and a down-state with $\mathcal{L}$ prices  

$$
B(T,d)=1.25,S(T,d)=0.75,\mathrm{andtherefore}C(T,d)=0.
$$  

Table 1.2: Original portfolio   


<html><body><table><tr><td>Financial asset</td><td>Number of</td><td>Total amount in f</td></tr><tr><td>Bond</td><td>10</td><td>10</td></tr><tr><td>Stock</td><td>10</td><td>10</td></tr><tr><td>Call</td><td>25</td><td>5</td></tr></table></body></html>  

Now our investor has a starting capital of $\mathcal{L}25$ , and divides it as in Table 1.2 below (we call such a division a portfolio). Depending of the state of the world at time $t=T$ this portfolio will give t he $\mathcal{L}$ return shown in Table 1.3. Can the investor do better? Let us consider the restructured in the different possible future states (Table 1.5). We see that this portfolio generates the same time $t=T$ return while costing only $\mathcal{L}24.6$ now, a saving of $\mathcal{L}0.4$ against the first portfolio. So the investor should use the second portfolio and have a free lunch today!  

Table 1.3: Return of original portfolio   


<html><body><table><tr><td>State of the world</td><td>Bond</td><td>Stock</td><td>Call</td><td>Total</td></tr><tr><td>Up Down</td><td>12.5 12.5</td><td>17.5 7.5</td><td>18.75 0</td><td>48.75 20.</td></tr></table></body></html>  

portfolio of Table 1.4. This portfolio requires only an investment of $\mathcal{L}24.6$ . We compute its return   
Table 1.4: Restructured portfolio   


<html><body><table><tr><td>Financial asset</td><td>Number of</td><td>Total amount in f</td></tr><tr><td>Bond</td><td>11.8</td><td>11.8</td></tr><tr><td>Stock</td><td>7</td><td>7</td></tr><tr><td>Call</td><td>29</td><td>5.8</td></tr></table></body></html>  

In the above example the investor was able to restructure his portfolio, reducing the current (time $t=0$ ) expenses without changing the return at the future date. $t=T$ in both possible states of the world. So there is an arbitrage possibility in the above market situation, and the prices quoted are not arbitrage (or market) prices. If we regard (as we shall do) the prices of the bond. and the stock (our underlying) as given, the option must be mispriced. We will develop in this. book models of financial market (with different degrees of sophistication) which will allow us to find methods to avoid (or to spot) such pricing errors. For the time being, let us have a closer look at the differences between portfolio 1, consisting of 10 bonds, 10 stocks and 25 call options, in short $(10,10,25)$ , and portfolio 2, of the form (11.8, 7, 29). The difference (from the point of view of portfolio 1, say) is the following portfolio, D:. $\left(-1.8,3,-4\right)$ . Sell short three stocks (see below), buy four options and put. $\mathcal{L}1.8$ in your bank account. The left-over is exactly the. $\mathcal{L}0.4$ of the example. But what is the effect of doing that? Let us consider the consequences in the possible states of the world. From Table 1.6 below, we see in both cases that the effects of the different positions of the portfolio offset themselves. But clearly the portfolio generates an income at $t=0$ and is therefore itself an arbitrage opportunity.  

If we only look at the position in bonds and stocks, we can say that this position covers us against possible price movements of the option, i.e. having. $\mathcal{L}1.8$ in your bank account and being. three stocks short has the same time. $t=T$ effects of having four call options outstanding against. us. We say that the bond/stock position is a hedge against the position in options..  

Let us emphasise that the above arguments were independent of the preferences and plans of the investor. They were also independent of the interpretation of. $t=T$ : it could be a fixed time, maybe a year from now, but it could refer to the happening of a certain event, e.g. a stock hitting a certain level, exchange rates at a certain level, etc..  

Table 1.5: Return of the restructured portfolio   


<html><body><table><tr><td>State of the world</td><td>Bond</td><td>Stock</td><td>Call</td><td>Total</td></tr><tr><td>Up</td><td>14.75</td><td>12.25</td><td>21.75</td><td>48.75</td></tr><tr><td>Down</td><td>14.75</td><td>5.25</td><td>0</td><td>20.</td></tr></table></body></html>  

Table 1.6: Difference portfolio   


<html><body><table><tr><td>world is in state up</td><td>world is in state down</td></tr><tr><td>exercise option 3 buy 3 stocks at 1.75 -5.25 sell bond 2.25</td><td>option is worthless 0 buy 3 stocks at 0.75 -2.25 sell bond 2.25</td></tr><tr><td>Balance 二</td><td>Balance</td></tr></table></body></html>  

# 1.3 Arbitrage Relationships  

We will in this section use arbitrage-based arguments (arbitrage pricing technique) to develop. general bounds on the value of options. Such bounds, deduced from the underlying assumption. that no arbitrage should be possible, allow one to test the plausibility of sophisticated financial market models.  

In our analysis here we use stocks as the underlying.  

# 1.3.1 Fundamental Determinants of Option Values  

We consider the determinants of the option value in table 1.7 below. Since we restrict ourselves to non-dividend paying stocks we don't have to consider cash dividends as another natural determinant.  

Table 1.7: Determinants affecting option value   


<html><body><table><tr><td>Current stock price</td><td>S(t)</td></tr><tr><td>Strike price</td><td>K</td></tr><tr><td>Stockvolatility</td><td></td></tr><tr><td>Time to expiry</td><td>-L</td></tr><tr><td>Interest rates</td><td>r</td></tr></table></body></html>  

We now examine the effects of the single determinants on the option prices (all other factors remaining unchanged).  

We saw that at expiry the only variables that mattered were the stock price $S(T)$ and strike price $K$ : remember the payoffs $C=(S(T)-K)^{+},P=(S(T)-K)^{-}(:=\operatorname*{max}\{K-S(T),0\})$ Looking at the payoffs, we see that an increase in the stock price will increase (decrease) the value of a call (put) option (recall all other factors remain unchanged). The opposite happens if the strike price is increased: the price of a call (put) option will go down (up)..  

When we buy an option, we bet on a favourable outcome. The actual outcome is uncertain; its uncertainty is represented by a probability density; favourable outcomes are governed by the tails. of the density (right or left tail for a call or a put option). An increase in volatility flattens out the density and thickens the tails, so increases the value of both call and put options. Of course, this. argument again relies on the fact that we don't suffer from (with the increase of volatility more. likely) more severe unfavourable outcomes - we have the right, but not the obligation, to exercise. the option.  

A heuristic statement of the effects of time to expiry or interest rates is not so easy to make.. In the simplest of models (no dividends, interest rates remain fixed during the period under consideration), one might argue that the longer the time to expiry the more can happen to the price of a stock. Therefore a longer period increases the possibility of movements of the stock price. and hence the value of a call (put) should be higher the more time remains before expiry. But only the owner of an American-type option can react immediately to favourable price movements,. whereas the owner of a European option has to wait until expiry, and only the stock price then is relevant. Observe the contrast with volatility: an increase in volatility increases the likelihood of favourable outcomes at expiry, whereas the stock price movements before expiry may cancel out themselves. A longer time until expiry might also increase the possibility of adverse effects from which the stock price has to recover before expiry. We see that by using purely heuristic. arguments we are not able to make precise statements. One can, however, show by explicit arbitrage arguments that an increase in time to expiry leads to an increase in the value of call options as well as put options. (We should point out that in case of a dividend-paying stock the. statement is not true in general for European-type options.).  

To qualify the effects of the interest rate we have to consider two aspects. An increase in the. interest rate tends to increase the expected growth rate in an economy and hence the stock price tends to increase. On the other hand, the present value of any future cash fows decreases. These two effects both decrease the value of a put option, while the first effect increases the value of a call option. However, it can be shown that the first effect always dominates the second effect, so. the value of a call option will increase with increasing interest rates..  

The above heuristic statements, in particular the last, will be verified again in appropriate models of financial markets, see \$4.5.4 and 6.2.3..  

We summarise in table 1.8 the effect of an increase of one of the parameters on the value of options on non-dividend paying stocks while keeping all others fixed:  

Table 1.8: Effects of parameters   


<html><body><table><tr><td>Parameter (increase)</td><td>Call</td><td>Put</td></tr><tr><td>Stock price Strike price Volatility Interest rates Time to expiry</td><td>Positive Negative Positive Positive Positive</td><td>Negative Positive Positive Negative</td></tr></table></body></html>  

We would like to emphasise again that these results all assume that all other variables remain fixed, which of course is not true in practice. For example stock prices tend to fall (rise) when interest rates rise (fall) and the observable effect on option prices may well be different from the effects deduced under our assumptions.  

Cox and Rubinstein (1985), p. 37-39, discuss other possible determining factors of option. value, such as expected rate of growth of the stock price, additional properties of stock price. movements, investors' attitudes toward risk, characteristics of other assets and institutional environment (tax rules, margin requirements, transaction costs, market structure). They show that.  

in many important circumstances the influence of these variables is marginal or even vanishing.  

# 1.3.2 Arbitrage bounds  

We now use the principle of no-arbitrage to obtain bounds for option prices. Such bounds, de-. duced from the underlying assumption that no arbitrage should be possible, allow one to test the plausibility of sophisticated financial market models. We focus on European options (puts. and calls) with identical underlying (say a stock. $S$ ), strike $K$ and expiry date $T$ . Furthermore we assume the existence of a risk-free bank account (bond) with constant interest rate. $r$ (continuously compounded) during the time interval $[0,T]$ . We start with a fundamental relationship:  

Proposition 1.3.1. We have the following put-call parity between the prices of the underlying asset $S$ and European call and put options on stocks that pay no dividends:.  

$$
S+P-C=K e^{-r(T-t)}.
$$  

Proof. Consider a portfolio consisting of one stock, one put and a short position in one call (the holder of the portfolio has written the call); write. $V(t)$ for the value of this portfolio. Then.  

$$
V(t)=S(t)+P(t)-C(t)
$$  

for all. $t\in[0,T]$ . At expiry we have  

$$
V(T)=S(T)+(S(T)-K)^{-}-(S(T)-K)^{+}=S(T)+K-S(T)=K.
$$  

This portfolio thus guarantees a payoff $K$ at time $T$ .Using the principle of no-arbitrage, the value of the portfolio must at any time $t$ correspond to the value of a sure payoff $K$ at $T$ , that is. V(t) = Ke-r(T-t).  

Having established (1.1), we concentrate on European calls in the following.  

Proposition 1.3.2. The following bounds hold for European call options:  

$$
\operatorname*{max}\left\{S(t)-e^{-r(T-t)}K,0\right\}=\left(S(t)-e^{-r(T-t)}K\right)^{+}\leq C(t)\leq S(t).
$$  

Proof. That $C\geq0$ is obvious, otherwise buying' the call would give a riskless profit now and no obligation later.  

Similarly the upper bound $C\leq S$ must hold, since violation would mean that the right to. buy the stock has a higher value than owning the stock. This must be false, since a stock offers additional benefits.  

Now from put-call parity (1.1) and the fact that $P\geq0$ (use the same argument as above), we. have  

$$
S(t)-K e^{-r(T-t)}=C(t)-P(t)\leq C(t),
$$  

which proves the last assertion.  

It is immediately clear that an American call option can never be worth less than the corresponding European call option, for the American option has the added feature of being able to be exercised at any time until the maturity date. Hence (with the obvious notation): $C_{A}(t)\geq C_{E}(t)$ The striking result we are going to show (due to R.C. Merton in 1973, (Merton 1990), Theorem 8.2) is:  

Proposition 1.3.3. For a non-dividend paying stock we have  

$$
C_{A}(t)=C_{E}(t).
$$  

Proof. Exercising the American call at time $t<T$ generates the cash-flow $S(t)-K$ .From Proposition 1.3.2 we know that the value of the call must be greater or equal to $S(t)-K e^{-r(T-t)}$ which is greater than $S(t)-K$ . Hence selling the call would have realised a higher cash-flow and. the early exercise of the call was suboptimal.  

Remark 1.3.1. Qualitatively, there are two reasons why an American call should not be exercised early:  

(i) Insurance. An investor who holds a call option instead of the underlying stock is insured against a fall in stock price below $K$ , and if he exercises early, he loses this insurance.   
(ii) Interest on the strike price. When the holder exercises the option, he buys the stock and pays the strike price, $K$ .Early exercise at $t<T$ deprives the holder of the interest on $K$ between times t and $^T$ : the later he pays out $K$ , the better.  

We remark that an American put offers additional value compared to a European put.  

# 1.4 Single-Period Market Models  

# 1.4.1 A fundamental example  

We consider a one-period model, i.e. we allow trading only at $t=0$ and $t=T=1(\mathrm{say})$ . Our aim is to value at. $t=0$ a European derivative on a stock $S$ with maturity. $T$  

First idea. Model. $S_{T}$ as a random variable on a probability space $(\Omega,{\mathcal{F}},I P)$ . The derivative is given by $H=f(S_{T})$ , i.e. it is a random variable (for a suitable function $f(.)$ ). We could then. price the derivative using some discount factor $\beta$ by using the expected value of the discounted future payoff:  

$$
H_{0}=D E(\beta H).
$$  

Problem. How should we pick the probability measure. $\mathcal{W}$ ?According to their preferences. investors will have different opinions about the distribution of the price $S_{T}$  

Black-Scholes-Merton (Ross) approach. Use the no-arbitrage principle and construct a hedging portfolio using only known (and already priced) securities to duplicate the payoff $H$ .We assume  

1. Investors are non-satiable, i.e. they always prefer more to less.   
2. Markets do not allow arbitrage , i.e. the possibility of risk-free profits.  

From the no-arbitrage principle we see:  

If it is possible to duplicate the payoff $H$ of a derivative using a portfolio $V$ of underlying (basic). securities, i.e. $H(\omega)=V(\omega)$ $\forall\omega$ , the price of the portfolio at $t=0$ must equal the price of the derivative at. $t=0$  

Let us assume there are two tradeable assets  

: a riskfree bond (bank account) with $B(0)=1$ and $B(T)=1$ , that is the interest rate $r=0$ and the discount factor $\beta(t)=1$ .(In this context we use. $\beta(t)=1/B(t)$ as the discount factor).  

a risky stock $S$ with $S(0)=10$ and two possible values at $t=T$  

$$
S(T)={\left\{\begin{array}{l l}{20}&{{\mathrm{~with~probability~}}p}\ {7.5}&{{\mathrm{~with~probability~}}1-p.}\end{array}\right.}
$$  

We call this setting a $(B,S)-$ market. The problem is to price a European call at $t=0$ with strike $K=15$ and maturity $T$ , i.e. the random payoff. $H=(S(T)-K)^{+}$ . We can evaluate the call in every possible state at. $t=T$ and see $H=5$ (if $S(T)=20$ ) with probability $p$ and $H=0$ (if $S(T)=7.5$ ) with probability $1-p$ . This is illustrated in figure (1.4.1).  

The key idea now is to try to find a portfolio combining bond and stock, which synthesizes the cash flow of the option. If such a portfolio exists, holding this portfolio today would be equivalent to holding the option - they would produce the same cash flow in the future. Therefore the price of the option should be the same as the price of constructing the portfolio, otherwise investors could just restructure their holdings in the assets and obtain a riskfree profit today.  

![](ab3438638b76b47c8b52a633d92876a8a9bf2afafa8f4a494e424976392037a0.jpg)  
Figure 1.2: One-period example  

We briefly present the constructing of the portfolio $\pmb{\theta}=(\theta_{0},\theta_{1})$ , which in the current setting is. just a simple exercise in linear algebra. If we buy. $\theta_{1}$ stocks and invest $\theta_{0}$ $\mathrm{\mathcal{L}}$ in the bank account,. then today's value of the portfolio is  

$$
V(0)=\theta_{0}+\theta_{1}\cdot S(0).
$$  

In state 1 the stock price is $20~\mathrm{£}\mathrm{~d}^{.}$ and the value of the option $^\textrm{\scriptsize5\textrm{d}}$ , so  

$$
\theta_{0}+\theta_{1}\cdot20=5.
$$  

In state 2 the stock price is 7.5  and the value of the option $0 \$£^{\ast}$ , SO  
$$
\theta_{0}+\theta_{1}\cdot7.5=0.
$$

We solve this and get $\theta_{0}=-3\quad\mathrm{and}\quad\theta_{1}=0.4$ So the value of our portfolio at time $0$ in $£$ is  

$$
V(0)=-3B(0)+0.4S(0)=-3+0.4\times10=1
$$  

$V(0)$ is called the no-arbitrage price. Every other price allows a riskless profit, since if the option is too cheap, buy it and finance yourself by selling short the above portfolio (i.e. sell the portfolio without possessing it and promise to deliver it at time $T=1$ this is riskfree because you own the option). If on the other hand the option is too dear, write it (i.e. sell it in the market) and cover yourself by setting up the above portfolio.  

We see that the no-arbitrage price is independent of the individual preferences of the investor. (given by certain probability assumptions about the future, i.e. a probability measure $\mathcal{W}$ ).But one can identify a special, so called risk-neutral, probability measure. ${\mathcal{M}}^{*}$ , such that  

$$
{\cal H}_{0}={\cal I}E^{*}\left(\beta{\cal H}\right)=\left(p^{*}\cdot\beta(S_{1}-K)+\left(1-p^{*}\right)\cdot0\right)=1.
$$  

In the above example we get from $1=p^{*}5+(1-p^{*})0$ that $p^{*}=0.2$ This probability measure ${\mathcal{N}}^{*}$ is equivalent to $\mathcal{W}$ , and the discounted stock price process, i.e. $\beta_{t}S_{t},t=0,1$ follows a ${\mathcal{N}}^{*}$ martingale. In the above example this corresponds to $S(0)=p^{*}S(T)^{u p}+(1-p^{*})S(T)^{d o w n}$ , that is $S(0)=I E^{*}\left(\beta S(T)\right)$  

We will show that the above generalizes. Indeed, we will find that the no-arbitrage condition is equivalent to the existence of an equivalent martingale measure (first fundamental theorem of asset pricing) and that the property that we can price assets using the expectation operator is equivalent to the uniqueness of the equivalent martingale measure..  

Let us consider the construction of hedging strategies from a different perspective. Consider a one-period $(B,S)-$ market setting with discount factor $\beta=1$ . Assume we want to replicate a derivative $H$ (that is a random variable on some probability space $(\Omega,\mathcal{F},I P)$ . For each hedging strategy $\pmb{\theta}=(\theta_{0},\theta_{1})$ we have an initial value of the portfolio $V(0)=\theta_{0}+\theta_{1}S(0)$ and a time $t=T$ value of $V(T)=\theta_{0}+\theta_{1}S(T)$ . We can write $V(T)=V(0)+\left(V(T)-V(0)\right)$ with $G(T)=$ $V(T)-V(0)=\theta_{1}(S(T)-S(0))$ the gains from trading. So the costs $C(0)$ of setting up this portfolio at time $t=0$ are given by $C(0)=V(0)$ , while maintaining (or achieving) a perfect hedge at $t=T$ requires an additional capital of $C(T)=H-V(T)$ . Thus we have two possibilities for finding 'optimal' hedging strategies:  

Mean-variance hedging. Find $\theta_{0}$ (or alternatively $V(0)$ ) and $\theta_{1}$ such that  

$$
E\left((H-V(T))^{2}\right)=E\left(\left(H-\left(V(0)+\theta_{1}(S(T)-S(0))\right)\right)^{2}\right)\rightarrow\mathrm{min}
$$  

.Risk-minimal hedging. Minimize the cost from trading, i.e. an appropriate functional involving the costs $C(t)$ $t=0,T$  

In our example mean-variance hedging corresponds to the standard linear regression problem, and SO  

$$
\theta_{1}=\frac{{\pmb C}o v(H,({\cal S}(T)-{\cal S}(0)))}{{\pmb W}a r({\cal S}(T)-{\cal S}(0))}\mathrm{and}V_{0}={\pmb E}(H)-\theta_{1}{\pmb E}({\cal S}(T)-{\cal S}(0)).
$$  

We can also calculate the optimal value of the risk functional  

$$
R_{\mathrm{min}}={\cal V}a r(H)-\theta_{1}^{2}{\cal W}a r(S(T)-S(0))={\cal V}a r(H)(1-\rho^{2}),
$$  

where $\rho$ is the correlation coefficient of $H$ and $S(T)$ . Therefore we can't expect a perfect hedge in general. If however. $|\rho|=1$ , i.e. $H$ is a linear function of. $S(T)$ , a perfect hedge is possible. We call a market complete if a perfect hedge is possible for all contingent claims.  

# 1.4.2 A single-period model  

We proceed to formalise and extend the above example and present in detail a simple model of. a financial market. Despite its simplicity it already has all the key features needed in the sequel. (and the reader should not hesitate to come back here from more advanced chapters to see the bare concepts again).  

We introduce in passing a little of the terminology and notation of Chapter 4; see also Harrison. and Kreps (1979). We use some elementary vocabulary from probability theory, which is explained in detail in Chapter 2..  

We consider a single period model, i.e. we have two time-indices, say $t=0$ , which is thet current time (date), and $t=T$ , which is the terminal date for all economic activities considered..  

The financial market contains $d+1$ traded financial assets, whose prices at time $t=0$ are denoted by the vector $S(0)\in\mathbb{R}^{d+1}$  

$$
S(0)=(S_{0}(0),S_{1}(0),\ldots,S_{d}(0))^{\prime}
$$  

(where $'$ denotes the transpose of a vector or matrix). At time $T$ , the owner of financial asset number $i$ receives a random payment depending on the state of the world. We model this randomness by introducing a finite probability space $(\Omega,{\mathcal{F}},I P)$ , with a finite number $|\Omega|=N$ of points (each) corresponding to a certain state of the world) $\omega_{1},\ldots,\omega_{j},\ldots,\omega_{N}$ , each with positive probability: ${\cal P}(\{\omega\})>0$ , which means that every state of the world is possible. $\mathcal{F}$ is the set of subsets of $\Omega$ (events that can happen in the world) on which $\mathbb{\textit{P}}(.)$ is defined (we can quantify how probable these events are), here $\mathcal{F}=\mathcal{P}(\Omega)$ the set of all subsets of $\Omega$ .(In more complicated models it is not possible to define a probability measure on all subsets of the state space $\Omega$ , see 2.1.) We can now write the random payment arising from financial asset $i$ as  

$$
S_{i}(T)=(S_{i}(T,\omega_{1}),\dots,S_{i}(T,\omega_{j}),\dots,S_{i}(T,\omega_{N}))^{\prime}.
$$  

At time $t=0$ the agents can buy and sell financial assets. The portfolio position of an individual agent is given by a trading strategy $\varphi$ , which is an $\textstyle\mathit{\Pi}\mathit{{H}}^{d+1}$ vector,  

$$
\varphi=(\varphi_{0},\varphi_{1},\ldots,\varphi_{d})^{\prime}.
$$  

Here $\varphi_{i}$ denotes the quantity of the. $i$ th asset bought at time. $t=0$ , which may be negative as well.   
as positive (recall we allow short positions).  

The dynamics of our model using the trading strategy $\varphi$ are as follows: at time. $t=0$ we invest the amount $\begin{array}{r}{S(0)^{\prime}\varphi=\sum_{i=0}^{d}\varphi_{i}S_{i}(0)}\end{array}$ and at time $t=T$ we receive the random payment $S(T,\omega)^{\prime}\varphi=$ $\textstyle\sum_{i=0}^{d}\varphi_{i}S_{i}(T,\omega)$ depending on the realised state $\omega$ of the world. Using the. $(d+1)\times N$ matrix $\vec{S}$ whose columns are the vectors $S(T,\omega)$ , we can write the possible payments more compactly as $\vec{S}^{\prime}\varphi$  

What does an arbitrage opportunity mean in our model? As arbitrage is 'making something out of nothing; an arbitrage strategy is a vector $\varphi\in\ensuremath{\mathbb{R}}^{d+1}$ such that $S(0)^{\prime}\varphi=0$ , our net investment at time $t=0$ is zero, and  

$$
S(T,\omega)^{\prime}\varphi\geq0,~\forall\omega\in\Omega~\mathrm{and~there~exists~a~}~\omega\in\Omega~\mathrm{such~that}~S(T,\omega)^{\prime}\varphi>0.
$$  

We can equivalently formulate this as: $S(0)^{\prime}\varphi<0$ , we borrow money for consumption at time $t=0$ , and  

$$
S(T,\omega)^{\prime}\varphi\geq0,\forall\omega\in\Omega,
$$  

i.e we don't have to repay anything at $t=T$ . Now this means we had a free lunch' at $t=0$ at the market's expense.  

We agreed that we should not have arbitrage opportunities in our model. The consequences of this assumption are surprisingly far-reaching.  

So assume that there are no arbitrage opportunities. If we analyse the structure of our model. above, we see that every statement can be formulated in terms of Euclidean geometry or linear algebra. For instance, absence of arbitrage means that the space.  

$$
\Gamma=\left\{\left({\begin{array}{l}{x}\ {y}\end{array}}\right),x\in I R,y\in I R^{N}:x=-S(0)^{\prime}\varphi,y={\vec{S}}^{\prime}\varphi,\varphi\in I R^{d+1}\right\}
$$  

and the space  

$$
\displaystyle{I R_{+}^{N+1}=\left\{z\in I R^{N+1}:z_{i}\geq0\forall0\leq i\leq N\quad\exists i\mathrm{suchthat}z_{i}>0\right\}}
$$  

have no common points. A statement like that naturally points to the use of a separation theorem for convex subsets, the separating hyperplane theorem (see e.g. Rockafellar (1970) for an account of such results, or Appendix A). Using such a theorem we come to the following characterisation. of no arbitrage.  

Theorem 1.4.1. There is no arbitrage if and only if there exists a vector  

$$
\psi\in I R^{N},\quad\psi_{i}>0,\forall1\leq i\leq N
$$  

such that  

$$
{\vec{S}}\psi=S(0).
$$  

Proof. The implication. $\cdot\Leftarrow$ ' follows straightforwardly: assume that $S(T,\omega)^{\prime}\varphi\geq0,\omega\in\Omega$ for a vector $\varphi\in\ensuremath{\mathbb{R}}^{d+1}$ Then  

$$
S(0)^{\prime}\varphi=(\vec{S}\psi)^{\prime}\varphi=\psi^{\prime}\vec{S}^{\prime}\varphi\geq0,
$$  

iince $\psi_{i}>0$ $\forall1\leq i\leq N$ . So no arbitrage opportunities exist  

To show the implication $\Rrightarrow$ ' we use a variant of the separating hyperplane theorem. Absence of arbitrage means the $\Gamma$ and $\mathbb{R}_{+}^{N+1}$ have no common points. This means that $K\subset\mathbb{R}_{+}^{N+1}$ defined by  

$$
K=\left\{z\in I R_{+}^{N+1}:\sum_{i=0}^{N}z_{i}=1\right\}
$$  

and $\Gamma$ do not meet. But $K$ is a compact and convex set, and by the separating hyperplane theorem (Appendix C), there is a vector $\lambda\in\mathbb{R}^{N+1}$ such that for all $z\in K$  

$$
\lambda^{\prime}z>0
$$  

but for all $(x,y)^{\prime}\in\Gamma$  

$$
\lambda_{0}x+\lambda_{1}y_{1}+...+\lambda_{N}y_{N}=0.
$$  

Now choosing. $z_{i}=1$ successively we see that $\lambda_{i}>0,i=0,...N$ , and hence by normalising we get $\psi=\lambda/\lambda_{0}$ with $\psi_{0}=1$ . Now set $x=-S(0)^{\prime}\varphi$ and $y=\vec{S^{\prime}}\varphi$ and the claim follows.  

The vector $\psi$ is called a state-price vector. We can think of $\psi_{j}$ as the marginal cost of obtaining an additional unit of account in state $\omega_{j}$ . We can now reformulate the above statement to:  

There is no arbitrage if and only if there exists a state-price vector.  

Using a further normalisation, we can clarify the link to our probabilistic setting. Given a state-price vector $\psi=(\psi_{1},...,\psi_{N})$ , we set $\psi_{0}=\psi_{1}+...+\psi_{N}$ and for any state. $\omega_{j}$ write $q_{j}=\psi_{j}/\psi_{0}$ . We can now view $\left(q_{1},\ldots,q_{N}\right)$ as probabilities and define a new probability measure. on $\Omega$ by $\mathbf{\deltaQ}(\{\omega_{j}\})=q_{j},j=1,\dots,N$ . Using this probability measure, we see that for each asset $i$ we have the relation  

$$
\frac{S_{i}(0)}{\psi_{0}}=\sum_{j=1}^{N}q_{j}S_{i}(T,\omega_{j})=E_{\pmb{Q}}(S_{i}(T)).
$$  

Hence the normalized price of the financial security $i$ is just its expected payoff under some specially chosen 'risk-neutral' probabilities. Observe that we didn't make any use of the specific probability measure $\mathcal{W}$ in our given probability space.  

So far we have not specified anything about the denomination of prices. From a technical point. of view we could choose any asset. $i$ as long as its price vector $(S_{i}(0),S_{i}(T,\omega_{1}),\ldots,S_{i}(T,\omega_{N}))^{\prime}$ only contains positive entries, and express all other prices in units of this asset. We say that we use this asset as numeraire. Let us emphasise again that arbitrage opportunities do not depend on the chosen numeraire. It turns out that appropriate choice of the numeraire facilitates the probability-theoretic analysis in complex settings, and we will discuss the choice of the numeraire in detail later on.  

For simplicity, let us assume that asset $0$ is a riskless bond paying one unit in all states $\omega\in\Omega$ at time $T$ . This means that $S_{0}(T,\omega)=1$ in all states of the world $\omega\in\Omega$ . By the above analysis we must have  

$$
\frac{S_{0}(0)}{\psi_{0}}=\sum_{j=1}^{N}q_{j}S_{0}(T,\omega_{j})=\sum_{j=1}^{N}q_{j}1=1,
$$  

and $\psi_{0}$ is the discount on riskless borrowing. Introducing an interest rate $r$ , we must have $S_{0}(0)=$ $\psi_{0}=(1+r)^{-T}$ . We can now express the price of asset $i$ at time $t=0$ as  

$$
S_{i}(0)=\sum_{j=1}^{N}q_{j}\frac{S_{i}(T,\omega_{j})}{(1+r)^{T}}=E_{Q}\left(\frac{S_{i}(T)}{(1+r)^{T}}\right).
$$  

We rewrite this as  

$$
\frac{S_{i}(T)}{(1+r)^{0}}=E_{Q}\left(\frac{S_{i}(T)}{(1+r)^{T}}\right).
$$  

In the language of probability theory we just have shown that the processes. $S_{i}(t)/(1{+}r)^{t},~t=0,T$   
are $\mathbb{Q}$ -martingales. (Martingales are the probabilists' way of describing fair games: see Chapter 3.) It is important to notice that under the given probability measure. $\mathcal{W}$ (which reflects an individual.   
agent's belief or the markets' belief) the processes $S_{i}(t)/(1+r)^{t},~t=0,T$ generally do not form.   
$\mathcal{W}$ - martingales.  

We use this to shed light on the relationship of the probability measures $\mathcal{W}$ and $\mathbb{Q}$ .Since $\mathbb{Q}(\{\omega\})>0$ for all $\omega\in\Omega$ the probability measures $\mathcal{W}$ and $\mathbb{Q}$ are equivalent and (see Chapters 2 and 3) because of the argument above we call. $\mathbb{Q}$ an equivalent martingale measure. So we arrived. at yet another characterisation of arbitrage:.  

There is no arbitrage if and only if there exists an equivalent martingale measure.  

We also see that risk-neutral pricing corresponds to using the expectation operator with respect. to an equivalent martingale measure. This concept lies at the heart of stochastic (mathematical) finance and will be the golden thread (or roter Faden) throughout this book..  

We now know how the given prices of our $(d+1)$ financial assets should be related in order to <clude arbitrage opportunities, but how should we price a newly introduced financial instrument? We can represent this financial instrument by its random payments $\delta(T)=(\delta(T,\omega_{1}),\dots,\delta(T,\omega_{j}),\dots,\delta(T,\omega_{N}))^{\prime}$ (observe that $\delta(T)$ is a vector in $\mathbb{R}^{N}$ ) at time $t=T$ and ask for its price $\delta(0)$ at time $t=0$ . The natural idea is to use an equivalent probability measure $\mathbb{Q}$ and set  

$$
\delta(0)=E_{Q}(\delta(T)/(1+r)^{T})
$$  

(recall that all time $t=0$ and time $t=T$ prices are related in this way). Unfortunately, as we don't have a unique martingale measure in general, we cannot guarantee the uniqueness of the $t=0$ price. Put another way, we know every equivalent martingale measure leads to a reasonable relative price for our newly created financial instrument, but which measure should one choose?  

The easiest way out would be if there were only one equivalent martingale measure at our disposal - and surprisingly enough the classical economic pricing theory puts us exactly in this situation! Given a set of financial assets on a market the underlying question is whether we are able to price any new financial asset which might be introduced in the market, or equivalently whether we can replicate the cash-flow of the new asset by means of a portfolio of our original assets. If this is the case and we can replicate every new asset, the market is called complete.  

In our financial market situation the question can be restated mathematically in terms of Euclidean geometry: do the vectors $S_{i}(T)$ span the whole $\mathbb{R}^{N}$ ? This leads to:  

Theorem 1.4.2. Suppose there are no arbitrage opportunities. Then the model is complete if and only if the matrix equation  

$$
\vec{S}^{\prime}\varphi=\delta
$$  

has a solution $\varphi\in\ensuremath{\mathbb{R}}^{d+1}$ for any vector $\delta\in\mathbb{R}^{N}$  

Linear algebra immediately tells us that the above theorem means that the number of independent vectors in $\vec{S^{\prime}}$ must equal the number of states in $\Omega$ . In an informal way we can say that if the financial market model contains 2 ( $N$ ) states of the world at time $T$ it allows for 1 $(N-1)$ sources of randomness (if there is only one state we know the outcome). Likewise we can view the numeraire asset as risk-free and all other assets as risky. We can now restate the above characterisation of completeness in an informal (but intuitive) way as:  

A financial market model is complete if it contains at least as many independent risky assets as sources of randomness.  

The question of completeness can be expressed equivalently in probabilistic language (to be introduced in Chapter 3), as a question of representability of the relevant random variables or whether the $\sigma$ -algebra they generate is the full $\sigma$ -algebra.  

If a financial market model is complete, traditional economic theory shows that there exists a unique system of prices. If there exists only one system of prices, and every equivalent martingale measure gives rise to a price system, we can only have a unique equivalent martingale measure. (We will come back to this important question in Chapters 4 and 6).  

The (arbitrage-free) market is complete if and only if there exists a unique equivalent martingale measure.  

# Example (continued).  

We formalise the above example of a binary single-period model. We have $d+1=2$ assets and $|\Omega|=2$ states of the world $\Omega=\{\omega_{1},\omega_{2}\}$ . Keeping the interest rate $r=0$ we obtain the following vectors (and matrices):  

$$
S(0)=\left[\begin{array}{c}{S_{0}(0)}\ {S_{1}(0)}\end{array}\right]=\left[\begin{array}{c}{1}\ {150}\end{array}\right],S_{0}(T)=\left[\begin{array}{c}{1}\ {1}\end{array}\right],S_{1}(T)=\left[\begin{array}{c}{180}\ {90}\end{array}\right],\vec{S}=\left[\begin{array}{c c}{1}&{1}\ {180}&{90}\end{array}\right].
$$  

We try to solve (1.4) for state prices, i.e. we try to find a vector $\psi=(\psi_{1},\psi_{2})^{\prime},\psi_{i}>0,i=1,2$ such that  

$$
{\left[\begin{array}{l}{1}\ {150}\end{array}\right]}={\left[\begin{array}{l l}{1}&{1}\ {180}&{90}\end{array}\right]}\quad{\left[\begin{array}{l}{\psi_{1}}\ {\psi_{2}}\end{array}\right]}.
$$  

Now this has a solution  

$$
{\left[\begin{array}{l}{\psi_{1}}\ {\psi_{2}}\end{array}\right]}={\left[\begin{array}{l}{2/3}\ {1/3}\end{array}\right]},
$$  

hence showing that there are no arbitrage opportunities in our market model. Furthermore, since $\psi_{1}+\psi_{2}=1$ we see that we already have computed risk-neutral probabilities, and so we have found an equivalent martingale measure $\mathbb{Q}$ with  

$$
\pmb{Q}(\omega_{1})=\frac{2}{3},\pmb{Q}(\omega_{2})=\frac{1}{3}.
$$  

We now want to find out if the market is complete (or equivalently if there is a unique equivalent martingale measure). For that we introduce a new financial asset $\delta$ with random payments $\delta(T)=$ $(\delta(T,\omega_{1}),\delta(T,\omega_{2}))^{\prime}$ . For the market to be complete, each such. $\delta(T)$ must be in the linear span of. $S_{0}(T)$ and $S_{1}(T)$ . Now since $S_{0}(T)$ and $S_{1}(T)$ are linearly independent, their linear span is the. whole ${\cal R}^{2}(={\cal R}^{|\Omega|})$ and $\delta(T)$ is indeed in the linear span. Hence we can find a replicating portfolio by solving  

$$
\left[\begin{array}{c c}{\delta(T,\omega_{1})}\ {\delta(T,\omega_{2})}\end{array}\right]=\left[\begin{array}{c c}{1}&{180}\ {1}&{90}\end{array}\right]\left[\begin{array}{c c}{\varphi_{0}}\ {\varphi_{1}}\end{array}\right].
$$  

Let us consider the example of a European option above. There $\delta(T,\omega_{1})=30,\delta(T,\omega_{2})=0$ and the above becomes  

$$
{\left[\begin{array}{l}{30}\ {0}\end{array}\right]}={\left[\begin{array}{l l}{1}&{180}\ {1}&{90}\end{array}\right]}\quad{\left[\begin{array}{l}{\varphi_{0}}\ {\varphi_{1}}\end{array}\right]},
$$  

with solution $\varphi_{0}=-30$ and $\varphi_{1}={\textstyle\frac{1}{3}}$ , telling us to borrow 30 units and buy $\frac13$ stocks, which is exactly what we did to set up our portfolio above. Of course an alternative way of showing market completeness is to recognise that (1.4) above admits only one solution for risk-neutral probabilities, showing the uniqueness of the martingale measure.  

# Example. Change of numeraire.  

We choose a situation similar to the above example, i.e. we have $d+1=2$ assets and $|\Omega|=2$ states of the world. $\Omega=\{\omega_{1},\omega_{2}\}$ . But now we assume two risky assets (and no bond) as the financial instruments at our disposal. The price vectors are given by  

$$
S(0)={\left[\begin{array}{l}{S_{0}(0)}\ {S_{1}(0)}\end{array}\right]}={\left[\begin{array}{l}{1}\ {1}\end{array}\right]},S_{0}(T)={\left[\begin{array}{l}{3/4}\ {5/4}\end{array}\right]},S_{1}(T)={\left[\begin{array}{l}{1/2}\ {2}\end{array}\right]},{\vec{S}}={\left[\begin{array}{l l}{3/4}&{5/4}\ {1/2}&{2}\end{array}\right]}.
$$  

We solve (1.4) and get state prices  

$$
{\left[\begin{array}{l}{\psi_{1}}\ {\psi_{2}}\end{array}\right]}={\left[\begin{array}{l}{6/7}\ {2/7}\end{array}\right]},
$$  

showing that there are no arbitrage opportunities in our market model. So we find an equivalent martingale measure $\mathbb{Q}$ with  

$$
\pmb{Q}(\omega_{1})=\frac{3}{4},\pmb{Q}(\omega_{2})=\frac{1}{4}.
$$  

Since we don't have a risk-free asset in our model, this normalisation (this numeraire) is very artificial, and we shall use one of the modelled assets as a numeraire, say. $S_{0}$ . Under this normalisation, we have the following asset prices (in terms of. $S_{0}(t,\omega)$ !):  

$$
\begin{array}{r l}&{\tilde{S}(0)=\left[\begin{array}{l}{\tilde{S}_{0}(0)}\ {\tilde{S}_{1}(0)}\end{array}\right]=\left[\begin{array}{l}{S_{0}(0)/S_{0}(0)}\ {S_{1}(0)/S_{0}(0)}\end{array}\right]=\left[\begin{array}{l}{1}\ {1}\end{array}\right],}\ &{\tilde{S}_{0}(T)=\left[\begin{array}{l}{S_{0}(T,\omega_{1})/S_{0}(T,\omega_{1})}\ {S_{0}(T,\omega_{2})/S_{0}(T,\omega_{2})}\end{array}\right]=\left[\begin{array}{l}{1}\ {1}\end{array}\right],}\ &{\tilde{S}_{1}(T)=\left[\begin{array}{l}{S_{1}(T,\omega_{1})/S_{0}(T,\omega_{1})}\ {S_{1}(T,\omega_{2})/S_{0}(T,\omega_{2})}\end{array}\right]=\left[\begin{array}{l}{2/3}\ {8/5}\end{array}\right].}\end{array}
$$  

Since the model is arbitrage-free (recall that a change of numeraire doesn't affect the no-arbitrage property), we are able to find risk-neutrl probabilities $\tilde{q}_{1}=\frac{9}{14}$ and $\begin{array}{r}{\tilde{q}_{2}=\frac{5}{14}}\end{array}$  

We now compute the prices for a call option to exchange $S_{0}$ for $S_{1}$ . Define $Z(T)=\operatorname*{max}\{S_{1}(T)-$ $S_{0}(T),0\}$ and the cash flow is given by  

$$
{\left[\begin{array}{l}{Z(T,\omega_{1})}\ {Z(T,\omega_{2})}\end{array}\right]}={\left[\begin{array}{l}{~0}\ {3/4}\end{array}\right]}.
$$  

option as There are no difficulties in finding the hedge portfolio $\begin{array}{r}{Z_{0}=\frac{3}{14}}\end{array}$ $\varphi_{0}=-{\frac{3}{7}}$ and $\varphi_{1}=\frac{\mathfrak{g}}{14}$ and pricing the  

We want to point out the following observation. Using $S_{0}$ as numeraire we naturally write  

$$
\frac{Z(T,\omega)}{S_{0}(T,\omega)}=\operatorname*{max}\left\{\frac{S_{1}(T,\omega)}{S_{0}(T,\omega)}-1,0\right\}
$$  

and see that this seemingly complicated option is (by use of the appropriate numeraire) equivalent to  

$$
\tilde{Z}(T,\omega)=\operatorname*{max}\Big\{\tilde{S}_{1}(T,\omega)-1,0\Big\},
$$  

a European call on the asset ${\tilde{S}}_{1}$  

# 1.4.3 A few financial-economic considerations  

The underlying principle for modelling economic behaviour of investors (or economic agents in general) is the maximisation of expected utility, that is one assumes that agents have a utility function $U(.)$ and base economic decisions on expected utility considerations. For instance, as-. suming a one-period model, an economic agent might have a utility function over current( $t=0$ and future ( $t=T$ ) values of consumption  

$$
U(c_{0},c_{T})=u(c_{0})+B(\beta u(c_{T})),
$$  

where $c_{t}$ is consumption at time $t$  

$u(.)$ is a standard utility function expressing  

non-satiation - investors prefer more to less; $u$ is increasing;   
risk aversion - investors reject an actuarially fair gamble; $u$ is concave;   
and (maybe) decreasing absolute risk aversion and constant relative risk aversion.  

Typical examples are power utility $u(x)=(x^{\gamma}-1)/\gamma$ , log utility $u(x)=\log(x)$ or quadratic utility $u(x)=x^{2}+d x$ (for which only the first two properties are true.)  

Assume such an investor is offered at $t=0$ at a price $p$ a random payoff $X$ at $t=T$ . How much will she buy? Denote with $\xi$ the amount of the asset she chooses to buy and with $e_{\tau},\tau=0,T$ her original consumption. Thus, her problem is  

$$
\operatorname*{max}_{\xi}\left[u(c_{0})+I E[\beta u(c_{T})]\right]
$$  

such that  

$$
c_{0}=e_{0}-p\xi\quad\mathrm{and}c_{T}=e_{T}+X\xi,
$$  

Substituting the constraints into the objective function and differentiating with respect to $\xi$ , we get the first-order condition.  

$$
p u^{\prime}(c_{0})=I E\left[\beta u^{\prime}(c_{T})X\right]\quad\Leftrightarrow\quad p=I E\left[\beta\frac{u^{\prime}(c_{T})}{u^{\prime}(c_{0})}X\right].
$$  

The investor buys or sells more of the asset until this first-order condition is satisfied.  

If we use the stochastic discount factor  

$$
m=\beta\frac{u^{\prime}(c_{T})}{u^{\prime}(c_{0})},
$$  

we obtain the central equation  

$$
p=l E(m X).
$$  

We can use (under regularity conditions) the random variable $m$ to perform a change of measure,. i.e. define a probability measure. $\mathit{\Pi}\mathit{\perp}\mathit{\Psi}$ using  

$$
B P^{*}(A)=B E^{*}({\bf1}_{A})=B E(m{\bf1}_{A}).
$$  

We write (1.6) under measure $\mathit{\Pi}\mathit{\perp}\mathit{\Psi}$ and get  

$$
p=\textstyle\operatorname{\mathbb{E}}^{*}(X)
$$  

Returning to the initial pricing equation, we see that under $\b{\mathcal{N}}^{*}$ the investor has the utility function $u(x)=x$ . Such an investor is called risk-neutral, and consequently one often calls the corresponding measure a risk-neutral measure. An excellent discussion of these issues (and further much deeper results) are given in Cochrane (2001).  

# Chapter 2  

# Financial Market Theory  

# 2.1 Choice under Uncertainty  

In a complete financial market model prices of derivative securities can be obtained by arbitrage. arguments. In incomplete market situations, these financial instruments carry an intrinsic risk. which cannot be hedged away. Thus in order to price these instruments further assumptions on the investors, especially regarding their preferences towards the risks involved, are needed.  

# 2.1.1 Preferences and the Expected Utility Theorem  

Let $\mathcal{X}$ be some non-empty set. An element $x\in\mathcal{X}$ will be interpreted as a possible choice of an economic agent. If presented with two choices $x,y\in{\mathcal{X}}$ the agent might prefer one over the other. This can be formalized  

Definition 2.1.1. A binary relation $\succeq$ defined on. $\mathcal{X}\times\mathcal{X}$ is called a preference relation, if it is  

transitive: $x\succeq y,y\succeq z\Rightarrow x\succeq z$ complete: for all $x,y\in{\mathcal{X}}$ either $x\succeq y$ or $y\succeq x$  

If $x\succeq y$ and $y\succeq x$ we write $x\sim y$ (indifference relation). x is said to be strictly preferred to $y$ denoted by $x\succ y$ , if $x\succeq y$ and $y\not\subset x$  

Definition 2.1.2. A numerical representation of a preference order $\succeq$ is a function $U:{\mathcal{X}}\rightarrow{\mathcal{R}}$ such that  

$$
y\succeq x\Leftrightarrow U(y)\geq U(x).
$$  

In order to characterize existence of a numerical representation we need  

Definition 2.1.3. $L e t\succeq b e$ a preference relation on $\mathcal{X}$ . A subset $\mathcal{Z}$ of $\mathcal{X}$ is called order dense if for any pair $x,y\in{\mathcal{X}}$ such that $x\succ y$ there exists some. $z\in{\mathcal{Z}}$ such that $x\succeq z\succeq y$  

Theorem 2.1.1. For the existence of a numerical representation of a preference relation $\succeq i t$ is necessary and sufficient that $\mathcal{X}$ contains a countable order dense subset $\mathcal{Z}$ . In particular, any preference relation admits a numerical representation if $\mathcal{X}$ is countable.  

Suppose that each possible choice of our economic agent corresponds to a probability distribution on a sample space $(\Omega,{\mathcal{F}})$ .Thus the set. $\mathcal{X}$ can be identified with a subset $\mathcal{M}$ of the set $\mathcal{M}_{1}(\Omega,\mathcal{F})$ of all probability distributions on $(\Omega,{\mathcal{F}})$ .In the context of the theory of choice the elements of. $\mathcal{M}$ are sometimes called lotteries. We assume in the sequel that. $\mathcal{M}$ is convex. The aim in the following is to characterize the preference orders $\succeq$ that allow a numerical representation of the form.  

$$
\mu\succeq\nu\Leftrightarrow\intop_{\Omega}u(\omega)\mu(d\omega)\geq\intop_{\Omega}u(\omega)\nu(d\omega)
$$  

Definition 2.1.4. A numerical representation $U$ of a preference order $\succeq$ on $\mathcal{M}$ is called a von Neumann-Morgenstern representation if it is of form (2.2).  

Any von Neumann-Morgenstern representation of $U$ is affine on $\mathcal{M}$ in the sense that  

$$
U(\alpha\mu+(1-\alpha)\nu)=\alpha U(\mu)+(1-\alpha)U(\nu)
$$  

for all $\mu,\nu\in{\mathcal{M}}$ and $\alpha\in[0,1]$  

Affinity implies the tow following properties or axioms  

: Independence (substitution) (I): Let $\mu,\nu,\lambda\in{\mathcal{M}}$ and $\alpha\in(0,1]$ then  

$$
\begin{array}{r l}{\mu\succ\nu}&{{}\Rightarrow\alpha\mu+(1-\alpha)\lambda\succ\alpha\nu+(1-\alpha)\lambda}\end{array}
$$  

Archimedean (continuity) (A): If $\mu\succ\lambda\succ\nu\in\mathcal{M}$ then there exist $\alpha,\beta\in(0,1)$ such that  

$$
\alpha\mu+(1-\alpha)\nu\succ\lambda\succ\beta\mu+(1-\beta)\nu
$$  

Theorem 2.1.2. Suppose the preference relation $\succeq$ on $\mathcal{M}$ satisfies the axioms (A) and (I). Then there exists an affine numerical representation $U$ of $\succeq$ . Moreover, $U$ is unique up to positive affine transformations, i.e. any other affine numerical representation $\tilde{U}$ with these properties is of the form $\tilde{U}=a U+b$ for some $a>0$ and $b\in\mathcal{M}$  

In case of a discrete (finite) probability distribution existence of an affine numerical representation is equivalent to existence of a von Neumann-Morgenstern representation.  

In the general case one needs to introduce a further axiom, the so-called sure thing principle: For $\mu,\nu\in{\mathcal{M}}$ and $A\in{\mathcal{F}}$ such that $\mu(A)=1$  

and  

$$
{\begin{array}{r l}{\delta_{x}\succ\nu{\mathrm{~for~all~}}x\in A\to\mu\succ\nu}\ {}\ {\nu\succ\delta_{x}{\mathrm{~for~all~}}x\in A\to\nu\succ\mu.}\end{array}}
$$  

From now on we will work within the framework of the expected utility representation.  

# 2.1.2 Risk Aversion  

We focus now on individual financial assets under the assumption that their payoff distributions. at a fixed time are known. We can view these asset distributions as probability distributions on some interval $S\subseteq{\mathcal{R}}$ . Thus we take. $\mathcal{M}$ as a fixed set of Borel probability measures on. $S$ . We also assume that $\mathcal{M}$ is convex and contains all point masses. $\delta_{x}$ for $x\in S$ . Also, we assume that each $\mu\in\mathcal M$ has a well defined expectation  

$$
m(\mu)=\int x\mu(d x)\in I R.
$$  

For assets with random payoff $\mu$ resp. insurance contracts with random damage $m(\mu)$ is often called fair price resp. fair premium. However, actual prices resp. premia will typically be different due to risk premia, which can be explained within our conceptual framework. We assume in the sequel that preference relations have a von Neumann-Morgenstern representation.  

Definition 2.1.5. A preference relation $\succ$ on $\mathcal{M}$ is called monotone if  

$$
x>y i m p l i e s\delta_{x}\succ\delta_{y}.
$$  

The preference relation is called risk averse if for $\mu\in\mathcal{M}$  

$$
\delta_{m(\mu)}\succ\mu\quad u n l e s s\quad\mu=\delta_{m(\mu)}.
$$  

Remark 2.1.1. An economic agent is called risk-averse if his preference relation is risk averse A risk-averse economic agent is unwilling to accept or indifferent to every actuarially fair gamble. An economic agent is strictly risk averse if he is unwilling to accept every actuarially fair gamble.  

Proposition 2.1.1. A preference relation a is  

(i) monotone, iff u is strictly increasing (ii) risk averse, iff $u$ is concave.  

Proof.(i) Monotonicity is equivalent to  

$$
u(x)=\int u(s)\delta_{x}(d s)=U(\delta_{x})>U(\delta_{y})=u(y)
$$  

for x > y.  

(ii) For $\mu=\alpha\delta_{x}+(1-\alpha)\delta_{y}$ we have  

$$
m(\mu)=\int s(\alpha\delta_{x}+(1-\alpha)\delta_{y})(d s)=\alpha x+(1-\alpha)y.
$$  

So if $\succ$ is risk-averse, then  

$$
\delta_{\alpha x+(1-\alpha)y}\succ\alpha\delta_{x}+(1-\alpha)\delta_{y}
$$  

holds for all distinct $x,y\in S$ and $\alpha\in(0,1)$ . Hence  

$$
u(\alpha x+(1-\alpha)y)>\alpha u(x)+(1-\alpha)u(y),
$$  

$u$ is strictly concave. Conversely, if $u$ is strictly concave, then Jensen's inequality implies risk aversion, since  

$$
U(\delta_{m(\mu)})=u\left(\int x\mu(d x)\right)\geq i n t u(x)\mu(d x)=U(\mu)
$$  

with equality iff $\mu=\delta_{m(\mu)}$  

Definition 2.1.6. A function $u:S\rightarrow\underline{{{R}}}$ is called utility function if it is strictly concave, strictly increasing and continuous on $S$  

By the intermediate value theorem there is for any $\mu\in\mathcal M$ a unique number $c(\mu)$ such that  

$$
u(c(\mu))=U(\mu)=\int u d\mu.
$$  

So $\delta_{c(\mu)}\sim\mu$ , i.e. there is indifference between $\mu$ and the sure amount. $c(\mu)$  

Definition 2.1.7. The certainty equivalent of $\mu$ , denoted by $c(\mu)$ is the number defined in (2.4). It is the amount of money for which the individual is indifferent between the lottery $\mu$ and the certain amount $c(\mu)$ The number  

$$
\rho(\mu)=m(\mu)-c(\mu)
$$  

is called the risk premium.  

The certainty equivalent can be viewed as the upper price an investor would pay for the asset distribution $\mu$ . Thus the fair price must be reduced by the risk premium if one wants an agent to buy the asset.  

Consider now an investor who has the choice to invest a fraction of his wealth in a riskfree and. the remaining fraction of his wealth in a risky asset. We want to find conditions on the distribution of the risky asset and the preferences (utility function) of the investor in order to determine his. willingness for a risky investment. Formally, we consider the following optimisation problem.  

$$
f(\lambda)=U(\mu_{\lambda})=\int u d\mu_{\lambda}\to\operatorname*{max},
$$  

where $\mu_{\lambda}$ is the distribution of  

$$
X_{\lambda}=(1-\lambda)X+\lambda c
$$  

with $X$ an integrable random variable with non-degenerate distribution $\mu$ and $c\in S$ is a certain amount.  

Proposition 2.1.2. We have $\lambda^{*}=1$ if $\b{\mathcal{L}}(\b{X})\leq c$ and $\lambda^{*}>0$ if $c\geq c(\mu)$  

Proof. By Jensen's inequality  

$$
f(\lambda)\leq u\left({\cal E}\left[X_{\lambda}\right]\right)=u\left((1-\lambda){\cal E}(X)+\lambda c\right)
$$  

with equality iff $\lambda=1$ .It follows that $\lambda^{*}=1$ if the right-hand side is increasing in $\lambda$ , i.e. $\b{\mathcal{L}}(X)\leq c$  

Now, strict concavity of $u$ implies  

$$
f(\lambda)\geq E\left(1-\lambda\right)u(X)+\lambda u(c))=(1-\lambda)u(c(\mu))+\lambda u(c)
$$  

with equality iff. $\lambda\in\{0,1\}$ . The right-hand side is increasing in $\lambda$ if $c\geq c(\mu)$ , and this implies.   
$\lambda^{*}>0$ . Remark 2.1.2. (i) (Demand for a risky asset.) The price of a risky asset must be below the expected discounted payoff in order to attract any risk-averse investor.   
(ii) (Demand for insurance.) Risk aversion can create a demand for insurance even if the insurance premium lies above the fair price.   
(iii) If $u\in C^{1}(\mathcal{R})$ then  

$$
\begin{array}{r l r}{\lambda^{*}=1}&{{}\Leftrightarrow}&{{\cal{L}}(X)\in\cal{c}}\ {\lambda^{*}=0}&{{}\Leftrightarrow}&{\stackrel{}{\cal{c}}\leq\frac{{\cal{L}}(X u^{\prime}(X))}{{\cal{L}}(U^{\prime}(X))}.}\end{array}
$$  

We assume now that. $\mu$ has a finite variance. $W a r(\mu)$ . We consider the Taylor expansion of a sufficiently smooth utility function $u(x)$ at $x=c(\mu)$ around $m=m(\mu)$ . We have  

$$
u(c(\mu))\approx u(m)+u^{\prime}(m)\left(c(\mu)-m\right)=u(m)+u^{\prime}(m)\rho(m).
$$  

On the other hand,  

$$
\begin{array}{r c l}{{u(c(\mu))}}&{{=}}&{{\displaystyle\int u(x)\mu(d x)+\int\left[u(m)+u^{\prime}(m)\left(c(\mu)-m\right)+\frac{1}{2}u^{\prime\prime}(m)\left(c(\mu)-m\right)^{2}+r(x)\right]\mu(d x)}}\ {{}}&{{}}&{{}}\ {{}}&{{\approx}}&{{\displaystyle u(m)+\frac{1}{2}u^{\prime\prime}(m)\boldsymbol{W}a r(\mu)}}\end{array}
$$  

(where $r(x)$ denotes the remainder term in the Taylor expansion). So  

$$
\rho(\mu)\approx-\frac{u^{\prime\prime}(m)}{2u^{\prime}(m)}\mathbb{{W}}a r(\mu)=\frac{1}{2}\alpha(m)\mathbb{{W}}a r(\mu).
$$  

Thus $\alpha(m(\mu))$ is the factor by which an economic agent with utility function $u$ weighs the risk (measured by $\mathbb{V}a r(\mu),$ in order to determine the risk premium..  

Definition 2.1.8. Suppose that u is a twice continuously differentiable utility function on $S$ .Then  

$$
\alpha(x)=-\frac{u^{\prime\prime}(x)}{u^{\prime}(x)}
$$  

is called the Arrow-Pratt coefficient of absolute risk aversion of u at level $x$  

Example 2.1.1. (i) Constant absolute risk aversion (CARA). Here $\alpha(x)\equiv\alpha$ for some constant. This implies a (normalized) utility function  

$$
u(x)=1-e^{-\alpha x}.
$$  

(ii) Hyperbolic absolute risk aversion (HARA). Here $\alpha(x)=(1-\gamma)/x$ for some $\gamma\in[0,1)$ .This implies  

$$
\begin{array}{r c l l r}{{u(x)}}&{{=}}&{{\log x}}&{{f o r}}&{{\gamma=0}}\ {{}}&{{}}&{{}}&{{}}\ {{u(x)}}&{{=}}&{{x^{\gamma}/\gamma}}&{{f o r}}&{{0<\gamma<1.}}\end{array}
$$  

Remark 2.1.3. For $u$ and $\bar{u}$ two utility functions on $S$ with $\alpha$ and $\tilde{\alpha}$ the corresponding ArrowPratt coefficients we have  

$$
\alpha(x)\geq{\tilde{\alpha}}(x)\forall x\in S\Leftrightarrow\rho(\mu)\geq{\tilde{\rho}}(\mu)
$$  

with $\rho,\tilde{\rho}$ the corresponding risk premia.  

It is also useful to analyse risk aversion in terms of the proportion of wealth that is invested in a risky asset.  

Definition 2.1.9. Suppose that $u$ is a twice continuously differentiable utility function on $S$ . Then  

$$
\alpha_{R}(x)=\alpha(x)x=-x\frac{u^{\prime\prime}(x)}{u^{\prime}(x)}
$$  

is called the Arrow-Pratt coefficient of relative risk aversion of u at level $x$  

Remark 2.1.4. (i) An individuals utility function displays decreasing (constant, increasing) absolute risk aversion if $\alpha(x)$ is decreasing (constant, increasing). (ii) An individuals utility function displays decreasing (constant, increasing) relative risk aversion if $\alpha_{R}(x)$ is decreasing (constant, increasing)..  

# 2.1.3 Further measures of risk  

In this section we focus on the question whether one (risky asset) distribution is preferred to another, regardless of the choice of a particular utility function. Assume $S=\mathcal{R}$ and $\mathcal{M}=c M_{1}$ (expectation exists).  

Definition 2.1.10. Let $\mu,\nu$ be elements of. $\mathcal{M}$ .We say that. $\mu$ is uniformly preferred over $\nu$ notation $\mu\succ_{u n i}\nu$ if for all utility functions $u$  

$$
\int u d\mu\geq\int u d\nu.
$$  

$\succ_{u n i}$ is also called second order stochastic dominance.  

Theorem 2.1.3. For any pair. $\mu,\nu\in{\mathcal{M}}$ the following conditions are equivalent:  

(i) $u\succ_{u n i}\nu$  

(ii) $\textstyle\int f d\mu\geq\int f d\nu$ for all increasing concave functions $f$  

(iii) For all $c\in\mathcal{R}$ we have  

$$
\int(c-x)^{+}\mu(d x)\leq\int(c-x)^{+}\nu(d x).
$$  

(iv) If $F$ and $G$ denote the respective distribution functions of $\mu$ and $\nu$ , then  

$$
\int_{-\infty}^{c}F(x)d x\leq\int_{-\infty}^{c}G(x)d x\forall c\in I R.
$$  

Proof. Recall $u$ is a utility function iff it is strictly concave and strictly increasing.  

$(\mathbf{a})\Rightarrow(\mathbf{b})((b)\Rightarrow(a)$ is clear). Choose any utility function $u_{0}$ with $\int u_{0}d\mu$ and $\int u_{0}d\nu$ finite. For instance,  

$$
u_{0}(x)=\left\{\begin{array}{l l l}{x-e^{x/2}+1}&{\mathrm{if}}&{x\leq0}\ {\sqrt{x+1}-1}&{\mathrm{if}}&{x\geq0}\end{array}\right.
$$  

Then for $f$ concave and increasing and for $\alpha\in[0,1)$  

$$
u_{\alpha}(x)=\alpha f(x)+(1-\alpha)u_{0}(x)
$$  

is a utility function. Hence  

$$
\int f d\mu=\operatorname*{lim}_{\alpha\uparrow1}\int u_{\alpha}d\mu\geq\operatorname*{lim}_{\alpha\uparrow1}\int u_{\alpha}d\nu=\int f d\nu
$$  

$(\mathbf{b})\Leftrightarrow(\mathbf{c})$  

$\Rightarrow$ ": Follows, because. $f(x)=-(c-x)^{+}$ is concave and increasing.  

$^{,}$ : Let $f$ be an increasing concave function and $h=-f$ .Then $h$ is convex and decreasing   
and its increasing right-hand derivative $h:=h_{+}^{\prime}$ can be regarded as a distribution function of a   
non-negative (Radon) measure on $\mathbb{R}$ . Thus $\gamma$  

$$
h^{\prime}(b)=h^{\prime}(a)+\gamma([a,b])\mathrm{for}a<b.
$$  

For $x<b$ we find  

$$
h(x)=h(b)-h^{\prime}(b)(b-x)+\int_{[-\infty,b]}(z-x)^{+}\gamma(d z)\quad\mathrm{for}\quad x<b.
$$  

Using (c), the fact that, $h^{\prime}(b)\leq0$ and Fubini's theorem we obtain  

$$
\begin{array}{r l}&{\underset{(-\infty,b]}{\int}h d\mu}\ {=}&{h(b)(\mu(-\infty,b])-h^{\prime}(b)\int(b-x)^{+}\mu(d x)+\underset{(-\infty,b]}{\int}\int(z-x)^{+}\mu(d x)\gamma(d z)}\ {\leq}&{h(b)(\nu(-\infty,b])-h^{\prime}(b)\int(b-x)^{+}\nu(d x)+\underset{(-\infty,b]}{\int}\int(z-x)^{+}\nu(d x)\gamma(d z)}\ {=}&{\underset{(-\infty,b]}{\int}h d\nu.}\end{array}
$$  

Now letting $b\uparrow\infty$ yields $\textstyle\int f d\mu\geq\int f d\nu$  

$\mathbf{\Sigma}(\mathbf{c})\Leftrightarrow\mathbf{\Sigma}(\mathbf{d})$ . By Fubini's theorem  

$$
\begin{array}{r c l}{\overset{c}{\underset{-\infty}{\overset{c}{\int}}}F(y)d y}&{=}&{\overset{c}{\underset{-\infty}{\overset{c}{\int}}}\underset{(-\infty,y)}{\overset{f}{\int}}\mu(d z)d y}\ &&{=}&{\int\int\mathbf{1}(z\leq y\leq c)d y\mu(d z)}\ &&{=}&{\int(c-z)^{+}\mu(d z).}\end{array}
$$  

Remark 2.1.5.(i) Also: $\mu\geq_{u n i}\nu\Leftrightarrow\int_{0}^{\lambda}F^{-1}(y)d y\geq\int_{0}^{\lambda}G^{-1}(y)d y$ for all $\lambda\in(0,1]$ , where $F^{-1},G^{-1}$ are the inverses, or quartile functions of the distribution.  

(ii) Taking $f(x)=x$ in $(b)$ , we see $\mu\geq_{u n i}\nu\Rightarrow m(\mu)\geq m(\nu)$  

(iii) For normal distributions, we have  

$$
{\mathcal{N}}(m,\sigma^{2})\geq_{u n i}{\mathcal{N}}
$$  

iff $m\geq{\tilde{m}}$ and $\sigma^{2}\le\tilde{\sigma}^{2}$  

If $\mu,\nu\subset{\mathcal{M}}$ such that $m(\mu)=m(\nu)$ and $\mu\geq_{u n i}\nu$ then $v a r(\mu)\leq v a r(\nu)$ . Here  

$$
v a r(\mu)=\int(x-m(\mu))\mu(d x)=\int x^{2}\mu(d x)-m(\mu)^{2}
$$  

is the variance of $\mu$ (use condition) $(b)$ with $f(x)=-x^{2}$ ) which holds under $m(\nu)=m(\nu)$ for all concave functions.  

In the financial context, comparison of portfolios with known payoff distributions often use a mean-variance approach with  

$$
\mu\geq\nu\Leftrightarrow m(\nu)\geq m(\nu)\quad\mathrm{and}\quad v a r(\mu)\leq v a r(\nu).
$$  

For normal distributions $\mu\geq\nu$ is equivalent to. $\mu\geq_{u n i}\nu$ , but not in general..  

Example 2.1.2. $\mu=U[-1,1],s o m(\mu)=0,v a r(\mu)={\textstyle{\frac{1}{2}}}\intop x^{2}d x={\textstyle{\frac{1}{3}}}\left({\textstyle{\frac{x^{3}}{3}}}|_{-1}^{1}\right)={\textstyle{\frac{1}{3}}}$ for $\nu=$ $p\delta_{-1/2}+(1-p)\delta_{2}$ , with $\textstyle p={\frac{4}{5}}$ we have  

$$
m(\nu)={\frac{4}{5}}\left(-{\frac{1}{2}}\right)+{\frac{1}{5}}\cdot2=0,\quad v a r(\nu)={\frac{4}{5}}\cdot{\frac{1}{4}}+{\frac{1}{5}}\cdot4=1
$$  

Thus $v a r(\nu)>v a r(\mu)$ , but  

$$
\begin{array}{r l}&{\int(-\frac{1}{2}-x)^{+}\mu(d x)=\frac{1}{2}\underset{-1}{\overset{-1/2}{\int}}(-\frac{1}{2}-x)d x=\frac{1}{2}\big(-\frac{1}{2}x-\frac{1}{2}x\big)\big|_{-1}^{-1/2}}\ {=}&{\frac{1}{2}\left(\frac{1}{4}-\frac{1}{8}-\frac{1}{2}+\frac{1}{2}\right)=1/16}\end{array}
$$  

and  

$$
\int\left(-{\frac{1}{2}}-x\right)^{+}\nu(d x)=0.
$$  

So $\mu\geq_{u n i}\nu$ does not hold.  

A further important class of distributions is discussed in the following example.  

Example 2.1.3. A real-valued random variable $Y$ on some probability space. $(\Omega,{\mathcal{F}},I P)$ is called log-normally distributed with parameters $\alpha\in\mathbb R$ and $\sigma\in\mathbb{R}_{+}$ if it can be written as.  

$$
Y=\exp(\alpha+\sigma X)
$$  

where $X$ has a standard normal law ${\mathcal{N}}(0,1)$ . For log-normal distributions  uni $\breve{\mu}\leftrightarrow\sigma^{2}\leq\tilde{\sigma}^{2}$ and $\begin{array}{r}{\alpha+\frac{1}{2}\sigma^{2}\geq\tilde{\alpha}+\frac{1}{2}\tilde{\sigma}^{2}}\end{array}$  

Definition 2.1.11. Let $\mu$ and $\nu$ be two arbitrary probability measures on $\mathbb{R}$ .We say that $\mu$ stochastically dominates $\nu$ , notation $\mu\geq_{m o n}\nu$ if  

$$
\int f d\mu\geq\int f d\nu
$$  

for all bounded increasing functions. $f\in C(\mathbb{R})$ .Stochastic dominance is also called first-order stochastic dominance.  

Theorem 2.1.4. For. $\mu,v\in\mathcal{M}_{1}(\mathbb{R})$ the following conditions are equivalent  

(a) $\mu\geq_{m o n}\nu$   
(b) for all $x,F(x)\leq G(x)$ where $F,G$ are respectively the distribution functions of $\mu,\nu$   
(c) there exists a probability space. $(\Omega,{\mathcal{F}},I P)$ with random variables $X$ and $Y$ having respective distributions $\mu$ and $\nu$ such that $X\ge Y\quad l l-a.s.$  

# 2.2 Optimal Portfolios  

# 2.2.1 The mean-variance approach  

Recall our one-period model with securities. $S_{0},S_{1},\ldots,S_{d}$ and security prices. $S_{i}(T)$ at the final. time $t=T$ . Here $S_{0}$ is the risk-free bond and. $S_{1},\ldots,S_{d}$ are random variables on some prob. space $(\Omega,{\mathcal{F}},I P)$ . For the purpose of this section we disregard the risk free asset and invest only in the risky assets. We consider their returns.  

$$
R_{i}(T)=\frac{S_{i}(T)}{S_{i}(0)}\quad i=1,\dots,d
$$  

and assume we know (or have estimated) their means and covariance matrix  

$$
E(R_{i}(T))=m_{i}\quad i=1,\dots,d
$$  

and  

$$
\begin{array}{r}{C o v(R_{i}(T),R_{j}(T))=\sigma_{i j}\quad i,j=1,\dots,d}\end{array}
$$  

(Observe that $\Sigma=(\sigma_{i j})$ is positive semi-definite).  

We consider portfolio vectors $\varphi_{i}\in\mathbb{R}^{d}$ with $\varphi_{i}\geq0$ (in order to avoid the possibility of negative final wealth).  

Definition 2.2.1. An investor with initial wealth $x>0$ is assumed to hold. $\varphi_{i}\geq0$ shares of security $i,i=1,\ldots,d$ with  

$$
\sum_{i=1}^{d}\varphi_{1}S_{i}(0)=x\quad"b u d g e t e q u a t i o n".
$$  

Then the portfolio vector $\pi=(\pi_{1},\ldots,\pi_{d})$ is defined as  

$$
\pi_{i}=\frac{\varphi_{i}\cdot S_{i}(0)}{x}\quad i=1,\ldots,d
$$  

and  

$$
R^{\pi}=\sum_{i=1}^{d}\pi_{i}R_{i}(T)
$$  

is called the corresponding portfolio return.  

Remark 2.2.1. (1) The components of the portfolio vector represent the fractions of total wealth invested in the corresponding securities. In particular, we have  

$$
\sum_{i=1}^{d}\pi_{i}=\frac{1}{x}\sum_{i=1}^{d}\varphi_{i}S_{i}(0)=\frac{x}{x}=1
$$  

(2) Let $V^{\pi}(T)$ denote the final wealth corresponding to an initial wealth of $x$ and a portfolio vector $\varphi$ , i. e.  

$$
V^{\pi}(T)=\sum_{i=1}^{d}\varphi_{i}S_{i}(T)
$$  

then we find  

$$
R^{\pi}=\sum_{i=1}^{d}\pi_{i}R_{i}(T)=\sum_{i=1}^{d}\frac{\varphi_{i}S_{i}(0)}{x}\cdot\frac{S_{i}(T)}{S_{i}(0)}=\frac{V^{\pi}(T)}{x}
$$  

(3) The mean and the variance of the portfolio return are given by  

$$
\displaystyle{E(R^{\pi})=\sum_{i=1}^{d}\pi_{i}m_{i},\quad\displaystyle{\mathbb{V}}a r(R^{\pi})=\sum_{i=1}^{d}\sum_{j=1}^{d}\pi_{i}\sigma_{i j}\pi_{j}}
$$  

We now need to consider criteria for selecting a portfolio. The basic (by now classical) idea. of Markowitz was to look for a balance between risk (i.e. portfolio variance) and return (i.e. portfolio mean). He considered the problem of requiring a lower bound for the portfolio return (minimum return) and then choosing from the corresponding set the portfolio vector with the minimal variance. Alternatively, set an upper bound for the variance and determine the portfolio. vector with the highest possible mean return. We consider.  

Definition 2.2.2. A portfolio is a frontier portfolio if it has the minimum variance among port-. folios that have the same expected rate of return. The set of all frontier portfolios is called the portfolio frontier.  

We now discuss briefly the assumptions of the mean-variance approach.  

(1) A preference for expected return and an aversion to variance is implied by monotonicity and strict concavity of a utility function. However, for arbitrary utility functions, expected. utility cannot be defined over just the expected return and variances. For. $\mu\in\mathcal M$ assume  

$$
\begin{array}{l c l}{{U(\mu)}}&{{=}}&{{\int u(x)\mu(d x)=}}\ {{}}&{{}}&{{}}\ {{}}&{{=}}&{{u(m)+\frac{1}{2}u^{\prime\prime}(m)W a r(\mu)+R_{3}(\mu)}}\end{array}(x-m)^{k}\mu(d x)
$$  

(i.e. convergence of Taylor series and interchangeability of integral). Thus, the remainder term needs (for the general case) to be considered as well.  

(2) Assuming quadratic utility, i.e.  

$$
u(x)=x-\frac{b}{2}x^{2}\quad,b>0
$$  

we find  

$$
U(\mu)=m-\frac b2m_{2}=m-\frac b2({\cal{W}}a r(\mu)+m^{2}).
$$  

Unfortunately, quadratic utility displays satiation (negative utility for increasing wealth) and increasing absolute risk aversion.  

(3) For $\mu_{i}$ normal distributions, $R^{\pi}\sim{\mathcal N}$ , thus preferences can be expressed solely from mean and variance.  

Proposition 2.2.1. $A$ portfolio $p$ is a frontier portfolio if and only if the portfolio weight vector $\pi^{p}$ is a solution to the optimisation problem.  

$$
\operatorname*{min}_{\pi}\frac{1}{2}\pi^{\prime}\Sigma\pi=\operatorname*{min}_{\pi}\frac{1}{2}\sum_{i}\sum_{j}\pi_{i}\pi_{j}\sigma_{i j}^{2}\quad(=2{\cal V}a r(R^{\pi}))
$$  

subject to  

$$
\begin{array}{l c l}{{\pi^{\prime}\mu=\displaystyle\sum_{i}\pi_{i}\mu_{i}}}&{{=}}&{{{\displaystyle I E(R^{\pi}):=m_{p}}}}\ {{\pi^{\prime}{\bf1}=\displaystyle\sum_{i}\pi_{i}}}&{{=}}&{{{\displaystyle1.}}}\end{array}
$$  

1 is an $N$ -vector of ones, $\pmb{m}=(m_{1},\dots,m_{d})$ is the vector of expected returns of the assets and $m_{p}$ is a fixed rate of portfolio-return.  

We can solve (2.13) and write the solution as  

$$
\pmb{\pi}_{p}=\pmb{g}+\pmb{h}m_{p}
$$  

with  

$$
\begin{array}{r c l}{{g}}&{{=}}&{{\displaystyle\frac{1}{D}\left[B(\Sigma^{-1}{\bf1})-A(\Sigma^{-1}m)\right]}}\ {{}}&{{}}&{{}}\ {{h}}&{{=}}&{{\displaystyle\frac{1}{D}\left[C(\Sigma^{-1}m)-A(\Sigma^{-1}{\bf1})\right]}}\end{array}
$$  

where A = 1T $\Sigma^{-1}m=m^{\prime}\Sigma^{-1}{\bf1},B=m^{T}\Sigma^{-1}m,C={\bf1^{\prime}}\Sigma^{-1}{\bf1}$ and $D=B C-A^{2}>0$  

For $m_{p}=0$ we find from (2.14) that the optimal portfolio is $g$ . Also, for $m_{p}=1$ (2.14) implies that the optimal portfolio is. $g+h$ . Now for any given expected return $m_{q}$ we find  

$$
\pi^{q}=g+h m_{q}=(1-m_{q})g+m_{q}(g+h).
$$  

This generalizes to  

Proposition 2.2.2 (Two-fund separation). The portfolio frontier can be generated by any two distinct frontier portfolios.  

The covariance between the rates of return of any frontier portfolios $p$ and $q$ is  

$$
{\cal C}o v\left(R^{p},R^{q}\right)={\frac{\cal C}{\cal D}}\left(m_{p}-{\frac{\cal A}{\cal C}}\right)\left(m_{q}-{\frac{\cal A}{\cal C}}\right)+{\frac{1}{\cal C}}.
$$  

Thus, for the variances  

$$
\frac{\sigma^{2}(R^{p})}{1/C}-\frac{(m_{p}-A/C)^{2}}{D/C^{2}}=1,
$$  

which is a hyperbola in the standard-deviation - expected return $(\sigma-\mu)$ space.  

(i) The portfolio having the minimum variance of all feasible portfolios is called minimum variance portfolio and denoted as mvp.   
(ii) A frontier portfolio is efficient if it has a strictly higher expected return than the mvp.   
(iii) Frontier portfolios that are neither mvp nor efficient are called inefficient.   
(iv) The efficient frontier is the part of the curve lying above the point of global minimum of standard deviation.  

We can use (2.15) to show that for any frontier portfolio $p$ (except the mvp) there exists a. unique frontier portfolio. $z c(p)$ which has zero covariance with. $p$  

Proposition 2.2.3. If $\pi$ is any envelope portfolio, then for any other portfolio (envelope or not) $\tilde{\pi}$ we have the relation.  

$$
m_{\pi}=c+\beta_{\pi}(m_{\tilde{\pi}}-c)
$$  

where  

$$
\beta_{\pi}=\frac{{\mathbb C}o v(\pi,\tilde{\pi})}{\sigma_{\tilde{\pi}}^{2}}.
$$  

Furthermore, c is the expected return of a portfolio $\pi^{*}$ whose covariance with $\tilde{\pi}$ is zero.  

Existence of a risk-free asset has the effect of making the efficient frontier a straight line extending from the rate to the point where the line is tangential to the original efficient frontier for the risky assets. This leads to the one-fund theorem: There is a single fund (portfolio) such that any efficient portfolio can be constructed as a combination of the fund and the risk-free asset.  

The implication of Proposition 2.2.3 in the presence of the a risk-free asset is that there exists a linear relationship between any security and portfolios on the efficient frontiers involving so-called. 'beta factors'.  

$$
m_{i}-r=\beta_{i,p}(m_{p}-r),
$$  

where $\beta_{i,p}$ is a linear factor defined as  

$$
\beta_{i,p}=\mathbb{C}o v(R_{i},R^{p})/\sigma_{p}^{2}.
$$  

This extends to any portfolio $q$ , i.e.  

$$
m_{q}-r=\beta_{q,p}(m_{p}-r),
$$  

with $\beta_{q,p}=\mathbb{C}o v(R^{q},R^{p})/\sigma_{p}^{2}$  

# 2.2.2 Capital asset pricing model  

We now consider a so-called Equilibrium Model. The focus of attention is turned from the individual investor to the aggregate market for securities (and all investors) as a whole. We need assumptions on the investors' behaviour and the market as a whole.  

. All investors have the same one-period horizon..   
. All investors can borrow or lend at the same risk-free rate..   
. The markets for risky assets are perfect. Information is freely and instantly available to all investors and no investor believes that they can affect the price of a security by their own action.   
Investors have the same estimates of the expected returns, standard deviations and covariances over the one-period horizon..   
All investors measure in the same numeraire..  

Under the assumptions of mean-variance theory we have in equilibrium  

1. If investors have homogeneous expectations, then they are all faced by the same efficient frontier of risky securities.   
2. If there is a risk-free asset the efficient frontier collapses for all investors to a straight line which passes through the risk-free rate of return on the $m$ axis and is tangential to the efficient frontier.  

All investors face the same efficient frontier because they have the same views on the available securities. Thus:  

1. All rational investors will hold a combination of the risk-free asset and the portfolio of assets where the straight line through the risk-free return touches the original efficient frontier.   
2. Because investors share the same efficient frontier they all hold the same diversified portfolio. Because this portfolio is held in different quantities by all investors it must consist of all risky assets in proportion to their market capitalization. It is commonly called the 'market portfolio' .   
3. Other strategies are non-optimal.  

The line denoting the efficient frontier is called the capital market line and its equation is  

$$
m_{p}-r=(m_{M}-r)\frac{\sigma_{p}}{\sigma_{M}}
$$  

where $m_{p}$ is the expected return of any portfolio p on the efficient frontier; $\sigma_{p}$ is the standard deviation of the return on portfolio p;. $m_{M}$ is the expected return on the market portfolio, $O u$ is the standard deviation of the market portfolio and. $r$ is the risk-free rate of return..  

Thus the expected return on any portfolio is a linear function of its standard deviation. The factor $\frac{m_{M}-r}{\sigma_{M}}$ is called the market price of risk.  

We can also develop an equation relating the expected return of any asset to the return of the market  

$$
m_{i}-r=(m_{M}-r)\beta_{i}
$$  

where $m_{i}$ is the expected return on security $i$ ; $\beta_{i}$ is the beta factor of security. $i$ ,defined as $\mathbb{C}o v(R_{i},R^{M})/\mathbb{V}a r(R^{M})$ $m_{M}$ is the expected return on the market portfolio and $r$ is the riskfree rate of return. Equation (2.19) is called the security market line. It shows that the expected return of any security (and portfolio) can be expressed as a linear function of the securities covariance with the market as a whole.  

# 2.2.3 Portfolio optimisation and the absence of arbitrage  

Consider the standard one-period model with assets. $(S_{0},\dots,S_{d}),S_{0}$ the risk-free bond with interest. rate $r>0$ . Denote by $\boldsymbol{\varphi}=\left(\varphi_{0},\ldots,\varphi_{d}\right)$ portfolio vectors specifying the amount of shares of the assets in the portfolio..  

We consider an investor with utility function $\tilde{u}$ . A rational choice of the investor's portfolio will be based on expected utility.  

$$
\it{I E}(\tilde{u}(\varphi^{\prime}S(T)))
$$  

of the payoff. $\varphi^{\prime}S(T)$ at time $T$ , where the portfolio. $\varphi$ satisfies the budget constraint  

$$
\varphi^{\prime}S(0)\leq\omega
$$  

with $\omega$ the initial of the investor. We consider the discounted net gain.  

$$
{\frac{\varphi^{\prime}S(T)}{1+r}}-\varphi^{\prime}S(0)=\varphi^{\prime}Y
$$  

with $Y=(Y_{0},Y_{1},...,Y_{d})$ and $\begin{array}{r}{Y_{i}=\frac{S_{i}(T)}{1+r}-S_{i}(0)}\end{array}$ . (Here $Y_{0}=0!$  

For any portfolio $\varphi$ with. $\varphi^{\prime}S(0)<\omega$ , adding the risk-free investment $\omega-\varphi^{\prime}S(0)$ would lead to. the strictly better portfolio $\left(\varphi_{0}+\omega-\varphi^{\prime}S(0),\varphi_{1},...,\varphi_{d}\right)$ . Thus we can focus on $\varphi$ with $\varphi^{\prime}S(0)=\omega$ Then the payoff is an affine function of the discounted net gain  

$$
\begin{array}{r}{\varphi^{\prime}S(T)=(1+r)(\varphi^{\prime}Y+\omega).}\end{array}
$$  

Since $Y_{0}=0$ we only need the focus on the risky assets. Define the following transformation of the original utility function. $\tilde{u}$  

$$
\begin{array}{r}{u(y)=\tilde{u}((1+r)(y+\omega)).}\end{array}
$$  

So the optimization problem is equivalent to maximizing the expected utility of  

$$
\mathit{I E}(u(\varphi^{\prime}Y))
$$  

among all $\varphi\in\ensuremath{\mathbb{R}^{d}}$ such that $\varphi^{\prime}Y$ is contained in the domain $D$ of $u$  

Assumption A1. Either  

(a) $D=\mathcal{R}$ , then we admit all $\varphi^{\prime}\in\mathcal{R}^{d}$ , but assume the $u$ is bounded from above (Example: $u(x)=1-e^{-\alpha x}$ or  

(b) $D=[a,\infty)$ for some $a<0$ . In this case we only consider portfolios with $\varphi^{\prime}Y\geq a$ and assume that the expected utility generated by such portfolios is finite, i.e.  

$$
E[u(\varphi^{\prime}Y)]<\infty\quad\mathrm{for~all}\quad\varphi\in I R^{d}\quad\mathrm{with}\quad\varphi^{\prime}Y\geq a.
$$  

(Example $\begin{array}{r}{u(x)=\frac{1}{\gamma}(x-c)^{\gamma},}\end{array}$  

Denote by  

$$
\mathcal{S}(D)=\{\varphi\in I R^{d}|\varphi^{\prime}Y\in D\}
$$  

the set of admissible portfolios for $D$ . Our aim now is to find a $\varphi^{*}\in S(D)$ which maximizes the expected utility $\mathit{I E}(u(\varphi^{\prime}Y))$ among $\varphi\in S(D)$  

Theorem 2.2.1. Let the above assumption A1 hold true. Then there exits a maximizer of the expected utility  

$$
E[n(\varphi^{\prime}Y)]\quad\varphi\in S(D)
$$  

if the only if the market model is arbitrage-free. Moreover, there exists at most one maximizer if the market model is complete.  

Proof. Uniqueness follows from the strict concavity of the function $\varphi\to L(u(\varphi^{\prime}Y))$ for complete market models.  

In case the model is incomplete we can find a complete submodel and apply the result to this submodel. So we may assume completeness. (Recall completeness is equivalent to $\begin{array}{r l}{\eta^{\prime}Y=0}&{{}\Rightarrow}\end{array}$ $\eta=0$ ). If the model admits arbitrage, we find a vector $\xi^{\prime}\cdot Y\ge0\underline{{\cal P}}$ -a.s. and $D P(\xi^{\prime}Y)>0$ with no initial investment. So for $\varphi^{*}$ optimal  

$$
\begin{array}{r}{B E(u(\varphi^{*^{\prime}}Y))<B E(u((\varphi^{*}+\eta)^{\prime}Y))}\end{array}
$$  

a contradiction.  

Assume now that the market is arbitrage-free. We consider the case $D=[a,\infty)$ for some $a\in(-\infty,0)$ .We show  

(i) $S(D)$ is compact;   
(ii) $\varphi\to L[u(\varphi^{\prime}Y)]$ is continuous.  

Clearly, $(i)$ and $(i i)$ imply existence of a maximizer.  

To show (i), assume that ( $\varphi_{n,}$ is a diverging sequence in. $S(D)$ . By choosing a subsequence if necessary, we may assume that $\eta_{n}=\varphi_{n}/|_{\varphi_{n}}|$ converges to some unit vector $\eta\in\mathcal{R}^{d}$ . Then  

$$
\eta^{\prime}Y=\operatorname*{lim}_{n\to\infty}\frac{\varphi_{n}^{\prime}Y}{|\varphi_{n}|}\geq\frac{a}{|\varphi_{n}|}=0\quad\mathit{I P a.s.}
$$  

and so by completeness $\tilde{\varphi}=(-S(0)^{\prime}\eta,\eta)$ is an arbitrage opportunity. However, under completeness $\eta^{\prime}Y=0$ $\mathbf{\Omega}_{\mu}\mathbf{\Omega}_{\mathrm{a}.\mathrm{s}}$ . implies $\eta=0$  

(ii) To show continuity it suffices to construct an integrable random variable which dominates $u(\varphi^{\prime}Y)$ for all $\varphi\in S(D)$ . Define $\eta\in\mathcal{R}^{d}$ by  

$$
\eta_{i}=0\vee\operatorname*{max}_{\varphi\in S(D)}\varphi^{i}<\infty.
$$  

Then, $\eta^{\prime}S(T)\ge\varphi^{\prime}S(T)$ for $\varphi\in S(D)$ and hence  

$$
\varphi^{\prime}Y={\frac{\varphi^{\prime}S(T)}{1+r}}-\varphi^{\prime}S(0)\leq{\frac{\eta^{\prime}\cdot S(T)}{1+r}}-\left(0\wedge\operatorname*{min}_{\xi\in S(D)}\xi^{\prime}S(0)\right).
$$  

Now $\eta^{\prime}Y$ is bounded below by $-\eta^{\prime}S(0)$ and there exists some $\alpha\in(0,1]$ such that $\alpha\eta^{\prime}S(0)<|a|$ Hence $\alpha\eta\in S(D)$ and by our assumption $L(u(\alpha\eta^{\prime}Y))<\infty$  

Applying Lemma 2.2.1 first with $b:=-\alpha S(0)^{\prime}\eta$ and then with. $b:=-0\wedge\operatorname*{min}_{\varphi\in S(D)}\varphi^{\prime}S(0)$ shows +hat  

$$
L\left[u\left(\frac{\eta^{\prime}S(0)}{1+r}-\sigma\wedge\operatorname*{min}_{\varphi\in S(D)}\varphi^{\prime}S(0)\right)\right]<\infty.
$$  

Lemma 2.2.1. If $D=[a,\infty),b<|a|,0<\alpha\leq1$ , and $X$ is a non-negative random variable, then  

$$
E[u(\alpha X-b)]<\infty\Rightarrow B[u(X)]<\infty.
$$  

Proof. The concavity of. $n$ implies that $u$ has a decreasing right-continuous derivative $u^{\prime}$ . Hence  

$$
\begin{array}{r c l}{{u(a X-b)}}&{{=}}&{{u(-b)+\begin{array}{c c}{{\alpha X-b}}\ {{\int}}\end{array}\quad u^{\prime}(x)d x\geq u(-b)+\begin{array}{c}{{\alpha X}}\ {{\int}}\end{array}u^{\prime}(y)d y}}\ {{}}&{{}}&{{-b}}\ {{}}&{{=}}&{{u(-b)+\alpha\underset{0}{\mathop{\int}}u^{\prime}(\alpha z)d z\geq u(-b)+\alpha(u(X)-u(0)).}}\end{array}
$$  

This shows that. $u(X)$ can be dominated by a multiple of $\boldsymbol{u}(\alpha X-\boldsymbol{b})$ plus some constant.  

We now turn to a characterization of the solution $\varphi^{*}$ of the utility maximization problem for continuously differentiable utility functions.  

Proposition 2.2.4. Let $n$ be a twice continuously differentiable utility function on $D$ such that $\mathit{I E}(u(\varphi^{\prime}Y))$ is finite for all $\varphi\in S(D)$ . Suppose that $\varphi^{*}$ is a solution of the utility maximization problem, and that one of the following conditions is satisfied. Either  

u is defined on $D=\mathit{\Pi}\mathit{\/{R}}$ and bounded from above or u is defined on $D=[a,\infty)$ and $\varphi^{*}$ is an interior point of. $S(D)$  

Then  

$$
u^{\prime}(\varphi^{*^{\prime}}Y)|Y|\in\mathcal{L}^{1}(I P)
$$  

and the following first-order condition holds  

$$
\begin{array}{r}{\mathbb{E}[u^{\prime}(\boldsymbol\varphi^{*^{\prime}}\boldsymbol Y)\cdot\boldsymbol Y]=0}\end{array}
$$  

Proof. For $\varphi\in S(D)$ and $\varepsilon\in[0,1]$ let $\varphi_{\varepsilon}=\varepsilon\varphi+(1-\varepsilon)\varphi^{*}$ and define  

$$
\Delta_{\varepsilon}=\frac{u(\varphi_{\varepsilon}^{\prime}Y)-u(\varphi^{*^{\prime}}Y)}{\varepsilon}
$$  

The concavity of $u$ implies that $\Delta_{\varepsilon}\geq\Delta_{\delta}$ for $\varepsilon\leq\delta$ , and so  

$$
\Delta_{\varepsilon}\uparrow u^{\prime}(\varepsilon\ast^{\prime}Y)(\varphi-\varphi^{\ast})^{\prime}Y\quad\mathrm{as}\quad\varepsilon\downarrow0.
$$  

Since $\Delta_{1}=u(\varepsilon^{\prime}Y)\in{\mathcal{L}}(I P)$ monotone convergence and the optimality of $\varphi^{*}$ yield  

$$
\begin{array}{r}{0\geq B(\Delta_{\varepsilon})\uparrow B\left(u^{\prime}(\varphi^{*^{\prime}}Y)(\varphi-\varphi^{*})^{\prime}Y\right)\quad\mathrm{as}\quad\varepsilon\downarrow0.}\end{array}
$$  

In particular, the expectation on the right-hand side is finite.  

Both sets of assumptions imply that $\varphi^{*}$ is an interior point of $S(D)$ . Hence from (2.22) we find by letting $\boldsymbol{\eta}=\boldsymbol{\varphi}-\boldsymbol{\varphi}^{*}$ that  

$$
L(u^{\prime}(\varphi*^{\prime}Y)\eta^{\prime}Y)\le0
$$  

for all $\eta$ in a small ball centered in the origin of ${\mathcal{R}}^{d}$ . Replacing $\eta$ by $-\eta$ shows that the expectation must vanish; i.e.. ${\cal{I}}E(u^{\prime}(\varphi^{*^{\prime}}Y)\eta^{\prime}Y)=0\forall\eta$ in a small ball around the origin, so ${\cal E}(u^{\prime}(\varphi^{*^{\prime}}Y)\eta^{\prime}Y)=$ 0.  

We can now give a characterisation of an equivalent risk-neutral measure.  

Corollary 2.2.1. Suppose that the market model is arbitrage-free and that the assumptions of Proposition 2.2.4 are satisfied for a utility function $u:D\rightarrow\mathscr{R}$ .Let $\phi^{*}$ be a maximizer of the expected utility. Then  

$$
\frac{d D^{*}}{d D}=\frac{u^{\prime}(\varphi^{*^{\prime}}Y)}{D E(u^{\prime}(\varphi^{*^{\prime}}Y))}
$$  

defines an equivalent risk-neutral measure.  

Proof. Recall that. $\textstyle{\mathcal{E}}^{*}(Y)=0$ is the criterion for risk-neutrality which is satisfied by Proposition 2.2.4. Hence $\b{\mathcal{N}}^{*}$ is a risk-neutral measure if it is well-defined, i.e..  

$$
\begin{array}{r}{D E(u^{\prime}(\varphi^{*^{\prime}}Y))\in\mathcal{L}^{1}(D).}\end{array}
$$  

Let  

$$
c=\operatorname*{sup}\left\{u^{\prime}(x)|x\in D{\mathrm{~and~}}|x|\leq|\varphi^{*}|\right\}\leq{\left\{\begin{array}{l l}{u^{\prime}(a)}&{D\in[a,\infty)}\ {u^{\prime}(-|\varphi^{*}|)}&{D=R}\end{array}\right.}
$$  

which is finite by our assumption that $u$ is continuously differentiable on $D$ . So  

$$
0\leq u^{\prime}(\varphi^{*^{\prime}}Y)\leq c+u^{\prime}(\varphi^{*^{\prime}}Y)|Y|\mathbf{1}_{\{|Y|\geq1\}}
$$  

and the right-hand side has finite expectation.  

Remark 2.2.2. We can now give a constructive proof of the first fundamental theorem of asset pricing. Suppose the model is arbitrage-free..   
(i) If $Y$ is a.s. $\mathcal{W}$ -a.s. bounded, then so is. $u^{\prime}(\varphi^{*^{\prime}}Y)$ and the measure $\b{\mathcal{M}}^{*}$ is an equivalent martingale measure with a bounded density.   
(ii) If $Y$ is unbounded we may consider the bounded random vector  

$$
\tilde{Y}=\frac{Y}{1+|Y|}
$$  

which also satisfies the no-arbitrage condition.  

Let $\tilde{\varphi}^{*}$ be a maximiser of expected utility $\it{I E}(u^{\prime}(\varphi^{\prime}\tilde{Y})$ . Then an equivalent martingale measure is given by $\b{\mathcal{N}}^{*}$ defined via the bounded density  

$$
\frac{d{D/}^{*}}{d{D/}}=c\frac{u^{\prime}({\tilde{\varphi}^{*}}^{\prime}{\tilde{Y}})}{1+|Y|}
$$  

where c is an appropriate constant.  

# Chapter 3  

# Discrete-time models of financial markets  

# 3.1 The model  

We will study so-called finite markets - i.e. discrete-time models of financial markets in which all. relevant quantities take a finite number of values. Following the approach of Harrison and Pliska (1981) and Taqqu and Willinger (1987), it suffices, to illustrate the ideas, to work with a finite. probability space $(\Omega,{\mathcal{F}},I P)$ , with a finite number. $|\Omega|$ of points $\omega$ , each with positive probability: ${\cal P}(\{\omega\})>0$  

We specify a time horizon $T$ , which is the terminal date for all economic activities considered. (For a simple option pricing model the time horizon typically corresponds to the expiry date of the option.)  

As before, we use a filtration $\boldsymbol{F}=\{\mathcal{F}_{t}\}_{t=0}^{T}$ consisting ofd $\sigma$ -algebras ${\mathcal{F}}_{0}\subset{\mathcal{F}}_{1}\subset\cdots\subset{\mathcal{F}}_{T}$ : we take $\mathcal{F}_{0}=\{\varnothing,\Omega\}$ , the trivial. $\sigma$ -field, $\mathcal{F}_{T}=\mathcal{F}=\mathcal{P}(\Omega)$ (here $\mathcal{P}(\Omega)$ is the power-set of $\Omega$ , the class. of all $2^{|\Omega|}$ subsets of. $\Omega$ : we need every possible subset, as they all - apart from the empty set -- carry positive probability).  

The financial market contains $d+1$ financial assets. The usual interpretation is to assume. one risk-free asset (bond, bank account) labelled. $0$ , and $d$ risky assets (stocks, say) labelled 1 to $d$ .While the reader may keep this interpretation as a mental picture, we prefer not to use it directly. The prices of the assets at time. $t$ are random variables,. $S_{0}(t,\omega),S_{1}(t,\omega),\ldots,S_{d}(t,\omega)$ say, non-negative and. $\mathbf{\mathcal{F}}_{t}$ -measurable (i.e. adapted: at time $t$ , we know the prices. $S_{i}(t)$ ).We write $S(t)=(S_{0}(t),S_{1}(t),\ldots,S_{d}(t))^{\prime}$ for the vector of prices at time $t$ . Hereafter we refer to the. probability space $(\Omega,{\mathcal{F}},I P)$ , the set of trading dates, the price process $S$ and the information. structure $\bar{\mathcal{M}}$ , which is typically generated by the price process. $S$ , together as a securities market model.  

It will be essential to assume that the price process of at least one asset follows a strictly positive process.  

Definition 3.1.1. A numeraire is a price process $(X(t))_{t=0}^{T}$ (a sequence of random variables),.   
which is strictly positive for all. $t\in\{0,1,\ldots,T\}$  

For the standard approach the risk-free bank account process is used as numeraire. In some applications, however, it is more convenient to use a security other than the bank account and we therefore just use $S_{0}$ without further specification as a numeraire. We furthermore take. $S_{0}(0)=1$ (that is, we reckon in units of the initial value of our numeraire), and define $\beta(t):=1/S_{0}(t)$ as a discount factor.  

A trading strategy (or dynamic portfolio) $\varphi$ is a $\textstyle\mathit{\Pi}\mathit{{H}}^{d+1}$ vector stochastic process $\varphi=(\varphi(t))_{t=1}^{T}=$ $((\varphi_{0}(t,\omega),\varphi_{1}(t,\omega),\ldots,\varphi_{d}(t,\omega))^{\prime})_{t=1}^{T}$ which is predictable (or previsible): each $\varphi_{i}(t)$ is $\mathcal{F}_{t-1}$ -measurable for $t\geq1$ . Here $\varphi_{i}(t)$ denotes the number of shares of asset $i$ held in the portfolio at time $t-$ to  

be determined on the basis of information available before time. $t$ ; i.e. the investor selects his time $t$ portfolio after observing the prices $S(t-1)$ . However, the portfolio $\varphi(t)$ must be established before, and held until after, announcement of the prices. $S(t)$ . The components $\varphi_{i}(t)$ may assume negative as well as positive values, reflecting the fact that we allow short sales and assume that the assets are perfectly divisible.  

Definition 3.1.2. The value of the portfolio at time $t$ is the scalar product  

$$
V_{\varphi}(t)=\varphi(t)\cdot S(t):=\sum_{i=0}^{d}\varphi_{i}(t)S_{i}(t),(t=1,2,\ldots,T)a n d V_{\varphi}(0)=\varphi(1)\cdot S(0).
$$  

The process $V_{\varphi}(t,\omega)$ is called the wealth or value process of the trading strategy $\varphi$  

The initial wealth. $V_{\varphi}(0)$ is called the initial investment or endowment of the investor. Now $\varphi(t)\cdot S(t-1)$ reflects the market value of the portfolio just after it has been established at time $t-1$ , whereas $\varphi(t)\cdot S(t)$ is the value just after time $t$ prices are observed, but before changes. are made in the portfolio. Hence  

$$
\varphi(t)\cdot(S(t)-S(t-1))=\varphi(t)\cdot\Delta S(t)
$$  

is the change in the market value due to changes in security prices which occur between time $t-1$ and $t$ .This motivates:  

Definition 3.1.3. The gains process $G_{\varphi}$ of a trading strategy. $\varphi$ is given by.  

$$
G_{\varphi}(t):=\sum_{\tau=1}^{t}\varphi(\tau)\cdot(S(\tau)-S(\tau-1))=\sum_{\tau=1}^{t}\varphi(\tau)\cdot\Delta S(\tau),(t=1,2,\ldots,T).
$$  

Observe the - for now - formal similarity of the gains process $G_{\varphi}$ from trading in $S$ following a trading strategy $\varphi$ to the martingale transform of $S$ by $\varphi$  

Define $S(t)=(1,\beta(t)S_{1}(t),\ldots,\beta(t)S_{d}(t))^{\prime}$ , the vector of discounted prices, and consider the discounted value process  

$$
\tilde{V}_{\varphi}(t)=\beta(t)(\varphi(t)\cdot S(t))=\varphi(t)\cdot\tilde{S}(t),(t=1,2,\ldots,T)
$$  

and the discounted gains process  

$$
\tilde{G}_{\varphi}(t):=\sum_{\tau=1}^{t}\varphi(\tau)\cdot(\tilde{S}(\tau)-\tilde{S}(\tau-1))=\sum_{\tau=1}^{t}\varphi(\tau)\cdot\Delta\tilde{S}(\tau),\quad(t=1,2,\ldots,T).
$$  

Observe that the discounted gains process reflects the gains from trading with assets $^{1}$ to $d$ only, which in case of the standard model (a bank account and. $d$ stocks) are the risky assets.  

We will only consider special classes of trading strategies.  

Definition 3.1.4. The strategy $\varphi$ is self-financing, $\varphi\in\Phi$ $i f$  

$$
\varphi(t)\cdot S(t)=\varphi(t+1)\cdot S(t)(t=1,2,\ldots,T-1).
$$  

# Interpretation.  

When new prices $S(t)$ are quoted at time $t$ , the investor adjusts his portfolio from $\varphi(t)$ to $\varphi(t+1)$ without bringing in or consuming any wealth. The following result (which is trivial in our current setting, but requires a little argument in continuous time) shows that renormalising security prices (i.e. changing the numeraire) has essentially no economic effects.  

Proposition 3.1.1 (Numeraire Invariance). Let $X(t)$ be a numeraire. A trading strategy $\varphi$ is self-financing with respect to $S(t)$ if and only if $\varphi$ is self-financing with respect to $X(t)^{-1}S(t)$  

Proof. Since. $X(t)$ is strictly positive for all. $t=0,1,\ldots,T$ we have the following equivalence, which implies the claim:.  

$$
\begin{array}{r l}{\varphi(t)\cdot S(t)=\varphi(t+1)\cdot S(t)}&{(t=1,2,\ldots,T-1)}\ {\qquad}&{\Leftrightarrow}\ {\varphi(t)\cdot X(t)^{-1}S(t)=\varphi(t+1)\cdot X(t)^{-1}S(t)}&{(t=1,2,\ldots,T-1).}\end{array}
$$  

Corollary 3.1.1. A trading strategy $\varphi$ is self-financing with respect to. $S(t)$ if and only if. $\varphi$ is self-financing with respect to $\tilde{S}(t)$  

We now give a characterisation of self-financing strategies in terms of the discounted processes.  

Proposition 3.1.2. $A$ trading strategy $\varphi$ belongs to $\Phi$ if and only if  

$$
\begin{array}{r}{\tilde{V}_{\varphi}(t)=V_{\varphi}(0)+\tilde{G}_{\varphi}(t),(t=0,1,\ldots,T).}\end{array}
$$  

Proof. Assume $\varphi\in\Phi$ . Then using the defining relation (3.1), the numeraire invariance theorem and the fact that $S_{0}(0)=1$  

$$
\begin{array}{l l l}{{{\displaystyle V_{\varphi}(0)+\tilde{G}_{\varphi}(t)}}}&{{=}}&{{\displaystyle\varphi(1)\cdot S(0)+\sum_{\tau=1}^{t}\varphi(\tau)\cdot(\tilde{S}(\tau)-\tilde{S}(\tau-1))}}\ {{}}&{{=}}&{{\displaystyle\varphi(1)\cdot\tilde{S}(0)+\varphi(t)\cdot\tilde{S}(t)}}\ {{}}&{{}}&{{-}}&{{\displaystyle\sum_{\tau=1}^{t-1}(\varphi(\tau)-\varphi(\tau+1))\cdot\tilde{S}(\tau)-\varphi(1)\cdot\tilde{S}(0)}}\ {{}}&{{=}}&{{\displaystyle\varphi(t)\cdot\tilde{S}(t)=\tilde{V}_{\varphi}(t).}}\end{array}
$$  

Assume now that (3.2) holds true. By the numeraire invariance theorem it is enough to show the discounted version of relation (3.1). Summing up to. $t=2$ (3.2) is  

$$
\varphi(2)\cdot\tilde{S}(2)=\varphi(1)\cdot\tilde{S}(0)+\varphi(1)\cdot(\tilde{S}(1)-\tilde{S}(0))+\varphi(2)\cdot(\tilde{S}(2)-\tilde{S}(1)).
$$  

Subtracting $\varphi(2)\cdot\tilde{S}(2)$ on both sides gives $\varphi(2)\cdot\tilde{S}(1)=\varphi(1)\cdot\tilde{S}(1)$ , which is (3.1) for $t=1$ Proceeding similarly - or by induction - we can show $\varphi(t)\cdot\tilde{S}(t)=\varphi(t+1)\cdot\tilde{S}(t)$ for $t=2,\ldots,T-1$ as required.  

We are allowed to borrow (so $\varphi_{0}(t)$ may be negative) and sell short (so. $\varphi_{i}(t)$ may be negative for $i=1,\ldots,d$ ). So it is hardly surprising that if we decide what to do about the risky assets and fix an initial endowment, the numeraire will take care of itself, in the following sense..  

Proposition 3.1.3. If $(\varphi_{1}(t),\dots,\varphi_{d}(t))^{\prime}$ is predictable and. $V_{0}$ is $\mathcal{F}_{0}$ -measurable, there is a unique. predictable process $(\varphi_{0}(t))_{t=1}^{T}$ such that $\varphi=(\varphi_{0},\varphi_{1},\ldots,\varphi_{d})^{\prime}$ is self-financing with initial value of the corresponding portfolio $V_{\varphi}(0)=V_{0}$  

Proof. If $\varphi$ is self-financing, then by Proposition 3.1.2,  

$$
\tilde{V}_{\varphi}(t)=V_{0}+\tilde{G}_{\varphi}(t)=V_{0}+\sum_{\tau=1}^{t}(\varphi_{1}(\tau)\Delta\tilde{S}_{1}(\tau)+...+\varphi_{d}(\tau)\Delta\tilde{S}_{d}(\tau)).
$$  

On the other hand,  

$$
\mathbf{\Phi}_{\varphi}^{r}(t)=\varphi(t)\cdot\tilde{S}(t)=\varphi_{0}(t)+\varphi_{1}(t)\tilde{S}_{1}(t)+\ldots+\varphi_{d}
$$  

Equate these:  

$$
\begin{array}{r c l}{\displaystyle\varphi_{0}(t)}&{=}&{\displaystyle V_{0}+\sum_{\tau=1}^{t}(\varphi_{1}(\tau)\Delta\tilde{S}_{1}(\tau)+...+\varphi_{d}(\tau)\Delta\tilde{S}_{d}(\tau))}\ &&{\displaystyle-(\varphi_{1}(t)\tilde{S}_{1}(t)+...+\varphi_{d}(t)\tilde{S}_{d}(t)),}\end{array}
$$  

which defines. $\varphi_{0}(t)$ uniquely. The terms in $\tilde{S}_{i}(t)$ are  

$$
\varphi_{i}(t)\Delta\tilde{S}_{i}(t)-\varphi_{i}(t)\tilde{S}_{i}(t)=-\varphi_{i}(t)\tilde{S}_{i}(t-1),
$$  

which is $\mathcal{F}_{t-1}$ -measurable. So  

$$
\begin{array}{r c l}{\displaystyle\varphi_{0}(t)}&{=}&{\displaystyle V_{0}+\sum_{\tau=1}^{t-1}(\varphi_{1}(\tau)\Delta\tilde{S}_{1}(\tau)+...+\varphi_{d}(\tau)\Delta\tilde{S}_{d}(\tau))}\ &&{\displaystyle-(\varphi_{1}(t)S_{1}(t-1)+...+\varphi_{d}(t)\tilde{S}_{d}(t-1)),}\end{array}
$$  

where as. $\varphi_{1},\ldots,\varphi_{d}$ are predictable, all terms on the right-hand side are $\mathcal{F}_{t-1}$ -measurable, so $\varphi_{0}$ is predictable. $\llcorner$  

Remark 3.1.1. Proposition 3.1.3 has a further important consequence: for defining a gains proceSs $\tilde{G}_{\varphi}$ only the components $(\varphi_{1}(t),\dots,\varphi_{d}(t))^{\prime}$ are needed. If we require them to be predictable. they correspond in a unique way (after fixing initial endowment) to a self-financing trading strategy. Thus for the discounted world predictable strategies and final cash-flows generated by them are all that matters..  

We now turn to the modelling of derivative instruments in our current framework. This is done in the following fashion..  

Definition 3.1.5. A contingent claim $X$ with maturity date. $T$ is an arbitrary. $\mathcal{F}_{T}=\mathcal{F}$ -measurable random variable (which is by the finiteness of the probability space bounded). We denote the class of all contingent claims by. $L^{0}=L^{0}(\Omega,{\mathcal{F}},I P)$  

The notation $L^{0}$ for contingent claims is motivated by the them being simply random variables in our context (and the functional-analytic spaces used later on).  

A typical example of a contingent claim $X$ is an option on some underlying asset $S$ , then (e.g. for the case of a European call option with maturity date. $T$ and strike $K$ ) we have a functional. relation $X=f(S)$ with some function. $f$ (e.g. $X=(S(T)-K)^{+})$ . The general definition allows for more complicated relationships which are captured by the ${\mathcal{F}}_{T}$ -measurability of $X$ (recall that ${\mathcal{F}}_{T}$ is typically generated by the process. $S$  

# 3.2 Existence of Equivalent Martingale Measures  

# 3.2.1 The No-Arbitrage Condition  

The central principle in the single period example was the absence of arbitrage opportunities, i.e.. the absence investment strategies for making profits without exposure to risk. As mentioned there. this principle is central for any market model, and we now define the mathematical counterpart of this economic principle in our current setting..  

Definition 3.2.1. Let ${\tilde{\Phi}}\subset\Phi$ be a set of self-financing strategies.. $A$ strategy $\varphi\in\tilde{\Phi}$ is called an arbitrage opportunity or arbitrage strategy with respect to $\tilde{\Phi}$ if ${\cal I}P\{V_{\varphi}(0)=0\}=1$ , and the. terminal wealth of $\varphi$ satisfies  

$$
{\cal I P}\{V_{\varphi}(T)\geq0\}=1a n d{\cal P}\{V_{\varphi}(T)>0\}>0.
$$  

So an arbitrage opportunity is a self-financing strategy with zero initial value, which produces. a non-negative final value with probability one and has a positive probability of a positive final value. Observe that arbitrage opportunities are always defined with respect to a certain class of trading strategies.  

Definition 3.2.2. We say that a security market $\mathcal{M}$ is arbitrage-fre if there are no arbitrage.   
opportunities in the class. $\Phi$ of trading strategies.  

We will allow ourselves to use 'no-arbitrage' in place of 'arbitrage-free' when convenient.  

The fundamental insight in the single-period example was the equivalence of the no-arbitrage. condition and the existence of risk-neutral probabilities. For the multi-period case we now use probabilistic machinery to establish the corresponding result..  

Definition 3.2.3. A probability measure $\b{\mathcal{N}}^{*}$ on $(\Omega,\mathcal{F}_{T})$ equivalent to $\mathit{\Pi}_{\mathit{\Pi}}{\mathcal{P}}$ is called a martingale measure for $\tilde{S}$ if the process $\tilde{S}$ follows a $\mathit{\Pi}\mathit{\perp}\mathit{\Psi}$ -martingale with respect to the filtration $\bar{\mu}$ . We denote by $\mathcal{P}(\tilde{S})$ the class of equivalent martingale measures.  

Proposition 3.2.1. Let $\b{\mathcal{M}}^{*}$ be an equivalent martingale measure $(I P^{\ast}\in\mathcal P(\tilde{S}))$ and $\varphi\in\Phi$ any self-financing strategy. Then the wealth process $\tilde{V}_{\varphi}(t)$ is a $\b{\mathcal{M}}^{*}$ -martingale with respect to the filtration $\bar{\mathcal{M}}$  

Proof. By the self-financing property of. $\varphi$ (compare Proposition 3.1.2, (3.2)), we have  

$$
\begin{array}{r}{\tilde{V}_{\varphi}(t)=V_{\varphi}(0)+\tilde{G}_{\varphi}(t)(t=0,1,\ldots,T).}\end{array}
$$  

So  

$$
\tilde{V}_{\varphi}(t+1)-\tilde{V}_{\varphi}(t)=\tilde{G}_{\varphi}(t+1)-\tilde{G}_{\varphi}(t)=\varphi(t+1)\cdot(\tilde{S}(t+1)-\tilde{S}(t)).
$$  

So for $\varphi\in\Phi$ $\tilde{V}_{\varphi}(t)$ is the martingale transform of the $\mathit{\Pi}\mathit{\perp}\mathit{\Psi}$ martingale $\tilde{S}$ by $\varphi$ (see Theorem C.4.1) and hence a $\b{\mathcal{N}}^{*}$ martingale itself.  

Observe that in our setting all processes are bounded, i.e. the martingale transform theorem. is applicable without further restrictions. The next result is the key for the further development.  

Proposition 3.2.2. If an equivalent martingale measure exists - that is, if $\mathcal{P}(\tilde{S})\neq\emptyset$ - then the market $\mathcal{M}$ is arbitrage-free.  

Proof. Assume such a $\mathit{\Pi}/\mathit{\Pi}^{*}$ exists. For any self-financing strategy $\varphi$ , we have as before  

$$
\tilde{V}_{\varphi}(t)=V_{\varphi}(0)+\sum_{\tau=1}^{t}\varphi(\tau)\cdot\Delta\tilde{S}(\tau).
$$  

By Proposition 3.2.1, $\tilde{S}(t)$ a (vector) $\b{\mathcal{U}}^{*}$ -martingale implies $\tilde{V}_{\varphi}(t)$ is a $P^{*}$ -martingale. So the initial and final $\b{\mathcal{M}}^{*}$ -expectations are the same,  

$$
\begin{array}{r}{E^{*}(\tilde{V}_{\varphi}(T))=I E^{*}(\tilde{V}_{\varphi}(0)).}\end{array}
$$  

If the strategy is an arbitrage opportunity its initial value - the right-hand side above - is zero. Therefore the left-hand side $\tilde{\cal M}^{*}(\tilde{V}_{\varphi}(T))$ is zero, but $\tilde{V}_{\varphi}(T)\geq0$ (by definition). Also each $D P^{*}(\{\omega\})>0$ (by assumption, each $I P(\{\omega\})>0$ , so by equivalence each $I P^{*}(\{\omega\})>0$ ). This and $\dot{V}_{\varphi}(T)\geq0$ force $\tilde{V}_{\varphi}(T)=0$ . So no arbitrage is possible.  

Proposition 3.2.3. If the market $\mathcal{M}$ is arbitrage-free, then the class. $\mathcal{P}(\tilde{S})$ of equivalent martingale measures is non-empty..  

For the proof (for which we follow Schachermayer (2o00) we need some auxiliary observations. Recall the definition of arbitrage, i.e. Definition 3.2.1, in our finite-dimensional setting: a selffinancing trading strategy $\varphi\in\Phi$ is an arbitrage opportunity if $V_{\varphi}(0)=0$ $V_{\varphi}(T,\omega)\geq0\forall\omega\in\Omega$ and there exists a. $\omega\in\Omega$ with $V_{\varphi}(T,\omega)>0$  

Now call $L^{0}=L^{0}(\Omega,{\mathcal{F}},I P)$ the set of random variables on $(\Omega,{\mathcal{F}})$ and  

$$
L_{++}^{0}(\Omega,\mathcal{F},\mathcal{P}):=\{X\in L^{0}:X(\omega)\geq0\forall\omega\in\Omega\mathrm{and}\exists\omega\in\Omega\mathrm{such~that}X(\omega)>0\}.
$$  

(Observe that $L_{++}^{0}$ is a cone -closed under vector addition and multiplication by positive scalars.) Using $L_{++}^{0}$ we can write the arbitrage condition more compactly as  

$$
V_{\varphi}(0)=\tilde{V}_{\varphi}(0)=0\Rightarrow\tilde{V}_{\varphi}(T)\notin L_{++}^{0}(\Omega,\mathcal{F},T).
$$  

for any self-financing strategy $\varphi$  

The next lemma formulates the arbitrage condition in terms of discounted gains processes. The important advantage in using this setting (rather than a setting in terms of value processes) is that we only have to assume predictability of a vector process. $\left(\varphi_{1},\ldots,\varphi_{d}\right)$ . Recall Remark 3.1.1 and Proposition 3.1.3 here: we can choose a process. $\varphi_{0}$ in such a way that the strategy. $\varphi=(\varphi_{0},\varphi_{1},\ldots,\varphi_{d})$ has zero initial value and is self-financing..  

Lemma 3.2.1. In an arbitrage-free market any predictable vector process $\varphi^{\prime}=(\varphi_{1},\ldots,\varphi_{d})$ satisfies  

$$
\tilde{G}_{\varphi^{\prime}}(T)\not\in L_{++}^{0}(\Omega,{\mathcal{F}},I P).
$$  

(Observe the slight abuse of notation: for the value of the discounted gains process the zeroth component of a trading strategy doesn't matter. Hence we use the operator $\tilde{G}$ for $d$ -dimensional vectors as well.)  

Proof. By Proposition 3.1.3 there exists a unique predictable process $(\varphi_{0}(t))$ such that $\varphi=$ $\left(\varphi_{0},\varphi_{1},\ldots,\varphi_{d}\right)$ has zero initial value and is self-financing. Assume. $\tilde{G}_{\varphi^{\prime}}(T)\in L_{++}^{0}(\Omega,{\mathcal{F}},I P)$ Then using Proposition 3.1.2,.  

$$
V_{\varphi}(T)=\beta(T)^{-1}\tilde{V}_{\varphi}(T)=\beta(T)^{-1}(V_{\varphi}(0)+\tilde{G}_{\varphi}(T))=\beta(T)^{-1}\tilde{G}_{\varphi^{\prime}}(T)\geq0,
$$  

and is positive somewhere (i.e. with positive probability) by definition of $L_{++}^{0}$ . Hence $\varphi$ is an arbitrage opportunity with respect to $\Phi$ .This contradicts the assumption that the market is arbitrage-free.  

We now define the space of contingent claims, i.e. random variables on. $\left(\Omega,\mathcal{F}\right)$ , which an economic agent may replicate with zero initial investment by pursuing some predictable trading strategy $\varphi$  

Definition 3.2.4. We call the subspace $K$ of $L^{0}(\Omega,\mathcal{F},I P)$ defined by.  

$$
K=\{X\in L^{0}(\Omega,{\mathcal{F}},I P):X={\tilde{G}}_{\varphi}(T),\varphi p r e d i c t a b l e\}
$$  

the set of contingent claims attainable at price 0.  

We can now restate Lemma 3.2.1 in terms of spaces A market is arbitrage-free if and only if  

$$
K\cap L_{++}^{0}(\Omega,{\mathcal{F}},I P)=\emptyset.
$$  

Proof of Proposition 3.2.3. Since our market model is finite we can use results from Euclidean geometry, in particular we can identify $L^{0}$ with $\mathbb{R}^{|\Omega|}$ ). By assumption we have (3.3), i.e. $K$ and $L_{++}^{0}$ do not intersect. So $K$ does not meet the subset  

$$
D:=\{X\in L_{++}^{0}:\sum_{\omega\in\Omega}X(\omega)=1\}.
$$  

Now $D$ is a compact convex set. By the separating hyperplane theorem, there is a vector $\lambda=$ $\lambda(\omega):\omega\in\Omega)$ such that for all $X\in D$  

$$
\lambda\cdot X:=\sum_{\omega\in\Omega}\lambda(\omega)X(\omega)>0,
$$  

but for all $\tilde{G}_{\varphi}(T)$ in $K$  

$$
\lambda\cdot\tilde{G}_{\varphi}(T)=\sum_{\omega\in\Omega}\lambda(\omega)\tilde{G}_{\varphi}(T)(\omega)=0.
$$  

Choosing each $\omega\in\Omega$ successively and taking $X$ to be $^{1}$ on this $\omega$ and zero elsewhere, (3.4) tells us that each $\lambda(\omega)>0$ . So  

$$
P^{*}(\{\omega\}):=\frac{\lambda(\omega)}{\sum_{\omega^{\prime}\in\Omega}\lambda(\omega^{\prime})}
$$  

defines a probability measure equivalent to $\mathcal{W}$ (no non-empty null sets). With $\mathbf{\nabla}\mu^{*}$ as $\b{\mathcal{M}}^{*}$ expectation, (3.5) says that  

$$
{\cal E}^{*}\left(\tilde{G}_{\varphi}(T)\right)=0,
$$  

i.e.  

$$
E^{*}\left(\sum_{\tau=1}^{T}\varphi(\tau)\cdot\Delta\tilde{S}(\tau)\right)=0.
$$  

In particular, choosing for each $i$ to hold only stock $i$  

$$
H^{*}\left(\sum_{\tau=1}^{T}\varphi_{i}(\tau)\Delta\tilde{S}_{i}(\tau)\right)=0\quad(i=1,\dots,d).
$$  

Since this holds for any predictable $\varphi$ (boundedness holds automatically as $\Omega$ is finite), the martingale transform lemma tells us that the discounted price processes $(\Tilde{S}_{i}(t))$ are $\b{\mathcal{M}}^{*}$ -martingales.  

Note. Our situation is finite-dimensional, so all we have used here is Euclidean geometry. We. have a subspace, and a cone not meeting the subspace except at the origin. Take. $\lambda$ orthogonal to the subspace on the same side of the subspace as the cone. The separating hyperplane theorem. holds also in infinite-dimensional situations, where it is a form of the Hahn-Banach theorem of functional analysis.  

We now combine Propositions 3.2.2 and 3.2.3 as a first central theorem in this chapter.  

Theorem 3.2.1 (No-Arbitrage Theorem). The market $\mathcal{M}$ is arbitrage-free if and only if there exists a probability measure. $\mathit{\Pi}\mathit{\perp}\mathit{\Psi}$ equivalent to $\mathcal{W}$ under which the discounted d-dimensional asset price process $\bar{S}$ is a $\b{\mathcal{M}}^{*}$ -martingale.  

# 3.2.2 Risk-Neutral Pricing  

We now turn to the main underlying question of this text, namely the pricing of contingent claims (i.e. financial derivatives). As in chapter 1 the basic idea is to reproduce the cash flow of a contingent claim in terms of a portfolio of the underlying assets. On the other hand, the equivalence of the no-arbitrage condition and the existence of risk-neutral probability measures imply the possibility of using risk-neutral measures for pricing purposes. We will explore the relation of these tow approaches in this subsection.  

We say that a contingent claim is attainable if there exists a replicating strategy $\varphi\in\Phi$ such that  

$$
V_{\varphi}(T)=X.
$$  

So the replicating strategy generates the same time $T$ cash-flow as does $X$ .Working with discounted values (recall we use $\beta$ as the discount factor) we find  

$$
\beta(T)X=\tilde{V}_{\varphi}(T)=V(0)+\tilde{G}_{\varphi}(T).
$$  

So the discounted value of a contingent claim is given by the initial cost of setting up a replication. strategy and the gains from trading. In a highly efficient security market we expect that the law. of one price holds true, that is for a specified cash-flow there exists only one price at any time instant. Otherwise arbitrageurs would use the opportunity to cash in a riskless profit. So the no-arbitrage condition implies that for an attainable contingent claim its time. $t$ price must be given by the value (inital cost) of any replicating strategy (we say the claim is uniquely replicated in that case). This is the basic idea of the arbitrage pricing theory..  

Let us investigate replicating strategies a bit further. The idea is to replicate a given cash-flow at a given point in time. Using a self-financing trading strategy the investor's wealth may go negative at time $t<T$ , but he must be able to cover his debt at the final date. To avoid negative wealth the concept of admissible strategies is introduced. A self-financing trading strategy $\varphi\in\Phi$ is called admissible if $V_{\varphi}(t)\geq0$ for each $t=0,1,\ldots,T$ .We write. $\Phi_{a}$ for the class of admissible trading strategies. The modelling assumption of admissible strategies reflects the economic fact that the broker should be protected from unbounded short sales. In our current setting all processes are bounded anyway, so this distinction is not really needed and we use self-financing strategies when addressing the mathematical aspects of the theory. (In fact one can show that a security market which is arbitrage-free with respect to $\Phi_{a}$ is also arbitrage-free with respect to $\Phi$ ; see Exercises.)  

We now return to the main question of the section: given a contingent claim $X$ , i.e. a cash-flow at time $T$ , how can we determine its value (price) at time $t<T$ ? For an attainable contingent claim this value should be given by the value of any replicating strategy at time $t$ , i.e. there should be a unique value process (say $V_{X}(t)$ ) representing the time $t$ value of the simple contingent claim $X$ . The following proposition ensures that the value processes of replicating trading strategies coincide, thus proving the uniqueness of the value process.  

Proposition 3.2.4. Suppose the market. $\mathcal{M}$ is arbitrage-free. Then any attainable contingent claim $X$ is uniquely replicated in. $\mathcal{M}$  

Proof. Suppose there is an attainable contingent claim $X$ and strategies $\varphi$ and $\psi$ such that  

$$
V_{\varphi}(T)=V_{\psi}(T)=X,
$$  

but there exists a $\tau<T$ such that  

$$
V_{\varphi}(u)=V_{\psi}(u)\mathrm{forevery}u<\tau\mathrm{and}V_{\varphi}(\tau)\neq V_{\psi}(\tau).
$$  

Define $A:=\{\omega\in\Omega:V_{\varphi}(\tau,\omega)>V_{\psi}(\tau,\omega)\}$ , then $A\in\mathcal{F}_{\tau}$ and $\textstyle{\cal{T}}(A)>0$ (otherwise just rename the strategies). Define the ${\mathcal{F}}_{\tau}$ -measurable random variable $Y:=V_{\varphi}(\tau)-V_{\psi}(\tau)$ and consider the trading strategy $\xi$ defined by  

$$
\xi(u)=\left\{\begin{array}{l l}{\varphi(u)-\psi(u),}&{u\leq\tau}\ {\mathbf{1}_{A^{c}}(\varphi(u)-\psi(u))+\mathbf{1}_{A}(Y\beta(\tau),0,\dots,0),}&{\tau<u\leq T.}\end{array}\right.
$$  

The idea here is to use. $\varphi$ and $\psi$ to construct a self-financing strategy with zero initial investment (hence use their difference $\xi$ ) and put any gains at time $\tau$ in the savings account (i.e. invest them riskfree) up to time. $T$  

We need to show formally that $\xi$ satisfies the conditions of an arbitrage opportunity. By construction $\xi$ is predictable and the self-financing condition (3.1) is clearly true for $t\neq\tau$ , and for $t=\tau$ we have using that $\varphi,\psi\in\Phi$  

$$
\begin{array}{r c l}{\boldsymbol{\xi}(\tau)\cdot\boldsymbol{S}(\tau)}&{=}&{\left(\varphi(\tau)-\psi(\tau)\right)\cdot\boldsymbol{S}(\tau)=V_{\varphi}(\tau)-V_{\psi}(\tau),}\ {\boldsymbol{\xi}(\tau+1)\cdot\boldsymbol{S}(\tau)}&{=}&{\mathbf{1}_{A^{c}}(\varphi(\tau+1)-\psi(\tau+1))\cdot\boldsymbol{S}(\tau)+\mathbf{1}_{A}\boldsymbol{Y}\beta(\tau)S_{0}(\tau)}\ &{=}&{\mathbf{1}_{A^{c}}(\varphi(\tau)-\psi(\tau))\cdot\boldsymbol{S}(\tau)+\mathbf{1}_{A}(V_{\varphi}(\tau)-V_{\psi}(\tau))\beta(\tau)\beta^{-1}(\tau)}\ &{=}&{V_{\varphi}(\tau)-V_{\psi}(\tau).}\end{array}
$$  

Hence $\xi$ is a self-financing strategy with initial value equal to zero. Furthermore  

$$
\begin{array}{l l l}{{V_{\xi}(T)}}&{{=}}&{{{\bf1}_{A^{c}}(\varphi(T)-\psi(T))\cdot S(T)+{\bf1}_{A}(Y\beta(\tau),0,\ldots,0)\cdot S(T)}}\ {{}}&{{}}&{{}}\ {{}}&{{=}}&{{{\bf1}_{A}Y\beta(\tau)S_{0}(T)\geq0}}\end{array}
$$  

and  

$$
{\cal I P}\{V_{\xi}(T)>0\}={\cal I P}\{A\}>0.
$$  

Hence the market contains an arbitrage opportunity with respect to the class. $\Phi$ of self-financing strategies. But this contradicts the assumption that the market $\mathcal{M}$ is arbitrage-free.  

This uniqueness property allows us now to define the important concept of an arbitrage price process.  

Definition 3.2.5. Suppose the market is arbitrage-free. Let $X$ be any attainable contingent claim with time $T$ maturity. Then the arbitrage price process. $\pi_{X}(t),0\leq t\leq T$ or simply arbitrage price. of $X$ is given by the value process of any replicating strategy. $\varphi$ for $X$  

The construction of hedging strategies that replicate the outcome of a contingent claim (for. example a European option) is an important problem in both practical and theoretical applications.. Hedging is central to the theory of option pricing. The classical arbitrage valuation models, such as the Black-Scholes model ((Black and Scholes 1973), depend on the idea that an option can be perfectly hedged using the underlying asset (in our case the assets of the market model), so making it possible to create a portfolio that replicates the option exactly. Hedging is also widely used to reduce risk, and the kinds of delta-hedging strategies implicit in the Black-Scholes model. are used by participants in option markets. We will come back to hedging problems subsequently.  

Analysing the arbitrage-pricing approach we observe that the derivation of the price of a contingent claim doesn't require any specific preferences of the agents other than nonsatiation, i.e.. agents prefer more to less, which rules out arbitrage. So, the pricing formula for any attainable contingent claim must be independent of all preferences that do not admit arbitrage. In particular,. an economy of risk-neutral investors must price a contingent claim in the same manner. This fundamental insight, due to Cox and Ross (Cox and Ross 1976) in the case of a simple economy a riskless asset and one risky asset - and in its general form due to Harrison and Kreps (Harrison and Kreps 1979), simplifies the pricing formula enormously. In its general form the price of an. attainable simple contingent claim is just the expected value of the discounted payoff with respect to an equivalent martingale measure.  

Proposition 3.2.5. The arbitrage price process of any attainable contingent claim $X$ is given by the risk-neutral valuation formula  

$$
\pi_{\boldsymbol{X}}(t)=\beta(t)^{-1}\boldsymbol{I}\boldsymbol{E}^{*}\left(\boldsymbol{X}\boldsymbol{\beta}(T)\vert\boldsymbol{\mathcal{F}}_{t}\right)\quad\forall t=0,1,\ldots,T,
$$  

where $\mathit{\Pi}\mathit{{I E}}^{*}$ is the expectation operator with respect to an equivalent martingale measure ${\mathcal{M}}^{\flat}$  

Proof. Since we assume the the market is arbitrage-free there exists (at least) an equivalent martingale measure $\b{\mathcal{M}}^{*}$ . By Proposition 3.2.1 the discounted value process $\tilde{V}_{\varphi}$ of any self-financing strategy $\varphi$ is a $\b{\mathcal{N}}^{*}$ -martingale. So for any contingent claim $X$ with maturity $T$ and any replicating trading strategy $\varphi\in\Phi$ we have for each $t=0,1,\ldots,T$  

$$
\begin{array}{r c l l}{{\pi_{X}(t)}}&{{=}}&{{V_{\varphi}(t)=\beta(t)^{-1}\tilde{V}_{\varphi}(t)}}\ {{}}&{{}}&{{}}\ {{}}&{{=}}&{{\beta(t)^{-1}E^{*}(\tilde{V}_{\varphi}(T)|\mathcal{F}_{t})}}&{{(\mathrm{as~}\tilde{V}_{\varphi}(t)\mathrm{~is~a~}I P^{*}\mathrm{-martingale})}}\ {{}}&{{}}&{{}}\ {{}}&{{=}}&{{\beta(t)^{-1}E^{*}(\beta(T)V_{\varphi}(T)|\mathcal{F}_{t})}}&{{(\mathrm{undoing~the~discounting})}}\ {{}}&{{}}&{{}}\ {{}}&{{=}}&{{\beta(t)^{-1}E^{*}(\beta(T)X|\mathcal{F}_{t})}}&{{(\mathrm{as~}\varphi\mathrm{~is~a~replicating~strategy~for~}X).}}\end{array}
$$  

# 3.3 Complete Markets: Uniqueness of Equivalent Martingale Measures  

The last section made clear that attainable contingent claims can be priced using an equivalent martingale measure. In this section we will discuss the question of the circumstances under which all contingent claims are attainable. This would be a very desirable property of the market $\mathcal{M}$ because we would then have solved the pricing question (at least for contingent claims) completely. Since contingent claims are merely ${\mathcal{F}}_{T}$ -measurable random variables in our setting, it should be. no surprise that we can give a criterion in terms of probability measures. We start with:  

Definition 3.3.1. A market $\mathcal{M}$ is complete if every contingent claim is attainable, i.e. for every ${\mathcal{F}}_{T}$ -measurable random variable $X\in L^{0}$ there exists a replicating self-financing strategy $\varphi\in\Phi$ such that $V_{\varphi}(T)=X$  

In the case of an arbitrage-free market. $\mathcal{M}$ one can even insist on replicating nonnegative. contingent claims by an admissible strategy. $\varphi\in\Phi_{a}$ . Indeed, if $\varphi$ is self-financing and $\mathit{\Pi}\mathit{\iint}^{\mathrm{*}}$ is an equivalent martingale measure under which discounted prices. $\tilde{S}$ are $\b{\mathcal{M}}^{*}$ -martingales (such $\b{\mathcal{M}}^{*}$ exist since $\mathcal{M}$ is arbitrage-free and we can hence use the no-arbitrage theorem (Theorem 3.2.1)), $\tilde{V}_{\varphi}(t)$ is also a $\b{\mathcal{M}}^{*}$ -martingale, being the martingale transform of the martingale. $\tilde{S}$ by $\varphi$ (see Proposition 3.2.1). So  

$$
\begin{array}{r}{\tilde{V}_{\varphi}(t)=E^{*}(\tilde{V}_{\varphi}(T)|\mathcal{F}_{t})}&{{}(t=0,1,\ldots,T).}\end{array}
$$  

If $\varphi$ replicates $X$ $V_{\varphi}(T)=X\geq0$ , so discounting, $\tilde{V}_{\varphi}(T)\geq0$ , so the above equation gives $\tilde{V}_{\varphi}(t)\geq0$ for each $t$ . Thus all the values at each time $t$ are non-negative - not just the final value at time $^T-$ so $\varphi$ is admissible.  

Theorem 3.3.1 (Completeness Theorem). An arbitrage-free market $\mathcal{M}$ is complete if and.   
only if there exists a unique probability measure. $\mathit{\Pi}\mathit{\perp}\mathit{\Psi}$ equivalent to $\mathcal{W}$ under which discounted asset.   
prices are martingales.  

Proof. '-': Assume that the arbitrage-free market $\mathcal{M}$ is complete.Then for any ${\mathcal{F}}_{T}$ measurable random variable $X$ ( contingent claim), there exists an admissible (so self-financing) strategy $\varphi$ replicating $X$ $X=V_{\varphi}(T)$ . As $\varphi$ is self-financing, by Proposition 3.1.2,  

$$
\beta(T)X=\tilde{V}_{\varphi}(T)=V_{\varphi}(0)+\sum_{\tau=1}^{T}\varphi(\tau)\cdot\Delta\tilde{S}(\tau).
$$  

We know by the no-arbitrage theorem (Theorem 3.2.1) that an equivalent martingale measure $\b{\mathcal{P}}^{*}$ exists; we have to prove uniqueness. So, let $\textstyle\#_{1},\#_{2}$ be two such equivalent martingale measures. For $i=1,2$ $(\dot{V}_{\varphi}(t))_{t=0}^{T}$ is a $\boldsymbol{\mathscr{N}}_{i}$ -martingale. So,  

$$
\begin{array}{r}{E_{i}(\tilde{V}_{\varphi}(T))=I E_{i}(\tilde{V}_{\varphi}(0))=V_{\varphi}(0),}\end{array}
$$  

since the value at time zero is non-random ( $\mathcal{F}_{0}=\{\varnothing,\Omega\}$ ) and $\beta(0)=1$ . So  

$$
H_{1}(\beta(T)X)=H_{2}(\beta(T)X).
$$  

Since $X$ is arbitrary, $[E_{1},B_{2}$ have to agree on integrating all integrands. Now $E_{i}$ is expectation (i.e. integration) with respect to the measure $\boldsymbol{\mathscr{N}}_{i}$ , and measures that agree on integrating all integrands must coincide. So $I P_{1}=I P_{2}$ , giving uniqueness as required.  

'': Assume that the arbitrage-free market $\mathcal{M}$ is incomplete: then there exists a non-attainable.   
${\mathcal{F}}_{T}$ -measurable random variable $X$ (a contingent claim). By Proposition 3.1.3, we may confine   
attention to the risky assets. $S_{1},\ldots,S_{d}$ , as these suffice to tell us how to handle the numeraire $S_{0}$ Consider the following set of random variables:  

$$
\Tilde{K}:=\Bigg\{Y\in L^{0}:Y=Y_{0}+\sum_{t=1}^{T}\varphi(t)\cdot\Delta\Tilde{S}(t),Y_{0}\in I R,\varphi\mathrm{predictable}\Bigg\}.
$$  

(Recall that $Y_{0}$ is $\mathcal{F}_{0}$ -measurable and set $\varphi=((\varphi_{1}(t),\dots,\varphi_{d}(t))^{\prime})_{t=1}^{\prime}$ with predictable components.) Then by the above reasoning, the discounted value $\beta(T)X$ does not belong to $\ddot{K}$ , so $\tilde{K}$ is a proper subset of the set $L^{0}$ of all random variables on $\Omega$ (which may be identified with $\mathbb{R}^{|\Omega|}$ Let $\mathit{\Pi}\mathit{\perp}\mathit{\Psi}$ be a probability measure equivalent to $\mathcal{W}$ under which discounted prices are martingales (such $\mathit{\Pi}\mathit{\perp}\mathit{\Psi}$ exist by the no-arbitrage theorem (Theorem 3.2.1). Define the scalar product  

$$
(Z,Y)\to I E^{*}(Z Y)
$$  

on random variables on. $\Omega$ . Since $\tilde{K}$ is a proper subset, there exists a non-zero random variable $Z$ orthogonal to. $\tilde{K}$ (since $\Omega$ is finite, $\mathbb{R}^{|\Omega|}$ is Euclidean: this is just Euclidean geometry). That is,  

$$
\begin{array}{r}{E^{*}(Z Y)=0,~\forall Y\in\tilde{K}.}\end{array}
$$  

Choosing the special $Y=1\in{\tilde{K}}$ given by $\varphi_{i}(t)=0,t=1,2,\ldots,T;i=1,\ldots,d$ and $Y_{0}=1$ we find  

$$
I{E}^{\ast}(Z)=0.
$$  

Write $\|X\|_{\infty}:=\operatorname*{sup}\{|X(\omega)|:\omega\in\Omega\}$ , and define $\b{\mathcal{P}}^{**}$ by  

$$
I P^{**}(\{\omega\})=\left(1+\frac{Z(\omega)}{2\left\|Z\right\|_{\infty}}\right)I P^{*}(\{\omega\}).
$$  

By construction, $\b{\mathcal{P}}^{**}$ is equivalent to $\mathit{\Pi}\mathit{\perp}\mathit{\Psi}$ (same null sets - actually, as $\smash{\mu^{*}\sim\mathcal{P}}$ and $\mathcal{W}$ has no non-empty null sets, neither do $\mathbb{P}^{*},\mathbb{P}^{**})$ . From $\textstyle\mathcal{E}^{*}(Z)=0$ , we see that $\sum{I P^{**}(\omega)}=1$ , i.e. is a probability measure. As $Z$ is non-zero, $\b{\mathcal{P}}^{**}$ and $\b{\mathcal{M}}^{*}$ are different. Now  

$$
\begin{array}{r l}{E^{**}\left(\displaystyle\sum_{t=1}^{T}\varphi(t)\cdot\Delta\tilde{S}(t)\right)}&{=\displaystyle\sum_{\omega\in\Omega}I P^{**}(\omega)\left(\displaystyle\sum_{t=1}^{T}\varphi(t,\omega)\cdot\Delta\tilde{S}(t,\omega)\right)}\ {=\displaystyle\sum_{\omega\in\Omega}\left(1+\frac{Z(\omega)}{2\left\|Z\right\|_{\infty}}\right)P^{*}(\omega)\bigg(\displaystyle\sum_{t=1}^{T}\varphi(t,\omega)\cdot\Delta\tilde{S}(t,\omega)\bigg).}\end{array}
$$  

The '1' term on the right gives  

$$
\pi^{*}\left(\sum_{t=1}^{T}\varphi(t)\cdot\Delta\tilde{S}(t)\right),
$$  

which is zero since this is a martingale transform of the $\mathit{\Pi}\mathit{\perp}\mathit{\Psi}$ -martingale $\tilde{S}(t)$ (recall martingale transforms are by definition null at zero). The . $Z^{\gamma}$ term gives a multiple of the inner product.  

$$
(Z,\sum_{t=1}^{T}\varphi(t)\cdot\Delta\tilde{S}(t)),
$$  

which is zero as. $Z$ is ort hogonal to $\tilde{K}$ and $\begin{array}{r}{\sum_{t=1}^{T}\varphi(t)\cdot\Delta\tilde{S}(t)\in\tilde{K}}\end{array}$ . By the martingale transform   
lemma (Lemma C.4.1), $\tilde{S}(t)$ is a $\b{\mathcal{U}}^{***}$ martingale since is an arbitrary predictable process. Thus $\varphi$   
$\mathbb{\mathnormal{H}^{**}}$ is a second equivalent martingale measure, different from $\mathcal{W}$ : So incompleteness implies   
non-uniqueness of equivalent martingale measures, as required.  

# Martingale Representation.  

To say that every contingent claim can be replicated means that every. $\b{\mathcal{M}}^{*}$ -martingale (where $\mathit{\Pi}\mathit{\perp}\mathit{\Psi}$ is the risk-neutral measure, which is unique) can be written, or represented, as a martingale transform (of the discounted prices) by a replicating (perfect-hedge) trading strategy $\varphi$ .In stochasticprocess language, this says that all. $\b{\mathcal{M}}^{*}$ -martingales can be represented as martingale transforms. of discounted prices. Such martingale representation theorems hold much more generally, and are. very important. For background, see (Revuz and Yor 1991, Yor 1978)..  

# 3.4 The Cox-Ross-Rubinstein Model  

In this section we consider simple discrete-time financial market models. The development of the risk-neutral pricing formula is particularly clear in this setting since we require only elementary. mathematical methods. The link to the fundamental economic principles of the arbitrage pricing. method can be obtained equally straightforwardly. Moreover binomial models, by their very. construction, give rise to simple and efficient numerical procedures. We start with the paradigm of all binomial models - the celebrated Cox-Ross-Rubinstein model (Cox, Ross, and Rubinstein 1979).  

# 3.4.1 Model Structure  

We take $d=1$ , that is, our model consists of two basic securities. Recall that the essence of the. relative pricing theory is to take the price processes of these basic securities as given and price secondary securities in such a way that no arbitrage is possible..  

Our time horizon is. $T$ and the set of dates in our financial market model is. $t=0,1,\ldots,T$ Assume that the first of our given basic securities is a (riskless) bond or bank account $B$ , which yields a riskless rate of return $r>0$ in each time interval. $[t,t+1]$ , i.e.  

$$
B(t+1)=(1+r)B(t),B(0)=1.
$$  

So its price process is $B(t)=(1+r)^{t},\quad t=0,1,\ldots,T$ Furthermore, we have a risky asset (stock) $S$ with price process  

$$
S(t+1)=\left\{\begin{array}{l l}{(1+u)S(t)}&{\quad\mathrm{with~probability}\quad p,}\ {(1+d)S(t)}&{\quad\mathrm{with~probability}\quad1-p,}\end{array}\right.\quad t=0,1,\dots,T-1.
$$  

with $-1<d<u,S_{0}\in I R_{0}^{+}$ (see Fig. 3.4.1 below).  

![](5d2d21c17e3a7a0f17dcff64d2655ca913f6ec0e96fcf8ffe53fc1f36b8abfff.jpg)  
Figure 3.1: One-step tree diagram  

Alternatively we write this as  

$$
Z(t+1):=\frac{S(t+1)}{S(t)}-1,\quad t=0,1,\ldots,T-1.
$$  

We set up a probabilistic model by considering the $Z(t),t=1,\ldots,T$ as random variables defined on probability spaces $(\tilde{\Omega}_{t},\tilde{\mathcal{F}}_{t},\tilde{\boldsymbol{\mathit{I P}}}_{t})$ with  

$$
\begin{array}{r l}{\tilde{\Omega}_{t}}&{=\tilde{\Omega}\quad=\{d,u\},}\ {\tilde{\mathcal{F}}_{t}}&{=\tilde{\mathcal{F}}\quad=\mathcal{P}(\tilde{\Omega})=\{\emptyset,\{d\},\{u\},\tilde{\Omega}\},}\ {\tilde{P}_{t}}&{=\tilde{P}\quad\mathrm{with}\quad\tilde{P}(\{u\})=p,\tilde{P}(\{d\})=1-p,p\in(0,1).}\end{array}
$$  

On these probability spaces we define  

$$
Z(t,u)=u\mathrm{and}Z(t,d)=d,t=1,2,\ldots,T.
$$  

Our aim, of course, is to define a probability space on which we can model the basic securities $(B,S)$ . Since we can write the stock price as  

$$
S(t)=S(0)\prod_{\tau=1}^{t}(1+Z(\tau)),\:\:\:t=1,2,\ldots,T,
$$  

the above definitions suggest using as the underlying probabilistic model of the financial market the product space $(\Omega,{\mathcal{F}},I P)$ (see e.g. (Williams 1991) ch. 8), i.e.  

$$
\Omega=\tilde{\Omega}_{1}\times\ldots\times\tilde{\Omega}_{T}=\tilde{\Omega}^{T}=\{d,u\}^{T},
$$  

with each $\omega\in\Omega$ representing the successive values of $Z(t),t=1,2,\ldots,T$ . Hence each $\omega\in\Omega$ is a $T$ -tuple $\omega=(\tilde{\omega}_{1},\dots,\tilde{\omega}_{T})$ and $\tilde{\omega}_{t}\in\tilde{\Omega}=\{d,u\}$ . For the $\sigma$ -algebra we use $\mathcal{F}=\mathcal{P}(\Omega)$ and the probability measure is given by  

$$
\begin{array}{r}{I P(\{\omega\})=\tilde{I P}_{1}(\{\omega_{1}\})\times\ldots\times\tilde{I P}_{T}(\{\omega_{T}\})=\tilde{I P}(\{\omega_{1}\})\times\ldots\times\tilde{I P}(\{\omega_{T}\}).}\end{array}
$$  

The role of a product space is to model independent replication of a random experiment. The $Z(t)$ above are two-valued random variables, so can be thought of as tosses of a biased coin; we need to build a probability space on which we can model a succession of such independent tosses. Now we redefine (with a slight abuse of notation) the $Z(t),t=1,\ldots,T$ as random variables on $(\Omega,{\mathcal{F}},I P)$ as (the $t$ th projection)  

$$
Z(t,\omega)=Z(t,\omega_{t}).
$$  

Observe that by this definition (and the above construction) $Z(1),\ldots,Z(T)$ are independent and identically distributed with  

$$
I P(Z(t)=u)=p=1-I P(Z(t)=d).
$$  

To model the flow of information in the market we use the obvious filtration  

$$
\begin{array}{r c l l}{\mathcal{F}_{0}}&{=}&{\{\emptyset,\Omega\}}&{\mathrm{~(trivial~}\sigma\mathrm{-}\mathrm{field}),}\ {\mathcal{F}_{t}}&{=}&{\sigma(Z(1),\ldots,Z(t))=\sigma(S(1),\ldots,S(t)),}&\ {\mathcal{F}_{T}=\mathcal{F}}&{=}&{\mathcal{P}(\Omega)}&{\mathrm{~(class~of~all~subsets~of~}\Omega).}\end{array}
$$  

This construction emphasises again that a multi-period model can be viewed as a sequence of. single-period models. Indeed, in the Cox-Ross-Rubinstein case we use identical and independent single-period models. As we will see in the sequel this will make the construction of equivalent martingale measures relatively easy. Unfortunately we can hardly defend the assumption of independent and identically distributed price movements at each time period in practical applications.  

Remark 3.4.1. We used this example to show explicitly how to construct the underlying probability. space. Having done this in full once, we will from now on feel free to take for granted the existence of an appropriate probability space on which all relevant random variables can be defined..  

# 3.4.2 Risk-Neutral Pricing  

We now turn to the pricing of derivative assets in the Cox-Ross-Rubinstein market model. To do so we first have to discuss whether the Cox-Ross-Rubinstein model is arbitrage-free and complete.  

To answer these questions we have, according to our fundamental theorems (Theorems 3.2.1 and 3.3.1), to understand the structure of equivalent martingale measures in the Cox-Ross-Rubinstein model. In trying to do this we use (as is quite natural and customary) the bond price process $B(t)$ as numeraire.  

Our first task is to find an equivalent martingale measure $\mathbb{Q}$ such that the $Z(1),\ldots,Z(T)$ remain independent and identically distributed, i.e. a probability measure $\mathbb{Q}$ defined as a product measure via a measure $\tilde{\mathbb{Q}}$ on $(\Tilde{\Omega},\Tilde{\mathcal{F}})$ such that $\tilde{\mathbb{Q}}(\{u\})=q$ and $\tilde{\mathbb{Q}}(\{d\})=1-q$ . We have:  

Proposition 3.4.1. (i) A martingale measure $\mathbb{Q}$ for the discounted stock price. $\tilde{S}$ exists if and. only if  

$$
d<r<u.
$$  

(ii) If equation (3.8) holds true, then there is a unique such measure in $\mathcal{P}$ characterised by  

$$
q={\frac{r-d}{u-d}}.
$$  

Proof. Since. $S(t)=\tilde{S}(t)B(t)=\tilde{S}(t)(1+r)^{t}$ , we have. $Z(t+1)=S(t+1)/S(t)-1=(\tilde{S}(t+$ $1)/\tilde{S}(t))(1+r)-1$ .So, the discounted price $(\Tilde{S}(t))$ is a $\mathbb{Q}$ martingale if and only if for $t=$ $0,1,\ldots,T-1$  

$$
\begin{array}{r l}&{E^{\pmb{Q}}[\tilde{S}(t+1)|\mathcal{F}_{t}]=\tilde{S}(t)\Leftrightarrow E^{\pmb{Q}}[(\tilde{S}(t+1)/\tilde{S}(t))|\mathcal{F}_{t}]=1}\ {\Leftrightarrow}&{E^{\pmb{Q}}[\pmb{Z}(t+1)|\mathcal{F}_{t}]=r.}\end{array}
$$  

But $Z(1),\ldots,Z(T)$ are mutually independent and hence $Z(t+1)$ is independent of. ${\mathcal{F}}_{t}=\sigma(Z(1),\ldots,Z(t))$ So  

$$
r=I E^{\pmb{Q}}(Z(t+1)|\mathcal{F}_{t})=I E^{\pmb{Q}}(Z(t+1))=u q+d(1-q)
$$  

is a weighted average of $u$ and $d$ ; this can be $r$ if and only if $r\in[d,u]$ . As $\mathbb{Q}$ is to be equivalent to $\mathcal{W}$ and $\mathcal{W}$ has no non-empty null sets, $r=d,u$ are excluded and (3.8) is proved.  

To prove uniqueness and to find the value of $q$ we simply observe that under (3.8)  

$$
u\times q+d\times(1-q)=r
$$  

.as a unique solution. Solving it for $q$ leads to the above formula.  

From now on we assume that (3.8) holds true. Using the above Proposition we immediately get:  

Corollary 3.4.1. The Cox-Ross-Rubinstein model is arbitrage-free.  

Proof. By Proposition 3.4.1 there exists an equivalent martingale measure and this is by the no-. arbitrage theorem (Theorem 3.2.1) enough to guarantee that the Cox-Ross-Rubinstein model is free of arbitrage. $\llcorner$  

Uniqueness of the solution of the linear equation (4.7) under (3.8) gives completeness of the model, by the completeness theorem (Theorem 3.3.1):  

Proposition 3.4.2. The Cox-Ross-Rubinstein model is complete.  

One can translate this result - on uniqueness of the equivalent martingale measure - into. financial language. Completeness means that all contingent claims can be replicated. If we do this in the large, we can do it in the small by restriction, and conversely, we can build up our full model from its constituent components. To summarize:  

Corollary 3.4.2. The multi-period model is complete if and only if every underlying single-period model is complete.  

We can now use the risk-neutral valuation formula to price every contingent claim in the Cox-Ross-Rubinstein model.  

Proposition 3.4.3. The arbitrage price process of a contingent claim $X$ in the Cox-Ross-Rubinstein model is given by  

$$
\pi_{\boldsymbol{X}}(t)=\boldsymbol{B}(t)\boldsymbol{E}^{*}\left(\boldsymbol{X}/\boldsymbol{B}(T)|\boldsymbol{\mathcal{F}}_{t}\right)\quad\forall t=0,1,\ldots,T,
$$  

where $\mathbf{\nabla}\mu^{*}$ is the expectation operator with respect to the unique equivalent martingale measure $\b{\mathcal{P}}^{*}$ characterised by $\boldsymbol{p}^{*}=(\boldsymbol{r}-\boldsymbol{d})/(u-\boldsymbol{d})$  

Proof. This follows directly from Proposition 3.2.4 since the Cox-Ross-Rubinstein model is arbitrage free and complete.  

We now give simple formulas for pricing (and hedging) of European contingent claims $X=$ $f(S_{T})$ for suitable functions $f$ (in this simple framework all functions. $f:I R\to R$ ). We use the notation  

$$
F_{\tau}(x,p):=\sum_{j=0}^{\tau}\binom{\tau}{j}p^{j}(1-p)^{\tau-j}f\left(x(1+u)^{j}(1+d)^{\tau-j}\right)
$$  

Observe that this is just an evaluation of $f(S(j))$ along the probability-weighted paths of the price process. Accordingly, $j$ $\tau-j$ are the numbers of times. $Z(i)$ takes the two possible values. $d,u$  

Corollary 3.4.3. Consider a European contigent claim with expiry $T$ given by $X=f(S_{T})$ .The arbitrage price process $\pi_{\boldsymbol{X}}(t),t=0,1,\ldots,T$ of the contingent claim is given by (set $\tau=T-t$  

$$
\pi_{\boldsymbol{X}}(t)=(1+r)^{-\tau}F_{\tau}(S_{t},p^{*}).
$$  

Proof. Recall that  

$$
S(t)=S(0)\prod_{j=1}^{t}(1+Z(j)),\:\:\:t=1,2,\ldots,T.
$$  

By Proposition 3.4.3 the price $\Pi_{X}(t)$ of a contingent claim $X=f(S_{T})$ at time $t$ is  

$$
\begin{array}{r c l}{\pi_{X}(t)}&{=}&{(1+r)^{-(T-t)}{\cal{E}}^{*}[f(S(T))|{\mathcal{F}}_{t}]}\ &&{=}&{(1+r)^{-(T-t)}{\cal{E}}^{*}\left[f\left(S(t)\displaystyle\prod_{i=t+1}^{T}(1+Z(i))\right)\bigg|{\mathcal{F}}_{t}\right]}\ &&{=}&{(1+r)^{-(T-t)}{\cal{E}}^{*}\left[f\left(S(t)\displaystyle\prod_{i=t+1}^{T}(1+Z(i))\right)\right]}\ &{=}&{(1+r)^{-\tau}F_{\tau}(S(t),p^{*}).}\end{array}
$$  

We used the role of independence property of conditional expectations from Proposition B.5.1 in the next-to-last equality. It is applicable since $S(t)$ is $\mathbf{\mathcal{F}}_{t}$ -measurable and $Z(t+1),\ldots,Z(T)$ are independent of $\mathcal{F}_{t}$ $\llcorner$  

An immediate consequence is the pricing formula for the European call option, i.e. $X=f(S_{T})$ with $f(x)=(x-K)^{+}$  

Corollary 3.4.4. Consider a European call option with expiry $T$ and strike price. $K$ written on. (one share of) the stock $S$ . The arbitrage price process $\Pi_{C}(t),~t=0,1,\ldots,T$ of the option is given by (set $\tau=T-t$  

$$
\Pi_{C}(t)=(1+r)^{-\tau}\sum_{j=0}^{\tau}{\binom{\tau}{j}}p^{*j}(1-p^{*})^{\tau-j}(S(t)(1+u)^{j}(1+d)^{\tau-j}-K)^{+}.
$$  

For a European put option, we can either argue similarly or use put-call parity.  

# 3.4.3 Hedging  

Since the Cox-Ross-Rubinstein model is complete we can find unique hedging strategies for replicating contingent claims. Recall that this means we can find a self-financing portfolio $\varphi(t)=$ $(\varphi_{0}(t),\varphi_{1}(t))$ $\varphi$ predictable, such that the value process $V_{\varphi}(t)=\varphi_{0}(t)B(t)+\varphi_{1}(t)S(t)$ satisfies  

$$
\Pi_{X}(t)=V_{\varphi}(t),\quad{\mathrm{for~all}}t=0,1,\ldots,T.
$$  

Using the bond as numeraire we get the discounted equation  

$$
\begin{array}{r}{\tilde{\Pi}_{X}(t)=\tilde{V}_{\varphi}(t)=\varphi_{0}(t)+\varphi_{1}(t)\tilde{S}(t),\quad\mathrm{for~all}~t=0,1,\ldots,T.}\end{array}
$$  

By the pricing formula, Proposition 3.4.3, we know the arbitrage price process and using the restriction of predictability of. $\varphi$ , this leads to a unique replicating portfolio process $\varphi$ .We can compute this portfolio process at any point in time as follows. The equation $\Pi_{X}(t)=\varphi_{0}(t)+$ $\varphi_{1}(t)\tilde{S}(t)$ has to be true for each. $\omega\in\Omega$ and each $t=1,\ldots,T$ . Given such a $t$ we only can use information up to (and including) time $t-1$ to ensure that $\varphi$ is predictable. Therefore we know. $S(t-1)$ , but we only know that. $S(t)=(1+Z(t))S(t-1)$ . However, the fact that $Z(t)\in\{d,u\}$ leads to the following system of equations, which can be solved for $\varphi_{0}(t)$ and $\varphi_{1}(t)$ uniquely. Making the dependence of $\tilde{\Pi}_{X}$ on $\tilde{S}$ explicit, we have  

$$
\begin{array}{r l r}{\tilde{\Pi}_{X}(t,\tilde{S}_{t-1}(1+u))}&{=}&{\varphi_{0}(t)+\varphi_{1}(t)\tilde{S}_{t-1}(1+u),}\ {\tilde{\Pi}_{X}(t,\tilde{S}_{t-1}(1+d))}&{=}&{\varphi_{0}(t)+\varphi_{1}(t)\tilde{S}_{t-1}(1+d).}\end{array}
$$  

The solution is given by  

$$
\begin{array}{r c l}{\varphi_{0}(t)}&{=}&{\frac{\tilde{S}_{t-1}(1+u)\tilde{\Pi}_{X}(t,\tilde{S}_{t-1}(1+d))-\tilde{S}_{t-1}(1+d)\tilde{\Pi}_{X}(t,\tilde{S}_{t-1}(1+u))}{\tilde{S}_{t-1}(1+u)-\tilde{S}_{t-1}(1+d)}}\ &{=}&{\frac{(1+u)\tilde{\Pi}_{X}(t,\tilde{S}_{t-1}(1+d))-(1+d)\tilde{\Pi}_{X}(t,\tilde{S}_{t-1}(1+u))}{(u-d)}}\ &{=}&{\frac{\tilde{\Pi}_{X}(t,\tilde{S}_{t-1}(1+u))-\tilde{\Pi}_{X}(t,\tilde{S}_{t-1}(1+d))}{\tilde{S}_{t-1}(1+u)-\tilde{S}_{t-1}(1+d)}}\ &{=}&{\frac{\tilde{\Pi}_{X}(t,\tilde{S}_{t-1}(1+u))-\tilde{\Pi}_{X}(t,\tilde{S}_{t-1}(1+d))}{\tilde{S}_{t-1}(u)-\tilde{S}_{t-1}(1+d)}.}\end{array}
$$  

Observe that we only need to have information up to time $t-1$ to compute $\varphi(t)$ , hence $\varphi$ is predictable. We make this rather abstract construction more transparent by constructing the hedge portfolio for the European contingent claims.  

Proposition 3.4.4. The perfect hedging strategy $\varphi=\left(\varphi_{0},\varphi_{1}\right)$ replicating the European contingent.   
claim $f(S_{T})$ with time of expiry. $T$ is given by (again using. $\tau=T-t$  

$$
\begin{array}{r c l}{{\varphi_{1}(t)}}&{{=}}&{{\displaystyle\frac{(1+r)^{-\tau}\left(F_{\tau}\left(S_{t-1}\left(1+u\right),p^{*}\right)-F_{\tau}\left(S_{t-1}\left(1+d\right),p^{*}\right)\right)}{S_{t-1}(u-d)},}}\ {{}}&{{}}&{{}}\ {{\varphi_{0}(t)}}&{{=}}&{{\displaystyle\frac{(1+u)F_{\tau}\left(S_{t-1}\left(1+d\right),p^{*}\right)-(1+d)F_{\tau}\left(S_{t-1}\left(1+u\right),p^{*}\right)}{(u-d)(1+r)^{T}}.}}\end{array}
$$  

Proof. $(1+r)^{-\tau}F_{\tau}(S_{t},p^{*})$ must be the value of the portfolio at time $t$ if the strategy $\varphi=(\varphi(t))$ replicates the claim:  

$$
\begin{array}{r}{\varphi_{0}(t)(1+r)^{t}+\varphi_{1}(t)S(t)=(1+r)^{-\tau}F_{\tau}(S_{t},p^{\ast}).}\end{array}
$$  

Now $S(t)=S(t-1)(1+Z(t))=S(t-1)(1+u)$ or $S(t-1)(1+d)$ , so:  

$$
\begin{array}{r l}&{\varphi_{0}(t)(1+r)^{t}+\varphi_{1}(t)S(t-1)(1+u)=(1+r)^{-\tau}F_{\tau}(S_{t-1}(1+u),p^{\ast}),}\ &{}\ &{\varphi_{0}(t)(1+r)^{t}+\varphi_{1}(t)S(t-1)(1+d)=(1+r)^{-\tau}F_{\tau}(S_{t-1}(1+d),p^{\ast}).}\end{array}
$$  

Subtract:  

$$
)(u-d)=(1+r)^{-\tau}\left(F_{\tau}(S_{t-1}(1+u),p^{*})-F_{\tau}(S_{t}
$$  

So $\varphi_{1}(t)$ in fact depends only on. $S(t-1)$ , thus yielding the predictability of $\varphi$ , and  

$$
\varphi_{1}(t)=\frac{(1+r)^{-\tau}\left(F_{\tau}(S_{t-1}(1+u),p^{*})-F_{\tau}(S_{t-1}(1+d),p^{*})\right)}{S(t-1)(u-d)}.
$$  

Jsing any of the equations in the above system and solving for $\varphi_{0}(t)$ completes the proof.  

To write the corresponding result for the European call, we use the following notation.  

$$
C(\tau,x):=\sum_{j=0}^{\tau}\binom{\tau}{j}p^{*j}(1-p^{*})^{\tau-j}(x(1+u)^{j}(1+d)^{\tau-j}-K)^{+}.
$$  

Then $(1+r)^{-\tau}C(\tau,x)$ is value of the call at time $t$ (with time to expiry $\tau$ ) given that $S(t)=x$  

Corollary 3.4.5. The perfect hedging strategy $\varphi=\left(\varphi_{0},\varphi_{1}\right)$ replicating the European call option with time of expiry $T$ and strike price $K$ is given by  

$$
\begin{array}{r c l}{{\varphi_{1}(t)}}&{{=}}&{{\displaystyle\frac{(1+r)^{-\tau}\left(C(\tau,S_{t-1}(1+u))-C(\tau,S_{t-1}(1+d))\right)}{S_{t-1}(u-d)},}}\ {{}}&{{}}&{{}}\ {{\varphi_{0}(t)}}&{{=}}&{{\displaystyle\frac{(1+u)C(\tau,S_{t-1}(1+d))-(1+d)C(\tau,S_{t-1}(1+u))}{(u-d)(1+r)^{T}}.}}\end{array}
$$  

Notice that the numerator in the equation for $\varphi_{1}(t)$ is the difference of two values of $C(\tau,x)$ with the larger value of $x$ in the first term (recall $u>d$ ). When the payoff function $C(\tau,x)$ is an increasing function of $x$ , as for the European call option considered here, this is non-negative. In this case, the Proposition gives $\varphi_{1}(t)\geq0$ : the replicating strategy does not involve short-selling. We record this as:  

Corollary 3.4.6. When the payoff function is a non-decreasing function of the asset price. $S(t)$   
the perfect-hedging strategy replicating the claim does not involve short-selling of the risky asset.  

If we do not use the pricing formula from Proposition 3.4.3 (i.e. the information on the price. process), but only the final values of the option (or more generally of a contingent claim) we are still able to compute the arbitrage price and to construct the hedging portfolio by backward induction. In essence this is again only applying the one-period calculations for each time interval and each state of the world. We outline this procedure for the European call starting with the last period $[T-1,T]$ . We have to choose a replicating portfolio. $\varphi(T)=(\varphi_{0}(T),\varphi_{1}(T)$ based on the information available at time $T-1$ (and so ${\mathcal{F}}_{T-1}$ -measurable). So for each $\omega\in\Omega$ the following equation has to hold:  

$$
\pi_{X}(T,\omega)=\varphi_{0}(T,\omega)B(T,\omega)+\varphi_{1}(T,\omega)S(T,\omega).
$$  

Given the information ${\mathcal{F}}_{T-1}$ we know all but the last coordinate of $\omega$ , and this gives rise to two equations (with the same notation as above):  

$$
\begin{array}{r l r}{\pi_{X}(T,S_{T-1}(1+u))}&{=}&{\varphi_{0}(T)(1+r)^{T}+\varphi_{1}(T)S_{T-1}(1+u),}\ &{}&\ {\pi_{X}(T,S_{T-1}(1+d))}&{=}&{\varphi_{0}(T)(1+r)^{T}+\varphi_{1}(T)S_{T-1}(1+d).}\end{array}
$$  

Since we know the payoff structure of the contingent claim time $T$ , for example in case of a. European call. $\pi_{X}(T,S_{T-1}(1+u))=((1+u)S_{T-1}-K)^{+}$ and $\pi_{X}(T,S_{T-1}(1+d))=((1+$ $d)S_{T-1}-K)^{+}$ , we can solve the above system and obtain.  

$$
\begin{array}{l c l}{{\varphi_{0}(T)}}&{{=}}&{{\frac{(1+u)\Pi_{X}\left(T,S_{T-1}(1+d)\right)-(1+d)\Pi_{X}\left(T,S_{T-1}(1+u)\right)}{(u-d)(1+r)}}}\ {{}}&{{}}&{{}}\ {{\varphi_{1}(t)}}&{{=}}&{{\frac{\Pi_{X}\left(T,S_{T-1}(1+u)\right)-\Pi_{X}\left(T,S_{T-1}(1+d)\right)}{S_{T-1}(u-d)}.}}\end{array}
$$  

Using this portfolio one can compute the arbitrage price of the contingent claim at time $T-1$ given that the current asset price is $S_{T-1}$ as  

$$
\pi_{X}(T-1,S_{T-1})=\varphi_{0}(T,S_{T-1})(1+r)^{T-1}+\varphi_{1}(T,S_{T-1})S(T-1).
$$  

Now the arbitrage prices at time. $T-1$ are known and one can repeat the procedure to successively compute the prices at $T-2,\ldots,1,0$  

The advantage of our risk-neutral pricing procedure over this approach is that we have a single formula for the price of the contingent claim at all times. $t$ at once, and don't have to go to a. backwards induction only to compute a price at a special time. $t$  

# 3.5 Binomial Approximations  

Suppose we observe financial assets during a continuous time period. $[0,T]$ . To construct a stochastic model of the price processes of these assets (to, e.g. value contingent claims) one basically has two choices: one could model the processes as continuous-time stochastic processes (for which the theory of stochastic calculus is needed) or one could construct a sequence of discrete-time models in which the continuous-time price processes are approximated by discrete-time stochastic processes in a suitable sense. We describe the the second approach now by examining the asymptotic. properties of a sequence of Cox-Ross-Rubinstein models..  

# 3.5.1 Model Structure  

We assume that all random variables subsequently introduced are defined on a suitable probability space $(\Omega,{\mathcal{F}},I P)$ . We want to model two assets, a riskless bond. $B$ and a risky stock. $S$ , which we now observe in a continuous-time interval. $[0,T]$ . To transfer the continuous-time framework into a binomial structure we make the following adjustments. Looking at the. $n$ th Cox-Ross-Rubinstein. model in our sequence, there is a prespecified number $k_{n}$ of trading dates. We set. $\Delta_{n}=T/k_{n}$ and divide $[0,T]$ in $k_{n}$ subintervals of length. $\Delta_{n}$ , namely $I_{j}=[j\Delta_{n},(j+1)\Delta_{n}]$ $j=0,\ldots,k_{n}-1$ . We suppose that trading occurs only at the equidistant time points $t_{n,j}=j\Delta_{n}$ $j=0,\ldots,k_{n}-1$ . We fix $r_{n}$ as the riskless interest rate over each interval. $I_{j}$ , and hence the bond process (in the $n$ th model) is given by.  

$$
B(t_{n,j})=(1+r_{n})^{j},\quad j=0,\ldots,k_{n}.
$$  

In the continuous-time model we compound continuously with spot rate $r\geq0$ and hence the bond. price process $B(t)$ is given by $\boldsymbol B(t)=\boldsymbol e^{r t}$ . In order to approximate this process in the discrete-time framework, we choose. $r_{n}$ such that  

$$
1+r_{n}=e^{r\Delta_{n}}.
$$  

With this choice we have for any $j=0,\ldots,k_{n}$ that $(1+r_{n})^{j}=\exp(r j\Delta_{n})=\exp(r t_{n,j})$ . Thus we have approximated the bond process exactly at the time points of the discrete model.  

Next we model the one-period returns $S(t_{n,j+1})/S(t_{n,j})$ of the stock by a family of random variables $Z_{n,i};i=1,\ldots,k_{n}$ taking values $\{d_{n},u_{n}\}$ with  

$$
I P(Z_{n,i}=u_{n})=p_{n}=1-I P(Z_{n,i}=d_{n})
$$  

for some $p_{n}\in(0,1)$ (which we specify later). With these $Z_{n,j}$ we model the stock price process $S_{n}$ in the $n$ th Cox-Ross-Rubinstein model as  

$$
S_{n}(t_{n,j})=S_{n}(0)\prod_{i=1}^{j}\left(1+Z_{n,i}\right),\quad j=0,1,\ldots,k_{n}.
$$  

With the specification of the one-period returns we get a complete description of the discrete. dynamics of the stock price process in each Cox-Ross-Rubinstein model. We call such a finite sequence $Z_{n}~=~(Z_{n,i})_{i=1}^{k_{n}}$ a lattice or tree. The parameters $u_{n},d_{n},p_{n},k_{n}$ differ from lattice to lattice, but remain constant throughout a specific lattice. In the triangular array. $(Z_{n,i}),~i=$ $1,\ldots,k_{n};~n=1,2,\ldots$ we assume that the random variables are row-wise independent (but we. allow dependence between rows). The approximation of a continuous-time setting by a sequence. of lattices is called the lattice approach.  

It is important to stress that for each $n$ we get a different discrete stock price process $S_{n}(t)$ and that in general these processes do not coincide on common time points (and are also different from the price process $S(t)$  

Turning back to a specific Cox-Ross-Rubinstein model, we now have as in. $\S3.4$ a discretetime bond and stock price process. We want arbitrage-free financial market models and therefore have to choose the parameters $u_{n},d_{n},p_{n}$ accordingly. An arbitrage-free financial market model is.  

guaranteed by the existence of an equivalent martingale measure, and by Proposition 3.4.1 (i) the (necessary and) sufficient condition for that is  

$$
d_{n}<r_{n}<u_{n}.
$$  

The risk-neutrality approach implies that the expected (under an equivalent martingale measure) one-period return must equal the one-period return of the riskless bond and hence we get (see Proposition 3.4.1(ii)  

$$
p_{n}^{*}=\frac{r_{n}-d_{n}}{u_{n}-d_{n}}.
$$  

So the only parameters to choose freely in the model are $u_{n}$ and $d_{n}$ .In the next sections we.   
consider some special choices.  

# 3.5.2 The Black-Scholes Option Pricing Formula  

We now choose the parameters in the above lattice approach in a special way. Assuming the risk-free rate of interest $r$ as given, we have by (3.13) $1+r_{n}=e^{r\Delta_{n}};$ and the remaining degrees of freedom are resolved by choosing $u_{n}$ and $d_{n}$ . We use the following choice:  

$$
1+u_{n}=e^{\sigma\sqrt{\Delta_{n}}},\quad\mathrm{and}\quad1+d_{n}=(1+u_{n})^{-1}=e^{-\sigma\sqrt{\Delta_{n}}}.
$$  

By condition (3.14) the risk-neutral probabilities for the corresponding single period models are given by  

$$
p_{n}^{*}={\frac{r_{n}-d_{n}}{u_{n}-d_{n}}}={\frac{e^{r\Delta_{n}}-e^{-\sigma{\sqrt{\Delta_{n}}}}}{e^{\sigma{\sqrt{\Delta_{n}}}}-e^{-\sigma{\sqrt{\Delta_{n}}}}}}.
$$  

We can now price contingent claims in each Cox-Ross-Rubinstein model using the expectation operator with respect to the (unique) equivalent martingale measure characterised by the probabilities $\boldsymbol{p}_{n}^{*}$ (compare 3.4.2). In particular we can compute the price $\Pi_{C}(t)$ at time $t$ of a European call on the stock $S$ with strike $K$ and expiry $T$ by formula (3.12) of Corollary 3.4.4.Let us reformulate this formula slightly. We define  

$$
a_{n}=\operatorname*{min}{\big\{}j\in I N_{0}|S(0)(1+u_{n})^{j}(1+d_{n})^{k_{n}-j}>K{\big\}}.
$$  

Then we can rewrite the pricing formula (3.12) for $t=0$ in the setting of the $n$ th Cox-RossRubinstein model as  

$$
\begin{array}{l c l}{{\Pi_{C}(0)}}&{{=}}&{{(1+r_{n})^{-k_{n}}\displaystyle\sum_{j=a_{n}}^{k_{n}}{\binom{k_{n}}{j}}p_{n}^{*j}(1-p_{n}^{*})^{k_{n}-j}(S(0)(1+u_{n})^{j}(1+d_{n})^{k_{n}-j}-K)}}\ {{}}&{{=}}&{{S(0)\left[\displaystyle\sum_{j=a_{n}}^{k_{n}}{\binom{k_{n}}{j}}\left(\displaystyle\frac{p_{n}^{*}(1+u_{n})}{1+r_{n}}\right)^{j}\left(\displaystyle\frac{(1-p_{n}^{*})(1+d_{n})}{1+r_{n}}\right)^{k_{n}-j}\right]}}\ {{}}&{{}}&{{-(1+r_{n})^{-k_{n}}K\displaystyle\left[\displaystyle\sum_{j=a_{n}}^{k_{n}}{\binom{k_{n}}{j}}p_{n}^{*j}(1-p_{n}^{*})^{k_{n}-j}\right].}}\end{array}
$$  

Denoting the binomial cumulative distribution function with parameters $(n,p)$ as $B^{n,p}(.)$ we see that the second bracketed expression is just  

$$
\begin{array}{r}{\bar{B}^{k_{n},p_{n}^{*}}(a_{n})=1-B^{k_{n},p_{n}^{*}}(a_{n}).}\end{array}
$$  

Also the first bracketed expression is $\bar{B}^{k_{n},\hat{p}_{n}}(a_{n})$ with  

$$
\hat{p}_{n}=\frac{p_{n}^{*}(1+u_{n})}{1+r_{n}}.
$$  

That $\hat{p}_{n}$ is indeed a probability can be shown straightforwardly. Using this notation we have in the $n$ th Cox-Ross-Rubinstein model for the price of a European call at time $t=0$ the following formula:  

$$
\Pi_{C}^{(n)}(0)=S_{n}(0)\bar{B}^{k_{n},\hat{p}_{n}}(a_{n})-K(1+r_{n})^{-k_{n}}\bar{B}^{k_{n},p_{n}^{*}}(a_{n}).
$$  

(We stress again that the underlying is $S_{n}(t)$ , dependent on $n$ , but $S_{n}(0)=S(0)$ for all $n$ .) We now look at the limit of this expression.  

Proposition 3.5.1. We have the following limit relation:  

$$
\operatorname*{lim}_{n\to\infty}\Pi_{C}^{(n)}(0)=\Pi_{C}^{B S}(0)
$$  

with $\Pi_{C}^{B S}(0)$ given by the Black-Scholes formula (we use $S=S(0)$ to ease the notation)  

$$
\Pi_{C}^{B S}(0)=S N(d_{1}(S,T))-K e^{-r T}N(d_{2}(S,T)).
$$  

The functions $d_{1}(s,t)$ and $d_{2}(s,t)$ are given by  

$$
\begin{array}{l c l}{{d_{1}(s,t)}}&{{=}}&{{{\displaystyle\frac{\log(s/K)+(r+\frac{\sigma^{2}}{2})t}{\sigma\sqrt{t}}},}}\ {{}}&{{}}&{{}}\ {{d_{2}(s,t)}}&{{=}}&{{d_{1}(s,t)-\sigma\sqrt{t}=\displaystyle\frac{\log(s/K)+(r-\frac{\sigma^{2}}{2})t}{\sigma\sqrt{t}}}}\end{array}
$$  

and $N(.)$ is the standard normal cumulative distribution function.  

Proof. Since $S_{n}(0)=S$ (say) all we have to do to prove the proposition is to show  

$$
\begin{array}{r l r}{\displaystyle\operatorname*{lim}_{n\rightarrow\infty}\bar{B}^{k_{n},\hat{p}_{n}}(a_{n})}&{=}&{N(d_{1}(S,T)),}\ {\displaystyle\operatorname*{lim}_{n\rightarrow\infty}\bar{B}^{k_{n},p_{n}^{*}}(a_{n})}&{=}&{N(d_{2}(S,T)).}\end{array}
$$  

hese statements involve the convergence of distribution functions.  

To show (i) we interpret  

$$
\bar{B}^{k_{n},\hat{p}_{n}}(a_{n})=I P\left(a_{n}\leq Y_{n}\leq k_{n}\right)
$$  

with $\left(Y_{n}\right)$ a sequence of random variables distributed according to the binomial law with parameters $(k_{n},\hat{p}_{n})$ . We normalise $Y_{n}$ to  

$$
\tilde{Y}_{n}=\frac{Y_{n}-\mathit{{R P}}(Y_{n})}{\sqrt{V a r(Y_{n})}}=\frac{Y_{n}-k_{n}\hat{p}_{n}}{\sqrt{k_{n}\hat{p}_{n}(1-\hat{p}_{n})}}=\frac{\overset{k_{n}}{\sum}(B_{j,n}-\hat{p}_{n})}{\sqrt{k_{n}\hat{p}_{n}(1-\hat{p}_{n})}},
$$  

where $B_{j,n},j=1,\ldots,k_{n}$ $n=1,2,\ldots$ are row-wise independent Bernoulli random variables with parameter $\hat{p}_{n}$ . Now using the central limit theorem we know that for $\alpha_{n}\rightarrow\alpha,\beta_{n}\rightarrow\beta$ we have  

$$
\operatorname*{lim}_{n\to\infty}P(\alpha_{n}\leq\tilde{Y}_{n}\leq\beta_{n})=N(\beta)-N(\alpha).
$$  

By definition we have  

$$
{I P}\left(a_{n}\leq Y_{n}\leq k_{n}\right)=I P\left(\alpha_{n}\leq{\tilde{Y}}_{n}\leq\beta_{n}\right)
$$  

with  

$$
\alpha_{n}=\frac{a_{n}-k_{n}\hat{p}_{n}}{\sqrt{k_{n}\hat{p}_{n}(1-\hat{p}_{n})}}~\mathrm{and}~\beta_{n}=\frac{k_{n}(1-\hat{p}_{n})}{\sqrt{k_{n}\hat{p}_{n}(1-\hat{p}_{n})}}.
$$  

Using the following limiting relations:  

$$
\operatorname*{lim}_{n\to\infty}\hat{p}_{n}=\frac{1}{2},\quad\operatorname*{lim}_{n\to\infty}k_{n}(1-2\hat{p}_{n})\sqrt{\Delta_{n}}=-T\left(\frac{r}{\sigma}+\frac{\sigma}{2}\right),
$$  

and the defining relation for $a_{n}$ , formula (3.15), we get  

$$
\begin{array}{r c l}{\displaystyle\operatorname*{lim}_{n\to\infty}\alpha_{n}}&{=}&{\displaystyle\operatorname*{lim}_{n\to\infty}\frac{\frac{\log(K/S)+k_{n}\sigma\sqrt{\Delta_{n}}}{2\sigma\sqrt{\Delta_{n}}}-k_{n}\hat{p}_{n}}{\sqrt{k_{n}\hat{p}_{n}(1-\hat{p}_{n})}}}\ &{=}&{\displaystyle\operatorname*{lim}_{n\to\infty}\frac{\log(K/S)+\sigma k_{n}\sqrt{\Delta_{n}}(1-2\hat{p}_{n})}{2\sigma\sqrt{k_{n}\Delta_{n}\hat{p}_{n}(1-\hat{p}_{n})}}}\ &{=}&{\displaystyle\frac{\log(K/S)-(r+\frac{\sigma^{2}}{2})T}{\sigma\sqrt{T}}=-d_{1}(S,T).}\end{array}
$$  

Furthermore we have  

$$
\operatorname*{lim}_{n\to\infty}\beta_{n}=\operatorname*{lim}_{n\to\infty}\sqrt{k_{n}\hat{p}_{n}^{-1}(1-\hat{p}_{n})}=+\infty.
$$  

So $N(\beta_{n})\to1,N(\alpha_{n})\to N(-d_{1})=1-N(d_{1})$ , completing the proof of (i).  

To prove (ii) we can argue in very much the same way and arrive at parameters $\alpha_{n}^{*}$ and $\beta_{n}^{*}$ with $\hat{p}_{n}$ replaced by $\boldsymbol{p}_{n}^{*}$ . Using the following limiting relations:  

$$
\operatorname*{lim}_{n\to\infty}p_{n}^{*}=\frac{1}{2},\quad\operatorname*{lim}_{n\to\infty}k_{n}(1-2p_{n}^{*})\sqrt{\Delta_{n}}=T\Big(\frac{\sigma}{2}-\frac{r}{\sigma}\Big),
$$  

we get  

$$
\begin{array}{r l r}{\underset{n\rightarrow\infty}{\operatorname*{lim}}\alpha_{n}^{*}}&{=}&{\underset{n\rightarrow\infty}{\operatorname*{lim}}\frac{\log\left(K/S\right)+\sigma n\sqrt{\Delta_{n}}(1-2p_{n}^{*})}{2\sigma\sqrt{n\Delta_{n}p_{n}^{*}(1-p_{n}^{*})}}}\ &{=}&{\frac{\log\left(K/S\right)-(r-\frac{\sigma^{2}}{2})T}{\sigma\sqrt{T}}=-d_{2}(s,T).}\end{array}
$$  

For the upper limit we get  

$$
\operatorname*{lim}_{n\to\infty}\beta_{n}^{*}=\operatorname*{lim}_{n\to\infty}\sqrt{k_{n}(p_{n}^{*})^{-1}(1-p_{n}^{*})}=+\infty,
$$  

whence (ii) follows similarly.  

By the above proposition we have derived the classical Black-Scholes European call option valuation formula as an asymptotic limit of option prices in a sequence of Cox-Ross-Rubinstein. type models with a special choice of parameters. We will therefore call these models discrete. Black-Scholes models. Let us mention here that in the continuous-time Black-Scholes model the dynamics of the (stochastic) stock price process $S(t)$ are modelled by a geometric Brownian motion (or exponential Wiener process). The sample paths of this stochastic price process are almost all continuous and the probability law of $S(t)$ at any time $t$ is lognormal. In particular the time $T$ distribution of $\log\{S(T)/S(0)\}$ is $N(T\mu,T\sigma^{2})$ .Looking back at the construction of our sequence of Cox-Ross-Rubinstein models we see that  

$$
\log{\frac{S_{n}(T)}{S(0)}}=\sum_{i=1}^{k_{n}}\log(1+Z_{n,i}),
$$  

with $\log(Z_{n,i})$ Bernoulli random variables with  

$$
{\cal P}(\log(1+Z_{n,i})=\sigma\sqrt{\Delta_{n}})=p_{n}=1-{\cal P}(\log(1+Z_{n,i})=-\sigma\sqrt{\Delta_{n}}).
$$  

$\log{\frac{S_{n}(T)}{S(0)}}$ Doing similar calculations as in the above proposition we can compute the normalising constants and get  

$$
\operatorname*{lim}_{n\to\infty}\log\frac{S_{n}(T)}{S(0)}\sim N(T(r-\sigma^{2}/2),T\sigma^{2}),
$$  

i.e. $\frac{S_{n}(T)}{S(0)}$ is in the limit lognormally distributed.  

# 3.6 American Options  

Consider a general multi-period framework. The holder of an American derivative security can 'exercise' in any period $t$ and receive payment $f(S_{t})$ (or more general a non-negative payment. $f_{t}$ In order to hedge such an option, we want to construct a self-financing trading strategy. $\varphi_{t}$ such that for the corresponding value process $V_{\varphi}(t)$  

$$
\begin{array}{r c l}{{V_{\varphi}(0)}}&{{=}}&{{x\mathrm{initialcapital}}}\ {{V_{\varphi}(t)}}&{{\geq}}&{{f(S_{t}),\forall t.}}\end{array}
$$  

Such a hedging portfolio is minimal, if for a stopping time $\tau$  

$$
V_{\varphi}(\tau)=f(S_{\tau}).
$$  

Our aim in the following will be to discuss existence and construction of such a stopping time.  

# 3.6.1 Stopping Times, Optional Stopping and Snell Envelopes  

A random variable $\tau$ taking values in $\{0,1,2,...;{+}\infty\}$ is called a stopping time (or optional time) if  

$$
\{\tau\leq n\}=\{\omega:\tau(\omega)\leq n\}\in\mathscr{F}_{n}\mathrm{~~}\forall\mathrm{~}n\leq\infty.
$$  

From $\{\tau=n\}=\{\tau\leq n\}\setminus\{\tau\leq n-1\}$ and $\begin{array}{r}{\{\tau\leq n\}=\bigcup_{k\leq n}\{\tau=k\}}\end{array}$ , we see the equivalent characterisation  

$$
\{\tau=n\}\in\mathcal{F}_{n}\forall n\leq\infty.
$$  

Call a stopping time $\tau$ bounded, if there is a constant $K$ such that ${\cal I P}(\tau\leq K)=1$ .(Since $\tau(\omega)\le K$ for some constant $K$ and all $\omega\in\Omega\setminus N$ with $\textstyle{\mathcal{P}}(N)=0$ all identities hold true except on a null set, i.e. almost surely.)  

Example. Suppose ( $X_{n}$ ) is an adapted process and we are interested in the time of first entry of $X$ into a Borel set $B$ (typically one might have $B=[c,\infty)$  

$$
\tau=\operatorname*{inf}\{n\geq0:X_{n}\in B\}.
$$  

Now $\begin{array}{r}{\{\tau\leq n\}=\bigcup_{k\leq n}\{X_{k}\in B\}\in\mathcal{F}_{n}}\end{array}$ and $\tau=\infty$ if $X$ never enters $B$ . Thus $\tau$ is a stopping time.  

Intuitively, think of $\tau$ as a time at which you decide to quit a gambling game: whether or not you quit at time $n$ depends only on the history up to and including time $n$ NOT the future. Thus stopping times model gambling and other situations where there is no foreknowledge, or prescience of the future; in particular, in the financial context, where there is no insider trading. Furthermore since a gambler cannot cheat the system the expectation of his hypothetical fortune (playing with unit stake) should equal his initial fortune.  

Theorem 3.6.1 (Doob's Stopping-Time Principle (STP)). Let $\tau$ be a bounded stopping.   
time and $X=\left(X_{n}\right)$ a martingale. Then $X_{\tau}$ is integrable, and.  

$$
\begin{array}{r}{{\cal I E}(X_{\tau})={\cal I E}(X_{0}).}\end{array}
$$  

Proof. Assume $\tau(\omega)\leq K$ for all $\omega$ , where we can take $K$ to be an integer and write  

$$
X_{\tau(\omega)}(\omega)=\sum_{k=0}^{\infty}X_{k}(\omega)\mathbf{1}_{\{\tau(\omega)=k\}}=\sum_{k=0}^{K}X_{k}(\omega)\mathbf{1}_{\{\tau(\omega)=k\}}
$$  

Thus using successively the linearity of the expectation operator, the martingale property of $X$ the ${\mathcal F}_{k}$ -measurability of $\{\tau=k\}$ and finally the definition of conditional expectation, we get.  

$$
\begin{array}{r c l}{{\displaystyle\mathbb{E}(X_{\tau})}}&{{=}}&{{\displaystyle\mathbb{E}\left[\sum_{k=0}^{K}X_{k}\mathbf{1}_{\left\{\tau=k\right\}}\right]=\sum_{k=0}^{K}{\cal E}\left[X_{k}\mathbf{1}_{\left\{\tau=k\right\}}\right]}}\ {{}}&{{=}}&{{\displaystyle\sum_{k=0}^{K}{\cal E}\left[{\cal E}(X_{K}|{\mathcal F}_{k})\mathbf{1}_{\left\{\tau=k\right\}}\right]=\sum_{k=0}^{K}{\cal E}\left[X_{K}\mathbf{1}_{\left\{\tau=k\right\}}\right]}}\ {{}}&{{=}}&{{\displaystyle{\cal E}\left[X_{K}\sum_{k=0}^{K}\mathbf{1}_{\left\{\tau=k\right\}}\right]={\cal E}(X_{K})={\cal E}(X_{0}).}}\end{array}
$$  

The stopping time principle holds also true if $X=\left(X_{n}\right)$ is a supermartingale; then the conclusion is  

$$
\begin{array}{r}{I E X_{\tau}\leq I E X_{0}.}\end{array}
$$  

Also, alternative conditions such as  

(i) $X=\left(X_{n}\right)$ is bounded $\langle|X_{n}(\omega)|\leq L$ for some $L$ and all $n,\omega$ (ii) $I E\tau<\infty$ and $(X_{n}-X_{n-1})$ is bounded; suffice for the proof of the stopping time principle.  

The stopping time principle is important in many areas, such as sequential analysis in statistics. We turn in the next section to related ideas specific to the gambling/financial context..  

We now wish to create the concept of the. $\sigma$ -algebra of events observable up to a stopping time. $\tau$ , in analogy to the. $\sigma$ -algebra ${\mathcal{F}}_{n}$ which represents the events observable up to time $n$  

Definition 3.6.1. Let $\tau$ be a stopping time. The stopping time $\sigma-$ algebra ${\mathcal{F}}_{\tau}$ is defined to be  

$$
\mathcal{F}_{\tau}=\{A\in\mathcal{F}:A\cap\{\tau\leq n\}\in\mathcal{F}_{n},~f o r~a l l~n\}.
$$  

Proposition 3.6.1. For $\tau$ a stopping time, ${\mathcal{F}}_{\tau}$ is a - algebra.  

Proof. We simply have to check the defining properties. Clearly $\Omega,\emptyset$ are in ${\mathcal{F}}_{\tau}$ .Also for $A\in\mathcal{F}_{\tau}$ we find  

$$
A^{c}\cap\left\{\tau\leq n\right\}=\left\{\tau\leq n\right\}\setminus\left(A\cap\left\{\tau\leq n\right\}\right)\in{\mathcal{F}}_{n},
$$  

thus $A^{c}\in\mathcal{F}_{\tau}$ . Finally, for a family $A_{i}\in{\mathcal{F}}_{\tau},i=1,2,...$ we have  

$$
\left(\bigcup_{i=1}^{\infty}A_{i}\right)\cap\left\{\tau\leq n\right\}=\bigcup_{i=1}^{\infty}\left(A_{i}\cap\left\{\tau\leq n\right\}\right)\in\mathcal{F}_{n},
$$  

showing $\textstyle\bigcup_{i=1}^{\infty}A_{i}\in{\mathcal{F}}_{\tau}$  

Proposition 3.6.2. Let $\sigma,\tau$ be stopping times with $\sigma\leq\tau$ .Then ${\mathcal{F}}_{\sigma}\subseteq{\mathcal{F}}_{\tau}$  

Proof. Since $\sigma\leq\tau$ we have $\{\tau\leq n\}\subseteq\{\sigma\leq n\}$ . So for $A\in{\mathcal{F}}_{\sigma}$ we get  

$$
A\cap\left\{\tau\leq n\right\}=\left(A\cap\left\{\sigma\leq n\right\}\right)\cap\left\{\tau\leq n\right\}\in\mathcal{F}_{n},
$$  

since $(.)\in\mathcal{F}_{n}$ as $A\in{\mathcal{F}}_{\sigma}$ . So $A\in\mathcal{F}_{\tau}$  

Proposition 3.6.3. For any adapted sequence of random variables $X=\left(X_{n}\right)$ and a.s.finite stopping time $\tau$ , define  

$$
X_{\tau}=\sum_{n=0}^{\infty}X_{n}\mathbf{1}_{\{\tau=n\}}.
$$  

Then $X_{\tau}$ is ${\mathcal{F}}_{\tau}$ -measurable.  

Proof. Let $B$ be a Borel set. We need to show $\{X_{\tau}\in B\}\in\mathcal{F}_{\tau}$ . Now using the fact that on the set $\{\tau=k\}$ we have $X_{\tau}=X_{k}$ , we find  

$$
\{X_{\tau}\in B\}\cap\{\tau\leq n\}=\bigcup_{k=1}^{n}\{X_{\tau}\in B\}\cap\{\tau=k\}=\bigcup_{k=1}^{n}\{X_{k}\in B\}\cap\{\tau=k\}.
$$  

Now sets $\left\{X_{k}\in B\right\}\cap\left\{\tau=k\right\}\in\mathcal{F}_{k}\subseteq\mathcal{F}_{n}$ , and the result follows.  

We are now in position to obtain an important extension of the Stopping-Time Principle, Theorem 3.6.1.  

Theorem 3.6.2 (Doob's Optional-Sampling Theorem, OST). Let $X=\left(X_{n}\right)$ be a martingale and let $\sigma,\tau$ be bounded stopping times with. $\sigma\leq\tau$ .Then  

$$
I E\left[X_{\tau}|\mathcal{F}_{\sigma}\right]=X_{\sigma}
$$  

and thus $H(X_{\tau})=I E(X_{\sigma})$  

Proof. First observe that $X_{\tau}$ and $X_{\sigma}$ are integrable (use the sum representation and the fact that $\tau$ is bounded by an integer. $K$ ) and $X_{\sigma}$ is ${\mathcal{F}}_{\sigma}$ -measurable by Proposition 3.6.3. So it only. remains to prove that  

$$
E({\bf1}_{A}X_{\tau})=E({\bf1}_{A}X_{\sigma})~\forall A\in\mathcal{F}_{\sigma}.
$$  

For any such fixed $A\in{\mathcal{F}}_{\sigma}$ , define. $\rho$ by  

$$
\boldsymbol{\rho}(\omega)=\boldsymbol{\sigma}(\omega)\mathbf{1}_{A}(\omega)+\boldsymbol{\tau}(\omega)\mathbf{1}_{A^{c}}(\omega).
$$  

Since  

$$
\{\rho\leq n\}=(A\cap\{\sigma\leq n\})\cup(A^{c}\cap\{\tau\leq n\})\in\mathcal{F}_{n}
$$  

$\rho$ is a stopping time, and from $\rho\leq\tau$ we see that $\rho$ is bounded. So the STP (Theorem 3.6.1) implies $\begin{array}{r}{{\cal E}(X_{\rho})={\cal E}(X_{0})={\cal E}(X_{\tau})}\end{array}$ . But  

$$
\begin{array}{r l r}{{\cal E}(X_{\rho})}&{=}&{{\cal E}\left(X_{\sigma}{\bf1}_{A}+X_{\tau}{\bf1}_{A^{c}}\right),}\ {{}}&{}&{{}}\ {{\cal E}(X_{\tau})}&{=}&{{\cal E}\left(X_{\tau}{\bf1}_{A}+X_{\tau}{\bf1}_{A^{c}}\right).}\end{array}
$$  

So subtracting yields (3.19).  

We can establish a further characterisation of the martingale property.  

Proposition 3.6.4. Let $X=\left(X_{n}\right)$ be an adapted sequence of random variables with $\textstyle H(|X_{n}|)<\infty$ for all $n$ and $\ensuremath{\boldsymbol{{H}}}(\ensuremath{\boldsymbol{{X}}}_{\tau})=0$ for all bounded stopping times $\tau$ . Then $X$ is a martingale.  

Proof. Let $0\leq m<n,\infty$ and $A\in{\mathcal{F}}_{m}$ . Define a stopping time $\tau$ by $\tau=n\mathbf{1}_{A}+m\mathbf{1}_{A^{c}}$ . Then  

$$
\begin{array}{r l r}{0={\cal E}(X_{\tau})}&{{}=}&{{\cal E}\left(X_{n}{\bf1}_{A}+X_{m}{\bf1}_{A^{c}}\right),}\ {0={\cal E}(X_{m})}&{{}=}&{{\cal E}\left(X_{m}{\bf1}_{A}+X_{m}{\bf1}_{A^{c}}\right),}\end{array}
$$  

and by subtraction we obtain $E\left(X_{m}\mathbf{1}_{A}\right)=E\left(X_{n}\mathbf{1}_{A}\right)$ .Since this holds for all $\textit{A}\in\mathcal{F}_{m}$ $\displaystyle\mathit{I E}(X_{n}|\mathcal{F}_{m})=X_{m}$ by definition of conditional expectation. This says that ( $X_{n}$ ) is a martingale, as required.  

Write $X^{\tau}=(X_{n}^{\tau})$ for the sequence $X=\left(X_{n}\right)$ stopped at time $\tau$ , where we define $X_{n}^{\tau}(\omega):=$ $X_{\tau(\omega)\wedge n}(\omega)$  

Proposition 3.6.5. (i) If $X$ is adapted and $\tau$ is a stopping time, then the stopped sequence $X^{\tau}$ is adapted.  

(ii) If $X$ is a martingale (super-, submartingale) and $\tau$ is a stopping time, $X^{\tau}$ is a martingale (super-, submartingale).  

Proof. Let $C_{j}:=\mathbf{1}_{\{j\leq\tau\}}$ ; then  

$$
X_{\tau\wedge n}=X_{0}+\sum_{j=1}^{n}C_{j}(X_{j}-X_{j-1})
$$  

(as the right is $\begin{array}{r}{X_{0}\mathrm{+}\sum_{j=1}^{\tau\wedge n}(X_{j}{-}X_{j-1})}\end{array}$ which telecopes to $X_{\tau\wedge n}$ ). Since $\{j\leq\tau\}$ is the complement of $\{\tau<j\}=\{\tau\leq j-1\}\in\mathcal{F}_{j-1}$ $\left(C_{n}\right)$ is predictable. So $X_{n}^{\tau}$ ) is adapted.  

If $X$ is a martingale, so is $X^{\tau}$ as it is the martingale transform of ( $X_{n}$ ) by ( $C_{n}$ ) (use Theorem C.4.1). The right-hand side above is. $X_{\tau\wedge(n-1)}{+}C_{n}(X_{n}{-}X_{n-1})$ . So taking conditional expectation. given ${\mathcal{F}}_{n-1}$ and using predictability of. $\left(C_{n}$  

$$
\begin{array}{r}{E(X_{\tau\wedge n}|\mathcal{F}_{n-1})=X_{\tau\wedge(n-1)}+C_{n}(E[X_{n}|\mathcal{F}_{n-1}]-X_{n-1}).}\end{array}
$$  

Then $\textstyle C_{n}\geq0$ shows that if $X$ is a supermartingale (submartingale), so is $X^{\tau}$  

We now discuss the Snell envelope, which will be an important tool for the valuation of American options. The idea is due to Snell (1952); for a textbook account, see e.g. Neveu (1975), VI.  

Definition 3.6.2. If $X=(X_{n})_{n=0}^{N}$ is a sequence adapted to a filtration ${\mathcal{F}}_{n}$ with $L(|X_{n}|)<\infty$ the sequence $Z=(Z_{n})_{n=0}^{N}$ defined by.  

$$
\left\{\begin{array}{l}{Z_{N}:=X_{N},}\ {Z_{n}:=\operatorname*{max}\left\{X_{n},E\left(Z_{n+1}|\mathcal{F}_{n}\right)\right\}\quad(n\leq N-1)}\end{array}\right.
$$  

is called the Snell envelope of $X$  

Theorem 3.6.3. The Snell envelope $Z$ of $X$ is a supermartingale, and is the smallest supermartingale dominating $X$ (that is, with. $Z_{n}\geq X_{n}$ for all $n$  

Proof. First, $Z_{n}\geq I E(Z_{n+1}|\mathcal{F}_{n})$ , so $Z$ is a supermartingale, and $Z_{n}\geq X_{n}$ , so $Z$ dominates $X$  

Next, let $Y=\left(Y_{n}\right)$ be any other supermartingale dominating $X$ ; we must show. $Y$ dominates $Z$ also. First, since. $Z_{N}=X_{N}$ and $Y$ dominates $X$ , we must have $Y_{N}\ge Z_{N}$ . Assume inductively that $Y_{n}\ge Z_{n}$ . Then as $Y$ is a supermartingale,  

$$
\begin{array}{r}{Y_{n-1}\geq I E(Y_{n}|\mathcal{F}_{n-1})\geq I E(Z_{n}|\mathcal{F}_{n-1}),}\end{array}
$$  

and as $Y$ dominates $X$  

$$
Y_{n-1}\geq X_{n-1}.
$$  

Combining,  

$$
\begin{array}{r}{Y_{n-1}\geq\operatorname*{max}\left\{X_{n-1},E(Z_{n}|\mathcal{F}_{n-1})\right\}=Z_{n-1}.}\end{array}
$$  

By repeating this argument (or more formally, by backward induction), $Y_{n}\geq Z_{n}$ for all $n$ , as required.  

Proposition 3.6.6. $\tau^{*}:=\operatorname*{inf}\{n\geq0:Z_{n}=X_{n}\}$ is a stopping time, and the stopped process $Z^{\tau^{*}}$ is a martingale.  

Proof. Since $Z_{N}=X_{N}$ $\tau^{*}\in\{0,1,\ldots,N\}$ is well-defined and clearly bounded. For $k=0$ $\{\tau^{*}=0\}=\{Z_{0}=X_{0}\}\in\mathcal{F}_{0}$ ; for $k\geq1$  

$$
\{\tau^{*}=k\}=\left\{Z_{0}>X_{0}\right\}\cap\cdots\cap\left\{Z_{k-1}>X_{k-1}\right\}\cap\left\{Z_{k}=X_{k}\right\}\in{\mathcal{F}}_{k}.
$$  

So $\tau^{*}$ is a stopping time.  

As in the proof of Proposition 3.6.5,  

$$
{Z_{n}^{\tau}}^{*}=Z_{n\wedge\tau^{*}}=Z_{0}+\sum_{j=1}^{n}C_{j}\Delta Z_{j},
$$  

where $C_{j}=\mathbf{1}_{\{j\leq\tau^{*}\}}$ is predictable. For $n\leq N-1$  

$$
Z_{n+1}^{\tau^{*}}-Z_{n}^{\tau^{*}}=C_{n+1}(Z_{n+1}-Z_{n})=\mathbf{1}_{\left\{n+1\leq\tau^{*}\right\}}(Z_{n+1}-Z_{n}).
$$  

Now $Z_{n}:=\operatorname*{max}\left\{X_{n},I E(Z_{n+1}|\mathcal{F}_{n})\right\}$ , and by definition of $\tau^{*}$  

$$
Z_{n}>X_{n}\mathrm{on}\{n+1\leq\tau^{*}\}.
$$  

So from the definition of $Z_{n}$  

$$
Z_{n}=I E(Z_{n+1}|\mathcal{F}_{n})~\mathrm{on}~\{n+1\leq\tau^{*}\}.
$$  

We next prove  

$$
Z_{n+1}^{\tau^{*}}-Z_{n}^{\tau^{*}}=\mathbf{1}_{\left\{n+1\leq\tau^{*}\right\}}(Z_{n+1}-I E(Z_{n+1}|\mathcal{F}_{n})).
$$  

For, suppose first that. $\tau^{*}\geq n+1$ . Then the left of (3.20) is $Z_{n+1}-Z_{n}$ , the right is. $Z_{n+1}-$ $\mathbb{E}(Z_{n+1}|\mathcal{F}_{n})$ , and these agree on $\{n{+}1\leq\tau^{*}\}$ by above. The other possibility is that. $\tau^{*}<n{+}1$ , i.e. $\tau^{*}\leq n$ . Then the left of $(3.20)$ is $Z_{\tau^{*}}-Z_{\tau^{*}}=0$ , while the right is zero because the indicator is zero, completing the proof of (3.20). Now apply. $\textstyle{\mathcal{L}}(.|{\mathcal{F}}_{n})$ to (3.20): since $\{n{+}1\leq\tau^{*}\}=\{\tau^{*}\leq n\}^{c}\in\mathcal{F}_{n}$  

$$
\begin{array}{r l}{E\left[(Z_{n+1}^{\tau^{*}}-Z_{n}^{\tau^{*}})|\mathcal{F}_{n}\right]}&{=\mathbf{1}_{\{n+1\leq\tau^{*}\}}E\left[\left(Z_{n+1}-\ensuremath{\mathbb{E}}(Z_{n+1}|\mathcal{F}_{n})\right)|\mathcal{F}_{n}\right]}\ &{=\mathbf{1}_{\{n+1\leq\tau^{*}\}}\left[\ensuremath{\mathbb{E}}(Z_{n+1}|\mathcal{F}_{n})-\ensuremath{\mathbb{E}}(Z_{n+1}|\mathcal{F}_{n})\right]=0.}\end{array}
$$  

So $\boldsymbol{\it E}(Z_{n+1}^{\tau^{*}}|\mathcal{F}_{n})=Z_{n}^{\tau^{*}}$ . This says that $Z^{\tau^{*}}$ is a martingale, as required.  

Write $T_{n,N}$ for the set of stopping times taking values in $\{n,n+1,\ldots,N\}$ (a finite set, as $\Omega$ is finite). Call a stopping time $\sigma\in{\mathcal{T}}_{n,N}$ optimal for ( $X_{n}$ ) if  

$$
E(X_{\sigma}|\mathcal{F}_{n})=\operatorname*{sup}\{I E(X_{\tau}|\mathcal{F}_{n}):\tau\in\mathcal{T}_{n,N}\}.
$$  

We next see that the Snell envelope can be used to solve the optimal stopping problem for $\left(X_{n}\right)$ in $\mathcal{T}_{0,N}$ . Recall that $\mathcal{F}_{0}=\{\varnothing,\Omega\}$ SO $\begin{array}{r}{\begin{array}{r}{I E(Y|\mathcal{F}_{0})=I E(Y)}\end{array}}\end{array}$ for any integrable random variable $Y$  

Proposition 3.6.7. $\tau^{*}$ solves the optimal stopping problem for $X$  

$$
Z_{0}=I E(X_{\tau^{*}})=\operatorname*{sup}\left\{I E\left(X_{\tau}\right):\tau\in{\mathcal{T}}_{0,N}\right\}.
$$  

Proof. To prove the first statement we use that $\left(Z_{n}^{\tau^{*}}\right)$ is a martingale and $Z_{\tau^{*}}=X_{\tau^{*}}$ ; then  

$$
Z_{0}=Z_{0}^{\tau^{*}}=I E\left(Z_{N}^{\tau^{*}}\right)=I E\left(Z_{\tau^{*}}\right)=I E\left(X_{\tau}^{*}\right).
$$  

Now for any stopping time $\tau\in T_{0,N}$ , since $Z$ is a supermartingale (above), so is the stopped process $Z^{\tau}$ (see Proposition 3.6.5). Together with the property that $Z$ dominates $X$ this yields  

$$
Z_{0}=Z_{0}^{\tau}\geq\ensuremath{\boldsymbol{{\cal E}}}\left(Z_{N}^{\tau}\right)=\ensuremath{\boldsymbol{{\cal E}}}\left(Z_{\tau}\right)\geq\ensuremath{\boldsymbol{{\cal E}}}\left(X_{\tau}\right).
$$  

Combining (3.21) and (3.22) and taking the supremum on $\tau$ gives the result.  

The same argument, starting at time $n$ rather than time. $0$ , gives  

Corollary 3.6.1. If $\tau_{n}^{*}:=\operatorname*{inf}\{j\geq n:Z_{j}=X_{j}\}$  

$$
Z_{n}=\ensuremath{\boldsymbol{{\cal E}}}(X_{\tau_{n}^{*}}|\mathcal{F}_{n})=\operatorname*{sup}\left\{\ensuremath{\boldsymbol{{\cal E}}}(X_{\tau}|\mathcal{F}_{n}):\tau\in\mathcal{T}_{n,N}\right\}.
$$  

As we are attempting to maximise our payoff by stopping $X=\left(X_{n}\right)$ at the most advantageous time, the Corollary shows that $\tau_{n}^{*}$ gives the best stopping time that is realistic: it maximises our expected payoff given only information currently available.  

We proceed by analysing optimal stopping times. One can characterize optimality by establishing a martingale property:  

Proposition 3.6.8. The stopping time $\sigma\in T$ is optimal for (. $X_{t}$ ) if and only if the following two.   
conditions hold. (i) $Z_{\sigma}=X_{\sigma}$ .   
(ii) $Z^{\sigma}$ is a martingale.  

Proof. We start showing that (i) and (ii) imply optimality. If $Z^{\sigma}$ is a martingale then  

$$
Z_{0}=I E(Z_{0}^{\sigma})=I E(Z_{N}^{\sigma})=I E(Z_{\sigma})=I E(X_{\sigma}),
$$  

where we used (i) for the last identity. Since $Z$ is a supermartingale Proposition 3.6.5 implies that $Z^{\tau}$ is a supermartingale for any. $\tau\in T_{0,N}$ . Now $Z$ dominates $X$ , and so  

$$
Z_{0}={\cal E}(Z_{0}^{\tau})\ge{\cal E}(Z_{N}^{\tau})={\cal E}(Z_{\tau})\ge{\cal E}(X_{\tau}).
$$  

Combining, $\sigma$ is optimal.  

Now assume that $\sigma$ is optimal. Thus  

$$
Z_{0}=\operatorname*{max}\left\{{L E(X_{\tau});\tau\in{\mathcal{T}}_{0,N}}\right\}=E(X_{\sigma})\leq E(Z_{\sigma}),
$$  

since $Z$ dominates $X$ . Since $Z^{\sigma}$ is a supermartingale, we also have $Z_{0}\geq\mathcal{L}(Z_{\sigma})$ . Combining.  

$$
H(X_{\sigma})=Z_{0}=I E(Z_{\sigma}).
$$  

But $X\le Z$ , so $X_{\sigma}\leq Z_{\sigma}$ , while by the above $X_{\sigma}$ and $Z_{\sigma}$ have the same expectation. So they must. be a.s. equal: $X_{\sigma}=Z_{\sigma}$ a.s., showing (i). To see (ii), observe that for any $n\leq N$  

$$
\begin{array}{r}{E(Z_{\sigma})=Z_{0}\geq E(Z_{\sigma\wedge n})\geq E(Z_{\sigma})=E(E(Z_{\sigma}|\mathcal{F}_{n})),}\end{array}
$$  

where the second inequality follows from Doob's OST (Theorem 3.6.2) with the bounded stopping times $(\sigma\land n)\le\sigma$ and the supermartingale $Z$ .Using that $Z$ is a supermartingale again, we also. find  

$$
Z_{\sigma\wedge n}\geq I E(Z_{\sigma}|\mathcal{F}_{n}).
$$  

As above, this inequality between random variables with equal expectations forces a.s. equality: $Z_{\sigma\wedge n}=I E(Z_{\sigma}|\mathcal{F}_{n})$ a.s.. Apply $\it{l b}(.|\mathcal{F}_{n-1})$  

$$
\begin{array}{r}{E\left(Z_{\sigma\wedge n}\big|\mathcal{F}_{n-1}\right)=E E\left(E(Z_{\sigma}|\mathcal{F}_{n})|\mathcal{F}_{n-1}\right)=E(Z_{\sigma}|\mathcal{F}_{n-1})=Z_{\sigma\wedge(n-1)},}\end{array}
$$  

by (3.23) with $n-1$ for $n$ . This says  

$$
E\left(Z_{n}^{\sigma}|{\mathcal{F}}_{n-1}\right)=Z_{n-1}^{\sigma},
$$  

so $Z^{\sigma}$ is a martingale.  

From Proposition 3.6.6 and its definition (first time when $Z$ and $X$ are equal) it follows that $\tau^{*}$ is the smallest optimal stopping time . To find the largest optimal stopping time we try to find the time when $Z$ 'ceases to be a martingale'. In order to do so we need a structural result of genuine interest and importance  

Theorem 3.6.4 (Doob Decomposition). Let $X=\left(X_{n}\right)$ be an adapted process with each $X_{n}\in$ $\mathcal{L}^{1}$ . Then $X$ has an (essentially unique) Doob decomposition  

$$
X=X_{0}+M+A:\quad X_{n}=X_{0}+M_{n}+A_{n}\quad\forall n
$$  

with M a martingale null at zero, $A$ a predictable process null at zero. If also $X$ is a submartingale (increasing on average'), $A$ is increasing: $A_{n}\leq A_{n+1}$ for all $n$ , a.s..  

Proof. If $X$ has a Doob decomposition (3.24),  

$$
E[X_{n}-X_{n-1}|\mathcal{F}_{n-1}]=E[M_{n}-M_{n-1}|\mathcal{F}_{n-1}]+E[A_{n}-A_{n-1}|\mathcal{F}_{n-1}].
$$  

The first term on the right is zero, as $M$ is a martingale. The second is. $A_{n}-A_{n-1}$ , since $A_{n}$ (and $A_{n-1}$ ) is ${\mathcal{F}}_{n-1}$ -measurable by predictability. So  

$$
\begin{array}{r}{H[X_{n}-X_{n-1}|\mathcal{F}_{n-1}]=A_{n}-A_{n-1},}\end{array}
$$  

and summation gives  

$$
A_{n}=\sum_{k=1}^{n}{\cal E}[X_{k}-X_{k-1}|{\mathcal F}_{k-1}],\quad a.s.
$$  

So set $A_{0}=0$ and use this formula to define ( $A_{n}$ ), clearly predictable. We then use (3.24) to define ( $M_{n}$ ), then a martingale, giving the Doob decomposition (3.24). To see uniqueness, assume two decompositions, i.e. $X_{n}=X_{0}+M_{n}+A_{n}=X_{0}+\tilde{M}_{n}+\tilde{A}_{n}$ , then $M_{n}-\tilde{M}_{n}=A_{n}-\tilde{A}_{n}$ . Thus the martingale $M_{n}-\tilde{M_{n}}$ is predictable and so must be constant a.s..  

If $X$ is a submartingale, the LHS of (3.25) is $\geq0$ , so the RHS of (3.25) is $\geq0$ , i.e. $A_{n}$ ) is increasing.  

Although the Doob decomposition is a simple result in discrete time, the analogue in continuous. time - the Doob-Meyer decomposition - is deep. This illustrates the contrasts that may arise between the theories of stochastic processes in discrete and continuous time..  

Equipped with the Doob-decomposition we return to the above setting and can write  

$$
Z=Z_{0}+L+B
$$  

with $L$ a martingale and $B$ predictable and decreasing. Then $M=Z_{0}+L$ is a martingale and.   
$A=\left(-B\right)$ is increasing and we have. $Z=M-A$  

Definition 3.6.3. Define a random variable $\nu:\Omega\to I N_{0}$ by setting  

$$
\begin{array}{r}{\nu(\omega)=\left\{\begin{array}{l l}{N}&{i f A_{N}(\omega)=0}\ {\operatorname*{min}\{n\geq0:A_{n+1}>0\}}&{i f A_{N}(\omega)>0.}\end{array}\right.}\end{array}
$$  

Observe that $\nu$ (bounded by $N$ ) is a stopping time, since  

$$
\{\nu=n\}=\bigcup_{k\leq n}\{A_{k}=0\}\cap\{A_{n+1}>0\}\in{\mathcal{F}}_{n}
$$  

as $A$ is predictable.  

Proposition 3.6.9. v is optimal for (. $X_{t}$ ), and it is the largest optimal stopping time for $\left(X_{t}\right)$  

Proof. We use Proposition 3.6.8. Since for $k\le\nu(\omega),Z_{k}(\omega)=M_{k}(\omega)-A_{k}(\omega)=M_{k}(\omega)$ $Z^{\nu}$ is a martingale and thus we have (ii) of Proposition 3.6.8. To see (i) we write  

$$
\begin{array}{r c l}{{Z_{\nu}}}&{{=}}&{{\displaystyle\sum_{k=0}^{N-1}\mathbf{1}_{\left\{\nu=k\right\}}Z_{k}+\mathbf{1}_{\left\{\nu=N\right\}}Z_{N}}}\ {{}}&{{=}}&{{\displaystyle\sum_{k=0}^{N-1}\mathbf{1}_{\left\{\nu=k\right\}}\operatorname*{max}\{X_{k},{\cal E}(Z_{k+1}|\mathcal{F}_{k})\}+\mathbf{1}_{\left\{\nu=N\right\}}X_{N}.}}\end{array}
$$  

Now IE(z $\begin{array}{r}{Z_{k+1}\vert\mathcal{F}_{k})=H(M_{k+1}-A_{k+1}\vert\mathcal{F}_{k})=M_{k}-A_{k+1}}\end{array}$ I. On $\{\nu=k\}$ we have $A_{k}~=~0$ and $A_{k+1}>0$ , so $I E(Z_{k+1}|\mathcal{F}_{k})<Z_{k}$ . Hence $Z_{k}=\operatorname*{max}\{X_{k},L E(Z_{k+1}|{\mathcal{F}}_{k})\}=X_{k}$ on the set $\{\nu=k\}$ So  

$$
Z_{\nu}=\sum_{k=0}^{N-1}\mathbf{1}_{\left\{\nu=k\right\}}X_{k}+\mathbf{1}_{\left\{\nu=N\right\}}X_{N}=X_{\nu},
$$  

which is (i) of Proposition 3.6.8. Now take $\tau\in\{\mathcal T\}_{0,N}$ with $\tau\geq\nu$ and $I P(\tau>\nu)>0$ . From the definition of $\nu$ and the fact that $A$ is increasing, $A_{\tau}>0$ with positive probability. So $E(A_{\tau})>0$ and  

$$
E(Z_{\tau})=E(M_{\tau})-E(A_{\tau})=E(Z_{0})-E(A_{\tau})<E(Z_{0}).
$$  

So $\tau$ cannot be optimal.  

# 3.6.2 The Financial Model  

We assume now that we work in a market model $(\Omega,{\mathcal{F}},I F,I P)$ , which is complete with. $\mathit{\Pi}\mathit{\perp}\mathit{\Psi}$ the unique martingale measure..  

Then for any hedging strategy $\varphi$ we have that under $\b{\mathcal{M}}^{*}$  

$$
M(t)=\tilde{V}_{\varphi}(t)=\beta(t)V_{\varphi}(t)
$$  

is a martingale. Thus we can use the STP (Theorem 3.6.1) to find for any stopping time $\tau$  

$$
V_{\varphi}(0)=M_{0}=I E^{*}(\tilde{V}_{\varphi}(\tau)).
$$  

Since we require $V_{\varphi}(\tau)\geq f_{\tau}(S)$ for any stopping time we find for the required initial capital  

$$
x\geq\operatorname*{sup}_{\tau\in\mathcal{T}}I E^{*}(\beta(\tau)f_{\tau}(S)).
$$  

Suppose now that $\tau^{*}$ is such that. $V_{\varphi}(\tau^{*})=f_{\tau^{*}}(S)$ then the strategy $\varphi$ is minimal and since $V_{\varphi}(t)\geq f_{t}(S)$ for all $t$ we have  

$$
x=I E^{*}(\beta(\tau^{*})f_{\tau^{*}}(S))=\operatorname*{sup}_{\tau\in\cal{T}}I E^{*}(\beta(\tau)f_{\tau}(S))
$$  

Thus (3.29) is a necessary condition for the existence of a minimal strategy. $\varphi$ . We will show that it is also sufficient and call the price in (3.29) the rational price of an American contingent claim.  

Now consider the problem of the option writer to construct such a strategy $\varphi$ . At time $T$ the hedging strategy needs to cover. $f_{T}$ , i.e. $V_{\varphi}(T)\geq f_{T}$ is required (We write short. $f_{t}$ for $f_{t}(S)$ ). At time $T-1$ the option holder can either exercise and receive $f_{T-1}$ or hold the option to expiry,. in which case. $B(T-1)E^{*}(\beta(T)f_{T}|F_{T-1})$ needs to be covered. Thus the hedging strategy of the. writer has to satisfy.  

$$
V_{\varphi}(T-1)=\operatorname*{max}\{f_{T-1},B(T-1)E^{*}(\beta(T)f_{T}|\mathcal{F}_{T-1})\}
$$  

Using a backwards induction argument we can show that  

$$
\begin{array}{r}{V_{\varphi}(t-1)=\operatorname*{max}\{f_{t-1},B(t-1)E^{*}(\beta(t)V_{\varphi}(t)|\mathcal{F}_{t-1})\}.}\end{array}
$$  

Considering only discounted values this leads to  

$$
\begin{array}{r}{\tilde{V}_{\varphi}(t-1)=\operatorname*{max}\{\tilde{f}_{t-1},E^{*}(\tilde{V}_{\varphi}(t)|\mathcal{F}_{t-1})\}.}\end{array}
$$  

Thus we see that $\tilde{V}_{\varphi}(t)$ is the Snell envelope $Z_{t}$ Of $\tilde{f}_{t}$  

In particular we know that  

$$
Z_{t}=\operatorname*{sup}_{\tau\in{\mathcal{T}}_{t}}I E^{*}(\tilde{f}_{\tau}|{\mathcal{F}}_{t})
$$  

and the stopping time $\begin{array}{r}{\tau^{*}=\operatorname*{min}\{s\ge t:Z_{s}=\tilde{f}_{s}\}}\end{array}$ is optimal. So.  

$$
Z_{t}=I E^{*}(\tilde{f}_{\tau^{*}}|\mathcal{F}_{t})
$$  

In case $t=0$ we can use $\tau_{0}^{*}=\operatorname*{min}\{s\geq0:Z_{s}=\tilde{f}_{s}\}$ and then  

$$
x=Z_{0}=I E^{*}(\tilde{f}_{\tau_{0}^{*}})=\operatorname*{sup}_{\tau\in\mathcal{T}_{0}}I E^{*}(\tilde{f}_{\tau})
$$  

is the rational option price.  

We still need to construct the strategy $\varphi$ . To do this recall that. $Z$ is a supermartingale and so. the Doob decomposition yields.  

$$
Z=\tilde{M}-\tilde{A}
$$  

with a martingale $\tilde{M}$ and a predictable, increasing process. $\tilde{A}$ .We write $M_{t}=\tilde{M}_{t}B_{t}$ and $A_{t}={}$ $\tilde{A}_{t}B_{t}$ . Since the market is complete we know that there exists a self-financing strategy $\bar{\varphi}$ such that  

$$
\tilde{M}_{t}=\tilde{V}_{\bar{\varphi}}(t).
$$  

Also using (3.36) we find $Z_{t}B_{t}=V_{\bar{\varphi}}(t)-A_{t}$ . Now on $C=\{(t,\omega):0\leq t<\tau^{*}(\omega)\}$ we have that $Z$ is a martingale and thus $A_{t}(\omega)=0$ . Thus we obtain from $\dot{V}_{\bar{\varphi}}(t)=Z_{t}$ that  

$$
\tilde{V}_{\bar{\varphi}}(t)=\operatorname*{sup}_{t\leq\tau\leq T}{I E^{*}(\tilde{f}_{\tau}|\mathcal{F}_{t})}\forall(t,\omega)\in C.
$$  

Now $\tau^{*}$ is the smallest exercise time and $\tilde{A}_{\tau^{*}(\omega)}=0$ . Thus  

$$
\tilde{V}_{\bar{\varphi}}(\tau^{*}(\omega),\omega)=Z_{\tau^{*}(\omega)}(\omega)=\tilde{f}_{\tau^{*}(\omega)}(\omega)
$$  

Undoing the discounting we find  

$$
V_{\bar{\varphi}}(\tau^{*})=f_{\tau^{*}}
$$  

and therefore $\phi$ is a minimal hedge.  

Now consider the problem of the option holder, how to find the optimal exercise time. We observe that the optimal exercise time must be an optimal stopping time, since for any other stopping time $\sigma$ (use Proposition 3.6.8)  

$$
\tilde{V}_{\varphi}(\sigma)=Z_{\sigma}>\tilde{f}_{\sigma}
$$  

and holding the asset longer would generate a larger payoff. Thus the holder needs to wait until $Z_{\sigma}=\tilde{f}_{\sigma}$ i.e. (i) of Proposition 3.6.8 is true. On the other hand with $\nu$ the largest stopping time (compare Definition 3.6.3) we see that $\sigma\leq\nu$ . This follows since using $\bar{\phi}$ after $\nu$ with initial capital. from exercising will always yield a higher portfolio value than the strategy of exercising later. To see this recall that.. $V_{\bar{\varphi}}=Z_{t}B_{t}+A_{t}$ with $A_{t}~>~0$ for $t>\nu$ . So we must have. $\sigma\leq\nu$ and since $A_{t}=0$ for $t\leq\nu$ we see that. $Z^{\sigma}$ is a martingale. Now criterion (ii) of Proposition 3.6.8 is true and $\sigma$ is thus optimal. So  

Proposition 3.6.10. A stopping time. $\sigma\in T_{t}$ is an optimal exercise time for the American option $\left(f_{t}\right)$ if and only if.  

$$
E^{*}(\beta(\sigma)f_{\sigma})=\operatorname*{sup}_{\tau\in\mathcal{T}_{t}}E^{*}(\beta(\tau)f_{\tau})
$$  

# 3.6.3 American Options in the Cox-Ross-Rubinstein model  

We now consider how to evaluate an American put option in a standard CRR model. We assume that the time interval $[0,T]$ is divided into. $N$ equal subintervals of length $\Delta$ say. Assuming the risk-free rate of interest $r$ (over [0,T]) as given, we have $1+\rho=e^{r\Delta}$ (where we denote the riskfree rate of interest in each subinterval by $\rho$ ). The remaining degrees of freedom are resolved by choosing $u$ and $d$ as follows:  

$$
1+u=e^{\sigma\sqrt{\Delta}},\quad\mathrm{and}\quad1+d=(1+u)^{-1}=e^{-\sigma\sqrt{\Delta}}.
$$  

By condition (3.9) the risk-neutral probabilities for the corresponding single period models are given by  

$$
p^{*}={\frac{\rho-d}{u-d}}={\frac{e^{r\Delta}-e^{-\sigma{\sqrt{\Delta}}}}{e^{\sigma{\sqrt{\Delta}}}-e^{-\sigma{\sqrt{\Delta}}}}}.
$$  

Thus the stock with initial value $S=S(0)$ is worth $S(1+u)^{i}(1+d)^{j}$ after $i$ steps up and $j$ steps down. Consequently, after $N$ steps, there are $N+1$ possible prices, $S(1+u)^{i}(1+d)^{N-i}$ $(i=0,\ldots,N)$ . There are $2^{N}$ possible paths through the tree. It is common to take $N$ of the order of 30, for two reasons:  

(i) typical lengths of time to expiry of options are measured in months (9 months, say); this gives a time step around the corresponding number of days,.   
(ii) $2^{30}$ paths is about the order of magnitude that can be comfortably handled by computers (recall that $2^{10}=1,024$ , SO $2^{30}$ is somewhat over a billion).  

We can now calculate both the value of an American put option and the optimal exercise strategy by working backwards through the tree (this method of backward recursion in time is a form of the dynamic programming (DP) technique, due to Richard Bellman, which is important in many areas of optimisation and Operational Research).  

1. Draw a binary tree showing the initial stock value and having the right number, $N$ , of time intervals.   
2. Fill in the stock prices: after one time interval, these are $S(1+u)$ (upper) and $S(1+d)$ (lower); after two time intervals, $S(1+u)^{2}$ $S$ and $S(1+d)^{2}=S/(1+u)^{2}$ ; after $i$ time intervals, these are $S(1+u)^{j}(1+d)^{i-j}=S(1+u)^{2j-i}$ at the node with $j$ 'up' steps and $i-j$ 'down' steps (the $(i,j)$ node).   
3. Using the strike price $K$ and the prices at the terminal nodes, fill in the payoffs $f_{N,j}^{A}=$ $\operatorname*{max}\{K-S(1+u)^{j}(1+d)^{N-j},0\}$ from the option at the terminal nodes underneath the terminal prices.   
4. Work back down the tree, from right to left. The no-exercise values $f_{i j}$ of the option at the $(i,j)$ node are given in terms of those of its upper and lower right neighbours in the usual way, as discounted expected values under the risk-neutral measure:  

$$
f_{i j}=e^{-r\Delta}[p^{*}f_{i+1,j+1}^{A}+(1-p^{*})f_{i+1,j}^{A}].
$$  

The intrinsic (or early-exercise) value of the American put at the $(i,j)$ node - the value there if it. is exercised early - is  

$$
K-S(1+u)^{j}(1+d)^{i-j}
$$  

(when this is non-negative, and so has any value). The value of the American put is the higher of t hese:  

$$
\begin{array}{l l l}{{f_{i j}^{A}}}&{{=}}&{{\operatorname*{max}\{f_{i j},K-S(1+u)^{j}(1+d)^{i-j}\}}}\ {{}}&{{=}}&{{\operatorname*{max}\left\{e^{-r\Delta}(p^{*}f_{i+1,j+1}^{A}+(1-p^{*})f_{i+1,j}^{A}),K-S(1+u)^{j}(1+d)^{i-j}\right\}.}}\end{array}
$$  

5. The initial value of the option is the value $f_{0}^{A}$ filled in at the root of the tree.  

6. At each node, it is optimal to exercise early if the early-exercise value there exceeds the value $f_{i j}$ there of expected discounted future payoff.  

# 3.6.4 A Three-period Example  

Assume we have two basic securities: a risk-free bond and a risky stock. The one-year risk-free. interest rate (continuously compounded) is $r=0.06$ and the volatility of the stock is. $20\%$ .We price calls and puts in three-period Cox-Ross-Rubinstein model. The up and down movements of the stock price are given by  

$$
1+u=e^{\sigma\sqrt{\Delta}}=1.1224\quad\mathrm{and}\quad1+d=(1+u)^{-1}=e^{-\sigma\sqrt{\Delta}}=0.8910,
$$  

with $\sigma=0.2$ and $\Delta=1/3$ . We obtain risk-neutral probabilities by (3.9)  

$$
p^{*}=\frac{e^{r\Delta}-d}{u-d}=0.5584.
$$  

We assume that the price of the stock at time. $t=0$ is $S(0)=100$ . To price a European call option. with maturity one year (. $N=3$ ) and strike $K=10$ ) we can either use the valuation formula (3.12) or work our way backwards through the tree. Prices of the stock and the call are given in Figure 4.2 below. One can implement the simple evaluation formulae for the CRR- and the BS-models and compare the values. Figure 3.3 is for $S=100,K=90,r=0.06,\sigma=0.2,T=1.$  

![](7779388d070b426040dfbaec3e2174d598fc2b85bf65ea70933bb8f7418a753d.jpg)  
Figure 3.2: Stock and European call prices  

![](ac9e26819594dbdbaef2357f5a8490ae18862966caa46a7c42dc192a0dc78bd4.jpg)  
Figure 3.3: Approximation of Black-Scholes price by Binomial models  

To price a European put, with price process denoted by. $p(t)$ , and an American put, $P(t)$ (maturity $N=3$ , strike 100), we can for the European put either use the put-call parity (1.1), the. risk-neutral pricing formula, or work backwards through the tree. For the prices of the American put we use the technique outlined in \$4.8.1. Prices of the two puts are given in Figure 4.4. We. indicate the early exercise times of the American put in bold type. Recall that the discrete-time. rule is to exercise if the intrinsic value $K-S(t)$ is larger than the value of the corresponding European put.  

![](681bb4bf788c39818d65fa4d9745bc094532c0049e1a45b060796fbdbbe16275.jpg)  
Figure 3.4: European $p(.)$ and American $P(.)$ put prices  

# Chapter 4  

# Continuous-time Financial Market Models  

# 4.1 The Stock Price Process and its Stochastic Calculus  

# 4.1.1 Continuous-time Stochastic Processes  

A stochastic process $X=(X(t))_{t\geq0}$ is a family of random variables defined on $(\Omega,{\mathcal{F}},I P,I F)$ . We say $X$ is adapted if. $X(t)\in\mathcal{F}_{t}$ (i.e. $X(t)$ is $\mathcal{F}_{t}$ -measurable) for each $t$ : thus $X(t)$ is known when. $\mathbf{\mathcal{F}}_{t}$ is known, at time. $t$  

The martingale property in continuous time is just that suggested by the discrete-time case:  

Definition 4.1.1. A stochastic process $X=(X(t))_{0\leq t<\infty}$ is a martingale relative to. $(\mathbf{}F,\mathbf{}P)$ if (i) $X$ is adapted, and $\textstyle\operatorname{\mathbb{E}}|X(t)|<\infty$ for a $l l\leq t<\infty$ (ii) $L[X(t)|\mathcal{F}_{s}]=X(s)D-a.s.(0\leq s\leq t),$  

and similarly for sub- and supermartingales.  

There are regularisation results, under which one can take. $X(t)$ RCLL in $t$ (basically $t\rightarrow$ $\ensuremath{\boldsymbol{{H}}}\ensuremath{\boldsymbol{{X}}}(t)$ has to be right-continuous). Then the analogues of the results for discrete-time martingales hold true.  

Interpretation. Martingales model fair games. Submartingales model favourable games. Supermartingales model unfavourable games.  

Brownian motion originates in work of the botanist Robert Brown in 1828. It was introduced into finance by Louis Bachelier in 1900, and developed in physics by Albert Einstein in 1905.  

Definition 4.1.2. A stochastic process $X=(X(t))_{t\geq0}$ is a standard (one-dimensional) Brownian motion, $B M$ or $B M(R)$ , on some probability space. $(\Omega,{\mathcal{F}},I P)$ , if  

(i) $X(0)=0$ a.8.,   
(ii) $X$ has independent increments: $X(t+u)-X(t)$ is independent of $\sigma(X(s):s\leq t)$ for $u\geq0$   
(iii) $X$ has stationary increments: the law of. $X(t+u)-X(t)$ depends only on u,.   
(iv) $X$ has Gaussian increments: $X(t+u)-X(t)$ is normally distributed with mean 0 and variance $u$ $X(t+u)-X(t)\sim N(0,u)$   
(v) $X$ has continuous paths: $X(t)$ is a continuous function of. $t$ , i.e. $t\to X(t,\omega)$ is continuous in $t$ for all $\omega\in\Omega$  

We shall henceforth denote standard Brownian motion $B M(R)$ by $W~=~(W(t))$ $W$ for Wiener), though. $B=(B(t))$ $B$ for Brown) is also common. Standard Brownian motion $B M(R^{d})$ in $d$ dimensions is defined by. $W(t):=(W_{1}(t),\ldots,W_{d}(t))$ , where $W_{1},\dots,W_{d}$ are independent standard Brownian motions in one dimension (independent copies of $B M(R)$  

We have Wiener's theorem:  

# Theorem 4.1.1 (Wiener). Brownian motion exists.  

For further background, see any measure-theoretic text on stochastic processes. A treatment starting directly from our main reference of measure-theoretic results, Williams (Williams 1991), is Rogers and Williams (Rogers and Williams 1994), Chapter 1. The classic is Doob's book, (Doob 1953), VIII.2. Excellent modern texts include (Karatzas and Shreve 1991, Revuz and Yor 1991) (see particularly (Karatzas and Shreve 1991), $\S$ 2.2-4 for construction).  

# Geometric Brownian Motion  

Now that we have both Brownian motion. $W$ and Ito's Lemma to hand, we can introduce the most. important stochastic process for us, a relative of Brownian motion - geometric (or exponential, or economic) Brownian motion.  

Suppose we wish to model the time evolution of a stock price $S(t)$ (as we will, in the BlackScholes theory). Consider how $S$ will change in some small time-interval from the present time. $t$ to a time $t+d t$ in the near future. Writing $d S(t)$ for the change $S(t+d t)-S(t)$ in $S$ , the return on $S$ in this interval is $d S(t)/S(t)$ . It is economically reasonable to expect this return to decompose. into two components, a systematic part and a random part. The systematic part could plausibly be modelled by $\mu d t$ , where $\mu$ is some parameter representing the mean rate of return of the stock. The random part could plausibly be modelled by $\sigma d W(t)$ , where $d W(t)$ represents the noise term driving the stock price dynamics, and $\sigma$ is a second parameter describing how much effect this. noise has - how much the stock price fluctuates. Thus. $\sigma$ governs how volatile the price is, and is called the volatility of the stock. The role of the driving noise term is to represent the random. buffeting effect of the multiplicity of factors at work in the economic environment in which the stock price is determined by supply and demand.  

Putting this together, we have the stochastic differential equation  

$$
d S(t)=S(t)(\mu d t+\sigma d W(t)),\quad S(0)>0,
$$  

due to Ito in 1944. This corrects Bachelier's earlier attempt of 1900 (he did not have the factor $S(t)$ on the right - missing the interpretation in terms of returns, and leading to negative stock prices!) Incidentally, Bachelier's work served as Ito's motivation in introducing Ito calculus. The mathematical importance of Ito's work was recognised early, and led on to the work of (Doob 1953), (Meyer 1976) and many others (see the memorial volume (Ikeda, Watanabe, M., and Kunita 1996) in honour of Ito's eightieth birthday in 1995). The economic importance of geometric Brownian. motion was recognised by Paul A. Samuelson in his work from 1965 on ((Samuelson 1965)), for. which Samuelson received the Nobel Prize in Economics in 1970, and by Robert Merton (see (Merton 1990) for a full bibliography), in work for which he was similarly honoured in 1997..  

# 4.1.2 Stochastic Analysis  

Stochastic integration was introduced by K. Ito in 1944, hence its name Ito calculus. It gives a meaning to  

$$
\intop_{0}^{t}X d Y=\intop_{0}^{t}X(s,\omega)d Y(s,\omega),
$$  

for suitable stochastic processes $X$ and $Y$ , the integrand and the integrator. We shall confine our attention here mainly to the basic case with integrator Brownian motion: $Y=W$ . Much greater generality is possible: for $Y$ a continuous martingale, see (Karatzas and Shreve 1991) or (Revuz and Yor 1991); for a systematic general treatment, see (Protter 2004).  

The first thing to note is that stochastic integrals with respect to Brownian motion, if they exist, must be quite different from the measure-theoretic integral. For, the Lebesgue-Stieltjes integrals described there have as integrators the difference of two monotone (increasing) functions, which are locally of bounded variation. But we know that Brownian motion is of infinite (unbounded) variation on every interval. So Lebesgue-Stieltjes and Ito integrals must be fundamentally different.  

In view of the above, it is quite surprising that Ito integrals can be defined at all. But if we take for granted Ito's fundamental insight that they can be, it is obvious how to begin and clear enough how to proceed. We begin with the simplest possible integrands $X$ , and extend successively in much the same way that we extended the measure-theoretic integral.  

# Indicators.  

If $X(t,\omega)=\mathbf{1}_{[a,b]}(t)$ , there is exactly one plausible way to define $\textstyle\int X d W$  

$$
\int_{0}^{t}X(s,\omega)d W(s,\omega):=\left\{\begin{array}{l l}{0}&{\mathrm{if~}t\leq a,}\ {W(t)-W(a)}&{\mathrm{if~}a\leq t\leq b,}\ {W(b)-W(a)}&{\mathrm{if~}t\geq b.}\end{array}\right.
$$  

# Simple Functions.  

Extend by linearity: if $X$ is a linear combination of indicators, $\begin{array}{r}{X=\sum_{i=1}^{n}c_{i}\mathbf{1}_{[a_{i},b_{i}]}}\end{array}$ , we should define  

$$
\intop_{0}^{t}X d W:=\sum_{i=1}^{n}c_{i}\intop_{0}^{t}\mathbf{1}_{[a_{i},b_{i}]}d W.
$$  

Already one wonders how to extend this from constants. $c_{i}$ to suitable random variables, and one.   
seeks to simplify the obvious but clumsy three-line expressions above.  

We begin again, this time calling a stochastic process $X$ simple if there is a partition $0=t_{0}<$ $t_{1}<...<t_{n}=T<\infty$ and uniformly bounded $\mathcal{F}_{t_{n}}$ -measurable random variables $\xi_{k}$ $|\xi_{k}|\le C$ for all $k=0,\ldots,n$ and $\omega$ , for some $C$ ) and if $X(t,\omega)$ can be written in the form  

$$
X(t,\omega)=\xi_{0}(\omega)\mathbf{1}_{\{0\}}(t)+\sum_{i=0}^{n}\xi_{i}(\omega)\mathbf{1}_{(t_{i},t_{i+1}]}(t)(0\leq t\leq T,\omega\in\Omega).
$$  

Then if tk t<tk+1,  

$$
\begin{array}{r c l}{{I_{t}(X):=\displaystyle\int_{0}^{t}{X}d W}}&{{=}}&{{\displaystyle\sum_{i=0}^{k-1}\xi_{i}(W(t_{i+1})-W(t_{i}))+\xi_{k}(W(t)-W(t_{k}))}}\ {{}}&{{=}}&{{\displaystyle\sum_{i=0}^{n}\xi_{i}(W(t\wedge t_{i+1})-W(t\wedge t_{i})).}}\end{array}
$$  

Note that by definition $I_{0}(X)=0$ ${\cal I}{\cal P}-a.s..$ We collect some properties of the stochastic integral defined so far:  

Lemma 4.1.1. (i) $I_{t}(a X+b Y)=a I_{t}(X)+b I_{t}(Y)$ (ii) $\begin{array}{r}{\mathit{I E}(I_{t}(X)|\mathcal{F}_{s})=I_{s}(X)\mathit{\Psi}\mathit{I P}-a.s}\end{array}$ $0\leq s<t<\infty$ ), hence. $I_{t}(X)$ is a continuous martingale.  

The stochastic integral for simple integrands is essentially a martingale transform, and the above is essentially the proof that martingale transforms are martingales..  

We pause to note a property of square-integrable martingales which we shall need below. Call $M(t)-M(s)$ the increment of $M$ over $(s,t]$ . Then for a martingale $M$ , the product of the increments over disjoint intervals has zero mean. For, if. $s<t\leq u<v$  

$$
\begin{array}{r l}&{I E\left[(M(v)-M(u))(M(t)-M(s))\right]}\ {=}&{I E\left[T(M(v)-M(u))(M(t)-M(s))|\mathcal{F}_{u}\right)\right]}\ {=}&{I E\left[(M(t)-M(s))E((M(v)-M(u))|\mathcal{F}_{u})\right],}\end{array}
$$  

taking out what is known (as. $s,t\leq u$ ). The inner expectation is zero by the martingale property, so the left-hand side is zero, as required..  

We now can add further properties of the stochastic integral for simple functions.  

Lemma 4.1.2. (i) We have the Ito isometry  

$$
\begin{array}{r}{E\left((I_{t}(X))^{2}\right)=E\left(\smallint_{0}^{t}X(s)^{2}d s\right).}\ {(i i)I E\left((I_{t}(X)-I_{s}(X))^{2}|\mathcal{F}_{s}\right)=E\left(\smallint_{s}^{t}X(u)^{2}d u\right)\quad\it{I P-a.s.}}\end{array}
$$  

The Ito isometry above suggests that $\textstyle\int_{0}^{t}X d W$ should be defined only for processes with  

$$
\intop_{0}^{t}E\left(X(u)^{2}\right)d u<\infty\mathrm{for~all}t.
$$  

We then can transfer convergence on a suitable. $L^{2}$ -space of stochastic processes to a suitable. $L^{2}$ space of martingales. This gives us an. $L^{2}$ -theory of stochastic integration, for which Hilbert-space methods are available.  

For the financial applications we have in mind, there is a fixed time-interval - $[0,T]$ say - on which we work (e.g., an option is written at time. $t=0$ , with expiry time $t=T$ ). Then the above becomes  

$$
\intop_{0}^{T}E(X(u)^{2})d u<\infty.
$$  

# Approximation.  

We seek a class of integrands suitably approximable by simple integrands. It turns out that:  

(i) The suitable class of integrands is the class of $(B([0,\infty))\otimes{\mathcal{F}})$ -measurable, $(\mathcal{F}_{t})$ - adapted processes $X$ with $\begin{array}{r}{\int_{0}^{t}I E\left(X(u)^{2}\right)d u<\infty}\end{array}$ for all $t>0$   
(ii) Each such $X$ may be approximated by a sequence of simple integrands $X_{n}$ so that the stochastic integral $\begin{array}{r}{I_{t}(X)=\int_{0}^{t}X d W}\end{array}$ may be defined as the limit of. $\begin{array}{r}{I_{t}(X_{n})=\int_{0}^{t}X_{n}d W}\end{array}$   
(iii) The properties from both lemmas above remain true for the stochastic integral $\textstyle\int_{0}^{t}X d W$ de fined by (i) and (ii).  

# Example.  

We calculate $\textstyle\int W(u)d W(u)$ . We start by approximating the integrand by a sequence of simple functions.  

$$
X_{n}(u)=\left\{\begin{array}{l l}{W(0)=0\quad}&{\mathrm{if}0\leq u\leq t/n,}\ {W(t/n)\quad}&{\mathrm{if}t/n<u\leq2t/n,}\ {\vdots\quad}&{\vdots}\ {W\left(\frac{(n-1)t}{n}\right)}&{\mathrm{if}(n-1)t/n<u\leq t.}\end{array}\right.
$$  

By definition,  

$$
\int_{0}^{t}W(u)d W(u)=\operatorname*{lim}_{n\to\infty}\sum_{k=0}^{n-1}W\left({\frac{k t}{n}}\right)\left(W{\bigg(}{\frac{(k+1)t}{n}}{\bigg)}-W{\bigg(}{\frac{k t}{n}}{\bigg)}\right).
$$  

Rearranging terms, we obtain for the sum on the right  

$$
\begin{array}{r l}&{\displaystyle\sum_{k=0}^{n-1}W\left(\frac{k t}{n}\right)\left(W\left(\frac{(k+1)t}{n}\right)-W\left(\frac{k t}{n}\right)\right)}\ {=}&{\displaystyle\frac{1}{2}W(t)^{2}-\frac{1}{2}\left[\sum_{k=0}^{n-1}\left(W\left(\frac{(k+1)t}{n}\right)-W\left(\frac{k t}{n}\right)\right)^{2}\right].}\end{array}
$$  

Since the second term approximates the quadratic variation of $W$ and hence tends to $t$ for $n\to\infty$ we find  

$$
\intop_{0}^{t}W(u)d W(u)=\frac{1}{2}W(t)^{2}-\frac{1}{2}t.
$$  

Note the contrast with ordinary (Newton-Leibniz) calculus! Ito calculus requires the second term on the right - the Ito correction term - which arises from the quadratic variation of. $W$  

One can construct a closely analogous theory for stochastic integrals with the Brownian integrator $W$ above replaced by a square-integrable martingale integrator. $M$ . The properties above hold, with (i) in Lemma replaced by.  

$$
{\cal E}\left[\left(\int_{0}^{t}X(u)d M(u)\right)^{2}\right]={\cal E}\left[\int_{0}^{t}X(u)^{2}d\langle M\rangle(u)\right].
$$  

# Quadratic Variation, Quadratic Covariation.  

We shall need to extend quadratic variation and quadratic covariation to stochastic integrals. The quadratic variation of $\begin{array}{r}{I_{t}(X)=\int_{0}^{t}X(u)d W(u)}\end{array}$ is $\begin{array}{r}{\int_{0}^{t}X(u)^{2}d u}\end{array}$ . This is proved in the same way as the case $X\equiv1$ , that $W$ has quadratic variation process $t$ . More generally, if. $\begin{array}{r}{Z(t)=\int_{0}^{t}X(u)d M(u)}\end{array}$ for a continuous martingale integrator $M$ , then $\begin{array}{r}{\left<Z\right>(t)=\int_{0}^{t}X^{2}(u)d\left<M\right>(u)}\end{array}$ . Similarly (or by) polarisation), if $\begin{array}{r}{Z_{i}(t)=\int_{0}^{t}X_{i}(u)d M_{i}(u)~(i=1,2)}\end{array}$ $\begin{array}{r}{\left\langle Z_{1},Z_{2}\right\rangle(t)=\int_{0}^{t}X_{1}(u)X_{2}(u)d\left\langle M_{1},M_{2}\right\rangle(u)}\end{array}$  

# 4.1.3 Ito's Lemma  

Suppose that $b$ is adapted and locally integrable (so $\begin{array}{r}{\int_{0}^{t}b(s)d s}\end{array}$ is defined as an ordinary integral), and $\sigma$ is adapted and measurable with $\begin{array}{r}{\int_{0}^{t}I E\left(\sigma(u)^{2}\right)d u<\infty}\end{array}$ for all $t$ (so $\begin{array}{r}{\int_{0}^{t}\sigma(s)d W(s)}\end{array}$ is defined as a stochastic integral). Then  

$$
X(t):=x_{0}+\intop_{0}^{t}b(s)d s+\intop_{0}^{t}\sigma(s)d W(s)
$$  

defines a stochastic process $X$ with $X(0)=x_{0}$ . It is customary, and convenient, to express such an equation symbolically in differential form, in terms of the stochastic differential equation  

$$
\begin{array}{r}{d X(t)=b(t)d t+\sigma(t)d W(t),~X(0)=x_{0}.}\end{array}
$$  

Now suppose $f:\mathbb{R}\to\mathbb{R}$ is of class $C^{2}$ . The question arises of giving a meaning to the stochastic differential $d f(X(t))$ of the process $f(X(t))$ , and finding it. Given a partition. $\mathcal{P}$ of $[0,t]$ , i.e. $0=t_{0}<t_{1}<...<t_{n}=t$ , we can use Taylor's formula to obtain.  

$$
\begin{array}{r c l}{f(X(t))-f(X(0))}&{=}&{\displaystyle\sum_{k=0}^{n-1}f(X(t_{k+1}))-f(X(t_{k}))}\ &{=}&{\displaystyle\sum_{k=0}^{n-1}f^{\prime}(X(t_{k}))\Delta X(t_{k})}\ &{+}&{\displaystyle\frac{1}{2}\sum_{k=0}^{n-1}f^{\prime\prime}(X(t_{k})+\theta_{k}\Delta X(t_{k}))(\Delta X(t_{k}))^{2}}\end{array}
$$  

with $0<\theta_{k}<1$ . We know that $\textstyle\sum(\Delta X(t_{k}))^{2}\to\langle X\rangle(t)$ in probability (so, taking a subsequence, with probability one), and with a little more effort one can prove  

$$
\sum_{k=0}^{n-1}f^{\prime\prime}(X(t_{k})+\theta_{k}\Delta X(t_{k}))(\Delta X(t_{k}))^{2}\to\int_{0}^{t}f^{\prime\prime}(X(u))d\left<X\right>(u).
$$  

The first sum is easily recognized as an approximating sequence of a stochastic integral; indeed, we find  

$$
\sum_{k=0}^{n-1}f^{\prime}(X(t_{k}))\Delta X(t_{k})\to\int_{0}^{t}f^{\prime}(X(u))d X(u).
$$  

So we have  

Theorem 4.1.2 (Basic Ito formula). If $X$ has stochastic differential given by 4.3 and $f\in C^{2}$ then $f(X)$ has stochastic differential  

$$
d f(X(t))=f^{\prime}(X(t))d X(t)+{\frac{1}{2}}f^{\prime\prime}(X(t))d\left<X\right>(t),
$$  

or writing out the integrals,  

$$
f(X(t))=f(x_{0})+\intop_{0}^{t}f^{\prime}(X(u))d X(u)+\frac{1}{2}\intop_{0}^{t}f^{\prime\prime}(X(u))d\left<X\right>(u).
$$  

More generally, suppose that $f:I R^{2}\to I R$ is a function, continuously differentiable once in. its first argument (which will denote time), and twice in its second argument (space): $f\in C^{1,2}$ By the Taylor expansion of a smooth function of several variables we get for $t$ close to $t_{0}$ (we use subscripts to denote partial derivatives: $f_{t}:=\partial f/\partial t$ $f_{t x}:=\partial^{2}f/\partial t\partial x$  

$$
\begin{array}{r c l}{{f(t,X(t))}}&{{=}}&{{f(t_{0},X(t_{0}))}}\ {{}}&{{}}&{{\displaystyle+(t-t_{0})f_{t}(t_{0},X(t_{0}))+(X(t)-X(t_{0}))f_{x}(t_{0},X(t_{0}))}}\ {{}}&{{}}&{{\displaystyle+\frac{1}{2}(t-t_{0})^{2}f_{t t}(t_{0},X(t_{0}))+\frac{1}{2}(X(t)-X(t_{0}))^{2}f_{x x}(t_{0},X(t_{0}))}}\ {{}}&{{}}&{{\displaystyle+(t-t_{0})(X(t)-X(t_{0}))f_{t x}(t_{0},X(t_{0}))+\ldots,}}\end{array}
$$  

which may be written symbolically as  

$$
d f=f_{t}d t+f_{x}d X+{\frac{1}{2}}f_{t t}(d t)^{2}+f_{t x}d t d X+{\frac{1}{2}}f_{x x}(d X)^{2}+....
$$  

In this, we substitute $d X(t)=b(t)d t+\sigma(t)d W(t)$ from above, to obtain  

$$
\begin{array}{l l l}{{d f}}&{{=}}&{{f_{t}d t+f_{x}(b d t+\sigma d W)}}\ {{}}&{{}}&{{\displaystyle+\frac{1}{2}f_{t t}(d t)^{2}+f_{t x}d t(b d t+\sigma d W)+\frac{1}{2}f_{x x}(b d t+\sigma d W)^{2}+...}}\end{array}
$$  

Now using the formal multiplication rules. $d t\cdot d t=0,d t\cdot d W=0,d W\cdot d W=d t$ (which are just shorthand for the corresponding properties of the quadratic variations, we expand  

$$
(b d t+\sigma d W)^{2}=\sigma^{2}d t+2b\sigma d t d W+b^{2}(d t)^{2}=\sigma^{2}d t+\mathrm{higher-order~terms}
$$  

to get finally  

$$
d f=\left(f_{t}+b f_{x}+{\frac{1}{2}}\sigma^{2}f_{x x}\right)d t+\sigma f_{x}d W+{\mathrm{higher-order~terms}}.
$$  

As above the higher-order terms are irrelevant, and summarising, we obtain Ito's lemma, the analogue for the Ito or stochastic calculus of the chain rule for ordinary (Newton-Leibniz) calculus:  

Theorem 4.1.3 (Ito's Lemma). If $X(t)$ has stochastic differential given by 4.3, then $f\mathrm{~=~}$ $f(t,X(t))$ has stochastic differential  

$$
d f=\left(f_{t}+b f_{x}+{\frac{1}{2}}\sigma^{2}f_{x x}\right)d t+\sigma f_{x}d W.
$$  

That is, writing. $f_{0}$ for $f(0,x_{0})$ , the initial value of $f$  

$$
f=f_{0}+\intop_{0}^{t}(f_{t}+b f_{x}+\frac{1}{2}\sigma^{2}f_{x x})d t+\intop_{0}^{t}\sigma f_{x}d W.
$$  

We will make good use of:  

Corollary 4.1.1. $\begin{array}{r}{E\left(f(t,X(t))\right)=f_{0}+\int_{0}^{t}E\left(f_{t}+b f_{x}+\frac{1}{2}\sigma^{2}f_{x x}\right)d t.}\end{array}$  

Proof. $\textstyle\int_{0}^{t}\sigma f_{2}d W$ is a stochastic integral, so a martingale, so its expectation is constant ( $=0$ as it starts at 0).  

The differential equation (4.1) above has the unique solution  

For, writing  

$$
S(t)=S(0)\exp\bigg\{\bigg(\mu-\frac{1}{2}\sigma^{2}\bigg)t+\sigma d W(t)\bigg\}.
$$  

$$
f(t,x):=\exp\bigg\{\bigg(\mu-\frac{1}{2}\sigma^{2}\bigg)t+\sigma x\bigg\},
$$  

we have  

$$
f_{t}=\left(\mu-\frac{1}{2}\sigma^{2}\right)f,\quad f_{x}=\sigma f,\quad f_{x x}=\sigma^{2}f,
$$  

and with $x=W(t)$ , one has  

$$
d x=d W(t),\quad(d x)^{2}=d t.
$$  

Thus Ito's lemma gives  

$$
\begin{array}{l c l}{\displaystyle d f(t,W(t))}&{=}&{f_{t}d t+f_{x}d W(t)+\displaystyle\frac{1}{2}f_{x x}(d W(t))^{2}}\ {\displaystyle}&{=}&{f\left(\left(\mu-\displaystyle\frac{1}{2}\sigma^{2}\right)d t+\sigma d W(t)+\displaystyle\frac{1}{2}\sigma^{2}d t\right)}\ {\displaystyle}&{=}&{f(\mu d t+\sigma d W(t)),}\end{array}
$$  

SO $f(t,W(t))$ is a solution of the stochastic differential equation, and the initial condition $f(0,W(0))=$ $S(0)$ as $W(0)=0$ , giving existence.  

# 4.1.4 Girsanov's Theorem  

Consider first independent $N(0,1)$ random variables $Z_{1},\ldots,Z_{n}$ on a probability space $(\Omega,{\mathcal{F}},I P)$ Given a vector $\gamma=(\gamma_{1},\dots,\gamma_{n})$ , consider a new probability measure $\tilde{\cal{I}}{}^{\dot{}{P}}$ on $(\Omega,{\mathcal{F}})$ defined by  

$$
\tilde{I P}(d\omega)=\exp\left\{\sum_{i=1}^{n}\gamma_{i}Z_{i}(\omega)-\frac{1}{2}\sum_{i=1}^{n}\gamma_{i}^{2}\right\}I P(d\omega).
$$  

As $\exp\{.\}>0$ and integrates to $^{1}$ , as $\begin{array}{r}{\int\exp\{\gamma_{i}Z_{i}\}d I P=\exp\{\frac{1}{2}\gamma_{i}^{2}\}}\end{array}$ , this is a probability measure.. It is also equivalent to. $\mathcal{W}$ (has the same null sets), again as the exponential term is positive. Also  

$$
\begin{array}{l l}{{}}&{{\displaystyle{\tilde{P}(Z_{i}\in d z_{i},\alpha_{i}=1,\ldots,n)}}}\ {{=}}&{{\displaystyle{\exp\left\{\sum_{i=1}^{n}\gamma_{i}Z_{i}-\frac{1}{2}\sum_{i=1}^{n}\gamma_{i}^{2}\right\}}P(Z_{i}\in d z_{i},i=1,\ldots,n)}}\ {{=}}&{{\displaystyle(2\pi)^{-\frac{n}{2}}\exp\left\{\sum_{i=1}^{n}\gamma_{i}z_{i}-\frac{1}{2}\sum_{i=1}^{n}\gamma_{i}^{2}-\frac{1}{2}\sum_{i=1}^{n}z_{i}^{2}\right\}\prod_{i=1}^{n}d z_{i}}}\ {{=}}&{{\displaystyle(2\pi)^{-\frac{n}{2}}\exp\left\{-\frac{1}{2}\sum_{i=1}^{n}(z_{i}-\gamma_{i})^{2}\right\}d z_{1}\ldots d z_{n}.}}\end{array}
$$  

This says that if the $Z_{i}$ are independent $N(0,1)$ under $\mathcal{W}$ , they are independent $N(\gamma_{i},1)$ under $\tilde{\cal{I}}{}_{P}^{}$ Thus the effect of the change of measure $\tilde{\mathcal{P}}\to\tilde{\mathcal{P}}$ , from the original measure $\mathcal{W}$ to the equivalent measure $\tilde{\cal{I}}{}_{P}^{}$ , is to change the mean, from $0=(0,\ldots,0)$ to $\gamma=(\gamma_{1},\dots,\gamma_{n})$  

This result extends to infinitely many dimensions - i.e., from random vectors to stochastic processes, indeed with random rather than deterministic means. Let $W~=~(W_{1},\dots,W_{d})$ be a $d$ -dimensional Brownian motion defined on a filtered probability space $(\Omega,{\mathcal{F}},I P,I F)$ with the filtration $\bar{\mu}$ satisfying the usual conditions.Let $(\gamma(t):0\leq t\leq T)$ be a measurable, adapted $d$ dimensional process with $\begin{array}{r}{\int_{0}^{T^{\prime}}\gamma_{i}(t)^{2}d t<\infty\quad a.s.,i=1,\ldots,d}\end{array}$ , and define the process ( $L(t):0\leq t\leq T,$ by  

$$
L(t)=\exp\left\{-\intop_{0}^{t}\gamma(s)^{\prime}d W(s)-\frac{1}{2}\intop_{0}^{t}\left\|\gamma(s)\right\|^{2}d s\right\}.
$$  

Then $L$ is continuous, and, being the stochastic exponential of $\begin{array}{r}{-\int_{0}^{t}\gamma(s)^{\prime}d W(s)}\end{array}$ , is a local martingale. Given sufficient integrability on the process $\gamma$ $L$ will in fact be a (continuous) martingale. For this, Novikov's condition suffices:.  

$$
L\left(\exp\left\{\frac{1}{2}\int_{0}^{T}\left\|\gamma(s)\right\|^{2}d s\right\}\right)<\infty.
$$  

We are now in the position to state a version of Girsanov's theorem, which will be one of our main tools in studying continuous-time financial market models.  

Theorem 4.1.4 (Girsanov). Let $\gamma$ be as above and satisfy Novikov's condition; let $L$ be the corresponding continuous martingale. Define the processes $\tilde{W_{i}}$ $i=1,\ldots,d$ by  

$$
\tilde{W}_{i}(t):=W_{i}(t)+\int_{0}^{t}\gamma_{i}(s)d s,\quad(0\leq t\leq T),\:\:\:i=1,\ldots,d.
$$  

Then under the equivalent probability measure $\tilde{\cal{I}}{}^{\tilde{}{P}}$ (defined on $\left(\Omega,\mathcal{F}_{T}\right)$ ) with Radon-Nikodym deriva-. tive  

$$
{\frac{d{\tilde{D}}}{d D}}=L(T),
$$  

the process $\tilde{W}=(\tilde{W}_{1},\dots,\tilde{W}_{d})$ is $d$ -dimensional Brownian motion.  

In particular, for. $\gamma(t)$ constant $(=\gamma$ ), change of measure by introducing the Radon-Nikodym derivative $\textstyle\exp\left\{-\gamma W(t)-{\frac{1}{2}}\gamma^{2}t\right\}$ corresponds to a change of drift from. $c$ to $c-\gamma$ . If $\mathbf{\mathcal{F}}=\left(\mathcal{F}_{t}\right)$ is the Brownian filtration (basically. $\mathcal{F}_{t}=\sigma(W(s),0\leq s\leq t)$ slightly enlarged to satisfy the usual. conditions) any pair of equivalent probability measures $\mathbb{Q}\sim\mathcal{N}$ on $\mathcal{F}=\mathcal{F}_{T}$ is a Girsanov pair, i.e..  

$$
\left.\frac{d\tilde{\pmb{Q}}}{d D}\right|_{\mathcal{F}_{t}}=\pmb{L}(t)
$$  

with $L$ defined as above. Girsanov's theorem (or the Cameron-Martin-Girsanov theorem) is formulated in varying degrees of generality, discussed and proved, e.g. in (Karatzas and Shreve 1991), \$3.5, (Protter 2004), III.6, (Revuz and Yor 1991), VIII, (Dothan 1990), 35.4 (discrete time), $\S11.6$ (continuous time).  

# 4.2 Financial Market Models  

# 4.2.1 The Financial Market Model  

We start with a general model of a frictionless (compare Chapter 1) security market where investors are allowed to trade continuously up to some fixed finite planning horizon $T$ . Uncertainty in the financial market is modelled by a probability space $(\Omega,{\mathcal{F}},I P)$ and a filtration $\mathbf{\mathcal{F}}=(\mathcal{F}_{t})_{0\leq t\leq T}$ satisfying the usual conditions of right-continuity and completeness. We assume that the $\sigma$ -field $\mathcal{F}_{0}$ is trivial, i.e. for every $A\in{\mathcal{F}}_{0}$ either $\textstyle P(A)=0$ or ${\cal{P}}(A)=1$ , and that $\mathcal{F}_{T}=\mathcal{F}$  

There are $d+1$ primary traded assets, whose price processes are given by stochastic processes $S_{0},\ldots,S_{d}$ .We assume that the processes $S_{0},\ldots,S_{d}$ represent the prices of some traded assets (stocks, bonds, or options).  

We have not emphasised so far that there was an implicit numeraire behind the prices $S_{0},\ldots,S_{d}$ it is the numeraire relevant for domestic transactions at time. $t$ . The formal definition of a numeraire. is very much as in the discrete setting..  

Definition 4.2.1. A numeraire is a price process $X(t)$ almost surely strictly positive for each $t\in[0,T]$  

We assume now that. $S_{0}(t)$ is a non-dividend paying asset, which is (almost surely) strictly. positive and use $S_{0}$ as numeraire. Historically' (see (Harrison and Pliska 1981) the money market account $B(t)$ , given by $B(t)=e^{r(t)}$ with a positive deterministic process $r(t)$ and $r(0)=0$ was used as a numeraire, and the reader may think of. $S_{0}(t)$ as being $B(t)$  

Our principal task will be the pricing and hedging of contingent claims, which we model as ${\mathcal{F}}_{T}$ -measurable random variables. This implies that the contingent claims specify a stochastic cash-flow at time $T$ and that they may depend on the whole path of the underlying in. $[0,T]$ - because ${\mathcal{F}}_{T}$ contains all that information. We will often have to impose further integrability conditions on the contingent claims under consideration. The fundamental concept in (arbitrage) pricing and hedging contingent claims is the interplay of self-financing replicating portfolios and risk-neutral probabilities. Although the current setting is on a much higher level of sophistication, the key ideas remain the same.  

We call an $\textstyle\mathit{\Pi}\mathit{{H}}^{d+1}$ -valued predictable process  

$$
\varphi(t)=(\varphi_{0}(t),\ldots,\varphi_{d}(t)),\quad t\in[0,T]
$$  

with $\begin{array}{r}{\int_{0}^{T}L E(\varphi_{0}(t))d t<\infty,\sum_{i=0}^{d}\int_{0}^{T}L E(\varphi_{i}^{2}(t))d t<\infty}\end{array}$ a trading strategy (or dynamic portfolio process). Here. $\varphi_{i}(t)$ denotes the number of shares of asset. $i$ held in the portfolio at time. $t$ - to be determined on the basis of information available before time $t$ ; i.e. the investor selects his time $t$ portfolio after observing the prices. $S(t-)$ . The components $\varphi_{i}(t)$ may assume negative as well. as positive values, reflecting the fact that we allow short sales and assume that the assets are perfectly divisible..  

Definition 4.2.2. (i) The value of the portfolio $\varphi$ at time $t$ is given by the scalar product  

$$
V_{\varphi}(t):=\varphi(t)\cdot S(t)=\sum_{i=0}^{d}\varphi_{i}(t)S_{i}(t),t\in[0,T].
$$  

The process $V_{\varphi}(t)$ is called the value process, or wealth process, of the trading strategy $\varphi$ (ii) The gains process. $G_{\varphi}(t)$ is defined by.  

$$
G_{\varphi}(t):=\intop_{0}^{t}\varphi(u)d S(u)=\sum_{i=0}^{d}\intop_{0}^{t}\varphi_{i}(u)d S_{i}(u).
$$  

(iii) $A$ trading strategy $\varphi$ is called self-financing if the wealth process $V_{\varphi}(t)$ satisfies  

$$
V_{\varphi}(t)=V_{\varphi}(0)+G_{\varphi}(t)\mathrm{\it~for~}a l l t\in[0,T].
$$  

Remark 4.2.1. (i) The financial implications of the above equations are that all changes in the wealth of the portfolio are due to capital gains, as opposed to withdrawals of cash or injections of new funds.  

(ii) The definition of a trading strategy includes regularity assumptions in order to ensure the existence of stochastic integrals.  

Using the special numeraire $S_{0}(t)$ we consider the discounted price process  

$$
\tilde{S}(t):=\frac{S(t)}{S_{0}(t)}=(1,\tilde{S}_{1}(t),\dots\tilde{S}_{d}(t))
$$  

with $\tilde{S}_{i}(t)=S_{i}(t)/S_{0}(t),i=1,2,\ldots,d$ .Furthermore, the discounted wealth process $\tilde{V}_{\varphi}(t)$ is given by  

$$
\tilde{V}_{\varphi}(t):=\frac{V_{\varphi}(t)}{S_{0}(t)}=\varphi_{0}(t)+\sum_{i=1}^{d}\varphi_{i}(t)\tilde{S}_{i}(t)
$$  

and the discounted gains process $\ddot{G}_{\varphi}(t)$ is  

$$
\tilde{G}_{\varphi}(t):=\sum_{i=1}^{d}\int_{0}^{t}\varphi_{i}(t)d\tilde{S}_{i}(t).
$$  

Observe that $\tilde{G}_{\varphi}(t)$ does not depend on the numeraire component $\varphi_{0}$  

It is convenient to reformulate the self-financing condition in terms of the discounted processes:  

'roposition 4.2.1. Let. $\varphi$ be a trading strategy. Then $\varphi$ if self-financing if and only if  

$$
\tilde{V}_{\varphi}(t)=\tilde{V}_{\varphi}(0)+\tilde{G}_{\varphi}(t).
$$  

Of course, $V_{\varphi}(t)\geq0$ if and only if $\tilde{V}_{\varphi}(t)\geq0$  

The proof follows by the numeraire invariance theorem using $S_{0}$ as numeraire.  

Remark 4.2.2. The above result shows that a self-financing strategy is completely determined by its initial value and the components. $\varphi_{1},\ldots,\varphi_{d}$ . In other words, any set of predictable processes. $\varphi_{1},\ldots,\varphi_{d}$ such that the stochastic integrals $\textstyle\int\varphi_{i}d{\tilde{S}}_{i},i=1,\ldots,d$ exist can be uniquely extended to a self-financing strategy. $\varphi$ with specified initial value $\tilde{V}_{\varphi}(0)=v$ by setting the cash holding as  

$$
\varphi_{0}(t)=v+\sum_{i=1}^{d}\intop_{0}^{t}\varphi_{i}(u)d\Tilde{S}_{i}(u)-\sum_{i=1}^{d}\varphi_{i}(t)\Tilde{S}_{i}(t),t\in[0,T].
$$  

# 4.2.2 Equivalent Martingale Measures  

We develop a relative pricing theory for contingent claims. Again the underlying concept is the link between the no-arbitrage condition and certain probability measures. We begin with:  

Definition 4.2.3. A self-financing trading strategy $\varphi$ is called an arbitrage opportunity if the wealth process $V_{\varphi}$ satisfies the following set of conditions:  

$$
0,\quad D(V_{\varphi}(T)\geq0)=1,\quad a n d\quad D(V_{\varphi}(T)>0)>
$$  

Arbitrage opportunities represent the limitless creation of wealth through risk-free profit and thus should not be present in a well-functioning market.  

The main tool in investigating arbitrage opportunities is the concept of equivalent martingale measures:  

Definition 4.2.4. We say that a probability measure $\mathbb{Q}$ defined on $(\Omega,{\mathcal{F}})$ is an equivalent mar-.   
tingale measure if:. (i) $\mathbb{Q}$ is equivalent to. $\mathcal{W}$   
(ii) the discounted price process $\tilde{S}$ is a $\mathbb{Q}$ martingale.  

We denote the set of martingale measures by $\mathcal{P}$  

A useful criterion in determining whether a given equivalent measure is indeed a martingale measure is the observation that the growth rates relative to the numeraire of all given primary. assets under the measure in question must coincide. For example, in the case. $S_{0}(t)\stackrel{}{=}B(t)$ we have:  

Lemma 4.2.1. Assume $S_{0}(t)=B(t)=e^{r(t)}$ , then $\mathbb{Q}\sim I P$ is a martingale measure if and only if every asset price process. $S_{i}$ has price dynamics under $\mathbb{Q}$ of the form.  

$$
d S_{i}(t)=r(t)S_{i}(t)d t+d M_{i}(t),
$$  

where $M_{i}$ is a $\mathbb{Q}$ -martingale.  

The proof is an application of Ito's formula.  

In order to proceed we have to impose further restrictions on the set of trading strategies.  

Definition 4.2.5. A self-financing trading strategy $\varphi$ is called tame (relative to the numeraire. $S_{0}$ if  

$$
\begin{array}{r}{\tilde{V}_{\varphi}(t)\geq0~f o r~a l l t\in[0,T].}\end{array}
$$  

We use the notation $\Phi$ for the set of tame trading strategies.  

We next analyse the value process under equivalent martingale measures for such strategies  

Proposition 4.2.2. For $\varphi\in\Phi\tilde{V}_{\varphi}(t)$ is a martingale under each $\mathbb{Q}\in\mathcal{P}$  

This observation is the key to our first central result:  

Theorem 4.2.1. Assume $\mathcal{P}\neq\emptyset$ . Then the market model contains no arbitrage opportunities in $\Phi$  

Proof. For any. $\varphi\in\Phi$ and under any. $\mathbb{Q}\in\mathcal{P}\tilde{V}_{\varphi}(t)$ is a martingale. That is,  

$$
{\mathbb E}_{\pmb{Q}}\left(\tilde{V}_{\varphi}(t)|\mathcal{F}_{u}\right)=\tilde{V}_{\varphi}(u),\mathrm{for~all}\quad u\le t\le T.
$$  

For $\varphi\in\Phi$ to be an arbitrage opportunity we must have $\tilde{V}_{\varphi}(0)=V_{\varphi}(0)=0$ . Now  

$$
E_{Q}\left(\tilde{V}_{\varphi}(t)\right)=0,\mathrm{forall}0\leq t\leq T.
$$  

Now $\varphi$ is tame, so $\tilde{V}_{\varphi}(t)\geq0,0\leq t\leq T$ , implying ${\cal I}E_{\bf{\boldsymbol{Q}}}\left(\tilde{V}_{\varphi}(t)\right)=0$ $0\leq t\leq T$ , and in particular ${\cal E}_{\cal Q}\left(\tilde{V}_{\varphi}(T)\right)=0$ . But an arbitrage opportunity $\varphi$ also has to satisfy $\begin{array}{r}{P\left(V_{\varphi}(T)\ge0\right)=1}\end{array}$ , and since $\mathbb{Q}\sim\mathcal{N}$ , this means $\mathbb{Q}\left(V_{\varphi}(T)\ge0\right)=1$ . Both together yield  

$$
\begin{array}{r}{Q\left(V_{\varphi}(T)>0\right)=I P\left(V_{\varphi}(T)>0\right)=0,}\end{array}
$$  

and hence the result follows.  

# 4.2.3 Risk-neutral Pricing  

We now assume that there exists an equivalent martingale measure. $\b{\mathcal{M}}^{*}$ which implies that there are no arbitrage opportunities with respect to. $\Phi$ in the financial market model. Until further notice. we use $\mathit{\Pi}\mathit{\perp}\mathit{\Psi}$ as our reference measure, and when using the term martingale we always assume that the underlying probability measure is $\b{\mathcal{M}}^{*}$ . In particular, we restrict our attention to contingent. claims $X$ such that $X/S_{0}(T)\in L^{1}(\mathcal{F},I P^{*})$  

We now define a further subclass of trading strategies:  

Definition 4.2.6. A self-financing trading strategy is called ( $\b{\mathcal{P}}^{*}$ -) admissible if the relative. $\varphi$   
gains process  

$$
\tilde{G}_{\varphi}(t)=\int_{0}^{t}\varphi(u)d\tilde{S}(u)
$$  

is a ( $\b{\mathcal{P}}^{*}$ -) martingale. The class of all $(\varPsi^{*}-)$ admissible trading strategies is denoted $\Phi({\cal P}^{*})$  

By definition $\tilde{S}$ is a martingale, and $\tilde{G}$ is the stochastic integral with respect to $\tilde{S}$ . We see that any sufficiently integrable processes $\varphi_{1},\ldots,\varphi_{d}$ give rise to $\b{\mathcal{M}}^{*}$ -admissible trading strategies. We can repeat the above argument to obtain  

Theorem 4.2.2. The financial market model $\mathcal{M}$ contains no arbitrage opportunities in. $\Phi(\boldsymbol{P}^{*})$  

Under the assumption that no arbitrage opportunities exist, the question of pricing and hedg-. ing a contingent claim reduces to the existence of replicating self-financing trading strategies. Formally:  

Definition 4.2.7. (i) A contingent claim $X$ is called attainable if there exists at least one admissible trading strategy such that  

$$
V_{\varphi}(T)=X.
$$  

We call such a trading strategy $\varphi$ a replicating strategy for $X$ (ii) The financial market model $\mathcal{M}$ is said to be complete if any contingent claim is attainable.  

Again we emphasise that this depends on the class of trading strategies. On the other hand, it does not depend on the numeraire: it is an easy exercise in the continuous asset-price process case to show that if a contingent claim is attainable in a given numeraire it is also attainable in any other numeraire and the replicating strategies are the same.  

If a contingent claim. $X$ is attainable, $X$ can be replicated by a portfolio $\varphi\in\Phi(D^{*})$ . This means that holding the portfolio and holding the contingent claim are equivalent from a financial point of view. In the absence of arbitrage the (arbitrage) price process. $\Pi_{X}(t)$ of the contingent. claim must therefore satisfy.  

$$
\Pi_{X}(t)=V_{\varphi}(t).
$$  

Of course the questions arise of what will happen if $X$ can be replicated by more than one portfolio, and what the relation of the price process to the equivalent martingale measure(s) is. The following central theorem is the key to answering these questions:  

Theorem 4.2.3 (Risk-Neutral Valuation Formula). The arbitrage price process of any attainable claim is given by the risk-neutral valuation formula.  

$$
\Pi_{X}(t)=S_{0}(t)E_{I P^{*}}\left[\left.\frac{X}{S_{0}(T)}\right|\mathcal{F}_{t}\right].
$$  

The uniqueness question is immediate from the above theorem:  

Corollary 4.2.1. For any two replicating portfolios $\varphi,\psi\in\Phi(D^{*})$ we hav  

$$
V_{\varphi}(t)=V_{\psi}(t).
$$  

Proof of Theorem 4.2.3 Since $X$ is attainable, there exists a replicating strategy $\varphi\in\Phi(D^{*})$ such that $V_{\varphi}(T)=X$ and $\Pi_{X}(t)=V_{\varphi}(t)$ . Since $\varphi\in\Phi(D^{*})$ the discounted value process $\dot{V}_{\varphi}(t)$ is a martingale, and hence  

$$
\begin{array}{r c l}{{\Pi_{X}(t)}}&{{=}}&{{V_{\varphi}(t)=S_{0}(t)\tilde{V}_{\varphi}(t)}}\ {{}}&{{}}&{{}}\ {{}}&{{=}}&{{S_{0}(t){\cal{L}}_{I P^{*}}\left[\left.\tilde{V}_{\varphi}(T)\right|\mathcal{F}_{t}\right]=S_{0}(t){\cal{L}}_{I P^{*}}\left[\left.\frac{V_{\varphi}(T)}{S_{0}(T)}\right|\mathcal{F}_{t}\right]}}\ {{}}&{{}}&{{}}\ {{}}&{{=}}&{{S_{0}(t){\cal{L}}_{I P^{*}}\left[\left.\frac{X}{S_{0}(T)}\right|\mathcal{F}_{t}\right].}}\end{array}
$$  

# 4.2.4 The Black-Scholes Model  

# The Model  

We concentrate on the classical Black-Scholes model  

$$
\begin{array}{r c l l}{d B(t)}&{=}&{r B(t)d t,\quad}&{B(0)=1,\quad}\ {d S(t)}&{=}&{S(t)\left(b d t+\sigma d W(t)\right),\quad}&{S(0)=p\in(0,\infty),}\end{array}
$$  

with constant coefficients $b\in I R,r,\sigma\in I R_{+}$ . We write as usual $\tilde{S}(t)=S(t)/B(t)$ for the discounted stock price process (with the bank account being the natural numeraire), and get from Ito's formula  

$$
d\tilde{S}(t)=\tilde{S}(t)\{(b-r)d t+\sigma d W(t)\}.
$$  

# Equivalent Martingale Measure  

Because we use the Brownian filtration any pair of equivalent probability measures $I P\sim\mathbb{Q}$ on ${\mathcal{F}}_{T}$ is a Girsanov pair, i.e..  

$$
\left.\frac{d\pmb{Q}}{d D}\right|_{\mathcal{F}_{t}}=L(t)
$$  

with  

$$
L(t)=\exp\left\{-\intop_{0}^{t}\gamma(s)d W(s)-\frac{1}{2}\intop_{0}^{t}\gamma(s)^{2}d s\right\},
$$  

and ( $\gamma(t):0\leq t\leq T)$ a measurable, adapted $d$ dimensional process with $\begin{array}{r}{\int_{0}^{T}\gamma(t)^{2}d t<\infty}\end{array}$ a.8.. By Girsanov's theorem 4.1.4 we have  

$$
d W(t)=d\tilde{W}(t)-\gamma(t)d t,
$$  

where $\tilde{W}$ is a $\mathbb{Q}$ -Wiener process. Thus the $\mathbb{Q}$ -dynamics for $\tilde{S}$ are  

$$
d\tilde{S}(t)=\tilde{S}(t)\left\{(b-r-\sigma\gamma(t))d t+\sigma d\tilde{W}(t)\right\}.
$$  

Since $\tilde{S}$ has to be a martingale under $\mathbb{Q}$ we must have  

$$
b-r-\sigma\gamma(t)=0\quad t\in[0,T],
$$  

and so we must choose  

$$
\gamma(t)\equiv\gamma=\frac{b-r}{\sigma},
$$  

(the 'market price of risk'). Indeed, this argument leads to a unique martingale measure, and we will make use of this fact later on. Using the product rule, we find the. $\mathbb{Q}$ dynamics of $S$ aS  

$$
d S(t)=S(t)\left\{r d t+\sigma d{\tilde{W}}\right\}.
$$  

We see that the appreciation rate $b$ is replaced by the interest rate $r$ , hence the terminology risk-neutral (or yield-equating) martingale measure.  

We also know that we have a unique martingale measure $\b{\mathcal{M}}^{*}$ (recall $\gamma=(b-r)/\sigma$ in Girsanov's transformation).  

# Pricing and Hedging Contingent Claims  

Recall that a contingent claim. $X$ is a ${\mathcal{F}}_{T}$ -measurable random variable such that. $X/B(T)~\in$ $L^{1}(\Omega,\mathcal{F}_{T},D^{*})$ .(We write $\mathbf{\xi}\mathbf{\mathcal{L}}^{*}$ for ${\cal{L}}_{I P^{*}}$ in this section.) By the risk-neutral valuation principle the price of a contingent claim $X$ is given by.  

$$
\Pi_{X}(t)=e^{\{-r(T-t)\}}I E^{*}\left[X|\mathcal{F}_{t}\right],
$$  

with $\mathbf{\nabla}\mu^{*}$ given via the Girsanov density  

$$
L(t)=\exp\left\{-\left(\frac{b-r}{\sigma}\right)W(t)-\frac{1}{2}\left(\frac{b-r}{\sigma}\right)^{2}t\right\}.
$$  

Now consider a European call with strike. $K$ and maturity $T$ on the stock $S$ (so $\Phi(T)=(S(T)-$ $K)^{+}$ ), we can evaluate the above expected value (which is easier than solving the Black-Scholes partial differential equation) and obtain:  

Proposition 4.2.3 (Black-Scholes Formula). The Black-Scholes price process of a European call is given by.  

$$
C(t)=S(t){N}({d_{1}}(S(t),T-t))-K{e^{-r(T-t)}}{N}({d_{2}}(S(t),T-t)).
$$  

The functions $d_{1}(s,t)$ and $d_{2}(s,t)$ are given by  

$$
\begin{array}{l c l}{{d_{1}(s,t)}}&{{=}}&{{\displaystyle\frac{\log(s/K)+(r+\frac{\sigma^{2}}{2})t}{\sigma\sqrt{t}},}}\ {{}}&{{}}&{{}}\ {{d_{2}(s,t)}}&{{=}}&{{d_{1}(s,t)-\sigma\sqrt{t}=\displaystyle\frac{\log(s/K)+(r-\frac{\sigma^{2}}{2})t}{\sigma\sqrt{t}}}}\end{array}
$$  

Observe that we have already deduced this formula as a limit of a discrete-time setting.  

To obtain a replicating portfolio we start in the discounted setting. We have from the riskneutral valuation principle  

$$
M(t)=\exp\left\{-r T\right\}L E^{*}\left[\Phi(S(T))|\mathcal{F}_{t}\right].
$$  

Now we use Ito's lemma to find the dynamics of the $\b{\mathcal{P}}^{*}$ -martingale $M(t)=G(t,S(t))$  

$$
d M(t)=\sigma S(t)G_{s}(t,S(t))d\tilde{W}(t).
$$  

Using this representation, we get for the stock component of the replicating portfolio  

$$
h(t)=\sigma S(t)G_{s}(t,S(t)).
$$  

Now for the discounted assets the stock component is  

$$
\begin{array}{r}{\varphi_{1}(t)=G_{s}(t,S(t))B(t),}\end{array}
$$  

and using the self-financing condition the cash component is  

$$
\varphi_{0}(t)=G(t,S(t))-G_{s}(t,S(t))S(t).
$$  

To transfer this portfolio to undiscounted values we multiply it by the discount factor, i.e $F(t,S(t))$ $=B(t)G(t,S(t))$ and get:  

Proposition 4.2.4. The replicating strategy in the classical Black-Scholes model is given by  

$$
\begin{array}{l c l}{\varphi_{0}}&{=}&{\displaystyle\frac{F(t,S(t))-F_{s}(t,S(t))S(t)}{B(t)},}\ {\varphi_{1}}&{=}&{F_{s}(t,S(t)).}\end{array}
$$  

We can also use an arbitrage approach to derive the Black-Scholes formula. For this consider a self-financing portfolio which has dynamics  

$$
)+\varphi_{1}(t)d S(t)=(\varphi_{0}(t)r B(t)+\varphi_{1}(t)\mu S(t))d t+\varphi
$$  

Assume that the portfolio value can be written as  

$$
V_{\varphi}(t)=V(t)=f(t,S(t))
$$  

for a suitable function $f\in C^{1,2}$ . Then by Ito's formula  

$$
d V(t)=(f_{t}(t,S_{t})+f_{x}(t,S_{t})S_{t}\mu+\frac{1}{2}S_{t}^{2}\sigma^{2}f_{x x}(t,S_{t}))d t+f_{x}(t,S_{t})\sigma S_{t}d W_{t}.
$$  

Now we match the coefficients and find  

$$
\varphi_{1}(t)=f_{x}(t,S_{t})
$$  

and  

$$
\varphi_{0}(t)=\frac{1}{r B(t)}(f_{t}(t,S_{t})+\frac{1}{2}\sigma^{2}S_{t}^{2}f_{x x}(t,S_{t})).
$$  

Then looking at the total portfolio value we find that $f(t,x)$ must satisfy the following PDE  

$$
f_{t}(t,x)+r x f_{x}(t,x)+{\frac{1}{2}}\sigma^{2}x^{2}f_{x x}(t,x)-r f(t,x)=0
$$  

and initial condition $f(T,x)=(x-K)^{+}$  

In their original paper Black and Scholes (1973), Black and Scholes used an arbitrage pricing approach (rather than our risk-neutral valuation approach) to deduce the price of a European call as the solution of a partial differential equation (we call this the PDE approach). The idea is as follows: start by assuming that the option price $C(t)$ is given by $C(t)=f(t,S(t))$ for some sufficiently smooth function. $f:I R_{+}\times[0,T]\rightarrow I R$ . By Ito's formula (Theorem 4.1.3) we find for the dynamics of the option price process (observe that we work under $\mathcal{W}$ $d S=S(b d t+\sigma d W))$  

$$
d C=\left\{f_{t}(t,S)+f_{s}(t,S)S b+\frac{1}{2}f_{s s}(t,S)S^{2}\sigma^{2}\right\}d t+f_{s}S\sigma d W.
$$  

Consider a portfolio $\psi$ consisting of a short position in. $\psi_{1}(t)=f_{s}(t,S(t))$ stocks and a long position in $\psi_{2}(t)=1$ call and assume the portfolio is self-financing. Then its value process is  

$$
V_{\psi}(t)=-\psi_{1}(t)S(t)+C(t),
$$  

and by the self-financing condition we have (to ease the notation we omit the arguments)  

$$
\begin{array}{l c l}{{d V_{\psi}}}&{{=}}&{{-\psi_{1}d S+d C}}\ {{}}&{{}}&{{}}\ {{}}&{{=}}&{{-f_{s}(S b d t+S\sigma d W)+\displaystyle\left(f_{t}+f_{s}S b+\frac{1}{2}f_{s s}S^{2}\sigma^{2}\right)d t+f_{s}S\sigma d W}}\ {{}}&{{}}&{{}}\ {{}}&{{=}}&{{\displaystyle\left(f_{t}+\frac{1}{2}f_{s s}S^{2}\sigma^{2}\right)d t.}}\end{array}
$$  

So the dynamics of the value process of the portfolio do not have any exposure to the driving Brownian motion, and its appreciation rate in an arbitrage-free world must therefore equal the risk-free rate, i.e.  

$$
d V_{\psi}(t)=r V_{\psi}(t)d t=\left(-r f_{s}S+r C\right)d t.
$$  

Comparing the coefficients and using $C(t)=f(t,S(t))$ , we must have  

$$
-r S f_{s}+r f=f_{t}+\frac{1}{2}\sigma^{2}S^{2}f_{s s}.
$$  

This leads again to the Black-Scholes partial differential equation (4.8) for $f$ , i.e.  

$$
f_{t}+r s f_{s}+\frac{1}{2}\sigma^{2}s^{2}f_{s s}-r f=0.
$$  

Since $C(T)=(S(T)-K)^{+}$ we need to impose the terminal condition $f(s,T)=(s-K)^{+}$ for all $s\in\mathbb{R}^{+}$  

# Note.  

One point in the justification of the above argument is missing: we have to show that the trading strategy short $\psi_{1}$ stocks and long one call is self-financing. In fact, this is not true, since $\psi_{1}=$ $\psi_{1}(t,S(t))$ is dependent on the stock price process. Formally, for the self-financing condition to be true we must have  

$$
d V_{\psi}(t)=d(\psi_{1}(t)S(t))+d C(t)=\psi_{1}(t)d S(t)+d C(t).
$$  

Now $\psi(t)=\psi(t,S(t))$ depends on the stock price and so we have  

$$
d(\psi_{1}(t,S(t))S(t))=\psi_{1}(t)d S(t)+S(t)d\psi_{1}(t,S(t))+d\left<\psi_{1},S\right>(t).
$$  

We see that the portfolio $\psi$ is self-financing, if  

$$
S(t)d\psi_{1}(t,S(t))+d\left\langle\psi_{1},S\right\rangle(t)=0.
$$  

It is an exercise in Ito calculus to show that this is not the case.  

# 4.2.5 The Greeks  

We will now analyse the impact of the underlying parameters in the standard Black-Scholes model on the prices of call and put options. The Black-Scholes option values depend on the (current) stock price, the volatility, the time to maturity, the interest rate and the strike price. The sensitivities of the option price with respect to the first four parameters are called the Greeks and are widely used for hedging purposes. We can determine the impact of these parameters by taking partial derivatives. Recall the Black-Scholes formula for a European call (4.7):  

$$
C(0)=C(S,T,K,r,\sigma)=S N(d_{1}(S,T))-K e^{-r T}N(d_{2}(S,T)),
$$  

with the functions $d_{1}(s,t)$ and $d_{2}(s,t)$ given by  

One obtains  

$$
\begin{array}{l c l}{{d_{1}(s,t)}}&{{=}}&{{\displaystyle\frac{\log(s/K)+(r+\frac{\sigma^{2}}{2})t}{\sigma\sqrt{t}},}}\ {{}}&{{}}&{{}}\ {{d_{2}(s,t)}}&{{=}}&{{d_{1}(s,t)-\sigma\sqrt{t}=\displaystyle\frac{\log(s/K)+(r-\frac{\sigma^{2}}{2})t}{\sigma\sqrt{t}}.}}\end{array}
$$  

$$
\begin{array}{r c l}{{\Delta}}&{{:=}}&{{\displaystyle\frac{\partial C}{\partial S}}}&{{=\phantom{-}N(d_{1})>0,}}\ {{\displaystyle\mathcal{V}}}&{{:=}}&{{\displaystyle\frac{\partial C}{\partial\sigma}}}&{{=\phantom{-}S\sqrt{T}n(d_{1})>0,}}\ {{\Theta}}&{{:=}}&{{\displaystyle\frac{\partial C}{\partial T}}}&{{=\phantom{-}\displaystyle\frac{S\sigma}{2\sqrt{T}}n(d_{1})+K r e^{-r T}N(d_{2})>0,}}\ {{\rho}}&{{:=}}&{{\displaystyle\frac{\partial C}{\partial r}}}&{{=\phantom{-}T K e^{-r T}N(d_{2})>0,}}\ {{\Gamma}}&{{:=}}&{{\displaystyle\frac{\partial^{2}C}{\partial S^{2}}}}&{{=\displaystyle\frac{n(d_{1})}{S\sigma\sqrt{T}}>0.}}\end{array}
$$  

(As usual $N$ is the cumulative normal distribution function and. $n$ is its density.) From the definitions it is clear that $\Delta$ delta - measures the change in the value of the option compared with the change in the value of the underlying asset, $\nu$ vega - measures the change of the. option compared with the change in the volatility of the underlying, and similar statements hold for $\Theta$ theta - and $\rho$ rho (observe that these derivatives are in line with our arbitrage-based. considerations in 1.3). Furthermore,. $\Delta$ gives the number of shares in the replication portfolio for a call option (see Proposition 4.2.4), so. $\Gamma$ measures the sensitivity of our portfolio to the change. in the stock price..  

The Black-Scholes partial differential equation (4.8) can be used to obtain the relation between the Greeks, i.e. (observe that. $\Theta$ is the derivative of. $C$ , the price of a European call, with respect to the time to expiry. $T-t$ , while in the Black-Scholes PDE the partial derivative with respect to the current time $t$ appears)  

$$
r C=\frac{1}{2}s^{2}\sigma^{2}\Gamma+r s\Delta-\Theta.
$$  

Let us now compute the dynamics of the call option's price $C(t)$ under the risk-neutral martingale measure $\b{\mathcal{M}}^{*}$ . Using formula (4.9) we find  

$$
d C(t)=r C(t)d t+\sigma N(d_{1}(S(t),T-t))S(t)d\tilde{W}(t).
$$  

Defining the elasticity coefficient of the option's price as  

$$
\eta^{c}(t)=\frac{\Delta(S(t),T-t)S(t)}{C(t)}=\frac{N(d_{1}(S(t),T-t))}{C(t)}
$$  

we can rewrite the dynamics as  

$$
d C(t)=r C(t)d t+\sigma\eta^{c}(t)C(t)d\tilde{W}(t).
$$  

So, as expected in the risk-neutral world, the appreciation rate of the call option equals the riskfree rate $r$ . The volatility coefficient is. $\sigma\eta^{c}$ , and hence stochastic. It is precisely this feature that. causes difficulties when assessing the impact of options in a portfolio..  

# 4.2.6 Barrier Options  

The question of whether or not a particular stock will attain a particular level within a specified.   
period has long been an important one for risk managers. From at least 1967 - predating both CBOE and Black-Scholes in 1973 - practitioners have sought to reduce their exposure to specific.   
risks of this kind by buying options designed with such barrier-crossing events in mind. As usual,.   
the motivation is that buying specific options - that is, taking out specific insurance - is a cheaper.   
way of covering oneself against a specific danger than buying a more general one..  

One-barrier options specify a stock-price level,. $H$ say, such that the option pays ('knocks in'). or not ('knocks out') according to whether or not level. $H$ is attained, from below ('up') or above. ('down'). There are thus four possibilities: 'up and in', 'up and out', 'down and in' and 'down and out'. Since barrier options are path-dependent (they involve the behaviour of the path, rather than just the current price or price at expiry), they may be classified as exotic; alternatively, the four basic one-barrier types above may be regarded as 'vanilla barrier' options, with their more complicated variants, described below, as 'exotic barrier' options. Note that holding both a knock-in option and the corresponding knock-out is equivalent to the corresponding vanilla option with the barrier removed. The sum of the prices of the knock-in and the knock-out is thus the price of the vanilla - again showing the attractiveness of barrier options as being cheaper than their vanilla counterparts.  

A barrier option is often designed to pay a $r e b a t e\mathrm{~-~}\mathrm{a~}$ sum specified in advance - to compensate the holder if the option is rendered otherwise worthless by hitting/not hitting the barrier. We restrict attention to zero rebate here for simplicity.  

Consider, to be specific, a down-and-out call option with strike $K$ and barrier $H$ (the other possibilities may be handled similarly). The payoff is (unless otherwise stated min and max are Over $[0,T]$  

$$
(S(T)-K)^{+}\mathbf{1}_{\left\{\operatorname*{min}S(.)\geq H\right\}}=(S(T)-K)\mathbf{1}_{\left\{S(T)\geq K,\operatorname*{min}S(.)\geq H\right\}},
$$  

so by risk-neutral pricing the value of the option is  

$$
D O C_{K,H}:=I E\left[e^{-r T}(S(T)-K)\mathbf{1}_{\left\{S(T)\geq K,\operatorname*{min}S(.)\geq H\right\}}\right],
$$  

where $S$ is geometric Brownian motion,. $\begin{array}{r}{S(t)=p_{0}\exp\{(\mu-\frac{1}{2}\sigma^{2}t)+\sigma W(t)\}}\end{array}$ . Write $c:=\mu-{\textstyle\frac{1}{2}}\sigma^{2}/\sigma$ then $\operatorname*{min}S(.)\geq H$ iff $\operatorname*{min}(c t+W(t))\geq\sigma^{-1}\log(H/p_{0})$ .Writing $X$ for $X(t):=c t+W(t)-\mathrm{driftir}$ ig Brownian motion with drift $c$ $m$ $M$ for its minimum and maximum processes  

$$
m(t):=\operatorname*{min}\{X(s):s\in[0,t]\},\quad M(t):=\operatorname*{max}\{X(s):s\in[0,t]\}.
$$  

the payoff function involves the bivariate process $(X,m)$ , and the option price involves the joint.   
law of this process..  

Consider first the case $c=0$ : we require the joint law of standard Brownian motion and its maximum or minimum, $(W,M)$ or $(W,m)$ . Taking $(W,M)$ for definiteness, we start the Brownian. motion $W$ at the origin at time zero, choose a level. $b>0$ , and run the process until the first-passage. time (see Exercise 5.2)  

$$
\tau(b):=\operatorname*{inf}\{t\geq0:W(t)\geq b\}
$$  

at which the level $b$ is first attained. This is a stopping time, and we may use the strong Markov property for $W$ at time $\tau(b)$ . The process now begins afresh at level $b$ , and by symmetry the probabilistic properties of its further evolution are invariant under reflection in the level $b$ (thought of as a mirror). This reflection principle leads to the joint density of $(W(t),M(t))$ as  

$$
\begin{array}{l l}{{}}&{{\displaystyle{\it I P_{0}}(W(t)\in d x,M(t)\in d y)}}\ {{}}&{{=}}\ {{=}}&{{\displaystyle{\frac{2(2y-x)}{\sqrt{2\pi t^{3}}}\exp\left\{-\frac{1}{2}(2y-x)^{2}/t\right\}\left(0\leq x\leq y),\right.}}}\end{array}
$$  

a formula due to Levy. (Levy also obtained the identity in law of the bivariate processes $(M(t)-$ $W(t),M(t))$ and $(|W(t)|,L(t))$ , where $L$ is the local time process of $W$ at zero: see e.g. Revuz and Yor (1991), VI.2). The idea behind the reflection principle goes back to work of Desire Andre in 1887, and indeed further, to the method of images of Lord Kelvin (1824-1907), then Sir William Thomson, of 1848 on electrostatics. For background on this, see any good book on electromagnetism, e.g. Jeans (1925), Chapter VIII.  

Levy's formula for the joint density of $(W(t),M(t))$ may be extended to the case of general drift $c$ by the usual method for changing drift, Girsanov's theorem. The general result is  

$$
\begin{array}{l l}{{}}&{{P_{0}\left(X(t)\in d x,M(t)\in d y\right)}}\ {{=}}&{{{\displaystyle\frac{2(2y-x)}{\sqrt{2\pi t^{3}}}\exp\left\{-\frac{(2y-x)^{2}}{2t}+c x-{\displaystyle\frac{1}{2}}c^{2}t\right\}\quad(0\leq x\leq y).}}}\end{array}
$$  

See e.g. Rogers and Williams (1994), I, (13.10), or Harrison (1985), \$1.8. As an alternative to. the probabilistic approach above, a second approach to this formula makes explicit use of Kelvin's language - mirrors, sources, sinks; see e.g. Cox and Miller (1972), \$5.7..  

Given such an explicit formula for the joint density of $(X(t),M(t))-\mathrm{or}$ equivalently, $(X(t),m(t))$ - we can calculate the option price by integration. The factor. $S(T)-K$ , or $S-K$ , gives rise to. two terms, in. $S$ and $K$ , while the integrals, involving relatives of the normal density function. $n$ may be obtained explicitly in terms of the normal distribution function. $N$ - both features familiar from the Black-Scholes formula. Indeed, this resemblance makes it convenient to decompose the price $D O C_{K,H}$ of the down-and-out call into the (Black-Scholes) price of the corresponding vanilla call, $C_{K}$ say, and the knockout discount, $K O D_{K,H}$ say, by which the knockout barrier at. $H$ lowers the price:  

$$
D O C_{K,H}=C_{K}-K O D_{K,H}.
$$  

The details of the integration, which are tedious, are omitted; the result is, writing $\scriptstyle\lambda:=r-{\frac{1}{2}}\sigma^{2}$  

$$
K O D_{K,H}=p_{0}(H/p_{0})^{2+2\lambda/\sigma^{2}}N(c_{1})-K e^{-r T}(H/p_{0})^{2\lambda/\sigma^{2}}N(c_{2}),
$$  

where $p_{0}$ is the initial stock price as usual and $c_{1}$ $c_{2}$ are functions of the price. $p=p_{0}$ and time $t=T$ given by  

$$
c_{1,2}(p,t)=\frac{\log(H^{2}/p K)+(r\pm\frac{1}{2}\sigma^{2})t}{\sigma\sqrt{t}}
$$  

(the notation is that of the excellent text Musiela and Rutkowski (1997), s9.6, to which we refer for further detail). The other cases of vanilla barrier options, and their sensitivity analysis, are given in detail in Zhang (1997), Chapter 10..  

# Chapter 5  

# Interest Rate Theory  

# 5.1 The Bond Market  

# 5.1.1 The Term Structure of Interest Rates  

We start with a heuristic discussion, which we will formalize in the following section. The main traded objects we consider are zero-coupon bonds. A zero-coupon bond is a bond that has no coupon payments. The price of a zero-coupon bond at time. $t$ that pays, say, a sure. $£$ at time $T\geq t$ is denoted $p(t,T)$ . All zero-coupon bonds are assumed to be default-free and have strictly positive prices. Various different interest rates are defined in connection with zero-coupon bonds,. but we will only consider continuously compounded interest rates (which facilitates theoretical. considerations).  

Using the arbitrage pricing technique, we easily obtain pricing formulas for coupon bonds. Coupon bonds are bonds with regular interest payments, called coupons, plus a principal repayment at maturity. Let $c_{j}$ be the payments at times $t_{j}$ $j=1,\dots,n$ $F$ be the face value paid at time $t_{n}$ . Then the price of the coupon bond $B_{c}$ must satisfy.  

$$
B_{c}=\sum_{j=1}^{n}c_{j}p(0,t_{j})+F p(0,t_{n}).
$$  

Hence, we see that a coupon bond is equivalent to a portfolio of zero-coupon bonds.  

The yield-to-maturity is defined as an interest rate per annum that equates the present value of future cash fows to the current market value. Using continuous compounding, the yield-tomaturity $y_{c}$ is defined by the relation  

$$
B_{c}=\sum_{j=1}^{n}c_{j}\exp\{-y_{c}t_{j}\}+F\exp\{-y_{c}t_{n}\}.
$$  

If for instance the i $\cdot_{j},~j=1,\dots,n$ are expressed in years, then $y_{c}$ is an annual continuously compounded yield-to-maturity (with the continuously compounded annual interest rate, $r(T)$ defined by the relation $p(0,T)=\exp\left\{-r(T)\left(T/365\right)\right\}$  

The term structure of interest rates is defined as the relationship between the yield-to-maturity on a zero-coupon bond and the bond's maturity. Normally, this yields an upward sloping curve (as in figure 5.1), but flat and downward sloping curves have also been observed.  

In constructing the term structure of interest rates, we face the additional problem that in. most economies no zero-coupon bonds with maturity greater than one year are traded (in the USA, Treasury bills are only traded with maturity up to one year). We can, however, use prices of. coupon bonds and invert formula (5.1) for zero-coupon prices. In practice, additional complications. arise, since the maturities of coupon bonds are not equally spaced and trading in bonds with some maturities may be too thin to give reliable prices. We refer the reader to Jarrow and Turnbull (2000) for further discussion of these issues..  

![](9d3a8c6cd69f86d00cca9e93898e1b416c35a057dd374220e290ac1e0ae55b2c.jpg)  
Figure 5.1: Yield curve  

# 5.1.2 Mathematical Modelling  

Let $(\Omega,{\mathcal{F}},I P,I F)$ be a filtered probability space with a filtration $\boldsymbol{F}=(\mathcal{F}_{t})_{t\le T^{*}}$ satisfying the usual conditions (used to model the flow of information) and fix a terminal time horizon $T^{*}$ .We assume that all processes are defined on this probability space. The basic building blocks for our relative pricing approach, zero-coupon bonds, are defined as follows..  

Definition 5.1.1. A zero-coupon bond with maturity date. $T$ , also called a. $T$ -bond, is a contract that guarantees the holder a cash payment of one unit on the date $T$ .The price at time. $t$ of a bond. with maturity date $T$ is denoted by. $p(t,T)$  

Obviously we have $p(t,t)=1$ for all $t$ . We shall assume that the price process $p(t,T),t\in[0,T]$ is adapted and strictly positive and that for every fixed $t$ $p(t,T)$ is continuously differentiable in the $T$ variable.  

Based on arbitrage considerations (recall our basic aim is to construct a market model that is free of arbitrage), we now define several risk-free interest rates. Given three dates $t<T_{1}<T_{2}$ the basic question is: what is the risk-free rate of return, determined at the contract time $t$ , over the interval $[T_{1},T_{2}]$ of an investment of $^{1}$ at time $T_{1}$ ? To answer this question we consider the arbitrage Table 5.1 below (compare $\S1.3$ for the use of arbitrage tables).  

Table 5.1: Arbitrage table for forward rates   


<html><body><table><tr><td>Time</td><td>t</td><td>T1</td><td>T2</td></tr><tr><td></td><td>Buy p(t,Ti)</td><td>T2 bonds</td><td>Receive p(t,T1)</td></tr><tr><td>Netinvestment</td><td>0</td><td>-1</td><td>p(t,T1)</td></tr></table></body></html>  

To exclude arbitrage opportunities, the equivalent constant rate of interest $R$ over this period (we pay out 1 at time $T_{1}$ and receive $e^{R(T_{2}-T_{1})}$ at $T_{2}$ ) has thus to be given by  

$$
e^{R(T_{2}-T_{1})}=\frac{p(t,T_{1})}{p(t,T_{2})}.
$$  

We formalize this in:  

Definition 5.1.2.. (i) The forward rate for the period $[T_{1},T_{2}]$ as seen at time at. $t$ is defined as.  

$$
R(t;T_{1},T_{2})=-\frac{\log p(t,T_{2})-\log p(t,T_{1})}{T_{2}-T_{1}}.
$$  

(ii) The spot rate $R(T_{1},T_{2})$ , for the period $[T_{1},T_{2}]$ is defined as  

$$
R(T_{1},T_{2})=R(T_{1};T_{1},T_{2}){}.
$$  

(ii) The instantaneous forward rate with maturity $T$ , at time $t$ , is defined by  

$$
f(t,T)=-\frac{\partial\log p(t,T)}{\partial T}.
$$  

(iv) The instantaneous short rate at time $t$ is defined by  

$$
r(t)=f(t,t).
$$  

Definition 5.1.3. The money account process is defined by  

$$
B(t)=\exp\left\{\intop_{0}^{t}r(s)d s\right\}.
$$  

The interpretation of the money market account is a strategy of instantaneously reinvesting at the current short rate.  

Lemma 5.1.1. For $t\leq s\leq T$ we have  

$$
p(t,T)=p(t,s)\exp\left\{-\intop_{s}^{T}f(t,u)d u\right\},
$$  

and in particular  

$$
p(t,T)=\exp\left\{-\intop_{t}^{T}f(t,s)d s\right\}.
$$  

In what follows, we model the above processes in a generalized Black-Scholes framework. That is, we assume that. $W=(W_{1},\dots,W_{d})$ is a standard $d$ dimensional Brownian motion and the filtration $\bar{\mathcal{M}}$ is the augmentation of the filtration generated by $W(t)$ . The dynamics of the various. processes are given as follows:  

Short-rate Dynamics:  

$$
\begin{array}{r}{d r(t)=a(t)d t+b(t)d W(t),}\end{array}
$$  

Bond-price Dynamics:  

$$
d p(t,T)=p(t,T)\left\{m(t,T)d t+v(t,T)d W(t)\right\},
$$  

Forward-rate Dynamics:  

$$
d f(t,T)=\alpha(t,T)d t+\sigma(t,T)d W(t).
$$  

We assume that in the above formulas, the coefficients meet standard conditions required to guarantee the existence of the various processes - that is, existence of solutions of the various. stochastic differential equations. Furthermore, we assume that the processes are smooth enough to allow differentiation and certain operations involving changing of order of integration and. differentiation. Since the actual conditions are rather technical, we refer the reader to Bjork (1997), Heath, Jarrow, and Morton (1992) and Protter (2004) (the latter reference for the stochastic Fubini. theorem) for these conditions.  

Following Bjork (1997) for formulation and proof, we now give a small toolbox for the relationships between the processes specified above.  

Proposition 5.1.1. (i) If $p(t,T)$ satisfies (5.3), then for the forward-rate dynamics we have  

$$
d f(t,T)=\alpha(t,T)d t+\sigma(t,T)d W(t),
$$  

where a and $\sigma$ are given by  

$$
\left\{\begin{array}{l l}{\alpha(t,T)}&{=v_{T}(t,T)v(t,T)-m_{T}(t,T),}\ {\sigma(t,T)}&{=-v_{T}(t,T).}\end{array}\right.
$$  

(ii) If $f(t,T)$ satisfies (5.4), then the short rate satisfies  

$$
\begin{array}{r}{d r(t)=a(t)d t+b(t)d W(t),}\end{array}
$$  

where a and b are given by  

$$
\left\{\begin{array}{l l}{a(t)}&{=f_{T}(t,t)+\alpha(t,t),}\ {b(t)}&{=\sigma(t,t).}\end{array}\right.
$$  

(iii) If $f(t,T)$ satisfies (5.4), then $p(t,T)$ satisfies  

$$
d p(t,T)=p(t,T)\left\{r(t)+A(t,T)+\frac{1}{2}\left\|S(t,T)\right\|^{2}\right\}d t+p(t,T)S(t,T)d W(t),
$$  

where  

$$
A(t,T)=-\int_{t}^{T}\alpha(t,s)d s,S(t,T)=-\int_{t}^{T}\sigma(t,s)d s.
$$  

Proof. To prove (i) we only have to apply Ito's formula to the defining equation for the forward rates.  

To prove (ii) we start by integrating the forward-rate dynamics. This leads to  

$$
f(t,t)=r(t)=f(0,t)+\intop_{0}^{t}\alpha(s,t)d s+\intop_{0}^{t}\sigma(s,t)d W(s).
$$  

Writing also $\alpha$ and $\sigma$ in integrated form  

$$
\begin{array}{r c l}{{\alpha(s,t)}}&{{=}}&{{\alpha(s,s)+\displaystyle{\int_{s}^{t}}\alpha_{T}(s,u)d u,}}\ {{}}&{{}}&{{\hphantom{=}}}\ {{\sigma(s,t)}}&{{=}}&{{\sigma(s,s)+\displaystyle{\int_{s}^{t}}\sigma_{T}(s,u)d u,}}\end{array}
$$  

and inserting this into (5.7), we find  

$$
\begin{array}{r c l}{{r(t)}}&{{=}}&{{\displaystyle f(0,t)+\int_{0}^{t}\alpha(s,s)d s+\int\int_{t}^{t}\alpha_{T}(s,u)d u d s}}\ {{}}&{{}}&{{\displaystyle+\int_{0}^{t}\sigma(s,s)d W(s)+\int\int_{s}^{0}\sigma_{T}(s,u)d u d W(s).}}\end{array}
$$  

fter changing the order of integration we can identify terms to establish (ii).  

For (iii) we use a technique from Heath, Jarrow, and Morton (1992); compare Bjork (1997). By the definition of the forward rates we may write the bond-price process as  

$$
p(t,T)=\exp\{Z(t,T)\},
$$  

where $Z$ is given by  

$$
Z(t,T)=-\intop_{t}^{T}f(t,s)d s.
$$  

Again we write (5.4) in integrated form:  

$$
f(t,s)=f(0,s)+\intop_{0}^{t}\alpha(u,s)d t+\intop_{0}^{t}\sigma(u,s)d W(u).
$$  

We insert the integrated form in (5.8) to get  

$$
Z(t,T)=-\intop_{t}^{T}f(0,s)d s-\intop_{0}^{t}\intop_{t}^{T}\alpha(u,s)d s d u-\intop_{0}^{t}\intop_{t}^{T}\sigma(u,s)d s d W(u).
$$  

Now, splitting the integrals and changing the order of integration gives us  

$$
\begin{array}{r c l}{{Z(t,T)}}&{{=}}&{{\displaystyle-\int\int f(0,s)d s-\int\int_{t}^{T}\alpha(u,s)d s d u-\int\int_{t}^{T}\sigma(u,s)d s d W(u)}}\ {{}}&{{\mathrm{~}}}&{{\mathrm{~}_{0}\mathrm{~}_{t}}}\ {{}}&{{+}}&{{\displaystyle\int f(0,s)d s+\int\int_{t}^{0}\alpha(u,s)d s d u+\int_{t}^{0}\int\sigma(u,s)d s d W(u)}}\ {{}}&{{=}}&{{\displaystyle\int_{0}^{0}\frac{t}{t}\int_{T}^{0}u}}\ {{}}&{{=}}&{{\displaystyle Z(0,T)-\int\int d\left(u,s\right)d s d u-\int\int_{0}^{0}\sigma(u,s)d s d W(u)}}\ {{}}&{{}}&{{\mathrm{~}_{t}^{t}\int_{0}^{s}\alpha+\int\int_{0}^{0}\alpha(u,s)d W(u)d s+\int_{0}^{0}\int\sigma(u,s)d W(u)d s.}}\ {{}}&{{+}}&{{\displaystyle\int_{0}^{t}f(0,s)d s+\int_{0}^{1}\int\alpha(u,s)d u d s+\int_{0}^{1}\int\sigma(u,s)d W(u)d s.}}\end{array}
$$  

The last line is just the integrated form of the forward-rate dynamics (5.4) over the interval $[0,s]$ Since $r(s)=f(s,s)$ , this last line above equals. $\begin{array}{r}{\int_{0}^{t}r(s)d s}\end{array}$ . So we obtain  

$$
Z(t,T)=Z(0,T)+\intop_{0}^{t}r(s)d s-\intop_{0}^{t}\intop_{u}^{T}\alpha(u,s)d s d u-\intop_{0}^{t}\intop_{u}^{T}\sigma(u,s)d s d W(u).
$$  

Using $A$ and $S$ from (5.6), the stochastic differential of $Z$ is given by.  

$$
d Z(t,T)=(r(t)+A(t,T))d t+S(t,T)d W(t).
$$  

Now we can apply Ito's lemma to the process $p(t,T)=\exp\{Z(t,T)\}$ to complete the proof.  

# 5.1.3 Bond Pricing, Martingale Measures and Trading Strategies  

We will now examine the mathematical structure of our bond-market model in more detail. As. usual, our first task is to find a convenient characterization of the no-arbitrage assumption. By Theorem 4.2.1, absence of arbitrage is guaranteed by the existence of an equivalent martingale. measure $\mathbb{Q}$ . Recall that by definition an equivalent martingale measure has to satisfy $\mathbb{Q}\sim\mathcal{N}$ and the discounted price processes (with respect to a suitable numeraire) of the basic securities have. to be $\mathbb{Q}$ -martingales. For the bond market this implies that all zero-coupon bonds with maturities. $0\le T\le T^{*}$ have to be martingales.  

More precisely, taking the risk-free bank account $B(t)$ as numeraire we have  

Definition 5.1.4. A measure. $\mathbb{Q}\sim\mathcal{N}$ defined on. $(\Omega,{\mathcal{F}},I P)$ is an equivalent martingale measure. for the bond market, if for every fixed $0\le T\le T^{*}$ the process  

$$
{\frac{p(t,T)}{B(t)}},0\leq t\leq T
$$  

is a $\mathbb{Q}$ -martingale.  

Assume now that there exists at least one equivalent martingale measure, say $\mathbb{Q}$ . Defining contingent claims as. ${\mathcal{F}}_{T}$ -measurable random variables such that $X/B(T)\in L^{1}(\mathcal{F}_{T},\mathbb{Q})$ with some $0\le T\le T^{*}$ (notation: $T$ -contingent claims), we can use the risk-neutral valuation principle (4.6) to obtain:  

Proposition 5.1.2. Consider a. $T$ -contingent claim $X$ . Then the price process. $\Pi_{X}(t)$ $0\leq t\leq T$ of the contingent claim is given by  

$$
\Pi_{X}(t)=B(t)E_{\pmb{Q}}\left[\left.\frac{X}{B(T)}\right|\mathcal{F}_{t}\right]=E_{\pmb{Q}}\left[X e^{-\int_{t}^{T}r(s)d s}\right|\mathcal{F}_{t}\right].
$$  

In particular, the price process of a zero-coupon bond with maturity $T$ is given by  

$$
p(t,T)=I E_{Q}\left[\left.e^{-\int_{t}^{T}r(s)d s}\right|\mathcal{F}_{t}\right].
$$  

Proof. We just have to apply Theorem 4.2.3.  

We thus see that the relevant dynamics of the price processes are those given under a martingale.   
measure $\mathbb{Q}$ . The implication for model building is that it is natural to model all objects directly.   
under a martingale measure $\mathbb{Q}$ . This approach is called martingale modelling. The price one has.   
to pay in using this approach lies in the statistical problems associated with parameter estimation.  

# 5.2 Short-rate Models  

Following our introductory remarks, we now look at models of the short rate of the type  

$$
d r(t)=a(t,r(t))d t+b(t,r(t))d W(t),
$$  

with functions $a,b$ sufficiently regular and $W$ a real-valued Brownian motion.  

The crucial point in this setting is the assumption on the probability measure under which the short rate is modelled.  

If we model under the objective probability measure $\mathcal{W}$ and assume that a locally risk-free asset $B$ (the money market) exists, we face the question whether in an arbitrage-free market bond prices - quite naturally viewed as derivatives with the short rate as underlying - are uniquely determined. In contrast to the equity market setting, with a risky asset and a risk-free asset available for trading, the short rate $r$ is not the price of a traded asset, and hence we only can set up portfolios consisting of putting money in the bank account. We thus face an incomplete market situation, and the best we can hope for is to find consistency requirements for bonds of different maturity. Given a single 'benchmark' bond, we should then be able to price all other bonds relative to this given bond..  

On the other hand, if we assume that the short rate is modelled under an equivalent martingale measure, we can immediately price all contingent claims via the risk-neutral valuation formula. The drawback in this case is the question of calibrating the model (we do not observe the parameters of the process under an equivalent martingale measure, but rather under the objective probability measure!).  

# 5.2.1 The Term-structure Equation  

Let us assume that the short-rate dynamics satisfy (5.9) under the historical probability measure $\mathcal{W}$ . In our Brownian setting, we know that each equivalent martingale measure $\mathbb{Q}$ is given in terms of a Girsanov density  

$$
L(t)=\exp\left\{-\intop_{0}^{t}\gamma(u)d W(u)-\frac{1}{2}\intop_{0}^{t}\gamma(u)^{2}d u\right\},\quad0\leq t\leq T.
$$  

Assume now that $\gamma$ is given as $\gamma(t)=\lambda(t,r(t))$ , with a sufficiently smooth function $\lambda$ .(We will use the notation $\mathbb{Q}(\lambda)$ to emphasize the dependence of the equivalent martingale measure on $\lambda$ By Girsanov's Theorem 4.1.4, we know that $\begin{array}{r}{\tilde{W}=W+\int\lambda d t}\end{array}$ is a $\mathbb{Q}(\lambda)$ -Brownian motion. So the $\mathbb{Q}(\lambda)$ -dynamics of $r$ are given by  

$$
d r(t)=\{a(t,r(t))-b(t,r(t))\lambda(t,r(t))\}d t+b(t,r(t))d\tilde{W}(t).
$$  

Now consider a $T$ -contingent claim $X=\Phi(r(T))$ , for some sufficiently smooth function $\Phi:{\cal{R}}\rightarrow$ $\mathbb{R}^{+}$ . We know that using the risk-neutral valuation formula we obtain arbitrage-free prices for any contingent claim by applying the expectation operator under an equivalent martingale measure (to the discounted time $T$ value). An slight modification of the argument used to find the BlackScholes PDE yields, for any $\mathbb{Q}(\lambda)$  

$$
{\cal E}_{{\bf{Q}}(\lambda)}\left[\left.e^{-\int_{t}^{T}r(u)d u}\Phi(r(T))\right|\mathcal{F}_{t}\right]={\cal F}(t,r(t)),
$$  

where $F:[0,T^{*}]\times I R\rightarrow I R$ satisfies the partial differential equation (we omit the arguments $(t,r)$  

$$
F_{t}+(a-b\lambda)F_{r}+\frac{1}{2}b^{2}F_{r r}-r F=0
$$  

and terminal condition $F(T,r)=\Phi(r)$ , for all $r\in\mathcal{M}$ . Suppose now that the price process $p(t,T)$ of a $T$ -bond is determined by the assessment, at time $t$ , of the segment. $\{r(\tau),t\leq\tau\leq T\}$ of the short rate process over the term of the bond. So we assume  

$$
p(t,T)=F(t,r(t);T),
$$  

with $F$ a sufficiently smooth function.  

Since we know that the value of a zero-coupon bond is one unit at maturity, we have the terminal condition $F(T,r;T)=1$ . Thus we have  

Proposition 5.2.1 (Term-structure Equation). If there exists an equivalent martingale mea sure of type $\mathbb{Q}(\lambda)$ for the bond market (implying that the no-arbitrage condition holds) and the price processes $p(t,T)$ of $T$ -bonds are given are given by a sufficiently smooth function $F$ as above, then $F$ will satisfy the partial differential equation (5.10) with terminal condition $F(T,r;T)=1$  

# 5.2.2 Martingale Modelling  

We now fix an equivalent martingale measure $\mathbb{Q}$ (which we assume to exist), and return to modelling the short-rate dynamics directly under. $\mathbb{Q}$ . Thus we assume that. $r$ has $\mathbb{Q}$ -dynamics  

$$
d r(t)=a(t,r(t))d t+b(t,r(t))d W(t)
$$  

with $W$ a (real-valued) $\mathbb{Q}$ -Wiener process. We can immediately apply the risk-neutral valuation technique to obtain the price process $\Pi_{X}(t)$ of any sufficiently integrable $T$ -contingent claim $X$ by computing the $\mathbb{Q}$ -expectation, i.e.  

$$
\Pi_{X}(t)=I E_{\pmb{Q}}\left[e^{-\int_{t}^{T}r(u)d u}X|\mathcal{F}_{t}\right].
$$  

If, additionally, the contingent claim is of the form $X=\Phi(r(T))$ with a sufficiently smooth function $\Phi$ , we obtain  

Proposition 5.2.2 (Term-structure Equation). Consider $T$ -contingent claims of the form $X=\Phi(r(T))$ . Then arbitrage-free price processes are given by $\Pi_{X}(t)=F(t,r(t))$ , where $F$ is the solution of the partial differential equation  

$$
F_{t}+a F_{r}+\frac{b^{2}}{2}F_{r r}-r F=0
$$  

with terminal condition $F(T,r)=\Phi(r)$ for all. $r\in\mathcal{M}$ . In particular,. $T$ -bond prices are given by $p(t,T)=F(t,r(t);T)$ , with $F$ solving (5.12) and terminal condition $F(T,r;T)=1$  

Suppose we want to evaluate the price of a European call option with maturity $S$ and strike $K$ on an underlying $T$ -bond. This means we have to price the $S$ -contingent claim  

$$
X=\operatorname*{max}\{p(S,T)-K,0\}.
$$  

We first have to find the price process. $p(t,T)=F(t,r;T)$ by solving (5.12) with terminal condition. $F(T,r;T)=1$ . Secondly, we use the risk-neutral valuation principle to obtain $\Pi_{X}(t)=G(t,r)$ with $G$ solving  

$$
G_{t}+a G_{r}+\frac{b^{2}}{2}G_{r r}-r G=0\mathrm{and}G(S,r)=\operatorname*{max}\{F(S,r;T)-K,0\},\forall r\in I R.
$$  

So we are clearly in need of efficient methods of solving the above partial differential equations, or from a modelling point of view, we need short-rate models that facilate this computational task. Fortunately, there is a class of models, exhibiting an affine term structure (ATS), which allows for simplification.  

Definition 5.2.1. If bond prices are given as  

$$
p(t,T)=\exp{\left\{A(t,T)-B(t,T)r\right\}},\quad0\leq t\leq T,
$$  

with $A(t,T)$ and $B(t,T)$ are deterministic functions, we say that the model possesses an affine term structure.  

Assuming that we have such a model in which both $a$ and $b^{2}$ are affine in $r$ , say $a(t,r)=$ $\alpha(t)-\beta(t)r$ and $b(t,r)=\sqrt{\gamma(t)+\delta(t)r}$ , we find that $A$ and $B$ are given as solutions of ordinary differential equations,  

$$
\begin{array}{r l r}{A_{t}(t,T)-\alpha(t)B(t,T)+\displaystyle\frac{\gamma(t)}{2}B^{2}(t,T)}&{=}&{0,\qquadA(T,T)=0,}\ {\displaystyle(1+B_{t}(t,T))-\beta(t)B(t,T)-\frac{\delta(t)}{2}B^{2}(t,T)}&{=}&{0,\qquadB(T,T)=0.}\end{array}
$$  

The equation for $B$ is a Riccati equation, which can be solved analytically, see Ince (1944), s2.15, 12.51, A.21. Using the solution for $B$ we get $A$ by integrating.  

Examples of short-rate models exhibiting an affine term structure include the following.  

1. Vasicek model: $d r=(\alpha-\beta r)d t+\gamma d W$   
2. Cox-Ingersoll-Ross (CIR) model: $d r=(\alpha-\beta r)d t+\delta\sqrt{r}d W$   
3. Ho-Lee model: $d r=\alpha(t)d t+\gamma d W$   
4. Hull-White (extended Vasicek) model: $d r=(\alpha(t)-\beta(t)r)d t+\gamma(t)d W$   
5. Hull-White (extended CIR) model: $d r=(\alpha(t)-\beta(t)r)d t+\delta(t)\sqrt{r}d W$  

# 5.3 Heath-Jarrow-Morton Methodology  

# 5.3.1 The Heath-Jarrow-Morton Model Class  

Modelling the term structure with only one explanatory variable leads to various undesirable properties of the model (to say the least). Various authors have proposed models with more than one state variable, e.g. the short rate and a long rate and/or intermediate rates. The. Heath-Jarrow-Morton method (compare Heath, Jarrow, and Morton (1992)) is at the far end of. this spectrum - they propose using the entire forward rate curve as their (infinite-dimensional). state variable. More precisely, for any fixed. $T\leq T^{*}$ the dynamics of instantaneous, continuously. compounded forward rates $f(t,T)$ are exogenously given by.  

$$
d f(t,T)=\alpha(t,T)d t+\sigma(t,T)d W(t),
$$  

where $W$ is a $d$ -dimensional Brownian motion with respect to the underlying (objective) probability measure $\mathcal{l}^{p}$ and $\alpha(t,T)$ resp. $\sigma(t,T)$ are adapted $\mathscr{R}$ resp. $\mathit{\Pi}_{\mathit{I R}^{d}}$ -valued processes. For any fixed maturity $T$ , the initial condition of the stochastic differential equation (5.4) is determined. by the current value of the empirical (observed) forward rate for the future date. $T$ which prevails at time 0. Observe that we have defined an infinite-dimensional stochastic system, and that by construction we obtain a perfect fit to the observed term structure (thus avoiding the problem of. inverting the yield curve)..  

The exogenous specification of the family of forward rates $\{f(t,T);T>0\}$ is equivalent to a specification of the entire family of bond prices $\{p(t,T);T>0\}$ . Furthermore, by Proposition 5.1.1 we obtain the dynamics of the bond-price processes as  

$$
d p(t,T)=p(t,T)\left\{m(t,T)d t+S(t,T)d W(t)\right\},
$$  

where  

$$
m(t,T)=r(t)+A(t,T)+\frac{1}{2}\left\|S(t,T)\right\|^{2},
$$  

$\begin{array}{r}{A(t,T)=-\int_{t}^{T}\alpha(t,s)d s}\end{array}$ and $\begin{array}{r}{S(t,T)=-\int_{t}^{T}\sigma(t,s)d s}\end{array}$ (compare (5.6)).We now explore what conditions we must impose on the coefficients in order to ensure the existence of an equivalent martingale measure with respect to a suitable numeraire. By Theorem 4.2.1, we then could conclude that our bond market model is free of arbitrage.  

As a first possible choice of numeraire, we use the money-market account $B$ (assuming that there exists a measurable version of. $f(t,t)$ in $[0,T^{*}]$ ), given by  

$$
B(t)=\exp\left\{\intop_{0}^{t}f(u,u)d u\right\}=\exp\left\{\intop_{0}^{t}r(u)d u\right\}.
$$  

So we allow investments in a savings account too. We must find an equivalent measure such that  

$$
Z(t,T)={\frac{p(t,T)}{B(t)}}
$$  

is a martingale for every. $0\le T\le T^{*}$ . We will call such a measure risk-neutral martingale measure to emphasize the dependence on the numeraire..  

Theorem 5.3.1. Assume that the family of forward rates is given by (5.4). Then there exists a risk-neutral martingale measure if and only if there exists an adapted process $\lambda(t)$ ,with the properties that  

(i) $\begin{array}{r}{\int_{0}^{T}\|\lambda(t)\|^{2}d t<\infty}\end{array}$ ,a.s. and $\textstyle E(L(T))=1$ , with  

$$
L(t)=\exp{\left\{-\intop_{0}^{t}\lambda(u)^{\prime}d W(u)-\frac{1}{2}\intop_{0}^{t}\left\|\lambda(u)\right\|^{2}d u\right\}}.
$$  

(ii) For all $0\le T\le T^{*}$ and for all $t\leq T$ , we have  

$$
\alpha(t,T)=\sigma(t,T)\intop_{t}^{T}\sigma(t,s)d s+\sigma(t,T)\lambda(t).
$$  

Proof. Since we are working in a Brownian framework we know that any equivalent measure $\mathbb{Q}\sim{\mathcal{M}}$ is given via a Girsanov density (5.15). Using Ito's formula and Girsanov's Theorem 4.1.4, we find the $\mathbb{Q}$ -dynamics of $Z(t,T)$ (omitting the arguments) as:  

$$
d Z=Z\left(A+\frac{1}{2}\left\|S\right\|^{2}-S\lambda\right)d t+Z S d\tilde{W},
$$  

with $\tilde{W}$ a $\mathbb{Q}$ Brownian motion. In order for. $Z$ to be a $\mathbb{Q}$ -martingale, the drift coefficient in (5.17 has to be zero, so we obtain.  

$$
A(t,T)+\frac{1}{2}\left\|S(t,T)\right\|^{2}=S(t,T)\lambda(t).
$$  

Taking the derivative with respect to $T$ , we get  

$$
-\alpha(t,T)-\sigma(t,T)S(t,T)=-\sigma(t,T)\lambda(t),
$$  

which after rearranging is (5.16).  

It is possible to interpret. $\lambda$ as a risk premium, which has to be exogenously specified to allow the. choice of a particular risk-neutral martingale measure. In view of (5.16) this leads to a restriction on drift and volatility coefficients in the specification of the forward rate dynamics (5.4). The particular choice $\lambda\equiv0$ means that we assume we model directly under a risk-neutral martingale measure $\mathbb{Q}$ . In that case the relations between the various infinitesimal characteristics for the. forward rate are known as the 'Heath-Jarrow-Morton drift condition'..  

Theorem 5.3.2 (Heath-Jarrow-Morton). Assume that $\mathbb{Q}$ is a risk-neutral martingale measure.   
for the bond market and that the forward-rate dynamics under $\mathbb{Q}$ are given by.  

$$
d f(t,T)=\alpha(t,T)d t+\sigma(t,T)d\tilde{W}(t),
$$  

with Wa $\mathbb{Q}$ -Brownian motion. Then we have:  

(i) the Heath-Jarrow-Morton drift condition  

$$
\alpha(t,T)=\sigma(t,T)\intop_{t}^{T}\sigma(t,s)d s,\:\:\:0\leq t\leq T\leq T^{*},\:\:Q\gets a.s.,
$$  

(ii) and bond-price dynamics under $\mathbb{Q}$ are given by  

$$
d p(t,T)=p(t,T)r(t)d t+p(t,T)S(t,T)d\tilde{W}(t),
$$  

with $S$ as in (5.6).  

# 5.3.2 Forward Risk-neutral Martingale Measures  

For many valuation problems in the bond market it is more suitable to use the bond price process $p(t,T^{*})$ as numeraire. We then have to find an equivalent probability measure $\mathbb{Q}^{*}$ such that the auxiliary process  

$$
Z^{*}(t,T)=\frac{p(t,T)}{p(t,T^{*})},\forall t\in[0,T],
$$  

is a martingale under $\mathbb{Q}^{*}$ for all $T\leq T^{*}$ . We will call such a measure forward risk-neutral mar-. tingale measure. In this setting, a savings account is not used and the existence of a martingale measure $\mathbb{Q}^{*}$ guarantees that there are no arbitrage opportunities between bonds of different maturities.  

In order to find sufficient conditions for the existence of such a martingale measure, we follow the same programme as above. By (5.13) bond price dynamics under the original probability measure $\mathcal{W}$ are given as  

$$
d p(t,T)=p(t,T)\left\{m(t,T)d t+S(t,T)d W(t)\right\},
$$  

with $m(t,T)$ as in (5.14). Now applying Ito's formula to the quotient $p(t,T)/p(t,T^{*})$ we find  

$$
d Z^{*}(t,T)=Z^{*}(t,T)\left\{\tilde{m}(t,T)d t+(S(t,T)-S(t,T^{*}))d W(t)\right\},
$$  

with $\tilde{m}(t,T)=m(t,T)-m(t,T^{*})-S(t,T^{*})(S(t,T)-S(t,T^{*}))$ . Again, any equivalent martingale measure $\mathbb{Q}^{*}$ is given via a Girsanov density $L(t)$ defined by a function $\gamma(t)$ as in Theorem 5.3.1. So the drift coefficient of $Z^{*}(t,T)$ under $\mathbb{Q}^{*}$ is given as.  

$$
\tilde{m}(t,T)-(S(t,T)-S(t,T^{*}))\gamma(t).
$$  

Now for $Z^{*}(t,T)$ to be a $\mathbb{Q}^{*}$ -martingale this coefficient has to be zero, and replacing $\tilde{m}$ with its definition we get  

$$
\begin{array}{l}{\displaystyle\left(A(t,T)-A(t,T^{*})\right)+\frac{1}{2}\left(\left\|S(t,T)\right\|^{2}-\left\|S(t,T^{*})\right\|^{2}\right)}\ {=\left(S(t,T^{*})+\gamma(t)\right)\left(S(t,T)-S(t,T^{*})\right).}\end{array}
$$  

Written in terms of the coefficients of the forward-rate dynamics, this identity simplifies to  

$$
\int_{T}^{T^{*}}\alpha(t,s)d s+\frac{1}{2}\left\vert\left\vert\int_{T}^{T^{*}}\sigma(t,s)d s\right\vert\right\vert^{2}=\gamma(t)\int_{T}^{T^{*}}\sigma(t,s)d s.
$$  

Taking the derivative with respect to $T$ , we obtain  

$$
\alpha(t,T)+\sigma(t,T)\intop_{T}^{T^{*}}\sigma(t,s)d s=\gamma(t)\sigma(t,T).
$$  

We have thus proved:  

Theorem 5.3.3. Assume that the family of forward rates is given by (5.4). Then there exists a forward risk-neutral martingale measure if and only if there exists an adapted process. $\gamma(t)$ , with the properties (i) of Theorem 5.3.1, such that  

$$
\alpha(t,T)=\sigma(t,T)\left(S(T,T^{*})+\gamma(t)\right),0\leq t\leq T\leq T^{*}.
$$  

# 5.4 Pricing and Hedging Contingent Claims  

# 5.4.1 Gaussian HJM Framework  

Assume that the dynamics of the forward rate are given under a risk-neutral martingale measure $\mathbb{Q}$ by  

$$
d f(t,T)=\alpha(t,T)d t+\sigma(t,T)d\tilde{W}(t),\quad f(0,T)=\hat{f}(0,T),
$$  

with all processes real-valued. We restrict the class of models by assuming that the forward rate's volatility is deterministic. The HJM-drift condition (5.20) and the integrated form of the forward rate (compare (5.7)) lead to  

$$
f(t,t)=r(t)=f(0,t)+\intop_{0}^{t}(-\sigma(u,t)S(u,t))d u+\intop_{0}^{t}\sigma(u,t)d\Tilde{W}(u),
$$  

which implies that the short-rate (as well as the forward rates. $f(t,T))$ have Gaussian probability laws (hence the terminology). By Theorem 5.3.2, bond-price dynamics under $\mathbb{Q}$ are given by  

$$
d p(t,T)=p(t,T)\left\{r(t)d t+S(t,T)d\tilde{W}(t)\right\},
$$  

which we can solve in special cases explicitly for $p(t,T)$  

To price options on zero-coupon bonds, we use the change of numeraire technique. Consider a European call. $C$ on a $T^{*}$ -bond with maturity $T\leq T^{*}$ and strike. $K$ .So we consider the $T$ contingent claim  

$$
X=(p(T,T^{*})-K)^{+}.
$$  

The price of this call at time $t=0$ is given as  

$$
C(0)=p(0,T^{*})Q^{*}(A)-K p(0,T)Q^{T}(A),
$$  

with $A=\{\omega:p(T,T^{*})>K\}$ and $\\\mathbb{Q}^{T}$ resp. $\mathbb{Q}^{*}$ the $T$ - resp. $T^{*}$ -forward risk-neutral measure. Now  

$$
\tilde{Z}(t,T)=\frac{p(t,T^{*})}{p(t,T)}
$$  

has $\mathbb{Q}$ -dynamics (omitting the arguments and writing $S^{*}$ for $S(t,T^{*})$  

$$
d\tilde{Z}=\tilde{Z}\Big\{S(S-S^{*})d t-(S-S^{*})d\tilde{W}(t)\Big\},
$$  

so a deterministic variance coefficient. Now  

$$
Q^{*}(p(T,T^{*})\geq K)=Q^{*}\left(\frac{p(T,T^{*})}{p(T,T)}\geq K\right)=Q^{*}(\tilde{Z}(T,T)\geq K).
$$  

Since $\Tilde{Z}(t,T)$ is a $\\\mathbb{Q}^{T}$ -martingale with $\\\ Q^{T}$ -dynamics  

$$
d\tilde{Z}(t,T)=-\tilde{Z}(t,T)(S(t,T)-S(t,T^{*}))d W^{T}(t),
$$  

we find that under $\\\ Q^{T}$ (again $S=S(t,T),S^{*}=S(t,T^{*}),$  

$$
\tilde{Z}(T,T)=\frac{p(0,T^{*})}{p(0,T)}\exp\left\{-\int_{0}^{T}(S-S^{*})d W^{T}(t)-\frac{1}{2}\int_{0}^{T}(S-S^{*})^{2}d t\right\}
$$  

(with $W^{T}$ a $\\\ Q^{T}$ -Brownian motion). The stochastic integral in the exponential is Gaussian with zero mean and variance.  

$$
\Sigma^{2}(T)=\int_{0}^{T}(S(t,T)-S(t,T^{*}))^{2}d t.
$$  

So  

$$
\pmb{Q}^{T}(p(T,T^{*})\ge K)=\pmb{Q}^{T}(\tilde{Z}(T,T)\ge K)=N(d_{2})
$$  

with  

$$
d_{2}=\frac{\log\Big(\frac{p(0,T)}{K p(0,T^{*})}\Big)-\frac{1}{2}\Sigma^{2}(T)}{\sqrt{\Sigma^{2}(T)}}.
$$  

Similarly, for the first term  

$$
Z^{*}(t,T)=\frac{p(t,T)}{p(t,T^{*})}
$$  

has $\mathbb{Q}$ -dynamics (compare (5.21))  

$$
d Z^{*}=Z^{*}\Big\{S^{*}(S^{*}-S)d t+(S-S^{*})d\tilde{W}(t)\Big\},
$$  

and also a deterministic variance coefficient. Now  

$$
Q^{*}(p(T,T^{*})\geq K)=Q^{*}\left(\frac{1}{p(T,T^{*})}\leq\frac{1}{K}\right)=Q^{*}(Z^{*}(T,T)\leq\frac{1}{K}).
$$  

Under $\mathbb{Q}^{*}~Z^{*}(t,T)$ is a martingale with  

$$
d Z^{*}(t,T)=Z^{*}(t,T)(S(t,T)-S(t,T^{*}))d W^{*}(t),
$$  

so  

$$
d Z^{*}(T,T)=\frac{p(0,T)}{p(0,T^{*})}\exp\left\{\intop_{0}^{T}(S-S^{*})d W^{*}(t)-\frac{1}{2}\intop_{0}^{T}(S-S^{*})^{2}d t\right\}.
$$  

Again we have a Gaussian variable with the (same) variance $\Sigma^{2}(T)$ in the exponential. Using this fact it follows (after some computations) that:  

$$
\begin{array}{r}{Q^{*}(p(T,T^{*})\geq K)=N(d_{1}),}\end{array}
$$  

with  

$$
d_{1}=d_{2}+\sqrt{\Sigma^{2}(T)}.
$$  

So we obtain:  

Proposition 5.4.1. The price of the call option defined in (5.22) is given by  

$$
C(0)=p(0,T^{*})N(d_{2})-K p(0,T)N(d_{1}),
$$  

with parameters given as above.  

# 5.4.2 Swaps  

This section is devoted to the pricing of swaps. We consider the case of a forward swap settled in arrears. Such a contingent claim is characterized by:.  

a fixed time $t$ , the contract time,   
dates $T_{0}<T_{1},...<T_{n}$ , equally distanced $T_{i+1}-T_{i}=\delta$ $R$ , a prespecified fixed rate of interest, $K$ , a nominal amount.  

A swap contract. $S$ with $K$ and $R$ fixed for the period $T_{0},\ldots T_{n}$ is a sequence of payments, where the amount of money paid out at. $T_{i+1}$ $i=0,\ldots,n-1$ is defined by.  

$$
X_{i+1}=K\delta(L(T_{i},T_{i})-R).
$$  

The floating rate over. $[T_{i},T_{i+1}]$ observed at $T_{i}$ is a simple rate defined as  

$$
p(T_{i},T_{i+1})=\frac{1}{1+\delta L(T_{i},T_{i})}.
$$  

We do not need to specify a particular interest-rate model here, all we need is the existence of a risk-neutral martingale measure. Using the risk-neutral pricing formula we obtain (we may use $K=1$  

$$
\begin{array}{r c l}{{\displaystyle\Pi(t,S)}}&{{=}}&{{\displaystyle\sum_{i=1}^{n}\hfil\hfil\hfil\hfil B_{Q}\left[e^{-\int_{t}^{T}r(s)d s}\delta\big(L(T_{i},T_{i})-R\big)\bigg|\mathcal{F}_{t}\right]}}\ {{}}&{{=}}&{{\displaystyle\sum_{i=1}^{n}\hfil\hfil B_{Q}\left[\left.\mathbb{E}_{Q}\left[e^{-\int_{T_{i-1}^{T}r(s)d s}^{T_{i}}\Bigg|\mathcal{F}_{T_{i-1}}}\right]\right.\right.}}\ {{}}&{{}}&{{\displaystyle\left.\times e^{-\int_{t}^{T}r(s)d s}\left(\frac{1}{p(T_{i-1},T_{i})}-(1+\delta R)\right)\right|\mathcal{F}_{t}\right]}}\ {{}}&{{=}}&{{\displaystyle\sum_{i=1}^{n}\hfil\hfil(p(t,T_{i-1})-(1+\delta R)p(t,T_{i}))=p(t,T_{0})-\sum_{i=1}^{n}c_{i}p(t,T_{i}),}}\end{array}
$$  

with $c_{i}=\delta R,i=1,\ldots,n-1$ and $c_{n}=1+\delta R$ .So a swap is a linear combination of zero-. coupon bonds, and we obtain its price accordingly. This again shows the power of risk-neutral. pricing. Using the linearity of the expectation operator we can reduce complicated claims to sums of simpler ones.  

# 5.4.3 Caps  

An interest cap is a contract where the seller of the contract promises to pay a certain amount of cash to the holder of the contract if the interest rate exceeds a certain predetermined level (the cap rate) at some future date. A cap can be broken down in a series of caplets. A caplet is a contract written at $t$ , in force between $[T_{0},T_{1}]$ $\delta=T_{1}-T_{0}$ , the nominal amount is $K$ , the cap rate is denoted by $R$ . The relevant interest rate (LIBOR, for instance) is observed in $T_{0}$ and defined by  

$$
p(T_{0},T_{1})=\frac{1}{1+\delta L(T_{0},T_{0})}.
$$  

A caplet $C$ is a $T_{1}$ -contingent claim with payoff $X=K\delta(L(T_{0},T_{0}){-}R)^{+}$ . Writing $L=L(T_{0},T_{0}),p=$ $p(T_{0},T_{1}),R^{*}=1+\delta R$ , we have $L=(1-p)/(\delta p)$ , (assuming $K=1$ ) and  

$$
\begin{array}{r c l}{{X}}&{{=}}&{{\delta(L-R)^{+}=\delta\left(\displaystyle\frac{1-p}{\delta p}-R\right)^{+}}}\ {{}}&{{=}}&{{\left(\displaystyle\frac{1}{p}-(1+\delta R)\right)^{+}=\left(\displaystyle\frac{1}{p}-R^{*}\right)^{+}.}}\end{array}
$$  

The risk-neutral pricing formula leads to  

$$
\begin{array}{r l}{\Pi_{C}(t)}&{=E_{\mathbf{Q}}\left[e^{-\int_{t}^{\Pi_{r}}r(s)d s}\left(\frac{1}{p}-R^{*}\right)^{*}\Bigg|\mathcal{F}_{t}\right]}\ {=}&{E_{\mathbf{Q}}\left[E_{\mathbf{Q}}\left[e^{-\int_{T_{n}^{\mathsf{T}}}^{\Pi_{r}}r(s)d s}\Bigg|\mathcal{F}_{T_{n}}\right]e^{-\int_{T_{n}^{\mathsf{T}}}^{\Pi_{r}}r(s)d s}\left(\frac{1}{p}-R^{*}\right)^{*}\Bigg|\mathcal{F}_{t}\right]}\ {=}&{E_{\mathbf{Q}}\Bigg[p(T_{0},T_{1})e^{-\int_{T_{n}^{\mathsf{T}}}^{\Pi_{r}}r(s)d s}\left(\frac{1}{p}-R^{*}\right)^{*}\Bigg|\mathcal{F}_{t}\Bigg]}\ {=}&{E_{\mathbf{Q}}\left[e^{-\int_{T_{n}^{\mathsf{T}}}^{\Pi_{r}}r(s)d s}\left(1-p R^{*}\right)^{*}\Bigg|\mathcal{F}_{t}\right]}\ {=}&{R^{*}E_{\mathbf{Q}}\left[e^{-\int_{T_{n}^{\mathsf{T}}}^{\Pi_{r}}r(s)d s}\left(\frac{1}{R^{*}}-p\right)^{*}\Bigg|\mathcal{F}_{t}\right].}\end{array}
$$  

So a caplet is equivalent to $R^{*}$ put options on a. $T_{1}$ -bond with maturity. $T_{0}$ and strike $1/R^{*}$  

# Appendix A  

# Basic Probability Background  

# A.1 Fundamentals  

To describe a random experiment we use a sample space $\Omega$ , the set of all possible outcomes. Each point $\omega$ of $\Omega$ , or sample point, represents a possible random outcome of performing the random experiment.  

Examples. Write down $\Omega$ for experiments such as flip a coin three times, roll two dice. For a set $A\subseteq\Omega$ we want to know the probability ${\cal{P}}(A)$ . The class $\mathcal{F}$ of subsets of $\Omega$ whose robabilities ${\cal{P}}(A)$ are defined (call such $A$ events) should be a $\sigma$ -algebra , i.e.  

(i) $\varnothing,\Omega\in{\mathcal{F}}$ (ii) $F\in{\mathcal{F}}$ implies $F^{c}\in{\mathcal{F}}$ (iii) $F_{1},F_{2},...\in\mathcal{F}\mathrm{then}\bigcup_{n}F_{n}\in\mathcal{F}.$  

We want a probability measure defined on $\mathcal{F}$  

(i) $\begin{array}{r}{I P(\varnothing)=0,I P(\Omega)=1,}\end{array}$   
(ii) $\textstyle{\mathcal{P}}(A)\geq0$ for all $A$   
(ii) If $A_{1},A_{2},\ldots$ , are disjoint, $\textstyle P(\bigcup_{i}A_{i})=\sum_{i}P(A_{i})$ countable additivity.  

Definition A.1.1. A probability space, or Kolmogorov triple, is a triple $(\Omega,{\mathcal{F}},I P)$ satisfying Kolmogorov axioms $(i),(i i)$ and (iii) above.  

A probability space is a mathematical model of a random experiment  

Examples. Assign probabilities for the above experiments.  

Definition A.1.2. Let $(\Omega,{\mathcal{F}},I P)$ be a probability space. $A$ random variable (vector) $X$ is $a$ function $X:\Omega\to I R(I R^{k})$ such that $X^{-1}(B)=\{\omega\in\Omega:X(\omega)\in B\}\in{\mathcal{F}}$ for all Borel sets. $B\in B(B(B^{k}))$  

For a random variable $X$  

$$
\{\omega\in\Omega:X(\omega)\leq x\}\in\mathcal{F}
$$  

for all $x\in\mathcal{R}$ . So define the distribution function $F_{X}$ of $X$ by  

$$
F_{X}(x):=D P{\bigl(}\{\omega:X(\omega)\leq x\}{\bigr)}.
$$  

Recall: $\sigma(X)$ , the $\sigma$ -algebra generated by $X$  

# Some important probability distributions  

Binomial distribution: Number of successes  

$$
I P(S_{n}=k)={\binom{n}{k}}p^{k}(1-p)^{n-k}.
$$  

Geometric distribution: Waiting time  

$$
P(N=n)=p(1-p)^{n-1}.
$$  

Poisson distribution:  

$$
I P(X=k)=e^{-\lambda}\frac{\lambda^{k}}{k!}.
$$  

.Density of Uniform distribution:  

$$
f(x)={\frac{1}{b-a}}\mathbf{1}_{\left\{(a,b)\right\}}.
$$  

. Density of Exponential distribution:  

$$
f(x)=\lambda e^{-\lambda x}{\bf1}_{\{[0,\infty)\}}.
$$  

. Density of standard Normal distribution:  

$$
f(x)={\frac{1}{\sqrt{2\pi}}}e^{-x^{2}/2}.
$$  

Definition A.1.3. The expectation $\mathit{\Pi}_{\mathit{I B}}$ of a random variable $X$ on $(\Omega,{\mathcal{F}},I P)$ is defined by  

$$
E X:=\int X d P,\quad o r\quad\int X(\omega)d P(\omega).
$$  

The variance of a random variable is defined as  

$$
W a r(X):=I E\left[(X-I E(X))^{2}\right]=I E\left(X^{2}\right)-(I E X)^{2}.
$$  

If $X$ is real-valued with density $f$ (i.e $\begin{array}{r}{f(x)\geq0:\int f(x)d x=1)}\end{array}$  

$$
E X:=\int x f(x)d x
$$  

or if $X$ is discrete, taking values $x_{n}(n=1,2,...)$ with probability function $f(x_{n})(\geq0)$  

$$
E X:=\sum x_{n}f(x_{n}).
$$  

Examples. Calculate moments for some of the above distributions.  

Definition A.1.4. Random variables $X_{1},\ldots,X_{n}$ are independent if whenever $A_{i}\in B$ (the Borel $\sigma$ -algebra) for $i=1,\dots n$ we have  

$$
I P\left(\bigcap_{i=1}^{n}\{X_{i}\in A_{i}\}\right)=\prod_{i=1}^{n}I P(\{X_{i}\in A_{i}\}).
$$  

Lemma A.1.1. In order for. $X_{1},\ldots,X_{n}$ to be independent it is necessary and sufficient that for all $x_{1},...x_{n}\in(-\infty,\infty]$  

$$
I P\left(\bigcap_{i=1}^{n}\{X_{i}\leq x_{i}\}\right)=\prod_{i=1}^{n}I P(\{X_{i}\leq x_{i}\}).
$$  

Theorem A.1.1 (Multiplication Theorem). If $X_{1},\ldots,X_{n}$ are independent and $\left|\mathbb{E}\left|X_{i}\right|\right.<$ $\infty$ $\infty,i=1,\ldots,n$ , then  

$$
E\left(\prod_{i=1}^{n}X_{i}\right)=\prod_{i=1}^{n}{\cal{E}}(X_{i}).
$$  

If $X$ $Y$ are independent, with distribution functions $F$ $G$ , define $Z:=X+Y$ with distribution. function $H$ .We call $H$ the convolution of. $F$ and $G$ , written $H=F*G$  

Suppose $X$ $Y$ have densities $f$ $g$ , then $Z$ has a density $h$ with  

$$
h(z)=\intop_{-\infty}^{\infty}f(z-y)g(y)d y=\intop_{-\infty}^{\infty}f(x)g(z-x)d x.
$$  

Example. Assume $t_{1},\ldots,t_{n}$ are independent random variables that have an exponential distribution with parameter $\lambda$ . Then $T=t_{1}+...+t_{n}$ has the Gamma $(n,\lambda)$ density function  

$$
f(x)=\frac{\lambda^{n}x^{n-1}}{(n-1)!}e^{-\lambda x}.
$$  

Definition A.1.5. If $X$ is a random variable with distribution function $F$ , its moment generating function $\phi_{X}$ is  

$$
\phi(t):=I E(e^{t X})=\int_{-\infty}^{\infty}e^{t x}d F(x).
$$  

The mgf takes convolution into multiplication: if $X$ $Y$ are independent,  

$$
\phi_{X+Y}(t)=\phi_{X}(t)\phi_{Y}(t).
$$  

Observe $\phi^{(k)}(t)=\mathbb{E}(X^{k}e^{t X})$ and $\phi(0)=\mathbb{E}(X^{k})$  

For $X$ on nonnegative integers use the generating function  

$$
\gamma_{X}(z)=I E(z^{X})=\sum_{k=0}^{\infty}z^{k}I P(Z=k).
$$  

# A.2 Convolution and Characteristic Functions  

The most basic operation on numbers is addition; the most basic operation on random variables is addition of independent random variables. If $X$ $Y$ are independent, with distribution functions $F$ $G$ , and  

$$
Z:=X+Y,
$$  

let $Z$ have distribution function $H$ .Then since $X+Y=Y+X$ (addition is commutative), $H$ depends on $F$ and $G$ symmetrically.We call $H$ the convolution (German: Faltung) of $F$ and $G$ written  

$$
H=F*G.
$$  

Suppose first that $X$ $Y$ have densities $f$ $g$ . Then  

$$
H(z)=P(Z\leq z)=P(X+Y\leq z)=\int_{\{(x,y):x+y\leq z\}}f(x)g(y)d x d y,
$$  

since by independence of $X$ and $Y$ the joint density of. $X$ and $Y$ is the product. $f(x)g(y)$ of their. separate (marginal) densities, and to find probabilities in the density case we integrate the joint density over the relevant region. Thus.  

$$
H(z)=\intop_{-\infty}^{\infty}f(x)\left\{\intop_{-\infty}^{z-x}g(y)d y\right\}d x=\intop_{-\infty}^{\infty}f(x)G(z-x)d x.
$$  

If  

$$
h(z):=\int_{-\infty}^{\infty}f(x)g(z-x)d x,
$$  

(and of course symmetrically with $f$ and $g$ interchanged), then integrating we recover the equation above (after interchanging the order of integration. This is legitimate, as the integrals are nonnegative, by Fubini's theorem, which we quote from measure theory, see e.g. (Williams 1991),. 88.2). This shows that if $X$ $Y$ are independent with densities $f$ $g$ , and $Z=X+Y$ , then $Z$ has density $h$ , where  

$$
h(x)=\int_{-\infty}^{\infty}f(x-y)g(y)d y.
$$  

We write  

$$
h=f*g,
$$  

d call the density. $h$ the convolution of the densities $f$ and $g$  

If $X$ $Y$ do not have densities, the argument above may still be taken as far as  

$$
H(z)=I P(Z\leq z)=P(X+Y\leq z)=\int_{-\infty}^{\infty}F(x-y)d G(y)
$$  

(and, again, symmetrically with $F$ and $G$ interchanged), where the integral on the right is the Lebesgue-Stieltjes integral of \$2.2. We again write  

$$
H=F*G,
$$  

and call the distribution function $H$ the convolution of the distribution functions $F$ and $G$  

In sum: addition of independent random variables corresponds to convolution of distribution functions or densities.  

Now we frequently need to add (or average) lots of independent random variables: for example,. when forming sample means in statistics - when the bigger the sample size is, the better. But. convolution involves integration, so adding $n$ independent random variables involves $n-1$ integrations, and this is awkward to do for large $n$ . One thus seeks a way to transform distributions so as to make the awkward operation of convolution as easy to handle as the operation of addition of independent random variables that gives rise to it.  

Definition A.2.1. If $X$ is a random variable with distribution function $F$ ,its characteristic. function $\phi$ (or $\phi_{X}$ if we need to emphasise $X$ ) is  

$$
\phi(t):=I E(e^{i t X})=\int_{-\infty}^{\infty}e^{i t x}d F(x),(t\in I R).
$$  

# Note.  

Here $i:=\sqrt{-1}$ . All other numbers - $t$ $x$ etc. - are real; all expressions involving $i$ such as $e^{i t x}$ $\phi(t)=\mathbb{E}(e^{i t x})$ are complex numbers.  

The characteristic function takes convolution into multiplication: if $X$ $Y$ are independent,  

$$
\phi_{X+Y}(t)=\phi_{X}(t)\phi_{Y}(t).
$$  

For, as. $X$ $Y$ are independent, so are $e^{i t X}$ and $e^{i t Y}$ for any. $t$ , so by the multiplication theorem (Theorem B.3.1),  

$$
E(e^{i t(X+Y)})=I E(e^{i t X}\cdot e^{i t Y})=I E(e^{i t X})\cdot I E(e^{i t Y})
$$  

as required.  

We list some properties of characteristic functions that we shall need.  

1. $\phi(0)=1$ . For, $\phi(0)=E(e^{i\cdot0\cdot X})=E(e^{0})=E(1)=1$  

2. $|\phi(t)|\leq1$ for all $t\in\mathcal{M}$  

Proof. $\begin{array}{r}{|\phi(t)|=\left|\int_{-\infty}^{\infty}e^{i t x}d F(x)\right|\le\int_{-\infty}^{\infty}\left|e^{i t x}\right|d F(x)=\int_{-\infty}^{\infty}1d F(x)=1.}\end{array}$  

Thus in particular the characteristic function always exists (the integral defining it is always. absolutely convergent). This is a crucial advantage, far outweighing the disadvantage of having to work with complex rather than real numbers (the nuisance value of which is in fact slight)..  

3. $\phi$ is continuous (indeed, $\phi$ is uniformly continuous).   
Proof.  

$$
\begin{array}{r c l}{|\phi(t+u)-\phi(t)|}&{=}&{\displaystyle\left\lfloor\displaystyle\int_{-\infty}^{\infty}\{e^{i(t+u)x}-e^{i t x}\}d F(x)\right\rfloor}\ &{=}&{\displaystyle\left\lfloor\displaystyle\int_{-\infty}^{\infty}e^{i t x}(e^{i u x}-1)d F(x)\right\rfloor\le\displaystyle\int_{-\infty}^{\infty}\left\lvert e^{i u x}-1\right\rvert d F(x),}\end{array}
$$  

for all $t$ .Now as $u\rightarrow0$ $\left|e^{i u x}-1\right|\rightarrow0$ , and $\left|e^{i u x}-1\right|\leq2$ .The bound on the right tends. to zero as $u\to0$ by Lebesgue's dominated convergence theorem (which we quote from measure. theory: see e.g. (Williams 1991), 35.9), giving continuity; the uniformity follows as the bound holds uniformly in $t$  

4. (Uniqueness theorem): $\phi$ determines the distribution function $F$ uniquely.  

Technically, $\phi$ is the Fourier-Stieltjes transform of $F$ , and here we are quoting the uniqueness property of this transform. Were uniqueness not to hold, we would lose information on taking characteristic functions, and so $\phi$ would not be useful.  

5. (Continuity theorem): If. $X_{n}$ $X$ are random variables with distribution functions $F_{n}$ $F$ and characteristic functions $\phi_{n}$ $\phi$ , then convergence of. $\phi_{n}$ to $\phi$  

$$
\phi_{n}(t)\to\phi(t)\quad(n\to\infty)\quad\mathrm{for~all}\quad t\in I R
$$  

is equivalent to convergence in distribution of $X_{n}$ to $X$ .This result is due to Levy; see e.g.. (Williams 1991), $\S18.1$  

6. Moments. Suppose $X$ has $k$ th moment: $I E|X|^{k}<\infty$ . Take the Taylor (power-series) expansion of eitx as far as the kth power term:  

$$
e^{i t x}=1+i t x+\cdots+(i t x)^{k}/k!+o\left(t^{k}\right),
$$  

where $\mathbf{\dot{o}}\left(t^{k}\right)^{,}$ denotes an error term of smaller order than $t^{k}$ for small $k$ . Now replace $x$ by $X$ and take expectations. By linearity, we obtain  

$$
\phi(t)=I E(e^{i t X})=1+i t I E X+\cdot\cdot\cdot+\frac{(i t)^{k}}{k!}I E(X^{k})+e(t),
$$  

where the error term $e(t)$ is the expectation of the error terms (now random, as $X$ is random) obtained above (one for each value $X(\omega)$ of $X$ ). It is not obvious, but it is true, that $e(t)$ is still of smaller order than $t^{k}$ for $t\rightarrow0$  

$$
\mathrm{if}\quad\mathbb{E}\left(\left|X\right|^{k}\right)<\infty,\quad\phi(t)=1+i t\mathbb{E}(X)+\ldots+\frac{(i t)^{k}}{k!}\mathbb{E}\left(X^{k}\right)+o\left(t^{k}\right)\quad(t\rightarrow0).
$$  

We shall need the case $k=2$ in dealing with the central limit theorem below.  

# Examples  

# 1. Standard Normal Distribution,  

$N(0,1)$ . For the standard normal density $\begin{array}{r}{f(x)=\frac{1}{\sqrt{2\pi}}\exp\{-\frac{1}{2}x^{2}\}}\end{array}$ , one has, by the process of completing the square' (familiar from when one first learns to solve quadratic equations!),  

$$
\begin{array}{l c l}{{{\displaystyle\int_{-\infty}^{\infty}e^{t x}f(x)d x}}}&{{{=}}}&{{{\displaystyle\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty}\exp\left\{t x-\frac{1}{2}x^{2}\right\}d x}}}\ {{{}}}&{{{=}}}&{{{\displaystyle\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty}\exp\left\{-\frac{1}{2}(x-t)^{2}+\frac{1}{2}t^{2}\right\}d x}}}\ {{{}}}&{{{=}}}&{{{\displaystyle\exp\left\{\frac{1}{2}t^{2}\right\}\cdot\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty}\exp\left\{-\frac{1}{2}(x-t)^{2}\right\}d x.}}}\end{array}
$$  

The second factor on the right is $^{1}$ (it has the form of a normal integral). This gives the integral on the left as $\exp\{\frac{1}{2}t^{2}\}$  

Now replace $t$ by $i t$ (legitimate by analytic continuation, which we quote from complex analysis, see e.g. (Burkill and Burkill 1970)). The right becomes $\exp\{-{\textstyle\frac{1}{2}}t^{2}\}$ .The integral on the left becomes the characteristic function of the standard normal density - which we have thus now identified (and will need below in g2.8).  

# 2. General Normal Distribution,  

$N(\mu,\sigma)$ . Consider the transformation $x\mapsto\mu+\sigma x$ . Applied to a random variable $X$ , this adds. $\mu$ to the mean (a change of location), and multiplies the variance by $\sigma^{2}$ (a change of scale). One can check that if. $X$ has the standard normal density above, then $\mu+\sigma X$ has density  

$$
f(x)=\frac{1}{\sigma\sqrt{2\pi}}\exp{\left\{-\frac{1}{2}(x-\mu)^{2}/\sigma^{2}\right\}},
$$  

and characteristic function  

$$
\begin{array}{c c l}{{E e^{i t(\mu+\sigma X)}}}&{{=}}&{{\exp\{i\mu t\}{\cal{E}}\left(e^{(i\sigma t)X}\right)=\exp\{i\mu t\}\exp\left\{-\displaystyle\frac{1}{2}(\sigma t)^{2}\right\}}}\ {{}}&{{}}&{{}}\ {{}}&{{=}}&{{\exp\left\{i\mu t-\displaystyle\frac{1}{2}\sigma^{2}t^{2}\right\}.}}\end{array}
$$  

Thus the general normal density and its characteristic function are  

$$
f(x)={\frac{1}{\sigma{\sqrt{2\pi}}}}\exp\left\{-{\frac{1}{2}}(x-\mu)^{2}/\sigma^{2}\right\},\phi(t)=\exp\left\{i\mu t-{\frac{1}{2}}\sigma^{2}t^{2}\right\}.
$$  

# 3. Poisson Distribution,  

$P(\lambda)$ . Here, the probability mass function is  

$$
f(k):=I P(X=k)=e^{-\lambda}\lambda^{k}/k!,\quad(k=0,1,2,\ldots).
$$  

The characteristic function is thus  

$$
\begin{array}{l c l}{{\phi(t)}}&{{=}}&{{\displaystyle{\cal E}\left(e^{i t X}\right)=\sum_{k=0}^{\infty}\frac{e^{-\lambda}\lambda^{k}}{k!}\cdot e^{i t k}}}\ {{}}&{{=}}&{{\displaystyle e^{-\lambda}\sum_{k=0}^{\infty}(\lambda e^{i t})^{k}/k!=e^{-\lambda}\exp\{\lambda e^{i t}\}=\exp\{-\lambda(1-e^{i t})\}.}}\end{array}
$$  

# A.3 The Central Limit Theorem  

Readers of this book will be well aware that  

$$
\left(1+{\frac{x}{n}}\right)^{n}\to e^{x}\quad(n\to\infty)\quad\forall x\in I R.
$$  

This is the formula governing the passage from discrete to continuous compound interest. Invest one pound (or dollar) for one year at. $100x\%$ p.a.; with interest compounded $n$ times p.a., our capital after one year is. $(1+{\frac{x}{n}})^{n}$ . With continuous compounding, our capital after one year is the exponential $e^{x}$ : exponential growth corresponds to continuously compounded interest.  

We need two extensions: the formula still holds with $x\in\mathcal{M}$ replaced by a complex number $z\in\pmb{\mathcal{C}}$  

$$
\left(1+{\frac{z}{n}}\right)^{n}\to e^{z}(n\to\infty)\forall z\in\varmathbb{C},
$$  

and if $z_{n}\in\pmb{\mathcal{C}}$ $z_{n}\to z$  

$$
\left(1+{\frac{z_{n}}{n}}\right)^{n}\to e^{z}(n\to\infty)(z_{n}\to z\in\mathbb{C}).
$$  

As a first illustration of the power of transform methods, we prove the weak law of large numbers:  

Theorem A.3.1 (Weak Law of Large Numbers). If $X_{1},X_{2},\dots$ are independent and identically distributed with mean $\mu$ , then  

$$
{\frac{1}{n}}\sum_{i=1}^{n}X_{i}\to\mu~(n\to\infty)~i n~p r o b a b i l i t y.
$$  

Proof. If the $X_{i}$ have characteristic function $\phi$ , then by the moment property of $\S2.8$ with $k=1$  

$$
\phi(t)=1+i\mu t+o(t)\quad(t\to0).
$$  

Now using the i.i.d. assumption, $\textstyle{\frac{1}{n}}\sum_{i=1}^{n}X_{i}$ has characteristic function  

$$
\begin{array}{r c l}{{\displaystyle\mathbb{E}\left(\exp\left\{i t\cdot\frac{1}{n}\sum_{1}^{n}X_{j}\right\}\right)}}&{{=}}&{{\displaystyle\mathbb{E}\left(\prod_{i=1}^{n}\exp\left\{i t\cdot\frac{1}{n}X_{j}\right\}\right)}}\ {{}}&{{=}}&{{\displaystyle\prod_{i=1}^{n}{\cal E}\left(\exp\left\{\frac{i t}{n}X_{j}\right\}\right)=(\phi(t/n))^{n}}}\ {{}}&{{=}}&{{\displaystyle\left(1+\frac{i\mu t}{n}+o\left(1/n\right)\right)^{n}\rightarrow e^{i\mu t}(n\rightarrow\infty),}}\end{array}
$$  

and $e^{i\mu t}$ is the characteristic function of the constant $\mu$ (for fixed $t$ ${\cal o}\left(1/n\right)$ is an error term of smaller order than $1/n$ as $n\to\infty$ ). By the continuity theorem,  

$$
{\frac{1}{n}}\sum_{i=1}^{n}X_{i}\to\mu{\mathrm{~in~distribution}},
$$  

and as $\mu$ is constant, this says (see 2.6) that  

$$
{\frac{1}{n}}\sum_{1}^{n}X_{i}\to\mu{\mathrm{~in~probability.}}
$$  

The main result of this section is the same argument carried one stage further.  

Theorem A.3.2 (Central Limit Theorem). If $X_{1},X_{2},\dots$ are independent and identically distributed with mean $\mu$ and variance $\sigma^{2}$ , then with $N(0,1)$ the standard normal distribution,  

$$
{\frac{\sqrt{n}}{\sigma}}{\frac{1}{n}}\sum_{i=1}^{n}(X_{i}-\mu)={\frac{1}{\sqrt{n}}}\sum_{i=1}^{n}(X_{i}-\mu)/\sigma\rightarrow N(0,1)(n\rightarrow\infty)i n d i s t r i b u t i o n.
$$  

That is, for all $x\in\mathcal{R}$  

$$
{\cal P}\left(\frac{1}{\sqrt{n}}\sum_{i=1}^{n}(X_{i}-\mu)/\sigma\leq x\right)\to\Phi(x):=\frac{1}{\sqrt{2\pi}}\int^{x}e^{-\frac{1}{2}y^{2}}d y~(n\to\infty).
$$  

Proof. We first centre at the mean. If $X_{i}$ has characteristic function $\phi$ , let $X_{i}-\mu$ have characteristic function $\phi_{0}$ .Since $X_{i}-\mu$ has mean $0$ and second moment $\begin{array}{r}{\sigma^{2}=V a r(X_{i})=}\end{array}$ $E[(X_{i}-H X_{i})^{2}]=l E[(X_{i}-\mu)^{2}]$ , the case $k=2$ of the moment property of g2.7 gives  

$$
\phi_{0}(t)=1-\frac{1}{2}\sigma^{2}t^{2}+{\pmb o}\left(t^{2}\right)\quad(t\rightarrow0).
$$  

Now $\textstyle{\sqrt{n}}({\frac{1}{n}}\sum_{i=1}^{n}X_{i}-\mu)/\sigma$ has characteristic function  

$$
\begin{array}{r l}&{E\left(\exp\left\{i t\cdot\frac{\sqrt{n}}{\sigma}\left(\frac{1}{n}\displaystyle\sum_{j=1}^{n}X_{j}-\mu\right)\right\}\right)}\ {=}&{E\left(\displaystyle\prod_{j=1}^{n}\exp\left\{\frac{i t(X_{j}-\mu)}{\sigma\sqrt{n}}\right\}\right)=\displaystyle\prod_{j=1}^{n}E\left(\exp\left\{\frac{i t}{\sigma\sqrt{n}}(X_{j}-\mu)\right\}\right)}\ {=}&{\left(\phi_{0}\left(\frac{t}{\sigma\sqrt{n}}\right)\right)^{n}=\left(1-\frac{\frac{1}{2}\sigma^{2}t^{2}}{\sigma^{2}n}+o\left(\frac{1}{n}\right)\right)^{n}\rightarrow e^{-\frac{1}{2}t^{2}}(n\rightarrow\infty),}\end{array}
$$  

and $e^{-\frac{1}{2}t^{2}}$ is the characteristic function of the standard normal distribution $N(0,1)$ . The result follows by the continuity theorem..  

# Note.  

In Theorem A.3.2, we:  

(i) centre the. $X_{i}$ by subtracting the mean (to get mean $0$ );   
(ii) scale the resulting $X_{i}-\mu$ by dividing by the standard deviation $\sigma$ (to get variance 1). Then if $Y_{i}:=(X_{i}-\mu)/\sigma$ are the resulting standardised variables, ${\frac{1}{\sqrt{n}}}\sum_{1}^{n}Y_{i}$ converges in distribution to standard normal.  

# Example: the Binomial Case.  

If each $X_{i}$ is Bernoulli distributed with parameter $p\in(0,1)$  

$$
\begin{array}{r}{I P(X_{i}=1)=p,~I P(X_{i}=0)=q:=1-p}\end{array}
$$  

- so $X_{i}$ has mean $p$ and variance $\begin{array}{r}{p q-S_{n}:=\sum_{i=1}^{n}X_{i}}\end{array}$ is binomially distributed with parameters $n$ and $p$  

$$
P\left(\sum_{i=1}^{n}X_{i}=k\right)={\binom{n}{k}}p^{k}q^{n-k}={\frac{n!}{(n-k)!k!}}p^{k}q^{n-k}.
$$  

A direct attack on the distribution of $\textstyle{\frac{1}{\sqrt{n}}}\sum_{i=1}^{n}(X_{i}-p)/{\sqrt{p q}}$ can be made via  

$$
{\cal P}\left(a\leq\sum_{i=1}^{n}X_{i}\leq b\right)=\sum_{k:n p+a\sqrt{n p q}\leq k\leq n p+b\sqrt{n p q}}{\frac{n!}{(n-k)!k!}}p^{k}q^{n-k}.
$$  

Since $n$ $k$ and $n-k$ will all be large here, one needs an approximation to the factorials. The required result is Stirling's formula of 1730:.  

$$
n!\sim{\sqrt{2\pi}}e^{-n}n^{n+{\frac{1}{2}}}\quad(n\to\infty)
$$  

(the symbol $\sim$ indicates that the ratio of the two sides tends to 1). The argument can be carried. $\textstyle\int_{a}^{b}{\frac{1}{\sqrt{2\pi}}}e^{-{\frac{1}{2}}x^{2}}d x$ 1827). The proof of the de-Moivre-Laplace limit theorem sketched above is closely analogous to the passage from the discrete to the continuous Black-Scholes formula: see \$4.6 and \$6.4..  

# Local Limit Theorems.  

The central limit theorem as proved above is a global limit theorem: it relates to distributions and convergence thereof. The de Moivre-Laplace limit theorem above, however, deals directly with individual probabilities in the discrete case (the sum of a large number of which is shown to approximate an integral). A limit theorem dealing with densities and convergence thereof in the density case, or with the discrete analogues of densities - such as the individual probabilities $\textstyle{\mathit{I P}}(S_{n}=k)$ in the binomial case above - is called a local limit theorem.  

# Poisson Limit Theorem.  

The de Moivre-Laplace limit theorem - convergence of binomial to normal - is only one possible limiting regime for binomial models. The next most important one has a Poisson limit in place of a normal one.  

Suppose we have a sequence of binomial models $B(n,p)$ , where the success probability $p=p_{n}$ varies with $n$ , in such a way that  

$$
n p_{n}\to\lambda\to0,(n\to\infty).
$$  

Thus. $p_{n}\to0$ - indeed, $p_{n}\sim\lambda/n$ . This models a situation where we have a large number $n$ of Bernoulli trials, each with small probability $p_{n}$ of success, but such that $n p_{n}$ , the expected total number of successes, is 'neither large nor small, but intermediate'. Binomial models satisfying condition (A.1) converge to the Poisson model $P(\lambda)$ with parameter $\lambda>0$  

This result is sometimes called the law of small numbers. The Poisson distribution is widely used to model statistics of accidents, insurance claims and the like, where one has a large number $n$ of individuals at risk, each with a small probability $p_{n}$ of generating an accident, insurance claim etc. ('success probability' seems a strange usage here!).  

# Appendix B  

# Facts form Probability and Measure Theory  

We will assume that most readers will be familiar with such things from an elementary course in probability and statistics; for a clear introduction see, e.g. Grimmett and Welsh (1986), or the first few chapters of ?; Ross (1997), Resnick (2001), Durrett (1999), Ross (1997), Rosenthal (2000) are also useful.  

# B.1 Measure  

The language of modelling financial markets involves that of probability, which in turn involves. that of measure theory. This originated with Henri Lebesgue (1875-1941), in his thesis, 'Integrale, longueur, aire' Lebesgue (1902). We begin with defining a measure on. $\mathit{\Pi}_{\mathit{\Pi}}{\mathit{\Pi}}_{\mathit{\Pi}}{\mathit{\Pi}}_{\mathit{\Pi}}{\mathit{\Pi}}_{\mathit{\Pi}}\quad{\mathit{\Pi}}_{\mathit{\Pi}}\quad{\mathit{\Pi}}_{\mathit{\Pi}}\quad\mathit{\Pi}_{\mathit{\Pi}}\quad\mathit{\Pi}_{\mathit{\Pi}}\quad\quad\mathit{\Pi}_{\mathit{\Pi}}\quad\quad\mathit{\Pi}_{\mathit{\Pi}}\quad\quad\quad\mathrm{\delta}_{\mathit{\Pi}}\quad\quad\mathrm{\delta}_{\mathit{\Pi}}\quad\quad\mathrm{\delta}_{\mathit{\Pi}}\quad\quad\mathrm{\delta}_{\mathit{\Pi}}\quad\quad\mathrm{\delta}_{\mathit{\Pi}}\quad\quad\mathrm{\delta}_{\mathit{\Pi}}\quad\quad\mathrm{\delta}_{\mathit{\Pi}}\quad\quad\mathrm{\delta}_{\mathit\mathit{\Pi}}\quad\quad\mathrm{\delta}_{\mathit\mathit{\Pi}}\quad\quad\mathrm{\delta}_{\mathit\mathit{\Pi}}\quad\quad\mathrm{\delta}_{\mathit\mathit{\Pi}}\quad\quad\mathrm{\delta}_{\mathit\mathit{\Pi}}\quad\quad\mathrm{\delta}_{\mathit\mathrm{\Pi}}\quad\quad\mathrm{\delta}_{\mathrm\mathrm{\delta}}_{\mathit\mathit{\delta}}\quad\quad\quad\mathrm{\delta}\quad\quad\$ generalising the intuitive notion of length.  

The length $\mu(I)$ of an interval. $I=(a,b),[a,b],[a,b)$ or $(a,b]$ should be $b-a$ .. $\mu(I)=b-a$ . The length of the disjoint union. $\textstyle I=\bigcup_{r=1}^{n}I_{r}$ of intervals $I_{r}$ should be the sum of their lengths:  

$$
\mu\left(\bigcup_{r=1}^{n}I_{r}\right)=\sum_{r=1}^{n}\mu(I_{r})\qquad(\mathrm{finite~additivity}).
$$  

Consider now an infinite sequence. $I_{1},I_{2},...(a d i n f i n i t u m)$ of disjoint intervals. Letting. $n$ tend to $\infty$ suggests that length should again be additive over disjoint intervals:  

$$
\mu\left(\bigcup_{r=1}^{\infty}I_{r}\right)=\sum_{r=1}^{\infty}\mu(I_{r})\qquad(\mathrm{countable~additivity}).
$$  

For $I$ an interval, $A$ a subset of length $\mu(A)$ , the length of the complement $I\setminus A:=I\cap A^{c}$ of $A$ in $I$ should be  

$$
\mu(I\setminus A)=\mu(I)-\mu(A)\qquad({\mathrm{complementation}}).
$$  

If $A\subseteq B$ and $B$ has length $\mu(B)=0$ , then $A$ should have length 0 also:  

$$
A\subseteq B{\mathrm{~and~}}\mu(B)=0\Rightarrow\mu(A)=0{\mathrm{~(completeness)}}.
$$  

The term 'countable' here requires comment. We must distinguish first between finite and infinite sets; then countable sets (like ${I N}=\left\{1,2,3,\ldots\right\}$ ) are the 'smallest, or 'simplest', infinite sets, as. distinct from uncountable sets such as. ${\cal{R}}=(-\infty,\infty)$  

Let $\mathcal{F}$ be the smallest class of sets $A\subset\mathcal{R}$ containing the intervals, closed under countable. disjoint unions and complements, and complete (containing all subsets of sets of length 0 as sets of length 0). The above suggests - what Lebesgue showed - that length can be sensibly defined on the.  

sets $\mathcal{F}$ on the line, but on no others. There are others - but they are hard to construct (in technical. language: the axiom of choice, or some variant of it such as Zorn's lemma, is needed to demonstrate the existence of non-measurable sets - but all such proofs are highly non-constructive). So: some but not all subsets of the line have a length. These are called the Lebesgue-measurable sets, and. form the class $\mathcal{F}$ described above; length, defined on $\mathcal{F}$ , is called Lebesgue measure $\mu$ (on the real line, $\mathscr{R}$ ). Turning now to the general case, we make the above rigorous. Let. $\Omega$ be a set.  

Definition B.1.1. A collection $A_{0}$ of subsets of. $\Omega$ is called an algebra on. $\Omega$ if:  

(i) $\Omega\in A_{0}$ (ii) $A\in\mathcal{A}_{0}\Rightarrow A^{c}=\Omega\backslash A\in\mathcal{A}_{0}$ (iii) $A,B\in\mathcal{A}_{0}\Rightarrow A\cup B\in\mathcal{A}_{0}$  

Using this definition and induction, we can show that an algebra on $\Omega$ is a family of subsets of $\Omega$ closed under finitely many set operations.  

Definition B.1.2. An algebra $\mathcal{A}$ of subsets of. $\Omega$ is called a $\sigma$ -algebra on. $\Omega$ if for any sequence $A_{n}\in{\mathcal{A}},(n\in I N)$ , we have.  

$$
\bigcup_{n=1}^{\infty}A_{n}\in{\mathcal{A}}.
$$  

Such a pair $(\Omega,A)$ is called a measurable space.  

Thus a $\sigma$ -algebra on $\Omega$ is a family of subsets of $\Omega$ closed under any countable collection of set operations.  

The main examples of. $\sigma$ -algebras are $\sigma$ -algebras generated by a class $\mathcal{C}$ of subsets of $\Omega$ , i.e. $\sigma(\mathcal{C})$ is the smallest. $\sigma$ -algebra on $\Omega$ containing $\mathit{c}$  

The Borel $\sigma$ -algebra $B=B(\mathit{\mathit{R}})$ is the $\sigma$ -algebra of subsets of $\mathit{\Pi}_{\mathit{{M}}}$ generated by the open intervals (equivalently, by half-lines such as $(-\infty,x]$ as $x$ varies in $\mathit{\Pi}_{\mathit{\Pi}}{\mathit{\Pi}}_{\mathit{\Pi}}{\mathit{\Pi}}_{\mathit{\Pi}}^{\mathit{\Pi}}\mathit{\Pi}_{\mathit{\Pi}}\mathit{\Pi}_{\mathit{\Pi}}\mathit{\Pi}_{\mathit{\Pi}}\mathit{\Pi}_{\mathit{\Pi}}\mathit{\Pi}_{\mathit{\Pi}}\mathit{\Pi}_{\mathit{\Pi}}\mathit{\Pi}_{\mathit{\Pi}}\mathit{\Pi}_{\mathit{\Pi}}\mathit{\Pi}_{\mathit{\Pi}}\quad\mathit{\Pi}_{\mathit{\Pi}}\mathit{\Pi}_{\mathit{\Pi}}\quad\mathit{\Pi}_{\mathit{\Pi}}\quad\mathit{\Pi}_{\mathit{\Pi}}\quad\mathit{\Pi}_{\mathit{\Pi}}\quad\$  

As our aim is to define measures on collection of sets we now turn to set functions.  

Definition B.1.3. Let $\Omega$ be a set, $A_{\mathrm{0}}$ an algebra on $\Omega$ and $\mu_{0}$ a non-negative set function $\mu_{0}:$ $A_{0}\rightarrow[0,\infty]$ such that $\mu_{0}(\varnothing)=0$ $\mu_{0}$ is called:  

(i) additive, if $A,B\in A_{0},A\cap B=\varnothing\Rightarrow\mu_{0}(A\cup B)=\mu_{0}(A)+\mu_{0}(B)$   
(ii) countably additive, if whenever $(A_{n})_{n\in\mathbb{N}}$ is a sequence of disjoint sets in $A_{0}$ with $\cup A_{n}\in A_{0}$   
then  

$$
\mu_{0}\left(\bigcup_{n=0}^{\infty}A_{n}\right)=\sum_{n=1}^{\infty}\mu_{0}(A_{n}).
$$  

Definition B.1.4. Let $(\Omega,A)$ be a measurable space. $A$ countably additive map  

$$
\mu:{\mathcal{A}}\rightarrow[0,\infty]
$$  

is called a measure on $(\Omega,A)$ . The triple. $(\Omega,A,\mu)$ is called a measure space.  

Recall that our motivating example was to define a measure on $\mathscr{R}$ consistent with our geometrical knowledge of length of an interval. That means we have a suitable definition of measure on. a family of subsets of. $\mathscr{R}$ and want to extend it to the generated. $\sigma$ -algebra. The measure-theoretic. tool to do so is the Caratheodory extension theorem, for which the following lemma is an inevitable prerequisite.  

Lemma B.1.1. Let $\Omega$ be a set. Let $\boldsymbol{\mathcal{T}}$ be a $\pi$ -system on $\Omega$ , that is, a family of subsets of $\Omega$ closed under finite intersections: $I_{1},I_{2}\in\mathcal{T}\Rightarrow I_{1}\cap I_{2}\in\mathcal{T}$ . Let $\mathcal{A}=\sigma(\mathcal{T})$ and suppose that $\mu_{1}$ and $\mu_{2}$ are finite measures on $(\Omega,A)$ (i.e. $\mu_{1}(\Omega)=\mu_{2}(\Omega)<\infty,$ ) and $\mu_{1}=\mu_{2}$ on $\mathcal{L}$ . Then  

$$
\mu_{1}=\mu_{2}o n{\mathcal{A}}.
$$  

Theorem B.1.1 (Caratheodory Extension Theorem). Let $\Omega$ be a set, $A_{\mathrm{0}}$ an algebra on $\Omega$ and $\mathcal{A}=\sigma(\mathcal{A}_{0})$ . If $\mu_{0}$ is a countably additive set function on $A_{0}$ , then there exists a measure $\mu$ on $(\Omega,A)$ such that  

$$
\mu=\mu_{0}o n{\mathcal{A}}_{0}.
$$  

If $\mu_{0}$ is finite, then the extension is unique.  

For proofs of the above and further discussion, we refer the reader to Chapter 1 and Appendix 1 of Williams (1991) and the appendix in Durrett (1996).  

Returning to the motivating example $\Omega=\mathcal{M}$ , we say that. $A\subset{\mathcal{R}}$ belongs to the collection of. sets $A_{0}$ if $A$ can be written as.  

$$
A=(a_{1},b_{1}]\cup\ldots\cup(a_{r},b_{r}],
$$  

where $r\in\mathcal{N}$ $-\infty\leq a_{1}<b_{1}\leq\ldots\leq a_{r}<b_{r}\leq\infty$ . It can be shown that $\mathcal{A}_{0}$ is an algebra and.   
$\sigma(\mathcal{A}_{0})=B$ . For $A$ as above define.  

$$
\mu_{0}(A)=\sum_{k=1}^{r}(b_{k}-a_{k}).
$$  

$\mu_{0}$ is well-defined and countably additive on. $\mathcal{A}_{0}$ . As intervals belong to $A_{\mathrm{0}}$ our geometric intuition of length is preserved. Now by Caratheodory's extension theorem there exists a measure $\mu$ on $(\Omega,B)$ extending $\mu_{0}$ on $(\Omega,A_{0})$ . Thise $\mu$ is called Lebesgue measure.  

With the same approach we can generalise:  

(i) the area of rectangles $R=(a_{1},b_{1})\times(a_{2},b_{2})$ with or without any of its perimeter included - given by $\mu(R)=(b_{1}-a_{1})\times(b_{2}-a_{2})$ to Lebesgue measure on Borel sets in $\mathit{\Pi}\mathcal{R}^{2}$ (ii) the volume of cuboids $C=(a_{1},b_{1})\times(a_{2},b_{2})\times(a_{3},b_{3})$ given by  

$$
\mu(C)=(b_{1}-a_{1})\cdot(b_{2}-a_{2})\cdot(b_{3}-a_{3})
$$  

to Lebesgue measure on Borel sets in $\mathit{\Pi}\mathit{\mathit{\Pi}}\mathit{\mathit{\Pi}}\mathit{\mathit{\Pi}}\mathit{\mathit{\Pi}}\mathit{\mathit{\Pi}}\mathit{\mathit{\Pi}}\mathit{\mathit{\Pi}}\mathit{\mathit{\Pi}}\mathit{\mathit{\Pi}}\mathit{\mathit{\Pi}}\mathit{\mathit{\Pi}}\mathit{\mathit{\Pi}}\mathit{\mathit{\Pi}}\mathit{\mathit{\Pi}}\mathit{\mathit{\Pi}}\mathit{\mathit{\Pi}}\mathit{\mathit{\Pi}}\mathit{\mathit{\Pi}}\mathit{\mathit{\Pi}}$  

(iii) and similarly in. $k$ -dimensional Euclidean space. $\smash{\varmathbb{R}^{k}}$ .We start with the formula for a $k$ dimensional box,  

$$
\mu\left(\prod_{i=1}^{k}(a_{i},b_{i})\right)=\prod_{i=1}^{k}(b_{i}-a_{i}),
$$  

and obtain Lebesgue measure $\mu$ , defined on $\boldsymbol{\it B}$ , in $\smash{\varmathbb{R}^{k}}$  

We are mostly concerned with a special class of measures:  

Definition B.1.5. A measure $\mathcal{W}$ on a measurable space $(\Omega,A)$ is called a probability measure if  

$$
{\cal I P}(\Omega)=1.
$$  

The triple. $(\Omega,{\cal A},{\cal P})$ is called a probability space.  

Observe that the above lemma and Caratheodory's extension theorem guarantee uniqueness if we construct a probability measure using the above procedure. For example the unit cube $[0,1]^{k}$ in ${\mathbf{\varLambda}}{\mathbf{\varLambda}}{\mathbf{\varLambda}}{\mathbf{\varLambda}}$ has (Lebesgue) measure 1. Using. $\Omega=[0,1]^{k}$ as the underlying set in the above construction. we find a unique probability (which equals length/area/volume if $k=1/2/3$  

If a property holds everywhere except on a set of measure zero, we say it holds almost everywhere (a.e.). If it holds everywhere except on a set of probability zero, we say it holds almost surely (a.s.) (or, with probability one).  

Roughly speaking, one uses addition in countable (or finite) situations, integration in uncountable ones. As the key measure-theoretic axiom of countable additivity above concerns addition, countably infinite situations (such as we meet in discrete time) fit well with measure theory. By contrast, uncountable situations (such as we meet in continuous time) do not - or at least, are considerably harder to handle. This is why the discrete-time setting of Chapters 3, 4 is easier than, and precedes, the continuous-time setting of Chapters 5, 6. Our strategy is to do as much as possible to introduce the key ideas - economic, financial and mathematical - in discrete time (which, because we work with a finite time-horizon, the expiry time $T$ , is actually a finite situation), before treating the harder case of continuous time.  

# B.2 Integral  

Let $(\Omega,A)$ be a measurable space. We want to define integration for a suitable class of real-valued functions.  

Definition B.2.1. Let $f:\Omega\to\mathbb{R}$ . For $A\subset{\mathcal{R}}$ define $f^{-1}(A)=\{\omega\in\Omega:f(\omega)\in A\}$ $f$ is called (A-) measurable if  

Let $\mu$ be a measure on $(\Omega,A)$ . Our aim now is to define, for suitable measurable functions, the (Lebesgue) integral with respect to $\mu$ . We will denote this integral by  

$$
\mu(f)=\intop_{\Omega}f d\mu=\intop_{\Omega}f(\omega)\mu(d\omega).
$$  

We start with the simplest functions. If $A\in{\mathcal{A}}$ the indicator function $\mathbf{1}_{A}(\omega)$ is defined by.  

$$
\mathbf{1}_{A}(\omega)={\left\{\begin{array}{l l}{1,}&{{\mathrm{if~}}\omega\in A}\ {0,}&{{\mathrm{if~}}\omega\notin A.}\end{array}\right.}
$$  

Then define $\mu(\mathbf{1}_{A})=\mu(A)$  

The next step extends the definition to simple functions. A function $f$ is called simple if it is a finite linear combination of indicators: $\textstyle f=\sum_{i=1}^{n}c_{i}\mathbf{1}_{A_{i}}$ for constants $c_{i}$ and indicator functions $\mathbf{1}_{A_{i}}$ of measurable sets $A_{i}$ . One then extends the definition of the integral from indicator functions to simple functions by linearity:  

$$
\mu\left(\sum_{i=1}^{n}c_{i}\mathbf{1}_{A_{i}}\right):=\sum_{i=1}^{n}c_{i}\mu(\mathbf{1}_{A_{i}})=\sum_{i=1}^{n}c_{i}\mu(A_{i}),
$$  

or constants $c_{i}$ and indicators of measurable sets $A_{i}$  

If $f$ is a non-negative measurable function, we define  

$$
\mu(f):=\operatorname*{sup}\{\mu(f_{0}):f_{0}{\mathrm{~simple}},f_{0}\leq f\}.
$$  

The key result in integration theory, which we must use here to guarantee that the integral for non-negative measurable functions is well-defined is:.  

Theorem B.2.1 (Monotone Convergence Theorem). If ( $f_{n})$ is a sequence of non-negative.   
measurable functions such that. $f_{n}$ is strictly monotonic increasing to a function $f$ (which is then.   
also measurable), then. $\mu(f_{n})\to\mu(f)\leq\infty$  

We quote that we can construct each non-negative measurable $f$ as the increasing limit of a. sequence of simple functions $f_{n}$  

$$
f_{n}(\omega)\uparrow f(\omega)\mathrm{for~all}\omega\in\Omega\mathrm{(}n\rightarrow\infty),f_{n}\mathrm{simple.}
$$  

Using the monotone convergence theorem we can thus obtain the integral of $f$ as  

$$
\mu(f):=\operatorname*{lim}_{n\to\infty}\mu(f_{n}).
$$  

Since $f_{n}$ increases in $n$ , so does. $\mu(f_{n})$ (the integral is order-preserving), so either $\mu(f_{n})$ increases to a finite limit, or diverges to. $\infty$ .In the first case, we say. $f$ is (Lebesgue-) integrable with. (Lebesgue-) integral $\mu(f)=\operatorname*{lim}\mu(f_{n})$  

Finally if $f$ is a measurable function that may change sign, we split it into its positive and negative parts, $f_{\pm}$  

$$
\begin{array}{r l}&{f_{+}(\omega):=\operatorname*{max}(f(\omega),0),\quad f_{-}(\omega):=-\operatorname*{min}(f(\omega),0),}\ &{f(\omega)=f_{+}(\omega)-f_{-}(\omega),\quad|f(\omega)|=f_{+}(\omega)+f_{-}(\omega).}\end{array}
$$  

If both $f_{+}$ and $f_{-}$ are integrable, we say that $f$ is too, and define  

$$
\mu(f):=\mu(f_{+})-\mu(f_{-}).
$$  

Thus, in particular, $|f|$ is also integrable, and  

$$
\mu(|f|)=\mu(f_{+})+\mu(f_{-}).
$$  

The Lebesgue integral thus defined is, by construction, an absolute integral: $f$ is integrable iff $|f|$ is integrable. Thus, for instance, the well-known formula.  

$$
\int_{0}^{\infty}{\frac{\sin{x}}{x}}d x={\frac{\pi}{2}}
$$  

has no meaning for Lebesgue integrals, since $\textstyle\int_{1}^{\infty}{\frac{|\sin x|}{x}}d x$ diverges to $+\infty$ like $\textstyle\int_{1}^{\infty}{\frac{1}{x}}d x$ . It has to be replaced by the limit relation  

$$
\int_{0}^{X}{\frac{\sin{x}}{x}}d x\to{\frac{\pi}{2}}(X\to\infty).
$$  

The class of (Lebesgue-) integrable functions $f$ on $\Omega$ is written. $\mathcal{L}(\Omega)$ or (for reasons explained below) $\mathcal{L}^{1}(\Omega)$ - abbreviated to $\mathcal{L}^{1}$ or $\mathcal{L}$  

For $p\geq1$ , the $\mathcal{L}^{p}$ space ${\mathcal{L}}^{p}(\Omega)$ on $\Omega$ is the space of measurable functions $f$ with $\mathcal{L}^{p}$ -norm  

$$
\|f\|_{p}:=\left(\int_{\Omega}|f|^{p}d\mu\right)^{\frac{1}{p}}<\infty.
$$  

The case $p=2$ gives $\mathcal{L}^{2}$ , which is particular important as it is a Hilbert space (Appendix A).  

Turning now to the special case $\Omega=\pi^{k}$ we recall the well-known Riemann integral. Math-. ematics undergraduates are taught the Riemann integral (G.B. Riemann (1826-1866)) as their first rigorous treatment of integration theory - essentially this is just a rigorisation of the school integral. It is much easier to set up than the Lebesgue integral, but much harder to manipulate.  

For finite intervals $[a,b]$ ,we quote:  

(i) for any function $f$ Riemann-integrable on $[a,b]$ , it is Lebesgue-integrable to the same value (but many more functions are Lebesgue integrable);   
(ii) $f$ is Riemann-integrable on $[a,b]$ iff it is continuous a.e. on $[a,b]$ . Thus the question, 'Which functions are Riemann-integrable?' cannot be answered without the language of measure theory - which gives one the technically superior Lebesgue integral anyway.  

Suppose that $F(x)$ is a non-decreasing function on $\mathit{\Pi}_{\mathit{\Pi}}{\mathit{\Pi}}_{\mathit{\Pi}}{\mathit{\Pi}}_{\mathit{\Pi}}^{\mathit{\Pi}}\mathit{\Pi}_{\mathit{\Pi}}\mathit{\Pi}_{\mathit{\Pi}}\mathit{\Pi}_{\mathit{\Pi}}\mathit{\Pi}_{\mathit{\Pi}}\mathit{\Pi}_{\mathit{\Pi}}\mathit{\Pi}_{\mathit{\Pi}}\mathit{\Pi}_{\mathit{\Pi}}\mathit{\Pi}_{\mathit{\Pi}}\mathit{\Pi}_{\mathit{\Pi}}\quad\mathit{\Pi}_{\mathit{\Pi}}\mathit{\Pi}_{\mathit{\Pi}}\quad\mathit{\Pi}_{\mathit{\Pi}}\quad\mathit{\Pi}_{\mathit{\Pi}}\quad\mathit{\Pi}_{\mathit{\Pi}}\quad\$  

$$
F(x)\leq F(y)\quad{\mathrm{~if~}}x\leq y.
$$  

Such functions can have at most countably many discontinuities, which are at worst jumps. We may without loss redefine $F$ at jumps so as to be right-continuous. We now generalise the starting. points above:  

. Measure. We take $\mu((a,b]):=F(b)-F(a)$  

Integral. We have $\mu(\mathbf{1}_{(a,b]})=\mu((a,b])=F(b)-F(a)$  

We may now follow through the successive extension procedures used above. We obtain:  

. Lebesgue-Stieltjes measure $\mu_{F}$ . Lebesgue-Stieltjes integral $\textstyle\mu_{F}(f)=\int f d\mu_{F}$ , or even $\textstyle\int f d F$  

The approach generalises to higher dimensions; we omit further details.  

If instead of being monotone non-decreasing, $F$ is the difference of two such functions,. $F=$ $F_{1}-F_{2}$ , we can define the integrals. $\int f d F_{1},\int f d F_{2}$ as above, and then define.  

$$
\int f d F=\int f d(F_{1}-F_{2}):=\int f d F_{1}-\int f d F_{2}.
$$  

If $[a,b]$ is a finite interval and. $F$ is defined on. $[a,b]$ , a finite collection of points, with $x_{0},x_{1},\ldots,x_{n}$ $a=x_{0}<x_{1}<\cdots<x_{n}=b$ , is called a partition of. $[a,b]$ $\mathcal{P}$ say. The sum $\textstyle\sum_{i=1}^{n}|F(x_{i})-F(x_{i-1})|$ is called the variation of $F$ over the partition. The least upper bound of this over all partitions $\mathcal{P}$ is called the variation of $F$ over the interval. $[a,b]$ $V_{a}^{b}(F)$  

$$
V_{a}^{b}(F):=\operatorname*{sup}_{\mathcal{P}}\sum|F(x_{i})-F(x_{i-1})|.
$$  

This may be. $+\infty$ ; but if $V_{a}^{b}(F)<\infty$ $F$ is said to be of bounded variation on. $[a,b]$ $F\in B V_{a}^{b}$ If $F$ is of bounded variation on all finite intervals, $F$ is said to be locally of bounded variation, $F\in B V_{\mathrm{loc}}$ ; if $F$ is of bounded variation on the real line $\mathscr{R}$ $F$ is of bounded variation,. $F\in B V$  

We quote that the following two properties are equivalent:  

(i) $F$ is locally of bounded variation, (ii) $F$ can be written as the difference $F=F_{1}-F_{2}$ of two monotone functions.  

So the above procedure defines the integral $\textstyle\int f d F$ when the integrator $F$ is of bounded variation.  

Remark B.2.1. (i) When we pass from discrete to continuous time, we will need to handle both 'smooth' paths and paths that vary by jumps - of bounded variation - and rough' ones - of unbounded variation but bounded quadratic variation; (i) The Lebesgue-Stieltjes integral $\textstyle\int g(x)d F(x)$ is needed to express the expectation $E g(X)$ , where $X$ is random variable with distribution function $F$ and $g$ a suitable function.  

# B.3 Probability  

As we remarked in the introduction of this chapter, the mathematical theory of probability can be traced to 1654, to correspondence between Pascal (1623-1662) and Fermat (1601-1665). However, the theory remained both incomplete and non-rigorous until the 20th century. It turns out that the Lebesgue theory of measure and integral sketched above is exactly the machinery needed to construct a rigorous theory of probability adequate for modelling reality (option pricing, etc.) for us. This was realised by Kolmogorov (1903-1987), whose classic book of 1933, Grundbegriffe der Wahrscheinlichkeitsrechnung (Foundations of Probability Theory), Kolmogorov (1933), inaugurated the modern era in probability.  

Recall from your first course on probability that, to describe a random experiment mathematically, we begin with the sample space $\Omega$ , the set of all possible outcomes. Each point $\omega$ of $\Omega$ , or sample point, represents a possible - random - outcome of performing the random experiment. For a set $A\subseteq\Omega$ of points $\omega$ we want to know the probability $\textstyle{\mathcal{P}}(A)$ (or $\operatorname*{Pr}(A),\operatorname{pr}(A),$ . We clearly want  

$\begin{array}{r l}{\small{\mathrm{~\alpha~}})}&{{}\mathit{I P}(\varnothing)=0,\mathit{I P}(\Omega)=1,}\end{array}$  

(ii) $P(A)\geq0{\mathrm{~for~all~}}A,$   
(iii) If $A_{1},A_{2},\ldots,A_{n}$ are disjoint, $\textstyle P(\bigcup_{i=1}^{n}A_{i})=\sum_{i=1}^{n}P(A_{i})$ (finite additivity), which, as above we will strengthen to  

(ii)\* If $A_{1},A_{2}\ldots(a d i n f.)$ are disjoint,  

$$
P\left(\bigcup_{i=1}^{\infty}A_{i}\right)=\sum_{i=1}^{\infty}P(A_{i})\qquad{\mathrm{(countable~additivity)}}.
$$  

(iv) If $B\subseteq A$ and $\textstyle{\mathcal{P}}(A)=0$ , then $\textstyle{\mathcal{P}}(B)=0$ (completeness).  

Then by (i) and (i) (with $A=A_{1},\Omega\setminus A=A_{2})$  

$$
P(A^{c})=P(\Omega\backslash A)=1-P(A).
$$  

So the class $\mathcal{F}$ of subsets of $\Omega$ whose probabilities ${\cal{P}}(A)$ are defined (call such $A$ events) should be closed under countable, disjoint unions and complements, and contain the empty set $\varnothing$ and the whole space $\Omega$ . Therefore $\mathcal{F}$ should be a $\sigma$ -algebra and $\mathcal{W}$ should be defined on $\mathcal{F}$ according to Definition 2.1.5. Repeating this:.  

Definition B.3.1. $A$ probability space, or Kolmogorov triple, is a triple $(\Omega,{\mathcal{F}},I P)$ satisfying Kolmogorov axioms $(i),(i i),(i i i)^{*}$ (iv) above.  

A probability space is a mathematical model of a random experiment. Often we quantify outcomes $\omega$ of random experiments by defining a real-valued function $X$ on $\Omega$ , i.e. $X:\Omega\to{\mathit{I R}}$ . If such a function is measurable it is called a random variable.  

Definition B.3.2. Let $(\Omega,{\mathcal{F}},I P)$ be a probability space. $A$ random variable (vector) $X$ is a function $X:\Omega\to{\mathit{I R}}$ $\boldsymbol{X}:\Omega\rightarrow\boldsymbol{\mathit{R}}^{k}$ ) such that $X^{-1}(B)=\{\omega\in\Omega:X(\omega)\in B\}\in{\mathcal{F}}$ for all Borel sets $B\in B(I R)(B\in B(I R^{k}))$  

In particular we have for a random variable $X$ that $\{\omega\in\Omega:X(\omega)\leq x\}\in{\mathcal{F}}$ for all $x\in\mathcal{M}$ Hence we can define the distribution function $F_{X}$ of $X$ by  

$$
F_{X}(x):=D P{\bigl(}\{\omega:X(\omega)\leq x\}{\bigr)}.
$$  

The smallest $\sigma$ -algebra containing all the sets $\{\omega:X(\omega)\leq x\}$ for all real $x$ (equivalently, $\{X<x\}$ $\{X\geq x\}$ $\{X>x\}$ is called the. $\sigma$ -algebra generated by. $X$ , written $\sigma(X)$ . Thus,  

The events in the $\sigma$ -algebra generated by $X$ are the events $\{\omega:X(\omega)\in B\}$ , where $B$ runs through the Borel $\sigma$ -algebra on the line. When the (random) value $X(\omega)$ is known, we know which of these events have happened.  

# Interpretation.  

Think of. $\sigma(X)$ as representing what we know when we know $X$ , or in other words the information. contained in $X$ (or in knowledge of. $X$ ). This is reflected in the following result, due to J.L. Doob, which we quote:.  

$$
\sigma(X)\subseteq\sigma(Y)\qquad{\mathrm{if~and~only~if}}\qquadX=g(Y)
$$  

for some measurable function. $g$ . For, knowing $Y$ means we know $X:=g(Y)$ - but not vice versa,. unless the function $g$ is one-to-one (injective), when the inverse function $g^{-1}$ exists, and we can go back via. $Y=g^{-1}(X)$  

# Note.  

An extended discussion of generated $\sigma$ -algebras in the finite case is given in Dothan's book Dothan (1990), Chapter 3. Although technically avoidable, this is useful preparation for the general case, needed for continuous time.  

A measure (\$2.1) determines an integral (\$2.2). A probability measure. $\mathcal{W}$ , being a special kind of measure (a measure of total mass one) determines a special kind of integral, called an expectation.  

Definition B.3.3. The expectation $\mathit{I E}$ of a random variable $X$ on $(\Omega,{\mathcal{F}},I P)$ is defined by  

$$
E X:=\int X d P,\quad o r\quad\int X(\omega)d P(\omega).
$$  

The expectation - also called the mean - describes the location of a distribution (and so is called a location parameter). Information about the scale of a distribution (the corresponding scale parameter) is obtained by considering the variance  

$$
W a r(X):=I E\left[(X-I E(X))^{2}\right]=I E\left(X^{2}\right)-(I E X)^{2}.
$$  

If $X$ is real-valued, say, with distribution function $F$ , recall that $\mathbb{E}X$ is defined in your first. course on probability by.  

$$
H E X:=\int x f(x)d x\mathrm{if}X\mathrm{has}\mathrm{adensity}f
$$  

or if $X$ is discrete, taking values $x_{n}(n=1,2,...)$ with probability function $f(x_{n})(\geq0)$ $\textstyle(\sum_{x_{n}}f(x_{n})=$ 1),  

$$
E X:=\sum x_{n}f(x_{n}).
$$  

These two formulae are the special cases (for the density and discrete cases) of the general formula  

$$
E X:=\int_{-\infty}^{\infty}x d F(x)
$$  

where the integral on the right is a Lebesgue-Stieltjes integral. This in turn agrees with the definition above, since if. $F$ is the distribution function of. $X$  

$$
\int_{\Omega}X d D P=\int_{-\infty}^{\infty}x d F(x)\stackrel{}{_{\Omega}}
$$  

follows by the change of variable formula for the measure-theoretic integral, on applying the map $X:\Omega\to{\mathit{I R}}$ (we quote this: see any book on measure theory, e.g. Dudley (1989)).  

Clearly the expectation operator. $\mathit{\Pi}_{\mathit{I B}}$ is linear. It even becomes multiplicative if we consider independent random variables..  

Definition B.3.4. Random variables $X_{1},\ldots,X_{n}$ are independent if whenever $A_{i}\in B$ for $i=$ $1,\ldots n$ we have  

$$
I P\left(\bigcap_{i=1}^{n}\{X_{i}\in A_{i}\}\right)=\prod_{i=1}^{n}I P(\{X_{i}\in A_{i}\}).
$$  

Using Lemma B.1.1 we can give a more tractable condition for independence:  

Lemma B.3.1. In order for. $X_{1},\ldots,X_{n}$ to be independent it is necessary and sufficient that for all $x_{1},...x_{n}\in(-\infty,\infty]$  

$$
I P\left(\bigcap_{i=1}^{n}\{X_{i}\leq x_{i}\}\right)=\prod_{i=1}^{n}I P(\{X_{i}\leq x_{i}\}).
$$  

Now using the usual measure-theoretic steps (going from simple to integrable functions) it is easy to show:  

Theorem B.3.1 (Multiplication Theorem). If $X_{1},\ldots,X_{n}$ are independent and. $\left|\mathbb{E}\left|X_{i}\right|\right.<$ $\infty$ $i=1,\ldots,n$ , then  

$$
E\left(\prod_{i=1}^{n}X_{i}\right)=\prod_{i=1}^{n}{\cal{R}}(X_{i}).
$$  

We now review the distributions we will mainly use in our models of financial markets.  

# Examples.  

(i) Bernoulli distribution. Recall our arbitrage-pricing example from $\S$ 1.4. There we were given a. stock with price. $S(0)$ at time $t=0$ . We assumed that after a period of time $\Delta t$ the stock price. could have only one of two values, either $S(\Delta t)=e^{u}S(0)$ with probability $p$ or $S(\Delta t)=e^{d}S(0)$ with probability $1-p$ $u,d\in\pi)$ . Let $R(\Delta t)=r(1)$ be a random variable modelling the logarithm of the stock return over the period. $[0,\Delta t]$ ; then  

$$
P(r(1)=u)=p\mathrm{and}P(r(1)=d)=1-p.
$$  

We say that $r(1)$ is distributed according to a Bernoulli distribution. Clearly ${\cal I E}(r(1))=u p+$ $d(1-p)$ and $\begin{array}{r}{V a r(r(1))=u^{2}p+d^{2}(1-p)-(E X)^{2}.}\end{array}$  

The standard case of a Bernoulli distribution is given by choosing $u=1,d=0$ (which is not a very useful choice in financial modelling)..  

(ii) Binomial distribution. If we consider the logarithm of the stock return over $n$ periods (of equal length), say over $[0,T]$ , then subdividing into the periods $1,\ldots,n$ we have  

$$
\begin{array}{r c l}{{R(T)}}&{{=}}&{{\log\left[\displaystyle\frac{S(T)}{S(0)}\right]=\log\left[\displaystyle\frac{S(T)}{S(T-\Delta t)}\cdots\displaystyle\frac{S(\Delta t)}{S(0)}\right]}}\ {{}}&{{=}}&{{\log\left[\displaystyle\frac{S(T)}{S(T-\Delta t)}\right]+\ldots+\log\left[\displaystyle\frac{S(\Delta t)}{S(0)}\right]=r(n)+\ldots+r(1).}}\end{array}
$$  

Assuming that $r(i)$ $i=1,\ldots,n$ are independent and each. $r(i)$ is Bernoulli distributed as above. we have that $\begin{array}{r}{R(T)=\sum_{i=1}^{n}r(i)}\end{array}$ is binomially distributed. Linearity of the expectation operator and independence yield $\begin{array}{r}{E(R(T))=\sum_{i=1}^{n}E(r(i))}\end{array}$ and $\begin{array}{r}{\mathbb{V}a r(R(T))=\sum_{i=1}^{n}\mathbb{V}a r(r(i))}\end{array}$  

Again for the standard case one would use $u=1,d=0$ . The shorthand notation for a binomial random variable $X$ is then $X\sim B(n,p)$ and we can compute  

$$
T P(X=k)={\binom{n}{k}}p^{k}(1-p)^{(n-k)},\quad E(X)=n p,\quad W a r(X)=n p(1-p).
$$  

(iii) Normal distribution. As we will show in the sequel the limit of a sequence of appropriate normalised binomial distributions is the (standard) normal distribution. We say a random variable $X$ is normally distributed with parameters $\mu,\sigma^{2}$ , in short $X\sim N(\mu,\sigma^{2})$ , if $X$ has density function  

$$
f_{\mu,\sigma^{2}}(x)={\frac{1}{\sqrt{2\pi}\sigma}}\exp{\left\{-{\frac{1}{2}}\left({\frac{x-\mu}{\sigma}}\right)^{2}\right\}}.
$$  

One can show that. ${\mathbb{E}}(X)=\mu$ and $W a r(X)=\sigma^{2}$ , and thus a normally distributed random variable.   
is fully described by knowledge of its mean and variance.  

Returning to the above example, one of the key results of this text will be that the limiting. model of a sequence of financial markets with one-period asset returns modelled by a Bernoulli distribution is a model where the distribution of the logarithms of instantaneous asset returns is normal. That means $S(t+\Delta t)/S(t)$ is lognormally distributed (i.e.. $\log(S(t+\Delta t)/S(t))$ is normally distributed). Although rejected by many empirical studies (see Eberlein and Keller (1995) for a.  

recent overview), such a model seems to be the standard in use among financial practitioners (and. we will call it the standard model in the following). The main arguments against using normally distributed random variables for modelling log-returns (i.e. log-normal distributions for returns) are asymmetry and (semi-) heavy tails. We know that distributions of financial asset returns are generally rather close to being symmetric around zero, but there is a definite tendency towards asymmetry. This may be explained by the fact that the markets react differently to positive as opposed to negative information (see Shephard (1996) s1.3.4). Since the normal distribution is. symmetric it is not possible to incorporate this empirical fact in the standard model. Financial. time series also suggest modelling by probability distributions whose densities behave for $x\rightarrow\pm\infty$ as  

$$
|x|^{\rho}\exp\{-\sigma|x|\}
$$  

with $\rho\in I R,\sigma>0$ . This means that we should replace the normal distribution with a distribution with heavier tails. Such a model like this would exhibit higher probabilities of extreme events and the passage from ordinary observations (around the mean) to extreme observations would be more sudden. Among suggested (classes of) distributions to be used to address these facts is the class of hyperbolic distributions (see Eberlein and Keller (1995) and $\S2.12$ below), and more general distributions of normal inverse Gaussian type (see Barndorff-Nielsen (1998), Rydberg (1996), Rydberg (1997)) appear to be very promising.  

(iv) Poisson distribution. Sometimes we want to incorporate in our model of financial markets. the possibility of sudden jumps. Using the standard model we model the asset price process by a. continuous stochastic process, so we need an additional process generating the jumps. To do this we use point processes in general and the Poisson process in particular. For a Poisson process the. probability of a jump (and no jump respectively) during a small interval. $\Delta t$ are approximately  

$$
P(\nu(1)=1)\approx\lambda\Delta t\mathrm{and}P(\nu(1)=0)\approx1-\lambda\Delta\iota
$$  

where $\lambda$ is a positive constant called the rate or intensity. Modelling small intervals in such a way we get for the number of jumps $N(T)=\nu(1)+...+\nu(n)$ in the interval $[0,T]$ the probability function  

$$
\quad\:P(N(T)=k)={\frac{e^{-\lambda T}(\lambda T)^{k}}{k!}},\quad k=0,1,....
$$  

and we say the process. $N(T)$ has a Poisson distribution with parameter $\lambda T$ .We can show $\textstyle E(N(T))=\lambda T$ and $V a r(N(T))=\lambda T$  

# Glossary.  

Table B.1 summarises the two parallel languages, measure-theoretic and probabilistic, which we have established.  

Table B.1: Measure-theoretic and probabilistic languages   


<html><body><table><tr><td>Measure</td><td>Probability</td></tr><tr><td>Integral Measurableset Measurablefunction Almost-everywhere (a.e.)</td><td>Expectation Event Random variable Almost-surely (a.s.)</td></tr></table></body></html>  

# B.4 Equivalent Measures and Radon-Nikodym Derivatives  

Given two measures $\mathcal{W}$ and $\mathbb{Q}$ defined on the same. $\sigma$ -algebra $\mathcal{F}$ , we say that $\mathcal{W}$ is absolutely continuous with respect to $\mathbb{Q}$ , written  

$$
\textstyle{\mathcal{P}}<<{\mathcal{Q}}
$$  

if $\textstyle{\cal{P}}(A)=0$ , whenever $Q(A)=0,A\in{\mathcal{F}}$ . We quote from measure theory the vitally important Radon-Nikodym theorem:  

Theorem B.4.1 (Radon-Nikodym). $\mathbb{P}<<\mathbb{Q}$ iff there exists a $(\mathcal{F}-)$ measurable function $f$ such that  

$$
\displaystyle I P(A)=\int_{A}f d\pmb{Q}~\forall A\in\mathcal{F}.
$$  

(Note that since the integral of anything over a null set is zero, any $\mathcal{l}^{p}$ so representable is certainly absolutely continuous with respect to. $\mathbb{Q}$ the point is that the converse holds.).  

Since $\textstyle P(A)=\int_{A}d P$ , this says that. $\textstyle\int_{A}d{\cal D}=\int_{A}f d Q$ for all $A\in{\mathcal{F}}$ . By analogy with the chain rule of ordinary calculus, we write $d\varmathbb{P}/d\protect\mathbb{Q}$ for $f$ ; then.  

$$
\intop d\boldsymbol{I}P=\intop_{A}\frac{d\boldsymbol{I}P}{d\boldsymbol{Q}}d\boldsymbol{Q}\quad\forall A\in\mathcal{F}.
$$  

Symbolically,  

$$
\mathrm{if}\quad l l^{\vphantom{l l l}}<<Q,\quad d l P=\frac{d I P}{d Q}d Q.
$$  

The measurable function (random variable) $d\varPsi/d\protect\mathbb{Q}$ is called the Radon-Nikodym derivative (RNderivative) of $\mathcal{W}$ with respect to $\mathbb{Q}$  

If $\mathbb{\Gamma}\times<<\mathbb{Q}$ and also $\mathbb{Q}<<\mathbb{P}$ , we call $\mathcal{W}$ and $\mathbb{Q}$ equivalent measures, written $I P\sim\mathbb{Q}$ . Then $d\varmathbb{P}/d\protect\mathbb{Q}$ and $d\mathscr{Q}/d I P$ both exist, and.  

$$
\frac{d D}{d Q}=1/\frac{d Q}{d D}.
$$  

For ${\cal P}\sim\mathbb{Q}$ $\textstyle{\cal{P}}(A)=0$ iff $\textstyle{\mathcal{Q}}(A)=0$ .. $\mathcal{W}$ and $\mathbb{Q}$ have the same null sets. Taking negations:. $\mathcal{P}\sim\mathcal{Q}$ iff $\mathcal{P},\mathcal{Q}$ have the same sets of positive measure. Taking complements:. $I P\sim\mathbb{Q}$ iff $\mathcal{l}^{P,Q}$ have the same sets of probability one (the same a.s. sets). Thus the following are equivalent:  

P \~ Q iff $\mathcal{P},\mathcal{Q}$ have the same null sets, iff $\mathbb{\Gamma}\left(\mathcal{P},\mathbb{Q}\right)$ have the same a.s. sets, iff $\mathcal{P},\mathcal{Q}$ have the same sets of positive measure.  

Far from being an abstract theoretical result, the Radon-Nikodym theorem is of key practical importance, in two ways:.  

(a) It is the key to the concept of conditioning (\$2.5, 32.6 below), which is of central importance. throughout, (b) The concept of equivalent measures is central to the key idea of mathematical finance, riskneutrality, and hence to its main results, the Black-Scholes formula, fundamental theorem of asset pricing, etc. The key to all this is that prices should be the discounted expected values under an equivalent martingale measure. Thus equivalent measures, and the operation of change of measure, are of central economic and financial importance. We shall return to this later in connection with the main mathematical result on change of measure, Girsanov's theorem (see 35.7)..  

# B.5 Conditional expectation  

For basic events define  

$$
P(A|B):=P(A\cap B)/P(B){\mathrm{if}}P(B)>0.
$$  

From this definition, we get the multiplication rule  

$$
P(A\cap B)=P(A|B)P(B).
$$  

Using the partition equation $\begin{array}{r}{D P(B)=\sum_{n}D(B|A_{n})D P(A_{n})}\end{array}$ with ( $A_{n}$ ) a finite or countable partition of $\Omega$ , we get the Bayes rule.  

$$
P(A_{i}|B)={\frac{I P(A_{i})I P(B|A_{i})}{\sum_{j}I P(A_{j})I P(B|A_{j})}}.
$$  

We can always write. $\begin{array}{r}{D(A)=D E(\mathbf{1}_{A})}\end{array}$ with $\mathbf{1}_{A}(\omega)=1$ if $\omega\in A$ and $\mathbf{1}_{A}(\omega)=0$ otherwise. Then. the above can be written  

$$
|E(\mathbf{1}_{A}|B)={\frac{l E(\mathbf{1}_{A}\mathbf{1}_{B})}{l P(B)}}
$$  

This suggest defining, for suitable random variables $X$ , the $\mathcal{W}$ average of $X$ over $B$ as  

$$
B({\boldsymbol{X}}|{\boldsymbol{B}})={\frac{{\cal{L}}({\boldsymbol{X}}\mathbf{1}_{B})}{{\cal{P}}({\boldsymbol{B}})}}.
$$  

Consider now discrete random variables $X$ and $Y$ .Assume $X$ takes values $x_{1},\ldots,x_{m}$ with   
probabilities $f_{1}(x_{i})>0$ $Y$ takes values with probabilities $f_{2}(y_{j})>0$ , while the vector $y_{1},\ldots,y_{n}$   
$(X,Y)$ takes values $(x_{i},y_{j})$ with probabilities $f(x_{i},y_{j})>0$ . Then the marginal distributions   
are  

$$
f_{1}(x_{i})=\sum_{j=1}^{n}f(x_{i},y_{j})\quad{\mathrm{~and~}}\quad f_{2}(y_{j})=\sum_{i=1}^{m}f(x_{i},y_{j}).
$$  

We can use the standard definition above for the events $\{Y=y_{j}\}$ and $\{X=x_{i}\}$ to get  

$$
P(Y=y_{j}|X=x_{i})=\frac{I P(X=x_{i},Y=y_{j})}{I P(X=x_{i})}=\frac{f(x_{i},y_{j})}{f_{1}(x_{i})}.
$$  

Thus conditional on $X=x_{i}$ (given the information $X=x_{i}$ ), $Y$ takes on the values $y_{1},\ldots,y_{n}$ with (conditional) probabilities  

$$
f_{Y|X}(y_{j}|x_{i})=\frac{f(x_{i},y_{j})}{f_{1}(x_{i})}.
$$  

So we can compute its expectation as usual:  

$$
E(Y|X=x_{i})=\sum_{j}y_{j}f_{Y|X}{\big(}y_{j}|x_{i}{\big)}={\frac{\sum_{j}y_{j}f(x_{i},y_{j})}{f_{1}(x_{i})}}.
$$  

Now define the random variable $Z=I E(Y|X)$ , the conditional expectation of $Y$ given $X$ , as follows:  

Observe that in this case $Z$ is given by a 'nice' function of $X$ . However, a more abstract property also holds true. Since $Z$ is constant on the the sets $\{X=x_{i}\}$ it is $\sigma(X)$ -measurable (these sets generate the $\sigma$ -algebra). Furthermore  

$$
\begin{array}{r c l}{{\displaystyle\int_{\{X=x_{i}\}}Z d I P}}&{{=}}&{{\displaystyle z_{i}I P(X=x_{i})=\sum_{j}y_{j}f_{Y|X}(y_{j}|x_{i})I P(X=x_{i})}}\ {{}}&{{}}&{{}}\ {{}}&{{=}}&{{\displaystyle\sum_{j}y_{j}P(Y=y_{j};X=x_{i})=\sum_{\{X=x_{i}\}}Y d I P.}}\end{array}
$$  

Since the $\{X=x_{i}\}$ generate $\sigma(X)$ , this implies  

$$
\int_{G}Z d I P=\int_{G}Y d I P\quad\forall G\in{\sigma}(X).
$$  

Density case. If the random vector $(X,Y)$ has density $f(x,y)$ , then $X$ has (marginal) density $\begin{array}{r}{f_{1}(x):=\int_{-\infty}^{\infty}f(x,y)d y}\end{array}$ $Y$ has (marginal) density $\begin{array}{r}{f_{2}(y):=\int_{-\infty}^{\infty}f(x,y)d x}\end{array}$ . The conditional density of $Y$ given $X=x$ is:  

$$
f_{Y|X}(y|x):=\frac{f(x,y)}{f_{1}(x)}.
$$  

Its expectation is  

So we define  

$$
E(Y|X=x)=\int_{-\infty}^{\infty}y f_{Y|X}(y|x)d y=\frac{\int_{-\infty}^{\infty}y f(x,y)d y}{f_{1}(x)}.
$$  

$$
c(x)={\left\{\begin{array}{l l}{H E(Y|X=x)}&{\quad{\mathrm{if}}f_{1}(x)>0}\ {0}&{\quad{\mathrm{if}}f_{1}(x)=0,}\end{array}\right.}
$$  

and call $c(X)$ the conditional expectation of $Y$ given $X$ , denoted by ${\cal{H}}(Y|X)$ .Observe that on sets with probability zero (i.e $\{\omega:X(\omega)=x;f_{1}(x)=0\}$ ) the choice of $c(x)$ is arbitrary, hence ${\cal{H}}(Y|X)$ is only defined up to a set of probability zero; we speak of different versions in such cases. With this definition we again find  

$$
\int_{G}c(X)d I P=\int_{G}Y d I P\quad\forall G\in\sigma(X).
$$  

Indeed, for sets $G$ with $G=\{\omega:X(\omega)\in B\}$ with $B$ a Borel set, we find by Fubini's theorem  

$$
\begin{array}{r c l}{{\displaystyle\int_{G}c(X)d P}}&{{=}}&{{\displaystyle\int_{-\infty}^{\infty}{\bf1}_{B}(x)c(x)f_{1}(x)d x}}\ {{}}&{{}}&{{\displaystyle-\infty}}\ {{}}&{{=}}&{{\displaystyle\int_{-\infty}^{\infty}{\bf1}_{B}(x)f_{1}(x)\displaystyle\int_{-\infty}^{\infty}y f_{Y|X}(y|x)d y d x}}\ {{}}&{{}}&{{\displaystyle-\infty}}\ {{}}&{{=}}&{{\displaystyle\int_{-\infty-\infty}^{\infty}\int_{1}^{\infty}{\bf1}_{B}(x)y f(x,y)d y d x=\displaystyle\int_{G}Y d P.}}\end{array}
$$  

Now these sets. $G$ generate $\sigma(X)$ and by a standard technique (the $\pi$ -systems lemma, see Williams. (2001), s2.3) the claim is true for all $G\in\sigma(X)$  

# Example. Bivariate Normal Distribution,  

$N(\mu_{1},\mu_{2},\sigma_{1}^{2},\sigma_{2}^{2},\rho)$  

$$
I E(Y|X=x)=\mu_{2}+\rho\frac{\sigma_{2}}{\sigma_{1}}(x-\mu_{1}),
$$  

the familiar regression line of statistics (linear model) - see Exercise 2.6.  

General case. Here, we follow Kolmogorov's construction using the Radon-Nikodym theorem. Suppose that $\mathcal{G}$ is a sub- $\sigma$ -algebra of $\mathcal{F}$ $\mathcal{G}\subset\mathcal{F}$ .If $Y$ is a non-negative random variable with $I E Y<\infty$ , then  

$$
\pmb{Q}(G):=\int_{G}Y d D\qquad(G\in{\mathcal{G}})
$$  

is non-negative, $\sigma$ -additive - because  

$$
\int_{G}Y d I P=\sum_{n}\int_{G_{n}}Y d I P
$$  

if $G=\cup_{n}G_{n}$ $G_{n}$ disjoint - and defined on the $\sigma$ -algebra $\mathcal{G}$ , so it is a measure on $\mathcal{G}$  

If ${\cal{P}}(G)=0$ , then $\mathbb{Q}(G)=0$ also (the integral of anything over a null set is zero), so $\mathbb{Q}<<\mathcal{N}$ By the Radon-Nikodym theorem, there exists a Radon-Nikodym derivative of $\mathbb{Q}$ with respect. to $\mathcal{W}$ on $\mathcal{G}$ , which is $\mathcal{G}$ -measurable. Following Kolmogorov, we call this Radon-Nikodym derivative the conditional expectation of $Y$ given (or conditional on) ${\mathcal{G}},{\mathcal{L}}(Y|{\mathcal{G}})$ , whose existence we now have established. For $Y$ that changes sign, split into $Y=Y^{+}-Y^{-}$ , and define. $\mathcal{\mathbb{E}}(Y|\mathcal{G}):=$ $\begin{array}{r}{\begin{array}{r l}{\lefteqn{I E(Y^{+}|\mathcal{G})-I E(Y^{-}|\mathcal{G})}}\end{array}}\end{array}$ . We summarize:  

Definition B.5.1. Let $Y$ be a random variable with $\textstyle\mathbb{E}(|Y|)<\infty$ and $\mathcal{G}$ be a sub- $\cdot\sigma$ -algebra of $\mathcal{F}$ We call a random variable $Z$ a version of the conditional expectation ${\mathcal{L}}(Y|{\mathcal{G}})$ of $Y$ given $\mathcal{G}$ , and write $Z=I E(Y|{\mathcal{G}})$ , a.s., if  

(i) $Z$ is $\mathcal{G}$ -measurable; (ii) $\textstyle\mathbb{E}(|Z|)<\infty$ (iii) for every set $G$ in $\mathcal{G}$ , we have  

$$
\int_{G}Y d I P=\int_{G}Z d I P\quad\quad\forall G\in{\mathcal{G}}.
$$  

Notation. Suppose ${\mathcal{G}}=\sigma(X_{1},\ldots,X_{n})$ . Then  

$$
E(Y|{\mathcal{G}})=E\left(Y|\sigma(X_{1},\ldots,X_{n})\right)=:E(Y|X_{1},\ldots,X_{n}),
$$  

and one can compare the general case with the motivating examples above.  

To see the intuition behind conditional expectation, consider the following situation. Assume an experiment has been performed, i.e.. $\omega\in\Omega$ has been realized. However, the only information we. have is the set of values $X(\omega)$ for every $\mathcal{G}$ -measurable random variable $X$ . Then $Z(\omega)=I E(Y|\mathcal{G})(\omega)$ is the expected value of $Y(\omega)$ given this information.  

We used the traditional approach to define conditional expectation via the Radon-Nikodym theorem. Alternatively, one can use Hilbert space projection theory (Neveu (1975) and Jacod and Protter (2000) follow this route). Indeed, for $Y\in{\mathcal{L}}^{2}(\Omega,{\mathcal{F}},I P)$ one can show that the conditional expectation $Z=I E(Y|{\mathcal{G}})$ is the least-squares-best. $\mathcal{G}$ measurable predictor of. $Y$ : amongst all $\mathcal{G}$ -measurable random variables it minimises the quadratic distance, i.e.  

$$
E[(Y-{\cal E}(Y|{\mathcal{G}}))^{2}]=\operatorname*{min}\{{\cal E}[(Y-X)^{2}]:X\quad{\mathcal{G}}-\mathrm{measurable}\}.
$$  

# Note.  

1. To check that something is a conditional expectation: we have to check that it integrates the right way over the right sets (i.e., as in (B.4))..   
2. From (B.4): if two things integrate the same way over all sets $B\in{\mathcal{G}}$ , they have the same. conditional expectation given $\mathcal{G}$   
3. For notational convenience, we shall pass between. ${\mathcal{L}}(Y|{\mathcal{G}})$ and $\mathcal{L}_{\mathcal{G}}Y$ at will.   
4. The conditional expectation thus defined coincides with any we may have already encountered - in regression or multivariate analysis, for example. However, this may not be immediately obvious. The conditional expectation defined above - via. $\sigma$ -algebras and the Radon-Nikodym theorem - is. rightly called by Williams ((Williams 1991), p.84) 'the central definition of modern probability'. It may take a little getting used to. As with all important but non-obvious definitions, it proves its worth in action: see. $\S2.6$ below for properties of conditional expectations, and Chapter 3 for its use in studying stochastic processes, particularly martingales (which are defined in terms of conditional expectations).  

We now discuss the fundamental properties of conditional expectation. From the definition linearity of conditional expectation follows from the linearity of the integral. Further properties are given by  

Proposition B.5.1. $\mathcal{G}=\{\emptyset,\Omega\},\quad E(Y|\{\emptyset,\Omega\})=E Y.$  

2. If $\mathcal{G}=\mathcal{F},\quad\mathit{I E}(Y|\mathcal{F})=Y\quad\mathit{I P}-a.s..$  

3. If $Y$ is $\mathcal{G}$ -measurable, $\begin{array}{r}{I E(Y|\mathcal{G})=Y\quad I P-a.s.}\end{array}$  

4. Positivity. If $X\geq0$ , then $I{\cal E}(X|\mathcal{G})\geq0$ $\it{I P}-\it{a.s.}$  

5. Taking out what is known. If $Y$ is $\mathcal{G}$ -measurable and bounded,. $L(Y Z|\mathcal{G})=Y B E(Z|\mathcal{G})$ $\mathcal{P}-$ a.s..  

6. Tower property. If $\mathcal{G}_{0}\subset\mathcal{G},\mathbb{E}[H\mathit{F}(Y|\mathcal{G})|\mathcal{G}_{0}]=I E[Y|\mathcal{G}_{0}]\quad a.$ S..  

7. Conditional mean formula. $E[B E(Y|\mathcal{G})]=B Y\quad D P-a.s$  

8. Role of independence. If $Y$ is independent of. $\mathcal{G}$ $\begin{array}{r}{\mathbb{E}(Y|\mathcal{G})=\mathbb{E}Y}\end{array}$ a.s.  

9. Conditional Jensen formula. If $c:\mathbb{R}\to\mathbb{R}$ is convex, and. $L|c(X)|<\infty$ , then  

$$
L(c(X)|{\mathcal{G}})\geq c\left(L(X|{\mathcal{G}})\right).
$$  

Proof. 1. Here $\mathcal{G}=\{\emptyset,\Omega\}$ is the smallest possible $\sigma$ -algebra (any $\sigma$ -algebra of subsets of $\Omega$ contains $\varnothing$ and $\Omega$ ), and represents knowing nothing'. We have to check (B.4) for $G=\emptyset$ and $G=\Omega$ . For $G=\emptyset$ both sides are zero; for $G=\Omega$ both sides are $\mathcal{B}\mathcal{Y}$  

2. Here $\mathcal{G}=\mathcal{F}$ is the largest possible $\sigma$ -algebra, and represents knowing everything'. We have. to check (B.4) for all sets $G\in{\mathcal{F}}$ . The only integrand that integrates like. $Y$ over $a{\boldsymbol{l}}{\boldsymbol{l}}$ sets is $Y$ itself, or a function agreeing with. $Y$ except on a set of measure zero.. Note. When we condition on. $\mathcal{F}$ (knowing everything'), we know. $Y$ (because we know everything).. There is thus no uncertainty left in $Y$ to average out, so taking the conditional expectation (averaging out remaining randomness) has no effect, and leaves $Y$ unaltered.  

3. Recall that $Y$ is always. $\mathcal{F}$ -measurable (this is the definition of. $Y$ being a random variable).. For $\mathcal{G}\subset\mathcal{F}$ $Y$ may not be. $\mathcal{G}$ -measurable, but if it is, the proof above applies with $\mathcal{G}$ in place of $\mathcal{F}$ Note. To say that $Y$ is $\mathcal{G}$ -measurable is to say that. $Y$ is known given $\mathcal{G}$ that is, when we are. conditioning on $\mathcal{G}$ . Then $Y$ is no longer random (being known when $\mathcal{G}$ is given), and so counts as. a constant when the conditioning is performed.  

4. Let $Z$ be a version of ${\cal{E}}(X|\mathcal{G})$ . If $D(Z<0)>0$ , then for some $n$ , the set  

$$
G:=\{Z<-n^{-1}\}\in\mathcal{G}\quad\mathrm{and}\quad P(\{Z<-n^{-1}\})>0.
$$  

Thus  

$$
0\leq B(X\mathbf{1}_{G})=B(Z\mathbf{1}_{G})<-n^{-1}B P(G)<0,
$$  

which contradicts the positivity of $X$  

5. First, consider the case when $Y$ is discrete. Then $Y$ can be written as  

$$
Y=\sum_{n=1}^{N}b_{n}\mathbf{1}_{B_{n}},
$$  

for constants $b_{n}$ and events $B_{n}\in{\mathcal{G}}$ . Then for any $B\in{\mathcal{G}}$ $B\cap B_{n}\in{\mathcal G}$ also (as $\mathcal{G}$ is a $\sigma$ -algebra), and using linearity and (B.4):  

$$
\begin{array}{r c l}{\displaystyle\int Y E(Z|\mathcal{G})d P}&{=}&{\displaystyle\int\left(\sum_{n=1}^{N}b_{n}\mathbf{1}_{B_{n}}\right)E(Z|\mathcal{G})d P=\sum_{n=1}^{N}b_{n}\int\mathbf{\delta}E(Z|\mathcal{G})d P}\ &{=}&{\displaystyle\sum_{n=1}^{N}b_{n}\int Z d P=\int\sum_{B}^{N}b_{n}\mathbf{1}_{B_{n}}Z d P}\ &{=}&{\displaystyle\int Y Z d P.}\end{array}
$$  

Since this holds for all $B\in{\mathcal{G}}$ , the result holds by $(B.4)$  

For the general case, we approximate to a general random variable. $Y$ by a sequence of discrete random variables $Y_{n}$ , for each of which the result holds as just proved. We omit details of the. proof here, which involves the standard approximation steps based on the monotone convergence theorem from measure theory (see e.g. (Williams 1991), p.90, proof of (j)). We are thus left to. show the $\smash{\ensuremath{\mathbb{{L}}}(|Z Y|)<\infty}$ , which follows from the assumption that $Y$ is bounded and $Z\in{\mathcal{L}}^{1}$  

6. $I E_{\mathcal{G}_{0}}\underline{{\mathcal{K}}}_{\mathcal{G}}Y$ is $\mathscr{G}_{0}$ -measurable, and for $C\in\mathcal{G}_{0}\subset\mathcal{G}$ , using the definition of $\mathcal{L}_{\mathcal{G}_{0}},\mathcal{B}_{\mathcal{G}}$  

$$
\intop_{C}H_{\mathcal{G}_{0}}[L E_{\mathcal{G}}Y]d P=\intop_{C}H_{\mathcal{G}}Y d P=\intop_{C}Y d P.
$$  

So $\mathit{l}{\mathit{E}_{\mathcal{G}_{0}}}[\mathit{l}\mathit{E_{\mathcal{G}}Y}]$ satisfies the defining relation for $\mathcal{B}g_{0}Y$ . Being also $\mathcal{G}_{0}$ -measurable, it is. $\mathcal{l}E_{\mathcal{G}_{0}}Y$ (a.s.). We also have:.  

$6^{\circ}$ . If $\mathcal{G}_{0}\subset\mathcal{G}$ $\begin{array}{r}{E[E(Y|\mathcal{G}_{0})|\mathcal{G}]=E[Y|\mathcal{G}_{0}]}\end{array}$ a.s..  

Proof. ${\cal{H}}[Y|\mathcal{G}_{0}]$ is $\mathcal{G}_{0}$ -measurable, so $\mathcal{G}$ -measurable as $\mathcal{G}_{0}\subset\mathcal{G}$ , so $E[.|\mathcal{G}]$ has no effect on it, by 3.  

# Note.  

$_6$ $6^{\circ}$ are the two forms of the iterated conditional expectations property. When conditioning on two $\sigma$ -algebras, one larger (finer), one smaller (coarser), the coarser rubs out the effect of the finer, either way round. This may be thought of as the coarse-averaging property: we shall use this term interchangeably with the iterated conditional expectations property (Williams (1991) uses the term tower property).  

7. Take $\mathcal{G}_{0}=\{\emptyset,\Omega\}$ in 6. and use 1.   
8. If $Y$ is independent of $\mathcal{G}$ $Y$ is independent of ${\bf1}_{B}$ for every $B\in{\mathcal{G}}$ . So by (B.4) and linearity.  

$$
\begin{array}{r c l}{{\displaystyle\int E(Y|\mathcal{G})d I P}}&{{=}}&{{\displaystyle\int Y d I P=\int\mathbf{1}_{B}Y d I P}}\ {{\displaystyle B}}&{{=}}&{{\displaystyle{\cal E}(\mathbf{1}_{B}Y)={\cal E}(\mathbf{1}_{B}){\cal E}(Y)=\int E Y d I P,}}\end{array}
$$  

using the multiplication theorem for independent random variables. Since this holds for all $B\in{\mathcal{G}}$ the result follows by $(B.4)$  

9. Recall (see e.g. Williams (1991), \$6.6a, 39.7h, $\mathrm{\S9.8h)}$ , that for every convex function there. exists a countable sequence $(a_{n},b_{n}),$ of points in. $\mathit{\Pi}\overline{{\mathit{{R}}^{2}}}$ such that  

$$
c(x)=\operatorname*{sup}_{n}(a_{n}x+b_{n}),x\in I R.
$$  

For each fixed $n$ we use 4. to see from $c(X)\geq a_{n}X+b_{n}$ that  

$$
\begin{array}{r}{I E[c(X)|\mathcal G]\ge a_{n}I E(X|\mathcal G)+b_{n}.}\end{array}
$$  

So,  

$$
E[c(X)|{\mathcal{G}}]\geq\operatorname*{sup}_{n}\left(a_{n}E(X|{\mathcal{G}})+b_{n}\right)=c\left(L E(X|{\mathcal{G}})\right).
$$  

Remark B.5.1. If in $6,6^{\prime}$ we take $\mathcal{G}=\mathcal{G}_{0}$ , we obtain:.  

$$
E[E(X|\mathcal{G})|\mathcal{G}]=B(X|\mathcal{G}).
$$  

Thus the map $X\to\mathit{I E}(X|\mathcal{G})$ is idempotent: applying it twice is the same as applying it once..   
Hence we may identify the conditional expectation operator as a projection.  

# B.6 Modes of Convergence  

So far, we have dealt with one probability measure - or its expectation operator - at a time. We shall, however, have many occasions to consider a whole sequence of them, converging (in a suitable sense) to some limiting probability measure. Such situations arise, for example, whenever we approximate a financial model in continuous time (such as the continuous-time Black-Scholes model of 6.2) by a sequence of models in discrete time (such as the discrete-time Black-Scholes model of 4.6).  

In the stochastic-process setting - such as the passage from discrete to continuous Black-Scholes models mentioned above - we need concepts beyond those we have to hand, which we develop later. We confine ourselves here to setting out what we need to discuss convergence of random variables, in the various senses that are useful.  

The first idea that occurs to one is to use the ordinary convergence concept in this new setting, of random variables: then if $X_{n}$ $X$ are random variables,  

$$
\quad X_{n}\to X\quad(n\to\infty)
$$  

would be taken literally - as if the $X_{n}$ $X$ were non-random. For instance, if $X_{n}$ is the observed frequency of heads in a long series of. $n$ independent tosses of a fair coin, $X=1/2$ the expected frequency, then the above in this case would be the man-in-the-street's idea of the law of averages'. It turns out that the above statement is false in this case, taken literally: some qualification is. needed. However, the qualification needed is absolutely the minimal one imaginable: one merely. needs to exclude a set of probability zero - that is, to assert convergence on a set of probability one ('almost surely'), rather than everywhere.  

Definition B.6.1. If $X_{n}$ $X$ are random variables, we say $X_{n}$ converges to $X$ almost surely -  

$$
X_{n}\rightarrow X\quad(n\rightarrow\infty)\quad a.s.
$$  

- if $X_{n}\rightarrow X$ with probability one - that is, if  

$$
P(\{\omega:X_{n}(\omega)\rightarrow X(\omega)\quad a s\enspace n\rightarrow\infty\})=1.
$$  

The loose idea of the 'law of averages' has as its precise form a statement on convergence almost. surely. This is Kolmogorov's strong law of large numbers (see e.g. (Williams 1991), \$12.10), which is quite difficult to prove.  

Weaker convergence concepts are also useful: they may hold under weaker conditions, or they may be easier to prove.  

Definition B.6.2. If $X_{n}$ $X$ are random variables, we say that $X_{n}$ converges to $X$ in probability  

- if, for all $\epsilon>0$  

$$
P\left(\{\omega:|X_{n}(\omega)-X(\omega)|>\epsilon\}\right)\to0(n\to\infty).
$$  

It turns out that convergence almost surely implies convergence in probability, but not in gen-. eral conversely. Thus almost-sure convergence is a stronger convergence concept than convergence in probability. This comparison is reflected in the form the 'law of averages' takes for convergence. in probability: this is called the weak law of large numbers, which as its name implies is a weaker form of the strong law of large numbers. It is correspondingly much easier to prove: indeed, we. shall prove it in $\S2.8$ below.  

Recall the. $L^{p}$ -spaces of $p$ th-power integrable functions (\$2.2). We similarly define the $L^{p}$ -spaces of $p$ th-power integrable random variables: if $p\geq1$ and $X$ is a random variable with  

$$
\begin{array}{r}{\|X\|_{p}:=(I E|X|^{p})^{1/p}<\infty,}\end{array}
$$  

we say that $X\in L^{p}$ (or $L^{p}(\Omega,\mathcal{F},\varmathbb{\it{P}})$ to be precise). For $X_{n}$ $X\in L^{p}$ , there is a natural convergence concept: we say that $X_{n}$ converges to $X$ in $L^{p}$ , or in pth mean,  

$$
X_{n}\to X\quad{\mathrm{in}}\quad L^{p},
$$  

if  

$$
\|X_{n}-X\|_{p}\to0(n\to\infty),
$$  

that is, if  

$$
B E(|X_{n}-X|^{p})\to0(n\to\infty).
$$  

The cases $p=1,2$ are particularly important: if $X_{n}\rightarrow X$ in $L^{1}$ , we say that. $X_{n}\rightarrow X$ in mean;   
if $X_{n}\to X$ in $L^{2}$ we say that $X_{n}\rightarrow X$ in mean square. Convergence in $p$ th mean is not directly.   
comparable with convergence almost surely (of course, we have to restrict to random variables in $L^{p}$ for the comparison even to be meaningful): neither implies the other. Both, however, imply.   
convergence in probability.  

All the modes of convergence discussed so far involve the values of random variables. Often,. however, it is only the distributions of random variables that matter. In such cases, the natural mode of convergence is the following:  

Definition B.6.3. We say that random variables $X_{n}$ converge to $X$ in distribution if the distri-.   
bution functions of. $X_{n}$ converge to that of. $X$ at all points of continuity of the latter:.  

if  

$$
P(\{X_{n}\leq x\})\rightarrow P(\{X\leq x\})(n\rightarrow\infty)
$$  

for all points. $x$ at which the right-hand side is continuous.  

The restriction to continuity points $x$ of the limit seems awkward at first, but it is both natural and necessary. It is also quite weak: note that the function $x\mapsto I P(\{X\leq x\})$ , being monotone in $x$ , is continuous except for at most countably many jumps. The set of continuity points is thus uncountable: 'most' points are continuity points.  

Convergence in distribution is (by far) the weakest of the modes of convergence introduced so far: convergence in probability implies convergence in distribution, but not conversely. There is, however, a partial converse (which we shall need in g2.8): if the limit $X$ is constant (non-random), convergence in probability and in distribution are equivalent.  

# Weak Convergence.  

If ${\boldsymbol{\mathit{I P}}}_{n}$ $\mathcal{W}$ are probability measures, we say that  

$$
{\cal I}P_{n}\rightarrow{\cal I}P(n\rightarrow\infty)\mathrm{weakly}
$$  

if  

$$
\int f d P_{n}\to\int f d P(n\to\infty)
$$  

for all bounded continuous functions $f$ . This definition is given a full-length book treatment in. (Billingsley 1968), and we refer to this for background and details. For ordinary (real-valued) random variables, weak convergence of their probability measures is the same as convergence. in distribution of their distribution functions. However, the weak-convergence definition above applies equally, not just to this one-dimensional case, or to the finite-dimensional (vector-valued) setting, but also to infinite-dimensional settings such as arise in convergence of stochastic processes. We shall need such a framework in the passage from discrete- to continuous-time Black-Scholes. models.  

# Appendix C  

# Stochastic Processes in Discrete Time  

# C.1 Information and Filtrations  

Access to full, accurate, up-to-date information is clearly essential to anyone actively engaged in.   
financial activity or trading. Indeed, information is arguably the most important determinant.   
of success in financial life. Partly for simplicity, partly to reflect the legislation and regulations.   
against insider trading, we shall confine ourselves to the situation where agents take decisions on.   
the basis of information in the public domain, and available to all. We shall further assume that.   
information once known remains known - is not forgotten - and can be accessed in real time.  

In reality, of course, matters are more complicated. Information overload is as much of a danger. as information scarcity. The ability to retain information, organise it, and access it quickly, is one of the main factors which will discriminate between the abilities of different economic agents to. react to changing market conditions. However, we restrict ourselves here to the simplest possible situation and do not differentiate between agents on the basis of their information-processing abilities. Thus as time passes, new information becomes available to all agents, who continually. update their information. What we need is a mathematical language to model this information fow, unfolding with time. This is provided by the idea of a filtration; we outline below the elements of this theory that we shall need..  

The Kolmogorov triples $(\Omega,{\mathcal{F}},P)$ , and the Kolmogorov conditional expectations ${\mathcal{L}}(X|B)$ give us all the machinery we need to handle static situations involving randomness. To handle dynamic situations, involving randomness which unfolds with time, we need further structure..  

We may take the initial, or starting, time as $t=0$ . Time may evolve discretely, or continuously. We postpone the continuous case to Chapter 5; in the discrete case, we may suppose time evolves in integer steps, $t=0,1,2,\ldots$ (say, stock-market quotations daily, or tick data by the second).. There may be a final time $T$ , or time horizon, or we may have an infinite time horizon (in the. context of option pricing, the time horizon $T$ is the expiry time).  

We wish to model a situation involving randomness unfolding with time. As above, we suppose, for simplicity, that information is never lost (or forgotten): thus, as time increases we learn more. We recall from Chapter 2 that $\sigma$ -algebras represent information or knowledge. We thus need a sequence of $\sigma$ -algebras $\{{\mathcal{F}}_{n}:n=0,1,2,...\}$ , which are increasing:  

$$
{\mathcal{F}}_{n}\subset{\mathcal{F}}_{n+1}\quad(n=0,1,2,\ldots),
$$  

with ${\mathcal{F}}_{n}$ representing the information, or knowledge, available to us at time $n$ .We shall always suppose all $\sigma$ -algebras to be complete (this can be avoided, and is not always appropriate, but it simplifies matters and suffices for our purposes). Thus. $\mathcal{F}_{0}$ represents the initial information (if.  

there is none, $\mathcal{F}_{0}=\{\varnothing,\Omega\}$ , the trivial $\sigma$ -algebra). On the other hand,  

$$
{\mathcal{F}}_{\infty}:=\operatorname*{lim}_{n\to\infty}{\mathcal{F}}_{n}=\sigma\left(\bigcup_{n}{\mathcal{F}}_{n}\right)
$$  

represents all we ever will know (the Doomsday. $\sigma$ -algebra'). Often,. $\mathcal{F}_{\infty}$ will be $\mathcal{F}$ (the $\sigma$ -algebra from Chapter 2, representing 'knowing everything'). But this will not always be so; see e.g. Williams (1991), \$15.8 for an interesting example. Such a family. ${\cal{F}}:=\{{\mathcal{F}}_{n}:n=0,1,2,...\}$ is called a filtration; a probability space endowed with such a filtration,. $\{\Omega,\pi,{\mathcal{F}},P\}$ is called a stochastic basis or filtered probability space.. These definitions are due to P. A. Meyer of. Strasbourg; Meyer and the Strasbourg (and more generally, French) school of probabilists have been responsible for the 'general theory of (stochastic) processes, and for much of the progress. in stochastic integration, since the 1960s; see e.g. Dellacherie and Meyer (1978), Dellacherie and Meyer (1982), Meyer (1966), Meyer (1976).  

For the special case of a finite state space $\Omega=\{\omega_{1},\ldots,\omega_{n}\}$ and a given $\sigma$ algebra $\mathcal{F}$ on $\Omega$ (which in this case is just an algebra) we can always find a unique finite partition $\mathcal{P}=\{A_{1},\ldots,A_{l}\}$ of $\Omega$ , i.e. the sets $A_{i}$ are disjoint and $\textstyle\bigcup_{i=1}^{l}A_{i}=\Omega$ , corresponding to $\mathcal{F}$ . A filtration $\bar{\mathcal{M}}$ therefore corresponds to a sequence of finer and finer partitions $\mathcal{P}_{n}$ . At time $t=0$ the agents only know that. some event $\omega\in\Omega$ will happen, at time. $T<\infty$ they know which specific event $\omega^{*}$ has happened. During the flow of time the agents learn the specific structure of the $(\sigma-)$ algebras ${\mathcal{F}}_{n}$ , which means they learn the corresponding partitions $\mathcal{P}$ . Having the information in. ${\mathcal{F}}_{n}$ revealed is equivalent to. knowing in which $A_{i}^{(n)}\in\mathcal{P}_{n}$ the event $\omega^{*}$ is. Since the partitions become finer the information on $\omega^{*}$ becomes more detailed with each step.  

Unfortunately this nice interpretation breaks down as soon as $\Omega$ becomes infinite.It turns out that the concept of filtrations rather than that of partitions is relevant for the more general situations of infinite $\Omega$ , infinite $T$ and continuous-time processes.  

# C.2 Discrete-Parameter Stochastic Processes  

The word 'stochastic' (derived from the Greek) is roughly synonymous with 'random'. It is perhaps unfortunate that usage favours 'stochastic process' rather than the simpler 'random process', but as it does, we shall follow it.  

We need a framework which can handle dynamic situations, in which time evolves, and in which new information unfolds with time. In particular, we need to be able to speak in terms of 'the information available at time. $n^{\prime}$ , or, 'what we know at time. $n$ '. Further, we need to be able to. increase $n-\mathrm{t}$ hereby increasing the information available as new information (typically, new price information) comes in, and talk about the information fow over time. One has a clear mental picture of what is meant by this - there is no conceptual difficulty. However, what is needed is a precise mathematical construct, which can be conveniently manipulated - perhaps in quite complicated ways - and yet which bears the above heuristic meaning. Now 'information' is not only an ordinary word, but even a technical term in mathematics - many books have been written on the subject of information theory. However, information theory in this sense is not what we. need: for us, the emphasis is on the flow of information, and how to model and describe it. With. this by way of motivation, we proceed to give some of the necessary definitions..  

A stochastic process $X=\{X_{n}:n\in I\}$ is a family of random variables, defined on some common probability space, indexed by an index-set $I$ . Usually (always in this book),. $I$ represents time (sometimes $I$ represents space, and one calls. $X$ a spatial process). Here,. $I=\{0,1,2,\ldots,T\}$ (finite horizon) or $I=\{0,1,2,...\}$ (infinite horizon). The (stochastic) process. $X=(X_{n})_{n=0}^{\infty}$ is Said to be adapted to the filtration. $\textstyle F=({\mathcal{F}}_{n})_{n=0}^{\infty}$ if  

$$
X_{n}{\mathrm{~is~}}{\mathcal{F}}_{n}-{\mathrm{measurable~for~all~}}n.
$$  

So if $X$ is adapted, we will know the value of $X_{n}$ at time $n$ . If  

$$
\mathcal{F}_{n}=\sigma(X_{0},X_{1},...,X_{n})
$$  

we call ( ${\mathcal{F}}_{n}$ ) the natural filtration of. $X$ . Thus a process is always adapted to its natural filtration.   
A typical situation is that.  

$$
{\mathcal{F}}_{n}=\sigma(W_{0},W_{1},\ldots,W_{n})
$$  

is the natural filtration of some process $W=(W_{n})$ . Then $X$ is adapted to $\boldsymbol{\varPsi}=\left(\mathcal{F}_{n}\right)$ , i.e. each $X_{n}$ is ${\mathcal{F}}_{n}$ - (or $\sigma(W_{0},\cdot\cdot\cdot,W_{n})-$ ) measurable, iff  

$$
X_{n}=f_{n}(W_{0},W_{1},\ldots,W_{n})
$$  

for some measurable function $f_{n}$ (non-random) of $n+1$ variables.  

# Notation.  

For a random variable $X$ on $(\Omega,{\mathcal{F}},I P)$ $X(\omega)$ is the value $X$ takes on $\omega$ $\omega$ represents the randomness). For a stochastic process $X=\left(X_{n}\right)$ , it is convenient (e.g., if using suffixes, $n_{i}$ say) to use $X_{n}$ $X(n)$ interchangeably, and we shall feel free to do this. With $\omega$ displayed, these become $X_{n}(\omega)$ $X(n,\omega)$ , etc.  

The concept of a stochastic process is very general - and so very flexible -- but it is too general. for useful progress to be made without specifying further structure or further restrictions. There are two main types of stochastic process which are both general enough to be sufficiently flexible to model many commonly encountered situations, and sufficiently specific and structured to have a rich and powerful theory. These two types are Markov processes and martingales. A Markov. process models a situation in which where one is, is all one needs to know when wishing to predict the future - how one got there provides no further information. Such a lack of memory' property,. though an idealisation of reality, is very useful for modelling purposes. We shall encounter Markov processes more in continuous time (see Chapter 5) than in discrete time, where usage dictates that they are called Markov chains. For an excellent and accessible recent treatment of Markov chains, see e.g. Norris (1997). Martingales, on the other hand (see 3.3 below) model fair gambling games - situations where there may be lots of randomness (or unpredictability), but no tendency to drift. one way or another: rather, there is a tendency towards stability, in that the chance influences tend to cancel each other out on average..  

# C.3 Definition and basic properties of martingales  

Excellent accounts of discrete-parameter martingales are Neveu (1975), Williams (1991) and Williams (2001) to which we refer the reader for detailed discussions. We will summarise what we need to use martingales for modelling in finance..  

Definition C.3.1. A process $X=\left(X_{n}\right)$ is called a martingale relative to $(\{\mathcal{F}_{n}\},\mathcal{P})$ if  

(i) $X$ is adapted (to $\{\mathcal{F}_{n}\}.$   
(ii) $\textstyle H\left|X_{n}\right|<\infty$ for all $n$   
(iii) $E[X_{n}|\mathcal{F}_{n-1}]=X_{n-1}$ P-a.s.(n1).  

$X$ is a supermartingale if in place of (i)  

$$
\begin{array}{r}{B E[X_{n}|\mathcal F_{n-1}]\leq X_{n-1}~B P-a.s.~(n\geq1);}\end{array}
$$  

$X$ is a submartingale if in place of (iii)  

$$
E[X_{n}|{\mathcal{F}}_{n-1}]\geq X_{n-1}~D-a.s.~(n\geq1).
$$  

Martingales have a useful interpretation in terms of dynamic games: a martingale is 'constant. on average', and models a fair game; a supermartingale is 'decreasing on average', and models an unfavourable game; a submartingale is 'increasing on average', and models a favourable game.  

# Note.  

1. Martingales have many connections with harmonic functions in probabilistic potential theory. The terminology in the inequalities above comes from this: supermartingales correspond to superharmonic functions, submartingales to subharmonic functions..   
2. $X$ is a submartingale (supermartingale) if and only if. $-X$ is a supermartingale (submartingale); $X$ is a martingale if and only if it is both a submartingale and a supermartingale.   
3. $\left(X_{n}\right)$ is a martingale if and only if. $\left(X_{n}-X_{0}\right)$ is a martingale. So we may without loss of. generality take $X_{0}=0$ when convenient.   
4.If $X$ is a martingale, then for $m\:<\:n$ using the iterated conditional expectation and the martingale property repeatedly (all equalities are in the a.s.-sense)  

$$
\begin{array}{r c l}{{\cal E}[X_{n}|{\mathcal F}_{m}]}&{=}&{{\cal E}[{\cal E}(X_{n}|{\mathcal F}_{n-1})|{\mathcal F}_{m}]={\cal E}[X_{n-1}|{\mathcal F}_{m}]}\ {}&{}&{}\ {}&{=}&{\ldots={\cal E}[X_{m}|{\mathcal F}_{m}]=X_{m},}\end{array}
$$  

and similarly for submartingales, supermartingales.  

From the Oxford English Dictionary: martingale (etymology unknown)  

1. 1589. An article of harness, to control a horse's head..   
2. Naut. A rope for guying down the jib-boom to the dolphin-striker..   
3. A system of gambling which consists in doubling the stake when losing in order to recoup oneself (1815).   
Thackeray: 'You have not played as yet? Do not do so; above all avoid a martingale if you do.'  

Gambling games have been studied since time immemorial - indeed, the Pascal-Fermat correspondence of 1654 which started the subject was on a problem (de Mere's problem) related to gambling. The doubling strategy above has been known at least since 1815.  

The term 'martingale' in our sense is due to J. Ville (1939). Martingales were studied by Paul Levy (1886-1971) from 1934 on (see obituary (Loeve 1973) and by J.L. Doob (1910-) from 1940 on. The first systematic exposition was (Doob 1953). This classic book, though hard going, is still a valuable source of information.  

# Examples.  

1. Mean zero random walk:. $S_{n}=\sum X_{i}$ , with $X_{i}$ independent with $\textstyle{\mathcal{L}}(X_{i})=0$ is a martingale (submartingales: positive mean; supermartingale: negative mean).   
2. Stock prices: $S_{n}=S_{0}\zeta_{1}\cdot\cdot\cdot\zeta_{n}$ with $\zeta_{i}$ independent positive r.vs with existing first moment. 3. Accumulating data about a random variable (Williams (1991), pp. 96, 166-167). If $\xi\in\mathbf{\Xi}$ $\mathcal{L}^{1}(\Omega,\mathcal{F},\mathit{\Pi},\mathit{\Pi}^{\textit{\Pi}})$ $M_{n}:=I E(\xi|\mathcal{F}_{n})$ (so $M_{n}$ represents our best estimate of $\xi$ based on knowledge at time $n$ ), then using iterated conditional expectations  

$$
\begin{array}{r}{E[M_{n}|\mathcal{F}_{n-1}]=E[E(\xi|\mathcal{F}_{n})|\mathcal{F}_{n-1}]=E[\xi|\mathcal{F}_{n-1}]=M_{n-1},}\end{array}
$$  

so ( $M_{n}$ ) is a martingale. One has the convergence  

$$
M_{n}\rightarrow M_{\infty}:=I E[\xi|\mathcal{F}_{\infty}]\quad a.s.\quad\mathrm{and~in~}\mathcal{L}^{1}.
$$  

# C.4 Martingale Transforms  

Now think of a gambling game, or series of speculative investments, in discrete time. There is no play at time $0$ ; there are plays at times $n=1,2,\ldots$ and  

$$
\Delta X_{n}:=X_{n}-X_{n-1}
$$  

represents our net winnings per unit stake at play $n$ . Thus if $X_{n}$ is a martingale, the game is 'fair on average'.  

Call a process. $C=(C_{n})_{n=1}^{\infty}$ predictable if $C_{n}$ is ${\mathcal{F}}_{n-1}$ -measurable for all. $n\geq1$ . Think of $C_{n}$ as your stake on play $n$ $C_{0}$ is not defined, as there is no play at time $0$ ). Predictability says that you have to decide how much to stake on play. $n$ based on the history before time $n$ (i.e., up to. and including play $n-1$ ). Your winnings on game $n$ are $C_{n}\Delta X_{n}=C_{n}(X_{n}-X_{n-1})$ . Your total. (net) winnings up to time $n$ are  

$$
Y_{n}=\sum_{k=1}^{n}C_{k}\Delta X_{k}=\sum_{k=1}^{n}C_{k}(X_{k}-X_{k-1}).
$$  

We write  

$$
Y=C\bullet X,Y_{n}=(C\bullet X)_{n},\Delta Y_{n}=C_{n}\Delta X_{n}
$$  

$((C\bullet X)_{0}=0$ as $\textstyle\sum_{k=1}^{0}$ is empty), and call $C\bullet X$ the martingale transform of $X$ by $C$  

Theorem C.4.1. (i) If $C$ is a bounded non-negative predictable process and $X$ is a supermartingale, $C\bullet X$ is a supermartingale null at zero. (ii) If $C$ is bounded and predictable and $X$ is a martingale,. $C\bullet X$ is a martingale null at zero.  

Proof. $Y=C\bullet X$ is integrable, since $C$ is bounded and $X$ integrable. Now  

$$
\begin{array}{r l r}{I E[Y_{n}-Y_{n-1}|\mathcal{F}_{n-1}]}&{=}&{I E[C_{n}(X_{n}-X_{n-1})|\mathcal{F}_{n-1}]}\ &{}&\ &{=}&{C_{n}I E[(X_{n}-X_{n-1})|\mathcal{F}_{n-1}]}\end{array}
$$  

(as $C_{n}$ is bounded, so integrable, and ${\mathcal{F}}_{n-1}$ -measurable, so can be taken out)  

in case (i), as. $C\geq0$ and $X$ is a supermartingale,  

$$
=0
$$  

in case (ii), as $X$ is a martingale.  

Interpretation. You can't beat the system! In the martingale case, predictability of. $C$ means we can't foresee the future (which is realistic and fair). So we expect to gain nothing - as we should.  

# Note.  

1. Martingale transforms were introduced and studied by Burkholder (1966). For a textbook account, see e.g. Neveu (1975), VIII.4.   
2. Martingale transforms are the discrete analogues of stochastic integrals. They dominate the mathematical theory of finance in discrete time, just as stochastic integrals dominate the theory in continuous time.  

Lemma C.4.1 (Martingale Transform Lemma). An adapted sequence of real integrable random variables ( $X_{n}$ ) is a martingale iff for any bounded predictable sequence (. $C_{n}$  

$$
E\left(\sum_{k=1}^{n}C_{k}\Delta X_{k}\right)=0(n=1,2,\ldots).
$$  

Proof. If ( $X_{n}$ ) is a martingale, $Y$ defined by $Y_{0}=0$  

$$
Y_{n}=\sum_{k=1}^{n}C_{k}\Delta X_{k}(n\geq1)
$$  

is the martingale transform $C\bullet X$ , so is a martingale. Now $\begin{array}{r}{\begin{array}{r}{E(Y_{1})=E(C_{1}I E(X_{1}-X_{0}))=0}\end{array}}\end{array}$ and we see by induction that  

$$
E(Y_{n+1})=E(C_{n+1}(X_{n+1}-X_{n}))+E(Y_{n})=0.
$$  

Conversely, if the condition of the proposition holds, choose $j$ , and for any ${\mathcal{F}}_{j}$ -measurable set $A$ write $\textstyle C_{n}=0$ for $n\neq j+1$ $C_{j+1}=\mathbf{1}_{A}$ . Then ( $C_{n}$ ) is predictable, so the condition of the proposition, $\begin{array}{r}{D E(\sum_{k=1}^{n}C_{k}\Delta X_{k})=0}\end{array}$ , becomes  

$$
E[\mathbf{1}_{A}(X_{j+1}-X_{j})]=0.
$$  

Since this holds for every set. $A\in{\mathcal{F}}_{j}$ , the definition of conditional expectation gives  

$$
\begin{array}{r}{I E(X_{j+1}|\mathcal{F}_{j})=X_{j}.}\end{array}
$$  

Since this holds for every $j$ $X_{n}$ ) is a martingale.  

Remark C.4.1. The proof above is a good example of the value of Kolmogorov's definition of. conditional expectation - which reveals itself, not in immediate transparency, but in its ease of handling in proofs. We shall see in Chapter 4 the financial significance of martingale transforms. $H\bullet M$  

# Bibliography  

Allingham, M., 1991, Arbitrage. Elements of financial economics. (MacMillan).   
Barndorff-Nielsen, O.E., 1998, Processes of normal inverse Gaussian type, Finance and Stochastics 2, 41-68.   
Billingsley, P., 1968, Convergence of probability measures. (Wiley, New York)   
Bjork, T., 1995, Arbitrage theory in continuous time, Notes from Ascona meeting..   
Bjork, T., 1997, Interest rate theory, in Financial Mathematics, ed. by W.J. Runggaldier Lecture Notes in Mathematics pp. 53-122. Springer, Berlin New York London.   
Black, F., and M. Scholes, 1973, The pricing of options and corporate liabilities, Journal of Political Economy 72, 637-659.   
Brown, R.H., and S.M. Schaefer, 1995, Interest rate volatility and the shape of the term structure, in S.D. Howison, F.P. Kelly, and P. Wilmott, eds.: Mathematical models in finance (Chapman. & Hall, ).   
Burkholder, D.L., 1966, Martingale transforms, Ann. Math. Statist. 37, 1494-1504.   
Burkill, J.C., and H. Burkill, 1970, A second course in mathematical analysis. (Cambridge Uni-. versity Press).   
Cochrane, J.H., 2001, Asset pricing. (Princeton University Press).   
Cox, D.R., and H.D. Miller, 1972, The theory of stochastic processes. (Chapman and Hall, London and New York) First published 1965 by Methuen & Co Ltd.   
Cox, J.C., and S.A. Ross, 1976, The valuation of options for alternative stochastic processes, Journal of Financial Economics 3, 145-166.   
Cox, J.C., S. A. Ross, and M. Rubinstein, 1979, Option pricing: a simplified approach, J. Financial Economics 7, 229-263.   
Cox, J.C., and M. Rubinstein, 1985, Options markets. (Prentice-Hall).   
Davis, M.H.A., 1994, A general option pricing formula, Preprint, Imperial College.   
Dellacherie, C., and P.-A. Meyer, 1978, Probabilities and potential vol. A. (Hermann, Paris).   
Dellacherie, C., and P.-A. Meyer, 1982, Probabilities and potential vol. B. (North Holland, Amsterdam New York).   
Doob, J. L., 1953, Stochastic processes. (Wiley).   
Dothan, M. U., 1990, Prices in financial markets. (Oxford University Press).   
Dudley, R.M., 1989, Real Analysis and Probability. (Wadsworth, Pacific Grove).   
Duffie, D., 1992, Dynamic Asset Pricing Theory. (Princton University Press).   
Duffie, D., and R. Kan, 1995, Multi-factor term structure models, in S.D. Howison, F.P. Kelly, and P. Wilmott, eds.: Mathematical models in finance (Chapman & Hall, ).   
Durrett, R., 1996, Probability: Theory and Examples. (Duxbury Press at Wadsworth Publishing Company) 2nd edn.   
Durrett, R., 1999, Essentials of stochastic processes. (Springer).   
Eberlein, E., and U. Keller, 1995, Hyperbolic distributions in finance, Bernoulli 1, 281-299.   
Edwards, F.R., and C.W. Ma, 1992, Futures and Options. (McGraw-Hill, New York).   
El Karoui, N., R. Myneni, and R. Viswanathan, 1992, Arbitrage pricing and hedging of interest rate claims with state variables: I. Theory, Universite de Paris VI and Stanford University.   
Grimmett, G.R., and D.J.A. Welsh, 1986, Probability: An introduction. (Oxford University Press).   
Harrison, J.M., 1985, Brownian motion and stochastic flow systems. (John Wiley and Sons, New York).   
Harrison, J.M., and D. M. Kreps, 1979, Martingales and arbitrage in multiperiod securities markets, J. Econ. Th. 20, 381-408.   
Harrison, J.M., and S.R. Pliska, 1981, Martingales and stochastic integrals in the theory of continuous trading, Stochastic Processes and their Applications 11, 215-260.   
Heath, D., R. Jarrow, and A. Morton, 1992, Bond pricing and the term structure of interest rates:. a new methodology for contingent claim valuation, Econometrica 60, 77-105.   
Ikeda, N., S. Watanabe, Fukushima M., and H. Kunita  (eds.), 1996, Ito stochastic calculus and probability theory. (Springer, Tokyo Berlin New York) Festschrift for Kiyosi Ito's eightieth birthday, 1995.   
Ince, E.L., 1944, Ordinary differential equations. (Dover New York).   
Jacod, J., and P. Protter, 2000, Probability essentials. (Springer).   
Jameson, R. (ed.), 1995, Derivative credit risk. (Risk Publications London).   
Jarrow, R.A., and S.M. Turnbull, 2000, Derivative Securities. (South-Western College Publishing,. Cincinnati) 2nd edn. 1st ed. 1996.   
Jeans, Sir James, 1925, The mathematical theory of electricity and magnetism. (Cambridge University Press) 5th. edn.   
Karatzas, I., and S. Shreve, 1991, Brownian motion and stochastic calculus. (Springer, New York) 2nd edn.   
Kolb, R.W., 1991, Understanding Futures Markets. (Kolb Publishing, Miami) 3rd edn.   
Kolmogorov, A.N., 1933, Grundbegriffe der Wahrscheinlichkeitsrechnung. (Springer) English translation: Foundations of probability theory, Chelsea, New York, (1965).   
Lebesgue, H., 1902, Integrale, longueur, aire, Annali di Mat. 7, 231-259..   
Loeve, M., 1973, Paul Levy (1886-1971), obituary, Annals of Probability 1, 1-18.   
Madan, D., 1998, Default risk, in D.J. Hand, and S.D. Jacka, eds.: Statistics in finance (Arnold, London, ).   
BIBLIOGRAPHY 141   
Merton, R.C., 1973, Theory of rational option pricing, Bell Journal of Economics and Management Science 4, 141-183.   
Merton, R.C., 1990, Continuous-time finance. (Blackwell, Oxford)..   
Meyer, P.-A., 1966, Probability and potential. (Blaisdell, Waltham, Mass.)..   
Meyer, P.-A., 1976, Un cours sur les integrales stochastiques, in Seminaire de Probabilites $X$ no. 511 in Lecture Notes in Mathematics pp. 245-400. Springer, Berlin Heidelberg New York.   
Musiela, M., and M. Rutkowski, 1997, Martingale methods in financial modelling vol. 36 of Applications of Mathematics: Stochastic Modelling and Applied Probability. (Springer, New York)..   
Neveu, J., 1975, Discrete-parameter martingales. (North-Holland).   
Norris, J.R., 1997, Markov chains. (Cambridge University Press)..   
Protter, P., 2004, Stochastic Integration and Differential Equations. (Springer, New York) 2nd edn. 1rst edition, 1992.   
Rennocks, John, 1997, Hedging can only defer currency volatility impact for British Steel, Financial Times 08, Letter to the editor.   
Resnick, S., 2001, A probability path. (Birkhauser) 2nd printing.   
Revuz, D., and M. Yor, 1991, Continuous martingales and Brownian motion. (Springer, New York).   
Rockafellar, R.T., 1970, Convex Analysis. (Princton University Press, Princton NJ).   
Rogers, L.C.G., and D. Williams, 1994, Diffusions, Markov processes and martingales, Volume 1: Foundation. (Wiley) 2nd edn. 1st ed. D. Williams, 1970.   
Rosenthal, J.S., 2000, A first look at rigorous probability theory. (World Scientific)..   
Ross, S.M., 1997, Probability models. (Academic Press) 6th edn.   
Rydberg, T.H., 1996, Generalized hyperbolic diffusions with applications towards finance, Research Report 342, Department of Theoretical Statistics, Institute of Mathematics, University. Of Arhus University.   
Rydberg, T.H., 1997, The normal inverse Gaussian Levy process: Simulation and approximation, Research Report, Department of Theoretical Statistics, Institute of Mathematics, University of Arhus University.   
Samuelson, P.A., 1965, Rational theory of warrant pricing, Industrial Management Review 6, 13-39.   
Schachermayer, W., 2000, Introduction to the mathematics of financial markets, to appear as Springer Lecture Notes.   
Shephard, N., 1996, Statistical aspects of ARCH and stochastic volatility, in D.R. Cox, D.V. Hinkley, and O.E. Barndorff-Nielsen, eds.: Time Series Models - in econometrics, finance and other fields (Chapman & Hall, ).   
Snell, J. L., 1952, Applications of martingale systems theorems, Trans. Amer. Math. Soc. 73, 293-312.   
Taqqu, M.S., and W. Willinger, 1987, The analysis of finite security markets using martingales, Adv. Appl. Prob. 19, 1-25.   
Williams, D., 1991, Probability with martingales. (Cambridge University Press).   
Williams, D., 2001, Weighing the odds. (Cambridge University Press)   
Yor, M., 1978, Sous-espaces denses dans $L^{1}$ et $H^{1}$ et representation des martingales, in Seminaire de Probabilites, XII no. 649 in Lecture Notes in Mathematics pp. 265-309. Springer.   
Zhang, P.G., 1997, Exotic Options. (World Scientific, Singapore).  