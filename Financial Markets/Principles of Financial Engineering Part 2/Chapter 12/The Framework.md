---
tags:
  - '#arbitrage_opportunity'
  - '#elementary_insurance_contracts'
  - '#fundamental_theorem_of_asset_pricing'
  - '#option_pricing'
  - '#payoff_matrix'
  - '#pricing_framework'
  - '#risk_management'
  - '#state_prices'
  - '#states_of_the_world'
---
# 12.3 THE FRAMEWORK  

The pricing framework that we use emphasizes important aspects of the theory within a real-world setting. We assume that. $m$ liquid asset prices are observed at times $t_{i:}$ $i=1$ , 2, ... The time. $t_{i}$ price of the kth asset is denoted by. $S_{k t_{i}}$ . The latter can represent credit, stocks, fixed-income instruments, the corresponding derivatives, or commodity prices.  

In theory, a typical $S_{k t_{i}}$ can assume any real value. This makes the number of possible values. infinite and uncountable. But in practice, every price is quoted to a small number of decimal places. and, hence, has a countable number of possible future values. FX rates, for example, are in general quoted to four decimal places. This brings us to the next important notion that we would like to introduce.  

# 12.3.1 STATES OF THE WORLD  

Let $t_{0}$ denote the "present," and consider the kth asset price. $S_{k T},$ at a future date, $T=t_{i}$ for some $0<i.$ At time $t_{0}$ $S_{k T}$ will be a random variable." Let the symbol. $\omega^{j}$ with $j=1,...,n$ represent time $T$ states of the world that relate to the random variable. $S_{k T}$ 5 We assume that $n\leq m$ , which amounts. to saying that there are at least as many liquid assets as there are time $T$ states of the world. For. example, it is common practice in financial markets to assume a "bullish" state, a "bearish" state, and a "no-change"' state. Traders expect prices in the future to be either "higher," "lower," or to "remain the same." The $\omega^{j}$ generalizes this characterization and makes it operational..  

# EXAMPLE  

In this example, we construct the states of the world that relate to some asset whose time $t_{i}$ price is denoted by $S_{t_{i}}$ . Without any loss of generality, let.  

$$
S_{t_{0}}=100
$$  

Suppose, at a future date. $T.$ with $t_{n}=T$ , there are only $n=4$ states of the world. We con-. sider the task of defining these states.  

1. Set the value of some grid parameter $\Delta S$ to assign neighboring values of. $S_{T}$ into a single state. For example, let.  

$$
\Delta S=2
$$  

2. Next, pick two upper and lower bounds $[S^{\operatorname*{min}},S^{\operatorname*{max}}]$ such that the probability of $S_{T}$ being outside this interval is relatively small and that excursions outside this range can safely be ignored. For example, let $S^{\mathrm{max}}=104\$ and $S^{\mathrm{min}}=96$ . Accordingly, the events $104<S_{T}$ and $S_{T}<96$ are considered unlikely to occur, and, hence, a detailed breakdown of these states of the world is not needed. Clearly, the choice of numerical values for $[S^{\operatorname*{min}},S^{\operatorname*{max}}]$ depends, among other things, on the perceived volatility of $S_{t}$ during the period $[t_{0},T]$ 6.  

3. The states of the world can then be defined in the following fashion:  

$$
\omega^{1}=\{S_{T}\mathrm{such~that~}S_{T}<S^{\mathrm{min}}\}
$$  

$$
\omega^{2}=\{S_{T}\mathrm{suchthat}S_{T}\in[S^{\mathrm{min}},S^{\mathrm{min}}+\Delta S]\}
$$  

$$
\omega^{3}=\{S_{T}\mathrm{suchthat}S_{T}\in[S^{\mathrm{min}}+\Delta S,S^{\mathrm{min}}+2\Delta S=S^{\mathrm{max}}]\}
$$  

$$
\omega^{4}=\{S_{T}\mathrm{suchthat}S^{\mathrm{max}}<S_{T}\}
$$  

