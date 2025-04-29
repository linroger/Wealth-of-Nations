# PRICING TOOLS IN FINANCIAL 12 ENGINEERING  

# CHAPTER OUTLINE  

# 12.1 Introduction . 39  

12.2 Summary of Pricing Approaches... 395  

# 2.3 The Framework . 396  

12.3.1 States of the World . 396   
12.3.2 The Payoff Matrix . 398   
12.3.3 The Fundamental Theorem. 398   
12.3.4 Definition of an Arbitrage Opportunity . 399   
12.3.5 Interpreting the $Q^{j}$ : State Prices. 399   
12.3.5.1 Remarks .. 401  

# 2.4 An Application . 401  

12.4.1 Obtaining the $\omega^{j}$ 402   
12.4.2 Elementary Contracts and Options 405   
12.4.3 Elementary Contracts and Replication .. 406  

# 12.5 Implications of the Fundamental Theorem.. 408  

12.5.1 Result 1: Risk-Adjusted Probabilities 408   
12.5.1.1 Risk-neutral probabilities 409   
12.5.1.2 Other probabilities . 409   
12.5.1.3 A remark... 411   
12.5.1.4 Swap measure.. 412   
12.5.2 Result 2: Martingale Property 412   
12.5.2.1 Martingales under $\tilde{P}$ . 412   
12.5.2.2 Martingales under other probabilities 413   
12.5.3 Result 3: Expected Returns.. 413   
12.5.3.1 Martingales and risk premia.. 414  

# 12.6 Arbitrage-Free Dynamics.. 415  

12.6.1 Arbitrage-Free SDEs 415   
12.6.2 Tree Models . 416   
12.6.2.1 Case 1 . 417   
12.6.2.2 Case 2 . 419  

# 12.7 Which Pricing Method to Choose?. 419  

12.8 Conclusions.. 420  

Suggested Reading . . 420   
Appendix 12.1: Simple Economics of the Fundamental Theorem .. . 420   
Exercises . 422   
EXCEL Exercises . . 424  

# 12.1 INTRODUCTION  

We have thus far proceeded without a discussion of asset pricing models and the tools associated with them, as financial engineering has many important dimensions besides pricing. In this chapter, we will discuss models of asset pricing, albeit in a very simple context. A summary chapter on pricing tools would unify some of the previous topics and show the subtle connections between them. The discussion will approach the issue using a framework that is a natural extension of the financial engineering logic utilized thus far.  

Pricing comes with at least two problems that seem, at first, difficult to surmount in any satisfactory way. Investors like return, but dislike risk. This means that assets associated with nondiversifiable risks will carry risk premia. But, how can we measure such risk premia objectively when buying assets is essentially a matter of subjective preferences? Modeling risk premia using utility functions may be feasible theoretically, but this is not attractive from a trader’s point of view if hundreds of millions of dollars are involved in the process. The potential relationship between risk premia and utility functions of players in the markets is the first unpleasant aspect of practical pricing decisions.  

The second problem follows from the first. One way or another, the pricing approach needs to be based on measuring the volatility of future cash flows. But volatility is associated with randomness and with some probability distribution. How can an asset pricing approach that intends to be applicable in practice obtain a reasonable set of real-world probabilities?1  

Modern finance has found an ingenious and practical way of dealing with both these questions simultaneously. Instead of using a framework where risk premia are modeled explicitly, the profession transforms a problem with risk premia into one where there are no risk premia. Interestingly, this transformation is done in a way that the relevant probability distribution ceases to be the realworld probability and, instead, becomes a market-determined probability that can be numerically calculated at any point in time if there is a reasonable number of liquid instruments.2 With this approach, the assets will be priced in an artificial risk-neutral environment where the risk premia are indirectly taken into account. This methodology is labeled the Martingale approach. It is a powerful tool in practical asset pricing and risk management.  

A newcomer to financial engineering may find it hard to believe that a more or less unified theory for pricing financial assets that can be successfully applied in real-world pricing actually exists. After all, there are many different types of assets, and not all of them seem amenable to the same pricing methodology, even at a theoretical level. A market practitioner may already have heard of risk-neutral pricing, but just like the newcomer to financial engineering, he or she may regard the basic theory behind it as very abstract. And yet, the theory is surprisingly potent. This chapter provides a discussion of this methodology from the point of view of a financial engineer. Hence, even though the topic is asset pricing, the way we approach it is based on ideas developed in previous chapters. Basically, this pricing methodology is presented as a general approach to synthetic asset creation.  

Of course, like any other theory, this methodology depends on some strict assumptions. The methods used in this text will uniformly make one common assumption that needs to be pointed out at the start. Only those models that assume complete markets are discussed. In heuristic terms, when markets are “complete,” there are “enough” liquid instruments for obtaining the working probability distribution.  

This chapter progressively introduces a number of important theoretical results that are used in pricing, hedging, and risk-management application. The main result is called the fundamental theorem of asset pricing. Instead of a mathematical proof, we use a financial engineering argument to justify it, and a number of important consequences will emerge. Throughout the chapter, we will single out the results that have practical implications.  

# 12.2 SUMMARY OF PRICING APPROACHES  

In this section, we remind the reader of some important issues from earlier chapters. Suppose we want to find the fair market price of an instrument. First, we construct a synthetic equivalent to this instrument using liquid contracts that trade in financial markets. Clearly, this requires that such contracts are indeed available. Second, once these liquid contracts are found, an arbitrage argument is used. The cost of the replicating portfolio should equal the cost of the instrument we are trying to price. Third, a trader would add a proper margin to this cost and thus obtain the fair price.  

In earlier chapters, we obtained synthetics for forward rate agreements (FRAs), foreign exchange (FX) forwards, and several other quasi-linear instruments. Each of these constitutes an early example of asset pricing. Obtain the synthetic and see how much it costs. By adding a profit to this cost, the fair market price is obtained. It turns out that we can extend this practical approach and obtain a general theory.  

It should be reemphasized that pricing and hedging efforts can sometimes be regarded as two sides of the same coin. In fact, hedging a product requires finding a replicating portfolio and then using it to cover the position in the original asset. If the trader is long in the original instrument, he or she would be short in the synthetic, and vice versa. This way, exposures to risks would cancel out and the position would become “riskless.” This process results in the creation of a replicating portfolio whose cost cannot be that different from the price of the original asset. Thus, a hedge will transfer unwanted risks to other parties but, at the same time, will provide a way to price the original asset.3  

Pricing theory is also useful for the creation of “new products.” A new product is basically a series of contingent cash flows. We would, first, put together a combination of financial instruments that have the same cash flows. Then, we would write a separate contract and sell these cash flows to others under a new name. For example, a strip of FRAs or futures can be purchased and resulting cash flows are then labeled a swap and sold to others. The new product is, in fact, a dynamically maintained portfolio of existing instruments, and its fair cost will equal the sum of the price of its constituents.  

# 12.3 THE FRAMEWORK  

The pricing framework that we use emphasizes important aspects of the theory within a real-world setting. We assume that $m$ liquid asset prices are observed at times $t_{i}.$ , $i=1$ , 2, . . . The time $t_{i}$ price of the kth asset is denoted by $S_{k t_{i}}$ . The latter can represent credit, stocks, fixed-income instruments, the corresponding derivatives, or commodity prices.  

In theory, a typical $S_{k t_{i}}$ can assume any real value. This makes the number of possible values infinite and uncountable. But in practice, every price is quoted to a small number of decimal places and, hence, has a countable number of possible future values. FX rates, for example, are in general quoted to four decimal places. This brings us to the next important notion that we would like to introduce.  

# 12.3.1 STATES OF THE WORLD  

Let $t_{0}$ denote the “present,” and consider the kth asset price $S_{k T},$ at a future date, $T=t_{i}$ , for some $0<i$ . At time $t_{0}$ , $S_{k T}$ will be a random variable.4 Let the symbol $\omega^{j}$ , with $j=1,...,n$ represent time $T$ states of the world that relate to the random variable $S_{k T}$ .5 We assume that $n\leq m$ , which amounts to saying that there are at least as many liquid assets as there are time $T$ states of the world. For example, it is common practice in financial markets to assume a “bullish” state, a “bearish” state, and a “no-change” state. Traders expect prices in the future to be either “higher,” “lower,” or to “remain the same.” The $\omega^{j}$ generalizes this characterization and makes it operational.  

# EXAMPLE  

In this example, we construct the states of the world that relate to some asset whose time $t_{i}$ price is denoted by $S_{t_{i}}$ . Without any loss of generality, let  

$$
S_{t_{0}}=100
$$  

Suppose, at a future date $T.$ , with $t_{n}=T$ , there are only $n=4$ states of the world. We consider the task of defining these states.  

1. Set the value of some grid parameter $\Delta S$ to assign neighboring values of $S_{T}$ into a single state. For example, let  

$$
\Delta S=2
$$  

2. Next, pick two upper and lower bounds $[S^{\mathrm{min}},S^{\mathrm{max}}]$ such that the probability of $S_{T}$ being outside this interval is relatively small and that excursions outside this range can safely be ignored. For example, let $S^{\mathrm{max}}=104$ and $S^{\mathrm{min}}=96$ . Accordingly, the events $104<S_{T}$ and $S_{T}{<}96$ are considered unlikely to occur, and, hence, a detailed breakdown of these states of the world is not needed. Clearly, the choice of numerical values for $[S^{\mathrm{min}},S^{\mathrm{max}}]$ depends, among other things, on the perceived volatility of $S_{t}$ during the period $[t_{0},T]$ .6  

3. The states of the world can then be defined in the following fashion:  

$$
\omega^{1}=\{S_{T}\ \mathrm{such\that}\ S_{T}<S^{\mathrm{min}}\}
$$  

$$
\omega^{2}=\{S_{T}\ \mathrm{such\that}\ S_{T}\in[S^{\mathrm{min}},S^{\mathrm{min}}+\Delta S]\}
$$  

$$
\omega^{3}=\{S_{T}\mathrm{\such\that{}}S_{T}\in[S^{\mathrm{min}}+\Delta S,S^{\mathrm{min}}+2\Delta S=S^{\mathrm{max}}]\}
$$  

$$
\omega^{4}=\{S_{T}\ \mathrm{such\that\}S^{\mathrm{max}}<S_{T}\}
$$  

This situation is shown in Figure 12.1.  

![](48fbbc19f6ec626ecaa49e16afbf07a23001564ad062731acf78f2b72ef6d211.jpg)  

# FIGURE 12.1  

States of the world and asset values.  

