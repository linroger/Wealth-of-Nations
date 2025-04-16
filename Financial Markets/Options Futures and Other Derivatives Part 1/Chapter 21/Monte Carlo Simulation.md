---
tags:
  - '#asian_option'
  - '#black_scholes_merton'
  - '#cholesky_decomposition'
  - '#derivative_valuation'
  - '#greek_letters'
  - '#monte_carlo_simulation'
  - '#option_pricing'
  - '#random_sampling'
  - '#risk_neutral_valuation'
  - '#stochastic_processes'
---
# 21.6 MONTE CARLO SIMULATION  

We now explain Monte Carlo simulation, a quite different approach for valuing derivatives from binomial trees. Business Snapshot 21.1 illustrates the random sampling idea underlying Monte Carlo simulation by showing how a simple Excel program can be constructed to estimate $\pi$  

When used to value an option, Monte Carlo simulation uses the risk-neutral valuation result. We sample paths to obtain the expected payoff in a risk-neutral world  

Figure 21.13 Calculation of $\pi$ by throwing darts.  

![](images/1c96f1c905c1ede8d51dab3ecd8c94665f18b2392b0add2268fd7a3038ca28d6.jpg)  

Table 21.1 Sample spreadsheet calculations in Business Snapshot 21.1.   


<html><body><table><tr><td></td><td>A</td><td>B</td><td>C</td></tr><tr><td>1</td><td>0.207</td><td>0.690</td><td>4</td></tr><tr><td>2</td><td>0.271</td><td>0.520</td><td>4</td></tr><tr><td>3</td><td>0.007</td><td>0.221</td><td>0</td></tr><tr><td>·</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>*</td></tr><tr><td>100</td><td>0.198</td><td>0.403</td><td>4</td></tr><tr><td>101</td><td></td><td></td><td></td></tr><tr><td>102</td><td></td><td>Mean:</td><td>3.04</td></tr><tr><td>103</td><td></td><td>SD:</td><td>1.69</td></tr></table></body></html>  

and then discount this payoff at the risk-free rate. Consider a derivative dependent on a single market variable $S$ that provides a payoff at time $T.$ Assuming that interest rates are constant, we can value the derivative as follows:  

1. Sample a random path for $S$ in a risk-neutral world..   
2. Calculate the payoff from the derivative.   
3. Repeat steps 1 and 2 to get many sample values of the payoff from the derivative in a risk-neutral world..   
4. Calculate the mean of the sample payoffs to get an estimate of the expected payoff. in a risk-neutral world..   
5. Discount this expected payoff at the risk-free rate to get an estimate of the value of the derivative.  

This is illustrated by the Monte Carlo worksheet in DerivaGem.  

Suppose that the process followed by the underlying market variable in a risk-neutra. world is  

$$
d S=\hat{\mu}S d t+\sigma S d z
$$  

where $d z$ is a Wiener process, $\hat{\mu}$ is the expected return in a risk-neutral world, and $\sigma$ is the volatility.12 To simulate the path followed by. $S$ , we can divide the life of the derivative into $N$ short intervals of length $\Delta t$ and approximate equation (21.13) as  

$$
S(t+\Delta t)-S(t)=\hat{\mu}S(t)\Delta t+\sigma S(t)\epsilon\sqrt{\Delta t}
$$  

where $S(t)$ denotes the value of. $S$ at time $t,\epsilon$ is a random sample from a normal. distribution with mean zero and standard deviation of 1.0. This enables the value of $S$ at time $\Delta t$ to be calculated from the initial value of $S$ the value at time. $2~\Delta t$ to be calculated from the value at time. $\Delta t$ and so on. An illustration of the procedure is in Section 14.3. One simulation trial involves constructing a complete path for $S$ using $N$ random samples from a normal distribution.  

In practice, it is usually more accurate to simulate ln $S$ rather than $S$ . From Ito's lemma the process followed by ln $S$ is  