This situation is shown in Figure 12.1.  

![](images/46118e4db009e002f8106154e908d47746051f77a7f5aafd97ffebd9073a7121.jpg)  

# FIGURE 12.1  

States of the world and asset values.  

Here, the total number of states of the world depends on the size of the grid parameter. $\Delta S$ and on the choice of upper and lower bounds $[S^{\operatorname*{min}},S^{\operatorname*{max}}]$ . These, in turn, depend on market psychology at time $t_{0}$ For example, selecting the total number of states as $n=4$ could be justified, if the ranges for $S_{T}$ shown here were the only ones found relevant for pricing and risk-management problems. faced during that particular day. If a problem under consideration requires a finer or coarser subdivision of the future, the value for $n$ would change accordingly..  

# 12.3.2 THE PAYOFF MATRIX  

The next step in obtaining the fundamental theorem of asset pricing is the definition of a payoff matrix for period $T.$ Time $T$ values of the assets, $S_{k t}$ , depend on the state of the world, $\omega^{i}$ that will occur at time $T.$ Given that we are working with a finite number of states of the world, possible values for these assets would be easy to list. Let $z_{k}^{i}$ represent the value assumed by the kth asset in state $\omega^{i}$ , at time $T$  

$$
S_{k T}^{i}=z_{k}^{i}
$$  

Then, for the first $n$ assets, $n\leq m$ , we can form the following payoff matrix for time $T$  

$$
D={\left(\begin{array}{l l l}{z_{1}^{1}}&{\cdots}&{z_{1}^{n}}\ &{\cdots}&\ {z_{n}^{1}}&{\cdots}&{z_{n}^{n}}\end{array}\right)}
$$  

A typical row of this matrix would represent possible values of a particular asset in different. states of the world. A typical column represents different asset prices, in a particular state of the world. The definition of. $\omega^{i}$ should automatically lead to a definition of the possible values for. assets under consideration, as shown in the previous example..  

The fundamental theorem of asset pricing is about how "current' asset prices, $S_{k t}$ relate to the possible values represented by matrix. $D$ . We form a matrix equation that will play an important. role in the next three chapters..  

# 12.3.3 THE FUNDAMENTAL THEOREM  

Consider the linear system of equations defined for a series of $Q^{i}$ , indexed by the state of the world $i$  

$$
\binom{S_{1t_{0}}}{\cdots}=\binom{z_{1}^{1}}{z_{n}^{1}}\begin{array}{c c c}{{\cdots}}&{{z_{1}^{n}}}\ {{\cdots}}&{{\cdots}}&{{}}\ {{\left.z_{n}^{1}\right)}}&{{\cdots}}&{{z_{n}^{n}}}\end{array}\right)\binom{Q^{1}}{\cdots}
$$  

The left-hand side shows the vector of current liquid asset prices observed at time $t_{0}$ . The righthand side has two components. The first is the matrix $D$ of possible values for these prices at time $T$ and the second is a vector of constants, $\{Q^{1},...,Q^{n}\}$ . The fundamental theorem of asset pricing concerns this matrix equation and the properties of the $\{Q^{i}\}$ . The theorem can be stated heuristically as follows:  

Theorem: The time $t_{0}$ prices for the $\{S_{k t_{0}}\}$ are arbitrage-free if and only if $\{Q^{i}\}$ exist and are positive.  

Thus, the theorem actually works both ways. If $S_{k t_{0}}$ are arbitrage-free, then $Q^{i}$ exist and are all positive. If $Q^{i}$ exist and are positive, then $S_{k t_{0}}$ are arbitrage-free.  

The fundamental theorem of asset pricing provides a unified pricing tool for pricing real-world. assets. In the remaining part of this chapter, we derive important implications of this theorem. These can be regarded as corollaries that are exploited routinely in asset pricing. The first of these corollaries is the existence of synthetic probabilities. However, before we discuss these results we need to motivate the $\{Q^{i}\}$ and show why the theorem holds..  