Here, the total number of states of the world depends on the size of the grid parameter $\Delta S$ , and on the choice of upper and lower bounds $[S^{\mathrm{min}},S^{\mathrm{max}}]$ . These, in turn, depend on market psychology at time $t_{0}$ . For example, selecting the total number of states as $n=4$ could be justified, if the ranges for $S_{T}$ shown here were the only ones found relevant for pricing and risk-management problems faced during that particular day. If a problem under consideration requires a finer or coarser subdivision of the future, the value for $n$ would change accordingly.  

# 12.3.2 THE PAYOFF MATRIX  

The next step in obtaining the fundamental theorem of asset pricing is the definition of a payoff matrix for period $T.$ . Time $T$ values of the assets, $S_{k t}$ , depend on the state of the world, $\omega^{i}$ that will occur at time $T.$ Given that we are working with a finite number of states of the world, possible values for these assets would be easy to list. Let $z_{k}^{i}$ represent the value assumed by the kth asset in state $\omega^{i}$ , at time $T_{\mathbf{\delta}}$ :  

$$
S_{k T}^{i}=z_{k}^{i}
$$  

Then, for the first $n$ assets, $n\leq m$ , we can form the following payoff matrix for time $T$ :  

$$
D={\binom{z_{1}^{1}\quad\dots\quad z_{1}^{n}}{z_{n}^{1}}}
$$  

A typical row of this matrix would represent possible values of a particular asset in different states of the world. A typical column represents different asset prices, in a particular state of the world. The definition of $\omega^{i}$ should automatically lead to a definition of the possible values for assets under consideration, as shown in the previous example.  

The fundamental theorem of asset pricing is about how “current” asset prices, $S_{k t}$ , relate to the possible values represented by matrix $D$ . We form a matrix equation that will play an important role in the next three chapters.  

# 12.3.3 THE FUNDAMENTAL THEOREM  

Consider the linear system of equations defined for a series of $\boldsymbol{Q}^{i}$ , indexed by the state of the world $i$ :  

$$
{\binom{S_{1t_{0}}}{\dots}}={\binom{z_{1}^{1}}{\dots}}\quad\dots\quad z_{1}^{n}\biggr)\quad{\binom{Q^{1}}{\dots}}
$$  

The left-hand side shows the vector of current liquid asset prices observed at time $t_{0}$ . The righthand side has two components. The first is the matrix $D$ of possible values for these prices at time $T$ , and the second is a vector of constants, $\{Q^{1},...,Q^{n}\}$ . The fundamental theorem of asset pricing concerns this matrix equation and the properties of the $\{Q^{i}\}$ . The theorem can be stated heuristically as follows:  

Theorem: The time $t_{0}$ prices for the $\{S_{k t_{0}}\}$ are arbitrage-free if and only if $\{Q^{i}\}$ exist and are positive.  

Thus, the theorem actually works both ways. If $S_{k t_{0}}$ are arbitrage-free, then $\boldsymbol{Q}^{i}$ exist and are all positive. If $\boldsymbol{Q}^{i}$ exist and are positive, then $S_{k t_{0}}$ are arbitrage-free.  

The fundamental theorem of asset pricing provides a unified pricing tool for pricing real-world assets. In the remaining part of this chapter, we derive important implications of this theorem. These can be regarded as corollaries that are exploited routinely in asset pricing. The first of these corollaries is the existence of synthetic probabilities. However, before we discuss these results we need to motivate the $\{\boldsymbol{Q}^{i}\}$ and show why the theorem holds.  

# 12.3.4 DEFINITION OF AN ARBITRAGE OPPORTUNITY  

What is meant by arbitrage-free prices? To answer this question we need to define arbitrage opportunity formally. Formal definition of the framework outlined in this section provides this. Consider the asset prices $S_{1t},...,S_{k t}.$ . Associate the portfolio weights $\theta_{i}$ with asset $S_{i t}$ . Then we say that there is an arbitrage opportunity if either of the following two conditions hold.  

1. A portfolio with weights $\theta_{i}$ can be found such that:  

$$
\sum_{i=1}^{k}\theta_{i}S_{i t}=0
$$  

simultaneously with  

$$
0\leq\sum_{i=1}^{k}\theta_{i}S_{i T}
$$  

According to these conditions, the market practitioner advances no cash at time $t$ to form the portfolio, but still has access to some non-zero gains at time $T.$ This is the first type of arbitrage opportunity.  

2. A portfolio with weights $\theta_{i}$ can be found such that:  

$$
\sum_{i=1}^{k}\theta_{i}S_{i t}\leq0
$$  

simultaneously with  

$$
\sum_{i=1}^{k}\theta_{i}S_{i T}=0
$$  

In this case, the market practitioner receives cash at time $t$ while forming the portfolio, but has no liabilities at time $T$ .  

It is clear that in either case, the size of these arbitrage portfolios is arbitrary since no liabilities are incurred. The formal definition of arbitrage-free prices requires that such portfolios not be feasible at the “current” prices $\{S_{i t}\}$ .  

Note that what market professionals call an arbitrage strategy is very different from this formal definition of arbitrage opportunity. In general, when practitioners talk about “arb” they mean positions that have a relatively small probability of losing money. Clearly this violates both of the conditions mentioned above. The methods introduced in this chapter deal with the lack of formal arbitrage opportunities and not with the market practitioners’ arbitrage strategies. It should be remembered that it is the formal no-arbitrage condition that provides the important tools used in pricing and risk management.  

# 12.3.5 INTERPRETING THE $\pmb{Q}^{\prime}$ : STATE PRICES  

Given the states of the world $\omega^{i},i=1,...,n.$ , we can write the preceding matrix equation for the special case of two important sets of instruments that are essential to understanding arbitrage-free  

pricing. Suppose the first asset $S_{1t}$ is a risk-free savings deposit account and assume, without any loss of generality, that $t_{i}$ represents years.7 If 1 dollar is deposited at time $t_{0}.$ , $\left(1+r_{t_{0}}\right)$ can be earned at time $t_{1}$ without any risk of default. The $r_{t_{0}}$ is the rate that is observed as of time $t_{0}$ .  

The second set of instruments are elementary insurance contracts. We denote them by $C_{i}$ . These contracts are defined in the following way:  

$C_{1}$ pays $\$1$ at time $T$ if $\omega^{1}$ occurs. Otherwise it pays zero.   
$C_{n}$ pays $\$1$ at time $T$ if $\omega^{n}$ occurs. Otherwise it pays zero.  

If a market practitioner considers state $\omega^{i}$ as “risky,” he or she can buy a desired number of $C_{i}$ ’s as insurance to guarantee any needed cash flow in that state.  

Suppose now that all $C_{i}$ are actively traded at time $t_{0}$ . Then, according to the matrix equation, the correct arbitrage-free prices of these contracts are given by $\boldsymbol{Q}^{i}$ . This is the case since plugging the current prices of the savings account and the $C_{i}$ at time $t_{0}$ into the matrix equation (12.9) gives8  

$$
\begin{array}{r}{\left[\begin{array}{c}{1}\\ {C_{1}}\\ {\cdots}\\ {C_{n}}\end{array}\right]=\left[\begin{array}{c c c c c}{\left(1+r_{t_{0}}\right)}&{\cdots}&{\cdots}&{\left(1+r_{t_{0}}\right)}\\ {1}&{0}&{\cdots}&{0}\\ {\cdots}&{\cdots}&{\cdots}&{\cdots}\\ {0}&{\cdots}&{0}&{1}\end{array}\right]\left[\begin{array}{c}{Q^{1}}\\ {\cdots}\\ {Q^{n}}\end{array}\right]}\end{array}
$$  

Following from this matrix equation, $\boldsymbol{Q}^{i}$ have three important properties. First, we see that they are equal to the prices of the elementary insurance contracts:  

$$
C_{i}=Q^{i}
$$  

It is for this reason that $\boldsymbol{Q}^{i}$ are also called state prices. Second, we can show that if interest rates are positive, the sum of the time $t_{0}$ prices of $C_{i}$ is less than one. Consider the following: a portfolio that consists of buying one of each insurance contract $C_{i}$ at time $t_{0}$ will guarantee 1 dollar at time $t_{0}$ no matter which state, $\omega^{i}$ , is realized at time $T$ . But, a guaranteed future dollar should be worth less than a current dollar at hand, as long as interest rates are positive. This means that the sum of $\boldsymbol{Q}^{i}$ paid for the elementary contracts at time $t_{0}$ should satisfy  

$$
Q^{1}+Q^{2}+\cdots+Q^{n}<1
$$  

From the first row of the matrix equation in Eq. (12.14), we can write  

$$
\sum_{i=1}^{n}{\cal Q}^{i}\big(1+r_{t_{0}}\big)=1
$$  

After rearranging,  

$$
\mathcal{Q}^{1}+\mathcal{Q}^{2}+\cdots+\mathcal{Q}^{n}=\frac{1}{\left(1+r_{t_{0}}\right)}
$$  

The third property is a little harder to see. As the fundamental theorem states, none of the $Q^{i}$ can be negative or zero if $C_{i}$ are indeed arbitrage-free. We show this with a simple counter example.  

# EXAMPLE  

Suppose we have $n=4$ and that the first elementary contract has a negative price, $C_{1}=-1$ . Without any loss of generality, suppose all other elementary insurance contracts have a positive price. Then the portfolio  

has zero cost at time $t_{0}$ and yet will guarantee a positive return at time $t_{1}$ . More precisely, the portfolio returns 1 dollar in states 2 4 and $(Q^{\bar{2}}+Q^{3}+Q^{4})$ dollars in state 1.  

Hence, as long as one or more of the $\boldsymbol{Q}^{i}$ are negative, there will always be an arbitrage opportunity. A trader can “buy” the contract(s) with a negative price and use the cash generated to purchase the other contracts. This way, a positive return at $T$ is guaranteed, while at the same time the zero-cost structure of the initial portfolio is maintained. For such arbitrage opportunities not to exist, we need $0<Q^{i}$ for all $i.$ .  

# 12.3.5.1 Remarks  

Before going further, we ask two questions that may have already troubled the reader given the financial engineering approach we adopted in this book.  

Do insurance contracts such as $C_{i}$ exist in the real world? Are they actively traded? • Is the assumption of a small finite number of states of the world realistic? How can such a restrictive view of the future be useful in pricing real-world instruments?  

In the next few sections, we will show that the answer to both of these questions is a qualified yes. To understand this, we need to relate the elementary insurance contracts to the concept of options. Options can be considered as ways of trading baskets of $C_{i}$ ’s. A typical $C_{i}$ pays 1 dollar if state $i$ occurs and nothing in all other states. Thus, it is clear that option payoffs at expiration are different from those of elementary contracts. Options pay nothing if they expire out-of-the-money, but they pay, $(S_{T}-K)$ if they expire in-the-money. This means that depending on how we define the states $\omega^{i}$ , unlike the elementary contracts, options can make payments in more than one state. But this difference is really not that important since we can get all desired $C_{i}$ from option prices, if options trade for all strikes $K$ . In other words, the pricing framework that we are discussing here will be much more useful in practice than it seems at first.  

