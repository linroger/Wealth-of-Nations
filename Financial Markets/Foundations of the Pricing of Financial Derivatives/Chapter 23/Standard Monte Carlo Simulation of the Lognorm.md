---
tags:
  - '#asset_price_simulation'
  - '#black_scholes_merton_model'
  - '#european_call_option'
  - '#excel_rand_function'
  - '#lognormal_diffusion'
  - '#monte_carlo_simulation'
  - '#option_pricing'
  - '#risk_neutral_measure'
  - '#simulation_error'
  - '#standard_normal_random_variable'
---
# 23.1 STANDARD MONTE CARLO SIMULATION OF THE LOGNORMAL DIFFUSION

Recall that the Black-Scholes-Merton model is based on geometric Brownian motion with risk-neutral growth of the underlying asset,.

$$
d S_{t}=S_{t}r_{c}d t+S_{t}\sigma d W_{t},
$$

where the stochastic integral solution can be expressed as2

$$
S_{T}=S_{t}e^{\left[\left(r_{c}-\frac{\sigma^{2}}{2}\right)\tau+\sigma\sqrt{\tau}\varepsilon\right]},
$$

where, as we have previously shown, the term $\varepsilon$ is a normally distributed random number with mean equal to 0 and standard deviation equal to 1. Note that we do not add a time subscript to this epsilon because it is generic within the simulator and time to expiration is handled separately.

The objective of Monte Carlo simulation is to generate a sample of terminal asset. prices, $S_{T}$ Following Boyle (1977), we desire a simulation that converges quickly to. the annualized, continuously compounded rates of return satisfying the following two conditions:

$$
r_{c}=\frac{E_{t}\left[\ln\left(\frac{S_{T}}{S_{t}}\right)\right]}{\tau}~\mathrm{and}~\
$$

$$
\sigma^{2}=\frac{\operatorname{var}_{t}\left[\ln\left(\frac{S_{T}}{S_{t}}\right)\right]}{\tau}.
$$

Note also that by using the risk-free rate as the expected return, we are operating under. the risk-neutral measure. We shall ultimately be consistent with that assumption by discounting simulated values at the risk-free rate..

What we want to do is generate future asset prices from Equation (23.2). It is actually quite easy. We learned how to do this in Chapter 10, where we simulated Brownian motion. A standard normal random variable, denoted here as $\varepsilon$ , can be approximated with a slight adjustment to Excel's Rand() function, which produces a uniform random number between 0 and 1, meaning that it generates numbers between O and 1 with equal probability. A. good approximation for a standard normal variable is obtained by the Excel formula,. = RandO + RandO + RandO + RandO + RandO + RandO + Rando + Rando + Rando + Rando + Rando + Rando - 6.0, or simply 12 uniform random numbers minus 6.0.3

After generating one standard normal random variable, we then simply insert it into. the right-hand side of the above formula for. $d S$ . But the key question is over what period. of time this price change applies. Note in Equation (23.1) the continuous increment, $d t.$ That means the price change is instantaneous, which means an infinitesimally small unit. of time. We cannot do simulation in continuous time, so we have to choose a unit of time. Let us choose one day. That is, we change Equation (23.2) to.

$$
S_{\Delta t}=S_{t}e^{\left[\left(r_{c}-\frac{\sigma^{2}}{2}\right)\Delta t+\sigma\sqrt{\Delta t}\varepsilon\right]}
$$

and let $\Delta t=1/365$ , or approximately 0.0027. So, assuming $N$ days in the life of the option,. the expiration is $\tau=N/365$ . Recall from Chapter 2, there is some debate on whether to use trading days rather than calendar days. In the US, there are approximately 252 trading days. in a year. We then simulate the price change for day 1, which generates a new price, which. forms the base of the price change for day 2. We continue this until we have reached the expiration, day $N.$ Now, we have an estimate of the asset price at expiration,. $S_{T}.$ We then compute the price of the option at expiration according to the standard formulas,. $\operatorname*{max}(0,$ $S_{T}-X)$ for a call or $\operatorname*{max}(0,X-S_{T})$ for a put, where $X$ is the exercise price and $S_{T}$ is the asset price at expiration. This operation produces one possible option value at expiration. We then repeat this procedure many thousands of times, take the average value of the call at expiration, and discount that value at the risk-free rate. Some users also compute.

the standard deviation of the call prices in order to obtain a feel for the possible error in estimating the price.

