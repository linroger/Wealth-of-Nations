---
tags:
  - '#cash_flow_mapping'
  - '#correlation_matrix'
  - '#covariance_matrix'
  - '#interest_rate_risk'
  - '#linear_model'
  - '#options_delta'
  - '#portfolio_variance'
  - '#risk_management'
  - '#var_es_calculation'
---
# 22.4  THE LINEAR MODEL  

The examples we have just considered are simple illustrations of the use of the linear model for calculating VaR or ES. Suppose that we have a portfolio worth $P$ consisting of $n$ assets with an amount $\alpha_{i}$ being invested in asset $i$ $(1\leq i\leq n)$ . Define $\Delta x_{i}$ as the return on asset $i$ in one day. The dollar change in the value of the investment in asset $i$ in one day is $\alpha_{i}\Delta x_{i}$ and  

$$
\Delta P=\sum_{i=1}^{n}\alpha_{i}\Delta x_{i}
$$  

where $\Delta P$ is the dollar change in the value of the whole portfolio in one day.  

In the example considered in the previous section,. $\$10$ million was invested in the first. asset (Microsoft) and $\$5$ million was invested in the second asset (AT&T), so that (in millions of dollars) $\alpha_{1}=10,\alpha_{2}=5$ , and  

$$
\Delta P=10\Delta x_{1}+5\Delta x_{2}
$$  

If we assume that the. $\Delta x_{i}$ in equation (22.2) are multivariate normal, then. $\Delta P$ is normally distributed. To calculate VaR or ES, we therefore need to calculate only the mean and standard deviation of. $\Delta P$ We assume, as discussed in the previous section, that the expected value of each. $\Delta x_{i}$ is zero. This implies that the mean of. $\Delta P$ is zero.  

To calculate the standard deviation of $\Delta P$ , we define $\sigma_{i}$ as the daily volatility of the ith asset and $\rho_{i j}$ as the coefficient of correlation between returns on asset $i$ and asset $j$ This means that $\sigma_{i}$ is the standard deviation of $\Delta x_{i},$ and $\rho_{i j}$ is the coefficient of correlation between $\Delta x_{i}$ and $\Delta x_{j}.$ The variance of $\Delta P$ , which we will denote by $\sigma_{P}^{2}$ is given by  

$$
\sigma_{P}^{2}=\sum_{i=1}^{n}\sum_{j=1}^{n}\rho_{i j}\alpha_{i}\alpha_{j}\sigma_{i}\sigma_{j}
$$  

This equation can also be written as  

$$
\sigma_{P}^{2}=\sum_{i=1}^{n}\alpha_{i}^{2}\sigma_{i}^{2}+2\sum_{i=1}^{n}\sum_{j<i}\rho_{i j}\alpha_{i}\alpha_{j}\sigma_{i}\sigma_{j}
$$  

The standard deviation of the change over $N$ days is $\sigma_{P}\sqrt{N}$ , and the $99\%$ VaR for an $N$ -day time horizon is. $2.326\sigma_{P}\sqrt{N}$  

The portfolio return in one day is. $\Delta P/P.$ From equation (22.3), the variance of this is  

$$
\sum_{i=1}^{n}\sum_{j=1}^{n}\rho_{i j}w_{i}w_{j}\sigma_{i}\sigma_{j}
$$  

where $w_{i}=\alpha_{i}/P$ is the weight of the ith investment in the portfolio. This version of equation (22.3) is the one usually used by portfolio managers..  

In the example considered in the previous section, $\sigma_{1}=0.02,\sigma_{2}=0.01$ ,and $\rho_{12}=0.3$ As already noted, $\alpha_{1}=10$ and $\alpha_{2}=5$ , so that from equation (22.3)  

$$
\sigma_{P}^{2}=10^{2}\times0.02^{2}+5^{2}\times0.01^{2}+2\times10\times5\times0.3\times0.02\times0.01=0.0485
$$  

and $\sigma_{P}=0.2202$ . This is the standard deviation of the change in the portfolio value per day (in millions of dollars). The ten-day. $99\%$ VaR is $2.326\times\dot{0}.2202\times\sqrt{10}^{\textmd{\textperthousand}}$ $\$1.62$ million. This agrees with the calculation in the previous section..  

