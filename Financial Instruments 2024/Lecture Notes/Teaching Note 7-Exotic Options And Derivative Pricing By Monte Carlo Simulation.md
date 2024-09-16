---
title: Teaching Note 7-Exotic Options And Derivative Pricing By Monte Carlo Simulation
---
**[[Teaching Note 1Forward Rates Agreement]]**
 [[Teaching Note 2-Futures Contracts]]
 **[[Teaching Note 3 SwapsFinancial Instruments]]**
 **[[Teaching Note 4-Multiperiod Binomial Trees]]**
 [[Teaching Note 5Black Scholes Formula]]
 [[Teaching Note 6-Implied Volatility]]
 [[Teaching Note 7-Exotic Options And Derivative Pricing By Monte Carlo Simulation]]
 [[Teaching Note 8 American Options]]
 [[Teaching Notes 9Corporate Securities And Credit Derivatives]]
 [[Teaching Notes 9ACredit Default Swaps]]
 [[Teaching Notes 10Interest Rate Derivatives]]

[Teaching Note 5 Risk Neutral Pricing](Teaching%20Note%205%20Risk%20Neutral%20Pricing.md)
[Teaching Note 6 Mortgage Backed Securities](Teaching%20Note%206%20Mortgage%20Backed%20Securities.md)

## FINANCIAL INSTRUMENTS TEACHING NOTE 7 EXOTIC OPTIONS AND DERIVATIVE PRICING BY MONTE CARLO SIMULATION

John Heaton The University of Chicago Booth School of Business

1.Risk Neutral Trees and Monte Carlo Simulations
1.1 One Step tree
1.2 Multi-Step Tree
1.3 Why Monte Carlo Simulations?
Monte Carlo Simulations without Trees
2.1 Lognormal Model
2.2 Multi Factors
2.3 Delta Calculation

## RISK NEUTRAL TREES

- Consider again a one-step tree (to begin with). - Assume$S_0$= 100; K = 100, T = 1, r = 2%, σ = 30%.
- Given that u = eσ
Given that$u=e^{\sigma\sqrt{T}}=1.34986$, the price of _any_ derivative security with payoff$V(S_{1})$can be computed as
⚠️upload failed, check dev console

$$V_{0}=E^{*}\left[e^{-rT}V(S_{1})\right]=e^{-rT}\left[q^{*}V(S_{1,u})+(1-q^{*})V(S_{1,d})\right]$$

- For instance, a call option has price given by

```tikzpicture
\usetikzlibrary{positioning}
\documentclass{standalone}
\begin{tikzpicture}
  % Define the nodes
  \node (i0) {$i = 0$};
  \node[below=1cm of i0,draw,inner sep=5pt] (box0) {
    \begin{tabular}{l}
      $S_0 = 100.000$ 
      $q_0^* = 0.4587$ 
      $c_0 = e^{-rT} \times q_0^* \times c_{1,u} = 15.731$
    \end{tabular}
  };
  
  % Nodes for i = 1
  \node[right=3cm of i0] (i1) {$i = 1$};
  \node[draw,above right=0.5cm and 1cm of i1,inner sep=5pt] (box1u) {
    \begin{tabular}{l}
      $S_{1,u} = 134.986$ 
      $c_{1,u} = 34.986$
    \end{tabular}
  };
  \node[draw,below right=0.5cm and 1cm of i1,inner sep=5pt] (box1d) {
    \begin{tabular}{l}
      $S_{1,d} = 74.082$ 
      $c_{1,d} = 0$
    \end{tabular}
  };
\end{tikzpicture}

```

$i=0$$i=1$$S_{1,u}=134.986$$c_{1,u}=34.986$$S_{0}=100.000$$q_{0}^{*}=0.4587$$c_{0}=e^{-rT}\times q_{0}^{*}\times c_{1,u}=15.731$$S_{1,d}=74.082$$c_{1,d}=0$