$$
d\ln S=\bigg(\hat{\mu}-\frac{\sigma^{2}}{2}\bigg)d t+\sigma d z
$$  

so that  

or equivalently  

$$
\ln S(t+\Delta t)-\ln S(t)=\bigg(\hat{\mu}-\frac{\sigma^{2}}{2}\bigg)\Delta t+\sigma\epsilon\sqrt{\Delta t}
$$  

$$
S(t+\Delta t)=S(t)\mathrm{exp}\bigg[\bigg(\hat{\mu}-\frac{\sigma^{2}}{2}\bigg)\Delta t+\sigma\epsilon\sqrt{\Delta t}\bigg]
$$  

This equation is used to construct a path for $S$  

Working with $\ln S$ rather than $S$ gives more accuracy. Also, if $\hat{\mu}$ and $\sigma$ are constant, then  

$$
\ln S(T)-\ln S(0)=\biggl(\hat{\mu}-\frac{\sigma^{2}}{2}\biggl)T+\sigma\epsilon\sqrt{T}
$$  

is true for all $T.^{13}$ It follows that  

$$
S(T)=S(0)\mathrm{exp}\biggl[\biggl(\hat{\mu}-\frac{\sigma^{2}}{2}\biggr)T+\sigma\epsilon\sqrt{T}\biggr]
$$  

This equation can be used to value derivatives that provide a nonstandard payoff at time $T$ As shown in Business Snapshot 21.2, it can also be used to check the Black-- Scholes-Merton formulas.  

The key advantage of Monte Carlo simulation is that it can be used when the. payoff depends on the path followed by the underlying variable. $S$ as well as when it. depends only on the final value of S. (For example, it can be used when payoffs depend on the average value of $S$ between time 0 and time. $T.$ ) Payoffs can occur at. several times during the life of the derivative rather than all at the end. Any stochastic process for $S$ can be accommodated. As will be shown shortly, the procedure can also. be extended to accommodate situations where the payoff from the derivative depends on several underlying market variables. The drawbacks of Monte Carlo simulation are. that it is computationally very time consuming and cannot easily handle situations where there are early exercise opportunities.14  

# Derivatives Dependent on More than One Market Variable  

We discussed correlated stochastic processes in Section 14.5. Consider the situation where the payoff from a derivative depends on $n$ variables $\theta_{i}$ $1\leq i\leq n$ ). Define $s_{i}$ as the volatility of $\theta_{i}$ $\hat{m}_{i}$ as the expected growth rate of $\theta_{i}$ in a risk-neutral world, and $\rho_{i k}$ as the correlation between the Wiener processes driving $\theta_{i}$ and $\theta_{k}$ 15 As in the single-variable case, the life of the derivative must be divided into $N$ subintervals of length $\Delta t.$ The  

# Business Snapshot 21.2 Checking Black-Scholes-Merton in Excel  

The Black-Scholes-Merton formula for a European call option can be checked by using a binomial tree with a very large number of time steps. An alternative way of checking it is to use Monte Carlo simulation. Table 21.2 shows a spreadsheet that can be constructed. The cells $\mathrm{C}2,\mathrm{D}2,\mathrm{E}2,\mathrm{F}2$ , and G2 contain $S_{\mathrm{0}},K,r,\sigma$ , and $T$ , respectively. Cells D4, E4, and F4 calculate $d_{1},d_{2}$ , and the Black-Scholes-Merton price, respectively. (The Black-Scholes-Merton price is 4.817 in the sample spreadsheet.)  

NORMSINV is the inverse cumulative function for the standard normal distribution. It follows that NORMSINV(RANDQ) gives a random sample from a standard normal distribution. We set cell A1 as  

