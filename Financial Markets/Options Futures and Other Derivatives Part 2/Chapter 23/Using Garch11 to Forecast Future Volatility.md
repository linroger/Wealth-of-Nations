# 23.6 USING GARCH(1,1) TO FORECAST FUTURE VOLATILITY  

The variance rate estimated at the end of day $n-1$ for day $n$ , when GARCH(1,1) is used, is  

$$
\sigma_{n}^{2}=(1-\alpha-\beta)V_{L}+\alpha u_{n-1}^{2}+\beta\sigma_{n-1}^{2}
$$  

so that  

$$
\sigma_{n}^{2}-V_{L}=\alpha(u_{n-1}^{2}-V_{L})+\beta(\sigma_{n-1}^{2}-V_{L})
$$  

On day $n+t$ in the future,  

$$
\sigma_{n+t}^{2}-V_{L}=\alpha(u_{n+t-1}^{2}-V_{L})+\beta(\sigma_{n+t-1}^{2}-V_{L})
$$  

The expected value of $u_{n+t-1}^{2}$ is $\sigma_{n+t-1}^{2}$ . Hence,  

$$
E[\sigma_{n+t}^{2}-V_{L}]=(\alpha+\beta)E[\sigma_{n+t-1}^{2}-V_{L}]
$$  

where $E$ denotes expected value. Using this equation repeatedly yields  

$$
E[\sigma_{n+t}^{2}-V_{L}]=(\alpha+\beta)^{t}(\sigma_{n}^{2}-V_{L})
$$  

or  

$$
E[\sigma_{n+t}^{2}]=V_{L}+(\alpha+\beta)^{t}(\sigma_{n}^{2}-V_{L})
$$  

This equation forecasts the volatility on day. $n+t$ using the information available at the. end of day $n-1,$ In the EWMA model, $\alpha+\beta=1$ and equation (23.13) shows that the expected future variance rate equals the current variance rate. When. $\alpha+\beta<1$ , the final term in the equation becomes progressively smaller as. $t$ increases. Figure 23.3 shows the expected path followed by the variance rate for situations where the current variance rate is different from $V_{L}$ . As mentioned earlier, the variance rate exhibits mean reversion. with a reversion level of. $V_{L}$ and a reversion rate of $1-\alpha-\beta$ . Our forecast of the future. variance rate tends towards $V_{L}$ as we look further and further ahead. This analysis. emphasizes the point that we must have. $\alpha+\beta<1$ for a stable GARCH(1,1) process. When $\alpha+\beta>1$ , the weight given to the long-term average variance is negative and the process is "mean fleeing" rather than "mean reverting"..  

For the S&P 500 data considered earlier, $\alpha+\beta=0.9714$ and $V_{L}=0.0001391$ Suppose that the estimate of the current variance rate per day is O.o003. (This corresponds to a volatility of $1.732\%$ per day.) In 10 days, the expected variance rate is  

$$
0.0001391+0.9714^{10}(0.0003-0.0001391)=0.0002594
$$  

![](dc645dc8f9e1545fdc6fffaaed47c0f8d5c6c8d9b1fb240387e6c03834364387.jpg)  
Figure 23.3 Expected path for the variance rate when (a) current variance rate is above long-term variance rate and (b) current variance rate is below long-term variance rate.  

The expected volatility per day is $1.61\%$ , still well above the long-term volatility of $1.18\%$ per day. However, the expected variance rate in 100 days is  

$$
0.0001391+0.9714^{100}(0.0003-0.0001391)=0.0001479
$$  

and the expected volatility per day is $1.22\%$ , much closer to the long-term volatility.  

# Volatility Term Structures  

Suppose it is day $n$ . Define:  

$$
V(t)=E(\sigma_{n+t}^{2})
$$  

and  

$$
a=\ln\frac{1}{\alpha+\beta}
$$  

so that equation (23.13) becomes  

$$
V(t)=V_{L}+e^{-a t}[V(0)-V_{L}]
$$  

Here, $V(t)$ is an estimate of the instantaneous variance rate in $t$ days. The average variance rate per day between today and time $T$ is given by  