# Correlation and Covariance Matrices  

A correlation matrix is a matrix where the entry in the ith row and jth column is the correlation $\rho_{i j}$ between variable $i$ and $j$ It is shown in Table 22.5. Since a variable is always perfectly correlated with itself, the diagonal elements of the correlation matrix are 1. Furthermore, because. $\rho_{i j}=\rho_{j i}$ the correlation matrix is symmetric. The.  

Table 22.5 A correlation matrix: $\rho_{i j}$ is the correlation between variable $i$ and variable $j$  

$$
\left[\begin{array}{c c c c c c}{1}&{\rho_{12}}&{\rho_{13}}&{\cdot\cdot\cdot}&{\rho_{1n}}\ {\rho_{21}}&{1}&{\rho_{23}}&{\cdot\cdot\cdot}&{\rho_{2n}}\ {\rho_{31}}&{\rho_{32}}&{1}&{\cdot\cdot\cdot}&{\rho_{3n}}\ {\vdots}&{\vdots}&{\vdots}&{\vdots}&{\vdots}\ {\rho_{n1}}&{\rho_{n2}}&{\rho_{n3}}&{\cdot\cdot\cdot}&{\vdots}\end{array}\right]
$$  

$$
\left[\begin{array}{c c c c c c}{\mathbf{var}_{1}}&{\mathbf{cov}_{12}}&{\mathbf{cov}_{13}}&{\cdots}&{\mathbf{cov}_{1n}}\ {\mathbf{cov}_{21}}&{\mathbf{var}_{2}}&{\mathbf{cov}_{23}}&{\cdots}&{\mathbf{cov}_{2n}}\ {\mathbf{cov}_{31}}&{\mathbf{cov}_{32}}&{\mathbf{var}_{3}}&{\cdots}&{\mathbf{cov}_{3n}}\ {\vdots}&{\vdots}&{\vdots}&{\vdots}&{\vdots}\ {\mathbf{c}}&{\mathbf{vav}_{n1}}&{\mathbf{cov}_{n2}}&{\mathbf{cov}_{n3}}&{\cdots}&{\mathbf{var}_{n}}\end{array}\right]
$$  

correlation matrix, together with the daily standard deviations of the variables, enables the portfolio variance to be calculated using equation (22.3)..  

Instead of working with correlations and volatilities, analysts often use variances and covariances. The daily variance $\mathbf{Var}_{i}$ of variable $i$ is the square of its daily volatility:  

$$
\mathrm{var}_{i}=\sigma_{i}^{2}
$$  

The covariance. $\mathbf{cov}_{i j}$ between variable $i$ and variable. $j$ is the product of the daily volatility of variable $i$ , the daily volatility of variable $j_{:}$ and the correlation between $i$ and $j$  

$$
\mathrm{cov}_{i j}=\sigma_{i}\sigma_{j}\rho_{i j}
$$  

The equation for the variance of the portfolio in equation (22.3) can be written  

$$
\sigma_{P}^{2}=\sum_{i=1}^{n}\sum_{j=1}^{n}\mathrm{cov}_{i j}\alpha_{i}\alpha_{j}
$$  

In a covariance matrix, the entry in the ith row and. $j$ th column is the covariance. between variable $i$ and variable $j.$ As just mentioned, the covariance between a. variable and itself is its variance. The diagonal entries in the matrix are therefore. variances (see Table 22.6). For this reason, the covariance matrix is sometimes called the variance-covariance matrix. (Like the correlation matrix, it is symmetric.) Using matrix notation, the equation for the variance of the portfolio just given becomes.  

$$
\sigma_{P}^{2}=\alpha^{\mathsf{T}}C\alpha
$$  

where $\alpha$ is the (column) vector whose ith element is $\alpha_{i},C$ is the variance-covariance matrix, and $\upalpha^{\intercal}$ is the transpose of $\alpha$  

# The Four-Index Example  

We now return to the four-index example in Section 22.2. This involved the portfolio in Table 22.1. Data and calculations presented here can be found on the author's website..  