# 12.3.4 DEFINITION OF AN ARBITRAGE OPPORTUNITY  

What is meant by arbitrage-free prices? To answer this question we need to define arbitrage opportunity formally. Formal definition of the framework outlined in this section provides this. Consider the asset prices $S_{1t},...,S_{k t}$ Associate the portfolio weights $\theta_{i}$ with asset $S_{i t}$ . Then we say that there is an arbitrage opportunity if either of the following two conditions hold.  

1. A portfolio with weights $\theta_{i}$ can be found such that:.  

$$
\sum_{i=1}^{k}\theta_{i}S_{i t}=0
$$  

simultaneously with  

$$
0\leq\sum_{i=1}^{k}\theta_{i}S_{i T}
$$  

According to these conditions, the market practitioner advances no cash at time $t$ to form the portfolio, but still has access to some non-zero gains at time $T.$ This is the first type of arbitrage opportunity.  

2. A portfolio with weights $\theta_{i}$ can be found such that:.  

$$
\sum_{i=1}^{k}\theta_{i}S_{i t}\leq0
$$  

simultaneously with  

$$
\sum_{i=1}^{k}\theta_{i}S_{i T}=0
$$  

In this case, the market practitioner receives cash at time $t$ while forming the portfolio, but. has no liabilities at time. $T$  

It is clear that in either case, the size of these arbitrage portfolios is arbitrary since no liabilities. are incurred. The formal definition of arbitrage-free prices requires that such portfolios not be feasible at the "current' prices $\{S_{i t}\}$  

Note that what market professionals call an arbitrage strategy is very different from this formal definition of arbitrage opportunity. In general, when practitioners talk about "arb" they mean positions that have a relatively small probability of losing money. Clearly this violates both of the conditions mentioned above. The methods introduced in this chapter deal with the lack of formal arbitrage opportunities and not with the market practitioners' arbitrage strategies. It should be remembered that it is the formal no-arbitrage condition that provides the important tools used in pricing and risk management.  

# 12.3.5 INTERPRETING THE $\pmb{Q}^{\prime}$ : STATE PRICES  

Given the states of the world $\omega^{i},i=1,...,n.$ we can write the preceding matrix equation for the special case of two important sets of instruments that are essential to understanding arbitrage-free  

pricing. Suppose the first asset. $S_{1t}$ is a risk-free savings deposit account and assume, without any loss of generality, that $t_{i}$ represents years. If 1 dollar is deposited at time. $t_{0}$ $\left(1+r_{t_{0}}\right)$ can be earned at time $t_{1}$ without any risk of default. The $r_{t_{0}}$ is the rate that is observed as of time. $t_{0}$  

The second set of instruments are elementary insurance contracts. We denote them by $C_{i}$ These contracts are defined in the following way:  

$C_{1}$ pays $\$1$ at time $T$ if $\omega^{1}$ occurs. Otherwise it pays zero.   
$C_{n}$ pays $\$1$ at time $T$ if $\omega^{n}$ occurs. Otherwise it pays zero.  

If a market practitioner considers state $\omega^{i}$ as "risky," he or she can buy a desired number of $C_{i}$ S as insurance to guarantee any needed cash flow in that state.  

Suppose now that all $C_{i}$ are actively traded at time $t_{0}$ . Then, according to the matrix equation, the correct arbitrage-free prices of these contracts are given by $Q^{i}$ This is the case since plugging the current prices of the savings account and the. $C_{i}$ at time $t_{0}$ into the matrix equation (12.9) gives  

$$
\left[\begin{array}{c}{{1}}\ {{C_{1}}}\ {{\ldots}}\ {{C_{n}}}\end{array}\right]=\left[\begin{array}{c c c c}{{\left(1+r_{t_{0}}\right)}}&{{\cdots}}&{{\cdots}}&{{\left(1+r_{t_{0}}\right)}}\ {{1}}&{{0}}&{{\cdots}}&{{0}}\ {{\ldots}}&{{\ldots}}&{{\ldots}}&{{\ldots}}\ {{0}}&{{\ldots}}&{{0}}&{{1}}\end{array}\right]\left[\begin{array}{l}{{Q^{1}}}\ {{\ldots}}\ {{Q^{n}}}\end{array}\right]
$$  

