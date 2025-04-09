# 23.2 THE EXPONENTIALLY WEIGHTED MOVING AVERAGE MODEL  

The exponentially weighted moving average (EwMA) model is a particular case of the model in equation (23.4) where the weights. $\alpha_{i}$ decrease exponentially as we move back through time. Specifically, $\alpha_{i+1}=\lambda\alpha_{i}$ where $\lambda$ is a constant between 0 and 1.  

It turns out that this weighting scheme leads to a particularly simple formula for updating volatility estimates. The formula is.  

$$
\sigma_{n}^{2}=\lambda\sigma_{n-1}^{2}+(1-\lambda)u_{n-1}^{2}
$$  

The estimate, $\sigma_{n}$ , of the volatility of a variable for day $n$ (made at the end of d $\exists{}\mathrm{y}n\mathrm{~-~}1\mathrm{~}$ is calculated from $\sigma_{n-1}$ (the estimate that was made at the end of day $n-2$ of the volatility for day $n-1,$ and $u_{n-1}$ (the most recent daily percentage change in the variable).  

To understand why equation (23.7) corresponds to weights that decrease exponentially, we substitute for $\bar{\sigma_{n-1}^{2}}$ to get  

$$
\sigma_{n}^{2}=\lambda[\lambda\sigma_{n-2}^{2}+(1-\lambda)u_{n-2}^{2}]+(1-\lambda)u_{n-1}^{2}
$$  

or  

$$
\sigma_{n}^{2}=(1-\lambda)(u_{n-1}^{2}+\lambda u_{n-2}^{2})+\lambda^{2}\sigma_{n-2}^{2}
$$  

Substituting in a similar way for $\sigma_{n-2}^{2}$ gives  

$$
\sigma_{n}^{2}=(1-\lambda)(u_{n-1}^{2}+\lambda u_{n-2}^{2}+\lambda^{2}u_{n-3}^{2})+\lambda^{3}\sigma_{n-3}^{2}
$$  

Continuing in this way gives  

$$
\sigma_{n}^{2}=(1-\lambda)\sum_{i=1}^{m}\lambda^{i-1}u_{n-i}^{2}+\lambda^{m}\sigma_{n-m}^{2}
$$  

For large $m$ , the term $\lambda^{m}\sigma_{n-m}^{2}$ is sufficiently small to be ignored, so that equation (23.7) is the same as equation (23.4) with $\alpha_{i}=(\dot{1}-\lambda)\lambda^{i-1}$ . The weights for the $u_{i}$ decline at rate $\lambda$ as we move back through time. Each weight is $\lambda$ times the previous weight.  

# Example 23.1  

Suppose that $\lambda$ is 0.90, the volatility estimated for a market variable for day $n\mathrm{~-~}1$ is $1\%$ per day, and during day. $n\mathrm{~-~}1$ the market variable increased by. $2\%$ . This means that $\sigma_{n-1}^{2}=0.01^{2}=0.0001$ and $u_{n-1}^{2}=0.02^{2}=0.0004.$ Equation (23.7) gives  

$$
\sigma_{n}^{2}=0.9\times0.0001+0.1\times0.0004=0.00013
$$  

The estimate of the volatility, $\sigma_{n}.$ for day $n$ is therefore $\sqrt{0.00013}$ , or $1.14\%$ , per day. Note that the expected value of $u_{n-1}^{2}$ is $\sigma_{n-1}^{2}$ , or 0.0001. In this example, the realized value of $u_{n-1}^{2}$ is greater than the expected value, and as a result our volatility estimate increases. If the realized value of $u_{n-1}^{2}$ had been less than its expected value, our estimate of the volatility would have decreased.  

The EWMA approach has the attractive feature that relatively little data need be. stored. At any given time, only the current estimate of the variance rate and the most recent observation on the value of the market variable need be remembered. When a new observation on the market variable is obtained, a new daily percentage change is. calculated and equation (23.7) is used to update the estimate of the variance rate. The old estimate of the variance rate and the old value of the market variable can then be discarded.  

The EwMA approach is designed to track changes in the volatility. Suppose there is a big move in the market variable on day. $n\mathrm{~-~}1$ , so that. $u_{n-1}^{2}$ is large. From equation (23.7) this causes the estimate of the current volatility to move upward. The value of $\lambda$ governs how responsive the estimate of the daily volatility is to the. most recent daily percentage change. A low value of. $\lambda$ leads to a great deal of weight. being given to the $\overline{{u_{n-1}^{2}}}$ when $\sigma_{n}$ is calculated. In this case, the estimates produced for. the volatility on successive days are themselves highly volatile. A high value of $\lambda$ (i.e.,. a value close to 1.0) produces estimates of the daily volatility that respond relatively. slowly to new information provided by the daily percentage change..  

The RiskMetrics database, which was originally created by JP Morgan and made publicly available in 1994, used the EWMA model with $\lambda=0.94$ for updating daily volatility estimates. This is because the company found that, across a range of different market variables, this value of. $\lambda$ gives forecasts of the variance rate that come closest to the realized variance rate. The realized variance rate on a particular day was calculated as an equally weighted average of the. $u_{i}^{2}$ on the subsequent 25 days (see Problem 23.19).  