- An alternative way of computing the expected future payoff is to _simulate_ up and down movements using a computer.
- For instance, in Excel the function _RAND_() simulates a uniform between \[0, 1].
- Thus, RAND() _> $q^∗$ occurs with probability $(1 − q^∗)$, and vice-versa (e.g $q^∗ = 1$ implies that $(1 − q^∗) = 0$, and indeed _RAND_() can never be above $q^∗$).
- We can simulate _RAND_() many times, say N:
- Whenever the realization RAND() _> q_∗ we say that we went _down_ the tree;
- Whenever $RAND() _< q^∗$, we say we went up the tree.
- Compute the value of the stock price at time T = 1, S1,u or S1,d for each simulation
- Let $S^i_1$ denote the realization of S1 in simulation run i.
- Compute the payoff of the security at time T = 1 for each simulation run, e.g. $V(S^i_1) =max(S^i_1 − K, 0)$
- The value of the security is the average of the realizations
$$\tilde{V}_{0}=\mathrm{average~of~}\{e^{-r T}V(S_{1}^{1}),e^{-r T}V(S_{1}^{2}),e^{-r T}V(S_{1}^{3}),…,e^{-r T}V(S_{1}^{N})\}=\frac{1}{N}\sum\limits_{i=1}^{N}e^{-r T}V(S_{1}^{i})$$
- For instance, given $q^∗ = 0.4587$, we obtain the following table

![500](IMG-20240913171226935.png)
⚠️upload failed, check dev console
⚠️upload failed, check dev console
![](IMG-20240913171233708.png)

- With only N = 10 simulation, it is no surprise that the value of the security $\hat{V_0} = 17.147$ comes
rather different from the value from the tree ($V_0 = 15.731$).
- As N increases, the value gets more and more precise.
- How many simulations?
- The number of simulations$N$should be large enough to obtain a reasonable "standard error", that is, standard deviation of our estimate itself.
- This is computed as the standard deviation of our discounted payoff, divided by$\sqrt{N}$:$$\text{Standard error}=\frac{\text{Standard Deviation of}\{e^{-rT}V(S_{1}^{1}),e^{-rT}V(S_{1}^{2}),e^{-rT}V(S_{1}^{3}),…,e^{-rT}V(S_{1}^{N})\}}{\sqrt{N}}.$$
- In the previous example, the standard error was _s.e._ = 5.715
- This implies that with 95% probability, the true value of the security is between

$$\text{ConfidenceInterval}=[\hat{V}_0-2\times s.e.,\hat{V}_0+2\times s.e.]=[5.715,28.577]$$

- Given the number of simulations, we give 95% probability that the true value is between 5.715 and 28.577, a rather large interval.
- Increasing the number of simulations to N = 1000, we obtain $\hat{V_0} = 15.725$ with _s.e._ = 0.54.
- The confidence interval is \[14.644, 16.806], much tighter than before.
- The same logic applies to multi step trees.
- Consider a two step tree, with the same parameters
- ![500](IMG-20240913171240214.png)
$i=0$$i=1$$i=2$$S_{2,uu}=152.847$$S_{1,u}=123.631$$S_{0}=100$$S_{1,d}=80.886$$S_{2,dd}=65.425$
![500](IMG-20240913171243930.png)
- Again, the value of any derivative security with payoff V (S2) is given by

$$V(S)=E^{*}[e^{-r T}V(S_{2})]$$

- For instance, with N = 10 simulations, we may obtain something as follows:
![500](IMG-20240913171248005.png)

- With N = 1000 simuations, the price is $\hat{V_0}$ = 10.453 with _s.e._ = 0.657.
- The value from the risk neutral tree is instead 11.476
- A 10-step tree is as follows:
![500](IMG-20240913171253150.png)

- 10 simulated paths are given by (the price in the table refers to N = 1000 though.)
![500](IMG-20240913171258610.png)
## OPTION PRICES BY SIMULATIONS (ON THE TREE)

- The simulation paths are (they look like a tree, with missing branches).
![500](IMG-20240913171303496.png)
## WHY MONTE CARLO SIMULATIONS?

- Why do we need Monte Carlo Simulations on the tree, when we have the tree itself?
- Monte Carlo Simulations may be useful to price derivative securities with path dependent payoff.
	- That is, the value at maturity depends on the _path_ taken by the stock during the life of the security.
- For instance, Asian options have payoff given by
$$\text{Asian Call Option} = max(\text{Average of St from 0 to T} − K, 0)$$
$$\text{Asian Put Option} = max (K − \text{Average of St from 0 to T}, 0)$$

- These options are very hard to price on a tree without simulations.
- Consider a two step tree.
![500](IMG-20240913171307606.png)

