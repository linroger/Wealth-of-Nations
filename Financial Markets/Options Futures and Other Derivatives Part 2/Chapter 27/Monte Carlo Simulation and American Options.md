---
tags:
  - '#american_options'
  - '#equivalent_martingale_measure'
  - '#exercise_boundary'
  - '#least_squares_approach'
  - '#market_price_of_risk'
  - '#martingales'
  - '#monte_carlo_simulation'
  - '#path_dependent_options'
  - '#risk_neutral_valuation'
  - '#stochastic_interest_rates'
---
# 27.8 MONTE CARLO SIMULATION AND AMERICAN OPTIONS  

Monte Carlo simulation is well suited to valuing path-dependent options and options where there are many stochastic variables. Trees and finite difference methods are well suited to valuing American-style options. What happens if an option is both path dependent and American? What happens if an American option depends on several stochastic variables? Section 27.5 explained a way in which the binomial tree approach can be modified to value path-dependent options in some situations. A number of researchers have adopted a different approach by searching for a way in which Monte Carlo simulation can be used to value American-style options.29 This section explains two alternative ways of proceeding.  

Table 27.2 Combination of binomials assuming no correlation.   


<html><body><table><tr><td rowspan="2">S2-move</td><td colspan="2">S-move</td></tr><tr><td>Down</td><td>Up</td></tr><tr><td>Up</td><td>0.25</td><td>0.25</td></tr><tr><td>Down</td><td>0.25</td><td>0.25</td></tr></table></body></html>  

Table 27.3 Combination of binomials assuming correlation of $\rho$ $S_{2}$ move $S_{1}$ move   


<html><body><table><tr><td rowspan="2">p2-ntove</td><td colspan="2"></td></tr><tr><td>Down</td><td>Up</td></tr><tr><td>Up</td><td>0.25(1 - p)</td><td>0.25(1 + p)</td></tr><tr><td>Down</td><td>0.25(1 + p)</td><td>0.25(1 - p)</td></tr></table></body></html>  

# The Least-Squares Approach  

In order to value an American-style option it is necessary to choose between exercising and continuing at each early exercise point. The value of exercising is normally easy to determine. A number of researchers including Longstaff and Schwartz provide a way of determining the value of continuing when Monte Carlo simulation is used.30 Their. approach involves using a least-squares analysis to determine the best-fit relationship. between the value of continuing and the values of relevant variables at each time an early exercise decision has to be made. The approach is best illustrated with a numerical example. We use the one in the Longstaff-Schwartz paper..  

Table 27.4 Sample paths for put option example.   


<html><body><table><tr><td>Path</td><td>t=0</td><td>t=1</td><td>t=2</td><td>t=3</td></tr><tr><td>1</td><td>1.00</td><td>1.09</td><td>1.08</td><td>1.34</td></tr><tr><td>2</td><td>1.00</td><td>1.16</td><td>1.26</td><td>1.54</td></tr><tr><td>3</td><td>1.00</td><td>1.22</td><td>1.07</td><td>1.03</td></tr><tr><td>4</td><td>1.00</td><td>0.93</td><td>0.97</td><td>0.92</td></tr><tr><td>5</td><td>1.00</td><td>1.11</td><td>1.56</td><td>1.52</td></tr><tr><td>6</td><td>1.00</td><td>0.76</td><td>0.77</td><td>0.90</td></tr><tr><td>7</td><td>1.00</td><td>0.92</td><td>0.84</td><td>1.01</td></tr><tr><td>8</td><td>1.00</td><td>0.88</td><td>1.22</td><td>1.34</td></tr></table></body></html>  

Table 27.5 Cash flows if exercise only possible at 3-year point.   


<html><body><table><tr><td>Path</td><td>t=1 t=2</td><td>t=3</td></tr><tr><td>1</td><td>0.00</td><td>0.00 0.00</td></tr><tr><td>2</td><td>0.00</td><td>0.00 0.00</td></tr><tr><td>3</td><td>0.00 0.00</td><td>0.07</td></tr><tr><td>4</td><td>0.00</td><td>0.00 0.18</td></tr><tr><td>5</td><td>0.00</td><td>0.00 0.00</td></tr><tr><td>6</td><td>0.00</td><td>0.00 0.20</td></tr><tr><td>7</td><td>0.00 0.00</td><td>0.09</td></tr><tr><td>8</td><td>0.00</td><td>0.00</td></tr></table></body></html>  

