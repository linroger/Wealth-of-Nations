---
title: Teaching Note 8-American Options
tags:
  - american_options
  - binomial_trees
  - early_exercise
  - no_arbitrage
  - option_pricing
aliases:
  - American Option
  - Binomial Model
  - Option Valuation
key_concepts:
  - American option features
  - Binomial tree method
  - Dynamic replication strategy
  - Early exercise decision
  - No arbitrage bounds
---

# Teaching Note 8-American Options

### 1. American options
1.1 No Arbitrage Bounds
1.2 Early Exercise

### 2. American Options on Binomial Trees
2.1 Two-Step Trees
2.2 Multi-Step Trees
2.3 Dynamic Replication

## AMERICAN OPTIONS
- An American Option is identical to a European Option,  but it can be exercised anytime before expiration.
- Examples of American options:
  1. Individual stock options
  1. Some options that essentially track indexes: e.g.,  SPY (CBOE)
  1. Some widely traded OTC interest rate options (e.g.,  American Interest Rate Swaptions,  options to enter into an interest rate swap)
  1. American options embedded in other contracts (e.g.,  Callable and Puttable bonds; Convertible Bonds; Mortgages)
  1. Real options (e.g.,  option to invest in a new project,  option to close down a plant,  etc.)
- In all these cases,  not only decide IF we want to exercise the option,  but also **WHEN**.

## AMERICAN OPTIONS: NO ARBITRAGE BOUNDS
1. **American options are at least as valuable as European options**:
$$C^{A}(S,    K,    t,    T) \geq C^{E}(S,    K,    t,    T)$$

$$ P^{A}(S,    K,    t,    T) \geq P^{E}(S,    K,    t,    T) $$
2. **American options with longer time to maturity are at least as valuable as the same option with shorter time to maturity**. If $T_2 > T_1$: $$C^{A}(S,    K,    t,    T_2) \geq C^{A}(S,    K,    t,    T_1)$$
$$P^{A}(S,    K,    t,    T_2) \geq P^{A}(S,    K,    t,    T_1) $$
3. **An American option is at least as valuable as its intrinsic value**:$$C^{A}(S,    K,    t,    T) \geq \max(S - K,     0); $$$$ P^{A}(S,    K,    t,    T) \geq \max(K - S,     0)$$
4. **An American Call option on non-dividend-paying stocks** has the following bound: $$C^{A}(S,    K,    t,    T) \geq \max(S - K \times e^{-r(T-t)},     0)$$

## AMERICAN OPTIONS: NO ARBITRAGE BOUNDS

1. An American Call option on a non dividend paying stocks has
$$C^{A}(S,    K,    t,    T)\geq\operatorname*{max}(S-K\times e^{-r(T-t)})$$
- To see this,  if *S < K* × e−r(T−t) =⇒ right-hand-side = 0 and the inequality is obvious.
- If *S > K* × e−r(T−t) and CA(S,  K,  t,  T) *< S* − K × e−r(T−t),  then (a) short stock S,  (b)
buy the option and (c) invest K × e−r(T−t). Today we get S − CA − Ke−r(T−t) > 0.
- At maturity T,
- If $S_{T} > K$,  exercise the option,  obtain ST − K,  cash in K from bond investment,  and pay the short −ST,  netting$0.
- If$S_{T} < K$,  cash in K from bond investment,  and pay the short −ST,  netting K−ST > 0
- (Note that the above no arbitrage bound also holds for European options.)

## EXAMPLE: SPY OPTIONS

- As an example,  consider the SPY options.
	- The following figures plot the March 17,  2023,  call and put options for various moneyness $K/S_0$.
	- The option values are normalized by the value of the index,  so the figure plots $Call/S_0$ and $Put/S_0$.
- The figure also plots the intrinsic value,  also normalized by the value of the index:
For Puts: Normalized Intrinsic Value$\,    =\dfrac{\max(K-S_{0})}{S_{0}}=\max(\text{Moneyness}-1,    0)$

For Calls: Normalized Intrinsic Value$\,    =\dfrac{\max(S_{0}-K)}{S_{0}}=\max(1-\text{Moneyness})$

