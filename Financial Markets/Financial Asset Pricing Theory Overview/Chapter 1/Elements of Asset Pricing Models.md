---
tags:
  - asset_pricing
  - consumption
  - financial_assets
  - investors
  - stochastic_process
aliases:
  - Asset Pricing Models
  - Elements of Asset Pricing
key_concepts:
  - financial asset characteristics
  - future asset payments
  - individual consumption modeling
  - institutional investors role
  - stochastic dividend process
---

# 1.2 Elements of asset pricing models  

# 1.2.1 Assets  

For potential investors the important characteristics of a financial asset or any other investment. opportunity are its current price and its future payments which the investor will be entitled to if she. buys the asset. Stocks deliver dividends to owners. The dividends will surely depend on the wellbeing of the company. Bonds deliver coupon payments and repayments of the outstanding debt, usually according to some predetermined schedule. For bonds issued by most governments, you might consider these payments to be certain, i.e. risk-free. On the other hand, if the government bond promises certain dollar payments, you will not know how many consumption goods you will be able to buy for these dollar payments, that is the payments are risky in real terms. The. payments of bonds issued by corporations are also uncertain. The future payments of derivatives. such as forwards, futures, options, and swaps depend on the evolution of some underlying random variable and therefore are also uncertain.  

Let us simply refer to the payments of any asset as dividends. More precisely, a "dividend" means the payment of a given asset at a given point in time. The uncertain dividend of an asset at a given point in time is naturally modeled by a random variable. If an asset provides the owner with payments at several points in time, we need a collection of random variables (one for each payment date) to represent all the dividends. Such a collection of random variables is called a stochastic process. A stochastic process is therefore the natural way to represent the uncertain fow of dividends of an asset over time. We will refer to the stochastic process representing the dividends of an asset as the dividend process of the asset.  

# 1.2.2 Investors  

In reality, only a small part of the trading in financial markets is executed directly by individuals while the majority of trades are executed by corporations and financial institutions such as pension funds, insurance companies, banks, broker firms, etc. However, these institutional investors trade on behalf of individuals, either customers or shareholders. Productive firms issue stocks and corporate bonds to finance investments in production technology they hope will generate high earnings and, consequently, high returns to their owners in future years. In the end, the decisions taken at the company level are also driven by the desires of individuals to shift consumption opportunities across time and states. In our basic models we will assume that all investors are individuals and ignore the many good reasons for the existence of various intermediaries. For example, we will assume that assets are traded without transaction costs. We will also ignore taxes and the role of the government and central banks in the financial markets. Some authors use the term "agent" or "investor' instead of "individual," maybe in order to indicate that some investment decisions are taken by other decision-making units than individual human beings..  

How should we represent an individual in an asset pricing model? We will assume that individuals basically care about their consumption of goods and services throughout their life. The consumption of a given individual at a future point in time is typically uncertain and we will therefore represent it by a random variable. The consumption of an individual at all future dates is represented by a stochastic process, the consumption process of the individual. Although real-life economies offer a large variety of consumption goods and services, in our basic models we will. assume that there is only one good available for consumption and that each individual only cares about her own consumption and not the consumption of other individuals. The single consump-. tion good is assumed to be perishable, i.e. it cannot be stored or resold but has to be consumed immediately. In more advanced models discussed in later chapters we will in fact relax these assumptions and allow for multiple consumption goods, e.g. we will introduce a durable good (like a house), and we will also discuss models in which the well-being of an individual also depends on what other individuals consume, which is often referred to as the "keeping up with the Jones'es" property. Both extensions turn out to be useful in bringing our theoretical models closer to real-life financial data but it is preferable to understand the simpler models first. Of course, the well-being of an individual will also be affected by the number of hours she works, the physical and mental challenges offered by her position, etc., but such issues will also be ignored in basic models..  

We will assume that each individual is endowed with some current wealth and some future. income stream from labor, gifts, inheritance, etc. For most individuals the future income will be uncertain. The income of an individual at a given future point in time is thus represented by. a random variable and the income at all future dates is represented by a stochastic process, the income process. We will assume that the income process is exogenously given and hence ignore. labor supply decisions.  

If the individual cannot make investments at all (not even save current wealth), it will be.   
impossible for her to currently consume more than her current wealth and impossible to consume.   
more at a future point in time than her income at that date. Financial markets allow the individual   
to shift consumption opportunities from one point in time to another, e.g. from working life to.   
retirement, and from one state of the world to another, e.g. from a state in which income is.  

extremely high to a state where income is extremely low. The prices of financial assets define the prices of shifting consumption through time and states of the world. The individuals' desire. to shift consumption through time and states will determine the demand and supply and hence the equilibrium prices of the financial assets. To study asset pricing we therefore have to model. how individuals choose between different, uncertain consumption processes. The preferences for consumption of an individual is typically modeled by a utility function. Since this is a text on asset pricing, we are not primarily interested in deriving the optimal consumption stream and the. associated optimal strategy for trading financial assets. However, since asset prices are set by the decisions of individuals, we will have to discuss some aspects of optimal consumption and trading..  