As to the second question, it has to be said that, in practice, few strikes of an option series trade actively. This suggests that the finite state assumption may not be that unrealistic after all.  

# 12.4 AN APPLICATION  

The framework based on state prices and elementary insurance contracts is a surprisingly potent and realistic pricing tool. Before going any further and obtaining more results from the  

fundamental theorem of asset pricing, we prefer to provide a real-world example. The following reading deals with the S&P500 index and its associated options.  

# EXAMPLE  

The S&P500 is an index of 500 leading stocks from the United States. It is closely monitored by market participants and traded in futures markets. One can buy and sell liquid options written on the S&P500 at the Chicago Board of Options Exchange (CBOE). These options with an expiration date of December 2001 are shown in Table 11.1 as they were quoted on August 10, 2001.  

At the time these data were gathered, the index was at 1187. The three most liquid call options are  

$$
\{1275-\mathrm{Call},1200-\mathrm{Call},1350-\mathrm{Call}\}
$$  

The three most liquid put options, on the other hand, are  

$$
\{1200-\mathrm{Put},1050-\mathrm{Put},900-\mathrm{Put}\}
$$  

Not surprisingly, all the liquid options are out-of-the-money as liquid options generally are.9  

We will now show how this information can be used to obtain (i) the states of the world $\omega^{i}.$ , (ii) the state prices $\boldsymbol{Q}^{i}$ , and (iii) the corresponding synthetic probabilities associated with $\boldsymbol{Q}^{i}$ . We will do this in the simple setting used thus far.  

# 12.4.1 OBTAINING THE $\omega^{I}$  

A financial engineer always operates in response to a particular kind of problem and the states of the world to be defined relative to the needs, at that time. In our present example we are working with S&P500 options, which means that the focus is on equity markets. Hence, the corresponding states of the world would relate to different states in which the US stock market might be at a future date. Also, we need to take into account that trader behavior singles out a relatively small number of liquid options with expirations of about 3 months. For the following example, refer to Table 12.1.  

<html><body><table><tr><td colspan="6"> Table 12.1 S&P500 Option Quotes</td></tr><tr><td>Calls</td><td>Last Sale</td><td>Bid</td><td>Ask</td><td>Volume</td><td>Open Interest</td></tr><tr><td>Dec 1175</td><td>67.1</td><td>68</td><td>70</td><td>51</td><td>1378</td></tr><tr><td>Dec 1200</td><td>46.5</td><td>52.8</td><td>54.8</td><td>150</td><td>8570</td></tr><tr><td>Dec 1225</td><td>41</td><td>40.3</td><td>42.3</td><td>1</td><td>6792</td></tr><tr><td>Dec 1250</td><td>28.5</td><td>29.6</td><td>31.6</td><td>0</td><td>11,873</td></tr><tr><td>Dec 1275</td><td>22.8</td><td>21.3</td><td>23.3</td><td>201</td><td>6979</td></tr><tr><td>Dec 1300</td><td>15.8</td><td>15</td><td>16.2</td><td>34</td><td>16,362</td></tr><tr><td>Dec 1325</td><td>9.5</td><td>10</td><td>11</td><td>0</td><td>9281</td></tr><tr><td>Dec 1350</td><td>6.8</td><td>6.3</td><td>7.3</td><td>125</td><td>8916</td></tr><tr><td>Dec 1375</td><td>4.1</td><td>4</td><td>4.7</td><td>0</td><td>2818</td></tr><tr><td>Dec 1400</td><td>2.5</td><td>2.5</td><td>3.2</td><td>10</td><td>17,730</td></tr><tr><td>Dec 1425</td><td>1.4</td><td>1.4</td><td>1.85</td><td>0</td><td>4464</td></tr><tr><td>Dec 1450</td><td>0.9</td><td>0.8</td><td>1.25</td><td>9</td><td>9383</td></tr><tr><td>Dec 1475</td><td>0.5</td><td>0.35</td><td>0.8</td><td>0</td><td>122</td></tr><tr><td> Puts</td><td>Last Sale</td><td>Bid</td><td>Ask</td><td>Volume</td><td>Open Interest</td></tr><tr><td>Dec 800</td><td>1.65</td><td>1.2</td><td>1.65</td><td>10</td><td>1214</td></tr><tr><td>Dec 900</td><td>4.3</td><td>3.4</td><td>4.1</td><td>24</td><td>11,449</td></tr><tr><td>Dec 950</td><td>5.4</td><td>5.3</td><td>6.3</td><td>10</td><td>8349</td></tr><tr><td>Dec 995</td><td>10.1</td><td>8.5</td><td>9.5</td><td>0</td><td>11,836</td></tr><tr><td>Dec 1025</td><td>13</td><td>11.1</td><td>12.6</td><td>11</td><td>5614</td></tr><tr><td>Dec 1050</td><td>13.6</td><td>14</td><td>15.5</td><td>106</td><td>19,483</td></tr><tr><td>Dec 1060</td><td>16.5</td><td>15.7</td><td>17.2</td><td>1</td><td>1597</td></tr><tr><td>Dec 1075</td><td>22.5</td><td>18</td><td>19.5</td><td>1</td><td>316</td></tr><tr><td>Dec 1100</td><td>26</td><td>22.7</td><td>24.7</td><td>0</td><td>17,947</td></tr><tr><td>Dec 1150</td><td>39</td><td>35.3</td><td>37.3</td><td>2</td><td>16,587</td></tr><tr><td>Dec 1175</td><td>44</td><td>44.1</td><td>46.1</td><td>14</td><td>4897</td></tr><tr><td>Dec 1200</td><td>53</td><td>53.9</td><td>55.9</td><td>897</td><td>26,949</td></tr></table></body></html>  

# EXAMPLE  

We let $S_{T}$ represent the value of the S&P500 at expiration and then use the strike prices $K_{i}$ of the liquid options to define the future states of the world. In fact, strike prices of puts and calls discussed in the preceding example divide the $S_{T}$ axis into intervals of equal length. But only a handful of these options are liquid, implying that fine subdivisions were perhaps not needed by the markets for that day and that particular expiration. Accordingly, we can use the strike prices of the three liquid out-of-the-money puts to obtain the intervals  

$$
\omega^{1}=S_{T}<900
$$  

$$
\omega^{2}=900\leq S_{T}<1050
$$  

$$
\omega^{3}=1050\leq S_{T}<1200
$$  

Note that the liquid puts lead to intervals of equal length. It is interesting, but also expected, that the liquid options have this kind of regularity in their strikes. Next, we use the three out-of-the-money calls to get three intervals to define three additional states of the world as  

$$
\begin{array}{c}{\omega^{4}=1200\leq S_{T}<1275}\\ {\omega^{5}=1275\leq S_{T}<1350}\\ {\omega^{6}=1350\leq S_{T}}\end{array}
$$  

Here, the last interval is obtained from the highest strike liquid call option. Figure 12.2 shows these options and the implied intervals. Since these intervals relate to future values of $S_{T},$ , we consider them the relevant states of the world for $S_{T}$ .  

We pick the midpoint of the bounded intervals as an approximation to that particular state. Let these midpoints be denoted by $\{{\overline{{S}}}^{i},i=2,...,5\}$ . These midpoints can then be used as a finite set of points that represent $\omega^{i}$ . For the first and last half-open intervals, we select the values of the two extreme points, $\overline{{S}}^{1}$ , and $\overline{{S}}^{6}$ , arbitrarily for the time being. We let  

$$
\overline{{\boldsymbol{S}}}^{1}=75\boldsymbol{0}
$$  

![](8cabb2920b55b45aa01ab28c3389370a2db8c1147032dc87645e37503b4c1e4a.jpg)  

# FIGURE 12.2  

Option payoffs and states of the world.  

$$
\overline{{S}}^{6}=1400
$$  

so that the distance between $\mathit{\overline{{S}}^{i}}$ remains constant. This arbitrary selection of the “end states” is clearly unsatisfactory. In fact, by doing this we are in a sense setting the volatility of the random variables arbitrarily. We can, however, calibrate our selection. Once our educated guesses are plugged in, we can try to adjust these extreme values so that the resulting $Q^{i}$ all become positive and price some other liquid asset correctly. In a sense, calibration is an attempt to see which value of the two “end states” replicates the observed prices. But for the time being, we ignore this issue and assume that the end points are selected correctly.  

It is open to debate if selecting just six states of the world, as in the example, might represent future possibilities concerning $S_{T}$ accurately. Traders dealing with the risk in the example must have thought so, since on that particular date trading approximately six liquid options was sufficient to resolve their tasks. It seems that if a finer subdivision of the future possibilities were more appropriate, then more liquid strikes would have been traded.  

Hence, as usual in financial engineering, the specific values of $\omega^{i}$ that we select are based on the values of liquid instruments. In our case, the possible states of the world were chosen as dictated by liquid call and put options.  

# 12.4.2 ELEMENTARY CONTRACTS AND OPTIONS  

Elementary insurance contracts $C_{i}$ do not trade directly in world financial markets. Yet, $C_{i}$ are not far from a well-known instrument class—options—and they trade “indirectly.” This section shows how elementary insurance contracts can be obtained from options, and vice versa. Plain vanilla options are, in fact, close relatives of elementary insurance contracts. The best way to see this is to consider a numerical example. (Generalizations are straightforward.)  

# EXAMPLE  

Start with the first and last options selected for the previous example. Note that the 900-put is equivalent to $K_{1}-\overline{{S}}^{1}$ units of $C_{1}$ because it pays approximately this many dollars if state $\upomega_{1}$ occurs and nothing in all other states. Similarly, the 1350-call is equivalent to $\overline{{S}}^{6}-K_{6}$ units of $C_{6}$ because it pays approximately this many dollars if state 6 occurs and nothing otherwise.  

The other calls and puts have payoffs in more than one state, but they also relate to elementary contracts in straightforward ways. For example, the 1050-put is equivalent to a portfolio of two elementary insurance contracts, $K_{2}-\overline{{S}}^{1}$ units of $\mathbf{C}_{1}$ and $K_{2}-\overline{{S}}^{2}$ units of $\mathbf{C}_{2}$ , because it makes these payments in states 1 and 2, respectively, and nothing else in other states. In fact, pursuing this reasoning, we can obtain the following matrix equation between the payoffs of elementary contracts $\mathbf{C}_{1},\hdots.$ , $\mathrm{C}_{6}$ and the option prices:  

