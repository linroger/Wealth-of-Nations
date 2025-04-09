# 23.7 CORRELATIONS  

The discussion so far has centered on the estimation and forecasting of volatility. As explained in Chapter 22, correlations also play a key role in the calculation of VaR. In this section, we show how correlation estimates can be updated in a similar way to volatility estimates.  

The correlation between two variables $X$ and $Y$ can be defined as.  

$$
\frac{\mathsf{c o v}(X,Y)}{\sigma_{X}\sigma_{Y}}
$$  

where $\sigma_{X}$ and $\sigma_{Y}$ are the standard deviations of $X$ and $Y$ and $\operatorname{cov}(X,Y)$ is the covariance between $X$ and $Y$ The covariance between $X$ and $Y$ is defined as.  

$$
E[(X-\mu_{X})(Y-\mu_{Y})]
$$  

where $\mu_{X}$ and $\mu_{Y}$ are the means of $X$ and $Y$ and $E$ denotes the expected value. Although it is easier to develop intuition about the meaning of a correlation than it is for a covariance, it is covariances that are the fundamental variables of our analysis.15.  

Define $x_{i}$ and $y_{i}$ as the percentage changes in $X$ and $Y$ between the end of day $i\textrm{--}1$ and the end of day. $i$  

$$
x_{i}=\frac{X_{i}-X_{i-1}}{X_{i-1}},~y_{i}=\frac{Y_{i}-Y_{i-1}}{Y_{i-1}}
$$  

where $X_{i}$ and $Y_{i}$ are the values of $X$ and $Y$ at the end of day $i$ . We also define the following:  

$\sigma_{x,n}$ : Daily volatility of variable $X$ , estimated for day $n$   
$\sigma_{y,n}$ : Daily volatility of variable $Y$ estimated for day $n$   
$\operatorname{cov}_{n}$ : Estimate of covariance between daily changes in $X$ and $Y.$ calculated on day $n$  

The estimate of the correlation between $X$ and $Y$ on day $n$ is  

$$
\frac{\mathrm{cov}_{n}}{\sigma_{x,n}\sigma_{y,n}}
$$  

Using equal weighting and assuming that the means of $x_{i}$ and $y_{i}$ are zero, equation (23.3) shows that the variance rates of $X$ and $Y$ can be estimated from the most recent. $m$ observations as  

$$
\sigma_{x,n}^{2}=\frac{1}{m}\sum_{i=1}^{m}x_{n-i}^{2},\qquad\sigma_{y,n}^{2}=\frac{1}{m}\sum_{i=1}^{m}y_{n-i}^{2}
$$  

A similar estimate for the covariance between $X$ and $Y$ is  

$$
\operatorname{cov}_{n}={\frac{1}{m}}\sum_{i=1}^{m}x_{n-i}y_{n-i}
$$  

One alternative for updating covariances is an EWMA model similar to equation (23.7). The formula for updating the covariance estimate is then  

$$
\mathsf{c o v}_{n}=\lambda\mathsf{c o v}_{n-1}+(1-\lambda)x_{n-1}y_{n-1}
$$  

A similar analysis to that presented for the EwMA volatility model shows that the weights given to observations on the $x_{i}y_{i}$ decline as we move back through time. The lower the value of $\lambda$ , the greater the weight that is given to recent observations.  

# Example 23.3  

Suppose that $\lambda=0.95$ and that the estimate of the correlation between two variables $X$ and $Y$ on day $n\mathrm{~-~}1$ is 0.6. Suppose further that the estimate of the volatilities for the $X$ and $Y$ on day $n\mathrm{~-~}1$ are $1\%$ and $2\%$ , respectively. From the relationship between correlation and covariance, the estimate of the covariance between the $X$ and $Y$ on day $n\mathrm{~-~}1$ is  

$$
0.6\times0.01\times0.02=0.00012
$$  

Suppose that the percentage changes in. $X$ and $Y$ on day $n\mathrm{~-~}1$ are $0.5\%$ and $2.5\%$ respectively. The variance and covariance for day $n$ would be updated as follows:  

