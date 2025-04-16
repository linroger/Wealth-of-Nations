---
tags:
  - '#binomial_model'
  - '#derivative_pricing'
  - '#expected_return'
  - '#option_pricing'
  - '#real_world_vs_risk_neutral'
  - '#risk_aversion'
  - '#risk_free_rate'
  - '#risk_neutral_valuation'
---
# 13.2 RISK-NEUTRAL VALUATION  

We are now in a position to introduce a very important principle in the pricing of. derivatives known as risk-neutral valuation. This states that, when valuing a derivative, we can make the assumption that investors are risk-neutral. This assumption means investors do not increase the expected return they require from an investment to compensate for increased risk. A world where investors are risk-neutral is referred to as a risk-neutral world. The world we live in is, of course, not a risk-neutral world. The higher the risks investors take, the higher the expected returns they require. However, it turns out that assuming a risk-neutral world gives us the right option price for the world we live in, as well as for a risk-neutral world. Almost miraculously, it finesses the problem that we know hardly anything about the risk aversion of the buyers and sellers of options.  

Risk-neutral valuation seems a surprising result when it is first encountered. Options are risky investments. Should not a person's risk preferences affect how they are priced? The answer is that, when we are pricing an option in terms of the price of the underlying stock, risk preferences are unimportant. As investors become more riskaverse, stock prices decline, but the formulas relating option prices to stock prices remain the same.  

A risk-neutral world has two features that simplify the pricing of derivatives:  

1. The expected return on a stock (or any other investment) is the risk-free rate. 2. The discount rate used for the expected payoff on an option (or any other instrument) is the risk-free rate..  

Returning to equation (13.2), the parameter $p$ should be interpreted as the probability of an up movement in a risk-neutral world, so that $1-p$ is the probability of a down movement in this world. (We assume $u>e^{r T}$ , so that $0<p<1.$ ) The expression  

$$
p f_{u}+(1-p)f_{d}
$$  

is the expected future payoff from the option in a risk-neutral world and equation (13.2). states that the value of the option today is its expected future payoff in a risk-neutral world discounted at the risk-free rate. This is an application of risk-neutral valuation..  

To prove the validity of our interpretation of $p$ , we note that, when $p$ is the probability of an up movement, the expected stock price $E(S_{T})$ at time $T$ is given by  

$$
E(S_{T})=p S_{0}u+(1-p)S_{0}d
$$  

or  

$$
E(S_{T})=p S_{0}(u-d)+S_{0}d
$$  

Substituting from equation (13.3) for $p$ gives  

$$
E(S_{T})=S_{0}e^{r T}
$$  

This shows that the stock price grows, on average, at the risk-free rate when $p$ is the probability of an up movement. In other words, the stock price behaves exactly as we would expect it to behave in a risk-neutral world when $p$ is the probability of an up movement.  

Risk-neutral valuation is a very important general result in the pricing of derivatives.. It states that, when we assume the world is risk-neutral, we get the right price for a. derivative in all worlds, not just in a risk-neutral one. We have shown that risk-neutral valuation is correct when a simple binomial model is assumed for how the price of the the stock evolves. We will prove it when the stock price follows a continuous-time. stochastic process in Chapter 15. It is a result that is true regardless of the assumptions made about the evolution of the stock price..  

To apply risk-neutral valuation to the pricing of a derivative, we first calculate what the probabilities of different outcomes would be if the world were risk-neutral. We then calculate the expected payoff from the derivative and discount that expected payoff at the risk-free rate of interest.  

# The One-Step Binomial Example Revisited  

We now return to the example in Figure 13.1 and illustrate that risk-neutral valuation gives the same answer as no-arbitrage arguments. In Figure 13.1, the stock price is currently $\$20$ and will move either up to $\$22$ or down to $\$18$ at the end of 3 months. The option considered is a European call option with a strike price of $\$21$ and an expiration date in 3 months. The risk-free interest rate is $4\%$ per annum.  

We define $p$ as the probability of an upward movement in the stock price in a riskneutral world. We can calculate. $p$ from equation (13.3). Alternatively, we can argue that the expected return on the stock in a risk-neutral world must be the risk-free rate of $4\%$ This means that $p$ must satisfy  

$$
22p+18(1-p)=20e^{0.04\times3/12}
$$  

or  

$$
4p=20e^{0.04\times3/12}-18
$$  

That is, $p$ must be 0.5503.  

At the end of the 3 months, the call option has a 0.5503 probability of being worth 1 and a 0.4497 probability of being worth zero. Its expected value is therefore  

$$
0.5503\times1+0.4497\times0=0.5503
$$  

In a risk-neutral world this should be discounted at the risk-free rate. The value of the option today is therefore  

$$
0.5503e^{-0.04\times3/12}
$$  

or $\$0.545$ . This is the same as the value obtained earlier, demonstrating that noarbitrage arguments and risk-neutral valuation give the same answer..  

# Real World vs. Risk-Neutral World  

It should be emphasized that. $p$ is the probability of an up movement in a risk-neutral world. In general, this is not the same as the probability of an up movement in the real world. In our example. $p=0.5503$ . When the probability of an up movement is 0.5503, the expected return on both the stock and the option is the risk-free rate of $4\%$ Suppose that, in the real world, the expected return on the stock is $10\%$ and $p^{*}$ is the probability of an up movement in this world. It follows that  

$$
22p^{*}+18(1-p^{*})=20e^{0.10\times3/12}
$$  

so that $p^{*}=0.6266$  

The expected payoff from the option in the real world is then given by  

$$
p^{*}\times1+(1-p^{*})\times0
$$  

or 0.6266. Unfortunately, it is not easy to know the correct discount rate to apply to the. expected payoff in the real world. The return the market requires on the stock is. $10\%$ and this is the discount rate that would be used for the expected cash flows from an investment in the stock. A position in a call option is riskier than a position in the. stock. As a result the discount rate to be applied to the payoff from a call option is greater than $10\%$ , but we do not have a direct measure of how much greater than. $10\%$ it should be.1 Using risk-neutral valuation solves this problem because we know that in a risk-neutral world the expected return on all assets (and therefore the discount rate to use for all expected payoffs) is the risk-free rate..  