$$
{\frac{1}{T}}{\int_{0}^{T}}V(t)d t=V_{L}+{\frac{1-e^{-a T}}{a T}}[V(0)-V_{L}]
$$  

The larger $T$ is, the closer this is to $V_{L}$ . Define $\sigma(T)$ as the volatility per annum that should be used to price a $T$ day option under GARCH(1,1). Assuming 252 days per  

Table 23.3 S&P 500 volatility term structure predicted from GARCH(1,1).   


<html><body><table><tr><td>Option life (days)</td><td>10</td><td>30</td><td>50</td><td>100</td><td>500</td></tr><tr><td>Option volatility (% per annum)</td><td>26.5</td><td>24.9</td><td>23.8</td><td>22.0</td><td>19.5</td></tr></table></body></html>  

year, $\sigma(T)^{2}$ is 252 times the average variance rate per day, so that  

$$
\sigma(T)^{2}=252\bigg(V_{L}+{\frac{1-e^{-a T}}{a T}}[V(0)-V_{L}]\bigg)
$$  

As discussed in Chapter 20, the market prices of different options on the same asset are often used to calculate a volatility term structure. This is the relationship between the implied volatilities of the options and their maturities. Equation (23.14) can be used to estimate a volatility term structure based on the GARCH(1,1) model. The estimated volatility term structure is not usually the same as the implied volatility term structure. However, as we will show, it is often used to predict the way that the implied volatility term structure will respond to volatility changes.  

When the current volatility is above the long-term volatility, the GARCH(1,1) model estimates a downward-sloping volatility term structure. When the current volatility is below the long-term volatility, it estimates an upward-sloping volatility term structure. In the case of the S&P 500 data, $a=\ln(1/0.97137)=0.02905$ and $V_{L}=0.0001391$ . Suppose that the current variance rate per day, $V(0)$ , is estimated as 0.0003 per day. It follows from equation (23.14) that  

$$
\sigma(T)^{2}=252\bigg(0.0001391+{\frac{1-e^{-0.02905T}}{0.02905T}}(0.0003-0.0001391)\bigg)
$$  

where $T$ is measured in days. Table 23.3 shows the volatility per year for different values of $T$  

# Impact of Volatility Changes  

Equation (23.14) can be written  

$$
\sigma(T)^{2}=252\biggl[V_{L}+{\frac{1-e^{-a T}}{a T}}\biggl({\frac{\sigma(0)^{2}}{252}}-V_{L}\biggr)\biggr]
$$  

When $\sigma(0)$ changes bye $\Delta\sigma(0),\sigma(T)$ changes by approximately  

$$
\frac{1-e^{-a T}}{a T}\frac{\sigma(0)}{\sigma(T)}\Delta\sigma(0)
$$  

Table 23.4 shows the effect of a volatility change on options of varying maturities for the S&P 500 data considered above. We assume as before that $V(0)=0.0003$ , so that $\sigma(0)=\sqrt{252}\times\sqrt{0.0003}=27.50\%$ The table considers a 100-basis-point change in the instantaneous volatility from $27.50\%$ per year to. $28.50\%$ per year. This means that $\Delta\sigma(0)=0.01$ , or $1\%$  

Table 23.4Impact of $1\%$ change in the instantaneous volatility predicted from GARCH(1,1).   


<html><body><table><tr><td>Option life (days)</td><td>10</td><td>30</td><td>50</td><td>100</td><td>500</td></tr><tr><td>Increase in volatility (%)</td><td>0.90</td><td>0.74</td><td>0.61</td><td>0.41</td><td>0.10</td></tr></table></body></html>  

Many financial institutions use analyses such as this when determining the exposure of their books to volatility changes. Rather than consider an across-the-board increase of $1\%$ in implied volatilities when calculating vega, they relate the size of the volatility increase that is considered to the maturity of the option. Based on Table 23.4, a $0.90\%$ volatility increase would be considered for a 10-day option, a. $0.74\%$ increase for a 30-day option, a $0.61\%$ increase for a 50-day option, and so on..  
