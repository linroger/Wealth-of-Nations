---
tags:
  - '#ewma_model'
  - '#garch_1_1_model'
  - '#ljung_box_statistic'
  - '#maximum_likelihood_method'
  - '#parameter_estimation'
  - '#sp_500_index'
  - '#variance_estimation'
  - '#variance_targeting'
  - '#volatility_modeling'
---
# 23.5 MAXIMUM LIKELIHOOD METHODS  

It is now appropriate to discuss how the parameters in the models we have been. considering are estimated from historical data. The approach used is known as the maximum likelihood method. It involves choosing values for the parameters that. maximize the chance (or likelihood) of the data occurring.  

To illustrate the method, we start with a very simple example. Suppose that we sample 10 stocks at random on a certain day and find that the price of one of them declined on that day and the prices of the other nine either remained the same or increased. What is the best estimate of the probability of a randomly chosen stock's price declining on the day? The natural answer is O.1. Let us see if this is what the maximum likelihood method gives.  

Suppose that the probability of a price decline is. $p$ . The probability that one particular stock declines in price and the other nine do not is $\bar{p}(1-p)^{9}$ . Using the. maximum likelihood approach, the best estimate of. $p$ is the one that maximizes. $p(1-p)^{9}$ Differentiating this expression with respect to. $p$ and setting the result equal to zero, we find that. $p=0.1$ maximizes the expression. This shows that the maximum likelihood estimate of. $p$ is 0.1, as expected.  

# Estimating a Constant Variance  

Our next example of maximum likelihood methods considers the problem of estimating the variance of a variable. $X$ from $m$ observations on $X$ when the underlying distribution. is normal with zero mean. Assume that the observations are $u_{1},u_{2},\ldots,u_{m}$ Denote the variance by $\nu$ . The likelihood of. $u_{i}$ being observed is defined as the probability density function for $X$ when $X=u_{i}$ This is  

$$
\frac{1}{\sqrt{2\pi\nu}}\exp\left(\frac{-u_{i}^{2}}{2\nu}\right)
$$  

The likelihood of $m$ observations occurring in the order in which they are observed is  

$$
\prod_{i=1}^{m}\left[\frac{1}{\sqrt{2\pi\nu}}\exp{\left(\frac{-u_{i}^{2}}{2\nu}\right)}\right]
$$  

Using the maximum likelihood method, the best estimate of $\nu$ is the value that maximizes this expression.  

Maximizing an expression is equivalent to maximizing the logarithm of the expres-. sion. Taking logarithms of the expression in equation (23.10) and ignoring constant multiplicative factors, it can be seen that we wish to maximize.  

$$
\sum_{i=1}^{m}\left[-\ln(\nu)-\frac{u_{i}^{2}}{\nu}\right]
$$  

or  

$$
-m\ln(\nu)-\sum_{i=1}^{m}\frac{u_{i}^{2}}{\nu}
$$  

Differentiating this expression with respect to. $\nu$ and setting the resulting equation to zero, we see that the maximum likelihood estimator of $\nu$ is  

$$
\frac{1}{m}\sum_{i=1}^{m}u_{i}^{2}
$$  

# Estimating EWMA or GARCH (1,1) Parameters  

We now consider how the maximum likelihood method can be used to estimate the parameters when EWMA, GARCH (1,1), or some other volatility updating scheme is used. Define $\nu_{i}=\sigma_{i}^{2}$ as the variance estimated for day $i$ Assume that the probability distribution of $u_{i}$ conditional on the variance is normal. A similar analysis to the one just given shows the best parameters are the ones that maximize  

$$
\prod_{i=1}^{m}\left[\frac{1}{\sqrt{2\pi\nu_{i}}}\exp\left(\frac{-u_{i}^{2}}{2\nu_{i}}\right)\right]
$$  

Taking logarithms, we see that this is equivalent to maximizing  

$$
\sum_{i=1}^{m}\left[-\mathrm{ln}(\nu_{i})-\frac{u_{i}^{2}}{\nu_{i}}\right]
$$  

This is the same as the expression in equation (23.11), except that $\nu$ is replaced by $\nu_{i}.$ It is necessary to search iteratively to find the parameters in the model that maximize the expression in equation (23.12).  

The spreadsheet in Table 23.1 indicates how the calculations could be organized for. the GARCH(1,1) model. The table analyzes data on the S&P 500 between July 10, 2015, and July 9, 2020.10 The first column in the table records the date. The second column counts the days. The third column shows the S&P. $500,S_{i},$ at the end of day i. The fourth. column shows the proportional change in the S&P 500 between the end of day. $i-1$ and the end of day i. This is. $u_{i}=(S_{i}-S_{i-1})/S_{i-1}$  