- Even if $S_{2,ud}=S_{2,du}=100$, the payoff when the fınal price is 100 depends on the path of $S$, namely, whether $S_1=S_{1,u}=123.631$ or $S_1=S_{1,d}=80.886.$
- In this case, we can compute the value of the security on the tree $V_0=\Sigma_j=1^4Q_j^*V_{2,j}=7.45$
- 1000 Monte Carlo simuations yield $\widehat{V}_0=7.560$ with $s.e.=0.316$

## WHY MONTE CARLO SIMULATIONS?

![500](IMG-20240913171311645.png)

- When we move to multi-period trees, path dependent options become much difficult to price without Monte Carlo Simulations.
- The following picture shows the averages St over 10 paths.
- While the original paths look like the recombining tree we started out with, the averages look like paths on a non-recombining tree.
- Non recombining trees are much harder to evaluate numerically for a large number of time steps

## WHY MONTE CARLO SIMULATIONS? WHY MONTE CARLO SIMULATIONS?
- The number of path dependent options is very large.
- Besides the asian option discussed, some other popular examples are:
- Barrier Options
- The option expires if stock hits an upper (up and out) or a lower (down and out) barrier
- The option comes into existence if the stock hits and upper (up and in) or a lower (down and in) barrier
- Lookback Options: The final payoff depends on the maximum or minimum value achieved by the stock before maturity. For instance:
$$g_{T}=(\operatorname*{max}(S_{0},…,S_{T})-S_{T})$$
- Asian Strike Options: The strike price is equal to the average stock price. E.g.
$$g_{T}=\operatorname*{max}(S_{T}-A v e r a g e(S_{0},…,S_{T}))$$

## MONTE CARLO SIMULATIONS WITHOUT TREES

- There is no reason to limit MC simulations to trees.
- The main motivation behind pricing by MC simulations is risk neutral pricing.
∗ That is, dynamic replication can be achieved.
- These no arbitrage conditions are naturally satisfied on trees, as we have seen.
- However, once we decide we can use risk neutral pricing, we can simulate out of any distribution.
- In particular, we can use the lognormal model, as in Black and Scholes
- Risk neutral pricing implies that over a small period
$$E^{*}\left(\frac{S_{t+h}}{S_{t}}\right)=e^{r h}$$

## MONTE CARLO SIMULATIONS UNDER LOG NORMALITY

- One way to simulate is then to use the following algorithm
$$S_{t+h}=S_{t}\times e^{(r-\frac{\sigma^{2}}{2})h+\sigma\sqrt{h}\epsilon_{t}}$$
- where $ϵ_t ∼ N(0, 1)$
- The rules of the log-normal distribution imply$$E^{*}\left(\frac{S_{t+h}}{S_{t}}\right)=e^{(r-\frac{\sigma^{2}}{2})h+\left\{E^{*}[\sigma\sqrt{h}\times\epsilon_{t}]+1/2Var[\sigma\sqrt{h}\times\epsilon_{t}]\right\}}=e^{rh}$$
- Moreover, σ2 converges to the (annualized) variance of log returns _V ar_[log(St+h/St)]

## MONTE CARLO SIMULATIONS UNDER LOG NORMALITY

- For instance, a few 10-period paths are plotted in the next figure
![500](IMG-20240913171314302.png)
## MONTE CARLO SIMULATIONS UNDER LOG NORMALITY

- MC price of put and calls under Black and Scholes assumptions (1000 simulations)
![500](IMG-20240913171318591.png)

## MONTE CARLO SIMULATIONS WITH MANY "FACTORS"

- The Monte Carlo Simulation method to price options can be extended to price derivative securities that depend on multiple factors. For instance:
	- time varying interest rates
	- time varying volatility
	- payoffs on the relative value of different stocks, exchange rates etc.
- The methodology is the same
	1. Simulate _risk neutral_ factors
	2. Compute the cash flows of the security
	3. Compute the present value, discounting at the risk free rate
	4. Average all of the simulated paths.
- One difficulty is with obtaining risk neutral dynamics for factors:
- Traded factors are simple: the expected return on such factor must be the risk free rate.
- It is harder for non-traded factors (e.g. interest rates, volatility). We attack this problem later on.

## MONTE CARLO SIMULATIONS WITH MANY "FACTORS"