$$
\left[\begin{array}{c}{900-\mathrm{Put}}\\ {1050-\mathrm{Put}}\\ {1200-\mathrm{Put}}\\ {120-\mathrm{Call}}\\ {1275-\mathrm{Call}}\\ {1350-\mathrm{Call}}\end{array}\right]=\left[\begin{array}{c c c c c c c}{z_{1}^{1}}&{0}&{0}&{0}&{0}&{0}\\ {z_{2}^{1}}&{z_{2}^{2}}&{0}&{0}&{0}&{0}\\ {z_{3}^{1}}&{z_{3}^{2}}&{z_{3}^{3}}&{0}&{0}&{0}\\ {0}&{0}&{0}&{z_{4}^{4}}&{z_{4}^{5}}&{z_{4}^{6}}\\ {0}&{0}&{0}&{0}&{z_{5}^{5}}&{z_{5}^{6}}\\ {0}&{0}&{0}&{0}&{0}&{z_{6}^{6}}\end{array}\right]\left[\begin{array}{c}{C_{1}}\\ {C_{2}}\\ {C_{3}}\\ {C_{4}}\\ {C_{5}}\\ {C_{6}}\end{array}\right]
$$  

This equation holds since we have  

$$
Q^{i}=C_{i}
$$  

for all i.10  

Thus, given the arbitrage-free values of traded puts and calls with different strikes but similar in every other aspect, we can easily obtain the values of the elementary insurance contracts $C_{i}$ by inverting the $(6\times6)$ matrix on the right side. In fact, it is interesting to see that the matrix equation in the example contains two triangular subsystems that can be solved separately and recursively.  

Hence, the existence of liquid options makes a direct application of the fundamental theorem of asset pricing possible. Given a large enough number of liquid option contracts, we can obtain the state prices, $\boldsymbol{Q}^{i}$ , if these exist, and, if they are all positive, use them to price other illiquid assets that depend on the same risk.11 Obviously, when traders deal with interest rate, or exchange rate risk, or when they are interested in pricing contracts on commodities, they would use liquid options for those particular sectors and work with different definitions of the state of the world.  

# 12.4.3 ELEMENTARY CONTRACTS AND REPLICATION  

We now show how elementary insurance contracts and options that belong to a series can be used in replicating instruments with arbitrary payoffs. Consider an arbitrary financial asset, $S_{t}$ , that is worth $z_{T}^{i}$ in state of the world $\omega^{i}$ , $i=1,...,n$ , at time $T.$ Given $n$ elementary insurance contracts $C_{i}$ , we can immediately form a replicating portfolio for this asset. Assuming, without any loss of generality, that the time $T$ payoffs of the $S_{t}$ asset are denoted by $0<z_{T}^{i}$ , we can consider buying the following portfolio:  

$$
\{z_{T}^{1}\mathrm{units~of}C_{1},z_{T}^{2}\mathrm{units~of}C_{2},...,z_{T}^{n}\mathrm{units~of}C_{n}\}
$$  

At time $T$ , this portfolio should be worth exactly the same as $S_{t},$ since whatever state occurs, the basket of insurance contracts will make the same time $T$ payoff as the original asset. This provides  

an immediate synthetic for $S_{t}$ . Accordingly, if there are no-arbitrage opportunities, the value of the portfolio and the value of $S_{t}$ will be identical as of time $t$ as well.12 We consider an example.  

# EXAMPLE  

Take any four independent assets $S_{k t},k=1,...,4$ with different payoffs, $z_{k}^{i}$ , in the states $\{\omega^{i},i=1,...,4\}$ . We can express each one of these assets in terms of the elementary insurance contracts. In other words, we can find one synthetic for each $S_{k t}$ by purchasing the portfolios:  

$$
\{z_{k}^{1}\mathrm{unit~of~}C_{1},z_{k}^{2}\mathrm{unit~of~}C_{2},z_{k}^{3}\mathrm{unit~of~}C_{3},z_{k}^{4}\mathrm{unit~of~}C_{4}\}
$$  

Putting these in matrix form, we see that arbitrage-free values, $S_{k t_{0}}$ , of these assets at time $t_{0}$ have to satisfy the matrix equation:  

$$
\left[\begin{array}{c}{1}\\ {S_{1t_{0}}}\\ {S_{2t_{0}}}\\ {S_{3t_{0}}}\\ {S_{4t_{0}}}\end{array}\right]=\left[\begin{array}{c c c c c}{1+r_{t_{0}}}&{1+r_{t_{0}}}&{1+r_{t_{0}}}&{1+r_{t_{0}}}\\ {z_{1}^{1}}&{z_{1}^{2}}&{z_{1}^{3}}&{z_{1}^{4}}\\ {z_{2}^{1}}&{z_{2}^{2}}&{z_{2}^{3}}&{z_{2}^{4}}\\ {z_{3}^{1}}&{z_{3}^{2}}&{z_{3}^{3}}&{z_{3}^{4}}\\ {z_{4}^{1}}&{z_{4}^{2}}&{z_{4}^{3}}&{z_{4}^{4}}\end{array}\right]\left[\begin{array}{c}{Q^{1}}\\ {Q^{2}}\\ {Q^{3}}\\ {Q^{4}}\end{array}\right]
$$  

where the matrix on the right-hand side contains all possible values of the assets $S_{k t}$ in states $\omega^{i}$ , at time $T$ .13  

Hence, given the prices of actively traded elementary contracts $C_{i},$ we can easily calculate the time $t$ cost of forming the portfolio:  

$$
\mathrm{Cost}=C_{1}z_{T}^{1}+C_{2}z_{T}^{2}+\cdots+C_{n}z_{T}^{n}
$$  

This can be regarded as the cost basis for the $S_{t}$ asset. Adding a proper margin to it will give the fair market price $S_{t}.$  

# EXAMPLE  

Suppose the $S_{t}$ asset has the following payoffs in the states of the world $i=1,...,4$ :  

$$
\{z_{T}^{1}=10,z_{T}^{2}=1,z_{T}^{2}=14,z_{T}^{2}=16\}
$$  

Then, buying 10 units of the first insurance contract $C_{1}$ will guarantee the 10 in the first state, and so on.  

Suppose we observe the following prices for the elementary insurance contracts:  

$$
C_{1}=0.3,C_{2}=0.2,C_{3}=0.4,C_{4}=0.07
$$  

Then the total cost of the insurance contracts purchased will be  

$$
\begin{array}{c}{{\mathrm{Cost}=(0.3)10+(0.2)(1)+(0.4)14+(0.07)16}}\\ {{{}}}\\ {{=9.92}}\end{array}
$$  

This should equal the current price of $S_{t}$ once a proper profit margin is added.  

Clearly, if such elementary insurance contracts actively traded in financial markets, the job of a financial engineer would be greatly simplified. It would be straightforward to construct synthetics for any asset, and then price them using the cost of the replicating portfolios as shown in the example. However, there is a close connection between $C_{i}$ and options of the same series that differ only in their strikes. We saw how to obtain $C_{i}$ from liquid option prices. Accordingly, if options with a broad array of strikes trade in financial markets, then traders can create static replicating portfolios for assets with arbitrary payoffs.14  

# 12.5 IMPLICATIONS OF THE FUNDAMENTAL THEOREM  

The fundamental theorem of asset pricing has a number of implications that play a critical role in financial engineering and derivatives pricing. First, using this theorem we can obtain probability distributions that can be used in asset pricing. These probability distributions will be objective and operational. Second, the theorem leads to the so-called Martingale representation of asset prices. Such a representation is useful in modeling asset price dynamics. Third, we will see that the Martingale representation can serve to objectively set expected asset returns. This property eliminates the need to model and estimate the “drift factors” in asset price dynamics. We will now study these issues in more detail.  

# 12.5.1 RESULT 1: RISK-ADJUSTED PROBABILITIES  

$\boldsymbol{Q}^{i}$ introduced in the previous section can be modified judiciously in order to obtain convenient probability distributions that the financial engineer can work with. These distributions do not provide real-world odds on the states of the world $\omega^{i}$ , and hence cannot be used directly in econometric prediction. Yet they do yield correct arbitrage-free prices. (This section shows how.) But there is more. As there are many such distributions, the market practitioner can also choose the distribution that fits his/her current needs best. How to makes this choice is discussed in the next section.  

# 12.5.1.1 Risk-neutral probabilities  

Using the state prices $\boldsymbol{Q}^{i}$ , we first obtain the so-called risk-neutral probability distribution. Consider the first row of the matrix equation (12.9). Assume that it represents the savings account.15  

$$
\big(1+r_{t_{0}}\big)Q^{1}+\cdots+\big(1+r_{t_{0}}\big)Q^{n}=1
$$  

Relabel, using  

$$
\tilde{p}_{i}=\left(1+r_{t_{0}}\right)Q^{i}
$$  

According to Eq. (12.40), we have  

$$
{\tilde{p}}_{i}+\dots+{\tilde{p}}_{n}=1
$$  

where  

$$
0<\tilde{p}_{i}
$$  

since each $\boldsymbol{Q}^{i}$ is positive. This implies that the numbers $\tilde{p}_{i}$ have the properties of a discrete probability distribution. They are positive and they add up to one. Since they are determined by the markets, we call them “risk-adjusted” probabilities. They are, in fact, obtained as linear combinations of $n$ current asset prices. This particular set of synthetic probabilities is referred to as the riskneutral probability distribution.  

To be more precise, the risk-neutral probabilities $\{\tilde{p}_{i}\}$ are time $t_{0}$ probabilities on the states that occur at time $T$ . Thus, if we wanted to be more exact, they would have to carry two more subscripts, $t_{0}$ and $T.$ Yet, these will be omitted for notational convenience and assumed to be understood by the reader.  

# 12.5.1.2 Other probabilities  

Several other synthetic probabilities can be generated, and these may turn out to be more useful than the risk-neutral probabilities. Given the positive $\boldsymbol{Q}^{i}$ , we can rescale these by any positive normalizing factor so that they can be interpreted as probabilities. There are many ways to proceed. In fact, as long as a current asset price $S_{k t_{0}}$ is nonzero and $z_{i}^{j}$ are positive, one can choose any kth row of the matrix equation in Eq. (12.9) to write and then define  

$$
1=\sum_{i=1}^{n}\frac{z_{k}^{i}}{S_{k t_{0}}}Q^{i}
$$  

and then define  

$$
\frac{z_{k}^{i}}{S_{k t_{0}}}Q^{i}=\tilde{p}_{i}^{k}
$$  

$\tilde{p}_{i}^{k},i=1,...,n,$ , can be interpreted as probabilities obtained after normalizing by the $S_{k t_{0}}$ asset. $\tilde{p}_{i}^{k}$ will be positive and will add up to one. Hence, they will have the characteristics of a probability distribution, but again they cannot be used in prediction since they are not the actual probabilities of a particular state of the world $\omega^{i}$ occurring. Clearly, for each nonzero $S_{k t_{0}}$ we can obtain a new probability $\tilde{p}_{i}^{k}$ . These will be different across states $\omega^{i}$ , as long as the time $T$ value of the asset is positive in all states.16  