We start by storing trial values for $\omega,\alpha$ , and $\beta$ in cells of the spreadsheet. We use an iterative procedure to move from these values to optimal values. The fifth column shows the estimate of the variance rate,. $\nu_{i}=\sigma_{i}^{2}$ , for day $i$ made at the end of day. $i-1$ . On day 3, we start things off by setting the variance equal to $u_{2}^{2}$ On subsequent days, equation (23.9) is used with the current values of $\omega,\alpha$ , and $\beta$ . The sixth column tabulates the likelihood measure, $-\ln(\nu_{i})-u_{i}^{2}/\nu_{i},$ The iterative search procedure chooses $\omega,\alpha$ , and $\beta$ to maximize the sum of the numbers in the sixth column.11  

Table 23.1 Estimation of Parameters in GARCH(1,1) Model for S&P 500 between July 10, 2015, and July 9, 2020.   


<html><body><table><tr><td>Date</td><td>Day i</td><td>Si</td><td>ui</td><td>Vi= 02</td><td>-ln(vi) -u²/vi</td><td></td></tr><tr><td>10-Jul-2015</td><td>1</td><td>2076.62</td><td></td><td></td><td></td><td></td></tr><tr><td>13-Jul-2015</td><td>2</td><td>2099.60</td><td>0.011066</td><td></td><td></td><td></td></tr><tr><td>14-Jul-2015</td><td>3</td><td>2108.95</td><td>0.004453</td><td>0.00012246</td><td></td><td>8.8458</td></tr><tr><td>15-Jul-2015</td><td>4</td><td>2107.40</td><td>-0.000735</td><td>0.00009997</td><td></td><td>9.2053</td></tr><tr><td>16-Jul-2015</td><td>5</td><td>2124.29</td><td>0.008015</td><td>0.00007884</td><td></td><td>8.6333</td></tr><tr><td>17-Jul-2015</td><td>6</td><td>2126.64</td><td>0.001106</td><td>0.00007729</td><td></td><td>9.4521</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>8-Jul-2020</td><td>1258</td><td>3169.94</td><td>0.007827</td><td>0.00016729</td><td></td><td>8.3295</td></tr><tr><td>9-Jul-2020</td><td>1259</td><td>3152.05</td><td>-0.005644</td><td>0.00014276</td><td></td><td>8.6313</td></tr></table></body></html>  

In our example, the optimal values of the parameters turn out to be  

$$
\omega=0.0000039818,\alpha=0.223793,\beta=0.747577
$$  

and the maximum value of the function in equation (23.12) is 10,837.4227. The. numbers shown in Table 23.1 were calculated on the final iteration of the search for the optimal $\omega,\alpha$ and $\beta$  

The long-term variance rate, $V_{L}$ , in our example is.  

$$
{\frac{\omega}{1-\alpha-\beta}}={\frac{0.0000039818}{0.02863}}=0.0001391
$$  

The long-term volatility is $\sqrt{0.0001391}$ , or $1.179\%$ , per day.  

Figures 23.1 and 23.2 show the S&P 500 index and its GARCH(1,1) volatility during the 5-year period covered by the data. Most of the time, the volatility was less than $2\%$ per day, but volatilities as high as $8\%$ per day were experienced in March 2020.  

An alternative approach to estimating parameters in GARCH(1,1), which is sometimes more robust, is known as variance targeting.12 This involves setting the long-run. average variance rate, $V_{L}$ equal to the sample variance calculated from the data (or to some other value that is believed to be reasonable). The value of. $\omega$ then equals $V_{L}(1-\alpha-\beta)$ and only two parameters (. $\alpha$ and $\beta$ ) have to be estimated. For the data. in Table 23.1, the sample variance is 0.0001490, which gives a daily volatility of. $1.2208\%$ Setting $V_{L}$ equal to the sample variance, the values of. $\alpha$ and $\beta$ that maximize the objective function in equation (23.12) are 0.22636 and 0.74704, respectively. The value of the objective function is 10,837.4047, only marginally below the value of 10,837.4227 obtained using the earlier procedure..  

When the EWMA model is used, the estimation procedure is relatively simple. We set $\omega=0,\alpha=1-\lambda$ , and $\beta=\lambda$ , and only one parameter has to be estimated. In the data in Table 23.1, the value of $\lambda$ that maximizes the objective function in equation (23.12) is. 0.9182 and the value of the objective function is 10,692.6213.  

![](adfe20a83a00c243b3d31145aae103b252214ffa9eae90c73fc5f73854f83bb3.jpg)  
Figure 23.1 S&P 500 index: July 10, 2015, to July 9, 2020.  

