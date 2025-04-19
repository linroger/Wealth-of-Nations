---
tags:
  - '#arbitrage'
  - '#binomial_model'
  - '#martingale'
  - '#no_arbitrage_condition'
  - '#option_pricing'
  - '#risk_aversion'
  - '#risk_neutral_pricing'
  - '#risk_neutral_probabilities'
---
# 6.2 RISK-NEUTRAL PRICING IN DISCRETE TIME

One of the most important results derived from option pricing theory is that all assets can be valued via a risk neutrality argument. Unfortunately, risk-neutral pricing has been a source of much confusion. Those who do not understand the process are led to believe that some mysterious sleight of hand has been done and that the resulting price is somehow tainted by ignoring the risk. In fact, risk-neutral pricing makes no such assumption of risk neutrality. It simply uses the assumption that no arbitrage opportunities exist rather than the assumption that investors are risk averse to motivate the pricing process.

The point is most easily made in a simple model in which a risky asset has two future outcomes. The outcomes themselves are known, but we do not know which will occur. We can assign probabilities, though as we will show later, these probabilities are not required for risk-neutral pricing. This type of framework, in which an asset has two possible future outcomes, is sometimes called a two-state model but more often called a binomial model. On the surface it seems that this model oversimplifies things. Naturally in the real world, there are more than two future outcomes. That problem can be easily accommodated by allowing multiple time periods such that each realized outcome is followed by two more possible outcomes, and so forth. But more fundamentally, a binomial framework permits. a simplified but powerful accommodation of uncertainty. As long as we acknowledge that we do not know which outcome will occur, we have built uncertainty into the model..

Consider an asset currently priced at $S$ whose price one period later can be. $S u$ with probability $q$ or $S d$ with probability $1-q$ . The factors $\boldsymbol{\mathscr{u}}$ and $d$ represent one plus the percentage change in the asset price. Let us first consider how that asset would be priced in a world of risk-averse investors. Under risk aversion, any risky asset is priced as the discounted value of its expected future price. The expected future price of the asset is $q S u+(1-q)S d$ Consequently, the current price would be given as.

$$
S=\frac{q S u+(1-q)S d}{1+k_{R}},
$$

where $k_{R}$ is the discount rate that reflects an adjustment for risk. For risk-averse investors, the discount rate will consist of the risk-free rate,. $r_{:}$ plus a risk premium. The rate $k_{R}$ is sometimes considered as having arisen out of an asset's covariance with the market, such. as in the capital asset pricing model (recall denoted CAPM), or some alternative model of market equilibrium, but it is not necessary to assume any such type of equilibrium. It can. simply be a subjective estimate of the premium a risk-averse investor expects to earn. For. a risk-neutral investor, the discount rate will be the risk-free rate..

Given knowledge of. $S,u.$ and $d$ let us restate the price of the asset in the following manner: First, we ask if there are probability values that can be substituted for $q$ and $1-q$ that permit us to change. $k_{R}$ to the risk-free rate,. $r_{\mathrm{{i}}}$ , while keeping the price exactly as it was. In the absence of arbitrage, the answer is yes, as we demonstrate next.

Consider a world of two assets: the stock and a risk-free bond. Now let us assume that $d>1+r.$ In other words, the worst return on the stock is better than the risk-free interest rate. It would not take a genius to figure out that one could borrow money to pay the price of the stock at the risk-free rate, buy the stock, and then merely wait on the outcome. If the stock goes to. $S u$ , that is enough money to pay back the loan $S(1+r)$ and would leave. $S u-S(1+r)=S[u-(1+r)]$ , which is positive. If. $d>1+r$ , then, if the. worst-case outcome occurs, the investor will have $S d-S(1+r)=S[d-(1+r)]$ . Again, we assumed $d>1+r,$ , so this outcome is positive. In simple terms, if the worst outcome of the stock is better than the risk-free rate, an arbitrage profit is available. Clearly investors would take advantage of this situation, and their trading activity would likely adjust the stock price. With this new adjusted stock price $\boldsymbol{\mathscr{u}}$ and $d$ would change until there is no. arbitrage profit available. And naturally, we could not have the risk-free rate exceed the up return, $u-1$ , on the stock, for in that case no one would buy the stock, so its value would be zero. So ultimately it must be that $u>1+r>d$ 2.

Given that $u>1+r>d$ , we will now demonstrate that it is possible to find weights that we will identify as $\phi$ (lowercase Greek letter, pronounced $^{\mathrm{{66}}}\mathrm{{phi}}^{\mathrm{{,99}}})$ and $1-\phi$ that are consistent with the statement $\phi u+(1-\phi)d=1+r$ or the equivalent statement, $\phi=(1+$ $r-d)/(u-d)$ . If we multiply by $S$ and do some rearranging, we obtain the following:

