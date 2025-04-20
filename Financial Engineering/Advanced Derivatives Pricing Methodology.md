---
tags:
  - advanced_derivatives_pricing
  - derivative_securities
  - no_arbitrage
  - risk_management
  - valuation
aliases:
  - Advanced Pricing
  - Derivatives Pricing
  - P v. Q
key_concepts:
  - future cash flows
  - no-arbitrage models
  - risk-neutral probabilities
  - underlying security price
  - valuation replication hedging
---

# Overview  


Advanced Derivatives Pricing  

# Review: Valuation and investment in primary securities  

The securities have direct claims to future cash flows.  

o Valuation is based on forecasts of future cash flows and risk:  

DCF (Discounted Cash Flow Method): Discount time-series forecastec future cash flow with a discount rate that is commensurate with the.   
forecasted risk.   
We diversify as much as we can. There are remaining risks after.   
diversification - market risk. We assign a premium to the remaining.   
risk we bear to discount the cash flows..  

Investment: Buy if market price is lower than model value; sell otherwise.  

o Both valuation and investment depend crucially on forecasts of future cash flows (growth rates) and risks (beta, credit risk)..  

This is not what we do.  

# Compare: Derivative securities  

o Payoffs are linked directly to the price of an "underlying"' security.  

Valuation is mostly based on replication/hedging arguments.  

Find a portfolio that includes the underlying security, and possibly other related derivatives, to replicate the payoff of the target derivative security, or to hedge away the risk in the derivative payoff.   
Since the hedged portfolio is riskfree, the payoff of the portfolio can be discounted by the riskfree rate. No need to worry about the risk premium of a "zero-beta" portfolio.   
Models of this type are called "no-arbitrage" models.  

Key: No forecasts are involved. Valuation is based on cross-sectiona! comparison.  

It is not about whether the underlying security price will go up or down (growth rate or risk forecasts), but about the relative pricing relation. between the underlying and the derivatives under all possible scenarios..  

# Readings behind the technical jargons: P v. Q  

$\mathbb{P}$ : Actual probabilities that earnings will be high or low, estimated based on historical data and other insights about the company.  

Valuation is all about getting the forecasts right and assigning the. appropriate price for the forecasted risk - fair wrt future cashflows (and your risk preference)..  

$\mathbb{Q}$ :"Risk-neutral" probabilities that we can use to aggregate expected future payoffs and discount them back with riskfree rate, regardless of how risky the cash flow is.  

It is related to real-time scenarios, but it not to real-time probability.. You need to list all possible scenarios, but you do not need to forecast the probability of each scenario. Since the intention is to hedge away risk under all scenarios and. discount back with riskfree rate, we do not really care about the actual probability of each scenario happening.. We just care about what all the possible scenarios are and whether our hedging works under all scenarios..  

$\mathbb{Q}$ is not about getting close to the actual probability, but about being fair wrt the prices of securities that you use for hedging.,.  

# A Micky Mouse example  

Consider a non-dividend paying stock in a world with zero riskfree interest rate. Currently, the market price for the stock is \$10o. What should be the forward price for the stock with one year maturity?  

o The forward price is \$100.  

Standard forward pricing argument says that the forward price should be equal to the cost of buying the stock and carrying it over to maturity.   
The buying cost is \$100, with no storage or interest cost or dividend benefit.  

How should you value the forward differently if you have inside information that the company will be bought tomorrow and the stock price is going to. double?  

Shorting a forward at \$100 is still safe for you if you can buy the stock at \$100 to hedge.  

# Investing in derivative securities without insights  

o If you can really forecast the cashflow (with inside information), you probably do not care much about hedging or no-arbitrage modeling..  

What is risk to the market is an opportunity for you..   
You just lift the market and try not getting caught for insider trading.  

o If you do not have insights on cash flows and still want to invest in derivatives, the focus does not need to be on forecasting, but on cross-sectional consistency.  

-No-arbitrage pricing models can be useful.  

# Derivative products  

Forward & futures:  

Terminal Payoff: $(S_{T}-K)$ , linear in the underlying security price $(S_{T})$  

No-arbitrage pricing:  

Buying the underlying security and carrying it over to expiry generates the same payoff as signing a forward.. The forward price should be equal to the cost of the replicating portfolio (buy & carry). This pricing method does not depend on (forecasts) how the underlying security price moves in the future or whether its current price is fair. but it does depend on the actual cost of buying and carrying (not all things can be carried through time...), i.e., the implementability of the replicating strategy. $F_{t,T}=S_{t}e^{(r-q)(T-t)}$ , with $r$ and $q$ being continuously compounded rates of carrying cost (interest, storage) and benefit (dividend, foreign interest, convenience yield).  

# Derivative products  

Options:  

Terminal Payoff: Call $(S_{T}-K)^{+}$ , put - (K - S+)+.   
European, American, ITM, OTM, ATMV...  

No-arbitrage pricing:  

Can we replicate the payoff of an option with the underlying security so that we can value the option as the cost of the replicating portfolio?  

Can we use the underlying security (or something else liquid and with known prices) to completely hedge away the risk?.  

If we can hedge away all risks, we do not need to worry about risk premiums.  

No-arbitrage models:  

For forwards, we can hedge away all risks without assumption on price dynamics (only assumption on being able to buy and carry...) For options, we can hedge away all risks under some assumptions on the price dynamics and frictionless transactions.  

# Another Mickey Mouse example: A one-step binomial tree  

