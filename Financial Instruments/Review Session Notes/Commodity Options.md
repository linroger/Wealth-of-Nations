---
linter-yaml-title-alias: COMMODITY OPTIONS
title: COMMODITY OPTIONS
tags:
  - call_option
  - commodity_options
  - commodity_price_hedging
  - jet_fuel
  - options_strategy
aliases:
  - Commodity Options
  - Options Hedging
key_concepts:
  - Call option parameters
  - Commodity price hedging
  - Evaluating option performance
  - Jet fuel price changes
  - Options for hedging
---

# COMMODITY OPTIONS
## 1. COMMODITY PRICE HEDGING USING OPTIONS

### 1.1. ASSUMPTIONS

1. Date at which option can be exercised versus date at which commodity is needed.
2. Pass through of change in oil price to a change in jet fuel price.
3. Rate of conversion between 1 barrel of oil and 1 barrel of jet fuel.

### 1.2. OPTIONS UNDER A STRAIGHT INSURANCE STRATEGY

#### 1.2.1. PARAMETERS

a. Annual jet fuel consumption in gallons:$C > 0$.
b. Hedge percentage:$x \in [0,1]$.
c. Strike price on call option for oil:$\$P > 0$.

#### 1.2.2. IMPLICIT SHORT POSITION

Since Southwest consumes jet fuel in the future, it has an implicit short position on jet fuel. Thus, if jet fuel prices rise in the future, then Southwest makes a loss. Conversely, if jet fuel prices fall, then Southwest makes a profit.

##### 1.2.2.1. DETERMINING NUMBER OF OPTIONS

3. Compute hedge jet fuel quantity in barrels for Q1 in 2008.

$$H(C, x) = C \cdot \frac{1}{4} \cdot x \cdot \frac{1}{42}$$

4. Takeaway: If the oil price per barrel rises increases by$\Delta$between December 31, 2007, and March 31, 2008, then Southwest makes a loss of$\$\\Delta$on each barrel that is hedged. Given a hedge position comprising$H(C, x)$barrels, Southwest makes a loss of$H(C, x) \cdot \Delta$.
5. The role of options: [Options](Options.md) provide a hedge against changes in the oil price per barrel.
6. Payoff from option: Given a call option on oil with a strike price$P$, if the oil price per barrel rises to$(P + \Delta)$, then each option yields a profit of$\$1,000 \cdot \Delta$since each option trades on one lot of 1,000 oil barrels. What is the profit from the call option if the oil price per barrel falls to$(P - \Delta)$?
7. Optimal number of options: The optimal number of options is that which, if the oil price per barrel rises by 1 USD between December 31, 2007, and March 31, 2008, then Southwest will make a profit of 1 USD on each barrel that is hedged.

$$N \cdot 1000 \cdot \Delta\text{ Profit on Option} = H(C, x) \cdot \Delta\text{ Loss from Implicit Short Position}$$

Does the optimal number of options$N$depend on the USD change in the oil price per barrel given by$\Delta$?

8. Relaxing pass-through price assumption: Suppose a$\$\\Delta$change in the oil price per barrel induces a$y \\cdot \\Delta$change in the jet fuel price per barrel, where$y > 1$. The optimal number of options satisfies the following equation.

$$N \cdot 1000 \cdot \Delta = H \cdot y \cdot \Delta$$

##### 1.2.2.2. EVALUATING PERFORMANCE OF OPTIONS

1. Suppose a$\Delta$change in the oil price per barrel induces a$y \cdot\Delta$change in the jet fuel price per barrel, where$y > 1$. Suppose one purchases options assuming the pass-through is one-for-one. What is the expected profit or loss from this strategy?
2. Number options assuming one-for-one pass-through.

$$N^{(1)} = \frac{H(C, x)}{1000}$$

3. Number of options assuming actual pass-through. Note that$N^{(2)} > N^{(1)}$since$y > 1$.

$$N^{(2)} = \frac{H(C, x) \cdot y}{1000}$$

4. Given the implicit short position, the expected loss on each barrel that is hedged from a$\$\\Delta$change in the oil price per barrel is$H(C, x) \cdot y \cdot \Delta$. Are the number of options$N^{(1)}$sufficient to offset this loss?

### 1.3. OPTIONS UNDER A COLLAR STRATEGY

#### 1.3.1. DETERMINING ZERO COST COLLAR STRATEGY (PART I)

1. Positions: A collar strategy requires selling a put option (short) to finance buying a call option (long).
2. Zero-cost: Let$c(P) > 0$denote option price as a function of the strike price. Given a target strike price$P_c > 0$for the call option, the optimal choice of the strike price$P_p > 0$is that which yields a zero net payoff.

$$c(P_p) - c(P_c) = 0$$

#### 1.3.2. DETERMINING ZERO COST COLLAR STRATEGY (PART II)

1. Suppose instead one chooses a strike price for the put option. To satisfy the zero-cost at inception, one must determine the number of put options that satisfies zero-cost.
2. Recall the number of call options that exactly offsets the loss from the implicit short position.$$N_c \cdot 1000 \cdot \Delta\text{ Profit on Call Option} = H(C, x) \cdot \Delta\text{ Loss from Implicit Short Position}$$
3. Given a strike price$P_c$for the call option and a strike price$P_p$for the put option, determine the number of put options$N_p$.$$N_c \cdot P_c = N_p \cdot P_p$$