$$
=5\mathrm{CS2^{\ast}E X P((\mathbb{S}E\mathbb{S}2-\mathbb{S}F\mathbb{S}2^{\ast}\mathbb{S}\mathrm{F}\mathbb{S}2/2)^{\ast}\mathbb{S}\mathrm{G}\mathbb{S}2+\mathbb{S}\mathrm{F}\mathbb{S}2^{\ast}\mathrm{NORMSINV}(\mathrm{RAND(\it~)})^{\ast}\mathrm{SORT(\mathbb{S}G\mathbb{S}2))}
$$  

This corresponds to equation (21.17) and is a random sample from the set of all stock prices at time T. We set cell B1 as  

$$
=\mathrm{EXP}(-\S\mathrm{E}\S2^{*}\S\mathrm{G}\S2)^{*}\mathbf{M}\mathrm{AX}(\mathrm{A}1-\S\mathrm{D}\S2,0)
$$  

This is the present value of the payoff from a call option. We define the next 999 rows of the spreadsheet similarly to the first one. (This is a "select and drag" operation in Excel.) Define B1002 as AVERAGE(B1:B1000), which is 4.98 in the sample spreadsheet. This is an estimate of the value of the option and should be not too far from the Black-Scholes-Merton price. B1003 is defined as STDEV(B1:B1000).As we shall see in Example 21.8, it can be used to assess the accuracy of the estimate.  

discrete version of the process for $\theta_{i}$ is then  

$$
\theta_{i}(t+\Delta t)-\theta_{i}(t)=\hat{m}_{i}\theta_{i}(t)\Delta t+s_{i}\theta_{i}(t)\epsilon_{i}\sqrt{\Delta t}
$$  

where $\epsilon_{i}$ is a random sample from a standard normal distribution. The coefficient of correlation between $\epsilon_{i}$ and $\epsilon_{k}$ .5 $\rho_{i k}$ $1\leq i;k\leq n$ ). One simulation trial involves obtaining $N$ samples of the $\epsilon_{i}$ - $1\leq i\leq n$ ) from a multivariate standardized normal distribution. These are substituted into equation (21.18) to produce simulated paths for each $\theta_{i},$ thereby enabling a sample value for the derivative to be calculated.  

Table 21.2 Monte Carlo simulation to check Black-Scholes-Merton.   


<html><body><table><tr><td></td><td>A</td><td>B</td><td>C</td><td>D</td><td>E</td><td>F</td><td>G</td></tr><tr><td>1</td><td>45.95</td><td>0</td><td>So</td><td>K</td><td>r</td><td></td><td>T</td></tr><tr><td>2</td><td>54.49</td><td>4.38</td><td>50</td><td>50</td><td>0.05</td><td>0.3</td><td>0.5</td></tr><tr><td>3</td><td>50.09</td><td>0.09</td><td></td><td>d1</td><td>d2</td><td>BSM price</td><td></td></tr><tr><td>4</td><td>47.46</td><td>0</td><td></td><td>0.2239</td><td>0.0118</td><td>4.817</td><td></td></tr><tr><td>5</td><td>44.93</td><td>0</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>*</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>1000</td><td>68.27</td><td>17.82</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>1001</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>1002 1003</td><td>Mean: SD:</td><td>4.98 7.68</td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>  

# Generating the Random Samples from Normal Distributions  

The instruction $\risingdotseq$ NORMSINV(RAND()) in Excel can be used to generate a random sample from a standard normal distribution, as in Business Snapshot 21.2. When two correlated samples $\epsilon_{1}$ and $\epsilon_{2}$ from standard normal distributions are required, an. appropriate procedure is as follows. Independent samples. $x_{1}$ and $x_{2}$ from a univariate standardized normal distribution are obtained as just described. The required samples. $\epsilon_{1}$ and $\epsilon_{2}$ are then calculated as follows:.  

$$
\begin{array}{l}{\epsilon_{1}=x_{1}}\ {\epsilon_{2}=\rho x_{1}+x_{2}\sqrt{1-\rho^{2}}}\end{array}
$$  

where $\rho$ is the coefficient of correlation.  