$$
\begin{array}{l}{{\sigma_{x,n}^{2}=0.95\times0.01^{2}+0.05\times0.005^{2}=0.00009625}}\ {{\sigma_{y,n}^{2}=0.95\times0.02^{2}+0.05\times0.025^{2}=0.00041125}}\end{array}
$$  

$$
\mathsf{c o v}_{n}=0.95\times0.00012+0.05\times0.005\times0.025=0.00012025
$$  

The new volatility of. $X$ is $\sqrt{0.00009625}=0.981\%$ and the new volatility of $Y$ is $\sqrt{0.00041125}=\dot{2}.028\%$ The new coefficient of correlation between $X$ and $Y$ is  

$$
\frac{0.00012025}{0.00981\times0.02028}=0.6044
$$  

GARCH models can also be used for updating covariance estimates and forecasting the future level of covariances. For example, the GARCH(1,1) model for updating a covariance is  

$$
\mathrm{cov}_{n}=\omega+\alpha x_{n-1}y_{n-1}+\beta\mathrm{cov}_{n-1}
$$  

and the long-term average covariance is $\omega/(1-\alpha-\beta) $ Formulas similar to those in  

equations (23.13) and (23.14) can be developed for forecasting future covariances and calculating the average covariance during the life of an option.16  

# Consistency Condition for Covariances  

Once all the variances and covariances have been calculated, a variance-covariance matrix can be constructed. As explained in Section 22.4, when $i\neq j,$ the $(i,j)$ th element of this matrix shows the covariance between variable $i$ and variable $j.$ When $i=j$ it shows the variance of variable $i$  

Not all symmetric variance-covariance matrices are internally consistent. The condition for an $N\times N$ variance-covariance matrix $\Omega$ to be internally consistent is  

$$
w^{\top}\Omega w\geq0
$$  

for all $N\times1$ vectors $w$ , where $w^{\mathsf{T}}$ is the transpose of. $w$ . A matrix that satisfies this.   
property is known as positive-semidefinite.  

To understand why the condition in equation (23.17) must hold, suppose that $w^{\top}$ is $[w_{1},w_{2},~.~.~.~,w_{n}].$ The expression $w^{\top}\Omega w$ is the variance of $w_{1}x_{1}+w_{2}x_{2}+\cdots+w_{n}x_{n} $ where $x_{i}$ is the value of variable $i.$ As such, it cannot be negative.  

To ensure that a positive-semidefinite matrix is produced, variances and covariances should be calculated consistently. For example, if variances are calculated by giving equal weight to the last $m$ data items, the same should be done for covariances. If variances are. updated using an EWMA model with $\lambda=0.94$ , the same should be done for covariances.  

An example of a variance-covariance matrix that is not internally consistent is  

$$
\left[{\begin{array}{c c c}{1}&{0}&{0.9}\ {0}&{1}&{0.9}\ {0.9}&{0.9}&{1}\end{array}}\right]
$$  

The variance of each variable is 1.0, and so the covariances are also coefficients of correlation. The first variable is highly correlated with the third variable and the second variable is highly correlated with the third variable. However, there is no correlation at all between the first and second variables. This seems strange. When. $w$ is set equal to $(1,1,-1)$ , the condition in equation (23.17) is not satisfied, proving that the matrix is. not positive-semidefinite.17  

# SUMMARY  

Most popular option pricing models, such as Black-Scholes-Merton, assume that the. volatility of the underlying asset is constant. This assumption is far from perfect. In practice, the volatility of an asset, like the asset's price, is a stochastic variable. Unlike the asset price, it is not directly observable. This chapter has discussed procedures for attempting to keep track of the current level of volatility..  