Consider a 3-year American put option on a non-dividend-paying stock that can be exercised at the end of year 1, the end of year 2, and the end of year 3. The risk-free rate is $6\%$ per annum (continuously compounded). The current stock price is 1.00 and the strike price is 1.10. Assume that the eight paths shown in Table 27.4 are sampled for the stock price. (This example is for illustration only; in practice many more paths would be sampled.) If the option can be exercised only at the 3-year point, it provides a cash flow equal to its intrinsic value at that point. This is shown in the last column of Table 27.5.  

If the put option is in the money at the 2-year point, the option holder must decide. whether to exercise. Table 27.4 shows that the option is in the money at the 2-year point. for paths 1, 3, 4, 6, and 7. For these paths, we assume an approximate relationship:  

$$
V=a+b S+c S^{2}
$$  

where $S$ is the stock price at the 2-year point and $V$ is the value of continuing, discounted back to the 2-year point. Our five observations on $S$ are: 1.08, 1.07, 0.97, 0.77, and 0.84. From Table 27.5 the corresponding values for $V$ are: $0.00,0.07e^{-0.06\times1}$ $0.18e^{-0.06\times1}$ $0.20e^{-0.06\times1}$ , and $0.09e^{-0.06\times1}$ The values of $a,b$ , and $c$ that minimize  

$$
\sum_{i=1}^{5}(V_{i}-a-b S_{i}-c S_{i}^{2})^{2}
$$  

where $S_{i}$ and $V_{i}$ are the ith observation on $S$ and $V$ , respectively, are $a=-1.070$ $b=2.983$ and $c=-1.813$ , so that the best-fit relationship is  

$$
V=-1.070+2.983S-1.813S^{2}
$$  

This gives the value at the 2-year point of continuing for paths 1, 3, 4, 6, and 7 of 0.0369, 0.0461, 0.1176, 0.1520, and 0.1565, respectively. From Table 27.4 the value of exercising is 0.02, 0.03, 0.13, 0.33, and 0.26. This means that we should exercise at the 2-year point for paths 4, 6, and 7. Table 27.6 summarizes the cash flows assuming exercise at either the 2-year point or the 3-year point for the eight paths.  

Table 27.6 Cash flows if exercise only possible at 2- and 3-year point.   


<html><body><table><tr><td>Path</td><td>t=1</td><td>t=2</td><td>t=3</td></tr><tr><td>1</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>2</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>3</td><td>0.00</td><td>0.00</td><td>0.07</td></tr><tr><td>4</td><td>0.00</td><td>0.13</td><td>0.00</td></tr><tr><td>5</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>6</td><td>0.00</td><td>0.33</td><td>0.00</td></tr><tr><td>7</td><td>0.00</td><td>0.26</td><td>0.00</td></tr><tr><td>8</td><td>0.00</td><td>0.00</td><td>0.00</td></tr></table></body></html>  

Consider next the paths that are in the money at the 1-year point. These are paths 1, 4, 6, 7, and 8. From Table 27.4 the values of $S$ for the paths are 1.09, 0.93, 0.76, 0.92, and 0.88, respectively. From Table 27.6, the corresponding continuation values discounted back to $t=1$ are 0.00, $0.13e^{-0.06\times1}$ $0.33e^{\frac{\lambda}{-}0.06\times1}$ $\bar{0}.26e^{-0.06\times1}$ , and 0.00, respectively. The least-squares relationship is  

$$
V=2.038-3.335S+1.356S^{2}
$$  

This gives the value of continuing at the 1-year point for paths 1, 4, 6, 7, 8 as 0.0139,. 0.1092, 0.2866, 0.1175, and 0.1533, respectively. From Table 27.4 the value of exercising. is 0.01, 0.17, 0.34, 0.18, and 0.22, respectively. This means that we should exercise at the 1-year point for paths 4, 6, 7, and 8. Table 27.7 summarizes the cash flows assuming. that early exercise is possible at all three times. The value of the option is determined by discounting each cash flow back to time zero at the risk-free rate and calculating the mean of the results. It is.  