More generally, consider the situation where we require $n$ correlated samples from normal distributions with the correlation between sample $i$ and sample $j$ being $\rho_{i j}$ We first sample $n$ independent variables $x_{i}$ $(1\leq i\leq n$ ), from univariate standardized normal distributions. The required samples, $\epsilon_{i}$ $1\leq i\leq n$ ), are then defined as follows:  

$$
\left.\begin{array}{l}{\epsilon_{1}=\alpha_{11}x_{1}}\ {\epsilon_{2}=\alpha_{21}x_{1}+\alpha_{22}x_{2}}\ {\epsilon_{3}=\alpha_{31}x_{1}+\alpha_{32}x_{2}+\alpha_{33}x_{3}}\end{array}\right\}
$$  

and so on. We choose the coefficients $\alpha_{i j}$ so that the correlations and variances are correct. This can be done step by step as follows. Set $\alpha_{11}=1$ ; choose $\alpha_{21}$ so that $\alpha_{21}\alpha_{11}=\rho_{21}$ ; choose $\alpha_{22}$ so that $\alpha_{21}^{2}+\alpha_{22}^{2}=1$ ; choose $\alpha_{31}$ so that $\alpha_{31}\alpha_{11}=\rho_{31}$ ; choose d32 50 that a31021 + 03222 = P32; choose 33 so that 31 + 032 + 033 = 1; and so on.16 This procedure is known as the Cholesky decomposition.  

# Number of Trials  

The accuracy of the result given by Monte Carlo simulation depends on the number of. trials. It is usual to calculate the standard deviation as well as the mean of the discounted payoffs given by the simulation trials. Denote the mean by $\mu$ and the standard deviation by $\omega$ . The variable $\mu$ is the simulation's estimate of the value of the derivative. The standard error of the estimate is  

$$
\frac{\omega}{\sqrt{M}}
$$  

where $M$ is the number of trials. A. $95\%$ confidence interval for the price $f$ of the derivative is therefore given by.  

$$
\mu-\frac{1.96\omega}{\sqrt{M}}<f<\mu+\frac{1.96\omega}{\sqrt{M}}
$$  

This shows that uncertainty about the value of the derivative is inversely proportional to the square root of the number of trials. To double the accuracy of a simulation, we  

must quadruple the number of trials; to increase the accuracy by a factor of 10, the number of trials must increase by a factor of 100; and so on..  

# Example 21.7  

In Table 21.1, $\pi$ is calculated as the average of 100 numbers. The standard deviation of the numbers is 1.69. In this case, $\omega=1.69$ and $M=100$ , so that the standard error of the estimate is $1.69/\sqrt{100}=0.169$ . The spreadsheet therefore gives a $95\%$ confidence interval for $\pi$ as $(3.04-1.96\times0.169)$ to $(3.04+1.96\times0.169)$ or 2.71 to 3.37. (The correct value of 3.14159 lies within this confidence interval.)  

# Example 21.8  

In Table 21.2, the value of the option is calculated as the average of 1000 numbers. The standard deviation of the numbers is 7.68. In this case, $\omega=7.68$ and $M=1000$ . The standard error of the estimate is $7.68/\sqrt{1000}=0.24$ The spreadsheet therefore gives a $95\%$ confidence interval for the option value as $(4.98-1.96\times0.24)$ to $(4.98+1.96\times0.24\$ ), or 4.51 to 5.45. (The Black-Scholes-- Merton price, 4.817, lies within this confidence interval.)  

# Sampling through a Tree  

Instead of implementing Monte Carlo simulation by randomly sampling from the. stochastic process for an underlying variable, we can use an $N$ step binomial tree and sample from the $2^{N}$ paths that are possible. Suppose we have a binomial tree where the probability of an "up"' movement is 0.6. The procedure for sampling a random path. through the tree is as follows. At each node, we sample a random number between 0 and 1. If the number is less than O.4, we take the down branch. If it is greater than 0.4, we take the up branch. Once we have a complete path from the initial node to the end of. the tree, we can calculate a payoff. This completes the first trial. A similar procedure is used to complete more trials. The mean of the payoffs is discounted at the risk-free rate to get an estimate of the value of the derivative.17  

