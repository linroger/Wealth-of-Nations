# 15.1 LOGNORMAL PROPERTY OF STOCK PRICES  

The model of stock price behavior used by Black, Scholes, and Merton is the model we developed in Chapter 14. It assumes that percentage changes in the stock price in a very short period of time are normally distributed. Define  

$\mu$ : Expected return in a short period of time (annualized) $\sigma$ :Volatility of the stock price..  

The mean and standard deviation of the return in time $\Delta t$ are approximately $\mu\Delta t$ and $\sigma\sqrt{\Delta t}$ , so that  

$$
\frac{\Delta S}{S}\sim\phi(\mu\Delta t,\sigma^{2}\Delta t)
$$  

where $\Delta S$ is the change in the stock price $S$ in time. $\Delta t$ and $\phi(m,\nu)$ denotes a normal distribution with mean $m$ and variance. $\nu$ (This is equation (14.9).)  

As shown in Section 14.7, the model implies that  

so that  

$$
\begin{array}{l}{{\displaystyle\ln S_{T}-\ln S_{0}\sim\phi\bigg[\bigg(\mu-{\frac{\sigma^{2}}{2}}\bigg)T,\sigma^{2}T\bigg]}}\ {{\displaystyle\ln{\frac{S_{T}}{S_{0}}}\sim\phi\bigg[\bigg(\mu-{\frac{\sigma^{2}}{2}}\bigg)T,\sigma^{2}T\bigg]}}\ {{\displaystyle\ln S_{T}\sim\phi\bigg[\ln S_{0}+\bigg(\mu-{\frac{\sigma^{2}}{2}}\bigg)T,\sigma^{2}T\bigg]}}\end{array}
$$  

and  

where $S_{T}$ is the stock price at a future time. $T$ and $S_{0}$ is the stock price at time 0. There is no approximation here. The variable ln $S_{T}$ is normally distributed, so that. $S_{T}$ has a lognormal distribution. The mean of ln $S_{T}$ is ln $S_{0}+\dot{(}\mu-\sigma^{2}/2)T$ and the standard deviation of ln $S_{T}$ is $\sigma\sqrt{T}$  

# Example 15.1  

Consider a stock with an initial price of $\$40$ , an expected return of $16\%$ per annum, and a volatility of $20\%$ per annum. From equation (15.3), the probability distribution of the stock price $S_{T}$ in 6 months' time is given by  

$$
\begin{array}{l}{\ln S_{T}\sim\phi[\ln40+(0.16-0.2^{2}/2)\times0.5,0.2^{2}\times0.5]}\ {\ln S_{T}\sim\phi(3.759,0.02)}\end{array}
$$  

There is a $95\%$ probability that a normally distributed variable has a value within 1.96 standard deviations of its mean. In this case, the standard deviation is $\sqrt{0.02}=0.141$ Hence, with $95\%$ confidence,  

$$
3.759-1.96\times0.141<\ln S_{T}<3.759+1.96\times0.141
$$  

This can be written  

$$
e^{3.759-1.96\times0.141}<S_{T}<e^{3.759+1.96\times0.141}
$$  

or  

$$
32.55<S_{T}<56.56
$$  

Thus, there is a $95\%$ probability that the stock price in 6 months will lie between 32.55 and 56.56.  

![](images/20c4902095e5ce8a10dab9ab1a7a7f49bbc37705a3c43e8915fe969b696330ef.jpg)  
Figure 15.1 Lognormal distribution.  

A variable that has a lognormal distribution can take any value between zero and infinity. Figure 15.1 illustrates the shape of a lognormal distribution. Unlike the normal distribution, it is skewed so that the mean, median, and mode are all different. From equation (15.3) and the properties of the lognormal distribution, it can be shown that the expected value $E(S_{T})$ Of $S_{T}$ is given by  

$$
E(S_{T})=S_{0}e^{\mu T}
$$  

The variance $\mathrm{var}(S_{T})$ of $S_{T}$ can be shown to be given by2  

$$
\mathrm{var}(S_{T})=S_{0}^{2}e^{2\mu T}(e^{\sigma^{2}T}-1)
$$  

# Example 15.2  

Consider a stock where the current price is $\$20$ , the expected return is $20\%$ per annum, and the volatility is $40\%$ per annum. The expected stock price, $E(S_{T})$ , and the variance of the stock price, $\mathrm{var}(S_{T})$ , in 1 year are given by  

$$
E(S_{T})=20e^{0.2\times1}=24.43\quad\mathrm{and}\quad\mathrm{var}(S_{T})=400e^{2\times0.2\times1}(e^{0.4^{2}\times1}-1)=103.54
$$  

The standard deviation of the stock price in 1 year is $\sqrt{103.54}.$ or 10.18.  