$$
\begin{array}{r}{\frac{1}{8}(0.07e^{-0.06\times3}+0.17e^{-0.06\times1}+0.34e^{-0.06\times1}+0.18e^{-0.06\times1}+0.22e^{-0.06\times1})=0.1144}\end{array}
$$  

Since this is greater than 0.10, it is not optimal to exercise the option immediately.  

Table 27.7 Cash flows from option.   


<html><body><table><tr><td>Path</td><td>t=1</td><td>t=2</td><td>t=3</td></tr><tr><td>1</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>2</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>3</td><td>0.00</td><td>0.00</td><td>0.07</td></tr><tr><td>4</td><td>0.17</td><td>0.00</td><td>0.00</td></tr><tr><td>5</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>6</td><td>0.34</td><td>0.00</td><td>0.00</td></tr><tr><td>7</td><td>0.18</td><td>0.00</td><td>0.00</td></tr><tr><td>8</td><td>0.22</td><td>0.00</td><td>0.00</td></tr></table></body></html>  

This method can be extended in a number of ways. If the option can be exercised at. any time we can approximate its value by considering a large number of exercise points (just as a binomial tree does). The relationship between $V$ and $S$ can be assumed to be more complicated. For example we could assume that $V$ is a cubic rather than a quadratic function of S. The method can be used where the early exercise decision. depends on several state variables. A functional form for the relationship between. $V$ and the variables is assumed and the parameters are estimated using the least-squares. approach, as in the example just considered.  

# The Exercise Boundary Parameterization Approach  