The correlations that would be calculated on July 8, 2020, from the previous 500. returns are shown in Table 22.7 and the covariance matrix is shown in Table 22.8. From equation (22.4), the covariance matrix gives the variance of portfolio gains/losses $(\$0000s)$ as 14,406.193. The standard deviation of portfolio gains/losses is the square root of this, or 120.03. The 1-day $99\%$ VaR in $\$000$ is therefore $2.326\times120.03=279.222$ and the 1-day $99\%$ ES in $\$000$ is, from equation (22.1), 319.894. These values are much lower than the values given by the historical simulation approach. This is because the latter are greatly affected by a handful of large losses occurring in March 2020.  

In the next chapter we will see how the weights given to observations can decline as. the observations become older when the volatilities and correlations are calculated in the model-building approach.  

# Handling Interest Rates  

It is out of the question in the model-building approach to define a separate market variable for every single bond price or interest rate to which a company is exposed. Some simplifications are necessary when the model-building approach is used. One possibility is to assume that only parallel shifts in the yield curve occur. It is then necessary to define only one market variable: the size of the parallel shift. The changes in the value of a bond portfolio can then be calculated using the duration relationship  

Table 22.7 Correlation matrix on July 8, 2020: variable 1 is S&P500; variable 2 is. FTSE 100; variable 3 is CAC 40; variable 4 is Nikkei 225. All indices are total return indices.   


<html><body><table><tr><td>1</td><td>0.415</td><td>0.694</td><td>0.368</td></tr><tr><td>0.415</td><td>1</td><td>0.656</td><td>0.566</td></tr><tr><td>0.694</td><td>0.656</td><td>1</td><td>0.482</td></tr><tr><td>0.368</td><td>0.566</td><td>0.482</td><td>1</td></tr></table></body></html>  

<html><body><table><tr><td>0.000275</td><td>0.000094</td><td>0.000177</td><td>0.000080</td></tr><tr><td>0.000094</td><td>0.000187</td><td>0.000138</td><td>0.000102</td></tr><tr><td>0.000177</td><td>0.000138</td><td>0.000237</td><td>0.000097</td></tr><tr><td>0.000080</td><td>0.000102</td><td>0.000097</td><td>0.000173</td></tr><tr><td></td><td></td><td></td><td></td></tr></table></body></html>  

$$
\Delta P=-D P\Delta y
$$  

where $P$ is the value of the portfolio, $\Delta P$ is the change in $P$ in one day, $D$ is the modified duration of the portfolio, and $\Delta y$ is the parallel shift in 1 day.  

This approach does not usually give enough accuracy. The procedure usually followed is to choose as market variables the prices of zero-coupon bonds with standard maturities: 1 month, 3 months, 6 months, 1 year, 2 years, 5 years, 7 years, 10 years, and 30 years. For the purposes of calculating VaR or ES, the cash flows from instruments in the portfolio are mapped into cash flows occurring on the standard maturity dates. Consider a $\$1$ million position in a Treasury bond lasting 1.2 years that pays a coupon of $6\%$ semiannually. Coupons are paid in 0.2, 0.7, and 1.2 years, and the principal is. paid in 1.2 years. This bond is, therefore, in the first instance regarded as a $\$30,000$ position in 0.2-year zero-coupon bond plus a $\$30,000$ position in a 0.7-year zerocoupon bond plus a $\$1.03$ million position in a 1.2-year zero-coupon bond. The position in the 0.2-year bond is then replaced by an approximately equivalent position in 1-month and 3-month zero-coupon bonds; the position in the 0.7-year bond is. replaced by an approximately equivalent position in 6-month and 1-year zero-coupon bonds; and the position in the 1.2-year bond is replaced by an approximately equivalent position in 1-year and 2-year zero-coupon bonds. The result is that the position in the 1.2-year coupon-bearing bond is regarded as a position in zero-coupon bonds having. maturities of 1 month, 3 months, 6 months, 1 year, and 2 years.  

