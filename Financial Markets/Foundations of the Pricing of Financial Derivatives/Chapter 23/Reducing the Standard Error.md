# 23.2 REDUCING THE STANDARD ERROR

The option price obtained from a Monte Carlo simulation is a sample average. Thus, its standard deviation is the standard deviation of the sample divided by the square root of the sample size.4 Consequently, the error reduces at the rate of 1 over the square root of the sample size. Notice what this means for increasing the sample accuracy by increasing the sample size. Suppose $\sigma_{S}$ is the sample standard deviation. We first conduct a Monte Carlo simulation using $n_{1}$ random drawings. Because the option value is a sample mean, the. standard deviation of our estimate of the option value is. $\sigma_{S}/\sqrt{n_{1}}$ where $n_{1}$ is the sample size. Now suppose we wanted to reduce that standard deviation in half. How much larger must the sample be? Let this new sample size be. $n_{2}$ . Then its standard deviation of the estimate of. the option price is $\sigma_{S}/\sqrt{n_{2}}$ Now note that the following specification, which reduces the. standard deviation of the average in half:

$$
\frac{1}{2}\frac{\sigma_{S}}{\sqrt{n_{1}}}=\frac{\sigma_{S}}{\sqrt{n_{2}}},
$$

if and only if

$$
n_{2}=4n_{1}.
$$

IABLE 23.2 Monte Carlo Price of Standard European Call Option


<html><body><table><tr><td></td><td colspan="4">Number of Trials</td></tr><tr><td>Parameters for 20 samples</td><td>1,000 (base case)</td><td>4,000</td><td>16,000</td><td>100,000</td></tr><tr><td>Average</td><td>2.9721</td><td>3.0007</td><td>2.9774</td><td>2.9795</td></tr><tr><td>Standarddeviation</td><td>0.0921</td><td>0.0561</td><td>0.0219</td><td>0.0126</td></tr><tr><td>Percentage reduction from base case</td><td>NA</td><td>39.09%</td><td>76.22%</td><td>86.32%</td></tr></table></body></html>

Thus, to achieve a $50\%$ reduction in error, that is, a $50\%$ increase in accuracy, we must quadruple the number of random drawings. The standard error reduces only at the rate of the square root of the sample size, not at the rate of the sample size itself.

Table 23.2 provides an example of this effect. Consider a European call with an asset price of 42, an exercise price of 40, a volatility of 0.35, a risk-free rate of $5\%$ , and a time to expiration of one month, which is $1/12=0.0833$ The table presents the results of simulations of 1,000, 4,000, 16,000, and 100,000 trials. For each set of these trials, the simulation is run 20 times. In other words, there are 20 simulations of 1,000 trials, 20 simulations of 4,000 trials, and so on. The mean and standard deviation of each group of. 20 simulations of 1,000, 4,000, 16,000, and 100,000 trials is shown in the table. Starting off with the 1,000-trial case, the average value is 2.9721 with a standard deviation of 0.0921 across the 20 runs of 1,000 trials each. Now, suppose we want to cut that standard. deviation in half. As noted, we need to quadruple the number of trials. Hence, we do 20. runs of 4,000 trials. The average is shown as 3.0007 and the standard deviation is 0.0561.. This is a reduction of about. $39\%$ , which is not the $50\%$ reduction we hoped for, but. the formula is not an exact result. It is a sample result and will get more accurate with larger samples. If we want to cut the standard deviation by $75\%$ , the formula above would say that we need 16,000 trials. In the next column, notice that the reduction in standard. deviation is $76\%$ . The final column is the case of 100,o00 trials, which is the number required to cut the standard deviation by. $90\%$ . Note that it does a pretty good job, as the standard deviation is reduced by. $86\%$

But still, it can take a lot of trials to get a high degree of accuracy. Notice with 100,000. trials, the standard deviation in this problem is about 1.3 cents. Because the sample average is normally distributed by the central limit theorem, we can say that the mean estimate of 2.9795 is bracketed with $95\%$ confidence in a range of plus or minus two standard deviations, which is $2(0.0126)=0.0252$ . That means the confidence interval is 2.9543 to 3.0047. For an institution with a lot of volume, a five-cent interval can be quite large.

# 23.2.1 The Antithetic Variate Method

With this problem in mind, it behooves the user of Monte Carlo simulation to attempt to achieve greater accuracy through other means. One method of doing so is quite simple and automatically doubles the sample size with only a minimum increase in computational time. This approach is called the antithetic variate method. Remember that in the standard Monte Carlo simulation, we are generating observations of a standard normal random variable. The standard normal random variable is distributed with a mean of zero, a variance of 1.0, and is symmetric. Thus, for each value we draw, there is an equally likely chance of having drawn the observed value times $-1$ . Consequently, for each value of $\varepsilon$ we draw, we can legitimately create an artificially observed companion observation of $-\varepsilon$ . This paired drawing is the antithetic variate. We simply use it the same way we use the value we drew, that is, in computing a sequence of asset prices from which we compute an option price based on the price at expiration. This procedure automatically doubles our sample size without having increased the number of random drawings. To take advantage of the antithetic variate method, we should average the option price from the standard result with the option price from the antithetic variate result. We get two observations for the price of one as well as a more accurate average.

In the case of Black-Scholes-Merton, which converges rapidly in a simulation, this may not matter that much.

# 23.2.2 The Control Variate Method

Another method that can be used with certain types of options is called the control variate. method, which in this context is a somewhat similar option whose value is known. We then obtain a simulated value of that option. The difference between the value of the control variate and its simulated value is then added to the simulated value of the option we are. trying to price. In this manner, the error in the control variate is added to the simulated value of the option of interest. Let us see how this method works..

Let $c_{s}$ be the simulated price of the option we are trying to price. Let $\nu_{t}$ be the value of another similar option and. $\nu_{s}$ be its simulated value. Our control variate estimate of the option price is then found as.

$$
c_{s}+(\nu_{t}-\nu_{s}).
$$

What we are doing is running a simulation of $c_{s}-\nu_{s}$ and adding $\nu_{t}$ to try to obtain a better estimate. Note the following result for the variance:

$$
\operatorname{var}(c_{s}-\nu_{s})=\operatorname{var}(c_{s})+\operatorname{var}(\nu_{s})-2\operatorname{cov}(c_{s},\nu_{s}).
$$

This will be less than $\mathrm{var}(c_{s})$ if $\operatorname{var}(\nu_{s})<2\operatorname{cov}(c_{s},\nu_{s})$ , meaning that the control variate method relies on the assumption of a large covariance between $c_{s}$ and $\nu_{s}$ . The control variate chosen should be one that is very highly correlated with the option we are pricing.

The control variate method is somewhat appropriate when pricing complex and. path-dependent options. It can be challenging to use, however, in that we must know a. great deal about the relationship of the price of the control variate to the price of the option of interest. Often it is difficult to know something about that relationship without knowing how to price the option of interest..

# 23.2.3 Other Methods for Improved Simulation

There are a number of methods for improving the accuracy of Monte Carlo simulation. Some methods improve the sampling process so that random but unusual results are balanced with more typical outcomes. These methods belong to a family called low discrepancy sequences. For example, if a random sample is generated, it is quite possible that numbers that ought to appear with a given frequency within a specific range might not appear with the expected frequency. Some common techniques from this family are Halton sequences and Sobol numbers, which are used to supply random outcomes that result in the sample of random numbers being much closer to a truly random sample with observed outcomes as expected.