It turns out that how we normalize a sequence of $\{Q^{i}\}$ in order to convert them into some synthetic probability is important. The special case, where  

$$
S_{k t_{0}}=B(t_{0},T)
$$  

$B(t_{0},T)$ being the current price of a $T_{\mathbf{\delta}}$ -maturity risk-free pure discount bond, is especially interesting. This yields the so-called $T_{\mathbf{\delta}}$ -forward measure. Because the discount bond matures at time $T_{\cdot}$ the time $T$ values of the asset are given by  

$$
z_{k}^{i}=1
$$  

for all $i.$ .  

Thus, we can simply divide state prices $\boldsymbol{Q}^{i}$ by the current price of a default-free discount bond maturing at time $t_{0}$ , and obtain the $T-$ -forward measure:  

$$
\tilde{p}_{i}^{T}=Q^{i}\frac{1}{B(t_{0},T)}
$$  

We will see in Chapter 14 that the $T$ -forward measure is the natural way to deal with payoffs associated with time $T.$ Let’s consider an example.  

# EXAMPLE  

Suppose short-term risk-free rates are $5\%$ and that there are four states of the world. We observe the following arbitrage-free bid prices for four assets at time $t_{0}$ :  

$$
S_{1t_{0}}=2.45238,S_{2t_{0}}=1.72238,S_{3t_{0}}=6.69429,S_{4t_{0}}=3.065
$$  

It is assumed that at time $T=t_{0}+1$ , measured in years, the four possible values for each asset will be given by the matrix:  

$$
\left[{\begin{array}{l l l l}{10}&{3}&{1}&{1}\\ {2}&{3}&{2}&{1}\\ {1}&{10}&{10}&{1}\\ {8}&{2}&{10}&{2}\end{array}}\right]
$$  

We can form the matrix equation and then solve for the corresponding $\boldsymbol{Q}^{i}$ :  

$$
\left[\begin{array}{l}{1}\\ {S_{1t_{0}}}\\ {S_{2t_{0}}}\\ {S_{3t_{0}}}\\ {S_{4t_{0}}}\end{array}\right]=\left[\begin{array}{l l l l l}{1+0.5}&{1+0.5}&{1+0.5}&{1+0.5}\\ {10}&{3}&{1}&{1}\\ {2}&{3}&{2}&{1}\\ {1}&{10}&{10}&{6}\\ {8}&{2}&{10}&{2}\end{array}\right]\left[\begin{array}{l}{Q^{1}}\\ {Q^{2}}\\ {Q^{3}}\\ {Q^{4}}\end{array}\right]
$$  

Using the first four rows of this system, we solve for $\boldsymbol{Q}^{i}$ :  

$$
Q^{1}=0.1,Q^{2}=0.3,Q^{3}=0.07,Q^{4}=0.482
$$  

Next, we obtain the risk-neutral probabilities by using  

$$
\tilde{p}_{i}=(1+0.5)Q^{i}
$$  

which gives  

$$
\tilde{p}_{1}=0.105,\tilde{p}_{2}=0.315,\tilde{p}_{3}=0.0735,\tilde{p}_{4}=0.5065
$$  

As a final point, note that we used the first four rows of the system shown here to determine the values of $\boldsymbol{Q}^{i}$ . However, the price of $S_{4t_{0}}$ is also arbitrage-free:  

$$
\sum_{i=1}^{4}Q^{i}S_{4T}^{i}=3.065
$$  

as required.  

Interestingly, for short-term instruments, and with “normal” short-term interest rates of around $3-5\%$ , the savings account normalization makes little difference. If $T-t_{0}$ is small, $\boldsymbol{Q}^{i}$ will be only marginally different from p\~i.17  

# 12.5.1.3 A remark  

Can derivatives be used for normalization? For example, instead of normalizing by a savings account or by using bonds, could we normalize with a swap? The answer is no. There are probabilities called swap measures, but the normalization that applies in these cases is not a swap, but an annuity. Most derivatives are not usable in the normalization process because normalization by an $S_{k t}$ implies, essentially, that the state prices $\boldsymbol{Q}^{i}$ are multiplied by factors such as  

$$
{\frac{z_{k}^{i}}{S_{k t}}}{\frac{S_{k t}}{z_{k}^{i}}}=1
$$  

and then grouped according to  

$$
\frac{z_{k}^{i}}{S_{k t}}\frac{S_{k t}}{z_{k}^{i}}Q^{i}=\frac{S_{k t}}{z_{k}^{i}}\tilde{p}_{i}^{k}
$$  

17 For example, at a $5\%$ short rate, a 1-month discount bond will sell for approximately  

$$
B(t_{0},t)={\frac{1}{1+0.5{\frac{1}{12}}}}=0.9958
$$  

so that dividing by this scale factor will not modify $\boldsymbol{Q}^{i}$ very much.  

But in this operation, both $z_{k}^{i}$ , $i=1,...,n$ and $S_{k t}$ should be nonzero. Otherwise the ratios would be undefined. This will be seen below.  

# 12.5.1.4 Swap measure  

The normalizations thus far used only one asset, $S_{k t}$ , in converting $\boldsymbol{Q}^{i}$ into probabilities $\tilde{p}^{k}$ . This need not be so. We can normalize using a linear combination of many assets, and sometimes this proves very useful. This is the case for the so-called swap, or annuity, measure. The swap measure is dealt with in Chapter 17.  

# 12.5.2 RESULT 2: MARTINGALE PROPERTY  

The fundamental theorem of asset pricing also provides a convenient model for pricing and riskmanagement purposes. All properly normalized asset prices have a Martingale property under a properly selected synthetic probability $\tilde{p}^{k}$ . Let $X_{t}$ be a stochastic process that has the following property:  

$$
X_{t}=E_{t}^{\tilde{p}^{k}}[X_{T}]\quad t<T
$$  

This essentially says that $X_{t}$ have no predictable trend for all $t.~X_{t}$ is referred to as a Martingale. To see how this can be applied to asset pricing theory, first choose the risk-neutral probability $\tilde{P}$ as the working probability distribution.  

# 12.5.2.1 Martingales under $\Tilde{\pmb{P}}$  

Consider any kth row in the matrix equation (12.9)  

$$
S_{k t_{0}}=(z_{k}^{1})Q^{1}+(z_{k}^{2})Q^{2}+\cdots+(z_{k}^{n})Q^{n}
$$  

Replace $\boldsymbol{Q}^{i}$ with the risk-neutral probabilities $\tilde{p}_{i}$ using  

$$
Q^{i}=\frac{1}{1+r_{t_{0}}}\tilde{p}_{i}
$$  

$r_{t_{0}}$ is the interest on a risk-free 1-year deposit.  

This gives  

$$
S_{k t_{0}}-{\frac{1}{1+r_{t_{0}}}}\left[z_{k}^{1}{\tilde{p}}_{1}+\dots+z_{k}^{n}{\tilde{p}}_{n}\right]
$$  

Here, the right-hand side is an average of the future values of $S_{k T},$ weighted by $\tilde{p}_{i}$ . Thus, bringing back the time subscripts, the current arbitrage-free price $S_{k t_{0}}$ satisfies  

$$
S_{k t_{0}}={\frac{1}{\left(1+r_{t_{0}}\right)}}E_{t_{0}}^{\tilde{p}}[s_{k T}]\quad t_{0}<T
$$  

In general terms, letting  

$$
X_{t}={\frac{\mathrm{time}\cdot t{\mathrm{~value~of~}}S_{k t}}{\mathrm{time}\cdot t{\mathrm{~value~of~the~savings~account}}}}
$$  

we see that asset values normalized by the savings deposit have the Martingale property:  

$$
X_{t}=E_{t}^{\tilde{p}}[X_{T}]\quad t<T
$$  

Thus, all tools associated with Martingales immediately become available to the financial engineer for pricing and risk management.  

# 12.5.2.2 Martingales under other probabilities  

The convenience of working with Martingales is not limited to the risk-neutral measure $\tilde{P}$ . A normalization with any non-zero price $S_{j t}$ will lead to another Martingale. Consider the same kth row of the matrix equation in Eq. (12.9)  

$$
S_{k t_{0}}=(z_{k}^{1})Q^{1}+\cdots+(z_{k}^{n})Q^{n}
$$  

This time, replace $\boldsymbol{Q}^{i}$ using $S_{j t_{0}},j\ne k$ , normalization:  

$$
\tilde{p}_{i}^{j}=Q^{1}\frac{z_{j}^{i}}{S_{j t_{0}}}
$$  

We obtain, assuming that the denominator elements are positive:  

$$
S_{k t_{0}}=s_{j t_{0}}\left[z_{k}^{1}\frac{1}{z_{j}^{1}}\tilde{p}_{1}^{j}+\dots+z_{k}^{n}\frac{1}{z_{j}^{n}}\tilde{p}_{n}^{j}\right]
$$  

this means that the ratio,  

$$
X_{t}=\frac{S_{k t}}{S_{j t}}
$$  

is a Martingale under $\tilde{P}^{j}$ measure:  

$$
X_{t}-E_{t}^{\tilde{p}^{j}}[X_{T}]\quad t<T
$$  

It is obvious that the probability associated with a particular Martingale is a function of the normalization that is chosen, and that the implied Martingale property can be exploited in pricing. By choosing a Martingale, the financial engineer is also choosing the probability that he or she will be working with. In the remainder of this chapter and in the next, we will see several examples of how Martingale properties can be utilized.  

# 12.5.3 RESULT 3: EXPECTED RETURNS  

The next implication of the fundamental theorem is useful in modeling arbitrage-free dynamics for asset prices. Every synthetic probability leads to a particular expected return for the asset prices under consideration. These expected returns will differ from the true (subjective) expectations of players in the markets, but because they are agreed upon by all market participants and are associated with arbitrage-free prices, they will be even more useful than the true expectations.  

We conduct the discussion in terms of the risk-neutral probability $\tilde{P}$ , but our conclusions are valid for all other $\tilde{p}^{k}$ . Consider again the Martingale property for an asset whose price is denoted by $S_{t},$ but this time reintroduce the day’s adjustment parameter $\delta$ , dropping the assumption that $t_{i}$ represents years. We can write, for some $0<\delta$ ,  

$$
S_{t}=\frac{1}{(1+r_{t}\delta)}E_{t}^{\tilde{P}}[S_{t+\delta}]
$$  

Rearrange to obtain  

$$
(1+r_{t}\delta)=E_{t}^{\tilde{P}}\left[\frac{S_{t+\delta}}{S_{t}}\right]
$$  