Alternatively, we can simply simulate the terminal asset price directly rather. than the entire path. Thus, we deploy a Monte Carlo simulation and apply it within Equation (23.2). So now let us price a call option on an asset. The asset price is 55, the exercise price is 50, the continuously compounded risk-free rate is 0.05, the volatility is 0.40, and the time to expiration is 0.75; that is, the option expires in nine months, or three-quarters of a year. Inserting the previous approximation formula for a standard. normal random variable in any cell in an Excel spreadsheet produces a random number. Suppose that number is 0.733449. Inserting into Equation (23.2), we obtain.

$$
\begin{array}{r}{S_{0.75}=55e^{\left[\left(0.05-\frac{0.4^{2}}{2}\right)0.75+0.4\sqrt{0.75}(0.733449)\right]}=69.33.}\end{array}
$$

Thus, the simulated value of the asset at expiration is $\$69.33$ . At that price, the option will be worth $\operatorname*{max}(0,69.33-50)=19.33$ at expiration. We then draw another random number. Suppose we get -0.18985. Inserting into Equation (23.2), we obtain

$$
\begin{array}{r}{S_{0.75}=55e^{\left[\left(0.05-\frac{0.4^{2}}{2}\right)0.75+0.4\sqrt{0.75}(-0.18985)\right]}=50.35.}\end{array}
$$

This gives us an asset price of $\$50.35$ and an option payoff of $\operatorname*{max}(0,50.35-50)=0.35.$ Both of these cases are in-the-money, but many will be out-of-the-money, leading to an option value of zero. We repeat this procedure several thousand times, after which we take an average of the simulated option prices and then discount that average to the present using the present value formula e-0.0s(o.7s).

Recall one way to represent the call value is the present value of the expected terminal. payout, where the discounting is based on the risk-free rate and the expected terminal. value is based on the underlying asset growing at the risk-free rate. With Monte Carlo simulation, we replace the expected terminal value with the average terminal value or

$$
c_{t}=P V_{r}[E_{t}(c_{T})]=e^{-r_{c}(T-t)}\left[\frac{1}{n}\sum_{i=1}^{n}\operatorname*{max}\left(0,S_{t}e^{\left[\left(r_{c}-\frac{\sigma^{2}}{2}\right)\Delta t+\sigma\sqrt{\Delta t}\varepsilon_{i}\right]}-X\right)\right].
$$

Naturally every simulation is different because each set of random numbers is different. A Monte Carlo procedure written in the $\mathrm{R}$ programming language produced Table 23.1 values for this call, whose actual Black-Scholes-Merton price is 11.02, where the number of random drawings is the sample size,. $_n$ If we reran each simulation, we would obtain different values. As the number of simulations increase, the variation declines, and we get very close to the Black-Scholes-Merton value of 11.02.

To illustrate further, we show several figures with a new set of parameters. Consider now a stock trading at $\$100$ with exercise price of $\$100$ . Further, assume a $5\%$ interest rate, $30\%$ volatility, and one year to expiration. Figure 23.1 illustrates 200 separate sets of simulations where the sample size increases by a factor of 10. Panel A demonstrates moving from a sample size of 10 to 100 we observe a significant decline in the variation of simulated call prices when compared to the BSM model price of $\$14.23$ . Clearly, as we move from 10 to 10,o00 illustrated in Panel A the variation consistently declines. Note that in Panel B at 100,000 $\left(1\mathrm{e}{+}05\right)$ , we rescale the $y$ -axis, enabling you to see the further decline in variation. Without rescaling, the call values would appear constant as the slight. variations would be undetectable.

IABLE 23.1 Monte Carlo Price of Standard European Call Option


<html><body><table><tr><td>n (number of simulations)</td><td>OptionPrice</td></tr><tr><td>1,000</td><td>11.42</td></tr><tr><td>5,000</td><td>10.75</td></tr><tr><td>10,000</td><td>11.11</td></tr><tr><td>25,000</td><td>11.02</td></tr><tr><td>50,000</td><td>10.94</td></tr><tr><td>100,000</td><td>11.05</td></tr><tr><td>1,000,000</td><td>11.02</td></tr></table></body></html>

Given the computational time required for large sample sizes, there are several ways to reduce the errors encountered with simulation. We explore several of these methods next.

![](images/39ca9c8b0875ff84e8365682caf3c6fc61e49b55192a748a12c9dbece1c5ef5d.jpg)
Panel A. y-Axis Scale from $\$0$ to $\$40$
FGURE 23.1 Sample Error and Monte Carlo Price of Standard European Call Option

![](images/dd8ab38acfa285bc95787fea83490fb2e842204d746d8ade7b4a2c6a63636605.jpg)
Panel B. y-Axis Scale from $\$14.0$ to $\$14.5$

# FIGURE 23.1Continued
