---
tags:
  - arbitrage
  - discrete_time
  - law_of_one_price
  - one_period_framework
  - risk_free_profit
aliases:
  - Arbitrage Definition
  - Arbitrage Opportunity
  - Risk-Free Profit
key_concepts:
  - Absence of arbitrage implies law
  - 'Arbitrage: risk-free profit'
  - One-period framework defined
  - Prices obey Law of One Price
  - Self-financing trading strategy
---

# 3.4 Arbitrage  

We have already made an assumption about prices, namely that prices obey the Law of One Price, i.e. prices are linear. We will now make the slightly stronger assumption that prices are set so that there is no arbitrage. An arbitrage is basically a risk-free profit.  

# 3.4.1 The one-period framework  

In the one-period framework we define an arbitrage as a portfolio $\pmb{\theta}$ satisfying one of the following. two conditions:  

(i) $P^{\theta}<0$ and $D^{\theta}\geq0$ (ii) $P^{\theta}\leq0$ and $D^{\theta}\geq0$ with $\mathbb{P}\left(D^{\theta}>0\right)>0$  

Here $D^{\theta}$ is the random variable that represents the dividend of the portfolio $\pmb{\theta}$ . The inequality $D^{\theta}\geq0$ means that the dividend will be non-negative no matter which state is realized, i.e.. $D^{\pmb{\theta}}(\omega)\geq0$ for all $\omega\in\Omega$ . (In a finite-state economy this can be replaced by the condition $D^{\theta}\geq0$ on the dividend vector, which means that all elements of the vector are non-negative. The condition $\mathbb{P}\left(D^{\theta}>0\right)>0$ can be replaced by the condition $D_{\omega}^{\theta}>0$ for some state $\omega$  

An arbitrage offers something for nothing. It offers a non-negative dividend no matter which state is realized and its price is non-positive so that you do not have to pay anything. Either you. get something today (case (i)) or you get something at the end in some state (case (ii)). This is. clearly attractive to any greedy individual, i.e. any individual preferring more to less. Therefore,. a market with arbitrage cannot be a market in equilibrium. Since we are interested in equilibrium. pricing systems, we need only to care about pricing systems that do not admit arbitrage..  

Absence of arbitrage implies that the law of one price holds. To see this, first suppose that $P^{\theta}<\theta\cdot P$ . Then an arbitrage can be formed by purchasing the portfolio $\pmb{\theta}$ for the price of $P^{\theta}$ and, for each $i=1,\dots,I$ selling $\theta_{i}$ units of asset $i$ at a unit price of. $P_{i}$ . The end-of-period net. dividend from this position will be zero no matter which state is realized. The total initial price of the position is $P^{\theta}-\theta\cdot P$ , which is negative. Hence, in the absence of arbitrage, we cannot have that $P^{\theta}<\theta\cdot P$ . The inequality $P^{\theta}>\theta\cdot P$ can be ruled out by a similar argument.  

On the other hand, the law of one price does not rule out arbitrage. For example, suppose that there are two possible states. Asset 1 gives a dividend of. $0$ in state 1 and a dividend of 1 in state 2.  

and costs 0.9. Asset 2 gives a dividend of. $^{1}$ in state 1 and a dividend of 2 in state 2 and costs 1.6.. Suppose the law of one price holds so that the price of any portfolio $(\theta_{1},\theta_{2})^{\top}$ is $0.9\theta_{1}+1.6\theta_{2}$ Consider the portfolio $(-2,1)^{\top}$ i.e. a short position in two units of asset 1 and a long position of. on unite of asset 2. The dividend of this portfolio will be. $^{1}$ in state 1 and. $0$ in state 2 and the price is $0.9\cdot(-2)+1.6\cdot1=-0.2$ . This portfolio is clearly an arbitrage..  

# 3.4.2 The discrete-time and continuous-time frameworks  

In both the discrete-time and the continuous-time framework we define an arbitrage to be a selffinancing trading strategy $\pmb{\theta}$ satisfying one of the following two conditions:.  

(i) $V_{0}^{\theta}<0$ and $V_{T}^{\pmb\theta}\ge0$ with probability one, (ii) $V_{0}^{\theta}\leq0$ $V_{T}^{\pmb\theta}\ge0$ with probability one, and $V_{T}^{\pmb\theta}>0$ with strictly positive probability.  

As we have seen above, $V_{T}^{\theta}=D_{T}^{\theta}$ and $V_{0}^{\pmb\theta}=-D_{0}^{\pmb\theta}$ for self-financing trading strategies. We can. therefore equivalently define an arbitrage in terms of dividends. A self-financing trading strategy is an arbitrage if it generates non-negative initial and terminal dividends with one of them being strictly positive with a strictly positive probability. Due to our assumptions on the dividends of the individual assets, the absence of arbitrage will imply that the prices of individual assets are. strictly positive.  

Ruling out arbitrages defined in (i) and (ii) will also rule out shorter term risk-free gains. Suppose for example that we can construct a trading strategy with a non-positive initial value (i.e. a nonpositive price), always non-negative values, and a strictly positive value at some time $t<T$ .Then this strictly positive value can be invested in any asset until time. $T$ generating a strictly positive terminal value with a strictly positive probability. The focus on self-financing trading strategies is therefore no restriction. Note that the definition of an arbitrage implies that a self-financing trading strategy with a terminal dividend of zero (in any state) must have a value process identically equal to zero.  

# 3.4.3 Continuous-time doubling strategies  

In a continuous-time setting it is theoretically possible to construct some strategies that generate something for nothing. These are the so-called doubling strategies, which were apparently first mentioned in a finance setting by Harrison and Kreps (1979). Think of a series of coin tosses numbered $n=1,2,\ldots$ The $^{\textit{\textbf{\textit{1}}}}$ 'th coin toss takes place at time $1-1/n\in[0,1)$ . In the $^{\textit{\textbf{\textit{1}}}}$ 'th toss, you get $\alpha2^{n-1}$ if heads comes up, and looses $\alpha2^{n-1}$ Otherwise, where $\alpha$ is some positive number.. You stop betting the first time heads comes up. Suppose heads comes up the first time in toss number $(k+1)$ . Then in the first. $k$ tosses you have lost a total of $\alpha(1+2+\cdot\cdot\cdot+2^{k-1})=\alpha(2^{k}-1)$ Since you win $\alpha2^{k}$ in toss number $k+1$ , your total profit will be $\alpha2^{k}-\alpha(2^{k}-1)=\alpha$ . Since the probability that heads comes up eventually is equal to one, you will gain $\alpha$ with probability one.. The gain is obtained before time 1 and can be made as large as possible by increasing $\alpha$  

Similar strategies, with future dividends appropriately discounted, can be constructed in continuoustime models of financial markets- at least if a risk-free asset is traded--but are clearly impossible to implement in real life. As shown by Dybvig and Huang (1988), doubling strategies can be ruled out by requiring that trading strategies have values that are bounded from below, i.e. that some  

constant $K$ exists such that $V_{t}^{\pmb{\theta}}\geq-K$ for all $t$ . A trading strategy satisfying such a condition is said to be credit-constrained. A lower bound is reasonable since nobody can borrow an infinite amount of money. If you have a limited borrowing potential, the doubling strategy described above cannot be implemented. If you have no future income at all, $K=0$ seems reasonable. An alternative way of eliminating doubling strategies is to impose the condition that the value process of the trading strategy has finite variance, cf. Duffie (2001). For a doubling strategy the variance of the value process is in fact infinite.  

It seems evident that any greedy investor would implement a doubling strategy, if possible, since the investor will make a positive net return with a probability of one in finite time. However, Omberg (1989) shows that a doubling strategy may in fact generate an expected utility of minus infinity for risk-averse investors. In some events of zero probability a doubling strategy may result in outcomes associated with a utility of minus infinity. When multiplying zero and minus infinity in order to compute the expected utility, the result is indeterminate. Omberg computes the actual expected utility of the doubling strategy by taking an appropriate limit and finds that this is. minus infinity for commonly used utility functions that are unbounded from below. Although this questions the above definition of an arbitrage, we will stick to that definition which is also the. standard of the literature.  

In the rest of this book we will-often implicitly--assume that some conditions are imposed so that doubling strategies are not implementable or that nobody wants to implement them.  