According to this expression, under the probability $\tilde{P}$ , expected net annual returns for all liquid assets will equal $\boldsymbol{r}_{t},$ the risk-free rate observed at time $t$ .  

Similar results concerning the expected returns of the assets are obtained under other probabilities $\tilde{p}^{k}$ . The expected returns will be different under different probabilities. Market practitioners can select the working probability so as to set the expected return of the asset to a desired number.18  

In Chapter 14, we will see more complicated applications of this idea using time $T$ forward measures. There, the expected change in the forward rates is set equal to zero by a judicious choice of probabilities.  

# 12.5.3.1 Martingales and risk premia  

Let us see how the use of Martingales “internalizes” the risk premia associated with nondiversifiable market risks. Let $X_{t},t\in[t_{0},T]$ be a risky asset and $\Delta>0$ be a small time interval. The annualized gross return of $X_{t}$ as expected by players at time $t$ is defined by  

$$
1+\hat{R}_{t}\Delta=E_{t}^{P}\left[\frac{X_{t+\Delta}}{X_{t}}\right]
$$  

where $P$ represents the real-world probability used by market participants in setting up their expectation. Since this is an actual market expectation, the gross return will contain a risk premium:  

$$
\hat{R_{t}}=r_{t}=\mu_{t}
$$  

where $\boldsymbol{r}_{t}$ is the risk-free rate and $\mu_{t}$ is the risk premium commanded by the risky asset.19 Putting these together, we have  

$$
(1+r_{t}\Delta+\mu_{t}\Delta)=E_{t}^{P}\left[\frac{X_{t+\Delta}}{X_{t}}\right]
$$  

or  

$$
X_{t}=\frac{1}{(1+r_{t}\Delta+\mu_{t}\Delta)}=E_{t}^{P}[X_{t+\Delta}]
$$  

This equality states that the asset price $X_{t+\Delta}$ discounted by the factor $(1+r_{t}\Delta+\mu_{t}\Delta)$ is a Martingale only if we use the probability $P$ . Note that in this setup there are two unknowns: (i) the risk premium $\mu_{t}$ and (ii) the real-world probability $P.$ Future cash flows accordingly need to be discounted by subjective discount factors and real-world probabilities need to be estimated. The pricing problem under these conditions is more complex. Financial engineers have to determine the value of the risk premium in addition to “projecting” future earnings or cash flows.  

Now consider an alternative. Setting the (positive) risk premium equal to zero in the previous equation gives the inequality  

$$
X_{t}<\frac{1}{(1+r_{t}\Delta)}E_{t}^{P}[X_{t+\Delta}]
$$  

But this is the same as risk-free savings account normalization. This means that by switching from $P$ to $\tilde{P}$ , we can restore the equality  

$$
X_{t}=\frac{1}{(1+r_{t}\Delta)}E_{t}^{\tilde{P}}[X_{t+\Delta}]
$$  

Thus, normalization and synthetic probabilities internalize the risk premia by converting both unknowns into a known and objective probability $\tilde{P}$ . Equation (12.77) can be exploited for pricing and risk management.  

# 12.6 ARBITRAGE-FREE DYNAMICS  

The last result that we derive from the fundamental theorem of asset pricing is a combination of all the corollaries discussed thus far. The synthetic probabilities and the Martingale property that we obtained earlier can be used to derive several arbitrage-free dynamics for an asset price. These arbitrage-free dynamics play an important role in pricing situations where an exact synthetic cannot be created, either due to differences in nonlinearities or due to a lack of liquid constituent assets. In fact, most of the pricing models will proceed along the lines of first obtaining arbitrage-free dynamics, and then either simulating paths from this or obtaining the implied binomial or trinomial trees. PDE methods also use these arbitrage-free dynamics.  

# 12.6.1 ARBITRAGE-FREE SDEs  

In this section, we briefly discuss the use of stochastic differential equations (SDEs) as a tool in financial engineering and then show how the fundamental theorem helps in specifying explicit SDEs that can be used in pricing and hedging in practice.21 Consider an asset price $S_{t}.$ Suppose we divide the time period $[t,T]$ into small intervals of equal size $\Delta$ . For each time $t+i\Delta$ , $i=1,...,n$ , we observe a different $S_{t+i\Delta}$ . $S_{t+\Delta}-S_{t}$ is the change in asset price at time $t$ . Choose a working probability from all available synthetic probabilities, and denote it by $P^{*}$ .  

Then, we can always calculate the expected value of this change under this probability. In the case of $P^{*}=\tilde{P}$ , we obtain the risk-neutral expected net return by  

$$
E_{t}^{\tilde{P}}[S_{t+\Delta}-S_{t}]=r_{t}S_{t}\Delta
$$  

Next, note that the following statement is always true:  

Now we can use the probability switching method and exploit the Martingale property. For example, for the risk-neutral probability we have  

$$
[S_{t+\Delta}-S_{t}]E_{t}^{\tilde{P}}[S_{t+\Delta}-S_{t}]+\epsilon_{t}
$$  