# 1.2.3 Equilibrium  

For any given asset, i.e. any given dividend process, our aim is to characterize the "reasonable" price or the set of "reasonable" prices. A price is considered reasonable if the price is an equilibrium price. An equilibrium is characterized by two conditions: (1) supply equals demand for any asset, i.e. markets clear, (2) any investor is satisfied with her current position in the assets given her personal situation and the asset prices. Associated with any equilibrium is a set of prices for all assets and, for each investor, a trading strategy and the implied consumption strategy.  

# 1.2.4 The time span of the model  

As discussed above, the important ingredients of all basic asset pricing models are the dividends. of the assets available for trade and the utility functions, current wealth, and future incomes of the individuals that can trade the assets. We will discuss asset pricing in three types of models:  

1. one-period model: all action takes place at two points in time, the beginning of the period (time 0) and the end of the period (time 1). Assets pay dividends only at the end of the period and are traded only at the beginning of the period. The aim of the model is to characterize the prices of the assets at the beginning of the period. Individuals have some initial beginning-of-period wealth and (maybe) some end-of-period income. They can consume at both points in time.  

2. discrete-time model: all action takes place at a finite number of points in time. Let us denote the set of these time points by. $\mathcal{T}=\{0,1,2,\ldots,T\}$ . Individuals can trade at any of these time points, except at. $T$ , and consume at any time. $t\in\mathcal{T}$ . Assets can pay dividends at. any time in. $\mathcal{T}$ , except time 0. Assuming that the price of a given asset at a given point in time. is ex-dividend, i.e. the value of future dividends excluding any dividend at that point in time,. prices are generally non-trivial at all but the last point in time. We aim at characterizing. these prices.  

3. continuous-time model: individuals can consume at any point in time in an interval $\mathcal{T}=[0,T]$ .Assets pay dividends in the interval $(0,T]$ and can be traded in $[0,T)$ .Exdividend asset prices are non-trivial in $\lfloor0,T)$ . Again, our aim is to characterize these prices.  

In a one-period setting there is uncertainty about the state of the world at the end of the period. The dividends of financial assets and the incomes of the individuals at the end of the period will generally be unknown at the beginning of the period and thus modeled as random variables. Any quantity that depends on either the dividends or income will also be random variables. For example, this will be the case for the end-of-period value of portfolios and the end-of-period consumption of individuals.  

Both the discrete-time model and the continuous-time model are multi-period models and can potentially capture the dynamics of asset prices. In both cases,. $T$ denotes some terminal date in. the sense that we will not model what happens after time $T$ . We assume that $T<\infty$ but under some technical conditions the analysis extends to $T=\infty$  

Financial markets are by nature dynamic and should therefore be studied in a multi-period. setting. One-period models should serve only as a pedagogical first step in the derivation of the. more appropriate multi-period models. Indeed, many of the important conclusions derived in one-. period models carry over to multi-period models. Other conclusions do not. And some issues cannot be meaningfully studied in a one-period framework..  

It is not easy to decide on whether to use a discrete-time or a continuous-time framework for studying multi-period asset pricing. Both model types have their virtues and drawbacks. Both. model types are applied in theoretical research and real-life applications. We will therefore consider both modeling frameworks. The basic asset pricing results in the early chapters will be derived in both settings. Some more specific asset pricing models discussed in later chapters will only be presented in one of these frameworks. Some authors prefer to use a discrete-time model, others prefer a continuous-time model. It is comforting that, for most purposes, both models will result. in identical or very similar conclusions..  

At first, you might think that the discrete-time framework is more realistic. However, in reallife economies individuals can in fact consume and adjust portfolios at virtually any point in time.. Individuals are certainly not restricted to consume and trade at a finite set of pre-specified points in. time. Of course no individual will trade financial assets continuously due to the existence of explicit and implicit costs of such transactions. But even if we take such costs into account, the frequency. and exact timing of actions can be chosen by each individual. If we are really concerned about transaction costs, it would be better to include those in a continuous-time modeling framework.  

Many people will find discrete-time models easier to understand than continuous-time models and if you want to compare theoretical results with actual data it will usually be an advantage if the model is formulated with a period length closely linked to the data frequency. On the other hand, once you have learned how to deal with continuous-time stochastic processes, many results are clearer and more elegantly derived in continuous-time models than in discrete-time models. The analytical virtues of continuous-time models are basically due to the well-developed theory of stochastic calculus for continuous-time stochastic processes, but also due to the fact that integrals are easier to deal with than discrete sums, differential equations are easier to deal with than difference equations, etc.  