# Example 21.9  

Suppose that the tree in Figure 21.3 is used to value an option that pays off $\mathrm{max}(S_{\mathrm{ave}}-50,0)$ , where $S_{\mathrm{ave}}$ is the average stock price during the 5 months (with the first and last stock price being included in the average). This is known as an Asian option. When ten simulation trials are used one possible result is shown in Table 21.3. The value of the option is calculated as the average payoff discounted at the risk-free rate. In this case, the average payoff is $\$7.08$ and the risk-free rate is $10\%$ and so the calculated value is $7.08e^{-0.1\times5/12}=6.79$ (This illustrates the methodology. In practice, we would have to use more time steps on the tree and. many more simulation trials to get an accurate answer.)  

# Calculating the Greek Letters  

The Greek letters discussed in Chapter 19 can be calculated using Monte Carlo simulation. Suppose that we are interested in the partial derivative of $f$ with respect to $x$ , where $f$ is the value of the derivative and. $x$ is the value of an underlying variable. or a parameter. First, Monte Carlo simulation is used in the usual way to calculate an estimate $\hat{f}$ for the value of the derivative. A small increase $\Delta x$ is then made in the value of $x$ , and a new value for the derivative,. $\hat{f}^{*}$ , is calculated in the same way as. $\hat{f}$ . An estimate for the hedge parameter is given by.  

Table 21.3  Monte Carlo simulation to value Asian option from the tree in Figure 21.3. Payoff is amount by which average stock price exceeds $\$50.0$ up movement; $\mathbf{D_{\alpha}}=$ down movement.   


<html><body><table><tr><td>Trial</td><td>Path</td><td>Averagestockprice</td><td>Optionpayoff</td></tr><tr><td>1</td><td>UUUUD</td><td>64.98</td><td>14.98</td></tr><tr><td>2</td><td>UUUDD</td><td>59.82</td><td>9.82</td></tr><tr><td>3</td><td>DDDUU</td><td>42.31</td><td>0.00</td></tr><tr><td>4</td><td>UUUUU</td><td>68.04</td><td>18.04</td></tr><tr><td>5</td><td>UUDDU</td><td>55.22</td><td>5.22</td></tr><tr><td>6</td><td>UDUUD</td><td>55.22</td><td>5.22</td></tr><tr><td>7</td><td>DDUDD</td><td>42.31</td><td>0.00</td></tr><tr><td>8</td><td>UUDDU</td><td>55.22</td><td>5.22</td></tr><tr><td>9</td><td>UUUDU</td><td>62.25</td><td>12.25</td></tr><tr><td>10</td><td>DDUUD</td><td>45.56</td><td>0.00</td></tr><tr><td>Average</td><td></td><td></td><td>7.08</td></tr></table></body></html>  

$$
\frac{\hat{f}^{*}-\hat{f}}{\Delta x}
$$  

In order to minimize the standard error of the estimate, the number of time intervals, $N$ the random samples that are used, and the number of trials, $M$ , should be the same for. calculating both $\hat{f}$ and $\hat{f}^{*}$  

# Applications  

Monte Carlo simulation tends to be numerically more efficient than other procedures when there are three or more stochastic variables. This is because the time taken to carry out a Monte Carlo simulation increases approximately linearly with the number of variables, whereas the time taken for most other procedures increases exponentially with the number of variables. One advantage of Monte Carlo simulation is that it can provide a standard error for the estimates that it makes. Another is that it is an approach that can accommodate complex payoffs and complex stochastic processes. Also, it can be used when the payoff depends on some function of the whole path followed by a variable, not just its terminal value.  
