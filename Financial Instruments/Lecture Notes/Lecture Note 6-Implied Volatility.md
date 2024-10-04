---
title: LECTURE NOTE 7-EXOTIC OPTIONS AND DERIVATIVE PRICING BY MONTE CARLO SIMULATION
aliases: [LECTURE NOTE 7-EXOTIC OPTIONS AND DERIVATIVE PRICING BY MONTE CARLO SIMULATION]
linter-yaml-title-alias: LECTURE NOTE 7-EXOTIC OPTIONS AND DERIVATIVE PRICING BY MONTE CARLO SIMULATION
---

# LECTURE NOTE 7-EXOTIC OPTIONS AND DERIVATIVE PRICING BY MONTE CARLO SIMULATION
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
- Consider again a one-step tree (to begin with). - Assume$S_0$= 100; K = 100,  T = 1,  r = 2%,  σ = 30%.
- Given that u = eσ
Given that$u=e^{\sigma\sqrt{T}}=1.34986$,  the price of _any_ derivative security with payoff$V(S_{1})$can be computed as
$$V_{0}=E^{*}\left[e^{-rT}V(S_{1})\right]=e^{-rT}\left[q^{*}V(S_{1, u})+(1-q^{*})V(S_{1, d})\right]$$
- For instance,  a call option has price given by
```latex
\usetikzlibrary{positioning}
\begin{document}
\begin{tikzpicture}
  % Define the nodes
  \node (i0) {$i = 0$};
  \node[below=1cm of i0, draw, inner sep=5pt] (box0) {
    \begin{tabular}{l}
      $S_0 = 100.000$ 
      $q_0^* = 0.4587$ 
      $c_0 = e^{-rT} \times q_0^* \times c_{1, u} = 15.731$
    \end{tabular}
  };
  
  % Nodes for i = 1
  \node[right=3cm of i0] (i1) {$i = 1$};
  \node[draw, above right=0.5cm and 1cm of i1, inner sep=5pt] (box1u) {
    \begin{tabular}{l}
      $S_{1, u} = 134.986$ 
      $c_{1, u} = 34.986$
    \end{tabular}
  };
  \node[draw, below right=0.5cm and 1cm of i1, inner sep=5pt] (box1d) {
    \begin{tabular}{l}
      $S_{1, d} = 74.082$ 
      $c_{1, d} = 0$
    \end{tabular}
  };
\end{tikzpicture}
\end{document}
```
$i=0$$i=1$$S_{1, u}=134.986$$c_{1, u}=34.986$$S_{0}=100.000$$q_{0}^{*}=0.4587$$c_{0}=e^{-rT}\times q_{0}^{*}\times c_{1, u}=15.731$$S_{1, d}=74.082$$c_{1, d}=0$
- An alternative way of computing the expected future payoff is to _simulate_ up and down movements using a computer.
- For instance,  in Excel the function _RAND_() simulates a uniform between [0,  1].
- Thus,  RAND() _> q_∗ occurs with probability (1 − q∗),  and vice-versa (e.g q∗ = 1 implies
that (1 − q∗) = 0,  and indeed _RAND_() can never be above q∗).
- We can simulate _RAND_() many times,  say N:
- Whenever the realization RAND() _> q_∗ we say that we went _down_ the tree;
- Whenever RAND() _< q_∗,  we say we went up the tree.
- Compute the value of the stock price at time T = 1,  S1, u or S1, d for each simulation
- Let Si
1 denote the realization of S1 in simulation run i.
- Compute the payoff of the security at time T = 1 for each simulation run,  e.g. V (Si
1. =
max(Si
1 − K,  0)
- The value of the security is the average of the realizations
$$\tilde{V}_{0}=\mathrm{average~of~}\{e^{-r T}V(S_{1}^{1}), e^{-r T}V(S_{1}^{2}), e^{-r T}V(S_{1}^{3}), …, e^{-r T}V(S_{1}^{N})\}=\frac{1}{N}\sum\limits_{i=1}^{N}e^{-r T}V(S_{1}^{i})$$
- For instance,  given q∗ = 0.4587,  we obtain the following table

|           |        |   RAND() Move on Tree Price at T |   Payoff |   discounted |
|-----------|--------|----------------------------------|----------|--------------|
| 0.457335  | up     |                          134.986 |   34.986 |       34.293 |
| 0.393937  | up     |                          134.986 |   34.986 |       34.293 |
| 0.090053  | up     |                          134.986 |   34.986 |       34.293 |
| 0.878148  | down   |                           74.082 |    0     |        0     |
| 0.658659  | down   |                           74.082 |    0     |        0     |
| 0.759579  | down   |                           74.082 |    0     |        0     |
| 0.798027  | down   |                           74.082 |    0     |        0     |
| 0.061689  | up     |                          134.986 |   34.986 |       34.293 |
| 0.969222  | down   |                           74.082 |    0     |        0     |
| 0.39267   | up     |                          134.986 |   34.986 |       34.293 |
| Average   | 17.147 |                                  |          |              |
| st. error | 5.715  |                                  |          |              |
- With only N = 10 simulation,  it is no surprise that the value of the security �V0 = 17.147 comes
rather different from the value from the tree (V0 = 15.731).
- As N increases,  the value gets more and more precise.
- How many simulations?
- The number of simulations$N$should be large enough to obtain a reasonable "standard error",  that is,  standard deviation of our estimate itself.
- This is computed as the standard deviation of our discounted payoff,  divided by$\sqrt{N}$:$$\text{Standard error}=\frac{\text{Standard Deviation of}\{e^{-rT}V(S_{1}^{1}), e^{-rT}V(S_{1}^{2}), e^{-rT}V(S_{1}^{3}), …, e^{-rT}V(S_{1}^{N})\}}{\sqrt{N}}.$$
- In the previous example,  the standard error was _s.e._ = 5.715
- This implies that with 95% probability,  the true value of the security is between
$$\text{ConfidenceInterval}=[\hat{V}_0-2\times s.e., \hat{V}_0+2\times s.e.]=[5.715, 28.577]$$
- Given the number of simulations,  we give 95% probability that the true value is between 5.715 and 28.577,  a rather large interval.
- Increasing the number of simulations to N = 1000,  we obtain �V0 = 15.725 with _s.e._ = 0.54.
- The confidence interval is [14.644,  16.806],  much tighter than beofre.
- The same logic applies to multi step trees. - Consider a two step tree,  with the same parameters
$i=0$$i=1$$i=2$$S_{2, uu}=152.847$$S_{1, u}=123.631$$S_{0}=100$$S_{1, d}=80.886$$S_{2, dd}=65.425$
- Again,  the value of any derivative security with payoff V (S2) is given by
$$V(S)=E^{*}[e^{-r T}V(S_{2})]$$
- For instance,  with N = 10 simulations,  we may obtain something as follows:

|           |       |          |      |   RAND() Move on Tree RAND() Move on Tree Price at T |   Payoff |   discounted |
|-----------|-------|----------|------|------------------------------------------------------|----------|--------------|
| 0.535163  | down  | 0.621716 | down |                                               65.425 |    0     |          0   |
| 0.501443  | down  | 0.542492 | down |                                               65.425 |    0     |          0   |
| 0.079387  | up    | 0.021237 | up   |                                              152.847 |   52.847 |         51.8 |
| 0.194357  | up    | 0.964902 | down |                                              100     |    0     |          0   |
| 0.329731  | up    | 0.487593 | down |                                              100     |    0     |          0   |
| 0.581736  | down  | 0.841805 | down |                                               65.425 |    0     |          0   |
| 0.450822  | up    | 0.30804  | up   |                                              152.847 |   52.847 |         51.8 |
| 0.017819  | up    | 0.978316 | down |                                              100     |    0     |          0   |
| 0.110075  | up    | 0.636362 | down |                                              100     |    0     |          0   |
| 0.452457  | up    | 0.84503  | down |                                              100     |    0     |          0   |
| Average   | 10.36 |          |      |                                                      |          |              |
| st. error | 6.90  |          |      |                                                      |          |              |
- With N = 1000 simuations,  the price is �V0 = 10.453 with _s.e._ = 0.657.
- The value from the risk neutral tree is instead 11.476
- A 10-step tree is as follows:

| Stock Assumption   | Option Assumption   | Tree        | Risk Neutral Prob   |
|--------------------|---------------------|-------------|---------------------|
| mu                 |                     |             |                     |
| 0.1                | T                   | 1           | n                   |
| sigma              | 0.3                 | K           | 100                 |
| r                  | 0.02                | Call or Put | 1 (=1 for call      |
| q                  | 0                   | d           | 0.909493            |
|$S_0$| 100                 | p           | 0.52919             |
| time ==>           | 0                   | 0.1         | 0.2                 |
| i==>               | 0                   | 1           | 2                   |
| 0                  | 100.000             | 109.951     | 120.893             |
| 1                  | 90.949              | 100.000     | 109.951             |
| 2                  | 82.718              | 90.949      | 100.000             |
| 3                  | 75.231              | 82.718      | 90.949              |
| 4                  | 68.422              | 75.231      | 82.718              |
| 5                  | 62.229              | 68.422      | 75.231              |
| 6                  | 56.597              | 62.229      | 68.422              |
| 7                  | 51.475              | 56.597      | 62.229              |
| 8                  | 46.816              | 51.475      | 56.597              |
| 9                  | 42.579              | 46.816      |                     |
| 10                 | 38.725              |             |                     |
| time ==>           | 0.000               | 0.100       | 0.200               |
| i==>               | 0.0                 | 1.0         | 2.0                 |
| 0                  | 12.530              | 18.247      | 25.881              |
| 1                  | 7.156               | 11.075      | 16.699              |
| 2                  | 3.465               | 5.782       | 9.429               |
| 3                  | 1.280               | 2.345       | 4.231               |
| 4                  | 0.275               | 0.566       | 1.164               |
| 5                  | 0.000               | 0.000       | 0.000               |
| 6                  | 0.000               | 0.000       | 0.000               |
| 7                  | 0.000               | 0.000       | 0.000               |
| 8                  | 0.000               | 0.000       | 0.000               |
| 9                  | 0.000               | 0.000       |                     |
| 10                 | 0.000               |             |                     |
| 11                 |                     |             |                     |
- 10 simulated paths are given by (the price in the table refers to N = 1000 though.)
## OPTION PRICES BY SIMULATIONS (ON THE TREE)
|                                          |                 |                  |   Simulated Simulated | Call Price Binomial Tree    |   12.530 |
|------------------------------------------|-----------------|------------------|-----------------------|-----------------------------|----------|
| Put Price                                | Call Price      | Maturity (years) |                   1   | Call Price Black and Schole |   12.822 |
| 11.030                                   | 12.637 Price    |                  |                       |                             |          |
| Maturity (steps)                         | 10.000          |                  |                       |                             |          |
| 0.480                                    | 0.675 St. Error |                  |                       |                             |          |
| Time                                     |                 |                  |                       |                             |          |
| SIMULATION OF RISK NEUTRAL PRICE PROCESS |                 |                  |                       |                             |          |
| DiscountedDiscounted                     | 0.000           | 0.100            |                   0.2 | 0.300                       |    0.4   |
| Put Payoff Call Payoff Simulation        | 0.000           | 1.000            |                   2   | 3.000                       |    4     |
| 0.000                                    | 45.238          | 1.000            |                 100   | 90.949                      |   82.718 |
| 0.000                                    | 20.479          | 2.000            |                 100   | 109.951                     |  120.893 |
| 16.940                                   | 0.000           | 3.000            |                 100   | 90.949                      |   82.718 |
| 0.000                                    | 0.000           | 4.000            |                 100   | 109.951                     |  100     |
| 16.940                                   | 0.000           | 5.000            |                 100   | 109.951                     |  120.893 |
| 0.000                                    | 0.000           | 6.000            |                 100   | 90.949                      |   82.718 |
| 16.940                                   | 0.000           | 7.000            |                 100   | 90.949                      |   82.718 |
| 0.000                                    | 0.000           | 8.000            |                 100   | 90.949                      |  100     |
| 16.940                                   | 0.000           | 9.000            |                 100   | 90.949                      |   82.718 |
| 0.000                                    | 0.000           | 10.000           |                 100   | 90.949                      |  100     |
- The simulation paths are (they look like a tree,  with missing branches).
## WHY MONTE CARLO SIMULATIONS?
- Why do we need Monte Carlo Simulations on the tree,  when we have the tree itself?
- Monte Carlo Simulations may be useful to price derivative securities with path dependent
payoff.
∗ That is,  the value at maturity depends on the _path_ taken by the stock during the life of
the security.
- For instance,  Asian options have payoff given by
Asian Call Option = max ({Average of St from 0 to T} − K,  0)
Asian Put Option = max (K *− {*Average of St from 0 to T},  0)
- These options are very hard to price on a tree without simulations. - Consider a two step tree.
i = 0
i = 1
i = 2
(_r.n.prob_)
S2, uu = 152.847 S2, uu = 125.4925 =⇒ c2, uu = 25.4925 (Q∗ 2, uu = 22.15%) S1, u = 123.631 S2, ud = 100 S2, ud = 107.877 =⇒ c2, ud = 7.877 (Q∗ 2, ud = 24.91%)$S_0$= 100 S2, du = 100 S2, ud = 93.628 =⇒ c2, du = 0 (Q∗ 2, du = 24.91%) S1, d = 80.886 S2, dd = 65.425 S2, ud = 82.1036 =⇒ c2, dd = 0 (Q∗ 2, dd = 28.01%)
- Even if S2, ud = S2, du = 100,  the payoff when the final price is 100 depends on the path of S,
namely,  whether S1 = S1, u = 123.631 or S1 = S1, d = 80.886.
- In this case,  we can compute the value of the security on the tree V0 =
�4
j=1 Q∗
jV2, j = 7.45
- 1000 Monte Carlo simuations yield �V0 = 7.560 with _s.e._ = 0.316
## WHY MONTE CARLO SIMULATIONS?
- When we move to multi-period trees,  path dependent options become much difficult to price
without Monte Carlo Simulations.
- The following picture shows the averages St over 10 paths.
- While the original paths look like the recombining tree we started out with,  the averages
look like paths on a non-recombining tree.
- Non recombining trees are much harder to evaluate numerically for a large number of time
steps
## WHY MONTE CARLO SIMULATIONS? WHY MONTE CARLO SIMULATIONS?
- The number of path dependent options is very large. - Besides the asian option discussed,  some other popular examples are:
## - BARRIER OPTIONS
∗ The option expires if stock hits an upper (up and out) or a lower (down and out) barrier
∗ The option comes into existence if the stock hits and upper (up and in) or a lower (down
and in) barrier
- Lookback Options: The final payoff depends on the maximum or minimum value achieved
by the stock before maturity. For instance:
$$g_{T}=(\operatorname*{max}(S_{0}, …, S_{T})-S_{T})$$
- Asian Strike Options: The strike price is equal to the average stock price. E.g.
$$g_{T}=\operatorname*{max}(S_{T}-A v e r a g e(S_{0}, …, S_{T}))$$
## MONTE CARLO SIMULATIONS WITHOUT TREES
- There is no reason to limit MC simulations to trees.
- The main motivation behind pricing by MC simulations is risk neutral pricing.
∗ That is,  dynamic replication can be achieved.
- These no arbitrage conditions are naturally satisfied on trees,  as we have seen.
- However,  once we decide we can use risk neutral pricing,  we can simulate out of any distribution.
- In particular,  we can use the lognormal model,  as in Black and Scholes - Risk neutral pricing implies that over a small period
$$E^{*}\left(\frac{S_{t+h}}{S_{t}}\right)=e^{r h}$$
## MONTE CARLO SIMULATIONS UNDER LOG NORMALITY
$\bullet$One way to simulate is then to use the following algorithm
$$S_{t+h}=S_{t}\times e^{(r-\frac{\sigma^{2}}{2})h+\sigma\sqrt{h}\epsilon_{t}}$$
- where
ϵt ∼ N(0,  1)
- The rules of the log-normal distribution imply$$E^{*}\left(\frac{S_{t+h}}{S_{t}}\right)=e^{(r-\frac{\sigma^{2}}{2})h+\left\{E^{*}[\sigma\sqrt{h}\times\epsilon_{t}]+1/2Var[\sigma\sqrt{h}\times\epsilon_{t}]\right\}}=e^{rh}$$
- Moreover,  σ2 converges to the (annualized) variance of log returns _V ar_[log(St+h/St)]
## MONTE CARLO SIMULATIONS UNDER LOG NORMALITY
- For instance,  a few 10-period paths are plotted in the next figure
## MONTE CARLO SIMULATIONS UNDER LOG NORMALITY
- MC price of put and calls under Black and Scholes assumptions (1000 simulations)
Option Prices By Simulations (Log-Normal Distribution)
Stock Assumption
Option Assumption
mu
0.1
T
1
sigma
0.3
K
100
Simulated Simulated
r
0.02
Black Scholes Call
12.822 d1
0.216667
Put Price
Call Price
q
0
n
252 (<252)
Black Scholes Put
10.841
10.163
13.359 Price
$S_0$
100
h
0.003968
0.431
0.682 St. Error
Maturity (steps)
252.000
Time
SIMULATION OF RISK NEUTRAL PRICE PROCESS
DiscountedDiscounted
0.000
0.004
0.008
0.012
0.016
0.020
0.024
0.028
0.032
0.036
0.040
Put Payoff Call Payoff Simulation
0.000
1.000
2.000
3.000
4.000
5.000
6.000
7.000
8.000
9.000
10.000
0.000
31.151
1.000
100.000
97.613
98.064
100.457
102.757
106.178
101.884
101.433
103.553
101.447
100.132
0.000
19.822
2.000
100.000
100.405
99.739
101.503
100.558
105.110
106.598
107.834
105.852
107.609
110.592
0.000
39.492
3.000
100.000
102.859
102.330
99.617
98.805
99.322
98.000
99.091
98.651
99.639
96.081
24.924
0.000
4.000
100.000
99.685
96.690
95.207
94.187
92.794
90.516
90.312
92.204
91.063
90.879
45.921
0.000
5.000
100.000
101.070
100.563
99.672
104.184
101.702
101.876
96.681
96.982
97.708
98.033
7.946
0.000
6.000
100.000
99.763
98.818
98.931
96.804
95.383
96.966
95.921
93.207
94.368
92.951
27.690
0.000
7.000
100.000
99.271
103.740
104.955
101.755
101.093
100.605
100.517
102.338
99.242
102.166
0.000
24.657
8.000
100.000
100.857
100.063
99.801
103.115
99.530
97.481
99.713
101.662
102.279
104.883
0.000
23.407
9.000
100.000
102.632
102.350
99.951
98.363
99.582
102.310
102.637
103.626
105.255
105.642
40.778
0.000
10.000
100.000
95.962
92.762
91.641
91.992
92.294
92.229
91.780
90.591
91.673
90.779
## MONTE CARLO SIMULATIONS WITH MANY "FACTORS"
- The Monte Carlo Simulation method to price options can be extended to price derivative securities that depend on multiple factors. For instance:
- time varying interest rates - time varying volatility
- payoffs on the relative value of different stocks,  exchange rates etc.
- The methodology is the same
1. Simulate _risk neutral_ factors
1. Compute the cash flows of the security 3. Compute the present value,  discounting at the risk free rate 4. Average all of the simulated paths.
- One difficulty is with obtaining risk neutral dynamics for factors:
- Traded factors are simple: the expected return on such factor must be the risk free rate. - It is harder for non-traded factors (e.g. interest rates,  volatility). We attack this problem
later on.
## MONTE CARLO SIMULATIONS WITH MANY "FACTORS"
- Consider an option that pays the maximum between the stock return on IBM and Apple within
a prespecified period.
- That is,  if$S_{0}$and$N_{0}$are the current prices of the two stocks,  the payoff at maturity of the option is$$\text{Payoff at}T=\max\left(\frac{S_{T}}{S_{0}}, \frac{N_{T}}{N_{0}}\right)$$
- How much would pay for this security?
- We can use Monte Carlo Simulations to find out.
- The risk neutral processes of St and Nt are the same as before,  so we simulate
$$\begin{array}{l l l}{{S_{t+h}}}&{{=}}&{{S_{t}\times e^{(r-\frac{\sigma_{S}^{2}}{2})h+\sigma_{S}\sqrt{h\epsilon_{1, t}}}}}\\ {{}}&{{}}&{{}}\\ {{N_{t+h}}}&{{=}}&{{N_{t}\times e^{(r-\frac{\sigma_{N}^{2}}{2})h+\sigma_{N}\sqrt{h\epsilon_{2, t}}}}}\end{array}$$
- If IBM and Apple are correlated stocks (as they are),  we need a methodology to simulate
correlated shocks ϵ1, t, ϵ2, t.
- Let$\hat{e}_{t}$be a standard normal,  uncorrelated with$\epsilon_{1, t}$. Then,  define$$\epsilon_{2, t}=\rho\epsilon_{1, t}+\sqrt{1-\rho^{2}}\hat{e}_{t}$$
- **Claim**:$\epsilon_{2, t}$has zero mean,  variance 1,  and correlation$\rho$with$\epsilon_{1, t}$(check!)
## MONTE CARLO SIMULATIONS WITH MANY "FACTORS"
$\bullet$For each simulation run$i$,  compute the discounted payoff
$$V^{i}=e^{-rT}\max\left(\frac{S_{T}^{i}}{S_{0}}, \frac{N_{T}^{i}}{N_{0}}\right)$$
- The price of the security is then
$$\widehat{V}_{0}=\frac{1}{n}\sum_{i=1}^{n}V^{i}$$
- Assuming σS = σN =,  r = and ρ =,  the value of this option is �V0 = 1.134.
- As a second example,  consider an option with the payoff$$\text{Payoff at}T=\max\left(\frac{S_{T}}{S_{0}}-\frac{N_{T}}{N_{0}}\right)$$
- That is,  it pays only when the first stock (say IBM) does better than the second (say Apple).
- The same simulations show that the fair value of this option is �V0 = 0.1
- Note that the difference between one option and another is simply the final payoff. The methodology is identical.
## OPTION PRICES BY SIMULATIONS (LOG-NORMAL DISTRIBUTION)
Stock S Assumption Option Assumption
mu
0.1
T
1
sigma
0.3
K
100
Payoff =
Payfoff =
r
0.02
max(ST/S0 - NT/N0, 0)
max(ST/S0, NT/N0)
q
0
n
252 (<252)
0.100
1.134
Price
$S_0$
100
h
0.003968
0.008
0.018
St. Error
Time
SIMULATION OF RISK NEUTRAL PRICE PROCESS
Discounted
Discounted
0.000
0.004
0.008
0.012
0.016
0.020
0.024
Put Payoff
Call Payoff
Simulation
0.000
1.000
2.000
3.000
4.000
5.000
6.000
0.000
1.215
1.000
100.000
100.302
98.673
100.314
100.721
100.624
99.894
0.000
0.961
2.000
100.000
100.580
101.532
103.190
101.181
101.547
103.710
0.000
1.239
3.000
100.000
102.966
101.310
102.796
103.523
104.315
106.980
0.197
1.010
4.000
100.000
100.704
101.976
103.820
105.250
107.532
110.269
0.307
0.891
5.000
100.000
100.525
97.271
95.557
93.942
93.288
93.062
0.040
0.930
6.000
100.000
102.864
106.022
103.541
101.559
101.838
103.471
0.079
0.675
7.000
100.000
97.681
97.768
96.612
92.258
92.593
93.897
0.000
1.236
8.000
100.000
100.442
98.513
94.624
94.781
97.290
98.014
0.008
1.665
9.000
100.000
98.807
97.080
97.667
99.475
100.306
102.362
0.475
1.281
10.000
100.000
96.897
98.374
97.406
97.495
96.087
96.882
## SIMULATION SECOND STOCK
Stock N Assumption
mu
0.1
sigma
0.3
rho
0.700
q
0
$S_0$
100
Time
SIMULATION OF RISK NEUTRAL PRICE PROCESS
0.000
0.004
0.008
0.012
0.016
0.020
0.024
Simulation
0.000
1.000
2.000
3.000
4.000
5.000
6.000
1.000
100.000
98.498
97.697
100.548
102.477
104.831
101.270
2.000
100.000
100.697
100.882
103.319
101.228
104.745
107.374
3.000
100.000
104.143
102.590
101.671
101.579
102.504
103.337
4.000
100.000
100.266
98.972
99.121
99.309
99.744
99.729
5.000
100.000
101.133
98.477
96.643
98.565
96.410
96.365
6.000
100.000
101.824
103.298
101.684
98.772
97.923
100.191
7.000
100.000
97.859
101.048
101.048
95.698
95.496
96.103
8.000
100.000
100.923
99.002
96.070
98.452
97.768
96.828
9.000
100.000
101.021
99.586
98.328
98.466
99.917
103.322
10.000
100.000
94.981
93.695
92.245
92.556
91.834
92.319
## HOW CAN WE COMPUTE "∆" WITH MONTE CARLO SIMULATIONS?
- Once we have computed the value of the security,  we may want to know what is its sensitivity
to changes in the stock.
- Computing the "$\Delta$" is not hard,  and we use Monte Carlo simulations again.$$\Delta=\frac{d\ V(S)}{d\ S}\approx\frac{V(S+h)-V(S)}{h}$$
- Thus,  compute V (S) and V (S + h) using MC simulations1
- Apply the above formula. - For instance,  we obtained earlier the price of a call equal to c(100) = 13.359. - Using S = 101 we obtain c(101) = 13.979. =⇒ ∆ = (13.979 − 13.359)/1 = 0.62.
- Black and Scholes Delta is ∆ = N(d1) = 0.58. As N increases,  the simulated ∆ converges
to the true one.
## CONCLUSION
- The Monte Carlo Simulations Method is one of the main tools used by practitioners to price
complex securities under fairly general assumption about the underlying stochastic processes
- Just three steps:
1. Simulate many paths of underlying stochastic variables under the _risk neutral_ probabilities
1. For each path,  compute the discounted simulated payoff of the security
1. Compute the average
- MCS are especially useful to value _path dependent_ securities,  or securities that depend on the
value of multiple underlying variables
- Barrier options,  Asian options,  Lookback options - Options on maximum,  options on relative returns across securities
- MCS are also very useful to value securities under general processes for underlying stochastic
variable,  such as
- Stochastic volatility - Stochastic interest rates
- Jumps
- The ever increasing gains in the computer speed make MCS methodology increasingly attractive.