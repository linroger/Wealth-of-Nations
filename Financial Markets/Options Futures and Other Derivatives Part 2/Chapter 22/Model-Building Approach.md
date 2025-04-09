# 22.3 MODEL-BUILDING APPROACH  

The main alternative to historical simulation is the model-building approach. Before. getting into the details of the approach, it is appropriate to mention one issue concerned with the units for measuring volatility.  

# Daily Volatilities  

In option pricing, time is usually measured in years, and the volatility of an asset is usually quoted as a "volatility per year". When using the model-building approach to calculate VaR or ES for market risk, time is usually measured in days and the volatility of an asset is usually quoted as a "volatility per day."  

What is the relationship between the volatility per year used in option pricing and the volatility per day used in VaR or ES calculations? Let us define $\sigma_{\mathrm{year}}$ as the volatility per year of a certain asset and $\sigma_{\mathrm{day}}$ as the equivalent volatility per day of the asset. Assuming 252 trading days in a year, equation (15.2) gives the standard deviation of the continuously compounded return on the asset in one year as either $\sigma_{\mathrm{year}}$ or $\sigma_{\mathrm{day}}\sqrt{252}$ . It follows that  

$$
\sigma_{\mathrm{year}}=\sigma_{\mathrm{day}}{\sqrt{252}}\quad{\mathrm{or}}\quad\sigma_{\mathrm{day}}=\sigma_{\mathrm{year}}/{\sqrt{252}}
$$  

so that daily volatility is about $6\%$ of annual volatility..  

As pointed out in Section $15.4,\upsigma_{\mathrm{day}}$ is approximately equal to the standard deviation of. the percentage change in the asset price in one day. For the purposes of calculating VaR. or ES we assume exact equality. The daily volatility of an asset price (or any other variable) is therefore defined as equal to the standard deviation of the percentage change. in one day.  

Our discussion in the next few sections assumes that estimates of daily volatilities and correlations are available. Chapter 23 discusses how the estimates can be produced.  

# Single-Asset Case  

Consider how VaR is calculated using the model-building approach in a very simple situation where the portfolio consists of a position in a single stock:. $\$10$ million in shares. of Microsoft. We suppose that. $N=10$ and $X=99$ , so that we are interested in the loss level over 10 days that we are $99\%$ confident will not be exceeded. Initially, we consider a. 1-day time horizon..  

Assume that the volatility of Microsoft is $2\%$ per day (corresponding to about $32\%$ per year). Because the size of the position is $\$10$ million, the standard deviation of daily changes in the value of the position is $2\%$ of $\$10$ million, or. $\$200,000$  

It is customary in the model-building approach to assume that the expected change in a market variable over the time period considered is zero. This is not exactly true, but it is a reasonable assumption. The expected change in the price of a market variable over a short time period is generally small when compared with the standard deviation of the change. Suppose, for example, that Microsoft has an expected return of $20\%$ per annum. Over a 1-day period, the expected return is $0.20/252$ , Or about $0.08\%$ , whereas the standard deviation of the return is $2\%$ . Over a 10-day period, the expected return is $0.08\times10$ , or about $0.8\%$ , whereas the standard deviation of the return is $2\sqrt{10}$ , or about $6.3\%$  

So far, we have established that the change in the value of the portfolio of Microsoft shares over a 1-day period has a standard deviation of $\$200,000$ and (at least approximately) a mean of zero. We assume that the change is normally distributed. From the  

Excel NORMSINV function, $N^{-1}(0.01)=-2.326$ . This means that there is a $1\%$ probability that a normally distributed variable will decrease in value by more than 2.326 standard deviations. Equivalently, it means that we are. $99\%$ certain that a. normally distributed variable will not decrease in value by more than 2.326 standard deviations. The 1-day $99\%$ VaR for our portfolio consisting of a. $\$10$ million position in. Microsoft is therefore.  

$$
2.326\times200,000=\$465,300
$$  

As discussed earlier, the $N$ -day $\mathrm{VaR}$ is calculated as $\sqrt{N}$ times the 1-day VaR. The 10-day $99\%$ VaR for Microsoft is therefore  