We define $u_{i}$ as the percentage change in a market variable between the end of. day $i-1$ and the end of day i. The variance rate of the market variable (that is, the. square of its volatility) is calculated as a weighted average of the. $u_{i}^{2}$ . The key feature of the procedures that have been discussed here is that they do not give equal weight to. the observations on the $u_{i}^{2}$ . The more recent an observation, the greater the weight assigned to it. In the EWMA and the GARCH(1,1) models, the weights assigned to. observations decrease exponentially as the observations become older. The GARCH(1,1) model differs from the EWMA model in that some weight is also assigned to the long-run average variance rate. It has a structure that enables forecasts of the future level of variance rate to be produced relatively easily.  

Maximum likelihood methods are usually used to estimate parameters from historical. data in the EWMA, GARCH(1,1), and similar models. These methods involve using an. iterative procedure to determine the parameter values that maximize the chance or likelihood that the historical data will occur. Once its parameters have been determined, a GARCH(1,1) model can be judged by how well it removes autocorrelation from the. $u_{i}^{2}$  

For every model that is developed to track variances, there is a corresponding model. that can be developed to track covariances. The procedures described here can therefore be used to update the complete variance-covariance matrix used in value at risk calculations.  

# FURTHER READING  

Bollerslev, T. "Generalized Autoregressive Conditional Heteroscedasticity, Journal of Econometrics, 31 (1986): 307-27.   
Cumby, R., S. Figlewski, and J. Hasbrook. "Forecasting Volatilities and Correlations with EGARCH Models," Journal of Derivatives, 1, 2 (Winter 1993): 51-63.   
Engle, R. F. "Autoregressive Conditional Heteroscedasticity with Estimates of the Variance of U.K. Inflation," Econometrica 50 (1982): 987-1008.   
Engle R. F., and J. Mezrich. "Grappling with GARCH," Risk, September 1995: 112-117.   
Engle, R. F., and J. Mezrich, "GARCH for Groups," Risk, August 1996: 36-40.   
Engle, R. F., and V. Ng, "Measuring and Testing the Impact of News on Volatility," Journal of Finance, 48 (1993): 1749-78.   
Noh, J., R. F. Engle, and A. Kane. "Forecasting Volatility and Option Prices of the S&P 500 Index," Journal of Derivatives, 2 (1994): 17-30.  

# Practice Questions  

23.1. Explain the exponentially weighted moving average (EwMA) model for estimating volatility from historical data..   
23.2. What is the difference between the exponentially weighted moving average model and the GARCH(1,1) model for updating volatilities?   
23.3. The most recent estimate of the daily volatility of an asset is. $1.5\%$ and the price of the asset at the close of trading yesterday was. $\$30.00$ . The parameter $\lambda$ in the EWMA model  

is 0.94. Suppose that the price of the asset at the close of trading today is $\$30.50$ . How will this cause the volatility to be updated by the EWMA model?  

23.4. A company uses an EwMA model for forecasting volatility. It decides to change the parameter $\lambda$ from 0.95 to 0.85. Explain the likely impact on the forecasts..  

23.5. The volatility of a certain market variable is $30\%$ per annum. Calculate a $99\%$ confidence interval for the size of the percentage daily change in the variable.  

23.6. A company uses the GARCH(1,1) model for updating volatility. The three parameters are $\omega,\alpha,$ and $\beta$ . Describe the impact of making a small increase in each of the parameters. while keeping the others fixed..  

23.7. The most recent estimate of the daily volatility of the U.S. dollar/sterling exchange rate is $0.6\%$ and the exchange rate at $4\mathrm{p.m}$ yesterday was 1.5000. The parameter $\lambda$ in the EWMA model is 0.9. Suppose that the exchange rate at $4\mathrm{p.m}$ . today proves to be 1.4950. How would the estimate of the daily volatility be updated?  

23.8. Assume that S&P 500 at close of trading yesterday was 3,040 and the daily volatility of the index was estimated as. $1\%$ per day at that time. The parameters in a GARCH(1,1) model are $\omega=0.000002$ $\alpha=0.06$ , and $\beta=0.92$ . If the level of the index at close of. trading today is 3,060, what is the new volatility estimate?.  

