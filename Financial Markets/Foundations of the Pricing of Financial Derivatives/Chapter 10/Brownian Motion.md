---
tags:
  - '#asset_pricing_models'
  - '#brownian_motion'
  - '#mathematical_modeling'
  - '#random_variables'
  - '#standard_normal_distribution'
  - '#time_series_analysis'
  - '#variance_calculation'
  - '#wiener_process'
---
# 10.1 BROWNIAN MOTION

In 1827, the Scottish botanist Robert Brown (1773-1858) observed the random behavior of pollen particles suspended in water. This phenomenon came to be known as Brownian motion. About 80 years passed before Albert Einstein developed the mathematical. properties of Brownian motion. This gap in time, however, is not to suggest that no work was being done in the interim, but scientists did not always know what additional research was going on. For example, Louis Bachelier in his doctoral work on option pricing in 1900. made numerous advances of these mathematical properties several years before Einstein. It is not surprising that it was Einstein who received most of the credit, because he was. certainly the most famous scientist of that era and possibly of all time. In this chapter and ensuing chapters, we shall borrow from the scientific theory of Brownian motion..

Let us start by assuming that a series of random numbers emanates from a standard normal or bell-shaped probability distribution. Let these variables be denoted as. $\varepsilon_{t+\Delta t}$ where $t+\Delta t$ denotes the point in time when the variable is observed. Because the numbers. are of the standard normal type, this means they on average equal zero and have a standard deviation of 1 (at the moment, we assume. $\Delta t=1$ ). Numbers like this have very limited properties, however, and in this form are not very useful for modeling asset prices, but we can take them further. Let us transform these numbers into another process identified with a $\boldsymbol{W}$ because it will eventually be called a Wiener process. Suppose we are currently. at time $t.$ This is our starting point. Now move ahead to time $t+\Delta t$ by drawing a number. from the standard normal probability distribution. Call the drawn number $\varepsilon_{t+\Delta t}$ which has an expected value of zero and its variance is 1. A very simple transformation of the standard normal variable into the W variable would be to add $\varepsilon_{t+\Delta t}$ to $\mathbf{}\mathbf{}{W}_{t}$ to get $\mathbb{W}_{t+\Delta t}$ Another simple transformation would be to multiply. $\varepsilon_{t+\Delta t}$ by a term we call. $d t$ which is the length of time that elapses between. $t$ and $t+\Delta t$ . Given that we typically measure. financial variables in years, if that time interval happens to be one minute,. $d t$ would be $1/\big(60^{*}24^{*}265\big)$ , or in other words, the fraction of a year that elapses between. $t$ and $t+\Delta t$

One reason we like to multiply $\varepsilon_{t+\Delta t}$ by a time factor is that we would like our model to accommodate time intervals between $t$ and $t+\Delta t$ of different lengths. These statistical shocks that are the source of randomness might be larger if they were spread out over a longer time period; hence, we need to scale them by a function of time. In fact, to model asset prices evolving continuously, we need the interval between. $t$ and $t+\Delta t$ to be as short. as possible. Mathematicians use the terminology in the limit, roughly meaning that we. are almost but not quite to a specific point. They also use. $d t$ instead of. $\Delta t$ Here dt will. approach zero in the limit but not actually get there. Unfortunately, the model $\mathbb{W}_{t+\Delta t}=$ $\mathbb{W}_{t}+\varepsilon_{t+\Delta t}d t$ will become problematic when $d t$ is nearly zero, because the variance of $\mathbf{\boldsymbol{W}}_{t+\Delta t}$ will be nearly zero. That is because $d t$ is very small and to obtain the variance, we have to square it, which drives it even closer to zero. Thus, the variable. $\mathbf{}\mathbf{}{W}_{t}$ will have no variance, which takes away its randomness. Because it would not vary, we cannot even call it a variable anymore.

The problem is best solved by multiplying $\varepsilon_{t+\Delta t}$ by the square root of $d t$

$$
\mathrm{W}_{t+1}=\mathrm{W}_{t}+\varepsilon_{t+\Delta t}\sqrt{d t}.
$$

Then when we square the term representing time to take the variance, we obtain $d t$ , which is not zero.

This model has many convenient properties. Suppose we are interested in predicting a future value of. $\boldsymbol{W}$ , say at time $t+\Delta t$ Then the expected value of. $\mathbb{W}_{t+\Delta t}$ is $\mathbf{}\mathbf{}{W}_{t}$ because the expected random change in the process is zero. If you start off at $\mathbf{}\mathbf{}{W}_{t}$ and keep incrementing it by values that average to zero, you can expect to get nowhere. The variance of $\mathbb{W}_{t+\Delta t}$ is $t+\Delta t=\Delta t$ , or, in other words, the variance equals how much time elapses between now, time $t$ , and the future point, time. $t+\Delta t$ . This result is found intuitively by noting that the variance of each increment is $d t$ . Integrating over all the increments, we obtain $\Delta t$ We shall do this in a more formal manner for the case in which the increment has a variance other than 1 later in this chapter.

Going forward, we seek to model a continuous process by allowing the time step, $\Delta t$ , to get smaller, essentially trending to nearly zero. Thus, the point of observation of $t$ or $t+\Delta t$ will be negligibly different. Going forward, we adopt the traditional notation. where, for example, $\varepsilon_{t+\Delta t}$ is denoted simply as $\varepsilon_{t}$ . The random variable, $\varepsilon_{t}.$ is observed at time $t+\Delta t$ but generated between points in time $t$ and $t+\Delta t$ Remember, the goal is to eventually migrate $\Delta t$ to $d t$