- Consider an option that pays the maximum between the stock return on IBM and Apple within
a prespecified period.

- That is, if $S_{0}$ and $N_{0}$ are the current prices of the two stocks, the payoff at maturity of the option is $$\text{Payoff at}T=\max\left(\frac{S_{T}}{S_{0}},\frac{N_{T}}{N_{0}}\right)$$
- How much would pay for this security?
- We can use Monte Carlo Simulations to find out.
- The risk neutral processes of St and Nt are the same as before, so we simulate

$$\begin{array}{l l l}{{S_{t+h}}}&{{=}}&{{S_{t}\times e^{(r-\frac{\sigma_{S}^{2}}{2})h+\sigma_{S}\sqrt{h\epsilon_{1,t}}}}}\\ {{}}&{{}}&{{}}\\ {{N_{t+h}}}&{{=}}&{{N_{t}\times e^{(r-\frac{\sigma_{N}^{2}}{2})h+\sigma_{N}\sqrt{h\epsilon_{2,t}}}}}\end{array}$$

- If IBM and Apple are correlated stocks (as they are), we need a methodology to simulate correlated shocks $ϵ_{1,t},ϵ_{2,t}$.
- Let $\hat{e}_{t}$ be a standard normal, uncorrelated with $\epsilon_{1,t}$. Then, define $$\epsilon_{2,t}=\rho\epsilon_{1,t}+\sqrt{1-\rho^{2}}\hat{e}_{t}$$
- **Claim**: $\epsilon_{2,t}$ has zero mean, variance 1, and correlation $\rho$ with $\epsilon_{1,t}$ (check!)

## MONTE CARLO SIMULATIONS WITH MANY "FACTORS"
- For each simulation run $i$, compute the discounted payoff
$$V^{i}=e^{-rT}\max\left(\frac{S_{T}^{i}}{S_{0}},\frac{N_{T}^{i}}{N_{0}}\right)$$
- The price of the security is then
$$\widehat{V}_{0}=\frac{1}{n}\sum_{i=1}^{n}V^{i}$$
- Assuming $σ_S = σ_N =0.3, r =0.02 and ρ =0.7,$ the value of this option is $\hat{V_0}$ = 1.134.
- As a second example, consider an option with the payoff$$\text{Payoff at}T=\max\left(\frac{S_{T}}{S_{0}}-\frac{N_{T}}{N_{0}}\right)$$
- That is, it pays only when the first stock (say IBM) does better than the second (say Apple).
- The same simulations show that the fair value of this option is $\hat{V_0}$ = 0.1
- Note that the difference between one option and another is simply the final payoff. The methodology is identical.
![500](IMG-20240913171321736.png)

## HOW CAN WE COMPUTE "∆" WITH MONTE CARLO SIMULATIONS?

- Once we have computed the value of the security, we may want to know what is its sensitivity
to changes in the stock.
- Computing the "$\Delta$" is not hard, and we use Monte Carlo simulations again.$$\Delta=\frac{d\ V(S)}{d\ S}\approx\frac{V(S+h)-V(S)}{h}$$
- Thus, compute V (S) and V (S + h) using MC simulations1
- Apply the above formula. - For instance, we obtained earlier the price of a call equal to c(100) = 13.359. - Using S = 101 we obtain c(101) = 13.979. =⇒ ∆ = (13.979 − 13.359)/1 = 0.62.
- Black and Scholes Delta is ∆ = N(d1) = 0.58. As N increases, the simulated ∆ converges to the true one.

## CONCLUSION

- The Monte Carlo Simulations Method is one of the main tools used by practitioners to price
complex securities under fairly general assumption about the underlying stochastic processes
- Just three steps:
	1. Simulate many paths of underlying stochastic variables under the _risk neutral_ probabilities
	2. For each path, compute the discounted simulated payoff of the security
	3. Compute the average
- MCS are especially useful to value _path dependent_ securities, or securities that depend on the. value of multiple underlying variables
- Barrier options, Asian options, Lookback options - Options on maximum, options on relative returns across securities
- MCS are also very useful to value securities under general processes for underlying stochastic variable, such as
	- Stochastic volatility
	- Stochastic interest rates
	- Jumps
- The ever increasing gains in the computer speed make MCS methodology increasingly attractive.