A number of researchers, such as Andersen, have proposed an alternative approach. where the early exercise boundary is parameterized and the optimal values of the. parameters are determined iteratively by starting at the end of the life of the option. and working backward.31 To illustrate the approach, we continue with the put option. example and assume that the eight paths shown in Table 27.4 have been sampled. In. this case, the early exercise boundary at time t can be parameterized by a critical value of $S,S^{*}(t)$ . If the asset price at time $t$ is below $\boldsymbol{S}^{*}(t)$ we exercise at time $t;$ if it is above $S^{*}(t)$ we do not exercise at time $t.$ The value of $\boldsymbol{S}^{*}(3)$ is 1.10. If the stock price is above. 1.10 when $t=3$ (the end of the option's life) we do not exercise; if it is below 1.10 we exercise. We now consider the determination of. $S^{*}(2)$  

Suppose that we choose a value of. $\boldsymbol{S}^{*}(2)$ less than 0.77. The option is not exercised at. the 2-year point for any of the paths. The value of the option at the 2-year point for the eight paths is then 0.00, 0.00, $\mathrm{0.07}e^{-0.06\times1}$ $0.18e^{-0.06\times1}$ , 0.00, $0.20e^{-0.\dot{0}6\times1}$ $\mathrm{\hat{\Pi}}_{0.09e}\mathrm{-}0.06\mathrm{\times}1$ and 0.00, respectively. The average of these is 0.0636. Suppose next that $S^{*}(2)=0.77$ The value of the option at the 2-year point for the eight paths is then O.00, 0.00, $0.07e^{-0.06\times1}$ $0.18e^{-0.66\times1}$ $0.00,0.33,\overset{\cdot}{0}.09e^{-0.06\times1}$ and 0.00, respectively. The average of these is 0.0813. Similarly when. $\boldsymbol{S}^{*}(2)$ equals 0.84, 0.97, 1.07, and 1.08, the average value of the option at the 2-year point is. $0.1032,0.0982,0.0938.$ and 0.0963, respectively. This analysis shows that the optimal value of $S^{*}(2)$ (i.e., the one that maximizes the. average value of the option) is 0.84. (More precisely, it is optimal to choose $0.84\bar{\le}{\cal S}^{*}(2)<0.97.)$ When we choose this optimal value for $S^{*}(2)$ , the value of the option at the 2-year point for the eight paths is $0.00,0.00,0.0659,0.1695,0.00,0.33,0.26$ and 0.00, respectively. The average value is 0.1032.  

We now move on to calculate. $\boldsymbol{S}^{*}(1)$ . If $S^{*}(1)<0.76$ the option is not exercised at the. 1-year point for any of the paths and the value at the option at the 1-year point is $0.{\dot{1}}032e^{-0.06\times1}=0.{\dot{0}}972$ If $\bar{S}^{*}(1)=0.76$ , the value of the option for each of the eight paths at the 1-year point is o.0o, o.0o, $0.0659e^{-0.06\times1}$ $0.1695e^{-0.06\times1}$ , 0.0, 0.34, $\phantom{+}0.26e^{-0.06\times1}$ , and 0.00, respectively. The average value of the option is 0.1008. Similarly when $\boldsymbol{S}^{*}(1)$ equals 0.88, 0.92, 0.93, and 1.09 the average value of the option is 0.1283, 0.1202, 0.1215, and 0.1228, respectively. The analysis therefore shows that the optimal value of $\boldsymbol{S}^{*}(1)$ is 0.88. (More precisely, it is optimal to choose $0.88\leq S^{*}(1)<0.9\bar{2}.)$ The value of the option at time zero with no early exercise is $0.1283e^{-0.06\times1}=0.1208.$ This is greater than the value of 0.10 obtained by exercising at time zero.  

In practice, tens of thousands of simulations are carried out to determine the early. exercise boundary in the way we have described. Once the early exercise boundary has  

been obtained, the paths for the variables are discarded and a new Monte Carlo.   
simulation using the early exercise boundary is carried out to value the option. Our American put option example is simple in that we know that the early exercise.   
boundary at a time can be defined entirely in terms of the value of the stock price at.   
that time. In more complicated situations it is necessary to make assumptions about.   
how the early exercise boundary should be parameterized..  

# Upper Bounds  

The two approaches we have outlined tend to underprice American-style options because they assume a suboptimal early exercise boundary. This has led Andersen and Broadie to propose a procedure that provides an upper bound to the price.32 This procedure can be used in conjunction with any algorithm that generates a lower bound and pinpoints the true value of an American-style option more precisely than the algorithm does by itself.  

# SUMMARY  

A number of models have been developed to fit the volatility smiles that are observed in practice. The constant elasticity of variance modelleads to a volatility smile similar to that. observed for equity options. The jump-diffusion model leads to a volatility smile similar. to that observed for currency options. Variance-gamma and stochastic volatility models. are more flexible in that they can lead to either the type of volatility smile observed for equity options or the type of volatility smile observed for currency options. The implied. volatility function model provides even more flexibility than this. It is designed to provide an exact fit to any pattern of European option prices observed in the market..  

The natural technique to use for valuing path-dependent options is Monte Carlo simulation. This has the disadvantage that it is fairly slow and unable to handle American-style derivatives easily. Luckily, trees can be used to value many types of path-dependent derivatives. The approach is to choose representative values for the underlying path function at each node of the tree and calculate the value of the derivative for each of these values as we roll back through the tree.  

The binomial tree methodology can be extended to value convertible bonds. Extra branches corresponding to a default by the company are added to the tree. The roll-back calculations then reflect the holder's option to convert and the issuer's option to call.  

Trees can be used to value many types of barrier options, but the convergence of the option value to the correct value as the number of time steps is increased tends to be slow. One approach for improving convergence is to arrange the geometry of the tree so that nodes always lie on the barriers. Another is to use an interpolation scheme to adjust for the fact that the barrier being assumed by the tree is different from the true barrier. A third is to design the tree so that it provides a finer representation of movements in the underlying asset price near the barrier.  

One way of valuing options dependent on the prices of two correlated assets is to. apply a transformation to the asset price to create two new uncorrelated variables.  

These two variables are each modeled with trees and the trees are then combined to form a single three-dimensional tree. At each node of the tree, the inverse of the.   
transformation gives the asset prices. A second approach is to arrange the positions.   
of nodes on the three-dimensional tree to reflect the correlation. A third approach is to.   
start with a tree that assumes no correlation between the variables and then adjust the.   
probabilities on the tree to reflect the correlation..  

Monte Carlo simulation is not naturally suited to valuing American-style options, but there are two waysit can be adapted to handle them. The first uses a least-squares analysis to relate the value of continuing (i.e, not exercising) to the values of relevant variables. The second involves parameterizing the early exercise boundary and determining it iteratively by working back from the end of the life of the option to the beginning.  

# FURTHER READING  

Andersen, L. B. G., "A Simple Approach to the Pricing of Bermudan Swaptions in the Multifactor LIBOR Market Model," Journal of Computational Finance, 3, 2 (Winter 2000): 1- 32.   
Andersen, L. B. G., and R. Brotherton-Ratcliffe, "The Equity Option Volatility Smile: An Implicit Finite Difference Approach," Journalof Computational Finance,1,2 (Winter 1997/98): 3-37.   
Bodurtha, J. N., and M. Jermakyan, "Non-Parametric Estimation of an Implied Volatility. Surface," Journal of Computational Finance, 2, 4 (Summer 1999): 29-61.   
Boyle, P. P., and S. H. Lau, "Bumping Up Against the Barrier with the Binomial Method," Journal of Derivatives, 1, 4 (Summer 1994): 6-14.   
Cox, J. C. and S. A. Ross, "The Valuation of Options for Alternative Stochastic Processes,' Journal of Financial Economics, 3 (March 1976), 145-66.   
Derman, E., and I. Kani, "Riding on a Smile,"' Risk, February (1994): 32-39..   
Duan, J.-C., "The GARCH Option Pricing Model," Mathematical Finance, 5 (1995): 13-32.   
Duan, J.-C., "Cracking the Smile," Risk, December (1996): 55-59.   
Dupire, B., "Pricing with a Smile," Risk, February (1994): 18-20.   
El Euch, O., J. Gatheral, and M. Rosenbaum, "Roughening Heston," Risk, May (2019): 84-89.   
Figlewski, S., and B. Gao, "The Adaptive Mesh Model: A New Approach to Efficient Option Pricing," Journal of Financial Economics, 53 (1999): 313-51.   
Gatheral, J., T. Jaisson, and M. Rosenbaum, "Volatility is Rough," Quantitative Finance, 18, 6 (2018): 933-949.   
Hagan, P., D. Kumar, A. Lesniewski, and D. Woodward, "Managing Smile Risk," Wilmott, September 2002: 84-108. Also www.math.ku.dk/\~rolf/SABR.pdf.   
Heston, S. L., "A Closed Form Solution for Options with Stochastic Volatility with Applications to Bonds and Currency Options," Review of Financial Studies, 6, 2 (1993): 327-43.   
Hull, J. C., and A. White, "Efficient Procedures for Valuing European and American Path-. Dependent Options," Journal of Derivatives, 1, 1 (Fall 1993): 21-31.   
Hull J. C., and A. White, "The Pricing of Options on Assets with Stochastic Volatilities," Journal of Finance, 42 (June 1987): 281-300.   
Hull, J. C. and W. Suo, "A Methodology for the Assessment of Model Risk and its Application to the Implied Volatility Function Model," Journal of Financial and Quantitative Analysis, 37,2 (2002): 297-318.   
Longstaff, F. A. and E. S. Schwartz, "Valuing American Options by Simulation: A Simple LeastSquares Approach, Review of Financial Studies, 14, 1 (Spring 2001): 113-47.   
Madan D. B., P. P. Carr, and E. C. Chang, "The Variance-Gamma Process and Option Pricing" European Finance Review, 2 (1998): 79-105.   
Merton, R. C., "Option Pricing When Underlying Stock Returns Are Discontinuous," Journal of Financial Economics, 3 (March 1976): 125-44.   
Milanov, K., O. Kounchev, F. J. Fabozzi, Y. S. Kim, and S. T. Rachev, "A Binomial Tree Model for Convertible Bond Pricing," Journal of Fixed Income, 22, 3 (Winter 2013): 79-94.   
Rebonato, R., Volatility and Correlation: The Perfect Hedger and the Fox, 2nd edn. Chichester: Wiley, 2004.   
Ritchken, P, and R. Trevor, "Pricing Options Under Generalized GARCH and Stochastic Volatility Processes," Journal of Finance 54, 1 (February 1999): 377-402   
Rubinstein, M., "Implied Binomial Trees," Journal of Finance, 49, 3 (July 1994): 771-818. Rubinstein, M., "Return to Oz," Risk, November (1994): 67-70.   
Stutzer, M., "A Simple Nonparametric Approach to Derivative Security Valuation, Journal of Finance, 51 (December 1996): 1633-52.   
Tilley, J. A., "Valuing American Options in a Path Simulation Model," Transactions of the Society of Actuaries, 45 (1993): 83-104.  

# Practice Questions  

27.1. Confirm that the CEV model formulas satisfy put-call parity.   
27.2. What is Merton's mixed jump-diffusion model price for a European call option when $r=5\%,q=0,\lambda=0.3,k=50\%,\sigma=25\%,S_{0}=30,K=30,s=50\%$ ,and $T=1.$ Use DerivaGem to check your price.   
27.3. Confirm that Merton's jump-diffusion model satisfies put-call parity when one plus the jump size is lognormal.   
27.4. Suppose that the volatility of an asset will be $20\%$ from month 0 to month 6, $22\%$ from month 6 to month 12, and $24\%$ from month 12 to month 24. What volatility should be used in Black-Scholes-Merton to value a 2-year option?   
27.5. Consider the case of Merton's jump-diffusion model where jumps always reduce the asset price to zero. Assume that the average number of jumps per year is $\lambda$ . Show that the price of a European call option is the same as in a world with no jumps except that the risk-free rate is $r+\lambda$ rather than $r$ . Does the possibility of jumps increase or reduce the value of the call option in this case? (Hint: Value the option assuming no jumps and assuming one or more jumps. The probability of no jumps in time $T$ is $e^{-\lambda\bar{T}}$   
27.6. At time 0 the price of a non-dividend-paying stock is $S_{0}$ Suppose that the time interval between O and $T$ is divided into two subintervals of length $t_{1}$ and $t_{2}$ . During the first subinterval, the risk-free interest rate and volatility are $r_{1}$ and $\sigma_{1}$ , respectively. During the second subinterval, they are $r_{2}$ and $\sigma_{2}$ , respectively. Assume that the world is risk neutral.. (a) Use the results in Chapter 15 to determine the stock price distribution at time $T$ in terms of $r_{1},r_{2},\sigma_{1},\sigma_{2},t_{1},t_{2}$ and $S_{0}$ (b) Suppose that $\bar{r}$ is the average interest rate between time zero and $T$ and that $\overline{V}$ is the average variance rate between times zero and T. What is the stock price distribution as a function of $T$ in terms of ${\bar{r}},{\overline{{V}}}$ $T.$ and $S_{0}$ (c) What are the results corresponding to (a) and (b) when there are three subintervals with different interest rates and volatilities?  

(d) Show that if the risk-free rate, $r$ , and the volatility,. $\sigma$ , are known functions of time, the stock price distribution at time $T$ in a risk-neutral world is.  

$$
\ln S_{T}\sim\phi[\ln S_{0}+(\bar{r}-{\textstyle\frac{1}{2}}\overline{{V}})T,\overline{{V}}T]
$$  

where $\bar{r}$ is the average value of $r,\overline{{V}}$ is equal to the average value of. $\sigma^{2}$ , and $S_{0}$ is the stock price today and. $\phi(m,\nu)$ is a normal distribution with mean $m$ and variance $\nu$  

27.7. Write down the equations for simulating the path followed by the asset price in the stochastic volatility model in equations (27.2) and (27.3).  

27.8. "The IVF model does not necessarily get the evolution of the volatility surface correct." Explain this statement.  

27.9. \*The IVF model correctly values any derivative whose payoff depends on the value of the underlying asset at only one time." Explain why..  

27.10. Use a three-time-step tree to value an American floating lookback call option on a currency when the initial exchange rate is 1.6, the domestic risk-free rate is $5\%$ per annum, the foreign risk-free interest rate is $8\%$ per annum, the exchange rate volatility is $15\%$ , and the time to maturity is 18 months. Use the approach in Section 27.5.  

27.11. What happens to the variance-gamma model as the parameter $\nu$ tends to zero?  

27.12. Use a three-time-step tree to value an American put option on the geometric average of the price of a non-dividend-paying stock when the stock price is $\$40$ , the strike price is $\$40$ , the risk-free interest rate is $10\%$ per annum, the volatility is. $35\%$ per annum, and the time to maturity is three months. The geometric average is measured from today until the option matures..  

27.13. Can the approach for valuing path-dependent options in Section 27.5 be used for a 2-year American-style option that provides a payoff equal to max( $\zeta_{\mathrm{ave}}\:-\:K,\:0\rangle$ , where $S_{\mathrm{ave}}$ is the average asset price over the three months preceding exercise? Explain your answer.  

27.14. Verify that the 6.492 number in Figure 27.3 is correct.  

27.15. Examine the early exercise policy for the eight paths considered in the example in Section 27.8. What is the difference between the early exercise policy given by the least. squares approach and the exercise boundary parameterization approach? Which gives a. higher option price for the paths sampled?.  

27.16. Consider a European put option on a non-dividend paying stock when the stock price is $\$100$ , the strike price is $\$110$ , the risk-free rate is $5\%$ per annum, and the time to. maturity is one year. Suppose that the average variance rate during the life of an option has a 0.20 probability of being 0.06, a 0.5 probability of being 0.09, and a 0.3 probability of being 0.12. The volatility is uncorrelated with the stock price. Estimate the value of the option. Use DerivaGem.  

27.17. When there are two barriers how can a tree be designed so that nodes lie on both barriers?  

27.18. Consider an 18-month zero-coupon bond with a face value of $\$100$ that can be converted into five shares of the company's stock at any time during its life. Suppose that the current share price is $\$20$ , no dividends are paid on the stock, the risk-free rate for all maturities is $6\%$ per annum with continuous compounding, and the share price volatility conditional on no default is $25\%$ per annum. Assume that the hazard rate is $3\%$ per year and the recovery rate is $35\%$ . The bond is callable at $\$110$ . Use a three-time-step tree to calculate the value of the bond. What is the value of the conversion option (net of the issuer's call option)?  

27.19. A new European-style floating lookback call option on a stock index has a maturity of 9 months. The current level of the index is 400, the risk-free rate is $6\%$ per annum, the dividend yield on the index is $4\%$ per annum, and the volatility of the index is $20\%$ . Use the approach in Section 27.5 to value the option and compare your answer to the result. given by DerivaGem using the analytic valuation formula.  

27.20. Technical Note 13 at www-2.rotman.utoronto.ca/\~hull/TechnicalNotes provides a different approach to valuing lookbacks. Value the lookback in Problem 27.19 using this approach. Show that it gives the same answer as the approach in Section 27.5..  

27.21. Suppose that the volatilities used to price a 6-month currency option are as in Table 20.2. Assume that the domestic and foreign risk-free rates are $5\%$ per annum and the current exchange rate is 1.00. Consider a bull spread that consists of a long position in a 6-month call option with strike price 1.05 and a short position in a 6-month call option with a strike price 1.10.  

(a) What is the value of the spread?   
(b) What single volatility if used for both options gives the correct value of the bull spread? (Use the DerivaGem Application Builder together with Goal Seek or Solver.)   
(c) Does your answer support the assertion at the beginning of the chapter that the correct volatility to use when pricing exotic options can be counterintuitive?   
(d) Does the IVF model give the correct price for the bull spread?  

27.22. Repeat the analysis in Section 27.8 for the put option example on the assumption that the strike price is 1.13. Use both the least squares approach and the exercise boundary parameterization approach.  

27.23. In the SABR model, suppose that $F_{0}=5,\beta=0.5,\sigma_{0}=0.447$ (equivalent to a lognormal volatility of $20\%$ ), and $T=1$ . Show how the volatility smile varies with $\rho$ for (a) $\nu=0.6$ and (b) $\nu=1.2$ . Consider value of $\rho$ equal to 0.4, 0.2, 0, $-0.2$ $-0.4$ and values of the strike price equal to 4.0, 4.5, 5.0, 5.5, 6.0.  

27.24. A 3-year convertible bond with a face value of. $\$100$ has been issued by company ABC. It pays a coupon of. $\$5$ at the end of each year. It can be converted into ABC's equity at the end of the first year or at the end of the second year. At the end of the first year, it can be exchanged for 3.6 shares immediately after the coupon date. At the end of the second. year, it can be exchanged for 3.5 shares immediately after the coupon date. The current. stock price is. $\$25$ and the stock price volatility conditional on no default is. $25\%$ . No dividends are paid on the stock. The risk-free interest rate is $5\%$ with continuous. compounding. The yield on bonds issued by ABC is. $7\%$ with continuous compounding and the recovery rate is $30\%$  

(a) Use a three-step tree to calculate the value of the bond.   
(b) How much is the conversion option worth?.   
(c) What difference does it make to the value of the bond if the bond is callable for $\$115$ immediately before the coupon payment at the end of years 1 and 2?   
(d) Explain how your analysis would change if there were a dividend payment of. $\$1$ on the equity at the 6-month, 18-month, and 30-month points. Detailed calculations are. not required.   
(Hint: Use equation (24.2) to estimate the average hazard rate.).  

27.25. Show that, if there is no recovery from the bond in the event of default, a convertible bond can be valued by assuming that (a) both the expected return and discount rate are $r+\lambda$ and (b) there is no chance of default.  

![](e6d4987018d78ea3f7cd47fbc5b1f2dcab706a442d12a55b025ef4eeabf8ae80.jpg)  

# Martingales and Measures  

Up to now interest rates have been assumed to be constant when valuing options. In this chapter, this assumption is relaxed in preparation for valuing interest rate derivatives in Chapters 29 to 34.  

The risk-neutral valuation principle states that a derivative can be valued by (a) calculating the expected payoff on the assumption that the expected return from the underlying asset equals the risk-free interest rate and (b) discounting the expected payoff at the risk-free interest rate. When interest rates are constant, risk-neutral valuation provides a well-defined and unambiguous valuation tool. When interest rates are stochastic, it is less clear-cut. What does it mean to assume that the expected return on the underlying asset equals to the risk-free rate? Does it mean (a) that each day the expected return is the one-day risk-free rate, or (b) that each year the expected return is the 1-year risk-free rate, or (c) that over a 5-year period the expected return is the 5-year rate at the beginning of the period? What does it mean to discount expected payoffs at the risk-free rate? Can we, for example, discount an expected payoff realized in year 5 at today's 5-year risk-free rate?  

In this chapter we explain the theoretical underpinnings of risk-neutral valuation when interest rates are stochastic and show that there are many different risk-neutral worlds that can be assumed in any given situation. We first define a parameter known as the market price of risk and show that the excess return over the risk-free interest rate earned by any derivative in a short period of time is linearly related to the market prices of risk of the underlying stochastic variables. What we will refer to as the traditional risk-neutral world assumes that all market prices of risk are zero, but we will find that other assumptions about the market price of risk are useful in some situations.  

Martingales and measures are critical to a full understanding of risk neutral valua-. tion. A martingale is a zero-drift stochastic process. A measure is the unit in which we. value security prices. A key result in this chapter will be the equivalent martingale. measure result. This states that if we use the price of a traded security as the unit of. measurement then there is a market price of risk for which all security prices follow martingales.  

This chapter illustrates the power of the equivalent martingale measure result by using it to extend Black's model (see Section 18.7) to the situation where interest rates are stochastic and to value options to exchange one asset for another. Chapter 29 uses the result to understand the standard market models for valuing interest rate derivatives,  

Chapter 30 uses it to value some nonstandard derivatives, and Chapter 33 uses it to develop the LIBOR market model.  