For both GARCH (1,1) and EWMA, we can use the Solver routine in Excel to search for the values of the parameters that maximize the likelihood function. The routine works well provided that the spreadsheet is structured so that the parameters being searched for have roughly equal values. For example, in GARCH (1,1) we could let cells A1, A2, and A3 contain $\omega\times10^{5}$ $10\alpha$ , and $\beta$ . We could then set. $\mathbf{B}1=\mathbf{A}1/100{,}000$ $\mathrm{B}2=\mathrm{A}2/10$ , and $\mathrm{B}3=\mathrm{A}3$ . We would use B1, B2, and B3 to calculate the likelihood function. We would ask Solver to calculate the values of A1, A2, and A3 that maximize the likelihood function. Occasionally Solver gives a local maximum, so testing a number of different starting values for parameters is a good idea.  

![](5a9de376f586582fc41fd18f9eb65ee483274b8fd68676a2a1d755e689aacaeb.jpg)  
Figure 23.2Volatility ( $\%$ per day) of S&P 500 index: July 10, 2015, to July 9, 2020.  

# How Good Is the Model?  

The assumption underlying a GARCH model is that volatility changes with the passage of time. During some periods volatility is relatively high; during other periods it is relatively low. To put this another way, when $u_{i}^{2}$ is high, there is a tendency for $u_{i+1}^{2}$ $u_{i+2}^{2}$ ,... to be high; when $u_{i}^{2}$ is low, there is a tendency for $u_{i+1}^{2},u_{i+2}^{2}$ ,... to be low. We can test how true this is by examining the autocorrelation structure of the $u_{i}^{2}$  

Let us assume the $u_{i}^{2}$ do exhibit autocorrelation. If a GARCH model is working well, it should remove the autocorrelation. We can test whether it has done so by considering the autocorrelation structure for the variables. $u_{i}^{2}/\sigma_{i}^{2}$ . If these show very little autocorrelation,. our model for $\sigma_{i}$ has succeeded in explaining autocorrelations in the $u_{i}^{2}$  

Table 23.2 shows results for the S&P 500 data used above. The first column shows the lags considered when the autocorrelation is calculated. The second shows autocorrela-. tions for $u_{i}^{2}$ ; the third shows autocorrelations for $u_{i}^{2}/\sigma_{i}^{2}$ 13 The table shows that the. autocorrelations are positive for $u_{i}^{2}$ for all lags between 1 and 15. In the case of. $u_{i}^{2}/\sigma_{i}^{2}$ some of the autocorrelations are positive and some are negative. They are all much. smaller in magnitude than the autocorrelations for $u_{i}^{2}$  

The GARCH model appears to have done a good job in explaining the data. For a more scientific test, we can use what is known as the Ljung-Box statistic.14 If a certain series has $m$ observations the Ljung-Box statistic is  

$$
m\sum_{k=1}^{K}w_{k}\eta_{k}^{2}
$$  

Table 23.2 Autocorrelations before and after the use of a GARCH model for S&P 500 data.   


<html><body><table><tr><td>Timelag</td><td>Autocorrelation for u?</td><td>Autocorrelation for u²/o²</td></tr><tr><td>1</td><td>0.537</td><td>0.022</td></tr><tr><td>2</td><td>0.556</td><td>-0.014</td></tr><tr><td>3</td><td>0.352</td><td>-0.001</td></tr><tr><td>4</td><td>0.351</td><td>0.046</td></tr><tr><td>5</td><td>0.334</td><td>-0.025</td></tr><tr><td>6</td><td>0.413</td><td>-0.005</td></tr><tr><td>7</td><td>0.326</td><td>-0.035</td></tr><tr><td>8</td><td>0.353</td><td>-0.023</td></tr><tr><td>9</td><td>0.295</td><td>0.000</td></tr><tr><td>10</td><td>0.259</td><td>0.064</td></tr><tr><td>11</td><td>0.233</td><td>-0.012</td></tr><tr><td>12</td><td>0.168</td><td>-0.024</td></tr><tr><td>13</td><td>0.169</td><td>-0.009</td></tr><tr><td>14</td><td>0.168</td><td>0.010</td></tr><tr><td>15</td><td>0.200</td><td>-0.005</td></tr></table></body></html>

13 For a series $x_{i}.$ the autocorrelation with a lag of $k$ is the coefficient f correlation between $x_{i}$ and $x_{i+k}$ 14 See G. M. Ljung and G.E. P. Box, "On a Measure of Lack of Fit in Time Series Models" Biometrica, 65 (1978): 297-303.  

where $\eta_{k}$ is the autocorrelation for a lag of $k$ $K$ is the number of lags considered, and  

$$
w_{k}=\frac{m+2}{m-k}
$$  

For $K=15$ , zero autocorrelation can be rejected with $95\%$ confidence when the Ljung-.   
Box statistic is greater than 25.  

From Table 23.2, the Ljung-Box statistic for the $u_{i}^{2}$ series is about 2,170. This is strong evidence of autocorrelation. For the $u_{i}^{2}/\sigma_{i}^{2}$ series, the Ljung-Box statistic is 13.2, suggesting that the autocorrelation has been largely removed by the GARCH model.  