Following from this matrix equation,. $Q^{i}$ have three important properties. First, we see that they. are equal to the prices of the elementary insurance contracts:  

$$
C_{i}=Q^{i}
$$  

It is for this reason that $Q^{i}$ are also called state prices. Second, we can show that if interest rates are positive, the sum of the time $t_{0}$ prices of. $C_{i}$ is less than one. Consider the following: a portfolio that consists of buying one of each insurance contract $C_{i}$ at time $t_{0}$ will guarantee 1 dollar at time $t_{0}$ no matter which state, $\omega^{i}$ , is realized at time $T$ But, a guaranteed future dollar should be worth less than a current dollar at hand, as long as interest rates are positive. This means that the sum of $Q^{i}$ paid for the elementary contracts at time $t_{0}$ should satisfy  

$$
Q^{1}+Q^{2}+\cdots+Q^{n}<1
$$  

From the first row of the matrix equation in Eq. (12.14), we can write  

$$
\sum_{i=1}^{n}Q^{i}\big(1+r_{t_{0}}\big)=1
$$  

After rearranging,  

$$
Q^{1}+Q^{2}+\cdots+Q^{n}={\frac{1}{\left(1+r_{t_{0}}\right)}}
$$  

The third property is a little harder to see. As the fundamental theorem states, none of the $Q^{i}$ can be negative or zero if $C_{i}$ are indeed arbitrage-free. We show this with a simple counter example.  

# EXAMPLE  

Suppose we have $n=4$ and that the first elementary contract has a negative price, $C_{1}=-1$ Without any loss of generality, suppose all other elementary insurance contracts have a positive price. Then the portfolio  

has zero cost at time. $t_{0}$ and yet will guarantee a positive return at time $t_{1}$ . More precisely, the portfolio returns 1 dollar in states 2-4 and. $(Q^{\bar{2}}+Q^{3}+Q^{4})$ dollars in state 1.  

Hence, as long as one or more of the. $Q^{i}$ are negative, there will always be an arbitrage opportunity. A trader can "buy" the contract(s) with a negative price and use the cash generated to purchase the other contracts. This way, a positive return at. $T$ is guaranteed, while at the same time the. zero-cost structure of the initial portfolio is maintained. For such arbitrage opportunities not to exist, we need $0<Q^{i}$ for all $i.$  

# 12.3.5.1 Remarks  

Before going further, we ask two questions that may have already troubled the reader given the financial engineering approach we adopted in this book.  

Do insurance contracts such as $C_{i}$ exist in the real world? Are they actively traded? Is the assumption of a small finite number of states of the world realistic? How can such a restrictive view of the future be useful in pricing real-world instruments?  

In the next few sections, we will show that the answer to both of these questions is a qualified yes. To understand this, we need to relate the elementary insurance contracts to the concept of options. Options can be considered as ways of trading baskets of. $C_{i}$ s. A typical $C_{i}$ pays 1 dollar if state $i$ occurs and nothing in all other states. Thus, it is clear that option payoffs at expiration are. different from those of elementary contracts. Options pay nothing if they expire out-of-the-money,. but they pay, $(S_{T}-K)$ if they expire in-the-money. This means that depending on how we define the states $\omega^{i}$ , unlike the elementary contracts, options can make payments in more than one state. But this difference is really not that important since we can get all desired. $C_{i}$ from option prices, if options trade for all strikes. $K.$ In other words, the pricing framework that we are discussing here. will be much more useful in practice than it seems at first..  

As to the second question, it has to be said that, in practice, few strikes of an option series trade actively. This suggests that the finite state assumption may not be that unrealistic after all..  