$$
465,300\times\sqrt{10}=\S1,471,300
$$  

Consider next a portfolio consisting of a $\$5$ million position in AT&T, and suppose the daily volatility of AT&T is $1\%$ (approximately $16\%$ per year). A similar calculation. to that for Microsoft shows that the standard deviation of the change in the value of the portfolio in 1 day is.  

$$
5,000,000\times0.01=50.000
$$  

Assuming the change is normally distributed, the 1-day $99\%$ VaR is  

$$
50,000\times2.326=\S116,300
$$  

and the 10-day $99\%$ VaR is  

$$
116,300\times\sqrt{10}=\$367,800
$$  

# Two-Asset Case  

Now consider a portfolio consisting of both. $\$10$ million of Microsoft shares and. $\$5$ million of AT&T shares. We suppose that the returns on the two shares have a bivariate normal distribution with a correlation of O.3. A standard result in statistics tells us that, if two variables $X$ and $Y$ have standard deviations equal to $\sigma_{X}$ and $\sigma_{Y}$ with the coefficient of correlation between them equal to. $\rho$ , the standard deviation of $X+Y$ is given by  

$$
\sigma_{X+Y}=\sqrt{\sigma_{X}^{2}+\sigma_{Y}^{2}+2\rho\sigma_{X}\sigma_{Y}}
$$  

To apply this result, we set. $X$ equal to the change in the value of the position in Microsoft over a 1-day period and. $Y$ equal to the change in the value of the position in. AT&T over a 1-day period, so that.  

$$
\sigma_{X}=200,000\quad\mathrm{and}\quad\sigma_{Y}=50,000
$$  

The standard deviation of the change in the value of the portfolio consisting of both stocks over a 1-day period is therefore  

$$
\sqrt{200,000^{2}+50,000^{2}+2\times0.3\times200,000\times50,000}=220,200
$$  

The mean change is assumed to be zero and the change is normally distributed. So the 1-day $99\%$ VaR is therefore  

$$
220,200\times2.326=\mathbb{\mathbb{\mathbb{S}}}512,300
$$  

The 10-day $99\%$ VaR is $\sqrt{10}$ times this, or $\$1,620,100$  

# The Benefits of Diversification  

In the example we have just considered:  

1. The 10-day $99\%$ VaR for the portfolio of Microsoft shares is. $\$1,471,300$ 2. The 10-day $99\%$ VaR for the portfolio of AT&T shares is. $\$367,800$ 3. The 10-day $99\%$ VaR for the portfolio of both Microsoft and AT&T shares is $\$1,620,100$  

The amount  

$$
(1,471,300+367,800)-1,620,100=\mathbb{\mathbb{S}}219,000
$$  

represents the benefits of diversification. If Microsoft and AT&T were perfectly correlated, the VaR for the portfolio of both Microsoft and AT&T would equal the VaR for the Microsoft portfolio plus the VaR for the AT&T portfolio. Less than perfect correlation leads to some of the risk being "diversified away. 6  

# ES Calculation  

When the loss is normally distributed with mean $\mu$ , and standard deviation $\sigma$ , it can be shown that ES with a confidence level of $X$ is given by  

$$
\mathrm{ES}=\mu+\sigma{\frac{e^{-Y^{2}/2}}{\sqrt{2\pi}(1-X)}}
$$  

where $Y$ is the $X\mathrm{th}$ percentile point of the standard normal distribution (i.e., it is the point on a normal distribution with mean zero and standard deviation one that has a probability $1-X$ of being exceeded). This shows that, when $\mu$ is assumed to be zero,. ES like VaR is proportional to $\sigma$  

The formula shows that in our example the ten-day ES for the Microsoft portfolio with $99\%$ confidence ( $X=0.99$ and $Y=2.326$ ) is $\$1,48$ ; the ten-day ES for the. AT&T portfolio with $99\%$ confidence is $\$421,400$ ; and the ten-day ES for the combined. portfolio with $99\%$ confidence is $\$1,856,100$  
