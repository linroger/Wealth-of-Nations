---
tags:
  - call_option
  - forward_contract
  - futures_contract
  - geometric_brownian_motion
  - option_pricing
aliases:
  - Forward Price
  - Futures Option
  - Preview
  - Recap
key_concepts:
  - Convenience yield
  - Forward contract pricing
  - Futures contract
  - Geometric Brownian motion
  - Option payoff
---

# 22.4 RECAP AND PREVIEW

In this chapter, we introduced a different type of derivative, the forward contract and its. variant the futures contract. We showed how these derivatives are priced, which is by the same principle as option pricing, but which does not require a dynamic hedge. As such,

the math is much simpler. We also took a look at options on forwards and futures, which is our first attempt to integrate both options, which have nonlinear payoffs, and forwards and futures, which have linear payoffs.

We have now completed Part IV. In Part V, we take up two methods of obtaining numerical solutions for option prices.

# QUESTIONS AND PROBLEMS

1 Assume at time O a five-year forward contract was entered at $\$75$ You have been tasked with determining the fair value of this contract after two years. At that. time, the underlying instrument price is. $\$70$ and the interest rate is. $4.89\%$ (annual compounding). Calculate the forward price after two years as well as the value of the initial forward contract entered at time 0..

2 Assuming the underlying follows geometric Brownian motion,. $d S_{t}=S_{t}\alpha d t+S_{t}\sigma d\mathrm{W}_{t}.$ derive the stochastic process of the forward price where the interest rate and dividend yield are expressed in continuous compounding, that is, $F_{0}(T)=S_{0}e^{\left(r_{c}-\delta\right)\tau}$

3 Derive the delta of a call option on a futures contract assuming

$$
\begin{array}{l}{{c_{t}=e^{-r_{c}\tau^{*}}\left[f_{t}N\left(d_{1}\right)-X N\left(d_{2}\right)\right]}}\ {{{}}}\ {{d_{1}=\frac{\ln\left(\frac{f_{t}}{X}\right)+\left(\frac{\sigma^{2}}{2}\right)\tau^{*}}{\sigma\sqrt{\tau^{*}}}}}\ {{{}}}\ {{d_{2}=d_{1}-\sigma\sqrt{\tau^{*}}.}}\end{array}
$$

Hint: It is helpful to use the following relationship between these two probability density functions:

$$
n\big(d_{2}\big)=\frac{e^{r_{c}\tau^{*}}f_{t}}{X}n\big(d_{1}\big).
$$

4 Derive the gamma of a call option on a futures contract.

5Derive the theta of a call option on a futures contract.

6  Demonstrate that the call option on futures model is valid when compared to the partial differential equation. Specifically, substitute the partial derivatives in the PDE and demonstrate coherence.

7  Suppose the futures price is $\$24.8$ , the exercise price is $\$24$ , the time to expiration is 4.0, the interest rate is $1.0\%$ , continuously compounded, and the volatility is $30\%$ Compute the call and put futures option prices.

# NOTES

1. We shall see that it is possible that the two parties can offset or negate their transaction before the expiration date, and one party can sell its obligation to another party. This is the only way in which exercise is avoided, but each party must still effectively do something for the other, and the arrangement must be fair from the perspective of both parties. In an option, however, the long. can simply walk away without doing anything.
2. Options can also be created on the over-the-counter market, or on an exchange. Forwards, however, are not offered on exchanges, though they can be offered in a near-exchange manner, such as on electronic trading platforms..
3. Terminal option payoffs are piecewise linear rather than simply linear.
4. We shall discuss what happens if. $r$ is not constant.
5. Observers of futures markets note that futures prices are sometimes not equal to the spot price. grossed up by the interest plus the carrying costs as a result of a rather vaguely specified benefit called the convenience yield. This effect is a factor in the pricing of the underlying asset that occurs sometimes in shortages, wherein the underlying asset has an abnormally high price, a result of tight market conditions. When this happens, the asset is hard to borrow because owners hold on to it. Shorting is, thus, virtually impossible and the futures could appear to violate the no-arbitrage formula, Equation (22.3), when in fact the effect is driven by an inability to short the asset. The deviation of the futures price from the no-arbitrage formula is, thus, often plugged with a concept called the convenience yield. For more details, see Brooks (2012).
6. As we said, the value of the futures is the accumulated price change since the last settlement. Because there has been no previous settlement, the value is zero.
7. It may be a little unclear in taking the first derivative with respect to time as to why we obtain the $-r$ We have to differentiate $\tau$ with respect to $t$ The parameter $\tau$ is the time to expiration in years. The parameter $t$ is just a time indicator. We can think of it somewhat like the value of 1/365, though it is technically a smaller unit than 1/365. Nonetheless, the effect is the same when we differentiate $\tau$ . In other words, the derivative of $\tau$ with respect to $t$ is simply $-1$
8. These points are covered in considerable detail in Brenner, Courtadon, and Subrahmanyam (1985).

# Numerical Methods

# Monte Carlo Simulation

bilities assumed to be associated with a source of uncertainty, such as the sales of a new. product or, more appropriately for our purposes, stock prices, interest rates, exchange. rates, or commodity prices. Outcomes associated with these random drawings are then analyzed to determine the likely results and the associated risk. Oftentimes this technique is called Monte Carlo simulation, being named for the city of Monte Carlo, which is noted. for its casinos.

Gambling analogy notwithstanding, Monte Carlo simulation is a powerful and widely. used technique for dealing with uncertainty in many aspects of business operations. For our purposes, it has been shown to be an accurate method of pricing options and particularly. useful for types of options for which no known formula exists..

To facilitate an understanding of the technique, we shall look at how Monte Carlo. simulation has been used to price standard European options.1 Of course, we know that. under the appropriate assumptions, the Black-Scholes-Merton model is the correct method of pricing these options, so Monte Carlo simulation is not really needed. It is useful, however, to conduct this demonstration under the assumptions of the Black-Scholes-Merton model, because it shows the accuracy of the technique for a simple option of which the exact price is easily obtained from a known formula. That is, it gives us a benchmark from. which to judge the accuracy of the simulation..

Unfortunately, Monte Carlo simulation is not very practical for American options because it works by simulating prices forward, whereas the early exercise decision is best. valued by positioning oneself at expiration and working backwards, as we do in the binomial model.
