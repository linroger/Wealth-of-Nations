# 15.3 THE EXPECTED RETURN  

The expected return, $\mu$ , required by investors from a stock depends on the riskiness of the stock. The higher the risk, the higher the expected return. It also depends on the level of interest rates in the economy. The higher the level of interest rates, the higher. the expected return required on any given stock. Fortunately, we do not have to concern. ourselves with the determinants of $\mu$ in any detail. It turns out that the value of a stock option, when expressed in terms of the value of the underlying stock, does not depend on $\mu$ at all. Nevertheless, there is one aspect of the expected return from a stock that frequently causes confusion and needs to be explained.  

Our model of stock price behavior implies that, in a very short period of time. $\Delta t$ , the mean return is $\mu\Delta t$ It is natural to assume from this that $\mu$ is the expected continuously compounded return on the stock. However, this is not the case. The continuously compounded return, $x$ , actually realized over a period of time of length $T$  

is given by equation (15.6) as  

$$
x=\frac{1}{T}\mathrm{ln}\frac{S_{T}}{S_{0}}
$$  

and, as indicated in equation (15.7), the expected value $E(x)$ of $x$ is $\mu-\sigma^{2}/2$  

The reason why the expected continuously compounded return is different from $\mu$ is subtle, but important. Suppose we consider a very large number of very short periods of time of length $\Delta t.$ Define $S_{i}$ as the stock price at the end of the ith interval and $\Delta S_{i}$ as $S_{i+1}-S_{i}.$ Under the assumptions we are making for stock price behavior, the arithmetic. average of the returns on the stock in each interval is close to. $\mu$ . In other words,. $\mu\Delta t$ is close to the arithmetic mean of the. $\Delta S_{i}/S_{i}.$ However, the expected return over the whole. period covered by the data, expressed with a compounding interval of. $\Delta t$ , is a geometric average and is close to. $\mu\mathrm{~-~}\sigma^{\hat{2}}/2$ , not $\mu$ 3 Business Snapshot 15.1 provides a numerical example concerning the mutual fund industry to illustrate why this is so..  

For another explanation of what is going on, we start with equation (15.4):  

$$
E(S_{T})=S_{0}e^{\mu T}
$$  

Taking logarithms, we get  

$$
\ln[E(S_{T})]=\ln(S_{0})+\mu T
$$  

It is now tempting to set $\ln[E(S_{T})]=E[\ln(S_{T})]$ , so that $E[\ln(S_{T})]-\ln(S_{0})=\mu T$ or $E[\ln(S_{T}/S_{0})]=\mu T$ which leads to $E(x)=\mu$ However, we cannot do this because ln is a nonlinear function. In fact, $\ln[E(S_{T})]>E[\ln(S_{T})]$ , so that $E[\ln(S_{T}/S_{0})]<\mu T,$ which leads to $E(x)<\mu$ . (As shown above, $E(x)=\mu-\sigma^{2}/2.$  