23.9. Suppose that the daily volatilities of asset A and asset B, calculated at the close of trading yesterday, are $1.6\%$ and $2.5\%$ , respectively. The prices of the assets at close of trading. yesterday were $\$20$ and $\$40$ and the estimate of the coefficient of correlation between the. returns on the two assets was 0.25. The parameter $\lambda$ used in the EWMA model is 0.95..  

(a) Calculate the current estimate of the covariance between the assets. (b) On the assumption that the prices of the assets at close of trading today are $\$20.5$ and $\$40.5$ , update the correlation estimate.   
23.10. The parameters of a GARCH(1,1) model are estimated as $\omega=0.000004$ $\alpha=0.05$ ,and $\beta=0.92$ What is the long-run average volatility and what is the equation describing the. way that the variance rate reverts to its long-run average? If the current volatility is $20\%$ per year, what is the expected volatility in 20 days?   
23.11. Suppose that the current daily volatilities of asset $\boldsymbol{\mathrm X}$ and asset $\mathrm{Y}$ are $1.0\%$ and $1.2\%$ respectively. The prices of the assets at close of trading yesterday were. $\$30$ and $\$50$ and the estimate of the coefficient of correlation between the returns on the two assets made at this time was 0.50. Correlations and volatilities are updated using a GARCH(1,1) model. The estimates of the model's parameters are $\alpha=0.04$ and $\beta=0.94$ For the correlation $\omega=0.000001$ , and for the volatilities $\omega=0.000003.$ If the prices of the two assets at close of trading today are $\$31$ and $\$51$ , how is the correlation estimate updated?.   
23.12. Suppose that the daily volatility of the FTSE 100 stock index (measured in pounds. sterling) is $1.8\%$ and the daily volatility of the dollar/sterling exchange rate is. $0.9\%$ Suppose further that the correlation between the FTSE 100 and the dollar/sterling exchange rate is 0.4. What is the volatility of the FTSE 100 when it is translated to U.S. dollars? Assume that the dollar/sterling exchange rate is expressed as the number of. U.S. dollars per pound sterling. (Hint: When. $Z=X Y$ the percentage daily change in. $Z$ is approximately equal to the percentage daily change in. $X$ plus the percentage daily. change in $Y$   
23.13. Suppose that in Problem 23.12 the correlation between the S&P 500 Index (measured in dollars) and the FTSE 100 Index (measured in sterling) is 0.7, the correlation between.  

the S&P 500 Index (measured in dollars) and the dollar/sterling exchange rate is 0.3, and the daily volatility of the S&P 500 index is. $1.6\%$ . What is the correlation between the. S&P 500 index (measured in dollars) and the FTSE 100 index when it is translated to dollars? (Hint: For three variables. $X,Y$ , and $Z$ the covariance between $X+Y$ and $Z$ equals the covariance between $X$ and $Z$ plus the covariance between $Y$ and $Z$  

23.14. Show that the GARCH (1,1) model. $\sigma_{n}^{2}=\omega+\alpha u_{n-1}^{2}+\beta\sigma_{n-1}^{2}$ in equation (23.9) is equivalent to the stochastic volatility model. $d V=a(V_{L}-V)d t+\xi V d z$ where time is measured in days,. $V$ is the square of the volatility of the asset price, and  

$$
a=1-\alpha-\beta,V_{L}=\frac{\omega}{1-\alpha-\beta},\xi=\alpha\sqrt{2}
$$  

What is the stochastic volatility model when time is measured in years? (Hint: The variable $u_{n-1}$ is the return on the asset price in time $\Delta t.$ It can be assumed to be normally distributed with mean zero and standard deviation $\sigma_{n-1}$ . It follows from the moments of the normal distribution that the mean and variance of $u_{n-1}^{2}$ are $\sigma_{n-1}^{2}$ and $2\sigma_{n-1}^{4}$ respectively.)  

23.15. Use the model-building approach in conjunction with the EWMA model to calculate VaR and ES for the four-index example in Chapter 22 when. $\lambda=0.94$  

23.16. What is the effect of changing $\lambda$ from 0.94 to 0.97 in Problem 23.15.  

23.17. Suppose that the price of gold at close of trading yesterday was $\$600$ and its volatility was estimated as $1.3\%$ per day. The price at the close of trading today is. $\$596$ . Update the volatility estimate using  

(a) The EWMA model with $\lambda=0.94$ (b) The GARCH(1,1) model with $\omega=0.000002.$ $\alpha=0.04$ , and $\beta=0.94$  

23.18. Suppose that in Problem 23.17 the price of silver at the close of trading yesterday was $\$16$ its volatility was estimated as $1.5\%$ per day, and its correlation with gold was estimated as 0.8. The price of silver at the close of trading today is unchanged at. $\$16$ . Update the volatility of silver and the correlation between silver and gold using the two models in Problem 23.17. In practice, is the $\omega$ parameter likely to be the same for gold and silver?  

23.19. An Excel spreadsheet containing over 900 days of daily data on a number of different exchange rates and stock indices can be downloaded from the author's website:  

www-2.rotman.utoronto.ca/\~hull/data.  

Choose one exchange rate and one stock index. Estimate the value of. $\lambda$ in the EWMA model that minimizes the value of $\Sigma_{i}(\nu_{i}-\beta_{i})^{2}$ , where $\nu_{i}$ is the variance forecast made at the end of day $i-1$ and $\beta_{i}$ is the variance calculated from data between day $i$ and day $i+25$ . Use the Solver tool in Excel. Set the variance forecast at the end of the first day. equal to the square of the return on that day to start the EWMA calculations.  

23.20. Estimate parameters for EWMA and GARCH(1,1) from data on the euro/USD exchange rate on the author's website:.  

www-2.rotman.utoronto.ca/\~hull/data.  

![](6736579988986b038b4cf287fe6b2a41c24ffaa672ab66927b768f2dc67cda7f.jpg)  
Credit Risk  

Most of the derivatives considered so far in this book have been concerned with market risk. In this chapter we consider another important risk for financial institutions: credit risk. Most financial institutions devote considerable resources to the measurement and management of credit risk. Regulators have for many years required banks to keep capital to reflect the credit risks they are bearing.  

Credit risk arises from the possibility that borrowers and counterparties in derivatives transactions may default. This chapter discusses a number of different approaches to estimating the probability that a company will default and explains the key difference between risk-neutral and real-world probabilities of default. It examines the nature of the credit risk in over-the-counter derivatives transactions and discusses the clauses derivatives dealers write into their derivatives agreements to reduce credit risk. It also covers default correlation, Gaussian copula models, and the estimation of credit value at risk.  

Chapter 25 will discuss credit derivatives and show how ideas introduced in this chapter can be used to value these instruments..  

# 24.1 CREDIT RATINGS  

Rating agencies, such as Moody's, S&P, and Fitch, are in the business of providing. ratings describing the creditworthiness of corporate bonds. The best rating assigned by Moody's is Aaa. Bonds with this rating are considered to have almost no chance of defaulting. The next best rating is Aa. Following that comes A, Baa, Ba, B, Caa, Ca, and C. Only bonds with ratings of Baa or above are considered to be investment grade. The S&P and Fitch ratings corresponding to Moody's Aaa, Aa, A, Baa, Ba, B, Caa,. Ca, and C are AAA, AA, A, BBB, BB, B, CCC, CC, and C, respectively. To create finer rating measures, Moody's divides its Aa rating category into Aa1, Aa2, and Aa3, its A category into A1, A2, and A3, and so on. Similarly, S&P and Fitch divide their AA rating category into ${\bf A}{\bf A}+$ , AA, and AA-, their A rating category into ${\bf A}+$ , A, and $\mathbf{A}-$ and so on. Moody's Aaa category and the S&P/Fitch AAA category are not sub-. divided, nor usually are the two lowest rating categories.  