This procedure is known as cash-flow mapping. One way of doing it is explained in Technical Note 25 at www-2.rotman.utoronto.ca/\~hull/TechnicalNotes. Note that cash-flow mapping is not necessary when the historical simulation approach is used. This is because the complete term structure of interest rates can be calculated from the variables that are considered for each of the scenarios generated by using the bootstrap method in Chapter 4.  

# Applications of the Linear Model  

The simplest application of the linear model is to a portfolio with no derivatives consisting of positions in stocks and bonds. Cash-flow mapping converts the bonds to. zero-coupon bonds with standard maturities. The change in the value of the portfolio is linearly dependent on the returns on the stocks and these zero-coupon bonds.  

Another instrument that can be handled by the linear model is a forward contract to buy or sell foreign currency at a future time T. The contract can be regarded as the exchange of a foreign zero-coupon bond maturing at time. $T$ for a domestic zero-coupon bond maturing at time T. For the purposes of calculating VaR or ES, the forward. contract is therefore treated as a long position in the foreign bond combined with a short position in the domestic bond. Each bond is handled using a cash-flow mapping. procedure.  

An overnight indexed swap (OIS) can also be handled using the linear model. It can. be regarded as the exchange of a fixed-rate bond for a floating-rate bond. The floating-. rate bond has a known value, which is the amount the notional principal would become if it were invested at overnight rates for a period of time starting at the last reset date.. The fixed-rate bond can be handled using cash-flow mapping procedures..  

# The Linear Model and Options  

We now consider how we might try to use the linear model when there are options. Consider first a portfolio consisting of options on a single stock whose current price is $S$ Suppose that the delta of the position (calculated in the way described in Chapter 19) is 8.' Since $\delta$ is the rate of change of the value of the portfolio with. $S$ , it is approximately true that  

$$
\delta={\frac{\Delta P}{\Delta S}}
$$  

or  

$$
\Delta P=\delta\Delta S
$$  

where $\Delta S$ is the dollar change in the stock price in 1 day and $\Delta P$ is, as usual, the dollar change in the portfolio in 1 day. Define $\Delta x$ as the percentage change in the stock price in 1 day, so that  

$$
\Delta x={\frac{\Delta S}{S}}
$$  

It follows that an approximate relationship between $\Delta P$ and $\Delta x$ is  

$$
\Delta P=S\delta\Delta x
$$  

When we have a position in several underlying market variables that includes options, we can derive an approximate linear relationship between. $\Delta P$ and the $\Delta x_{i}$ similarly. This relationship is  

$$
\Delta P=\sum_{i=1}^{n}S_{i}\delta_{i}\Delta x_{i}
$$  

where $S_{i}$ is the value of the ith market variable and $\delta_{i}$ is the delta of the portfolio with respect to the ith market variable. This corresponds to equation (22.2):  

$$
\Delta P=\sum_{i=1}^{n}\alpha_{i}\Delta x_{i}
$$  

with $\alpha_{i}=S_{i}\delta_{i} $ Equation (22.3) or (22.4) can therefore be used to calculate the standard deviation of $\Delta P$  

# Example 22.1  

A portfolio consists of options on Microsoft and AT&T. The options on Microsoft have a delta of 1,000, and the options on AT&T have a delta of 20,000. The Microsoft share price is $\$120$ , and the AT&T share price is $\$30$ . From equation (22.6), it is approximately true that  

$$
\Delta P=120\times1.000\times\Delta x_{1}+30\times20.000\times\Delta x_{2}
$$  

or  

$$
\Delta P=120,000\Delta x_{1}+600,000\Delta x_{2}
$$  

where $\Delta x_{1}$ and $\Delta x_{2}$ are the returns from Microsoft and AT&T in 1 day and. $\Delta P$ is the resultant change in the value of the portfolio. (The portfolio is assumed to be equivalent to an investment of $\$120,000$ in Microsoft and $\$600,000$ in AT&T.) Assuming that the daily volatility of Microsoft is $2\%$ and the daily volatility of AT&T is $1\%$ and the correlation between the daily changes is 0.3, the standard deviation of $\Delta P$ (in thousands of dollars) is  

$$
{\sqrt{(120\times0.02)^{2}+(600\times0.01)^{2}+2\times120\times0.02\times600\times0.01\times0.3}}=7.099
$$  