Observation: The current stock price $\left(S_{t}\right)$ is \$20. The current continuously compounded interest rate $r$ (at 3 month maturity) is $12\%$ .(crazy number from Hull's book).  

Model/Assumption: In 3 months, the stock price is either \$22 or \$18 (no dividend for now).  

$$
S_{t}=20\ensuremath{\begin{array}{l}{\longrightarrow\qquadS_{T}=22}\ {S_{t}=20}\end{array}}
$$  

# Comments:  

o Once we make the binomial dynamics assumption, the actual probability of reaching either node (going up or down) no longer matters.  

o We have enough information (we have made enough assumption) to price options that expire in 3 months..  

Remember: For derivative pricing, what matters is the list of possible scenarios, but not the actual probability of each scenario happening..  

# A 3-month call option  

Consider a 3-month call option on the stock with a strike of \$21  

Backward induction: Given the terminal stock price $(S_{T})$ , we can compute the option payoff at each node, $(S_{T}-K)^{+}$  

o The zero-coupon bond price with \$1 par value is: $1\times e^{-.12\times.25}=\S0.9704.$  

![](20b25348201d805a103918820b2801dce194a0243f0d6edc827a9bf4c22f2ebf.jpg)  

# Two angles:  

o Replicating: See if you can replicate the call's payoff using stock and bond. $\Rightarrow$ If the payoffs equal, so does the value..  

Hedging: See if you can hedge away the risk of the call using stock. => If the hedged payoff is riskfree, we can compute the present value using riskfree rate.  

# Replicating  

![](294e42883529c5e32337ff56eabad6cb87e5dc00a8031c866785a3889eaf44c5.jpg)  

Assume that we can replicate the payoff of 1 call using $\Delta$ share of stock and $D$ par value of bond, we have  

$$
1=\Delta22+D1,\quad0=\Delta18+D1.
$$  

Solve for : $\Delta=(1-0)/(22-18)=1/4.\Delta={\mathsf{C h a n g e}}$ in C/Change in S, a sensitivity measure.   
Solve for $D$ $\begin{array}{r}{D=-\frac{1}{4}18=-4.5\mathrm{(borrow)}.}\end{array}$   
o Value of option $=$ value of replicating portfolio $\begin{array}{r}{=\frac{1}{4}20-4.5\times0.9704=0.633.}\end{array}$  

# Hedging  

![](ad57fec2ca8ad286495d43656fecdffdb19f8eaa673afc977a84e5a3a0abb9fe.jpg)  

o Assume that we can hedge away the risk in 1 call by shorting $\Delta$ share of stock, such as the hedged portfolio has the same payoff at both nodes: $1-\Delta22=0-\Delta18$  

Solve for :  = (1 - 0)/(22 $-18)=1/4$ (the same): = Change in C/Change in S, a sensitivity measure.  

The hedged portfolio has riskfree payoff: $\textstyle1-{\frac{1}{4}}22=0-{\frac{1}{4}}18=-4.5.$  

Its present value is: $-4.5\times0.9704=-4.3668=1c_{t}-\Delta S_{t}.$  

Ct = $-4.3668+\Delta S_{t}=-4.3668+\textstyle{\frac{1}{4}}20=0.633.$  

# One principle underlying two angles  

o If you can replicate, you can hedge:. Long the option contract, short the replicating portfolio.   
The replication portfolio is composed of stock and bond.   
Since bond only generates parallel shifts in payoff and does not play any role. in offsetting/hedging risks, it is the stock that really plays the hedging role.   
The optimal hedge ratio when hedging options using stocks is defined as the ratio of option payoff change over the stock payoff change - Delta..   
o Hedging derivative risks using the underlying security (stock, currency) is called delta hedging. To hedge a long position in an option, you need to short delta of the underlying. To replicate the payoff of a long position in option, you need to long delta of the underlying.  

# The limit of delta hedging  

Delta hedging completely erases risk under the binomial model assumption: The underlying stock can only take on two possible values..  

Using two (independent) securities can span the two possible realizations.  

We can use stock and bond to replicate the payoff of an option. We can also use stock and option to replicate the payoff of a bond. One of the 3 securities is redundant and can hence be priced by the other two.  

What will happen for the hedging/replicating exercise if the stock can take on 3 possible values three months later, e.g., (22, 20, 18)?.  

It is impossible to find a  that perfectly hedge the option position c replicate the option payoff.   
We need another instrument (say another option) to do perfect hedging or replication.  

# Risk-neutral valuation  

![](b46bc059cd46418e10c879f8bafcde5931131ec719dc0a08545a3201b907726a.jpg)  

Compute a set of artificial probabilities for the two nodes. $\left(p,1-p\right)$ Ssuch that the stock price equals the expected value of the terminal payment, discounted by the riskfree rate..  

$$
\begin{array}{r}{.9704\left(22p+18(1-p)\right)\Rightarrow p=\frac{20/0.9704-18}{22-18}}\end{array}
$$  

Since we are discounting risky payoffs using riskfree rate, it is as if we live in an artificial world where people are risk-neutral. Hence, $\left(p,1-p\right)$ are the risk-neutral probabilities.  

These are not really probabilities, but more like unit prices:0.9704p is the price of a security that pays \$1 at the up state and zero otherwise. 0.9704 $\left(1-p\right)$ is the unit price for the down state..  

To exclude arbitrage, the same set of unit prices (risk-neutral probabilities) should be applicable to all securities, including options..  

# Risk-neutral probabilities  

Under the binomial model assumption, we can identify a unique set of risk-neutral probabilities (RNP) from the current stock price.  

The risk-neutral probabilities have to be probability-like (positive, less than 1) for the stock price to be arbitrage free..   
What would happen if. $p<0$ or $p>1$  

If the prices of market securities do not allow arbitrage, we can identify at least one set of risk-neutral probabilities that match with all these prices.  

o When the market is, in addition, complete (all risks can be hedged away completely by the assets), there exist one unique set of RNP.  

Under the binomial model, the market is complete with the stock alone. We can uniquely determine one set of RNP using the stock price alone.  

Under a trinomial assumption, the market is not complete with the stock alone: There are many feasible RNPs that match the stock price..  

In this case, we add an option to fully determine a unique set of RNP.   
That is, we use this option (and the trinomial) to complete the market.  

# Market completeness  

Market completeness (or incompleteness) is a relative concept: Market may. not be complete with one asset, but can be complete with two... o To me, the real-world market is severely incomplete with primary market securities alone (stocks and bonds). To complete the market, we need to include all available options, plus model structures. Model and instruments can play similar rules to complete a market. RNP are not learned from the stock price alone, but from the option prices. Risk-neutral dynamics need to be estimated using option prices. Options are not redundant. Neither is this option pricing class.  

# Muti-step binomial trees  

o A one-step binomial model looks very Mickey Mouse: In reality, the stock price can take on many possible values than just two.   
Extend the one-step to multiple steps. The number of possible values (nodes) at expiry increases with the number of steps.   
o If we grow the tree with enough steps, it can generate as many nodes as reality calls for.   
o With many nodes, using stock alone can no longer achieve a perfect hedge in one shot.   
But locally, within each step, we still have only two possible nodes. Thus, we can achieve perfect hedge within each step.   
We just need to adjust the hedge at each step - dynamic hedge.   
By doing as many hedge rebalancing at there are time steps, we can still achieve a perfect hedge globally.   
The market can still be completed with the stock alone, in a dynamic sense.  

# Constructing the binomial tree  

![](4450969e0f97a7cd4a460649c750b6072a96a32e7cb8e0a8ed3196688101be8f.jpg)  

One way to set up the tree is to use $(u,d)$ to match the stock return volatility (Cox, Ross, Rubinstein):  

$$
\begin{array}{r}{u=e^{\sigma\sqrt{\Delta t}},\quad d=1/u.}\end{array}
$$  

- the annualized return volatility (standard deviation).  

The risk-neutral probability becomes: $\textstyle p={\frac{a-d}{u-d}}$ where  

$a=e^{r\Delta t}$ for non-dividend paying stock.   
$\boldsymbol{a}=\boldsymbol{e}^{(r-q)\Delta t}$ for dividend paying stock.   
$a=e^{(r-r_{f})\Delta t}$ for currency.   
$a=1$ for futures.  

# Liuren Wu  

# Estimating the return volatility  

To determine the tree $(S_{t},u,d)$ , we set  

$$
\begin{array}{r}{u=e^{\sigma\sqrt{\Delta t}},\quad d=1/u.}\end{array}
$$  

o The only un-observable or "free" parameter is the return volatility $\sigma$  

Mean expected return (risk premium) does not matter for derivative pricing under the binomial model because we can completely hedge. away the risk. $S_{t}$ can be observed from the stock market.  

We can estimate the return volatility using the time series data $\begin{array}{r}{\widehat{\sigma}=\sqrt{\frac{1}{\Delta t}\left[\frac{1}{N-1}\sum_{t=1}^{N}(R_{t}-\overline{{R}})^{2}\right]}.\gets\frac{1}{\Delta t}}\end{array}$ is for annualization.  

o Implied volatility: We can estimate the volatility $(\sigma)$ by matching observed option prices.  

Under the current model assumption, the two approaches should generate similar estimates on average, but they differ in reality (for reasons that we'll discuss later).  

# Practical issues with binominal tree pricing  

The option prices obtained from the binominal tree often shows a zigzag behavior across strikes..  

One way to smooth it up is to price the options using two trees, one using N steps and the other using. $(N+1)$ steps. Then, simply averaging the value. from the two trees with generate much better/smoother results..  

Yet another simple approach is to replace the last step value by the BMS model analytical value.  

Even if the option is American, replacing the last step with the European value does not hurt much. The smoothing effect can be even better than the averaging approach.  

# The Black-Merton-Scholes (BMS) model  

Black and Scholes (1973) and Merton (1973) derive option prices under the following assumption on the stock price dynamics,.  

$$
d S_{t}=\mu S_{t}d t+\sigma S_{t}d W_{t}
$$  

o The binomial model: Discrete states and discrete time (The number of possible stock prices and time steps are both finite).  

o The BMS model: Continuous states (stock price can be anything between 0 and oo) and continuous time (time goes continuously)..  

Scholes and Merton won Nobel price. Black passed away.  

o BMS proposed the model for stock option pricing. Later, the model has been extended/twisted to price currency options (Garman&Kohlhagen) and options on futures (Black)..  

o I treat all these variations as the same concept and call them indiscriminately the BMS model.  

# Primer on continuous time process  

$$
d S_{t}=\mu S_{t}d t+\sigma S_{t}d W_{t}
$$  

The driver of the process is $W_{t}$ , a Brownian motion, or a Wiener process.  

The sample paths of a Brownian motion are continuous over time, but nowhere differentiable.   
It is the idealization of the trajectory of a single particle being constantly bombarded by an infinite number of infinitessimally small random forces.   
Like a shark, a Brownian motion must always be moving, or else it dies.   
If you sum the absolute values of price changes over a day (or any time horizon) implied by the model, you get an infinite number.   
If you tried to accurately draw a Brownian motion sample path, your pen would run out of ink before one second had elapsed.  

The first who brought Brownian motion to finance is Bachelier in his 1900 PhD thesis: The theory of speculation..  

# Properties of a Brownian motion  

$$
d S_{t}=\mu S_{t}d t+\sigma S_{t}d W_{t}
$$  

o The process $W_{t}$ generates a random variable that is normally distributed with mean O and variance $t$ $\phi(0,t)$ . (Also referred to as Gaussian.)  

Everybody believes in the normal approximation, the. experimenters because they believe it is a mathematical theorem, the mathematicians because they believe it is an experimental. fact!  

The process is made of independent normal increments $d W_{t}\sim\phi(0,d t).$  

"d" is the continuous time limit of the discrete time difference $(\triangle)$   
t denotes a finite time step (say, 3 months), dt denotes an extremely thin slice of time (smaller than 1 milisecond)..   
It is so thin that it is often referred to as instantaneous. Similarly, $d W_{t}=W_{t+d t}-W_{t}$ denotes the instantaneous increment. (change) of a Brownian motion..  

By extension, increments over non-overlapping time periods are independent: For $\left(t_{1}>t_{2}>t_{3}\right)$ $(W_{t_{3}}-W_{t_{2}})\sim\phi(0,t_{3}-t_{2})$ is independent of $(W_{t_{2}}-W_{t_{1}})\sim\phi(0,t_{2}-t_{1})$  

# Properties of a normally distributed random variable  

$$
d S_{t}=\mu S_{t}d t+\sigma S_{t}d W_{t}
$$  

o lf $X\sim\phi(0,1)$ , then $a+b X\sim\phi\left(a,b^{2}\right).$  

o If $y\sim\phi(m,V)$ , then $a+b y\sim\phi(a+b m,b^{2}V).$  

Since $d W_{t}\sim\phi(0,d t)$ , the instantaneous price change $d S_{t}=\mu S_{t}d t+\sigma S_{t}d W_{t}\sim\phi(\mu S_{t}d t,\sigma^{2}S_{t}^{2}d t)$  

The instantaneous return $\begin{array}{r}{\frac{d S}{S}=\mu d t+\sigma d W_{t}\sim\phi(\mu d t,\sigma^{2}d t).}\end{array}$  

Under the BMS model,. $\mu$ is the annualized mean of the instantaneous return - instantaneous mean return.  

$\sigma^{2}$ is the annualized variance of the instantaneous return - instantaneous return variance..  

$\sigma$ is the annualized standard deviation of the instantaneous return - instantaneous return volatility..  

# Geometric Brownian motion  

$$
d S_{t}/S_{t}=\mu d t+\sigma d W_{t}
$$  

The stock price is said to follow a geometric Brownian motion.. $\mu$ is often referred to as the drift, and $\sigma$ the diffusion of the process.   
Instantaneously, the stock price change is normally distributed,. $\phi\big(\mu S_{t}d t,\sigma^{2}S_{t}^{2}d t\big).$   
, Over longer horizons, the price change is lognormally distributed. The log return (continuous compounded return) is normally distributed over all horizons: d In $S_{t}=\left(\mu-{\textstyle\frac{1}{2}}\sigma^{2}\right)$ dt + odW. (By Ito's lemma) $\begin{array}{r l}&{{\ I}\ln S_{t}\sim\phi{\ I}\mu d t-\frac{1}{2}\sigma^{2}d t,\sigma^{2}d t\big).}\ &{\cap S_{t}\sim\phi{\left(\ln S_{0}+\mu t-\frac{1}{2}\sigma^{2}t,\sigma^{2}t\right)}.}\ &{\cap S_{T}/S_{t}\sim\phi\left(\left(\mu-\frac{1}{2}\sigma^{2}\right){\left(T-t\right)},\sigma^{2}{\left(T-t\right)}\right)}\end{array}$   
D Integral form: St = Soet-3o?t+oW, $S_{t}=S_{0}e^{\mu t-\frac{1}{2}\sigma^{2}t+\sigma W_{t}},\quad\ln S_{t}=\ln S_{0}+\mu t-$ 1o2t+0Wt  

# Normal versus lognormal distribution  

$\begin{array}{r}{\mathcal{I}S_{t}=\mu S_{t}d t+\sigma S_{t}d W_{t},\quad\mu=10\%,\sigma=20\%}\end{array}$ 6, So = 100, t = 1.  

![](f017cb82878a5d85dcc2f0b21d4b1ce130c745cf79043b07841e14dac7e50c2e.jpg)  

The earliest application of Brownian motion to finance is Louis Bachelier in his dissertation (1900) "Theory of Speculation." He specified the stock price as following a Brownian motion with drift:.  

$$
d S_{t}=\mu d t+\sigma d W_{t}
$$  

# Simulate 100 stock price sample paths  

$\begin{array}{r}{\mathcal{I}S_{t}=\mu S_{t}d t+\sigma S_{t}d W_{t},\quad\mu=10\%,\sigma=20\%}\end{array}$ 6, So = 100, t = 1.  

![](0958083e43e6bb1ee5903a02478be26e9e2daa2ce902f7801c0f6ffb4c30486b.jpg)  

, Stock with the return process: $d$ $\begin{array}{r}{\prime\ln S_{t}=(\mu-\frac{1}{2}\sigma^{2})d t+\sigma d W_{t}.}\end{array}$ Discretize to daily intervals $d t\approx\Delta t=1/252.$ Draw standard normal random variables $\varepsilon(100\times252)\sim\phi(0,1).$ Convert them into daily log returns: $\begin{array}{r}{R_{d}=(\mu-\frac{1}{2}\sigma^{2})\Delta t+\sigma\sqrt{\Delta t}\varepsilon.}\end{array}$ Convert returns into stock price sample paths: $S_{t}=S_{0}e^{\sum_{d=1}^{252}R_{d}}.$  

# Ito's lemma on continuous processes  

For a generic continuous process $x_{t}$  

$$
d x_{t}=\mu_{x}d t+\sigma_{x}d W_{t},
$$  

the transformed variable $y=f(x,t)$ follows,  

$$
d y_{t}=\left(f_{t}+f_{x}\mu_{x}+\frac{1}{2}f_{x x}\sigma_{x}^{2}\right)d t+f_{x}\sigma_{x}d W_{t}
$$  

Taylor expansion up to dt term, with $(d W)^{2}=d t$  

Example 1: $d S_{t}=\mu S_{t}d t+\sigma S_{t}d W_{t}$ and $\boldsymbol{y}=\ln S_{t}$ . We have d In $S_{t}=\left(\mu-{\textstyle{\frac{1}{2}}}\sigma^{2}\right)d t+\sigma d W_{t}$ Example 2: $d v_{t}=\kappa\left(\theta-v_{t}\right)d t+\omega\sqrt{v_{t}}d W_{t}$ , and $\sigma_{t}=\sqrt{v_{t}}$  

$$
d\sigma_{t}=\left(\frac{1}{2}\sigma_{t}^{-1}\kappa\theta-\frac{1}{2}\kappa\sigma_{t}-\frac{1}{8}\omega^{2}\sigma_{t}^{-1}\right)d t+
$$  

Example 3: $d x_{t}=-\kappa x_{t}d t+\sigma d W_{t}$ and $v_{t}=a+b x_{t}^{2}.\Rightarrow d v_{t}=?.$  

# Ito's lemma on jumps  

For a generic process $x_{t}$ with jumps,  

$$
\begin{array}{r l}{=}&{{}\mu_{x}d t+\sigma_{x}d W_{t}+\int g(z)\left(\mu(d z,d t)-\imath\right.}\ {=}&{{}\left(\mu_{x}-\mathbb{E}_{t}[g]\right)d t+\sigma_{x}d W_{t}+\int g(z)\mu(d\sigma}\end{array}
$$  

where the random counting measure $\mu(d z,d t)$ realizes to a nonzero value for a given $Z$ if and only if $x$ jumps from $x_{t-}$ to $x_{t}=x_{t-}+g(z)$ at time $t$ The process $\nu(z,t)d z d t$ compensates the jump process so that the last term is the increment of a pure jump martingale. The transformed variable $y=f(x,t)$ follows,  

$$
\begin{array}{r l}{=}&{\left(f_{t}+f_{x}\mu_{x}+\frac{1}{2}f_{x x}\sigma_{x}^{2}\right)d t+f_{x}\sigma_{x}d W_{t}}\ &{+\int\left(f(x_{t-}+g(z),t)-f(x_{t-},t)\right)\mu(d z,}\ {=}&{\left(f_{t}+f_{x}\left(\mu_{x}-\mathbb{E}_{t}[g]\right)+\frac{1}{2}f_{x x}\sigma_{x}^{2}\right)d t+f_{x}\sigma_{x}}\ &{+\int\left(f(x_{t-}+g(z),t)-f(x_{t-},t)\right)\mu(d z,}\end{array}
$$  

# Ito's lemma on jumps: Merton (1976) example  

$$
\begin{array}{r l}{\mathrm{~\f~}}&{\left(f_{t}+f_{x}\mu_{x}+\frac12f_{x x}\sigma_{x}^{2}\right)d t+f_{x}\sigma_{x}d W_{t}}\ &{+\int\left(f(x_{t-}+g(z),t)-f(x_{t-},t)\right)\mu(d z,d}\ &{\left(f_{t}+f_{x}\left(\mu_{x}-\mathbb{E}_{t}[g(z)]\right)+\frac12f_{x x}\sigma_{x}^{2}\right)d t+f_{x}}\ &{+\int\left(f(x_{t-}+g(z),t)-f(x_{t-},t)\right)\mu(d z,d}\end{array}
$$  

Merton (1976)'s jump-diffusion process:  

$$
\begin{array}{r}{\phantom{}_{t}S_{t-}d t+\sigma S_{t-}d W_{t}+\int S_{t-}\left(e^{z}-1\right)\left(\mu(z,t)\right.}\end{array}
$$  

$$
\mathfrak{\backslash}_{t}=\left(\mu-\frac{1}{2}\sigma^{2}\right)d t+\sigma d W_{t}+\int z\mu(d z,d t)
$$  

$$
\cdot+g(z),t)-f(x_{t-},t)=\ln S_{t}-\ln S_{t-}=I r
$$  

The specification $\left(e^{z}-1\right)$ on price guarantees that the maximum downside jump is no larger than the pre-jump price level $S_{t-}$  

$$
\begin{array}{r}{\circ\ln\mathrm{Merton},\nu(z,t)=\lambda\frac{1}{\sigma_{J}\sqrt{2\pi}}e^{-\frac{(z-\mu_{J})^{2}}{2\sigma_{J}^{2}}}.}\end{array}
$$  

# The key idea behind BMS option pricing  

Under the binominal model, if we cut time step t small enough, the binomial tree converges to the distribution behavior of the geometric. Brownian motion.   
Reversely, the Brownian motion dynamics implies that if we slice the tim thin enough $\left(d t\right)$ , it behaves like a binominal tree.  

Under this thin slice of time interval, we can combine the option with the stock to form a riskfree portfolio, like in the binomial case. Recall our hedging argument: Choose $\Delta$ such that $f-\Delta S$ is riskfree. The portfolio is riskless (under this thin slice of time interval) and must earn the riskfree rate.. Since we can hedge perfectly, we do not need to worry about risk premium and expected return. Thus, $\mu$ does not matter for this portfolio and hence does not matter for the option valuation. Only $\sigma$ matters, as it controls the width of the binomial branching.  

# The hedging proof  

The stock price dynamics: $d S=\mu S d t+\sigma S d W_{t}.$  

o Let $f(S,t)$ denote the value of a derivative on the stock, by Ito's lemma: $\begin{array}{r}{\boldsymbol{\epsilon}_{t}=\left(f_{t}+f_{S}\mu S+\frac{1}{2}f_{S S}\sigma^{2}S^{2}\right)d t+f_{S}\sigma S d W_{t}.}\end{array}$   
o At time $t$ , form a portfolio that contains 1 derivative contract and $-\Delta=f_{S}$ of the stock. The value of the portfolio is. $P=f-f_{S}S$   
The instantaneous uncertainty of the portfolio is $f_{S}\sigma S d W_{t}-f_{S}\sigma S d W_{t}=0.$ Hence, instantaneously the delta-hedged portfolio is riskfree.   
Thus, the portfolio must earn the riskfree rate:. $d P=r P d t$   
o dP=df-fsd $\begin{array}{r}{S=\left(f_{t}+f_{S}\mu S+\frac{1}{2}f_{S S}\sigma^{2}S^{2}-f_{S}\mu S\right)d t=r(}\end{array}$ f  fsS)dt   
This lead to the fundamental partial differential equation (PDE): $\begin{array}{r}{f_{t}+r S f_{S}+\frac{1}{2}f_{S S}\sigma^{2}S^{2}=r f}\end{array}$   
No where do we see the drift (expected return) of the price dynamics $(\mu)$  

# Partial differential equation  

o The hedging argument leads to the following partial differential equation:  

$$
\frac{\partial{f}}{\partial t}+(r-q)S\frac{\partial{f}}{\partial S}+\frac{1}{2}\sigma^{2}S^{2}\frac{\partial^{2}{f}}{\partial S^{2}}=r f
$$  

The only free parameter is $\sigma$ (as in the binominal model).  

Solving this PDE, subject to the terminal payoff condition of the derivative (e.g., $f_{T}=(S_{T}-K)^{+}$ for a European call option), BMS derive analytical. formulas for call and put option value..  

Similar formula had been derived before based on distributional (normal return) argument, but $\mu$ was still in. The realization that option valuation does not depend on $\mu$ is big Plus, it provides a way to hedge the option position.  

o The PDE is generic for any derivative securities, as long as S follows geometric Brownian motion..  

Given boundary conditions, derivative values can be solved numerically from the PDE.  

# Explicit finite difference method  

One way to solve the PDE numerically is to discretize across time using N time steps $(0,\Delta t,2\Delta t,\cdot\cdot\textit{,}T)$ and discretize across states using $M$ grids (0, S, ..., $S_{\mathrm{max}})$  

We can approximate the partial derivatives at time $i$ and state $j,(i,j)$ , by the differences: $\begin{array}{r}{f_{S}\approx\frac{f_{i,j+1}-f_{i,j-1}}{2\Delta S}}\end{array}$ $\begin{array}{r}{\begin{array}{r}{f_{S S}\approx\frac{f_{i,j+1}+f_{i,j-1}-2f_{i,j}}{\Delta S^{2}}}\end{array}}\end{array}$ , and $\begin{array}{r}{f_{t}=\frac{{{f}_{i,j}}-{{f}_{i-1,j}}}{\Delta t}}\end{array}$   
The PDE becomes: $\begin{array}{r}{\frac{f_{i,j}-f_{i-1,j}}{\Delta t}+(r-q)j\Delta S\frac{f_{i,j+1}-f_{i,j-1}}{2\Delta S}+\frac{1}{2}\sigma^{2}j^{2}}\end{array}$ (ss) =rfij   
Collecting terms: ${f_{i-1,j}}={a_{j}}{f_{i,j-1}}+{b_{j}}{f_{i,j}}+{c_{j}}{f_{i,j+1}}$  

Essentially a trinominal tree: The time-i value at $j$ state of $f_{i,j}$ is a weighted average of the time-. $j+1$ values at the three adjacent states. $(j-1,j,j+1).$  

# Finite difference methods: variations  

o At $(i,j)$ , we can define the difference $\left(\mathsfit{f}_{t},\mathsfit{f}_{S}\right)$ in three different ways:  

Backward: $f_{t}=(f_{i,j}-f_{i-1,j})/\Delta t.$ Forward: $f_{t}=(f_{i+1,j}-f_{i,j})/\Delta t$ Centered: $f_{t}=(f_{i+1,j}-f_{i-1,j})/(2\Delta t).$  

o Different definitions results in different numerical schemes:  

Explicit: $\begin{array}{l}{{f_{i-1,j}=a_{j}f_{i,j-1}+b_{j}f_{i,j}+c_{j}f_{i,j+1}.}}\ {{a_{j}f_{i,j-1}++b_{j}f_{i,j}+c_{j}f_{i,j+1}=f_{i+1,j}.}}\end{array}$   
Implicit:   
Crank-Nicolson:   
-aj f $\begin{array}{r}{-1,j-1+\bigl(1-\beta_{j}\bigr)f_{i-1,j}-\gamma_{j}f_{i-1,j+1}=\alpha_{j}f_{i,j-1}.}\end{array}$ +(1+j)fi,j+yjfi,j+1  

# The BMS formula for European options  

where  

$$
\begin{array}{r l r}{c_{t}}&{=}&{S_{t}e^{-q(T-t)}N(d_{1})-K e^{-r(T-t)}N(d_{2})}\ {\jmath_{t}}&{=}&{-S_{t}e^{-q(T-t)}N(-d_{1})+K e^{-r(T-t)}N}\end{array}
$$  

$$
\begin{array}{r l r l}{\iota_{1}}&{=}&&{\frac{\ln(S_{t}/K)+(r-q)(T-t)+\frac{1}{2}\sigma^{2}(T-t)}{\sigma\sqrt{T-t}},}\ {\iota_{2}}&{=}&&{\frac{\ln(S_{t}/K)+(r-q)(T-t)-\frac{1}{2}\sigma^{2}(T-t)}{\sigma\sqrt{T-t}}=d_{1}-}\end{array}
$$  

Black derived a variant of the formula for futures (which I like better):  

with d1,2 = !  

$$
\begin{array}{c}{{c_{t}=e^{-r(T-t)}\left[F_{t}N(d_{1})-K N(d_{2}\right.}}\ {{\left.\frac{\ln(F_{t}/K)\pm\frac{1}{2}\sigma^{2}(T-t)}{\sigma\sqrt{T-t}}.\right.}}\ {{.\left.\left.\frac{\sigma}{\sigma}-\varsigma\varsigma(r-q)(T-t)\right.}}\end{array}
$$  

Recall: Ft = Ste(r-q)(T-t).   
Once I know call value, I can obtain put value via put-call parity: $c_{t}-p_{t}=e^{-r(T-t)}\left[F_{t}-K_{t}\right].$  

# Implied volatility  

$$
[F_{t}N(d_{1})-K N(d_{2})],\quad d_{1,2}=\frac{\ln(F_{t}/K)\pm\frac{1}{2}}{\sigma\sqrt{T}}
$$  

o Since $F_{t}$ (or $S_{t}$ ) is observable from the underlying stock or futures market, $(K,t,\tau)$ are specified in the contract. The only unknown (and hence free) parameter is $\sigma$  

We can estimate $\sigma$ from time series return. (standard deviation calculation).  

Alternatively, we can choose. $\sigma$ to match the observed option price - implied volatility (IV).  

There is a one-to-one correspondence between prices and implied volatilities.  

Traders and brokers often quote implied volatilities rather than dollar prices.  

o The BMS model says that $I V=\sigma$ . In reality, the implied volatility calculated from different options (across strikes, maturities, dates) are usually different.  

# Risk-neutral valuation  

Recall: Under the binomial model, we derive a set of risk-neutral probabilities such that we can calculate the expected payoff from the option and discount them using the riskfree rate.  

Risk premiums are hidden in the risk-neutral probabilities. If in the real world, people are indeed risk-neutral, the risk-neutral probabilities are the same as the real-world probabilities. Otherwise, they are different.  

o Under the BMS model, we can also assume that there exists such an. artificial risk-neutral world, in which the expected returns on all asset. risk-free rate.   
The stock price dynamics under the risk-neutral world becomes, $d S_{t}/S_{t}=(r-q)d t+\sigma d W_{t}.$   
Simply replace the actual expected return $(\mu)$ with the return from a risk-neutral world. $\left(r-q\right)$ [ex-dividend return].   
We label the true probability measure by $\mathbb{P}$ and the risk-neutral measure by $\mathbb{Q}$  

# The risk-neutral return on spots  

$d S_{t}/S_{t}=(r-q)d t+\sigma d W_{t}$ under risk-neutral probabilities. o In the risk-neutral world, investing in all securities make the riskfree rate as the total return. o If a stock pays a dividend yield of $q$ , then the risk-neutral expected return From stock price appreciation is $\left(r-q\right)$ , such as the total expected return is: dividend yield+ price appreciation $=r$ Investing in a currency earns the foreign interest rate $r_{f}$ similar to dividend yield. Hence, the risk-neutral expected currency appreciation is $\left(r-r_{f}\right)$ so that the total expected return is still $r$ o Regard $q$ as $r_{f}$ and value options as if they are the same.  

# The risk-neutral return on forwards/futures  

o If we sign a forward contract, we do not pay anything upfront and we do not. receive anything in the middle (no dividends or foreign interest rates). Any P&L at expiry is excess return..   
Under the risk-neutral world, we do not make any excess return. Hence, the. forward price dynamics has zero mean (driftless) under the risk-neutral probabilities: $d F_{t}/F_{t}=\sigma d W_{t}$   
The carrying costs are all hidden under the forward price, making the pricing. equations simpler.  

# Return predictability and option pricing  

Consider the following stock price dynamics,  

$$
\begin{array}{r c l}{/S_{t}}&{=}&{\left(a+b X_{t}\right)d t+\sigma d W_{t},}\ {/X_{t}}&{=}&{\kappa\left(\theta-X_{t}\right)+\sigma_{x}d W_{2t},\quad\rho d t=\mathbb{E}[d}\end{array}
$$  

5tock returns are predictable by a vector of mean-reverting predictors $X_{t}$ .How should we price options on this predictable stock?.  

o Option pricing is based on replication/hedging - a cross-sectional focus, not based on prediction - a time series behavior.  

o Whether we can predict the stock price is irrelevant. The key is whether we can replicate or hedge the option risk using the underlying stock.  

o Consider a derivative $f(S,t)$ , whose terminal payoff depends on $S$ but not on X, then it remains true that $d f_{t}=\left(f_{t}+f_{S}\mu\dot{S}+\textstyle{\frac{1}{2}}f_{S S}\dot{\sigma^{2}}S^{2}\right)d t+f_{S}\sigma S d W$ +  

The delta-hedged option portfolio $\left(f-f_{S}S\right)$ remains riskfree.  

The same PDE holds for $f$ $\begin{array}{r}{f_{t}+r S f_{S}+\frac{1}{2}f_{S S}\sigma^{2}S^{2}=r f}\end{array}$  

# Return predictability and risk-neutral valuation  

Consider the following stock price dynamics (under P), dSt/ $\begin{array}{r c l}{{\zeta_{t}}}&{{=}}&{{\left(a+b X_{t}\right)d t+\sigma d W_{t},}}\ {{\zeta_{t}}}&{{=}}&{{\kappa\left(\theta-X_{t}\right)+\sigma_{x}d W_{2t},\quad\rho d t=\mathbb{E}[d V}}\end{array}$ d) /t dW2t].  

o Under the risk-neutral measure. $(\mathbb{Q})$ , stocks earn the riskfree rate, regardless of the predictability:. $d S_{t}/S_{t}=\left(r-q\right)d t+\sigma d W_{t}$  

Analogously, the futures price is a martingale under $\mathbb{Q}$ , regardless of whether. you can predict the futures movements or not:. $d F_{t}/F_{t}=\sigma d W_{t}$  

Measure change from $\mathbb{P}$ to $\mathbb{Q}$ does not change the diffusion component odW.  

The BMS formula still applies.  

# Stochastic volatility and option pricing  

Consider the following stock price dynamics,  

$$
\begin{array}{r c l}{{\mathsf{S}_{t}}}&{{=}}&{{\mu d t+\sqrt{v_{t}}d W_{t},}}\ {{v_{t}}}&{{=}}&{{\kappa\left({\theta-v_{t}}\right)+\omega\sqrt{v_{t}}d W_{2t},\quad\rho d t=\mathbb{E}[}}\end{array}
$$  

How should we price options on this stock with stochastic volatility?  

o Consider a call option on S. Even though the terminal value does not depend on $\boldsymbol{v}_{t}$ , the value of the option at other periods have to depend on. $\boldsymbol{v}_{t}$  

Assume $f(S,t)$ does not depend on $\boldsymbol{v}_{t}$ , we have $\begin{array}{r}{\mathcal{H}_{t}=\left(f_{t}+\dot{f}_{S}\mu S+\frac{1}{2}\dot{f}_{S S}v_{t}S^{2}\right)d t+\dot{f}_{S}\sigma S\sqrt{v_{t}}c}\end{array}$ Wt, which obviously depend on $\boldsymbol{v}_{t}$  

o For $f(S,v,t)$ , we have (bivariate version of Ito): df = $\begin{array}{r l}&{\left(f_{t}+\dot{f}_{S}\mu S+\frac{1}{2}\dot{f}_{S S}\dot{v}_{t}S^{2}+f_{v}\kappa\left(\theta-v_{t}\right)+\frac{1}{2}\dot{f}_{v v}\right)}\ &{\sqrt{v_{t}}d W_{t}+f_{v}\omega\sqrt{v_{t}}d W_{2t}.}\end{array}$ w2Vt+ fSvWVtP) dt + fsoS  

Since there are two sources of risk $(W_{t},W_{2t})$ , delta-hedging is not going to. lead to a riskfree portfolio.  

# Pricing kernel  

In the absence of arbitrage, in an economy, there exists at least one strictly positive process, $M_{t}$ , the state-price deflator, such that the deflated gains. process associated with any admissible strategy is a martingale. The ratio of $M_{t}$ at two horizons, $M_{t,T}$ , is called a stochastic discount factor, or more. informally, a pricing kernel..  

For an asset that has a terminal payoff $\tau$ , its time-t value is $p_{t}=\mathbb{E}_{t}^{\mathbb{P}}\left[M_{t,T}\Pi_{T}\right]$   
The time- $t$ price of a \$1 par riskfree zero-coupon bond that expires at $\tau$ is $p_{t}=\mathbb{E}_{t}^{\mathbb{P}}\left[M_{t,T}\right]$   
In a discrete-time representative agent economy with an additive CRRA utility, the pricing kernel is equal to the ratio of the marginal utilities of consumption,  

$$
M_{t,t+1}=\beta\frac{u^{\prime}(c_{t+1})}{u^{\prime}(c_{t})}=\beta\left(\frac{c_{t+1}}{c_{t}}\right)^{-\gamma}
$$  

# From pricing kernel to exchange rates  

o Let $M_{t,T}^{h}$ denote the pricing kernel in economy $h$ that prices all securities in that economy with its currency denomination.  

o The $h\cdot$ -currency price of currency- $f$ $h$ is home currency) is linked to the pricing kernels of the two economies by,  

$$
{\frac{S_{T}^{\mathit{f h}}}{S_{t}^{\mathit{f h}}}}={\frac{M_{t,T}^{\mathit{f}}}{M_{t,T}^{\mathit{h}}}}
$$  

o The log currency return over period. $[t,T]$ , In $S_{T}^{t h}/S_{t}^{f h}$ equals the difference between the log pricing kernels of the two economies.  

o Let $S$ denote the dollar price of pound (e.g. $S_{t}=\S2.06)$ , then $S_{T}/S_{t}=\ln M_{t,T}^{p o u n d}-\ln M_{t,T}^{d o I I a r}.$  

o If markets are completed by primary securities (e.g., bonds and stocks),. there is one unique pricing kernel per economy. The exchange rate. movement is uniquely determined by the ratio of the pricing kernels.  

If the markets are not completed by primary securities, exchange rates (and currency options) help complete the markets by requiring that the ratio of any two viable pricing kernels go through the exchange rate.  

# From pricing kernel to measure change  

o In continuous time, it is convenient to define the pricing kernel via the following multiplicative decomposition:  

$$
M_{t,T}=\exp\left(-\int_{t}^{T}r_{s}d s\right)\mathcal{E}\left(-\int_{t}^{T}\gamma_{s}^{\top}d X_{s}\right.
$$  

$r$ is the instantaneous riskfree rate, $\mathcal{E}$ is the stochastic exponential martingale operator, $X$ denotes the risk sources in the economy, and $\gamma$ is the market price of the risk $X$  

If $X_{t}=W_{t}$ $\begin{array}{r}{\mathcal{E}\left(-\int_{t}^{T}\gamma_{s}d W_{s}\right)=\exp\left(-\int_{t}^{T}\gamma_{s}d W_{s}-\frac{1}{2}.}\end{array}$ ST Y2 dsJ   
In a continuous time version of the representative agent example, $d X_{s}=d$ In $c_{t}$ and $\gamma$ is relative risk aversion. $r$ is usually a function of $X$  

The exponential martingale $\mathcal{E}(\cdot)$ defines the measure change from $\mathbb{P}$ to $\mathbb{Q}$  

# Measure change defined by exponential martingales  

Consider the following exponential martingale that defines the measure change from $\mathbb{P}$ to $\mathbb{Q}$  

$$
\begin{array}{r}{\frac{d\mathbb{Q}}{d\mathbb{P}}\Big\vert_{t}=\mathcal{E}\left(-\int_{0}^{t}\gamma_{s}d W_{s}\right),}\end{array}
$$  

o If the $\mathbb{P}$ dynamics is: $d S_{t}^{i}=\mu^{i}S_{t}^{i}d t+\sigma^{i}S_{t}^{i}d W_{t}^{i}$ , with $\begin{array}{r}{\rho^{i}d t=\mathbb{E}[d W_{t}d W_{t}^{i}],}\end{array}$ then the dynamics of $S_{t}^{i}$ under $\mathbb{Q}$ is: $d S_{t}^{i}=$ ' S dt $+\sigma^{j}S_{t}^{i}d W_{t}^{i}+\mathbb{E}[-\gamma_{t}d W_{t},\sigma^{i}S_{t}^{i}d W_{t}^{i}]=\left(\mu_{t}^{i}-\right.$ yo'p') S{dt+0'S|dWj   
o If $S_{t}^{i}$ is the price of a traded security, we need $r=\mu_{t}^{i}-\gamma\sigma^{i}\rho^{i}$ . The risk premium on the security is. $\mu_{t}^{i}-r=\gamma\sigma^{i}\rho^{i}$  

How do things change if the pricing kernel is given by: Mt,T = $\begin{array}{r}{\mathsf{s x p}\left(-\int_{t}^{T}r_{s}d s\right)\mathcal{E}\left(-\int_{t}^{T}\gamma_{s}^{\top}d W_{s}\right)\mathcal{E}\left(-\int_{t}^{T}.\right.}\end{array}$ YT dZ, where $Z_{t}$ is another Brownian motion independent of $W_{t}$ or $W_{t}^{i}$  

# Bond pricing under P and Q  

The time-t price of a \$1 par riskfree zero-coupon bond that expires at T is:  

$$
\begin{array}{r c l}{\eta_{t}}&{=}&{\mathbb{E}_{t}^{\mathbb{P}}\left[M_{t},\tau\right]}\ &{=}&{\mathbb{E}_{t}^{\mathbb{P}}\left[\exp\left(-\int_{t}^{T}r_{s}d s\right)\mathcal{E}\left(-\int_{t}^{T}\gamma_{s}^{\top}d X_{s}\right.}\ &{=}&{\mathbb{E}_{t}^{\mathbb{Q}}\left[\exp\left(-\int_{t}^{T}r_{s}d s\right)\right].}\end{array}
$$  

We need to know the short rate dynamics under $\mathbb{Q}$ for bond pricing.  

o Suppose the pricing kernel is: Mt,T = $\begin{array}{r}{\exp\left(-\int_{t}^{T}r_{s}d s\right)\mathcal{E}\left(-\int_{t}^{T}\gamma_{s}^{\top}d X_{s}\right)\mathcal{E}\left(-\int_{t}^{T}}\end{array}$ nT dZs) with X,Z orthogonal, and $r=r(X)$ Bond price will only depend on $X$ , not $Z$  

# Measure change defined by exponential martingales: Jumps  

Let $X$ denote a pure jump process with its compensator being $\nu(x,t)$ under P.   
Consider a measure change defined by the exponential martingale: $\begin{array}{r}{\frac{d\mathbb{Q}}{d\mathbb{P}}\Big\vert_{t}=\mathcal{E}\left(-\gamma X_{t}\right),}\end{array}$ D   
The compensator of the jump process under $\mathbb{Q}$ becomes: $\nu(x,t)^{\mathbb{Q}}=e^{-\gamma x}\nu(x,t).$ Example: Merton (176)'s compound Poisson jump process, $\begin{array}{r l}&{(x,t)=\lambda\frac{1}{\sigma_{J}\sqrt{2\pi}}e^{-\frac{(x-\mu_{J})^{2}}{2\sigma_{J}^{2}}}.\mathsf{U n d e r~\mathbb{Q}},\mathsf{i t~b e c o r}}\ &{(x,t)^{\mathbb{Q}}=\lambda\frac{1}{\sigma_{J}\sqrt{2\pi}}e^{-\gamma x-\frac{(x-\mu_{J})^{2}}{2\sigma_{J}^{2}}}=\lambda^{\mathbb{Q}}\frac{1}{\sigma_{J}\sqrt{2\pi}}e^{-}}\ &{\mathsf{u d}\lambda^{\mathbb{Q}}=\lambda e^{\frac{1}{2}\gamma(\gamma\sigma_{J}^{2}-2\mu_{J})}.}\end{array}$ nes (x-u9)2 2o3 with $\mu^{\mathbb{Q}}=\mu_{J}-\gamma\sigma_{J}^{2}$ ar  

# The BMS Delta  

The BMS delta of European options (Can you derive them?):  

![](2de89cd4f566ddbd40d380f91efe03c7a202529a141e5b8c3884c09aac62383f.jpg)  

Industry quotes the delta in absolute percentage terms (right panel).   
Which of the following is out-of-the-money? (i) 25-delta call, (ii) 25-delta put, (ii) 75-delta call, (iv) 75-delta put.   
The strike of a 25-delta call is close to the strike of: (i) 25-delta put, (ii) 50-delta put, (ii) 75-delta put.   
Delta as a moneyness measure   
Different ways of measuring moneyness: K (relative to S or $F$ ): Raw measure, not comparable across different stocks : $K/F$ : better scaling than $K-F$ o In $K/F$ : more symmetric under BMS. $\circ\frac{\mathsf{l n}K/F}{\sigma\sqrt{(T-t)}}$ : standardized by volatility and option maturity, comparable across stocks. Need to decide what $\sigma$ to use (ATMV, IV, 1). - $d_{1}$ : a standardized variable. : $d_{2}$ : Under BMS, this variable is the truly standardized normal variable with $\phi(0,1)$ under the risk-neutral measure. o delta: Used frequently in the industry Measures moneyness: Approximately the percentage chance the option will be in the money at expiry. Reveals your underlying exposure (how many shares needed to achieve delta-neutral).  

# OTC quoting and trading conventions for currency options  

Options are quoted at fixed time-to-maturity (not fixed expiry date).  

o Options at each maturity are not quoted in invoice prices (dollars), but in the following format:  

Delta-neutral straddle implied volatility (ATMV):  

A straddle is a portfolio of a call $\&$ a put at the same strike. The strike here is set to make the portfolio delta-neutral $\Rightarrow d_{1}=0$ 25-delta risk reversal: $I V(\Delta_{c}=25)-I V(\Delta_{p}=25)$ 25-delta butterfly spreads: $^{(}I V(\Delta_{c}=25)+I V(\Delta_{p}=25))/2-A T M V.$ Risk reversals and butterfly spreads at other deltas, e.g., 10-delta.  

When trading, invoice prices and strikes are calculated based on the BMS formula.  

The two parties exchange both the option and the underlying delta.  

The trades are delta-neutral.  

# The BMS vega  

.Vega $(\nu)$ is the rate of change of the value of a derivatives portfolio with. respect to volatility - it is a measure of the volatility exposure.  

BMS vega: the same for call and put options of the same maturity  

$$
\nu\equiv\frac{\partial c_{t}}{\partial\sigma}=\frac{\partial p_{t}}{\partial\sigma}=S_{t}e^{-q(T-t)}\sqrt{T-t}n(d_{1})
$$  

$n(d_{1})$ is the standard normal probability density: $\begin{array}{r}{\eta(x)=\frac{1}{\sqrt{2\pi}}e^{-\frac{x^{2}}{2}}.}\end{array}$  

![](053595a7c3ba3b069e0335e1041fe57353f635052661a979e1ba9c2fd2d68ec7.jpg)  

Volatility exposure (vega) is higher for at-the-money options.  

# Vega hedging  

Delta can be changed by taking a position in the underlying. To adjust the volatility exposure (vega), it is necessary to take a position i an option or other derivatives..  

Hedging in practice:  

Traders usually ensure that their portfolios are delta-neutral at least once a day.   
Whenever the opportunity arises, they improve/manage their vega exposure - options trading is more expensive.   
As portfolio becomes larger, hedging becomes less expensive.  

Under the assumption of BMS, vega hedging is not necessary: $\sigma$ does not change. But in reality, it does..  

.Vega hedge is outside the BMS model.  

# Example: Delta and vega hedging  

Consider an option portfolio that is delta-neutral but with a vega of -8, 00o. We plan to make the portfolio both delta and vega neutral using two instruments:  

The underlying stock o A traded option with delta 0.6 and vega 2.0.  

How many shares of the underlying stock and the traded option contracts do w   
need? To achieve vega neutral, we need long 8000/2=4,000 contracts of the traded option. With the traded option added to the portfolio, the delta of the portfolio increases from $0~{\mathrm{to}}~0.6\times4,000=2,400$ We hence also need to short 2,400 shares of the underlying stock $\Rightarrow$ each share of the stock has a delta of one.  

# Another example: Delta and vega hedging  

Consider an option portfolio with a delta of 2,000 and vega of 60,000. We plan to make the portfolio both delta and vega neutral using:  

The underlying stock o A traded option with delta 0.5 and vega 10.  

How many shares of the underlying stock and the traded option contracts do we need?  

As before, it is easier to take care of the vega first and then worry about the delta using stocks.   
To achieve vega neutral, we need short/write 60000/10 $=$ 6000 contracts of the traded option.   
With the traded option position added to the portfolio, the delta of the portfolio becomes 2000 $-0.5\times6000=-1000$   
We hence also need to long 1000 shares of the underlying stock.  

# A more formal setup  

Let $(\Delta_{p},\Delta_{1},\Delta_{2})$ denote the delta of the existing portfolio and the two hedging instruments. $\mathsf{L e t}\big(\nu_{p},\nu_{1},\nu_{2}\big)$ denote their vega. Let. $\left(n_{1},n_{2}\right)$ denote the shares of the two instruments needed to achieve the target delta and vega exposure $(\Delta_{T},\nu_{T})$ .We have  

$$
\begin{array}{r c l}{{\Delta_{T}}}&{{=}}&{{\Delta_{p}+n_{1}\Delta_{1}+n_{2}\Delta_{2}}}\ {{\nu_{T}}}&{{=}}&{{\nu_{p}+n_{1}\nu_{1}+n_{2}\nu_{2}}}\end{array}
$$  

Ne can solve the two unknowns $\left(n_{1},n_{2}\right)$ from the two equations..  

o Example 1: The stock has delta of 1 and zero vega.  

$$
\begin{array}{l c l}{{0}}&{{=}}&{{0+n_{1}0.6+n_{2}}}\ {{0}}&{{=}}&{{-8000+n_{1}2+0}}\end{array}
$$  

Example 2: The stock has delta of 1 and zero vega.  

$$
0=2000+n_{1}0.5+n_{2},\quad0=60000+n
$$  

n1 = 6000, $n_{2}=1000$  

When do you want to have non-zero target exposures?  

# Liuren Wu  

# BMS gamma  

o Gamma () is the rate of change of delta $(\triangle)$ with respect to the price of. the underlying asset..  

o The BMS gamma is the same for calls and puts:  

![](5b4b65a9f6a212b42647685b15a4ec7121251166d9b2b474eb19e62d779e9916.jpg)  

Gamma is high for near-the-money options..   
High gamma implies high variation in delta, and hence more frequent rebalancing to maintain low delta exposure..  

# Gamma hedging  

o High gamma implies high variation in delta, and hence more frequent rebalancing to maintain low delta exposure..   
Delta hedging is based on small moves during a very short time period. assuming that the relation between option and the stock is linear. locally. When gamma is high, The relation is more curved (convex) than linear, The P&L (hedging error) is more likely to be large in the presence of. large moves. The gamma of a stock is zero.   
o We can use traded options to adjust the gamma of a portfolio, similar to what we have done to vega.   
But if we are really concerned about large moves, we may want to try something else.  

# Dynamic hedging with greeks  

The idea of delta and vega hedging is.   
based on a locally linear approximation.   
(partial derivative) of the relation.   
between the derivative portfolio value and the underlying stock price and.   
volatility.  

![](d85ce84842874e74ce720957b94bbc0b769d8deb48a85fb064bca0e343e34cb2.jpg)  

Since the relation is not linear, the hedging ratios change as the environment change.  

Dynamic hedging, hedging based on partial derivatives, often asks for frequent rebalancing.  

o Dynamic hedging works well if  

The overall relation is close to linear. Hence, the hedging ratio is stable over time. The underlying variable (stock. price, volatility) varies smoothly and only changes a little within a certain time interval.  

# Dynamic versus static hedging  

Dynamic hedging can generate large hedging errors when the underlying variable (stock price) can jump randomly..  

A large move size per se is not an issue, as long as we know how much it moves - a binomial tree can be very large moves, but delta hedge. works perfectly.  

As long as we know the magnitude, hedging is relatively easy .The key problem comes from large moves of random size.  

An alternative is to devise static hedging strategies: The position of the hedging instruments does not vary over time..  

Conceptually not as easy. Different derivative products ask for different static strategies.   
It involves more option positions. Cost per transaction is high.   
Monitoring cost is low. Fewer transactions.  

# Example: Static hedging long-term option using short-term options  

"Static hedging of standard options," Carr and Wu, wp.  

o A European call option maturing at a fixed time T can be replicated by a static position in a continuum of European call options at a shorter maturity $u\leq T$  

$$
C(S,t;K,T)=\intop_{0}^{\infty}w(K)C(S,t;K,u)d K,
$$  

with the weight of the portfolio given by $\begin{array}{r}{w(\mathcal{K})=\frac{\partial^{2}}{\partial\mathcal{K}^{2}}C(\mathcal{K},u;K,T)}\end{array}$ the gamma that the target call option will have at time $u$ , should the underlying price level be at $\boldsymbol{\kappa}$ then.  

Assumption: The stock price can jump randomly. The only requirement is that the stock price is Markovian in itself:. $S_{t}$ captures all the information. about the stock up to time t..  

# Practical implementation and performance  

<html><body><table><tr><td>Target Mat</td><td>2</td><td>4</td><td>12</td><td>12</td><td>12</td><td>2</td><td>4</td><td>12</td></tr><tr><td>Strategy Instruments</td><td>1</td><td>1</td><td>1</td><td>Static with Five Options 2</td><td>4</td><td></td><td>Daily Delta Underlying Futures</td><td></td></tr><tr><td></td><td>-0.00</td><td>-0.10</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Mean Std Err</td><td>0.23</td><td>0.50</td><td>-0.01 0.87</td><td>-0.07 0.64</td><td>0.01 0.42</td><td>0.16 0.57</td><td>0.03</td><td>-0.01</td></tr><tr><td>RMSE</td><td>0.23</td><td>0.51</td><td>0.86</td><td>0.64</td><td>0.42</td><td>0.59</td><td>0.65</td><td>0.88</td></tr><tr><td></td><td>-0.62</td><td>-1.55</td><td>-2.32</td><td>-1.97</td><td>-1.58</td><td>-1.28</td><td>0.65</td><td>0.87</td></tr><tr><td>Min Max</td><td>0.50</td><td>1.09</td><td>1.56</td><td>1.10</td><td>0.86</td><td>1.45</td><td>-2.23 1.42</td><td>-2.51 1.76</td></tr><tr><td>Target Call</td><td>3.68</td><td>6.16</td><td>10.94</td><td>10.76</td><td>11.52</td><td>3.65</td><td>6.14</td><td>11.58</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>  

# Semi-static hedge of barriers  

Option being hedged: a one-month one-touch barrier option with a lower barrier and payment at expiry  

Hedging instruments: vanilla and binary put options, binary call  

. Procedure:  

At time $t$ , sell the barrier, and put on a hedging position with vanilla options with the terminal payoff  

If the barrier $L$ never hits before expiry, both the barrier and the hedging portfolio generate zero payoff.  

If the barrier is hit before expiry, then:  

Sell a European option with the terminal payoff $\begin{array}{r l}&{1(S_{T}<L)\left(\frac{S_{T}}{L}\right)=(S<L)-(L-S)^{+}/L.}\ {\star}&{\mathsf{B u y~a~E u r o p e a n~o p t i o n~t h a t~p a y s~}1(S_{T}>L}\ {\star}&{\mathsf{T h e~o p e r a t i o n~i s~s e l f-f i n a n c i n g~u n d e r~t h e~B~}}\end{array}$ MS when $r=q$  

Hedging barriers: Dynamic and static hedging performance  

JPYUSD:   


<html><body><table><tr><td>Strategy</td><td>Mean</td><td>Std</td><td>Max</td><td>Min</td><td>Skew</td><td>Kurt</td></tr><tr><td>Value</td><td>55.40</td><td>3.71</td><td>67.39</td><td>37.77</td><td>0.55</td><td>2.77</td></tr><tr><td>No Hedge</td><td>-49.46</td><td>50.01</td><td>0.00</td><td>-100.00</td><td>-0.02</td><td>1.00</td></tr><tr><td>Delta</td><td>-44.24</td><td>20.88</td><td>76.67</td><td>-138.26</td><td>0.79</td><td>7.86</td></tr><tr><td>Vega</td><td>-44.45</td><td>17.50</td><td>67.47</td><td>-130.67</td><td>1.40</td><td>10.14</td></tr><tr><td>Vanna</td><td>-45.38</td><td>18.01</td><td>67.47</td><td>-137.32</td><td>1.32</td><td>10.08</td></tr><tr><td>Static</td><td>-50.86</td><td>10.68</td><td>48.94</td><td>-68.02</td><td>6.66</td><td>62.00</td></tr></table></body></html>  

Hedging barriers: Dynamic and static hedging performance  

GBPUSD:   


<html><body><table><tr><td>Strategy</td><td>Mean</td><td>Std</td><td>Max</td><td>Min</td><td>Skew</td><td>Kurt</td></tr><tr><td>Value</td><td>49.35</td><td>1.66</td><td>54.98</td><td>42.86</td><td>0.21</td><td>4.09</td></tr><tr><td>No Hedge</td><td>-32.21</td><td>46.73</td><td>0.00</td><td>-100.00</td><td>-0.76</td><td>1.58</td></tr><tr><td>Delta</td><td>-36.39</td><td>19.81</td><td>70.02</td><td>-127.86</td><td>1.20</td><td>6.34</td></tr><tr><td>Vega</td><td>-38.24</td><td>16.58</td><td>55.74</td><td>-124.94</td><td>1.85</td><td>8.82</td></tr><tr><td>Vanna</td><td>-39.07</td><td>16.33</td><td>54.92</td><td>-119.33</td><td>1.85</td><td>8.56</td></tr><tr><td>Static</td><td>-46.55</td><td>10.80</td><td>49.19</td><td>-52.62</td><td>5.07</td><td>39.81</td></tr></table></body></html>  

# Implied volatility  

Recall the BMS formula:  

c(S,t,K, T) =e-rT $^{-t)}\left[F_{t,T}N(d_{1})-K N(d_{2})\right],d_{1,2}=\frac{\ln\frac{F_{t,T}}{K}\pm\frac{1}{2}}{\sigma\sqrt{7}}$ o2(T-t) - t  

The BMS model has only one free parameter, the asset return volatility $\sigma$   
Call and put option values increase monotonically with increasing $\sigma$ under BMS. Given the contract specifications $(K,T)$ and the current market observations $(S_{t},F_{t},r)$ , the mapping between the option price and $\sigma$ is a unique one-to-one mapping.   
The $\sigma$ input into the BMS formula that generates the market observed option price (or sometimes a model-generated price) is referred to as the implied volatility (IV).   
Practitioners often quote/monitor implied volatility for each option contract  

instead of the option invoice price.  

# The relation between option price and  under BMS  

![](2c351e1a8ced1a61c6f813e34a32e47be057ed3c8d2a5b2d2f4ed60c88277836.jpg)  

o An option value has two components:  

Intrinsic value: the value of the option if the underlying price does not move (or if the future price. $=$ the current forward). Time value: the value generated from the underlying price movement.  

o Since options give the holder only rights but no obligation, larger moves generate bigger opportunities but no extra risk - Higher volatility increases the option's time value..  

At-the-money option price is approximately linear in implied volatility.  

# Implied volatility versus  

o If the real world behaved just like BMS, $\sigma$ would be a constant..  

In this BMS world, we could use one. $\sigma$ input to match market quotes on options at all days, all strikes, and all maturities..   
Implied volatility is the same as the security's return volatility (standard deviation).  

o In reality, the BMS assumptions are violated. With one $\sigma$ input, the BMS model can only match one market quote at a specific date, strike, and maturity.  

The IVs at different $(t,K,T)$ are usually different - direct evidence that the BMS assumptions do not match reality.   
IV no longer has the meaning of return volatility.   
IV still reflects the time value of the option.   
The intrinsic value of the option is model independent (e.g., $e^{-r(T-t)}(F-K)^{+}$ for call), modelers should only pay attention to time value.  

# Implied volatility at (t, K, T)  

At each date t, strike $\boldsymbol{\kappa}$ , and expiry date T, there can be two European options: one is a call and the other is a put..   
The two options should generate the same implied volatility value to exclude arbitrage. Recall put-call parity: $c-p=e^{r(T-t)}(F-K).$ The difference between the call and the put at the same $(t,K,T)$ is the forward value. The forward value does not depend on (ii) model assumptions, (ii) time value, or (ili) implied volatility.  

At each $(t,K,T)$ , we can write the in-the-money option as the sum of the intrinsic value and the value of the out-of-the-money option:.  

If $F>K$ , call is ITM with intrinsic value $e^{r(T-t)}(F-K)$ , put is OTM. Hence, $c=e^{r(T-t)}(F-K)+p.$   
If $F<K$ , put is ITM with intrinsic value $e^{r(T-t)}(K-F)$ , call is OTM. Hence, $p=c+e^{r(T-t)}(K-F)$   
If $F=K$ , both are ATM (forward), intrinsic value is zero for both options. Hence, $c=p$  

# Liuren Wu  

# Implied volatility quotes on OTC currency options  

At each date t and each fixed time-to-maturity $\tau=(T-t)$ , OTC currency options are quoted in terms of  

Delta-neutral straddle implied volatility (ATMV):  

A straddle is a portfolio of a call $\&$ a put at the same strike. The strike here is set to make the portfolio delta-neutral: eq(T-t)N(di) $\begin{array}{r}{-e^{q(T-t)}N(-d_{1})=0\Rightarrow N(d_{1})=\frac{1}{2}\Rightarrow d_{1}=}\end{array}$  

25-delta risk reversal: $R R_{25}=I V(\Delta_{c}=25)-I V(\Delta_{p}=25).$  

25-delta butterfly spreads: BF25 = $(I V(\Delta_{c}=25)+I V(\Delta_{p}=25))/2-A T M V.$  

# From delta to strikes  

o Given these quotes, we can compute the IV at the three moneyness (strike) levels:  

$$
\begin{array}{r c l r}{I V}&{=}&{A T M V}&{a t}&{d_{1}}\ {I V}&{=}&{B F_{25}+A T M V+R R_{25}/2\quad a t}&{\Delta_{c}}\ {I V}&{=}&{B F_{25}+A T M V-R R_{25}/2\quad a t}&{\Delta_{F}}\end{array}
$$  

The three strikes at the three deltas can be inverted as follows:  

$$
\begin{array}{l l}{F\exp\left(\frac{1}{2}I V^{2}\tau\right)}&{a t}\ {F\exp\left(\frac{1}{2}I V^{2}\tau-N^{-1}(\Delta_{c}e^{q\tau})I V\sqrt\tau\right)}&{a t}\ {F\exp\left(\frac{1}{2}I V^{2}\tau+N^{-1}(\left\vert\Delta_{p}\right\vert e^{q\tau})I V\sqrt\tau\right)}&{a t}\end{array}
$$  

o Put-call parity is guaranteed in the OTC quotes: one implied volatility at each delta/strike.  

These are not exactly right... They are simplified versions of the much messier real industry convention..  

# Example  

On 9/29/2004, I obtain the following quotes on USDJPY: $S_{t}=110.87.$ ATMV = 8.73, 8.5, 8.66, $R R_{25}=-0.53$ , 0.7, -0.98, and $B F_{25}=0.24$ , 0.26, 0.31 at 3 fixed maturities of 1, 3, and 2 months. (The quotes are in percentages).  

o The USD interest rates at 3 maturities are: 1.82688, 1.9, 2.31. The JPY rates are 0.03625, 0.04688, 0.08125. (Assume that they are continuously. compounding). All rates are in percentages..  

o Compute the implied volatility at three moneyness levels at each of the three maturities. Compute the corresponding strike prices.   
o Compute the invoice prices for call and put options at these strikes and maturities.  

# Violations of put-call parities  

On the exchange, calls and puts at the same maturity and strike are quoted/traded separately. It is possible to observe put-call parity being violated at some times.  

Violations can happen when there are market frictions such as short-sale constraints.   
For American options (on single name stocks), there only exists a put-call inequality. The "effective" maturities of the put and call American options witl same strike and expiry dates can be different.  

The option with the higher chance of being exercised early has effectively a shorter maturity.  

o Put-call violations can predict future spot price movements.  

One can use the call and put option prices at the same strike to compute an "option implied spot price:". $S_{t}^{o}=\left(c_{t}-p_{t}+e^{-r\tau}K\right)e^{q\tau}.$ The difference between the implied spot price and the price from the stock market can contain predictive information: $S_{t}-S_{t}^{o}$  

# The information content of the implied volatility surface  

,At each time. $t$ , we observe options across many strikes K and maturities ${\boldsymbol{\tau}}={\boldsymbol{T}}-t.$   
o When we plot the implied volatility against strike and maturity, we obtain an implied volatility surface.   
If the BMS model assumptions hold in reality, the BMS model should be able to match all options with one $\sigma$ input. The implied volatilities are the same across all $\boldsymbol{\kappa}$ and $\tau$ The surface is flat.. We can use the shape of the implied volatility surface to determine what. BMS assumptions are violated and how to build new models to account for. these violations. For the plots, do not use $\boldsymbol{\kappa}$ $K-F$ $K/F$ or even In $K/F$ as the moneyness measure. Instead, use a standardized measure, such as ATMV, d2, d, or delta. Using standardized measure makes it easy to compare the figures across maturities and assets.  

# Implied volatility smiles & skews on a stock  

![](58664768c3b2ab5ac188bd6bda47cad18da63978491994d420590d70aecdbec7.jpg)  

# Implied volatility skews on a stock index (SPX)  

![](d131d49ce404e17b55c3ad6e85eb1ae1d8d254e23064bf5c6792ba95b9299215.jpg)  

# Average implied volatility smiles on currencies  

![](fb2799538b2966e5023406e8401ec6bb116ac068774ba2309cd5646920e4dacb.jpg)  

Maturities: 1m (solid), 3m (dashed), 1y (dash-dotted)  

# Return non-normalities and implied volatility smiles/skews  

BMS assumes that the security returns (continuously compounding) are normally distributed. In $S_{T}/S_{t}\sim{\cal N}\left((\mu-{\textstyle\frac{1}{2}}\sigma^{2})\tau,\sigma^{2}\tau\right).$  

$\mu=r-q$ under risk-neutral probabilities.  

o A smile implies that actual OTM option prices are more expensive than BMS model values.  

$\Rightarrow$ The probability of reaching the tails of the distribution is higher than that from a normal distribution.   
$\Rightarrow$ Fat tails, or (formally) leptokurtosis.  

A negative skew implies that option values at low strikes are more expensive than BMS model values.  

$\Rightarrow$ The probability of downward movements is higher than that from a normal distribution.   
$\Rightarrow$ Negative skewness in the distribution..  

Implied volatility smiles and skews indicate that the underlying security return distribution is not normally distributed (under the risk-neutral measure -We are talking about cross-sectional behaviors, not time series)  

# Quantifying the linkage  

$$
\mathbf{\Psi})\approx A T M V\left(1+\frac{\mathsf{S k e w.}}{6}d+\frac{\mathsf{K u r t.}}{24}d^{2}\right),d=
$$  

o If we fit a quadratic function to the smile, the slope reflects the skewness c the underlying return distribution.   
The curvature measures the excess kurtosis of the distribution.   
A normal distribution has zero skewness (it is symmetric) and zero excess kurtosis.   
This equation is just an approximation, based on expansions of the normal density (Read "Accounting for Biases in Black-Scholes."). The currency option quotes: Risk reversals measure slope/skewness, butterfly spreads measure curvature/kurtosis.. Check the VOLC function on Bloomberg.  

# Revisit the implied volatility smile graphics  

For single name stocks (AMD), the short-term return distribution is highly fat-tailed. The long-term distribution is highly negatively skewed.   
For stock indexes (SPX), the distributions are negatively skewed at both short and long horizons.   
For currency options, the average distribution has positive butterfly spreads (fat tails).   
Normal distribution assumption does not work well.   
Another assumption of BMS is that the return volatility $(\sigma)$ is constant - Check the evidence in the next few pages.  

# Stochastic volatility on stock indexes  

![](c299852caa58aabe5368461bc13a3f07116bbf986a983b4844ccbe34d366b7a7.jpg)  

At-the-money implied volatilities at fixed time-to-maturities from 1 month to 5 years.  

# Stochastic volatility on currencies  

![](ffd9658429ef07c327dede9538a107cbedec9488d6978ed2e0e41a4f578b70e4.jpg)  

Three-month delta-neutral straddle implied volatility.  

# Stochastic skewness on stock indexes  

![](22438c94acf5da0f8802f14e41f956e109eb8baf09bed7855c64c8b7baf07e11.jpg)  

Implied volatility spread between $80\%$ and $120\%$ strikes at fixed time-to-maturities from 1 month to 5 years.  

# Stochastic skewness on currencies  

![](e6e55dd313ca0a92ef196d3841960201c7acb81e3907343e56fac2908ed4d6e0.jpg)  

Three-month 10-delta risk reversal (blue lines) and butterfly spread (red lines)  

# What do the implied volatility plots tell us?  

Returns on financial securities (stocks, indexes, currencies) are not normally distributed.  

They all have fatter tails than normal (most of the time).. The distribution is also skewed, mostly negative for stock indexes (and sometimes single name stocks), but can be of either direction (positive or negative) for currencies..  

The return distribution is not constant over time, but varies strongly.  

The volatility of the distribution is not constant.   
Even higher moments (skewness, kurtosis) of the distribution are not constant, either.  

o A good option pricing model should account for return non-normality and its stochastic (time-varying) feature.  

# Weird implied volatility shapes  

Sometimes, the implied volatility plot against moneyness can show weird shapes:  

Implied volatility frown - This does not happen often, but it does happen.  

It is more difficult to model than a smile.  

The implied volatility shape around corporate actions such as mergers, takeovers, etc.  

Although most of our models are time homogeneous, calendar day effects are important considerations in practice. How to reconcile the two?  

Build a business calendar and modify the option time to maturity based on business activities:  

Treat non-trading days as zero (or a small fraction) of one day.  

Treat each earnings announcement date as two days.  

Pre-process the data as much as possible before applying to a model  

Most deterministic components should be pre-processed.  