where $\in_{t}$ represents a random variable with zero expectation under $\tilde{P}$ . Replace from Eq. (12.78  

$$
[S_{t+\Delta}-S_{t}]=r_{t}S_{t}\Delta+\in_{t}
$$  

Now the error term $\in_{t}$ can be written in the equivalent form  

$$
\in_{t}=\sigma(S_{t})S_{t}\Delta W_{t}
$$  

here $\Delta W_{t}$ is a Wiener process increment with variance equal to $\Delta$ .  

Thus, the arbitrage-free dynamics under the $\tilde{P}$ measure can be written as  

$$
[S_{t+\Delta}-S_{t}]=r_{t}S_{t}\Delta+\sigma(S_{t})S_{t}\Delta W_{t}
$$  

Letting $\Delta\to0$ , this equation becomes an SDE, that represents the arbitrage-free dynamics under the synthetic probability, $\tilde{P}$ , during an infinitesimally short period $\mathrm{d}t$ . Symbolically, the SDE is written as  

$$
\mathrm{d}S_{t}=r_{t}S_{t}\mathrm{d}t+\sigma(S_{t})S_{t}\mathrm{d}W_{t}
$$  

$\mathrm{d}S_{t}$ and $\mathrm{d}W_{t}$ represent changes in the relevant variables during an infinitesimal time interval. Given the values for the (percentage) volatility parameter, $\sigma(S_{t})$ , these equations can be used to generate arbitrage-free trajectories for $S_{t}$ . We deal with these in the next chapter. Note a major advantage of using the risk-neutral probability. The drift term, that is to say the first term on the right-hand side, is known. At this point, we consider a second way of obtaining arbitrage-free paths.  

# 12.6.2 TREE MODELS  

We will see another major application of the Martingale property. We develop the notion of binomial (trinomial) trees introduced in Chapter 8 and obtain an alternative way of handling arbitragefree dynamics. Suppose the dynamics of $S_{t}$ can be described by a (geometric) SDE:  

$$
\mathrm{d}S_{t}=r S_{t}\mathrm{d}t+\sigma S_{t}\mathrm{d}W_{t}
$$  

where the volatility is assumed to be given by  

$$
\sigma(S_{t})=\sigma
$$  

This is the constant percentage volatility of $S_{t}$ . Also note that $\boldsymbol{r}_{t}$ is set to a constant. It can be shown that this SDE can be “solved” for $S_{t}$ to obtain the relationship (Øksendal, 2010).  

$$
S_{t+\Delta}=S_{t}e^{r\Delta-\frac{1}{2}\sigma^{2}\Delta+\sigma(W_{t+\Delta}-W_{t})}
$$  

Our purpose is to construct an approximation to the arbitrage-free dynamics of this $S_{t}$ . We will do this by considering approximations to possible paths that $S_{t}$ can follow between $t$ and some “expiration” date $T.$ . This approximation will be such that $S_{t}$ will satisfy the Martingale property under a judiciously chosen probability. Finally, the approximation should be chosen so that as $\Delta\to0$ , the mean and the variance of the discrete approximation converge to those of the continuous time process under the relevant probability. It turns out that this can be done in many different ways. Each method may have its advantages and disadvantages. We discuss two different ways of building trees. As $\Delta\to0$ , the dynamics become those of continuous time.  

# 12.6.2.1 Case 1  

The method introduced by Cox Ross Rubinstein (CRR) selects the following approximation. First, the period $[t_{0},\ T]$ is divided into $N$ subintervals of equal length. Then, it is assumed that at each point of a path there are possible states. In the CRR case, $n=2$ and the paths become binomial. An alternative trinomial tree is shown in Figure 12.3.  

At every node $i$ of a possible path, there are only two possible states represented by the numbers $\{u_{i},d_{i}\}$ , with the (marginal) probabilities $p$ and $(1-p)$ . The dynamics are selected as follows:  

$$
\begin{array}{c}{{S_{i}^{u}=u_{i}S_{i-\Delta}}}\\ {{{}}}\\ {{S_{i}^{d}=d_{i}S_{i-\Delta}}}\end{array}
$$  

where $S_{i}$ is the shortcut notation for $S_{t+i\Delta}$ .  

![](aca4a13cefdd06b088218930b6e5e6a47b8b4fe678dc6212edc8de9efd3f2af5.jpg)  

# FIGURE 12.3  

Trinomial tree.  

# 418 CHAPTER 12 PRICING TOOLS IN FINANCIAL ENGINEERING  

• The $\{\underline{{u}}_{i},d_{i}\}$ are assumed to be constant at $u,d.$ .  

We now show how to determine the Martingale probabilities. One approach is to find probabilities such that under $p$ , $(1-p)$ :  

$$
S_{i}=e^{-r\Delta}E_{i}^{\tilde{p}}[S_{i+\Delta}]
$$  

or  

$$
S_{i}=e^{-r\Delta}[p S_{i+\Delta}^{u}+(1-p)S_{i+\Delta}^{d}]
$$  

Using the definition of $S_{i+\Delta}^{u},S_{i+\Delta}^{d}$ , in Eqs. (12.88) and (12.89), we can write  

$$
S_{i}=e^{-r\Delta}[p S_{i}u+(1-p)S_{i}d]
$$  

The mean and the variance of $S_{i}$ under this probability should also be as given by the postulated dynamics of the continuous time process in the limit.22 In other words, $p$ should also satisfy  

$$
E_{i}^{\tilde{P}}[S_{i+\Delta}]=[p u+(1-p)d]S_{i}
$$  

and  

$$
E_{i}^{\tilde{P}}[S_{i+\Delta}^{2}-E_{i}^{\tilde{P}}[S_{i+\Delta}]^{2}]=[p u^{2}+(1-p)d^{2}]S_{i}^{2}-E_{i}^{\tilde{P}}[S_{i+\Delta}]^{2}
$$  

Use  

$$
E_{i}^{\tilde{P}}[S_{i+\Delta}]=S_{i}e^{r\Delta}
$$  

$$
E_{i}^{\tilde{P}}[S_{i+\Delta}^{2}-E_{i}^{\tilde{P}}[S_{i+\Delta}]^{2}]=S_{i}^{2}e^{2r\Delta}(e^{\sigma^{2}\Delta}-1)
$$  

and get the equations  

$$
\begin{array}{c}{{e^{r\Delta}=p u+(1-p)d}}\\ {{e^{2r\Delta+\sigma^{2}\Delta}=p u^{2}+(1-p)d^{2}}}\end{array}
$$  

The $p,\ u,\ d$ that satisfy these two equations will (i) satisfy the Martingale equality for all $\Delta$ , (ii) get arbitrarily close to the mean and the variance of the continuous time process $S_{t}$ as $\Delta$ goes to zero, and (iii) make the asymptotic distribution of $S_{i}$ normal. However, there is one problem. Note that here we have two equations and three unknowns: $u,\ d,$ , and $p$ . One more equation is needed. Choose  

$$
u={\frac{1}{d}}
$$  

This makes the tree recombine and completes the system of equations. Under these conditions, the following values solve the equations  

$$
\begin{array}{c}{p=\displaystyle\frac{e^{r\Delta}-d}{u-d}}\\ {u=e^{\sigma\sqrt{\Delta}}}\\ {d=e^{-\sigma\sqrt{\Delta}}}\end{array}
$$  

Any approximation here is in the sense that all terms containing higher orders of $\Delta$ are ignored.23  

# 12.6.2.2 Case 2  

The previous selection of $p,u,d$ satisfies  

$$
S_{i}=e^{-r\Delta}\left[p S_{i}e^{\sigma\sqrt{\Delta}}+(1-p)S_{i}e^{-\sigma\sqrt{\Delta}}\right]
$$  

It turns out that $p,u,d$ can be selected in other ways as well. In particular, note that during an interval $\Delta,S_{t}$ moves to  

$$
S_{t+\Delta}=S_{t}e^{r\Delta-\frac{1}{2}\sigma^{2}\Delta+\sigma[W_{t+\Delta}-W_{t}]}
$$  

Using the approximation  

$$
W_{t+\Delta}-W_{t}={\left\{\begin{array}{l l}{+{\sqrt{\Delta}}}&{{\mathrm{with~probability~}}0.5}\\ {-{\sqrt{\Delta}}}&{{\mathrm{with~probability~}}0.5}\end{array}\right.}
$$  

we get new values for $p,u$ , and $d$ :  

$$
\begin{array}{c}{{u=e^{r\Delta-\frac12\sigma^{2}\Delta+\sigma\sqrt{(\Delta)}}}}\\ {{{}}}\\ {{d=e^{r\Delta-\frac12\sigma^{2}\Delta-\sigma\sqrt{(\Delta)}}}}\\ {{{}}}\\ {{p=0.5}}\end{array}
$$  

These values will again satisfy the Martingale equality, the equality for the mean, and the variance of $S_{i}$ , in the same approximate sense.  

# 12.7 WHICH PRICING METHOD TO CHOOSE?  

In general, the choice of a pricing method depends on the following factors:  

The accuracy of pricing methods does, in general, differ. Some methods are numerically more stable than others. Some methods yield coarser approximations than others. Precision is an important factor. The speed of pricing methods also changes from one method to another. In general, everything else being the same, the faster results are preferred. Some methods are easier to implement. The ease of understanding a pricing method is an important factor in its selection by practitioners. The parsimony associated with the model is also important. In general, we want our pricing models to depend on as few parameters as possible. This way, the model has to be calibrated to a smaller number of parameters, which means that fewer things can go wrong. Also, a trader/ broker can in general compensate for a parsimonious model by adjusting the quotes based on trading experience.  

However, in the end, the method chosen depends on the circumstances and is a matter of experience. What a book like this can do is to present a brief overview of the various approaches available to the financial engineer.  

# 12.8 CONCLUSIONS  

We obtained some important results in this chapter. First, we showed that the notion of state prices can be made practical in environments with liquid option prices at different strikes. From here we showed how to obtain risk-neutral and forward measures and the corresponding arbitrage-free dynamics.  

Finally, as long as liquid option prices with different strikes exist, we showed how to replicate an asset using a static portfolio of options. This is true for the following reasons:  

1. Given the option prices, we can get the prices of elementary insurance contracts. 2. But we know that every asset can be synthetically created as a portfolio of elementary insurance contracts. 3. This means that every asset can be created as a portfolio of liquid options.  

Hence, option markets not only provide close relatives of elementary insurance contracts, but also show us how to obtain generalized static synthetics for all assets in principle. Of course, the practical application depends on the availability of liquid options.  

Finally, we must emphasize that risk management and pricing are never as straightforward in real life, since given the day, the number, and the type of liquid option, contracts change.  

# SUGGESTED READING  

The treatment of the fundamental theorem of finance in this chapter has been heuristic and introductory, although all important aspects of the theorem have been covered. The reader can get more insight into the theorem by looking at Duffie (2001), which offers an excellent treatment of asset pricing. The article by Brace et al. (1997) is an important milestone in the use of Martingale theory, and places the right emphasis on pricing and the measure of change that fits this chapter. Clewlow and Strickland (1998) provide several examples.  

# APPENDIX 12.1: SIMPLE ECONOMICS OF THE FUNDAMENTAL THEOREM  

This appendix provides a justification for the fundamental theorem from standard microeconomic theory. Consider the following setup. An investor faces a decision that involves two time periods; the time of decision, and $T_{\cdot}$ , the relevant future date. At $T_{\mathrm{{:}}}$ there are only two possible states of the world $\omega^{i}$ , $i=1$ , 2. The investor’s subjective probabilities for these are $p^{1}$ and $p^{2}$ , respectively.  

This investor’s preferences are described by a utility function $U\left(X_{t}\right)$ , where $X_{t}$ is total (real) consumption at time $t.$ . Essentially, this investor is better off the higher his or her consumption:  

$$
0<\frac{\mathrm{d}U}{\mathrm{d}X_{t}}
$$  

But, additional consumption would incrementally have less and less positive effect:  

$$
\frac{\mathrm{d}^{2}U}{\mathrm{d}X_{t}^{2}}<0
$$  

This investor would like to maximize the expected utility associated with his or her current and future consumption:  

$$
E_{t}^{P}[U(X_{t})+\beta U(X_{T})]=U(X_{t})+\beta(p^{1}U(X_{T}^{1})+p^{2}U(X_{T}^{2}))
$$  

where $\beta$ is a constant subjective discount factor, $P$ is the subjective personal probability, and $X_{T}^{1}$ and $X_{T}^{2}$ are the consumption levels in states 1 and 2 during period $T_{\mathrm{{:}}}$ respectively. The maximization of this function is subject to the investor’s budget constraint at time $t$ and on the two states of the world at time $T_{\mathbf{\delta}}$ .  

$$
\begin{array}{r l}&{q_{t}X_{t}+S_{t}h_{t}=I}\\ &{~q_{T}^{1}X_{T}^{1}=I+h_{t}S_{T}^{1}}\\ &{~q_{T}^{2}X_{T}^{2}=I+h_{t}S_{T}^{2}}\end{array}
$$  

$S_{t}$ is a risky asset that can be purchased at time $t.$ . It has possible values $S_{T}^{1}$ and $S_{T}^{2}$ at time $T.$ . Here $I$ is a known and constant income earned at times $t$ and $T.\ q_{t},\ q_{T}^{1}$ , and $q_{T}^{2}$ are the corresponding prices of the consumption good. Note that, at time $T_{\mathbf{\delta}}$ , there are two prices, one for each state. Finally, $h_{t}$ is the number of $S_{t}$ purchased by the investor at time $t$ .  

According to this, we are dealing with an investor who receives a constant income that needs to be split between saving and consumption in a two-period setting. The investment can be made only by buying a desired amount of the $S_{t}$ asset. The price of this asset is a random variable in the model.  

The investor is risk averse and maximizes the expected utility function. There are several ways one can solve this maximization. Our intention is to show a simple example to motivate the fundamental theorem of finance. Hence, we are not concerned with the optimal consumption itself. Rather, we would like to obtain a relationship between “current” asset price $S_{t}$ and the two possible values $S_{T}^{1}$ and $S_{T}^{2}$ at time $T.$ . The fundamental theorem of asset pricing is about these two sets of prices. Thus, we should be able to find out how the present framework can generate the state prices $\boldsymbol{Q}^{i}$ of the fundamental theorem.  

Keeping these objectives in mind, we proceed by first substituting out $X_{t},X_{T}^{1},X_{T}^{2}$ from the equations in (12.112), and then differentiating the resulting expression with respect to the only remaining choice variable $h_{t}$ . The substitution gives  

$$
\begin{array}{r l}{X_{t})+\beta(p^{1}U(X_{T}^{1})+p^{2}U(X_{T}^{2}))=}&{{}U\left(\frac{I-S_{t}h_{t}}{q_{t}}\right)+\beta\left(p^{1}U\left(\frac{I+h_{t}S_{T}^{1}}{q_{T}^{1}}\right)+p^{2}U\left(\frac{I+h_{t}S_{T}^{2}}{q_{T}^{2}}\right)\right)}\end{array}
$$  

Differentiating the right side with respect to $h_{t}.$ , equating to zero, and then rearranging,  

$$
\begin{array}{r l}{U^{\prime}\left(\frac{I-S_{t}h_{t}}{q_{t}}\right)\left(\frac{S_{t}}{q_{t}}\right)=}&{{}\beta\left(p^{1}U^{\prime}\left(\frac{I+h_{t}S_{T}^{1}}{q_{T}^{1}}\right)\left(\frac{S_{T}^{1}}{q_{T}^{1}}\right)+p^{2}U^{\prime}\left(\frac{I+h_{t}S_{T}^{2}}{q_{T}^{2}}\right)\left(\frac{S_{T}^{2}}{q_{T}^{2}}\right)\right)}\end{array}
$$  

where $U^{\prime}(.)$ is the derivative of $U\left(x\right)$ with respect to $^{66}x$ .”  

Now comes the critical point. We can rearrange the first-order condition in Eq. (12.114) to obtain  

$$
S_{t}=\beta\bigg(p^{1}\frac{U^{\prime}((I+h_{t}S_{T}^{1})/q_{T}^{1})}{U^{\prime}((I-S_{t}h_{t})/q_{t})}\frac{q_{t}}{q_{T}^{1}}S_{T}^{1}+p^{2}\frac{U^{\prime}((I+h_{t}S_{T}^{2})/q_{T}^{2})}{U^{\prime}((I-S_{t}h_{t})/q_{t})}\frac{q_{t}}{q_{T}^{2}}S_{T}^{2}\bigg)
$$  

Now relabel as follows:  

$$
Q^{1}=\beta p^{1}\frac{U^{\prime}((I+h_{t}S_{T}^{1})/q_{T}^{1})}{U^{\prime}((I-S_{t}h_{t})/q_{t})}\frac{q_{t}}{q_{T}^{1}}
$$  

and  

$$
Q^{2}=\beta p^{2}\frac{U^{\prime}((I+h_{t}S_{T}^{2})/q_{T}^{2})}{U^{\prime}((I-S_{t}h_{t})/q_{t})}\frac{q_{t}}{q_{T}^{2}}
$$  

It is clear that all elements of the right-side expressions are positive and, as a result, $Q^{i},i=1,$ 2, are positive. Substituting these $\boldsymbol{Q}^{i}$ back in Eq. (12.115), we get  

$$
S_{t}=S_{T}^{1}Q^{1}+S_{T}^{2}Q^{2}
$$  

In other words, there is a linear relationship between current asset price $S_{t}$ and the future possible values $S_{T}^{1}$ and $S_{T}^{2}$ , and $\{Q^{i}\}$ is the determining factor.  

An interesting implication of the derivation shown here is the following. Even when the utility function $U(.)$ and the subjective probabilities $p^{i}$ differ among investors, general equilibrium conditions would equate the marginal rates of substitution across these differing investors and hence the $\{Q^{i}\}$ would be the same. In other words, $\{Q^{i}\}$ would be unique to all consumers even when these consumers disagree on the expected future behavior of the economy.  

# EXERCISES  

1. The following prices of the four different stocks are reported from an arbitrage-free market at time $t_{0}$  

$$
S_{t_{0}}^{1}=12.66,S_{t_{0}}^{2}=12.24,S_{t_{0}}^{3}=20.66,S_{t_{0}}^{4}=18.25
$$  

Find out the price of the 5th asset given the following possible values of these assets at time $T$ .  

<html><body><table><tr><td>14 3</td><td>25</td></tr><tr><td>11 10</td><td>9</td></tr><tr><td>9 23</td><td>24 22</td></tr><tr><td>8 25</td><td>10</td></tr><tr><td>6 15</td><td>25 10</td></tr></table></body></html>  

2. The current time is $t=1$ and our framework is the LIBOR model. We consider a situation with four states of the world $\omega_{i}$ at time $t=3$ .  

Suppose $L_{i}$ is the LIBOR process with a particular tenor and $B(1,3)$ , $B(1,4)$ , and $B(1,4)$ are zero-coupon bond prices with indicated maturities. The possible payoffs of these instruments in the four future states of the world are as follows:  

$$
L=6\%,6\%,4\%,4\%
$$  

$$
B(1,3)=1,1,1,1
$$  

$$
\begin{array}{l}{{B(1,4)=0.9,0.92,0.95,0.96}}\\ {{B(1,5)=0.8,0.84,0.85,0.88}}\end{array}
$$  

The current prices are, respectively,  

Here the 1 is a dollar invested in LIBOR. It is like a savings account. Finally, current LIBOR is $5\%$ .  

a. Using Mathematica or MATLAB, determine a state price vector $q_{1},q_{2},q_{3},q_{4}$ , that corresponds to $B$ (1, 3), $B(1,4)$ , $B(1,5)$ , $L$ as a basis.   
b. Does $q_{i}$ satisfy the required condition of positivity? Is there an arbitrage opportunity?   
c. Let $F$ be the $1\times2$ FRA rate. Can you determine its arbitrage-free value?   
d. Now let $C$ be an ATM caplet (i.e., the strike is $5\%$ ) that expires at time $t=2$ , but settled at time $t=3$ with notional amount 1. How much is it worth?  

3. Suppose you are given the following data. The risk-free interest rate is $4\%$ . The stock price follows:  

$$
\mathrm{d}S_{t}=\mu S_{t}+\sigma S_{t}\mathrm{d}W_{t}
$$  

The percentage annual volatility is $18\%$ a year. The stock pays no dividends and the current stock price is 100.  

Using these data, you are asked to calculate the current value of a European call option on the stock. The option has a strike price of 100 and a maturity of 200 days.  

a. Determine an appropriate time interval $\Delta$ , such that the binomial tree has five steps. b. What would be the implied $u$ and $d$ ?   
c. What is the implied “up” probability?   
d. Determine the binomial tree for the stock price $S_{t}$ .   
e. Determine the tree for the call premium $C_{t}$ .  

4. Suppose the stock discussed in the previous exercise pays dividends. Assume all parameters are the same. Consider three forms of dividends paid by the firm:  

a. The stock pays a continuous, known stream of dividends at a rate of $4\%$ per time.   
b. The stock pays $5\%$ of the value of the stock at the third node. No other dividends are paid.   
c. The stock pays a $\$5$ dividend at the third node. In each case, determine the tree for the ex-dividend stock price. For the first two cases, determine the premium of the call. In what way(s) will the third type of dividend payment complicate the binomial tre  

5. We use binomial trees to value American-style options on the British pound. Assume that the British pound is currently worth $\$1.40$ . Volatility is $20\%$ . The current British risk-free rate is $6\%$ and the US risk-free rate is $3\%$ . The put option has a strike price of $\$1.50$ . It expires in 200 days. a. The first issue to be settled is the role of US and British interest rates. This option is being purchased in the United States, so the relevant risk-free rate is $3\%$ . But British pounds can be used to earn the British risk-free rate. So this variable can be treated as a continuous rate of dividends. Or we can say that interest rate differentials are supposed to equal the expected appreciation of the currency. Taking this into account, determine a $\Delta$ such that the binomial tree has five periods. b. Determine the implied $u$ and $d$ and the relevant probabilities. c. Determine the tree for the exchange rate. d. Determine the tree for a European put with the same characteristics. e. Determine the price of an American-style put with the previously stated properties.  

6. Barrier options belong to one of four main categories. They can be up-and-out, down-andout, up-and-in, or down-and-in. In each case, there is a specified “barrier,” and when the underlying asset price down- or up-crosses this barrier, the option either expires automatically (the “out” case) or comes into life automatically (the “in” case).  

Consider a European-style up-and-out call written on a stock with a current price of 100 and a volatility of $30\%$ . The stock pays no dividends and follows a geometric price process. The risk-free interest rate is $6\%$ and the option matures in 200 days. The strike price is 110. Finally, the barrier is 120. If the before-maturity stock price exceeds 120, the option automatically expires.  

a. Determine the relevant $u$ and $d$ and the corresponding probability.   
b. Value a call with the same characteristics but without the barrier property. c. Value the up-and-out call.   
d. Which option is cheaper?  

# EXCEL EXERCISES  

7. (European Option)  

Write a VBA program to determine the initial price of a European Call and European Put option in a binomial model based on the following data:  

Create a function to calculate the option price using the Black Scholes formula and compare the two results. Now gradually increase the value of $M$ and report the subsequent option prices. Use the value of u 5 eσpffiΔffiffitffi and d 5 e2σpffiΔffiffitffi  

8. (European Option Nonrecombining Binomial Tree)  

Write a VBA program to determine the initial price of a European Call and European Put option in a nonrecombining binomial tree model based on the following data:  

$S(O)=100\$ ; $K=105$ ; $T=1$ ; $r=8\%$ ; $\sigma=30\%$ ; $M=10$  

Create a function to calculate the option price using the Black Scholes formula and compare the two results. Now gradually increase the value of $M$ and report the subsequent option prices. Use the value of $u=e^{\sigma\sqrt{\Delta t}+(r-\sigma^{2}/2)\Delta t}$ and $d=e^{-\sigma\sqrt{\Delta t}+(r-\sigma^{2}/2)\Delta t}$  

9. (American Option)  

Write a VBA program to determine the initial price of an American Call and American Put option in a binomial model based on the following data:  

Gradually increase the value of $M$ and report the subsequent option prices. Use the value of $u=e^{\sigma{\sqrt{\Delta t}}}$ and $d=e^{-\sigma{\sqrt{\Delta t}}}$  

10. European option on dividend paying index  

Write a VBA program to determine the initial price of a European Call and European Put option in a binomial model based on the following data:  

Create function to calculate the option price using the Black Scholes formula and compare. Now gradually increase the value of $M$ and report the subsequent option prices.  

Use the value of $u=e^{\sigma\sqrt{\Delta t}}$ and $d=e^{-\sigma{\sqrt{\Delta t}}}$  

11. European option on dividend paying index (nonrecombining binomial tree)  

Write a VBA program to determine the initial price of a European Call and European Put option in nonrecombining binomial model based on the following data:  

$S(O)=100\$ ; $K=105$ ; $T=1$ ; $r=8\%$ ; $\sigma=30\%$ ; $\mathrm{div}=8\%$ ; $M=10$  

Create function to calculate the option price using the Black Scholes formula and compare. Now gradually increase the value of $M$ and report the subsequent option prices.  

Use the value of $u=e^{\sigma\sqrt{\Delta t}+(r-\mathrm{div}-\sigma^{2}/2)\Delta t}$ and $d=e^{-\sigma{\sqrt{\Delta t}}+(r-\mathrm{div}-\sigma^{2}/2)\Delta t}$  

12. (FX American Option)  

Write a VBA program to determine the initial price of an American-style options on the British pound in a binomial model based on the following data:  

Gradually increase the value of $M$ and report the subsequent option prices. Use the value of $u=e^{\sigma{\sqrt{\Delta t}}}$ and $d=e^{-\sigma{\sqrt{\Delta t}}}$  

13. FX European Option  

Write a VBA program to determine the initial price of European-style options on the British pound in the binomial model based on the following data:  

Create a function to calculate the option price using the Black Scholes formula and compare. Now gradually increase the value of $M$ and report the subsequent option prices.  

Use the value of $u=e^{\sigma\sqrt{\Delta t}}$ and $d=e^{-\sigma{\sqrt{\Delta t}}}$  

# 426 CHAPTER 12 PRICING TOOLS IN FINANCIAL ENGINEERING  

14. FX European Option (Nonrecombining B-Tree) Write a VBA program to determine the initial price of European-style options on the British pound in a nonrecombining binomial tree model based on the following data:  

Create a function to calculate the option price using the Black Scholes formula and compare. Now gradually increase the value of $M$ and report the subsequent option prices. Use the value of $u=e^{\sigma\sqrt{\Delta t}+(r-r_{f}-\sigma^{2}/2)\Delta t}$ and $d=e^{-\sigma\sqrt{\Delta t}+(r-r_{f}-\sigma_{2}/2)\Delta t}$  