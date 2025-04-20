---
linter-yaml-title-alias: LECTURE NOTE 4-MULTIPERIOD BINOMIAL TREES
title: LECTURE NOTE 4-MULTIPERIOD BINOMIAL TREES
tags:
  - binomial_trees
  - multiperiod_model
  - option_pricing
  - replicating_portfolio
  - risk_neutral_pricing
aliases:
  - Binomial Tree
  - Multi-Step Trees
  - One Step Binomial Trees
  - Two-Step Binomial Trees
key_concepts:
  - American option valuation
  - Binomial tree pricing
  - Option pricing methodology
  - Replicating portfolio
  - Risk neutral valuation
---

# Teaching Note 4-Multiperiod Binomial Trees

%% Begin Waypoint %%
- **[[Teaching Note 4-Multiperiod Binomial Trees]]**
	- [[Financial Instruments/Lecture Notes- Financial Instruments/Teaching Note 4-Multiperiod Binomial Trees/Binomial Option Pricing]]
	- [[Binomial Tree Steps]]
	- [[Calculate Stock Prices at Different Nodes]]
	- [[Options Strategies Construction]]
	- [[Teaching Note 4-Multiperiod Binomial Trees]]
	- [[Teaching Note 7- [[Exotic Options and Derivative Pricing By Monte Carlo Simulation]]
	- [[Teaching Note 7- [[Lecture Note 6-Implied Volatility]]
	- [[The Pricing of Options and Corporate Liabilities]]

%% End Waypoint %%

**[[Teaching Note 1Forward Rates Agreement]]**
 [[Teaching Note 2-Futures Contracts]]
 **[[Teaching Note 3 SwapsFinancial Instruments]]**
 **[[Teaching Note 4-Multiperiod Binomial Trees]]**
 [[Teaching Note 5Black Scholes Formula]]
 [[Teaching Note 6-Implied Volatility]]
 [[Teaching Note 7-Exotic Options And Derivative Pricing By Monte Carlo Simulation|LECTURE NOTE 7-EXOTIC OPTIONS AND DERIVATIVE PRICING BY MONTE CARLO SIMULATION]]
 [[Teaching Note 8 American Options]]
 [[Teaching Notes 9Corporate Securities And Credit Derivatives]]
 [[Teaching Notes 9ACredit Default Swaps]]
 [[Teaching Notes 10Interest Rate Derivatives]]
[PSET 5 Financial Instruments](PSET%205%20Financial%20Instruments.md)
[Option Pricing With Multiperiod Binomial Tree](Option%20Pricing%20With%20Multiperiod%20Binomial%20Tree.md)

# LECTURE 4 BINOMIAL TREE
- **1. Binomial Trees**
		  - **1.1 One Step Binomial Trees**
		  - **1.2 Replicating Portfolio**
- **2. Risk Neutral Pricing**
- **3. Two-Step Binomial Trees**
- **4. Multi Step Trees**
		  - **4.1 Binomial Trees and the Log-normal Distribution of Stock Returns**
**Key Concepts**
		  - **Binomial Trees**
			 - Binomial trees are a useful tool to introduce fundamental techniques for pricing derivative securities,  specifically Risk Neutral Pricing.
			 - They are simple to understand and offer a pricing methodology for complex problems.
		  - **Applications:**
			 - Used as a standard numerical procedure for solving American options,  or options with time-varying volatility.
**One Step Binomial Trees**
		  - Evaluating a stock at$t = 0$.
		  - At$t = 1$,  stock can be:
			 -$S_{1;u} = 70$with probability$q = 0.7$,  or
			 -$S_{1;d} = 35$with probability$1 - q = 0.3$.
		  - Given an expected return of$R = 19\%$,  the market value today:

 -$$S_0 = \frac{q \times S_{1;u} + (1 - q) \times S_{1;d}}{1 + R} = \frac{0.7 \times 70 + 0.3 \times 35}{1.19} = 50$$

.
		  - Stock tree is given by
		  -![|300](IMG-20240913171226954.png)
**Expected Return and Volatility on Binomial Trees**
		  - Expected (Gross) Return:
			 -$$E_0\left[\frac{S_1}{S_0}\right] = q \times \left[\frac{S_{1;u}}{S_0}\right] + (1 - q) \times \left[\frac{S_{1;d}}{S_0}\right] = 1.19$$

.
		  - Variance calculation and standard deviation (volatility):
			 -$\sigma = \sqrt{0.1029} = 0.3207$.
**Option Prices on a Binomial Tree**
		  - Pricing a call option with maturity$T = 1$and strike price$K = 50$.
			 - The value of a call option at$T = 1$:
				- In the Up Node:$c_{1;u} = \max(S_{1;u} - K,  0) = \max(70 - 50,  0) = 20$
				- In the Down Node:$c_{1;d} = \max(S_{1;d} - K,  0) = \max(35 - 50,  0) = 0$
			 - Determining the value of the call option at$T = 0$(denoted as$c_0$).
			 -![|400](IMG-20240913171235433.png)
**Replicating Portfolio**
		  - Assuming a continuously compounded interest rate$r = 0.11$.
		  - Construction of a portfolio of stocks and bonds:
			 - Position$\delta = 0.5714$in stocks,  dollar value$\delta \times S_0 = 28.5714$
			 - Position of$B_0 = -17.9167$in bonds (negative indicates short bonds).
		  - Portfolio value today:$P_0 = 28.5714 - 17.9167 = 10.6547$
		  - Portfolio value at$T = 1$in both Up and Down Nodes.
		  - Demonstrating no arbitrage:$c_0 = P_0$.
**Origin of the Replicating Portfolio**
		  - Concept of an arbitrageur buying a call option and hedging it using delta ($\delta$) stocks.
		  - Portfolio value$$\Phi_0 = c_0 - \delta \times S_0$$
		  - Delta Hedging: Ensuring portfolio value remains constant regardless of stock movement at$t = 1$.
			 -$$\Phi_{1;u} = \Phi_{1;d}$$
			 -$$c_{1;u} - \delta \times S_{1;u} = c_{1;d} - \delta \times S_{1;d}$$
			 - Solving for $\delta$ as the sensitivity of the call price to changes in the stock price.
**Further Analysis of the Replicating Portfolio**
	  - Ensuring equal portfolio value in both up and down nodes.
	  - Present value calculation of the portfolio:$$\Phi_0 = e^{-rT} \times \Phi_{1;u}$$
	  - Deriving $c_0$ from $$\Phi_0 = c_0 - \delta \times S_0$$
	  - Relationship with the replicating portfolio$P_0 = \delta \times S_0 + B_0$(equivalent to$c_0$by no arbitrage).
		 - Bond position$$B_0 = \Phi_0 = e^{-rT} \times (c_{1;u} - \delta \times S_{1;u})$$

.
**Example - Call Option**
		  - Example of call option pricing on a binomial tree.
		  - Calculating$\Delta$for the portfolio:
		  -![400](IMG-20240913171240842.png)
			 -$$\delta = \frac{c_{1;u} - c_{1;d}}{S_{1;u} - S_{1;d}} = \frac{20 - 0}{70 - 35} = 0.5714$$
		  - Portfolio long the call and short$\delta$stocks valued at time$i = 1$:$$\Phi_{1;u} = c_{1;u} - \delta \times S_{1;u} = 20 - 0.5714 \times 70 = -20$$$$\Phi_{1;d} = c_{1;d} - \delta \times S_{1;d} = 0 - 0.5714 \times 35 = -$20$$

		  - Bond position$B_0 = e^{-0.11} \times (-20) = -17.9167$(negative indicates borrowing).

![|300](IMG-20240913171244321.svg)

**Summing Up and Put Option Example**
  - Process for pricing any derivative security on the tree.
	 - Define$\delta$to invest in stocks.
	 - Compute amount of bonds.
	 - Compute value of security.
  - Example: Put option with strike price$K = 50$.
	 -$p_{1;u} = 0$and$p_{1;d} = \max(K - S_{1;d},  0) = 15$
	 - Delta calculation and bond position.
	 - Value of the put option and replicating portfolio.
	 - Replicating portfolio value at$t = 1$in both Up and Down Nodes.
**Probability of Moving Up in Binomial Trees**
  - The pricing formula does not include the probability of moving up, $q$.
  - Impact of$q$on option prices:
	 - Given$S_0,  S_{1;u}$and$S_{1;d}$,  option payoffs can be replicated without reference to probabilities. Thus,  no impact of$q$on prices.
	 - However, $q$determines the expected future stock price.$S_0$is determined as the present value (PV) of future stock price,  dependent on$q$.
	 - Since option values depend on$S_0$,  the probability$q$does impact the value of options.
**Risk Neutral Pricing**
  - Alternative procedure to the cumbersome one previously discussed.
  - Since given$S_0,  S_{1;u}$,  and$S_{1;d}$,  the probability$q$does not impact the option price,  a fake$q'$can be chosen for easier computations.
  - Risk Neutral Pricing: Choose$q'$so that all risky assets yield the risk-free rate.
	 - Find$q'$such that$E'_0\left[\frac{S_1}{S_0}\right] = e^{rT}$where$E'_0$is the expected value using$q'$.

	 -$$q' = \frac{S_0 \times e^{rT} - S_{1;d}}{S_{1;u} - S_{1;d}}$$

  - Risk Neutral Pricing formula:$\text{Price of any derivative security} = E'_0[e^{-rT} \times \text{Derivative Payoff}]$.
  -$E'_0[\cdot]$denotes the expected value using the fake probability$q'$.
  - Example calculations:
	 - Risk Neutral Probability:$q' = \frac{50 \times e^{-0.11} - 35}{70 - 35} = 0.5947$.
	 - Call Price:$$c_0 = e^{-rT} \times E'_0[c_1] = e^{-0.11} \times [q' \times 20 + (1 - q') \times 0] = 10.65$47$$
	 - Put Price:$$p_0 = e^{-rT} \times E'_0[p_1] = e^{-0.11} \times [q' \times 0 + (1 - q') \times 15] = 5.4464$$
	 - Forward Contract:$$f_0 = e^{-rT} \times E'_0[K - S_1] = e^{-0.11} \times [q' \times (50 - 70) + (1 - q') \times (50 - 35)] = -5.2083$$

.
**Risk Neutral Pricing: A Recipe**
 Steps to price derivative securities:

 1. Assume everyone is risk neutral.
 1. Compute probabilities consistent with risk neutralities.
 1. Price any derivative security using the formula:$$\text{Price of Derivative Security} = E'_0[e^{-rT} \times \text{Payoff at } T]$$

	  - This methodology is applicable even outside of the binomial tree model,  as an implication of no arbitrage.
**Risk Neutral Pricing: Examples**
  - Forward Contracts:
	 - Profit at$T$from a forward contract:$\text{Profit at } T = S_T - F_{0;T}$.
	 - Cost of entering a forward contract is zero.
	 - Expected profit,  if everyone is risk neutral,  should be zero:$E'_0[S_T - F_{0;T}] = 0$thus$$F_{0;T} = E'_0[S_T]$$

Return on stocks,  if everyone is risk neutral,  is the risk-free rate:$S_0 = e^{rT} \times E'_0[S_T]$.

	 - Thus, $$F_{0;T} = E'_0[S_T] = S_0 \times e^{rT}$$

**Risk Neutral Pricing - [Swaps](Swaps.md)**
		  - [Swaps](Swaps.md) involve counterparties agreeing to exchange cash flows at multiple times$T_1,  T_2,  …,  T_n$.
			 - Cash Flow at$T_i = (S_{T_i} - K)$.
		  - Swap value at time zero:$V_{\text{swap}}^0$can be computed using risk neutral pricing.

			 -$$V_{\text{swap}}^0 = \sum_{i=1}^{n} e^{-rT_i} \times E'_0[S_{T_i} - K]$$

Using$F_{0;T_i} = E'_0[S_{T_i}]$,  the swap value is$V_{\text{swap}}^0 = \sum_{i=1}^{n} e^{-rT_i} \times [F_{0;T_i} - K]$.

			 - To find Swap Price$K$such that$V_{\text{swap}}^0 = 0$,  solve for$$K = \sum_{i=1}^{n} w_i F_{0;T_i}$$where$$w_i = \frac{e^{-rT_i}}{\sum_{j=1}^{n} e^{-rT_j}}$$

.
**Risk Neutral Pricing and Discount Rates**
		  - Demonstrates the convenience of risk neutral pricing technique.
		  - This technique is specific to pricing derivative securities and follows from no arbitrage principles.
		  - Clarification: Market participants are not assumed to be risk neutral; they are risk averse.
			 - Dynamic hedging strategy (like delta hedging) mitigates risk,  allowing for the pretend assumption of risk neutrality in pricing derivative securities.

**Risk Neutral Pricing and Discount Rates - Forward Prices**
		  - The forward price$F_{0;T}$is the risk neutral expected future stock price:$F_{0;T} = E'_0[S_T]$.
		  - Forward prices provide limited information about true market expectations of future stock prices.
		  - Risk adjustments are necessary:
			 -$F_{0;T} = S_0 \times e^{rT}$.
			 - Using true expectations and expected return:$E[S_T] = S_0 \times e^{\mu T}$.
			 - Relation between forward price and expected future stock price:$F_{0;T} = e^{(\mu - r)T} \times E[S_T]$.
			 - The forward price is the expected future stock price,  discounted at the excess rate of return$(\mu - r)$.
**Risk Neutral Pricing and Discount Rates - Forward Prices**
		  - Example using currency exchange rates:
			 - Current Exchange Rate ($M_0$): 1.3375 (USD/EUR).
			 - One Year Forward Exchange Rate ($F_{0;1}$): 1.3506.
		  - Questioning market expectations on currency appreciation.
		  - Forward exchange rate as risk neutral expectation,  not representing true expectation.
		  - Forward rate depends on interest rate differential between two countries (as per TN 2).
		  - Relationship between forward prices and expected forward prices is complicated by risk.
**Two-Step Binomial Trees**
		  - Introducing a more complex example with a two-step binomial tree.
		  - Objective: Price an option with maturity$T = 2$and strike price$K = 50$.
		  - Tree structure with various stock prices at$i = 0,  1,  2$.
		  -![|300](IMG-20240913171248361.png)

**Methodology 1 - Dynamic Replication**
![600](IMG-20240913171254264.svg)

**Methodology 2 - Risk Neutral Pricing**
 ![500](IMG-20240913171259467.svg)

**Risk Neutral Pricing**
  - Concludes that risk neutral pricing simplifies computations considerably.
  - All computations can be easily programmed with a computer.
  - Introduces notation for nodes in the tree ($i,  j$) and the backward formula for computations.
  -$V_{i, j} = e^{-rh} \times E'_0[V_{i+1, j}]$where$h$is the time interval between steps in the tree.
**Risk Neutral Pricing - 2**
  - Application of risk neutral pricing with known probabilities of stock prices at time$T$.
  - Example calculations:
	 - Probability of different outcomes (e.g., $S_{2;uu},  S_{2;ud},  S_{2;dd}$).
	 - Calculating the price of a call option with strike$K = 50$:$c_0 = e^{-0.11 \times 2} \times 0.3347 \times (100 - 50) = 13.4294$.
	 - Price of a put and a short forward contract.
**Multi-Step Trees**
  - Extension of the two-step model to an$n$-step model.
  - Assumptions of constant expected return$\mu$and constant volatility$\sigma$.
  - Discretization of the time interval$[0,  T]$into$n$small intervals.
  - Each interval size is$h = T/n$,  and steps are denoted as$i = 0,  1,  \ldots,  n$.
**Multi-Step Trees**
 Description of a stock process in a multi-step tree:
		 -$S_{i+1} = S_i \times u$with probability$q$,  or$S_i \times d$with probability$1 - q$.
Conditions to approximate the expected return$\mu$and variance$\sigma^2$:

 1. Expected Return:$$E[S_{i+1}/S_i] = e^{\mu h}$$implying$$q \times u + (1 - q) \times d = e^{\mu$h}$$
 1. Variance:$E[(S_{i+1}/S_i / e^{\mu h})^2] = \sigma^2 \times h$leading to a specific relation for$u,  d, $and$q$.
	  - Assumption of symmetry: Percentage increase in stock$u$equals the inverse of the percentage decrease$1/d$.
**Multi-Step Trees**
  - Solution to the three equations for$u,  d, $and$q$:
	 -$u = e^{\sigma \sqrt{h}}$, $d = 1/u$,  and$q = \frac{e^{\mu h} - d}{u - d}$.
**Multi-Step Trees: Example**
  - Notes on indexing in multi-step trees:
	 - Time index:$i = 0,  1,  \ldots,  n$.
	 - Node index:$j = 0,  1,  \ldots,  n$.
  - Movement in the tree:
	 - An 'up' movement in$S$between$i$and$i + 1$corresponds to the same index$j$.
	 - A 'down' movement in$S$corresponds to an increase in the index$j$.
			 -![|500](IMG-20240913171304253.png)
**Multi-Step Trees - Derivative Pricing**
- Methodology for pricing a derivative security on a multi-step binomial tree using risk neutral pricing.
- Steps include:
	 1. Computing the risk neutral probability$q'$.
	 1. Moving backward on the tree with$V_{i, j} = e^{-rh} \times E^*[V_{I+1, j}]$.
			 - For call options,  start from the end of the tree and move backward applying the formula.
			 -![|500](IMG-20240913171308510.png)
**Multi-Step Trees - Probability Distribution of$S_T$**
  - Discussion on the [[Lecture 1- Probability Distributions of Returns|probability distribution]] of stock price at maturity$S_T$in a multi-step tree.
  - Illustration of how each node at maturity can be reached,  and the probability of reaching each node.
  - Probability calculation for each node$j$at maturity$T = nh$using binomial coefficients.
**Multi-Step Trees - Probability Distribution of$S_T$**
  - As the number of steps$n$in the binomial tree increases to infinity,  the distribution of the stock price$S_T$at maturity converges to a log-normal distribution.
  - A figure is referenced showing the probabilities of$S_T$for$n = 250$and$T = 1$.
		  -![|500](IMG-20240913171312134.png)
**Multi-Step Trees - Probability Distribution of$S_T$**
  - Probability density with respect to$\log(S_T)$.
  - Comparison with the normal density,  including mean and standard deviation calculations.
		  -![|500](IMG-20240913171315251.png)
**Multi-Step Trees and Black-Scholes Model** [Lecture Notes 5-Black Scholes Equation](Lecture%20Notes%205-Black%20Scholes%20Equation.md)
	  - The [[Lecture 1- Probability Distributions of Returns|probability distribution]] of$\log(S_T)$implied by the binomial tree matches the normal distribution.
	  - Formula for option price from the binomial tree.
	  - Approximation of$S_T$as log-normally distributed leads to the Black-Scholes formula.
	  - Discussion on the convergence of the call option price as$n$increases.
**Conclusions**
	  - Binomial trees are valuable tools for derivative pricing and can be programmed for computation.
	  - Useful for computing positions in dynamic replication portfolios.
	  - As the number of steps$n$increases,  the distribution at maturity converges to a log-normal distribution,  key to the Black-Scholes model.
	  - Application of binomial trees in computing the value of American options,  Monte Carlo simulations,  and pricing exotic securities.
	  - Risk-neutral pricing as a tool,  not an assumption of risk-neutral agents.
	  - Methodology stems from the use of a replicating portfolio to hedge exposure from a derivative security.
## BINOMIAL TREES ARE VERY USEFUL TOOLS FOR DERIVATIVE PRICING
- –  They can be easily programmed on computers to carry out the backward procedure to compute the value of any derivative security.
- –  Moreover,  we can use them to compute the positions in the dynamic replication portfolio.
- –  Under a particular assumption on how we build the tree,  as the number of steps n increases,  the distribution at maturity converges to a log-normal distribution,  the key assumption in Black-Scholes model.
- –  As we will see,  we can also use binomial trees to compute the value of American options (much harder than Europeans) as well as to carry out Monte Carlo simulations,  and price more complicated exotic securities. 
- Risk neutral pricing is another useful tool for pricing securities
- –  It is a tool,  and it is not the assumption that agents are risk neutral. They are not in our models.
- –  The risk neutral methodology stems from the fact that we can use a replicating portfolio to hedge the exposure from a derivative security. * The hedge eliminates all of the risk in the total position (e.g. short derivative and long replicating portfolio) * =⇒ we can choose the probabilities on the tree to make computations simpler.