## EXAMPLE: SPY OPTIONS EXAMPLE: SPY OPTIONS - NOTE

  ![SPY Options](https://storage.simpletex.cn/view/fK7NXo8YqYiiLI0nkGXrHP7fZNP4FMZ3Y)

![|500](CleanShot%202024-02-13%20-000374@2x.png)

1. American [Options](Options.md) are always as valuable as Europeans.
	- True in the diagram for puts,  not quite for calls
	- Differences in the underlying securities: paper index versus an ETF
	- Settlement differences: cash for SPX,  shares for SPY
- Tradings costs (e.g. bid-ask spread) bigger for SPY than SPX
1. The European ITM Put Option is below its intrinsic value,  but the American ITM Put Option is above.
1. The American Put option touches the intrinsic value for high$\frac{K}{S_0}$..
1. The American Call option appears close to being equal to the European Call option for every$\frac{K}{S_0}$.

## AMERICAN CALL OPTIONS: EARLY EXERCISE

- **Question**: Should you ever exercise an American Call option on a non dividend paying stock before maturity?
- **Example**: Example: You own a 3-month Call option with $K=100$,  and today $S=105$. Should you exercise now or wait until maturity?
  - Since $C(S,    K,    T) \geq \max(0,     S - K \times e^{-rT})$,  selling the option is better as $C(S,    K,    T) > S - K$.
	- If you exercise you gain $5 = S − K$.
	- If you wait one more day,  you may get more as the price may increase.
But you may also lose.
- Should you exercise now or wait until maturity?
- If you sell the option,  you get $C(S,     K,     0,     T)$ today. If you exercise,  you get $S − K$.
- We know that for non dividend paying stocks
$$C(S,    K,    T)\geq\operatorname*{max}(0,    S-K e^{-r T})$$
- Since $S − Ke^{−rT} > S − K > 0$,  selling the option is better as $C(S,     K,     0,     T) > S − K$

## AMERICAN CALL OPTIONS: EARLY EXERCISE

- What if we cannot sell the option? Is it optimal to exercise early?
	  - No. If you exercise,  you get $S - K$,  which at maturity is $(S - K)e^{rT}$.
	  - Instead,  keep the call,  short the stock for $S$ and buy bonds.
	 - At $T$,  you have $$\left.Se^{rT}-S_T+\max(S_T-K)=\left\{\begin{array}{ll}Se^{rT}-K=(S-K)e^{rT}+K(e^{rT}-1)&\mathrm{if}&S_T>K\\Se^{rT}-S_T>Se^{rT}-K&\mathrm{if}&S_T<K\end{array}\right.\right.$$ - Either way,  it is more than $(S - K)e^{rT}$. Especially if $S_T < K$ at maturity,  we make a killing.
- "An American Call on a non dividend paying stock is always worth more alive than dead"
- Intuition:
  - If we exercise early,  we lose both
	 1. The time value of money on the strike.
	 1. The value of the right to exercise the option in the future.
- When is it optimal to exercise early?

## AMERICAN OPTIONS. PROS AND CONS OF EARLY EXERCISE

- If we exercise a Call early:
	- (Good) We get any dividends paid between now and maturity
	- (Bad) We pay K today instead of in the future =⇒ lose the interest on K.
	- (Bad) We pay K today for a stock that may be worth less than K at T.
- Even if $S > K$ today,  it may well be that $S_{T} < K$,  in which case we will not want to exercise.
- S today reflects all of the possible possibilities,  including low$S_T$.
- By waiting,  we reserve the right of **not to exercise if** $S_T < K$
- "But if we exercise we get $S − K$ today… "
	- Yes,  but you can get more by shorting the stock and buying bonds (see earlier). In fact,  this strategy pays handsomely exactly when $S_T < K$ at maturity.

## AMERICAN OPTIONS. PROS AND CONS OF EARLY EXERCISE

- If we exercise a Put early:
	- (Good) We receive K today instead of in the future =⇒ gain the interest on K.
	- (Bad) We lose any dividends paid between now and maturity.
	- (Bad) We receive K today for a stock that may be worth more than K at T.
∗ Even if *S < K* today,  it may well be that$S_{T} > K$,  in which case we will not want toexercise.
∗ S today reflects all of the possible possibilities,  including high ST.
∗ By waiting,  we reserve the right of **not to exercise if**$S_{T} > K$.
- Still,  even if there is nƒo dividends,  put options may be worth exercise early.
- For example,  if the company goes bankrupt,  then S = 0. Exercising immediately is then optimal,  as you receive K today. It cannot get any better than this,  and waiting you lose the interest.

## AMERICAN OPTIONS. DIVIDEND RULES

- Suppose dividends are unknown,  but:
  $D^+ = \max PV[\mathrm{dividends~until~maturity}]$
  $D^- = \min PV[\mathrm{dividends~until~maturity}]$
- Then:
  - **Never exercise a call** if $D^+ < K \times (1 - e^{-rT})$.
  - **Never exercise a put** if $D^- > K \times (1 - e^{-r^{\prime}T})$.
- To see this,  consider the call (for the put it is similar).
- The value of a call is always higher than the value of a forward contract with the same strike price (the call always pays at least as much as the forward!):
$$
\begin{align}
C(S,     K,     t,     T) &\geq S - PV(D) - K e^{-rT} \\
              &\geq S - D^{+} - K e^{-rT} \\
              &> S - K(1 - e^{-rT}) - K e^{-rT} \\
              &= S - K
\end{align}
$$
- =⇒ Sell the option,  rather than exercise it.

## AMERICAN OPTIONS. DIVIDEND RULES - 2

- It is only optimal to exercise an American Call at maturity,  or just before a dividend payment.
- It is never optimal to exercise an American Put just before a dividend payment.
- Intuitively,  consider the figures
 ![500](CleanShot%202024-10-02%20-003074@2x.png)
- By exercising a Call at (1) instead of (2) you: (A) lose both the interest between (1) and (2),  and the right not to exercise; (B) gain nothing,  as there is no dividend between (1) and (2). It cannot be optimal.
- By exercising a Call at (3) instead of (2) you: (A) lose both the dividend,  and the right not to exercise; (B) gain a little interest,  but small given the small interval.
- By exercising a Put at (2) instead of (3) you: (A) lose both the dividend and the right not to exercise; (B) gain a little interest,  but small given the small interval.

## AMERICAN OPTIONS: PRICING AND OPTIMAL EXERCISE TIME

- How do we price American [Options](Options.md)? How can we compute the optimal exercise time?
- For instance,  you are long a Sep 07 put option on the S&P 100 index with strike price$K = 740.$
- On May 11 2007 the S&P 100 closed at 689.83. You are 7% in-the-money.
- Question: Is it time to exercise?
- Or keeping the option alive has still sufficient value to wait longer?
- In order to decide whether it is optimal to exercise,  we have to compare the payoff today (if exercised) with the expected payoff in the future (if waiting).
	- We exercise if and only if: $$K - S > \text{Discounted Expected Future Payoff if Wait}$$
- How do we compute the discounted expected future payoff if we wait?
- Binomial Trees are excellent tools that allow us to perform this computation.

## AMERICAN OPTION: TWO STEP TREE

- Let $S_{0}=100$;
- $K=100$,
- $T=1$,
- $r=2\%$,
- $\sigma=30\%\Longrightarrow u=e^{r\sqrt{T}}=1.34986$and
- $q^{*}=0.4707$.
- Consider a put option with K = 100. The European option is given by
-  ![500](CleanShot%202024-10-02%20-003075@2x.png)

## AMERICAN OPTION: TWO STEP TREE

- Consider now the American put option
- At maturity i = 2 the payoff of the American option is the same as the European option
$$p_{2,    j}^{A}=p_{2,    j}^{E}\quad\mathrm{~for~}\ j=u u,    \ u d,    \ d u,    \ d d$$
- At i = 1,  at each node u and d compare the payoff if exercise with expected payoff if wait.
- In node (1,  u) the put option is OTM =⇒ no exercise. Note that $p^{A}_{1,    u} = 0$.
- In node (1,  d)
	1. If exercise get K − S = 100 − 80.886 = 19.114.
	1. If wait,  the value of the option is equal to the European counterpart

Value of Option if Wait $=e^{-r/2}E^{*}[p_{2}^{A}|S_{1,    d}]=e^{-r/2}E^{*}[p_{2}^{E}|S_{1,    d}]=18.119$

- Thus,  **exercise in node** (1,  d) is optimal.
- =⇒ The value of the option in node (1,  d) is equal to 19.114. That is$$p_{1,    d}^{A}=\operatorname*{max}{(K-S_{1,    d},    \mathrm{Value~of~Option~if~Wait})}$$
- The value of the option at time 0 is then$$p_{0}^{A}=e^{-r/2}E^{*}\left[p_{1}^{A}\right]=e^{-r/2}\;(1-q^{*})\;p_{1,    d}^{A}=10.017$$

## AMERICAN OPTION: TWO STEP TREE

 ![500](CleanShot%202024-10-02%20-003076@2x.png)

## AMERICAN OPTIONS. MULTI STEP TREES

- The tree methodology can be easily extended to many steps. - Remember that the pair (*i,  j*) represent time i = 0,  1,  2*…,  n* and node j = 1,  2,  …,  n
- With European style derivatives,  we solve for prices Vi,  j using the rule
$$V_{i,    j}^{E}=e^{-r\times h}\times E^{*}\left[V_{i+1}^{E}|(i,    j)\right]$$
- where h = *T/n* is the time interval between steps.
- With American style derivatives,  we solve for prices$V_{i,    j}$using the rule
$$V_{i,    j}^{A}=\operatorname*{max}\Big\{\ g_{i,    j}\,    \ \ e^{-r\times h}\times E^{*}\left[V_{i+1}^{A}|(i,    j)\right]\Big\}$$
- where gi,  j is the payoff from the American derivative if exercise occurs in node (*i,  j*)
- For instance,  for the case of put options,  we have
$$p_{i,    j}^{A}=\operatorname*{max}\Big\{\ K-S_{i,    j}\,    \ \ e^{-r\times h}\times\big(q^{*}\times p_{i+1,    j}^{A}+(1-q^{*})\times p_{i+1,    j+1}^{A}\big)\Big\}$$

## AMERICAN OPTIONS. MULTI STEP TREES BINOMIAL TREE MODEL

 ![500](CleanShot%202024-10-02%20-003077@2x.png)

## MULTI STEP TREE: DOES IT WORK?

- Consider the relative pricing of S&P 500 options (European) and S&P 100 options (American)
- For instance,  the 5% in the money Sep Put have (renormalized) values of
$$p^{S\&P500}(1.05)=0.0491\qquad\mathrm{and}\qquad p^{S\&P100}(1.05)=0.0540$$
- The three month interest rate is r = 0.0483 and the dividend yield around δ = 0.0191.
- The implied volatility that exactly prices the S&P 500 put option is σ = 0.10366
- The value of the corresponding American Option is pA = 0.0529,  a little lower than the market value.

## MULTI STEP TREE: DOES IT WORK? BINOMIAL TREE MODEL

 ![500](CleanShot%202024-10-02%20-003078@2x.png)

-  ![500](https://storage.simpletex.cn/view/ffPgGtPeGrgkGlKC3pXOd7sbSkSlBTI7u)
## AMERICAN OPTIONS. DYNAMIC REPLICATION

- Can we "dynamically replicate" an American option using a portfolio of stocks and bonds?
- Yes! Once we solve for the optimal exercise strategy,  we have a standard option tree. - Consider the earlier example:

 ![500](https://storage.simpletex.cn/view/fniSs76T3dR8R2gYxCr02RG9gB4BAGpeC)

## AMERICAN OPTIONS. DYNAMIC REPLICATION

- Suppose you sold the option to a client. - At time i = 0 we must set up a portfolio that replicates pA
1. The same rule as in TN 4 applies:
1. Compute$\Delta=(p_{1,    u}^{A}-p_{1,    d}^{A})/(S_{1,    u}-S_{1,    d})=-0.447$
1. Compute bonds$B_{0}=e^{-r/2}\left(p_{1,    u}^{A}-\Delta S_{1,    u}\right)=54.733$
1. The replicating portfolio is$P_{0}=\Delta S_{0}+B_{0}=10.017=p_{0}^{A}$
- At time i = 1 the replicating portfolio has payoffs
	- In the Up Node $P_{1,    u}=\Delta S_{1,    u}+B_{0}e^{r/2}=0$
	- In the Down Node $P_{1,    d}=\Delta S_{1,    d}+B_{0}e^{r/2}=19.114$
- At time i = 1 we need to rebalance.
- In the up node,  ∆ = 0,  and so we are out of the market. - In the down node,  the option holder is supposed to optimally exercise the option,  and so we
simply hand them the payoff
$$P_{1,    d}=K-S_{1,    d}=19.114$$
- Note that the node (2,  d) is never reached under the optimal exercise strategy.

## AMERICAN OPTIONS. DYNAMIC REPLICATION
- What if the option holder does not exercise the American option in node $(1,    d)$?
   - In this case,  we must continue with the replicating portfolio until time $i = 2$.
   - The new replicating portfolio is:
	  - $\Delta_{1,    d} = \frac{p_{2,    du}^A - p_{2,    dd}^A}{S_{2,    du} - S_{2,    dd}} = -1$.
	  - $B_{1,    d} = e^{r/2}(p_2^A - \Delta_{1,    d} S_{2,    u}) = 99.005$.
   - The value of the new replicating portfolio in node $(1,    d)$ is $P_{1,    d}^{new} = \Delta_{1,    d} S_{1,    d} + B_{1,    d} = 18.119$.
   - The value is lower than the value obtained earlier: $P_{1,    d} = 19.114$ from the initial replicating strategy.
   - – = ⇒The fact that the counterpart forgets to exercise the American option at node (1,  d) make us earn money:
Profit from suboptimal exercise of option holder = $$P_{1,    d} − P^{new}_{1,    d} = 19.113 − 18.119 = 0.99$$
## CONCLUSION
- **American options** are harder to evaluate due to the timing decision of when to exercise (if at all).
   - The decision to exercise relies on the value of the option in case of no exercise.
   - The methodology requires a backward procedure to evaluate the option to wait.
- **Binomial trees** are useful due to the backward procedure,  but they are restrictive.
   - They are hard to use with multiple factors (e.g.,  if volatility is stochastic).
   - They are also challenging for path-dependent securities.
- **New methodologies**,  such as Monte Carlo simulations,  have been introduced to handle these complexities.