$$
S=\frac{\phi S u+(1-\phi)S d}{1+r}.
$$

This expression looks identical to a valuation equation. If $\phi$ were the probability of. the price $S u$ occurring and $1-\phi$ were the probability of the price. $S d$ occurring, then the.

numerator would be the expected price. To value an asset, we discount the expected price by an appropriate rate. If the risk-free rate $r$ was the appropriate discount rate, then $S$ would be the price. It is a fact that $S$ is the asset price and also a fact that $S u$ and $S d$ are the possible future asset prices, but $\phi$ is not the probability of an upward move. Nonetheless, $\phi$ looks a lot like a probability and is used like a probability. In addition, $r$ is not the appropriate discount rate when applying the real probability, but it looks a lot like it and is used in that manner. The numerator of Equation (6.2) is sometimes referred to as a certainty equivalent, which is an amount of cash that an investor is willing to receive rather than take a stated risk.

What we have done here is change the probabilities from their true values, $q$ and $1-q$ to alternative values, $\phi$ and $1-\phi$ , such that we can use the risk-free rate as the discount rate. These probabilities are sometimes referred to as pseudo-probabilities because they are not the real probabilities, but they behave like them. They are more appropriately referred to as risk-neutral probabilities and sometimes martingale or equivalent martingale probabilities. We shall explain the martingale concept in a few paragraphs.

The adjustment that enabled us to obtain Equation (6.2) is clearly correct and acceptable, inasmuch as it produces the correct stock price, S. What enables us to do this is the simple no-arbitrage condition that $u>1+r>d$ The only information we need to know is the up and down factors and the risk-free rate. The up and down factors characterize the volatility of the asset. We have made no assumptions about how investors address risk. Indeed, what we have done is perfectly compatible with risk aversion. If investors are risk averse, which is what Equation (6.1) says, then Equation (6.2) also gives the value of the asset.

What we have just illustrated is called the arbitrage theorem. It simply states that if. there are no opportunities for arbitrage, then it is possible to state the price of the asset in. terms of risk-neutral probabilities where the discounting is done at the risk-free rate. The theorem goes two ways. If it is possible to state the price of the asset in this manner, then. there are no arbitrage possibilities.

Calling $\phi$ and $1-\phi$ risk-neutral probabilities can be, however, a source of much con-. fusion, inasmuch as it may imply that we are assuming investors are risk neutral, which. we certainly are not. Alternatively, these probabilities are sometimes called martingale or equivalent martingale probabilities. A martingale is a stochastic process in which the expected return of the asset is the current value of the asset. Under the equivalent martingale approach, however, the future asset price is restated so as to be already discounted at the risk-free rate. That is, the right-hand side of Equation (6.2) is. $\phi\widehat{S}u+(\dot{1}-\phi)\widehat{S}d$ where $\widehat{S}=S/(1+r)$ is an adjusted asset price. In other words, the future $S$ value is the future price already discounted.

There is a definite relationship between the binomial probability, $\phi$ , and the actual probability, $q$ . Define the market price of risk of the stock as $\lambda=[E(R)-r]/\sigma$ where $E(R)$ is the expected return on the stock, which is $E(R)=q u+(1-q)d-1.$ The stock's variance is defined as $\sigma^{2}=q(1-q)(u-d)^{2}$ . These statements hold by definition. They are simply the expected value and volatility of a one-period binomially distributed variable, the return on the asset, that can go up to $S u$ or down to $S d$ Substituting these values into the risk premium and noting that $\phi=(1+r-d)/(u-d)$ , we obtain the result,

$$
\phi=q-\lambda\sqrt{q(1-q)}.
$$

Thus, the binomial probability is the actual probability minus the risk premium times the square root term, which is related to the volatility. In short, knowing the binomial probability, $\phi=(1+r-d)/(u-d)$ , tells us everything we need to know to avoid having to know the market price of risk, $\lambda$ , and the actual probability, $q$

Note that we have not introduced options. The point is easily established without the use of options. When introducing options, however, it is easily shown that a call option can. be replicated by positions in the asset and the risk-free bond. That being the case, the call. is a redundant asset. Consequently, introducing a redundant asset does nothing to change. the nature of the market, provided, of course, that the redundant asset is properly priced.. But that will be true by the requirement of no arbitrage..

Though we have introduced this point in the simple binomial framework, it can also. be established, albeit with more mathematical complexity in the continuous time models. This topic is covered in Chapter 12..
