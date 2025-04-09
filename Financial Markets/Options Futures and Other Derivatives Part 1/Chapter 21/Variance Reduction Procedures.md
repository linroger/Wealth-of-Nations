# 21.7 VARIANCE REDUCTION PROCEDURES  

If the stochastic processes for the variables underlying a derivative are simulated as. indicated in equations (21.13) to (21.18), a very large number of trials is usually  

necessary to estimate the value of the derivative with reasonable accuracy. This is very. expensive in terms of computation time. In this section, we examine a number of variance reduction procedures that can lead to dramatic savings in computation time..  

# Antithetic Variable Technique  

In the antithetic variable technique, a simulation trial involves calculating two values of the derivative. The first value $f_{1}$ is calculated in the usual way; the second value. $f_{2}$ is calculated by changing the sign of all the random samples from standard normal. distributions. (If $\epsilon$ is a sample used to calculate $f_{1}$ , then $-\epsilon$ is the corresponding sample used to calculate $f_{2}$ ) The sample value of the derivative calculated from a simulation. trial is the average of $f_{1}$ and $f_{2}$ . This works well because when $f_{1}$ is above the true value, $f_{2}$ tends to be below, and vice versa..  

Denote $\bar{f}$ as the average of. $f_{1}$ and $f_{2}$  

$$
\bar{f}=\frac{f_{1}+f_{2}}{2}
$$  

The final estimate of the value of the derivative is the average of the $\bar{f}$ 's. If $\bar{\omega}$ is the standard deviation of the $\bar{f}$ s, and $M$ is the number of simulation trials (i.e., the number of pairs of values calculated), then the standard error of the estimate is  

$$
{\bar{\omega}}/{\sqrt{M}}
$$  

This is usually much less than the standard error calculated using $2M$ random trials.  

# Control Variate Technique  

We have already given one example of the control variate technique in connection with the use of trees to value American options (see Section 21.3). The control variate technique is applicable when there are two similar derivatives, A and B. Derivative A is the one being valued; derivative B is similar to derivative A and has an analytic solution available. Two simulations using the same random number streams and the same $\Delta t$ are carried out in parallel. The first is used to obtain an estimate $f_{A}^{*}$ of the value of A; the second is used to obtain an estimate $f_{B}^{*}$ , of the value of B. A better estimate $f_{A}$ of the value of A is then obtained using the formula  

$$
f_{A}=f_{A}^{*}-f_{B}^{*}+f_{B}
$$  

where $f_{B}$ is the known true value of B calculated analytically. Hull and White provide. an example of the use of the control variate technique when evaluating the effect of stochastic volatility on the price of a European call option.18 In this case, A is the option assuming stochastic volatility and. $\mathrm{B}$ is the option assuming constant volatility..  

# Importance Sampling  

Importance sampling is best explained with an example. Suppose that we wish to calculate the price of a deep-out-of-the-money European call option with strike.  

price $K$ and maturity $T.$ If we sample values for the underlying asset price at time $T$ in the usual way, most of the paths will lead to zero payoff. This is a waste of computation time because the zero-payoff paths contribute very little to the determination of the value of the option. We therefore try to choose only important paths, that is, paths where the stock price is above $K$ at maturity.  

Suppose $F$ is the unconditional probability distribution function for the stock price at time $T$ and $q$ , the probability of the stock price being greater than $K$ at maturity, is known analytically. Then $G=F/q$ is the probability distribution of the stock price conditional on the stock price being greater than $K$ . To implement importance sampling, we sample from $G$ rather than $F.$ The estimate of the value of the option is the average discounted payoff multiplied by $q$  

# Stratified Sampling  

Sampling representative values rather than random values from a probability distribution usually gives more accuracy. Stratified sampling is a way of doing this. Suppose we.   
wish to take 1000 samples from a probability distribution. We would divide the.   
distribution into 1000 equally likely intervals and choose a representative value.   
(typically the mean or median) for each interval..  

In the case of a standard normal distribution when there are $n$ intervals, we can calculate the representative value for the ith interval as  

$$
N^{-1}\bigg(\frac{i-0.5}{n}\bigg)
$$  

where $N^{-1}$ is the inverse cumulative normal distribution. For example, when $n=4$ the representative values corresponding to the four intervals are $N^{-1}(0.125)$ $N^{-1}(0.375)$ $N^{-1}(0.625)$ $N^{-1}(0.875)$ . The function $N^{-1}$ can be calculated using the NORMSINV function in Excel.  

# Moment Matching  

Moment matching involves adjusting the samples taken from a standardized normal. distribution so that the first, second, and possibly higher moments are matched.. Suppose that we sample from a normal distribution with mean 0 and standard deviation 1 to calculate the change in the value of a particular variable over a particular. time period. Suppose that the samples are e;. $(1\leq i\leq n)$ . To match the first two moments, we calculate the mean of the samples,. $m$ , and the standard deviation of the samples, $s$ We then define adjusted samples $\epsilon_{i}^{*}$ $1\leq i\leq n$ ) as  

$$
\epsilon_{i}^{*}=\frac{\epsilon_{i}-m}{s}
$$  

These adjusted samples have the correct mean of 0 and the correct standard deviation of 1.0. We use the adjusted samples for all calculations.  

Moment matching saves computation time, but can lead to memory problems. because every number sampled must be stored until the end of the simulation. Moment matching is sometimes termed quadratic resampling. It is often used in conjunction with the antithetic variable technique. Because the latter automatically matches all odd.  

moments, the goal of moment matching then becomes that of matching the second moment and, possibly, the fourth moment.  

# Using Quasi-Random Sequences  

A quasi-random sequence (also called a low-discrepancy sequence) is a sequence of representative samples from a probability distribution.19 Descriptions of the use of quasi-random sequences appear in Brotherton-Ratcliffe, and Press et al.20 Quasi-random sequences can have the desirable property that they lead to the standard error of an estimate being proportional to $1/M$ rather than $1/\dot{\sqrt{M}}$ , where $M$ is the sample size.  

Quasi-random sampling is similar to stratified sampling. The objective is to sample. representative values for the underlying variables. In stratified sampling, it is assumed that we know in advance how many samples will be taken. A quasi-random sampling. procedure is more flexible. The samples are taken in such a way that we are always. "filling in" gaps between existing samples. At each stage of the simulation, the sampled. points are roughly evenly spaced throughout the probability space..  

Figure 21.14 shows points generated in two dimensions using a procedure by Sobol'.21 It can be seen that successive points do tend to fill in the gaps left by previous points.  
